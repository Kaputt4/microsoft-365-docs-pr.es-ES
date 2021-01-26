---
title: Crear un modelo de procesamiento de formularios
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
description: Crear un modelo de procesamiento de formularios en Microsoft SharePoint Syntex.
ms.openlocfilehash: c025317a5eb88199b849f90b51fac9779e1c97a2
ms.sourcegitcommit: 162c01dfaa2fdb3225ce4c24964c1065ce22ed5d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/25/2021
ms.locfileid: "49976014"
---
# <a name="create-a-form-processing-model-in-microsoft-sharepoint-syntex"></a>Crear un modelo de procesamiento de formularios en Microsoft SharePoint Syntex

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GnhN]  

</br>

Usar [AI Builder](https://docs.microsoft.com/ai-builder/overview): característica en Microsoft PowerApps - SharePoint Syntex los usuarios pueden crear un [modelo de procesamiento de formularios](form-processing-overview.md) directamente desde una biblioteca de documentos de SharePoint. 

Crear un modelo de procesamiento de formularios implica lo siguiente:
 - Paso 1: crear el modelo de procesamiento de formularios para crear el tipo de contenido
 - Paso 2: agregar y analizar archivos de ejemplo
 - Paso 3: seleccionar los campos de formulario
 - Paso 4: entrenar y probar el modelo
 - Paso 5: publicar el modelo
 - Paso 6: usar el modelo

## <a name="requirements"></a>Requisitos

Solo puede crear un modelo de procesamiento de formularios en las bibliotecas de documentos de SharePoint para las que está habilitado. Si el procesamiento de formularios está habilitado, puede ver el **AI Builder** **"Crear un modelo de procesamiento de formularios"** en el menú **Automatizar** en la biblioteca de documentos.  Si necesita el procesamiento habilitado en la biblioteca de documentos, póngase en contacto con el Administrador de SharePoint.

 ![Crear un modelo de AI Builder](../media/content-understanding/create-ai-builder-model.png)</br>

## <a name="step-1-create-a-form-processing-model"></a>Paso 1: crear un modelo de procesamiento de formularios

El primer paso para crear un modelo de procesamiento de formularios es asignarle un nombre, crear la definición, crear el nuevo tipo de contenido y crear una nueva vista de la biblioteca de documentos.

1. En la biblioteca de documentos, seleccione el menú **Automatizar**, seleccione **AI Builder** y, después elija **Crear un modelo de procesamiento de formularios**.

    ![Crear un modelo](../media/content-understanding/create-ai-builder-model.png)</br>

2. En el panel **Nuevo modelo de procesamiento de formularios**, en el campo **Nombre**, escriba el nombre del modelo (por ejemplo, *Pedidos de compra*).

    ![Nuevo modelo de procesamiento de formularios](../media/content-understanding/new-form-model.png)</br> 

3. Al crear un modelo de procesamiento de formularios, también crea un nuevo tipo de contenido de SharePoint. Un tipo de contenido de SharePoint representa una categoría de documentos que tienen características comunes y comparten una colección de columnas o propiedades de metadatos para ese contenido en particular. Los tipos de contenido de SharePoint se administran en la [Galería de tipos de contenido]().

    Seleccione **Configuración avanzada** si quiere asignar este modelo a un tipo de contenido existente en la galería de tipos de contenido de SharePoint para usar su esquema. 

4. El modelo crea una nueva vista de la biblioteca de documentos para los datos obtenidos. Si no quiere que aparezca en la vista predeterminada, anule la selección de **Establecer la vista como predeterminada**.

5. Seleccione **Crear**.

## <a name="step-2-add-and-analyze-documents"></a>Paso 2: agregar y analizar documentos

Después de crear el nuevo modelo de procesamiento de formularios, el explorador abrirá una nueva página de modelo de procesamiento de formularios de PowerApps AI Builder. En esta página, puede agregar y analizar sus documentos de ejemplo. </br>

> [!NOTE]
> Al buscar archivos de ejemplo para usar, vea los [requisitos del documento de entrada del modelo de procesamiento de formularios y los consejos de optimización](https://docs.microsoft.com/ai-builder/form-processing-model-requirements). 

   ![Power Apps AI Builder](../media/content-understanding/powerapps.png)</br> 
 
1. Seleccione **Agregar documentos** para comenzar a agregar documentos de ejemplo analizados para determinar los pares de valores nombrados que se pueden extraer. A continuación, puede elegir **Cargar desde almacenamiento local**, **SharePoint** o **Azure Blob Storage**. Debe usar al menos cinco archivos para el entrenamiento.

2. Después de agregar archivos, seleccione **Analizar** para comprobar si hay información común en todos los archivos. Esta acción puede tardar varios minutos en completarse.</br> 
 
    ![Analizar archivos](../media/content-understanding/analyze.png)</br> 

3. Después de que se hayan analizados los archivos, en la página **Seleccionar los campos de formulario que quiere guardar** seleccione el archivo para ver los campos detectados.</br>

    ![Seleccionar campos de formulario](../media/content-understanding/select-form-fields.png)</br> 

## <a name="step-3-select-your-form-fields"></a>Paso 3: seleccionar los campos de formulario

Después de analizar los documentos para los campos, puede ver los campos que encontró e identificar los que quiere guardar. Los campos guardados se muestran como columnas en la vista de la biblioteca de documentos del modelo y muestran los valores extraídos de cada documento.

1. En la página siguiente se mostrará uno de los archivos de ejemplo y se resaltarán todos los campos comunes que el sistema detectó automáticamente. </br>

    ![Página seleccionar campos](../media/content-understanding/select-fields-page.png)</br> 

2. Seleccione los campos que quiere guardar y marque la casilla para confirmar la selección. Por ejemplo, en el modelo de pedido de compra, elija para seleccionar los campos *Fecha*, *OC*, y *Total*.  Tenga en cuenta que también puede elegir cambiar el nombre de un campo. </br>

    ![Seleccionar OC#](../media/content-understanding/po.png)</br> 

3. Si un análisis no ha detectado un campo, aún puede agregarlo. Resalte la información que desea extraer y, en el cuadro Nombre, escriba el nombre que desee. Después, seleccione la casilla. Tenga en cuenta que debe confirmar los campos no detectados en los archivos de ejemplo restantes.

4. Haga clic en **Confirmar campos** después de seleccionar los campos que quiere guardar. </br>
 
    ![Confirmar campos después de seleccionar campos](../media/content-understanding/confirm-fields.png)</br> 
 
5. La página **Seleccionar los campos de formulario que quiere guardar**, muestra el número de campos que ha seleccionado. Seleccione **Listo**.

## <a name="step-4-train-and-test-your-model"></a>Paso 4: entrenar y probar el modelo

Después de seleccionar los campos que quiere guardar, la página **Resumen del modelo** le permite entrenar y probar el modelo.

1. En la página **Resumen del modelo**, los campos guardados se mostrarán en la sección **Seleccionar campos**. Seleccione **Entrenar** para comenzar el entrenamiento en sus archivos de ejemplo. Tenga en cuenta que esta acción puede tardar unos minutos en completarse.</br>

     ![Seleccionar campos de entrenamiento](../media/content-understanding/select-fields-train.png)</br> 

2. Cuando vea la notificación de que el entrenamiento ha finalizado, seleccione **Ir a la página de detalles**. 

3. En la página **Detalles del modelo**, puede elegir probar el funcionamiento del modelo seleccionando **Prueba rápida**. Esto le permite arrastrar y soltar archivos a la página y ver si se detectan los campos.

    ![Confirmar campos](../media/content-understanding/select-fields-train.png)</br> 

2. Cuando vea la notificación de que el entrenamiento ha finalizado, seleccione **Ir a la página de detalles**. 

3. En la página **Detalles del modelo**, elija probar cómo funciona el modelo seleccionando **Prueba rápida**. Esto le permite arrastrar y soltar archivos a la página y ver si se detectan los campos.

## <a name="step-5-publish-your-model"></a>Paso 5: publicar el modelo

1. Si está de acuerdo con los resultados de su modelo, seleccione **Publicar** para que esté disponible para su uso.

2. Después de que se publique el modelo, seleccione **Usar modelo**. Esto crea un flujo de PowerAutomate que puede ejecutarse en la biblioteca de documentos de SharePoint y extrae los campos que se han identificado en el modelo, luego seleccione **Crear flujo**.
  
3. Cuando finalice, verá el mensaje **Su flujo se ha creado correctamente**.
 
## <a name="step-6-use-your-model"></a>Paso 6: usar el modelo

Después de publicar el modelo y crear el flujo de PowerAutomate, puede usar el modelo en la biblioteca de documentos de SharePoint.

1. Después de publicar el modelo, seleccione **Ir a SharePoint** para ir a la biblioteca de documentos.

2. En la vista modelo de la biblioteca de documentos, tenga en cuenta que los campos que seleccionó se muestran como columnas.</br>

    ![Modelo de la biblioteca de documentos aplicado](../media/content-understanding/doc-lib-view.png)</br> 

3. Observe que el vínculo de información junto a **Documentos** indica que se aplica un modelo de procesamiento de formularios a esta biblioteca de documentos.

    ![Botón información](../media/content-understanding/info-button.png)</br>  

4. Cargue los archivos a la biblioteca de documentos. Los archivos que el modelo identifica como su tipo de contenido muestran los archivos en la vista y muestra en las columnas los datos extraídos.</br>

    ![Hecho](../media/content-understanding/doc-lib-done.png)</br>  

## <a name="see-also"></a>Vea también
  
[Documentación de Power Automate](https://docs.microsoft.com/power-automate/)

[Aprendizaje: mejorar el rendimiento empresarial con AI Builder](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)
