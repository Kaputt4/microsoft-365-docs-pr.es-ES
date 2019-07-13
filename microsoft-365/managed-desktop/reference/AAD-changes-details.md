---
title: Detalles de inquilinos de Azure Active Directory
description: En este tema se describen los cambios realizados en la cuenta de AAD al inscribirse en el escritorio administrado de Microsoft
keywords: Escritorio administrado de Microsoft, Microsoft 365, Service, Documentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.openlocfilehash: 6b2b30d8dedba1086bfa9268fb0fdbce20367c20
ms.sourcegitcommit: dd426c686b52cf79325f11022b2d99bc45285577
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/12/2019
ms.locfileid: "35643951"
---
# <a name="azure-active-directory-tenant-details"></a><span data-ttu-id="35584-104">Detalles de inquilinos de Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="35584-104">Azure Active Directory tenant details</span></span>
<span data-ttu-id="35584-105">{Gory detalles sobre cuentas, llamadas API, perms, etc., etc.}</span><span class="sxs-lookup"><span data-stu-id="35584-105">{gory details about accounts, API calls, perms, etc., etc.}</span></span>


## <a name="data-transmitted-to-and-from-your-aad-account"></a><span data-ttu-id="35584-106">Datos que se transmiten a y desde la cuenta de AAD</span><span class="sxs-lookup"><span data-stu-id="35584-106">Data transmitted to and from your AAD account</span></span>


<span data-ttu-id="35584-107">Datos enviados a su cuenta desde Microsoft:</span><span class="sxs-lookup"><span data-stu-id="35584-107">Data sent to your account from Microsoft:</span></span>

- <span data-ttu-id="35584-108">Nombres de grupo</span><span class="sxs-lookup"><span data-stu-id="35584-108">Group names</span></span>
- <span data-ttu-id="35584-109">Configuración de la Directiva de seguridad</span><span class="sxs-lookup"><span data-stu-id="35584-109">Security policy configuration</span></span>
- <span data-ttu-id="35584-110">Pedidos de dispositivo</span><span class="sxs-lookup"><span data-stu-id="35584-110">Device orders</span></span>
- <span data-ttu-id="35584-111">Cuentas de usuario (msadmin, MSTest, mwaas_soc_ro, mwaas_wdgsoc)</span><span class="sxs-lookup"><span data-stu-id="35584-111">User accounts (msadmin, mstest, mwaas_soc_ro, mwaas_wdgsoc)</span></span>
- <span data-ttu-id="35584-112">Asignación de licencias de E5 a las cuentas de usuario</span><span class="sxs-lookup"><span data-stu-id="35584-112">E5 License assignment to the user accounts</span></span>
- <span data-ttu-id="35584-113">Directivas de Windows Update para anillos de actualización</span><span class="sxs-lookup"><span data-stu-id="35584-113">Windows update policies for update rings</span></span>

<span data-ttu-id="35584-114">Datos enviados a Microsoft desde su cuenta:</span><span class="sxs-lookup"><span data-stu-id="35584-114">Data sent to Microsoft from your account:</span></span>

- <span data-ttu-id="35584-115">Datos de actualización de dispositivos, uso y confiabilidad</span><span class="sxs-lookup"><span data-stu-id="35584-115">Device update, usage and reliability data</span></span>
- <span data-ttu-id="35584-116">Datos de confiabilidad y de implementación de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="35584-116">App deployment and reliability data</span></span>
- <span data-ttu-id="35584-117">Actualización y datos de implementación de la Directiva de seguridad</span><span class="sxs-lookup"><span data-stu-id="35584-117">Update and security policy deployment data</span></span>
- <span data-ttu-id="35584-118">Usuarios asignados a dispositivos</span><span class="sxs-lookup"><span data-stu-id="35584-118">Users assigned to devices</span></span>  

<span data-ttu-id="35584-119">Los datos transmitidos desde su cuenta se almacenan en Azure SQL Databases en el inquilino de Microsoft hospedado en Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="35584-119">Data transmitted from your account is stored in Azure SQL databases in the Microsoft tenant hosted in the USA.</span></span> <span data-ttu-id="35584-120">Los datos se almacenan y controlan de acuerdo con las directivas descritas en {Microsoft Azure Security}.</span><span class="sxs-lookup"><span data-stu-id="35584-120">Data is stored and handled in accordance the policies described in {Microsoft Azure security}.</span></span> 

## <a name="api-permissions-and-calls"></a><span data-ttu-id="35584-121">Permisos y llamadas de la API</span><span class="sxs-lookup"><span data-stu-id="35584-121">API permissions and calls</span></span>

<span data-ttu-id="35584-122">**Durante la inscripción:**</span><span class="sxs-lookup"><span data-stu-id="35584-122">**During enrollment:**</span></span>

