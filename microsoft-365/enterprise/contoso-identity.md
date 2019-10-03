---
title: Identidad para Contoso Corporation
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 09/06/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Cómo Contoso aprovecha la Identidad como servicio (IDaaS) y proporciona autenticación basada en la nube a sus empleados y autenticación federada a sus partners y clientes.
ms.openlocfilehash: 5c78e8cc9235eb2ca5de091c05d1883ed6cca1b4
ms.sourcegitcommit: c6eab4a9f1b70e7ff0db6b2a1128a4db2591cbaf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2019
ms.locfileid: "37369611"
---
# <a name="identity-for-the-contoso-corporation"></a><span data-ttu-id="10e60-103">Identidad para Contoso Corporation</span><span class="sxs-lookup"><span data-stu-id="10e60-103">Identity for the Contoso Corporation</span></span>

<span data-ttu-id="10e60-104">**Resumen:** Cómo Contoso aprovecha la Identidad como servicio (IDaaS) y proporciona autenticación basada en la nube a sus empleados y autenticación federada a sus partners y clientes.</span><span class="sxs-lookup"><span data-stu-id="10e60-104">**Summary:** How Contoso takes advantage of Identity as a Service (IDaaS) and provides cloud-based authentication for its employees and federated authentication for its partners and customers.</span></span>

<span data-ttu-id="10e60-105">Microsoft proporciona una Identidad como servicio (IDaaS) en su oferta en la nube con Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="10e60-105">Microsoft provides an Identity as a Service (IDaaS) across its cloud offerings with Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="10e60-106">Para adoptar Microsoft 365 Enterprise, la solución IDaaS de Contoso debe aprovechar su proveedor de identidades local y seguir incluyendo la autenticación federada con sus proveedores de identidades de terceros de confianza existentes.</span><span class="sxs-lookup"><span data-stu-id="10e60-106">To adopt Microsoft 365 Enterprise, Contoso's IDaaS solution had to leverage their on-premises identity provider and still include federated authentication with their existing trusted, third-party identity providers.</span></span>

## <a name="contosos-active-directory-domain-services-forest"></a><span data-ttu-id="10e60-107">Bosque de Active Directory Domain Services de Contoso</span><span class="sxs-lookup"><span data-stu-id="10e60-107">Contoso's Active Directory Domain Services forest</span></span>

<span data-ttu-id="10e60-108">Contoso usa un único bosque de Active Directory Domain Services (AD DS) para contoso.com con siete subdominios, uno para cada región del mundo.</span><span class="sxs-lookup"><span data-stu-id="10e60-108">Contoso uses a single Active Directory Domain Services (AD DS) forest for contoso.com with seven sub-domains, one for each region of the world.</span></span> <span data-ttu-id="10e60-109">La sede, las oficinas regionales y las oficinas satélite contienen controladores de dominio para la autenticación y la autorización local.</span><span class="sxs-lookup"><span data-stu-id="10e60-109">The headquarters, regional hub offices, and satellite offices contain domain controllers for local authentication and authorization.</span></span>

<span data-ttu-id="10e60-110">La figura 1 muestra el bosque de Contoso con dominios regionales para las distintas partes del mundo que contienen centros regionales.</span><span class="sxs-lookup"><span data-stu-id="10e60-110">Figure 1 shows the Contoso forest with regional domains for the different parts of the world that contain regional hubs.</span></span>

![Bosque y dominios de Contoso en todo el mundo](./media/contoso-identity/contoso-identity-fig1.png)
 
<span data-ttu-id="10e60-112">**Figura 1: Bosque y dominios de Contoso en todo el mundo**</span><span class="sxs-lookup"><span data-stu-id="10e60-112">**Figure 1: Contoso's forest and domains worldwide**</span></span>

<span data-ttu-id="10e60-113">Contoso quería usar las cuentas y los grupos del bosque contoso.com para la autenticación y la autorización de sus cargas de trabajo y servicios en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="10e60-113">Contoso wanted to use the accounts and groups in the contoso.com forest for authentication and authorization for its Microsoft 365 workloads and services.</span></span>

## <a name="contosos-federated-authentication-infrastructure"></a><span data-ttu-id="10e60-114">Infraestructura de autenticación federada de Contoso</span><span class="sxs-lookup"><span data-stu-id="10e60-114">Contoso's federated authentication infrastructure</span></span>

<span data-ttu-id="10e60-115">Contoso permite lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="10e60-115">Contoso allows:</span></span>

