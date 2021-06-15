---
title: API de REST del modelo de comprensión mediante documentos de SharePoint Syntex
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: reference
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: m365initiative-syntex
localization_priority: Priority
description: Información general sobre la API de REST del modelo de comprensión mediante documentos de SharePoint Syntex.
ms.openlocfilehash: 279c624bb818e5d8d33b476f997290269ff634cb
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904316"
---
# <a name="sharepoint-syntex-document-understanding-model-rest-api"></a><span data-ttu-id="51ead-103">API de REST del modelo de comprensión mediante documentos de SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="51ead-103">SharePoint Syntex document understanding model REST API</span></span>

<span data-ttu-id="51ead-104">Puede usar la interfaz REST de SharePoint para crear un modelo de comprensión mediante documentos, aplicar o quitar el modelo a una o más bibliotecas, y obtener o actualizar información sobre el modelo.</span><span class="sxs-lookup"><span data-stu-id="51ead-104">You can use the SharePoint REST interface to create a document understanding model, apply or remove the model to one or more libraries, and obtain or update information about the model.</span></span> 

<span data-ttu-id="51ead-105">El servicio REST de SharePoint Online (y SharePoint 2016 o versiones posteriores locales) admite la combinación de varias solicitudes en una sola llamada al servicio mediante el uso de la opción de consulta $batch de OData.</span><span class="sxs-lookup"><span data-stu-id="51ead-105">The SharePoint Online (and SharePoint 2016 and later on-premises) REST service supports combining multiple requests into a single call to the service by using the OData $batch query option.</span></span> 

