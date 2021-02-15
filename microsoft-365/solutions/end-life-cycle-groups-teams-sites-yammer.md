---
title: Opciones de fin de ciclo de vida para grupos, equipos y Yammer
ms.reviewer: mmclean
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: Opciones de fin de ciclo de vida para grupos, equipos y Yammer.
ms.openlocfilehash: 31383287f3288cbab68d6e249f98210dec62af2f
ms.sourcegitcommit: 554755bc9ce40228ce6e34bde6fc6e226869b6a1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2020
ms.locfileid: "48681715"
---
# <a name="end-of-lifecycle-options-for-groups-teams-and-yammer"></a>Opciones de fin de ciclo de vida para grupos, equipos y Yammer

Los grupos de Microsoft 365 y Microsoft Teams funcionan con una variedad de servicios conectados. Cuando se elimina un grupo o equipo, también se elimina la mayor parte de la información de los servicios conectados. En este artículo se describen las opciones para conservar la información al moverla fuera del grupo o equipo antes de la eliminación.

Un procedimiento común para grupos o equipos que ya no son necesarios es mover los archivos fuera del equipo y almacenarlos en otra ubicación, como una biblioteca de documentos de SharePoint que actúe como repositorio o archivo. Esta práctica se basa en un estilo heredado de trabajo en el que la información se almacena en archivos y carpetas, y las comunicaciones se llevan a cabo por correo electrónico.

En la tabla siguiente se describen los servicios asociados a grupos y equipos, así como los tipos clave de contenido que se encuentran en cada uno de ellos:

|Servicio|Tipos de contenido|
|:------|:---------------|
|Teams|Conversaciones de canal, archivos en canales|
|Formularios|Estructura y resultados de la encuesta|
|OneNote|Bloc de notas|
|Outlook|Correo y calendario|
|Planner|Información de tareas y estado del proyecto|
|Power Automate|Flujos de trabajo|
|Power BI|Datos, informes y paneles|
|Proyecto en la web|Planes del proyecto|
|Guía básica|Guías básicas|
|SharePoint|Archivos, listas, datos wiki del canal de Teams|
|Stream|Vídeos|
|Yammer|Conversaciones|

Al eliminar un grupo o equipo, también se eliminan la mayoría de los recursos asociados. Algunas de las excepciones a esto incluyen vídeos en Stream, que permanecen y siguen siendo propiedad de la persona que los ha cargado o grabado, al igual que los flujos de Power Automate. Los datos del proyecto y la guía básica de Project en la web permanecen en el CDS y se pueden restaurar por separado.

Los grupos y equipos permanecen en estado de eliminación de forma flexible durante 30 días y se pueden restaurar en cualquier momento. Sin embargo, transcurridos los 30 días, tanto ellos como los recursos asociados, como los servicios y el contenido, se purgan completamente del entorno de Microsoft 365. Cualquier contenido protegido por una directiva de retención permanece disponible a través de búsquedas de exhibición de documentos electrónicos.

## <a name="end-of-life-cycle-considerations-for-group-connected-services"></a>Consideraciones de fin del ciclo de vida para los servicios conectados a grupos

Hay tres áreas clave que los propietarios de equipos y grupos y los administradores de TI deben tener en cuenta al eliminar un grupo o equipo.

**Contenido**

¿Es necesario conservar el contenido después de que el equipo ya no esté funcional o en existencia? ¿Es suficiente confiar en las capacidades de retención de Microsoft 365 o es parte del contenido de aplicaciones y servicios que no ofrecen retención? ¿Es necesario conservar el contenido con fines de administración de registros, con fines de archivo o con fines de referencia y uso futuro?

Estas preguntas deben realizarse antes de archivar o eliminar cualquier equipo, para evitar posibles pérdidas de datos.

**Servicios**

Además del contenido de varias aplicaciones y servicios, ¿deben permanecer en su formulario de trabajo actual? Por ejemplo, ¿es necesario que el informe de Power BI siga siendo accesible, los resultados del formulario deben estar disponibles en la vista de resumen visual, están las listas de SharePoint vinculadas o incrustadas en cualquier lugar?

De forma similar a las consideraciones de contenido, estas preguntas deben realizarse antes de que se elimine el grupo subyacente, ya que simplemente exportar el contenido puede no ser suficiente.

