---
title: Estrategias de implementación de la infraestructura base de Microsoft 365 para empresas
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 09/24/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Conozca algunas de las formas en las que puede implementar las fases de la infraestructura base de Microsoft 365 para empresas.
ms.openlocfilehash: 354ce1a30b91f602049143dc0e93fe01629e6b04
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/19/2019
ms.locfileid: "40801895"
---
# <a name="microsoft-365-for-enterprise-foundation-infrastructure-deployment-strategies"></a><span data-ttu-id="d7bb0-103">Estrategias de implementación de la infraestructura base de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="d7bb0-103">Microsoft 365 Enterprise foundation infrastructure deployment strategies</span></span>

<span data-ttu-id="d7bb0-p101">Hay varias formas de implementar las fases de la [infraestructura base](deploy-foundation-infrastructure.md) de Microsoft 365 para empresas y distribuir las funciones, el software y los servicios a los usuarios. Para empezar a trabajar en la administración de proyectos de esta tarea, que puede ser grande y compleja en función del tamaño de la organización y su infraestructura existente, tenga en cuenta las siguientes estrategias de implementación:</span><span class="sxs-lookup"><span data-stu-id="d7bb0-p101">There are many ways you can deploy the phases of the [foundation infrastructure](deploy-foundation-infrastructure.md) of Microsoft 365 Enterprise and roll out its capabilities, software, and services to your users. To get you started on the project management of this undertaking, which can be large and complex depending on the size of your organization and its existing infrastructure, consider the following deployment strategies:</span></span>

- <span data-ttu-id="d7bb0-106">Implementación de serie:</span><span class="sxs-lookup"><span data-stu-id="d7bb0-106">Serial deployment</span></span>
- <span data-ttu-id="d7bb0-107">Implementación paralela con implementación de usuarios que no se superpone</span><span class="sxs-lookup"><span data-stu-id="d7bb0-107">Parallel deployment with non-overlapping user rollout</span></span>
- <span data-ttu-id="d7bb0-108">Implementación paralela con implementación de usuarios que se superpone</span><span class="sxs-lookup"><span data-stu-id="d7bb0-108">Parallel deployment with overlapping user rollout</span></span>
- <span data-ttu-id="d7bb0-109">Infraestructura inicial e implementación de la configuración completa</span><span class="sxs-lookup"><span data-stu-id="d7bb0-109">Up-front infrastructure and rollout of the end-to-end configuration</span></span>

<span data-ttu-id="d7bb0-110">Utilice estas estrategias para obtener ideas sobre cómo administrar todo el proyecto y obtener más rápidamente las ventajas empresariales de Microsoft 365 para empresas.</span><span class="sxs-lookup"><span data-stu-id="d7bb0-110">Use these strategies for ideas on how to manage the overall project and more quickly realize the business benefits of Microsoft 365 Enterprise.</span></span>

>[!Note]
><span data-ttu-id="d7bb0-p102">Este artículo contiene supuestos y simplificaciones como una manera coherente de describir las estrategias de implementación. Estas estrategias de implementación son generalizadas y no pretenden implicar períodos de tiempo concretos, ni se aplican a todas las organizaciones y situaciones.</span><span class="sxs-lookup"><span data-stu-id="d7bb0-p102">This article contains assumptions and simplifications for a consistent way to describe the deployment strategies. These deployment strategies are generalized and are not meant to imply any specific timeframes, nor are they meant to apply to all organizations and situations.</span></span>
>

## <a name="elements-of-it-project-management-for-typical-enterprise-organizations"></a><span data-ttu-id="d7bb0-113">Elementos de la administración de proyectos de TI para organizaciones empresariales típicas</span><span class="sxs-lookup"><span data-stu-id="d7bb0-113">Elements of IT project management for typical enterprise organizations</span></span>

<span data-ttu-id="d7bb0-p103">La infraestructura de TI incluye servicios back-end y la implementación de funcionalidades nuevas o mejoradas o la instalación de software en los usuarios finales. Los departamentos de TI suelen implementar los elementos de una infraestructura de TI de forma metódica. Un enfoque para la implementación correcta de un elemento de la infraestructura de TI consiste en:</span><span class="sxs-lookup"><span data-stu-id="d7bb0-p103">IT infrastructure includes both backend services and the rollout of new or improved capabilities or installed software to end users. IT departments typically deploy elements of an IT infrastructure in a methodical way. One approach to the successful deployment of an element of IT infrastructure consists of:</span></span>

