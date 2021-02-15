---
title: Modelos de identidad de Microsoft 365 y Azure Active Directory
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.date: 09/30/2020
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- M365-identity-device-management
- M365-security-compliance
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-mar2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 06a189e7-5ec6-4af2-94bf-a22ea225a7a9
description: Obtenga información sobre cómo administrar el servicio de identidad de usuario de Azure AD en Microsoft 365 con modelos de identidad híbridos o solo en la nube.
ms.openlocfilehash: 6b5b80584408671a1925e32df1fbf458b7c16139
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327956"
---
# <a name="microsoft-365-identity-models-and-azure-active-directory"></a><span data-ttu-id="a9862-103">Modelos de identidad de Microsoft 365 y Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="a9862-103">Microsoft 365 identity models and Azure Active Directory</span></span>

<span data-ttu-id="a9862-104">*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="a9862-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="a9862-105">Microsoft 365 usa Azure Active Directory (Azure AD), un servicio de autenticación e identidad de usuario basado en la nube que se incluye con su suscripción de Microsoft 365, para administrar las identidades y la autenticación de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a9862-105">Microsoft 365 uses Azure Active Directory (Azure AD), a cloud-based user identity and authentication service that is included with your Microsoft 365 subscription, to manage identities and authentication for Microsoft 365.</span></span> <span data-ttu-id="a9862-106">Configurar correctamente la infraestructura de identidades es fundamental para administrar los permisos y el acceso de usuarios de Microsoft 365 para su organización.</span><span class="sxs-lookup"><span data-stu-id="a9862-106">Getting your identity infrastructure configured correctly is vital to managing Microsoft 365 user access and permissions for your organization.</span></span>

<span data-ttu-id="a9862-107">Antes de empezar, vea este vídeo para obtener una introducción a los modelos de identidad y autenticación de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a9862-107">Before you begin, watch this video for an overview of identity models and authentication for Microsoft 365.</span></span>

<span data-ttu-id="a9862-108"><p> </p></span><span class="sxs-lookup"><span data-stu-id="a9862-108"><p> </p></span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2Pjwu]

<span data-ttu-id="a9862-109">La primera opción de planeación es el modelo de identidad de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a9862-109">Your first planning choice is the Microsoft 365 identity model.</span></span>

## <a name="microsoft-365-identity-models"></a><span data-ttu-id="a9862-110">Modelos de identidad de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a9862-110">Microsoft 365 identity models</span></span>

<span data-ttu-id="a9862-111">Para planear las cuentas de usuario, primero debe comprender los dos modelos de identidad en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a9862-111">To plan for user accounts, you first need to understand the two identity models in Microsoft 365.</span></span> <span data-ttu-id="a9862-112">Puede mantener las identidades de su organización solo en la nube o puede mantener sus identidades locales de Servicios de dominio de Active Directory (AD DS) y usarlas para la autenticación cuando los usuarios accedan a los servicios en la nube de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a9862-112">You can maintain your organization's identities only in the cloud, or you can maintain your on-premises Active Directory Domain Services (AD DS) identities and use them for authentication when users access Microsoft 365 cloud services.</span></span>  

<span data-ttu-id="a9862-113">Estos son los dos tipos de identidad y su mejor ajuste y ventajas.</span><span class="sxs-lookup"><span data-stu-id="a9862-113">Here are the two types of identity and their best fit and benefits.</span></span>

