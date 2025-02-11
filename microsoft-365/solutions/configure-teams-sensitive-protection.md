---
title: Configure equipos con protección de datos confidenciales
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: high
search.appverid:
- MET150
ms.collection:
- highpri
- Ent_O365
- Strat_O365_Enterprise
- m365solution-3tiersprotection
- m365solution-securecollab
ms.custom:
- Ent_Solutions
- admindeeplinkSPO
recommendations: false
description: Obtenga información sobre cómo implementar equipos con la protección de datos confidenciales.
ms.openlocfilehash: 23c9d4761ce20cc003c91b2fea329ca74b2bc835
ms.sourcegitcommit: fce27da5140691b013a6f7c0ea9c88b4ea4b7c10
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2022
ms.locfileid: "67987222"
---
# <a name="configure-teams-with-protection-for-sensitive-data"></a>Configure equipos con protección de datos confidenciales

En este artículo, observamos la configuración de un equipo con un nivel de protección confidencial. Asegúrese de que ha completado los pasos descritos en [Implementar equipos con la protección de línea base](configure-teams-baseline-protection.md) antes de seguir los pasos de este artículo. El nivel confidencial ofrece las siguientes protecciones adicionales al nivel de línea base:

- A sensitivity label for the team that allows you to turn guest sharing on or off and limits access to SharePoint content to web-only for unmanaged devices. This label can also be used to classify files.
- Un tipo de vínculo para compartir predeterminado más restrictivo
- Solo los propietarios del equipo podrán crear canales privados.

## <a name="video-demonstration"></a>Demostración de vídeo

Vea este vídeo para conocer los procedimientos descritos en este artículo.
<br>
<br>
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4NMS6]

## <a name="guest-sharing"></a>Uso compartido de invitados

Según la naturaleza de su empresa, es posible que quiera habilitar o no el uso compartido para invitados para equipos que contienen datos confidenciales. Si tiene previsto colaborar con personas ajenas a su organización en el equipo, le recomendamos que habilite el uso compartido de invitados. Microsoft 365 incluye una variedad de características de seguridad y cumplimiento para ayudarle a compartir contenido confidencial de forma segura. Por lo general, se trata de una opción más segura que enviar correo directamente a las personas de fuera de su organización.

Para más información sobre el uso compartido de invitados de forma segura, vea los recursos siguientes:

- [Limitar la exposición accidental de archivos al compartirlos con usuarios externos a la organización](./share-limit-accidental-exposure.md)
- [Crear un entorno seguro de uso compartido para invitados](./create-secure-guest-sharing-environment.md)

Para permitir o bloquear el uso compartido de invitados, utilizamos una combinación de una etiqueta de confidencialidad para el equipo y controles de uso compartido a nivel de sitio para el sitio de SharePoint asociado, ambos tratados más adelante.

## <a name="sensitivity-labels"></a>Etiquetas de confidencialidad

Para el nivel de protección confidencial, usaremos una etiqueta de confidencialidad para clasificar el equipo. Esta etiqueta también se puede usar para clasificar archivos individuales en este o en otros equipos, o en otras ubicaciones de archivo como SharePoint o OneDrive. 

Como primer paso, debe habilitar las etiquetas de confidencialidad para Teams. Consulte [Usar etiquetas de confidencialidad para proteger el contenido en Microsoft Teams, grupos de Office 365 y sitios de SharePoint](../compliance/sensitivity-labels-teams-groups-sites.md) para más información.

Si ya tiene las etiquetas de confidencialidad implementadas en la organización, tenga en cuenta que se adapta a la estrategia general de etiquetas. Si es necesario, puede cambiar el nombre o la configuración para satisfacer las necesidades de su organización.

Cuando haya habilitado las etiquetas de confidencialidad para Teams, el siguiente paso es crear la etiqueta.

