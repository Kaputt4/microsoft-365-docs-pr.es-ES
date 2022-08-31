---
title: Tabla DeviceTvmSoftwareVulnerabilities en el esquema de búsqueda avanzada
description: Obtenga información sobre las vulnerabilidades de software que se encuentran en los dispositivos y la lista de actualizaciones de seguridad disponibles que abordan cada vulnerabilidad en la tabla DeviceTvmSoftwareVulnerabilities del esquema de búsqueda avanzada.
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, threat & vulnerability management, TVM, device management, software, inventory, vulnerabilities, CVE ID, OS DeviceTvmSoftwareInventoryVulnerabilities
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
ms.collection: m365-security-compliance
ms.topic: article
ms.openlocfilehash: 99a3d0a3ca730062783abd7ace664bd0bd010b18
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2022
ms.locfileid: "67481490"
---
# <a name="devicetvmsoftwarevulnerabilities"></a>DeviceTvmSoftwareVulnerabilities

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender
- Microsoft Defender para punto de conexión

>[!IMPORTANT]
> Algunas informaciones se refieren al producto publicado previamente, que puede modificarse sustancialmente antes de su lanzamiento comercial. Microsoft no otorga garantías, expresas o implícitas, con respecto a la información que aquí se proporciona.

La `DeviceTvmSoftwareVulnerabilities` tabla del esquema de búsqueda avanzada contiene la [Administración de vulnerabilidades de Microsoft Defender](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) lista de vulnerabilidades de los productos de software instalados. Esta tabla también incluye información sobre el sistema operativo, IDs de CVE e información sobre la gravedad de la vulnerabilidad. Puede usar esta tabla, por ejemplo, para buscar eventos que impliquen dispositivos que tengan vulnerabilidades graves en su software. Use esta referencia para crear consultas que devuelvan información de la tabla.

>[!NOTE]
> Las `DeviceTvmSoftwareInventory` tablas y `DeviceTvmSoftwareVulnerabilities` han reemplazado a la `DeviceTvmSoftwareInventoryVulnerabilities` tabla. Juntos, las dos primeras tablas incluyen más columnas que puede usar para ayudar a informar sobre las actividades de administración de vulnerabilidades o buscar dispositivos vulnerables.

Para obtener información sobre otras tablas del esquema de búsqueda avanzada, vea [la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).

| Nombre de columna | Tipo de datos | Descripción |
|-------------|-----------|-------------|
| `DeviceId` | `string` | Identificador único para el equipo en servicio |
| `DeviceName` | `string` | Nombre de dominio completo (FQDN, por sus siglas en inglés) del equipo |
| `OSPlatform` | `string` | Plataforma del sistema operativo que se ejecuta en el equipo. Indica sistemas operativos específicos, incluidas las variaciones dentro de la misma familia, como Windows 11, Windows 10 y Windows 7. |
| `OSVersion` | `string` | Versión del sistema operativo que se ejecuta en el equipo. |
| `OSArchitecture` | `string` | Arquitectura del sistema operativo que se ejecuta en el equipo. |
| `SoftwareVendor` | `string` | Nombre del publicador de software |
| `SoftwareName` | `string` | Nombre del producto de software |
| `SoftwareVersion` | `string` | Número de versión del producto de software |
| `CveId` | `string` | Identificador único asignado a la vulnerabilidad de seguridad en el sistema de vulnerabilidades y exposiciones comunes (CVE) |
| `VulnerabilitySeverityLevel` | `string` | Nivel de gravedad asignado a la vulnerabilidad de seguridad basada en la puntuación CVSS y los factores dinámicos influidos por el panorama de amenazas |
| `RecommendedSecurityUpdate` | `string` | Nombre o descripción de la actualización de seguridad proporcionada por el publicador de software para solucionar la vulnerabilidad |
| `RecommendedSecurityUpdateId` | `string` | Identificador de las actualizaciones de seguridad o identificador aplicables para los artículos de guía o knowledge base (KB) correspondientes |



## <a name="related-topics"></a>Temas relacionados

- [Búsqueda proactiva de amenazas](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades](advanced-hunting-query-emails-devices.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)
- [Introducción a Administración de vulnerabilidades de Microsoft Defender](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)