---
title: Colaborar con participantes externos en un canal compartido
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- m365solution-3tiersprotection
- m365solution-securecollab
- m365initiative-externalcollab
ms.custom: ''
localization_priority: Priority
f1.keywords: NOCSH
recommendations: false
description: Obtenga información sobre cómo habilitar canales compartidos en Microsoft Teams para la colaboración con personas ajenas a su organización.
ms.openlocfilehash: c45d345a38b1ba9d045d6984feda614513512021
ms.sourcegitcommit: 4cd8be7c22d29100478dce225dce3bcdce52644d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/10/2022
ms.locfileid: "65302155"
---
# <a name="collaborate-with-external-participants-in-a-shared-channel"></a>Colaborar con participantes externos en un canal compartido

Si desea permitir que los usuarios colaboren con personas ajenas a la organización en [canales compartidos](/MicrosoftTeams/shared-channels), debe configurar la conexión directa B2B para cada organización con la que quiera colaborar. (Como alternativa, puede [Habilitar canales compartidos con todas las organizaciones externas](/microsoft-365/solutions/allow-direct-connect-with-all-organizations)).

Al habilitar canales compartidos en Teams con otra organización:

- Los propietarios de equipos de su organización podrán invitar a personas de otras organizaciones a participar en canales compartidos.
- Las aplicaciones personalizadas (línea de negocio) de su organización estarán disponibles en los canales compartidos y los participantes externos podrán acceder a ellas.
- La lista de aplicaciones de su organización estará disponible en los canales compartidos y los participantes externos podrán acceder a ellas.

> [!NOTE]
> Los canales compartidos están en versión preliminar y requieren que haya configurado [Versión preliminar pública de Microsoft Teams](/MicrosoftTeams/public-preview-doc-updates). Si planea compartir canales con otras organizaciones, también deben haber configurado la versión preliminar pública de Teams.

## <a name="video-demonstration"></a>Demostración de vídeo

En este vídeo se muestran los pasos de configuración descritos en este documento.
<br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4WRMx?autoplay=false]

## <a name="enable-shared-channels-in-teams"></a>Habilitar canales compartidos en Teams

Los canales compartidos están habilitados de forma predeterminada en Teams. Siga este procedimiento para confirmar la configuración.

