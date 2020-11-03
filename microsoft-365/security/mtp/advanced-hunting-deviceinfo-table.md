---
title: Tabla DeviceInfo en el esquema de búsqueda avanzada
description: Información sobre el sistema operativo, el nombre del equipo y otros datos del equipo en la tabla DeviceInfo del esquema de búsqueda avanzada
keywords: caza avanzado, caza de amenazas, búsqueda de amenazas en el ciberespacio, protección contra amenazas de Microsoft, Microsoft 365, MTP, M365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, machineinfo, DeviceInfo, dispositivo, máquina, so, plataforma, usuarios
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 1bb48b4332bc9d60de15bb513f04a503d6a6913b
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "48842719"
---
# <a name="deviceinfo"></a>DeviceInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 defender



La `DeviceInfo` tabla del esquema de [búsqueda avanzada](advanced-hunting-overview.md) contiene información sobre los equipos de la organización, incluida la versión del sistema operativo, los usuarios activos y el nombre del equipo. Utilice esta referencia para crear consultas que devuelvan información sobre la tabla.

Para obtener información sobre otras tablas del esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).

| Nombre de columna | Tipo de datos | Descripción |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Fecha y hora en que se registró el evento. |
| `DeviceId` | cadena | Identificador único para el equipo en servicio |
| `DeviceName` | cadena | Nombre de dominio completo (FQDN, por sus siglas en inglés) del equipo |
| `ClientVersion` | cadena | Versión del agente de extremo o del sensor que se ejecuta en el equipo |
| `PublicIP` | string | Dirección IP pública usada por el equipo incorporado para conectarse a Microsoft defender para el servicio de extremo. Podría ser la dirección IP del equipo, un dispositivo NAT o un proxy |
| `OSArchitecture` | cadena | Arquitectura del sistema operativo que se ejecuta en el equipo. |
| `OSPlatform` | cadena | Plataforma del sistema operativo que se ejecuta en el equipo. Esto indica sistemas operativos específicos, incluidas las variaciones dentro de la misma familia, como Windows 10 y Windows 7. |
| `OSBuild` | string | Versión de compilación del sistema operativo que se ejecuta en el equipo |
| `IsAzureADJoined` | boolean | Indicador booleano de si el equipo está unido a Azure Active Directory |
| `LoggedOnUsers` | string | Lista de todos los usuarios que han iniciado sesión en el equipo en el momento del evento en el formato de matriz JSON |
| `RegistryDeviceTag` | string | Etiqueta de máquina agregada a través del registro |
| `ReportId` | largo | Identificador de eventos basado en un contador de repetición. Para identificar eventos únicos, esta columna debe usarse junto con las columnas DeviceName y timestamp. |
| `OSVersion` | cadena | Versión del sistema operativo que se ejecuta en el equipo. |
| `MachineGroup` | cadena | Grupo de máquinas del equipo. El control de acceso basado en roles usa este grupo para determinar el acceso al equipo |

## <a name="related-topics"></a>Temas relacionados
- [Información general sobre la búsqueda avanzada](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades](advanced-hunting-query-emails-devices.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)