<span data-ttu-id="35584-123">Permisos de API:</span><span class="sxs-lookup"><span data-stu-id="35584-123">API permissions:</span></span>
- <span data-ttu-id="35584-124">DeviceManagementServiceConfig.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="35584-124">DeviceManagementServiceConfig.ReadWrite.All</span></span>
- <span data-ttu-id="35584-125">Directory.AccessAsUser.All</span><span class="sxs-lookup"><span data-stu-id="35584-125">Directory.AccessAsUser.All</span></span>
- <span data-ttu-id="35584-126">User.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="35584-126">User.ReadWrite.All</span></span>
- <span data-ttu-id="35584-127">DeviceManagementConfiguration.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="35584-127">DeviceManagementConfiguration.ReadWrite.All</span></span>
- <span data-ttu-id="35584-128">DeviceManagementManagedDevices.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="35584-128">DeviceManagementManagedDevices.ReadWrite.All</span></span>
- <span data-ttu-id="35584-129">Group.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="35584-129">Group.ReadWrite.All</span></span>

<span data-ttu-id="35584-130">Llamadas a la API:</span><span class="sxs-lookup"><span data-stu-id="35584-130">API calls:</span></span>
- <span data-ttu-id="35584-131">PUBLICAR/organization/{organizationId}/setMobileDeviceManagementAuthority</span><span class="sxs-lookup"><span data-stu-id="35584-131">POST /organization/{organizationId}/setMobileDeviceManagementAuthority</span></span>
- <span data-ttu-id="35584-132">GET/POST/directoryRoles/{id}/members</span><span class="sxs-lookup"><span data-stu-id="35584-132">GET/POST /directoryRoles/{id}/members</span></span>
- <span data-ttu-id="35584-133">GET/POST/users</span><span class="sxs-lookup"><span data-stu-id="35584-133">GET/POST /users</span></span>
- <span data-ttu-id="35584-134">GET/POST/Groups</span><span class="sxs-lookup"><span data-stu-id="35584-134">GET/POST /groups</span></span>
- <span data-ttu-id="35584-135">REVISIÓN/Groups/{ID}</span><span class="sxs-lookup"><span data-stu-id="35584-135">PATCH /groups/{id}</span></span>
- <span data-ttu-id="35584-136">GET/POST/deviceManagement/deviceConfigurations</span><span class="sxs-lookup"><span data-stu-id="35584-136">GET/POST /deviceManagement/deviceConfigurations</span></span>
- <span data-ttu-id="35584-137">OBTENER/deviceManagement/detectedApps</span><span class="sxs-lookup"><span data-stu-id="35584-137">GET /deviceManagement/detectedApps</span></span>

<span data-ttu-id="35584-138">**Tras la inscripción, durante la administración ordinaria:**</span><span class="sxs-lookup"><span data-stu-id="35584-138">**After enrollment, during ordinary management:**</span></span>

<span data-ttu-id="35584-139">Permisos de API:</span><span class="sxs-lookup"><span data-stu-id="35584-139">API permissions:</span></span>
- <span data-ttu-id="35584-140">DeviceManagementManagedDevices.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="35584-140">DeviceManagementManagedDevices.ReadWrite.All</span></span>
- <span data-ttu-id="35584-141">DeviceManagementApps.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="35584-141">DeviceManagementApps.ReadWrite.All</span></span>
- <span data-ttu-id="35584-142">DeviceManagementConfiguration.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="35584-142">DeviceManagementConfiguration.ReadWrite.All</span></span>
- <span data-ttu-id="35584-143">Reports.Read.All</span><span class="sxs-lookup"><span data-stu-id="35584-143">Reports.Read.All</span></span>
- <span data-ttu-id="35584-144">User.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="35584-144">User.ReadWrite.All</span></span>
- <span data-ttu-id="35584-145">Group.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="35584-145">Group.ReadWrite.All</span></span>
- <span data-ttu-id="35584-146">Directory.AccessAsUser.All</span><span class="sxs-lookup"><span data-stu-id="35584-146">Directory.AccessAsUser.All</span></span>

