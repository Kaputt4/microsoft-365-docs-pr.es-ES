---
title: Evaluación de Microsoft 365 Defender
description: Configure el entorno piloto o el laboratorio de prueba de Microsoft 365 Defender para probar y experimentar la solución de seguridad diseñada para proteger dispositivos, identidades, datos y aplicaciones de su organización.
keywords: Prueba de Protección contra amenazas de Microsoft, pruebe la Protección contra amenazas de Microsoft, evalúe la Protección contra amenazas de Microsoft, el laboratorio de evaluación de protección contra amenazas de Microsoft, el piloto de Protección contra amenazas de Microsoft, la seguridad cibernética, la amenaza persistente avanzada, la seguridad empresarial, los dispositivos, el dispositivo, la identidad, los usuarios, los datos, las aplicaciones, los incidentes, la investigación y corrección automatizada, la búsqueda avanzada
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 6735817a71f9fb50843acad3a13596ec247aa407
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930215"
---
# <a name="create-a-microsoft-365-defender-trial-lab-or-pilot-environment"></a><span data-ttu-id="64fbf-104">Crear un entorno piloto o laboratorio de prueba de Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="64fbf-104">Create a Microsoft 365 Defender trial lab or pilot environment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="64fbf-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="64fbf-105">**Applies to:**</span></span>
- <span data-ttu-id="64fbf-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="64fbf-106">Microsoft 365 Defender</span></span>


<span data-ttu-id="64fbf-107">Esta guía le ayuda a trabajar en la configuración de un entorno de laboratorio con usuarios y grupos y, a continuación, le guiará a través de la configuración de las capacidades de Microsoft 365 Defender para que pueda imitar un ataque de amenazas y obtener un resultado de prueba significativo.</span><span class="sxs-lookup"><span data-stu-id="64fbf-107">This guide helps you work across setting up a lab environment with users and groups, then guides you through the configuration of the capabilities in Microsoft 365 Defender so that you can mimic a threat attack and obtain a meaningful trial result.</span></span> 

<span data-ttu-id="64fbf-108">El propósito de crear este entorno de prueba o piloto es ilustrar las capacidades completas e integradas de Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="64fbf-108">The purpose of creating this trial lab or pilot environment is to illustrate the comprehensive and integrated Microsoft 365 Defender capabilities.</span></span> <span data-ttu-id="64fbf-109">Experimente cómo esta solución de seguridad inteligente detecta, impide, investiga automáticamente y responde a amenazas avanzadas de su organización.</span><span class="sxs-lookup"><span data-stu-id="64fbf-109">Experience how this intelligent security solution detects, prevents, automatically investigates, and responds to advanced threats your organization.</span></span> 


<span data-ttu-id="64fbf-110">Se le guiará por los pasos para iniciar la evaluación de Microsoft 365 Defender en función de las rutas de implementación recomendadas.</span><span class="sxs-lookup"><span data-stu-id="64fbf-110">You will be guided through the steps to start your Microsoft 365 Defender evaluation based on the recommended deployment paths.</span></span> <span data-ttu-id="64fbf-111">El objetivo es ayudarle a configurar la solución de seguridad en un entorno de laboratorio con una cuenta de prueba o en un entorno piloto en producción con una licencia completa.</span><span class="sxs-lookup"><span data-stu-id="64fbf-111">The goal is to help you set up the security solution either in a lab environment with a trial account, or in a pilot environment in production with a full license.</span></span> <span data-ttu-id="64fbf-112">Preparar el entorno de prueba o piloto puede ayudarle a presentar casos de uso de operaciones de seguridad a los responsables de la toma de decisiones de su organización.</span><span class="sxs-lookup"><span data-stu-id="64fbf-112">Preparing your trial lab or pilot environment can help you present security operation use cases to decision makers in your organization.</span></span> <span data-ttu-id="64fbf-113">Cuando haya terminado de ejecutar las simulaciones de ataque y esté satisfecho con los resultados, puede implementarlo y operarlo completamente en su organización con la ayuda de los profesionales de ventas técnicas de Microsoft o expertos de su organización.</span><span class="sxs-lookup"><span data-stu-id="64fbf-113">When you’re done running your attack simulations and are satisfied with the results, you can fully deploy and operationalize it in your organization with the help of Microsoft Technical Sales Professionals or experts in your organization.</span></span> 

