---
title: Creación de un modelo de empresa en Microsoft Syntex
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
description: Obtenga información sobre cómo crear un modelo personalizado o precompilado con Microsoft Syntex.
ms.openlocfilehash: bd2275c40c491626e42f666d2a75dd809c04e584
ms.sourcegitcommit: 87283bb02ca750286f7c069f811b788730ed5832
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2022
ms.locfileid: "68664486"
---
# <a name="create-an-enterprise-model-in-microsoft-syntex"></a>Creación de un modelo de empresa en Microsoft Syntex

<sup>**Se aplica a:**  &ensp; &#10003; Todos los modelos &ensp; | &ensp; personalizados &#10003; Todos los modelos precompilados</sup>

Un modelo de empresa se crea y entrena en el [centro de contenido](create-a-content-center.md) y otros usuarios pueden detectarlo para usarlo. Tanto si desea crear un modelo personalizado como usar un modelo precompilado, puede hacerlo desde cualquiera de estos lugares en Microsoft Syntex:

- Desde la biblioteca **Modelos**
- Desde la página principal del [centro de contenido](create-a-content-center.md)
- Desde cualquier biblioteca de documentos de un sitio donde Syntex se haya activado

En este artículo, comenzamos en la biblioteca **Modelos** . Para obtener información sobre los distintos tipos de modelo, consulte [Información general sobre los tipos de modelo en Syntex](model-types-overview.md).

Si desea crear un modelo local, consulte [Creación de un modelo en un sitio de SharePoint local](create-local-model.md).

## <a name="create-a-model"></a>Crear un modelo

En la biblioteca **Modelos** , seleccione **Crear un modelo**.

![Captura de pantalla de la biblioteca Modelos que muestra el botón Crear un modelo.](../media/content-understanding/create-a-model-from-the-models-page.png) 

En la página **Opciones para la creación de modelos** , hay dos secciones:

