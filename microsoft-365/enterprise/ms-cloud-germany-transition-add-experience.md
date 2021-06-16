---
title: Actividades posteriores a la migración de Microsoft Cloud Deutschland
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/11/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: 'Resumen: actividades posteriores a la migración después de pasar de Microsoft Cloud Germany (Microsoft Cloud Deutschland) a Office 365 servicios en la nueva región del centro de datos alemán.'
ms.openlocfilehash: 3659ce8ffa3424c3521c8f8954be88c7d53d0a51
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/14/2021
ms.locfileid: "52930420"
---
# <a name="post-migration-activities-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="79b6d-103">Actividades posteriores a la migración de Microsoft Cloud Deutschland</span><span class="sxs-lookup"><span data-stu-id="79b6d-103">Post-migration activities for the migration from Microsoft Cloud Deutschland</span></span>

<span data-ttu-id="79b6d-104">Las secciones siguientes proporcionan actividades posteriores a la migración para varios servicios después de pasar de Microsoft Cloud Germany (Microsoft Cloud Deutschland) a Office 365 servicios en la nueva región del centro de datos alemán.</span><span class="sxs-lookup"><span data-stu-id="79b6d-104">The following sections provide post-migration activities for multiple services after moving from Microsoft Cloud Germany (Microsoft Cloud Deutschland) to Office 365 services in the new German datacenter region.</span></span>

## <a name="azure-ad"></a><span data-ttu-id="79b6d-105">Azure AD</span><span class="sxs-lookup"><span data-stu-id="79b6d-105">Azure AD</span></span>
<!-- This AAD Endpoints comparison table could be added to the documentation, not finally decided.
### Azure AD Endpoints
**Applies to:** All customers

After the cut over to Azure AD is complete, the organization is fully using Office 365 services and is no longer connected to Microsoft Cloud Deutschland and the endpoints cannot be used anymore. At this point, the customer needs to ensure that all applications are using the endpoints for the new German datacenter region.
The following table provides an overview about which endpoints will replace the previously used endpoints in Microsoft Cloud Germany (Microsoft Cloud Deutschland). 

|Endpoint in Microsoft Cloud Germany  |Endpoint in the new German datacenter region  |
|:---------|:---------|
|becws.microsoftonline.de<br>provisioningapi.microsoftonline.de |becws.microsoftonline.com<br>provisioningapi.microsoftonline.com |
|adminwebservice.microsoftonline.de |adminwebservice.microsoftonline.com |
|login.microsoftonline.de<br>logincert.microsoftonline.de<br>sts.microsoftonline.de |login.microsoftonline.com<br>login.windows.net<br>logincert.microsoftonline.com<br>accounts.accesscontrol.windows.net |
|enterpriseregistration.microsoftonline.de |enterpriseregistration.windows.net |
|graph.cloudapi.de |graph.windows.net |
|graph.microsoft.de |graph.microsoft.com |
|||
-->

### <a name="azure-ad-federated-authentication-with-ad-fs"></a><span data-ttu-id="79b6d-106">Autenticación federada de Azure AD con AD FS</span><span class="sxs-lookup"><span data-stu-id="79b6d-106">Azure AD federated authentication with AD FS</span></span>
<span data-ttu-id="79b6d-107">**Se aplica a:** Todos los clientes que usan autenticación federada con AD FS</span><span class="sxs-lookup"><span data-stu-id="79b6d-107">**Applies to:** All customers using federated authentication with AD FS</span></span>

| <span data-ttu-id="79b6d-108">Pasos</span><span class="sxs-lookup"><span data-stu-id="79b6d-108">Step(s)</span></span> | <span data-ttu-id="79b6d-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="79b6d-109">Description</span></span> | <span data-ttu-id="79b6d-110">Impacto</span><span class="sxs-lookup"><span data-stu-id="79b6d-110">Impact</span></span> |
|:-------|:-------|:-------|
| <span data-ttu-id="79b6d-111">Quitar confianzas de usuario de confianza de Microsoft Cloud Deutschland AD FS.</span><span class="sxs-lookup"><span data-stu-id="79b6d-111">Remove relying party trusts from Microsoft Cloud Deutschland AD FS.</span></span> | <span data-ttu-id="79b6d-112">Una vez completado el recorte a Azure AD, la organización usa completamente los servicios Office 365 y ya no está conectada a Microsoft Cloud Deutschland.</span><span class="sxs-lookup"><span data-stu-id="79b6d-112">After the cut-over to Azure AD is complete, the organization is fully using Office 365 services and is no longer connected to Microsoft Cloud Deutschland.</span></span> <span data-ttu-id="79b6d-113">En este punto, el cliente debe quitar la confianza de usuario de confianza a los puntos de conexión de Microsoft Cloud Deutschland.</span><span class="sxs-lookup"><span data-stu-id="79b6d-113">At this point, the customer needs to remove the relying party trust to the Microsoft Cloud Deutschland endpoints.</span></span> <span data-ttu-id="79b6d-114">Esto solo se puede hacer cuando ninguna de las aplicaciones del cliente apunta a puntos de conexión de Microsoft Cloud Deutschland cuando Azure AD se aprovecha como proveedor de identidades (IdP).</span><span class="sxs-lookup"><span data-stu-id="79b6d-114">This can only be done when none of the customer's applications points to Microsoft Cloud Deutschland endpoints when Azure AD is leveraged as an Identity Provider (IdP).</span></span> | <span data-ttu-id="79b6d-115">Organizaciones de autenticación federada</span><span class="sxs-lookup"><span data-stu-id="79b6d-115">Federated Authentication organizations</span></span> | 
||||

