---
title: Tabla DeviceNetworkInfo en el esquema de búsqueda avanzada
description: Obtenga información sobre la configuración de red en la tabla DeviceNetworkInfo del esquema de búsqueda avanzada
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, Microsoft 365 Defender, microsoft 365, m365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, machinenetworkinfo, DeviceNetworkInfo, dispositivo, máquina, mac, ip, adaptador, dns, dhcp, puerta de enlace, túnel
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
ms.openlocfilehash: 5b7bd42a8d9cbfd93a45d36a8236fb858eeb0436
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2021
ms.locfileid: "60209254"
---
# <a name="devicenetworkinfo"></a>DeviceNetworkInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender
- Microsoft Defender para punto de conexión



La tabla del esquema de búsqueda avanzada contiene información sobre la configuración de redes de máquinas, incluidos adaptadores de red, direcciones IP y MAC, y redes `DeviceNetworkInfo` o dominios conectados. [](advanced-hunting-overview.md) Utilice esta referencia para crear consultas que devuelvan información sobre la tabla.

Para obtener información sobre otras tablas del esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).

| Nombre de columna | Tipo de datos | Descripción |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Fecha y hora en que se registró el evento. |
| `DeviceId` | cadena | Identificador único para el equipo en servicio |
| `DeviceName` | cadena | Nombre de dominio completo (FQDN, por sus siglas en inglés) del equipo |
| `NetworkAdapterName` | cadena | Nombre del adaptador de red |
| `MacAddress` | string | Dirección MAC del adaptador de red |
| `NetworkAdapterType` | string | Tipo de adaptador de red. Para obtener los valores posibles, consulte [esta enumeración](/dotnet/api/system.net.networkinformation.networkinterfacetype) |
| `NetworkAdapterStatus` | string | Estado operativo del adaptador de red. Para obtener los valores posibles, consulte [esta enumeración](/dotnet/api/system.net.networkinformation.operationalstatus) |
| `TunnelType` | string | Protocolo de túnel, si la interfaz se usa para este fin, por ejemplo, 6to4, Teredo, ISATAP, PPTP, SSTP y SSH |
| `ConnectedNetworks` | string | Redes a las que está conectado el adaptador. Cada matriz JSON contiene el nombre de red, la categoría (público, privado o dominio), una descripción y una marca que indica si está conectada públicamente a Internet |
| `DnsAddresses` | string | Direcciones de servidor DNS en formato de matriz JSON |
| `IPv4Dhcp` | string | Dirección IPv4 del servidor DHCP |
| `IPv6Dhcp` | string | Dirección IPv6 del servidor DHCP |
| `DefaultGateways` | string | Direcciones de puerta de enlace predeterminadas en formato de matriz JSON |
| `IPAddresses` | string | Matriz JSON que contiene todas las direcciones IP asignadas al adaptador, junto con su prefijo de subred y espacio de direcciones IP respectivos, como pública, privada o local de vínculos |
| `ReportId` | largo | Identificador de eventos basado en un contador de repetición. Para identificar eventos únicos, esta columna debe usarse junto con las columnas DeviceName y Timestamp |

## <a name="related-topics"></a>Temas relacionados
- [Información general sobre la búsqueda avanzada de amenazas](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades](advanced-hunting-query-emails-devices.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)