---
title: Interacciones de los servicios de grupos
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
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: Interacciones de los servicios de grupos
ms.openlocfilehash: 9632debf1bc6fdd2fce061a4c535906410700175
ms.sourcegitcommit: 66f1f430b3dcae5f46cb362a32d6fb7da4cff5c1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2020
ms.locfileid: "46662839"
---
# <a name="groups-services-interactions"></a>Interacciones de los servicios de grupos

Microsoft 365 grupos proporciona una estructura común para varios servicios y cargas de trabajo dentro de la plataforma de Microsoft 365 para ofrecer una experiencia de conexión para los usuarios finales. En esencia, existe un grupo de Microsoft 365 para proporcionar:

- Una forma de administrar la pertenencia (Azure AD)
- Un espacio para la mensajería y las conversaciones que se deben realizar (buzón de correo de Exchange, Microsoft Teams, Yammer)
- Un espacio para que se almacenen los archivos (SharePoint)
- Un calendario para la programación (Exchange)
- Un bloc de notas para capturar notas (OneNote)

En el punto de creación del grupo, también se aprovisionan otros recursos, aunque no son visibles hasta que se accede a ellos por primera vez desde el servicio:

- Un panel para administrar tareas de grupo (Planner)
- Un área de trabajo para informes (Power BI)
- Un área para vídeos compartidos (Microsoft Stream)
- Un área para formularios compartidos (formularios)

En Microsoft 365, otros servicios pueden interactuar con los grupos de Microsoft 365 para ofrecer funcionalidad y capacidades adicionales a los miembros del grupo.
Algunos ejemplos son:

- Power apps for apps
- Automatizar la alimentación para flujos de trabajo
- Proyecto en la web y mapa de ruta para la administración de proyectos en cascada
- Teams para conversaciones basadas en canal
- Yammer para comunidades de interés

## <a name="user-interactions-with-groups"></a>Interacciones del usuario con grupos

Los grupos de 365 de Microsoft se pueden crear y administrar desde una amplia variedad de interfaces, tanto por los administradores como por los usuarios finales. 

### <a name="administrative-experiences"></a>Experiencias administrativas

Los administradores pueden crear y administrar grupos de Microsoft 365 desde varios centros de administración de cargas de trabajo, interfaces de línea de comandos que admitan scripting, así como aplicaciones personalizadas que interactúen con la API de Graph. La única excepción a esto son los grupos de Yammer, que se deben crear desde dentro de la interfaz Web de Yammer.

**Configuración relacionada**

En las distintas interfaces administrativas que pueden administrar la configuración de un grupo existen varios solapamiento que debe tener en cuenta.

**Centro de administración de Microsoft 365**

En el centro de administración de 365 de Microsoft, el acceso de invitado a grupos está habilitado de forma predeterminada, al igual que la capacidad de permitir que los propietarios agreguen invitados. No hay otros controles de nivel de organización disponibles para los grupos desde este centro de administración.

**Centro de administración de Azure AD**

El centro de administración de Azure AD ofrece controles sobre si los usuarios pueden crear grupos o asignar propietarios en los portales de Azure, así como la configuración de caducidad y de la Directiva de nomenclatura.

El centro de administración también proporciona varias medidas de control de invitación de invitado que van más allá de la del centro de administración de Microsoft 365, como la capacidad de limitar si los no propietarios también pueden invitar a invitados

**SharePoint**

Los sitios de SharePoint se crean con grupos de seguridad de propietario, miembro y visitante, con las dos primeras que coinciden con sus homólogos de grupo de Microsoft 365. Aunque la pertenencia a sitios de SharePoint Online suele estar administrada por el grupo de Microsoft 365 asociado, no es una relación bidireccional. Los cambios en la pertenencia en el nivel de grupo de Microsoft 365 se reflejan en SharePoint, sin embargo, si se modifica la pertenencia en el grupo de SharePoint, esto no se refleja en el grupo 365 de Microsoft.

### <a name="user-experiences"></a>Experiencias de usuario

Los usuarios finales pueden crear grupos a partir de varios de los servicios de Microsoft 365 y en otros que solo pueden compartir con un grupo.

Los siguientes servicios permiten la creación de grupos por parte de los usuarios finales:
                         
Proyecto de Outlook Planner para la secuencia de SharePoint Web Microsoft Teams Yammer

