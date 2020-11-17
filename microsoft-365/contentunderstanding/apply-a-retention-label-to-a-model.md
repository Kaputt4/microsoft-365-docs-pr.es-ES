---
title: Aplicar una etiqueta de retención a un modelo de comprensión mediante documentos
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: Priority
description: Este artículo muestra cómo aplicar una etiqueta de retención a un modelo de comprensión mediante documentos
ms.openlocfilehash: 2e6d300b63a173d01488406485cffa44fab4278e
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087480"
---
# <a name="apply-a-retention-label-to-a-document-understanding-model"></a>Aplicar una etiqueta de retención a un modelo de comprensión mediante documentos

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GydO]  

</br>


Puede aplicar fácilmente una [etiqueta de retención](https://docs.microsoft.com/microsoft-365/compliance/retention) a un modelo de comprensión mediante documentos en Microsoft SharePoint Syntex.

Las etiquetas de retención le permiten aplicar la configuración de retención a los documentos que identifican sus modelos de comprensión mediante documentos.  Por ejemplo, si desea que el modelo no solo identifique cualquier documento de *Notificación de seguros* cargados en la biblioteca de documentos, sino que también pueda aplicar una etiqueta de retención de *negocios* para que estos documentos no se puedan eliminar de la biblioteca de documentos durante el período de tiempo especificado (por ejemplo, los próximos cinco meses).

Puede aplicar una etiqueta de retención preexistente al modelo de comprensión mediante documentos en la página principal del modelo. 

> [!Important]
> Para que las etiquetas de retención estén disponibles para aplicarlas a su modelo de comprensión mediante documentos, deben [crearse y publicarse en el Centro de cumplimiento de Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/create-apply-retention-labels#how-to-create-and-publish-retention-labels).

## <a name="to-add-a-retention-label-to-a-document-understanding-model"></a>Aplicar una etiqueta de retención a un modelo de comprensión mediante documentos

1. En la página principal del modelo, seleccione **Configuración del modelo**.</br>
2. En **Configuración del modelo**, en la sección **Seguridad y cumplimiento**, seleccione el menú **Etiqueta de retención** para ver una lista de las etiquetas de retención disponibles para que se apliquen al modelo.</br>
 ![Menú Etiqueta de retención](../media/content-understanding/retention-labels-menu.png)</br> 
3. Seleccione la etiqueta de retención que desea aplicar al modelo y, a continuación, seleccione **Guardar**.</br>

Después de aplicar la etiqueta de retención al modelo, podrá aplicarla a:
- una nueva biblioteca de documentos y
- una biblioteca de documentos en la que ya se aplica el modelo.
 
## <a name="apply-the-retention-label-to-a-document-library-to-which-the-model-is-already-applied"></a>Aplicar la etiqueta de retención a la biblioteca de documentos en la que ya se aplica el modelo

Si ya se ha aplicado el modelo de comprensión mediante documentos a una biblioteca de documentos, puede hacer lo siguiente para sincronizar la actualización de la etiqueta de retención y aplicarla en la biblioteca de documentos:</br>

1. En la Página principal del modelo, en la sección **Bibliotecas con este modelo**, seleccione la biblioteca de documentos a la que quiera aplicar la actualización de la etiqueta de retención. </br> 
2. Seleccione **Sincronizar**. </br>
 ![Modelo de sincronización](../media/content-understanding/sync-model.png)</br> 


Después de aplicar la actualización y sincronizarla con el modelo, puede confirmar que se ha aplicado haciendo lo siguiente:

1. En el centro de contenido, en la sección **Bibliotecas con este modelo**, haga clic en la biblioteca a la que se ha aplicado el modelo actualizado. </br>
2. En la vista de la biblioteca de documentos, seleccione el icono de información para ver las propiedades del modelo.</br>  
3. En la lista **Modelos activos**, seleccione el modelo actualizado.</br>
4. En la sección **Etiqueta de retención** verá el nombre de la etiqueta de retención aplicada.</br>


En la página de vista del modelo de la biblioteca de documentos, se mostrará una nueva columna de la **Etiqueta de retención**.  A medida que el modelo clasifica los archivos que identifica como pertenecientes al tipo de contenido y los muestra en la vista de biblioteca, en la columna Etiqueta de retención también se muestra el nombre de la etiqueta de retención que se ha aplicado a través del modelo.


Por ejemplo, todos los documentos de *Avisos de seguros* que su modelo identifique también tendrán la etiqueta de retención *Negocios* aplicada para que no se eliminen de la biblioteca de documentos durante cinco meses. Si se intenta eliminar el archivo de la biblioteca de documentos, se mostrará un error que indica que no está permitido debido a la etiqueta de retención aplicada.

## <a name="see-also"></a>Consulte también
[Crear un clasificador](create-a-classifier.md)

[Crear un extractor](create-an-extractor.md)

[Información general de la comprensión mediante documentos ](document-understanding-overview.md)


