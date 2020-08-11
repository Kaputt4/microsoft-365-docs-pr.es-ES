---
title: Aplicación de un documento que comprende el modelo a una biblioteca de documentos (versión preliminar)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Obtenga información sobre cómo aplicar un modelo publicado a una biblioteca de documentos de SharePoint.
ms.openlocfilehash: 0658710704273ed04e9f2067413d1141773ef4aa
ms.sourcegitcommit: a3a5dc541b0c971608cc86ef480509c25a13ca60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/10/2020
ms.locfileid: "46612685"
---
# <a name="apply-a-document-understanding-model-preview"></a>Aplicación de un modelo de comprensión de documentos (versión preliminar)

> [!Note] 
> El contenido de este artículo es para la versión preliminar privada de Project Cortex. [Obtenga más información sobre Project Cortex](https://aka.ms/projectcortex).

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

Después de publicar el documento con información sobre el modelo, puede aplicarlo a una biblioteca de documentos de SharePoint en su inquilino de Microsoft 365.

> [!Note]
> Solo podrá aplicar el modelo a las bibliotecas de documentos a las que tiene acceso.


## <a name="apply-your-model-to-a-document-library"></a>Aplique el modelo a una biblioteca de documentos.

Para aplicar el modelo a una biblioteca de documentos de SharePoint:

1. En la Página principal del modelo, en el mosaico **aplicar modelo a bibliotecas** , seleccione **publicar modelo**. O bien, puede seleccionar **+ Agregar biblioteca** en la sección **bibliotecas con este modelo** . </br>

    ![Agregar un modelo a la biblioteca](../media/content-understanding/apply-to-library.png)</br>

2. A continuación, puede seleccionar el sitio de SharePoint que contiene la biblioteca de documentos a la que desea aplicar el modelo. Si el sitio no aparece en la lista, use el cuadro de búsqueda para buscarlo.</br>

    ![Seleccionar un sitio](../media/content-understanding/site-search.png)</br>

    > [!Note]
    > Debe tener permisos de *Administración de listas* o derechos de *edición* en la biblioteca de documentos a la que va a aplicar el modelo.</br>

3. Después de seleccionar el sitio, debe seleccionar la biblioteca de documentos a la que desea aplicar el modelo. En el ejemplo, se selecciona la biblioteca de documentos *documentos* del sitio de *seguimiento de casos de Contoso* .</br>

    ![Selección de una biblioteca de documentos](../media/content-understanding/select-doc-library.png)</br>

4. Como el modelo está asociado a un tipo de contenido, cuando se aplica a la biblioteca, se creará una vista para el tipo de contenido con las etiquetas que se extrajo Mostrar como columnas. De forma predeterminada, esta vista será la vista predeterminada de la biblioteca, pero, opcionalmente, puede optar por no tenerla como la vista predeterminada seleccionando **Configuración avanzada** y deseleccionando **establecer esta nueva vista como predeterminada**.</br>

    ![Vista de biblioteca](../media/content-understanding/library-view.png)</br>

5. Seleccione **Agregar** para aplicar el modelo a la biblioteca. 
6. En la Página principal del modelo, en la sección **bibliotecas con este modelo** , verá la dirección URL del sitio de SharePoint que se muestra.</br>

    ![Vista de biblioteca](../media/content-understanding/selected-library.png)</br>

7. Vaya a la biblioteca de documentos y asegúrese de que se encuentra en la vista de la biblioteca de documentos del modelo. Observará que si selecciona el botón información junto al nombre de la biblioteca de documentos, un mensaje le indicará que el modelo se ha aplicado a la biblioteca de documentos.

    ![Vista de biblioteca](../media/content-understanding/info-du.png)</br> 


Después de aplicar el modelo a la biblioteca de documentos, puede empezar a cargar los documentos en el sitio y ver los resultados.

El modelo identificará los archivos con el tipo de contenido asociado al modelo y los mostrará en la vista. Si el modelo tiene algún extractor, la vista mostrará columnas para los datos que va a extraer de cada archivo.

### <a name="apply-the-model-to-files-already-in-the-document-library"></a>Aplicar el modelo a los archivos que ya se encuentran en la biblioteca de documentos

Mientras que un modelo aplicado procesará todos los archivos cargados en la biblioteca de documentos después de su aplicación, también puede hacer lo siguiente para ejecutar el modelo en archivos que ya existían en la biblioteca de documentos antes del modelo que se aplica:

1. En la biblioteca de documentos, seleccione los archivos que desea que procese el modelo.
2. Después de seleccionar los archivos, la **clasificación y la extracción** aparecerán en la cinta de la biblioteca de documentos. Seleccione **clasificar y extraer**.
3. Los archivos seleccionados se agregarán a la cola para ser procesados.

      ![Clasificar y extraer](../media/content-understanding/extract-classify.png)</br> 





## <a name="see-also"></a>Vea también
[Crear un clasificador](create-a-classifier.md)</br>
[Crear un extractor](create-an-extractor.md)</br>
[Información general sobre el documento](document-understanding-overview.md)</br>
[Crear un modelo de procesamiento de formularios](create-a-form-processing-model.md)  




