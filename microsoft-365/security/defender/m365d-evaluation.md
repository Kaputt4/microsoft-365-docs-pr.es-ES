---
title: Evaluar Microsoft 365 Defender
description: Configure su laboratorio Microsoft 365 Defender prueba o entorno piloto para probar y experimentar la solución de seguridad diseñada para proteger los dispositivos, la identidad, los datos y las aplicaciones de su organización.
keywords: Microsoft 365 Defender prueba, pruebe Microsoft 365 Defender, evalúe Microsoft 365 Defender, laboratorio de evaluación de Microsoft 365 Defender Microsoft 365 Defender, piloto, ciberseguridad, amenazas persistentes avanzadas, seguridad empresarial, dispositivos, identidad, usuarios, datos, aplicaciones, incidentes, investigación y corrección automatizadas, búsqueda avanzada
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 1c260588b80d8325567b74148a7a62586cfbc707
ms.sourcegitcommit: 9856f86532bdcf0befbcdbdb7c6dc6bf89fe63b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/16/2021
ms.locfileid: "53458833"
---
# <a name="create-a-microsoft-365-defender-trial-lab-or-pilot-environment"></a><span data-ttu-id="0cc0e-104">Crear un Microsoft 365 Defender de prueba o un entorno piloto</span><span class="sxs-lookup"><span data-stu-id="0cc0e-104">Create a Microsoft 365 Defender trial lab or pilot environment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="0cc0e-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="0cc0e-105">**Applies to:**</span></span>
- <span data-ttu-id="0cc0e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0cc0e-106">Microsoft 365 Defender</span></span>


<span data-ttu-id="0cc0e-107">Esta guía le ayuda a trabajar en la configuración de un entorno de laboratorio con usuarios y grupos y, a continuación, le guía a través de la configuración de las capacidades en Microsoft 365 Defender para que pueda imitar un ataque de amenazas y obtener un resultado de prueba significativo.</span><span class="sxs-lookup"><span data-stu-id="0cc0e-107">This guide helps you work across setting up a lab environment with users and groups, then guides you through the configuration of the capabilities in Microsoft 365 Defender so that you can mimic a threat attack and obtain a meaningful trial result.</span></span> 

<span data-ttu-id="0cc0e-108">El propósito de crear este entorno piloto o de laboratorio de prueba es ilustrar las capacidades Microsoft 365 Defender integradas.</span><span class="sxs-lookup"><span data-stu-id="0cc0e-108">The purpose of creating this trial lab or pilot environment is to illustrate the comprehensive and integrated Microsoft 365 Defender capabilities.</span></span> <span data-ttu-id="0cc0e-109">Experimente cómo esta solución de seguridad inteligente detecta, evita, investiga automáticamente y responde a amenazas avanzadas de su organización.</span><span class="sxs-lookup"><span data-stu-id="0cc0e-109">Experience how this intelligent security solution detects, prevents, automatically investigates, and responds to advanced threats your organization.</span></span> 


<span data-ttu-id="0cc0e-110">Se le guiará a través de los pasos para iniciar la evaluación Microsoft 365 Defender en función de las rutas de implementación recomendadas.</span><span class="sxs-lookup"><span data-stu-id="0cc0e-110">You will be guided through the steps to start your Microsoft 365 Defender evaluation based on the recommended deployment paths.</span></span> <span data-ttu-id="0cc0e-111">El objetivo es ayudarle a configurar la solución de seguridad en un entorno de laboratorio con una cuenta de prueba o en un entorno piloto en producción con una licencia completa.</span><span class="sxs-lookup"><span data-stu-id="0cc0e-111">The goal is to help you set up the security solution either in a lab environment with a trial account, or in a pilot environment in production with a full license.</span></span> <span data-ttu-id="0cc0e-112">Preparar el entorno piloto o de laboratorio de prueba puede ayudarle a presentar casos de uso de la operación de seguridad a los responsables de la toma de decisiones de su organización.</span><span class="sxs-lookup"><span data-stu-id="0cc0e-112">Preparing your trial lab or pilot environment can help you present security operation use cases to decision makers in your organization.</span></span> <span data-ttu-id="0cc0e-113">Cuando haya terminado de ejecutar las simulaciones de ataque y esté satisfecho con los resultados, puede implementarlo y operarlo completamente en su organización con la ayuda de profesionales de ventas técnicas de Microsoft o expertos en su organización.</span><span class="sxs-lookup"><span data-stu-id="0cc0e-113">When you’re done running your attack simulations and are satisfied with the results, you can fully deploy and operationalize it in your organization with the help of Microsoft Technical Sales Professionals or experts in your organization.</span></span> 

