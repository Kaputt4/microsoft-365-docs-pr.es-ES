---
title: Clasificación de alertas para la alerta de robo de cookies de sesión
description: Revise, administre y caldee la alerta de robo de cookies de sesión como True Positive (TP) o False Positive (FP), y si hay TP, tome las medidas recomendadas para corregir el ataque y mitigar los riesgos de seguridad que se generan debido a él.
keywords: incidentes, alertas, investigar, analizar, responder, correlación, ataque, máquinas, dispositivos, usuarios, identidades, identidad, buzón de correo electrónico, 365, microsoft, m365, robo de cookies, AiTM, Atacante en el medio, Adversario en el medio, robo de sesión, robo de cookies de aitm, robo de sesión de aitm.
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier2
ms.topic: how-to
ms.custom:
- autoir
- admindeeplinkDEFENDER
ms.reviewer: evaldm, isco
ms.openlocfilehash: a3fb894a2ba2ce675b904d95df45a388e4c3100e
ms.sourcegitcommit: a250d043a2e42ecbc7b86147468d1660af5a6ba7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2022
ms.locfileid: "68673403"
---
# <a name="alert-grading-for-session-cookie-theft-alert"></a>Clasificación de alertas para la alerta de robo de cookies de sesión 
 
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**
- Microsoft 365 Defender

Este artículo contiene información sobre la clasificación de alertas para las alertas de robo de cookies de sesión en Microsoft 365 Defender:

- **Se usó una cookie de sesión robada**
- **Solicitud de autenticación desde la página de suplantación de identidad relacionada con AiTM**

Los actores de amenazas han empezado a usar formas innovadoras de infiltrarse en sus entornos de destino. Inspirándose en ataques de adversario en el medio, este tipo de ataque usa phishing para robar credenciales o su sesión de inicio de sesión con el fin de llevar a cabo acciones malintencionadas. Las campañas bec son un ejemplo excelente.

Este ataque funciona mediante la configuración de un sitio intermedio (phishing), que funciona eficazmente como una conexión de proxy entre el usuario y el sitio web legítimo que el atacante está suplantando. Al actuar como intermediario (proxy), el atacante puede robar la contraseña y la cookie de sesión del destino. Por lo tanto, el atacante puede autenticarse en una sesión legítima a medida que se autentica en nombre del usuario.

Este cuaderno de estrategias ayuda a investigar los casos en los que se observa un comportamiento sospechoso que indica un tipo de ataque en el medio (AiTM) para el robo de cookies. Esto ayuda a los equipos de seguridad, como el Centro de operaciones de seguridad (SOC) y los administradores de TI, a revisar, administrar y calificar las alertas como Verdadero positivo (TP) o Falso positivo (FP) y, si es TP, realice las acciones recomendadas para corregir el ataque y mitigar los riesgos de seguridad derivados de él. 

Los resultados del uso de este cuaderno de estrategias son:

- Ha identificado las alertas asociadas a AiTM como actividades malintencionadas (TP) o benignas (FP).
- Si se identifica como malintencionado, ha tomado las medidas necesarias para corregir el ataque.

## <a name="investigating-steps"></a>Pasos de investigación

1. Investigue si el usuario afectado ha desencadenado otras alertas de seguridad. 
 
    - Céntrese en las alertas basadas en anomalías de ubicación geográfica para inicios `[AadSignInEventsBeta or IdentityLogonEvents]`de sesión .
    - Investigue los eventos de inicio de sesión pertinentes examinando la información `[AadSignInEventsBeta]`del identificador de sesión .
        - Busque eventos asociados con el identificador de sesión identificado (robado) para realizar un seguimiento de las actividades realizadas mediante la cookie `[CloudAppEvents]`robada. 
        - Busque una diferencia de tiempo entre las actividades de inicio de sesión en las que haya una diferencia en la ubicación geográfica. No deben ser posibles varias sesiones para la misma cuenta con distintas ubicaciones (lo que indica que se podría robar la sesión). 
    - Compruebe si hay alertas generadas para la cuenta desde el host corporativo. 
        - Si la cuenta está en peligro, podría haber alertas que precedieran al peligro que indica ataques, por ejemplo, alertas `[NetworkConnectionEvents]`de SmartScreen . 

