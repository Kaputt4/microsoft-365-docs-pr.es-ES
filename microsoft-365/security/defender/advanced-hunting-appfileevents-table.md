---
title: Tabla AppFileEvents en el esquema de búsqueda avanzada
description: Obtenga información sobre los eventos relacionados con archivos asociados con aplicaciones y servicios en la nube en la tabla AppFileEvents del esquema de búsqueda avanzada
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, protección contra amenazas de Microsoft, microsoft 365, mtp, m365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, AppFileEvents, Cloud App Security, MCAS
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
ms.openlocfilehash: b8b3b34e1b8535772d19f8ddd9f52c5c0a89292b
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499345"
---
# <a name="appfileevents"></a>AppFileEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

La tabla del esquema de búsqueda avanzada contiene información sobre las actividades relacionadas con archivos en aplicaciones y servicios en la nube `AppFileEvents` supervisados por Microsoft Cloud App Security. [](advanced-hunting-overview.md) Utilice esta referencia para crear consultas que devuelvan información sobre la tabla.

>[!WARNING]
>Esta tabla se retirará pronto. A partir del 7 de marzo de 2021, la tabla ya no es `AppFileEvents` registros. Los usuarios que desprotegán las actividades relacionadas con archivos en los servicios en la nube en y más allá de esa fecha deben usar la [tabla CloudAppEvents](advanced-hunting-cloudappevents-table.md) en su lugar. <br><br>Asegúrese de buscar consultas y reglas de detección personalizadas que aún usan la tabla y `AppFileEvents` editarlas para usar la `CloudAppEvents` tabla. Encontrará más instrucciones sobre la conversión de consultas afectadas en [Hunt across cloud app activities with Microsoft 365 Defender advanced hunting](https://techcommunity.microsoft.com/t5/microsoft-365-defender/hunt-across-cloud-app-activities-with-microsoft-365-defender/ba-p/1893857).


Para obtener información sobre otras tablas del esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).

| Nombre de columna | Tipo de datos | Descripción |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Fecha y hora en que se registró el evento. |
| `ActionType` | cadena | Tipo de actividad que desencadenó el evento. Vea la [referencia de esquema en el portal](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) para obtener más información |
| `Application` | cadena | Aplicación que realizó la acción grabada |
| `FileName` | cadena | Nombre del archivo donde se aplicó la acción registrada |
| `FolderPath` | cadena | Carpeta que contiene el archivo al que se aplicó la acción grabada |
| `PreviousFileName` | cadena | Nombre original del archivo cuyo nombre se cambió como resultado de la acción |
| `PreviousFolderPath` | cadena | Carpeta original que contiene el archivo antes de aplicar la acción grabada |
| `Protocol` | cadena | Protocolo de red usado |
| `AccountName` | cadena | Nombre de usuario de la cuenta |
| `AccountDomain` | cadena | Dominio de la cuenta |
| `AccountSid` | cadena | Identificador de seguridad (SID) de la cuenta |
| `AccountUpn` | cadena | Nombre principal de usuario (UPN) de la cuenta |
| `AccountObjectId` | cadena | Identificador único de la cuenta en Azure AD |
| `AccountDisplayName` | cadena | Nombre del usuario de la cuenta que se muestra en la libreta de direcciones. Normalmente, una combinación de un nombre o un nombre determinado, un inicio intermedio y un apellido o apellido. |
| `DeviceName` | cadena | Nombre de dominio completo (FQDN) del dispositivo |
| `DeviceType` | cadena | Tipo de dispositivo | 
| `OSPlatform` | cadena | Plataforma del sistema operativo que se ejecuta en el dispositivo. Esto indica que se trata de sistemas operativos específicos, incluyendo variaciones dentro de la misma familia, como Windows 10 y Windows 7. |
| `IPAddress` | cadena | Dirección IP asignada al extremo y usada durante las comunicaciones de red relacionadas |
| `Port` | cadena | Puerto TCP usado durante la comunicación  |
| `DestinationDeviceName` | cadena | Nombre del dispositivo que ejecuta la aplicación de servidor que procesó la acción grabada |
| `DestinationIPAddress` | cadena | Dirección IP del dispositivo que ejecuta la aplicación de servidor que procesó la acción grabada |
| `DestinationPort` | cadena | Puerto de destino de comunicaciones de red relacionadas |
| `Location` | cadena | Ciudad, país u otra ubicación geográfica asociada al evento |
| `Isp` | cadena | Proveedor de servicios de Internet (ISP) asociado con la dirección IP del extremo |
| `ReportId` | largo | Identificador único del evento |
| `AdditionalFields` | cadena | Información adicional sobre la entidad o el evento |

>[!TIP]
> Para obtener información detallada acerca de los tipos de eventos ( valores) admitidos por una tabla, use la referencia de esquema integrada `ActionType` disponible en el centro de seguridad.


## <a name="related-topics"></a>Temas relacionados
- [Información general sobre la búsqueda avanzada de amenazas](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades](advanced-hunting-query-emails-devices.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)
