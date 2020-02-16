---
title: Análisis de relevancia de pruebas en Office 365 Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
ms.date: 09/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 1b092f7c-ea55-44f5-b419-63f3458fd7e0
description: 'Obtenga información sobre cómo usar la pestaña prueba tras el cálculo por lotes en Office 365 Advanced eDiscovery para probar, comparar y validar la calidad general de procesamiento.  '
ms.openlocfilehash: e07d02a0eff1e07cacbce5debd27d4057fe40db2
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42080947"
---
# <a name="test-relevance-analysis-in-office-365-advanced-ediscovery"></a><span data-ttu-id="5cd0d-103">Análisis de relevancia de pruebas en Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="5cd0d-103">Test Relevance analysis in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="5cd0d-p101">Para usar eDiscovery avanzado, su organización necesita una suscripción de Office 365 E3 con el complemento Cumplimiento avanzado, o bien una suscripción de E5. Si no tiene ese plan y quiere probar eDiscovery avanzado, puede [registrarse para una prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="5cd0d-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="5cd0d-106">La pestaña prueba de eDiscovery avanzado permite probar, comparar y validar la calidad general de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="5cd0d-106">The Test tab in Advanced eDiscovery enables you to test, compare, and validate the overall quality of processing.</span></span> <span data-ttu-id="5cd0d-107">Estas pruebas se realizan después del cálculo por lotes.</span><span class="sxs-lookup"><span data-stu-id="5cd0d-107">These tests are performed after Batch calculation.</span></span> <span data-ttu-id="5cd0d-108">Al etiquetar los archivos de la colección, un experto realiza la última decisión sobre si cada archivo etiquetado es realmente relevante para el caso.</span><span class="sxs-lookup"><span data-stu-id="5cd0d-108">By tagging the files in the collection, an expert makes the final judgment about whether each tagged file is actually relevant to the case.</span></span> 
  
<span data-ttu-id="5cd0d-109">En escenarios únicos o de varios problemas, las pruebas se realizan normalmente por problema.</span><span class="sxs-lookup"><span data-stu-id="5cd0d-109">In single and multiple-issue scenarios, tests are typically performed per issue.</span></span> <span data-ttu-id="5cd0d-110">Los resultados se pueden ver después de cada prueba y los resultados de la prueba se pueden volver a usar con los archivos de prueba de ejemplo especificados.</span><span class="sxs-lookup"><span data-stu-id="5cd0d-110">Results can be viewed after each test, and test results can be reworked with specified sample test files.</span></span>
  
## <a name="testing-the-rest"></a><span data-ttu-id="5cd0d-111">Probar el resto</span><span class="sxs-lookup"><span data-stu-id="5cd0d-111">Testing the rest</span></span>

<span data-ttu-id="5cd0d-112">La prueba "probar el resto" se usa para validar las decisiones de selección, por ejemplo, para revisar solo los archivos por encima de una puntuación de límite de relevancia específica basada en los resultados avanzados de eDiscovery avanzado.</span><span class="sxs-lookup"><span data-stu-id="5cd0d-112">The "Test the Rest" test is used to validate culling decisions, for example, to review only files above a specific Relevance cutoff score based on the final Advanced eDiscovery results.</span></span> <span data-ttu-id="5cd0d-113">El experto revisa un ejemplo de archivos con una puntuación de límite seleccionada para evaluar el número de archivos relevantes dentro de ese conjunto.</span><span class="sxs-lookup"><span data-stu-id="5cd0d-113">The expert reviews a sample of files under a selected cutoff score to evaluate the number of relevant files within that set.</span></span>
  
<span data-ttu-id="5cd0d-114">Esta prueba proporciona estadísticas y una comparación entre el conjunto de revisión y la prueba de la población de REST.</span><span class="sxs-lookup"><span data-stu-id="5cd0d-114">This test provides statistics and a comparison between the Review set and the Test the Rest population.</span></span> <span data-ttu-id="5cd0d-115">Los resultados del conjunto de revisión son los que se calculan por relevancia durante la formación.</span><span class="sxs-lookup"><span data-stu-id="5cd0d-115">The results of the review set are those calculated by Relevance during Training.</span></span> <span data-ttu-id="5cd0d-116">Los resultados incluyen cálculos, basados en la configuración y los parámetros de entrada, como:</span><span class="sxs-lookup"><span data-stu-id="5cd0d-116">The results include calculations , based on settings and input parameters, such as:</span></span>
  
