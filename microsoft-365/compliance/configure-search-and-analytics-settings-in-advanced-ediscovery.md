---
title: Establecer la configuración de búsqueda y análisis
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
description: Configure las opciones avanzadas de eDiscovery que se aplican a todo el conjunto de revisiones en un caso. Esto incluye la configuración de análisis y OCR.
ms.openlocfilehash: 9a7568fac91fa9c021d05b255fc0a145002e7f29
ms.sourcegitcommit: 0b2c41dad19da5f0513097c36a4ff32a5868836c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/11/2020
ms.locfileid: "42588813"
---
# <a name="configure-search-and-analytics-settings"></a>Establecer la configuración de búsqueda y análisis

Puede establecer la configuración de cada caso de exhibición avanzada de documentos electrónicos para controlar las siguientes funciones.

- Duplicación cercana y subprocesamiento de correo electrónico

- Temas

- Consulta de conjunto de revisiones generadas automáticamente

- Omitir texto

- Reconocimiento óptico de caracteres

Para configurar las opciones de búsqueda y análisis para un caso:

1. En la página **exhibición avanzada** de documentos electrónicos, seleccione el caso.

2. En la pestaña **configuración** , en **análisis de & de búsqueda**, haga clic en **seleccionar**.

   Se muestra la página Configuración de casos. Esta configuración se aplica a todos los conjuntos de revisión en un caso.

   ![Configurar los análisis y la configuración de búsqueda para un caso de exhibición avanzada de documentos electrónicos](../media/AeDCaseSettings.png)

## <a name="near-duplicates-and-email-threading"></a>Duplicación cercana y subprocesamiento de correo electrónico

En esta sección, puede establecer parámetros para la detección de duplicados, la detección de mensajes casi duplicados y el hilo de correo electrónico. Para obtener más información, vea cerca de la [detección de duplicados](near-duplicates.md) y el [procesamiento de correo electrónico](email-threading.md).

- **Subprocesos Near duplicados/correo electrónico:** Cuando se activa, la detección de duplicados, la detección de duplicados Near y el procesamiento de correo electrónico se incluyen como parte del flujo de trabajo al ejecutar análisis en los datos de un conjunto de revisión.

- **Umbral de similitud de documento y correo electrónico:** Si el nivel de similitud de dos documentos está por encima del umbral, ambos documentos se colocan en el mismo conjunto Near duplicado.

- **Número mínimo o máximo de palabras:** Estas opciones de configuración especifican que solo se realizan duplicados y análisis de subprocesos de correo electrónico en documentos que tienen como mínimo el número mínimo de palabras y el número máximo de palabras como máximo.

## <a name="themes"></a>Temas

En esta sección, puede establecer parámetros para los temas. Para obtener más información, vea [temas](themes-in-advanced-ediscovery.md).

- **Temas:** Cuando se activa, la agrupación en clústeres de temas se realiza como parte del flujo de trabajo al ejecutar análisis en los datos de un conjunto de revisión.

- **Número máximo de temas:** Especifica el número máximo de temas que se pueden generar al ejecutar análisis en los datos de un conjunto de revisión.

- **Incluir números en los temas:** Cuando se activa, los números (que identifican un tema) se incluyen al generar temas. 

- **Ajustar el número máximo de temas de forma dinámica:** En algunas situaciones, puede que no haya documentos suficientes en un conjunto de revisiones para producir el número de temas deseado. Cuando esta configuración está habilitada, eDiscovery avanzado ajusta el número máximo de temas dinámicamente en lugar de intentar aplicar el número máximo de temas.

## <a name="review-set-query"></a>Revisar establecer consulta

Si activa la casilla de verificación **crear automáticamente una para revisión guardada para revisión después de análisis** , Advanced eDiscovery autogenerará la consulta del conjunto de revisión denominado **para revisión.** 

![La consulta autogenerada para revisión](../media/AeDForReviewQuery.png)

Esta consulta básicamente filtra los elementos duplicados del conjunto de revisión. Esto le permite revisar los elementos únicos en el conjunto de revisión. Esta consulta solo se crea al ejecutar análisis para un conjunto de revisión en el caso. Para obtener más información acerca de las consultas de set View, consulte [consultar los datos de un conjunto de revisión](review-set-search.md).

## <a name="ignore-text"></a>Omitir texto

Hay situaciones en las que cierto texto va a afectar a la calidad de los análisis, como las declinaciones de declinación de responsabilidad que se agregan a los mensajes de correo electrónico independientemente del contenido del correo electrónico. Si sabe que hay texto que debe omitirse, puede excluirlo de análisis especificando la cadena de texto y la funcionalidad de análisis (casi duplicados, subprocesamiento de correo electrónico, temas y relevancia) a la que se debe excluir el texto. También se admite el uso de expresiones regulares (RegEx) como texto omitido. 

## <a name="optical-character-recognition-ocr"></a>Reconocimiento óptico de caracteres (OCR)

Cuando esta opción está activada, OCR se ejecutará en archivos de imagen que se agregan a los conjuntos de revisión para que el texto de la imagen se pueda revisar, buscar, etiquetar y analizar. Puede ver el texto extraído en el visor de texto del archivo de imagen seleccionado en el conjunto de revisiones. Para obtener más información, vea:

- [Agregar los resultados de búsqueda a un conjunto de revisión](add-data-to-review-set.md#optical-character-recognition)

- [Tipos de archivo de imagen admitidos](supported-filetypes-ediscovery20.md#image)
