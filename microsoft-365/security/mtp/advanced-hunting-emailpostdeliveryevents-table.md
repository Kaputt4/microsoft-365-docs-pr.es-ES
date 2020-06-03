---
title: Tabla EmailPostDeliveryEvents en el esquema de búsqueda avanzada
description: Obtenga información sobre las acciones posteriores a la entrega realizadas en los correos electrónicos de Microsoft 365 en la tabla EmailPostDeliveryEvents del esquema de búsqueda avanzada
keywords: caza avanzado, caza de amenazas, búsqueda de amenazas en el ciberespacio, protección contra amenazas de Microsoft, Microsoft 365, MTP, M365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, EmailPostDeliveryEvents, identificador de mensaje de red, remitente, destinatario, identificador de datos adjuntos, nombre de datos adjuntos, veredicto
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
ms.openlocfilehash: f4b34abdbfcbd6c3a2f142001a3d486485c86fcd
ms.sourcegitcommit: eee4f651bd51d5aedd64e42d02bfed8ccb9be4cd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "44515938"
---
# <a name="emailpostdeliveryevents"></a>EmailPostDeliveryEvents

**Se aplica a:**
- Protección contra amenazas de Microsoft

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

La `EmailPostDeliveryEvents` tabla del esquema de [búsqueda avanzada](advanced-hunting-overview.md) contiene información sobre las acciones posteriores a la entrega realizadas en los mensajes de correo electrónico procesados por Microsoft 365. Utilice esta referencia para crear consultas que devuelvan información sobre la tabla.

Para obtener más información sobre los mensajes de correo electrónico individuales, también puede usar las [`EmailEvents`](advanced-hunting-emailevents-table.md) [`EmailAttachmentInfo`](advanced-hunting-emailattachmentinfo-table.md) tablas, y [`EmailUrlInfo`](advanced-hunting-emailurlinfo-table.md) . Para obtener información sobre otras tablas del esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).

| Nombre de columna | Tipo de datos | Descripción |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Fecha y hora en que se registró el evento. |
| `EventId` | string | Identificador único del evento |
| `NetworkMessageId` | string | Identificador único del correo electrónico generado por Microsoft 365 |
| `InternetMessageId` | string | Identificador público para el correo electrónico que establece el sistema de correo electrónico de envío. |
| `Action` | string | Acción realizada en la entidad |
| `ActionType` | string | Tipo de actividad que ha desencadenado el evento: corrección manual, ZAP de Phish, ZAP de malware |
| `ActionTrigger` | string | Indica si una acción ha desencadenado un administrador (manualmente o mediante la aprobación de una acción automatizada pendiente) o mediante algún mecanismo especial, como una ZAP o una entrega dinámica |
| `ActionResult` | string | Resultado de la acción |
| `RecipientEmailAddress` | string | Dirección de correo electrónico del destinatario, después de la expansión de la lista de distribución. |
| `DeliveryLocation` | cadena | Ubicación en la que se entregó el correo electrónico: bandeja de entrada / carpeta, local / externo, correo no deseado, cuarentena, erróneo, descartado, elementos eliminados. |

## <a name="supported-event-types"></a>Tipos de eventos admitidos
Esta tabla captura eventos con los siguientes `ActionType` valores:

- **Corrección manual** : un administrador realizó manualmente una acción en un mensaje de correo electrónico después de que se entregó al buzón del usuario. Esto incluye las acciones realizadas manualmente a través del [Explorador de amenazas](../office-365-security/threat-explorer.md) o las aprobaciones de [las acciones de investigación y respuesta automáticas (Air)](mtp-autoir-actions.md).
- **Zap phish** : la [depuración automática de cero horas (ZAP)](../office-365-security/zero-hour-auto-purge.md) llevó a cabo una acción en un correo de suplantación de identidad tras la entrega.
- **Zap de malware** : la depuración automática de cero horas (ZAP) llevó a cabo una acción en un mensaje de correo electrónico que contiene malware después de la entrega.

## <a name="related-topics"></a>Temas relacionados
- [Búsqueda proactiva de amenazas](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Búsqueda de amenazas en dispositivos y mensajes de correo electrónico](advanced-hunting-query-emails-devices.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)