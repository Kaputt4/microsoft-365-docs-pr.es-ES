---
title: Tabla EmailPostDeliveryEvents en el esquema de búsqueda avanzada
description: Obtenga información sobre las acciones posteriores a la entrega realizadas en los correos electrónicos de Microsoft 365 en la tabla EmailPostDeliveryEvents del esquema de búsqueda avanzada
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de ciberamenazas, protección contra amenazas de Microsoft, microsoft 365, mtp, m365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, EmailPostDeliveryEvents, id. de mensaje de red, remitente, destinatario, id. de datos adjuntos, nombre de datos adjuntos, veredicto de malware, veredicto de suplantación de identidad, recuento de datos adjuntos, recuento de vínculos, recuento de direcciones URL
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
ms.openlocfilehash: d7920be05156320411f3907cbcdae88d315b5136
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929714"
---
# <a name="emailpostdeliveryevents"></a>EmailPostDeliveryEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

La tabla del esquema de búsqueda avanzada contiene información sobre las acciones posteriores a la entrega realizadas en los mensajes de correo electrónico `EmailPostDeliveryEvents` procesados por Microsoft 365. [](advanced-hunting-overview.md) Utilice esta referencia para crear consultas que devuelvan información sobre la tabla.

>[!TIP]
> Para obtener información detallada acerca de los tipos de eventos (valores) admitidos por una tabla, use la referencia de esquema integrada `ActionType` disponible en el centro de seguridad. [](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)

Para obtener más información sobre mensajes de correo electrónico individuales, también puede usar [`EmailEvents`](advanced-hunting-emailevents-table.md) las [`EmailAttachmentInfo`](advanced-hunting-emailattachmentinfo-table.md) tablas , [`EmailUrlInfo`](advanced-hunting-emailurlinfo-table.md) y. Para obtener información sobre otras tablas del esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).

| Nombre de columna | Tipo de datos | Descripción |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Fecha y hora en que se registró el evento. |
| `EventId` | cadena | Identificador único del evento |
| `NetworkMessageId` | string | Identificador único del correo electrónico, generado por Microsoft 365 |
| `InternetMessageId` | cadena | Identificador público para el correo electrónico que establece el sistema de correo electrónico de envío. |
| `Action` | cadena | Acción realizada en la entidad |
| `ActionType` | string | Tipo de actividad que desencadenó el evento: Corrección manual, PHISH ZAP, MALWARE ZAP |
| `ActionTrigger` | string | Indica si un administrador desencadenó una acción (manualmente o mediante la aprobación de una acción automatizada pendiente) o mediante algún mecanismo especial, como un ZAP o una entrega dinámica |
| `ActionResult` | string | Resultado de la acción |
| `RecipientEmailAddress` | cadena | Dirección de correo electrónico del destinatario, después de la expansión de la lista de distribución. |
| `DeliveryLocation` | cadena | Ubicación en la que se entregó el correo electrónico: bandeja de entrada / carpeta, local / externo, correo no deseado, cuarentena, erróneo, descartado, elementos eliminados. |

## <a name="supported-event-types"></a>Tipos de eventos admitidos
En esta tabla se capturan eventos con los siguientes `ActionType` valores:

- **Corrección manual:** un administrador tomó medidas manualmente en un mensaje de correo electrónico después de entregarlo al buzón de usuario. Esto incluye acciones realizadas manualmente a [través](../office-365-security/threat-explorer.md) del Explorador de amenazas o aprobaciones de acciones de investigación y [respuesta automatizadas (AIR).](mtp-autoir-actions.md)
- **PHISH ZAP:** purga automática de cero horas [(ZAP)](../office-365-security/zero-hour-auto-purge.md) tomó medidas en un correo electrónico de suplantación de identidad después de la entrega.
- **Malware ZAP:** purga automática de cero horas (ZAP) tomó medidas en un mensaje de correo electrónico que contenía malware después de la entrega.

## <a name="related-topics"></a>Temas relacionados
- [Información general sobre la búsqueda avanzada](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades](advanced-hunting-query-emails-devices.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)
