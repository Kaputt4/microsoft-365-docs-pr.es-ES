---
title: Tabla EmailPostDeliveryEvents en el esquema de búsqueda avanzada
description: Obtenga información sobre las acciones posteriores a la entrega Microsoft 365 mensajes de correo electrónico en la tabla EmailPostDeliveryEvents del esquema de búsqueda avanzada
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernéticas, Microsoft 365 Defender, microsoft 365, m365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, EmailPostDeliveryEvents, id. de mensaje de red, remitente, destinatario, id. de datos adjuntos, nombre de datos adjuntos, veredicto de malware, veredicto de phishing, recuento de datos adjuntos, recuento de vínculos, recuento de direcciones URL
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
ms.openlocfilehash: 59d611ae89aeedf386cd0dcad5939a9510f0820e
ms.sourcegitcommit: 6dcc3b039e0f0b9bae17c386f14ed2b577b453a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/15/2021
ms.locfileid: "61530674"
---
# <a name="emailpostdeliveryevents"></a>EmailPostDeliveryEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

La tabla del esquema de búsqueda avanzada contiene información sobre las acciones posteriores a la entrega realizadas en los mensajes de correo electrónico procesados `EmailPostDeliveryEvents` por Microsoft 365. [](advanced-hunting-overview.md) Utilice esta referencia para crear consultas que devuelvan información sobre la tabla.

>[!TIP]
> Para obtener información detallada acerca de los tipos de eventos ( valores) admitidos por una tabla, use la referencia de esquema integrada `ActionType` disponible en Defender para la nube.

Para obtener más información acerca de los mensajes de correo electrónico individuales, también puede usar [`EmailEvents`](advanced-hunting-emailevents-table.md) las tablas , y [`EmailAttachmentInfo`](advanced-hunting-emailattachmentinfo-table.md) [`EmailUrlInfo`](advanced-hunting-emailurlinfo-table.md) . Para obtener información sobre otras tablas del esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).

> [!IMPORTANT]
> Parte de la información se refiere a productos preliminares que pueden ser modificados sustancialmente antes de su lanzamiento comercial. Microsoft no otorga garantías, expresas o implícitas, con respecto a la información que aquí se proporciona.

| Nombre de columna | Tipo de datos | Description |
|-------------|-----------|-------------|
| `Timestamp` | `datetime` | Fecha y hora en que se registró el evento. |
| `NetworkMessageId` | `string` | Identificador único del correo electrónico, generado por Microsoft 365 |
| `InternetMessageId` | `string` | Identificador público para el correo electrónico que establece el sistema de correo electrónico de envío. |
| `Action` | `string` | Acción realizada en la entidad |
| `ActionType` | `string` | Tipo de actividad que desencadenó el evento: Corrección manual, PHISH ZAP, MALWARE ZAP |
| `ActionTrigger` | `string` | Indica si un administrador desencadenó una acción (manualmente o mediante la aprobación de una acción automatizada pendiente) o por algún mecanismo especial, como un ZAP o una entrega dinámica |
| `ActionResult` | `string` | Resultado de la acción |
| `RecipientEmailAddress` | `string` | Dirección de correo electrónico del destinatario, después de la expansión de la lista de distribución. |
| `DeliveryLocation` | `string` | Ubicación en la que se entregó el correo electrónico: bandeja de entrada / carpeta, local / externo, correo no deseado, cuarentena, erróneo, descartado, elementos eliminados. |
| `ReportId` | `long` | Identificador de eventos basado en un contador de repetición. Para identificar eventos únicos, esta columna debe usarse junto con las columnas DeviceName y Timestamp. |
| `ThreatTypes` | `string` | Verdict from the email filtering stack on whether the email contains malware, phishing, or other threats |
| `DetectionMethods` | `string` | Métodos usados para detectar malware, phishing u otras amenazas encontradas en el correo electrónico |

## <a name="supported-event-types"></a>Tipos de eventos admitidos
En esta tabla se capturan eventos con los siguientes `ActionType` valores:

- **Corrección manual:** un administrador realizó acciones manualmente en un mensaje de correo electrónico después de entregarlo al buzón de usuario. Esto incluye acciones realizadas manualmente a través del [Explorador de](../office-365-security/threat-explorer.md) amenazas o aprobaciones de acciones de investigación y respuesta [automatizadas (AIR).](m365d-autoir-actions.md)
- **PHISH ZAP:** la purga automática de hora cero [(ZAP)](../office-365-security/zero-hour-auto-purge.md) tomó medidas en un correo electrónico de suplantación de identidad (phishing) después de la entrega.
- **ZAP de malware:** la purga automática de hora cero (ZAP) tomó medidas en un mensaje de correo electrónico encontrado que contiene malware después de la entrega.

## <a name="related-topics"></a>Temas relacionados
- [Información general sobre la búsqueda avanzada de amenazas](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades](advanced-hunting-query-emails-devices.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)
