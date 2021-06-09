---
title: Análisis de relevancia de prueba en Advanced eDiscovery
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
description: Obtenga información sobre cómo usar la pestaña Prueba después del cálculo por lotes Advanced eDiscovery probar, comparar y validar la calidad general del procesamiento.
ms.openlocfilehash: 3ac12c176f2e46ac0321976a7e0689fbd8893bba
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769175"
---
# <a name="test-relevance-analysis-in-advanced-ediscovery"></a><span data-ttu-id="c08b8-103">Análisis de relevancia de prueba en Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="c08b8-103">Test Relevance analysis in Advanced eDiscovery</span></span>
  
<span data-ttu-id="c08b8-104">La pestaña Prueba de Advanced eDiscovery permite probar, comparar y validar la calidad general del procesamiento.</span><span class="sxs-lookup"><span data-stu-id="c08b8-104">The Test tab in Advanced eDiscovery enables you to test, compare, and validate the overall quality of processing.</span></span> <span data-ttu-id="c08b8-105">Estas pruebas se realizan después del cálculo por lotes.</span><span class="sxs-lookup"><span data-stu-id="c08b8-105">These tests are performed after Batch calculation.</span></span> <span data-ttu-id="c08b8-106">Al etiquetar los archivos de la colección, un experto hace el juicio final sobre si cada archivo etiquetado es relevante para el caso.</span><span class="sxs-lookup"><span data-stu-id="c08b8-106">By tagging the files in the collection, an expert makes the final judgment about whether each tagged file is relevant to the case.</span></span>
  
<span data-ttu-id="c08b8-107">En escenarios únicos y de varios problemas, las pruebas suelen realizarse por problema.</span><span class="sxs-lookup"><span data-stu-id="c08b8-107">In single and multiple-issue scenarios, tests are typically performed per issue.</span></span> <span data-ttu-id="c08b8-108">Los resultados se pueden ver después de cada prueba y los resultados de la prueba se pueden volver a trabajar con archivos de prueba de ejemplo especificados.</span><span class="sxs-lookup"><span data-stu-id="c08b8-108">Results can be viewed after each test, and test results can be reworked with specified sample test files.</span></span>
  
## <a name="testing-the-rest"></a><span data-ttu-id="c08b8-109">Probar el resto</span><span class="sxs-lookup"><span data-stu-id="c08b8-109">Testing the rest</span></span>

<span data-ttu-id="c08b8-110">La prueba "Probar el resto" se usa para validar las decisiones de selección, por ejemplo, para revisar solo los archivos por encima de una puntuación de límite de relevancia específica en función de los resultados Advanced eDiscovery resultados finales.</span><span class="sxs-lookup"><span data-stu-id="c08b8-110">The "Test the Rest" test is used to validate culling decisions, for example, to review only files above a specific Relevance cutoff score based on the final Advanced eDiscovery results.</span></span> <span data-ttu-id="c08b8-111">El experto revisa una muestra de archivos bajo una puntuación de límite seleccionada para evaluar el número de archivos relevantes dentro de ese conjunto.</span><span class="sxs-lookup"><span data-stu-id="c08b8-111">The expert reviews a sample of files under a selected cutoff score to evaluate the number of relevant files within that set.</span></span>
  
<span data-ttu-id="c08b8-112">Esta prueba proporciona estadísticas y una comparación entre el conjunto de revisión y la población Probar el resto.</span><span class="sxs-lookup"><span data-stu-id="c08b8-112">This test provides statistics and a comparison between the Review set and the Test the Rest population.</span></span> <span data-ttu-id="c08b8-113">Los resultados del conjunto de revisión son los calculados por Relevancia durante el aprendizaje.</span><span class="sxs-lookup"><span data-stu-id="c08b8-113">The results of the review set are those calculated by Relevance during Training.</span></span> <span data-ttu-id="c08b8-114">Los resultados incluyen cálculos basados en la configuración y los parámetros de entrada, como:</span><span class="sxs-lookup"><span data-stu-id="c08b8-114">The results include calculations based on settings and input parameters, such as:</span></span>
  
