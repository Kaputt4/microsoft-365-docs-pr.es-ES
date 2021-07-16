---
title: Introducción a la visibilidad y la información
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
description: Introducción a la visibilidad y la información.
ms.openlocfilehash: 93be3557c32345e81c7126b669ead8edf8ebac21
ms.sourcegitcommit: 997a21b83795789cda0a6b4a77f9985a3233d0c0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/14/2021
ms.locfileid: "53430485"
---
# <a name="get-started-with-visibility-and-insights"></a><span data-ttu-id="a8281-103">Introducción a la visibilidad y la información</span><span class="sxs-lookup"><span data-stu-id="a8281-103">Get started with visibility and insights</span></span>

><span data-ttu-id="a8281-104">*[Guía de licencias de Microsoft 365 para la seguridad y el cumplimiento](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="a8281-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="a8281-105">El primer lugar para comenzar es el panel de gobernanza de aplicaciones en [https://aka.ms/appgovernance](https://aka.ms/appgovernance).</span><span class="sxs-lookup"><span data-stu-id="a8281-105">The first place to get started is the app governance dashboard at [https://aka.ms/appgovernance](https://aka.ms/appgovernance).</span></span> <span data-ttu-id="a8281-106">Tenga en cuenta que su cuenta de inicio de sesión debe tener uno de estos [roles de administrador de gobernanza de aplicaciones](app-governance-get-started.md#administrator-roles) para ver cualquier dato de gobernanza de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="a8281-106">Note that your sign-in account must have one of [these app governance administrator roles](app-governance-get-started.md#administrator-roles) to view any app governance data.</span></span>

![Página de información general de gobernanza de aplicaciones en el Centro de cumplimiento de Microsoft 365](..\media\manage-app-protection-governance\mapg-cc-overview.png)

<span data-ttu-id="a8281-108">También puede acceder al panel de gobernanza de aplicaciones desde **Centro de administración de Microsoft 365 > Centro de cumplimiento de Microsoft 365 > Gobernanza de aplicaciones > Información general**.</span><span class="sxs-lookup"><span data-stu-id="a8281-108">You can also access the app governance dashboard from **Microsoft 365 admin center > Microsoft 365 Compliance Center > App governance > Overview page**.</span></span>

## <a name="whats-available-on-the-dashboard"></a><span data-ttu-id="a8281-109">Lo que está disponible en el panel</span><span class="sxs-lookup"><span data-stu-id="a8281-109">What’s available on the dashboard</span></span>

<span data-ttu-id="a8281-110">El panel contiene un resumen de los componentes del ecosistema de aplicaciones Microsoft 365 en el usuario:</span><span class="sxs-lookup"><span data-stu-id="a8281-110">The dashboard contains a summary of the components of the Microsoft 365 app ecosystem in the tenant:</span></span>

- <span data-ttu-id="a8281-111">**Resumen de usuarios**: rel recuento de categorías de alertas y aplicaciones clave.</span><span class="sxs-lookup"><span data-stu-id="a8281-111">**Tenant summary**: The count of key app and alert categories.</span></span>
- <span data-ttu-id="a8281-112">**Alertas de directiva y detección**: las alertas activas más recientes en el usuario</span><span class="sxs-lookup"><span data-stu-id="a8281-112">**Detection and policy alerts**: The most recent active alerts in the tenant</span></span>
- <span data-ttu-id="a8281-113">**Acceso a datos y recursos**: agregue el acceso a la API de la aplicación y al uso general de los recursos principales del usuario.</span><span class="sxs-lookup"><span data-stu-id="a8281-113">**Data and resources access**: Aggregate application API access and overall usage of top resources in the tenant.</span></span> <span data-ttu-id="a8281-114">Pase el mouse por cada columna de mes en el gráfico para ver el valor correspondiente.</span><span class="sxs-lookup"><span data-stu-id="a8281-114">Mouse over each month column in the graph to see the corresponding value.</span></span>
- <span data-ttu-id="a8281-115">**Mejore la protección y la gobernanza de sus aplicaciones**: acciones recomendadas tales como la creación de una directiva de permisos o de uso de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="a8281-115">**Improve your app protection and governance**: Recommended actions such as creating an app usage or permissions policy.</span></span>
- <span data-ttu-id="a8281-116">**Principales aplicaciones por categorías**: las aplicaciones principales ordenadas por estas categorías:</span><span class="sxs-lookup"><span data-stu-id="a8281-116">**Top apps by categories**: The top apps sorted by these categories:</span></span>
  
  - <span data-ttu-id="a8281-117">**Todas las categorías**: se ordena entre todas las categorías disponibles.</span><span class="sxs-lookup"><span data-stu-id="a8281-117">**All categories**: Sorts across all available categories.</span></span>
  - <span data-ttu-id="a8281-118">**Privilegios elevados**: privilegios elevados es una categoría determinada internamente basada en el aprendizaje automático y las señales de la plataforma.</span><span class="sxs-lookup"><span data-stu-id="a8281-118">**High privilege**: High privilege is an internally determined category based on platform machine learning and signals.</span></span>
  - <span data-ttu-id="a8281-119">**Privilegios excesivos**: cuando la gobernanza de aplicaciones recibe datos de telemetría que indican que no se ha usado un permiso concedido a una aplicación en los últimos 90 días, esa aplicación tiene privilegios excesivos.</span><span class="sxs-lookup"><span data-stu-id="a8281-119">**Overprivileged**: When app governance receives telemetry that indicates that a permission granted to an application has not been used in the last 90 days, that application is overprivileged.</span></span> <span data-ttu-id="a8281-120">La gobernanza de aplicaciones debe funcionar durante al menos 90 días para determinar si alguna aplicación tiene privilegios excesivos.</span><span class="sxs-lookup"><span data-stu-id="a8281-120">App governance must be operating for at least 90 days to determine if any app is overprivileged.</span></span>  
  - <span data-ttu-id="a8281-121">**Sin verificar**: las aplicaciones que no han recibido [certificación de editorial](https://docs.microsoft.com/azure/active-directory/develop/publisher-verification-overview) se consideran sin verificar.</span><span class="sxs-lookup"><span data-stu-id="a8281-121">**Unverified**: Applications that have not received [publisher certification](https://docs.microsoft.com/azure/active-directory/develop/publisher-verification-overview) are considered unverified.</span></span>
  - <span data-ttu-id="a8281-122">**Solo aplicaciones**: [los permisos de aplicaciones](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent#permission-types) se utilizan por aplicaciones que pueden ejecutarse sin un usuario que haya iniciado sesión.</span><span class="sxs-lookup"><span data-stu-id="a8281-122">**App only**: [Application permissions](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent#permission-types) are used by apps that can run without a signed-in user present.</span></span> <span data-ttu-id="a8281-123">Las aplicaciones con permisos para acceder a los datos en el usuario son potencialmente de mayor riesgo.</span><span class="sxs-lookup"><span data-stu-id="a8281-123">Apps with permissions to access data across the tenant are potentially a higher risk.</span></span>
  - <span data-ttu-id="a8281-124">**Aplicaciones nuevas**: nuevas aplicaciones de Microsoft 365 que se han registrado en los últimos siete días.</span><span class="sxs-lookup"><span data-stu-id="a8281-124">**New apps**: New Microsoft 365 apps that have been registered in the last seven days.</span></span>  

## <a name="next-step"></a><span data-ttu-id="a8281-125">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="a8281-125">Next step</span></span>

<span data-ttu-id="a8281-126">[Obtenga información detallada sobre una aplicación específica](app-governance-visibility-insights-view-apps.md).</span><span class="sxs-lookup"><span data-stu-id="a8281-126">[Get detailed insights on a specific app](app-governance-visibility-insights-view-apps.md).</span></span>
