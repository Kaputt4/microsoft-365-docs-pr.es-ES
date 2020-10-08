---
title: Integración de Microsoft 365 con entornos locales
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.collection:
- Ent_O365
search.appverid:
- MET150
- LYN150
- SPS150
- MOE150
- MED150
ms.assetid: 263faf8d-aa21-428b-aed3-2021837a4b65
description: En este artículo, aprenderá a integrar Microsoft 365 con los servicios de directorio y los entornos locales existentes.
ms.openlocfilehash: 9c5e287ed4a440d1f62081a4c94e39f0f162b4dc
ms.sourcegitcommit: 11d1044c6600b1f568b6dc8a53db9b07f2f0ad1c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/08/2020
ms.locfileid: "48384869"
---
# <a name="microsoft-365-integration-with-on-premises-environments"></a><span data-ttu-id="73be1-103">Integración de Microsoft 365 con entornos locales</span><span class="sxs-lookup"><span data-stu-id="73be1-103">Microsoft 365 integration with on-premises environments</span></span>

<span data-ttu-id="73be1-104">*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="73be1-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="73be1-105">Puede integrar Microsoft 365 con los servicios locales de dominio de Active Directory (AD DS) existentes y con instalaciones locales de Exchange Server, Skype empresarial Server 2015 o SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="73be1-105">You can integrate Microsoft 365 with your existing on-premises Active Directory Domain Services (AD DS) and with on-premises installations of Exchange Server, Skype for Business Server 2015, or SharePoint Server.</span></span>
  
 - <span data-ttu-id="73be1-106">Al integrar AD DS, puede sincronizar y administrar las cuentas de usuario de ambos entornos.</span><span class="sxs-lookup"><span data-stu-id="73be1-106">When you integrate AD DS, you can synchronize and manage user accounts for both environments.</span></span> <span data-ttu-id="73be1-107">También puede Agregar la sincronización de hash de contraseña (PHS) o el inicio de sesión único (SSO) para que los usuarios puedan iniciar sesión en ambos entornos con sus credenciales locales.</span><span class="sxs-lookup"><span data-stu-id="73be1-107">You can also add password hash synchronization (PHS) or single sign-on (SSO) so users can log on to both environments with their on-premises credentials.</span></span>
 - <span data-ttu-id="73be1-108">Cuando se integra con productos de servidor local, se crea un entorno híbrido.</span><span class="sxs-lookup"><span data-stu-id="73be1-108">When you integrate with on-premises server products, you create a hybrid environment.</span></span> <span data-ttu-id="73be1-109">Un entorno híbrido puede ayudarle a migrar usuarios o información a Microsoft 365, o puede seguir teniendo algunos usuarios o información local y algunos en la nube.</span><span class="sxs-lookup"><span data-stu-id="73be1-109">A hybrid environment can help as you migrate users or information to Microsoft 365, or you can continue to have some users or some information on-premises and some in the cloud.</span></span> <span data-ttu-id="73be1-110">Para obtener más información acerca de los entornos híbridos, consulte [nube híbrida](../solutions/cloud-architecture-models.md#hybrid).</span><span class="sxs-lookup"><span data-stu-id="73be1-110">For more information about hybrid environments, see [hybrid cloud](../solutions/cloud-architecture-models.md#hybrid).</span></span>

<span data-ttu-id="73be1-111">También puede usar los asesores de Azure Active Directory (Azure AD) para obtener instrucciones de configuración personalizadas en el centro de administración de Microsoft 365 (debe haber iniciado sesión en Microsoft 365):</span><span class="sxs-lookup"><span data-stu-id="73be1-111">You can also use the Azure Active Directory (Azure AD) advisors for customized setup guidance in the Microsoft 365 admin center (you must be signed in to Microsoft 365):</span></span>

- [<span data-ttu-id="73be1-112">Guía de configuración de Azure AD</span><span class="sxs-lookup"><span data-stu-id="73be1-112">Azure AD setup guide</span></span>](https://aka.ms/aadpguidance)
- [<span data-ttu-id="73be1-113">Sincronizar usuarios del directorio de su organización</span><span class="sxs-lookup"><span data-stu-id="73be1-113">Sync users from your org's directory</span></span>](https://aka.ms/aadconnectpwsync)
- [<span data-ttu-id="73be1-114">Asesor de implementación de servicios de Federación de Active Directory (AD FS)</span><span class="sxs-lookup"><span data-stu-id="73be1-114">Active Directory Federation Services (AD FS) deployment advisor</span></span>](https://aka.ms/adfsguidance)
   
## <a name="before-you-begin"></a><span data-ttu-id="73be1-115">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="73be1-115">Before you begin</span></span>

<span data-ttu-id="73be1-116">Antes de integrar Microsoft 365 y un entorno local, también debe realizar la [planeación de red y el ajuste del rendimiento](network-planning-and-performance.md).</span><span class="sxs-lookup"><span data-stu-id="73be1-116">Before you integrate Microsoft 365 and an on-premises environment, you also need to do [network planning and performance tuning](network-planning-and-performance.md).</span></span> <span data-ttu-id="73be1-117">También le interesará conocer los modelos de [identidad](about-microsoft-365-identity.md)disponibles.</span><span class="sxs-lookup"><span data-stu-id="73be1-117">You will also want to understand the available [identity models](about-microsoft-365-identity.md).</span></span> 

<span data-ttu-id="73be1-118">Consulte [Manage microsoft 365 accounts](manage-microsoft-365-accounts.md) para obtener una lista de las herramientas que puede usar para administrar las cuentas de usuario de 365 de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="73be1-118">See [manage Microsoft 365 accounts](manage-microsoft-365-accounts.md) for a list of tools you can use to manage Microsoft 365 user accounts.</span></span> 
  
## <a name="integrate-microsoft-365-with-ad-ds"></a><span data-ttu-id="73be1-119">Integración de Microsoft 365 con AD DS</span><span class="sxs-lookup"><span data-stu-id="73be1-119">Integrate Microsoft 365 with AD DS</span></span>

<span data-ttu-id="73be1-120">Si tiene cuentas de usuario existentes en AD DS, no desea volver a crear todas las cuentas en Microsoft 365 y arriesgarse a introducir diferencias o errores entre los entornos.</span><span class="sxs-lookup"><span data-stu-id="73be1-120">If you have existing user accounts in AD DS, you don't want to re-create all of those accounts in Microsoft 365 and risk introducing differences or errors between the environments.</span></span> <span data-ttu-id="73be1-121">La sincronización de directorios le ayuda a reflejar esas cuentas entre su entorno local y el entorno en línea.</span><span class="sxs-lookup"><span data-stu-id="73be1-121">Directory synchronization helps you mirror those accounts between your on-premises and online environments.</span></span> <span data-ttu-id="73be1-122">Con la sincronización de directorios, los usuarios no tienen que recordar nueva información para cada entorno y no es necesario crear o actualizar cuentas dos veces.</span><span class="sxs-lookup"><span data-stu-id="73be1-122">With directory synchronization, your users don't have to remember new information for each environment, and you don't have to create or update accounts twice.</span></span> <span data-ttu-id="73be1-123">Tendrá que [preparar el directorio local para la](prepare-for-directory-synchronization.md) sincronización de directorios.</span><span class="sxs-lookup"><span data-stu-id="73be1-123">You will need to [prepare your on-premises directory](prepare-for-directory-synchronization.md) for directory synchronization.</span></span>
  
![Usar la sincronización de directorios para mantener sincronizada la información de cuenta de usuario local y en línea](../media/microsoft-365-integration/directory-synchronization.png)
  
<span data-ttu-id="73be1-125">Si desea que los usuarios puedan iniciar sesión en Microsoft 365 con sus credenciales locales, también puede configurar el SSO.</span><span class="sxs-lookup"><span data-stu-id="73be1-125">If you want users to be able to log on to Microsoft 365 with their on-premises credentials, you can also configure SSO.</span></span> <span data-ttu-id="73be1-126">Con SSO, Microsoft 365 está configurado para confiar en el entorno local para la autenticación de usuarios.</span><span class="sxs-lookup"><span data-stu-id="73be1-126">With SSO, Microsoft 365 is configured to trust the on-premises environment for user authentication.</span></span>
  
![Con el inicio de sesión único, la misma cuenta está disponible tanto en el entorno local como en el en línea.](../media/microsoft-365-integration/single-sign-on.png)

### <a name="directory-synchronization-with-or-without-password-hash-synchronization-or-pass-through-authentication-pta"></a><span data-ttu-id="73be1-128">Sincronización de directorios con o sin sincronización de hash de contraseña o autenticación de paso a través (PTA)</span><span class="sxs-lookup"><span data-stu-id="73be1-128">Directory synchronization with or without password hash synchronization or pass-through authentication (PTA)</span></span>

<span data-ttu-id="73be1-129">Un usuario inicia sesión en su entorno local con su cuenta de usuario (dominio\nombre de usuario).</span><span class="sxs-lookup"><span data-stu-id="73be1-129">A user logs on to their on-premises environment with their user account (domain\username).</span></span> <span data-ttu-id="73be1-130">Cuando vayan a Microsoft 365, deben volver a iniciar sesión con su cuenta profesional o educativa (user@domain.com).</span><span class="sxs-lookup"><span data-stu-id="73be1-130">When they go to Microsoft 365, they must log on again with their work or school account (user@domain.com).</span></span> <span data-ttu-id="73be1-131">El nombre de usuario es el mismo en ambos entornos.</span><span class="sxs-lookup"><span data-stu-id="73be1-131">The user name is the same in both environments.</span></span> <span data-ttu-id="73be1-132">Cuando se agrega PHS o PTA, el usuario tiene la misma contraseña para ambos entornos, pero tendrá que volver a escribir las credenciales al iniciar sesión en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="73be1-132">When you add PHS or PTA, the user has the same password for both environments, but will have to provide those credentials again when logging on to Microsoft 365.</span></span> <span data-ttu-id="73be1-133">La sincronización de directorios con PHS es la sincronización de directorios que se usa con más frecuencia.</span><span class="sxs-lookup"><span data-stu-id="73be1-133">Directory synchronization with PHS is the most commonly used directory synchronization .</span></span>

<span data-ttu-id="73be1-134">Para configurar la sincronización de directorios, use Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="73be1-134">To set up directory synchronization, use Azure AD Connect.</span></span> <span data-ttu-id="73be1-135">Para obtener instrucciones, consulte [configurar la sincronización de directorios para Microsoft 365](set-up-directory-synchronization.md) y [Azure ad Connect con la configuración rápida](https://go.microsoft.com/fwlink/p/?LinkId=698537).</span><span class="sxs-lookup"><span data-stu-id="73be1-135">For instructions, see [Set up directory synchronization for Microsoft 365](set-up-directory-synchronization.md) and [Azure AD Connect with express settings](https://go.microsoft.com/fwlink/p/?LinkId=698537).</span></span>

<span data-ttu-id="73be1-136">Obtenga más información sobre la [preparación para la sincronización de directorios en Microsoft 365](prepare-for-directory-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="73be1-136">Learn more about [preparing for directory synchronization to Microsoft 365](prepare-for-directory-synchronization.md).</span></span>

### <a name="directory-synchronization-with-sso"></a><span data-ttu-id="73be1-137">Sincronización de directorios con SSO</span><span class="sxs-lookup"><span data-stu-id="73be1-137">Directory synchronization with SSO</span></span>

<span data-ttu-id="73be1-138">Un usuario inicia sesión en su entorno local con su cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="73be1-138">A user logs on to their on-premises environment with their user account.</span></span> <span data-ttu-id="73be1-139">Cuando van a Microsoft 365, inician sesión automáticamente o inician sesión con las mismas credenciales que usan para su entorno local (dominio\nombre de usuario).</span><span class="sxs-lookup"><span data-stu-id="73be1-139">When they go to Microsoft 365, they are either logged on automatically, or they log on using the same credentials they use for their on-premises environment (domain\username).</span></span>

<span data-ttu-id="73be1-140">Para configurar el SSO, también puede usar Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="73be1-140">To set up SSO you also use Azure AD Connect.</span></span> <span data-ttu-id="73be1-141">Para obtener instrucciones, consulte [instalación personalizada de Azure ad Connect](https://go.microsoft.com/fwlink/p/?LinkID=698430).</span><span class="sxs-lookup"><span data-stu-id="73be1-141">For instructions, see [Custom installation of Azure AD Connect](https://go.microsoft.com/fwlink/p/?LinkID=698430).</span></span>

<span data-ttu-id="73be1-142">Para obtener más información, consulte [Inicio de sesión único (Single Sign-on)](https://go.microsoft.com/fwlink/p/?LinkId=698604).</span><span class="sxs-lookup"><span data-stu-id="73be1-142">For more information, see [single sign-on](https://go.microsoft.com/fwlink/p/?LinkId=698604).</span></span>

## <a name="azure-ad-connect"></a><span data-ttu-id="73be1-143">Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="73be1-143">Azure AD Connect</span></span>

<span data-ttu-id="73be1-144">Azure AD Connect reemplaza versiones antiguas de herramientas de integración de identidades, como DirSync y sincronización de Azure AD. Si quiere actualizar desde Azure Active Directory Sync a Azure AD Connect, consulte [las instrucciones de actualización](https://go.microsoft.com/fwlink/p/?LinkId=733240).</span><span class="sxs-lookup"><span data-stu-id="73be1-144">Azure AD Connect replaces older versions of identity integration tools such as DirSync and Azure AD Sync. If you want to update from Azure Active Directory Sync to Azure AD Connect, see [the upgrade instructions](https://go.microsoft.com/fwlink/p/?LinkId=733240).</span></span> 

## <a name="see-also"></a><span data-ttu-id="73be1-145">Consulte también</span><span class="sxs-lookup"><span data-stu-id="73be1-145">See also</span></span>

[<span data-ttu-id="73be1-146">Información general de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="73be1-146">Microsoft 365 Enterprise overview</span></span>](microsoft-365-overview.md)
