---
title: Crear un extractor en Microsoft SharePoint Syntex
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
description: Obtener información sobre cómo crear un extractor en Microsoft SharePoint Syntex.
ms.openlocfilehash: 7d9e04b26e04a3145f5008121bfde162387a9f6b
ms.sourcegitcommit: 23e186b46b27a6a4863f507a52a11105afae9726
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/15/2022
ms.locfileid: "64882536"
---
# <a name="create-an-extractor-in-microsoft-sharepoint-syntex"></a>Crear un extractor en Microsoft SharePoint Syntex


<br/>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL2G]

<br/>

Antes o después de crear un modelo de clasificación para automatizar la identificación y la clasificación de tipos de documentos específicos, puede optar por agregar extractores a su modelo para extraer información específica de estos documentos. Por ejemplo, es posible que desee que su modelo no sólo identifique todos los documentos de *Renovación de contrato* agregados a su biblioteca de documentos, sino que también muestre la *Fecha inicial del servicio* de cada documento como un valor de columna en la biblioteca de documentos.

Es necesario crear un extractor para cada entidad del documento que se desea extraer. En nuestro ejemplo, queremos extraer la fecha de **inicio del servicio** para cada documento de **renovación de contrato** identificado por el modelo. Queremos poder ver una vista en la biblioteca de documentos de todos los documentos de **renovación de contrato** , con una columna que muestra el valor de fecha **de inicio del servicio** de cada documento.

> [!NOTE]
> Para crear un extractor, utilice los mismos archivos que ha subido previamente para entrenar al clasificador.

## <a name="name-your-extractor"></a>Asigne un nombre a su extractor

1. En la página principal del modelo, en el icono **Crear y entrenar extractores**, seleccione **Train extractor (Entrenar extractor).**

2. En la pantalla del extractor de **Nueva entidad**, escriba el nombre de su extractor en el campo **Nombre del nuevo extractor**. Por ejemplo, llámelo **Fecha de inicio del servicio** si desea extraer la fecha de inicio del servicio de cada documento de renovación de contrato. También puede optar por reutilizar una columna creada previamente (por ejemplo, una columna de metadatos administrados).

    De forma predeterminada, el tipo de columna es **Una sola línea de texto**. Si desea cambiar el tipo de columna, seleccione **Configuración** >  **avanzadaTipo de columna** y, a continuación, seleccione el tipo que desea usar.

    ![Captura de pantalla de la parte Configuración avanzada del panel Extractor de nueva entidad que muestra la opción Tipo de columna.](../media/content-understanding/advanced-settings-column-type.png)

    > [!NOTE]
    > Para los extractores con el tipo **de columna Línea única de texto**, el límite máximo de caracteres es 255. Cualquier carácter que escriba que exceda el límite se trunca.

3. Cuando haya terminado, seleccione **Crear**.

## <a name="add-a-label"></a>Agregar una etiqueta

El siguiente paso es etiquetar la entidad que desea extraer en sus archivos de entrenamiento de ejemplo.

Crear el extractor abre la página del extractor. Aquí, podrá ver una lista de los archivos de muestra; el primer archivo de la lista se mostrará en el visor.

1. En el visor, seleccione los datos que desea extraer de los archivos. Por ejemplo, si se quiere extraer la *Fecha de inicio del servicio*, se resalta el valor de la fecha en el primer archivo (*lunes 14 de octubre de 2019*). y, a continuación, seleccione **Guardar**. Debería ver la visualización del valor del archivo en la lista de ejemplos etiquetados, bajo la columna **Etiqueta**.
2. Seleccione **Siguiente archivo** para guardar automáticamente y abra el siguiente archivo en la lista en el visor. O seleccione **Guardar** y luego seleccione otro archivo de la lista de **Ejemplos etiquetados**.
3. En el visor, repita los pasos 1 y 2, y luego repita hasta que haya guardado la etiqueta en los cinco archivos.

    ![Configuración avanzada.](../media/content-understanding/select-service-start-date.png)

Una vez que etiquetó cinco archivos, se muestra un banner de notificación que le informa de pasar al entrenamiento. Puedes elegir entre etiquetar más documentos o avanzar a la formación.

