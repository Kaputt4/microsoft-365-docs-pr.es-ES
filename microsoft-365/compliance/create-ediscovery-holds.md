---
title: Crear retenciones de exhibición de documentos electrónicos en un caso de eDiscovery principal
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
description: Puede crear una retención asociada a un caso de exhibición de documentos electrónicos principal para conservar el contenido que puede ser relevante para una investigación.
ms.openlocfilehash: 76ea455af0a7600cd901bdcdaeb0e4b15ef9bc43
ms.sourcegitcommit: cbe8724bd71d1c002395d98f1451c5f578c824f9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "49988154"
---
# <a name="create-an-ediscovery-hold"></a>Crear un caso de retención de eDiscovery

Puede usar un caso de exhibición de documentos electrónicos principal para crear retenciones para conservar el contenido que pueda ser relevante para el caso. Puede colocar una retención en los buzones de Exchange y en las cuentas de OneDrive para la Empresa de las personas que está investigando en el caso. También puede colocar una retención en los buzones y sitios asociados a Microsoft Teams, Grupos de Office 365 y Grupos de Yammer. Al poner las ubicaciones de contenido en retención, el contenido se conserva hasta que se quita la retención de la ubicación de contenido o hasta que se elimina la retención.

Después de crear una retención de exhibición de documentos electrónicos, la retención puede tardar hasta 24 horas en tener efecto. 

Al crear una retención, tiene las siguientes opciones para el ámbito del contenido que se conserva en las ubicaciones de contenido especificadas:
  
- Se crea una retención infinita en la que todo el contenido de las ubicaciones especificadas se coloca en retención. Como alternativa, puede crear una retención basada en consulta en la que solo se reteje el contenido de las ubicaciones especificadas que coincidan con una consulta de búsqueda.

- Puede especificar un intervalo de fechas para conservar solo el contenido que se envió, recibió o creó dentro de ese intervalo de fechas. Como alternativa, puede retener todo el contenido en ubicaciones especificadas independientemente de cuándo se envió, recibió o creó.
  
## <a name="how-to-create-an-ediscovery-hold"></a>Cómo crear una retención de exhibición de documentos electrónicos

Para crear una retención de exhibición de documentos electrónicos asociada a un caso de exhibición de documentos electrónicos principal:
  
