---
title: Tabla EmailAttachmentInfo del esquema de búsqueda avanzada
description: Obtenga más información sobre los datos adjuntos en la tabla de EmailAttachmentInfo del esquema de búsqueda avanzada.
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, protección contra amenazas de Microsoft, microsoft 365, mtp, m365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, EmailAttachmentInfo, id. de mensaje de red, remitente, destinatario, id. de datos adjuntos, nombre de datos adjuntos, veredicto de malware
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
localization_priority: Normal
manager: dansimp
audience: ITPro
mms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 43e861d43e6e98f1e17d737f431bb72c42f3f4f6
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51073960"
---
# <a name="emailattachmentinfo"></a>EmailAttachmentInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender



La tabla del esquema de búsqueda avanzada contiene información acerca de los datos adjuntos de los correos electrónicos procesados por `EmailAttachmentInfo` Microsoft Defender para Office 365. [](advanced-hunting-overview.md) Utilice esta referencia para crear consultas que devuelvan información sobre la tabla.

Para obtener información sobre otras tablas del esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).

| Nombre de columna | Tipo de datos | Descripción |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Fecha y hora en que se registró el evento. |
| `NetworkMessageId` | cadena | Identificador único del correo electrónico, generado por Microsoft 365 |
| `SenderFromAddress` | cadena | Dirección de correo electrónico del remitente en el encabezado DE, que es visible para los destinatarios de correo electrónico de sus clientes. |
| `SenderDisplayName` | cadena | Nombre del remitente que se muestra en la libreta de direcciones, normalmente una combinación de un nombre o nombre determinado, una inicial intermedia y un apellido o apellido |
| `SenderObjectId` | string | Identificador único de la cuenta del remitente en Azure AD |
| `RecipientEmailAddress` | cadena | Dirección de correo electrónico del destinatario, después de la expansión de la lista de distribución. |
| `RecipientObjectId` | cadena | Identificador único para el destinatario de correo electrónico en Azure AD |
| `FileName` | cadena | Nombre del archivo donde se aplicó la acción registrada |
| `FileType` | cadena | Tipo de extensión de archivo |
| `SHA256` | cadena | SHA-256 del archivo donde se aplicó la acción registrada. Este campo no suele estar rellenado; use la columna SHA1 cuando se encuentre disponible. |
| `ThreatTypes` | cadena | Verdict from the email filtering stack on whether the email contains malware, phishing, or other threats |
| `ThreatNames` | string | Nombre de detección de malware u otras amenazas encontradas |
| `DetectionMethods` | string | Métodos usados para detectar malware, phishing u otras amenazas encontradas en el correo electrónico |
| `ReportId` | largo | Identificador de eventos basado en un contador de repetición. Para identificar eventos únicos, esta columna debe usarse junto con las columnas DeviceName y Timestamp. |

## <a name="related-topics"></a>Temas relacionados
- [Información general sobre la búsqueda avanzada](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades](advanced-hunting-query-emails-devices.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)
