---
title: Opciones de final de ciclo de vida para grupos, equipos y Yammer
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
description: Opciones de final de ciclo de vida para grupos, equipos y Yammer.
ms.openlocfilehash: 31383287f3288cbab68d6e249f98210dec62af2f
ms.sourcegitcommit: 554755bc9ce40228ce6e34bde6fc6e226869b6a1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2020
ms.locfileid: "48681715"
---
# <a name="end-of-lifecycle-options-for-groups-teams-and-yammer"></a>Opciones de final de ciclo de vida para grupos, equipos y Yammer

Los grupos de Microsoft 365 y Microsoft Teams trabajan con una variedad de servicios conectados. Cuando se elimina un grupo o equipo, también se elimina la mayor parte de la información de los servicios conectados. En este artículo se describen las opciones para conservar la información moviéndola del grupo o equipo antes de su eliminación.

Una práctica común para grupos o equipos que ya no son necesarios es mover los archivos fuera del equipo y almacenarlos en otra ubicación, como una biblioteca de documentos de SharePoint que actúa como repositorio o archivo. Este procedimiento se basa en un estilo heredado de trabajo donde la información se almacena en archivos y carpetas, y las comunicaciones se realizan a través del correo electrónico.

En la siguiente tabla se describen los servicios asociados a grupos y equipos, y los tipos de contenido clave que se encuentran en cada uno de ellos:

|Servicio|Tipos de contenido|
|:------|:---------------|
|Teams|Conversaciones de canal, archivos en canales|
|Forms|Resultados y estructura de la encuesta|
|OneNote|Bloc de notas|
|Outlook|Correo y calendario|
|Planner|Información de estado y tarea del proyecto|
|Power Automate|Flujos de trabajo|
|Power BI|Datos, informes y paneles|
|Proyecto en la web|Planes de proyecto|
|Guía básica|Guías básicas|
|SharePoint|Archivos, listas, Teams canal datos de wiki|
|Stream|Vídeos|
|Yammer|Conversaciones|

Al eliminar un grupo o un equipo, la mayoría de los recursos asociados también se eliminan. Algunas de las excepciones a esto incluyen vídeos en secuencia, que siguen siendo propiedad de la persona que los ha cargado o grabado, tal y como lo hacen los flujos de energía automatizada. Los datos de proyectos y guías básicas de Project en la web permanecen en los CD y se pueden restaurar por separado.

Los grupos y los equipos permanecen en un estado de eliminación temporal durante 30 días y pueden restaurarse en cualquier momento. Sin embargo, después de los 30 días, y los recursos asociados, como los servicios y el contenido, se eliminan completamente del entorno de Microsoft 365. Cualquier contenido protegido por una directiva de retención sigue disponible a través de las búsquedas de exhibición de documentos electrónicos.

## <a name="end-of-life-cycle-considerations-for-group-connected-services"></a>Fin del ciclo de vida consideraciones para los servicios conectados a grupos

Hay tres áreas clave que los propietarios de grupo y de grupo y los administradores de TI deben tener en cuenta al eliminar un grupo o un equipo.

**Content**

¿Se debe conservar el contenido después de que el equipo ya no funcione o exista? ¿Es suficiente para confiar en las capacidades de retención de Microsoft 365 o es parte del contenido de aplicaciones y servicios que no ofrece retención? ¿Es necesario conservar el contenido para fines de administración de registros, con fines de archivo, o para uso futuro y referencia?

Estas preguntas se deben formular antes de archivar o eliminar un equipo, para evitar cualquier posible pérdida de datos.

**Servicios**

En la parte superior del contenido de varias aplicaciones y servicios, ¿deben permanecer en su formulario de trabajo actual? Por ejemplo, ¿el informe de Power BI debe seguir siendo accesible, los resultados del formulario deben estar disponibles en la vista de Resumen visual, ¿están vinculados o incrustados en cualquier parte de SharePoint?

De forma similar a las consideraciones de contenido, estas preguntas se deben formular antes de que se elimine el grupo subyacente ya que la simple exportación del contenido puede no ser suficiente.

**Visitantes**

