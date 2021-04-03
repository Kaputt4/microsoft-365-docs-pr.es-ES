---
title: Tabla DeviceNetworkInfo en el esquema de búsqueda avanzada
description: Obtenga información sobre la configuración de red en la tabla DeviceNetworkInfo del esquema de búsqueda avanzada
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, protección contra amenazas de Microsoft, microsoft 365, mtp, m365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, machinenetworkinfo, DeviceNetworkInfo, dispositivo, máquina, mac, ip, adaptador, dns, dhcp, puerta de enlace, túnel
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 6d860e20bdd116d579b3cb178e3352825c60fe44
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500900"
---
# <a name="devicenetworkinfo"></a>DeviceNetworkInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender



La tabla del esquema de búsqueda avanzada contiene información sobre la configuración de redes de máquinas, incluidos adaptadores de red, direcciones IP y MAC, y redes `DeviceNetworkInfo` o dominios conectados. [](advanced-hunting-overview.md) Utilice esta referencia para crear consultas que devuelvan información sobre la tabla.

Para obtener información sobre otras tablas del esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).

| Nombre de columna | Tipo de datos | Descripción |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Fecha y hora en que se registró el evento. |
| `DeviceId` | cadena | Identificador único para el equipo en servicio |
| `DeviceName` | cadena | Nombre de dominio completo (FQDN, por sus siglas en inglés) del equipo |
| `NetworkAdapterName` | cadena | Nombre del adaptador de red |
| `MacAddress` | cadena | Dirección MAC del adaptador de red |
| `NetworkAdapterType` | cadena | Tipo de adaptador de red. Para obtener los valores posibles, consulte [esta enumeración](/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2) |
| `NetworkAdapterStatus` | cadena | Estado operativo del adaptador de red. Para obtener los valores posibles, consulte [esta enumeración](/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2) |
| `TunnelType` | cadena | Protocolo de túnel, si la interfaz se usa para este fin, por ejemplo, 6to4, Teredo, ISATAP, PPTP, SSTP y SSH |
| `ConnectedNetworks` | cadena | Redes a las que está conectado el adaptador. Cada matriz JSON contiene el nombre de red, la categoría (público, privado o dominio), una descripción y una marca que indica si está conectada públicamente a Internet |
| `DnsAddresses` | cadena | Direcciones de servidor DNS en formato de matriz JSON |
| `IPv4Dhcp` | cadena | Dirección IPv4 del servidor DHCP |
| `IPv6Dhcp` | cadena | Dirección IPv6 del servidor DHCP |
| `DefaultGateways` | cadena | Direcciones de puerta de enlace predeterminadas en formato de matriz JSON |
| `IPAddresses` | cadena | Matriz JSON que contiene todas las direcciones IP asignadas al adaptador, junto con su prefijo de subred y espacio de direcciones IP respectivos, como pública, privada o local de vínculos |
| `ReportId` | largo | Identificador de eventos basado en un contador de repetición. Para identificar eventos únicos, esta columna debe usarse junto con las columnas DeviceName y Timestamp |

## <a name="related-topics"></a>Temas relacionados
- [Información general sobre la búsqueda avanzada de amenazas](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades](advanced-hunting-query-emails-devices.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)