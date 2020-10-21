---
title: Identidad para Contoso Corporation
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Cómo Contoso aprovecha la Identidad como servicio (IDaaS) y proporciona autenticación basada en la nube a sus empleados y autenticación federada a sus partners y clientes.
ms.openlocfilehash: 10db0a35024595c4dba9a33ad83ae75bcad3870c
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2020
ms.locfileid: "48637252"
---
# <a name="identity-for-the-contoso-corporation"></a><span data-ttu-id="3f750-103">Identidad para Contoso Corporation</span><span class="sxs-lookup"><span data-stu-id="3f750-103">Identity for the Contoso Corporation</span></span>

<span data-ttu-id="3f750-104">Microsoft proporciona identidad como un servicio (IDaaS) en todas sus ofertas de la nube a través de Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="3f750-104">Microsoft provides Identity as a Service (IDaaS) across its cloud offerings through Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="3f750-105">Para adoptar Microsoft 365 para empresas, la solución IDaaS de Contoso tuvo que usar su proveedor de identidades local e incluir la autenticación federada con sus proveedores de identidades de terceros de confianza existentes.</span><span class="sxs-lookup"><span data-stu-id="3f750-105">To adopt Microsoft 365 for enterprise, the Contoso IDaaS solution had to use their on-premises identity provider and include federated authentication with their existing trusted, third-party identity providers.</span></span>

## <a name="the-contoso-active-directory-domain-services-forest"></a><span data-ttu-id="3f750-106">El bosque de servicios de dominio de Active Directory de Contoso</span><span class="sxs-lookup"><span data-stu-id="3f750-106">The Contoso Active Directory Domain Services forest</span></span>

<span data-ttu-id="3f750-107">Contoso usa un solo bosque de servicios de dominio de Active Directory (AD DS) para contoso \. com con siete subdominios, uno para cada región del mundo.</span><span class="sxs-lookup"><span data-stu-id="3f750-107">Contoso uses a single Active Directory Domain Services (AD DS) forest for contoso\.com with seven subdomains, one for each region of the world.</span></span> <span data-ttu-id="3f750-108">La sede, las oficinas regionales y las oficinas satélite contienen controladores de dominio para la autenticación y la autorización local.</span><span class="sxs-lookup"><span data-stu-id="3f750-108">The headquarters, regional hub offices, and satellite offices contain domain controllers for local authentication and authorization.</span></span>

<span data-ttu-id="3f750-109">Este es el bosque de Contoso con dominios regionales para las distintas partes del mundo que contienen centros regionales.</span><span class="sxs-lookup"><span data-stu-id="3f750-109">Here's the Contoso forest with regional domains for the different parts of the world that contain regional hubs.</span></span>

![Bosque y dominios de Contoso en todo el mundo](../media/contoso-identity/contoso-identity-fig1.png)
 
<span data-ttu-id="3f750-111">Contoso decidió usar las cuentas y los grupos del \. bosque com de Contoso para la autenticación y autorización de sus cargas de trabajo y servicios de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3f750-111">Contoso decided to use the accounts and groups in the contoso\.com forest for authentication and authorization for its Microsoft 365 workloads and services.</span></span>

## <a name="the-contoso-federated-authentication-infrastructure"></a><span data-ttu-id="3f750-112">La infraestructura de autenticación federada de Contoso</span><span class="sxs-lookup"><span data-stu-id="3f750-112">The Contoso federated authentication infrastructure</span></span>

<span data-ttu-id="3f750-113">Contoso permite lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3f750-113">Contoso allows:</span></span>

