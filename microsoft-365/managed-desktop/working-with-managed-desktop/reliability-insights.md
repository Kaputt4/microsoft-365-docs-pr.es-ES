---
title: Información sobre la confiabilidad
description: ''
keywords: Escritorio administrado de Microsoft, Microsoft 365, Service, Documentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 8ecc117b2bc6e7cec3dcf0470a6d3c61ad34adf0
ms.sourcegitcommit: e386037c9cc335c86896dc153344850735afbccd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/27/2019
ms.locfileid: "39634037"
---
# <a name="reliability-insights"></a><span data-ttu-id="d267e-103">Información sobre la confiabilidad</span><span class="sxs-lookup"><span data-stu-id="d267e-103">Reliability insights</span></span>

<span data-ttu-id="d267e-104">Esta vista le proporciona un resumen de estado de los dispositivos administrados.</span><span class="sxs-lookup"><span data-stu-id="d267e-104">This view provides you with a health summary of your managed devices.</span></span> <span data-ttu-id="d267e-105">Para ver los datos de confiabilidad, seleccione la ficha **confiabilidad** .</span><span class="sxs-lookup"><span data-stu-id="d267e-105">To view reliability data, select the **Reliability** tab.</span></span>


![Panel confiabilidad](images/insights_reliability.png)

<span data-ttu-id="d267e-107">La sección **confiabilidad en todos los dispositivos** ofrece un resumen rápido del estado de la implementación en los últimos 14 días mediante la generación de informes sobre el porcentaje de dispositivos considerados "correctos" y el tiempo medio observado desde el último error notificado.</span><span class="sxs-lookup"><span data-stu-id="d267e-107">The **Reliability across devices** section offers a quick health summary of your deployment over the last 14 days by reporting the percentage of devices considered to be “healthy” and the mean time observed since the last reported failure.</span></span> 

 
<span data-ttu-id="d267e-108">El gráfico **confiabilidad sobre el tiempo** de la derecha informa sobre el número de dispositivos con errores críticos y el número total de errores críticos observados a lo largo del tiempo.</span><span class="sxs-lookup"><span data-stu-id="d267e-108">The **Reliability over time** graph on the right reports the number of devices with critical errors and the total number of observed critical errors over time.</span></span>

<span data-ttu-id="d267e-109">En la sección **problemas principales** se explican los problemas específicos detectados que afectan al menos el 5% de los dispositivos administrados.</span><span class="sxs-lookup"><span data-stu-id="d267e-109">The **Top issues** section details specific detected issues that affect at least 5% of your managed devices.</span></span> <span data-ttu-id="d267e-110">Los detalles que se indican incluyen:</span><span class="sxs-lookup"><span data-stu-id="d267e-110">Reported details include:</span></span>

- <span data-ttu-id="d267e-111">El tipo de problema</span><span class="sxs-lookup"><span data-stu-id="d267e-111">The type of issue</span></span>
    - <span data-ttu-id="d267e-112">Bloqueos de aplicación, en los que una aplicación deja de funcionar o se detiene inesperadamente</span><span class="sxs-lookup"><span data-stu-id="d267e-112">Application crashes, in which an app stops functioning or unexpectedly stops</span></span>
    - <span data-ttu-id="d267e-113">La aplicación se bloquea, donde una aplicación deja de responder a la entrada</span><span class="sxs-lookup"><span data-stu-id="d267e-113">Application hangs, where an application stops responding to input</span></span>
    - <span data-ttu-id="d267e-114">Errores críticos, que se producen cuando Windows ha encontrado un problema del que no se puede recuperar</span><span class="sxs-lookup"><span data-stu-id="d267e-114">Critical errors, which occur when Windows has encountered an issue it can't recover from</span></span>
- <span data-ttu-id="d267e-115">El número de dispositivos afectados por el mismo problema</span><span class="sxs-lookup"><span data-stu-id="d267e-115">The number of devices affected by the same issue</span></span>
- <span data-ttu-id="d267e-116">El porcentaje de dispositivos administrados que representa el número</span><span class="sxs-lookup"><span data-stu-id="d267e-116">The percentage of managed devices that number represents</span></span>
- <span data-ttu-id="d267e-117">Número total de repeticiones del problema específico</span><span class="sxs-lookup"><span data-stu-id="d267e-117">The total count of occurences of the specific issue</span></span>
- <span data-ttu-id="d267e-118">Componente de software que parece ser el origen del problema</span><span class="sxs-lookup"><span data-stu-id="d267e-118">The software component that appears to be the source of the problem</span></span>
- <span data-ttu-id="d267e-119">La categoría del problema detectado:</span><span class="sxs-lookup"><span data-stu-id="d267e-119">The category of the detected problem:</span></span>
    - <span data-ttu-id="d267e-120">Explorador (Edge, Chrome, IE)</span><span class="sxs-lookup"><span data-stu-id="d267e-120">Browser (Edge, Chrome, IE)</span></span>
    - <span data-ttu-id="d267e-121">Desconocido (componentes que no son de Microsoft)</span><span class="sxs-lookup"><span data-stu-id="d267e-121">Unknown (Non-Microsoft components)</span></span>
    - <span data-ttu-id="d267e-122">Controlador (audio, gráficos u otros controladores)</span><span class="sxs-lookup"><span data-stu-id="d267e-122">Driver (audio, graphics, or other drivers)</span></span>
    - <span data-ttu-id="d267e-123">Productividad (margen de demora, G-Suites, Microsoft Office y sus complementos o extensiones, Teams)</span><span class="sxs-lookup"><span data-stu-id="d267e-123">Productivity (Slack, G-Suites, Microsoft Office and its add-ons or extensions, Teams)</span></span>
    - <span data-ttu-id="d267e-124">Multimedia (imagen, música o aplicaciones de vídeo</span><span class="sxs-lookup"><span data-stu-id="d267e-124">Media (image, music, or video apps</span></span>
    - <span data-ttu-id="d267e-125">Seguridad (componentes de seguridad de Windows)</span><span class="sxs-lookup"><span data-stu-id="d267e-125">Security (Windows security components)</span></span>
- <span data-ttu-id="d267e-126">El estado actual de Microsoft Managed Desktop Operations investiga y corrige el problema</span><span class="sxs-lookup"><span data-stu-id="d267e-126">The current status as Microsoft Managed Desktop Operations investigates and remediates the issue</span></span>

