---
title: Crear retenciones de exhibición de documentos electrónicos en un caso de exhibición de documentos electrónicos principal
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
ms.custom: admindeeplinkMAC
search.appverid:
- MOE150
- MET150
description: Puede crear una retención asociada a un caso de exhibición de documentos electrónicos principal en Microsoft 365 para conservar el contenido relevante para una investigación o un caso legal.
ms.openlocfilehash: 57e825822ac622d224a402d677d4951ad9fa444a
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/12/2021
ms.locfileid: "59165931"
---
# <a name="create-an-ediscovery-hold"></a>Crear un caso de retención de eDiscovery

Puede usar un caso de exhibición de documentos electrónicos principal para crear retenciones para conservar contenido que pueda ser relevante para el caso. Puede colocar una retención en los buzones Exchange de correo y OneDrive para la Empresa de las personas que está investigando en el caso. También puede colocar una retención en los buzones y sitios asociados con Microsoft Teams, Office 365 grupos y Yammer grupos. Al poner las ubicaciones de contenido en espera, el contenido se conserva hasta que quita la ubicación de contenido de la retención o hasta que elimina la retención.

Después de crear una retención de exhibición de documentos electrónicos, la retención puede tardar hasta 24 horas en tener efecto.

Al crear una retención, tiene las siguientes opciones para tener en cuenta el contenido que se conserva en las ubicaciones de contenido especificadas:
  
- Cree una retención infinita donde todo el contenido de las ubicaciones especificadas esté en espera. Como alternativa, puede crear una retención basada en consultas donde solo se mantenga en espera el contenido de las ubicaciones especificadas que coincidan con una consulta de búsqueda.

- Especifique un intervalo de fechas para conservar solo el contenido que se envió, recibió o creó dentro de ese intervalo de fechas. Como alternativa, puede contener todo el contenido en ubicaciones especificadas independientemente de cuándo se envió, recibió o creó.
  
## <a name="how-to-create-an-ediscovery-hold"></a>Cómo crear una retención de exhibición de documentos electrónicos

Para crear una retención de exhibición de documentos electrónicos asociada a un caso de exhibición de documentos electrónicos principal:
  
1. Vaya a <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">Centro de cumplimiento de Microsoft 365</a> e inicie sesión con las credenciales de la cuenta de usuario a la que se han asignado los permisos de exhibición de documentos electrónicos adecuados.

2. En el panel de navegación izquierdo, haga clic **en Mostrar todo** y, a continuación, haga clic en **Exhibición de documentos electrónicos > Core**.

3. En la **página Exhibición de documentos electrónicos** principal, haga clic en el nombre del caso en el que desea crear la retención.

4. En la **página principal** del caso, haga clic en la **pestaña** Retención.
  
5. En la **página Retención,** haga clic **en Crear**.

6. En la **página Nombre del** asistente para retención, asigne a la retención un nombre y agregue una descripción opcional y, a continuación, haga clic en **Siguiente**. El nombre de la suspensión debe ser exclusivo en la organización.

7. En la **página Asistente** para elegir ubicaciones, elija las ubicaciones de contenido que desea poner en espera. Puede retener buzones, sitios y carpetas públicas.

    ![Elegir las ubicaciones de contenido para colocar en suspensión.](../media/eDiscoveryHoldLocations.png)
  
   1. **Buzones de Exchange**: establezca el botón de alternancia en **Activado** y después haga clic en **Elegir usuarios, grupos o equipos** para especificar los buzones para colocar en suspensión. Use el cuadro de búsqueda para encontrar buzones de usuario y grupos de distribución (para colocar una suspensión en los buzones de miembros de grupo) para suspenderlos. También puede colocar una retención en el buzón asociado para un grupo de Microsoft, Office 365 grupo y Yammer grupo. Para obtener más información acerca de los datos de la aplicación que se conservan cuando se coloca un buzón en espera, vea Contenido almacenado en buzones [para exhibición de](what-is-stored-in-exo-mailbox.md)documentos electrónicos.

   2. **Sitios de SharePoint**: establezca el botón de alternancia en **Activado** y haga clic en **Elegir sitios** para especificar los sitios de SharePoint y las cuentas de OneDrive que se deben colocar en suspensión. Escriba la dirección URL de cada sitio que quiere colocar en suspensión. También puede agregar la dirección URL del sitio SharePoint para un grupo de Microsoft, Office 365 grupo o un Yammer grupo.
  
   3. **Carpetas públicas de Exchange**: establezca la opción de alternancia en **Activado** para poner todas las carpetas públicas en su organización de Exchange Online en suspensión. No puede elegir carpetas públicas específicas para poner en suspensión. Deje el botón de alternancia desactivado si no quiere establecer una suspensión en las carpetas públicas.

   > [!NOTE]
   > Debe agregar al menos una ubicación de contenido a la retención. De lo contrario, las estadísticas de retención de exhibición de documentos electrónicos mostrarán que no hay elementos en espera.

