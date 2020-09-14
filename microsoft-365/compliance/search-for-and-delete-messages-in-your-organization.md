---
title: Buscar y eliminar mensajes de correo electrónico en la organización
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 3526fd06-b45f-445b-aed4-5ebd37b3762a
description: Use la característica de búsqueda y depuración en el Centro de seguridad y cumplimiento para buscar y eliminar un mensaje de correo electrónico de todos los buzones de la organización.
ms.openlocfilehash: f4bcd012708c0b7e9fa37b06288cda18ad4766cf
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/12/2020
ms.locfileid: "47546538"
---
# <a name="search-for-and-delete-email-messages"></a>Buscar y eliminar mensajes de correo electrónico

**Este artículo es para los administradores. ¿Está intentando buscar elementos que quiere eliminar en el buzón? Vea [Buscar un mensaje o elemento con la Búsqueda instantánea](https://support.office.com/article/69748862-5976-47b9-98e8-ed179f1b9e4d)**.

Puede usar la característica de búsqueda de contenido para buscar y eliminar un mensaje de correo electrónico de todos los buzones de la organización. De esta forma puede buscar y eliminar correos electrónicos potencialmente dañinos o de alto riesgo, como:

- Mensajes que contienen virus o datos adjuntos peligrosos

- Mensajes de suplantación de identidad

- Mensajes que contienen datos confidenciales

> [!CAUTION]
> Búsqueda y depuración es una característica eficaz que permite eliminar mensajes de correo electrónico de los buzones de la organización a cualquier usuario que tenga asignados los permisos necesarios.

## <a name="before-you-begin"></a>Antes de empezar

- Para crear y ejecutar una búsqueda de contenido, tiene que ser miembro del grupo de roles **Administrador de eDiscovery** o tener asignado el rol de administración **Búsqueda de cumplimiento**. Para eliminar mensajes, tiene que ser miembro del grupo de roles **Administración de la organización** o tener asignado el rol de administración **Búsqueda y depuración**. Para más información sobre cómo agregar usuarios a un grupo de roles, consulte [ Asignar permisos de eDiscovery en el Centro de seguridad y cumplimiento](assign-ediscovery-permissions.md).

- Debe usar el PowerShell del Centro de seguridad y cumplimiento para eliminar mensajes. Vea el [paso 2](#step-2-connect-to-security--compliance-center-powershell) para obtener instrucciones sobre cómo conectarse.

- Se puede eliminar un máximo de 10 elementos por buzón a la vez. Como la función de buscar y quitar mensajes está diseñada para ser una herramienta de respuesta a incidentes, este límite ayuda a garantizar que los mensajes se quitan rápidamente de los buzones. Esta característica no está diseñada para limpiar buzones de usuarios.

- El número máximo de buzones en una búsqueda de contenido en los que puede eliminar elementos mediante una acción de búsqueda y depuración es 50 000. Si la búsqueda de contenido (que ha creado en el [paso 1](#step-1-create-a-content-search-to-find-the-message-to-delete)) tiene más de 50 000 buzones de origen, la acción de depuración (que ha creado en el paso 3) no se realizará correctamente. En la sección [Más información](#more-information) se muestra una sugerencia para realizar una operación de búsqueda y depuración en más de 50 000 buzones.

- El procedimiento descrito en este artículo solo se puede usar para eliminar elementos de buzones y carpetas públicas de Exchange Online. No se puede usar para eliminar el contenido de los sitios de SharePoint o OneDrive para la Empresa.

- Los elementos de correo electrónico en un conjunto de revisiones en un caso de eDiscovery avanzado no se pueden eliminar utilizando los procedimientos de este artículo. Esto se debe a que los elementos de un conjunto de revisiones se almacenan en una ubicación de almacenamiento de Azure y no en el servicio activo. Esto significa que no se devolverán por la búsqueda de contenido que creó en el paso 1. Para eliminar elementos en un conjunto de revisiones, tiene que eliminar el caso de eDiscovery avanzado que contiene el conjunto de revisiones. Para más información, consulte [Cerrar o eliminar un caso de eDiscovery avanzado](close-or-delete-case.md).

## <a name="step-1-create-a-content-search-to-find-the-message-to-delete"></a>Paso 1: Crear una búsqueda de contenido para buscar el mensaje que quiera eliminar

El primer paso es crear y ejecutar una búsqueda de contenido para buscar el mensaje que quiera quitar de los buzones de la organización. Para crear la búsqueda, puede usar el Centro de seguridad y cumplimiento o ejecutar los cmdlets **New-ComplianceSearch** y **Start-ComplianceSearch**. Los mensajes que coincidan con la consulta de esta búsqueda se eliminarán al ejecutar el comando **New-ComplianceSearchAction-Purge** en el [paso 3](#step-3-delete-the-message). Para obtener información sobre cómo crear una búsqueda de contenido y configurar consultas de búsqueda, vea los temas siguientes:

- [Búsqueda de contenido de Office 365](content-search.md)

- [Consultas de palabras clave para búsqueda de contenido](keyword-queries-and-search-conditions.md)

- [New-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/New-ComplianceSearch)

- [Start-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/Start-ComplianceSearch)

> [!NOTE]
> Las ubicaciones de contenido que se buscan en la búsqueda de contenido que ha creado en este paso no pueden incluir sitios de SharePoint o OneDrive para la Empresa. Puede incluir solo los buzones y las carpetas públicas en una búsqueda de contenido que se usará para enviar mensajes de correo electrónico. Si la búsqueda de contenido incluye sitios, recibirá un error en el paso 3, al ejecutar el cmdlet **New- ComplianceSearchAction**.

### <a name="tips-for-finding-messages-to-remove"></a>Sugerencias para buscar mensajes que quiere eliminar

El objetivo de la consulta de búsqueda es limitar los resultados de la búsqueda para encontrar el mensaje (o mensajes) que quiere quitar. Aquí encontrará algunas sugerencias:

- Si conoce el texto o la frase exacta usados en la línea de asunto del mensaje, use la propiedad **Subject** en la consulta de búsqueda.

- Si conoce la fecha exacta (o el intervalo de fechas) del mensaje, incluya la propiedad **Received** en la consulta de búsqueda.

- Si conoce quién envió el mensaje, incluya la propiedad **From** en la consulta de búsqueda.

- Obtenga una vista previa de los resultados de la búsqueda para comprobar que la búsqueda solo devolvió el mensaje (o los mensajes) que quiere eliminar.

- Use las estadísticas de estimación de búsqueda (que se muestran en el panel de detalles de la búsqueda en el Centro de seguridad y cumplimiento o mediante el cmdlet [Get-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517934)) para obtener un recuento del número total de resultados.

Estos son dos ejemplos de consultas para buscar mensajes de correo electrónico sospechosos.

- Esta consulta devuelve los mensajes recibidos por los usuarios entre el 13 de abril de 2016 y el 14 de abril de 2016 que contengan las palabras "acción" y "necesario" en la línea de asunto.

  ```powershell
  (Received:4/13/2016..4/14/2016) AND (Subject:'Action required')
  ```

- Esta consulta devuelve los mensajes enviados por chatsuwloginsset12345@outlook.com que contienen la frase exacta "Actualice la información de la cuenta" en la línea de asunto.

  ```powershell
  (From:chatsuwloginsset12345@outlook.com) AND (Subject:"Update your account information")
  ```

Este es un ejemplo del uso de una consulta para crear e iniciar una búsqueda mediante la ejecución de los cmdlets **New-ComplianceSearch** y **Start-ComplianceSearch** para buscar en todos los buzones de la organización:

```powershell
$Search=New-ComplianceSearch -Name "Remove Phishing Message" -ExchangeLocation All -ContentMatchQuery '(Received:4/13/2016..4/14/2016) AND (Subject:"Action required")'
Start-ComplianceSearch -Identity $Search.Identity
```

## <a name="step-2-connect-to-security--compliance-center-powershell"></a>Paso 2: Conectarse al PowerShell del Centro de seguridad y cumplimiento

El siguiente paso es conectarse al PowerShell del Centro de seguridad y cumplimiento de su organización. Para obtener instrucciones paso a paso, vea [Conectarse al PowerShell del Centro de seguridad y cumplimiento](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).

Cuando se haya conectado al PowerShell del Centro de seguridad y cumplimiento, ejecute los cmdlets **New-ComplianceSearch** y **Start-ComplianceSearch** que preparó en el paso anterior.

## <a name="step-3-delete-the-message"></a>Paso 3: Eliminar el mensaje

Después de crear y restringir una búsqueda de contenido para devolver el mensaje que quiere eliminar y después de conectarse al PowerShell del Centro de seguridad y cumplimiento, el último paso es ejecutar el cmdlet **New-ComplianceSearchAction** para eliminar el mensaje. Puede eliminar el mensaje de forma temporal o permanente. Un mensaje eliminado temporalmente se mueve a la carpeta Elementos recuperables de un usuario y se conserva hasta que expire el período de retención de elementos eliminados. Los mensajes eliminados permanentemente se marcan para la eliminación definitiva del buzón y se eliminarán la próxima vez que el Asistente para carpetas administradas procese el buzón. Si se habilita la recuperación de un único elemento en el buzón, los elementos eliminados permanentemente se eliminarán definitivamente cuando expire el período de retención de elementos eliminados. Si un buzón está en retención, los mensajes eliminados se conservan hasta que expire la duración del período de retención de un elemento o hasta que se quite la retención del buzón.

En el ejemplo siguiente, el comando elimina software de los resultados de la búsqueda devueltos por una búsqueda de contenido denominada "quitar mensaje de suplantación de identidad".

```powershell
New-ComplianceSearchAction -SearchName "Remove Phishing Message" -Purge -PurgeType SoftDelete
```

Para eliminar de forma permanente los elementos devueltos por la búsqueda de contenido "quitar el mensaje de suplantación de identidad", ejecutaría este comando:

```powershell
New-ComplianceSearchAction -SearchName "Remove Phishing Message" -Purge -PurgeType HardDelete
```

Cuando ejecuta el comando anterior en mensajes de eliminación parcial o Soft, la búsqueda especificada por el parámetro *SearchName* es la búsqueda de contenido que creó en el paso 1.

Para obtener más información, vea [ New-ComplianceSearchAction](https://docs.microsoft.com/powershell/module/exchange/New-ComplianceSearchAction).

## <a name="more-information"></a>Más información

- **¿Cómo se obtiene el estado de la operación de búsqueda y eliminación? **

  Ejecute **Get-ComplianceSearchAction** para obtener el estado de la operación de eliminación.  El objeto que se crea al ejecutar el cmdlet **New-ComplianceSearchAction** se denomina con este formato: `<name of Content Search>_Purge`.

- **¿Qué ocurre después de eliminar un mensaje?**

  Un mensaje que se elimina con el comando `New-ComplianceSearchAction -Purge -PurgeType HardDelete` se mueve a la carpeta de depuración y el usuario no puede obtener acceso a él. Después de mover el mensaje a la carpeta de depuración, el mensaje se conserva durante el período de retención de elementos eliminados si está habilitada la recuperación de un único elemento en el buzón. (En Microsoft 365, la recuperación de elemento único se habilita de manera predeterminada cuando se crea un nuevo buzón). Cuando expire el período de retención de elementos eliminados, se marca el mensaje para eliminarlo de forma permanente y se depura de Microsoft 365 la próxima vez que el Asistente para carpetas administradas procese el buzón.

  Si usa el comando `New-ComplianceSearchAction -Purge -PurgeType SoftDelete`, los mensajes se mueven a la carpeta de eliminaciones de la carpeta Elementos recuperables del usuario. No se depura inmediatamente de Microsoft 365. El usuario dispone de un plazo para recuperar los mensajes de la carpeta Elementos eliminados, que se basa en el período de retención de elementos eliminados configurado para el buzón. Una vez finalizado este período de retención (o si el usuario purga el mensaje antes de que expire), el mensaje se mueve a la carpeta Purgas y el usuario ya no puede acceder a él. Cuando el mensaje se encuentra en la carpeta de depuración, se conserva durante un período basado en el período de retención de elementos eliminados configurado para el buzón, si se habilitó la recuperación de elemento único en el buzón. (En Microsoft 365, la recuperación de elemento único se habilita de manera predeterminada cuando se crea un nuevo buzón). Cuando expire el período de retención de elementos eliminados, se marca el mensaje para eliminarlo de forma permanente y se depura de Microsoft 365 la siguiente vez que el Asistente para carpetas administradas procese el buzón.

- **¿Qué ocurre si tiene que eliminar un mensaje de más de 50 000 buzones?**

  Como se ha mencionado anteriormente, puede realizar una operación de búsqueda y depuración en un máximo de 50 000 buzones. Si tiene que realizar una operación de búsqueda y depuración en más de 50 000 buzones de correo, considere la posibilidad de crear filtros de permisos de búsqueda temporales que reduzcan el número de buzones en los que se buscaría a menos de 50 000 buzones. Por ejemplo, si su organización contiene buzones de diferente departamentos, comunidades autónomas o países, puede crear un filtro de permisos de búsqueda de buzón en función de una de esas propiedades de buzón para buscar en un subconjunto de buzones de su organización. Después de crear el filtro de permisos de búsqueda, debe crear la búsqueda (como se describe en el paso 1) y, después, eliminar el mensaje (como se describe en el paso 3). Luego, puede editar el filtro para buscar y depurar mensajes en un conjunto de buzones diferente. Para obtener más información sobre cómo crear filtros de permisos de búsqueda, vea [Configurar el filtrado de permisos para la búsqueda de contenido](permissions-filtering-for-content-search.md).

- **¿Se eliminarán los elementos sin indexar incluidos en los resultados de la búsqueda?**

  No, el comando New-ComplianceSearchAction-Purge no elimina elementos sin indexar.

- **¿Qué ocurre si se elimina un mensaje de un buzón colocado en conservación local o en retención por litigio o que está asignado a una directiva de retención de Microsoft 365?**

  Una vez que el mensaje se depure y se mueva a la carpeta de depuración, este se conserva hasta que expire la duración de la retención. Si la duración de la retención es ilimitada, los elementos se conservan hasta que se elimine la retención o se modifique su duración.

- **¿Por qué el proceso de búsqueda y eliminación se divide entre distintos grupos de roles del Centro de seguridad y cumplimiento?**

  Como ya se explicó antes, para poder buscar en buzones es necesario pertenecer al grupo de roles de administrador de exhibición de documentos electrónicos o tener asignado el rol de administración de búsqueda de cumplimiento. Para eliminar mensajes, es necesario pertenecer al grupo de roles de administración de la organización o tener asignado el rol de administración de búsqueda y depuración. Esto permite controlar quién pueden buscar en los buzones de la organización y quién puede eliminar mensajes.
