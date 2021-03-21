---
title: Administrar retenciones en eDiscovery avanzada
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Obtenga información sobre cómo colocar retenciones en los custodios y sus orígenes de datos para conservar el contenido relevante para su caso de exhibición de documentos electrónicos avanzada.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 07edcb2707d1dffecfa5a2aac6c4340ac6cbe53f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926378"
---
# <a name="manage-holds-in-advanced-ediscovery"></a>Administrar retenciones en eDiscovery avanzada

Puede usar un caso de exhibición de documentos electrónicos avanzada para crear retenciones para conservar contenido que pueda ser relevante para su caso. Con las capacidades de retención avanzada de exhibición de documentos electrónicos, puede colocar retenciones en los custodios y sus orígenes de datos. Además, puede colocar una retención sin custodia en buzones y sitios de OneDrive para la Empresa. También puede colocar una retención en el buzón de grupo, el sitio de SharePoint y el sitio de OneDrive para la Empresa para un grupo de Microsoft 365. Del mismo modo, puede colocar una retención en el buzón y el sitio asociados con Microsoft Teams. Al poner las ubicaciones de contenido en espera, el contenido se mantiene hasta que libera al custodio, quita una ubicación de datos específica o elimina la directiva de retención por completo.

## <a name="manage-custodian-based-holds"></a>Administrar retenciones basadas en custodios

En algunos casos, es posible que tenga un conjunto de custodios que haya identificado y haya decidido conservar sus datos durante el caso. En eDiscovery avanzada, cuando estos custodios se ponen en espera, el usuario y sus orígenes de datos seleccionados se agregan automáticamente a una directiva de retención de custodia.

Para ver la directiva de retención de custodia:

1. En el Centro de cumplimiento de Microsoft 365, haga clic en **eDiscovery > Advanced** para mostrar la lista de casos de la organización.

2. Vaya a la **pestaña Orígenes** para agregar custodios dentro de su caso. Para obtener información sobre cómo agregar y poner a los custodios en espera dentro de un caso de exhibición de documentos electrónicos [avanzados, vea Agregar custodios a un caso](add-custodians-to-case.md). Si ya ha agregado custodios y los ha puesto en espera, vaya al paso 3.

3. Vaya a la **pestaña Retenciones** y haga clic **en \<HoldId> CustodianHold**.

4. En la página desplegable, puede ver las estadísticas de retención de la directiva. También puede realizar acciones como aplicar una consulta a la retención basada en custodia. Para obtener más información acerca de la creación de una consulta de retención y el uso de condiciones, vea Consultas de palabras clave y condiciones [de búsqueda para búsqueda de contenido](keyword-queries-and-search-conditions.md).

## <a name="manage-non-custodial-holds"></a>Administrar retenciones sin custodia

Al crear una retención, tiene las siguientes opciones para tener en cuenta el contenido que se mantiene en las ubicaciones de contenido especificadas:

- Se crea una retención infinita donde todo el contenido está en espera. Como alternativa, puede crear una retención basada en consultas en la que solo el contenido que coincida con una consulta de búsqueda esté en espera.
  
- Puede especificar un intervalo de fechas para contener solo el contenido que se envió, recibió o creó dentro de ese intervalo de fechas. Como alternativa, puede contener todo el contenido independientemente de cuándo se envió, recibió o creó.

Para crear una retención sin custodia para un caso de exhibición de documentos electrónicos avanzada:

1. En el Centro de cumplimiento de Microsoft 365, haga clic en **eDiscovery > Advanced** para mostrar la lista de casos de la organización.
  
2. Haga **clic en** Abrir junto al caso en el que desea crear las retenciones.
  
3. En la página principal del caso, haga clic en la **pestaña Retenciones.**
  
4. En la **pestaña Retenciones,** haga clic **en Crear**.
  
5. En la **página Nombre de la** retención, asigne un nombre a la retención. El nombre de la suspensión debe ser exclusivo en la organización.
 
6. (Opcional) En el **cuadro** Descripción, agregue una descripción de la retención.
  
7. Haga clic en **Siguiente**.
  
