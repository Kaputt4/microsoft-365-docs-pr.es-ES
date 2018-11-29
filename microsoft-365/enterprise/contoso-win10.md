---
title: Implementación de Windows 10 Enterprise para Contoso
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 09/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Obtenga información sobre cómo Contoso usó System Center Configuration Manager para implementar las actualizaciones locales de Windows 10 Enterprise.
ms.openlocfilehash: a4b24d55951c83875b9aa08db05fa4f8591472d6
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2018
ms.locfileid: "26871496"
---
# <a name="windows-10-enterprise-deployment-for-contoso"></a><span data-ttu-id="62f1c-103">Implementación de Windows 10 Enterprise para Contoso</span><span class="sxs-lookup"><span data-stu-id="62f1c-103">Windows 10 Enterprise deployment for Contoso</span></span>

<span data-ttu-id="62f1c-104">**Resumen:** Obtenga información sobre cómo Contoso usó System Center Configuration Manager para implementar las actualizaciones locales de Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="62f1c-104">**Summary:** Understand how Contoso used System Center Configuration Manager to deploy in-place upgrades for Windows 10 Enterprise.</span></span>

<span data-ttu-id="62f1c-p101">Antes de la amplia implementación de Microsoft 365 Enterprise, Contoso tenía equipos y dispositivos compatibles con Windows con una combinación de Windows 7 (10 %), Windows 8.1 (65 %) y Windows 10 (25 %). Contoso quería actualizar sus equipos para que Windows 10 Enterprise aprovechara las ventajas de la mejora de seguridad y la reducción de la sobrecarga de TI de las implementaciones automatizadas de las actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="62f1c-p101">Prior to the wide rollout of Microsoft 365 Enterprise, Contoso had Windows-compatible PCs and devices running a mixture of Windows 7 (10%), Windows 8.1 (65%), and Windows 10 (25%). Contoso wanted to upgrade their PCs for Windows 10 Enterprise take advantage of improved security and lowered IT overhead from automated deployments of updates.</span></span> 

<span data-ttu-id="62f1c-107">Después de evaluar la infraestructura y las necesidades empresariales, Contoso identificó estos requisitos de implementación principales:</span><span class="sxs-lookup"><span data-stu-id="62f1c-107">After assessing their infrastructure and business needs, Contoso identified these key requirements for the deployment:</span></span>

- <span data-ttu-id="62f1c-108">Se debería ejecutar Windows 10 Enterprise en el mayor número posible de equipos y dispositivos.</span><span class="sxs-lookup"><span data-stu-id="62f1c-108">As many PCs and devices as possible should run Windows 10 Enterprise</span></span>
- <span data-ttu-id="62f1c-109">La implementación de las actualizaciones locales aprovecha la infraestructura existente de System Center Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="62f1c-109">Rollout of the in-place upgrades leverages existing System Center Configuration Manager infrastructure</span></span>
- <span data-ttu-id="62f1c-110">Control sobre qué versiones de Windows 10 Enterprise se implementan y actualizan a través de anillos.</span><span class="sxs-lookup"><span data-stu-id="62f1c-110">Control over which versions of Windows 10 Enterprise to deploy and updates are done through rings</span></span>
- <span data-ttu-id="62f1c-111">Los equipos y dispositivos se deberían mantener actualizados con los mínimos costos administrativos de TI y el menor impacto en los usuarios finales.</span><span class="sxs-lookup"><span data-stu-id="62f1c-111">PCs and devices should stay up to date with minimal IT administrative costs and with minimal impact to end-users</span></span>

<span data-ttu-id="62f1c-112">Actualizado se define como la versión compatible de Windows 10 Enterprise que satisface las necesidades empresariales de Contoso, lo que puede diferir de tener equipos compatibles con Windows con la versión más reciente de Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="62f1c-112">Up to date is defined as the supported version of Windows 10 Enterprise that meets Contoso’s business needs, which can be different from having all Windows-compatible PCs running the latest version of Windows 10 Enterprise.</span></span>

