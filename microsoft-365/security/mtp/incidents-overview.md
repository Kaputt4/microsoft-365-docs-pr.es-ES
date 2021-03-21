---
title: Información general sobre incidentes en Microsoft 365 Defender
description: Investigar incidentes vistos en todos los dispositivos, usuarios y buzones de correo.
keywords: incidentes, alertas, investigar, correlación, ataque, equipos, dispositivos, usuarios, identidades, identidad, buzón, correo electrónico, 365, Microsoft, M365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: de3fba2692f5b6df7c7192c328a3911287cd7ce2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928729"
---
# <a name="incidents-overview-in-microsoft-365-defender"></a><span data-ttu-id="f1be8-104">Información general sobre incidentes en Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f1be8-104">Incidents overview in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="f1be8-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="f1be8-105">**Applies to:**</span></span>
- <span data-ttu-id="f1be8-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f1be8-106">Microsoft 365 Defender</span></span>

> <span data-ttu-id="f1be8-107">¿Desea experimentar Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="f1be8-107">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="f1be8-108">Puede [evaluarlo en un entorno de laboratorio o](./mtp-evaluation.md?ocid=cx-docs-MTPtriallab) ejecutar el proyecto piloto en [producción.](./mtp-pilot.md?ocid=cx-evalpilot)</span><span class="sxs-lookup"><span data-stu-id="f1be8-108">You can [evaluate it in a lab environment](./mtp-evaluation.md?ocid=cx-docs-MTPtriallab) or [run your pilot project in production](./mtp-pilot.md?ocid=cx-evalpilot).</span></span>
>


<span data-ttu-id="f1be8-109">Los incidentes se basan en alertas relacionadas.</span><span class="sxs-lookup"><span data-stu-id="f1be8-109">Incidents are based on related alerts.</span></span> <span data-ttu-id="f1be8-110">Las alertas se crean cuando se detecta un evento o una actividad maliciosa en la red.</span><span class="sxs-lookup"><span data-stu-id="f1be8-110">Alerts are created when a malicious event or activity is seen on your network.</span></span> <span data-ttu-id="f1be8-111">Las alertas individuales proporcionan pistas valiosas sobre un ataque en marcha.</span><span class="sxs-lookup"><span data-stu-id="f1be8-111">Individual alerts provide valuable clues about an on-going attack.</span></span> <span data-ttu-id="f1be8-112">Sin embargo, los ataques suelen emplear diversos vectores y técnicas para llevar a cabo una infracción.</span><span class="sxs-lookup"><span data-stu-id="f1be8-112">However, attacks typically employ various vectors and techniques to carry out a breach.</span></span> <span data-ttu-id="f1be8-113">La circular de pistas individuales puede ser difícil y consumir mucho tiempo.</span><span class="sxs-lookup"><span data-stu-id="f1be8-113">Piecing individual clues together can be challenging and time-consuming.</span></span>

<span data-ttu-id="f1be8-114">En este breve vídeo se ofrece información general sobre los incidentes en Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="f1be8-114">This short video gives an overview of incidents in Microsoft 365 Defender.</span></span>
<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

<span data-ttu-id="f1be8-115">Un incidente es una colección de alertas correlacionadas que son la historia de un ataque.</span><span class="sxs-lookup"><span data-stu-id="f1be8-115">An incident is a collection of correlated alerts that make up the story of an attack.</span></span> <span data-ttu-id="f1be8-116">Microsoft 365 Defender agrega automáticamente eventos malintencionados y sospechosos que se encuentran en diferentes entidades de dispositivo, usuario y buzón de correo de la red.</span><span class="sxs-lookup"><span data-stu-id="f1be8-116">Malicious and suspicious events that are found in different device, user, and mailbox entities in the network are automatically aggregated by Microsoft 365 Defender.</span></span> <span data-ttu-id="f1be8-117">La agrupación de alertas relacionadas en un incidente proporciona a los defensores de seguridad una vista completa de un ataque.</span><span class="sxs-lookup"><span data-stu-id="f1be8-117">Grouping related alerts into an incident gives security defenders a comprehensive view of an attack.</span></span> 

<span data-ttu-id="f1be8-118">Por ejemplo, los defensores de seguridad pueden ver dónde comenzó el ataque, qué tácticas se usaron y hasta qué punto el ataque ha llegado a la red.</span><span class="sxs-lookup"><span data-stu-id="f1be8-118">For instance, security defenders can see where the attack started, what tactics were used, and how far the attack has gone into the network.</span></span> <span data-ttu-id="f1be8-119">También pueden ver el ámbito del ataque, como cuántos dispositivos, usuarios y buzones se vieron afectados, qué tan grave fue el impacto y otros detalles sobre las entidades afectadas.</span><span class="sxs-lookup"><span data-stu-id="f1be8-119">They can also see the scope of the attack, like how many devices, users, and mailboxes were impacted, how severe the impact was, and other details about affected entities.</span></span>

<span data-ttu-id="f1be8-120">Si está habilitado, Microsoft 365 Defender puede investigar y resolver automáticamente las alertas individuales a través de la automatización y la inteligencia artificial.</span><span class="sxs-lookup"><span data-stu-id="f1be8-120">If enabled, Microsoft 365 Defender can automatically investigate and resolve the individual alerts through automation and artificial intelligence.</span></span> <span data-ttu-id="f1be8-121">Los defensores de seguridad también pueden realizar pasos de corrección adicionales para resolver el ataque directamente desde la vista incidentes.</span><span class="sxs-lookup"><span data-stu-id="f1be8-121">Security defenders can also perform additional remediation steps to resolve the attack straight from the incidents view.</span></span> 

<span data-ttu-id="f1be8-122">Los incidentes de los últimos 30 días se muestran en la cola de incidentes.</span><span class="sxs-lookup"><span data-stu-id="f1be8-122">Incidents from the last 30 days are shown in the incident queue.</span></span> <span data-ttu-id="f1be8-123">Desde aquí, los defensores de seguridad pueden ver qué incidentes deben priorizarse en función del nivel de riesgo y otros factores.</span><span class="sxs-lookup"><span data-stu-id="f1be8-123">From here, security defenders can see which incidents should be prioritized based on risk level and other factors.</span></span> 

<span data-ttu-id="f1be8-124">Los defensores de seguridad también pueden cambiar el nombre de los incidentes, asignarlos a analistas individuales, clasificar y agregar etiquetas a los incidentes para una experiencia de administración de incidentes mejor y más personalizada.</span><span class="sxs-lookup"><span data-stu-id="f1be8-124">Security defenders can also rename incidents, assign them to individual analysts, classify, and add tags to incidents for a better and more customized incident management experience.</span></span>



## <a name="see-also"></a><span data-ttu-id="f1be8-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="f1be8-125">See also</span></span>
- [<span data-ttu-id="f1be8-126">Priorizar incidentes</span><span class="sxs-lookup"><span data-stu-id="f1be8-126">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="f1be8-127">Investigar incidentes</span><span class="sxs-lookup"><span data-stu-id="f1be8-127">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="f1be8-128">Administrar incidentes</span><span class="sxs-lookup"><span data-stu-id="f1be8-128">Manage incidents</span></span>](manage-incidents.md)