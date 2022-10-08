---
title: Tabla EmailAttachmentInfo del esquema de búsqueda avanzada
description: Obtenga más información sobre los datos adjuntos en la tabla de EmailAttachmentInfo del esquema de búsqueda avanzada.
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernética, Microsoft 365 Defender, microsoft 365, m365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, EmailAttachmentInfo, id. de mensaje de red, remitente, destinatario, identificador de datos adjuntos, nombre de datos adjuntos, veredicto de malware
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
ms.openlocfilehash: 24ceb3addf4df4f7c142dc9a5fe5dbcf23458a12
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68086979"
---
# <a name="emailattachmentinfo"></a>EmailAttachmentInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**

- Microsoft 365 Defender
- Microsoft Defender para Office 365

La `EmailAttachmentInfo` tabla del esquema [de búsqueda avanzada](advanced-hunting-overview.md) contiene información sobre los datos adjuntos de los correos electrónicos procesados por Microsoft Defender para Office 365. Utilice esta referencia para crear consultas que devuelvan información sobre la tabla.

Para obtener información sobre otras tablas del esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).

> [!IMPORTANT]
> Parte de la información se refiere a productos preliminares que pueden ser modificados sustancialmente antes de su lanzamiento comercial. Microsoft no otorga garantías, expresas o implícitas, con respecto a la información que aquí se proporciona.

| Nombre de columna | Tipo de datos | Descripción |
|-------------|-----------|-------------|
| `Timestamp` | `datetime` | Fecha y hora en que se registró el evento. |
| `NetworkMessageId` | `string` | Identificador único del correo electrónico, generado por Microsoft 365 |
| `SenderFromAddress` | `string` | Dirección de correo electrónico del remitente en el encabezado DE, que es visible para los destinatarios de correo electrónico de sus clientes. |
| `SenderDisplayName` | `string` | Nombre del remitente que se muestra en la libreta de direcciones, normalmente una combinación de un nombre o nombre determinado, una inicial intermedia y un apellido o apellido |
| `SenderObjectId` | `string` | Identificador único de la cuenta del remitente en Azure AD |
| `RecipientEmailAddress` | `string` | Dirección de correo electrónico del destinatario, después de la expansión de la lista de distribución. |
| `RecipientObjectId` | `string` | Identificador único del destinatario del correo electrónico en Azure AD |
| `FileName` | `string` | Nombre del archivo donde se aplicó la acción registrada |
| `FileType` | `string` | Tipo de extensión de archivo |
| `SHA256` | `string` | SHA-256 del archivo donde se aplicó la acción registrada. Este campo no suele estar rellenado; use la columna SHA1 cuando se encuentre disponible. |
| `ThreatTypes` | `string` | Veredicto de la pila de filtrado de correo electrónico sobre si el correo electrónico contiene malware, suplantación de identidad (phishing) u otras amenazas |
| `ThreatNames` | `string` | Nombre de detección de malware u otras amenazas encontradas |
| `DetectionMethods` | `string` | Métodos usados para detectar malware, suplantación de identidad (phishing) u otras amenazas que se encuentran en el correo electrónico |
| `ReportId` | `long` | Identificador de eventos basado en un contador de repetición. Para identificar eventos únicos, esta columna debe usarse junto con las columnas DeviceName y Timestamp. |
| `FileSize` | `string` | Tamaño del archivo en bytes |

## <a name="related-topics"></a>Temas relacionados

- [Información general sobre la búsqueda avanzada de amenazas](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades](advanced-hunting-query-emails-devices.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)
