---
title: Supervisión de la seguridad de exploración web en Microsoft Defender para endpoint
description: Usar la protección web en Microsoft Defender para endpoint para supervisar la seguridad de exploración web
keywords: protección web, protección contra amenazas web, exploración web, supervisión, informes, tarjetas, lista de dominios, seguridad, phishing, malware, exploit, sitios web, protección de red, Edge, Internet Explorer, Chrome, Firefox, explorador web
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
ms.openlocfilehash: ee6388c779d2c5bc09a82f5e9064d1b981e885cb
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "51687428"
---
# <a name="monitor-web-browsing-security"></a><span data-ttu-id="0c662-104">Supervisar la seguridad de exploración web</span><span class="sxs-lookup"><span data-stu-id="0c662-104">Monitor web browsing security</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0c662-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="0c662-105">**Applies to:**</span></span>
- [<span data-ttu-id="0c662-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="0c662-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="0c662-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0c662-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="0c662-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="0c662-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="0c662-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="0c662-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

<span data-ttu-id="0c662-110">La protección web le permite supervisar la seguridad de navegación web de su organización a través de informes **en Informes > protección web** en el Centro de seguridad de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="0c662-110">Web protection lets you monitor your organization’s web browsing security through reports under **Reports > Web protection** in the Microsoft Defender Security Center.</span></span> <span data-ttu-id="0c662-111">El informe contiene tarjetas que proporcionan estadísticas de detección de amenazas web.</span><span class="sxs-lookup"><span data-stu-id="0c662-111">The report contains cards that provide web threat detection statistics.</span></span>

- <span data-ttu-id="0c662-112">**Detecciones** de protección contra amenazas web con el tiempo: esta tarjeta de tendencia muestra el número de amenazas web detectadas por tipo durante el período de tiempo seleccionado (Últimos 30 días, Últimos 3 meses, Últimos 6 meses)</span><span class="sxs-lookup"><span data-stu-id="0c662-112">**Web threat protection detections over time** - this trending card displays the number of web threats detected by type during the selected time period (Last 30 days, Last 3 months, Last 6 months)</span></span>
 
    ![Imagen de la tarjeta que muestra detecciones de protección contra amenazas web con el tiempo](images/wtp-blocks-over-time.png)

- <span data-ttu-id="0c662-114">**Resumen de protección contra** amenazas web: esta tarjeta muestra el total de detecciones de amenazas web en los últimos 30 días, mostrando la distribución entre los diferentes tipos de amenazas web.</span><span class="sxs-lookup"><span data-stu-id="0c662-114">**Web threat protection summary** - this card displays the total web threat detections in the past 30 days, showing distribution across the different types of web threats.</span></span> <span data-ttu-id="0c662-115">Al seleccionar un segmento, se abre la lista de dominios que se encontraron con sitios web malintencionados o no deseados.</span><span class="sxs-lookup"><span data-stu-id="0c662-115">Selecting a slice opens the list of the domains that were found with malicious or unwanted websites.</span></span>

    ![Imagen de la tarjeta que muestra el resumen de protección contra amenazas web](images/wtp-summary.png)

>[!Note]
><span data-ttu-id="0c662-117">Puede tardar hasta 12 horas antes de que un bloque se refleje en las tarjetas o en la lista de dominios.</span><span class="sxs-lookup"><span data-stu-id="0c662-117">It can take up to 12 hours before a block is reflected in the cards or the domain list.</span></span>

## <a name="types-of-web-threats"></a><span data-ttu-id="0c662-118">Tipos de amenazas web</span><span class="sxs-lookup"><span data-stu-id="0c662-118">Types of web threats</span></span>

<span data-ttu-id="0c662-119">La protección web categoriza los sitios web malintencionados y no deseados como:</span><span class="sxs-lookup"><span data-stu-id="0c662-119">Web protection categorizes malicious and unwanted websites as:</span></span>

- <span data-ttu-id="0c662-120">**Phishing:** sitios web que contienen formularios web suplantados y otros mecanismos de suplantación de identidad diseñados para engañar a los usuarios para que divulgen credenciales y otra información confidencial</span><span class="sxs-lookup"><span data-stu-id="0c662-120">**Phishing** - websites that contain spoofed web forms and other phishing mechanisms designed to trick users into divulging credentials and other sensitive information</span></span>
- <span data-ttu-id="0c662-121">**Malintencionado: sitios** web que hospedan malware y código de vulnerabilidad</span><span class="sxs-lookup"><span data-stu-id="0c662-121">**Malicious** - websites that host malware and exploit code</span></span>
- <span data-ttu-id="0c662-122">**Indicador personalizado:** sitios web cuyas direcciones URL o dominios ha agregado a la lista de [indicadores personalizados](manage-indicators.md) para bloquear</span><span class="sxs-lookup"><span data-stu-id="0c662-122">**Custom indicator** - websites whose URLs or domains you've added to your [custom indicator list](manage-indicators.md) for blocking</span></span>

## <a name="view-the-domain-list"></a><span data-ttu-id="0c662-123">Ver la lista de dominios</span><span class="sxs-lookup"><span data-stu-id="0c662-123">View the domain list</span></span>

<span data-ttu-id="0c662-124">Seleccione una categoría de amenaza web específica en la **tarjeta de** resumen de protección contra amenazas web para abrir la **página Dominios.**</span><span class="sxs-lookup"><span data-stu-id="0c662-124">Select a specific web threat category in the **Web threat protection summary** card to open the **Domains** page.</span></span> <span data-ttu-id="0c662-125">Esta página muestra la lista de dominios bajo esa categoría de amenaza.</span><span class="sxs-lookup"><span data-stu-id="0c662-125">This page displays the list of the domains under that threat category.</span></span> <span data-ttu-id="0c662-126">La página proporciona la siguiente información para cada dominio:</span><span class="sxs-lookup"><span data-stu-id="0c662-126">The page provides the following information for each domain:</span></span>

- <span data-ttu-id="0c662-127">**Recuento de acceso:** número de solicitudes de direcciones URL en el dominio</span><span class="sxs-lookup"><span data-stu-id="0c662-127">**Access count** - number of requests for URLs in the domain</span></span>
- <span data-ttu-id="0c662-128">**Bloques:** número de veces que se bloquearon las solicitudes</span><span class="sxs-lookup"><span data-stu-id="0c662-128">**Blocks** - number of times requests were blocked</span></span>
- <span data-ttu-id="0c662-129">**Tendencia de acceso:** cambio en el número de intentos de acceso</span><span class="sxs-lookup"><span data-stu-id="0c662-129">**Access trend** - change in number of access attempts</span></span>
- <span data-ttu-id="0c662-130">**Categoría de amenaza:** tipo de amenaza web</span><span class="sxs-lookup"><span data-stu-id="0c662-130">**Threat category** - type of web threat</span></span>
- <span data-ttu-id="0c662-131">**Dispositivos:** número de dispositivos con intentos de acceso</span><span class="sxs-lookup"><span data-stu-id="0c662-131">**Devices** - number of devices with access attempts</span></span>

<span data-ttu-id="0c662-132">Seleccione un dominio para ver la lista de dispositivos que han intentado obtener acceso a las direcciones URL de ese dominio y la lista de direcciones URL.</span><span class="sxs-lookup"><span data-stu-id="0c662-132">Select a domain to view the list of devices that have attempted to access URLs in that domain and the list of URLs.</span></span>

## <a name="related-topics"></a><span data-ttu-id="0c662-133">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="0c662-133">Related topics</span></span>

- [<span data-ttu-id="0c662-134">Introducción a protección web</span><span class="sxs-lookup"><span data-stu-id="0c662-134">Web protection overview</span></span>](web-protection-overview.md)
- [<span data-ttu-id="0c662-135">Filtrado de contenido web</span><span class="sxs-lookup"><span data-stu-id="0c662-135">Web content filtering</span></span>](web-content-filtering.md)
- [<span data-ttu-id="0c662-136">Protección contra amenazas web</span><span class="sxs-lookup"><span data-stu-id="0c662-136">Web threat protection</span></span>](web-threat-protection.md)
- [<span data-ttu-id="0c662-137">Responder a amenazas web</span><span class="sxs-lookup"><span data-stu-id="0c662-137">Respond to web threats</span></span>](web-protection-response.md)
