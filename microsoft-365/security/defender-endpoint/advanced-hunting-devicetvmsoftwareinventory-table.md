---
title: Tabla DeviceTvmSoftwareInventory en el esquema de búsqueda avanzada
description: Obtenga información sobre el inventario de software en sus dispositivos en la tabla DeviceTvmSoftwareInventory del esquema de búsqueda avanzado.
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, mdatp, atp de microsoft defender, búsqueda wdatp, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, administración de vulnerabilidades de & de amenazas, TVM, administración de dispositivos, software, inventario, vulnerabilidades, IDENTIFICADOR CVE, OS DeviceTvmSoftwareInventoryVulnerabilities
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 18e43d8e38c24a8aa28c6455dc1a769b8da0df2b
ms.sourcegitcommit: c75aac39ee8d93218a79585113ef6b36f47c9ddf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/29/2021
ms.locfileid: "51408628"
---
# <a name="devicetvmsoftwareinventory"></a>DeviceTvmSoftwareInventory

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)

>¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

La tabla del esquema de búsqueda avanzada contiene el inventario de administración de amenazas y vulnerabilidades del software instalado actualmente en dispositivos de la red, incluida la información de fin `DeviceTvmSoftwareInventory` de soporte técnico. [](next-gen-threat-and-vuln-mgt.md) Por ejemplo, puede buscar eventos que impliquen dispositivos instalados con una versión de software vulnerable actualmente. Use esta referencia para crear consultas que devuelvan información de la tabla.

DeviceTVMSoftwareInventory contiene todo el software que la administración de amenazas y vulnerabilidades pudo hacer coincidir con una enumeración de plataforma común (CPE), independientemente de si es vulnerable o no.

>[!NOTE]
>Las `DeviceTvmSoftwareInventory` tablas y han reemplazado a la `DeviceTvmSoftwareVulnerabilities` `DeviceTvmSoftwareInventoryVulnerabilities` tabla. Juntos, las dos primeras tablas incluyen más columnas que puede usar para ayudar a informar sobre las actividades de administración de vulnerabilidades.

Para obtener información sobre otras tablas del esquema de búsqueda avanzada, vea [la referencia de búsqueda avanzada](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).

| Nombre de columna | Tipo de datos | Descripción |
|-------------|-----------|-------------|
| `DeviceId` | string | Identificador único del dispositivo en el servicio. |
| `DeviceName` | cadena | Nombre de dominio completo (FQDN) del dispositivo. |
| `OSPlatform` | cadena | Plataforma del sistema operativo que se ejecuta en el dispositivo. Esto indica que se trata de sistemas operativos específicos, incluyendo variaciones dentro de la misma familia, como Windows 10 y Windows 7. |
| `OSVersion` | cadena | Versión del sistema operativo que se ejecuta en el dispositivo. |
| `OSArchitecture` | cadena | Arquitectura del sistema operativo que se ejecuta en el dispositivo. |
| `SoftwareVendor` | cadena | Nombre del proveedor de software. |
| `SoftwareName` | cadena | Nombre del producto de software. |
| `SoftwareVersion` | cadena | Número de versión del producto de software. |
| `EndOfSupportStatus` | cadena | Indica la fase de ciclo de vida del producto de software en relación con la fecha de fin de soporte técnico (EOS) o de fin de vida (EOL) especificada. |
| `EndOfSupportDate` | cadena | Fecha de fin de soporte técnico (EOS) o de fin de vida (EOL) del producto de software. |

## <a name="related-topics"></a>Temas relacionados

- [Información general sobre la búsqueda avanzada de amenazas](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Entender el esquema](advanced-hunting-schema-reference.md)
- [Información general sobre la Administración de amenazas y vulnerabilidades](next-gen-threat-and-vuln-mgt.md)