**Invitados**

Cuando se invita a invitados a un equipo, el flujo de trabajo crea su identidad en Azure Active Directory de la organización host antes de agregarlos al equipo. Cuando se elimina un equipo, los invitados no se quitan de Azure Active Directory y, como tal, siguen existiendo en el entorno de Microsoft Teams. Aunque los invitados no pueden acceder a grupos, sitios, equipos o contenido que no se haya compartido con ellos, aún pueden usar características dentro de Microsoft Teams, como iniciar chats, llamadas de voz y vídeo, y usar aplicaciones.

El propietario de un equipo o grupo puede invitar a un usuario externo para que se convierta en invitado en Azure Active Directory, agregarlo al equipo y quitarlo del equipo. Sin embargo, el propietario de un equipo no puede quitar al invitado de Azure Active Directory; esto solo lo puede realizar un administrador global o un administrador de usuarios.

Por lo tanto, es importante realizar revisiones de invitados, así como comprender si los invitados deben quitarse de Azure Active Directory tras la eliminación del equipo. Puede haber un caso válido para que los invitados permanezcan en el directorio, como ser miembro de uno o más equipos o usar otros servicios de Microsoft 365 o Azure.

## <a name="teams"></a>Teams

El contenido específico de Teams se encuentra principalmente en forma de conversaciones.

Las conversaciones en canales no se pueden copiar ni mover con la funcionalidad nativa de Microsoft Teams. Sin embargo, se pueden exportar mediante la API de Graph.

Además, si se aplica una directiva de retención a Teams, las conversaciones se conservan y están disponibles a través de búsquedas de exhibición de documentos electrónicos. (Los elementos encontrados en las búsquedas de exhibición de documentos electrónicos se pueden exportar, pero no queda ningún contexto ni estructura de su origen original, simplemente son mensajes individuales).

### <a name="archiving-a-team"></a>Archivado de un equipo

