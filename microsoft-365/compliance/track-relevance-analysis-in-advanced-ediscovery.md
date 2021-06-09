---
title: Realizar un seguimiento del análisis de relevancia en Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 3ab1e2c3-28cf-4bf5-b0a8-c0222f32bdf5
ROBOTS: NOINDEX, NOFOLLOW
description: Obtenga información sobre cómo ver e interpretar el estado de aprendizaje de relevancia y los resultados de los problemas de casos en Advanced eDiscovery.
ms.openlocfilehash: 224337969b5e662d45c5b804fa5a0ee045f4fb84
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769185"
---
# <a name="track-relevance-analysis-in-advanced-ediscovery"></a><span data-ttu-id="278c1-103">Realizar un seguimiento del análisis de relevancia en Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="278c1-103">Track Relevance analysis in Advanced eDiscovery</span></span>
  
<span data-ttu-id="278c1-104">En Advanced eDiscovery, la pestaña Pista de relevancia muestra la validez calculada del aprendizaje de relevancia realizado en la pestaña Etiqueta e indica el siguiente paso para realizar el proceso de aprendizaje iterativo en Relevancia.</span><span class="sxs-lookup"><span data-stu-id="278c1-104">In Advanced eDiscovery, the Relevance Track tab displays the calculated validity of the Relevance training performed in the Tag tab and indicates the next step to take in the iterative training process in Relevance.</span></span> 
  
## <a name="tracking-relevance-training-status"></a><span data-ttu-id="278c1-105">Seguimiento del estado de aprendizaje de relevancia</span><span class="sxs-lookup"><span data-stu-id="278c1-105">Tracking Relevance training status</span></span>

