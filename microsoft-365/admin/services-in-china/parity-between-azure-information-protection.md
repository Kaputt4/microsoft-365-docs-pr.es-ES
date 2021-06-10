---
title: Compatibilidad con Azure Information Protection para Office 365 operado por 21Vianet
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
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
description: Obtenga más información sobre Azure Information Protection (AIP) para Office 365 operado por 21Vianet y cómo configurarlo para clientes en China.
monikerRange: o365-21vianet
ms.openlocfilehash: 8b85ae43df31bb1947b841d616cc83c3a0b614e4
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2021
ms.locfileid: "52535847"
---
# <a name="azure-information-protection-support-for-office-365-operated-by-21vianet"></a><span data-ttu-id="f9890-103">Compatibilidad con Azure Information Protection para Office 365 operado por 21Vianet</span><span class="sxs-lookup"><span data-stu-id="f9890-103">Azure Information Protection support for Office 365 operated by 21Vianet</span></span>

<span data-ttu-id="f9890-104">En este artículo se tratan las diferencias entre la compatibilidad con Azure Information Protection (AIP) para Office 365 operado por 21Vianet y las ofertas comerciales, así como instrucciones específicas para configurar AIP para clientes en China, incluido cómo instalar el escáner local de AIP y administrar trabajos de examen de &mdash; contenido.</span><span class="sxs-lookup"><span data-stu-id="f9890-104">This article covers the differences between Azure Information Protection (AIP) support for Office 365 operated by 21Vianet and commercial offerings, as well as specific instructions for configuring AIP for customers in China&mdash;including how to install the AIP on-premises scanner and manage content scan jobs.</span></span>

## <a name="differences-between-aip-for-office-365-operated-by-21vianet-and-commercial-offerings"></a><span data-ttu-id="f9890-105">Diferencias entre AIP para Office 365 operado por 21Vianet y ofertas comerciales</span><span class="sxs-lookup"><span data-stu-id="f9890-105">Differences between AIP for Office 365 operated by 21Vianet and commercial offerings</span></span>

<span data-ttu-id="f9890-106">Aunque nuestro objetivo es ofrecer todas las características comerciales y funcionalidades a los clientes de China con nuestra oferta de AIP para Office 365 operado por 21Vianet, nos gustaría destacar algunas funciones que nos gustaría destacar.</span><span class="sxs-lookup"><span data-stu-id="f9890-106">While our goal is to deliver all commercial features and functionality to customers in China with our AIP for Office 365 operated by 21Vianet offer, there's some missing functionality that we'd like to highlight.</span></span>

<span data-ttu-id="f9890-107">La siguiente lista incluye las diferencias existentes entre AIP para Office 365 operado por 21Vianet y nuestras ofertas comerciales a partir de enero de 2021:</span><span class="sxs-lookup"><span data-stu-id="f9890-107">The following list includes the existing gaps between AIP for Office 365 operated by 21Vianet and our commercial offerings as of January 2021:</span></span>

- <span data-ttu-id="f9890-108">Information Rights Management (IRM) solo se admite Aplicaciones Microsoft 365 para empresas (compilación 11731.10000 o posterior).</span><span class="sxs-lookup"><span data-stu-id="f9890-108">Information Rights Management (IRM) is supported only for Microsoft 365 Apps for enterprise (build 11731.10000 or higher).</span></span> <span data-ttu-id="f9890-109">Office 2010, Office 2013 y otras versiones Office 2016 no son compatibles.</span><span class="sxs-lookup"><span data-stu-id="f9890-109">Office 2010, Office 2013, and other Office 2016 versions are not supported.</span></span>

- <span data-ttu-id="f9890-110">La migración Active Directory Rights Management Services (AD RMS) a AIP no está disponible actualmente.</span><span class="sxs-lookup"><span data-stu-id="f9890-110">Migration from Active Directory Rights Management Services (AD RMS) to AIP is currently not available.</span></span>
  
- <span data-ttu-id="f9890-111">Se admite el uso compartido de correos electrónicos protegidos con usuarios en la nube comercial.</span><span class="sxs-lookup"><span data-stu-id="f9890-111">Sharing of protected emails with users in the commercial cloud is supported.</span></span>
  
- <span data-ttu-id="f9890-112">El uso compartido de documentos y datos adjuntos de correo electrónico con usuarios en la nube comercial no está disponible actualmente.</span><span class="sxs-lookup"><span data-stu-id="f9890-112">Sharing of documents and email attachments with users in the commercial cloud is currently not available.</span></span> <span data-ttu-id="f9890-113">Esto incluye Office 365 operado por 21 usuarios deVianet en la nube comercial, no Office 365 operado por 21 usuarios deVianet en la nube comercial y usuarios con una licencia rms para individuos.</span><span class="sxs-lookup"><span data-stu-id="f9890-113">This includes Office 365 operated by 21Vianet users in the commercial cloud, non-Office 365 operated by 21Vianet users in the commercial cloud, and users with an RMS for Individuals license.</span></span>
  
- <span data-ttu-id="f9890-114">IRM con SharePoint (bibliotecas y sitios protegidos por IRM) actualmente no está disponible.</span><span class="sxs-lookup"><span data-stu-id="f9890-114">IRM with SharePoint (IRM-protected sites and libraries) is currently not available.</span></span>
  
- <span data-ttu-id="f9890-115">La extensión de dispositivo móvil para AD RMS no está disponible actualmente.</span><span class="sxs-lookup"><span data-stu-id="f9890-115">The Mobile Device Extension for AD RMS is currently not available.</span></span>

- <span data-ttu-id="f9890-116">[El Visor móvil no](/azure/information-protection/rms-client/mobile-app-faq) es compatible con Azure China 21Vianet.</span><span class="sxs-lookup"><span data-stu-id="f9890-116">The [Mobile Viewer](/azure/information-protection/rms-client/mobile-app-faq) is not supported by Azure China 21Vianet.</span></span>

