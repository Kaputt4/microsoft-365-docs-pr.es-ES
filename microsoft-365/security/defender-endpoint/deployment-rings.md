---
title: Implementar Microsoft Defender para endpoint en anillos
description: Obtenga información sobre cómo implementar Microsoft Defender para endpoint en anillos
keywords: deploy, rings, evaluate, pilot, insider fast, insider slow, setup, onboard, phase, deployment, deploying, adoption, configuring
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
- m365solution-overview
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 2d34b984436b3ed0537af2eebcd8475ec270cd8e
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165794"
---
# <a name="deploy-microsoft-defender-for-endpoint-in-rings"></a><span data-ttu-id="98e6b-104">Implementar Microsoft Defender para endpoint en anillos</span><span class="sxs-lookup"><span data-stu-id="98e6b-104">Deploy Microsoft Defender for Endpoint in rings</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="98e6b-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="98e6b-105">**Applies to:**</span></span>
- [<span data-ttu-id="98e6b-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="98e6b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="98e6b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="98e6b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="98e6b-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="98e6b-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="98e6b-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="98e6b-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="98e6b-110">La implementación de Microsoft Defender para endpoint se puede realizar mediante un enfoque de implementación basado en anillos.</span><span class="sxs-lookup"><span data-stu-id="98e6b-110">Deploying Microsoft Defender for Endpoint can be done using a ring-based deployment approach.</span></span> 

<span data-ttu-id="98e6b-111">Los anillos de implementación se pueden aplicar en los siguientes escenarios:</span><span class="sxs-lookup"><span data-stu-id="98e6b-111">The deployment rings can be applied in the following scenarios:</span></span>
- [<span data-ttu-id="98e6b-112">Nuevas implementaciones</span><span class="sxs-lookup"><span data-stu-id="98e6b-112">New deployments</span></span>](#new-deployments)
- [<span data-ttu-id="98e6b-113">Implementaciones existentes</span><span class="sxs-lookup"><span data-stu-id="98e6b-113">Existing deployments</span></span>](#existing-deployments)

## <a name="new-deployments"></a><span data-ttu-id="98e6b-114">Nuevas implementaciones</span><span class="sxs-lookup"><span data-stu-id="98e6b-114">New deployments</span></span>

![Imagen de anillos de implementación](images/deployment-rings.png)


<span data-ttu-id="98e6b-116">Un enfoque basado en anillos es un método para identificar un conjunto de puntos de conexión a incorporar y comprobar que se cumplen ciertos criterios antes de continuar con la implementación del servicio en un conjunto de dispositivos más grande.</span><span class="sxs-lookup"><span data-stu-id="98e6b-116">A ring-based approach is a method of identifying a set of endpoints to onboard and verifying that certain criteria is met before proceeding to deploy the service to a larger set of devices.</span></span> <span data-ttu-id="98e6b-117">Puede definir los criterios de salida de cada anillo y asegurarse de que se cumplen antes de pasar al siguiente anillo.</span><span class="sxs-lookup"><span data-stu-id="98e6b-117">You can define the exit criteria for each ring and ensure that they are satisfied before moving on to the next ring.</span></span>

<span data-ttu-id="98e6b-118">La adopción de una implementación basada en anillos ayuda a reducir los posibles problemas que podrían surgir al implementar el servicio.</span><span class="sxs-lookup"><span data-stu-id="98e6b-118">Adopting a ring-based deployment helps reduce potential issues that could arise while rolling out the service.</span></span> <span data-ttu-id="98e6b-119">Al pilotar un determinado número de dispositivos en primer lugar, puedes identificar posibles problemas y mitigar los posibles riesgos que puedan surgir.</span><span class="sxs-lookup"><span data-stu-id="98e6b-119">By piloting a certain number of devices first, you can identify potential issues and mitigate potential risks that might arise.</span></span> 


<span data-ttu-id="98e6b-120">La tabla 1 proporciona un ejemplo de los anillos de implementación que puede usar.</span><span class="sxs-lookup"><span data-stu-id="98e6b-120">Table 1 provides an example of the deployment rings you might use.</span></span> 

<span data-ttu-id="98e6b-121">**Tabla 1**</span><span class="sxs-lookup"><span data-stu-id="98e6b-121">**Table 1**</span></span>

|<span data-ttu-id="98e6b-122">**Anillo de implementación**</span><span class="sxs-lookup"><span data-stu-id="98e6b-122">**Deployment ring**</span></span>|<span data-ttu-id="98e6b-123">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="98e6b-123">**Description**</span></span>|
|:-----|:-----|
<span data-ttu-id="98e6b-124">Evaluate</span><span class="sxs-lookup"><span data-stu-id="98e6b-124">Evaluate</span></span> | <span data-ttu-id="98e6b-125">Anillo 1: Identificar 50 sistemas para pruebas piloto</span><span class="sxs-lookup"><span data-stu-id="98e6b-125">Ring 1: Identify 50 systems for pilot testing</span></span> 
<span data-ttu-id="98e6b-126">Piloto</span><span class="sxs-lookup"><span data-stu-id="98e6b-126">Pilot</span></span> | <span data-ttu-id="98e6b-127">Anillo 2: Identificar los siguientes 50-100 puntos de conexión en el entorno de producción</span><span class="sxs-lookup"><span data-stu-id="98e6b-127">Ring 2: Identify the next 50-100  endpoints in production environment</span></span> <br>  
<span data-ttu-id="98e6b-128">Implementación completa</span><span class="sxs-lookup"><span data-stu-id="98e6b-128">Full deployment</span></span> | <span data-ttu-id="98e6b-129">Anillo 3: Implementación del servicio en el resto del entorno en incrementos más grandes</span><span class="sxs-lookup"><span data-stu-id="98e6b-129">Ring 3: Roll out service to the rest of environment in larger increments</span></span>



### <a name="exit-criteria"></a><span data-ttu-id="98e6b-130">Criterios de salida</span><span class="sxs-lookup"><span data-stu-id="98e6b-130">Exit criteria</span></span>
<span data-ttu-id="98e6b-131">Un conjunto de ejemplos de criterios de salida para estos anillos puede incluir:</span><span class="sxs-lookup"><span data-stu-id="98e6b-131">An example set of exit criteria for these rings can include:</span></span>
- <span data-ttu-id="98e6b-132">Los dispositivos se muestran en la lista de inventario de dispositivos</span><span class="sxs-lookup"><span data-stu-id="98e6b-132">Devices show up in the device inventory list</span></span>
- <span data-ttu-id="98e6b-133">Las alertas aparecen en el panel</span><span class="sxs-lookup"><span data-stu-id="98e6b-133">Alerts appear in dashboard</span></span>
- [<span data-ttu-id="98e6b-134">Ejecutar una prueba de detección</span><span class="sxs-lookup"><span data-stu-id="98e6b-134">Run a detection test</span></span>](run-detection-test.md)
- [<span data-ttu-id="98e6b-135">Ejecutar un ataque simulado en un dispositivo</span><span class="sxs-lookup"><span data-stu-id="98e6b-135">Run a simulated attack on a device</span></span>](attack-simulations.md)

### <a name="evaluate"></a><span data-ttu-id="98e6b-136">Evaluate</span><span class="sxs-lookup"><span data-stu-id="98e6b-136">Evaluate</span></span>
<span data-ttu-id="98e6b-137">Identifique un pequeño número de máquinas de prueba en su entorno para incorporarse al servicio.</span><span class="sxs-lookup"><span data-stu-id="98e6b-137">Identify a small number of test machines in your environment to onboard to the service.</span></span> <span data-ttu-id="98e6b-138">Lo ideal es que estas máquinas sean menos de 50 puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="98e6b-138">Ideally, these machines would be fewer than 50 endpoints.</span></span> 


### <a name="pilot"></a><span data-ttu-id="98e6b-139">Piloto</span><span class="sxs-lookup"><span data-stu-id="98e6b-139">Pilot</span></span>
<span data-ttu-id="98e6b-140">ATP de Microsoft Defender admite una variedad de puntos de conexión que puede incorporar al servicio.</span><span class="sxs-lookup"><span data-stu-id="98e6b-140">Microsoft Defender ATP supports a variety of endpoints that you can onboard to the service.</span></span> <span data-ttu-id="98e6b-141">En este anillo, identifique varios dispositivos que se incorporarán y en función de los criterios de salida que defina, decida continuar con el siguiente anillo de implementación.</span><span class="sxs-lookup"><span data-stu-id="98e6b-141">In this ring, identify several devices to onboard and based on the exit criteria you define, decide to proceed to the next deployment ring.</span></span>

<span data-ttu-id="98e6b-142">En la tabla siguiente se muestran los puntos de conexión compatibles y la herramienta correspondiente que puede usar para incorporar dispositivos al servicio.</span><span class="sxs-lookup"><span data-stu-id="98e6b-142">The following table shows the supported endpoints and the corresponding tool you can use to onboard devices to the service.</span></span> 

| <span data-ttu-id="98e6b-143">Extremo</span><span class="sxs-lookup"><span data-stu-id="98e6b-143">Endpoint</span></span>     | <span data-ttu-id="98e6b-144">Herramienta de implementación</span><span class="sxs-lookup"><span data-stu-id="98e6b-144">Deployment tool</span></span>                       |
|--------------|------------------------------------------|
| <span data-ttu-id="98e6b-145">**Windows**</span><span class="sxs-lookup"><span data-stu-id="98e6b-145">**Windows**</span></span>  |  [<span data-ttu-id="98e6b-146">Script local (hasta 10 dispositivos)</span><span class="sxs-lookup"><span data-stu-id="98e6b-146">Local script (up to 10 devices)</span></span>](configure-endpoints-script.md) <br> <span data-ttu-id="98e6b-147">NOTA: Si desea implementar más de 10 dispositivos en un entorno de producción, use el método de directiva de grupo en su lugar o las otras herramientas compatibles que se enumeran a continuación.</span><span class="sxs-lookup"><span data-stu-id="98e6b-147">NOTE: If you want to deploy more than 10 devices in a production environment, use the Group Policy method instead or the other supported tools listed below.</span></span><br>  [<span data-ttu-id="98e6b-148">Directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="98e6b-148">Group Policy</span></span>](configure-endpoints-gp.md) <br>  [<span data-ttu-id="98e6b-149">Microsoft Endpoint Manager/Mobile Device Manager</span><span class="sxs-lookup"><span data-stu-id="98e6b-149">Microsoft Endpoint Manager/ Mobile Device Manager</span></span>](configure-endpoints-mdm.md) <br>   [<span data-ttu-id="98e6b-150">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="98e6b-150">Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md) <br> [<span data-ttu-id="98e6b-151">Scripts VDI</span><span class="sxs-lookup"><span data-stu-id="98e6b-151">VDI scripts</span></span>](configure-endpoints-vdi.md)   |
| <span data-ttu-id="98e6b-152">**macOS**</span><span class="sxs-lookup"><span data-stu-id="98e6b-152">**macOS**</span></span>    | [<span data-ttu-id="98e6b-153">Script local</span><span class="sxs-lookup"><span data-stu-id="98e6b-153">Local script</span></span>](mac-install-manually.md) <br> [<span data-ttu-id="98e6b-154">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="98e6b-154">Microsoft Endpoint Manager</span></span>](mac-install-with-intune.md) <br> [<span data-ttu-id="98e6b-155">JAMF Pro</span><span class="sxs-lookup"><span data-stu-id="98e6b-155">JAMF Pro</span></span>](mac-install-with-jamf.md) <br> [<span data-ttu-id="98e6b-156">Administración de dispositivos móviles</span><span class="sxs-lookup"><span data-stu-id="98e6b-156">Mobile Device Management</span></span>](mac-install-with-other-mdm.md) |
| <span data-ttu-id="98e6b-157">**Servidor Linux**</span><span class="sxs-lookup"><span data-stu-id="98e6b-157">**Linux Server**</span></span> | [<span data-ttu-id="98e6b-158">Script local</span><span class="sxs-lookup"><span data-stu-id="98e6b-158">Local script</span></span>](linux-install-manually.md) <br> [<span data-ttu-id="98e6b-159">Puppet</span><span class="sxs-lookup"><span data-stu-id="98e6b-159">Puppet</span></span>](linux-install-with-puppet.md) <br> [<span data-ttu-id="98e6b-160">Ansible</span><span class="sxs-lookup"><span data-stu-id="98e6b-160">Ansible</span></span>](linux-install-with-ansible.md)|
| <span data-ttu-id="98e6b-161">**iOS**</span><span class="sxs-lookup"><span data-stu-id="98e6b-161">**iOS**</span></span>      | [<span data-ttu-id="98e6b-162">Basado en aplicaciones</span><span class="sxs-lookup"><span data-stu-id="98e6b-162">App-based</span></span>](ios-install.md)                                |
| <span data-ttu-id="98e6b-163">**Android**</span><span class="sxs-lookup"><span data-stu-id="98e6b-163">**Android**</span></span>  | [<span data-ttu-id="98e6b-164">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="98e6b-164">Microsoft Endpoint Manager</span></span>](android-intune.md)               | 




### <a name="full-deployment"></a><span data-ttu-id="98e6b-165">Implementación completa</span><span class="sxs-lookup"><span data-stu-id="98e6b-165">Full deployment</span></span>
<span data-ttu-id="98e6b-166">En esta fase, puede usar el material de planeación [de implementación](deployment-strategy.md) para ayudarle a planear la implementación.</span><span class="sxs-lookup"><span data-stu-id="98e6b-166">At this stage, you can use the [Plan deployment](deployment-strategy.md) material to help you plan your deployment.</span></span> 


<span data-ttu-id="98e6b-167">Use el siguiente material para seleccionar la arquitectura de ATP de Microsoft Defender adecuada que mejor se adapte a su organización.</span><span class="sxs-lookup"><span data-stu-id="98e6b-167">Use the following material to select the appropriate Microsoft Defender ATP architecture that best suites your organization.</span></span>

|<span data-ttu-id="98e6b-168">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="98e6b-168">**Item**</span></span>|<span data-ttu-id="98e6b-169">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="98e6b-169">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="98e6b-170">[![Imagen en miniatura de la estrategia de implementación de ATP de Microsoft Defender](images/mdatp-deployment-strategy.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)</span><span class="sxs-lookup"><span data-stu-id="98e6b-170">[![Thumb image for Microsoft Defender ATP deployment strategy](images/mdatp-deployment-strategy.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)</span></span><br/> <span data-ttu-id="98e6b-171">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  \| [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx)</span><span class="sxs-lookup"><span data-stu-id="98e6b-171">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  \| [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx)</span></span> | <span data-ttu-id="98e6b-172">El material arquitectónico le ayuda a planear la implementación de las arquitecturas siguientes:</span><span class="sxs-lookup"><span data-stu-id="98e6b-172">The architectural material helps you plan your deployment for the following architectures:</span></span> <ul><li> <span data-ttu-id="98e6b-173">Nativo en la nube</span><span class="sxs-lookup"><span data-stu-id="98e6b-173">Cloud-native</span></span> </li><li> <span data-ttu-id="98e6b-174">Administración conjunta</span><span class="sxs-lookup"><span data-stu-id="98e6b-174">Co-management</span></span> </li><li> <span data-ttu-id="98e6b-175">Local</span><span class="sxs-lookup"><span data-stu-id="98e6b-175">On-premise</span></span></li><li><span data-ttu-id="98e6b-176">Evaluación e incorporación local</span><span class="sxs-lookup"><span data-stu-id="98e6b-176">Evaluation and local onboarding</span></span></li>




## <a name="existing-deployments"></a><span data-ttu-id="98e6b-177">Implementaciones existentes</span><span class="sxs-lookup"><span data-stu-id="98e6b-177">Existing deployments</span></span>

### <a name="windows-endpoints"></a><span data-ttu-id="98e6b-178">Puntos de conexión de Windows</span><span class="sxs-lookup"><span data-stu-id="98e6b-178">Windows endpoints</span></span>
<span data-ttu-id="98e6b-179">Para Windows y/o Windows Servers, seleccionas varias máquinas para probar con antelación (antes de la revisión del martes) mediante el programa de validación de actualizaciones de seguridad **(SUVP).**</span><span class="sxs-lookup"><span data-stu-id="98e6b-179">For Windows and/or Windows Servers, you select several machines to test ahead of time (before patch Tuesday) by using the **Security Update Validation program (SUVP)**.</span></span>

<span data-ttu-id="98e6b-180">Para más información, vea:</span><span class="sxs-lookup"><span data-stu-id="98e6b-180">For more information, see:</span></span>
- [<span data-ttu-id="98e6b-181">¿Qué es el programa de validación de actualización de seguridad?</span><span class="sxs-lookup"><span data-stu-id="98e6b-181">What is the Security Update Validation Program</span></span>](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/what-is-the-security-update-validation-program/ba-p/275767)
- [<span data-ttu-id="98e6b-182">Software Update Validation Program and Centro de protección contra malware de Microsoft Establishment - TwC Interactive Timeline Part 4</span><span class="sxs-lookup"><span data-stu-id="98e6b-182">Software Update Validation Program and Microsoft Malware Protection Center Establishment - TwC Interactive Timeline Part 4</span></span>](https://www.microsoft.com/security/blog/2012/03/28/software-update-validation-program-and-microsoft-malware-protection-center-establishment-twc-interactive-timeline-part-4/)


### <a name="non-windows-endpoints"></a><span data-ttu-id="98e6b-183">Puntos de conexión que no son de Windows</span><span class="sxs-lookup"><span data-stu-id="98e6b-183">Non-Windows endpoints</span></span>
<span data-ttu-id="98e6b-184">Con macOS y Linux, puede tomar un par de sistemas y ejecutarse en el canal "InsidersFast".</span><span class="sxs-lookup"><span data-stu-id="98e6b-184">With macOS and Linux, you could take a couple of systems and run in the "InsidersFast" channel.</span></span>

>[!NOTE]
><span data-ttu-id="98e6b-185">Lo ideal es que al menos un administrador de seguridad y un desarrollador puedan encontrar problemas de compatibilidad, rendimiento y confiabilidad antes de que la compilación lo haga en el canal "Producción".</span><span class="sxs-lookup"><span data-stu-id="98e6b-185">Ideally at least one security admin and one developer so that you are able to find compatibility, performance and reliability issues before the build makes it into the "Production" channel.</span></span>

<span data-ttu-id="98e6b-186">La elección del canal determina el tipo y la frecuencia de las actualizaciones que se ofrecen al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="98e6b-186">The choice of the channel determines the type and frequency of updates that are offered to your device.</span></span> <span data-ttu-id="98e6b-187">Los dispositivos de insiders-fast son los primeros en recibir actualizaciones y nuevas características, seguidos más adelante por insiders-slow y, por último, por prod.</span><span class="sxs-lookup"><span data-stu-id="98e6b-187">Devices in insiders-fast are the first ones to receive updates and new features, followed later by insiders-slow and lastly by prod.</span></span>

![Imagen de anillos insider](images/insider-rings.png)

<span data-ttu-id="98e6b-189">Para obtener una vista previa de las nuevas características y proporcionar comentarios anticipados, se recomienda configurar algunos dispositivos de la empresa para que usen insiders-fast o insiders-slow.</span><span class="sxs-lookup"><span data-stu-id="98e6b-189">In order to preview new features and provide early feedback, it is recommended that you configure some devices in your enterprise to use either insiders-fast or insiders-slow.</span></span>

>[!WARNING]
><span data-ttu-id="98e6b-190">Cambiar el canal después de la instalación inicial requiere que se vuelva a instalar el producto.</span><span class="sxs-lookup"><span data-stu-id="98e6b-190">Switching the channel after the initial installation requires the product to be reinstalled.</span></span> <span data-ttu-id="98e6b-191">Para cambiar el canal de producto: desinstale el paquete existente, vuelva a configurar el dispositivo para que use el nuevo canal y siga los pasos descritos en este documento para instalar el paquete desde la nueva ubicación.</span><span class="sxs-lookup"><span data-stu-id="98e6b-191">To switch the product channel: uninstall the existing package, re-configure your device to use the new channel, and follow the steps in this document to install the package from the new location.</span></span>
