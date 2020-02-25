---
title: Office 365 operado por 21Vianet
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: mnirkhe
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
search.appverid:
- MET150
- GEU150
- GEA150
description: Obtenga más información sobre Azure Information Protection para Office 365 operado por 21Vianet y cómo configurarlo para clientes en China.
monikerRange: o365-21vianet
ms.openlocfilehash: a4eb8c3370a123b939fdccc53eec3905f79ee806
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2020
ms.locfileid: "42247940"
---
# <a name="parity-between-azure-information-protection-for-office-365-operated-by-21vianet-and-commercial-offerings"></a><span data-ttu-id="6e0a6-103">Paridad entre Azure Information Protection para Office 365 ofrecido por 21Vianet y ofertas comerciales</span><span class="sxs-lookup"><span data-stu-id="6e0a6-103">Parity between Azure Information Protection for Office 365 operated by 21Vianet and commercial offerings</span></span>

<span data-ttu-id="6e0a6-104">Aunque nuestro objetivo es ofrecer todas las características y funcionalidades comerciales a los clientes en China con nuestra oferta de Azure Information Protection para Office 365 operado por 21Vianet, hay algunas funcionalidades que nos gustaría destacar.</span><span class="sxs-lookup"><span data-stu-id="6e0a6-104">While our goal is to deliver all commercial features and functionality to customers in China with our Azure Information Protection for Office 365 operated by 21Vianet offer, there is some missing functionality that we'd like to highlight.</span></span>

<span data-ttu-id="6e0a6-105">Estas son las brechas existentes entre Azure Information Protection para Office 365 operado por 21Vianet y nuestras ofertas comerciales a partir de julio de 2019:</span><span class="sxs-lookup"><span data-stu-id="6e0a6-105">These are the existing gaps between Azure Information Protection for Office 365 operated by 21Vianet and our commercial offerings as of July 2019:</span></span>

- <span data-ttu-id="6e0a6-106">Information Rights Management (IRM) solo es compatible con Office 365 ProPlus (compilación 11731,10000 o posterior).</span><span class="sxs-lookup"><span data-stu-id="6e0a6-106">Information Rights Management (IRM) is supported only for Office 365 ProPlus (build 11731.10000 or higher).</span></span> <span data-ttu-id="6e0a6-107">Office 2010, Office 2013 y otras versiones de Office 2016 no son compatibles.</span><span class="sxs-lookup"><span data-stu-id="6e0a6-107">Office 2010, Office 2013, and other Office 2016 versions are not supported.</span></span>

- <span data-ttu-id="6e0a6-108">Actualmente no se puede realizar la migración de Active Directory Rights Management Services (AD RMS) a Azure Information Protection.</span><span class="sxs-lookup"><span data-stu-id="6e0a6-108">Migration from Active Directory Rights Management Services (AD RMS) to Azure Information Protection is currently not available.</span></span>
  
- <span data-ttu-id="6e0a6-109">Se admite el uso compartido de correo electrónico protegido para los usuarios en la nube comercial.</span><span class="sxs-lookup"><span data-stu-id="6e0a6-109">Sharing of protected emails to users in the commercial cloud is supported.</span></span>
  
- <span data-ttu-id="6e0a6-110">Actualmente no está disponible el uso compartido de documentos y datos adjuntos de correo electrónico en los usuarios de la nube comercial.</span><span class="sxs-lookup"><span data-stu-id="6e0a6-110">Sharing of documents and email attachments to users in the commercial cloud is currently not available.</span></span> <span data-ttu-id="6e0a6-111">Esto incluye Office 365 operado por usuarios de 21Vianet en la nube comercial, los usuarios que no son de Office 365 operados por 21Vianet en la nube comercial y los usuarios con una licencia de RMS para personas.</span><span class="sxs-lookup"><span data-stu-id="6e0a6-111">This includes Office 365 operated by 21Vianet users in the commercial cloud, non-Office 365 operated by 21Vianet users in the commercial cloud, and users with an RMS for Individuals license.</span></span>
  
