---
title: Clasificación de alertas para reglas de manipulación de bandeja de entrada sospechosas
description: Clasificación de alertas para reglas de manipulación de la bandeja de entrada sospechosas para revisar las alertas y realizar acciones recomendadas para corregir el ataque y proteger la red.
keywords: incidentes, alertas, investigar, analizar, responder, correlación, ataque, máquinas, dispositivos, usuarios, identidades, identidad, buzón, correo electrónico, 365, microsoft, m365
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
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
ms.openlocfilehash: 102731beb6da535e91ad197379a08d4d0f7cddfe
ms.sourcegitcommit: e3bff611439354e6339bb666a88682078f32ec13
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2022
ms.locfileid: "62355255"
---
# <a name="alert-grading-for-suspicious-inbox-manipulation-rules"></a>Clasificación de alertas para reglas de manipulación de bandeja de entrada sospechosas

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**
- Microsoft 365 Defender

Los actores de amenazas pueden usar cuentas de usuario comprometidas para muchos fines malintencionados, como leer correos electrónicos en la bandeja de entrada de un usuario, crear reglas de bandeja de entrada para reenviar correos electrónicos a cuentas externas, eliminar seguimientos y enviar correos de suplantación de identidad. Las reglas de la bandeja de entrada malintencionadas son comunes durante las campañas de suplantación de identidad (BEC) y de correo electrónico empresarial y es importante supervisarlas de forma coherente. 

Este libro de juegos te ayuda a investigar cualquier incidente relacionado con las reglas de manipulación de la bandeja de entrada sospechosas configuradas por los atacantes y a realizar las acciones recomendadas para corregir el ataque y proteger la red. Este libro de juegos está para los equipos de seguridad, incluidos los analistas del Centro de operaciones de seguridad (SOC) y los administradores de TI que revisan, investigan y califican las alertas. Puedes calificar rápidamente las alertas como verdadero positivo (TP) o falso positivo (TP) y realizar acciones recomendadas para que las alertas de TP corrija el ataque. 

Los resultados del uso de este libro de juegos son:

- Ha identificado las alertas asociadas con las reglas de manipulación de la bandeja de entrada como actividades malintencionadas (TP) o benignas (FP).

  Si es malintencionado, ha quitado las reglas de manipulación de la bandeja de entrada malintencionada.

- Ha realizado la acción necesaria si los correos electrónicos se han reenviado a una dirección de correo electrónico malintencionada.

## <a name="inbox-manipulation-rules"></a>Reglas de manipulación de la Bandeja de entrada

Las reglas de la Bandeja de entrada se establecen para administrar automáticamente los mensajes de correo electrónico en función de criterios predefinidos. Por ejemplo, puede crear una regla de bandeja de entrada para mover todos los mensajes del administrador a otra carpeta o reenviar los mensajes que reciba a otra dirección de correo electrónico.

### <a name="malicious-inbox-manipulation-rules"></a>Reglas de manipulación de bandeja de entrada malintencionadas

Los atacantes pueden configurar reglas de correo electrónico para ocultar los correos electrónicos entrantes en el buzón de usuario comprometido para ocultar sus actividades malintencionadas del usuario. También pueden establecer reglas en el buzón de usuario comprometido para eliminar correos electrónicos, mover los correos electrónicos a otra carpeta menos perceptible (como RSS) o reenviar correos a una cuenta externa. Algunas reglas pueden mover todos los correos electrónicos a otra carpeta y marcarlos como "leídos", mientras que algunas reglas pueden mover solo los correos que contienen palabras clave específicas en el asunto o mensaje de correo electrónico. 

Por ejemplo, la regla de bandeja de entrada puede establecerse para buscar palabras clave como "factura", "phish", "no responder", "correo electrónico sospechoso" o "correo no deseado", entre otras, y moverlas a una cuenta de correo electrónico externa. Los atacantes también pueden usar el buzón de usuario en peligro para distribuir correo no deseado, correos electrónicos de suplantación de identidad o malware. 

## <a name="workflow"></a>Flujo de trabajo

Este es el flujo de trabajo para identificar actividades sospechosas de reglas de manipulación de la bandeja de entrada.

