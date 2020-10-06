---
title: Evaluar la Protección contra amenazas de Microsoft
description: Configure el entorno piloto o el laboratorio de pruebas de Microsoft Threat Protection para probar cómo la solución coordinada de protección contra amenazas diseñada para proteger los dispositivos, la identidad, los datos y las aplicaciones puede ayudar a su organización
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
- m365solution-evalutatemtp
ms.topic: conceptual
ms.openlocfilehash: 3768937fc882fee8d6a744e4fb504095882c7e81
ms.sourcegitcommit: 9d8d071659e662c266b101377e24549963e43fef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2020
ms.locfileid: "48368064"
---
# <a name="create-a-microsoft-threat-protection-trial-lab-or-pilot-environment"></a><span data-ttu-id="4342d-104">Crear un entorno piloto o un laboratorio de prueba de Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="4342d-104">Create a Microsoft Threat Protection trial lab or pilot environment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="4342d-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="4342d-105">**Applies to:**</span></span>
- <span data-ttu-id="4342d-106">Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="4342d-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="4342d-107">La finalidad de crear este entorno de prueba o un entorno piloto es ilustrar las capacidades completas, integradas e inteligentes de la protección contra amenazas de Microsoft en detección, prevención, investigación y respuesta que puede usar en su organización.</span><span class="sxs-lookup"><span data-stu-id="4342d-107">The purpose of creating this trial lab or pilot environment is to illustrate the comprehensive, integrated, and intelligent capabilities of Microsoft Threat Protection in detection, prevention, investigation, and response that you can use in your organization.</span></span> 

<span data-ttu-id="4342d-108">Esta guía le guiará por los pasos necesarios para iniciar la evaluación de Microsoft Threat Protection en función de las rutas de implementación recomendadas.</span><span class="sxs-lookup"><span data-stu-id="4342d-108">This guide takes you through the steps to start your Microsoft Threat Protection evaluation based on the recommended deployment paths.</span></span> <span data-ttu-id="4342d-109">El objetivo es ayudarle a configurar los servicios integrados de protección contra amenazas de Microsoft en un entorno de laboratorio cuando use una cuenta de prueba o en un entorno piloto en producción cuando use una licencia completa.</span><span class="sxs-lookup"><span data-stu-id="4342d-109">The goal is to help you set up the integrated Microsoft Threat Protection services in a lab environment when using a trial account, or in a pilot environment in production when using a full license.</span></span> <span data-ttu-id="4342d-110">Cuyos resultados serán útiles para presentar los casos de uso de las operaciones de seguridad a los responsables de la toma de decisiones de soluciones de seguridad de la organización.</span><span class="sxs-lookup"><span data-stu-id="4342d-110">The results of which will be useful in presenting security operation use cases to security solution decision makers in your organization.</span></span> <span data-ttu-id="4342d-111">Una vez que haya terminado de ejecutar las simulaciones de ataque y esté satisfecho con los resultados, puede implementar y operar por completo en su organización con la ayuda de profesionales de ventas técnicos de Microsoft o expertos de su organización.</span><span class="sxs-lookup"><span data-stu-id="4342d-111">When you’re done running your attack simulations, and are satisfied with the results, you can fully deploy and operationalize it in your organization with the help of Microsoft Technical Sales Professionals or experts in your organization.</span></span> 

<span data-ttu-id="4342d-112">Esta guía le ayudará a:</span><span class="sxs-lookup"><span data-stu-id="4342d-112">This guide will help you:</span></span>
- <span data-ttu-id="4342d-113">Configurar el servidor y los equipos del laboratorio</span><span class="sxs-lookup"><span data-stu-id="4342d-113">Set up your lab server and computers</span></span>
- <span data-ttu-id="4342d-114">Configuración de Active Directory con usuarios y grupos</span><span class="sxs-lookup"><span data-stu-id="4342d-114">Configure Active Directory with users and groups</span></span>
- <span data-ttu-id="4342d-115">Configurar y configurar ATP de Azure, ATP de Office, ATP de Microsoft defender y Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="4342d-115">Set up and configure Azure ATP, Office ATP, Microsoft Defender ATP, and Microsoft Cloud App Security</span></span>
- <span data-ttu-id="4342d-116">Configurar directivas locales para el servidor y los equipos</span><span class="sxs-lookup"><span data-stu-id="4342d-116">Set up local policies for your server and computers</span></span>
- <span data-ttu-id="4342d-117">Imitar un ataque de amenaza para generar una alerta o incidente de prueba en la protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="4342d-117">Mimic a threat attack to generate a test incident or alert in Microsoft Threat Protection</span></span>

>[!IMPORTANT]
><span data-ttu-id="4342d-118">Para obtener resultados óptimos, siga las instrucciones de configuración del laboratorio tan cerca como sea posible.</span><span class="sxs-lookup"><span data-stu-id="4342d-118">For optimum results, follow the lab setup instructions as closely as possible.</span></span>


