---
title: Administrar contraseñas de cuentas de usuario de Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-mar2020
ms.collection:
- Ent_O365
- M365-subscription-management
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: 98ca5b3f-f720-4d8e-91be-fe656548a25a
description: Obtenga información sobre cómo administrar contraseñas de cuentas de usuario de Microsoft 365.
ms.openlocfilehash: af64002ad54b517a6e8f0b687a00d6bed9ab0214
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2020
ms.locfileid: "48328542"
---
# <a name="manage-microsoft-365-user-account-passwords"></a><span data-ttu-id="28e14-103">Administrar contraseñas de cuentas de usuario de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="28e14-103">Manage Microsoft 365 user account passwords</span></span>

<span data-ttu-id="28e14-104">*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="28e14-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="28e14-105">Puede administrar las contraseñas de cuentas de usuario de Microsoft 365 de varias maneras, según la configuración de identidad.</span><span class="sxs-lookup"><span data-stu-id="28e14-105">You can manage Microsoft 365 user account passwords in several different ways, depending on your identity configuration.</span></span> <span data-ttu-id="28e14-106">Puede administrar cuentas de usuario en el Centro de administración de [Microsoft 365,](https://docs.microsoft.com/microsoft-365/admin/add-users/)en Servicios de dominio de Active Directory (AD DS) o en el Centro de administración de Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="28e14-106">You can manage user accounts in the [Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/add-users/), in Active Directory Domain Services (AD DS), or in the Azure Active Directory (Azure AD) admin center.</span></span>

## <a name="plan-for-where-and-how-you-will-manage-your-user-account-passwords"></a><span data-ttu-id="28e14-107">Planear dónde y cómo administrará las contraseñas de las cuentas de usuario</span><span class="sxs-lookup"><span data-stu-id="28e14-107">Plan for where and how you will manage your user account passwords</span></span>

<span data-ttu-id="28e14-108">El lugar y la forma en que puede administrar las cuentas de usuario depende del modelo de identidad que desee usar para Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="28e14-108">Where and how you can manage your user accounts depends on the identity model you want to use for your Microsoft 365.</span></span> <span data-ttu-id="28e14-109">Los dos modelos son híbridos y solo en la nube.</span><span class="sxs-lookup"><span data-stu-id="28e14-109">The two models are cloud-only and hybrid.</span></span>
  
### <a name="cloud-only"></a><span data-ttu-id="28e14-110">Solo de nube</span><span class="sxs-lookup"><span data-stu-id="28e14-110">Cloud-only</span></span>

<span data-ttu-id="28e14-111">Las contraseñas de cuentas de usuario se administran en:</span><span class="sxs-lookup"><span data-stu-id="28e14-111">You manage user account passwords in:</span></span>

- [<span data-ttu-id="28e14-112">Centro de administración de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="28e14-112">The Microsoft 365 admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/add-users/)
- <span data-ttu-id="28e14-113">Centro de administración de Azure AD</span><span class="sxs-lookup"><span data-stu-id="28e14-113">The Azure AD admin center</span></span>
    
### <a name="hybrid"></a><span data-ttu-id="28e14-114">Híbrido</span><span class="sxs-lookup"><span data-stu-id="28e14-114">Hybrid</span></span>

<span data-ttu-id="28e14-115">Con la identidad híbrida, las contraseñas se almacenan en AD DS, por lo que debe usar las herramientas locales de AD DS para administrar las contraseñas de cuentas de usuario.</span><span class="sxs-lookup"><span data-stu-id="28e14-115">With hybrid identity, passwords are stored in AD DS so you must use on-premises AD DS tools to manage user account passwords.</span></span> <span data-ttu-id="28e14-116">Incluso cuando se usa la sincronización de hash de contraseña (PHS), en la que Azure AD almacena una versión con hash de la versión ya con hash en AD DS, usted y los usuarios deben administrar sus contraseñas en AD DS.</span><span class="sxs-lookup"><span data-stu-id="28e14-116">Even when using Password Hash Synchronization (PHS), in which Azure AD stores a hashed version of the already hashed version in AD DS, you and users must manage their passwords in AD DS.</span></span>

