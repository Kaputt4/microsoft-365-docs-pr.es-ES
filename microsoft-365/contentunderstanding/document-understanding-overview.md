---
title: Información general sobre la comprensión de documentos
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Obtenga información general sobre la comprensión des documentos en Microsoft SharePoint Syntex.
ms.openlocfilehash: 73e217e458fb9e1ccad8b64ffc81a6c9522a04f4
ms.sourcegitcommit: 1244bbc4a3d150d37980cab153505ca462fa7ddc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/26/2021
ms.locfileid: "51222760"
---
# <a name="document-understanding-overview"></a><span data-ttu-id="c4385-103">Información general sobre la comprensión de documentos</span><span class="sxs-lookup"><span data-stu-id="c4385-103">Document understanding overview</span></span>


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSu7] 

</br>

<span data-ttu-id="c4385-104">La comprensión de documentos usa modelos de inteligencia artificial (IA) para automatizar la clasificación de archivos y extraer la información.</span><span class="sxs-lookup"><span data-stu-id="c4385-104">Document understanding uses artificial intelligence (AI) models to automate classification of files and extraction of information.</span></span> <span data-ttu-id="c4385-105">Funciona mejor con documentos sin estructura, como cartas o contratos.</span><span class="sxs-lookup"><span data-stu-id="c4385-105">It works best with unstructured documents, such as letters or contracts.</span></span> <span data-ttu-id="c4385-106">Estos documentos deben tener texto que pueda identificarse en función de frases o patrones.</span><span class="sxs-lookup"><span data-stu-id="c4385-106">These documents must have text that can be identified based on phrases or patterns.</span></span> <span data-ttu-id="c4385-107">El texto identificado designa tanto el tipo de archivo (su clasificación) como lo que le gustaría extraer (sus extractores).</span><span class="sxs-lookup"><span data-stu-id="c4385-107">The identified text designates both the type of file it is (its classification) and what you'd like to extract (its extractors).</span></span>

> [!NOTE]
> <span data-ttu-id="c4385-108">Consulte [Adopción de SharePoint Syntex: Guía de introducción](./adoption-getstarted.md) para obtener más información sobre ejemplos de escenarios de comprensión mediante documentos.</span><span class="sxs-lookup"><span data-stu-id="c4385-108">See the [SharePoint Syntex adoption: Get started guide](./adoption-getstarted.md) for more information about document understanding scenario examples.</span></span>

<span data-ttu-id="c4385-109">Los modelos de comprensión mediante documentos se crean y se administran en un tipo de sitio de SharePoint denominado *centro de contenido*.</span><span class="sxs-lookup"><span data-stu-id="c4385-109">Document understanding models are created and managed in a type of SharePoint site called a *content center*.</span></span> <span data-ttu-id="c4385-110">Cuando se aplica a una biblioteca de documentos de SharePoint, el modelo está asociado a un tipo de contenido que tiene columnas para almacenar la información que se va a extraer.</span><span class="sxs-lookup"><span data-stu-id="c4385-110">When applied to a SharePoint document library, the model is associated with a content type has columns to store the information being extracted.</span></span> <span data-ttu-id="c4385-111">El tipo de contenido que cree se almacena en la galería de tipo de contenido de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="c4385-111">The content type you create is stored in the SharePoint content type gallery.</span></span> <span data-ttu-id="c4385-112">También puede optar por usar tipos de contenido existentes para usar su esquema.</span><span class="sxs-lookup"><span data-stu-id="c4385-112">You can also choose to use existing content types to use their schema.</span></span>

> [!NOTE]
> <span data-ttu-id="c4385-113">Los tipos de contenido de solo lectura o sellado no pueden ser actualizados, de manera que no pueden ser usados en un modelo.</span><span class="sxs-lookup"><span data-stu-id="c4385-113">Read-only or sealed content types cannot be updated, so they cannot be used in a model.</span></span>

<span data-ttu-id="c4385-114">Agregue *clasificadores* y *extractores* a los modelos de comprensión del documento para hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c4385-114">Add *classifiers* and *extractors* to your document understanding models to do the following:</span></span> 

- <span data-ttu-id="c4385-115">Los clasificadores se usan para identificar y clasificar documentos cargados en la biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="c4385-115">Classifiers are used to identify and classify documents that are uploaded to the document library.</span></span> <span data-ttu-id="c4385-116">Por ejemplo, un clasificador puede ser "entrenado" para identificar todos los documentos de *renovación de contrato* que se carguen en la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="c4385-116">For example, a classifier can be "trained" to identify all *contract renewal* documents that are uploaded to the library.</span></span> <span data-ttu-id="c4385-117">El tipo de contenido de renovación de contrato lo define el usuario al crear el clasificador.</span><span class="sxs-lookup"><span data-stu-id="c4385-117">The contract renewal content type is defined by you when you create your classifier.</span></span>

