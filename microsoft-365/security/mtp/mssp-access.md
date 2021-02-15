---
title: Microsoft Defender para puntos de conexión en el Centro de seguridad de Microsoft 365
description: Obtenga información sobre los cambios del Centro de seguridad de Microsoft Defender al Centro de seguridad de Microsoft 365
keywords: Introducción al Centro de seguridad de Microsoft 365, OATP, MDATP, MDO, MDE, panel único de cristal, portal convergente, portal de seguridad, portal de seguridad de defender
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
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
ms.openlocfilehash: 96d5a3bdbd0acbf428f01cc3bb5afefaa95950b4
ms.sourcegitcommit: 78f48304f990e969a052fe6536b2e8d6856e1086
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "50242986"
---
# <a name="provide-managed-security-service-provider-mssp-access"></a><span data-ttu-id="91a92-104">Proporcionar acceso de proveedor de servicios de seguridad administrados (MSSP)</span><span class="sxs-lookup"><span data-stu-id="91a92-104">Provide managed security service provider (MSSP) access</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

<span data-ttu-id="91a92-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="91a92-105">**Applies to:**</span></span>

- [<span data-ttu-id="91a92-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="91a92-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)
- [<span data-ttu-id="91a92-107">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="91a92-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)

<span data-ttu-id="91a92-108">Para implementar una solución de acceso delegado multiinquilino, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="91a92-108">To implement a multi-tenant delegated access solution, take the following steps:</span></span>

1. <span data-ttu-id="91a92-109">Habilite [el control de acceso basado en roles](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac) en Defender para puntos de conexión en el Centro de seguridad de Microsoft 365 y conéctese con grupos de Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="91a92-109">Enable [role-based access control](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac) in Defender for Endpoint in Microsoft 365 security center and connect with Azure Active Directory (Azure AD) groups.</span></span>

2. <span data-ttu-id="91a92-110">Configurar [paquetes de acceso de gobierno](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview) para la solicitud de acceso y el aprovisionamiento.</span><span class="sxs-lookup"><span data-stu-id="91a92-110">Configure [Governance Access Packages](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview) for access request and provisioning.</span></span>

3. <span data-ttu-id="91a92-111">Administrar solicitudes de acceso y auditorías [en Microsoft Myaccess](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-request-approve).</span><span class="sxs-lookup"><span data-stu-id="91a92-111">Manage access requests and audits in [Microsoft Myaccess](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-request-approve).</span></span>

## <a name="enable-role-based-access-controls-in-microsoft-defender-for-endpoint-in-microsoft-365-security-center"></a><span data-ttu-id="91a92-112">Habilitar controles de acceso basados en roles en Microsoft Defender para puntos de conexión en el Centro de seguridad de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="91a92-112">Enable role-based access controls in Microsoft Defender for Endpoint in Microsoft 365 security center</span></span>

1. <span data-ttu-id="91a92-113">**Crear grupos de acceso para recursos de MSSP en AAD de cliente: grupos**</span><span class="sxs-lookup"><span data-stu-id="91a92-113">**Create access groups for MSSP resources in Customer AAD: Groups**</span></span>

    <span data-ttu-id="91a92-114">Estos grupos se vincularán a los roles que cree en Defender para puntos de conexión en el Centro de seguridad de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="91a92-114">These groups will be linked to the Roles you create in Defender for Endpoint in Microsoft 365 security center.</span></span> <span data-ttu-id="91a92-115">Para ello, en el inquilino de AD del cliente, cree tres grupos.</span><span class="sxs-lookup"><span data-stu-id="91a92-115">To do so, in the customer AD tenant, create three groups.</span></span> <span data-ttu-id="91a92-116">En nuestro enfoque de ejemplo, creamos los siguientes grupos:</span><span class="sxs-lookup"><span data-stu-id="91a92-116">In our example approach, we create the following groups:</span></span>

    - <span data-ttu-id="91a92-117">Analista de nivel 1</span><span class="sxs-lookup"><span data-stu-id="91a92-117">Tier 1 Analyst</span></span> 
    - <span data-ttu-id="91a92-118">Analista de nivel 2</span><span class="sxs-lookup"><span data-stu-id="91a92-118">Tier 2 Analyst</span></span> 
    - <span data-ttu-id="91a92-119">Aprobadores de analista de MSSP</span><span class="sxs-lookup"><span data-stu-id="91a92-119">MSSP Analyst Approvers</span></span>  


2. <span data-ttu-id="91a92-120">Crear roles de Defender para puntos de conexión para niveles de acceso adecuados en Customer Defender para Endpoint en grupos y roles del Centro de seguridad de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="91a92-120">Create Defender for Endpoint roles for appropriate access levels in Customer Defender for Endpoint in Microsoft 365 security center roles and groups.</span></span>

    <span data-ttu-id="91a92-121">Para habilitar RBAC en el Centro de seguridad de Microsoft 365 del cliente, obtenga acceso a los roles permisos > Extremos & grupos **> Roles** con una cuenta de usuario con derechos de administrador global o administrador de seguridad.</span><span class="sxs-lookup"><span data-stu-id="91a92-121">To enable RBAC in the customer Microsoft 365 security center, access **Permissions >  Endpoints roles & groups > Roles** with a user account with Global Administrator or Security Administrator rights.</span></span>

    ![Imagen del acceso de MSSP](../../media/mssp-access.png)

    <span data-ttu-id="91a92-123">A continuación, cree roles RBAC para satisfacer las necesidades del nivel soC de MSSP.</span><span class="sxs-lookup"><span data-stu-id="91a92-123">Then, create RBAC roles to meet MSSP SOC Tier needs.</span></span> <span data-ttu-id="91a92-124">Vincule estos roles a los grupos de usuarios creados a través de "Grupos de usuarios asignados".</span><span class="sxs-lookup"><span data-stu-id="91a92-124">Link these roles to the created user groups via "Assigned user groups".</span></span>

    <span data-ttu-id="91a92-125">Dos roles posibles:</span><span class="sxs-lookup"><span data-stu-id="91a92-125">Two possible roles:</span></span>

    - <span data-ttu-id="91a92-126">**Analistas de nivel 1**</span><span class="sxs-lookup"><span data-stu-id="91a92-126">**Tier 1 Analysts**</span></span> <br>
      <span data-ttu-id="91a92-127">Realice todas las acciones excepto la respuesta en directo y administre la configuración de seguridad.</span><span class="sxs-lookup"><span data-stu-id="91a92-127">Perform all actions except for live response and manage security settings.</span></span>

    - <span data-ttu-id="91a92-128">**Analistas de nivel 2**</span><span class="sxs-lookup"><span data-stu-id="91a92-128">**Tier 2 Analysts**</span></span> <br>
      <span data-ttu-id="91a92-129">Capacidades de nivel 1 con adición a [la respuesta en directo](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response)</span><span class="sxs-lookup"><span data-stu-id="91a92-129">Tier 1 capabilities with the addition to [live response](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response)</span></span>

    <span data-ttu-id="91a92-130">Para obtener más información, vea [Usar control de acceso basado en roles.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)</span><span class="sxs-lookup"><span data-stu-id="91a92-130">For more information, see [Use role-based access control](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac).</span></span>



## <a name="configure-governance-access-packages"></a><span data-ttu-id="91a92-131">Configurar paquetes de acceso de gobierno</span><span class="sxs-lookup"><span data-stu-id="91a92-131">Configure Governance Access Packages</span></span>

1.  <span data-ttu-id="91a92-132">**Agregar MSSP como organización conectada en AAD de cliente: Gobierno de identidades**</span><span class="sxs-lookup"><span data-stu-id="91a92-132">**Add MSSP as Connected Organization in Customer AAD: Identity Governance**</span></span>
    
    <span data-ttu-id="91a92-133">Agregar el MSSP como organización conectada permitirá que el MSSP solicite y tenga accesos aprovisionados.</span><span class="sxs-lookup"><span data-stu-id="91a92-133">Adding the MSSP as a connected organization will allow the MSSP to request and have accesses provisioned.</span></span> 

    <span data-ttu-id="91a92-134">Para ello, en el inquilino de AD del cliente, acceda a Identity Governance: Organización conectada.</span><span class="sxs-lookup"><span data-stu-id="91a92-134">To do so, in the customer AD tenant, access Identity Governance: Connected organization.</span></span> <span data-ttu-id="91a92-135">Agregue una nueva organización y busque su inquilino de MSSP Analyst a través del identificador de inquilino o dominio.</span><span class="sxs-lookup"><span data-stu-id="91a92-135">Add a new organization and search for your MSSP Analyst tenant via Tenant ID or Domain.</span></span> <span data-ttu-id="91a92-136">Se recomienda crear un inquilino de AD independiente para los analistas de MSSP.</span><span class="sxs-lookup"><span data-stu-id="91a92-136">We suggest creating a separate AD tenant for your MSSP Analysts.</span></span>

2. <span data-ttu-id="91a92-137">**Crear un catálogo de recursos en customer AAD: Identity Governance**</span><span class="sxs-lookup"><span data-stu-id="91a92-137">**Create a resource catalog in Customer AAD: Identity Governance**</span></span>

    <span data-ttu-id="91a92-138">Los catálogos de recursos son una colección lógica de paquetes de acceso, creados en el inquilino de AD del cliente.</span><span class="sxs-lookup"><span data-stu-id="91a92-138">Resource catalogs are a logical collection of access packages, created in the customer AD tenant.</span></span>

    <span data-ttu-id="91a92-139">Para ello, en el inquilino de AD del cliente, acceda a Identity Governance: Catalogs y agregue **New Catalog**.</span><span class="sxs-lookup"><span data-stu-id="91a92-139">To do so, in the customer AD tenant,  access Identity Governance: Catalogs, and add **New Catalog**.</span></span> <span data-ttu-id="91a92-140">En nuestro ejemplo, lo llamaremos **MSSP Accesses**.</span><span class="sxs-lookup"><span data-stu-id="91a92-140">In our example, we will call it **MSSP Accesses**.</span></span> 

    ![Imagen del nuevo catálogo](../../media/goverance-catalog.png)

    <span data-ttu-id="91a92-142">Para obtener más información, [vea Crear un catálogo de recursos.](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-catalog-create)</span><span class="sxs-lookup"><span data-stu-id="91a92-142">Further more information, see [Create a catalog of resources](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-catalog-create).</span></span>


3. <span data-ttu-id="91a92-143">**Crear paquetes de acceso para recursos MSSP Customer AAD: Identity Governance**</span><span class="sxs-lookup"><span data-stu-id="91a92-143">**Create access packages for MSSP resources Customer AAD: Identity Governance**</span></span>

    <span data-ttu-id="91a92-144">Los paquetes de acceso son la colección de derechos y accesos que se concederá a un solicitante tras su aprobación.</span><span class="sxs-lookup"><span data-stu-id="91a92-144">Access packages are the collection of rights and accesses that a requestor will be granted upon approval.</span></span> 

    <span data-ttu-id="91a92-145">Para ello, en el inquilino de AD del cliente, acceda a Identity Governance: Access Packages y agregue **New Access Package**.</span><span class="sxs-lookup"><span data-stu-id="91a92-145">To do so, in the customer AD tenant, access Identity Governance: Access Packages, and add **New Access Package**.</span></span> <span data-ttu-id="91a92-146">Crea un paquete de acceso para los aprobadores de MSSP y cada nivel de analista.</span><span class="sxs-lookup"><span data-stu-id="91a92-146">Create an access package for the MSSP approvers and each analyst tier.</span></span> <span data-ttu-id="91a92-147">Por ejemplo, la siguiente configuración de analista de nivel 1 crea un paquete de acceso que:</span><span class="sxs-lookup"><span data-stu-id="91a92-147">For example, the following Tier 1 Analyst configuration creates an access package that:</span></span>

    - <span data-ttu-id="91a92-148">Requiere que un miembro del grupo ad **MSSP Analyst Approvers** autorice nuevas solicitudes</span><span class="sxs-lookup"><span data-stu-id="91a92-148">Requires a member of the AD group **MSSP Analyst Approvers** to authorize new requests</span></span>
    - <span data-ttu-id="91a92-149">Tiene revisiones de acceso anuales, donde los analistas de SOC pueden solicitar una extensión de acceso</span><span class="sxs-lookup"><span data-stu-id="91a92-149">Has annual access reviews, where the SOC analysts can request an access extension</span></span>
    - <span data-ttu-id="91a92-150">Solo pueden solicitarlo los usuarios del inquilino soC de MSSP</span><span class="sxs-lookup"><span data-stu-id="91a92-150">Can only be requested by users in the MSSP SOC Tenant</span></span>
    - <span data-ttu-id="91a92-151">El acceso automático expira después de 365 días</span><span class="sxs-lookup"><span data-stu-id="91a92-151">Access auto expires after 365 days</span></span>

    ![Imagen del nuevo paquete de acceso](../../media/new-access-package.png)

    <span data-ttu-id="91a92-153">Para obtener más información, vea [Crear un nuevo paquete de acceso.](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-access-package-create)</span><span class="sxs-lookup"><span data-stu-id="91a92-153">For more information, see [Create a new access package](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-access-package-create).</span></span>


4. <span data-ttu-id="91a92-154">**Proporcionar un vínculo de solicitud de acceso a recursos de MSSP desde AAD de cliente: Gobierno de identidades**</span><span class="sxs-lookup"><span data-stu-id="91a92-154">**Provide access request link to MSSP resources from Customer AAD: Identity Governance**</span></span>

    <span data-ttu-id="91a92-155">Los analistas de SOC de MSSP usan el vínculo mi portal de acceso para solicitar acceso a través de los paquetes de acceso creados.</span><span class="sxs-lookup"><span data-stu-id="91a92-155">The My Access portal link is used by MSSP SOC analysts to request access via the access packages created.</span></span> <span data-ttu-id="91a92-156">El vínculo es duradero, lo que significa que el mismo vínculo puede usarse con el tiempo para nuevos analistas.</span><span class="sxs-lookup"><span data-stu-id="91a92-156">The link is durable, meaning the same link may be used over time for new analysts.</span></span> <span data-ttu-id="91a92-157">La solicitud de analista entra en una cola para su aprobación por parte de los aprobadores del analista **de MSSP**.</span><span class="sxs-lookup"><span data-stu-id="91a92-157">The analyst request goes into a queue for approval by the **MSSP Analyst Approvers**.</span></span>


    ![Imagen de las propiedades de acceso](../../media/access-properties.png)

    <span data-ttu-id="91a92-159">El vínculo se encuentra en la página de información general de cada paquete de acceso.</span><span class="sxs-lookup"><span data-stu-id="91a92-159">The link is located on the overview page of each access package.</span></span>

## <a name="manage-access"></a><span data-ttu-id="91a92-160">Administrar el acceso</span><span class="sxs-lookup"><span data-stu-id="91a92-160">Manage access</span></span> 

1. <span data-ttu-id="91a92-161">Revise y autorice las solicitudes de acceso en El cliente y/o MSSP myaccess.</span><span class="sxs-lookup"><span data-stu-id="91a92-161">Review and authorize access requests in Customer and/or MSSP myaccess.</span></span>

    <span data-ttu-id="91a92-162">Las solicitudes de acceso las administran los miembros del grupo Aprobadores de analistas de MSSP en el cliente Mi acceso.</span><span class="sxs-lookup"><span data-stu-id="91a92-162">Access requests are managed in the customer My Access, by members of the MSSP Analyst Approvers group.</span></span>

    <span data-ttu-id="91a92-163">Para ello, accede a myaccess del cliente mediante:  `https://myaccess.microsoft.com/@<Customer Domain >` .</span><span class="sxs-lookup"><span data-stu-id="91a92-163">To do so, access the customer's myaccess using:  `https://myaccess.microsoft.com/@<Customer Domain >`.</span></span> 

    <span data-ttu-id="91a92-164">Ejemplo:  `https://myaccess.microsoft.com/@M365x440XXX.onmicrosoft.com#/`</span><span class="sxs-lookup"><span data-stu-id="91a92-164">Example:  `https://myaccess.microsoft.com/@M365x440XXX.onmicrosoft.com#/`</span></span>   
2. <span data-ttu-id="91a92-165">Aprobar o denegar solicitudes en la **sección Aprobaciones** de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="91a92-165">Approve or deny requests in the **Approvals** section of the UI.</span></span>

     <span data-ttu-id="91a92-166">En este punto, se ha aprovisionado el acceso de analista y cada analista debe poder acceder al Centro de seguridad de Microsoft 365 del cliente:</span><span class="sxs-lookup"><span data-stu-id="91a92-166">At this point, analyst access has been provisioned, and each analyst should be able to access the customer's Microsoft 365 Security Center:</span></span> 

    <span data-ttu-id="91a92-167">`https://security.microsoft.com/?tid=<CustomerTenantId>` con los permisos y roles que se asignaron.</span><span class="sxs-lookup"><span data-stu-id="91a92-167">`https://security.microsoft.com/?tid=<CustomerTenantId>` with the permissions and roles they were assigned.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="91a92-168">Actualmente, el acceso delegado a Microsoft Defender para Endpoint en el Centro de seguridad de Microsoft 365 permite el acceso a un único inquilino por ventana del explorador.</span><span class="sxs-lookup"><span data-stu-id="91a92-168">Delegated access to Microsoft Defender for Endpoint in the Microsoft 365 security center currently allows access to a single tenant per browser window.</span></span> 