---
title: Crear un extractor
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Obtenga información sobre cómo crear un extractor en Microsoft SharePoint Syntex.
ms.openlocfilehash: 740df6769b3a1675e4e1691f84d164312b15567c
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295461"
---
# <a name="create-an-extractor-preview"></a>Crear un extractor (versión preliminar)

El contenido de este artículo es para la versión preliminar privada de Project Cortex. [Obtenga más información sobre Project Cortex](https://aka.ms/projectcortex).

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL2G]

</br> 

Antes o después de crear un modelo de clasificador para automatizar la identificación y la clasificación de los tipos de documentos específicos, puede elegir opcionalmente agregar extractores al modelo para extraer información específica de estos documentos. Por ejemplo, es posible que desee que el modelo no solo identifique todos los documentos de *renovación de contratos* agregados a la biblioteca de documentos, sino que también muestre la fecha de *Inicio del servicio* de cada documento como una columna en la biblioteca de documentos.

Debe crear un extractor para cada entidad en el documento que desea extraer. En el ejemplo, desea extraer la fecha de *Inicio del servicio* de cada documento de *renovación de contratos* que se identifica por el modelo. Esto debe suceder cuando desea ver una vista en la biblioteca de documentos de todos los documentos de *renovación de contratos* con una columna que muestra el valor de fecha de inicio de servicio para cada documento.

