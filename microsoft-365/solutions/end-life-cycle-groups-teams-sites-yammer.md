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
ms.openlocfilehash: 468f41df747b6cf12d3f6619d79cb97248eba1d1
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2021
ms.locfileid: "52346431"
---
# <a name="end-of-lifecycle-options-for-groups-teams-and-yammer"></a>Opciones de fin de ciclo de vida para grupos, equipos y Yammer

Microsoft 365 Los grupos Microsoft Teams funcionan con varios servicios conectados. Cuando se elimina un grupo o equipo, la mayor parte de la información de los servicios conectados también se elimina. En este artículo se describen las opciones para conservar la información al moverla fuera del grupo o equipo antes de eliminarla.

Una práctica común para grupos o equipos que ya no son necesarios es mover los archivos fuera del equipo y archivarlos en otra ubicación, como una biblioteca SharePoint documentos. Esta práctica se basa en un estilo heredado de trabajo donde la información se almacena en archivos y carpetas, y las comunicaciones se realizan por correo electrónico.

En la tabla siguiente se describen los servicios asociados con grupos y equipos y los tipos clave de contenido que se encuentran en cada uno de ellos:

|Servicio|Tipos de contenido|
|:------|:---------------|
|Teams|Conversaciones de canal, archivos en canales|
|Formularios|Estructura y resultados de la encuesta|
|OneNote|Bloc de notas|
|Outlook|Correo y calendario|
|Planner|Project estado y la información de tareas|
|Power Automate|Flujos de trabajo|
|Power BI|Datos, informes y paneles|
|Project en la web|Project planes|
|Guía básica|Guías básicas|
|SharePoint|Archivos, listas, Teams wiki de canal|
|Stream|Vídeos|
|Yammer|Conversaciones|

Al eliminar un grupo o equipo, la mayoría de los recursos asociados también se eliminan. Entre las excepciones se incluyen:

- Los vídeos de Stream permanecen y son propiedad de la persona que los ha cargado o grabado
- Los flujos Power Automate permanecen y son propiedad de la persona que los creó.
- Project y los datos del mapa de ruta Project en la web permanecen en el CDS y se pueden restaurar por separado.

Los grupos y los equipos permanecen en estado de eliminación suave durante 30 días y se pueden restaurar en cualquier momento. Sin embargo, después de los 30 días, ellos y los recursos asociados, como servicios y contenido, se purgan del Microsoft 365 usuario. Cualquier contenido protegido por una directiva de retención permanece disponible a través de búsquedas de exhibición de documentos electrónicos.

## <a name="end-of-life-cycle-considerations-for-group-connected-services"></a>Consideraciones sobre el fin del ciclo de vida de los servicios conectados a grupos

Hay tres áreas clave que los propietarios de equipos y grupos y los administradores de TI deben tener en cuenta al eliminar un grupo o equipo.

**Content**

¿Es necesario conservar el contenido después de que el equipo ya no esté allí? ¿Es suficiente confiar en las capacidades de retención de Microsoft 365 o es parte del contenido de aplicaciones y servicios que no ofrecen retención? ¿Es necesario conservar el contenido para la administración de registros, el archivo o el uso futuro y la referencia?

Para evitar cualquier posible pérdida de datos, estas preguntas deben realizarse antes de archivar o eliminar cualquier equipo.

**Servicios**

¿El contenido debe permanecer en su formulario de trabajo actual? Por ejemplo, ¿el informe Power BI debe seguir siendo accesible? ¿Los resultados del formulario deben estar disponibles en la vista de resumen visual? ¿Las listas de SharePoint están vinculadas o incrustadas en cualquier lugar?

Estas preguntas deben realizarse antes de eliminar el grupo subyacente, ya que es posible que no sea suficiente exportar el contenido.

**Invitados**

