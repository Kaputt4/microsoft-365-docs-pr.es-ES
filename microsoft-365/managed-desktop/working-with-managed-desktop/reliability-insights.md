---
title: Información sobre la confiabilidad
description: ''
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 06e1446ca290439c9e6689f4461c825438cf6aaf
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950347"
---
# <a name="reliability-insights"></a><span data-ttu-id="cfa24-103">Información sobre la confiabilidad</span><span class="sxs-lookup"><span data-stu-id="cfa24-103">Reliability insights</span></span>

<span data-ttu-id="cfa24-104">Esta vista le proporciona un resumen de estado de los dispositivos administrados.</span><span class="sxs-lookup"><span data-stu-id="cfa24-104">This view provides you with a health summary of your managed devices.</span></span> <span data-ttu-id="cfa24-105">Para ver los datos de confiabilidad, seleccione la ficha **confiabilidad** .</span><span class="sxs-lookup"><span data-stu-id="cfa24-105">To view reliability data, select the **Reliability** tab.</span></span>


![Panel confiabilidad: confiabilidad en los dispositivos en la parte superior izquierda, la confiabilidad con el gráfico de tiempo en la esquina superior derecha, la tabla de problemas principales en la parte inferior.](../../media/insights_reliability.png)

<span data-ttu-id="cfa24-108">La sección **confiabilidad en todos los dispositivos** ofrece un resumen rápido del estado de la implementación en los últimos 14 días mediante la generación de informes sobre el porcentaje de dispositivos considerados "correctos" y el tiempo medio observado desde el último error notificado.</span><span class="sxs-lookup"><span data-stu-id="cfa24-108">The **Reliability across devices** section offers a quick health summary of your deployment over the last 14 days by reporting the percentage of devices considered to be “healthy” and the mean time observed since the last reported failure.</span></span> 

 
<span data-ttu-id="cfa24-109">El gráfico **confiabilidad sobre el tiempo** de la derecha informa sobre el número de dispositivos con errores críticos y el número total de errores críticos observados a lo largo del tiempo.</span><span class="sxs-lookup"><span data-stu-id="cfa24-109">The **Reliability over time** graph on the right reports the number of devices with critical errors and the total number of observed critical errors over time.</span></span>

<span data-ttu-id="cfa24-110">En la sección **problemas principales** se explican los problemas específicos detectados que afectan al menos el 5% de los dispositivos administrados.</span><span class="sxs-lookup"><span data-stu-id="cfa24-110">The **Top issues** section details specific detected issues that affect at least 5% of your managed devices.</span></span> <span data-ttu-id="cfa24-111">Los detalles que se indican incluyen:</span><span class="sxs-lookup"><span data-stu-id="cfa24-111">Reported details include:</span></span>

- <span data-ttu-id="cfa24-112">El tipo de problema</span><span class="sxs-lookup"><span data-stu-id="cfa24-112">The type of issue</span></span>
    - <span data-ttu-id="cfa24-113">Bloqueos de aplicación, en los que una aplicación deja de funcionar o se detiene inesperadamente</span><span class="sxs-lookup"><span data-stu-id="cfa24-113">Application crashes, in which an app stops functioning or unexpectedly stops</span></span>
    - <span data-ttu-id="cfa24-114">La aplicación se bloquea, donde una aplicación deja de responder a la entrada</span><span class="sxs-lookup"><span data-stu-id="cfa24-114">Application hangs, where an application stops responding to input</span></span>
    - <span data-ttu-id="cfa24-115">Errores críticos, que se producen cuando Windows ha encontrado un problema del que no se puede recuperar</span><span class="sxs-lookup"><span data-stu-id="cfa24-115">Critical errors, which occur when Windows has encountered an issue it can't recover from</span></span>
- <span data-ttu-id="cfa24-116">El número de dispositivos afectados por el mismo problema</span><span class="sxs-lookup"><span data-stu-id="cfa24-116">The number of devices affected by the same issue</span></span>
- <span data-ttu-id="cfa24-117">El porcentaje de dispositivos administrados que representa el número</span><span class="sxs-lookup"><span data-stu-id="cfa24-117">The percentage of managed devices that number represents</span></span>
- <span data-ttu-id="cfa24-118">Número total de ocurrencias del problema específico</span><span class="sxs-lookup"><span data-stu-id="cfa24-118">The total count of occurrences of the specific issue</span></span>
- <span data-ttu-id="cfa24-119">Componente de software que parece ser el origen del problema</span><span class="sxs-lookup"><span data-stu-id="cfa24-119">The software component that appears to be the source of the problem</span></span>
- <span data-ttu-id="cfa24-120">La categoría del problema detectado:</span><span class="sxs-lookup"><span data-stu-id="cfa24-120">The category of the detected problem:</span></span>
    - <span data-ttu-id="cfa24-121">Explorador (Edge, Chrome, IE)</span><span class="sxs-lookup"><span data-stu-id="cfa24-121">Browser (Edge, Chrome, IE)</span></span>
    - <span data-ttu-id="cfa24-122">Desconocido (componentes que no son de Microsoft)</span><span class="sxs-lookup"><span data-stu-id="cfa24-122">Unknown (Non-Microsoft components)</span></span>
    - <span data-ttu-id="cfa24-123">Controlador (audio, gráficos u otros controladores)</span><span class="sxs-lookup"><span data-stu-id="cfa24-123">Driver (audio, graphics, or other drivers)</span></span>
    - <span data-ttu-id="cfa24-124">Productividad (margen de demora, G-Suites, Microsoft Office y sus complementos o extensiones, Teams)</span><span class="sxs-lookup"><span data-stu-id="cfa24-124">Productivity (Slack, G-Suites, Microsoft Office and its add-ons or extensions, Teams)</span></span>
    - <span data-ttu-id="cfa24-125">Multimedia (imagen, música o aplicaciones de vídeo</span><span class="sxs-lookup"><span data-stu-id="cfa24-125">Media (image, music, or video apps</span></span>
    - <span data-ttu-id="cfa24-126">Seguridad (componentes de seguridad de Windows)</span><span class="sxs-lookup"><span data-stu-id="cfa24-126">Security (Windows security components)</span></span>
- <span data-ttu-id="cfa24-127">El estado actual de Microsoft Managed Desktop Operations investiga y corrige el problema</span><span class="sxs-lookup"><span data-stu-id="cfa24-127">The current status as Microsoft Managed Desktop Operations investigates and remediates the issue</span></span>

