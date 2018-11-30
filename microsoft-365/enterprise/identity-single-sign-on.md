---
title: 'Paso 10: Simplificar el inicio de sesión de usuario'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/01/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Comprenda y configure el inicio de sesión único de conexión directa de Azure AD (SSO de conexión directa).
ms.openlocfilehash: 9d18cb559d3a4a9ee401e0f94fb53bc6360d88c8
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2018
ms.locfileid: "26871702"
---
# <a name="step-10-simplify-user-sign-in"></a>Paso 10: Simplificar el inicio de sesión de usuario

*Este paso es opcional para los entornos híbridos y es válido para las versiones E3 y E5 de Microsoft 365 Enterprise*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

En este paso, configurará el inicio de sesión único de conexión directa de Azure Active Directory (SSO de conexión directa de Azure AD) para permitir que los usuarios inicien sesión en los servicios que usen las cuentas de usuario de Azure AD sin tener que escribir las contraseñas ni, en muchos casos, sus nombres de usuario. Esto ofrece a los usuarios un acceso más fácil a las aplicaciones basadas en la nube, como Office 365, sin que se necesiten otros componentes locales, como servidores de federación de identidades.

Configurará el SSO de conexión directa de Azure AD con la herramienta Azure AD Connect.

Vea las [instrucciones para configurar el SSO de conexión directa de Azure AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).

|||
|:-------|:-----|
|![Guías del entorno de pruebas para Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Guía del entorno de pruebas: Inicio de sesión único de conexión directa de Azure AD](single-sign-on-m365-ent-test-environment.md) |
|||

Como punto de control provisional, puede ver los [criterios de salida](identity-exit-criteria.md#crit-identity-sso) de este paso.

## <a name="next-step"></a>Siguiente paso

|||
|:-------|:-----|
|![](./media/stepnumbers/Step11.png)| [Personalizar la página de inicio de sesión de Office 365](identity-customize-office-365-sign-in.md) |

