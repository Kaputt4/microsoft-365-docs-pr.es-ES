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
# <a name="leverage-term-store-taxonomy-when-creating-an-extractor"></a>Aprovechar la taxonomía del almacén de términos al crear un extractor


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

Al crear un extractor en el documento con información sobre el modelo en SharePoint Syntex, puede aprovechar la taxonomía del almacén de términos de los [servicios de metadatos administrados](https://docs.microsoft.com/sharepoint/managed-metadata#terms) para mostrar los términos preferidos de los datos que extrae.  

Por ejemplo, el modelo identifica y clasifica todos los documentos de **contrato** que se cargan en la biblioteca de documentos.  Además, el modelo también extrae un valor de **servicio de contrato** de cada contrato y lo muestra en una columna en la vista de biblioteca. Entre los distintos valores de servicios de contrato en los contratos, hay varios valores anteriores que su compañía ya no utiliza y a los que se les ha cambiado el nombre. Por ejemplo, todas las referencias a los términos *diseño*, *gráficos*o servicios del contrato de *topografía* deben llamarse ahora *creativo*. Siempre que el modelo extrae uno de los términos obsoletos de un documento de contrato, desea que muestre el término actual-creativo-en la vista de biblioteca. En el ejemplo siguiente, al entrenar el modelo, vemos que un documento de muestra contiene el período de *diseño*obsoleto.

   ![Almacén de términos](../media/content-understanding/design.png)</br>


## <a name="term-set-synonyms"></a>Sinónimos del conjunto de términos 

Los conjuntos de términos se configuran en el almacén de términos de servicios de metadatos administrados en el centro de administración de SharePoint. En el ejemplo siguiente, el [conjunto de términos](https://docs.microsoft.com/sharepoint/managed-metadata#term-set) de *servicios de contrato* está configurado para incluir una serie de términos, incluido el *creativo*.  Los detalles de este muestran que el término tiene tres sinónimos (*diseño*, *gráficos*y *topografía*) y que los sinónimos se deben traducir a *creativo*.

   ![Conjunto de términos](../media/content-understanding/term-store.png)</br>

<Mike, aquí es donde no estoy seguro de cómo describir esto.  Qué acción indica al modelo que cuando se crea un extractor para extraer y mostrar una columna de servicios de contrato, ¿cómo se marca dicha columna para usar el conjunto de términos de metadatos administrados para servicios creativos? >

## <a name="configure-your-document-library-site-column-for-a-managed-metadata-field"></a>Configurar la columna de sitio de la biblioteca de documentos para un campo de metadatos administrados


   ![Crear metadatos administrados](../media/content-understanding/creative.png)</br>

## <a name="see-also"></a>Consulte también
[Introducción a los metadatos administrados](https://docs.microsoft.com/sharepoint/managed-metadata#terms)</br>
[Crear un extractor](create-an-extractor.md)</br>
[Crear una columna de metadatos administrados](https://support.microsoft.com/office/create-a-managed-metadata-column-8fad9e35-a618-4400-b3c7-46f02785d27f?redirectSourcePath=%252farticle%252fc2a06717-8105-4aea-890d-3082853ab7b7&ui=en-US&rs=en-US&ad=US)</br>





