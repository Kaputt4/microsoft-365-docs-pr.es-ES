---
title: Uso de un modelo precompilado para extraer información de facturas en Microsoft Syntex
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
description: Obtenga información sobre cómo usar un modelo de facturas precompilado en Microsoft Syntex.
ms.openlocfilehash: f2f23a164231089e803c4626c09ffa76f908123c
ms.sourcegitcommit: 87283bb02ca750286f7c069f811b788730ed5832
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2022
ms.locfileid: "68664466"
---
# <a name="use-a-prebuilt-model-to-extract-information-from-invoices-in-microsoft-syntex"></a>Uso de un modelo precompilado para extraer información de facturas en Microsoft Syntex

El modelo de *facturas* precompilado analiza y extrae información clave de las facturas de ventas. La API reconoce las facturas en varios formatos y [extrae la información clave de la factura](/azure/applied-ai-services/form-recognizer/concept-invoice#field-extraction), como el nombre del cliente, la dirección de facturación, la fecha de vencimiento y el importe vencido.

Para usar un modelo de facturas, siga estos pasos:

- Paso 1: [Crear un modelo de facturas](#create-an-invoices-model)
- Paso 2: [Carga de un archivo de ejemplo para analizar](#upload-an-example-file-to-analyze)
- Paso 3: [Selección de extractores para el modelo](#select-extractors-for-your-model)
- Paso 4: [Aplicar el modelo](#apply-the-model)

## <a name="create-an-invoices-model"></a>Creación de un modelo de facturas

Siga las instrucciones de [Creación de un modelo en Syntex](create-syntex-model.md) para crear un modelo de facturas precompilado. A continuación, continúe con los pasos siguientes para completar el modelo.


<!---
## Create an invoices model

Follow these steps to create a trained invoices model.

1. From the **Models** page, select **Create a model**.

    ![Screenshot of the Models page showing the Create a model button.](../media/content-understanding/create-a-model-from-the-models-page.png) 


2. On the **View options for classification and extraction** page, in the **Use a trained model** section, select **Invoices**.

    ![Screenshot of the View options for classification and extraction page showing the custom models and trained models.](../media/content-understanding/view-options-for-classification-and-extraction-page.png) 

3. To continue, follow these [instructions to continue to create an invoices model](create-syntex-model.md#invoices).

    > [!NOTE]
    > Sensitivity labels are not available for trained models at this time.
--->

## <a name="upload-an-example-file-to-analyze"></a>Carga de un archivo de ejemplo para analizar

1. En la página **Modelos** , en la sección **Agregar un archivo para analizar** , seleccione **Agregar archivo**.

    ![Captura de pantalla de la página nuevos modelos que muestra la sección Agregar un archivo para analizar.](../media/content-understanding/prebuilt-add-file-to-analyze.png) 

2. En la página **Archivos para analizar el modelo** , seleccione **Agregar** para buscar el archivo que desea usar.

    ![Captura de pantalla de la página Archivos para analizar el modelo que muestra el botón Agregar.](../media/content-understanding/prebuilt-add-file-button.png) 

3. En la página **Agregar un archivo de la biblioteca de archivos de entrenamiento** , seleccione el archivo y, a continuación, seleccione **Agregar**.

    ![Captura de pantalla de la página Agregar un archivo desde la biblioteca de archivos de entrenamiento.](../media/content-understanding/prebuilt-add-file-from-training-library.png) 

4. En la página **Archivos para analizar el modelo** , seleccione **Siguiente**.

## <a name="select-extractors-for-your-model"></a>Selección de extractores para el modelo

En la página de detalles del extractor, verá el área del documento a la derecha y el panel **Extractores** de la izquierda. El panel **Extractores** muestra la lista de extractores que se han identificado en el documento.

   ![Captura de pantalla de la página de detalles del extractor y del panel Extractor.](../media/content-understanding/prebuilt-extractor-details-page.png) 

Los campos de entidad resaltados en verde en el área de documento son los elementos detectados por el modelo al analizar el archivo. Al seleccionar una entidad que se va a extraer, el campo resaltado cambiará a azul. Si más adelante decide no incluir la entidad, el campo resaltado cambiará a gris. Los resaltados facilitan la visualización del estado actual de los extractores seleccionados.

> [!TIP]
> Puede usar la rueda de desplazamiento del mouse o los controles de la parte inferior del área de documento para acercar o alejar según sea necesario para leer los campos de entidad.

### <a name="select-an-extractor-entity"></a>Selección de una entidad extractora

Puede seleccionar un extractor desde el área de documento o desde el panel **Extractores** , según sus preferencias.
 
- Para seleccionar un extractor del área de documento, seleccione el campo de entidad.

    ![Captura de pantalla del área del documento en la que se muestra cómo seleccionar un campo de entidad.](../media/content-understanding/prebuilt-document-area-select-field.png) 

- Para seleccionar un extractor en el panel **Extractores** , active la casilla situada a la derecha del nombre de la entidad.

    ![Captura de pantalla del panel Extractores que muestra cómo seleccionar un campo de entidad.](../media/content-understanding/prebuilt-extractors-panel-select-field.png) 

Al seleccionar un extractor, se muestra un cuadro **Seleccionar extractor en** el área de documento. El cuadro muestra el nombre del extractor, el valor original y la opción para seleccionarlo como extractor. Para determinados tipos de datos, como números o fechas, también mostrará un valor extraído.

   ![Captura de pantalla del cuadro Seleccionar extractor en la página de detalles del extractor.](../media/content-understanding/prebuilt-select-distractor-box.png) 

El valor original es lo que realmente está en el documento. El valor extraído es lo que se escribirá en la columna de SharePoint. Cuando el modelo se aplica a una biblioteca, puede usar el formato de columna para especificar cómo desea que se vea en el documento.

Continúe con la selección de extractores adicionales que quiera usar. También puede agregar otros archivos para analizar la configuración de este modelo.

### <a name="rename-an-extractor"></a>Cambiar el nombre de un extractor

Puede cambiar el nombre de un extractor desde la página principal del modelo o desde el panel **Extractores** . Puede considerar la posibilidad de cambiar el nombre de los extractores seleccionados porque estos nombres se usarán como nombres de columna cuando el modelo se aplique a la biblioteca.

Para cambiar el nombre de un extractor desde la página principal del modelo:

1. En la sección **Extractores** , seleccione el extractor al que desea cambiar el nombre y, a continuación, seleccione **Cambiar nombre**.

    ![Captura de pantalla de la sección Extractores con la opción Cambiar nombre resaltada.](../media/content-understanding/prebuilt-model-page-rename-extractor.png) 

2. En el panel **Cambiar nombre del extractor de entidades** , escriba el nuevo nombre del extractor y, a continuación, seleccione **Cambiar nombre**.

Para cambiar el nombre de un extractor desde el panel **Extractores** :

1. Seleccione el extractor al que desea cambiar el nombre y, a continuación, seleccione **Cambiar nombre**.

    ![Captura de pantalla del panel Extractores que muestra cómo cambiar el nombre de un extractor.](../media/content-understanding/prebuilt-extractors-panel-rename-field.png) 

2. En el cuadro **Cambiar nombre del extractor** , escriba el nuevo nombre del extractor y, a continuación, seleccione **Cambiar nombre**.

## <a name="apply-the-model"></a>Aplicar el modelo

- Para guardar los cambios y volver a la página principal del modelo, en el panel **Extractores** , seleccione **Guardar y salir**.

- Si está listo para aplicar el modelo a una biblioteca, en el área de documento, seleccione **Siguiente**. En el panel **Agregar a la biblioteca** , elija la biblioteca a la que desea agregar el modelo y, a continuación, seleccione **Agregar**.

## <a name="change-the-view-in-a-document-library"></a>Cambio de la vista en una biblioteca de documentos

Para obtener información sobre cómo establecer la vista predeterminada y cómo cambiar la vista de una biblioteca de documentos, vea [Elegir la vista en una biblioteca de documentos](choose-library-view.md).

<!---
[!INCLUDE [Change the view in a document library](../includes/change-library-view.md)]
--->
