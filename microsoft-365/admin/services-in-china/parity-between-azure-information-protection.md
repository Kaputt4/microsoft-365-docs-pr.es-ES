---
title: Paridad entre Azure Information Protection para Office 365 operado por 21Vianet y ofertas comerciales
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
ms.reviewer: arthurj
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- GEU150
- GEA150
description: Obtenga más información sobre Azure Information Protection (AIP) para Office 365 operado por 21Vianet y cómo configurarlo para los clientes de China.
monikerRange: o365-21vianet
ms.openlocfilehash: 50269749b5f4e544263f790ec9c7e4474af57219
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840306"
---
# <a name="parity-between-azure-information-protection-for-office-365-operated-by-21vianet-and-commercial-offerings"></a><span data-ttu-id="cb43f-103">Paridad entre Azure Information Protection para Office 365 operado por 21Vianet y ofertas comerciales</span><span class="sxs-lookup"><span data-stu-id="cb43f-103">Parity between Azure Information Protection for Office 365 operated by 21Vianet and commercial offerings</span></span>

<span data-ttu-id="cb43f-104">Aunque nuestro objetivo es ofrecer todas las funciones y características comerciales a los clientes de China con nuestra oferta de Azure Information Protection (AIP) para Office 365 operado por 21Vianet, nos gustaría resaltar algunas funciones que faltan.</span><span class="sxs-lookup"><span data-stu-id="cb43f-104">While our goal is to deliver all commercial features and functionality to customers in China with our Azure Information Protection (AIP) for Office 365 operated by 21Vianet offer, there's some missing functionality that we'd like to highlight.</span></span>

<span data-ttu-id="cb43f-105">La siguiente lista incluye las diferencias existentes entre Azure Information Protection para Office 365 operado por 21Vianet y nuestras ofertas comerciales a partir de enero de 2021:</span><span class="sxs-lookup"><span data-stu-id="cb43f-105">The following list includes the existing gaps between Azure Information Protection for Office 365 operated by 21Vianet and our commercial offerings as of January 2021:</span></span>

- <span data-ttu-id="cb43f-106">Information Rights Management (IRM) solo es compatible con Aplicaciones de Microsoft 365 para empresas (compilación 11731.10000 o posterior).</span><span class="sxs-lookup"><span data-stu-id="cb43f-106">Information Rights Management (IRM) is supported only for Microsoft 365 Apps for enterprise (build 11731.10000 or higher).</span></span> <span data-ttu-id="cb43f-107">Office 2010, Office 2013 y otras versiones de Office 2016 no son compatibles.</span><span class="sxs-lookup"><span data-stu-id="cb43f-107">Office 2010, Office 2013, and other Office 2016 versions are not supported.</span></span>

- <span data-ttu-id="cb43f-108">La migración de Active Directory Rights Management Services (AD RMS) a Azure Information Protection no está disponible actualmente.</span><span class="sxs-lookup"><span data-stu-id="cb43f-108">Migration from Active Directory Rights Management Services (AD RMS) to Azure Information Protection is currently not available.</span></span>
  
- <span data-ttu-id="cb43f-109">Se admite el uso compartido de correos electrónicos protegidos a los usuarios en la nube comercial.</span><span class="sxs-lookup"><span data-stu-id="cb43f-109">Sharing of protected emails to users in the commercial cloud is supported.</span></span>
  
- <span data-ttu-id="cb43f-110">El uso compartido de documentos y datos adjuntos de correo electrónico para los usuarios de la nube comercial no está disponible actualmente.</span><span class="sxs-lookup"><span data-stu-id="cb43f-110">Sharing of documents and email attachments to users in the commercial cloud is currently not available.</span></span> <span data-ttu-id="cb43f-111">Esto incluye Office 365 operado por usuarios de 21Vianet en la nube comercial, usuarios que no son de Office 365 operados por 21Vianet en la nube comercial y usuarios con una licencia rms para personas.</span><span class="sxs-lookup"><span data-stu-id="cb43f-111">This includes Office 365 operated by 21Vianet users in the commercial cloud, non-Office 365 operated by 21Vianet users in the commercial cloud, and users with an RMS for Individuals license.</span></span>
  