- <span data-ttu-id="c08b8-115">Probar estadísticas de ejemplo del número de archivos de un ejemplo e identificar archivos relevantes.</span><span class="sxs-lookup"><span data-stu-id="c08b8-115">Test sample statistics of the number of files in a sample and identified relevant files.</span></span>

- <span data-ttu-id="c08b8-116">Comparación tabular de los parámetros Population del conjunto Review y Rest, por ejemplo, el número de archivos, el número estimado de archivos relevantes, la riqueza estimada y el costo promedio de encontrar otro archivo relevante.</span><span class="sxs-lookup"><span data-stu-id="c08b8-116">Tabular comparison of the Population parameters of the Review set and the Rest, for example, the number of files, estimated number of relevant files, estimated richness, and the average cost of finding another relevant file.</span></span> <span data-ttu-id="c08b8-117">La configuración del parámetro de costo la puede establecer el administrador.</span><span class="sxs-lookup"><span data-stu-id="c08b8-117">Cost parameter settings can be set by the administrator.</span></span>

<span data-ttu-id="c08b8-118">Para ejecutar la prueba "Probar el resto":</span><span class="sxs-lookup"><span data-stu-id="c08b8-118">To run the "Test the Rest" test:</span></span>

1. <span data-ttu-id="c08b8-119">Abra la **pestaña Prueba \> de relevancia.**</span><span class="sxs-lookup"><span data-stu-id="c08b8-119">Open the **Relevance \> Test** tab.</span></span>

2. <span data-ttu-id="c08b8-120">En la **pestaña Prueba,** haga clic **en Nueva prueba**.</span><span class="sxs-lookup"><span data-stu-id="c08b8-120">In the **Test** tab, click **New test**.</span></span> <span data-ttu-id="c08b8-121">Se **muestra el cuadro** de diálogo Crear prueba, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="c08b8-121">The **Create test** dialog is displayed, as shown in the following example.</span></span>

    ![Resultados de Probar el resto de relevancia](../media/46e6898a-f929-4fd0-88d9-6f91d04b6ce2.png)
  
3. <span data-ttu-id="c08b8-123">En **Nombre de prueba** y **Descripción,** escriba el nombre y la descripción.</span><span class="sxs-lookup"><span data-stu-id="c08b8-123">In **Test name**, and **Description**, type the name and description.</span></span>

4. <span data-ttu-id="c08b8-124">En la **lista Tipo de** prueba, seleccione Probar el **resto**</span><span class="sxs-lookup"><span data-stu-id="c08b8-124">In the **Test type** list, select **Test the Rest**</span></span>

5. <span data-ttu-id="c08b8-125">En la **lista Problema o categoría,** seleccione el nombre del problema.</span><span class="sxs-lookup"><span data-stu-id="c08b8-125">In the **Issue / Category** list, select the issue name.</span></span>

6. <span data-ttu-id="c08b8-126">En la **lista Cargar,** seleccione la carga.</span><span class="sxs-lookup"><span data-stu-id="c08b8-126">In the **Load** list, select the load.</span></span> 

7. <span data-ttu-id="c08b8-127">En **Read %**, acepte el valor predeterminado o seleccione un valor para la puntuación de relevancia de corte.</span><span class="sxs-lookup"><span data-stu-id="c08b8-127">In **Read %**, accept the default value or select a value for the cutoff Relevance score.</span></span> 

8. <span data-ttu-id="c08b8-128">En **Establecer tamaño** o aceptar el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="c08b8-128">In **Set size**, or accept the default value.</span></span> <span data-ttu-id="c08b8-129">Los iconos de restauración restaurarán los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="c08b8-129">The restore icons will restore the default values.</span></span>

