---
title: Aplicar un modelo de comprensión mediante documentos en la sintaxis de Microsoft SharePoint
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.service: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.localizationpriority: medium
description: Obtenga información sobre cómo aplicar un modelo publicado a una biblioteca de documentos de SharePoint en Microsoft SharePoint Syntex.
ms.openlocfilehash: c11e4ba11cdf7da57a344dae774dab7518a72369
ms.sourcegitcommit: 6d86713c3b1da2db338c78fa60bd7d93e24aa6f4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/09/2022
ms.locfileid: "67639644"
---
# <a name="apply-a-document-understanding-model-in-microsoft-sharepoint-syntex"></a>Aplicar un modelo de comprensión mediante documentos en la sintaxis de Microsoft SharePoint

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

Después de publicar el modelo de comprensión de documentos, puede aplicarlo a una o varias bibliotecas de documentos de SharePoint en el inquilino de Microsoft 365.

> [!NOTE]
> Solo puede aplicar el modelo a las bibliotecas de documentos a las que tenga acceso.


## <a name="apply-your-model-to-a-document-library"></a>Aplicación del modelo a una biblioteca de documentos

Para aplicar el modelo a una biblioteca de documentos de SharePoint:

1. En la página principal del modelo, en el icono **Aplicar modelo a bibliotecas** , seleccione **Aplicar modelo**. O bien, en la sección **Dónde se aplica el modelo** , seleccione **+Agregar biblioteca**.

    ![Captura de pantalla de la sección Dónde se aplica el modelo con la opción Agregar biblioteca resaltada.](../media/content-understanding/apply-to-library.png)

2. Después, puede seleccionar el sitio de SharePoint que contiene la biblioteca de documentos a la que desea aplicar el modelo. Si el sitio no aparece en la lista, use el cuadro de búsqueda para encontrarlo.

    ![Seleccione un sitio.](../media/content-understanding/site-search.png)

    > [!NOTE]
    > Debe tener permisos de *Administración de lista* o de *Edición* en la biblioteca de documentos a la que va a aplicar el modelo.

3. Después de seleccionar el sitio, seleccione la biblioteca de documentos a la que quiere aplicar el modelo. En el ejemplo, seleccione la biblioteca de documentos *Documentos* en el sitio de *Seguimiento de casos de Contoso*.

    ![Seleccione una biblioteca de documentos.](../media/content-understanding/select-doc-library.png)