- <span data-ttu-id="cb43f-112">IRM con SharePoint (bibliotecas y sitios protegidos por IRM) no está disponible actualmente.</span><span class="sxs-lookup"><span data-stu-id="cb43f-112">IRM with SharePoint (IRM-protected sites and libraries) is currently not available.</span></span>
  
- <span data-ttu-id="cb43f-113">La extensión de dispositivo móvil para AD RMS no está disponible actualmente.</span><span class="sxs-lookup"><span data-stu-id="cb43f-113">The Mobile Device Extension for AD RMS is currently not available.</span></span>

- <span data-ttu-id="cb43f-114">El [Visor móvil no](/azure/information-protection/rms-client/mobile-app-faq) es compatible con Azure China 21Vianet.</span><span class="sxs-lookup"><span data-stu-id="cb43f-114">The [Mobile Viewer](/azure/information-protection/rms-client/mobile-app-faq) is not supported by Azure China 21Vianet.</span></span>

## <a name="configuring-azure-information-protection-for-customers-in-china"></a><span data-ttu-id="cb43f-115">Configuración de Azure Information Protection para clientes en China</span><span class="sxs-lookup"><span data-stu-id="cb43f-115">Configuring Azure Information Protection for customers in China</span></span>

### <a name="enable-rights-management-for-the-tenant"></a><span data-ttu-id="cb43f-116">Habilitar Rights Management para el inquilino</span><span class="sxs-lookup"><span data-stu-id="cb43f-116">Enable Rights Management for the tenant</span></span>

<span data-ttu-id="cb43f-117">Para que el cifrado funcione correctamente, el RMS debe estar habilitado para el inquilino.</span><span class="sxs-lookup"><span data-stu-id="cb43f-117">For the encryption to work correctly, the RMS must be enabled for the tenant.</span></span>

- <span data-ttu-id="cb43f-118">Compruebe si rms está habilitado:</span><span class="sxs-lookup"><span data-stu-id="cb43f-118">Check if the RMS is enabled:</span></span>
  1. <span data-ttu-id="cb43f-119">Inicie PowerShell como administrador.</span><span class="sxs-lookup"><span data-stu-id="cb43f-119">Launch PowerShell as an administrator.</span></span>
  2. <span data-ttu-id="cb43f-120">Si el módulo AIPService no está instalado, ejecute `Install-Module AipService` .</span><span class="sxs-lookup"><span data-stu-id="cb43f-120">If the AIPService module isn't installed, run `Install-Module AipService`.</span></span>
  3. <span data-ttu-id="cb43f-121">Importe el módulo mediante `Import-Module AipService` .</span><span class="sxs-lookup"><span data-stu-id="cb43f-121">Import the module using `Import-Module AipService`.</span></span>
  4. <span data-ttu-id="cb43f-122">Conéctese al servicio mediante `Connect-AipService -environmentname azurechinacloud` .</span><span class="sxs-lookup"><span data-stu-id="cb43f-122">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
  5. <span data-ttu-id="cb43f-123">Ejecute `(Get-AipServiceConfiguration).FunctionalState` y compruebe si el estado es `Enabled` .</span><span class="sxs-lookup"><span data-stu-id="cb43f-123">Run `(Get-AipServiceConfiguration).FunctionalState` and check if the state is `Enabled`.</span></span>

- <span data-ttu-id="cb43f-124">Si el estado funcional es `Disabled` , ejecute `Enable-AipService` .</span><span class="sxs-lookup"><span data-stu-id="cb43f-124">If the functional state is `Disabled`, run `Enable-AipService`.</span></span>

### <a name="dns-configuration-for-encryption-windows"></a><span data-ttu-id="cb43f-125">Configuración dns para cifrado (Windows)</span><span class="sxs-lookup"><span data-stu-id="cb43f-125">DNS configuration for encryption (Windows)</span></span>

