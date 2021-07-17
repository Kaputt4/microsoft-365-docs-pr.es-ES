---
title: Pilot Microsoft Defender for Identity, set up configuration benchmarks, standards, guidelines, and take tutorials about detecting, and remediating various Identity threats like reconnaissance, compromised credential, lateral movement, domain dominance, and exfiltration alerts, conduct user, computer, entity, and lateral movement paths investigation.
description: Pilot Microsoft Defender for Identity, set benchmarks, take tutorials on reconnaissance, compromised credential, lateral movement, domain dominance, and exfiltration alerts, among others.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
ms.date: 07/09/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 14c5b9252e980d1f693139393d26b9405cb1b812
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458549"
---
# <a name="pilot-microsoft-defender-for-identity"></a><span data-ttu-id="761cf-103">Piloto de Microsoft Defender para identidad</span><span class="sxs-lookup"><span data-stu-id="761cf-103">Pilot Microsoft Defender for Identity</span></span>


<span data-ttu-id="761cf-104">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="761cf-104">**Applies to:**</span></span>
- <span data-ttu-id="761cf-105">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="761cf-105">Microsoft 365 Defender</span></span>

<span data-ttu-id="761cf-106">Este artículo es [el paso 3 de 3](eval-defender-identity-overview.md) en el proceso de configuración del entorno de evaluación para Microsoft Defender for Identity.</span><span class="sxs-lookup"><span data-stu-id="761cf-106">This article is [Step 3 of 3](eval-defender-identity-overview.md) in the process of setting up the evaluation environment for Microsoft Defender for Identity.</span></span> <span data-ttu-id="761cf-107">Para obtener más información acerca de este proceso, vea el [artículo de introducción](eval-defender-identity-overview.md).</span><span class="sxs-lookup"><span data-stu-id="761cf-107">For more information about this process, see the [overview article](eval-defender-identity-overview.md).</span></span>

<span data-ttu-id="761cf-108">Siga estos pasos para configurar y configurar el piloto de Microsoft Defender para la identidad.</span><span class="sxs-lookup"><span data-stu-id="761cf-108">Use the following steps to setup and configure the pilot for Microsoft Defender for identity.</span></span> <span data-ttu-id="761cf-109">Tenga en cuenta que las recomendaciones no incluyen la configuración de un grupo piloto.</span><span class="sxs-lookup"><span data-stu-id="761cf-109">Note that the recommendations don't include setting up a pilot group.</span></span> <span data-ttu-id="761cf-110">El procedimiento recomendado es continuar e instalar el sensor en todos los servidores que ejecutan Servicios de dominio de Active Directory (AD DS) y Servicios federados de Active Directory (AD FS).</span><span class="sxs-lookup"><span data-stu-id="761cf-110">The best practice is to go ahead and install the sensor on all of your servers running Active Directory Domain Services (AD DS) and Active Directory Federated Services (AD FS).</span></span>

![Pasos para agregar Microsoft Defender for Identity al entorno de evaluación de Defender](../../media/defender/m365-defender-identity-pilot-steps.png)

<span data-ttu-id="761cf-112">En la tabla siguiente se describen los pasos de la ilustración.</span><span class="sxs-lookup"><span data-stu-id="761cf-112">The following table describes the steps in the illustration.</span></span>

