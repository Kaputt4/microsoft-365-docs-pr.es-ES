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
ms.openlocfilehash: bddba69ecc8b7b80d2b2c7c48d820ec22d293362
ms.sourcegitcommit: b56a8ff9bb496bf2bc1991000afca3d251f45b72
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/30/2021
ms.locfileid: "51418037"
---
# <a name="azure-information-protection-support-for-office-365-operated-by-21vianet"></a><span data-ttu-id="c0d9b-103">Compatibilidad con Azure Information Protection para Office 365 operado por 21Vianet</span><span class="sxs-lookup"><span data-stu-id="c0d9b-103">Azure Information Protection support for Office 365 operated by 21Vianet</span></span>

<span data-ttu-id="c0d9b-104">En este artículo se tratan las diferencias entre la compatibilidad con Azure Information Protection (AIP) para Office 365 operado por 21Vianet y las ofertas comerciales, así como instrucciones específicas para configurar AIP para clientes en China, incluido cómo instalar el escáner local de AIP y administrar trabajos de examen de &mdash; contenido.</span><span class="sxs-lookup"><span data-stu-id="c0d9b-104">This article covers the differences between Azure Information Protection (AIP) support for Office 365 operated by 21Vianet and commercial offerings, as well as specific instructions for configuring AIP for customers in China&mdash;including how to install the AIP on-premises scanner and manage content scan jobs.</span></span>

## <a name="differences-between-aip-for-office-365-operated-by-21vianet-and-commercial-offerings"></a><span data-ttu-id="c0d9b-105">Diferencias entre AIP para Office 365 operado por 21Vianet y ofertas comerciales</span><span class="sxs-lookup"><span data-stu-id="c0d9b-105">Differences between AIP for Office 365 operated by 21Vianet and commercial offerings</span></span>

<span data-ttu-id="c0d9b-106">Aunque nuestro objetivo es ofrecer todas las características comerciales y funcionalidades a los clientes de China con nuestra oferta de AIP para Office 365 operado por 21Vianet, nos gustaría destacar algunas funciones que nos gustaría destacar.</span><span class="sxs-lookup"><span data-stu-id="c0d9b-106">While our goal is to deliver all commercial features and functionality to customers in China with our AIP for Office 365 operated by 21Vianet offer, there's some missing functionality that we'd like to highlight.</span></span>

<span data-ttu-id="c0d9b-107">La siguiente lista incluye las diferencias existentes entre AIP para Office 365 operado por 21Vianet y nuestras ofertas comerciales a partir de enero de 2021:</span><span class="sxs-lookup"><span data-stu-id="c0d9b-107">The following list includes the existing gaps between AIP for Office 365 operated by 21Vianet and our commercial offerings as of January 2021:</span></span>

- <span data-ttu-id="c0d9b-108">Information Rights Management (IRM) solo es compatible con aplicaciones de Microsoft 365 para empresas (compilación 11731.10000 o posterior).</span><span class="sxs-lookup"><span data-stu-id="c0d9b-108">Information Rights Management (IRM) is supported only for Microsoft 365 Apps for enterprise (build 11731.10000 or higher).</span></span> <span data-ttu-id="c0d9b-109">Office 2010, Office 2013 y otras versiones de Office 2016 no son compatibles.</span><span class="sxs-lookup"><span data-stu-id="c0d9b-109">Office 2010, Office 2013, and other Office 2016 versions are not supported.</span></span>

- <span data-ttu-id="c0d9b-110">Actualmente, la migración de Active Directory Rights Management Services (AD RMS) a AIP no está disponible.</span><span class="sxs-lookup"><span data-stu-id="c0d9b-110">Migration from Active Directory Rights Management Services (AD RMS) to AIP is currently not available.</span></span>
  
- <span data-ttu-id="c0d9b-111">Se admite el uso compartido de correos electrónicos protegidos con usuarios en la nube comercial.</span><span class="sxs-lookup"><span data-stu-id="c0d9b-111">Sharing of protected emails with users in the commercial cloud is supported.</span></span>
  
