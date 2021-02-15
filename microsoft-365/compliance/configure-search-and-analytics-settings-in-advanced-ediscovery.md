---
title: 'Configuración de búsqueda y análisis: eDiscovery avanzado'
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
ms.custom: seo-marvel-mar2020
description: Configure las opciones avanzadas de exhibición de documentos electrónicos que se aplican a todo el conjunto de revisión en un caso. Esto incluye la configuración de análisis y reconocimiento óptico de caracteres.
ms.openlocfilehash: 11932d2172d797ae1913cf28e713d57805ace122
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/05/2021
ms.locfileid: "49751307"
---
# <a name="configure-search-and-analytics-settings-in-advanced-ediscovery"></a>Configurar las opciones de búsqueda y análisis en eDiscovery avanzado

Puede configurar las opciones de cada caso de eDiscovery avanzado para controlar la siguiente funcionalidad.

- Casi duplicados y subprocesos de correo electrónico

- Temas

- Consulta de conjunto de revisión generado automáticamente

- Omitir texto

- Reconocimiento óptico de caracteres

Para configurar las opciones de búsqueda y análisis para un caso:

1. En la **página eDiscovery avanzado,** seleccione el caso.

2. En la **pestaña Configuración,** en **Buscar & análisis**, haga clic en **Seleccionar**.

   Se muestra la página de configuración de casos. Esta configuración se aplica a todos los conjuntos de revisión en un caso.

   ![Configurar las opciones de análisis y búsqueda para un caso de eDiscovery avanzado](../media/AeDCaseSettings.png)

## <a name="near-duplicates-and-email-threading"></a>Casi duplicados y subprocesos de correo electrónico

En esta sección, puede establecer parámetros para la detección de duplicados, la detección de duplicados cercanos y los subprocesos de correo electrónico. Para obtener más información, vea [Detección de duplicados cercanos](near-duplicate-detection-in-advanced-ediscovery.md) y [subprocesos de correo electrónico.](email-threading-in-advanced-ediscovery.md)

- **Casi duplicados/subprocesos de correo electrónico:** Cuando se activa, la detección de duplicados, la detección de duplicados cercanos y los subprocesos de correo electrónico se incluyen como parte del flujo de trabajo al ejecutar análisis en los datos de un conjunto de revisión.

- **Umbral de similitud de documento y correo electrónico:** Si el nivel de similitud de dos documentos está por encima del umbral, ambos documentos se colocarán en el mismo conjunto casi duplicado.

- **Número mínimo/máximo de palabras:** Esta configuración especifica que los duplicados cercanos y el análisis de subprocesos de correo electrónico solo se realizan en documentos que tienen al menos el número mínimo de palabras y, como máximo, el número máximo de palabras.

## <a name="themes"></a>Temas

En esta sección, puede establecer parámetros para los temas. Para obtener más información, vea [Temas](themes-in-advanced-ediscovery.md).

- **Temas:** Cuando está activado, la agrupación en clústeres de temas se realiza como parte del flujo de trabajo al ejecutar análisis en los datos de un conjunto de revisión.

- **Número máximo de temas:** Especifica el número máximo de temas que se pueden generar al ejecutar análisis en los datos de un conjunto de revisión.

- **Incluir números en temas:** Cuando está activado, se incluyen números (que identifican un tema) al generar temas. 

- **Ajustar el número máximo de temas dinámicamente:** En determinadas situaciones, es posible que no haya suficientes documentos en un conjunto de revisión para producir el número de temas deseado. Cuando esta configuración está habilitada, eDiscovery avanzado ajusta el número máximo de temas dinámicamente en lugar de intentar aplicar el número máximo de temas.

## <a name="review-set-query"></a>Consulta de conjunto de revisión

Si activa la **casilla** Crear automáticamente una búsqueda guardada para revisión después del análisis, eDiscovery avanzado genera automáticamente la consulta del conjunto de revisión denominada For **Review.** 

![Consulta de generación automática Para revisión](../media/AeDForReviewQuery.png)

Esta consulta filtra básicamente los elementos duplicados del conjunto de revisión. Esto te permite revisar los elementos únicos del conjunto de revisión. Esta consulta solo se crea cuando se ejecuta el análisis de un conjunto de revisión en el caso. Para obtener más información, acerca de las consultas de conjunto de revisión, [vea Consultar los datos de un conjunto de revisión.](review-set-search.md)

## <a name="ignore-text"></a>Omitir texto

Hay situaciones en las que determinado texto disminuirá la calidad del análisis, como los largos avisos de declinación de responsabilidades que se agregan a los mensajes de correo electrónico independientemente del contenido del correo electrónico. Si conoce el texto que debe omitirse, puede excluirlo del análisis especificando la cadena de texto y la funcionalidad de análisis (Duplicados cercanos, Subprocesos de correo electrónico, Temas y Relevancia) para las que se debe excluir el texto. También se admite el uso de expresiones regulares (RegEx) como texto omitido. 

## <a name="optical-character-recognition-ocr"></a>Reconocimiento óptico de caracteres (OCR)

Cuando esta configuración está activada, el procesamiento ocr se ejecutará en archivos de imagen. El procesamiento de OCR se ejecuta en las siguientes situaciones:

- Cuando los administradores y [orígenes de](non-custodial-data-sources.md) datos que no son administradores se agregan a un caso. El procesamiento de OCR se realiza durante el proceso de indización avanzada. Esto significa que el texto de los archivos de imagen que coincida con los criterios de búsqueda se devolverá en una búsqueda de colección.

- Cuando se agrega contenido de otros orígenes de datos (que no están asociados con un administrador y se agregan al caso en un origen de datos que no es de custodia) a un conjunto de revisión.

Después de agregar datos a un conjunto de revisión, el texto de la imagen se puede revisar, buscar, etiquetar y analizar. Puede ver el texto extraído en el visor de texto del archivo de imagen seleccionado en el conjunto de revisión. Para obtener más información, vea:

- [Clasificación avanzada de los datos de administración](indexing-custodian-data.md)

- [Agregar los resultados de búsqueda a un conjunto de revisión](add-data-to-review-set.md#optical-character-recognition)

- [Tipos de archivo de imagen admitidos](supported-filetypes-ediscovery20.md#image)