- <span data-ttu-id="10e60-116">Que los clientes usen sus cuentas de Microsoft, Facebook o Google Mail para iniciar sesión en su sitio web público.</span><span class="sxs-lookup"><span data-stu-id="10e60-116">Customers to use their Microsoft, Facebook, or Google Mail accounts to sign in to their public web site.</span></span>
- <span data-ttu-id="10e60-117">Que los proveedores y partners usen sus cuentas de LinkedIn, Salesforce o Google Mail para iniciar sesión en la extranet de partners.</span><span class="sxs-lookup"><span data-stu-id="10e60-117">Vendors and partners to use their LinkedIn, Salesforce, or Google Mail accounts to sign in to the partner extranet.</span></span>

<span data-ttu-id="10e60-p103">La figura 2 muestra la red perimetral de Contoso con un sitio web público, una extranet de partners y un conjunto de servidores de Servicios de federación de Active Directory (AD FS). La red perimetral está conectada a Internet que contiene clientes y partners, y servicios de Internet.</span><span class="sxs-lookup"><span data-stu-id="10e60-p103">Figure 2 shows the Contoso DMZ containing a public web site, a partner extranet, and a set of Active Directory Federation Services (AD FS) servers. The DMZ is connected to the Internet that contains customers, partners, and Internet services.</span></span>

![Soporte de Contoso para autenticación federada para clientes y partners](./media/contoso-identity/contoso-identity-fig2.png)

<span data-ttu-id="10e60-121">**Figura 2: Soporte de Contoso para la autenticación federada para clientes y partners**</span><span class="sxs-lookup"><span data-stu-id="10e60-121">**Figure 2: Contoso's support for federated authentication for customers and partners**</span></span>
 
<span data-ttu-id="10e60-122">Los servidores de AD FS de la red perimetral facilitan autenticar las credenciales de cliente en sus proveedores de identidad para el acceso al sitio web público y las credenciales de partner para el acceso a la extranet de partners.</span><span class="sxs-lookup"><span data-stu-id="10e60-122">AD FS servers in the DMZ authenticate customer credentials for access to the public web site and partner credentials for access to the partner extranet.</span></span>