:::image type="content" source="../../media/alert-grading-playbook-inbox-manipulation-rules/alert-grading-playbook-inbox-manipulation-rules-workflow.png" alt-text="Flujo de trabajo de investigación de alertas para reglas de manipulación de bandeja de entrada" lightbox="../../media/alert-grading-playbook-inbox-manipulation-rules/alert-grading-playbook-inbox-manipulation-rules-workflow.png":::


## <a name="investigation-steps"></a>Pasos de investigación

Esta sección contiene instrucciones detalladas paso a paso para responder al incidente y seguir los pasos recomendados para proteger su organización de nuevos ataques.

### <a name="1-review-the-alerts"></a>1. Revisar las alertas

Este es un ejemplo de una alerta de regla de manipulación de bandeja de entrada en la cola de alertas.

:::image type="content" source="../../media/alert-grading-playbook-inbox-manipulation-rules/alert-grading-playbook-inbox-manipulation-rules-alert-queue.png" alt-text="Ejemplo de una regla de manipulación de la bandeja de entrada" lightbox="../../media/alert-grading-playbook-inbox-manipulation-rules/alert-grading-playbook-inbox-manipulation-rules-alert-queue.png":::

Este es un ejemplo de los detalles de una alerta desencadenada por una regla de manipulación malintencionada de la bandeja de entrada.

:::image type="content" source="../../media/alert-grading-playbook-inbox-manipulation-rules/alert-grading-playbook-inbox-manipulation-rules-alert-description.png" alt-text="Detalles de la alerta desencadenada por una regla de manipulación malintencionada de la bandeja de entrada" lightbox="../../media/alert-grading-playbook-inbox-manipulation-rules/alert-grading-playbook-inbox-manipulation-rules-alert-description.png":::


### <a name="2-investigate-inbox-manipulation-rule-parameters"></a>2. Investigar parámetros de regla de manipulación de la bandeja de entrada 

Determine si las reglas son sospechosas de acuerdo con los siguientes parámetros o criterios de regla:

- Palabras clave

   El atacante puede aplicar la regla de manipulación solo a los correos electrónicos que contengan determinadas palabras. Puede encontrar estas palabras clave en determinados atributos como: "BodyContainsWords", "SubjectContainsWords" o "SubjectOrBodyContainsWords". 

   Si hay filtrado por palabras clave, compruebe si las palabras clave le parecen sospechosas (los escenarios comunes son filtrar correos electrónicos relacionados con las actividades del atacante, como "phish", "spam", "no responder", entre otros).

   Si no hay ningún filtro, también puede ser sospechoso.

- Carpeta de destino

   Para eludir la detección de seguridad, el atacante puede mover los correos electrónicos a una carpeta menos perceptible y marcar los correos electrónicos como leídos (por ejemplo, la carpeta "RSS"). Si el atacante aplica la acción "MoveToFolder" y "MarkAsRead", compruebe si la carpeta de destino está relacionada de alguna manera con las palabras clave de la regla para decidir si parece sospechosa o no. 

- Eliminar todo

   Algunos atacantes simplemente eliminarán todos los correos electrónicos entrantes para ocultar su actividad. En su mayoría, una regla de "eliminar todos los correos electrónicos entrantes" sin filtrarlos con palabras clave es un indicador de actividad malintencionada. 
 
Este es un ejemplo de una configuración de regla "eliminar todos los correos electrónicos entrantes" (como se ve en RawEventData.Parameters) del registro de eventos relevante. 

:::image type="content" source="../../media/alert-grading-playbook-inbox-manipulation-rules/alert-grading-playbook-inbox-manipulation-rules-delete-log.png" alt-text="Ejemplo de una configuración de regla eliminar todos los correos electrónicos entrantes" lightbox="../../media/alert-grading-playbook-inbox-manipulation-rules/alert-grading-playbook-inbox-manipulation-rules-delete-log.png":::


### <a name="3-investigate-the-ip-address"></a>3. Investigar la dirección IP

Revise los atributos de la dirección IP que realizó el evento relevante de creación de reglas:

- Busque otras actividades en la nube sospechosas que se originaron desde la misma IP en el inquilino. Por ejemplo, la actividad sospechosa puede ser varios intentos de inicio de sesión con errores. 
- ¿Es el ISP común y razonable para este usuario?
- ¿La ubicación es común y razonable para este usuario?