1. <span data-ttu-id="278c1-106">Vea los siguientes detalles en El seguimiento de relevancia para los problemas de caso, como se muestra en el siguiente ejemplo de un cuadro de diálogo **Nombre de** problema a continuación.</span><span class="sxs-lookup"><span data-stu-id="278c1-106">View the following details in Relevance Track for the case issues, as shown in the following example of an **Issue name** dialog below.</span></span>

   - <span data-ttu-id="278c1-107">**Evaluación:** este indicador de progreso muestra hasta qué punto el aprendizaje de relevancia realizado hasta este punto ha alcanzado el objetivo de evaluación en términos de margen de error.</span><span class="sxs-lookup"><span data-stu-id="278c1-107">**Assessment**: This progress indicator shows to what degree the Relevance training performed to this point has achieved the assessment target in terms of margin of error.</span></span> <span data-ttu-id="278c1-108">También se muestra la riqueza de los resultados del aprendizaje de relevancia.</span><span class="sxs-lookup"><span data-stu-id="278c1-108">The richness of the Relevance training results is also displayed.</span></span>

   - <span data-ttu-id="278c1-109">**Aprendizaje:** este indicador de progreso codificado por colores y la sugerencia de herramienta indican la estabilidad de los resultados del aprendizaje de relevancia y una escala numérica que muestra el número de muestras de aprendizaje de relevancia etiquetadas para cada problema.</span><span class="sxs-lookup"><span data-stu-id="278c1-109">**Training**: This color-coded progress indicator and tool-tip indicates the Relevance training results stability and a numeric scale showing the number of Relevance training samples tagged for each issue.</span></span> <span data-ttu-id="278c1-110">El experto supervisa el progreso del proceso de aprendizaje de relevancia iterativa.</span><span class="sxs-lookup"><span data-stu-id="278c1-110">The expert monitors the progress of the iterative Relevance training process.</span></span> 
  
   - <span data-ttu-id="278c1-111">**Cálculo por lotes:** este indicador de progreso proporciona información sobre la finalización del cálculo por lotes.</span><span class="sxs-lookup"><span data-stu-id="278c1-111">**Batch calculation**: This progress indicator provides information about the completion of Batch calculation.</span></span>
  
   - <span data-ttu-id="278c1-112">**Paso siguiente:** muestra la recomendación para el siguiente paso que se va a realizar.</span><span class="sxs-lookup"><span data-stu-id="278c1-112">**Next step**: Displays the recommendation for the next step to be performed.</span></span> 
  
    <span data-ttu-id="278c1-113">En el ejemplo, se muestra una evaluación completada correctamente para un problema, indicada por el indicador de progreso de color completado y la marca de verificación.</span><span class="sxs-lookup"><span data-stu-id="278c1-113">In the example, a successfully completed Assessment for an issue is shown, indicated by the completed color progress indicator and the checkmark.</span></span> <span data-ttu-id="278c1-114">El etiquetado está en curso, pero el caso aún se considera inestable (el estado de estabilidad también se muestra en una sugerencia de herramienta).</span><span class="sxs-lookup"><span data-stu-id="278c1-114">Tagging is underway, but the case is still considered unstable (stability status also shown in a tool-tip).</span></span> <span data-ttu-id="278c1-115">El siguiente paso recomendado es "Training".</span><span class="sxs-lookup"><span data-stu-id="278c1-115">The next step recommendation is "Training".</span></span> 
  
    ![Formación del seguimiento de relevancia paso 1](../media/a00fe607-680a-48eb-9d61-4565319f7ab6.png)
  
    <span data-ttu-id="278c1-117">La vista expandida muestra información y opciones adicionales.</span><span class="sxs-lookup"><span data-stu-id="278c1-117">The expanded view displays additional information and options.</span></span> <span data-ttu-id="278c1-118">El margen de error actual mostrado es el margen de error de la recuperación en el estado actual de evaluación, dados los archivos de evaluación existentes (ya etiquetados).</span><span class="sxs-lookup"><span data-stu-id="278c1-118">The displayed current error margin is the error margin of the recall in the current state of assessment, given the existing (already tagged) assessment files.</span></span>
  
    > [!NOTE]
    >  <span data-ttu-id="278c1-119">La fase de evaluación se puede omitir desactivando **la** casilla Evaluación por problema y, a continuación, para "todos los problemas".</span><span class="sxs-lookup"><span data-stu-id="278c1-119">The Assessment stage can be bypassed by clearing the **Assessment** check box per issue and then for "all issues".</span></span> <span data-ttu-id="278c1-120">Sin embargo, como resultado, no habrá estadísticas para este problema.</span><span class="sxs-lookup"><span data-stu-id="278c1-120">However, as a result, there will be no statistics for this issue.</span></span> <span data-ttu-id="278c1-121">> desactivar la **casilla Evaluación** solo se puede hacer antes de realizar la evaluación.</span><span class="sxs-lookup"><span data-stu-id="278c1-121">> Clearing the **Assessment** check box can only be done before assessment is performed.</span></span> <span data-ttu-id="278c1-122">Cuando existen varios problemas en un caso, la evaluación solo se omite si la casilla está desactivada para cada problema</span><span class="sxs-lookup"><span data-stu-id="278c1-122">Where multiple issues exist in a case, assessment is bypassed only if the check box is cleared for each issue</span></span> 
  
    <span data-ttu-id="278c1-123">Cuando la evaluación no se completa con el primer conjunto de archivos de ejemplo, la evaluación puede ser el siguiente paso para etiquetar más archivos.</span><span class="sxs-lookup"><span data-stu-id="278c1-123">When assessment is not completed with the first sample set of files, assessment might be the next step for tagging more files.</span></span>
  
    <span data-ttu-id="278c1-124">En **Pista de** \> **relevancia,** el indicador de progreso de aprendizaje y la sugerencia de herramienta indican el número estimado de muestras adicionales necesarias para alcanzar la estabilidad.</span><span class="sxs-lookup"><span data-stu-id="278c1-124">In **Relevance** \> **Track**, the training progress indicator and tool-tip indicate the estimated number of additional samples needed to reach stability.</span></span> <span data-ttu-id="278c1-125">Esta estimación proporciona una guía para la formación adicional necesaria.</span><span class="sxs-lookup"><span data-stu-id="278c1-125">This estimate provides a guideline for the additional training needed.</span></span>
  
    ![Formación del seguimiento de relevancia](../media/98dbc3f5-5238-4d73-9f88-1aa4d77ea729.png)
  
