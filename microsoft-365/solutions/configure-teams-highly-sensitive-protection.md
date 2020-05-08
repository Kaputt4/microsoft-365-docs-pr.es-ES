---
title: Configuración de equipos con protección de datos con un nivel de confidencialidad alto
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365solutions
ms.custom:
- Ent_Solutions
description: Obtenga información sobre cómo implementar equipos con la protección de datos con un nivel de confidencialidad alto.
ms.openlocfilehash: f60c46c3b596c131bb04a49f0293c6dd8bbbea2b
ms.sourcegitcommit: 46644f9778bc70ab6d62783e0a1e60ba2eccc27f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/08/2020
ms.locfileid: "44166178"
---
# <a name="configure-teams-with-protection-for-highly-sensitive-data"></a>Configuración de equipos con protección de datos con un nivel de confidencialidad alto

En este artículo, observamos la configuración de un equipo con un nivel de protección de confidencialidad alta. Asegúrese de que ha completado los pasos descritos en [Implementar equipos con la protección de línea base](configure-teams-baseline-protection.md) antes de seguir los pasos de este artículo.

Para este nivel de protección, se crea una etiqueta de sensibilidad que puede usarse en toda la organización para los equipos y archivos altamente confidenciales. Solo los miembros de su organización y los invitados que haya especificado podrán descifrar los archivos que usen esta etiqueta. Si tiene que aislar aún más los permisos para que solo los miembros de un equipo específico puedan descifrar los archivos, consulte [Implementación de un equipo con aislamiento de seguridad](secure-teams-security-isolation.md).

El nivel de confidencialidad alto ofrece las siguientes protecciones adicionales al nivel de línea base:

- Una etiqueta de confidencialidad para el equipo que le permite activar o desactivar el uso compartido de invitado y limita el acceso a contenido de SharePoint a solo web para dispositivos no administrados. Esta etiqueta también se puede usar para clasificar y cifrar archivos.
- Un tipo de vínculo para compartir predeterminado más restrictivo
- Solo los propietarios del equipo podrán crear canales privados.
- Las solicitudes de acceso para el sitio de SharePoint asociado están desactivadas.

## <a name="guest-sharing"></a>Uso compartido de invitados

Según la naturaleza de su empresa, es posible que quiera habilitar o no el uso compartido de invitados para equipos que contienen datos con un nivel de confidencialidad alto. Si tiene previsto colaborar con personas ajenas a su organización en el equipo, le recomendamos que habilite el uso compartido de invitados. Microsoft 365 incluye una variedad de características de seguridad y cumplimiento para ayudarle a compartir contenido confidencial de forma segura. Por lo general, se trata de una opción más segura que enviar correo directamente a las personas de fuera de su organización.

Para más información sobre el uso compartido con invitados de forma segura, vea los recursos siguientes:

