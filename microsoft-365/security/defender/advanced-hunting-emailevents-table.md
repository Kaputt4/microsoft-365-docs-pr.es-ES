---
title: La tabla EmailEvents en el esquema de búsqueda avanzada
description: Obtenga información sobre los eventos asociados a Microsoft 365 correos electrónicos en la tabla EmailEvents del esquema de búsqueda avanzada.
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de amenazas cibernética, Microsoft 365 Defender, microsoft 365, m365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, EmailEvents, id. de mensaje de red, remitente, destinatario, identificador de datos adjuntos, nombre de datos adjuntos, veredicto de malware, veredicto de phishing, recuento de datos adjuntos, recuento de vínculos, recuento de direcciones URL
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
ms.openlocfilehash: f4456dc29f4d62703041b9c386aa7c9fa132695a
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/06/2022
ms.locfileid: "64667370"
---
# <a name="emailevents"></a>EmailEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**

- Microsoft 365 Defender

La `EmailEvents` tabla del esquema [de búsqueda avanzada](advanced-hunting-overview.md) contiene información sobre eventos que implican el procesamiento de correos electrónicos en Microsoft Defender para Office 365. Utilice esta referencia para crear consultas que devuelvan información sobre la tabla.

> [!TIP]
> Para obtener información detallada sobre los tipos de eventos (`ActionType`valores) admitidos por una tabla, use la referencia de esquema integrada disponible en el Defender for Cloud.

Para obtener información sobre otras tablas del esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).

> [!IMPORTANT]
> Parte de la información se refiere a productos preliminares que pueden ser modificados sustancialmente antes de su lanzamiento comercial. Microsoft no otorga garantías, expresas o implícitas, con respecto a la información que aquí se proporciona.

