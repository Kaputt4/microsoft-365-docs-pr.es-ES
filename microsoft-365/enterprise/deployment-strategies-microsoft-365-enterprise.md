---
title: Estrategias de implementación de la infraestructura base de Microsoft 365 Enterprise
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 01/23/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Conozca algunas de las formas en las que puede implementar las fases de la infraestructura base de Microsoft 365 Enterprise.
ms.openlocfilehash: 909526fb4938c8da142b4f667140f10dda660877
ms.sourcegitcommit: 6f94b7a272e33c492957336eae28f439e438c85b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/13/2019
ms.locfileid: "29993241"
---
# <a name="microsoft-365-enterprise-foundation-infrastructure-deployment-strategies"></a><span data-ttu-id="406e4-103">Estrategias de implementación de la infraestructura base de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="406e4-103">Microsoft 365 Enterprise foundation infrastructure deployment strategies</span></span>

<span data-ttu-id="406e4-p101">Hay varias formas de implementar las fases de la [infraestructura base](deploy-foundation-infrastructure.md) de Microsoft 365 Enterprise y distribuir las funciones, el software y los servicios a los usuarios. Para empezar a trabajar en la administración de proyectos de esta tarea, que puede ser grande y compleja en función del tamaño de la organización y su infraestructura existente, tenga en cuenta las siguientes estrategias de implementación:</span><span class="sxs-lookup"><span data-stu-id="406e4-p101">There are many ways you can deploy the phases of the [foundation infrastructure](deploy-foundation-infrastructure.md) of Microsoft 365 Enterprise and roll out its capabilities, software, and services to your users. To get you started on the project management of this undertaking, which can be large and complex depending on the size of your organization and its existing infrastructure, consider the following deployment strategies:</span></span>

- <span data-ttu-id="406e4-106">Implementación de serie:</span><span class="sxs-lookup"><span data-stu-id="406e4-106">Serial deployment</span></span>
- <span data-ttu-id="406e4-107">Implementación paralela con implementación de usuarios que no se superpone</span><span class="sxs-lookup"><span data-stu-id="406e4-107">Parallel deployment with non-overlapping user rollout</span></span>
- <span data-ttu-id="406e4-108">Implementación paralela con implementación de usuarios que se superpone</span><span class="sxs-lookup"><span data-stu-id="406e4-108">Parallel deployment with overlapping user rollout</span></span>
- <span data-ttu-id="406e4-109">Infraestructura inicial e implementación de la configuración completa</span><span class="sxs-lookup"><span data-stu-id="406e4-109">Up-front infrastructure and rollout of the end-to-end configuration</span></span>

<span data-ttu-id="406e4-110">Utilice estas estrategias para obtener ideas sobre cómo administrar todo el proyecto y obtener más rápidamente las ventajas empresariales de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="406e4-110">Use these strategies for ideas on how to manage the overall project and more quickly realize the business benefits of Microsoft 365 Enterprise.</span></span>

>[!Note]
><span data-ttu-id="406e4-p102">Este artículo contiene supuestos y simplificaciones como una manera coherente de describir las estrategias de implementación. Estas estrategias de implementación son generalizadas y no pretenden implicar períodos de tiempo concretos, ni se aplican a todas las organizaciones y situaciones.</span><span class="sxs-lookup"><span data-stu-id="406e4-p102">This article contains assumptions and simplifications for a consistent way to describe the deployment strategies. These deployment strategies are generalized and are not meant to imply any specific timeframes, nor are they meant to apply to all organizations and situations.</span></span>
>

## <a name="elements-of-it-project-management-for-typical-enterprise-organizations"></a><span data-ttu-id="406e4-113">Elementos de la administración de proyectos de TI para organizaciones empresariales típicas</span><span class="sxs-lookup"><span data-stu-id="406e4-113">Elements of IT project management for typical enterprise organizations</span></span>