<span data-ttu-id="0cc0e-114">Esta guía le ayudará a:</span><span class="sxs-lookup"><span data-stu-id="0cc0e-114">This guide will help you:</span></span>
- <span data-ttu-id="0cc0e-115">Configurar el servidor de laboratorio y los equipos</span><span class="sxs-lookup"><span data-stu-id="0cc0e-115">Set up your lab server and computers</span></span>
- <span data-ttu-id="0cc0e-116">Configurar Active Directory con usuarios y grupos</span><span class="sxs-lookup"><span data-stu-id="0cc0e-116">Configure Active Directory with users and groups</span></span>
- <span data-ttu-id="0cc0e-117">Configurar y configurar Microsoft Defender para Identity, Microsoft Defender para Office 365, Microsoft Defender para endpoint y Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="0cc0e-117">Set up and configure Microsoft Defender for Identity, Microsoft Defender for Office 365, Microsoft Defender for Endpoint, and Microsoft Cloud App Security</span></span>
- <span data-ttu-id="0cc0e-118">Configurar directivas locales para el servidor y los equipos</span><span class="sxs-lookup"><span data-stu-id="0cc0e-118">Set up local policies for your server and computers</span></span>
- <span data-ttu-id="0cc0e-119">Imitar un ataque de amenaza para generar un incidente de prueba o una alerta en Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0cc0e-119">Mimic a threat attack to generate a test incident or alert in Microsoft 365 Defender</span></span>

>[!IMPORTANT]
><span data-ttu-id="0cc0e-120">Para obtener resultados óptimos, siga las instrucciones de configuración del laboratorio lo más de cerca posible.</span><span class="sxs-lookup"><span data-stu-id="0cc0e-120">For optimum results, follow the lab setup instructions as closely as possible.</span></span>


## <a name="deployment-phases"></a><span data-ttu-id="0cc0e-121">Fases de implementación</span><span class="sxs-lookup"><span data-stu-id="0cc0e-121">Deployment phases</span></span>

<span data-ttu-id="0cc0e-122">Existen tres fases para crear un entorno de Microsoft 365 Defender de prueba.</span><span class="sxs-lookup"><span data-stu-id="0cc0e-122">There are three phases in creating a Microsoft 365 Defender trial lab environment.</span></span>

![Fases de implementación: preparar, configurar, incorporar](../../media/evaluation-guide-phases.png)

|<span data-ttu-id="0cc0e-124">Fase</span><span class="sxs-lookup"><span data-stu-id="0cc0e-124">Phase</span></span> | <span data-ttu-id="0cc0e-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="0cc0e-125">Description</span></span> | 
|:-------|:-----|
|[<span data-ttu-id="0cc0e-126">Fase 1: Preparación</span><span class="sxs-lookup"><span data-stu-id="0cc0e-126">Phase 1: Prepare</span></span>](prepare-m365d-eval.md)| <span data-ttu-id="0cc0e-127">Obtenga información sobre lo que debe tener en cuenta al implementar Microsoft 365 Defender en un entorno piloto o de laboratorio de prueba:</span><span class="sxs-lookup"><span data-stu-id="0cc0e-127">Learn what you need to consider when deploying Microsoft 365 Defender in a trial lab or pilot environment:</span></span> <br><br><span data-ttu-id="0cc0e-128">- Partes interesadas y inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="0cc0e-128">- Stakeholders and sign-off</span></span> <br> <span data-ttu-id="0cc0e-129">- Consideraciones sobre el entorno</span><span class="sxs-lookup"><span data-stu-id="0cc0e-129">- Environment considerations</span></span> <br><span data-ttu-id="0cc0e-130">- Access</span><span class="sxs-lookup"><span data-stu-id="0cc0e-130">- Access</span></span> <br><span data-ttu-id="0cc0e-131">- Azure Active Directory configuración</span><span class="sxs-lookup"><span data-stu-id="0cc0e-131">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="0cc0e-132">- Orden de configuración</span><span class="sxs-lookup"><span data-stu-id="0cc0e-132">- Configuration order</span></span>
|[<span data-ttu-id="0cc0e-133">Fase 2: Configuración</span><span class="sxs-lookup"><span data-stu-id="0cc0e-133">Phase 2: Setup</span></span>](setup-m365deval.md)|  <span data-ttu-id="0cc0e-134">Siga los pasos iniciales para obtener acceso Microsoft 365 de seguridad para configurar el entorno Microsoft 365 Defender prueba o entorno piloto.</span><span class="sxs-lookup"><span data-stu-id="0cc0e-134">Take the initial steps to access Microsoft 365 Security Center to set up your Microsoft 365 Defender trial lab or pilot environment.</span></span> <span data-ttu-id="0cc0e-135">Se le guiará a:</span><span class="sxs-lookup"><span data-stu-id="0cc0e-135">You'll be guided to:</span></span><br><br><span data-ttu-id="0cc0e-136">- Registrarse para la Microsoft 365 E5 prueba</span><span class="sxs-lookup"><span data-stu-id="0cc0e-136">- Sign up for Microsoft 365 E5 Trial</span></span> <br>  <span data-ttu-id="0cc0e-137">- Configurar dominio</span><span class="sxs-lookup"><span data-stu-id="0cc0e-137">- Configure domain</span></span><br><span data-ttu-id="0cc0e-138">- Asignar Microsoft 365 E5 licencias</span><span class="sxs-lookup"><span data-stu-id="0cc0e-138">- Assign Microsoft 365 E5 licenses</span></span><br><span data-ttu-id="0cc0e-139">- Completar el asistente de configuración en el portal</span><span class="sxs-lookup"><span data-stu-id="0cc0e-139">- Complete the setup wizard in the portal</span></span>|
|[<span data-ttu-id="0cc0e-140">Fase 3: Configurar & incorporación</span><span class="sxs-lookup"><span data-stu-id="0cc0e-140">Phase 3: Configure & Onboard</span></span>](config-m365d-eval.md) | <span data-ttu-id="0cc0e-141">Configure cada Microsoft 365 Defender y puntos de conexión integrados.</span><span class="sxs-lookup"><span data-stu-id="0cc0e-141">Configure each Microsoft 365 Defender pillar and onboard endpoints.</span></span> <span data-ttu-id="0cc0e-142">Se le guiará a:</span><span class="sxs-lookup"><span data-stu-id="0cc0e-142">You'll be guided to:</span></span><br><br><span data-ttu-id="0cc0e-143">- Configurar Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="0cc0e-143">- Configure Microsoft Defender for Office 365</span></span><br><span data-ttu-id="0cc0e-144">- Configurar Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="0cc0e-144">- Configure Microsoft Cloud App Security</span></span><br><span data-ttu-id="0cc0e-145">- Configurar Microsoft Defender para la identidad</span><span class="sxs-lookup"><span data-stu-id="0cc0e-145">- Configure Microsoft Defender for Identity</span></span><br><span data-ttu-id="0cc0e-146">- Configurar Microsoft Defender para el punto de conexión</span><span class="sxs-lookup"><span data-stu-id="0cc0e-146">- Configure Microsoft Defender for Endpoint</span></span>