### <a name="use-find-to-search-your-file"></a>Usar Buscar para buscar en el archivo

Puede usar la característica **Buscar** para buscar una entidad que quiera etiquetar en el documento.

   ![Busque en el archivo.](../media/content-understanding/find-feature.png)

La característica Buscar es útil si está buscando un documento grande o si hay varias instancias de la entidad en el documento. Si encuentra varias instancias, puede seleccionar la que necesite en los resultados de búsqueda para ir a esa ubicación en el visor y etiquetarla.

## <a name="add-an-explanation"></a>Agregue una explicación

En nuestro ejemplo, vamos a crear una explicación que proporcione una sugerencia sobre el propio formato de entidad y las variaciones que podría tener en los documentos de ejemplo. Por ejemplo, el valor de una fecha puede estar en varios formatos diferentes, como:

- 14/10/2019
- 14 de octubre de 2019
- Lunes 14 de octubre de 2019

Para ayudar a identificar la *Fecha de inicio del servicio*, puede crear una explicación del patrón.

1. En la sección de Explicación, seleccione **Nuevo** y escriba un nombre (por ejemplo, *Fecha*).
2. Para Tipo, seleccione **Lista de patrones**.
3. Para el Valor, proporcione la variación de la fecha tal como aparece en los archivos de muestra. Por ejemplo, si tiene formatos de fecha que aparecen como 0/00/0000, introduzca cualquier variación que aparezca en sus documentos, como por ejemplo:
    - 0/0/0000
    - 0/00/0000
    - 00/0/0000
    - 00/00/0000
4. Seleccione **Guardar**.

> [!NOTE]
> Para obtener más información sobre los tipos de explicación, consulte [Tipos de explicación](./explanation-types-overview.md)..

### <a name="use-the-explanation-library"></a>Usar la biblioteca de explicación

Para crear explicaciones para elementos como fechas, es más fácil [usar la biblioteca de explicaciones](./explanation-types-overview.md) que escribir manualmente todas las variaciones. La biblioteca de explicaciones es un conjunto de explicaciones de frases y patrones pre generados. La biblioteca intenta proporcionar todos los formatos para las listas de frases o patrones comunes, como fechas, números de teléfono, códigos postales y muchos otros.

En el ejemplo *Fecha de inicio del servicio* , es más eficaz usar la explicación pregenerada de *Fecha* en la biblioteca de explicaciones:

1. En la sección de **Explicación**, seleccione **Nuevo**, y luego seleccione **Desde la biblioteca de explicaciones**.
2. En la biblioteca de explicación, seleccione **Fecha**. Puede ver todas las variaciones de fecha que son reconocidas
3. Seleccione **Agregar**.

    ![Biblioteca de explicación.](../media/content-understanding/explanation-library.png)

4. En la página **Crear una explicación**, la información de la *Fecha* de la biblioteca de explicaciones rellena automáticamente los campos. Seleccione **Guardar**.

    ![Fecha.](../media/content-understanding/date-explanation-library.png)

## <a name="train-the-model"></a>Entrenar el modelo

Al guardar la explicación, se inicia el entrenamiento. Si el modelo tiene suficiente información para extraer los datos de los archivos de ejemplo etiquetados, verá cada archivo con la etiqueta **Match**.

![Coincidencia.](../media/content-understanding/match2.png)

Si la explicación no tiene suficiente información para buscar los datos que desea extraer, cada archivo se etiquetará con **error de coincidencia**. Puede seleccionar Archivos **no coincidentes** para ver más información sobre por qué hubo una falta de coincidencia.

## <a name="add-another-explanation"></a>Agregar otra explicación

A menudo, la falta de coincidencia es una indicación de que la explicación que proporcionamos no proporcionaba suficiente información para extraer el valor de fecha de inicio del servicio para que coincida con nuestros archivos etiquetados. Es posible que tenga que editarlo o agregar otra explicación.

Para nuestro ejemplo, note que la cadena de texto *Fecha de Inicio del servicio de* siempre precede al valor real. Para ayudar a identificar la fecha de Inicio del servicio, necesita crear una frase de explicación.

