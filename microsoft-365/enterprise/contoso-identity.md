---
title: Identidad para Contoso Corporation
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 01/17/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Cómo Contoso aprovecha la Identidad como servicio (IDaaS) y proporciona autenticación basada en la nube a sus empleados y autenticación federada a sus partners y clientes.
ms.openlocfilehash: bcd83eaafb5df86d9a660aeb74b2e97f7bdc6b7b
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32277607"
---
# <a name="identity-for-the-contoso-corporation"></a><span data-ttu-id="34479-103">Identidad para Contoso Corporation</span><span class="sxs-lookup"><span data-stu-id="34479-103">Identity for the Contoso Corporation</span></span>

<span data-ttu-id="34479-104">**Resumen:** Cómo Contoso aprovecha la Identidad como servicio (IDaaS) y proporciona autenticación basada en la nube a sus empleados y autenticación federada a sus partners y clientes.</span><span class="sxs-lookup"><span data-stu-id="34479-104">**Summary:** How Contoso takes advantage of Identity as a Service (IDaaS) and provides cloud-based authentication for its employees and federated authentication for its partners and customers.</span></span>

<span data-ttu-id="34479-105">Microsoft proporciona una Identidad como servicio (IDaaS) en su oferta en la nube con Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="34479-105">Microsoft provides an Identity as a Service (IDaaS) across its cloud offerings with Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="34479-106">Para adoptar Microsoft 365 Enterprise, la solución IDaaS de Contoso debe aprovechar su proveedor de identidades local y seguir incluyendo la autenticación federada con sus proveedores de identidades de terceros de confianza existentes.</span><span class="sxs-lookup"><span data-stu-id="34479-106">Microsoft provides an Identity as a Service (IDaaS) across its cloud offerings with Azure Active Directory (AD). To adopt Microsoft 365 Enterprise, Contoso's IDaaS solution had to leverage their on-premises identity provider and still include federated authentication with their existing trusted, third-party identity providers.</span></span>

## <a name="contosos-active-directory-domain-services-forest"></a><span data-ttu-id="34479-107">Bosque de Active Directory Domain Services de Contoso</span><span class="sxs-lookup"><span data-stu-id="34479-107">Contoso's Active Directory Domain Services forest</span></span>

<span data-ttu-id="34479-108">Contoso usa un único bosque de Active Directory Domain Services (AD DS) para contoso.com con siete subdominios, uno para cada región del mundo.</span><span class="sxs-lookup"><span data-stu-id="34479-108">Contoso uses a single Active Directory Domain Services (AD DS) forest for contoso.com with seven sub-domains, one for each region of the world.</span></span> <span data-ttu-id="34479-109">La sede, las oficinas regionales y las oficinas satélite contienen controladores de dominio para la autenticación y la autorización local.</span><span class="sxs-lookup"><span data-stu-id="34479-109">The headquarters, regional hub offices, and satellite offices contain domain controllers for local authentication and authorization.</span></span>

<span data-ttu-id="34479-110">La figura 1 muestra el bosque de Contoso con dominios regionales para las distintas partes del mundo que contienen centros regionales.</span><span class="sxs-lookup"><span data-stu-id="34479-110">Figure 1 shows the Contoso forest with regional domains for the different parts of the world that contain regional hubs.</span></span>

![](./media/contoso-identity/contoso-identity-fig1.png)
 
<span data-ttu-id="34479-111">**Figura 1: Bosque y dominios de Contoso en todo el mundo**</span><span class="sxs-lookup"><span data-stu-id="34479-111">**Figure 1: Contoso's forest and domains worldwide**</span></span>

<span data-ttu-id="34479-112">Contoso quería usar las cuentas y los grupos del bosque contoso.com para la autenticación y la autorización de sus cargas de trabajo y servicios en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="34479-112">Contoso wants to use the accounts and groups in the contoso.com forest for authentication and authorization for its cloud-based apps and workloads.</span></span>

## <a name="contosos-federated-authentication-infrastructure"></a><span data-ttu-id="34479-113">Infraestructura de autenticación federada de Contoso</span><span class="sxs-lookup"><span data-stu-id="34479-113">Contoso's federated authentication infrastructure</span></span>

<span data-ttu-id="34479-114">Contoso permite lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="34479-114">Contoso allows:</span></span>

