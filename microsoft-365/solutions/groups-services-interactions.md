---
title: Agrupa las interacciones de servicios
ms.reviewer: ''
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
description: Agrupa las interacciones de servicios
ms.openlocfilehash: ab1bda8b3065518736468a6603e9356e9a2d0d25
ms.sourcegitcommit: d3ef9391f621e8f4ca70661184b3bb82c6cbda94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2022
ms.locfileid: "67585760"
---
# <a name="groups-services-interactions"></a>Agrupa las interacciones de servicios

Grupos de Microsoft 365 proporciona un tejido común para varios servicios y cargas de trabajo dentro de la plataforma de Microsoft 365 para ofrecer una experiencia conectada a los usuarios finales. En esencia, existe un grupo de Microsoft 365 para proporcionar:

- Una manera de administrar la pertenencia (Azure AD)
- Un lugar para la mensajería y las conversaciones (buzón de Exchange, Microsoft Teams, Yammer)
- Un lugar para almacenar archivos (SharePoint)
- Un calendario para la programación (Exchange)
- Un cuaderno para capturar notas (OneNote)

En el momento de la creación del grupo, también se aprovisionan otros recursos, pero no son visibles hasta que se accede por primera vez desde el servicio:

- Un panel para administrar tareas de grupo (Planner)
- Un área de trabajo para informes (Power BI)
- Un área para vídeos compartidos (Microsoft Stream)
- Un área para formularios compartidos (Formularios)

En Microsoft 365, otros servicios pueden interactuar con grupos de Microsoft 365 para ofrecer funcionalidades y funcionalidades adicionales a los miembros del grupo.
Algunos ejemplos de esto son:

- Power Apps para aplicaciones
- Power Automate para flujos de trabajo
- Proyecto en la web y hoja de ruta para la administración de proyectos basada en cascada
- Teams para conversaciones basadas en canales
- Yammer para comunidades de interés

## <a name="user-interactions-with-groups"></a>Interacciones del usuario con grupos

Grupos de Microsoft 365 pueden crearse y administrarse desde varias interfaces, tanto por administradores como por usuarios finales. 

### <a name="administrative-experiences"></a>Experiencias administrativas

Los administradores pueden crear y administrar grupos de Microsoft 365 desde varios de los centros de administración de cargas de trabajo, interfaces de línea de comandos que admiten scripting, así como aplicaciones personalizadas que interactúan con el Graph API. La única excepción a esto son los grupos de Yammer, que deben crearse desde la interfaz web de Yammer.

**Configuración relacionada**

En las distintas interfaces administrativas que pueden administrar la configuración de grupo existen varias superposiciones que debe tener en cuenta.

**Centro de administración de Microsoft 365**

En el Centro de administración de Microsoft 365, el acceso de invitado a grupos está habilitado de forma predeterminada, al igual que la capacidad de permitir que los propietarios agreguen invitados. No hay más controles de nivel de organización disponibles para los grupos de este centro de administración.

**Centro de administración de Azure AD**

El Centro de administración de Azure AD ofrece controles sobre si los usuarios pueden crear grupos o asignar propietarios en Azure Portal, así como la configuración de directivas de expiración y nomenclatura.

El centro de administración también proporciona varias medidas de control de invitación de invitado que van más allá de la de la Centro de administración de Microsoft 365, como la capacidad de limitar si los no propietarios también pueden invitar a invitados

**SharePoint**

Los sitios de SharePoint se crean con grupos de seguridad Propietario, Miembro y Visitante, y los dos primeros coinciden con sus homólogos de grupo de Microsoft 365. Aunque la pertenencia a sitios de SharePoint Online suele administrarse mediante el grupo de Microsoft 365 asociado, no es una relación bidireccional. Los cambios en la pertenencia en el nivel de grupo de Microsoft 365 se reflejan en SharePoint; sin embargo, si se cambia la pertenencia al grupo de SharePoint, esto no se refleja en el grupo de Microsoft 365.

### <a name="user-experiences"></a>Experiencias de usuario

Los usuarios finales pueden crear grupos a partir de varios de los servicios de Microsoft 365 y, en otros, solo pueden compartir con un grupo.

Los siguientes servicios permiten la creación de grupos por parte de los usuarios finales:

- Outlook
- Planner
- Project para la Web
- SharePoint
- Stream
- Microsoft Teams
- Yammer