<span data-ttu-id="406e4-p103">La infraestructura de TI incluye servicios back-end y la implementación de funcionalidades nuevas o mejoradas o la instalación de software en los usuarios finales. Los departamentos de TI suelen implementar los elementos de una infraestructura de TI de forma metódica. Un enfoque para la implementación correcta de un elemento de la infraestructura de TI consiste en:</span><span class="sxs-lookup"><span data-stu-id="406e4-p103">IT infrastructure includes both backend services and the rollout of new or improved capabilities or installed software to end users. IT departments typically deploy elements of an IT infrastructure in a methodical way. One approach to the successful deployment of an element of IT infrastructure consists of:</span></span>

- <span data-ttu-id="406e4-117">Una implementación piloto</span><span class="sxs-lookup"><span data-stu-id="406e4-117">A pilot rollout</span></span> 

  <span data-ttu-id="406e4-118">Incluye la configuración de la infraestructura inicial y la implementación en un grupo piloto de usuarios, así como las pruebas y las modificaciones posteriores en la configuración de la infraestructura.</span><span class="sxs-lookup"><span data-stu-id="406e4-118">This includes initial infrastructure configuration and rollout to a pilot set of users, testing, and subsequent modifications to the infrastructure configuration.</span></span>

- <span data-ttu-id="406e4-119">Una implementación de usuarios</span><span class="sxs-lookup"><span data-stu-id="406e4-119">A user rollout</span></span>

  <span data-ttu-id="406e4-120">Incluye la implementación en el resto de la organización en función de las regiones, los departamentos o los grupos o con otros tipos de propagación sistemática de la configuración o el software.</span><span class="sxs-lookup"><span data-stu-id="406e4-120">This includes the rollout to the rest of your organization based on regions, departments, groups, or other types of systematic propagation of configuration or software.</span></span>

<span data-ttu-id="406e4-121">El conjunto de usuarios de la implementación piloto no es igual al de la implementación de usuarios.</span><span class="sxs-lookup"><span data-stu-id="406e4-121">The set of users in the pilot rollout are not the same as those in the user rollout.</span></span>

<span data-ttu-id="406e4-122">En este artículo se usan los gráficos siguientes para representar estas definiciones:</span><span class="sxs-lookup"><span data-stu-id="406e4-122">This article uses the following graphics to depict these definitions:</span></span> 

![](./media/deployment-strategies-microsoft-365-enterprise/definitions.png) 

<span data-ttu-id="406e4-123">El sombreado del gráfico de implementación de usuarios indica el porcentaje en toda la organización de 0 % a 100 % con un enfoque estructurado o metódico, como grupos, departamentos o regiones.</span><span class="sxs-lookup"><span data-stu-id="406e4-123">The shading for the user rollout graphic indicates the rollout across your organization from 0% to 100% using a structured or methodical approach such as groups, departments, or regions.</span></span>

## <a name="deployment-strategies"></a><span data-ttu-id="406e4-124">Estrategias de implementación</span><span class="sxs-lookup"><span data-stu-id="406e4-124">Deployment strategies</span></span>

<span data-ttu-id="406e4-125">Tenga en cuenta las siguientes estrategias de implementación:</span><span class="sxs-lookup"><span data-stu-id="406e4-125">Consider the following deployment strategies:</span></span>

- <span data-ttu-id="406e4-126">Implementación de serie:</span><span class="sxs-lookup"><span data-stu-id="406e4-126">Serial deployment</span></span>
- <span data-ttu-id="406e4-127">Implementación paralela con implementación de usuarios que no se superpone</span><span class="sxs-lookup"><span data-stu-id="406e4-127">Parallel deployment with non-overlapping user rollout</span></span>
- <span data-ttu-id="406e4-128">Implementación paralela con implementación de usuarios que se superpone</span><span class="sxs-lookup"><span data-stu-id="406e4-128">Parallel deployment with overlapping user rollout</span></span>
- <span data-ttu-id="406e4-129">Infraestructura inicial e implementación de la configuración completa</span><span class="sxs-lookup"><span data-stu-id="406e4-129">Up-front infrastructure and rollout of the end-to-end configuration</span></span>

### <a name="serial-deployment"></a><span data-ttu-id="406e4-130">Implementación de serie:</span><span class="sxs-lookup"><span data-stu-id="406e4-130">Serial deployment</span></span>