2. <span data-ttu-id="278c1-127">Cuando haya terminado de etiquetar y si necesita continuar con el aprendizaje, haga clic en **Aprendizaje**.</span><span class="sxs-lookup"><span data-stu-id="278c1-127">When you're done tagging and if you need to continue training, click **Training**.</span></span> <span data-ttu-id="278c1-128">Otro conjunto de archivos de ejemplo se genera a partir del conjunto de archivos cargado para un aprendizaje adicional.</span><span class="sxs-lookup"><span data-stu-id="278c1-128">Another sample set of files is generated from the loaded file set for additional training.</span></span> <span data-ttu-id="278c1-129">A continuación, se le devuelve a la pestaña Etiqueta para etiquetar y entrenar más archivos.</span><span class="sxs-lookup"><span data-stu-id="278c1-129">You are then returned to the Tag tab to tag and train more files.</span></span>

### <a name="reaching-stable-training-levels"></a><span data-ttu-id="278c1-130">Alcanzar niveles de aprendizaje estables</span><span class="sxs-lookup"><span data-stu-id="278c1-130">Reaching stable training levels</span></span>

<span data-ttu-id="278c1-131">Una vez que los archivos de evaluación han alcanzado un nivel estable de aprendizaje, Advanced eDiscovery está listo para el cálculo por lotes.</span><span class="sxs-lookup"><span data-stu-id="278c1-131">After the assessment files have attained a stable level of training, Advanced eDiscovery is ready for Batch calculation.</span></span>
  
> [!NOTE]
> <span data-ttu-id="278c1-132">Normalmente, después de tres muestras de aprendizaje estables, el siguiente paso es "Cálculo por lotes".</span><span class="sxs-lookup"><span data-stu-id="278c1-132">Usually, after three stable training samples, the next step is "Batch calculation".</span></span> <span data-ttu-id="278c1-133">Puede haber excepciones, por ejemplo, cuando hubo cambios en el etiquetado de archivos de ejemplos anteriores o cuando se agregaron archivos de ed.</span><span class="sxs-lookup"><span data-stu-id="278c1-133">There may be exceptions, for example, when there were changes to the tagging of files from earlier samples or when seed files were added.</span></span> 
  
### <a name="performing-batch-calculation"></a><span data-ttu-id="278c1-134">Realizar cálculos por lotes</span><span class="sxs-lookup"><span data-stu-id="278c1-134">Performing Batch calculation</span></span>

<span data-ttu-id="278c1-135">El cálculo por lotes se ejecuta como el siguiente paso después de completar correctamente el aprendizaje (cuando la barra de progreso muestra un estado de aprendizaje estable, una marca de verificación y un estado estable en la sugerencia de herramienta). El cálculo por lotes aplica los conocimientos adquiridos durante el aprendizaje de relevancia a toda la población de archivos, para evaluar la relevancia de los archivos y asignar puntuaciones de relevancia.</span><span class="sxs-lookup"><span data-stu-id="278c1-135">Batch calculation is executed as the next step after training is successfully completed (when a stable training status is shown by the progress bar, a checkmark and stable status in the tool-tip.) Batch calculation applies the knowledge acquired during the Relevance training to the entire file population, to assess the files' relevance and to assign Relevance scores.</span></span>
  
<span data-ttu-id="278c1-136">Cuando hay más de un problema, el cálculo por lotes se realiza por problema.</span><span class="sxs-lookup"><span data-stu-id="278c1-136">When there is more than one issue, Batch calculation is done per issue.</span></span> <span data-ttu-id="278c1-137">Durante el cálculo por lotes, el progreso se supervisa al procesar todos los archivos.</span><span class="sxs-lookup"><span data-stu-id="278c1-137">During Batch calculation, progress is monitored while processing all of the files.</span></span> 
  
<span data-ttu-id="278c1-138">Aquí, el siguiente paso recomendado es "Ninguno", lo que indica que no se requiere ningún aprendizaje de relevancia iterativo adicional en este momento.</span><span class="sxs-lookup"><span data-stu-id="278c1-138">Here, the recommended next step is "None", which indicates that no additional iterative Relevance training is required at this point.</span></span> <span data-ttu-id="278c1-139">La siguiente fase es la pestaña **Decisión \> de** relevancia.</span><span class="sxs-lookup"><span data-stu-id="278c1-139">The next phase is the **Relevance \> Decide** tab.</span></span> 
  
<span data-ttu-id="278c1-140">Si desea importar nuevos archivos después del cálculo por lotes, el administrador puede agregar los archivos importados a una nueva carga.</span><span class="sxs-lookup"><span data-stu-id="278c1-140">If you want to import new files after Batch calculation, the administrator can add the imported files to a new load.</span></span>
  