<span data-ttu-id="cb43f-126">Para que el cifrado funcione correctamente, las aplicaciones cliente de Office deben conectarse a la instancia de China del servicio y arrancar desde allí.</span><span class="sxs-lookup"><span data-stu-id="cb43f-126">For encryption to work correctly, Office client applications must connect to the China instance of the service and bootstrap from there.</span></span> <span data-ttu-id="cb43f-127">Para redirigir las aplicaciones cliente a la instancia de servicio correcta, el administrador de inquilinos debe configurar un registro SRV de DNS con información sobre la dirección URL de Azure RMS.</span><span class="sxs-lookup"><span data-stu-id="cb43f-127">To redirect client applications to the right service instance, the tenant admin must configure a DNS SRV record with information about the Azure RMS URL.</span></span> <span data-ttu-id="cb43f-128">Sin el registro SRV de DNS, la aplicación cliente intentará conectarse a la instancia de nube pública de forma predeterminada y se producirá un error.</span><span class="sxs-lookup"><span data-stu-id="cb43f-128">Without the DNS SRV record, the client application will attempt to connect to the public cloud instance by default and will fail.</span></span>

<span data-ttu-id="cb43f-129">Además, se supone que los usuarios iniciarán sesión con un nombre de usuario basado en el dominio propiedad del inquilino (por ejemplo, ) y no con el nombre de usuario `joe@contoso.cn` `onmschina` (por ejemplo, `joe@contoso.onmschina.cn` ).</span><span class="sxs-lookup"><span data-stu-id="cb43f-129">Also, the assumption is that users will log in with a username based off the tenant-owned domain (for example, `joe@contoso.cn`), and not the `onmschina` username (for example, `joe@contoso.onmschina.cn`).</span></span> <span data-ttu-id="cb43f-130">El nombre de dominio del nombre de usuario se usa para la redirección dns a la instancia de servicio correcta.</span><span class="sxs-lookup"><span data-stu-id="cb43f-130">The domain name from the username is used for DNS redirection to the correct service instance.</span></span>

- <span data-ttu-id="cb43f-131">Obtenga el id. de RMS:</span><span class="sxs-lookup"><span data-stu-id="cb43f-131">Get the RMS ID:</span></span>
  1. <span data-ttu-id="cb43f-132">Inicie PowerShell como administrador.</span><span class="sxs-lookup"><span data-stu-id="cb43f-132">Launch PowerShell as an administrator.</span></span>
  2. <span data-ttu-id="cb43f-133">Si el módulo AIPService no está instalado, ejecute `Install-Module AipService` .</span><span class="sxs-lookup"><span data-stu-id="cb43f-133">If the AIPService module isn't installed, run `Install-Module AipService`.</span></span>
  3. <span data-ttu-id="cb43f-134">Conéctese al servicio mediante `Connect-AipService -environmentname azurechinacloud` .</span><span class="sxs-lookup"><span data-stu-id="cb43f-134">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
  4. <span data-ttu-id="cb43f-135">Ejecutar `(Get-AipServiceConfiguration).RightsManagementServiceId` para obtener el identificador de RMS.</span><span class="sxs-lookup"><span data-stu-id="cb43f-135">Run `(Get-AipServiceConfiguration).RightsManagementServiceId` to get the RMS ID.</span></span>

- <span data-ttu-id="cb43f-136">Inicie sesión en su proveedor de DNS, vaya a la configuración DNS del dominio y, a continuación, agregue un nuevo registro SRV.</span><span class="sxs-lookup"><span data-stu-id="cb43f-136">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>
  - <span data-ttu-id="cb43f-137">Service = `_rmsredir`</span><span class="sxs-lookup"><span data-stu-id="cb43f-137">Service = `_rmsredir`</span></span>
  - <span data-ttu-id="cb43f-138">Protocolo = `_http`</span><span class="sxs-lookup"><span data-stu-id="cb43f-138">Protocol = `_http`</span></span>
  - <span data-ttu-id="cb43f-139">Name = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="cb43f-139">Name = `_tcp`</span></span>
  - <span data-ttu-id="cb43f-140">Target = `[GUID].rms.aadrm.cn` (donde GUID es el id. de RMS)</span><span class="sxs-lookup"><span data-stu-id="cb43f-140">Target = `[GUID].rms.aadrm.cn` (where GUID is the RMS ID)</span></span>
  - <span data-ttu-id="cb43f-141">Prioridad, Peso, Segundos, TTL = valores predeterminados</span><span class="sxs-lookup"><span data-stu-id="cb43f-141">Priority, Weight, Seconds, TTL = default values</span></span>

