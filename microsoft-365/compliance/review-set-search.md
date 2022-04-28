---
title: Consulta del contenido de un conjunto de revisión
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Obtenga información sobre cómo crear y ejecutar una consulta en un conjunto de revisión para organizar el contenido para una revisión más eficaz en un caso de exhibición de documentos electrónicos (Premium) de Microsoft Purview.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 44f4b9d6aed92a6593f5c6c70322656e4c770c3d
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "65090925"
---
# <a name="query-and-filter-content-in-a-review-set"></a>Consultar y filtrar el contenido de un conjunto de revisión

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

En la mayoría de los casos, será útil profundizar en el contenido de un conjunto de revisión y organizarlo para facilitar una revisión más eficaz. El uso de filtros y consultas en un conjunto de revisión le ayuda a centrarse en un subconjunto de documentos que cumplen los criterios de la revisión.

## <a name="default-filters"></a>Filtros predeterminados

En un conjunto de revisión, hay cinco filtros predeterminados que se cargan previamente en el conjunto de revisión:

- Palabras clave
- Fecha
- Remitente/autor
- Asunto o título
- Etiquetas

![Tipos de filtro predeterminados.](../media/DefaultFilterTypes.png)

Haga clic en cada filtro para expandirlo y asignar un valor. Haga clic fuera del filtro para aplicar automáticamente el filtro al conjunto de revisión. En la captura de pantalla siguiente se muestra el filtro Fecha configurado para mostrar documentos dentro de un intervalo de fechas.

![Filtro predeterminado expandido.](../media/ExpandedFilter.png)

## <a name="add-or-remove-filters"></a>Adición o eliminación de filtros

Para agregar o quitar filtros que se muestran para el conjunto de revisión, seleccione **Filtros** para abrir el panel de filtros, que se muestra en una página de control flotante. 

![Panel de filtro.](../media/FilterPanel.png)

Los filtros disponibles se organizan en cuatro secciones:

- **Búsqueda**: filtros que proporcionan diferentes funcionalidades de búsqueda.

- **Análisis & codificación predictiva**: filtra las propiedades generadas y agregadas a los documentos cuando se ejecuta el trabajo analítico de document **& correo electrónico** o se usan modelos de codificación predictiva.

- **Identificadores**: filtra todas las propiedades de identificador de los documentos.

- **Propiedades de elemento**: filtros para las propiedades del documento. 

Expanda cada sección y seleccione o anule la selección de filtros para agregarlos o quitarlos en el conjunto de filtros. Al agregar un filtro, se muestra en el conjunto de filtros. 

![Lista de secciones y propiedades de filtro en el panel de filtro.](../media/FilterPanel2.png)

> [!NOTE]
> Al expandir una sección en el panel de filtros, observará que se seleccionan los tipos de filtro predeterminados. Puede mantenerlas seleccionadas o deseleccionarlas y quitarlas del conjunto de filtros. 

## <a name="filter-types"></a>Tipos de filtro

Cada campo que se puede buscar en un conjunto de revisión tiene un filtro correspondiente que puede usar para filtrar elementos basados en un campo específico.

Hay varios tipos de filtros:

- **Freetext**: se aplica un filtro de texto libre a campos de texto como "Subject". Puede enumerar varios términos de búsqueda si los separa con una coma.

- **Fecha**: se usa un filtro de fecha para campos de fecha como "Fecha de última modificación".

- **Opciones de** búsqueda: un filtro de opciones de búsqueda proporciona una lista de valores posibles (cada valor se muestra con una casilla que puede seleccionar) para campos concretos en la revisión. Este filtro se usa para campos, como "Sender", donde hay un número finito de valores posibles en el conjunto de revisión.

- **Palabra clave**: una condición de palabra clave es una instancia específica de la condición freetext que puede usar para buscar términos. También puede usar un lenguaje de consulta similar a KQL en este tipo de filtro. Para obtener más información, consulte las secciones Lenguaje de consulta y Generador de consultas avanzadas de este artículo.

## <a name="include-and-exclude-filter-relationships"></a>Incluir y excluir relaciones de filtro

Puede cambiar la relación de inclusión y exclusión de un filtro determinado. Por ejemplo, en el filtro Etiqueta, puede excluir los elementos etiquetados con una etiqueta determinada seleccionando Igual a **ninguno de** en el filtro desplegable. 

