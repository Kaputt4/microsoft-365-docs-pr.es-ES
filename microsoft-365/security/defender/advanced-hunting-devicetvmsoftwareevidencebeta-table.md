---
title: Tabla DeviceTvmSoftwareEvidenceBeta en el esquema de búsqueda avanzada
description: Aprende a usar la tabla DeviceTvmSoftwareEvidenceBeta en el esquema de búsqueda avanzado.
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, Microsoft 365 Defender, microsoft 365, m365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, & administración de vulnerabilidades , evidence, software evidence, TVM, device management, software, inventory, vulnerabilities, CVE ID, OS DeviceTvmSoftwareEvidenceBeta
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
ms.openlocfilehash: 7fd064b906e4afe5e337df85d9dc6f174edc99cf
ms.sourcegitcommit: 36a19d80fe3f053df0fec398a7ff2dfc777f9730
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/30/2021
ms.locfileid: "61645843"
---
# <a name="devicetvmsoftwareevidencebeta"></a>DeviceTvmSoftwareEvidenceBeta

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender
- Microsoft Defender para punto de conexión

> [!IMPORTANT]
> La `DeviceTvmSoftwareEvidenceBeta` tabla está actualmente en beta. Una vez que deja beta, el nombre de la tabla final cambiará y los nombres de columna también pueden cambiar. A continuación, es probable que las modificaciones rompan las consultas que siguen usando nombres anteriores. Se recomienda a los usuarios revisar y ajustar sus consultas cuando se haya finalizado esta tabla. 


La tabla del esquema de búsqueda avanzada contiene datos de `DeviceTvmSoftwareEvidenceBeta` [Threat & Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) relacionados con la sección de [pruebas de software](/microsoft-365/security/defender-endpoint/tvm-software-inventory#software-evidence). Esta tabla te permite ver evidencias de dónde se detectó un software específico en un dispositivo. Puede usar esta tabla, por ejemplo, para identificar las rutas de acceso a archivos de software específico. Use esta referencia para crear consultas que devuelvan información de la tabla.

Para obtener información sobre otras tablas del esquema de búsqueda avanzada, consulte la [referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).

| Nombre de columna | Tipo de datos | Descripción |
|-------------|-----------|-------------|
| `DeviceId` | `string` | Identificador único del dispositivo en el servicio |
| `SoftwareVendor` | `string` | Nombre del editor de software |
| `SoftwareName` | `string` | Nombre del producto de software |
| `SoftwareVersion` | `string` | Número de versión del producto de software |
| `RegistryPaths` | `dynamic` | Rutas de registro en las que se detectó evidencia que indica la existencia del software en un dispositivo |
| `DiskPaths` | `dynamic` | Rutas de disco en las que se detectó evidencia de nivel de archivo que indica la existencia del software en un dispositivo |
| `LastSeenTime` | `string` | Fecha y hora en que el dispositivo vio por última vez este servicio |




## <a name="related-topics"></a>Temas relacionados

- [Información general sobre la Administración de amenazas y vulnerabilidades](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
- [Búsqueda proactiva de amenazas](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades](advanced-hunting-query-emails-devices.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)
