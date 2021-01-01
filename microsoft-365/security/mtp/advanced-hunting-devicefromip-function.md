---
title: La función DeviceFromIP () en la búsqueda avanzada de Microsoft 365 defender
description: Obtenga información sobre cómo usar la función DeviceFromIP () para obtener los dispositivos que se han asignado a una dirección IP específica.
keywords: caza avanzado, caza de amenazas, búsqueda de amenazas en el ciberespacio, protección contra amenazas de Microsoft, Microsoft 365, MTP, M365, búsqueda, consulta, telemetría, referencia de esquema, kusto, dispositivo, devicefromIP, función, enriquecimiento
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 65409dd93f3703f1af115178c4cd9fa470fb7497
ms.sourcegitcommit: 25ac2736a66bb72c0d574c3fbde7472ac98d5321
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/31/2020
ms.locfileid: "49741117"
---
# <a name="devicefromip"></a>DeviceFromIP()

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender


[!INCLUDE [Prerelease information](../includes/prerelease.md)]


Use la `DeviceFromIP()` función en las consultas de [búsqueda avanzada](advanced-hunting-overview.md) para obtener rápidamente la lista de dispositivos que se han asignado a una dirección IP determinada en un momento determinado. 

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

- **x**: el primer parámetro suele ser una columna en la consulta. En este caso, es la columna denominada `IP` , la dirección IP para la que desea ver una lista de dispositivos que se le han asignado. Debe ser una dirección IP local. No se admiten las direcciones IP externas.
- **y**: un segundo parámetro opcional es el `Timestamp` , que indica a la función que obtenga los dispositivos asignados más recientes a partir de una hora específica. Si no se especifica, la función devuelve los últimos registros disponibles.

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