- <span data-ttu-id="c0d9b-112">El uso compartido de documentos y datos adjuntos de correo electrónico con usuarios en la nube comercial no está disponible actualmente.</span><span class="sxs-lookup"><span data-stu-id="c0d9b-112">Sharing of documents and email attachments with users in the commercial cloud is currently not available.</span></span> <span data-ttu-id="c0d9b-113">Esto incluye Office 365 operado por 21 usuarios deVianet en la nube comercial, que no es Office 365 operado por 21 usuarios deVianet en la nube comercial y usuarios con una licencia rms para individuos.</span><span class="sxs-lookup"><span data-stu-id="c0d9b-113">This includes Office 365 operated by 21Vianet users in the commercial cloud, non-Office 365 operated by 21Vianet users in the commercial cloud, and users with an RMS for Individuals license.</span></span>
  
- <span data-ttu-id="c0d9b-114">IRM con SharePoint (bibliotecas y sitios protegidos por IRM) actualmente no está disponible.</span><span class="sxs-lookup"><span data-stu-id="c0d9b-114">IRM with SharePoint (IRM-protected sites and libraries) is currently not available.</span></span>
  
- <span data-ttu-id="c0d9b-115">La extensión de dispositivo móvil para AD RMS no está disponible actualmente.</span><span class="sxs-lookup"><span data-stu-id="c0d9b-115">The Mobile Device Extension for AD RMS is currently not available.</span></span>

- <span data-ttu-id="c0d9b-116">[El Visor móvil no](/azure/information-protection/rms-client/mobile-app-faq) es compatible con Azure China 21Vianet.</span><span class="sxs-lookup"><span data-stu-id="c0d9b-116">The [Mobile Viewer](/azure/information-protection/rms-client/mobile-app-faq) is not supported by Azure China 21Vianet.</span></span>

- <span data-ttu-id="c0d9b-117">El área AIP de Azure Portal no está disponible para los clientes en China.</span><span class="sxs-lookup"><span data-stu-id="c0d9b-117">The AIP area of the Azure portal is unavailable to customers in China.</span></span> <span data-ttu-id="c0d9b-118">Use [comandos de PowerShell en](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs) lugar de realizar acciones en el portal, como instalar el escáner local y administrar los trabajos de examen de contenido.</span><span class="sxs-lookup"><span data-stu-id="c0d9b-118">Use [PowerShell commands](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs) instead of performing actions in the portal, such as installing the on-premises scanner and managing your content scan jobs.</span></span>

## <a name="configure-aip-for-customers-in-china"></a><span data-ttu-id="c0d9b-119">Configurar AIP para clientes en China</span><span class="sxs-lookup"><span data-stu-id="c0d9b-119">Configure AIP for customers in China</span></span>

