---
title: Tabla EmailAttachmentInfo del esquema de búsqueda avanzada
description: Obtenga más información sobre los datos adjuntos en la tabla de EmailAttachmentInfo del esquema de búsqueda avanzada.
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, Microsoft 365 Defender, microsoft 365, m365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, EmailAttachmentInfo, id. de mensaje de red, remitente, destinatario, id. de datos adjuntos, nombre de datos adjuntos, veredicto de malware
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: m365-security-compliance
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: ac3e7aeff6778709f68aa1da74446cf55a1a6c06
ms.sourcegitcommit: 6dcc3b039e0f0b9bae17c386f14ed2b577b453a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/15/2021
ms.locfileid: "61531308"
---
# <a name="emailattachmentinfo"></a>EmailAttachmentInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**

- Microsoft 365 Defender

La tabla del esquema de búsqueda avanzada contiene información acerca de los datos adjuntos de los correos electrónicos procesados por `EmailAttachmentInfo` Microsoft Defender para Office 365. [](advanced-hunting-overview.md) Utilice esta referencia para crear consultas que devuelvan información sobre la tabla.

Para obtener información sobre otras tablas del esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).

> [!IMPORTANT]
> Parte de la información se refiere a productos preliminares que pueden ser modificados sustancialmente antes de su lanzamiento comercial. Microsoft no otorga garantías, expresas o implícitas, con respecto a la información que aquí se proporciona.

| Nombre de columna | Tipo de datos | Description |
|-------------|-----------|-------------|
| `Timestamp` | `datetime` | Fecha y hora en que se registró el evento. |
| `NetworkMessageId` | `string` | Identificador único del correo electrónico, generado por Microsoft 365 |
| `SenderFromAddress` | `string` | Dirección de correo electrónico del remitente en el encabezado DE, que es visible para los destinatarios de correo electrónico de sus clientes. |
| `SenderDisplayName` | `string` | Nombre del remitente que se muestra en la libreta de direcciones, normalmente una combinación de un nombre o nombre determinado, una inicial intermedia y un apellido o apellido |
| `SenderObjectId` | `string` | Identificador único de la cuenta del remitente en Azure AD |
| `RecipientEmailAddress` | `string` | Dirección de correo electrónico del destinatario, después de la expansión de la lista de distribución. |
| `RecipientObjectId` | `string` | Identificador único para el destinatario de correo electrónico en Azure AD |
| `FileName` | `string` | Nombre del archivo donde se aplicó la acción registrada |
| `FileType` | `string` | Tipo de extensión de archivo |
| `SHA256` | `string` | SHA-256 del archivo donde se aplicó la acción registrada. Este campo no suele estar rellenado; use la columna SHA1 cuando se encuentre disponible. |
| `ThreatTypes` | `string` | Verdict from the email filtering stack on whether the email contains malware, phishing, or other threats |
| `ThreatNames` | `string` | Nombre de detección de malware u otras amenazas encontradas |
| `DetectionMethods` | `string` | Métodos usados para detectar malware, phishing u otras amenazas encontradas en el correo electrónico |
| `ReportId` | `long` | Identificador de eventos basado en un contador de repetición. Para identificar eventos únicos, esta columna debe usarse junto con las columnas DeviceName y Timestamp. |
| `FileSize` | `string` | Tamaño del archivo en bytes |

## <a name="related-topics"></a>Temas relacionados

- [Información general sobre la búsqueda avanzada de amenazas](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades](advanced-hunting-query-emails-devices.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)