<span data-ttu-id="35584-147">Llamadas a la API:</span><span class="sxs-lookup"><span data-stu-id="35584-147">API calls:</span></span>
- <span data-ttu-id="35584-148">GET/POST/directoryRoles/{id}/members</span><span class="sxs-lookup"><span data-stu-id="35584-148">GET/POST /directoryRoles/{id}/members</span></span>
- <span data-ttu-id="35584-149">GET/PATCH/POST/users</span><span class="sxs-lookup"><span data-stu-id="35584-149">GET/PATCH/POST /users</span></span>
- <span data-ttu-id="35584-150">GET/POST/Groups</span><span class="sxs-lookup"><span data-stu-id="35584-150">GET/POST /groups</span></span>
- <span data-ttu-id="35584-151">REVISIÓN/Groups/{ID}</span><span class="sxs-lookup"><span data-stu-id="35584-151">PATCH /groups/{id}</span></span>
- <span data-ttu-id="35584-152">GET/POST/deviceManagement/deviceConfigurations</span><span class="sxs-lookup"><span data-stu-id="35584-152">GET/POST /deviceManagement/deviceConfigurations</span></span>
- <span data-ttu-id="35584-153">GET/POST/deviceAppManagement/mobileApps</span><span class="sxs-lookup"><span data-stu-id="35584-153">GET/POST /deviceAppManagement/mobileApps</span></span>
- <span data-ttu-id="35584-154">OBTENER/deviceManagement/detectedApps</span><span class="sxs-lookup"><span data-stu-id="35584-154">GET /deviceManagement/detectedApps</span></span>
- <span data-ttu-id="35584-155">OBTENER/Devices</span><span class="sxs-lookup"><span data-stu-id="35584-155">GET /devices</span></span>
- <span data-ttu-id="35584-156">POST/users/{ID | userPrincipalName}/assignLicense</span><span class="sxs-lookup"><span data-stu-id="35584-156">POST /users/{id | userPrincipalName}/assignLicense</span></span>
- <span data-ttu-id="35584-157">OBTENER/subscribedSkus</span><span class="sxs-lookup"><span data-stu-id="35584-157">GET /subscribedSkus</span></span>

## <a name="accounts-used-by-microsoft-managed-desktop"></a><span data-ttu-id="35584-158">Cuentas usadas por el escritorio administrado por Microsoft</span><span class="sxs-lookup"><span data-stu-id="35584-158">Accounts used by Microsoft Managed Desktop</span></span>





| <span data-ttu-id="35584-159">Cuenta</span><span class="sxs-lookup"><span data-stu-id="35584-159">Account</span></span> | <span data-ttu-id="35584-160">Descripción</span><span class="sxs-lookup"><span data-stu-id="35584-160">Description</span></span>  | <span data-ttu-id="35584-161">Acceso condicional</span><span class="sxs-lookup"><span data-stu-id="35584-161">Conditional access</span></span>  | <span data-ttu-id="35584-162">Autenticación multifactor</span><span class="sxs-lookup"><span data-stu-id="35584-162">Multi-factor authentication</span></span>  | <span data-ttu-id="35584-163">Por qué es correcto</span><span class="sxs-lookup"><span data-stu-id="35584-163">Why this is OK</span></span> |
|---------|---------|---------|---------|--------------|
| <span data-ttu-id="35584-164">msadmin @ \* onmmicrosoft. com</span><span class="sxs-lookup"><span data-stu-id="35584-164">msadmin@\*onmmicrosoft.com</span></span> | <span data-ttu-id="35584-165">Cuenta de servicio limitada con privilegios de administrador, usada como Microsoft Intune y usuario administrador {¿qué es esto?}</span><span class="sxs-lookup"><span data-stu-id="35584-165">Limited service account with administrator privileges, used as a Microsoft Intune and User administrator {what's this?}</span></span> <span data-ttu-id="35584-166">para definir y configurar el inquilino para los dispositivos de escritorio modernos de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="35584-166">to define and configure the tenant for Microsoft Modern Desktop devices.</span></span><span data-ttu-id="35584-167">No tiene permisos de inicio de sesión interactivo; realiza operaciones solo a través del servicio.</span><span class="sxs-lookup"><span data-stu-id="35584-167">  Does not have interactive login permissions; performs operations only through the service.</span></span>  | <span data-ttu-id="35584-168">Excluido porque no se origina en la red</span><span class="sxs-lookup"><span data-stu-id="35584-168">Excluded, because it doesn't originate in your network</span></span>        | <span data-ttu-id="35584-169">Excluido porque no hay inicio de sesión interactivo</span><span class="sxs-lookup"><span data-stu-id="35584-169">Excluded because there is no interactive logon</span></span>        | <span data-ttu-id="35584-170">Contraseña almacenada en el almacén de claves de Azure</span><span class="sxs-lookup"><span data-stu-id="35584-170">Password stored in Azure Key Vault</span></span> |
| <span data-ttu-id="35584-171">MSTest @ \* onmmicrosoft. com</span><span class="sxs-lookup"><span data-stu-id="35584-171">mstest@\*onmmicrosoft.com</span></span>     |         |         |         |
| <span data-ttu-id="35584-172">mssupport @ \* onmmicrosoft. com</span><span class="sxs-lookup"><span data-stu-id="35584-172">mssupport@\*onmmicrosoft.com</span></span>     |         |         |         |
| <span data-ttu-id="35584-173">msadminint @ \* onmmicrosoft. com</span><span class="sxs-lookup"><span data-stu-id="35584-173">msadminint@\*onmmicrosoft.com</span></span>     |         |         |         |