8. Cuando haya terminado de agregar ubicaciones a la retención, haga clic en **Siguiente**.

9. Para crear una retención basada en consultas con palabras clave o condiciones, siga estos pasos. Para conservar todo el contenido en las ubicaciones de contenido especificadas, haga clic en **Siguiente**.

    ![Cree una retención basada en consultas con palabras clave y condiciones.](../media/eDiscoveryHoldQuery.png)
  
    1. En el cuadro palabras **clave**, escriba una consulta para conservar solo el contenido que coincida con los criterios de consulta. Puede especificar palabras clave, propiedades de mensaje de correo electrónico o propiedades de sitio, como nombres de archivo. También puede usar consultas más complejas que usen un operador booleano, como **AND**, **OR** o **NOT**.

    2. Haga **clic en Agregar condición** para agregar una o más condiciones para restringir la consulta para la retención. Cada condición agrega una cláusula a la consulta de búsqueda KQL que se crea y se ejecuta al crear la retención. Por ejemplo, puede especificar un intervalo de fechas para que se conserven los documentos de correo electrónico o de sitio que se crearon dentro del intervalo de fechas. Una condición está conectada lógicamente a la consulta de palabras clave (especificada en el cuadro Palabras clave) y **otras** condiciones por el **operador AND.** Esto significa que los elementos deben satisfacer tanto la consulta de palabras clave como la condición que se va a conservar.

    Para obtener más información acerca de cómo crear una consulta de búsqueda y usar condiciones, vea Consultas de palabras clave y [condiciones de búsqueda para eDiscovery](keyword-queries-and-search-conditions.md).

10. Después de configurar una retención basada en consultas, haga clic en **Siguiente**.

11. Revise la configuración (y edite si es necesario) y, a continuación, haga clic en **Enviar**.

## <a name="query-based-holds-placed-on-sites"></a>Retenciones basadas en consultas colocadas en sitios

Tenga en cuenta lo siguiente al colocar una retención de exhibición de documentos electrónicos basada en consultas en documentos ubicados en SharePoint sitios:

- Una retención basada en consultas conserva inicialmente todos los documentos de un sitio durante un breve período de tiempo después de su eliminación. Esto significa que cuando se elimina un documento, se mueve a la biblioteca de conservación de conservación incluso si no coincide con los criterios de la retención basada en consultas. Sin embargo, un trabajo del temporizador que procesa la biblioteca de conservación quitará los documentos eliminados que no coincidan con una retención basada en consultas. El trabajo del temporizador se ejecuta periódicamente y compara todos los documentos de la biblioteca de conservación con las retenciones de exhibición de documentos electrónicos basadas en consultas (y otros tipos de retenciones y directivas de retención). El trabajo del temporizador elimina los documentos que no coinciden con una retención basada en consultas y conserva los documentos que sí.

- Las retenciones basadas en consultas no deben usarse para realizar la conservación dirigida, como conservar documentos en una carpeta o sitio específicos o mediante otros criterios de retención basados en la ubicación. Si lo hace, puede que tenga resultados no deseados. Se recomienda usar criterios de retención no basados en la ubicación, como palabras clave, intervalos de fechas u otras propiedades de documento para conservar los documentos del sitio.

## <a name="ediscovery-hold-statistics"></a>Estadísticas de retención de eDiscovery

