---
title: Etiquetado y evaluación en eDiscovery avanzado
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
ms.assetid: b5c82de7-ed2f-4cc6-becd-db403faf4d18
ROBOTS: NOINDEX, NOFOLLOW
description: Revise los pasos para realizar la formación de evaluación, incluido el etiquetado de archivos y la revisión de los resultados de la evaluación en eDiscovery avanzado.
ms.openlocfilehash: 15bc8254ea1589d9afa17a74eaf3bfbcdfd4bba0
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769195"
---
# <a name="tagging-and-assessment-in-the-relevance-module-in-advanced-ediscovery"></a><span data-ttu-id="93b96-103">Etiquetado y evaluación en el módulo Relevancia en eDiscovery avanzado</span><span class="sxs-lookup"><span data-stu-id="93b96-103">Tagging and Assessment in the Relevance module in Advanced eDiscovery</span></span>
  
<span data-ttu-id="93b96-104">En esta sección se describe el procedimiento para la evaluación en el módulo Relevancia en eDiscovery avanzado.</span><span class="sxs-lookup"><span data-stu-id="93b96-104">This section describes the procedure for Assessment in the Relevance module in Advanced eDiscovery.</span></span>
  
## <a name="performing-assessment-training-and-analysis"></a><span data-ttu-id="93b96-105">Realización de análisis y formación de evaluación</span><span class="sxs-lookup"><span data-stu-id="93b96-105">Performing Assessment training and analysis</span></span>

1. <span data-ttu-id="93b96-106">En la pestaña **Seguimiento \> de** relevancia, haga clic **en Evaluación** para iniciar la evaluación de casos.</span><span class="sxs-lookup"><span data-stu-id="93b96-106">In the **Relevance \> Track** tab, click **Assessment** to start case assessment.</span></span>

    <span data-ttu-id="93b96-107">Para fines de este procedimiento, se crea un conjunto de evaluación  de ejemplo de 500 archivos y se muestra la pestaña Etiqueta, que contiene el panel de etiquetado, el contenido del archivo mostrado y otras opciones de etiquetado.</span><span class="sxs-lookup"><span data-stu-id="93b96-107">For example purposes in this procedure, a sample assessment set of 500 files is created and the **Tag** tab is displayed, which contains the Tagging panel, displayed file content and other tagging options.</span></span> 

    ![Pestaña de etiqueta de relevancia para la evaluación](../media/c8acf891-b1cd-4344-816c-eabb8cbbe742.png)
  
2. <span data-ttu-id="93b96-109">Revisa cada archivo del ejemplo, determina la relevancia del archivo para cada problema de caso y etiqueta el archivo con los botones Relevancia (R), No relevante (NR) y Omitir en el **panel** de etiquetado.</span><span class="sxs-lookup"><span data-stu-id="93b96-109">Review each file in the sample, determine the file's relevance for each case issue, and tag the file using the Relevance (R), Not relevant (NR) and Skip buttons in the **Tagging panel** pane.</span></span> 

    > [!NOTE]
    >  <span data-ttu-id="93b96-110">La evaluación requiere 500 archivos etiquetados.</span><span class="sxs-lookup"><span data-stu-id="93b96-110">Assessment requires 500 tagged files.</span></span> <span data-ttu-id="93b96-111">Si los archivos se "omiten", recibirá más archivos para etiquetar.</span><span class="sxs-lookup"><span data-stu-id="93b96-111">If files are "skipped", you will receive more files to tag.</span></span> 
  