> [!NOTE]
> <span data-ttu-id="278c1-141">Si hace clic **en Cancelar** durante el cálculo por lotes, el proceso guarda lo que ya se ejecutó.</span><span class="sxs-lookup"><span data-stu-id="278c1-141">If you click **Cancel** during Batch calculation, the process saves what was already executed.</span></span> <span data-ttu-id="278c1-142">Si vuelve a ejecutar el cálculo por lotes, el proceso continuará desde el último punto ejecutado.</span><span class="sxs-lookup"><span data-stu-id="278c1-142">If you run Batch calculation again, the process will continue from the last executed point.</span></span> 
  
### <a name="assessing-tagging-consistency"></a><span data-ttu-id="278c1-143">Evaluar la coherencia de etiquetado</span><span class="sxs-lookup"><span data-stu-id="278c1-143">Assessing tagging consistency</span></span>

<span data-ttu-id="278c1-144">Si hay incoherencias en el etiquetado de archivos, puede afectar al análisis.</span><span class="sxs-lookup"><span data-stu-id="278c1-144">If there are inconsistencies in file tagging, it can affect the analysis.</span></span> <span data-ttu-id="278c1-145">El Advanced eDiscovery de coherencia de etiquetado se puede usar cuando los resultados no son óptimos o la coherencia está en duda.</span><span class="sxs-lookup"><span data-stu-id="278c1-145">The Advanced eDiscovery tagging consistency process can be used when results are not optimal or consistency is in doubt.</span></span> <span data-ttu-id="278c1-146">Se devuelve una lista de posibles archivos etiquetados incoherentemente y se pueden revisar y volver a etiquetar, según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="278c1-146">A list of possible inconsistently tagged files is returned, and they can be reviewed and retagged, as necessary.</span></span>
  
> [!NOTE]
> <span data-ttu-id="278c1-147">Después de siete o más rondas de aprendizaje después de la evaluación, la coherencia de etiquetado se puede ver en **Resultados** detallados del seguimiento de relevancia Progreso de \>  \>  \>  \> **la formación.**</span><span class="sxs-lookup"><span data-stu-id="278c1-147">After seven or more training rounds following assessment, tagging consistency can be viewed in **Relevance** \> **Track** \> **Issue** \> **Detailed results** \> **Training progress**.</span></span> <span data-ttu-id="278c1-148">Esta revisión se realiza por un problema a la vez.</span><span class="sxs-lookup"><span data-stu-id="278c1-148">This review is done for one issue at a time.</span></span>
  
1. <span data-ttu-id="278c1-149">En **Pista \> de relevancia,** expanda la fila de un problema.</span><span class="sxs-lookup"><span data-stu-id="278c1-149">In **Relevance \> Track**, expand an issue's row.</span></span>
  
2. <span data-ttu-id="278c1-150">A la derecha del **paso Siguiente,** haga clic **en Modificar**.</span><span class="sxs-lookup"><span data-stu-id="278c1-150">To the right of **Next step**, click **Modify**.</span></span>
  
3. <span data-ttu-id="278c1-151">Seleccione **Etiquetar incoherencias** como **la** opción Paso siguiente, después de siete ejemplos de aprendizaje y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="278c1-151">Select **Tag inconsistencies** as the **Next step** option, after seven training samples and click **OK**.</span></span>
  
4. <span data-ttu-id="278c1-152">Seleccione **Incoherencias de etiqueta.**</span><span class="sxs-lookup"><span data-stu-id="278c1-152">Select **Tag inconsistencies**.</span></span> <span data-ttu-id="278c1-153">La **pestaña** Etiqueta se abre mostrando una lista de las incoherencias para volver a etiquetar según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="278c1-153">The **Tag** tab opens displaying a list of the inconsistencies to retag as necessary.</span></span>
  
5. <span data-ttu-id="278c1-154">Haga **clic en** Calcular para enviar los cambios.</span><span class="sxs-lookup"><span data-stu-id="278c1-154">Click **Calculate** to submit the changes.</span></span> <span data-ttu-id="278c1-155">El siguiente paso después de etiquetar incoherencias es "Training".</span><span class="sxs-lookup"><span data-stu-id="278c1-155">The next step after tagging inconsistencies is "Training".</span></span> 
  
