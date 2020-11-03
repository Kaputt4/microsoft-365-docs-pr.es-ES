---
title: La tabla EmailEvents en el esquema de búsqueda avanzada
description: Obtenga información sobre los eventos asociados a los correos electrónicos de Microsoft 365 en la tabla EmailEvents del esquema de búsqueda avanzada.
keywords: caza avanzado, caza de amenazas, búsqueda de amenazas en el ciberespacio, protección contra amenazas de Microsoft, Microsoft 365, MTP, M365, búsqueda, consulta, telemetría, referencia de esquema, kusto, tabla, columna, tipo de datos, descripción, EmailEvents, identificador de mensaje de red, remitente, destinatario, identificador de datos adjuntos, nombre de datos adjuntos, veredicto
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
ms.openlocfilehash: 86cc32cf395f2216eb3e167e372d1225734c4c28
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "48842637"
---
# <a name="emailevents"></a>EmailEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 defender



La `EmailEvents` tabla del esquema de [búsqueda avanzada](advanced-hunting-overview.md) contiene información sobre los eventos que implican el procesamiento de mensajes de correo electrónico en Microsoft Defender para Office 365. Use esta referencia para crear consultas que devuelvan información de esta tabla.

>[!TIP]
> Para obtener información detallada acerca de los tipos de eventos ( `ActionType` valores) admitidos por una tabla, use la [referencia de esquema integrada](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) disponible en el centro de seguridad.

Para obtener información sobre otras tablas del esquema de búsqueda avanzada, [vea la referencia de búsqueda avanzada](advanced-hunting-schema-tables.md).

| Nombre de columna | Tipo de datos | Descripción |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Fecha y hora en que se registró el evento. |
| `EmailId` | cadena | Identificador único del destinatario y correo electrónico. |
| `NetworkMessageId` | cadena | Identificador único del correo electrónico generado por Microsoft 365 |
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
| `PhishDetectionMethod` | cadena | Método que se usa para detectar el correo electrónico como phish: reputación de dirección URL malintencionada, detonación de dirección URL de vínculos seguros, filtro de phish avanzado, filtro de phish general, anti-falseamiento: intra-org, anti-spoofing: dominio externo, suplantación de dominio, suplantación de usuarios, suplantación de marca |
| `MalwareFilterVerdict` | cadena | Veredicto sobre la pila de mensajes de correo electrónico filtrados para determinar si los correos contienen código malintencionado: Malware, no malware |
| `MalwareDetectionMethod` | cadena | Método usado para detectar malware en el correo electrónico: motor antimalware, reputación de archivos, datos adjuntos seguros |
| `FinalEmailAction` | cadena | Acción final tomada sobre el correo electrónico basada en el veredicto del filtro, las directivas y las acciones del usuario: mover el mensaje a la carpeta correo no deseado, agregar encabezado X, modificar el asunto, redirigir mensaje, eliminar mensaje, enviar a cuarentena, no realizar ninguna acción, enviar mensaje con CCO. |
| `FinalEmailActionPolicy` | cadena | Directiva de acciones que entró en vigor: correo electrónico no deseado con alto nivel de confianza, correo electrónico no deseado, correo electrónico no deseado masivo, correo electrónico no deseado de suplantación de identidad, suplantación de un dominio protegido contra la suplantación de identidad, suplantación de un usuario protegido contra la suplantación de identidad, suplantación de identidad en contra de las medidas contra la suplantación de identidad, suplantación del gráfico contra la suplantación de identidad, contra el software malintencionado, datos adjuntos seguros, reglas de transporte empresarial (RTE). |
| `FinalEmailActionPolicyGuid` | cadena | Identificador único de la directiva que determinó la acción final tomada sobre el correo electrónico. |
| `AttachmentCount` | entero | Número de datos adjuntos en el correo electrónico. |
| `UrlCount` | entero | Número de URL insertadas en el correo electrónico. |
| `EmailLanguage` | cadena | Lenguaje detectado en el contenido del correo electrónico. |

## <a name="related-topics"></a>Temas relacionados
- [Información general sobre la búsqueda avanzada](advanced-hunting-overview.md)
- [Aprender el lenguaje de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartidas](advanced-hunting-shared-queries.md)
- [Buscar entre dispositivos, correos electrónicos, aplicaciones e identidades](advanced-hunting-query-emails-devices.md)
- [Entender el esquema](advanced-hunting-schema-tables.md)
- [Aplicar procedimientos recomendados de consulta](advanced-hunting-best-practices.md)