<!--
    Question from ckinder
    The following paragraph is not clear
-->
### <a name="group-approvals"></a><span data-ttu-id="79b6d-116">Aprobaciones de grupo</span><span class="sxs-lookup"><span data-stu-id="79b6d-116">Group approvals</span></span>
<span data-ttu-id="79b6d-117">**Se aplica a:** Usuarios finales cuyas solicitudes de aprobación de grupo de Azure AD no se aprobaron en los últimos 30 días antes de la migración</span><span class="sxs-lookup"><span data-stu-id="79b6d-117">**Applies to:** End-users whose Azure AD group approval requests weren't approved in the last 30 days before migration</span></span> 

| <span data-ttu-id="79b6d-118">Pasos</span><span class="sxs-lookup"><span data-stu-id="79b6d-118">Step(s)</span></span> | <span data-ttu-id="79b6d-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="79b6d-119">Description</span></span> | <span data-ttu-id="79b6d-120">Impacto</span><span class="sxs-lookup"><span data-stu-id="79b6d-120">Impact</span></span> |
|:-------|:-------|:-------|
| <span data-ttu-id="79b6d-121">Las solicitudes para unirse a un grupo de Azure AD en los últimos 30 días antes de la migración tendrán que volver a solicitarse si la solicitud original no se aprobó.</span><span class="sxs-lookup"><span data-stu-id="79b6d-121">Requests to join an Azure AD group in the last 30 days before migration will need to be requested again if the original request wasn't approved.</span></span> | <span data-ttu-id="79b6d-122">Los clientes del usuario final tendrán que usar el panel de Access para enviar una solicitud para unirse de nuevo a un grupo de Azure AD si dichas solicitudes no se aprobaron en los últimos 30 días antes de la migración.</span><span class="sxs-lookup"><span data-stu-id="79b6d-122">End-user customers will need to use the Access panel to submit a request to join an Azure AD group again if those requests weren't approved in the last 30 days before the migration.</span></span> |  <span data-ttu-id="79b6d-123">Como usuario final:</span><span class="sxs-lookup"><span data-stu-id="79b6d-123">As an end-user:</span></span> <ol><li><span data-ttu-id="79b6d-124">Vaya al [panel De acceso](https://account.activedirectory.windowsazure.com/r#/joinGroups).</span><span class="sxs-lookup"><span data-stu-id="79b6d-124">Navigate to [Access panel](https://account.activedirectory.windowsazure.com/r#/joinGroups).</span></span></li><li><span data-ttu-id="79b6d-125">Busque un grupo de Azure AD para el que la aprobación de pertenencia estaba pendiente durante los 30 días antes de la migración.</span><span class="sxs-lookup"><span data-stu-id="79b6d-125">Find an Azure AD group for which membership approval was pending during the 30 days before migration.</span></span></li><li><span data-ttu-id="79b6d-126">Solicitar unirse de nuevo al grupo de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="79b6d-126">Request to join the Azure AD group again.</span></span></li></ol> <span data-ttu-id="79b6d-127">Las solicitudes para unirse a un grupo que están activos menos de 30 días antes de la migración no se pueden aprobar, a menos que se soliciten de nuevo después de la migración.</span><span class="sxs-lookup"><span data-stu-id="79b6d-127">Requests to join a group that are active less than 30 days before migration cannot be approved, unless they're requested again after migration.</span></span> |
||||

## <a name="custom-dns-updates"></a><span data-ttu-id="79b6d-128">Actualizaciones dns personalizadas</span><span class="sxs-lookup"><span data-stu-id="79b6d-128">Custom DNS updates</span></span>
<span data-ttu-id="79b6d-129">**Se aplica a:**  Todos los clientes que administran sus propias zonas DNS</span><span class="sxs-lookup"><span data-stu-id="79b6d-129">**Applies to:**  All customer managing their own DNS zones</span></span>

| <span data-ttu-id="79b6d-130">Pasos</span><span class="sxs-lookup"><span data-stu-id="79b6d-130">Step(s)</span></span> | <span data-ttu-id="79b6d-131">Descripción</span><span class="sxs-lookup"><span data-stu-id="79b6d-131">Description</span></span> | <span data-ttu-id="79b6d-132">Impacto</span><span class="sxs-lookup"><span data-stu-id="79b6d-132">Impact</span></span> |
|:------|:-------|:-------|
| <span data-ttu-id="79b6d-133">Actualice los servicios DNS locales para los Office 365 de servicios locales.</span><span class="sxs-lookup"><span data-stu-id="79b6d-133">Update on-premises DNS services for Office 365 services endpoints.</span></span> | <span data-ttu-id="79b6d-134">Las entradas DNS administradas por el cliente que apuntan a Microsoft Cloud Deutschland deben actualizarse para que apunten a los puntos de conexión Office 365 servicios globales.</span><span class="sxs-lookup"><span data-stu-id="79b6d-134">Customer-managed DNS entries that point to Microsoft Cloud Deutschland need to be updated to point to the Office 365 Global services endpoints.</span></span> <span data-ttu-id="79b6d-135">Consulte Dominios [en el centro de administración Microsoft 365 y](https://admin.microsoft.com/Adminportal/Home#/Domains) aplique los cambios en la configuración de DNS.</span><span class="sxs-lookup"><span data-stu-id="79b6d-135">Please refer to [Domains in the Microsoft 365 admin center](https://admin.microsoft.com/Adminportal/Home#/Domains) and apply the changes in your DNS configuration.</span></span> | <span data-ttu-id="79b6d-136">Si no lo hace, puede producirse un error en el servicio o en clientes de software.</span><span class="sxs-lookup"><span data-stu-id="79b6d-136">Failure to do so may result in failure of the service or of software clients.</span></span> |
||||

## <a name="third-party-services"></a><span data-ttu-id="79b6d-137">Servicios de terceros</span><span class="sxs-lookup"><span data-stu-id="79b6d-137">Third-party services</span></span>
<span data-ttu-id="79b6d-138">**Se aplica a:** Clientes que usan servicios de terceros para Office 365 de servicios</span><span class="sxs-lookup"><span data-stu-id="79b6d-138">**Applies to:** Customers using third-party services for Office 365 services endpoints</span></span>

| <span data-ttu-id="79b6d-139">Pasos</span><span class="sxs-lookup"><span data-stu-id="79b6d-139">Step(s)</span></span> | <span data-ttu-id="79b6d-140">Descripción</span><span class="sxs-lookup"><span data-stu-id="79b6d-140">Description</span></span> | <span data-ttu-id="79b6d-141">Impacto</span><span class="sxs-lookup"><span data-stu-id="79b6d-141">Impact</span></span> |
|:-------|:-------|:-------|
| <span data-ttu-id="79b6d-142">Actualice los partners y los servicios de terceros para los Office 365 de servicios de terceros.</span><span class="sxs-lookup"><span data-stu-id="79b6d-142">Update partners and third-party services for Office 365 services endpoints.</span></span> | <ul><li><span data-ttu-id="79b6d-143">Los servicios y asociados de terceros que apuntan a Office 365 Alemania deben actualizarse para que apunten a los puntos de conexión Office 365 de servicios.</span><span class="sxs-lookup"><span data-stu-id="79b6d-143">Third-party services and partners that point to Office 365 Germany need to be updated to point to the Office 365 services endpoints.</span></span> <span data-ttu-id="79b6d-144">Ejemplo: vuelva a registrar, en alineación con sus proveedores y asociados, la versión de la aplicación de galería de aplicaciones, si está disponible.</span><span class="sxs-lookup"><span data-stu-id="79b6d-144">Example: Re-register, in alignment with your vendors and partners, the gallery app version of applications, if available.</span></span> </li><li><span data-ttu-id="79b6d-145">Apunte todas las aplicaciones personalizadas que aprovechan Graph API de `graph.microsoft.de` a `graph.microsoft.com` .</span><span class="sxs-lookup"><span data-stu-id="79b6d-145">Point all custom applications that leverage Graph API from `graph.microsoft.de` to `graph.microsoft.com`.</span></span> <span data-ttu-id="79b6d-146">Otras API con puntos de conexión modificados también deben actualizarse, si se aprovechan.</span><span class="sxs-lookup"><span data-stu-id="79b6d-146">Other APIs with changed endpoints also need to be updated, if leveraged.</span></span> </li><li><span data-ttu-id="79b6d-147">Cambie todas las aplicaciones empresariales que no son de primera persona para redirigir a los puntos de conexión mundiales.</span><span class="sxs-lookup"><span data-stu-id="79b6d-147">Change all non-first-party enterprise applications to redirect to the worldwide endpoints.</span></span> </li></ul>| <span data-ttu-id="79b6d-148">Acción necesaria.</span><span class="sxs-lookup"><span data-stu-id="79b6d-148">Required action.</span></span> <span data-ttu-id="79b6d-149">Si no lo hace, puede producirse un error en el servicio o en clientes de software.</span><span class="sxs-lookup"><span data-stu-id="79b6d-149">Failure to do so may result in failure of the service or of software clients.</span></span> |
||||