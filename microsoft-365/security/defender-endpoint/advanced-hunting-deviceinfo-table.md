---
title: Tabla DeviceInfo en el esquema de búsqueda avanzada
description: Obtenga información sobre el sistema operativo, el nombre del equipo y otra información del dispositivo en la tabla DeviceInfo del esquema de búsqueda avanzada
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, deviceinfo, dispositivo, sistema operativo, plataforma, usuarios, DeviceInfo
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
ms.openlocfilehash: e6a11af94a5d2b2099d14b660cf65c846532ebd1
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500829"
---
# <a name="deviceinfo"></a>DeviceInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)


>¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

La tabla del esquema de búsqueda avanzada contiene información sobre los dispositivos de la organización, incluida su versión del sistema operativo, los `DeviceInfo` usuarios activos y el nombre del equipo. [](advanced-hunting-overview.md) Use esta referencia para crear consultas que devuelvan información de la tabla.

Para obtener información sobre otras tablas del esquema de búsqueda avanzada, vea la referencia de esquema [de búsqueda avanzada](advanced-hunting-schema-reference.md).

| Nombre de columna | Tipo de datos | Descripción |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Fecha y hora en que se registró el evento. |
| `DeviceId` | cadena | Identificador único del dispositivo en el servicio |
| `DeviceName` | cadena | Nombre de dominio completo (FQDN) del dispositivo |
| `ClientVersion` | cadena | Versión del agente de punto de conexión o sensor que se ejecuta en el dispositivo |
| `PublicIP` | cadena | Dirección IP pública usada por el dispositivo incorporado para conectarse al servicio Defender para endpoints. Podría ser la dirección IP del propio dispositivo, un dispositivo NAT o un proxy |
| `OSArchitecture` | cadena | Arquitectura del sistema operativo que se ejecuta en el dispositivo |
| `OSPlatform` | cadena | Plataforma del sistema operativo que se ejecuta en el dispositivo. Esto indica sistemas operativos específicos, incluidas las variaciones dentro de la misma familia, como Windows 10 y Windows 7 |
| `OSBuild` | cadena | Versión de compilación del sistema operativo que se ejecuta en el dispositivo |
| `IsAzureADJoined` | boolean | Indicador booleano de si el dispositivo está unido a Azure Active Directory |
| `LoggedOnUsers` | cadena | Lista de todos los usuarios que han iniciado sesión en el dispositivo en el momento del evento en formato de matriz JSON |
| `RegistryDeviceTag` | cadena | Etiqueta de dispositivo agregada a través del Registro |
| `ReportId` | largo | Identificador de eventos basado en un contador de repetición. Para identificar eventos únicos, esta columna debe usarse junto con las columnas DeviceName y Timestamp |
| `OSVersion` | cadena | Versión del sistema operativo que se ejecuta en el dispositivo |
| `MachineGroup` | cadena | Grupo de máquinas de la máquina. Este grupo lo usa el control de acceso basado en roles para determinar el acceso a la máquina |

## <a name="related-topics"></a>Temas relacionados
- [Información general sobre la búsqueda avanzada de amenazas](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Entender el esquema](advanced-hunting-schema-reference.md)
