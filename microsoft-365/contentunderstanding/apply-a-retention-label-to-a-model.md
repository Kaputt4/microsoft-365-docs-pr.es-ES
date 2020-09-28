---
title: Aplicar una etiqueta de retención a un documento con información sobre el modelo
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
description: En este artículo se explica cómo aplicar una etiqueta de retención a un documento con información sobre el modelo
ms.openlocfilehash: 26ad64906c0e2a311d8b244e8e1596a8b975cc15
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/28/2020
ms.locfileid: "48294939"
---
# <a name="apply-a-retention-label-to-a-document-understanding-model"></a>Aplicar una etiqueta de retención a un documento con información sobre el modelo

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

Puede aplicar fácilmente una [etiqueta de retención](https://docs.microsoft.com/microsoft-365/compliance/retention) a un documento que comprenda el modelo en Microsoft SharePoint Syntex.

Las etiquetas de retención le permiten aplicar la configuración de retención a los documentos que identifican su documento que comprende los modelos.  Por ejemplo, desea que el modelo no solo identifique ningún documento de *aviso de seguro* que se cargue en la biblioteca de documentos, sino que también aplique una etiqueta de retención *empresarial* para que estos documentos no se puedan eliminar de la biblioteca de documentos durante el período de tiempo especificado (por ejemplo, los siguientes cinco meses).

Puede aplicar una etiqueta de retención preexistente en el documento que comprenda el modelo mediante la configuración de modelo en la Página principal del modelo. 

> [!Important]
> Para que las etiquetas de retención estén disponibles para aplicarse a su contenido que comprenda el modelo, deben [crearse y publicarse en el centro de cumplimiento de Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/create-apply-retention-labels#how-to-create-and-publish-retention-labels).

## <a name="to-add-a-retention-label-to-a-document-understanding-model"></a>Para agregar una etiqueta de retención a un documento que comprenda el modelo

1. En la Página principal del modelo, seleccione **configuración del modelo**.</br>
2. En **configuración de modelo**, en la sección **seguridad y cumplimiento** , seleccione el menú **etiqueta de retención** para ver una lista de las etiquetas de retención que están disponibles para que las aplique al modelo.</br>
 ![Menú de etiqueta de retención](../media/content-understanding/retention-labels-menu.png)</br> 
3. Seleccione la etiqueta de retención que desea aplicar al modelo y, a continuación, seleccione **Guardar**.</br>

Una vez aplicada la etiqueta de retención al modelo, podrá aplicarla a:
- Nueva biblioteca de documentos
- Biblioteca de documentos a la que ya se ha aplicado el modelo
 
## <a name="apply-the-retention-label-to-a-document-library-to-which-the-model-is-already-applied"></a>Aplicar la etiqueta de retención a una biblioteca de documentos a la que ya se ha aplicado el modelo

Si ya se ha aplicado el modelo de conocimiento del documento a una biblioteca de documentos, puede hacer lo siguiente para sincronizar la actualización de la etiqueta de retención para aplicarla a la biblioteca de documentos:</br>

1. En la Página principal del modelo, en la sección **bibliotecas con este modelo** , seleccione la biblioteca de documentos a la que desea aplicar la actualización de la etiqueta de retención. </br> 
2. Seleccione **sincronizar**. </br>
 ![Modelo de sincronización](../media/content-understanding/sync-model.png)</br> 


Después de aplicar la actualización y sincronizarla con el modelo, puede confirmar que se ha aplicado haciendo lo siguiente:

1. En el centro de contenido, en la sección **bibliotecas con este modelo** , haga clic en la biblioteca a la que se ha aplicado el modelo actualizado. </br>
2. En la vista de la biblioteca de documentos, seleccione el icono de información para comprobar las propiedades del modelo.</br>  
3. En la lista **modelos activos** , seleccione el modelo actualizado.</br>
4. En la sección **etiqueta de retención** verá el nombre de la etiqueta de retención aplicada.</br>


En la página de vista del modelo en la biblioteca de documentos, se mostrará una nueva columna de **etiqueta de retención** .  A medida que el modelo clasifica los archivos que identifica como pertenecientes a su tipo de contenido y los enumera en la vista de biblioteca, la columna etiqueta de retención también mostrará el nombre de la etiqueta de retención que se le ha aplicado a través del modelo.


Por ejemplo, todos los documentos de un *aviso de seguro* que identifique el modelo también tendrán la etiqueta de retención *empresarial* aplicada, evitando que se eliminen de la biblioteca de documentos durante cinco meses. Si se realiza un intento de eliminar el archivo de la biblioteca de documentos, se mostrará un error que indica que no está permitido debido a la etiqueta de retención aplicada.

## <a name="see-also"></a>Consulte también
[Crear un clasificador](create-a-classifier.md)</br>
[Crear un extractor](create-an-extractor.md)</br>
[Información general sobre el documento](document-understanding-overview.md)</br>
[Crear un modelo de procesamiento de formularios](create-a-form-processing-model.md)  