Después de crear una retención de exhibición de documentos electrónicos, se muestra información sobre la nueva retención en la página desplegable de la retención seleccionada. Esta información incluye el número de buzones y sitios en espera y estadísticas sobre el contenido que se colocó en espera, como el número total y el tamaño de los elementos puestos en espera y la última vez que se calcularon las estadísticas de retención. Estas estadísticas de retención le ayudan a identificar la cantidad de contenido relacionado con el caso que se está conservando.
  
![Mantener las estadísticas.](../media/eDiscoveryHoldStatistics.png)
  
Tenga en cuenta lo siguiente sobre las estadísticas de retención de exhibición de documentos electrónicos:
  
- El número total de elementos en espera indica el número de elementos de todos los orígenes de contenido que están en espera. Si ha creado una retención basada en consultas, esta estadística indica el número de elementos que coinciden con la consulta.

- El número de elementos en espera también incluye elementos no indexados que se encuentran en las ubicaciones de contenido. Si crea una retención basada en consultas, todos los elementos no indexados de las ubicaciones de contenido se colocan en espera. Esto incluye elementos sin indizar que no coinciden con los criterios de búsqueda de una retención basada en consultas y elementos sin indizar que podrían estar fuera de una condición de intervalo de fechas. Esto es diferente de lo que sucede al ejecutar una búsqueda, en la que los elementos no indexados que no coinciden con la consulta de búsqueda o que se excluyen por una condición de intervalo de fechas no se incluyen en los resultados de la búsqueda. Para obtener más información acerca de los elementos sin indizar, [vea Elementos parcialmente indizados](partially-indexed-items-in-content-search.md).

- Puede obtener las estadísticas de retención más recientes haciendo clic en Actualizar **estadísticas** para volver a ejecutar una estimación de búsqueda que calcule el número actual de elementos en espera.

- Es normal que el número de elementos en espera aumente con el tiempo porque los usuarios cuyo buzón o sitio están en espera suelen enviar o recibir un nuevo mensaje de correo electrónico y crear nuevos documentos en SharePoint y OneDrive.

- Si un buzón de Exchange, un sitio SharePoint o una cuenta de OneDrive se mueven a una región diferente en un entorno multige geográfico, las estadísticas de ese sitio no se incluirán en las estadísticas de retención. Pero el contenido de esas ubicaciones seguirá conservandose. Además, si un buzón o sitio se mueve a una región diferente, la dirección SMTP o la dirección URL que se muestra en la retención no se actualizarán automáticamente. Tendrás que editar la retención y actualizar la dirección URL o SMTP para que las ubicaciones de contenido se incluyan una vez más en las estadísticas de retención

## <a name="search-locations-on-ediscovery-hold"></a>Ubicaciones de búsqueda en retención de exhibición de documentos electrónicos

Al buscar [contenido en](search-for-content-in-core-ediscovery.md) un caso de exhibición de documentos electrónicos principal, puede configurar rápidamente la búsqueda para que solo busque las ubicaciones de contenido que se han colocado en una retención asociada al caso.

Seleccione la **opción Ubicaciones en espera** para buscar en todas las ubicaciones de contenido que se han colocado en espera. Si el caso contiene varias retenciones de exhibición de documentos electrónicos, se buscarán las ubicaciones de contenido de todas las retenciones cuando seleccione esta opción. Además, si se colocó una ubicación de contenido en una retención basada en consulta, solo se buscarán los elementos que coincidan con la consulta de retención al ejecutar la búsqueda. En otras palabras, solo se devuelve el contenido que coincide con los criterios de retención y los criterios de búsqueda con los resultados de la búsqueda. Por ejemplo, si un usuario se colocó en una retención de casos basada en consulta que conserva elementos que se enviaron o crearon antes de una fecha específica, solo se buscarían esos elementos. Esto se logra conectando la consulta de retención de casos y la consulta de búsqueda mediante un **operador AND.**

Estas son algunas otras cosas que debe tener en cuenta al buscar ubicaciones en retención de exhibición de documentos electrónicos:

- Si una ubicación de contenido forma parte de varias retenciones dentro del mismo caso, los operadores **OR** combinan las consultas de retención cuando se busca en esa ubicación de contenido con la opción de contenido de todos los casos. Del mismo modo, si una ubicación de contenido forma parte de dos retenciones diferentes, donde una está basada en consultas y la otra es una retención infinita (donde todo el contenido está en espera), todo el contenido se busca debido a la retención infinita.

- Si una búsqueda está configurada para buscar ubicaciones en espera y, a continuación, cambia una retención de exhibición de documentos electrónicos en el caso (agregando o quitando una ubicación o cambiando una consulta de retención), la configuración de búsqueda se actualiza con esos cambios. Sin embargo, debe volver a ejecutar la búsqueda después de cambiar la retención para actualizar los resultados de la búsqueda.

- Si se colocan varias retenciones de exhibición de documentos electrónicos en una sola ubicación en un caso de exhibición de documentos electrónicos y selecciona buscar ubicaciones en espera, el número máximo de palabras clave para esa consulta de búsqueda es 500. Esto se debe a que la búsqueda combina todas las retenciones basadas en consultas mediante el operador **OR.** Si hay más de 500 palabras clave en las consultas de retención combinadas y la consulta de búsqueda, se busca todo el contenido del buzón, no solo el contenido que coincide con las retenciones de casos basadas en consultas.

- Si una retención de exhibición de documentos electrónicos tiene el estado **Activado (pendiente),** puede buscar en las ubicaciones en espera mientras se está activada la retención.

## <a name="preserve-content-in-microsoft-teams"></a>Conservar contenido en Microsoft Teams

Las conversaciones que forman parte de un canal Microsoft Teams se almacenan en el buzón asociado al equipo de Microsoft. Asimismo, los archivos que los miembros del equipo comparten en un canal se almacenan en el sitio de SharePoint del equipo. Por lo tanto, debe colocar el buzón de equipo y SharePoint sitio en retención de exhibición de documentos electrónicos para conservar conversaciones y archivos en un canal.

Como alternativa, las conversaciones que forman parte de la lista chat de Teams (llamadas *chats 1:1* o chats de grupo *1:N)* se almacenan en los buzones de los usuarios que participan en el chat. Y los archivos que los usuarios comparten en conversaciones de chat se almacenan en OneDrive cuenta del usuario que comparte el archivo. Por lo tanto, debe agregar los buzones de usuario individuales y las OneDrive a una retención de exhibición de documentos electrónicos para conservar conversaciones y archivos en la lista de chat. Es una buena idea colocar una retención en los buzones de los miembros de un equipo de Microsoft, además de poner el buzón de equipo y el sitio en espera.

> [!NOTE]
> Si su organización tiene una implementación híbrida de Exchange (o su organización sincroniza una organización de Exchange local con Office 365) y ha habilitado Microsoft Teams, los usuarios locales pueden usar la aplicación de chat de Teams y participar en chats 1:1 y chats de grupo 1:N. Estas conversaciones se almacenan en almacenamiento basado en la nube que está asociado con un usuario local. Si un usuario local se coloca en una retención de exhibición de documentos electrónicos, se conservará el Teams de chat en el almacenamiento basado en la nube. Para más información, consulte [Buscar los datos de chat de Teams de usuarios locales](search-cloud-based-mailboxes-for-on-premises-users.md).

Para obtener más información acerca de cómo conservar Teams contenido, vea [Colocar un Microsoft Teams usuario o](/MicrosoftTeams/legal-hold)equipo en retención legal .

### <a name="preserve-card-content"></a>Conservar el contenido de la tarjeta

Del mismo modo, el contenido de tarjeta generado por las aplicaciones en canales de Teams, chats 1:1 y chats de grupo 1:N se almacena en buzones y se conserva cuando un buzón se coloca en una retención de exhibición de documentos electrónicos. Una *tarjeta* es un contenedor de IU para pequeños fragmentos de contenido. Las tarjetas pueden tener varias propiedades y datos adjuntos, y pueden incluir botones que desencadenan acciones de tarjeta. Para obtener más información, vea [Tarjetas](/microsoftteams/platform/task-modules-and-cards/what-are-cards). Igual que el resto de contenido de Teams, el lugar donde se almacena el contenido de las tarjetas depende de dónde se haya usado. El contenido de tarjetas usado en un canal de Teams se almacena en el buzón del grupo de Teams. El contenido de tarjetas de los chats 1x1 y 1xN se almacena en los buzones de los participantes de los chats.