## <a name="deployment-tools"></a><span data-ttu-id="62f1c-113">Herramientas de implementación</span><span class="sxs-lookup"><span data-stu-id="62f1c-113">Deployment tools</span></span>

<span data-ttu-id="62f1c-114">Antes y durante las actualizaciones locales de Windows 10 Enterprise, Contoso usó las siguientes soluciones de Windows Analytics:</span><span class="sxs-lookup"><span data-stu-id="62f1c-114">Prior to and during in-place upgrades of Windows 10 Enterprise, Contoso used the following solutions of Windows Analytics:</span></span>

- <span data-ttu-id="62f1c-115">Upgrade Readiness</span><span class="sxs-lookup"><span data-stu-id="62f1c-115">Upgrade Readiness</span></span>  

  <span data-ttu-id="62f1c-116">Recopila datos del sistema, aplicaciones y controladores para el análisis y, después, identifica los problemas de compatibilidad que pueden bloquear una actualización y sugiere correcciones de los problemas que Microsoft conoce.</span><span class="sxs-lookup"><span data-stu-id="62f1c-116">Collects system, application, and driver data for analysis, and then identifies compatibility issues that can block an upgrade and suggested fixes the issues are known to Microsoft.</span></span>

- <span data-ttu-id="62f1c-117">Update Compliance</span><span class="sxs-lookup"><span data-stu-id="62f1c-117">Update Compliance</span></span>  

  <span data-ttu-id="62f1c-118">Recopila datos del sistema y de diagnóstico como el progreso de instalación de la actualización, datos de configuración de Windows Update para empresas (WUfB), datos de Antivirus de Windows Defender y otra información específica de la actualización y, después, almacena estos datos en el análisis y uso en la nube.</span><span class="sxs-lookup"><span data-stu-id="62f1c-118">Collects system and diagnostics data including update installation progress, Windows Update for Business (WUfB) configuration data, Windows Defender Antivirus data, and other update-specific information, and then stores this data in the cloud analysis and usage.</span></span>

- <span data-ttu-id="62f1c-119">Estado del dispositivo</span><span class="sxs-lookup"><span data-stu-id="62f1c-119">Device Health</span></span>  

  <span data-ttu-id="62f1c-120">Recopila datos del sistema de Windows 10 y de diagnóstico como el progreso de instalación de la actualización, datos de configuración de Windows Update para empresas (WUfB), datos de Antivirus de Windows Defender y otra información específica de la actualización y, después, almacena estos datos en el análisis y uso en la nube.</span><span class="sxs-lookup"><span data-stu-id="62f1c-120">Collects Windows 10 system and diagnostic data including update installation progress, Windows Update for Business (WUfB) configuration data, Windows Defender Antivirus data, and other update-specific information, and then stores this data in the cloud analysis and usage.</span></span>
 
<span data-ttu-id="62f1c-p102">Contoso tiene una infraestructura existente de System Center Configuration Manager (Rama actual). Configuration Manager se escala en entornos de gran tamaño y proporciona un amplio control sobre la instalación, las actualizaciones y la configuración. También incluye características integradas para que implementar y administrar Windows 10 Enterprise sea más fácil y eficaz.</span><span class="sxs-lookup"><span data-stu-id="62f1c-p102">Contoso has an existing System Center Configuration Manager (Current Branch) infrastructure. Configuration Manager scales for large environments and provides extensive control over installation, updates, and settings. It also has built-in features to make it easier and more efficient to deploy and manage Windows 10 Enterprise.</span></span>

## <a name="planning-process"></a><span data-ttu-id="62f1c-124">Proceso de planeación</span><span class="sxs-lookup"><span data-stu-id="62f1c-124">Planning process</span></span>

<span data-ttu-id="62f1c-125">Antes de la implementación, Contoso definió los anillos siguientes:</span><span class="sxs-lookup"><span data-stu-id="62f1c-125">Prior to deployment, Contoso defined the following rings:</span></span>

