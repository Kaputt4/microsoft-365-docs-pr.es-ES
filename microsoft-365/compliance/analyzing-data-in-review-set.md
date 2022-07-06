---
title: Análisis de datos en un conjunto de revisión en eDiscovery (Premium)
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
description: Obtenga información sobre las herramientas disponibles para organizar conjuntos de documentos al analizar un caso de Microsoft Purview eDiscovery (Premium).
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 822c21c05b865bdf1208f7679eaff9ea35b10a9e
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2022
ms.locfileid: "66634839"
---
# <a name="analyze-data-in-a-review-set-in-ediscovery-premium"></a>Análisis de datos en un conjunto de revisión en eDiscovery (Premium)

Cuando el número de documentos recopilados es grande, puede ser difícil revisarlos todos. Microsoft Purview eDiscovery (Premium) proporciona una serie de herramientas para analizar los documentos con el fin de reducir el volumen de documentos que se van a revisar sin pérdida de información y para ayudarle a organizar los documentos de forma coherente. Para obtener más información sobre estas funcionalidades, consulte:

- [Detección de semiduplicados](near-duplicate-detection-in-advanced-ediscovery.md)

- [Subprocesos de correo electrónico](email-threading-in-advanced-ediscovery.md)

- [Temas](themes-in-advanced-ediscovery.md)

## <a name="run-analytics-for-a-review-set"></a>Ejecución de análisis para un conjunto de revisión

Para analizar los datos de un conjunto de revisión:

1. Configure los valores de análisis para su caso. Para obtener más información, consulte [Configuración de las opciones de búsqueda y análisis](configure-search-and-analytics-settings-in-advanced-ediscovery.md).

2. Abra el conjunto de revisión que desea analizar.

3. Haga clic en **Análisis** > **Ejecutar documento & análisis de correo electrónico**.

   ![Seleccione Ejecutar documento & análisis de correo electrónico en la lista desplegable Análisis](..\media\RunAnalytics1.png)

Puede comprobar el progreso del análisis en la pestaña **Trabajos** del caso.

 Una vez completado el análisis, puede ver el informe de análisis, ejecutar consultas dentro del conjunto de revisión en las salidas del análisis (consulte [Consulta dentro del conjunto de revisión](review-set-search.md) y ver los documentos relacionados de un documento determinado (consulte [Revisión de datos en el conjunto de revisión](reviewing-data-in-review-set.md)).

## <a name="using-the-for-review-filter-query"></a>Uso de la consulta de filtro Para revisar

Después de ejecutar análisis para el conjunto de revisiones, puede usar una consulta de filtro generada automáticamente (denominada *Para revisión) que filtre* la revisión para excluir elementos inmateriales, duplicados o no inclusivos. Esto solo le deja con los elementos representativos, únicos e inclusivos en el conjunto de revisión.

Para aplicar la consulta de filtro **Para revisar** a un conjunto de revisiones, seleccione la lista desplegable **Consultas de filtro guardadas** y, a continuación, seleccione **\[AutoGen] Para revisar**.

![Seleccione Para revisar en la lista desplegable Consultas de filtro guardadas](..\media\ForReviewFilterQuery1.png)

Esta es la sintaxis de la consulta de filtro **For Review** :

`(((FileClass="Email") AND (InclusiveType="InclusiveMinus" OR InclusiveType="Inclusive")) OR ((FileClass="Attachment") AND (UniqueInEmailSet="true")) OR ((FileClass="Document") AND (MarkAsRepresentative="Unique")) OR (FileClass="Conversations"))`

En la lista siguiente se describe el resultado de la consulta de filtro en términos de qué contenido se muestra después de aplicarlo al conjunto de revisión.

- **Correo electrónico**. Muestra los elementos marcados como **Inclusive** o **InclusiveMinus**. Un elemento inclusivo es el mensaje final de un subproceso de correo electrónico. Contiene todo el contenido anterior en el subproceso de correo electrónico. Un elemento inclusivo menos contiene uno o varios datos adjuntos asociados al mensaje específico en el subproceso de correo electrónico. Un revisor puede usar el valor menos inclusivo para determinar qué mensajes específicos del subproceso de correo electrónico tienen datos adjuntos asociados.

- **Datos adjuntos**. Filtra los datos adjuntos duplicados en el mismo conjunto de correo electrónico. Solo se muestran los datos adjuntos que son únicos en un subproceso de correo electrónico.

- **Documentos y otros**. Filtra los documentos duplicados. Solo se muestran los documentos que son únicos en el conjunto de revisión.

- **Conversaciones de Teams**. Se muestran todas las conversaciones de Teams (y Yammer) del conjunto de revisión.

Para obtener más información sobre los tipos inclusivos y la unicidad del documento, vea [Subprocesos de correo electrónico en eDiscovery (Premium).](email-threading-in-advanced-ediscovery.md)

> [!NOTE]
> Durante la versión preliminar pública [del nuevo formato de caso](advanced-ediscovery-new-case-format.md) en eDiscovery (Premium), la consulta de filtro **For Review** no devolvió las conversaciones de Teams o Yammer para los conjuntos de revisión (en los casos que usan el formato de mayúsculas y minúsculas) creados antes del 4 de noviembre de 2021. Este problema se ha resuelto. Esto significa que si vuelve a aplicar la consulta **For Review** a un conjunto de revisión en un caso que usa el formato de mayúsculas y minúsculas, es posible que se muestren más elementos que coincidan con la consulta de filtro porque se incluyen todas las conversaciones de Teams o Yammer.

## <a name="analytics-report"></a>Informe de análisis

Para ver el informe de análisis de un conjunto de revisión:

1. Abra el conjunto de revisión.

2. Haga clic en **Análisis** > **Mostrar informes**.

El informe **de Análisis** tiene siete componentes del análisis:

- **Población de destino:** Número de mensajes de correo electrónico, datos adjuntos y documentos sueltos que se encuentran en el conjunto de revisión.

- **Documentos (excluyendo datos adjuntos):** El número de documentos sueltos que son pivotes, únicos cerca de duplicados de una tabla dinámica o un duplicado exacto de otro documento.

- **Correos electrónicos:** Número de mensajes de correo electrónico marcados como inclusivos, copia inclusiva, menos inclusivo o ninguno de los anteriores.

- **Accesorios:** El número de datos adjuntos de correo electrónico que son únicos o duplicados de otros datos adjuntos de correo electrónico en el conjunto de revisión.

- **Número de documentos por tipo de archivo:** Número de archivos, identificados por la extensión de archivo.

- **Documentos por origen:** Un resumen del contenido por su origen de datos original.

- **Documentos agregados por proceso:** Un resumen del contenido mediante procesos de conjunto de revisión. 
