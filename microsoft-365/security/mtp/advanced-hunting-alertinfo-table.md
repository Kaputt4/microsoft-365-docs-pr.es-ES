---
title: Tabla AlertInfo en el esquema de búsqueda avanzada
description: Obtenga información sobre los eventos de generación de alertas en la tabla AlertInfo del esquema de búsqueda avanzada.
keywords: caza avanzado, caza de amenazas, búsqueda de amenazas en el ciberespacio, protección contra amenazas de Microsoft, Microsoft 365, MTP, M365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, AlertInfo, alerta, gravedad, categoría, MITRE, ATT&CK, Microsoft defender ATP, MDATP, Office 365 ATP, Microsoft Cloud App Security, MCAS
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
ms.openlocfilehash: e4d7ec213a4b4d1108c06784fb5e6675c79429c1
ms.sourcegitcommit: 3b2fdf159d7dd962493a3838e3cf0cf429ee2bf2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2020
ms.locfileid: "42929521"
---
# <a name="alertinfo"></a>AlertInfo

**Se aplica a:**
- Protección contra amenazas de Microsoft



La `AlertInfo` tabla del esquema de [búsqueda avanzada](advanced-hunting-overview.md) contiene información sobre las alertas de Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security y Azure ATP. Utilice esta referencia para crear consultas que devuelvan información sobre la tabla.

Para obtener información sobre otras tablas del esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).

| Nombre de columna | Tipo de datos | Descripción |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Fecha y hora en que se registró el evento. |
| `AlertId` | string | Identificador único de alerta. |
| `Title` | cadena | Título de la alerta. |
| `Category` | cadena | Tipo de indicador de amenazas o actividad de vulneración identificada por la alerta |
| `Severity` | string | El indicador de amenazas indica el posible impacto (alto, medio o bajo) de las actividades de vulneración identificadas por la alerta. |
| `ServiceSource` | string | Producto o servicio que ha proporcionado la información de alerta |
| `DetectionSource` | string | Tecnología o sensor de detección que identificó el componente o la actividad más importante |
| `AttackTechniques` | string | MITRE ATT&CK las técnicas asociadas con la actividad que desencadenó la alerta |

## <a name="related-topics"></a>Temas relacionados
- [Búsqueda proactiva de amenazas](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Búsqueda de amenazas en dispositivos y mensajes de correo electrónico](advanced-hunting-query-emails-devices.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)