- <span data-ttu-id="62f1c-126">Tres anillos de validación y pruebas de implementación</span><span class="sxs-lookup"><span data-stu-id="62f1c-126">Three rings for validation and deployment staging</span></span> 
  - <span data-ttu-id="62f1c-127">Uno para las compilaciones de versión preliminar</span><span class="sxs-lookup"><span data-stu-id="62f1c-127">One for preview builds</span></span> 
  - <span data-ttu-id="62f1c-128">Uno para las compilaciones de versión nuevas</span><span class="sxs-lookup"><span data-stu-id="62f1c-128">One for new release builds</span></span>
  - <span data-ttu-id="62f1c-129">Uno para una versión anterior</span><span class="sxs-lookup"><span data-stu-id="62f1c-129">One for a previous build</span></span> 
- <span data-ttu-id="62f1c-130">Un anillo para la implementación general de Windows 10 Enterprise en función de los datos de los anillos de validación</span><span class="sxs-lookup"><span data-stu-id="62f1c-130">One ring for broad deployment of Windows 10 Enterprise based on data from the validation rings</span></span>

<span data-ttu-id="62f1c-131">Contoso también usó la solución Upgrade Readiness de Windows Analytics para determinar el conjunto de aplicaciones instaladas y su compatibilidad con Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="62f1c-131">Contoso also used the Upgrade Readiness solution of Windows Analytics to determine the set of installed apps and their compatibility with Windows 10 Enterprise.</span></span>

## <a name="deployment-process"></a><span data-ttu-id="62f1c-132">Proceso de implementación</span><span class="sxs-lookup"><span data-stu-id="62f1c-132">Deployment process</span></span>

<span data-ttu-id="62f1c-133">Para completar la implementación de actualizaciones locales de Windows 10 Enterprise, Contoso implementó el siguiente proceso, que incluye los procedimientos recomendados de Microsoft:</span><span class="sxs-lookup"><span data-stu-id="62f1c-133">To complete the in-place upgrade deployment of Windows 10 Enterprise, Contoso implemented the following process, which includes best practice recommendations from Microsoft:</span></span>

1. <span data-ttu-id="62f1c-134">Habilitó la caché del mismo nivel para Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="62f1c-134">Enabled peer cache for Configuration Manager.</span></span>
2. <span data-ttu-id="62f1c-135">Creó paquetes de Windows personalizados en función de imágenes del Centro de servicios de licencias por volumen.</span><span class="sxs-lookup"><span data-stu-id="62f1c-135">Created customized Windows packages based on images from the Volume Licensing Service Center.</span></span>
3. <span data-ttu-id="62f1c-136">Usó Configuration Manager para implementar los paquetes de Windows en puntos de distribución en su red e implementó las compilaciones en los tres anillos de validación y pruebas de implementación.</span><span class="sxs-lookup"><span data-stu-id="62f1c-136">Used Configuration Manager to deploy the Windows packages to distribution points across their network and deployed builds to the three validation and deployment staging rings.</span></span>
4. <span data-ttu-id="62f1c-137">Evaluó el éxito de los equipos y dispositivos en los tres anillos de validación y pruebas de implementación mediante las soluciones Estado del dispositivo y Update Compliance de Windows Analytics.</span><span class="sxs-lookup"><span data-stu-id="62f1c-137">Performed assessment of success for PCs and devices in the three validation and deployment staging rings using the Device Health and Update Compliance solutions of Windows Analytics.</span></span>
5. <span data-ttu-id="62f1c-138">Según la información de Windows Analytics, Contoso determinó la versión de Windows 10 Enterprise que se iba a implementar en el anillo de implementación general.</span><span class="sxs-lookup"><span data-stu-id="62f1c-138">Based on the Windows Analytics information, Contoso determined the version of Windows 10 Enterprise to deploy to the broad deployment ring.</span></span>
6. <span data-ttu-id="62f1c-139">Ejecutó las secuencias de tareas de implementación de Configuration Manager para implementar el paquete de Windows seleccionado en el anillo de implementación general.</span><span class="sxs-lookup"><span data-stu-id="62f1c-139">Ran the Configuration Manager deployment task sequences to deploy the selected Windows package to the broad deployment ring.</span></span>
7. <span data-ttu-id="62f1c-140">Supervisó los equipos y dispositivos del anillo de implementación general mediante las soluciones Estado del dispositivo y Update Compliance proporcionadas por Windows Analytics para solucionar los problemas.</span><span class="sxs-lookup"><span data-stu-id="62f1c-140">Monitored PCs and devices in the broad deployment ring using the Device Health and Update Compliance solutions provided by Windows Analytics to address issues.</span></span>