<span data-ttu-id="64fbf-114">Esta guía le ayudará a:</span><span class="sxs-lookup"><span data-stu-id="64fbf-114">This guide will help you:</span></span>
- <span data-ttu-id="64fbf-115">Configurar el servidor de laboratorio y los equipos</span><span class="sxs-lookup"><span data-stu-id="64fbf-115">Set up your lab server and computers</span></span>
- <span data-ttu-id="64fbf-116">Configurar Active Directory con usuarios y grupos</span><span class="sxs-lookup"><span data-stu-id="64fbf-116">Configure Active Directory with users and groups</span></span>
- <span data-ttu-id="64fbf-117">Configurar Microsoft Defender para Identity, Microsoft Defender para Office 365, Microsoft Defender para Endpoint y Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="64fbf-117">Set up and configure Microsoft Defender for Identity, Microsoft Defender for Office 365, Microsoft Defender for Endpoint, and Microsoft Cloud App Security</span></span>
- <span data-ttu-id="64fbf-118">Configurar directivas locales para el servidor y los equipos</span><span class="sxs-lookup"><span data-stu-id="64fbf-118">Set up local policies for your server and computers</span></span>
- <span data-ttu-id="64fbf-119">Imitar un ataque de amenaza para generar una alerta o incidente de prueba en Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="64fbf-119">Mimic a threat attack to generate a test incident or alert in Microsoft 365 Defender</span></span>

>[!IMPORTANT]
><span data-ttu-id="64fbf-120">Para obtener resultados óptimos, siga las instrucciones de configuración del laboratorio lo más cerca posible.</span><span class="sxs-lookup"><span data-stu-id="64fbf-120">For optimum results, follow the lab setup instructions as closely as possible.</span></span>


## <a name="deployment-phases"></a><span data-ttu-id="64fbf-121">Fases de implementación</span><span class="sxs-lookup"><span data-stu-id="64fbf-121">Deployment phases</span></span>

<span data-ttu-id="64fbf-122">Hay tres fases para crear un entorno de laboratorio de prueba de Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="64fbf-122">There are three phases in creating a Microsoft 365 Defender trial lab environment.</span></span>

![Fases de implementación: preparar, configurar, incorporar](../../media/evaluation-guide-phases.png)

