---
title: Información general sobre la comprensión de documentos
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Obtenga información general sobre la comprensión des documentos en Microsoft SharePoint Syntex.
ms.openlocfilehash: 7e5818a929fa0f4554a7ee4ece460b4fe0d691aa
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2021
ms.locfileid: "52683828"
---
# <a name="document-understanding-overview"></a><span data-ttu-id="f0faa-103">Información general sobre la comprensión de documentos</span><span class="sxs-lookup"><span data-stu-id="f0faa-103">Document understanding overview</span></span>


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSu7] 

</br>

<span data-ttu-id="f0faa-104">La comprensión de documentos usa modelos de inteligencia artificial (IA) para automatizar la clasificación de archivos y extraer la información.</span><span class="sxs-lookup"><span data-stu-id="f0faa-104">Document understanding uses artificial intelligence (AI) models to automate classification of files and extraction of information.</span></span> <span data-ttu-id="f0faa-105">Funciona mejor con documentos sin estructura, como cartas o contratos.</span><span class="sxs-lookup"><span data-stu-id="f0faa-105">It works best with unstructured documents, such as letters or contracts.</span></span> <span data-ttu-id="f0faa-106">Estos documentos deben tener texto que pueda identificarse en función de frases o patrones.</span><span class="sxs-lookup"><span data-stu-id="f0faa-106">These documents must have text that can be identified based on phrases or patterns.</span></span> <span data-ttu-id="f0faa-107">El texto identificado designa tanto el tipo de archivo (su clasificación) como lo que le gustaría extraer (sus extractores).</span><span class="sxs-lookup"><span data-stu-id="f0faa-107">The identified text designates both the type of file it is (its classification) and what you'd like to extract (its extractors).</span></span>

> [!NOTE]
> <span data-ttu-id="f0faa-108">Consulte [Adopción de SharePoint Syntex: Guía de introducción](./adoption-getstarted.md) para obtener más información sobre ejemplos de escenarios de comprensión mediante documentos.</span><span class="sxs-lookup"><span data-stu-id="f0faa-108">See the [SharePoint Syntex adoption: Get started guide](./adoption-getstarted.md) for more information about document understanding scenario examples.</span></span>

<span data-ttu-id="f0faa-109">Los modelos de comprensión mediante documentos se crean y se administran en un tipo de sitio de SharePoint denominado *centro de contenido*.</span><span class="sxs-lookup"><span data-stu-id="f0faa-109">Document understanding models are created and managed in a type of SharePoint site called a *content center*.</span></span> <span data-ttu-id="f0faa-110">Cuando se aplica a una biblioteca de documentos de SharePoint, el modelo está asociado a un tipo de contenido que tiene columnas para almacenar la información que se va a extraer.</span><span class="sxs-lookup"><span data-stu-id="f0faa-110">When applied to a SharePoint document library, the model is associated with a content type has columns to store the information being extracted.</span></span> <span data-ttu-id="f0faa-111">El tipo de contenido que cree se almacena en la galería de tipo de contenido de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="f0faa-111">The content type you create is stored in the SharePoint content type gallery.</span></span> <span data-ttu-id="f0faa-112">También puede optar por usar tipos de contenido existentes para usar su esquema.</span><span class="sxs-lookup"><span data-stu-id="f0faa-112">You can also choose to use existing content types to use their schema.</span></span>

> [!NOTE]
> <span data-ttu-id="f0faa-113">Los tipos de contenido de solo lectura o sellado no pueden ser actualizados, de manera que no pueden ser usados en un modelo.</span><span class="sxs-lookup"><span data-stu-id="f0faa-113">Read-only or sealed content types cannot be updated, so they can't be used in a model.</span></span>

<span data-ttu-id="f0faa-114">Agregue *clasificadores* y *extractores* a los modelos de comprensión del documento para hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f0faa-114">Add *classifiers* and *extractors* to your document understanding models to do the following:</span></span> 

- <span data-ttu-id="f0faa-115">Los clasificadores se usan para identificar y clasificar documentos cargados en la biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="f0faa-115">Classifiers are used to identify and classify documents that are uploaded to the document library.</span></span> <span data-ttu-id="f0faa-116">Por ejemplo, un clasificador puede ser "entrenado" para identificar todos los documentos de *renovación de contrato* que se carguen en la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="f0faa-116">For example, a classifier can be "trained" to identify all *contract renewal* documents that are uploaded to the library.</span></span> <span data-ttu-id="f0faa-117">El tipo de contenido de renovación de contrato lo define el usuario al crear el clasificador.</span><span class="sxs-lookup"><span data-stu-id="f0faa-117">The contract renewal content type is defined by you when you create your classifier.</span></span>

