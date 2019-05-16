---
title: 'Paso 4: Configurar autenticación segura de usuario'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/17/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Comprenda y configure la autenticación multifactor para las cuentas de usuario.
ms.openlocfilehash: 73e884802329765fd6a89cfb7d0e04116c17968c
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "34072090"
---
# <a name="step-4-configure-secure-user-authentication"></a>Paso 4: Configurar autenticación segura de usuario

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-mfa"></a>
## <a name="set-up-multi-factor-authentication"></a>Configurar la autenticación multifactor

*Este paso es opcional y es válido para las versiones E3 y E5 de Microsoft 365 Enterprise*

En este paso, configurará la autenticación multifactor (MFA) para agregar un segundo nivel de seguridad en las transacciones y los inicios de sesión de usuario. MFA necesita un método de verificación adicional después de que los usuarios escriban correctamente la contraseña. Sin MFA, la contraseña es el único método de verificación. El problema de las contraseñas es que un atacante podría adivinar fácilmente muchas de ellas, o bien se pueden compartir de manera inadvertida con partes que no son de confianza.

Con MFA, el segundo nivel de seguridad puede ser:

- Un dispositivo personal y de confianza que no se pueda suplantar o duplicar fácilmente, como un smartphone.
- Un atributo biométrico, como una huella digital.

Habilitará MFA y configurará el método de autenticación secundario en cada cuenta de usuario. Asegúrese de informar a los usuarios de que se habilitará MFA para que comprendan los requisitos (como el uso obligatorio de un smartphone para iniciar sesión) y que puedan iniciar sesión correctamente.

Para obtener más información, consulte [el Plan de autenticación multifactor](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted).

>[!Note]
>En algunas aplicaciones (como Microsoft Office 2010 o versiones anteriores, y Apple Mail), no se puede usar MFA. Para usar estas aplicaciones, necesitará usar “contraseñas de aplicación” en lugar de la contraseña tradicional. La contraseña de aplicación permite a la aplicación omitir MFA y seguir funcionando. Para obtener más información sobre las contraseñas de aplicación, vea [Crear una contraseña de aplicación para Office 365](https://support.office.com/article/Create-an-app-password-for-Office-365-3e7c860f-bda4-4441-a618-b53953ee1183).
>

|||
|:-------|:-----|
|![Guías de laboratorio de pruebas en Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Guía de laboratorio de pruebas: Autenticación multifactor](multi-factor-authentication-microsoft-365-test-environment.md) |
|||

Como control provisional, puede ver el [criterio de salida](identity-exit-criteria.md#crit-identity-mfa) de esta sección.



<a name="identity-ident-prot"></a>
## <a name="protect-against-credential-compromise"></a>Proteger contra credenciales en peligro

*Esto es opcional y solo se aplica a la versión E5 de Microsoft 365 Enterprise*

En esta sección, aprenderá a configurar las directivas que protejan credenciales en peligro, donde un atacante determine el nombre de una cuenta de usuario y la contraseña para acceder a servicios en la nube y los datos de una organización. La protección de identidad de Azure AD proporciona varias formas de evitar que un atacante se desplace lateralmente por las cuentas y grupos, y acceda a sus datos más importantes.

Con Azure AD Identity Protection, puede:

|||
|:---------|:---------|
|Determinar y corregir posibles vulnerabilidades en las identidades de su organización|Azure AD usa aprendizaje automático para detectar anomalías y actividades sospechosas, como inicios de sesión y actividades posteriores al inicio de sesión. Con estos datos, Identity Protection genera informes y alertas que le permiten evaluar los problemas y tomar medidas.|
|Detectar acciones sospechosas relacionadas con las identidades de su organización y responder a ellas automáticamente|Puede configurar directivas basadas en riesgos que responden automáticamente a los problemas encontrados cuando se alcanza un nivel de riesgo especificado. Estas directivas, además de otros controles de acceso condicional proporcionados por Azure Active Directory y Enterprise Mobility + Security (EMS), pueden automáticamente impedir el acceso o realizar acciones correctivas, como activar restablecimientos de contraseña y exigir la autenticación multifactor para los inicios de sesión posteriores.|
|Investigar incidentes sospechosos y solucionarlos con acciones administrativas|Puede investigar eventos de riesgo con información sobre el incidente de seguridad. Hay disponibles flujos de trabajo básicos para realizar un seguimiento de las investigaciones e iniciar acciones de corrección, como restablecimientos de contraseña.|

Vea [más información sobre Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection).

Vea los [pasos para habilitar Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable).

El resultado de este paso es que habilitó Azure AD Identity Protection y ahora lo usa para:

- Solucionar posibles vulnerabilidades de identidad.
- Detectar posibles intentos de uso ilícito de credenciales.
- Investigar y solucionar incidentes de identidad sospechosos y continuados.

|||
|:-------|:-----|
|![Guías de laboratorio de pruebas en Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Guía de laboratorio de pruebas: Azure AD Identity Protection](azure-ad-identity-protection-microsoft-365-test-environment.md) |
|||

Como control provisional, puede ver el [criterio de salida](identity-exit-criteria.md#crit-identity-ident-prot) de esta sección.

## <a name="monitor-tenant-and-sign-in-activity"></a>Supervisar la actividad de inicio de sesión y del espacio empresarial

*Este paso es opcional y es válido para las versiones E3 y E5 de Microsoft 365 Enterprise*

En este paso, revisará los registros de auditoría y la actividad de inicio de sesión con los informes de Azure AD. Hay disponibles dos tipos de informes.

El **Informe de actividades de registros de auditoría** registra el historial de todas las tareas realizadas en el espacio empresarial de Azure AD. Este informe responde a preguntas como las siguientes:

- ¿Quién agregó a un usuario a un grupo de administradores?
- ¿Qué usuarios inician sesión en una aplicación específica?
- ¿Cuántos restablecimientos de contraseña se producen?

El **Informe de actividades de inicios de sesión** registra quién realizó las tareas incluidas en el informe de registros de auditoría. Este informe responde a preguntas como las siguientes:

- Para un usuario específico que esté bajo investigación, ¿cuál es su patrón de inicio de sesión?
- ¿Cuál es mi volumen de inicios de sesión en un día, semana o mes?
- ¿Cuántos de estos intentos de inicio de sesión no fueron correctos y para qué cuentas?

Para obtener más información sobre los informes y obtener acceso a ellos, vea [Informes de Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-azure-portal).

Como resultado de este paso, obtendrá información sobre estos informes y conocerá cómo puede usarlos para comprender en profundidad los eventos y actividades de Azure AD con fines de planeamiento y seguridad.



## <a name="next-step"></a>Paso siguiente

|||
|:-------|:-----|
|![](./media/stepnumbers/Step5.png)| [Simplificar el acceso de usuarios](identity-password-reset.md) |

