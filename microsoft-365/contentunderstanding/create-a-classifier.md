---
title: Crear un clasificador (versión preliminar)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Obtener información sobre cómo crear un clasificador
ms.openlocfilehash: 088770ace8914b583b184c78c3ce110d9d68b4c7
ms.sourcegitcommit: a3a5dc541b0c971608cc86ef480509c25a13ca60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/10/2020
ms.locfileid: "46612613"
---
# <a name="create-a-classifier-preview"></a>Crear un clasificador (versión preliminar)

> [!Note] 
> El contenido de este artículo es para la versión preliminar privada de Project Cortex. [Obtenga más información sobre Project Cortex](https://aka.ms/projectcortex).

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL0R]  

</br>

Un clasificador es un tipo de modelo que automatiza la identificación y clasificación de un tipo de documento. Por ejemplo, es posible que desee identificar todos los documentos de *renovación de contratos* que se agregan a la biblioteca de documentos, como los siguientes.

![Documento de renovación de contrato](../media/content-understanding/contract-renewal.png)

La creación de un clasificador creará un nuevo [tipo de contenido de SharePoint](https://docs.microsoft.com/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) que se asociará al modelo.

Al crear el clasificador, tiene que crear *explicaciones* que le ayuden a definir el modelo mediante la anotación de datos comunes que esperaría buscar de forma coherente en este tipo de documento. 

Puede usar ejemplos del tipo de documento ("archivos de ejemplo") para "entrenar" su modelo para identificar los archivos que tienen el mismo tipo de contenido.

Para crear un clasificador, debe:
1. Asigne un nombre al modelo
2. Adición de los archivos de ejemplo
3. Etiquetar los archivos de ejemplo
4. Crear una explicación
5. Probar el modelo 

> [!Note]
> Mientras que el modelo utiliza un clasificador para identificar y clasificar los tipos de documentos, también puede optar por extraer fragmentos específicos de información de cada archivo identificado por el modelo. Para ello, cree un **extractor** para agregarlo al modelo y esto se describe en Create a [extractor](create-an-extractor.md).

## <a name="name-your-model"></a>Asigne un nombre al modelo

El primer paso consiste en crear el modelo en el centro de contenido asignándole un nombre:

1. En el centro de contenido, haga clic en **nuevo**y, a continuación, haga clic en **crear un modelo**.
2. En el panel **nuevo documento que comprende el modelo** , en el campo **nombre** , escriba el nombre del modelo. En nuestro ejemplo, si queremos identificar documentos de renovación de contratos, podríamos nombrar esta renovación de *contrato*de modelo.
3. Haga clic en **Crear**. De este modo, se creará una página principal para el modelo.</br>

    ![Página de inicio del modelo de clasificador](../media/content-understanding/model-home.png)

Al crear un modelo, se crea un nuevo tipo de contenido de SharePoint. Un tipo de contenido de SharePoint representa una categoría de documentos que tienen características comunes y comparten una colección de columnas o propiedades de metadatos para ese contenido en particular. Los tipos de contenido de SharePoint se administran a través de la [Galería de tipos de contenido](). En nuestro ejemplo, cuando creamos el modelo, crearemos un nuevo tipo de contenido de *renovación de contrato* .

Seleccione **Configuración avanzada** si desea asignar este modelo a un tipo de contenido existente en la galería de tipos de contenido de SharePoint para usar su esquema. Tenga en cuenta que, si bien puede usar un tipo de contenido existente para aprovechar su esquema para ayudar con la identificación y clasificación, deberá entrenar el modelo para extraer información de los archivos que identifica.</br>

![Configuración avanzada](../media/content-understanding/advanced-settings.png)

## <a name="add-your-example-files"></a>Adición de los archivos de ejemplo

En la Página principal del modelo, puede Agregar los archivos de ejemplos que necesita para entrenar el modelo para identificar su tipo de documento. </br>
</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4D0iX] 

</br>

> [!Note]
> Se deben usar los mismos archivos para la formación de clasificador y [extractor](create-an-extractor.md). Siempre tiene la opción de agregar más adelante, pero normalmente debe agregar un conjunto completo de archivos de ejemplo. Deberá etiquetar algunas para entrenar el modelo y probar los restantes no etiquetados para evaluar la idoneidad del modelo. 

Para su conjunto de aprendizaje, querrá usar ejemplos positivos y negativos:
- Ejemplo positivo: documentos que representan el tipo de documento. Contienen cadenas e información que siempre estaría en este tipo de documento.
- Ejemplo negativo: documentos que no representan el tipo de documento.  Faltan cadenas e información que debe estar presente en este tipo de documento.

Querrá usar al menos cinco ejemplos positivos y un ejemplo negativo para entrenar el modelo.  Querrá tener otros para probar el modelo después de la formación.

Para agregar archivos de ejemplo:

