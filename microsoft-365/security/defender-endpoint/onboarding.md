---
title: Incorporación al servicio microsoft defender para puntos de conexión
description: Obtenga información sobre cómo incorporar puntos de conexión a Microsoft Defender para el servicio de punto de conexión
keywords: ''
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-endpointprotect
- m365solution-scenario
ms.topic: article
ms.technology: mde
ms.openlocfilehash: cc538c887397d5bbea78f63c8a8acd318ec7fe9f
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689538"
---
# <a name="onboard-to-the-microsoft-defender-for-endpoint-service"></a><span data-ttu-id="d8a61-103">Incorporación al servicio microsoft defender para puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="d8a61-103">Onboard to the Microsoft Defender for Endpoint service</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d8a61-104">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="d8a61-104">**Applies to:**</span></span>
- [<span data-ttu-id="d8a61-105">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="d8a61-105">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="d8a61-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d8a61-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="d8a61-107">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="d8a61-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="d8a61-108">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="d8a61-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="d8a61-109">Obtenga información sobre las distintas fases de implementación de Microsoft Defender para endpoint y cómo configurar las funcionalidades de la solución.</span><span class="sxs-lookup"><span data-stu-id="d8a61-109">Learn about the various phases of deploying Microsoft Defender for Endpoint and how to configure the capabilities within the solution.</span></span> 

<span data-ttu-id="d8a61-110">La implementación de Defender for Endpoint es un proceso de tres fases:</span><span class="sxs-lookup"><span data-stu-id="d8a61-110">Deploying Defender for Endpoint is a three-phase process:</span></span>

| <span data-ttu-id="d8a61-111">[![fase de implementación: preparar](images/phase-diagrams/prepare.png)](prepare-deployment.md)</span><span class="sxs-lookup"><span data-stu-id="d8a61-111">[![deployment phase - prepare](images/phase-diagrams/prepare.png)](prepare-deployment.md)</span></span><br>[<span data-ttu-id="d8a61-112">Fase 1: Preparación</span><span class="sxs-lookup"><span data-stu-id="d8a61-112">Phase 1: Prepare</span></span>](prepare-deployment.md) | <span data-ttu-id="d8a61-113">[![fase de implementación: configuración](images/phase-diagrams/setup.png)](production-deployment.md)</span><span class="sxs-lookup"><span data-stu-id="d8a61-113">[![deployment phase - setup](images/phase-diagrams/setup.png)](production-deployment.md)</span></span><br>[<span data-ttu-id="d8a61-114">Fase 2: Configuración</span><span class="sxs-lookup"><span data-stu-id="d8a61-114">Phase 2: Setup</span></span>](production-deployment.md) | ![fase de implementación: incorporación](images/phase-diagrams/onboard.png)<br><span data-ttu-id="d8a61-116">Fase 3: Incorporación</span><span class="sxs-lookup"><span data-stu-id="d8a61-116">Phase 3: Onboard</span></span> |
| ----- | ----- | ----- |
| | |<span data-ttu-id="d8a61-117">*¡Estás aquí!*</span><span class="sxs-lookup"><span data-stu-id="d8a61-117">*You are here!*</span></span>|

<span data-ttu-id="d8a61-118">Actualmente se encuentra en la fase de incorporación.</span><span class="sxs-lookup"><span data-stu-id="d8a61-118">You are currently in the onboarding phase.</span></span>

<span data-ttu-id="d8a61-119">Estos son los pasos que debe seguir para implementar Defender for Endpoint:</span><span class="sxs-lookup"><span data-stu-id="d8a61-119">These are the steps you need to take to deploy Defender for Endpoint:</span></span>

- <span data-ttu-id="d8a61-120">Paso 1: Incorporar puntos de conexión al servicio</span><span class="sxs-lookup"><span data-stu-id="d8a61-120">Step 1: Onboard endpoints to the service</span></span> 
- <span data-ttu-id="d8a61-121">Paso 2: Configurar capacidades</span><span class="sxs-lookup"><span data-stu-id="d8a61-121">Step 2: Configure capabilities</span></span> 

## <a name="step-1-onboard-endpoints-using-any-of-the-supported-management-tools"></a><span data-ttu-id="d8a61-122">Paso 1: Incorporar puntos de conexión con cualquiera de las herramientas de administración admitidas</span><span class="sxs-lookup"><span data-stu-id="d8a61-122">Step 1: Onboard endpoints using any of the supported management tools</span></span>
<span data-ttu-id="d8a61-123">En [el tema Plan deployment](deployment-strategy.md) se describen los pasos generales que debe seguir para implementar Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="d8a61-123">The [Plan deployment](deployment-strategy.md) topic outlines the general steps you need to take to deploy Defender for Endpoint.</span></span>  


<span data-ttu-id="d8a61-124">Vea este vídeo para obtener una introducción rápida al proceso de incorporación y obtenga información sobre las herramientas y métodos disponibles.</span><span class="sxs-lookup"><span data-stu-id="d8a61-124">Watch this video for a quick overview of the onboarding process and learn about the available tools and methods.</span></span>
<br />
<br />

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4bGqr]