- <span data-ttu-id="5cd0d-117">Probar estadísticas de muestra del número de archivos de una muestra e identificado archivos relevantes.</span><span class="sxs-lookup"><span data-stu-id="5cd0d-117">Test sample statistics of the number of files in a sample and identified relevant files.</span></span> 
    
- <span data-ttu-id="5cd0d-118">Comparación tabular de los parámetros de población del conjunto de revisión y el resto, por ejemplo, el número de archivos, el número estimado de archivos relevantes, la riqueza estimada y el costo medio de buscar un archivo relevante adicional.</span><span class="sxs-lookup"><span data-stu-id="5cd0d-118">Tabular comparison of the Population parameters of the Review set and the Rest, for example, the number of files, estimated number of relevant files, estimated richness, and the average cost of finding an additional relevant file.</span></span> <span data-ttu-id="5cd0d-119">El administrador puede establecer la configuración del parámetro cost.</span><span class="sxs-lookup"><span data-stu-id="5cd0d-119">Cost parameter settings can be set by the administrator.</span></span>
    
1. <span data-ttu-id="5cd0d-120">Abra la **pestaña \> prueba de relevancia** .</span><span class="sxs-lookup"><span data-stu-id="5cd0d-120">Open the **Relevance \> Test** tab.</span></span> 
    
2. <span data-ttu-id="5cd0d-121">En la pestaña **prueba** , haga clic en **nueva prueba**.</span><span class="sxs-lookup"><span data-stu-id="5cd0d-121">In the **Test** tab, click **New test**.</span></span> <span data-ttu-id="5cd0d-122">Se muestra el cuadro de diálogo **crear prueba** , tal como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="5cd0d-122">The **Create test** dialog is displayed, as shown in the following example.</span></span> 
    
    ![Resultados de Probar el resto de relevancia](../media/46e6898a-f929-4fd0-88d9-6f91d04b6ce2.png)
  
3. <span data-ttu-id="5cd0d-124">En **nombre**de la prueba y **Descripción**, escriba el nombre y la descripción.</span><span class="sxs-lookup"><span data-stu-id="5cd0d-124">In **Test name**, and **Description**, type the name and description.</span></span>
    
4. <span data-ttu-id="5cd0d-125">En la lista **tipo de prueba** , seleccione **probar el resto**</span><span class="sxs-lookup"><span data-stu-id="5cd0d-125">In the **Test type** list, select **Test the Rest**</span></span>
    
5. <span data-ttu-id="5cd0d-126">En la lista **emisión/categoría** , seleccione el nombre del problema.</span><span class="sxs-lookup"><span data-stu-id="5cd0d-126">In the **Issue / Category** list, select the issue name.</span></span> 
    
6. <span data-ttu-id="5cd0d-127">En la lista **cargar** , seleccione la carga.</span><span class="sxs-lookup"><span data-stu-id="5cd0d-127">In the **Load** list, select the load.</span></span> 
    
7. <span data-ttu-id="5cd0d-128">En el **% lectura**, acepte el valor predeterminado o seleccione un valor para la puntuación de relevancia de corte.</span><span class="sxs-lookup"><span data-stu-id="5cd0d-128">In **Read %**, accept the default value or select a value for the cutoff Relevance score.</span></span> 
    
8. <span data-ttu-id="5cd0d-129">En **establecer tamaño**o aceptar el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="5cd0d-129">In **Set size**, or accept the default value.</span></span> <span data-ttu-id="5cd0d-130">Tenga en cuenta que los iconos de restauración restaurarán los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="5cd0d-130">Note that the restore icons will restore the default values.</span></span>
    
9. <span data-ttu-id="5cd0d-131">Haga clic en **iniciar etiquetado**.</span><span class="sxs-lookup"><span data-stu-id="5cd0d-131">Click **Start tagging**.</span></span> <span data-ttu-id="5cd0d-132">Se genera una muestra de prueba.</span><span class="sxs-lookup"><span data-stu-id="5cd0d-132">A test sample is generated.</span></span>
    
