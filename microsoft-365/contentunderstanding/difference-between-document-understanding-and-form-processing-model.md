---
title: Diferencia entre los modelos de comprensión de documentos y procesamiento de formularios (versión preliminar)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Describe la diferencia clave entre los modelos de procesamiento de formularios y la comprensión de documentos.
ms.openlocfilehash: ceea3a6e7898d8971ea458222d6164b496fcb8b7
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950065"
---
# <a name="difference-between-document-understanding-and-form-processing-models-preview"></a><span data-ttu-id="bb145-103">Diferencia entre los modelos de comprensión de documentos y procesamiento de formularios (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="bb145-103">Difference between document understanding and form processing models (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="bb145-104">El contenido de este artículo es para la versión preliminar privada de Project Cortex.</span><span class="sxs-lookup"><span data-stu-id="bb145-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="bb145-105">[Obtenga más información sobre Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="bb145-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="bb145-106">La comprensión del contenido en Project Cortex permite identificar y clasificar los documentos que se cargan en bibliotecas de documentos de SharePoint, así como extraer información relevante de cada archivo.</span><span class="sxs-lookup"><span data-stu-id="bb145-106">Content understanding in Project Cortex allows you to identify and classify documents that are uploaded to SharePoint document libraries, as well as extracting relevant information from each file.</span></span>  <span data-ttu-id="bb145-107">Por ejemplo, a medida que los archivos se cargan en una biblioteca de documentos de SharePoint, todos los archivos que se identifican como *pedidos de compra* se clasifican como tales y se muestran en una vista de biblioteca de documentos personalizada en la que se muestran.</span><span class="sxs-lookup"><span data-stu-id="bb145-107">For example, as files are uploaded to a SharePoint document library, all files that are identified as *Purchase Orders* are classified as such and displayed in a custom document library view in which they are displayed.</span></span> <span data-ttu-id="bb145-108">Además, puede extraer información específica de cada archivo (por ejemplo, *número de PC* y *total*) y mostrarla en una columna en la vista de la biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="bb145-108">Additionally, you can pull specific information from each file (for example, *PO Number* and *Total*) and display it in a column in your document library view.</span></span> 


<span data-ttu-id="bb145-109">El conocimiento del contenido le permite crear *modelos* para identificar y extraer la información que necesita.</span><span class="sxs-lookup"><span data-stu-id="bb145-109">Content understanding lets you create *models* to identify and extract the information you need.</span></span>  <span data-ttu-id="bb145-110">Hay dos tipos de modelos que se pueden usar:</span><span class="sxs-lookup"><span data-stu-id="bb145-110">There are two types of models that can be used:</span></span>

- [<span data-ttu-id="bb145-111">Documento sobre modelos</span><span class="sxs-lookup"><span data-stu-id="bb145-111">Document understanding models</span></span>](document-understanding-overview.md)
- [<span data-ttu-id="bb145-112">Modelos de procesamiento de formularios</span><span class="sxs-lookup"><span data-stu-id="bb145-112">Form processing models</span></span>](form-processing-overview.md)

<span data-ttu-id="bb145-113">Aunque ambos modelos se usan por lo general, hay diferencias clave que afectarán a la opción que se puede elegir usar.</span><span class="sxs-lookup"><span data-stu-id="bb145-113">While both models are used for generally the same purpose, there are key differences that will affect which one you might choose to use.</span></span>


## <a name="structured-versus-unstructured-and-semi-structured-content"></a><span data-ttu-id="bb145-114">Contenido estructurado en lugar de contenido semiestructurado.</span><span class="sxs-lookup"><span data-stu-id="bb145-114">Structured versus unstructured and semi-structured content</span></span>