### <a name="preserve-meeting-and-call-information"></a>Conservar información de reuniones y llamadas

La información de resumen de reuniones y llamadas en un canal de Teams también se almacena en los buzones de los usuarios que marcaron en la reunión o llamada. Este contenido también se conserva cuando se coloca una retención de exhibición de documentos electrónicos en los buzones de usuario.

### <a name="preserve-content-in-private-channels"></a>Conservar contenido en canales privados

A partir de febrero de 2020, también hemos activado la capacidad de conservar contenido en canales privados. Dado que los chats de canal privado se almacenan en los buzones de los participantes de chat, colocar un buzón de usuario en retención de exhibición de documentos electrónicos conservará los chats de canal privado. Además, si un buzón de usuario se colocó en una retención de exhibición de documentos electrónicos antes de febrero de 2020, la retención se aplicará automáticamente a los mensajes de canal privado almacenados en ese buzón. También se admite la conservación de archivos compartidos en canales privados.

### <a name="preserve-wiki-content"></a>Conservar contenido wiki

Cada canal de equipo o equipo también contiene un wiki para la toma de notas y la colaboración. El contenido de esta se guarda automáticamente en un archivo con un formato .mht. Este archivo se almacena en la biblioteca de documentos de Datos Wiki de Teams en el sitio de SharePoint del equipo. Puede conservar el contenido wiki agregando el sitio SharePoint del equipo a una retención de exhibición de documentos electrónicos.

> [!NOTE]
> La capacidad de conservar el contenido wiki de un canal de equipo o equipo (cuando se coloca el sitio SharePoint del equipo en espera) se publicó el 22 de junio de 2017. Si un sitio de grupo está en espera, el contenido wiki se conservará a partir de esa fecha. Sin embargo, si un sitio de grupo está en espera y el contenido wiki se eliminó antes del 22 de junio de 2017, el contenido wiki no se conserva.

### <a name="office-365-groups"></a>Grupos de Office 365

Teams se basa en Office 365 grupos. Por lo tanto, colocar Office 365 en retención de exhibición de documentos electrónicos es similar Teams contenido en espera.

Tenga en cuenta lo siguiente al colocar grupos Teams y Office 365 en una retención de exhibición de documentos electrónicos:

- Como se explicó anteriormente, para poner contenido ubicado en grupos de Teams y Office 365 en espera, debe especificar el buzón y el sitio SharePoint asociados con un grupo o equipo.

- Ejecute el cmdlet **Get-UnifiedGroup** en [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) para ver las propiedades de Teams y Office 365 grupos. Esta es una buena forma de obtener la dirección URL del sitio que está asociado con un grupo de Office 365 grupo. Por ejemplo, el comando siguiente muestra las propiedades seleccionadas de un grupo de Office365 denominado Senior Leadership Team:

    ```text
    Get-UnifiedGroup "Senior Leadership Team" | FL DisplayName,Alias,PrimarySmtpAddress,SharePointSiteUrl

    DisplayName            : Senior Leadership Team
    Alias                  : seniorleadershipteam
    PrimarySmtpAddress     : seniorleadershipteam@contoso.onmicrosoft.com
    SharePointSiteUrl      : https://contoso.sharepoint.com/sites/seniorleadershipteam
    ```

    > [!NOTE]
    > Para ejecutar el cmdlet **Get-UnifiedGroup** debe tener asignado el rol de destinatarios con permiso de vista en Exchange Online o ser un miembro de un grupo de roles que tenga asignado el rol de destinatarios con permiso de vista. 
  
