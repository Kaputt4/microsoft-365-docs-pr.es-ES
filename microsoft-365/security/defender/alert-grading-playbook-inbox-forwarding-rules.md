---
title: Clasificación de alertas para reglas de reenvío de bandeja de entrada sospechosas
description: Clasificación de alertas para reglas de reenvío de bandeja de entrada sospechosas para revisar las alertas y realizar las acciones recomendadas para corregir el ataque y proteger la red.
keywords: incidentes, alertas, investigar, analizar, respuesta, correlación, ataque, máquinas, dispositivos, usuarios, identidades, identidad, buzón de correo electrónico, 365, microsoft, m365
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
- M365-security-compliance
- m365initiative-m365-defender
ms.custom: admindeeplinkDEFENDER
ms.topic: conceptual
search.appverid:
- MOE150
- met150
ms.openlocfilehash: 9d02727df9684e8c3da9f5abf003ef9a4c7012b6
ms.sourcegitcommit: b1ed6470645455c2f1fcf467450debc622c40147
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2022
ms.locfileid: "67711013"
---
# <a name="alert-grading-for-suspicious-inbox-forwarding-rules"></a>Clasificación de alertas para reglas de reenvío de bandeja de entrada sospechosas

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**
- Microsoft 365 Defender

Los actores de amenazas pueden usar cuentas de usuario en peligro para varios propósitos malintencionados, como leer correos electrónicos en la bandeja de entrada de un usuario, crear reglas de bandeja de entrada para reenviar correos electrónicos a cuentas externas, enviar correos electrónicos de phishing, entre otros. Las reglas de bandeja de entrada malintencionadas son muy comunes durante las campañas de suplantación de identidad (BEC) y de correo electrónico empresarial, y es importante supervisarlas de forma coherente.

Este cuaderno de estrategias le ayuda a investigar las alertas de reglas de reenvío de bandeja de entrada sospechosas y clasificarlas rápidamente como un verdadero positivo (TP) o un falso positivo (TP). A continuación, puede realizar las acciones recomendadas para que las alertas de TP corrijan el ataque.

Para obtener información general sobre la clasificación de alertas para Microsoft Defender para Office 365 y Microsoft Defender for Cloud Apps, consulte el [artículo de introducción](alert-grading-playbooks.md).

Los resultados del uso de este cuaderno de estrategias son:

- Ha identificado las alertas asociadas con las reglas de reenvío de bandeja de entrada como actividades malintencionadas (TP) o benignas (FP).

  Si es malintencionado, ha quitado reglas de reenvío de bandeja de entrada malintencionadas.

- Ha realizado la acción necesaria si los correos electrónicos se han reenviado a una dirección de correo electrónico malintencionada.

## <a name="inbox-forwarding-rules"></a>Reglas de reenvío de bandeja de entrada

Las reglas de bandeja de entrada se configuran para administrar automáticamente los mensajes de correo electrónico en función de criterios predefinidos. Por ejemplo, puede crear una regla de bandeja de entrada para mover todos los mensajes del administrador a otra carpeta o reenviar los mensajes que reciba a otra dirección de correo electrónico.

### <a name="suspicious-inbox-forwarding-rules"></a>Reglas del reenvío sospechoso desde la bandeja de entrada

Después de obtener acceso a los buzones de los usuarios, los atacantes suelen crear una regla de bandeja de entrada que les permite filtrar datos confidenciales a una dirección de correo electrónico externa y usarla con fines malintencionados.

Las reglas de bandeja de entrada malintencionadas automatizan el proceso de filtración. Con reglas específicas, cada correo electrónico de la bandeja de entrada del usuario de destino que coincida con los criterios de regla se reenviará al buzón del atacante. Por ejemplo, es posible que un atacante quiera recopilar datos confidenciales relacionados con finanzas. Crean una regla de bandeja de entrada para reenviar todos los correos electrónicos que contienen palabras clave, como "finance" y "invoice" en el asunto o el cuerpo del mensaje, a su buzón.

Las reglas de reenvío de bandeja de entrada sospechosas pueden ser muy difíciles de detectar porque el mantenimiento de las reglas de bandeja de entrada es una tarea común que realizan los usuarios. Por lo tanto, es importante supervisar las alertas.

## <a name="workflow"></a>Flujo de trabajo

