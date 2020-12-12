---
title: Evalúe Microsoft 365 defender
description: Configure el entorno piloto o el laboratorio de prueba de Microsoft 365 defender para probar y experimentar la solución de seguridad diseñada para proteger los dispositivos, la identidad, los datos y las aplicaciones de su organización.
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
ms.openlocfilehash: 8504b036203e1f73dc9e0a0d79a228425fb88bfa
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659638"
---
# <a name="create-a-microsoft-365-defender-trial-lab-or-pilot-environment"></a><span data-ttu-id="1fe14-104">Crear un entorno piloto o un laboratorio de prueba de Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="1fe14-104">Create a Microsoft 365 Defender trial lab or pilot environment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="1fe14-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="1fe14-105">**Applies to:**</span></span>
- <span data-ttu-id="1fe14-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1fe14-106">Microsoft 365 Defender</span></span>


<span data-ttu-id="1fe14-107">Esta guía le ayudará a configurar un entorno de laboratorio con usuarios y grupos y, a continuación, le guiará a través de la configuración de las capacidades de Microsoft 365 defender para poder imitar un ataque de amenaza y obtener un resultado de prueba significativo.</span><span class="sxs-lookup"><span data-stu-id="1fe14-107">This guide helps you work across setting up a lab environment with users and groups, then guides you through the configuration of the capabilities in Microsoft 365 Defender so that you can mimic a threat attack and obtain a meaningful trial result.</span></span> 

<span data-ttu-id="1fe14-108">La finalidad de crear este entorno de prueba o un entorno piloto es ilustrar las capacidades completas e integradas de Microsoft 365 defender.</span><span class="sxs-lookup"><span data-stu-id="1fe14-108">The purpose of creating this trial lab or pilot environment is to illustrate the comprehensive and integrated Microsoft 365 Defender capabilities.</span></span> <span data-ttu-id="1fe14-109">Experimente cómo esta solución de seguridad inteligente detecta, evita, investiga automáticamente y responde a las amenazas avanzadas de su organización.</span><span class="sxs-lookup"><span data-stu-id="1fe14-109">Experience how this intelligent security solution detects, prevents, automatically investigates, and responds to advanced threats your organization.</span></span> 


<span data-ttu-id="1fe14-110">Se le guiará por los pasos para iniciar la evaluación de Microsoft 365 defender en función de las rutas de implementación recomendadas.</span><span class="sxs-lookup"><span data-stu-id="1fe14-110">You will be guided through the steps to start your Microsoft 365 Defender evaluation based on the recommended deployment paths.</span></span> <span data-ttu-id="1fe14-111">El objetivo es ayudarle a configurar la solución de seguridad, ya sea en un entorno de laboratorio con una cuenta de prueba o en un entorno piloto en producción con una licencia completa.</span><span class="sxs-lookup"><span data-stu-id="1fe14-111">The goal is to help you set up the security solution either in a lab environment with a trial account, or in a pilot environment in production with a full license.</span></span> <span data-ttu-id="1fe14-112">La preparación del entorno piloto o del laboratorio de pruebas puede ayudarle a presentar los casos de uso de la operación de seguridad a los responsables de la toma de decisiones de la organización.</span><span class="sxs-lookup"><span data-stu-id="1fe14-112">Preparing your trial lab or pilot environment can help you present security operation use cases to decision makers in your organization.</span></span> <span data-ttu-id="1fe14-113">Cuando haya terminado de ejecutar las simulaciones de ataque y esté satisfecho con los resultados, puede implementar y descargar por completo en su organización con la ayuda de profesionales de ventas técnicos de Microsoft o expertos de su organización.</span><span class="sxs-lookup"><span data-stu-id="1fe14-113">When you’re done running your attack simulations and are satisfied with the results, you can fully deploy and operationalize it in your organization with the help of Microsoft Technical Sales Professionals or experts in your organization.</span></span> 

