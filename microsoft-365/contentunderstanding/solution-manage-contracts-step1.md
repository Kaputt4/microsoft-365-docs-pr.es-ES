---
title: Paso 1. Usar SharePoint Syntex para identificar archivos de contrato y extraer datos
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.date: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: ''
description: Obtenga información sobre cómo usar SharePoint Syntex para identificar archivos de contrato y extraer datos mediante una Microsoft 365 solución.
ms.openlocfilehash: b4b11b1bdb980b0ee7629af0cbecbb126a5ae5e5
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2021
ms.locfileid: "52636211"
---
# <a name="step-1-use-sharepoint-syntex-to-identify-contract-files-and-extract-data"></a>Paso 1. Usar SharePoint Syntex para identificar archivos de contrato y extraer datos

Su organización necesita una forma de identificar y clasificar todos los documentos de contrato de los muchos archivos que recibe. También desea poder ver rápidamente varios elementos clave en cada uno de los archivos de contrato identificados (por ejemplo, *Client*, *Contractor* y *Fee amount*). Para ello, use SharePoint [Syntex](index.md) para crear un modelo de descripción de documentos y aplicarlo a una biblioteca de documentos.

## <a name="overview-of-the-process"></a>Información general del proceso

[La comprensión de](document-understanding-overview.md) documentos usa modelos de inteligencia artificial (IA) para automatizar la clasificación de archivos y la extracción de información. Los modelos de comprensión de documentos también son óptimos para extraer información de documentos no estructurados y semiestructurados donde la información que necesita no está contenida en tablas o formularios, como contratos.

1. En primer lugar, debe buscar al menos cinco archivos de ejemplo que pueda usar para "entrenar" el modelo para buscar características específicas del tipo de contenido que está intentando identificar (un contrato). 