Cuando se invita a los invitados a un equipo, el flujo de trabajo crea su identidad en el Azure Active Directory de la organización host antes de agregarlos al equipo. Cuando se elimina un equipo, los invitados no se quitan de Azure Active Directory y, como tal, sigue existiendo en el entorno de Microsoft Teams. Aunque los invitados no pueden acceder a grupos, sitios, equipos o contenido que no se han compartido con ellos, todavía pueden usar características de Microsoft Teams como iniciar chats, llamadas de voz y vídeo, y usar aplicaciones.

El propietario de un equipo o grupo puede invitar a un usuario externo a ser invitado en Azure Active Directory, agregarlo al equipo y quitarlo del equipo. Un propietario de equipo no puede, sin embargo, quitar al invitado de Azure Active Directory (esto solo puede realizarla un administrador global o un administrador de usuarios).

Por lo tanto, es importante realizar revisiones de invitado, así como comprender si es necesario quitar a los invitados de Azure Active Directory tras la eliminación del equipo. Puede que haya un caso válido para que los invitados permanezcan en el directorio, como ser miembros de uno o más equipos o usar otros servicios de Microsoft 365 o Azure.

## <a name="teams"></a>Teams

El contenido específico de Microsoft Teams está principalmente en forma de conversaciones.

Las conversaciones en los canales no se pueden copiar ni mover mediante la funcionalidad nativa de Microsoft Teams. Sin embargo, se pueden exportar con la API de Graph.

Además, si se aplica una directiva de retención a Teams, las conversaciones se conservan y están disponibles a través de búsquedas de exhibición de documentos electrónicos. (Los elementos que se encuentran en las búsquedas de exhibición de documentos electrónicos se pueden exportar; sin embargo, no se conserva el contexto o la estructura de su origen original; son simplemente mensajes individuales).

### <a name="archiving-a-team"></a>Archivado de un equipo