- Cuando se busca en el buzón de un usuario, no se buscará en ningún grupo o grupo de Office 365 del que el usuario sea miembro. Del mismo modo, cuando se coloca un grupo o un grupo Office 365 en retención de exhibición de documentos electrónicos, solo el buzón de grupo y el sitio de grupo se colocan en espera. Los buzones y OneDrive para la Empresa de los miembros del grupo no se ponen en espera a menos que los agregue explícitamente a la retención de exhibición de documentos electrónicos. Por lo tanto, si tiene que poner un grupo o un grupo de Office 365 en espera por un motivo legal, considere la posibilidad de agregar los buzones y las cuentas OneDrive de los miembros del equipo o grupo en la misma retención.

- Para obtener una lista de los miembros de un grupo o grupo <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank"></a> de Office 365, puede ver las propiedades en la página Grupos en el Centro de administración de Microsoft 365. Además, puede ejecutar el comando siguiente en PowerShell de Exchange Online:

    ```powershell
    Get-UnifiedGroupLinks <group or team name> -LinkType Members | FL DisplayName,PrimarySmtpAddress
    ```

    > [!NOTE]
    > Para ejecutar el cmdlet **Get-UnifiedGroupLinks** debe tener asignado el rol de destinatarios con permiso de vista en Exchange Online o ser un miembro de un grupo de roles que tenga asignado el rol de destinatarios con permiso de vista.

## <a name="preserve-content-in-onedrive-accounts"></a>Conservar contenido en OneDrive cuentas

Para recopilar una lista de las direcciones URL de los sitios de OneDrive para la Empresa de la organización para que pueda agregarlas a una retención o búsqueda asociada a un caso de exhibición de documentos electrónicos, vea [Create a list of all OneDrive locations in your organization](/onedrive/list-onedrive-urls). El script de este artículo crea un archivo de texto que contiene una lista de todos los OneDrive de la organización. Para ejecutar este script, tiene que instalar y usar el Shell de SharePoint Online Management. Asegúrese de anexar la dirección URL para el dominio MiSitio de su organización a cada sitio de OneDrive que quiera buscar. Este es el dominio que contiene todos los sitios OneDrive; por ejemplo, `https://contoso-my.sharepoint.com`. Este es un ejemplo de una dirección URL para un sitio de usuario de OneDrive: `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft.com`.

> [!IMPORTANT]
> La dirección URL de la cuenta OneDrive usuario incluye su nombre principal de usuario (UPN) (por ejemplo, `https://alpinehouse-my.sharepoint.com/personal/sarad_alpinehouse_onmicrosoft_com` ). En el caso poco frecuente de que se cambie el UPN de una persona, su dirección URL OneDrive también cambiará para incorporar el nuevo UPN. Si la cuenta de OneDrive de un usuario forma parte de una retención de exhibición de documentos electrónicos, antigua y su UPN cambia, deberá actualizar la retención y deberá actualizar la retención y agregar la nueva dirección URL de OneDrive del usuario y quitar la anterior. Para más información, consulte [Cómo afectan los cambios de UPN a la dirección URL de OneDrive](/onedrive/upn-changes).

## <a name="removing-content-locations-from-an-ediscovery-hold"></a>Quitar ubicaciones de contenido de una retención de exhibición de documentos electrónicos

Después de quitar SharePoint buzón, sitio o OneDrive de una retención de exhibición de documentos electrónicos, se aplica *una* retención de retraso. Esto significa que la eliminación real de la retención se retrasa durante 30 días para evitar que los datos se eliminen permanentemente (se purguen) de una ubicación de contenido. Esto ofrece a los administradores la oportunidad de buscar o recuperar contenido que se purgará después de quitar una retención de exhibición de documentos electrónicos. Los detalles de cómo funciona la retención retrasada para buzones y sitios son diferentes.

