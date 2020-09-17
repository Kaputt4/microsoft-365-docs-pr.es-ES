---
title: Información general sobre el procesamiento de formularios (versión preliminar)
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
description: Obtenga información sobre el procesamiento de formularios en Project Cortex.
ms.openlocfilehash: de8e0ed546380059cc1b7b209eeec71f1eb779f9
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950029"
---
# <a name="form-processing-overview-preview"></a><span data-ttu-id="de4f5-103">Información general sobre el procesamiento de formularios (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="de4f5-103">Form Processing overview (Preview)</span></span>
> [!Note]
> <span data-ttu-id="de4f5-104">El contenido de este artículo es para la versión preliminar privada de Project Cortex.</span><span class="sxs-lookup"><span data-stu-id="de4f5-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="de4f5-105">[Obtenga más información sobre Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="de4f5-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="de4f5-106">Project Cortex usa el procesamiento de formularios de Microsoft PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview) para crear modelos dentro de las bibliotecas de documentos de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="de4f5-106">Project Cortex uses Microsoft PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview) form processing to create models within SharePoint document libraries.</span></span>
<span data-ttu-id="de4f5-107">Puede usar el procesamiento de formularios del generador de AI para crear modelos AI que usen la tecnología de aprendizaje automático para identificar y extraer pares de valores clave y datos de tabla de documentos estructurados o semiestructurados, como formularios y facturas.</span><span class="sxs-lookup"><span data-stu-id="de4f5-107">You can use AI Builder form processing to create AI models that use machine learning technology to identify and extract key-value pairs and table data from structured or semi-structured  documents, like forms and invoices.</span></span>

<span data-ttu-id="de4f5-108">Las empresas a menudo reciben facturas en grandes cantidades y en una gran variedad de orígenes, como correo, fax, correo electrónico o en persona.</span><span class="sxs-lookup"><span data-stu-id="de4f5-108">Companies often receive invoices in large quantities and from a variety of sources, such as mail, fax, email, or in person.</span></span> <span data-ttu-id="de4f5-109">El procesamiento de estos documentos y su introducción manual en la base de datos puede tardar una cantidad considerable de tiempo.</span><span class="sxs-lookup"><span data-stu-id="de4f5-109">Processing these documents and manually entering them into your database can take a considerable amount of time.</span></span> <span data-ttu-id="de4f5-110">Mediante el uso de AI para extraer el texto, los pares clave/valor y las tablas de los documentos, el procesamiento de formularios automatizará este proceso.</span><span class="sxs-lookup"><span data-stu-id="de4f5-110">By using AI to extract the text, key/value pairs, and tables from your documents, form processing will automate this process.</span></span> 

<span data-ttu-id="de4f5-111">Por ejemplo, puede crear un modelo de procesamiento de formularios que identifique todos los documentos de pedido de compra que se cargan en la biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="de4f5-111">For example, you can create a form processing model that will identify all purchase order documents that are uploaded to the document library.</span></span> <span data-ttu-id="de4f5-112">Y de cada pedido de compra puede extraer y Mostrar datos específicos que sean importantes para usted, como *número de pedido*, *fecha*o *coste total*.</span><span class="sxs-lookup"><span data-stu-id="de4f5-112">And from each purchase order you can extract and display specific data that is important to you, such as *PO Number*, *Date*, or *Total Cost*.</span></span>

<span data-ttu-id="de4f5-113">Los archivos de ejemplo se usan para entrenar el modelo y definir la información que se va a extraer del formulario.</span><span class="sxs-lookup"><span data-stu-id="de4f5-113">You use example files to train your model and define the information to be extracted from your form.</span></span> <span data-ttu-id="de4f5-114">El diseño del documento se conoce mediante el entrenamiento del modelo.</span><span class="sxs-lookup"><span data-stu-id="de4f5-114">The layout of your document is learned by training your model.</span></span> <span data-ttu-id="de4f5-115">Solo necesita cinco documentos de formulario para empezar.</span><span class="sxs-lookup"><span data-stu-id="de4f5-115">You only need five form documents to get started.</span></span> <span data-ttu-id="de4f5-116">El generador de AI analizará los archivos de ejemplo para los pares clave-valor, y también puede identificar manualmente aquellos que no se hayan detectado.</span><span class="sxs-lookup"><span data-stu-id="de4f5-116">AI Builder will analyze your example files for key-value pairs, and you can also manually identify ones that may not have been detected.</span></span>  <span data-ttu-id="de4f5-117">El generador de AI permite probar la precisión del modelo en los archivos de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="de4f5-117">AI builder lets you test the accuracy of your model on your sample files.</span></span>

<span data-ttu-id="de4f5-118">Después de entrenar y publicar el modelo, puede usarlo para crear un [flujo de automatización de energía](https://docs.microsoft.com/power-automate/getting-started).</span><span class="sxs-lookup"><span data-stu-id="de4f5-118">After you train and publish your model, to use it you create a [Power Automate Flow](https://docs.microsoft.com/power-automate/getting-started).</span></span> <span data-ttu-id="de4f5-119">El flujo se ejecuta cuando un archivo se carga en la biblioteca de documentos de SharePoint y extrae los datos identificados en el modelo.</span><span class="sxs-lookup"><span data-stu-id="de4f5-119">The flow runs when a file is uploaded to the SharePoint document library and will extract data that has been identified in the model.</span></span> <span data-ttu-id="de4f5-120">Los datos extraídos se mostrarán en columnas en la vista de la biblioteca de documentos del modelo.</span><span class="sxs-lookup"><span data-stu-id="de4f5-120">The extracted data will display in columns in your model's document library view.</span></span>

<span data-ttu-id="de4f5-121">Un administrador de Office 365 debe [Habilitar el procesamiento de formularios](https://docs.microsoft.com/microsoft-365/contentunderstanding/set-up-content-understanding?view=o365-worldwide#to-set-up-content-understanding) para la biblioteca de documentos de SharePoint para que los usuarios puedan [crear un modelo de procesamiento de formularios](create-a-form-processing-model.md) en él.</span><span class="sxs-lookup"><span data-stu-id="de4f5-121">An Office 365 admin needs to [enable Form processing](https://docs.microsoft.com/microsoft-365/contentunderstanding/set-up-content-understanding?view=o365-worldwide#to-set-up-content-understanding) for the SharePoint document library for users to be able to [create a form processing model](create-a-form-processing-model.md) in it.</span></span>



## <a name="see-also"></a><span data-ttu-id="de4f5-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="de4f5-122">See Also</span></span>
  
[<span data-ttu-id="de4f5-123">Documentación automatizada de la energía</span><span class="sxs-lookup"><span data-stu-id="de4f5-123">Power Automate documentation</span></span>](https://docs.microsoft.com/power-automate/)</br>
[<span data-ttu-id="de4f5-124">Crear un modelo de procesamiento de formularios</span><span class="sxs-lookup"><span data-stu-id="de4f5-124">Create a form processing model</span></span>](create-a-form-processing-model.md)</br>
[<span data-ttu-id="de4f5-125">Información general sobre el documento</span><span class="sxs-lookup"><span data-stu-id="de4f5-125">Document understanding overview</span></span>](document-understanding-overview.md)</br>
[<span data-ttu-id="de4f5-126">Aprendizaje: mejorar el rendimiento empresarial con el generador de AI</span><span class="sxs-lookup"><span data-stu-id="de4f5-126">Training: Improve business performance with AI Builder</span></span>](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>




