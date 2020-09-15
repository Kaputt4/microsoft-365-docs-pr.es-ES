---
title: Evaluar la Protección contra amenazas de Microsoft
description: Configure el entorno de prueba de la protección contra amenazas de Microsoft para probar cómo la solución coordinada de protección contra amenazas diseñada para proteger dispositivos, identidades, datos y aplicaciones puede ayudar a su organización
keywords: Microsoft Threat Protection Trial, pruebe la protección contra amenazas de Microsoft, evalúe Microsoft Threat Protection, Microsoft Threat Protection Evaluation Lab, Cyber Security, la seguridad persistente avanzada, seguridad empresarial, dispositivos, dispositivo, identidad, usuarios, datos, aplicaciones, incidentes, investigación automatizada y corrección, búsqueda avanzada
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
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.openlocfilehash: a9d7b514aac8d1a769c0dabf6dcdb54f4bcb447b
ms.sourcegitcommit: 9a275a13af3e063e80ce1bd3cd8142a095db92d2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2020
ms.locfileid: "47649966"
---
# <a name="create-a-microsoft-threat-protection-trial-lab-environment"></a><span data-ttu-id="79566-104">Crear un entorno de laboratorio de prueba de Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="79566-104">Create a Microsoft Threat Protection trial lab environment</span></span> 

<span data-ttu-id="79566-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="79566-105">**Applies to:**</span></span>
- <span data-ttu-id="79566-106">Protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="79566-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="79566-107">El propósito de crear este entorno de laboratorio de prueba es ilustrar las capacidades completas, integradas e inteligentes de la protección contra amenazas de Microsoft en detección, prevención, investigación y respuesta que puede usar en su organización.</span><span class="sxs-lookup"><span data-stu-id="79566-107">The purpose of creating this trial lab environment is to illustrate the comprehensive, integrated, and intelligent capabilities of Microsoft Threat Protection in detection, prevention, investigation, and response that you can use in your organization.</span></span> 

<span data-ttu-id="79566-108">Esta guía le guiará por los pasos necesarios para iniciar la evaluación de Microsoft Threat Protection en función de las rutas de implementación recomendadas.</span><span class="sxs-lookup"><span data-stu-id="79566-108">This guide takes you through the steps to start your Microsoft Threat Protection evaluation based on the recommended deployment paths.</span></span> <span data-ttu-id="79566-109">El objetivo es ayudarle a configurar los servicios integrados de protección contra amenazas de Microsoft en un entorno de laboratorio o como una prueba de concepto (POC) cuando se presentan a los responsables de las decisiones de las soluciones de seguridad de la organización.</span><span class="sxs-lookup"><span data-stu-id="79566-109">The goal is to help you set up the integrated Microsoft Threat Protection services in a lab environment or as a proof of concept (POC) when presenting to security solution decision makers in your organization.</span></span> <span data-ttu-id="79566-110">Cuando haya terminado de ejecutar las simulaciones de ataque, la investigación y la respuesta automatizadas, y que estén satisfechos con los resultados, puede implementarla en su entorno de producción con la ayuda de profesionales de ventas técnicos de Microsoft o expertos de su organización.</span><span class="sxs-lookup"><span data-stu-id="79566-110">When you’re done running your attack simulations, automated investigation and response, and are satisfied with the results, you can deploy it in your production environment with the help of Microsoft Technical Sales Professionals or experts in your organization.</span></span> 

<span data-ttu-id="79566-111">Esta guía le ayudará a:</span><span class="sxs-lookup"><span data-stu-id="79566-111">This guide will help you:</span></span>
- <span data-ttu-id="79566-112">Configurar el servidor y los equipos del laboratorio</span><span class="sxs-lookup"><span data-stu-id="79566-112">Set up your lab server and computers</span></span>
- <span data-ttu-id="79566-113">Configuración de Active Directory con usuarios y grupos</span><span class="sxs-lookup"><span data-stu-id="79566-113">Configure Active Directory with users and groups</span></span>
- <span data-ttu-id="79566-114">Configurar y configurar ATP de Azure, ATP de Office, ATP de Microsoft defender y Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="79566-114">Set up and configure Azure ATP, Office ATP, Microsoft Defender ATP, and Microsoft Cloud App Security</span></span>
- <span data-ttu-id="79566-115">Configurar directivas locales para el servidor y los equipos</span><span class="sxs-lookup"><span data-stu-id="79566-115">Setup local policies for your server and computers</span></span>
- <span data-ttu-id="79566-116">Imitar un ataque de amenaza para generar una alerta o incidente de prueba en la protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="79566-116">Mimic a threat attack to generate a test incident or alert in Microsoft Threat Protection</span></span>

