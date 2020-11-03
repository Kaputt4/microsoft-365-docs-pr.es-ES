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
ms.openlocfilehash: d6c96f7720344721bb2786dc130c490a5a8ea657
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846489"
---
# <a name="create-a-microsoft-365-defender-trial-lab-or-pilot-environment"></a><span data-ttu-id="90bb4-104">Crear un entorno piloto o un laboratorio de prueba de Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="90bb4-104">Create a Microsoft 365 Defender trial lab or pilot environment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="90bb4-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="90bb4-105">**Applies to:**</span></span>
- <span data-ttu-id="90bb4-106">Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="90bb4-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="90bb4-107">La finalidad de crear este entorno de prueba o un entorno piloto es ilustrar las capacidades completas e integradas de Microsoft 365 defender.</span><span class="sxs-lookup"><span data-stu-id="90bb4-107">The purpose of creating this trial lab or pilot environment is to illustrate the comprehensive and integrated Microsoft 365 Defender capabilities.</span></span> <span data-ttu-id="90bb4-108">Experimente cómo esta solución de seguridad inteligente detecta, evita, investiga automáticamente y responde a las amenazas avanzadas de su organización.</span><span class="sxs-lookup"><span data-stu-id="90bb4-108">Experience how this intelligent security solution detects, prevents, automatically investigates, and responds to advanced threats your organization.</span></span> 

<span data-ttu-id="90bb4-109">Esta guía le guiará por los pasos para iniciar la evaluación de Microsoft 365 defender en función de las rutas de implementación recomendadas.</span><span class="sxs-lookup"><span data-stu-id="90bb4-109">This guide takes you through the steps to start your Microsoft 365 Defender evaluation based on the recommended deployment paths.</span></span> <span data-ttu-id="90bb4-110">El objetivo es ayudarle a configurar la solución de seguridad, ya sea en un entorno de laboratorio con una cuenta de prueba o en un entorno piloto en producción con una licencia completa.</span><span class="sxs-lookup"><span data-stu-id="90bb4-110">The goal is to help you set up the security solution either in a lab environment with a trial account, or in a pilot environment in production with a full license.</span></span> <span data-ttu-id="90bb4-111">La preparación del entorno piloto o del laboratorio de pruebas puede ayudarle a presentar los casos de uso de la operación de seguridad a los responsables de la toma de decisiones de la organización.</span><span class="sxs-lookup"><span data-stu-id="90bb4-111">Preparing your trial lab or pilot environment can help you present security operation use cases to decision makers in your organization.</span></span> <span data-ttu-id="90bb4-112">Cuando haya terminado de ejecutar las simulaciones de ataque y esté satisfecho con los resultados, puede implementar y descargar por completo en su organización con la ayuda de profesionales de ventas técnicos de Microsoft o expertos de su organización.</span><span class="sxs-lookup"><span data-stu-id="90bb4-112">When you’re done running your attack simulations and are satisfied with the results, you can fully deploy and operationalize it in your organization with the help of Microsoft Technical Sales Professionals or experts in your organization.</span></span> 

<span data-ttu-id="90bb4-113">Esta guía le ayudará a:</span><span class="sxs-lookup"><span data-stu-id="90bb4-113">This guide will help you:</span></span>
- <span data-ttu-id="90bb4-114">Configurar el servidor y los equipos del laboratorio</span><span class="sxs-lookup"><span data-stu-id="90bb4-114">Set up your lab server and computers</span></span>
- <span data-ttu-id="90bb4-115">Configuración de Active Directory con usuarios y grupos</span><span class="sxs-lookup"><span data-stu-id="90bb4-115">Configure Active Directory with users and groups</span></span>
- <span data-ttu-id="90bb4-116">Instalación y configuración de Microsoft defender para identidad, Microsoft defender para Office 365, Microsoft defender para el Endpoint y Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="90bb4-116">Set up and configure Microsoft Defender for Identity, Microsoft Defender for Office 365, Microsoft Defender for Endpoint, and Microsoft Cloud App Security</span></span>
- <span data-ttu-id="90bb4-117">Configurar directivas locales para el servidor y los equipos</span><span class="sxs-lookup"><span data-stu-id="90bb4-117">Set up local policies for your server and computers</span></span>
- <span data-ttu-id="90bb4-118">Imitar un ataque de amenaza para generar una alerta o incidente de prueba en Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="90bb4-118">Mimic a threat attack to generate a test incident or alert in Microsoft 365 Defender</span></span>

>[!IMPORTANT]
><span data-ttu-id="90bb4-119">Para obtener resultados óptimos, siga las instrucciones de configuración del laboratorio tan cerca como sea posible.</span><span class="sxs-lookup"><span data-stu-id="90bb4-119">For optimum results, follow the lab setup instructions as closely as possible.</span></span>


