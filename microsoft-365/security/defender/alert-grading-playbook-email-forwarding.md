---
title: Clasificación de alertas para actividades sospechosas de reenvío de correo electrónico
description: Clasificación de alertas para la actividad sospechosa de reenvío de correo electrónico para revisar las alertas y realizar las acciones recomendadas para corregir el ataque y proteger la red.
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
ms.openlocfilehash: 088cb74f16fae1155b86b1bfa6b5c72aae287720
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2022
ms.locfileid: "67482106"
---
# <a name="alert-grading-for-suspicious-email-forwarding-activity"></a>Clasificación de alertas para actividades sospechosas de reenvío de correo electrónico

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**
- Microsoft 365 Defender

Los actores de amenazas pueden usar cuentas de usuario en peligro para varios propósitos malintencionados, como leer correos electrónicos en la bandeja de entrada de un usuario, reenviar correos electrónicos a destinatarios externos y enviar correos de phishing, entre otros. Es posible que el usuario de destino no sea consciente de que se están reenviando sus correos electrónicos. Se trata de una táctica muy común que los atacantes usan cuando las cuentas de usuario están en peligro.

Los correos electrónicos se pueden reenviar manualmente o automáticamente mediante reglas de reenvío. El reenvío automático se puede implementar de varias maneras, como reglas de bandeja de entrada, regla de transporte de Exchange (ETR) y reenvío SMTP. Aunque el reenvío manual requiere la acción directa de los usuarios, es posible que no tengan en cuenta todos los correos electrónicos reenviados automáticamente. En Microsoft 365, se genera una alerta cuando un usuario reenvía automáticamente un correo electrónico a una dirección de correo electrónico potencialmente malintencionada.

Este cuaderno de estrategias le ayuda a investigar alertas sospechosas de actividad de reenvío de Email y a calificarlas rápidamente como un verdadero positivo (TP) o un falso positivo (FP). A continuación, puede realizar las acciones recomendadas para que las alertas de TP corrijan el ataque.

Para obtener información general sobre la clasificación de alertas para Microsoft Defender para Office 365 y Microsoft Defender for Cloud Apps, consulte el [artículo de introducción](alert-grading-playbooks.md).

Los resultados del uso de este cuaderno de estrategias son:

- Ha identificado las alertas asociadas con correos electrónicos reenviados automáticamente como actividades malintencionadas (TP) o benignas (FP).

  Si es malintencionado, ha [detenido el reenvío automático de correo electrónico](../office-365-security/external-email-forwarding.md) para los buzones afectados.

- Ha realizado la acción necesaria si los correos electrónicos se han reenviado a una dirección de correo electrónico malintencionada.

## <a name="email-forwarding-rules"></a>reglas de reenvío de Email

Email reglas de reenvío permiten a los usuarios crear una regla para reenviar mensajes de correo electrónico enviados al buzón de correo de un usuario al buzón de otro usuario dentro o fuera de la organización. Algunos usuarios de correo electrónico, especialmente los que tienen varios buzones, configuran reglas de reenvío para mover los correos electrónicos del empleador a sus cuentas de correo electrónico privadas. Email reenvío es una característica útil, pero también puede suponer un riesgo para la seguridad debido a la posible divulgación de información. Los atacantes pueden usar esta información para atacar a su organización o a sus asociados.

### <a name="suspicious-email-forwarding-activity"></a>Actividad de reenvío de correo electrónico sospechoso

Los atacantes pueden configurar reglas de correo electrónico para ocultar los correos electrónicos entrantes en el buzón de usuario en peligro para ocultar sus actividades malintencionadas al usuario. También pueden establecer reglas en el buzón de usuario en peligro para eliminar correos electrónicos, mover los correos electrónicos a otra carpeta menos notable, como una carpeta RSS, o reenviar correos electrónicos a una cuenta externa.

