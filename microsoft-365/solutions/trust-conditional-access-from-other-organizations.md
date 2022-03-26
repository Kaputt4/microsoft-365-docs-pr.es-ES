---
title: Requerir acceso condicional para personas fuera de la organización
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
description: Obtenga información sobre cómo requerir que las personas fuera de su organización pasen comprobaciones de acceso condicional, como MFA y dispositivos compatibles.
ms.openlocfilehash: 181ee77e6b8a8d491294c9a5d3f8ec9202c9f9c1
ms.sourcegitcommit: 46456ca009c9d50622e57e24269be74986184654
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/22/2022
ms.locfileid: "63716094"
---
# <a name="require-conditional-access-for-people-outside-your-organization"></a>Requerir acceso condicional para personas fuera de la organización

Puede requerir cualquiera de las siguientes opciones de acceso condicional para personas fuera de la organización:

- Autenticación multifactor
- Dispositivos compatibles
- Dispositivos Azure AD híbridos unidos

Al usar Azure AD conexión directa B2B , como con canales compartidos en Teams, puede optar por confiar en la configuración de acceso condicional de otras organizaciones para estas opciones.

## <a name="planning-considerations-for-conditional-access"></a>Consideraciones de planeación para el acceso condicional

La autenticación multifactor se puede usar con cualquier cuenta externa. Si su organización no confía en la autenticación multifactor de otras organizaciones de Azure AD, los usuarios de dichas organizaciones tendrán que realizar la autenticación multifactor al acceder a los recursos de la organización. A las personas con direcciones de correo electrónico de terceros (no hospedadas por Microsoft) siempre se les pedirá autenticación multifactor.

Las opciones **Requerir que el dispositivo se marque** como  compatible y Requerir dispositivos Azure AD unidos requieren dispositivos que se administran en Azure AD. Si decide habilitar estas opciones, las personas de fuera de la organización deben usar dispositivos administrados por su organización o por una organización en la que confíe. Las personas sin dispositivos administrados se bloquearán, incluidos:

- Personas con direcciones de correo electrónico de terceros o consumidores
- Personas de Microsoft 365 organizaciones Azure AD que no administran dispositivos
- Personas de Microsoft 365 o Azure AD que requieren dispositivos administrados en los que su organización no confía en su configuración de acceso condicional.

Se recomienda tener cuidado al requerir dispositivos Azure AD compatibles o híbridos, ya que esto bloqueará muchos escenarios de colaboración externa. Asegúrese de que todas las organizaciones asociadas administran sus dispositivos y de que su organización confía en su configuración.

## <a name="set-up-conditional-access-requirements-for-people-outside-your-organization"></a>Configurar requisitos de acceso condicional para personas fuera de la organización

Para requerir acceso condicional para personas ajenas a su organización, haga lo siguiente:

1. [Elija la configuración de acceso condicional para confiar en otras organizaciones](#choose-conditional-access-settings-to-trust-from-other-organizations).
1. [Configurar el acceso condicional para personas fuera de la organización](#set-up-conditional-access-for-people-outside-your-organization).

## <a name="choose-conditional-access-settings-to-trust-from-other-organizations"></a>Elegir la configuración de acceso condicional para confiar en otras organizaciones

Puede elegir confiar en la configuración de acceso condicional de todas las demás organizaciones Microsoft 365 y Azure AD o solo de las que especifique.

> [!NOTE]
> Los cambios en la configuración de acceso entre inquilinos pueden tardar dos horas en tener efecto.

### <a name="trust-conditional-access-settings-from-all-azure-active-directory-organizations"></a>Confiar en la configuración de acceso condicional de todas Azure Active Directory organizaciones

Si desea confiar en la configuración de acceso condicional de todas las organizaciones, siga este procedimiento.

Para confiar en la configuración de acceso condicional de todas Azure Active Directory organizaciones
1. Inicie sesión en [Azure Active Directory](https://aad.portal.azure.com) con una cuenta de administrador global o de administrador de seguridad.
1. Seleccione **Identidades externas y**, a continuación, **seleccione Configuración de acceso entre inquilinos (versión preliminar).**.
1. Seleccione la **pestaña Configuración predeterminada** .
1. En **Configuración de acceso entrante**, seleccione **Editar valores predeterminados de entrada**.
1. Seleccione la **pestaña Configuración de confianza** .
1. Elige qué configuración quieres que acepten las directivas de acceso condicional de otras organizaciones.
1. Seleccione **Guardar** y cerrar la **hoja Configuración** predeterminada.

### <a name="trust-conditional-access-settings-from-a-specific-organization"></a>Confiar en la configuración de acceso condicional de una organización específica

Si desea confiar en la configuración de acceso condicional de una organización específica, siga este procedimiento.

Para confiar en la configuración de acceso condicional de una organización específica
1. Inicie sesión en [Azure Active Directory](https://aad.portal.azure.com) con una cuenta de administrador global o de administrador de seguridad.
1. Seleccione **Identidades externas y**, a continuación, **seleccione Configuración de acceso entre inquilinos (versión preliminar).**.
1. Seleccione la **configuración de acceso entrante** de la organización en la que desea confiar en la configuración de acceso condicional.
1. Seleccione la **pestaña Configuración de confianza** .
1. Seleccione la **opción Personalizar configuración** .
1. Elige qué configuración quieres que acepten las directivas de acceso condicional de otras organizaciones.
1. Seleccione **Guardar** y cerrar la **hoja Configuración** predeterminada.

## <a name="set-up-conditional-access-for-people-outside-your-organization"></a>Configurar el acceso condicional para personas fuera de la organización

La configuración de una directiva de acceso condicional para personas ajenas a su organización afecta a lo siguiente:

- Personas que usan cuentas de invitado (Azure AD usuarios de colaboración B2B)
- Participantes externos en Teams compartidos (Azure AD usuarios de conexión directa B2B)

> [!IMPORTANT]
> Solo selecciona el  dispositivo Requerir que se marque compatible o Requerir dispositivo unido Azure AD híbrido si todos los usuarios externos **a** la organización usan un dispositivo administrado por la organización o por una organización Microsoft 365 o Azure AD confianza.

Para configurar el acceso condicional para personas fuera de la organización
1. Vaya a [directivas de acceso condicional de Azure](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade).
1. En la hoja **Acceso condicional | Directivas**, seleccione **Nueva directiva**.
1. En el campo **Nombre**, escriba un nombre.
1. En **Asignaciones**, haga clic en **Usuarios y grupos**.
1. En la hoja **Usuarios y grupos**, seleccione **Seleccionar usuarios y grupos**, marque la casilla **Todos los invitados y usuarios externos**.
1. En **Tareas**, haga clic en **Aplicaciones o acciones en la nube**.
1. En la hoja **Aplicaciones o acciones en la nube**, seleccione **Todas las aplicaciones en la nube** en la pestaña **Incluir**.
1. En **Controles de acceso**, haga clic en **Conceder**.
1. En la **hoja Conceder** , seleccione las opciones que desea requerir para personas fuera de la organización y, a continuación, haga clic en **Seleccionar**.
1. En la hoja **Nuevo**, en **Habilitar directiva**, haga clic en **Activar** y, luego, haga clic **Crear**.

## <a name="related-topics"></a>Temas relacionados

[Tutorial: Exigir la autenticación multifactor para invitados B2B](/azure/active-directory/external-identities/b2b-tutorial-require-mfa)
