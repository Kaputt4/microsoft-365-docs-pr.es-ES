---
title: Habilitar el entorno de evaluación para Microsoft Cloud App Security
description: Obtenga información sobre la arquitectura de MCAS dentro de Microsoft Defender Office 365 y comprenda las interacciones entre los Microsoft 365 Defender productos.
keywords: Microsoft 365 Defender prueba, pruebe Microsoft 365 Defender, evalúe Microsoft 365 Defender, laboratorio de evaluación de Microsoft 365 Defender Microsoft 365 Defender, piloto, ciberseguridad, amenazas persistentes avanzadas, seguridad empresarial, dispositivos, identidad, usuarios, datos, aplicaciones, incidentes, investigación y corrección automatizadas, búsqueda avanzada
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 6ada9613f852e085158b7002cbbb9a9928d36d58
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458546"
---
# <a name="enable-the-evaluation-environment-for-microsoft-cloud-app-security"></a><span data-ttu-id="4e4b5-104">Habilitar el entorno de evaluación para Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="4e4b5-104">Enable the evaluation environment for Microsoft Cloud App Security</span></span>


<span data-ttu-id="4e4b5-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="4e4b5-105">**Applies to:**</span></span>

- <span data-ttu-id="4e4b5-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4e4b5-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="4e4b5-107">Este artículo es [el paso 2 de 2](eval-defender-mcas-overview.md) en el proceso de configuración del entorno de evaluación para Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="4e4b5-107">This article is [Step 2 of 2](eval-defender-mcas-overview.md) in the process of setting up the evaluation environment for Microsoft Cloud App Security.</span></span> <span data-ttu-id="4e4b5-108">Para obtener más información acerca de este proceso, vea el [artículo de introducción](eval-defender-mcas-overview.md).</span><span class="sxs-lookup"><span data-stu-id="4e4b5-108">For more information about this process, see the [overview article](eval-defender-mcas-overview.md).</span></span>

<span data-ttu-id="4e4b5-109">En este artículo se explica el proceso de acceso al portal de Cloud App Security y la configuración de la integración necesaria para recopilar datos de tráfico de aplicaciones en la nube.</span><span class="sxs-lookup"><span data-stu-id="4e4b5-109">This article walks you through the process of accessing the Cloud App Security portal and configuring the necessary integration to collect cloud app traffic data.</span></span>

<span data-ttu-id="4e4b5-110">Para descubrir las aplicaciones en la nube que se usan en el entorno, puede realizar una o ambas de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="4e4b5-110">To discover cloud apps used in your environment, you can do one or both of the following:</span></span>

- <span data-ttu-id="4e4b5-111">Para empezar a trabajar rápidamente con Cloud Discovery, integre con Microsoft Defender para Endpoint.</span><span class="sxs-lookup"><span data-stu-id="4e4b5-111">Get up and running quickly with Cloud Discovery by integrating with Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="4e4b5-112">Esta integración nativa le permite empezar inmediatamente a recopilar datos sobre el tráfico en la nube en Windows 10 dispositivos, en y fuera de la red.</span><span class="sxs-lookup"><span data-stu-id="4e4b5-112">This native integration enables you to immediately start collecting data on cloud traffic across your Windows 10 devices, on and off your network.</span></span>
- <span data-ttu-id="4e4b5-113">Para descubrir todas las aplicaciones en la nube a las que acceden todos los dispositivos conectados a la red, implemente el recopilador de registros Cloud App Security en los firewalls y otros servidores proxy.</span><span class="sxs-lookup"><span data-stu-id="4e4b5-113">To discover all cloud apps accessed by all devices connected to your network, deploy the Cloud App Security log collector on your firewalls and other proxies.</span></span> <span data-ttu-id="4e4b5-114">Esto recopila datos de los puntos de conexión y los envía a Cloud App Security para su análisis.</span><span class="sxs-lookup"><span data-stu-id="4e4b5-114">This collects data from your endpoints and sends it to Cloud App Security for analysis.</span></span> <span data-ttu-id="4e4b5-115">Cloud App Security se integra de forma nativa con algunos servidores proxy de terceros para obtener aún más funcionalidades.</span><span class="sxs-lookup"><span data-stu-id="4e4b5-115">Cloud App Security natively integrates with some third-party proxies for even more capabilities.</span></span>