- <span data-ttu-id="f0faa-118">Los extractores extraen información de estos documentos.</span><span class="sxs-lookup"><span data-stu-id="f0faa-118">Extractors pull information from these documents.</span></span> <span data-ttu-id="f0faa-119">Por ejemplo, para todos los documentos de renovación de contratos identificados en la biblioteca de documentos, las columnas se muestran en la vista que también muestra la *Fecha de inicio del servicio* y el *Cliente* por cada documento de renovación de contrato.</span><span class="sxs-lookup"><span data-stu-id="f0faa-119">For example, for all contract renewal documents identified in your document library, columns display in your view that also show the *Service Start Date* and  *Client* for each contract renewal document.</span></span> 

<span data-ttu-id="f0faa-120">Puede usar archivos de ejemplo para entrenarlos y probarlos en el modelo.</span><span class="sxs-lookup"><span data-stu-id="f0faa-120">You can use example files to train and test your classifiers and extractors in your model.</span></span> <span data-ttu-id="f0faa-121">Los archivos de ejemplo proporcionan ejemplos al modelo de lo que debe buscar al intentar identificar y extraer datos de archivos.</span><span class="sxs-lookup"><span data-stu-id="f0faa-121">Example files provide your model examples of what to look for when trying to identify and extract data from files.</span></span> <span data-ttu-id="f0faa-122">Por ejemplo, entrenaría los clasificadores y extracciones de renovación de contrato con ejemplos de documentos de renovación de contratos con los que trabaja su empresa.</span><span class="sxs-lookup"><span data-stu-id="f0faa-122">For example, you would train your contract renewal classifiers and extractors with examples of contract renewal documents your company works with.</span></span> <span data-ttu-id="f0faa-123">También puede usar archivos de ejemplo para probar la efectividad del modelo.</span><span class="sxs-lookup"><span data-stu-id="f0faa-123">You can also use example files to test the effectiveness of your model.</span></span>

<span data-ttu-id="f0faa-124">Después de publicar el modelo, utilice el centro de contenido para aplicarlo a cualquier biblioteca de documentos de SharePoint a la que tenga acceso.</span><span class="sxs-lookup"><span data-stu-id="f0faa-124">After publishing your model, use the content center to apply it to any SharePoint document library that you have access to.</span></span>  

## <a name="file-limitations"></a><span data-ttu-id="f0faa-125">Limitaciones de archivos</span><span class="sxs-lookup"><span data-stu-id="f0faa-125">File limitations</span></span>

<span data-ttu-id="f0faa-126">En los modelos de comprensión mediante documentos se usa la tecnología de reconocimiento óptico de caracteres (OCR) para digitalizar archivos PDF, imágenes y archivos TIFF, tanto al entrenar un modelo con archivos de ejemplo como al ejecutar el modelo en archivos de una biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="f0faa-126">Document understanding models use Optical Character Recognition (OCR) technology to scan PDFs, images, and TIFF files, both when you train a model with example files and when you run the model against files in a document library.</span></span>

<span data-ttu-id="f0faa-127">Tenga en cuenta las siguientes diferencias en relación con los archivos de texto basados en Microsoft Office y los archivos digitalizados con OCR (PDF, imagen o TIFF):</span><span class="sxs-lookup"><span data-stu-id="f0faa-127">Note the following differences with regard to Microsoft Office text-based files and OCR-scanned files (PDF, image, or TIFF):</span></span>

- <span data-ttu-id="f0faa-128">Archivos de Office: truncados a 64 000 caracteres (durante el entrenamiento y cuando se ejecuta en archivos de una biblioteca de documentos).</span><span class="sxs-lookup"><span data-stu-id="f0faa-128">Office files: Truncated at 64,000 characters (in training and when run against files in a document library).</span></span>

- <span data-ttu-id="f0faa-129">Archivos digitalizados con OCR: hay un límite de 20 páginas.</span><span class="sxs-lookup"><span data-stu-id="f0faa-129">OCR-scanned files: There's a 20-page limit.</span></span>  

### <a name="requirements"></a><span data-ttu-id="f0faa-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f0faa-130">Requirements</span></span>

<span data-ttu-id="f0faa-131">El procesamiento de OCR funciona mejor en documentos que cumplen los siguientes requisitos:</span><span class="sxs-lookup"><span data-stu-id="f0faa-131">OCR processing works best on documents that meet the following requirements:</span></span>

