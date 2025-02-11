---
title: Habilitar canales compartidos con todas las organizaciones externas
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.collection:
- highpri
- SPO_Content
- M365-collaboration
- m365solution-securecollab
- m365solution-scenario
- m365initiative-externalcollab
ms.localizationpriority: medium
f1.keywords: NOCSH
recommendations: false
description: Aprenda a habilitar canales compartidos con todas las demás organizaciones de Microsoft 365 y Azure Active Directory.
ms.openlocfilehash: 36184a9ab743ee1aac2cc76e5b61fc83752ee163
ms.sourcegitcommit: fce27da5140691b013a6f7c0ea9c88b4ea4b7c10
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2022
ms.locfileid: "67985770"
---
# <a name="enable-shared-channels-with-all-external-organizations"></a>Habilitar canales compartidos con todas las organizaciones externas

Aunque el uso compartido de canales compartidos está habilitado externamente de forma predeterminada en Teams, la configuración de acceso entre inquilinos de Azure Active Directory para [la conexión directa B2B](/azure/active-directory/external-identities/b2b-direct-connect-overview) también debe configurarse para compartir un canal externamente. De forma predeterminada, esta configuración se establece para bloquear todas las organizaciones.

Puede cambiar la configuración predeterminada de conexión directa B2B para permitir todas las organizaciones. Esto permite a los usuarios colaborar en canales compartidos sin que su organización tenga que crear una configuración independiente para cada organización con la que quiera colaborar. (Tenga en cuenta que las organizaciones con las que colabora también tendrán que configurar sus opciones de conexión directa B2B).

Si su organización no tiene un requisito para restringir la colaboración con otras organizaciones, habilitar todas las organizaciones de forma predeterminada puede ahorrarle tiempo y complejidad en la administración de cada organización por separado.

> [!NOTE]
> Los cambios en la configuración de acceso entre inquilinos pueden tardar dos horas en surtir efecto.

> [!NOTE]
> [La configuración de invitado de Grupos de Microsoft 365](/microsoft-365/admin/create-groups/manage-guest-access-in-groups) debe estar habilitada para usar canales compartidos con participantes externos.

## <a name="allow-users-to-invite-people-in-other-organizations-to-participate-in-shared-channels"></a>Permitir a los usuarios invitar a personas de otras organizaciones a participar en canales compartidos

Puede permitir que los usuarios inviten a personas de otras organizaciones a usar recursos compartidos (como canales compartidos en Teams) de forma predeterminada.

Para permitir a los usuarios invitar a participantes de conexión directa B2B de forma predeterminada
1. Inicie sesión en [Azure Active Directory](https://aad.portal.azure.com) con una cuenta de administrador global o administrador de seguridad.
1. Seleccione **Identidades externas** y, a continuación, seleccione **Configuración de acceso entre inquilinos (versión preliminar)**.
1. En la pestaña **Configuración predeterminada** , en **Configuración de acceso de entrada**, seleccione **Editar valores predeterminados de entrada**.
1. Seleccione la pestaña **Conexión directa B2B** .
1. En la pestaña **Usuarios y grupos** , en **Estado de acceso**, elija **Permitir acceso**.
1. En la pestaña **Aplicaciones externas** , en **Estado de acceso**, elija **Permitir acceso**.
1. Seleccione **Guardar**.
1. Seleccione la pestaña **Configuración de confianza** .
1. Elija si desea confiar en la autenticación multifactor, los dispositivos compatibles o los dispositivos unidos a Azure AD híbrido de otras organizaciones.
1. Seleccione **Guardar**.
1. Cierre la hoja **Configuración predeterminada** .

## <a name="allow-users-to-participate-in-shared-channels-in-other-organizations"></a>Permitir que los usuarios participen en canales compartidos en otras organizaciones

Puede permitir que los usuarios accedan a los recursos hospedados por una organización externa (como canales compartidos en Teams) de forma predeterminada.

Para permitir que los usuarios accedan al recurso desde otras organizaciones de forma predeterminada
1. En [Azure Active Directory](https://aad.portal.azure.com), seleccione **Identidades externas** y, a continuación, seleccione **Configuración de acceso entre inquilinos (versión preliminar)**.
1. En la pestaña **Configuración predeterminada** , en **Configuración de acceso saliente**, seleccione **Editar valores predeterminados de salida**.
1. Seleccione la pestaña **Conexión directa B2B** .
1. En la pestaña **Usuarios y grupos** , en **Estado de acceso**, elija **Permitir acceso**.
1. En la pestaña **Aplicaciones externas** , en **Estado de acceso**, elija **Permitir acceso**.
1. Seleccione **Guardar**.
1. Cierre la hoja **Configuración predeterminada** .

## <a name="related-topics"></a>Temas relacionados

[Información general sobre la conexión directa B2B](/azure/active-directory/external-identities/b2b-direct-connect-overview)

[Configurar la configuración de acceso entre inquilinos para la conexión directa B2B](/azure/active-directory/external-identities/cross-tenant-access-settings-b2b-direct-connect)

