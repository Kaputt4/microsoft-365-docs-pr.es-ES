---
title: Decisión basada en los resultados de Advanced eDiscovery
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
description: Obtenga información sobre cómo la pestaña Decidir en Advanced eDiscovery proporciona datos que pueden ayudarle a determinar el tamaño correcto del conjunto de revisión de archivos de casos.
ROBOTS: NOINDEX, NOFOLLOW
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7a4c2fe891a48451d9b8d852f603b225ab7b080d
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769155"
---
# <a name="decisions-based-on-relevance-results-in-advanced-ediscovery"></a><span data-ttu-id="d41b8-103">Las decisiones basadas en relevancia se traducen en Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="d41b8-103">Decisions based on Relevance results in Advanced eDiscovery</span></span>
  
<span data-ttu-id="d41b8-104">En el módulo Relevancia de Advanced eDiscovery, la pestaña Decidir proporciona información adicional para ver y usar estadísticas de compatibilidad con decisiones para determinar el tamaño del conjunto de revisión de archivos de casos.</span><span class="sxs-lookup"><span data-stu-id="d41b8-104">In the Relevance module in Advanced eDiscovery, the Decide tab provides additional information for viewing and using decision-support statistics for determining the size of the review set of case files.</span></span>
  
## <a name="using-the-decide-tab"></a><span data-ttu-id="d41b8-105">Uso de la pestaña Decidir</span><span class="sxs-lookup"><span data-stu-id="d41b8-105">Using the Decide tab</span></span>

![Decisión de relevancia](../media/f32fed89-f3b5-404a-90c7-ea25d2eb58a9.png)
  
<span data-ttu-id="d41b8-107">Esta pestaña incluye los siguientes componentes:</span><span class="sxs-lookup"><span data-stu-id="d41b8-107">This tab includes the following components:</span></span>
  
- <span data-ttu-id="d41b8-108">**Problema:** desde aquí, puede seleccionar el problema de interés de la lista.</span><span class="sxs-lookup"><span data-stu-id="d41b8-108">**Issue**: From here, you can select the issue of interest from the list.</span></span>

- <span data-ttu-id="d41b8-109">**Relación revisión-recuperación:** comparaciones de Advanced eDiscovery de acuerdo con las puntuaciones de relevancia.</span><span class="sxs-lookup"><span data-stu-id="d41b8-109">**Review-recall ratio**: Comparisons of Advanced eDiscovery review according to Relevance scores.</span></span> <span data-ttu-id="d41b8-110">El punto de corte del gráfico representa el porcentaje de archivos que se revisarán, asignados a una puntuación de relevancia.</span><span class="sxs-lookup"><span data-stu-id="d41b8-110">The Cutoff point in the chart represents the percentage of files to review, mapped to a Relevance score.</span></span> <span data-ttu-id="d41b8-111">Esto se usa en la fase de prueba de relevancia y como umbral de exportación para la selección.</span><span class="sxs-lookup"><span data-stu-id="d41b8-111">This is used in the Relevance Test phase and as an Export threshold for culling.</span></span> <span data-ttu-id="d41b8-112">El punto de corte predeterminado, para el número de archivos que se va a revisar es en el punto en el que el equilibrio entre Recall y Precision es óptimo.</span><span class="sxs-lookup"><span data-stu-id="d41b8-112">The default cutoff point, for the number of files to review is at the point in which the balance between Recall and Precision is optimal.</span></span> <span data-ttu-id="d41b8-113">El usuario debe determinar el punto de límite real en función de los objetivos y la negociación de costos (%review) y el riesgo (%recall).</span><span class="sxs-lookup"><span data-stu-id="d41b8-113">The actual cutoff point should be determined by the user depending on objectives and the cost tradeoff (%review) and risk (%recall).</span></span> <span data-ttu-id="d41b8-114">Con el control deslizante, puede ajustar el punto de corte y ver el efecto en el gráfico y los parámetros, al ajustar el porcentaje de archivos relevantes que se recuperarán y antes de validar una decisión.</span><span class="sxs-lookup"><span data-stu-id="d41b8-114">Using the slider, you can adjust the cutoff point and see the effect on the graph and parameters, when adjusting the percent of relevant files to be retrieved, and before validating a decision.</span></span>

- <span data-ttu-id="d41b8-115">**Parameters**: Review, Recall, Next relevant and Total cost parameters are cumulative calculated statistics pertaining to the review set in relation to the collection for the entire case.</span><span class="sxs-lookup"><span data-stu-id="d41b8-115">**Parameters**: Review, Recall, Next relevant and Total cost parameters are cumulative calculated statistics pertaining to the review set in relation to the collection for the entire case.</span></span> <span data-ttu-id="d41b8-116">Las definiciones de estos parámetros son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="d41b8-116">Definitions for these parameters are as follows:</span></span>

  - <span data-ttu-id="d41b8-117">**Review**: Percentage of files to review based on this cutoff.</span><span class="sxs-lookup"><span data-stu-id="d41b8-117">**Review**: Percentage of files to review based on this cutoff.</span></span>

  - <span data-ttu-id="d41b8-118">**Recall**: Porcentaje de archivos relevantes en el conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="d41b8-118">**Recall**: Percentage of relevant files in the review set.</span></span>

  - <span data-ttu-id="d41b8-119">**Siguiente relevante:** costo para revisar e identificar otro archivo relevante que no está actualmente en el conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="d41b8-119">**Next relevant**: Cost to review and identify another relevant file that is not currently in the review set.</span></span>

  - <span data-ttu-id="d41b8-120">**Costo total:** costo para revisar este porcentaje de los archivos de caso.</span><span class="sxs-lookup"><span data-stu-id="d41b8-120">**Total cost**: Cost for reviewing this percentage of the case files.</span></span> <span data-ttu-id="d41b8-121">El administrador de casos puede establecer la configuración de parámetros de costo.</span><span class="sxs-lookup"><span data-stu-id="d41b8-121">Cost parameter settings can be set by the Case manager.</span></span>

  - <span data-ttu-id="d41b8-122">**Distribución por puntuación de relevancia:** los archivos de la pantalla gris oscuro a la izquierda están por debajo de la puntuación de límite.</span><span class="sxs-lookup"><span data-stu-id="d41b8-122">**Distribution by relevance score**: Files in the dark gray display to the left are below the cutoff score.</span></span> <span data-ttu-id="d41b8-123">Una sugerencia de herramienta muestra la puntuación relevancia y el porcentaje relacionado de archivos en el conjunto de archivos de revisión en relación con el total de archivos.</span><span class="sxs-lookup"><span data-stu-id="d41b8-123">A tool-tip displays the Relevance score and the related percentage of files in the review file set in relation to the total files.</span></span>

<span data-ttu-id="d41b8-124">El panel **Detalles expandido** muestra más detalles.</span><span class="sxs-lookup"><span data-stu-id="d41b8-124">The expanded **Details** pane displays more details.</span></span> <span data-ttu-id="d41b8-125">Los archivos de las figuras de colección no incluyen archivos vacíos o nebulosos.</span><span class="sxs-lookup"><span data-stu-id="d41b8-125">Files in collection figures do not include empty or nebulous files.</span></span> <span data-ttu-id="d41b8-126">Las figuras de archivos de familia representan archivos que no se cargan en Relevancia, pero que aún se cuentan como parte de la familia.</span><span class="sxs-lookup"><span data-stu-id="d41b8-126">Family files figures represent files that are not loaded in Relevance, yet still counted as part of the family.</span></span>
