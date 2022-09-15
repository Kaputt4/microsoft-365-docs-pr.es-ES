---
title: Requerir acceso condicional para personas ajenas a la organización
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.service: microsoft-365-enterprise
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
description: Obtenga información sobre cómo requerir que personas ajenas a su organización pasen comprobaciones de acceso condicional, como MFA y dispositivos compatibles.
ms.openlocfilehash: 9e424ef6dde16137a334f391efa71b6b61860dfb
ms.sourcegitcommit: 0af064e8b6778060f1bd365378d69b16fc9949b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2022
ms.locfileid: "67731450"
---
# <a name="require-conditional-access-for-people-outside-your-organization"></a>Requerir acceso condicional para personas ajenas a la organización

Puede requerir cualquiera de las siguientes opciones de acceso condicional para personas ajenas a la organización:

- Autenticación multifactor
- Dispositivos compatibles
- Dispositivos unidos a Azure AD híbrido

Al usar la conexión directa B2B de Azure AD, como con canales compartidos en Teams, puede optar por confiar en la configuración de acceso condicional de otras organizaciones para estas opciones. Tenga en cuenta que las directivas de acceso condicional solo se usan para acceder a la pestaña Archivos del canal compartido y al sitio de SharePoint asociado.

## <a name="planning-considerations-for-conditional-access"></a>Consideraciones de planeación para el acceso condicional

La autenticación multifactor se puede usar con cualquier cuenta externa. Si su organización no confía en la autenticación multifactor de otras organizaciones de Azure AD, los usuarios de esas organizaciones tendrán que realizar la autenticación multifactor al acceder a los recursos de la organización. Personas con direcciones de correo electrónico de terceros (no hospedadas por Microsoft) siempre se le pedirá autenticación multifactor.

Las opciones Requerir que el **dispositivo se marque como compatible** y **Requerir dispositivo unido a Azure AD híbrido** requieren dispositivos administrados en Azure AD. Si decide habilitar estas opciones, las personas ajenas a su organización deben usar dispositivos administrados por su organización o por una organización en la que confíe. Personas sin dispositivos administrados se bloquearán, lo que incluye:

- Personas con direcciones de correo electrónico de terceros o consumidores
- Personas de organizaciones de Microsoft 365 o Azure AD que no administran dispositivos
- Personas de organizaciones de Microsoft 365 o Azure AD que requieren dispositivos administrados en los que su organización no confía en su configuración de acceso condicional.

Se recomienda tener cuidado al requerir dispositivos compatibles o unidos a Azure AD híbridos, ya que esto bloqueará muchos escenarios de colaboración externa. Asegúrese de que todas las organizaciones asociadas administran sus dispositivos y de que su organización confía en su configuración.

## <a name="set-up-conditional-access-requirements-for-people-outside-your-organization"></a>Configuración de requisitos de acceso condicional para personas ajenas a la organización

Para requerir acceso condicional para personas ajenas a la organización, haga lo siguiente:

1. [Elija la configuración de acceso condicional para confiar en otras organizaciones](#choose-conditional-access-settings-to-trust-from-other-organizations).
1. [Configure el acceso condicional para personas ajenas a la organización](#set-up-conditional-access-for-people-outside-your-organization).

## <a name="choose-conditional-access-settings-to-trust-from-other-organizations"></a>Elección de la configuración de acceso condicional para confiar en otras organizaciones

Puede optar por confiar en la configuración de acceso condicional de todas las demás organizaciones de Microsoft 365 y Azure AD o solo de las que especifique.

> [!NOTE]
> Los cambios en la configuración de acceso entre inquilinos pueden tardar dos horas en surtir efecto.

### <a name="trust-conditional-access-settings-from-all-azure-active-directory-organizations"></a>Confiar en la configuración de acceso condicional de todas las organizaciones de Azure Active Directory

Si desea confiar en la configuración de acceso condicional de todas las organizaciones, siga este procedimiento.

Para confiar en la configuración de acceso condicional de todas las organizaciones de Azure Active Directory
1. Inicie sesión en [Azure Active Directory](https://aad.portal.azure.com) con una cuenta de administrador global o administrador de seguridad.
1. Seleccione **Identidades externas** y, a continuación, seleccione **Configuración de acceso entre inquilinos (versión preliminar)**.
1. Seleccione la pestaña **Configuración predeterminada** .
1. En **Configuración de acceso de entrada**, seleccione **Editar valores predeterminados de entrada**.
1. Seleccione la pestaña **Configuración de confianza** .
1. Elija qué configuración quiere que acepten las directivas de acceso condicional de otras organizaciones.
1. Seleccione **Guardar** y cierre la hoja **Configuración predeterminada** .

### <a name="trust-conditional-access-settings-from-a-specific-organization"></a>Confiar en la configuración de acceso condicional de una organización específica

Si desea confiar en la configuración de acceso condicional de una organización específica, siga este procedimiento.

Para confiar en la configuración de acceso condicional de una organización específica
1. Inicie sesión en [Azure Active Directory](https://aad.portal.azure.com) con una cuenta de administrador global o administrador de seguridad.
1. Seleccione **Identidades externas** y, a continuación, seleccione **Configuración de acceso entre inquilinos (versión preliminar)**.
1. Seleccione la configuración **de acceso de entrada** de la organización en la que desea confiar en la configuración de acceso condicional.
1. Seleccione la pestaña **Configuración de confianza** .
1. Seleccione la opción **Personalizar configuración** .
1. Elija qué configuración quiere que acepten las directivas de acceso condicional de otras organizaciones.
1. Seleccione **Guardar** y cierre la hoja **Configuración predeterminada** .

## <a name="set-up-conditional-access-for-people-outside-your-organization"></a>Configuración del acceso condicional para personas ajenas a la organización

La configuración de una directiva de acceso condicional para personas ajenas a la organización afecta a lo siguiente:

- Personas con cuentas de invitado (usuarios de colaboración B2B de Azure AD)
- Participantes externos en canales compartidos de Teams (usuarios de conexión directa de Azure AD B2B)

> [!IMPORTANT]
> Solo seleccione Requerir que el **dispositivo esté marcado como compatible** o **Requerir dispositivo unido a Azure AD híbrido** si todos los usuarios de fuera de la organización usan un dispositivo administrado por su organización o por una organización de Confianza de Microsoft 365 o Azure AD.

Para configurar el acceso condicional para personas ajenas a la organización
1. Vaya a [directivas de acceso condicional de Azure](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade).
1. En la hoja **Acceso condicional | Directivas**, seleccione **Nueva directiva**.
1. En el campo **Nombre**, escriba un nombre.
1. En **Asignaciones**, haga clic en **Usuarios y grupos**.
1. En la hoja **Usuarios y grupos**, seleccione **Seleccionar usuarios y grupos**, marque la casilla **Todos los invitados y usuarios externos**.
1. En **Tareas**, haga clic en **Aplicaciones o acciones en la nube**.
1. En la hoja **Aplicaciones o acciones en la nube**, seleccione **Todas las aplicaciones en la nube** en la pestaña **Incluir**.
1. En **Controles de acceso**, haga clic en **Conceder**.
1. En la hoja **Conceder** , seleccione las opciones que desea requerir para las personas de fuera de la organización y, a continuación, haga clic en **Seleccionar**.
1. En la hoja **Nuevo**, en **Habilitar directiva**, haga clic en **Activar** y, luego, haga clic **Crear**.

## <a name="related-topics"></a>Temas relacionados

[Tutorial: Aplicación de la autenticación multifactor para invitados B2B](/azure/active-directory/external-identities/b2b-tutorial-require-mfa)
