---
title: Crear indicadores para direcciones IP y direcciones URL/dominios
ms.reviewer: ''
description: Cree indicadores para direcciones IP y direcciones URL/dominios que definan la detección, prevención y exclusión de entidades.
keywords: ip, url, domain, manage, allowed, blocked, block, clean, malicious, file hash, ip address, urls, domain
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
ms.openlocfilehash: 3cfdc226ec5b476a37d15b67ca6158313e508adf
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51075747"
---
# <a name="create-indicators-for-ips-and-urlsdomains"></a><span data-ttu-id="aef4d-104">Crear indicadores para direcciones IP y direcciones URL/dominios</span><span class="sxs-lookup"><span data-stu-id="aef4d-104">Create indicators for IPs and URLs/domains</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="aef4d-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="aef4d-105">**Applies to:**</span></span>
- [<span data-ttu-id="aef4d-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="aef4d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="aef4d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="aef4d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)



><span data-ttu-id="aef4d-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="aef4d-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="aef4d-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="aef4d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)


<span data-ttu-id="aef4d-110">Defender for Endpoint puede bloquear lo que Microsoft considera direcciones IP/DIRECCIONES URL malintencionadas, a través de Windows Defender SmartScreen para exploradores de Microsoft y a través de Network Protection para exploradores que no son de Microsoft o llamadas realizadas fuera de un explorador.</span><span class="sxs-lookup"><span data-stu-id="aef4d-110">Defender for Endpoint can block what Microsoft deems as malicious IPs/URLs, through Windows Defender SmartScreen for Microsoft browsers, and through Network Protection for non-Microsoft browsers or calls made outside of a browser.</span></span>

<span data-ttu-id="aef4d-111">Microsoft ha administrado el conjunto de datos de inteligencia de amenazas para esto.</span><span class="sxs-lookup"><span data-stu-id="aef4d-111">The threat intelligence data set for this has been managed by Microsoft.</span></span>

<span data-ttu-id="aef4d-112">Al crear indicadores para direcciones IP y direcciones URL o dominios, ahora puede permitir o bloquear direcciones IP, direcciones URL o dominios basados en su propia inteligencia de amenazas.</span><span class="sxs-lookup"><span data-stu-id="aef4d-112">By creating indicators for IPs and URLs or domains, you can now allow or block IPs, URLs, or domains based on your own threat intelligence.</span></span> <span data-ttu-id="aef4d-113">Puedes hacerlo a través de la página de configuración o por grupos de máquinas si consideras que determinados grupos están más o menos en riesgo que otros.</span><span class="sxs-lookup"><span data-stu-id="aef4d-113">You can do this through the settings page or by machine groups if you deem certain groups to be more or less at risk than others.</span></span>

> [!NOTE]
> <span data-ttu-id="aef4d-114">No se admite Inter-Domain de enrutamiento sin clases (CIDR) para direcciones IP.</span><span class="sxs-lookup"><span data-stu-id="aef4d-114">Classless Inter-Domain Routing (CIDR) notation for IP addresses is not supported.</span></span> 