9. <span data-ttu-id="c08b8-130">Haga **clic en Iniciar etiquetado**.</span><span class="sxs-lookup"><span data-stu-id="c08b8-130">Click **Start tagging**.</span></span> <span data-ttu-id="c08b8-131">Se genera un ejemplo de prueba.</span><span class="sxs-lookup"><span data-stu-id="c08b8-131">A test sample is generated.</span></span>

10. <span data-ttu-id="c08b8-132">Revise y etiquete cada uno de los archivos de la pestaña **Etiqueta \> de** relevancia y, cuando haya terminado, haga clic en **Calcular**.</span><span class="sxs-lookup"><span data-stu-id="c08b8-132">Review and tag each of the files in the **Relevance \> Tag** tab and when done, click **Calculate**.</span></span>

11. <span data-ttu-id="c08b8-133">En la pestaña Prueba, puede hacer clic en **Ver resultados** para ver los resultados de la prueba.</span><span class="sxs-lookup"><span data-stu-id="c08b8-133">In the Test tab, you can click **View results** to see the test results.</span></span> <span data-ttu-id="c08b8-134">En la siguiente captura de pantalla se muestra un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="c08b8-134">An example is shown in the following screenshot.</span></span>

    ![Resultados de Probar el resto](../media/b95744a9-047d-4c29-992d-04fa7e58e58a.png)
  
<span data-ttu-id="c08b8-136">En la captura  de pantalla anterior, la sección Parámetros de ejemplo de la tabla contiene detalles sobre el número de archivos de la muestra etiquetados por el experto y el número de archivos relevantes que se encuentran en esa muestra.</span><span class="sxs-lookup"><span data-stu-id="c08b8-136">In the previous screenshot, the **Sample parameters** section of the table contains details about the number of files in the sample tagged by the expert, and the number of relevant files found in that sample.</span></span>
  
<span data-ttu-id="c08b8-137">La sección **Parámetros** de población de la tabla contiene los resultados de la prueba, incluido el conjunto de revisión de la población de archivos con una puntuación por debajo del límite seleccionado y la población de archivos "El resto" con una puntuación por encima del límite seleccionado.</span><span class="sxs-lookup"><span data-stu-id="c08b8-137">The **Population parameters** section of the table contains the test results, including the Review set population of files with a score below the selected cutoff and "The Rest" population of files with a score above the selected cutoff.</span></span> <span data-ttu-id="c08b8-138">Para cada población, se muestran los siguientes resultados:</span><span class="sxs-lookup"><span data-stu-id="c08b8-138">For each population, the following results are displayed:</span></span>
  
- <span data-ttu-id="c08b8-139">Incluye archivos con % de lectura: límite declarado</span><span class="sxs-lookup"><span data-stu-id="c08b8-139">Includes files with read % - Stated cutoff</span></span>

- <span data-ttu-id="c08b8-140">El número total de archivos</span><span class="sxs-lookup"><span data-stu-id="c08b8-140">The total number of files</span></span>

- <span data-ttu-id="c08b8-141">Número estimado de archivos relevantes</span><span class="sxs-lookup"><span data-stu-id="c08b8-141">The estimated number of relevant files</span></span>

- <span data-ttu-id="c08b8-142">La riqueza estimada</span><span class="sxs-lookup"><span data-stu-id="c08b8-142">The estimated richness</span></span>

- <span data-ttu-id="c08b8-143">Costo medio de revisión de buscar otro archivo relevante</span><span class="sxs-lookup"><span data-stu-id="c08b8-143">The average review cost of finding another relevant file</span></span>

## <a name="testing-the-slice"></a><span data-ttu-id="c08b8-144">Probar el segmento</span><span class="sxs-lookup"><span data-stu-id="c08b8-144">Testing the slice</span></span>

