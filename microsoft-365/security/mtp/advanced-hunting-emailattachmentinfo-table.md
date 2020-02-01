---
title: Tabla EmailAttachmentInfo del esquema de búsqueda avanzada
description: Obtenga más información sobre los datos adjuntos en la tabla de EmailAttachmentInfo del esquema de búsqueda avanzada.
keywords: caza avanzado, cazar amenazas, búsqueda de amenazas en el ciberespacio, protección contra amenazas de Microsoft, Microsoft 365, MTP, M365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, EmailAttachmentInfo, identificador de mensaje de red, remitente, destinatario, identificador de datos adjuntos, nombre de datos adjuntos, veredicto
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
ms.openlocfilehash: 9ae500e29c12a29527970c595c18eab1cadfb5dc
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "41600377"
---
# <a name="emailattachmentinfo"></a>EmailAttachmentInfo

**Se aplica a:**
- Protección contra amenazas de Microsoft

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

La `EmailAttachmentInfo` tabla del esquema de [búsqueda avanzada](advanced-hunting-overview.md) contiene información sobre los datos adjuntos en los correos electrónicos procesados por la ATP de Office 365. Utilice esta referencia para crear consultas que devuelvan información sobre la tabla.

Para obtener información sobre otras tablas del esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).

| Nombre de columna | Tipo de datos | Descripción |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Fecha y hora en que se registró el evento. |
| `AttachmentId` | cadena | Identificador único de datos adjuntos al correo electrónico |
| `NetworkMessageId` | cadena | Identificador único de correo electrónico, generado por Office 365 |
| `SenderFromAddress` | cadena | Dirección de correo electrónico del remitente en el encabezado DE, que es visible para los destinatarios de correo electrónico de sus clientes. |
| `RecipientEmailAddress` | cadena | Dirección de correo electrónico del destinatario, después de la expansión de la lista de distribución. |
| `FileName` | cadena | Nombre del archivo donde se aplicó la acción registrada |
| `FileType` | cadena | Tipo de extensión de archivo |
| `SHA256` | cadena | SHA-256 del archivo donde se aplicó la acción registrada. Este campo no suele estar rellenado; use la columna SHA1 cuando se encuentre disponible. |
| `MalwareFilterVerdict` | cadena | Veredicto sobre la pila de mensajes de correo electrónico filtrados para determinar si los correos contienen código malintencionado: Malware, no malware |
| `MalwareDetectionMethod` | cadena | Método utilizado para detectar el código malintencionado en el correo electrónico: Motor de antimalware, reputación del archivo, archivos adjuntos seguros de ATP. |

## <a name="related-topics"></a>Temas relacionados
- [Búsqueda proactiva de amenazas](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Búsqueda de amenazas en dispositivos y mensajes de correo electrónico](advanced-hunting-query-emails-devices.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)