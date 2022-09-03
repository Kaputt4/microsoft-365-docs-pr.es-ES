---
title: Opciones de fin de ciclo de vida para grupos, equipos y Yammer
ms.reviewer: mmclean
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
recommendations: false
description: Opciones de fin de ciclo de vida para grupos, equipos y Yammer.
ms.openlocfilehash: a5240f0f9e38fe6f4a044ffa782cb7f536db7ffc
ms.sourcegitcommit: d3ef9391f621e8f4ca70661184b3bb82c6cbda94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2022
ms.locfileid: "67584714"
---
# <a name="end-of-lifecycle-options-for-groups-teams-and-yammer"></a>Opciones de fin de ciclo de vida para grupos, equipos y Yammer

Grupos de Microsoft 365 y Microsoft Teams funcionan con varios servicios conectados. Cuando se elimina un grupo o equipo, también se elimina la mayor parte de la información de los servicios conectados. En este artículo se describen las opciones para conservar la información moviendola fuera del grupo o equipo antes de la eliminación.

Una práctica común para los grupos o equipos que ya no son necesarios es mover los archivos del equipo y archivarlos en otra ubicación, como una biblioteca de documentos de SharePoint. Esta práctica se basa en un estilo heredado de trabajo donde la información se almacena en archivos y carpetas, y las comunicaciones se realizan por correo electrónico.

En la tabla siguiente se describen los servicios asociados a grupos y equipos y los tipos clave de contenido que se encuentran en cada uno de ellos:

|Servicio|Tipos de contenido|
|:------|:---------------|
|Teams|Conversaciones de canales, archivos en canales|
|Forms|Estructura y resultados de la encuesta|
|OneNote|Bloc de notas|
|Outlook|Correo y calendario|
|Planner|Estado del proyecto e información de tareas|
|Power Automate|Flujos de trabajo|
|Power BI|Datos, informes y paneles|
|Proyecto en la web|Planes de proyecto|
|Guía básica|Guías básicas|
|SharePoint|Archivos, listas, datos wiki del canal de Teams|
|Stream|Vídeos|
|Yammer|Conversaciones|

Al eliminar un grupo o un equipo, también se eliminan la mayoría de los recursos asociados. Entre las excepciones se incluyen:

- Los vídeos de Stream permanecen y son propiedad de la persona que los cargó o grabó.
- Los flujos de Power Automate permanecen y son propiedad de la persona que los creó.
- Los datos de proyecto y hoja de ruta de Project en la web permanecen en el CDS y se pueden restaurar por separado.

Los grupos y equipos permanecen en un estado de eliminación temporal durante 30 días y se pueden restaurar en cualquier momento. Sin embargo, después de los 30 días, se purgan del entorno de Microsoft 365 y de los recursos asociados, como servicios y contenido. Cualquier contenido protegido por una directiva de retención permanece disponible a través de búsquedas eDiscovery.

## <a name="end-of-life-cycle-considerations-for-group-connected-services"></a>Consideraciones sobre el ciclo de vida final de los servicios conectados a grupos

Hay tres áreas clave que los propietarios de equipos y grupos y los administradores de TI deben tener en cuenta al eliminar un grupo o un equipo.

**Contenido**

¿Es necesario conservar el contenido después de que el equipo ya no esté allí? ¿Es suficiente confiar en las funcionalidades de retención de Microsoft 365 o es parte del contenido de aplicaciones y servicios que no ofrecen retención? ¿Es necesario conservar el contenido con fines de administración de registros, archivado o uso y referencia futuros?

Para evitar posibles pérdidas de datos, estas preguntas deben hacerse antes de que cualquier equipo se archive o elimine.

**Servicios**

¿Es necesario que el contenido permanezca en su forma de trabajo actual? Por ejemplo, ¿el informe de Power BI debe seguir siendo accesible? ¿Es necesario que los resultados del formulario estén disponibles en la vista de resumen visual? ¿Las listas de SharePoint están vinculadas o incrustadas en cualquier lugar?

Estas preguntas deben hacerse antes de eliminar el grupo subyacente porque es posible que la exportación del contenido no sea suficiente.

**Invitados**