<span data-ttu-id="c08b8-145">La prueba "Probar el segmento" realiza pruebas similares a la prueba "Probar el resto", pero a un segmento del conjunto de archivos especificado por Relevancia Lectura %.</span><span class="sxs-lookup"><span data-stu-id="c08b8-145">The "Test the Slice" test performs testing similar to the "Test the Rest" test, but to a segment of the file set as specified by Relevance Read %.</span></span>

<span data-ttu-id="c08b8-146">Para ejecutar la prueba "Probar el segmento":</span><span class="sxs-lookup"><span data-stu-id="c08b8-146">To run the "Test the Slice" test:</span></span>
  
1. <span data-ttu-id="c08b8-147">Abra la **pestaña Prueba \> de relevancia.**</span><span class="sxs-lookup"><span data-stu-id="c08b8-147">Open the **Relevance \> Test** tab.</span></span>

2. <span data-ttu-id="c08b8-148">En la **pestaña Prueba,** haga clic **en Nueva prueba**.</span><span class="sxs-lookup"><span data-stu-id="c08b8-148">In the **Test** tab, click **New test**.</span></span> <span data-ttu-id="c08b8-149">Se **muestra el cuadro de** diálogo Crear prueba.</span><span class="sxs-lookup"><span data-stu-id="c08b8-149">The **Create test** dialog is displayed.</span></span>

3. <span data-ttu-id="c08b8-150">En **Nombre de prueba** y **Descripción,** escriba la información.</span><span class="sxs-lookup"><span data-stu-id="c08b8-150">In **Test name** and **Description**, type the information.</span></span>

4. <span data-ttu-id="c08b8-151">En la **lista Tipo de** prueba, seleccione Probar el **segmento**.</span><span class="sxs-lookup"><span data-stu-id="c08b8-151">In the **Test type** list, select **Test the Slice**.</span></span>

5. <span data-ttu-id="c08b8-152">En la **lista Problema,** seleccione el nombre del problema.</span><span class="sxs-lookup"><span data-stu-id="c08b8-152">In the **Issue** list, select the issue name.</span></span>

6. <span data-ttu-id="c08b8-153">En la **lista Cargar,** seleccione la carga.</span><span class="sxs-lookup"><span data-stu-id="c08b8-153">In the **Load** list, select the load.</span></span>

7. <span data-ttu-id="c08b8-154">En **Leer % entre**, acepte los valores predeterminados de rango bajo y alto o seleccione valores para las puntuaciones de relevancia de corte.</span><span class="sxs-lookup"><span data-stu-id="c08b8-154">In **Read % between**, accept the default low and high range values or select values for the cutoff Relevance scores.</span></span>

8. <span data-ttu-id="c08b8-155">En **Establecer tamaño,** seleccione un valor o acepte el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="c08b8-155">In **Set size**, select a value or accept the default value.</span></span>

    <span data-ttu-id="c08b8-156">Los iconos de restauración restaurarán el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="c08b8-156">The restore icons will restore the default value.</span></span>

9. <span data-ttu-id="c08b8-157">Haga **clic en Iniciar etiquetado**.</span><span class="sxs-lookup"><span data-stu-id="c08b8-157">Click **Start tagging**.</span></span> <span data-ttu-id="c08b8-158">Se genera un ejemplo de prueba.</span><span class="sxs-lookup"><span data-stu-id="c08b8-158">A test sample is generated.</span></span>

10. <span data-ttu-id="c08b8-159">Revise y etiquete cada uno de los archivos de la pestaña **Etiqueta \> de** relevancia y, cuando haya terminado, haga clic en **Calcular**.</span><span class="sxs-lookup"><span data-stu-id="c08b8-159">Review and tag each of the files in the **Relevance \> Tag** tab and when done, click **Calculate**.</span></span>

11. <span data-ttu-id="c08b8-160">En la pestaña Prueba, puede hacer clic en **Ver resultados** para ver los resultados de la prueba.</span><span class="sxs-lookup"><span data-stu-id="c08b8-160">In the Test tab, you can click **View results** to see the test results.</span></span>
