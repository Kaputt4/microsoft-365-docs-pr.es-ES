---
title: Introducción a las opciones de colaboración externa en Microsoft 365
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: ''
ms.collection:
- SPO_Content
ms.localizationpriority: medium
description: Obtenga información sobre cómo las personas de fuera de su organización pueden acceder a su suscripción de Microsoft 365 para reuniones, uso compartido de invitados, chat y colaboración.
ms.openlocfilehash: 988a1ecae8a060cae2334f97ef19bc90ba2be6bc
ms.sourcegitcommit: 5eff41a350a01e18d9cdd572c9d8ff99d6c9563a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2022
ms.locfileid: "64836465"
---
# <a name="overview-of-external-collaboration-options-in-microsoft-365"></a>Introducción a las opciones de colaboración externa en Microsoft 365

Con Microsoft 365, los usuarios pueden colaborar con personas ajenas a su organización de varias maneras. Los usuarios pueden compartir archivos, invitar a invitados a equipos, tener reuniones con participantes externos y chatear con personas de otras organizaciones. En este artículo se tratan las opciones de colaboración externa disponibles y los vínculos al contenido que necesita para configurar cada una de ellas.

En la tabla siguiente se muestran las principales formas en que los usuarios de fuera de la organización pueden acceder a los recursos de Microsoft 365:

|Actividad|Tipo de cuenta|Configuración predeterminada|
|:-------|:-----------|:--------------|
|Uso compartido de archivos y carpetas autenticados|Cuenta de invitado|Habilitado|
|Uso compartido de sitios|Cuenta de invitado|Habilitado|
|Uso compartido de equipos|Cuenta de invitado|Habilitado|
|Canal compartido en Teams|Cuenta externa Microsoft 365 existente|Deshabilitado|
|Chat externo y reuniones|Cuenta externa Microsoft 365 existente|Habilitado|
|Unirse a una reunión anónima|Ninguno|Habilitado|
|Uso compartido de archivos y carpetas no autenticados|Ninguno|Habilitado|

Las personas ajenas a la organización no tienen acceso a menos que un usuario de la organización inicie una de estas actividades. Puede deshabilitar cualquiera de estas configuraciones si no desea permitir esa actividad en su organización.

## <a name="document-site-and-team-sharing-with-guest-accounts"></a>Uso compartido de documentos, sitios y equipos con cuentas de invitado

El uso compartido de documentos, sitios y equipos con personas ajenas a la organización usa *cuentas de invitado*. Las cuentas de invitado son un tipo de cuenta en Azure Active Directory que se administra a través [de Azure AD colaboración B2B](/azure/active-directory/external-identities/what-is-b2b). Se pueden usar para compartir recursos de su organización con cualquier persona que tenga una dirección de correo electrónico. Puede administrar las cuentas de invitado de la misma manera que administra los usuarios de su organización. Los invitados no requieren una licencia para la mayoría de las características de colaboración. 

Los invitados solo pueden acceder a los recursos que comparta específicamente con ellos.

Si el invitado tiene una cuenta profesional o educativa en otra organización o una cuenta de Microsoft, puede iniciar sesión con su nombre de usuario y contraseña normales. Si tienen un tipo de cuenta diferente, como una cuenta de Gmail, pueden iniciar sesión mediante un código de acceso único que se envía a su dirección de correo electrónico.

Con los invitados puede:

- Invítelos a Microsoft 365 grupos, equipos o sitios de SharePoint en los que puedan colaborar con personas de su organización.
- Comparta un único archivo o una carpeta con ellos que puedan ver o editar en función de los permisos que se les concedan.

Para obtener información sobre cómo planear la colaboración con invitados en Microsoft 365, consulte las siguientes referencias:

- [Planear la colaboración externa](/microsoft-365/solutions/plan-external-collaboration)
- [Configuración del uso compartido de archivos seguro y la colaboración con Microsoft Teams](/microsoft-365/solutions/setup-secure-collaboration-with-teams)

Para obtener información sobre cómo configurar Microsoft 365 para la colaboración con invitados, consulte las siguientes referencias:

- [Colaborar con invitados en un documento](/microsoft-365/solutions/collaborate-on-documents)
- [Colaborar con invitados en un sitio](/microsoft-365/solutions/collaborate-in-site)
- [Colaborar con invitados en un equipo](/microsoft-365/solutions/collaborate-as-team)
 
## <a name="shared-channels"></a>Canales compartidos

Los canales compartidos son un tipo de canal Teams que permite compartir con personas ajenas al equipo, incluidas las personas de otras organizaciones Microsoft 365. Aunque los canales compartidos están activados de forma predeterminada en Teams, la colaboración externa con canales compartidos está deshabilitada de forma predeterminada. La colaboración externa con canales compartidos usa [Azure AD conexión directa B2B](/azure/active-directory/external-identities/b2b-direct-connect-overview), que permite agregar personas de otras organizaciones de Microsoft 365 a canales de Teams sin necesidad de crear una cuenta de invitado.

Los canales compartidos tienen una ventaja particular sobre las cuentas de invitado, ya que no requieren que los participantes externos cambien las organizaciones en el Teams cliente de escritorio o inicien sesión en su organización. Pueden permanecer conectados a su organización y acceder directamente al canal.

El uso compartido de canales con personas ajenas a la organización requiere que su organización y la organización externa configuren una relación organizativa en [Azure AD Conectar de B2B Direct](/azure/active-directory/external-identities/b2b-direct-connect-overview).