<span data-ttu-id="406e4-p104">Con una implementación de serie, se distribuye completamente una fase, lo que permite que la fase llegue a completar el 100 % de la implementación para todos los usuarios antes de pasar a la siguiente. Aquí tiene algunos de los motivos por los que se podría implementar de esta forma:</span><span class="sxs-lookup"><span data-stu-id="406e4-p104">With a serial deployment, you completely roll out a phase, allowing the phase to reach 100% completion of deployment to all of your users, before moving on to the next one. Here are some of the reasons why you might deploy this way:</span></span>

- <span data-ttu-id="406e4-133">Mitigación de riesgos</span><span class="sxs-lookup"><span data-stu-id="406e4-133">Risk mitigation</span></span>
- <span data-ttu-id="406e4-134">Restricciones de recursos</span><span class="sxs-lookup"><span data-stu-id="406e4-134">Resourcing constraints</span></span>
- <span data-ttu-id="406e4-135">Ciclos de financiación del departamento de TI</span><span class="sxs-lookup"><span data-stu-id="406e4-135">IT department funding cycles</span></span>
- <span data-ttu-id="406e4-136">Dependencias de la tecnología de TI</span><span class="sxs-lookup"><span data-stu-id="406e4-136">IT technology dependencies</span></span>
- <span data-ttu-id="406e4-137">Administración de cambios empresariales y resistencia del usuario final</span><span class="sxs-lookup"><span data-stu-id="406e4-137">Business change management and end-user resistance</span></span>

<span data-ttu-id="406e4-138">Este diagrama de Gantt muestra una implementación de serie simplificada de las fases 2 a la 6 de la infraestructura base de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="406e4-138">This Gantt chart shows a simplified serial deployment of phases 2-6 of the foundation infrastructure for Microsoft 365 Enterprise.</span></span>

![](./media/deployment-strategies-microsoft-365-enterprise/serial.png) 
 
<span data-ttu-id="406e4-139">Para simplificar la explicación y el ejemplo, se presupone que se tardará lo mismo en cada fase y cada segmento de implementación en cada fase.</span><span class="sxs-lookup"><span data-stu-id="406e4-139">To simplify the discussion and example, each phase and deployment segment within each phase are assumed to take the same amount of time.</span></span>

>[!Note]
><span data-ttu-id="406e4-p105">Fase 1: La creación de la red de la infraestructura base de Microsoft 365 Enterprise es una fase exclusiva del departamento de TI. Los usuarios obtienen las ventajas de una conectividad optimizada con los recursos de nube de Microsoft pero no están obligados a conseguirla.</span><span class="sxs-lookup"><span data-stu-id="406e4-p105">Phase 1: Networking of the Microsoft 365 Enterprise Foundation Infrastructure is an IT department-only phase. Users reap the benefits of optimized connectivity to Microsoft’s cloud resources but are not imposed upon to achieve it.</span></span>
>

<span data-ttu-id="406e4-142">Se simplificó la experiencia del usuario piloto de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="406e4-142">Simplified example pilot user experience:</span></span>

- <span data-ttu-id="406e4-p106">En diciembre, necesito usar mi smartphone para MFA. (Identidad)</span><span class="sxs-lookup"><span data-stu-id="406e4-p106">In December, I need to use my smart phone for MFA. (Identity)</span></span>
- <span data-ttu-id="406e4-p107">En marzo, instalo Windows 10 Enterprise en el escritorio de Windows 8.1. (Windows 10 Enterprise)</span><span class="sxs-lookup"><span data-stu-id="406e4-p107">In March, I get Windows 10 Enterprise installed on my Windows 8.1 desktop. (Windows 10 Enterprise)</span></span>
- <span data-ttu-id="406e4-p108">En junio, instalo Office 365 ProPlus en reemplazo de Office 2013. (Office 365 ProPlus)</span><span class="sxs-lookup"><span data-stu-id="406e4-p108">In June, I get Office 365 ProPlus installed, replacing Office 2013. (Office 365 ProPlus)</span></span>
- <span data-ttu-id="406e4-p109">En septiembre, aplico las directivas de acceso condicional y de aplicaciones, así como de inscripción de dispositivos. (Administración de dispositivos móviles)</span><span class="sxs-lookup"><span data-stu-id="406e4-p109">In September, I get device enrollment and app and conditional access policies applied. (Mobile device management)</span></span>
- <span data-ttu-id="406e4-p110">En diciembre, instalo el cliente de Azure Information Protection y me entreno en la aplicación de etiquetas a los documentos. (Information Protection)</span><span class="sxs-lookup"><span data-stu-id="406e4-p110">In December, I get the Azure Information Protection client installed and get trained on how to apply labels to documents. (Information protection)</span></span>

