---
title: Paso 1. Aumentar la seguridad de inicio de sesión para trabajadores remotos con MFA
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 05/01/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
ms.custom:
- M365solutions
description: Requerir que los trabajadores remotos inicien sesión con autenticación multifactor (MFA).
ms.openlocfilehash: f8154f35baaf693bb51c523cfe4c44374437de02
ms.sourcegitcommit: 101084f9c81616342d78493232d8f13f5ffa4ddf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/01/2020
ms.locfileid: "44003584"
---
# <a name="step-1-increase-sign-in-security-for-remote-workers-with-mfa"></a>Paso 1. Aumentar la seguridad de inicio de sesión para trabajadores remotos con MFA

Para aumentar la seguridad de los inicios de sesión de los trabajadores remotos, use la autenticación multifactor (MFA). MFA requiere que los inicios de sesión de usuario estén sujetos a una comprobación adicional más allá de la contraseña de la cuenta de usuario. Incluso si un usuario malintencionado determina la contraseña de una cuenta de usuario, también debe poder responder a una comprobación adicional, como un mensaje de texto que se envía a un smartphone, antes de que se otorgue el acceso.

Microsoft recomienda MFA para todos los trabajadores remotos, especialmente los administradores.

Existen tres formas de requerir que los usuarios usen MFA basándose en su plan de Microsoft 365.