![Excluir filtro de etiquetas.](../media/TagFilterExclude.png)

## <a name="save-filters-as-queries"></a>Guardar filtros como consultas

Una vez que esté satisfecho con los filtros, puede guardar la combinación de filtros como una consulta de filtro. Esto le permite aplicar el filtro en las sesiones de revisión futuras.

Para guardar un filtro, seleccione **Guardar la consulta** y asígnele el nombre . Usted u otros revisores pueden ejecutar consultas de filtro guardadas anteriormente seleccionando la lista desplegable **Consultas de filtro guardadas** y seleccionando una consulta de filtro que se aplicará para revisar los documentos establecidos. 

![Guarde una consulta de filtro.](../media/SaveFilterQuery.png)

Para eliminar una consulta de filtro, abra el panel de filtro y seleccione el icono de papelera situado junto a la consulta.

![Elimine una consulta de filtro.](../media/DeleteFilterQuery.png)

## <a name="query-language"></a>Lenguaje de consulta

Además de usar filtros, también puede usar un lenguaje de consulta similar a KQL en el filtro Palabras clave para compilar la consulta de búsqueda del conjunto de revisión. El lenguaje de consulta de las consultas de conjunto de revisión admite operadores booleanos estándar, como **AND**, **OR**, **NOT** y **NEAR**. También admite un carácter comodín de un solo carácter (?) y un carácter comodín de varios caracteres (*).

## <a name="advanced-query-builder"></a>Generador de consultas avanzadas

También puede crear consultas más avanzadas para buscar documentos en un conjunto de revisión.

1. Abra el panel de filtros, seleccione **Filtros** y expanda la sección **Buscar** .

  ![Agregue un filtro de KQL.](../media/AddKQLFilter.png)

2. Seleccione el filtro **KQL** y haga clic en **Abrir generador de consultas**.

   En este panel, puede crear consultas KQL complejas mediante el generador de consultas. Puede agregar condiciones o agregar grupos de condiciones que se componen de varias condiciones que están conectadas lógicamente por las relaciones **AND** o **OR** .

   ![Use el generador de consultas para configurar consultas de filtro complejas.](../media/ComplexQuery.png)

## <a name="filter-partially-indexed-items"></a>Filtrar elementos parcialmente indizados

Si seleccionó la opción para agregar elementos parcialmente indizados desde orígenes de datos adicionales al confirmar la colección de borradores en un conjunto de revisión. Probablemente querrá identificar y ver esos elementos para determinar si un elemento puede ser relevante para la investigación y si necesita corregir el error que provocó que el elemento se indizase parcialmente.

En este momento, no hay una opción de filtro en un conjunto de revisión para mostrar elementos parcialmente indexados. Pero estamos trabajando en ello. Hasta entonces, esta es una manera de filtrar y mostrar los elementos parcialmente indexados que agregó a un conjunto de revisión.

1. Cree una colección y confírmela en un nuevo conjunto de revisión *sin* agregar elementos indizados parcialmente desde los orígenes de datos adicionales.

2. Cree una nueva colección copiando la colección del paso 1.

3. Confirme la nueva colección en el mismo conjunto de revisión. Pero esta vez, agregue los elementos parcialmente indizados de los orígenes de datos adicionales. Dado que los elementos de la colección que creó en el paso 1 ya se han agregado al conjunto de revisión, solo los elementos indizados parcialmente de la segunda colección se agregan al conjunto de revisión.

4. Una vez agregadas ambas colecciones al conjunto de revisión, vaya al conjunto de revisión y seleccione **AdministrarInstalar** >  **conjuntos**.

5. Copie o anote el **identificador de carga** de la segunda colección (el que creó en el paso 2). El nombre de la colección se identifica en la columna **Información de origen** .

6. De nuevo en el conjunto de revisión, haga clic en **Filtrar**, expanda la sección **Identificadores** y, a continuación, active la casilla **Id. de carga** .

7. Expanda el filtro **Load Id (Id** . de carga) y, a continuación, active la casilla del id. de carga que corresponde a la segunda colección para mostrar los elementos parcialmente indexados.