## <a name="deployment-phases"></a><span data-ttu-id="90bb4-120">Fases de implementación</span><span class="sxs-lookup"><span data-stu-id="90bb4-120">Deployment phases</span></span>

<span data-ttu-id="90bb4-121">Hay tres fases para crear un entorno de laboratorio de prueba de Microsoft 365 defender e implementarlo:</span><span class="sxs-lookup"><span data-stu-id="90bb4-121">There are three phases in creating a Microsoft 365 Defender trial lab environment and deploying it:</span></span>

|<span data-ttu-id="90bb4-122">Fase</span><span class="sxs-lookup"><span data-stu-id="90bb4-122">Phase</span></span> | <span data-ttu-id="90bb4-123">Description</span><span class="sxs-lookup"><span data-stu-id="90bb4-123">Description</span></span> | 
|:-------|:-----|
| <span data-ttu-id="90bb4-124">![Fase 1: preparación](../../media/prepare.png)</span><span class="sxs-lookup"><span data-stu-id="90bb4-124">![Phase 1: Prepare](../../media/prepare.png)</span></span><br>[<span data-ttu-id="90bb4-125">Fase 1: preparación</span><span class="sxs-lookup"><span data-stu-id="90bb4-125">Phase 1: Prepare</span></span>](prepare-mtpeval.md)| <span data-ttu-id="90bb4-126">Obtenga información sobre lo que debe tener en cuenta al implementar Microsoft 365 defender en un laboratorio de pruebas o un entorno piloto:</span><span class="sxs-lookup"><span data-stu-id="90bb4-126">Learn what you need to consider when deploying Microsoft 365 Defender in a trial lab or pilot environment:</span></span> <br><br><span data-ttu-id="90bb4-127">-Partes interesadas y la firma</span><span class="sxs-lookup"><span data-stu-id="90bb4-127">- Stakeholders and sign-off</span></span> <br> <span data-ttu-id="90bb4-128">Consideraciones del entorno</span><span class="sxs-lookup"><span data-stu-id="90bb4-128">- Environment considerations</span></span> <br><span data-ttu-id="90bb4-129">Acceso a</span><span class="sxs-lookup"><span data-stu-id="90bb4-129">- Access</span></span> <br><span data-ttu-id="90bb4-130">-Instalación de Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="90bb4-130">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="90bb4-131">-Orden de configuración</span><span class="sxs-lookup"><span data-stu-id="90bb4-131">- Configuration order</span></span>
|  <span data-ttu-id="90bb4-132">![Fase 2: configuración](../../media/setup.png)</span><span class="sxs-lookup"><span data-stu-id="90bb4-132">![Phase 2: Setup](../../media/setup.png)</span></span> <br>[<span data-ttu-id="90bb4-133">Fase 2: configuración</span><span class="sxs-lookup"><span data-stu-id="90bb4-133">Phase 2: Setup</span></span>](setup-mtpeval.md)|  <span data-ttu-id="90bb4-134">Siga los pasos iniciales para acceder al centro de seguridad de Microsoft 365 para configurar el entorno piloto o el laboratorio de pruebas de Microsoft 365 defender.</span><span class="sxs-lookup"><span data-stu-id="90bb4-134">Take the initial steps to access Microsoft 365 Security Center to set up your Microsoft 365 Defender trial lab or pilot environment.</span></span> <span data-ttu-id="90bb4-135">Se le guiará a:</span><span class="sxs-lookup"><span data-stu-id="90bb4-135">You'll be guided to:</span></span><br><br><span data-ttu-id="90bb4-136">-Inscríbase en la versión de prueba de Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="90bb4-136">- Sign up for Microsoft 365 E5 Trial</span></span> <br>  <span data-ttu-id="90bb4-137">-Configurar dominio</span><span class="sxs-lookup"><span data-stu-id="90bb4-137">- Configure domain</span></span><br><span data-ttu-id="90bb4-138">-Asignar licencias de Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="90bb4-138">- Assign Microsoft 365 E5 licenses</span></span><br><span data-ttu-id="90bb4-139">-Completar el Asistente de configuración en el portal</span><span class="sxs-lookup"><span data-stu-id="90bb4-139">- Complete the setup wizard in the portal</span></span>|
|  <span data-ttu-id="90bb4-140">![Fase 3: configurar & incorporado](../../media/config-onboard.png)</span><span class="sxs-lookup"><span data-stu-id="90bb4-140">![Phase 3: Configure & Onboard](../../media/config-onboard.png)</span></span> <br>[<span data-ttu-id="90bb4-141">Fase 3: configurar & incorporado</span><span class="sxs-lookup"><span data-stu-id="90bb4-141">Phase 3: Configure & Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="90bb4-142">Configure cada uno de los puntos de conexión y los pilares de 365 defender de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="90bb4-142">Configure each Microsoft 365 Defender pillar and onboard endpoints.</span></span> <span data-ttu-id="90bb4-143">Se le guiará a:</span><span class="sxs-lookup"><span data-stu-id="90bb4-143">You'll be guided to:</span></span><br><br><span data-ttu-id="90bb4-144">-Configurar Microsoft defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="90bb4-144">- Configure Microsoft Defender for Office 365</span></span><br><span data-ttu-id="90bb4-145">-Configurar Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="90bb4-145">- Configure Microsoft Cloud App Security</span></span><br><span data-ttu-id="90bb4-146">-Configurar Microsoft defender para identidad</span><span class="sxs-lookup"><span data-stu-id="90bb4-146">- Configure Microsoft Defender for Identity</span></span><br><span data-ttu-id="90bb4-147">-Configurar Microsoft defender para el punto de conexión</span><span class="sxs-lookup"><span data-stu-id="90bb4-147">- Configure Microsoft Defender for Endpoint</span></span>


## <a name="in-scope"></a><span data-ttu-id="90bb4-148">En el ámbito</span><span class="sxs-lookup"><span data-stu-id="90bb4-148">In scope</span></span>

<span data-ttu-id="90bb4-149">Las siguientes tareas se encuentran en el ámbito de esta guía:</span><span class="sxs-lookup"><span data-stu-id="90bb4-149">The following tasks are in scope for this guide:</span></span>
-   <span data-ttu-id="90bb4-150">Configurar Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="90bb4-150">Set up Azure Active Directory</span></span>
-   <span data-ttu-id="90bb4-151">Configurar Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="90bb4-151">Set up Microsoft 365 Defender</span></span>
    -   <span data-ttu-id="90bb4-152">Regístrese en la versión de prueba de Microsoft 365 E5 o use su licencia completa si está ejecutando un piloto</span><span class="sxs-lookup"><span data-stu-id="90bb4-152">Sign up for Microsoft 365 E5 Trial or use your full license if you're running a pilot</span></span>
    -   <span data-ttu-id="90bb4-153">Configurar dominio</span><span class="sxs-lookup"><span data-stu-id="90bb4-153">Configure domain</span></span>
    -   <span data-ttu-id="90bb4-154">Asignar licencias de Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="90bb4-154">Assign Microsoft 365 E5 licenses</span></span>
    -   <span data-ttu-id="90bb4-155">Finalización del Asistente para la instalación en el portal</span><span class="sxs-lookup"><span data-stu-id="90bb4-155">Completing the setup wizard within the portal</span></span>
-   <span data-ttu-id="90bb4-156">Configurar todos los pilares de 365 defender de Microsoft según los procedimientos recomendados</span><span class="sxs-lookup"><span data-stu-id="90bb4-156">Configure all Microsoft 365 Defender pillars based on best practices</span></span>
    -   <span data-ttu-id="90bb4-157">Microsoft defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="90bb4-157">Microsoft Defender for Office 365</span></span>
    -   <span data-ttu-id="90bb4-158">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="90bb4-158">Microsoft Defender for Identity</span></span>
    -   <span data-ttu-id="90bb4-159">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="90bb4-159">Microsoft Cloud App Security</span></span>
    -   <span data-ttu-id="90bb4-160">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="90bb4-160">Microsoft Defender for Endpoint</span></span>

## <a name="out-of-scope"></a><span data-ttu-id="90bb4-161">Fuera de ámbito</span><span class="sxs-lookup"><span data-stu-id="90bb4-161">Out of scope</span></span>

<span data-ttu-id="90bb4-162">Las siguientes opciones están fuera del ámbito de esta guía de implementación:</span><span class="sxs-lookup"><span data-stu-id="90bb4-162">The following are out of scope of this deployment guide:</span></span>

-   <span data-ttu-id="90bb4-163">Configuración de soluciones de terceros que pueden integrarse con Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="90bb4-163">Configuration of third-party solutions that might integrate with Microsoft 365 Defender</span></span>
-   <span data-ttu-id="90bb4-164">Pruebas de penetración en el entorno de producción</span><span class="sxs-lookup"><span data-stu-id="90bb4-164">Penetration testing in production environment</span></span>

## <a name="next-step"></a><span data-ttu-id="90bb4-165">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="90bb4-165">Next step</span></span>
<span data-ttu-id="90bb4-166">![Fase 1: preparación](../../media/prepare.png)</span><span class="sxs-lookup"><span data-stu-id="90bb4-166">![Phase 1: Prepare](../../media/prepare.png)</span></span> <br><span data-ttu-id="90bb4-167">[Fase 1: preparación](prepare-mtpeval.md) 
</span><span class="sxs-lookup"><span data-stu-id="90bb4-167">[Phase 1: Prepare](prepare-mtpeval.md) 
</span></span><br> <span data-ttu-id="90bb4-168">Preparar el entorno piloto o el laboratorio de prueba de Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="90bb4-168">Prepare your Microsoft 365 Defender trial lab or pilot environment</span></span>