La ventaja de [archivar un equipo](https://docs.microsoft.com/microsoftteams/archive-or-delete-a-team) es que proporciona acceso total al equipo tal como era, de modo que los usuarios todavía pueden examinar conversaciones de canal y abrir archivos incluso si no están activos. Además, los equipos se pueden volver a archivar si es necesario seguir trabajando en ellos (por ejemplo, en el caso de una extensión de proyecto).

Cuando un propietario archiva un equipo, se establece en solo lectura para los miembros tanto para el contenido dentro del equipo como si está seleccionado, el sitio de SharePoint asociado. El objetivo de esta acción es asegurarse de que las conversaciones en los canales se conservan en su estado actual, junto con el contenido basado en SharePoint, como archivos y wikis.

En el sitio de SharePoint no hay cambios visibles, pero no se pueden realizar cambios en ningún archivo o lista, ya que el grupo de permisos basados en SharePoint para el grupo de Microsoft 365 está establecido en el nivel de visitantes del sitio. Esto incluye el Bloc de notas de OneNote para el equipo, ya que se almacena en la biblioteca activos del sitio en el sitio de SharePoint.

Cuando se archiva un equipo, el grupo 365 de Microsoft subyacente sigue sujeto a la Directiva de expiración (si se ha establecido) y, como tal, el propietario debe continuar renovando el equipo.

Mientras las conversaciones del canal del equipo y el contenido del sitio de SharePoint están establecidos como de solo lectura, no se aplica el mismo a otros servicios asociados:

- Los cubos y las tareas de Planner todavía se pueden crear, modificar y eliminar
- Los formularios todavía pueden recibir envíos
- El buzón de Outlook puede seguir recibiendo correos electrónicos
- Los paneles de Power BI, los informes y los datos se pueden seguir modificando
- Los proyectos y las guías básicas todavía pueden editarse en Project en la web
- Los vídeos aún se pueden cargar, modificar y eliminar en la secuencia
- Los flujos de automatización automatizada todavía pueden crearse, modificarse, eliminarse y seguir ejecutándose (se producirá un error si, si es necesario, se publica un mensaje en un canal del equipo archivado)

## <a name="forms"></a>Forms

Mientras que un formulario se puede mover de una cuenta individual a un grupo, no se puede mover ni copiar de un grupo a otro. Hay tres opciones disponibles para un formulario cuando se elimina un equipo.

**Duplicar el formulario**

Los formularios se pueden [compartir como plantillas](https://support.microsoft.com/office/82ea9d8a-260a-47a0-afdb-497f3d746e3f), lo que permite a otros usuarios copiarlos en su propia cuenta o en un grupo. Esto no conserva los datos de los envíos de resultados; solo la estructura del formulario, como preguntas y opciones de configuración.

**Exportar resultados a una hoja de cálculo**

Si es necesario conservar los datos de las respuestas del formulario, puede hacerlo [exportando los resultados a una hoja de cálculo de Excel](https://support.office.com/article/02859424-341d-406f-b32a-9a0fbaf357af). Esto sólo exportará las preguntas y respuestas como datos: no incluye los gráficos creados por los formularios.


**Eliminar el formulario**

Aunque la eliminación del grupo también dará como resultado la eliminación de los formularios asociados, los miembros del grupo pueden [eliminarlos directamente](https://support.microsoft.com/office/2207e468-ce1b-4c4a-a256-caf631d87af0) sin ser propietarios del grupo; sin embargo, se trata de un paso manual que no proporciona ninguna ventaja adicional.

## <a name="onenote"></a>OneNote

El Bloc de notas de OneNote incluido en un grupo se almacena en la biblioteca activos del sitio en el sitio de SharePoint asociado. Aunque los archivos de Bloc de notas se pueden repartir a veces en varios archivos individuales, no se pueden copiar y abrir de forma independiente. En su lugar, el contenido del Bloc de notas de OneNote debe moverse o exportarse con OneNote 2016.

**Mover páginas y secciones a otro Bloc de notas**

[Mover individualmente las páginas o secciones a otro Bloc de notas](https://support.office.com/article/c3c8b098-7f9c-4c2a-a0dc-ebb83bc76364) proporciona a los propietarios una oportunidad para limpiar sus datos y solo lo deben conservar.

**Exportar el Bloc de notas completo como un paquete**

Si es necesario conservar el Bloc de notas completo con su estructura existente, puede [exportarse como un](https://support.office.com/article/a4b60da5-8f33-464e-b1ba-b95ce540f309) archivo de paquete de OneNote y, a continuación, importarse a una nueva ubicación. Como alternativa, puede usarse como un método para conservar el contenido de un único archivo en lugar de la estructura de varios archivos existente.

**Impresión en PDF**

En los escenarios en los que parte del contenido del Bloc de notas solo debe retenerse para referencia o como registros, las páginas individuales pueden [imprimirse en PDF y almacenarse en otra ubicación](https://support.office.com/article/13d173b5-7f4c-45a8-94eb-9354d63af5cd).

## <a name="mailbox-and-calendar"></a>Buzón y calendario

No es raro que se utilice el buzón asociado al grupo, aunque muchas conversaciones se hayan llevado a cabo dentro de los canales del equipo. El buzón solo almacena los correos electrónicos que se enviaron directamente por correo electrónico y no incluye los correos electrónicos que se enviaron directamente a los canales.

En algunos casos, los correos electrónicos almacenados en el buzón pueden ser simplemente notificaciones de reuniones, actualizaciones de tareas del planeador y otros mensajes generados por el sistema o la aplicación. Es importante revisar el contenido del buzón para determinar si el contenido se debe conservar o eliminar.

Si se aplica una directiva de retención a Exchange, los mensajes de correo electrónico y los elementos de calendario se conservan y están disponibles a través de búsquedas de exhibición de documentos electrónicos.

**Exportar correo y calendario**

Los miembros del equipo o del grupo pueden [exportar el contenido del buzón y del calendario a un archivo de datos/almacenamiento personal (PST) de Outlook](https://support.office.com/article/14252b52-3075-4e9b-be4e-ff9ef1068f91). A continuación, este archivo puede almacenarse en otro lugar o el contenido se puede importar a un buzón de correo diferente. La primera opción no se recomienda, ya que no se puede buscar en el contenido del archivo PST sin abrirlo en Outlook, y el archivo en sí puede dañarse con el tiempo.

**Migración de contenido realizada por ti**

Los administradores pueden usar herramientas de terceros para migrar el contenido del calendario y el correo electrónico entre buzones sin intervención del usuario. Una ubicación de almacenamiento potencial podría ser un buzón compartido creado solamente para servir como "archivo" del contenido del buzón de grupo.

## <a name="planner"></a>Planner

Cada grupo o equipo puede tener varios planes. Durante el proceso de descarga, es importante asegurarse de que cada plan se dirige a si se conserva su contenido. Al igual que otros productos, hay varios métodos para desincorpora contenido en Planner.

**Exportar el plan a una hoja de cálculo**

Si solo es necesario conservar una copia del plan para el mantenimiento de registros, el enfoque más sencillo es [exportar el plan a una hoja de cálculo de Excel](https://support.microsoft.com/office/4d850c6e-e548-4aab-83b4-b62b68662d2a). Se trata de una acción unidireccional, ya que no hay ninguna opción para importar los planes desde una hoja de cálculo.

> [!IMPORTANT]
> Al exportar un plan a Excel, se tomará la mayor parte de la información dentro del plan, pero no se incluirán comentarios, vínculos o archivos.

**Copiar y mover tareas a otro plan**

Aunque parece una solución, las tareas individuales solo se pueden [copiar o mover entre planes](https://support.microsoft.com/office/ad43a5d8-c1ad-42fd-b3da-fe97d72c8a1b) dentro del mismo grupo, lo que niega la ventaja de si se elimina el grupo asociado con el plan.

**Copiar el plan completo**

También es posible [copiar todo el plan](https://support.microsoft.com/office/50401e13-a25f-40df-93c6-b608cc28c3d4). Sin embargo, esto no puede ser un grupo existente ni siquiera dentro del mismo grupo. Al copiar el plan, se creará un nuevo grupo. Además, la copia de todo el plan no incluirá comentarios, asignaciones, vínculos, datos adjuntos o fechas.

## <a name="power-automate"></a>Power Automate

Los flujos creados con la automatización de la alimentación y asociados a un grupo o un equipo no pertenecen al grupo y, en su lugar, son propiedad del creador y solo se comparten con otros usuarios y grupos. Como tal, no se ven afectados si se elimina un grupo o un equipo.

**Cambiar la propiedad del flujo**

Si el flujo de trabajo debe seguir funcionando, los propietarios pueden simplemente agregar otros usuarios o grupos de Microsoft 365 como propietarios.

**Exportar el flujo**

Si el flujo de trabajo no necesita seguir funcionando, pero debe conservarse para un uso futuro posible, se puede [exportar como un archivo](https://flow.microsoft.com/blog/import-export-bap-packages/) y volver a importarlo más adelante.

## <a name="power-bi"></a>Power BI

Los datos y las áreas de trabajo de Power BI pueden funcionar independientemente de grupos y equipos y, al igual que otras cargas de trabajo, ofrecen distintas formas de offboarded.

**Copiar informes en otro área de trabajo**

Si el informe debe conservarse en su estado funcional más allá de la vida del grupo o equipo, se puede [Copiar desde el área de trabajo existente a otro área de trabajo de Power BI](https://docs.microsoft.com/power-bi/connect-data/service-datasets-copy-reports).

**Exportar datos de un panel o informe**

Como alternativa, si el informe ya no tiene que estar activo, pero los datos deben conservarse, se puede [exportar a Excel](https://docs.microsoft.com/power-bi/visuals/power-bi-visualization-export-data).

## <a name="project"></a>Project

Los proyectos y las guías básicas creadas en Project en la web pueden asociarse con los grupos de 365 de Microsoft y ofrece métodos de descarga similares a Power BI.

**Asignar el proyecto a otro grupo**

Si el proyecto debe conservarse en su estado funcional más allá de la vida del grupo o equipo, puede [asignarse a un grupo de Microsoft 365 diferente](https://docs.microsoft.com/project-for-the-web/access-a-project-after-group-is-deleted#reassign-the-project) mediante el centro de administración de Dynamics 365.

**Exportar datos del proyecto o plan de desarrollo**

Mediante el uso del centro de administración de Dynamics 365, es posible [exportar datos de usuario del proyecto](https://docs.microsoft.com/project-for-the-web/export-user-data-from-project-for-the-web) a una hoja de cálculo o, si se usa un script de PowerShell, los datos se pueden exportar al archivo de proyecto (. MPP) y los formatos de archivo XML.

## <a name="sharepoint"></a>SharePoint
Todos los archivos de los canales de equipo se almacenan en la biblioteca de documentos del sitio de SharePoint del grupo asociado. En algunos casos, puede haber contenido que no sean documentos en SharePoint, como listas o páginas.
Por lo general, los archivos se almacenan en tres ubicaciones principales dentro de un sitio de SharePoint:

- Páginas: biblioteca de páginas de sitio
- Imágenes usadas en páginas: biblioteca de activos del sitio
- Archivos en canales: biblioteca de documentos
- Páginas wiki: biblioteca de datos wiki de Microsoft Teams

Si el sitio tiene uno o más subsitios anidados debajo, el proceso de retirada tendrá que repetirse para cada subsitio. Si el equipo contiene canales privados, hay un sitio de SharePoint independiente para cada canal.

Es importante al quitar archivos de un grupo o equipo para tener en cuenta que pueden compartirse con usuarios que no son miembros del grupo o equipo (ya sean internos o externos a la organización) y, como tal, puede merecer la pena comunicar el cambio inminente a ellos.

**Descargar archivos**

En el caso de los archivos almacenados en SharePoint en una de las bibliotecas mencionadas anteriormente, estos se pueden [Descargar en un equipo local](https://support.office.com/article/5c7397b7-19c7-4893-84fe-d02e8fa5df05).

**Mover archivos**

Además, los archivos se pueden mover a otra ubicación dentro de SharePoint, como una biblioteca en un sitio diferente.
Referencias https://support.office.com/article/move-or-copy-files-in-sharepoint-00e2f483-4df3-46be-a861-1f5f0c1a87bc

**Exportar lista** Los datos almacenados en las listas de SharePoint se pueden [exportar a una hoja de cálculo de Excel](https://support.office.com/article/bfb2ea48-6118-4fa9-abb6-cced9424e5d9)y volver a importar a una lista en otro sitio.

Como alternativa, se puede usar una herramienta de terceros para migrar la lista entre sitios para conservar funciones, vistas de lista, formato y otros atributos.

**Archivos "Export" de wiki**

El contenido de la wiki dentro de los canales de equipo se almacena en un archivo con formato HTML en una biblioteca dedicada del sitio de SharePoint asociado. No se pueden exportar e importar fácilmente a otro wiki de canal, pero se pueden convertir a un archivo HTML y abrirlos como página web.

## <a name="microsoft-stream"></a>Microsoft Stream

Como la automatización de la alimentación, los vídeos de la secuencia asociados a un grupo o equipo no son realmente propiedad del grupo y no se eliminan cuando se elimina el grupo. Los vídeos en secuencia los posee la persona que cargó o creó el vídeo, incluso si agregan usuarios o grupos como propietarios. Este es también el caso de las reuniones registradas en un canal de Teams; son propiedad de la persona que inició la grabación.

**Agregar otros propietarios**

A medida que el vídeo se retiene en la secuencia independientemente de la eliminación del grupo, el propietario original puede [compartir el vídeo con otros usuarios y grupos, e incluso agregarlos como propietarios](https://docs.microsoft.com/stream/portal-edit-video).

**Descargar el vídeo**

En los escenarios en los que no es necesario conservar el vídeo en la secuencia o debe almacenarse en una ubicación alternativa, como un sistema de administración de registros, un propietario puede [descargarlo de forma local](https://docs.microsoft.com/stream/portal-download-video) .

## <a name="yammer"></a>Yammer

A diferencia de las conversaciones en Microsoft Teams, Yammer ofrece a los usuarios y a los administradores opciones para mover o exportar conversaciones.

**Mover conversaciones a otro grupo o comunidad**

Los usuarios pueden mover conversaciones a otro grupo de Yammer, no solo los propietarios o los administradores. Esto es posible tanto en la versión [clásica de Yammer](https://support.office.com/article/149c6399-4ac1-4ced-84d7-e0660960a872)como en las [nuevas](https://support.office.com/article/d63debf1-1c90-4ec5-b5ae-8a00939a1680) interfaces de Yammer.

**Exportar datos de red**

Los administradores de red de Yammer pueden [exportar datos de red](https://docs.microsoft.com/yammer/manage-security-and-compliance/export-yammer-enterprise-data), pero al hacerlo se exportarán todas las conversaciones de toda la red. Sin embargo, la exportación resultante enumera el identificador de grupo, por lo que es posible filtrar conversaciones en función de esto.
