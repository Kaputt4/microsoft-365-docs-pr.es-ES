---
title: Busque y elimine mensajes de chat en Teams
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 3526fd06-b45f-445b-aed4-5ebd37b3762a
description: Use eDiscovery (Premium) y el Explorador de Microsoft Graph para buscar y purgar mensajes de chat en Microsoft Teams y responder a incidentes de desbordamiento de datos en Teams.
ms.openlocfilehash: c2202c45cc5e3caaa0af429439d44b1dfed3ac86
ms.sourcegitcommit: 4cd8be7c22d29100478dce225dce3bcdce52644d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/10/2022
ms.locfileid: "65302077"
---
# <a name="search-and-purge-chat-messages-in-teams-preview"></a>Buscar y purgar mensajes de chat en Teams (versión preliminar)

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

Puede usar eDiscovery (Premium) y el Explorador de Microsoft Graph para buscar y eliminar mensajes de chat en Microsoft Teams. Esto puede ayudarle a encontrar y quitar información confidencial o contenido inadecuado. Este flujo de trabajo de búsqueda y purga también le ayudará a responder a un incidente de derrame de datos, cuando el contenido que contiene información confidencial o malintencionada se publica a través de Teams mensajes de chat.

> [!NOTE]
> Este artículo se aplica a las organizaciones Microsoft 365 Enterprise. El soporte técnico para la nube del Gobierno de EE. UU. (incluidos GCC, GCC High y DoD) estará disponible próximamente.

## <a name="before-you-search-and-purge-chat-messages"></a>Antes de buscar y purgar mensajes de chat

- Para crear un caso de eDiscovery (Premium) y usar colecciones para buscar mensajes de chat, debe ser miembro del grupo de roles administrador de **eDiscovery** en el portal de cumplimiento de Microsoft Purview. Para eliminar mensajes de chat, debe tener asignado el rol **Buscar y purgar** . Este rol se asigna a los grupos de roles Investigador de datos y Administración de la organización de forma predeterminada. Para más información, consulte [Asignar permisos de eDiscovery](assign-ediscovery-permissions.md).
- La búsqueda y purga se admiten para las conversaciones dentro del inquilino. La compatibilidad con las conversaciones de Teams Conectar Chat (acceso externo o federación) está habilitada en la interfaz en algunos casos, pero no funciona según lo previsto.
- Se puede eliminar un máximo de 10 elementos por buzón a la vez. Dado que la capacidad de buscar y quitar mensajes de chat está pensada para ser una herramienta de respuesta a incidentes, este límite ayuda a garantizar que los mensajes de chat se quiten rápidamente.

## <a name="search-and-purge-workflow"></a>Flujo de trabajo de búsqueda y purga

Este es el proceso para buscar y purgar Teams mensajes de chat:

![Flujo de trabajo para buscar y purgar Teams mensajes de chat.](../media/TeamsSearchAndPurgeWorkflow.png)

## <a name="step-1-create-a-case-in-ediscovery-premium"></a>Paso 1: Crear un caso en eDiscovery (Premium)

El primer paso es crear un caso en eDiscovery (Premium) para administrar el proceso de búsqueda y purga. Para obtener información sobre cómo crear un caso, consulte [Uso del nuevo formato de caso](advanced-ediscovery-new-case-format.md). 

## <a name="step-2-create-a-draft-collection"></a>Paso 2: Crear una colección de borradores

Después de crear un caso, el siguiente paso es crear una colección de borradores para buscar los mensajes de chat Teams que desea purgar. El proceso de purga que realice es que el paso 5 purgará todos los elementos que se encuentran en la colección de borradores.

En eDiscovery (Premium), una *colección* es una búsqueda de exhibición de documentos electrónicos de las ubicaciones de contenido Teams que contienen los mensajes de chat que desea purgar. Cree la colección de borradores en el caso que creó en el paso anterior. Para obtener más información, consulte [Creación de una colección de borradores](create-draft-collection.md).

