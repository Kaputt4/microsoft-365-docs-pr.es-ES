---
title: Evaluar la Protección contra amenazas de Microsoft
description: Configure el entorno piloto o el laboratorio de pruebas de Microsoft Threat Protection para probar y experimentar la solución de seguridad diseñada para proteger los dispositivos, la identidad, los datos y las aplicaciones de su organización.
keywords: Microsoft Threat Protection Trial, pruebe Microsoft Threat Protection, evalúe Microsoft Threat Protection, Microsoft Threat Protection Evaluation Lab, Microsoft Threat Protection Pilot, Cyber Security, seguridad persistente avanzada, seguridad empresarial, dispositivos, dispositivo, identidad, usuarios, datos, aplicaciones, incidentes, investigación automatizada y corrección, búsqueda avanzada
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.openlocfilehash: d3f63c8ac4ba82a80c365dce564bbd8d3dd4da4b
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "48447124"
---
# <a name="create-a-microsoft-threat-protection-trial-lab-or-pilot-environment"></a><span data-ttu-id="6ab73-104">Crear un entorno piloto o un laboratorio de prueba de Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="6ab73-104">Create a Microsoft Threat Protection trial lab or pilot environment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="6ab73-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="6ab73-105">**Applies to:**</span></span>
- <span data-ttu-id="6ab73-106">Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="6ab73-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="6ab73-107">La finalidad de crear este entorno de prueba o un entorno piloto es ilustrar las capacidades completas e integradas de la protección contra amenazas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6ab73-107">The purpose of creating this trial lab or pilot environment is to illustrate the comprehensive and integrated Microsoft Threat Protection capabilities.</span></span> <span data-ttu-id="6ab73-108">Experimente cómo esta solución de seguridad inteligente detecta, evita, investiga automáticamente y responde a las amenazas avanzadas de su organización.</span><span class="sxs-lookup"><span data-stu-id="6ab73-108">Experience how this intelligent security solution detects, prevents, automatically investigates, and responds to advanced threats your organization.</span></span> 

<span data-ttu-id="6ab73-109">Esta guía le guiará por los pasos necesarios para iniciar la evaluación de Microsoft Threat Protection en función de las rutas de implementación recomendadas.</span><span class="sxs-lookup"><span data-stu-id="6ab73-109">This guide takes you through the steps to start your Microsoft Threat Protection evaluation based on the recommended deployment paths.</span></span> <span data-ttu-id="6ab73-110">El objetivo es ayudarle a configurar la solución de seguridad, ya sea en un entorno de laboratorio con una cuenta de prueba o en un entorno piloto en producción con una licencia completa.</span><span class="sxs-lookup"><span data-stu-id="6ab73-110">The goal is to help you set up the security solution either in a lab environment with a trial account, or in a pilot environment in production with a full license.</span></span> <span data-ttu-id="6ab73-111">La preparación del entorno piloto o del laboratorio de pruebas puede ayudarle a presentar los casos de uso de la operación de seguridad a los responsables de la toma de decisiones de la organización.</span><span class="sxs-lookup"><span data-stu-id="6ab73-111">Preparing your trial lab or pilot environment can help you present security operation use cases to decision makers in your organization.</span></span> <span data-ttu-id="6ab73-112">Cuando haya terminado de ejecutar las simulaciones de ataque y esté satisfecho con los resultados, puede implementar y descargar por completo en su organización con la ayuda de profesionales de ventas técnicos de Microsoft o expertos de su organización.</span><span class="sxs-lookup"><span data-stu-id="6ab73-112">When you’re done running your attack simulations and are satisfied with the results, you can fully deploy and operationalize it in your organization with the help of Microsoft Technical Sales Professionals or experts in your organization.</span></span> 

<span data-ttu-id="6ab73-113">Esta guía le ayudará a:</span><span class="sxs-lookup"><span data-stu-id="6ab73-113">This guide will help you:</span></span>
- <span data-ttu-id="6ab73-114">Configurar el servidor y los equipos del laboratorio</span><span class="sxs-lookup"><span data-stu-id="6ab73-114">Set up your lab server and computers</span></span>
- <span data-ttu-id="6ab73-115">Configuración de Active Directory con usuarios y grupos</span><span class="sxs-lookup"><span data-stu-id="6ab73-115">Configure Active Directory with users and groups</span></span>
- <span data-ttu-id="6ab73-116">Configurar y configurar ATP de Azure, ATP de Office, ATP de Microsoft defender y Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="6ab73-116">Set up and configure Azure ATP, Office ATP, Microsoft Defender ATP, and Microsoft Cloud App Security</span></span>
- <span data-ttu-id="6ab73-117">Configurar directivas locales para el servidor y los equipos</span><span class="sxs-lookup"><span data-stu-id="6ab73-117">Set up local policies for your server and computers</span></span>
- <span data-ttu-id="6ab73-118">Imitar un ataque de amenaza para generar una alerta o incidente de prueba en la protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="6ab73-118">Mimic a threat attack to generate a test incident or alert in Microsoft Threat Protection</span></span>

