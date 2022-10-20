---
title: Función DeviceFromIP() en la búsqueda avanzada de Microsoft 365 Defender
description: Aprenda a usar la función DeviceFromIP() para obtener los dispositivos a los que se ha asignado una dirección IP específica.
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernética, Microsoft 365 Defender, microsoft 365, m365, búsqueda, consulta, telemetría, referencia de esquema, kusto, dispositivo, devicefromIP, función, enriquecimiento
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
ms.topic: conceptual
ms.openlocfilehash: c5021854af82cdc9e3337162b47d4ca8d21ff99b
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68644095"
---
# <a name="devicefromip"></a>DeviceFromIP()

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender


[!INCLUDE [Prerelease information](../includes/prerelease.md)]


Use la `DeviceFromIP()` función en las consultas [de búsqueda avanzadas](advanced-hunting-overview.md) para obtener rápidamente la lista de dispositivos que se han asignado a una dirección IP determinada en un momento dado. 

Esta función devuelve una tabla con las columnas siguientes:

| Column | Tipo de datos | Descripción |
|------------|-------------|-------------|
| `IP` | `string` | Dirección IP  |
| `DeviceId` | `string` | Identificador único del dispositivo en el servicio |


## <a name="syntax"></a>Sintaxis

```kusto
invoke DeviceFromIP()
```

## <a name="arguments"></a>Argumentos

Esta función se invoca como parte de una consulta.

- **x**: el primer parámetro suele ser una columna de la consulta. En este caso, es la columna denominada `IP`, la dirección IP para la que desea ver una lista de dispositivos que se le han asignado. Debe ser una dirección IP local. No se admiten direcciones IP externas.
- **y**: un segundo parámetro opcional es , `Timestamp`que indica a la función que obtenga los dispositivos asignados más recientes de una hora específica. Si no se especifica, la función devuelve los registros disponibles más recientes.

## <a name="example"></a>Ejemplo


### <a name="get-the-latest-devices-that-have-been-assigned-specific-ip-addresses"></a>Obtener los dispositivos más recientes a los que se han asignado direcciones IP específicas

```kusto
DeviceNetworkEvents 
| limit 100 
| project IP = LocalIP 
| invoke DeviceFromIP()
```

## <a name="related-topics"></a>Temas relacionados
- [Información general sobre la búsqueda avanzada de amenazas](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
