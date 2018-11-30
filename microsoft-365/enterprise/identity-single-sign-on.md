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
# <a name="step-10-simplify-user-sign-in"></a><span data-ttu-id="33c40-103">Paso 10: Simplificar el inicio de sesión de usuario</span><span class="sxs-lookup"><span data-stu-id="33c40-103">Step 10: Simplify user sign-in</span></span>

<span data-ttu-id="33c40-104">*Este paso es opcional para los entornos híbridos y es válido para las versiones E3 y E5 de Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="33c40-104">*This step is optional for hybrid environments and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="33c40-p101">En este paso, configurará el inicio de sesión único de conexión directa de Azure Active Directory (SSO de conexión directa de Azure AD) para permitir que los usuarios inicien sesión en los servicios que usen las cuentas de usuario de Azure AD sin tener que escribir las contraseñas ni, en muchos casos, sus nombres de usuario. Esto ofrece a los usuarios un acceso más fácil a las aplicaciones basadas en la nube, como Office 365, sin que se necesiten otros componentes locales, como servidores de federación de identidades.</span><span class="sxs-lookup"><span data-stu-id="33c40-p101">In Step 8, you'll set up Azure Active Directory Seamless Single Sign-On (Azure AD Seamless SSO) to allow your users to sign in to services that use Azure AD user accounts without having to type in their passwords, and in many cases, their usernames. This gives your users easier access to cloud-based applications, such as Office 365, without needing any additional on-premises components such as identity federation servers.</span></span>

<span data-ttu-id="33c40-107">Configurará el SSO de conexión directa de Azure AD con la herramienta Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="33c40-107">You'll configure Azure AD Seamless SSO with the Azure AD Connect tool.</span></span>

<span data-ttu-id="33c40-108">Vea las [instrucciones para configurar el SSO de conexión directa de Azure AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).</span><span class="sxs-lookup"><span data-stu-id="33c40-108">See the [instructions to configure Azure AD Seamless SSO](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).</span></span>

|||
|:-------|:-----|
|![Guías del entorno de pruebas para Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="33c40-110">Guía del entorno de pruebas: Inicio de sesión único de conexión directa de Azure AD</span><span class="sxs-lookup"><span data-stu-id="33c40-110">Test Lab Guide: Azure AD Seamless Single Sign-on</span></span>](single-sign-on-m365-ent-test-environment.md) |
|||

<span data-ttu-id="33c40-111">Como punto de control provisional, puede ver los [criterios de salida](identity-exit-criteria.md#crit-identity-sso) de este paso.</span><span class="sxs-lookup"><span data-stu-id="33c40-111">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-sso) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="33c40-112">Siguiente paso</span><span class="sxs-lookup"><span data-stu-id="33c40-112">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step11.png)| [<span data-ttu-id="33c40-113">Personalizar la página de inicio de sesión de Office 365</span><span class="sxs-lookup"><span data-stu-id="33c40-113">Customize the Office 365 sign-in page</span></span>](identity-customize-office-365-sign-in.md) |

