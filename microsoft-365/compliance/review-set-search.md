---
title: Consultar los datos de un conjunto de revisión
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
description: ''
ms.openlocfilehash: 8eadfbeb1a78edd12129c97dc3144a45c5c409cf
ms.sourcegitcommit: caa3f681a68daf5e463093a922c3d6f378143d91
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "39191275"
---
# <a name="query-the-data-in-a-review-set"></a>Consultar los datos de un conjunto de revisión

En la mayoría de los casos, será útil poder profundizar más en los datos de un conjunto de revisión y organizar los datos para facilitar una revisión más eficiente. Usar consultas en un conjunto de revisiones le ayudará a centrarse en un subconjunto de documentos que cumplan los criterios de la revisión.

## <a name="creating-and-running-a-query-in-a-review-set"></a>Crear y ejecutar una consulta en un conjunto de revisiones

Para crear y ejecutar una consulta en los documentos de un conjunto de revisiones, haga clic en **nueva consulta** en el conjunto de revisiones. Después de asignar un nombre a la consulta y definir las condiciones, haga clic en **Guardar** para guardar y ejecutar la consulta. Para ejecutar una consulta que se ha guardado previamente, haga clic en una consulta guardada. 

![Revisar establecer consultas](media/AeDReviewSetQueries.png)

## <a name="building-a-review-set-query"></a>Creación de una consulta de conjunto de revisión

Puede crear una consulta mediante una combinación de tarjetas de condición y lenguaje de consulta en la tarjeta de condición de palabras clave. También puede agrupar las tarjetas de condición como un bloque (denominado *grupo de condición*) para crear una consulta más compleja. Para obtener una lista y una descripción de las propiedades de metadatos que puede buscar, consulte [Document Metadata Fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).

### <a name="condition-cards"></a>Tarjetas de condición

Cada campo de búsqueda de un conjunto de revisión tiene una tarjeta de condición correspondiente que puede usar para crear la consulta.

Hay varios tipos de tarjetas de condición:

- FREETEXT: se usa una tarjeta de condición FREETEXT para los campos de texto, como el asunto. Puede enumerar varios términos de búsqueda separándolos con una coma.

- Fecha: se usa una tarjeta de condición de fecha para los campos de fecha como última fecha de modificación.

- Opciones de búsqueda: una tarjeta de condición de opciones de búsqueda proporcionará una lista de valores posibles para el campo en particular en su conjunto de revisión. Se usa para los campos, como Sender, donde hay un número finito de valores posibles en su conjunto de revisión.

- Palabra clave: una tarjeta de condición de palabra clave es una instancia específica de la tarjeta de condición FREETEXT que puede usar para buscar términos o usar el lenguaje de consulta de tipo KQL en. Consulte a continuación para obtener más detalles.

### <a name="query-language"></a>Lenguaje de consulta

Además de las tarjetas de condición, puede usar un lenguaje de consulta similar a tipo KQL en la tarjeta Keywords para crear la consulta. El lenguaje de consulta para las consultas set de revisión admite operadores booleanos estándar, como AND, OR, NOT y NEAR (n). También admite caracteres comodín de un solo carácter (?) y un comodín de varios caracteres (*).

## <a name="using-filters"></a>Uso de filtros

Además de las consultas que puede guardar, puede usar la revisión Set filters para aplicar rápidamente condiciones adicionales a una consulta de conjunto de revisión. Esto le ayuda a restringir aún más los resultados mostrados por una consulta de conjunto de revisión. 

![Revisar definir filtros](media/AeDReviewSetFilters.png)

Los filtros difieren de las consultas de dos maneras significativas:

- Los filtros son transitorios. No se conservan más allá de la sesión existente. Es decir, no se puede guardar un filtro. Las consultas se guardan en el conjunto de revisión y acceden a ellas cada vez que se abre el conjunto de revisión.

- Los filtros siempre son aditivos. Se aplican filtros además de la consulta del conjunto de revisiones actual. Si se aplica una consulta diferente, se reemplazarán los resultados devueltos por la consulta actual.
