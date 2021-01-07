---
title: Probar el análisis de relevancia en eDiscovery avanzado
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
ms.assetid: 1b092f7c-ea55-44f5-b419-63f3458fd7e0
ROBOTS: NOINDEX, NOFOLLOW
description: Obtenga información sobre cómo usar la pestaña prueba tras el cálculo del lote en la exhibición avanzada de documentos electrónicos para probar, comparar y validar la calidad general de procesamiento.
ms.openlocfilehash: 3ac12c176f2e46ac0321976a7e0689fbd8893bba
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769175"
---
# <a name="test-relevance-analysis-in-advanced-ediscovery"></a><span data-ttu-id="0dfc7-103">Probar el análisis de relevancia en eDiscovery avanzado</span><span class="sxs-lookup"><span data-stu-id="0dfc7-103">Test Relevance analysis in Advanced eDiscovery</span></span>
  
<span data-ttu-id="0dfc7-104">La pestaña prueba de eDiscovery avanzado permite probar, comparar y validar la calidad general de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="0dfc7-104">The Test tab in Advanced eDiscovery enables you to test, compare, and validate the overall quality of processing.</span></span> <span data-ttu-id="0dfc7-105">Estas pruebas se realizan después del cálculo por lotes.</span><span class="sxs-lookup"><span data-stu-id="0dfc7-105">These tests are performed after Batch calculation.</span></span> <span data-ttu-id="0dfc7-106">Al etiquetar los archivos de la colección, un experto realiza la última decisión sobre si cada archivo etiquetado es relevante para el caso.</span><span class="sxs-lookup"><span data-stu-id="0dfc7-106">By tagging the files in the collection, an expert makes the final judgment about whether each tagged file is relevant to the case.</span></span>
  
<span data-ttu-id="0dfc7-107">En escenarios únicos o de varios problemas, las pruebas se realizan normalmente por problema.</span><span class="sxs-lookup"><span data-stu-id="0dfc7-107">In single and multiple-issue scenarios, tests are typically performed per issue.</span></span> <span data-ttu-id="0dfc7-108">Los resultados se pueden ver después de cada prueba y los resultados de la prueba se pueden volver a usar con los archivos de prueba de ejemplo especificados.</span><span class="sxs-lookup"><span data-stu-id="0dfc7-108">Results can be viewed after each test, and test results can be reworked with specified sample test files.</span></span>
  
## <a name="testing-the-rest"></a><span data-ttu-id="0dfc7-109">Probar el resto</span><span class="sxs-lookup"><span data-stu-id="0dfc7-109">Testing the rest</span></span>

<span data-ttu-id="0dfc7-110">La prueba "probar el resto" se usa para validar las decisiones de selección, por ejemplo, para revisar solo los archivos por encima de una puntuación de límite de relevancia específica basada en los resultados avanzados de eDiscovery avanzado.</span><span class="sxs-lookup"><span data-stu-id="0dfc7-110">The "Test the Rest" test is used to validate culling decisions, for example, to review only files above a specific Relevance cutoff score based on the final Advanced eDiscovery results.</span></span> <span data-ttu-id="0dfc7-111">El experto revisa un ejemplo de archivos con una puntuación de límite seleccionada para evaluar el número de archivos relevantes dentro de ese conjunto.</span><span class="sxs-lookup"><span data-stu-id="0dfc7-111">The expert reviews a sample of files under a selected cutoff score to evaluate the number of relevant files within that set.</span></span>
  
<span data-ttu-id="0dfc7-112">Esta prueba proporciona estadísticas y una comparación entre el conjunto de revisión y la prueba de la población de REST.</span><span class="sxs-lookup"><span data-stu-id="0dfc7-112">This test provides statistics and a comparison between the Review set and the Test the Rest population.</span></span> <span data-ttu-id="0dfc7-113">Los resultados del conjunto de revisión son los que se calculan por relevancia durante la formación.</span><span class="sxs-lookup"><span data-stu-id="0dfc7-113">The results of the review set are those calculated by Relevance during Training.</span></span> <span data-ttu-id="0dfc7-114">Los resultados incluyen cálculos basados en la configuración y los parámetros de entrada, como:</span><span class="sxs-lookup"><span data-stu-id="0dfc7-114">The results include calculations based on settings and input parameters, such as:</span></span>
  
