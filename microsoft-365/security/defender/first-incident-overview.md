---
title: Introducción a la respuesta a su primer incidente
description: Conceptos básicos para responder al primer incidente en Microsoft 365 Defender.
keywords: incidentes, alertas, investigar, correlación, ataque, dispositivos, usuarios, identidades, identidad, buzón, correo electrónico, 365, microsoft, m365, respuesta a incidentes, ciberataque
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
ms.openlocfilehash: f66c9821e5db00cc3da5718f52b8aaaeff5a431e
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114759"
---
# <a name="introduction-to-responding-to-your-first-incident"></a><span data-ttu-id="45172-104">Introducción a la respuesta a su primer incidente</span><span class="sxs-lookup"><span data-stu-id="45172-104">Introduction to responding to your first incident</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="45172-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="45172-105">**Applies to:**</span></span>
- <span data-ttu-id="45172-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="45172-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="45172-107">La estrategia de respuesta a incidentes de una organización determina su capacidad para hacer frente a incidentes de seguridad y ciberdelincuencia cada vez más disruptivos.</span><span class="sxs-lookup"><span data-stu-id="45172-107">An organization's incident response strategy determines its ability to deal with increasingly disruptive security incidents and cybercrime.</span></span> <span data-ttu-id="45172-108">Aunque es importante tomar medidas de prevención, la capacidad de actuar rápidamente para contener, eliminar y recuperarse de incidentes detectados puede minimizar los daños y las pérdidas empresariales.</span><span class="sxs-lookup"><span data-stu-id="45172-108">While taking preventative measures is important, the ability to act quickly to contain, eradicate, and recover from detected incidents can minimize damage and business losses.</span></span>

<span data-ttu-id="45172-109">Este tutorial de respuesta a incidentes muestra cómo, como parte de un equipo de operaciones de seguridad, puede realizar la mayoría de los pasos clave de respuesta a incidentes en Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="45172-109">This incident response walkthrough shows how you, as part of a security operations team, can perform most of the key incident response steps within Microsoft 365 Defender.</span></span> <span data-ttu-id="45172-110">Estos son los pasos:</span><span class="sxs-lookup"><span data-stu-id="45172-110">Here are the steps:</span></span>

- <span data-ttu-id="45172-111">Preparación de la postura de seguridad</span><span class="sxs-lookup"><span data-stu-id="45172-111">Preparation of your security posture</span></span>
- <span data-ttu-id="45172-112">Para cada incidente:</span><span class="sxs-lookup"><span data-stu-id="45172-112">For each incident:</span></span>
  - <span data-ttu-id="45172-113">Paso 1: Triaje y análisis</span><span class="sxs-lookup"><span data-stu-id="45172-113">Step 1: Triage and analysis</span></span>
  - <span data-ttu-id="45172-114">Paso 2: Corrección (contención, eliminación y recuperación)</span><span class="sxs-lookup"><span data-stu-id="45172-114">Step 2: Remediation (containment, eradication, and recovery)</span></span>
  - <span data-ttu-id="45172-115">Paso 3: Revisión posterior al incidente</span><span class="sxs-lookup"><span data-stu-id="45172-115">Step 3: Post-incident review</span></span>

<span data-ttu-id="45172-116">El Instituto Nacional de Estándares y Tecnología (NIST) define un incidente de seguridad como "una ocurrencia que realmente o potencialmente pone en peligro la confidencialidad, integridad o disponibilidad de un sistema de información; o la información que procesa, almacena o transmite el sistema; o que constituye una infracción o una amenaza inminente de violación de las directivas de seguridad, los procedimientos de seguridad o las directivas de uso aceptables".</span><span class="sxs-lookup"><span data-stu-id="45172-116">A security incident is defined by National Institute of Standards and Technology (NIST) as "an occurrence that actually or potentially jeopardizes the confidentiality, integrity, or availability of an information system; or the information the system processes, stores, or transmits; or that constitutes a violation or imminent threat of violation of security policies, security procedures, or acceptable use policies."</span></span>

<span data-ttu-id="45172-117">Los incidentes en Microsoft 365 Defender son los puntos de partida lógicos para el análisis y la respuesta a incidentes.</span><span class="sxs-lookup"><span data-stu-id="45172-117">Incidents in Microsoft 365 Defender are the logical starting points for analysis and incident response.</span></span> <span data-ttu-id="45172-118">El análisis y la corrección de incidentes suele ser la mayor parte de las tareas de un equipo de operaciones de seguridad.</span><span class="sxs-lookup"><span data-stu-id="45172-118">Analyzing and remediating incidents typically makes up most of a security operations team's tasks.</span></span>

## <a name="next-step"></a><span data-ttu-id="45172-119">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="45172-119">Next step</span></span>

<span data-ttu-id="45172-120">[![Preparar la organización y Microsoft 365 inquilino](../../media/first-incident-overview/first-incident-path.png)](first-incident-prepare.md)</span><span class="sxs-lookup"><span data-stu-id="45172-120">[![Prepare your organization and Microsoft 365 tenant](../../media/first-incident-overview/first-incident-path.png)](first-incident-prepare.md)</span></span>

<span data-ttu-id="45172-121">Asegúrese de que su organización y Microsoft 365 inquilino esté [preparado para el tratamiento de incidentes.](first-incident-prepare.md)</span><span class="sxs-lookup"><span data-stu-id="45172-121">Make sure your organization and Microsoft 365 tenant is [prepared for incident handling](first-incident-prepare.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="45172-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="45172-122">See also</span></span>

- [<span data-ttu-id="45172-123">Información general sobre incidentes</span><span class="sxs-lookup"><span data-stu-id="45172-123">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="45172-124">Analizar incidentes</span><span class="sxs-lookup"><span data-stu-id="45172-124">Analyze incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="45172-125">Administrar incidentes</span><span class="sxs-lookup"><span data-stu-id="45172-125">Manage incidents</span></span>](manage-incidents.md)
