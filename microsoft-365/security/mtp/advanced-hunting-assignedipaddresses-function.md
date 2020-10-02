---
title: La función AssignedIPAddresses () en la caza avanzada para la protección contra amenazas de Microsoft
description: Obtenga información sobre cómo usar la función AssignedIPAddresses () para obtener las direcciones IP más recientes asignadas a un dispositivo.
keywords: caza avanzado, caza de amenazas, búsqueda de amenazas en el ciberespacio, protección contra amenazas de Microsoft, Microsoft 365, MTP, M365, búsqueda, consulta, telemetría, referencia de esquema, kusto, FileProfile, perfil de archivo, función, enriquecimiento
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: ea6b65e5e6d676c5efb2622193197bae5b9ba1b2
ms.sourcegitcommit: 0f48beaca3afa4df12d41847014975d50a4ebe7d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2020
ms.locfileid: "48338550"
---
# <a name="assignedipaddresses"></a>AssignedIPAddresses()

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Protección contra amenazas de Microsoft

Use la `AssignedIPAddresses()` función en las consultas de [búsqueda avanzada](advanced-hunting-overview.md) para obtener rápidamente las direcciones IP más recientes que se han asignado a un dispositivo. Si especifica un argumento timestamp, esta función obtiene las direcciones IP más recientes a la hora especificada. 

Esta función devuelve una tabla con las siguientes columnas:

| Columna | Tipo de datos | Descripción |
|------------|-------------|-------------|
| `Timestamp` | datetime | La última hora a la que se observó el dispositivo con la dirección IP |
| `IPAddress` | string | Dirección IP usada por el dispositivo |
| `IPType` | string | Indica si la dirección IP es una dirección pública o privada |
| `NetworkAdapterType` | entero | Tipo de adaptador de red usado por el dispositivo al que se ha asignado la dirección IP. Para obtener los valores posibles, consulte [esta enumeración](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype) . |
| `ConnectedNetworks` | entero | Redes a las que está conectado el adaptador con la dirección IP asignada. Cada matriz JSON contiene el nombre de red, la categoría (pública, privada o de dominio), una descripción y una marca que indica si está conectado públicamente a Internet |

## <a name="syntax"></a>Sintaxis

```kusto
AssignedIPAddresses(x, y)
```

## <a name="arguments"></a>Argumentos

- **x**— `DeviceId` o `DeviceName` valor que identifica el dispositivo
- **y**: `Timestamp` (DateTime) que indica a la función que debe obtener las direcciones IP asignadas más recientemente de una hora específica. Si no se especifica, la función devuelve las direcciones IP más recientes.

## <a name="examples"></a>Ejemplos

### <a name="get-the-list-of-ip-addresses-used-by-a-device-24-hours-ago"></a>Obtener la lista de direcciones IP que usa un dispositivo hace 24 horas

```kusto
AssignedIPAddresses('example-device-name', ago(1d))
```

### <a name="get-ip-addresses-used-by-a-device-and-find-devices-communicating-with-it"></a>Obtener las direcciones IP usadas por un dispositivo y buscar dispositivos que se comunican con ella
Esta consulta usa la `AssignedIPAddresses()` función para obtener las direcciones IP asignadas para el dispositivo ( `example-device-name` ) en o antes de una fecha específica ( `example-date` ). A continuación, usa las direcciones IP para buscar conexiones al dispositivo Iniciado por otros dispositivos. 

```kusto
let Date = datetime(example-date);
let DeviceName = "example-device-name";
// List IP addresses used on or before the specified date
AssignedIPAddresses(DeviceName, Date)
| project DeviceName, IPAddress, AssignedTime = Timestamp 
// Get all network events on devices with the assigned IP addresses as the destination addresses
| join kind=inner DeviceNetworkEvents on $left.IPAddress == $right.RemoteIP
// Get only network events around the time the IP address was assigned
| where Timestamp between ((AssignedTime - 1h) .. (AssignedTime + 1h))
```

## <a name="related-topics"></a>Temas relacionados
- [Información general sobre la búsqueda avanzada](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
