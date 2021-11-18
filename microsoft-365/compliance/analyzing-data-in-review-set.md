---
title: Analizar datos en un conjunto de revisión en Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
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
description: Obtenga información sobre las herramientas disponibles para organizar conjuntos de documentos al analizar un Advanced eDiscovery caso.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: dc1bd7b8a717d5f53514209fe50499844644f27b
ms.sourcegitcommit: c2b5ce3150ae998e18a51bad23277cedad1f06c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2021
ms.locfileid: "61064468"
---
# <a name="analyze-data-in-a-review-set-in-advanced-ediscovery"></a>Analizar datos en un conjunto de revisión en Advanced eDiscovery

Cuando el número de documentos recopilados es grande, puede ser difícil revisarlos todos. Advanced eDiscovery proporciona una serie de herramientas para analizar los documentos para reducir el volumen de documentos que se revisarán sin pérdida de información y para ayudarle a organizar los documentos de forma coherente. Para obtener más información sobre estas funcionalidades, vea:

- [Detección de semiduplicados](near-duplicate-detection-in-advanced-ediscovery.md)

- [Subprocesos de correo electrónico](email-threading-in-advanced-ediscovery.md)

- [Temas](themes-in-advanced-ediscovery.md)

## <a name="run-analytics-for-a-review-set"></a>Ejecutar análisis para un conjunto de revisión

Para analizar los datos de un conjunto de revisión:

1. Configure las opciones de análisis para su caso. Para obtener más información, vea [Configure search and analytics settings](configure-search-and-analytics-settings-in-advanced-ediscovery.md).

2. Abra el conjunto de revisión que desea analizar.

3. Haga clic **en Analytics** Ejecutar documento & análisis de  >  **correo electrónico**.

   ![Seleccione Ejecutar análisis de & de correo electrónico en la lista desplegable Análisis](..\media\RunAnalytics1.png)

Puede comprobar el progreso del análisis en la **pestaña Trabajos** del caso.

 Una vez completado el análisis, puede ver el informe de análisis, ejecutar consultas dentro del conjunto de revisión en los resultados del análisis (vea [Consulta](review-set-search.md)dentro del conjunto de revisión) y ver documentos relacionados de un documento determinado (vea [Revisión](reviewing-data-in-review-set.md)de datos en el conjunto de revisión).

## <a name="using-the-for-review-filter-query"></a>Uso de la consulta de filtro Para revisión

Después de ejecutar análisis para el conjunto de opiniones, puede usar una consulta de filtro generada automáticamente (denominada *Para* revisión) que filtra la revisión para excluir elementos inmateriales, duplicados o no incluidos. Esto le deja solo con los elementos que son representativos, únicos e inclusivos en el conjunto de revisión.

Para aplicar la **consulta de** filtro Para revisión a un conjunto de revisión, seleccione la lista desplegable Consultas **de** filtro guardadas y, a continuación, **\[ seleccione AutoGen] Para Revisar**.

![Select For Review from the Saved filter queries dropdown list](..\media\ForReviewFilterQuery1.png)

Esta es la sintaxis de la consulta de filtro **Para** revisión:

`(((FileClass="Email") AND (InclusiveType="InclusiveMinus" OR InclusiveType="Inclusive")) OR ((FileClass="Attachment") AND (UniqueInEmailSet="true")) OR ((FileClass="Document") AND (MarkAsRepresentative="Unique")) OR (FileClass="Conversations"))`

En la siguiente lista se describe el resultado de la consulta de filtro en términos del contenido que se muestra después de aplicarlo al conjunto de revisión.

- **Correo electrónico**. Muestra los elementos marcados como **Inclusive** o **InclusiveMinus**. Un elemento inclusivo es el mensaje final de un subproceso de correo electrónico. Contiene todo el contenido anterior en el subproceso de correo electrónico. Un menos inclusivo contiene uno o más datos adjuntos asociados con el mensaje específico en el subproceso de correo electrónico. Un revisor puede usar el valor menos inclusivo para determinar qué mensajes específicos del subproceso de correo electrónico tienen datos adjuntos asociados.

- **Datos adjuntos**. Filtra los datos adjuntos duplicados en el mismo conjunto de correo electrónico. Solo se muestran los datos adjuntos que son únicos en un subproceso de correo electrónico.

- **Documentos y otros**. Filtra documentos duplicados. Solo se muestran los documentos que son únicos en el conjunto de revisión.

- **Teams conversaciones**. Se muestran Teams (y Yammer) del conjunto de opiniones.

Para obtener más información acerca de los tipos inclusivos y la singularidad de los documentos, vea [Subprocesos de correo](email-threading-in-advanced-ediscovery.md)electrónico en Advanced eDiscovery .

> [!NOTE]
> Durante la vista previa pública del formato de  caso grande en [Advanced eDiscovery](advanced-ediscovery-large-cases.md), la consulta de filtro Para revisión no ha devuelto conversaciones de Teams o Yammer para conjuntos de revisión (en casos que usan el formato de caso grande) creados antes del 4 de noviembre de 2021. Este problema se ha resuelto. Esto significa que si  vuelve a aplicar la consulta Para revisión a un conjunto de revisión en un caso que usa el formato de mayúsculas y minúsculas, se pueden mostrar más elementos que coincidan con la consulta de filtro porque se incluyen todas las conversaciones Teams o Yammer.

## <a name="analytics-report"></a>Informe de análisis

Para ver el informe de análisis de un conjunto de revisión:

1. Abra el conjunto de revisión.

2. Haga clic **en Analytics**  >  **Show reports**.

El **informe de Analytics** tiene siete componentes del análisis:

- **Población objetivo:** Número de mensajes de correo electrónico, datos adjuntos y documentos sueltos que se encuentran en el conjunto de revisión.

- **Documentos (excluyendo datos adjuntos):** El número de documentos sueltos que son pivotes, únicos casi duplicados de un elemento dinámico o un duplicado exacto de otro documento.

- **Correos electrónicos:** El número de mensajes de correo electrónico marcados como una copia inclusiva, inclusiva menos o ninguna de las anteriores.

- **Datos adjuntos:** Número de datos adjuntos de correo electrónico que son únicos o duplicados de otros datos adjuntos de correo electrónico en el conjunto de revisión.

- **Número de documentos por tipo de archivo:** El número de archivos, identificados por extensión de archivo.

- **Documentos por origen:** Un resumen del contenido por su origen de datos original.

- **Documentos agregados por proceso:** Un resumen del contenido mediante procesos de conjunto de revisión. 
