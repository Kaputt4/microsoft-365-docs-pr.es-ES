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
ms.openlocfilehash: 5ea847e822e094049dd8f0b941f22f3bb4f7eff4
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/10/2021
ms.locfileid: "52297181"
---
# <a name="introduction-to-responding-to-your-first-incident"></a><span data-ttu-id="275cd-104">Introducción a la respuesta a su primer incidente</span><span class="sxs-lookup"><span data-stu-id="275cd-104">Introduction to responding to your first incident</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="275cd-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="275cd-105">**Applies to:**</span></span>
- <span data-ttu-id="275cd-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="275cd-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="275cd-107">La estrategia de respuesta a incidentes de una organización determina su capacidad para hacer frente a incidentes de seguridad y ciberdelincuencia cada vez más disruptivos.</span><span class="sxs-lookup"><span data-stu-id="275cd-107">An organization's incident response strategy determines its ability to deal with increasingly disruptive security incidents and cybercrime.</span></span> <span data-ttu-id="275cd-108">Aunque es importante tomar medidas de prevención, la capacidad de actuar rápidamente para contener, eliminar y recuperarse de incidentes detectados puede minimizar los daños y las pérdidas empresariales.</span><span class="sxs-lookup"><span data-stu-id="275cd-108">While taking preventative measures is important, the ability to act quickly to contain, eradicate, and recover from detected incidents can minimize damage and business losses.</span></span>

<span data-ttu-id="275cd-109">Este tutorial de respuesta a incidentes muestra cómo, como parte de un equipo de operaciones de seguridad, puede realizar la mayoría de los pasos clave de respuesta a incidentes en Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="275cd-109">This incident response walkthrough shows how you, as part of a security operations team, can perform most of the key incident response steps within Microsoft 365 Defender.</span></span> <span data-ttu-id="275cd-110">Estos son los pasos:</span><span class="sxs-lookup"><span data-stu-id="275cd-110">Here are the steps:</span></span>

- <span data-ttu-id="275cd-111">Preparación de la postura de seguridad</span><span class="sxs-lookup"><span data-stu-id="275cd-111">Preparation of your security posture</span></span>
- <span data-ttu-id="275cd-112">Para cada incidente:</span><span class="sxs-lookup"><span data-stu-id="275cd-112">For each incident:</span></span>
  - <span data-ttu-id="275cd-113">Paso 1: Triaje y análisis</span><span class="sxs-lookup"><span data-stu-id="275cd-113">Step 1: Triage and analysis</span></span>
  - <span data-ttu-id="275cd-114">Paso 2: Corrección (contención, eliminación y recuperación)</span><span class="sxs-lookup"><span data-stu-id="275cd-114">Step 2: Remediation (containment, eradication, and recovery)</span></span>
  - <span data-ttu-id="275cd-115">Paso 3: Revisión posterior al incidente</span><span class="sxs-lookup"><span data-stu-id="275cd-115">Step 3: Post-incident review</span></span>

<span data-ttu-id="275cd-116">El Instituto Nacional de Estándares y Tecnología (NIST) define un incidente de seguridad como "una ocurrencia que realmente o potencialmente pone en peligro la confidencialidad, integridad o disponibilidad de un sistema de información; o la información que procesa, almacena o transmite el sistema; o que constituye una infracción o una amenaza inminente de violación de las directivas de seguridad, los procedimientos de seguridad o las directivas de uso aceptables".</span><span class="sxs-lookup"><span data-stu-id="275cd-116">A security incident is defined by National Institute of Standards and Technology (NIST) as "an occurrence that actually or potentially jeopardizes the confidentiality, integrity, or availability of an information system; or the information the system processes, stores, or transmits; or that constitutes a violation or imminent threat of violation of security policies, security procedures, or acceptable use policies."</span></span>

<span data-ttu-id="275cd-117">Los incidentes en Microsoft 365 Defender son los puntos de partida lógicos para el análisis y la respuesta a incidentes.</span><span class="sxs-lookup"><span data-stu-id="275cd-117">Incidents in Microsoft 365 Defender are the logical starting points for analysis and incident response.</span></span> <span data-ttu-id="275cd-118">El análisis y la corrección de incidentes suele ser la mayor parte de las tareas de un equipo de operaciones de seguridad.</span><span class="sxs-lookup"><span data-stu-id="275cd-118">Analyzing and remediating incidents typically makes up most of a security operations team's tasks.</span></span>

## <a name="next-step"></a><span data-ttu-id="275cd-119">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="275cd-119">Next step</span></span>

<span data-ttu-id="275cd-120">[![Preparar la organización y Microsoft 365 inquilino](../../media/first-incident-overview/first-incident-path.png)](first-incident-prepare.md)</span><span class="sxs-lookup"><span data-stu-id="275cd-120">[![Prepare your organization and Microsoft 365 tenant](../../media/first-incident-overview/first-incident-path.png)](first-incident-prepare.md)</span></span>

<span data-ttu-id="275cd-121">Asegúrese de que su organización y Microsoft 365 inquilino esté [preparado para el tratamiento de incidentes.](first-incident-prepare.md)</span><span class="sxs-lookup"><span data-stu-id="275cd-121">Make sure your organization and Microsoft 365 tenant is [prepared for incident handling](first-incident-prepare.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="275cd-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="275cd-122">See also</span></span>

<span data-ttu-id="275cd-123">Instrucciones de respuesta a incidentes para Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="275cd-123">Incident response guidance for Microsoft 365 Defender:</span></span>

- [<span data-ttu-id="275cd-124">Información general sobre incidentes</span><span class="sxs-lookup"><span data-stu-id="275cd-124">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="275cd-125">Investigar incidentes</span><span class="sxs-lookup"><span data-stu-id="275cd-125">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="275cd-126">Administrar incidentes</span><span class="sxs-lookup"><span data-stu-id="275cd-126">Manage incidents</span></span>](manage-incidents.md)

<span data-ttu-id="275cd-127">Ejemplos adicionales de las primeras respuestas a incidentes:</span><span class="sxs-lookup"><span data-stu-id="275cd-127">Additional examples of first incident responses:</span></span>

- [<span data-ttu-id="275cd-128">Correo de suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="275cd-128">Phishing email</span></span>](first-incident-path-phishing.md)
- [<span data-ttu-id="275cd-129">Ataque de base de identidad</span><span class="sxs-lookup"><span data-stu-id="275cd-129">Identity-base attack</span></span>](first-incident-path-identity.md)

[<span data-ttu-id="275cd-130">Libros de juegos de respuesta a incidentes detallados</span><span class="sxs-lookup"><span data-stu-id="275cd-130">Detailed incident response playbooks</span></span>](https://docs.microsoft.com/security/compass/incident-response-playbooks)