- <span data-ttu-id="c4385-118">Los extractores extraen información de estos documentos.</span><span class="sxs-lookup"><span data-stu-id="c4385-118">Extractors pull information from these documents.</span></span> <span data-ttu-id="c4385-119">Por ejemplo, para todos los documentos de renovación de contratos identificados en la biblioteca de documentos, las columnas se muestran en la vista que también muestra la *Fecha de inicio del servicio* y el *Cliente* por cada documento de renovación de contrato.</span><span class="sxs-lookup"><span data-stu-id="c4385-119">For example, for all contract renewal documents identified in your document library, columns display in your view that also show the *Service Start Date* and  *Client* for each contract renewal document.</span></span> 

<span data-ttu-id="c4385-120">Puede usar archivos de ejemplo para entrenarlos y probarlos en el modelo.</span><span class="sxs-lookup"><span data-stu-id="c4385-120">You can use example files to train and test your classifiers and extractors in your model.</span></span> <span data-ttu-id="c4385-121">Los archivos de ejemplo proporcionan ejemplos al modelo de lo que debe buscar al intentar identificar y extraer datos de archivos.</span><span class="sxs-lookup"><span data-stu-id="c4385-121">Example files provide your model examples of what to look for when trying to identify and extract data from files.</span></span> <span data-ttu-id="c4385-122">Por ejemplo, entrenaría los clasificadores y extracciones de renovación de contrato con ejemplos de documentos de renovación de contratos con los que trabaja su empresa.</span><span class="sxs-lookup"><span data-stu-id="c4385-122">For example, you would train your contract renewal classifiers and extractors with examples of contract renewal documents your company works with.</span></span> <span data-ttu-id="c4385-123">También puede usar archivos de ejemplo para probar la efectividad del modelo.</span><span class="sxs-lookup"><span data-stu-id="c4385-123">You can also use example files to test the effectiveness of your model.</span></span>

<span data-ttu-id="c4385-124">Después de publicar el modelo, utilice el centro de contenido para aplicarlo a cualquier biblioteca de documentos de SharePoint a la que tenga acceso.</span><span class="sxs-lookup"><span data-stu-id="c4385-124">After publishing your model, use the content center to apply it to any SharePoint document library that you have access to.</span></span>  

### <a name="file-limitations"></a><span data-ttu-id="c4385-125">Limitaciones de archivos</span><span class="sxs-lookup"><span data-stu-id="c4385-125">File limitations</span></span>

<span data-ttu-id="c4385-126">En los modelos de comprensión mediante documentos se usa la tecnología de reconocimiento óptico de caracteres (OCR) para digitalizar archivos PDF, imágenes y archivos TIFF, tanto al entrenar un modelo con archivos de ejemplo como al ejecutar el modelo en archivos de una biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="c4385-126">Document understanding models use Optical Character Recognition (OCR) technology to scan PDFs, images, and TIFF files, both when you train a model with example files and when you run the model against files in a document library.</span></span>

<span data-ttu-id="c4385-127">Tenga en cuenta las siguientes diferencias en relación con los archivos de texto basados en Microsoft Office y los archivos digitalizados con OCR (PDF, imagen o TIFF):</span><span class="sxs-lookup"><span data-stu-id="c4385-127">Note the following differences in regards to Microsoft Office text-based files and OCR-scanned files (PDF, image, or TIFF):</span></span>

- <span data-ttu-id="c4385-128">Archivos de Office: el límite para truncar archivos es 64 000 caracteres (durante el entrenamiento y cuando se ejecuta en archivos de una biblioteca de documentos).</span><span class="sxs-lookup"><span data-stu-id="c4385-128">Office files: We truncate at 64K characters (in training and when run against files in a document library).</span></span>
- <span data-ttu-id="c4385-129">Archivos digitalizados con OCR: hay un límite de 20 páginas.</span><span class="sxs-lookup"><span data-stu-id="c4385-129">OCR-scanned files: There is a 20 page limit.</span></span>  

#### <a name="supported-file-types"></a><span data-ttu-id="c4385-130">Tipos de archivo compatibles</span><span class="sxs-lookup"><span data-stu-id="c4385-130">Supported file types</span></span>

<span data-ttu-id="c4385-131">Los modelos de comprensión mediante documentos admiten los siguientes tipos de archivo:</span><span class="sxs-lookup"><span data-stu-id="c4385-131">Document understanding models support the following file types:</span></span>

