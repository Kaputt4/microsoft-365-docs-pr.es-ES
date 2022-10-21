---
title: Entrenamiento de un modelo de procesamiento de documentos de forma libre en Microsoft Syntex
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
ms.custom: admindeeplinkSPO
ms.localizationpriority: medium
description: Aprenda a entrenar un modelo de procesamiento de documentos de forma libre en Microsoft Syntex.
ms.openlocfilehash: b8e306c725680be1bf36ba8922e52c9d1978242e
ms.sourcegitcommit: fa5a1699c8c863a1e61e427e522b3c40855a4f7a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2022
ms.locfileid: "68667806"
---
# <a name="train-a-freeform-document-processing-model-in-microsoft-syntex"></a>Entrenamiento de un modelo de procesamiento de documentos de forma libre en Microsoft Syntex

Siga las instrucciones de [Creación de un modelo en Syntex](create-syntex-model.md) para crear un modelo de procesamiento de documentos de forma libre en un centro de contenido. O bien, siga las instrucciones de [Creación de un modelo en un sitio de SharePoint local](create-local-model.md) para crear el modelo en un sitio local. A continuación, use este artículo para entrenar el modelo.

Para entrenar un modelo de procesamiento de documentos de forma libre, siga estos pasos:

 - [Paso 1: Agregar y analizar documentos](#step-1-add-and-analyze-documents)
 - [Paso 2: Etiquetar campos y tablas](#step-2-tag-fields-and-tables)
 - [Paso 3: Entrenamiento y publicación del modelo](#step-3-train-and-publish-your-model)
 - [Paso 4: Uso del modelo](#step-4-use-your-model)

## <a name="step-1-add-and-analyze-documents"></a>Paso 1: Agregar y analizar documentos

Después de crear el modelo de procesamiento estructurado de documentos, se abre la página **Elegir información para extraer** . Aquí se enumeran todos los fragmentos de información que desea que el modelo de inteligencia artificial extraiga de los documentos, como nombre, dirección o cantidad.  

> [!NOTE]
> Cuando busque archivos de ejemplo que usar, consulte los [requisitos de documento de entrada del modelo de procesamiento de documentos y sugerencias de optimización](/ai-builder/form-processing-model-requirements). 
 
1. En primer lugar, defina los campos y las tablas que quiere enseñar al modelo a extraer en la página **Elija la información para extraer**. Para ver los pasos detallados, vea [Definir campos y tablas para extraer](/ai-builder/create-form-processing-model#define-fields-and-tables-to-extract). 

2.  Puede crear tantas colecciones de diseños de documentos como quiera que procese el modelo. Para ver los pasos detallados, vea [Agrupar documentos por colecciones](/ai-builder/create-form-processing-model#group-documents-by-collections). 

3. Después de crear las colecciones y agregar al menos cinco archivos de ejemplo para cada una, AI Builder en Syntex examinará los documentos cargados para detectar los campos y las tablas. Este proceso suele tardar unos segundos. Una vez completado el análisis, puede continuar con el etiquetado de los documentos.

## <a name="step-2-tag-fields-and-tables"></a>Paso 2: Etiquetar campos y tablas

Debe etiquetar los documentos para enseñar al modelo a comprender los campos y los datos de tabla que quiere extraer. Para ver los pasos detallados, vea [Etiquetar documentos](/ai-builder/create-form-processing-model#tag-documents).

## <a name="step-3-train-and-publish-your-model"></a>Paso 3: Entrenamiento y publicación del modelo

1. Después de crear y entrenar el modelo, está listo para publicarlo y usarlo en SharePoint. Para publicar el modelo, seleccione **Publicar**. Para obtener pasos detallados, consulte [Entrenamiento y publicación del modelo de procesamiento de documentos](/ai-builder/form-processing-train). 

    ![Captura de pantalla en la que se muestran los detalles del modelo en la página principal del modelo.](../media/content-understanding/ai-builder-create-a-flow-1.png)

2. Una vez publicado el modelo, irá a la página principal del modelo. A continuación, tendrá la opción de aplicar el modelo a una biblioteca de documentos.

    ![Captura de pantalla de la página principal del modelo para aplicar el modelo a una biblioteca.](../media/content-understanding/ai-builder-apply-model.png)

## <a name="step-4-use-your-model"></a>Paso 4: Uso del modelo

1. En la vista de modelo de la biblioteca de documentos, tenga en cuenta que los campos que seleccionó se muestran como columnas.

    ![Captura de pantalla que muestra el modelo de biblioteca de documentos aplicado.](../media/content-understanding/doc-lib-view.png)

2. Observe que el vínculo de información junto a **Documentos** indica que se aplica un modelo de procesamiento de formularios a esta biblioteca de documentos.

3. Cargue los archivos a la biblioteca de documentos. Los archivos que el modelo identifica como su tipo de contenido muestran los archivos en la vista y muestra en las columnas los datos extraídos.

    ![Captura de pantalla que muestra que el proceso se ha realizado.](../media/content-understanding/doc-lib-done.png) 

> [!NOTE]
> Si un modelo de procesamiento de documentos estructurados o de forma libre y un modelo de procesamiento de documentos no estructurado se aplican a la misma biblioteca, el archivo se clasifica mediante el modelo de procesamiento de documentos no estructurado y los extractores entrenados para ese modelo. Si hay columnas vacías que coincidan con el modelo de procesamiento de documentos estructurado o de forma libre, las columnas se rellenarán con esos valores extraídos.

### <a name="classification-date-field"></a>Campo Fecha de clasificación

Cuando se aplica un modelo personalizado de Syntex a una biblioteca de documentos, el campo **Fecha de clasificación** se incluye en el esquema de la biblioteca. De forma predeterminada, este campo está vacío. Sin embargo, cuando un modelo procesa y clasifica documentos, este campo se actualiza con una marca de fecha y hora de finalización. 

Cuando un modelo se marca con la **fecha de clasificación**, puede usar **enviar un correo electrónico después de que Syntex procese un** flujo de archivos para notificar a los usuarios que un modelo ha procesado y clasificado un nuevo archivo en la biblioteca de documentos de SharePoint.

Para ejecutar el flujo:

1. Seleccione un archivo y, a continuación, seleccione **Integrar** > **Power Automate** > **Crear un flujo**.

2. En el panel **Crear un flujo** , seleccione **Enviar un correo electrónico después de que Syntex procese un archivo**.

    ![Captura de pantalla que muestra la opción Crear un panel de flujo y flujo resaltada.](../media/content-understanding/integrate-create-flow.png) 

## <a name="see-also"></a>Vea también
  
[Creación de un modelo en Microsoft Syntex](create-syntex-model.md)

[Documentación de Power Automate](/power-automate/)

[Aprendizaje: mejorar el rendimiento empresarial con AI Builder](/learn/paths/improve-business-performance-ai-builder/?source=learn)