- <span data-ttu-id="f0faa-132">Formato JPG, PNG o PDF (texto o digitalizado).</span><span class="sxs-lookup"><span data-stu-id="f0faa-132">JPG, PNG, or PDF format (text or scanned).</span></span> <span data-ttu-id="f0faa-133">Los archivos PDF con texto incrustado son mejores, ya que no se producen errores en la extracción y la ubicación de caracteres.</span><span class="sxs-lookup"><span data-stu-id="f0faa-133">Text-embedded PDFs are better, because there won't be any errors in character extraction and location.</span></span>

- <span data-ttu-id="f0faa-134">Si sus archivos PDF están bloqueados con contraseña, debe quitar el bloqueo antes de enviarlos.</span><span class="sxs-lookup"><span data-stu-id="f0faa-134">If your PDFs are password-locked, you must remove the lock before submitting them.</span></span>

- <span data-ttu-id="f0faa-135">El tamaño de archivo combinado de los documentos usados para el aprendizaje no debe superar los 50 MB por colección y los documentos PDF no deben tener más de 500 páginas.</span><span class="sxs-lookup"><span data-stu-id="f0faa-135">The combined file size of the documents used for training per collection must not exceed 50 MB, and PDF documents shouldn't have more than 500 pages.</span></span>

- <span data-ttu-id="f0faa-136">Para las imágenes, las dimensiones deben estar entre 50 × 50 y 10 000 × 10 000 píxeles.</span><span class="sxs-lookup"><span data-stu-id="f0faa-136">For images, dimensions must be between 50 × 50 and 10,000 × 10,000 pixels.</span></span>
   > [!NOTE]
   > <span data-ttu-id="f0faa-137">Es posible que las imágenes muy anchas o con dimensiones inusuales (por ejemplo, planos de planta) se trunquen en el proceso de OCR y pierdan precisión.</span><span class="sxs-lookup"><span data-stu-id="f0faa-137">Images that are very wide or have odd dimensions (for example, floor plans) might get truncated in the OCR process and lose accuracy.</span></span>
 
- <span data-ttu-id="f0faa-138">Para los archivos PDF, las dimensiones deben ser como máximo de 17 x 17 pulgadas, que corresponden al tamaño de papel A3 o legal y tamaños menores.</span><span class="sxs-lookup"><span data-stu-id="f0faa-138">For PDF files, dimensions must be at most 17 x 17 inches, corresponding to Legal or A3 paper sizes and smaller.</span></span>

- <span data-ttu-id="f0faa-139">Si se escanean desde documentos en papel, las digitalizaciones deberían ser imágenes de alta calidad.</span><span class="sxs-lookup"><span data-stu-id="f0faa-139">If scanned from paper documents, scans should be high-quality images.</span></span>

- <span data-ttu-id="f0faa-140">Debe usar el alfabeto latino (caracteres en inglés).</span><span class="sxs-lookup"><span data-stu-id="f0faa-140">Must use the Latin alphabet (English characters).</span></span>

> [!NOTE]
> <span data-ttu-id="f0faa-141">Actualmente, el Generador de AI no admite los siguientes tipos de datos de entrada de procesamiento de formularios:</span><span class="sxs-lookup"><span data-stu-id="f0faa-141">AI Builder doesn't currently support the following types of form processing input data:</span></span><br><span data-ttu-id="f0faa-142">- Casillas o botones de radio</span><span class="sxs-lookup"><span data-stu-id="f0faa-142">- Check boxes or radio buttons</span></span><br><span data-ttu-id="f0faa-143">- Firmas</span><span class="sxs-lookup"><span data-stu-id="f0faa-143">- Signatures</span></span><br><span data-ttu-id="f0faa-144">- Archivos PDF que se pueden rellenar</span><span class="sxs-lookup"><span data-stu-id="f0faa-144">- Fillable PDFs</span></span>

### <a name="supported-file-types"></a><span data-ttu-id="f0faa-145">Tipos de archivo compatibles</span><span class="sxs-lookup"><span data-stu-id="f0faa-145">Supported file types</span></span>

<span data-ttu-id="f0faa-146">Los modelos de comprensión mediante documentos admiten los siguientes tipos de archivo:</span><span class="sxs-lookup"><span data-stu-id="f0faa-146">Document understanding models support the following file types:</span></span>