Cuando se invita a los invitados a un equipo, se crea una cuenta de invitado en el Azure Active Directory de la organización host antes de agregarlos al equipo. Cuando se elimina un equipo, los invitados no se quitan de Azure Active Directory. Aunque los invitados no pueden tener acceso a grupos, sitios, equipos o contenido que no se haya compartido con ellos, pueden usar potencialmente características dentro de Microsoft Teams como iniciar chats, llamadas de voz y vídeo y usar aplicaciones.

Un propietario de grupo o equipo puede invitar a alguien de fuera de la organización a convertirse en invitado en Azure Active Directory agregarlos a un equipo. Sin embargo, el propietario de un equipo no puede quitar al invitado de Azure Active Directory. La eliminación de cuentas solo la puede realizar un administrador global o un administrador de usuario.

Es importante realizar revisiones de invitados y comprender si los invitados deben eliminarse de Azure Active Directory eliminación del equipo. Puede haber un caso válido para que los invitados permanezcan en el directorio, como ser miembro de otros equipos o usar otros Microsoft 365 servicios de Azure.

## <a name="teams"></a>Teams

Teams contenido específico está principalmente en forma de conversaciones.

Las conversaciones en canales no se pueden copiar ni mover con la funcionalidad Microsoft Teams nativa. Sin embargo, se pueden exportar mediante la API Graph datos.

Además, si se aplica una directiva de retención a Teams, las conversaciones se conservan y están disponibles a través de búsquedas de exhibición de documentos electrónicos. Con eDiscovery avanzado puede [reconstruir una conversación Teams chat](/microsoft-365/compliance/conversation-review-sets).


### <a name="archiving-a-team"></a>Archivado de un equipo

La ventaja de [archivar un equipo](/microsoftteams/archive-or-delete-a-team) es que proporciona acceso completo al equipo tal como estaba. Los usuarios aún pueden examinar conversaciones de canal y abrir archivos incluso si no están activos. Además, los equipos pueden no estar anquilosados si es necesario seguir trabajando en ellos (por ejemplo, si se amplía un proyecto).

Cuando un propietario archiva un equipo, se establece en solo lectura para los miembros, tanto para el contenido dentro del equipo como si está seleccionado, el sitio SharePoint asociado. El objetivo de esta acción es garantizar que las conversaciones de los canales se conserven en su estado existente, junto con el contenido basado SharePoint como archivos y wikis.

En el SharePoint no hay cambios visibles. Sin embargo, no se pueden realizar cambios en ningún archivo o lista porque los permisos de SharePoint para el grupo de Microsoft 365 están establecidos en **Visitantes del sitio**. Esto incluye el bloc OneNote de notas del equipo, que se almacena en la biblioteca activos del sitio dentro del SharePoint sitio.

Cuando se archiva un equipo, el grupo de Microsoft 365 subyacente sigue sujeto a la directiva de expiración (si se establece) y, como tal, el propietario debe continuar renovando el equipo.

Aunque las conversaciones de canal del equipo y SharePoint contenido del sitio están establecidos en solo lectura, no se aplica lo mismo a otros servicios asociados:

- Los cubos y las tareas de Planner aún se pueden crear, modificar y eliminar.
- Los formularios aún pueden recibir envíos.
- El Outlook buzón de correo aún puede recibir correos electrónicos.
- Power BI paneles, informes y datos aún se pueden modificar.
- Los proyectos y los planes de ruta aún se pueden editar Project en la web.
- Los vídeos aún se pueden cargar, modificar y eliminar en Stream.
- Los flujos Power Automate pueden crearse, modificarse, eliminarse y se seguirán ejecutando. (No obstante, se producirá un error si es necesario para publicar un mensaje en un canal del equipo archivado).

## <a name="forms"></a>Formularios

Aunque un formulario se puede mover de una cuenta individual a un grupo, no se puede mover ni copiar de un grupo a otro. Hay tres opciones disponibles para un formulario cuando se elimina un equipo.

**Duplicar el formulario**

