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
description: Obtenga información sobre cómo seleccionar documentos de un conjunto de revisión y trabajar con ellos individualmente en otro conjunto en un Advanced eDiscovery caso.
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

En algunos casos, puede que sea necesario seleccionar documentos de un conjunto de revisión y trabajar con ellos individualmente en otro conjunto de revisión. Esto es especialmente útil si ha seleccionado contenido en un conjunto de revisión y quiere ejecutar un análisis en el subconjunto de datos.

Siga el flujo de trabajo de este artículo para agregar contenido de un conjunto de revisión a otro.

## <a name="create-a-review-set"></a>Crear un conjunto de revisión

Antes de empezar, deberá crear un conjunto de revisión para agregar los datos.  Se puede agregar un nuevo conjunto de revisión en la **pestaña Conjuntos de revisión** del caso. Para obtener más información, vea [Create a review set](managing-review-sets.md#create-a-review-set).

## <a name="step-1-identify-content-to-add-to-another-review-set"></a>Paso 1: Identificar el contenido que se agregará a otro conjunto de revisión

Para agregar contenido de un conjunto de revisión a otro, seleccione documentos específicos en el conjunto de revisión de origen o seleccione todos los elementos devueltos por la consulta del conjunto de revisión. Si va a agregar elementos seleccionados, seleccione los elementos, **seleccione Acción** y, a continuación, seleccione Agregar a otro conjunto **de revisión**.

![Agregar a otro conjunto de revisión en el menú Acción](../media/64f2a4d4-eba3-4ab3-a3ba-d519feea3142.png)

## <a name="step-2-specify-options-for-adding-to-another-review-set"></a>Paso 2: Especificar opciones para agregar a otro conjunto de revisión

En la **página desplegable Agregar a otro** conjunto de revisión, elija el conjunto de revisión al que desea agregar los elementos. Elija si desea agregar **Todos los resultados de búsqueda** o Elementos **seleccionados**.  **La** información adicional proporciona opciones para incluir todos los metadatos de  los elementos y si se deben incluir las etiquetas (seleccionando la casilla Etiquetas) del conjunto de revisión de origen cuando se agregan los documentos al nuevo conjunto de revisión.  

![Opciones para agregar datos a otro conjunto de revisión](../media/6440ee44-68fd-44d7-b43a-3a477345525c.png)

Después de hacer clic **en Aceptar,** se crea un nuevo trabajo (denominado **Agregar datos** a otro conjunto de revisión) para agregar el contenido a otro conjunto de opiniones. Puede ir a la pestaña **Trabajos** y supervisar el progreso de este trabajo. Para obtener más información, vea [Administrar trabajos](managing-jobs-ediscovery20.md).