- <span data-ttu-id="cb43f-142">Asocie el dominio personalizado con el inquilino en [Azure Portal.](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains)</span><span class="sxs-lookup"><span data-stu-id="cb43f-142">Associate the custom domain with the tenant in the [Azure portal](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains).</span></span> <span data-ttu-id="cb43f-143">Esto agregará una entrada en DNS, que puede tardar varios minutos en comprobarse después de agregar el valor a la configuración dns.</span><span class="sxs-lookup"><span data-stu-id="cb43f-143">This will add an entry in DNS, which might take several minutes to get verified after you add the value to the DNS settings.</span></span>

- <span data-ttu-id="cb43f-144">Inicie sesión en el Centro de administración de Microsoft 365 con las credenciales de administrador global correspondientes y agregue el dominio (por ejemplo, ) para `contoso.cn` la creación de usuarios.</span><span class="sxs-lookup"><span data-stu-id="cb43f-144">Log in to the Microsoft 365 admin center with the corresponding global admin credentials and add the domain (for example, `contoso.cn`) for user creation.</span></span> <span data-ttu-id="cb43f-145">En el proceso de comprobación, es posible que se necesiten cambios dns adicionales.</span><span class="sxs-lookup"><span data-stu-id="cb43f-145">In the verification process, additional DNS changes might be required.</span></span> <span data-ttu-id="cb43f-146">Una vez realizada la comprobación, se pueden crear usuarios.</span><span class="sxs-lookup"><span data-stu-id="cb43f-146">Once verification is done, users can be created.</span></span>

### <a name="dns-configuration-for-encryption-mac-ios-android"></a><span data-ttu-id="cb43f-147">Configuración dns para el cifrado (Mac, iOS, Android)</span><span class="sxs-lookup"><span data-stu-id="cb43f-147">DNS configuration for encryption (Mac, iOS, Android)</span></span>

<span data-ttu-id="cb43f-148">Inicie sesión en su proveedor de DNS, vaya a la configuración DNS del dominio y, a continuación, agregue un nuevo registro SRV.</span><span class="sxs-lookup"><span data-stu-id="cb43f-148">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>

- <span data-ttu-id="cb43f-149">Service = `_rmsdisco`</span><span class="sxs-lookup"><span data-stu-id="cb43f-149">Service = `_rmsdisco`</span></span>
- <span data-ttu-id="cb43f-150">Protocolo = `_http`</span><span class="sxs-lookup"><span data-stu-id="cb43f-150">Protocol = `_http`</span></span>
- <span data-ttu-id="cb43f-151">Name = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="cb43f-151">Name = `_tcp`</span></span>
- <span data-ttu-id="cb43f-152">Target = `api.aadrm.cn`</span><span class="sxs-lookup"><span data-stu-id="cb43f-152">Target = `api.aadrm.cn`</span></span>
- <span data-ttu-id="cb43f-153">Port = `80`</span><span class="sxs-lookup"><span data-stu-id="cb43f-153">Port = `80`</span></span>
- <span data-ttu-id="cb43f-154">Prioridad, Peso, Segundos, TTL = valores predeterminados</span><span class="sxs-lookup"><span data-stu-id="cb43f-154">Priority, Weight, Seconds, TTL = default values</span></span>

### <a name="aip-client-configuration"></a><span data-ttu-id="cb43f-155">Configuración de cliente AIP</span><span class="sxs-lookup"><span data-stu-id="cb43f-155">AIP client configuration</span></span>

