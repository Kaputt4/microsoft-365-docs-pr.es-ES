---
title: Clasificación de alertas para reglas sospechosas de manipulación de bandeja de entrada
description: Clasificación de alertas para reglas sospechosas de manipulación de bandeja de entrada para revisar las alertas y realizar las acciones recomendadas para corregir el ataque y proteger la red.
keywords: incidentes, alertas, investigar, analizar, respuesta, correlación, ataque, máquinas, dispositivos, usuarios, identidades, identidad, buzón de correo electrónico, 365, microsoft, m365
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: e663d02037633599b9dffc19e1ebbd174aa279e1
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/06/2022
ms.locfileid: "64663190"
---
# <a name="alert-grading-for-suspicious-inbox-manipulation-rules"></a>Clasificación de alertas para reglas sospechosas de manipulación de bandeja de entrada

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**
- Microsoft 365 Defender

Los actores de amenazas pueden usar cuentas de usuario en peligro para muchos propósitos malintencionados, como leer correos electrónicos en la bandeja de entrada de un usuario, crear reglas de bandeja de entrada para reenviar correos electrónicos a cuentas externas, eliminar seguimientos y enviar correos de phishing. Las reglas de bandeja de entrada malintencionadas son comunes durante las campañas de suplantación de identidad (BEC) y de correo electrónico empresarial y es importante supervisarlas de forma coherente.

Este cuaderno de estrategias le ayuda a investigar cualquier incidente relacionado con reglas sospechosas de manipulación de bandeja de entrada configuradas por los atacantes y a realizar las acciones recomendadas para corregir el ataque y proteger la red. Este cuaderno de estrategias está destinado a los equipos de seguridad, incluidos los analistas del Centro de operaciones de seguridad (SOC) y los administradores de TI que revisan, investigan y califican las alertas. Puede calificar rápidamente las alertas como verdaderos positivos (TP) o falsos positivos (TP) y realizar las acciones recomendadas para que las alertas de TP corrijan el ataque.

Los resultados del uso de este cuaderno de estrategias son:

- Ha identificado las alertas asociadas con las reglas de manipulación de bandeja de entrada como actividades malintencionadas (TP) o benignas (FP).

  Si es malintencionado, ha quitado reglas de manipulación de bandeja de entrada malintencionadas.

- Ha realizado la acción necesaria si los correos electrónicos se han reenviado a una dirección de correo electrónico malintencionada.

## <a name="inbox-manipulation-rules"></a>Reglas de manipulación de bandeja de entrada

Las reglas de bandeja de entrada se establecen para administrar automáticamente los mensajes de correo electrónico en función de criterios predefinidos. Por ejemplo, puede crear una regla de bandeja de entrada para mover todos los mensajes del administrador a otra carpeta o reenviar los mensajes que reciba a otra dirección de correo electrónico.

### <a name="malicious-inbox-manipulation-rules"></a>Reglas de manipulación de bandeja de entrada malintencionadas

Los atacantes pueden configurar reglas de correo electrónico para ocultar los correos electrónicos entrantes en el buzón de usuario en peligro para ocultar sus actividades malintencionadas al usuario. También pueden establecer reglas en el buzón de usuario en peligro para eliminar correos electrónicos, mover los correos electrónicos a otra carpeta menos notable (como RSS) o reenviar los correos a una cuenta externa. Algunas reglas pueden mover todos los correos electrónicos a otra carpeta y marcarlos como "leídos", mientras que algunas reglas solo pueden mover correos que contienen palabras clave específicas en el mensaje de correo electrónico o asunto.

Por ejemplo, la regla de bandeja de entrada podría establecerse para buscar palabras clave como "factura", "phish", "no responder", "correo electrónico sospechoso" o "spam" entre otros, y moverlas a una cuenta de correo electrónico externa. Los atacantes también pueden usar el buzón de usuario en peligro para distribuir correo no deseado, correos electrónicos de suplantación de identidad (phishing) o malware.

## <a name="workflow"></a>Flujo de trabajo

Este es el flujo de trabajo para identificar actividades sospechosas de regla de manipulación de bandeja de entrada.

