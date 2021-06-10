---
title: Proteger su organización contra amenazas web
description: Obtenga información sobre la protección web en Microsoft Defender para endpoint y cómo puede proteger su organización.
keywords: protección web, protección contra amenazas web, navegación web, seguridad, phishing, malware, vulnerabilidad, sitios web, protección de red, Edge, Internet Explorer, Chrome, Firefox, explorador web
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
ms.openlocfilehash: 0c42c05e318390741b94b6d7d1b5394fca961714
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "51688950"
---
# <a name="protect-your-organization-against-web-threats"></a><span data-ttu-id="aa260-104">Proteger su organización contra amenazas web</span><span class="sxs-lookup"><span data-stu-id="aa260-104">Protect your organization against web threats</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="aa260-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="aa260-105">**Applies to:**</span></span>
- [<span data-ttu-id="aa260-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="aa260-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="aa260-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="aa260-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="aa260-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="aa260-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="aa260-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="aa260-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

<span data-ttu-id="aa260-110">La protección contra amenazas web forma parte de [la protección web](web-protection-overview.md) en Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="aa260-110">Web threat protection is part of [Web protection](web-protection-overview.md) in Defender for Endpoint.</span></span> <span data-ttu-id="aa260-111">Usa la [protección de red para](network-protection.md) proteger los dispositivos contra amenazas web.</span><span class="sxs-lookup"><span data-stu-id="aa260-111">It uses [network protection](network-protection.md) to secure your devices against web threats.</span></span> <span data-ttu-id="aa260-112">Al integrar con Microsoft Edge y exploradores de terceros populares como Chrome y Firefox, la protección contra amenazas web detiene las amenazas web sin un proxy web y puede proteger los dispositivos mientras están fuera o localmente.</span><span class="sxs-lookup"><span data-stu-id="aa260-112">By integrating with Microsoft Edge and popular third-party browsers like Chrome and Firefox, web threat protection stops web threats without a web proxy and can protect devices while they are away or on premises.</span></span> <span data-ttu-id="aa260-113">La protección contra amenazas web detiene el acceso a sitios de phishing, vectores de malware, sitios de vulnerabilidad, sitios que no son de confianza o de baja reputación, así como sitios que ha bloqueado en la lista de [indicadores personalizados.](manage-indicators.md)</span><span class="sxs-lookup"><span data-stu-id="aa260-113">Web threat protection stops access to phishing sites, malware vectors, exploit sites, untrusted or low-reputation sites, as well as sites that you have blocked in your [custom indicator list](manage-indicators.md).</span></span>

>[!Note]
><span data-ttu-id="aa260-114">Los dispositivos pueden tardar hasta una hora en recibir nuevos indicadores personalizados.</span><span class="sxs-lookup"><span data-stu-id="aa260-114">It can take up to an hour for devices to receive new custom indicators.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="aa260-115">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="aa260-115">Prerequisites</span></span>
<span data-ttu-id="aa260-116">La protección web usa la protección de red para proporcionar seguridad de navegación web Microsoft Edge exploradores web de terceros.</span><span class="sxs-lookup"><span data-stu-id="aa260-116">Web protection uses network protection to provide web browsing security on Microsoft Edge and third-party web browsers.</span></span>

<span data-ttu-id="aa260-117">Para activar la protección de red en los dispositivos:</span><span class="sxs-lookup"><span data-stu-id="aa260-117">To turn on network protection on your devices:</span></span>
- <span data-ttu-id="aa260-118">Edite la línea base de seguridad de Defender for Endpoint en **Web & Network Protection** para habilitar la protección de red antes de implementarla o volver a implementarla.</span><span class="sxs-lookup"><span data-stu-id="aa260-118">Edit the Defender for Endpoint security baseline under **Web & Network Protection** to enable network protection before deploying or redeploying it.</span></span> [<span data-ttu-id="aa260-119">Obtenga información sobre cómo revisar y asignar la línea base de seguridad de Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="aa260-119">Learn about reviewing and assigning the Defender for Endpoint security baseline</span></span>](configure-machines-security-baseline.md#review-and-assign-the-microsoft-defender-for-endpoint-security-baseline)
- <span data-ttu-id="aa260-120">Activa la protección de red con la configuración de dispositivos de Intune, SCCM, la directiva de grupo o la solución MDM.</span><span class="sxs-lookup"><span data-stu-id="aa260-120">Turn network protection on using Intune device configuration, SCCM, Group Policy, or your MDM solution.</span></span> [<span data-ttu-id="aa260-121">Más información sobre cómo habilitar la protección de red</span><span class="sxs-lookup"><span data-stu-id="aa260-121">Read more about enabling network protection</span></span>](enable-network-protection.md)  

>[!Note]
><span data-ttu-id="aa260-122">Si establece la protección de red en **Solo auditoría,** el bloqueo no estará disponible.</span><span class="sxs-lookup"><span data-stu-id="aa260-122">If you set network protection to **Audit only**, blocking will be unavailable.</span></span> <span data-ttu-id="aa260-123">Además, podrás detectar e registrar intentos de acceso a sitios web malintencionados y no deseados en Microsoft Edge solo.</span><span class="sxs-lookup"><span data-stu-id="aa260-123">Also, you will be able to detect and log attempts to access malicious and unwanted websites on Microsoft Edge only.</span></span>

## <a name="related-topics"></a><span data-ttu-id="aa260-124">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="aa260-124">Related topics</span></span>

- [<span data-ttu-id="aa260-125">Introducción a protección web</span><span class="sxs-lookup"><span data-stu-id="aa260-125">Web protection overview</span></span>](web-protection-overview.md)
- [<span data-ttu-id="aa260-126">Protección contra amenazas web</span><span class="sxs-lookup"><span data-stu-id="aa260-126">Web threat protection</span></span>](web-threat-protection.md)
- [<span data-ttu-id="aa260-127">Supervisar la seguridad web</span><span class="sxs-lookup"><span data-stu-id="aa260-127">Monitor web security</span></span>](web-protection-monitoring.md)
- [<span data-ttu-id="aa260-128">Responder a amenazas web</span><span class="sxs-lookup"><span data-stu-id="aa260-128">Respond to web threats</span></span>](web-protection-response.md)
- [<span data-ttu-id="aa260-129">Protección de red</span><span class="sxs-lookup"><span data-stu-id="aa260-129">Network protection</span></span>](network-protection.md)
