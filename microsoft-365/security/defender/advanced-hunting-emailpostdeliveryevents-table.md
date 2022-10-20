---
title: Tabla EmailPostDeliveryEvents en el esquema de búsqueda avanzada
description: Obtenga información sobre las acciones posteriores a la entrega realizadas en los correos electrónicos de Microsoft 365 en la tabla EmailPostDeliveryEvents del esquema de búsqueda avanzada.
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de ciberamenazas, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, EmailPostDeliveryEvents, network message id, sender, recipient, attachment id, attachment name, malware verdict, phishing verdict, attachment count, link count, url count
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
ms.topic: conceptual
ms.openlocfilehash: 6567ba4f5fba6f0cef19b89105702e3493310db5
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68631554"
---
# <a name="emailpostdeliveryevents"></a>EmailPostDeliveryEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender
- Microsoft Defender para Office 365

La `EmailPostDeliveryEvents` tabla del esquema [de búsqueda avanzada](advanced-hunting-overview.md) contiene información sobre las acciones posteriores a la entrega realizadas en los mensajes de correo electrónico procesados por Microsoft 365. Utilice esta referencia para crear consultas que devuelvan información sobre la tabla.

>[!TIP]
> Para obtener información detallada sobre los tipos de eventos (`ActionType` valores) admitidos por una tabla, use la referencia de esquema integrada disponible en Defender for Cloud.

Para obtener más información sobre los mensajes de correo electrónico individuales, también puede usar las [`EmailEvents`](advanced-hunting-emailevents-table.md)tablas , [`EmailAttachmentInfo`](advanced-hunting-emailattachmentinfo-table.md)y [`EmailUrlInfo`](advanced-hunting-emailurlinfo-table.md) . Para obtener información sobre otras tablas del esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).

> [!IMPORTANT]
> Parte de la información se refiere a productos preliminares que pueden ser modificados sustancialmente antes de su lanzamiento comercial. Microsoft no otorga garantías, expresas o implícitas, con respecto a la información que aquí se proporciona.

| Nombre de columna | Tipo de datos | Descripción |
|-------------|-----------|-------------|
| `Timestamp` | `datetime` | Fecha y hora en que se registró el evento. |
| `NetworkMessageId` | `string` | Identificador único del correo electrónico, generado por Microsoft 365 |
| `InternetMessageId` | `string` | Identificador público para el correo electrónico que establece el sistema de correo electrónico de envío. |
| `Action` | `string` | Acción realizada en la entidad |
| `ActionType` | `string` | Tipo de actividad que desencadenó el evento: Corrección manual, Phish ZAP, Malware ZAP |
| `ActionTrigger` | `string` | Indica si un administrador ha desencadenado una acción (manualmente o a través de la aprobación de una acción automatizada pendiente) o por algún mecanismo especial, como un ZAP o una entrega dinámica. |
| `ActionResult` | `string` | Resultado de la acción |
| `RecipientEmailAddress` | `string` | Dirección de correo electrónico del destinatario, después de la expansión de la lista de distribución. |
| `DeliveryLocation` | `string` | Ubicación en la que se entregó el correo electrónico: bandeja de entrada / carpeta, local / externo, correo no deseado, cuarentena, erróneo, descartado, elementos eliminados. |
| `ReportId` | `long` | Identificador de eventos basado en un contador de repetición. Para identificar eventos únicos, esta columna debe usarse junto con las columnas DeviceName y Timestamp. |
| `ThreatTypes` | `string` | Veredicto de la pila de filtrado de correo electrónico sobre si el correo electrónico contiene malware, suplantación de identidad (phishing) u otras amenazas |
| `DetectionMethods` | `string` | Métodos usados para detectar malware, suplantación de identidad (phishing) u otras amenazas que se encuentran en el correo electrónico |

## <a name="supported-event-types"></a>Tipos de eventos admitidos
Esta tabla captura eventos con los siguientes `ActionType` valores:

- **Corrección manual** : un administrador tomó medidas manualmente en un mensaje de correo electrónico después de entregarlo al buzón de usuario. Esto incluye las acciones realizadas manualmente a través del [Explorador de amenazas](../office-365-security/threat-explorer.md) o las aprobaciones de [acciones automatizadas de investigación y respuesta (AIR).](m365d-autoir-actions.md)
- **Phish ZAP** : la [purga automática de cero horas (ZAP)](../office-365-security/zero-hour-auto-purge.md) tomó medidas en un correo electrónico de suplantación de identidad (phishing) después de la entrega.
- **ZAP de malware** : la purga automática de cero horas (ZAP) tomó medidas en un mensaje de correo electrónico encontrado que contiene malware después de la entrega.

## <a name="related-topics"></a>Temas relacionados
- [Información general sobre la búsqueda avanzada de amenazas](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades](advanced-hunting-query-emails-devices.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)
