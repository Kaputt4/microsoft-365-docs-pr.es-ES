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
description: ''
ms.openlocfilehash: fbc2ad99433e2bf296e2891b6f3e85e22b6af6df
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42079937"
---
# <a name="analyze-data-in-a-review-set-in-advanced-ediscovery"></a>Analizar datos en un conjunto de revisión en eDiscovery avanzado

Cuando el número de documentos recopilados es grande, puede ser difícil revisarlos todos. EDiscovery avanzado proporciona una serie de herramientas para analizar los documentos para reducir el volumen de documentos que se van a revisar sin ninguna pérdida de información y para ayudarle a organizar los documentos de forma coherente. Para obtener más información acerca de estas funciones, consulte:

- [Detección de semiduplicados](near-duplicates.md)

- [Subprocesos de correo electrónico](email-threading.md)

- [Temas](themes.md)

Para analizar los datos de un conjunto de revisión:

1. Configure las opciones de análisis en su caso. Para obtener más información, vea [Configure Search and Analytics Settings](configure-search-analytics-settings.md).

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

El informe tiene cuatro componentes del análisis:

- **Desglose** : cuántos mensajes de correo electrónico, datos adjuntos y documentos sueltos se encontraron en el conjunto de revisión.

- **Documentos (sin datos adjuntos)** : Cuántos documentos sueltos eran tablas dinámicas, únicas cerca de duplicados de un pivote o un duplicado exacto de otro documento.

- **Mensajes de correo electrónico:** cuántos mensajes de correo electrónico eran inclusivos, copias inclusivas, menos inclusivas o ninguna de las anteriores.

- **Datos adjuntos** : Cuántos archivos adjuntos de correo electrónico son únicos o duplicados de otro correo electrónico adjunto en el conjunto de revisión.