Crear una etiqueta de confidencialidad
1. Abra el [portal de cumplimiento de Microsoft Purview](https://compliance.microsoft.com).
2. En **Soluciones**, haga clic en **Protección de la información**.
3. Haga clic en **Crear una etiqueta**.
4. Give the label a name. We suggest **Sensitive**, but you can choose a different name if that one is already in use.
5. Escriba un nombre y una descripción para el complemento y, a continuación, haga clic en **Siguiente**.
6. En la página **Definir el ámbito de la página de la etiqueta**, seleccione **Archivos & mensajes de correo electrónico** y **Grupos & sitios** y haga clic en **Siguiente**.
7. En la página **Elija la configuración de protección de archivos y mensajes de correo electrónico**, haga clic en **Siguiente**.
8. En la página *Etiquetado automático para archivos y mensajes de correo electrónico**, haga clic en **Siguiente**.
9. En la página **Definir la configuración de protección de los sitios y grupos**, seleccione **Configuración de privacidad y acceso de usuarios externo** y **Configuración de acceso de dispositivo y uso compartido externo** y haga clic en **Siguiente**.
10. En la página **Definir privacidad y acceso a usuarios externos**, en **Privacidad**, seleccione la opción **Privado**.
11. Si desea permitir el acceso de invitado, en **Acceso de usuarios externos**, seleccione **Permitir que los propietarios del grupo de Microsoft 365 agreguen personas de fuera de su organización al grupo como invitados**.
12. Haga clic en **Siguiente**.
13. En la página **Definir el uso compartido externo y el acceso al dispositivo**, seleccione **Controlar el uso compartido externo en sitios de SharePoint etiquetados**.
14. En **El contenido se puede compartir con**, elija **Invitados nuevos y existentes** si va a permitir el acceso de invitado o **Solo los usuarios de su organización** en caso contrario.
15. En **Dispositivos no administrados**, elija **Permitir el acceso limitado, sólo a través de la web**.
16. Haga clic en **Siguiente**.
17. En la página **Etiquetado automático para las columnas de la base de datos**, haga clic en **Siguiente**.
18. Haga clic en **Crear etiqueta** y después en **Listo**.

Una vez que haya creado la etiqueta, debe comunicarla a los usuarios que la van a usar. Para la protección confidencial, haremos que la etiqueta esté disponible para todos los usuarios. La etiqueta se publica en el portal de cumplimiento de Microsoft Purview, en la pestaña **Directivas de etiquetas** de la página **Information Protection**. Si tiene una directiva existente que se aplica a todos los usuarios, agregue esta etiqueta a esa directiva. Si necesita crear una directiva nueva, vea [Publicar etiquetas de confidencialidad creando una directiva de etiqueta](../compliance/create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy).

## <a name="create-a-team"></a>Crear un equipo

La configuración adicional del escenario confidencial se hace en el sitio de SharePoint asociado al equipo, por lo que el siguiente paso es crear un equipo.

Para crear un equipo para información confidencial
1. En Teams, haga clic en **Teams** en el lado izquierdo de la aplicación, luego haga clic en **Unirse o crear un equipo** en la parte inferior de la lista de equipos.
2. Haga clic en **Crear equipo** (primera tarjeta, esquina superior izquierda).
3. Elija **Crear un equipo desde cero**.
4. En la lista **Confidencialidad**, elija la etiqueta **confidencial** que acaba de crear.
5. En **Privacidad**, haga clic en **Privado**.
6. Escriba un nombre para el equipo y haga clic en **Crear**.
7. Agregue usuarios al equipo y, después, haga clic en **Cerrar**.

## <a name="private-channel-settings"></a>Configuración de canal privado

En este nivel, restringimos la creación de canales privados a los propietarios del equipo.

Para restringir la creación de un canal privado
1. En el equipo, haga clic en **Más opciones** y después en **Administrar equipo**.
2. En la pestaña **Configuración**, expanda **Permisos de los miembros**.
3. Desactive la casilla de verificación **Permitir a los miembros crear canales privados**.

También puede usar [Directivas de equipos](/MicrosoftTeams/teams-policies) para controlar quién puede crear canales privados.

## <a name="shared-channel-settings"></a>Configuración del canal compartido

[Shared channels](/MicrosoftTeams/shared-channels) doesn't have team-level settings. The shared channel settings you configure in the Teams admin center and Azure AD apply to all teams regardless of sensitivity.

## <a name="sharepoint-settings"></a>Configuración de SharePoint

Cada vez que cree un nuevo equipo con la etiqueta confidencial, debe realizar dos pasos en SharePoint:

- Actualice la configuración de uso compartido de invitado para el sitio en el Centro de administración de SharePoint Online para actualizar el vínculo para compartir predeterminado a *Personas específicas*.
- Actualice la configuración de uso compartido del sitio en el propio sitio para evitar que los miembros compartan el sitio.

### <a name="site-default-sharing-link-settings"></a>Configuración del vínculo para compartir predeterminado del sitio

Para actualizar el tipo de vínculo para compartir predeterminado del sitio

1. Abra el centro de administración SharePoint y, en **Sitios**, seleccione <a href="https://go.microsoft.com/fwlink/?linkid=2185220" target="_blank">**Sitios activos**</a>.
1. Haga clic en el sitio que está asociado al equipo.
1. En **Uso compartido externo** de la pestaña **Directivas**, haga clic en **Editar**.
1. En Tipo de vínculo de uso compartido predeterminado, desactive la casilla de verificación **Igual que la configuración de nivel de organización** y seleccione **Personas específicas (solo las personas que el usuario especifica)**.
1. Seleccione **Guardar**.

Si quiere utilizar un script para esto como parte del proceso de creación del equipo, puede usar [Set-SPOSite](/powershell/module/sharepoint-online/set-sposite) con el parámetro `-DefaultSharingLinkType Direct` para cambiar el vínculo de uso compartido predeterminado a *Usuarios específicos*.

Tenga en cuenta que si agrega canales privados o compartidos al equipo, cada uno de ellos crea un nuevo sitio de SharePoint con la configuración de uso compartido predeterminada. Puede actualizarlos en el Centro de administración de SharePoint seleccionando los sitios asociados con el equipo.

### <a name="site-sharing-settings"></a>Configuración de uso compartido del sitio 

Para ayudar a garantizar que el sitio de SharePoint no se comparta con personas que no son miembros del equipo, limitamos dicho uso compartido a los propietarios. Esto solo es necesario para el sitio de SharePoint que se creó con el equipo. Los sitios adicionales creados como parte de canales privados o compartidos no se pueden compartir fuera del equipo o canal.

Para configurar el uso compartido del sitio solo para propietarios
1. En Teams, vaya a la pestaña **General** del equipo que quiere actualizar.
2. En la barra de herramientas del equipo, haga clic en **Archivos**.
3. Haga clic en los puntos suspensivos y, luego, en **Abrir en SharePoint**.
4. En la barra de herramientas, haga clic en el sitio de SharePoint subyacente, en el icono de configuración y, luego, en **Permisos del sitio**.
5. En el panel **Permisos del sitio**, en **Uso compartido del sitio**, haga clic en **Cambiar cómo pueden compartir los miembros**.
6. En **Permisos de uso compartido**, elija **Los propietarios y miembros del sitio y las personas con permisos de edición pueden compartir archivos y carpetas, pero solo los propietarios de sitios pueden compartir el sitio** y haga clic en **Guardar**.


## <a name="related-topics"></a>Temas relacionados

[Crear y configurar etiquetas de confidencialidad y sus directivas](../compliance/create-sensitivity-labels.md)