<span data-ttu-id="406e4-153">El resultado es una cadencia de 90 días entre implementaciones piloto sucesivas.</span><span class="sxs-lookup"><span data-stu-id="406e4-153">The result is a 90-day cadence between successive pilot rollouts.</span></span>

<span data-ttu-id="406e4-154">Se simplificó la experiencia del usuario final de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="406e4-154">Simplified example end-user experience:</span></span>

- <span data-ttu-id="406e4-p111">En enero, necesito usar mi smartphone para MFA. (Identidad)</span><span class="sxs-lookup"><span data-stu-id="406e4-p111">In January, I need to use my smart phone for MFA. (Identity)</span></span>
- <span data-ttu-id="406e4-p112">En abril, instalo Windows 10 Enterprise en el escritorio de Windows 8.1. (Windows 10 Enterprise)</span><span class="sxs-lookup"><span data-stu-id="406e4-p112">In April, I get Windows 10 Enterprise installed on my Windows 8.1 desktop. (Windows 10 Enterprise)</span></span>
- <span data-ttu-id="406e4-p113">En julio, instalo Office 365 ProPlus en reemplazo de Office 2013. (Office 365 ProPlus)</span><span class="sxs-lookup"><span data-stu-id="406e4-p113">In July, I get Office 365 ProPlus installed, replacing Office 2013. (Office 365 ProPlus)</span></span>
- <span data-ttu-id="406e4-p114">En octubre, aplico las directivas de acceso condicional y de aplicaciones, así como de inscripción de dispositivos. (Administración de dispositivos móviles)</span><span class="sxs-lookup"><span data-stu-id="406e4-p114">In October, I get device enrollment and app and conditional access policies applied. (Mobile device management)</span></span>
- <span data-ttu-id="406e4-p115">En enero del año siguiente, instalo el cliente de Azure Information Protection y me entreno en la aplicación de etiquetas a los documentos. (Information Protection)</span><span class="sxs-lookup"><span data-stu-id="406e4-p115">In January of the following year, I get the Azure Information Protection client installed and get trained on how to apply labels to documents. (Information protection)</span></span>

<span data-ttu-id="406e4-165">El resultado es una cadencia de 90 días entre implementaciones sucesivas de usuarios.</span><span class="sxs-lookup"><span data-stu-id="406e4-165">The result is a 90-day cadence between successive user rollouts.</span></span>

<span data-ttu-id="406e4-166">La desventaja de esta estrategia de implementación es que se puede tardar mucho en implementar por completo la infraestructura base de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="406e4-166">The disadvantage to this deployment strategy is that it can take a long time to fully deploy the Microsoft 365 Enterprise foundation infrastructure.</span></span>

### <a name="parallel-deployment-with-non-overlapping-user-rollout-parallel-1"></a><span data-ttu-id="406e4-167">Implementación paralela con implementación de usuarios que no se superpone (paralela 1)</span><span class="sxs-lookup"><span data-stu-id="406e4-167">Parallel deployment with non-overlapping user rollout (Parallel 1)</span></span>

<span data-ttu-id="406e4-p116">En esta estrategia, se inicia la implementación piloto de la siguiente fase durante la última parte de la implementación de usuarios de la fase actual. Aquí tiene la implementación de las fases de la 2 a la 6 cuando la implementación piloto se produce al concluir la implementación de usuarios de la fase anterior.</span><span class="sxs-lookup"><span data-stu-id="406e4-p116">For this deployment strategy, you start the pilot rollout of the next phase during the last part of the user rollout of the current phase. Here is the deployment of phases 2-6 when the pilot rollout occurs as the user rollout of the previous phase is wrapping up.</span></span>