Este es el flujo de trabajo para identificar reglas de reenvío de correo electrónico sospechosas.

:::image type="content" source="../../media/alert-grading-playbook-inbox-forwarding-rules/alert-grading-playbook-inbox-forwarding-rules-workflow.png" alt-text="Flujo de trabajo de investigación de alertas para reglas de reenvío de bandeja de entrada" lightbox="../../media/alert-grading-playbook-inbox-forwarding-rules/alert-grading-playbook-inbox-forwarding-rules-workflow.png":::

## <a name="investigation-steps"></a>Pasos de investigación

Esta sección contiene instrucciones detalladas paso a paso para responder al incidente y seguir los pasos recomendados para proteger su organización de ataques adicionales.

### <a name="review-generated-alerts"></a>Revisión de las alertas generadas

Este es un ejemplo de una alerta de regla de reenvío de bandeja de entrada en la cola de alertas.

:::image type="content" source="../../media/alert-grading-playbook-inbox-forwarding-rules/alert-grading-playbook-inbox-forwarding-rules-alert-queue.png" alt-text="Ejemplo de una notificación en la cola de alertas" lightbox="../../media/alert-grading-playbook-inbox-forwarding-rules/alert-grading-playbook-inbox-forwarding-rules-alert-queue.png":::

Este es un ejemplo de los detalles de la alerta desencadenada por una regla de reenvío de bandeja de entrada malintencionada.

:::image type="content" source="../../media/alert-grading-playbook-inbox-forwarding-rules/alert-grading-playbook-inbox-forwarding-rules-alert-description.png" alt-text="Detalles de la alerta desencadenada por una regla de reenvío de bandeja de entrada malintencionada" lightbox="../../media/alert-grading-playbook-inbox-forwarding-rules/alert-grading-playbook-inbox-forwarding-rules-alert-description.png":::

### <a name="investigate-rule-parameters"></a>Investigación de parámetros de regla

El propósito de esta fase es determinar si las reglas parecen sospechosas según determinados criterios:

Destinatarios de la regla de reenvío:

- Validar la dirección de correo electrónico de destino no es un buzón adicional propiedad del mismo usuario (evitando casos en los que el usuario reenvíe correos electrónicos de forma automática entre buzones personales).
- Valide que la dirección de correo electrónico de destino no es una dirección interna o un subdominio que pertenezcan a la empresa.

Filtros:

- Si la regla de bandeja de entrada contiene filtros que buscan palabras clave específicas en el asunto o cuerpo del correo electrónico, compruebe si las palabras clave proporcionadas, como finanzas, credenciales y redes, entre otras, parecen estar relacionadas con actividades malintencionadas. Puede encontrar estos filtros en los siguientes atributos (que se muestran en la columna RawEventData del evento): "BodyContainsWords", "SubjectContainsWords" o "SubjectOrBodyContainsWords"
- Si el atacante decide no establecer ningún filtro en los correos y, en su lugar, la regla de bandeja de entrada reenvía todos los elementos de buzón al buzón del atacante), este comportamiento también es sospechoso.

### <a name="investigate-ip-address"></a>Investigación de la dirección IP

Revise los atributos relacionados con la dirección IP que realizó el evento pertinente de creación de la regla:

1. Busque otras actividades sospechosas en la nube que se originaron desde la misma dirección IP en el inquilino. Por ejemplo, la actividad sospechosa podría ser varios intentos de inicio de sesión erróneos.
2. ¿Es el ISP común y razonable para este usuario?
3. ¿La ubicación es común y razonable para este usuario?

### <a name="investigate-any-suspicious-activity-with-the-user-inbox-before-creating-rules"></a>Investigar cualquier actividad sospechosa con la bandeja de entrada del usuario antes de crear reglas

Puede revisar todas las actividades del usuario antes de crear reglas, buscar indicadores de peligro e investigar las acciones de usuario que parezcan sospechosas. Por ejemplo, varios inicios de sesión con errores.

- Inicios de sesión:

  Compruebe que la actividad de inicio de sesión antes del evento de creación de reglas no es sospechosa (como la ubicación común, ISP o user-agent).

- Otras alertas o incidentes
  - Se desencadenaron otras alertas para el usuario antes de la creación de la regla. Si es así, esto podría indicar que el usuario se puso en peligro.
  - Si la alerta se correlaciona con otras alertas para indicar un incidente, ¿contiene el incidente otras alertas positivas verdaderas?