- <span data-ttu-id="6e0a6-112">En estos momentos, IRM con SharePoint (bibliotecas y sitios protegidos por IRM) no está disponible.</span><span class="sxs-lookup"><span data-stu-id="6e0a6-112">IRM with SharePoint (IRM-protected sites and libraries) is currently not available.</span></span>
  
- <span data-ttu-id="6e0a6-113">El conector Rights Management no está disponible en este momento.</span><span class="sxs-lookup"><span data-stu-id="6e0a6-113">The Rights Management Connector is currently not available.</span></span>
  
- <span data-ttu-id="6e0a6-114">La extensión de dispositivos móviles para AD RMS actualmente no está disponible.</span><span class="sxs-lookup"><span data-stu-id="6e0a6-114">The Mobile Device Extension for AD RMS is currently not available.</span></span>

## <a name="configuring-azure-information-protection-for-customers-in-china"></a><span data-ttu-id="6e0a6-115">Configuración de Azure Information Protection para clientes en China</span><span class="sxs-lookup"><span data-stu-id="6e0a6-115">Configuring Azure Information Protection for customers in China</span></span>

### <a name="enable-rights-management-for-the-tenant"></a><span data-ttu-id="6e0a6-116">Habilitar la administración de derechos para el inquilino</span><span class="sxs-lookup"><span data-stu-id="6e0a6-116">Enable Rights Management for the tenant</span></span>

<span data-ttu-id="6e0a6-117">Para que el cifrado funcione correctamente, RMS debe estar habilitado para el inquilino.</span><span class="sxs-lookup"><span data-stu-id="6e0a6-117">For the encryption to work correctly, the RMS must be enabled for the tenant.</span></span>

- <span data-ttu-id="6e0a6-118">Compruebe si el RMS está habilitado:</span><span class="sxs-lookup"><span data-stu-id="6e0a6-118">Check if the RMS is enabled:</span></span>
  1. <span data-ttu-id="6e0a6-119">Inicie PowerShell como administrador.</span><span class="sxs-lookup"><span data-stu-id="6e0a6-119">Launch PowerShell as an administrator.</span></span>
  2. <span data-ttu-id="6e0a6-120">Si el módulo AIPService no está instalado, ejecute `Install-Module AipService`.</span><span class="sxs-lookup"><span data-stu-id="6e0a6-120">If the AIPService module is not installed, run `Install-Module AipService`.</span></span>
  3. <span data-ttu-id="6e0a6-121">Importe el módulo mediante `Import-Module AipService`.</span><span class="sxs-lookup"><span data-stu-id="6e0a6-121">Import the module using `Import-Module AipService`.</span></span>
  4. <span data-ttu-id="6e0a6-122">Conéctese al servicio con `Connect-AipService -environmentname azurechinacloud`.</span><span class="sxs-lookup"><span data-stu-id="6e0a6-122">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
  5. <span data-ttu-id="6e0a6-123">Ejecute `(Get-AipServiceConfiguration).FunctionalState` y compruebe si el estado es `Enabled`.</span><span class="sxs-lookup"><span data-stu-id="6e0a6-123">Run `(Get-AipServiceConfiguration).FunctionalState` and check if the state is `Enabled`.</span></span>

- <span data-ttu-id="6e0a6-124">Si el estado funcional es `Disabled`, ejecute `Enable-AipService`.</span><span class="sxs-lookup"><span data-stu-id="6e0a6-124">If the functional state is `Disabled`, run `Enable-AipService`.</span></span>

### <a name="dns-configuration-for-encryption-windows"></a><span data-ttu-id="6e0a6-125">Configuración de DNS para el cifrado (Windows)</span><span class="sxs-lookup"><span data-stu-id="6e0a6-125">DNS configuration for encryption (Windows)</span></span>