- [<span data-ttu-id="761cf-113">Paso 1: Configurar recomendaciones comparativas para su entorno de identidad</span><span class="sxs-lookup"><span data-stu-id="761cf-113">Step 1: Configure benchmark recommendations for your identity environment</span></span>](#step-1-configure-benchmark-recommendations-for-your-identity-environment)
- [<span data-ttu-id="761cf-114">Paso 2: Probar capacidades: tutoriales para identificar y corregir diferentes tipos de ataques </span><span class="sxs-lookup"><span data-stu-id="761cf-114">Step 2: Try out capabilities — Walk through tutorials for identifying and remediating different attack types </span></span>](#step-2-try-out-capabilities--walk-through-tutorials-for-identifying-and-remediating-different-attack-types)

## <a name="step-1-configure-benchmark-recommendations-for-your-identity-environment"></a><span data-ttu-id="761cf-115">Paso 1.</span><span class="sxs-lookup"><span data-stu-id="761cf-115">Step 1.</span></span> <span data-ttu-id="761cf-116">Configurar recomendaciones de referencia para su entorno de identidad</span><span class="sxs-lookup"><span data-stu-id="761cf-116">Configure benchmark recommendations for your identity environment</span></span>

<span data-ttu-id="761cf-117">Microsoft proporciona recomendaciones de referencia de seguridad para los clientes que usan los servicios de Microsoft Cloud.</span><span class="sxs-lookup"><span data-stu-id="761cf-117">Microsoft provides security benchmark recommendations for customers using Microsoft Cloud services.</span></span> <span data-ttu-id="761cf-118">Azure [Security Benchmark](/security/benchmark/azure/overview) (ASB) proporciona recomendaciones y procedimientos recomendados prescriptivos para ayudar a mejorar la seguridad de las cargas de trabajo, los datos y los servicios en Azure.</span><span class="sxs-lookup"><span data-stu-id="761cf-118">The [Azure Security Benchmark](/security/benchmark/azure/overview) (ASB) provides prescriptive best practices and recommendations to help improve the security of workloads, data, and services on Azure.</span></span>

<span data-ttu-id="761cf-119">Estas recomendaciones de referencia incluyen la línea [base de seguridad de Azure para Microsoft Defender para Identity](/security/benchmark/azure/baselines/defender-for-identity-security-baseline).</span><span class="sxs-lookup"><span data-stu-id="761cf-119">These benchmark recommendations include [Azure security baseline for Microsoft Defender for Identity](/security/benchmark/azure/baselines/defender-for-identity-security-baseline).</span></span> <span data-ttu-id="761cf-120">La implementación de estas recomendaciones puede tardar algún tiempo en planearse e implementarse.</span><span class="sxs-lookup"><span data-stu-id="761cf-120">Implementing these recommendations can take some time to plan and implement.</span></span> <span data-ttu-id="761cf-121">Aunque aumentarán considerablemente la seguridad del entorno de identidad, no deben impedir que continúes evaluando e implementando Microsoft Defender para Identity.</span><span class="sxs-lookup"><span data-stu-id="761cf-121">While these will greatly increase the security of your identity environment, they shouldn't prevent you from continuing to evaluate and implement Microsoft Defender for Identity.</span></span> <span data-ttu-id="761cf-122">Estos se proporcionan aquí para su conocimiento.</span><span class="sxs-lookup"><span data-stu-id="761cf-122">These are provided here for your awareness.</span></span>

## <a name="step-2-try-out-capabilities--walk-through-tutorials-for-identifying-and-remediating-different-attack-types"></a><span data-ttu-id="761cf-123">Paso 2.</span><span class="sxs-lookup"><span data-stu-id="761cf-123">Step 2.</span></span> <span data-ttu-id="761cf-124">Capacidades de prueba: tutoriales para identificar y corregir diferentes tipos de ataques</span><span class="sxs-lookup"><span data-stu-id="761cf-124">Try out capabilities — Walk through tutorials for identifying and remediating different attack types</span></span>

<span data-ttu-id="761cf-125">La documentación de Microsoft Defender para identidades incluye una serie de tutoriales que le guían por el proceso de identificación y corrección de varios tipos de ataques.</span><span class="sxs-lookup"><span data-stu-id="761cf-125">The Microsoft Defender for Identity documentation includes a series of tutorials that walk through the process of identifying and remediating various attack types.</span></span>

<span data-ttu-id="761cf-126">Pruebe los tutoriales de Defender for Identity:</span><span class="sxs-lookup"><span data-stu-id="761cf-126">Try out Defender for Identity tutorials:</span></span>
- [<span data-ttu-id="761cf-127">Alertas de reconocimiento</span><span class="sxs-lookup"><span data-stu-id="761cf-127">Reconnaissance alerts</span></span>](/defender-for-identity/reconnaissance-alerts)
- [<span data-ttu-id="761cf-128">Alertas de credenciales comprometidas</span><span class="sxs-lookup"><span data-stu-id="761cf-128">Compromised credential alerts</span></span>](/defender-for-identity/compromised-credentials-alerts)
- [<span data-ttu-id="761cf-129">Alertas de movimiento lateral</span><span class="sxs-lookup"><span data-stu-id="761cf-129">Lateral movement alerts</span></span>](/defender-for-identity/lateral-movement-alerts)
- [<span data-ttu-id="761cf-130">Alertas de dominio dominante</span><span class="sxs-lookup"><span data-stu-id="761cf-130">Domain dominance alerts</span></span>](/defender-for-identity/domain-dominance-alerts)
- [<span data-ttu-id="761cf-131">Alertas de exfiltración</span><span class="sxs-lookup"><span data-stu-id="761cf-131">Exfiltration alerts</span></span>](/defender-for-identity/exfiltration-alerts)
- [<span data-ttu-id="761cf-132">Investigar a un usuario</span><span class="sxs-lookup"><span data-stu-id="761cf-132">Investigate a user</span></span>](/defender-for-identity/investigate-a-user)
- [<span data-ttu-id="761cf-133">Investigar un equipo</span><span class="sxs-lookup"><span data-stu-id="761cf-133">Investigate a computer</span></span>](/defender-for-identity/investigate-a-computer)
- [<span data-ttu-id="761cf-134">Investigar rutas de movimiento lateral</span><span class="sxs-lookup"><span data-stu-id="761cf-134">Investigate lateral movement paths</span></span>](/defender-for-identity/investigate-lateral-movement-path)
- [<span data-ttu-id="761cf-135">Investigar entidades</span><span class="sxs-lookup"><span data-stu-id="761cf-135">Investigate entities</span></span>](/defender-for-identity/investigate-entity)

## <a name="next-steps"></a><span data-ttu-id="761cf-136">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="761cf-136">Next steps</span></span>

[<span data-ttu-id="761cf-137">Evaluar Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="761cf-137">Evaluate Microsoft Defender for Office 365</span></span>](eval-defender-office-365-overview.md)

<span data-ttu-id="761cf-138">Vuelva a la introducción a [Evaluate Microsoft Defender for Office 365](eval-defender-office-365-overview.md)</span><span class="sxs-lookup"><span data-stu-id="761cf-138">Return to the overview for [Evaluate Microsoft Defender for Office 365](eval-defender-office-365-overview.md)</span></span>

<span data-ttu-id="761cf-139">Vuelva a la introducción a [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)</span><span class="sxs-lookup"><span data-stu-id="761cf-139">Return to the overview for [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)</span></span>