---
title: Consultar el contenido de un conjunto de revisión
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
description: Obtenga información sobre cómo crear y ejecutar una consulta en un conjunto de revisión para organizar el contenido para una revisión más eficaz en un Advanced eDiscovery caso.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 64dbeb8ad68f4188e5768a0a7e0e80ca6c22760b
ms.sourcegitcommit: cc9e3cac6af23f20d7cc5ac6fc6f6e01bc3cc5c5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2021
ms.locfileid: "52736458"
---
# <a name="query-and-filter-content-in-a-review-set"></a>Consultar y filtrar contenido en un conjunto de revisión

En la mayoría de los casos, será útil profundizar en el contenido de un conjunto de revisión y organizarlo para facilitar una revisión más eficaz. El uso de filtros y consultas en un conjunto de revisión le ayuda a centrarse en un subconjunto de documentos que cumplan los criterios de la revisión.

## <a name="default-filters"></a>Filtros predeterminados

En un conjunto de revisión, hay cinco filtros predeterminados que se cargan previamente en el conjunto de revisión:

- Palabras clave
- Fecha
- Sender/Author
- Asunto/Título
- Etiquetas

![Tipos de filtro predeterminados](../media/DefaultFilterTypes.png)

Haga clic en cada filtro para expandirlo y asignar un valor. Haga clic fuera del filtro para aplicar automáticamente el filtro al conjunto de revisión. La siguiente captura de pantalla muestra el filtro Fecha configurado para mostrar documentos dentro de un intervalo de fechas.

![Filtro predeterminado expandido](../media/ExpandedFilter.png)

## <a name="add-or-remove-filters"></a>Agregar o quitar filtros

Para agregar o quitar los filtros que se  muestran para el conjunto de revisión, seleccione Filtros para abrir el panel de filtro, que se muestra en una página desplegable. 

![Panel de filtro](../media/FilterPanel.png)

Los filtros disponibles se organizan en cuatro secciones:

- **Búsqueda:** filtros que proporcionan distintas capacidades de búsqueda.

- **Analytics & codificación predictiva:** filtra las propiedades generadas y agregadas a los documentos al ejecutar el trabajo analítico de correo electrónico de **&** o al usar modelos de codificación predictiva.

- **Identificadores:** filtra todas las propiedades de identificador de los documentos.

- **Propiedades del elemento:** filtra las propiedades del documento. 

Expanda cada sección y seleccione o anule la selección de filtros para agregarlos o quitarlos en el conjunto de filtros. Al agregar un filtro, se muestra en el conjunto de filtros. 

![Lista de secciones y propiedades de filtro en el panel de filtros](../media/FilterPanel2.png)

> [!NOTE]
> Al expandir una sección en el panel de filtros, observará que los tipos de filtro predeterminados están seleccionados. Puede mantener estos seleccionados o anular la selección y quitarlos del conjunto de filtros. 

## <a name="filter-types"></a>Tipos de filtro

Cada campo que se puede buscar en un conjunto de revisión tiene un filtro correspondiente que puede usar para los elementos de filtro en función de un campo específico.

Hay varios tipos de filtros:

- **Freetext:** se aplica un filtro de texto libre a campos de texto como "Subject". Puede enumerar varios términos de búsqueda separlos con una coma.

- **Fecha:** se usa un filtro de fecha para campos de fecha como "Fecha de última modificación".

- **Opciones de** búsqueda: un filtro de opciones de búsqueda proporciona una lista de valores posibles (cada valor se muestra con una casilla que puede seleccionar) para campos concretos de la revisión. Este filtro se usa para campos, como "Sender", donde hay un número finito de valores posibles en el conjunto de revisión.

- **Palabra** clave: una condición de palabra clave es una instancia específica de condición de texto libre que puede usar para buscar términos. También puede usar el lenguaje de consulta de tipo KQL en este tipo de filtro. Para obtener más información, vea las secciones Lenguaje de consulta y Generador de consultas avanzado en este tema.

## <a name="include-and-exclude-filter-relationships"></a>Incluir y excluir relaciones de filtro

Tiene la opción de cambiar la relación de incluir y excluir para un filtro determinado. Por ejemplo, en el filtro Etiqueta, puede excluir elementos **etiquetados** con una etiqueta determinada seleccionando Igual a ninguno en el filtro desplegable. 

![Excluir filtro de etiquetas](../media/TagFilterExclude.png)

## <a name="save-filters-as-queries"></a>Guardar filtros como consultas

Una vez que esté satisfecho con los filtros, puede guardar la combinación de filtros como una consulta de filtro. Esto le permite aplicar el filtro en las sesiones de revisión futuras.

Para guardar un filtro, seleccione **Guardar la consulta** y así mismo. Usted u otros revisores pueden ejecutar consultas de filtro guardadas previamente seleccionando el menú desplegable Consultas **de** filtro guardadas y seleccionando una consulta de filtro para aplicar a los documentos establecidos de revisión. 

![Guardar una consulta de filtro](../media/SaveFilterQuery.png)

Para eliminar una consulta de filtro, abra el panel de filtro y seleccione el icono de papelera junto a la consulta.

![Eliminar una consulta de filtro](../media/DeleteFilterQuery.png)

## <a name="query-language"></a>Lenguaje de consulta

Además de usar filtros, también puede usar un lenguaje de consulta de tipo KQL en el filtro Palabras clave para crear la consulta de búsqueda del conjunto de revisión. El lenguaje de consulta para consultas de conjunto de revisión admite operadores booleanos estándar, como **AND**, **OR**, **NOT** y **NEAR**. También admite un comodín de un solo carácter (?) y un comodín de varios caracteres (*).

## <a name="advanced-query-builder"></a>Generador de consultas avanzada

También puede crear consultas más avanzadas para buscar documentos en un conjunto de revisión.

1. Abra el panel de filtro, seleccione **Filtros** y expanda la **sección** Búsqueda.

  ![Agregar un filtro KQL](../media/AddKQLFilter.png)

2. Seleccione el filtro **KQL y** haga clic **en Abrir generador de consultas**.

   En este panel, puede crear consultas KQL complejas mediante el generador de consultas. Puede agregar condiciones o agregar grupos de condiciones que estén hechos de varias condiciones que estén conectadas lógicamente mediante relaciones **AND** **o OR.**

   ![Usar el generador de consultas para configurar consultas de filtro complejas](../media/ComplexQuery.png)
