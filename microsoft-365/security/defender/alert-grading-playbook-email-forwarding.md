---
title: Clasificación de alertas para actividad de reenvío de correo electrónico sospechosa
description: Clasificación de alertas para la actividad de reenvío de correo electrónico sospechoso para revisar las alertas y realizar acciones recomendadas para corregir el ataque y proteger la red.
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
ms.openlocfilehash: 83e8061d2c9473c274d615c8905b2918e1b72d17
ms.sourcegitcommit: e3bff611439354e6339bb666a88682078f32ec13
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2022
ms.locfileid: "62355210"
---
# <a name="alert-grading-for-suspicious-email-forwarding-activity"></a>Clasificación de alertas para actividad de reenvío de correo electrónico sospechosa

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**
- Microsoft 365 Defender

Los actores de amenazas pueden usar cuentas de usuario comprometidas para varios fines malintencionados, como leer correos electrónicos en la bandeja de entrada de un usuario, reenviar correos electrónicos a destinatarios externos y enviar correos de suplantación de identidad, entre otros. Es posible que el usuario de destino no tenga conocimiento de que se reenvía su correo electrónico. Esta es una táctica muy común que usan los atacantes cuando las cuentas de usuario están en peligro.

Los correos electrónicos se pueden reenviar manualmente o automáticamente mediante reglas de reenvío. El reenvío automático se puede implementar de varias maneras, como reglas de bandeja de entrada, Exchange de transporte (ETR) y reenvío SMTP. Aunque el reenvío manual requiere una acción directa de los usuarios, es posible que no conozcan todos los correos electrónicos reenviados automáticamente. En Microsoft 365, se genera una alerta cuando un usuario reenvía automáticamente un correo electrónico a una dirección de correo electrónico potencialmente malintencionada.

Este libro de juegos te ayuda a investigar las alertas de reenvío de correo electrónico sospechoso y calificarlas rápidamente como verdadero positivo (TP) o falso positivo (FP). A continuación, puede realizar las acciones recomendadas para las alertas de TP para corregir el ataque.

Para obtener información general sobre la calificación de alertas para Microsoft Defender para Office 365 y Microsoft Defender para aplicaciones en la nube, consulte el [artículo de introducción](alert-grading-playbooks.md).

Los resultados del uso de este libro de juegos son:

- Ha identificado las alertas asociadas con correos electrónicos reenviados automáticamente como actividades malintencionadas (TP) o benignas (FP).

  Si es malintencionado, ha detenido [el reenvío automático de correo electrónico](../office-365-security/external-email-forwarding.md) para los buzones afectados.

- Ha realizado la acción necesaria si los correos electrónicos se han reenviado a una dirección de correo electrónico malintencionada.

## <a name="email-forwarding-rules"></a>Reglas de reenvío de correo electrónico

La regla de reenvío de correo electrónico permite a los usuarios configurar una regla para reenviar los mensajes de correo electrónico enviados al buzón de un usuario al buzón de otro usuario dentro o fuera de la organización. Algunos usuarios de correo electrónico, especialmente los que tienen varios buzones, configuran reglas de reenvío para mover los correos electrónicos de los empleadores a sus cuentas de correo electrónico privadas. El reenvío de correo electrónico es una característica útil, pero también puede suponer un riesgo de seguridad debido a la posible divulgación de información. Los atacantes pueden usar esta información para atacar a su organización o a sus asociados.

### <a name="suspicious-email-forwarding-rules"></a>Reglas de reenvío de correo electrónico sospechosas

Los atacantes pueden configurar reglas de correo electrónico para ocultar los correos electrónicos entrantes en el buzón de usuario comprometido para ocultar sus actividades malintencionadas del usuario. También pueden establecer reglas en el buzón de usuario comprometido para eliminar correos electrónicos, mover los correos electrónicos a otra carpeta menos perceptible, como una carpeta RSS, o reenviar correos electrónicos a una cuenta externa.  

Algunas reglas pueden mover todos los correos electrónicos a otra carpeta y marcarlos como "leídos", mientras que algunas reglas pueden mover solo los correos que contienen palabras clave específicas en el asunto o mensaje de correo electrónico. Por ejemplo, la regla de bandeja de entrada puede establecerse para buscar palabras clave como "factura", "phish", "no responder", "correo electrónico sospechoso" o "correo no deseado", entre otras, y moverlas a una cuenta de correo electrónico externa. Los atacantes también pueden usar el buzón de usuario en peligro para distribuir correo no deseado, correos electrónicos de suplantación de identidad o malware.
 
