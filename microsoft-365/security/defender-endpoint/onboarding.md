---
title: Incorporación al servicio microsoft defender para puntos de conexión
description: Obtenga información sobre cómo incorporar puntos de conexión a Microsoft Defender para el servicio de punto de conexión
keywords: microsoft Defender para el punto de conexión, la incorporación, la implementación
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
ms.openlocfilehash: f63b4f81f454fec60a26c7cb063d66bed4a2bead
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933546"
---
# <a name="onboard-to-the-microsoft-defender-for-endpoint-service"></a><span data-ttu-id="cc4ef-104">Incorporación al servicio microsoft defender para puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="cc4ef-104">Onboard to the Microsoft Defender for Endpoint service</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="cc4ef-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="cc4ef-105">**Applies to:**</span></span>
- [<span data-ttu-id="cc4ef-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="cc4ef-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="cc4ef-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cc4ef-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="cc4ef-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="cc4ef-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="cc4ef-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="cc4ef-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="cc4ef-110">Obtenga información sobre las distintas fases de implementación de Microsoft Defender para endpoint y cómo configurar las funcionalidades de la solución.</span><span class="sxs-lookup"><span data-stu-id="cc4ef-110">Learn about the various phases of deploying Microsoft Defender for Endpoint and how to configure the capabilities within the solution.</span></span> 

<span data-ttu-id="cc4ef-111">La implementación de Defender for Endpoint es un proceso de tres fases:</span><span class="sxs-lookup"><span data-stu-id="cc4ef-111">Deploying Defender for Endpoint is a three-phase process:</span></span>

| <span data-ttu-id="cc4ef-112">[![fase de implementación: preparar](images/phase-diagrams/prepare.png)](prepare-deployment.md)</span><span class="sxs-lookup"><span data-stu-id="cc4ef-112">[![deployment phase - prepare](images/phase-diagrams/prepare.png)](prepare-deployment.md)</span></span><br>[<span data-ttu-id="cc4ef-113">Fase 1: Preparación</span><span class="sxs-lookup"><span data-stu-id="cc4ef-113">Phase 1: Prepare</span></span>](prepare-deployment.md) | <span data-ttu-id="cc4ef-114">[![fase de implementación: configuración](images/phase-diagrams/setup.png)](production-deployment.md)</span><span class="sxs-lookup"><span data-stu-id="cc4ef-114">[![deployment phase - setup](images/phase-diagrams/setup.png)](production-deployment.md)</span></span><br>[<span data-ttu-id="cc4ef-115">Fase 2: Configuración</span><span class="sxs-lookup"><span data-stu-id="cc4ef-115">Phase 2: Setup</span></span>](production-deployment.md) | ![fase de implementación: incorporación](images/phase-diagrams/onboard.png)<br><span data-ttu-id="cc4ef-117">Fase 3: Incorporación</span><span class="sxs-lookup"><span data-stu-id="cc4ef-117">Phase 3: Onboard</span></span> |
| ----- | ----- | ----- |
| | |<span data-ttu-id="cc4ef-118">*¡Estás aquí!*</span><span class="sxs-lookup"><span data-stu-id="cc4ef-118">*You are here!*</span></span>|

<span data-ttu-id="cc4ef-119">Actualmente se encuentra en la fase de incorporación.</span><span class="sxs-lookup"><span data-stu-id="cc4ef-119">You are currently in the onboarding phase.</span></span>

<span data-ttu-id="cc4ef-120">Estos son los pasos que debe seguir para implementar Defender for Endpoint:</span><span class="sxs-lookup"><span data-stu-id="cc4ef-120">These are the steps you need to take to deploy Defender for Endpoint:</span></span>

- <span data-ttu-id="cc4ef-121">Paso 1: Incorporar puntos de conexión al servicio</span><span class="sxs-lookup"><span data-stu-id="cc4ef-121">Step 1: Onboard endpoints to the service</span></span> 
- <span data-ttu-id="cc4ef-122">Paso 2: Configurar capacidades</span><span class="sxs-lookup"><span data-stu-id="cc4ef-122">Step 2: Configure capabilities</span></span> 

## <a name="step-1-onboard-endpoints-using-any-of-the-supported-management-tools"></a><span data-ttu-id="cc4ef-123">Paso 1: Incorporar puntos de conexión con cualquiera de las herramientas de administración admitidas</span><span class="sxs-lookup"><span data-stu-id="cc4ef-123">Step 1: Onboard endpoints using any of the supported management tools</span></span>
<span data-ttu-id="cc4ef-124">En [el tema Plan deployment](deployment-strategy.md) se describen los pasos generales que debe seguir para implementar Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="cc4ef-124">The [Plan deployment](deployment-strategy.md) topic outlines the general steps you need to take to deploy Defender for Endpoint.</span></span>  


<span data-ttu-id="cc4ef-125">Vea este vídeo para obtener una introducción rápida al proceso de incorporación y obtenga información sobre las herramientas y métodos disponibles.</span><span class="sxs-lookup"><span data-stu-id="cc4ef-125">Watch this video for a quick overview of the onboarding process and learn about the available tools and methods.</span></span>
<br />
<br />

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4bGqr]