<span data-ttu-id="bb145-115">Use Document que comprenda los modelos para identificar y extraer datos de documentos no estructurados, como cartas o contratos, donde las entidades de texto que desea extraer residen en oraciones o regiones específicas del documento.</span><span class="sxs-lookup"><span data-stu-id="bb145-115">Use document understanding models to identify and extract data from unstructured documents, such as letters or contracts, where the text entities you want to extract reside in sentences or specific regions of the document.</span></span> <span data-ttu-id="bb145-116">Por ejemplo, un documento sin estructurar podría ser una carta de renovación de contrato que puede escribirse de varias formas.</span><span class="sxs-lookup"><span data-stu-id="bb145-116">For example, an unstructured document could be a contract renewal letter that can be written in different ways.</span></span> <span data-ttu-id="bb145-117">Sin embargo, hay información que es coherente en el cuerpo de cada documento de renovación de contrato, como la cadena de texto "fecha de inicio del servicio" seguida de una fecha real.</span><span class="sxs-lookup"><span data-stu-id="bb145-117">However, there is information that is consistently in the body of each contract renewal document, such as the text string "Service start date of" followed by an actual date.</span></span>   

<span data-ttu-id="bb145-118">Use modelos de procesamiento de formularios para identificar archivos y extraer datos de documentos estructurados o semiestructurados, como formularios o facturas, donde tiene pares clave-valor claros (por ejemplo, *Date: 10/1/2020*) \* o datos de tabla.</span><span class="sxs-lookup"><span data-stu-id="bb145-118">Use form processing models to identify files and extract data from structured or semi-structured documents, such as forms or invoices, where you have clear key-value pairs (for example, *Date: 10/1/2020*)\* or table data.</span></span> <span data-ttu-id="bb145-119">Por ejemplo, un buen candidato para el procesamiento de formularios sería el formulario de solicitud de pedido de una compañía en el que los clientes necesitan proporcionar su información para campos específicos que se encuentran en la misma área del diseño del documento, como *el nombre, el* *número de teléfono*, el *costo total*, etc.  Un formulario de impuestos es un buen ejemplo de un documento estructurado.</span><span class="sxs-lookup"><span data-stu-id="bb145-119">As an example, a good candidate for form processing would be a company's order request form in which clients need to provide their information for specific fields which are located in the same area of the document layout, such as *Name*, *Phone Number*, *Total Cost*, etc.  A tax form is a good example of a structured document.</span></span> 

## <a name="where-they-are-created"></a><span data-ttu-id="bb145-120">Dónde se crean</span><span class="sxs-lookup"><span data-stu-id="bb145-120">Where they are created</span></span>

<span data-ttu-id="bb145-121">Document: los modelos se crean y administran en un sitio del centro de contenido de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="bb145-121">Document understanding models are created and managed in a SharePoint content center site.</span></span> <span data-ttu-id="bb145-122">Debe tener acceso a un sitio del centro de contenido para crear un documento que comprenda el modelo o para aplicar uno a una biblioteca de documentos de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="bb145-122">You must have access to a content center site to create a document understanding model or to apply one to a SharePoint document library.</span></span> 

<span data-ttu-id="bb145-123">Al crear un documento que comprenda el modelo, se crea un nuevo [tipo de contenido de SharePoint](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978) que se guarda en la galería de tipos de contenido de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="bb145-123">When you create a document understanding model, you create a new [SharePoint content type](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978) that is saved to the SharePoint Content Types gallery.</span></span> <span data-ttu-id="bb145-124">Opcionalmente, puede usar los tipos de contenido existentes para definir el modelo si es necesario.</span><span class="sxs-lookup"><span data-stu-id="bb145-124">You can optionally use existing content types to define your model if needed.</span></span>

<span data-ttu-id="bb145-125">Los modelos de procesamiento de formularios se crean en PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview), pero la creación se inicia directamente desde una biblioteca de documentos de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="bb145-125">Form processing models are created in PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview), but the creation is initiated directly from a SharePoint document library.</span></span> <span data-ttu-id="bb145-126">El modelo de procesamiento de formularios debe estar habilitado en la biblioteca de documentos para que un usuario pueda crear un modelo de procesamiento de formularios para el mismo, y un administrador puede hacer esto en el contenido que comprenda la configuración de administración.</span><span class="sxs-lookup"><span data-stu-id="bb145-126">Form processing model creation needs to be enabled on your document library in order for a user to create a form processing model for it, and an admin can do this in the content understanding admin settings.</span></span> <span data-ttu-id="bb145-127">Los modelos de procesamiento de formularios usan flujos de PowerAutomate para procesar archivos cuando se cargan en la biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="bb145-127">Form processing models use PowerAutomate flows to process files when they are uploaded to the document library.</span></span>