- <span data-ttu-id="d7bb0-117">Una implementación piloto</span><span class="sxs-lookup"><span data-stu-id="d7bb0-117">A pilot rollout</span></span> 

  <span data-ttu-id="d7bb0-118">Incluye la configuración de la infraestructura inicial y la implementación en un grupo piloto de usuarios, así como las pruebas y las modificaciones posteriores en la configuración de la infraestructura.</span><span class="sxs-lookup"><span data-stu-id="d7bb0-118">This includes initial infrastructure configuration and rollout to a pilot set of users, testing, and subsequent modifications to the infrastructure configuration.</span></span>

- <span data-ttu-id="d7bb0-119">Una implementación de usuarios</span><span class="sxs-lookup"><span data-stu-id="d7bb0-119">A user rollout</span></span>

  <span data-ttu-id="d7bb0-120">Incluye la implementación en el resto de la organización en función de las regiones, los departamentos o los grupos o con otros tipos de propagación sistemática de la configuración o el software.</span><span class="sxs-lookup"><span data-stu-id="d7bb0-120">This includes the rollout to the rest of your organization based on regions, departments, groups, or other types of systematic propagation of configuration or software.</span></span>

<span data-ttu-id="d7bb0-121">El conjunto de usuarios de la implementación piloto no es igual al de la implementación de usuarios.</span><span class="sxs-lookup"><span data-stu-id="d7bb0-121">The set of users in the pilot rollout are not the same as those in the user rollout.</span></span>

<span data-ttu-id="d7bb0-122">En este artículo se usan los gráficos siguientes para representar estas definiciones:</span><span class="sxs-lookup"><span data-stu-id="d7bb0-122">This article uses the following graphics to depict these definitions:</span></span> 

![Los gráficos para representar las definiciones de implementación piloto y de usuarios](./media/deployment-strategies-microsoft-365-enterprise/definitions.png) 

<span data-ttu-id="d7bb0-124">El sombreado del gráfico de implementación de usuarios indica el porcentaje en toda la organización de 0 % a 100 % con un enfoque estructurado o metódico, como grupos, departamentos o regiones.</span><span class="sxs-lookup"><span data-stu-id="d7bb0-124">The shading for the user rollout graphic indicates the percentage across your organization from 0% to 100% using a structured or methodical approach such as groups, departments, or regions.</span></span>

## <a name="deployment-strategies"></a><span data-ttu-id="d7bb0-125">Estrategias de implementación</span><span class="sxs-lookup"><span data-stu-id="d7bb0-125">Deployment strategies</span></span>

<span data-ttu-id="d7bb0-126">Tenga en cuenta las siguientes estrategias de implementación:</span><span class="sxs-lookup"><span data-stu-id="d7bb0-126">Consider the following deployment strategies:</span></span>

- <span data-ttu-id="d7bb0-127">Implementación de serie:</span><span class="sxs-lookup"><span data-stu-id="d7bb0-127">Serial deployment</span></span>
- <span data-ttu-id="d7bb0-128">Implementación paralela con implementación de usuarios que no se superpone</span><span class="sxs-lookup"><span data-stu-id="d7bb0-128">Parallel deployment with non-overlapping user rollout</span></span>
- <span data-ttu-id="d7bb0-129">Implementación paralela con implementación de usuarios que se superpone</span><span class="sxs-lookup"><span data-stu-id="d7bb0-129">Parallel deployment with overlapping user rollout</span></span>
- <span data-ttu-id="d7bb0-130">Infraestructura inicial e implementación de la configuración completa</span><span class="sxs-lookup"><span data-stu-id="d7bb0-130">Up-front infrastructure and rollout of the end-to-end configuration</span></span>

### <a name="serial-deployment"></a><span data-ttu-id="d7bb0-131">Implementación de serie:</span><span class="sxs-lookup"><span data-stu-id="d7bb0-131">Serial deployment</span></span>

<span data-ttu-id="d7bb0-p104">Con una implementación de serie, se distribuye completamente una fase, lo que permite que la fase llegue a completar el 100 % de la implementación para todos los usuarios antes de pasar a la siguiente. Aquí tiene algunos de los motivos por los que se podría implementar de esta forma:</span><span class="sxs-lookup"><span data-stu-id="d7bb0-p104">With a serial deployment, you completely roll out a phase, allowing the phase to reach 100% completion of deployment to all of your users, before moving on to the next one. Here are some of the reasons why you might deploy this way:</span></span>

