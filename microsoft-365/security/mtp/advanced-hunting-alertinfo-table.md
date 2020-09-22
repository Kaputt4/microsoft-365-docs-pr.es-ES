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
ms.openlocfilehash: 61efedf8323833b65a5f0b0b857cd83a5c5b085a
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "48198264"
---
# <a name="alertinfo"></a>AlertInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica para:**
- Protección contra amenazas de Microsoft



La `AlertInfo` tabla del esquema de [búsqueda avanzada](advanced-hunting-overview.md) contiene información sobre las alertas de Microsoft defender atp, Office 365 ATP, Microsoft Cloud App Security y Azure ATP. Utilice esta referencia para crear consultas que devuelvan información sobre la tabla.

Para obtener información sobre otras tablas del esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).

| Nombre de columna | Tipo de datos | Descripción |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Fecha y hora en que se registró el evento. |
| `AlertId` | string | Identificador único de alerta. |
| `Title` | cadena | Título de la alerta. |
| `Category` | cadena | Tipo de indicador de amenazas o actividad de vulneración identificada por la alerta |
| `Severity` | cadena | El indicador de amenazas indica el posible impacto (alto, medio o bajo) de las actividades de vulneración identificadas por la alerta. |
| `ServiceSource` | cadena | Producto o servicio que ha proporcionado la información de alerta |
| `DetectionSource` | string | Tecnología o sensor de detección que identificó el componente o la actividad más importante |
| `AttackTechniques` | string | MITRE ATT&CK las técnicas asociadas con la actividad que desencadenó la alerta |

## <a name="related-topics"></a>Temas relacionados
- [Información general sobre la búsqueda avanzada](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades](advanced-hunting-query-emails-devices.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)