<span data-ttu-id="6e0a6-126">Para que el cifrado funcione correctamente, las aplicaciones cliente de Office deben conectarse a la instancia de China del servicio y arrancar desde allí.</span><span class="sxs-lookup"><span data-stu-id="6e0a6-126">For encryption to work correctly, Office client applications must connect to the China instance of the service and bootstrap from there.</span></span> <span data-ttu-id="6e0a6-127">Para redirigir las aplicaciones cliente a la instancia de servicio correcta, el administrador de inquilinos debe configurar un registro SRV de DNS con información sobre la dirección URL de Azure RMS.</span><span class="sxs-lookup"><span data-stu-id="6e0a6-127">To redirect client applications to the right service instance, the tenant admin must configure a DNS SRV record with information about the Azure RMS URL.</span></span> <span data-ttu-id="6e0a6-128">Sin el registro SRV de DNS, la aplicación cliente intentará conectarse a la instancia de nube pública de forma predeterminada y se producirá un error.</span><span class="sxs-lookup"><span data-stu-id="6e0a6-128">Without the DNS SRV record, the client application will attempt to connect to the public cloud instance by default and will fail.</span></span>

<span data-ttu-id="6e0a6-129">Además, se supone que los usuarios inician sesión con un nombre de usuario basado en el dominio de propiedad del espacio empresarial `joe@contoso.cn`(por ejemplo,) `onmschina` y no en el nombre `joe@contoso.onmschina.cn`de usuario (por ejemplo,).</span><span class="sxs-lookup"><span data-stu-id="6e0a6-129">Also, the assumption is that users will log in with a username based off the tenant-owned domain (for example, `joe@contoso.cn`), and not the `onmschina` username (for example, `joe@contoso.onmschina.cn`).</span></span> <span data-ttu-id="6e0a6-130">El nombre de dominio del nombre de usuario se usa para el redireccionamiento de DNS a la instancia de servicio correcta.</span><span class="sxs-lookup"><span data-stu-id="6e0a6-130">The domain name from the username is used for DNS redirection to the correct service instance.</span></span>

- <span data-ttu-id="6e0a6-131">Obtener el identificador de RMS:</span><span class="sxs-lookup"><span data-stu-id="6e0a6-131">Get the RMS ID:</span></span>
  1. <span data-ttu-id="6e0a6-132">Inicie PowerShell como administrador.</span><span class="sxs-lookup"><span data-stu-id="6e0a6-132">Launch PowerShell as an administrator.</span></span>
  2. <span data-ttu-id="6e0a6-133">Si el módulo AIPService no está instalado, ejecute `Install-Module AipService`.</span><span class="sxs-lookup"><span data-stu-id="6e0a6-133">If the AIPService module is not installed, run `Install-Module AipService`.</span></span>
  3. <span data-ttu-id="6e0a6-134">Conéctese al servicio con `Connect-AipService -environmentname azurechinacloud`.</span><span class="sxs-lookup"><span data-stu-id="6e0a6-134">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
  4. <span data-ttu-id="6e0a6-135">Ejecutar `(Get-AipServiceConfiguration).RightsManagementServiceId` para obtener el identificador de RMS.</span><span class="sxs-lookup"><span data-stu-id="6e0a6-135">Run `(Get-AipServiceConfiguration).RightsManagementServiceId` to get the RMS ID.</span></span>

- <span data-ttu-id="6e0a6-136">Inicie sesión en el proveedor de DNS, navegue hasta la configuración DNS del dominio y, a continuación, agregue un nuevo registro SRV.</span><span class="sxs-lookup"><span data-stu-id="6e0a6-136">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>
  - <span data-ttu-id="6e0a6-137">Servicio = `_rmsredir`</span><span class="sxs-lookup"><span data-stu-id="6e0a6-137">Service = `_rmsredir`</span></span>
  - <span data-ttu-id="6e0a6-138">Protocolo = `_http`</span><span class="sxs-lookup"><span data-stu-id="6e0a6-138">Protocol = `_http`</span></span>
  - <span data-ttu-id="6e0a6-139">Name = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="6e0a6-139">Name = `_tcp`</span></span>
  - <span data-ttu-id="6e0a6-140">Target = `[GUID].rms.aadrm.cn` (donde GUID es el identificador RMS)</span><span class="sxs-lookup"><span data-stu-id="6e0a6-140">Target = `[GUID].rms.aadrm.cn` (where GUID is the RMS ID)</span></span>
  - <span data-ttu-id="6e0a6-141">Prioridad, peso, segundos, TTL = valores predeterminados</span><span class="sxs-lookup"><span data-stu-id="6e0a6-141">Priority, Weight, Seconds, TTL = default values</span></span>

