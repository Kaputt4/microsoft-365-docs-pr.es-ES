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
description: Obtenga información sobre cómo crear y ejecutar una consulta en un conjunto de revisión para organizar los datos para una revisión más eficaz en un Advanced eDiscovery caso.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 5a03b0c863f9cc2050b18ce83ed11b8a71d1db4d
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2021
ms.locfileid: "52345805"
---
# <a name="query-the-data-in-a-review-set"></a>Consultar los datos de un conjunto de revisión

En la mayoría de los casos, será útil profundizar en los datos de un conjunto de revisión y organizar esos datos para facilitar una revisión más eficaz. El uso de consultas en un conjunto de revisión le ayuda a centrarse en un subconjunto de documentos que cumplen los criterios de la revisión.

## <a name="creating-and-running-a-query-in-a-review-set"></a>Creación y ejecución de una consulta en un conjunto de revisión

Para crear y ejecutar una consulta en los documentos de un conjunto de revisión, **seleccione Nueva consulta** en el conjunto de revisión. Después de nombrar la consulta y definir las condiciones, seleccione **Guardar** para guardar y ejecutar la consulta. Para ejecutar una consulta que se haya guardado anteriormente, seleccione una consulta guardada.

![Revisar consultas de conjunto](../media/AeDReviewSetQueries.png)

## <a name="building-a-review-set-query"></a>Creación de una consulta de conjunto de revisión

Puede crear una consulta mediante una combinación de palabras clave, propiedades y condiciones en la condición Palabras clave. También puede agrupar condiciones como un bloque (denominado grupo *de condiciones)* para crear una consulta más compleja. Para obtener una lista y una descripción de las propiedades de metadatos en las que puede buscar, consulte [Campos de metadatos de documento en eDiscovery avanzado](document-metadata-fields-in-Advanced-eDiscovery.md).

### <a name="conditions"></a>Condiciones

Cada campo que se puede buscar en un conjunto de revisión tiene una condición correspondiente que puede usar para crear la consulta.

Hay varios tipos de condiciones:

- Freetext: se usa una condición de texto libre para campos de texto como subject. Puede enumerar varios términos de búsqueda separlos con una coma.

- Fecha: se usa una condición de fecha para campos de fecha como la fecha de última modificación.

- Opciones de búsqueda: una condición de opciones de búsqueda proporcionará una lista de valores posibles para el campo concreto del conjunto de revisión. Esto se usa para campos, como el remitente, donde hay un número finito de valores posibles en el conjunto de revisión.

- Palabra clave: una condición de palabra clave es una instancia específica de condición de texto libre que puede usar para buscar términos o usar un lenguaje de consulta como KQL en. Vea a continuación para obtener más detalles.

### <a name="query-language"></a>Lenguaje de consulta

Además de las condiciones, puede usar un lenguaje de consulta de tipo KQL en la condición Palabras clave para crear la consulta. El lenguaje de consulta para consultas de conjunto de revisión admite operadores booleanos estándar, como **AND**, **OR**, **NOT** y **NEAR**. También admite un comodín de un solo carácter (?) y un comodín de varios caracteres (*).

## <a name="filters"></a>Filtros

Además de las consultas que puede guardar, puede usar filtros de conjunto de revisión para aplicar rápidamente condiciones adicionales a una consulta de conjunto de revisión. El uso de filtros ayuda a refinar aún más los resultados que muestra una consulta de conjunto de revisión.

![Revisar filtros de conjunto](../media/AeDReviewSetFilters.png)

Los filtros difieren de las consultas de dos maneras significativas:

- Los filtros son transitorios. No persisten más allá de la sesión existente. En otras palabras, no puede guardar un filtro. Las consultas se guardan en el conjunto de revisión y tienen acceso a ellas siempre que abra el conjunto de revisión.

- Los filtros siempre son aditivos. Los filtros se aplican además de la consulta de conjunto de revisión actual. Aplicar una consulta diferente reemplazará los resultados devueltos por la consulta actual.