- [**Entrenamiento de un modelo personalizado**](#train-a-custom-model)
    
- [**Configuración de un modelo precompilado**](#set-up-a-prebuilt-model)

![Captura de pantalla de la página Opciones para la creación de modelos que muestra los modelos personalizados y los modelos precompilados.](../media/content-understanding/options-for-model-creation.png) 

> [!NOTE]
> Es posible que todas las opciones del modelo no estén disponibles. El administrador de Microsoft 365 configura estas opciones.

## <a name="train-a-custom-model"></a>Entrenamiento de un modelo personalizado

La sección **Entrenar un modelo personalizado** muestra los tipos de modelos personalizados que puede crear.

![Captura de pantalla de la sección Crear un modelo personalizado en la página Opciones para la creación de modelos.](../media/content-understanding/build-a-custom-model-section.png) 

- **Método de enseñanza** : crea un [modelo de procesamiento de documentos no estructurado](document-understanding-overview.md).

- **Método de selección de forma** libre: crea un [modelo de procesamiento de documentos de forma libre](freeform-document-processing-overview.md).

- **Método Layout** : crea un [modelo de procesamiento de documentos estructurado](form-processing-overview.md).

Seleccione una de las pestañas siguientes para continuar con el modelo personalizado que desea usar.

# <a name="teaching-method"></a>[Método de enseñanza](#tab/teaching-method)

Use el **método Teaching** para crear un [modelo de procesamiento de documentos no estructurado](document-understanding-overview.md).

1. Seleccione **Método de enseñanza**.

2. En la página **Teaching method: Details (Método de enseñanza: detalles** ), encontrará más información sobre el modelo. Si desea continuar con la creación del modelo, seleccione **Siguiente**.

3. En el panel derecho de la página **Crear un modelo con el método de enseñanza** , escriba la siguiente información.

    - **Nombre** del modelo: escriba el nombre del modelo, por ejemplo, *contratos de servicio*.

    - **Descripción** : escriba información sobre cómo se usará este modelo.

        ![Captura de pantalla del panel derecho de la página Crear un modelo con el método de enseñanza.](../media/content-understanding/create-a-model-panel.png) 
    
4. En **Configuración avanzada**:

    - En la sección **Tipo de contenido**, elija si quiere crear un nuevo tipo de contenido o usar uno existente.

    - En la sección **Cumplimiento** , en **Etiquetas de retención**, seleccione la etiqueta de retención que desea agregar. En **Etiquetas de confidencialidad**, seleccione la etiqueta de confidencialidad que desea agregar. Si ya se ha aplicado una etiqueta de cumplimiento a la biblioteca donde se almacena el archivo, se mostrará.

5. Cuando esté listo para crear el modelo, seleccione **Crear**.

6. Ya está listo para [entrenar el modelo](create-a-classifier.md).

# <a name="freeform-selection-method"></a>[Método de selección de forma libre](#tab/freeform-selection-method)

Use el **método de selección Deformulario** para crear un [modelo de procesamiento de documentos de forma libre](freeform-document-processing-overview.md).

1. Seleccione **Método de selección de forma libre**.

2. En la página **Método de selección de forma libre: Detalles** , encontrará más información sobre el modelo. Si desea continuar con la creación del modelo, seleccione **Siguiente**.

3. En el panel derecho de la página **Crear un modelo con el método de selección de forma libre** , escriba la siguiente información.

    - **Nombre** del modelo: escriba el nombre del modelo, por ejemplo, *contratos de servicio*.

    - **Descripción** : escriba información sobre cómo se usará este modelo.

        ![Captura de pantalla del panel derecho de la página Crear un modelo con el método de selección de forma libre.](../media/content-understanding/create-a-model-panel.png) 
    
4. En **Configuración avanzada**:

    - En la sección **Tipo de contenido**, elija si quiere crear un nuevo tipo de contenido o usar uno existente.

    - En la sección **Cumplimiento** , en **Etiquetas de retención**, seleccione la etiqueta de retención que desea agregar. Si ya se ha aplicado una etiqueta de cumplimiento a la biblioteca donde se almacena el archivo, se mostrará.

    > [!NOTE]
    > Las etiquetas de confidencialidad no están disponibles para el **método de selección de forma libre** (modelos de procesamiento de documentos de forma libre) en este momento.

5. Cuando esté listo para crear el modelo, seleccione **Crear**.

6. Ya está listo para [entrenar el modelo](train-freeform-document-processing-model.md).

    > [!NOTE]
    > Cuando se publica, este tipo de modelo está disponible para su reutilización por parte de otros usuarios que no poseen el modelo. Actualmente, este modelo solo se puede editar y compartir para que lo edite el propietario del modelo.

# <a name="layout-method"></a>[Layout (método)](#tab/layout-method)

Use el **método Layout** para crear un [modelo de procesamiento de documentos estructurado](form-processing-overview.md).

1. Seleccione **Layout method (Método de diseño).**

2. En la página **Método de diseño: Detalles** , encontrará más información sobre el modelo. Si desea continuar con la creación del modelo, seleccione **Siguiente**.

3. En el panel derecho de la página **Crear un modelo con el método de diseño** , escriba la siguiente información.

    - **Nombre** del modelo: escriba el nombre del modelo, por ejemplo, *contratos de servicio*.

    - **Descripción** : escriba información sobre cómo se usará este modelo.

        ![Captura de pantalla del panel derecho de la página Crear un modelo con el método de diseño.](../media/content-understanding/create-a-model-panel.png) 
    
4. En **Configuración avanzada**:

    - En la sección **Tipo de contenido**, elija si quiere crear un nuevo tipo de contenido o usar uno existente.

    - En la sección **Cumplimiento** , en **Etiquetas de retención**, seleccione la etiqueta de retención que desea agregar. Si ya se ha aplicado una etiqueta de cumplimiento a la biblioteca donde se almacena el archivo, se mostrará.

    > [!NOTE]
    > Las etiquetas de confidencialidad no están disponibles para el **método Layout** (modelos de procesamiento de documentos estructurados) en este momento.

5. Cuando esté listo para crear el modelo, seleccione **Crear**.

6. Ya está listo para [entrenar el modelo](create-a-form-processing-model.md).

    > [!NOTE]
    > Cuando se publica, este tipo de modelo está disponible para su reutilización por parte de otros usuarios que no poseen el modelo. Actualmente, este modelo solo se puede editar y compartir para que lo edite el propietario del modelo.

---

## <a name="set-up-a-prebuilt-model"></a>Configuración de un modelo precompilado

En la sección **Configurar un modelo precompilado** se muestran los tipos de modelos precompilados que puede usar. 

![Captura de pantalla de la sección Usar un modelo precompilado en la página Configurar un modelo precompilado.](../media/content-understanding/use-a-trained-model-section.png) 

- **Procesamiento de facturas**

- **Procesamiento de recibos**

Seleccione una de las pestañas siguientes para continuar con el modelo precompilado que desea usar.

# <a name="invoice-processing"></a>[Procesamiento de facturas](#tab/invoice-processing)

1. Seleccione **Procesamiento de facturas**.

2. En la página **Procesamiento de facturas: detalles** , encontrará más información sobre el modelo. Si desea continuar con el uso del modelo, seleccione **Siguiente**.

3. En el panel derecho de la página **Crear un modelo de procesamiento de facturas** , escriba la siguiente información.

    - **Nombre** del modelo: escriba el nombre del modelo, por ejemplo, *gastos de Office*.

    - **Descripción** : escriba información sobre cómo se usará este modelo.

        ![Captura de pantalla del panel derecho de la página Crear un modelo de procesamiento de facturas.](../media/content-understanding/create-a-model-panel.png) 
    
4. En **Configuración avanzada**:

    - En la sección **Tipo de contenido**, elija si quiere crear un nuevo tipo de contenido o usar uno existente.

    - En la sección **Cumplimiento** , en **Etiquetas de retención**, seleccione la etiqueta de retención que desea agregar. Si ya se ha aplicado una etiqueta de retención a la biblioteca donde se almacena el archivo, se seleccionará. 

    > [!NOTE]
    > Las etiquetas de confidencialidad no están disponibles para los modelos precompilados en este momento.

5. Cuando esté listo para crear el modelo, seleccione **Crear**.

6. Ya está listo para [completar la configuración del modelo](prebuilt-model-invoice.md).

# <a name="receipt-processing"></a>[Procesamiento de recibos](#tab/receipt-processing)


1. Seleccione **Procesamiento de recibos**.

2. En la página **Procesamiento de recibos: detalles** , encontrará más información sobre el modelo. Si desea continuar con el uso del modelo, seleccione **Siguiente**.

2. En el panel derecho de la página **Crear un modelo de procesamiento de recibos** , escriba la siguiente información.

    - **Nombre** del modelo: escriba el nombre del modelo, por ejemplo, *gastos de Office*.

    - **Descripción** : escriba información sobre cómo se usará este modelo.

        ![Captura de pantalla del panel derecho de la página Crear un modelo para procesar recibos.](../media/content-understanding/create-a-model-panel.png) 
    
3. En **Configuración avanzada**:

    - En la sección **Tipo de contenido**, elija si quiere crear un nuevo tipo de contenido o usar uno existente.

    - En la sección **Cumplimiento** , en **Etiquetas de retención**, seleccione la etiqueta de retención que desea agregar. Si ya se ha aplicado una etiqueta de retención a la biblioteca donde se almacena el archivo, se seleccionará. 

    > [!NOTE]
    > Las etiquetas de confidencialidad no están disponibles para los modelos precompilados en este momento.

4. Cuando esté listo para crear el modelo, seleccione **Crear**.

5. Ya está listo para [completar la configuración del modelo](prebuilt-model-receipt.md).

---



<!---
### Teaching method

Use the **Teaching method** to create an [unstructured document processing model](document-understanding-overview.md).

1. Select **Teaching method**.

2. On the **Teaching method: Details** page, you'll find more information about the model. If you want to proceed with creating the model, select **Next**.

3. On the right panel of the **Create a model with the teaching method** page, enter the following information.

    - **Model name** – Enter the name of the model, for example *Service agreements*.

    - **Description** – Enter information about how this model will be used.

        ![Screenshot of the right panel of the Create a model with the teaching method  page.](../media/content-understanding/create-a-model-panel.png) 
    
4. Under **Advanced settings**:

    - In the **Content type** section, choose whether to create a new content type or to use an existing one.

    - In the **Compliance** section, under **Retention labels**, select the retention label you want to add. Under **Sensitivity labels**, select the sensitivity label you want to add. If a compliance label has been already applied to the library where the file is stored, it will be shown.

5. When you are ready to create the model, select **Create**.

6. You are now ready to [train the model](create-a-classifier).

### Freeform selection method

Use the **Freeform selection method** to create a [freeform document processing model](freeform-document-processing-overview.md).

1. Select **Freeform selection method**.

2. On the **Freeform selection method: Details** page, you'll find more information about the model. If you want to proceed with creating the model, select **Next**.

3. On the right panel of the **Create a model with the freeform selection method** page, enter the following information.

    - **Model name** – Enter the name of the model, for example *Service agreements*.

    - **Description** – Enter information about how this model will be used.

        ![Screenshot of the right panel of the Create a model with the Freeform selection method page.](../media/content-understanding/create-a-model-panel.png) 
    
4. Under **Advanced settings**:

    - In the **Content type** section, choose whether to create a new content type or to use an existing one.

    - In the **Compliance** section, under **Retention labels**, select the retention label you want to add. If a compliance label has been already applied to the library where the file is stored, it will be shown.

    > [!NOTE]
    > Sensitivity labels are not available for **Freeform selection method** (freeform document processing models) at this time.

5. When you are ready to create the model, select **Create**.

6. You are now ready to [train the model](train-freeform-document-processing-model.md).

    > [!NOTE]
    > When published, this model type is available for reuse by others who do not own the model. Currently, this model can be edited and shared for editing only by the model owner.

### Layout method

Use the **Layout method** to create a [structured document processing model](form-processing-overview.md).

1. Select **Layout method**.

2. On the **Layout method: Details** page, you'll find more information about the model. If you want to proceed with creating the model, select **Next**.

3. On the right panel of the **Create a model with the layout method** page, enter the following information.

    - **Model name** – Enter the name of the model, for example *Service agreements*.

    - **Description** – Enter information about how this model will be used.

        ![Screenshot of the right panel of the Create a model with the layout method page.](../media/content-understanding/create-a-model-panel.png) 
    
4. Under **Advanced settings**:

    - In the **Content type** section, choose whether to create a new content type or to use an existing one.

    - In the **Compliance** section, under **Retention labels**, select the retention label you want to add. If a compliance label has been already applied to the library where the file is stored, it will be shown.

    > [!NOTE]
    > Sensitivity labels are not available for **Layout method** (structured document processing models) at this time.

5. When you are ready to create the model, select **Create**.

6. You are now ready to [train the model](create-a-form-processing-model.md).

    > [!NOTE]
    > When published, this model type is available for reuse by others who do not own the model. Currently, this model can be edited and shared for editing only by the model owner.

## Set up a prebuilt model

1. In the **Set up a prebuilt model** section, view the types of prebuilt models you can use. Select the type of prebuilt model you want to learn more about or to start using. 

    ![Screenshot of the Use a prebuilt model section on the Set up a prebuilt model page.](../media/content-understanding/use-a-trained-model-section.png) 

    - [**Invoice processing**](#invoice-processing)

    - [**Receipt processing**](#receipt-processing)

2. When you select a prebuilt model, the next page will show you more information about the model. If you want to continue to create the model, select **Next**.

### Invoice processing

1. Select **Invoice processing**.

2. On the **Invoice processing: Details** page, you'll find more information about the model. If you want to proceed with using the model, select **Next**.

3. On the right panel of the **Create an invoice processing model** page, enter the following information.

    - **Model name** – Enter the name of the model, for example *Office expenses*.

    - **Description** – Enter information about how this model will be used.

        ![Screenshot of the right panel of the Create an invoice processing model page.](../media/content-understanding/create-a-model-panel.png) 
    
4. Under **Advanced settings**:

    - In the **Content type** section, choose whether to create a new content type or to use an existing one.

    - In the **Compliance** section, under **Retention labels**, select the retention label you want to add. If a retention label has been already applied to the library where the file is stored, it will be selected. 

    > [!NOTE]
    > Sensitivity labels are not available for prebuilt models at this time.

5. When you are ready to create the model, select **Create**.

6. You are now ready to [complete setting up the model](prebuilt-model-invoice.md).

### Receipt processing

1. Select **Receipt processing**.

2. On the **Receipt processing: Details** page, you'll find more information about the model. If you want to proceed with using the model, select **Next**.

2. On the right panel of the **Create a receipt processing model** page, enter the following information.

    - **Model name** – Enter the name of the model, for example *Office expenses*.

    - **Description** – Enter information about how this model will be used.

        ![Screenshot of the right panel of the Create a model to process receipts page.](../media/content-understanding/create-a-model-panel.png) 
    
3. Under **Advanced settings**:

    - In the **Content type** section, choose whether to create a new content type or to use an existing one.

    - In the **Compliance** section, under **Retention labels**, select the retention label you want to add. If a retention label has been already applied to the library where the file is stored, it will be selected. 

    > [!NOTE]
    > Sensitivity labels are not available for prebuilt models at this time.

4. When you are ready to create the model, select **Create**.

5. You are now ready to [complete setting up the model](prebuilt-model-receipt.md).
--->