|<span data-ttu-id="64fbf-124">Fase</span><span class="sxs-lookup"><span data-stu-id="64fbf-124">Phase</span></span> | <span data-ttu-id="64fbf-125">Description</span><span class="sxs-lookup"><span data-stu-id="64fbf-125">Description</span></span> | 
|:-------|:-----|
|[<span data-ttu-id="64fbf-126">Fase 1: Preparar</span><span class="sxs-lookup"><span data-stu-id="64fbf-126">Phase 1: Prepare</span></span>](prepare-mtpeval.md)| <span data-ttu-id="64fbf-127">Obtenga información sobre lo que necesita tener en cuenta al implementar Microsoft 365 Defender en un entorno piloto o laboratorio de prueba:</span><span class="sxs-lookup"><span data-stu-id="64fbf-127">Learn what you need to consider when deploying Microsoft 365 Defender in a trial lab or pilot environment:</span></span> <br><br><span data-ttu-id="64fbf-128">- Partes interesadas y cerrar sesión</span><span class="sxs-lookup"><span data-stu-id="64fbf-128">- Stakeholders and sign-off</span></span> <br> <span data-ttu-id="64fbf-129">- Consideraciones de entorno</span><span class="sxs-lookup"><span data-stu-id="64fbf-129">- Environment considerations</span></span> <br><span data-ttu-id="64fbf-130">- Acceso</span><span class="sxs-lookup"><span data-stu-id="64fbf-130">- Access</span></span> <br><span data-ttu-id="64fbf-131">- Configuración de Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="64fbf-131">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="64fbf-132">- Orden de configuración</span><span class="sxs-lookup"><span data-stu-id="64fbf-132">- Configuration order</span></span>
|[<span data-ttu-id="64fbf-133">Fase 2: Instalación</span><span class="sxs-lookup"><span data-stu-id="64fbf-133">Phase 2: Setup</span></span>](setup-mtpeval.md)|  <span data-ttu-id="64fbf-134">Siga los pasos iniciales para acceder al Centro de seguridad de Microsoft 365 para configurar el entorno piloto o el laboratorio de prueba de Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="64fbf-134">Take the initial steps to access Microsoft 365 Security Center to set up your Microsoft 365 Defender trial lab or pilot environment.</span></span> <span data-ttu-id="64fbf-135">Se le guiará a:</span><span class="sxs-lookup"><span data-stu-id="64fbf-135">You'll be guided to:</span></span><br><br><span data-ttu-id="64fbf-136">- Registrarse para la prueba de Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="64fbf-136">- Sign up for Microsoft 365 E5 Trial</span></span> <br>  <span data-ttu-id="64fbf-137">- Configurar dominio</span><span class="sxs-lookup"><span data-stu-id="64fbf-137">- Configure domain</span></span><br><span data-ttu-id="64fbf-138">- Asignar licencias de Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="64fbf-138">- Assign Microsoft 365 E5 licenses</span></span><br><span data-ttu-id="64fbf-139">- Completar el asistente de configuración en el portal</span><span class="sxs-lookup"><span data-stu-id="64fbf-139">- Complete the setup wizard in the portal</span></span>|
|[<span data-ttu-id="64fbf-140">Fase 3: Configurar & incorporación</span><span class="sxs-lookup"><span data-stu-id="64fbf-140">Phase 3: Configure & Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="64fbf-141">Configurar cada columna de Microsoft 365 Defender y incorporar puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="64fbf-141">Configure each Microsoft 365 Defender pillar and onboard endpoints.</span></span> <span data-ttu-id="64fbf-142">Se le guiará a:</span><span class="sxs-lookup"><span data-stu-id="64fbf-142">You'll be guided to:</span></span><br><br><span data-ttu-id="64fbf-143">- Configurar Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="64fbf-143">- Configure Microsoft Defender for Office 365</span></span><br><span data-ttu-id="64fbf-144">- Configurar Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="64fbf-144">- Configure Microsoft Cloud App Security</span></span><br><span data-ttu-id="64fbf-145">- Configurar Microsoft Defender para la identidad</span><span class="sxs-lookup"><span data-stu-id="64fbf-145">- Configure Microsoft Defender for Identity</span></span><br><span data-ttu-id="64fbf-146">- Configurar Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="64fbf-146">- Configure Microsoft Defender for Endpoint</span></span>


<span data-ttu-id="64fbf-147">Después de completar esta guía, habrá identificado a las partes interesadas implicadas y las aprobaciones necesarias, tiene los permisos de acceso adecuados, se ha registrado para la prueba, los dominios configurados y cada uno de los pilares de Microsoft 365 Defender, y los puntos de conexión se incorporarán al servicio.</span><span class="sxs-lookup"><span data-stu-id="64fbf-147">After you've completed this guide, you would have identified the stakeholders involved and the required approvals,  have the right access permissions, signed up for trial, configured domains and each of the Microsoft 365 Defender pillars, and your endpoints will be onboarded to the service.</span></span>

## <a name="key-capabilities"></a><span data-ttu-id="64fbf-148">Principales funcionalidades</span><span class="sxs-lookup"><span data-stu-id="64fbf-148">Key capabilities</span></span>

<span data-ttu-id="64fbf-149">Aunque Microsoft 365 Defender proporciona muchas funcionalidades, el propósito principal de esta guía de implementación es empezar a incorporar dispositivos.</span><span class="sxs-lookup"><span data-stu-id="64fbf-149">While Microsoft 365 Defender provides many capabilities, the primary purpose of this deployment guide is to get you started by onboarding devices.</span></span> <span data-ttu-id="64fbf-150">Además de la incorporación, estas instrucciones te ayudarán a empezar con las siguientes funcionalidades.</span><span class="sxs-lookup"><span data-stu-id="64fbf-150">In addition to onboarding, this guidance gets you started with the following capabilities.</span></span>


<span data-ttu-id="64fbf-151">Funcionalidad</span><span class="sxs-lookup"><span data-stu-id="64fbf-151">Capability</span></span> | <span data-ttu-id="64fbf-152">Descripción</span><span class="sxs-lookup"><span data-stu-id="64fbf-152">Description</span></span> 
:---|:---
<span data-ttu-id="64fbf-153">Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="64fbf-153">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="64fbf-154">Ayuda a proteger todo el aislamiento de Office 365 de las amenazas actuales</span><span class="sxs-lookup"><span data-stu-id="64fbf-154">Helps protect your entire Office 365 envrionment from today's threats</span></span>
<span data-ttu-id="64fbf-155">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="64fbf-155">Microsoft Defender for Identity</span></span> | <span data-ttu-id="64fbf-156">Identifica y detecta amenazas en identidades comprometidas y acciones internas malintencionadas.</span><span class="sxs-lookup"><span data-stu-id="64fbf-156">Identifies and detects  threats on compromised identities and malicious insider actions.</span></span>
<span data-ttu-id="64fbf-157">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="64fbf-157">Microsoft Cloud App Security</span></span> | <span data-ttu-id="64fbf-158">Proporciona una visibilidad enriquecida, controla los viajes de datos y detecta ciberamenazas en los servicios en la nube.</span><span class="sxs-lookup"><span data-stu-id="64fbf-158">Provides rich visibility, control data travel, and detect cyberthreats across cloud services.</span></span>
<span data-ttu-id="64fbf-159">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="64fbf-159">Microsoft Defender for Endpoint</span></span> | <span data-ttu-id="64fbf-160">Impide, detecta y proporciona capacidades de respuesta a amenazas avanzadas con seguridad completa de los puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="64fbf-160">Prevents, detects, and provides response capabilities to advanced threats with comprehensive endpoint security.</span></span>


## <a name="in-scope"></a><span data-ttu-id="64fbf-161">En el ámbito</span><span class="sxs-lookup"><span data-stu-id="64fbf-161">In scope</span></span>

<span data-ttu-id="64fbf-162">Las siguientes tareas están en el ámbito de esta guía:</span><span class="sxs-lookup"><span data-stu-id="64fbf-162">The following tasks are in scope for this guide:</span></span>
-   <span data-ttu-id="64fbf-163">Configurar Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="64fbf-163">Set up Azure Active Directory</span></span>
-   <span data-ttu-id="64fbf-164">Configurar Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="64fbf-164">Set up Microsoft 365 Defender</span></span>
    -   <span data-ttu-id="64fbf-165">Registrarse para la prueba de Microsoft 365 E5 o usar la licencia completa si está ejecutando un piloto</span><span class="sxs-lookup"><span data-stu-id="64fbf-165">Sign up for Microsoft 365 E5 Trial or use your full license if you're running a pilot</span></span>
    -   <span data-ttu-id="64fbf-166">Configurar dominio</span><span class="sxs-lookup"><span data-stu-id="64fbf-166">Configure domain</span></span>
    -   <span data-ttu-id="64fbf-167">Asignar licencias de Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="64fbf-167">Assign Microsoft 365 E5 licenses</span></span>
    -   <span data-ttu-id="64fbf-168">Finalización del asistente para la instalación en el portal</span><span class="sxs-lookup"><span data-stu-id="64fbf-168">Completing the setup wizard within the portal</span></span>
-   <span data-ttu-id="64fbf-169">Configurar todos los pilares de Microsoft 365 Defender en función de los procedimientos recomendados</span><span class="sxs-lookup"><span data-stu-id="64fbf-169">Configure all Microsoft 365 Defender pillars based on best practices</span></span>
    -   <span data-ttu-id="64fbf-170">Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="64fbf-170">Microsoft Defender for Office 365</span></span>
    -   <span data-ttu-id="64fbf-171">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="64fbf-171">Microsoft Defender for Identity</span></span>
    -   <span data-ttu-id="64fbf-172">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="64fbf-172">Microsoft Cloud App Security</span></span>
    -   <span data-ttu-id="64fbf-173">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="64fbf-173">Microsoft Defender for Endpoint</span></span>

## <a name="out-of-scope"></a><span data-ttu-id="64fbf-174">Fuera de ámbito</span><span class="sxs-lookup"><span data-stu-id="64fbf-174">Out of scope</span></span>

<span data-ttu-id="64fbf-175">Los siguientes elementos están fuera del ámbito de esta guía de implementación:</span><span class="sxs-lookup"><span data-stu-id="64fbf-175">The following are out of scope of this deployment guide:</span></span>

-   <span data-ttu-id="64fbf-176">Configuración de soluciones de terceros que podrían integrarse con Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="64fbf-176">Configuration of third-party solutions that might integrate with Microsoft 365 Defender</span></span>
-   <span data-ttu-id="64fbf-177">Pruebas de penetración en entornos de producción</span><span class="sxs-lookup"><span data-stu-id="64fbf-177">Penetration testing in production environment</span></span>

## <a name="next-step"></a><span data-ttu-id="64fbf-178">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="64fbf-178">Next step</span></span>
<span data-ttu-id="64fbf-179">[Fase 1: Preparar](prepare-mtpeval.md) 
</span><span class="sxs-lookup"><span data-stu-id="64fbf-179">[Phase 1: Prepare](prepare-mtpeval.md) 
</span></span><br> <span data-ttu-id="64fbf-180">Preparar el entorno piloto o el laboratorio de prueba de Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="64fbf-180">Prepare your Microsoft 365 Defender trial lab or pilot environment</span></span>
