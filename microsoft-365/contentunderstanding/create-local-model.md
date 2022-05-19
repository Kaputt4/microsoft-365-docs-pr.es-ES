---
title: Creación de un modelo en un sitio de SharePoint local con Microsoft SharePoint Syntex
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
description: Obtenga información sobre cómo crear un modelo local en un sitio de SharePoint local con SharePoint Syntex.
ms.openlocfilehash: bcd3f1f086af3982cb4a3ecc5fe754cf82f09a70
ms.sourcegitcommit: e624221597480295b799d56568c4f6f56d40b41d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2022
ms.locfileid: "65535390"
---
# <a name="create-a-model-on-a-local-sharepoint-site-with-microsoft-sharepoint-syntex"></a>Creación de un modelo en un sitio de SharePoint local con Microsoft SharePoint Syntex

SharePoint Syntex ahora proporciona una opción para crear y entrenar modelos localmente en su propio sitio SharePoint. Estos modelos solo se pueden usar en el sitio donde se crean. 

Al activar la clasificación y extracción de documentos en el sitio de SharePoint, SharePoint Syntex permite clasificar archivos en bibliotecas de documentos, extraer información de archivos nuevos y automatizar actividades basadas en información extraída.

Al activar la creación de modelos locales, se agregarán las siguientes listas y bibliotecas al sitio:

- Biblioteca de documentos de modelos
- Biblioteca de documentos de archivos de entrenamiento
- Lista de plantillas de explicación
- Lista de uso del modelo

Esta característica solo está disponible para crear [modelos de comprensión de documentos](apply-a-model.md) y [modelos precompilados](prebuilt-models.md). 

## <a name="create-a-model-on-a-local-site"></a>Creación de un modelo en un sitio local

1. En una biblioteca de documentos SharePoint, seleccione los archivos que desea analizar y, a continuación, seleccione **Clasificar y extraer**.

    ![Captura de pantalla de una biblioteca de documentos SharePoint con la opción Clasificar y extraer resaltada.](../media/content-understanding/local-model-classify-and-extract-option.png) 

2. La primera vez que use esta característica, activará SharePoint Syntex en su sitio. Verá el siguiente mensaje.

    ![Captura de pantalla de la página Activar información de extracción y clasificación de documentos.](../media/content-understanding/local-model-first-run-activate-message.png) 

    > [!NOTE]
    > Debe tener el permiso Administrar sitio web para realizar tareas de administración y administrar el contenido del sitio. Este sería el propietario del sitio. Una vez activada la característica, cualquier usuario con el permiso Administrar listas podrá crear y administrar modelos.

3. Seleccione **Activar** para continuar. Verá el siguiente mensaje.

    ![Captura de pantalla del mensaje activado Clasificación y extracción de documentos con la opción Crear un modelo.](../media/content-understanding/local-model-activated-message.png) 

4. Seleccione **Crear un modelo**.

5. En el panel **Crear un modelo** , escriba el nombre del modelo, seleccione el tipo de modelo y, a continuación, seleccione **Crear**.

    ![Captura de pantalla del panel Crear un modelo.](../media/content-understanding/local-model-create-a-model.png) 

6. Continúe con el [entrenamiento del modelo de comprensión de documentos](apply-a-model.md) o para [configurar el modelo precompilado](prebuilt-models.md) mediante los archivos que seleccionó.

7. Cuando haya terminado, se abrirá el panel **Agregar a la biblioteca** .

    ![Captura de pantalla del panel Agregar a la biblioteca que muestra el sitio y las bibliotecas aplicadas.](../media/content-understanding/local-model-add-to-library-panel.png) 

8. En el panel **Agregar a la biblioteca**, verá el nombre del sitio de SharePoint y la biblioteca de documentos a la que se aplicará el modelo. Si desea aplicar el modelo a otra biblioteca, seleccione **Volver a las bibliotecas** y elija la biblioteca que desea usar. A continuación, seleccione **Aceptar**.

9. En la página principal del modelo, en la sección **Where the model is applied on this site (Dónde se aplica el modelo en este sitio** ), puede ver las bibliotecas que tienen aplicado el modelo. Para aplicar el modelo a otras bibliotecas del sitio, seleccione **Aplicar modelo**. 

    ![Captura de pantalla de la página principal del modelo que muestra la sección Dónde se aplica el modelo en el sitio.](../media/content-understanding/local-model-home-page.png) 

