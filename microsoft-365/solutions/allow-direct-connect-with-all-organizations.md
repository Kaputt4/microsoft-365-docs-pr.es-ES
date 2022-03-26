---
title: Habilitar canales compartidos con todas las organizaciones externas
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- m365solution-securecollab
- m365solution-scenario
- m365initiative-externalcollab
ms.localizationpriority: medium
f1.keywords: NOCSH
recommendations: false
description: Obtenga información sobre cómo habilitar canales compartidos con todas Microsoft 365 y Azure Active Directory organizaciones.
ms.openlocfilehash: 601bfaa825afdaf9ec5addb4b7c7e21804b07cb7
ms.sourcegitcommit: 46456ca009c9d50622e57e24269be74986184654
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/22/2022
ms.locfileid: "63716100"
---
# <a name="enable-shared-channels-with-all-external-organizations"></a>Habilitar canales compartidos con todas las organizaciones externas

Aunque compartir canales compartidos externamente está habilitado de forma predeterminada en Teams, Azure Active Directory la configuración de acceso entre inquilinos para la conexión directa [B2B](/azure/active-directory/external-identities/b2b-direct-connect-overview) también debe configurarse para compartir un canal externamente. De forma predeterminada, esta configuración se establece para bloquear todas las organizaciones.

Puede cambiar la configuración predeterminada de conexión directa B2B para permitir a todas las organizaciones. Esto permite a los usuarios colaborar en canales compartidos sin que la organización tenga que crear una configuración independiente para cada organización con la que quiera colaborar. (Tenga en cuenta que las organizaciones con las que colabora también tendrán que configurar sus opciones de conexión directa B2B).

Si su organización no tiene un requisito para restringir la colaboración con otras organizaciones, habilitar todas las organizaciones de forma predeterminada puede ahorrarle tiempo y complejidad en la administración de cada organización por separado.

> [!NOTE]
> Los cambios en la configuración de acceso entre inquilinos pueden tardar dos horas en tener efecto.

## <a name="allow-users-to-invite-people-in-other-organizations-to-participate-in-shared-channels"></a>Permitir que los usuarios inviten a personas de otras organizaciones a participar en canales compartidos

Puede permitir que los usuarios inviten a personas de otras organizaciones a usar recursos compartidos (como canales compartidos en Teams) de forma predeterminada.

Para permitir que los usuarios inviten a participantes de conexión directa B2B de forma predeterminada
1. Inicie sesión en [Azure Active Directory](https://aad.portal.azure.com) con una cuenta de administrador global o de administrador de seguridad.
1. Seleccione **Identidades externas y**, a continuación, **seleccione Configuración de acceso entre inquilinos (versión preliminar).**.
1. En la **pestaña Configuración predeterminada** , en **Configuración de acceso entrante**, seleccione **Editar valores predeterminados de entrada**.
1. Seleccione la **pestaña Conexión directa B2B** .
1. En la **pestaña Usuarios y grupos** , en **Estado de Access**, elija **Permitir acceso**.
1. En la **pestaña Aplicaciones externas** , en **Estado de Access**, elija **Permitir acceso**.
1. Seleccione **Guardar**.
1. Seleccione la **pestaña Configuración de confianza** .
1. Elige si quieres confiar en la autenticación multifactor, dispositivos compatibles o dispositivos híbridos Azure AD dispositivos unidos de otras organizaciones.
1. Seleccione **Guardar**.
1. Cierre la **hoja Configuración predeterminada** .

## <a name="allow-users-to-participate-in-shared-channels-in-other-organizations"></a>Permitir a los usuarios participar en canales compartidos en otras organizaciones

Puede permitir que los usuarios obtengan acceso a los recursos hospedados por una organización externa ( como canales compartidos en Teams ) de forma predeterminada.

Para permitir que los usuarios accedan a recursos de otras organizaciones de forma predeterminada
1. En [Azure Active Directory](https://aad.portal.azure.com), seleccione **Identidades externas y**, a continuación, seleccione **Configuración de acceso entre inquilinos (versión preliminar).**
1. En la **pestaña Configuración predeterminada** , en **Configuración de acceso saliente**, seleccione **Editar valores predeterminados de salida**.
1. Seleccione la **pestaña Conexión directa B2B** .
1. En la **pestaña Usuarios y grupos** , en **Estado de Access**, elija **Permitir acceso**.
1. En la **pestaña Aplicaciones externas** , en **Estado de Access**, elija **Permitir acceso**.
1. Seleccione **Guardar**.
1. Cierre la **hoja Configuración predeterminada** .

## <a name="related-topics"></a>Temas relacionados

[Introducción a la conexión directa B2B](/azure/active-directory/external-identities/b2b-direct-connect-overview)

[Configurar las opciones de acceso entre inquilinos para la conexión directa B2B](/azure/active-directory/external-identities/cross-tenant-access-settings-b2b-direct-connect)

