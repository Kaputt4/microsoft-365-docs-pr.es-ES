---
title: Usar un modelo precompilado para extraer información de facturas o recibos en Microsoft SharePoint Syntex
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
description: Obtenga información sobre cómo crear y configurar un modelo precompilado en SharePoint Syntex.
ms.openlocfilehash: 7867fe197fd53e6095f51869fc5aaad18af9157b
ms.sourcegitcommit: cdb90f28e59f36966f8751fa8ba352d233317fc1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2022
ms.locfileid: "63401054"
---
# <a name="use-a-prebuilt-model-to-extract-info-from-invoices-or-receipts-in-microsoft-sharepoint-syntex"></a>Usar un modelo precompilado para extraer información de facturas o recibos en Microsoft SharePoint Syntex

Los modelos precompilados están previamente entrenados para reconocer documentos y la información estructurada de los documentos. En lugar de tener que crear un nuevo modelo personalizado desde cero, puede iterar en un modelo preentrenado existente para agregar campos específicos que se ajusten a las necesidades de su organización. 

Actualmente, hay dos modelos precompilado disponibles: factura y recibo.

- El *modelo precompilado de factura* analiza y extrae información clave de las facturas de ventas. La API analiza las facturas en varios [formatos y extrae](/azure/applied-ai-services/form-recognizer/concept-invoice#field-extraction) información de factura clave, como el nombre del cliente, la dirección de facturación, la fecha de vencimiento y el importe debido.

- El *modelo de confirmación precompilado* analiza y extrae información clave de los recibos de ventas. La API analiza recibos impresos y escritos a mano y extrae información de recibo de clave, como el nombre del comerciante, el número de teléfono del comerciante, la fecha de transacción, los [impuestos](/azure/applied-ai-services/form-recognizer/concept-receipt#field-extraction) y el total de transacciones.

Los modelos precompilados adicionales estarán disponibles en futuras versiones.

## <a name="create-a-prebuilt-model"></a>Crear un modelo precompilado

Siga estos pasos para crear un modelo precompilado para clasificar documentos en SharePoint Syntex.

1. En la **página Modelos** , seleccione **Crear un modelo**.

    ![Captura de pantalla de la página Modelos que muestra el botón Crear un modelo.](../media/content-understanding/prebuilt-create-model-button.png) 

2. En el **panel Crear un** modelo, en el **campo Nombre** , escriba el nombre del modelo.

    ![Captura de pantalla del panel Nuevo modelo de comprensión de documentos que muestra los tipos de modelo disponibles.](../media/content-understanding/prebuilt-create-panel.png) 

3. En la **sección Tipo de** modelo, seleccione uno de los modelos precompilado:
   - **Procesamiento de facturas precompilado**
   - **Procesamiento de recibos precompilado**

   Si desea crear un modelo tradicional de comprensión de documentos sin restricciones en lugar de un modelo precompilado, seleccione **Descripción de documentos personalizados**.

4. Si desea cambiar el tipo de contenido o agregar una etiqueta de retención, seleccione **Configuración avanzada**.

    > [!NOTE]
    > Las etiquetas de confidencialidad no están disponibles para modelos precompilado en este momento.

5. Seleccione **Crear**. El modelo se guardará en la **biblioteca Modelos** .

## <a name="add-a-file-to-analyze"></a>Agregar un archivo para analizar

1. En la **página Modelos** , en la **sección Agregar un archivo para analizar** , seleccione **Agregar archivo**.

    ![Captura de pantalla de la página nuevos modelos que muestra la sección Agregar un archivo para analizar.](../media/content-understanding/prebuilt-add-file-to-analyze.png) 

2. En la **página Archivos para analizar el modelo** , seleccione **Agregar** para buscar el archivo que desea usar.

    ![Captura de pantalla de la página Archivos para analizar el modelo que muestra el botón Agregar.](../media/content-understanding/prebuilt-add-file-button.png) 

3. En la **página Agregar un archivo de la biblioteca** de archivos de aprendizaje, seleccione el archivo y, a continuación, **seleccione Agregar**.

    ![Captura de pantalla de la página Agregar un archivo de la biblioteca de archivos de aprendizaje.](../media/content-understanding/prebuilt-add-file-from-training-library.png) 

6. En la **página Archivos para analizar el modelo** , seleccione **Siguiente**.

## <a name="select-extractors-for-your-model"></a>Seleccionar extractores para el modelo

En la página de detalles del extractor, verá el área del documento a la derecha y el panel **Extractores** a la izquierda. El **panel Extractores** muestra la lista de extractores que se han identificado en el documento.

   ![Captura de pantalla de la página de detalles del extractor y del panel Extractor.](../media/content-understanding/prebuilt-extractor-details-page.png) 

Los campos de entidad que se resaltan en verde en el área del documento son los elementos detectados por el modelo al analizar el archivo. Al seleccionar una entidad para extraer, el campo resaltado cambiará a azul. Si más adelante decide no incluir la entidad, el campo resaltado cambiará a gris. Los resaltados facilitan la vista del estado actual de los extractores seleccionados.

> [!TIP]
> Puede usar el volante de desplazamiento del mouse o los controles situados en la parte inferior del área del documento para acercar o alejar los campos de entidad según sea necesario.

### <a name="select-an-extractor-entity"></a>Seleccionar una entidad extractora

Puede seleccionar un extractor en el área del documento o en el panel **Extractores** , según su preferencia.
 
- Para seleccionar un extractor del área del documento, seleccione el campo de entidad.

    ![Captura de pantalla del área del documento que muestra cómo seleccionar un campo de entidad.](../media/content-understanding/prebuilt-document-area-select-field.png) 

- Para seleccionar un extractor en el panel **Extractores** , active la casilla a la derecha del nombre de la entidad.

    ![Captura de pantalla del panel Extractores que muestra cómo seleccionar un campo de entidad.](../media/content-understanding/prebuilt-extractors-panel-select-field.png) 

Al seleccionar un extractor, se muestra un cuadro **Seleccionar extractor en** el área del documento. El cuadro muestra el nombre del extractor, el valor original y la opción para seleccionarlo como extractor. Para determinados tipos de datos, como números o fechas, también mostrará un valor extraído.

   ![Captura de pantalla del cuadro Seleccionar extractor de la página de detalles del extractor.](../media/content-understanding/prebuilt-select-distractor-box.png) 

El valor original es lo que está realmente en el documento. El valor extraído es lo que se escribirá en la columna de SharePoint. Cuando el modelo se aplica a una biblioteca, puede usar el formato de columna para especificar cómo desea que se vea en el documento.

Continúa seleccionando extractores adicionales que quieras usar. También puede agregar otros archivos para analizar la configuración de este modelo.

## <a name="rename-an-extractor"></a>Cambiar el nombre de un extractor

Puede cambiar el nombre de un extractor desde la página principal del modelo o desde el **panel Extractores** . Es posible que considere cambiar el nombre de los extractores seleccionados porque estos nombres se usarán como nombres de columna cuando se aplique el modelo a la biblioteca.

Para cambiar el nombre de un extractor de la página principal del modelo:

1. En la **sección Extractores** , seleccione el extractor al que desea cambiar el nombre y, a continuación, seleccione **Cambiar nombre**.

    ![Captura de pantalla de la sección Extractores con la opción Cambiar nombre resaltada.](../media/content-understanding/prebuilt-model-page-rename-extractor.png) 

2. En el panel **Cambiar nombre del extractor de entidades** , escriba el nuevo nombre del extractor y, a continuación, seleccione **Cambiar nombre**.

Para cambiar el nombre de un extractor desde el panel **Extractores** :

1. Seleccione el extractor al que desea cambiar el nombre y, a continuación, seleccione **Cambiar nombre**.

    ![Captura de pantalla del panel Extractores que muestra cómo cambiar el nombre de un extractor.](../media/content-understanding/prebuilt-extractors-panel-rename-field.png) 

2. En el **cuadro Cambiar nombre del extractor** , escriba el nuevo nombre del extractor y, a continuación, seleccione **Cambiar nombre**.

## <a name="apply-the-model"></a>Aplicar el modelo

- Para guardar los cambios y volver a la página principal del modelo, en el panel **Extractores** , **seleccione Guardar y salir**.

- Si está listo para aplicar el modelo a una biblioteca, en el área del documento, seleccione **Siguiente**. En el **panel Agregar a biblioteca** , elija la biblioteca a la que desea agregar el modelo y, a continuación, **seleccione Agregar**.

> [!TIP]
> Puede cambiar la vista de la biblioteca de documentos para que se ajuste a sus necesidades o preferencias. Para obtener más información, [vea Cambiar la vista en una biblioteca de documentos](apply-a-model.md#change-the-view-in-a-document-library).

## <a name="see-also"></a>Consulte también

[Aplicar un modelo de comprensión mediante documentos](apply-a-model.md)