- <span data-ttu-id="f0faa-147">doc</span><span class="sxs-lookup"><span data-stu-id="f0faa-147">doc</span></span>
- <span data-ttu-id="f0faa-148">docx</span><span class="sxs-lookup"><span data-stu-id="f0faa-148">docx</span></span>
- <span data-ttu-id="f0faa-149">eml</span><span class="sxs-lookup"><span data-stu-id="f0faa-149">eml</span></span>
- <span data-ttu-id="f0faa-150">heic</span><span class="sxs-lookup"><span data-stu-id="f0faa-150">heic</span></span>
- <span data-ttu-id="f0faa-151">heif</span><span class="sxs-lookup"><span data-stu-id="f0faa-151">heif</span></span>
- <span data-ttu-id="f0faa-152">htm</span><span class="sxs-lookup"><span data-stu-id="f0faa-152">htm</span></span>
- <span data-ttu-id="f0faa-153">html</span><span class="sxs-lookup"><span data-stu-id="f0faa-153">html</span></span>
- <span data-ttu-id="f0faa-154">jpeg</span><span class="sxs-lookup"><span data-stu-id="f0faa-154">jpeg</span></span>
- <span data-ttu-id="f0faa-155">jpg</span><span class="sxs-lookup"><span data-stu-id="f0faa-155">jpg</span></span>
- <span data-ttu-id="f0faa-156">markdown</span><span class="sxs-lookup"><span data-stu-id="f0faa-156">markdown</span></span>
- <span data-ttu-id="f0faa-157">md</span><span class="sxs-lookup"><span data-stu-id="f0faa-157">md</span></span>
- <span data-ttu-id="f0faa-158">msg</span><span class="sxs-lookup"><span data-stu-id="f0faa-158">msg</span></span>
- <span data-ttu-id="f0faa-159">pdf</span><span class="sxs-lookup"><span data-stu-id="f0faa-159">pdf</span></span>
- <span data-ttu-id="f0faa-160">png</span><span class="sxs-lookup"><span data-stu-id="f0faa-160">png</span></span>
- <span data-ttu-id="f0faa-161">ppt</span><span class="sxs-lookup"><span data-stu-id="f0faa-161">ppt</span></span>
- <span data-ttu-id="f0faa-162">pptx</span><span class="sxs-lookup"><span data-stu-id="f0faa-162">pptx</span></span>
- <span data-ttu-id="f0faa-163">rtf</span><span class="sxs-lookup"><span data-stu-id="f0faa-163">rtf</span></span>
- <span data-ttu-id="f0faa-164">tif</span><span class="sxs-lookup"><span data-stu-id="f0faa-164">tif</span></span>
- <span data-ttu-id="f0faa-165">tiff</span><span class="sxs-lookup"><span data-stu-id="f0faa-165">tiff</span></span>
- <span data-ttu-id="f0faa-166">txt</span><span class="sxs-lookup"><span data-stu-id="f0faa-166">txt</span></span>
- <span data-ttu-id="f0faa-167">xls</span><span class="sxs-lookup"><span data-stu-id="f0faa-167">xls</span></span>
- <span data-ttu-id="f0faa-168">xlsx</span><span class="sxs-lookup"><span data-stu-id="f0faa-168">xlsx</span></span>



## <a name="see-also"></a><span data-ttu-id="f0faa-169">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f0faa-169">See Also</span></span>
[<span data-ttu-id="f0faa-170">Crear un clasificador</span><span class="sxs-lookup"><span data-stu-id="f0faa-170">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="f0faa-171">Crear un extractor</span><span class="sxs-lookup"><span data-stu-id="f0faa-171">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="f0faa-172">Crear un centro de contenido</span><span class="sxs-lookup"><span data-stu-id="f0faa-172">Create a content center</span></span>](create-a-content-center.md)

[<span data-ttu-id="f0faa-173">Crear un modelo de procesamiento de formularios</span><span class="sxs-lookup"><span data-stu-id="f0faa-173">Create a form processing model</span></span>](create-a-form-processing-model.md)

[<span data-ttu-id="f0faa-174">Aplicar un modelo</span><span class="sxs-lookup"><span data-stu-id="f0faa-174">Apply a model</span></span>](apply-a-model.md)   

[<span data-ttu-id="f0faa-175">Diferencia entre un modelo de comprensión de documentos y un modelo de procesamiento de formularios</span><span class="sxs-lookup"><span data-stu-id="f0faa-175">Difference between a document understanding and a form processing model</span></span>](difference-between-document-understanding-and-form-processing-model.md)
  
[<span data-ttu-id="f0faa-176">Información general del procesamiento de formularios</span><span class="sxs-lookup"><span data-stu-id="f0faa-176">Form processing overview</span></span>](form-processing-overview.md)

[<span data-ttu-id="f0faa-177">Modo de accesibilidad de SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="f0faa-177">SharePoint Syntex Accessibility Mode</span></span>](accessibility-mode.md)