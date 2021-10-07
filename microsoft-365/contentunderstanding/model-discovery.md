---
title: Publicación y detección de modelos en Microsoft SharePoint Syntex
ms.author: chucked
author: chuckedmonson
manager: pamgreen
audience: admin
ms.reviewer: ssquires
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.localizationpriority: medium
description: Obtenga información sobre cómo poner el modelo entrenado a disposición de otros usuarios y cómo aplicar otros modelos entrenados en Microsoft SharePoint Syntex.
ms.openlocfilehash: 528071efaf06c68d42b34f6d7e509a1839f6ca08
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2021
ms.locfileid: "60201006"
---
# <a name="publish-and-discover-models-in-microsoft-sharepoint-syntex"></a>Publicación y detección de modelos en Microsoft SharePoint Syntex

Puede hacer que los modelos entrenados de comprensión mediante documentos estén disponibles para que otros usuarios puedan verlos y usarlos directamente desde la biblioteca de documentos de SharePoint. 

También puede buscar y evaluar modelos entrenados en otros centros de contenido creados por otros usuarios de su organización. Seleccione el modelo que sea más útil para clasificar los archivos o extraer información específica de ellos. 

> [!NOTE]
> Esta característica no está disponible todavía para los modelos de procesamiento de formularios.

## <a name="make-your-model-discoverable-to-others"></a>Hacer que el modelo sea detectable por parte de otros usuarios

Para que el modelo entrenado esté disponible para que otros usuarios lo usen:

1. En la página **Modelos** del modelo, seleccione **Configuración del modelo**.

2. En el panel **Configuración del modelo**, en la sección **Sitios donde este modelo está disponible**, seleccione **Editar**.

3. En este punto, el panel **Seleccionar los sitios donde está disponible este modelo** será diferente en función de si es administrador o no. 

    Si es administrador, verá esta vista.

    ![Captura de pantalla del panel Seleccionar los sitios donde está disponible este modelo que muestra las opciones de dónde desea que el modelo esté disponible para otros usuarios.](../media/content-understanding/select-sites.png)

    - **No está disponible en ningún sitio**: el modelo no estará disponible para que lo usen otros usuarios.
    - **Todos los sitios**: el modelo estará disponible en la galería de tipo de contenido para que lo usen otros usuarios.
    - **Solo sitios seleccionados**: puede elegir el sitio o los sitios en los que el modelo estará disponible. Haga clic en el cuadro de texto para buscar y elegir los sitios a los que desea aplicar el modelo. Solo verá los sitios a los que tiene acceso.

    Si *no* es un administrador, verá esta vista.

    ![Captura de pantalla del panel Seleccionar los sitios donde está disponible este modelo que muestra las opciones para los usuarios finales con solo algunos sitios disponibles.](../media/content-understanding/select-site-user.png)

    Solo puede agregar o quitar la disponibilidad de los sitios específicos a los que ya tiene acceso.

4. Seleccione los sitios en los que desea que el modelo esté disponible para que otros usuarios lo apliquen y, a continuación, seleccione **Guardar**.

## <a name="discover-other-trained-models"></a>Descubrir otros modelos entrenados

Para buscar modelos entrenados que puedan ser adecuados para su contenido:

1. En la biblioteca de documentos del modelo, seleccione **Automatizar** > **Ver modelos de comprensión mediante documentos**.

2. En la página **Revistar modelos y aplicar otros nuevos**, puede revisar los modelos aplicados y los modelos que están disponibles para aplicarse a la biblioteca de documentos.

    ![Captura de pantalla de la página Revisar modelos y aplicar otros nuevos que muestra las pestañas Aplicado y Disponible.](../media/content-understanding/review-models-apply-new-ones.png)

   - En la pestaña **Aplicado**, vea los modelos que se han aplicado a la biblioteca. Seleccione **Ver los detalles del modelo** para ver información sobre el modelo, como la descripción, los extractores y otras opciones de configuración.
   
   - En la pestaña **Disponible**, vea los modelos entrenados que están disponibles para aplicarse a la biblioteca.


### <a name="apply-a-trained-model-to-your-library"></a>Aplicación de un modelo entrenado a la biblioteca

Puede evaluar modelos entrenados con respecto a su contenido para ayudarle a encontrar el más adecuado. Para seleccionar un modelo que desee aplicar a la biblioteca:

1. En la página **Revistar modelos y aplicar otros nuevos**, seleccione la pestaña **Disponible** para revisar los modelos de la lista.

    ![Captura de pantalla de la página Revisar modelos y aplicar otros nuevos en la que se muestran los modelos en la pestaña Disponible.](../media/content-understanding/available-models-to-apply.png)

2. Elija el modelo con el que cree que obtendrá los mejores resultados, seleccione **Ver los detalles del modelo** y, a continuación, seleccione **Aplicar a la biblioteca**.

### <a name="get-a-recommendation-for-a-trained-model"></a>Obtener una recomendación para un modelo entrenado

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

### <a name="remove-an-applied-model"></a>Quitar un modelo aplicado

Para quitar un modelo aplicado de la biblioteca de documentos:

1. En la página **Revisar modelos y aplicar otros nuevos**, en la pestaña **Aplicado**, consulte los modelos que se han aplicado a la biblioteca.

2. En el modelo que desee quitar, seleccione **Ver detalles del modelo** y, a continuación, seleccione **Quitar de la biblioteca**.


## <a name="see-also"></a>Consulte también

[Aplicar un modelo de comprensión mediante documentos](apply-a-model.md)

[Información general sobre la comprensión de documentos](document-understanding-overview.md)
