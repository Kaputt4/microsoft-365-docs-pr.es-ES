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
ms.openlocfilehash: 795fb7dcb886c792c80d3bb251c9cb5774f1bf97
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686039"
---
# <a name="identity-for-the-contoso-corporation"></a><span data-ttu-id="c3fc1-103">Identidad para Contoso Corporation</span><span class="sxs-lookup"><span data-stu-id="c3fc1-103">Identity for the Contoso Corporation</span></span>

<span data-ttu-id="c3fc1-104">Microsoft proporciona una Identidad como servicio (IDaaS) en su oferta en la nube con Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="c3fc1-104">Microsoft provides an Identity as a Service (IDaaS) across its cloud offerings with Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="c3fc1-105">Para adoptar Microsoft 365 para empresas, la solución IDaaS de Contoso tuvo que aprovechar su proveedor de identidades local y seguir incluyendo la autenticación federada con sus proveedores de identidades de terceros de confianza existentes.</span><span class="sxs-lookup"><span data-stu-id="c3fc1-105">To adopt Microsoft 365 for enterprise, Contoso's IDaaS solution had to leverage their on-premises identity provider and still include federated authentication with their existing trusted, third-party identity providers.</span></span>

## <a name="contosos-active-directory-domain-services-forest"></a><span data-ttu-id="c3fc1-106">Bosque de Active Directory Domain Services de Contoso</span><span class="sxs-lookup"><span data-stu-id="c3fc1-106">Contoso's Active Directory Domain Services forest</span></span>

<span data-ttu-id="c3fc1-107">Contoso usa un único bosque de Active Directory Domain Services (AD DS) para contoso.com con siete subdominios, uno para cada región del mundo.</span><span class="sxs-lookup"><span data-stu-id="c3fc1-107">Contoso uses a single Active Directory Domain Services (AD DS) forest for contoso.com with seven sub-domains, one for each region of the world.</span></span> <span data-ttu-id="c3fc1-108">La sede, las oficinas regionales y las oficinas satélite contienen controladores de dominio para la autenticación y la autorización local.</span><span class="sxs-lookup"><span data-stu-id="c3fc1-108">The headquarters, regional hub offices, and satellite offices contain domain controllers for local authentication and authorization.</span></span>

<span data-ttu-id="c3fc1-109">Este es el bosque de Contoso con dominios regionales para las distintas partes del mundo que contienen centros regionales.</span><span class="sxs-lookup"><span data-stu-id="c3fc1-109">Here is the Contoso forest with regional domains for the different parts of the world that contain regional hubs.</span></span>

![Bosque y dominios de Contoso en todo el mundo](../media/contoso-identity/contoso-identity-fig1.png)
 
<span data-ttu-id="c3fc1-111">Contoso quería usar las cuentas y los grupos del bosque contoso.com para la autenticación y la autorización de sus cargas de trabajo y servicios en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c3fc1-111">Contoso wanted to use the accounts and groups in the contoso.com forest for authentication and authorization for its Microsoft 365 workloads and services.</span></span>

## <a name="contosos-federated-authentication-infrastructure"></a><span data-ttu-id="c3fc1-112">Infraestructura de autenticación federada de Contoso</span><span class="sxs-lookup"><span data-stu-id="c3fc1-112">Contoso's federated authentication infrastructure</span></span>

<span data-ttu-id="c3fc1-113">Contoso permite lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c3fc1-113">Contoso allows:</span></span>

- <span data-ttu-id="c3fc1-114">Que los clientes usen sus cuentas de Microsoft, Facebook o Google Mail para iniciar sesión en su sitio web público.</span><span class="sxs-lookup"><span data-stu-id="c3fc1-114">Customers to use their Microsoft, Facebook, or Google Mail accounts to sign in to their public web site.</span></span>
- <span data-ttu-id="c3fc1-115">Que los proveedores y partners usen sus cuentas de LinkedIn, Salesforce o Google Mail para iniciar sesión en la extranet de partners.</span><span class="sxs-lookup"><span data-stu-id="c3fc1-115">Vendors and partners to use their LinkedIn, Salesforce, or Google Mail accounts to sign in to the partner extranet.</span></span>

