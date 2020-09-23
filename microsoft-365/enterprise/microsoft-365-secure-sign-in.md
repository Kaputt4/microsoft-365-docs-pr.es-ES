---
title: Asegurar inicios de sesión de usuario en el espacio empresarial de Microsoft 365
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 09/16/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Requerir que los usuarios inicien sesión de forma segura con la autenticación multifactor (MFA) y otras características.
ms.openlocfilehash: 6c8f58e54ae21b4a5e1566dc72673e1d69152863
ms.sourcegitcommit: fdb5f9d865037c0ae23aae34a5c0f06b625b2f69
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2020
ms.locfileid: "48132250"
---
# <a name="secure-user-sign-ins-to-your-microsoft-365-tenant"></a>Asegurar inicios de sesión de usuario en el espacio empresarial de Microsoft 365

Para aumentar la seguridad de los inicios de sesión de los usuarios:

- Use la protección de contraseñas de Azure Active Directory
- Use la autenticación multifactor (MFA)
- Implemente las directivas comunes de acceso a dispositivos e identidades

## <a name="azure-ad-password-protection"></a>Protección de contraseñas de Azure AD

La protección de contraseñas de Azure AD detecta y bloquea las contraseñas que son conocidas por ser vulnerables y sus variantes. Además, también puede bloquear los términos vulnerables adicionales que sean específicos de su organización. Las listas de contraseñas desvetadas global predeterminada se aplican automáticamente a todos los usuarios de un inquilino de Azure AD. Se puede definir entradas adicionales en una lista personalizada de contraseñas prohibidas. Cuando los usuarios cambien o restablezcan sus contraseñas, estas listas de contraseñas prohibidas se comprueban para exigir el uso de contraseñas seguras.

Para obtener más información, consulte [Configurar la protección de contraseñas de Azure AD](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad).

## <a name="mfa"></a>MFA

MFA requiere que los inicios de sesión de usuario estén sujetos a una comprobación adicional más allá de la contraseña de la cuenta de usuario. Incluso si un usuario malintencionado determina la contraseña de una cuenta de usuario, también debe poder responder a una comprobación adicional, como un mensaje de texto que se envía a un smartphone, antes de que se otorgue el acceso.

![La contraseña correcta más una comprobación adicional produce un inicio de sesión correcto](../media/empower-people-to-work-remotely/remote-workers-mfa.png)

El primer paso en el uso de MFA es que sea ***necesario para todas las cuentas de administrador***, también conocidas como cuentas con privilegios.

Después de este primer paso, Microsoft recomienda de manera enfática el uso de MFA para todos los usuarios.

Existen tres maneras para requerir que los administradores o usuarios usen MFA basándose en su plan de Microsoft 365.