<span data-ttu-id="406e4-170">Aquí tiene una comparación simplificada entre las estrategias de implementación de serie y paralela.</span><span class="sxs-lookup"><span data-stu-id="406e4-170">Here is a simplified comparison between parallel and serial deployment strategies.</span></span>

![](./media/deployment-strategies-microsoft-365-enterprise/parallel1.png) 
 
<span data-ttu-id="406e4-p117">El resultado final es que la implementación de usuarios de la fase actual se completa en toda la organización antes de que empiece la siguiente. Los usuarios que no están en la implementación piloto no se enfrentan a las implementaciones de varias fases al mismo tiempo, pero las implementaciones piloto se realizan en paralelo con las implementaciones de usuarios.</span><span class="sxs-lookup"><span data-stu-id="406e4-p117">The end result is that user rollout for the current phase completes across your organization before the next one starts. Users that are not in pilot rollouts are not dealing with the rollouts of multiple phases at the same time, but pilot rollouts are done in parallel with user rollouts.</span></span>

<span data-ttu-id="406e4-173">Se simplificó la experiencia del usuario piloto de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="406e4-173">Simplified example pilot user experience:</span></span> 

- <span data-ttu-id="406e4-p118">En diciembre, necesito usar mi smartphone para MFA. (Identidad)</span><span class="sxs-lookup"><span data-stu-id="406e4-p118">In December, I need to use my smart phone for MFA. (Identity)</span></span>
- <span data-ttu-id="406e4-p119">En febrero, instalo Windows 10 Enterprise en el escritorio de Windows 8.1. (Windows 10 Enterprise)</span><span class="sxs-lookup"><span data-stu-id="406e4-p119">In February, I get Windows 10 Enterprise installed on my Windows 8.1 desktop. (Windows 10 Enterprise)</span></span>
- <span data-ttu-id="406e4-p120">En abril, instalo Office 365 ProPlus en reemplazo de Office 2013. (Office 365 ProPlus)</span><span class="sxs-lookup"><span data-stu-id="406e4-p120">In April, I get Office 365 ProPlus installed, replacing Office 2013. (Office 365 ProPlus)</span></span>
- <span data-ttu-id="406e4-p121">En junio, aplico las directivas de acceso condicional y de aplicaciones, así como de inscripción de dispositivos. (Administración de dispositivos móviles)</span><span class="sxs-lookup"><span data-stu-id="406e4-p121">In June, I get device enrollment and app and conditional access policies applied. (Mobile device management)</span></span>
- <span data-ttu-id="406e4-p122">En agosto, instalo el cliente de Azure Information Protection y me entreno en la aplicación de etiquetas a los documentos. (Information Protection)</span><span class="sxs-lookup"><span data-stu-id="406e4-p122">In August, I get the Azure Information Protection client installed and get trained on how to apply labels to documents. (Information protection)</span></span>

<span data-ttu-id="406e4-184">El resultado es una cadencia de 60 días entre implementaciones piloto sucesivas.</span><span class="sxs-lookup"><span data-stu-id="406e4-184">The result is a 60-day cadence between successive pilot rollouts.</span></span>

<span data-ttu-id="406e4-185">Se simplificó la experiencia del usuario final de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="406e4-185">Simplified example end-user experience:</span></span>

- <span data-ttu-id="406e4-p123">En enero, necesito usar mi smartphone para MFA. (Identidad)</span><span class="sxs-lookup"><span data-stu-id="406e4-p123">In January, I need to use my smart phone for MFA. (Identity)</span></span>
- <span data-ttu-id="406e4-p124">En marzo, instalo Windows 10 Enterprise en el escritorio de Windows 8.1. (Windows 10 Enterprise)</span><span class="sxs-lookup"><span data-stu-id="406e4-p124">In March, I get Windows 10 Enterprise installed on my Windows 8.1 desktop. (Windows 10 Enterprise)</span></span>
- <span data-ttu-id="406e4-p125">En mayo, instalo Office 365 ProPlus en reemplazo de Office 2013. (Office 365 ProPlus)</span><span class="sxs-lookup"><span data-stu-id="406e4-p125">In May, I get Office 365 ProPlus installed, replacing Office 2013. (Office 365 ProPlus)</span></span>
- <span data-ttu-id="406e4-p126">En julio, aplico las directivas de acceso condicional y de aplicaciones, así como de inscripción de dispositivos. (Administración de dispositivos móviles)</span><span class="sxs-lookup"><span data-stu-id="406e4-p126">In July, I get device enrollment and app and conditional access policies applied. (Mobile device management)</span></span>
- <span data-ttu-id="406e4-p127">En septiembre, instalo el cliente de Azure Information Protection y me entreno en la aplicación de etiquetas a los documentos. (Information Protection)</span><span class="sxs-lookup"><span data-stu-id="406e4-p127">In September, I get the Azure Information Protection client installed and get trained on how to apply labels to documents. (Information protection)</span></span>

