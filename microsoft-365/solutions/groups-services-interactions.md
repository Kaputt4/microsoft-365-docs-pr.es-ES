---
title: Interacciones de servicios de grupos
ms.reviewer: ''
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
description: Interacciones de servicios de grupos
ms.openlocfilehash: 331c30c86481b1729251c685de2d663fb14f390b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921029"
---
# <a name="groups-services-interactions"></a>Interacciones de servicios de grupos

Grupos de Microsoft 365 proporciona un tejido común para una serie de servicios y cargas de trabajo dentro de la plataforma de Microsoft 365 para ofrecer una experiencia conectada para los usuarios finales. En su núcleo, existe un grupo de Microsoft 365 para proporcionar:

- Una forma de administrar la pertenencia (Azure AD)
- Un lugar para que se lleve a cabo la mensajería y las conversaciones (buzón de Exchange, Microsoft Teams, Yammer)
- Un lugar para que los archivos se almacenen (SharePoint)
- Un calendario para la programación (Exchange)
- Bloc de notas para capturar notas (OneNote)

En el punto de creación de grupos, también se aprovisionan otros recursos, pero no son visibles hasta que se accede por primera vez desde el servicio:

- Un panel para administrar tareas de grupo (Planner)
- Un área de trabajo para informes (Power BI)
- Un área para vídeos compartidos (Microsoft Stream)
- Un área para formularios compartidos (formularios)

En Microsoft 365, otros servicios pueden interactuar con grupos de Microsoft 365 para ofrecer funcionalidades y funcionalidades adicionales a los miembros del grupo.
Algunos ejemplos de esto son:

- Power Apps para aplicaciones
- Power Automate para flujos de trabajo
- Project on the web y Roadmap for waterfall-based project management
- Teams para conversaciones basadas en canal
- Yammer para comunidades de interés

## <a name="user-interactions-with-groups"></a>Interacciones del usuario con grupos

Los grupos de Microsoft 365 se pueden crear y administrar desde una variedad de interfaces, tanto por administradores como por usuarios finales. 

### <a name="administrative-experiences"></a>Experiencias administrativas

Los administradores pueden crear y administrar grupos de Microsoft 365 desde varios de los centros de administración de cargas de trabajo, interfaces de línea de comandos que admiten scripting, así como aplicaciones personalizadas que interactúan con la API de Graph. La única excepción a esto son los grupos de Yammer, que deben crearse desde la interfaz web de Yammer.

**Configuración relacionada**

En las distintas interfaces administrativas que pueden administrar la configuración de grupo existen varias superposiciones que debe tener en cuenta.

**Centro de administración de Microsoft 365**

En el Centro de administración de Microsoft 365, el acceso de invitado a grupos está habilitado de forma predeterminada, al igual que la capacidad de permitir que los propietarios agreguen invitados. No hay más controles de nivel de organización disponibles para grupos desde este centro de administración.

**Centro de administración de Azure AD**

El Centro de administración de Azure AD ofrece controles sobre si los usuarios pueden crear grupos o asignar propietarios en Azure Portals, así como la configuración de la directiva de expiración y nomenclatura.

El Centro de administración también proporciona una serie de medidas de control de invitaciones de invitado que van más allá de las del Centro de administración de Microsoft 365, como la capacidad de limitar si los no propietarios también pueden invitar invitados

**SharePoint**

Los sitios de SharePoint se crean con grupos de seguridad propietarios, miembros y visitantes, y los dos primeros coinciden con sus equivalentes de grupo de Microsoft 365. Aunque el grupo asociado de Microsoft 365 suele administrar la pertenencia a sitios de SharePoint Online, no es una relación bidireccional. Cualquier cambio en la pertenencia en el nivel de grupo de Microsoft 365 se refleja en SharePoint, pero si se cambia la pertenencia en el grupo de SharePoint, esto no se refleja en el grupo de Microsoft 365.

### <a name="user-experiences"></a>Experiencias de usuario

Los usuarios finales pueden crear grupos a partir de varios de los servicios de Microsoft 365 y, en otros, solo pueden compartir con un grupo.

Los siguientes servicios permiten la creación de grupos por usuarios finales:
                         