> [!NOTE]
> Antes de crear un extractor, debe [Agregar los archivos de ejemplo](https://docs.microsoft.com/microsoft-365/contentunderstanding/create-a-classifier#add-your-example-files) para ayudar a entrenar el modelo para que identifique la información que desea extraer. Use los mismos archivos de ejemplo que usó para crear su clasificador.

## <a name="name-your-extractor"></a>Nombre del extractor

1. En el cuadro **crear y entrenar extractor** de la Página principal del modelo, haga clic en **extractor de tren**.
2. En la pantalla **nuevo extractor de entidades** , escriba el nombre del extractor en el campo **nombre del extractor nuevo** . Por ejemplo, denomine **fecha de inicio del servicio** de ti si desea extraer la fecha de inicio del servicio de cada documento de renovación de contratos.
3. Haga clic en **Crear**.

## <a name="add-a-label"></a>Agregar una etiqueta

El siguiente paso consiste en etiquetar la información que desea extraer en los archivos de formación de ejemplo.

Crear el extractor abre la página extractor. Aquí verá una lista de los archivos de ejemplo, con el primer archivo de la lista que se muestra en el visor.

1. En el visor, seleccione los datos que desea extraer de los archivos. Por ejemplo, si desea extraer la fecha de *Inicio del servicio*, resaltará el valor de fecha en el primer archivo (*lunes, 14 de octubre, 2019*). y, a continuación, haga clic en **Guardar**.  Debe ver el valor mostrado del archivo en la lista de ejemplos con etiquetas, en la columna **etiqueta** .
2. Seleccione **archivo siguiente** para guardar automáticamente y abrir el archivo siguiente de la lista en el visor. O bien, seleccione **Guardar** y, a continuación, seleccione otro archivo en la lista de **ejemplos con etiquetas** .
3. En el visor, repita los pasos 1 y 2 y, a continuación, repita este procedimiento hasta que haya guardado la etiqueta en los cinco archivos.

    ![Configuración avanzada](../media/content-understanding/select-service-start-date.png) 

### <a name="add-a-negative-example"></a>Agregar un ejemplo negativo

De forma similar a como agrega un archivo de ejemplo negativo al crear un clasificador, necesita agregar una muestra negativa para el extractor. Debe ser un archivo que no contenga un valor de fecha de "Inicio de servicio".

1. En la lista de **ejemplos con etiquetas** , seleccione un ejemplo negativo.
2. En el visor que se encuentra en la parte superior del artículo, seleccione **sin etiqueta**.
3. Haga clic en **Guardar **.
 
Una vez que haya etiquetado cinco archivos, aparecerá un banner de notificación que le informará de que debe cambiar a Training. Puede elegir más documentos o avanzar a la formación. 

## <a name="add-an-explanation"></a>Agregar una explicación

Para el ejemplo, se crea una explicación que proporciona una sugerencia sobre el mismo formato de entidad y las variaciones que puede tener en los documentos de muestra. Por ejemplo, un valor de fecha puede estar en varios formatos diferentes, como:
- 10/14/2019
- 14 de octubre de 2019
- Lunes, 14 de octubre de 2019
 

Para ayudar a identificar la *fecha de inicio del servicio* , cree una explicación de la trama.

1. En la sección explicación, seleccione **nuevo** y escriba un nombre (por ejemplo, *fecha*).
2. En tipo, seleccione **lista de tramas**.
3. En valor, especifique la variación de fecha tal y como aparece en los archivos de ejemplo. Por ejemplo, si tiene formatos de fecha que aparecen como 0/00/0000, especifique cualquier variación que aparezca en los documentos, como:
    - 0/0/0000
    - 0/00/0000
    - 00/0/0000
    - 00/00/0000
4. Seleccione **Guardar**.

### <a name="use-the-explanation-library"></a>Usar la biblioteca de explicación

Para crear explicaciones de elementos como fechas, es más fácil usar la biblioteca de explicación que especificar manualmente todas las variantes. La biblioteca de explicación es un conjunto de frases predefinidas y explicaciones de patrones. La biblioteca proporciona todos los formatos para las listas de patrones o frases comunes, como fechas, números de teléfono, código postal, etc. 

Para la muestra de *fecha de inicio de servicio* , es más eficaz usar la explicación predefinida para la *fecha* en la biblioteca de explicación:

1. En la **sección explicación**, seleccione **nuevo**y, a continuación, seleccione **de la biblioteca de explicación**.
2. En la biblioteca de explicación, seleccione **fecha**. Puede ver todas las variaciones de fecha que se reconocen.
3. Seleccione **Agregar**.</br>

    ![Biblioteca de explicación](../media/content-understanding/explanation-library.png) 

4. En la página **crear una explicación** , la información de *fecha* de la biblioteca de explicación rellena automáticamente los campos. Seleccione **Guardar**.</br>

    ![Fecha](../media/content-understanding/date-explanation-library.png) 

## <a name="train-the-model"></a>Entrenar el modelo 

Al guardar la explicación se inicia el curso. Si el modelo tiene información suficiente para extraer los datos de los archivos de ejemplo con la etiqueta, verá cada archivo con la etiqueta **coincidencia**.  

![Coincidir](../media/content-understanding/match2.png) 

Si la explicación no tiene suficiente información para encontrar los datos que desea extraer, los archivos se etiquetarán con una etiqueta que no **coincide**. Puede hacer clic en los archivos no **coincidentes** para ver más información sobre los motivos por los que se ha producido un error de coincidencia.


## <a name="add-another-explanation"></a>Agregar otra explicación

A menudo, la falta de coincidencia es una indicación de que la explicación proporcionada no proporcionó suficiente información para extraer el valor de fecha de inicio de servicio para que coincida con los archivos etiquetados. Es posible que tenga que editarla o agregar otra explicación.

Para la muestra, observe que la *fecha de inicio del servicio de* la cadena de texto siempre precede al valor real. Para ayudar a identificar la fecha de inicio del servicio, debe crear una explicación de la frase.

1. En la sección explicación, seleccione **nuevo**y, a continuación, escriba un nombre (por ejemplo, *cadena de prefijo*).
2. Para el tipo, seleccione **lista de frases**.
3. Use la *fecha de inicio del servicio* como valor.
4. Seleccione **Guardar**.

    ![Cadena de prefijo](../media/content-understanding/prefix-string.png) 

## <a name="train-the-model-again"></a>Volver a entrenar el modelo

Al guardar la explicación, se vuelve a iniciar el programa de aprendizaje, esta vez con las explicaciones del ejemplo. Si el modelo tiene información suficiente para extraer los datos de los archivos de ejemplo con la etiqueta, verá cada archivo con la etiqueta **coincidencia**. 

Si vuelve a recibir una **falta de coincidencia** en los archivos etiquetados, es probable que deba crear otra explicación para proporcionar al modelo más información para identificar el tipo de documento o considerar la posibilidad de realizar cambios en el modelo de ejemplo.

## <a name="test-your-model"></a>Probar el modelo

Si recibe una coincidencia en los archivos de ejemplo con la etiqueta, ahora puede probar el modelo en los restantes archivos de ejemplo sin etiqueta.

1. En la Página principal del modelo, haga clic en la pestaña **prueba** .  Esto ejecuta el modelo en los archivos de ejemplo sin etiqueta.
2. En la lista **archivos de prueba** , se muestran los archivos de ejemplo para mostrar si el modelo puede extraer la información que necesita. Use esta información para ayudar a determinar la eficacia del clasificador en la identificación de los documentos.

    ![Probar los archivos](../media/content-understanding/test-filies-extractor.png) 
