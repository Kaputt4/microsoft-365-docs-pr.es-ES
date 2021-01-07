---
title: Decisión basada en los resultados en eDiscovery avanzado
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: aed65bcd-0a4f-43e9-b5e5-b98cc376bdf8
description: Obtenga información sobre cómo la pestaña decidir en eDiscovery avanzado proporciona datos que pueden ayudarle a determinar el tamaño correcto del conjunto de revisión de los archivos de casos.
ROBOTS: NOINDEX, NOFOLLOW
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7a4c2fe891a48451d9b8d852f603b225ab7b080d
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769155"
---
# <a name="decisions-based-on-relevance-results-in-advanced-ediscovery"></a><span data-ttu-id="1c192-103">Decisiones basadas en los resultados de relevancia en eDiscovery avanzado</span><span class="sxs-lookup"><span data-stu-id="1c192-103">Decisions based on Relevance results in Advanced eDiscovery</span></span>
  
<span data-ttu-id="1c192-104">En el módulo de relevancia de eDiscovery avanzado, la pestaña decidir proporciona información adicional para ver y usar estadísticas de ayuda para la toma de decisiones para determinar el tamaño del conjunto de revisión de los archivos de casos.</span><span class="sxs-lookup"><span data-stu-id="1c192-104">In the Relevance module in Advanced eDiscovery, the Decide tab provides additional information for viewing and using decision-support statistics for determining the size of the review set of case files.</span></span>
  
## <a name="using-the-decide-tab"></a><span data-ttu-id="1c192-105">Uso de la pestaña decidir</span><span class="sxs-lookup"><span data-stu-id="1c192-105">Using the Decide tab</span></span>

![Decisión de relevancia](../media/f32fed89-f3b5-404a-90c7-ea25d2eb58a9.png)
  
<span data-ttu-id="1c192-107">Esta pestaña incluye los siguientes componentes:</span><span class="sxs-lookup"><span data-stu-id="1c192-107">This tab includes the following components:</span></span>
  
- <span data-ttu-id="1c192-108">**Problema**: desde aquí, puede seleccionar el asunto de interés de la lista.</span><span class="sxs-lookup"><span data-stu-id="1c192-108">**Issue**: From here, you can select the issue of interest from the list.</span></span>

- <span data-ttu-id="1c192-109">**Tasa de revisión-RECALL**: comparaciones de la revisión avanzada de eDiscovery según los resultados de relevancia.</span><span class="sxs-lookup"><span data-stu-id="1c192-109">**Review-recall ratio**: Comparisons of Advanced eDiscovery review according to Relevance scores.</span></span> <span data-ttu-id="1c192-110">El punto de corte en el gráfico representa el porcentaje de archivos que se van a revisar, asignado a una puntuación de relevancia.</span><span class="sxs-lookup"><span data-stu-id="1c192-110">The Cutoff point in the chart represents the percentage of files to review, mapped to a Relevance score.</span></span> <span data-ttu-id="1c192-111">Se usa en la fase de prueba de relevancia y como un umbral de exportación para culling.</span><span class="sxs-lookup"><span data-stu-id="1c192-111">This is used in the Relevance Test phase and as an Export threshold for culling.</span></span> <span data-ttu-id="1c192-112">El punto de corte predeterminado, para el número de archivos que se van a revisar, es el punto en el que el equilibrio entre la recuperación y la precisión es óptimo.</span><span class="sxs-lookup"><span data-stu-id="1c192-112">The default cutoff point, for the number of files to review is at the point in which the balance between Recall and Precision is optimal.</span></span> <span data-ttu-id="1c192-113">El punto de corte real debe estar determinado por el usuario en función de los objetivos y del equilibrio de costes (% Review) y el riesgo (% recall).</span><span class="sxs-lookup"><span data-stu-id="1c192-113">The actual cutoff point should be determined by the user depending on objectives and the cost tradeoff (%review) and risk (%recall).</span></span> <span data-ttu-id="1c192-114">Con el control deslizante, puede ajustar el punto de corte y ver el efecto en el gráfico y los parámetros, al ajustar el porcentaje de archivos relevantes que se van a recuperar y antes de validar una decisión.</span><span class="sxs-lookup"><span data-stu-id="1c192-114">Using the slider, you can adjust the cutoff point and see the effect on the graph and parameters, when adjusting the percent of relevant files to be retrieved, and before validating a decision.</span></span>