<span data-ttu-id="cb43f-156">El cliente AIP unificado se puede descargar desde el Centro [de descarga de Microsoft.](https://www.microsoft.com/download/details.aspx?id=53018)</span><span class="sxs-lookup"><span data-stu-id="cb43f-156">The unified AIP client can be downloaded from the [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>

<span data-ttu-id="cb43f-157">Para obtener más información, vea:</span><span class="sxs-lookup"><span data-stu-id="cb43f-157">For more information, see:</span></span>

- [<span data-ttu-id="cb43f-158">Documentación de Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="cb43f-158">Azure Information Protection documentation</span></span>](/azure/information-protection/)
- [<span data-ttu-id="cb43f-159">Historial de versiones AIP y directiva de soporte técnico</span><span class="sxs-lookup"><span data-stu-id="cb43f-159">AIP version history and support policy</span></span>](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)
- [<span data-ttu-id="cb43f-160">Requisitos del sistema AIP</span><span class="sxs-lookup"><span data-stu-id="cb43f-160">AIP system requirements</span></span>](/azure/information-protection/requirements)
- [<span data-ttu-id="cb43f-161">Inicio rápido de AIP: implementar el cliente AIP</span><span class="sxs-lookup"><span data-stu-id="cb43f-161">AIP quickstart: Deploy the AIP client</span></span>](/azure/information-protection/quickstart-deploy-client)
- [<span data-ttu-id="cb43f-162">Guía de administrador de AIP</span><span class="sxs-lookup"><span data-stu-id="cb43f-162">AIP administrator guide</span></span>](/azure/information-protection/rms-client/clientv2-admin-guide)
- [<span data-ttu-id="cb43f-163">Guía de usuario de AIP</span><span class="sxs-lookup"><span data-stu-id="cb43f-163">AIP user guide</span></span>](/azure/information-protection/rms-client/clientv2-user-guide)
- [<span data-ttu-id="cb43f-164">Más información sobre las etiquetas de confidencialidad de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="cb43f-164">Learn about Microsoft 365 sensitivity labels</span></span>](/microsoft-365/compliance/sensitivity-labels)

### <a name="aip-apps-configuration-unified-labeling-client-only"></a><span data-ttu-id="cb43f-165">Configuración de aplicaciones AIP (solo cliente de etiquetado unificado)</span><span class="sxs-lookup"><span data-stu-id="cb43f-165">AIP apps configuration (unified labeling client only)</span></span>

<span data-ttu-id="cb43f-166">Para la solución de etiquetado unificado, las aplicaciones AIP en Windows necesitan la siguiente clave del Registro para apuntarlas a la nube soberana correcta para Azure China:</span><span class="sxs-lookup"><span data-stu-id="cb43f-166">For the unified labeling solution, AIP apps on Windows need the following registry key to point them to the correct sovereign cloud for Azure China:</span></span>

- <span data-ttu-id="cb43f-167">Nodo del Registro = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`</span><span class="sxs-lookup"><span data-stu-id="cb43f-167">Registry node = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`</span></span>
- <span data-ttu-id="cb43f-168">Name = `CloudEnvType`</span><span class="sxs-lookup"><span data-stu-id="cb43f-168">Name = `CloudEnvType`</span></span>
- <span data-ttu-id="cb43f-169">Valor = `6` (valor predeterminado = 0)</span><span class="sxs-lookup"><span data-stu-id="cb43f-169">Value = `6` (default = 0)</span></span>
- <span data-ttu-id="cb43f-170">Type = `REG_DWORD`</span><span class="sxs-lookup"><span data-stu-id="cb43f-170">Type = `REG_DWORD`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cb43f-171">Asegúrese de no eliminar la clave del Registro después de una desinstalación.</span><span class="sxs-lookup"><span data-stu-id="cb43f-171">Make sure you don't delete the registry key after an uninstall.</span></span> <span data-ttu-id="cb43f-172">Si la clave está vacía, incorrecta o inexistente, la funcionalidad se comportará como el valor predeterminado (valor predeterminado = 0 para la nube comercial).</span><span class="sxs-lookup"><span data-stu-id="cb43f-172">If the key is empty, incorrect, or non-existent, the functionality will behave as the default value (default value = 0 for the commercial cloud).</span></span> <span data-ttu-id="cb43f-173">Si la clave está vacía o es incorrecta, también se agrega un error de impresión al registro.</span><span class="sxs-lookup"><span data-stu-id="cb43f-173">If the key is empty or incorrect, a print error is also added to the log.</span></span>

### <a name="manage-azure-information-protection-content-scan-jobs"></a><span data-ttu-id="cb43f-174">Administrar trabajos de análisis de contenido de Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="cb43f-174">Manage Azure Information Protection content scan jobs</span></span>

<span data-ttu-id="cb43f-175">Para administrar los trabajos de análisis de contenido de Azure Information Protection con un servidor de escáner de Azure China, use los cmdlets siguientes en lugar de Azure Portal:</span><span class="sxs-lookup"><span data-stu-id="cb43f-175">To manage your Azure Information Protection content scan jobs with an Azure China scanner server, use the following cmdlets instead of the Azure portal:</span></span><br><br>

| <span data-ttu-id="cb43f-176">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="cb43f-176">Cmdlet</span></span> | <span data-ttu-id="cb43f-177">Descripción</span><span class="sxs-lookup"><span data-stu-id="cb43f-177">Description</span></span> |
|--|--|
| [<span data-ttu-id="cb43f-178">Add-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="cb43f-178">Add-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/add-aipscannerrepository) | <span data-ttu-id="cb43f-179">Agrega un nuevo repositorio al trabajo de análisis de contenido.</span><span class="sxs-lookup"><span data-stu-id="cb43f-179">Adds a new repository to your content scan job.</span></span> |
| [<span data-ttu-id="cb43f-180">Get-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="cb43f-180">Get-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/get-aipscannercontentscanjob) | <span data-ttu-id="cb43f-181">Obtiene detalles sobre el trabajo de análisis de contenido.</span><span class="sxs-lookup"><span data-stu-id="cb43f-181">Gets details about your content scan job.</span></span> |
| [<span data-ttu-id="cb43f-182">Get-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="cb43f-182">Get-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/get-aipscannerrepository) | <span data-ttu-id="cb43f-183">Obtiene detalles acerca de los repositorios definidos para el trabajo de análisis de contenido.</span><span class="sxs-lookup"><span data-stu-id="cb43f-183">Gets details about repositories defined for your content scan job.</span></span> |
| [<span data-ttu-id="cb43f-184">Remove-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="cb43f-184">Remove-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/remove-aipscannercontentscanjob) | <span data-ttu-id="cb43f-185">Elimina el trabajo de análisis de contenido.</span><span class="sxs-lookup"><span data-stu-id="cb43f-185">Deletes your content scan job.</span></span> |
| [<span data-ttu-id="cb43f-186">Remove-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="cb43f-186">Remove-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/remove-aipscannerrepository) | <span data-ttu-id="cb43f-187">Quita un repositorio del trabajo de análisis de contenido.</span><span class="sxs-lookup"><span data-stu-id="cb43f-187">Removes a repository from your content scan job.</span></span> |
| [<span data-ttu-id="cb43f-188">Set-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="cb43f-188">Set-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) | <span data-ttu-id="cb43f-189">Define la configuración del trabajo de análisis de contenido.</span><span class="sxs-lookup"><span data-stu-id="cb43f-189">Defines settings for your content scan job.</span></span> |
| [<span data-ttu-id="cb43f-190">Set-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="cb43f-190">Set-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/set-aipscannerrepository) | <span data-ttu-id="cb43f-191">Define la configuración de un repositorio existente en el trabajo de detección de contenido.</span><span class="sxs-lookup"><span data-stu-id="cb43f-191">Defines settings for an existing repository in your content scan job.</span></span> |

<span data-ttu-id="cb43f-192">Para obtener más información, vea [Administrar los trabajos de análisis de contenido solo con PowerShell.](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer)</span><span class="sxs-lookup"><span data-stu-id="cb43f-192">For more information, see [Manage your content scan jobs using PowerShell only](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer).</span></span>