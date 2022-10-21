---
title: Uso compartido de un modelo de empresa en Microsoft Syntex
ms.author: chucked
author: chuckedmonson
manager: pamgreen
audience: admin
ms.reviewer: ssquires
ms.topic: article
ms.service: microsoft-syntex
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.localizationpriority: medium
description: Obtenga información sobre cómo hacer que los modelos entrenados estén disponibles para otros usuarios y cómo aplicar otros modelos entrenados en Microsoft Syntex.
ms.openlocfilehash: 031c5334d2937b077df0dd4f6816c368afab7b11
ms.sourcegitcommit: 87283bb02ca750286f7c069f811b788730ed5832
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2022
ms.locfileid: "68662388"
---
# <a name="share-an-enterprise-model-in-microsoft-syntex"></a>Uso compartido de un modelo de empresa en Microsoft Syntex

<sup>**Se aplica a:**  &ensp; &#10003; Todos los modelos &ensp; | &ensp; personalizados &#10003; Todos los modelos precompilados</sup>

Puede hacer que los modelos empresariales entrenados estén disponibles para que otros usuarios puedan ver y usar directamente desde una biblioteca de documentos de SharePoint. Los modelos empresariales se crean y entrenan en el [centro de contenido](create-a-content-center.md). 

## <a name="share-your-model-with-others"></a>Compartir el modelo con otros usuarios

Para que el modelo entrenado esté disponible para que otros usuarios lo usen:

1. En la página **Modelos** del modelo, seleccione **Configuración del modelo**.

2. En el panel **Configuración del modelo**, en la sección **Sitios donde este modelo está disponible**, seleccione **Editar**.

3. En este momento, **el panel Seleccionar los sitios donde está disponible este modelo** será diferente en función de si es administrador o no. 

    Si es administrador de SharePoint, verá esta vista.

    ![Captura de pantalla del panel Seleccionar los sitios donde está disponible este modelo que muestra las opciones de dónde desea que el modelo esté disponible para otros usuarios.](../media/content-understanding/select-sites.png)

    - **No está disponible en ningún sitio**: el modelo no estará disponible para que lo usen otros usuarios.
    - **Todos los sitios**: el modelo estará disponible en la galería de tipo de contenido para que lo usen otros usuarios.
    - **Solo sitios seleccionados**: puede elegir el sitio o los sitios en los que el modelo estará disponible. Use el cuadro de texto para buscar y elegir los sitios a los que desea aplicar el modelo. Solo verá los sitios a los que tiene acceso.

    Si *no es* administrador de SharePoint, verá esta vista.

    ![Captura de pantalla del panel Seleccionar los sitios donde está disponible este modelo que muestra las opciones para los usuarios finales con solo algunos sitios disponibles.](../media/content-understanding/select-site-user.png)

    Solo puede agregar o quitar la disponibilidad de los sitios específicos a los que ya tiene acceso.

4. Seleccione los sitios en los que desea que el modelo esté disponible para que otros usuarios lo apliquen y, a continuación, seleccione **Guardar**.

## <a name="see-also"></a>Vea también

[Descubrir otros modelos entrenados](discover-other-trained-models.md)
