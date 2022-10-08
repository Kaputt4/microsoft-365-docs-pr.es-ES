---
title: Tabla DeviceTvmInfoGatheringKB en el esquema de búsqueda avanzada
description: Obtenga información sobre los metadatos de los eventos de evaluación en la tabla DeviceTvmInfoGathering del esquema de búsqueda avanzada.
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, threat & vulnerability management, TVM, device management, software, inventory, vulnerabilities, CVE ID, OS DeviceTvmSoftwareInventoryVulnerabilities, MDVM
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier3
ms.topic: article
ms.openlocfilehash: 0f27247ab6ea04ab15fbdac5fc6803b5aaf9eafb
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68089243"
---
# <a name="devicetvminfogatheringkb"></a>DeviceTvmInfoGatheringKB

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender
- Microsoft Defender para punto de conexión

> [!IMPORTANT]
> Parte de la información se refiere a productos preliminares que pueden ser modificados sustancialmente antes de su lanzamiento comercial. Microsoft no otorga garantías, expresas o implícitas, con respecto a la información que aquí se proporciona.

La `DeviceTvmInfoGatheringKB` tabla del esquema de búsqueda avanzada contiene metadatos para [Administración de vulnerabilidades de Microsoft Defender](/microsoft-365/security/defender-vulnerability-management/defender-vulnerability-management) datos de eventos de evaluación recopilados en la `DeviceTvmInfoGathering` tabla. La `DeviceTvmInfoGatheringKB` tabla contiene la lista de diversas evaluaciones de la configuración y superficie expuesta a ataques usadas por la recopilación de información de Administración de vulnerabilidades de Defender para evaluar los dispositivos. Use esta referencia para crear consultas que devuelvan información de la tabla.

Para obtener información sobre otras tablas del esquema de búsqueda avanzada, consulte la [referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).

| Nombre de columna | Tipo de datos | Descripción |
|-------------|-----------|-------------|
| `IgId` | `string` | Identificador único para la parte de información recopilada |
| `FieldName` | `string` | Nombre del campo donde aparece esta información en la columna AdditionalFields de la tabla DeviceTvmInfoGathering |
| `Description` | `string` | Descripción de la información recopilada |
| `Categories` | `string` | Lista de categorías a las que pertenece la información, en formato de matriz JSON  |
| `DataStructure` | `string` | Estructura de datos de la información recopilada  |

Puede usar esta tabla para explorar los tipos de información disponibles en `DeviceTvmInfoGathering` para que pueda ajustar más adelante la consulta de búsqueda.

Por ejemplo, para ver la lista de información que se recopila, puede probar la siguiente consulta:

```kusto
// Check out what is being collected 
DeviceTvmInfoGatheringKB  
```

A partir de los resultados, supongamos que se interesa por las categorías disponibles, puede usar la siguiente consulta:

```kusto
// Return all available categories 
DeviceTvmInfoGatheringKB 
| mv-expand Categories to typeof(string) 
| distinct Categories 
```

A continuación, supongamos que desea ver las categorías de evaluación que implican el protocolo TLS:

```kusto
// Return all findings for a specified category 
DeviceTvmInfoGatheringKB 
| where Categories contains "tls" 
```

Con los campos resultantes, puede usar la `DeviceTvmInfoGathering` tabla para obtener una lista de dispositivos mediante la versión 1.0 del cliente TLS.

```kusto
// Return all devices on which the TLS version 1.0 is enabled 
DeviceTvmInfoGathering 
| where AdditionalFields.TlsClient10 == "Enabled" or AdditionalFields.TlsServer10 == "Enabled" 
```

## <a name="related-topics"></a>Temas relacionados

- [DeviceTvmInfoGathering](advanced-hunting-devicetvminfogathering-table.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)
- [Información general sobre la administración de vulnerabilidades de Defender](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