- <span data-ttu-id="1c192-115">**Parámetros**: los parámetros revisión, recuperación, siguiente relevante y costo total son estadísticas calculadas acumuladas relativas a la revisión establecida en relación con la colección para todo el caso.</span><span class="sxs-lookup"><span data-stu-id="1c192-115">**Parameters**: Review, Recall, Next relevant and Total cost parameters are cumulative calculated statistics pertaining to the review set in relation to the collection for the entire case.</span></span> <span data-ttu-id="1c192-116">Las definiciones de estos parámetros son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="1c192-116">Definitions for these parameters are as follows:</span></span>

  - <span data-ttu-id="1c192-117">**Revisión**: porcentaje de archivos que se van a revisar en función de este límite.</span><span class="sxs-lookup"><span data-stu-id="1c192-117">**Review**: Percentage of files to review based on this cutoff.</span></span>

  - <span data-ttu-id="1c192-118">**RECALL**: porcentaje de archivos relevantes en el conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="1c192-118">**Recall**: Percentage of relevant files in the review set.</span></span>

  - <span data-ttu-id="1c192-119">**Siguiente relevante**: costo para revisar e identificar otro archivo relevante que no se encuentra actualmente en el conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="1c192-119">**Next relevant**: Cost to review and identify another relevant file that is not currently in the review set.</span></span>

  - <span data-ttu-id="1c192-120">**Costo total**: costo de revisión de este porcentaje de los archivos de casos.</span><span class="sxs-lookup"><span data-stu-id="1c192-120">**Total cost**: Cost for reviewing this percentage of the case files.</span></span> <span data-ttu-id="1c192-121">La configuración del parámetro costo puede definirla el administrador de casos.</span><span class="sxs-lookup"><span data-stu-id="1c192-121">Cost parameter settings can be set by the Case manager.</span></span>

  - <span data-ttu-id="1c192-122">**Distribución por puntuación de relevancia**: los archivos en la pantalla gris oscuro a la izquierda están por debajo de la puntuación límite.</span><span class="sxs-lookup"><span data-stu-id="1c192-122">**Distribution by relevance score**: Files in the dark gray display to the left are below the cutoff score.</span></span> <span data-ttu-id="1c192-123">Una información sobre herramientas muestra la puntuación de relevancia y el porcentaje relacionado de los archivos en el archivo de revisión establecido en relación con el total de archivos.</span><span class="sxs-lookup"><span data-stu-id="1c192-123">A tool-tip displays the Relevance score and the related percentage of files in the review file set in relation to the total files.</span></span>

<span data-ttu-id="1c192-124">El panel de **detalles** expandido muestra más detalles.</span><span class="sxs-lookup"><span data-stu-id="1c192-124">The expanded **Details** pane displays more details.</span></span> <span data-ttu-id="1c192-125">Los archivos de las figuras de la colección no incluyen archivos vacíos o Nebulous.</span><span class="sxs-lookup"><span data-stu-id="1c192-125">Files in collection figures do not include empty or nebulous files.</span></span> <span data-ttu-id="1c192-126">Las figuras de los archivos de familia representan los archivos que no se cargan en relevancia, aunque todavía se cuentan como parte de la familia.</span><span class="sxs-lookup"><span data-stu-id="1c192-126">Family files figures represent files that are not loaded in Relevance, yet still counted as part of the family.</span></span>