## <a name="viewing-and-using-relevance-results"></a><span data-ttu-id="278c1-156">Visualización y uso de resultados de relevancia</span><span class="sxs-lookup"><span data-stu-id="278c1-156">Viewing and using Relevance results</span></span>

<span data-ttu-id="278c1-157">En la **pestaña Pista \> de** relevancia, expanda la fila de un problema y, junto a **Resultados detallados,** haga clic en **Ver**.</span><span class="sxs-lookup"><span data-stu-id="278c1-157">In the **Relevance \> Track** tab, expand an issue's row, and next to **Detailed results**, click **View**.</span></span> <span data-ttu-id="278c1-158">Se muestran los paneles de resultados detallados, como se muestra y se describe a continuación.</span><span class="sxs-lookup"><span data-stu-id="278c1-158">The Detailed results panes are displayed, as shown and described below.</span></span>
  
![Resultados detallados de la formación de relevancia](../media/495c04a9-ed1e-4355-8cab-c14270ca2bbb.png)
  
### <a name="tagging-summary"></a><span data-ttu-id="278c1-160">Resumen de etiquetado</span><span class="sxs-lookup"><span data-stu-id="278c1-160">Tagging summary</span></span>

 <span data-ttu-id="278c1-161">En el ejemplo siguiente, el resumen de etiquetado muestra totales para cada uno de los procesos de etiquetado de archivos de evaluación, aprendizaje y ponerse al día. </span><span class="sxs-lookup"><span data-stu-id="278c1-161">In the example shown below, the **Tagging summary** displays totals for each of Assessment, Training, and Catch-up file tagging processes.</span></span>
  
![Resumen de etiquetado del seguimiento de relevancia](../media/0ec906fc-bc84-4245-a964-fb3ca37891db.png)
  
### <a name="keywords"></a><span data-ttu-id="278c1-163">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="278c1-163">Keywords</span></span>

<span data-ttu-id="278c1-164">Una palabra clave es una cadena, palabra, frase o secuencia única de palabras en un archivo identificado por Advanced eDiscovery como un indicador significativo de si un archivo es relevante.</span><span class="sxs-lookup"><span data-stu-id="278c1-164">A keyword is a unique string, word, phrase, or sequence of words in a file identified by Advanced eDiscovery as a significant indicator of whether a file is relevant.</span></span> <span data-ttu-id="278c1-165">Las columnas "Incluir" enumeran palabras clave y grosores en archivos etiquetados como Relevantes y las columnas "Excluir" enumeran palabras clave y ponderaciones en archivos etiquetados como No relevantes.</span><span class="sxs-lookup"><span data-stu-id="278c1-165">The "Include" columns list keyword and weights in files tagged as Relevant, and the "Exclude" columns lists keywords and weights in files tagged as Not relevant.</span></span>
  
<span data-ttu-id="278c1-166">Advanced eDiscovery asigna valores de peso de palabras clave negativos o positivos.</span><span class="sxs-lookup"><span data-stu-id="278c1-166">Advanced eDiscovery assigns negative or positive keyword weight values.</span></span> <span data-ttu-id="278c1-167">Cuanto mayor sea el peso, mayor será la probabilidad de que un archivo en el que aparece la palabra clave se asigne una puntuación de relevancia más alta durante el cálculo por lotes.</span><span class="sxs-lookup"><span data-stu-id="278c1-167">The higher the weight, the higher the likelihood that a file in which the keyword appears is assigned a higher Relevance score during Batch calculation.</span></span>
  
<span data-ttu-id="278c1-168">La Advanced eDiscovery lista de palabras clave se puede usar para complementar una lista creada por un experto o como una comprobación indirecta de la cordura en cualquier momento del proceso de revisión de archivos.</span><span class="sxs-lookup"><span data-stu-id="278c1-168">The Advanced eDiscovery list of keywords can be used to supplement a list built by an expert or as an indirect sanity check at any point in the file review process.</span></span>
  
### <a name="training-progress"></a><span data-ttu-id="278c1-169">Progreso de la formación</span><span class="sxs-lookup"><span data-stu-id="278c1-169">Training progress</span></span>

<span data-ttu-id="278c1-170">El **panel Progreso de** aprendizaje incluye un gráfico de progreso de aprendizaje y una presentación del indicador de calidad, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="278c1-170">The **Training Progress** pane includes a training progress graph and quality indicator display, as shown in the example below.</span></span>
  