1. En la sección de Explicación, seleccione **Nuevo**, y luego escriba un nombre (por ejemplo, *Cadena de prefijos*).
2. Para el Tipo, seleccione **Lista de frases**.
3. Utilice la *Fecha de inicio del servicio de* como valor.
4. Seleccione **Guardar**.

    ![Cadena de prefijo.](../media/content-understanding/prefix-string.png)

## <a name="train-the-model-again"></a>Entrenar el modelo de nuevo

Guardando la explicación inicie el entrenamiento de nuevo, esta vez usando ambas explicaciones en el ejemplo. Si su modelo tiene suficiente información para extraer los datos de los archivos de ejemplo etiquetados, verá cada archivo etiquetado con **Coincidencia**.

Si vuelve a recibir un **No coincidencia** en sus archivos etiquetados, es probable que necesite crear otra explicación para proporcionar al modelo más información para identificar el tipo de documento, o considerar la posibilidad de hacer cambios en los ya existentes.

## <a name="test-your-model"></a>Pruebe el modelo

Si recibe una coincidencia en sus archivos de muestra etiquetados, ahora puede probar su modelo en los archivos de muestra no etiquetados restantes. Esto es opcional, pero un paso útil para evaluar la "adecuación" o preparación del modelo antes de usarlo, mediante la prueba en los archivos que el modelo no ha visto antes.

1. En la página principal del modelo, haga clic en la pestaña **Probar**. Esto ejecuta el modelo en sus archivos de muestra sin etiquetar.

2. En la lista de **Archivos de prueba**, sus archivos de ejemplo son presentados para mostrar si el modelo es capaz de extraer la información que necesita. Utilice esta información para ayudar a determinar la eficacia de su clasificador en la identificación de sus documentos.

    ![Prueba en los archivos.](../media/content-understanding/test-filies-extractor.png)

### <a name="further-refine-an-extractor"></a>Refinar aún más un extractor

Si tiene entidades duplicadas y desea extraer solo un valor o un determinado número de valores, puede establecer una regla para especificar cómo desea que se procese. Para agregar una regla para refinar la información extraída, siga estos pasos:

1. En la página principal del modelo, en la sección **Entity extractors (Extractores de entidades** ), seleccione el extractor que desea refinar y, a continuación, seleccione **Refine extracted info (Refinar información extraída**).

    ![Captura de pantalla de la sección Entity extractors (Extractores de entidades) en la que se muestra la opción Refine extracted info (Refinar información extraída) resaltada.](../media/content-understanding/refine-extracted-info.png)

2. En la página **Refinar información extraída** , seleccione una de las reglas siguientes:

    - Conservar uno o varios de los primeros valores
    - Conservar uno o varios de los últimos valores
    - Eliminación de valores duplicados
    - Mantener una o varias de las primeras líneas
    - Mantener una o varias de las últimas líneas

    ![Captura de pantalla de la página Refinar información extraída que muestra las opciones de reglas.](../media/content-understanding/refine-extracted-info-page.png)

3. Escriba el número de líneas o valores que desea usar y, a continuación, seleccione **Refinar**.

4. Si desea editar una regla cambiando el número de líneas o valores, seleccione el extractor que desea editar, seleccione **Refinar información extraída**, cambie el número y, a continuación, seleccione **Guardar**.

5. Al probar el extractor, podrá ver el refinamiento en la columna **Resultado de refinamiento** de la lista **Archivos de prueba** .

    ![Lista archivos de prueba que muestra la columna de resultados de refinamiento.](../media/content-understanding/test-filies-extractor-2.png)

6. Si desea eliminar una regla de refinamiento en un extractor, seleccione el extractor del que desea quitar la regla, seleccione **Refinar información extraída** y, a continuación, seleccione **Eliminar**.

## <a name="see-also"></a>Consulte también

[Crear un clasificador](create-a-classifier.md)

[Tipos de explicación](explanation-types-overview.md)

[Aprovechar la taxonomía del almacén de términos al crear un extractor](leverage-term-store-taxonomy.md)

[Información general sobre la comprensión mediante documentos](document-understanding-overview.md)

[Aplicar un modelo](apply-a-model.md)

[Modo de accesibilidad de SharePoint Syntex](accessibility-mode.md)
