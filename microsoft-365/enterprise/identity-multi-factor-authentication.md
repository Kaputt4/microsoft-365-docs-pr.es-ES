---
title: 'Paso 4: Configurar autenticación segura de usuario'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/06/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Comprenda y configure la autenticación multifactor para las cuentas de usuario.
ms.openlocfilehash: 2a4a0926a08ae8279523219a2d7a2386ea0c6742
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2019
ms.locfileid: "36981851"
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

Habilitará MFA y configurará el método de autenticación secundario con [directivas de acceso condicional](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted#enable-multi-factor-authentication-with-conditional-access), que le permiten usar grupos de Azure Active Directory (Azure AD) para implementar MFA en conjuntos específicos de usuarios, como usuarios piloto, regiones geográficas o departamentos. Asegúrese de informar a los usuarios de que se habilitará MFA para que comprendan los requisitos (como el uso obligatorio de un smartphone para iniciar sesión) y que puedan iniciar sesión correctamente. 

Para obtener más información, consulte [el Plan de autenticación multifactor](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted).

>[!Note]
>En algunas aplicaciones (como Microsoft Office 2010 o versiones anteriores, y Apple Mail), no se puede usar MFA. Para usar estas aplicaciones, necesitará usar “contraseñas de aplicación” en lugar de la contraseña tradicional. La contraseña de aplicación permite a la aplicación omitir MFA y seguir funcionando. Para obtener más información sobre las contraseñas de aplicación, vea [Crear una contraseña de aplicación para Office 365](https://support.office.com/article/Create-an-app-password-for-Office-365-3e7c860f-bda4-4441-a618-b53953ee1183).
>

|||
|:-------|:-----|
|![Guías de laboratorio de pruebas en Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Guía de laboratorio de pruebas: Autenticación multifactor](multi-factor-authentication-microsoft-365-test-environment.md) |
|||

Como control provisional, puede consultar los [criterios de salida](identity-exit-criteria.md#crit-identity-mfa) correspondientes a esta sección.

<a name="identity-password-prot"></a>
## <a name="prevent-bad-passwords"></a>Evite contraseñas no válidas

*Este paso es opcional y se aplica a las versiones E3 y E5 de Microsoft 365 Enterprise*

Para evitar que los usuarios creen una contraseña que se pueda averiguar con facilidad, use la protección con contraseña de Azure AD, que usa tanto una lista de contraseñas prohibidas global como una lista opcional de contraseñas prohibidas personalizada que usted especifica. Por ejemplo, puede especificar términos que sean específicos para su organización, como "

- Nombres de marcas
- Nombres de productos
- Ubicaciones (por ejemplo, como la oficina central de la empresa)
- Términos internos específicos de la empresa
- Abreviaturas que tienen un significado específico en la empresa.

Puede prohibir contraseñas no válidas [en la nube](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) y para los [Servicios de dominio de Active Directory (AD DS) locales](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises).

Como control provisional, puede consultar los [criterios de salida](identity-exit-criteria.md#crit-password-prot) correspondientes a esta sección.

<a name="identity-ident-prot"></a>
## <a name="protect-against-credential-compromise"></a>Proteger contra credenciales en peligro

*Esto es opcional y solo se aplica a la versión E5 de Microsoft 365 Enterprise*

En esta sección, aprenderá a configurar las directivas que protejan credenciales en peligro, donde un atacante determine el nombre de una cuenta de usuario y la contraseña para acceder a servicios en la nube y los datos de una organización. La protección de identidad de Azure AD proporciona varias formas de evitar que un atacante se desplace lateralmente por las cuentas y grupos, y acceda a sus datos más importantes.

Con Azure AD Identity Protection, puede:

|||
|:---------|:---------|
|Determinar y corregir posibles vulnerabilidades en las identidades de su organización|Azure AD usa el aprendizaje automático para detectar anomalías y actividad sospechosa, como inicios de sesión y actividades posteriores al inicio de sesión. Con estos datos, Azure AD Identity Protection genera informes y alertas que le ayudarán a evaluar los problemas y tomar medidas.|
|Detectar acciones sospechosas relacionadas con las identidades de su organización y responder a ellas automáticamente|Puede configurar directivas basadas en riesgos que respondan automáticamente a problemas detectados si se alcanza un nivel de riesgo específico. Estas directivas, además de otros controles de acceso condicional proporcionados por Azure AD y Microsoft Intune, pueden bloquear automáticamente el acceso o llevar a cabo acciones correctivas que incluyen el restablecimiento de contraseñas y la solicitud de la autenticación multifactor en posteriores inicios de sesión.|
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

