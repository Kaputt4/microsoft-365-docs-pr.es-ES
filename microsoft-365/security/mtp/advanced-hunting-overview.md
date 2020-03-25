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
ms.openlocfilehash: dc91b97f48d6a5ca76c405e4c1006dceb9dc0b34
ms.sourcegitcommit: 3b2fdf159d7dd962493a3838e3cf0cf429ee2bf2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2020
ms.locfileid: "42929033"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting-in-microsoft-threat-protection"></a>Búsqueda proactiva de amenazas con la búsqueda avanzada en la Protección contra amenazas de Microsoft

**Se aplica a:**
- Protección contra amenazas de Microsoft

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

La búsqueda avanzada es una herramienta de búsqueda de amenazas basada en consulta que le permite explorar hasta 30 días de datos sin procesar. Puede inspeccionar eventos de forma proactiva en su red para localizar indicadores y entidades interesantes. El acceso flexible a los datos facilita la búsqueda sin restricciones de las amenazas conocidas y potenciales.

Puede usar las mismas consultas de búsqueda de amenazas para crear reglas de detección personalizadas. Estas reglas se ejecutan automáticamente para comprobar varios eventos y Estados del sistema, así como para responder a ellos, lo que incluye la actividad de infracciones y los equipos mal configurados.

En el centro de seguridad de Microsoft 365, la búsqueda avanzada admite consultas que buscan datos de varias áreas de trabajo, incluidos datos sobre dispositivos, correos electrónicos, aplicaciones e identidades de ATP de Microsoft defender, Office 365 ATP, Microsoft Cloud App Security y Azure ATP. Para usar la búsqueda avanzada, [active la Protección contra amenazas de Microsoft](mtp-enable.md).

## <a name="get-started-with-advanced-hunting"></a>Introducción a la búsqueda avanzada

Le recomendamos que siga los pasos siguientes para empezar a trabajar rápidamente con la búsqueda avanzada.

| Objetivo de aprendizaje | Descripción | Recurso |
|--|--|--|
| **Conozca el idioma** | La búsqueda avanzada está basada en el [lenguaje de consulta de Kusto](https://docs.microsoft.com/azure/kusto/query/) y admite la misma sintaxis y operadores. Empiece a aprender el lenguaje de consulta mediante la ejecución de la primera consulta. | [Introducción al lenguaje de consulta](advanced-hunting-query-language.md) |
| **Obtener información sobre cómo usar los resultados de la consulta** | Obtenga información sobre los gráficos y las distintas formas en que puede ver o exportar los resultados. Descubra cómo puede ajustar rápidamente las consultas y profundizar para obtener información más completa. | [Trabajar con resultados de consulta](advanced-hunting-query-results.md) |
| **Entender el esquema** | Obtenga una visión adecuada y de alto nivel de las tablas en el esquema y sus columnas. Esto le ayudará a determinar dónde buscar datos y cómo crear las consultas. | [Referencia del esquema](advanced-hunting-schema-tables.md) |
| **Aprovechar consultas predefinidas** | Explore colecciones de consultas predefinidas que cubren diferentes escenarios de búsqueda de amenazas. | [Usar consultas compartidas](advanced-hunting-shared-queries.md) |
| **Optimizar las consultas** | Obtenga información acerca de cómo crear consultas eficientes y consultas que combinan datos de mensajes de correo electrónico y dispositivos. | - [Procedimientos recomendados de consulta](advanced-hunting-shared-queries.md) <br>- [Búsqueda en dispositivos y correos electrónicos](advanced-hunting-best-practices.md) |
| **Crear reglas de detección personalizadas** | Comprenda cómo puede usar consultas de búsqueda avanzada para desencadenar alertas y aplicar acciones de respuesta automáticamente. | - [Información general sobre las detecciones personalizadas](custom-detections-overview.md)<br>- [Reglas de detección personalizadas](custom-detection-rules.md) |

## <a name="get-help-as-you-write-queries"></a>Obtener ayuda mientras escribe consultas
Aprovéchese de las funciones siguientes para escribir consultas más rápido:
- **Autosugerir** : cuando se escriben consultas, la búsqueda avanzada ofrece sugerencias de IntelliSense. 
- **Referencia del esquema**: se proporciona una referencia de esquema que incluye la lista de tablas y sus columnas junto al área de trabajo. Para obtener más información, mueva el puntero sobre un elemento. Haga doble clic en un elemento para insertarlo en el editor de consultas.


## <a name="related-topics"></a>Temas relacionados
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Trabajar con resultados de consulta](advanced-hunting-query-results.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Búsqueda de amenazas en dispositivos y mensajes de correo electrónico](advanced-hunting-query-emails-devices.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)
- [Introducción a las detecciones personalizadas](custom-detections-overview.md)