<span data-ttu-id="406e4-196">El resultado es una cadencia de 60 días entre implementaciones sucesivas de usuarios.</span><span class="sxs-lookup"><span data-stu-id="406e4-196">The result is a 60-day cadence between successive user rollouts.</span></span>

<span data-ttu-id="406e4-197">La ventaja de esta estrategia de implementación es que se puede tardar menos en implementar por completo la infraestructura base de Microsoft 365 Enterprise, sin que el departamento de TI y los usuarios tengan que enfrentarse a varias implementaciones a la vez.</span><span class="sxs-lookup"><span data-stu-id="406e4-197">The advantage to this deployment strategy is that it can take less time to fully deploy the Microsoft 365 Enterprise foundation infrastructure, without having your IT department and users deal with multiple rollouts the same time.</span></span>

### <a name="parallel-deployment-with-overlapping-user-rollout-parallel-2"></a><span data-ttu-id="406e4-198">Implementación paralela con implementación de usuarios que se superpone (paralela 2)</span><span class="sxs-lookup"><span data-stu-id="406e4-198">Parallel deployment with overlapping user rollout (Parallel 2)</span></span>

<span data-ttu-id="406e4-199">Con esta estrategia de implementación, se inicia:</span><span class="sxs-lookup"><span data-stu-id="406e4-199">For this deployment strategy, you start the:</span></span>

- <span data-ttu-id="406e4-200">La implementación piloto de la fase siguiente se realiza durante la última parte de la implementación de usuarios de la fase actual.</span><span class="sxs-lookup"><span data-stu-id="406e4-200">Pilot rollout of the next phase during the last part of the user rollout of the current phase.</span></span>
- <span data-ttu-id="406e4-p128">La implementación de usuarios de la siguiente fase se realiza durante la implementación de usuarios de la fase actual de tal manera que ningún usuario se enfrenta a las implementaciones de varias fases al mismo tiempo. Se supone que cada fase de la infraestructura base se distribuye de la misma forma, por regiones, departamentos o de otra forma.</span><span class="sxs-lookup"><span data-stu-id="406e4-p128">User rollout of the next phase during the user rollout of the current phase in such a way that no user is dealing with the rollouts of multiple phases at the same time. This assumes that you are rolling out each phase of the foundation infrastructure in the same way, via regions, departments, or other.</span></span>

<span data-ttu-id="406e4-203">Aquí tiene una comparación simplificada entre distintas estrategias de implementación.</span><span class="sxs-lookup"><span data-stu-id="406e4-203">Here is a simplified comparison between the different deployment strategies.</span></span>

![](./media/deployment-strategies-microsoft-365-enterprise/parallel2.png) 

<span data-ttu-id="406e4-204">El resultado final es que:</span><span class="sxs-lookup"><span data-stu-id="406e4-204">The end result is that:</span></span>

- <span data-ttu-id="406e4-205">Las implementaciones piloto pasan sin pausa de una fase a la siguiente.</span><span class="sxs-lookup"><span data-stu-id="406e4-205">Pilot rollouts go from one phase to the next without a pause.</span></span>
- <span data-ttu-id="406e4-206">La implementación de usuarios de una fase comienza antes de completar la implementación de usuarios de la fase anterior, pero ningún usuario individual se distribuirá en más de una fase a la vez.</span><span class="sxs-lookup"><span data-stu-id="406e4-206">The user rollout for a phase begins before the completion of the user rollout of the previous phase, but no individual user is rolling out more than one phase at a time.</span></span>

