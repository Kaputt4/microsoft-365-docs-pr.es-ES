---
title: Identidad para Contoso Corporation
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 09/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Cómo Contoso aprovecha la Identidad como servicio (IDaaS) y proporciona autenticación basada en la nube a sus empleados y autenticación federada a sus partners y clientes.
ms.openlocfilehash: 7571aa455cac4da9e56d7d2001ae4421c3769c94
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2018
ms.locfileid: "26871628"
---
# <a name="identity-for-the-contoso-corporation"></a><span data-ttu-id="2c08e-103">Identidad para Contoso Corporation</span><span class="sxs-lookup"><span data-stu-id="2c08e-103">Identity for the Contoso Corporation</span></span>

<span data-ttu-id="2c08e-104">**Resumen:** Cómo Contoso aprovecha la Identidad como servicio (IDaaS) y proporciona autenticación basada en la nube a sus empleados y autenticación federada a sus partners y clientes.</span><span class="sxs-lookup"><span data-stu-id="2c08e-104">**Summary:** How Contoso takes advantage of Identity as a Service (IDaaS) and provides cloud-based authentication for its employees and federated authentication for its partners and customers.</span></span>

<span data-ttu-id="2c08e-p101">Microsoft proporciona una Identidad como servicio (IDaaS) en sus ofertas de nube con Azure Active Directory (AD). Para adoptar Microsoft 365 Enterprise, la solución IDaaS de Contoso tuvo que aprovechar su proveedor de identidades local e incluir la autenticación federada con sus proveedores de confianza existentes de identidades de terceros.</span><span class="sxs-lookup"><span data-stu-id="2c08e-p101">Microsoft provides an Identity as a Service (IDaaS) across its cloud offerings with Azure Active Directory (AD). To adopt Microsoft 365 Enterprise, Contoso's IDaaS solution had to leverage their on-premises identity provider and still include federated authentication with their existing trusted, third-party identity providers.</span></span>

## <a name="contosos-windows-server-ad-forest"></a><span data-ttu-id="2c08e-107">Bosque de Windows Server AD de Contoso</span><span class="sxs-lookup"><span data-stu-id="2c08e-107">Contoso's Windows Server AD forest</span></span>

<span data-ttu-id="2c08e-p102">Contoso usa un único bosque de Windows Server Active Directory (AD) para contoso.com con siete subdominios, uno para cada región del mundo. La sede, las oficinas de hubs regionales y las oficinas satélite contienen controladores de dominio para la autenticación local y la autorización.</span><span class="sxs-lookup"><span data-stu-id="2c08e-p102">Contoso uses a single Windows Server Active Directory (AD) forest for contoso.com with seven sub-domains, one for each region of the world. The headquarters, regional hub offices, and satellite offices contain domain controllers for local authentication and authorization.</span></span>

<span data-ttu-id="2c08e-110">La figura 1 muestra el bosque de Contoso con dominios regionales para las distintas partes del mundo que contienen centros regionales.</span><span class="sxs-lookup"><span data-stu-id="2c08e-110">Figure 1 shows the Contoso forest with regional domains for the different parts of the world that contain regional hubs.</span></span>

![](./media/contoso-identity/contoso-identity-fig1.png)
 
<span data-ttu-id="2c08e-111">**Figura 1: Bosque y dominios de Contoso en todo el mundo**</span><span class="sxs-lookup"><span data-stu-id="2c08e-111">**Figure 1: Contoso's forest and domains worldwide**</span></span>

<span data-ttu-id="2c08e-112">Contoso quiere usar las cuentas y los grupos del bosque contoso.com para la autenticación y la autorización de sus aplicaciones y cargas de trabajo basadas en la nube.</span><span class="sxs-lookup"><span data-stu-id="2c08e-112">Contoso wants to use the accounts and groups in the contoso.com forest for authentication and authorization for its cloud-based apps and workloads.</span></span>

## <a name="contosos-federated-authentication-infrastructure"></a><span data-ttu-id="2c08e-113">Infraestructura de autenticación federada de Contoso</span><span class="sxs-lookup"><span data-stu-id="2c08e-113">Contoso's federated authentication infrastructure</span></span>

<span data-ttu-id="2c08e-114">Contoso permite lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2c08e-114">Contoso allows:</span></span>

- <span data-ttu-id="2c08e-115">Que los clientes usen sus cuentas de Microsoft, Facebook o Google Mail para iniciar sesión en su sitio web público.</span><span class="sxs-lookup"><span data-stu-id="2c08e-115">Customers to use their Microsoft, Facebook, or Google Mail accounts to sign in to their public web site.</span></span>
- <span data-ttu-id="2c08e-116">Que los proveedores y partners usen sus cuentas de LinkedIn, Salesforce o Google Mail para iniciar sesión en la extranet de partners.</span><span class="sxs-lookup"><span data-stu-id="2c08e-116">Vendors and partners to use their LinkedIn, Salesforce, or Google Mail accounts to sign in to the partner extranet.</span></span>