- <span data-ttu-id="34479-115">Que los clientes usen sus cuentas de Microsoft, Facebook o Google Mail para iniciar sesión en su sitio web público.</span><span class="sxs-lookup"><span data-stu-id="34479-115">Customers to use their Microsoft, Facebook, or Google Mail accounts to sign in to their public web site.</span></span>
- <span data-ttu-id="34479-116">Que los proveedores y partners usen sus cuentas de LinkedIn, Salesforce o Google Mail para iniciar sesión en la extranet de partners.</span><span class="sxs-lookup"><span data-stu-id="34479-116">Vendors and partners to use their LinkedIn, Salesforce, or Google Mail accounts to sign in to the partner extranet.</span></span>

<span data-ttu-id="34479-p103">La figura 2 muestra la red perimetral de Contoso con un sitio web público, una extranet de partners y un conjunto de servidores de Servicios de federación de Active Directory (AD FS). La red perimetral está conectada a Internet que contiene clientes y partners, y servicios de Internet.</span><span class="sxs-lookup"><span data-stu-id="34479-p103">Figure 2 shows the Contoso DMZ containing a public web site, a partner extranet, and a set of Active Directory Federation Services (AD FS) servers. The DMZ is connected to the Internet that contains customers, partners, and Internet services.</span></span>

![](./media/contoso-identity/contoso-identity-fig2.png)

<span data-ttu-id="34479-119">**Figura 2: Soporte de Contoso para la autenticación federada para clientes y partners**</span><span class="sxs-lookup"><span data-stu-id="34479-119">**Figure 2: Contoso's support for federated authentication for customers and partners**</span></span>
 
<span data-ttu-id="34479-120">Los servidores de los Servicios de federación de Active Directory (AD FS) de la red perimetral autentican las credenciales de cliente para el acceso al sitio web público y las credenciales de partner para el acceso a la extranet de partners.</span><span class="sxs-lookup"><span data-stu-id="34479-120">AD FS servers in the DMZ authenticate customer credentials for access to the public web site and partner credentials for access to the partner extranet.</span></span>

