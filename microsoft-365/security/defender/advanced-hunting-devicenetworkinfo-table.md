---
title: Tabla DeviceNetworkInfo en el esquema de búsqueda avanzada
description: Obtenga información sobre la configuración de red en la tabla DeviceNetworkInfo del esquema de búsqueda avanzada.
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de ciberamenazas, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, machinenetworkinfo, DeviceNetworkInfo, device, machine, mac, ip, adapter, dns, dhcp, gateway, tunnel
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
ms.openlocfilehash: 91f6d12619a698028974616ffe6628ea9d4f3116
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68083019"
---
# <a name="devicenetworkinfo"></a>DeviceNetworkInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender
- Microsoft Defender para punto de conexión



La `DeviceNetworkInfo` tabla del esquema [de búsqueda avanzada](advanced-hunting-overview.md) contiene información sobre la configuración de red de las máquinas, incluidos los adaptadores de red, las direcciones IP y MAC, y las redes o dominios conectados. Utilice esta referencia para crear consultas que devuelvan información sobre la tabla.

Para obtener información sobre otras tablas del esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).

| Nombre de columna | Tipo de datos | Descripción |
|-------------|-----------|-------------|
| `Timestamp` | `datetime` | Fecha y hora en que se registró el evento. |
| `DeviceId` | `string` | Identificador único para el equipo en servicio |
| `DeviceName` | `string` | Nombre de dominio completo (FQDN, por sus siglas en inglés) del equipo |
| `NetworkAdapterName` | `string` | Nombre del adaptador de red |
| `MacAddress` | `string` | Dirección MAC del adaptador de red |
| `NetworkAdapterType` | `string` | Tipo de adaptador de red. Para conocer los valores posibles, consulte [esta enumeración](/dotnet/api/system.net.networkinformation.networkinterfacetype). |
| `NetworkAdapterStatus` | `string` | Estado operativo del adaptador de red. Para conocer los valores posibles, consulte [esta enumeración](/dotnet/api/system.net.networkinformation.operationalstatus). |
| `TunnelType` | `string` | Protocolo de tunelización, si se usa la interfaz para este propósito, por ejemplo, 6to4, Teredo, ISATAP, PPTP, SSTP y SSH |
| `ConnectedNetworks` | `string` | Redes a las que está conectado el adaptador. Cada matriz JSON contiene el nombre de red, la categoría (pública, privada o dominio), una descripción y una marca que indica si está conectada públicamente a Internet. |
| `DnsAddresses` | `string` | Direcciones de servidor DNS en formato de matriz JSON |
| `IPv4Dhcp` | `string` | Dirección IPv4 del servidor DHCP |
| `IPv6Dhcp` | `string` | Dirección IPv6 del servidor DHCP |
| `DefaultGateways` | `string` | Direcciones de puerta de enlace predeterminadas en formato de matriz JSON |
| `IPAddresses` | `string` | Matriz JSON que contiene todas las direcciones IP asignadas al adaptador, junto con el prefijo de subred y el espacio de direcciones IP correspondientes, como público, privado o local de vínculo |
| `ReportId` | `long` | Identificador de eventos basado en un contador de repetición. Para identificar eventos únicos, esta columna debe usarse junto con las columnas DeviceName y Timestamp. |

## <a name="related-topics"></a>Temas relacionados
- [Información general sobre la búsqueda avanzada de amenazas](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades](advanced-hunting-query-emails-devices.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)