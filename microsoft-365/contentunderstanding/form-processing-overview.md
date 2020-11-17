---
title: Información general del procesamiento de formularios
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: Priority
description: Más información sobre el procesamiento de formularios en Microsoft SharePoint Syntex
ms.openlocfilehash: 6c2cb2ee3c1fc621e7814f4603ad2e6f0b891701
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087408"
---
# <a name="form-processing-overview"></a><span data-ttu-id="b67c9-103">Información general del procesamiento de formularios</span><span class="sxs-lookup"><span data-stu-id="b67c9-103">Form processing overview</span></span>

 ![Generador de IA](../media/content-understanding/ai-builder.png)</br>

<span data-ttu-id="b67c9-105">Microsoft SharePoint Syntex usa el procesamiento de formularios del [generador de IA](https://docs.microsoft.com/ai-builder/overview) de Microsoft PowerApps para crear modelos en las bibliotecas de documentos de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="b67c9-105">Microsoft SharePoint Syntex uses Microsoft PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview) form processing to create models within SharePoint document libraries.</span></span>

<span data-ttu-id="b67c9-106">Puede usar el procesamiento de formularios del generador de IA para crear modelos de IA que usan la tecnología de aprendizaje automático para identificar y extraer pares de valor-clave y datos de tabla de documentos estructurados o semiestructurados, como formularios y facturas.</span><span class="sxs-lookup"><span data-stu-id="b67c9-106">You can use AI Builder form processing to create AI models that use machine learning technology to identify and extract key-value pairs and table data from structured or semi-structured  documents, like forms and invoices.</span></span>

<span data-ttu-id="b67c9-107">La mayoría de las organizaciones suelen recibir facturas en grandes cantidades y de una gran variedad de orígenes, como correo, fax, correo electrónico, etc. Procesar estos documentos y añadirlos manualmente a una base de datos puede suponer un tiempo considerable.</span><span class="sxs-lookup"><span data-stu-id="b67c9-107">Organizations often receive invoices in large quantities from a variety of sources, such as mail, fax, email, etc. Processing these documents and manually entering them into a database can take a considerable amount of time.</span></span> <span data-ttu-id="b67c9-108">Mediante el uso de IA para extraer el texto, los pares clave o de valor y las tablas de los documentos, el procesamiento de formularios automatiza este proceso.</span><span class="sxs-lookup"><span data-stu-id="b67c9-108">By using AI to extract the text, key/value pairs, and tables from your documents, form processing automates this process.</span></span> 

> [!NOTE]
> <span data-ttu-id="b67c9-109">Consulte la guía [Adopción de SharePoint Syntex: Guía de introducción](https://docs.microsoft.com/microsoft-365/contentunderstanding/adoption-getstarted#form-processing-scenario-example) para obtener más información sobre ejemplos de escenarios de procesamiento de formularios.</span><span class="sxs-lookup"><span data-stu-id="b67c9-109">See the [SharePoint Syntex adoption: Get started guide](https://docs.microsoft.com/microsoft-365/contentunderstanding/adoption-getstarted#form-processing-scenario-example) for more information about form processing scenario examples.</span></span>

<span data-ttu-id="b67c9-110">Por ejemplo, puede crear un modelo de procesamiento de formularios que identifique todos los documentos de pedido de compra que se hayan cargado en la biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="b67c9-110">For example, you can create a form processing model that identifies all purchase order documents that are uploaded to the document library.</span></span> <span data-ttu-id="b67c9-111">A partir de cada pedido de compra, puede extraer y mostrar datos específicos que sean importantes para usted, como el *Número de pedido de compra*, la *Fecha* o el *Coste total*.</span><span class="sxs-lookup"><span data-stu-id="b67c9-111">From each purchase order you can then extract and display specific data that is important to you, such as *PO Number*, *Date*, or *Total Cost*.</span></span>

![Vista de la biblioteca de documentos](../media/content-understanding/doc-lib-done.png)</br>  

<span data-ttu-id="b67c9-113">Use archivos de ejemplo para entrenar el modelo y definir la información que se extrae del formulario.</span><span class="sxs-lookup"><span data-stu-id="b67c9-113">You use example files to train your model and define the information to be extracted from your form.</span></span> <span data-ttu-id="b67c9-114">El diseño del documento viene se aprende al entrenar el modelo.</span><span class="sxs-lookup"><span data-stu-id="b67c9-114">The layout of your document is learned by training your model.</span></span> <span data-ttu-id="b67c9-115">Solo necesita cinco documentos de formulario para empezar.</span><span class="sxs-lookup"><span data-stu-id="b67c9-115">You only need five form documents to get started.</span></span> <span data-ttu-id="b67c9-116">El generador de IA analizará los archivos de ejemplo para pares de clave y valor, y también puede identificar manualmente los que no se hayan detectado.</span><span class="sxs-lookup"><span data-stu-id="b67c9-116">AI Builder will analyze your example files for key-value pairs, and you can also manually identify ones that may not have been detected.</span></span>  <span data-ttu-id="b67c9-117">El generador de IA le permite probar la precisión de su modelo en los archivos de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="b67c9-117">AI builder lets you test the accuracy of your model on your example files.</span></span>

<span data-ttu-id="b67c9-118">Necesita un mínimo de cinco documentos de formulario para empezar.</span><span class="sxs-lookup"><span data-stu-id="b67c9-118">You need a minimum of five form documents to get started.</span></span> <span data-ttu-id="b67c9-119">La creación de IA analiza los archivos de ejemplo para buscar pares de clave-valor e identifica manualmente los que es posible que no se hayan detectado.</span><span class="sxs-lookup"><span data-stu-id="b67c9-119">AI building analyzes your example files for key-value pairs, and then manually identifies the ones that may not have been detected.</span></span>  <span data-ttu-id="b67c9-120">El generador de IA le permite probar la precisión de su modelo en los archivos de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="b67c9-120">AI builder lets you test the accuracy of your model on your example files.</span></span>

<span data-ttu-id="b67c9-121">Una vez que haya entrenado y publicado el modelo, el modelo crea un [flujo de Power Automate](https://docs.microsoft.com/power-automate/getting-started).</span><span class="sxs-lookup"><span data-stu-id="b67c9-121">After you train and publish your model, your model creates a [Power Automate Flow](https://docs.microsoft.com/power-automate/getting-started).</span></span> <span data-ttu-id="b67c9-122">El flujo se ejecuta cuando se carga un archivo en la biblioteca de documentos de SharePoint y se extraen los datos identificados en el modelo.</span><span class="sxs-lookup"><span data-stu-id="b67c9-122">The flow runs when a file is uploaded to the SharePoint document library and will extract data that has been identified in the model.</span></span> <span data-ttu-id="b67c9-123">Los datos extraídos se mostrarán en columnas en la vista de la biblioteca de documentos del modelo.</span><span class="sxs-lookup"><span data-stu-id="b67c9-123">The extracted data will display in columns in your model's document library view.</span></span>

<span data-ttu-id="b67c9-124">Los administradores de Office 365 deben [habilitar el procesamiento de formularios](https://docs.microsoft.com/microsoft-365/contentunderstanding/set-up-content-understanding#to-set-up-content-understanding) para la biblioteca de documentos de SharePoint para que los usuarios puedan [crear un modelo de procesamiento de formularios](create-a-form-processing-model.md) en ella.</span><span class="sxs-lookup"><span data-stu-id="b67c9-124">An Office 365 admin needs to [enable Form processing](https://docs.microsoft.com/microsoft-365/contentunderstanding/set-up-content-understanding#to-set-up-content-understanding) for the SharePoint document library for users to be able to [create a form processing model](create-a-form-processing-model.md) in it.</span></span> <span data-ttu-id="b67c9-125">Puede seleccionar los sitios durante la instalación o después de la misma, en la configuración de administración.</span><span class="sxs-lookup"><span data-stu-id="b67c9-125">You can select the sites during setup, or after setup in your management settings.</span></span>



## <a name="see-also"></a><span data-ttu-id="b67c9-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b67c9-126">See Also</span></span>
  
[<span data-ttu-id="b67c9-127">Documentación de Power Automate</span><span class="sxs-lookup"><span data-stu-id="b67c9-127">Power Automate documentation</span></span>](https://docs.microsoft.com/power-automate/)

[<span data-ttu-id="b67c9-128">Crear un modelo de procesamiento de formularios</span><span class="sxs-lookup"><span data-stu-id="b67c9-128">Create a form processing model</span></span>](create-a-form-processing-model.md)

[<span data-ttu-id="b67c9-129">Información general sobre la comprensión de documentos</span><span class="sxs-lookup"><span data-stu-id="b67c9-129">Document understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="b67c9-130">Aprendizaje: mejorar el rendimiento empresarial con el generador de IA</span><span class="sxs-lookup"><span data-stu-id="b67c9-130">Training: Improve business performance with AI Builder</span></span>](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)
