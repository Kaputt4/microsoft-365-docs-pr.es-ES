---
title: Microsoft 365 modelos de identidad y Azure Active Directory
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
description: Obtenga información sobre cómo administrar el servicio de identidad de usuario de Azure AD en Microsoft 365 modelos de identidad híbrida o solo en la nube.
ms.openlocfilehash: b54ccce6ea2a468e02d9db95e7932d847df4e64b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905709"
---
# <a name="microsoft-365-identity-models-and-azure-active-directory"></a><span data-ttu-id="e0153-103">Microsoft 365 modelos de identidad y Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="e0153-103">Microsoft 365 identity models and Azure Active Directory</span></span>

<span data-ttu-id="e0153-104">*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="e0153-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="e0153-105">Microsoft 365 usa Azure Active Directory (Azure AD), un servicio de autenticación y identidad de usuario basado en la nube que se incluye con la suscripción Microsoft 365, para administrar identidades y autenticación para Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e0153-105">Microsoft 365 uses Azure Active Directory (Azure AD), a cloud-based user identity and authentication service that is included with your Microsoft 365 subscription, to manage identities and authentication for Microsoft 365.</span></span> <span data-ttu-id="e0153-106">La configuración correcta de la infraestructura de identidad es fundamental para administrar Microsoft 365 acceso de usuario y permisos para la organización.</span><span class="sxs-lookup"><span data-stu-id="e0153-106">Getting your identity infrastructure configured correctly is vital to managing Microsoft 365 user access and permissions for your organization.</span></span>

<span data-ttu-id="e0153-107">Antes de empezar, vea este vídeo para obtener una introducción a los modelos de identidad y autenticación de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e0153-107">Before you begin, watch this video for an overview of identity models and authentication for Microsoft 365.</span></span>

<span data-ttu-id="e0153-108"><p> </p></span><span class="sxs-lookup"><span data-stu-id="e0153-108"><p> </p></span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2Pjwu]

<span data-ttu-id="e0153-109">La primera opción de planeación es Microsoft 365 de identidad.</span><span class="sxs-lookup"><span data-stu-id="e0153-109">Your first planning choice is the Microsoft 365 identity model.</span></span>

## <a name="microsoft-365-identity-models"></a><span data-ttu-id="e0153-110">Microsoft 365 de identidad</span><span class="sxs-lookup"><span data-stu-id="e0153-110">Microsoft 365 identity models</span></span>

<span data-ttu-id="e0153-111">Para planear las cuentas de usuario, primero debe comprender los dos modelos de identidad en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e0153-111">To plan for user accounts, you first need to understand the two identity models in Microsoft 365.</span></span> <span data-ttu-id="e0153-112">Puede mantener las identidades de su organización solo en la nube, o puede mantener sus identidades locales de Servicios de dominio de Active Directory (AD DS) y usarlas para la autenticación cuando los usuarios tienen acceso Microsoft 365 servicios en la nube.</span><span class="sxs-lookup"><span data-stu-id="e0153-112">You can maintain your organization's identities only in the cloud, or you can maintain your on-premises Active Directory Domain Services (AD DS) identities and use them for authentication when users access Microsoft 365 cloud services.</span></span>  

<span data-ttu-id="e0153-113">Estos son los dos tipos de identidad y su mejor ajuste y ventajas.</span><span class="sxs-lookup"><span data-stu-id="e0153-113">Here are the two types of identity and their best fit and benefits.</span></span>