Los formularios [se pueden compartir como plantillas,](https://support.microsoft.com/office/82ea9d8a-260a-47a0-afdb-497f3d746e3f)lo que permite a otros usuarios copiarlos en su propia cuenta o en un grupo. Esto no conserva los datos de los envíos de resultados; solo estructura del formulario, como preguntas y configuración.

**Exportar resultados a una hoja de cálculo**

Si es necesario conservar los datos de las respuestas del formulario, esto se puede lograr exportando los resultados a una [Excel hoja de cálculo](https://support.office.com/article/02859424-341d-406f-b32a-9a0fbaf357af). Esto solo exportará las preguntas y sus respuestas como datos; no incluye gráficos creados por Formularios.

**Eliminar el formulario**

Aunque la eliminación del grupo también dará como resultado la eliminación de los formularios asociados, los miembros del grupo pueden eliminarlos directamente [sin](https://support.microsoft.com/office/2207e468-ce1b-4c4a-a256-caf631d87af0) ser propietarios del grupo. Sin embargo, este es un paso manual que no proporciona ninguna ventaja adicional.

## <a name="onenote"></a>OneNote

El bloc OneNote de notas incluido en un grupo se almacena en la biblioteca activos del sitio dentro del sitio SharePoint asociado. Aunque a veces los archivos de bloc de notas se pueden propagar entre varios archivos individuales, no se pueden copiar y abrir de forma independiente. En su lugar, el contenido del bloc de notas OneNote debe moverse o exportarse mediante OneNote 2016.

**Mover páginas y secciones a otro bloc de notas**

[Mover páginas o secciones individualmente](https://support.office.com/article/c3c8b098-7f9c-4c2a-a0dc-ebb83bc76364) a otro bloc de notas ofrece a los propietarios la oportunidad de limpiar sus datos y tomar solo lo que se debe conservar.

**Exportar todo el bloc de notas como un paquete**

Si todo el bloc de notas necesita conservarse con su estructura existente, se puede exportar como un archivo de paquete OneNote y, a continuación, importarlo [a](https://support.office.com/article/a4b60da5-8f33-464e-b1ba-b95ce540f309) una nueva ubicación. En su lugar, se puede usar como método para conservar el contenido de un solo archivo en lugar de la estructura de varios archivos existente.

**Impresión en PDF**

En escenarios en los que solo es necesario conservar parte del contenido del bloc de notas como referencia o como registros, las páginas individuales se pueden imprimir en PDF y almacenarse en [otro lugar.](https://support.office.com/article/13d173b5-7f4c-45a8-94eb-9354d63af5cd)

## <a name="mailbox-and-calendar"></a>Buzón y calendario

No es raro que se utilice el buzón asociado al grupo, aunque muchas conversaciones se hayan llevado a cabo dentro de los canales de equipo. El buzón solo almacena mensajes de correo electrónico que se le enviaron directamente y no incluye correos electrónicos que se enviaron directamente a los canales.

En algunos casos, los correos electrónicos almacenados en el buzón pueden ser notificaciones de reuniones, actualizaciones de tareas de Planner y otros mensajes generados por la aplicación o el sistema. es importante que se revise el contenido del buzón para determinar si el contenido debe conservarse o eliminarse.

Si se aplica una directiva de retención en Exchange, los correos electrónicos y los elementos del calendario se conservan y están disponibles a través de búsquedas de exhibición de documentos electrónicos.

**Exportar correo y calendario**

Los miembros del equipo o del grupo pueden exportar el contenido del buzón y el calendario a un archivo [Outlook Data /Personal Storage (PST).](https://support.office.com/article/14252b52-3075-4e9b-be4e-ff9ef1068f91) A continuación, este archivo se puede almacenar en otro lugar o el contenido se puede importar a un buzón diferente. El primero no se recomienda, ya que el contenido del archivo PST no se puede buscar sin abrirlo en Outlook y el propio archivo puede dañarse con el tiempo.

**Migración de contenido realizada por IT**

Los administradores pueden usar herramientas de terceros para migrar el contenido del correo electrónico y el calendario entre buzones sin intervención del usuario. Una ubicación de almacenamiento potencial podría ser un buzón compartido creado exclusivamente para servir como "archivo" del contenido del buzón de grupo.

## <a name="planner"></a>Planner

Cada grupo o equipo puede tener varios planes. Es importante durante el proceso de baja para garantizar que los requisitos de retención se aborde para cada plan. Al igual que los otros servicios, hay varios enfoques para el contenido de fuera de la tabla en Planner.

**Exportar el plan a una hoja de cálculo**

Si solo es necesario conservar una copia del plan con fines de mantenimiento de registros, el enfoque más sencillo es exportar el plan a una hoja [de cálculo Excel archivo](https://support.microsoft.com/office/4d850c6e-e548-4aab-83b4-b62b68662d2a). Se trata de una acción unitiva: no hay ninguna opción para importar planes de una hoja de cálculo.

> [!IMPORTANT]
> La exportación de un plan Excel la mayor parte de la información del plan, pero no incluirá comentarios, vínculos ni archivos.

**Copiar y mover tareas a otro plan**

Aunque copiar o mover tareas a otro plan parece una solución, las tareas individuales solo se pueden copiar o mover entre [planes](https://support.microsoft.com/office/ad43a5d8-c1ad-42fd-b3da-fe97d72c8a1b) dentro del mismo grupo. Esto no hace una copia de seguridad de los datos si se elimina el grupo asociado al plan.

**Copiar plan completo**

También es posible copiar [todo el plan](https://support.microsoft.com/office/50401e13-a25f-40df-93c6-b608cc28c3d4). La copia no se puede realizar en un grupo existente. Al copiar el plan se creará un nuevo grupo. Además, copiar todo el plan no incluirá comentarios, asignaciones, vínculos, datos adjuntos o fechas.

## <a name="power-automate"></a>Power Automate

Los flujos creados Power Automate y asociados a un grupo o equipo no pertenecen al grupo. Son propiedad del creador y simplemente se comparten con otros usuarios y grupos. Por lo tanto, no se ven afectados si se elimina un grupo o equipo.

**Cambiar la propiedad del flujo**

Si el flujo necesita seguir funcionando, los propietarios pueden agregar otros usuarios o grupos Microsoft 365 como propietarios.

**Exportar el flujo**

Si el flujo no necesita seguir funcionando pero necesita conservarse para su [](https://flow.microsoft.com/blog/import-export-bap-packages/) posible uso futuro, se puede exportar como archivo e importarlo de nuevo más adelante.

## <a name="power-bi"></a>Power BI

Power BI datos y áreas de trabajo pueden funcionar independientemente de grupos y equipos y, al igual que otras cargas de trabajo, ofrecen diferentes formas de ser independientes.

**Copiar informes en otro área de trabajo**

Si necesita el informe una vez eliminado el grupo o el equipo, se puede copiar desde el área de trabajo existente a otro área de trabajo dentro [de Power BI](/power-bi/connect-data/service-datasets-copy-reports).

**Exportar datos desde un panel o informe**

En su lugar, si el informe ya no necesita estar activo pero los datos deben conservarse, se puede exportar [a Excel](/power-bi/visuals/power-bi-visualization-export-data).

## <a name="project"></a>Project

Los proyectos y los planes de ruta creados en Project web están asociados con grupos Microsoft 365 y tienen enfoques de salida similares a Power BI.

**Asignar el proyecto a otro grupo**

Si el proyecto necesita conservarse en su estado funcional más allá de la vida del grupo o equipo, se puede asignar a un grupo de Microsoft 365 [diferente.](/project-for-the-web/access-a-project-after-group-is-deleted#reassign-the-project) Esto se puede hacer con el Centro de administración de Dynamics 365.

**Exportar datos desde el proyecto o plan de desarrollo**

Con el Centro de administración de Dynamics 365, es posible exportar datos de usuario del [proyecto](/project-for-the-web/export-user-data-from-project-for-the-web) a una hoja de cálculo. Los datos también se pueden exportar a Project archivo (. MPP) y formatos de archivo XML mediante PowerShell.

## <a name="sharepoint"></a>SharePoint

Todos los archivos de los canales de grupo se almacenan en el SharePoint del grupo asociado. En algunos casos, puede haber contenido que no sea documentos SharePoint, como listas o páginas.

Por lo general, los archivos se almacenan en tres ubicaciones principales dentro de un SharePoint web:

- Páginas: biblioteca de páginas de sitio
- Imágenes usadas en páginas: biblioteca de activos del sitio
- Archivos en canales: biblioteca de documentos
- Páginas wiki: Teams de datos wiki

Si el sitio tiene uno o varios subsitios, el proceso de baja tendrá que repetirse para cada subsitio. Si el equipo contiene canales privados, hay un sitio SharePoint para cada canal.

Es importante al quitar archivos de un grupo o equipo para considerar que pueden compartirse con usuarios que no son miembros del grupo o equipo. Es posible que desee comunicarles el cambio inminente.

**Descargar archivos**

Los archivos almacenados SharePoint en una de las bibliotecas mencionadas anteriormente se pueden [descargar en un equipo local.](https://support.office.com/article/5c7397b7-19c7-4893-84fe-d02e8fa5df05)

**Mover archivos**

Además, los archivos se pueden mover a otra ubicación dentro [de SharePoint como una biblioteca en un sitio diferente.](https://support.office.com/article/00e2f483-4df3-46be-a861-1f5f0c1a87bc)

**Exportar lista**

Los datos almacenados en SharePoint pueden exportarse a una hoja Excel [de](https://support.office.com/article/bfb2ea48-6118-4fa9-abb6-cced9424e5d9)cálculo y volver a importarse a una lista de otro sitio.

Como alternativa, se puede usar una herramienta de terceros para migrar la lista entre sitios con el fin de conservar funciones, vistas de lista, formato y otros atributos.

**"Exportar" archivos wiki**

El contenido wiki dentro de los canales de grupo se almacena en un archivo con formato HTML en una biblioteca dedicada del sitio SharePoint asociado. No se pueden exportar e importar fácilmente a otro wiki de canal, pero se pueden convertir a un archivo HTML y abrirse como una página web.

## <a name="microsoft-stream"></a>Microsoft Stream

Al Power Automate, los vídeos de Stream asociados a un grupo o equipo no son realmente propiedad del grupo y no se eliminan cuando se elimina el grupo. Los vídeos de Stream son propiedad de la persona que carró o creó el vídeo, incluso si agregan usuarios o grupos como propietarios. Las reuniones grabadas en un Teams son propiedad de la persona que inició la grabación.

**Agregar otros propietarios**

Dado que el vídeo se conserva en Stream cuando se elimina el grupo, el propietario original puede compartir el vídeo con otros usuarios y grupos, incluso agregarlos [como propietarios.](/stream/portal-edit-video)

**Descargar el vídeo**

En escenarios en los que el vídeo no necesita conservarse en Stream o necesita almacenarse en una ubicación alternativa, como un sistema de administración de registros, un propietario puede descargarlo [localmente.](/stream/portal-download-video)

## <a name="yammer"></a>Yammer

A diferencia de las Microsoft Teams, Yammer ofrece opciones de usuarios y administradores para mover o exportar conversaciones.

**Mover conversaciones a otro grupo o comunidad**

Cualquier usuario puede mover las conversaciones Yammer otro grupo de usuarios, no solo propietarios o administradores. Esto es posible tanto en las interfaces [Yammer](https://support.office.com/article/149c6399-4ac1-4ced-84d7-e0660960a872) clásicas como en las [Yammer](https://support.office.com/article/d63debf1-1c90-4ec5-b5ae-8a00939a1680) nuevas.

**Exportar datos de red**

Yammer administradores de red [exportan datos de red](/yammer/manage-security-and-compliance/export-yammer-enterprise-data). Sin embargo, al hacerlo, se exportarán todas las conversaciones de toda la red. La exportación resultante muestra el identificador de grupo. Es posible filtrar conversaciones en función de este identificador.
