---
title: Buscar y eliminar mensajes de correo electrónico en la organización
description: Use la característica de búsqueda y depuración en el portal de cumplimiento de Microsoft Purview para buscar y eliminar un mensaje de correo electrónico de todos los buzones de la organización.
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection:
- tier1
- purview-compliance
- content-search
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: f99f2ebdb6b2e05d5846cdf1a4570cc227fa0752
ms.sourcegitcommit: e7dbe3b0d97cd8c64b5ae15f990d5e4b1dc9c464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/24/2022
ms.locfileid: "68687936"
---
# <a name="search-for-and-delete-email-messages"></a>Buscar y eliminar mensajes de correo electrónico

> [!TIP]
>This article is for administrators. Are you trying to find items in your mailbox that you want to delete? See [Find a message or item with Instant Search](https://support.office.com/article/69748862-5976-47b9-98e8-ed179f1b9e4d).

You can use the Content search feature to search for and delete email messages from all mailboxes in your organization. This can help you find and remove potentially harmful or high-risk email, such as:

- Mensajes que contienen virus o datos adjuntos peligrosos
- Mensajes de suplantación de identidad
- Mensajes que contienen datos confidenciales

> [!TIP]
> Si su organización tiene una suscripción a Defender para Office 365 Plan 2, se recomienda usar el procedimiento detallado en [Corregir el correo electrónico malintencionado que se ha entregado en Office 365](/microsoft-365/security/office-365-security/remediate-malicious-email-delivered-office-365), en lugar de seguir el procedimiento descrito en este artículo.

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="before-you-begin"></a>Antes de empezar

- El flujo de trabajo de búsqueda y purga descrito en este artículo no elimina los mensajes de chat ni ningún otro contenido de Microsoft Teams. Si la búsqueda de contenido que se crea en el paso 2 devuelve elementos de Microsoft Teams, esos elementos no se eliminarán cuando se purguen los elementos en el paso 3. Para buscar y eliminar mensajes de chat, vea [Buscar y purgar mensajes de chat en Teams](search-and-delete-Teams-chat-messages.md).
- Para crear y ejecutar una búsqueda de contenido, tiene que ser un miembro del grupo de roles *Administrador de eDiscovery* o que se le asigne el rol *Búsqueda de cumplimiento* en el portal de cumplimiento de Microsoft Purview. Para eliminar mensajes, debe ser miembro del grupo de roles *Administración* de la organización o tener asignado el rol *Buscar y purgar* en el portal de cumplimiento Para obtener información sobre cómo agregar usuarios a un grupo de roles, consulte [Asignación de permisos de exhibición de documentos electrónicos](assign-ediscovery-permissions.md).

  > [!NOTE]
  > El rol *Administración de la organización* existe en Exchange Online y en el portal de cumplimiento. Se trata de grupos de roles independientes que conceden permisos diferentes. Ser miembro de la *Administración de la organización* en Exchange Online no concede los permisos necesarios para eliminar mensajes de correo electrónico. Si no tiene asignado el rol *Buscar y purgar* en el portal de cumplimiento (ya sea directamente o a través de un grupo de roles como *Organization Management*), recibirá un error en el paso 3 al ejecutar el cmdlet *New-ComplianceSearchAction* con el mensaje "No se puede encontrar un parámetro que coincida con el nombre del parámetro 'Purge'".

- Debe usar Seguridad y cumplimiento de PowerShell para eliminar mensajes. Consulte [Paso 1: Conectar a Seguridad y cumplimiento de PowerShell](#step-1-connect-to-security--compliance-powershell) para obtener instrucciones sobre cómo conectarse.
- A maximum of 10 items per mailbox can be removed at one time. Because the capability to search for and remove messages is intended to be an incident-response tool, this limit helps ensure that messages are quickly removed from mailboxes. This feature isn't intended to clean up user mailboxes.
- El número máximo de buzones en una búsqueda de contenido que puede usar para eliminar elementos al realizar una acción de búsqueda y depuración es 50 000. Si la búsqueda (creada en el [paso 2](#step-2-create-a-content-search-to-find-the-message-to-delete)) se realiza en más de 50 000 buzones, la acción de depuración (creada en el paso 3) no se realizará correctamente. Hacer la búsqueda en más de 50 000 buzones en una sola búsqueda suele ocurrir cuando se configura para que incluya a todos los buzones de la organización. Esta restricción aplica incluso cuando haya menos de 50 000 buzones que contengan elementos que coincidan con la consulta de la búsqueda. Consulte la sección de [Más información](#more-information) para obtener instrucciones sobre el uso de los filtros de permisos de búsqueda para buscar y depurar elementos de más de 50 000 buzones.
- El procedimiento descrito en este artículo solo se puede usar para eliminar elementos de buzones y carpetas públicas de Exchange Online. No se puede usar para eliminar el contenido de los sitios de SharePoint o OneDrive para la Empresa.
- Los elementos de correo electrónico en un conjunto de revisiones en un caso de eDiscovery (Premium) no se pueden eliminar utilizando los procedimientos de este artículo. Esto se debe a que los elementos de un conjunto de revisiones se almacenan en una ubicación de almacenamiento de Azure y no en el servicio activo. Esto significa que no se devolverán por la búsqueda de contenido que creó en el paso 1. Para eliminar elementos en un conjunto de revisiones, tiene que eliminar el caso de eDiscovery (Premium) que contiene el conjunto de revisiones. Para más información, consulte [Cerrar o eliminar un caso de eDiscovery (Premium)](close-or-delete-case.md).

## <a name="step-1-connect-to-security--compliance-powershell"></a>Paso 1: Conectarse a Seguridad y cumplimiento de PowerShell

El primer paso es conectarse a [PowerShell de cumplimiento de seguridad &](/powershell/exchange/scc-powershell) para su organización. Para obtener instrucciones paso a paso, vea [Conectarse Seguridad y cumplimiento de PowerShell](/powershell/exchange/connect-to-scc-powershell).

## <a name="step-2-create-a-content-search-to-find-the-message-to-delete"></a>Paso 2: Crear una búsqueda de contenido para encontrar el mensaje que se desea eliminar

El segundo paso es crear y ejecutar una búsqueda de contenido para encontrar el mensaje que desea quitar de los buzones de la organización. Puede crear la búsqueda mediante el [portal de cumplimiento Microsoft Purview](https://compliance.microsoft.com) o mediante la ejecución de los cmdlets **New-ComplianceSearch** y **Start-ComplianceSearch** en PowerShell de seguridad & cumplimiento. Los mensajes que coincidan con la consulta de esta búsqueda se eliminarán al ejecutar el comando **New-ComplianceSearchAction-Purge** en el [paso 3](#step-3-delete-the-message). Para obtener información sobre cómo crear una búsqueda de contenido y configurar consultas de búsqueda, consulte los artículos siguientes:

- [Búsqueda de contenido en Office 365](content-search.md)
- [Consultas de palabras clave para búsqueda de contenido](keyword-queries-and-search-conditions.md)
- [New-ComplianceSearch](/powershell/module/exchange/New-ComplianceSearch)
- [Start-ComplianceSearch](/powershell/module/exchange/Start-ComplianceSearch)

> [!NOTE]
> Las ubicaciones de contenido en la búsqueda de contenido que ha creado en este paso no pueden incluir sitios de SharePoint o OneDrive para la Empresa. Puede incluir solo buzones y carpetas públicas en una búsqueda de contenido que se usará para enviar mensajes de correo electrónico. Si la búsqueda de contenido incluye sitios, recibirá un error en el paso 3 al ejecutar el cmdlet **New- ComplianceSearchAction**.

### <a name="tips-for-finding-messages-to-remove"></a>Sugerencias para buscar mensajes que quiere eliminar

The goal of the search query is to narrow the results of the search to only the message or messages that you want to remove. Here are some tips:

- Si conoce el texto o la frase exacta usados en la línea de asunto del mensaje, use la propiedad **Subject** en la consulta de búsqueda.
- Si conoce la fecha exacta (o el intervalo de fechas) del mensaje, incluya la propiedad **Received** en la consulta de búsqueda.
- Si conoce quién envió el mensaje, incluya la propiedad **From** en la consulta de búsqueda.
- Obtenga una vista previa de los resultados de la búsqueda para comprobar que la búsqueda solo devolvió el mensaje (o los mensajes) que quiere eliminar.
- Use las estadísticas de estimación de búsqueda (que se muestran en el panel de detalles de la búsqueda en el portal de cumplimiento o mediante el cmdlet [Get-ComplianceSearch](/powershell/module/exchange/get-compliancesearch)) para obtener un recuento del número total de resultados.

Estos son dos ejemplos de consultas para buscar mensajes de correo electrónico sospechosos.

- Esta consulta devuelve los mensajes recibidos por los usuarios entre el 13 de abril de 2016 y el 14 de abril de 2016 que contengan las palabras "acción" y "necesario" en la línea de asunto.

  ```powershell
  (Received:4/13/2016..4/14/2016) AND (Subject:'Action required')
  ```

- Esta consulta devuelve los mensajes enviados por user@contoso.com y que contienen la frase exacta "Actualizar la información de la cuenta" en la línea de asunto.

  ```powershell
  (From:user@contoso.com) AND (Subject:"Update your account information")
  ```

Este es un ejemplo del uso de una consulta para crear e iniciar una búsqueda mediante la ejecución de los cmdlets **New-ComplianceSearch** y **Start-ComplianceSearch** para buscar en todos los buzones de la organización:

```powershell
$Search=New-ComplianceSearch -Name "Remove Phishing Message" -ExchangeLocation All -ContentMatchQuery '(Received:4/13/2016..4/14/2016) AND (Subject:"Action required")'
Start-ComplianceSearch -Identity $Search.Identity
```

## <a name="step-3-delete-the-message"></a>Paso 3: Eliminar el mensaje

Después de crear y restringir una búsqueda de contenido a fin de obtener el mensaje que desea eliminar, el último paso es ejecutar el comando **New-ComplianceSearchAction -Purge** en el PowerShell del Centro de Seguridad y cumplimiento para eliminar el mensaje.

Puede eliminar el mensaje de forma temporal o permanente. Un mensaje eliminado temporalmente se mueve a la carpeta Elementos recuperables de un usuario y se conserva hasta que expire el período de retención de elementos eliminados. Los mensajes eliminados permanentemente se marcan para la eliminación definitiva del buzón y se eliminarán la próxima vez que el Asistente para carpetas administradas procese el buzón. Si se habilita la recuperación de un único elemento en el buzón, los elementos eliminados permanentemente se eliminarán definitivamente cuando expire el período de retención de elementos eliminados. Si un buzón está en retención, los mensajes eliminados se conservan hasta que expire la duración del período de retención de un elemento o hasta que se quite la retención del buzón.

> [!NOTE]
> Como se ha indicado anteriormente, los elementos de Microsoft Teams devueltos por la búsqueda de contenido no se eliminan cuando se ejecuta el comando **New-ComplianceSearchAction -Purge** .

Para ejecutar los siguientes comandos para eliminar mensajes, asegúrese de que está [conectado a Seguridad y cumplimiento de PowerShell](/powershell/exchange/connect-to-scc-powershell).

### <a name="soft-delete-messages"></a>Eliminar mensajes temporalmente

En el ejemplo siguiente, el comando elimina temporalmente los resultados de la búsqueda obtenidos por una búsqueda de contenido denominada "quitar el mensaje de suplantación de identidad".

```powershell
New-ComplianceSearchAction -SearchName "Remove Phishing Message" -Purge -PurgeType SoftDelete
```

### <a name="hard-delete-messages"></a>Eliminar mensajes de forma permanente

Para eliminar de forma permanente los elementos devueltos por la búsqueda de contenido "quitar el mensaje de suplantación de identidad", ejecutaría este comando:

```powershell
New-ComplianceSearchAction -SearchName "Remove Phishing Message" -Purge -PurgeType HardDelete
```

Cuando ejecute los comandos anteriores para eliminar mensajes de forma temporal o permanente, la búsqueda especificada por el parámetro *SearchName* es la búsqueda de contenido que creó en el paso 1.

Para obtener más información, vea [ New-ComplianceSearchAction](/powershell/module/exchange/New-ComplianceSearchAction).

## <a name="more-information"></a>Más información

- **¿Cómo se obtiene el estado de la operación de búsqueda y eliminación?**

  Run the **Get-ComplianceSearchAction** to get the status on the delete operation. The object that is created when you run the **New-ComplianceSearchAction** cmdlet is named using this format:  `<name of Content Search>_Purge`.

- **¿Qué ocurre después de eliminar un mensaje?**

  Un mensaje que se elimina con el comando `New-ComplianceSearchAction -Purge -PurgeType HardDelete` se mueve a la carpeta de depuración y el usuario no puede obtener acceso a él. Después de mover el mensaje a la carpeta de depuración, el mensaje se conserva durante el período de retención de elementos eliminados si está habilitada la recuperación de un único elemento en el buzón. (En Microsoft 365, la recuperación de elemento único se habilita de manera predeterminada cuando se crea un nuevo buzón). Cuando expire el período de retención de elementos eliminados, se marca el mensaje para eliminarlo de forma permanente y se depura de Microsoft 365 la próxima vez que el Asistente para carpetas administradas procese el buzón.

  Si usa el comando `New-ComplianceSearchAction -Purge -PurgeType SoftDelete`, los mensajes se mueven a la carpeta de eliminaciones de la carpeta Elementos recuperables del usuario. No se depura inmediatamente de Microsoft 365. El usuario dispone de un plazo para recuperar los mensajes de la carpeta Elementos eliminados, que se basa en el período de retención de elementos eliminados configurado para el buzón. Una vez finalizado este período de retención (o si el usuario purga el mensaje antes de que expire), el mensaje se mueve a la carpeta Purgas y el usuario ya no puede acceder a él. Cuando el mensaje se encuentra en la carpeta de depuración, se conserva durante un período basado en el período de retención de elementos eliminados configurado para el buzón, si se habilitó la recuperación de elemento único en el buzón. (En Microsoft 365, la recuperación de elemento único se habilita de manera predeterminada cuando se crea un nuevo buzón). Cuando expire el período de retención de elementos eliminados, se marca el mensaje para eliminarlo de forma permanente y se depura de Microsoft 365 la siguiente vez que el Asistente para carpetas administradas procese el buzón.

- **¿Qué ocurre si tiene que eliminar un mensaje de más de 50 000 buzones?**

  Como se indicó anteriormente, puede realizar una operación de búsqueda y depuración en un máximo de 50 000 buzones (incluso si menos de 50 000 contienen elementos que coincidan con la consulta de la búsqueda). Si tiene que realizar una operación de búsqueda y depuración en más de 50 000 buzones, considere la posibilidad de crear filtros de permisos de búsqueda temporales que reduzcan el número de buzones en los que se buscará a menos de 50 000 buzones. Por ejemplo, si su organización contiene buzones de diferentes departamentos, comunidades autónomas o países, puede crear un filtro de permisos de búsqueda de buzón en función de una de esas propiedades de buzón para buscar en un subconjunto de buzones de su organización. Después de crear el filtro de permisos de búsqueda, debe crear la búsqueda (como se describe en el paso 1) y, después, eliminar el mensaje (como se describe en el paso 3). Luego, puede editar el filtro para buscar y depurar mensajes en un conjunto de buzones diferente. Para obtener más información sobre cómo crear filtros de permisos de búsqueda, vea [Configurar el filtrado de permisos para la búsqueda de contenido](permissions-filtering-for-content-search.md).

- **¿Se eliminarán los elementos sin indexar incluidos en los resultados de la búsqueda?**

  No, el comando New-ComplianceSearchAction-Purge no elimina elementos sin indexar.

- **¿Qué ocurre si se elimina un mensaje de un buzón colocado en conservación local o en retención por litigio o que está asignado a una directiva de retención de Microsoft 365?**

  After the message is purged and moved to the Purges folder, the message is retained until the hold duration expires. If the hold duration is unlimited, then items are retained until the hold is removed or the hold duration is changed.

- **¿Por qué el proceso de búsqueda y eliminación se divide entre distintos grupos de roles del Centro de seguridad y cumplimiento?**

  As previously explained, a person has to be a member of the eDiscovery Manager role group or be assigned the Compliance Search management role to search mailboxes. To delete messages, a person has to be a member of the Organization Management role group or be assigned the Search And Purge management role. This makes it possible to control who can search mailboxes in the organization and who can delete messages.
