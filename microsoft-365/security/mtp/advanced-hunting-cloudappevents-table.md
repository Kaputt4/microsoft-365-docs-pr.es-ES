---
title: Tabla CloudAppEvents en el esquema de búsqueda avanzada
description: Obtenga información sobre eventos de servicios y aplicaciones en la nube en la tabla CloudAppEvents del esquema de búsqueda avanzada
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de ciberamenazas, protección contra amenazas de Microsoft, microsoft 365, mtp, m365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, CloudAppEvents, Cloud App Security, MCAS
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 021a8210bbe5886021e980b33ade0b9e2ded7b5b
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928458"
---
# <a name="cloudappevents"></a>CloudAppEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Actualmente disponible en versión preliminar, la tabla del esquema de búsqueda avanzada contiene información sobre las actividades en diversas aplicaciones y servicios en la nube, específicamente `CloudAppEvents` Microsoft Teams y Exchange Online. [](advanced-hunting-overview.md) Utilice esta referencia para crear consultas que devuelvan información sobre la tabla.

Esta tabla se expandirá para incluir más actividades supervisadas por Microsoft Cloud App Security. Finalmente, esta tabla incluirá la actividad de archivos almacenada actualmente en la [tabla AppFileEvents.](advanced-hunting-appfileevents-table.md) Microsoft proporcionará instrucciones adicionales a medida que se muevan más datos a esta tabla.

Para obtener información sobre otras tablas del esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).

| Nombre de columna | Tipo de datos | Descripción |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Fecha y hora en que se registró el evento. |
| `ActionType` | cadena | Tipo de actividad que desencadenó el evento |
| `Application` | string | Aplicación que realizó la acción grabada |
| `ApplicationId` | string | Identificador único de la aplicación |
| `AccountObjectId` | string | Identificador único de la cuenta en Azure Active Directory |
| `AccountDisplayName` | string | Nombre del usuario de la cuenta que se muestra en la libreta de direcciones. Normalmente, una combinación de un nombre o nombre, una iniciación intermedia y un apellido o apellido. |
| `IsAdminOperation` | string | Indica si la actividad la realizó un administrador |
| `DeviceType` | string | Tipo de dispositivo basado en propósito y funcionalidad, como "Dispositivo de red", "Estación de trabajo", "Servidor", "Móvil", "Consola de juegos" o "Impresora" | 
| `OSPlatform` | string | Plataforma del sistema operativo que se ejecuta en el dispositivo. Esta columna indica sistemas operativos específicos, incluidas las variaciones dentro de la misma familia, como Windows 10 y Windows 7. |
| `IPAddress` | string | Dirección IP asignada al extremo y usada durante las comunicaciones de red relacionadas |
| `IsAnonymousProxy` | string | Indica si la dirección IP pertenece a un proxy anónimo conocido |
| `CountryCode` | string | Código de dos letras que indica el país donde se geolocalización la dirección IP del cliente |
| `City` | string | Ciudad en la que se geolocalización de la dirección IP del cliente |
| `Isp` | string | Proveedor de servicios de Internet (ISP) asociado a la dirección IP |
| `UserAgent` | string | Información de agente de usuario del explorador web u otra aplicación cliente |
| `ActivityType` | string | Tipo de actividad que desencadenó el evento |
| `ActivityObjects` | string | Lista de objetos, como archivos o carpetas, que participaron en la actividad grabada |
| `ObjectName` | string | Nombre del objeto al que se aplicó la acción grabada |
| `ObjectType` | string | Tipo de objeto, como un archivo o una carpeta, al que se aplicó la acción grabada |
| `ObjectId` | string | Identificador único del objeto al que se aplicó la acción grabada |
| `ReportId` | string | Identificador único del evento |
| `RawEventData` | string | Información de evento sin procesar de la aplicación o servicio de origen en formato JSON |
| `AdditionalFields` | string | Información adicional sobre la entidad o el evento |

## <a name="related-topics"></a>Temas relacionados
- [Información general sobre la búsqueda avanzada](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades](advanced-hunting-query-emails-devices.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)