- <span data-ttu-id="d7bb0-134">Mitigación de riesgos</span><span class="sxs-lookup"><span data-stu-id="d7bb0-134">Risk mitigation</span></span>
- <span data-ttu-id="d7bb0-135">Restricciones de recursos</span><span class="sxs-lookup"><span data-stu-id="d7bb0-135">Resourcing constraints</span></span>
- <span data-ttu-id="d7bb0-136">Ciclos de financiación del departamento de TI</span><span class="sxs-lookup"><span data-stu-id="d7bb0-136">IT department funding cycles</span></span>
- <span data-ttu-id="d7bb0-137">Dependencias de la tecnología de TI</span><span class="sxs-lookup"><span data-stu-id="d7bb0-137">IT technology dependencies</span></span>
- <span data-ttu-id="d7bb0-138">Administración de cambios empresariales y resistencia del usuario final</span><span class="sxs-lookup"><span data-stu-id="d7bb0-138">Business change management and end-user resistance</span></span>

<span data-ttu-id="d7bb0-139">Este diagrama de Gantt muestra una implementación de serie simplificada de las fases 2 a la 6 de la infraestructura base de Microsoft 365 para empresas.</span><span class="sxs-lookup"><span data-stu-id="d7bb0-139">This Gantt chart shows a simplified serial deployment of phases 2-6 of the foundation infrastructure for Microsoft 365 Enterprise.</span></span>

![La implementación en serie de las fases 2-6 de la infraestructura básica](./media/deployment-strategies-microsoft-365-enterprise/serial.png) 
 
<span data-ttu-id="d7bb0-141">Para simplificar la explicación y el ejemplo, se presupone que se tardará lo mismo en cada fase y cada segmento de implementación en cada fase.</span><span class="sxs-lookup"><span data-stu-id="d7bb0-141">To simplify the discussion and example, each phase and deployment segment within each phase are assumed to take the same amount of time.</span></span>

>[!Note]
><span data-ttu-id="d7bb0-p105">Fase 1: La creación de la red de la infraestructura base de Microsoft 365 para empresas es una fase exclusiva del departamento de TI. Los usuarios obtienen las ventajas de una conectividad optimizada con los recursos de nube de Microsoft pero no están obligados a conseguirla.</span><span class="sxs-lookup"><span data-stu-id="d7bb0-p105">Phase 1: Networking of the Microsoft 365 Enterprise Foundation Infrastructure is an IT department-only phase. Users reap the benefits of optimized connectivity to Microsoft’s cloud resources but are not imposed upon to achieve it.</span></span>
>

<span data-ttu-id="d7bb0-144">Esta es una experiencia de usuario piloto simplificada como un ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d7bb0-144">Here’s a simplified pilot user experience as an example:</span></span>

- <span data-ttu-id="d7bb0-p106">En diciembre, necesito usar mi smartphone para MFA. (Identidad)</span><span class="sxs-lookup"><span data-stu-id="d7bb0-p106">In December, I need to use my smart phone for MFA. (Identity)</span></span>
- <span data-ttu-id="d7bb0-p107">En marzo, instalo Windows 10 Enterprise en el escritorio de Windows 8.1. (Windows 10 Enterprise)</span><span class="sxs-lookup"><span data-stu-id="d7bb0-p107">In March, I get Windows 10 Enterprise installed on my Windows 8.1 desktop. (Windows 10 Enterprise)</span></span>
- <span data-ttu-id="d7bb0-p108">En junio, instalo Office 365 ProPlus en reemplazo de Office 2013. (Office 365 ProPlus)</span><span class="sxs-lookup"><span data-stu-id="d7bb0-p108">In June, I get Office 365 ProPlus installed, replacing Office 2013. (Office 365 ProPlus)</span></span>
- <span data-ttu-id="d7bb0-151">En septiembre, obtengo la inscripción de dispositivos y las directivas de aplicaciones y dispositivos aplicadas.</span><span class="sxs-lookup"><span data-stu-id="d7bb0-151">In September, I get device enrollment and app and device policies applied.</span></span> <span data-ttu-id="d7bb0-152">(Administración de dispositivos móviles)</span><span class="sxs-lookup"><span data-stu-id="d7bb0-152">(Mobile device management)</span></span>
- <span data-ttu-id="d7bb0-p110">En diciembre, instalo el cliente de Azure Information Protection y me entreno en la aplicación de etiquetas a los documentos. (Information Protection)</span><span class="sxs-lookup"><span data-stu-id="d7bb0-p110">In December, I get the Azure Information Protection client installed and get trained on how to apply labels to documents. (Information protection)</span></span>

