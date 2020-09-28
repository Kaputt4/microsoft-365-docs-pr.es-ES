---
title: Aprovechar la taxonomía del almacén de términos al crear un extractor
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 10/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Aproveche la taxonomía del almacén de términos al crear un extractor en el documento información sobre el modelo en Microsoft SharePoint Syntex.
ms.openlocfilehash: 94f7a0389d2f06e0f8c1a60a341a02e43dfb2071
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/28/2020
ms.locfileid: "48296010"
---
# <a name="leverage-term-store-taxonomy-when-creating-an-extractor"></a><span data-ttu-id="a0bee-103">Aprovechar la taxonomía del almacén de términos al crear un extractor</span><span class="sxs-lookup"><span data-stu-id="a0bee-103">Leverage term store taxonomy when creating an extractor</span></span>


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

<span data-ttu-id="a0bee-104">Al crear un extractor en el documento con información sobre el modelo en SharePoint Syntex, puede aprovechar la taxonomía del almacén de términos de los [servicios de metadatos administrados](https://docs.microsoft.com/sharepoint/managed-metadata#terms) para mostrar los términos preferidos de los datos que extrae.</span><span class="sxs-lookup"><span data-stu-id="a0bee-104">When you create an extractor in your document understanding model in SharePoint Syntex, you can take advantage of [Managed Metadata services](https://docs.microsoft.com/sharepoint/managed-metadata#terms) term store taxonomy to display preferred terms for data that you extract.</span></span>  

<span data-ttu-id="a0bee-105">Por ejemplo, el modelo identifica y clasifica todos los documentos de **contrato** que se cargan en la biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="a0bee-105">As an example, your model identifies and classifies all **Contract** documents that are uploaded to the document library.</span></span>  <span data-ttu-id="a0bee-106">Además, el modelo también extrae un valor de **servicio de contrato** de cada contrato y lo muestra en una columna en la vista de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="a0bee-106">Additionally, the model also extracts a **Contract Service** value from each contract, and will display it in a column in your library view.</span></span> <span data-ttu-id="a0bee-107">Entre los distintos valores de servicios de contrato en los contratos, hay varios valores anteriores que su compañía ya no utiliza y a los que se les ha cambiado el nombre.</span><span class="sxs-lookup"><span data-stu-id="a0bee-107">Among the various Contract Services values in the contracts, there are several older values that your company no longer uses and have been renamed.</span></span> <span data-ttu-id="a0bee-108">Por ejemplo, todas las referencias a los términos *diseño*, *gráficos*o servicios del contrato de *topografía* deben llamarse ahora *creativo*.</span><span class="sxs-lookup"><span data-stu-id="a0bee-108">For example, all references to the terms *Design*, *Graphics*, or *Topography* contract services should now be called *Creative*.</span></span> <span data-ttu-id="a0bee-109">Siempre que el modelo extrae uno de los términos obsoletos de un documento de contrato, desea que muestre el término actual-creativo-en la vista de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="a0bee-109">Whenever your model extracts one of the outdated terms from a contract document, you want it to display the current term - Creative - in your library view.</span></span> <span data-ttu-id="a0bee-110">En el ejemplo siguiente, al entrenar el modelo, vemos que un documento de muestra contiene el período de *diseño*obsoleto.</span><span class="sxs-lookup"><span data-stu-id="a0bee-110">In the example below, while training the model we see that one sample document contains the outdated term of *Design*.</span></span>

   ![Almacén de términos](../media/content-understanding/design.png)</br>


## <a name="term-set-synonyms"></a><span data-ttu-id="a0bee-112">Sinónimos del conjunto de términos</span><span class="sxs-lookup"><span data-stu-id="a0bee-112">Term set synonyms</span></span> 

<span data-ttu-id="a0bee-113">Los conjuntos de términos se configuran en el almacén de términos de servicios de metadatos administrados en el centro de administración de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a0bee-113">Term sets are configured in the Managed Metadata services term store in the SharePoint admin center.</span></span> <span data-ttu-id="a0bee-114">En el ejemplo siguiente, el [conjunto de términos](https://docs.microsoft.com/sharepoint/managed-metadata#term-set) de *servicios de contrato* está configurado para incluir una serie de términos, incluido el *creativo*.</span><span class="sxs-lookup"><span data-stu-id="a0bee-114">In the the example below, the *Contract Services* [term set](https://docs.microsoft.com/sharepoint/managed-metadata#term-set) is configured to include a number of terms, including *Creative*.</span></span>  <span data-ttu-id="a0bee-115">Los detalles de este muestran que el término tiene tres sinónimos (*diseño*, *gráficos*y *topografía*) y que los sinónimos se deben traducir a *creativo*.</span><span class="sxs-lookup"><span data-stu-id="a0bee-115">The details for it show that the term has three synonyms (*Design*, *Graphics*, and *Topography*) and the synonyms should be translated to *Creative*.</span></span>

   ![Conjunto de términos](../media/content-understanding/term-store.png)</br>

<span data-ttu-id="a0bee-117"><Mike, aquí es donde no estoy seguro de cómo describir esto.</span><span class="sxs-lookup"><span data-stu-id="a0bee-117"><Mike, here is where I am unsure about how to describe this.</span></span>  <span data-ttu-id="a0bee-118">Qué acción indica al modelo que cuando se crea un extractor para extraer y mostrar una columna de servicios de contrato, ¿cómo se marca dicha columna para usar el conjunto de términos de metadatos administrados para servicios creativos? ></span><span class="sxs-lookup"><span data-stu-id="a0bee-118">What action tells the model that when I create an extractor to extract and display a Contract Services column, how is that column "marked" to use the managed metadata term set for Creative Services?></span></span>

## <a name="configure-your-document-library-site-column-for-a-managed-metadata-field"></a><span data-ttu-id="a0bee-119">Configurar la columna de sitio de la biblioteca de documentos para un campo de metadatos administrados</span><span class="sxs-lookup"><span data-stu-id="a0bee-119">Configure your document library site column for a managed metadata field</span></span>


   ![Crear metadatos administrados](../media/content-understanding/creative.png)</br>

## <a name="see-also"></a><span data-ttu-id="a0bee-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a0bee-121">See Also</span></span>
[<span data-ttu-id="a0bee-122">Introducción a los metadatos administrados</span><span class="sxs-lookup"><span data-stu-id="a0bee-122">Introduction to Managed Metadata</span></span>](https://docs.microsoft.com/sharepoint/managed-metadata#terms)</br>
[<span data-ttu-id="a0bee-123">Crear un extractor</span><span class="sxs-lookup"><span data-stu-id="a0bee-123">Create an extractor</span></span>](create-an-extractor.md)</br>
[<span data-ttu-id="a0bee-124">Crear una columna de metadatos administrados</span><span class="sxs-lookup"><span data-stu-id="a0bee-124">Create a managed metadata column</span></span>](https://support.microsoft.com/office/create-a-managed-metadata-column-8fad9e35-a618-4400-b3c7-46f02785d27f?redirectSourcePath=%252farticle%252fc2a06717-8105-4aea-890d-3082853ab7b7&ui=en-US&rs=en-US&ad=US)</br>