## <a name="deployment-phases"></a><span data-ttu-id="4342d-119">Fases de implementación</span><span class="sxs-lookup"><span data-stu-id="4342d-119">Deployment phases</span></span>

<span data-ttu-id="4342d-120">Hay tres fases para la creación de un entorno de laboratorio de prueba de Microsoft Threat Protection y su implementación:</span><span class="sxs-lookup"><span data-stu-id="4342d-120">There are three phases in creating a Microsoft Threat Protection trial lab environment and deploying it:</span></span>

|<span data-ttu-id="4342d-121">Fase</span><span class="sxs-lookup"><span data-stu-id="4342d-121">Phase</span></span> | <span data-ttu-id="4342d-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="4342d-122">Description</span></span> | 
|:-------|:-----|
| <span data-ttu-id="4342d-123">![Fase 1: preparación](../../media/prepare.png)</span><span class="sxs-lookup"><span data-stu-id="4342d-123">![Phase 1: Prepare](../../media/prepare.png)</span></span><br>[<span data-ttu-id="4342d-124">Fase 1: preparación</span><span class="sxs-lookup"><span data-stu-id="4342d-124">Phase 1: Prepare</span></span>](prepare-mtpeval.md)| <span data-ttu-id="4342d-125">Obtenga información sobre lo que debe tener en cuenta al implementar la protección contra amenazas de Microsoft en un laboratorio de pruebas o un entorno piloto:</span><span class="sxs-lookup"><span data-stu-id="4342d-125">Learn what you need to consider when deploying Microsoft Threat Protection in a trial lab or pilot environment:</span></span> <br><br><span data-ttu-id="4342d-126">-Partes interesadas y la firma</span><span class="sxs-lookup"><span data-stu-id="4342d-126">- Stakeholders and sign-off</span></span> <br> <span data-ttu-id="4342d-127">Consideraciones del entorno</span><span class="sxs-lookup"><span data-stu-id="4342d-127">- Environment considerations</span></span> <br><span data-ttu-id="4342d-128">Acceso a</span><span class="sxs-lookup"><span data-stu-id="4342d-128">- Access</span></span> <br><span data-ttu-id="4342d-129">-Instalación de Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="4342d-129">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="4342d-130">-Orden de configuración</span><span class="sxs-lookup"><span data-stu-id="4342d-130">- Configuration order</span></span>
|  <span data-ttu-id="4342d-131">![Fase 2: configuración](../../media/setup.png)</span><span class="sxs-lookup"><span data-stu-id="4342d-131">![Phase 2: Setup](../../media/setup.png)</span></span> <br>[<span data-ttu-id="4342d-132">Fase 2: configuración</span><span class="sxs-lookup"><span data-stu-id="4342d-132">Phase 2: Setup</span></span>](setup-mtpeval.md)|  <span data-ttu-id="4342d-133">Siga los pasos iniciales para acceder al centro de seguridad de Microsoft 365 para configurar el entorno piloto o el laboratorio de pruebas de Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="4342d-133">Take the initial steps to access Microsoft 365 Security Center to set up your Microsoft Threat Protection trial lab or pilot environment.</span></span> <span data-ttu-id="4342d-134">Se le guiará a:</span><span class="sxs-lookup"><span data-stu-id="4342d-134">You'll be guided to:</span></span><br><br><span data-ttu-id="4342d-135">-Inscríbase en la versión de prueba de Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="4342d-135">- Sign up for Microsoft 365 E5 Trial</span></span> <br>  <span data-ttu-id="4342d-136">-Configurar dominio</span><span class="sxs-lookup"><span data-stu-id="4342d-136">- Configure domain</span></span><br><span data-ttu-id="4342d-137">-Asignar licencias de Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="4342d-137">- Assign Microsoft 365 E5 licenses</span></span><br><span data-ttu-id="4342d-138">-Completar el Asistente de configuración en el portal</span><span class="sxs-lookup"><span data-stu-id="4342d-138">- Complete the setup wizard in the portal</span></span>|
|  <span data-ttu-id="4342d-139">![Fase 3: configurar & incorporado](../../media/config-onboard.png)</span><span class="sxs-lookup"><span data-stu-id="4342d-139">![Phase 3: Configure & Onboard](../../media/config-onboard.png)</span></span> <br>[<span data-ttu-id="4342d-140">Fase 3: configurar & incorporado</span><span class="sxs-lookup"><span data-stu-id="4342d-140">Phase 3: Configure & Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="4342d-141">Configure cada uno de los extremos incorporados y de la protección contra amenazas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4342d-141">Configure each Microsoft Threat Protection pillar and onboard endpoints.</span></span> <span data-ttu-id="4342d-142">Se le guiará a:</span><span class="sxs-lookup"><span data-stu-id="4342d-142">You'll be guided to:</span></span><br><br><span data-ttu-id="4342d-143">-Configurar la protección contra amenazas avanzada de Office 365</span><span class="sxs-lookup"><span data-stu-id="4342d-143">- Configure Office 365 Advanced Threat Protection</span></span><br><span data-ttu-id="4342d-144">-Configurar Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="4342d-144">- Configure Microsoft Cloud App Security</span></span><br><span data-ttu-id="4342d-145">-Configurar la protección contra amenazas avanzada de Azure</span><span class="sxs-lookup"><span data-stu-id="4342d-145">- Configure Azure Advanced Threat Protection</span></span><br><span data-ttu-id="4342d-146">-Configurar la protección contra amenazas avanzada de Microsoft defender</span><span class="sxs-lookup"><span data-stu-id="4342d-146">- Configure Microsoft Defender Advanced Threat Protection</span></span> 


## <a name="in-scope"></a><span data-ttu-id="4342d-147">En el ámbito</span><span class="sxs-lookup"><span data-stu-id="4342d-147">In scope</span></span>

<span data-ttu-id="4342d-148">Las siguientes tareas se encuentran en el ámbito de esta guía:</span><span class="sxs-lookup"><span data-stu-id="4342d-148">The following tasks are in scope for this guide:</span></span>
-   <span data-ttu-id="4342d-149">Configurar Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="4342d-149">Set up Azure Active Directory</span></span>
-   <span data-ttu-id="4342d-150">Configuración de la protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="4342d-150">Set up Microsoft Threat Protection</span></span>
    -   <span data-ttu-id="4342d-151">Regístrese en la versión de prueba de Microsoft 365 E5 o use su licencia completa si está ejecutando un piloto</span><span class="sxs-lookup"><span data-stu-id="4342d-151">Sign up for Microsoft 365 E5 Trial or use your full license if you're running a pilot</span></span>
    -   <span data-ttu-id="4342d-152">Configurar dominio</span><span class="sxs-lookup"><span data-stu-id="4342d-152">Configure domain</span></span>
    -   <span data-ttu-id="4342d-153">Asignar licencias de Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="4342d-153">Assign Microsoft 365 E5 licenses</span></span>
    -   <span data-ttu-id="4342d-154">Finalización del Asistente para la instalación en el portal</span><span class="sxs-lookup"><span data-stu-id="4342d-154">Completing the setup wizard within the portal</span></span>
-   <span data-ttu-id="4342d-155">Configurar todos los pilares de la protección contra amenazas de Microsoft según los procedimientos recomendados</span><span class="sxs-lookup"><span data-stu-id="4342d-155">Configure all Microsoft Threat Protection pillars based on best practices</span></span>
    -   <span data-ttu-id="4342d-156">Protección contra amenazas avanzada de Office 365</span><span class="sxs-lookup"><span data-stu-id="4342d-156">Office 365 Advanced Threat Protection</span></span>
    -   <span data-ttu-id="4342d-157">Azure Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="4342d-157">Azure Advanced Threat Protection</span></span>
    -   <span data-ttu-id="4342d-158">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="4342d-158">Microsoft Cloud App Security</span></span>
    -   <span data-ttu-id="4342d-159">Protección contra amenazas avanzada de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="4342d-159">Microsoft Defender Advanced Threat Protection</span></span>

## <a name="out-of-scope"></a><span data-ttu-id="4342d-160">Fuera de ámbito</span><span class="sxs-lookup"><span data-stu-id="4342d-160">Out of scope</span></span>

<span data-ttu-id="4342d-161">Las siguientes opciones están fuera del ámbito de esta guía de implementación:</span><span class="sxs-lookup"><span data-stu-id="4342d-161">The following are out of scope of this deployment guide:</span></span>

-   <span data-ttu-id="4342d-162">Configuración de soluciones de terceros que pueden integrarse con la protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="4342d-162">Configuration of third-party solutions that might integrate with Microsoft Threat Protection</span></span>
-   <span data-ttu-id="4342d-163">Pruebas de penetración en el entorno de producción</span><span class="sxs-lookup"><span data-stu-id="4342d-163">Penetration testing in production environment</span></span>

## <a name="next-step"></a><span data-ttu-id="4342d-164">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="4342d-164">Next step</span></span>
<span data-ttu-id="4342d-165">![Fase 1: preparación](../../media/prepare.png)</span><span class="sxs-lookup"><span data-stu-id="4342d-165">![Phase 1: Prepare](../../media/prepare.png)</span></span> <br><span data-ttu-id="4342d-166">[Fase 1: preparación](prepare-mtpeval.md) 
</span><span class="sxs-lookup"><span data-stu-id="4342d-166">[Phase 1: Prepare](prepare-mtpeval.md) 
</span></span><br> <span data-ttu-id="4342d-167">Preparar el entorno piloto o el laboratorio de pruebas de Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="4342d-167">Prepare your Microsoft Threat Protection trial lab or pilot environment</span></span>
