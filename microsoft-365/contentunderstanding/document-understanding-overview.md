---
title: Información general sobre el documento
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 08/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Obtenga información general sobre la descripción de los documentos en Microsoft SharePoint Syntex.
ms.openlocfilehash: dd8731759d8f1cbea57d171fa7a803ffc4f1baa7
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/28/2020
ms.locfileid: "48294765"
---
# <a name="document-understanding-overview"></a><span data-ttu-id="538d2-103">Información general sobre el documento</span><span class="sxs-lookup"><span data-stu-id="538d2-103">Document understanding overview</span></span>


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSu7] 

</br>

<span data-ttu-id="538d2-104">Document Understanding utiliza modelos de inteligencia artificial (AI) para automatizar la clasificación de archivos y la extracción de información.</span><span class="sxs-lookup"><span data-stu-id="538d2-104">Document understanding uses artificial intelligence (AI) models to automate classification of files and extraction of information.</span></span> <span data-ttu-id="538d2-105">Funciona mejor con documentos no estructurados, como cartas o contratos.</span><span class="sxs-lookup"><span data-stu-id="538d2-105">It works best with unstructured documents, such as letters or contracts.</span></span> <span data-ttu-id="538d2-106">Estos documentos deben tener texto que pueda identificarse en función de frases o patrones.</span><span class="sxs-lookup"><span data-stu-id="538d2-106">These documents must have text that can be identified based on phrases or patterns.</span></span> <span data-ttu-id="538d2-107">El texto identificado designa tanto el tipo de archivo (su clasificación) como el que desea extraer (sus extractores).</span><span class="sxs-lookup"><span data-stu-id="538d2-107">The identified text designates both the type of file it is (its classification) and what you'd like to extract (its extractors).</span></span>

<span data-ttu-id="538d2-108">Document: los modelos se crean y se administran en un tipo de sitio de SharePoint denominado *centro de contenido*.</span><span class="sxs-lookup"><span data-stu-id="538d2-108">Document understanding models are created and managed in a type of SharePoint site called a *content center*.</span></span> <span data-ttu-id="538d2-109">Cuando se aplica a una biblioteca de documentos de SharePoint, el modelo está asociado a un tipo de contenido que tiene columnas para almacenar la información que se va a extraer.</span><span class="sxs-lookup"><span data-stu-id="538d2-109">When applied to a SharePoint document library, the model is associated with a content type has columns to store the information being extracted.</span></span> <span data-ttu-id="538d2-110">El tipo de contenido que cree se almacena en la galería de tipos de contenido de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="538d2-110">The content type you create is stored in the SharePoint content type gallery.</span></span> <span data-ttu-id="538d2-111">También puede optar por usar los tipos de contenido existentes para usar su esquema.</span><span class="sxs-lookup"><span data-stu-id="538d2-111">You can also choose to use existing content types to use their schema.</span></span>

<span data-ttu-id="538d2-112">Agregue *clasificadores* y *extractores* a su documento que comprenda los modelos para hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="538d2-112">Add *classifiers* and *extractors* to your document understanding models to do the following:</span></span> 

- <span data-ttu-id="538d2-113">Los clasificadores se usan para identificar y clasificar los documentos que se cargan en la biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="538d2-113">Classifiers are used to identify and classify documents that are uploaded to the document library.</span></span> <span data-ttu-id="538d2-114">Por ejemplo, un clasificador se puede "entrenar" para identificar todos los documentos de *renovación de contratos* que se cargan en la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="538d2-114">For example, a classifier can be "trained" to identify all *contract renewal* documents that are uploaded to the library.</span></span> <span data-ttu-id="538d2-115">El tipo de contenido de renovación del contrato lo define el usuario al crear el clasificador.</span><span class="sxs-lookup"><span data-stu-id="538d2-115">The contract renewal content type is defined by you when you create your classifier.</span></span>

- <span data-ttu-id="538d2-116">Los extractores extraen información de estos documentos.</span><span class="sxs-lookup"><span data-stu-id="538d2-116">Extractors pull information from these documents.</span></span> <span data-ttu-id="538d2-117">Por ejemplo, para todos los documentos de renovación de contratos identificados en la biblioteca de documentos, las columnas se muestran en la vista que también muestran la *fecha de inicio del servicio* y el  *cliente* para cada documento de renovación de contrato.</span><span class="sxs-lookup"><span data-stu-id="538d2-117">For example, for all contract renewal documents identified in your document library, columns display in your view that also show the *Service Start Date* and  *Client* for each contract renewal document.</span></span> 

<span data-ttu-id="538d2-118">Puede usar archivos de ejemplo para entrenar y probar los clasificadores y los extractores en el modelo.</span><span class="sxs-lookup"><span data-stu-id="538d2-118">You can use sample files to train and test your classifiers and extractors in your model.</span></span> <span data-ttu-id="538d2-119">Los archivos de ejemplo proporcionan ejemplos de modelo que deben buscarse al intentar identificar y extraer datos de los archivos.</span><span class="sxs-lookup"><span data-stu-id="538d2-119">Sample files provide your model examples of what to look for when trying to identify and extract data from files.</span></span> <span data-ttu-id="538d2-120">Por ejemplo, puede entrenar a sus clasificadores y extractores de renovación de contratos con muestras de documentos de renovación de contratos con los que trabaja su empresa.</span><span class="sxs-lookup"><span data-stu-id="538d2-120">For example, you would train your contract renewal classifiers and extractors with samples of contract renewal documents your company works with.</span></span> <span data-ttu-id="538d2-121">También puede usar archivos de ejemplo para probar la eficacia del modelo.</span><span class="sxs-lookup"><span data-stu-id="538d2-121">You can also use sample files to test the effectiveness of your model.</span></span>

<span data-ttu-id="538d2-122">Después de publicar el modelo, use el centro de contenido para aplicarlo a cualquier biblioteca de documentos de SharePoint a la que tenga acceso.</span><span class="sxs-lookup"><span data-stu-id="538d2-122">After publishing your model, use the content center to apply it to any SharePoint document library that you have access to.</span></span>  


## <a name="see-also"></a><span data-ttu-id="538d2-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="538d2-123">See Also</span></span>
[<span data-ttu-id="538d2-124">Crear un clasificador</span><span class="sxs-lookup"><span data-stu-id="538d2-124">Create a classifier</span></span>](create-a-classifier.md)</br>
[<span data-ttu-id="538d2-125">Crear un extractor</span><span class="sxs-lookup"><span data-stu-id="538d2-125">Create an extractor</span></span>](create-an-extractor.md)</br>
<span data-ttu-id="538d2-126">[Crear un centro](create-a-content-center.md) 
 de contenido [Crear un modelo de procesamiento de formularios](create-a-form-processing-model.md)</span><span class="sxs-lookup"><span data-stu-id="538d2-126">[Create a content center](create-a-content-center.md)
[Create a form processing model](create-a-form-processing-model.md)</span></span></br>
<span data-ttu-id="538d2-127">[Aplicar un modelo](apply-a-model.md) </span><span class="sxs-lookup"><span data-stu-id="538d2-127">[Apply a model](apply-a-model.md) </span></span>  
[<span data-ttu-id="538d2-128">Diferencia entre una comprensión de documento y un modelo de procesamiento de formularios</span><span class="sxs-lookup"><span data-stu-id="538d2-128">Difference between a document understanding and a form processing model</span></span>](difference-between-document-understanding-and-form-processing-model.md)  
[<span data-ttu-id="538d2-129">Introducción al procesamiento de formularios</span><span class="sxs-lookup"><span data-stu-id="538d2-129">Form processing overview</span></span>](form-processing-overview.md)
