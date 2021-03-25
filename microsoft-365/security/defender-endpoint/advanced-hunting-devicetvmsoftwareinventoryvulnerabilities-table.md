---
title: Tabla DeviceTvmSoftwareInventoryVulnerabilities en el esquema de búsqueda avanzada
description: Obtenga más información sobre el inventario de software en sus dispositivos y sus vulnerabilidades en la tabla DeviceTvmSoftwareInventoryVulnerabilities del esquema de búsqueda avanzada.
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, mdatp, atp de microsoft defender, búsqueda wdatp, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, administración de vulnerabilidades de & de amenazas, TVM, administración de dispositivos, software, inventario, vulnerabilidades, IDENTIFICADOR CVE, OS DeviceTvmSoftwareInventoryVulnerabilities
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: bbb535aa3f106c8569edb3c64ba95bba9bf36186
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163464"
---
# <a name="devicetvmsoftwareinventoryvulnerabilities"></a>DeviceTvmSoftwareInventoryVulnerabilities

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**

- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)

>¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)


[!include[Prerelease information](../../includes/prerelease.md)]

La tabla `DeviceTvmSoftwareInventoryVulnerabilities` en el esquema de búsqueda avanzada contiene el inventario de software de la [Administración de amenazas y vulnerabilidades](next-gen-threat-and-vuln-mgt.md) en sus dispositivos, así como las vulnerabilidades conocidas de estos productos de software. Esta tabla también incluye información sobre el sistema operativo, IDs de CVE e información sobre la gravedad de la vulnerabilidad. Use esta referencia para crear consultas que devuelvan información de la tabla.

Para obtener información sobre otras tablas del esquema de búsqueda avanzada, consulte la [referencia de búsqueda avanzada](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).

| Nombre de columna | Tipo de datos | Descripción |
|-------------|-----------|-------------|
| `DeviceId` | string | Identificador único del dispositivo en el servicio |
| `DeviceName` | string | Nombre de dominio completo (FQDN) del dispositivo |
| `OSPlatform` | string | Plataforma del sistema operativo que se ejecuta en el dispositivo. Esto indica que se trata de sistemas operativos específicos, incluyendo variaciones dentro de la misma familia, como Windows 10 y Windows 7. |
| `OSVersion` | cadena | Versión del sistema operativo que se ejecuta en el dispositivo |
| `OSArchitecture` | string | Arquitectura del sistema operativo que se ejecuta en el dispositivo |
| `SoftwareVendor` | string | Nombre del proveedor de software |
| `SoftwareName` | cadena | Nombre del producto de software |
| `SoftwareVersion` | cadena | Número de versión del producto de software |
| `CveId` | cadena | Identificador único asignado a la vulnerabilidad de seguridad en el sistema de vulnerabilidades y exposiciones comunes (CVE) |
| `VulnerabilitySeverityLevel` | string | Nivel de gravedad asignado a la vulnerabilidad de seguridad basada en la puntuación CVSS y los factores dinámicos influidos por el panorama de amenazas |



## <a name="related-topics"></a>Temas relacionados

- [Información general sobre la búsqueda avanzada](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Entender el esquema](advanced-hunting-schema-reference.md)
- [Información general sobre la Administración de amenazas y vulnerabilidades](next-gen-threat-and-vuln-mgt.md)
