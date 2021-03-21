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
description: En este artículo, obtenga información sobre cómo integrar Microsoft 365 con los servicios de directorio existentes y los entornos locales.
ms.openlocfilehash: c0453b7685254ccbbb301a17749fe48549fae78d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923971"
---
# <a name="microsoft-365-integration-with-on-premises-environments"></a><span data-ttu-id="b4fca-103">Integración de Microsoft 365 con entornos locales</span><span class="sxs-lookup"><span data-stu-id="b4fca-103">Microsoft 365 integration with on-premises environments</span></span>

<span data-ttu-id="b4fca-104">*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="b4fca-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="b4fca-105">Puede integrar Microsoft 365 con los Servicios de dominio de Active Directory (AD DS) locales existentes y con instalaciones locales de Exchange Server, Skype Empresarial Server 2015 o SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="b4fca-105">You can integrate Microsoft 365 with your existing on-premises Active Directory Domain Services (AD DS) and with on-premises installations of Exchange Server, Skype for Business Server 2015, or SharePoint Server.</span></span>
  
 - <span data-ttu-id="b4fca-106">Al integrar AD DS, puedes sincronizar y administrar cuentas de usuario para ambos entornos.</span><span class="sxs-lookup"><span data-stu-id="b4fca-106">When you integrate AD DS, you can synchronize and manage user accounts for both environments.</span></span> <span data-ttu-id="b4fca-107">También puede agregar sincronización de hash de contraseña (PHS) o inicio de sesión único (SSO) para que los usuarios puedan iniciar sesión en ambos entornos con sus credenciales locales.</span><span class="sxs-lookup"><span data-stu-id="b4fca-107">You can also add password hash synchronization (PHS) or single sign-on (SSO) so users can log on to both environments with their on-premises credentials.</span></span>
 - <span data-ttu-id="b4fca-108">Cuando se integra con productos de servidor locales, se crea un entorno híbrido.</span><span class="sxs-lookup"><span data-stu-id="b4fca-108">When you integrate with on-premises server products, you create a hybrid environment.</span></span> <span data-ttu-id="b4fca-109">Un entorno híbrido puede ayudar a migrar usuarios o información a Microsoft 365, o puede seguir teniendo algunos usuarios o información local y otras en la nube.</span><span class="sxs-lookup"><span data-stu-id="b4fca-109">A hybrid environment can help as you migrate users or information to Microsoft 365, or you can continue to have some users or some information on-premises and some in the cloud.</span></span> <span data-ttu-id="b4fca-110">Para obtener más información acerca de los entornos híbridos, vea [hybrid cloud](../solutions/cloud-architecture-models.md#hybrid).</span><span class="sxs-lookup"><span data-stu-id="b4fca-110">For more information about hybrid environments, see [hybrid cloud](../solutions/cloud-architecture-models.md#hybrid).</span></span>

<span data-ttu-id="b4fca-111">También puede usar los asesores de Azure Active Directory (Azure AD) para obtener instrucciones de configuración personalizadas en el Centro de administración de Microsoft 365 (debe haber iniciado sesión en Microsoft 365):</span><span class="sxs-lookup"><span data-stu-id="b4fca-111">You can also use the Azure Active Directory (Azure AD) advisors for customized setup guidance in the Microsoft 365 admin center (you must be signed in to Microsoft 365):</span></span>

- [<span data-ttu-id="b4fca-112">Guía de configuración de Azure AD</span><span class="sxs-lookup"><span data-stu-id="b4fca-112">Azure AD setup guide</span></span>](https://aka.ms/aadpguidance)
- [<span data-ttu-id="b4fca-113">Sincronizar usuarios desde el directorio de la organización</span><span class="sxs-lookup"><span data-stu-id="b4fca-113">Sync users from your org's directory</span></span>](https://aka.ms/aadconnectpwsync)
- [<span data-ttu-id="b4fca-114">Asesor de implementación de Servicios de federación de Active Directory (AD FS)</span><span class="sxs-lookup"><span data-stu-id="b4fca-114">Active Directory Federation Services (AD FS) deployment advisor</span></span>](https://aka.ms/adfsguidance)
   
## <a name="before-you-begin"></a><span data-ttu-id="b4fca-115">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="b4fca-115">Before you begin</span></span>

<span data-ttu-id="b4fca-116">Antes de integrar Microsoft 365 y un entorno local, también debe realizar la planeación de red y [el ajuste del rendimiento.](network-planning-and-performance.md)</span><span class="sxs-lookup"><span data-stu-id="b4fca-116">Before you integrate Microsoft 365 and an on-premises environment, you also need to do [network planning and performance tuning](network-planning-and-performance.md).</span></span> <span data-ttu-id="b4fca-117">También querrá comprender los modelos de [identidad disponibles.](about-microsoft-365-identity.md)</span><span class="sxs-lookup"><span data-stu-id="b4fca-117">You will also want to understand the available [identity models](about-microsoft-365-identity.md).</span></span> 

<span data-ttu-id="b4fca-118">Consulta [administrar cuentas de Microsoft 365](manage-microsoft-365-accounts.md) para obtener una lista de las herramientas que puedes usar para administrar cuentas de usuario de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b4fca-118">See [manage Microsoft 365 accounts](manage-microsoft-365-accounts.md) for a list of tools you can use to manage Microsoft 365 user accounts.</span></span> 
  
## <a name="integrate-microsoft-365-with-ad-ds"></a><span data-ttu-id="b4fca-119">Integrar Microsoft 365 con AD DS</span><span class="sxs-lookup"><span data-stu-id="b4fca-119">Integrate Microsoft 365 with AD DS</span></span>

<span data-ttu-id="b4fca-120">Si tienes cuentas de usuario existentes en AD DS, no quieres volver a crear todas esas cuentas en Microsoft 365 y te arriesgas a introducir diferencias o errores entre los entornos.</span><span class="sxs-lookup"><span data-stu-id="b4fca-120">If you have existing user accounts in AD DS, you don't want to re-create all of those accounts in Microsoft 365 and risk introducing differences or errors between the environments.</span></span> <span data-ttu-id="b4fca-121">La sincronización de directorios le ayuda a reflejar esas cuentas entre sus entornos locales y en línea.</span><span class="sxs-lookup"><span data-stu-id="b4fca-121">Directory synchronization helps you mirror those accounts between your on-premises and online environments.</span></span> <span data-ttu-id="b4fca-122">Con la sincronización de directorios, los usuarios no tienen que recordar información nueva para cada entorno y no tiene que crear o actualizar cuentas dos veces.</span><span class="sxs-lookup"><span data-stu-id="b4fca-122">With directory synchronization, your users don't have to remember new information for each environment, and you don't have to create or update accounts twice.</span></span> <span data-ttu-id="b4fca-123">Deberá preparar el [directorio local](prepare-for-directory-synchronization.md) para la sincronización de directorios.</span><span class="sxs-lookup"><span data-stu-id="b4fca-123">You will need to [prepare your on-premises directory](prepare-for-directory-synchronization.md) for directory synchronization.</span></span>
  
![Usar la sincronización de directorios para mantener sincronizada la información de cuenta de usuario local y en línea](../media/microsoft-365-integration/directory-synchronization.png)
  
<span data-ttu-id="b4fca-125">Si desea que los usuarios puedan iniciar sesión en Microsoft 365 con sus credenciales locales, también puede configurar SSO.</span><span class="sxs-lookup"><span data-stu-id="b4fca-125">If you want users to be able to log on to Microsoft 365 with their on-premises credentials, you can also configure SSO.</span></span> <span data-ttu-id="b4fca-126">Con SSO, Microsoft 365 está configurado para confiar en el entorno local para la autenticación de usuario.</span><span class="sxs-lookup"><span data-stu-id="b4fca-126">With SSO, Microsoft 365 is configured to trust the on-premises environment for user authentication.</span></span>
  
![Con el inicio de sesión único, la misma cuenta está disponible en los entornos locales y en línea](../media/microsoft-365-integration/single-sign-on.png)

### <a name="directory-synchronization-with-or-without-password-hash-synchronization-or-pass-through-authentication-pta"></a><span data-ttu-id="b4fca-128">Sincronización de directorios con o sin sincronización de hash de contraseña o autenticación de paso a través (PTA)</span><span class="sxs-lookup"><span data-stu-id="b4fca-128">Directory synchronization with or without password hash synchronization or pass-through authentication (PTA)</span></span>

<span data-ttu-id="b4fca-129">Un usuario inicia sesión en su entorno local con su cuenta de usuario (dominio\nombredeusuario).</span><span class="sxs-lookup"><span data-stu-id="b4fca-129">A user logs on to their on-premises environment with their user account (domain\username).</span></span> <span data-ttu-id="b4fca-130">Cuando vayan a Microsoft 365, deben iniciar sesión de nuevo con su cuenta laboral o educativa (user@domain.com).</span><span class="sxs-lookup"><span data-stu-id="b4fca-130">When they go to Microsoft 365, they must log on again with their work or school account (user@domain.com).</span></span> <span data-ttu-id="b4fca-131">El nombre de usuario es el mismo en ambos entornos.</span><span class="sxs-lookup"><span data-stu-id="b4fca-131">The user name is the same in both environments.</span></span> <span data-ttu-id="b4fca-132">Al agregar PHS o PTA, el usuario tiene la misma contraseña para ambos entornos, pero tendrá que proporcionar esas credenciales de nuevo al iniciar sesión en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b4fca-132">When you add PHS or PTA, the user has the same password for both environments, but will have to provide those credentials again when logging on to Microsoft 365.</span></span> <span data-ttu-id="b4fca-133">La sincronización de directorios con PHS es la sincronización de directorios más usada.</span><span class="sxs-lookup"><span data-stu-id="b4fca-133">Directory synchronization with PHS is the most commonly used directory synchronization .</span></span>

<span data-ttu-id="b4fca-134">Para configurar la sincronización de directorios, use Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="b4fca-134">To set up directory synchronization, use Azure AD Connect.</span></span> <span data-ttu-id="b4fca-135">Para obtener instrucciones, consulte Configurar la sincronización [de directorios para Microsoft 365](set-up-directory-synchronization.md) y [Azure AD Connect con configuración express.](/azure/active-directory/hybrid/how-to-connect-install-express)</span><span class="sxs-lookup"><span data-stu-id="b4fca-135">For instructions, see [Set up directory synchronization for Microsoft 365](set-up-directory-synchronization.md) and [Azure AD Connect with express settings](/azure/active-directory/hybrid/how-to-connect-install-express).</span></span>

<span data-ttu-id="b4fca-136">Obtenga más información [sobre cómo preparar la sincronización de directorios con Microsoft 365](prepare-for-directory-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="b4fca-136">Learn more about [preparing for directory synchronization to Microsoft 365](prepare-for-directory-synchronization.md).</span></span>

### <a name="directory-synchronization-with-sso"></a><span data-ttu-id="b4fca-137">Sincronización de directorios con SSO</span><span class="sxs-lookup"><span data-stu-id="b4fca-137">Directory synchronization with SSO</span></span>

<span data-ttu-id="b4fca-138">Un usuario inicia sesión en su entorno local con su cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="b4fca-138">A user logs on to their on-premises environment with their user account.</span></span> <span data-ttu-id="b4fca-139">Cuando van a Microsoft 365, inician sesión automáticamente o inician sesión con las mismas credenciales que usan para su entorno local (dominio\nombredeusuario).</span><span class="sxs-lookup"><span data-stu-id="b4fca-139">When they go to Microsoft 365, they are either logged on automatically, or they log on using the same credentials they use for their on-premises environment (domain\username).</span></span>

<span data-ttu-id="b4fca-140">Para configurar SSO, también usa Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="b4fca-140">To set up SSO you also use Azure AD Connect.</span></span> <span data-ttu-id="b4fca-141">Para obtener instrucciones, [consulte Instalación personalizada de Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-custom).</span><span class="sxs-lookup"><span data-stu-id="b4fca-141">For instructions, see [Custom installation of Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-custom).</span></span>

<span data-ttu-id="b4fca-142">Para obtener más información, [vea single sign-on](/azure/active-directory/manage-apps/what-is-single-sign-on).</span><span class="sxs-lookup"><span data-stu-id="b4fca-142">For more information, see [single sign-on](/azure/active-directory/manage-apps/what-is-single-sign-on).</span></span>

## <a name="azure-ad-connect"></a><span data-ttu-id="b4fca-143">Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="b4fca-143">Azure AD Connect</span></span>

<span data-ttu-id="b4fca-144">Azure AD Connect reemplaza las versiones anteriores de las herramientas de integración de identidades, como DirSync y Azure AD Sync. Si quieres actualizar de Azure Active Directory Sync a Azure AD Connect, consulta [las instrucciones de actualización](/azure/active-directory/hybrid/how-to-dirsync-upgrade-get-started).</span><span class="sxs-lookup"><span data-stu-id="b4fca-144">Azure AD Connect replaces older versions of identity integration tools such as DirSync and Azure AD Sync. If you want to update from Azure Active Directory Sync to Azure AD Connect, see [the upgrade instructions](/azure/active-directory/hybrid/how-to-dirsync-upgrade-get-started).</span></span> 

## <a name="see-also"></a><span data-ttu-id="b4fca-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="b4fca-145">See also</span></span>

[<span data-ttu-id="b4fca-146">Información general de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="b4fca-146">Microsoft 365 Enterprise overview</span></span>](microsoft-365-overview.md)