<span data-ttu-id="28e14-117">Con [la reescribición de](#pw_writeback)contraseñas, los usuarios pueden cambiar sus contraseñas de AD DS a través de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="28e14-117">With [password writeback](#pw_writeback), your users can change their AD DS passwords through Azure AD.</span></span>

## <a name="prevent-bad-passwords"></a><span data-ttu-id="28e14-118">Evite contraseñas no válidas</span><span class="sxs-lookup"><span data-stu-id="28e14-118">Prevent bad passwords</span></span>

<span data-ttu-id="28e14-119">Todos los usuarios deben utilizar la [guía de contraseñas de Microsoft](https://www.microsoft.com/research/publication/password-guidance)para crear las contraseñas de sus cuentas de usuario.</span><span class="sxs-lookup"><span data-stu-id="28e14-119">All your users should be using [Microsoft's password guidance](https://www.microsoft.com/research/publication/password-guidance) to create their user account passwords.</span></span>

<span data-ttu-id="28e14-120">Para evitar que los usuarios creen una contraseña que se pueda determinar con facilidad, utilice la protección de contraseña de Azure AD, que utiliza tanto una lista de contraseñas globalmente prohibidas como una lista opcional personalizada de contraseñas prohibidas que usted especifique.</span><span class="sxs-lookup"><span data-stu-id="28e14-120">To prevent users from creating an easily-determined password, use Azure AD password protection, which uses both a global banned password list and an optional custom banned password list that you specify.</span></span> <span data-ttu-id="28e14-121">Por ejemplo, puede especificar términos que sean específicos de su organización, como:</span><span class="sxs-lookup"><span data-stu-id="28e14-121">For example, you can specify terms that are specific to your organization, such as:</span></span>

- <span data-ttu-id="28e14-122">Nombres de marcas</span><span class="sxs-lookup"><span data-stu-id="28e14-122">Brand names</span></span>
- <span data-ttu-id="28e14-123">Nombres de productos</span><span class="sxs-lookup"><span data-stu-id="28e14-123">Product names</span></span>
- <span data-ttu-id="28e14-124">Ubicaciones (por ejemplo, como la oficina central de la empresa)</span><span class="sxs-lookup"><span data-stu-id="28e14-124">Locations (for example, such as company headquarters)</span></span>
- <span data-ttu-id="28e14-125">Términos internos específicos de la empresa</span><span class="sxs-lookup"><span data-stu-id="28e14-125">Company-specific internal terms</span></span>
- <span data-ttu-id="28e14-126">Abreviaturas que tienen un significado específico en la empresa</span><span class="sxs-lookup"><span data-stu-id="28e14-126">Abbreviations that have specific company meaning</span></span>

<span data-ttu-id="28e14-127">Puede prohibir contraseñas [incorrectas en la nube](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) y para [su AD DS local.](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises)</span><span class="sxs-lookup"><span data-stu-id="28e14-127">You can ban bad passwords [in the cloud](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) and for your [on-premises AD DS](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises).</span></span>

## <a name="simplify-user-sign-in"></a><span data-ttu-id="28e14-128">Simplificar el inicio de sesión de usuario</span><span class="sxs-lookup"><span data-stu-id="28e14-128">Simplify user sign-in</span></span>

<span data-ttu-id="28e14-129">Azure AD Seamless Single Sign-On (SSO de conexión directa de Azure AD) funciona con PHS y Pass-Through Authentication (PTA), para permitir que los usuarios inicien sesión en los servicios que usan cuentas de usuario de Azure AD sin tener que escribir sus contraseñas y, en muchos casos, sus nombres de usuario.</span><span class="sxs-lookup"><span data-stu-id="28e14-129">Azure AD Seamless Single Sign-On (Azure AD Seamless SSO) works with PHS and Pass-Through Authentication (PTA), to allow your users to sign in to services that use Azure AD user accounts without having to type in their passwords, and in many cases, their usernames.</span></span> <span data-ttu-id="28e14-130">Esto ofrece facilita a los usuarios el acceso a aplicaciones en la nube, como Office 365, sin necesidad de componentes locales adicionales, como los servidores de federación de identidades.</span><span class="sxs-lookup"><span data-stu-id="28e14-130">This gives your users easier access to cloud-based applications, such as Office 365, without needing any additional on-premises components such as identity federation servers.</span></span>

<span data-ttu-id="28e14-131">Configure el SSO de conexión directa de Azure AD con la herramienta Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="28e14-131">You configure Azure AD Seamless SSO with the Azure AD Connect tool.</span></span> <span data-ttu-id="28e14-132">Vea las [instrucciones para configurar el SSO de conexión directa de Azure AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).</span><span class="sxs-lookup"><span data-stu-id="28e14-132">See the [instructions to configure Azure AD Seamless SSO](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).</span></span>

<a name="pw_writeback"></a>
## <a name="simplify-password-updates-to-ad-ds"></a><span data-ttu-id="28e14-133">Simplificar las actualizaciones de contraseñas en AD DS</span><span class="sxs-lookup"><span data-stu-id="28e14-133">Simplify password updates to AD DS</span></span>

<span data-ttu-id="28e14-134">Con la reescribición de contraseñas, puede permitir que los usuarios restablezcan sus contraseñas a través de Azure AD, que luego se replica en AD DS.</span><span class="sxs-lookup"><span data-stu-id="28e14-134">With password writeback, you can allow users to reset their passwords through Azure AD, which is then replicated to AD DS.</span></span> <span data-ttu-id="28e14-135">Los usuarios no necesitan tener acceso a su AD DS local para actualizar sus contraseñas.</span><span class="sxs-lookup"><span data-stu-id="28e14-135">Users don’t need to access their on-premises AD DS to update their passwords.</span></span> <span data-ttu-id="28e14-136">Esto resulta útil para los usuarios móviles o remotos que no disponen de una conexión de acceso remoto a la red local.</span><span class="sxs-lookup"><span data-stu-id="28e14-136">This is valuable to roaming or remote users who do not have a remote access connection to the on-premises network.</span></span>

<span data-ttu-id="28e14-137">La escritura diferida de contraseñas es necesaria para utilizar por completo las capacidades de Azure AD Identity Protection, como solicitar a los usuarios que cambien sus contraseñas locales cuando se haya detectado un alto riesgo de que la cuenta se haya visto comprometida.</span><span class="sxs-lookup"><span data-stu-id="28e14-137">Password writeback is required to fully utilize Azure AD Identity Protection capabilities, such as requiring users to change their on-premises passwords when there has been a high risk of account compromise detected.</span></span>

<span data-ttu-id="28e14-138">Para obtener más información e instrucciones de configuración, vea [Azure AD SSPR with password writeback](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-writeback) (SSPR de Azure AD con escritura diferida de contraseñas).</span><span class="sxs-lookup"><span data-stu-id="28e14-138">For additional information and configuration instructions, see [Azure AD SSPR with password writeback](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-writeback).</span></span>

>[!Note]
><span data-ttu-id="28e14-p108">Actualice a la última versión de Azure AD Connect para garantizar que tiene la mejor experiencia posible y nuevas características cuando se publican. Para obtener más información, vea [Instalación personalizada de Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-get-started-custom).</span><span class="sxs-lookup"><span data-stu-id="28e14-p108">Upgrade to the latest version of Azure AD Connect to ensure the best possible experience and new features as they are released. For more information, see [Custom installation of Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-get-started-custom).</span></span>
>

## <a name="simplify-password-resets"></a><span data-ttu-id="28e14-141">Simplificar los restablecimientos de contraseña</span><span class="sxs-lookup"><span data-stu-id="28e14-141">Simplify password resets</span></span>

<span data-ttu-id="28e14-142">El autoservicio de restablecimiento de contraseña (SSPR) permite a los usuarios restablecer o desbloquear sus contraseñas o cuentas.</span><span class="sxs-lookup"><span data-stu-id="28e14-142">Self-service password reset (SSPR) allows users to reset or unlock their passwords or accounts.</span></span> <span data-ttu-id="28e14-143">Para alertarle acerca de abusos o usos indebidos, el sistema incluye informes detallados del seguimiento de acceso de los usuarios al sistema, además de notificaciones.</span><span class="sxs-lookup"><span data-stu-id="28e14-143">To alert you to misuse or abuse, you can use the detailed reporting that tracks when users access the system, along with notifications.</span></span> <span data-ttu-id="28e14-144">Debe habilitar la [reescribición de contraseñas](#pw_writeback) para poder implementar restablecimientos de contraseña.</span><span class="sxs-lookup"><span data-stu-id="28e14-144">You must enable [password writeback](#pw_writeback) before you can deploy password resets.</span></span>

<span data-ttu-id="28e14-145">Consulte las [instrucciones para habilitar el restablecimiento de contraseña](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment).</span><span class="sxs-lookup"><span data-stu-id="28e14-145">See the [instructions to roll out password reset](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment).</span></span>

