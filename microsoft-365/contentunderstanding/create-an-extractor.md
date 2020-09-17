---
title: Crear un extractor (versión preliminar)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Obtener información sobre cómo crear un extractor
ms.openlocfilehash: 7219726fb385d0b67f7ee0614f5075ba226140ab
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950089"
---
# <a name="create-an-extractor-preview"></a>Crear un extractor (versión preliminar)
> [!Note] 
> El contenido de este artículo es para la versión preliminar privada de Project Cortex. [Obtenga más información sobre Project Cortex](https://aka.ms/projectcortex).

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL2G]

</br> 

Ya sea antes o después de crear un modelo de clasificador para automatizar la identificación y clasificación de tipos de documentos específicos, también puede elegir agregar extractores al modelo para extraer información específica de estos documentos. Por ejemplo, es posible que desee que el modelo no solo identifique todos los documentos de *renovación de contratos* que se agreguen a la biblioteca de documentos, sino que muestre la fecha de *Inicio del servicio* de cada documento como una columna en la biblioteca de documentos.

Debe crear un extractor para cada entidad en el documento que desea extraer. En nuestro ejemplo, queremos extraer la fecha de *Inicio del servicio* para cada documento de *renovación de contrato* identificado por el modelo. Queremos ver una vista en la biblioteca de documentos de todos los documentos de *renovación de contratos* , con una columna que muestra el valor de fecha de inicio de servicio de cada documento.

