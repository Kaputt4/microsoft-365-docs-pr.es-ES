---
title: Analizar datos en un conjunto de revisión en eDiscovery avanzado
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
description: Obtenga información sobre las herramientas disponibles para organizar conjuntos de documentos al analizar un caso de exhibición avanzada de documentos electrónicos.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 7c63e7eca2e032bfa11c4d4e6f961bb7a7700a4e
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/05/2021
ms.locfileid: "49751375"
---
# <a name="analyze-data-in-a-review-set-in-advanced-ediscovery"></a>Analizar datos en un conjunto de revisión en eDiscovery avanzado

Cuando el número de documentos recopilados es grande, puede ser difícil revisarlos todos. EDiscovery avanzado proporciona una serie de herramientas para analizar los documentos para reducir el volumen de documentos que se van a revisar sin ninguna pérdida de información y para ayudarle a organizar los documentos de forma coherente. Para obtener más información acerca de estas funciones, consulte:

- [Detección de semiduplicados](near-duplicate-detection-in-advanced-ediscovery.md)

- [Subprocesos de correo electrónico](email-threading-in-advanced-ediscovery.md)

- [Temas](themes-in-advanced-ediscovery.md)

Para analizar los datos de un conjunto de revisión:

1. Configure las opciones de análisis en su caso. Para obtener más información, vea [Configure Search and Analytics Settings](configure-search-and-analytics-settings-in-advanced-ediscovery.md).

2. Abra el conjunto de revisiones que desee analizar.

3. Haga clic en **administrar conjunto de revisiones**.

4. Haga clic en **ejecutar análisis para el conjunto de revisión**.

Puede comprobar el progreso del análisis en la ficha **trabajos** del caso.

 Una vez completado el análisis, puede ver el informe de análisis, ejecutar consultas dentro de su conjunto de revisión en los resultados del análisis (vea la [consulta dentro del conjunto de revisión](review-set-search.md)) y ver los documentos relacionados de un documento determinado (vea [revisar los datos en el conjunto de revisiones](reviewing-data-in-review-set.md)).

## <a name="analytics-report"></a>Informe de análisis

Para ver un informe de análisis de un conjunto de revisión:

1. Abra el conjunto de revisión.

2. Haga clic en **administrar conjunto de revisiones**.

3. Haga clic en **Ver informe**.

El informe tiene siete componentes del análisis:

- **Rellenado de destino:** El número de mensajes de correo electrónico, datos adjuntos y documentos sueltos que se encuentran en el conjunto de revisión.

- **Documentos (sin datos adjuntos):** El número de documentos sueltos que son dinámicos, únicos Near duplicados de un pivote o un duplicado exacto de otro documento.

- **Mensajes de correo electrónico:** El número de mensajes de correo electrónico que son inclusivos, copias inclusivas, menos inclusivas o ninguna de las anteriores.

- **Datos adjuntos:** El número de datos adjuntos de correo electrónico que son únicos o duplicados de otro correo electrónico adjunto en el conjunto de revisión.

- **Número de archivos por tipo:** El número de archivos, identificados por extensión de archivo.

- **Documentos por origen:** Un resumen del contenido por su origen de datos original.

- **Documentos agregados por proceso:** Un resumen del contenido de los procesos del conjunto de revisión. 