<span data-ttu-id="2c08e-p103">La figura 2 muestra la red perimetral de Contoso con un sitio web público, una extranet de partners y un conjunto de servidores de Servicios de federación de Active Directory (AD FS). La red perimetral está conectada a Internet que contiene clientes y partners, y servicios de Internet.</span><span class="sxs-lookup"><span data-stu-id="2c08e-p103">Figure 2 shows the Contoso DMZ containing a public web site, a partner extranet, and a set of Active Directory Federation Services (AD FS) servers. The DMZ is connected to the Internet that contains customers, partners, and Internet services.</span></span>

![](./media/contoso-identity/contoso-identity-fig2.png)

<span data-ttu-id="2c08e-119">**Figura 2: Soporte de Contoso para la autenticación federada para clientes y partners**</span><span class="sxs-lookup"><span data-stu-id="2c08e-119">**Figure 2: Contoso's support for federated authentication for customers and partners**</span></span>
 
<span data-ttu-id="2c08e-120">Los servidores de los Servicios de federación de Active Directory (AD FS) de la red perimetral autentican las credenciales de cliente para el acceso al sitio web público y las credenciales de partner para el acceso a la extranet de partners.</span><span class="sxs-lookup"><span data-stu-id="2c08e-120">AD FS servers in the DMZ authenticate customer credentials for access to the public web site and partner credentials for access to the partner extranet.</span></span>