<span data-ttu-id="d7bb0-155">El resultado es una cadencia de 90 días entre implementaciones piloto sucesivas.</span><span class="sxs-lookup"><span data-stu-id="d7bb0-155">The result is a 90-day cadence between successive pilot rollouts.</span></span>

<span data-ttu-id="d7bb0-156">Esta es una experiencia de usuario final simplificada como un ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d7bb0-156">Here’s a simplified end-user experience as an example:</span></span>

- <span data-ttu-id="d7bb0-p111">En enero, necesito usar mi smartphone para MFA. (Identidad)</span><span class="sxs-lookup"><span data-stu-id="d7bb0-p111">In January, I need to use my smart phone for MFA. (Identity)</span></span>
- <span data-ttu-id="d7bb0-p112">En abril, instalo Windows 10 Enterprise en el escritorio de Windows 8.1. (Windows 10 Enterprise)</span><span class="sxs-lookup"><span data-stu-id="d7bb0-p112">In April, I get Windows 10 Enterprise installed on my Windows 8.1 desktop. (Windows 10 Enterprise)</span></span>
- <span data-ttu-id="d7bb0-p113">En julio, instalo Office 365 ProPlus en reemplazo de Office 2013. (Office 365 ProPlus)</span><span class="sxs-lookup"><span data-stu-id="d7bb0-p113">In July, I get Office 365 ProPlus installed, replacing Office 2013. (Office 365 ProPlus)</span></span>
- <span data-ttu-id="d7bb0-163">En octubre, obtengo la inscripción de dispositivos y las directivas de aplicaciones y dispositivos aplicadas.</span><span class="sxs-lookup"><span data-stu-id="d7bb0-163">In October, I get device enrollment and app and device policies applied.</span></span> <span data-ttu-id="d7bb0-164">(Administración de dispositivos móviles)</span><span class="sxs-lookup"><span data-stu-id="d7bb0-164">(Mobile device management)</span></span>
- <span data-ttu-id="d7bb0-p115">En enero del año siguiente, instalo el cliente de Azure Information Protection y me entreno en la aplicación de etiquetas a los documentos. (Information Protection)</span><span class="sxs-lookup"><span data-stu-id="d7bb0-p115">In January of the following year, I get the Azure Information Protection client installed and get trained on how to apply labels to documents. (Information protection)</span></span>

<span data-ttu-id="d7bb0-167">El resultado es una cadencia de 90 días entre implementaciones sucesivas de usuarios.</span><span class="sxs-lookup"><span data-stu-id="d7bb0-167">The result is a 90-day cadence between successive user rollouts.</span></span>

<span data-ttu-id="d7bb0-168">La desventaja de esta estrategia de implementación es que se puede tardar mucho en implementar por completo la infraestructura base de Microsoft 365 para empresas.</span><span class="sxs-lookup"><span data-stu-id="d7bb0-168">The disadvantage to this deployment strategy is that it can take a long time to fully deploy the Microsoft 365 Enterprise foundation infrastructure.</span></span>

### <a name="parallel-deployment-with-non-overlapping-user-rollout-parallel-1"></a><span data-ttu-id="d7bb0-169">Implementación paralela con implementación de usuarios que no se superpone (paralela 1)</span><span class="sxs-lookup"><span data-stu-id="d7bb0-169">Parallel deployment with non-overlapping user rollout (Parallel 1)</span></span>

<span data-ttu-id="d7bb0-p116">En esta estrategia, se inicia la implementación piloto de la siguiente fase durante la última parte de la implementación de usuarios de la fase actual. Aquí tiene la implementación de las fases de la 2 a la 6 cuando la implementación piloto se produce al concluir la implementación de usuarios de la fase anterior.</span><span class="sxs-lookup"><span data-stu-id="d7bb0-p116">For this deployment strategy, you start the pilot rollout of the next phase during the last part of the user rollout of the current phase. Here is the deployment of phases 2-6 when the pilot rollout occurs as the user rollout of the previous phase is wrapping up.</span></span>

![Implementación paralela de las fases 2-6 con implementación de usuarios que no se superpone](./media/deployment-strategies-microsoft-365-enterprise/parallel1.png) 
 
