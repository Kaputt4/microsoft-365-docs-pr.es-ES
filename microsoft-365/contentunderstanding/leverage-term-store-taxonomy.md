---
title: Aprovechar la taxonomía del almacén de términos al crear un extractor
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Priority
description: Saque el máximo partido de la taxonomía al crear un extractor en el modelo de comprensión de documentos en Microsoft SharePoint Syntex.
ms.openlocfilehash: f7219f6facc1d29242f7bd52743da92e13de3b89
ms.sourcegitcommit: 3f8e573244bc082518125e339a385c41ef6ee800
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2020
ms.locfileid: "48337282"
---
# <a name="leverage-term-store-taxonomy-when-creating-an-extractor"></a>Aprovechar la taxonomía del almacén de términos al crear un extractor

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GpJJ]  

</br>


Cuando se crea un extractor en el modelo de comprensión de documentos en SharePoint Syntex, puede aprovechar la taxonomía del almacén de términos de los [servicios de metadatos administrados](https://docs.microsoft.com/sharepoint/managed-metadata#terms) para mostrar los términos preferidos para los datos que extraerá.  

Por ejemplo, el modelo identifica y clasifica todos los documentos de **Contrato** cargados en la biblioteca de documentos.  Además, el modelo también extrae un valor de **Servicio de contrato** de cada contrato, y lo mostrará en una columna de la vista de la biblioteca. Entre los distintos valores de Servicios de contrato en los contratos, hay varios valores anteriores que la empresa ya no usa y a los que se les ha cambiado el nombre. Por ejemplo, todas las referencias a los términos de los servicios de contratos *Diseño*, *Gráficos* o *Topografía* ahora deberían llamarse *Creativo*. Siempre que el modelo extrae uno de los términos desactualizado de un documento de contrato, quiere que muestre el término actual, "Creativo", en la vista de la biblioteca. En el ejemplo siguiente, al entrenar el modelo, observamos que un documento de muestra contiene el término desactualizado de *Diseño*.

   ![Almacén de términos](../media/content-understanding/design.png)</br>


## <a name="use-a-managed-metadata-column-in-your-extractor"></a>Usar una columna de metadatos administrados en el extractor

Los conjuntos de términos se configuran en el almacén de términos de servicios de metadatos administrados en el Centro de administración de SharePoint. En el ejemplo siguiente, el *conjunto de términos* de [Servicios de contrato](https://docs.microsoft.com/sharepoint/managed-metadata#term-set) se configura para incluir un número de términos, incluido *Creativo*.  En los detalles, se muestra que el término tiene tres sinónimos (*Diseño*, *Gráficos* y *Topografía*) y los sinónimos se deberían traducir como *Creativo*. 

   ![Conjunto de términos](../media/content-understanding/term-store.png)</br>

Puede haber varios motivos por los que quiera usar un sinónimo en el conjunto de términos. Por ejemplo, es posible que haya términos no actualizados, términos con nombre cambiado o variaciones en la denominación entre los departamentos de su organización.

Para que el campo de metadatos administrados esté disponible para que lo seleccione cuando cree el extractor en el modelo, debe [agregarlo como una columna de sitio de metadatos administrados](https://support.microsoft.com/office/8fad9e35-a618-4400-b3c7-46f02785d27f). Después de agregar la columna del sitio, estará disponible para que la seleccione cuando cree el extractor para el modelo.

   ![Servicio de contrato](../media/content-understanding/contract-services.png)</br>


Después de aplicar el modelo a la biblioteca de documentos, cuando los documentos se carguen en la biblioteca, en la columna *Servicios creativos* se mostrará el término preferido (*Creativo*) cuando el extractor encuentre cualquiera de los valores de los sinónimos (*Diseño*, *Gráficos* y *Topografía*).

   ![Columna de servicio de contrato](../media/content-understanding/creative.png)</br>


## <a name="see-also"></a>Consulte también
[Introducción a los metadatos administrados](https://docs.microsoft.com/sharepoint/managed-metadata#terms)

[Crear un extractor](create-an-extractor.md)

[Crear una columna de metadatos administrados](https://support.microsoft.com/office/create-a-managed-metadata-column-8fad9e35-a618-4400-b3c7-46f02785d27f?redirectSourcePath=%252farticle%252fc2a06717-8105-4aea-890d-3082853ab7b7&ui=en-US&rs=en-US&ad=US)





