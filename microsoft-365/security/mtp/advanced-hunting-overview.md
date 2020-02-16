---
title: Información general sobre la búsqueda avanzada en la Protección contra amenazas de Microsoft
description: Obtenga más información sobre las consultas de búsqueda avanzada en Microsoft 365 y cómo usarlas para encontrar de forma proactiva amenazas y debilidades en la red
keywords: caza avanzado, caza de amenazas, búsqueda de amenazas en el ciberespacio, protección contra amenazas de Microsoft, Microsoft 365, MTP, M365, búsqueda, consulta, telemetría, detecciones personalizadas, esquema, kusto, Microsoft 365, protección contra amenazas de Microsoft
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: f268c87da68c2badbfa885f0d9357a6a53d0a039
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42087508"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting-in-microsoft-threat-protection"></a>Búsqueda proactiva de amenazas con la búsqueda avanzada en la Protección contra amenazas de Microsoft

**Se aplica a:**
- Protección contra amenazas de Microsoft

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

La búsqueda avanzada es una herramienta de búsqueda de amenazas basada en consulta que le permite explorar hasta 30 días de datos sin procesar. Puede inspeccionar eventos de forma proactiva en su red para localizar indicadores y entidades interesantes. El acceso flexible a los datos facilita la búsqueda sin restricciones de las amenazas conocidas y potenciales.

En el centro de seguridad de Microsoft 365, la búsqueda avanzada admite consultas que buscan datos de ATP de Microsoft defender, datos de cobertura de dispositivos integrados y Office 365 ATP, que proporcionan datos de los correos electrónicos. Para usar la búsqueda avanzada, [active la Protección contra amenazas de Microsoft](mtp-enable.md).

## <a name="get-started-with-advanced-hunting"></a>Introducción a la búsqueda avanzada

Le recomendamos que siga los pasos siguientes para empezar a trabajar rápidamente con la búsqueda avanzada.

| Objetivo de aprendizaje | Descripción | Recurso |
|--|--|--|
| **Conozca el idioma** | La búsqueda avanzada está basada en el [lenguaje de consulta de Kusto](https://docs.microsoft.com/azure/kusto/query/) y admite la misma sintaxis y operadores. Empiece a aprender el lenguaje de consulta mediante la ejecución de la primera consulta. | [Introducción al lenguaje de consulta](advanced-hunting-query-language.md) |
| **Entender el esquema** | Obtenga una visión adecuada y de alto nivel de las tablas en el esquema y sus columnas. Esto le ayudará a determinar dónde buscar datos y cómo crear las consultas. | [Referencia del esquema](advanced-hunting-schema-tables.md) |
| **Usar consultas predefinidas** | Explore colecciones de consultas predefinidas que cubren diferentes escenarios de búsqueda de amenazas. | [Usar consultas compartidas](advanced-hunting-shared-queries.md)
| **Optimizar las consultas** | Obtenga información acerca de cómo crear consultas eficientes y consultas que combinan datos de mensajes de correo electrónico y dispositivos. | [Procedimientos recomendados de consulta](advanced-hunting-shared-queries.md), [buscar entre dispositivos y mensajes de correo electrónico](advanced-hunting-best-practices.md)

## <a name="get-help-as-you-write-queries"></a>Obtener ayuda mientras escribe consultas
Aprovéchese de las funciones siguientes para escribir consultas más rápido:
- **Sugerencias automáticas**: cuando escribe consultas, la búsqueda avanzada ofrece sugerencias. 
- **Referencia del esquema**: se proporciona una referencia de esquema que incluye la lista de tablas y sus columnas junto al área de trabajo. Para obtener más información, mueva el puntero sobre un elemento. Haga doble clic en un elemento para insertarlo en el editor de consultas.

## <a name="drilldown-from-query-results"></a>Desglose de los resultados de la consulta
Para ver más información sobre las entidades, como máquinas, archivos, usuarios, direcciones IP y URL, en los resultados de la consulta, simplemente haga clic en el identificador de entidad. Se abrirá la página de perfil detallado de la entidad seleccionada en el Centro de seguridad de Microsoft Defender.

## <a name="tweak-your-queries-from-the-results"></a>Modificar las consultas de los resultados
Haga clic con el botón derecho en un valor en el conjunto de resultados para mejorar la búsqueda rápidamente. Puede usar las opciones para:

- Buscar explícitamente el valor seleccionado (`==`)
- Excluir el valor seleccionado de la consulta (`!=`)
- Obtenga más operadores avanzados para agregar el valor a la consulta, como `contains`, `starts with` y `ends with` 

![Imagen del conjunto de resultados de la búsqueda avanzado ATP de Microsoft Defender](../../media/advanced-hunting-results-filter.png)

## <a name="filter-the-query-results"></a>Filtrar los resultados de la consulta
Los filtros que aparecen a la derecha proporcionan un resumen del conjunto de resultados. Cada columna tiene una sección en la que se muestra una lista de los valores de la columna y el número de instancias.

Para refinar la consulta, seleccione los botones "+" o "-" que aparecen en los valores que desea incluir o excluir y, a continuación, seleccione **ejecutar consulta**.

![Imagen del filtro de búsqueda avanzada](../../media/advanced-hunting-filter.png)

Cuando aplica el filtro para modificar la consulta y, a continuación, ejecuta la consulta, los resultados se actualizan en consecuencia.

## <a name="related-topics"></a>Temas relacionados
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Búsqueda de amenazas en dispositivos y mensajes de correo electrónico](advanced-hunting-query-emails-devices.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)