- <span data-ttu-id="c4385-132">doc</span><span class="sxs-lookup"><span data-stu-id="c4385-132">doc</span></span>
- <span data-ttu-id="c4385-133">docx</span><span class="sxs-lookup"><span data-stu-id="c4385-133">docx</span></span>
- <span data-ttu-id="c4385-134">eml</span><span class="sxs-lookup"><span data-stu-id="c4385-134">eml</span></span>
- <span data-ttu-id="c4385-135">heic</span><span class="sxs-lookup"><span data-stu-id="c4385-135">heic</span></span>
- <span data-ttu-id="c4385-136">heif</span><span class="sxs-lookup"><span data-stu-id="c4385-136">heif</span></span>
- <span data-ttu-id="c4385-137">htm</span><span class="sxs-lookup"><span data-stu-id="c4385-137">htm</span></span>
- <span data-ttu-id="c4385-138">html</span><span class="sxs-lookup"><span data-stu-id="c4385-138">html</span></span>
- <span data-ttu-id="c4385-139">jpeg</span><span class="sxs-lookup"><span data-stu-id="c4385-139">jpeg</span></span>
- <span data-ttu-id="c4385-140">jpg</span><span class="sxs-lookup"><span data-stu-id="c4385-140">jpg</span></span>
- <span data-ttu-id="c4385-141">markdown</span><span class="sxs-lookup"><span data-stu-id="c4385-141">markdown</span></span>
- <span data-ttu-id="c4385-142">md</span><span class="sxs-lookup"><span data-stu-id="c4385-142">md</span></span>
- <span data-ttu-id="c4385-143">msg</span><span class="sxs-lookup"><span data-stu-id="c4385-143">msg</span></span>
- <span data-ttu-id="c4385-144">pdf</span><span class="sxs-lookup"><span data-stu-id="c4385-144">pdf</span></span>
- <span data-ttu-id="c4385-145">png</span><span class="sxs-lookup"><span data-stu-id="c4385-145">png</span></span>
- <span data-ttu-id="c4385-146">ppt</span><span class="sxs-lookup"><span data-stu-id="c4385-146">ppt</span></span>
- <span data-ttu-id="c4385-147">pptx</span><span class="sxs-lookup"><span data-stu-id="c4385-147">pptx</span></span>
- <span data-ttu-id="c4385-148">rtf</span><span class="sxs-lookup"><span data-stu-id="c4385-148">rtf</span></span>
- <span data-ttu-id="c4385-149">tif</span><span class="sxs-lookup"><span data-stu-id="c4385-149">tif</span></span>
- <span data-ttu-id="c4385-150">tiff</span><span class="sxs-lookup"><span data-stu-id="c4385-150">tiff</span></span>
- <span data-ttu-id="c4385-151">txt</span><span class="sxs-lookup"><span data-stu-id="c4385-151">txt</span></span>
- <span data-ttu-id="c4385-152">xls</span><span class="sxs-lookup"><span data-stu-id="c4385-152">xls</span></span>
- <span data-ttu-id="c4385-153">xlsx</span><span class="sxs-lookup"><span data-stu-id="c4385-153">xlsx</span></span>



## <a name="see-also"></a><span data-ttu-id="c4385-154">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c4385-154">See Also</span></span>
[<span data-ttu-id="c4385-155">Crear un clasificador</span><span class="sxs-lookup"><span data-stu-id="c4385-155">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="c4385-156">Crear un extractor</span><span class="sxs-lookup"><span data-stu-id="c4385-156">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="c4385-157">Crear un centro de contenido</span><span class="sxs-lookup"><span data-stu-id="c4385-157">Create a content center</span></span>](create-a-content-center.md)

[<span data-ttu-id="c4385-158">Crear un modelo de procesamiento de formularios</span><span class="sxs-lookup"><span data-stu-id="c4385-158">Create a form processing model</span></span>](create-a-form-processing-model.md)

[<span data-ttu-id="c4385-159">Aplicar un modelo</span><span class="sxs-lookup"><span data-stu-id="c4385-159">Apply a model</span></span>](apply-a-model.md)   

[<span data-ttu-id="c4385-160">Diferencia entre un modelo de comprensión de documentos y un modelo de procesamiento de formularios</span><span class="sxs-lookup"><span data-stu-id="c4385-160">Difference between a document understanding and a form processing model</span></span>](difference-between-document-understanding-and-form-processing-model.md)
  
[<span data-ttu-id="c4385-161">Información general del procesamiento de formularios</span><span class="sxs-lookup"><span data-stu-id="c4385-161">Form processing overview</span></span>](form-processing-overview.md)

[<span data-ttu-id="c4385-162">Modo de accesibilidad de SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="c4385-162">SharePoint Syntex Accessibility Mode</span></span>](accessibility-mode.md)