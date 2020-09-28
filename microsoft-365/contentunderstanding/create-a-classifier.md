---
title: Crear un clasificador
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
description: Obtener información sobre cómo crear un clasificador
ms.openlocfilehash: 29b2a4775bec12649c66b4cb4a07fe5f0fc93ae2
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/28/2020
ms.locfileid: "48294907"
---
# <a name="create-a-classifier-in-microsoft-sharepoint-syntex"></a>Crear un clasificador en Microsoft SharePoint Syntex

El contenido de este artículo es para la versión preliminar privada de Project Cortex. [Obtenga más información sobre Project Cortex](https://aka.ms/projectcortex).

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL0R]  

</br>

Un clasificador es un tipo de modelo que puede usar para automatizar la identificación y clasificación de un tipo de documento. Por ejemplo, es posible que desee identificar todos los documentos de *renovación de contratos* que se agregan a la biblioteca de documentos, como se muestra en la siguiente ilustración.

![Documento de renovación de contrato](../media/content-understanding/contract-renewal.png)

La creación de un clasificador permite crear un nuevo [tipo de contenido de SharePoint](https://docs.microsoft.com/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) que se asociará al modelo.

Al crear el clasificador, debe crear *explicaciones* para definir el modelo. Esto le permite anotar datos comunes que espera que encuentren de forma coherente este tipo de documento. 

Use ejemplos del tipo de documento ("archivos de ejemplo") para "entrenar" su modelo para identificar los archivos que tienen el mismo tipo de contenido.

Para crear un clasificador, debe:
1. Asigne un nombre al modelo.
2. Agregue los archivos de ejemplo.
3. Etiquete los archivos de ejemplo.
4. Cree una explicación.
5. Pruebe el modelo.

> [!NOTE]
> Aunque el modelo usa un clasificador para identificar y clasificar los tipos de documentos, también puede optar por extraer fragmentos específicos de información de cada archivo identificado por el modelo. Para ello, cree un **extractor** para agregarlo al modelo. Consulte [Create a extractor](create-an-extractor.md).

## <a name="name-your-model"></a>Asigne un nombre al modelo

El primer paso para crear el modelo es darle un nombre:

1. En el centro de contenido, seleccione **nuevo**y, a continuación, **cree un modelo**.
2. En el panel **nuevo documento que comprende el modelo** , en el campo **nombre** , escriba el nombre del modelo. Por ejemplo, si desea identificar documentos de renovación de contratos, puede asignar un nombre a la *renovación del contrato*del modelo.
3. Seleccione **Crear**. Esto crea una página principal para el modelo.</br>

    ![Página de inicio del modelo de clasificador](../media/content-understanding/model-home.png)

Al crear un modelo, también se crea un nuevo tipo de contenido de SharePoint. Un tipo de contenido de SharePoint representa una categoría de documentos que tienen características comunes y comparten una colección de columnas o propiedades de metadatos para ese contenido en particular. Los tipos de contenido de SharePoint se administran a través de la [Galería de tipos de contenido](https://support.microsoft.com/office/create-or-customize-a-site-content-type-27eb6551-9867-4201-a819-620c5658a60f). En este ejemplo, al crear el modelo, se crea un nuevo tipo de contenido de *renovación de contrato* .

Seleccione **Configuración avanzada** si desea asignar este modelo a un tipo de contenido existente en la galería de tipos de contenido de SharePoint para usar su esquema. Tenga en cuenta que, aunque puede usar un tipo de contenido existente para aprovechar su esquema para ayudar con la identificación y clasificación, debe entrenar el modelo para extraer información de los archivos que identifica.</br>

![Configuración avanzada](../media/content-understanding/advanced-settings.png)

## <a name="add-your-example-files"></a>Adición de los archivos de ejemplo

En la Página principal del modelo, agregue los archivos de ejemplos que necesitará para entrenar el modelo para identificar el tipo de documento. </br>
</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4D0iX] 

</br>

> [!NOTE]
> Debe usar los mismos archivos para la formación de clasificador y [extractor](create-an-extractor.md). Siempre tiene la opción de agregar más adelante, pero normalmente agrega un conjunto completo de archivos de ejemplo. Etiquete algunos para entrenar el modelo y pruebe los restantes no etiquetados para evaluar la idoneidad del modelo. 

Para su conjunto de aprendizaje, desea usar ejemplos positivos y negativos:
- Ejemplo positivo: documentos que representan el tipo de documento. Contienen cadenas e información que siempre estaría en este tipo de documento.
- Ejemplo negativo: documentos que no representan el tipo de documento. Faltan cadenas e información que deben estar presentes en este tipo de documento.

Asegúrese de usar al menos cinco ejemplos positivos y al menos un ejemplo negativo para entrenar el modelo.  Desea crear otros para probar el modelo después del proceso de formación.

Para agregar archivos de ejemplo:

1. En la Página principal del modelo, en el mosaico **biblioteca de ejemplo de compilación** , haga clic en **Agregar archivos**.
2. En la página **seleccionar archivos de ejemplo para el modelo** , seleccione los archivos de ejemplo de la biblioteca de archivos de ejemplo en el centro de contenido. Si todavía no los ha cargado, elija cargarlos ahora haciendo clic en **cargar** para moverlos a la biblioteca de archivos de ejemplo.
3. Después de seleccionar los archivos de ejemplo que se usarán para entrenar el modelo, haga clic en **Agregar**.

    ![Seleccionar archivos de ejemplo](../media/content-understanding/select-sample.png) 

## <a name="label-your-example-files"></a>Etiquetar los archivos de ejemplo

Después de agregar los archivos de ejemplo, debe etiquetarlos como ejemplos positivos o negativos.

1. En el cuadro **clasificar archivos y ejecutar formación** de la Página principal del modelo, haga clic en **formar clasificador**.
   Se muestra la página de etiqueta que muestra una lista de los archivos de ejemplo, con el primer archivo visible en el visor.
2. En el visor de la parte superior del primer archivo de ejemplo, debería ver texto que le preguntará si el archivo es un ejemplo del modelo que acaba de crear. Si es un ejemplo positivo, seleccione **sí**. Si es un ejemplo negativo, seleccione **no**.
3. En la lista de **ejemplos con etiquetas** de la izquierda, seleccione archivos adicionales que desee usar como ejemplos y etiquételo. 

    ![Página principal del clasificador](../media/content-understanding/classifier-home-page.png) 


> [!NOTE]
> Etiquete como mínimo cinco ejemplos positivos y un ejemplo negativo. 

## <a name="create-an-explanation"></a>Crear una explicación

El paso siguiente es para crear una explicación en la página del tren. Una explicación ayuda a que el modelo comprenda cómo reconocer el documento. Por ejemplo, los documentos de renovación de contratos siempre contienen una *solicitud de cadena de texto de divulgación adicional* .

> [!Note]
> Cuando se usa con extractores, una explicación identifica la cadena que se desea extraer del documento. 

Para crear una explicación:

1. En la Página principal del modelo, seleccione la ficha **tren** para ir a la página tren.
2. En la página tren, en la sección **archivos entrenados** , verá una lista de los archivos de ejemplo etiquetados previamente. Seleccione uno de los archivos positivos de la lista y se muestra en el visor.
3. En la sección explicación, seleccione **nuevo** y, a continuación, **en blanco**.
4. En la página **crear una explicación** :</br>
    a. Escriba el **nombre** (por ejemplo, "bloque de revelación").</br>
    b. Seleccione el **tipo**. Para el ejemplo, seleccione **lista de frases**, ya que agrega una cadena de texto.</br>
    c. En el cuadro **Escriba aquí** , escriba la cadena. Para ver el ejemplo, agregue "solicitud de divulgación adicional". Puede seleccionar **mayúsculas** y minúsculas si la cadena debe distinguir mayúsculas de minúsculas.</br>
    d. Haga clic en **Guardar **.

    ![Crear explicación](../media/content-understanding/explanation.png) 
    
 
5. Ahora, el modelo comprueba si la explicación que ha creado fue lo suficientemente buena como para identificar correctamente los archivos de ejemplo con etiquetas restantes como ejemplos positivos y negativos. En la sección archivos entrenados, revise la columna **evaluación** después de que se haya completado el entrenamiento para ver los resultados. Los archivos muestran un valor de **coincidencia**si las explicaciones que ha creado son suficientes para coincidir con lo que ha etiquetado como positivo o negativo.

    ![Valor de coincidencia](../media/content-understanding/match.png) 

Si recibe un error de **coincidencia** con los archivos etiquetados, es posible que deba crear una explicación adicional para proporcionar al modelo más información para identificar el tipo de documento. Si esto ocurre, haga clic en el archivo para obtener más información acerca de por qué se ha producido un error de coincidencia.

## <a name="test-your-model"></a>Probar el modelo

Si ha recibido una coincidencia en los archivos de ejemplo con la etiqueta, ahora puede probar el modelo en los restantes archivos de ejemplo sin etiqueta.

1. En la Página principal del modelo, seleccione la pestaña **prueba** .  Esto ejecuta el modelo en los archivos de ejemplo sin etiqueta.
2. En la lista **archivos de prueba** , los archivos de ejemplo muestran y muestran si el modelo predictó para ser positivos o negativos. Use esta información para ayudar a determinar la eficacia del clasificador en la identificación de los documentos.

    ![Prueba de archivos sin etiquetar](../media/content-understanding/test-on-files.png) 

## <a name="see-also"></a>Consulte también
[Crear un extractor](create-an-extractor.md)</br>
[Información general sobre el documento](document-understanding-overview.md)</br>
[Crear un modelo de procesamiento de formularios](create-a-form-processing-model.md)</br>
[Aplicar un modelo](apply-a-model.md) 
