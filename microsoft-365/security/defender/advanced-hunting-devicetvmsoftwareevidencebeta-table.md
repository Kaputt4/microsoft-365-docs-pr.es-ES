---
title: Tabla DeviceTvmSoftwareEvidenceBeta en el esquema de búsqueda avanzada
description: Obtenga información sobre cómo usar la tabla DeviceTvmSoftwareEvidenceBeta en el esquema de búsqueda avanzada.
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de ciberamenazas, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, threat & vulnerability management, evidence, software evidence, TVM, device management, software, inventory, vulnerabilities, CVE ID, OS DeviceTvmSoftwareEvidenceBeta
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.collection: m365-security-compliance
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 9739511e366b24fdbca15548f6788c2e6de87084
ms.sourcegitcommit: 217108c59be41b01963a393b4f16d137636fe6a8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "67329385"
---
# <a name="devicetvmsoftwareevidencebeta"></a>DeviceTvmSoftwareEvidenceBeta

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender
- Microsoft Defender para punto de conexión

> [!IMPORTANT]
> La `DeviceTvmSoftwareEvidenceBeta` tabla está actualmente en versión beta. Una vez que salga de la versión beta, el nombre final de la tabla cambiará y también pueden cambiar los nombres de columna. A continuación, es probable que las modificaciones interrumpan las consultas que siguen usando nombres anteriores. Se recomienda a los usuarios revisar y ajustar sus consultas cuando finalice esta tabla. 

La `DeviceTvmSoftwareEvidenceBeta` tabla del esquema de búsqueda avanzada contiene datos de [Administración de vulnerabilidades de Microsoft Defender](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) relacionados con la [sección de pruebas de software](/microsoft-365/security/defender-endpoint/tvm-software-inventory#software-evidence). Esta tabla le permite ver la evidencia de dónde se detectó un software específico en un dispositivo. Puede usar esta tabla, por ejemplo, para identificar las rutas de acceso de archivo de software específico. Use esta referencia para crear consultas que devuelvan información de la tabla.

Para obtener información sobre otras tablas del esquema de búsqueda avanzada, consulte la [referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).

| Nombre de columna | Tipo de datos | Descripción |
|-------------|-----------|-------------|
| `DeviceId` | `string` | Identificador único del dispositivo en el servicio |
| `SoftwareVendor` | `string` | Nombre del publicador de software |
| `SoftwareName` | `string` | Nombre del producto de software |
| `SoftwareVersion` | `string` | Número de versión del producto de software |
| `RegistryPaths` | `dynamic` | Rutas de acceso del Registro donde se detectó evidencia que indica la existencia del software en un dispositivo |
| `DiskPaths` | `dynamic` | Rutas de acceso de disco en las que se detectó evidencia de nivel de archivo que indica la existencia del software en un dispositivo |
| `LastSeenTime` | `string` | Fecha y hora en que este servicio vio por última vez el dispositivo |

## <a name="related-topics"></a>Temas relacionados

- [Introducción a Administración de vulnerabilidades de Microsoft Defender](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
- [Búsqueda proactiva de amenazas](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades](advanced-hunting-query-emails-devices.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)
