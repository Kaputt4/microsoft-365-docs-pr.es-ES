---
title: Aplicar un modelo de comprensión mediante documentos en la sintaxis de Microsoft SharePoint
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
description: Obtenga información sobre cómo aplicar un modelo publicado a una SharePoint de documentos en Microsoft SharePoint Syntex.
ms.openlocfilehash: f8e6cc20b010df5deafe478bbd718946f328a6af
ms.sourcegitcommit: 166bf635c0905ae12c04b1865cb17aadef81e82a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/08/2021
ms.locfileid: "60245734"
---
# <a name="apply-a-document-understanding-model-in-microsoft-sharepoint-syntex"></a>Aplicar un modelo de comprensión mediante documentos en la sintaxis de Microsoft SharePoint

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

Después de publicar el modelo de comprensión de documentos, puede aplicarlo a una o más bibliotecas de documentos SharePoint bibliotecas de documentos de su Microsoft 365 inquilino.

> [!NOTE]
> Solo puede aplicar el modelo a las bibliotecas de documentos a las que tenga acceso.


## <a name="apply-your-model-to-a-document-library"></a>Aplicar el modelo a una biblioteca de documentos

Para aplicar el modelo a una biblioteca de documentos de SharePoint:

1. En la página principal del modelo, en el icono Aplicar modelo a **bibliotecas,** seleccione **Aplicar modelo**. O bien, en la sección Dónde se aplica **el modelo,** seleccione **+Agregar biblioteca**.

    ![Captura de pantalla de la sección Donde se aplica el modelo con la opción Agregar biblioteca resaltada.](../media/content-understanding/apply-to-library.png)

2. Después, puede seleccionar el sitio de SharePoint que contiene la biblioteca de documentos a la que desea aplicar el modelo. Si el sitio no aparece en la lista, use el cuadro de búsqueda para encontrarlo.

    ![Seleccione un sitio.](../media/content-understanding/site-search.png)

    > [!NOTE]
    > Debe tener permisos de *Administración de lista* o de *Edición* en la biblioteca de documentos a la que va a aplicar el modelo.

3. Después de seleccionar el sitio, seleccione la biblioteca de documentos a la que quiere aplicar el modelo. En el ejemplo, seleccione la biblioteca de documentos *Documentos* en el sitio de *Seguimiento de casos de Contoso*.

    ![Seleccione una biblioteca de documentos.](../media/content-understanding/select-doc-library.png)

4. Dado que el modelo está asociado a un tipo de contenido, al aplicarlo a la biblioteca, agregará el tipo de contenido y su vista con las etiquetas extraídas que se muestran como columnas. De forma predeterminada, esta vista es la vista predeterminada de la biblioteca. Sin embargo, si lo desea, puede optar por  no ser la vista predeterminada seleccionando Configuración avanzada y desactivando la casilla Establecer esta nueva vista **como predeterminada.**

    ![Vista Biblioteca.](../media/content-understanding/library-view.png)

5. Seleccione **Agregar** para aplicar el modelo a la biblioteca.

6. En la página principal del modelo, en la sección **Dónde** se aplica el modelo, debería ver el nombre del sitio SharePoint lista.

7. Vaya a la biblioteca de documentos y asegúrese de estar en la vista de biblioteca de documentos del modelo. Seleccione **Automatizar ver** modelos de descripción de  >  **documentos.**

8. En la **página Revisar modelos y** aplicar  nuevos, seleccione la pestaña Aplicado para ver los modelos que se aplican a la biblioteca de documentos.

    ![Captura de pantalla que muestra la pestaña Aplicada seleccionada y los modelos aplicados.](../media/content-understanding/applied-models.png) 

9. Seleccione **Ver** detalles del modelo para ver información sobre un modelo, como una descripción del modelo, quién publicó el modelo y si el modelo aplica etiquetas de retención o confidencialidad a los archivos que clasifica.

Después de aplicar el modelo a la biblioteca de documentos, puede iniciar la carga de documentos en el sitio y ver los resultados.

El modelo identifica los archivos y carpetas con el tipo de contenido asociado del modelo y los enumera en la vista. Si el modelo tiene extractores, la vista muestra las columnas de los datos que va a extraer de cada archivo o carpeta.

## <a name="apply-the-model-to-files-and-folder-content-already-in-the-document-library"></a>Aplicar el modelo a archivos y contenido de carpetas que ya están en la biblioteca de documentos

Aunque un modelo aplicado procesa todos los archivos y el contenido de carpetas cargados en la biblioteca de documentos después de aplicarlo, también puede hacer lo siguiente para ejecutar el modelo en archivos y contenido de carpetas que ya existen en la biblioteca de documentos antes de aplicar el modelo:

1. En la biblioteca de documentos, seleccione los archivos y carpetas que desea procesar el modelo.

2. Después de seleccionar los archivos y carpetas, **Clasificar y extraer** aparecerá en la cinta de opciones de la biblioteca de documentos. Seleccione **Clasificar y extraer**.

      ![Captura de pantalla que muestra la opción Clasificar y extraer.](../media/content-understanding/extract-classify.png) 

3. Los archivos y carpetas seleccionados se agregarán a la cola que se procesará.

    > [!NOTE]
    > Recibirá un mensaje que indica cuánto tiempo puede tardar la clasificación. Si solo ha seleccionado archivos, la clasificación puede tardar hasta 30 minutos. Si ha seleccionado una o más carpetas, la clasificación puede tardar hasta 24 horas.

### <a name="classification-date-field"></a>Campo Fecha de clasificación

Cuando se SharePoint Syntex un modelo de comprensión de documentos o de procesamiento de formularios a una biblioteca de documentos, el campo **Fecha** de clasificación se incluye en el esquema de biblioteca. De forma predeterminada, este campo está vacío. Sin embargo, cuando un modelo procesa y clasifica documentos, este campo se actualiza con una marca de fecha y hora de finalización. 

   ![Captura de pantalla de una biblioteca de documentos que muestra la columna Fecha de clasificación.](../media/content-understanding/class-date-column.png) 

El campo Fecha de [](/connectors/sharepointonline/#when-a-file-is-classified-by-a-content-understanding-model) clasificación lo usa el desencadenador Cuando un modelo de descripción de contenido clasifica un archivo para ejecutar un  flujo de Power Automate después de que un modelo de comprensión de contenido syntex haya terminado de procesar un archivo o carpeta y haya actualizado el campo Fecha de clasificación. 

   ![Flow desencadenador.](../media/content-understanding/trigger.png)

El **desencadenador When a file is classified by a content understanding model** can then be used to start another workflow using any extracted information from the file or folder.



## <a name="see-also"></a>Consulte también

[Crear un clasificador](create-a-classifier.md)

[Crear un extractor](create-an-extractor.md)

[Información general de la comprensión mediante documentos ](document-understanding-overview.md)