10. <span data-ttu-id="5cd0d-133">Revise y etiquete cada uno de los archivos en la pestaña \*\*etiqueta de relevancia \> \*\* y, cuando haya terminado, haga clic en **calcular**.</span><span class="sxs-lookup"><span data-stu-id="5cd0d-133">Review and tag each of the files in the **Relevance \> Tag** tab and when done, click **Calculate**.</span></span>
    
11. <span data-ttu-id="5cd0d-134">En la pestaña prueba, puede hacer clic en **ver resultados** para ver los resultados de la prueba.</span><span class="sxs-lookup"><span data-stu-id="5cd0d-134">In the Test tab, you can click **View results** to see the test results.</span></span> <span data-ttu-id="5cd0d-135">En la siguiente figura se muestra un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="5cd0d-135">An example is shown in the following figure.</span></span> 
    
    ![Resultados de Probar el resto](../media/b95744a9-047d-4c29-992d-04fa7e58e58a.png)
  
<span data-ttu-id="5cd0d-137">En la figura anterior, la sección **parámetros de ejemplo** de la tabla contiene detalles sobre el número de archivos del ejemplo etiquetado por el experto y el número de archivos relevantes que se encuentran en ese ejemplo.</span><span class="sxs-lookup"><span data-stu-id="5cd0d-137">In the figure above, the **Sample parameters** section of the table contains details about the number of files in the sample tagged by the expert, and the number of relevant files found in that sample.</span></span> 
  
<span data-ttu-id="5cd0d-138">La sección **parámetros de rellenado** de la tabla contiene los resultados de la prueba, incluido el rellenado de la revisión del conjunto de archivos con una puntuación inferior al límite seleccionado y el rellenado "el resto" de los archivos con una puntuación superior al límite seleccionado.</span><span class="sxs-lookup"><span data-stu-id="5cd0d-138">The **Population parameters** section of the table contains the test results, including the Review set population of files with a score below the selected cutoff and "The Rest" population of files with a score above the selected cutoff.</span></span> <span data-ttu-id="5cd0d-139">Para cada población, se muestran los siguientes resultados:</span><span class="sxs-lookup"><span data-stu-id="5cd0d-139">For each population, the following results are displayed:</span></span> 
  
- <span data-ttu-id="5cd0d-140">Incluye archivos con el%-límite de lectura declarados</span><span class="sxs-lookup"><span data-stu-id="5cd0d-140">Includes files with read % - Stated cutoff</span></span>
    
- <span data-ttu-id="5cd0d-141">El número total de archivos</span><span class="sxs-lookup"><span data-stu-id="5cd0d-141">The total number of files</span></span> 
    
- <span data-ttu-id="5cd0d-142">El número estimado de archivos relevantes</span><span class="sxs-lookup"><span data-stu-id="5cd0d-142">The estimated number of relevant files</span></span> 
    
- <span data-ttu-id="5cd0d-143">La riqueza estimada</span><span class="sxs-lookup"><span data-stu-id="5cd0d-143">The estimated richness</span></span> 
    
- <span data-ttu-id="5cd0d-144">El costo medio de revisión de buscar otro archivo relevante</span><span class="sxs-lookup"><span data-stu-id="5cd0d-144">The average review cost of finding another relevant file</span></span>
    
## <a name="testing-the-slice"></a><span data-ttu-id="5cd0d-145">Prueba del segmento</span><span class="sxs-lookup"><span data-stu-id="5cd0d-145">Testing the slice</span></span>

<span data-ttu-id="5cd0d-146">La prueba "probar el sector" realiza una prueba similar a la prueba "probar el resto", pero con un segmento del conjunto de archivos tal y como se especifica por% de lectura de relevancia.</span><span class="sxs-lookup"><span data-stu-id="5cd0d-146">The "Test the Slice" test performs testing similar to the "Test the Rest" test, but to a segment of the file set as specified by Relevance Read %.</span></span>
  
1. <span data-ttu-id="5cd0d-147">Abra la **pestaña \> prueba de relevancia** .</span><span class="sxs-lookup"><span data-stu-id="5cd0d-147">Open the **Relevance \> Test** tab.</span></span> 
    
