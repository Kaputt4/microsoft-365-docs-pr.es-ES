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
ms.sourcegitcommit: cebbdd393dcfd93ff43a1ab66ad70115853f83e7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2021
ms.locfileid: "52739816"
---
# <a name="reliability-insights"></a><span data-ttu-id="187ed-103">Información sobre la confiabilidad</span><span class="sxs-lookup"><span data-stu-id="187ed-103">Reliability insights</span></span>

<span data-ttu-id="187ed-104">Esta vista le proporciona un resumen de estado de los dispositivos administrados.</span><span class="sxs-lookup"><span data-stu-id="187ed-104">This view provides you with a health summary of your managed devices.</span></span> <span data-ttu-id="187ed-105">Para ver los datos de confiabilidad, seleccione la **pestaña** Confiabilidad.</span><span class="sxs-lookup"><span data-stu-id="187ed-105">To view reliability data, select the **Reliability** tab.</span></span>


![Panel de confiabilidad: confiabilidad en todos los dispositivos en la parte superior izquierda, confiabilidad con el gráfico de tiempo en la parte superior derecha, tabla de problemas superior en la parte inferior.](../../media/insights_reliability.png)

<span data-ttu-id="187ed-108">La  sección Confiabilidad entre dispositivos ofrece un resumen de estado rápido de la implementación en los últimos 14 días al informar del porcentaje de dispositivos considerados "correctos" y el tiempo medio observado desde el último error notificado.</span><span class="sxs-lookup"><span data-stu-id="187ed-108">The **Reliability across devices** section offers a quick health summary of your deployment over the last 14 days by reporting the percentage of devices considered to be “healthy” and the mean time observed since the last reported failure.</span></span> 

 
<span data-ttu-id="187ed-109">El **gráfico Confiabilidad con el tiempo** de la derecha informa del número de dispositivos con errores críticos y el número total de errores críticos observados con el tiempo.</span><span class="sxs-lookup"><span data-stu-id="187ed-109">The **Reliability over time** graph on the right reports the number of devices with critical errors and the total number of observed critical errors over time.</span></span>

<span data-ttu-id="187ed-110">En **la sección Principales problemas** se detallan los problemas detectados específicos que afectan al menos al 5 % de los dispositivos administrados.</span><span class="sxs-lookup"><span data-stu-id="187ed-110">The **Top issues** section details specific detected issues that affect at least 5% of your managed devices.</span></span> <span data-ttu-id="187ed-111">Entre los detalles notificados se incluyen:</span><span class="sxs-lookup"><span data-stu-id="187ed-111">Reported details include:</span></span>

- <span data-ttu-id="187ed-112">Tipo de problema</span><span class="sxs-lookup"><span data-stu-id="187ed-112">The type of issue</span></span>
    - <span data-ttu-id="187ed-113">Se bloquea la aplicación, en la que una aplicación deja de funcionar o se detiene inesperadamente</span><span class="sxs-lookup"><span data-stu-id="187ed-113">Application crashes, in which an app stops functioning or unexpectedly stops</span></span>
    - <span data-ttu-id="187ed-114">La aplicación se cuelga, donde una aplicación deja de responder a la entrada</span><span class="sxs-lookup"><span data-stu-id="187ed-114">Application hangs, where an application stops responding to input</span></span>
    - <span data-ttu-id="187ed-115">Errores críticos, que se producen Windows se ha encontrado con un problema del que no puede recuperarse</span><span class="sxs-lookup"><span data-stu-id="187ed-115">Critical errors, which occur when Windows has encountered an issue it can't recover from</span></span>
- <span data-ttu-id="187ed-116">El número de dispositivos afectados por el mismo problema</span><span class="sxs-lookup"><span data-stu-id="187ed-116">The number of devices affected by the same issue</span></span>
- <span data-ttu-id="187ed-117">Porcentaje de dispositivos administrados que representa el número</span><span class="sxs-lookup"><span data-stu-id="187ed-117">The percentage of managed devices that number represents</span></span>
- <span data-ttu-id="187ed-118">Recuento total de repeticiones del problema específico</span><span class="sxs-lookup"><span data-stu-id="187ed-118">The total count of occurrences of the specific issue</span></span>
- <span data-ttu-id="187ed-119">El componente de software que parece ser el origen del problema</span><span class="sxs-lookup"><span data-stu-id="187ed-119">The software component that appears to be the source of the problem</span></span>
- <span data-ttu-id="187ed-120">Categoría del problema detectado:</span><span class="sxs-lookup"><span data-stu-id="187ed-120">The category of the detected problem:</span></span>
    - <span data-ttu-id="187ed-121">Explorador (Edge, Chrome, IE)</span><span class="sxs-lookup"><span data-stu-id="187ed-121">Browser (Edge, Chrome, IE)</span></span>
    - <span data-ttu-id="187ed-122">Desconocido (componentes que no son de Microsoft)</span><span class="sxs-lookup"><span data-stu-id="187ed-122">Unknown (Non-Microsoft components)</span></span>
    - <span data-ttu-id="187ed-123">Controlador (audio, gráficos u otros controladores)</span><span class="sxs-lookup"><span data-stu-id="187ed-123">Driver (audio, graphics, or other drivers)</span></span>
    - <span data-ttu-id="187ed-124">Productividad (Slack, G-Suites, Microsoft Office y sus complementos o extensiones, Teams)</span><span class="sxs-lookup"><span data-stu-id="187ed-124">Productivity (Slack, G-Suites, Microsoft Office and its add-ons or extensions, Teams)</span></span>
    - <span data-ttu-id="187ed-125">Medios (aplicaciones de imagen, música o vídeo</span><span class="sxs-lookup"><span data-stu-id="187ed-125">Media (image, music, or video apps</span></span>
    - <span data-ttu-id="187ed-126">Seguridad (Windows de seguridad)</span><span class="sxs-lookup"><span data-stu-id="187ed-126">Security (Windows security components)</span></span>
- <span data-ttu-id="187ed-127">El estado actual como Escritorio administrado de Microsoft operations investiga y corrige el problema</span><span class="sxs-lookup"><span data-stu-id="187ed-127">The current status as Microsoft Managed Desktop Operations investigates and remediates the issue</span></span>