| Plan | Recomendación |
|---------|---------|
|Todos los planes de Microsoft 365 (sin licencias de Azure AD Premium P1 o P2)     |[Habilitar los valores predeterminados de seguridad en Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults). Los valores predeterminados de seguridad en Azure AD incluyen MFA para los usuarios y administradores.   |
|Microsoft 365 E3 (incluye las licencias de Azure AD Premium P1)     | Use [Directivas comunes de acceso condicional](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common) para configurar las directivas siguientes: <br>- [Requerir MFA para los administradores](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa) <br>- [Requerir MFA para todos los usuarios](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa) <br> - [Bloquear la autenticación heredada](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)       |
|Microsoft 365 E5 (incluye las licencias de Azure AD Premium P2)     | Aprovechando la protección de identidades de Azure AD Identity Protection, empiece a implementar el [conjunto recomendado de directivas de acceso condicional y relacionadas](../enterprise/identity-access-policies.md) de Microsoft creando estas dos directivas:<br> - [Exigir la autenticación multifactor (MFA) cuando el riesgo de inicio de sesión es medio o alto](../enterprise/identity-access-policies.md#require-mfa-based-on-sign-in-risk) <br>- [Los usuarios de riesgo alto tienen que cambiar la contraseña](../enterprise/identity-access-policies.md#high-risk-users-must-change-password)       |
| | |

### <a name="security-defaults"></a>Valores predeterminados de seguridad

Los valores predeterminados de seguridad son una nueva característica para las suscripciones pago o de prueba de Microsoft 365 y Office 365 creadas después del 21 de octubre de 2019. Estas suscripciones tienen los valores predeterminados de seguridad activados, lo que ***obliga a que todos los usuarios usen MFA con la aplicación Microsoft Authenticator***.
 
Los usuarios tienen 14 días para registrarse en MFA con la aplicación Microsoft Authenticator desde sus teléfonos inteligentes, que comienzan a contar desde la primera vez que inician sesión después de que se hayan habilitado los valores predeterminados de seguridad. Transcurridos 14 días, el usuario no podrá iniciar sesión hasta que el registro de MFA se haya completado.

Los valores predeterminados de seguridad garantizan que todas las organizaciones tengan un nivel básico de seguridad para el inicio de sesión de usuario habilitado de forma predeterminada. Puede deshabilitar los valores predeterminados de seguridad y usar MFA con directivas de acceso condicional o para cuentas individuales.

Para más información, vea esta [información general de los valores predeterminados de seguridad](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).

### <a name="conditional-access-policies"></a>Directivas de acceso condicional

Las directivas de acceso condicional son un conjunto de reglas que especifican las condiciones en las que se evalúan y se conceden los accesos. Por ejemplo, puede crear una directiva de acceso condicional que indique lo siguiente:

- Si el nombre de la cuenta de usuario es miembro de un grupo de usuarios a los que se han asignado los roles de administrador de Exchange, de usuarios, de contraseñas, de seguridad, de SharePoint o global, requerir MFA antes de permitir el acceso.

Esta directiva le permite exigir MFA en función de la pertenencia a grupos, en lugar de intentar configurar cuentas de usuario individuales para MFA cuando se asignan o se quitan estos roles de administrador.

También puede usar directivas de acceso condicionales para funciones más avanzadas, como requerir que el inicio de sesión se realice desde un dispositivo que cumpla las normativas, como su equipo portátil que ejecuta Windows 10.

El acceso condicional requiere licencias de Azure AD Premium P1, que se incluyen con Microsoft 365 E3 y E5.

Para más información, vea la [información general sobre el acceso condicional](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).

### <a name="using-these-methods-together"></a>Usar estos métodos conjuntamente

Tenga en cuenta lo siguiente:

- No puede habilitar los valores predeterminados de seguridad si tiene habilitadas directivas de acceso condicional.
- No puede habilitar ninguna directiva de acceso condicional si tiene habilitados los valores predeterminados de seguridad.

Si los valores predeterminados de seguridad están habilitados, se le pedirá al usuario el registro de MFA y el uso de la aplicación Microsoft Authenticator. 

Esta tabla muestra los resultados de habilitar MFA con los valores predeterminados de seguridad y las directivas de acceso condicional.

| Método | Habilitado | Deshabilitado | Método de autenticación adicional |
|:-------|:-----|:-------|:-------|
| **Valores predeterminados de seguridad**  | No se pueden usar directivas de acceso condicional | Se pueden usar directivas de acceso condicional | Aplicación Microsoft Authenticator |
| **Directivas de acceso condicional** | Si hay alguna habilitada, no puede habilitar los valores predeterminados de seguridad | Si se deshabilitan todos, puede habilitar los valores predeterminados de seguridad  | Especificado por el usuario durante el registro de MFA  |
||||

## <a name="identity-and-device-access-policies"></a>Directivas de acceso a dispositivos e identidades

Las directivas y configuraciones de acceso a dispositivos e identidades son características de requisitos previos recomendadas y sus opciones de configuración combinada con el acceso condicional, Intune y directivas de Azure AD Identity Protection. Estas determinan si se debe conceder una solicitud de acceso determinada y en qué condiciones. Esta determinación se basa en la cuenta de usuario del inicio de sesión, el dispositivo que se usa, la aplicación que el usuario usa para obtener acceso, la ubicación desde la que se realiza la solicitud de acceso y una valoración del riesgo de la solicitud. Esta funcionalidad le permite garantizar que solo los usuarios y dispositivos aprobados puedan acceder a los recursos críticos.

>[!Note]
>Azure AD Identity Protection requiere licencias de Azure AD Premium P2, que se incluyen con Microsoft 365 E5.
>

Las directivas de acceso a dispositivos e identidades están definidas para usarse en tres niveles: 

- La protección de línea base es un nivel mínimo de seguridad para las identidades y dispositivos que tienen acceso a sus aplicaciones y datos.
- La protección confidencial ofrece seguridad adicional para datos específicos. Las identidades y los dispositivos están sujetos a los niveles más altos de requisitos de seguridad y estado del dispositivo.
- La protección para entornos con información altamente regulada o clasificada se aplica a una pequeña cantidad de datos que están clasificados en niveles superiores, contienen secretos comerciales o están sometidos a regulaciones de datos. Las identidades y los dispositivos están sujetos a los niveles incluso más altos de requisitos de seguridad y estado del dispositivo. 

Estos niveles y sus configuraciones correspondientes proporcionan niveles de protección coherentes en los datos, las identidades y los dispositivos.

Microsoft recomienda la configuración y la implementación de directivas de acceso a dispositivos e identidades en la organización, incluidas las configuraciones específicas para Microsoft Teams, Exchange Online y SharePoint. Para más información, consulte [Configuraciones de acceso a dispositivos e identidades](microsoft-365-policies-configurations.md).

<!--

## Let your users reset their own passwords

Self-Service Password Reset (SSPR) enables users to reset their own passwords without impacting IT staff. Users can quickly reset their passwords at any time and from any place. Watch [this video](https://go.microsoft.com/fwlink/?linkid=2128524) to set up SSPR.

## Sign in to SaaS apps with Azure AD

In addition to providing cloud authentication for users, Azure AD can also be your central way to secure all your apps, whether they’re on-premises, in Microsoft’s cloud, or in another cloud. By [integrating your apps into Azure AD](https://docs.microsoft.com/azure/active-directory/manage-apps/plan-an-application-integration), you can make it easy for your users to discover the applications they need and sign into them securely.

## Results of deployment of secure sign-ins

After deployment of MFA, your users:

- Are required to use MFA for sign-ins.
- Have completed the MFA registration process and are using MFA for all sign-ins.
- Can use SSPR to reset their own passwords.

- [Plan an Azure AD self-service password reset deployment](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment)

--> 

## <a name="admin-technical-resources-for-mfa-and-secure-sign-ins"></a>Recursos técnicos de administración para MFA e inicios de sesión seguros

- [MFA para Microsoft 365](../admin/security-and-compliance/multi-factor-authentication-microsoft-365.md)
- [Plan de identidad para Microsoft 365](identity-roadmap-microsoft-365.md)
- [Vídeos de aprendizaje de Azure Academy Azure AD](https://www.youtube.com/watch?v=pN8o0owHfI0&list=PL-V4YVm6AmwUFpC3rXr2i2piRQ708q_ia)
- [Configurar la directiva de registro de autenticación multi-factor de Azure](https://docs.microsoft.com/azure/active-directory/identity-protection/howto-identity-protection-configure-mfa-policy)
- [Configuraciones de acceso a dispositivos e identidades](microsoft-365-policies-configurations.md)

