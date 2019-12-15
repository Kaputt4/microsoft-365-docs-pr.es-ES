---
title: Tabla DeviceTvmSoftwareInventoryVulnerabilities en el esquema de búsqueda avanzada
description: Obtenga más información sobre el inventario de software en sus dispositivos y sus vulnerabilidades en la tabla DeviceTvmSoftwareInventoryVulnerabilities del esquema de búsqueda avanzada.
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de ciberamenazas, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, administración de amenazas y vulnerabilidades, TVM, administración de dispositivos, software, inventario, vulnerabilidades, Id. de CVE, SO DeviceTvmSoftwareInventoryVulnerabilities
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: f7c7ab393a956aa894a0ca8704ea0e99a82addc9
ms.sourcegitcommit: 0c9c28a87201c7470716216d99175356fb3d1a47
ms.translationtype: MT + HT Review
ms.contentlocale: es-ES
ms.lasthandoff: 12/09/2019
ms.locfileid: "39911609"
---
# <a name="devicetvmsoftwareinventoryvulnerabilities"></a>DeviceTvmSoftwareInventoryVulnerabilities

**Se aplica a:**
- Protección contra amenazas de Microsoft

[!include[Prerelease information](prerelease.md)]

La tabla `DeviceTvmSoftwareInventoryVulnerabilities` en el esquema de búsqueda avanzada contiene el inventario de software de la [Administración de amenazas y vulnerabilidades](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) en sus dispositivos, así como las vulnerabilidades conocidas de estos productos de software. Esta tabla también incluye información sobre el sistema operativo, IDs de CVE e información sobre la gravedad de la vulnerabilidad. Use esta referencia para crear consultas que devuelvan información de la tabla.

Para obtener información sobre otras tablas del esquema de búsqueda avanzada, consulte la [referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).

| Nombre de columna | Tipo de datos | Descripción |
|-------------|-----------|-------------|
| `MachineId` | string | Identificador único para el equipo en servicio |
| `ComputerName` | cadena | Nombre de dominio completo (FQDN, por sus siglas en inglés) del equipo |
| `OSPlatform` | cadena | Plataforma del sistema operativo que se ejecuta en el equipo. Esto indica que se trata de sistemas operativos específicos, incluyendo variaciones dentro de la misma familia, como Windows 10 y Windows 7. |
| `OSVersion` | cadena | Versión del sistema operativo que se ejecuta en el equipo. |
| `OSArchitecture` | cadena | Arquitectura del sistema operativo que se ejecuta en el equipo. |
| `SoftwareVendor` | cadena | Nivel de gravedad asignado a la vulnerabilidad de seguridad basada en la puntuación CVSS y los factores dinámicos influidos por el panorama de amenazas |
| `SoftwareName` | cadena | Nombre del producto de software |
| `SoftwareVersion` | cadena | Número de versión del producto de software |
| `CveId` | cadena | Identificador único asignado a la vulnerabilidad de seguridad en el sistema de vulnerabilidades y exposiciones comunes (CVE) |
| `VulnerabilitySeverityLevel` | cadena | Nivel de gravedad asignado a la vulnerabilidad de seguridad basada en la puntuación CVSS y los factores dinámicos influidos por el panorama de amenazas |



## <a name="related-topics"></a>Temas relacionados

- [Búsqueda proactiva de amenazas](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Búsqueda de amenazas en dispositivos y mensajes de correo electrónico](advanced-hunting-query-emails-devices.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)
- [Información general sobre la Administración de amenazas y vulnerabilidades](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