<span data-ttu-id="1fe14-114">Esta guía le ayudará a:</span><span class="sxs-lookup"><span data-stu-id="1fe14-114">This guide will help you:</span></span>
- <span data-ttu-id="1fe14-115">Configurar el servidor y los equipos del laboratorio</span><span class="sxs-lookup"><span data-stu-id="1fe14-115">Set up your lab server and computers</span></span>
- <span data-ttu-id="1fe14-116">Configuración de Active Directory con usuarios y grupos</span><span class="sxs-lookup"><span data-stu-id="1fe14-116">Configure Active Directory with users and groups</span></span>
- <span data-ttu-id="1fe14-117">Instalación y configuración de Microsoft defender para identidad, Microsoft defender para Office 365, Microsoft defender para el Endpoint y Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="1fe14-117">Set up and configure Microsoft Defender for Identity, Microsoft Defender for Office 365, Microsoft Defender for Endpoint, and Microsoft Cloud App Security</span></span>
- <span data-ttu-id="1fe14-118">Configurar directivas locales para el servidor y los equipos</span><span class="sxs-lookup"><span data-stu-id="1fe14-118">Set up local policies for your server and computers</span></span>
- <span data-ttu-id="1fe14-119">Imitar un ataque de amenaza para generar una alerta o incidente de prueba en Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="1fe14-119">Mimic a threat attack to generate a test incident or alert in Microsoft 365 Defender</span></span>

>[!IMPORTANT]
><span data-ttu-id="1fe14-120">Para obtener resultados óptimos, siga las instrucciones de configuración del laboratorio tan cerca como sea posible.</span><span class="sxs-lookup"><span data-stu-id="1fe14-120">For optimum results, follow the lab setup instructions as closely as possible.</span></span>


## <a name="deployment-phases"></a><span data-ttu-id="1fe14-121">Fases de implementación</span><span class="sxs-lookup"><span data-stu-id="1fe14-121">Deployment phases</span></span>

<span data-ttu-id="1fe14-122">Hay tres fases para la creación de un entorno de prueba de Microsoft 365 defender.</span><span class="sxs-lookup"><span data-stu-id="1fe14-122">There are three phases in creating a Microsoft 365 Defender trial lab environment.</span></span>

![Fases de implementación: preparación, configuración, incorporación](../../media/evaluation-guide-phases.png)

