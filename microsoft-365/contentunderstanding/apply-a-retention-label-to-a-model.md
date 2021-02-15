---
title: Aplicar una etiqueta de retención a un modelo
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Este artículo muestra cómo aplicar una etiqueta de retención a un modelo en SharePoint Syntex
ms.openlocfilehash: 48c0b983316cfe29019d09cb20546fa4b325b3b0
ms.sourcegitcommit: 78f48304f990e969a052fe6536b2e8d6856e1086
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "50242776"
---
# <a name="apply-a-retention-label-to-a-model-in-sharepoint-syntex"></a>Puede aplicar fácilmente una etiqueta de retención a un modelo en SharePoint Syntex.

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GydO]  

</br>


Puede aplicar fácilmente una [etiqueta de retención](https://docs.microsoft.com/microsoft-365/compliance/retention) a un modelo en Microsoft SharePoint Syntex. Puede hacerlo tanto para modelos de comprensión de documentos como para modelos de procesamiento de formularios

Las etiquetas de retención le permiten aplicar la configuración de retención a los documentos que identifican sus modelos.  Por ejemplo, si desea que el modelo no solo identifique cualquier documento de *Notificación de seguros* cargados en la biblioteca de documentos, sino que también pueda aplicar una etiqueta de retención de *negocios* para que estos documentos no se puedan eliminar de la biblioteca de documentos durante el período de tiempo especificado (por ejemplo, los próximos cinco meses).

Puede aplicar una etiqueta de retención preexistente al modelo en la página principal del modelo. 

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

## <a name="to-add-a-retention-label-to-a-form-processing-model"></a>Agregar una etiqueta de retención a un modelo de comprensión mediante documentos

> [!Important]
> Para que las etiquetas de retención estén disponibles para aplicarlas a su modelo de procesamiento de formularios, deben [crearse y publicarse en el Centro de cumplimiento de Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/create-apply-retention-labels#how-to-create-and-publish-retention-labels).

Puede aplicar una etiqueta de retención a un modelo de procesamiento de formularios cuando cree el modelo, o bien aplicarlo a un modelo ya existente.

### <a name="to-add-a-retention-label-when-you-create-a-form-processing-model"></a>Agregar una etiqueta de retención a un modelo de comprensión mediante documentos cuando se crea el modelo

1. Cuando cree un [nuevo modelo de procesamiento de formularios](https://docs.microsoft.com/microsoft-365/contentunderstanding/create-a-form-processing-model), seleccione la <b>Configuración avanzada.</b>
2. En <b>Configuración avanzada</b>, en la sección <b>Etiqueta de retención</b>, seleccione el menú y, después, seleccione la etiqueta de retención que quiere aplicar al modelo.</b>

 
     ![Agregar a un nuevo modelo de procesamiento de formularios](../media/content-understanding/retention-label-forms.png)</br>

3.  Cuando haya completado la configuración del modelo restante, seleccione <b>Crear</b> para crear el modelo.

### <a name="to-add-a-retention-label-to-an-existing-form-processing-model"></a>Agregar una etiqueta de retención a un modelo de comprensión mediante documentos existente

Hay dos maneras de agregar una etiqueta de retención a un modelo de comprensión mediante documentos existente:
- A través del menú Automatizar de la biblioteca de documentos
- A través de la configuración del Modelo activo en la biblioteca de documentos 


#### <a name="to-add-a-retention-label-to-an-existing-form-processing-model-through-the-automate-menu"></a>Agregar una etiqueta de retención a un modelo de comprensión mediante documentos existente con el menú Automatizar

Puede agregar una etiqueta de retención a un modelo de procesamiento de formularios existente del que sea propietario mediante el menú Automatizar de la biblioteca de documentos en la que se aplica el modelo.


1. En la biblioteca de documentos a la que se aplica el modelo de procesamiento de formularios, seleccione el menú <b>Automatizar</b>, luego <b>AI Builder</b> y finalmente <b>Ver detalles del modelo de procesamiento de formularios</b>.

   ![Menú Automatizar](../media/content-understanding/automate-menu.png)</br>

2. En los detalles del modelo, en <b>Etiqueta de retención</b>, seleccione la etiqueta de retención que quiera aplicar.  Después, seleccione <b>Guardar</b>.

     ![Agregar a un modelo de procesamiento de formularios ya existente](../media/content-understanding/retention-label-model-details.png)</br> 

#### <a name="to-add-a-retention-label-to-an-existing-form-processing-model-in-the-active-model-settings"></a>Agregar una etiqueta de retención a un modelo de procesamiento de formularios existente en la configuración del modelo activo

Puede agregar una etiqueta de retención a un modelo de procesamiento de formulario existente del que sea propietario en la configuración del Modelo activo de la biblioteca de documentos en la que se aplica el modelo.

1. En la biblioteca de documentos de SharePoint en la que se aplica el modelo, seleccione el icono <b>Ver modelos activos</b> y, después, seleccione <b>Ver modelos activos</b>.</b>

   ![Ver modelos activos](../media/content-understanding/info-du.png)</br> 

2. En <b>Modelos activos</b>, seleccione el modelo de procesamiento de formularios al que quiere aplicar la etiqueta de retención.

     ![Detalles del modelo](../media/content-understanding/retention-label-model-details.png)</br> 


3. En los detalles del modelo, en <b>Etiqueta de retención</b>, seleccione la etiqueta de retención que quiera aplicar.  Después, seleccione <b>Guardar</b>.

> [!NOTE]
> Debe ser el propietario del modelo del panel de configuración del modelo para poder editarlo. 


## <a name="see-also"></a>Consulte también
[Crear un clasificador](create-a-classifier.md)

[Crear un extractor](create-an-extractor.md)

[Información general de la comprensión mediante documentos ](document-understanding-overview.md)


