---
title: Aplicación de una etiqueta de retención a un modelo en Microsoft Syntex
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.service: microsoft-syntex
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.localizationpriority: medium
description: Obtenga información sobre cómo aplicar una etiqueta de retención a un modelo en Microsoft Syntex.
ms.openlocfilehash: 7fb57fa2e33bde1a3534ffbb6c4541587072b730
ms.sourcegitcommit: 87283bb02ca750286f7c069f811b788730ed5832
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2022
ms.locfileid: "68661641"
---
# <a name="apply-a-retention-label-to-a-model-in-microsoft-syntex"></a>Aplicación de una etiqueta de retención a un modelo en Microsoft Syntex

<sup>**Se aplica a:**  &ensp; &#10003; procesamiento &ensp; | &ensp; de documentos no estructurados &#10003; procesamiento &ensp;| &ensp; estructurado de documentos &#10003; Todos los modelos precompilados</sup>

<!---
</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GydO]  

</br>
--->

Puede aplicar fácilmente una [etiqueta de retención](../compliance/retention.md) a un modelo en Microsoft Syntex.

> [!Note]
> Las etiquetas de retención aún no están disponibles para los modelos de procesamiento de documentos de Freeform.

Las etiquetas de retención le permiten aplicar la configuración de retención a los documentos que identifican sus modelos.  Por ejemplo, quiere que el modelo no solo identifique los documentos de *aviso de seguro* que se carguen en la biblioteca de documentos, sino que también les aplique una etiqueta de retención *empresarial* para que estos documentos no se puedan eliminar de la biblioteca de documentos durante el período de tiempo especificado (los próximos cinco meses, por ejemplo).

Puede aplicar una etiqueta de retención preexistente al modelo en la página principal del modelo. 

## <a name="add-a-retention-label-to-an-unstructured-document-processing-model-or-a-prebuilt-model"></a>Agregar una etiqueta de retención a un modelo de procesamiento de documentos no estructurado o a un modelo precompilado

