---
title: Implementación de Windows 10 Enterprise para Contoso
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: Entienda cómo Contoso usó Configuration Manager de Microsoft Endpoint para implementar las actualizaciones locales de Windows 10 Enterprise.
ms.openlocfilehash: 7907bf64acce3af8b21459202cb6f5cbc1e9f990
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907691"
---
# <a name="windows-10-enterprise-deployment-for-contoso"></a><span data-ttu-id="21a13-103">Implementación de Windows 10 Enterprise para Contoso</span><span class="sxs-lookup"><span data-stu-id="21a13-103">Windows 10 Enterprise deployment for Contoso</span></span>

<span data-ttu-id="21a13-104">Antes de la implementación de Microsoft 365 para empresas, Contoso tenía equipos y dispositivos compatibles con Windows que ejecutaba una mezcla de Windows 7 (10%), Windows 8.1 (65%) y Windows 10 (25%).</span><span class="sxs-lookup"><span data-stu-id="21a13-104">Prior to the wide rollout of Microsoft 365 for enterprise, Contoso had Windows-compatible PCs and devices running a mixture of Windows 7 (10%), Windows 8.1 (65%), and Windows 10 (25%).</span></span> <span data-ttu-id="21a13-105">Contoso quería actualizar sus equipos para Windows 10 Enterprise aprovechar la seguridad avanzada y reducir la sobrecarga de TI de las implementaciones automatizadas de actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="21a13-105">Contoso wanted to upgrade their PCs for Windows 10 Enterprise take advantage of advanced security and lowered IT overhead from automated deployments of updates.</span></span> 

<span data-ttu-id="21a13-106">Después de evaluar la infraestructura y las necesidades empresariales, Contoso identificó estos requisitos de implementación principales:</span><span class="sxs-lookup"><span data-stu-id="21a13-106">After assessing their infrastructure and business needs, Contoso identified these key requirements for the deployment:</span></span>

- <span data-ttu-id="21a13-107">Se debería ejecutar Windows 10 Enterprise en el mayor número posible de equipos y dispositivos.</span><span class="sxs-lookup"><span data-stu-id="21a13-107">As many PCs and devices as possible should run Windows 10 Enterprise</span></span>
- <span data-ttu-id="21a13-108">La implementación de las actualizaciones locales aprovecha la infraestructura existente de Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="21a13-108">Rollout of the in-place upgrades leverages existing Configuration Manager infrastructure</span></span>
- <span data-ttu-id="21a13-109">Control sobre qué versiones de Windows 10 Enterprise se implementan y actualizan a través de anillos.</span><span class="sxs-lookup"><span data-stu-id="21a13-109">Control over which versions of Windows 10 Enterprise to deploy and updates are done through rings</span></span>
- <span data-ttu-id="21a13-110">Los equipos y dispositivos se deberían mantener actualizados con los mínimos costos administrativos de TI y el menor impacto en los usuarios finales.</span><span class="sxs-lookup"><span data-stu-id="21a13-110">PCs and devices should stay up to date with minimal IT administrative costs and with minimal impact to end-users</span></span>

<span data-ttu-id="21a13-111">Actualizado se define como la versión compatible de Windows 10 Enterprise que satisface las necesidades empresariales de Contoso, lo que puede diferir de tener equipos compatibles con Windows con la versión más reciente de Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="21a13-111">Up to date is defined as the supported version of Windows 10 Enterprise that meets Contoso’s business needs, which can be different from having all Windows-compatible PCs running the latest version of Windows 10 Enterprise.</span></span>

## <a name="deployment-tools"></a><span data-ttu-id="21a13-112">Herramientas de implementación</span><span class="sxs-lookup"><span data-stu-id="21a13-112">Deployment tools</span></span>

<span data-ttu-id="21a13-113">Antes y durante las actualizaciones locales de Windows 10 Enterprise, Contoso usó las siguientes soluciones de Windows Analytics:</span><span class="sxs-lookup"><span data-stu-id="21a13-113">Prior to and during in-place upgrades of Windows 10 Enterprise, Contoso used the following solutions of Windows Analytics:</span></span>

- <span data-ttu-id="21a13-114">Upgrade Readiness</span><span class="sxs-lookup"><span data-stu-id="21a13-114">Upgrade Readiness</span></span>  

  <span data-ttu-id="21a13-115">Recopila datos del sistema, aplicaciones y controladores para el análisis y, después, identifica los problemas de compatibilidad que pueden bloquear una actualización y sugiere correcciones de los problemas que Microsoft conoce.</span><span class="sxs-lookup"><span data-stu-id="21a13-115">Collects system, application, and driver data for analysis, and then identifies compatibility issues that can block an upgrade and suggested fixes the issues are known to Microsoft.</span></span>