- <span data-ttu-id="0dfc7-115">Probar estadísticas de muestra del número de archivos de una muestra e identificado archivos relevantes.</span><span class="sxs-lookup"><span data-stu-id="0dfc7-115">Test sample statistics of the number of files in a sample and identified relevant files.</span></span>

- <span data-ttu-id="0dfc7-116">Comparación tabular de los parámetros de población del conjunto de revisión y el resto, por ejemplo, el número de archivos, el número estimado de archivos relevantes, la riqueza estimada y el costo medio de buscar otro archivo relevante.</span><span class="sxs-lookup"><span data-stu-id="0dfc7-116">Tabular comparison of the Population parameters of the Review set and the Rest, for example, the number of files, estimated number of relevant files, estimated richness, and the average cost of finding another relevant file.</span></span> <span data-ttu-id="0dfc7-117">El administrador puede establecer la configuración del parámetro cost.</span><span class="sxs-lookup"><span data-stu-id="0dfc7-117">Cost parameter settings can be set by the administrator.</span></span>

<span data-ttu-id="0dfc7-118">Para ejecutar la prueba "probar el resto":</span><span class="sxs-lookup"><span data-stu-id="0dfc7-118">To run the "Test the Rest" test:</span></span>

1. <span data-ttu-id="0dfc7-119">Abra la **pestaña \> prueba de relevancia** .</span><span class="sxs-lookup"><span data-stu-id="0dfc7-119">Open the **Relevance \> Test** tab.</span></span>

2. <span data-ttu-id="0dfc7-120">En la pestaña **prueba** , haga clic en **nueva prueba**.</span><span class="sxs-lookup"><span data-stu-id="0dfc7-120">In the **Test** tab, click **New test**.</span></span> <span data-ttu-id="0dfc7-121">Se muestra el cuadro de diálogo **crear prueba** , tal como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="0dfc7-121">The **Create test** dialog is displayed, as shown in the following example.</span></span>

    ![Resultados de Probar el resto de relevancia](../media/46e6898a-f929-4fd0-88d9-6f91d04b6ce2.png)
  
3. <span data-ttu-id="0dfc7-123">En **nombre** de la prueba y **Descripción**, escriba el nombre y la descripción.</span><span class="sxs-lookup"><span data-stu-id="0dfc7-123">In **Test name**, and **Description**, type the name and description.</span></span>

4. <span data-ttu-id="0dfc7-124">En la lista **tipo de prueba** , seleccione **probar el resto**</span><span class="sxs-lookup"><span data-stu-id="0dfc7-124">In the **Test type** list, select **Test the Rest**</span></span>

5. <span data-ttu-id="0dfc7-125">En la lista **emisión/categoría** , seleccione el nombre del problema.</span><span class="sxs-lookup"><span data-stu-id="0dfc7-125">In the **Issue / Category** list, select the issue name.</span></span>

6. <span data-ttu-id="0dfc7-126">En la lista **cargar** , seleccione la carga.</span><span class="sxs-lookup"><span data-stu-id="0dfc7-126">In the **Load** list, select the load.</span></span> 

7. <span data-ttu-id="0dfc7-127">En el **% lectura**, acepte el valor predeterminado o seleccione un valor para la puntuación de relevancia de corte.</span><span class="sxs-lookup"><span data-stu-id="0dfc7-127">In **Read %**, accept the default value or select a value for the cutoff Relevance score.</span></span> 

8. <span data-ttu-id="0dfc7-128">En **establecer tamaño** o aceptar el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="0dfc7-128">In **Set size**, or accept the default value.</span></span> <span data-ttu-id="0dfc7-129">Los iconos de restauración restaurarán los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="0dfc7-129">The restore icons will restore the default values.</span></span>

