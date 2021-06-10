---
title: Responder a amenazas web en Microsoft Defender para endpoint
description: Responder a alertas relacionadas con sitios web malintencionados y no deseados. Comprender cómo la protección contra amenazas web informa a los usuarios finales a través de sus exploradores web y Windows notificaciones
keywords: protección web, protección contra amenazas web, exploración web, alertas, respuesta, seguridad, phishing, malware, vulnerabilidad, sitios web, protección de red, Edge, Internet Explorer, Chrome, Firefox, explorador web, notificaciones, usuarios finales, notificaciones de Windows, página de bloqueo,
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 110b379863b4c6e23c947c56faf831e136231237
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "51688482"
---
# <a name="respond-to-web-threats"></a><span data-ttu-id="51167-105">Responder a amenazas web</span><span class="sxs-lookup"><span data-stu-id="51167-105">Respond to web threats</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="51167-106">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="51167-106">**Applies to:**</span></span>
- [<span data-ttu-id="51167-107">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="51167-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="51167-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="51167-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="51167-109">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="51167-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="51167-110">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="51167-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

<span data-ttu-id="51167-111">La protección web en Microsoft Defender para endpoint le permite investigar y responder eficazmente a alertas relacionadas con sitios web y sitios web malintencionados en su lista de indicadores personalizados.</span><span class="sxs-lookup"><span data-stu-id="51167-111">Web protection in Microsoft Defender for Endpoint lets you efficiently investigate and respond to alerts related to malicious websites and websites in your custom indicator list.</span></span>

## <a name="view-web-threat-alerts"></a><span data-ttu-id="51167-112">Ver alertas de amenazas web</span><span class="sxs-lookup"><span data-stu-id="51167-112">View web threat alerts</span></span>
<span data-ttu-id="51167-113">Microsoft Defender para endpoint genera las siguientes [alertas para](manage-alerts.md) actividades web malintencionadas o sospechosas:</span><span class="sxs-lookup"><span data-stu-id="51167-113">Microsoft Defender for Endpoint generates the following [alerts](manage-alerts.md) for malicious or suspicious web activity:</span></span>
- <span data-ttu-id="51167-114">**Conexión sospechosa bloqueada** por la protección de red: esta alerta se genera cuando un  intento de acceder a un sitio web malintencionado o a un sitio web de la lista de indicadores personalizados se detiene mediante la protección de red en *modo de* bloqueo</span><span class="sxs-lookup"><span data-stu-id="51167-114">**Suspicious connection blocked by network protection** — this alert is generated when an attempt to access a malicious website or a website in your custom indicator list is *stopped* by network protection in *block* mode</span></span>
- <span data-ttu-id="51167-115">**Conexión sospechosa detectada** por la protección de red: esta alerta se genera cuando la protección de red detecta un intento de obtener acceso a un sitio web malintencionado o a un sitio web de la lista de indicadores personalizados en modo de solo *auditoría.*</span><span class="sxs-lookup"><span data-stu-id="51167-115">**Suspicious connection detected by network protection** — this alert is generated when an attempt to access a malicious website or a website in your custom indicator list is detected by network protection in *audit only* mode</span></span>

<span data-ttu-id="51167-116">Cada alerta proporciona la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="51167-116">Each alert provides the following information:</span></span> 
- <span data-ttu-id="51167-117">Dispositivo que intentó acceder al sitio web bloqueado</span><span class="sxs-lookup"><span data-stu-id="51167-117">Device that attempted to access the blocked website</span></span>
- <span data-ttu-id="51167-118">Aplicación o programa usado para enviar la solicitud web</span><span class="sxs-lookup"><span data-stu-id="51167-118">Application or program used to send the web request</span></span>
- <span data-ttu-id="51167-119">Dirección URL malintencionada en la lista de indicadores personalizados</span><span class="sxs-lookup"><span data-stu-id="51167-119">Malicious URL or URL in the custom indicator list</span></span>
- <span data-ttu-id="51167-120">Acciones recomendadas para respondedores</span><span class="sxs-lookup"><span data-stu-id="51167-120">Recommended actions for responders</span></span>

![Imagen de una alerta relacionada con la protección contra amenazas web](images/wtp-alert.png)

>[!Note]
><span data-ttu-id="51167-122">Para reducir el volumen de alertas, Microsoft Defender para endpoint consolida las detecciones de amenazas web para el mismo dominio en el mismo dispositivo cada día en una sola alerta.</span><span class="sxs-lookup"><span data-stu-id="51167-122">To reduce the volume of alerts, Microsoft Defender for Endpoint consolidates web threat detections for the same domain on the same device each day to a single alert.</span></span> <span data-ttu-id="51167-123">Solo se genera una alerta y se cuenta en el informe [de protección web](web-protection-monitoring.md).</span><span class="sxs-lookup"><span data-stu-id="51167-123">Only one alert is generated and counted into the [web protection report](web-protection-monitoring.md).</span></span>

## <a name="inspect-website-details"></a><span data-ttu-id="51167-124">Inspeccionar detalles del sitio web</span><span class="sxs-lookup"><span data-stu-id="51167-124">Inspect website details</span></span>
<span data-ttu-id="51167-125">Puedes profundizar seleccionando la dirección URL o el dominio del sitio web en la alerta.</span><span class="sxs-lookup"><span data-stu-id="51167-125">You can dive deeper by selecting the URL or domain of the website in the alert.</span></span> <span data-ttu-id="51167-126">Esto abre una página sobre esa dirección URL o dominio en particular con información diversa, como:</span><span class="sxs-lookup"><span data-stu-id="51167-126">This opens a page about that particular URL or domain with various information, including:</span></span>
- <span data-ttu-id="51167-127">Dispositivos que intentaron acceder al sitio web</span><span class="sxs-lookup"><span data-stu-id="51167-127">Devices that attempted to access website</span></span>
- <span data-ttu-id="51167-128">Incidentes y alertas relacionados con el sitio web</span><span class="sxs-lookup"><span data-stu-id="51167-128">Incidents and alerts related to the website</span></span>
- <span data-ttu-id="51167-129">Con qué frecuencia se ha visto el sitio web en eventos de su organización</span><span class="sxs-lookup"><span data-stu-id="51167-129">How frequent the website was seen in events in your organization</span></span>

    ![Imagen de la página de detalles de la entidad de dirección URL o dominio](images/wtp-website-details.png)

[<span data-ttu-id="51167-131">Más información sobre las páginas de entidad de dominio o URL</span><span class="sxs-lookup"><span data-stu-id="51167-131">Learn more about URL or domain entity pages</span></span>](investigate-domain.md)

## <a name="inspect-the-device"></a><span data-ttu-id="51167-132">Inspeccionar el dispositivo</span><span class="sxs-lookup"><span data-stu-id="51167-132">Inspect the device</span></span>
<span data-ttu-id="51167-133">También puedes comprobar el dispositivo que intentó obtener acceso a una dirección URL bloqueada.</span><span class="sxs-lookup"><span data-stu-id="51167-133">You can also check the device that attempted to access a blocked URL.</span></span> <span data-ttu-id="51167-134">Al seleccionar el nombre del dispositivo en la página de alerta, se abre una página con información completa sobre el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="51167-134">Selecting the name of the device on the alert page opens a page with comprehensive information about the device.</span></span>

[<span data-ttu-id="51167-135">Más información sobre las páginas de entidad de dispositivo</span><span class="sxs-lookup"><span data-stu-id="51167-135">Learn more about device entity pages</span></span>](investigate-machines.md)

## <a name="web-browser-and-windows-notifications-for-end-users"></a><span data-ttu-id="51167-136">Explorador web y notificaciones Windows para usuarios finales</span><span class="sxs-lookup"><span data-stu-id="51167-136">Web browser and Windows notifications for end users</span></span>

<span data-ttu-id="51167-137">Con la protección web en Microsoft Defender para endpoint, los usuarios finales no podrán visitar sitios web malintencionados o no deseados Microsoft Edge otros exploradores.</span><span class="sxs-lookup"><span data-stu-id="51167-137">With web protection in Microsoft Defender for Endpoint, your end users will be prevented from visiting malicious or unwanted websites using Microsoft Edge or other browsers.</span></span> <span data-ttu-id="51167-138">Dado que el bloqueo se realiza [mediante la protección de red,](network-protection.md)verán un error genérico desde el explorador web.</span><span class="sxs-lookup"><span data-stu-id="51167-138">Because blocking is performed by [network protection](network-protection.md), they will see a generic error from the web browser.</span></span> <span data-ttu-id="51167-139">También verán una notificación de Windows.</span><span class="sxs-lookup"><span data-stu-id="51167-139">They will also see a notification from Windows.</span></span>

<span data-ttu-id="51167-140">![Imagen de Microsoft Edge muestra un error 403 y la Windows notificación ](images/wtp-browser-blocking-page.png)
 *web bloqueada en Microsoft Edge*</span><span class="sxs-lookup"><span data-stu-id="51167-140">![Image of Microsoft Edge showing a 403 error and the Windows notification](images/wtp-browser-blocking-page.png)
*Web threat blocked on Microsoft Edge*</span></span>

<span data-ttu-id="51167-141">![Imagen del explorador web Chrome que muestra una advertencia de conexión segura y la Windows notificación ](images/wtp-chrome-browser-blocking-page.png)
 *web bloqueada en Chrome*</span><span class="sxs-lookup"><span data-stu-id="51167-141">![Image of Chrome web browser showing a secure connection warning and the Windows notification](images/wtp-chrome-browser-blocking-page.png)
*Web threat blocked on Chrome*</span></span>

## <a name="related-topics"></a><span data-ttu-id="51167-142">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="51167-142">Related topics</span></span>
- [<span data-ttu-id="51167-143">Introducción a protección web</span><span class="sxs-lookup"><span data-stu-id="51167-143">Web protection overview</span></span>](web-protection-overview.md)
- [<span data-ttu-id="51167-144">Filtrado de contenido web</span><span class="sxs-lookup"><span data-stu-id="51167-144">Web content filtering</span></span>](web-content-filtering.md)
- [<span data-ttu-id="51167-145">Protección contra amenazas web</span><span class="sxs-lookup"><span data-stu-id="51167-145">Web threat protection</span></span>](web-threat-protection.md)
- [<span data-ttu-id="51167-146">Supervisar la seguridad web</span><span class="sxs-lookup"><span data-stu-id="51167-146">Monitor web security</span></span>](web-protection-monitoring.md)
