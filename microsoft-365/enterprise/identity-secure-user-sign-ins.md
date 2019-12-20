---
title: 'Paso 3: proteja y administre los inicios de sesión de usuario'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/20/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Haga que los inicios de sesión en los dispositivos Windows y en Microsoft 365 sean más seguros.
ms.openlocfilehash: c1379cfdd65204a27c8147ade8c8c8704e441f1f
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/19/2019
ms.locfileid: "40801735"
---
# <a name="step-3-secure-and-manage-your-user-sign-ins"></a>Paso 3: Proteja y administre los inicios de sesión de usuario

![Fase 2-Identidad](./media/deploy-foundation-infrastructure/identity_icon-small.png)


<a name="identity-windows-hello"></a>
## <a name="use-windows-hello-for-business"></a>Use Windows Hello para empresas

*Este paso es opcional y se aplica a las versiones E3 y E5 de Microsoft 365*

Windows Hello para empresas en Windows 10 Enterprise reemplaza el mero uso de contraseñas por la ultrasegura autenticación de dos factores cuando inicie sesión en un dispositivo Windows. Esta es un nueva forma de inicio de sesión que vincula el dispositivo de un usuario con un factor biométrico o un PIN.

Para más información, consulte [Información general para Windows Hello para empresas](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview).


<a name="identity-mfa"></a>
## <a name="set-up-azure-multi-factor-authentication"></a>Configure Azure Multi-Factor Authentication

*Este paso es opcional y se aplica a las versiones E3 y E5 de Microsoft 365*

En este paso, configurará Azure Multi-Factor Authentication (MFA) para agregar un segundo nivel de seguridad en inicios de sesión de usuario y transacciones. El MFA realiza una comprobación adicional después de que los usuarios hayan escrito correctamente su contraseña. Si no usa MFA, la contraseña será el único método de verificación de identidad. El problema de las contraseñas consiste en que un atacante pueda adivinarlas fácilmente y se pueden compartir con terceros de dudosa confianza.

Con MFA, el segundo nivel de seguridad puede ser:

- Un dispositivo personal y de confianza que no se pueda suplantar o duplicar fácilmente, como un smartphone.
- Un atributo biométrico, como una huella digital.

Habilitará MFA y configurará el método de autenticación secundario con [directivas de acceso condicional](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted#enable-multi-factor-authentication-with-conditional-access), que le permiten usar grupos de Azure Active Directory (Azure AD) para implementar MFA en conjuntos específicos de usuarios, como usuarios piloto, regiones geográficas o departamentos. Asegúrese de informar a los usuarios de que se habilitará MFA para que comprendan los requisitos (como el uso obligatorio de un smartphone para iniciar sesión) y que puedan iniciar sesión correctamente. 

Para obtener más información, vea [Planificar la implementación en la nube de Azure Multi-Factor Authentication](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted).

|||
|:-------|:-----|
|![Guías del entorno de pruebas para Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Guía de laboratorio de pruebas: Azure Multi-Factor Authentication](multi-factor-authentication-microsoft-365-test-environment.md) |
|||

Como control provisional, puede consultar los [criterios de salida](identity-exit-criteria.md#crit-identity-mfa) correspondientes a esta sección.

<a name="identity-ident-prot"></a>
## <a name="protect-against-credential-compromise"></a>Proteger contra credenciales en peligro

*Esto es opcional y solo se aplica a la versión E5 de Microsoft 365 Enterprise*

En esta sección, aprenderá a configurar las directivas que protejan credenciales en peligro, donde un atacante determine el nombre de una cuenta de usuario y la contraseña para acceder a servicios en la nube y los datos de una organización. La protección de identidad de Azure AD ofrece varias maneras de evitar que un atacante acceda a las credenciales de una cuenta de usuario.

Con Azure AD Identity Protection, puede:

|||
|:---------|:---------|
|Determinar y corregir posibles vulnerabilidades en las identidades de su organización|Azure AD usa el aprendizaje automático para detectar anomalías y actividad sospechosa, como inicios de sesión y actividades posteriores al inicio de sesión. Con estos datos, Azure AD Identity Protection genera informes y alertas que le ayudarán a evaluar los problemas y tomar medidas.|
|Detectar acciones sospechosas relacionadas con las identidades de su organización y responder a ellas automáticamente|Puede configurar directivas basadas en riesgos que respondan automáticamente a problemas detectados si se alcanza un nivel de riesgo específico. Estas directivas, además de otros controles de acceso condicional proporcionados por Azure AD y Microsoft Intune, pueden bloquear automáticamente el acceso o llevar a cabo acciones correctivas que incluyen el restablecimiento de contraseñas y la solicitud de Azure Multi-Factor Authentication en posteriores inicios de sesión.|
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

Como control provisional, puede consultar los [criterios de salida](identity-exit-criteria.md#crit-identity-ident-prot) correspondientes a esta sección.

|||
|:-------|:-----|
|![Paso 4](./media/stepnumbers/Step4.png)| [Agregue cuentas de usuario](identity-add-user-accounts.md) |
