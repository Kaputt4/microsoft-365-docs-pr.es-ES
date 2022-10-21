---
title: Creación de un modelo en un sitio local de SharePoint con Microsoft Syntex
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
description: Obtenga información sobre cómo crear un modelo local en un sitio local de SharePoint con Microsoft Syntex.
ms.openlocfilehash: dcd514b0d6656f7a4ce4d181aca348016e7ada53
ms.sourcegitcommit: 87283bb02ca750286f7c069f811b788730ed5832
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2022
ms.locfileid: "68660256"
---
# <a name="create-a-model-on-a-local-sharepoint-site-with-microsoft-syntex"></a>Creación de un modelo en un sitio local de SharePoint con Microsoft Syntex

<sup>**Se aplica a:**  &ensp; &#10003; Todos los modelos personalizados &ensp; | &ensp; &#10003; Todos los modelos entrenados</sup>

Microsoft Syntex proporciona una opción para crear y entrenar modelos localmente en su propio sitio de SharePoint. Estos modelos solo se pueden usar en el sitio donde se crean. 

> [!NOTE]
> Si desea que el modelo sea reconocible y esté disponible para otros usuarios, debe crear un *modelo empresarial*. Un modelo de empresa es un modelo que se crea y entrena en el [centro de contenido](create-a-content-center.md).  

Al activar la clasificación y extracción de documentos en el sitio de SharePoint, Syntex le permite clasificar archivos en bibliotecas de documentos, extraer información de archivos nuevos y automatizar actividades basadas en información extraída.

Al activar la creación de modelos locales, se agregarán las siguientes listas y bibliotecas al sitio:

- Biblioteca de documentos de modelos
- Biblioteca de documentos de archivos de entrenamiento
- Lista de plantillas de explicación
- Lista de uso del modelo

Un modelo se promueve automáticamente al sitio actual solo cuando el modelo se ha aplicado por primera vez a cualquier biblioteca del sitio. Esto hace que el modelo se pueda detectar en la lista de modelos de sitio disponibles y esté disponible para cualquier otra biblioteca del sitio. Hasta que el modelo se aplique a una biblioteca del sitio, no estará disponible. De forma similar, cuando se quita un modelo de todas las bibliotecas del sitio, también se quita de la lista de modelos de sitio disponibles. 

Esta característica está disponible para todos los [tipos de modelo](model-types-overview.md). 

## <a name="create-a-model-on-a-local-site"></a>Creación de un modelo en un sitio local

1. En una biblioteca de documentos de SharePoint, seleccione los archivos que desea analizar y, a continuación, seleccione **Clasificar y extraer**.

    ![Captura de pantalla de una biblioteca de documentos de SharePoint con la opción Clasificar y extraer resaltada.](../media/content-understanding/local-model-classify-and-extract-option.png) 

2. La primera vez que use esta característica, activará Syntex en su sitio. Verá el siguiente mensaje.

    ![Captura de pantalla de la página Activar información de extracción y clasificación de documentos.](../media/content-understanding/local-model-first-run-activate-message.png) 

    > [!NOTE]
    > Debe tener el permiso Administrar sitio web para realizar tareas de administración y administrar el contenido del sitio. Este sería el propietario del sitio. Una vez activada la característica, cualquier usuario con el permiso Administrar listas podrá crear y administrar modelos.

3. Seleccione **Activar** para continuar. Verá el siguiente mensaje.

    ![Captura de pantalla del mensaje activado Clasificación y extracción de documentos con la opción Crear un modelo.](../media/content-understanding/local-model-activated-message.png) 

4. Seleccione **Crear un modelo**.

5. En el panel **Crear un modelo** , escriba el nombre del modelo, seleccione el tipo de modelo y, a continuación, seleccione **Crear**.

    ![Captura de pantalla del panel Crear un modelo.](../media/content-understanding/local-model-create-a-model.png) 

6. Continúe con el [entrenamiento del modelo personalizado](apply-a-model.md) o para [configurar el modelo entrenado](prebuilt-overview.md) mediante los archivos que seleccionó.

7. Cuando haya terminado, se abrirá el panel **Agregar a la biblioteca** .

    ![Captura de pantalla del panel Agregar a la biblioteca que muestra el sitio y las bibliotecas aplicadas.](../media/content-understanding/local-model-add-to-library-panel.png) 

8. En el panel **Agregar a la biblioteca** , verá el nombre del sitio de SharePoint y la biblioteca de documentos a la que se aplicará el modelo. Si desea aplicar el modelo a otra biblioteca, seleccione **Volver a las bibliotecas** y elija la biblioteca que desea usar. A continuación, seleccione **Aceptar**.

9. En la página principal del modelo, en la sección **Where the model is applied on this site (Dónde se aplica el modelo en este sitio** ), puede ver las bibliotecas que tienen aplicado el modelo. Para aplicar el modelo a otras bibliotecas del sitio, seleccione **Aplicar modelo**. 

    ![Captura de pantalla de la página principal del modelo que muestra la sección Dónde se aplica el modelo en el sitio.](../media/content-understanding/local-model-home-page.png) 

> [!NOTE]
> Cuando se aplica un modelo local a una sola biblioteca, está disponible para la detección de aplicaciones en otras bibliotecas del mismo sitio.