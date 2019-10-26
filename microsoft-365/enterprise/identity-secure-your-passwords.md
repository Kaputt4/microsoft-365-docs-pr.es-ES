---
title: 'Paso 2: Proteja sus contraseñas'
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
description: Necesita que sus contraseñas sean seguras y que se puedan administrar en toda la organización.
ms.openlocfilehash: a3661eedc11e0c826422f540cf1e2e9abf911f9d
ms.sourcegitcommit: 83b919f8a7fcc4f75044ffc09fecd66fb4ed35b5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/24/2019
ms.locfileid: "37662556"
---
# <a name="step-2-secure-your-passwords"></a>Paso 2: Proteja sus contraseñas

![Fase 2: identidad](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-password-prot"></a>
## <a name="prevent-bad-passwords"></a>Evite contraseñas no válidas

*Este paso es opcional y se aplica a las versiones E3 y E5 de Microsoft 365 Enterprise*

Todos los usuarios deben utilizar la [guía de contraseñas de Microsoft](https://www.microsoft.com/research/publication/password-guidance/)para crear las contraseñas de sus cuentas de usuario.

Para evitar que los usuarios creen una contraseña que se pueda determinar con facilidad, utilice la protección de contraseña de Azure AD, que utiliza tanto una lista de contraseñas globalmente prohibidas como una lista opcional personalizada de contraseñas prohibidas que usted especifique. Por ejemplo, puede especificar términos que sean específicos de su organización, como:

- Nombres de marcas
- Nombres de productos
- Ubicaciones (por ejemplo, como la oficina central de la empresa)
- Términos internos específicos de la empresa
- Abreviaturas que tienen un significado específico en la empresa

Puede prohibir contraseñas no válidas [en la nube](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) y para los [Servicios de dominio de Active Directory (AD DS) locales](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises).

Como control provisional, puede consultar los [criterios de salida](identity-exit-criteria.md#crit-password-prot) correspondientes a esta sección.

<a name="identity-pw-reset"></a>
## <a name="simplify-password-resets"></a>Simplificar los restablecimientos de contraseña

*Este paso es opcional y se aplica a las versiones E3 y E5 de Microsoft 365 Enterprise*

En esta sección, habilitará el restablecimiento de contraseña de autoservicio (SSPR) para permitir a los usuarios restablecer o desbloquear sus contraseñas o cuentas. Para alertarle acerca de abusos o usos indebidos, el sistema incluye informes detallados del seguimiento de acceso de los usuarios al sistema, además de notificaciones. Debe habilitar la reescritura de contraseña para poder implementar los restablecimientos de contraseña.

Consulte las [instrucciones para habilitar el restablecimiento de contraseña](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment).

|||
|:-------|:-----|
|![Guías de laboratorio de pruebas para Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Guía del laboratorio de pruebas: restablecimiento de contraseña](password-reset-m365-ent-test-environment.md) |
|||

Como control provisional, puede consultar los [criterios de salida](identity-exit-criteria.md#crit-identity-pw-reset) correspondientes a esta sección.


<a name="identity-sso"></a>
## <a name="simplify-user-sign-in"></a>Simplificar el inicio de sesión de usuario

*Esta función es opcional para los entornos híbridos y se aplica a las versiones E3 y E5 de Microsoft 365 Enterprise*

En esta sección, configurará Azure Active Directory Seamless Single Sign-On (Azure AD Seamless SSO), que funciona mediante Sincronización de hash de contraseña (PHS) y Autenticación de paso a través (PTA) para permitir que los usuarios inicien sesión en servicios que usan cuentas de usuario de Azure AD sin tener que escribir sus contraseñas y, en muchos casos, los nombres de usuario. Esto ofrece facilita a los usuarios el acceso a aplicaciones en la nube, como Office 365, sin necesidad de componentes locales adicionales, como los servidores de federación de identidades.

Configure el SSO de conexión directa de Azure AD con la herramienta Azure AD Connect.

Vea las [instrucciones para configurar el SSO de conexión directa de Azure AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).

|||
|:-------|:-----|
|![Guías del entorno de pruebas para Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Guía del entorno de pruebas: Inicio de sesión único de conexión directa de Azure AD](single-sign-on-m365-ent-test-environment.md) |
|||

Como control provisional, puede consultar los [criterios de salida](identity-exit-criteria.md#crit-identity-sso) correspondientes a esta sección.


<a name="identity-custom-sign-in"></a>
## <a name="customize-the-office-365-sign-in-page"></a>Personalizar la página de inicio de sesión de Office 365

*Esta sección es opcional y se aplica a las versiones E3 y E5 de Microsoft 365 Enterprise*

En esta sección, ayudará a los usuarios a reconocer la página de inicio de sesión de su organización; para ello, agregará el nombre de la compañía, el logotipo y otros elementos reconocibles. 

Con Microsoft 365 Enterprise, puede personalizar la apariencia de las páginas de inicio de sesión y del Panel de acceso de forma que incluyan información de usuario personalizada, las combinaciones de colores y el logotipo de su compañía. 

Para obtener más información, vea [Agregar la personalización de marca de su empresa a la página de inicio de sesión de Office 365](https://docs.microsoft.com/office365/admin/setup/customize-sign-in-page).

Para obtener instrucciones de configuración, vea [Incorporación de personalización de marca de empresa a sus páginas de inicio de sesión y del Panel de acceso](http://aka.ms/aadpaddbranding).

Como control provisional, puede consultar los [criterios de salida](identity-exit-criteria.md#crit-identity-custom-sign-in) correspondientes a esta sección.

## <a name="next-step"></a>Siguiente paso

|||
|:-------|:-----|
|![Paso 3](./media/stepnumbers/Step3.png)| [Proteja y administre los inicios de sesión de usuario](identity-secure-user-sign-ins.md) |
