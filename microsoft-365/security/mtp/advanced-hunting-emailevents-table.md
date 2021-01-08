---
title: La tabla EmailEvents en el esquema de búsqueda avanzada
description: Obtenga información sobre los eventos asociados con los correos electrónicos de Microsoft 365 en la tabla EmailEvents del esquema de búsqueda avanzada
keywords: búsqueda avanzada, búsqueda de amenazas, búsqueda de ciberamenazas, protección contra amenazas de Microsoft, microsoft 365, mtp, m365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, EmailEvents, id. de mensaje de red, remitente, destinatario, id. de datos adjuntos, nombre de datos adjuntos, veredicto de malware, veredicto de suplantación de identidad, recuento de datos adjuntos, recuento de vínculos, recuento de direcciones URL
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 6dbd7473074212c6bc257e683288040056426048
ms.sourcegitcommit: ec293978e951b09903b79e6642aa587824935e0c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2021
ms.locfileid: "49780277"
---
# <a name="emailevents"></a>EmailEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender



La tabla del esquema de búsqueda avanzada contiene información sobre eventos relacionados con el procesamiento de correos electrónicos en `EmailEvents` Microsoft Defender para Office 365. [](advanced-hunting-overview.md) Use esta referencia para crear consultas que devuelvan información de esta tabla.

>[!TIP]
> Para obtener información detallada acerca de los tipos de eventos (valores) admitidos por una tabla, use la referencia de esquema integrada `ActionType` disponible en el centro de seguridad. [](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)

Para obtener información sobre otras tablas del esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).

| Nombre de columna | Tipo de datos | Descripción |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Fecha y hora en que se registró el evento. |
| `EmailId` | cadena | Identificador único del destinatario y correo electrónico. |
| `NetworkMessageId` | cadena | Identificador único del correo electrónico, generado por Microsoft 365 |
| `InternetMessageId` | cadena | Identificador público para el correo electrónico que establece el sistema de correo electrónico de envío. |
| `SenderMailFromAddress` | cadena | Dirección de correo electrónico del remitente en el encabezado MAIL FROM, que también se conoce como remitente del sobre o la dirección de Ruta de devolución. |
| `SenderFromAddress` | cadena | Dirección de correo electrónico del remitente en el encabezado DE, que es visible para los destinatarios de correo electrónico de sus clientes. |
| `SenderMailFromDomain` | cadena | Dominio de remitente en el encabezado MAIL FROM, que también se conoce como remitente del sobre o la dirección de Ruta de devolución. |
| `SenderFromDomain` | cadena | Dominio del remitente en el encabezado FROM, que es visible para los destinatarios del correo electrónico en los clientes de correo. |
| `SenderIPv4` | cadena | Dirección IPv4 del último servidor de correo detectado que retransmitió el mensaje. |
| `SenderIPv6` | cadena | Dirección IPv6 del último servidor de correo detectado que retransmitió el mensaje. |
| `RecipientEmailAddress` | cadena | Dirección de correo electrónico del destinatario, después de la expansión de la lista de distribución. |
| `Subject` | cadena | Asunto del correo electrónico. |
| `EmailClusterId` | cadena | Identificador para el grupo de correos electrónicos similares agrupados según el análisis heurístico de su contenido. |
| `EmailDirection` | cadena | Dirección del correo electrónico relativo a su red: entrante, saliente, dentro de la organización. |
| `DeliveryAction` | cadena | Acción de entrega del correo electrónico: entregado, marcado como correo no deseado, bloqueado o reemplazado. |
| `DeliveryLocation` | cadena | Ubicación en la que se entregó el correo electrónico: bandeja de entrada / carpeta, local / externo, correo no deseado, cuarentena, erróneo, descartado, elementos eliminados. |
| `PhishFilterVerdict` | cadena | Veredicto sobre la pila de correos electrónicos filtrados para determinar si el correo es para suplantar la identidad: suplantar identidad o no suplantar identidad. |
| `PhishDetectionMethod` | cadena | Método usado para detectar el correo electrónico como suplantación de identidad: reputación de url malintencionada, detonación de url de vínculos seguros, filtro de suplantación de identidad avanzado, filtro de suplantación de identidad general, anti-suplantación de identidad: dentro de la organización, contra la suplantación de identidad: dominio externo, suplantación de dominio, suplantación de usuario, suplantación de marca |
| `MalwareFilterVerdict` | cadena | Veredicto sobre la pila de mensajes de correo electrónico filtrados para determinar si los correos contienen código malintencionado: Malware, no malware |
| `MalwareDetectionMethod` | cadena | Método usado para detectar malware en el correo electrónico: motor de antimalware, reputación del archivo, datos adjuntos seguros |
| `EmailAction` | cadena | Acción final tomada sobre el correo electrónico basada en el veredicto del filtro, las directivas y las acciones del usuario: mover el mensaje a la carpeta correo no deseado, agregar encabezado X, modificar el asunto, redirigir mensaje, eliminar mensaje, enviar a cuarentena, no realizar ninguna acción, enviar mensaje con CCO. |
| `EmailActionPolicy` | cadena | Directiva de acciones que entró en vigor: correo electrónico no deseado con alto nivel de confianza, correo electrónico no deseado, correo electrónico no deseado masivo, correo electrónico no deseado de suplantación de identidad, suplantación de un dominio protegido contra la suplantación de identidad, suplantación de un usuario protegido contra la suplantación de identidad, suplantación de identidad en contra de las medidas contra la suplantación de identidad, suplantación del gráfico contra la suplantación de identidad, contra el software malintencionado, datos adjuntos seguros, reglas de transporte empresarial (RTE). |
| `EmailActionPolicyGuid` | cadena | Identificador único de la directiva que determinó la acción final tomada sobre el correo electrónico. |
| `AttachmentCount` | entero | Número de datos adjuntos en el correo electrónico. |
| `UrlCount` | entero | Número de URL insertadas en el correo electrónico. |
| `EmailLanguage` | cadena | Lenguaje detectado en el contenido del correo electrónico. |
| `OrgLevelAction` | string | Acción realizada en el correo electrónico en respuesta a coincidencias con una directiva definida en el nivel organizativo |
| `OrgLevelPolicy` | string | Directiva organizativa que desencadenó la acción realizada en el correo electrónico |
| `UserLevelAction` | string | Acción realizada en el correo electrónico en respuesta a coincidencias con una directiva de buzón definida por el destinatario |
| `UserLevelPolicy` | string | Directiva de buzón de usuario final que desencadenó la acción realizada en el correo electrónico |
| `Connectors` | string | Instrucciones personalizadas que definen el flujo de correo de la organización y cómo se enrutó el correo electrónico |
| `SenderDisplayName` | string | Nombre del remitente que se muestra en la libreta de direcciones, normalmente una combinación de un nombre o un nombre, una inicial intermedia y un apellido o apellido |
| `SenderObjectId` | string |Identificador único de la cuenta del remitente en Azure AD |
| `ThreatTypes` | string | Veredicto de la pila de filtrado de correo electrónico sobre si el correo electrónico contiene malware, suplantación de identidad u otras amenazas |
| `ThreatNames` | string |Nombre de detección de malware u otras amenazas encontradas |
| `DetectionMethods` | string | Métodos usados para detectar malware, phishing u otras amenazas que se encuentran en el correo electrónico |


## <a name="related-topics"></a>Temas relacionados
- [Información general sobre la búsqueda avanzada](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades](advanced-hunting-query-emails-devices.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)
