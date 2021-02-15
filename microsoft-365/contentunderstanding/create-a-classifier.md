---
title: Crear un clasificador
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Aprenda a crear un clasificador
ms.openlocfilehash: bff23807fce18bf4a585dbb1ec47c1502ab686f6
ms.sourcegitcommit: 78f48304f990e969a052fe6536b2e8d6856e1086
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "50242693"
---
# <a name="create-a-classifier-in-microsoft-sharepoint-syntex"></a>Crear un clasificador en Microsoft SharePoint Syntex


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL0R]  

</br>

Un clasificador es un tipo de modelo que se puede usar para automatizar la identificación y la clasificación de un tipo de documento. Por ejemplo, es posible que quiera identificar todas los *renovaciones de contrato* documentos que se agregan a la biblioteca de documentos, como se muestra en la siguiente ilustración.

![Documento de renovación de contrato](../media/content-understanding/contract-renewal.png)

La creación de un clasificador le permite crear un nuevo [ tipo de contenido de SharePoint](https://docs.microsoft.com/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) que se asociará al modelo.

Al crear el clasificador, debe crear *explicaciones* para definir el modelo. Esto le permite tener en cuenta datos comunes que esperaría encontrar constantemente este tipo de documento. 

Use ejemplos del tipo de documento ("archivos de ejemplo") para "entrenar" al modelo para identificar los archivos que tienen el mismo tipo de contenido.

Para crear un clasificador, es necesario:
1. Nombrar a su modelo.
2. Añadir sus archivos de ejemplo.
3. Etiquetar los archivos de ejemplo.
4. Agregar una explicación
5. Probar el modelo

> [!NOTE]
> Aunque el modelo usa un clasificador para identificar y clasificar los tipos de documentos, también puede elegir extraer fragmentos específicos de información de cada archivo identificado por el modelo. Para ello, cree un **extractor** para agregarlo al modelo. Ver [Crear un extractor](create-an-extractor.md)

## <a name="name-your-model"></a>Nombrar a su modelo

El primer paso para crear el modelo es nombrarlo:

1. En el centro de contenido, seleccione **Nuevo** y, a continuación, **Crear un modelo**.
2. En el panel **Documento nuevo comprender el modelo** en el campo **Nombre** escriba el nombre del modelo. Por ejemplo, si desea identificar documentos de renovación de contratos, puede nombrar al modelo *Renovación de contratos*.
3. Seleccione **Crear**. Esto crea una página principal para el modelo.</br>

    ![Página principal de modelo de clasificador](../media/content-understanding/model-home.png)

Cuando se crea un modelo, también se crea un nuevo tipo de contenido para el sitio. Un tipo de contenido representa una categoría de documentos que tienen características comunes y comparten una colección de columnas o propiedades de metadatos para ese contenido en particular. Los tipos de contenido de SharePoint se administran en la [Galería de tipos de contenido](https://support.microsoft.com/office/create-or-customize-a-site-content-type-27eb6551-9867-4201-a819-620c5658a60f). Para este ejemplo, al crear el modelo, va a crear un nuevo *tipo de contenido* Renovación de contrato.

Seleccionar **Configuración avanzada** si quiere asignar este modelo a un tipo de contenido existente en la galería de tipos de contenido de SharePoint para usar su esquema. Los tipos de contenido de empresa se almacenan en el concentrador de tipo de contenido en el centro de administración de SharePoint y se distribuyen en todos los sitios del espacio empresarial. Tenga en cuenta que, aunque puede usar un tipo de contenido existente para aprovechar su esquema para ayudar con la identificación y la clasificación, aún necesita entrenar el modelo para extraer la información de los archivos que identifica.</br>

![Configuración avanzada](../media/content-understanding/advanced-settings.png)

## <a name="add-your-example-files"></a>Añadir sus archivos de ejemplo

En la Página principal del modelo, agregue los archivos de ejemplo que necesitará para entrenar al modelo para que identifique el tipo de documento. </br>
</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4D0iX] 

</br>

> [!NOTE]
> Debe usar los mismos archivos tanto para el clasificador como para el[entrenador de extracción](create-an-extractor.md). Siempre queda la opción de agregar más después, pero normalmente se agrega un conjunto completo de archivos de ejemplo. Etiquete algunos para entrenar el modelo y pruebe el resto de los no etiquetados para evaluar la idoneidad del modelo. 

Para su conjunto de aprendizaje, puede usar ejemplos positivos y negativos:
- Ejemplo positivo: documentos que representan el tipo de documento. Estos contienen secuencias de datos e información que siempre se encuentran en este tipo de documentos.
- Ejemplo negativo: cualquier otro documento que no representa el documento que desea clasificar. 

Asegúrese de usar al menos cinco ejemplos positivos y al menos un ejemplo negativo para entrenar el modelo.  Se deben crear otros para probar el modelo después del proceso de formación.

Para añadir archivos de ejemplo:

1. En la Página principal del modelo, en el cuadro **Añadir archivos de ejemplo** haga clic en **Añadir archivos**.
2. En la página **seleccionar archivos de ejemplo para el modelo** seleccione los archivos de ejemplo de la biblioteca de archivos de aprendizaje en el centro de contenido. Si aún no se han cargado allí, elija cargarlos ahora haciendo clic en **Cargar** para copiarlos a la biblioteca de archivos de aprendizaje.
3. Después de seleccionar los archivos de ejemplo que se usarán para entrenar el modelo, haga clic en **Añadir**.

    ![Seleccionar archivos de ejemplo:](../media/content-understanding/select-sample.png) 

## <a name="label-your-example-files"></a>Etiquetar los archivos de ejemplo

Después de agregar los archivos de ejemplo, debe etiquetarlos como ejemplos positivos o negativos.

1. En la página principal del modelo, en el cuadro **Clasificar archivos y ejecutar el entrenamiento** haga clic en **Clasificador de documentos**.
   Esto muestra la página de etiquetas que contiene un listado de sus archivos de ejemplo, con el primer archivo visible en el visor.
2. En el visor, en la parte superior del primer archivo de ejemplo, debería ver un texto que pregunta si el archivo es un ejemplo del modelo que acaba de crear. Si es un ejemplo positivo, seleccione **sí**. Si es un ejemplo negativo, seleccione **no**.
3. En la lista **Ejemplos etiquetados** en la parte izquierda, seleccione los archivos adicionales que desea usar como ejemplos y asígneles etiquetas. 

    ![Página principal del Clasificador](../media/content-understanding/classifier-home-page.png) 


> [!NOTE]
> Etiquete como mínimo cinco ejemplos positivos. También debe etiquetar al menos un ejemplo negativo. 

## <a name="create-an-explanation"></a>Crear una explicación

El siguiente paso consiste en crear una explicación en la página de entrenamiento. Una explicación ayuda al modelo a comprender cómo se reconoce el documento. Por ejemplo, los documentos de renovación de contrato siempre contienen una *cadena de texto:* solicitud para divulgación adicional.

> [!Note]
> Cuando se usa con extractores, una explicación identifica la cadena que desea extraer del documento. 

Para crear una explicación:

1. En la Página principal del modelo, seleccione la pestaña **Entrenar** para ir a la página de entrenamiento.
2. En la página entrenamiento, en la sección **archivos entrenados** debería ver una lista de los archivos de ejemplo que etiquetó anteriormente. Seleccione uno de los archivos positivos de la lista, y se mostrará en el visor.
3. En la sección de Explicación, seleccione **Nuevo** y después **En blanco**.
4. En la **página** Crear una explicación:</br>
    a. Escriba el **Nombre** (por ejemplo, "bloque de divulgación").</br>
    b. Seleccione el **Tipo**. Para la muestra, seleccione **Lista de frases**,ya que se añade una cadena de texto.</br>
    c. En el cuadro **Escriba aquí**, escriba la cadena. Agregue "solicitud para divulgación adicional" para el ejemplo. Puede seleccionar **Distinguir mayúsculas de minúsculas** si la cadena tiene que distinguir mayúsculas de minúsculas.</br>
    d. Haga clic en **Guardar**.

    ![Crear una explicación](../media/content-understanding/explanation.png) 
    
5. El centro de contenido ahora comprueba si la explicación que ha creado es lo suficientemente completa como para identificar el resto de los archivos de ejemplo con etiquetas correctamente, como ejemplos positivos y negativos. En la sección archivos entrenados, Compruebe la columna **Evaluación** una vez completada la formación para ver los resultados. Los archivos muestran el valor **Coincidencia**, si las explicaciones que ha creado son suficientes como para coincidir con la etiquetada como positiva o negativa.

    ![Valor de coincidencia](../media/content-understanding/match.png) 

Si recibe una **No coincidencia** en los archivos etiquetados, es posible que tenga que crear una explicación adicional para proporcionar al modelo más información para identificar el tipo de documento. En ese caso, haga clic en el archivo para obtener más información sobre el motivo por el que se ha producido un error de coincidencia.

## <a name="test-your-model"></a>Pruebe el modelo

Si recibe una coincidencia en sus archivos de muestra etiquetados, ahora puede probar su modelo en los archivos de muestra no etiquetados restantes.  Se trata de un paso opcional, pero resulta útil para evaluar la idoneidad del modelo o determinar si está preparado antes de usarlo, y para ello se prueba en archivos que el modelo no ha visto antes.

1. En la página principal del modelo, haga clic en la pestaña **Probar**. Esto ejecuta el modelo en sus archivos de muestra sin etiquetar.
2. En la lista **archivos de prueba**, sus archivos de ejemplo se muestran e indican si el modelo predijo que fueran positivos o negativos. Utilice esta información para ayudar a determinar la eficacia de su clasificador en la identificación de sus documentos.

    ![Probar archivos sin etiquetar](../media/content-understanding/test-on-files.png) 

## <a name="see-also"></a>Consulte también
[Crear un extractor](create-an-extractor.md)

[Información general sobre la comprensión de los documentos](document-understanding-overview.md)

[Tipos de explicación](explanation-types-overview.md)

[Aplicar un modelo](apply-a-model.md) 

[Modo de accesibilidad de SharePoint Syntex](accessibility-mode.md)