| <span data-ttu-id="e0153-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="e0153-114">Attribute</span></span> | <span data-ttu-id="e0153-115">Identidad solo de nube</span><span class="sxs-lookup"><span data-stu-id="e0153-115">Cloud-only identity</span></span> | <span data-ttu-id="e0153-116">Identidad híbrida</span><span class="sxs-lookup"><span data-stu-id="e0153-116">Hybrid identity</span></span> |
|:-------|:-----|:-----|
| <span data-ttu-id="e0153-117">**Definición**</span><span class="sxs-lookup"><span data-stu-id="e0153-117">**Definition**</span></span> | <span data-ttu-id="e0153-118">La cuenta de usuario solo existe en el inquilino de Azure AD para su Microsoft 365 suscripción.</span><span class="sxs-lookup"><span data-stu-id="e0153-118">User account only exists in the Azure AD tenant for your Microsoft 365 subscription.</span></span> | <span data-ttu-id="e0153-119">La cuenta de usuario existe en AD DS y también hay una copia en el inquilino de Azure AD para su Microsoft 365 suscripción.</span><span class="sxs-lookup"><span data-stu-id="e0153-119">User account exists in AD DS and a copy is also in the Azure AD tenant for your Microsoft 365 subscription.</span></span> <span data-ttu-id="e0153-120">La cuenta de usuario de Azure AD también puede incluir una versión hash de la contraseña de la cuenta de usuario de AD DS ya hash.</span><span class="sxs-lookup"><span data-stu-id="e0153-120">The user account in Azure AD might also include a hashed version of the already hashed AD DS user account password.</span></span> |
| <span data-ttu-id="e0153-121">**Cómo Microsoft 365 autentica las credenciales de usuario**</span><span class="sxs-lookup"><span data-stu-id="e0153-121">**How Microsoft 365 authenticates user credentials**</span></span> | <span data-ttu-id="e0153-122">El inquilino de Azure AD para la suscripción Microsoft 365 realiza la autenticación con la cuenta de identidad de la nube.</span><span class="sxs-lookup"><span data-stu-id="e0153-122">The Azure AD tenant for your Microsoft 365 subscription performs the authentication with the cloud identity account.</span></span> | <span data-ttu-id="e0153-123">El inquilino de Azure AD para la suscripción Microsoft 365 administra el proceso de autenticación o redirige al usuario a otro proveedor de identidades.</span><span class="sxs-lookup"><span data-stu-id="e0153-123">The Azure AD tenant for your Microsoft 365 subscription either handles the authentication process or redirects the user to another identity provider.</span></span> |
| <span data-ttu-id="e0153-124">**Ideal para**</span><span class="sxs-lookup"><span data-stu-id="e0153-124">**Best for**</span></span> | <span data-ttu-id="e0153-125">Organizaciones que no tienen o necesitan un AD DS local.</span><span class="sxs-lookup"><span data-stu-id="e0153-125">Organizations that do not have or need an on-premises AD DS.</span></span> | <span data-ttu-id="e0153-126">Organizaciones que usan AD DS u otro proveedor de identidades.</span><span class="sxs-lookup"><span data-stu-id="e0153-126">Organizations using AD DS or another identity provider.</span></span> |
| <span data-ttu-id="e0153-127">**Mayor beneficio**</span><span class="sxs-lookup"><span data-stu-id="e0153-127">**Greatest benefit**</span></span> | <span data-ttu-id="e0153-128">Fácil de usar.</span><span class="sxs-lookup"><span data-stu-id="e0153-128">Simple to use.</span></span> <span data-ttu-id="e0153-129">No se requieren servidores ni herramientas de directorio adicionales.</span><span class="sxs-lookup"><span data-stu-id="e0153-129">No extra directory tools or servers required.</span></span> | <span data-ttu-id="e0153-130">Los usuarios pueden usar las mismas credenciales al obtener acceso a recursos locales o basados en la nube.</span><span class="sxs-lookup"><span data-stu-id="e0153-130">Users can use the same credentials when accessing on-premises or cloud-based resources.</span></span> |
||||

## <a name="cloud-only-identity"></a><span data-ttu-id="e0153-131">Identidad solo de nube</span><span class="sxs-lookup"><span data-stu-id="e0153-131">Cloud-only identity</span></span>

<span data-ttu-id="e0153-132">Una identidad solo en la nube usa cuentas de usuario que solo existen en Azure AD.</span><span class="sxs-lookup"><span data-stu-id="e0153-132">A cloud-only identity uses user accounts that exist only in Azure AD.</span></span> <span data-ttu-id="e0153-133">La identidad de solo nube suele ser usada por organizaciones pequeñas que no tienen servidores locales o que no usan AD DS para administrar identidades locales.</span><span class="sxs-lookup"><span data-stu-id="e0153-133">Cloud-only identity is typically used by small organizations that do not have on-premises servers or do not use AD DS to manage local identities.</span></span> 