<span data-ttu-id="d8a61-125">Después de identificar la arquitectura, deberá decidir qué método de implementación usar.</span><span class="sxs-lookup"><span data-stu-id="d8a61-125">After identifying your architecture, you'll need to decide which deployment method to use.</span></span> <span data-ttu-id="d8a61-126">La herramienta de implementación que elija influye en la forma en que incorpora puntos de conexión al servicio.</span><span class="sxs-lookup"><span data-stu-id="d8a61-126">The deployment tool you choose influences how you onboard endpoints to the service.</span></span> 

### <a name="onboarding-tool-options"></a><span data-ttu-id="d8a61-127">Opciones de la herramienta de incorporación</span><span class="sxs-lookup"><span data-stu-id="d8a61-127">Onboarding tool options</span></span>

<span data-ttu-id="d8a61-128">En la tabla siguiente se enumeran las herramientas disponibles en función del extremo que necesita incorporar.</span><span class="sxs-lookup"><span data-stu-id="d8a61-128">The following table lists the available tools based on the endpoint that you need to onboard.</span></span>

| <span data-ttu-id="d8a61-129">Extremo</span><span class="sxs-lookup"><span data-stu-id="d8a61-129">Endpoint</span></span>     | <span data-ttu-id="d8a61-130">Opciones de herramientas</span><span class="sxs-lookup"><span data-stu-id="d8a61-130">Tool options</span></span>                       |
|--------------|------------------------------------------|
| <span data-ttu-id="d8a61-131">**Windows**</span><span class="sxs-lookup"><span data-stu-id="d8a61-131">**Windows**</span></span>  |  [<span data-ttu-id="d8a61-132">Script local (hasta 10 dispositivos)</span><span class="sxs-lookup"><span data-stu-id="d8a61-132">Local script (up to 10 devices)</span></span>](configure-endpoints-script.md) <br>  [<span data-ttu-id="d8a61-133">Directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="d8a61-133">Group Policy</span></span>](configure-endpoints-gp.md) <br>  [<span data-ttu-id="d8a61-134">Microsoft Endpoint Manager/Mobile Device Manager</span><span class="sxs-lookup"><span data-stu-id="d8a61-134">Microsoft Endpoint Manager/ Mobile Device Manager</span></span>](configure-endpoints-mdm.md) <br> [<span data-ttu-id="d8a61-135">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="d8a61-135">Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md) <br> [<span data-ttu-id="d8a61-136">Scripts VDI</span><span class="sxs-lookup"><span data-stu-id="d8a61-136">VDI scripts</span></span>](configure-endpoints-vdi.md) <br> [<span data-ttu-id="d8a61-137">Azure Security Center</span><span class="sxs-lookup"><span data-stu-id="d8a61-137">Azure Security Center</span></span>](configure-server-endpoints.md#integration-with-azure-security-center) |
| <span data-ttu-id="d8a61-138">**macOS**</span><span class="sxs-lookup"><span data-stu-id="d8a61-138">**macOS**</span></span>    | [<span data-ttu-id="d8a61-139">Scripts locales</span><span class="sxs-lookup"><span data-stu-id="d8a61-139">Local scripts</span></span>](mac-install-manually.md) <br> [<span data-ttu-id="d8a61-140">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="d8a61-140">Microsoft Endpoint Manager</span></span>](mac-install-with-intune.md) <br> [<span data-ttu-id="d8a61-141">JAMF Pro</span><span class="sxs-lookup"><span data-stu-id="d8a61-141">JAMF Pro</span></span>](mac-install-with-jamf.md) <br> [<span data-ttu-id="d8a61-142">Administración de dispositivos móviles</span><span class="sxs-lookup"><span data-stu-id="d8a61-142">Mobile Device Management</span></span>](mac-install-with-other-mdm.md) |
| <span data-ttu-id="d8a61-143">**Servidor Linux**</span><span class="sxs-lookup"><span data-stu-id="d8a61-143">**Linux Server**</span></span> | [<span data-ttu-id="d8a61-144">Script local</span><span class="sxs-lookup"><span data-stu-id="d8a61-144">Local script</span></span>](linux-install-manually.md) <br> [<span data-ttu-id="d8a61-145">Puppet</span><span class="sxs-lookup"><span data-stu-id="d8a61-145">Puppet</span></span>](linux-install-with-puppet.md) <br> [<span data-ttu-id="d8a61-146">Ansible</span><span class="sxs-lookup"><span data-stu-id="d8a61-146">Ansible</span></span>](linux-install-with-ansible.md)|
| <span data-ttu-id="d8a61-147">**iOS**</span><span class="sxs-lookup"><span data-stu-id="d8a61-147">**iOS**</span></span>      | [<span data-ttu-id="d8a61-148">Basado en aplicaciones</span><span class="sxs-lookup"><span data-stu-id="d8a61-148">App-based</span></span>](ios-install.md)                                |
| <span data-ttu-id="d8a61-149">**Android**</span><span class="sxs-lookup"><span data-stu-id="d8a61-149">**Android**</span></span>  | [<span data-ttu-id="d8a61-150">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="d8a61-150">Microsoft Endpoint Manager</span></span>](android-intune.md)               | 


## <a name="step-2-configure-capabilities"></a><span data-ttu-id="d8a61-151">Paso 2: Configurar capacidades</span><span class="sxs-lookup"><span data-stu-id="d8a61-151">Step 2: Configure capabilities</span></span>
<span data-ttu-id="d8a61-152">Después de incorporar los puntos de conexión, configurarás las distintas funcionalidades, como la detección y respuesta de puntos de conexión, la protección de próxima generación y la reducción de superficie de ataque.</span><span class="sxs-lookup"><span data-stu-id="d8a61-152">After onboarding the endpoints, you'll then configure the various capabilities such as endpoint detection and response, next-generation protection, and attack surface reduction.</span></span> 


## <a name="example-deployments"></a><span data-ttu-id="d8a61-153">Implementaciones de ejemplo</span><span class="sxs-lookup"><span data-stu-id="d8a61-153">Example deployments</span></span>
<span data-ttu-id="d8a61-154">En esta guía de implementación, le guiaremos a través del uso de dos herramientas de implementación para incorporar puntos de conexión y cómo configurar las capacidades.</span><span class="sxs-lookup"><span data-stu-id="d8a61-154">In this deployment guide, we'll guide you through using two deployment tools to onboard endpoints and how to configure capabilities.</span></span>

<span data-ttu-id="d8a61-155">Las herramientas de las implementaciones de ejemplo son:</span><span class="sxs-lookup"><span data-stu-id="d8a61-155">The tools in the example deployments are:</span></span>
- [<span data-ttu-id="d8a61-156">Incorporación mediante Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="d8a61-156">Onboarding using Microsoft Endpoint Configuration Manager</span></span>](onboarding-endpoint-configuration-manager.md)
- [<span data-ttu-id="d8a61-157">Incorporación con Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="d8a61-157">Onboarding using Microsoft Endpoint Manager</span></span>](onboarding-endpoint-manager.md)

<span data-ttu-id="d8a61-158">Con las herramientas de implementación mencionadas anteriormente, se le guiará en la configuración de las siguientes funcionalidades de Defender for Endpoint:</span><span class="sxs-lookup"><span data-stu-id="d8a61-158">Using the mentioned deployment tools above, you'll then be guided in configuring the following Defender for Endpoint capabilities:</span></span>
- <span data-ttu-id="d8a61-159">Detección de extremos y configuración de respuesta</span><span class="sxs-lookup"><span data-stu-id="d8a61-159">Endpoint detection and response configuration</span></span>
- <span data-ttu-id="d8a61-160">Configuración de protección de última generación</span><span class="sxs-lookup"><span data-stu-id="d8a61-160">Next-generation protection configuration</span></span>
- <span data-ttu-id="d8a61-161">Configuración de reducción de superficie de ataque</span><span class="sxs-lookup"><span data-stu-id="d8a61-161">Attack surface reduction configuration</span></span>

## <a name="related-topics"></a><span data-ttu-id="d8a61-162">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="d8a61-162">Related topics</span></span>
- [<span data-ttu-id="d8a61-163">Incorporación mediante Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="d8a61-163">Onboarding using Microsoft Endpoint Configuration Manager</span></span>](onboarding-endpoint-configuration-manager.md)
- [<span data-ttu-id="d8a61-164">Incorporación con Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="d8a61-164">Onboarding using Microsoft Endpoint Manager</span></span>](onboarding-endpoint-manager.md)
- [<span data-ttu-id="d8a61-165">Documentos seguros en Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="d8a61-165">Safe Documents in Microsoft 365 E5</span></span>](../office-365-security/safe-docs.md)