<span data-ttu-id="406e4-207">Se simplificó la experiencia del usuario piloto de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="406e4-207">Simplified example pilot user experience:</span></span> 

- <span data-ttu-id="406e4-p129">En diciembre, necesito usar mi smartphone para MFA. (Identidad)</span><span class="sxs-lookup"><span data-stu-id="406e4-p129">In December, I need to use my smart phone for MFA. (Identity)</span></span>
- <span data-ttu-id="406e4-p130">En enero, instalo Windows 10 Enterprise en el escritorio de Windows 8.1. (Windows 10 Enterprise)</span><span class="sxs-lookup"><span data-stu-id="406e4-p130">In January, I get Windows 10 Enterprise installed on my Windows 8.1 desktop. (Windows 10 Enterprise)</span></span>
- <span data-ttu-id="406e4-p131">En febrero, instalo Office 365 ProPlus en reemplazo de Office 2013. (Office 365 ProPlus)</span><span class="sxs-lookup"><span data-stu-id="406e4-p131">In February, I get Office 365 ProPlus installed, replacing Office 2013. (Office 365 ProPlus)</span></span>
- <span data-ttu-id="406e4-p132">En marzo, aplico las directivas de acceso condicional y de aplicaciones, así como de inscripción de dispositivos. (Administración de dispositivos móviles)</span><span class="sxs-lookup"><span data-stu-id="406e4-p132">In March, I get device enrollment and app and conditional access policies applied. (Mobile device management)</span></span>
- <span data-ttu-id="406e4-p133">En abril, instalo el cliente de Azure Information Protection y me entreno en la aplicación de etiquetas a los documentos. (Information Protection)</span><span class="sxs-lookup"><span data-stu-id="406e4-p133">In April, I get the Azure Information Protection client installed and get trained on how to apply labels to documents. (Information protection)</span></span>

<span data-ttu-id="406e4-218">El resultado es una cadencia de 30 días entre implementaciones piloto sucesivas.</span><span class="sxs-lookup"><span data-stu-id="406e4-218">The result is a 30-day cadence between successive pilot rollouts.</span></span>

<span data-ttu-id="406e4-219">Se simplificó la experiencia del usuario final de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="406e4-219">Simplified example end-user experience:</span></span>

- <span data-ttu-id="406e4-p134">En enero, necesito usar mi smartphone para MFA. (Identidad)</span><span class="sxs-lookup"><span data-stu-id="406e4-p134">In January, I need to use my smart phone for MFA. (Identity)</span></span>
- <span data-ttu-id="406e4-p135">En febrero, instalo Windows 10 Enterprise en el escritorio de Windows 8.1. (Windows 10 Enterprise)</span><span class="sxs-lookup"><span data-stu-id="406e4-p135">In February, I get Windows 10 Enterprise installed on my Windows 8.1 desktop. (Windows 10 Enterprise)</span></span>
- <span data-ttu-id="406e4-p136">En marzo, instalo Office 365 ProPlus en reemplazo de Office 2013. (Office 365 ProPlus)</span><span class="sxs-lookup"><span data-stu-id="406e4-p136">In March, I get Office 365 ProPlus installed, replacing Office 2013. (Office 365 ProPlus)</span></span>
- <span data-ttu-id="406e4-p137">En abril, aplico las directivas de acceso condicional y de aplicaciones, así como de inscripción de dispositivos. (Administración de dispositivos móviles)</span><span class="sxs-lookup"><span data-stu-id="406e4-p137">In April, I get device enrollment and app and conditional access policies applied. (Mobile device management)</span></span>
- <span data-ttu-id="406e4-p138">En mayo, instalo el cliente de Azure Information Protection y me entreno en la aplicación de etiquetas a los documentos. (Information Protection)</span><span class="sxs-lookup"><span data-stu-id="406e4-p138">In May, I get the Azure Information Protection client installed and get trained on how to apply labels to documents. (Information protection)</span></span>

<span data-ttu-id="406e4-230">El resultado es una cadencia de 30 días entre implementaciones sucesivas de usuarios.</span><span class="sxs-lookup"><span data-stu-id="406e4-230">The result is a 30-day cadence between successive user rollouts.</span></span>

