---
title: Revisar los requisitos y conceptos clave de la arquitectura de puntos de conexión de Microsoft Defender
description: El diagrama técnico de Microsoft Defender para endpoint en Microsoft 365 Defender le ayudará a comprender la identidad en Microsoft 365 antes de crear el entorno piloto o el laboratorio de prueba.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: v-jweston
author: jweston-1
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
ms.openlocfilehash: 4df1ac2ca5fdfaa88ec2d08c85112f52da26b873
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458603"
---
# <a name="review-microsoft-defender-for-endpoint-architecture-requirements-and-key-concepts"></a><span data-ttu-id="dee56-103">Revisar los requisitos y conceptos clave de la arquitectura de puntos de conexión de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="dee56-103">Review Microsoft Defender for Endpoint architecture requirements and key concepts</span></span>

<span data-ttu-id="dee56-104">**Se aplica a:** Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="dee56-104">**Applies to:** Microsoft 365 Defender</span></span>

<span data-ttu-id="dee56-105">Este artículo le guiará en el proceso de configuración de la evaluación del entorno de Microsoft Defender para endpoints.</span><span class="sxs-lookup"><span data-stu-id="dee56-105">This article will guide you in the process of setting up the evaluation for Microsoft Defender for Endpoint environment.</span></span>

<span data-ttu-id="dee56-106">Para obtener más información acerca de este proceso, vea el [artículo de introducción](eval-defender-endpoint-overview.md).</span><span class="sxs-lookup"><span data-stu-id="dee56-106">For more information about this process, see the [overview article](eval-defender-endpoint-overview.md).</span></span>

<span data-ttu-id="dee56-107">Antes de habilitar Microsoft Defender para endpoint, asegúrese de comprender la arquitectura y de cumplir los requisitos.</span><span class="sxs-lookup"><span data-stu-id="dee56-107">Before enabling Microsoft Defender for Endpoint, be sure you understand the architecture and can meet the requirements.</span></span>

## <a name="understand-the-architecture"></a><span data-ttu-id="dee56-108">Información sobre la arquitectura</span><span class="sxs-lookup"><span data-stu-id="dee56-108">Understand the architecture</span></span>

<span data-ttu-id="dee56-109">En el siguiente diagrama se muestra Microsoft Defender para la arquitectura y las integraciones de puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="dee56-109">The following diagram illustrates Microsoft Defender for Endpoint architecture and integrations.</span></span> 

![Pasos para agregar Microsoft Defender para Office al entorno de evaluación de Defender](../../media/defender/m365-defender-endpoint-architecture.png)

<span data-ttu-id="dee56-111">En la tabla siguiente se describe la ilustración.</span><span class="sxs-lookup"><span data-stu-id="dee56-111">The following table describes the illustration.</span></span>

<span data-ttu-id="dee56-112">Llamada</span><span class="sxs-lookup"><span data-stu-id="dee56-112">Call-out</span></span> | <span data-ttu-id="dee56-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="dee56-113">Description</span></span>
:---|:---|
<span data-ttu-id="dee56-114">1</span><span class="sxs-lookup"><span data-stu-id="dee56-114">1</span></span> | <span data-ttu-id="dee56-115">Los dispositivos se abordo a través de una de las herramientas de administración admitidas.</span><span class="sxs-lookup"><span data-stu-id="dee56-115">Devices are on-boarded through one of the supported management tools.</span></span> 
<span data-ttu-id="dee56-116">2</span><span class="sxs-lookup"><span data-stu-id="dee56-116">2</span></span> | <span data-ttu-id="dee56-117">Los dispositivos abordo proporcionan y responden a Microsoft Defender para los datos de señal de punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="dee56-117">On-boarded devices provide and respond to Microsoft Defender for Endpoint signal data.</span></span>
<span data-ttu-id="dee56-118">3</span><span class="sxs-lookup"><span data-stu-id="dee56-118">3</span></span> | <span data-ttu-id="dee56-119">Los dispositivos administrados se unen o se inscriben en Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="dee56-119">Managed devices are joined and/or enrolled in Azure Active Directory.</span></span>
<span data-ttu-id="dee56-120">4 </span><span class="sxs-lookup"><span data-stu-id="dee56-120">4</span></span> | <span data-ttu-id="dee56-121">Los dispositivos de Windows 10 unidos al dominio se sincronizan con Azure Active Directory mediante Azure Active Directory Conectar.</span><span class="sxs-lookup"><span data-stu-id="dee56-121">Domain-joined Windows 10 devices are synchronized to Azure Active Directory using Azure Active Directory Connect.</span></span>
<span data-ttu-id="dee56-122">5 </span><span class="sxs-lookup"><span data-stu-id="dee56-122">5</span></span> | <span data-ttu-id="dee56-123">Las alertas, investigaciones y respuestas de Microsoft Defender para puntos de conexión se administran en Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="dee56-123">Microsoft Defender for Endpoint alerts, investigations, and responses are managed in Microsoft 365 Defender.</span></span>