1. En la Página principal del modelo, en el mosaico **biblioteca de ejemplo de compilación** , haga clic en **Agregar archivos**.
2. En la página **seleccionar archivos de ejemplo para el modelo** , seleccione los archivos de ejemplo de la biblioteca de archivos de ejemplo en el centro de contenido. Si aún no se han cargado allí, puede optar por cargarlas ahora haciendo clic en **cargar** para moverlas a la biblioteca de archivos de muestra.
3. Después de seleccionar los archivos de ejemplo que se usarán para entrenar el modelo, haga clic en **Agregar**.

    ![Seleccionar archivos de ejemplo](../media/content-understanding/select-sample.png) 

## <a name="label-your-example-files"></a>Etiquetar los archivos de ejemplo

Después de agregar los archivos de ejemplo, debe etiquetarlos como ejemplos positivos o negativos.

1. En la Página principal del modelo, en el icono **clasificar archivos y ejecutar el entrenamiento** , haga clic en **formar clasificador**.
   Se mostrará la página de etiqueta que muestra una lista de los archivos de ejemplo, con el primer archivo visible en el visor.
2. En el visor, en la parte superior del primer archivo de ejemplo, verá texto que le pregunta si el archivo es un ejemplo del modelo que acaba de crear. Si es un ejemplo positivo, seleccione **sí**. Si es un ejemplo negativo, seleccione **no**.
3. En la lista de **ejemplos con etiquetas** de la izquierda, seleccione los archivos adicionales que desee usar como ejemplos y etiquételo también. 

    ![Página de inicio del modelo de clasificador](../media/content-understanding/classifier-home-page.png) 


> [!Note]
> Etiquete como mínimo cinco ejemplos positivos y un ejemplo negativo. 

## <a name="create-an-explanation"></a>Crear una explicación

El siguiente paso es crear una explicación en la página del tren.  Una explicación es una sugerencia o indicio para ayudar a que el modelo comprenda cómo reconocer este documento. Por ejemplo, los documentos de renovación de contratos siempre contienen una *solicitud para una cadena de texto de divulgación adicional* .

> [!Note]
> Cuando se usa con extractores, se usa una explicación para identificar la cadena que se desea extraer del documento. 

Para crear una explicación:

1. En la Página principal del modelo, haga clic en la pestaña **tren** para ir a la página tren.
2. En la página tren, en la sección **archivos entrenados** , verá una lista de los archivos de ejemplo que ha etiquetado anteriormente. Seleccione uno de los archivos positivos de la lista y se mostrará en el visor.
3. En la sección explicación, haga clic en **nuevo**y, a continuación, haga clic en **en blanco**.
4. En la página **crear una explicación** :</br>
    a. Escriba el **nombre** (por ejemplo, "bloque de revelación").</br>
    b. Seleccione el **tipo**. En nuestro ejemplo, seleccionaremos **lista de frases**, ya que estamos agregando una cadena de texto.</br>
    c. En el cuadro **Escriba aquí** , escriba la cadena.  Para nuestro ejemplo, agregaremos "solicitud de divulgación adicional". Puede seleccionar **mayúsculas** y minúsculas si la cadena debe distinguir mayúsculas de minúsculas.</br>
    d. Haga clic en **Guardar**.

    ![Crear explicación](../media/content-understanding/explanation.png) 
    
 
5.  El modelo comprobará ahora si la explicación que ha creado es lo suficientemente buena como para identificar los archivos de ejemplo con la etiqueta que queden correctamente como ejemplos positivos y negativos. En la sección archivos entrenados, revise la columna **evaluación** después de que se haya completado el entrenamiento para ver los resultados.  Los archivos mostrarán un valor de **coincidencia** si la explicación que ha creado es suficiente para coincidir con lo que ha etiquetado como (positivo o negativo).

    ![Crear explicación](../media/content-understanding/match.png) 

Si recibe un error de **coincidencia** con los archivos etiquetados, es posible que deba crear una explicación adicional para proporcionar al modelo más información para identificar el tipo de documento. Puede hacer clic en el archivo para obtener más información sobre la razón por la que se produjo la discrepancia.

## <a name="test-your-model"></a>Probar el modelo

Si ha recibido una coincidencia en los archivos de ejemplo con la etiqueta, ahora puede probar el modelo en los restantes archivos de ejemplo sin etiqueta.

1. En la Página principal del modelo, haga clic en la pestaña **prueba** .  Esto hará que se ejecute el modelo en los archivos de ejemplo sin etiqueta.
2. En la lista **archivos de prueba** , se mostrarán los archivos de ejemplo y se mostrará si el modelo predictó como ejemplos positivos o negativos. Puede usar esta información para ayudar a determinar la eficacia del clasificador en la identificación de los documentos.

    ![Prueba de archivos sin etiquetar](../media/content-understanding/test-on-files.png) 



## <a name="see-also"></a>Vea también
[Crear un extractor](create-an-extractor.md)</br>
[Información general sobre el documento](document-understanding-overview.md)</br>
[Crear un modelo de procesamiento de formularios](create-a-form-processing-model.md)</br>
[Aplicar un modelo](apply-a-model.md) 




