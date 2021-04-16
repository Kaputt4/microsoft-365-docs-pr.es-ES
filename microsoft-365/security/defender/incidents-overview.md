---
title: Incidentes en Microsoft 365 Defender
description: Investigar incidentes vistos en todos los dispositivos, usuarios y buzones de correo.
keywords: incidentes, alertas, investigar, correlación, ataque, equipos, dispositivos, usuarios, identidades, identidad, buzón, correo electrónico, 365, Microsoft, M365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
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
ms.openlocfilehash: e1e028f7b58df07eccf945b3a79012b4ea12366d
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861628"
---
# <a name="incidents-in-microsoft-365-defender"></a><span data-ttu-id="5262b-104">Incidentes en Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5262b-104">Incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="5262b-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="5262b-105">**Applies to:**</span></span>
- <span data-ttu-id="5262b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5262b-106">Microsoft 365 Defender</span></span>

> <span data-ttu-id="5262b-107">¿Quiere experimentar Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="5262b-107">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="5262b-108">Puede [evaluarlo en un entorno de pruebas](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) o bien [ejecutar el proyecto piloto en producción](m365d-pilot.md?ocid=cx-evalpilot).</span><span class="sxs-lookup"><span data-stu-id="5262b-108">You can [evaluate it in a lab environment](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) or [run your pilot project in production](m365d-pilot.md?ocid=cx-evalpilot).</span></span>
>

<span data-ttu-id="5262b-109">Un incidente en Microsoft 365 Defender es una colección de alertas correlacionadas y datos asociados que son la historia de un ataque.</span><span class="sxs-lookup"><span data-stu-id="5262b-109">An incident in Microsoft 365 Defender is a collection of correlated alerts and associated data that make up the story of an attack.</span></span> 

<span data-ttu-id="5262b-110">Los servicios y aplicaciones de Microsoft 365 crean alertas cuando detectan un evento o actividad sospechosos o malintencionados.</span><span class="sxs-lookup"><span data-stu-id="5262b-110">Microsoft 365 services and apps create alerts when they detect a suspicious or malicious event or activity.</span></span> <span data-ttu-id="5262b-111">Las alertas individuales proporcionan pistas valiosas sobre un ataque completado o en curso.</span><span class="sxs-lookup"><span data-stu-id="5262b-111">Individual alerts provide valuable clues about a completed or ongoing attack.</span></span> <span data-ttu-id="5262b-112">Sin embargo, los ataques suelen emplear varias técnicas en distintos tipos de entidades, como dispositivos, usuarios y buzones.</span><span class="sxs-lookup"><span data-stu-id="5262b-112">However, attacks typically employ various techniques against different types of entities, such as devices, users, and mailboxes.</span></span> <span data-ttu-id="5262b-113">El resultado son varias alertas para varias entidades del espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="5262b-113">The result is multiple alerts for multiple entities in your tenant.</span></span> 

<span data-ttu-id="5262b-114">Dado que unir las alertas individuales para obtener información sobre un ataque puede ser un desafío y un consumo de tiempo, Microsoft 365 Defender agrega automáticamente las alertas y su información asociada en un incidente.</span><span class="sxs-lookup"><span data-stu-id="5262b-114">Because piecing the individual alerts together to gain insight into an attack can be challenging and time-consuming, Microsoft 365 Defender automatically aggregates the alerts and their associated information into an incident.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents.png" alt-text="Cómo Microsoft 365 Defender correlaciona eventos de entidades en un incidente":::

<span data-ttu-id="5262b-116">Vea esta breve introducción a los incidentes en Microsoft 365 Defender (4 minutos).</span><span class="sxs-lookup"><span data-stu-id="5262b-116">Watch this short overview of incidents in Microsoft 365 Defender (4 minutes).</span></span>

<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