<span data-ttu-id="406e4-p139">La ventaja de esta estrategia de implementación es que se puede tardar incluso menos en implementar completamente la infraestructura base de Microsoft 365 Enterprise, sin que los usuarios individuales tengan que enfrentarse a varias implementaciones a la vez. Pero los usuarios no tienen descanso entre fases sucesivas.</span><span class="sxs-lookup"><span data-stu-id="406e4-p139">The advantage to this deployment strategy is that it can take even less time to fully deploy the Microsoft 365 Enterprise foundation infrastructure, still without having individual users deal with multiple rollouts the same time. However, users don’t get a break between successive phases.</span></span>

### <a name="up-front-infrastructure-and-rollout-of-end-to-end-configuration"></a><span data-ttu-id="406e4-233">Infraestructura inicial e implementación de la configuración completa</span><span class="sxs-lookup"><span data-stu-id="406e4-233">Up-front infrastructure and rollout of end-to-end configuration</span></span>

<span data-ttu-id="406e4-234">En el caso de organizaciones más pequeñas con la posibilidad de comprimir las fases de la 2 a la 6 en un solo segmento de implementación, la implementación resultante tiene el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="406e4-234">For smaller organizations with the ability to compress phases 2-6 into a single deployment segment, the resulting deployment looks like this:</span></span>
 
![](./media/deployment-strategies-microsoft-365-enterprise/up-front.png) 

<span data-ttu-id="406e4-p140">El departamento de TI configura la infraestructura de las fases 2 a la 6, luego la distribuye a los usuarios piloto para comprobar la funcionalidad completa. Por ejemplo, los usuarios piloto obtienen toda esta funcionalidad al mismo tiempo:</span><span class="sxs-lookup"><span data-stu-id="406e4-p140">The IT department configures the infrastructure for phases 2-6, then rolls out to the pilot users to check for the end-to-end functionality. For example, pilot users get all of this functionality at the same time:</span></span>

- <span data-ttu-id="406e4-237">MFA y otras características de identidad (identidad)</span><span class="sxs-lookup"><span data-stu-id="406e4-237">MFA and other identity features (Identity)</span></span>
- <span data-ttu-id="406e4-238">Windows 10 Enterprise en dispositivos Windows (Windows 10 Enterprise)</span><span class="sxs-lookup"><span data-stu-id="406e4-238">Windows 10 Enterprise on Windows devices (Windows 10 Enterprise)</span></span>
- <span data-ttu-id="406e4-239">Office 365 ProPlus para el conjunto de aplicaciones de Office (Office 365 ProPlus)</span><span class="sxs-lookup"><span data-stu-id="406e4-239">Office 365 ProPlus for the Office suite (Office 365 ProPlus)</span></span>
- <span data-ttu-id="406e4-240">Directivas de acceso condicional y aplicaciones (Administración de dispositivos móviles)</span><span class="sxs-lookup"><span data-stu-id="406e4-240">App and conditional access policies (Mobile device management)</span></span>
- <span data-ttu-id="406e4-241">Instalación del cliente de Azure Information Protection y entrenamiento en la aplicación de etiquetas a los documentos (Information Protection)</span><span class="sxs-lookup"><span data-stu-id="406e4-241">Azure Information Protection client installed and training on how to apply labels to documents (Information protection)</span></span>

<span data-ttu-id="406e4-242">Tras finalizar la implementación piloto, empiece la implementación de usuarios en la que cada usuario obtiene todas las funciones la vez.</span><span class="sxs-lookup"><span data-stu-id="406e4-242">Once the pilot rollout is concluded, the user rollout begins in which each user gets all the functionality the same time.</span></span>

## <a name="next-step"></a><span data-ttu-id="406e4-243">Siguiente paso</span><span class="sxs-lookup"><span data-stu-id="406e4-243">Next step</span></span>

<span data-ttu-id="406e4-244">Inicio de la implementación de Microsoft 365 Enterprise con la [infraestructura base](deploy-foundation-infrastructure.md).</span><span class="sxs-lookup"><span data-stu-id="406e4-244">Start your deployment of Microsoft 365 Enterprise with the [foundation infrastructure](deploy-foundation-infrastructure.md).</span></span>