Para configurar canales compartidos
1. En el [Center de administración de Teams](https://admin.teams.microsoft.com/), expanda **Equipos** y, a continuación, seleccione **Administrador de Teams**.
1. Seleccione la directiva para la que desea habilitar los canales compartidos y, a continuación, seleccione **Editar**.
1. Seleccione las opciones que desea habilitar:
    - Para permitir que los propietarios del equipo creen canales compartidos, active **Crear canales compartidos**.
    - Para permitir que los propietarios del equipo compartan canales compartidos con personas ajenas a la organización, active **Invitar a usuarios externos a canales compartidos**.
    - Para permitir que se invite a usuarios a canales compartidos de otras organizaciones, active **Unirse a canales compartidos externos**.
1. Seleccione **Aplicar**.

Para que los participantes del canal externo participen en reuniones, se debe habilitar el acceso externo. Esto también es necesario para poder ver la presencia de los participantes externos en el canal.

Para habilitar el acceso externo
1. En el [centro de administración de Teams](https://admin.teams.microsoft.com/), expanda **Usuarios** y, a continuación, seleccione **Acceso externo**.
1. En **Usuarios de Teams y Skype Empresarial en organizaciones externas**, asegúrese de que las organizaciones con las que desea colaborar no estén bloqueadas.

## <a name="configure-cross-tenant-access-settings-in-azure-ad"></a>Configurar el acceso entre inquilinos en Azure AD

La conexión directa B2B de Azure AD está deshabilitada de forma predeterminada. Para habilitar la colaboración en canales compartidos con personas de otras organizaciones, debe:

1. [Agregar una organización](#add-an-organization).
1. [Configurar la configuración de entrada](#configure-inbound-settings) para que la organización permita invitar a los usuarios de la organización a los canales compartidos.
1. [Configurar la configuración de salida](#configure-outbound-settings) para que la organización permita invitar a los usuarios a los canales compartidos de otra organización.

Como parte de esta configuración, habilitamos la aplicación **Office 365**, que incluye Teams y servicios integrados en Teams, como SharePoint.

> [!NOTE]
> Los cambios en la configuración de acceso entre inquilinos pueden tardar dos horas en surtir efecto.

### <a name="add-an-organization"></a>Agregar una organización

Agregue cada organización con la que quiera participar en canales compartidos.

Para agregar una organización
1. Inicie sesión en [Azure Active Directory](https://aad.portal.azure.com) con una cuenta de administrador global o administrador de seguridad.
1. Seleccione **Identidades externas** y, a continuación, seleccione **Configuración de acceso entre inquilinos (versión preliminar)**.
1. Seleccione **Configuración de la organización**.
1. Seleccione **Agregar organización**.
1. En el panel **Agregar organización**, escriba el nombre de dominio completo (o id. de inquilino) de la organización y presione Entrar.
1. Seleccione **Agregar**.
1. La organización aparece en la lista de organizaciones. En este momento, toda la configuración de acceso de esta organización se hereda de la configuración predeterminada.

### <a name="configure-inbound-settings"></a>Configurar opciones de entrada

Siga este procedimiento para cada organización en la que quiera invitar a participantes externos.

Para configurar las opciones de entrada de una organización
1. En [Azure Active Directory](https://aad.portal.azure.com), seleccione **Identidades externas** y, a continuación, seleccione **Configuración de acceso entre inquilinos (versión preliminar)**.
1. Seleccione el vínculo de acceso de entrada para la organización que desea modificar.
1. En la pestaña **Conexión directa B2B**, elija **Personalizar configuración**.
1. En la pestaña **Usuarios y grupos externos**, elija **Permitir acceso** y **Todos los usuarios y grupos externos**. (Puede elegir **Seleccionar usuarios y grupos externos** si desea limitar el acceso a usuarios y grupos específicos, por ejemplo, los que hayan firmado un acuerdo de confidencialidad).
1. En la pestaña **Aplicaciones**, elija **Permitir acceso** y **Seleccionar aplicaciones**.
1. Seleccione **Agregar aplicaciones de Microsoft**.
1. Seleccione la aplicación **Office 365** y, a continuación, elija **Seleccionar**.
1. Seleccione **Guardar** y cierre la hoja **Configuración de acceso de entrada**.

### <a name="configure-outbound-settings"></a>Configurar opciones de salida

Siga este procedimiento para cada organización en la que quiera que los usuarios puedan participar en canales compartidos externos.

Para configurar las opciones de salida de una organización
1. En [Azure Active Directory](https://aad.portal.azure.com), seleccione **Identidades externas** y, a continuación, seleccione **Configuración de acceso entre inquilinos (versión preliminar)**.
1. Seleccione el vínculo de acceso de salida de la organización que desea modificar.
1. En la pestaña **Conexión directa B2B**, elija **Personalizar configuración**.
1. En la pestaña **Usuarios y grupos externos**, elija **Permitir acceso** y establezca un **Aplicabl a** de todos los usuarios.
1. En la pestaña **Aplicaciones externas**, elija **Permitir acceso** y **Seleccionar aplicaciones externas**.
1. Seleccione **Agregar aplicaciones de Microsoft**.
1. Seleccione la aplicación **Office 365** y, a continuación, elija **Seleccionar**.
1. Seleccione **Guardar**, elija **Sí** para confirmar y cierre la hoja **Configuración de acceso de salida**.

## <a name="see-also"></a>Vea también

[Información general sobre la conexión directa B2B](/azure/active-directory/external-identities/b2b-direct-connect-overview)

[Configurar la configuración de acceso entre inquilinos para la conexión directa B2B](/azure/active-directory/external-identities/cross-tenant-access-settings-b2b-direct-connect)

[Limitar a quién puede invitar una organización](limit-invitations-from-specific-organization.md)

[Límites de canales compartidos](/MicrosoftTeams/shared-channels#shared-channel-limits)
