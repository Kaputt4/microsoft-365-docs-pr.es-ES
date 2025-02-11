---
title: Tabla DeviceTvmSoftwareInventory en el esquema de búsqueda avanzada
description: Obtenga información sobre el inventario de software en los dispositivos en la tabla DeviceTvmSoftwareInventory del esquema de búsqueda avanzada.
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
ms.collection:
- m365-security
- tier3
ms.topic: conceptual
ms.openlocfilehash: 4b4c27564c7e77de38f4e348cb5bf054e3f30602
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68640860"
---
# <a name="devicetvmsoftwareinventory"></a>DeviceTvmSoftwareInventory

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender
- Microsoft Defender para punto de conexión

>[!IMPORTANT]
> Parte de la información se refiere a productos preliminares que pueden ser modificados sustancialmente antes de su lanzamiento comercial. Microsoft no otorga garantías, expresas o implícitas, con respecto a la información que aquí se proporciona.


La `DeviceTvmSoftwareInventory` tabla del esquema de búsqueda avanzada contiene el [inventario de Administración de vulnerabilidades de Microsoft Defender](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) de software instalado actualmente en los dispositivos de la red, incluida la información de finalización de soporte técnico. Por ejemplo, puede buscar eventos que impliquen dispositivos instalados con una versión de software actualmente vulnerable. Use esta referencia para crear consultas que devuelvan información de la tabla.

>[!NOTE]
> Las `DeviceTvmSoftwareInventory` tablas y `DeviceTvmSoftwareVulnerabilities` han reemplazado a la `DeviceTvmSoftwareInventoryVulnerabilities` tabla. Juntos, las dos primeras tablas incluyen más columnas que puede usar para ayudar a informar sobre las actividades de administración de vulnerablidad o buscar dispositivos vulnerables.

Para obtener información sobre otras tablas del esquema de búsqueda avanzada, vea [la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).

| Nombre de columna | Tipo de datos | Descripción |
|-------------|-----------|-------------|
| `DeviceId` | `string` | Identificador único para el equipo en servicio |
| `DeviceName` | `string` | Nombre de dominio completo (FQDN, por sus siglas en inglés) del equipo |
| `OSPlatform` | `string` | Plataforma del sistema operativo que se ejecuta en el equipo. Esto indica sistemas operativos específicos, incluidas las variaciones dentro de la misma familia, como Windows 11, Windows 10 y Windows 7. |
| `OSVersion` | `string` | Versión del sistema operativo que se ejecuta en el equipo. |
| `OSArchitecture` | `string` | Arquitectura del sistema operativo que se ejecuta en el equipo. |
| `SoftwareVendor` | `string` | Nombre del proveedor de software |
| `SoftwareName` | `string` | Nombre del producto de software |
| `SoftwareVersion` | `string` | Número de versión del producto de software |
| `EndOfSupportStatus` | `string` | Indica la fase del ciclo de vida del producto de software en relación con su fecha de fin de soporte técnico (EOS) o de fin de ciclo de vida (EOL) especificado. |
| `EndOfSupportDate` | `string` | Fecha de finalización del soporte técnico (EOS) o fin de ciclo de vida (EOL) del producto de software |
| `ProductCodeCpe` | `string` | CPE del producto de software o "no disponible" cuando no hay ningún CPE |
| `CveTags` | `string` | Matriz de las etiquetas pertinentes para el CVE. Las etiquetas que se admiten actualmente son "ZeroDay" y "NoSecurityUpdate".

## <a name="related-topics"></a>Temas relacionados

- [Búsqueda proactiva de amenazas](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades](advanced-hunting-query-emails-devices.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)
- [Introducción a Administración de vulnerabilidades de Microsoft Defender](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)