>[!IMPORTANT]
><span data-ttu-id="79566-117">Para obtener resultados óptimos, siga las instrucciones de configuración del laboratorio tan cerca como sea posible.</span><span class="sxs-lookup"><span data-stu-id="79566-117">For optimum results, follow the lab setup instructions as closely as possible.</span></span>


## <a name="deployment-phases"></a><span data-ttu-id="79566-118">Fases de implementación</span><span class="sxs-lookup"><span data-stu-id="79566-118">Deployment phases</span></span>

<span data-ttu-id="79566-119">Hay tres fases para la creación de un entorno de laboratorio de prueba de Microsoft Threat Protection y su implementación:</span><span class="sxs-lookup"><span data-stu-id="79566-119">There are three phases in creating a Microsoft Threat Protection trial lab environment and deploying it:</span></span>

|<span data-ttu-id="79566-120">Fase</span><span class="sxs-lookup"><span data-stu-id="79566-120">Phase</span></span> | <span data-ttu-id="79566-121">Description</span><span class="sxs-lookup"><span data-stu-id="79566-121">Description</span></span> | 
|:-------|:-----|
| <span data-ttu-id="79566-122">![Fase 1: preparación](../../media/prepare.png)</span><span class="sxs-lookup"><span data-stu-id="79566-122">![Phase 1: Prepare](../../media/prepare.png)</span></span><br>[<span data-ttu-id="79566-123">Fase 1: preparación</span><span class="sxs-lookup"><span data-stu-id="79566-123">Phase 1: Prepare</span></span>](prepare-mtpeval.md)| <span data-ttu-id="79566-124">Obtenga información sobre lo que debe tener en cuenta al implementar la protección contra amenazas de Microsoft en un entorno de prueba de pruebas:</span><span class="sxs-lookup"><span data-stu-id="79566-124">Learn what you need to consider when deploying Microsoft Threat Protection in a trial lab environment:</span></span> <br><br><span data-ttu-id="79566-125">-Partes interesadas y la firma</span><span class="sxs-lookup"><span data-stu-id="79566-125">- Stakeholders and sign-off</span></span> <br> <span data-ttu-id="79566-126">Consideraciones del entorno</span><span class="sxs-lookup"><span data-stu-id="79566-126">- Environment considerations</span></span> <br><span data-ttu-id="79566-127">Acceso a</span><span class="sxs-lookup"><span data-stu-id="79566-127">- Access</span></span> <br><span data-ttu-id="79566-128">-Instalación de Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="79566-128">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="79566-129">-Orden de configuración</span><span class="sxs-lookup"><span data-stu-id="79566-129">- Configuration order</span></span>
|  <span data-ttu-id="79566-130">![Fase 2: configuración](../../media/setup.png)</span><span class="sxs-lookup"><span data-stu-id="79566-130">![Phase 2: Setup](../../media/setup.png)</span></span> <br>[<span data-ttu-id="79566-131">Fase 2: configuración</span><span class="sxs-lookup"><span data-stu-id="79566-131">Phase 2: Setup</span></span>](setup-mtpeval.md)|  <span data-ttu-id="79566-132">Siga los pasos iniciales para acceder al centro de seguridad de Microsoft 365 para configurar el entorno de laboratorio de prueba de Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="79566-132">Take the initial steps to access Microsoft 365 Security Center to setup your Microsoft Threat Protection trial lab environment.</span></span> <span data-ttu-id="79566-133">Se le guiará para:</span><span class="sxs-lookup"><span data-stu-id="79566-133">You will be guided to:</span></span><br><br><span data-ttu-id="79566-134">-Inscríbase en la versión de prueba de Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="79566-134">- Sign up for Microsoft 365 E5 Trial</span></span> <br>  <span data-ttu-id="79566-135">-Configurar dominio</span><span class="sxs-lookup"><span data-stu-id="79566-135">- Configure domain</span></span><br><span data-ttu-id="79566-136">-Asignar licencias de Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="79566-136">- Assign Microsoft 365 E5 licenses</span></span><br><span data-ttu-id="79566-137">-Completar el Asistente de configuración en el portal</span><span class="sxs-lookup"><span data-stu-id="79566-137">- Complete the setup wizard in the portal</span></span>|
|  <span data-ttu-id="79566-138">![Fase 3: configurar & incorporado](../../media/config-onboard.png)</span><span class="sxs-lookup"><span data-stu-id="79566-138">![Phase 3: Configure & Onboard](../../media/config-onboard.png)</span></span> <br>[<span data-ttu-id="79566-139">Fase 3: configurar & incorporado</span><span class="sxs-lookup"><span data-stu-id="79566-139">Phase 3: Configure & Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="79566-140">Configure cada uno de los extremos incorporados y de la protección contra amenazas de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="79566-140">Configure each Microsoft Threat Protection pillar and onboard endpoints.</span></span> <span data-ttu-id="79566-141">Se le guiará para:</span><span class="sxs-lookup"><span data-stu-id="79566-141">You will be guided to:</span></span><br><br><span data-ttu-id="79566-142">-Configurar la protección contra amenazas avanzada de Office 365</span><span class="sxs-lookup"><span data-stu-id="79566-142">- Configure Office 365 Advanced Threat Protection</span></span><br><span data-ttu-id="79566-143">-Configurar Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="79566-143">- Configure Microsoft Cloud App Security</span></span><br><span data-ttu-id="79566-144">-Configurar la protección contra amenazas avanzada de Azure</span><span class="sxs-lookup"><span data-stu-id="79566-144">- Configure Azure Advanced Threat Protection</span></span><br><span data-ttu-id="79566-145">-Configurar la protección contra amenazas avanzada de Microsoft defender</span><span class="sxs-lookup"><span data-stu-id="79566-145">- Configure Microsoft Defender Advanced Threat Protection</span></span> 


## <a name="in-scope"></a><span data-ttu-id="79566-146">En el ámbito</span><span class="sxs-lookup"><span data-stu-id="79566-146">In scope</span></span>

<span data-ttu-id="79566-147">A continuación se encuentra en el ámbito de esta guía del entorno de laboratorio de prueba:</span><span class="sxs-lookup"><span data-stu-id="79566-147">The following is in scope for this trial lab environment guide:</span></span>
-   <span data-ttu-id="79566-148">Configurar Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="79566-148">Set up Azure Active Directory</span></span>
-   <span data-ttu-id="79566-149">Configuración de la protección contra amenazas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="79566-149">Set up Microsoft Threat Protection</span></span>
    -   <span data-ttu-id="79566-150">Inscríbase en la versión de prueba de Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="79566-150">Sign up for Microsoft 365 E5 Trial</span></span>
    -   <span data-ttu-id="79566-151">Configurar dominio</span><span class="sxs-lookup"><span data-stu-id="79566-151">Configure domain</span></span>
    -   <span data-ttu-id="79566-152">Asignar licencias de Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="79566-152">Assign Microsoft 365 E5 licenses</span></span>
    -   <span data-ttu-id="79566-153">Finalización del Asistente para la instalación en el portal</span><span class="sxs-lookup"><span data-stu-id="79566-153">Completing the setup wizard within the portal</span></span>
-   <span data-ttu-id="79566-154">Configurar todos los pilares de la protección contra amenazas de Microsoft según los procedimientos recomendados</span><span class="sxs-lookup"><span data-stu-id="79566-154">Configure all Microsoft Threat Protection pillars based on best practices</span></span>
    -   <span data-ttu-id="79566-155">Protección contra amenazas avanzada de Office 365</span><span class="sxs-lookup"><span data-stu-id="79566-155">Office 365 Advanced Threat Protection</span></span>
    -   <span data-ttu-id="79566-156">Azure Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="79566-156">Azure Advanced Threat Protection</span></span>
    -   <span data-ttu-id="79566-157">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="79566-157">Microsoft Cloud App Security</span></span>
    -   <span data-ttu-id="79566-158">Protección contra amenazas avanzada de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="79566-158">Microsoft Defender Advanced Threat Protection</span></span>

## <a name="out-of-scope"></a><span data-ttu-id="79566-159">Fuera de ámbito</span><span class="sxs-lookup"><span data-stu-id="79566-159">Out of scope</span></span>

<span data-ttu-id="79566-160">Las siguientes opciones están fuera del ámbito de esta guía de implementación:</span><span class="sxs-lookup"><span data-stu-id="79566-160">The following are out of scope of this deployment guide:</span></span>

-   <span data-ttu-id="79566-161">Configuración de soluciones de terceros que pueden integrarse con ATP de Microsoft defender</span><span class="sxs-lookup"><span data-stu-id="79566-161">Configuration of third-party solutions that might integrate with Microsoft Defender ATP</span></span>
-   <span data-ttu-id="79566-162">Pruebas de penetración en el entorno de producción</span><span class="sxs-lookup"><span data-stu-id="79566-162">Penetration testing in production environment</span></span>

## <a name="next-step"></a><span data-ttu-id="79566-163">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="79566-163">Next step</span></span>
<span data-ttu-id="79566-164">![Fase 1: preparación](../../media/prepare.png)</span><span class="sxs-lookup"><span data-stu-id="79566-164">![Phase 1: Prepare](../../media/prepare.png)</span></span> <br><span data-ttu-id="79566-165">[Fase 1: preparación](prepare-mtpeval.md) 
</span><span class="sxs-lookup"><span data-stu-id="79566-165">[Phase 1: Prepare](prepare-mtpeval.md) 
</span></span><br> <span data-ttu-id="79566-166">Preparar el entorno de laboratorio de evaluación de Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="79566-166">Prepare your Microsoft Threat Protection evaluation lab environment</span></span>