#### <a name="restriction-of-group-creation"></a>Restricción de la creación de grupos

Un enfoque común para controlar la expansión de los equipos es limitar qué usuarios pueden crearlos. Esto solo se puede hacer limitando la creación de grupos. Esto afecta a la capacidad de crear grupos a partir de otros servicios cuando sea necesario para el usuario final. Grupos de Microsoft 365 no admite la capacidad de restringir la creación de grupos desde algunas aplicaciones o servicios, al tiempo que lo permite desde otras.

La experiencia de restricción de creación de grupos varía entre aplicaciones y servicios:

|Aplicación o servicio|Experiencia|
|---|---|
|Outlook|**La opción Nuevo grupo** se quita del menú Nuevo en la página personas|
|Planner|**El nuevo plan** explica que la creación de grupos se ha desactivado y ofrece agregar el plan a un grupo existente.|
|Proyecto para la web y la hoja de ruta|**El menú Crear grupo** explica que la creación de grupos está restringida y sugiere usar un grupo existente.|
|SharePoint|Todavía puede crear un sitio de equipo que no esté conectado a un grupo.|
|Stream|**La opción Grupo** no aparece en el **menú Crear**.|
|Teams|El usuario no puede crear un equipo con un grupo nuevo, pero todavía puede crear un equipo que use un grupo existente.<br><br>**El botón Crear un equipo** se reemplaza por **Crear equipo a partir de un grupo**.|
|Yammer|**La opción Crear un grupo** se quita de la navegación principal Grupos/Comunidades.|

## <a name="services-interactions-with-groups"></a>Interacciones de servicios con grupos

Consulte el póster Grupos en Microsoft 365 para obtener información sobre los distintos tipos de grupos, cómo se crean y administran, y algunas recomendaciones de gobernanza.