<span data-ttu-id="cc4ef-126">Después de identificar la arquitectura, deberá decidir qué método de implementación usar.</span><span class="sxs-lookup"><span data-stu-id="cc4ef-126">After identifying your architecture, you'll need to decide which deployment method to use.</span></span> <span data-ttu-id="cc4ef-127">La herramienta de implementación que elija influye en la forma en que incorpora puntos de conexión al servicio.</span><span class="sxs-lookup"><span data-stu-id="cc4ef-127">The deployment tool you choose influences how you onboard endpoints to the service.</span></span> 

### <a name="onboarding-tool-options"></a><span data-ttu-id="cc4ef-128">Opciones de la herramienta de incorporación</span><span class="sxs-lookup"><span data-stu-id="cc4ef-128">Onboarding tool options</span></span>

<span data-ttu-id="cc4ef-129">En la tabla siguiente se enumeran las herramientas disponibles en función del extremo que necesita incorporar.</span><span class="sxs-lookup"><span data-stu-id="cc4ef-129">The following table lists the available tools based on the endpoint that you need to onboard.</span></span>

| <span data-ttu-id="cc4ef-130">Extremo</span><span class="sxs-lookup"><span data-stu-id="cc4ef-130">Endpoint</span></span>     | <span data-ttu-id="cc4ef-131">Opciones de herramientas</span><span class="sxs-lookup"><span data-stu-id="cc4ef-131">Tool options</span></span>                       |
|--------------|------------------------------------------|
| <span data-ttu-id="cc4ef-132">**Windows**</span><span class="sxs-lookup"><span data-stu-id="cc4ef-132">**Windows**</span></span>  |  [<span data-ttu-id="cc4ef-133">Script local (hasta 10 dispositivos)</span><span class="sxs-lookup"><span data-stu-id="cc4ef-133">Local script (up to 10 devices)</span></span>](configure-endpoints-script.md) <br>  [<span data-ttu-id="cc4ef-134">Directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="cc4ef-134">Group Policy</span></span>](configure-endpoints-gp.md) <br>  [<span data-ttu-id="cc4ef-135">Microsoft Endpoint Manager/ Administrador de dispositivos móviles</span><span class="sxs-lookup"><span data-stu-id="cc4ef-135">Microsoft Endpoint Manager/ Mobile Device Manager</span></span>](configure-endpoints-mdm.md) <br> [<span data-ttu-id="cc4ef-136">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="cc4ef-136">Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md) <br> [<span data-ttu-id="cc4ef-137">Scripts VDI</span><span class="sxs-lookup"><span data-stu-id="cc4ef-137">VDI scripts</span></span>](configure-endpoints-vdi.md) <br> [<span data-ttu-id="cc4ef-138">Integración con Azure Defender</span><span class="sxs-lookup"><span data-stu-id="cc4ef-138">Integration with Azure Defender</span></span>](configure-server-endpoints.md#integration-with-azure-defender) |
| <span data-ttu-id="cc4ef-139">**macOS**</span><span class="sxs-lookup"><span data-stu-id="cc4ef-139">**macOS**</span></span>    | [<span data-ttu-id="cc4ef-140">Scripts locales</span><span class="sxs-lookup"><span data-stu-id="cc4ef-140">Local scripts</span></span>](mac-install-manually.md) <br> [<span data-ttu-id="cc4ef-141">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="cc4ef-141">Microsoft Endpoint Manager</span></span>](mac-install-with-intune.md) <br> [<span data-ttu-id="cc4ef-142">Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="cc4ef-142">JAMF Pro</span></span>](mac-install-with-jamf.md) <br> [<span data-ttu-id="cc4ef-143">Administración de dispositivos móviles</span><span class="sxs-lookup"><span data-stu-id="cc4ef-143">Mobile Device Management</span></span>](mac-install-with-other-mdm.md) |
| <span data-ttu-id="cc4ef-144">**Servidor Linux**</span><span class="sxs-lookup"><span data-stu-id="cc4ef-144">**Linux Server**</span></span> | [<span data-ttu-id="cc4ef-145">Script local</span><span class="sxs-lookup"><span data-stu-id="cc4ef-145">Local script</span></span>](linux-install-manually.md) <br> [<span data-ttu-id="cc4ef-146">Puppet</span><span class="sxs-lookup"><span data-stu-id="cc4ef-146">Puppet</span></span>](linux-install-with-puppet.md) <br> [<span data-ttu-id="cc4ef-147">Ansible</span><span class="sxs-lookup"><span data-stu-id="cc4ef-147">Ansible</span></span>](linux-install-with-ansible.md)|
| <span data-ttu-id="cc4ef-148">**iOS**</span><span class="sxs-lookup"><span data-stu-id="cc4ef-148">**iOS**</span></span>      | [<span data-ttu-id="cc4ef-149">Basado en aplicaciones</span><span class="sxs-lookup"><span data-stu-id="cc4ef-149">App-based</span></span>](ios-install.md)                                |
| <span data-ttu-id="cc4ef-150">**Android**</span><span class="sxs-lookup"><span data-stu-id="cc4ef-150">**Android**</span></span>  | [<span data-ttu-id="cc4ef-151">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="cc4ef-151">Microsoft Endpoint Manager</span></span>](android-intune.md)               | 


## <a name="step-2-configure-capabilities"></a><span data-ttu-id="cc4ef-152">Paso 2: Configurar capacidades</span><span class="sxs-lookup"><span data-stu-id="cc4ef-152">Step 2: Configure capabilities</span></span>
<span data-ttu-id="cc4ef-153">Después de incorporar los puntos de conexión, configurarás las distintas funcionalidades, como detección y respuesta de puntos de conexión, protección de última generación y reducción de superficie de ataque.</span><span class="sxs-lookup"><span data-stu-id="cc4ef-153">After onboarding the endpoints, you'll then configure the various capabilities such as endpoint detection and response, next-generation protection, and attack surface reduction.</span></span> 


## <a name="example-deployments"></a><span data-ttu-id="cc4ef-154">Implementaciones de ejemplo</span><span class="sxs-lookup"><span data-stu-id="cc4ef-154">Example deployments</span></span>
<span data-ttu-id="cc4ef-155">En esta guía de implementación, le guiaremos a través del uso de dos herramientas de implementación para incorporar puntos de conexión y cómo configurar las capacidades.</span><span class="sxs-lookup"><span data-stu-id="cc4ef-155">In this deployment guide, we'll guide you through using two deployment tools to onboard endpoints and how to configure capabilities.</span></span>

<span data-ttu-id="cc4ef-156">Las herramientas de las implementaciones de ejemplo son:</span><span class="sxs-lookup"><span data-stu-id="cc4ef-156">The tools in the example deployments are:</span></span>
- [<span data-ttu-id="cc4ef-157">Incorporación mediante Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="cc4ef-157">Onboarding using Microsoft Endpoint Configuration Manager</span></span>](onboarding-endpoint-configuration-manager.md)
- [<span data-ttu-id="cc4ef-158">Incorporación con Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="cc4ef-158">Onboarding using Microsoft Endpoint Manager</span></span>](onboarding-endpoint-manager.md)

<span data-ttu-id="cc4ef-159">Con las herramientas de implementación mencionadas anteriormente, se le guiará en la configuración de las siguientes funcionalidades de Defender for Endpoint:</span><span class="sxs-lookup"><span data-stu-id="cc4ef-159">Using the mentioned deployment tools above, you'll then be guided in configuring the following Defender for Endpoint capabilities:</span></span>
- <span data-ttu-id="cc4ef-160">Detección de extremos y configuración de respuesta</span><span class="sxs-lookup"><span data-stu-id="cc4ef-160">Endpoint detection and response configuration</span></span>
- <span data-ttu-id="cc4ef-161">Configuración de protección de última generación</span><span class="sxs-lookup"><span data-stu-id="cc4ef-161">Next-generation protection configuration</span></span>
- <span data-ttu-id="cc4ef-162">Configuración de reducción de superficie de ataque</span><span class="sxs-lookup"><span data-stu-id="cc4ef-162">Attack surface reduction configuration</span></span>

## <a name="related-topics"></a><span data-ttu-id="cc4ef-163">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="cc4ef-163">Related topics</span></span>
- [<span data-ttu-id="cc4ef-164">Incorporación mediante Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="cc4ef-164">Onboarding using Microsoft Endpoint Configuration Manager</span></span>](onboarding-endpoint-configuration-manager.md)
- [<span data-ttu-id="cc4ef-165">Incorporación con Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="cc4ef-165">Onboarding using Microsoft Endpoint Manager</span></span>](onboarding-endpoint-manager.md)
- [<span data-ttu-id="cc4ef-166">Documentos seguros en Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="cc4ef-166">Safe Documents in Microsoft 365 E5</span></span>](../office-365-security/safe-docs.md)