Outlook Planner Project para web SharePoint Stream Microsoft Teams Yammer

**Restricción de creación de grupos**

Un enfoque común para controlar la expansión de los equipos es limitar los usuarios que pueden crearlos. Esto solo se puede hacer limitando la creación de grupos. Esto afecta a la capacidad de crear grupos desde otros servicios cuando esto puede ser necesario para el usuario final. Grupos de Microsoft 365 no admite la capacidad de restringir la creación de grupos desde algunas aplicaciones o servicios mientras se permite desde otras.

La experiencia de restricción de creación de grupos varía entre aplicaciones y servicios:


|Aplicación o servicio|Experiencia|
|:-------------|:---------|
|Outlook|**La nueva opción** de grupo se quita del menú Nuevo en la página personas|
|Planner|**El nuevo plan** explica que la creación de grupos se ha desactivado y ofrece agregar el plan a un grupo existente|
|Project for the web and Roadmap|**El menú** Crear grupo explica que la creación de grupos está restringida y sugiere el uso de un grupo existente.|
|SharePoint|Sigue siendo capaz de crear un sitio de grupo que no esté conectado a un grupo.|
|Stream|**La** opción Grupo no aparece en el **menú Crear**.|
|Teams|El usuario no puede crear un equipo con un grupo nuevo, pero puede crear un equipo que use un grupo existente.<br><br>**Crear un botón** de equipo se reemplaza por **Crear equipo desde un grupo.**|
|Yammer|**Crear una opción de** grupo se quita de la navegación grupos/comunidades principales.|

## <a name="services-interactions-with-groups"></a>Interacciones de servicios con grupos

Vea el póster Grupos en Microsoft 365 para obtener información sobre los distintos tipos de grupos, cómo se crean y administran, y algunas recomendaciones de gobierno.