[![Imagen del pulgar para la infografía de grupos.](../downloads/msft-m365-groups-architecture-thumb.png)](https://download.microsoft.com/download/6/3/0/6309218f-a169-4f2d-af4c-2fe49e30ba17/msft-m365-groups.pdf)

[PDF](https://download.microsoft.com/download/6/3/0/6309218f-a169-4f2d-af4c-2fe49e30ba17/msft-m365-groups.pdf) \| [Visio](https://download.microsoft.com/download/6/3/0/6309218f-a169-4f2d-af4c-2fe49e30ba17/msft-m365-groups.vsdx)

En la tabla siguiente se proporciona información general sobre las interacciones Grupos de Microsoft 365 con varios servicios:

|Producto|Características|¿Existe el servicio sin un grupo?|¿Puede el servicio crear un grupo?|¿Elimina la instancia del grupo?|
|---|---|---|---|---|
|Azure AD|Pertenencia, Controles de grupo, Invitados|Sí|Sí|Sí|
|Exchange|Calendario, buzón|Sí|Sí|Sí|
|Forms|Formulario|Yes|No|No|
|OneNote|Bloc de notas|Yes|No|No|
|Planner|Panel de tareas|No|Sí|Sí|
|Aplicación de Power Apps|Aplicación|Yes|No|No|
|Power Automate|Flujo de trabajo|Yes|No|No|
|Power BI (clásico)|Área de trabajo|No|Sí|Sí|
|Power BI (nuevo)|Área de trabajo|Yes|No|Sí|
|Project para la Web|Plan de proyecto|Sí|Sí|No|
|Guía básica|Guía básica|Sí|Sí|No|
|SharePoint|Site|Sí|Sí|Sí|
|Stream|Canal, vídeo|Sí|Sí|Sí|
|Teams|Equipo|No|Sí|Sí|
|Yammer|Group|Sí|Sí|Sí|

Aunque la tabla anterior proporciona información general de alto nivel de las interacciones de grupo con los servicios de Microsoft 365, hay varios matices e complejidades que debe comprender. En las secciones siguientes se examinan más detalladamente las cargas de trabajo específicas y sus interacciones con grupos.

## <a name="azure-ad"></a>Azure AD

Azure AD proporciona las funcionalidades subyacentes de administración de identidades en Microsoft 365.

**Características clave proporcionadas a los grupos**

- Pertenencia a grupos
- Directiva de nomenclatura
- Directiva de expiración
- Invitados
- Restricción de la creación de grupos

**¿Puede Azure AD crear un grupo?**

Sí, Grupos de Microsoft 365 se pueden crear desde Azure AD a través del portal web de administración, a través de PowerShell o Graph API.

**¿Existe Azure AD sin un grupo?**

Sí, Azure AD realiza un gran número de servicios que no tienen ninguna relación con Grupos de Microsoft 365. Cada grupo de Microsoft 365 se representa como un objeto en Azure AD.

**¿Puede haber varias instancias de Azure AD por grupo?**

No, solo hay una instancia de Azure AD.

**¿Azure AD se puede asociar a varios grupos?**

Sí, porque Azure AD es la plataforma subyacente que proporciona el servicio de pertenencia a grupos.

**¿Puede cambiar la asociación de Azure AD con un grupo?**

No, Azure AD es la plataforma subyacente donde existen grupos.

**¿La eliminación de la instancia elimina el grupo?**

Al eliminar el grupo en Azure AD, se eliminarán los servicios y el contenido correspondientes asociados al grupo.

## <a name="teams"></a>Teams

Teams es un área de trabajo centrada en el chat destinada a mejorar la colaboración proporcionando una interfaz singular para interactuar con varios servicios de Microsoft y de terceros.

De forma predeterminada, cuando se crea un equipo, el buzón de correo y el calendario asociados al grupo de Microsoft 365 están ocultos tanto en la lista global de direcciones de Exchange como en Outlook. Un administrador puede invalidarlo manualmente si el usuario desea usar Outlook y Teams en el mismo grupo de Microsoft 365.

**Características clave proporcionadas a los grupos**

- Conversaciones
- Pestañas de & canales
- Reuniones

**¿Puede Teams crear un grupo?**

Sí, la creación de un nuevo equipo creará un nuevo grupo de Microsoft 365. También es posible crear un equipo para un grupo existente que actualmente no tiene uno.

**¿Existen equipos sin un grupo?**

No, no es posible que un equipo exista sin un grupo.

**¿Puede haber varios equipos por grupo?**

No, la relación entre un equipo y un grupo es 1:1.

**¿Se puede asociar un equipo a varios grupos?**

No, el propio equipo solo se puede asociar a un único grupo.

**¿Puede cambiar la asociación de un equipo con un grupo?**

No, el equipo solo puede asociarse al grupo al que se asoció originalmente.

**¿Elimina el equipo el grupo?**

Sí, al eliminar el equipo de Microsoft Teams se eliminarán el grupo, los servicios asociados al grupo y el contenido.

## <a name="exchange"></a>Exchange

Exchange Online proporciona la funcionalidad de mensajería, calendario, contacto y asociada. En el contexto de un grupo, solo se asocia un solo recurso, en lugar de una instancia de servicio completa.

**Características clave proporcionadas a los grupos**

- Buzón de correo y calendario
- Capacidad de enviar un correo electrónico a todos los miembros del grupo
- Almacenamiento de conversaciones de canales de Teams con fines de exhibición de documentos electrónicos, comentarios de Planner

**¿Puede Exchange crear un grupo?**

Sí, es posible crear un grupo desde el centro de administración de Exchange Online, así como desde Outlook. También puede convertir listas de distribución de Exchange a grupos de Microsoft 365.

**¿Existe Exchange sin un grupo?**

Sí, Exchange Online proporciona varios servicios, incluidos buzones y calendarios compartidos, sin ninguna asociación de grupo.

**¿Puede haber varias instancias de buzones o calendarios de Exchange por grupo?**

No, solo puede haber un único buzón de Exchange Online y un calendario para un grupo.

**¿Se pueden asociar buzones y calendarios de Exchange a varios grupos?**

No, el buzón y el calendario tienen una relación 1:1 con el grupo. Es posible compartir el buzón con otros usuarios o grupos, pero esto no establece ningún tipo de asociación de servicio.

**¿Puede cambiar la asociación del buzón de Exchange o del calendario con un grupo?**

No, el buzón de correo y el calendario no se pueden cambiar a otro grupo. Sin embargo, el contenido se puede mover de un buzón a otro dentro de Outlook o mediante una herramienta de terceros.

**¿Elimina el buzón el grupo?**

Sí, al eliminar el buzón de Exchange se eliminará el grupo, así como los servicios y el contenido asociados al grupo.

## <a name="forms"></a>Forms

Forms proporciona encuestas y cuestionarios basados en web.

**Características clave proporcionadas a los grupos**

- Propiedad de formularios

**¿Pueden los formularios crear un grupo?**

No, Forms no puede crear un grupo.

**¿Existen formularios sin un grupo?**

Sí, las encuestas y cuestionarios se pueden crear directamente en la cuenta de un usuario final.

**¿Puede haber varios formularios por grupo?**

Sí, puede haber varias formas asociadas a un grupo.

**¿Se pueden asociar formularios a varios grupos?**

No, un formulario solo se puede asociar a un único grupo.

**¿Puede cambiar la asociación de un formulario con un grupo?**

No, una vez que un formulario está asociado a un grupo (creado directamente dentro de, o la propiedad transferida desde un individuo) no se puede mover a otro grupo.

**¿Elimina el formulario el grupo?**

No, no es posible eliminar un grupo de la interfaz Forms, solo formularios individuales.

## <a name="onenote"></a>OneNote

OneNote es una aplicación de cuaderno digital. El cuaderno de OneNote creado con un grupo es un archivo en el sitio de SharePoint asociado en lugar de un servicio conectado a un grupo.

**Características clave proporcionadas a los grupos**

- Cuaderno compartido (almacenado en la biblioteca de SharePoint asociada al grupo)

**¿Puede OneNote crear un grupo?**

No, la aplicación OneNote no puede crear un grupo.

**¿Existen cuadernos de OneNote sin un grupo?**

Sí, los cuadernos se pueden crear directamente en OneDrive o en otras ubicaciones compartidas.

**¿Puede haber varios cuadernos de OneNote por grupo?**

Sí, se crea un cuaderno de forma predeterminada y se pueden agregar otros, pero cualquier vínculo a OneNote desde los servicios asociados al grupo siempre irá al cuaderno predeterminado.

**¿Se puede asociar un cuaderno de OneNote a varios grupos?**

No, el cuaderno se almacena en la biblioteca de sitios de SharePoint asociada al grupo y está vinculado desde varias interfaces. Sin embargo, se puede compartir con otros grupos de la misma manera que se puede compartir con individuos.

**¿Puede cambiar la asociación del cuaderno con un grupo?**

No, el propio cuaderno está asociado al grupo y se puede acceder directamente desde otros servicios conectados a grupos, pero el contenido se puede mover de un cuaderno a otro dentro de la aplicación OneNote.

**¿Elimina el cuaderno el grupo?**

No, sin embargo, si se elimina el cuaderno de OneNote, puede haber vínculos rotos en algunos de los servicios asociados al grupo.

## <a name="planner"></a>Planner

Planner es un servicio ligero de administración de tareas de grupo.

**Características clave proporcionadas a los grupos**

- Panel para administrar tareas de grupo

**¿Puede Planner crear un grupo?**

Sí, la creación de un plan creará un nuevo grupo.

**¿Existe un panel de Planner sin un grupo?**

No, un plan debe estar asociado a un grupo.

**¿Puede haber varios planes por grupo?**

Sí, puede haber varios planes por grupo.

**¿Se puede asociar un plan a varios grupos?**

No, un plan se basa únicamente en la pertenencia al grupo para determinar el acceso.

**¿Puede cambiar la asociación de un plan con un grupo?**

No, sin embargo, al copiar un plan se crea un nuevo grupo.

> [!NOTE]
> Un grupo creado por cualquier otra aplicación no se mostrará automáticamente en Planner para un usuario. Para acceder al panel inicialmente, tendrán que abrirlo desde otra interfaz basada en grupos, como Outlook.

**¿Elimina el plan el grupo?**

Sí, al eliminar el plan se eliminarán los servicios y el contenido asociados al grupo y al grupo.

## <a name="power-apps"></a>Power Apps

Power Apps proporciona un lienzo para el desarrollo de aplicaciones sin código.

**Características clave proporcionadas a los grupos**

- Las aplicaciones se pueden compartir con un grupo que se va a ejecutar y modificar.

**¿Puede Power Apps crear un grupo?**

No, Power Apps no puede crear un grupo de Microsoft 365.

**¿Existen Power Apps sin un grupo?**

Sí, las aplicaciones se pueden crear en Power Apps y residir en la cuenta de creadores hasta que se compartan o publiquen.

**¿Puede haber varias aplicaciones por grupo?**

Sí, puede haber varias aplicaciones compartidas con un grupo.

**¿Las aplicaciones se pueden asociar a varios grupos?**

Sí, una aplicación se puede compartir con varios grupos.

**¿Puede cambiar la asociación de una aplicación con un grupo?**

Sí, ya que la asociación entre Power Apps y un grupo de Microsoft 365 solo está compartiendo: la aplicación sigue residiendo con el creador.

> [!IMPORTANT]
> [Los grupos deben estar habilitados para la seguridad antes de que las aplicaciones se puedan compartir con ellos](/powerapps/maker/canvas-apps/share-app#share-an-app-with-office-365-groups).

**¿Elimina la aplicación el grupo?**

No, las aplicaciones no están conectadas al grupo que no sean compartidas con ellas.

## <a name="power-automate"></a>Power Automate

Power Automate (anteriormente conocido como Microsoft Flow) proporciona flujos de trabajo y servicios de automatización.

**Características clave proporcionadas a los grupos**

- Los flujos de trabajo se pueden compartir con un grupo que se va a ejecutar y modificar.

**¿Puede Power Automate crear un grupo?**

No, Power Automate no puede crear un grupo de Microsoft 365 en el contexto de estar asociado a uno.

Sin embargo, es posible crear un flujo que realice varias operaciones, como crear un grupo de seguridad de Azure AD o actualizar la pertenencia a un grupo de Microsoft 365.

**¿Existen flujos sin un grupo?**

Sí, los flujos se pueden crear en Power Automate y residir en la cuenta de creadores hasta que se compartan o publiquen.

**¿Puede haber varios flujos por grupo?**

Sí, puede haber varios flujos compartidos con un grupo.

**¿Se puede asociar un flujo a varios grupos?**

Sí, un flujo se puede compartir con varios grupos.

**¿Puede cambiar la asociación de un flujo con un grupo?**

Sí, ya que la asociación entre Power Automate y un grupo de Microsoft 365 solo está compartiendo: el flujo sigue residiendo con el creador.

**¿Eliminar un flujo elimina el grupo?**

No, al igual que Power Apps, los flujos no están conectados al grupo que no sean compartidos con ellos.

## <a name="power-bi-classic"></a>Power BI (clásico)

Power BI proporciona informes y paneles interactivos controlados por datos.

**Características clave proporcionadas a los grupos**

- Informes de datos

**¿Puede Power BI crear un grupo?**

Sí, la creación de un área de trabajo clásica creará un grupo de Microsoft 365.

**¿Existe un área de trabajo clásica de Power BI sin un grupo?**

No, [un área de trabajo clásica de Power BI debe estar asociada a un grupo](/power-bi/collaborate-share/service-collaborate-power-bi-workspace).

**¿Puede haber varias áreas de trabajo de Power BI por grupo?**

No, la relación entre un área de trabajo clásica y un grupo es 1:1.

**¿Se puede asociar un área de trabajo a varios grupos?**

Técnicamente no, mientras que el área de trabajo clásica se crea con el grupo, el contenido se puede compartir fuera del grupo con usuarios y grupos de seguridad.

**¿Puede cambiar la asociación del área de trabajo con un grupo?**

No, el área de trabajo clásica está asociada al grupo, pero el contenido se puede mover de un área de trabajo a otra dentro de la interfaz de Power BI o mediante la exportación de contenido localmente.

**¿Elimina el área de trabajo el grupo?**

Sí, al eliminar el área de trabajo en Power BI se eliminarán los servicios y el contenido asociados a grupos y grupos.

## <a name="power-bi-new"></a>Power BI (nuevo)

Power BI proporciona informes y paneles interactivos controlados por datos.

Mientras que la creación de un área de trabajo en Power BI no crea un grupo de Microsoft 365, la creación de un grupo por cualquier otro medio crea un nuevo área de trabajo (no clásica) en Power BI.

**Características clave proporcionadas a los grupos**

- Informes de datos

**¿Puede Power BI crear un grupo?**

No, no es posible crear un grupo de Microsoft 365 desde la nueva interfaz de Power BI.

**¿Existe el nuevo área de trabajo de Power BI sin un grupo?**

Sí, es posible crear informes y áreas de trabajo en Power BI que no estén asociadas a grupos de Microsoft 365.

**¿Puede haber varias áreas de trabajo por grupo?**

Sí, [varias áreas de trabajo creadas por Power BI se pueden compartir con un solo grupo](/power-bi/collaborate-share/service-create-the-new-workspaces#give-access-to-your-workspace).

**¿Se puede asociar un área de trabajo a varios grupos?**

No, un área de trabajo creada por Power BI solo se puede asociar a un único grupo.

**¿Puede cambiar la asociación de un área de trabajo con un grupo?**

Sí y no. Un área de trabajo creada por Power BI solo se puede asociar a un único grupo a la vez, pero puede cambiar la asociación en cualquier momento. Un área de trabajo creada en Power BI por un grupo se asocia permanentemente a ese grupo.

**¿Elimina el área de trabajo el grupo?**

Sí, al eliminar el área de trabajo en Power BI se eliminarán los servicios y el contenido asociados al grupo y al grupo.

## <a name="project-for-the-web"></a>Project para la Web

Project for the Web ofrece la capacidad de crear planes de proyecto, gráficos de Gantt y hojas de ruta.
Características clave proporcionadas a los grupos.

- Planes de proyecto

**¿Puede Project para la web crear un grupo?**

Sí, es posible crear un nuevo grupo de Microsoft 365 directamente desde Project para la web.

**¿Existen proyectos sin un grupo?**

Sí, los proyectos pueden existir sin estar asociados a un grupo de Microsoft 365, pero la asignación de tareas requiere asociación de grupos.

**¿Puede haber varios proyectos por grupo?**

Sí, es posible conectar varios proyectos en un solo grupo.

**¿Se puede asociar el proyecto a varios grupos?**

No, un proyecto solo se puede asociar a un único grupo.

**¿Puede cambiar la asociación de un proyecto con un grupo?**

No, una vez establecida la asociación con un grupo, no puede cambiar.

**¿Elimina el grupo el proyecto?**

No, la eliminación del proyecto en Project para la web no eliminará el grupo.

## <a name="roadmap"></a>Guía básica

Roadmap proporciona la capacidad de crear hojas de ruta del proyecto con Project para la web y Project Online.

**Características clave proporcionadas a los grupos**

- Hojas de ruta del proyecto

**¿Puede Roadmap crear un grupo?**

Sí, es posible crear un nuevo grupo de Microsoft 365 directamente desde la hoja de ruta.

**¿Existe Roadmap sin un grupo?**

Sí, los planes de desarrollo pueden existir sin estar asociados a un grupo de Microsoft 365, pero para compartir la hoja de ruta se requiere asociación de grupos.

**¿Puede haber varias hojas de ruta por grupo?**

Sí, es posible conectar varias hojas de ruta a un solo grupo.

**¿Se puede asociar una hoja de ruta a varios grupos?**

No, una hoja de ruta solo se puede asociar a un único grupo.

**¿Puede cambiar la asociación de una hoja de ruta con un grupo?**

No, una vez establecida la asociación con un grupo, no puede cambiar.

**¿Elimina el grupo la hoja de ruta?**

No, la eliminación de la hoja de ruta no eliminará el grupo.

## <a name="sharepoint"></a>SharePoint

SharePoint es una plataforma de administración de contenido basada en web que proporciona, entre otras cosas, servicios de almacenamiento para varios servicios de Microsoft 365.

**Características clave proporcionadas a los grupos**

- Biblioteca de documentos
- Biblioteca para el almacenamiento del cuaderno de OneNote
- Almacenamiento de archivos wiki de Teams

**¿Puede SharePoint crear un grupo?**

Sí, la creación de un sitio de equipo en SharePoint creará un grupo de Microsoft 365 de forma predeterminada. También es posible crear un grupo y, opcionalmente, un equipo para un sitio existente.

**¿Existen sitios de SharePoint sin un grupo?**

Sí, SharePoint ofrece varios servicios y sitios no asociados a grupos, como sitios de comunicación y concentradores. 

**¿Puede haber varios sitios por grupo?**

No, solo puede haber un único sitio por grupo. Los canales privados y compartidos de Teams usan sitios adicionales que no están conectados al grupo.

**¿Los sitios se pueden asociar a varios grupos?**

Técnicamente no, pero mientras se crea un sitio con un grupo, el contenido se puede compartir con otros grupos.

**¿Puede cambiar la asociación de un sitio con un grupo?**

No, el propio sitio está asociado al grupo, pero el contenido se puede mover de un sitio a otro dentro de la interfaz de SharePoint, exportando contenido localmente o usando una herramienta de terceros.

**¿Elimina el sitio el grupo?**

Sí, al eliminar el sitio en SharePoint se eliminarán los servicios y el contenido asociados a grupos y grupos.

## <a name="stream"></a>Stream

Microsoft Stream es una plataforma de hospedaje y uso compartido de vídeo.

**Características clave proporcionadas a los grupos**

- Almacenamiento de vídeo
- Grabación de reuniones de Teams
- Canales de vídeo

**¿Puede Stream crear un grupo?**

Sí, es posible crear un nuevo grupo de Microsoft 365 directamente desde Stream.

**¿Existe Stream sin un grupo?**

Sí, los canales de vídeo y los vídeos pueden existir en Stream sin estar asociados a un grupo.

**¿Puede haber varios vídeos y canales por grupo?**

Sí, puede haber varios vídeos y canales en cada grupo.

**¿Se puede asociar un vídeo o un canal a varios grupos?**

Sí, mientras se crea un vídeo o canal con un grupo, se puede compartir con otros grupos.

**¿Puede cambiar su asociación con un grupo?**

Sí y no; Los vídeos de Stream son propiedad del cargador original o de la grabadora de reuniones, por lo que se pueden asociar a cualquier grupo, pero los canales de vídeo solo se pueden asociar al grupo en el que se crearon originalmente.

**¿La eliminación de vídeos o canales elimina el grupo?**

No, la eliminación de vídeos o canales no elimina el grupo. Sin embargo, al eliminar el propio grupo en Stream se eliminarán los servicios y el contenido asociados al grupo, excepto los vídeos reales.

## <a name="yammer"></a>Yammer

Yammer es una plataforma social empresarial diseñada para fomentar la participación de la comunidad dentro y entre organizaciones.

La creación de una comunidad (anteriormente conocida como "grupo") en Yammer crea un buzón de correo, pero en la actualidad esto no se usa.

No se puede usar un grupo de Microsoft 365 asociado a Yammer con un equipo de Microsoft Teams.

No se puede usar un grupo de Yammer con un área de trabajo de PowerBI Pro.

**Características clave proporcionadas a los grupos**

- Área de conversación

**¿Puede Yammer crear un grupo de Microsoft 365?**

Sí, la creación de un nuevo grupo en Yammer creará un nuevo grupo de Microsoft 365, si las plataformas están conectadas y el usuario tiene la capacidad de crear un grupo.

No se puede crear un grupo de Yammer con un grupo de Microsoft 365 asociado en ninguna interfaz o servicio que no sea el propio Yammer.

**¿Existe un grupo de Yammer sin un grupo de Microsoft 365?**

Sí, es posible crear un grupo de Yammer sin un grupo de Microsoft 365.

Si la plataforma de Yammer no está conectada a grupos de Microsoft 365 o los usuarios no tienen la capacidad de crear un grupo de Microsoft 365, los grupos de Yammer se crean sin una asociación de grupos de Microsoft 365.

**¿Puede haber varios grupos de Yammer por grupo de Microsoft 365?**

No, la relación entre un grupo de Yammer y un grupo de Microsoft 365 es 1:1.

**¿Se puede asociar un grupo de Yammer a varios grupos de Microsoft 365?**

No, el grupo de Yammer solo se puede asociar a un único grupo de Microsoft 365. Es posible que las publicaciones se compartan con otros grupos de Yammer o se muevan a ellos.

**¿Puede cambiar la asociación de un grupo de Yammer con un grupo de Microsoft 365?**

No, el grupo de Yammer solo puede asociarse al grupo de Microsoft 365 al que se asoció originalmente.

**¿Elimina el grupo de Yammer el grupo de Microsoft 365?**

Sí, al eliminar el grupo en Yammer se eliminarán los servicios y el contenido relacionados con el grupo de Microsoft y el grupo asociado.

## <a name="related-topics"></a>Temas relacionados

[Recomendaciones de planeamiento de gobernanza de colaboración](collaboration-governance-overview.md#collaboration-governance-planning-recommendations)

[Creación del plan de gobernanza de colaboración](collaboration-governance-first.md)
