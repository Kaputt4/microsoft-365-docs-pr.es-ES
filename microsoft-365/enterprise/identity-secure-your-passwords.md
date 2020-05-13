---
title: 'Paso 2: Proteja sus contraseñas'
f1.keywords:
- NOCSH
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
ms.openlocfilehash: 6e5c2567ee2027be2a84121fdad10ba873ec1c43
ms.sourcegitcommit: 1c90bcc5c56f24895f01c3e0423c3f6b73715c13
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "44214655"
---
# <a name="step-2-secure-your-passwords"></a><span data-ttu-id="9d127-103">Paso 2: Proteja sus contraseñas</span><span class="sxs-lookup"><span data-stu-id="9d127-103">Step 2: Secure your passwords</span></span>

![Fase 2: identidad](../media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-password-prot"></a>
## <a name="prevent-bad-passwords"></a><span data-ttu-id="9d127-105">Evite contraseñas no válidas</span><span class="sxs-lookup"><span data-stu-id="9d127-105">Prevent bad passwords</span></span>

<span data-ttu-id="9d127-106">*Este paso es opcional y se aplica a las versiones E3 y E5 de Microsoft 365*</span><span class="sxs-lookup"><span data-stu-id="9d127-106">*This is optional and applies to both the E3 and E5 versions of Microsoft 365*</span></span>

<span data-ttu-id="9d127-107">Todos los usuarios deben utilizar la [guía de contraseñas de Microsoft](https://www.microsoft.com/research/publication/password-guidance)para crear las contraseñas de sus cuentas de usuario.</span><span class="sxs-lookup"><span data-stu-id="9d127-107">All your users should be using [Microsoft's password guidance](https://www.microsoft.com/research/publication/password-guidance) to create their user account passwords.</span></span>

<span data-ttu-id="9d127-108">Para evitar que los usuarios creen una contraseña que se pueda determinar con facilidad, utilice la protección de contraseña de Azure AD, que utiliza tanto una lista de contraseñas globalmente prohibidas como una lista opcional personalizada de contraseñas prohibidas que usted especifique.</span><span class="sxs-lookup"><span data-stu-id="9d127-108">To prevent users from creating an easily-determined password, use Azure AD password protection, which uses both a global banned password list and an optional custom banned password list that you specify.</span></span> <span data-ttu-id="9d127-109">Por ejemplo, puede especificar términos que sean específicos de su organización, como:</span><span class="sxs-lookup"><span data-stu-id="9d127-109">For example, you can specify terms that are specific to your organization, such as:</span></span>

- <span data-ttu-id="9d127-110">Nombres de marcas</span><span class="sxs-lookup"><span data-stu-id="9d127-110">Brand names</span></span>
- <span data-ttu-id="9d127-111">Nombres de productos</span><span class="sxs-lookup"><span data-stu-id="9d127-111">Product names</span></span>
- <span data-ttu-id="9d127-112">Ubicaciones (por ejemplo, como la oficina central de la empresa)</span><span class="sxs-lookup"><span data-stu-id="9d127-112">Locations (for example, such as company headquarters)</span></span>
- <span data-ttu-id="9d127-113">Términos internos específicos de la empresa</span><span class="sxs-lookup"><span data-stu-id="9d127-113">Company-specific internal terms</span></span>
- <span data-ttu-id="9d127-114">Abreviaturas que tienen un significado específico en la empresa</span><span class="sxs-lookup"><span data-stu-id="9d127-114">Abbreviations that have specific company meaning</span></span>

<span data-ttu-id="9d127-115">Puede prohibir contraseñas no válidas [en la nube](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) y para los [Servicios de dominio de Active Directory (AD DS) locales](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises).</span><span class="sxs-lookup"><span data-stu-id="9d127-115">You can ban bad passwords [in the cloud](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) and for your [on-premises Active Directory Domain Services (AD DS)](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises).</span></span>

<span data-ttu-id="9d127-116">Como control provisional, puede consultar los [criterios de salida](identity-exit-criteria.md#crit-password-prot) correspondientes a esta sección.</span><span class="sxs-lookup"><span data-stu-id="9d127-116">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-password-prot) for this section.</span></span>

<a name="identity-pw-reset"></a>
## <a name="simplify-password-resets"></a><span data-ttu-id="9d127-117">Simplificar los restablecimientos de contraseña</span><span class="sxs-lookup"><span data-stu-id="9d127-117">Simplify password resets</span></span>

<span data-ttu-id="9d127-118">*Este paso es opcional y se aplica a las versiones E3 y E5 de Microsoft 365*</span><span class="sxs-lookup"><span data-stu-id="9d127-118">*This is optional and applies to both the E3 and E5 versions of Microsoft 365*</span></span>

<span data-ttu-id="9d127-119">En esta sección, habilitará el restablecimiento de contraseña de autoservicio (SSPR) para permitir a los usuarios restablecer o desbloquear sus contraseñas o cuentas.</span><span class="sxs-lookup"><span data-stu-id="9d127-119">In this section, you'll enable self-service password reset (SSPR) to allow users to reset or unlock their passwords or accounts.</span></span> <span data-ttu-id="9d127-120">Para alertarle acerca de abusos o usos indebidos, el sistema incluye informes detallados del seguimiento de acceso de los usuarios al sistema, además de notificaciones.</span><span class="sxs-lookup"><span data-stu-id="9d127-120">To alert you to misuse or abuse, you can use the detailed reporting that tracks when users access the system, along with notifications.</span></span> <span data-ttu-id="9d127-121">Debe habilitar la reescritura de contraseña para poder implementar los restablecimientos de contraseña.</span><span class="sxs-lookup"><span data-stu-id="9d127-121">You must enable password writeback before you can deploy password resets.</span></span>

<span data-ttu-id="9d127-122">Consulte las [instrucciones para habilitar el restablecimiento de contraseña](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment).</span><span class="sxs-lookup"><span data-stu-id="9d127-122">See the [instructions to roll out password reset](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment).</span></span>

|||
|:-------|:-----|
|![Guías de laboratorio de pruebas para Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="9d127-124">Guía del laboratorio de pruebas: restablecimiento de contraseña</span><span class="sxs-lookup"><span data-stu-id="9d127-124">Test Lab Guide: Password reset</span></span>](password-reset-m365-ent-test-environment.md) |
|||

<span data-ttu-id="9d127-125">Como control provisional, puede consultar los [criterios de salida](identity-exit-criteria.md#crit-identity-pw-reset) correspondientes a esta sección.</span><span class="sxs-lookup"><span data-stu-id="9d127-125">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-pw-reset) for this section.</span></span>


<a name="identity-sso"></a>
## <a name="simplify-user-sign-in"></a><span data-ttu-id="9d127-126">Simplificar el inicio de sesión de usuario</span><span class="sxs-lookup"><span data-stu-id="9d127-126">Simplify user sign-in</span></span>

<span data-ttu-id="9d127-127">*Esta función es opcional para los entornos híbridos y se aplica a las versiones E3 y E5 de Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="9d127-127">*This is optional for hybrid environments and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="9d127-128">En esta sección, configurará Azure Active Directory Seamless Single Sign-On (Azure AD Seamless SSO), que funciona mediante Sincronización de hash de contraseña (PHS) y Autenticación de paso a través (PTA) para permitir que los usuarios inicien sesión en servicios que usan cuentas de usuario de Azure AD sin tener que escribir sus contraseñas y, en muchos casos, los nombres de usuario.</span><span class="sxs-lookup"><span data-stu-id="9d127-128">In this section, you'll set up Azure Active Directory Seamless Single Sign-On (Azure AD Seamless SSO), which works with Password Hash Synchronization (PHS) and Pass-Through Authentication (PTA), to allow your users to sign in to services that use Azure AD user accounts without having to type in their passwords, and in many cases, their usernames.</span></span> <span data-ttu-id="9d127-129">Esto ofrece facilita a los usuarios el acceso a aplicaciones en la nube, como Office 365, sin necesidad de componentes locales adicionales, como los servidores de federación de identidades.</span><span class="sxs-lookup"><span data-stu-id="9d127-129">This gives your users easier access to cloud-based applications, such as Office 365, without needing any additional on-premises components such as identity federation servers.</span></span>

<span data-ttu-id="9d127-130">Configure el SSO de conexión directa de Azure AD con la herramienta Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="9d127-130">You configure Azure AD Seamless SSO with the Azure AD Connect tool.</span></span>

<span data-ttu-id="9d127-131">Vea las [instrucciones para configurar el SSO de conexión directa de Azure AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).</span><span class="sxs-lookup"><span data-stu-id="9d127-131">See the [instructions to configure Azure AD Seamless SSO](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).</span></span>

|||
|:-------|:-----|
|![Guías del entorno de pruebas para Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="9d127-133">Guía del entorno de pruebas: Inicio de sesión único de conexión directa de Azure AD</span><span class="sxs-lookup"><span data-stu-id="9d127-133">Test Lab Guide: Azure AD Seamless Single Sign-on</span></span>](single-sign-on-m365-ent-test-environment.md) |
|||

<span data-ttu-id="9d127-134">Como control provisional, puede consultar los [criterios de salida](identity-exit-criteria.md#crit-identity-sso) correspondientes a esta sección.</span><span class="sxs-lookup"><span data-stu-id="9d127-134">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-sso) for this section.</span></span>


<a name="identity-custom-sign-in"></a>
## <a name="customize-the-sign-in-page"></a><span data-ttu-id="9d127-135">Personalización de la página de inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="9d127-135">Customize the sign-in page</span></span>

<span data-ttu-id="9d127-136">*Esta sección es opcional y se aplica a las versiones E3 y E5 de Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="9d127-136">*This is optional and for both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="9d127-137">En esta sección, ayudará a los usuarios a reconocer la página de inicio de sesión de su organización; para ello, agregará el nombre de la compañía, el logotipo y otros elementos reconocibles.</span><span class="sxs-lookup"><span data-stu-id="9d127-137">In this section, you'll help users recognize your organization’s sign-in page by adding your company name, logo, and other recognizable elements.</span></span> 

<span data-ttu-id="9d127-138">Con Microsoft 365 Enterprise, puede personalizar la apariencia de las páginas de inicio de sesión y del Panel de acceso de forma que incluyan información de usuario personalizada, las combinaciones de colores y el logotipo de su compañía.</span><span class="sxs-lookup"><span data-stu-id="9d127-138">With Microsoft 365 Enterprise, you can customize the appearance of the sign-in and Access Panel pages so they include your company logo, color schemes, and custom user information.</span></span> 

<span data-ttu-id="9d127-139">Para obtener más información, consulte [Agregar la personalización de marca de su empresa a la página de inicio de sesión de Microsoft 365](https://docs.microsoft.com/office365/admin/setup/customize-sign-in-page).</span><span class="sxs-lookup"><span data-stu-id="9d127-139">For more information, see [Add your company branding to Microsoft 365 Sign In page](https://docs.microsoft.com/office365/admin/setup/customize-sign-in-page).</span></span>

<span data-ttu-id="9d127-140">Para obtener instrucciones de configuración, vea [Incorporación de personalización de marca de empresa a sus páginas de inicio de sesión y del Panel de acceso](https://aka.ms/aadpaddbranding).</span><span class="sxs-lookup"><span data-stu-id="9d127-140">For configuration instructions, see [Add company branding to your sign-in and Access Panel pages](https://aka.ms/aadpaddbranding).</span></span>

<span data-ttu-id="9d127-141">Como control provisional, puede consultar los [criterios de salida](identity-exit-criteria.md#crit-identity-custom-sign-in) correspondientes a esta sección.</span><span class="sxs-lookup"><span data-stu-id="9d127-141">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-custom-sign-in) for this section.</span></span>

## <a name="next-step"></a><span data-ttu-id="9d127-142">Siguiente paso</span><span class="sxs-lookup"><span data-stu-id="9d127-142">Next step</span></span>

|||
|:-------|:-----|
|![Paso 3](../media/stepnumbers/Step3.png)| [<span data-ttu-id="9d127-144">Proteja y administre los inicios de sesión de usuario</span><span class="sxs-lookup"><span data-stu-id="9d127-144">Secure and manage your user sign-ins</span></span>](identity-secure-user-sign-ins.md) |
