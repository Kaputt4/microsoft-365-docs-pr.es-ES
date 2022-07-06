---
title: 'Configuración de búsqueda y análisis: eDiscovery (Premium)'
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
ms.custom: seo-marvel-mar2020
description: Configure los valores de Microsoft Purview eDiscovery (Premium) que se aplican a todos los conjuntos de revisión en un caso. Esto incluye la configuración para el análisis y el reconocimiento óptico de caracteres.
ms.openlocfilehash: 315448606e99a768bacd8d7d4ac7f858c79c7bed
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2022
ms.locfileid: "66624573"
---
# <a name="configure-search-and-analytics-settings-in-ediscovery-premium"></a>Configuración de búsqueda y análisis en eDiscovery (Premium)

Puede configurar los valores de cada caso de Microsoft Purview eDiscovery (Premium) para controlar la siguiente funcionalidad.

- Casi duplicados y subprocesos de correo electrónico

- Temas

- Consulta de conjunto de revisión generado automáticamente

- Omitir texto

- Reconocimiento óptico de caracteres

Para configurar las opciones de búsqueda y análisis de un caso:

1. En la página de **eDiscovery (Premium)**, seleccione el caso.

2. En la pestaña **Configuración**, en **Búsqueda y análisis**, haga clic en **Seleccionar**.

   Se muestra la página de configuración del caso. Esta configuración se aplica a todos los conjuntos de revisión en un caso.

   ![Configure los valores de análisis y búsqueda para un caso de exhibición de documentos electrónicos (Premium).](../media/AeDCaseSettings.png)

## <a name="near-duplicates-and-email-threading"></a>Casi duplicados y subprocesos de correo electrónico

En esta sección, puede establecer parámetros para la detección de duplicados, la detección de duplicados cercana y el subproceso de correo electrónico. Para obtener más información, vea [Near duplicate detection (Detección de duplicados cercanos)](near-duplicate-detection-in-advanced-ediscovery.md) y [Email threading (Subprocesos de correo electrónico](email-threading-in-advanced-ediscovery.md)).

- **Subprocesos de correo electrónico o duplicados cercanos:** Cuando está activado, la detección de duplicados, la detección casi duplicada y el subproceso de correo electrónico se incluyen como parte del flujo de trabajo al ejecutar análisis en los datos de un conjunto de revisión.

- **Umbral de similitud de documentos y correo electrónico:** Si el nivel de similitud de dos documentos está por encima del umbral, ambos documentos se colocan en el mismo conjunto casi duplicado.

- **Número mínimo o máximo de palabras:** Esta configuración especifica que los análisis de subprocesos de correo electrónico y duplicados cercanos solo se realizan en documentos que tienen al menos el número mínimo de palabras y, como máximo, el número máximo de palabras.

## <a name="themes"></a>Temas

En esta sección, puede establecer parámetros para los temas. Para obtener más información, vea [Temas](themes-in-advanced-ediscovery.md).

- **Temas:** Cuando está activado, la agrupación en clústeres de temas se realiza como parte del flujo de trabajo al ejecutar análisis en los datos de un conjunto de revisión.

- **Número máximo de temas:** Especifica el número máximo de temas que se pueden generar al ejecutar análisis en los datos de un conjunto de revisión.

- **Incluir números en temas:** Cuando está activado, los números (que identifican un tema) se incluyen al generar temas. 

- **Ajuste el número máximo de temas dinámicamente:** En determinadas situaciones, es posible que no haya suficientes documentos en un conjunto de revisión para generar el número deseado de temas. Cuando esta configuración está activada, eDiscovery (Premium) ajusta el número máximo de temas de forma dinámica en lugar de intentar imponer el número máximo de temas.

## <a name="review-set-query"></a>Consulta de un conjunto de revisión

Si activa la casilla **Crear automáticamente una búsqueda guardada después del análisis** , eDiscovery (Premium) genera automáticamente una consulta de conjunto de revisión denominada **Para revisión.** 

![Consulta generada automáticamente para la revisión.](../media/AeDForReviewQuery.png)

Esta consulta filtra básicamente los elementos duplicados del conjunto de revisión. Esto le permite revisar los elementos únicos del conjunto de revisión. Esta consulta se crea solo al ejecutar análisis para un conjunto de revisión en el caso. Para obtener más información, sobre las consultas de conjuntos de revisión, consulte [Consulta de los datos de un conjunto de revisión](review-set-search.md).

## <a name="ignore-text"></a>Omitir texto

Hay situaciones en las que cierto texto disminuirá la calidad del análisis, como largas declinaciones de responsabilidades que se agregan a los mensajes de correo electrónico independientemente del contenido del correo electrónico. Si sabe de texto que debe omitirse, puede excluirlo del análisis especificando la cadena de texto y la función de análisis (casi duplicados, conversación por correo electrónico, temas y relevancia) para las que se debe excluir el texto. También se admite el uso de expresiones regulares (RegEx) como texto omitido.

## <a name="optical-character-recognition-ocr"></a>Reconocimiento óptico de caracteres (OCR)

Cuando esta configuración está activada, el procesamiento de OCR se ejecutará en archivos de imagen. El procesamiento de OCR se ejecuta en las siguientes situaciones:

- Cuando los custodios y los [orígenes de datos que no son de custodia](non-custodial-data-sources.md) se agregan a un caso. Cuando se aplica OCR a los archivos de imagen, el texto de esos archivos se puede buscar durante una colección. El procesamiento de OCR se realiza durante el proceso [de indexación avanzada](indexing-custodian-data.md) . OCR solo se ejecuta en elementos que se procesan durante la indexación avanzada. Por ejemplo, si durante la indexación avanzada se procesa un archivo PDF de gran tamaño parcialmente indexado o que tenía otros errores de indexación, el archivo también tendrá aplicado OCR. En otras palabras, el procesamiento de OCR solo se produce en los archivos que se vuelven a indexar durante el proceso de indexación avanzada. Esto significa que puede haber situaciones en las que los custodios se agregan a un caso, pero algunos datos adjuntos de correo electrónico no se procesarán para OCR porque esos archivos no se procesan durante la indexación avanzada.

- Cuando el contenido de otros orígenes de datos (que no están asociados a un custodio y que se agregan al caso en un origen de datos que no es de custodia) se agrega a un conjunto de revisión.

Una vez agregados los datos a un conjunto de revisión, se puede revisar, buscar, etiquetar y analizar el texto de la imagen. Puede ver el texto extraído en el Visor de texto del archivo de imagen seleccionado en el conjunto de revisión. Para más información, vea:

- [Clasificación avanzada de los datos de administración](indexing-custodian-data.md)

- [Agregar los resultados de búsqueda a un conjunto de revisión](add-data-to-review-set.md#optical-character-recognition)

- [Tipos de archivo de imagen admitidos](supported-filetypes-ediscovery20.md#image)