4. Dado que el modelo está asociado a un tipo de contenido, al aplicarlo a la biblioteca, agregará el tipo de contenido y actualizará la vista predeterminada con las etiquetas extraídas que se muestran como columnas. Sin embargo, puede seleccionar **Configuración avanzada** para elegir, opcionalmente, conservar la vista de biblioteca actual o usar una nueva vista con información del modelo y miniaturas de archivo. Si decide mantener la vista de biblioteca actual, las nuevas vistas con información del modelo seguirán estando disponibles en el menú de vista de la biblioteca.

    ![Captura de pantalla de la configuración avanzada que muestra las vistas de la biblioteca.](../media/content-understanding/library-view.png)

    Para obtener más información, vea [Cambiar la vista en una biblioteca de documentos](#change-the-view-in-a-document-library) más adelante en este artículo.

5. Seleccione **Agregar** para aplicar el modelo a la biblioteca.

6. En la página principal del modelo, en la sección **Dónde se aplica el modelo** , debería ver el nombre del sitio de SharePoint en la lista.

7. Vaya a la biblioteca de documentos y asegúrese de estar en la vista de biblioteca de documentos del modelo. Seleccione **Automatizar ver** > **modelos de comprensión de documentos**.

8. En la página **Revisar modelos y aplicar nuevos** , seleccione la pestaña **Aplicado** para ver los modelos que se aplican a la biblioteca de documentos.

    ![Captura de pantalla que muestra la pestaña Aplicado seleccionada y los modelos aplicados.](../media/content-understanding/applied-models.png) 

9. Seleccione **Ver detalles del modelo** para ver información sobre un modelo, como una descripción del modelo, quién publicó el modelo y si el modelo aplica etiquetas de retención o confidencialidad a los archivos que clasifica.

Después de aplicar el modelo a la biblioteca de documentos, puede iniciar la carga de documentos en el sitio y ver los resultados.

El modelo identifica los archivos y carpetas con el tipo de contenido asociado del modelo y los enumera en la vista. Si el modelo tiene extractores, la vista muestra columnas para los datos que se van a extraer de cada archivo o carpeta.

> [!NOTE]
> Si se aplican dos o más modelos de comprensión de documentos a la misma biblioteca, el archivo cargado se clasifica mediante el modelo que tiene la puntuación de confianza media más alta. Las entidades extraídas serán solo del modelo aplicado. <br><br>Si un modelo de procesamiento de formularios personalizado y un modelo de comprensión de documentos se aplican a la misma biblioteca, el archivo se clasifica mediante el modelo de comprensión de documentos y los extractores entrenados para ese modelo. Si hay columnas vacías que coincidan con el modelo de procesamiento de formularios, las columnas se rellenarán con esos valores extraídos.

## <a name="sync-changes-to-one-or-more-libraries"></a>Sincronización de cambios en una o varias bibliotecas

Al publicar un modelo en varias bibliotecas de documentos y, a continuación, actualizar el modelo, como agregar o quitar un extractor, debe insertar la actualización en todas las bibliotecas a las que se ha aplicado el modelo.

Para sincronizar los cambios en todas las bibliotecas aplicadas:

1. En la página principal del modelo, en la sección **Dónde se aplica el modelo** , seleccione **Sincronizar todo**.

    ![Captura de pantalla que muestra la sección Dónde se aplica el modelo y el botón Sincronizar todo resaltado.](../media/content-understanding/sync-all-button.png) 

Para sincronizar los cambios en una o solo las bibliotecas seleccionadas:

1. En la página principal del modelo, en la sección **Dónde se aplica el modelo** , seleccione la biblioteca o bibliotecas a las que desea aplicar los cambios.

2. Seleccione **Sincronizar**.

    ![Captura de pantalla que muestra la sección Dónde se aplica el modelo y el botón Sincronizar resaltado.](../media/content-understanding/sync-button.png) 

## <a name="apply-the-model-to-files-and-folder-content-already-in-the-document-library"></a>Aplicar el modelo a archivos y contenido de carpeta que ya se encuentra en la biblioteca de documentos

Aunque un modelo aplicado procesa todos los archivos y el contenido de carpeta cargados en la biblioteca de documentos después de aplicarlo, también puede hacer lo siguiente para ejecutar el modelo en archivos y contenido de carpeta que ya existen en la biblioteca de documentos antes de que se aplique el modelo:

1. En la biblioteca de documentos, seleccione los archivos y carpetas que desea que procese el modelo.

2. Después de seleccionar los archivos y carpetas, **clasificar y extraer** aparecerá en la cinta de opciones de la biblioteca de documentos. Seleccione **Clasificar y extraer**.

      ![Captura de pantalla que muestra la opción Clasificar y extraer.](../media/content-understanding/extract-classify.png) 

3. Los archivos y carpetas seleccionados se agregarán a la cola que se va a procesar.

    > [!NOTE]
    > Si ha seleccionado una o varias carpetas o está migrando un gran conjunto de archivos, la clasificación puede tardar hasta 24 horas.

### <a name="classification-date-field"></a>Campo Fecha de clasificación

Cuando se aplica un SharePoint Syntex modelo de comprensión de documentos (o un modelo de procesamiento de formularios) a una biblioteca de documentos, el campo **Fecha de clasificación** se incluye en el esquema de la biblioteca. De forma predeterminada, este campo está vacío. Sin embargo, cuando un modelo procesa y clasifica documentos, este campo se actualiza con una marca de fecha y hora de finalización. 

   ![Captura de pantalla de una biblioteca de documentos que muestra la columna Fecha de clasificación.](../media/content-understanding/class-date-column.png) 

El campo **Fecha de clasificación** lo usa el desencadenador [**Cuando un archivo está clasificado por un modelo de comprensión de contenido**](/connectors/sharepointonline/#when-a-file-is-classified-by-a-content-understanding-model) para ejecutar un flujo de Power Automate después de que un modelo haya terminado de procesar el contenido de un archivo o carpeta y haya actualizado el campo **Fecha de clasificación** .

   ![Desencadenador de flujo.](../media/content-understanding/trigger.png)

**El desencadenador When a file is classified by a content understanding model (Cuando un archivo se clasifica mediante un desencadenador de modelo de comprensión de contenido**) se puede usar para iniciar un flujo mediante cualquier información extraída del archivo o carpeta.

Por ejemplo, cuando un modelo se marca con la fecha de **clasificación**, puede usar **enviar un correo electrónico después de SharePoint Syntex procesa un** flujo de archivo para notificar a los usuarios que un nuevo archivo se ha procesado y clasificado por un modelo en la biblioteca de documentos de SharePoint.

Para ejecutar el flujo:

1. Seleccione un archivo y, a continuación, seleccione **Integrar** > **Power Automate** > **Crear un flujo**.

2. En el panel **Crear un flujo**, seleccione **Enviar un correo electrónico después de SharePoint Syntex procese un archivo**.

    ![Captura de pantalla que muestra la opción Crear un panel de flujo y flujo resaltada.](../media/content-understanding/integrate-create-flow.png) 

## <a name="change-the-view-in-a-document-library"></a>Cambio de la vista en una biblioteca de documentos

[!INCLUDE [Change the view in a document library](../includes/change-library-view.md)]

## <a name="see-also"></a>Vea también

[Crear un clasificador](create-a-classifier.md)

[Crear un extractor](create-an-extractor.md)

[Información general de la comprensión mediante documentos ](document-understanding-overview.md)