![Progreso de formación del seguimiento de relevancia](../media/8a5089f5-a162-4246-ae09-bc1921859860.png)
  
<span data-ttu-id="278c1-172">**Indicador de calidad de aprendizaje:** muestra la clasificación de la coherencia de etiquetado de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="278c1-172">**Training quality indicator**: Displays the rating of the tagging consistency as follows:</span></span>
  
- <span data-ttu-id="278c1-173">**Bueno:** los archivos se etiquetan de forma coherente.</span><span class="sxs-lookup"><span data-stu-id="278c1-173">**Good**: Files are tagged consistently.</span></span> <span data-ttu-id="278c1-174">(Se muestra la luz verde)</span><span class="sxs-lookup"><span data-stu-id="278c1-174">(Green light displayed)</span></span>
  
- <span data-ttu-id="278c1-175">**Medium:** es posible que algunos archivos se etiquete de forma incoherente.</span><span class="sxs-lookup"><span data-stu-id="278c1-175">**Medium**: Some files may be tagged inconsistently.</span></span> <span data-ttu-id="278c1-176">(Se muestra luz amarilla)</span><span class="sxs-lookup"><span data-stu-id="278c1-176">(Yellow light displayed)</span></span>

- <span data-ttu-id="278c1-177">**Advertencia:** muchos archivos pueden etiquetarse de forma incoherente.</span><span class="sxs-lookup"><span data-stu-id="278c1-177">**Warning**: Many files may be tagged inconsistently.</span></span> <span data-ttu-id="278c1-178">(Se muestra la luz roja)</span><span class="sxs-lookup"><span data-stu-id="278c1-178">(Red light displayed)</span></span>

<span data-ttu-id="278c1-179">**Gráfico de progreso del** aprendizaje: muestra el grado de estabilidad del aprendizaje de relevancia después de muchos ciclos de aprendizaje de relevancia en comparación con el valor de la medida F.</span><span class="sxs-lookup"><span data-stu-id="278c1-179">**Training progress graph**: Shows the degree of Relevance training stability after many Relevance training cycles in comparison to the F-measure value.</span></span> <span data-ttu-id="278c1-180">A medida que nos movemos de la izquierda a la derecha a través del gráfico, el intervalo de confianza se estrecha y se usa, junto con la medida F, mediante Advanced eDiscovery Relevancia para determinar la estabilidad cuando se optimizan los resultados del aprendizaje de relevancia.</span><span class="sxs-lookup"><span data-stu-id="278c1-180">As we move from the left to the right across the graph, the confidence interval narrows and is used, along with the F-measure, by Advanced eDiscovery Relevance to determine stability when the Relevance training results are optimized.</span></span>
  
> [!NOTE]
> <span data-ttu-id="278c1-181">Relevancia usa F2, una métrica de medida F donde Recall recibe el doble de peso que Precision.</span><span class="sxs-lookup"><span data-stu-id="278c1-181">Relevance uses F2, an F-measure metric where Recall receives twice as much weight as Precision.</span></span> <span data-ttu-id="278c1-182">Para los casos con alta riqueza (más del 25%), Relevancia usa F1 (relación 1:1).</span><span class="sxs-lookup"><span data-stu-id="278c1-182">For cases with high richness (over 25%), Relevance uses F1 (1:1 ratio).</span></span> <span data-ttu-id="278c1-183">La relación de medida F se puede configurar en **Configuración de** \> **relevancia Configuración avanzada**.</span><span class="sxs-lookup"><span data-stu-id="278c1-183">The F-measure ratio can be configured in **Relevance setup** \> **Advanced settings**.</span></span>
  
### <a name="batch-calculation-results"></a><span data-ttu-id="278c1-184">Resultados del cálculo por lotes</span><span class="sxs-lookup"><span data-stu-id="278c1-184">Batch calculation results</span></span>

<span data-ttu-id="278c1-185">El **panel de resultados del** cálculo por lotes incluye el número de archivos que se puntuaron para Relevancia, de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="278c1-185">The **Batch calculation results** pane includes the number of files that were scored for Relevance, as follows:</span></span> 
  
- <span data-ttu-id="278c1-186">**Success**</span><span class="sxs-lookup"><span data-stu-id="278c1-186">**Success**</span></span>
  