<span data-ttu-id="5262b-117">La agrupación de alertas relacionadas en un incidente le ofrece una vista completa de un ataque.</span><span class="sxs-lookup"><span data-stu-id="5262b-117">Grouping related alerts into an incident gives you a comprehensive view of an attack.</span></span> <span data-ttu-id="5262b-118">Por ejemplo, puede ver:</span><span class="sxs-lookup"><span data-stu-id="5262b-118">For example, you can see:</span></span>

- <span data-ttu-id="5262b-119">Donde se inició el ataque.</span><span class="sxs-lookup"><span data-stu-id="5262b-119">Where the attack started.</span></span>
- <span data-ttu-id="5262b-120">Qué tácticas se usaron.</span><span class="sxs-lookup"><span data-stu-id="5262b-120">What tactics were used.</span></span>
- <span data-ttu-id="5262b-121">Cuánto ha llegado el ataque a su inquilino.</span><span class="sxs-lookup"><span data-stu-id="5262b-121">How far the attack has gone into your tenant.</span></span>
- <span data-ttu-id="5262b-122">El ámbito del ataque, como el número de dispositivos, usuarios y buzones de correo afectados.</span><span class="sxs-lookup"><span data-stu-id="5262b-122">The scope of the attack, such as how many devices, users, and mailboxes were impacted.</span></span> 
- <span data-ttu-id="5262b-123">Todos los datos asociados con el ataque.</span><span class="sxs-lookup"><span data-stu-id="5262b-123">All of the data associated with the attack.</span></span>

<span data-ttu-id="5262b-124">Si [está habilitado,](m365d-enable.md)Microsoft 365 Defender puede investigar y resolver alertas automáticamente a través de la automatización y la inteligencia artificial.</span><span class="sxs-lookup"><span data-stu-id="5262b-124">If [enabled](m365d-enable.md), Microsoft 365 Defender can automatically investigate and resolve alerts through automation and artificial intelligence.</span></span> <span data-ttu-id="5262b-125">También puedes realizar pasos de corrección adicionales para resolver el ataque.</span><span class="sxs-lookup"><span data-stu-id="5262b-125">You can also perform additional remediation steps to resolve the attack.</span></span> 

## <a name="incidents-and-alerts-in-the-microsoft-365-security-center"></a><span data-ttu-id="5262b-126">Incidentes y alertas en el centro de seguridad de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5262b-126">Incidents and alerts in the Microsoft 365 security center</span></span>

