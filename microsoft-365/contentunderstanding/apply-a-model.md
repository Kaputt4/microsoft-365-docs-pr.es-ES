---
title: Aplicar un modelo de comprensión mediante documentos a una biblioteca de documentos
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Priority
description: Aprenda a aplicar un modelo publicado a una biblioteca de documentos de SharePoint
ms.openlocfilehash: 8b7d6cf21f422ba54933c2d3ac29b4b34171059e
ms.sourcegitcommit: f7ca339bdcad38796c550064fb152ea09687d0f3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2020
ms.locfileid: "48322158"
---
# <a name="apply-a-document-understanding-model-in-microsoft-sharepoint-syntex"></a>Aplicar un modelo de comprensión mediante documentos en la sintaxis de Microsoft SharePoint

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

Después de publicar el modelo de comprensión mediante documentos, puede aplicarlo a una o más bibliotecas de documentos de SharePoint en su espacio empresarial de Microsoft 365.

> [!NOTE]
> Solo puede aplicar el modelo a las bibliotecas de documentos a las que tenga acceso.


## <a name="apply-your-model-to-a-document-library"></a>Aplique el modelo a una biblioteca de documentos.

Para aplicar el modelo a una biblioteca de documentos de SharePoint:

1. En la página principal del modelo, en el cuadro **Aplicar modelo a las bibliotecas**, seleccione **Publicar modelo**. También puede seleccionar **+Agregar biblioteca** en la sección **Bibliotecas con este modelo**. </br>

    ![Agregar un modelo a la biblioteca](../media/content-understanding/apply-to-library.png)</br>

2. Después, puede seleccionar el sitio de SharePoint que contiene la biblioteca de documentos a la que desea aplicar el modelo. Si el sitio no aparece en la lista, use el cuadro de búsqueda para encontrarlo.</br>

    ![Seleccionar un sitio](../media/content-understanding/site-search.png)</br>

    > [!NOTE]
    > Debe tener permisos de *Administración de lista* o de *Edición* en la biblioteca de documentos a la que va a aplicar el modelo.</br>

3. Después de seleccionar el sitio, seleccione la biblioteca de documentos a la que quiere aplicar el modelo. En el ejemplo, seleccione la biblioteca de documentos *Documentos* en el sitio de *Seguimiento de casos de Contoso*.</br>

    ![Seleccionar biblioteca de documentos](../media/content-understanding/select-doc-library.png)</br>

4. Como el modelo está asociado a un tipo de contenido, cuando lo aplique a la biblioteca, se agregará el tipo de contenido y su vista con las etiquetas que extrajo mostrándolo como columnas. De forma predeterminada, esta vista es la vista predeterminada de la biblioteca, pero si lo prefiere, puede elegir que no sea la vista predeterminada seleccionando **Configuración avanzada** y anulando la selección **Establecer esta vista nueva como predeterminada**.</br>

    ![Vista de biblioteca](../media/content-understanding/library-view.png)</br>

5. Seleccione **Agregar** para aplicar el modelo a la biblioteca. 
6. En la página principal del modelo, en la sección **Bibliotecas con este modelo**, debe ver la dirección URL del sitio de SharePoint que se muestra.</br>

    ![Biblioteca seleccionada](../media/content-understanding/selected-library.png)</br>

7. Vaya a la biblioteca de documentos y asegúrese de estar en la vista de biblioteca de documentos del modelo. Tenga en cuenta que si selecciona el botón de información junto al nombre de la biblioteca de documentos, se mostrará un mensaje que indica que su modelo se ha aplicado a la biblioteca de documentos.

    ![Vista de información](../media/content-understanding/info-du.png)</br> 


Después de aplicar el modelo a la biblioteca de documentos, puede iniciar la carga de documentos en el sitio y ver los resultados.

El modelo identifica los archivos con el tipo de contenido asociado al modelo y los enumera en la vista. Si su modelo tiene algún extractor, la vista muestra columnas para los datos que se extraen de cada archivo.

### <a name="apply-the-model-to-files-already-in-the-document-library"></a>Aplicar el modelo a los archivos que ya se encuentren en la biblioteca de documentos

Si bien un modelo aplicado procesa todos los archivos cargados en la biblioteca de documentos después de su aplicación, también puede hacer lo siguiente para ejecutar el modelo en archivos que ya existen en la biblioteca de documentos antes de que se aplique el modelo:

1. En la biblioteca de documentos, seleccione los archivos que quiere que sean procesados por su modelo.
2. Después de seleccionar los archivos, en la cinta de la biblioteca de documentos se mostrará **Clasificar y extraer**. Seleccione **Clasificar y extraer**.
3. Los archivos que seleccionó se agregarán a la cola para su procesamiento.

      ![Clasificar y extraer](../media/content-understanding/extract-classify.png)</br> 

## <a name="see-also"></a>Consulte también
[Crear un clasificador](create-a-classifier.md)

[Crear un extractor](create-an-extractor.md)

[Información general de la comprensión mediante documentos ](document-understanding-overview.md)

[Crear un modelo de procesamiento de formularios](create-a-form-processing-model.md)  
