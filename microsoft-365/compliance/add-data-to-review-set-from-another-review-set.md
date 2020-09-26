---
title: Agregar datos de un conjunto de revisión a otro conjunto de revisión
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Obtenga información sobre cómo seleccionar documentos de un conjunto de revisión y trabajar con ellos de forma individual en otro conjunto en un caso de exhibición avanzada de documentos electrónicos.
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: e03cd042ac11c36838e712ccd945bc249b849f43
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285195"
---
# <a name="add-data-to-a-review-set-from-another-review-set"></a>Agregar datos a un conjunto de revisión desde otro conjunto de revisión

En algunos casos, puede ser necesario seleccionar documentos de un conjunto de revisión y trabajar con ellos de forma individual en otro conjunto de revisión. Esto es especialmente útil si ha seleccionado contenido en un conjunto de revisión y desea ejecutar análisis en el subconjunto de datos.

Siga el flujo de trabajo de este artículo para agregar contenido de un conjunto de revisión a otro.

## <a name="create-a-review-set"></a>Crear un conjunto de revisión

Antes de empezar, deberá crear un conjunto de revisiones para agregar los datos.  Se puede Agregar un nuevo conjunto de revisiones en la ficha **Review sets** del caso. Para obtener más información, vea [Create a Review Set](managing-review-sets.md#create-a-review-set).

## <a name="step-1-identify-content-to-add-to-another-review-set"></a>Paso 1: identificar el contenido que se va a agregar a otro conjunto de revisión

Puede agregar contenido de un conjunto de revisión a otro seleccionando documentos específicos en el conjunto de revisión de origen o seleccionando todos los elementos devueltos por el conjunto de revisión consulta. Si está agregando elementos seleccionados, seleccione los elementos, seleccione **acción**y, a continuación, seleccione **Agregar a otro conjunto de revisión**.

![Agregar a otro conjunto de revisión en el menú Acción](../media/64f2a4d4-eba3-4ab3-a3ba-d519feea3142.png)

## <a name="step-2-specify-options-for-adding-to-another-review-set"></a>Paso 2: especificar opciones para agregar a otro conjunto de revisión

En la página **Agregar a otro** control flotante opciones de definición de revisión, elija el conjunto de revisiones al que desea agregar los elementos. Elija si desea agregar **todos los resultados de búsqueda** o los **elementos seleccionados**.  **Información adicional** proporciona opciones para incluir todos los metadatos de los elementos y si desea incluir las etiquetas (activando la casilla de verificación **etiquetas** ) en el conjunto de revisión de origen cuando se agregan los documentos al nuevo conjunto de revisión.  

![Opciones para agregar datos a otro conjunto de revisión](../media/6440ee44-68fd-44d7-b43a-3a477345525c.png)

Después de hacer clic en **Aceptar**, se crea un nuevo trabajo (denominado **Agregar datos a otro conjunto de revisión**) para agregar el contenido a otro conjunto de revisión. Puede ir a la pestaña **trabajos** y supervisar el progreso de este trabajo. Para obtener más información, consulte [Manage Jobs](managing-jobs-ediscovery20.md).