| <span data-ttu-id="a9862-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="a9862-114">Attribute</span></span> | <span data-ttu-id="a9862-115">Identidad solo de nube</span><span class="sxs-lookup"><span data-stu-id="a9862-115">Cloud-only identity</span></span> | <span data-ttu-id="a9862-116">Identidad híbrida</span><span class="sxs-lookup"><span data-stu-id="a9862-116">Hybrid identity</span></span> |
|:-------|:-----|:-----|
| <span data-ttu-id="a9862-117">**Definición**</span><span class="sxs-lookup"><span data-stu-id="a9862-117">**Definition**</span></span> | <span data-ttu-id="a9862-118">La cuenta de usuario solo existe en el inquilino de Azure AD para su suscripción a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a9862-118">User account only exists in the Azure AD tenant for your Microsoft 365 subscription.</span></span> | <span data-ttu-id="a9862-119">La cuenta de usuario existe en AD DS y también hay una copia en el inquilino de Azure AD para su suscripción a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a9862-119">User account exists in AD DS and a copy is also in the Azure AD tenant for your Microsoft 365 subscription.</span></span> <span data-ttu-id="a9862-120">La cuenta de usuario de Azure AD también puede incluir una versión con hash de la contraseña de la cuenta de usuario de AD DS ya con hash.</span><span class="sxs-lookup"><span data-stu-id="a9862-120">The user account in Azure AD might also include a hashed version of the already hashed AD DS user account password.</span></span> |
| <span data-ttu-id="a9862-121">**Cómo Autentica Microsoft 365 las credenciales de usuario**</span><span class="sxs-lookup"><span data-stu-id="a9862-121">**How Microsoft 365 authenticates user credentials**</span></span> | <span data-ttu-id="a9862-122">El inquilino de Azure AD para su suscripción de Microsoft 365 realiza la autenticación con la cuenta de identidad de la nube.</span><span class="sxs-lookup"><span data-stu-id="a9862-122">The Azure AD tenant for your Microsoft 365 subscription performs the authentication with the cloud identity account.</span></span> | <span data-ttu-id="a9862-123">El inquilino de Azure AD para su suscripción de Microsoft 365 controla el proceso de autenticación o redirige al usuario a otro proveedor de identidades.</span><span class="sxs-lookup"><span data-stu-id="a9862-123">The Azure AD tenant for your Microsoft 365 subscription either handles the authentication process or redirects the user to another identity provider.</span></span> |
| <span data-ttu-id="a9862-124">**Ideal para**</span><span class="sxs-lookup"><span data-stu-id="a9862-124">**Best for**</span></span> | <span data-ttu-id="a9862-125">Organizaciones que no tienen o necesitan un AD DS local.</span><span class="sxs-lookup"><span data-stu-id="a9862-125">Organizations that do not have or need an on-premises AD DS.</span></span> | <span data-ttu-id="a9862-126">Organizaciones que usan AD DS u otro proveedor de identidades.</span><span class="sxs-lookup"><span data-stu-id="a9862-126">Organizations using AD DS or another identity provider.</span></span> |
| <span data-ttu-id="a9862-127">**Mayor beneficio**</span><span class="sxs-lookup"><span data-stu-id="a9862-127">**Greatest benefit**</span></span> | <span data-ttu-id="a9862-128">Fácil de usar.</span><span class="sxs-lookup"><span data-stu-id="a9862-128">Simple to use.</span></span> <span data-ttu-id="a9862-129">No se necesitan más servidores ni herramientas de directorio.</span><span class="sxs-lookup"><span data-stu-id="a9862-129">No extra directory tools or servers required.</span></span> | <span data-ttu-id="a9862-130">Los usuarios pueden usar las mismas credenciales al obtener acceso a recursos locales o basados en la nube.</span><span class="sxs-lookup"><span data-stu-id="a9862-130">Users can use the same credentials when accessing on-premises or cloud-based resources.</span></span> |
||||

## <a name="cloud-only-identity"></a><span data-ttu-id="a9862-131">Identidad solo de nube</span><span class="sxs-lookup"><span data-stu-id="a9862-131">Cloud-only identity</span></span>

<span data-ttu-id="a9862-132">Una identidad solo de nube usa cuentas de usuario que solo existen en Azure AD.</span><span class="sxs-lookup"><span data-stu-id="a9862-132">A cloud-only identity uses user accounts that exist only in Azure AD.</span></span> <span data-ttu-id="a9862-133">La identidad solo en la nube se suele usar en organizaciones pequeñas que no tienen servidores locales o no usan AD DS para administrar identidades locales.</span><span class="sxs-lookup"><span data-stu-id="a9862-133">Cloud-only identity is typically used by small organizations that do not have on-premises servers or do not use AD DS to manage local identities.</span></span> 

