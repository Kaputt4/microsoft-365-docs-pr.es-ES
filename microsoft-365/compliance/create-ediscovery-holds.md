---
title: Crear suspensiones de eDiscovery en un caso de eDiscovery principal
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Puede crear una retención asociada a un caso de exhibición de documentos electrónicos principal para conservar el contenido que pueda ser relevante para una investigación.
ms.openlocfilehash: 6405dac51c34163f8eadb359d9c29f1aa81a1b82
ms.sourcegitcommit: bd51f626f0c7788c2a3cf89deee25264659aebd5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/17/2020
ms.locfileid: "43551492"
---
# <a name="create-an-ediscovery-hold"></a>Crear un caso de retención de eDiscovery

Puede usar un caso de exhibición de documentos electrónicos principal para crear suspensiones y conservar el contenido que pueda ser relevante para el caso. Puede poner una retención en los buzones de Exchange y en las cuentas de OneDrive para la empresa de las personas que está investigando en el caso. También puede suspender los buzones de correo y los sitios asociados a Microsoft Teams, grupos de Office 365 y grupos de Yammer. Cuando se colocan ubicaciones de contenido en retención, el contenido se conserva hasta que se quita la retención de la ubicación del contenido o hasta que se elimina la suspensión.

Después de crear una suspensión de exhibición de documentos electrónicos, la retención puede tardar hasta 24 horas en surtir efecto. 

Al crear una suspensión, tiene las siguientes opciones para limitar el contenido que se conserva en las ubicaciones de contenido especificadas:
  
- Se crea una retención infinita en la que todo el contenido se coloca en retención. Como alternativa, puede crear una retención basada en consultas en la que solo se coloca en retención el contenido que coincide con una consulta de búsqueda.

- Puede especificar un intervalo de fechas para conservar solo el contenido enviado, recibido o creado dentro del intervalo de fechas. Como alternativa, puede retener todo el contenido independientemente de Cuándo se haya enviado, recibido o creado.

> [!NOTE]
> Puede tener un máximo de 10.000 suspensiones de eDiscovery en todos los casos de eDiscovery principales de la organización.
  
## <a name="how-to-create-an-ediscovery-hold"></a>Cómo crear una retención de exhibición de documentos electrónicos

Para crear una retención de exhibición de documentos electrónicos asociada a un caso de exhibición de documentos electrónicos principal:
  
1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com) e inicie sesión con las credenciales de la cuenta de usuario a la que se le han asignado los permisos de eDiscovery adecuados.

2. En el panel de navegación izquierdo del centro de cumplimiento de Microsoft 365, haga clic en **Mostrar todos**y, a continuación, en **eDiscovery > Core**.

3. En la página **principal de eDiscovery** , seleccione el caso en el que desea crear la retención y, a continuación, haga clic en **abrir caso**.

4. En la página **principal** del caso, haga clic en la pestaña **suspensiones** .
  
5. En la página **suspensiones** , haga clic en **crear**.

6. En la página **nombre del** Asistente para la suspensión, asigne un nombre a la retención y agregue una descripción opcional y, a continuación, haga clic en **siguiente**. El nombre de la suspensión debe ser exclusivo en la organización.

