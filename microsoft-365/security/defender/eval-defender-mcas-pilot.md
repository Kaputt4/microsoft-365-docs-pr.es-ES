---
title: Prueba Microsoft Cloud App Security con Microsoft 365 Defender, crear grupos piloto, configurar el control de acceso condicional, probar funcionalidades, configurar como parte de Microsoft 365 Defender
description: Configure su laboratorio Microsoft 365 Defender prueba o entorno piloto para probar y experimentar la solución de seguridad diseñada para proteger dispositivos, identidades, datos y aplicaciones.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
ms.date: 07/09/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: e061bf213ee929f91a48b03c71b9654a7ea76b8c
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458543"
---
# <a name="pilot-microsoft-cloud-app-security-with-microsoft-365-defender"></a><span data-ttu-id="9343d-103">Piloto Microsoft Cloud App Security con Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9343d-103">Pilot Microsoft Cloud App Security with Microsoft 365 Defender</span></span>


<span data-ttu-id="9343d-104">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="9343d-104">**Applies to:**</span></span>
- <span data-ttu-id="9343d-105">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9343d-105">Microsoft 365 Defender</span></span>

<span data-ttu-id="9343d-106">Este artículo es [el paso 3 de 3](eval-defender-mcas-overview.md) en el proceso de configuración del entorno de evaluación para Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="9343d-106">This article is [Step 3 of 3](eval-defender-mcas-overview.md) in the process of setting up the evaluation environment for Microsoft Cloud App Security.</span></span> <span data-ttu-id="9343d-107">Para obtener más información acerca de este proceso, vea el [artículo de introducción](eval-defender-mcas-overview.md).</span><span class="sxs-lookup"><span data-stu-id="9343d-107">For more information about this process, see the [overview article](eval-defender-mcas-overview.md).</span></span>

<span data-ttu-id="9343d-108">Siga estos pasos para configurar y configurar el piloto para Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="9343d-108">Use the following steps to setup and configure the pilot for Microsoft Cloud App Security.</span></span>


![Pasos para la prueba piloto Microsoft Cloud App Security](../../media/defender/m365-defender-mcas-pilot-steps.png)

