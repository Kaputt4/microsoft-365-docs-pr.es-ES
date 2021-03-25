---
title: Proteger su organización contra amenazas web
description: Obtenga información sobre la protección web en ATP de Microsoft Defender y cómo puede proteger su organización.
keywords: protección web, protección contra amenazas web, navegación web, seguridad, phishing, malware, vulnerabilidad, sitios web, protección de red, Edge, Internet Explorer, Chrome, Firefox, explorador web
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 7754fa586b24fdedaa9691b45f5da4654c882a5b
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185986"
---
# <a name="protect-your-organization-against-web-threats"></a><span data-ttu-id="7ddad-104">Proteger su organización contra amenazas web</span><span class="sxs-lookup"><span data-stu-id="7ddad-104">Protect your organization against web threats</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="7ddad-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="7ddad-105">**Applies to:**</span></span>
- [<span data-ttu-id="7ddad-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="7ddad-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="7ddad-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7ddad-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="7ddad-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="7ddad-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="7ddad-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="7ddad-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

<span data-ttu-id="7ddad-110">La protección contra amenazas web forma parte de [la protección web](web-protection-overview.md) en Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="7ddad-110">Web threat protection is part of [Web protection](web-protection-overview.md) in Defender for Endpoint.</span></span> <span data-ttu-id="7ddad-111">Usa la [protección de red para](network-protection.md) proteger los dispositivos contra amenazas web.</span><span class="sxs-lookup"><span data-stu-id="7ddad-111">It uses [network protection](network-protection.md) to secure your devices against web threats.</span></span> <span data-ttu-id="7ddad-112">Al integrar con Microsoft Edge y exploradores de terceros populares como Chrome y Firefox, la protección contra amenazas web detiene las amenazas web sin un proxy web y puede proteger los dispositivos mientras están fuera o localmente.</span><span class="sxs-lookup"><span data-stu-id="7ddad-112">By integrating with Microsoft Edge and popular third-party browsers like Chrome and Firefox, web threat protection stops web threats without a web proxy and can protect devices while they are away or on premises.</span></span> <span data-ttu-id="7ddad-113">La protección contra amenazas web detiene el acceso a sitios de phishing, vectores de malware, sitios de vulnerabilidad, sitios que no son de confianza o de baja reputación, así como sitios que ha bloqueado en la lista de [indicadores personalizados.](manage-indicators.md)</span><span class="sxs-lookup"><span data-stu-id="7ddad-113">Web threat protection stops access to phishing sites, malware vectors, exploit sites, untrusted or low-reputation sites, as well as sites that you have blocked in your [custom indicator list](manage-indicators.md).</span></span>

>[!Note]
><span data-ttu-id="7ddad-114">Los dispositivos pueden tardar hasta una hora en recibir nuevos indicadores de cliente.</span><span class="sxs-lookup"><span data-stu-id="7ddad-114">It can take up to an hour for devices to receive new customer indicators.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7ddad-115">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="7ddad-115">Prerequisites</span></span>
<span data-ttu-id="7ddad-116">La protección web usa la protección de red para proporcionar seguridad de exploración web en Microsoft Edge y exploradores web de terceros.</span><span class="sxs-lookup"><span data-stu-id="7ddad-116">Web protection uses network protection to provide web browsing security on Microsoft Edge and third-party web browsers.</span></span>

<span data-ttu-id="7ddad-117">Para activar la protección de red en los dispositivos:</span><span class="sxs-lookup"><span data-stu-id="7ddad-117">To turn on network protection on your devices:</span></span>
- <span data-ttu-id="7ddad-118">Edite la línea base de seguridad de Defender for Endpoint en **Web & Network Protection** para habilitar la protección de red antes de implementarla o volver a implementarla.</span><span class="sxs-lookup"><span data-stu-id="7ddad-118">Edit the Defender for Endpoint security baseline under **Web & Network Protection** to enable network protection before deploying or redeploying it.</span></span> [<span data-ttu-id="7ddad-119">Obtenga información sobre cómo revisar y asignar la línea base de seguridad de Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="7ddad-119">Learn about reviewing and assigning the Defender for Endpoint security baseline</span></span>](configure-machines-security-baseline.md#review-and-assign-the-microsoft-defender-for-endpoint-security-baseline)
- <span data-ttu-id="7ddad-120">Activa la protección de red con la configuración de dispositivos de Intune, SCCM, la directiva de grupo o la solución MDM.</span><span class="sxs-lookup"><span data-stu-id="7ddad-120">Turn network protection on using Intune device configuration, SCCM, Group Policy, or your MDM solution.</span></span> [<span data-ttu-id="7ddad-121">Más información sobre cómo habilitar la protección de red</span><span class="sxs-lookup"><span data-stu-id="7ddad-121">Read more about enabling network protection</span></span>](enable-network-protection.md)  

>[!Note]
><span data-ttu-id="7ddad-122">Si establece la protección de red en **Solo auditoría,** el bloqueo no estará disponible.</span><span class="sxs-lookup"><span data-stu-id="7ddad-122">If you set network protection to **Audit only**, blocking will be unavailable.</span></span> <span data-ttu-id="7ddad-123">Además, solo podrá detectar e registrar intentos de acceso a sitios web malintencionados y no deseados en Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="7ddad-123">Also, you will be able to detect and log attempts to access malicious and unwanted websites on Microsoft Edge only.</span></span>

## <a name="related-topics"></a><span data-ttu-id="7ddad-124">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="7ddad-124">Related topics</span></span>

- [<span data-ttu-id="7ddad-125">Introducción a la protección web</span><span class="sxs-lookup"><span data-stu-id="7ddad-125">Web protection overview</span></span>](web-protection-overview.md)
- [<span data-ttu-id="7ddad-126">Protección contra amenazas web</span><span class="sxs-lookup"><span data-stu-id="7ddad-126">Web threat protection</span></span>](web-threat-protection.md)
- [<span data-ttu-id="7ddad-127">Supervisar la seguridad web</span><span class="sxs-lookup"><span data-stu-id="7ddad-127">Monitor web security</span></span>](web-protection-monitoring.md)
- [<span data-ttu-id="7ddad-128">Responder a amenazas web</span><span class="sxs-lookup"><span data-stu-id="7ddad-128">Respond to web threats</span></span>](web-protection-response.md)
- [<span data-ttu-id="7ddad-129">Protección de red</span><span class="sxs-lookup"><span data-stu-id="7ddad-129">Network protection</span></span>](network-protection.md)