2. Con SharePoint Syntex, cree un nuevo modelo de comprensión de documentos. Con los archivos de ejemplo, debe [crear un clasificador](create-a-classifier.md). Al entrenar al clasificador con los archivos de ejemplo, se le enseña a buscar características específicas de lo que vería en los contratos de su empresa. Por ejemplo, [cree una "explicación"](create-a-classifier.md#create-an-explanation) que busque cadenas específicas que estén en sus contratos, como *Contrato* de servicio, *Términos* de contrato y *Compensación*. Incluso puede entrenar su explicación para buscar estas cadenas en secciones específicas del documento o ubicadas junto a otras cadenas. Cuando piense que ha formado al clasificador con la información que necesita, puede probar el modelo en un conjunto de ejemplos de archivos de ejemplo para ver su eficacia. Después de realizar las pruebas, si es necesario, puede elegir realizar cambios en sus explicaciones para hacerlos más eficientes. 

3. En el modelo, puede crear [un extractor](create-an-extractor.md) para extraer partes específicas de datos de cada contrato. Por ejemplo, para cada contrato, la información que más le preocupa es quién es el cliente, el nombre del contratista y el costo total.

4. Después de crear correctamente el modelo, [apliquenlo a](apply-a-model.md)una biblioteca SharePoint documentos . Al cargar documentos en la biblioteca de documentos, el modelo de descripción de documentos se ejecutará e identificará y clasificará todos los archivos que coincidan con el tipo de contenido de contratos definido en el modelo. Todos los archivos clasificados como contratos se mostrarán en una vista de biblioteca personalizada. Los archivos también mostrarán los valores de cada contrato definido en el extractor.

   ![Contratos en la biblioteca de documentos](../media/content-understanding/doc-lib-solution.png)

5. Si tiene requisitos de retención para sus contratos, también puede usar el modelo para aplicar una etiqueta de retención que impedirá que los contratos se eliminen durante un período de tiempo especificado. [](apply-a-retention-label-to-a-model.md)

## <a name="steps-to-create-and-train-your-model"></a>Pasos para crear y entrenar el modelo

> [!NOTE]
> Para estos pasos, puede usar los archivos de ejemplo en el repositorio activos de solución de administración [de contratos](https://github.com/pnp/syntex-samples/tree/main/scenario%20assets/Contracts%20Management). Los ejemplos de este repositorio contienen tanto los archivos del modelo de descripción de documentos como los archivos usados para entrenar el modelo.

### <a name="create-a-contract-model"></a>Crear un modelo de contrato

El primer paso es crear el modelo de contrato.

1. En el centro de contenido, seleccione **Nuevo** y, a continuación, **Crear un modelo**.

2. En el **panel Nuevo modelo de comprensión** de documentos, en el campo **Nombre,** escriba el nombre del modelo. Para esta solución de administración de contratos, puede nombrar el modelo *Contract*.

4. Seleccione **Crear**. Esto crea una página principal para el modelo.</br>

    ![Captura de pantalla de la página principal del contrato.](../media/content-understanding/models-contract-home-page.png)


### <a name="train-your-model-to-classify-a-type-of-file"></a>Entrenar al modelo para clasificar un tipo de archivo

#### <a name="add-example-files-for-your-model"></a>Agregar archivos de ejemplo para el modelo

Debe agregar al menos cinco archivos de ejemplo que sean documentos de contrato y un archivo de ejemplo que no sea un documento de contrato (por ejemplo, una instrucción de trabajo). 

1. En la **página Modelos > Contrato,** en **Acciones** clave Agregar  >  **archivos de** ejemplo, seleccione **Agregar archivos**.

   ![Captura de pantalla que muestra la página Contratos con la opción Agregar archivos de ejemplo resaltada.](../media/content-understanding/key-actions-add-example-files.png)

2. En la **página Seleccionar archivos de ejemplo para el** modelo, abra la carpeta Contrato, seleccione los archivos que desea usar y, a continuación, seleccione **Agregar**. Si no tiene archivos de ejemplo, **seleccione Upload** para agregarlos.

#### <a name="label-the-files-as-positive-or-negative-examples"></a>Etiquetar los archivos como ejemplos positivos o negativos

1. En la **página Modelos > contrato,** en **Acciones** clave Clasificar archivos y ejecutar  >  **aprendizaje,** seleccione **Clasificador de aprendizaje**.

   ![Captura de pantalla que muestra la página Contratos con Clasificar archivos y ejecutar la opción de aprendizaje resaltada.](../media/content-understanding/key-actions-classify-files.png)

2. En  la página Clasificador > contrato > Contrato, en el visor de la parte superior del primer archivo de ejemplo, verá texto preguntando si el archivo es un ejemplo del modelo de contrato que creó. Si es un ejemplo positivo, seleccione **sí**. Si es un ejemplo negativo, seleccione **no**.

3. En la **lista Ejemplos etiquetados** de la izquierda, seleccione otros archivos que desee usar como ejemplos y rótulos. 

    ![Página principal del Clasificador](../media/content-understanding/models-contract-classifier.png) 

#### <a name="add-at-least-one-explanation-to-train-the-classifier&quot;></a>Agregar al menos una explicación para entrenar al clasificador 

1. En la **página > modelo > clasificador** de contrato, seleccione la **pestaña** Entrenar.

2. En la **sección Archivos entrenados,** verá una lista de los archivos de ejemplo etiquetados anteriormente. Seleccione uno de los archivos positivos de la lista para mostrarlo en el visor.

3. En la **sección Explicaciones,** seleccione **Nuevo** y, a continuación, **En blanco**.

4. En la **página** Crear una explicación:

    a. En el **campo** Nombre, escriba el nombre de la explicación (por ejemplo, &quot;Contrato").

    b. En el **campo Tipo de explicación,** seleccione **Lista de frases**, porque agrega una cadena de texto.

    c. En el **cuadro de lista** Frase, escriba la cadena (por ejemplo, "AGREEMENT"). Puede seleccionar Distingue **mayúsculas de** minúsculas si la cadena debe distingue mayúsculas de minúsculas.

    d. Seleccione **Guardar y entrenar**.

    ![Captura de pantalla del panel Crear una explicación.](../media/content-understanding/contract-classifier-create-explanation.png) 

#### <a name="test-your-model"></a>Pruebe el modelo

Puede probar el modelo de contrato en archivos de ejemplo que no haya visto antes. Esto es opcional, pero puede ser un procedimiento recomendado útil.

1. En la **página Modelos > clasificador de > contrato,** seleccione la **pestaña** Prueba. Esto ejecuta el modelo en los archivos de ejemplo sin etiquetar.

2. En la **lista Archivos de** prueba, los archivos de ejemplo se muestran y muestran si el modelo predijo que son positivos o negativos. Utilice esta información para ayudar a determinar la eficacia de su clasificador en la identificación de sus documentos.

    ![Captura de pantalla de los archivos sin etiquetar en la lista Archivos de texto](../media/content-understanding/test-on-files.png) 

3. Cuando haya terminado, seleccione **Salir del aprendizaje**.

### <a name="create-and-train-an-extractor"></a>Crear y entrenar un extractor

1. En la **página Modelos > contrato,** en **Acciones** clave Crear y entrenar  >  **extractores,** seleccione Crear **extractor**.

   ![Captura de pantalla que muestra la página Contratos con la opción Crear y entrenar extractores resaltada.](../media/content-understanding/key-actions-create-extractors.png)

2. En el **panel Nuevo extractor de entidades,** en el campo Nuevo **nombre,** escriba el nombre del extractor. Por ejemplo, descóyenlo *Cliente* si desea extraer el nombre del cliente de cada contrato.

3. Cuando haya terminado, seleccione **Crear**.

#### <a name="label-the-entity-you-want-to-extract"></a>Etiquetar la entidad que desea extraer

Al crear el extractor, se abre la página del extractor. Aquí puede ver una lista de sus archivos de muestra, con el primer archivo de la lista mostrado en el visor.

![Captura de pantalla de la página Ejemplos etiquetados del extractor de cliente.](../media/content-understanding/client-extractor-labeled-examples.png) 

Para etiquetar la entidad:

1. En el visor, seleccione los datos que desea extraer de los archivos. Por ejemplo, si desea extraer el *client*, resalte el valor de cliente en el primer archivo (en este ejemplo, *Best For You Organics*) y, a continuación, **seleccione Guardar**. Verá el valor que se muestra en el archivo en la lista **Ejemplos etiquetados,** en la **columna Etiqueta.**

2. Seleccione **Siguiente archivo** para guardar automáticamente y abra el siguiente archivo de la lista en el visor. O **bien, seleccione Guardar** y, a continuación, seleccione otro archivo de la **lista Ejemplos etiquetados.**

3. En el visor, repita los pasos 1 y 2 y repita hasta que guarde la etiqueta en todos los archivos.

Después de etiquetar los archivos, se muestra un banner de notificación que le informa de que debe pasar al aprendizaje. Puede elegir etiquetar más documentos o avanzar a la formación.

#### <a name="add-an-explanation"></a>Agregue una explicación

Puede crear una explicación que proporciona una sugerencia sobre el propio formato de entidad y las variaciones que puede tener en los archivos de ejemplo. Por ejemplo, un valor de fecha puede estar en muchos formatos diferentes, como:

- 14/10/2019
- 14 de octubre de 2019
- Lunes 14 de octubre de 2019

Para ayudar a identificar la *fecha de inicio del contrato,* puede crear una explicación de patrón.

1. En la **sección Explicaciones,** seleccione **Nuevo** y, a continuación, **En blanco**.

2. En la **página** Crear una explicación:

    a. En el **campo** Nombre, escriba el nombre de la explicación (por *ejemplo, Fecha).*

    b. En el **campo Tipo de explicación,** seleccione **Lista patrón**.

    c. En el **campo** Valor, proporcione la variación de fecha tal como aparecen en los archivos de ejemplo. Por ejemplo, si tiene formatos de fecha que aparecen como 0/00/0000, introduzca cualquier variación que aparezca en sus documentos, como por ejemplo:

    - 0/0/0000
    - 0/00/0000
    - 00/0/0000
    - 00/00/0000

4. Seleccione **Guardar y entrenar**.

#### <a name="test-your-model-again"></a>Vuelva a probar el modelo

Puede probar el modelo de contrato en archivos de ejemplo que no haya visto antes. Esto es opcional, pero puede ser un procedimiento recomendado útil.

1. En la **página Modelos > clasificador de > contrato,** seleccione la **pestaña** Prueba. Esto ejecuta el modelo en los archivos de ejemplo sin etiquetar.

2. En la **lista Archivos de** prueba, los archivos de ejemplo se muestran y muestran si el modelo puede extraer la información que necesita. Utilice esta información para ayudar a determinar la eficacia de su clasificador en la identificación de sus documentos.

3. Cuando haya terminado, seleccione **Salir del aprendizaje**.

### <a name="apply-your-model-to-a-document-library"></a>Aplicar el modelo a una biblioteca de documentos

Para aplicar el modelo a una SharePoint de documentos:

1. En la **página Modelos > contrato,** en **Acciones** clave Aplicar modelo  >  **a bibliotecas,** seleccione **Aplicar modelo**.

   ![Captura de pantalla que muestra la página Contratos con la opción Aplicar modelo a bibliotecas resaltada.](../media/content-understanding/key-actions-apply-model.png)

2. En el panel **Agregar contrato,** seleccione el SharePoint que contiene la biblioteca de documentos a la que desea aplicar el modelo. Si el sitio no aparece en la lista, use el cuadro de búsqueda para encontrarlo. Seleccione **Agregar**.

    > [!NOTE]
    > Debe tener permisos de *Administración de lista* o de *Edición* en la biblioteca de documentos a la que va a aplicar el modelo.

3. Después de seleccionar el sitio, seleccione la biblioteca de documentos a la que desea aplicar el modelo.

4. Dado que el modelo está asociado a un tipo de contenido, al aplicarlo a la biblioteca, agregará el tipo de contenido y su vista con las etiquetas extraídas que se muestran como columnas. Esta vista es la vista predeterminada de la biblioteca de forma predeterminada, pero opcionalmente  puede elegir  que no sea la vista predeterminada seleccionando Configuración avanzada y desactivando la casilla Establecer esta nueva vista como predeterminada.

5. Seleccione **Agregar** para aplicar el modelo a la biblioteca.

6. En la **página Modelos > contrato,** en la sección **Bibliotecas** con este modelo, verá la dirección URL del sitio SharePoint lista.

    ![Captura de pantalla de la página principal del contrato que muestra la sección Bibliotecas con este modelo.](../media/content-understanding/contract-libraries-with-this-model.png)

Después de aplicar el modelo a la biblioteca de documentos, puede empezar a cargar documentos en el sitio y ver los resultados.

## <a name="next-step"></a>Paso siguiente

[Paso 2. Usar Microsoft Teams para crear el canal de administración de contratos](solution-manage-contracts-step2.md)