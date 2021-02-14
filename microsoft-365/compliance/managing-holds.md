---
title: Administrar retenciones en eDiscovery avanzado
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Obtenga información sobre cómo colocar retenciones en administradores y sus orígenes de datos para conservar el contenido relevante para su caso de eDiscovery avanzado.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: f56d12b6d69e56e85f0e7ad37fbf65746a1cff23
ms.sourcegitcommit: 51a9f34796535309b8ca8b52da92da0a3621327b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2020
ms.locfileid: "45024740"
---
# <a name="manage-holds-in-advanced-ediscovery"></a>Administrar retenciones en eDiscovery avanzado

Puede usar un caso de eDiscovery avanzado para crear retenciones para conservar el contenido que pueda ser relevante para su caso. Con las capacidades de retención avanzada de exhibición de documentos electrónicos, puede colocar retenciones en los administradores y sus orígenes de datos. Además, puede colocar una retención no custodiada en buzones y sitios de OneDrive para la Empresa. También puede colocar una retención en el buzón de grupo, el sitio de SharePoint y el sitio de OneDrive para la Empresa para un grupo de Microsoft 365. De forma similar, puede colocar una retención en el buzón y el sitio asociados con Microsoft Teams. Cuando coloca las ubicaciones de contenido en retención, el contenido se mantiene hasta que libera al administrador, quita una ubicación de datos específica o elimina la directiva de retención por completo.

## <a name="manage-custodian-based-holds"></a>Administrar retenciones basadas en administradores

En algunos casos, es posible que tenga un conjunto de administradores que haya identificado y haya decidido conservar sus datos durante el caso. En eDiscovery avanzado, cuando estos administradores se colocan en retención, el usuario y sus orígenes de datos seleccionados se agregan automáticamente a una directiva de retención de administradores.

Para ver la directiva de retención de administradores:

1. En el Centro de cumplimiento de Microsoft 365, haga clic en **eDiscovery > Avanzado** para mostrar la lista de casos de su organización.

2. Vaya a la **pestaña Orígenes** para agregar administradores dentro de su caso. Para obtener información sobre cómo puede agregar y poner a los administradores en retención dentro de un caso de eDiscovery avanzado, vea Agregar administradores [a un caso.](add-custodians-to-case.md) Si ya ha agregado administradores y los ha puesto en retención, vaya al paso 3.

3. Vaya a la **pestaña Retenciones** y haga clic **en \<HoldId> CustodianHold**.

4. En la página desplegable, puedes ver las estadísticas de retención de la directiva. También puede realizar acciones como aplicar una consulta a la retención basada en administrador. Para obtener más información acerca de la creación de una consulta de retención y el uso de condiciones, vea Consultas de palabras clave y condiciones de búsqueda [para búsqueda de contenido.](keyword-queries-and-search-conditions.md)

## <a name="manage-non-custodial-holds"></a>Administrar retenciones que no son de custodia

Al crear una retención, tiene las siguientes opciones para el ámbito del contenido que se mantiene en las ubicaciones de contenido especificadas:

- Se crea una retención infinita en la que todo el contenido se coloca en espera. Como alternativa, puede crear una retención basada en consulta en la que solo se reteje el contenido que coincida con una consulta de búsqueda.
  
- Puede especificar un intervalo de fechas para contener solo el contenido que se envió, recibió o creó dentro de ese intervalo de fechas. Como alternativa, puede retener todo el contenido independientemente de cuándo se envió, recibió o creó.

Para crear una retención no custodial para un caso de eDiscovery avanzado:

1. En el Centro de cumplimiento de Microsoft 365, haga clic en **eDiscovery > Avanzado** para mostrar la lista de casos de su organización.
  
2. Haga **clic** en Abrir junto al caso en el que desea crear las retenciones.
  
3. En la página principal del caso, haga clic en la **pestaña Retenciones.**
  
4. En la **pestaña Retenciones,** haga clic **en Crear**.
  
5. En la **página Nombre de la** retención, asigne un nombre a la retención. El nombre de la suspensión debe ser exclusivo en la organización.
 
6. (Opcional) En el **cuadro** Descripción, agregue una descripción de la retención.
  
7. Haga clic en **Siguiente**.
  