<span data-ttu-id="62f1c-141">En la Figura 1 se muestra la arquitectura de implementación de actualización local y actualizaciones continuas.</span><span class="sxs-lookup"><span data-stu-id="62f1c-141">Figure 1 shows the in-place upgrade and ongoing updates deployment architecture.</span></span>

![](./media/contoso-win10/contoso-win10-fig1.png)
 
<span data-ttu-id="62f1c-142">**Figura 1: Infraestructura de implementación de Windows 10 Enterprise de Contoso**</span><span class="sxs-lookup"><span data-stu-id="62f1c-142">**Figure 1: Contoso’s Windows 10 Enterprise deployment infrastructure**</span></span>

<span data-ttu-id="62f1c-143">Esta infraestructura consta de:</span><span class="sxs-lookup"><span data-stu-id="62f1c-143">This infrastructure consists of:</span></span>

- <span data-ttu-id="62f1c-144">System Center Configuration Manager, que:</span><span class="sxs-lookup"><span data-stu-id="62f1c-144">System Center Configuration Manager, which:</span></span>
  - <span data-ttu-id="62f1c-145">Obtiene imágenes de paquetes de Windows 10 Enterprise del Centro de servicios de licencias por volumen de Microsoft en Microsoft Network.</span><span class="sxs-lookup"><span data-stu-id="62f1c-145">Obtains images for Windows 10 Enterprise packages from the Microsoft Volume Licensing Center in the Microsoft Network.</span></span>
  - <span data-ttu-id="62f1c-146">Es el punto de administración central para los paquetes de implementación.</span><span class="sxs-lookup"><span data-stu-id="62f1c-146">Is the central administration point for deployment packages.</span></span>
- <span data-ttu-id="62f1c-147">Puntos de distribución regionales que normalmente se encuentran en las oficinas satélite de Contoso.</span><span class="sxs-lookup"><span data-stu-id="62f1c-147">Regional distribution points that are typically located in Contoso’s satellite offices.</span></span>
- <span data-ttu-id="62f1c-148">Equipos y dispositivos Windows en diferentes ubicaciones que reciben e instalan los paquetes de implementación para la actualización local o las actualizaciones continuas según el anillo al que pertenezcan.</span><span class="sxs-lookup"><span data-stu-id="62f1c-148">Windows PCs and devices in various locations that receive and install the deployment packages for the in-place upgrade or ongoing updates based on ring membership.</span></span>

## <a name="next-step"></a><span data-ttu-id="62f1c-149">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="62f1c-149">Next step</span></span>

<span data-ttu-id="62f1c-150">[Obtenga información sobre](contoso-o365pp.md) cómo aprovecha Contoso su infraestructura de System Center Configuration Manager para implementar y mantener actualizado Office 365 ProPlus en la organización.</span><span class="sxs-lookup"><span data-stu-id="62f1c-150">[Learn](contoso-o365pp.md) how Contoso is leveraging its System Center Configuration Manager infrastructure to deploy and keep current Office 365 ProPlus across its organization.</span></span> 

## <a name="see-also"></a><span data-ttu-id="62f1c-151">Vea también</span><span class="sxs-lookup"><span data-stu-id="62f1c-151">See also</span></span>

[<span data-ttu-id="62f1c-152">Windows 10 Enterprise para Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="62f1c-152">Windows 10 Enterprise for Microsoft 365 Enterprise</span></span>](windows10-infrastructure.md)

[<span data-ttu-id="62f1c-153">Guía de implementación</span><span class="sxs-lookup"><span data-stu-id="62f1c-153">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="62f1c-154">Guías del laboratorio de pruebas</span><span class="sxs-lookup"><span data-stu-id="62f1c-154">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