- <span data-ttu-id="21a13-116">Update Compliance</span><span class="sxs-lookup"><span data-stu-id="21a13-116">Update Compliance</span></span>  

  <span data-ttu-id="21a13-117">Le muestra el estado de sus dispositivos con respecto a las actualizaciones de Windows, para que pueda asegurarse de que tienen instaladas las actualizaciones más recientes según corresponda.</span><span class="sxs-lookup"><span data-stu-id="21a13-117">Shows you the state of your devices with respect to the Windows updates so that you can ensure that they are on the most current updates as appropriate.</span></span>

- <span data-ttu-id="21a13-118">Estado del dispositivo</span><span class="sxs-lookup"><span data-stu-id="21a13-118">Device Health</span></span>  

  <span data-ttu-id="21a13-119">Identifica los dispositivos que se bloquean con frecuencia y que quizás deban volver a crearse o reemplazarse, y los controladores de dispositivos que estén causando bloqueos en los mismos, y ofrece sugerencias de versiones alternativas de dichos controladores que pueden reducir el número de bloqueos.</span><span class="sxs-lookup"><span data-stu-id="21a13-119">Identifies devices that crash frequently, and therefore might need to be rebuilt or replaced and device drivers that are causing device crashes, with suggestions of alternative versions of those drivers that might reduce the number of crashes.</span></span> <span data-ttu-id="21a13-120">Proporciona una notificación de las configuraciones incorrectas de Windows Information Protection que envía avisos a los usuarios finales.</span><span class="sxs-lookup"><span data-stu-id="21a13-120">Provides notification of Windows Information Protection misconfigurations that send prompts to end users.</span></span>
 
<span data-ttu-id="21a13-p103">Contoso tiene una infraestructura existente de Configuration Manager (Rama actual). Configuration Manager se escala en entornos de gran tamaño y proporciona un amplio control sobre la instalación, las actualizaciones y la configuración. También incluye características integradas para que sea más fácil y eficaz implementar y administrar Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="21a13-p103">Contoso has an existing Configuration Manager (Current Branch) infrastructure. Configuration Manager scales for large environments and provides extensive control over installation, updates, and settings. It also has built-in features to make it easier and more efficient to deploy and manage Windows 10 Enterprise.</span></span>

## <a name="planning-process"></a><span data-ttu-id="21a13-124">Proceso de planeación</span><span class="sxs-lookup"><span data-stu-id="21a13-124">Planning process</span></span>

<span data-ttu-id="21a13-125">Contoso usó la preparación de actualización en Windows Analytics para determinar el conjunto de aplicaciones instaladas y su compatibilidad con Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="21a13-125">Contoso used the Upgrade Readiness in Windows Analytics to determine the set of installed apps and their compatibility with Windows 10 Enterprise.</span></span>

## <a name="deployment-process"></a><span data-ttu-id="21a13-126">Proceso de implementación</span><span class="sxs-lookup"><span data-stu-id="21a13-126">Deployment process</span></span>

<span data-ttu-id="21a13-127">Para completar la implementación de actualizaciones locales de Windows 10 Enterprise, Contoso implementó el siguiente proceso, que incluye los procedimientos recomendados de Microsoft:</span><span class="sxs-lookup"><span data-stu-id="21a13-127">To complete the in-place upgrade deployment of Windows 10 Enterprise, Contoso implemented the following process, which includes best practice recommendations from Microsoft:</span></span>