9. <span data-ttu-id="0dfc7-130">Haga clic en **iniciar etiquetado**.</span><span class="sxs-lookup"><span data-stu-id="0dfc7-130">Click **Start tagging**.</span></span> <span data-ttu-id="0dfc7-131">Se genera una muestra de prueba.</span><span class="sxs-lookup"><span data-stu-id="0dfc7-131">A test sample is generated.</span></span>

10. <span data-ttu-id="0dfc7-132">Revise y etiquete cada uno de los archivos en la pestaña **\> etiqueta de relevancia** y, cuando haya terminado, haga clic en **calcular**.</span><span class="sxs-lookup"><span data-stu-id="0dfc7-132">Review and tag each of the files in the **Relevance \> Tag** tab and when done, click **Calculate**.</span></span>

11. <span data-ttu-id="0dfc7-133">En la pestaña prueba, puede hacer clic en **ver resultados** para ver los resultados de la prueba.</span><span class="sxs-lookup"><span data-stu-id="0dfc7-133">In the Test tab, you can click **View results** to see the test results.</span></span> <span data-ttu-id="0dfc7-134">En la siguiente captura de pantalla se muestra un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="0dfc7-134">An example is shown in the following screenshot.</span></span>

    ![Resultados de Probar el resto](../media/b95744a9-047d-4c29-992d-04fa7e58e58a.png)
  
<span data-ttu-id="0dfc7-136">En la captura de pantalla anterior, la sección **parámetros de ejemplo** de la tabla contiene detalles sobre el número de archivos en el ejemplo etiquetado por el experto y el número de archivos relevantes que se encuentran en ese ejemplo.</span><span class="sxs-lookup"><span data-stu-id="0dfc7-136">In the previous screenshot, the **Sample parameters** section of the table contains details about the number of files in the sample tagged by the expert, and the number of relevant files found in that sample.</span></span>
  
<span data-ttu-id="0dfc7-137">La sección **parámetros de rellenado** de la tabla contiene los resultados de la prueba, incluido el rellenado de la revisión del conjunto de archivos con una puntuación inferior al límite seleccionado y el rellenado "el resto" de los archivos con una puntuación superior al límite seleccionado.</span><span class="sxs-lookup"><span data-stu-id="0dfc7-137">The **Population parameters** section of the table contains the test results, including the Review set population of files with a score below the selected cutoff and "The Rest" population of files with a score above the selected cutoff.</span></span> <span data-ttu-id="0dfc7-138">Para cada población, se muestran los siguientes resultados:</span><span class="sxs-lookup"><span data-stu-id="0dfc7-138">For each population, the following results are displayed:</span></span>
  
- <span data-ttu-id="0dfc7-139">Incluye archivos con el%-límite de lectura declarados</span><span class="sxs-lookup"><span data-stu-id="0dfc7-139">Includes files with read % - Stated cutoff</span></span>

- <span data-ttu-id="0dfc7-140">El número total de archivos</span><span class="sxs-lookup"><span data-stu-id="0dfc7-140">The total number of files</span></span>

- <span data-ttu-id="0dfc7-141">El número estimado de archivos relevantes</span><span class="sxs-lookup"><span data-stu-id="0dfc7-141">The estimated number of relevant files</span></span>

- <span data-ttu-id="0dfc7-142">La riqueza estimada</span><span class="sxs-lookup"><span data-stu-id="0dfc7-142">The estimated richness</span></span>

- <span data-ttu-id="0dfc7-143">El costo medio de revisión de buscar otro archivo relevante</span><span class="sxs-lookup"><span data-stu-id="0dfc7-143">The average review cost of finding another relevant file</span></span>

## <a name="testing-the-slice"></a><span data-ttu-id="0dfc7-144">Prueba del segmento</span><span class="sxs-lookup"><span data-stu-id="0dfc7-144">Testing the slice</span></span>