## <a name="advanced-hunting-queries"></a>Consultas de búsqueda avanzadas

[Búsqueda avanzada](advanced-hunting-overview.md) es una herramienta de búsqueda de amenazas basada en consultas que le permite inspeccionar eventos en la red y localizar indicadores de amenazas.

Ejecute esta consulta para buscar todos los nuevos eventos de regla de bandeja de entrada durante un período de tiempo específico.

```kusto
let start_date = now(-10h);
let end_date = now();
let user_id = ""; // enter here the user id
CloudAppEvents
| where Timestamp between (start_date .. end_date)
| where AccountObjectId == user_id
| where Application == @"Microsoft Exchange Online"
| where ActionType in ("Set-Mailbox", "New-InboxRule", "Set-InboxRule") //set new inbox rule related operations
| project Timestamp, ActionType, CountryCode, City, ISP, IPAddress, RuleConfig = RawEventData.Parameters, RawEventData
```

*RuleConfig* contendrá la configuración de la regla.

Ejecute esta consulta para comprobar si el ISP es común para el usuario examinando el historial del usuario.

```kusto
let alert_date = now(); //enter alert date
let timeback = 30d;
let userid = ""; //enter here user id
CloudAppEvents
| where Timestamp between ((alert_date-timeback)..(alert_date-1h))
| where AccountObjectId == userid
| make-series ActivityCount = count() default = 0 on Timestamp  from (alert_date-timeback) to (alert_date-1h) step 12h by ISP
```

Ejecute esta consulta para comprobar si el país es común para el usuario examinando el historial del usuario.

```kusto
let alert_date = now(); //enter alert date
let timeback = 30d;
let userid = ""; //enter here user id
CloudAppEvents
| where Timestamp between ((alert_date-timeback)..(alert_date-1h))
| where AccountObjectId == userid
| make-series ActivityCount = count() default = 0 on Timestamp  from (alert_date-timeback) to (alert_date-1h) step 12h by CountryCode
```

Ejecute esta consulta para comprobar si el agente de usuario es común para el usuario examinando el historial del usuario.

```kusto
let alert_date = now(); //enter alert date
let timeback = 30d;
let userid = ""; //enter here user id
CloudAppEvents
| where Timestamp between ((alert_date-timeback)..(alert_date-1h))
| where AccountObjectId == userid
| make-series ActivityCount = count() default = 0 on Timestamp  from (alert_date-timeback) to (alert_date-1h) step 12h by UserAgent
```

Ejecute esta consulta para comprobar si otros usuarios crearon una regla de reenvío al mismo destino (podría indicar que otros usuarios también están en peligro).

```kusto
let start_date = now(-10h);
let end_date = now();
let dest_email = ""; // enter here destination email as seen in the alert
CloudAppEvents
| where Timestamp between (start_date .. end_date)
| where ActionType in ("Set-Mailbox", "New-InboxRule", "Set-InboxRule") //set new inbox rule related operations
| project Timestamp, ActionType, CountryCode, City, ISP, IPAddress, RuleConfig = RawEventData.Parameters, RawEventData
| where RuleConfig has dest_email
```

## <a name="recommended-actions"></a>Acciones recomendadas

1. Deshabilite la regla de bandeja de entrada malintencionada.
2. Restablezca las credenciales de la cuenta del usuario. También puede comprobar si la cuenta de usuario se ha puesto en peligro con Microsoft Defender for Cloud Apps, que obtiene señales de seguridad de Azure Active Directory (Azure AD) Identity Protection.
3. Busque otras actividades malintencionadas realizadas por el usuario afectado.
4. Compruebe si hay otra actividad sospechosa en el inquilino originada desde la misma dirección IP o desde el mismo ISP (si el ISP es poco frecuente) para encontrar otros usuarios en peligro.

## <a name="see-also"></a>Vea también

- [Introducción a la clasificación de alertas](alert-grading-playbooks.md)
- [Actividad de reenvío de correo electrónico sospechoso](alert-grading-playbook-email-forwarding.md)
- [Reglas sospechosas de manipulación de la bandeja de entrada](alert-grading-playbook-inbox-manipulation-rules.md)
- [Investigar alertas](investigate-alerts.md)