Cuando se invita a los invitados a un equipo, se crea una cuenta de invitado en Azure Active Directory de la organización host antes de agregarlos al equipo. Cuando se elimina un equipo, los invitados no se quitan de Azure Active Directory. Aunque los invitados no pueden acceder a grupos, sitios, equipos o contenido que no se haya compartido con ellos, pueden seguir usando características dentro de Microsoft Teams, como el inicio de chats, llamadas de voz y vídeo y el uso de aplicaciones.

Un propietario de grupo o equipo puede invitar a alguien de fuera de la organización para que se convierta en invitado en Azure Active Directory agregándolos a un equipo. Sin embargo, un propietario del equipo no puede quitar al invitado de Azure Active Directory. La eliminación de cuentas solo la puede realizar un administrador global o un administrador de usuarios.

Es importante realizar revisiones de invitado y saber si los invitados deben quitarse de Azure Active Directory tras la eliminación del equipo. Puede haber un caso válido para que los invitados permanezcan en el directorio, como ser miembro de otros equipos o usar otros servicios de Microsoft 365 o Azure.

## <a name="teams"></a>Teams

El contenido específico de Teams se encuentra principalmente en forma de conversaciones.

Las conversaciones en canales no se pueden copiar ni mover mediante la funcionalidad nativa de Microsoft Teams. Sin embargo, se pueden exportar mediante el Graph API.

Además, si se aplica una directiva de retención a Teams, las conversaciones se conservan y están disponibles a través de búsquedas de exhibición de documentos electrónicos. Con eDiscovery (Premium) puede [reconstruir una conversación de chat de Teams](/microsoft-365/compliance/conversation-review-sets).


### <a name="archiving-a-team"></a>Archivado de un equipo

La ventaja de [archivar un equipo](/microsoftteams/archive-or-delete-a-team) es que proporciona acceso completo al equipo tal y como estaba. Los usuarios todavía pueden examinar las conversaciones del canal y abrir archivos incluso si no están activos. Además, los equipos pueden no serarchivos si es necesario seguir trabajando en ellos (por ejemplo, si se extiende un proyecto).

Cuando un propietario archiva un equipo, se establece en solo lectura para los miembros, tanto para el contenido dentro del equipo como para el sitio de SharePoint asociado, si está seleccionado. El objetivo de esta acción es asegurarse de que las conversaciones en los canales se conservan en su estado existente, junto con contenido basado en SharePoint, como archivos y wikis.

En el sitio de SharePoint no hay cambios visibles. Sin embargo, no se puede realizar ningún cambio en ningún archivo o lista porque los permisos de SharePoint para el grupo de Microsoft 365 están establecidos en **Visitantes del sitio**. Esto incluye el cuaderno de OneNote para el equipo, que se almacena en la biblioteca Recursos del sitio dentro del sitio de SharePoint.

Cuando se archiva un equipo, el grupo subyacente de Microsoft 365 sigue estando sujeto a la directiva de expiración (si se establece) y, como tal, el propietario debe continuar renovando el equipo.

Aunque las conversaciones de canal del equipo y el contenido del sitio de SharePoint se establecen en solo lectura, no se aplica lo mismo a otros servicios asociados:

- Los cubos y las tareas de Planner todavía se pueden crear, modificar y eliminar.
- Los formularios todavía pueden recibir envíos.
- El buzón de Outlook todavía puede recibir correos electrónicos.
- Los paneles, informes y datos de Power BI todavía se pueden modificar.
- Los proyectos y los planes de desarrollo todavía se pueden editar en Project en la web.
- Los vídeos todavía se pueden cargar, modificar y eliminar en Stream.
- Los flujos de Power Automate todavía se pueden crear, modificar, eliminar y continuar ejecutándose. (No obstante, producirán un error si es necesario publicar un mensaje en un canal del equipo archivado).

## <a name="forms"></a>Forms

Aunque un formulario se puede mover de una cuenta individual a un grupo, no se puede mover ni copiar de un grupo a otro. Hay tres opciones disponibles para un formulario cuando se elimina un equipo.

**Duplicar el formulario**