<span data-ttu-id="c3fc1-116">Esta es la red perimetral de Contoso con un sitio web público, una extranet de partners y un conjunto de servidores de Active Directory Federation Services (AD FS).</span><span class="sxs-lookup"><span data-stu-id="c3fc1-116">Here is the Contoso DMZ containing a public web site, a partner extranet, and a set of Active Directory Federation Services (AD FS) servers.</span></span> <span data-ttu-id="c3fc1-117">La red perimetral está conectada al Internet que contiene clientes, partners y servicios de Internet.</span><span class="sxs-lookup"><span data-stu-id="c3fc1-117">The DMZ is connected to the Internet that contains customers, partners, and Internet services.</span></span>

![Soporte de Contoso de autenticación federada para los clientes y partners](../media/contoso-identity/contoso-identity-fig2.png)
 
<span data-ttu-id="c3fc1-119">Los servidores de AD FS de la red perimetral facilitan autenticar las credenciales de cliente en sus proveedores de identidad para el acceso al sitio web público y las credenciales de partner para el acceso a la extranet de partners.</span><span class="sxs-lookup"><span data-stu-id="c3fc1-119">AD FS servers in the DMZ facilitate the authentication of customer credentials by their identity providers for access to the public web site and partner credentials for access to the partner extranet.</span></span>

