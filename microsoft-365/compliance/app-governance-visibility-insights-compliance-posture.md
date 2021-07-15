---
title: Determinación de la posición de cumplimiento de las aplicaciones
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: Determine la posición de cumplimiento de las aplicaciones.
ms.openlocfilehash: 3d7cac319c31bac40a3aad2f6b9a4c16303f6a20
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420254"
---
# <a name="determine-your-app-compliance-posture"></a><span data-ttu-id="557a9-103">Determinación de la posición de cumplimiento de las aplicaciones</span><span class="sxs-lookup"><span data-stu-id="557a9-103">Determine your app compliance posture</span></span>

><span data-ttu-id="557a9-104">*[Guía de licencias de Microsoft 365 para la seguridad y el cumplimiento](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="557a9-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="557a9-105">La gobernanza de aplicaciones de Microsoft le permite evaluar rápidamente la posición de cumplimiento de las aplicaciones de terceros, y el acceso que tienen a los datos del inquilino de Microsoft 365, desde la página de información general de gobernanza de aplicaciones del [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com/appgovernance).</span><span class="sxs-lookup"><span data-stu-id="557a9-105">Microsoft app governance allows you to quickly assess the compliance posture of the third-party apps and their access to data in your Microsoft 365 tenant from the app governance Overview page in the [Microsoft 365 Compliance Center](https://compliance.microsoft.com/appgovernance).</span></span>

![Página de información general de gobernanza de aplicaciones en el Centro de cumplimiento de Microsoft 365](..\media\manage-app-protection-governance\mapg-cc-overview.png)

>[!Note]
> <span data-ttu-id="557a9-107">Su cuenta de inicio de sesión debe tener uno de los [estos roles](app-governance-get-started.md#administrator-roles) para ver datos de gobernanza de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="557a9-107">Your sign-in account must have one of [these roles](app-governance-get-started.md#administrator-roles) to view any app governance data.</span></span>
>

<span data-ttu-id="557a9-108">En esta página, podrá ver:</span><span class="sxs-lookup"><span data-stu-id="557a9-108">From this page, you can see:</span></span>

- <span data-ttu-id="557a9-109">En relación con las aplicaciones habilitadas para OAuth que usan la API de Microsoft Graph:</span><span class="sxs-lookup"><span data-stu-id="557a9-109">For OAuth-enabled apps that use the Microsoft Graph API:</span></span>

  - <span data-ttu-id="557a9-110">Cuántas están en el inquilino</span><span class="sxs-lookup"><span data-stu-id="557a9-110">How many are in your tenant</span></span>
  - <span data-ttu-id="557a9-111">Cuántas podrían tener privilegios excesivos</span><span class="sxs-lookup"><span data-stu-id="557a9-111">How many might be overprivileged</span></span>
  - <span data-ttu-id="557a9-112">Cuántas tienen privilegios elevados</span><span class="sxs-lookup"><span data-stu-id="557a9-112">How many are high privilege</span></span>

  <span data-ttu-id="557a9-113">A partir de esta información, puede determinar el nivel de riesgo para su organización a causa de las aplicaciones con privilegios excesivos y elevados.</span><span class="sxs-lookup"><span data-stu-id="557a9-113">From this information, you can determine the level of risk to your organization by overprivileged and high privilege apps.</span></span>

- <span data-ttu-id="557a9-114">En relación con las alertas:</span><span class="sxs-lookup"><span data-stu-id="557a9-114">For alerts:</span></span>

  - <span data-ttu-id="557a9-115">Cuántas alertas activas tiene el inquilino</span><span class="sxs-lookup"><span data-stu-id="557a9-115">How many active alerts your tenant has</span></span>
  - <span data-ttu-id="557a9-116">Cuántas se basan en las detecciones de gobernanza de aplicaciones (**alertas de amenazas**)</span><span class="sxs-lookup"><span data-stu-id="557a9-116">How many are based on app governance detections (**Threat alerts**)</span></span>
  - <span data-ttu-id="557a9-117">Cuántas se basan en las directivas de aplicaciones que tiene implementadas (**alertas de directivas**)</span><span class="sxs-lookup"><span data-stu-id="557a9-117">How many are based on app policies you have in place (**Policy alerts**)</span></span>
  - <span data-ttu-id="557a9-118">Las 10 alertas más recientes</span><span class="sxs-lookup"><span data-stu-id="557a9-118">The 10 latest alerts</span></span>

  <span data-ttu-id="557a9-119">A partir de esta información, puede determinar la rapidez con la que se generan las alertas y la cantidad relativa de alertas detectadas y basadas en directivas.</span><span class="sxs-lookup"><span data-stu-id="557a9-119">From this information, you can determine how quickly alerts are being generated and the relative number of detected and policy-based alerts.</span></span>

- <span data-ttu-id="557a9-120">En relación con el acceso a los datos y los recursos:</span><span class="sxs-lookup"><span data-stu-id="557a9-120">For data and resources access:</span></span>

  - <span data-ttu-id="557a9-121">El acceso a los datos de la API de la aplicación en los últimos 90 días</span><span class="sxs-lookup"><span data-stu-id="557a9-121">The application API data access in the last 90 days</span></span>
  - <span data-ttu-id="557a9-122">El uso de los recursos principales en los últimos 90 días</span><span class="sxs-lookup"><span data-stu-id="557a9-122">The usage of the top resources in the last 90 days</span></span>

  <span data-ttu-id="557a9-123">A partir de esta información, puede determinar si hay picos anómalos en el acceso a los datos del inquilino de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="557a9-123">From this information, you can determine if there are anomalous spikes in access to the data in your Microsoft 365 tenant.</span></span>