<span data-ttu-id="2c08e-p104">Contoso decidió mantener esta infraestructura y dedicarla a autenticaciones de partners y clientes. Los ingenieros de identidad de Contoso están investigando la conversión de esta infraestructura a Azure AD [B2B](https://docs.microsoft.com/azure/active-directory/b2b/hybrid-organizations) y soluciones [B2C](https://docs.microsoft.com/azure/active-directory-b2c/solution-articles).</span><span class="sxs-lookup"><span data-stu-id="2c08e-p104">Contoso decided to keep this infrastructure and dedicate it to customer and partner authentications. Contoso identity engineers are investigating the conversion of this infrastructure to Azure AD [B2B](https://docs.microsoft.com/azure/active-directory/b2b/hybrid-organizations) and [B2C](https://docs.microsoft.com/azure/active-directory-b2c/solution-articles) solutions.</span></span>

## <a name="hybrid-identity-with-pass-through-authentication-for-cloud-based-authentication"></a><span data-ttu-id="2c08e-123">Identidad híbrida con autenticación de paso a través para la autenticación basada en la nube</span><span class="sxs-lookup"><span data-stu-id="2c08e-123">Hybrid identity with pass-through authentication for cloud-based authentication</span></span>

<span data-ttu-id="2c08e-p105">Contoso quería aprovechar su bosque de Windows Server AD local para la autenticación para los recursos de nube de Microsoft 365. Se decidió por la autenticación de paso a través (PTA) con sincronización de hash de contraseñas (PHS).</span><span class="sxs-lookup"><span data-stu-id="2c08e-p105">Contoso wanted to leverage its on-premises Windows Server AD forest for authentication to Microsoft 365 cloud resources. It decided on pass-through authentication (PTA) with password hash synchronization (PHS).</span></span>

### <a name="pta-authentication"></a><span data-ttu-id="2c08e-126">Autenticación PTA</span><span class="sxs-lookup"><span data-stu-id="2c08e-126">PTA authentication</span></span>

<span data-ttu-id="2c08e-p106">Contoso usa la PTA para la autenticación de credenciales de usuario. Cuando un usuario de Contoso accede a los recursos en la nube, pasa las credenciales que envía se pasan desde Azure AD a un servidor que ejecuta a un agente de autenticación del centro de datos de la sede de Contoso. Uno de estos servidores de agente de autenticación valida las credenciales de usuario en nombre de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="2c08e-p106">For authentication of user credentials, Contoso is using PTA. When a Contoso user accesses a cloud-based resources, the credentials it sends are passed by Azure AD to a server running an Authentication Agent in the Contoso headquarters datacenter. One of these Authentication Agent servers validates the user credentials on behalf of Azure AD.</span></span>

<span data-ttu-id="2c08e-130">La figura 3 muestra un conjunto de servidores de la sede de Contoso que ejecutan el agente de autenticación, con las solicitudes de proceso de autenticación pasadas desde Azure AD.</span><span class="sxs-lookup"><span data-stu-id="2c08e-130">Figure 3 shows a set of servers in the Contoso headquarters running the Authentication Agent, which process authentication requests passed to it from Azure AD.</span></span> 

![](./media/contoso-identity/contoso-identity-fig3.png)
 
<span data-ttu-id="2c08e-131">**Figura 3: Infraestructura de autenticación de paso a través de Contoso**</span><span class="sxs-lookup"><span data-stu-id="2c08e-131">**Figure 3: Contoso's pass-through authentication infrastructure**</span></span>

<span data-ttu-id="2c08e-132">Contoso eligió la PTA para satisfacer sus requisitos de seguridad, que establecen que se evalúe todo intento de autenticación para detectar cambios inmediatos en los estados de cuentas de usuario, directivas de contraseñas y horas de inicio de sesión efectuados en el bosque de Windows Server AD local.</span><span class="sxs-lookup"><span data-stu-id="2c08e-132">Contoso chose PTA to fulfill its security requirement that all authentication attempts be evaluated for immediate changes to user account states, password policies, and sign-in hours made to the on-premises Windows Server AD forest.</span></span>

### <a name="phs"></a><span data-ttu-id="2c08e-133">PHS</span><span class="sxs-lookup"><span data-stu-id="2c08e-133">PHS</span></span>

<span data-ttu-id="2c08e-p107">PHS sincroniza el bosque de Windows Server AD local con el inquilino de Azure AD de la suscripción de Microsoft 365 Enterprise, copiando cuentas de usuario y de grupo y una versión cifrada mediante hash de contraseñas de cuentas de usuario. Contoso se decidió por PHS para proporcionar un método alternativo de autenticación directamente con el inquilino de Azure AD en caso de que la PTA no esté disponible.</span><span class="sxs-lookup"><span data-stu-id="2c08e-p107">PHS synchronizes the on-premises Windows Server AD forest with the Azure AD tenant of their Microsoft 365 Enterprise subscription, copying user and group accounts and a hashed version of user account passwords. Contoso decided on PHS to provide an alternate method of authentication directly with the Azure AD tenant in the event that PTA is not available.</span></span>

<span data-ttu-id="2c08e-p108">Para realizar la sincronización de directorios continua, Contoso ha implementado la herramienta Azure AD Connect en un servidor de su centro de datos de París. La figura 4 muestra el servidor que ejecuta Azure AD Connect sondeando el bosque de Windows Server AD de Contoso para detectar cambios, y sincronizando luego los cambios con el inquilino de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="2c08e-p108">To perform the ongoing directory synchronization, Contoso has deployed the Azure AD Connect tool on a server in its Paris datacenter. Figure 4 shows the server running Azure AD Connect polling the Contoso Windows Server AD forest for changes and then synchronizing those changes with the Azure AD tenant.</span></span>

![](./media/contoso-identity/contoso-identity-fig4.png)
 
<span data-ttu-id="2c08e-138">**Figura 4: Infraestructura de sincronización PHS de directorios de Contoso**</span><span class="sxs-lookup"><span data-stu-id="2c08e-138">**Figure 4: Contoso's PHS directory synchronization infrastructure**</span></span>

## <a name="conditional-access-policies-for-identity"></a><span data-ttu-id="2c08e-139">Directivas de acceso condicional de identidades</span><span class="sxs-lookup"><span data-stu-id="2c08e-139">Conditional access policies for identity</span></span>

<span data-ttu-id="2c08e-140">Contoso creó un conjunto de [directivas de acceso condicional](identity-access-policies.md) de Azure AD para garantizar que se aplique la autenticación multifactor y los cambios de contraseña cuando Azure AD determine que una solicitud de autenticación puede suponer una vulnerabilidad de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="2c08e-140">Contoso created a set of Azure AD [conditional access policies](identity-access-policies.md) to ensure that multi-factor authentication and password changes are enforced when Azure AD determines there is sign-in risk for an authentication request.</span></span>

<span data-ttu-id="2c08e-141">La figura 5 muestra el conjunto resultante de directivas de acceso condicional de identidad.</span><span class="sxs-lookup"><span data-stu-id="2c08e-141">Figure 5 shows their resulting set of conditional access policies for identity.</span></span>

![](./media/contoso-identity/contoso-identity-fig5.png)
 
<span data-ttu-id="2c08e-142">**Figura 5: Directivas de acceso condicional basado en la identidad de Contoso**</span><span class="sxs-lookup"><span data-stu-id="2c08e-142">**Figure 5: Contoso’s identity-based conditional access policies**</span></span>

## <a name="next-step"></a><span data-ttu-id="2c08e-143">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="2c08e-143">Next step</span></span>

<span data-ttu-id="2c08e-144">[Obtenga información sobre](contoso-win10.md) cómo aprovecha Contoso su infraestructura de System Center Configuration Manager para implementar y mantener actualizado Windows 10 Enterprise en la organización.</span><span class="sxs-lookup"><span data-stu-id="2c08e-144">[Learn](contoso-win10.md) how Contoso is leveraging its System Center Configuration Manager infrastructure to deploy and keep current Windows 10 Enterprise across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="2c08e-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="2c08e-145">See also</span></span>

[<span data-ttu-id="2c08e-146">Identidad para Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="2c08e-146">Identity for Microsoft 365 Enterprise</span></span>](identity-infrastructure.md)

[<span data-ttu-id="2c08e-147">Guía de implementación</span><span class="sxs-lookup"><span data-stu-id="2c08e-147">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="2c08e-148">Guías del laboratorio de pruebas</span><span class="sxs-lookup"><span data-stu-id="2c08e-148">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