Los formularios se pueden [compartir como plantillas](https://support.microsoft.com/office/82ea9d8a-260a-47a0-afdb-497f3d746e3f), lo que permite a otros usuarios copiarlos en su propia cuenta o grupo. Esto no conserva los datos de los envíos de resultados; estructura de formulario, como preguntas y configuración.

**Exportación de resultados a una hoja de cálculo**

Si es necesario conservar los datos de las respuestas del formulario, esto se puede lograr [exportando los resultados a una hoja de cálculo de Excel](https://support.office.com/article/02859424-341d-406f-b32a-9a0fbaf357af). Esto solo exportará las preguntas y sus respuestas como datos; no incluye los gráficos creados por Forms.

**Eliminar el formulario**

Aunque la eliminación del grupo también dará lugar a la eliminación de los formularios asociados, los miembros del grupo pueden [eliminarlos directamente](https://support.microsoft.com/office/2207e468-ce1b-4c4a-a256-caf631d87af0) sin ser propietarios del grupo. Sin embargo, se trata de un paso manual que no proporciona ninguna ventaja adicional.

## <a name="onenote"></a>OneNote

El cuaderno de OneNote incluido en un grupo se almacena en la biblioteca Recursos del sitio dentro del sitio de SharePoint asociado. Aunque los archivos de cuaderno a veces se pueden distribuir entre varios archivos individuales, no se pueden copiar ni abrir de forma independiente. En su lugar, el contenido del cuaderno de OneNote se debe mover o exportar mediante el cliente de escritorio de OneNote.

**Traslado de páginas y secciones a otro cuaderno**

[Mover páginas o secciones individualmente a otro cuaderno proporciona a](https://support.office.com/article/c3c8b098-7f9c-4c2a-a0dc-ebb83bc76364) los propietarios la oportunidad de limpiar sus datos y tomar solo lo que se debe conservar.

**Exportación de todo el cuaderno como paquete**

Si es necesario conservar todo el cuaderno con su estructura existente, se puede [exportar como un archivo de paquete de OneNote](https://support.office.com/article/a4b60da5-8f33-464e-b1ba-b95ce540f309) y, a continuación, importarlo a una nueva ubicación. En su lugar, esto se puede usar como método para conservar el contenido en un único archivo en lugar de la estructura de varios archivos existente.

**Impresión en PDF**

En escenarios en los que solo es necesario conservar parte del contenido del cuaderno como referencia o como registros, las páginas individuales se pueden [imprimir en PDF y almacenarse en otro lugar](https://support.office.com/article/13d173b5-7f4c-45a8-94eb-9354d63af5cd).

## <a name="mailbox-and-calendar"></a>Buzón de correo y calendario

No es raro que se use el buzón asociado al grupo, aunque muchas conversaciones se hayan llevado a cabo dentro de los canales del equipo. El buzón solo almacena los correos electrónicos que se le enviaron por correo electrónico directamente y no incluye los correos electrónicos que se enviaron directamente a los canales.

En algunos casos, los correos electrónicos almacenados en el buzón pueden ser notificaciones de reuniones, actualizaciones de tareas de Planner y otros mensajes generados por la aplicación o por el sistema. es importante que se revise el contenido del buzón para determinar si se debe conservar o eliminar el contenido.

Si se aplica una directiva de retención en Exchange, los correos electrónicos y los elementos de calendario se conservan y están disponibles a través de búsquedas de exhibición de documentos electrónicos.

**Exportar correo y calendario**

Los miembros del equipo o grupo pueden [exportar el contenido del buzón de correo y el calendario a un archivo de datos o almacenamiento personal (PST) de Outlook](https://support.office.com/article/14252b52-3075-4e9b-be4e-ff9ef1068f91). Este archivo se puede almacenar en otro lugar o el contenido se puede importar en otro buzón. El primero no se recomienda, ya que el contenido del archivo PST no se puede buscar sin abrirlo en Outlook, y el propio archivo puede dañarse con el tiempo.

**Migración de contenido realizada por TI**

Los administradores pueden usar herramientas de terceros para migrar el contenido de correo electrónico y calendario entre buzones sin intervención del usuario. Una posible ubicación de almacenamiento podría ser un buzón compartido creado únicamente para servir como "archivo" del contenido del buzón de grupo.

## <a name="planner"></a>Planner

Cada grupo o equipo puede tener varios planes. Es importante durante el proceso de eliminación para asegurarse de que se aborden los requisitos de retención para cada plan. Al igual que los demás servicios, hay varios enfoques para el contenido fuera de la placa en Planner.

**Exportación del plan a una hoja de cálculo**

Si solo es necesario conservar una copia del plan con fines de mantenimiento de registros, el enfoque más sencillo es [exportar el plan a una hoja de cálculo de Excel](https://support.microsoft.com/office/4d850c6e-e548-4aab-83b4-b62b68662d2a). Se trata de una acción unidireccional: no hay ninguna opción para importar planes desde una hoja de cálculo.

> [!IMPORTANT]
> La exportación de un plan a Excel tomará la mayor parte de la información del plan, pero no incluirá comentarios, vínculos ni archivos.

**Copia y traslado de tareas a otro plan**

Aunque copiar o mover tareas a otro plan parece una solución, las tareas individuales solo se pueden [copiar o mover entre planes](https://support.microsoft.com/office/ad43a5d8-c1ad-42fd-b3da-fe97d72c8a1b) del mismo grupo. Esto no hará una copia de seguridad de los datos si se elimina el grupo asociado al plan.

**Copia de todo el plan**

También es posible [copiar todo el plan](https://support.microsoft.com/office/50401e13-a25f-40df-93c6-b608cc28c3d4). La copia no se puede realizar en un grupo existente. Al copiar el plan, se creará un nuevo grupo. Además, la copia de todo el plan no incluirá comentarios, asignaciones, vínculos, datos adjuntos ni fechas.

## <a name="power-automate"></a>Power Automate

Los flujos creados en Power Automate y asociados a un grupo o equipo no pertenecen al grupo. Son propiedad del creador y simplemente se comparten con otros usuarios y grupos. Por lo tanto, no se ven afectados si se elimina un grupo o equipo.

**Cambiar la propiedad del flujo**

Si el flujo necesita seguir funcionando, los propietarios pueden agregar otros usuarios o grupos de Microsoft 365 como propietarios.

**Exportación del flujo**

Si el flujo no necesita continuar funcionando, pero debe conservarse para un posible uso futuro, se puede [exportar como un archivo](https://flow.microsoft.com/blog/import-export-bap-packages/) e importarlo de nuevo más adelante.

## <a name="power-bi"></a>Power BI

Los datos y áreas de trabajo de Power BI pueden funcionar de forma independiente de grupos y equipos y, al igual que otras cargas de trabajo, ofrecen diferentes formas de desconectarse.
Las áreas de trabajo clásicas de Power BI están asociadas a un grupo de Microsoft 365, mientras que las áreas de trabajo modernas no lo son y simplemente pueden compartir su contenido con el grupo (similar a un flujo).

**Copia de informes en otro área de trabajo**

Si necesita el informe una vez eliminado el grupo o el equipo, se puede [copiar del área de trabajo existente a otra área de trabajo de Power BI](/power-bi/connect-data/service-datasets-copy-reports).

**Exportación de datos desde un panel o informe**

En su lugar, si el informe ya no necesita estar activo, pero los datos deben conservarse, se puede [exportar a Excel](/power-bi/visuals/power-bi-visualization-export-data).

## <a name="project"></a>Project

Los proyectos y las hojas de ruta creados en Project for the Web están asociados a grupos de Microsoft 365 y tienen enfoques de retirada similares a Power BI.

**Asignar el proyecto a otro grupo**

Si el proyecto debe conservarse en su estado funcional más allá de la vida del grupo o equipo, se puede [asignar a otro grupo de Microsoft 365](/project-for-the-web/access-a-project-after-group-is-deleted#reassign-the-project). Esto se puede hacer mediante el Centro de administración de Dynamics 365.

**Exportación de datos desde el proyecto o la hoja de ruta**

Con el Centro de administración de Dynamics 365, es posible [exportar datos de usuario del proyecto](/project-for-the-web/export-user-data-from-project-for-the-web) a una hoja de cálculo. Los datos también se pueden exportar al archivo project (. MPP) y formatos de archivo XML mediante PowerShell.

## <a name="sharepoint"></a>SharePoint

Todos los archivos de los canales de equipo se almacenan en el sitio de SharePoint del grupo asociado. En algunos casos, puede haber contenido distinto de los documentos en SharePoint, como listas o páginas.

Por lo general, los archivos se almacenan en tres ubicaciones principales dentro de un sitio de SharePoint:

- Páginas: biblioteca de páginas de sitio
- Imágenes usadas en páginas: biblioteca de recursos de sitio
- Archivos en canales: biblioteca de documentos
- Páginas wiki: biblioteca de datos wiki de Teams

Si el sitio tiene uno o varios subsitios, el proceso de eliminación deberá repetirse para cada subsitio. Si el equipo contiene canales privados o compartidos, hay un sitio de SharePoint independiente para cada canal.

Es importante al quitar archivos de un grupo o equipo para tener en cuenta que pueden compartirse con usuarios que no son miembros del grupo o equipo. Es posible que quiera comunicarles el cambio inminente.

**Se descargan los archivos**

Los archivos almacenados en SharePoint en una de las bibliotecas mencionadas anteriormente se pueden [descargar en un equipo local](https://support.office.com/article/5c7397b7-19c7-4893-84fe-d02e8fa5df05).

**Mover archivos**

Además, los archivos se pueden [mover a otra ubicación dentro de SharePoint, como una biblioteca en otro sitio](https://support.office.com/article/00e2f483-4df3-46be-a861-1f5f0c1a87bc).

**Lista de exportación**

Los datos almacenados en listas de SharePoint se pueden [exportar a una hoja de cálculo de Excel](https://support.office.com/article/bfb2ea48-6118-4fa9-abb6-cced9424e5d9) e importarse de nuevo a una lista de otro sitio.

Como alternativa, Power Automate o una herramienta de terceros se pueden usar para migrar la lista entre sitios con el fin de conservar la función, las vistas de lista, el formato y otros atributos.

**"Exportar" archivos wiki**

El contenido de wiki dentro de los canales de equipo se almacena en un archivo con formato HTML en una biblioteca dedicada del sitio de SharePoint asociado. No se pueden exportar e importar fácilmente a otra wiki de canal, pero se pueden convertir en un archivo HTML y abrirse como una página web.

## <a name="microsoft-stream"></a>Microsoft Stream

Al igual que Power Automate, los vídeos de Stream asociados a un grupo o equipo no son realmente propiedad del grupo y no se eliminan cuando se elimina el grupo. Los vídeos de Stream son propiedad de la persona que cargó o creó el vídeo, incluso si agregan usuarios o grupos como propietarios. Las reuniones grabadas en un canal de Teams son propiedad de la persona que inició la grabación.

**Adición de otros propietarios**

Dado que el vídeo se conserva en Stream cuando se elimina el grupo, el propietario original puede [compartir el vídeo con otros usuarios y grupos, incluso agregarlos como propietarios](/stream/portal-edit-video).

**Descargar el vídeo**

En escenarios en los que el vídeo no necesita conservarse en Stream o debe almacenarse en una ubicación alternativa, como un sistema de administración de registros, un propietario puede [descargarlo localmente](/stream/portal-download-video).

## <a name="yammer"></a>Yammer

A diferencia de las conversaciones de Microsoft Teams, Yammer ofrece a los usuarios y administradores opciones para mover o exportar conversaciones.

**Mover conversaciones a otro grupo o comunidad**

Cualquier usuario, no solo propietarios o administradores, puede mover las conversaciones a otro grupo de Yammer. Esto es posible tanto en las interfaces [clásicas de Yammer](https://support.office.com/article/149c6399-4ac1-4ced-84d7-e0660960a872) como en las [nuevas de Yammer](https://support.office.com/article/d63debf1-1c90-4ec5-b5ae-8a00939a1680) .

**Exportación de datos de red**

Los administradores de red de Yammer [exportan datos de red](/yammer/manage-security-and-compliance/export-yammer-enterprise-data). Sin embargo, si lo hace, se exportarán todas las conversaciones de toda la red. La exportación resultante muestra el identificador de grupo. Es posible filtrar las conversaciones en función de este identificador.

## <a name="related-topics"></a>Temas relacionados

[Quitar un antiguo empleado y proteger los datos](/microsoft-365/admin/add-users/remove-former-employee)
