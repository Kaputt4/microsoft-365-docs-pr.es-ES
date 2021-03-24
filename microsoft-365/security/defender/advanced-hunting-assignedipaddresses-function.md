---
title: Función AssignedIPAddresses() en búsqueda avanzada para Microsoft 365 Defender
description: Obtenga información sobre cómo usar la función AssignedIPAddresses() para obtener las direcciones IP más recientes asignadas a un dispositivo
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, protección contra amenazas de Microsoft, microsoft 365, mtp, m365, búsqueda, consulta, telemetría, referencia de esquema, kusto, FileProfile, perfil de archivo, función, enriquecimiento
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 3760ff84e6abfbe05d9e4605d64087d0077300e3
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071635"
---
# <a name="assignedipaddresses"></a>AssignedIPAddresses()

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

Usa la función de las consultas de búsqueda avanzadas para obtener rápidamente las direcciones IP más recientes que se han `AssignedIPAddresses()` asignado a un dispositivo. [](advanced-hunting-overview.md) Si especifica un argumento de marca de tiempo, esta función obtiene las direcciones IP más recientes en el momento especificado. 

Esta función devuelve una tabla con las siguientes columnas:

| Column | Tipo de datos | Descripción |
|------------|-------------|-------------|
| `Timestamp` | datetime | Última hora en la que se observó el dispositivo con la dirección IP |
| `IPAddress` | string | Dirección IP usada por el dispositivo |
| `IPType` | string | Indica si la dirección IP es una dirección pública o privada |
| `NetworkAdapterType` | Entero | Tipo de adaptador de red usado por el dispositivo al que se ha asignado la dirección IP. Para obtener los valores posibles, consulte [esta enumeración](/dotnet/api/system.net.networkinformation.networkinterfacetype) |
| `ConnectedNetworks` | Entero | Redes a las que está conectado el adaptador con la dirección IP asignada. Cada matriz JSON contiene el nombre de red, la categoría (público, privado o dominio), una descripción y una marca que indica si está conectada públicamente a Internet |

## <a name="syntax"></a>Sintaxis

```kusto
AssignedIPAddresses(x, y)
```

## <a name="arguments"></a>Argumentos

- **x** o `DeviceId` valor que identifica el `DeviceName` dispositivo
- **y:** valor (datetime) que indica a la función que obtenga las direcciones IP asignadas más `Timestamp` recientes a partir de una hora específica. Si no se especifica, la función devuelve las direcciones IP más recientes.

## <a name="examples"></a>Ejemplos

### <a name="get-the-list-of-ip-addresses-used-by-a-device-24-hours-ago"></a>Obtener la lista de direcciones IP usadas por un dispositivo hace 24 horas

```kusto
AssignedIPAddresses('example-device-name', ago(1d))
```

### <a name="get-ip-addresses-used-by-a-device-and-find-devices-communicating-with-it"></a>Obtener direcciones IP usadas por un dispositivo y buscar dispositivos que se comuniquen con él
Esta consulta usa la función para obtener direcciones IP asignadas para el dispositivo ( ) en `AssignedIPAddresses()` o antes de una fecha específica ( `example-device-name` `example-date` ). A continuación, usa las direcciones IP para buscar conexiones al dispositivo iniciadas por otros dispositivos. 

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