<span data-ttu-id="c0d9b-120">Para configurar AIP para clientes en China:</span><span class="sxs-lookup"><span data-stu-id="c0d9b-120">To configure AIP for customers in China:</span></span>
1. <span data-ttu-id="c0d9b-121">[Habilitar Rights Management para el inquilino](#step-1-enable-rights-management-for-the-tenant).</span><span class="sxs-lookup"><span data-stu-id="c0d9b-121">[Enable Rights Management for the tenant](#step-1-enable-rights-management-for-the-tenant).</span></span>

2. <span data-ttu-id="c0d9b-122">[Configurar el cifrado DNS](#step-2-configure-dns-encryption).</span><span class="sxs-lookup"><span data-stu-id="c0d9b-122">[Configure DNS encryption](#step-2-configure-dns-encryption).</span></span>

3. <span data-ttu-id="c0d9b-123">[Instalar y configurar el cliente de etiquetado unificado AIP](#step-3-install-and-configure-the-aip-unified-labeling-client).</span><span class="sxs-lookup"><span data-stu-id="c0d9b-123">[Install and configure the AIP unified labeling client](#step-3-install-and-configure-the-aip-unified-labeling-client).</span></span>

4. <span data-ttu-id="c0d9b-124">[Configurar aplicaciones AIP en Windows](#step-4-configure-aip-apps-on-windows).</span><span class="sxs-lookup"><span data-stu-id="c0d9b-124">[Configure AIP apps on Windows](#step-4-configure-aip-apps-on-windows).</span></span>

5. <span data-ttu-id="c0d9b-125">[Instale el escáner local de AIP y administre trabajos de análisis de contenido.](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs)</span><span class="sxs-lookup"><span data-stu-id="c0d9b-125">[Install the AIP on-premises scanner and manage content scan jobs](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs).</span></span> 

### <a name="step-1-enable-rights-management-for-the-tenant"></a><span data-ttu-id="c0d9b-126">Paso 1: Habilitar Rights Management para el inquilino</span><span class="sxs-lookup"><span data-stu-id="c0d9b-126">Step 1: Enable Rights Management for the tenant</span></span>

<span data-ttu-id="c0d9b-127">Para que el cifrado funcione correctamente, RMS debe estar habilitado para el inquilino.</span><span class="sxs-lookup"><span data-stu-id="c0d9b-127">For the encryption to work correctly, RMS must be enabled for the tenant.</span></span>

1. <span data-ttu-id="c0d9b-128">Compruebe si RMS está habilitado:</span><span class="sxs-lookup"><span data-stu-id="c0d9b-128">Check if RMS is enabled:</span></span>

    1. <span data-ttu-id="c0d9b-129">Inicie PowerShell como administrador.</span><span class="sxs-lookup"><span data-stu-id="c0d9b-129">Launch PowerShell as an administrator.</span></span>
    2. <span data-ttu-id="c0d9b-130">Si el módulo AIPService no está instalado, ejecute `Install-Module AipService` .</span><span class="sxs-lookup"><span data-stu-id="c0d9b-130">If the AIPService module isn't installed, run `Install-Module AipService`.</span></span>
    3. <span data-ttu-id="c0d9b-131">Importe el módulo mediante `Import-Module AipService` .</span><span class="sxs-lookup"><span data-stu-id="c0d9b-131">Import the module using `Import-Module AipService`.</span></span>
    4. <span data-ttu-id="c0d9b-132">Conectarse al servicio mediante `Connect-AipService -environmentname azurechinacloud` .</span><span class="sxs-lookup"><span data-stu-id="c0d9b-132">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
    5. <span data-ttu-id="c0d9b-133">Ejecute `(Get-AipServiceConfiguration).FunctionalState` y compruebe si el estado es `Enabled` .</span><span class="sxs-lookup"><span data-stu-id="c0d9b-133">Run `(Get-AipServiceConfiguration).FunctionalState` and check if the state is `Enabled`.</span></span>

2. <span data-ttu-id="c0d9b-134">Si el estado funcional es `Disabled` , ejecute `Enable-AipService` .</span><span class="sxs-lookup"><span data-stu-id="c0d9b-134">If the functional state is `Disabled`, run `Enable-AipService`.</span></span>

### <a name="step-2-configure-dns-encryption"></a><span data-ttu-id="c0d9b-135">Paso 2: Configurar el cifrado DNS</span><span class="sxs-lookup"><span data-stu-id="c0d9b-135">Step 2: Configure DNS encryption</span></span>

<span data-ttu-id="c0d9b-136">Para que el cifrado funcione correctamente, las aplicaciones cliente de Office deben conectarse a la instancia china del servicio y arrancar desde allí.</span><span class="sxs-lookup"><span data-stu-id="c0d9b-136">For encryption to work correctly, Office client applications must connect to the China instance of the service and bootstrap from there.</span></span> <span data-ttu-id="c0d9b-137">Para redirigir las aplicaciones cliente a la instancia de servicio correcta, el administrador del espacio empresarial debe configurar un registro SRV dns con información sobre la dirección URL de Azure RMS.</span><span class="sxs-lookup"><span data-stu-id="c0d9b-137">To redirect client applications to the right service instance, the tenant admin must configure a DNS SRV record with information about the Azure RMS URL.</span></span> <span data-ttu-id="c0d9b-138">Sin el registro SRV de DNS, la aplicación cliente intentará conectarse a la instancia de nube pública de forma predeterminada y producirá un error.</span><span class="sxs-lookup"><span data-stu-id="c0d9b-138">Without the DNS SRV record, the client application will attempt to connect to the public cloud instance by default and will fail.</span></span>

<span data-ttu-id="c0d9b-139">Además, se supone que los usuarios iniciarán sesión con un nombre de usuario basado en el dominio propiedad del inquilino (por ejemplo, ), y no con el nombre de usuario `joe@contoso.cn` `onmschina` (por ejemplo, `joe@contoso.onmschina.cn` ).</span><span class="sxs-lookup"><span data-stu-id="c0d9b-139">Also, the assumption is that users will log in with a username based off the tenant-owned domain (for example, `joe@contoso.cn`), and not the `onmschina` username (for example, `joe@contoso.onmschina.cn`).</span></span> <span data-ttu-id="c0d9b-140">El nombre de dominio del nombre de usuario se usa para la redirección dns a la instancia de servicio correcta.</span><span class="sxs-lookup"><span data-stu-id="c0d9b-140">The domain name from the username is used for DNS redirection to the correct service instance.</span></span>

#### <a name="configure-dns-encryption---windows"></a><span data-ttu-id="c0d9b-141">Configurar el cifrado DNS: Windows</span><span class="sxs-lookup"><span data-stu-id="c0d9b-141">Configure DNS encryption - Windows</span></span>

1. <span data-ttu-id="c0d9b-142">Obtener el id. de RMS:</span><span class="sxs-lookup"><span data-stu-id="c0d9b-142">Get the RMS ID:</span></span>

    1. <span data-ttu-id="c0d9b-143">Inicie PowerShell como administrador.</span><span class="sxs-lookup"><span data-stu-id="c0d9b-143">Launch PowerShell as an administrator.</span></span>
    2. <span data-ttu-id="c0d9b-144">Si el módulo AIPService no está instalado, ejecute `Install-Module AipService` .</span><span class="sxs-lookup"><span data-stu-id="c0d9b-144">If the AIPService module isn't installed, run `Install-Module AipService`.</span></span>
    3. <span data-ttu-id="c0d9b-145">Conectarse al servicio mediante `Connect-AipService -environmentname azurechinacloud` .</span><span class="sxs-lookup"><span data-stu-id="c0d9b-145">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
    4. <span data-ttu-id="c0d9b-146">Ejecute `(Get-AipServiceConfiguration).RightsManagementServiceId` para obtener el identificador de RMS.</span><span class="sxs-lookup"><span data-stu-id="c0d9b-146">Run `(Get-AipServiceConfiguration).RightsManagementServiceId` to get the RMS ID.</span></span>

2. <span data-ttu-id="c0d9b-147">Inicie sesión en el proveedor dns, vaya a la configuración dns del dominio y, a continuación, agregue un nuevo registro SRV.</span><span class="sxs-lookup"><span data-stu-id="c0d9b-147">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>

    - <span data-ttu-id="c0d9b-148">Service = `_rmsredir`</span><span class="sxs-lookup"><span data-stu-id="c0d9b-148">Service = `_rmsredir`</span></span>
    - <span data-ttu-id="c0d9b-149">Protocolo = `_http`</span><span class="sxs-lookup"><span data-stu-id="c0d9b-149">Protocol = `_http`</span></span>
    - <span data-ttu-id="c0d9b-150">Name = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="c0d9b-150">Name = `_tcp`</span></span>
    - <span data-ttu-id="c0d9b-151">Target = `[GUID].rms.aadrm.cn` (donde GUID es el id. de RMS)</span><span class="sxs-lookup"><span data-stu-id="c0d9b-151">Target = `[GUID].rms.aadrm.cn` (where GUID is the RMS ID)</span></span>
    - <span data-ttu-id="c0d9b-152">Priority, Weight, Seconds, TTL = default values</span><span class="sxs-lookup"><span data-stu-id="c0d9b-152">Priority, Weight, Seconds, TTL = default values</span></span>

3. <span data-ttu-id="c0d9b-153">Asocie el dominio personalizado con el inquilino en [Azure Portal](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains).</span><span class="sxs-lookup"><span data-stu-id="c0d9b-153">Associate the custom domain with the tenant in the [Azure portal](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains).</span></span> <span data-ttu-id="c0d9b-154">Esto agregará una entrada en DNS, que puede tardar varios minutos en comprobarse después de agregar el valor a la configuración de DNS.</span><span class="sxs-lookup"><span data-stu-id="c0d9b-154">This will add an entry in DNS, which might take several minutes to get verified after you add the value to the DNS settings.</span></span>

4. <span data-ttu-id="c0d9b-155">Inicie sesión en el Centro de administración de Microsoft 365 con las credenciales de administración global correspondientes y agregue el dominio (por ejemplo, `contoso.cn` ) para la creación de usuarios.</span><span class="sxs-lookup"><span data-stu-id="c0d9b-155">Log in to the Microsoft 365 admin center with the corresponding global admin credentials and add the domain (for example, `contoso.cn`) for user creation.</span></span> <span data-ttu-id="c0d9b-156">En el proceso de comprobación, es posible que se necesiten cambios dns adicionales.</span><span class="sxs-lookup"><span data-stu-id="c0d9b-156">In the verification process, additional DNS changes might be required.</span></span> <span data-ttu-id="c0d9b-157">Una vez que se realiza la comprobación, se pueden crear usuarios.</span><span class="sxs-lookup"><span data-stu-id="c0d9b-157">Once verification is done, users can be created.</span></span>

#### <a name="configure-dns-encryption---mac-ios-android"></a><span data-ttu-id="c0d9b-158">Configurar el cifrado DNS: Mac, iOS, Android</span><span class="sxs-lookup"><span data-stu-id="c0d9b-158">Configure DNS encryption - Mac, iOS, Android</span></span>

<span data-ttu-id="c0d9b-159">Inicie sesión en el proveedor dns, vaya a la configuración dns del dominio y, a continuación, agregue un nuevo registro SRV.</span><span class="sxs-lookup"><span data-stu-id="c0d9b-159">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>

- <span data-ttu-id="c0d9b-160">Service = `_rmsdisco`</span><span class="sxs-lookup"><span data-stu-id="c0d9b-160">Service = `_rmsdisco`</span></span>
- <span data-ttu-id="c0d9b-161">Protocolo = `_http`</span><span class="sxs-lookup"><span data-stu-id="c0d9b-161">Protocol = `_http`</span></span>
- <span data-ttu-id="c0d9b-162">Name = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="c0d9b-162">Name = `_tcp`</span></span>
- <span data-ttu-id="c0d9b-163">Target = `api.aadrm.cn`</span><span class="sxs-lookup"><span data-stu-id="c0d9b-163">Target = `api.aadrm.cn`</span></span>
- <span data-ttu-id="c0d9b-164">Port = `80`</span><span class="sxs-lookup"><span data-stu-id="c0d9b-164">Port = `80`</span></span>
- <span data-ttu-id="c0d9b-165">Priority, Weight, Seconds, TTL = default values</span><span class="sxs-lookup"><span data-stu-id="c0d9b-165">Priority, Weight, Seconds, TTL = default values</span></span>

### <a name="step-3-install-and-configure-the-aip-unified-labeling-client"></a><span data-ttu-id="c0d9b-166">Paso 3: Instalar y configurar el cliente de etiquetado unificado AIP</span><span class="sxs-lookup"><span data-stu-id="c0d9b-166">Step 3: Install and configure the AIP unified labeling client</span></span>

<span data-ttu-id="c0d9b-167">Descargue el cliente de etiquetado unificado AIP desde el [Centro de descarga de Microsoft](https://www.microsoft.com/download/details.aspx?id=53018).</span><span class="sxs-lookup"><span data-stu-id="c0d9b-167">Download the AIP unified labeling client from the [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>

<span data-ttu-id="c0d9b-168">Para más información, vea:</span><span class="sxs-lookup"><span data-stu-id="c0d9b-168">For more information, see:</span></span>

- [<span data-ttu-id="c0d9b-169">Documentación de AIP</span><span class="sxs-lookup"><span data-stu-id="c0d9b-169">AIP documentation</span></span>](/azure/information-protection/)
- [<span data-ttu-id="c0d9b-170">Historial de versiones de AIP y directiva de soporte técnico</span><span class="sxs-lookup"><span data-stu-id="c0d9b-170">AIP version history and support policy</span></span>](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)
- [<span data-ttu-id="c0d9b-171">Requisitos del sistema AIP</span><span class="sxs-lookup"><span data-stu-id="c0d9b-171">AIP system requirements</span></span>](/azure/information-protection/requirements)
- [<span data-ttu-id="c0d9b-172">Inicio rápido de AIP: implementar el cliente AIP</span><span class="sxs-lookup"><span data-stu-id="c0d9b-172">AIP quickstart: Deploy the AIP client</span></span>](/azure/information-protection/quickstart-deploy-client)
- [<span data-ttu-id="c0d9b-173">Guía de administrador de AIP</span><span class="sxs-lookup"><span data-stu-id="c0d9b-173">AIP administrator guide</span></span>](/azure/information-protection/rms-client/clientv2-admin-guide)
- [<span data-ttu-id="c0d9b-174">Guía del usuario de AIP</span><span class="sxs-lookup"><span data-stu-id="c0d9b-174">AIP user guide</span></span>](/azure/information-protection/rms-client/clientv2-user-guide)
- [<span data-ttu-id="c0d9b-175">Obtenga información sobre las etiquetas de confidencialidad de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c0d9b-175">Learn about Microsoft 365 sensitivity labels</span></span>](../../compliance/sensitivity-labels.md)

### <a name="step-4-configure-aip-apps-on-windows"></a><span data-ttu-id="c0d9b-176">Paso 4: Configurar aplicaciones AIP en Windows</span><span class="sxs-lookup"><span data-stu-id="c0d9b-176">Step 4: Configure AIP apps on Windows</span></span>

<span data-ttu-id="c0d9b-177">Las aplicaciones AIP en Windows necesitan la siguiente clave del Registro para apuntarlas a la nube soberana correcta para Azure China:</span><span class="sxs-lookup"><span data-stu-id="c0d9b-177">AIP apps on Windows need the following registry key to point them to the correct sovereign cloud for Azure China:</span></span>

- <span data-ttu-id="c0d9b-178">Nodo del Registro = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`</span><span class="sxs-lookup"><span data-stu-id="c0d9b-178">Registry node = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`</span></span>
- <span data-ttu-id="c0d9b-179">Name = `CloudEnvType`</span><span class="sxs-lookup"><span data-stu-id="c0d9b-179">Name = `CloudEnvType`</span></span>
- <span data-ttu-id="c0d9b-180">Valor = `6` (valor predeterminado = 0)</span><span class="sxs-lookup"><span data-stu-id="c0d9b-180">Value = `6` (default = 0)</span></span>
- <span data-ttu-id="c0d9b-181">Type = `REG_DWORD`</span><span class="sxs-lookup"><span data-stu-id="c0d9b-181">Type = `REG_DWORD`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c0d9b-182">Asegúrese de que no elimina la clave del Registro después de una desinstalación.</span><span class="sxs-lookup"><span data-stu-id="c0d9b-182">Make sure you don't delete the registry key after an uninstall.</span></span> <span data-ttu-id="c0d9b-183">Si la clave está vacía, incorrecta o inexistente, la funcionalidad se comportará como el valor predeterminado (valor predeterminado = 0 para la nube comercial).</span><span class="sxs-lookup"><span data-stu-id="c0d9b-183">If the key is empty, incorrect, or non-existent, the functionality will behave as the default value (default value = 0 for the commercial cloud).</span></span> <span data-ttu-id="c0d9b-184">Si la clave está vacía o incorrecta, también se agrega un error de impresión al registro.</span><span class="sxs-lookup"><span data-stu-id="c0d9b-184">If the key is empty or incorrect, a print error is also added to the log.</span></span>

### <a name="step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs"></a><span data-ttu-id="c0d9b-185">Paso 5: Instalar el escáner local de AIP y administrar trabajos de detección de contenido</span><span class="sxs-lookup"><span data-stu-id="c0d9b-185">Step 5: Install the AIP on-premises scanner and manage content scan jobs</span></span>

<span data-ttu-id="c0d9b-186">Instale el escáner local de AIP para examinar la red y los recursos compartidos de contenido en busca de datos confidenciales y aplicar etiquetas de clasificación y protección según lo configurado en la directiva de su organización.</span><span class="sxs-lookup"><span data-stu-id="c0d9b-186">Install the AIP on-premises scanner to scan your network and content shares for sensitive data, and apply classification and protection labels as configured in your organization's policy.</span></span>

- <span data-ttu-id="c0d9b-187">Al crear y configurar aplicaciones de Azure AD para el comando [Set-AIPAuthentication,](/powershell/module/azureinformationprotection/set-aipauthentication) el panel Solicitar permisos **de api** muestra las API que mi organización usa en lugar de la pestaña API de **Microsoft.**  Seleccione las **API que usa mi organización para,** a continuación, seleccionar Azure Rights Management **Services**.</span><span class="sxs-lookup"><span data-stu-id="c0d9b-187">When creating and configuring Azure AD applications for the [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication) command, the **Request API permissions** pane shows the **APIs my organization uses** tab instead of the **Microsoft APIs** tab. Select the **APIs my organization uses** to then select **Azure Rights Management Services**.</span></span>

- <span data-ttu-id="c0d9b-188">Al instalar el escáner y administrar los trabajos de análisis de contenido, use los cmdlets siguientes en lugar de la interfaz de Azure Portal que usan las ofertas comerciales:</span><span class="sxs-lookup"><span data-stu-id="c0d9b-188">When installing the scanner and managing your content scan jobs, use the following cmdlets instead of the Azure portal interface that's used by the commercial offerings:</span></span><br><br>

    | <span data-ttu-id="c0d9b-189">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="c0d9b-189">Cmdlet</span></span> | <span data-ttu-id="c0d9b-190">Descripción</span><span class="sxs-lookup"><span data-stu-id="c0d9b-190">Description</span></span> |
    |--|--|
    | [<span data-ttu-id="c0d9b-191">Add-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="c0d9b-191">Add-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/add-aipscannerrepository) | <span data-ttu-id="c0d9b-192">Agrega un nuevo repositorio al trabajo de examen de contenido.</span><span class="sxs-lookup"><span data-stu-id="c0d9b-192">Adds a new repository to your content scan job.</span></span> |
    | [<span data-ttu-id="c0d9b-193">Get-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="c0d9b-193">Get-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/get-aipscannercontentscanjob) | <span data-ttu-id="c0d9b-194">Obtiene detalles sobre el trabajo de examen de contenido.</span><span class="sxs-lookup"><span data-stu-id="c0d9b-194">Gets details about your content scan job.</span></span> |
    | [<span data-ttu-id="c0d9b-195">Get-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="c0d9b-195">Get-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/get-aipscannerrepository) | <span data-ttu-id="c0d9b-196">Obtiene detalles sobre los repositorios definidos para el trabajo de examen de contenido.</span><span class="sxs-lookup"><span data-stu-id="c0d9b-196">Gets details about repositories defined for your content scan job.</span></span> |
    | [<span data-ttu-id="c0d9b-197">Remove-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="c0d9b-197">Remove-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/remove-aipscannercontentscanjob) | <span data-ttu-id="c0d9b-198">Elimina el trabajo de examen de contenido.</span><span class="sxs-lookup"><span data-stu-id="c0d9b-198">Deletes your content scan job.</span></span> |
    | [<span data-ttu-id="c0d9b-199">Remove-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="c0d9b-199">Remove-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/remove-aipscannerrepository) | <span data-ttu-id="c0d9b-200">Quita un repositorio del trabajo de examen de contenido.</span><span class="sxs-lookup"><span data-stu-id="c0d9b-200">Removes a repository from your content scan job.</span></span> |
    | [<span data-ttu-id="c0d9b-201">Set-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="c0d9b-201">Set-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) | <span data-ttu-id="c0d9b-202">Define la configuración del trabajo de examen de contenido.</span><span class="sxs-lookup"><span data-stu-id="c0d9b-202">Defines settings for your content scan job.</span></span> |
    | [<span data-ttu-id="c0d9b-203">Set-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="c0d9b-203">Set-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/set-aipscannerrepository) | <span data-ttu-id="c0d9b-204">Define la configuración de un repositorio existente en el trabajo de examen de contenido.</span><span class="sxs-lookup"><span data-stu-id="c0d9b-204">Defines settings for an existing repository in your content scan job.</span></span> |
    | | |

> [!TIP]
> <span data-ttu-id="c0d9b-205">Al [instalar el escáner,](/azure/information-protection/deploy-aip-scanner-configure-install#install-the-scanner)use el mismo nombre de clúster en el comando [Install-AIPScanner](/powershell/module/azureinformationprotection/install-aipscanner) para asociar varios nodos de escáner al mismo clúster.</span><span class="sxs-lookup"><span data-stu-id="c0d9b-205">When [installing the scanner](/azure/information-protection/deploy-aip-scanner-configure-install#install-the-scanner), use the same cluster name in the [Install-AIPScanner](/powershell/module/azureinformationprotection/install-aipscanner) command to associate multiple scanner nodes to the same cluster.</span></span> <span data-ttu-id="c0d9b-206">El uso del mismo clúster para varios nodos de escáner permite que varios escáneres funcionen juntos para realizar los exámenes.</span><span class="sxs-lookup"><span data-stu-id="c0d9b-206">Using the same cluster for multiple scanner nodes enables multiple scanners to work together to perform your scans.</span></span>
> 
> <span data-ttu-id="c0d9b-207">Use el cmdlet [Get-AIPScannerConfiguration](/powershell/module/azureinformationprotection/get-aipscannerconfiguration) para devolver detalles sobre el clúster.</span><span class="sxs-lookup"><span data-stu-id="c0d9b-207">Use the [Get-AIPScannerConfiguration](/powershell/module/azureinformationprotection/get-aipscannerconfiguration) cmdlet to return details about your cluster.</span></span>
> 
<span data-ttu-id="c0d9b-208">Para obtener más información, vea ¿Qué es el escáner de etiquetado unificado de [Azure Information Protection?](/azure/information-protection/deploy-aip-scanner) y Administrar los trabajos de examen de contenido [solo con PowerShell](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer).</span><span class="sxs-lookup"><span data-stu-id="c0d9b-208">For more information, see [What is the Azure Information Protection unified labeling scanner?](/azure/information-protection/deploy-aip-scanner) and [Manage your content scan jobs using PowerShell only](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer).</span></span>