<span data-ttu-id="d7bb0-p117">El resultado final es que la implementación de usuarios de la fase actual se completa en toda la organización antes de que empiece la siguiente. Los usuarios que no están en la implementación piloto no se enfrentan a las implementaciones de varias fases al mismo tiempo, pero las implementaciones piloto se realizan en paralelo con las implementaciones de usuarios.</span><span class="sxs-lookup"><span data-stu-id="d7bb0-p117">The end result is that user rollout for the current phase completes across your organization before the next one starts. Users that are not in pilot rollouts are not dealing with the rollouts of multiple phases at the same time, but pilot rollouts are done in parallel with user rollouts.</span></span>

<span data-ttu-id="d7bb0-175">Esta es una experiencia de usuario piloto simplificada como un ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d7bb0-175">Here’s a simplified pilot user experience as an example:</span></span>

- <span data-ttu-id="d7bb0-p118">En diciembre, necesito usar mi smartphone para MFA. (Identidad)</span><span class="sxs-lookup"><span data-stu-id="d7bb0-p118">In December, I need to use my smart phone for MFA. (Identity)</span></span>
- <span data-ttu-id="d7bb0-p119">En febrero, instalo Windows 10 Enterprise en el escritorio de Windows 8.1. (Windows 10 Enterprise)</span><span class="sxs-lookup"><span data-stu-id="d7bb0-p119">In February, I get Windows 10 Enterprise installed on my Windows 8.1 desktop. (Windows 10 Enterprise)</span></span>
- <span data-ttu-id="d7bb0-p120">En abril, instalo Office 365 ProPlus en reemplazo de Office 2013. (Office 365 ProPlus)</span><span class="sxs-lookup"><span data-stu-id="d7bb0-p120">In April, I get Office 365 ProPlus installed, replacing Office 2013. (Office 365 ProPlus)</span></span>
- <span data-ttu-id="d7bb0-182">En junio, obtengo la inscripción de dispositivos y las directivas de aplicaciones y dispositivos aplicadas.</span><span class="sxs-lookup"><span data-stu-id="d7bb0-182">In June, I get device enrollment and app and device policies applied.</span></span> <span data-ttu-id="d7bb0-183">(Administración de dispositivos móviles)</span><span class="sxs-lookup"><span data-stu-id="d7bb0-183">(Mobile device management)</span></span>
- <span data-ttu-id="d7bb0-p122">En agosto, instalo el cliente de Azure Information Protection y me entreno en la aplicación de etiquetas a los documentos. (Information Protection)</span><span class="sxs-lookup"><span data-stu-id="d7bb0-p122">In August, I get the Azure Information Protection client installed and get trained on how to apply labels to documents. (Information protection)</span></span>

<span data-ttu-id="d7bb0-186">El resultado es una cadencia de 60 días entre implementaciones piloto sucesivas.</span><span class="sxs-lookup"><span data-stu-id="d7bb0-186">The result is a 60-day cadence between successive pilot rollouts.</span></span>

<span data-ttu-id="d7bb0-187">Esta es una experiencia de usuario final simplificada como un ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d7bb0-187">Here’s a simplified end-user experience as an example:</span></span>

- <span data-ttu-id="d7bb0-p123">En enero, necesito usar mi smartphone para MFA. (Identidad)</span><span class="sxs-lookup"><span data-stu-id="d7bb0-p123">In January, I need to use my smart phone for MFA. (Identity)</span></span>
- <span data-ttu-id="d7bb0-p124">En marzo, instalo Windows 10 Enterprise en el escritorio de Windows 8.1. (Windows 10 Enterprise)</span><span class="sxs-lookup"><span data-stu-id="d7bb0-p124">In March, I get Windows 10 Enterprise installed on my Windows 8.1 desktop. (Windows 10 Enterprise)</span></span>
- <span data-ttu-id="d7bb0-p125">En mayo, instalo Office 365 ProPlus en reemplazo de Office 2013. (Office 365 ProPlus)</span><span class="sxs-lookup"><span data-stu-id="d7bb0-p125">In May, I get Office 365 ProPlus installed, replacing Office 2013. (Office 365 ProPlus)</span></span>
- <span data-ttu-id="d7bb0-194">En julio, obtengo la inscripción de dispositivos y las directivas de aplicaciones y dispositivos aplicadas.</span><span class="sxs-lookup"><span data-stu-id="d7bb0-194">In July, I get device enrollment and app and device policies applied.</span></span> <span data-ttu-id="d7bb0-195">(Administración de dispositivos móviles)</span><span class="sxs-lookup"><span data-stu-id="d7bb0-195">(Mobile device management)</span></span>
- <span data-ttu-id="d7bb0-p127">En septiembre, instalo el cliente de Azure Information Protection y me entreno en la aplicación de etiquetas a los documentos. (Information Protection)</span><span class="sxs-lookup"><span data-stu-id="d7bb0-p127">In September, I get the Azure Information Protection client installed and get trained on how to apply labels to documents. (Information protection)</span></span>