### <a name="data-sources-for-chat-messages"></a>Orígenes de datos para mensajes de chat

Use la tabla siguiente para determinar qué orígenes de datos buscar en función del tipo de mensaje de chat que necesite purgar.

| Para este tipo de chat...|Buscar en este origen de datos...|
|:---------|:---------|
|chats de Teams 1:1     |Buzón de correo de los participantes del chat.|
|Teams chats de grupo     |Buzones de los participantes del chat.|
|canales Teams (estándar y compartido) |Buzón asociado al equipo primario.|
|Teams canales privados |Buzón de correo de los miembros del canal privado.|

> [!NOTE]
> En el paso 4, también tiene que identificar y quitar las directivas de retención y retención asignadas al buzón de correo que contenga el tipo de mensajes de chat que desea eliminar.

### <a name="tips-for-searching-for-chat-messages"></a>Sugerencias para buscar mensajes de chat

Para garantizar la recopilación más completa de Teams conversaciones de chat (incluidos chats 1:1 y grupales y chats de chats estándar, compartidos y privados) use la condición **Tipo** y seleccione la opción **Mensajes instantáneos** al crear la consulta de búsqueda para la colección de borradores. También se recomienda incluir un intervalo de fechas o varias palabras clave para restringir el ámbito de la colección a elementos relevantes para la búsqueda de una investigación de purga.

Esta es una captura de pantalla de una consulta de ejemplo con las opciones **Tipo** y **Fecha** :

   ![Consulta para recopilar Teams contenido.](..\media\TeamsConditionsQueryType.png)

Para obtener más información, consulte [Compilación de consultas de búsqueda para colecciones](building-search-queries.md).

## <a name="step-3-review-and-verify-chat-messages-to-purge"></a>Paso 3: Revisión y comprobación de mensajes de chat para purgar