1. <span data-ttu-id="21a13-128">Habilitó la caché del mismo nivel para Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="21a13-128">Enabled peer cache for Configuration Manager.</span></span>
2. <span data-ttu-id="21a13-129">Creó paquetes de Windows personalizados en función de imágenes del Centro de servicios de licencias por volumen.</span><span class="sxs-lookup"><span data-stu-id="21a13-129">Created customized Windows packages based on images from the Volume Licensing Service Center.</span></span>
3. <span data-ttu-id="21a13-130">Se usó Configuration Manager para implementar los Windows paquetes de distribución en puntos de distribución en toda la red y se implementaron compilaciones en los tres grupos de validación e implementación provisional.</span><span class="sxs-lookup"><span data-stu-id="21a13-130">Used Configuration Manager to deploy the Windows packages to distribution points across their network and deployed builds to the three validation and deployment staging groups.</span></span>
4. <span data-ttu-id="21a13-131">Evaluó el éxito de los equipos y dispositivos en los tres anillos de validación y pruebas de implementación mediante las soluciones Estado del dispositivo y Update Compliance de Windows Analytics.</span><span class="sxs-lookup"><span data-stu-id="21a13-131">Performed assessment of success for PCs and devices in the three validation and deployment staging rings using the Device Health and Update Compliance solutions of Windows Analytics.</span></span>
5. <span data-ttu-id="21a13-132">En función de la Windows analytics, Contoso determinó la versión de Windows 10 Enterprise implementar en el grupo de implementación general.</span><span class="sxs-lookup"><span data-stu-id="21a13-132">Based on the Windows Analytics information, Contoso determined the version of Windows 10 Enterprise to deploy to the broad deployment group.</span></span>
6. <span data-ttu-id="21a13-133">Se ejecutaron las secuencias de tareas de implementación de Configuration Manager para implementar el paquete Windows seleccionado en el grupo de implementación general.</span><span class="sxs-lookup"><span data-stu-id="21a13-133">Ran the Configuration Manager deployment task sequences to deploy the selected Windows package to the broad deployment group.</span></span>
7. <span data-ttu-id="21a13-134">Equipos y dispositivos supervisados en el grupo de implementación general mediante las soluciones de mantenimiento de dispositivos y cumplimiento de actualizaciones para solucionar problemas.</span><span class="sxs-lookup"><span data-stu-id="21a13-134">Monitored PCs and devices in the broad deployment group using the Device Health and Update Compliance solutions to address issues.</span></span>

<span data-ttu-id="21a13-135">Aquí se muestra la arquitectura de implementación de actualización local y actualizaciones continuas de Contoso.</span><span class="sxs-lookup"><span data-stu-id="21a13-135">Here is Contoso’s in-place upgrade and ongoing updates deployment architecture.</span></span>

![Infraestructura de implementación de Windows 10 Enterprise de Contoso](../media/contoso-win10/contoso-win10-fig1.png)

<span data-ttu-id="21a13-137">Esta infraestructura consta de:</span><span class="sxs-lookup"><span data-stu-id="21a13-137">This infrastructure consists of:</span></span>

- <span data-ttu-id="21a13-138">Configuration Manager, el cual:</span><span class="sxs-lookup"><span data-stu-id="21a13-138">Configuration Manager, which:</span></span>
  - <span data-ttu-id="21a13-139">Obtiene imágenes de paquetes de Windows 10 Enterprise del Centro de servicios de licencias por volumen de Microsoft en Microsoft Network.</span><span class="sxs-lookup"><span data-stu-id="21a13-139">Obtains images for Windows 10 Enterprise packages from the Microsoft Volume Licensing Center in the Microsoft Network.</span></span>
  - <span data-ttu-id="21a13-140">Es el punto de administración central para los paquetes de implementación.</span><span class="sxs-lookup"><span data-stu-id="21a13-140">Is the central administration point for deployment packages.</span></span>
- <span data-ttu-id="21a13-141">Puntos de distribución regionales que normalmente se encuentran en las oficinas centrales regionales de Contoso.</span><span class="sxs-lookup"><span data-stu-id="21a13-141">Regional distribution points that are typically located in Contoso’s regional hub offices.</span></span>
- <span data-ttu-id="21a13-142">Windows Equipos y dispositivos en distintas ubicaciones que reciben e instalan los paquetes de implementación para la actualización local o actualizaciones en curso basadas en la pertenencia a grupos.</span><span class="sxs-lookup"><span data-stu-id="21a13-142">Windows PCs and devices in various locations that receive and install the deployment packages for the in-place upgrade or ongoing updates based on group membership.</span></span>

## <a name="next-step"></a><span data-ttu-id="21a13-143">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="21a13-143">Next step</span></span>

<span data-ttu-id="21a13-144">Obtenga información sobre cómo Contoso está aprovechando su infraestructura de Configuration Manager para [implementar y](contoso-o365pp.md) mantener las actualizaciones Aplicaciones Microsoft 365 para empresas toda la organización.</span><span class="sxs-lookup"><span data-stu-id="21a13-144">Learn how Contoso is leveraging its Configuration Manager infrastructure to [deploy and keep current Microsoft 365 Apps for enterprise](contoso-o365pp.md) across its organization.</span></span> 

## <a name="see-also"></a><span data-ttu-id="21a13-145">Consulte también</span><span class="sxs-lookup"><span data-stu-id="21a13-145">See also</span></span>

[<span data-ttu-id="21a13-146">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="21a13-146">Windows 10 Enterprise</span></span>](/windows/deployment/)

[<span data-ttu-id="21a13-147">Información general de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="21a13-147">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="21a13-148">Guías del laboratorio de pruebas</span><span class="sxs-lookup"><span data-stu-id="21a13-148">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)