### <a name="4-investigate-suspicious-activity-by-the-user-prior-to-creating-the-rules"></a>4. Investigar actividad sospechosa por parte del usuario antes de crear las reglas

Puede revisar todas las actividades de usuario antes de crear reglas, buscar indicadores de peligro e investigar acciones de usuario que parezcan sospechosas. 

Por ejemplo, para varios inicios de sesión con errores, examine: 

- Actividad de inicio de sesión 

   Valide que la actividad de inicio de sesión anterior a la creación de la regla no sea sospechosa. (ubicación común / ISP / user-agent). 

- Alertas

   Compruebe si el usuario recibió alertas antes de crear las reglas. Esto podría indicar que la cuenta de usuario podría estar en peligro. Por ejemplo, alerta de viaje imposible, país poco frecuente, varios inicios de sesión con errores, entre otros).

- Incidente

   Compruebe si la alerta está asociada con otras alertas que indican un incidente. Si es así, compruebe si el incidente contiene otras alertas positivas reales.

## <a name="advanced-hunting-queries"></a>Consultas de búsqueda avanzadas

[La búsqueda avanzada](advanced-hunting-overview.md) es una herramienta de búsqueda de amenazas basada en consultas que te permite inspeccionar eventos de la red para localizar indicadores de amenazas. 

Use esta consulta para buscar todos los nuevos eventos de regla de bandeja de entrada durante una ventana de tiempo específica.  

```kusto
let start_date = now(-10h); 
let end_date = now();
let user_id = ""; // enter here the user id
CloudAppEvents
| where Timestamp between (start_date .. end_date)
| where AccountObjectId == user_id
| where ActionType in ("Set-Mailbox", "New-InboxRule", "Set-InboxRule") //set new inbox rule related operations
| project Timestamp, ActionType, CountryCode, City, ISP, IPAddress, RuleConfig = RawEventData.Parameters, RawEventData
```

La *columna RuleConfig* proporcionará la nueva configuración de regla de bandeja de entrada.

Use esta consulta para comprobar si el ISP es común para el usuario al consultar el historial del usuario.

```kusto
let alert_date = now(); //enter alert date 
let timeback = 60d; 
let userid = ""; //enter here user id 
CloudAppEvents 
| where Timestamp between ((alert_date-timeback)..(alert_date-1h)) 
| where AccountObjectId == userid 
| make-series ActivityCount = count() default = 0 on Timestamp  from (alert_date-timeback) to (alert_date-1h) step 12h by ISP 
```

Use esta consulta para comprobar si el país es común para el usuario al consultar el historial del usuario.

```kusto
let alert_date = now(); //enter alert date 
let timeback = 60d; 
let userid = ""; //enter here user id 
CloudAppEvents 
| where Timestamp between ((alert_date-timeback)..(alert_date-1h)) 
| where AccountObjectId == userid 
| make-series ActivityCount = count() default = 0 on Timestamp  from (alert_date-timeback) to (alert_date-1h) step 12h by CountryCode
```

Use esta consulta para comprobar si el agente de usuario es común para el usuario al consultar el historial del usuario.

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

1. Deshabilitar la regla de bandeja de entrada malintencionada.
2. Restablezca las credenciales de la cuenta de usuario. También puedes comprobar si la cuenta de usuario se ha visto comprometida con Microsoft Defender para Aplicaciones en la nube, que obtiene las señales de seguridad de Azure Active Directory (Azure AD) Identity Protection.
3. Busque otras actividades malintencionadas realizadas por la cuenta de usuario afectada.
4. Compruebe si hay otra actividad sospechosa en el inquilino que se originó desde la misma IP o desde el mismo ISP (si el ISP es poco común) para encontrar otras cuentas de usuario comprometidas.

## <a name="see-also"></a>Vea también

- [Información general sobre la clasificación de alertas](alert-grading-playbooks.md)
- [Actividad de reenvío de correo electrónico sospechoso](alert-grading-playbook-email-forwarding.md)
- [Reglas de reenvío de bandeja de entrada sospechosas](alert-grading-playbook-inbox-forwarding-rules.md)
- [Investigar alertas](investigate-alerts.md)