<span data-ttu-id="bb145-128">Los modelos de procesamiento de formularios también crean nuevos [tipos de contenido de SharePoint](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978), que también se almacenan en la galería de tipos de contenido de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="bb145-128">Form processing models also create new [SharePoint content types](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978), which are also stored in the SharePoint Content Types gallery.</span></span>

## <a name="where-they-can-be-applied"></a><span data-ttu-id="bb145-129">Dónde se pueden aplicar</span><span class="sxs-lookup"><span data-stu-id="bb145-129">Where they can be applied</span></span>

<span data-ttu-id="bb145-130">Document: los modelos se pueden aplicar a diferentes bibliotecas de documentos de SharePoint a las que tiene acceso.</span><span class="sxs-lookup"><span data-stu-id="bb145-130">Document understanding models can be applied to different SharePoint document libraries that you have access to.</span></span> <span data-ttu-id="bb145-131">Puede usar el centro de contenido no solo para crear un documento que comprenda el modelo, sino también para aplicarlo a diferentes bibliotecas de documentos.</span><span class="sxs-lookup"><span data-stu-id="bb145-131">You can use the content center to not only create a document understanding model, but also to apply it to different document libraries.</span></span> <span data-ttu-id="bb145-132">El centro de contenido ofrece un control más central sobre cómo se usan los modelos de comprensión de los modelos y dónde se aplican, ya que esta información debe acumularse en un centro de contenido.</span><span class="sxs-lookup"><span data-stu-id="bb145-132">The content center gives a more central control of how document understanding models are used and where they are applied, since this information must roll up to a content center.</span></span>

<span data-ttu-id="bb145-133">Actualmente, los modelos de procesamiento de formularios solo se pueden aplicar a la biblioteca de documentos de SharePoint desde la que se crearon.</span><span class="sxs-lookup"><span data-stu-id="bb145-133">Form processing models can currently only be applied to the SharePoint document library from which they were created.</span></span> <span data-ttu-id="bb145-134">Esto permite que cualquier usuario con licencia que tenga acceso al sitio cree un modelo de procesamiento de formularios.</span><span class="sxs-lookup"><span data-stu-id="bb145-134">This allows any licensed user who has access to the site to create a form processing model.</span></span>




 ## <a name="see-also"></a><span data-ttu-id="bb145-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="bb145-135">See Also</span></span>
[<span data-ttu-id="bb145-136">Aprendizaje: mejorar el rendimiento empresarial con el generador de AI</span><span class="sxs-lookup"><span data-stu-id="bb145-136">Training: Improve business performance with AI Builder</span></span>](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>
[<span data-ttu-id="bb145-137">Crear un clasificador</span><span class="sxs-lookup"><span data-stu-id="bb145-137">Create a classifier</span></span>](create-a-classifier.md)</br>
[<span data-ttu-id="bb145-138">Crear un extractor</span><span class="sxs-lookup"><span data-stu-id="bb145-138">Create an extractor</span></span>](create-an-extractor.md)</br>
[<span data-ttu-id="bb145-139">Aplicación de un documento con información sobre el modelo</span><span class="sxs-lookup"><span data-stu-id="bb145-139">Apply a document understanding model</span></span>](apply-a-model.md)</br>
[<span data-ttu-id="bb145-140">Crear un modelo de procesamiento de formularios</span><span class="sxs-lookup"><span data-stu-id="bb145-140">Create a form processing model</span></span>](create-a-form-processing-model.md)</br>



  
  



