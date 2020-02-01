---
title: Tabla DeviceNetworkInfo en el esquema de búsqueda avanzada
description: Obtenga información sobre la configuración de red en la tabla DeviceNetworkInfo del esquema de búsqueda avanzada.
keywords: caza avanzado, caza de amenazas, búsqueda de amenazas en el ciberespacio, protección contra amenazas de Microsoft, Microsoft 365, MTP, M365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, machinenetworkinfo, DeviceNetworkInfo, dispositivo máquina, Mac, IP, adaptador, DNS, DHCP, puerta de enlace, túnel
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
ms.openlocfilehash: 25349328cd128113de7846cba5c7c9ad74631092
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "41600417"
---
# <a name="devicenetworkinfo"></a>DeviceNetworkInfo

**Se aplica a:**
- Protección contra amenazas de Microsoft

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

La `DeviceNetworkInfo` tabla del esquema de [búsqueda avanzada](advanced-hunting-overview.md) contiene información sobre la configuración de red de los equipos, incluidos los adaptadores de red, las direcciones IP y Mac y las redes o los dominios conectados. Utilice esta referencia para crear consultas que devuelvan información sobre la tabla.

Para obtener información sobre otras tablas del esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).

| Nombre de columna | Tipo de datos | Descripción |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Fecha y hora en que se registró el evento. |
| `DeviceId` | string | Identificador único para el equipo en servicio |
| `DeviceName` | cadena | Nombre de dominio completo (FQDN, por sus siglas en inglés) del equipo |
| `ReportId` | largo | Identificador de eventos basado en un contador de repetición. Para identificar eventos únicos, esta columna debe usarse junto con las columnas DeviceName y timestamp. |
| `NetworkAdapterName` | string | Nombre del adaptador de red |
| `MacAddress` | string | Dirección MAC del adaptador de red |
| `NetworkAdapterType` | string | Tipo de adaptador de red. Para obtener los valores posibles, consulte [esta enumeración](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2) . |
| `NetworkAdapterStatus` | string | Estado operativo del adaptador de red. Para obtener los valores posibles, consulte [esta enumeración](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2) . |
| `TunnelType` | string | Protocolo de túnel, si se usa la interfaz para este propósito, por ejemplo, 6to4, Teredo, ISATAP, PPTP, SSTP y SSH |
| `ConnectedNetworks` | string | Redes a las que está conectado el adaptador. Cada matriz JSON contiene el nombre de red, la categoría (pública, privada o de dominio), una descripción y una marca que indica si está conectado públicamente a Internet |
| `DnsAddresses` | string | Direcciones de servidor DNS en formato de matriz JSON |
| `IPv4Dhcp` | string | Dirección IPv4 del servidor DHCP |
| `IPv6Dhcp` | string | Dirección IPv6 del servidor DHCP |
| `DefaultGateways` | string | Direcciones de puerta de enlace predeterminadas en formato de matriz JSON |
| `IPAddresses` | string | Matriz JSON que contiene todas las direcciones IP asignadas al adaptador, junto con el prefijo de subred y el espacio de direcciones IP respectivos, como Public, Private o local Link |

## <a name="related-topics"></a>Temas relacionados
- [Búsqueda proactiva de amenazas](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Búsqueda de amenazas en dispositivos y mensajes de correo electrónico](advanced-hunting-query-emails-devices.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)