8. Elija las ubicaciones de contenido que desea poner en espera. Puede poner buzones, sitios y carpetas públicas en espera.

   1. **Correo electrónico de Exchange:** haga clic en Elegir usuarios, grupos o equipos **y,** a continuación, vuelva a hacer clic en Elegir **usuarios,** grupos o equipos para especificar los buzones que se colocarán en espera. Use el cuadro de búsqueda para buscar buzones de usuario y grupos de distribución (para colocar una retención en los buzones de los miembros del grupo) para colocar en espera. También puede colocar una retención en el buzón asociado para un grupo de Microsoft 365 o un equipo de Microsoft. Active la casilla usuario, grupo, equipo, haga clic **en Elegir** y, a continuación, haga clic **en Listo**.
 
      > [!NOTE]
      > Al hacer clic **en Elegir usuarios,** grupos o equipos para especificar los buzones que se colocarán en espera, el selector de buzones que se muestra está vacío. Esto se ha diseñado así para mejorar el rendimiento. Para agregar personas a esta lista, escriba un nombre (un mínimo de 3 caracteres) en el cuadro de búsqueda.

   1. **Sitios de SharePoint:** haga  clic **en Elegir sitios** y, a continuación, en Elegir sitios de nuevo para especificar los sitios de SharePoint y OneDrive para la Empresa que se colocarán en espera. Escriba la dirección URL de cada sitio que quiere suspender. También puede agregar la dirección URL del sitio de SharePoint para un grupo de Microsoft 365 o un equipo de Microsoft. Haga **clic en** Elegir y, a continuación, en **Listo.**
    
      Consulta la **sección preguntas** más frecuentes para obtener sugerencias sobre cómo poner grupos de Microsoft 365 y Microsoft Teams en espera.

      > [!NOTE]
      > La dirección URL de la cuenta de OneDrive de un usuario incluye su nombre principal de usuario (UPN) (por ejemplo, `https://alpinehouse-my.sharepoint.com/personal/sarad_alpinehouse_onmicrosoft_com` ). En el caso poco frecuente de que se cambie el UPN de una persona, la dirección URL de OneDrive también cambiará para incorporar el nuevo UPN. Si la cuenta de OneDrive de un usuario forma parte de una retención sin custodia y se cambia su UPN, debe actualizar la retención y apuntar a la nueva dirección URL de OneDrive. Para más información, consulte [Cómo afectan los cambios de UPN a la dirección URL de OneDrive](/onedrive/upn-changes).

   1. **Carpetas públicas de Exchange:** mueva el modificador de alternancia a la posición Todos para poner en espera todas las carpetas públicas de la organización de Exchange Online. Tenga en cuenta que no puede elegir carpetas públicas específicas para poner en espera. Deje el modificador de alternancia establecido en **Ninguno** si no desea poner una retención en carpetas públicas.

9. Cuando haya terminado de agregar ubicaciones de contenido a la retención, haga clic en **Siguiente**.
  
10. Para crear una retención basada en consultas con condiciones, complete lo siguiente. De lo contrario, simplemente haga clic **en Siguiente**.
    
    - En el cuadro de **palabras** clave , escriba una consulta de búsqueda en el cuadro para que solo se mantenga en espera el contenido que cumpla los criterios de búsqueda. Puede especificar palabras clave, propiedades de mensaje o propiedades de documento, como nombres de archivo. También puede usar consultas más complejas que usen un operador booleano, como AND, OR o NOT. Si deja el cuadro de palabra clave vacío, todo el contenido ubicado en las ubicaciones de contenido especificadas se colocará en espera.

    - Haga  **clic en** Agregar condiciones para agregar una o más condiciones para restringir la consulta de búsqueda para la retención. Cada condición agrega una cláusula a la consulta de búsqueda KQL que se crea y se ejecuta al crear la retención. Por ejemplo, puede especificar un intervalo de fechas para que los documentos de correo electrónico o de sitio que se crearon dentro del intervalo de fechas se coloquen en espera. Una condición se conecta lógicamente a la consulta de palabra clave (especificada en el cuadro de palabra clave) mediante el operador AND. Esto significa que los elementos deben satisfacer tanto la consulta de palabras clave como la condición que se va a colocar en espera.

     Para obtener más información acerca de cómo crear una consulta de búsqueda y usar condiciones, vea Consultas de palabras clave y condiciones [de búsqueda para búsqueda de contenido](/office365/SecurityCompliance/keyword-queries-and-search-conditions).