<span data-ttu-id="d7bb0-198">El resultado es una cadencia de 60 días entre implementaciones sucesivas de usuarios.</span><span class="sxs-lookup"><span data-stu-id="d7bb0-198">The result is a 60-day cadence between successive user rollouts.</span></span>

<span data-ttu-id="d7bb0-199">La ventaja de esta estrategia de implementación es que se puede tardar menos en implementar por completo la infraestructura base de Microsoft 365 para empresas, sin que el departamento de TI y los usuarios tengan que enfrentarse a varias implementaciones a la vez.</span><span class="sxs-lookup"><span data-stu-id="d7bb0-199">The advantage to this deployment strategy is that it can take less time to fully deploy the Microsoft 365 Enterprise foundation infrastructure, without having your IT department and users deal with multiple rollouts the same time.</span></span>

### <a name="parallel-deployment-with-overlapping-user-rollout-parallel-2"></a><span data-ttu-id="d7bb0-200">Implementación paralela con implementación de usuarios que se superpone (paralela 2)</span><span class="sxs-lookup"><span data-stu-id="d7bb0-200">Parallel deployment with overlapping user rollout (Parallel 2)</span></span>

<span data-ttu-id="d7bb0-201">Con esta estrategia de implementación, se inicia:</span><span class="sxs-lookup"><span data-stu-id="d7bb0-201">For this deployment strategy, you start the:</span></span>

- <span data-ttu-id="d7bb0-202">La implementación piloto de la fase siguiente se realiza durante la última parte de la implementación de usuarios de la fase actual.</span><span class="sxs-lookup"><span data-stu-id="d7bb0-202">Pilot rollout of the next phase during the last part of the user rollout of the current phase.</span></span>
- <span data-ttu-id="d7bb0-203">La implementación por parte de los usuarios de la siguiente fase durante la implementación de los usuarios de la fase actual, de modo que no haya ningún usuario trabajando con las implementaciones de varias fases al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="d7bb0-203">User rollout of the next phase during the user rollout of the current phase in such a way that no user is dealing with the rollouts of multiple phases at the same time.</span></span> <span data-ttu-id="d7bb0-204">Esto supone que está implementando cada fase de la infraestructura de Foundation de la misma manera, con regiones, departamentos u otros grupos.</span><span class="sxs-lookup"><span data-stu-id="d7bb0-204">This assumes that you are rolling out each phase of the foundation infrastructure in the same way, using regions, departments, or other groupings.</span></span>

<span data-ttu-id="d7bb0-205">Aquí tiene una comparación simplificada entre distintas estrategias de implementación.</span><span class="sxs-lookup"><span data-stu-id="d7bb0-205">Here is a simplified comparison between the different deployment strategies.</span></span>

![Implementación paralela de las fases 2-6 con implementación de usuarios que se superpone](./media/deployment-strategies-microsoft-365-enterprise/parallel2.png) 

<span data-ttu-id="d7bb0-207">El resultado final es que:</span><span class="sxs-lookup"><span data-stu-id="d7bb0-207">The end result is that:</span></span>

- <span data-ttu-id="d7bb0-208">Las implementaciones piloto pasan sin pausa de una fase a la siguiente.</span><span class="sxs-lookup"><span data-stu-id="d7bb0-208">Pilot rollouts go from one phase to the next without a pause.</span></span>
- <span data-ttu-id="d7bb0-209">La implementación de usuarios de una fase comienza antes de completar la implementación de usuarios de la fase anterior, pero ningún usuario individual se distribuirá en más de una fase a la vez.</span><span class="sxs-lookup"><span data-stu-id="d7bb0-209">The user rollout for a phase begins before the completion of the user rollout of the previous phase, but no individual user is rolling out more than one phase at a time.</span></span>

<span data-ttu-id="d7bb0-210">Esta es una experiencia de usuario piloto simplificada como un ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d7bb0-210">Here’s a simplified pilot user experience as an example:</span></span>