<span data-ttu-id="34479-p104">Contoso decidió mantener esta infraestructura y dedicarla a autenticaciones de partners y clientes. Los ingenieros de identidad de Contoso están investigando la conversión de esta infraestructura a Azure AD [B2B](https://docs.microsoft.com/azure/active-directory/b2b/hybrid-organizations) y soluciones [B2C](https://docs.microsoft.com/azure/active-directory-b2c/solution-articles).</span><span class="sxs-lookup"><span data-stu-id="34479-p104">Contoso decided to keep this infrastructure and dedicate it to customer and partner authentications. Contoso identity engineers are investigating the conversion of this infrastructure to Azure AD [B2B](https://docs.microsoft.com/azure/active-directory/b2b/hybrid-organizations) and [B2C](https://docs.microsoft.com/azure/active-directory-b2c/solution-articles) solutions.</span></span>

## <a name="hybrid-identity-with-password-hash-synchronization-for-cloud-based-authentication"></a><span data-ttu-id="34479-123">Identidad híbrida con sincronización de hash de contraseña para la autenticación basada en la nube</span><span class="sxs-lookup"><span data-stu-id="34479-123">Hybrid identity with password hash synchronization for cloud-based authentication</span></span>

<span data-ttu-id="34479-124">Contoso quería aprovechar su bosque local de AD DS para la autenticación para los recursos de nube de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="34479-124">Contoso wanted to leverage its on-premises Windows Server AD forest for authentication to Microsoft 365 cloud resources. It decided on pass-through authentication (PTA) with password hash synchronization (PHS).</span></span> <span data-ttu-id="34479-125">Optó por la sincronización de hash de contraseñas (PHS).</span><span class="sxs-lookup"><span data-stu-id="34479-125">It decided on password hash synchronization (PHS).</span></span>

<span data-ttu-id="34479-126">PHS sincroniza el bosque local de AD DS con la cuenta empresarial de Azure AD de su suscripción de Microsoft 365 Enterprise, copiando las cuentas de usuario y de grupo, junto con una versión en hash de las contraseñas de cuentas de usuario.</span><span class="sxs-lookup"><span data-stu-id="34479-126">PHS synchronizes the on-premises Windows Server AD forest with the Azure AD tenant of their Microsoft 365 Enterprise subscription, copying user and group accounts and a hashed version of user account passwords. Contoso decided on PHS to provide an alternate method of authentication directly with the Azure AD tenant in the event that PTA is not available.</span></span> 

<span data-ttu-id="34479-127">Para realizar la sincronización continua de directorios, Costoso ha implementado la herramienta Azure AD Connect en un servidor de su centro de datos de París.</span><span class="sxs-lookup"><span data-stu-id="34479-127">To perform the ongoing directory synchronization, Contoso has deployed the Azure AD Connect tool on a server in its Paris datacenter. Figure 4 shows the server running Azure AD Connect polling the Contoso Windows Server AD forest for changes and then synchronizing those changes with the Azure AD tenant.</span></span> <span data-ttu-id="34479-128">La figura 3 muestra el servidor que ejecuta Azure AD Connect y que sondea el bosque AD DS de Contoso en busca de cambios, para sincronizar dichos cambios con la cuenta empresarial de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="34479-128">To perform the ongoing directory synchronization, Contoso has deployed the Azure AD Connect tool on a server in its Paris datacenter. Figure 4 shows the server running Azure AD Connect polling the Contoso Windows Server AD forest for changes and then synchronizing those changes with the Azure AD tenant.</span></span>

![](./media/contoso-identity/contoso-identity-fig4.png)
 
<span data-ttu-id="34479-129">**Figura 3: Infraestructura de sincronización PHS de directorios de Contoso**</span><span class="sxs-lookup"><span data-stu-id="34479-129">**Figure 4: Contoso's PHS directory synchronization infrastructure**</span></span>


## <a name="conditional-access-policies-for-identity-and-device-access"></a><span data-ttu-id="34479-130">Directivas de acceso condicional a identidades y dispositivos</span><span class="sxs-lookup"><span data-stu-id="34479-130">Conditional access policies for identity and device access</span></span>

<span data-ttu-id="34479-131">Contoso creó un conjunto de [directivas de acceso condicional](identity-access-policies.md) de Azure AD e Intune de tres niveles de protección:</span><span class="sxs-lookup"><span data-stu-id="34479-131">Contoso created a set of Azure AD and Intune [conditional access policies](identity-access-policies.md) for three protection levels:</span></span>

- <span data-ttu-id="34479-132">Protección **básica**, que se aplica a todas las cuentas de usuario</span><span class="sxs-lookup"><span data-stu-id="34479-132">**Baseline** protections apply to all user accounts</span></span>
- <span data-ttu-id="34479-133">Protección **confidencial**, que se aplica al personal directivo y al personal ejecutivo</span><span class="sxs-lookup"><span data-stu-id="34479-133">**Sensitive** protections apply to senior leadership and executive staff</span></span>
- <span data-ttu-id="34479-134">Protección **altamente regulada**, que se aplica a usuarios específicos de los departamentos financiero, legal y de investigación que tienen acceso a datos altamente regulados.</span><span class="sxs-lookup"><span data-stu-id="34479-134">**Highly Regulated** protections apply to specific users in the finance, legal, and research departments that have access to highly regulated data</span></span>

<span data-ttu-id="34479-135">La figura 4 muestra el conjunto resultante de directivas de acceso condicional a identidades.</span><span class="sxs-lookup"><span data-stu-id="34479-135">Figure 5 shows their resulting set of conditional access policies for identity.</span></span>

![](./media/contoso-identity/contoso-identity-fig5.png)
 
<span data-ttu-id="34479-136">**Figura 4: Directivas de acceso condicional a identidades y dispositivos de Contoso**</span><span class="sxs-lookup"><span data-stu-id="34479-136">**Figure 4: Contoso’s identity and device conditional access policies**</span></span>

## <a name="next-step"></a><span data-ttu-id="34479-137">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="34479-137">Next step</span></span>

<span data-ttu-id="34479-138">[Obtenga información sobre](contoso-win10.md) cómo aprovecha Contoso su infraestructura de System Center Configuration Manager para implementar y mantener actualizado Windows 10 Enterprise en la organización.</span><span class="sxs-lookup"><span data-stu-id="34479-138">[Learn](contoso-win10.md) how Contoso is leveraging its System Center Configuration Manager infrastructure to deploy and keep current Windows 10 Enterprise across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="34479-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="34479-139">See also</span></span>

[<span data-ttu-id="34479-140">Identidad para Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="34479-140">Identity for Microsoft 365 Enterprise</span></span>](identity-infrastructure.md)

[<span data-ttu-id="34479-141">Guía de implementación</span><span class="sxs-lookup"><span data-stu-id="34479-141">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="34479-142">Guías del laboratorio de pruebas</span><span class="sxs-lookup"><span data-stu-id="34479-142">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