Microsoft Defender para Office 365 detectar y alertar sobre reglas de reenvío de correo electrónico sospechosas, lo que le permite buscar y eliminar reglas ocultas en el origen.

Para obtener más información, consulta estas entradas de blog:

- [Compromiso de correo electrónico empresarial](https://techcommunity.microsoft.com/t5/microsoft-defender-for-office/business-email-uncompromised-part-one/ba-p/2159900)
- [Entre bastidores de compromiso de correo electrónico empresarial: usar datos de amenazas entre dominios para interrumpir una campaña de BEC de gran tamaño](https://www.microsoft.com/security/blog/2021/06/14/behind-the-scenes-of-business-email-compromise-using-cross-domain-threat-data-to-disrupt-a-large-bec-infrastructure/)


## <a name="alert-details"></a>Detalles de la alerta

Para revisar la alerta específica, abra la página **Alertas** para ver la sección **Lista de** actividades. Por ejemplo:
 
:::image type="content" source="../../media/alert-grading-playbook-email-forwarding/alert-grading-playbook-email-forwarding-activity-list.png" alt-text="Lista de actividades relacionadas con la alerta" lightbox="../../media/alert-grading-playbook-email-forwarding/alert-grading-playbook-email-forwarding-activity-list.png":::

Seleccione **Actividad**  para ver los detalles de esa actividad en la barra lateral. Por ejemplo:
 
:::image type="content" source="../../media/alert-grading-playbook-email-forwarding/alert-grading-playbook-email-forwarding-activity-details.png" alt-text="Detalles de la actividad" lightbox="../../media/alert-grading-playbook-email-forwarding/alert-grading-playbook-email-forwarding-activity-details.png":::

El **campo** Motivo contiene la siguiente información relacionada con esta alerta.

- El tipo de reenvío (FT) es uno de los siguientes:

    -  Exchange de transporte (ETR): reenviada mediante y Exchange de transporte 

    -  SMTP: reenviado mediante el reenvío de buzones

    -  InboxRule: Reenviado mediante una regla de bandeja de entrada

- Id. de seguimiento de mensajes (MTI): este es el identificador (NetworkMessageId) del correo electrónico reenviado que desencadenó esta alerta. NetworkMessageId es el identificador único de un correo electrónico de la organización.
- Reenviador (F): el usuario que reenvía este correo electrónico.
- Lista de destinatarios sospechosos (SRL): la lista de destinatarios considerados sospechosos en este correo electrónico.
- Lista de destinatarios (RL): la lista de todos los destinatarios de este correo electrónico.

## <a name="investigation-workflow"></a>Flujo de trabajo de investigación

Al investigar esta alerta, debe determinar:

- ¿La cuenta de usuario y su buzón están en peligro?
- ¿Las actividades son malintencionadas?

### <a name="is-the-user-account-and-its-mailbox-compromised"></a>¿La cuenta de usuario y su buzón están en peligro?

Al ver el comportamiento pasado del remitente y las actividades recientes, debe poder determinar si la cuenta del usuario debe considerarse comprometida o no. Puede ver los detalles de las alertas generadas desde la página del usuario en el portal Microsoft 365 Defender usuario. 

También puede analizar estas actividades adicionales para el buzón afectado:

- Usar el Explorador de amenazas para comprender las amenazas relacionadas con el correo electrónico

    - Observe cuántos de los correos electrónicos recientes enviados por el remitente se detectan como phish, spam o malware.

    - Observe cuántos de los correos electrónicos enviados contienen información confidencial. 

- Evalúe el comportamiento de inicio de sesión arriesgado en el portal Microsoft Azure usuario.
- Compruebe si hay actividades malintencionadas en el dispositivo del usuario.

### <a name="are-the-activities-malicious"></a>¿Las actividades son malintencionadas?

Investigar la actividad de reenvío de correo electrónico. Por ejemplo, compruebe el tipo de correo electrónico, el destinatario de este correo electrónico o la forma en que se reenvía el correo electrónico. 

Para más información, consulte los siguientes artículos:

- [Información de mensajes reenviados automáticamente](/microsoft-365/security/office-365-security/mfi-auto-forwarded-messages-report)
- [Información de nuevos usuarios que reenvían correo electrónico](/microsoft-365/security/office-365-security/mfi-new-users-forwarding-email)
- [Responder a una cuenta de correo electrónico en peligro](/microsoft-365/security/office-365-security/responding-to-a-compromised-email-account)
- [Informar de falsos positivos y falsos negativos en Outlook](/microsoft-365/security/office-365-security/report-false-positives-and-false-negatives)

Este es el flujo de trabajo para identificar actividades sospechosas de reenvío de correo electrónico.

:::image type="content" source="../../media/alert-grading-playbook-email-forwarding/alert-grading-playbook-email-forwarding-workflow.png" alt-text="Flujo de trabajo de investigación de alertas para reenvío de correo electrónico" lightbox="../../media/alert-grading-playbook-email-forwarding/alert-grading-playbook-email-forwarding-workflow.png":::

Puede investigar una alerta de reenvío de correo electrónico mediante el Explorador de amenazas o con consultas avanzadas de búsqueda, en función de la disponibilidad de las características en el portal Microsoft 365 Defender correo electrónico. Puede elegir seguir todo el proceso o una parte del proceso según sea necesario.

## <a name="using-threat-explorer"></a>Uso del Explorador de amenazas

El Explorador de amenazas proporciona una experiencia de investigación interactiva para las amenazas relacionadas con el correo electrónico para determinar si esta actividad es sospechosa o no. Puede usar los siguientes indicadores de la información de alerta:

- SRL/RL: Use la lista de destinatarios (sospechosos) (SRL) para encontrar estos detalles:
 
    :::image type="content" source="../../media/alert-grading-playbook-email-forwarding/alert-grading-playbook-email-forwarding-recipients-list.png" alt-text="Ejemplo de la lista de destinatarios" lightbox="../../media/alert-grading-playbook-email-forwarding/alert-grading-playbook-email-forwarding-recipients-list.png":::

    - Quién más ha reenviado correos electrónicos a estos destinatarios.

    - ¿Cuántos correos electrónicos se han reenviado a estos destinatarios?

    - ¿Con qué frecuencia se reenvía el correo electrónico a estos destinatarios?
 

- MTI: Use el id. de seguimiento de mensajes/id. de mensaje de red para encontrar estos detalles:

    :::image type="content" source="../../media/alert-grading-playbook-email-forwarding/alert-grading-playbook-email-forwarding-network-message-id.png" alt-text="Ejemplo del id. de mensaje de red" lightbox="../../media/alert-grading-playbook-email-forwarding/alert-grading-playbook-email-forwarding-network-message-id.png":::

    - ¿Qué detalles adicionales están disponibles para este correo electrónico? Por ejemplo: asunto, ruta de acceso de devolución y marca de tiempo.

    - ¿Cuál es el origen de este correo electrónico? ¿Hay algún correo electrónico similar?

    - ¿Este correo electrónico contiene direcciones URL? ¿La dirección URL apunta a algún dato confidencial?

    - ¿El correo electrónico contiene datos adjuntos? ¿Los datos adjuntos contienen información confidencial?

    - ¿Cuál fue la acción realizada en el correo electrónico? ¿Se eliminó, marcó como leído o se movió a otra carpeta?

    - ¿Hay alguna amenaza asociada a este correo electrónico? ¿Este correo electrónico forma parte de alguna campaña?

En función de las respuestas a estas preguntas, debe poder determinar si un correo electrónico es malintencionado o benigno.

## <a name="advanced-hunting-queries"></a>Consultas de búsqueda avanzadas

Para usar [consultas](advanced-hunting-overview.md) avanzadas de búsqueda para recopilar información relacionada con una alerta y determinar si la actividad es sospechosa o no, asegúrese de tener acceso a las tablas siguientes:

- EmailEvents: contiene información relacionada con el flujo de correo electrónico.

- EmailUrlInfo: contiene información relacionada con las direcciones URL de los correos electrónicos.

- CloudAppEvents: contiene el registro de auditoría de las actividades del usuario.

- IdentityLogonEvents: contiene información de inicio de sesión para todos los usuarios.

Por ejemplo:

:::image type="content" source="../../media/alert-grading-playbook-email-forwarding/alert-grading-playbook-email-forwarding-advanced-hunting.png" alt-text="Ejemplo de la página Búsqueda avanzada" lightbox="../../media/alert-grading-playbook-email-forwarding/alert-grading-playbook-email-forwarding-advanced-hunting.png":::

Use consultas para recopilar información sobre las siguientes preguntas.

>[!Note]
>Ciertos parámetros son únicos para la organización o la red. Rellene estos parámetros específicos como se indica en cada consulta.
>

Ejecute esta consulta para averiguar quién más ha reenviado correos electrónicos a estos destinatarios (SRL/RL).

```kusto
let srl=pack_array("{SRL}"); //Put values from SRL here.
EmailEvents
| where RecipientEmailAddress in (srl)
| distinct SenderDisplayName, SenderFromAddress, SenderObjectId
```

Ejecute esta consulta para averiguar cuántos correos electrónicos se reenvían a estos destinatarios.

```kusto
let srl=pack_array("{SRL}"); //Put values from SRL here.
EmailEvents
| where RecipientEmailAddress in (srl)
| summarize Count=dcount(NetworkMessageId) by RecipientEmailAddress
```

Ejecute esta consulta para averiguar con qué frecuencia se reenvía el correo electrónico a estos destinatarios.

```kusto
let srl=pack_array("{SRL}"); //Put values from SRL here.
EmailEvents
| where RecipientEmailAddress in (srl)
| summarize Count=dcount(NetworkMessageId) by RecipientEmailAddress, bin(Timestamp, 1d)
```

Ejecute esta consulta para averiguar si el correo electrónico contiene direcciones URL.
 
```kusto
let mti='{MTI}'; //Replace {MTI} with MTI from alert
EmailUrlInfo
| where NetworkMessageId == mti
```

Ejecute esta consulta para averiguar si el correo electrónico contiene datos adjuntos.

   ```kusto
   let mti='{MTI}'; //Replace {MTI} with MTI from alert
   EmailAttachmentInfo
   | where NetworkMessageId == mti
   ```

Ejecute esta consulta para averiguar si el reenviador (remitente) ha creado alguna regla nueva.

```kusto
let sender = "{SENDER}"; //Replace {SENDER} with display name of Forwarder
let action_types = pack_array(
    "New-InboxRule", 
    "UpdateInboxRules", 
    "Set-InboxRule", 
    "Set-Mailbox",    
    "New-TransportRule",
    "Set-TransportRule");
CloudAppEvents
| where AccountDisplayName == sender
| where ActionType in (action_types)
```

Ejecute esta consulta para averiguar si hubo algún evento de inicio de sesión anómalo de este usuario. Por ejemplo: IP desconocidas, nuevas aplicaciones, países poco comunes, varios eventos LogonFailed.

```kusto
let sender = "{SENDER}"; //Replace {SENDER} with email of the Forwarder IdentityLogonEvents
| where AccountUpn == sender
```

### <a name="investigating-forwarding-rules"></a>Investigar reglas de reenvío

También puede encontrar reglas de reenvío sospechosas mediante el centro de administración de Exchange, en función del tipo de regla (el valor FT de la alerta).

- ETR 

  Exchange de transporte se enumeran en la **sección** Reglas. Compruebe que todas las reglas son las esperadas.

- SMTP

  Puede ver las reglas de reenvío de buzones **\> \> seleccionando el buzón del remitente Administrar la configuración del flujo de correo Editar reenvío de \> correo** electrónico.

- InboxRule

  Las reglas de la Bandeja de entrada se configuran con el cliente de correo electrónico. Puede usar el cmdlet [de PowerShell Get-InboxRule](/powershell/module/exchange/get-inboxrule) para enumerar las reglas de bandeja de entrada creadas por los usuarios.

### <a name="additional-investigation"></a>Investigación adicional

Junto con la evidencia detectada hasta ahora, puede determinar si hay nuevas reglas de reenvío que se están creando. Investigue la dirección IP asociada a la regla. Asegúrese de que no es una dirección IP anómala y que es coherente con las actividades habituales realizadas por el usuario.

## <a name="recommended-actions"></a>Acciones recomendadas

Una vez que determine que las actividades asociadas convierten esta alerta en True Positive, clasifique la alerta y realice estas acciones para la corrección:

1. Deshabilitar y eliminar la regla de reenvío de bandeja de entrada.
2. Para el tipo de reenvío InboxRule, restablezca las credenciales de cuenta del usuario.
3. Para el tipo de reenvío SMTP o ETR, investigue las actividades de la cuenta de usuario que creó la alerta.

    - Investigar cualquier otra actividad de administrador sospechosa.

    - Restablezca las credenciales de la cuenta de usuario.

4. Compruebe si hay actividades adicionales originadas por cuentas afectadas, direcciones IP y remitentes sospechosos.

## <a name="see-also"></a>Vea también

- [Información general sobre la clasificación de alertas](alert-grading-playbooks.md)
- [Reglas de reenvío de bandeja de entrada sospechosas](alert-grading-playbook-inbox-forwarding-rules.md)
- [Reglas sospechosas de manipulación de la bandeja de entrada](alert-grading-playbook-inbox-manipulation-rules.md)
- [Investigar alertas](investigate-alerts.md)