3. <span data-ttu-id="93b96-112">Después de etiquetar todos los archivos del ejemplo, haga clic **en Calcular**.</span><span class="sxs-lookup"><span data-stu-id="93b96-112">After tagging all files in the sample, click **Calculate**.</span></span>

    <span data-ttu-id="93b96-113">El margen de error actual de evaluación y  la enriquecimiento se calculan y se muestran en la pestaña Seguimiento de relevancia, con detalles ampliados por problema, como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="93b96-113">The Assessment current error margin and richness are calculated and displayed in the **Relevance Track** tab, with expanded details per issue, as shown below.</span></span> <span data-ttu-id="93b96-114">En la sección Revisión de los resultados de la evaluación se describen más detalles sobre este cuadro [de](#reviewing-assessment-results) diálogo.</span><span class="sxs-lookup"><span data-stu-id="93b96-114">More details about this dialog are described in the [Reviewing assessment results](#reviewing-assessment-results) section.</span></span>

    ![Seguimiento de relevancia: evaluación](../media/da911ba5-8678-40d6-9ad5-fd0b058355c1.png)
  
    > [!TIP]
    > <span data-ttu-id="93b96-116">De forma predeterminada, se recomienda continuar con el paso siguiente predeterminado cuando se haya completado el indicador de progreso de la evaluación del problema, lo que indica que se revisó la muestra de evaluación y se etiquetaron suficientes archivos relevantes.</span><span class="sxs-lookup"><span data-stu-id="93b96-116">By default, we recommend that you proceed to the default Next step when the Assessment progress indicator for the issue has completed, indicating that the assessment sample was reviewed and sufficient relevant files were tagged.</span></span> <span data-ttu-id="93b96-117">> lo contrario, si desea ver  los resultados de la pestaña Seguimiento y  controlar el margen de error y el siguiente paso, haga clic en Modificar adyacente al paso **siguiente,** seleccione Continuar evaluación y, a continuación, haga clic en Aceptar **.**</span><span class="sxs-lookup"><span data-stu-id="93b96-117">> Otherwise, if you want to view the **Track** tab results and control the margin of error and the next step, click **Modify** adjacent to **Next Step**, select **Continue assessment**, and then click **OK**.</span></span>
  
4. <span data-ttu-id="93b96-118">Haga **clic en** Modificar a la derecha de la casilla de verificación Evaluación para ver y especificar parámetros de evaluación por problema. </span><span class="sxs-lookup"><span data-stu-id="93b96-118">Click **Modify** to the right of the **Assessment** check box to view and specify assessment parameters per issue.</span></span> <span data-ttu-id="93b96-119">Se **muestra un** cuadro de diálogo de nivel de evaluación para cada problema, como se muestra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="93b96-119">An **Assessment level** dialog for each issue is displayed, as shown in the following example:</span></span> 

    ![Problema de caso del nivel de evaluación](../media/b7113fef-d125-4617-ae1b-c9eb0bf79aec.png)
  
    <span data-ttu-id="93b96-121">Los siguientes parámetros para el problema se calculan y se muestran en el cuadro de diálogo **Nivel de** evaluación:</span><span class="sxs-lookup"><span data-stu-id="93b96-121">The following parameters for the issue are calculated and displayed in the **Assessment level** dialog:</span></span> 

    <span data-ttu-id="93b96-122">**Margen de error de destino para estimaciones de** recuperación: en función de este valor, se calcula el número estimado de archivos adicionales necesarios para revisar.</span><span class="sxs-lookup"><span data-stu-id="93b96-122">**Target error margin for recall estimates**: Based on this value, the estimated number of additional files necessary to review is calculated.</span></span> <span data-ttu-id="93b96-123">El margen usado para la recuperación es mayor que el 75 % y con un nivel de confianza del 95 %.</span><span class="sxs-lookup"><span data-stu-id="93b96-123">The margin used for recall is greater than 75% and with a 95% confidence level.</span></span>

    <span data-ttu-id="93b96-124">**Archivos de evaluación adicionales necesarios:** indica cuántos archivos más son necesarios si no se han cumplido los requisitos del margen de error actual.</span><span class="sxs-lookup"><span data-stu-id="93b96-124">**Additional assessment files required**: Indicates how many more files are necessary if the current error margin's requirements have not been met.</span></span> 

5. <span data-ttu-id="93b96-125">Para ajustar el margen de error actual y ver el efecto de diferentes márgenes de error (por problema):</span><span class="sxs-lookup"><span data-stu-id="93b96-125">To adjust the current error margin and see the effect of different error margins (per issue):</span></span>

6. <span data-ttu-id="93b96-126">En la **lista Seleccionar** problema, seleccione un problema.</span><span class="sxs-lookup"><span data-stu-id="93b96-126">In the **Select issue** list, select an issue.</span></span> 

7. <span data-ttu-id="93b96-127">En **el margen de error de destino para las estimaciones de** recuperación, escriba un nuevo valor.</span><span class="sxs-lookup"><span data-stu-id="93b96-127">In **Target error margin for recall estimates**, enter a new value.</span></span>

8. <span data-ttu-id="93b96-128">Haz **clic en Actualizar** valores para ver el impacto de los ajustes.</span><span class="sxs-lookup"><span data-stu-id="93b96-128">Click **Update values** to see the impact of the adjustments.</span></span> 

9. <span data-ttu-id="93b96-129">Haga **clic en Avanzadas** en el cuadro de diálogo **Nivel** de evaluación para ver los siguientes parámetros y detalles adicionales:</span><span class="sxs-lookup"><span data-stu-id="93b96-129">Click **Advanced** in the **Assessment level** dialog to see the following additional parameters and details:</span></span> 

    ![Vista avanzada del problema de caso del nivel de evaluación](../media/577d7e0e-95df-48c2-9dec-bdeab5e801d8.png)
  
    - <span data-ttu-id="93b96-131">**Enriquecimiento estimado:** enriquecimiento estimado según los resultados de la evaluación actuales</span><span class="sxs-lookup"><span data-stu-id="93b96-131">**Estimated richness**: Estimated richness according to the current assessment results</span></span>

    - <span data-ttu-id="93b96-132">**Para la recuperación:** de forma predeterminada, el margen de error de destino se aplica a la recuperación superior al 75 %.</span><span class="sxs-lookup"><span data-stu-id="93b96-132">**For assumed recall**: By default, the target error margin applies to recall above 75%.</span></span> <span data-ttu-id="93b96-133">Haga **clic** en Editar si desea cambiar este parámetro y controlar el margen de error en un intervalo diferente de valores de recuperación.</span><span class="sxs-lookup"><span data-stu-id="93b96-133">Click **Edit** if you want to change this parameter and control the margin of error on a different range of recall values.</span></span> 

    - <span data-ttu-id="93b96-134">**Nivel de confianza:** de forma predeterminada, el margen de error recomendado para la confianza es del 95 %.</span><span class="sxs-lookup"><span data-stu-id="93b96-134">**Confidence level**: By default, the recommended error margin for confidence is 95%.</span></span> <span data-ttu-id="93b96-135">Haga **clic en** Editar si desea cambiar este parámetro.</span><span class="sxs-lookup"><span data-stu-id="93b96-135">Click **Edit** if you want to change this parameter.</span></span>

    - <span data-ttu-id="93b96-136">**Margen de error de** enriquecimiento esperado: dados los valores actualizados, este es el margen de error esperado de la enriquecimiento, después de que se revisen todos los archivos de evaluación adicionales.</span><span class="sxs-lookup"><span data-stu-id="93b96-136">**Expected richness error margin**: Given the updated values, this is the expected margin of error of the richness, after all additional assessment files are reviewed.</span></span>

    - <span data-ttu-id="93b96-137">**Se requieren archivos de evaluación** adicionales: dados los valores actualizados, el número de archivos de evaluación adicionales que deben revisarse para alcanzar el objetivo.</span><span class="sxs-lookup"><span data-stu-id="93b96-137">**Additional assessment files required**: Given the updated values, the number of additional assessment files that need to be reviewed to reach the target.</span></span>

    - <span data-ttu-id="93b96-138">**Total de archivos de evaluación necesarios:** teniendo en cuenta los valores actualizados, el total de archivos de evaluación necesarios para su revisión.</span><span class="sxs-lookup"><span data-stu-id="93b96-138">**Total assessment files required**: Given the updated values, total assessment files required for review.</span></span>

    - <span data-ttu-id="93b96-139">**Número esperado de archivos relevantes** en la evaluación: dados los valores actualizados, el número esperado de archivos relevantes en toda la evaluación después de revisar todos los archivos de evaluación adicionales.</span><span class="sxs-lookup"><span data-stu-id="93b96-139">**Expected number of relevant files in assessment**: Given the updated values, the expected number of relevant files in the entire assessment after all additional assessment files are reviewed.</span></span>

10. <span data-ttu-id="93b96-140">Haga **clic en Recalcular valores,** si se cambian los parámetros.</span><span class="sxs-lookup"><span data-stu-id="93b96-140">Click **Recalculate values**, if parameters are changed.</span></span> <span data-ttu-id="93b96-141">Cuando haya terminado, si hay un  problema, haga clic  en Aceptar para guardar los cambios (o siguiente cuando haya varios problemas para revisar o modificar y, a continuación, **finalizar**).</span><span class="sxs-lookup"><span data-stu-id="93b96-141">When you're done, if there is one issue, click **OK** to save the changes (or **Next** when there are multiple issues to review or modify and then **Finish**).</span></span> 

    <span data-ttu-id="93b96-142">Cuando hay varios problemas, después de revisar o ajustar todos los problemas, se muestra un nivel de **evaluación:** cuadro de diálogo de resumen, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="93b96-142">When there are multiple issues, after all issues have been reviewed or adjusted, an **Assessment level: summary** dialog is displayed, as shown in the following example.</span></span> 

    ![Resumen del nivel de evaluación](../media/4997b46d-10a5-4abc-b3b2-7b75a370eb9e.png)
  
    <span data-ttu-id="93b96-144">Una vez completada correctamente la evaluación, continúe con la siguiente etapa de la formación de relevancia.</span><span class="sxs-lookup"><span data-stu-id="93b96-144">On successful completion of assessment, proceed to the next stage in Relevance training.</span></span>

## <a name="reviewing-assessment-results"></a><span data-ttu-id="93b96-145">Revisión de los resultados de la evaluación</span><span class="sxs-lookup"><span data-stu-id="93b96-145">Reviewing assessment results</span></span>

<span data-ttu-id="93b96-146">Después de etiquetar un ejemplo de evaluación, los resultados de la evaluación se calculan y se muestran en la pestaña Seguimiento de relevancia.</span><span class="sxs-lookup"><span data-stu-id="93b96-146">After an Assessment sample is tagged, the assessment results are calculated and displayed in the Relevance Track tab.</span></span>
  
<span data-ttu-id="93b96-147">Los siguientes resultados se muestran en la pantalla De seguimiento expandida:</span><span class="sxs-lookup"><span data-stu-id="93b96-147">The following results are displayed in the expanded Track display:</span></span>
  
- <span data-ttu-id="93b96-148">Margen de error actual de evaluación para estimaciones de recuperación</span><span class="sxs-lookup"><span data-stu-id="93b96-148">Assessment current error margin for recall estimates</span></span>

- <span data-ttu-id="93b96-149">Enriquecimiento estimado</span><span class="sxs-lookup"><span data-stu-id="93b96-149">Estimated richness</span></span>

- <span data-ttu-id="93b96-150">Se requieren archivos de evaluación adicionales (para revisión)</span><span class="sxs-lookup"><span data-stu-id="93b96-150">Additional assessment files required (for review)</span></span>

<span data-ttu-id="93b96-151">El margen de error actual de evaluación es el margen de error recomendado por eDiscovery avanzado.</span><span class="sxs-lookup"><span data-stu-id="93b96-151">The Assessment current error margin is the error margin recommended by Advanced eDiscovery.</span></span> <span data-ttu-id="93b96-152">El número que se muestra para los "archivos de evaluación adicionales necesarios" corresponde a esa recomendación.</span><span class="sxs-lookup"><span data-stu-id="93b96-152">The number displayed for the "Additional assessment files required" corresponds to that recommendation.</span></span>
  
<span data-ttu-id="93b96-153">El indicador de progreso de la evaluación muestra el nivel de finalización de la evaluación, dado el margen de error actual.</span><span class="sxs-lookup"><span data-stu-id="93b96-153">The Assessment progress indicator shows the level of completion of the assessment, given the current error margin.</span></span> <span data-ttu-id="93b96-154">Cuando la evaluación esté en curso, el usuario etiquetará otra muestra de evaluación.</span><span class="sxs-lookup"><span data-stu-id="93b96-154">When assessment is underway, the user will tag another assessment sample.</span></span>
  
<span data-ttu-id="93b96-155">Cuando el indicador de progreso de la evaluación muestra la evaluación como completada, significa que se completó la revisión de la muestra de evaluación y se etiquetaron suficientes archivos relevantes.</span><span class="sxs-lookup"><span data-stu-id="93b96-155">When the assessment progress indicator shows assessment as complete, that means the assessment sample review was completed and sufficient relevant files were tagged.</span></span> 
  
<span data-ttu-id="93b96-156">La pantalla De seguimiento expandida muestra el siguiente paso recomendado, las estadísticas de evaluación y el acceso a los resultados detallados.</span><span class="sxs-lookup"><span data-stu-id="93b96-156">The expanded Track display shows the recommended next step, the assessment statistics, and access to detailed results.</span></span>
  
<span data-ttu-id="93b96-157">Cuando la variedad es muy baja, el número de archivos de evaluación adicionales necesarios para alcanzar un número mínimo de archivos relevantes para generar estadísticas útiles es muy alto.</span><span class="sxs-lookup"><span data-stu-id="93b96-157">When richness is very low, the number of additional assessment files needed to reach a minimal number of relevant files to produce useful statistics is very high.</span></span> <span data-ttu-id="93b96-158">A continuación, la exhibición avanzada de documentos electrónicos recomendará pasar a la formación.</span><span class="sxs-lookup"><span data-stu-id="93b96-158">Advanced eDiscovery will then recommend moving on to training.</span></span> <span data-ttu-id="93b96-159">El indicador de progreso de la evaluación se sombreará y no habrá estadísticas disponibles.</span><span class="sxs-lookup"><span data-stu-id="93b96-159">The assessment progress indicator will be shaded, and no statistics will be available.</span></span>
  
<span data-ttu-id="93b96-160">En ausencia de estabilización basada estadísticamente, habrá resultados con un nivel inferior de precisión y nivel de confianza.</span><span class="sxs-lookup"><span data-stu-id="93b96-160">In the absence of statistically based stabilization, there will be results with a lower level of accuracy and confidence level.</span></span> <span data-ttu-id="93b96-161">Sin embargo, estos resultados se pueden usar para buscar archivos relevantes cuando no es necesario conocer el porcentaje de archivos relevantes encontrados.</span><span class="sxs-lookup"><span data-stu-id="93b96-161">However, these results can be used to find relevant files when you do not need to know the percentage of relevant files found.</span></span> <span data-ttu-id="93b96-162">De forma similar, este estado se puede usar para entrenar problemas con poca variedad, donde las puntuaciones de relevancia pueden acelerar el acceso a los archivos relevantes para un problema específico.</span><span class="sxs-lookup"><span data-stu-id="93b96-162">Similarly, this status can be used to train issues with low richness, where Relevance scores can accelerate access to files relevant to a specific issue.</span></span>
  
> [!TIP]
> <span data-ttu-id="93b96-163">En la **pestaña \> Seguimiento de** relevancia, visualización de problemas expandida, están disponibles las siguientes opciones de visualización:</span><span class="sxs-lookup"><span data-stu-id="93b96-163">In the **Relevance \> Track** tab, expanded issue display, the following viewing options are available:</span></span> 
> 
> <span data-ttu-id="93b96-164">El siguiente paso recomendado, como Paso **siguiente:** el etiquetado se puede  omitir (por problema) haciendo clic en el botón Modificar a su derecha y, a continuación, seleccionando un paso diferente en el **paso siguiente**.</span><span class="sxs-lookup"><span data-stu-id="93b96-164">The recommended next step, such as **Next step: Tagging** can be bypassed (per issue) by clicking the **Modify** button to its right, and then selecting an different step in the **Next step**.</span></span> <span data-ttu-id="93b96-165">Cuando el indicador de progreso de la evaluación no se haya completado, la evaluación será la siguiente opción recomendada para etiquetar más archivos de evaluación y aumentar la precisión de las estadísticas.</span><span class="sxs-lookup"><span data-stu-id="93b96-165">When the assessment progress indicator has not completed, assessment will be the next recommended option, to tag more assessment files and increase statistics accuracy.</span></span> 
> 
> <span data-ttu-id="93b96-166">Puede cambiar el margen de error y evaluar su impacto; para ello, haga clic en Modificar y, en el cuadro de diálogo Nivel de **evaluación,** cambie el margen de **error** objetivo para las estimaciones de recuperación y haga clic en Actualizar **valores.**</span><span class="sxs-lookup"><span data-stu-id="93b96-166">You can change the error margin and assess its impact, by clicking **Modify**, and in the **Assessment level dialog**, changing the **Target error margin for recall estimates**, and clicking **Update values**.</span></span> <span data-ttu-id="93b96-167">Además, en este cuadro de diálogo, puede ver las opciones avanzadas haciendo clic en **Avanzadas.**</span><span class="sxs-lookup"><span data-stu-id="93b96-167">Also, in this dialog, you can view advanced options, by clicking **Advanced**.</span></span> 
> 
> <span data-ttu-id="93b96-168">Puede ver estadísticas adicionales del nivel de evaluación y su impacto haciendo clic en **Ver**.</span><span class="sxs-lookup"><span data-stu-id="93b96-168">You can view additional assessment level statistics and their impact by clicking **View**.</span></span> <span data-ttu-id="93b96-169">En el cuadro de diálogo De detalles mostrado, las estadísticas están disponibles por problema, cuando hay al menos 500 archivos de evaluación etiquetados y al menos 18 archivos se etiquetan como relevantes para el problema.</span><span class="sxs-lookup"><span data-stu-id="93b96-169">In the displayed Detail results dialog, statistics are available per issue, when there are at least 500 tagged assessment files and at least 18 files are tagged as Relevant for the issue.</span></span> 