:::image type="content" source="../../media/alert-grading-playbook-inbox-manipulation-rules/alert-grading-playbook-inbox-manipulation-rules-workflow.png" alt-text="Flujo de trabajo de investigación de alertas para reglas de manipulación de bandeja de entrada" lightbox="../../media/alert-grading-playbook-inbox-manipulation-rules/alert-grading-playbook-inbox-manipulation-rules-workflow.png":::

## <a name="investigation-steps"></a>Pasos de investigación

Esta sección contiene instrucciones detalladas paso a paso para responder al incidente y seguir los pasos recomendados para proteger su organización de ataques adicionales.

### <a name="1-review-the-alerts"></a>1. Revisar las alertas

Este es un ejemplo de una alerta de regla de manipulación de bandeja de entrada en la cola de alertas.

:::image type="content" source="../../media/alert-grading-playbook-inbox-manipulation-rules/alert-grading-playbook-inbox-manipulation-rules-alert-queue.png" alt-text="Ejemplo de una regla de manipulación de bandeja de entrada" lightbox="../../media/alert-grading-playbook-inbox-manipulation-rules/alert-grading-playbook-inbox-manipulation-rules-alert-queue.png":::

Este es un ejemplo de los detalles de una alerta desencadenada por una regla de manipulación de bandeja de entrada malintencionada.

:::image type="content" source="../../media/alert-grading-playbook-inbox-manipulation-rules/alert-grading-playbook-inbox-manipulation-rules-alert-description.png" alt-text="Detalles de la alerta desencadenada por una regla de manipulación de bandeja de entrada malintencionada" lightbox="../../media/alert-grading-playbook-inbox-manipulation-rules/alert-grading-playbook-inbox-manipulation-rules-alert-description.png":::

### <a name="2-investigate-inbox-manipulation-rule-parameters"></a>2. Investigar parámetros de regla de manipulación de bandeja de entrada

Determine si las reglas parecen sospechosas según los siguientes parámetros o criterios de regla:

- Palabras clave

   El atacante podría aplicar la regla de manipulación solo a los correos electrónicos que contengan ciertas palabras. Puede encontrar estas palabras clave en determinados atributos como: "BodyContainsWords", "SubjectContainsWords" o "SubjectOrBodyContainsWords".

   Si hay filtrado por palabras clave, compruebe si las palabras clave parecen sospechosas (los escenarios comunes son filtrar los correos electrónicos relacionados con las actividades del atacante, como "phish", "spam", "no responder", entre otros).

   Si no hay ningún filtro, también podría ser sospechoso.

- Carpeta de destino

   Para evitar la detección de seguridad, el atacante podría mover los correos electrónicos a una carpeta menos notable y marcar los correos electrónicos como leídos (por ejemplo, la carpeta "RSS"). Si el atacante aplica la acción "MoveToFolder" y "MarkAsRead", compruebe si la carpeta de destino está relacionada de alguna manera con las palabras clave de la regla para decidir si parece sospechosa o no.

- Eliminar todo

   Algunos atacantes simplemente eliminarán todos los correos electrónicos entrantes para ocultar su actividad. Principalmente, una regla de "eliminar todos los correos electrónicos entrantes" sin filtrarlos con palabras clave es un indicador de actividad malintencionada.

Este es un ejemplo de una configuración de regla "eliminar todos los correos electrónicos entrantes" (como se ve en RawEventData.Parameters) del registro de eventos pertinente.

:::image type="content" source="../../media/alert-grading-playbook-inbox-manipulation-rules/alert-grading-playbook-inbox-manipulation-rules-delete-log.png" alt-text="Ejemplo de una configuración de regla de eliminación de todos los correos electrónicos entrantes" lightbox="../../media/alert-grading-playbook-inbox-manipulation-rules/alert-grading-playbook-inbox-manipulation-rules-delete-log.png":::

### <a name="3-investigate-the-ip-address"></a>3. Investigar la dirección IP

Revise los atributos de la dirección IP que realizó el evento pertinente de creación de la regla:

- Busque otras actividades sospechosas en la nube que se originaron desde la misma dirección IP en el inquilino. Por ejemplo, la actividad sospechosa podría ser varios intentos de inicio de sesión erróneos.
- ¿Es el ISP común y razonable para este usuario?
- ¿La ubicación es común y razonable para este usuario?