2. <span data-ttu-id="5cd0d-148">En la pestaña **prueba** , haga clic en **nueva prueba**.</span><span class="sxs-lookup"><span data-stu-id="5cd0d-148">In the **Test** tab, click **New test**.</span></span> <span data-ttu-id="5cd0d-149">Se muestra el cuadro de diálogo **crear prueba** .</span><span class="sxs-lookup"><span data-stu-id="5cd0d-149">The **Create test** dialog is displayed.</span></span> 
    
3. <span data-ttu-id="5cd0d-150">En **nombre** de la prueba y **Descripción**, escriba la información.</span><span class="sxs-lookup"><span data-stu-id="5cd0d-150">In **Test name** and **Description**, type the information.</span></span>
    
4. <span data-ttu-id="5cd0d-151">En la lista **tipo de prueba** , seleccione **probar el sector**.</span><span class="sxs-lookup"><span data-stu-id="5cd0d-151">In the **Test type** list, select **Test the Slice**.</span></span>
    
5. <span data-ttu-id="5cd0d-152">En la lista de **problemas** , seleccione el nombre del problema.</span><span class="sxs-lookup"><span data-stu-id="5cd0d-152">In the **Issue** list, select the issue name.</span></span> 
    
6. <span data-ttu-id="5cd0d-153">En la lista **cargar** , seleccione la carga.</span><span class="sxs-lookup"><span data-stu-id="5cd0d-153">In the **Load** list, select the load.</span></span> 
    
7. <span data-ttu-id="5cd0d-154">En **leer% entre**, acepte los valores predeterminados de rango bajo y alto o seleccione valores para los resultados de relevancia de corte.</span><span class="sxs-lookup"><span data-stu-id="5cd0d-154">In **Read % between**, accept the default low and high range values or select values for the cutoff Relevance scores.</span></span> 
    
8. <span data-ttu-id="5cd0d-155">En **establecer tamaño**, seleccione un valor o acepte el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="5cd0d-155">In **Set size**, select a value or accept the default value.</span></span>
    
    <span data-ttu-id="5cd0d-156">Los iconos de restauración restaurarán el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="5cd0d-156">The restore icons will restore the default value.</span></span>
    
9. <span data-ttu-id="5cd0d-157">Haga clic en **iniciar etiquetado**.</span><span class="sxs-lookup"><span data-stu-id="5cd0d-157">Click **Start tagging**.</span></span> <span data-ttu-id="5cd0d-158">Se genera una muestra de prueba.</span><span class="sxs-lookup"><span data-stu-id="5cd0d-158">A test sample is generated.</span></span>
    
10. <span data-ttu-id="5cd0d-159">Revise y etiquete cada uno de los archivos en la pestaña \*\*etiqueta de relevancia \> \*\* y, cuando haya terminado, haga clic en **calcular**.</span><span class="sxs-lookup"><span data-stu-id="5cd0d-159">Review and tag each of the files in the **Relevance \> Tag** tab and when done, click **Calculate**.</span></span> 
    
11. <span data-ttu-id="5cd0d-160">En la pestaña prueba, puede hacer clic en **ver resultados** para ver los resultados de la prueba.</span><span class="sxs-lookup"><span data-stu-id="5cd0d-160">In the Test tab, you can click **View results** to see the test results.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="5cd0d-161">Vea también</span><span class="sxs-lookup"><span data-stu-id="5cd0d-161">See also</span></span>

[<span data-ttu-id="5cd0d-162">eDiscovery avanzado de Office 365</span><span class="sxs-lookup"><span data-stu-id="5cd0d-162">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="5cd0d-163">Descripción de la evaluación en relevancia</span><span class="sxs-lookup"><span data-stu-id="5cd0d-163">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="5cd0d-164">Etiquetado y evaluación</span><span class="sxs-lookup"><span data-stu-id="5cd0d-164">Tagging and Assessment</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="5cd0d-165">Aprendizaje de etiquetas y relevancia</span><span class="sxs-lookup"><span data-stu-id="5cd0d-165">Tagging and Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="5cd0d-166">Seguimiento del análisis de relevancia</span><span class="sxs-lookup"><span data-stu-id="5cd0d-166">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="5cd0d-167">Decisiones basadas en los resultados</span><span class="sxs-lookup"><span data-stu-id="5cd0d-167">Deciding based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)

