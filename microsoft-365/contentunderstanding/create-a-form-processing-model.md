---
title: Crear un modelo de procesamiento de formularios en Microsoft SharePoint Syntex
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.localizationpriority: medium
description: Obtenga información sobre cómo crear un modelo de procesamiento de formularios en SharePoint Syntex.
ms.openlocfilehash: 5ac00352c64f1403f87ff1c16f3fa44e8c737896
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2021
ms.locfileid: "60198594"
---
# <a name="create-a-form-processing-model-in-microsoft-sharepoint-syntex"></a>Crear un modelo de procesamiento de formularios en Microsoft SharePoint Syntex

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GnhN]  

</br>

Con [AI Builder](/ai-builder/overview) (una característica de Microsoft Power Apps), los usuarios de SharePoint Syntex pueden crear un [modelo de procesamiento de formularios](form-processing-overview.md) directamente desde una biblioteca de documentos de SharePoint. 

La creación de un modelo de procesamiento de formularios implica los pasos siguientes:

 - [Paso 1: crear un modelo de procesamiento de formularios](create-a-form-processing-model.md#step-1-create-a-form-processing-model)
 - [Paso 2: agregar y analizar documentos](create-a-form-processing-model.md#step-2-add-and-analyze-documents)
 - [Paso 3: etiquetar campos y tablas](create-a-form-processing-model.md#step-3-tag-fields-and-tables)
 - [Paso 4: entrenar y publicar el modelo](create-a-form-processing-model.md#step-4-train-and-publish-your-model)
 - [Paso 5: usar el modelo](create-a-form-processing-model.md#step-5-use-your-model)

## <a name="requirements"></a>Requisitos

Solo puede crear un modelo de procesamiento de formularios en las bibliotecas de documentos de SharePoint para las que está habilitado. Si el procesamiento de formularios está habilitado, puede ver el menú **Automatizar** > **AI Builder** > **Crear un modelo para procesar formularios** en la biblioteca de documentos. Si necesita el procesamiento habilitado en la biblioteca de documentos, póngase en contacto con el Administrador de SharePoint.

 ![Captura de pantalla que muestra el modelo de AI Builder.](../media/content-understanding/create-ai-builder-model2.png)

## <a name="step-1-create-a-form-processing-model"></a>Paso 1: crear un modelo de procesamiento de formularios

El primer paso para crear un modelo de procesamiento de formularios es asignar un nombre al modelo, definir el nuevo tipo de contenido y crear una nueva vista de biblioteca de documentos para él.

1. En la biblioteca de documentos, seleccione el menú **Automatizar**, seleccione **AI Builder** y seleccione **Crear un modelo para procesar formularios**.

    ![Captura de pantalla que muestra el menú Automatizar y la opción Crear un modelo para procesar formularios.](../media/content-understanding/create-ai-builder-model2.png)

2. En el panel **Crear un modelo para procesar formularios**, en el campo **Nombre**, escriba el nombre del modelo (por ejemplo, *Pedidos de compra*).

    ![Captura de pantalla que muestra el panel Crear un modelo para procesar formularios.](../media/content-understanding/new-form-model2.png) 

3. Ahora puede extraer y guardar automáticamente información de una *colección* de archivos estructurados que comparten un diseño similar, como facturas o documentos fiscales, que se encuentran en una biblioteca de documentos de SharePoint. Esto le permite componer varios modelos en un único modelo y extraer información específica de elementos de tabla.

   El nombre de la colección se guarda en una columna dedicada de la biblioteca de documentos donde se aplica el modelo, lo que permite distinguir diferentes diseños de archivo procesados por el mismo modelo.

   Además, la información de tabla extraída se guarda en una lista especificada y se asocia con el archivo cargado para facilitar la visualización o para la automatización adicional de procesos empresariales.

   Para extraer información de tabla en una lista asociada:<br><br>

     1. En la sección **¿Extraer información de tablas?**, seleccione **Sí**.

      ![Captura de pantalla que muestra la sección Extraer información de tablas en el panel Crear un modelo para procesar formularios.](../media/content-understanding/extract-info-from-tables.png) 

     2. En la sección **¿Dónde se debe guardar la información de la tabla?**:
 
        - Si selecciona **Una nueva lista** (la configuración predeterminada), se proporciona automáticamente un nombre sugerido en el cuadro **Nuevo nombre de lista**. Puede modificar el nombre si quiere. Si quiere mostrar la lista en la navegación del sitio, active la casilla **Mostrar en la navegación del sitio**.

        - Si selecciona **Una lista existente**, en el cuadro **Lista seleccionada**, elija la lista que quiere usar.

4. Al crear un modelo de procesamiento de formularios, también crea un nuevo tipo de contenido de SharePoint. Un tipo de contenido de SharePoint representa una categoría de documentos que tienen características comunes y comparten una colección de columnas o propiedades de metadatos para ese contenido en particular. Los tipos de contenido de SharePoint se administran a través del Centro de administración de SharePoint.

   Para asignar este modelo a un tipo de contenido existente en la galería de tipos de contenido de SharePoint, seleccione **Configuración avanzada**.

    ![Captura de pantalla que muestra la configuración avanzada en el panel Crear un modelo para procesar formularios.](../media/content-understanding/new-form-model-advanced-settings.png) 

   1. En la sección **Tipo de contenido**, elija si quiere crear un nuevo tipo de contenido o usar uno existente. 

   2. Para usar un tipo de contenido existente, seleccione **Seleccionar uno** y elija un tipo de contenido de la lista.

   3. El modelo crea una nueva vista en la biblioteca de documentos para los datos obtenidos. Si no quiere que sea la vista predeterminada, en la sección **Vista de biblioteca de este modelo**, desactive la casilla **Establecer la vista como predeterminada**.

   4. Para aplicar una etiqueta de retención a los archivos, en la sección **Etiqueta de retención**, seleccione la etiqueta de retención que quiera usar.

5. Seleccione **Crear**.

## <a name="step-2-add-and-analyze-documents"></a>Paso 2: agregar y analizar documentos

Después de crear el nuevo modelo de procesamiento de formularios, el explorador abrirá una nueva página de modelo de procesamiento de formularios de Power Apps AI Builder. En esta página, puede agregar y analizar sus documentos de ejemplo. 

> [!NOTE]
> Al buscar archivos de ejemplo para usar, vea los [requisitos del documento de entrada del modelo de procesamiento de formularios y los consejos de optimización](/ai-builder/form-processing-model-requirements). 
 
1. En primer lugar, defina los campos y las tablas que quiere enseñar al modelo a extraer en la página **Elija la información para extraer**. Para ver los pasos detallados, vea [Definir campos y tablas para extraer](/ai-builder/create-form-processing-model#define-fields-and-tables-to-extract). 

2.  Puede crear tantas colecciones de diseños de documentos como quiera que procese el modelo. Para ver los pasos detallados, vea [Agrupar documentos por colecciones](/ai-builder/create-form-processing-model#group-documents-by-collections). 

3. Después de crear las colecciones y agregar los archivos de ejemplo para cada una, AI Builder examinará los documentos cargados para detectar los campos y las tablas. Esto suele tardar unos minutos. Una vez completado el análisis, puede continuar con el etiquetado de los documentos.

## <a name="step-3-tag-fields-and-tables"></a>Paso 3: etiquetar campos y tablas

Debe etiquetar los documentos para enseñar al modelo a comprender los campos y los datos de tabla que quiere extraer. Para ver los pasos detallados, vea [Etiquetar documentos](/ai-builder/create-form-processing-model#tag-documents).

## <a name="step-4-train-and-publish-your-model"></a>Paso 4: entrenar y publicar el modelo

1. Después de crear y entrenar el modelo, está listo para publicarlo y usarlo en SharePoint. Para ver los pasos detallados, vea [Entrenar y publicar el modelo de procesamiento de formularios](/ai-builder/form-processing-train). 

2. Una vez publicado el modelo, seleccione **Usar modelo** y seleccione **Crear flujo**. Esto crea un flujo de Power Automate que puede ejecutarse en la biblioteca de documentos de SharePoint y extrae los campos que se han identificado en el modelo.

    ![Captura de pantalla de AI Builder que muestra el panel Crear un flujo.](../media/content-understanding/ai-builder-create-a-flow.png)
 
3. Cuando finalice, verá el mensaje: *Su flujo se ha creado correctamente*.

    ![Captura de pantalla de AI Builder que muestra que el flujo se creó correctamente.](../media/content-understanding/ai-builder-flow-created.png)

4. Seleccione el botón **Ir a SharePoint** para ver la biblioteca de documentos actualizada con el modelo.

## <a name="step-5-use-your-model"></a>Paso 5: usar el modelo

1. En la vista de modelo de la biblioteca de documentos, tenga en cuenta que los campos que seleccionó se muestran como columnas.

    ![Modelo de la biblioteca de documentos aplicado.](../media/content-understanding/doc-lib-view.png)

2. Observe que el vínculo de información junto a **Documentos** indica que se aplica un modelo de procesamiento de formularios a esta biblioteca de documentos.

    ![Botón información.](../media/content-understanding/info-button.png)  

3. Cargue los archivos a la biblioteca de documentos. Los archivos que el modelo identifica como su tipo de contenido muestran los archivos en la vista y muestra en las columnas los datos extraídos.

    ![Listo.](../media/content-understanding/doc-lib-done.png) 

## <a name="see-also"></a>Vea también
  
[Documentación de Power Automate](/power-automate/)

[Aprendizaje: mejorar el rendimiento empresarial con AI Builder](/learn/paths/improve-business-performance-ai-builder/?source=learn)