|Plan  |Recomendación  |
|---------|---------|
|Planes de Microsoft 365 (sin Azure AD Premium P1 o P2)     |[Habilitar los valores predeterminados de seguridad en Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults). Los valores predeterminados de seguridad en Azure AD incluyen MFA para los usuarios y administradores.   |
|Microsoft 365 E3 (con Azure AD Premium P1)     | Use [Directivas comunes de acceso condicional](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common) para configurar las directivas siguientes: <br>- [Requerir MFA para los administradores](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa) <br>- [Requerir MFA para todos los usuarios](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa) <br> - [Bloquear la autenticación heredada](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)       |
|Microsoft 365 E5 (con Azure AD Premium P2)     | Aprovechando la protección de identidades de Azure AD Identity Protection, empiece a implementar el [conjunto recomendado de directivas de acceso condicional y relacionadas](../enterprise/identity-access-policies.md) de Microsoft creando estas dos directivas:<br> - [Exigir la autenticación multifactor (MFA) cuando el riesgo de inicio de sesión es medio o alto](../enterprise/identity-access-policies.md#require-mfa-based-on-sign-in-risk) <br>- [Bloquear a los clientes que no sean compatibles con la autenticación moderna](../enterprise/identity-access-policies.md#block-clients-that-dont-support-modern-authentication)<br>- [Los usuarios de riesgo alto tienen que cambiar la contraseña](../enterprise/identity-access-policies.md#high-risk-users-must-change-password)       |
| | |

## <a name="security-defaults"></a>Valores predeterminados de seguridad

Los valores predeterminados de seguridad son una nueva característica para las suscripciones pago o de prueba de Microsoft 365 y Office 365 creadas después del 21 de octubre de 2019. Estas suscripciones tienen los valores predeterminados de seguridad activados, lo que ***obliga a que todos los usuarios usen MFA con la aplicación Microsoft Authenticator***.
 
Los usuarios tienen 14 días para registrarse en MFA con la aplicación Microsoft Authenticator desde sus teléfonos inteligentes, que comienzan a contar desde la primera vez que inician sesión después de que se hayan habilitado los valores predeterminados de seguridad. Transcurridos 14 días, el usuario no podrá iniciar sesión hasta que el registro de MFA se haya completado.

Los valores predeterminados de seguridad garantizan que todas las organizaciones tengan un nivel básico de seguridad para el inicio de sesión de usuario habilitado de forma predeterminada. Puede deshabilitar los valores predeterminados de seguridad y usar MFA con directivas de acceso condicional o para cuentas individuales.

Para más información, vea esta [información general de los valores predeterminados de seguridad](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).

## <a name="conditional-access-policies"></a>Directivas de acceso condicional

Las directivas de acceso condicional son un conjunto de reglas que especifican las condiciones en las que se evalúan y permiten los inicios de sesión. Por ejemplo, puede crear una directiva de acceso condicional que indique lo siguiente:

- Si el nombre de la cuenta de usuario es para un usuario que es un administrador de Exchange, usuarios, contraseñas, seguridad, SharePoint o global, se requiere MFA antes de permitir el acceso.

Esta directiva es más fácil que intentar recordar configurar cuentas de usuario individuales para MFA cuando se agregan o eliminan de estas funciones de administrador.

También puede usar directivas de acceso condicionales para funciones más avanzadas, como requerir que el inicio de sesión se realice desde un dispositivo que cumpla las normativas, como su equipo portátil que ejecuta Windows 10.

El acceso condicional requiere Azure AD Premium P1, que se incluye con Microsoft 365 E3 y E5.

Para más información, vea esta [información general sobre el acceso condicional](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).

## <a name="azure-ad-identity-protection-policies"></a>Directivas de protección de identidad de Azure AD Identity Protection

Las directivas de protección de identidad de Azure AD Identity Protection son reglas que especifican las condiciones bajo las cuales se evalúan y permiten los inicios de sesión. Por ejemplo, puede crear una directiva de protección de identidad de Azure AD Identity Protection que establezca:

- Si el riesgo del inicio de sesión se determina como medio o alto, el usuario debe usar MFA para iniciar sesión.

La protección de identidad de Azure AD Identity Protection requiere Azure AD Premium P2, que se incluye con Microsoft 365 E5.

Para más información, vea esta [información general sobre la protección de identidad de Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection).

## <a name="using-these-methods-together"></a>Usar estos métodos conjuntamente

Tenga en cuenta lo siguiente:

- No puede habilitar los valores predeterminados de seguridad si tiene habilitadas directivas de acceso condicional.
- No puede habilitar ninguna directiva de acceso condicional si tiene habilitados los valores predeterminados de seguridad.

Si los valores predeterminados de seguridad están habilitados, se le pedirá al usuario el registro de MFA y el uso de la aplicación Microsoft Authenticator. 

Esta tabla muestra los resultados de habilitar MFA con los valores predeterminados de seguridad, las directivas de acceso condicional y la configuración de cuenta por usuario.

|| Habilitado | Deshabilitado | Método de autenticación secundario |
|:-------|:-----|:-------|:-------|
| **Valores predeterminados de seguridad**  | No se pueden usar directivas de acceso condicional | Se pueden usar directivas de acceso condicional | Aplicación Microsoft Authenticator |
| **Directivas de acceso condicional** | Si hay alguna habilitada, no puede habilitar los valores predeterminados de seguridad | Si no hay ninguna habilitada, puede habilitar los valores predeterminados de seguridad  | Especificado por el usuario durante el registro de MFA  |
||||

## <a name="admin-training-and-technical-resources-for-mfa-and-identity"></a>Aprendizaje de administración y recursos técnicos para MFA e identidad

- [Planificación de MFA para Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/multi-factor-authentication-plan)
- [Las 5 mejores formas en que Azure AD puede ayudarle a habilitar el trabajo remoto](https://techcommunity.microsoft.com/t5/azure-active-directory-identity/top-5-ways-your-azure-ad-can-help-you-enable-remote-work/ba-p/1144691)
- [Planear e implementar la infraestructura de identidades de Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/identity-infrastructure?view=o365-worldwide#plan-and-deploy-your-microsoft-365-enterprise-identity-infrastructure)
- [Vídeos de aprendizaje de Azure Academy Azure AD](https://www.youtube.com/watch?v=pN8o0owHfI0&list=PL-V4YVm6AmwUFpC3rXr2i2piRQ708q_ia)
- [Configurar la directiva de registro de autenticación multi-factor de Azure](https://docs.microsoft.com/azure/active-directory/identity-protection/howto-identity-protection-configure-mfa-policy)

## <a name="results-of-step-1"></a>Resultado del paso 1

Después de la implementación de MFA, los usuarios:

- Están obligados a usar MFA para iniciar sesión.
- Han completado el proceso de registro de MFA y usan MFA para todos los inicios de sesión.

## <a name="next-step"></a>Paso siguiente

Continúe con el [paso 2](empower-people-to-work-remotely-remote-access.md) para proporcionar acceso remoto a servicios y aplicaciones locales.