- <span data-ttu-id="278c1-187">**Empty**: No contiene texto, por ejemplo, solo espacios/pestañas</span><span class="sxs-lookup"><span data-stu-id="278c1-187">**Empty**: Contains no text, for example, only spaces/tabs</span></span>
  
- <span data-ttu-id="278c1-188">**Error:** debido a un tamaño excesivo o no se pudo leer</span><span class="sxs-lookup"><span data-stu-id="278c1-188">**Failed**: Due to excessive size or could not be read</span></span>
  
- <span data-ttu-id="278c1-189">**Ignored**: Debido a un tamaño excesivo</span><span class="sxs-lookup"><span data-stu-id="278c1-189">**Ignored**: Due to excessive size</span></span>
  
- <span data-ttu-id="278c1-190">**Nebulous:** contiene texto sin sentido o sin características relevantes para el problema</span><span class="sxs-lookup"><span data-stu-id="278c1-190">**Nebulous**: Contains meaningless text or no features relevant to the issue</span></span>
  
> [!NOTE]
> <span data-ttu-id="278c1-191">Empty, Failed, Ignored o Nebulous recibirán una puntuación de relevancia de -1.</span><span class="sxs-lookup"><span data-stu-id="278c1-191">Empty, Failed, Ignored, or Nebulous will receive a Relevance score of -1.</span></span>
  
### <a name="training-statistics"></a><span data-ttu-id="278c1-192">Estadísticas de aprendizaje</span><span class="sxs-lookup"><span data-stu-id="278c1-192">Training statistics</span></span>

<span data-ttu-id="278c1-193">El **panel Estadísticas de aprendizaje** muestra estadísticas y gráficos basados en los resultados del Advanced eDiscovery de relevancia.</span><span class="sxs-lookup"><span data-stu-id="278c1-193">The **Training statistics** pane displays statistics and graphs based on results from Advanced eDiscovery Relevance training.</span></span> 
  
![Estadísticas de formación del seguimiento de relevancia](../media/9a07740e-20d3-49fb-b9b9-84265e0a1836.png)
  
<span data-ttu-id="278c1-195">Esta vista muestra lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="278c1-195">This view shows the following:</span></span>
  
- <span data-ttu-id="278c1-196">**Relación revisión-recuperación:** comparación de resultados según las puntuaciones de relevancia en una revisión hipotéticamente lineal.</span><span class="sxs-lookup"><span data-stu-id="278c1-196">**Review-recall ratio**: Comparison of results according to Relevance scores in a hypothetically linear review.</span></span> <span data-ttu-id="278c1-197">La recuperación se calcula teniendo en cuenta el conjunto de tamaños del conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="278c1-197">Recall is estimated given the review set size set.</span></span>
  
- <span data-ttu-id="278c1-198">**Parámetros:** estadísticas calculadas acumulativas relativas al conjunto de revisión en relación con la población de archivos para todo el caso.</span><span class="sxs-lookup"><span data-stu-id="278c1-198">**Parameters**: Cumulative calculated statistics pertaining to the review set in relation to the file population for the entire case.</span></span>
  
- <span data-ttu-id="278c1-199">**Review**: Percentage of files to review based on this cutoff.</span><span class="sxs-lookup"><span data-stu-id="278c1-199">**Review**: Percentage of files to review based on this cutoff.</span></span>
  
- <span data-ttu-id="278c1-200">**Recall**: Porcentaje de archivos relevantes en el conjunto de revisión.</span><span class="sxs-lookup"><span data-stu-id="278c1-200">**Recall**: Percentage of Relevant files in the review set.</span></span> 
  
- <span data-ttu-id="278c1-201">**Distribución por puntuación de relevancia:** los archivos de la pantalla gris oscuro a la izquierda están por debajo de la puntuación de límite.</span><span class="sxs-lookup"><span data-stu-id="278c1-201">**Distribution by relevance score**: Files in the dark gray display to the left are below the cutoff score.</span></span> <span data-ttu-id="278c1-202">Una sugerencia de herramienta muestra la puntuación relevancia y el porcentaje relacionado de archivos en el conjunto de archivos de revisión en relación con el total de archivos.</span><span class="sxs-lookup"><span data-stu-id="278c1-202">A tool-tip displays the Relevance score and the related percentage of files in the review file set in relation to the total files.</span></span>
