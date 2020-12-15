---
title: Tabla EmailAttachmentInfo del esquema de búsqueda avanzada
description: Obtenga más información sobre los datos adjuntos en la tabla de EmailAttachmentInfo del esquema de búsqueda avanzada.
keywords: caza avanzado, cazar amenazas, búsqueda de amenazas en el ciberespacio, protección contra amenazas de Microsoft, Microsoft 365, MTP, M365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, EmailAttachmentInfo, identificador de mensaje de red, remitente, destinatario, identificador de datos adjuntos, nombre de archivo adjunto, veredicto de malware
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
mms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 6d88303b34f78abc857e9aec749bf2f58090f43a
ms.sourcegitcommit: 1a9f0f878c045e1ddd59088ca2a94397605a242a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/14/2020
ms.locfileid: "49667654"
---
# <a name="emailattachmentinfo"></a>EmailAttachmentInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender



La `EmailAttachmentInfo` tabla del esquema de [búsqueda avanzada](advanced-hunting-overview.md) contiene información sobre los datos adjuntos de los mensajes de correo electrónico procesados por Microsoft Defender para Office 365. Utilice esta referencia para crear consultas que devuelvan información sobre la tabla.

Para obtener información sobre otras tablas del esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).

| Nombre de columna | Tipo de datos | Descripción |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Fecha y hora en que se registró el evento. |
| `AttachmentId` | cadena | Identificador único de datos adjuntos al correo electrónico |
| `NetworkMessageId` | cadena | Identificador único del correo electrónico generado por Microsoft 365 |
| `SenderFromAddress` | cadena | Dirección de correo electrónico del remitente en el encabezado DE, que es visible para los destinatarios de correo electrónico de sus clientes. |
| `RecipientEmailAddress` | cadena | Dirección de correo electrónico del destinatario, después de la expansión de la lista de distribución. |
| `FileName` | cadena | Nombre del archivo donde se aplicó la acción registrada |
| `FileType` | cadena | Tipo de extensión de archivo |
| `SHA256` | cadena | SHA-256 del archivo donde se aplicó la acción registrada. Este campo no suele estar rellenado; use la columna SHA1 cuando se encuentre disponible. |
| `MalwareFilterVerdict` | cadena | Veredicto sobre la pila de mensajes de correo electrónico filtrados para determinar si los correos contienen código malintencionado: Malware, no malware |
| `MalwareDetectionMethod` | cadena | Método usado para detectar malware en el correo electrónico: motor antimalware, reputación de archivos, datos adjuntos seguros |
| `SenderDisplayName` | string | Nombre del remitente que se muestra en la libreta de direcciones, normalmente una combinación de un nombre determinado o de un nombre, una inicial del segundo nombre y un apellido o un apellido |
| `SenderObjectId` | string | Identificador único de la cuenta del remitente en Azure AD |
| `ThreatTypes` | string | Veredicto de la pila de filtrado de correo electrónico de si el correo electrónico contiene malware, suplantación de identidad (phishing) u otras amenazas |
| `ThreatNames` | string | Nombre de detección de malware u otras amenazas encontradas |

## <a name="related-topics"></a>Temas relacionados
- [Información general sobre la búsqueda avanzada](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades](advanced-hunting-query-emails-devices.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)