|<span data-ttu-id="1fe14-124">Fase</span><span class="sxs-lookup"><span data-stu-id="1fe14-124">Phase</span></span> | <span data-ttu-id="1fe14-125">Description</span><span class="sxs-lookup"><span data-stu-id="1fe14-125">Description</span></span> | 
|:-------|:-----|
|[<span data-ttu-id="1fe14-126">Fase 1: preparación</span><span class="sxs-lookup"><span data-stu-id="1fe14-126">Phase 1: Prepare</span></span>](prepare-mtpeval.md)| <span data-ttu-id="1fe14-127">Obtenga información sobre lo que debe tener en cuenta al implementar Microsoft 365 defender en un laboratorio de pruebas o un entorno piloto:</span><span class="sxs-lookup"><span data-stu-id="1fe14-127">Learn what you need to consider when deploying Microsoft 365 Defender in a trial lab or pilot environment:</span></span> <br><br><span data-ttu-id="1fe14-128">-Partes interesadas y la firma</span><span class="sxs-lookup"><span data-stu-id="1fe14-128">- Stakeholders and sign-off</span></span> <br> <span data-ttu-id="1fe14-129">Consideraciones del entorno</span><span class="sxs-lookup"><span data-stu-id="1fe14-129">- Environment considerations</span></span> <br><span data-ttu-id="1fe14-130">Acceso a</span><span class="sxs-lookup"><span data-stu-id="1fe14-130">- Access</span></span> <br><span data-ttu-id="1fe14-131">-Instalación de Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="1fe14-131">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="1fe14-132">-Orden de configuración</span><span class="sxs-lookup"><span data-stu-id="1fe14-132">- Configuration order</span></span>
|[<span data-ttu-id="1fe14-133">Fase 2: configuración</span><span class="sxs-lookup"><span data-stu-id="1fe14-133">Phase 2: Setup</span></span>](setup-mtpeval.md)|  <span data-ttu-id="1fe14-134">Siga los pasos iniciales para acceder al centro de seguridad de Microsoft 365 para configurar el entorno piloto o el laboratorio de pruebas de Microsoft 365 defender.</span><span class="sxs-lookup"><span data-stu-id="1fe14-134">Take the initial steps to access Microsoft 365 Security Center to set up your Microsoft 365 Defender trial lab or pilot environment.</span></span> <span data-ttu-id="1fe14-135">Se le guiará a:</span><span class="sxs-lookup"><span data-stu-id="1fe14-135">You'll be guided to:</span></span><br><br><span data-ttu-id="1fe14-136">-Inscríbase en la versión de prueba de Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="1fe14-136">- Sign up for Microsoft 365 E5 Trial</span></span> <br>  <span data-ttu-id="1fe14-137">-Configurar dominio</span><span class="sxs-lookup"><span data-stu-id="1fe14-137">- Configure domain</span></span><br><span data-ttu-id="1fe14-138">-Asignar licencias de Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="1fe14-138">- Assign Microsoft 365 E5 licenses</span></span><br><span data-ttu-id="1fe14-139">-Completar el Asistente de configuración en el portal</span><span class="sxs-lookup"><span data-stu-id="1fe14-139">- Complete the setup wizard in the portal</span></span>|
|[<span data-ttu-id="1fe14-140">Fase 3: configurar & incorporado</span><span class="sxs-lookup"><span data-stu-id="1fe14-140">Phase 3: Configure & Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="1fe14-141">Configure cada uno de los puntos de conexión y los pilares de 365 defender de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1fe14-141">Configure each Microsoft 365 Defender pillar and onboard endpoints.</span></span> <span data-ttu-id="1fe14-142">Se le guiará a:</span><span class="sxs-lookup"><span data-stu-id="1fe14-142">You'll be guided to:</span></span><br><br><span data-ttu-id="1fe14-143">-Configurar Microsoft defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="1fe14-143">- Configure Microsoft Defender for Office 365</span></span><br><span data-ttu-id="1fe14-144">-Configurar Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="1fe14-144">- Configure Microsoft Cloud App Security</span></span><br><span data-ttu-id="1fe14-145">-Configurar Microsoft defender para identidad</span><span class="sxs-lookup"><span data-stu-id="1fe14-145">- Configure Microsoft Defender for Identity</span></span><br><span data-ttu-id="1fe14-146">-Configurar Microsoft defender para el punto de conexión</span><span class="sxs-lookup"><span data-stu-id="1fe14-146">- Configure Microsoft Defender for Endpoint</span></span>


<span data-ttu-id="1fe14-147">Una vez completada esta guía, habría identificado a las partes interesadas y las aprobaciones obligatorias, tener los permisos de acceso correctos, registrarse para la prueba, los dominios configurados y los pilares de 365 defender, y los puntos de conexión se incorporarán al servicio.</span><span class="sxs-lookup"><span data-stu-id="1fe14-147">After you've completed this guide, you would have identified the stakeholders involved and the required approvals,  have the right access permissions, signed up for trial, configured domains and each of the Microsoft 365 Defender pillars, and your endpoints will be onboarded to the service.</span></span>

## <a name="key-capabilities"></a><span data-ttu-id="1fe14-148">Principales funcionalidades</span><span class="sxs-lookup"><span data-stu-id="1fe14-148">Key capabilities</span></span>

<span data-ttu-id="1fe14-149">Mientras que Microsoft 365 defender proporciona muchas capacidades, el objetivo principal de esta guía de implementación es conseguir que comience por los dispositivos de incorporación.</span><span class="sxs-lookup"><span data-stu-id="1fe14-149">While Microsoft 365 Defender provides many capabilities, the primary purpose of this deployment guide is to get you started by onboarding devices.</span></span> <span data-ttu-id="1fe14-150">Además de la incorporación, esta guía le ayuda a comenzar con las siguientes funciones.</span><span class="sxs-lookup"><span data-stu-id="1fe14-150">In addition to onboarding, this guidance gets you started with the following capabilities.</span></span>


<span data-ttu-id="1fe14-151">Funcionalidad</span><span class="sxs-lookup"><span data-stu-id="1fe14-151">Capability</span></span> | <span data-ttu-id="1fe14-152">Descripción</span><span class="sxs-lookup"><span data-stu-id="1fe14-152">Description</span></span> 
:---|:---
<span data-ttu-id="1fe14-153">Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="1fe14-153">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="1fe14-154">Ayuda a proteger todo el envrionment de Office 365 de las amenazas actuales</span><span class="sxs-lookup"><span data-stu-id="1fe14-154">Helps protect your entire Office 365 envrionment from today's threats</span></span>
<span data-ttu-id="1fe14-155">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="1fe14-155">Microsoft Defender for Identity</span></span> | <span data-ttu-id="1fe14-156">Identifica y detecta amenazas para las identidades en peligro y las acciones de Insider malintencionadas.</span><span class="sxs-lookup"><span data-stu-id="1fe14-156">Identifies and detects  threats on compromised identities and malicious insider actions.</span></span>
<span data-ttu-id="1fe14-157">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="1fe14-157">Microsoft Cloud App Security</span></span> | <span data-ttu-id="1fe14-158">Proporciona una gran visibilidad, controla el desplazamiento de datos y detecta ciberamenazas a través de los servicios en la nube.</span><span class="sxs-lookup"><span data-stu-id="1fe14-158">Provides rich visibility, control data travel, and detect cyberthreats across cloud services.</span></span>
<span data-ttu-id="1fe14-159">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="1fe14-159">Microsoft Defender for Endpoint</span></span> | <span data-ttu-id="1fe14-160">Evita, detecta y proporciona funciones de respuesta a amenazas avanzadas con una completa seguridad de los extremos.</span><span class="sxs-lookup"><span data-stu-id="1fe14-160">Prevents, detects, and provides response capabilities to advanced threats with comprehensive endpoint security.</span></span>


## <a name="in-scope"></a><span data-ttu-id="1fe14-161">En el ámbito</span><span class="sxs-lookup"><span data-stu-id="1fe14-161">In scope</span></span>

<span data-ttu-id="1fe14-162">Las siguientes tareas se encuentran en el ámbito de esta guía:</span><span class="sxs-lookup"><span data-stu-id="1fe14-162">The following tasks are in scope for this guide:</span></span>
-   <span data-ttu-id="1fe14-163">Configurar Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="1fe14-163">Set up Azure Active Directory</span></span>
-   <span data-ttu-id="1fe14-164">Configurar Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="1fe14-164">Set up Microsoft 365 Defender</span></span>
    -   <span data-ttu-id="1fe14-165">Regístrese en la versión de prueba de Microsoft 365 E5 o use su licencia completa si está ejecutando un piloto</span><span class="sxs-lookup"><span data-stu-id="1fe14-165">Sign up for Microsoft 365 E5 Trial or use your full license if you're running a pilot</span></span>
    -   <span data-ttu-id="1fe14-166">Configurar dominio</span><span class="sxs-lookup"><span data-stu-id="1fe14-166">Configure domain</span></span>
    -   <span data-ttu-id="1fe14-167">Asignar licencias de Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="1fe14-167">Assign Microsoft 365 E5 licenses</span></span>
    -   <span data-ttu-id="1fe14-168">Finalización del Asistente para la instalación en el portal</span><span class="sxs-lookup"><span data-stu-id="1fe14-168">Completing the setup wizard within the portal</span></span>
-   <span data-ttu-id="1fe14-169">Configurar todos los pilares de 365 defender de Microsoft según los procedimientos recomendados</span><span class="sxs-lookup"><span data-stu-id="1fe14-169">Configure all Microsoft 365 Defender pillars based on best practices</span></span>
    -   <span data-ttu-id="1fe14-170">Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="1fe14-170">Microsoft Defender for Office 365</span></span>
    -   <span data-ttu-id="1fe14-171">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="1fe14-171">Microsoft Defender for Identity</span></span>
    -   <span data-ttu-id="1fe14-172">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="1fe14-172">Microsoft Cloud App Security</span></span>
    -   <span data-ttu-id="1fe14-173">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="1fe14-173">Microsoft Defender for Endpoint</span></span>

## <a name="out-of-scope"></a><span data-ttu-id="1fe14-174">Fuera de ámbito</span><span class="sxs-lookup"><span data-stu-id="1fe14-174">Out of scope</span></span>

<span data-ttu-id="1fe14-175">Las siguientes opciones están fuera del ámbito de esta guía de implementación:</span><span class="sxs-lookup"><span data-stu-id="1fe14-175">The following are out of scope of this deployment guide:</span></span>

-   <span data-ttu-id="1fe14-176">Configuración de soluciones de terceros que pueden integrarse con Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="1fe14-176">Configuration of third-party solutions that might integrate with Microsoft 365 Defender</span></span>
-   <span data-ttu-id="1fe14-177">Pruebas de penetración en el entorno de producción</span><span class="sxs-lookup"><span data-stu-id="1fe14-177">Penetration testing in production environment</span></span>

## <a name="next-step"></a><span data-ttu-id="1fe14-178">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="1fe14-178">Next step</span></span>
<span data-ttu-id="1fe14-179">[Fase 1: preparación](prepare-mtpeval.md) 
</span><span class="sxs-lookup"><span data-stu-id="1fe14-179">[Phase 1: Prepare](prepare-mtpeval.md) 
</span></span><br> <span data-ttu-id="1fe14-180">Preparar el entorno piloto o el laboratorio de prueba de Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="1fe14-180">Prepare your Microsoft 365 Defender trial lab or pilot environment</span></span>
