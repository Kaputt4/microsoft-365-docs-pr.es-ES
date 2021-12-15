---
title: Tabla DeviceInfo en el esquema de búsqueda avanzada
description: Obtenga información sobre el sistema operativo, el nombre del equipo y otra información de máquina en la tabla DeviceInfo del esquema de búsqueda avanzada
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, Microsoft 365 Defender, microsoft 365, m365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, machineinfo, DeviceInfo, dispositivo, máquina, sistema operativo, plataforma, usuarios
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
ms.openlocfilehash: acba50ec85e0d8d2f61a51aa902a26e5bcbed6f9
ms.sourcegitcommit: 6dcc3b039e0f0b9bae17c386f14ed2b577b453a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/15/2021
ms.locfileid: "61530810"
---
# <a name="deviceinfo"></a>DeviceInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender
- Microsoft Defender para punto de conexión

La tabla del esquema de búsqueda avanzada contiene información sobre los dispositivos de la organización, incluida la versión del sistema operativo, los `DeviceInfo` usuarios activos y el nombre del equipo. [](advanced-hunting-overview.md) Utilice esta referencia para crear consultas que devuelvan información sobre la tabla.

Para obtener información sobre otras tablas del esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).

| Nombre de columna | Tipo de datos | Description |
|-------------|-----------|-------------|
| `Timestamp` | `datetime` | Fecha y hora en que se registró el evento. |
| `DeviceId` | `string` | Identificador único para el equipo en servicio |
| `DeviceName` | `string` | Nombre de dominio completo (FQDN, por sus siglas en inglés) del equipo |
| `ClientVersion` | `string` | Versión del agente de punto de conexión o sensor que se ejecuta en la máquina |
| `PublicIP` | `string` | Dirección IP pública usada por el equipo incorporado para conectarse al servicio de Microsoft Defender para endpoints. Esta podría ser la dirección IP del propio equipo, un dispositivo NAT o un proxy |
| `OSArchitecture` | `string` | Arquitectura del sistema operativo que se ejecuta en el equipo. |
| `OSPlatform` | `string` | Plataforma del sistema operativo que se ejecuta en el equipo. Esto indica sistemas operativos específicos, incluidas las variaciones dentro de la misma familia, como Windows 11, Windows 10 y Windows 7. |
| `OSBuild` | `string` | Versión de compilación del sistema operativo que se ejecuta en la máquina |
| `IsAzureADJoined` | `boolean` | Indicador booleano de si la máquina está unida al Azure Active Directory |
| `AadObjectId` | `string` | Identificador único del dispositivo en Azure AD |
| `LoggedOnUsers` | `string` | Lista de todos los usuarios que han iniciado sesión en el equipo en el momento del evento en formato de matriz JSON |
| `RegistryDeviceTag` | `string` | Etiqueta de máquina agregada a través del Registro |
| `OSVersion` | `string` | Versión del sistema operativo que se ejecuta en el equipo. |
| `MachineGroup` | `string` | Grupo de máquinas de la máquina. Este grupo lo usa el control de acceso basado en roles para determinar el acceso a la máquina |
| `ReportId` | `long` | Identificador de eventos basado en un contador de repetición. Para identificar eventos únicos, esta columna debe usarse junto con las columnas DeviceName y Timestamp |
| `OnboardingStatus` | `string` | Indica si el dispositivo está actualmente incorporado o no en Microsoft Defender para Endpoint o si el dispositivo no es compatible |
|`AdditionalFields` | `string` | Información adicional sobre el evento en formato de matriz JSON |
|`DeviceCategory` | `string` | Clasificación más amplia que agrupa determinados tipos de dispositivos en las siguientes categorías: Endpoint, Network device, IoT, Unknown |
|`DeviceType` | `string` | Tipo de dispositivo basado en propósito y funcionalidad, como dispositivo de red, estación de trabajo, servidor, móvil, consola de juegos o impresora |
|`DeviceSubType` | `string` | Modificador adicional para determinados tipos de dispositivos, por ejemplo, un dispositivo móvil puede ser una tableta o un smartphone |
|`Model` | `string` | Nombre del modelo o número del producto del proveedor o fabricante |
|`Vendor` | `string` | Nombre del proveedor o fabricante del producto |
|`OSDistribution` | `string` | Distribución de la plataforma del sistema operativo, como Ubuntu o RedHat para plataformas Linux |
|`OSVersionInfo` | `string` | Información adicional sobre la versión del sistema operativo, como el nombre popular, el nombre de código o el número de versión |
|`MergedDeviceIds` | `string` | IDs de dispositivo anteriores que se han asignado al mismo dispositivo |
|`MergedToDeviceId` | `string` | El identificador de dispositivo más reciente asignado a un dispositivo |

La tabla proporciona información del dispositivo basada en latidos, que son informes `DeviceInfo` periódicos o señales de un dispositivo. Cada quince minutos, el dispositivo envía un latido parcial que contiene atributos que cambian con frecuencia, como `LoggedOnUsers` . Una vez al día, se envía un latido completo que contiene los atributos del dispositivo.

Puedes usar la siguiente consulta de ejemplo para obtener el estado más reciente de un dispositivo:

```kusto
// Get latest information on user/device
DeviceInfo
| where DeviceName == "example" and isnotempty(OSPlatform)
| summarize arg_max(Timestamp, *) by DeviceId 
```

## <a name="related-topics"></a>Temas relacionados
- [Información general sobre la búsqueda avanzada de amenazas](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades](advanced-hunting-query-emails-devices.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)
