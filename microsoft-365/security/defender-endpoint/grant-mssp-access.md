---
title: Conceder acceso al proveedor de servicios de seguridad administrado (MSSP)
description: Siga los pasos necesarios para configurar la integración de MSSP con Microsoft Defender para endpoint
keywords: proveedor de servicios de seguridad administrados, mssp, configuración, integración
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 311903cdd1409f4ab997641cc842ff199ce2500d
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843111"
---
# <a name="grant-managed-security-service-provider-mssp-access-preview"></a><span data-ttu-id="4998e-104">Conceder acceso al proveedor de servicios de seguridad administrado (MSSP) (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="4998e-104">Grant managed security service provider (MSSP) access (preview)</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="4998e-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="4998e-105">**Applies to:**</span></span>
- [<span data-ttu-id="4998e-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="4998e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="4998e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4998e-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="4998e-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="4998e-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="4998e-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="4998e-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)

>[!IMPORTANT] 
><span data-ttu-id="4998e-110">Parte de la información se refiere a productos preliminares que pueden ser modificados sustancialmente antes de su lanzamiento comercial.</span><span class="sxs-lookup"><span data-stu-id="4998e-110">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="4998e-111">Microsoft no otorga garantías, expresas o implícitas, con respecto a la información que aquí se proporciona.</span><span class="sxs-lookup"><span data-stu-id="4998e-111">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="4998e-112">Para implementar una solución de acceso delegado multiinquilino, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="4998e-112">To implement a multi-tenant delegated access solution, take the following steps:</span></span>

1. <span data-ttu-id="4998e-113">Habilite [el control de acceso basado en roles](rbac.md) en Defender para endpoint y conéctese con grupos de Active Directory (AD).</span><span class="sxs-lookup"><span data-stu-id="4998e-113">Enable [role-based access control](rbac.md) in Defender for Endpoint and connect with Active Directory (AD) groups.</span></span>

2. <span data-ttu-id="4998e-114">Configurar [paquetes de acceso de gobierno](/azure/active-directory/governance/identity-governance-overview) para la solicitud de acceso y el aprovisionamiento.</span><span class="sxs-lookup"><span data-stu-id="4998e-114">Configure [Governance Access Packages](/azure/active-directory/governance/identity-governance-overview) for access request and provisioning.</span></span>

3. <span data-ttu-id="4998e-115">Administrar solicitudes de acceso y auditorías [en Microsoft Myaccess](/azure/active-directory/governance/entitlement-management-request-approve).</span><span class="sxs-lookup"><span data-stu-id="4998e-115">Manage access requests and audits in [Microsoft Myaccess](/azure/active-directory/governance/entitlement-management-request-approve).</span></span>

## <a name="enable-role-based-access-controls-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="4998e-116">Habilitar controles de acceso basados en roles en Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="4998e-116">Enable role-based access controls in Microsoft Defender for Endpoint</span></span>

1. <span data-ttu-id="4998e-117">**Crear grupos de acceso para recursos MSSP en Customer AAD: Groups**</span><span class="sxs-lookup"><span data-stu-id="4998e-117">**Create access groups for MSSP resources in Customer AAD: Groups**</span></span>

    <span data-ttu-id="4998e-118">Estos grupos se vincularán a los roles que cree en Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="4998e-118">These groups will be linked to the Roles you create in Defender for Endpoint.</span></span> <span data-ttu-id="4998e-119">Para ello, en el inquilino de AD del cliente, cree tres grupos.</span><span class="sxs-lookup"><span data-stu-id="4998e-119">To do so, in the customer AD tenant, create three groups.</span></span> <span data-ttu-id="4998e-120">En nuestro enfoque de ejemplo, creamos los siguientes grupos:</span><span class="sxs-lookup"><span data-stu-id="4998e-120">In our example approach, we create the following groups:</span></span>

    - <span data-ttu-id="4998e-121">Analista de nivel 1</span><span class="sxs-lookup"><span data-stu-id="4998e-121">Tier 1 Analyst</span></span> 
    - <span data-ttu-id="4998e-122">Analista de nivel 2</span><span class="sxs-lookup"><span data-stu-id="4998e-122">Tier 2 Analyst</span></span> 
    - <span data-ttu-id="4998e-123">Aprobadores de analistas de MSSP</span><span class="sxs-lookup"><span data-stu-id="4998e-123">MSSP Analyst Approvers</span></span>  


2. <span data-ttu-id="4998e-124">Cree roles de Defender para endpoint para niveles de acceso adecuados en Customer Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="4998e-124">Create Defender for Endpoint roles for appropriate access levels in Customer Defender for Endpoint.</span></span>

    <span data-ttu-id="4998e-125">Para habilitar RBAC en la cuenta de cliente Centro de seguridad de Microsoft Defender, acceda a **Configuración > Permissions > Roles** y "Activar roles", desde una cuenta de usuario con derechos de administrador global o administrador de seguridad.</span><span class="sxs-lookup"><span data-stu-id="4998e-125">To enable RBAC in the customer Microsoft Defender Security Center, access **Settings > Permissions > Roles** and "Turn on roles", from a user account with Global Administrator or Security Administrator rights.</span></span>

    ![Imagen del acceso de MSSP](images/mssp-access.png)

    <span data-ttu-id="4998e-127">A continuación, cree roles RBAC para satisfacer las necesidades de nivel SOC de MSSP.</span><span class="sxs-lookup"><span data-stu-id="4998e-127">Then, create RBAC roles to meet MSSP SOC Tier needs.</span></span> <span data-ttu-id="4998e-128">Vincule estos roles a los grupos de usuarios creados mediante "Grupos de usuarios asignados".</span><span class="sxs-lookup"><span data-stu-id="4998e-128">Link these roles to the created user groups via "Assigned user groups".</span></span>

    <span data-ttu-id="4998e-129">Dos roles posibles:</span><span class="sxs-lookup"><span data-stu-id="4998e-129">Two possible roles:</span></span>

    - <span data-ttu-id="4998e-130">**Analistas de nivel 1**</span><span class="sxs-lookup"><span data-stu-id="4998e-130">**Tier 1 Analysts**</span></span> <br>
      <span data-ttu-id="4998e-131">Realice todas las acciones excepto la respuesta en directo y administre la configuración de seguridad.</span><span class="sxs-lookup"><span data-stu-id="4998e-131">Perform all actions except for live response and manage security settings.</span></span>

    - <span data-ttu-id="4998e-132">**Analistas de nivel 2**</span><span class="sxs-lookup"><span data-stu-id="4998e-132">**Tier 2 Analysts**</span></span> <br>
      <span data-ttu-id="4998e-133">Capacidades de nivel 1 con la adición a [la respuesta en directo](live-response.md)</span><span class="sxs-lookup"><span data-stu-id="4998e-133">Tier 1 capabilities with the addition to [live response](live-response.md)</span></span>

    <span data-ttu-id="4998e-134">Para obtener más información, vea [Use role-based access control](rbac.md).</span><span class="sxs-lookup"><span data-stu-id="4998e-134">For more information, see [Use role-based access control](rbac.md).</span></span>



## <a name="configure-governance-access-packages"></a><span data-ttu-id="4998e-135">Configurar paquetes de acceso de gobierno</span><span class="sxs-lookup"><span data-stu-id="4998e-135">Configure Governance Access Packages</span></span>

1.  <span data-ttu-id="4998e-136">**Agregar MSSP como organización conectada en customer AAD: Identity Governance**</span><span class="sxs-lookup"><span data-stu-id="4998e-136">**Add MSSP as Connected Organization in Customer AAD: Identity Governance**</span></span>
    
    <span data-ttu-id="4998e-137">Agregar el MSSP como organización conectada permitirá al MSSP solicitar y tener accesos aprovisionados.</span><span class="sxs-lookup"><span data-stu-id="4998e-137">Adding the MSSP as a connected organization will allow the MSSP to request and have accesses provisioned.</span></span> 

    <span data-ttu-id="4998e-138">Para ello, en el inquilino de AD del cliente, acceda a Identity Governance: Connected organization.</span><span class="sxs-lookup"><span data-stu-id="4998e-138">To do so, in the customer AD tenant, access Identity Governance: Connected organization.</span></span> <span data-ttu-id="4998e-139">Agregue una nueva organización y busque el inquilino de MSSP Analyst a través del identificador de inquilino o dominio.</span><span class="sxs-lookup"><span data-stu-id="4998e-139">Add a new organization and search for your MSSP Analyst tenant via Tenant ID or Domain.</span></span> <span data-ttu-id="4998e-140">Se recomienda crear un inquilino de AD independiente para los analistas de MSSP.</span><span class="sxs-lookup"><span data-stu-id="4998e-140">We suggest creating a separate AD tenant for your MSSP Analysts.</span></span>

2. <span data-ttu-id="4998e-141">**Crear un catálogo de recursos en Customer AAD: Identity Governance**</span><span class="sxs-lookup"><span data-stu-id="4998e-141">**Create a resource catalog in Customer AAD: Identity Governance**</span></span>

    <span data-ttu-id="4998e-142">Los catálogos de recursos son una colección lógica de paquetes de acceso, creados en el inquilino de AD del cliente.</span><span class="sxs-lookup"><span data-stu-id="4998e-142">Resource catalogs are a logical collection of access packages, created in the customer AD tenant.</span></span>

    <span data-ttu-id="4998e-143">Para ello, en el inquilino de AD del cliente, acceda a Identity Governance: Catalogs y agregue **New Catalog**.</span><span class="sxs-lookup"><span data-stu-id="4998e-143">To do so, in the customer AD tenant,  access Identity Governance: Catalogs, and add **New Catalog**.</span></span> <span data-ttu-id="4998e-144">En nuestro ejemplo, lo llamaremos **MSSP Accesses**.</span><span class="sxs-lookup"><span data-stu-id="4998e-144">In our example, we will call it **MSSP Accesses**.</span></span> 

    ![Imagen del nuevo catálogo](images/goverance-catalog.png)

    <span data-ttu-id="4998e-146">Para obtener más información, vea [Create a catalog of resources](/azure/active-directory/governance/entitlement-management-catalog-create).</span><span class="sxs-lookup"><span data-stu-id="4998e-146">Further more information, see [Create a catalog of resources](/azure/active-directory/governance/entitlement-management-catalog-create).</span></span>


3. <span data-ttu-id="4998e-147">**Crear paquetes de acceso para recursos MSSP Customer AAD: Identity Governance**</span><span class="sxs-lookup"><span data-stu-id="4998e-147">**Create access packages for MSSP resources Customer AAD: Identity Governance**</span></span>

    <span data-ttu-id="4998e-148">Los paquetes de acceso son la colección de derechos y accesos que se concederá a un solicitante tras su aprobación.</span><span class="sxs-lookup"><span data-stu-id="4998e-148">Access packages are the collection of rights and accesses that a requestor will be granted upon approval.</span></span> 

    <span data-ttu-id="4998e-149">Para ello, en el inquilino de AD del cliente, acceda a Identity Governance: Access Packages y agregue **New Access Package**.</span><span class="sxs-lookup"><span data-stu-id="4998e-149">To do so, in the customer AD tenant, access Identity Governance: Access Packages, and add **New Access Package**.</span></span> <span data-ttu-id="4998e-150">Cree un paquete de acceso para los aprobadores de MSSP y cada nivel de analista.</span><span class="sxs-lookup"><span data-stu-id="4998e-150">Create an access package for the MSSP approvers and each analyst tier.</span></span> <span data-ttu-id="4998e-151">Por ejemplo, la siguiente configuración de Analista de nivel 1 crea un paquete de acceso que:</span><span class="sxs-lookup"><span data-stu-id="4998e-151">For example, the following Tier 1 Analyst configuration creates an access package that:</span></span>

    - <span data-ttu-id="4998e-152">Requiere que un miembro del grupo de AD **aprobadores de analistas de MSSP** autorice nuevas solicitudes</span><span class="sxs-lookup"><span data-stu-id="4998e-152">Requires a member of the AD group **MSSP Analyst Approvers** to authorize new requests</span></span>
    - <span data-ttu-id="4998e-153">Tiene revisiones de acceso anuales, donde los analistas de SOC pueden solicitar una extensión de acceso</span><span class="sxs-lookup"><span data-stu-id="4998e-153">Has annual access reviews, where the SOC analysts can request an access extension</span></span>
    - <span data-ttu-id="4998e-154">Los usuarios solo pueden solicitarlo en el inquilino soc de MSSP</span><span class="sxs-lookup"><span data-stu-id="4998e-154">Can only be requested by users in the MSSP SOC Tenant</span></span>
    - <span data-ttu-id="4998e-155">Access auto expira después de 365 días</span><span class="sxs-lookup"><span data-stu-id="4998e-155">Access auto expires after 365 days</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="4998e-156">![Imagen del nuevo paquete de acceso](images/new-access-package.png)</span><span class="sxs-lookup"><span data-stu-id="4998e-156">![Image of new access package](images/new-access-package.png)</span></span>

    <span data-ttu-id="4998e-157">Para obtener más información, vea [Create a new access package](/azure/active-directory/governance/entitlement-management-access-package-create).</span><span class="sxs-lookup"><span data-stu-id="4998e-157">For more information, see [Create a new access package](/azure/active-directory/governance/entitlement-management-access-package-create).</span></span>


4. <span data-ttu-id="4998e-158">**Proporcionar vínculo de solicitud de acceso a recursos MSSP desde customer AAD: Identity Governance**</span><span class="sxs-lookup"><span data-stu-id="4998e-158">**Provide access request link to MSSP resources from Customer AAD: Identity Governance**</span></span>

    <span data-ttu-id="4998e-159">Los analistas de SOC de MSSP usan el vínculo Portal de My Access para solicitar acceso a través de los paquetes de acceso creados.</span><span class="sxs-lookup"><span data-stu-id="4998e-159">The My Access portal link is used by MSSP SOC analysts to request access via the access packages created.</span></span> <span data-ttu-id="4998e-160">El vínculo es duradero, lo que significa que el mismo vínculo puede usarse con el tiempo para los nuevos analistas.</span><span class="sxs-lookup"><span data-stu-id="4998e-160">The link is durable, meaning the same link may be used over time for new analysts.</span></span> <span data-ttu-id="4998e-161">La solicitud de analista entra en una cola para su aprobación por parte de los aprobadores de analistas de **MSSP**.</span><span class="sxs-lookup"><span data-stu-id="4998e-161">The analyst request goes into a queue for approval by the **MSSP Analyst Approvers**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="4998e-162">![Imagen de las propiedades de access](images/access-properties.png)</span><span class="sxs-lookup"><span data-stu-id="4998e-162">![Image of access properties](images/access-properties.png)</span></span>

    <span data-ttu-id="4998e-163">El vínculo se encuentra en la página de información general de cada paquete de acceso.</span><span class="sxs-lookup"><span data-stu-id="4998e-163">The link is located on the overview page of each access package.</span></span>

## <a name="manage-access"></a><span data-ttu-id="4998e-164">Administrar el acceso</span><span class="sxs-lookup"><span data-stu-id="4998e-164">Manage access</span></span> 

1. <span data-ttu-id="4998e-165">Revise y autorice las solicitudes de acceso en Customer y/o MSSP myaccess.</span><span class="sxs-lookup"><span data-stu-id="4998e-165">Review and authorize access requests in Customer and/or MSSP myaccess.</span></span>

    <span data-ttu-id="4998e-166">Las solicitudes de acceso se administran en el cliente My Access, por miembros del grupo Aprobadores de analistas de MSSP.</span><span class="sxs-lookup"><span data-stu-id="4998e-166">Access requests are managed in the customer My Access, by members of the MSSP Analyst Approvers group.</span></span>

    <span data-ttu-id="4998e-167">Para ello, acceda a myaccess del cliente mediante:  `https://myaccess.microsoft.com/@<Customer Domain >` .</span><span class="sxs-lookup"><span data-stu-id="4998e-167">To do so, access the customer's myaccess using:  `https://myaccess.microsoft.com/@<Customer Domain >`.</span></span> 

    <span data-ttu-id="4998e-168">Ejemplo:  `https://myaccess.microsoft.com/@M365x440XXX.onmicrosoft.com#/`</span><span class="sxs-lookup"><span data-stu-id="4998e-168">Example:  `https://myaccess.microsoft.com/@M365x440XXX.onmicrosoft.com#/`</span></span>   
2. <span data-ttu-id="4998e-169">Aprobar o denegar solicitudes en la sección **Aprobaciones** de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="4998e-169">Approve or deny requests in the **Approvals** section of the UI.</span></span>

    <span data-ttu-id="4998e-170">En este momento, se ha aprovisionado el acceso de analistas y cada analista debe tener acceso a la información del Centro de seguridad de Microsoft Defender:`https://securitycenter.Microsoft.com/?tid=<CustomerTenantId>`</span><span class="sxs-lookup"><span data-stu-id="4998e-170">At this point, analyst access has been provisioned, and each analyst should be able to access the customer's Microsoft Defender Security Center: `https://securitycenter.Microsoft.com/?tid=<CustomerTenantId>`</span></span>

## <a name="related-topics"></a><span data-ttu-id="4998e-171">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="4998e-171">Related topics</span></span>
- [<span data-ttu-id="4998e-172">Acceder al portal de clientes de MSSP</span><span class="sxs-lookup"><span data-stu-id="4998e-172">Access the MSSP customer portal</span></span>](access-mssp-portal.md)
- [<span data-ttu-id="4998e-173">Configurar notificaciones de alerta</span><span class="sxs-lookup"><span data-stu-id="4998e-173">Configure alert notifications</span></span>](configure-mssp-notifications.md)
- [<span data-ttu-id="4998e-174">Capturar alertas del espacio empresarial del cliente</span><span class="sxs-lookup"><span data-stu-id="4998e-174">Fetch alerts from customer tenant</span></span>](fetch-alerts-mssp.md)



 