- <span data-ttu-id="d7bb0-p129">En diciembre, necesito usar mi smartphone para MFA. (Identidad)</span><span class="sxs-lookup"><span data-stu-id="d7bb0-p129">In December, I need to use my smart phone for MFA. (Identity)</span></span>
- <span data-ttu-id="d7bb0-p130">En enero, instalo Windows 10 Enterprise en el escritorio de Windows 8.1. (Windows 10 Enterprise)</span><span class="sxs-lookup"><span data-stu-id="d7bb0-p130">In January, I get Windows 10 Enterprise installed on my Windows 8.1 desktop. (Windows 10 Enterprise)</span></span>
- <span data-ttu-id="d7bb0-p131">En febrero, instalo Office 365 ProPlus en reemplazo de Office 2013. (Office 365 ProPlus)</span><span class="sxs-lookup"><span data-stu-id="d7bb0-p131">In February, I get Office 365 ProPlus installed, replacing Office 2013. (Office 365 ProPlus)</span></span>
- <span data-ttu-id="d7bb0-217">En marzo, obtengo la inscripción de dispositivos y las directivas de aplicaciones y dispositivos aplicadas.</span><span class="sxs-lookup"><span data-stu-id="d7bb0-217">In March, I get device enrollment and app and device policies applied.</span></span> <span data-ttu-id="d7bb0-218">(Administración de dispositivos móviles)</span><span class="sxs-lookup"><span data-stu-id="d7bb0-218">(Mobile device management)</span></span>
- <span data-ttu-id="d7bb0-p133">En abril, instalo el cliente de Azure Information Protection y me entreno en la aplicación de etiquetas a los documentos. (Information Protection)</span><span class="sxs-lookup"><span data-stu-id="d7bb0-p133">In April, I get the Azure Information Protection client installed and get trained on how to apply labels to documents. (Information protection)</span></span>

<span data-ttu-id="d7bb0-221">El resultado es una cadencia de 30 días entre implementaciones piloto sucesivas.</span><span class="sxs-lookup"><span data-stu-id="d7bb0-221">The result is a 30-day cadence between successive pilot rollouts.</span></span>

<span data-ttu-id="d7bb0-222">Esta es una experiencia de usuario final simplificada como un ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d7bb0-222">Here’s a simplified end-user experience as an example:</span></span>

- <span data-ttu-id="d7bb0-p134">En enero, necesito usar mi smartphone para MFA. (Identidad)</span><span class="sxs-lookup"><span data-stu-id="d7bb0-p134">In January, I need to use my smart phone for MFA. (Identity)</span></span>
- <span data-ttu-id="d7bb0-p135">En febrero, instalo Windows 10 Enterprise en el escritorio de Windows 8.1. (Windows 10 Enterprise)</span><span class="sxs-lookup"><span data-stu-id="d7bb0-p135">In February, I get Windows 10 Enterprise installed on my Windows 8.1 desktop. (Windows 10 Enterprise)</span></span>
- <span data-ttu-id="d7bb0-p136">En marzo, instalo Office 365 ProPlus en reemplazo de Office 2013. (Office 365 ProPlus)</span><span class="sxs-lookup"><span data-stu-id="d7bb0-p136">In March, I get Office 365 ProPlus installed, replacing Office 2013. (Office 365 ProPlus)</span></span>
- <span data-ttu-id="d7bb0-229">En abril, obtengo la inscripción de dispositivos y las directivas de aplicaciones y dispositivos aplicadas.</span><span class="sxs-lookup"><span data-stu-id="d7bb0-229">In April, I get device enrollment and app and device policies applied.</span></span> <span data-ttu-id="d7bb0-230">(Administración de dispositivos móviles)</span><span class="sxs-lookup"><span data-stu-id="d7bb0-230">(Mobile device management)</span></span>
- <span data-ttu-id="d7bb0-p138">En mayo, instalo el cliente de Azure Information Protection y me entreno en la aplicación de etiquetas a los documentos. (Information Protection)</span><span class="sxs-lookup"><span data-stu-id="d7bb0-p138">In May, I get the Azure Information Protection client installed and get trained on how to apply labels to documents. (Information protection)</span></span>

<span data-ttu-id="d7bb0-233">El resultado es una cadencia de 30 días entre implementaciones sucesivas de usuarios.</span><span class="sxs-lookup"><span data-stu-id="d7bb0-233">The result is a 30-day cadence between successive user rollouts.</span></span>