- <span data-ttu-id="3f750-114">Los clientes usen sus cuentas de Microsoft, Facebook o Google Mail para iniciar sesión en el sitio web público de la compañía.</span><span class="sxs-lookup"><span data-stu-id="3f750-114">Customers to use their Microsoft, Facebook, or Google Mail accounts to sign in to the company's public web site.</span></span>
- <span data-ttu-id="3f750-115">Proveedores y partners para usar sus cuentas de LinkedIn, Salesforce o Google Mail para iniciar sesión en la extranet de asociados de la compañía.</span><span class="sxs-lookup"><span data-stu-id="3f750-115">Vendors and partners to use their LinkedIn, Salesforce, or Google Mail accounts to sign in to the company's partner extranet.</span></span>

<span data-ttu-id="3f750-116">Esta es la DMZ de Contoso que contiene un sitio web público, una extranet de asociados y un conjunto de servidores de AD FS.</span><span class="sxs-lookup"><span data-stu-id="3f750-116">Here's the Contoso DMZ containing a public web site, a partner extranet, and a set of AD FS servers.</span></span> <span data-ttu-id="3f750-117">La DMZ está conectada a Internet que contiene clientes, socios y servicios de Internet.</span><span class="sxs-lookup"><span data-stu-id="3f750-117">The DMZ is connected to the internet that contains customers, partners, and internet services.</span></span>

![Soporte técnico de Contoso para la autenticación federada para clientes y Partners](../media/contoso-identity/contoso-identity-fig2.png)
 
<span data-ttu-id="3f750-119">Los servidores de AD FS en la DMZ facilitan la autenticación de las credenciales del cliente por sus proveedores de identidades para obtener acceso al sitio web público y las credenciales del asociado para obtener acceso a la extranet del asociado.</span><span class="sxs-lookup"><span data-stu-id="3f750-119">AD FS servers in the DMZ facilitate authentication of customer credentials by their identity providers for access to the public web site and partner credentials for access to the partner extranet.</span></span>