- <span data-ttu-id="f9890-117">El área AIP de Azure Portal no está disponible para los clientes en China.</span><span class="sxs-lookup"><span data-stu-id="f9890-117">The AIP area of the Azure portal is unavailable to customers in China.</span></span> <span data-ttu-id="f9890-118">Use [comandos de PowerShell en](#step-6-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs) lugar de realizar acciones en el portal, como administrar y ejecutar los trabajos de examen de contenido.</span><span class="sxs-lookup"><span data-stu-id="f9890-118">Use [PowerShell commands](#step-6-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs) instead of performing actions in the portal, such as managing and running your content scan jobs.</span></span>

## <a name="configure-aip-for-customers-in-china"></a><span data-ttu-id="f9890-119">Configurar AIP para clientes en China</span><span class="sxs-lookup"><span data-stu-id="f9890-119">Configure AIP for customers in China</span></span>

<span data-ttu-id="f9890-120">Para configurar AIP para clientes en China:</span><span class="sxs-lookup"><span data-stu-id="f9890-120">To configure AIP for customers in China:</span></span>
1. <span data-ttu-id="f9890-121">[Habilitar Rights Management para el inquilino](#step-1-enable-rights-management-for-the-tenant).</span><span class="sxs-lookup"><span data-stu-id="f9890-121">[Enable Rights Management for the tenant](#step-1-enable-rights-management-for-the-tenant).</span></span>

1. <span data-ttu-id="f9890-122">[Agregue la entidad de servicio de sincronización de Microsoft Information Protection](#step-2-add-the-microsoft-information-protection-sync-service-service-principal).</span><span class="sxs-lookup"><span data-stu-id="f9890-122">[Add the Microsoft Information Protection Sync Service service principal](#step-2-add-the-microsoft-information-protection-sync-service-service-principal).</span></span>

1. <span data-ttu-id="f9890-123">[Configurar el cifrado DNS](#step-3-configure-dns-encryption).</span><span class="sxs-lookup"><span data-stu-id="f9890-123">[Configure DNS encryption](#step-3-configure-dns-encryption).</span></span>

1. <span data-ttu-id="f9890-124">[Instalar y configurar el cliente de etiquetado unificado AIP](#step-4-install-and-configure-the-aip-unified-labeling-client).</span><span class="sxs-lookup"><span data-stu-id="f9890-124">[Install and configure the AIP unified labeling client](#step-4-install-and-configure-the-aip-unified-labeling-client).</span></span>

1. <span data-ttu-id="f9890-125">[Configurar aplicaciones AIP en Windows](#step-5-configure-aip-apps-on-windows).</span><span class="sxs-lookup"><span data-stu-id="f9890-125">[Configure AIP apps on Windows](#step-5-configure-aip-apps-on-windows).</span></span>

1. <span data-ttu-id="f9890-126">[Instale el escáner local de AIP y administre trabajos de análisis de contenido.](#step-6-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs)</span><span class="sxs-lookup"><span data-stu-id="f9890-126">[Install the AIP on-premises scanner and manage content scan jobs](#step-6-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs).</span></span> 

### <a name="step-1-enable-rights-management-for-the-tenant"></a><span data-ttu-id="f9890-127">Paso 1: Habilitar Rights Management para el inquilino</span><span class="sxs-lookup"><span data-stu-id="f9890-127">Step 1: Enable Rights Management for the tenant</span></span>

<span data-ttu-id="f9890-128">Para que el cifrado funcione correctamente, RMS debe estar habilitado para el inquilino.</span><span class="sxs-lookup"><span data-stu-id="f9890-128">For the encryption to work correctly, RMS must be enabled for the tenant.</span></span>

1. <span data-ttu-id="f9890-129">Compruebe si RMS está habilitado:</span><span class="sxs-lookup"><span data-stu-id="f9890-129">Check if RMS is enabled:</span></span>

    1. <span data-ttu-id="f9890-130">Inicie PowerShell como administrador.</span><span class="sxs-lookup"><span data-stu-id="f9890-130">Launch PowerShell as an administrator.</span></span>
    2. <span data-ttu-id="f9890-131">Si el módulo AIPService no está instalado, ejecute `Install-Module AipService` .</span><span class="sxs-lookup"><span data-stu-id="f9890-131">If the AIPService module isn't installed, run `Install-Module AipService`.</span></span>
    3. <span data-ttu-id="f9890-132">Importe el módulo mediante `Import-Module AipService` .</span><span class="sxs-lookup"><span data-stu-id="f9890-132">Import the module using `Import-Module AipService`.</span></span>
    4. <span data-ttu-id="f9890-133">Conectar al servicio mediante `Connect-AipService -environmentname azurechinacloud` .</span><span class="sxs-lookup"><span data-stu-id="f9890-133">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
    5. <span data-ttu-id="f9890-134">Ejecute `(Get-AipServiceConfiguration).FunctionalState` y compruebe si el estado es `Enabled` .</span><span class="sxs-lookup"><span data-stu-id="f9890-134">Run `(Get-AipServiceConfiguration).FunctionalState` and check if the state is `Enabled`.</span></span>

2. <span data-ttu-id="f9890-135">Si el estado funcional es `Disabled` , ejecute `Enable-AipService` .</span><span class="sxs-lookup"><span data-stu-id="f9890-135">If the functional state is `Disabled`, run `Enable-AipService`.</span></span>

### <a name="step-2-add-the-microsoft-information-protection-sync-service-service-principal"></a><span data-ttu-id="f9890-136">Paso 2: Agregar la entidad de servicio de sincronización de Microsoft Information Protection</span><span class="sxs-lookup"><span data-stu-id="f9890-136">Step 2: Add the Microsoft Information Protection Sync Service service principal</span></span>

<span data-ttu-id="f9890-137">La **entidad de servicio del** servicio de sincronización de Microsoft Information Protection no está disponible en los inquilinos de Azure China de forma predeterminada y es necesaria para Azure Information Protection.</span><span class="sxs-lookup"><span data-stu-id="f9890-137">The **Microsoft Information Protection Sync Service** service principal is not available in Azure China tenants by default, and is required for Azure Information Protection.</span></span>

1. <span data-ttu-id="f9890-138">Cree esta entidad de servicio manualmente con el cmdlet [New-AzADServicePrincipal](/powershell/module/az.resources/new-azadserviceprincipal) y el identificador de aplicación del servicio de sincronización `870c4f2e-85b6-4d43-bdda-6ed9a579b725` de Microsoft Information Protection.</span><span class="sxs-lookup"><span data-stu-id="f9890-138">Create this service principal manually using the [New-AzADServicePrincipal](/powershell/module/az.resources/new-azadserviceprincipal) cmdlet and the `870c4f2e-85b6-4d43-bdda-6ed9a579b725` application ID for the Microsoft Information Protection Sync Service.</span></span> 

    ```powershell 
    New-AzADServicePrincipal -ApplicationId 870c4f2e-85b6-4d43-bdda-6ed9a579b725
    ```

1. <span data-ttu-id="f9890-139">Después de agregar la entidad de servicio, agregue los permisos pertinentes necesarios al servicio.</span><span class="sxs-lookup"><span data-stu-id="f9890-139">After adding the service principal, add the relevant permissions required to the service.</span></span>

### <a name="step-3-configure-dns-encryption"></a><span data-ttu-id="f9890-140">Paso 3: Configurar el cifrado DNS</span><span class="sxs-lookup"><span data-stu-id="f9890-140">Step 3: Configure DNS encryption</span></span>

<span data-ttu-id="f9890-141">Para que el cifrado funcione correctamente, Office aplicaciones cliente deben conectarse a la instancia china del servicio y arrancar desde allí.</span><span class="sxs-lookup"><span data-stu-id="f9890-141">For encryption to work correctly, Office client applications must connect to the China instance of the service and bootstrap from there.</span></span> <span data-ttu-id="f9890-142">Para redirigir las aplicaciones cliente a la instancia de servicio correcta, el administrador del espacio empresarial debe configurar un registro SRV dns con información sobre la dirección URL de Azure RMS.</span><span class="sxs-lookup"><span data-stu-id="f9890-142">To redirect client applications to the right service instance, the tenant admin must configure a DNS SRV record with information about the Azure RMS URL.</span></span> <span data-ttu-id="f9890-143">Sin el registro SRV de DNS, la aplicación cliente intentará conectarse a la instancia de nube pública de forma predeterminada y producirá un error.</span><span class="sxs-lookup"><span data-stu-id="f9890-143">Without the DNS SRV record, the client application will attempt to connect to the public cloud instance by default and will fail.</span></span>

<span data-ttu-id="f9890-144">Además, se supone que los usuarios iniciarán sesión con un nombre de usuario basado en el dominio propiedad del inquilino (por ejemplo, ), y no con el nombre de usuario `joe@contoso.cn` `onmschina` (por ejemplo, `joe@contoso.onmschina.cn` ).</span><span class="sxs-lookup"><span data-stu-id="f9890-144">Also, the assumption is that users will log in with a username based off the tenant-owned domain (for example, `joe@contoso.cn`), and not the `onmschina` username (for example, `joe@contoso.onmschina.cn`).</span></span> <span data-ttu-id="f9890-145">El nombre de dominio del nombre de usuario se usa para la redirección dns a la instancia de servicio correcta.</span><span class="sxs-lookup"><span data-stu-id="f9890-145">The domain name from the username is used for DNS redirection to the correct service instance.</span></span>

#### <a name="configure-dns-encryption---windows"></a><span data-ttu-id="f9890-146">Configurar el cifrado DNS: Windows</span><span class="sxs-lookup"><span data-stu-id="f9890-146">Configure DNS encryption - Windows</span></span>

1. <span data-ttu-id="f9890-147">Obtener el id. de RMS:</span><span class="sxs-lookup"><span data-stu-id="f9890-147">Get the RMS ID:</span></span>

    1. <span data-ttu-id="f9890-148">Inicie PowerShell como administrador.</span><span class="sxs-lookup"><span data-stu-id="f9890-148">Launch PowerShell as an administrator.</span></span>
    2. <span data-ttu-id="f9890-149">Si el módulo AIPService no está instalado, ejecute `Install-Module AipService` .</span><span class="sxs-lookup"><span data-stu-id="f9890-149">If the AIPService module isn't installed, run `Install-Module AipService`.</span></span>
    3. <span data-ttu-id="f9890-150">Conectar al servicio mediante `Connect-AipService -environmentname azurechinacloud` .</span><span class="sxs-lookup"><span data-stu-id="f9890-150">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
    4. <span data-ttu-id="f9890-151">Ejecute `(Get-AipServiceConfiguration).RightsManagementServiceId` para obtener el identificador de RMS.</span><span class="sxs-lookup"><span data-stu-id="f9890-151">Run `(Get-AipServiceConfiguration).RightsManagementServiceId` to get the RMS ID.</span></span>

2. <span data-ttu-id="f9890-152">Inicie sesión en el proveedor dns, vaya a la configuración dns del dominio y, a continuación, agregue un nuevo registro SRV.</span><span class="sxs-lookup"><span data-stu-id="f9890-152">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>

    - <span data-ttu-id="f9890-153">Service = `_rmsredir`</span><span class="sxs-lookup"><span data-stu-id="f9890-153">Service = `_rmsredir`</span></span>
    - <span data-ttu-id="f9890-154">Protocolo = `_http`</span><span class="sxs-lookup"><span data-stu-id="f9890-154">Protocol = `_http`</span></span>
    - <span data-ttu-id="f9890-155">Name = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="f9890-155">Name = `_tcp`</span></span>
    - <span data-ttu-id="f9890-156">Target = `[GUID].rms.aadrm.cn` (donde GUID es el id. de RMS)</span><span class="sxs-lookup"><span data-stu-id="f9890-156">Target = `[GUID].rms.aadrm.cn` (where GUID is the RMS ID)</span></span>
    - <span data-ttu-id="f9890-157">Priority, Weight, Seconds, TTL = default values</span><span class="sxs-lookup"><span data-stu-id="f9890-157">Priority, Weight, Seconds, TTL = default values</span></span>

3. <span data-ttu-id="f9890-158">Asocie el dominio personalizado con el inquilino en [Azure Portal](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains).</span><span class="sxs-lookup"><span data-stu-id="f9890-158">Associate the custom domain with the tenant in the [Azure portal](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains).</span></span> <span data-ttu-id="f9890-159">Esto agregará una entrada en DNS, que puede tardar varios minutos en comprobarse después de agregar el valor a la configuración de DNS.</span><span class="sxs-lookup"><span data-stu-id="f9890-159">This will add an entry in DNS, which might take several minutes to get verified after you add the value to the DNS settings.</span></span>

4. <span data-ttu-id="f9890-160">Inicie sesión en el Microsoft 365 de administración con las credenciales de administración global correspondientes y agregue el dominio (por ejemplo, `contoso.cn` ) para la creación de usuarios.</span><span class="sxs-lookup"><span data-stu-id="f9890-160">Log in to the Microsoft 365 admin center with the corresponding global admin credentials and add the domain (for example, `contoso.cn`) for user creation.</span></span> <span data-ttu-id="f9890-161">En el proceso de comprobación, es posible que se necesiten cambios dns adicionales.</span><span class="sxs-lookup"><span data-stu-id="f9890-161">In the verification process, additional DNS changes might be required.</span></span> <span data-ttu-id="f9890-162">Una vez que se realiza la comprobación, se pueden crear usuarios.</span><span class="sxs-lookup"><span data-stu-id="f9890-162">Once verification is done, users can be created.</span></span>

#### <a name="configure-dns-encryption---mac-ios-android"></a><span data-ttu-id="f9890-163">Configurar el cifrado DNS: Mac, iOS, Android</span><span class="sxs-lookup"><span data-stu-id="f9890-163">Configure DNS encryption - Mac, iOS, Android</span></span>

<span data-ttu-id="f9890-164">Inicie sesión en el proveedor dns, vaya a la configuración dns del dominio y, a continuación, agregue un nuevo registro SRV.</span><span class="sxs-lookup"><span data-stu-id="f9890-164">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>

- <span data-ttu-id="f9890-165">Service = `_rmsdisco`</span><span class="sxs-lookup"><span data-stu-id="f9890-165">Service = `_rmsdisco`</span></span>
- <span data-ttu-id="f9890-166">Protocolo = `_http`</span><span class="sxs-lookup"><span data-stu-id="f9890-166">Protocol = `_http`</span></span>
- <span data-ttu-id="f9890-167">Name = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="f9890-167">Name = `_tcp`</span></span>
- <span data-ttu-id="f9890-168">Target = `api.aadrm.cn`</span><span class="sxs-lookup"><span data-stu-id="f9890-168">Target = `api.aadrm.cn`</span></span>
- <span data-ttu-id="f9890-169">Port = `80`</span><span class="sxs-lookup"><span data-stu-id="f9890-169">Port = `80`</span></span>
- <span data-ttu-id="f9890-170">Priority, Weight, Seconds, TTL = default values</span><span class="sxs-lookup"><span data-stu-id="f9890-170">Priority, Weight, Seconds, TTL = default values</span></span>


### <a name="step-4-install-and-configure-the-aip-unified-labeling-client"></a><span data-ttu-id="f9890-171">Paso 4: Instalar y configurar el cliente de etiquetado unificado AIP</span><span class="sxs-lookup"><span data-stu-id="f9890-171">Step 4: Install and configure the AIP unified labeling client</span></span>

<span data-ttu-id="f9890-172">Descargue e instale el cliente de etiquetado unificado AIP desde el [Centro de descarga de Microsoft](https://www.microsoft.com/download/details.aspx?id=53018).</span><span class="sxs-lookup"><span data-stu-id="f9890-172">Download and install the AIP unified labeling client from the [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>

<span data-ttu-id="f9890-173">Para obtener más información, vea:</span><span class="sxs-lookup"><span data-stu-id="f9890-173">For more information, see:</span></span>

- [<span data-ttu-id="f9890-174">Documentación de AIP</span><span class="sxs-lookup"><span data-stu-id="f9890-174">AIP documentation</span></span>](/azure/information-protection/)
- [<span data-ttu-id="f9890-175">Historial de versiones de AIP y directiva de soporte técnico</span><span class="sxs-lookup"><span data-stu-id="f9890-175">AIP version history and support policy</span></span>](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)
- [<span data-ttu-id="f9890-176">Requisitos del sistema AIP</span><span class="sxs-lookup"><span data-stu-id="f9890-176">AIP system requirements</span></span>](/azure/information-protection/requirements)
- [<span data-ttu-id="f9890-177">Inicio rápido de AIP: implementar el cliente AIP</span><span class="sxs-lookup"><span data-stu-id="f9890-177">AIP quickstart: Deploy the AIP client</span></span>](/azure/information-protection/quickstart-deploy-client)
- [<span data-ttu-id="f9890-178">Guía de administrador de AIP</span><span class="sxs-lookup"><span data-stu-id="f9890-178">AIP administrator guide</span></span>](/azure/information-protection/rms-client/clientv2-admin-guide)
- [<span data-ttu-id="f9890-179">Guía del usuario de AIP</span><span class="sxs-lookup"><span data-stu-id="f9890-179">AIP user guide</span></span>](/azure/information-protection/rms-client/clientv2-user-guide)
- [<span data-ttu-id="f9890-180">Obtenga información sobre Microsoft 365 etiquetas de confidencialidad</span><span class="sxs-lookup"><span data-stu-id="f9890-180">Learn about Microsoft 365 sensitivity labels</span></span>](../../compliance/sensitivity-labels.md)

### <a name="step-5-configure-aip-apps-on-windows"></a><span data-ttu-id="f9890-181">Paso 5: Configurar aplicaciones AIP en Windows</span><span class="sxs-lookup"><span data-stu-id="f9890-181">Step 5: Configure AIP apps on Windows</span></span>

<span data-ttu-id="f9890-182">Las aplicaciones AIP Windows necesitan la siguiente clave del Registro para apuntarlas a la nube soberana correcta para Azure China:</span><span class="sxs-lookup"><span data-stu-id="f9890-182">AIP apps on Windows need the following registry key to point them to the correct sovereign cloud for Azure China:</span></span>

- <span data-ttu-id="f9890-183">Nodo del Registro = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`</span><span class="sxs-lookup"><span data-stu-id="f9890-183">Registry node = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`</span></span>
- <span data-ttu-id="f9890-184">Name = `CloudEnvType`</span><span class="sxs-lookup"><span data-stu-id="f9890-184">Name = `CloudEnvType`</span></span>
- <span data-ttu-id="f9890-185">Valor = `6` (valor predeterminado = 0)</span><span class="sxs-lookup"><span data-stu-id="f9890-185">Value = `6` (default = 0)</span></span>
- <span data-ttu-id="f9890-186">Type = `REG_DWORD`</span><span class="sxs-lookup"><span data-stu-id="f9890-186">Type = `REG_DWORD`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f9890-187">Asegúrese de que no elimina la clave del Registro después de una desinstalación.</span><span class="sxs-lookup"><span data-stu-id="f9890-187">Make sure you don't delete the registry key after an uninstall.</span></span> <span data-ttu-id="f9890-188">Si la clave está vacía, incorrecta o inexistente, la funcionalidad se comportará como el valor predeterminado (valor predeterminado = 0 para la nube comercial).</span><span class="sxs-lookup"><span data-stu-id="f9890-188">If the key is empty, incorrect, or non-existent, the functionality will behave as the default value (default value = 0 for the commercial cloud).</span></span> <span data-ttu-id="f9890-189">Si la clave está vacía o incorrecta, también se agrega un error de impresión al registro.</span><span class="sxs-lookup"><span data-stu-id="f9890-189">If the key is empty or incorrect, a print error is also added to the log.</span></span>

### <a name="step-6-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs"></a><span data-ttu-id="f9890-190">Paso 6: Instalar el escáner local de AIP y administrar trabajos de análisis de contenido</span><span class="sxs-lookup"><span data-stu-id="f9890-190">Step 6: Install the AIP on-premises scanner and manage content scan jobs</span></span>

<span data-ttu-id="f9890-191">Instale el escáner local de AIP para examinar la red y los recursos compartidos de contenido en busca de datos confidenciales y aplicar etiquetas de clasificación y protección según lo configurado en la directiva de su organización.</span><span class="sxs-lookup"><span data-stu-id="f9890-191">Install the AIP on-premises scanner to scan your network and content shares for sensitive data, and apply classification and protection labels as configured in your organization's policy.</span></span>

<span data-ttu-id="f9890-192">Al configurar y administrar los trabajos de análisis de contenido, use el siguiente procedimiento en lugar de la interfaz de [Azure Portal](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=azure-portal-only) que usan las ofertas comerciales.</span><span class="sxs-lookup"><span data-stu-id="f9890-192">When configuring and managing your content scan jobs, use the following procedure instead of the [Azure portal interface](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=azure-portal-only) that's used by the commercial offerings.</span></span>

<span data-ttu-id="f9890-193">Para obtener más información, vea ¿Qué es el escáner de etiquetado unificado de [Azure Information Protection?](/azure/information-protection/deploy-aip-scanner) y Administrar los trabajos de examen de contenido [solo con PowerShell](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer).</span><span class="sxs-lookup"><span data-stu-id="f9890-193">For more information, see [What is the Azure Information Protection unified labeling scanner?](/azure/information-protection/deploy-aip-scanner) and [Manage your content scan jobs using PowerShell only](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer).</span></span>

<span data-ttu-id="f9890-194">**Para instalar y configurar el escáner:**</span><span class="sxs-lookup"><span data-stu-id="f9890-194">**To install and configure your scanner**:</span></span>

1. <span data-ttu-id="f9890-195">Inicie sesión en el Windows servidor que ejecutará el escáner.</span><span class="sxs-lookup"><span data-stu-id="f9890-195">Sign in to the Windows Server computer that will run the scanner.</span></span> <span data-ttu-id="f9890-196">Use una cuenta que tenga derechos de administrador local y que tenga permisos para escribir en la SQL Server base de datos maestra.</span><span class="sxs-lookup"><span data-stu-id="f9890-196">Use an account that has local administrator rights and that has permissions to write to the SQL Server master database.</span></span>

1. <span data-ttu-id="f9890-197">Comience con PowerShell cerrado.</span><span class="sxs-lookup"><span data-stu-id="f9890-197">Start with PowerShell closed.</span></span> <span data-ttu-id="f9890-198">Si ha instalado previamente el cliente y el escáner de AIP, asegúrese de que el servicio **AIPScanner** está detenido.</span><span class="sxs-lookup"><span data-stu-id="f9890-198">If you've previously installed the AIP client and scanner, make sure that the **AIPScanner** service is stopped.</span></span>

1. <span data-ttu-id="f9890-199">Abra una Windows PowerShell sesión con la **opción Ejecutar como administrador.**</span><span class="sxs-lookup"><span data-stu-id="f9890-199">Open a Windows PowerShell session with the **Run as an administrator** option.</span></span>

1. <span data-ttu-id="f9890-200">Ejecute el cmdlet [Install-AIPScanner,](/powershell/module/azureinformationprotection/Install-AIPScanner) especificando la instancia de SQL Server en la que se va a crear una base de datos para el escáner de Azure Information Protection y un nombre significativo para el clúster de escáneres.</span><span class="sxs-lookup"><span data-stu-id="f9890-200">Run the [Install-AIPScanner](/powershell/module/azureinformationprotection/Install-AIPScanner) cmdlet, specifying your SQL Server instance on which to create a database for the Azure Information Protection scanner, and a meaningful name for your scanner cluster.</span></span>

    ```PowerShell
    Install-AIPScanner -SqlServerInstance <name> -Cluster <cluster name>
    ```

    > [!TIP]
    > <span data-ttu-id="f9890-201">Puede usar el mismo nombre de clúster en el comando [Install-AIPScanner](/powershell/module/azureinformationprotection/install-aipscanner) para asociar varios nodos de escáner al mismo clúster.</span><span class="sxs-lookup"><span data-stu-id="f9890-201">You can use the same cluster name in the [Install-AIPScanner](/powershell/module/azureinformationprotection/install-aipscanner) command to associate multiple scanner nodes to the same cluster.</span></span> <span data-ttu-id="f9890-202">El uso del mismo clúster para varios nodos de escáner permite que varios escáneres funcionen juntos para realizar los exámenes.</span><span class="sxs-lookup"><span data-stu-id="f9890-202">Using the same cluster for multiple scanner nodes enables multiple scanners to work together to perform your scans.</span></span>
    > 

1. <span data-ttu-id="f9890-203">Compruebe que el servicio ya está instalado mediante **servicios de herramientas**  >  **administrativas**.</span><span class="sxs-lookup"><span data-stu-id="f9890-203">Verify that the service is now installed by using **Administrative Tools** > **Services**.</span></span>

    <span data-ttu-id="f9890-204">El servicio instalado se denomina **Azure Information Protection Scanner** y está configurado para ejecutarse mediante la cuenta de servicio de escáner que creó.</span><span class="sxs-lookup"><span data-stu-id="f9890-204">The installed service is named **Azure Information Protection Scanner** and is configured to run by using the scanner service account that you created.</span></span>

1. <span data-ttu-id="f9890-205">Obtenga un token de Azure para usarlo con el escáner.</span><span class="sxs-lookup"><span data-stu-id="f9890-205">Get an Azure token to use with your scanner.</span></span> <span data-ttu-id="f9890-206">Un token de Azure AD permite que el escáner se autentique en el servicio de Azure Information Protection, lo que permite que el escáner se ejecute de forma no interactiva.</span><span class="sxs-lookup"><span data-stu-id="f9890-206">An Azure AD token allows the scanner to authenticate to the Azure Information Protection service, enabling the scanner to run non-interactively.</span></span> 

    1. <span data-ttu-id="f9890-207">Abra Azure Portal y cree una aplicación de Azure AD para especificar un token de acceso para la autenticación.</span><span class="sxs-lookup"><span data-stu-id="f9890-207">Open the Azure portal and create an Azure AD application to specify an access token for authentication.</span></span> <span data-ttu-id="f9890-208">Para obtener más información, [vea How to label files non-interactively for Azure Information Protection](/azure/information-protection/rms-client/clientv2-admin-guide-powershell#how-to-label-files-non-interactively-for-azure-information-protection).</span><span class="sxs-lookup"><span data-stu-id="f9890-208">For more information, see [How to label files non-interactively for Azure Information Protection](/azure/information-protection/rms-client/clientv2-admin-guide-powershell#how-to-label-files-non-interactively-for-azure-information-protection).</span></span>
    
        > [!TIP]
        > <span data-ttu-id="f9890-209">Al crear y configurar aplicaciones de Azure AD para el comando [Set-AIPAuthentication,](/powershell/module/azureinformationprotection/set-aipauthentication) el panel Solicitar permisos **de api** muestra las API que mi organización usa en lugar de la pestaña API de **Microsoft.**  Seleccione las **API que usa mi organización** para, a continuación, seleccionar Azure Rights Management **Servicios**.</span><span class="sxs-lookup"><span data-stu-id="f9890-209">When creating and configuring Azure AD applications for the [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication) command, the **Request API permissions** pane shows the **APIs my organization uses** tab instead of the **Microsoft APIs** tab. Select the **APIs my organization uses** to then select **Azure Rights Management Services**.</span></span> 
        >

    1. <span data-ttu-id="f9890-210">Desde el equipo Windows Server, si se ha concedido a su cuenta de servicio de escáner el derecho Iniciar sesión **localmente** para la instalación, inicie sesión con esta cuenta e inicie una sesión de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f9890-210">From the Windows Server computer, if your scanner service account has been granted the **Log on locally** right for the installation, sign in with this account and start a PowerShell session.</span></span> 
    
        <span data-ttu-id="f9890-211">Si no se puede conceder a su cuenta de servicio de escáner el derecho De iniciar sesión **localmente** para la instalación, use el parámetro *OnBehalfOf* con [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication), tal como se describe en [How to label files non-interactively for Azure Information Protection](/azure/information-protection/rms-client/clientv2-admin-guide-powershell#how-to-label-files-non-interactively-for-azure-information-protection).</span><span class="sxs-lookup"><span data-stu-id="f9890-211">If your scanner service account cannot be granted the **Log on locally** right for the installation, use the *OnBehalfOf* parameter with [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication), as described in [How to label files non-interactively for Azure Information Protection](/azure/information-protection/rms-client/clientv2-admin-guide-powershell#how-to-label-files-non-interactively-for-azure-information-protection).</span></span>

    1. <span data-ttu-id="f9890-212">Ejecute [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication), especificando los valores copiados desde la aplicación de Azure AD:</span><span class="sxs-lookup"><span data-stu-id="f9890-212">Run [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication), specifying values copied from your Azure AD application:</span></span>

      ```PowerShell
      Set-AIPAuthentication -AppId <ID of the registered app> -AppSecret <client secret sting> -TenantId <your tenant ID> -DelegatedUser <Azure AD account>
      ```

      <span data-ttu-id="f9890-213">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f9890-213">For example:</span></span>

      ```PowerShell
      $pscreds = Get-Credential CONTOSO\scanner
      Set-AIPAuthentication -AppId "77c3c1c3-abf9-404e-8b2b-4652836c8c66" -AppSecret "OAkk+rnuYc/u+]ah2kNxVbtrDGbS47L4" -DelegatedUser scanner@contoso.com -TenantId "9c11c87a-ac8b-46a3-8d5c-f4d0b72ee29a" -OnBehalfOf $pscreds
      Acquired application access token on behalf of CONTOSO\scanner.
      ```

    <span data-ttu-id="f9890-214">El escáner ahora tiene un token para autenticarse en Azure AD.</span><span class="sxs-lookup"><span data-stu-id="f9890-214">The scanner now has a token to authenticate to Azure AD.</span></span> <span data-ttu-id="f9890-215">Este token es válido durante un año, dos años o nunca, según la configuración del secreto de cliente de la aplicación **web /API** en Azure AD.</span><span class="sxs-lookup"><span data-stu-id="f9890-215">This token is valid for one year, two years, or never, according to your configuration of the **Web app /API** client secret in Azure AD.</span></span> <span data-ttu-id="f9890-216">Cuando expire el token, debe repetir este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="f9890-216">When the token expires, you must repeat this procedure.</span></span>

1. <span data-ttu-id="f9890-217">Ejecute el cmdlet [Set-AIPScannerConfiguration](/powershell/module/azureinformationprotection/set-aipscannerconfiguration) para establecer el escáner para que funcione en modo sin conexión.</span><span class="sxs-lookup"><span data-stu-id="f9890-217">Run the [Set-AIPScannerConfiguration](/powershell/module/azureinformationprotection/set-aipscannerconfiguration) cmdlet to set the scanner to function in offline mode.</span></span> <span data-ttu-id="f9890-218">Ejecutar:</span><span class="sxs-lookup"><span data-stu-id="f9890-218">Run:</span></span>

    ```powershell
    Set-AIPScannerConfiguration -OnlineConfiguration Off
    ```

1. <span data-ttu-id="f9890-219">Ejecute el cmdlet [Set-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) para crear un trabajo de detección de contenido predeterminado.</span><span class="sxs-lookup"><span data-stu-id="f9890-219">Run the [Set-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) cmdlet to create a default content scan job.</span></span>

    <span data-ttu-id="f9890-220">El único parámetro necesario en el cmdlet **Set-AIPScannerContentScanJob** es **Enforce**.</span><span class="sxs-lookup"><span data-stu-id="f9890-220">The only required parameter in the **Set-AIPScannerContentScanJob** cmdlet is **Enforce**.</span></span> <span data-ttu-id="f9890-221">Sin embargo, es posible que desee definir otras opciones de configuración para el trabajo de examen de contenido en este momento.</span><span class="sxs-lookup"><span data-stu-id="f9890-221">However, you may want to define other settings for your content scan job at this time.</span></span> <span data-ttu-id="f9890-222">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f9890-222">For example:</span></span>

    ```powershell
    Set-AIPScannerContentScanJob -Schedule Manual -DiscoverInformationTypes PolicyOnly -Enforce Off -DefaultLabelType PolicyDefault -RelabelFiles Off -PreserveFileDetails On -IncludeFileTypes '' -ExcludeFileTypes '.msg,.tmp' -DefaultOwner <account running the scanner>
    ```

    <span data-ttu-id="f9890-223">La sintaxis anterior configura las siguientes opciones mientras continúa la configuración:</span><span class="sxs-lookup"><span data-stu-id="f9890-223">The syntax above configures the following settings while you continue the configuration:</span></span>

    - <span data-ttu-id="f9890-224">Mantiene la programación de ejecución del escáner en *manual*</span><span class="sxs-lookup"><span data-stu-id="f9890-224">Keeps the scanner run scheduling to *manual*</span></span>
    - <span data-ttu-id="f9890-225">Establece los tipos de información que se detectarán en función de la directiva de etiquetado de confidencialidad</span><span class="sxs-lookup"><span data-stu-id="f9890-225">Sets the information types to be discovered based on the sensitivity labeling policy</span></span>
    - <span data-ttu-id="f9890-226">No *aplica una* directiva de etiquetado de confidencialidad</span><span class="sxs-lookup"><span data-stu-id="f9890-226">Does *not* enforce a sensitivity labeling policy</span></span>
    - <span data-ttu-id="f9890-227">Etiqueta automáticamente los archivos en función del contenido, con la etiqueta predeterminada definida para la directiva de etiquetado de confidencialidad</span><span class="sxs-lookup"><span data-stu-id="f9890-227">Automatically labels files based on content, using the default label defined for the sensitivity labeling policy</span></span>
    - <span data-ttu-id="f9890-228">No *permite* volver a etiquetar archivos</span><span class="sxs-lookup"><span data-stu-id="f9890-228">Does *not* allow for relabeling files</span></span>
    - <span data-ttu-id="f9890-229">Conserva los detalles del archivo durante el examen y el etiquetado automático, incluidas las fechas modificadas, *las* últimas modificadas y *modificadas por valores*</span><span class="sxs-lookup"><span data-stu-id="f9890-229">Preserves file details while scanning and auto-labeling, including *date modified*, *last modified*, and *modified by* values</span></span>
    - <span data-ttu-id="f9890-230">Establece el escáner para excluir los archivos .msg y .tmp al ejecutarse</span><span class="sxs-lookup"><span data-stu-id="f9890-230">Sets the scanner to exclude .msg and .tmp files when running</span></span>
    - <span data-ttu-id="f9890-231">Establece el propietario predeterminado en la cuenta que desea usar al ejecutar el escáner</span><span class="sxs-lookup"><span data-stu-id="f9890-231">Sets the default owner to the account you want to use when running the scanner</span></span>

1. <span data-ttu-id="f9890-232">Use el cmdlet [Add-AIPScannerRepository](/powershell/module/azureinformationprotection/add-aipscannerrepository) para definir los repositorios que desea examinar en el trabajo de detección de contenido.</span><span class="sxs-lookup"><span data-stu-id="f9890-232">Use the [Add-AIPScannerRepository](/powershell/module/azureinformationprotection/add-aipscannerrepository) cmdlet to define the repositories you want to scan in your content scan job.</span></span> <span data-ttu-id="f9890-233">Por ejemplo, ejecute:</span><span class="sxs-lookup"><span data-stu-id="f9890-233">For example, run:</span></span>

    ```powershell
    Add-AIPScannerRepository -OverrideContentScanJob Off -Path 'c:\repoToScan'
    ```
    
    <span data-ttu-id="f9890-234">Use una de las siguientes sintaxis, según el tipo de repositorio que agregue:</span><span class="sxs-lookup"><span data-stu-id="f9890-234">Use one of the following syntaxes, depending on the type of repository you're adding:</span></span>

    - <span data-ttu-id="f9890-235">Para un recurso compartido de red, use `\\Server\Folder` .</span><span class="sxs-lookup"><span data-stu-id="f9890-235">For a network share, use `\\Server\Folder`.</span></span>
    - <span data-ttu-id="f9890-236">Para una biblioteca SharePoint, use `http://sharepoint.contoso.com/Shared%20Documents/Folder` .</span><span class="sxs-lookup"><span data-stu-id="f9890-236">For a SharePoint library, use `http://sharepoint.contoso.com/Shared%20Documents/Folder`.</span></span>
    - <span data-ttu-id="f9890-237">Para una ruta de acceso local: `C:\Folder`</span><span class="sxs-lookup"><span data-stu-id="f9890-237">For a local path: `C:\Folder`</span></span>
    - <span data-ttu-id="f9890-238">Para una ruta de acceso UNC: `\\Server\Folder`</span><span class="sxs-lookup"><span data-stu-id="f9890-238">For a UNC path: `\\Server\Folder`</span></span>

    > [!NOTE]
    > <span data-ttu-id="f9890-239">No se admiten caracteres comodín y no se admiten las ubicaciones de WebDav.</span><span class="sxs-lookup"><span data-stu-id="f9890-239">Wildcards are not supported and WebDav locations are not supported.</span></span>
    >
    > <span data-ttu-id="f9890-240">Para modificar el repositorio más adelante, use el cmdlet [Set-AIPScannerRepository](/powershell/module/azureinformationprotection/set-aipscannerrepository) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="f9890-240">To modify the repository later on, use the [Set-AIPScannerRepository](/powershell/module/azureinformationprotection/set-aipscannerrepository) cmdlet instead.</span></span> 


<span data-ttu-id="f9890-241">Continúe con los pasos siguientes según sea necesario:</span><span class="sxs-lookup"><span data-stu-id="f9890-241">Continue with the following steps as needed:</span></span>

- [<span data-ttu-id="f9890-242">Ejecutar un ciclo de detección y ver informes del escáner</span><span class="sxs-lookup"><span data-stu-id="f9890-242">Run a discovery cycle and view reports for the scanner</span></span>](/azure/information-protection/deploy-aip-scanner-manage#run-a-discovery-cycle-and-view-reports-for-the-scanner)
- [<span data-ttu-id="f9890-243">Usar PowerShell para configurar el escáner para aplicar la clasificación y la protección</span><span class="sxs-lookup"><span data-stu-id="f9890-243">Use PowerShell to configure the scanner to apply classification and protection</span></span>](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=azure-portal-only#use-powershell-to-configure-the-scanner-to-apply-classification-and-protection)
- [<span data-ttu-id="f9890-244">Usar PowerShell para configurar una directiva DLP con el escáner</span><span class="sxs-lookup"><span data-stu-id="f9890-244">Use PowerShell to configure a DLP policy with the scanner</span></span>](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=azure-portal-only#use-powershell-to-configure-a-dlp-policy-with-the-scanner)

<span data-ttu-id="f9890-245">En la tabla siguiente se enumeran los cmdlets de PowerShell que son relevantes para instalar el escáner y administrar los trabajos de examen de contenido:</span><span class="sxs-lookup"><span data-stu-id="f9890-245">The following table lists PowerShell cmdlets that are relevant for installing the scanner and managing your content scan jobs:</span></span>

| <span data-ttu-id="f9890-246">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="f9890-246">Cmdlet</span></span> | <span data-ttu-id="f9890-247">Descripción</span><span class="sxs-lookup"><span data-stu-id="f9890-247">Description</span></span> |
|--|--|
| [<span data-ttu-id="f9890-248">Add-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="f9890-248">Add-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/add-aipscannerrepository) | <span data-ttu-id="f9890-249">Agrega un nuevo repositorio al trabajo de examen de contenido.</span><span class="sxs-lookup"><span data-stu-id="f9890-249">Adds a new repository to your content scan job.</span></span> |
| [<span data-ttu-id="f9890-250">Get-AIPScannerConfiguration</span><span class="sxs-lookup"><span data-stu-id="f9890-250">Get-AIPScannerConfiguration</span></span>](/powershell/module/azureinformationprotection/get-aipscannerconfiguration)|<span data-ttu-id="f9890-251">Devuelve detalles sobre el clúster.</span><span class="sxs-lookup"><span data-stu-id="f9890-251">Returns details about your cluster.</span></span> |
| [<span data-ttu-id="f9890-252">Get-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="f9890-252">Get-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/get-aipscannercontentscanjob) | <span data-ttu-id="f9890-253">Obtiene detalles sobre el trabajo de examen de contenido.</span><span class="sxs-lookup"><span data-stu-id="f9890-253">Gets details about your content scan job.</span></span> |
| [<span data-ttu-id="f9890-254">Get-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="f9890-254">Get-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/get-aipscannerrepository) | <span data-ttu-id="f9890-255">Obtiene detalles sobre los repositorios definidos para el trabajo de examen de contenido.</span><span class="sxs-lookup"><span data-stu-id="f9890-255">Gets details about repositories defined for your content scan job.</span></span> |
| [<span data-ttu-id="f9890-256">Remove-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="f9890-256">Remove-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/remove-aipscannercontentscanjob) | <span data-ttu-id="f9890-257">Elimina el trabajo de examen de contenido.</span><span class="sxs-lookup"><span data-stu-id="f9890-257">Deletes your content scan job.</span></span> |
| [<span data-ttu-id="f9890-258">Remove-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="f9890-258">Remove-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/remove-aipscannerrepository) | <span data-ttu-id="f9890-259">Quita un repositorio del trabajo de examen de contenido.</span><span class="sxs-lookup"><span data-stu-id="f9890-259">Removes a repository from your content scan job.</span></span> |
| [<span data-ttu-id="f9890-260">Set-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="f9890-260">Set-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) | <span data-ttu-id="f9890-261">Define la configuración del trabajo de examen de contenido.</span><span class="sxs-lookup"><span data-stu-id="f9890-261">Defines settings for your content scan job.</span></span> |
| [<span data-ttu-id="f9890-262">Set-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="f9890-262">Set-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/set-aipscannerrepository) | <span data-ttu-id="f9890-263">Define la configuración de un repositorio existente en el trabajo de examen de contenido.</span><span class="sxs-lookup"><span data-stu-id="f9890-263">Defines settings for an existing repository in your content scan job.</span></span> |
| | |

<span data-ttu-id="f9890-264">Para obtener más información, vea:</span><span class="sxs-lookup"><span data-stu-id="f9890-264">For more information, see:</span></span>

- [<span data-ttu-id="f9890-265">¿Qué es el escáner de etiquetado unificado de Azure Information Protection?</span><span class="sxs-lookup"><span data-stu-id="f9890-265">What is the Azure Information Protection unified labeling scanner?</span></span>](/azure/information-protection/deploy-aip-scanner)
- [<span data-ttu-id="f9890-266">Configuración e instalación del escáner de etiquetado unificado de Azure Information Protection (AIP)</span><span class="sxs-lookup"><span data-stu-id="f9890-266">Configuring and installing the Azure Information Protection (AIP) unified labeling scanner</span></span>](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=powershell-only)
- <span data-ttu-id="f9890-267">[Administrar los trabajos de examen de contenido solo con PowerShell](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer).</span><span class="sxs-lookup"><span data-stu-id="f9890-267">[Manage your content scan jobs using PowerShell only](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer).</span></span>
