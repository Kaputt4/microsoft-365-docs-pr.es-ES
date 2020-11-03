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
ms.openlocfilehash: e5ac3e9a02c333d3168c328aa6ad5532c48af99e
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846693"
---
# <a name="incidents-overview-in-microsoft-365-defender"></a><span data-ttu-id="196f8-104">Información general sobre los incidentes en Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="196f8-104">Incidents overview in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="196f8-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="196f8-105">**Applies to:**</span></span>
- <span data-ttu-id="196f8-106">Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="196f8-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="196f8-107">Los incidentes se basan en alertas relacionadas.</span><span class="sxs-lookup"><span data-stu-id="196f8-107">Incidents are based on related alerts.</span></span> <span data-ttu-id="196f8-108">Las alertas se crean cuando se detecta un evento o una actividad maliciosa en la red.</span><span class="sxs-lookup"><span data-stu-id="196f8-108">Alerts are created when a malicious event or activity is seen on your network.</span></span> <span data-ttu-id="196f8-109">Las alertas individuales proporcionan pistas valiosas sobre un ataque en curso.</span><span class="sxs-lookup"><span data-stu-id="196f8-109">Individual alerts provide valuable clues about an on-going attack.</span></span> <span data-ttu-id="196f8-110">Sin embargo, los ataques suelen usar varios vectores y técnicas para llevar a cabo una infracción.</span><span class="sxs-lookup"><span data-stu-id="196f8-110">However, attacks typically employ various vectors and techniques to carry out a breach.</span></span> <span data-ttu-id="196f8-111">Las pistas individuales de Piecing juntas pueden ser complicadas y laboriosas.</span><span class="sxs-lookup"><span data-stu-id="196f8-111">Piecing individual clues together can be challenging and time-consuming.</span></span>

<span data-ttu-id="196f8-112">Este vídeo breve ofrece una introducción a los incidentes en Microsoft 365 defender.</span><span class="sxs-lookup"><span data-stu-id="196f8-112">This short video gives an overview of incidents in Microsoft 365 Defender.</span></span>
<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

<span data-ttu-id="196f8-113">Un incidente es una colección de alertas correlacionadas que componen el caso de un ataque.</span><span class="sxs-lookup"><span data-stu-id="196f8-113">An incident is a collection of correlated alerts that make up the story of an attack.</span></span> <span data-ttu-id="196f8-114">Microsoft 365 defender agrega automáticamente eventos malintencionados y sospechosos que se encuentran en diferentes entidades de dispositivos, usuarios y buzones de la red.</span><span class="sxs-lookup"><span data-stu-id="196f8-114">Malicious and suspicious events that are found in different device, user, and mailbox entities in the network are automatically aggregated by Microsoft 365 Defender.</span></span> <span data-ttu-id="196f8-115">La agrupación de alertas relacionadas en un incidente ofrece a los defensores de seguridad una visión completa de un ataque.</span><span class="sxs-lookup"><span data-stu-id="196f8-115">Grouping related alerts into an incident gives security defenders a comprehensive view of an attack.</span></span> 

<span data-ttu-id="196f8-116">Por ejemplo, los defensores de seguridad pueden ver dónde se inició el ataque, qué tácticas se usaron y hasta qué punto ha ido el ataque a la red.</span><span class="sxs-lookup"><span data-stu-id="196f8-116">For instance, security defenders can see where the attack started, what tactics were used, and how far the attack has gone into the network.</span></span> <span data-ttu-id="196f8-117">También pueden ver el ámbito del ataque, por ejemplo, Cuántos dispositivos, usuarios y buzones de correo se vieron afectados, el grado de gravedad del impacto y otros detalles sobre las entidades afectadas.</span><span class="sxs-lookup"><span data-stu-id="196f8-117">They can also see the scope of the attack, like how many devices, users, and mailboxes were impacted, how severe the impact was, and other details about affected entities.</span></span>

<span data-ttu-id="196f8-118">Si se habilita, Microsoft 365 defender puede investigar y resolver automáticamente las alertas individuales a través de la automatización y la inteligencia artificial.</span><span class="sxs-lookup"><span data-stu-id="196f8-118">If enabled, Microsoft 365 Defender can automatically investigate and resolve the individual alerts through automation and artificial intelligence.</span></span> <span data-ttu-id="196f8-119">Los defensores de seguridad también pueden realizar pasos de corrección adicionales para resolver el ataque directamente desde la vista incidentes.</span><span class="sxs-lookup"><span data-stu-id="196f8-119">Security defenders can also perform additional remediation steps to resolve the attack straight from the incidents view.</span></span> 

<span data-ttu-id="196f8-120">Los incidentes de los últimos 30 días se muestran en la cola de incidentes.</span><span class="sxs-lookup"><span data-stu-id="196f8-120">Incidents from the last 30 days are shown in the incident queue.</span></span> <span data-ttu-id="196f8-121">Desde aquí, los defensores de seguridad pueden ver qué incidentes deben priorizarse según el nivel de riesgo y otros factores.</span><span class="sxs-lookup"><span data-stu-id="196f8-121">From here, security defenders can see which incidents should be prioritized based on risk level and other factors.</span></span> 

<span data-ttu-id="196f8-122">Los defensores de la seguridad también pueden cambiar el nombre de los incidentes, asignarlos a analistas individuales, clasificar y agregar etiquetas a incidentes para una experiencia de administración de incidentes mejor y más personalizada.</span><span class="sxs-lookup"><span data-stu-id="196f8-122">Security defenders can also rename incidents, assign them to individual analysts, classify, and add tags to incidents for a better and more customized incident management experience.</span></span>



## <a name="see-also"></a><span data-ttu-id="196f8-123">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="196f8-123">See also</span></span>
- [<span data-ttu-id="196f8-124">Priorizar incidentes</span><span class="sxs-lookup"><span data-stu-id="196f8-124">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="196f8-125">Investigar incidentes</span><span class="sxs-lookup"><span data-stu-id="196f8-125">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="196f8-126">Administrar incidentes</span><span class="sxs-lookup"><span data-stu-id="196f8-126">Manage incidents</span></span>](manage-incidents.md)