- [Limitar la exposición accidental de archivos al compartirlos con usuarios externos a la organización](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure)
- [Crear un entorno seguro de uso compartido para invitados](https://docs.microsoft.com/microsoft-365/solutions/create-secure-guest-sharing-environment)

Para permitir o bloquear el uso compartido de invitados, utilizamos una combinación de una etiqueta de confidencialidad para el equipo y controles de uso compartido a nivel de sitio para el sitio de SharePoint asociado, ambos tratados más adelante.

## <a name="sensitivity-labels"></a>Etiquetas de confidencialidad

Para el nivel de protección de confidencialidad alta, usaremos una etiqueta de confidencialidad para clasificar al equipo. Esta etiqueta también se puede usar para clasificar y cifrar archivos individuales en este o en otros equipos, o en otras ubicaciones de archivo como SharePoint o OneDrive. 

Como primer paso, debe habilitar las etiquetas de confidencialidad para los equipos. Consulte [Usar etiquetas de confidencialidad para proteger el contenido en Microsoft Teams, los grupos de Microsoft 365 y los sitios de SharePoint](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites) para más información.

Si ya tiene las etiquetas de confidencialidad implementadas en la organización, tenga en cuenta que se adapta a la estrategia general de etiquetas. Si es necesario, puede cambiar el nombre o la configuración para satisfacer las necesidades de su organización.

Cuando haya habilitado las etiquetas de confidencialidad para Teams, el siguiente paso es crear la etiqueta.

Crear una etiqueta de confidencialidad
1. Abra el [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com).
2. En **Soluciones**, haga clic en **Protección de la información**.
3. Haga clic en **Crear una etiqueta**.
4. Asigne un nombre a la etiqueta. Le sugerimos **Confidencialidad alta**, pero puede elegir otro nombre si ya está en uso.
5. Agregue información sobre herramientas y haga clic en **Siguiente**.
6. En la página **Cifrado**, en el menú desplegable **Cifrado**, elija **Aplicar**.
7. En **Asignar permisos a usuarios y grupos específicos**, haga clic en **Asignar permisos**.
8. Haga clic en **Agregar todos los usuarios y grupos de su organización**.
9. Si hay usuarios invitados que deben tener permisos para descifrar los archivos, haga clic en **Agregar usuarios o grupos** y agréguelos.
10.  Haga clic en **Guardar**y después en **Siguiente**.
11. En la página **Marcado de contenido**, active la marcación del contenido si quiere agregar automáticamente un encabezado, un pie de página o una marca de agua a los archivos clasificados con esta etiqueta.
12. En la página **Configuración de sitio y grupo**, establezca **Configuración de sitio y grupo** como **Activado**.
13. En el menú desplegable **Privacidad de los sitios de equipo conectados a grupos de Office 365**, elija **Privado: solo los miembros pueden acceder al sitio**.
14. Si desea permitir el acceso de invitado, seleccione la casilla de verificación **Permitir que los propietarios del grupo de Office 365 agreguen personas ajenas a la organización al grupo**. 
15. En **Equipos no administrados**, elija **Bloquear el acceso**.
16. Haga clic en **Siguiente**.
17. En la página **Etiquetado automático para las aplicaciones de Office**, haga clic en **Siguiente**.
18. Haga clic en **Enviar** y después en **Listo**.

Una vez que haya creado la etiqueta, debe publicarla para los usuarios que la van a usar. Para la protección confidencial, haremos que la etiqueta esté disponible para todos los usuarios. Publique la etiqueta en el Centro de cumplimiento de Microsoft 365, en la pestaña **Directivas de etiqueta** de la página **Protección de la información**. Si tiene una directiva existente que se aplica a todos los usuarios, agregue esta etiqueta a esa directiva. Si necesita crear una directiva nueva, vea [Publicar etiquetas de confidencialidad creando una directiva de etiqueta](https://docs.microsoft.com/microsoft-365/compliance/create-sensitivity-labels#publish-sensitivity-labels-by-creating-a-label-policy).

## <a name="create-a-team"></a>Crear un equipo

La configuración adicional del escenario de confidencialidad alta se hace en el sitio de SharePoint asociado al equipo, por lo que el siguiente paso es crear un equipo.

Para crear un equipo para información con un nivel de confidencialidad alto
1. En Teams, haga clic en **Teams** en el lado izquierdo de la aplicación, luego haga clic en **Unirse o crear un equipo** en la parte inferior de la lista de equipos.
2. Haga clic en **Crear equipo** (primera tarjeta, esquina superior izquierda).
3. Elija **Crear un equipo desde cero**.
4. En la lista **Confidencialidad**, elija la etiqueta **Confidencialidad alta** que acaba de crear.
5. En **Privacidad**, haga clic en **Privado**.
6. Escriba un nombre para el equipo y haga clic en **Crear**.
7. Agregue usuarios al equipo y haga clic en **Cerrar**.

## <a name="private-channel-settings"></a>Configuración de canal privado

En este nivel, restringimos la creación de canales privados a los propietarios del equipo.

Para restringir la creación de un canal privado
1. En el equipo, haga clic en **Más opciones** y después en **Administrar equipo**.
2. En la pestaña **Configuración**, expanda **Permisos de los miembros**.
3. Desactive la casilla de verificación **Permitir a los miembros crear canales privados**.

También puede usar [directivas de equipos](https://docs.microsoft.com/MicrosoftTeams/teams-policies) para controlar quién puede crear canales privados.

## <a name="sharepoint-settings"></a>Configuración de SharePoint

Cada vez que cree un nuevo equipo con la etiqueta de confidencialidad alta, debe realizar dos pasos en SharePoint:

- Actualice la configuración de uso compartido de invitado para el sitio en el Centro de administración de SharePoint para que coincida con lo que ha elegido al crear la etiqueta, y actualice el vínculo para compartir predeterminado a *Usuarios con acceso existente*.
- Actualice la configuración de uso compartido del sitio en el propio sitio para evitar que los miembros compartan los archivos, las carpetas o el sitio, y desactivar las solicitudes de acceso.

### <a name="site-guest-sharing-settings"></a>Configuración de uso compartido de invitado del sitio

La configuración de uso compartido de invitado que eligió al crear la etiqueta (que solo afecta a la pertenencia al equipo) debe coincidir con la configuración de uso compartido de invitado para el sitio de SharePoint asociado de la siguiente manera:

|Configuración de etiqueta|Configuración del sitio de SharePoint|
|:------------|:----------------------|
|**Permitir que los propietarios de grupos de Ofﬁce 365 agreguen a usuarios ajenos a la organización a los grupos** seleccionado|**Invitados nuevos y existentes** (predeterminado para equipos nuevos)|
|**Permitir que los propietarios de grupos de Ofﬁce 365 agreguen a usuarios ajenos a la organización a los grupos** no seleccionado|**Solo personas de la organización**|

Para actualizar la configuración del sitio
1. Abra el [Centro de administración de SharePoint](https://admin.microsoft.com/sharepoint).
2. En **Sitios**, haga clic en **Sitios activos**.
3. Haga clic en el sitio que está asociado al equipo.
4. En **Uso compartido externo** de la pestaña **Directivas**, haga clic en **Editar**.
5. Si permitió el uso compartido de invitados al crear la etiqueta Confidencialidad alta, asegúrese de que **Invitados nuevos y existentes** está seleccionado. Si no ha permitió el uso compartido cuando creó la etiqueta, elija **Solo las personas de la organización**.
6. En Tipo de vínculo de uso compartido predeterminado, desactive la casilla de verificación **Igual que la configuración de nivel de organización** y seleccione **Usuarios con acceso existente**.
7. Haga clic en **Guardar**.

Si quiere realizar scripts como parte del proceso de creación de su equipo, puede usar [Set-SPOSite](https://docs.microsoft.com/powershell/module/sharepoint-online/set-sposite) con los parámetros siguientes:

- `-SharingCapability Disabled` para desactivar el uso compartido de invitado (activado de forma predeterminada)
- `-DefaultSharingLinkType Internal` para cambiar el vínculo para compartir predeterminado a *Usuarios específicos*

#### <a name="private-channels"></a>Canales privados

Si agrega canales privados al equipo, cada canal privado crea un sitio de SharePoint nuevo con la configuración de uso compartido predeterminada. Estos sitios no están visibles en el Centro de administración de SharePoint, por lo que debe usar el cmdlet Set-SPOSite de PowerShell para actualizar la configuración de uso compartido de invitado.

### <a name="site-sharing-settings"></a>Configuración de uso compartido del sitio 

Para ayudar a garantizar que el sitio de SharePoint no se comparta con personas que no son miembros del equipo, limitamos dicho uso compartido a los propietarios. También limitamos el uso compartido de archivos y carpetas a los propietarios del equipo. Esto permite asegurar que los propietarios son conscientes siempre que se comparte un archivo con alguien ajeno al equipo.

Para configurar el uso compartido del sitio solo para propietarios
1. En Teams, vaya a la pestaña **General** del equipo que quiere actualizar.
2. En la barra de herramientas del equipo, haga clic en **Archivos**.
3. Haga clic en los puntos suspensivos y, luego, en **Abrir en SharePoint**.
4. En la barra de herramientas, haga clic en el sitio de SharePoint subyacente, en el icono de configuración y, luego, en **Permisos del sitio**.
5. En el panel Permisos del sitio, en **Configuración de uso compartido**, haga clic en **Cambiar configuración de uso compartido**.
6. En **Permisos de uso compartido**, seleccione **Solo los propietarios del sitio pueden compartir archivos, carpetas y el sitio**.
7. Establezca **Permitir solicitudes de acceso** en **Desactivado** y, después, haga clic en **Guardar**.

## <a name="see-also"></a>Consulte también

[Crear y configurar etiquetas de confidencialidad y sus directivas](https://docs.microsoft.com/microsoft-365/compliance/create-sensitivity-labels)