## <a name="understand-key-concepts"></a><span data-ttu-id="dee56-124">Comprender conceptos clave</span><span class="sxs-lookup"><span data-stu-id="dee56-124">Understand key concepts</span></span>

<span data-ttu-id="dee56-125">En la siguiente tabla se identificaron conceptos clave que son importantes para comprender al evaluar, configurar e implementar Microsoft Defender para endpoint:</span><span class="sxs-lookup"><span data-stu-id="dee56-125">The following table identified key concepts that are important to understand when evaluating, configuring, and deploying Microsoft Defender for Endpoint:</span></span> 

<span data-ttu-id="dee56-126">Concepto</span><span class="sxs-lookup"><span data-stu-id="dee56-126">Concept</span></span> | <span data-ttu-id="dee56-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="dee56-127">Description</span></span> | <span data-ttu-id="dee56-128">Más información</span><span class="sxs-lookup"><span data-stu-id="dee56-128">More information</span></span>
:---|:---|:---|
<span data-ttu-id="dee56-129">Portal de administración</span><span class="sxs-lookup"><span data-stu-id="dee56-129">Administration Portal</span></span> | <span data-ttu-id="dee56-130">Microsoft 365 Defender para supervisar y ayudar a responder a alertas de posibles infracciones de datos o actividad de amenazas persistentes avanzada.</span><span class="sxs-lookup"><span data-stu-id="dee56-130">Microsoft 365 Defender portal to monitor and assist in responding to alerts of potential advanced persistent threat activity or data breaches.</span></span> | [<span data-ttu-id="dee56-131">Introducción al portal de Microsoft Defender para endpoints</span><span class="sxs-lookup"><span data-stu-id="dee56-131">Microsoft Defender for Endpoint portal overview</span></span>](/defender-endpoint/portal-overview)
<span data-ttu-id="dee56-132">Reducción de superficie de ataque</span><span class="sxs-lookup"><span data-stu-id="dee56-132">Attack Surface Reduction</span></span> | <span data-ttu-id="dee56-133">Ayuda a reducir las superficies de ataque minimizando los lugares donde tu organización es vulnerable a ciberamenazas y ataques.</span><span class="sxs-lookup"><span data-stu-id="dee56-133">Help reduce your attack surfaces by minimizing the places where your organization is vulnerable to cyberthreats and attacks.</span></span> | [<span data-ttu-id="dee56-134">Introducción a la reducción de la superficie expuesta a ataques</span><span class="sxs-lookup"><span data-stu-id="dee56-134">Overview of attack surface reduction</span></span>](/defender-endpoint/overview-attack-surface-reduction)
<span data-ttu-id="dee56-135">Detección y respuesta de extremos</span><span class="sxs-lookup"><span data-stu-id="dee56-135">Endpoint Detection and Response</span></span> | <span data-ttu-id="dee56-136">Las capacidades de detección y respuesta de puntos de conexión proporcionan detecciones avanzadas de ataques que son casi en tiempo real y que pueden actuar.</span><span class="sxs-lookup"><span data-stu-id="dee56-136">Endpoint detection and response capabilities provide advanced attack detections that are near real-time and actionable.</span></span> | [<span data-ttu-id="dee56-137">Información general sobre detección y respuesta de puntos de conexión funcionalidades</span><span class="sxs-lookup"><span data-stu-id="dee56-137">Overview of endpoint detection and response capabilities</span></span>](/defender-endpoint/overview-endpoint-detection-response)
<span data-ttu-id="dee56-138">Bloqueo y contención del comportamiento</span><span class="sxs-lookup"><span data-stu-id="dee56-138">Behavioral Blocking and Containment</span></span> | <span data-ttu-id="dee56-139">Las capacidades de bloqueo y contención del comportamiento pueden ayudar a identificar y detener las amenazas, en función de sus comportamientos y de los árboles de proceso incluso cuando la amenaza ha comenzado a ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="dee56-139">Behavioral blocking and containment capabilities can help identify and stop threats, based on their behaviors and process trees even when the threat has started execution.</span></span> | [<span data-ttu-id="dee56-140">Contención y bloqueo de comportamiento</span><span class="sxs-lookup"><span data-stu-id="dee56-140">Behavioral blocking and containment</span></span>](/defender-endpoint/behavioral-blocking-containment)
<span data-ttu-id="dee56-141">Investigación y respuesta automatizadas</span><span class="sxs-lookup"><span data-stu-id="dee56-141">Automated Investigation and Response</span></span> | <span data-ttu-id="dee56-142">La investigación automatizada usa varios algoritmos de inspección basados en procesos que usan los analistas de seguridad y diseñados para examinar alertas y tomar medidas inmediatas para resolver infracciones.</span><span class="sxs-lookup"><span data-stu-id="dee56-142">Automated investigation uses various inspection algorithms based on processes that are used by security analysts and designed to examine alerts and take immediate action to resolve breaches.</span></span> | [<span data-ttu-id="dee56-143">Usar investigaciones automatizadas para investigar y corregir amenazas</span><span class="sxs-lookup"><span data-stu-id="dee56-143">Use automated investigations to investigate and remediate threats</span></span>](/defender-endpoint/automated-investigations)
<span data-ttu-id="dee56-144">Búsqueda avanzada de amenazas</span><span class="sxs-lookup"><span data-stu-id="dee56-144">Advanced Hunting</span></span> | <span data-ttu-id="dee56-145">La búsqueda avanzada es una herramienta de búsqueda de amenazas basada en consultas que le permite explorar hasta 30 días de datos sin procesar para que pueda inspeccionar de forma proactiva los eventos de la red para localizar indicadores y entidades de amenazas.</span><span class="sxs-lookup"><span data-stu-id="dee56-145">Advanced hunting is a query-based threat-hunting tool that lets you explore up to 30 days of raw data so that you can proactively inspect events in your network to locate threat indicators and entities.</span></span> | [<span data-ttu-id="dee56-146">Información general sobre la búsqueda avanzada</span><span class="sxs-lookup"><span data-stu-id="dee56-146">Overview of advanced hunting</span></span>](/defender-endpoint/advanced-hunting-overview)
<span data-ttu-id="dee56-147">Análisis de amenazas</span><span class="sxs-lookup"><span data-stu-id="dee56-147">Threat Analytics</span></span> | <span data-ttu-id="dee56-148">El análisis de amenazas es un conjunto de informes de investigadores expertos en seguridad de Microsoft que cubren las amenazas más relevantes.</span><span class="sxs-lookup"><span data-stu-id="dee56-148">Threat analytics is a set of reports from expert Microsoft security researchers covering the most relevant threats.</span></span> | [<span data-ttu-id="dee56-149">Seguir las amenazas emergentes y responder a ellas</span><span class="sxs-lookup"><span data-stu-id="dee56-149">Track and respond to emerging threats</span></span>](/defender-endpoint/threat-analytics)


