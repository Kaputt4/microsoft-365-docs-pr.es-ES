---
title: Función AssignedIPAddresses() en la búsqueda avanzada de Microsoft 365 Defender
description: Aprenda a usar la función AssignedIPAddresses() para obtener las direcciones IP más recientes asignadas a un dispositivo.
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernética, Microsoft 365 Defender, microsoft 365, m365, búsqueda, consulta, telemetría, referencia de esquema, kusto, FileProfile, perfil de archivo, función, enriquecimiento
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
ms.topic: article
ms.openlocfilehash: b93bcd80021055820f093b3ba52941b8a944781d
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68073017"
---
# <a name="assignedipaddresses"></a>AssignedIPAddresses()

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

Use la `AssignedIPAddresses()` función en las consultas [de búsqueda avanzadas](advanced-hunting-overview.md) para obtener rápidamente las direcciones IP más recientes que se han asignado a un dispositivo. Si especifica un argumento timestamp, esta función obtiene las direcciones IP más recientes en el momento especificado. 

Esta función devuelve una tabla con las columnas siguientes:

| Column | Tipo de datos | Descripción |
|------------|-------------|-------------|
| `Timestamp` | `datetime` | Hora más reciente en que se observó el dispositivo mediante la dirección IP |
| `IPAddress` | `string` | Dirección IP usada por el dispositivo |
| `IPType` | `string` | Indica si la dirección IP es una dirección pública o privada. |
| `NetworkAdapterType` | `int` | Tipo de adaptador de red usado por el dispositivo al que se ha asignado la dirección IP. Para conocer los valores posibles, consulte [esta enumeración](/dotnet/api/system.net.networkinformation.networkinterfacetype). |
| `ConnectedNetworks` | `int` | Redes a las que está conectado el adaptador con la dirección IP asignada. Cada matriz JSON contiene el nombre de red, la categoría (pública, privada o dominio), una descripción y una marca que indica si está conectada públicamente a Internet. |

## <a name="syntax"></a>Sintaxis

```kusto
AssignedIPAddresses(x, y)
```

## <a name="arguments"></a>Argumentos

- **x**:`DeviceId` o `DeviceName` valor que identifica el dispositivo
- **y**:`Timestamp` valor (datetime) que indica a la función que obtenga las direcciones IP asignadas más recientes de una hora específica. Si no se especifica, la función devuelve las direcciones IP más recientes.

## <a name="examples"></a>Ejemplos

### <a name="get-the-list-of-ip-addresses-used-by-a-device-24-hours-ago"></a>Obtener la lista de direcciones IP usadas por un dispositivo hace 24 horas

```kusto
AssignedIPAddresses('example-device-name', ago(1d))
```

### <a name="get-ip-addresses-used-by-a-device-and-find-devices-communicating-with-it"></a>Obtención de direcciones IP usadas por un dispositivo y búsqueda de dispositivos que se comunican con él
Esta consulta usa la `AssignedIPAddresses()` función para obtener direcciones IP asignadas para el dispositivo (`example-device-name`) en o antes de una fecha específica (`example-date`). A continuación, usa las direcciones IP para buscar conexiones al dispositivo iniciado por otros dispositivos. 

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
- [Información general sobre la búsqueda avanzada de amenazas](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)