8. Elija las ubicaciones de contenido que desea poner en espera. Puede colocar buzones, sitios y carpetas públicas en espera.

   1. **Correo electrónico de Exchange:** haga clic en Elegir **usuarios,** grupos o equipos y, a continuación, vuelva a hacer clic en Elegir **usuarios, grupos** o equipos para especificar los buzones que se deben poner en espera. Use el cuadro de búsqueda para buscar buzones de usuario y grupos de distribución (para colocar una retención en los buzones de los miembros del grupo) para poner en espera. También puede colocar una retención en el buzón asociado para un grupo de Microsoft 365 o un equipo de Microsoft. Seleccione la casilla usuario, grupo, equipo, haga clic en **Elegir** y, a continuación, haga clic en **Listo.**
 
      > [!NOTE]
      > Al hacer clic **en Elegir usuarios,** grupos o equipos para especificar los buzones que se deben poner en retención, el selector de buzones que se muestra está vacío. Esto se ha diseñado así para mejorar el rendimiento. Para agregar personas a esta lista, escriba un nombre (un mínimo de 3 caracteres) en el cuadro de búsqueda.

   1. **Sitios de SharePoint:** haga  clic **en** Elegir sitios y, a continuación, haga clic en Elegir sitios de nuevo para especificar sitios de SharePoint y OneDrive para la Empresa para poner en espera. Escriba la dirección URL de cada sitio que quiere suspender. También puede agregar la dirección URL del sitio de SharePoint para un grupo de Microsoft 365 o un equipo de Microsoft. Haga **clic en** Elegir y, a continuación, haga clic en **Listo.**
    
      Consulte la sección **de preguntas** más frecuentes para obtener sugerencias sobre cómo poner grupos de Microsoft 365 y Microsoft Teams en espera.

      > [!NOTE]
      > La dirección URL de la cuenta de OneDrive de un usuario incluye su nombre principal de usuario (UPN) (por ejemplo, `https://alpinehouse-my.sharepoint.com/personal/sarad_alpinehouse_onmicrosoft_com` ). En el caso poco frecuente de que se cambie el UPN de una persona, la dirección URL de OneDrive también cambiará para incorporar el nuevo UPN. Si la cuenta de OneDrive de un usuario forma parte de una retención que no es de custodia y se cambia su UPN, debe actualizar la retención y apuntar a la nueva dirección URL de OneDrive. Para más información, consulte [Cómo afectan los cambios de UPN a la dirección URL de OneDrive](https://docs.microsoft.com/onedrive/upn-changes).

   1. **Carpetas públicas de Exchange:** mueva el modificador de alternancia a la posición Todos para poner todas las carpetas públicas de su organización de Exchange Online en espera. Tenga en cuenta que no puede elegir carpetas públicas específicas para poner en espera. Deje el modificador para alternar establecido en **Ninguno** si no desea poner una retención en carpetas públicas.

9. Cuando haya terminado de agregar ubicaciones de contenido a la retención, haga clic en **Siguiente.**
  
10. Para crear una retención basada en consultas con condiciones, complete lo siguiente. De lo contrario, simplemente haga clic **en Siguiente**.
    
    - En el cuadro debajo de **Palabras** clave , escriba una consulta de búsqueda en el cuadro para que solo se coloque en espera el contenido que cumple los criterios de búsqueda. Puede especificar palabras clave, propiedades de mensaje o propiedades de documento, como nombres de archivo. También puede usar consultas más complejas que usen un operador booleano, como AND, OR o NOT. Si deja vacío el cuadro de palabra clave, todo el contenido ubicado en las ubicaciones de contenido especificadas se colocará en espera.

    - Haga  **clic en** Agregar condiciones para agregar una o más condiciones para restringir la consulta de búsqueda para la retención. Cada condición agrega una cláusula a la consulta de búsqueda de KQL que se crea y ejecuta al crear la retención. Por ejemplo, puede especificar un intervalo de fechas para que el correo electrónico o los documentos del sitio que se crearon dentro del intervalo de fechas se coloquen en espera. Una condición se conecta lógicamente a la consulta de palabra clave (especificada en el cuadro de palabra clave) mediante el operador AND. Esto significa que los elementos deben satisfacer tanto la consulta de palabra clave como la condición que se va a colocar en espera.

     Para obtener más información acerca de la creación de una consulta de búsqueda y el uso de condiciones, vea Consultas de palabras clave y condiciones de búsqueda [para búsqueda de contenido.](https://docs.microsoft.com/office365/SecurityCompliance/keyword-queries-and-search-conditions)

11. Después de configurar una retención basada en consultas, haga clic en **Siguiente**.

12. Revise la configuración y, a continuación, haga **clic en Crear esta retención.**

## <a name="view-hold-statistics"></a>Ver estadísticas de retención

Después de algún tiempo, la información sobre la nueva  retención se muestra en el panel de detalles de la pestaña Retenciones de la retención seleccionada. Esta información incluye el número de buzones y sitios en retención y estadísticas sobre el contenido que se colocó en retención, como el número total y el tamaño de los elementos colocados en retención y la última vez que se calcularon las estadísticas de retención. Estas estadísticas de retención le ayudan a identificar cuánto contenido está relacionado con el caso de eDiscovery que se está retenido.

Tenga en cuenta lo siguiente sobre las estadísticas de retención:

- El número total de elementos en espera indica el número de elementos de todos los orígenes de contenido que están en retención. Si ha creado una retención basada en consulta, esta estadística indica el número de elementos que coinciden con la consulta.
  
- El número de elementos en retención también incluye los elementos no indexados que se encuentran en las ubicaciones de contenido. Tenga en cuenta que si crea una retención basada en consultas, todos los elementos no indexados de las ubicaciones de contenido se colocan en retención. Esto incluye elementos no indexados que no coinciden con los criterios de búsqueda de una retención basada en consulta y elementos sin indexar que podrían estar fuera de una condición de intervalo de fechas. Esto es diferente de lo que sucede cuando se ejecuta una búsqueda de contenido, en la que los elementos no indexados que no coinciden con la consulta de búsqueda o que se excluyen mediante una condición de intervalo de fechas no se incluyen en los resultados de la búsqueda. Para obtener más información acerca de los elementos no indexados, vea Elementos parcialmente indizados en búsqueda de contenido [en Office 365.](partially-indexed-items-in-content-search.md) 

- Puede obtener las estadísticas de retención más recientes haciendo clic en Actualizar estadísticas para volver a ejecutar una estimación de búsqueda que calcule el número actual de elementos en retención.

- Si es necesario, haga clic en Actualizar en la barra de herramientas para actualizar las estadísticas de retención en el panel de detalles.

- Es normal que el número de elementos en retención aumente con el tiempo porque los usuarios cuyo buzón o sitio está en retención suelen enviar o recibir un nuevo mensaje de correo electrónico y crear nuevos documentos de SharePoint y OneDrive para la Empresa.

- Si se mueve un sitio de SharePoint o una cuenta de OneDrive a una región diferente en un entorno multigemico, las estadísticas de ese sitio no se incluirán en las estadísticas de retención. Sin embargo, el contenido del sitio seguirá en espera. Además, si un sitio se mueve a una región diferente, la dirección URL que se muestra en la retención no se actualizará. Tendrá que editar la retención y actualizar la dirección URL.

## <a name="place-a-hold-on-microsoft-teams-and-office-365-groups"></a>Colocar una retención en Grupos de Microsoft Teams y Office 365

Microsoft Teams se basa en Grupos de Office 365. Por lo tanto, ponerlas en espera en eDiscovery avanzado es muy similar. 

- **¿Cómo se asigna un sitio adicional de Grupos de Microsoft 365 o Microsoft Teams a un administrador? ¿Y qué sucede con la colocación de una retención no administradora en Grupos de Microsoft 365 y Microsoft Teams?** Microsoft Teams se basa en Grupos de Microsoft 365. Por lo tanto, ponerlas en espera en un caso de exhibición de documentos electrónicos es muy similar. Tenga en cuenta lo siguiente al poner grupos de Microsoft 365 y Microsoft Teams en espera.
  - Para poner contenido ubicado en Grupos de Microsoft 365 y Microsoft Teams en espera, debe especificar el buzón y el sitio de SharePoint asociados con un grupo o equipo.
  
  - Ejecute el cmdlet **Get-UnifiedGroup** en Exchange Online para ver las propiedades de un grupo de Microsoft 365 o Microsoft Team. Esta es una buena manera de obtener la dirección URL del sitio que está asociado a un grupo de Microsoft 365 o a un equipo de Microsoft. Por ejemplo, el comando siguiente muestra las propiedades seleccionadas de un grupo de Microsoft 365 denominado Senior Leadership Team:


    ```console
    Get-UnifiedGroup "Senior Leadership Team" | FL DisplayName,Alias,PrimarySmtpAddress,SharePointSiteUrl
    DisplayName            : Senior Leadership Team
    Alias                  : seniorleadershipteam
    PrimarySmtpAddress     : seniorleadershipteam@contoso.onmicrosoft.com
    SharePointSiteUrl      : https://contoso.sharepoint.com/sites/seniorleadershipteam
    ```

    > [!NOTE]
    > Para ejecutar el cmdlet Get-UnifiedGroup debe tener asignado el rol de destinatarios con permiso de vista en Exchange Online o ser un miembro de un grupo de roles que tenga asignado el rol de destinatarios con permiso de vista.

 - Cuando se busca en el buzón de un usuario, no se buscará en ningún grupo de Microsoft 365 o Microsoft Team del que el usuario sea miembro. Del mismo modo, cuando se coloca una retención de Grupo de Microsoft 365 o Microsoft Team, solo se colocan en retención el buzón de grupo y el sitio del grupo; Los buzones y los sitios de OneDrive para la Empresa de los miembros del grupo no se colocan en retención a menos que los agregue explícitamente como administradores o coloque la retención de sus orígenes de datos. Por lo tanto, si necesita poner un grupo de Microsoft 365 o Microsoft Team en retención para un administrador específico, considere la posibilidad de asignar el sitio de grupo y el buzón de grupo al administrador (vea Managing Custodians in Advanced eDiscovery). Si el Grupo de Microsoft 365 o Microsoft Team no es atribuible a un único administrador, considere la posibilidad de agregar el origen a una retención no administradora. 
 
 - Para obtener una lista de los miembros de un grupo de Microsoft 365 o Microsoft Team, puede ver las propiedades en la página Principal de grupos de > en el Centro de administración de Microsoft 365. Además, puede ejecutar el comando siguiente en PowerShell de Exchange Online:

   ```powershell
   Get-UnifiedGroupLinks <group or team name> -LinkType Members | FL DisplayName,PrimarySmtpAddress
   ```

    > [!NOTE]
    > Para ejecutar el cmdlet **Get-UnifiedGroupLinks** debe tener asignado el rol de destinatarios con permiso de vista en Exchange Online o ser un miembro de un grupo de roles que tenga asignado el rol de destinatarios con permiso de vista.

- Las conversaciones de canal que forman parte de un canal de Microsoft Teams se almacenan en el buzón asociado con el equipo. Asimismo, los archivos que los miembros del equipo comparten en un canal se almacenan en el sitio de SharePoint del equipo. Por lo tanto, debe poner el buzón de Microsoft Team y el sitio de SharePoint en espera para conservar conversaciones y archivos en un canal.
  
- Como alternativa, las conversaciones que forman parte de la lista de chat en Microsoft Teams se almacenan en el buzón de correo de los usuarios que participan en el chat.  Los archivos que comparte un usuario en conversaciones de chat se almacenan en el sitio de OneDrive para la Empresa del usuario que comparte el archivo. Por lo tanto, tiene que poner los buzones de usuario individuales y los sitios de OneDrive para la Empresa en espera para conservar las conversaciones y los archivos en la lista de chat. 
  
- Todos los canales de equipo o equipo de Microsoft Team contienen un sitio wiki para la toma de notas y la colaboración. El contenido de esta se guarda automáticamente en un archivo con un formato .mht. Este archivo se almacena en la biblioteca de documentos de Datos Wiki de Teams en el sitio de SharePoint del equipo. Puede poner el contenido del sitio wiki en retención si pone el sitio de SharePoint del equipo en retención.

  > [!NOTE]
  > La capacidad de conservar el contenido wiki de un equipo de Microsoft o un canal de equipo (cuando se coloca el sitio de SharePoint del equipo en espera) se publicó el 22 de junio de 2017. Si un sitio de grupo está en espera, el contenido wiki se conservará a partir de esa fecha. Sin embargo, si un sitio de grupo está en retención y el contenido wiki se eliminó antes del 22 de junio de 2017, no se retuvo el contenido wiki.
