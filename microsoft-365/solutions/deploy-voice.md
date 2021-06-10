---
title: Implementar voz en Microsoft 365
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
description: Obtenga información sobre cómo elegir e implementar la solución Teams de voz adecuada para su organización.
ms.openlocfilehash: ede8075767e9d0a80123ac742403f8a4d171392e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918387"
---
# <a name="plan-and-deploy-a-teams-voice-solution"></a><span data-ttu-id="2f37c-103">Planear e implementar una solución de voz de Teams</span><span class="sxs-lookup"><span data-stu-id="2f37c-103">Plan and deploy a Teams voice solution</span></span>

<span data-ttu-id="2f37c-104">Una Teams de voz permite a los usuarios de la organización realizar llamadas tanto dentro como fuera de la organización.</span><span class="sxs-lookup"><span data-stu-id="2f37c-104">A Teams voice solution enables people in your organization to make calls both within and outside your organization.</span></span> <span data-ttu-id="2f37c-105">Una solución de voz completa consta de Teams, Teléfono Microsoft system y una selección de opciones para conectarse a la red telefónica conmutada (RTC).</span><span class="sxs-lookup"><span data-stu-id="2f37c-105">A complete voice solution consists of Teams, Microsoft Phone System, and a choice of options for connecting to the Public Switched Telephone Network (PSTN).</span></span>

![Teams de soluciones de voz](..\media\solutions-architecture-center\voice-concepts.png)

<span data-ttu-id="2f37c-107">Sistema telefónico proporciona funcionalidades completas de Exchange de sucursal privada (PBX) para su organización.</span><span class="sxs-lookup"><span data-stu-id="2f37c-107">Phone System provides complete Private Branch Exchange (PBX) capabilities for your organization.</span></span> <span data-ttu-id="2f37c-108">Las llamadas entre usuarios de la organización, independientemente de su ubicación geográfica, se controlan internamente en Sistema telefónico lo que se quitan los costos de larga distancia en estas llamadas internas.</span><span class="sxs-lookup"><span data-stu-id="2f37c-108">Calls between users in your organization--no matter their geographic location--are handled internally within Phone System thereby removing long-distance costs on these internal calls.</span></span>  

<span data-ttu-id="2f37c-109">Al conectar Sistema telefónico a la red telefónica conmutada (RTC), los usuarios Teams pueden realizar llamadas fuera de la organización también.</span><span class="sxs-lookup"><span data-stu-id="2f37c-109">By connecting Phone System to the Public Switched Telephone Network (PSTN), your Teams users can make calls outside your organization as well.</span></span>

<span data-ttu-id="2f37c-110">Esta guía de solución le ayuda a:</span><span class="sxs-lookup"><span data-stu-id="2f37c-110">This solution guidance helps you to:</span></span>

- <span data-ttu-id="2f37c-111">Elija la solución de voz adecuada para su organización</span><span class="sxs-lookup"><span data-stu-id="2f37c-111">Choose the voice solution that is right for your organization</span></span>
- <span data-ttu-id="2f37c-112">Implementar la solución de voz seleccionada</span><span class="sxs-lookup"><span data-stu-id="2f37c-112">Deploy the voice solution you selected</span></span>

<span data-ttu-id="2f37c-113">Siga estos pasos para elegir, planear y configurar la solución de voz:</span><span class="sxs-lookup"><span data-stu-id="2f37c-113">Follow these steps to choose, plan, and configure your voice solution:</span></span>

![Elija su solución de voz](..\media\solutions-architecture-center\voice-solutions-overview-1.png)

1. [<span data-ttu-id="2f37c-115">Elija su solución de voz</span><span class="sxs-lookup"><span data-stu-id="2f37c-115">Choose your voice solution</span></span>](/MicrosoftTeams/cloud-voice-landing-page?bc=%2fmicrosoft-365%2fsolutions%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoft-365%2fsolutions%2ftoc.json)

2. [<span data-ttu-id="2f37c-116">Configurar el Sistema telefónico</span><span class="sxs-lookup"><span data-stu-id="2f37c-116">Set up Phone System</span></span>](/microsoftteams/setting-up-your-phone-system?bc=%2fmicrosoft-365%2fsolutions%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoft-365%2fsolutions%2ftoc.json)

3. <span data-ttu-id="2f37c-117">Configure la conectividad RTC eligiendo una o una combinación de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="2f37c-117">Set up PSTN connectivity by choosing one, or a combination, of the following:</span></span>
   - <span data-ttu-id="2f37c-118">[Plan de llamadas:](/microsoftteams/set-up-calling-plans?bc=%2fmicrosoft-365%2fsolutions%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoft-365%2fsolutions%2ftoc.json) la solución todo en la nube de Microsoft con Microsoft como proveedor de RTC</span><span class="sxs-lookup"><span data-stu-id="2f37c-118">[Calling Plan](/microsoftteams/set-up-calling-plans?bc=%2fmicrosoft-365%2fsolutions%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoft-365%2fsolutions%2ftoc.json) - Microsoft's all-in-the-cloud solution with Microsoft as your PSTN carrier</span></span>
   - <span data-ttu-id="2f37c-119">[Enrutamiento directo:](/microsoftteams/direct-routing-configure?bc=%2fmicrosoft-365%2fsolutions%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoft-365%2fsolutions%2ftoc.json) use el enrutamiento directo para conectar su propio operador RTC a Teams</span><span class="sxs-lookup"><span data-stu-id="2f37c-119">[Direct Routing](/microsoftteams/direct-routing-configure?bc=%2fmicrosoft-365%2fsolutions%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoft-365%2fsolutions%2ftoc.json) - Use Direct Routing to connect your own PSTN carrier to Teams</span></span> 

<span data-ttu-id="2f37c-120">Además, es posible que desee leer acerca de cómo una gran corporación multinacional migró a una solución de voz Teams en el caso práctico [contoso](/MicrosoftTeams/voice-case-study-overview?bc=%2fmicrosoft-365%2fsolutions%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoft-365%2fsolutions%2ftoc.json).</span><span class="sxs-lookup"><span data-stu-id="2f37c-120">In addition, you might want read about how a large, multi-national corporation migrated to a Teams voice solution in the [Contoso case study](/MicrosoftTeams/voice-case-study-overview?bc=%2fmicrosoft-365%2fsolutions%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoft-365%2fsolutions%2ftoc.json).</span></span>

<span data-ttu-id="2f37c-121">Para obtener información acerca de las licencias necesarias, vea lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2f37c-121">For information about required licenses, see the following:</span></span>

- [<span data-ttu-id="2f37c-122">Teams de complementos</span><span class="sxs-lookup"><span data-stu-id="2f37c-122">Teams add-on licenses</span></span>](/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing?bc=%2fmicrosoft-365%2fsolutions%2fbreadcrumb%2ftoc.json&tabs=enterprise#what-voice-features-are-available-with-my-plan/toc.json)

- [<span data-ttu-id="2f37c-123">Requisitos de licencias de enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="2f37c-123">Direct Routing licensing requirements</span></span>](/microsoftteams/direct-routing-plan?bc=%2fmicrosoft-365%2fsolutions%2fbreadcrumb%2ftoc.json#licensing-and-other-requirements/toc.json)