<span data-ttu-id="0dfc7-145">La prueba "probar el sector" realiza una prueba similar a la prueba "probar el resto", pero con un segmento del conjunto de archivos tal y como se especifica por% de lectura de relevancia.</span><span class="sxs-lookup"><span data-stu-id="0dfc7-145">The "Test the Slice" test performs testing similar to the "Test the Rest" test, but to a segment of the file set as specified by Relevance Read %.</span></span>

<span data-ttu-id="0dfc7-146">Para ejecutar la prueba "probar el sector":</span><span class="sxs-lookup"><span data-stu-id="0dfc7-146">To run the "Test the Slice" test:</span></span>
  
1. <span data-ttu-id="0dfc7-147">Abra la **pestaña \> prueba de relevancia** .</span><span class="sxs-lookup"><span data-stu-id="0dfc7-147">Open the **Relevance \> Test** tab.</span></span>

2. <span data-ttu-id="0dfc7-148">En la pestaña **prueba** , haga clic en **nueva prueba**.</span><span class="sxs-lookup"><span data-stu-id="0dfc7-148">In the **Test** tab, click **New test**.</span></span> <span data-ttu-id="0dfc7-149">Se muestra el cuadro de diálogo **crear prueba** .</span><span class="sxs-lookup"><span data-stu-id="0dfc7-149">The **Create test** dialog is displayed.</span></span>

3. <span data-ttu-id="0dfc7-150">En **nombre** de la prueba y **Descripción**, escriba la información.</span><span class="sxs-lookup"><span data-stu-id="0dfc7-150">In **Test name** and **Description**, type the information.</span></span>

4. <span data-ttu-id="0dfc7-151">En la lista **tipo de prueba** , seleccione **probar el sector**.</span><span class="sxs-lookup"><span data-stu-id="0dfc7-151">In the **Test type** list, select **Test the Slice**.</span></span>

5. <span data-ttu-id="0dfc7-152">En la lista de **problemas** , seleccione el nombre del problema.</span><span class="sxs-lookup"><span data-stu-id="0dfc7-152">In the **Issue** list, select the issue name.</span></span>

6. <span data-ttu-id="0dfc7-153">En la lista **cargar** , seleccione la carga.</span><span class="sxs-lookup"><span data-stu-id="0dfc7-153">In the **Load** list, select the load.</span></span>

7. <span data-ttu-id="0dfc7-154">En **leer% entre**, acepte los valores predeterminados de rango bajo y alto o seleccione valores para los resultados de relevancia de corte.</span><span class="sxs-lookup"><span data-stu-id="0dfc7-154">In **Read % between**, accept the default low and high range values or select values for the cutoff Relevance scores.</span></span>

8. <span data-ttu-id="0dfc7-155">En **establecer tamaño**, seleccione un valor o acepte el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="0dfc7-155">In **Set size**, select a value or accept the default value.</span></span>

    <span data-ttu-id="0dfc7-156">Los iconos de restauración restaurarán el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="0dfc7-156">The restore icons will restore the default value.</span></span>

9. <span data-ttu-id="0dfc7-157">Haga clic en **iniciar etiquetado**.</span><span class="sxs-lookup"><span data-stu-id="0dfc7-157">Click **Start tagging**.</span></span> <span data-ttu-id="0dfc7-158">Se genera una muestra de prueba.</span><span class="sxs-lookup"><span data-stu-id="0dfc7-158">A test sample is generated.</span></span>

10. <span data-ttu-id="0dfc7-159">Revise y etiquete cada uno de los archivos en la pestaña **\> etiqueta de relevancia** y, cuando haya terminado, haga clic en **calcular**.</span><span class="sxs-lookup"><span data-stu-id="0dfc7-159">Review and tag each of the files in the **Relevance \> Tag** tab and when done, click **Calculate**.</span></span>

11. <span data-ttu-id="0dfc7-160">En la pestaña prueba, puede hacer clic en **ver resultados** para ver los resultados de la prueba.</span><span class="sxs-lookup"><span data-stu-id="0dfc7-160">In the Test tab, you can click **View results** to see the test results.</span></span>
