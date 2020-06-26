---
title: Tabla AppFileEvents en el esquema de búsqueda avanzada
description: Obtenga información sobre eventos relacionados con archivos asociados con aplicaciones y servicios en la nube en la tabla AppFileEvents del esquema de búsqueda avanzada.
keywords: búsqueda avanzada, caza de amenazas, búsqueda de amenazas en el ciberespacio, protección contra amenazas de Microsoft, Microsoft 365, MTP, M365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, AppFileEvents, Cloud App Security, MCAS
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
ms.openlocfilehash: da3b331d4f607aa0961e275db9444aadbec4fcf2
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/26/2020
ms.locfileid: "44899344"
---
# <a name="appfileevents"></a>AppFileEvents

**Se aplica a:**
- Protección contra amenazas de Microsoft

La `AppFileEvents` tabla del esquema de [búsqueda avanzada](advanced-hunting-overview.md) contiene información sobre actividades relacionadas con archivos en aplicaciones en la nube y servicios supervisados por Microsoft Cloud App Security. Utilice esta referencia para crear consultas que devuelvan información sobre la tabla.

Para obtener información sobre otras tablas del esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).

| Nombre de columna | Tipo de datos | Descripción |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Fecha y hora en que se registró el evento. |
| `ActionType` | string | Tipo de actividad que ha desencadenado el evento |
| `Application` | string | Aplicación que realizó la acción grabada |
| `FileName` | cadena | Nombre del archivo donde se aplicó la acción registrada |
| `FolderPath` | cadena | Carpeta que contiene el archivo al que se aplicó la acción grabada |
| `PreviousFileName` | string | Nombre original del archivo cuyo nombre ha cambiado como resultado de la acción |
| `AccountName` | string | Nombre de usuario de la cuenta |
| `AccountDomain` | string | Dominio de la cuenta |
| `AccountUpn` | string | Nombre principal de usuario (UPN) de la cuenta |
| `AccountObjectId` | string | Identificador único de la cuenta en Azure AD |
| `AccountDisplayName` | string | Nombre del usuario de la cuenta que se muestra en la libreta de direcciones. Normalmente es una combinación de un nombre determinado o de un nombre, un inicio en el medio y un apellido o un apellido. |
| `IPAddress` | string | Dirección IP asignada al extremo y utilizada durante las comunicaciones de red relacionadas |
| `Location` | string | Ciudad, país u otra ubicación geográfica asociada con el evento |

## <a name="related-topics"></a>Temas relacionados
- [Información general sobre la búsqueda avanzada](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Búsqueda de amenazas en dispositivos y mensajes de correo electrónico](advanced-hunting-query-emails-devices.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)