[![Imagen en miniatura para la infografía de grupos](../downloads/msft-m365-groups-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf)

[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-groups.vsdx)

En la tabla siguiente se proporciona información general sobre las interacciones de grupos de Microsoft 365 con varios servicios:

|Producto|Características|¿El servicio<br>existen sin un grupo.|¿Puede el servicio?<br>crear un grupo|Elimina la<br>instancia eliminar el grupo?|
|:---|:---|:---|:---|:---|
|Azure AD|Pertenencia, Controles de grupo, Invitados|Sí|Sí|Sí|
|Exchange|Calendario, buzón|Sí|Sí|Sí|
|Formularios|Form|Sí|No|No|
|OneNote|Bloc de notas|Sí|No|No|
|Planner|Panel de tareas|No|Sí|Sí|
|Aplicación de Power Apps|Aplicación|Sí|No|No|
|Power Automate|Flujo de trabajo|Sí|No|No|
|Power BI (clásico)|Workspace|No|Sí|Sí|
|Power BI (nuevo)|Workspace|Sí|No|Sí|
|Project para la Web|Plan de proyecto|Sí|Sí|No|
|Guía básica|Guía básica|Sí|Sí|No|
|SharePoint|Site|Sí|Sí|Sí|
|Stream|Canal, vídeo|Sí|Sí|Sí|
|Teams|Equipo|No|Sí|Sí|
|Yammer|Group|Sí|Sí|Sí|

Aunque la tabla anterior proporciona una introducción general de alto nivel de las interacciones de grupo con los servicios de Microsoft 365, hay una serie de matices e complejidades que debe comprender. En las secciones siguientes se hace un análisis más detallado de las cargas de trabajo específicas y sus interacciones con los grupos.

## <a name="azure-ad"></a>Azure AD

Azure AD proporciona las capacidades de administración de identidades subyacentes en Microsoft 365.

**Características clave proporcionadas a grupos**

- Pertenencia a grupos
- Directiva de nomenclatura
- Directiva de expiración
- Invitados
- Restricción de creación de grupos

**¿Puede Azure AD crear un grupo?**

Sí, los grupos de Microsoft 365 se pueden crear desde Azure AD a través del portal web de administración, a través de PowerShell o la API de Graph.

**¿Azure AD existe sin un grupo?**

Sí, Azure AD realiza un gran número de servicios que no tienen relación con grupos de Microsoft 365. Cada grupo de Microsoft 365 se representa como un objeto en Azure AD.

**¿Puede haber varias instancias de Azure AD por grupo?**

No, solo hay una instancia de Azure AD.

**¿Azure AD se puede asociar a varios grupos?**

Sí, porque Azure AD es la plataforma subyacente que proporciona el servicio de pertenencia a grupos.

**¿Puede cambiar la asociación de Azure AD con un grupo?**

No, Azure AD es la plataforma subyacente donde existen grupos.

**¿Elimina la instancia el grupo?**

Al eliminar el grupo en Azure AD, se eliminará el contenido y los servicios asociados al grupo correspondientes.

## <a name="teams"></a>Teams

Teams es un área de trabajo centrada en el chat destinada a mejorar la colaboración proporcionando una interfaz singular para interactuar con una variedad de servicios de Microsoft y de terceros.

De forma predeterminada, cuando se crea un equipo, el buzón y el calendario asociados con el grupo de Microsoft 365 se ocultan tanto en la lista global de direcciones de Exchange como en Outlook. Un administrador puede invalidar esto manualmente si el usuario desea usar Outlook y Teams en el mismo grupo de Microsoft 365.

**Características clave proporcionadas a grupos**

- Conversaciones
- Canales & pestañas
- Reuniones

**¿Puede Teams crear un grupo?**

Sí, la creación de un nuevo equipo creará un nuevo grupo de Microsoft 365. También es posible crear un equipo para un grupo existente que no tenga uno actualmente.

**¿Existen equipos sin un grupo?**

No, no es posible que un equipo exista sin un grupo.

**¿Puede haber varios equipos por grupo?**

No, la relación entre un equipo y un grupo es 1:1.

**¿Se puede asociar un equipo a varios grupos?**

No, el equipo en sí solo puede asociarse con un solo grupo.

**¿Puede cambiar la asociación de un equipo con un grupo?**

No, el equipo solo se puede asociar al grupo al que estaba asociado originalmente.

**¿Elimina el equipo el grupo?**

Sí, al eliminar el equipo de Microsoft Teams se eliminará el grupo, los servicios asociados al grupo y el contenido.

## <a name="exchange"></a>Exchange

Exchange Online proporciona mensajería, calendario, contacto y funcionalidad asociada. En el contexto de un grupo, solo se asocia un único recurso, en lugar de una instancia de servicio completa.

**Características clave proporcionadas a grupos**

- Buzón y calendario
- Capacidad de enviar un correo electrónico a todos los miembros del grupo
- Almacenamiento de conversaciones de canal de Teams con fines de exhibición de documentos electrónicos, comentarios de Planner

**¿Puede Exchange crear un grupo?**

Sí, es posible crear un grupo desde el Centro de administración de Exchange Online, así como desde Outlook. También puede convertir listas de distribución de Exchange a grupos de Microsoft 365.

**¿Existe Exchange sin un grupo?**

Sí, Exchange Online proporciona una serie de servicios, incluidos los buzones y calendarios compartidos, sin ninguna asociación de grupo.

**¿Puede haber varias instancias de buzones o calendarios de Exchange por grupo?**

No, solo puede haber un único buzón y calendario de Exchange Online para un grupo.

**¿Los buzones y calendarios de Exchange se pueden asociar a varios grupos?**

No, el buzón y el calendario tienen una relación 1:1 con el grupo. Es posible compartir el buzón con otros usuarios o grupos, pero esto no establece ninguna forma de asociación de servicio.

**¿Puede cambiar la asociación del buzón de Exchange o del calendario con un grupo?**

No, el buzón y el calendario no se pueden cambiar a un grupo diferente. Sin embargo, el contenido se puede mover de un buzón a otro dentro de Outlook o mediante una herramienta de terceros.

**¿Elimina el buzón de correo el grupo?**

Sí, al eliminar el buzón en Exchange se eliminará el grupo, así como los servicios y el contenido asociados al grupo.

## <a name="forms"></a>Formularios

Forms proporciona encuestas y cuestionarios basados en web.

**Características clave proporcionadas a grupos**

- Propiedad de los formularios

**¿Pueden los formularios crear un grupo?**

No, Forms no puede crear un grupo.

**¿Existen formularios sin un grupo?**

Sí, las encuestas y los cuestionarios se pueden crear directamente en la cuenta de un usuario final.

**¿Puede haber varios formularios por grupo?**

Sí, puede haber varios formularios asociados a un grupo.

**¿Los formularios se pueden asociar a varios grupos?**

No, un formulario solo se puede asociar a un único grupo.

**¿Puede cambiar la asociación de un formulario con un grupo?**

No, una vez que un formulario está asociado a un grupo (ya sea creado directamente dentro o la propiedad transferida de un individuo) no se puede mover a otro grupo.

**¿Elimina el formulario el grupo?**

No, no es posible eliminar un grupo de la interfaz formularios, solo formularios individuales.

## <a name="onenote"></a>OneNote

OneNote es una aplicación de bloc de notas digital. El bloc de notas de OneNote creado con un grupo es un archivo en el sitio de SharePoint asociado en lugar de un servicio conectado a un grupo.

**Características clave proporcionadas a grupos**

- Bloc de notas compartido (almacenado en la biblioteca de SharePoint asociada al grupo)

**¿Puede OneNote crear un grupo?**

No, la aplicación de OneNote no puede crear un grupo.

**¿Existen blocs de notas de OneNote sin un grupo?**

Sí, los blocs de notas se pueden crear directamente en OneDrive o en otras ubicaciones compartidas.

**¿Puede haber varios blocs de notas de OneNote por grupo?**

Sí, un bloc de notas se crea de forma predeterminada y se pueden agregar otros, pero cualquier vínculo a OneNote desde los servicios asociados al grupo siempre irá al bloc de notas predeterminado.

**¿Se puede asociar un bloc de notas de OneNote a varios grupos?**

No, el bloc de notas se almacena en la biblioteca de sitios de SharePoint asociada al grupo y se vincula desde varias interfaces. Sin embargo, se puede compartir con otros grupos de la misma manera que se puede compartir con individuos.

**¿Puede cambiar la asociación del bloc de notas con un grupo?**

No, el propio bloc de notas está asociado al grupo y se puede acceder directamente desde otros servicios conectados a grupos, pero el contenido se puede mover de un bloc de notas a otro dentro de la aplicación de OneNote.

**¿Elimina el bloc de notas el grupo?**

No, sin embargo, si se elimina el bloc de notas de OneNote, puede haber vínculos rotos en algunos de los servicios asociados al grupo.

## <a name="planner"></a>Planner

Planner es un servicio ligero de administración de tareas de grupo.

**Características clave proporcionadas a grupos**

- Junta para administrar tareas de grupo

**¿Planner puede crear un grupo?**

Sí, la creación de un plan creará un nuevo grupo.

**¿Existe un consejo de Planner sin un grupo?**

No, un plan debe estar asociado a un grupo.

**¿Puede haber varios planes por grupo?**

Sí, puede haber varios planes por grupo.

**¿Se puede asociar un plan a varios grupos?**

No, un plan se basa únicamente en la pertenencia a grupos para determinar el acceso.

**¿Puede cambiar la asociación de un plan con un grupo?**

No, sin embargo, al copiar un plan se crea un nuevo grupo.

> [!NOTE]
> Un grupo creado por cualquier otra aplicación no se mostrará automáticamente en Planner para un usuario. Para tener acceso al tablero inicialmente, tendrán que abrirlo desde otra interfaz basada en grupo, como Outlook.

**¿Elimina el plan el grupo?**

Sí, al eliminar el plan se eliminará el contenido y los servicios asociados al grupo.

## <a name="power-apps"></a>Power Apps

Power Apps proporciona un lienzo para el desarrollo de aplicaciones sin código.

**Características clave proporcionadas a grupos**

- Las aplicaciones se pueden compartir con un grupo que se va a ejecutar y modificar

**¿Power Apps puede crear un grupo?**

No, Power Apps no puede crear un grupo de Microsoft 365.

**¿Existen Power Apps sin un grupo?**

Sí, las aplicaciones se pueden crear en Power Apps y residir en la cuenta de creadores hasta que se compartan o publiquen.

**¿Puede haber varias aplicaciones por grupo?**

Sí, puede haber varias aplicaciones compartidas con un grupo.

**¿Las aplicaciones se pueden asociar a varios grupos?**

Sí, una aplicación se puede compartir con varios grupos.

**¿Puede cambiar la asociación de una aplicación con un grupo?**

Sí, como la asociación entre Power Apps y un grupo de Microsoft 365 solo está compartiendo; la aplicación sigue residiendo con el creador.

> [!IMPORTANT]
> [Los grupos deben estar habilitados para que las aplicaciones puedan compartirse con ellos.](/powerapps/maker/canvas-apps/share-app#share-an-app-with-office-365-groups)

**¿Elimina la aplicación el grupo?**

No, las aplicaciones no están conectadas al grupo que no se compartan con ellas.

## <a name="power-automate"></a>Power Automate

Power Automate (anteriormente conocido como Microsoft Flow) proporciona flujos de trabajo y servicios de automatización.

**Características clave proporcionadas a grupos**

- Los flujos de trabajo se pueden compartir con un grupo que se va a ejecutar y modificar.

**¿Power Automate puede crear un grupo?**

No, Power Automate no puede crear un grupo de Microsoft 365 en el contexto de asociarse a uno.

Sin embargo, es posible crear un flujo que realice varias operaciones, como crear un grupo de seguridad de Azure AD o actualizar la pertenencia a un grupo de Microsoft 365.

**¿Existen flujos sin un grupo?**

Sí, los flujos se pueden crear en Power Automate y residir en la cuenta de creadores hasta que se compartan o publiquen.

**¿Puede haber varios flujos por grupo?**

Sí, puede haber varios flujos compartidos con un grupo.

**¿Se puede asociar un flujo a varios grupos?**

Sí, un flujo se puede compartir con varios grupos.

**¿Puede cambiar la asociación de un flujo con un grupo?**

Sí, como la asociación entre Power Automate y un grupo de Microsoft 365 solo está compartiendo; el flujo sigue residiendo con el creador.

**¿Elimina un flujo el grupo?**

No, al igual que Power Apps, los flujos no están conectados al grupo que no se compartan con ellos.

## <a name="power-bi-classic"></a>Power BI (clásico)

Power BI proporciona paneles e informes interactivos controlados por datos.

**Características clave proporcionadas a grupos**

- Informes de datos

**¿Power BI puede crear un grupo?**

Sí, la creación de un área de trabajo clásica creará un grupo de Microsoft 365.

**¿Existe un área de trabajo clásica de Power BI sin un grupo?**

No, [un área de trabajo clásica de Power BI debe estar asociada a un grupo](/power-bi/collaborate-share/service-collaborate-power-bi-workspace).

**¿Puede haber varias áreas de trabajo de Power BI por grupo?**

No, la relación entre un área de trabajo clásica y un grupo es 1:1.

**¿Se puede asociar un área de trabajo a varios grupos?**

Técnicamente no, mientras que el área de trabajo clásica se crea con el grupo, el contenido se puede compartir fuera del grupo con usuarios y grupos de seguridad.

**¿Puede cambiar la asociación del área de trabajo con un grupo?**

No, el área de trabajo clásica en sí está asociada al grupo, pero el contenido se puede mover de un área de trabajo a otra dentro de la interfaz de Power BI o exportando contenido localmente.

**¿Elimina el área de trabajo el grupo?**

Sí, al eliminar el área de trabajo en Power BI, se eliminará el contenido y los servicios asociados a grupos y grupos.

## <a name="power-bi-new"></a>Power BI (nuevo)

Power BI proporciona paneles e informes interactivos controlados por datos.

Si bien la creación de un nuevo área de trabajo en Power BI no crea un grupo de Microsoft 365, la creación de un grupo por cualquier otro medio crea un área de trabajo nueva (no clásica) en Power BI.

**Características clave proporcionadas a grupos**

- Informes de datos

**¿Power BI puede crear un grupo?**

No, no es posible crear un grupo de Microsoft 365 desde la nueva interfaz de Power BI.

**¿Existe el nuevo área de trabajo de Power BI sin un grupo?**

Sí, es posible crear informes y áreas de trabajo en Power BI que no estén asociados con grupos de Microsoft 365.

**¿Puede haber varias áreas de trabajo por grupo?**

Sí, se pueden compartir varias áreas de trabajo [creadas por Power BI con un solo grupo.](/power-bi/collaborate-share/service-create-the-new-workspaces#give-access-to-your-workspace)

**¿Se puede asociar un área de trabajo a varios grupos?**

No, un área de trabajo creada por Power BI solo se puede asociar a un único grupo.

**¿Puede cambiar la asociación de un área de trabajo con un grupo?**

Sí y no. Un área de trabajo creada por Power BI solo se puede asociar a un solo grupo a la vez, pero puede cambiar la asociación en cualquier momento. Un área de trabajo creada en Power BI por un grupo está asociada permanentemente a ese grupo.

**¿Elimina el área de trabajo el grupo?**

Sí, al eliminar el área de trabajo en Power BI, se eliminará el contenido y los servicios asociados al grupo.

## <a name="project-for-the-web"></a>Project para la Web

Project for the web ofrece la posibilidad de crear planes de proyecto, gráficos de Gantt y mapas de ruta.
Características clave que se proporcionan a los grupos.

- Planes de proyecto

**¿Project para la web puede crear un grupo?**

Sí, es posible crear un nuevo grupo de Microsoft 365 directamente desde Project para la web.

**¿Existen proyectos sin un grupo?**

Sí, los proyectos pueden existir sin estar asociados a un grupo de Microsoft 365, pero la asignación de tareas requiere una asociación de grupo.

**¿Puede haber varios proyectos por grupo?**

Sí, es posible conectar varios proyectos en un solo grupo.

**¿El proyecto se puede asociar a varios grupos?**

No, un proyecto solo se puede asociar a un único grupo.

**¿Puede cambiar la asociación de un proyecto con un grupo?**

No, una vez establecida la asociación con un grupo, no puede cambiar.

**¿Elimina el proyecto el grupo?**

No, la eliminación del proyecto en Project para la web no eliminará el grupo.

## <a name="roadmap"></a>Guía básica

Roadmap proporciona la capacidad de crear hojas de ruta del proyecto con Project para la web y Project Online.

**Características clave proporcionadas a grupos**

- Hojas de ruta del proyecto

**¿Puede roadmap crear un grupo?**

Sí, es posible crear un nuevo grupo de Microsoft 365 directamente desde el mapa de ruta.

**¿Existe roadmap sin un grupo?**

Sí, las hojas de ruta pueden existir sin estar asociadas con un grupo de Microsoft 365, pero para compartir la hoja de ruta es necesario asociarse a un grupo.

**¿Puede haber varias hojas de ruta por grupo?**

Sí, es posible conectar varias hojas de ruta a un solo grupo.

**¿Se puede asociar un mapa de ruta con varios grupos?**

No, un mapa de ruta solo se puede asociar a un único grupo.

**¿Puede cambiar la asociación de un plan con un grupo?**

No, una vez establecida la asociación con un grupo, no puede cambiar.

**¿Elimina el plan de ruta el grupo?**

No, la eliminación del mapa de ruta no eliminará el grupo.

## <a name="sharepoint"></a>SharePoint

SharePoint es una plataforma de administración de contenido basada en web que proporciona, entre otras cosas, servicios de almacenamiento para varios servicios de Microsoft 365.

**Características clave proporcionadas a grupos**

- Biblioteca de documentos
- Biblioteca para el almacenamiento del bloc de notas de OneNote
- Almacenamiento de archivos wiki de Teams

**¿Puede SharePoint crear un grupo?**

Sí, la creación de un sitio de grupo en SharePoint creará un grupo de Microsoft 365 de forma predeterminada. También es posible crear un grupo y, opcionalmente, un equipo para un sitio existente.

**¿Existen sitios de SharePoint sin un grupo?**

Sí, SharePoint ofrece una serie de sitios y servicios no asociados a grupos, como sitios de comunicaciones y concentradores. 

**¿Puede haber varios sitios por grupo?**

No, solo puede haber un solo sitio por grupo. Los canales privados de Teams usan sitios adicionales que no están conectados al grupo.

**¿Los sitios se pueden asociar a varios grupos?**

Técnicamente no, pero mientras se crea un sitio con un grupo, el contenido se puede compartir con otros grupos.

**¿Puede cambiar la asociación de un sitio con un grupo?**

No, el propio sitio está asociado con el grupo, pero el contenido se puede mover de un sitio a otro dentro de la interfaz de SharePoint, exportando contenido localmente o usando una herramienta de terceros.

**¿Elimina el sitio el grupo?**

Sí, al eliminar el sitio en SharePoint se eliminará el contenido y los servicios asociados a grupos y grupos.

## <a name="stream"></a>Stream

Microsoft Stream es una plataforma de hospedaje y uso compartido de vídeo.

**Características clave proporcionadas a grupos**

- Almacenamiento de vídeo
- Grabación de reuniones de Teams
- Canales de vídeo

**¿Stream puede crear un grupo?**

Sí, es posible crear un nuevo grupo de Microsoft 365 directamente desde Stream.

**¿Existe Stream sin un grupo?**

Sí, los canales de vídeo y los vídeos pueden existir en Stream sin estar asociados a un grupo.

**¿Puede haber varios vídeos y canales por grupo?**

Sí, puede haber varios vídeos y canales en cada grupo.

**¿Se puede asociar un vídeo o canal a varios grupos?**

Sí, mientras se crea un vídeo o canal con un grupo, se puede compartir con otros grupos.

**¿Puede cambiar su asociación con un grupo?**

Sí y no; Los vídeos de Stream son propiedad del cargador original o la grabadora de reuniones, por lo que se pueden asociar a cualquier grupo, pero los canales de vídeo solo pueden asociarse con el grupo en el que se crearon originalmente.

**¿Elimina vídeos o canales el grupo?**

No, la eliminación de vídeos o canales no elimina el grupo. Sin embargo, al eliminar el propio grupo en Stream, se eliminarán los servicios y el contenido asociados al grupo, excepto para los vídeos reales.

## <a name="yammer"></a>Yammer

Yammer es una plataforma social empresarial diseñada para fomentar la participación de la comunidad dentro y entre organizaciones.

La creación de una comunidad (anteriormente conocida como "grupo") en Yammer crea un buzón, pero en este momento no se usa.

Un grupo de Microsoft 365 asociado a Yammer no se puede usar con un equipo de Microsoft Teams.

**Características clave proporcionadas a grupos**

- Área de conversación

**¿Yammer puede crear un grupo de Microsoft 365?**

Sí, la creación de un nuevo grupo en Yammer creará un nuevo grupo de Microsoft 365, si las plataformas están conectadas y el usuario tiene la capacidad de crear un grupo.

Un grupo de Yammer con el grupo asociado de Microsoft 365 no se puede crear en ninguna interfaz o servicio que no sea el propio Yammer.

**¿Existe un grupo de Yammer sin un grupo de Microsoft 365?**

Sí, es posible crear un grupo de Yammer sin un grupo de Microsoft 365.

Si la plataforma Yammer no está conectada a grupos de Microsoft 365 o los usuarios no tienen la capacidad de crear un grupo de Microsoft 365, los grupos de Yammer se crean sin una asociación de grupo de Microsoft 365.

**¿Puede haber varios grupos de Yammer por grupo de Microsoft 365?**

No, la relación entre un grupo de Yammer y un grupo de Microsoft 365 es 1:1.

**¿Se puede asociar un grupo de Yammer a varios grupos de Microsoft 365?**

No, el grupo yammer solo se puede asociar a un único grupo de Microsoft 365. Es posible que las publicaciones se compartan o se traslade a otros grupos de Yammer.

**¿Puede cambiar la asociación de un grupo de Yammer con un grupo de Microsoft 365?**

No, el grupo Yammer solo se puede asociar al grupo de Microsoft 365 al que estaba asociado originalmente.

**¿Elimina el grupo Yammer el grupo de Microsoft 365?**

Sí, al eliminar el grupo en Yammer, se eliminará el contenido y los servicios asociados a grupos relacionados de Microsoft.

## <a name="related-topics"></a>Temas relacionados

[Planeación paso a paso de gobierno de colaboración](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Crear el plan de gobierno de colaboración](collaboration-governance-first.md)