<span data-ttu-id="dee56-150">Para obtener información más detallada acerca de las funcionalidades incluidas con Microsoft Defender para endpoint, vea [What is Microsoft Defender for Endpoint](/defender-endpoint/microsoft-defender-endpoint).</span><span class="sxs-lookup"><span data-stu-id="dee56-150">For more detailed information about the capabilities included with Microsoft Defender for Endpoint, see [What is Microsoft Defender for Endpoint](/defender-endpoint/microsoft-defender-endpoint).</span></span>

## <a name="siem-integration"></a><span data-ttu-id="dee56-151">Integración de SIEM</span><span class="sxs-lookup"><span data-stu-id="dee56-151">SIEM integration</span></span>

<span data-ttu-id="dee56-152">Puede integrar Microsoft Defender para Endpoint con Azure Sentinel para analizar más exhaustivamente los eventos de seguridad en toda la organización y crear libros de juegos para obtener una respuesta eficaz e inmediata.</span><span class="sxs-lookup"><span data-stu-id="dee56-152">You can integrate Microsoft Defender for Endpoint with Azure Sentinel to more comprehensively analyze security events across your organization and build playbooks for effective and immediate response.</span></span> 

<span data-ttu-id="dee56-153">Microsoft Defender para endpoint también se puede integrar en otras soluciones de administración de eventos y de información de seguridad (SIEM).</span><span class="sxs-lookup"><span data-stu-id="dee56-153">Microsoft Defender for Endpoint can also be integrated into other Security Information and Event Management (SIEM) solutions.</span></span> <span data-ttu-id="dee56-154">Para obtener más información, vea [Enable SIEM integration in Microsoft Defender for Endpoint](/defender-endpoint/enable-siem-integration).</span><span class="sxs-lookup"><span data-stu-id="dee56-154">For more information, see [Enable SIEM integration in Microsoft Defender for Endpoint](/defender-endpoint/enable-siem-integration).</span></span>


## <a name="next-steps"></a><span data-ttu-id="dee56-155">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="dee56-155">Next steps</span></span>
[<span data-ttu-id="dee56-156">Habilitar la evaluación</span><span class="sxs-lookup"><span data-stu-id="dee56-156">Enable the evaluation</span></span>](eval-defender-endpoint-enable-eval.md)

<span data-ttu-id="dee56-157">Vuelva a la introducción a [Evaluate Microsoft Defender for Endpoint](eval-defender-endpoint-overview.md)</span><span class="sxs-lookup"><span data-stu-id="dee56-157">Return to the overview for [Evaluate Microsoft Defender for Endpoint](eval-defender-endpoint-overview.md)</span></span>

<span data-ttu-id="dee56-158">Vuelva a la introducción a [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)</span><span class="sxs-lookup"><span data-stu-id="dee56-158">Return to the overview for [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)</span></span>