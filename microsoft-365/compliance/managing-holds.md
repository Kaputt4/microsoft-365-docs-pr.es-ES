---
title: Administrar retenciones en eDiscovery (Premium)
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Obtenga información sobre cómo colocar retenciones en los custodios y sus orígenes de datos para conservar el contenido pertinente para su caso de exhibición de documentos electrónicos (Premium).
ms.custom:
- seo-marvel-mar2020
- admindeeplinkMAC
ms.openlocfilehash: 16a4932993a652d8d7d71be78fd23a238fc90759
ms.sourcegitcommit: 52eea2b65c0598ba4a1b930c58b42dbe62cdaadc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/19/2022
ms.locfileid: "64939661"
---
# <a name="manage-holds-in-ediscovery-premium"></a>Administrar retenciones en eDiscovery (Premium)

Puede usar un caso de exhibición de documentos electrónicos de Microsoft Purview (Premium) para crear retenciones para conservar el contenido que podría ser relevante para su caso. Con las funcionalidades de suspensión de eDiscovery (Premium), puede colocar retenciones en los custodios y sus orígenes de datos. Además, puede colocar una suspensión sin custodia en buzones y sitios de OneDrive para la Empresa. También puede colocar una suspensión en el buzón de grupo, SharePoint sitio y OneDrive para la Empresa sitio para un grupo de Microsoft 365. Del mismo modo, puede colocar una suspensión en el buzón de correo y el sitio asociados a Microsoft Teams. Cuando coloca las ubicaciones de contenido en espera, el contenido se mantiene hasta que libera al custodio, quita una ubicación de datos específica o elimina por completo la directiva de retención.

## <a name="manage-custodian-based-holds"></a>Administración de retenciones basadas en custodios

En algunos casos, es posible que tenga un conjunto de custodios que haya identificado y haya decidido conservar sus datos durante el caso. En eDiscovery (Premium), cuando estos custodios están en espera, el usuario y sus orígenes de datos seleccionados se agregan automáticamente a una directiva de suspensión del custodio.

Para ver la directiva de suspensión del custodio:

1. En el portal de cumplimiento de Microsoft Purview, haga clic en **eDiscovery > Avanzadas** para mostrar la lista de casos de su organización.

2. Vaya a la pestaña **Orígenes** para agregar custodios dentro de su caso. Para obtener información sobre cómo puede agregar y colocar custodios en espera dentro de un caso de exhibición de documentos electrónicos (Premium), vea [Agregar custodios a un caso](add-custodians-to-case.md). Si ya ha agregado custodios y los ha colocado en espera, vaya al paso 3.

3. Vaya a la pestaña **Retenciones** y haga clic en **CustodianHold\<HoldId>**.

4. En la página de control flotante, puede ver las estadísticas de suspensión de la directiva. También puede realizar acciones como aplicar una consulta a la suspensión basada en el custodio. Para obtener más información sobre cómo crear una consulta de suspensión y usar condiciones, vea [Consultas de palabras clave y condiciones de búsqueda para búsqueda de contenido](keyword-queries-and-search-conditions.md).

## <a name="manage-non-custodial-holds"></a>Administración de retenciones sin custodia

Al crear una suspensión, tiene las siguientes opciones para limitar el contenido que se mantiene en las ubicaciones de contenido especificadas:

- Se crea una suspensión infinita donde todo el contenido se coloca en suspensión. Como alternativa, puede crear una suspensión basada en consultas en la que solo se coloque en suspensión el contenido que coincida con una consulta de búsqueda.
  
- Puede especificar un intervalo de fechas para contener solo el contenido que se envió, recibió o creó dentro de ese intervalo de fechas. Como alternativa, puede contener todo el contenido independientemente de cuándo se envió, recibió o creó.

Para crear una suspensión sin custodia para un caso de exhibición de documentos electrónicos (Premium):

1. En el <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">portal de cumplimiento</a>, haga clic en **eDiscovery > Avanzadas** para mostrar la lista de casos de su organización.
  
2. Haga clic en **Abrir** junto al caso en el que desea crear las retenciones.
  
3. En la página principal del caso, haga clic en la pestaña **Retenciones** .
  
4. En la pestaña **Suspensiones** , haga clic en **Crear**.
  
5. En la página **Nombre de la suspensión** , asigne un nombre a la suspensión. El nombre de la suspensión debe ser exclusivo en la organización.

6. (Opcional) En el cuadro **Descripción** , agregue una descripción de la suspensión.
  
7. Haga clic en **Siguiente**.
  