- **Buzones:** La próxima vez que el Asistente para carpetas administradas procese el buzón y detecte que se quitó una retención de exhibición de documentos electrónicos, se coloca una retención de retraso en un buzón. En concreto, se aplica una retención de retraso a un buzón cuando el Asistente para carpetas administradas establece una de las siguientes propiedades de buzón en **True**:

   - **DelayHoldApplied:** Esta propiedad se aplica al contenido relacionado con el correo electrónico (generado por personas que usan Outlook y Outlook en la Web) que se almacena en el buzón de un usuario.

   - **DelayReleaseHoldApplied:** Esta propiedad se aplica al contenido basado en la nube (generado por aplicaciones que no son de Outlook, como Microsoft Teams, Microsoft Forms y Microsoft Yammer) que se almacena en el buzón de un usuario. Los datos en la nube generados por una aplicación microsoft normalmente se almacenan en una carpeta oculta en el buzón de un usuario.

   Cuando se coloca una retención de retraso en el buzón (cuando cualquiera de las propiedades anteriores se establece en **True),** el buzón se considera aún en espera durante una duración de retención ilimitada, como si el buzón se encontraba en retención por juicio. Después de 30 días, la retención de retraso expira y Microsoft 365 intentará quitar automáticamente la retención de retraso (estableciendo la propiedad DelayHoldApplied o DelayReleaseHoldApplied en **False)** para que se quite la retención. Después de establecer cualquiera de estas propiedades en **False**, los elementos correspondientes marcados para la eliminación se purgan la próxima vez que el Asistente para carpetas administradas procese el buzón.

   Para obtener más información, consulte [Gestionar buzón con una retención de retraso](identify-a-hold-on-an-exchange-online-mailbox.md#managing-mailboxes-on-delay-hold).

- **SharePoint y OneDrive web:** Cualquier SharePoint o OneDrive contenido que se conserva en la biblioteca de conservación no se elimina durante el período de retención de retraso de 30 días después de quitar un sitio de una retención de exhibición de documentos electrónicos. Esto es similar a lo que sucede cuando un sitio se libera de una directiva de retención. Además, no puedes eliminar manualmente este contenido en la biblioteca de conservación durante el período de retención de retraso de 30 días. 

   Para obtener más información, [vea Releasing a policy for retention](retention.md#releasing-a-policy-for-retention).

También se aplica una retención de retraso a las ubicaciones de contenido en espera cuando se cierra un caso de exhibición de documentos electrónicos principal porque las retenciones se apagan cuando se cierra un caso. Para obtener más información acerca del cierre de un caso, vea [Close, reopen, and delete a Core eDiscovery case](close-reopen-delete-core-ediscovery-cases.md).

## <a name="ediscovery-hold-limits"></a>Límites de retención de eDiscovery

En la tabla siguiente se enumeran los límites para los casos de exhibición de documentos electrónicos y las retenciones de casos.

  | Descripción del límite | Límite |
  |:-----|:-----|
  |Número máximo de casos para una organización.  <br/> |Sin límite  <br/> |
  |Número máximo de retenciones de exhibición de documentos electrónicos para una organización.  <br/> |10,000  <br/> |
  |Número máximo de buzones en una única retención de exhibición de documentos electrónicos. Este límite incluye el total combinado de buzones de usuario y los buzones asociados con grupos de Microsoft 365, Microsoft Teams y Yammer grupos.  <br/> |1,000  <br/> |
  |Número máximo de sitios en una única retención de exhibición de documentos electrónicos. Este límite incluye el total combinado de sitios OneDrive para la Empresa, SharePoint y los sitios asociados con grupos de Microsoft 365, Microsoft Teams y Yammer grupos.  <br/> |100  <br/> |
  |Número máximo de casos que se muestran en la página principal de exhibición de documentos electrónicos y el número máximo de elementos que se muestran en las pestañas Retenciones, Búsquedas y Exportación dentro de un caso. <sup>1</sup> |1,000|
  |||

   > [!NOTE]
   > <sup>1</sup> Para ver una lista de más de 1.000 casos, retenciones, búsquedas o exportaciones, puede usar el cmdlet de PowerShell de Office 365 seguridad & cumplimiento correspondiente:
   >
   > - [Get-ComplianceCase](/powershell/module/exchange/get-compliancecase)
   > - [Get-CaseHoldPolicy](/powershell/module/exchange/get-caseholdpolicy)
   > - [Get-ComplianceSearch](/powershell/module/exchange/get-compliancesearch)
   > - [Get-ComplianceSearchAction](/powershell/module/exchange/get-compliancesearchaction)
