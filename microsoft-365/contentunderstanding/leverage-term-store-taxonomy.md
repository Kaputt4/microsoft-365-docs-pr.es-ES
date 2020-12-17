---
title: Aprovechar la taxonomía del almacén de términos al crear un extractor
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: Priority
description: Saque el máximo partido de la taxonomía al crear un extractor en el modelo de comprensión de documentos en Microsoft SharePoint Syntex.
ms.openlocfilehash: a8078e6ff2d2ecd0f98c22b602a54675f7d62816
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/17/2020
ms.locfileid: "49701100"
---
# <a name="leverage-term-store-taxonomy-when-creating-an-extractor"></a><span data-ttu-id="54f20-103">Aprovechar la taxonomía del almacén de términos al crear un extractor</span><span class="sxs-lookup"><span data-stu-id="54f20-103">Leverage term store taxonomy when creating an extractor</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GpJJ]  

</br>

<span data-ttu-id="54f20-104">Cuando se crea un extractor en el modelo de comprensión de documentos en SharePoint Syntex, puede aprovechar la taxonomía del almacén de términos de los [Servicios de metadatos administrados](https://docs.microsoft.com/sharepoint/managed-metadata#terms) para mostrar los términos preferidos para los datos que extraerá.</span><span class="sxs-lookup"><span data-stu-id="54f20-104">When you create an extractor in your document understanding model using SharePoint Syntex, you can take advantage of [Managed Metadata services](https://docs.microsoft.com/sharepoint/managed-metadata#terms) term store taxonomy to display preferred terms for data that you extract.</span></span>  

<span data-ttu-id="54f20-105">Por ejemplo, el modelo identifica y clasifica todos los documentos de **Contrato** cargados en la biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="54f20-105">As an example, your model identifies and classifies all **Contract** documents that are uploaded to the document library.</span></span>  <span data-ttu-id="54f20-106">Además, el modelo también extrae un valor de **Servicio de contrato** de cada contrato, y lo mostrará en una columna de la vista de la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="54f20-106">Additionally, the model also extracts a **Contract Service** value from each contract, and will display it in a column in your library view.</span></span> <span data-ttu-id="54f20-107">Entre los distintos valores de Servicios de contrato en los contratos, hay varios valores anteriores que la empresa ya no usa y a los que se les ha cambiado el nombre.</span><span class="sxs-lookup"><span data-stu-id="54f20-107">Among the various Contract Services values in the contracts, there are several older values that your company no longer uses and have been renamed.</span></span> <span data-ttu-id="54f20-108">Por ejemplo, todas las referencias a los términos de los servicios de contratos *Diseño*, *Gráficos* o *Topografía* ahora deberían llamarse *Creativo*.</span><span class="sxs-lookup"><span data-stu-id="54f20-108">For example, all references to the terms *Design*, *Graphics*, or *Topography* contract services should now be called *Creative*.</span></span> <span data-ttu-id="54f20-109">Siempre que el modelo extrae uno de los términos desactualizado de un documento de contrato, quiere que muestre el término actual, "Creativo", en la vista de la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="54f20-109">Whenever your model extracts one of the outdated terms from a contract document, you want it to display the current term - Creative - in your library view.</span></span> <span data-ttu-id="54f20-110">En el ejemplo siguiente, al entrenar el modelo, observamos que un documento de muestra contiene el término desactualizado de *Diseño*.</span><span class="sxs-lookup"><span data-stu-id="54f20-110">In the example below, while training the model we see that one sample document contains the outdated term of *Design*.</span></span>

   ![Almacén de términos](../media/content-understanding/design.png)</br>

## <a name="use-a-managed-metadata-column-in-your-extractor"></a><span data-ttu-id="54f20-112">Usar una columna de metadatos administrados en el extractor</span><span class="sxs-lookup"><span data-stu-id="54f20-112">Use a Managed metadata column in your extractor</span></span>

<span data-ttu-id="54f20-113">Los conjuntos de términos están configurados en el almacén de términos de los servicios de metadatos administrados (MMS) en el Centro de Administración de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="54f20-113">Term sets are configured in the Managed Metadata services (MMS) term store in the SharePoint admin center.</span></span> <span data-ttu-id="54f20-114">En el ejemplo siguiente, el *conjunto de términos* de [Servicios de contrato](https://docs.microsoft.com/sharepoint/managed-metadata#term-set) se configura para incluir un número de términos, incluido *Creativo*.</span><span class="sxs-lookup"><span data-stu-id="54f20-114">In the the example below, the *Contract Services* [term set](https://docs.microsoft.com/sharepoint/managed-metadata#term-set) is configured to include a number of terms, including *Creative*.</span></span>  <span data-ttu-id="54f20-115">En los detalles, se muestra que el término tiene tres sinónimos (*Diseño*, *Gráficos* y *Topografía*) y los sinónimos se deberían traducir como *Creativo*.</span><span class="sxs-lookup"><span data-stu-id="54f20-115">The details for it show that the term has three synonyms (*Design*, *Graphics*, and *Topography*) and the synonyms should be translated to *Creative*.</span></span> 

   ![Conjunto de términos](../media/content-understanding/term-store.png)</br>

> [!NOTE]
>  <span data-ttu-id="54f20-117">Los conjuntos de términos son configurados como globales en el campo MMS del centro de contenido.</span><span class="sxs-lookup"><span data-stu-id="54f20-117">Term sets are configured as global in the MMS field of the content center.</span></span>

<span data-ttu-id="54f20-118">Puede haber varios motivos por los que quiera usar un sinónimo en el conjunto de términos.</span><span class="sxs-lookup"><span data-stu-id="54f20-118">There could be a number of reasons why you might want to use a synonym in your term set.</span></span> <span data-ttu-id="54f20-119">Por ejemplo, es posible que haya términos no actualizados, términos con nombre cambiado o variaciones en la denominación entre los departamentos de su organización.</span><span class="sxs-lookup"><span data-stu-id="54f20-119">For example, there could be outdated terms, renamed terms, or variations between your organizations departments on naming.</span></span>

<span data-ttu-id="54f20-120">Para que el campo de metadatos administrados esté disponible para que lo seleccione cuando cree el extractor en el modelo, debe [agregarlo como una columna de sitio de metadatos administrados](https://support.microsoft.com/office/8fad9e35-a618-4400-b3c7-46f02785d27f).</span><span class="sxs-lookup"><span data-stu-id="54f20-120">To make the managed metadata field available for you to select when you create your extractor in your model, you need to [add it as a managed-metadata site column](https://support.microsoft.com/office/8fad9e35-a618-4400-b3c7-46f02785d27f).</span></span> <span data-ttu-id="54f20-121">Después de agregar la columna del sitio, estará disponible para que la seleccione cuando cree el extractor para el modelo.</span><span class="sxs-lookup"><span data-stu-id="54f20-121">After you add the site column, it will be available for you to select when you create the extractor for your model.</span></span>

   ![Servicio de contrato](../media/content-understanding/contract-services.png)</br>


<span data-ttu-id="54f20-123">Después de aplicar el modelo a la biblioteca de documentos, cuando los documentos se carguen en la biblioteca, en la columna *Servicios creativos* se mostrará el término preferido (*Creativo*) cuando el extractor encuentre cualquiera de los valores de los sinónimos (*Diseño*, *Gráficos* y *Topografía*).</span><span class="sxs-lookup"><span data-stu-id="54f20-123">After applying your model to the document library, when documents are uploaded to library, the *Creative Services* column will display the preferred term (*Creative*) when the extractor finds any of the synonym values (*Design*, *Graphics*, and *Topography*).</span></span>

   ![Columna de servicio de contrato](../media/content-understanding/creative.png)</br>


## <a name="see-also"></a><span data-ttu-id="54f20-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="54f20-125">See Also</span></span>
[<span data-ttu-id="54f20-126">Introducción a los metadatos administrados</span><span class="sxs-lookup"><span data-stu-id="54f20-126">Introduction to Managed Metadata</span></span>](https://docs.microsoft.com/sharepoint/managed-metadata#terms)

[<span data-ttu-id="54f20-127">Crear un extractor</span><span class="sxs-lookup"><span data-stu-id="54f20-127">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="54f20-128">Crear una columna de metadatos administrados</span><span class="sxs-lookup"><span data-stu-id="54f20-128">Create a managed metadata column</span></span>](https://support.microsoft.com/office/create-a-managed-metadata-column-8fad9e35-a618-4400-b3c7-46f02785d27f?redirectSourcePath=%252farticle%252fc2a06717-8105-4aea-890d-3082853ab7b7&ui=en-US&rs=en-US&ad=US)