Algunas reglas pueden mover todos los correos electrónicos a otra carpeta y marcarlos como "leídos", mientras que algunas reglas solo pueden mover correos que contienen palabras clave específicas en el mensaje de correo electrónico o asunto. Por ejemplo, la regla de bandeja de entrada podría establecerse para buscar palabras clave como "factura", "phish", "no responder", "correo electrónico sospechoso" o "spam" entre otros, y moverlas a una cuenta de correo electrónico externa. Los atacantes también pueden usar el buzón de usuario en peligro para distribuir correo no deseado, correos electrónicos de suplantación de identidad (phishing) o malware.

Microsoft Defender para Office 365 puede detectar y alertar sobre reglas de reenvío de correo electrónico sospechosas, lo que le permite buscar y eliminar reglas ocultas en el origen.

Para obtener más información, vea estas entradas de blog:

- [Compromiso de Email empresarial](https://techcommunity.microsoft.com/t5/microsoft-defender-for-office/business-email-uncompromised-part-one/ba-p/2159900)
- [En segundo plano del riesgo de correo electrónico empresarial: uso de datos de amenazas entre dominios para interrumpir una campaña de BEC grande](https://www.microsoft.com/security/blog/2021/06/14/behind-the-scenes-of-business-email-compromise-using-cross-domain-threat-data-to-disrupt-a-large-bec-infrastructure/)

## <a name="alert-details"></a>Detalles de la alerta

Para revisar la alerta Actividad de reenvío de Email sospechosa, abra la página **Alertas** para ver la sección **Lista de actividad**. Por ejemplo:

:::image type="content" source="../../media/alert-grading-playbook-email-forwarding/alert-grading-playbook-email-forwarding-activity-list.png" alt-text="Lista de actividades relacionadas con la alerta" lightbox="../../media/alert-grading-playbook-email-forwarding/alert-grading-playbook-email-forwarding-activity-list.png":::

Seleccione **Actividad**  para ver los detalles de esa actividad en la barra lateral. Por ejemplo:

:::image type="content" source="../../media/alert-grading-playbook-email-forwarding/alert-grading-playbook-email-forwarding-activity-details.png" alt-text="Detalles de la actividad" lightbox="../../media/alert-grading-playbook-email-forwarding/alert-grading-playbook-email-forwarding-activity-details.png":::

El campo **Motivo** contiene la siguiente información relacionada con esta alerta.

- El tipo de reenvío (FT) es uno de los siguientes:
  - Regla de transporte de Exchange (ETR): reenviado mediante y regla de transporte de Exchange
  - SMTP: reenviado mediante el reenvío de buzones
  - InboxRule: reenviado mediante una regla de bandeja de entrada

- Id. de seguimiento de mensajes (MTI): es el identificador (NetworkMessageId) del correo electrónico reenviado que desencadenó esta alerta. NetworkMessageId es el identificador único de un correo electrónico de la organización.
- Reenviador (F): el usuario que reenvió este correo electrónico.
- Lista de destinatarios sospechosos (SRL): lista de destinatarios considerados sospechosos en este correo electrónico.
- Lista de destinatarios (RL): lista de todos los destinatarios de este correo electrónico.

## <a name="investigation-workflow"></a>Flujo de trabajo de investigación

Al investigar esta alerta, debe determinar lo siguiente:

- ¿Está en peligro la cuenta de usuario y su buzón de correo?
- ¿Las actividades son malintencionadas?

### <a name="is-the-user-account-and-its-mailbox-compromised"></a>¿Está en peligro la cuenta de usuario y su buzón de correo?

Al examinar el comportamiento pasado del remitente y las actividades recientes, debe ser capaz de determinar si la cuenta del usuario debe considerarse en peligro o no. Puede ver los detalles de las alertas que se generan desde la página del usuario en el portal de Microsoft 365 Defender.

También puede analizar estas actividades adicionales para el buzón afectado:

- Uso del Explorador de amenazas para comprender las amenazas relacionadas con el correo electrónico
  - Observe cuántos de los correos electrónicos recientes enviados por el remitente se detectan como phish, spam o malware.
  - Observe cuántos de los correos electrónicos enviados contienen información confidencial.

- Evalúe el comportamiento de inicio de sesión de riesgo en microsoft Azure Portal.
- Compruebe si hay actividades malintencionadas en el dispositivo del usuario.

### <a name="are-the-activities-malicious"></a>¿Las actividades son malintencionadas?

Investigue la actividad de reenvío de correo electrónico. Por ejemplo, compruebe el tipo de correo electrónico, el destinatario de este correo electrónico o la manera en que se reenvía el correo electrónico.

Para más información, consulte los siguientes artículos:

- [Información de mensajes reenviados automáticamente](/microsoft-365/security/office-365-security/mfi-auto-forwarded-messages-report)
- [Información de nuevos usuarios que reenvían correo electrónico](/microsoft-365/security/office-365-security/mfi-new-users-forwarding-email)
- [Responder a una cuenta de correo electrónico en peligro](/microsoft-365/security/office-365-security/responding-to-a-compromised-email-account)
- [Informar de falsos positivos y falsos negativos en Outlook](/microsoft-365/security/office-365-security/report-false-positives-and-false-negatives)

Este es el flujo de trabajo para identificar actividades sospechosas de reenvío de correo electrónico.

:::image type="content" source="../../media/alert-grading-playbook-email-forwarding/alert-grading-playbook-email-forwarding-workflow.png" alt-text="Flujo de trabajo de investigación de alertas para el reenvío de correo electrónico" lightbox="../../media/alert-grading-playbook-email-forwarding/alert-grading-playbook-email-forwarding-workflow.png":::

Puede investigar una alerta de reenvío de correo electrónico mediante el Explorador de amenazas o con consultas de búsqueda avanzadas, en función de la disponibilidad de las características del portal de Microsoft 365 Defender. Puede elegir seguir todo el proceso o una parte del proceso según sea necesario.

## <a name="using-threat-explorer"></a>Uso del Explorador de amenazas

El Explorador de amenazas proporciona una experiencia de investigación interactiva para las amenazas relacionadas con el correo electrónico para determinar si esta actividad es sospechosa o no. Puede usar los siguientes indicadores de la información de alerta:

- SRL/RL: use la lista de destinatarios (SRL) (sospechosos) para encontrar estos detalles:

    :::image type="content" source="../../media/alert-grading-playbook-email-forwarding/alert-grading-playbook-email-forwarding-recipients-list.png" alt-text="Ejemplo de la lista de destinatarios" lightbox="../../media/alert-grading-playbook-email-forwarding/alert-grading-playbook-email-forwarding-recipients-list.png":::

  - ¿Quién más ha reenviado correos electrónicos a estos destinatarios?
  - ¿Cuántos correos electrónicos se han reenviado a estos destinatarios?
  - ¿Con qué frecuencia se reenvía un correo electrónico a estos destinatarios?

- MTI: use el identificador de seguimiento de mensajes o el identificador de mensaje de red para encontrar estos detalles:

    :::image type="content" source="../../media/alert-grading-playbook-email-forwarding/alert-grading-playbook-email-forwarding-network-message-id.png" alt-text="Ejemplo del identificador de mensaje de red" lightbox="../../media/alert-grading-playbook-email-forwarding/alert-grading-playbook-email-forwarding-network-message-id.png":::

  - ¿Qué detalles adicionales están disponibles para este correo electrónico? Por ejemplo: asunto, ruta de acceso de retorno y marca de tiempo.
  - ¿Cuál es el origen de este correo electrónico? ¿Hay correos electrónicos similares?
  - ¿Contiene este correo electrónico alguna dirección URL? ¿La dirección URL apunta a datos confidenciales?
  - ¿El correo electrónico contiene datos adjuntos? ¿Los datos adjuntos contienen información confidencial?
  - ¿Cuál fue la acción realizada en el correo electrónico? ¿Se eliminó, se marcó como leído o se movió a otra carpeta?
  - ¿Hay alguna amenaza asociada a este correo electrónico? ¿Este correo electrónico forma parte de alguna campaña?

En función de las respuestas a estas preguntas, debe ser capaz de determinar si un correo electrónico es malintencionado o benigno.

## <a name="advanced-hunting-queries"></a>Consultas de búsqueda avanzadas

Para usar consultas [de búsqueda avanzadas](advanced-hunting-overview.md) para recopilar información relacionada con una alerta y determinar si la actividad es sospechosa o no, asegúrese de que tiene acceso a las tablas siguientes:

- EmailEvents: contiene información relacionada con el flujo de correo electrónico.

- EmailUrlInfo: contiene información relacionada con las direcciones URL de los correos electrónicos.

- CloudAppEvents: contiene el registro de auditoría de las actividades del usuario.

- IdentityLogonEvents: contiene información de inicio de sesión para todos los usuarios.

> [!NOTE]
> Algunos parámetros son únicos para su organización o red. Rellene estos parámetros específicos como se indica en cada consulta.

Ejecute esta consulta para averiguar quién más ha reenviado correos electrónicos a estos destinatarios (SRL/RL).

```kusto
let srl=pack_array("{SRL}"); //Put values from SRL here.
EmailEvents
| where RecipientEmailAddress in (srl)
| distinct SenderDisplayName, SenderFromAddress, SenderObjectId
```

Ejecute esta consulta para averiguar cuántos correos electrónicos se han reenviado a estos destinatarios.

```kusto
let srl=pack_array("{SRL}"); //Put values from SRL here.
EmailEvents
| where RecipientEmailAddress in (srl)
| summarize Count=dcount(NetworkMessageId) by RecipientEmailAddress
```

Ejecute esta consulta para averiguar con qué frecuencia se reenvía correos electrónicos a estos destinatarios.

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

Ejecute esta consulta para averiguar si el reenviador (remitente) ha creado nuevas reglas.

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

Ejecute esta consulta para averiguar si había eventos de inicio de sesión anómalos de este usuario. Por ejemplo: direcciones IP desconocidas, nuevas aplicaciones, países poco comunes, varios eventos LogonFailed.

```kusto
let sender = "{SENDER}"; //Replace {SENDER} with email of the Forwarder
IdentityLogonEvents
| where AccountUpn == sender
```

### <a name="investigating-forwarding-rules"></a>Investigación de reglas de reenvío

También puede encontrar reglas de reenvío sospechosas mediante el Centro de administración de Exchange, en función del tipo de regla (el valor FT de la alerta).

- ETR

  Las reglas de transporte de Exchange se enumeran en la sección **Reglas** . Compruebe que todas las reglas son las esperadas.

- SMTP

  Para ver las reglas de reenvío de buzones, seleccione el buzón **\> del remitente Administrar la configuración \> del flujo de correo Email editar el \> reenvío**.

- InboxRule

  Las reglas de bandeja de entrada se configuran con el cliente de correo electrónico. Puede usar el cmdlet [Get-InboxRule](/powershell/module/exchange/get-inboxrule) de PowerShell para enumerar las reglas de bandeja de entrada creadas por los usuarios.

### <a name="additional-investigation"></a>Investigación adicional

Junto con la evidencia detectada hasta ahora, puede determinar si se están creando nuevas reglas de reenvío. Investigue la dirección IP asociada a la regla. Asegúrese de que no es una dirección IP anómala y que es coherente con las actividades habituales realizadas por el usuario.

## <a name="recommended-actions"></a>Acciones recomendadas

Una vez que determine que las actividades asociadas convierten esta alerta en True Positive, clasifique la alerta y realice estas acciones para la corrección:

1. Deshabilite y elimine la regla de reenvío de bandeja de entrada.
2. Para el tipo de reenvío InboxRule, restablezca las credenciales de la cuenta del usuario.
3. Para el tipo de reenvío SMTP o ETR, investigue las actividades de la cuenta de usuario que creó la alerta.

    - Investigue cualquier otra actividad de administración sospechosa.

    - Restablezca las credenciales de la cuenta de usuario.

4. Compruebe si hay actividades adicionales originadas en cuentas afectadas, direcciones IP y remitentes sospechosos.

## <a name="see-also"></a>Vea también

- [Introducción a la clasificación de alertas](alert-grading-playbooks.md)
- [Reglas del reenvío sospechoso desde la bandeja de entrada](alert-grading-playbook-inbox-forwarding-rules.md)
- [Reglas sospechosas de manipulación de la bandeja de entrada](alert-grading-playbook-inbox-manipulation-rules.md)
- [Investigar alertas](investigate-alerts.md)
