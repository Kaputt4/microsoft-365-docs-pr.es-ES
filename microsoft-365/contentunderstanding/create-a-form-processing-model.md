---
title: Crear un modelo de procesamiento de formularios (versión preliminar)
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
description: Cree un modelo de procesamiento de formularios en Project Cortex.
ms.openlocfilehash: 733baf24d8a484571ba9882fdda2633dc2ce0504
ms.sourcegitcommit: a3a5dc541b0c971608cc86ef480509c25a13ca60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/10/2020
ms.locfileid: "46612779"
---
# <a name="create-a-form-processing-model-preview"></a>Crear un modelo de procesamiento de formularios (versión preliminar)

> [!Note] 
> El contenido de este artículo es para la versión preliminar privada de Project Cortex. [Obtenga más información sobre Project Cortex](https://aka.ms/projectcortex).

Uso del [generador de AI](https://docs.microsoft.com/ai-builder/overview) : una característica de Microsoft PowerApps-Project Cortex los usuarios pueden crear un modelo de procesamiento de [formularios](form-processing-overview.md) directamente desde una biblioteca de documentos de SharePoint. 

La creación de un modelo de procesamiento de formularios implica lo siguiente:
 - Paso 1: crear el modelo de procesamiento para crear el tipo de contenido
 - Paso 2: agregar y analizar archivos de ejemplo
 - Paso 3: seleccionar los campos de formulario
 - Paso 4: entrenar y probar el modelo
 - Paso 5: publicar el modelo
 - Paso 6: usar el modelo


## <a name="requirements"></a>Requirements

Solo se puede crear un modelo de procesamiento de formularios en bibliotecas de documentos de SharePoint en el que esté habilitado. Si el procesamiento de formularios está habilitado, podrá ver el **generador de AI** **"crear un modelo de procesamiento de formularios"** en el menú **automatizar** de la biblioteca de documentos.  Si necesita el procesamiento habilitado en la biblioteca de documentos, póngase en contacto con el administrador.

 ![Crear un modelo de generador de AI](../media/content-understanding/create-ai-builder-model.png)</br>


## <a name="step-1-create-a-form-processing-model"></a>Paso 1: crear un modelo de procesamiento de formularios

El primer paso para crear un modelo de procesamiento de formularios es nombrarlo para crear la vista definir el nuevo tipo de contenido y crear una nueva vista de biblioteca de documentos.

1. En la biblioteca de documentos, seleccione el menú **automatizar** , seleccione **generador de AI**y, a continuación, seleccione **crear un modelo de procesamiento de formularios**.

    ![Crear un modelo de generador de AI](../media/content-understanding/create-ai-builder-model.png)</br>
2. En el panel **nuevo modelo de procesamiento de formularios** , en el campo **nombre** , escriba un nombre para el modelo (por ejemplo, *pedidos de compra*).

    ![Nuevo modelo de procesamiento de formularios](../media/content-understanding/new-form-model.png)</br> 

3. Cuando se crea un modelo de procesamiento de formularios, se crea un nuevo tipo de contenido de SharePoint. Un tipo de contenido de SharePoint representa una categoría de documentos que tienen características comunes y comparten una colección de columnas o propiedades de metadatos para ese contenido en particular. Los tipos de contenido de SharePoint se administran a través de la [Galería de tipos de contenido]().

    Seleccione **Configuración avanzada** si desea asignar este modelo a un tipo de contenido existente en la galería de tipos de contenido de SharePoint para usar su esquema. 

4. El modelo creará una nueva vista en la biblioteca de documentos para los datos extraídos. Si no desea que se ajuste a la vista predeterminada, anule **la selección de establecer la vista como predeterminada**.
5. Seleccione **Crear**.


## <a name="step-2-add-and-analyze-documents"></a>Paso 2: agregar y analizar documentos

Después de crear el nuevo modelo de procesamiento de formularios, el explorador abrirá una nueva página del modelo de procesamiento de formularios de PowerApps AI Builder. En esta página, puede Agregar y analizar los documentos de ejemplo. </br>

> [!Note]
> Al buscar archivos de ejemplo para usar, vea el [modelo de procesamiento de formularios requisitos de documentos de entrada y sugerencias de optimización](https://docs.microsoft.com/ai-builder/form-processing-model-requirements). 

   ![Generador de AI de Power apps](../media/content-understanding/powerapps.png)</br> 
 

1. Haga clic en **agregar documentos** para empezar a agregar documentos de ejemplo que se analizan para determinar qué pares de valor con nombre se pueden extraer. Puede elegir entre **cargar desde almacenamiento local**, **SharePoint**o almacenamiento de **blobs de Azure**. Debe usar al menos cinco archivos para el entrenamiento.
2. Después de agregar los archivos, seleccione **analizar** para comprobar si la información es común en todos los archivos. Tenga en cuenta que esto puede tardar varios minutos en completarse.</br> 
 
    ![Analizar archivos](../media/content-understanding/analyze.png)</br> 

3. Una vez analizados, en la página **Seleccione los campos de formulario que desea guardar** , haga clic en el archivo para ver los campos detectados.</br>

    ![Selección de campos de formulario](../media/content-understanding/select-form-fields.png)</br> 

## <a name="step-3-select-your-form-fields"></a>Paso 3: seleccionar los campos de formulario

Después de analizar los documentos para los campos, ahora puede ver qué campos se encontraron y cuáles desea guardar. Los campos guardados se mostrarán como columnas en la vista de la biblioteca de documentos del modelo y mostrarán los valores extraídos de cada documento.

1. En la página siguiente se mostrará uno de los archivos de ejemplo y se resaltarán todos los campos comunes detectados automáticamente por el sistema. </br>

    ![Selección de campos de formulario](../media/content-understanding/select-fields-page.png)</br> 

2. Seleccione los campos que desea guardar y active la casilla de verificación para confirmar la selección. Por ejemplo, en el modelo de pedido de compra, puede elegir seleccionar los campos *fecha*, *po*y *total* .  Tenga en cuenta que también puede cambiar el nombre de un campo si lo prefiere. </br>

    ![Seleccionar PO #](../media/content-understanding/po.png)</br> 

3. Si el análisis no ha detectado un campo, puede optar por agregarlo. Resalte la información que desea extraer y, en el cuadro Nombre, escriba el nombre que desea asignar. A continuación, seleccione la comprobación. Tenga en cuenta que deberá confirmar los campos no detectados en los archivos de ejemplo restantes.
4. Haga clic en **confirmar campos** después de haber seleccionado los campos que desea guardar. </br>
 
    ![Confirmar campos](../media/content-understanding/confirm-fields.png)</br> 
 
5. En la página **Seleccione los campos de formulario que desea guardar** , se mostrará el número de campos que ha seleccionado. Seleccione **Listo**.

## <a name="step-4-train-and-test-your-model"></a>Paso 4: entrenar y probar el modelo

Después de seleccionar los campos que desea guardar, la página de **Resumen del modelo** le permitirá entrenar y probar el modelo.

1. En la página de **Resumen del modelo** , los campos guardados se mostrarán en la sección **campos seleccionados** . Seleccione **entrenar** para empezar a entrenar en los archivos de ejemplo. Tenga en cuenta que esta operación puede tardar unos minutos en completarse.</br>
    ![Confirmar campos](../media/content-understanding/select-fields-train.png)</br> 
2. Cuando vea la notificación de que se ha completado el entrenamiento, seleccione **ir a la página de detalles**. 
3. En la página **detalles del modelo** , puede elegir probar el funcionamiento del modelo seleccionando **prueba rápida**. Esto le permite arrastrar y soltar archivos a la página y ver si se detectan los campos.

## <a name="step-5-publish-your-model"></a>Paso 5: publicar el modelo



1. Si está satisfecho con los resultados del modelo, seleccione **publicar** para que esté disponible para su uso.
2. Después de publicar el modelo, seleccione **usar modelo**. Esto crea un flujo de PowerAutomate que se ejecutará en la biblioteca de documentos de SharePoint y extraerá los campos identificados en el modelo. Seleccione **Crear flujo**.  
3. Una vez completado, verá el mensaje el **flujo se ha creado correctamente**.
 
 
## <a name="step-6-use-your-model"></a>Paso 6: usar el modelo

Después de publicar el modelo y crear su flujo de PowerAutomate, puede usar el modelo en la biblioteca de documentos de SharePoint.

1. Después de publicar el modelo, seleccione **ir a SharePoint** para ir a la biblioteca de documentos.
2. En la vista del modelo de la biblioteca de documentos, observe que los campos que seleccionó se muestran como columnas.</br>

    ![Biblioteca de documentos con el modelo aplicado](../media/content-understanding/doc-lib-view.png)</br> 

    Además, observe que el vínculo de información que hay junto a los **documentos** tendrá en cuenta que se aplica un modelo de procesamiento de formularios a esta biblioteca de documentos.

    ![Yendo](../media/content-understanding/info-button.png)</br>  

3. Cargar archivos en la biblioteca de documentos. Los archivos que el modelo identifica como su tipo de contenido mostrarán los archivos en la vista y mostrarán los datos extraídos en las columnas.</br>

    ![Yendo](../media/content-understanding/doc-lib-done.png)</br>  



## <a name="see-also"></a>Vea también
  
[Documentación automatizada de la energía](https://docs.microsoft.com/power-automate/)</br>
[Aprendizaje: mejorar el rendimiento empresarial con el generador de AI](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>