<span data-ttu-id="3f750-120">Contoso decidió mantener esta infraestructura y dedicarla a la autenticación de clientes y socios.</span><span class="sxs-lookup"><span data-stu-id="3f750-120">Contoso decided to keep this infrastructure and dedicate it to customer and partner authentication.</span></span> <span data-ttu-id="3f750-121">Los arquitectos de identidad de Contoso están investigando la conversión de esta infraestructura en las soluciones de Azure AD [B2B](https://docs.microsoft.com/azure/active-directory/b2b/hybrid-organizations) y [B2C](https://docs.microsoft.com/azure/active-directory-b2c/solution-articles)</span><span class="sxs-lookup"><span data-stu-id="3f750-121">Contoso identity architects are investigating the conversion of this infrastructure to Azure AD [B2B](https://docs.microsoft.com/azure/active-directory/b2b/hybrid-organizations) and [B2C](https://docs.microsoft.com/azure/active-directory-b2c/solution-articles) solutions.</span></span>

## <a name="hybrid-identity-with-password-hash-synchronization-for-cloud-based-authentication"></a><span data-ttu-id="3f750-122">Identidad híbrida con sincronización de hash de contraseña para la autenticación basada en la nube</span><span class="sxs-lookup"><span data-stu-id="3f750-122">Hybrid identity with password hash synchronization for cloud-based authentication</span></span>

<span data-ttu-id="3f750-123">Contoso quería usar su bosque de AD DS local para la autenticación en los recursos de nube de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3f750-123">Contoso wanted to use its on-premises AD DS forest for authentication to Microsoft 365 cloud resources.</span></span> <span data-ttu-id="3f750-124">Decidió usar la sincronización de hash de contraseña (PHS).</span><span class="sxs-lookup"><span data-stu-id="3f750-124">It decided to use password hash synchronization (PHS).</span></span>

<span data-ttu-id="3f750-125">PHS sincroniza el bosque de AD DS local con el inquilino de Azure AD de su suscripción de Microsoft 365 para empresas, copiando las cuentas de usuario y grupo y una versión hash de las contraseñas de cuentas de usuario.</span><span class="sxs-lookup"><span data-stu-id="3f750-125">PHS synchronizes the on-premises AD DS forest with the Azure AD tenant of their Microsoft 365 for enterprise subscription, copying user and group accounts and a hashed version of user account passwords.</span></span>

<span data-ttu-id="3f750-126">Para realizar la sincronización de directorios, contoso implementó la herramienta de Azure AD Connect en un servidor en su centro de recursos de París.</span><span class="sxs-lookup"><span data-stu-id="3f750-126">To do directory synchronization, Contoso deployed the Azure AD Connect tool on a server in its Paris datacenter.</span></span>

<span data-ttu-id="3f750-127">Este es el servidor que ejecuta Azure AD Connect y sondea el bosque de Contoso AD DS para obtener los cambios y, a continuación, sincronizar dichos cambios con el inquilino de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="3f750-127">Here's the server running Azure AD Connect polling the Contoso AD DS forest for changes and then synchronizing those changes with the Azure AD tenant.</span></span>

![La infraestructura de sincronización de directorios de Contoso PHS](../media/contoso-identity/contoso-identity-fig4.png)
 
## <a name="conditional-access-policies-for-identity-and-device-access"></a><span data-ttu-id="3f750-129">Directivas de Acceso Condicional a identidades y dispositivos</span><span class="sxs-lookup"><span data-stu-id="3f750-129">Conditional Access policies for identity and device access</span></span>

<span data-ttu-id="3f750-130">Contoso creó un conjunto de [directivas de Acceso Condicional](identity-access-policies.md) de Azure AD e Intune de tres niveles de protección:</span><span class="sxs-lookup"><span data-stu-id="3f750-130">Contoso created a set of Azure AD and Intune [Conditional Access policies](identity-access-policies.md) for three protection levels:</span></span>

- <span data-ttu-id="3f750-131">Las protecciones de *línea base* se aplican a todas las cuentas de usuario.</span><span class="sxs-lookup"><span data-stu-id="3f750-131">*Baseline* protections apply to all user accounts.</span></span>
- <span data-ttu-id="3f750-132">Las protecciones *confidenciales* son válidas para el liderazgo Senior y el personal ejecutivo.</span><span class="sxs-lookup"><span data-stu-id="3f750-132">*Sensitive* protections apply to senior leadership and executive staff.</span></span>
- <span data-ttu-id="3f750-133">Las protecciones *altamente reguladas* se aplican a usuarios específicos en los departamentos de finanzas, legales y de investigación que tienen acceso a datos altamente regulados.</span><span class="sxs-lookup"><span data-stu-id="3f750-133">*Highly Regulated* protections apply to specific users in the finance, legal, and research departments who have access to highly regulated data.</span></span>

<span data-ttu-id="3f750-134">Este es el conjunto resultante de directivas de acceso condicional de identidad de Contoso y de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3f750-134">Here's the resulting set of Contoso identity and device Conditional Access policies.</span></span>

![Directivas de acceso condicional a identidades y dispositivos de Contoso](../media/contoso-identity/contoso-identity-fig5.png)
 
## <a name="next-step"></a><span data-ttu-id="3f750-136">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="3f750-136">Next step</span></span>

<span data-ttu-id="3f750-137">[Obtenga información sobre](contoso-win10.md) cómo contoso usa su infraestructura de Microsoft Endpoint Configuration Manager para implementar y mantener la actual de Windows 10 Enterprise en su organización.</span><span class="sxs-lookup"><span data-stu-id="3f750-137">[Learn](contoso-win10.md) how Contoso uses its Microsoft Endpoint Configuration Manager infrastructure to deploy and keep current Windows 10 Enterprise across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="3f750-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="3f750-138">See also</span></span>

[<span data-ttu-id="3f750-139">Plan de identidad para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3f750-139">Identity roadmap for Microsoft 365</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="3f750-140">Información general de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="3f750-140">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="3f750-141">Guías del laboratorio de pruebas</span><span class="sxs-lookup"><span data-stu-id="3f750-141">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