Para obtener información sobre cómo configurar Microsoft 365 para la colaboración externa con canales compartidos, consulte las siguientes referencias:

- [Planear la colaboración externa](/microsoft-365/solutions/plan-external-collaboration)
- [Canales compartidos en Microsoft Teams](/MicrosoftTeams/shared-channels)
- [Colaborar con participantes externos en un canal](/microsoft-365/solutions/collaborate-teams-direct-connect)

## <a name="external-chat-and-meetings"></a>Chat externo y reuniones

Los usuarios de su organización pueden chatear, agregar usuarios a reuniones y usar audio o videoconferencia en Teams con usuarios de organizaciones externas Microsoft 365. De forma predeterminada, los usuarios de su organización pueden comunicarse de estas maneras con todos los demás dominios de Microsoft 365. Los usuarios de otras organizaciones pueden comunicarse de estas maneras con los usuarios si conocen la dirección de correo electrónico del usuario. Puede permitir o bloquear dominios específicos o bloquear todos los dominios si desea deshabilitar la característica.

También puede permitir que los usuarios de su organización se comuniquen con personas de fuera de la organización que usan cuentas de Teams que no están administradas por una organización, así como Skype Empresarial (en línea y local) y Skype usuarios.

Las cuentas de invitado no se usan como parte de chats y reuniones externos. Los participantes externos permanecen conectados a su organización o a Skype y pueden comunicarse directamente con las personas de la organización. No tienen acceso a sus equipos o canales.

Para obtener información sobre cómo configurar Microsoft 365 para reuniones y chats externos, consulte las siguientes referencias:

- [Uso del acceso de invitado y el acceso externo para colaborar con personas ajenas a la organización](/microsoftteams/communicate-with-users-from-other-organizations)
- [Administrar el acceso externo en Microsoft Teams](/microsoftteams/manage-external-access).

## <a name="anonymous-meeting-join"></a>Unirse a una reunión anónima 

Los usuarios de fuera de la organización pueden unirse a las reuniones de las siguientes maneras:

- Si ha iniciado sesión en su organización con una cuenta de invitado, se une a las reuniones como invitado.
- Si han iniciado sesión en otra organización con una cuenta profesional o educativa y su organización ha habilitado el acceso externo, se unen a las reuniones como participantes externos.
- Si no son invitados o participantes externos, deben unirse a las reuniones de forma anónima.

Si la configuración de unión anónima está habilitada para su organización, los usuarios anónimos solo pueden unirse a una reunión mediante un vínculo de reunión compartido con ellos (por ejemplo, un vínculo en la invitación a la reunión). Se les pedirá que escriban un nombre para mostrar de su elección al unirse a la reunión de forma anónima. Dependiendo de la configuración de la sala de espera, el usuario anónimo puede ser admitido automáticamente en la reunión o agregarse a una sala de espera donde el organizador de la reunión (o los participantes de la reunión con el rol moderador) pueden permitir o denegar el acceso a la reunión. 

No es posible comprobar la identidad de los usuarios anónimos antes, durante o después de la reunión. 

Puede controlar la capacidad de los usuarios anónimos para unirse a reuniones en el nivel de organización. Si está habilitada para la organización, los organizadores de reuniones pueden controlar la unión anónima a través de la configuración de la directiva de reunión.

Para obtener información sobre cómo configurar la unión anónima para reuniones, consulte [Administración de la configuración de reuniones en Microsoft Teams](/microsoftteams/meeting-settings-in-teams).

## <a name="unauthenticated-file-and-folder-access"></a>Acceso a archivos y carpetas no autenticados

En Microsoft 365, los archivos y carpetas de Teams, SharePoint y OneDrive se pueden compartir mediante vínculos no autenticados (o *cualquiera*). Los vínculos de cualquiera proporcionan acceso al elemento compartido a cualquier persona que tenga el vínculo. Todos los vínculos se pueden compartir con otros usuarios, lo que les da acceso al archivo o carpeta.

Las personas que usan un vínculo Cualquiera no tienen que autenticarse y sus accesos no se pueden auditar. Los propietarios de archivos y carpetas pueden revocar el acceso en cualquier momento mediante la eliminación del vínculo.

Los vínculos para cualquier usuario no se pueden usar con archivos en un sitio del canal compartido de Teams.

Para obtener información sobre cómo trabajar con el uso compartido anónimo de archivos y carpetas, consulte las siguientes referencias:

- [Administrar la configuración de uso compartido](/sharepoint/turn-external-sharing-on-or-off)
- [Prácticas recomendadas para compartir archivos y carpetas con usuarios no autenticados](/microsoft-365/solutions/best-practices-anonymous-sharing)

## <a name="related-topics"></a>Temas relacionados

[Introducción a la colaboración de archivos en Microsoft 365, con tecnología de SharePoint](/sharepoint/intro-to-file-collaboration)

[Colaboración de archivos en SharePoint con Microsoft 365](/sharepoint/deploy-file-collaboration)

[Uso del acceso de invitado y el acceso externo para colaborar con personas ajenas a la organización](/microsoftteams/communicate-with-users-from-other-organizations)

[Limitar el uso compartido de invitados a organizaciones específicas](/microsoft-365/solutions/limit-guest-sharing-to-specific-organization)

[Limitar las organizaciones en las que los usuarios pueden tener cuentas de invitado](/microsoft-365/solutions/limit-organizations-where-users-have-guest-accounts)