11. Después de configurar una retención basada en consultas, haga clic en **Siguiente**.

12. Revise la configuración y, a continuación, **haga clic en Crear esta retención.**

## <a name="view-hold-statistics"></a>Ver estadísticas de retención

Después de algún tiempo, la información sobre la nueva retención se muestra en el panel de detalles de la pestaña **Retenciones** de la retención seleccionada. Esta información incluye el número de buzones y sitios en espera y estadísticas sobre el contenido que se colocó en espera, como el número total y el tamaño de los elementos puestos en espera y la última vez que se calcularon las estadísticas de retención. Estas estadísticas de retención le ayudan a identificar la cantidad de contenido relacionado con el caso de exhibición de documentos electrónicos que se está celebrando.

Tenga en cuenta lo siguiente sobre las estadísticas de retención:

- El número total de elementos en espera indica el número de elementos de todos los orígenes de contenido que están en espera. Si ha creado una retención basada en consultas, esta estadística indica el número de elementos que coinciden con la consulta.
  
- El número de elementos en espera también incluye elementos no indexados que se encuentran en las ubicaciones de contenido. Tenga en cuenta que si crea una retención basada en consultas, todos los elementos sin indizar de las ubicaciones de contenido se colocan en espera. Esto incluye elementos sin indizar que no coinciden con los criterios de búsqueda de una retención basada en consultas y elementos sin indizar que podrían estar fuera de una condición de intervalo de fechas. Esto es diferente de lo que sucede al ejecutar una búsqueda de contenido, en la que los elementos no indexados que no coinciden con la consulta de búsqueda o que se excluyen por una condición de intervalo de fechas no se incluyen en los resultados de la búsqueda. Para obtener más información acerca de los elementos sin indizar, vea Elementos parcialmente indizados en Búsqueda de contenido [en Office 365](partially-indexed-items-in-content-search.md). 

- Puede obtener las estadísticas de retención más recientes haciendo clic en Actualizar estadísticas para volver a ejecutar una estimación de búsqueda que calcule el número actual de elementos en espera.

- Si es necesario, haga clic en Actualizar en la barra de herramientas para actualizar las estadísticas de retención en el panel de detalles.

- Es normal que el número de elementos en espera aumente con el tiempo porque los usuarios cuyo buzón o sitio están en espera suelen enviar o recibir un nuevo mensaje de correo electrónico y crear nuevos documentos de SharePoint y OneDrive para la Empresa.

- Si se mueve un sitio de SharePoint o una cuenta de OneDrive a una región diferente en un entorno multigeónico, las estadísticas de ese sitio no se incluirán en las estadísticas de retención. Sin embargo, el contenido del sitio seguirá en espera. Además, si un sitio se mueve a una región diferente, la dirección URL que se muestra en la retención no se actualizará. Tendrás que editar la retención y actualizar la dirección URL.

## <a name="place-a-hold-on-microsoft-teams-and-office-365-groups"></a>Colocar una retención en Grupos de Microsoft Teams y Office 365

Microsoft Teams se basa en grupos de Office 365. Por lo tanto, ponerlas en espera en exhibición de documentos electrónicos avanzados es muy similar. 