8. Elija las ubicaciones de contenido que desea colocar en espera. Puede retener buzones, sitios y carpetas públicas.

   1. **Exchange correo electrónico**: haga clic en **Elegir usuarios, grupos o equipos y,** a continuación, haga clic en **Elegir usuarios, grupos o equipos** de nuevo para especificar los buzones que se van a poner en espera. Use el cuadro de búsqueda para encontrar buzones de usuario y grupos de distribución (para colocar una suspensión en los buzones de miembros de grupo) para suspenderlos. También puede colocar una suspensión en el buzón asociado para un grupo de Microsoft 365 o un equipo de Microsoft. Active la casilla de verificación usuario, grupo, equipo, haga clic en **Elegiry**, a continuación, haga clic en **Listo**.

      > [!NOTE]
      > Al hacer clic en **Elegir usuarios, grupos o equipos** para especificar los buzones que se van a colocar en espera, el selector de buzones que se muestra está vacío. Esto se ha diseñado así para mejorar el rendimiento. Para agregar personas a esta lista, escriba un nombre (un mínimo de 3 caracteres) en el cuadro de búsqueda.

   1. **SharePoint Sitios**: haga clic en **Elegir sitios** y, a continuación, haga clic en **Elegir sitios** de nuevo para especificar SharePoint y OneDrive para la Empresa sitios que se van a colocar en espera. Escriba la dirección URL de cada sitio que quiere colocar en suspensión. También puede agregar la dirección URL del sitio de SharePoint para un grupo de Microsoft 365 o un equipo de Microsoft. Haga clic en **Elegiry**, a continuación, haga clic en **Listo**.

      > [!NOTE]
      > La dirección URL de la cuenta de OneDrive de un usuario incluye su nombre principal de usuario (UPN) (por ejemplo, `https://alpinehouse-my.sharepoint.com/personal/sarad_alpinehouse_onmicrosoft_com`). En el caso poco frecuente de que se cambie el UPN de una persona, su dirección URL de OneDrive también cambiará para incorporar el nuevo UPN. Si la cuenta de OneDrive de un usuario forma parte de una suspensión sin custodia y su UPN cambia, debe actualizar la suspensión y apuntar a la nueva dirección URL de OneDrive. Para más información, consulte [Cómo afectan los cambios de UPN a la dirección URL de OneDrive](/onedrive/upn-changes).

   1. **Exchange carpetas públicas**: mueva el modificador de alternancia a la posición Todos para poner en espera todas las carpetas públicas de la organización de Exchange Online. No puede elegir carpetas públicas específicas para poner en suspensión. Deje el modificador de alternancia establecido en **Ninguno** si no desea poner una suspensión en carpetas públicas.

9. Cuando haya terminado de agregar ubicaciones de contenido a la suspensión, haga clic en **Siguiente**.
  
10. Para crear una suspensión basada en consultas con condiciones, complete lo siguiente. De lo contrario, solo tiene que hacer clic en **Siguiente**.

    - En el cuadro **de Palabras clave**, escriba una consulta de búsqueda en el cuadro para que solo el contenido que cumpla los criterios de búsqueda se coloque en espera. Puede especificar palabras clave, propiedades de mensaje o propiedades de documento, como nombres de archivo. También puede usar consultas más complejas que usan un operador booleano, como AND, OR o NOT. Si deja vacío el cuadro de palabra clave, todo el contenido ubicado en las ubicaciones de contenido especificadas se colocará en espera.

    - Haga clic en  **Agregar** condiciones para agregar una o varias condiciones para restringir la consulta de búsqueda para la suspensión. Cada condición agrega una cláusula a la consulta de búsqueda KQL que se crea y se ejecuta cuando se creala suspensión. Por ejemplo, puede especificar un intervalo de fechas para que los documentos de correo electrónico o de sitio creados dentro del intervalo de fechas estén en espera. Una condición se conecta lógicamente a la consulta de palabra clave (especificada en el cuadro de palabra clave) mediante el operador AND. Esto significa que los elementos deben satisfacer la consulta de palabra clave y la condición que se va a colocar en espera.

     Para obtener más información sobre cómo crear una consulta de búsqueda y usar condiciones, vea [Consultas de palabras clave y condiciones de búsqueda para búsqueda de contenido](/office365/SecurityCompliance/keyword-queries-and-search-conditions).

11. Después de configurar una suspensión basada en consultas, haga clic en **Siguiente**.

12. Revise la configuración y, a continuación, haga clic en **Crear esta suspensión**.