- <span data-ttu-id="6e0a6-142">Asocie el dominio personalizado con el inquilino en [Azure portal](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains).</span><span class="sxs-lookup"><span data-stu-id="6e0a6-142">Associate the custom domain with the tenant in the [Azure portal](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains).</span></span> <span data-ttu-id="6e0a6-143">Esto agregará una entrada en DNS, que puede tardar varios minutos en realizar comprobaciones después de agregar el valor a la configuración de DNS.</span><span class="sxs-lookup"><span data-stu-id="6e0a6-143">This will add an entry in DNS, which might take several minutes to get verified after you add the value to the DNS settings.</span></span>

- <span data-ttu-id="6e0a6-144">Inicie sesión en el centro de administración de Microsoft 365 con las credenciales de administrador global correspondientes y agregue el dominio `contoso.cn`(por ejemplo,) para la creación de usuarios.</span><span class="sxs-lookup"><span data-stu-id="6e0a6-144">Log in to the Microsoft 365 admin center with the corresponding global admin credentials and add the domain (for example, `contoso.cn`) for user creation.</span></span> <span data-ttu-id="6e0a6-145">En el proceso de comprobación, es posible que se necesiten cambios de DNS adicionales.</span><span class="sxs-lookup"><span data-stu-id="6e0a6-145">In the verification process, additional DNS changes might be required.</span></span> <span data-ttu-id="6e0a6-146">Una vez realizada la comprobación, se pueden crear usuarios.</span><span class="sxs-lookup"><span data-stu-id="6e0a6-146">Once verification is done, users can be created.</span></span>

### <a name="dns-configuration-for-encryption-mac-ios-android"></a><span data-ttu-id="6e0a6-147">Configuración de DNS para cifrado (Mac, iOS, Android)</span><span class="sxs-lookup"><span data-stu-id="6e0a6-147">DNS configuration for encryption (Mac, iOS, Android)</span></span>

- <span data-ttu-id="6e0a6-148">Inicie sesión en el proveedor de DNS, navegue hasta la configuración DNS del dominio y, a continuación, agregue un nuevo registro SRV.</span><span class="sxs-lookup"><span data-stu-id="6e0a6-148">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>
  - <span data-ttu-id="6e0a6-149">Servicio = `_rmsdisco`</span><span class="sxs-lookup"><span data-stu-id="6e0a6-149">Service = `_rmsdisco`</span></span>
  - <span data-ttu-id="6e0a6-150">Protocolo = `_http`</span><span class="sxs-lookup"><span data-stu-id="6e0a6-150">Protocol = `_http`</span></span>
  - <span data-ttu-id="6e0a6-151">Name = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="6e0a6-151">Name = `_tcp`</span></span>
  - <span data-ttu-id="6e0a6-152">Target = `api.aadrm.cn`</span><span class="sxs-lookup"><span data-stu-id="6e0a6-152">Target = `api.aadrm.cn`</span></span>
  - <span data-ttu-id="6e0a6-153">Port = `80`</span><span class="sxs-lookup"><span data-stu-id="6e0a6-153">Port = `80`</span></span>
  - <span data-ttu-id="6e0a6-154">Prioridad, peso, segundos, TTL = valores predeterminados</span><span class="sxs-lookup"><span data-stu-id="6e0a6-154">Priority, Weight, Seconds, TTL = default values</span></span>