<span data-ttu-id="5262b-127">Puede administrar incidentes desde incidentes **& alertas > incidentes** en el inicio rápido del centro de seguridad de Microsoft 365 ([security.microsoft.com](https://security.microsoft.com)).</span><span class="sxs-lookup"><span data-stu-id="5262b-127">You manage incidents from **Incidents & alerts > Incidents** on the quick launch of the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)).</span></span> <span data-ttu-id="5262b-128">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="5262b-128">Here's an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="La página Incidentes en el Centro de seguridad de Microsoft 365":::

<span data-ttu-id="5262b-130">Al seleccionar un nombre de incidente, se muestra un resumen del incidente y se proporciona acceso a las pestañas con información adicional.</span><span class="sxs-lookup"><span data-stu-id="5262b-130">Selecting an incident name displays a summary of the incident and provides access to tabs with additional information.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-ss-incident-summary.png" alt-text="Ejemplo de la página Resumen de un incidente en el Centro de seguridad de Microsoft 365":::

<span data-ttu-id="5262b-132">Las pestañas adicionales para un incidente son:</span><span class="sxs-lookup"><span data-stu-id="5262b-132">The additional tabs for an incident are:</span></span>

- <span data-ttu-id="5262b-133">Alertas</span><span class="sxs-lookup"><span data-stu-id="5262b-133">Alerts</span></span> 

  <span data-ttu-id="5262b-134">Todas las alertas relacionadas con el incidente y su información.</span><span class="sxs-lookup"><span data-stu-id="5262b-134">All the alerts related to the incident and their information.</span></span>

- <span data-ttu-id="5262b-135">Dispositivos</span><span class="sxs-lookup"><span data-stu-id="5262b-135">Devices</span></span>

  <span data-ttu-id="5262b-136">Todos los dispositivos que se han identificado para formar parte o relacionados con el incidente.</span><span class="sxs-lookup"><span data-stu-id="5262b-136">All the devices that have been identified to be part of or related to the incident.</span></span>

- <span data-ttu-id="5262b-137">Usuarios</span><span class="sxs-lookup"><span data-stu-id="5262b-137">Users</span></span>

  <span data-ttu-id="5262b-138">Todos los usuarios identificados para formar parte del incidente o relacionados con ellos.</span><span class="sxs-lookup"><span data-stu-id="5262b-138">All the users that have been identified to be part of or related to the incident.</span></span>

- <span data-ttu-id="5262b-139">Buzones</span><span class="sxs-lookup"><span data-stu-id="5262b-139">Mailboxes</span></span>

  <span data-ttu-id="5262b-140">Todos los buzones que se han identificado para formar parte o relacionados con el incidente.</span><span class="sxs-lookup"><span data-stu-id="5262b-140">All the mailboxes that have been identified to be part of or related to the incident.</span></span>

- <span data-ttu-id="5262b-141">Investigaciones</span><span class="sxs-lookup"><span data-stu-id="5262b-141">Investigations</span></span>

  <span data-ttu-id="5262b-142">Todas las investigaciones automatizadas desencadenadas por alertas en el incidente.</span><span class="sxs-lookup"><span data-stu-id="5262b-142">All the automated investigations triggered by alerts in the incident.</span></span>

- <span data-ttu-id="5262b-143">Evidencia y respuesta</span><span class="sxs-lookup"><span data-stu-id="5262b-143">Evidence and Response</span></span>

  <span data-ttu-id="5262b-144">Todos los eventos admitidos y las entidades sospechosas en las alertas del incidente.</span><span class="sxs-lookup"><span data-stu-id="5262b-144">All the supported events and suspicious entities in the alerts in the incident.</span></span>

<span data-ttu-id="5262b-145">Esta es la relación entre un incidente y sus datos y las pestañas de un incidente en el Centro de seguridad de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5262b-145">Here's the relationship between an incident and its data and the tabs of an incident in the Microsoft 365 security center.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-security-center.png" alt-text="La relación de un incidente y sus datos con las pestañas de un incidente en el Centro de seguridad de Microsoft 365":::

## <a name="next-step"></a><span data-ttu-id="5262b-147">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="5262b-147">Next step</span></span>

<span data-ttu-id="5262b-148">La cola de incidentes de **la página Incidentes** enumera los incidentes más recientes.</span><span class="sxs-lookup"><span data-stu-id="5262b-148">The incident queue from the **Incidents** page lists the most recent incidents.</span></span> <span data-ttu-id="5262b-149">Desde aquí, puede:</span><span class="sxs-lookup"><span data-stu-id="5262b-149">From here, you can:</span></span>

- <span data-ttu-id="5262b-150">Vea qué incidentes deben [priorizarse en](incident-queue.md) función de la gravedad y otros factores.</span><span class="sxs-lookup"><span data-stu-id="5262b-150">See which incidents should be [prioritized](incident-queue.md) based on severity and other factors.</span></span> 
- <span data-ttu-id="5262b-151">Realice una [investigación](investigate-incidents.md) de un incidente.</span><span class="sxs-lookup"><span data-stu-id="5262b-151">Perform an [investigation](investigate-incidents.md) of an incident.</span></span>
- <span data-ttu-id="5262b-152">[Administrar incidentes, lo](manage-incidents.md)que incluye cambiar el nombre, asignarlos, clasificarlos y agregar etiquetas para el flujo de trabajo de administración de incidentes.</span><span class="sxs-lookup"><span data-stu-id="5262b-152">[Manage incidents](manage-incidents.md), which includes renaming, assigning them, classifying, and adding tags for your incident management workflow.</span></span>