<span data-ttu-id="d7bb0-234">La ventaja de esta estrategia de implementación es que puede tardar menos en completarse la implementación de la infraestructura de base de Microsoft 365 para empresas, sin necesidad de que los usuarios finales se ocupen de varias implementaciones de forma simultánea.</span><span class="sxs-lookup"><span data-stu-id="d7bb0-234">The advantage to this deployment strategy is that it can take even less time to fully deploy the Microsoft 365 Enterprise foundation infrastructure, still without having end-users deal with multiple rollouts the same time.</span></span> <span data-ttu-id="d7bb0-235">Sin embargo, los usuarios no pueden descansar entre fases sucesivas.</span><span class="sxs-lookup"><span data-stu-id="d7bb0-235">However, users don’t get a break between successive phases.</span></span>

### <a name="up-front-infrastructure-and-rollout-of-the-end-to-end-configuration"></a><span data-ttu-id="d7bb0-236">Infraestructura inicial e implementación de la configuración completa</span><span class="sxs-lookup"><span data-stu-id="d7bb0-236">Up-front infrastructure and rollout of the end-to-end configuration</span></span>

<span data-ttu-id="d7bb0-237">En el caso de organizaciones más pequeñas con la posibilidad de comprimir las fases de la 2 a la 6 en un solo segmento de implementación, la implementación resultante tiene el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="d7bb0-237">For smaller organizations with the ability to compress phases 2-6 into a single deployment segment, the resulting deployment looks like this:</span></span>
 
![Infraestructura inicial e implementación de la configuración completa](./media/deployment-strategies-microsoft-365-enterprise/up-front.png) 

<span data-ttu-id="d7bb0-p140">El departamento de TI configura la infraestructura de las fases 2 a la 6, luego la distribuye a los usuarios piloto para comprobar la funcionalidad completa. Por ejemplo, los usuarios piloto obtienen toda esta funcionalidad al mismo tiempo:</span><span class="sxs-lookup"><span data-stu-id="d7bb0-p140">The IT department configures the infrastructure for phases 2-6, then rolls out to the pilot users to check for the end-to-end functionality. For example, pilot users get all of this functionality at the same time:</span></span>

- <span data-ttu-id="d7bb0-241">MFA y otras características de identidad (identidad)</span><span class="sxs-lookup"><span data-stu-id="d7bb0-241">MFA and other identity features (Identity)</span></span>
- <span data-ttu-id="d7bb0-242">Windows 10 Enterprise en dispositivos Windows (Windows 10 Enterprise)</span><span class="sxs-lookup"><span data-stu-id="d7bb0-242">Windows 10 Enterprise on Windows devices (Windows 10 Enterprise)</span></span>
- <span data-ttu-id="d7bb0-243">Office 365 ProPlus para el conjunto de aplicaciones de Office (Office 365 ProPlus)</span><span class="sxs-lookup"><span data-stu-id="d7bb0-243">Office 365 ProPlus for the Office suite (Office 365 ProPlus)</span></span>
- <span data-ttu-id="d7bb0-244">Directivas de aplicaciones y dispositivos (administración de dispositivos móviles)</span><span class="sxs-lookup"><span data-stu-id="d7bb0-244">App and device policies (Mobile device management)</span></span>
- <span data-ttu-id="d7bb0-245">Instalación del cliente de Azure Information Protection y entrenamiento en la aplicación de etiquetas a los documentos (Information Protection)</span><span class="sxs-lookup"><span data-stu-id="d7bb0-245">Azure Information Protection client installed and training on how to apply labels to documents (Information protection)</span></span>

<span data-ttu-id="d7bb0-246">Tras finalizar la implementación piloto, empiece la implementación de usuarios en la que cada usuario obtiene todas las funciones la vez.</span><span class="sxs-lookup"><span data-stu-id="d7bb0-246">Once the pilot rollout is concluded, the user rollout begins in which each user gets all the functionality the same time.</span></span>

## <a name="next-step"></a><span data-ttu-id="d7bb0-247">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="d7bb0-247">Next step</span></span>

<span data-ttu-id="d7bb0-248">Inicio de la implementación de Microsoft 365 para empresas con la [infraestructura base](deploy-foundation-infrastructure.md).</span><span class="sxs-lookup"><span data-stu-id="d7bb0-248">Start your deployment of Microsoft 365 Enterprise with the [foundation infrastructure](deploy-foundation-infrastructure.md).</span></span>
