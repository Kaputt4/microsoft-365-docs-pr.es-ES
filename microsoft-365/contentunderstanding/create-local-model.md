---
title: Crear un modelo en un sitio SharePoint local con Microsoft SharePoint Syntex
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
description: Obtenga información sobre cómo crear un modelo local en un sitio SharePoint local con SharePoint Syntex.
ms.openlocfilehash: f6eab2d081dda379d8eb2c88d762661d374a1db6
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2022
ms.locfileid: "63319192"
---
# <a name="create-a-model-on-a-local-sharepoint-site-with-microsoft-sharepoint-syntex"></a>Crear un modelo en un sitio SharePoint local con Microsoft SharePoint Syntex

SharePoint Syntex ahora proporciona una opción para crear y entrenar modelos localmente en su propio sitio SharePoint web. Estos modelos solo se pueden usar en el sitio donde se crean. 

Al activar la clasificación y extracción de documentos en el sitio de SharePoint, SharePoint Syntex permite clasificar archivos en bibliotecas de documentos, extraer información de nuevos archivos y automatizar actividades basadas en la información extraída.

Al activar la creación de modelos locales, se agregarán las siguientes listas y bibliotecas al sitio:

- Biblioteca de documentos de modelos
- Biblioteca de documentos de archivos de aprendizaje
- Lista de plantillas de explicación
- Lista de uso del modelo

Esta característica solo está disponible para crear modelos [de descripción de documentos](apply-a-model.md) y [modelos precompilado](prebuilt-models.md). 

## <a name="create-a-model-on-a-local-site"></a>Crear un modelo en un sitio local

1. En una SharePoint de documentos, seleccione los archivos que desea analizar y, a continuación, **seleccione Clasificar y extraer**.

    ![Captura de pantalla de una SharePoint de documentos con la opción Clasificar y extraer resaltada.](../media/content-understanding/local-model-classify-and-extract-option.png) 

2. La primera vez que use esta característica, activará los SharePoint Syntex en el sitio. Verá el siguiente mensaje.

    ![Captura de pantalla de la página Activar la clasificación y extracción de documentos.](../media/content-understanding/local-model-first-run-activate-message.png) 

3. Seleccione **Activar** para continuar. Verá el siguiente mensaje.

    ![Captura de pantalla del mensaje de clasificación y extracción de documentos activado con la opción Crear un modelo.](../media/content-understanding/local-model-activated-message.png) 

4. Seleccione **Crear un modelo**.

5. En el panel **Crear un** modelo, escriba el nombre del modelo, seleccione el tipo de modelo y, a continuación, **seleccione Crear**.

    ![Captura de pantalla del panel Crear un modelo.](../media/content-understanding/local-model-create-a-model.png) 

6. Continúe con [la formación del modelo de comprensión de](apply-a-model.md) documentos o [para configurar el modelo precompilado](prebuilt-models.md) con los archivos seleccionados.

7. Cuando haya terminado, **se abrirá el** panel Agregar a la biblioteca.

    ![Captura de pantalla del panel Agregar a la biblioteca que muestra el sitio y las bibliotecas aplicadas.](../media/content-understanding/local-model-add-to-library-panel.png) 

8. En el **panel Agregar a biblioteca**, verá el nombre del sitio SharePoint y la biblioteca de documentos a la que se aplicará el modelo. Si desea aplicar el modelo a una biblioteca diferente, seleccione Volver a **bibliotecas** y elija la biblioteca que desea usar. A continuación, seleccione **Aceptar**.

9. En la página principal del modelo, en la sección **Dónde se** aplica el modelo en este sitio, puede ver las bibliotecas que tienen aplicado el modelo. Para aplicar el modelo a otras bibliotecas del sitio, seleccione **Aplicar modelo**. 

    ![Captura de pantalla de la página principal del modelo que muestra la sección Dónde se aplica el modelo en el sitio.](../media/content-understanding/local-model-home-page.png) 