> [!NOTE]
> Al crear una retención basada en consultas, todo el contenido de las ubicaciones seleccionadas se coloca inicialmente en suspensión. Posteriormente, cualquier contenido que no coincida con la consulta especificada se borra de la suspensión cada siete a 14 días. Sin embargo, una retención basada en consultas no borrará el contenido si se aplican más de cinco retenciones de cualquier tipo a una ubicación de contenido o si algún elemento tiene problemas de indexación.

> [!NOTE]
> Si la dirección SMTP del usuario cambia después de colocar el buzón del usuario en espera, el buzón permanecerá en espera. Para usar la nueva dirección SMTP para colocar la suspensión, cree una nueva suspensión.

## <a name="view-hold-statistics"></a>Visualización de estadísticas de retención

Después de algún tiempo, la información sobre la nueva suspensión se muestra en el panel de detalles de la pestaña **Retenciones** de la retención seleccionada. Esta información incluye el número de buzones y sitios en espera y estadísticas sobre el contenido que se ha colocado en suspensión, como el número total y el tamaño de los elementos colocados en espera y la última vez que se calcularon las estadísticas de retención. Estas estadísticas de retención le ayudan a identificar la cantidad de contenido relacionado con el caso de eDiscovery que se mantiene.

Tenga en cuenta lo siguiente sobre las estadísticas de retención:

- El número total de elementos en espera indica el número de elementos de todos los orígenes de contenido que se colocan en suspensión. Si ha creado una retención basada en consultas, esta estadística indica el número de elementos que coinciden con la consulta.
  
- El número de elementos en espera también incluye los elementos no indexados que se encuentran en las ubicaciones de contenido. Si crea una suspensión basada en consultas, todos los elementos no indexados de las ubicaciones de contenido se colocan en suspensión. Esto incluye elementos sin indexar que no coinciden con los criterios de búsqueda de una retención basada en consultas y elementos sin indexar que podrían estar fuera de una condición de intervalo de fechas. Esto es diferente de lo que sucede cuando se ejecuta una búsqueda de contenido, en la que los elementos sin indexar que no coinciden con la consulta de búsqueda o que están excluidos por una condición de intervalo de fechas no se incluyen en los resultados de la búsqueda. Para obtener más información sobre los elementos sin indexar, vea [Elementos indizados parcialmente en búsqueda de contenido en Office 365](partially-indexed-items-in-content-search.md).

- Para obtener las estadísticas de retención más recientes, haga clic en Actualizar estadísticas para volver a ejecutar una estimación de búsqueda que calcule el número actual de elementos en espera.

- Si es necesario, haga clic en Actualizar en la barra de herramientas para actualizar las estadísticas de suspensión en el panel de detalles.

- Es normal que el número de elementos en espera aumente con el tiempo porque los usuarios cuyo buzón de correo o sitio está en espera suelen enviar o recibir nuevos mensajes de correo electrónico y crear nuevos documentos SharePoint y OneDrive para la Empresa.

- Si un sitio de SharePoint o una cuenta de OneDrive se mueve a una región diferente en un entorno multigeográfico, las estadísticas de ese sitio no se incluirán en las estadísticas de suspensión. Sin embargo, el contenido del sitio seguirá en espera. Además, si un sitio se mueve a otra región, la dirección URL que se muestra en la suspensión no se actualizará. Tendrá que editar la suspensión y actualizar la dirección URL.

## <a name="place-a-hold-on-microsoft-teams-and-office-365-groups"></a>Mantener Microsoft Teams y Office 365 Grupos

Microsoft Teams se basa en grupos de Office 365. Por lo tanto, colocarlos en espera en eDiscovery (Premium) es similar.