- **¿Cómo puedo asignar un sitio adicional de Grupos de Microsoft 365 o Microsoft Teams a un custodio? ¿Y qué sucede con la colocación de una retención no custodial en Grupos de Microsoft 365 y Microsoft Teams?** Microsoft Teams se basa en grupos de Microsoft 365. Por lo tanto, ponerlas en espera en un caso de exhibición de documentos electrónicos es muy similar. Tenga en cuenta lo siguiente al poner grupos de Microsoft 365 y Microsoft Teams en espera.
  - Para poner contenido ubicado en Grupos de Microsoft 365 y Microsoft Teams en espera, debe especificar el buzón y el sitio de SharePoint asociados con un grupo o equipo.
  
  - Ejecute el cmdlet **Get-UnifiedGroup** en Exchange Online para ver las propiedades de un grupo de Microsoft 365 o un equipo de Microsoft. Esta es una buena forma de obtener la dirección URL del sitio asociado a un grupo de Microsoft 365 o a un equipo de Microsoft. Por ejemplo, el comando siguiente muestra las propiedades seleccionadas de un grupo de Microsoft 365 denominado Senior Leadership Team:


    ```console
    Get-UnifiedGroup "Senior Leadership Team" | FL DisplayName,Alias,PrimarySmtpAddress,SharePointSiteUrl
    DisplayName            : Senior Leadership Team
    Alias                  : seniorleadershipteam
    PrimarySmtpAddress     : seniorleadershipteam@contoso.onmicrosoft.com
    SharePointSiteUrl      : https://contoso.sharepoint.com/sites/seniorleadershipteam
    ```

    > [!NOTE]
    > Para ejecutar el cmdlet Get-UnifiedGroup debe tener asignado el rol de destinatarios con permiso de vista en Exchange Online o ser un miembro de un grupo de roles que tenga asignado el rol de destinatarios con permiso de vista.

 - Cuando se busca el buzón de un usuario, no se buscará ningún grupo de Microsoft 365 o equipo de Microsoft del que el usuario sea miembro. Del mismo modo, cuando se coloca una retención de Grupo de Microsoft 365 o Microsoft Team, solo el buzón de grupo y el sitio de grupo se colocan en espera; los buzones y los sitios de OneDrive para la Empresa de los miembros del grupo no se ponen en espera a menos que los agregue explícitamente como custodios o coloque sus orígenes de datos en espera. Por lo tanto, si necesita poner un grupo de Microsoft 365 o un equipo de Microsoft en espera para un custodio específico, considere la posibilidad de asignar el sitio de grupo y el buzón de grupo al custodio (vea Managing Custodians in Advanced eDiscovery). Si el grupo de Microsoft 365 o el equipo de Microsoft no es atribuible a un único custodio, considere la posibilidad de agregar el origen a una retención sin custodia. 
 
 - Para obtener una lista de los miembros de un grupo de Microsoft 365 o un equipo de Microsoft, puede ver las propiedades en la página Home > Groups en el Centro de administración de Microsoft 365. Además, puede ejecutar el comando siguiente en PowerShell de Exchange Online:

   ```powershell
   Get-UnifiedGroupLinks <group or team name> -LinkType Members | FL DisplayName,PrimarySmtpAddress
   ```

    > [!NOTE]
    > Para ejecutar el cmdlet **Get-UnifiedGroupLinks** debe tener asignado el rol de destinatarios con permiso de vista en Exchange Online o ser un miembro de un grupo de roles que tenga asignado el rol de destinatarios con permiso de vista.

- Las conversaciones de canal que forman parte de un canal de Microsoft Teams se almacenan en el buzón asociado al equipo. Asimismo, los archivos que los miembros del equipo comparten en un canal se almacenan en el sitio de SharePoint del equipo. Por lo tanto, debe poner el buzón de Microsoft Team y el sitio de SharePoint en espera para conservar conversaciones y archivos en un canal.
  
- Como alternativa, las conversaciones que forman parte de la lista chat en Microsoft Teams se almacenan en el buzón de los usuarios que participan en el chat.  Los archivos que un usuario comparte en conversaciones de chat se almacenan en el sitio de OneDrive para la Empresa del usuario que comparte el archivo. Por lo tanto, debe poner en espera los buzones de usuario individuales y los sitios de OneDrive para la Empresa para conservar conversaciones y archivos en la lista chat. 
  
- Cada canal de equipo o equipo de Microsoft contiene un wiki para tomar notas y colaborar. El contenido de esta se guarda automáticamente en un archivo con un formato .mht. Este archivo se almacena en la biblioteca de documentos de Datos Wiki de Teams en el sitio de SharePoint del equipo. Puede poner el contenido en la Wiki en espera colocando el sitio de SharePoint del equipo en espera.

  > [!NOTE]
  > La capacidad de retener contenido wiki para un equipo de Microsoft o un canal de equipo (cuando se coloca el sitio de SharePoint del equipo en espera) se publicó el 22 de junio de 2017. Si un sitio de grupo está en espera, el contenido wiki se conservará a partir de esa fecha. Sin embargo, si un sitio de grupo está en espera y el contenido wiki se eliminó antes del 22 de junio de 2017, no se retuvo el contenido wiki.