<span data-ttu-id="10e60-123">Contoso decidió mantener esta infraestructura y dedicarla a la autenticación de clientes y partners.</span><span class="sxs-lookup"><span data-stu-id="10e60-123">Contoso decided to keep this infrastructure and dedicate it to customer and partner authentications. Contoso identity engineers are investigating the conversion of this infrastructure to Azure AD B2B and B2C solutions.</span></span> <span data-ttu-id="10e60-124">Los arquitectos de identidad de Contoso están investigando la conversión de esta infraestructura en las soluciones de Azure AD [B2B](https://docs.microsoft.com/azure/active-directory/b2b/hybrid-organizations) y [B2C](https://docs.microsoft.com/azure/active-directory-b2c/solution-articles)</span><span class="sxs-lookup"><span data-stu-id="10e60-124">Contoso decided to keep this infrastructure and dedicate it to customer and partner authentications. Contoso identity engineers are investigating the conversion of this infrastructure to Azure AD [B2B](https://docs.microsoft.com/azure/active-directory/b2b/hybrid-organizations) and [B2C](https://docs.microsoft.com/azure/active-directory-b2c/solution-articles) solutions.</span></span>

## <a name="hybrid-identity-with-password-hash-synchronization-for-cloud-based-authentication"></a><span data-ttu-id="10e60-125">Identidad híbrida con sincronización de hash de contraseña para la autenticación basada en la nube</span><span class="sxs-lookup"><span data-stu-id="10e60-125">Hybrid identity with password hash synchronization for cloud-based authentication</span></span>

<span data-ttu-id="10e60-126">Contoso quería aprovechar su bosque local de AD DS para la autenticación para los recursos de nube de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="10e60-126">Contoso wanted to leverage its on-premises AD DS forest for authentication to Microsoft 365 cloud resources.</span></span> <span data-ttu-id="10e60-127">Optó por la sincronización de hash de contraseñas (PHS).</span><span class="sxs-lookup"><span data-stu-id="10e60-127">It decided on password hash synchronization (PHS).</span></span>

<span data-ttu-id="10e60-128">PHS sincroniza el bosque local de AD DS con la cuenta empresarial de Azure AD de su suscripción de Microsoft 365 Enterprise, copiando las cuentas de usuario y de grupo, junto con una versión en hash de las contraseñas de cuentas de usuario.</span><span class="sxs-lookup"><span data-stu-id="10e60-128">PHS synchronizes the on-premises AD DS forest with the Azure AD tenant of their Microsoft 365 Enterprise subscription, copying user and group accounts and a hashed version of user account passwords.</span></span> 

<span data-ttu-id="10e60-129">Para realizar la sincronización continua de directorios, Costoso ha implementado la herramienta Azure AD Connect en un servidor de su centro de datos de París.</span><span class="sxs-lookup"><span data-stu-id="10e60-129">To perform the ongoing directory synchronization, Contoso has deployed the Azure AD Connect tool on a server in its Paris datacenter.</span></span> <span data-ttu-id="10e60-130">La figura 3 muestra el servidor que ejecuta Azure AD Connect y que sondea el bosque AD DS de Contoso en busca de cambios, para sincronizar dichos cambios con la cuenta empresarial de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="10e60-130">Figure 3 shows the server running Azure AD Connect polling the Contoso AD DS forest for changes and then synchronizing those changes with the Azure AD tenant.</span></span>

![Infraestructura de sincronización PHS de directorios de Contoso](./media/contoso-identity/contoso-identity-fig4.png)
 
<span data-ttu-id="10e60-132">**Figura 3: Infraestructura de sincronización PHS de directorios de Contoso**</span><span class="sxs-lookup"><span data-stu-id="10e60-132">**Figure 3: Contoso's PHS directory synchronization infrastructure**</span></span>


## <a name="conditional-access-policies-for-identity-and-device-access"></a><span data-ttu-id="10e60-133">Directivas de acceso condicional a identidades y dispositivos</span><span class="sxs-lookup"><span data-stu-id="10e60-133">Conditional access policies for identity and device access</span></span>

<span data-ttu-id="10e60-134">Contoso creó un conjunto de [directivas de acceso condicional](identity-access-policies.md) de Azure AD e Intune de tres niveles de protección:</span><span class="sxs-lookup"><span data-stu-id="10e60-134">Contoso created a set of Azure AD and Intune [conditional access policies](identity-access-policies.md) for three protection levels:</span></span>

- <span data-ttu-id="10e60-135">Protección **básica**, que se aplica a todas las cuentas de usuario</span><span class="sxs-lookup"><span data-stu-id="10e60-135">**Baseline** protections apply to all user accounts</span></span>
- <span data-ttu-id="10e60-136">Protección **confidencial**, que se aplica al personal directivo y al personal ejecutivo</span><span class="sxs-lookup"><span data-stu-id="10e60-136">**Sensitive** protections apply to senior leadership and executive staff</span></span>
- <span data-ttu-id="10e60-137">Protección **altamente regulada**, que se aplica a usuarios específicos de los departamentos financiero, legal y de investigación que tienen acceso a datos altamente regulados.</span><span class="sxs-lookup"><span data-stu-id="10e60-137">**Highly Regulated** protections apply to specific users in the finance, legal, and research departments that have access to highly regulated data</span></span>

<span data-ttu-id="10e60-138">La figura 4 muestra el conjunto resultante de directivas de acceso condicional a identidades.</span><span class="sxs-lookup"><span data-stu-id="10e60-138">Figure 4 shows their resulting set of identity and device conditional access policies.</span></span>

![Directivas de acceso condicional a identidades y dispositivos de Contoso](./media/contoso-identity/contoso-identity-fig5.png)
 
<span data-ttu-id="10e60-140">**Figura 4: Directivas de acceso condicional a identidades y dispositivos de Contoso**</span><span class="sxs-lookup"><span data-stu-id="10e60-140">**Figure 4: Contoso’s identity and device conditional access policies**</span></span>

## <a name="next-step"></a><span data-ttu-id="10e60-141">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="10e60-141">Next step</span></span>

<span data-ttu-id="10e60-142">[Obtenga información sobre](contoso-win10.md) cómo aprovecha Contoso su infraestructura de System Center Configuration Manager para implementar y mantener actualizado Windows 10 Enterprise en la organización.</span><span class="sxs-lookup"><span data-stu-id="10e60-142">[Learn](contoso-win10.md) how Contoso is leveraging its System Center Configuration Manager infrastructure to deploy and keep current Windows 10 Enterprise across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="10e60-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="10e60-143">See also</span></span>

[<span data-ttu-id="10e60-144">Identidad para Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="10e60-144">Identity for Microsoft 365 Enterprise</span></span>](identity-infrastructure.md)

[<span data-ttu-id="10e60-145">Guía de implementación</span><span class="sxs-lookup"><span data-stu-id="10e60-145">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="10e60-146">Guías del laboratorio de pruebas</span><span class="sxs-lookup"><span data-stu-id="10e60-146">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