<span data-ttu-id="c3fc1-120">Contoso decidió mantener esta infraestructura y dedicarla a la autenticación de clientes y partners.</span><span class="sxs-lookup"><span data-stu-id="c3fc1-120">Contoso decided to keep this infrastructure and dedicate it to customer and partner authentications.</span></span> <span data-ttu-id="c3fc1-121">Los arquitectos de identidad de Contoso están investigando la conversión de esta infraestructura en las soluciones de Azure AD [B2B](https://docs.microsoft.com/azure/active-directory/b2b/hybrid-organizations) y [B2C](https://docs.microsoft.com/azure/active-directory-b2c/solution-articles)</span><span class="sxs-lookup"><span data-stu-id="c3fc1-121">Contoso identity architects are investigating the conversion of this infrastructure to Azure AD [B2B](https://docs.microsoft.com/azure/active-directory/b2b/hybrid-organizations) and [B2C](https://docs.microsoft.com/azure/active-directory-b2c/solution-articles) solutions.</span></span>

## <a name="hybrid-identity-with-password-hash-synchronization-for-cloud-based-authentication"></a><span data-ttu-id="c3fc1-122">Identidad híbrida con sincronización de hash de contraseña para la autenticación basada en la nube</span><span class="sxs-lookup"><span data-stu-id="c3fc1-122">Hybrid identity with password hash synchronization for cloud-based authentication</span></span>

<span data-ttu-id="c3fc1-123">Contoso quería aprovechar su bosque local de AD DS para la autenticación para los recursos de nube de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c3fc1-123">Contoso wanted to leverage its on-premises AD DS forest for authentication to Microsoft 365 cloud resources.</span></span> <span data-ttu-id="c3fc1-124">Optó por la sincronización de hash de contraseñas (PHS).</span><span class="sxs-lookup"><span data-stu-id="c3fc1-124">It decided on password hash synchronization (PHS).</span></span>

<span data-ttu-id="c3fc1-125">PHS sincroniza el bosque de AD DS local con el inquilino de Azure AD de su suscripción de Microsoft 365 para empresas, copiando las cuentas de usuario y grupo y una versión hash de las contraseñas de cuentas de usuario.</span><span class="sxs-lookup"><span data-stu-id="c3fc1-125">PHS synchronizes the on-premises AD DS forest with the Azure AD tenant of their Microsoft 365 for enterprise subscription, copying user and group accounts and a hashed version of user account passwords.</span></span> 

<span data-ttu-id="c3fc1-126">Para realizar la sincronización continua de directorios, Costoso ha implementado la herramienta Azure AD Connect en un servidor de su centro de datos de París.</span><span class="sxs-lookup"><span data-stu-id="c3fc1-126">To perform the ongoing directory synchronization, Contoso has deployed the Azure AD Connect tool on a server in its Paris datacenter.</span></span> 

<span data-ttu-id="c3fc1-127">Este es el servidor que ejecuta Azure AD Connect y que sondea el bosque AD DS de Contoso en busca de cambios, para después sincronizar dichos cambios con la cuenta empresarial de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="c3fc1-127">Here is the server running Azure AD Connect polling the Contoso AD DS forest for changes and then synchronizing those changes with the Azure AD tenant.</span></span>

![Infraestructura de sincronización PHS de directorios de Contoso](../media/contoso-identity/contoso-identity-fig4.png)
 
## <a name="conditional-access-policies-for-identity-and-device-access"></a><span data-ttu-id="c3fc1-129">Directivas de Acceso Condicional a identidades y dispositivos</span><span class="sxs-lookup"><span data-stu-id="c3fc1-129">Conditional Access policies for identity and device access</span></span>

<span data-ttu-id="c3fc1-130">Contoso creó un conjunto de [directivas de Acceso Condicional](identity-access-policies.md) de Azure AD e Intune de tres niveles de protección:</span><span class="sxs-lookup"><span data-stu-id="c3fc1-130">Contoso created a set of Azure AD and Intune [Conditional Access policies](identity-access-policies.md) for three protection levels:</span></span>

- <span data-ttu-id="c3fc1-131">Protección **básica**, que se aplica a todas las cuentas de usuario</span><span class="sxs-lookup"><span data-stu-id="c3fc1-131">**Baseline** protections apply to all user accounts</span></span>
- <span data-ttu-id="c3fc1-132">Protección **confidencial**, que se aplica al personal directivo y al personal ejecutivo</span><span class="sxs-lookup"><span data-stu-id="c3fc1-132">**Sensitive** protections apply to senior leadership and executive staff</span></span>
- <span data-ttu-id="c3fc1-133">Protección **altamente regulada**, que se aplica a usuarios específicos de los departamentos financiero, legal y de investigación que tienen acceso a datos altamente regulados.</span><span class="sxs-lookup"><span data-stu-id="c3fc1-133">**Highly Regulated** protections apply to specific users in the finance, legal, and research departments that have access to highly regulated data</span></span>

<span data-ttu-id="c3fc1-134">Este es el conjunto resultante de directivas de acceso condicional a identidades.</span><span class="sxs-lookup"><span data-stu-id="c3fc1-134">Here is Contoso's resulting set of identity and device Conditional Access policies.</span></span>

![Directivas de acceso condicional a identidades y dispositivos de Contoso](../media/contoso-identity/contoso-identity-fig5.png)
 
## <a name="next-step"></a><span data-ttu-id="c3fc1-136">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="c3fc1-136">Next step</span></span>

<span data-ttu-id="c3fc1-137">[Obtenga información acerca de](contoso-win10.md) cómo Contoso aprovecha su infraestructura de Microsoft Endpoint Configuration Manager para implementar y mantener Windows 10 Enterprise actual en su organización.</span><span class="sxs-lookup"><span data-stu-id="c3fc1-137">[Learn](contoso-win10.md) how Contoso is leveraging its Microsoft Endpoint Configuration Manager infrastructure to deploy and keep current Windows 10 Enterprise across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="c3fc1-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="c3fc1-138">See also</span></span>

[<span data-ttu-id="c3fc1-139">Mapa de ruta de identidad para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c3fc1-139">Identity roadmap for Microsoft 365</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="c3fc1-140">Información general de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="c3fc1-140">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="c3fc1-141">Guías del laboratorio de pruebas</span><span class="sxs-lookup"><span data-stu-id="c3fc1-141">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