<span data-ttu-id="51ead-106">Para obtener información detallada y vínculos a los ejemplos de código, vea [Realizar solicitudes de lote con las API de REST](/sharepoint/dev/sp-add-ins/make-batch-requests-with-the-rest-apis.md).</span><span class="sxs-lookup"><span data-stu-id="51ead-106">For details and links to code samples, see [Make batch requests with the REST APIs](/sharepoint/dev/sp-add-ins/make-batch-requests-with-the-rest-apis.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="51ead-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="51ead-107">Prerequisites</span></span>

<span data-ttu-id="51ead-108">Antes de empezar, asegúrese de que está familiarizado con lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="51ead-108">Before you get started, make sure that you're familiar with the following:</span></span>

- [<span data-ttu-id="51ead-109">Introducción al servicio REST para SharePoint</span><span class="sxs-lookup"><span data-stu-id="51ead-109">Get to know the SharePoint REST service</span></span>](/sharepoint/dev/sp-add-ins/get-to-know-the-sharepoint-rest-service.md) 
- [<span data-ttu-id="51ead-110">Completar operaciones básicas con puntos de conexión REST de SharePoint</span><span class="sxs-lookup"><span data-stu-id="51ead-110">Complete basic operations using SharePoint REST endpoints</span></span>](/sharepoint/dev/sp-add-ins/complete-basic-operations-using-sharepoint-rest-endpoints.md)

## <a name="rest-commands"></a><span data-ttu-id="51ead-111">Comandos de REST</span><span class="sxs-lookup"><span data-stu-id="51ead-111">REST commands</span></span>

<span data-ttu-id="51ead-112">Los siguientes comandos de REST están disponibles para trabajar con modelos de comprensión mediante documentos de Syntex:</span><span class="sxs-lookup"><span data-stu-id="51ead-112">The following REST commands are available for working with Syntex document understanding models:</span></span>

- <span data-ttu-id="51ead-113">[Crear modelo](rest-createmodel-method.md): Crea un modelo y su tipo de contenido asociado.</span><span class="sxs-lookup"><span data-stu-id="51ead-113">[Create model](rest-createmodel-method.md) – Creates a model and its associated content type.</span></span>
- <span data-ttu-id="51ead-114">[GetByUniqueId](rest-getbyuniqueid-method.md): Obtiene o actualiza información sobre un modelo de comprensión mediante documentos de SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="51ead-114">[GetByUniqueId](rest-getbyuniqueid-method.md) – Gets or updates information about a SharePoint Syntex document understanding model.</span></span>
- <span data-ttu-id="51ead-115">[GetByTitle](rest-getbytitle-method.md): Obtiene o actualiza información sobre un modelo de comprensión mediante documentos de SharePoint Syntex mediante el título del modelo.</span><span class="sxs-lookup"><span data-stu-id="51ead-115">[GetByTitle](rest-getbytitle-method.md) – Gets or updates information about a SharePoint Syntex document understanding model using the model title.</span></span>
- <span data-ttu-id="51ead-116">[Aplicar modelo](rest-applymodel-method.md): Aplica (o sincroniza) un modelo de comprensión mediante documentos entrenado a una o más bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="51ead-116">[Apply model](rest-applymodel-method.md) – Applies (or syncs) a trained document understanding model to one or more libraries.</span></span>
- <span data-ttu-id="51ead-117">[Obtener información de modelo y biblioteca](rest-getmodelandlibraryinfo.md): Obtiene información sobre un modelo y la biblioteca donde se ha aplicado.</span><span class="sxs-lookup"><span data-stu-id="51ead-117">[Get model and library information](rest-getmodelandlibraryinfo.md) – Gets information about a model and the library where it has been applied.</span></span>
- <span data-ttu-id="51ead-118">[UpdateModelSettings](rest-updatemodelsettings-method.md): Actualiza la configuración disponible de los modelos (descripción del modelo y etiqueta de retención asociada) para un modelo de comprensión mediante documentos de SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="51ead-118">[UpdateModelSettings](rest-updatemodelsettings-method.md) – Updates available models settings (associated retention label and model description) for a SharePoint Syntex document understanding model.</span></span>
- <span data-ttu-id="51ead-119">[BatchDelete](rest-batchdelete-method.md) : Quita un modelo de comprensión mediante documentos aplicado de una o más bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="51ead-119">[BatchDelete](rest-batchdelete-method.md) – Removes an applied document understanding model from one or more libraries.</span></span>
- <span data-ttu-id="51ead-120">[Crear solicitud de clasificación](rest-createclassificationrequest.md): Crea una solicitud para clasificar un archivo o archivos especificados con el modelo aplicado.</span><span class="sxs-lookup"><span data-stu-id="51ead-120">[Create classification request](rest-createclassificationrequest.md) – Creates a request to classify a specified file or files using the applied model.</span></span>

## <a name="scenarios"></a><span data-ttu-id="51ead-121">Escenarios</span><span class="sxs-lookup"><span data-stu-id="51ead-121">Scenarios</span></span>

<span data-ttu-id="51ead-122">Tenga en cuenta los ejemplos de escenarios siguientes que no son intuitivos a partir del nombre del método.</span><span class="sxs-lookup"><span data-stu-id="51ead-122">Note the following scenario examples that aren't intuitive from the method name.</span></span> <span data-ttu-id="51ead-123">Para obtener más información, consulte todos los artículos.</span><span class="sxs-lookup"><span data-stu-id="51ead-123">For more information, see each article.</span></span>

<span data-ttu-id="51ead-124">El método de creación de modelo solo crea el objeto de modelo y su tipo de contenido asociado.</span><span class="sxs-lookup"><span data-stu-id="51ead-124">The create model method only creates the model object and its associated content type.</span></span> <span data-ttu-id="51ead-125">Primero debe entrenar el modelo en el centro de contenido para que se pueda aplicar en una biblioteca.</span><span class="sxs-lookup"><span data-stu-id="51ead-125">You'll need to first train the model in the content center before it can be applied to a library.</span></span>

<span data-ttu-id="51ead-126">El método de "aplicar modelo" se usa para configurar el modelo en la biblioteca de destino para clasificar documentos y, de manera opcional, extraer información adicional.</span><span class="sxs-lookup"><span data-stu-id="51ead-126">The apply model method is used to configure the model on the target library to classify documents and optionally extract additional information.</span></span> <span data-ttu-id="51ead-127">Esta API también es compatible con la aplicación por lotes del modelo a varias bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="51ead-127">This API also supports batch applying the model to multiple libraries.</span></span>

<span data-ttu-id="51ead-128">El método de "eliminar modelo" solo quita el modelo de una o más bibliotecas donde se haya aplicado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="51ead-128">The remove model method just removes the model from one or more libraries where it was previously applied.</span></span> <span data-ttu-id="51ead-129">Si quiere eliminar el modelo, primero debe quitarse de todas las bibliotecas donde se ha aplicado.</span><span class="sxs-lookup"><span data-stu-id="51ead-129">If you want to delete the model, it must first be removed from all the libraries where it was applied.</span></span>


## <a name="see-also"></a><span data-ttu-id="51ead-130">Ver también</span><span class="sxs-lookup"><span data-stu-id="51ead-130">See also</span></span>

[<span data-ttu-id="51ead-131">Información general sobre la comprensión de documentos</span><span class="sxs-lookup"><span data-stu-id="51ead-131">Document understanding overview</span></span>](../document-understanding-overview.md)