- **Cómo asignar un sitio Grupos de Microsoft 365 o Microsoft Teams adicional a un custodio? ¿Y qué hay de colocar una suspensión no custodial en Grupos de Microsoft 365 y Microsoft Teams?** Microsoft Teams se basa en Grupos de Microsoft 365. Por lo tanto, colocarlos en espera en un caso de exhibición de documentos electrónicos es similar. Tenga en cuenta lo siguiente al poner Grupos de Microsoft 365 y Microsoft Teams en espera.

  - Para colocar contenido ubicado en Grupos de Microsoft 365 y Microsoft Teams en espera, debe especificar el buzón y SharePoint sitio asociado a un grupo o equipo.
  
  - Ejecute el cmdlet **Get-UnifiedGroup** en Exchange Online para ver las propiedades de un grupo de Microsoft 365 o un equipo de Microsoft. Esta es una buena manera de obtener la dirección URL del sitio asociado a un grupo de Microsoft 365 o un equipo de Microsoft. Por ejemplo, el comando siguiente muestra las propiedades seleccionadas de un grupo de Microsoft 365 denominado Senior Leadership Team:

    ```console
    Get-UnifiedGroup "Senior Leadership Team" | FL DisplayName,Alias,PrimarySmtpAddress,SharePointSiteUrl
    DisplayName            : Senior Leadership Team
    Alias                  : seniorleadershipteam
    PrimarySmtpAddress     : seniorleadershipteam@contoso.onmicrosoft.com
    SharePointSiteUrl      : https://contoso.sharepoint.com/sites/seniorleadershipteam
    ```

    > [!NOTE]
    > Para ejecutar el cmdlet Get-UnifiedGroup debe tener asignado el rol de destinatarios con permiso de vista en Exchange Online o ser un miembro de un grupo de roles que tenga asignado el rol de destinatarios con permiso de vista.

  - Cuando se busca el buzón de un usuario, no se buscará en ningún grupo de Microsoft 365 o equipo de Microsoft del que sea miembro el usuario. De forma similar, cuando se coloca una suspensión de grupo Microsoft 365 o equipo de Microsoft, solo el buzón de grupo y el sitio de grupo se colocan en suspensión; los buzones y los sitios de OneDrive para la Empresa de los miembros del grupo no se colocan en suspensión a menos que los agregue explícitamente como custodios o coloque sus orígenes de datos en suspensión. Por lo tanto, si necesita colocar un grupo de Microsoft 365 o un equipo de Microsoft en espera para un custodio específico, considere la posibilidad de asignar el sitio de grupo y el buzón de grupo al custodio (consulte Administración de custodios en eDiscovery (Premium)). Si el grupo de Microsoft 365 o el equipo de Microsoft no es atribuible a un único custodio, considere la posibilidad de agregar el origen a una retención que no sea de custodia.
  - Para obtener una lista de los miembros de un grupo de Microsoft 365 o un equipo de Microsoft, puede ver las propiedades en la página [**HomeGroups**](https://go.microsoft.com/fwlink/p/?linkid=2052855)  >  del Centro de administración de Microsoft 365. Además, puede ejecutar el comando siguiente en PowerShell de Exchange Online:

    ```powershell
    Get-UnifiedGroupLinks <group or team name> -LinkType Members | FL DisplayName,PrimarySmtpAddress
    ```

    > [!NOTE]
    > Para ejecutar el cmdlet **Get-UnifiedGroupLinks** debe tener asignado el rol de destinatarios con permiso de vista en Exchange Online o ser un miembro de un grupo de roles que tenga asignado el rol de destinatarios con permiso de vista.

  - Las conversaciones de canal que forman parte de un canal Microsoft Teams se almacenan en el buzón de correo asociado al equipo. Asimismo, los archivos que los miembros del equipo comparten en un canal se almacenan en el sitio de SharePoint del equipo. Por lo tanto, debe colocar el buzón de Microsoft Team y SharePoint sitio en espera para conservar conversaciones y archivos en un canal.
  
  - Como alternativa, las conversaciones que forman parte de la lista chat en Microsoft Teams se almacenan en el buzón de correo del usuario que participa en el chat.  Los archivos que un usuario comparte en conversaciones de chat se almacenan en el sitio OneDrive para la Empresa del usuario que comparte el archivo. Por lo tanto, debe colocar los buzones de usuario individuales y los sitios de OneDrive para la Empresa en espera para conservar conversaciones y archivos en la lista chat.
  
  - Cada equipo de Microsoft o canal de equipo contiene una wiki para tomar notas y colaborar. El contenido de esta se guarda automáticamente en un archivo con un formato .mht. Este archivo se almacena en la biblioteca de documentos de Datos Wiki de Teams en el sitio de SharePoint del equipo. Para poner el contenido en espera del wiki, coloque el sitio de SharePoint del grupo en suspensión.

    > [!NOTE]
    > El 22 de junio de 2017 se publicó la capacidad de conservar el contenido wiki de un equipo de Microsoft o un canal de equipo (cuando se coloca el sitio de SharePoint del equipo en espera). Si un sitio de equipo está en espera, el contenido wiki se conservará a partir de esa fecha. Sin embargo, si un sitio de equipo está en espera y el contenido wiki se eliminó antes del 22 de junio de 2017, no se retuvo el contenido wiki.
