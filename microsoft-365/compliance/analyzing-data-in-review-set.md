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
description: Obtenga información sobre las herramientas disponibles para organizar conjuntos de documentos al analizar un caso de eDiscovery avanzado.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 7c63e7eca2e032bfa11c4d4e6f961bb7a7700a4e
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/05/2021
ms.locfileid: "49751375"
---
# <a name="analyze-data-in-a-review-set-in-advanced-ediscovery"></a>Analizar datos en un conjunto de revisión en eDiscovery avanzado

Cuando el número de documentos recopilados es grande, puede ser difícil revisarlos todos. EDiscovery avanzado proporciona una serie de herramientas para analizar los documentos a fin de reducir el volumen de documentos que se revisarán sin pérdida de información y para ayudarle a organizar los documentos de forma coherente. Para obtener más información sobre estas funcionalidades, vea:

- [Detección de semiduplicados](near-duplicate-detection-in-advanced-ediscovery.md)

- [Subprocesos de correo electrónico](email-threading-in-advanced-ediscovery.md)

- [Temas](themes-in-advanced-ediscovery.md)

Para analizar datos en un conjunto de revisión:

1. Configura las opciones de análisis para tu caso. Para obtener más información, vea [Configuración de búsqueda y análisis.](configure-search-and-analytics-settings-in-advanced-ediscovery.md)

2. Abra el conjunto de revisión que desea analizar.

3. Haga **clic en Administrar conjunto de revisión.**

4. Haga **clic en Ejecutar análisis para el conjunto de revisión.**

Puede comprobar el progreso del análisis en la **ficha Trabajos** del caso.

 Una vez completado el análisis, puede ver el informe de análisis, ejecutar consultas [](review-set-search.md)dentro del conjunto de revisión en los resultados del análisis (vea Consulta dentro del conjunto de revisión) y ver documentos relacionados de un documento determinado (vea Revisión de datos en el conjunto de revisión). [](reviewing-data-in-review-set.md)

## <a name="analytics-report"></a>Informe de análisis

Para ver un informe de análisis de un conjunto de revisión:

1. Abra el conjunto de revisión.

2. Haga **clic en Administrar conjunto de revisión.**

3. Haga clic **en Ver informe.**

El informe tiene siete componentes del análisis:

- **Población objetivo:** El número de mensajes de correo electrónico, datos adjuntos y documentos sueltos que se encuentran en el conjunto de revisión.

- **Documentos (excluyendo datos adjuntos):** El número de documentos sueltos que son tablas dinámicas, duplicados cercanos únicos de un control dinámico o un duplicado exacto de otro documento.

- **Mensajes de correo electrónico:** El número de mensajes de correo electrónico incluidos, copias inclusivas, menos incluidos o ninguno de los anteriores.

- **Datos adjuntos:** El número de datos adjuntos de correo electrónico que son únicos o duplicados de otros datos adjuntos de correo electrónico en el conjunto de revisión.

- **Número de archivos por tipo:** El número de archivos, identificado por extensión de archivo.

- **Documentos por origen:** Un resumen del contenido por su origen de datos original.

- **Documentos agregados por proceso:** Un resumen del contenido por procesos de conjunto de revisión. 