La ventaja de archivar [un](https://docs.microsoft.com/microsoftteams/archive-or-delete-a-team) equipo es que proporciona acceso completo al equipo tal como estaba, de modo que los usuarios aún pueden explorar conversaciones de canal y abrir archivos aunque no estén activos. Además, los equipos pueden no estar anquilosados si es necesario seguir trabajando en ellos (por ejemplo, en el caso de una extensión de proyecto).

Cuando un propietario archiva un equipo, se establece en solo lectura para los miembros, tanto para el contenido dentro del equipo como si está seleccionado, para el sitio de SharePoint asociado. El objetivo de esta acción es garantizar que las conversaciones de los canales se conserven en su estado existente, junto con el contenido basado en SharePoint, como archivos y wikis.

En el sitio de SharePoint no hay cambios visibles, pero no se pueden realizar cambios en ningún archivo o lista, ya que el grupo de permisos basado en SharePoint para el grupo de Microsoft 365 está establecido en el nivel de visitantes del sitio. Esto incluye el bloc de notas de OneNote para el equipo, ya que se almacena en la biblioteca activos del sitio dentro del sitio de SharePoint.

Cuando se archiva un equipo, el grupo subyacente de Microsoft 365 sigue sujeto a la directiva de expiración (si se establece) y, como tal, el propietario debe continuar renovando el equipo.

Aunque las conversaciones de canal del equipo y el contenido del sitio de SharePoint se establecen como de solo lectura, no se aplica lo mismo a otros servicios asociados:

- Aún se pueden crear, modificar y eliminar cubos y tareas de Planner
- Los formularios aún pueden recibir envíos
- El buzón de Outlook aún puede recibir correos electrónicos
- Los paneles, informes y datos de Power BI aún se pueden modificar
- Los proyectos y las guías básicas aún se pueden editar en Project en la web
- Los vídeos aún se pueden cargar, modificar y eliminar en Stream
- Los flujos de Power Automate aún pueden crearse, modificarse, eliminarse y seguir funcionando (no obstante, se producirá un error si es necesario para publicar un mensaje en un canal del equipo archivado).

## <a name="forms"></a>Formularios

Aunque un formulario se puede mover de una cuenta individual a un grupo, no se puede mover ni copiar de un grupo a otro. Hay tres opciones disponibles para un formulario cuando se elimina un equipo.

**Duplicar el formulario**

Los formularios se [pueden compartir como plantillas,](https://support.microsoft.com/office/82ea9d8a-260a-47a0-afdb-497f3d746e3f)lo que permite a otros usuarios copiarlos en su propia cuenta o en un grupo. Esto no conserva los datos de los envíos de resultados; solo estructura del formulario, como preguntas y configuración.

**Exportar resultados a una hoja de cálculo**

Si es necesario conservar los datos de las respuestas del formulario, puede hacerlo exportando los resultados a una [hoja de cálculo de Excel.](https://support.office.com/article/02859424-341d-406f-b32a-9a0fbaf357af) Esto solo exportará las preguntas y sus respuestas como datos; no incluye gráficos creados por formularios.


**Eliminar el formulario**

Aunque la eliminación del grupo también dará como resultado [](https://support.microsoft.com/office/2207e468-ce1b-4c4a-a256-caf631d87af0) la eliminación de los formularios asociados, los miembros del grupo pueden eliminarlos directamente sin ser propietarios del grupo; sin embargo, este es un paso manual que no proporciona ninguna ventaja adicional.

## <a name="onenote"></a>OneNote

El bloc de notas de OneNote incluido en un grupo se almacena en la biblioteca activos del sitio dentro del sitio de SharePoint asociado. Aunque a veces los archivos de bloc de notas se pueden propagar en varios archivos individuales, simplemente no se pueden copiar y abrir de forma independiente. En su lugar, el contenido del bloc de notas de OneNote debe moverse o exportarse con OneNote 2016.

**Mover páginas y secciones a otro bloc de notas**

[Mover individualmente páginas o secciones](https://support.office.com/article/c3c8b098-7f9c-4c2a-a0dc-ebb83bc76364) a otro bloc de notas proporciona a los propietarios la oportunidad de limpiar sus datos y tomar solo lo que se debe conservar.

**Exportar todo el bloc de notas como un paquete**

Si es necesario conservar todo el bloc de notas con su estructura existente, se puede exportar como un archivo de paquete de [OneNote](https://support.office.com/article/a4b60da5-8f33-464e-b1ba-b95ce540f309) y, a continuación, importarlo a una nueva ubicación. Como alternativa, esto puede usarse como un método para conservar el contenido en un solo archivo en lugar de la estructura de varios archivos existente.

**Impresión en PDF**

En escenarios en los que algunos de los contenidos del bloc de notas solo necesitan conservarse como referencia o como registros, las páginas individuales se pueden imprimir en PDF y almacenarse en [otro lugar.](https://support.office.com/article/13d173b5-7f4c-45a8-94eb-9354d63af5cd)

## <a name="mailbox-and-calendar"></a>Buzón de correo y calendario

No es raro que se use el buzón asociado al grupo, aunque muchas conversaciones se hayan llevado a cabo dentro de los canales de equipo. El buzón solo almacena mensajes de correo electrónico enviados directamente a él y no incluye correos electrónicos que se enviaron directamente a los canales.

En algunos casos, los correos electrónicos almacenados en el buzón pueden ser simplemente notificaciones de reuniones, actualizaciones de tareas de Planner y otros mensajes generados por la aplicación o el sistema. Es importante que se revise el contenido del buzón para determinar si el contenido debe conservarse o eliminarse.

Si se aplica una directiva de retención a Exchange, los correos electrónicos y los elementos del calendario se conservan y están disponibles a través de búsquedas de exhibición de documentos electrónicos.

**Exportar correo y calendario**

Los miembros del equipo o grupo pueden exportar el contenido del buzón y el calendario a un archivo de datos o almacenamiento [personal (PST) de Outlook.](https://support.office.com/article/14252b52-3075-4e9b-be4e-ff9ef1068f91) Este archivo se puede almacenar en otro lugar o el contenido se puede importar a un buzón diferente. El primero no se recomienda, ya que el contenido del archivo PST no se puede buscar sin abrirlo en Outlook y el propio archivo puede dañarse con el tiempo.

**Migración de contenido realizada por EL**

Los administradores pueden usar herramientas de terceros para migrar el contenido del correo electrónico y el calendario entre buzones sin la intervención del usuario. Una posible ubicación de almacenamiento podría ser un buzón compartido creado exclusivamente para servir como un "archivo" del contenido del buzón de grupo.

## <a name="planner"></a>Planner

Cada grupo o equipo puede tener varios planes. Es importante durante el proceso de baja para asegurarse de que cada plan se aborda en cuanto a si su contenido se conserva. Al igual que los demás productos, hay varios enfoques para quitar contenido en Planner.

**Exportar el plan a una hoja de cálculo**

Si solo es necesario conservar una copia del plan con fines de mantenimiento de registros, el enfoque más sencillo es exportar el plan a una hoja [de cálculo de Excel](https://support.microsoft.com/office/4d850c6e-e548-4aab-83b4-b62b68662d2a). Se trata de una acción unitiva, ya que no hay ninguna opción para importar planes desde una hoja de cálculo.

> [!IMPORTANT]
> Exportar un plan a Excel tomará la mayor parte de la información dentro del plan, pero no incluirá comentarios, vínculos ni archivos.

**Copiar y mover tareas a otro plan**

Aunque parece una solución, las tareas [](https://support.microsoft.com/office/ad43a5d8-c1ad-42fd-b3da-fe97d72c8a1b) individuales solo se pueden copiar o mover entre planes dentro del mismo grupo, lo que anula la ventaja si se elimina el grupo asociado con el plan.

**Copiar todo el plan**

También es posible copiar [todo el plan.](https://support.microsoft.com/office/50401e13-a25f-40df-93c6-b608cc28c3d4) Sin embargo, esto no puede ser para un grupo existente o incluso dentro del mismo grupo. Al copiar el plan se creará un nuevo grupo. Además, la copia de todo el plan no incluirá comentarios, asignaciones, vínculos, datos adjuntos ni fechas.

## <a name="power-automate"></a>Power Automate

Los flujos creados en Power Automate y asociados a un grupo o equipo no pertenecen al grupo y, en su lugar, son propiedad del creador y simplemente se comparten con otros usuarios y grupos. Por lo tanto, no se verán afectados si se elimina un grupo o equipo.

**Cambiar la propiedad del flujo**

Si el flujo de trabajo necesita seguir funcionando, los propietarios pueden simplemente agregar otros usuarios o grupos de Microsoft 365 como propietarios.

**Exportar el flujo**

Si no es necesario que el flujo de trabajo continúe funcionando, pero debe conservarse para su posible uso futuro, se puede exportar como archivo y volver [a](https://flow.microsoft.com/blog/import-export-bap-packages/) importarse más adelante.

## <a name="power-bi"></a>Power BI

Los datos y áreas de trabajo de Power BI pueden funcionar independientemente de grupos y equipos, y al igual que otras cargas de trabajo, ofrecen diferentes formas de ser desabordadas.

**Copiar informes a otro área de trabajo**

Si el informe debe conservarse en su estado funcional más allá de la vida del grupo o equipo, se puede copiar desde el área de trabajo existente a otro área de trabajo dentro de [Power BI](https://docs.microsoft.com/power-bi/connect-data/service-datasets-copy-reports).

**Exportar datos de un panel o informe**

Como alternativa, si el informe ya no necesita estar activo pero es necesario conservar los datos, se puede [exportar a Excel](https://docs.microsoft.com/power-bi/visuals/power-bi-visualization-export-data).

## <a name="project"></a>Project

Los proyectos y los planes de desarrollo creados en Project en la web pueden asociarse con grupos de Microsoft 365 y ofrecen enfoques de descarga similares a Power BI.

**Asignar el proyecto a otro grupo**

Si el proyecto necesita conservarse en su estado funcional más allá de la vida del grupo o equipo, se puede asignar a un grupo de [Microsoft 365](https://docs.microsoft.com/project-for-the-web/access-a-project-after-group-is-deleted#reassign-the-project) diferente mediante el Centro de administración de Dynamics 365.

**Exportar datos del proyecto o plan de desarrollo**

Con el Centro de administración de Dynamics [](https://docs.microsoft.com/project-for-the-web/export-user-data-from-project-for-the-web) 365 es posible exportar datos de usuario del proyecto a una hoja de cálculo o, si se usa un script de PowerShell, los datos se pueden exportar al archivo de Project (. MPP) y formatos de archivo XML.

## <a name="sharepoint"></a>SharePoint
Todos los archivos de los canales de equipo se almacenan en la biblioteca de documentos del sitio de SharePoint del grupo asociado. En algunos casos, puede haber contenido que no sea documentos en SharePoint, como listas o páginas.
Por lo general, los archivos se almacenan en tres ubicaciones principales dentro de un sitio de SharePoint:

- Páginas: biblioteca de páginas del sitio
- Imágenes usadas en páginas: biblioteca de activos del sitio
- Archivos en canales: biblioteca de documentos
- Páginas wiki: biblioteca de datos wiki de Teams

Si el sitio tiene uno o varios subs sitios anidados por debajo, el proceso de baja se tendrá que repetir para cada subs sitios. Si el equipo contiene canales privados, hay un sitio de SharePoint independiente para cada canal.

Es importante al quitar archivos de un grupo o equipo tener en cuenta que pueden compartirse con usuarios que no son miembros del grupo o equipo (ya sean internos o externos a la organización) y, por lo tanto, puede ser conveniente comunicarles el cambio inminente.

**Descargar archivos**

En el caso de los archivos almacenados en SharePoint en una de las bibliotecas mencionadas anteriormente, estos se pueden [descargar en un equipo local.](https://support.office.com/article/5c7397b7-19c7-4893-84fe-d02e8fa5df05)

**Mover archivos**

Además, los archivos se pueden mover a otra ubicación dentro de SharePoint, como una biblioteca en un sitio diferente.
Referencia: https://support.office.com/article/move-or-copy-files-in-sharepoint-00e2f483-4df3-46be-a861-1f5f0c1a87bc

**Exportar lista** Los datos almacenados en listas de SharePoint se pueden exportar a una hoja [de cálculo](https://support.office.com/article/bfb2ea48-6118-4fa9-abb6-cced9424e5d9)de Excel y volver a importarse a una lista de otro sitio.

Como alternativa, se puede usar una herramienta de terceros para migrar la lista entre sitios con el fin de conservar la función, las vistas de lista, el formato y otros atributos.

**"Exportar" archivos wiki**

El contenido wiki dentro de los canales de grupo se almacena en un archivo con formato HTML en una biblioteca dedicada del sitio de SharePoint asociado. No se pueden exportar e importar fácilmente a otro sitio wiki de canal, pero se pueden convertir en un archivo HTML y abrirse como una página web.

## <a name="microsoft-stream"></a>Microsoft Stream

Al igual que Power Automate, los vídeos de Stream asociados a un grupo o equipo no son realmente propiedad del grupo y no se eliminan cuando se elimina el grupo. Los vídeos de Stream son propiedad de la persona que carró o creó el vídeo, incluso si agregan usuarios o grupos como propietarios. Este también es el caso de las reuniones grabadas en un canal de Teams; son propiedad de la persona que inició la grabación.

**Agregar otros propietarios**

Como el vídeo se conserva en Stream independientemente de la eliminación de grupos, el propietario original puede compartir el vídeo con otros usuarios y grupos, incluso agregarlos [como propietarios.](https://docs.microsoft.com/stream/portal-edit-video)

**Descargar el vídeo**

En escenarios en los que no es necesario conservar el vídeo en Stream o si es necesario almacenarlo en una ubicación alternativa, como un sistema de administración de registros, un propietario puede descargarlo [localmente](https://docs.microsoft.com/stream/portal-download-video)

## <a name="yammer"></a>Yammer

A diferencia de las conversaciones en Microsoft Teams, Yammer ofrece opciones de usuarios y administradores para mover o exportar conversaciones.

**Mover conversaciones a otro grupo o comunidad**

Cualquier usuario puede mover las conversaciones a otro grupo de Yammer, no solo a los propietarios o administradores. Esto es posible tanto en la [versión clásica de Yammer](https://support.office.com/article/149c6399-4ac1-4ced-84d7-e0660960a872)como en las nuevas interfaces [de Yammer.](https://support.office.com/article/d63debf1-1c90-4ec5-b5ae-8a00939a1680)

**Exportar datos de red**

Los administradores de red de Yammer pueden realizar una [exportación](https://docs.microsoft.com/yammer/manage-security-and-compliance/export-yammer-enterprise-data)de datos de red, pero al hacerlo, se exportarán todas las conversaciones de toda la red. Sin embargo, la exportación resultante muestra el identificador de grupo, por lo que es posible filtrar las conversaciones en función de esto.
