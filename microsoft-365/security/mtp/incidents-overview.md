---
title: Información general sobre los incidentes en Microsoft 365 defender
description: Investigar incidentes vistos en todos los dispositivos, usuarios y buzones de correo.
keywords: incidentes, alertas, investigar, correlación, ataque, equipos, dispositivos, usuarios, identidades, identidad, buzón, correo electrónico, 365, Microsoft, M365
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 6149b6f128b3c96d2338e325caa8df835c292b13
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/19/2020
ms.locfileid: "49357616"
---
# <a name="incidents-overview-in-microsoft-365-defender"></a><span data-ttu-id="db47f-104">Información general sobre los incidentes en Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="db47f-104">Incidents overview in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="db47f-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="db47f-105">**Applies to:**</span></span>
- <span data-ttu-id="db47f-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="db47f-106">Microsoft 365 Defender</span></span>

> <span data-ttu-id="db47f-107">¿Quiere experimentar Microsoft 365 defender?</span><span class="sxs-lookup"><span data-stu-id="db47f-107">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="db47f-108">Puede [evaluarlo en un entorno de laboratorio](https://aka.ms/mtp-trial-lab) o [ejecutar el proyecto piloto en producción](https://aka.ms/m365d-pilotplaybook).</span><span class="sxs-lookup"><span data-stu-id="db47f-108">You can [evaluate it in a lab environment](https://aka.ms/mtp-trial-lab) or [run your pilot project in production](https://aka.ms/m365d-pilotplaybook).</span></span>
>


<span data-ttu-id="db47f-109">Los incidentes se basan en alertas relacionadas.</span><span class="sxs-lookup"><span data-stu-id="db47f-109">Incidents are based on related alerts.</span></span> <span data-ttu-id="db47f-110">Las alertas se crean cuando se detecta un evento o una actividad maliciosa en la red.</span><span class="sxs-lookup"><span data-stu-id="db47f-110">Alerts are created when a malicious event or activity is seen on your network.</span></span> <span data-ttu-id="db47f-111">Las alertas individuales proporcionan pistas valiosas sobre un ataque en curso.</span><span class="sxs-lookup"><span data-stu-id="db47f-111">Individual alerts provide valuable clues about an on-going attack.</span></span> <span data-ttu-id="db47f-112">Sin embargo, los ataques suelen usar varios vectores y técnicas para llevar a cabo una infracción.</span><span class="sxs-lookup"><span data-stu-id="db47f-112">However, attacks typically employ various vectors and techniques to carry out a breach.</span></span> <span data-ttu-id="db47f-113">Las pistas individuales de Piecing juntas pueden ser complicadas y laboriosas.</span><span class="sxs-lookup"><span data-stu-id="db47f-113">Piecing individual clues together can be challenging and time-consuming.</span></span>

<span data-ttu-id="db47f-114">Este vídeo breve ofrece una introducción a los incidentes en Microsoft 365 defender.</span><span class="sxs-lookup"><span data-stu-id="db47f-114">This short video gives an overview of incidents in Microsoft 365 Defender.</span></span>
<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

<span data-ttu-id="db47f-115">Un incidente es una colección de alertas correlacionadas que componen el caso de un ataque.</span><span class="sxs-lookup"><span data-stu-id="db47f-115">An incident is a collection of correlated alerts that make up the story of an attack.</span></span> <span data-ttu-id="db47f-116">Microsoft 365 defender agrega automáticamente eventos malintencionados y sospechosos que se encuentran en diferentes entidades de dispositivos, usuarios y buzones de la red.</span><span class="sxs-lookup"><span data-stu-id="db47f-116">Malicious and suspicious events that are found in different device, user, and mailbox entities in the network are automatically aggregated by Microsoft 365 Defender.</span></span> <span data-ttu-id="db47f-117">La agrupación de alertas relacionadas en un incidente ofrece a los defensores de seguridad una visión completa de un ataque.</span><span class="sxs-lookup"><span data-stu-id="db47f-117">Grouping related alerts into an incident gives security defenders a comprehensive view of an attack.</span></span> 

<span data-ttu-id="db47f-118">Por ejemplo, los defensores de seguridad pueden ver dónde se inició el ataque, qué tácticas se usaron y hasta qué punto ha ido el ataque a la red.</span><span class="sxs-lookup"><span data-stu-id="db47f-118">For instance, security defenders can see where the attack started, what tactics were used, and how far the attack has gone into the network.</span></span> <span data-ttu-id="db47f-119">También pueden ver el ámbito del ataque, por ejemplo, Cuántos dispositivos, usuarios y buzones de correo se vieron afectados, el grado de gravedad del impacto y otros detalles sobre las entidades afectadas.</span><span class="sxs-lookup"><span data-stu-id="db47f-119">They can also see the scope of the attack, like how many devices, users, and mailboxes were impacted, how severe the impact was, and other details about affected entities.</span></span>

<span data-ttu-id="db47f-120">Si se habilita, Microsoft 365 defender puede investigar y resolver automáticamente las alertas individuales a través de la automatización y la inteligencia artificial.</span><span class="sxs-lookup"><span data-stu-id="db47f-120">If enabled, Microsoft 365 Defender can automatically investigate and resolve the individual alerts through automation and artificial intelligence.</span></span> <span data-ttu-id="db47f-121">Los defensores de seguridad también pueden realizar pasos de corrección adicionales para resolver el ataque directamente desde la vista incidentes.</span><span class="sxs-lookup"><span data-stu-id="db47f-121">Security defenders can also perform additional remediation steps to resolve the attack straight from the incidents view.</span></span> 

<span data-ttu-id="db47f-122">Los incidentes de los últimos 30 días se muestran en la cola de incidentes.</span><span class="sxs-lookup"><span data-stu-id="db47f-122">Incidents from the last 30 days are shown in the incident queue.</span></span> <span data-ttu-id="db47f-123">Desde aquí, los defensores de seguridad pueden ver qué incidentes deben priorizarse según el nivel de riesgo y otros factores.</span><span class="sxs-lookup"><span data-stu-id="db47f-123">From here, security defenders can see which incidents should be prioritized based on risk level and other factors.</span></span> 

<span data-ttu-id="db47f-124">Los defensores de la seguridad también pueden cambiar el nombre de los incidentes, asignarlos a analistas individuales, clasificar y agregar etiquetas a incidentes para una experiencia de administración de incidentes mejor y más personalizada.</span><span class="sxs-lookup"><span data-stu-id="db47f-124">Security defenders can also rename incidents, assign them to individual analysts, classify, and add tags to incidents for a better and more customized incident management experience.</span></span>



## <a name="see-also"></a><span data-ttu-id="db47f-125">Consulta también</span><span class="sxs-lookup"><span data-stu-id="db47f-125">See also</span></span>
- [<span data-ttu-id="db47f-126">Priorizar incidentes</span><span class="sxs-lookup"><span data-stu-id="db47f-126">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="db47f-127">Investigar incidentes</span><span class="sxs-lookup"><span data-stu-id="db47f-127">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="db47f-128">Administrar incidentes</span><span class="sxs-lookup"><span data-stu-id="db47f-128">Manage incidents</span></span>](manage-incidents.md)