**Restricción de la creación de grupos**

Un enfoque común para controlar la proliferación de equipos es limitar los usuarios que pueden crearlos. Esto solo puede hacerse limitando la creación de grupos. Esto afecta a la capacidad de crear grupos desde otros servicios en los que puede ser necesario para el usuario final. Los grupos de 365 de Microsoft no admiten la capacidad de restringir la creación de grupos a partir de algunas aplicaciones o servicios a la vez que se permite en otros.

La experiencia de la restricción de creación de grupos varía entre aplicaciones y servicios:


|Aplicación o servicio|Experiencia|
|:-------------|:---------|
|Outlook|La opción **nuevo grupo** se ha quitado del menú nuevo en la página personas|
|Planner|**Nuevo plan** explica que la creación de grupos se ha desactivado y ofrece agregar el plan a un grupo existente.|
|Proyecto para la web y la guía básica|El menú **Crear grupo** explica que la creación de grupos está restringida y sugiere el uso de un grupo existente.|
|SharePoint|Todavía puede crear un sitio de grupo que no esté conectado a un grupo.|
|Stream|La opción **Grupo** no aparece en el **menú crear**.|
|Teams|El usuario no puede crear un equipo con un grupo nuevo, pero todavía puede crear un equipo que use un grupo existente.<br><br>**El botón crear un equipo** se ha reemplazado por **crear equipo desde un grupo**.|
|Yammer|**Crear una** opción de grupo se ha quitado de la navegación de grupos principales/comunidades.|

## <a name="services-interactions-with-groups"></a>Interacciones de servicios con grupos

Vea los grupos en el póster de Microsoft 365 para obtener información sobre los distintos tipos de grupos, cómo se crean y administran, y algunas recomendaciones de gobierno.