> [!Note]
> Antes de crear un extractor, debe [Agregar los archivos de ejemplo](https://docs.microsoft.com/microsoft-365/contentunderstanding/create-a-classifier?view=o365-worldwide#add-your-example-files) que necesita para entrenar el modelo para que identifique la información que desea extraer. Use los mismos archivos de ejemplo que usó para crear su clasificador.


## <a name="name-your-extractor"></a>Nombre del extractor

1. En la Página principal del modelo, en el mosaico **crear y entrenar extractor** , haga clic en **entrenar extractor**.
2. En la pantalla **nuevo extractor de entidades** , escriba el nombre del extractor en el campo **nombre del extractor nuevo** . Por ejemplo, podemos nombrar la **fecha de inicio del servicio** de ti si queremos extraer la fecha de inicio del servicio de cada documento de renovación de contrato.
3. Haga clic en **Crear**.

## <a name="add-a-label"></a>Agregar una etiqueta

El siguiente paso consiste en etiquetar la información que desea extraer en los archivos de formación de ejemplo.

Al crear el extractor se abrirá la página del extractor en la que verá una lista de los archivos de ejemplo, con el primer archivo de la lista que se muestra en el visor.

1. En el visor, seleccione los datos que desea extraer de los archivos. Por ejemplo, si desea extraer la fecha de *Inicio del servicio*, resaltará el valor de fecha correspondiente en el primer archivo (*lunes, 14 de octubre de 2019*). Después, haga clic en **Guardar**.  Verá el valor que se muestra para el archivo en la lista de ejemplos con etiquetas en la columna **etiqueta** .
2. Seleccione **archivo siguiente** para autoguardar y abra el archivo siguiente de la lista en el visor, o bien, seleccione **Guardar** y seleccione otro archivo en la lista de **ejemplos con etiquetas** .
3. En el visor, repita los pasos 1 y 2, y haga esto hasta que haya guardado la etiqueta en cinco archivos.

    ![Configuración avanzada](../media/content-understanding/select-service-start-date.png) 


### <a name="add-a-negative-example"></a>Agregar un ejemplo negativo

De forma similar a como se agregaría un archivo de ejemplo negativo al crear un clasificador, necesita agregar un ejemplo negativo para el extractor. En nuestro ejemplo, debería ser un archivo que no contenga un valor de fecha de inicio de servicio.

1. En la lista de **ejemplos con etiquetas** , seleccione un ejemplo negativo.
2. En el visor, en la parte superior del artículo, seleccione **sin etiqueta presente**.
3. Haga clic en **Guardar**.
 
Una vez que haya etiquetado cinco archivos, se mostrará un banner de notificación que le indicará que debe cambiar a aprendizaje. Puede elegir más documentos o avanzar a la formación. 

## <a name="add-an-explanation"></a>Agregar una explicación

En nuestro ejemplo, vamos a crear una explicación que proporcione una sugerencia sobre el mismo formato de entidad y las variantes que puede tener en los documentos de ejemplo. Por ejemplo, un valor de fecha puede estar en varios formatos diferentes, como:
- 10/14/2019
- 14 de octubre de 2019
- Lunes, 14 de octubre de 2019
 

Para ayudar a identificar la *fecha de inicio del servicio* , puede crear una explicación de la trama.

1. En la sección explicación, seleccione **nuevo**y, a continuación, escriba un nombre (por ejemplo, *fecha*).
2. Para el tipo, seleccione la **lista trama**.
3. Para el valor, debe proporcionar la variación de fecha a medida que aparecen en los archivos de ejemplo. Por ejemplo, si tiene formatos de fecha que aparecen como 0/00/0000, tendría que especificar cualquier variación que aparezca en los documentos, como:
    - 0/0/0000
    - 0/00/0000
    - 00/0/0000
    - 00/00/0000
4. Seleccione **Guardar**.


### <a name="use-the-explanation-library"></a>Usar la biblioteca de explicación

Para crear explicaciones para cosas como fechas, es mucho más fácil usar la biblioteca de explicación que especificar manualmente todas las variantes. La biblioteca de explicación es un conjunto de frases predefinidas y explicaciones de patrones. La biblioteca intenta proporcionar todos los formatos para las listas de patrones o frases comunes, como fechas, números de teléfono, código postal y muchas otras. 

Para nuestro ejemplo de *fecha de inicio de servicio* , es más eficaz usar la explicación predefinida para *Date* en la biblioteca de explicación:

1. En la **sección explicación**, * * seleccione **nuevo**y, a continuación, seleccione **de la biblioteca de explicación**.
2. En la biblioteca de explicación, seleccione **fecha**. Puede ver todas las variaciones de fecha que se reconocerán.
3. Seleccione **Agregar**.</br>

    ![Biblioteca de explicación](../media/content-understanding/explanation-library.png) 

4. En la página **crear una explicación** , la información de *fecha* de la biblioteca de explicación rellenará los campos. Seleccione **Guardar**.</br>

    ![Biblioteca de explicación](../media/content-understanding/date-explanation-library.png) 

 
## <a name="train-the-model"></a>Entrenar el modelo 

Al guardar la explicación se iniciará el curso. Si el modelo tiene información suficiente para extraer los datos de los archivos de ejemplo con la etiqueta, verá cada archivo con la etiqueta **coincidencia**.  

![Biblioteca de explicación](../media/content-understanding/match2.png) 

Si la explicación no tiene suficiente información para encontrar los datos que desea extraer, los archivos se etiquetarán con una etiqueta que no **coincide**. Puede hacer clic en los archivos no coincidentes para ver más información sobre los motivos por los que se ha producido un error de coincidencia.


## <a name="add-another-explanation"></a>Agregar otra explicación

A menudo, la falta de coincidencia es una indicación de que la explicación proporcionada no proporcionó suficiente información para extraer el valor de fecha de inicio de servicio para que coincida con los archivos etiquetados. Es posible que tenga que editarla o agregar otra explicación.

En nuestro ejemplo, se observa que la *fecha de inicio del servicio de* la cadena de texto siempre precede al valor real. Para ayudar a identificar la fecha de inicio del servicio, podemos crear una explicación de la frase.

1. En la sección explicación, seleccione **nuevo**y, a continuación, escriba un nombre (por ejemplo, *cadena de prefijo*).
2. Para el tipo, seleccione **lista de frases**.
3. Use la *fecha de inicio del servicio* como valor.
4. Seleccione **Guardar**.

    ![Biblioteca de explicación](../media/content-understanding/prefix-string.png) 


## <a name="train-the-model"></a>Entrenar el modelo

Al guardar la explicación, se iniciará el aprendizaje de nuevo, esta vez con las explicaciones en nuestro ejemplo. Si el modelo tiene información suficiente para extraer los datos de los archivos de ejemplo con la etiqueta, verá cada archivo con la etiqueta **coincidencia**. 

Si vuelve a recibir una **falta de coincidencia** en los archivos etiquetados, es posible que tenga que crear otra explicación para proporcionar al modelo más información para identificar el tipo de documento o realizar cambios en los existentes.

## <a name="test-your-model"></a>Probar el modelo

Si ha recibido una coincidencia en los archivos de ejemplo con la etiqueta, ahora puede probar el modelo en los restantes archivos de ejemplo sin etiqueta.

1. En la Página principal del modelo, haga clic en la pestaña **prueba** .  Esto hará que se ejecute el modelo en los archivos de ejemplo sin etiqueta.
2. En la lista **archivos de prueba** , se mostrarán los archivos de ejemplo y se mostrará si el modelo puede extraer la información que necesita. Puede usar esta información para ayudar a determinar la eficacia del clasificador en la identificación de los documentos.

    ![Probar los archivos](../media/content-understanding/test-filies-extractor.png) 

## <a name="see-also"></a>Consulte también
  