### <a name="before-you-begin"></a><span data-ttu-id="aef4d-115">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="aef4d-115">Before you begin</span></span>
<span data-ttu-id="aef4d-116">Es importante comprender los siguientes requisitos previos antes de crear indicadores para IPS, direcciones URL o dominios:</span><span class="sxs-lookup"><span data-stu-id="aef4d-116">It's important to understand the following prerequisites prior to creating indicators for IPS, URLs, or domains:</span></span>
- <span data-ttu-id="aef4d-117">La dirección URL/IP permiten y bloquean la protección de red del componente Defender for Endpoint para habilitarse en modo de bloqueo.</span><span class="sxs-lookup"><span data-stu-id="aef4d-117">URL/IP allow and block relies on the Defender for Endpoint component Network Protection to be enabled in block mode.</span></span> <span data-ttu-id="aef4d-118">Para obtener más información sobre la protección de red y las instrucciones de configuración, vea [Enable network protection](enable-network-protection.md).</span><span class="sxs-lookup"><span data-stu-id="aef4d-118">For more information on Network Protection and configuration instructions, see [Enable network protection](enable-network-protection.md).</span></span>
- <span data-ttu-id="aef4d-119">La versión del cliente Antimalware debe ser 4.18.1906.x o posterior.</span><span class="sxs-lookup"><span data-stu-id="aef4d-119">The Antimalware client version must be 4.18.1906.x or later.</span></span> 
- <span data-ttu-id="aef4d-120">Compatible con máquinas en Windows 10, versión 1709 o posterior.</span><span class="sxs-lookup"><span data-stu-id="aef4d-120">Supported on machines on Windows 10, version 1709 or later.</span></span> 
- <span data-ttu-id="aef4d-121">Asegúrese de **que los indicadores de red personalizados** están habilitados en el Centro de seguridad de **Microsoft Defender > configuración > características avanzadas**.</span><span class="sxs-lookup"><span data-stu-id="aef4d-121">Ensure that **Custom network indicators** is enabled in **Microsoft Defender Security Center > Settings > Advanced features**.</span></span> <span data-ttu-id="aef4d-122">Para obtener más información, vea [Características avanzadas](advanced-features.md).</span><span class="sxs-lookup"><span data-stu-id="aef4d-122">For more information, see [Advanced features](advanced-features.md).</span></span>
- <span data-ttu-id="aef4d-123">Para obtener compatibilidad con indicadores en iOS, vea [Configure custom indicators](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/ios-configure-features#configure-custom-indicators).</span><span class="sxs-lookup"><span data-stu-id="aef4d-123">For support of indicators on iOS, see [Configure custom indicators](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/ios-configure-features#configure-custom-indicators).</span></span>


> [!IMPORTANT]
> <span data-ttu-id="aef4d-124">Solo se pueden agregar direcciones IP externas a la lista de indicadores.</span><span class="sxs-lookup"><span data-stu-id="aef4d-124">Only external IPs can be added to the indicator list.</span></span> <span data-ttu-id="aef4d-125">Los indicadores no se pueden crear para ip internas.</span><span class="sxs-lookup"><span data-stu-id="aef4d-125">Indicators cannot be created for internal IPs.</span></span>
> <span data-ttu-id="aef4d-126">Para escenarios de protección web, se recomienda usar las funcionalidades integradas en Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="aef4d-126">For web protection scenarios, we recommend using the built-in capabilities in Microsoft Edge.</span></span> <span data-ttu-id="aef4d-127">Microsoft Edge aprovecha [Network Protection para](network-protection.md) inspeccionar el tráfico de red y permite bloques para TCP, HTTP y HTTPS (TLS).</span><span class="sxs-lookup"><span data-stu-id="aef4d-127">Microsoft Edge leverages [Network Protection](network-protection.md) to inspect network traffic and allows blocks for TCP, HTTP, and HTTPS (TLS).</span></span> <span data-ttu-id="aef4d-128">Para todos los demás procesos, los escenarios de protección web aprovechan la protección de red para la inspección y la aplicación:</span><span class="sxs-lookup"><span data-stu-id="aef4d-128">For all other processes, web protection scenarios leverage Network Protection for inspection and enforcement:</span></span> <br>
> <span data-ttu-id="aef4d-129">NOTA:</span><span class="sxs-lookup"><span data-stu-id="aef4d-129">NOTE:</span></span>
> - <span data-ttu-id="aef4d-130">La IP es compatible con los tres protocolos</span><span class="sxs-lookup"><span data-stu-id="aef4d-130">IP is supported for all three protocols</span></span>
> - <span data-ttu-id="aef4d-131">Solo se admiten direcciones IP únicas (sin bloques CIDR ni intervalos IP)</span><span class="sxs-lookup"><span data-stu-id="aef4d-131">Only single IP addresses are supported (no CIDR blocks or IP ranges)</span></span>
> - <span data-ttu-id="aef4d-132">Las direcciones URL cifradas (ruta de acceso completa) solo se pueden bloquear en exploradores de terceros (Internet Explorer, Edge)</span><span class="sxs-lookup"><span data-stu-id="aef4d-132">Encrypted URLs (full path) can only be blocked on first party browsers (Internet Explorer, Edge)</span></span>
> - <span data-ttu-id="aef4d-133">Las direcciones URL cifradas (solo FQDN) se pueden bloquear fuera de los exploradores de terceros (Internet Explorer, Edge)</span><span class="sxs-lookup"><span data-stu-id="aef4d-133">Encrypted URLS (FQDN only) can be blocked outside of first party browsers (Internet Explorer, Edge)</span></span>
> - <span data-ttu-id="aef4d-134">Los bloques de ruta de acceso url completos se pueden aplicar en el nivel de dominio y todas las direcciones URL sin cifrar</span><span class="sxs-lookup"><span data-stu-id="aef4d-134">Full URL path blocks can be applied on the domain level and all unencrypted URLs</span></span>
 
> [!NOTE]
> <span data-ttu-id="aef4d-135">Puede haber hasta 2 horas de latencia (normalmente menos) entre el momento en que se realiza la acción y la dirección URL e IP bloqueadas.</span><span class="sxs-lookup"><span data-stu-id="aef4d-135">There may be up to 2 hours of latency (usually less) between the time the action is taken, and the URL and IP being blocked.</span></span> 

### <a name="create-an-indicator-for-ips-urls-or-domains-from-the-settings-page"></a><span data-ttu-id="aef4d-136">Crear un indicador de direcciones IP, direcciones URL o dominios desde la página de configuración</span><span class="sxs-lookup"><span data-stu-id="aef4d-136">Create an indicator for IPs, URLs, or domains from the settings page</span></span>

1. <span data-ttu-id="aef4d-137">En el panel de navegación, seleccione  >  **Indicadores de configuración**.</span><span class="sxs-lookup"><span data-stu-id="aef4d-137">In the navigation pane, select **Settings** > **Indicators**.</span></span>  

2. <span data-ttu-id="aef4d-138">Seleccione la **pestaña Direcciones IP o DIRECCIONES URL/Dominios.**</span><span class="sxs-lookup"><span data-stu-id="aef4d-138">Select the **IP addresses or URLs/Domains** tab.</span></span>

3. <span data-ttu-id="aef4d-139">Seleccione **Agregar elemento**.</span><span class="sxs-lookup"><span data-stu-id="aef4d-139">Select **Add item**.</span></span>

4. <span data-ttu-id="aef4d-140">Especifique los siguientes detalles:</span><span class="sxs-lookup"><span data-stu-id="aef4d-140">Specify the following details:</span></span>
   - <span data-ttu-id="aef4d-141">Indicador: especifique los detalles de la entidad y defina la expiración del indicador.</span><span class="sxs-lookup"><span data-stu-id="aef4d-141">Indicator - Specify the entity details and define the expiration of the indicator.</span></span>
   - <span data-ttu-id="aef4d-142">Action: especifique la acción que se va a realizar y proporcione una descripción.</span><span class="sxs-lookup"><span data-stu-id="aef4d-142">Action - Specify the action to be taken and provide a description.</span></span>
   - <span data-ttu-id="aef4d-143">Ámbito: defina el ámbito del grupo de máquinas.</span><span class="sxs-lookup"><span data-stu-id="aef4d-143">Scope - Define the scope of the machine group.</span></span>

5. <span data-ttu-id="aef4d-144">Revise los detalles de la pestaña Resumen y, a continuación, haga clic **en Guardar**.</span><span class="sxs-lookup"><span data-stu-id="aef4d-144">Review the details in the Summary tab, then click **Save**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="aef4d-145">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="aef4d-145">Related topics</span></span>
- [<span data-ttu-id="aef4d-146">Crear indicadores</span><span class="sxs-lookup"><span data-stu-id="aef4d-146">Create indicators</span></span>](manage-indicators.md)
- [<span data-ttu-id="aef4d-147">Crear indicadores para archivos</span><span class="sxs-lookup"><span data-stu-id="aef4d-147">Create indicators for files</span></span>](indicator-file.md)
- [<span data-ttu-id="aef4d-148">Crear indicadores basados en certificados</span><span class="sxs-lookup"><span data-stu-id="aef4d-148">Create indicators based on certificates</span></span>](indicator-certificates.md)
- [<span data-ttu-id="aef4d-149">Administrar indicadores</span><span class="sxs-lookup"><span data-stu-id="aef4d-149">Manage indicators</span></span>](indicator-manage.md)