<span data-ttu-id="a9862-134">Estos son los componentes básicos de la identidad de solo nube.</span><span class="sxs-lookup"><span data-stu-id="a9862-134">Here are the basic components of cloud-only identity.</span></span>
 
![Componentes básicos de identidad solo en la nube](../media/about-microsoft-365-identity/cloud-only-identity.png)

<span data-ttu-id="a9862-136">Tanto los usuarios locales como remotos (en línea) usan sus cuentas de usuario y contraseñas de Azure AD para acceder a los servicios en la nube de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a9862-136">Both on-premises and remote (online) users use their Azure AD user accounts and passwords to access Microsoft 365 cloud services.</span></span> <span data-ttu-id="a9862-137">Azure AD autentica las credenciales de usuario en función de sus contraseñas y cuentas de usuario almacenadas.</span><span class="sxs-lookup"><span data-stu-id="a9862-137">Azure AD authenticates user credentials based on its stored user accounts and passwords.</span></span>

### <a name="administration"></a><span data-ttu-id="a9862-138">Administración</span><span class="sxs-lookup"><span data-stu-id="a9862-138">Administration</span></span>
<span data-ttu-id="a9862-139">Dado que las cuentas de usuario solo se almacenan en Azure AD, las identidades de nube se administran con herramientas como el Centro de administración de [Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/add-users/) [y Windows PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="a9862-139">Because user accounts are only stored in Azure AD, you manage cloud identities with tools such as the [Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/add-users/) and [Windows PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md).</span></span> 

## <a name="hybrid-identity"></a><span data-ttu-id="a9862-140">Identidad híbrida</span><span class="sxs-lookup"><span data-stu-id="a9862-140">Hybrid identity</span></span>

<span data-ttu-id="a9862-141">La identidad híbrida usa cuentas que se originan en un AD DS local y tienen una copia en el inquilino de Azure AD de una suscripción de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a9862-141">Hybrid identity uses accounts that originate in an on-premises AD DS and have a copy in the Azure AD tenant of a Microsoft 365 subscription.</span></span> <span data-ttu-id="a9862-142">Sin embargo, la mayoría de los cambios solo fluyen de un modo.</span><span class="sxs-lookup"><span data-stu-id="a9862-142">However, most changes only flow one way.</span></span> <span data-ttu-id="a9862-143">Los cambios realizados en las cuentas de usuario de AD DS se sincronizan con su copia en Azure AD.</span><span class="sxs-lookup"><span data-stu-id="a9862-143">Changes that you make to AD DS user accounts are synchronized to their copy in Azure AD.</span></span> <span data-ttu-id="a9862-144">Pero los cambios realizados en las cuentas basadas en la nube en Azure AD, como las cuentas de usuario nuevas, no se sincronizan con AD DS.</span><span class="sxs-lookup"><span data-stu-id="a9862-144">But changes made to cloud-based accounts in Azure AD, such as new user accounts, are not synchronized with AD DS.</span></span>

<span data-ttu-id="a9862-145">Azure AD Connect proporciona la sincronización continua de cuentas.</span><span class="sxs-lookup"><span data-stu-id="a9862-145">Azure AD Connect provides the ongoing account synchronization.</span></span> <span data-ttu-id="a9862-146">Se ejecuta en un servidor local, comprueba si hay cambios en AD DS y reenvía esos cambios a Azure AD.</span><span class="sxs-lookup"><span data-stu-id="a9862-146">It runs on an on-premises server, checks for changes in the AD DS, and forwards those changes to Azure AD.</span></span> <span data-ttu-id="a9862-147">Azure AD Connect permite filtrar qué cuentas se sincronizan y si se sincroniza una versión con hash de contraseñas de usuario, conocida como sincronización de hash de contraseñas (PHS).</span><span class="sxs-lookup"><span data-stu-id="a9862-147">Azure AD Connect provides the ability to filter which accounts are synchronized and whether to synchronize a hashed version of user passwords, known as password hash synchronization (PHS).</span></span>

<span data-ttu-id="a9862-148">Al implementar la identidad híbrida, AD DS local es el origen autoritativo de la información de la cuenta.</span><span class="sxs-lookup"><span data-stu-id="a9862-148">When you implement hybrid identity, your on-premises AD DS is the authoritative source for account information.</span></span> <span data-ttu-id="a9862-149">Esto significa que se realizan tareas de administración principalmente locales, que luego se sincronizan con Azure AD.</span><span class="sxs-lookup"><span data-stu-id="a9862-149">This means that you perform administration tasks mostly on-premises, which are then synchronized to Azure AD.</span></span> 

<span data-ttu-id="a9862-150">Estos son los componentes de la identidad híbrida.</span><span class="sxs-lookup"><span data-stu-id="a9862-150">Here are the components of hybrid identity.</span></span>

![Componentes de identidad híbrida](../media/about-microsoft-365-identity/hybrid-identity.png)

<span data-ttu-id="a9862-152">El inquilino de Azure AD tiene una copia de las cuentas de AD DS.</span><span class="sxs-lookup"><span data-stu-id="a9862-152">The Azure AD tenant has a copy of the AD DS accounts.</span></span> <span data-ttu-id="a9862-153">En esta configuración, los usuarios locales y remotos que tienen acceso a los servicios en la nube de Microsoft 365 se autentican en Azure AD.</span><span class="sxs-lookup"><span data-stu-id="a9862-153">In this configuration, both on-premises and remote users accessing Microsoft 365 cloud services authenticate against Azure AD.</span></span>

>[!Note]
><span data-ttu-id="a9862-154">Siempre debe usar Azure AD Connect para sincronizar las cuentas de usuario para la identidad híbrida.</span><span class="sxs-lookup"><span data-stu-id="a9862-154">You always need to use Azure AD Connect to synchronize user accounts for hybrid identity.</span></span> <span data-ttu-id="a9862-155">Necesita las cuentas de usuario sincronizadas en Azure AD para realizar la asignación de licencias y la administración de grupos, configurar permisos y otras tareas administrativas relacionadas con las cuentas de usuario.</span><span class="sxs-lookup"><span data-stu-id="a9862-155">You need the synchronized user accounts in Azure AD to perform license assignment and group management, configure permissions, and other administrative tasks that involve user accounts.</span></span>
>

### <a name="administration"></a><span data-ttu-id="a9862-156">Administración</span><span class="sxs-lookup"><span data-stu-id="a9862-156">Administration</span></span>

<span data-ttu-id="a9862-157">Dado que las cuentas de usuario autoritativa y original se almacenan en ad DS local, las identidades se administran con las mismas herramientas que administra ad DS.</span><span class="sxs-lookup"><span data-stu-id="a9862-157">Because the original and authoritative user accounts are stored in the on-premises AD DS, you manage your identities with the same tools as you manage your AD DS.</span></span> 

<span data-ttu-id="a9862-158">No use el Centro de administración de Microsoft 365 ni PowerShell para Microsoft 365 para administrar cuentas de usuario sincronizadas en Azure AD.</span><span class="sxs-lookup"><span data-stu-id="a9862-158">You don't use the Microsoft 365 admin center or PowerShell for Microsoft 365 to manage synchronized user accounts in Azure AD.</span></span>

## <a name="next-step"></a><span data-ttu-id="a9862-159">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="a9862-159">Next step</span></span>

<span data-ttu-id="a9862-160">Si necesita el modelo de identidad solo de nube, consulte [Identidad solo de nube.](cloud-only-identities.md)</span><span class="sxs-lookup"><span data-stu-id="a9862-160">If you need the cloud-only identity model, see [Cloud-only identity](cloud-only-identities.md).</span></span>

<span data-ttu-id="a9862-161">Si necesita el modelo de identidad híbrida, consulte [Identidad híbrida.](plan-for-directory-synchronization.md)</span><span class="sxs-lookup"><span data-stu-id="a9862-161">If you need the hybrid identity model, see [Hybrid identity](plan-for-directory-synchronization.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="a9862-162">Vea también</span><span class="sxs-lookup"><span data-stu-id="a9862-162">See also</span></span>

[<span data-ttu-id="a9862-163">Información general de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="a9862-163">Microsoft 365 Enterprise overview</span></span>](microsoft-365-overview.md)