Como se mencionó anteriormente, el proceso de purga del paso 5 eliminará los elementos devueltos por la colección. Por lo tanto, es importante que revise los resultados de la colección de borradores para asegurarse de que la colección solo devuelve los elementos que desea purgar. Para revisar un ejemplo de elementos de una colección de borradores, consulte la sección "Pasos siguientes después de completar una colección de borradores" en [Creación de una colección de borradores](create-draft-collection.md#next-steps-after-a-draft-collection-is-complete).

Además, puede usar las estadísticas de recopilación (en concreto, las estadísticas de ubicaciones principales) para generar una lista de los orígenes de datos que contienen elementos devueltos por la colección. Use esta lista en el paso siguiente para quitar las directivas de retención y suspensión de los orígenes de datos que contienen resultados de búsqueda. Para obtener más información, consulte [Estadísticas e informes de recopilación](collection-statistics-reports.md).

## <a name="step-4-remove-holds-and-retention-policies-from-data-sources"></a>Paso 4: Quitar directivas de retención y retención de orígenes de datos

Para poder purgar los mensajes de chat de un buzón, debe quitar cualquier directiva de retención o suspensión asignada a un buzón de destino. Si no es así, se conservará el chat que intenta eliminar.

Use la lista de buzones que contienen los mensajes de chat que desea eliminar y determine si hay una directiva de retención o suspensión asignada a esos buzones y, a continuación, quite la directiva de retención o suspensión. Asegúrese de identificar la directiva de retención o retención que quite para poder reasignar a los buzones en el paso 7.

Para obtener instrucciones sobre cómo identificar y quitar las directivas de retención y retención, vea "Paso 3: Quitar todas las retenciones del buzón" en [Eliminar elementos en la carpeta Elementos recuperables de buzones basados en la nube en suspensión](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-3-remove-all-holds-from-the-mailbox). 

## <a name="step-5-purge-chat-messages-from-teams"></a>Paso 5: Purgar mensajes de chat de Teams

Ahora ya está listo para purgar realmente los mensajes de chat de Teams. Usará el Explorador de Microsoft Graph para realizar las tres tareas siguientes:

1. Obtenga el identificador del caso de eDiscovery (Premium) que creó en el paso 1. Este es el caso que contiene la colección creada en el paso 2.

2. Obtenga el identificador de la colección que creó en el paso 2 y comprobó los resultados de la búsqueda en el paso 3. La consulta de búsqueda de esta colección devuelve los mensajes de chat que se purgarán.

3. Purgar los mensajes de chat devueltos por la colección.

Para obtener información sobre el uso de Graph Explorer, consulte [Uso del Explorador de Graph para probar las API de Microsoft Graph](/graph/graph-explorer/graph-explorer-overview).

> [!IMPORTANT]
> Las API de la versión /beta de Microsoft Graph están sujetas a cambios. No se admite el uso de estas API en aplicaciones de producción. Para determinar si una API está disponible en la versión 1.0, use el selector de versiones.

> [!IMPORTANT]
> Para realizar estas tres tareas en Graph Explorador, es posible que tenga que dar su consentimiento a los permisos eDiscovery.Read.All y eDiscovery.ReadWrite.All. Para obtener más información, consulte la sección "Consentimiento para permisos" en [Trabajar con Graph Explorer](/graph/graph-explorer/graph-explorer-features#consent-to-permissions).

### <a name="get-the-case-id"></a>Obtener el identificador del caso

1. Vaya e <https://developer.microsoft.com/graph/graph-explorer> inicie sesión en el Explorador de Graph con una cuenta que tenga asignado el rol **Buscar y purgar** en el portal de cumplimiento de Microsoft Purview.

2. Ejecute la siguiente solicitud GET para recuperar el identificador del caso de eDiscovery (Premium). Use el valor `https://graph.microsoft.com/beta/compliance/ediscovery/cases` en la barra de direcciones de la consulta de solicitud. Asegúrese de seleccionar **v1.0** en la lista desplegable Versión de API.

   ![Solicitud GET para el identificador de caso.](..\media\GraphGetRequestForCaseId.png)

   Esta solicitud devuelve información sobre todos los casos de la organización en la pestaña **Vista previa de** respuesta.

3. Desplácese por la respuesta para buscar el caso de eDiscovery (Premium). Use la propiedad **displayName** para identificar el caso.

   ![Respuesta con el identificador de caso.](..\media\GraphResponseForCaseId.png)

4. Copie el identificador correspondiente (o cópielo y péguelo en un archivo de texto). Usará este identificador en la siguiente tarea para obtener el identificador de la colección.

> [!TIP]
> En lugar de usar el procedimiento anterior para obtener el identificador de caso, puede abrir el caso en el portal de cumplimiento de Microsoft Purview y copiar el identificador de caso de la dirección URL.

### <a name="get-the-collection-id"></a>Obtención del identificador de la colección

1. En Graph Explorador, ejecute la siguiente solicitud GET para recuperar el identificador de la colección que creó en el paso 2 y contiene los elementos que desea purgar. Use el valor `https://graph.microsoft.com/beta/compliance/ediscovery/cases('caseId')/sourceCollections` de la barra de direcciones de la consulta de solicitud, donde CaseId es el identificador que obtuvo en el procedimiento anterior. Asegúrese de rodear el identificador de caso con paréntesis y comillas simples.

   ![Solicitud GET para el identificador de colección.](..\media\GraphGetRequestForCollectionId.png)

   Esta solicitud devuelve información sobre todas las colecciones en el caso en la pestaña **Vista previa de** respuesta.

2. Desplácese por la respuesta para buscar la colección que contiene los elementos que desea purgar. Use la propiedad **displayName** para identificar la colección que creó en el paso 3.

   ![Respuesta con el identificador de colección.](..\media\GraphResponseForCollectionId.png)

   En la respuesta, la consulta de búsqueda de la colección se muestra en la propiedad **contentQuery** . Los elementos devueltos por esta consulta se purgarán en la siguiente tarea.

3. Copie el identificador correspondiente (o cópielo y péguelo en un archivo de texto). Usará este identificador en la siguiente tarea para purgar los mensajes de chat.

### <a name="purge-the-chat-messages"></a>Purgar los mensajes de chat

1. En Graph Explorador, ejecute la siguiente solicitud POST para purgar los elementos devueltos por la colección que creó en el paso 2. Use el valor `https://graph.microsoft.com/beta/compliance/ediscovery/cases('caseId')/sourceCollections('collectionId')/purgeData` de la barra de direcciones de la consulta de solicitud, donde caseId y collectionId son los identificadores que obtuvo en los procedimientos anteriores. Asegúrese de rodear los valores id con paréntesis y comillas simples.

      ![Solicitud POST para eliminar elementos devueltos por la colección.](..\media\GraphPOSTRequestToPurgeItems.png)

   Si la solicitud POST se realiza correctamente, se muestra un código de respuesta HTTP en un banner verde que indica que se ha aceptado la solicitud.

   ![Respuesta para la solicitud de purga.](..\media\GraphResponseForPurge.png)

  Para obtener más información sobre purgeData, vea [sourceCollection: purgeData](/graph/api/ediscovery-sourcecollection-purgedata).

## <a name="step-6-verify-chat-messages-are-purged"></a>Paso 6: Comprobar que los mensajes de chat se purgan

Después de ejecutar la solicitud POST para purgar mensajes de chat, estos mensajes se quitan del cliente Teams y se reemplazan por un generado automáticamente que indica que un administrador ha quitado el mensaje. Para ver un ejemplo de este mensaje, consulte la sección [Experiencia del usuario final](#end-user-experience) de este artículo.

Los mensajes de chat purgados se mueven a la carpeta SubstrateHolds, que es una carpeta de buzón oculta. Los mensajes de chat purgados se almacenan allí durante al menos 1 día y, a continuación, se eliminan permanentemente la próxima vez que se ejecuta el trabajo del temporizador (normalmente entre 1 y 7 días). Para obtener más información, consulte [Información sobre la retención de Microsoft Teams](retention-policies-teams.md).

## <a name="step-7-reapply-holds-and-retention-policies-to-data-sources"></a>Paso 7: Volver a aplicar las directivas de retención y retención a orígenes de datos

Después de comprobar que los mensajes de chat se purgan y quitan del cliente Teams, puede volver a aplicar las directivas de retención y retención que quitó en el paso 4.

<!--
## Deleting chat messages in federated environments

Admins can use the procedures in this article to search and delete Teams chat messages in federated environments. However, you must adhere to the following guidelines. These guidelines are based on the organizational ownership of the conversation thread that contains the messages you want to delete. An organization is the owner of a conversation thread that is started by a user in that organization. In other words, when a user starts a chat, the user's organization becomes the owner of the conversation thread.

- Admins can delete the compliance copy in conversation threads owned by their organization. That means compliance copies are purged when the admin who purges the chat messages in Step 5 is in the same organization as the user who initiated the conversation thread that contains the purged messages. If a conversation thread has users in two organizations, compliance copies for the other organization will be retained.

- If a conversation thread has users in two organizations, purged chat messages are removed from the Teams client in both organizations.

- The only way to purge chat messages from user mailboxes in your organization for chat messages in conversation threads owned by another organization is to use retention policies for Teams. For more information, see [Learn about retention for Microsoft Teams](retention-policies-teams.md).
-->

## <a name="end-user-experience"></a>Experiencia del usuario final

En el caso de los mensajes de chat eliminados, los usuarios verán un mensaje generado automáticamente que indica "Este mensaje fue eliminado por un administrador".

![Vista del mensaje de chat purgado en Teams cliente.](..\media\TeamsPurgeTombstone.png)

El mensaje de la captura de pantalla anterior reemplaza al mensaje de chat que se eliminó.

> [!NOTE]
> Si es un usuario final y se eliminó un mensaje de chat, póngase en contacto con el administrador para obtener más información.