2. Investigue el comportamiento sospechoso.
    - Busque eventos que indiquen patrones inusuales para identificar patrones `[CloudAppEvents]` sospechosos, como propiedades poco comunes para los usuarios, como ISP/País/Ciudad, etc.
    - Busque eventos que indiquen actividades nuevas o no vistas anteriormente, como intentos de inicio de sesión [éxito/error] en servicios nuevos o nunca usados, un aumento de la actividad de acceso al correo, un cambio en el uso de recursos de Azure, etc.
    - Inspeccione las modificaciones recientes en el entorno a partir de:
        - Office 365 aplicaciones (como cambios de permisos de Exchange Online, reenvío automático de correo o redireccionamiento)  
        - PowerApps (como configurar la transmisión automatizada de datos a través de PowerAutomate)
        - Entornos de Azure (por ejemplo, Azure Portal modificaciones de suscripción, etc.) 
        - SharePoint Online (acceso a varios sitios o a archivos que tienen contenido confidencial, como información de credenciales o estados financieros), etc.)
    - Inspeccione las operaciones observadas en varias plataformas (EXO, SPO, Azure, etc.) en un breve intervalo de tiempo para el usuario afectado.
        - Por ejemplo, las escalas de tiempo para eventos de auditoría de operaciones de lectura y envío de correo y la asignación o modificación de recursos de Azure (nuevo aprovisionamiento de máquinas o adición a AAD) no deben coincidir entre sí.
             
3. Investigue posibles ataques de seguimiento. Los ataques AiTM suelen ser un medio a un extremo y no el final, por lo que debe inspeccionar su entorno para ver otros ataques que siguen para las cuentas afectadas.
    - Un ejemplo sería examinar los casos de BEC 
        - Busque las actividades de búsqueda que se ven en el buzón `[CloudAppEvents]`de la cuenta de usuario alertada.
            - Las actividades de búsqueda en el buzón podrían tener palabras clave observadas en fraude financiero (por ejemplo, facturas, pagos, etc.), que son sospechosas. 
            - Busque también las reglas de bandeja de entrada creadas con la intención de mover y marcar como leído (algo a lo largo de las líneas de ActionType en (New-InboxRule, UpdateInboxRules, Set-InboxRule) y RawEventData has_all (MarkAsRead, MoveToFolder, Archive)).
    - Busque eventos de flujo de correo [EmailEvents & EmailUrlInfo en NetworkMessageId] donde se envían varios correos electrónicos con la misma dirección URL.  
        - Realice un seguimiento para comprobar si se observa `[CloudAppEvents]` un aumento o un gran volumen de eliminación de correo (ActivityType como papelera o eliminación) para la cuenta de buzón. 
        - El comportamiento coincidente podría considerarse altamente sospechoso. 
    - Examine los eventos de dispositivo en busca de eventos url que coincidan con eventos `[DeviceEvents on AccountName|AccountUpn]` de clic para correos electrónicos de Office365. 
        - La coincidencia de los eventos para los orígenes de clic (por ejemplo, direcciones IP diferentes para la misma dirección URL) podría ser una indicación de comportamiento malintencionado. 

## <a name="advanced-hunting-queries"></a>Consultas de búsqueda avanzadas 

[La búsqueda avanzada](advanced-hunting-overview.md) es una herramienta de búsqueda de amenazas basada en consultas que le permite inspeccionar eventos en la red y localizar indicadores de amenazas. Use estas consultas para recopilar más información relacionada con la alerta y determinar si la actividad es sospechosa.

Asegúrese de que tiene acceso a las tablas siguientes:

- AadSignInEventsBeta: contiene información de inicio de sesión para los usuarios.
- IdentityLogonEvents: contiene información de inicio de sesión para los usuarios.
- CloudAppEvents: contiene registros de auditoría de las actividades del usuario.
- EmailEvents: contiene información de flujo de correo o tráfico.
- EmailUrlInfo: contiene información de dirección URL contenida en los correos electrónicos.
- UrlClickEvents: contiene registros de clic de dirección URL para las direcciones URL en las que se ha hecho clic en los correos electrónicos.
- DeviceEvents: contiene eventos de auditoría de actividad de dispositivo.

Use la consulta siguiente para identificar el comportamiento de inicio de sesión sospechoso:

```kusto
let OfficeHomeSessionIds = 
AADSignInEventsBeta
| where Timestamp > ago(1d)
| where ErrorCode == 0
| where ApplicationId == "4765445b-32c6-49b0-83e6-1d93765276ca" //OfficeHome application 
| where ClientAppUsed == "Browser" 
| where LogonType has "interactiveUser" 
| summarize arg_min(Timestamp, Country) by SessionId;
AADSignInEventsBeta
| where Timestamp > ago(1d)
| where ApplicationId != "4765445b-32c6-49b0-83e6-1d93765276ca"
| where ClientAppUsed == "Browser" 
| project OtherTimestamp = Timestamp, Application, ApplicationId, AccountObjectId, AccountDisplayName, OtherCountry = Country, SessionId
| join OfficeHomeSessionIds on SessionId
| where OtherTimestamp > Timestamp and OtherCountry != Country
```
Use la consulta siguiente para identificar países poco comunes: 

```kusto
AADSignInEventsBeta 
| where Timestamp > ago(7d) 
| where ApplicationId == "4765445b-32c6-49b0-83e6-1d93765276ca" //OfficeHome application 
| where ClientAppUsed == "Browser" 
| where LogonType has "interactiveUser" 
| summarize Countries = make_set(Country) by AccountObjectId, AccountDisplayName
```
Use esta consulta para buscar nuevas reglas de bandeja de entrada de correo electrónico creadas durante una sesión de inicio de sesión sospechosa: 

```kusto
//Find suspicious tokens tagged by AAD "Anomalous Token" alert
let suspiciousSessionIds = materialize(
AlertInfo
| where Timestamp > ago(7d)
| where Title == "Anomalous Token"
| join (AlertEvidence | where Timestamp > ago(7d) | where EntityType == "CloudLogonSession") on AlertId
| project sessionId = todynamic(AdditionalFields).SessionId);
//Find Inbox rules created during a session that used the anomalous token
let hasSuspiciousSessionIds = isnotempty(toscalar(suspiciousSessionIds));
CloudAppEvents
| where hasSuspiciousSessionIds
| where Timestamp > ago(21d)
| where ActionType == "New-InboxRule"
| where RawEventData.SessionId in (suspiciousSessionIds)
```

## <a name="recommended-actions"></a>Acciones recomendadas 

Una vez que determine que las actividades de alerta son malintencionadas, clasifique esas alertas como Verdadero positivo (TP) y realice las siguientes acciones:

- Restablezca las credenciales de la cuenta del usuario. Además, deshabilite o revoque tokens para la cuenta en peligro.
- Si los artefactos que se encontraron estaban relacionados con el correo electrónico, configure el bloque en función de la dirección IP del remitente y los dominios de remitente.
    - Los dominios que están en cuclillas tipográficas pueden borrar las directivas DMARC, DKIM y SPF (ya que el dominio es diferente por completo) o pueden devolver resultados "null" (ya que probablemente no esté configurado por el actor de amenazas).
- Bloquear direcciones URL o direcciones IP (en las plataformas de protección de red) que se identificaron como malintencionadas durante la investigación.  

## <a name="see-also"></a>Vea también

[Del robo de cookies a BEC](https://www.microsoft.com/security/blog/2022/07/12/from-cookie-theft-to-bec-attackers-use-aitm-phishing-sites-as-entry-point-to-further-financial-fraud/)

   
