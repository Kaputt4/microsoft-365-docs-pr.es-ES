---
title: Introducción a la descripción de los documentos (versión preliminar)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 08/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Obtenga información general sobre la descripción de los documentos en Project Cortex.
ms.openlocfilehash: 13b0aa3742c6cf1c0c1123996c683d13c6577876
ms.sourcegitcommit: ea5e2f85bd6b609658545b120c7e08789b9686fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2020
ms.locfileid: "46537405"
---
# <a name="document-understanding-overview-preview"></a><span data-ttu-id="55542-103">Introducción a la descripción de los documentos (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="55542-103">Document understanding overview (Preview)</span></span>
> [!Note] 
> <span data-ttu-id="55542-104">Project Cortex se encuentra actualmente en versión preliminar.</span><span class="sxs-lookup"><span data-stu-id="55542-104">Project Cortex is currently in Preview.</span></span> <span data-ttu-id="55542-105">[Obtenga más información sobre Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="55542-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSu7] 

</br>

<span data-ttu-id="55542-106">Document Understanding utiliza modelos AI para automatizar la clasificación de archivos y la extracción de información.</span><span class="sxs-lookup"><span data-stu-id="55542-106">Document understanding uses AI models to automate classification of files and extraction of information.</span></span> <span data-ttu-id="55542-107">Funciona mejor con documentos no estructurados, como cartas o contratos.</span><span class="sxs-lookup"><span data-stu-id="55542-107">It works best with unstructured documents, like letters or contracts.</span></span> <span data-ttu-id="55542-108">Los documentos deben tener texto que pueda identificarse en función de frases o patrones.</span><span class="sxs-lookup"><span data-stu-id="55542-108">The documents should have text that can be identified based on phrases or patterns.</span></span> <span data-ttu-id="55542-109">El texto identificado puede designar tanto el tipo de archivo que es (su clasificación) como el que quiere extraer (sus extractores).</span><span class="sxs-lookup"><span data-stu-id="55542-109">The identified text can designate both the type of file it is (its classification) and what you'd like to extract (its extractors).</span></span>

<span data-ttu-id="55542-110">Document: los modelos se crean y se administran en un tipo de sitio de SharePoint denominado Centro de contenido.</span><span class="sxs-lookup"><span data-stu-id="55542-110">Document understanding models are created and managed in a type of SharePoint site called a content center.</span></span> <span data-ttu-id="55542-111">Cuando se aplica a una biblioteca de documentos de SharePoint, el modelo está asociado a un tipo de contenido que tiene columnas para almacenar la información extraída.</span><span class="sxs-lookup"><span data-stu-id="55542-111">When applied to a SharePoint document library, the model is associated with a content type which has columns to store the information extracted.</span></span> <span data-ttu-id="55542-112">El tipo de contenido que cree se almacena en la galería de tipos de contenido de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="55542-112">The content type you create is stored in the SharePoint content type gallery.</span></span> <span data-ttu-id="55542-113">También puede optar por usar los tipos de contenido existentes para usar su esquema.</span><span class="sxs-lookup"><span data-stu-id="55542-113">You can also choose to use existing content types in order to use their schema.</span></span>

<span data-ttu-id="55542-114">Puede agregar *clasificadores* y *extractores* a su documento que comprenda los modelos para hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="55542-114">You can add *classifiers* and *extractors* to your document understanding models to do the following:</span></span> 

- <span data-ttu-id="55542-115">Los clasificadores se usan para identificar y clasificar los documentos que se cargan en la biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="55542-115">Classifiers are used to identify and classify documents that are uploaded to the document library.</span></span> <span data-ttu-id="55542-116">Por ejemplo, un clasificador se puede "entrenar" para identificar todos los documentos de *renovación de contratos* que se cargan en la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="55542-116">For example, a classifier can be "trained" to identify all *contract renewal* documents that are uploaded to the library.</span></span> <span data-ttu-id="55542-117">El tipo de contenido de renovación del contrato lo define el usuario al crear el clasificador.</span><span class="sxs-lookup"><span data-stu-id="55542-117">The contract renewal content type is defined by you when you create your classifier.</span></span>

- <span data-ttu-id="55542-118">Los extractores extraen información de estos documentos.</span><span class="sxs-lookup"><span data-stu-id="55542-118">Extractors pull information from these documents.</span></span> <span data-ttu-id="55542-119">Por ejemplo, para todos los documentos de renovación de contratos que se identifican en la biblioteca de documentos, se mostrarán columnas en la vista que también mostrarán la *fecha de inicio del servicio* y el *cliente* para cada documento de renovación de contrato.</span><span class="sxs-lookup"><span data-stu-id="55542-119">For example, for all contract renewal documents that are identified in your document library, columns will display in your view that will also show the *Service Start Date* and  *Client* for each contract renewal document.</span></span> 

<span data-ttu-id="55542-120">Los archivos de ejemplo se usan para entrenar y probar los clasificadores y los extractores en el modelo.</span><span class="sxs-lookup"><span data-stu-id="55542-120">You use example files to train and test your classifiers and extractors in your model.</span></span> <span data-ttu-id="55542-121">Los archivos de ejemplo proporcionan ejemplos de modelo que deben buscarse al intentar identificar y extraer datos de los archivos.</span><span class="sxs-lookup"><span data-stu-id="55542-121">Example files provide your model examples of what to look for when trying to identify and extract data from files.</span></span> <span data-ttu-id="55542-122">Por ejemplo, puede entrenar a sus clasificadores y extractores de renovación de contratos con ejemplos de documentos de renovación de contratos con los que trabaja su empresa.</span><span class="sxs-lookup"><span data-stu-id="55542-122">For example, you would train your contract renewal classifiers and extractors with examples of contract renewal documents your company works with.</span></span> <span data-ttu-id="55542-123">También puede usar archivos de ejemplo para probar la eficacia del modelo.</span><span class="sxs-lookup"><span data-stu-id="55542-123">You can also use example files to test the effectiveness of your model.</span></span>

<span data-ttu-id="55542-124">Después de publicar el modelo, use el centro de contenido para aplicarlo a cualquier biblioteca de documentos de SharePoint a la que tenga acceso.</span><span class="sxs-lookup"><span data-stu-id="55542-124">After publishing your model, use the content center to apply it to any SharePoint document library that you have access to.</span></span>  


## <a name="see-also"></a><span data-ttu-id="55542-125">Consulta también</span><span class="sxs-lookup"><span data-stu-id="55542-125">See Also</span></span>
[<span data-ttu-id="55542-126">Crear un clasificador</span><span class="sxs-lookup"><span data-stu-id="55542-126">Create a classifier</span></span>](create-a-classifier.md)</br>
[<span data-ttu-id="55542-127">Crear un extractor</span><span class="sxs-lookup"><span data-stu-id="55542-127">Create an extractor</span></span>](create-an-extractor.md)</br>
<span data-ttu-id="55542-128">[Crear un centro](create-a-content-center.md) 
 de contenido [Crear un modelo de procesamiento de formularios](create-a-form-processing-model.md)</span><span class="sxs-lookup"><span data-stu-id="55542-128">[Create a content center](create-a-content-center.md)
[Create a form processing model](create-a-form-processing-model.md)</span></span></br>
<span data-ttu-id="55542-129">[Aplicar un modelo](apply-a-model.md) </span><span class="sxs-lookup"><span data-stu-id="55542-129">[Apply a model](apply-a-model.md) </span></span>  
[<span data-ttu-id="55542-130">Diferencia entre una comprensión de documento y un modelo de procesamiento de formularios</span><span class="sxs-lookup"><span data-stu-id="55542-130">Difference between a document understanding and a form processing model</span></span>](difference-between-document-understanding-and-form-processing-model.md)  
[<span data-ttu-id="55542-131">Introducción al procesamiento de formularios</span><span class="sxs-lookup"><span data-stu-id="55542-131">Form processing overview</span></span>](form-processing-overview.md)