- <span data-ttu-id="9343d-110">Paso 1.</span><span class="sxs-lookup"><span data-stu-id="9343d-110">Step 1.</span></span> [<span data-ttu-id="9343d-111">Crear el grupo piloto: ámbito de la implementación piloto en determinados grupos de usuarios</span><span class="sxs-lookup"><span data-stu-id="9343d-111">Create the pilot group — Scope your pilot deployment to certain user groups</span></span>](#step-1-create-the-pilot-group--scope-your-pilot-deployment-to-certain-user-groups)
- [<span data-ttu-id="9343d-112">Paso 2. Configurar protección: control de aplicaciones de acceso condicional</span><span class="sxs-lookup"><span data-stu-id="9343d-112">Step 2. Configure protection — Conditional Access App Control</span></span>](#step-2-configure-protection--conditional-access-app-control)
- [<span data-ttu-id="9343d-113">Paso 3. Probar funcionalidades: tutoriales para proteger el entorno</span><span class="sxs-lookup"><span data-stu-id="9343d-113">Step 3. Try out capabilities — Walk through tutorials for protecting your environment</span></span>](#step-3-try-out-capabilities--walk-through-tutorials-for-protecting-your-environment) 


## <a name="step-1-create-the-pilot-group--scope-your-pilot-deployment-to-certain-user-groups"></a><span data-ttu-id="9343d-114">Paso 1.</span><span class="sxs-lookup"><span data-stu-id="9343d-114">Step 1.</span></span> <span data-ttu-id="9343d-115">Crear el grupo piloto: ámbito de la implementación piloto en determinados grupos de usuarios</span><span class="sxs-lookup"><span data-stu-id="9343d-115">Create the pilot group — Scope your pilot deployment to certain user groups</span></span>

<span data-ttu-id="9343d-116">Microsoft Cloud App Security permite el ámbito de la implementación.</span><span class="sxs-lookup"><span data-stu-id="9343d-116">Microsoft Cloud App Security enables you to scope your deployment.</span></span> <span data-ttu-id="9343d-117">El ámbito permite seleccionar determinados grupos de usuarios que se supervisarán para las aplicaciones o se excluirán de la supervisión.</span><span class="sxs-lookup"><span data-stu-id="9343d-117">Scoping allows you to select certain user groups to be monitored for apps or excluded from monitoring.</span></span> <span data-ttu-id="9343d-118">Puede incluir o excluir grupos de usuarios.</span><span class="sxs-lookup"><span data-stu-id="9343d-118">You can include or exclude user groups.</span></span> <span data-ttu-id="9343d-119">Para ámbito de la implementación piloto, vea [Scoped Deployment](/cloud-app-security/scoped-deployment).</span><span class="sxs-lookup"><span data-stu-id="9343d-119">To scope your pilot deployment, see [Scoped Deployment](/cloud-app-security/scoped-deployment).</span></span>


## <a name="step-2-configure-protection--conditional-access-app-control"></a><span data-ttu-id="9343d-120">Paso 2.</span><span class="sxs-lookup"><span data-stu-id="9343d-120">Step 2.</span></span> <span data-ttu-id="9343d-121">Configurar protección: control de aplicaciones de acceso condicional</span><span class="sxs-lookup"><span data-stu-id="9343d-121">Configure protection — Conditional Access App Control</span></span>

<span data-ttu-id="9343d-122">Una de las protecciones más eficaces que puede configurar es el control de aplicaciones de acceso condicional.</span><span class="sxs-lookup"><span data-stu-id="9343d-122">One of the most powerful protections you can configure is Conditional Access App Control.</span></span> <span data-ttu-id="9343d-123">Esto requiere integración con Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="9343d-123">This requires integration with Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="9343d-124">Te permite aplicar directivas de acceso condicional, incluidas las directivas relacionadas (como requerir dispositivos en buen estado) a las aplicaciones en la nube que hayas sancionado.</span><span class="sxs-lookup"><span data-stu-id="9343d-124">It allows you to apply Conditional Access policies, including related policies (like requiring healthy devices), to cloud apps you've sanctioned.</span></span> 

<span data-ttu-id="9343d-125">El primer paso para usar Microsoft Cloud App Security para administrar aplicaciones SaaS es detectarlas y luego agregarlas al inquilino de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="9343d-125">The first step in using Microsoft Cloud App Security to manage SaaS apps is to discover these and then add them to your Azure AD tenant.</span></span> <span data-ttu-id="9343d-126">Si necesitas ayuda con la detección, consulta [Descubrir y administrar aplicaciones SaaS en la red.](/cloud-app-security/tutorial-shadow-it)</span><span class="sxs-lookup"><span data-stu-id="9343d-126">If you need help with discovery, see [Discover and manage SaaS apps in your network](/cloud-app-security/tutorial-shadow-it).</span></span> <span data-ttu-id="9343d-127">Después de descubrir aplicaciones, [agrégrelos a su inquilino de Azure AD](/azure/active-directory/manage-apps/add-application-portal).</span><span class="sxs-lookup"><span data-stu-id="9343d-127">After you've discovered apps, [add these to your Azure AD tenant](/azure/active-directory/manage-apps/add-application-portal).</span></span>

<span data-ttu-id="9343d-128">Puede empezar a administrarlos haciendo lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9343d-128">You can begin to manage these by doing the following:</span></span>

- <span data-ttu-id="9343d-129">En primer lugar, en Azure AD, cree una nueva directiva de acceso condicional y configúrela para "Usar control de aplicaciones de acceso condicional".</span><span class="sxs-lookup"><span data-stu-id="9343d-129">First, in Azure AD, create a new conditional access policy and configure it to "Use Conditional Access App Control."</span></span> <span data-ttu-id="9343d-130">Esto redirige la solicitud a Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="9343d-130">This redirects the request to Cloud App Security.</span></span> <span data-ttu-id="9343d-131">Puedes crear una directiva y agregar todas las aplicaciones SaaS a esta directiva.</span><span class="sxs-lookup"><span data-stu-id="9343d-131">You can create one policy and add all SaaS apps to this policy.</span></span>
- <span data-ttu-id="9343d-132">Después, en Cloud App Security, cree directivas de sesión.</span><span class="sxs-lookup"><span data-stu-id="9343d-132">Next, in Cloud App Security, create session policies.</span></span> <span data-ttu-id="9343d-133">Cree una directiva para cada control que desee aplicar.</span><span class="sxs-lookup"><span data-stu-id="9343d-133">Create one policy for each control you want to apply.</span></span>

<span data-ttu-id="9343d-134">Para obtener más información, incluidas las aplicaciones y clientes compatibles, consulta Proteger aplicaciones con Microsoft Cloud App Security control de aplicaciones [de acceso condicional.](/cloud-app-security/proxy-intro-aad)</span><span class="sxs-lookup"><span data-stu-id="9343d-134">For more information, including supported apps and clients, see [Protect apps with Microsoft Cloud App Security Conditional Access App Control](/cloud-app-security/proxy-intro-aad).</span></span> 

<span data-ttu-id="9343d-135">Por ejemplo, directivas, consulta [Recomendaciones Microsoft Cloud App Security para aplicaciones SaaS](../office-365-security/mcas-saas-access-policies.md).</span><span class="sxs-lookup"><span data-stu-id="9343d-135">For example policies, see [Recommended Microsoft Cloud App Security policies for SaaS apps](../office-365-security/mcas-saas-access-policies.md).</span></span> <span data-ttu-id="9343d-136">Estas directivas se basa en un conjunto [de](../office-365-security/microsoft-365-policies-configurations.md) directivas comunes de acceso a dispositivos y identidades que se recomiendan como punto de partida para todos los clientes.</span><span class="sxs-lookup"><span data-stu-id="9343d-136">These policies build on a set of [common identity and device access policies](../office-365-security/microsoft-365-policies-configurations.md) that are recommended as a starting point for all customers.</span></span> 

## <a name="step-3-try-out-capabilities--walk-through-tutorials-for-protecting-your-environment"></a><span data-ttu-id="9343d-137">Paso 3.</span><span class="sxs-lookup"><span data-stu-id="9343d-137">Step 3.</span></span> <span data-ttu-id="9343d-138">Probar funcionalidades: tutoriales para proteger el entorno</span><span class="sxs-lookup"><span data-stu-id="9343d-138">Try out capabilities — Walk through tutorials for protecting your environment</span></span> 

<span data-ttu-id="9343d-139">La Microsoft Cloud App Security incluye una serie de tutoriales para ayudarle a detectar riesgos y proteger su entorno.</span><span class="sxs-lookup"><span data-stu-id="9343d-139">The Microsoft Cloud App Security documentation includes a series of tutorials to help you discover risk and protect your environment.</span></span> 

<span data-ttu-id="9343d-140">Pruebe Cloud App Security tutoriales:</span><span class="sxs-lookup"><span data-stu-id="9343d-140">Try out Cloud App Security tutorials:</span></span>

- [<span data-ttu-id="9343d-141">Detectar actividad de usuario sospechosa</span><span class="sxs-lookup"><span data-stu-id="9343d-141">Detect suspicious user activity</span></span>](/cloud-app-security/tutorial-suspicious-activity)
- [<span data-ttu-id="9343d-142">Investigar usuarios riesgosos</span><span class="sxs-lookup"><span data-stu-id="9343d-142">Investigate risky users</span></span>](/cloud-app-security/tutorial-ueba)
- [<span data-ttu-id="9343d-143">Investigar aplicaciones de OAuth arriesgadas</span><span class="sxs-lookup"><span data-stu-id="9343d-143">Investigate risky OAuth apps</span></span>](/cloud-app-security/investigate-risky-oauth)
- [<span data-ttu-id="9343d-144">Descubrir y proteger información confidencial</span><span class="sxs-lookup"><span data-stu-id="9343d-144">Discover and protect sensitive information</span></span>](/cloud-app-security/tutorial-dlp)
- [<span data-ttu-id="9343d-145">Proteger cualquier aplicación de la organización en tiempo real</span><span class="sxs-lookup"><span data-stu-id="9343d-145">Protect any app in your organization in real time</span></span>](/cloud-app-security/tutorial-proxy)
- [<span data-ttu-id="9343d-146">Bloquear descargas de información confidencial</span><span class="sxs-lookup"><span data-stu-id="9343d-146">Block downloads of sensitive information</span></span>](/cloud-app-security/use-case-proxy-block-session-aad)
- [<span data-ttu-id="9343d-147">Proteger los archivos con cuarentena de administrador</span><span class="sxs-lookup"><span data-stu-id="9343d-147">Protect your files with admin quarantine</span></span>](/cloud-app-security/use-case-admin-quarantine)
- [<span data-ttu-id="9343d-148">Requerir autenticación de paso a paso tras una acción arriesgada</span><span class="sxs-lookup"><span data-stu-id="9343d-148">Require step-up authentication upon risky action</span></span>](/cloud-app-security/tutorial-step-up-authentication)

## <a name="next-steps"></a><span data-ttu-id="9343d-149">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="9343d-149">Next steps</span></span>

[<span data-ttu-id="9343d-150">Investigar y responder con Microsoft 365 Defender en un entorno piloto</span><span class="sxs-lookup"><span data-stu-id="9343d-150">Investigate and respond using Microsoft 365 Defender in a pilot environment</span></span>](eval-defender-investigate-respond.md)

<span data-ttu-id="9343d-151">Vuelva a la introducción a [Evaluate Microsoft Cloud App Security](eval-defender-mcas-overview.md)</span><span class="sxs-lookup"><span data-stu-id="9343d-151">Return to the overview for [Evaluate Microsoft Cloud App Security](eval-defender-mcas-overview.md)</span></span>

<span data-ttu-id="9343d-152">Vuelva a la introducción a [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)</span><span class="sxs-lookup"><span data-stu-id="9343d-152">Return to the overview for [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)</span></span>