<span data-ttu-id="0cc0e-147">Después de completar esta guía, habría identificado las partes interesadas implicadas y las aprobaciones necesarias, tiene los permisos de acceso adecuados, se ha registrado para la prueba, los dominios configurados y cada uno de los pilares de Microsoft 365 Defender y los puntos de conexión se incorporarán al servicio.</span><span class="sxs-lookup"><span data-stu-id="0cc0e-147">After you've completed this guide, you would have identified the stakeholders involved and the required approvals,  have the right access permissions, signed up for trial, configured domains and each of the Microsoft 365 Defender pillars, and your endpoints will be onboarded to the service.</span></span>

## <a name="key-capabilities"></a><span data-ttu-id="0cc0e-148">Principales funcionalidades</span><span class="sxs-lookup"><span data-stu-id="0cc0e-148">Key capabilities</span></span>

<span data-ttu-id="0cc0e-149">Aunque Microsoft 365 Defender muchas funcionalidades, el objetivo principal de esta guía de implementación es empezar a incorporar dispositivos.</span><span class="sxs-lookup"><span data-stu-id="0cc0e-149">While Microsoft 365 Defender provides many capabilities, the primary purpose of this deployment guide is to get you started by onboarding devices.</span></span> <span data-ttu-id="0cc0e-150">Además de la incorporación, esta guía le permite empezar con las siguientes funcionalidades.</span><span class="sxs-lookup"><span data-stu-id="0cc0e-150">In addition to onboarding, this guidance gets you started with the following capabilities.</span></span>


<span data-ttu-id="0cc0e-151">Funcionalidad</span><span class="sxs-lookup"><span data-stu-id="0cc0e-151">Capability</span></span> | <span data-ttu-id="0cc0e-152">Descripción</span><span class="sxs-lookup"><span data-stu-id="0cc0e-152">Description</span></span> 
:---|:---
<span data-ttu-id="0cc0e-153">Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="0cc0e-153">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="0cc0e-154">Ayuda a proteger toda la Office 365 envrionment de las amenazas actuales</span><span class="sxs-lookup"><span data-stu-id="0cc0e-154">Helps protect your entire Office 365 envrionment from today's threats</span></span>
<span data-ttu-id="0cc0e-155">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="0cc0e-155">Microsoft Defender for Identity</span></span> | <span data-ttu-id="0cc0e-156">Identifica y detecta amenazas en identidades comprometidas y acciones internas malintencionadas.</span><span class="sxs-lookup"><span data-stu-id="0cc0e-156">Identifies and detects  threats on compromised identities and malicious insider actions.</span></span>
<span data-ttu-id="0cc0e-157">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="0cc0e-157">Microsoft Cloud App Security</span></span> | <span data-ttu-id="0cc0e-158">Proporciona una visibilidad enriquecida, controla los viajes de datos y detecta ciberamenazas en los servicios en la nube.</span><span class="sxs-lookup"><span data-stu-id="0cc0e-158">Provides rich visibility, control data travel, and detect cyberthreats across cloud services.</span></span>
<span data-ttu-id="0cc0e-159">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="0cc0e-159">Microsoft Defender for Endpoint</span></span> | <span data-ttu-id="0cc0e-160">Impide, detecta y proporciona capacidades de respuesta a amenazas avanzadas con una seguridad de extremo completa.</span><span class="sxs-lookup"><span data-stu-id="0cc0e-160">Prevents, detects, and provides response capabilities to advanced threats with comprehensive endpoint security.</span></span>


