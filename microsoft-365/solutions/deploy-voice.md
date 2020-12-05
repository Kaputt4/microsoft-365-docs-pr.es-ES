---
title: Implementación de voz en Microsoft 365
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-overview
- m365solution-voice
- M365-voice
ms.custom:
- M365solutions
- seo-marvel-jun2020
f1.keywords: NOCSH
description: Obtenga información sobre cómo elegir e implementar la solución de voz de Teams adecuada para su organización.
ms.openlocfilehash: b5dda0ed3d9310c3c43052b9bac4996802e0ed2f
ms.sourcegitcommit: e53234b1f64ebca00e121da1706c02b3337c35f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "49580916"
---
# <a name="plan-and-deploy-a-teams-voice-solution"></a><span data-ttu-id="fd79c-103">Planeación e implementación de una solución de voz de Teams</span><span class="sxs-lookup"><span data-stu-id="fd79c-103">Plan and deploy a Teams voice solution</span></span>

<span data-ttu-id="fd79c-104">Una solución de voz de Teams permite a los usuarios de su organización realizar llamadas tanto dentro como fuera de la organización.</span><span class="sxs-lookup"><span data-stu-id="fd79c-104">A Teams voice solution enables people in your organization to make calls both within and outside your organization.</span></span> <span data-ttu-id="fd79c-105">Una solución de voz completa consiste en Teams, sistema telefónico de Microsoft y opciones para conectarse a la red telefónica conmutada (RTC).</span><span class="sxs-lookup"><span data-stu-id="fd79c-105">A complete voice solution consists of Teams, Microsoft Phone System, and a choice of options for connecting to the Public Switched Telephone Network (PSTN).</span></span>

![Introducción a las soluciones de voz de Microsoft Teams](..\media\solutions-architecture-center\voice-concepts.png)

<span data-ttu-id="fd79c-107">El sistema telefónico proporciona capacidades completas de central de conmutación (PBX) para su organización.</span><span class="sxs-lookup"><span data-stu-id="fd79c-107">Phone System provides complete Private Branch Exchange (PBX) capabilities for your organization.</span></span> <span data-ttu-id="fd79c-108">Las llamadas entre usuarios de su organización, independientemente de su ubicación geográfica, se administran internamente en el sistema telefónico, con lo que se eliminan los costos de larga distancia de estas llamadas internas.</span><span class="sxs-lookup"><span data-stu-id="fd79c-108">Calls between users in your organization--no matter their geographic location--are handled internally within Phone System thereby removing long-distance costs on these internal calls.</span></span>  

<span data-ttu-id="fd79c-109">Al conectar el sistema telefónico a la red telefónica conmutada (RTC), los usuarios de Microsoft Teams también pueden realizar llamadas fuera de su organización.</span><span class="sxs-lookup"><span data-stu-id="fd79c-109">By connecting Phone System to the Public Switched Telephone Network (PSTN), your Teams users can make calls outside your organization as well.</span></span>

<span data-ttu-id="fd79c-110">Esta guía de la solución le ayudará a:</span><span class="sxs-lookup"><span data-stu-id="fd79c-110">This solution guidance helps you to:</span></span>

- <span data-ttu-id="fd79c-111">Elegir la solución de voz adecuada para su organización</span><span class="sxs-lookup"><span data-stu-id="fd79c-111">Choose the voice solution that is right for your organization</span></span>
- <span data-ttu-id="fd79c-112">Implementar la solución de voz seleccionada</span><span class="sxs-lookup"><span data-stu-id="fd79c-112">Deploy the voice solution you selected</span></span>

<span data-ttu-id="fd79c-113">Siga estos pasos para elegir, planear y configurar la solución de voz:</span><span class="sxs-lookup"><span data-stu-id="fd79c-113">Follow these steps to choose, plan, and configure your voice solution:</span></span>

![Elegir la solución de voz](..\media\solutions-architecture-center\voice-solutions-overview-1.png)

1. [<span data-ttu-id="fd79c-115">Elegir la solución de voz</span><span class="sxs-lookup"><span data-stu-id="fd79c-115">Choose your voice solution</span></span>](https://docs.microsoft.com/MicrosoftTeams/cloud-voice-landing-page?toc=/microsoft-365/solutions/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json)

2. [<span data-ttu-id="fd79c-116">Configurar el Sistema telefónico</span><span class="sxs-lookup"><span data-stu-id="fd79c-116">Set up Phone System</span></span>](https://docs.microsoft.com/microsoftteams/setting-up-your-phone-system?toc=/microsoft-365/solutions/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json)

3. <span data-ttu-id="fd79c-117">Configure la conectividad con RTC eligiendo una, o una combinación de las siguientes:</span><span class="sxs-lookup"><span data-stu-id="fd79c-117">Set up PSTN connectivity by choosing one, or a combination, of the following:</span></span>
   - <span data-ttu-id="fd79c-118">[Plan de llamada](https://docs.microsoft.com/microsoftteams/set-up-calling-plans?toc=/microsoft-365/solutions/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json) : solución todo en la nube de Microsoft con Microsoft como operador de RTC</span><span class="sxs-lookup"><span data-stu-id="fd79c-118">[Calling Plan](https://docs.microsoft.com/microsoftteams/set-up-calling-plans?toc=/microsoft-365/solutions/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json) - Microsoft's all-in-the-cloud solution with Microsoft as your PSTN carrier</span></span>
   - <span data-ttu-id="fd79c-119">[Enrutamiento directo](https://docs.microsoft.com/microsoftteams/direct-routing-configure?toc=/microsoft-365/solutions/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json) : Use el enrutamiento directo para conectar su propio operador de RTC a Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="fd79c-119">[Direct Routing](https://docs.microsoft.com/microsoftteams/direct-routing-configure?toc=/microsoft-365/solutions/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json) - Use Direct Routing to connect your own PSTN carrier to Teams</span></span> 

<span data-ttu-id="fd79c-120">Además, es posible que desee leer sobre cómo una corporación multinacional de gran tamaño ha migrado a una solución de voz de Microsoft Teams en el [caso práctico de Contoso](https://docs.microsoft.com/MicrosoftTeams/voice-case-study-overview?toc=/microsoft-365/solutions/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json).</span><span class="sxs-lookup"><span data-stu-id="fd79c-120">In addition, you might want read about how a large, multi-national corporation migrated to a Teams voice solution in the [Contoso case study](https://docs.microsoft.com/MicrosoftTeams/voice-case-study-overview?toc=/microsoft-365/solutions/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json).</span></span>

<span data-ttu-id="fd79c-121">Para obtener información sobre las licencias necesarias, consulte lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="fd79c-121">For information about required licenses, see the following:</span></span>

- [<span data-ttu-id="fd79c-122">Licencias de complementos de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fd79c-122">Teams add-on licenses</span></span>](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing?tabs=enterprise#what-voice-features-are-available-with-my-plan/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json)

- [<span data-ttu-id="fd79c-123">Requisitos de licencia de enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="fd79c-123">Direct Routing licensing requirements</span></span>](https://docs.microsoft.com/microsoftteams/direct-routing-plan#licensing-and-other-requirements/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json)
