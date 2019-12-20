---
title: Tabla EmailUrlInfo en el esquema de búsqueda avanzada
description: Obtenga más información sobre la dirección URL o sobre el vínculo en la tabla EmailUrlInfo del esquema de búsqueda avanzada.
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de ciberamenazas, búsqueda, consulta, telemetría, referencia del esquema, kusto, tabla, columna, tipo de datos, descripción, EmailUrlInfo, id. del mensaje de red, dirección url, vínculo
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: da9712d1f3465c28d2ba880997a52434723a297d
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/19/2019
ms.locfileid: "40808675"
---
# <a name="emailurlinfo"></a>EmailUrlInfo

**Se aplica a:**
- Protección contra amenazas de Microsoft

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

La tabla `EmailUrlInfo` del esquema de [búsqueda avanzada](advanced-hunting-overview.md) contiene información sobre las direcciones URL en los correos electrónicos y datos adjuntos procesados por la ATP de Office 365. Use esta referencia para crear consultas que devuelvan información sobre la tabla.

Para obtener información sobre otras tablas en el esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).

| Nombre de columna | Tipo de datos | Descripción |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Fecha y hora en que se registró el evento |
| `UrlId` | cadena | Identificador único de la dirección URL en el asunto, el cuerpo o en los datos adjuntos del mensaje de correo electrónico |
| `NetworkMessageId` | cadena | Identificador único para el correo electrónico generado por Office 365. |
| `Url` | cadena | Dirección URL completa en el asunto, el cuerpo o en los datos adjuntos del mensaje de correo electrónico |

## <a name="related-topics"></a>Temas relacionados
- [Búsqueda proactiva de amenazas](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Búsqueda de amenazas en dispositivos y mensajes de correo electrónico](advanced-hunting-query-emails-devices.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)