>[!IMPORTANT]
><span data-ttu-id="6ab73-119">Para obtener resultados óptimos, siga las instrucciones de configuración del laboratorio tan cerca como sea posible.</span><span class="sxs-lookup"><span data-stu-id="6ab73-119">For optimum results, follow the lab setup instructions as closely as possible.</span></span>


## <a name="deployment-phases"></a><span data-ttu-id="6ab73-120">Fases de implementación</span><span class="sxs-lookup"><span data-stu-id="6ab73-120">Deployment phases</span></span>

<span data-ttu-id="6ab73-121">Hay tres fases para la creación de un entorno de laboratorio de prueba de Microsoft Threat Protection y su implementación:</span><span class="sxs-lookup"><span data-stu-id="6ab73-121">There are three phases in creating a Microsoft Threat Protection trial lab environment and deploying it:</span></span>

|<span data-ttu-id="6ab73-122">Fase</span><span class="sxs-lookup"><span data-stu-id="6ab73-122">Phase</span></span> | <span data-ttu-id="6ab73-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="6ab73-123">Description</span></span> | 
|:-------|:-----|
| <span data-ttu-id="6ab73-124">![Fase 1: preparación](../../media/prepare.png)</span><span class="sxs-lookup"><span data-stu-id="6ab73-124">![Phase 1: Prepare](../../media/prepare.png)</span></span><br>[<span data-ttu-id="6ab73-125">Fase 1: preparación</span><span class="sxs-lookup"><span data-stu-id="6ab73-125">Phase 1: Prepare</span></span>](prepare-mtpeval.md)| <span data-ttu-id="6ab73-126">Obtenga información sobre lo que debe tener en cuenta al implementar la protección contra amenazas de Microsoft en un laboratorio de pruebas o un entorno piloto:</span><span class="sxs-lookup"><span data-stu-id="6ab73-126">Learn what you need to consider when deploying Microsoft Threat Protection in a trial lab or pilot environment:</span></span> <br><br><span data-ttu-id="6ab73-127">-Partes interesadas y la firma</span><span class="sxs-lookup"><span data-stu-id="6ab73-127">- Stakeholders and sign-off</span></span> <br> <span data-ttu-id="6ab73-128">Consideraciones del entorno</span><span class="sxs-lookup"><span data-stu-id="6ab73-128">- Environment considerations</span></span> <br><span data-ttu-id="6ab73-129">Acceso a</span><span class="sxs-lookup"><span data-stu-id="6ab73-129">- Access</span></span> <br><span data-ttu-id="6ab73-130">-Instalación de Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="6ab73-130">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="6ab73-131">-Orden de configuración</span><span class="sxs-lookup"><span data-stu-id="6ab73-131">- Configuration order</span></span>
|  <span data-ttu-id="6ab73-132">![Fase 2: configuración](../../media/setup.png)</span><span class="sxs-lookup"><span data-stu-id="6ab73-132">![Phase 2: Setup](../../media/setup.png)</span></span> <br>[<span data-ttu-id="6ab73-133">Fase 2: configuración</span><span class="sxs-lookup"><span data-stu-id="6ab73-133">Phase 2: Setup</span></span>](setup-mtpeval.md)|  <span data-ttu-id="6ab73-134">Siga los pasos iniciales para acceder al centro de seguridad de Microsoft 365 para configurar el entorno piloto o el laboratorio de pruebas de Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="6ab73-134">Take the initial steps to access Microsoft 365 Security Center to set up your Microsoft Threat Protection trial lab or pilot environment.</span></span> <span data-ttu-id="6ab73-135">Se le guiará a:</span><span class="sxs-lookup"><span data-stu-id="6ab73-135">You'll be guided to:</span></span><br><br><span data-ttu-id="6ab73-136">-Inscríbase en la versión de prueba de Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="6ab73-136">- Sign up for Microsoft 365 E5 Trial</span></span> <br>  <span data-ttu-id="6ab73-137">-Configurar dominio</span><span class="sxs-lookup"><span data-stu-id="6ab73-137">- Configure domain</span></span><br><span data-ttu-id="6ab73-138">-Asignar licencias de Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="6ab73-138">- Assign Microsoft 365 E5 licenses</span></span><br><span data-ttu-id="6ab73-139">-Completar el Asistente de configuración en el portal</span><span class="sxs-lookup"><span data-stu-id="6ab73-139">- Complete the setup wizard in the portal</span></span>|
|  <span data-ttu-id="6ab73-140">![Fase 3: configurar & incorporado](../../media/config-onboard.png)</span><span class="sxs-lookup"><span data-stu-id="6ab73-140">![Phase 3: Configure & Onboard](../../media/config-onboard.png)</span></span> <br>[<span data-ttu-id="6ab73-141">Fase 3: configurar & incorporado</span><span class="sxs-lookup"><span data-stu-id="6ab73-141">Phase 3: Configure & Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="6ab73-142">Configure cada uno de los extremos incorporados y de la protección contra amenazas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6ab73-142">Configure each Microsoft Threat Protection pillar and onboard endpoints.</span></span> <span data-ttu-id="6ab73-143">Se le guiará a:</span><span class="sxs-lookup"><span data-stu-id="6ab73-143">You'll be guided to:</span></span><br><br><span data-ttu-id="6ab73-144">-Configurar la protección contra amenazas avanzada de Office 365</span><span class="sxs-lookup"><span data-stu-id="6ab73-144">- Configure Office 365 Advanced Threat Protection</span></span><br><span data-ttu-id="6ab73-145">-Configurar Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="6ab73-145">- Configure Microsoft Cloud App Security</span></span><br><span data-ttu-id="6ab73-146">-Configurar la protección contra amenazas avanzada de Azure</span><span class="sxs-lookup"><span data-stu-id="6ab73-146">- Configure Azure Advanced Threat Protection</span></span><br><span data-ttu-id="6ab73-147">-Configurar la protección contra amenazas avanzada de Microsoft defender</span><span class="sxs-lookup"><span data-stu-id="6ab73-147">- Configure Microsoft Defender Advanced Threat Protection</span></span> 


## <a name="in-scope"></a><span data-ttu-id="6ab73-148">En el ámbito</span><span class="sxs-lookup"><span data-stu-id="6ab73-148">In scope</span></span>

<span data-ttu-id="6ab73-149">Las siguientes tareas se encuentran en el ámbito de esta guía:</span><span class="sxs-lookup"><span data-stu-id="6ab73-149">The following tasks are in scope for this guide:</span></span>
-   <span data-ttu-id="6ab73-150">Configurar Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="6ab73-150">Set up Azure Active Directory</span></span>
-   <span data-ttu-id="6ab73-151">Configuración de la protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="6ab73-151">Set up Microsoft Threat Protection</span></span>
    -   <span data-ttu-id="6ab73-152">Regístrese en la versión de prueba de Microsoft 365 E5 o use su licencia completa si está ejecutando un piloto</span><span class="sxs-lookup"><span data-stu-id="6ab73-152">Sign up for Microsoft 365 E5 Trial or use your full license if you're running a pilot</span></span>
    -   <span data-ttu-id="6ab73-153">Configurar dominio</span><span class="sxs-lookup"><span data-stu-id="6ab73-153">Configure domain</span></span>
    -   <span data-ttu-id="6ab73-154">Asignar licencias de Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="6ab73-154">Assign Microsoft 365 E5 licenses</span></span>
    -   <span data-ttu-id="6ab73-155">Finalización del Asistente para la instalación en el portal</span><span class="sxs-lookup"><span data-stu-id="6ab73-155">Completing the setup wizard within the portal</span></span>
-   <span data-ttu-id="6ab73-156">Configurar todos los pilares de la protección contra amenazas de Microsoft según los procedimientos recomendados</span><span class="sxs-lookup"><span data-stu-id="6ab73-156">Configure all Microsoft Threat Protection pillars based on best practices</span></span>
    -   <span data-ttu-id="6ab73-157">Protección contra amenazas avanzada de Office 365</span><span class="sxs-lookup"><span data-stu-id="6ab73-157">Office 365 Advanced Threat Protection</span></span>
    -   <span data-ttu-id="6ab73-158">Azure Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="6ab73-158">Azure Advanced Threat Protection</span></span>
    -   <span data-ttu-id="6ab73-159">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="6ab73-159">Microsoft Cloud App Security</span></span>
    -   <span data-ttu-id="6ab73-160">Protección contra amenazas avanzada de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="6ab73-160">Microsoft Defender Advanced Threat Protection</span></span>

## <a name="out-of-scope"></a><span data-ttu-id="6ab73-161">Fuera de ámbito</span><span class="sxs-lookup"><span data-stu-id="6ab73-161">Out of scope</span></span>

<span data-ttu-id="6ab73-162">Las siguientes opciones están fuera del ámbito de esta guía de implementación:</span><span class="sxs-lookup"><span data-stu-id="6ab73-162">The following are out of scope of this deployment guide:</span></span>

-   <span data-ttu-id="6ab73-163">Configuración de soluciones de terceros que pueden integrarse con la protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="6ab73-163">Configuration of third-party solutions that might integrate with Microsoft Threat Protection</span></span>
-   <span data-ttu-id="6ab73-164">Pruebas de penetración en el entorno de producción</span><span class="sxs-lookup"><span data-stu-id="6ab73-164">Penetration testing in production environment</span></span>

## <a name="next-step"></a><span data-ttu-id="6ab73-165">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="6ab73-165">Next step</span></span>
<span data-ttu-id="6ab73-166">![Fase 1: preparación](../../media/prepare.png)</span><span class="sxs-lookup"><span data-stu-id="6ab73-166">![Phase 1: Prepare](../../media/prepare.png)</span></span> <br><span data-ttu-id="6ab73-167">[Fase 1: preparación](prepare-mtpeval.md) 
</span><span class="sxs-lookup"><span data-stu-id="6ab73-167">[Phase 1: Prepare](prepare-mtpeval.md) 
</span></span><br> <span data-ttu-id="6ab73-168">Preparar el entorno piloto o el laboratorio de pruebas de Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="6ab73-168">Prepare your Microsoft Threat Protection trial lab or pilot environment</span></span>