<span data-ttu-id="e0153-134">Estos son los componentes básicos de la identidad de solo nube.</span><span class="sxs-lookup"><span data-stu-id="e0153-134">Here are the basic components of cloud-only identity.</span></span>
 
![Componentes básicos de identidad de solo nube](../media/about-microsoft-365-identity/cloud-only-identity.png)

<span data-ttu-id="e0153-136">Tanto los usuarios locales como los remotos (en línea) usan sus cuentas de usuario y contraseñas de Azure AD para acceder a Microsoft 365 servicios en la nube.</span><span class="sxs-lookup"><span data-stu-id="e0153-136">Both on-premises and remote (online) users use their Azure AD user accounts and passwords to access Microsoft 365 cloud services.</span></span> <span data-ttu-id="e0153-137">Azure AD autentica las credenciales de usuario en función de sus cuentas de usuario y contraseñas almacenadas.</span><span class="sxs-lookup"><span data-stu-id="e0153-137">Azure AD authenticates user credentials based on its stored user accounts and passwords.</span></span>

### <a name="administration"></a><span data-ttu-id="e0153-138">Administración</span><span class="sxs-lookup"><span data-stu-id="e0153-138">Administration</span></span>
<span data-ttu-id="e0153-139">Dado que las cuentas de usuario solo se almacenan en [](../admin/add-users/index.yml) Azure AD, se administran identidades en la nube con herramientas como el centro de administración de Microsoft 365 y [Windows PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="e0153-139">Because user accounts are only stored in Azure AD, you manage cloud identities with tools such as the [Microsoft 365 admin center](../admin/add-users/index.yml) and [Windows PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md).</span></span> 

## <a name="hybrid-identity"></a><span data-ttu-id="e0153-140">Identidad híbrida</span><span class="sxs-lookup"><span data-stu-id="e0153-140">Hybrid identity</span></span>

<span data-ttu-id="e0153-141">La identidad híbrida usa cuentas que se originan en un AD DS local y tienen una copia en el inquilino de Azure AD de una Microsoft 365 suscripción.</span><span class="sxs-lookup"><span data-stu-id="e0153-141">Hybrid identity uses accounts that originate in an on-premises AD DS and have a copy in the Azure AD tenant of a Microsoft 365 subscription.</span></span> <span data-ttu-id="e0153-142">Sin embargo, la mayoría de los cambios solo fluyen de un modo.</span><span class="sxs-lookup"><span data-stu-id="e0153-142">However, most changes only flow one way.</span></span> <span data-ttu-id="e0153-143">Los cambios realizados en cuentas de usuario de AD DS se sincronizan con su copia en Azure AD.</span><span class="sxs-lookup"><span data-stu-id="e0153-143">Changes that you make to AD DS user accounts are synchronized to their copy in Azure AD.</span></span> <span data-ttu-id="e0153-144">Pero los cambios realizados en cuentas basadas en la nube en Azure AD, como las cuentas de usuario nuevas, no se sincronizan con AD DS.</span><span class="sxs-lookup"><span data-stu-id="e0153-144">But changes made to cloud-based accounts in Azure AD, such as new user accounts, are not synchronized with AD DS.</span></span>

<span data-ttu-id="e0153-145">Azure AD Conectar proporciona la sincronización de cuentas en curso.</span><span class="sxs-lookup"><span data-stu-id="e0153-145">Azure AD Connect provides the ongoing account synchronization.</span></span> <span data-ttu-id="e0153-146">Se ejecuta en un servidor local, comprueba si hay cambios en AD DS y reenvía esos cambios a Azure AD.</span><span class="sxs-lookup"><span data-stu-id="e0153-146">It runs on an on-premises server, checks for changes in the AD DS, and forwards those changes to Azure AD.</span></span> <span data-ttu-id="e0153-147">Azure AD Conectar permite filtrar qué cuentas están sincronizadas y si se sincroniza una versión hash de contraseñas de usuario, conocida como sincronización de hash de contraseña (PHS).</span><span class="sxs-lookup"><span data-stu-id="e0153-147">Azure AD Connect provides the ability to filter which accounts are synchronized and whether to synchronize a hashed version of user passwords, known as password hash synchronization (PHS).</span></span>

<span data-ttu-id="e0153-148">Al implementar la identidad híbrida, su AD DS local es el origen autoritativo para la información de la cuenta.</span><span class="sxs-lookup"><span data-stu-id="e0153-148">When you implement hybrid identity, your on-premises AD DS is the authoritative source for account information.</span></span> <span data-ttu-id="e0153-149">Esto significa que realiza tareas de administración principalmente locales, que luego se sincronizan con Azure AD.</span><span class="sxs-lookup"><span data-stu-id="e0153-149">This means that you perform administration tasks mostly on-premises, which are then synchronized to Azure AD.</span></span> 

<span data-ttu-id="e0153-150">Estos son los componentes de la identidad híbrida.</span><span class="sxs-lookup"><span data-stu-id="e0153-150">Here are the components of hybrid identity.</span></span>

![Componentes de identidad híbrida](../media/about-microsoft-365-identity/hybrid-identity.png)

<span data-ttu-id="e0153-152">El inquilino de Azure AD tiene una copia de las cuentas de AD DS.</span><span class="sxs-lookup"><span data-stu-id="e0153-152">The Azure AD tenant has a copy of the AD DS accounts.</span></span> <span data-ttu-id="e0153-153">En esta configuración, los usuarios locales y remotos que acceden a Microsoft 365 servicios en la nube se autentican en Azure AD.</span><span class="sxs-lookup"><span data-stu-id="e0153-153">In this configuration, both on-premises and remote users accessing Microsoft 365 cloud services authenticate against Azure AD.</span></span>

>[!Note]
><span data-ttu-id="e0153-154">Siempre debe usar Azure AD Conectar para sincronizar cuentas de usuario para la identidad híbrida.</span><span class="sxs-lookup"><span data-stu-id="e0153-154">You always need to use Azure AD Connect to synchronize user accounts for hybrid identity.</span></span> <span data-ttu-id="e0153-155">Necesita las cuentas de usuario sincronizadas en Azure AD para realizar la asignación de licencias y la administración de grupos, configurar permisos y otras tareas administrativas que impliquen cuentas de usuario.</span><span class="sxs-lookup"><span data-stu-id="e0153-155">You need the synchronized user accounts in Azure AD to perform license assignment and group management, configure permissions, and other administrative tasks that involve user accounts.</span></span>
>

### <a name="administration"></a><span data-ttu-id="e0153-156">Administración</span><span class="sxs-lookup"><span data-stu-id="e0153-156">Administration</span></span>

<span data-ttu-id="e0153-157">Dado que las cuentas de usuario originales y autoritativa se almacenan en el AD DS local, administra las identidades con las mismas herramientas que administra ad DS.</span><span class="sxs-lookup"><span data-stu-id="e0153-157">Because the original and authoritative user accounts are stored in the on-premises AD DS, you manage your identities with the same tools as you manage your AD DS.</span></span> 

<span data-ttu-id="e0153-158">No use el Centro de administración Microsoft 365 o PowerShell para Microsoft 365 administrar cuentas de usuario sincronizadas en Azure AD.</span><span class="sxs-lookup"><span data-stu-id="e0153-158">You don't use the Microsoft 365 admin center or PowerShell for Microsoft 365 to manage synchronized user accounts in Azure AD.</span></span>

## <a name="next-step"></a><span data-ttu-id="e0153-159">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="e0153-159">Next step</span></span>

<span data-ttu-id="e0153-160">Si necesita el modelo de identidad solo en la nube, consulte [Cloud-only identity](cloud-only-identities.md).</span><span class="sxs-lookup"><span data-stu-id="e0153-160">If you need the cloud-only identity model, see [Cloud-only identity](cloud-only-identities.md).</span></span>

<span data-ttu-id="e0153-161">Si necesita el modelo de identidad híbrida, vea [Identidad híbrida](plan-for-directory-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="e0153-161">If you need the hybrid identity model, see [Hybrid identity](plan-for-directory-synchronization.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="e0153-162">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e0153-162">See also</span></span>

[<span data-ttu-id="e0153-163">Información general de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="e0153-163">Microsoft 365 Enterprise overview</span></span>](microsoft-365-overview.md)