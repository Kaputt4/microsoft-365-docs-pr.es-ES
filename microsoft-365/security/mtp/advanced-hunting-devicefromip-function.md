---
title: Función DeviceFromIP() en la búsqueda avanzada para Microsoft 365 Defender
description: Aprende a usar la función DeviceFromIP() para obtener los dispositivos a los que se ha asignado una dirección IP específica
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de ciberamenazas, protección contra amenazas de Microsoft, microsoft 365, mtp, m365, búsqueda, consulta, telemetría, referencia de esquema, kusto, dispositivo, devicefromIP, función, enriquecimiento
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 86373c903252fde4ab71c80a81404428a7366da7
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931307"
---
# <a name="devicefromip"></a>DeviceFromIP()

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender


[!INCLUDE [Prerelease information](../includes/prerelease.md)]


Use la función de las consultas de búsqueda avanzada para obtener rápidamente la lista de dispositivos que se han asignado a una dirección IP determinada en un momento `DeviceFromIP()` dado. [](advanced-hunting-overview.md) 

Esta función devuelve una tabla con las siguientes columnas:

| Columna | Tipo de datos | Descripción |
|------------|-------------|-------------|
| `IP` | string | Dirección IP  |
| `DeviceId` | string | Identificador único del dispositivo en el servicio |


## <a name="syntax"></a>Sintaxis

```kusto
invoke DeviceFromIP()
```

## <a name="arguments"></a>Argumentos

Esta función se invoca como parte de una consulta.

- **x:** el primer parámetro suele ser ya una columna de la consulta. En este caso, es la columna denominada , la dirección IP para la que desea ver una lista de dispositivos que se le han `IP` asignado. Debe ser una dirección IP local. No se admiten direcciones IP externas.
- **y:** un segundo parámetro opcional es el , que indica a la función que obtenga los `Timestamp` dispositivos asignados más recientes de una hora específica. Si no se especifica, la función devuelve los últimos registros disponibles.

## <a name="example"></a>Ejemplo


### <a name="get-the-latest-devices-that-have-been-assigned-specific-ip-addresses"></a>Obtener los dispositivos más recientes a los que se han asignado direcciones IP específicas

```kusto
DeviceNetworkEvents 
| limit 100 
| project IP = LocalIP 
| invoke DeviceFromIP()
```

## <a name="related-topics"></a>Temas relacionados
- [Información general sobre la búsqueda avanzada](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
