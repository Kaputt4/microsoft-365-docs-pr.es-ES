---
title: Detectar otros modelos entrenados en Microsoft Syntex
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
description: Obtenga información sobre cómo encontrar modelos entrenados que se han aplicado a otros centros de contenido de Microsoft Syntex.
ms.openlocfilehash: 5aa13928095f314812e2bf7bb002c60611352878
ms.sourcegitcommit: 87283bb02ca750286f7c069f811b788730ed5832
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2022
ms.locfileid: "68664333"
---
# <a name="discover-other-trained-models-in-microsoft-syntex"></a>Detectar otros modelos entrenados en Microsoft Syntex

<sup>**Se aplica a:**  &ensp; &#10003; Todos los modelos &ensp; | &ensp; personalizados &#10003; Todos los modelos precompilados</sup>

Antes de crear un nuevo modelo, puede considerar si desea volver a usar uno existente. Puede encontrar y evaluar modelos entrenados creados por otros usuarios de su organización. Esto puede incluir modelos empresariales compartidos entrenados en un centro de contenido u otros modelos locales creados en el mismo sitio. Seleccione el modelo que sea más útil para clasificar los archivos o extraer información específica de ellos. 

## <a name="discover-other-trained-models"></a>Descubrir otros modelos entrenados

Para buscar modelos entrenados que puedan ser adecuados para su contenido:

1. En la biblioteca de documentos del modelo, seleccione **Clasificar y extraer**.

2. En la página **Revistar modelos y aplicar otros nuevos**, puede revisar los modelos aplicados y los modelos que están disponibles para aplicarse a la biblioteca de documentos.

    ![Captura de pantalla de la página Revisar modelos y aplicar otros nuevos que muestra las pestañas Aplicado y Disponible.](../media/content-understanding/review-models-apply-new-ones.png)

   - En la pestaña **Aplicado**, vea los modelos que se han aplicado a la biblioteca. Seleccione **Ver los detalles del modelo** para ver información sobre el modelo, como la descripción, los extractores y otras opciones de configuración.
   
   - En la pestaña **Disponible**, vea los modelos entrenados que están disponibles para aplicarse a la biblioteca.

## <a name="apply-a-trained-model-to-your-library"></a>Aplicación de un modelo entrenado a la biblioteca

Puede evaluar modelos entrenados con respecto a su contenido para ayudarle a encontrar el más adecuado. Para seleccionar un modelo que desee aplicar a la biblioteca:

1. En la página **Revistar modelos y aplicar otros nuevos**, seleccione la pestaña **Disponible** para revisar los modelos de la lista.

    ![Captura de pantalla de la página Revisar modelos y aplicar otros nuevos en la que se muestran los modelos en la pestaña Disponible.](../media/content-understanding/available-models-to-apply.png)

2. Elija el modelo con el que cree que obtendrá los mejores resultados, seleccione **Ver los detalles del modelo** y, a continuación, seleccione **Aplicar a la biblioteca**.

## <a name="get-a-recommendation-for-a-trained-model"></a>Obtener una recomendación para un modelo entrenado

Si no está seguro de qué modelo es el más adecuado para sus archivos, puede solicitar una recomendación. La recomendación podría incluir hasta 10 modelos.

1. En la página **Revisar modelos y aplicar otros nuevos**, seleccione la pestaña **Disponible**.

2. En el primer icono, seleccione **Obtener recomendación**.

    ![Captura de pantalla de la página Revisar modelos y aplicar otros nuevos en la que se muestra la opción Obtener recomendación en la pestaña Disponible.](../media/content-understanding/get-recommendation.png)

3. En la página **Seleccionar uno o varios modelos para el análisis**, seleccione los modelos que considere más adecuados y, a continuación, seleccione **Siguiente**.

    ![Captura de pantalla de la página Seleccionar uno o varios modelos que muestra los modelos recomendados con dos modelos seleccionados.](../media/content-understanding/recommendation-results.png)

4. En la página **Seleccionar un archivo para analizar**, seleccione un archivo del mismo tipo o similar que se almacenará en la biblioteca. Luego elija **Seleccionar**.

    ![Captura de pantalla de la página Seleccionar un archivo para analizar que muestra los archivos disponibles con un archivo seleccionado.](../media/content-understanding/file-to-analyze.png)

5. En la página **Revisar los resultados y seleccionar un modelo**, en **Nuestra recomendación**, verá el archivo recomendado. No es necesario aplicar el modelo recomendado. Puede optar por aplicar otro modelo si cree que es una mejor opción.

    ![Captura de pantalla de la página Revisar resultados y seleccionar un modelo que muestra los modelos recomendados.](../media/content-understanding/review-results.png)

6. Para el modelo con el que crea que obtendrá los mejores resultados, seleccione **Ver detalles del modelo** y, a continuación, seleccione **Aplicar a la biblioteca**.

7. Si no hay ningún modelo recomendado basado en el archivo seleccionado, puede volver atrás y seleccionar otro archivo o seleccionar modelos diferentes.

## <a name="remove-an-applied-model"></a>Quitar un modelo aplicado

> [!NOTE]
> Un modelo debe quitarse de todas las bibliotecas de documentos de SharePoint antes de que se pueda [eliminar](delete-a-model.md) o [cambiar su nombre](rename-a-model.md).

Para quitar un modelo aplicado de la biblioteca de documentos:

1. En la página **Revisar modelos y aplicar otros nuevos**, en la pestaña **Aplicado**, consulte los modelos que se han aplicado a la biblioteca.

2. En el modelo que desee quitar, seleccione **Ver detalles del modelo** y, a continuación, seleccione **Quitar de la biblioteca**.

<!---
## Change the view in a document library

[!INCLUDE [Change the view in a document library](../includes/change-library-view.md)]
--->

## <a name="see-also"></a>Consulte también

[Uso compartido de un modelo de empresa](model-discovery.md)

[Elección de la vista en una biblioteca de documentos](choose-library-view.md)