7. En la página **ubicaciones de contenido** , elija las ubicaciones de contenido que desea poner en retención. Puede poner buzones de correo, sitios y carpetas públicas en retención.

    ![Elegir las ubicaciones de contenido para colocar en suspensión](../media/a59e4265-9151-4dbf-913f-6a4ab8db06b4.png)
  
   a. **Ubicaciones de buzones** : haga clic en **elegir usuarios, grupos o equipos** y, a continuación, haga clic en **elegir usuarios, grupos o Teams** de nuevo para especificar los buzones que se deben poner en retención. Use el cuadro de búsqueda para buscar los buzones de usuario y los grupos de distribución (para poner una retención en los buzones de los miembros del grupo) para ponerlos en retención. También puede poner una retención en el buzón asociado para un grupo de Microsoft Teams, Office 365 o un grupo de Yammer. Active la casilla de verificación usuario, grupo, equipo, haga clic en **elegir**y, a continuación, haga clic en **listo**.

   b. **Ubicaciones del sitio** : haga clic en **elegir sitios** y, a continuación, haga clic en **elegir sitios** de nuevo para especificar que las cuentas de SharePoint y OneDrive se colocan en suspensión. Escriba la dirección URL de cada sitio que quiere suspender. También puede Agregar la dirección URL del sitio de SharePoint para un grupo de Microsoft Teams, Office 365 o un grupo de Yammer. Haga clic en **elegir**y, a continuación, en **listo**.
  
   c. **Carpetas públicas de Exchange.** Mueva el control](../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) de alternancia ![de alternancia a la posición **All** para poner todas las carpetas públicas en la organización de Exchange online en retención. No puede elegir carpetas públicas específicas que poner en retención. Deje el modificador de alternancia establecido en **ninguno** si no desea mantener una retención en las carpetas públicas.

8. Cuando haya acabado de agregar ubicaciones de contenido a la suspensión, haga clic en **siguiente**.

9. Para crear una retención basada en consultas con condiciones, realice lo siguiente. De lo contrario, para conservar todo el contenido de las ubicaciones de contenido especificadas, haga clic en **siguiente** .

    ![Crear una suspensión basada en consulta con condiciones](../media/d587b58e-d05c-4ac0-b0fe-09019e4f1063.png)
  
    a. En el cuadro bajo **palabras clave**, escriba una consulta de búsqueda para que solo se conserve el contenido que cumple los criterios de búsqueda. Puede especificar palabras clave, propiedades del mensaje de correo electrónico o propiedades del documento, como nombres de archivo. También puede usar consultas más complejas que usen un operador booleano, como **and**, **or**o **Not**.

    b. Haga clic en **Agregar condiciones** para agregar una o más condiciones para restringir la consulta de búsqueda para la retención. Cada condición agrega una cláusula a la consulta de búsqueda de KQL que se crea y se ejecuta cuando se crea la suspensión. Por ejemplo, puede especificar un intervalo de fechas para que los documentos de correo electrónico o de sitio creados en el intervalo de fechas se coloquen en suspensión. Una condición está conectada lógicamente a la consulta de palabras clave (que se especifica en el cuadro **palabras clave** ) por el operador **and** . Esto significa que los elementos deben cumplir con la consulta de palabras clave y la condición que se va a conservar.

    Para obtener más información acerca de la creación de una consulta de búsqueda y el uso de condiciones, consulte [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).

10. Después de configurar una retención basada en consultas, haga clic en **siguiente**.

11. Revise la configuración (y edítela si es necesario) y, a continuación, haga clic en **crear esta suspensión**.

## <a name="ediscovery-hold-statistics"></a>estadísticas de retención de eDiscovery

Después de crear una retención de exhibición de documentos electrónicos, la información sobre la nueva retención se muestra en la página de control flotante para la suspensión seleccionada. Esta información incluye el número de buzones de correo y sitios en espera y estadísticas sobre el contenido que se ha puesto en suspensión, como el número total y el tamaño de los elementos que se encuentran en suspensión y la última vez que se calcularon las estadísticas de retención. Estas estadísticas de retención ayudan a identificar la cantidad de contenido relacionado con el caso que se conserva.
  
![Almacenar estadísticas](../media/575cfe0a-9210-4ae4-8df8-65665d66712e.png)
  
Tenga en cuenta lo siguiente en cuanto a las estadísticas de retención de eDiscovery:
  
- El número total de elementos en espera indica el número de elementos de todos los orígenes de contenido que se encuentran en retención. Si ha creado una suspensión basada en consulta, esta estadística indica el número de elementos que coinciden con la consulta.

- El número de elementos en espera también incluye los elementos sin indexar encontrados en las ubicaciones de contenido. Si crea una suspensión basada en consulta, todos los elementos sin indexar en las ubicaciones de contenido se colocan en retención. Esto incluye los elementos sin indexar que no coinciden con los criterios de búsqueda de una retención basada en consultas y los elementos sin indexar que podrían estar fuera de una condición de intervalo de fechas. Esto es diferente a lo que sucede cuando se ejecuta una búsqueda, en la que los elementos no indexados que no coinciden con la consulta de búsqueda o se excluyen por una condición de intervalo de fechas no se incluyen en los resultados de la búsqueda. Para obtener más información acerca de los elementos sin indexar, vea [elementos parcialmente indizados](partially-indexed-items-in-content-search.md).

- Puede obtener las estadísticas de retención más recientes haciendo clic en **actualizar estadísticas** para volver a ejecutar una estimación de búsqueda que calcula el número actual de elementos en espera.

- Es normal que el número de elementos en espera aumente con el tiempo, ya que los usuarios cuyo buzón o sitio está en espera suelen enviar o recibir un nuevo mensaje de correo electrónico y crear nuevos documentos en SharePoint y OneDrive.

- Si un buzón de Exchange, un sitio de SharePoint o una cuenta de OneDrive se mueven a otra región en un entorno multigeográfico, las estadísticas de ese sitio no se incluirán en las estadísticas de retención. Pero el contenido de esas ubicaciones todavía se conservará. Además, si un buzón de correo o un sitio se mueven a otra región, la dirección o dirección SMTP que se muestra en la retención no se actualizará automáticamente. Tendrá que editar la retención y actualizar la dirección URL o la dirección SMTP para que las ubicaciones de contenido vuelvan a incluirse en las estadísticas de retención.

## <a name="search-locations-on-ediscovery-hold"></a>Ubicaciones de búsqueda en la retención de exhibición de documentos electrónicos

Cuando [busca contenido](search-for-content-in-core-ediscovery.md) en un caso principal de eDiscovery, puede configurar rápidamente la búsqueda para que solo busque en las ubicaciones de contenido que se han colocado en una suspensión asociada con el caso.

![Ubicaciones, ubicaciones en suspensión](../media/d56398aa-0b20-4500-8e26-494eab92a99f.png)

Seleccione la opción **ubicaciones en espera** para buscar en todas las ubicaciones de contenido que se encuentran en espera. Si el caso contiene varias suspensiones de exhibición de documentos electrónicos, las ubicaciones de contenido de todas las suspensiones se buscarán cuando seleccione esta opción. Además, si se colocó una ubicación de contenido en una suspensión basada en consulta, solo se buscará en los elementos que coinciden con la consulta de retención al ejecutar la búsqueda. Es decir, solo se devuelve el contenido que coincide con los criterios de retención y los criterios de búsqueda con los resultados de la búsqueda. Por ejemplo, si un usuario se colocó en la suspensión de casos basada en consultas y conserva los elementos que se enviaron o se crearon antes de una fecha específica, sólo se buscará en esos elementos. Esto se logra conectando la consulta de suspensión de casos y la consulta de búsqueda por un operador **and** .

Estas son algunas otras cosas que debe tener en cuenta al buscar ubicaciones en la exhibición de documentos electrónicos:

- Si una ubicación de contenido forma parte de varias suspensiones en el mismo caso, las consultas de retención se combinan mediante operadores **or** al buscar en esa ubicación de contenido mediante la opción de contenido todo el caso. De forma similar, si una ubicación de contenido forma parte de dos suspensiones diferentes, donde una se basa en la consulta y la otra es una retención infinita (donde todo el contenido se coloca en retención), todo el contenido se busca a causa de la suspensión infinita.

- Si se configura una búsqueda para buscar ubicaciones en suspensión y, a continuación, cambiar una retención de eDiscovery en el caso (agregando o quitando una ubicación o cambiando una consulta de retención), la configuración de búsqueda se actualizará con esos cambios. Sin embargo, tiene que volver a ejecutar la búsqueda una vez cambiada la retención para actualizar los resultados de la búsqueda.

- Si se colocan varias suspensiones de exhibición de documentos electrónicos en una sola ubicación en un caso de exhibición de documentos electrónicos y selecciona buscar ubicaciones en retención, el número máximo de palabras clave para esa consulta de búsqueda es de 500. Esto se debe a que la búsqueda combina todas las retenciones basadas en consultas mediante el operador **or** . Si hay más de 500 palabras clave en las consultas de retención combinada y la consulta de búsqueda, se buscará todo el contenido del buzón, no solo el contenido que coincida con el caso basado en consultas. 
    
- Si una retención de exhibición de documentos electrónicos tiene un estado de **activación**, puede seguir buscando en las ubicaciones en espera mientras se activa la suspensión.

## <a name="preserve-content-in-microsoft-teams"></a>Conservar contenido en Microsoft Teams

Las conversaciones que forman parte de un canal de Microsoft Teams se almacenan en el buzón de correo asociado con el equipo de Microsoft. Asimismo, los archivos que los miembros del equipo comparten en un canal se almacenan en el sitio de SharePoint del equipo. Por lo tanto, tiene que poner el buzón de equipo y el sitio de SharePoint en la exhibición de documentos electrónicos para conservar conversaciones y archivos en un canal.

Como alternativa, las conversaciones que forman parte de la lista de chats en Microsoft Teams (llamados *1:1 chats* o *1: N Group chats*) se almacenan en los buzones de los usuarios que participan en el chat. Y los archivos que los usuarios comparten en las conversaciones de chat se almacenan en la cuenta de OneDrive del usuario que comparte el archivo. Por lo tanto, tiene que agregar los buzones de usuario individuales y las cuentas de OneDrive a una conservación de exhibición de documentos electrónicos para conservar conversaciones y archivos en la lista de chats. Se recomienda retener una retención de los buzones de los miembros de un equipo de Microsoft, además de colocar el buzón de equipo y el sitio en suspensión.

A partir de febrero 2020, hemos activado la capacidad para preservar contenido en canales privados. Como los chats de canal privado se almacenan en los buzones de los participantes del chat, al colocar un buzón de usuario en la exhibición de documentos electrónicos se conservarán los chats de canal privado. Además, si se colocó un buzón de usuario en una retención de exhibición de documentos electrónicos antes del 2020 de febrero, la retención se aplicará ahora automáticamente a los mensajes de canal privado almacenados en ese buzón. También se admite la preservación de archivos compartidos en canales privados.

Para obtener más información acerca de la conservación de contenido de Teams, vea [poner a un usuario o un equipo de Microsoft Teams en retención legal](https://docs.microsoft.com/MicrosoftTeams/legal-hold).
    
> [!IMPORTANT]
> En una organización basada en la nube, los usuarios que participen en conversaciones que formen parte de la lista de chats en Microsoft Teams deben tener un buzón de correo de Exchange Online para conservar las conversaciones de chat cuando el buzón de correo se coloca en una suspensión de eDiscovery. Esto se debe a que las conversaciones que forman parte de la lista de chats se almacenan en buzones de correo basados en la nube de los participantes del chat. Si un participante de chat no tiene un buzón de correo de Exchange Online, no podrá conservar esas conversaciones de chat. Por ejemplo, en una implementación híbrida de Exchange, los usuarios con un buzón local podrían ser capaces de participar en conversaciones que formen parte de la lista de chats de Microsoft Teams. Pero, en este caso, el contenido de esta conversación no se puede conservar porque estos usuarios no tienen buzones de correo basados en la nube que puedan retenerse.
  
Cada canal de equipo o equipo también contiene un wiki para la toma de notas y la colaboración. El contenido de esta se guarda automáticamente en un archivo con un formato .mht. Este archivo se almacena en la biblioteca de documentos de Datos Wiki de Teams en el sitio de SharePoint del equipo. Puede conservar el contenido de la wiki agregando el sitio de SharePoint del equipo a una suspensión de exhibición de documentos electrónicos.
    
> [!NOTE]
> La capacidad de conservar el contenido del wiki para un canal de equipo o equipo (cuando se pone el sitio de SharePoint del equipo en espera) se presentó el 22 de junio de 2017. Si un sitio de grupo está en suspensión, el contenido de la wiki se conservará a partir de esa fecha. Sin embargo, si un sitio de grupo está en suspensión y el contenido de la wiki se eliminó antes del 22 de junio de 2017, no se conservó el contenido de la wiki.

### <a name="office-365-groups"></a>Grupos de Office 365

Teams se basa en grupos de Office 365. Por lo tanto, la colocación de grupos de Office 365 en la exhibición de documentos electrónicos es similar al contenido de los equipos en espera.

Tenga en cuenta lo siguiente cuando coloque tanto Teams como grupos de Office 365 en una suspensión de eDiscovery:

- Como se ha explicado anteriormente, para colocar el contenido ubicado en Teams and Office 365 Groups Hold, tiene que especificar el buzón de correo y el sitio de SharePoint que están asociados con un grupo o un equipo.

- Ejecute el cmdlet **Get-UnifiedGroup** en [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) para ver las propiedades de los grupos teams y Office 365. Esta es una buena forma de obtener la dirección URL del sitio que está asociado a un grupo de Office y Office 365. Por ejemplo, el comando siguiente muestra las propiedades seleccionadas de un grupo de Office365 denominado Senior Leadership Team:

    ```text
    Get-UnifiedGroup "Senior Leadership Team" | FL DisplayName,Alias,PrimarySmtpAddress,SharePointSiteUrl

    DisplayName            : Senior Leadership Team
    Alias                  : seniorleadershipteam
    PrimarySmtpAddress     : seniorleadershipteam@contoso.onmicrosoft.com
    SharePointSiteUrl      : https://contoso.sharepoint.com/sites/seniorleadershipteam
    ```

    > [!NOTE]
    > Para ejecutar el cmdlet **Get-UnifiedGroup** debe tener asignado el rol de destinatarios con permiso de vista en Exchange Online o ser un miembro de un grupo de roles que tenga asignado el rol de destinatarios con permiso de vista. 
  
- Cuando se realiza una búsqueda en el buzón de un usuario, no se buscará en ningún equipo o grupo de Office 365 del que el usuario sea miembro. De forma similar, cuando se coloca un grupo de Office 365 en un equipo en una suspensión de eDiscovery, solo el buzón de grupo y el sitio de grupo se colocan en retención. Los buzones y los sitios de OneDrive para la empresa de los miembros del grupo no se colocan en suspensión a menos que los agregue explícitamente a la retención de exhibición de documentos electrónicos. Por lo tanto, si tiene que poner un equipo o un grupo de Office 365 en espera por un motivo legal, considere la posibilidad de agregar los buzones y las cuentas de OneDrive de los miembros del equipo o del grupo en la misma retención.

- Para obtener una lista de los miembros de un grupo de Office 365 o de equipo, puede ver las propiedades de la página **grupos** en el centro de administración de Microsoft 365. Además, puede ejecutar el comando siguiente en PowerShell de Exchange Online: 
    
    ```powershell
    Get-UnifiedGroupLinks <group or team name> -LinkType Members | FL DisplayName,PrimarySmtpAddress
    ```

    > [!NOTE]
    > Para ejecutar el cmdlet **Get-UnifiedGroupLinks** debe tener asignado el rol de destinatarios con permiso de vista en Exchange Online o ser un miembro de un grupo de roles que tenga asignado el rol de destinatarios con permiso de vista.

## <a name="onedrive-accounts"></a>Cuentas de OneDrive

Para recopilar una lista de las direcciones URL de los sitios de OneDrive para la empresa de su organización para que pueda agregarlas a una suspensión o una búsqueda asociada a un caso de exhibición de documentos electrónicos, vea [crear una lista de todas las ubicaciones de OneDrive en la organización](https://docs.microsoft.com/onedrive/list-onedrive-urls). El script de este artículo crea un archivo de texto que contiene una lista de todos los sitios de OneDrive de la organización. Para ejecutar este script, tiene que instalar y usar el Shell de SharePoint Online Management. Asegúrese de anexar la dirección URL para el dominio MiSitio de su organización a cada sitio de OneDrive que quiera buscar. Este es el dominio que contiene todos los sitios OneDrive; por ejemplo, `https://contoso-my.sharepoint.com`. Este es un ejemplo de una dirección URL para un sitio de usuario de OneDrive: `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft.com`.

> [!IMPORTANT]
> La dirección URL de la cuenta de OneDrive de un usuario incluye su nombre principal de usuario (UPN) `https://alpinehouse-my.sharepoint.com/personal/sarad_alpinehouse_onmicrosoft_com`(por ejemplo,). En el caso poco probable de que se cambie el UPN de una persona, su dirección URL de OneDrive también cambiará para incorporar el nuevo UPN. Si la cuenta de OneDrive de un usuario forma parte de una suspensión de exhibición de documentos electrónicos, la antigua y su UPN se cambian, debe actualizar la retención y tendrá que actualizar la retención y agregar la nueva dirección URL de OneDrive del usuario y quitar la antigua. Para más información, consulte [Cómo afectan los cambios de UPN a la dirección URL de OneDrive](https://docs.microsoft.com/onedrive/upn-changes).

## <a name="ediscovery-hold-limits"></a>límites de retención de eDiscovery

En la siguiente tabla se enumeran los límites de casos de eDiscovery y suspensiones de casos.
    
  |**Descripción del límite**|**Límite**|
  |:-----|:-----|
  |Número máximo de casos para una organización  <br/> |Sin límite  <br/> |
  |Número máximo de suspensiones de eDiscovery para una organización  <br/> |10 000  <br/> |
  |Número máximo de buzones en una sola retención de exhibición de documentos electrónicos  <br/> |1.000  <br/> |
  |Número máximo de sitios de SharePoint y OneDrive para la empresa en una sola retención de exhibición de documentos electrónicos  <br/> |100  <br/> |
  |Número máximo de escenarios mostrados en la Página principal de eDiscovery y el número máximo de elementos que se muestran en las pestañas suspensiones, búsquedas y exportación en un caso. <sup>1</sup> |1.000|
  |||

   > [!NOTE]
   > <sup>1</sup> para ver una lista de más de 1.000 casos, suspensiones, búsquedas o exportaciones, puede usar el cmdlet de PowerShell de cumplimiento de & de seguridad de Office 365:<br/> [Get-ComplianceCase](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-compliancecase) <br/> [Get-CaseHoldPolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-caseholdpolicy)<br/> [Get-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearch)<br/> [Get-ComplianceSearchAction](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearchaction)