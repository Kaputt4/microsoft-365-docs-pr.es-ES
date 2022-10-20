---
title: Tabla DeviceTvmInfoGathering en el esquema de búsqueda avanzada
description: Obtenga información sobre los eventos de evaluación, incluido el estado de varias configuraciones y los estados de área expuesta a ataques de los dispositivos en la tabla DeviceTvmInfoGathering del esquema de búsqueda avanzada.
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, threat & vulnerability management, TVM, device management, software, inventory, vulnerabilities, CVE ID, OS DeviceTvmSoftwareInventoryVulnerabilities, Administración de vulnerabilidades de Microsoft Defender
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
ms.topic: conceptual
ms.openlocfilehash: 9021b592b346516e1b2ee958582f0c68775a816d
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68645877"
---
# <a name="devicetvminfogathering"></a>DeviceTvmInfoGathering

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender
- Microsoft Defender para punto de conexión

>[!IMPORTANT]
> Parte de la información se refiere a productos preliminares que pueden ser modificados sustancialmente antes de su lanzamiento comercial. Microsoft no otorga garantías, expresas o implícitas, con respecto a la información que aquí se proporciona.

La `DeviceTvmInfoGathering` tabla del esquema de búsqueda avanzada contiene [Administración de vulnerabilidades de Microsoft Defender](/microsoft-365/security/defender-vulnerability-management/defender-vulnerability-management) eventos de evaluación, incluido el estado de varias configuraciones y estados de área expuesta a ataques de los dispositivos. Puede usar esta tabla para buscar eventos de evaluación relacionados con la mitigación durante cero días, la evaluación de postura para las amenazas emergentes que admiten informes de estado de mitigación de análisis de amenazas, versiones habilitadas del protocolo TLS en servidores, etc. Use esta referencia para crear consultas que devuelvan información de la tabla.

Para obtener información sobre otras tablas del esquema de búsqueda avanzada, consulte la [referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).

| Nombre de columna | Tipo de datos | Descripción |
|-------------|-----------|-------------|
| `Timestamp` | `datetime` | Fecha y hora en que se registró el evento. |
| `LastSeenTime` | `datetime` | Fecha y hora en que el servicio vio por última vez el dispositivo |
| `DeviceId` | `string` | Identificador único del dispositivo en el servicio |
| `DeviceName` | `string` | Nombre de dominio completo (FQDN) del dispositivo |
| `OSPlatform` | `string` | Plataforma del sistema operativo que se ejecuta en el dispositivo. Esto indica que se trata de sistemas operativos específicos, incluyendo variaciones dentro de la misma familia, como Windows 10 y Windows 7. |
| `AdditionalFields` | `string` | Información adicional sobre el evento  |

Por ejemplo, para ver los dispositivos afectados por la [vulnerabilidad de Log4Shell](https://www.microsoft.com/security/blog/2021/12/11/guidance-for-preventing-detecting-and-hunting-for-cve-2021-44228-log4j-2-exploitation/) donde aún no se ha aplicado la mitigación de solución alternativa, o se ha aplicado y está pendiente de reinicio, puede usar la siguiente consulta.

```kusto
DeviceTvmInfoGathering
| where AdditionalFields.Log4JEnvironmentVariableMitigation in ("RebootRequired", "false")
| join kind=inner (
    DeviceTvmSoftwareVulnerabilities
    | where CveId == "CVE-2021-44228"
) on DeviceId
| summarize any(DeviceName), any(AdditionalFields.Log4JEnvironmentVariableMitigation) by DeviceId
```

## <a name="related-topics"></a>Temas relacionados
- [DeviceTvmInfoGatheringKB](advanced-hunting-devicetvminfogatheringkb-table.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)
- [Introducción a la administración de vulnerabilidades de Defender](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
- [Aprenda a administrar la vulnerabilidad de Log4Shell en Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/tvm-manage-log4shell-guidance)