### <a name="4-investigate-suspicious-activity-by-the-user-prior-to-creating-the-rules"></a>4. Investigar la actividad sospechosa por parte del usuario antes de crear las reglas

Puede revisar todas las actividades del usuario antes de crear reglas, comprobar si hay indicadores de riesgo e investigar las acciones de usuario que parecen sospechosas.

Por ejemplo, para varios inicios de sesión con errores, examine:

- Actividad de inicio de sesión

   Compruebe que la actividad de inicio de sesión antes de la creación de la regla no es sospechosa. (ubicación común / ISP / user-agent).

- Alertas

   Compruebe si el usuario recibió alertas antes de crear las reglas. Esto podría indicar que la cuenta de usuario podría estar en peligro. Por ejemplo, alerta de viaje imposible, país poco frecuente, varios inicios de sesión con errores, entre otros).

- Incidente

   Compruebe si la alerta está asociada a otras alertas que indican un incidente. Si es así, compruebe si el incidente contiene otras alertas positivas verdaderas.

## <a name="advanced-hunting-queries"></a>Consultas de búsqueda avanzadas

[Búsqueda avanzada](advanced-hunting-overview.md) es una herramienta de búsqueda de amenazas basada en consultas que le permite inspeccionar eventos en la red para localizar indicadores de amenazas.

Use esta consulta para buscar todos los nuevos eventos de regla de bandeja de entrada durante un período de tiempo específico.

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

La columna *RuleConfig* proporcionará la nueva configuración de regla de bandeja de entrada.

Use esta consulta para comprobar si el ISP es común para el usuario examinando el historial del usuario.

```kusto
let alert_date = now(); //enter alert date
let timeback = 60d;
let userid = ""; //enter here user id
CloudAppEvents
| where Timestamp between ((alert_date-timeback)..(alert_date-1h))
| where AccountObjectId == userid
| make-series ActivityCount = count() default = 0 on Timestamp  from (alert_date-timeback) to (alert_date-1h) step 12h by ISP
```

Use esta consulta para comprobar si el país es común para el usuario examinando el historial del usuario.

```kusto
let alert_date = now(); //enter alert date
let timeback = 60d;
let userid = ""; //enter here user id
CloudAppEvents
| where Timestamp between ((alert_date-timeback)..(alert_date-1h))
| where AccountObjectId == userid
| make-series ActivityCount = count() default = 0 on Timestamp  from (alert_date-timeback) to (alert_date-1h) step 12h by CountryCode
```

Use esta consulta para comprobar si el agente de usuario es común para el usuario examinando el historial del usuario.

```kusto
let alert_date = now(); //enter alert date
let timeback = 60d;
let userid = ""; //enter here user id
CloudAppEvents
| where Timestamp between ((alert_date-timeback)..(alert_date-1h))
| where AccountObjectId == userid
| make-series ActivityCount = count() default = 0 on Timestamp  from (alert_date-timeback) to (alert_date-1h) step 12h by UserAgent
```

## <a name="recommended-actions"></a>Acciones recomendadas

1. Deshabilite la regla de bandeja de entrada malintencionada.
2. Restablezca las credenciales de la cuenta de usuario. También puede comprobar si la cuenta de usuario se ha visto comprometida con Microsoft Defender for Cloud Apps, que obtiene señales de seguridad de Azure Active Directory (Azure AD) Identity Protection.
3. Busque otras actividades malintencionadas realizadas por la cuenta de usuario afectada.
4. Compruebe si hay otra actividad sospechosa en el inquilino que se originó desde la misma dirección IP o desde el mismo ISP (si el ISP es poco frecuente) para encontrar otras cuentas de usuario en peligro.

## <a name="see-also"></a>Vea también

- [Introducción a la clasificación de alertas](alert-grading-playbooks.md)
- [Actividad de reenvío de correo electrónico sospechoso](alert-grading-playbook-email-forwarding.md)
- [Reglas del reenvío sospechoso desde la bandeja de entrada](alert-grading-playbook-inbox-forwarding-rules.md)
- [Investigar alertas](investigate-alerts.md)
