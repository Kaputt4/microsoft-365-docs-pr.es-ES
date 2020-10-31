---
title: Consultar los datos de un conjunto de revisión
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Obtenga información sobre cómo crear y ejecutar una consulta en un conjunto de revisiones para organizar los datos para una revisión más eficiente en un caso de exhibición avanzada de documentos electrónicos.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 1ead897d412af2356d8b57ab8494539a5ed9a019
ms.sourcegitcommit: 3c39866865c8c61bce2169818d8551da65033cfe
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2020
ms.locfileid: "48816573"
---
# <a name="query-the-data-in-a-review-set"></a>Consultar los datos de un conjunto de revisión

En la mayoría de los casos, será útil poder profundizar más en los datos de un conjunto de revisión y organizar los datos para facilitar una revisión más eficiente. Usar consultas en un conjunto de revisiones le ayudará a centrarse en un subconjunto de documentos que cumplan los criterios de la revisión.

## <a name="creating-and-running-a-query-in-a-review-set"></a>Crear y ejecutar una consulta en un conjunto de revisiones

Para crear y ejecutar una consulta en los documentos de un conjunto de revisión, seleccione **nueva consulta** en el conjunto de revisiones. Después de asignar un nombre a la consulta y definir las condiciones, seleccione **Guardar** para guardar y ejecutar la consulta. Para ejecutar una consulta que se ha guardado previamente, seleccione una consulta guardada.

![Revisar establecer consultas](../media/AeDReviewSetQueries.png)

## <a name="building-a-review-set-query"></a>Creación de una consulta de conjunto de revisión

Puede crear una consulta mediante una combinación de palabras clave, propiedades y condiciones en la condición Keywords. También puede agrupar condiciones como un bloque (denominado *grupo de condición* ) para crear una consulta más compleja. Para obtener una lista y una descripción de las propiedades de metadatos que puede buscar, consulte [Document Metadata Fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).

### <a name="conditions"></a>Condiciones

Cada campo de búsqueda de un conjunto de revisión tiene una condición correspondiente que puede usar para crear la consulta.

Hay varios tipos de condiciones:

- FREETEXT: se usa una condición FREETEXT para campos de texto como Subject. Puede enumerar varios términos de búsqueda separándolos con una coma.

- Date: se usa una condición de fecha para los campos de fecha como fecha de última modificación.

- Opciones de búsqueda: una condición de opciones de búsqueda proporcionará una lista de valores posibles para el campo en particular en su conjunto de revisión. Se usa para los campos, como Sender, donde hay un número finito de valores posibles en su conjunto de revisión.

- Palabra clave: una condición de palabra clave es una instancia específica de condición FREETEXT que puede usar para buscar términos o usar el lenguaje de consulta de tipo KQL en. Consulte a continuación para obtener más detalles.

### <a name="query-language"></a>Lenguaje de consulta

Además de las condiciones, puede usar un lenguaje de consulta similar a tipo KQL en la condición Keywords para crear la consulta. El lenguaje de consulta para las consultas set de revisión admite operadores booleanos estándar, como **and** , **or** , **Not** y **Near** . También admite caracteres comodín de un solo carácter (?) y un comodín de varios caracteres (*).

## <a name="filters"></a>Filtros

Además de las consultas que puede guardar, puede usar la revisión Set filters para aplicar rápidamente condiciones adicionales a una consulta de conjunto de revisión. El uso de filtros ayuda a restringir aún más los resultados mostrados por una consulta de conjunto de revisión.

![Revisar definir filtros](../media/AeDReviewSetFilters.png)

Los filtros difieren de las consultas de dos maneras significativas:

- Los filtros son transitorios. No se conservan más allá de la sesión existente. Es decir, no se puede guardar un filtro. Las consultas se guardan en el conjunto de revisión y acceden a ellas cada vez que se abre el conjunto de revisión.

- Los filtros siempre son aditivos. Se aplican filtros además de la consulta del conjunto de revisiones actual. Si se aplica una consulta diferente, se reemplazarán los resultados devueltos por la consulta actual.