<span data-ttu-id="4e4b5-116">En este artículo se incluyen instrucciones para ambos métodos.</span><span class="sxs-lookup"><span data-stu-id="4e4b5-116">This article includes guidance for both methods.</span></span>

<span data-ttu-id="4e4b5-117">Siga estos pasos para configurar Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="4e4b5-117">Use the following steps to set up Microsoft Cloud App Security.</span></span>

![Pasos para habilitar Microsoft Microsoft Cloud App Security en el entorno de evaluación de Microsoft Defender](../../media/defender/m365-defender-mcas-eval-enable-steps.png)

- [<span data-ttu-id="4e4b5-119">Paso 1. Conectar al portal de Cloud App Security web</span><span class="sxs-lookup"><span data-stu-id="4e4b5-119">Step 1. Connect to the Cloud App Security portal</span></span>](#step-1-connect-to-the-cloud-app-security-portal)
- [<span data-ttu-id="4e4b5-120">Paso 2. Integrar con Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="4e4b5-120">Step 2. Integrate with Microsoft Defender for Endpoint</span></span>](#step-2-integrate-with-microsoft-defender-for-endpoint)
- [<span data-ttu-id="4e4b5-121">Paso 3. Implementar el Cloud App Security de registro en los firewalls y otros servidores proxy</span><span class="sxs-lookup"><span data-stu-id="4e4b5-121">Step 3. Deploy the Cloud App Security log collector on your firewalls and other proxies</span></span>](#step-3-deploy-the-cloud-app-security-log-collector-on-your-firewalls-and-other-proxies)
- [<span data-ttu-id="4e4b5-122">Paso 4. Ver el panel de detección en la nube para ver qué aplicaciones se usan en su organización</span><span class="sxs-lookup"><span data-stu-id="4e4b5-122">Step 4. View the Cloud Discovery dashboard to see what apps are being used in your organization</span></span>](#step-4-view-the-cloud-discovery-dashboard-to-see-what-apps-are-being-used-in-your-organization)

## <a name="step-1-connect-to-the-cloud-app-security-portal"></a><span data-ttu-id="4e4b5-123">Paso 1.</span><span class="sxs-lookup"><span data-stu-id="4e4b5-123">Step 1.</span></span> <span data-ttu-id="4e4b5-124">Conectar al portal de Cloud App Security web</span><span class="sxs-lookup"><span data-stu-id="4e4b5-124">Connect to the Cloud App Security portal</span></span>

<span data-ttu-id="4e4b5-125">Para comprobar las licencias y conectarse al portal de Cloud App Security, vea [Inicio rápido: Introducción a Microsoft Cloud App Security](/cloud-app-security/getting-started-with-cloud-app-security).</span><span class="sxs-lookup"><span data-stu-id="4e4b5-125">To verify licensing and to connect to the Cloud App Security portal, see [Quickstart: Get started with Microsoft Cloud App Security](/cloud-app-security/getting-started-with-cloud-app-security).</span></span> 

<span data-ttu-id="4e4b5-126">Si no puede conectarse inmediatamente al portal, es posible que deba agregar la dirección IP a la lista de permitidos del firewall.</span><span class="sxs-lookup"><span data-stu-id="4e4b5-126">If you're not immediately able to connect to the portal, you might need to add the IP address to the allow list of your firewall.</span></span> <span data-ttu-id="4e4b5-127">Consulte [Configuración básica para Cloud App Security](/cloud-app-security/general-setup).</span><span class="sxs-lookup"><span data-stu-id="4e4b5-127">See [Basic setup for Cloud App Security](/cloud-app-security/general-setup).</span></span>

<span data-ttu-id="4e4b5-128">Si aún tiene problemas, revise [Requisitos de red](/cloud-app-security/network-requirements).</span><span class="sxs-lookup"><span data-stu-id="4e4b5-128">If you're still having trouble, review [Network requirements](/cloud-app-security/network-requirements).</span></span>

## <a name="step-2-integrate-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="4e4b5-129">Paso 2.</span><span class="sxs-lookup"><span data-stu-id="4e4b5-129">Step 2.</span></span> <span data-ttu-id="4e4b5-130">Integrar con Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="4e4b5-130">Integrate with Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="4e4b5-131">Microsoft Cloud App Security se integra con Microsoft Defender para Endpoint de forma nativa.</span><span class="sxs-lookup"><span data-stu-id="4e4b5-131">Microsoft Cloud App Security integrates with Microsoft Defender for Endpoint natively.</span></span> <span data-ttu-id="4e4b5-132">La integración simplifica el lanzamiento de Cloud Discovery, amplía las capacidades de Cloud Discovery más allá de la red corporativa y habilita la investigación basada en dispositivos.</span><span class="sxs-lookup"><span data-stu-id="4e4b5-132">The integration simplifies roll out of Cloud Discovery, extends Cloud Discovery capabilities beyond your corporate network, and enables device-based investigation.</span></span> <span data-ttu-id="4e4b5-133">Esta integración muestra los servicios y aplicaciones en la nube a los que se accede desde dispositivos Windows 10 administración de IT.</span><span class="sxs-lookup"><span data-stu-id="4e4b5-133">This integration reveals cloud apps and services being accessed from IT-managed Windows 10 devices.</span></span> 

<span data-ttu-id="4e4b5-134">Si ya has configurado Microsoft Defender para Endpoint, configurar la integración con Cloud App Security es un botón de alternancia en Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="4e4b5-134">If you've already set up Microsoft Defender for Endpoint, configuring integration with Cloud App Security is a toggle in Microsoft 365 Defender.</span></span> <span data-ttu-id="4e4b5-135">Una vez activada la integración, puede volver al portal de Cloud App Security y ver datos enriquecidos en el Panel de detección de nube.</span><span class="sxs-lookup"><span data-stu-id="4e4b5-135">After integration is turned on, you can return to the Cloud App Security portal and view rich data in the Cloud Discovery Dashboard.</span></span>

<span data-ttu-id="4e4b5-136">Para realizar estas tareas, vea [Microsoft Defender for Endpoint integration with Microsoft Cloud App Security](/cloud-app-security/mde-integration).</span><span class="sxs-lookup"><span data-stu-id="4e4b5-136">To accomplish these tasks, see [Microsoft Defender for Endpoint integration with Microsoft Cloud App Security](/cloud-app-security/mde-integration).</span></span> 

## <a name="step-3-deploy-the-cloud-app-security-log-collector-on-your-firewalls-and-other-proxies"></a><span data-ttu-id="4e4b5-137">Paso 3.</span><span class="sxs-lookup"><span data-stu-id="4e4b5-137">Step 3.</span></span> <span data-ttu-id="4e4b5-138">Implementar el Cloud App Security de registro en los firewalls y otros servidores proxy</span><span class="sxs-lookup"><span data-stu-id="4e4b5-138">Deploy the Cloud App Security log collector on your firewalls and other proxies</span></span>

<span data-ttu-id="4e4b5-139">Para obtener cobertura en todos los dispositivos conectados a la red, implemente el recopilador de registros de Cloud App Security en los firewalls y otros servidores proxy para recopilar datos de los puntos de conexión y enviarlos a Cloud App Security para su análisis.</span><span class="sxs-lookup"><span data-stu-id="4e4b5-139">For coverage on all devices connected to your network, deploy the Cloud App Security log collector on your firewalls and other proxies to collect data from your endpoints and send it to Cloud App Security for analysis.</span></span> 

<span data-ttu-id="4e4b5-140">Si usa una de las siguientes puertas de enlace web seguras (SWG), Cloud App Security una implementación e integración sin problemas:</span><span class="sxs-lookup"><span data-stu-id="4e4b5-140">If you're using one of the following Secure Web Gateways (SWG), Cloud App Security provides seamless deployment and integration:</span></span>
- <span data-ttu-id="4e4b5-141">Zscaler</span><span class="sxs-lookup"><span data-stu-id="4e4b5-141">Zscaler</span></span>
- <span data-ttu-id="4e4b5-142">iboss</span><span class="sxs-lookup"><span data-stu-id="4e4b5-142">iboss</span></span>
- <span data-ttu-id="4e4b5-143">Corrata</span><span class="sxs-lookup"><span data-stu-id="4e4b5-143">Corrata</span></span>
- <span data-ttu-id="4e4b5-144">Menlo Security</span><span class="sxs-lookup"><span data-stu-id="4e4b5-144">Menlo Security</span></span>

<span data-ttu-id="4e4b5-145">Para obtener más información sobre la integración con estos dispositivos de red, consulte [Configurar la detección en la nube.](/cloud-app-security/set-up-cloud-discovery)</span><span class="sxs-lookup"><span data-stu-id="4e4b5-145">For more information on integrating with these network devices, see [Set up Cloud Discovery](/cloud-app-security/set-up-cloud-discovery).</span></span> 
## <a name="step-4-view-the-cloud-discovery-dashboard-to-see-what-apps-are-being-used-in-your-organization"></a><span data-ttu-id="4e4b5-146">Paso 4.</span><span class="sxs-lookup"><span data-stu-id="4e4b5-146">Step 4.</span></span> <span data-ttu-id="4e4b5-147">Ver el panel de detección en la nube para ver qué aplicaciones se usan en su organización</span><span class="sxs-lookup"><span data-stu-id="4e4b5-147">View the Cloud Discovery dashboard to see what apps are being used in your organization</span></span>

<span data-ttu-id="4e4b5-148">El panel de detección de nube está diseñado para ofrecerte más información sobre cómo se usan las aplicaciones en la nube en tu organización.</span><span class="sxs-lookup"><span data-stu-id="4e4b5-148">The Cloud Discovery dashboard is designed to give you more insight into how cloud apps are being used in your organization.</span></span> <span data-ttu-id="4e4b5-149">Proporciona una visión general general de los tipos de aplicaciones que se usan, las alertas abiertas y los niveles de riesgo de las aplicaciones de la organización.</span><span class="sxs-lookup"><span data-stu-id="4e4b5-149">It provides an at-a-glance overview of what kinds of apps are being used, your open alerts, and the risk levels of apps in your organization.</span></span> 

<span data-ttu-id="4e4b5-150">Para empezar a usar el panel de detección en la nube, consulta [Trabajar con aplicaciones detectadas.](/cloud-app-security/discovered-apps)</span><span class="sxs-lookup"><span data-stu-id="4e4b5-150">To get started using the Cloud Discovery dashboard, see [Working with discovered apps](/cloud-app-security/discovered-apps).</span></span>

## <a name="next-steps"></a><span data-ttu-id="4e4b5-151">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="4e4b5-151">Next steps</span></span>

<span data-ttu-id="4e4b5-152">Paso 3 de 3: [Piloto Microsoft Cloud App Security](eval-defender-mcas-pilot.md)</span><span class="sxs-lookup"><span data-stu-id="4e4b5-152">Step 3 of 3: [Pilot Microsoft Cloud App Security](eval-defender-mcas-pilot.md)</span></span>

<span data-ttu-id="4e4b5-153">Vuelva a la introducción a [Evaluate Microsoft Cloud App Security](eval-defender-mcas-overview.md)</span><span class="sxs-lookup"><span data-stu-id="4e4b5-153">Return to the overview for [Evaluate Microsoft Cloud App Security](eval-defender-mcas-overview.md)</span></span>

<span data-ttu-id="4e4b5-154">Vuelva a la introducción a [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)</span><span class="sxs-lookup"><span data-stu-id="4e4b5-154">Return to the overview for [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)</span></span>