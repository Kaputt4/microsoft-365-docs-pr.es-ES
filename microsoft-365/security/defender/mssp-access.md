---
title: Proporcionar acceso al proveedor de servicios de seguridad administrado (MSSP)
description: Obtenga información sobre los cambios de la Centro de seguridad de Microsoft Defender al centro Microsoft 365 seguridad
keywords: Introducción al centro de seguridad de Microsoft 365, Microsoft Defender para Office 365, Microsoft Defender para endpoint, MDO, MDE, panel único de cristal, portal convergente, portal de seguridad, portal de seguridad, portal de seguridad de defender
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
localization_priority: Normal
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
manager: dansimp
audience: ITPro
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.openlocfilehash: ddc28149ca2ab43b7c14d3bdbaeeecdad1b18387
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289768"
---
# <a name="provide-managed-security-service-provider-mssp-access"></a><span data-ttu-id="551b2-104">Proporcionar acceso al proveedor de servicios de seguridad administrado (MSSP)</span><span class="sxs-lookup"><span data-stu-id="551b2-104">Provide managed security service provider (MSSP) access</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

<span data-ttu-id="551b2-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="551b2-105">**Applies to:**</span></span>

- [<span data-ttu-id="551b2-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="551b2-106">Microsoft 365 Defender</span></span>](microsoft-365-defender.md)
- [<span data-ttu-id="551b2-107">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="551b2-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

<span data-ttu-id="551b2-108">Para implementar una solución de acceso delegado multiinquilino, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="551b2-108">To implement a multi-tenant delegated access solution, take the following steps:</span></span>

1. <span data-ttu-id="551b2-109">Habilite [el control de acceso basado](/windows/security/threat-protection/microsoft-defender-atp/rbac) en roles en Defender para endpoint en Microsoft 365 de seguridad y conéctese con Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="551b2-109">Enable [role-based access control](/windows/security/threat-protection/microsoft-defender-atp/rbac) in Defender for Endpoint in Microsoft 365 security center and connect with Azure Active Directory (Azure AD) groups.</span></span>

2. <span data-ttu-id="551b2-110">Configurar [paquetes de acceso de gobierno](/azure/active-directory/governance/identity-governance-overview) para la solicitud de acceso y el aprovisionamiento.</span><span class="sxs-lookup"><span data-stu-id="551b2-110">Configure [Governance Access Packages](/azure/active-directory/governance/identity-governance-overview) for access request and provisioning.</span></span>

3. <span data-ttu-id="551b2-111">Administrar solicitudes de acceso y auditorías [en Microsoft Myaccess](/azure/active-directory/governance/entitlement-management-request-approve).</span><span class="sxs-lookup"><span data-stu-id="551b2-111">Manage access requests and audits in [Microsoft Myaccess](/azure/active-directory/governance/entitlement-management-request-approve).</span></span>

## <a name="enable-role-based-access-controls-in-microsoft-defender-for-endpoint-in-microsoft-365-security-center"></a><span data-ttu-id="551b2-112">Habilitar controles de acceso basados en roles en Microsoft Defender para endpoint en Microsoft 365 de seguridad</span><span class="sxs-lookup"><span data-stu-id="551b2-112">Enable role-based access controls in Microsoft Defender for Endpoint in Microsoft 365 security center</span></span>

1. <span data-ttu-id="551b2-113">**Crear grupos de acceso para recursos MSSP en Customer AAD: Groups**</span><span class="sxs-lookup"><span data-stu-id="551b2-113">**Create access groups for MSSP resources in Customer AAD: Groups**</span></span>

    <span data-ttu-id="551b2-114">Estos grupos se vincularán a los roles que cree en Defender for Endpoint en Microsoft 365 de seguridad.</span><span class="sxs-lookup"><span data-stu-id="551b2-114">These groups will be linked to the Roles you create in Defender for Endpoint in Microsoft 365 security center.</span></span> <span data-ttu-id="551b2-115">Para ello, en el inquilino de AD del cliente, cree tres grupos.</span><span class="sxs-lookup"><span data-stu-id="551b2-115">To do so, in the customer AD tenant, create three groups.</span></span> <span data-ttu-id="551b2-116">En nuestro enfoque de ejemplo, creamos los siguientes grupos:</span><span class="sxs-lookup"><span data-stu-id="551b2-116">In our example approach, we create the following groups:</span></span>

    - <span data-ttu-id="551b2-117">Analista de nivel 1</span><span class="sxs-lookup"><span data-stu-id="551b2-117">Tier 1 Analyst</span></span>
    - <span data-ttu-id="551b2-118">Analista de nivel 2</span><span class="sxs-lookup"><span data-stu-id="551b2-118">Tier 2 Analyst</span></span>
    - <span data-ttu-id="551b2-119">Aprobadores de analistas de MSSP</span><span class="sxs-lookup"><span data-stu-id="551b2-119">MSSP Analyst Approvers</span></span>  

2. <span data-ttu-id="551b2-120">Cree roles de Defender para endpoint para niveles de acceso adecuados en Customer Defender for Endpoint en Microsoft 365 roles y grupos del centro de seguridad.</span><span class="sxs-lookup"><span data-stu-id="551b2-120">Create Defender for Endpoint roles for appropriate access levels in Customer Defender for Endpoint in Microsoft 365 security center roles and groups.</span></span>

    <span data-ttu-id="551b2-121">Para habilitar RBAC en el centro de seguridad de Microsoft 365 clientes, acceda a permisos > roles de puntos de conexión & grupos > **Roles** con una cuenta de usuario con derechos de administrador global o administrador de seguridad.</span><span class="sxs-lookup"><span data-stu-id="551b2-121">To enable RBAC in the customer Microsoft 365 security center, access **Permissions >  Endpoints roles & groups > Roles** with a user account with Global Administrator or Security Administrator rights.</span></span>

    ![Imagen del acceso de MSSP](../../media/mssp-access.png)

    <span data-ttu-id="551b2-123">A continuación, cree roles RBAC para satisfacer las necesidades de nivel SOC de MSSP.</span><span class="sxs-lookup"><span data-stu-id="551b2-123">Then, create RBAC roles to meet MSSP SOC Tier needs.</span></span> <span data-ttu-id="551b2-124">Vincule estos roles a los grupos de usuarios creados mediante "Grupos de usuarios asignados".</span><span class="sxs-lookup"><span data-stu-id="551b2-124">Link these roles to the created user groups via "Assigned user groups".</span></span>

    <span data-ttu-id="551b2-125">Dos roles posibles:</span><span class="sxs-lookup"><span data-stu-id="551b2-125">Two possible roles:</span></span>

    - <span data-ttu-id="551b2-126">**Analistas de nivel 1**</span><span class="sxs-lookup"><span data-stu-id="551b2-126">**Tier 1 Analysts**</span></span> <br>
      <span data-ttu-id="551b2-127">Realice todas las acciones excepto la respuesta en directo y administre la configuración de seguridad.</span><span class="sxs-lookup"><span data-stu-id="551b2-127">Perform all actions except for live response and manage security settings.</span></span>

    - <span data-ttu-id="551b2-128">**Analistas de nivel 2**</span><span class="sxs-lookup"><span data-stu-id="551b2-128">**Tier 2 Analysts**</span></span> <br>
      <span data-ttu-id="551b2-129">Capacidades de nivel 1 con la adición a [la respuesta en directo](/windows/security/threat-protection/microsoft-defender-atp/live-response)</span><span class="sxs-lookup"><span data-stu-id="551b2-129">Tier 1 capabilities with the addition to [live response](/windows/security/threat-protection/microsoft-defender-atp/live-response)</span></span>

    <span data-ttu-id="551b2-130">Para obtener más información, vea [Use role-based access control](/windows/security/threat-protection/microsoft-defender-atp/rbac).</span><span class="sxs-lookup"><span data-stu-id="551b2-130">For more information, see [Use role-based access control](/windows/security/threat-protection/microsoft-defender-atp/rbac).</span></span>

## <a name="configure-governance-access-packages"></a><span data-ttu-id="551b2-131">Configurar paquetes de acceso de gobierno</span><span class="sxs-lookup"><span data-stu-id="551b2-131">Configure Governance Access Packages</span></span>

1. <span data-ttu-id="551b2-132">**Agregar MSSP como organización conectada en customer AAD: Identity Governance**</span><span class="sxs-lookup"><span data-stu-id="551b2-132">**Add MSSP as Connected Organization in Customer AAD: Identity Governance**</span></span>

    <span data-ttu-id="551b2-133">Agregar el MSSP como organización conectada permitirá al MSSP solicitar y tener accesos aprovisionados.</span><span class="sxs-lookup"><span data-stu-id="551b2-133">Adding the MSSP as a connected organization will allow the MSSP to request and have accesses provisioned.</span></span> 

    <span data-ttu-id="551b2-134">Para ello, en el inquilino de AD del cliente, acceda a Identity Governance: Connected organization.</span><span class="sxs-lookup"><span data-stu-id="551b2-134">To do so, in the customer AD tenant, access Identity Governance: Connected organization.</span></span> <span data-ttu-id="551b2-135">Agregue una nueva organización y busque el inquilino de MSSP Analyst a través del identificador de inquilino o dominio.</span><span class="sxs-lookup"><span data-stu-id="551b2-135">Add a new organization and search for your MSSP Analyst tenant via Tenant ID or Domain.</span></span> <span data-ttu-id="551b2-136">Se recomienda crear un inquilino de AD independiente para los analistas de MSSP.</span><span class="sxs-lookup"><span data-stu-id="551b2-136">We suggest creating a separate AD tenant for your MSSP Analysts.</span></span>

2. <span data-ttu-id="551b2-137">**Crear un catálogo de recursos en Customer AAD: Identity Governance**</span><span class="sxs-lookup"><span data-stu-id="551b2-137">**Create a resource catalog in Customer AAD: Identity Governance**</span></span>

    <span data-ttu-id="551b2-138">Los catálogos de recursos son una colección lógica de paquetes de acceso, creados en el inquilino de AD del cliente.</span><span class="sxs-lookup"><span data-stu-id="551b2-138">Resource catalogs are a logical collection of access packages, created in the customer AD tenant.</span></span>

    <span data-ttu-id="551b2-139">Para ello, en el inquilino de AD del cliente, acceda a Identity Governance: Catalogs y agregue **New Catalog**.</span><span class="sxs-lookup"><span data-stu-id="551b2-139">To do so, in the customer AD tenant,  access Identity Governance: Catalogs, and add **New Catalog**.</span></span> <span data-ttu-id="551b2-140">En nuestro ejemplo, lo llamaremos **MSSP Accesses**.</span><span class="sxs-lookup"><span data-stu-id="551b2-140">In our example, we will call it **MSSP Accesses**.</span></span>

    ![Imagen del nuevo catálogo](../../media/goverance-catalog.png)

    <span data-ttu-id="551b2-142">Para obtener más información, vea [Create a catalog of resources](/azure/active-directory/governance/entitlement-management-catalog-create).</span><span class="sxs-lookup"><span data-stu-id="551b2-142">Further more information, see [Create a catalog of resources](/azure/active-directory/governance/entitlement-management-catalog-create).</span></span>

3. <span data-ttu-id="551b2-143">**Crear paquetes de acceso para recursos MSSP Customer AAD: Identity Governance**</span><span class="sxs-lookup"><span data-stu-id="551b2-143">**Create access packages for MSSP resources Customer AAD: Identity Governance**</span></span>

    <span data-ttu-id="551b2-144">Los paquetes de acceso son la colección de derechos y accesos que se concederá a un solicitante tras su aprobación.</span><span class="sxs-lookup"><span data-stu-id="551b2-144">Access packages are the collection of rights and accesses that a requestor will be granted upon approval.</span></span> 

    <span data-ttu-id="551b2-145">Para ello, en el inquilino de AD del cliente, acceda a Identity Governance: Access Packages y agregue **New Access Package**.</span><span class="sxs-lookup"><span data-stu-id="551b2-145">To do so, in the customer AD tenant, access Identity Governance: Access Packages, and add **New Access Package**.</span></span> <span data-ttu-id="551b2-146">Cree un paquete de acceso para los aprobadores de MSSP y cada nivel de analista.</span><span class="sxs-lookup"><span data-stu-id="551b2-146">Create an access package for the MSSP approvers and each analyst tier.</span></span> <span data-ttu-id="551b2-147">Por ejemplo, la siguiente configuración de Analista de nivel 1 crea un paquete de acceso que:</span><span class="sxs-lookup"><span data-stu-id="551b2-147">For example, the following Tier 1 Analyst configuration creates an access package that:</span></span>

    - <span data-ttu-id="551b2-148">Requiere que un miembro del grupo de AD **aprobadores de analistas de MSSP** autorice nuevas solicitudes</span><span class="sxs-lookup"><span data-stu-id="551b2-148">Requires a member of the AD group **MSSP Analyst Approvers** to authorize new requests</span></span>
    - <span data-ttu-id="551b2-149">Tiene revisiones de acceso anuales, donde los analistas de SOC pueden solicitar una extensión de acceso</span><span class="sxs-lookup"><span data-stu-id="551b2-149">Has annual access reviews, where the SOC analysts can request an access extension</span></span>
    - <span data-ttu-id="551b2-150">Los usuarios solo pueden solicitarlo en el inquilino soc de MSSP</span><span class="sxs-lookup"><span data-stu-id="551b2-150">Can only be requested by users in the MSSP SOC Tenant</span></span>
    - <span data-ttu-id="551b2-151">Access auto expira después de 365 días</span><span class="sxs-lookup"><span data-stu-id="551b2-151">Access auto expires after 365 days</span></span>

    ![Imagen del nuevo paquete de acceso](../../media/new-access-package.png)

    <span data-ttu-id="551b2-153">Para obtener más información, vea [Create a new access package](/azure/active-directory/governance/entitlement-management-access-package-create).</span><span class="sxs-lookup"><span data-stu-id="551b2-153">For more information, see [Create a new access package](/azure/active-directory/governance/entitlement-management-access-package-create).</span></span>

4. <span data-ttu-id="551b2-154">**Proporcionar vínculo de solicitud de acceso a recursos MSSP desde customer AAD: Identity Governance**</span><span class="sxs-lookup"><span data-stu-id="551b2-154">**Provide access request link to MSSP resources from Customer AAD: Identity Governance**</span></span>

    <span data-ttu-id="551b2-155">Los analistas de SOC de MSSP usan el vínculo Portal de My Access para solicitar acceso a través de los paquetes de acceso creados.</span><span class="sxs-lookup"><span data-stu-id="551b2-155">The My Access portal link is used by MSSP SOC analysts to request access via the access packages created.</span></span> <span data-ttu-id="551b2-156">El vínculo es duradero, lo que significa que el mismo vínculo puede usarse con el tiempo para los nuevos analistas.</span><span class="sxs-lookup"><span data-stu-id="551b2-156">The link is durable, meaning the same link may be used over time for new analysts.</span></span> <span data-ttu-id="551b2-157">La solicitud de analista entra en una cola para su aprobación por parte de los aprobadores de analistas de **MSSP**.</span><span class="sxs-lookup"><span data-stu-id="551b2-157">The analyst request goes into a queue for approval by the **MSSP Analyst Approvers**.</span></span>

    ![Imagen de las propiedades de access](../../media/access-properties.png)

    <span data-ttu-id="551b2-159">El vínculo se encuentra en la página de información general de cada paquete de acceso.</span><span class="sxs-lookup"><span data-stu-id="551b2-159">The link is located on the overview page of each access package.</span></span>

## <a name="manage-access"></a><span data-ttu-id="551b2-160">Administrar el acceso</span><span class="sxs-lookup"><span data-stu-id="551b2-160">Manage access</span></span>

1. <span data-ttu-id="551b2-161">Revise y autorice las solicitudes de acceso en Customer y/o MSSP myaccess.</span><span class="sxs-lookup"><span data-stu-id="551b2-161">Review and authorize access requests in Customer and/or MSSP myaccess.</span></span>

    <span data-ttu-id="551b2-162">Las solicitudes de acceso se administran en el cliente My Access, por miembros del grupo Aprobadores de analistas de MSSP.</span><span class="sxs-lookup"><span data-stu-id="551b2-162">Access requests are managed in the customer My Access, by members of the MSSP Analyst Approvers group.</span></span>

    <span data-ttu-id="551b2-163">Para ello, acceda a myaccess del cliente mediante: `https://myaccess.microsoft.com/@<Customer Domain>` .</span><span class="sxs-lookup"><span data-stu-id="551b2-163">To do so, access the customer's myaccess using: `https://myaccess.microsoft.com/@<Customer Domain>`.</span></span>

    <span data-ttu-id="551b2-164">Ejemplo: `https://myaccess.microsoft.com/@M365x440XXX.onmicrosoft.com#/`</span><span class="sxs-lookup"><span data-stu-id="551b2-164">Example: `https://myaccess.microsoft.com/@M365x440XXX.onmicrosoft.com#/`</span></span>

2. <span data-ttu-id="551b2-165">Aprobar o denegar solicitudes en la sección **Aprobaciones** de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="551b2-165">Approve or deny requests in the **Approvals** section of the UI.</span></span>

     <span data-ttu-id="551b2-166">En este momento, se ha aprovisionado el acceso de analistas y cada analista debe tener acceso al Centro de seguridad de Microsoft 365 cliente:</span><span class="sxs-lookup"><span data-stu-id="551b2-166">At this point, analyst access has been provisioned, and each analyst should be able to access the customer's Microsoft 365 Security Center:</span></span>

    <span data-ttu-id="551b2-167">`https://security.microsoft.com/?tid=<CustomerTenantId>` con los permisos y roles que se asignaron.</span><span class="sxs-lookup"><span data-stu-id="551b2-167">`https://security.microsoft.com/?tid=<CustomerTenantId>` with the permissions and roles they were assigned.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="551b2-168">El acceso delegado a Microsoft Defender para endpoint en el centro de seguridad Microsoft 365 permite actualmente el acceso a un único espacio empresarial por ventana del explorador.</span><span class="sxs-lookup"><span data-stu-id="551b2-168">Delegated access to Microsoft Defender for Endpoint in the Microsoft 365 security center currently allows access to a single tenant per browser window.</span></span>