## <a name="in-scope"></a><span data-ttu-id="0cc0e-161">En el ámbito</span><span class="sxs-lookup"><span data-stu-id="0cc0e-161">In scope</span></span>

<span data-ttu-id="0cc0e-162">Las siguientes tareas están en el ámbito de esta guía:</span><span class="sxs-lookup"><span data-stu-id="0cc0e-162">The following tasks are in scope for this guide:</span></span>
-   <span data-ttu-id="0cc0e-163">Configurar Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="0cc0e-163">Set up Azure Active Directory</span></span>
-   <span data-ttu-id="0cc0e-164">Configurar Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0cc0e-164">Set up Microsoft 365 Defender</span></span>
    -   <span data-ttu-id="0cc0e-165">Regístrate para Microsoft 365 E5 prueba o usa la licencia completa si estás ejecutando un piloto</span><span class="sxs-lookup"><span data-stu-id="0cc0e-165">Sign up for Microsoft 365 E5 Trial or use your full license if you're running a pilot</span></span>
    -   <span data-ttu-id="0cc0e-166">Configurar dominio</span><span class="sxs-lookup"><span data-stu-id="0cc0e-166">Configure domain</span></span>
    -   <span data-ttu-id="0cc0e-167">Asignar Microsoft 365 E5 licencias</span><span class="sxs-lookup"><span data-stu-id="0cc0e-167">Assign Microsoft 365 E5 licenses</span></span>
    -   <span data-ttu-id="0cc0e-168">Completar el asistente de configuración en el portal</span><span class="sxs-lookup"><span data-stu-id="0cc0e-168">Completing the setup wizard within the portal</span></span>
-   <span data-ttu-id="0cc0e-169">Configurar todos los Microsoft 365 Defender basados en procedimientos recomendados</span><span class="sxs-lookup"><span data-stu-id="0cc0e-169">Configure all Microsoft 365 Defender pillars based on best practices</span></span>
    -   <span data-ttu-id="0cc0e-170">Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="0cc0e-170">Microsoft Defender for Office 365</span></span>
    -   <span data-ttu-id="0cc0e-171">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="0cc0e-171">Microsoft Defender for Identity</span></span>
    -   <span data-ttu-id="0cc0e-172">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="0cc0e-172">Microsoft Cloud App Security</span></span>
    -   <span data-ttu-id="0cc0e-173">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="0cc0e-173">Microsoft Defender for Endpoint</span></span>

## <a name="out-of-scope"></a><span data-ttu-id="0cc0e-174">Fuera de ámbito</span><span class="sxs-lookup"><span data-stu-id="0cc0e-174">Out of scope</span></span>

<span data-ttu-id="0cc0e-175">Los siguientes están fuera del ámbito de esta guía de implementación:</span><span class="sxs-lookup"><span data-stu-id="0cc0e-175">The following are out of scope of this deployment guide:</span></span>

-   <span data-ttu-id="0cc0e-176">Configuración de soluciones de terceros que podrían integrarse con Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0cc0e-176">Configuration of third-party solutions that might integrate with Microsoft 365 Defender</span></span>
-   <span data-ttu-id="0cc0e-177">Pruebas de penetración en entornos de producción</span><span class="sxs-lookup"><span data-stu-id="0cc0e-177">Penetration testing in production environment</span></span>

## <a name="next-step"></a><span data-ttu-id="0cc0e-178">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="0cc0e-178">Next step</span></span>
<span data-ttu-id="0cc0e-179">[Fase 1: Preparar](prepare-m365d-eval.md) 
</span><span class="sxs-lookup"><span data-stu-id="0cc0e-179">[Phase 1: Prepare](prepare-m365d-eval.md) 
</span></span><br> <span data-ttu-id="0cc0e-180">Preparar su laboratorio Microsoft 365 Defender prueba o entorno piloto</span><span class="sxs-lookup"><span data-stu-id="0cc0e-180">Prepare your Microsoft 365 Defender trial lab or pilot environment</span></span>