1. Vaya e inicie sesión con las credenciales de la cuenta de usuario a la que se han asignado los permisos de exhibición de [https://compliance.microsoft.com](https://compliance.microsoft.com) documentos electrónicos adecuados.

2. En el panel de navegación izquierdo del Centro de cumplimiento de Microsoft 365, haga clic en Mostrar todo y, a continuación, haga clic en **eDiscovery > Principal.**

3. En la **página eDiscovery** principal, seleccione el caso en el que desea crear la retención y, a continuación, haga clic en **Abrir caso.**

4. En la **página principal** del caso, haga clic en la **pestaña Retenciones.**
  
5. En la **página Retenciones,** haga clic **en Crear**.

6. En la **página Nombre del asistente para** retención, asigne un nombre a la retención y agregue una descripción opcional y, a continuación, haga clic en **Siguiente.** El nombre de la suspensión debe ser exclusivo en la organización.

7. En la **página Ubicaciones de** contenido, elija las ubicaciones de contenido que desea poner en espera. Puede colocar buzones, sitios y carpetas públicas en espera.

    ![Elegir las ubicaciones de contenido para colocar en suspensión](../media/a59e4265-9151-4dbf-913f-6a4ab8db06b4.png)
  
   1. **Ubicaciones de buzones:** haga clic en Elegir **usuarios,** grupos o equipos y, a continuación, vuelva a hacer clic en Elegir **usuarios, grupos** o equipos para especificar los buzones que se colocarán en retención. Use el cuadro de búsqueda para buscar buzones de usuario y grupos de distribución (para colocar una retención en los buzones de los miembros del grupo) para poner en espera. También puede colocar una retención en el buzón asociado para un grupo de Microsoft Team, Office 365 o Yammer. Seleccione la casilla usuario, grupo, equipo, haga clic en **Elegir** y, a continuación, haga clic en **Listo.**

   1. **Ubicaciones de sitios:** haga  **clic en Elegir sitios** y, a continuación, haga clic en Elegir sitios de nuevo para especificar cuentas de SharePoint y OneDrive para ponerlas en retención. Escriba la dirección URL de cada sitio que quiere suspender. También puede agregar la dirección URL del sitio de SharePoint para un equipo de Microsoft, un grupo de Office 365 o un grupo de Yammer. Haga **clic en** Elegir y, a continuación, haga clic en **Listo.**
  
   1. **Carpetas públicas de Exchange.** Mueva el control de alternancia del modificador para alternar a la posición Todos para poner todas las carpetas públicas de la organización ![ de Exchange Online en ](../media/scc-toggle-on.png) espera.  No puede elegir carpetas públicas específicas para poner en espera. Deje el modificador para alternar establecido en **Ninguno** si no desea poner una retención en carpetas públicas.

   > [!NOTE]
   > Debe agregar al menos una ubicación de contenido a la retención. De lo contrario, las estáticas de retención de exhibición de documentos electrónicos mostrarán que no hay elementos en espera.

8. Cuando haya terminado de agregar ubicaciones de contenido a la retención, haga clic en **Siguiente.**

9. Para crear una retención basada en consultas con condiciones, complete lo siguiente. De lo contrario, para conservar todo el contenido de las ubicaciones de contenido especificadas, haga clic en **Siguiente**.

    ![Crear una retención basada en consultas con condiciones](../media/d587b58e-d05c-4ac0-b0fe-09019e4f1063.png)
  
    1. En el cuadro debajo **de Palabras clave,** escriba una consulta de búsqueda para que solo se conserve el contenido que cumple los criterios de búsqueda. Puede especificar palabras clave, propiedades de mensajes de correo electrónico o propiedades de documento, como nombres de archivo. También puede usar consultas más complejas que usen un operador booleano, como **AND**, **OR** o **NOT**.

    1. Haga **clic en Agregar condiciones** para agregar una o más condiciones para restringir la consulta de búsqueda para la retención. Cada condición agrega una cláusula a la consulta de búsqueda de KQL que se crea y ejecuta al crear la retención. Por ejemplo, puede especificar un intervalo de fechas para que el correo electrónico o los documentos del sitio que se crearon dentro del intervalo de fechas se coloquen en espera. Una condición está conectada lógicamente a la consulta de palabras clave (especificada en el cuadro **Palabras** clave) por el **operador AND.** Esto significa que los elementos deben satisfacer tanto la consulta de palabras clave como la condición que se va a conservar.

    Para obtener más información acerca de la creación de una consulta de búsqueda y el uso de condiciones, vea Consultas de palabras clave y condiciones de búsqueda [para búsqueda de contenido.](keyword-queries-and-search-conditions.md)

10. Después de configurar una retención basada en consultas, haga clic en **Siguiente**.

11. Revise la configuración (y edite si es necesario) y, a continuación, haga **clic en Crear esta retención.**

## <a name="query-based-holds-placed-on-site-documents"></a>Retenciones basadas en consultas colocadas en documentos del sitio

Tenga en cuenta lo siguiente al colocar una retención de exhibición de documentos electrónicos basada en consultas en documentos ubicados en sitios de SharePoint:

- Una retención basada en consultas conserva inicialmente todos los documentos de un sitio durante un breve período de tiempo después de que se eliminen. Esto significa que cuando se elimina un documento, se mueve a la biblioteca de conservación de documentos aunque no coincida con los criterios de la retención basada en consultas. Sin embargo, un trabajo del temporizador que procesa la biblioteca de conservación de documentos quitará los documentos eliminados que no coincidan con una retención basada en consultas. El trabajo del temporizador se ejecuta periódicamente y compara todos los documentos de la biblioteca de suspensión para conservación con las retenciones de exhibición de documentos electrónicos basadas en consultas (y otros tipos de retenciones y directivas de retención). El trabajo del temporizador elimina los documentos que no coinciden con una retención basada en consultas y conserva los documentos que sí lo hacen.

- Las retenciones basadas en consultas no deben usarse para realizar conservaciones dirigidas, como conservar documentos en una carpeta o sitio específicos o mediante otros criterios de retención basados en ubicación. Si lo hace, es posible que tenga resultados no deseados. Se recomienda usar criterios de retención no basados en ubicación, como palabras clave, intervalos de fechas u otras propiedades del documento para conservar los documentos del sitio.

## <a name="ediscovery-hold-statistics"></a>Estadísticas de retención de exhibición de documentos electrónicos

Después de crear una retención de exhibición de documentos electrónicos, la información sobre la nueva retención se muestra en la página desplegable de la retención seleccionada. Esta información incluye el número de buzones y sitios en retención y estadísticas sobre el contenido que se colocó en retención, como el número total y el tamaño de los elementos colocados en retención y la última vez que se calcularon las estadísticas de retención. Estas estadísticas de retención le ayudan a identificar la cantidad de contenido relacionado con el caso que se está conservando.
  
![Estadísticas de retención](../media/575cfe0a-9210-4ae4-8df8-65665d66712e.png)
  
Tenga en cuenta lo siguiente sobre las estadísticas de retención de exhibición de documentos electrónicos:
  
- El número total de elementos en espera indica el número de elementos de todos los orígenes de contenido que están en retención. Si ha creado una retención basada en consulta, esta estadística indica el número de elementos que coinciden con la consulta.

- El número de elementos en retención también incluye los elementos no indexados que se encuentran en las ubicaciones de contenido. Si crea una retención basada en consultas, todos los elementos no indexados de las ubicaciones de contenido se colocan en retención. Esto incluye elementos no indexados que no coinciden con los criterios de búsqueda de una retención basada en consulta y elementos sin indexar que podrían estar fuera de una condición de intervalo de fechas. Esto es diferente de lo que sucede cuando se ejecuta una búsqueda, en la que los elementos no indexados que no coinciden con la consulta de búsqueda o que se excluyen mediante una condición de intervalo de fechas no se incluyen en los resultados de la búsqueda. Para obtener más información acerca de los elementos no indexados, vea [Elementos parcialmente indizados.](partially-indexed-items-in-content-search.md)

- Puede obtener las estadísticas de retención más recientes haciendo clic en Actualizar **estadísticas** para volver a ejecutar una estimación de búsqueda que calcule el número actual de elementos en retención.

- Es normal que el número de elementos en retención aumente con el tiempo porque los usuarios cuyo buzón o sitio está en retención suelen enviar o recibir nuevos mensajes de correo electrónico y crear nuevos documentos en SharePoint y OneDrive.

- Si un buzón de Exchange, un sitio de SharePoint o una cuenta de OneDrive se mueven a una región diferente en un entorno multigeónico, las estadísticas de ese sitio no se incluirán en las estadísticas de retención. Sin embargo, el contenido de esas ubicaciones se conservará. Además, si un buzón o sitio se mueve a una región diferente, la dirección SMTP o la dirección URL que se muestra en la retención no se actualizará automáticamente. Tendrá que editar la retención y actualizar la dirección URL o SMTP para que las ubicaciones de contenido se incluyan de nuevo en las estadísticas de retención

## <a name="search-locations-on-ediscovery-hold"></a>Ubicaciones de búsqueda en retención de exhibición de documentos electrónicos

Al buscar [contenido](search-for-content-in-core-ediscovery.md) en un caso de exhibición de documentos electrónicos principal, puede configurar rápidamente la búsqueda para que solo busque en las ubicaciones de contenido que se han colocado en una retención asociada con el caso.

![Ubicaciones en espera](../media/d56398aa-0b20-4500-8e26-494eab92a99f.png)

Seleccione la **opción Ubicaciones en espera** para buscar en todas las ubicaciones de contenido que se han colocado en retención. Si el caso contiene varias retenciones de exhibición de documentos electrónicos, se buscarán las ubicaciones de contenido de todas las retenciones cuando seleccione esta opción. Además, si una ubicación de contenido se colocó en una retención basada en consulta, solo se buscarán los elementos que coincidan con la consulta de retención cuando ejecute la búsqueda. En otras palabras, solo se devuelve el contenido que coincide con los criterios de retención y de búsqueda con los resultados de la búsqueda. Por ejemplo, si un usuario se coloca en conservación de casos basada en consulta que conserva los elementos que se enviaron o crearon antes de una fecha específica, solo se buscarían esos elementos. Esto se logra conectando la consulta de retención de casos y la consulta de búsqueda mediante un **operador AND.**

Estas son algunas otras cosas que debe tener en cuenta al buscar ubicaciones en retención de exhibición de documentos electrónicos:

- Si una ubicación de contenido forma parte de varias retenciones dentro del mismo caso, los operadores **OR** combinan las consultas de retención cuando se busca en esa ubicación de contenido con la opción de contenido de todos los casos. De forma similar, si una ubicación de contenido forma parte de dos retenciones diferentes, donde una está basada en consultas y la otra es una retención infinita (donde todo el contenido se coloca en espera), todo el contenido se busca debido a la retención infinita.

- Si una búsqueda está configurada para buscar ubicaciones en espera y, a continuación, cambia una retención de exhibición de documentos electrónicos en caso de que (agregando o quitando una ubicación o cambiando una consulta de retención), la configuración de búsqueda se actualiza con esos cambios. Sin embargo, debe volver a ejecutar la búsqueda después de cambiar la retención para actualizar los resultados de la búsqueda.

- Si se colocan varias retenciones de exhibición de documentos electrónicos en una sola ubicación en un caso de eDiscovery y selecciona buscar ubicaciones en espera, el número máximo de palabras clave para esa consulta de búsqueda es 500. Esto se debe a que la búsqueda combina todas las retenciones basadas en consultas mediante el operador **OR.** Si hay más de 500 palabras clave en las consultas de retención combinadas y la consulta de búsqueda, se buscará todo el contenido del buzón, no solo el contenido que coincida con las retenciones de casos basadas en consultas.

- Si una retención de exhibición de documentos electrónicos tiene el estado De **activación,** puede buscar en las ubicaciones en espera mientras la retención está activada.

## <a name="preserve-content-in-microsoft-teams"></a>Conservar el contenido en Microsoft Teams

Las conversaciones que forman parte de un canal de Microsoft Teams se almacenan en el buzón asociado con Microsoft Team. Asimismo, los archivos que los miembros del equipo comparten en un canal se almacenan en el sitio de SharePoint del equipo. Por lo tanto, debe colocar el buzón de equipo y el sitio de SharePoint en conservación de exhibición de documentos electrónicos para conservar las conversaciones y los archivos en un canal.

Como alternativa, las conversaciones que forman parte de la lista de chat en Teams *(denominadas chats 1:1* o chats de grupo *1:N)* se almacenan en los buzones de los usuarios que participan en el chat. Además, los archivos que comparten los usuarios en conversaciones de chat se almacenan en la cuenta de OneDrive del usuario que comparte el archivo. Por lo tanto, tiene que agregar los buzones de usuario individuales y las cuentas de OneDrive a una retención de exhibición de documentos electrónicos para conservar las conversaciones y los archivos de la lista de chat. Es una buena idea colocar una retención en los buzones de los miembros de un equipo de Microsoft, además de poner el buzón de equipo y el sitio en retención.

> [!IMPORTANT]
> En una organización basada en la nube, los usuarios que participan en conversaciones que forman parte de la lista de chat en Teams deben tener un buzón de Exchange Online para conservar las conversaciones de chat cuando el buzón se coloca en una retención de exhibición de documentos electrónicos. Esto se debe a que las conversaciones que forman parte de la lista de chat se almacenan en los buzones basados en la nube de los participantes del chat. Si un participante de chat no tiene un buzón de Exchange Online, no podrá conservar esas conversaciones de chat. Por ejemplo, en una implementación híbrida de Exchange, los usuarios con un buzón local pueden participar en conversaciones que forman parte de la lista de chat en Teams. Pero en este caso, el contenido de estas conversaciones no se puede conservar porque estos usuarios no tienen buzones basados en la nube que se pueden colocar en retención.

Para obtener más información sobre cómo conservar el contenido de Teams, consulte Poner a un usuario o equipo de Microsoft Teams en [retención legal.](https://docs.microsoft.com/MicrosoftTeams/legal-hold)

### <a name="preserve-card-content"></a>Conservar el contenido de la tarjeta

Del mismo modo, el contenido de tarjetas generado por las aplicaciones en los canales de Teams, los chats 1:1 y los chats de grupo 1:N se almacena en buzones y se conserva cuando un buzón se coloca en una retención de exhibición de documentos electrónicos. Una *tarjeta* es un contenedor de IU para pequeños fragmentos de contenido. Las tarjetas pueden tener varias propiedades y datos adjuntos, y pueden incluir botones que desencadenan acciones de tarjeta. Para obtener más información, vea [Tarjetas](https://docs.microsoft.com/microsoftteams/platform/task-modules-and-cards/what-are-cards). Igual que el resto de contenido de Teams, el lugar donde se almacena el contenido de las tarjetas depende de dónde se haya usado. El contenido de tarjetas usado en un canal de Teams se almacena en el buzón del grupo de Teams. El contenido de tarjetas de los chats 1x1 y 1xN se almacena en los buzones de los participantes de los chats.

### <a name="preserve-meeting-and-call-information"></a>Conservar la información de reuniones y llamadas

La información de resumen de reuniones y llamadas en un canal de Teams también se almacena en los buzones de los usuarios que llamaron a la reunión o llamada. Este contenido también se conserva cuando se coloca una retención de exhibición de documentos electrónicos en los buzones de usuario.

### <a name="preserve-content-in-private-channels"></a>Conservar el contenido en canales privados

A partir de febrero de 2020, también hemos activado la capacidad de conservar el contenido en canales privados. Dado que los chats de canal privado se almacenan en los buzones de los participantes del chat, colocar un buzón de usuario en retención de exhibición de documentos electrónicos conservará los chats de canal privado. Además, si un buzón de usuario se colocó en una retención de exhibición de documentos electrónicos antes de febrero de 2020, la retención se aplicará automáticamente a los mensajes de canal privado almacenados en ese buzón. También se admite la conservación de archivos compartidos en canales privados.

### <a name="preserve-wiki-content"></a>Conservar el contenido wiki

Cada canal de equipo o equipo también contiene un sitio wiki para la toma de notas y la colaboración. El contenido de esta se guarda automáticamente en un archivo con un formato .mht. Este archivo se almacena en la biblioteca de documentos de Datos Wiki de Teams en el sitio de SharePoint del equipo. Puede conservar el contenido wiki agregando el sitio de SharePoint del equipo a una retención de exhibición de documentos electrónicos.

> [!NOTE]
> La capacidad de conservar el contenido wiki de un canal de equipo o equipo (cuando se coloca el sitio de SharePoint del equipo en espera) se publicó el 22 de junio de 2017. Si un sitio de grupo está en espera, el contenido wiki se conservará a partir de esa fecha. Sin embargo, si un sitio de grupo está en retención y el contenido wiki se eliminó antes del 22 de junio de 2017, el contenido wiki no se conserva.

### <a name="office-365-groups"></a>Grupos de Office 365

Teams se basa en Grupos de Office 365. Por lo tanto, colocar grupos de Office 365 en retención de exhibición de documentos electrónicos es similar colocar contenido de Teams en espera.

Tenga en cuenta lo siguiente al colocar teams y grupos de Office 365 en una retención de exhibición de documentos electrónicos:

- Como se ha explicado anteriormente, para poner contenido ubicado en Teams y Grupos de Office 365 en espera, debe especificar el buzón y el sitio de SharePoint asociados con un grupo o equipo.

- Ejecute el cmdlet **Get-UnifiedGroup en** [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) para ver las propiedades de Teams y Grupos de Office 365. Esta es una buena manera de obtener la dirección URL del sitio que está asociado a un equipo u grupo de Office 365. Por ejemplo, el comando siguiente muestra las propiedades seleccionadas de un grupo de Office365 denominado Senior Leadership Team:

    ```text
    Get-UnifiedGroup "Senior Leadership Team" | FL DisplayName,Alias,PrimarySmtpAddress,SharePointSiteUrl

    DisplayName            : Senior Leadership Team
    Alias                  : seniorleadershipteam
    PrimarySmtpAddress     : seniorleadershipteam@contoso.onmicrosoft.com
    SharePointSiteUrl      : https://contoso.sharepoint.com/sites/seniorleadershipteam
    ```

    > [!NOTE]
    > Para ejecutar el cmdlet **Get-UnifiedGroup** debe tener asignado el rol de destinatarios con permiso de vista en Exchange Online o ser un miembro de un grupo de roles que tenga asignado el rol de destinatarios con permiso de vista. 
  
- Cuando se busca en el buzón de un usuario, no se buscará en ningún equipo u grupo de Office 365 del que el usuario sea miembro. De forma similar, cuando se coloca un equipo u grupo de Office 365 en retención de exhibición de documentos electrónicos, solo el buzón de grupo y el sitio del grupo se colocan en retención. Los buzones y los sitios de OneDrive para la Empresa de los miembros del grupo no se colocan en retención a menos que los agregue explícitamente a la retención de exhibición de documentos electrónicos. Por lo tanto, si tiene que poner un equipo u grupo de Office 365 en retención por un motivo legal, considere la posibilidad de agregar los buzones y las cuentas de OneDrive de los miembros del equipo o grupo en la misma retención.

- Para obtener una lista de los miembros de un equipo u grupo de  Office 365, puede ver las propiedades en la página Grupos en el Centro de administración de Microsoft 365. Además, puede ejecutar el comando siguiente en PowerShell de Exchange Online:

    ```powershell
    Get-UnifiedGroupLinks <group or team name> -LinkType Members | FL DisplayName,PrimarySmtpAddress
    ```

    > [!NOTE]
    > Para ejecutar el cmdlet **Get-UnifiedGroupLinks** debe tener asignado el rol de destinatarios con permiso de vista en Exchange Online o ser un miembro de un grupo de roles que tenga asignado el rol de destinatarios con permiso de vista.

## <a name="preserve-content-in-onedrive-accounts"></a>Conservar el contenido de las cuentas de OneDrive

Para recopilar una lista de las direcciones URL de los sitios de OneDrive para la Empresa de su organización para que pueda agregarlas a una retención o búsqueda asociada a un caso de exhibición de documentos electrónicos, vea Crear una lista de todas las ubicaciones de [OneDrive](https://docs.microsoft.com/onedrive/list-onedrive-urls)en su organización. El script de este artículo crea un archivo de texto que contiene una lista de todos los sitios de OneDrive de su organización. Para ejecutar este script, tiene que instalar y usar el Shell de SharePoint Online Management. Asegúrese de anexar la dirección URL para el dominio MiSitio de su organización a cada sitio de OneDrive que quiera buscar. Este es el dominio que contiene todos los sitios OneDrive; por ejemplo, `https://contoso-my.sharepoint.com`. Este es un ejemplo de una dirección URL para un sitio de usuario de OneDrive: `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft.com`.

> [!IMPORTANT]
> La dirección URL de la cuenta de OneDrive de un usuario incluye su nombre principal de usuario (UPN) (por ejemplo, `https://alpinehouse-my.sharepoint.com/personal/sarad_alpinehouse_onmicrosoft_com` ). En el caso poco frecuente de que se cambie el UPN de una persona, la dirección URL de OneDrive también cambiará para incorporar el nuevo UPN. Si la cuenta de OneDrive de un usuario forma parte de una retención de exhibición de documentos electrónicos, la antigua y su UPN se cambia, debe actualizar la retención y tendrá que actualizar la retención y agregar la nueva dirección URL de OneDrive del usuario y quitar la antigua. Para más información, consulte [Cómo afectan los cambios de UPN a la dirección URL de OneDrive](https://docs.microsoft.com/onedrive/upn-changes).

## <a name="removing-content-locations-from-an-ediscovery-hold"></a>Quitar ubicaciones de contenido de una retención de exhibición de documentos electrónicos

Después de quitar un buzón, un sitio de SharePoint o una cuenta de OneDrive de una retención de exhibición de documentos electrónicos, se aplica *una* retención retrasada. Esto significa que la eliminación real de la retención se retrasa durante 30 días para evitar que los datos se eliminen permanentemente (se purguen) de una ubicación de contenido. Esto ofrece a los administradores la oportunidad de buscar o recuperar contenido que se purgará después de quitar una retención de exhibición de documentos electrónicos. Los detalles de cómo funciona la retención con retraso para buzones y sitios son diferentes.

- **Buzones:** Se coloca una retención retrasada en un buzón la próxima vez que el Asistente para carpetas administradas procesa el buzón y detecta que se quitó una retención de exhibición de documentos electrónicos. En concreto, se aplica una retención retrasada a un buzón cuando el Asistente para carpeta administrada establece una de las siguientes propiedades de buzón en **True:**

   - **DelayHoldApplied:** Esta propiedad se aplica al contenido relacionado con el correo electrónico (generado por personas que usan Outlook y Outlook en la Web) que se almacena en el buzón de un usuario.

   - **DelayReleaseHoldApplied:** Esta propiedad se aplica al contenido basado en la nube (generado por aplicaciones que no son de Outlook, como Microsoft Teams, Microsoft Forms y Microsoft Yammer) que se almacena en el buzón de un usuario. Los datos en la nube generados por una aplicación de Microsoft normalmente se almacenan en una carpeta oculta en el buzón de un usuario.

   Cuando se coloca una retención retrasada en el buzón (cuando cualquiera de las propiedades anteriores se establece en **True**), el buzón aún se considera que está en suspensión durante una duración de retención ilimitada, como si el buzón se encontrara en retención por juicio. Después de 30 días, la retención por retraso expira y Microsoft 365 intentará quitar automáticamente la retención de retraso (estableciendo la propiedad DelayHoldApplied o DelayReleaseHoldApplied en **False)** para que se quite la retención. Después de establecer cualquiera de estas propiedades en **False**, los elementos correspondientes marcados para su eliminación se purgan la próxima vez que el Asistente para carpeta administrada procese el buzón.

   Para obtener más información, consulte [Gestionar buzón con una retención de retraso](identify-a-hold-on-an-exchange-online-mailbox.md#managing-mailboxes-on-delay-hold).

- **Sitios de SharePoint y OneDrive:** Cualquier contenido de SharePoint o OneDrive que se retenga en la biblioteca de conservación de documentos no se elimina durante el período de retención de retraso de 30 días después de quitar un sitio de una retención de exhibición de documentos electrónicos. Esto es similar a lo que sucede cuando se libera un sitio de una directiva de retención. Además, no puede eliminar manualmente este contenido en la biblioteca de conservación de documentos durante el período de retención con retraso de 30 días. 

   Para obtener más información, [vea Liberar una directiva para retención.](retention.md#releasing-a-policy-for-retention)

También se aplica una retención retrasada a las ubicaciones de contenido en espera cuando se cierra un caso de eDiscovery principal porque las retenciones se desactivarán cuando se cierre un caso. Para obtener más información acerca de cómo cerrar un caso, vea Cerrar, volver a abrir y eliminar un caso de [eDiscovery principal.](close-reopen-delete-core-ediscovery-cases.md)

## <a name="ediscovery-hold-limits"></a>Límites de retención de eDiscovery

En la tabla siguiente se enumeran los límites para casos de eDiscovery y retenciones de casos.

  | Descripción del límite | Límite |
  |:-----|:-----|
  |Número máximo de casos para una organización  <br/> |Sin límite  <br/> |
  |Número máximo de retenciones de exhibición de documentos electrónicos para una organización  <br/> |10 000  <br/> |
  |Número máximo de buzones en una única retención de exhibición de documentos electrónicos  <br/> |1,000  <br/> |
  |Número máximo de sitios de SharePoint y OneDrive para la Empresa en una única retención de exhibición de documentos electrónicos  <br/> |100  <br/> |
  |Número máximo de casos que se muestran en la página principal de exhibición de documentos electrónicos y el número máximo de elementos que se muestran en las pestañas Retenciones, Búsquedas y Exportación dentro de un caso. <sup>1</sup> |1,000|
  |||

   > [!NOTE]
   > <sup>1</sup> Para ver una lista de más de 1.000 casos, retenciones, búsquedas o exportaciones, puede usar el cmdlet de PowerShell de seguridad y cumplimiento de Office 36 & 5 correspondiente:
   >
   > - [Get-ComplianceCase](https://docs.microsoft.com/powershell/module/exchange/get-compliancecase)
   > - [Get-CaseHoldPolicy](https://docs.microsoft.com/powershell/module/exchange/get-caseholdpolicy)
   > - [Get-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch)
   > - [Get-ComplianceSearchAction](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction)
