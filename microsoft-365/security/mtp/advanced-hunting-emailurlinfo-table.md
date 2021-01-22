---
title: Tabla EmailUrlInfo en el esquema de búsqueda avanzada
description: Obtenga más información sobre la dirección URL o sobre el vínculo en la tabla EmailUrlInfo del esquema de búsqueda avanzada.
keywords: búsqueda avanzada, búsqueda de amenazas, ciberamenazas, protección contra amenazas de Microsoft, microsoft 365, mtp, m365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, EmailUrlInfo, id. de mensaje de red, url, vínculo
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
ms.openlocfilehash: 56d35e2812d895215cbe76deb6791695380abc50
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929723"
---
# <a name="emailurlinfo"></a>EmailUrlInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

La tabla del esquema de búsqueda avanzada contiene información sobre las direcciones URL de los correos electrónicos y los datos adjuntos procesados por `EmailUrlInfo` Microsoft Defender para Office 365. [](advanced-hunting-overview.md) Use esta referencia para crear consultas que devuelvan información sobre la tabla.

Para obtener información sobre otras tablas en el esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).

| Nombre de columna | Tipo de datos | Descripción |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Fecha y hora en que se registró el evento |
| `UrlId` | cadena | Identificador único de la dirección URL en el asunto, el cuerpo o en los datos adjuntos del mensaje de correo electrónico |
| `NetworkMessageId` | cadena | Identificador único del correo electrónico, generado por Microsoft 365 |
| `Url` | cadena | Dirección URL completa en el asunto, el cuerpo o en los datos adjuntos del mensaje de correo electrónico |

## <a name="related-topics"></a>Temas relacionados
- [Información general sobre la búsqueda avanzada](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades](advanced-hunting-query-emails-devices.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)