[![Imagen en miniatura para la infografía de grupos](../downloads/msft-m365-groups-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf)

[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-groups.vsdx)

En la siguiente tabla se proporciona una introducción a las interacciones de Microsoft 365 Groups con varios servicios:

|Producto|Características|¿El servicio<br>¿existe sin un grupo?|Puede el servicio<br>¿crear un grupo?|Elimina el<br>instancia ¿eliminar el grupo?|
|:---|:---|:---|:---|:---|
|Azure AD|Pertenencia, controles de grupo, invitados|Sí|Sí|Sí|
|Exchange|Calendario, buzón de correo|Sí|Sí|Sí|
|Formularios|Formulario|Sí|No|No|
|OneNote|Bloc de notas|Sí|No|No|
|Planner|Panel de tareas|No|Sí|Sí|
|Aplicación de Power apps|Aplicación|Sí|No|No|
|Power Automate|Flujo de trabajo|Sí|No|No|
|Power BI (clásico)|Workspace|No|Sí|Sí|
|Power BI (nueva)|Workspace|Sí|No|Sí|
|Project para la web|Plan del proyecto|Sí|Sí|No|
|Hoja de ruta|Hoja de ruta|Sí|Sí|No|
|SharePoint|Sitio|Sí|Sí|Sí|
|Stream|Canal, vídeo|Sí|Sí|Sí|
|Teams|Equipo|No|Sí|Sí|
|Yammer|Group|Sí|Sí|Sí|

Aunque en la tabla anterior se proporciona una descripción general de alto nivel de las interacciones de grupo con los servicios de Microsoft 365, hay una serie de matices y complejidades que debe comprender. En las siguientes secciones se ofrece una visión más detallada de las cargas de trabajo específicas y sus interacciones con los grupos.

## <a name="azure-ad"></a>Azure AD

Azure AD proporciona las capacidades de administración de identidades subyacentes en Microsoft 365.

**Características clave que se proporcionan a los grupos**

- Pertenencia a grupos
- Directiva de nomenclatura
- Directiva de expiración
- Visitantes
- Restricción de la creación de grupos

**¿Puede Azure AD crear un grupo?**

Sí, los grupos de 365 de Microsoft se pueden crear desde Azure AD a través del portal web de administración, a través de PowerShell o la API de Graph.

**¿Hay Azure AD sin un grupo?**

Sí, Azure AD realiza un gran número de servicios que no tienen relación con los grupos de 365 de Microsoft. Cada grupo de Microsoft 365 se representa como un objeto en Azure AD.

**¿Puede haber varias instancias de Azure AD por grupo?**

No, solo hay una instancia de Azure AD.

**¿Puede asociarse Azure AD con varios grupos?**

Sí, porque Azure AD es la plataforma subyacente que proporciona el servicio de pertenencia a grupos.

**¿Puede la Asociación de Azure AD con un cambio de grupo?**

No, Azure AD es la plataforma subyacente en la que se encuentran los grupos.

**¿Se elimina la instancia, elimine el grupo?**

Al eliminar el grupo en Azure AD, se eliminará el contenido y los servicios relacionados con el grupo.

## <a name="teams"></a>Teams

Teams es un área de trabajo centrada en chat que tiene como objetivo mejorar la colaboración al ofrecer una interfaz singular para interactuar con una variedad de servicios de Microsoft y de terceros.

De forma predeterminada, cuando se crea un equipo, el buzón y el calendario asociados con el grupo de Microsoft 365 están ocultos en la lista global de direcciones de Exchange, así como en Outlook. Esto puede ser reemplazado manualmente por un administrador si el usuario desea usar Outlook y Teams en el mismo grupo de Microsoft 365.

**Características clave que se proporcionan a los grupos**

- Conversaciones
- Fichas de & de canales
- Meetings

**¿Puede Teams crear un grupo?**

Sí, la creación de un nuevo equipo creará un nuevo grupo de 365 de Microsoft. También es posible crear un equipo para un grupo existente que no tiene actualmente uno.

**¿Existen equipos sin un grupo?**

No, no es posible que exista un equipo sin un grupo.

**¿Puede haber varios equipos por grupo?**

No, la relación entre un equipo y un grupo es de 1:1.

**¿Se puede asociar un equipo a varios grupos?**

No, el equipo en sí solo puede estar asociado a un único grupo.

**¿Puede una asociación de un equipo con un cambio de grupo?**

No, el equipo solo puede asociarse con el grupo al que estaba asociado originalmente.

**¿Se elimina el equipo, ¿eliminar el grupo?**

Sí, al eliminar el equipo en Microsoft Teams, se eliminarán el grupo, los servicios asociados a grupos y el contenido.

## <a name="exchange"></a>Exchange

Exchange Online proporciona mensajería, calendario, contactos y funcionalidad asociada. En el contexto de un grupo, solo hay asociado un único recurso, en lugar de una instancia de servicio completa.

**Características clave que se proporcionan a los grupos**

- Buzón y calendario
- Capacidad para enviar por correo electrónico todos los miembros del grupo
- Almacenamiento de conversaciones de canal de Microsoft Teams para fines de eDiscovery, comentarios de Planner

**¿Puede Exchange crear un grupo?**

Sí, es posible crear un grupo desde el centro de administración de Exchange Online, así como desde Outlook. También puede convertir las listas de distribución de Exchange a grupos de Microsoft 365.

**¿Existe Exchange sin un grupo?**

Sí, Exchange Online proporciona una serie de servicios, como buzones y calendarios compartidos, sin ninguna asociación de grupo.

**¿Puede haber varias instancias de buzones o calendarios de Exchange por grupo?**

No, solo puede haber un único buzón de correo de Exchange Online y un calendario para un grupo.

**¿Los buzones de correo y los calendarios de Exchange se pueden asociar a varios grupos?**

No, el buzón y el calendario tienen una relación de 1:1 con el grupo. Es posible compartir el buzón con otros usuarios o grupos, pero esto no establece ninguna asociación de servicio.

**¿Puede cambiar el buzón o la Asociación del calendario de Exchange con un grupo?**

No, el buzón y el calendario no se pueden cambiar a un grupo diferente. Sin embargo, el contenido se puede mover de un buzón de correo a otro dentro de Outlook o mediante una herramienta de terceros.

**¿Se elimina el buzón ¿eliminar el grupo?**

Sí, al eliminar el buzón de Exchange se eliminará el grupo, así como el contenido y los servicios asociados a un grupo.

## <a name="forms"></a>Formularios

Forms proporciona encuestas y cuestionarios basados en Web.

**Características clave que se proporcionan a los grupos**

- Propiedad de los formularios

**¿Los formularios pueden crear un grupo?**

No, los formularios no pueden crear un grupo.

**¿Existen formularios sin un grupo?**

Sí, se pueden crear encuestas y cuestionarios directamente en una cuenta de usuario final.

**¿Puede haber varios formularios por grupo?**

Sí, puede haber varios formularios asociados a un grupo.

**¿Se pueden asociar formularios a varios grupos?**

No, un formulario solo se puede asociar con un único grupo.

**¿Puede la Asociación de un formulario con un grupo cambiar?**

No, una vez que un formulario está asociado a un grupo (ya sea creado directamente dentro del o se ha transferido de una persona) no se puede mover a otro grupo.

**¿Se elimina el formulario ¿eliminar el grupo?**

No, no es posible eliminar un grupo de la interfaz de formularios, sino sólo formularios individuales.

## <a name="onenote"></a>OneNote

OneNote es una aplicación digital para blocs de notas. El Bloc de notas de OneNote creado con un grupo es un archivo en el sitio de SharePoint asociado, en lugar de un servicio conectado a un grupo.

**Características clave que se proporcionan a los grupos**

- Bloc de notas compartido (almacenado en la biblioteca de SharePoint asociada al grupo)

**¿Puede OneNote crear un grupo?**

No, la aplicación de OneNote no puede crear un grupo.

**¿Los blocs de notas de OneNote existen sin un grupo?**

Sí, los blocs de notas se pueden crear directamente en OneDrive o en otras ubicaciones compartidas.

**¿Puede haber varios blocs de notas de OneNote por grupo?**

Sí, se crea un bloc de notas de forma predeterminada y se pueden agregar otros, pero cualquier vínculo a OneNote desde servicios asociados del grupo siempre va al bloc de notas predeterminado.

**¿Puede asociarse un bloc de notas de OneNote con varios grupos?**

No, el Bloc de notas se almacena en la biblioteca de sitio de SharePoint asociada al grupo y se vincula desde varias interfaces. Sin embargo, puede compartirse con otros grupos de la misma manera que se puede compartir con los usuarios.

**¿Puede cambiar la Asociación del Bloc de notas a un grupo?**

No, el Bloc de notas está asociado con el grupo y se puede tener acceso directamente a él desde otros servicios conectados a un grupo, pero el contenido se puede mover de un bloc de notas a otro dentro de la aplicación de OneNote.

**¿Se elimina el Bloc de notas, ¿eliminar el grupo?**

No obstante, si se elimina el Bloc de notas de OneNote, es posible que haya vínculos rotos en algunos de los servicios relacionados con el grupo.

## <a name="planner"></a>Planner

Planner es un servicio de administración de tareas de grupo ligero.

**Características clave que se proporcionan a los grupos**

- Panel para administrar tareas de grupo

**¿Puede el organizador crear un grupo?**

Sí, la creación de un plan creará un grupo nuevo.

**¿Hay un panel de Planner sin un grupo?**

No, un plan debe estar asociado a un grupo.

**¿Puede haber varios planes por grupo?**

Sí, puede haber varios planes por grupo.

**¿Se puede asociar un plan a varios grupos?**

No, un plan depende exclusivamente de la pertenencia al grupo para determinar el acceso.

**¿Puede una asociación de plan con un cambio de grupo?**

No, sin embargo, al copiar un plan se crea un grupo nuevo.

> [!NOTE]
> Un grupo creado por cualquier otra aplicación no se mostrará en Planner automáticamente para un usuario. Para tener acceso a la placa inicialmente, deberá abrirla desde otra interfaz basada en grupos, como Outlook.

**¿La eliminación del plan elimina el grupo?**

Sí, al eliminar el plan se eliminarán el contenido y los servicios asociados con el grupo y el grupo.

## <a name="power-apps"></a>PowerApps

Power apps proporciona un lienzo para el desarrollo de aplicaciones sin código.

**Características clave que se proporcionan a los grupos**

- Las aplicaciones se pueden compartir con un grupo para ejecutarse y modificarse

**¿Pueden las aplicaciones Power crear un grupo?**

No, Power apps no puede crear un grupo de 365 de Microsoft.

**¿Hay aplicaciones de energía sin un grupo?**

Sí, las aplicaciones se pueden crear en Power apps y residir dentro de la cuenta de los creadores hasta compartirla o publicarla.

**¿Puede haber varias aplicaciones por grupo?**

Sí, puede haber varias aplicaciones compartidas con un grupo.

**¿Las aplicaciones se pueden asociar a varios grupos?**

Sí, se puede compartir una aplicación con varios grupos.

**¿Puede la Asociación de una aplicación con un grupo cambiar?**

Sí, puesto que la asociación entre Power apps y un grupo de 365 de Microsoft está compartiendo solo: la aplicación sigue residiendo con el creador.

> [!IMPORTANT]
> Los [grupos deben estar habilitados para la seguridad antes de que las aplicaciones se puedan compartir con ellos](https://docs.microsoft.com/powerapps/maker/canvas-apps/share-app#share-an-app-with-office-365-groups).

**¿La eliminación de la aplicación elimina el grupo?**

No, las aplicaciones no están conectadas al grupo que no sea compartido con ellas.

## <a name="power-automate"></a>Power Automate

Power Automated (anteriormente conocido como Microsoft Flow) proporciona flujos de trabajo y servicios de automatización.

**Características clave que se proporcionan a los grupos**

- Los flujos de trabajo pueden compartirse con un grupo para ejecutarse y modificarse.

**¿Es posible automatizar la creación de un grupo?**

No, la automatización de la energía no puede crear un grupo de 365 de Microsoft en el contexto de estar asociado a uno.

Sin embargo, es posible crear un flujo que realice varias operaciones, como crear un grupo de seguridad de Azure AD o actualizar la pertenencia de un grupo de Microsoft 365.

**¿Existen flujos sin un grupo?**

Sí, se pueden crear flujos dentro de la automatización de la alimentación y residir dentro de la cuenta de los creadores hasta compartirla o publicarla.

**¿Puede haber varios flujos por grupo?**

Sí, puede haber varios flujos compartidos con un grupo.

**¿Se puede asociar un flujo con varios grupos?**

Sí, se puede compartir un flujo con varios grupos.

**¿Puede una asociación de flujo con un cambio de grupo?**

Sí, puesto que la asociación entre la automatización de energía y un grupo de 365 de Microsoft está compartiendo solo: el flujo sigue teniendo el creador.

**¿Se elimina un flujo, ¿eliminar el grupo?**

No, al igual que las aplicaciones de energía, los flujos no están conectados al grupo que no sea compartido con ellos.

## <a name="power-bi-classic"></a>Power BI (clásico)

Power BI ofrece paneles e informes interactivos controlados por datos.

**Características clave que se proporcionan a los grupos**

- Informes de datos

**¿Puede Power BI crear un grupo?**

Sí, al crear un área de trabajo clásica se creará un grupo de 365 de Microsoft.

**¿Hay un área de trabajo clásica de Power BI sin un grupo?**

No, [un área de trabajo clásica de Power BI debe estar asociada a un grupo](https://docs.microsoft.com/power-bi/collaborate-share/service-collaborate-power-bi-workspace).

**¿Puede haber varias áreas de trabajo de Power BI por grupo?**

No, la relación entre un área de trabajo clásica y un grupo es de 1:1.

**¿Se puede asociar un área de trabajo con varios grupos?**

Técnicamente no, mientras se crea el área de trabajo clásica con el grupo, el contenido se puede compartir fuera del grupo con usuarios y grupos de seguridad.

**¿Puede la Asociación del área de trabajo con un cambio de grupo?**

No, el espacio de trabajo clásico está asociado al grupo, pero el contenido se puede mover de un área de trabajo a otra dentro de la interfaz de Power BI o exportando el contenido de forma local.

**¿Se elimina el área de trabajo y se elimina el grupo?**

Sí, al eliminar el área de trabajo en Power BI, se eliminará el contenido y los servicios asociados a grupos y grupos.

## <a name="power-bi-new"></a>Power BI (nueva)

Power BI ofrece paneles e informes interactivos controlados por datos.

Al crear un área de trabajo nueva en Power BI no se crea un grupo de 365 de Microsoft, la creación de un grupo por cualquier otro método crea un nuevo espacio de trabajo (no clásico) en Power BI.

**Características clave que se proporcionan a los grupos**

- Informes de datos

**¿Puede Power BI crear un grupo?**

No, no se puede crear un grupo de Microsoft 365 desde la nueva interfaz de Power BI.

**¿El nuevo área de trabajo de Power BI existe sin un grupo?**

Sí, es posible que los informes y áreas de trabajo creados en Power BI no estén asociados a grupos de Microsoft 365.

**¿Puede haber varias áreas de trabajo por grupo?**

Sí, [se pueden compartir varias áreas de trabajo creadas por Power BI con un único grupo](https://docs.microsoft.com/power-bi/collaborate-share/service-create-the-new-workspaces#give-access-to-your-workspace).

**¿Se puede asociar un área de trabajo con varios grupos?**

No, un área de trabajo creada por Power BI solo se puede asociar a un único grupo.

**¿Puede una asociación de un área de trabajo con un cambio de grupo?**

Sí y no. Un área de trabajo creada por Power BI solo se puede asociar a un grupo individual a la vez, pero puede cambiar la asociación en cualquier momento. Un área de trabajo creada en Power BI por un grupo está permanentemente asociada a ese grupo.

**¿Se elimina el área de trabajo y se elimina el grupo?**

Sí, al eliminar el área de trabajo en Power BI, se eliminará el contenido y los servicios asociados con el grupo y el grupo.

## <a name="project-for-the-web"></a>Project para la web

Project for the Web ofrece la capacidad de crear planes de proyectos, diagramas de Gantt y guías básicas.
Características clave que se proporcionan a los grupos.

- Planes de proyecto

**¿Es posible que el proyecto para el Web cree un grupo?**

Sí, es posible crear un nuevo grupo de Microsoft 365 directamente desde Project para la Web.

**¿Existen proyectos sin un grupo?**

Sí, los proyectos pueden existir sin estar asociados con un grupo de 365 de Microsoft, aunque la asignación de tareas requiere la Asociación de grupos.

**¿Puede haber varios proyectos por grupo?**

Sí, es posible conectar varios proyectos en un único grupo.

**¿Es posible asociar un proyecto con varios grupos?**

No, un proyecto solo se puede asociar con un único grupo.

**¿Puede una asociación de un proyecto con un grupo cambia?**

No, una vez que se establece la asociación con un grupo, no puede cambiar.

**¿Se elimina el proyecto, ¿se elimina el grupo?**

No, al eliminar el proyecto en el proyecto para el Web no se eliminará el grupo.

## <a name="roadmap"></a>Hoja de ruta

Roadmap proporciona la capacidad de crear guías básicas del proyecto con Project para web y Project online.

**Características clave que se proporcionan a los grupos**

- Guías básicas del proyecto

**¿Se puede crear un grupo de planeación?**

Sí, es posible crear un nuevo grupo de Microsoft 365 directamente desde el mapa de ruta.

**¿Existe un plan de desarrollo sin un grupo?**

Sí, los planes de desarrollo pueden existir sin estar asociados con un grupo de 365 de Microsoft, pero compartir el plan requiere la Asociación de grupos.

**¿Puede haber varias guías básicas por grupo?**

Sí, es posible conectar varias guías planas a un único grupo.

**¿Se puede asociar un plan a varios grupos?**

No, un plan de desarrollo solo se puede asociar a un único grupo.

**¿Puede una asociación de plan con un cambio de grupo?**

No, una vez que se establece la asociación con un grupo, no puede cambiar.

**¿Se elimina el plan de desarrollo ¿eliminar el grupo?**

No, al eliminar el plan no se eliminará el grupo.

## <a name="sharepoint"></a>SharePoint

SharePoint es una plataforma de administración de contenido basada en Web que ofrece, entre otras cosas, servicios de almacenamiento para una cantidad de servicios de Microsoft 365.

**Características clave que se proporcionan a los grupos**

- Biblioteca de documentos
- Biblioteca para el almacenamiento de blocs de notas de OneNote
- Almacenamiento de los archivos wiki de Teams

**¿Puede SharePoint crear un grupo?**

Sí, al crear un sitio de grupo en SharePoint se creará un grupo de Microsoft 365 de forma predeterminada. También es posible crear un grupo y, opcionalmente, un equipo para un sitio existente.

**¿Existen sitios de SharePoint sin un grupo?**

Sí, SharePoint ofrece una serie de servicios y sitios no asociados a grupos, como sitios de comunicación y de concentradores. 

**¿Puede haber varios sitios por grupo?**

No, solo puede haber un único sitio por grupo. Los canales privados en Microsoft Teams usan sitios adicionales que no están conectados al grupo.

**¿Se pueden asociar sitios a varios grupos?**

Técnicamente no, pero mientras se crea un sitio con un grupo, el contenido se puede compartir con otros grupos.

**¿Puede cambiar la Asociación de un sitio con un grupo?**

No, el sitio en sí está asociado con el grupo, pero el contenido se puede mover de un sitio a otro dentro de la interfaz de SharePoint, exportando el contenido localmente o con una herramienta de terceros.

**¿La eliminación del sitio elimina el grupo?**

Sí, al eliminar el sitio en SharePoint se eliminarán el contenido y los servicios asociados a grupos y grupos.

## <a name="stream"></a>Stream

Microsoft Stream es una plataforma de hospedaje y uso compartido de vídeo.

**Características clave que se proporcionan a los grupos**

- Almacenamiento de vídeo
- Grabación de reuniones de Microsoft Teams
- Canales de vídeo

**¿Puede la secuencia crear un grupo?**

Sí, es posible crear un nuevo grupo de Microsoft 365 directamente desde la secuencia.

**¿Existe la secuencia sin un grupo?**

Sí, los canales de vídeo y los vídeos pueden existir en la secuencia sin estar asociados a un grupo.

**¿Puede haber varios vídeos y canales por grupo?**

Sí, puede haber varios vídeos y canales en cada grupo.

**¿Se puede asociar un vídeo o un canal con varios grupos?**

Sí, mientras se crea un vídeo o un canal con un grupo, se puede compartir con otros grupos.

**¿Puede su asociación con un grupo cambiar?**

Sí y no; los vídeos de la secuencia son propiedad de la carga original del cargador o la grabadora de reuniones, por lo que se pueden asociar a cualquier grupo, pero los canales de vídeo solo pueden asociarse con el grupo en el que se crearon originalmente.

**¿Se elimina el grupo de vídeos o canales?**

No, la eliminación de vídeos o canales no elimina el grupo. Sin embargo, la eliminación del grupo en secuencia eliminará el contenido y los servicios asociados a los grupos, excepto los vídeos reales.

## <a name="yammer"></a>Yammer

Yammer es una plataforma social empresarial diseñada para fomentar la participación de la comunidad dentro de las organizaciones y entre ellas.

La creación de una comunidad (antes denominada "grupo") en Yammer crea un buzón de correo, pero, en este momento, no se usa.

Un grupo de Microsoft 365 asociado con Yammer no se puede usar con un equipo en Microsoft Teams.

**Características clave que se proporcionan a los grupos**

- Área de conversación

**¿Puede Yammer crear un grupo de Microsoft 365?**

Sí, al crear un grupo nuevo en Yammer, se creará un nuevo grupo de Microsoft 365, si las plataformas están conectadas y si el usuario tiene la capacidad de crear un grupo.

No se puede crear un grupo de Yammer con el grupo de Microsoft 365 asociado en ninguna interfaz o servicio que no sea Yammer en sí.

**¿Existe un grupo de Yammer sin un grupo de Microsoft 365?**

Sí, es posible crear un grupo de Yammer sin un grupo de 365 de Microsoft.

Si la plataforma Yammer no está conectada a grupos de Microsoft 365, o los usuarios no tienen la capacidad de crear un grupo 365 de Microsoft, los grupos de Yammer se crean sin una asociación de grupo de Microsoft 365.

**¿Puede haber varios grupos de Yammer por grupo de Microsoft 365?**

No, la relación entre un grupo de Yammer y un grupo de 365 de Microsoft es 1:1.

**¿Se puede asociar un grupo de Yammer con varios grupos de Microsoft 365?**

No, el grupo de Yammer solo se puede asociar con un solo grupo de Microsoft 365. Es posible que las publicaciones se compartan o se muevan a otros grupos de Yammer.

**¿Puede una asociación de un grupo de Yammer con un cambio de grupo de Microsoft 365?**

No, el grupo de Yammer solo se puede asociar al grupo de 365 de Microsoft al que estaba asociado originalmente.

**¿Se elimina el grupo de Yammer? eliminar el grupo 365 de Microsoft?**

Sí, al eliminar el grupo en Yammer, se eliminará el contenido y los servicios asociados de grupo de Microsoft y el grupo relacionados.

