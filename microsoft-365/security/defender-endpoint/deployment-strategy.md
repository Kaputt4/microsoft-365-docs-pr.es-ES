---
title: Planear la implementación de Microsoft Defender para puntos de conexión
description: Seleccionar la mejor estrategia de implementación de Microsoft Defender para endpoint para su entorno
keywords: deploy, plan, deployment strategy, cloud native, management, on prem, evaluation, onboarding, local, group policy, gp, endpoint manager, mem
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 8cd670e72bbb4ec0abacd4ed053a9ea9af12608b
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163580"
---
# <a name="plan-your-microsoft-defender-for-endpoint-deployment"></a><span data-ttu-id="e2390-104">Planear la implementación de Microsoft Defender para puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="e2390-104">Plan your Microsoft Defender for Endpoint deployment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e2390-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="e2390-105">**Applies to:**</span></span>
- [<span data-ttu-id="e2390-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="e2390-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="e2390-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e2390-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="e2390-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="e2390-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="e2390-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="e2390-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-secopsdashboard-abovefoldlink) 


<span data-ttu-id="e2390-110">Planee la implementación de Microsoft Defender para puntos de conexión para que pueda maximizar las capacidades de seguridad dentro del conjunto de aplicaciones y proteger mejor su empresa de las amenazas cibernéticas.</span><span class="sxs-lookup"><span data-stu-id="e2390-110">Plan your Microsoft Defender for Endpoint deployment so that you can maximize the security capabilities within the suite and better protect your enterprise from cyber threats.</span></span>


<span data-ttu-id="e2390-111">Esta solución proporciona instrucciones sobre cómo identificar la arquitectura del entorno, seleccionar el tipo de herramienta de implementación que mejor se adapte a sus necesidades y instrucciones sobre cómo configurar las capacidades.</span><span class="sxs-lookup"><span data-stu-id="e2390-111">This solution provides guidance on how to identify your environment architecture, select the type of deployment tool that best fits your needs, and guidance on how to configure capabilities.</span></span>


![Imagen del flujo de implementación](images/deployment-guide-plan.png)


## <a name="step-1-identify-architecture"></a><span data-ttu-id="e2390-113">Paso 1: Identificar arquitectura</span><span class="sxs-lookup"><span data-stu-id="e2390-113">Step 1: Identify architecture</span></span>
<span data-ttu-id="e2390-114">Entendemos que cada entorno de empresa es único, por lo que hemos proporcionado varias opciones para darle la flexibilidad necesaria para elegir cómo implementar el servicio.</span><span class="sxs-lookup"><span data-stu-id="e2390-114">We understand that every enterprise environment is unique, so we've provided several options to give you the flexibility in choosing how to deploy the service.</span></span>

<span data-ttu-id="e2390-115">Dependiendo de su entorno, algunas herramientas son más adecuadas para determinadas arquitecturas.</span><span class="sxs-lookup"><span data-stu-id="e2390-115">Depending on your environment, some tools are better suited for certain architectures.</span></span> 

<span data-ttu-id="e2390-116">Use el siguiente material para seleccionar la arquitectura de Defender for Endpoint adecuada que mejor se adapte a su organización.</span><span class="sxs-lookup"><span data-stu-id="e2390-116">Use the following material to select the appropriate Defender for Endpoint architecture that best suites your organization.</span></span>

| <span data-ttu-id="e2390-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="e2390-117">Item</span></span> | <span data-ttu-id="e2390-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="e2390-118">Description</span></span> |
|:-----|:-----|
|<span data-ttu-id="e2390-119">[![Imagen digital de la estrategia de implementación de Defender for Endpoint](images/mdatp-deployment-strategy.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)</span><span class="sxs-lookup"><span data-stu-id="e2390-119">[![Thumb image for Defender for Endpoint deployment strategy](images/mdatp-deployment-strategy.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)</span></span><br/> <span data-ttu-id="e2390-120">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  \| [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx)</span><span class="sxs-lookup"><span data-stu-id="e2390-120">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  \| [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx)</span></span> | <span data-ttu-id="e2390-121">El material arquitectónico le ayuda a planear la implementación de las arquitecturas siguientes:</span><span class="sxs-lookup"><span data-stu-id="e2390-121">The architectural material helps you plan your deployment for the following architectures:</span></span> <ul><li> <span data-ttu-id="e2390-122">Nativo en la nube</span><span class="sxs-lookup"><span data-stu-id="e2390-122">Cloud-native</span></span> </li><li> <span data-ttu-id="e2390-123">Administración conjunta</span><span class="sxs-lookup"><span data-stu-id="e2390-123">Co-management</span></span> </li><li> <span data-ttu-id="e2390-124">Local</span><span class="sxs-lookup"><span data-stu-id="e2390-124">On-premise</span></span></li><li><span data-ttu-id="e2390-125">Evaluación e incorporación local</span><span class="sxs-lookup"><span data-stu-id="e2390-125">Evaluation and local onboarding</span></span></li>



## <a name="step-2-select-deployment-method"></a><span data-ttu-id="e2390-126">Paso 2: Seleccionar método de implementación</span><span class="sxs-lookup"><span data-stu-id="e2390-126">Step 2: Select deployment method</span></span>
<span data-ttu-id="e2390-127">Defender for Endpoint admite una variedad de puntos de conexión que puede incorporar al servicio.</span><span class="sxs-lookup"><span data-stu-id="e2390-127">Defender for Endpoint supports a variety of endpoints that you can onboard to the service.</span></span> 

<span data-ttu-id="e2390-128">En la tabla siguiente se enumeran los puntos de conexión admitidos y la herramienta de implementación correspondiente que puede usar para poder planear la implementación adecuadamente.</span><span class="sxs-lookup"><span data-stu-id="e2390-128">The following table lists the supported endpoints and the corresponding deployment tool that you can use so that you can plan the deployment appropriately.</span></span>

| <span data-ttu-id="e2390-129">Extremo</span><span class="sxs-lookup"><span data-stu-id="e2390-129">Endpoint</span></span>     | <span data-ttu-id="e2390-130">Herramienta de implementación</span><span class="sxs-lookup"><span data-stu-id="e2390-130">Deployment tool</span></span>                       |
|--------------|------------------------------------------|
| <span data-ttu-id="e2390-131">**Windows**</span><span class="sxs-lookup"><span data-stu-id="e2390-131">**Windows**</span></span>  |  [<span data-ttu-id="e2390-132">Script local (hasta 10 dispositivos)</span><span class="sxs-lookup"><span data-stu-id="e2390-132">Local script (up to 10 devices)</span></span>](configure-endpoints-script.md) <br>  [<span data-ttu-id="e2390-133">Directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="e2390-133">Group Policy</span></span>](configure-endpoints-gp.md) <br>  [<span data-ttu-id="e2390-134">Microsoft Endpoint Manager/ Administrador de dispositivos móviles</span><span class="sxs-lookup"><span data-stu-id="e2390-134">Microsoft Endpoint Manager/ Mobile Device Manager</span></span>](configure-endpoints-mdm.md) <br>   [<span data-ttu-id="e2390-135">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="e2390-135">Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md) <br> [<span data-ttu-id="e2390-136">Scripts VDI</span><span class="sxs-lookup"><span data-stu-id="e2390-136">VDI scripts</span></span>](configure-endpoints-vdi.md)   |
| <span data-ttu-id="e2390-137">**macOS**</span><span class="sxs-lookup"><span data-stu-id="e2390-137">**macOS**</span></span>    | [<span data-ttu-id="e2390-138">Script local</span><span class="sxs-lookup"><span data-stu-id="e2390-138">Local script</span></span>](mac-install-manually.md) <br> [<span data-ttu-id="e2390-139">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="e2390-139">Microsoft Endpoint Manager</span></span>](mac-install-with-intune.md) <br> [<span data-ttu-id="e2390-140">Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="e2390-140">JAMF Pro</span></span>](mac-install-with-jamf.md) <br> [<span data-ttu-id="e2390-141">Administración de dispositivos móviles</span><span class="sxs-lookup"><span data-stu-id="e2390-141">Mobile Device Management</span></span>](mac-install-with-other-mdm.md) |
| <span data-ttu-id="e2390-142">**Servidor Linux**</span><span class="sxs-lookup"><span data-stu-id="e2390-142">**Linux Server**</span></span> | [<span data-ttu-id="e2390-143">Script local</span><span class="sxs-lookup"><span data-stu-id="e2390-143">Local script</span></span>](linux-install-manually.md) <br> [<span data-ttu-id="e2390-144">Puppet</span><span class="sxs-lookup"><span data-stu-id="e2390-144">Puppet</span></span>](linux-install-with-puppet.md) <br> [<span data-ttu-id="e2390-145">Ansible</span><span class="sxs-lookup"><span data-stu-id="e2390-145">Ansible</span></span>](linux-install-with-ansible.md)|
| <span data-ttu-id="e2390-146">**iOS**</span><span class="sxs-lookup"><span data-stu-id="e2390-146">**iOS**</span></span>      | [<span data-ttu-id="e2390-147">Basado en aplicaciones</span><span class="sxs-lookup"><span data-stu-id="e2390-147">App-based</span></span>](ios-install.md)                                |
| <span data-ttu-id="e2390-148">**Android**</span><span class="sxs-lookup"><span data-stu-id="e2390-148">**Android**</span></span>  | [<span data-ttu-id="e2390-149">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="e2390-149">Microsoft Endpoint Manager</span></span>](android-intune.md)               | 



## <a name="step-3-configure-capabilities"></a><span data-ttu-id="e2390-150">Paso 3: Configurar capacidades</span><span class="sxs-lookup"><span data-stu-id="e2390-150">Step 3: Configure capabilities</span></span>
<span data-ttu-id="e2390-151">Después de incorporar puntos de conexión, configure las capacidades de seguridad en Defender para endpoint para que pueda maximizar la sólida protección de seguridad disponible en el conjunto de servidores.</span><span class="sxs-lookup"><span data-stu-id="e2390-151">After onboarding endpoints, configure the security capabilities in Defender for Endpoint so that you can maximize the robust security protection available in the suite.</span></span> <span data-ttu-id="e2390-152">Las funcionalidades incluyen:</span><span class="sxs-lookup"><span data-stu-id="e2390-152">Capabilities include:</span></span>

- <span data-ttu-id="e2390-153">EDR</span><span class="sxs-lookup"><span data-stu-id="e2390-153">Endpoint detection and response</span></span>
- <span data-ttu-id="e2390-154">Protección de última generación</span><span class="sxs-lookup"><span data-stu-id="e2390-154">Next-generation protection</span></span>
- <span data-ttu-id="e2390-155">Reducción de la superficie expuesta a ataques</span><span class="sxs-lookup"><span data-stu-id="e2390-155">Attack surface reduction</span></span>


  
## <a name="related-topics"></a><span data-ttu-id="e2390-156">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="e2390-156">Related topics</span></span>
- [<span data-ttu-id="e2390-157">Fases de implementación</span><span class="sxs-lookup"><span data-stu-id="e2390-157">Deployment phases</span></span>](deployment-phases.md)
