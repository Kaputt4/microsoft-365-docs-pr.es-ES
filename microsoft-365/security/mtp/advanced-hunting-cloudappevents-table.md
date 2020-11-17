---
title: Tabla CloudAppEvents en el esquema de búsqueda avanzada
description: Obtenga información sobre los eventos de aplicaciones y servicios en la nube en la tabla CloudAppEvents del esquema de búsqueda avanzada.
keywords: búsqueda avanzada, caza de amenazas, búsqueda de amenazas en el ciberespacio, protección contra amenazas de Microsoft, Microsoft 365, MTP, M365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, CloudAppEvents, Cloud App Security, MCAS
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 3cb4498e5db6a7752e99b8c677bc8936d2c975ef
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087775"
---
# <a name="cloudappevents"></a>CloudAppEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Actualmente disponible en la versión preliminar, la `CloudAppEvents` tabla del esquema de [búsqueda avanzada](advanced-hunting-overview.md) contiene información sobre las actividades en varias aplicaciones y servicios en la nube, en concreto Microsoft Teams y Exchange Online. Utilice esta referencia para crear consultas que devuelvan información sobre la tabla.

Esta tabla se expandirá para incluir más actividades supervisadas por Microsoft Cloud App Security. Finalmente, en esta tabla se incluirá la actividad File almacenada actualmente en la tabla [AppFileEvents](advanced-hunting-appfileevents-table.md) . Microsoft proporcionará instrucciones adicionales a medida que se vayan moviendo más datos a esta tabla.

Para obtener información sobre otras tablas del esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).

| Nombre de columna | Tipo de datos | Descripción |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Fecha y hora en que se registró el evento. |
| `ActionType` | cadena | Tipo de actividad que ha desencadenado el evento |
| `Application` | string | Aplicación que realizó la acción grabada |
| `ApplicationId` | string | Identificador único de la aplicación |
| `AccountObjectId` | string | Identificador único de la cuenta en Azure Active Directory |
| `AccountDisplayName` | string | Nombre del usuario de la cuenta que se muestra en la libreta de direcciones. Normalmente es una combinación de un nombre determinado o de un nombre, un inicio en el medio y un apellido o un apellido. |
| `IsAdminOperation` | string | Indica si la actividad la realizó un administrador |
| `DeviceType` | string | Tipo de dispositivo basado en el propósito y la funcionalidad, como "dispositivo de red", "estación de trabajo", "servidor", "móvil", "consola de juegos" o "impresora" | 
| `OSPlatform` | string | Plataforma del sistema operativo que se ejecuta en el dispositivo. Esta columna indica sistemas operativos específicos, incluidas las variaciones dentro de la misma familia, como Windows 10 y Windows 7. |
| `IPAddress` | string | Dirección IP asignada al extremo y utilizada durante las comunicaciones de red relacionadas |
| `IsAnonymousProxy` | string | Indica si la dirección IP pertenece a un proxy anónimo conocido |
| `CountryCode` | string | Código de dos letras que indica el país donde la dirección IP del cliente está geolocada |
| `City` | string | Ciudad donde la dirección IP del cliente está geolocada |
| `Isp` | string | Proveedor de servicios de Internet (ISP) asociado con la dirección IP |
| `UserAgent` | string | Información de agente de usuario desde el explorador Web u otra aplicación cliente |
| `ActivityType` | string | Tipo de actividad que ha desencadenado el evento |
| `ActivityObjects` | string | Lista de objetos, como archivos o carpetas, implicados en la actividad grabada |
| `ObjectName` | string | Nombre del objeto al que se aplicó la acción grabada |
| `ObjectType` | string | Tipo de objeto, como un archivo o una carpeta, al que se aplicó la acción grabada |
| `ObjectId` | string | Identificador único del objeto al que se aplicó la acción grabada |
| `ReportId` | string | Identificador único del evento |
| `RawEventData` | string | Información de evento sin procesar de la aplicación o servicio de origen en formato JSON |
| `AdditionalFields` | string | Información adicional acerca de la entidad o el evento |

## <a name="related-topics"></a>Temas relacionados
- [Información general sobre la búsqueda avanzada](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades](advanced-hunting-query-emails-devices.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)