> [!Important]
> Para que las etiquetas de retención estén disponibles para aplicarlas al procesamiento de documentos no estructurados o a los modelos precompilados, deben [crearse](../compliance/file-plan-manager.md#create-retention-labels) y [publicarse](../compliance/create-apply-retention-labels.md#how-to-publish-retention-labels) en el portal de cumplimiento Microsoft Purview.

1. En la página principal del modelo, seleccione **Configuración del modelo**.

2. En **Configuración del modelo**, en la sección **Seguridad y cumplimiento** , seleccione el menú **Etiqueta de retención** para ver una lista de las etiquetas de retención que están disponibles para que se apliquen al modelo.

 ![Menú Etiqueta de retención.](../media/content-understanding/retention-labels-menu.png)

3. Seleccione la etiqueta de retención que desea aplicar al modelo y, a continuación, seleccione **Guardar**.

Después de aplicar la etiqueta de retención al modelo, puede aplicarla a:

- una nueva biblioteca de documentos y
- una biblioteca de documentos en la que ya se aplica el modelo.
 
### <a name="apply-the-retention-label-to-a-document-library-to-which-the-model-is-already-applied"></a>Aplicar la etiqueta de retención a la biblioteca de documentos en la que ya se aplica el modelo

Si el modelo de procesamiento de documentos no estructurado o el modelo precompilado ya se ha aplicado a una biblioteca de documentos, puede hacer lo siguiente para sincronizar la actualización de la etiqueta de retención para aplicarla a la biblioteca de documentos:

1. En la Página principal del modelo, en la sección **Bibliotecas con este modelo**, seleccione la biblioteca de documentos a la que quiera aplicar la actualización de la etiqueta de retención.

2. Seleccione **Sincronizar**.

   ![Modelo de sincronización.](../media/content-understanding/sync-model.png)</br> 

Después de aplicar la actualización y sincronizarla con el modelo, puede confirmar que se ha aplicado realizando los pasos siguientes:

1. En el centro de contenido, sección **Bibliotecas con este modelo**, seleccione la biblioteca a la que se ha aplicado el modelo actualizado.

2. En la vista de la biblioteca de documentos, seleccione el icono de información para ver las propiedades del modelo.

3. En la lista **Modelos activos**, seleccione el modelo actualizado.

4. En la sección **Etiqueta de retención** , verá el nombre de la etiqueta de retención aplicada.

En la página de vista del modelo de la biblioteca de documentos, se mostrará una nueva columna de la **Etiqueta de retención**.  A medida que el modelo clasifica los archivos que identifica como pertenecientes a su tipo de contenido y los enumera en la vista de biblioteca, la columna **Etiqueta de retención** también mostrará el nombre de la etiqueta de retención que se le ha aplicado a través del modelo.

Por ejemplo, todos los documentos de *Avisos de seguros* que su modelo identifique también tendrán la etiqueta de retención *Negocios* aplicada para que no se eliminen de la biblioteca de documentos durante cinco meses. Si se intenta eliminar el archivo de la biblioteca de documentos, se mostrará un error que indica que no está permitido debido a la etiqueta de retención aplicada.

## <a name="add-a-retention-label-to-a-structured-document-processing-model"></a>Adición de una etiqueta de retención a un modelo de procesamiento estructurado de documentos

> [!Important]
> Para que las etiquetas de retención estén disponibles para aplicarlas a los modelos de procesamiento de documentos estructurados, deben [crearse](../compliance/file-plan-manager.md#create-retention-labels) y [publicarse](../compliance/create-apply-retention-labels.md#how-to-publish-retention-labels) en el portal de cumplimiento Microsoft Purview.

Puede aplicar una etiqueta de retención a un modelo de procesamiento de documentos estructurado al crear un modelo o aplicarlo a un modelo existente.

### <a name="to-add-a-retention-label-when-you-create-a-structured-document-processing-model"></a>Para agregar una etiqueta de retención al crear un modelo de procesamiento estructurado de documentos

1. Al [crear un nuevo modelo de procesamiento estructurado de documentos](./create-a-form-processing-model.md), seleccione **Configuración avanzada**.

2. En **Configuración avanzada**, en la sección **Etiqueta de retención**, seleccione el menú y, después, seleccione la etiqueta de retención que quiere aplicar al modelo.
 
     ![Agregue a un nuevo modelo de procesamiento de documentos estructurado.](../media/content-understanding/retention-label-forms.png)

3.  Cuando haya completado la configuración del modelo restante, seleccione **Crear** para crear el modelo.

### <a name="to-add-a-retention-label-to-an-existing-structured-document-processing-model"></a>Para agregar una etiqueta de retención a un modelo de procesamiento de documentos estructurado existente

Puede agregar una etiqueta de retención a un modelo de procesamiento de documentos estructurado existente de diferentes maneras:

- A través del menú **Automatizar** de la biblioteca de documentos
- A través de la configuración del **modelo activo** en la biblioteca de documentos 

#### <a name="to-add-a-retention-label-to-an-existing-structured-document-processing-model-through-the-automate-menu"></a>Para agregar una etiqueta de retención a un modelo de procesamiento de documentos estructurado existente mediante el menú Automatizar

Puede agregar una etiqueta de retención a un modelo de procesamiento de documentos estructurado existente que posee a través del menú **Automatizar** de la biblioteca de documentos en la que se aplica el modelo.

1. En la biblioteca de documentos a la que se aplica el modelo, seleccione los **detalles del modelo** **Automatizar** >  vista **del generador de inteligencia artificial** > .

    ![Menú Automatizar.](../media/content-understanding/automate-menu.png)

2. En los detalles del modelo, en la sección **Etiqueta de retención** , seleccione la etiqueta de retención que desea aplicar y, a continuación, seleccione **Guardar**.

    ![Agregue a un modelo de procesamiento de documentos estructurado existente.](../media/content-understanding/retention-label-model-details.png)</br> 

#### <a name="to-add-a-retention-label-to-an-existing-structured-document-processing-model-in-the-active-model-settings"></a>Para agregar una etiqueta de retención a un modelo de procesamiento de documentos estructurado existente en la configuración del modelo activo

Puede agregar una etiqueta de retención a un modelo de procesamiento de documentos estructurado existente que posee a través de la configuración del modelo activo en la biblioteca de documentos en la que se aplica el modelo.

1. En la biblioteca de documentos de SharePoint en la que se aplica el modelo, seleccione el icono **Ver modelos activos** y, después, seleccione **Ver modelos activos**.

    ![Ver modelos activos.](../media/content-understanding/info-du.png)

2. En **Modelos activos**, seleccione el modelo al que desea aplicar la etiqueta de retención.

    ![Detalles del modelo.](../media/content-understanding/retention-label-model-details.png)</br> 

3. En los detalles del modelo, en la sección **Etiqueta de retención** , seleccione la etiqueta de retención que desea aplicar y, a continuación, seleccione **Guardar**.

> [!NOTE]
> Debe ser el propietario del modelo del panel de configuración del modelo para poder editarlo. 

## <a name="see-also"></a>Vea también

[Aplicar una etiqueta de confidencialidad a un modelo en Microsoft Syntex](create-a-classifier.md)