| Nombre de columna | Tipo de datos | Descripción |
|-------------|-----------|-------------|
| `Timestamp` | `datetime` | Fecha y hora en que se registró el evento. |
| `NetworkMessageId` | `string` | Identificador único del correo electrónico, generado por Microsoft 365 |
| `InternetMessageId` | `string` | Identificador público para el correo electrónico que establece el sistema de correo electrónico de envío. |
| `SenderMailFromAddress` | `string` | Dirección de correo electrónico del remitente en el encabezado MAIL FROM, que también se conoce como remitente del sobre o la dirección de Ruta de devolución. |
| `SenderFromAddress` | `string` | Dirección de correo electrónico del remitente en el encabezado DE, que es visible para los destinatarios de correo electrónico de sus clientes. |
| `SenderDisplayName` | `string` | Nombre del remitente que se muestra en la libreta de direcciones, normalmente una combinación de un nombre o nombre determinado, una inicial intermedia y un apellido o apellido |
| `SenderObjectId` | `string` |Identificador único de la cuenta del remitente en Azure AD |
| `SenderMailFromDomain` | `string` | Dominio de remitente en el encabezado MAIL FROM, que también se conoce como remitente del sobre o la dirección de Ruta de devolución. |
| `SenderFromDomain` | `string` | Dominio del remitente en el encabezado FROM, que es visible para los destinatarios del correo electrónico en los clientes de correo. |
| `SenderIPv4` | `string` | Dirección IPv4 del último servidor de correo detectado que retransmitió el mensaje. |
| `SenderIPv6` | `string` | Dirección IPv6 del último servidor de correo detectado que retransmitió el mensaje. |
| `RecipientEmailAddress` | `string` | Dirección de correo electrónico del destinatario, después de la expansión de la lista de distribución. |
| `RecipientObjectId` | `string` | Identificador único del destinatario del correo electrónico en Azure AD |
| `Subject` | `string` | Asunto del correo electrónico. |
| `EmailClusterId` | `string` | Identificador para el grupo de correos electrónicos similares agrupados según el análisis heurístico de su contenido. |
| `EmailDirection` | `string` | Dirección del correo electrónico relativo a su red: entrante, saliente, dentro de la organización. |
| `DeliveryAction` | `string` | Acción de entrega del correo electrónico: entregado, marcado como correo no deseado, bloqueado o reemplazado. |
| `DeliveryLocation` | `string` | Ubicación en la que se entregó el correo electrónico: bandeja de entrada / carpeta, local / externo, correo no deseado, cuarentena, erróneo, descartado, elementos eliminados. |
| `ThreatTypes` | `string` | Veredicto de la pila de filtrado de correo electrónico sobre si el correo electrónico contiene malware, suplantación de identidad (phishing) u otras amenazas |
| `ThreatNames` | `string` |Nombre de detección de malware u otras amenazas encontradas |
| `DetectionMethods` | `string` | Métodos usados para detectar malware, suplantación de identidad (phishing) u otras amenazas que se encuentran en el correo electrónico |
| `ConfidenceLevel` | `string` | Lista de niveles de confianza de los veredictos de spam o phishing. En el caso del correo no deseado, esta columna muestra el nivel de confianza de correo no deseado (SCL), que indica si el correo electrónico se omitió (-1), se encontró que no era spam (0,1), se encontró que era correo no deseado con confianza moderada (5,6) o se encontró que era spam con alta confianza (9). En el caso de phishing, esta columna muestra si el nivel de confianza es "Alto" o "Bajo". |
| `EmailAction` | `string` | Acción final tomada sobre el correo electrónico basada en el veredicto del filtro, las directivas y las acciones del usuario: mover el mensaje a la carpeta correo no deseado, agregar encabezado X, modificar el asunto, redirigir mensaje, eliminar mensaje, enviar a cuarentena, no realizar ninguna acción, enviar mensaje con CCO. |
| `EmailActionPolicy` | `string` | Directiva de acciones que entró en vigor: correo electrónico no deseado con alto nivel de confianza, correo electrónico no deseado, correo electrónico no deseado masivo, correo electrónico no deseado de suplantación de identidad, suplantación de un dominio protegido contra la suplantación de identidad, suplantación de un usuario protegido contra la suplantación de identidad, suplantación de identidad en contra de las medidas contra la suplantación de identidad, suplantación del gráfico contra la suplantación de identidad, contra el software malintencionado, datos adjuntos seguros, reglas de transporte empresarial (RTE). |
| `EmailActionPolicyGuid` | `string` | Identificador único de la directiva que determinó la acción final tomada sobre el correo electrónico. |
| `AttachmentCount` | `int` | Número de datos adjuntos en el correo electrónico. |
| `UrlCount` | `int` | Número de URL insertadas en el correo electrónico. |
| `EmailLanguage` | `string` | Lenguaje detectado en el contenido del correo electrónico. |
| `Connectors` | `string` | Instrucciones personalizadas que definen el flujo de correo de la organización y cómo se enrutó el correo electrónico |
| `OrgLevelAction` | `string` | Acción realizada en el correo electrónico en respuesta a coincidencias con una directiva definida en el nivel organizativo |
| `OrgLevelPolicy` | `string` | Directiva organizativa que desencadenó la acción realizada en el correo electrónico |
| `UserLevelAction` | `string` | Acción realizada en el correo electrónico en respuesta a coincidencias con una directiva de buzón definida por el destinatario |
| `UserLevelPolicy` | `string` | Directiva de buzón de usuario final que desencadenó la acción realizada en el correo electrónico |
| `ReportId` | `long` | Identificador de eventos basado en un contador de repetición. Para identificar eventos únicos, esta columna debe usarse junto con las columnas DeviceName y Timestamp. |
| `AuthenticationDetails` | `string` | Lista de veredictos de paso o error por protocolos de autenticación por correo electrónico como DMARC, DKIM, SPF o una combinación de varios tipos de autenticación (CompAuth) |

## <a name="related-topics"></a>Temas relacionados

- [Información general sobre la búsqueda avanzada de amenazas](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades](advanced-hunting-query-emails-devices.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)
