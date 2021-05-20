---
title: Ajustar protección contra phishing
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid: ''
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
- MET150
description: Los administradores pueden aprender a identificar los motivos por los que un mensaje de suplantación de identidad (phishing) se ha recibido en Microsoft 365 y qué hacer para evitar más mensajes de suplantación de identidad en el futuro.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8d8f3f93b3fe1643467a12f90123b839addad2ed
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2021
ms.locfileid: "52537852"
---
# <a name="tune-anti-phishing-protection"></a>Ajustar protección contra phishing

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Aunque Microsoft 365 incluye una variedad de características contra la suplantación de identidad que están habilitadas de forma predeterminada, es posible que algunos mensajes de suplantación de identidad puedan llegar a los buzones de correo. En este tema se describe lo que puede hacer para descubrir por qué se ha pasado un mensaje de suplantación de identidad (phishing) y qué puede hacer para ajustar la configuración contra suplantación de identidad en su organización de Microsoft 365 sin empeorar accidentalmente las _cosas_.

## <a name="first-things-first-deal-with-any-compromised-accounts-and-make-sure-you-block-any-more-phishing-messages-from-getting-through"></a>En primer lugar: tratar con cuentas comprometidas y asegurarse de bloquear más mensajes de suplantación de identidad

Si la cuenta de un destinatario se ha visto comprometida como resultado del mensaje de suplantación de identidad, siga los pasos descritos en [Responder a](responding-to-a-compromised-email-account.md)una cuenta de correo electrónico comprometida en Microsoft 365 .

Si la suscripción incluye Microsoft Defender para Office 365, puedes usar Office 365 [inteligencia](office-365-ti.md) de amenazas para identificar otros usuarios que también recibieron el mensaje de suplantación de identidad. Tiene opciones adicionales para bloquear mensajes de suplantación de identidad:

- [Caja fuerte Vínculos en Microsoft Defender para Office 365](set-up-safe-links-policies.md)

- [Caja fuerte Datos adjuntos de Microsoft Defender para Office 365](set-up-safe-attachments-policies.md)

- [Directivas contra suplantación de identidad en Microsoft Defender para Office 365](configure-atp-anti-phishing-policies.md). Tenga en cuenta que puede aumentar temporalmente los umbrales de **suplantación** de identidad avanzada en la directiva de **Estándar** a **Agresivo,** Más agresivo **o** Más **agresivo.**

Compruebe que estas características de Defender Office 365 estén activadas.

## <a name="report-the-phishing-message-to-microsoft"></a>Notificar el mensaje de suplantación de identidad a Microsoft

Informar de mensajes de suplantación de identidad es útil para ajustar los filtros que se usan para proteger a todos los clientes de Microsoft 365. Para obtener instrucciones, vea [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="inspect-the-message-headers"></a>Inspeccionar los encabezados de mensaje

Puede examinar los encabezados del mensaje de suplantación de identidad (phishing) para ver si hay algo que pueda hacer usted mismo para evitar que se puedan recibir más mensajes de suplantación de identidad. En otras palabras, examinar los encabezados de mensajes puede ayudarle a identificar cualquier configuración de la organización que fuera responsable de permitir la entrada de mensajes de suplantación de identidad.

En concreto, debe comprobar el campo de encabezado **X-Forefront-Antispam-Report** en los encabezados de mensaje para obtener indicaciones de filtrado omitido para correo no deseado o suplantación de identidad (phishing) en el valor del veredicto de filtrado de correo no deseado (SFV). Los mensajes que omiten el filtrado tendrán una entrada de , lo que significa que una de las configuraciones permitió que este mensaje pasara invalidando los veredictos de correo no deseado o suplantación de identidad determinados por `SCL:-1` el servicio. Para obtener más información sobre cómo obtener encabezados de mensaje y la lista completa de todos los encabezados de mensajes contra correo no deseado y contra suplantación de identidad (phishing) disponibles, vea [Encabezados](anti-spam-message-headers.md)de mensajes contra correo no deseado en Microsoft 365 .

## <a name="best-practices-to-stay-protected"></a>Procedimientos recomendados para mantenerse protegido

- Cada mes, ejecute [Puntuación segura](../defender/microsoft-secure-score.md) para evaluar la configuración de seguridad de su organización.

- Para los mensajes que terminan en cuarentena por error o para los mensajes que se permiten, se recomienda buscar esos mensajes en el Explorador de amenazas y detecciones en [tiempo real.](threat-explorer.md) Puede buscar por remitente, destinatario o identificador de mensaje. Después de localizar el mensaje, vaya a los detalles haciendo clic en el asunto. Para obtener un mensaje en cuarentena, busque qué era la "tecnología de detección" para poder usar el método adecuado para invalidar. Para obtener un mensaje permitido, busque qué directiva permitió el mensaje.

- El correo electrónico de remitentes suplantados (la dirección De del mensaje no coincide con el origen del mensaje) se clasifica como suplantación de identidad en Defender para Office 365. A veces, la suplantación de identidad es benigna y, a veces, los usuarios no quieren que los mensajes de un remitente suplantado específico se pongan en cuarentena. Para minimizar el impacto para los usuarios, revise periódicamente la información sobre la suplantación de inteligencia [,](learn-about-spoof-intelligence.md)la pestaña Suplantación en la lista de [permitidos/bloqueados](tenant-allow-block-list.md)de inquilinos y el informe de detecciones [de suplantación.](view-email-security-reports.md#spoof-detections-report)  Una vez que haya revisado los remitentes suplantados permitidos y bloqueados y haya realizado las invalidaciones  necesarias, puede tener confianza para configurar la inteligencia de suplantación de identidad en directivas contra suplantación de identidad [(phishing)](set-up-anti-phishing-policies.md#spoof-settings) para poner en cuarentena los mensajes sospechosos en lugar de entregarlos a la carpeta de correo no deseado del usuario.

- Puede repetir el paso anterior para suplantación (dominio o usuario) en Microsoft Defender para Office 365. El informe de suplantación se encuentra en **Threat Management** \> **Dashboard** \> **Insights**.

- Revise periódicamente el informe [estado de protección contra amenazas](view-reports-for-mdo.md#threat-protection-status-report).

- Algunos clientes permiten inadvertidamente mensajes de suplantación de identidad colocando sus propios dominios en la lista Permitir remitente o Permitir dominio en directivas contra correo no deseado. Aunque esta configuración permitirá la entrada de algunos mensajes legítimos, también permitirá mensajes malintencionados que normalmente serían bloqueados por los filtros de correo no deseado o suplantación de identidad. En lugar de permitir el dominio, debe corregir el problema subyacente.

  La mejor manera de tratar los mensajes legítimos bloqueados por Microsoft 365 (falsos positivos) que implican remitentes en su dominio es  configurar completamente los registros SPF, DKIM y DMARC en DNS para todos los dominios de correo electrónico:

  - Compruebe que el registro SPF identifica _todos_ los orígenes de correo electrónico de los remitentes de su dominio (¡no olvide los servicios de terceros!).

  - Use error duro (todos) para asegurarse de que los sistemas de correo electrónico que están configurados para hacerlo rechazan a los \- remitentes no autorizados. Puede usar la [información](learn-about-spoof-intelligence.md) de inteligencia suplantación de identidad para ayudar a identificar los remitentes que usan su dominio para que pueda incluir remitentes de terceros autorizados en su registro SPF.

  Para obtener instrucciones de configuración, consulte:

  - [Configurar SPF para ayudar a evitar la suplantación de identidad](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

  - [Usar DKIM para validar el correo electrónico saliente enviado desde su dominio personalizado](use-dkim-to-validate-outbound-email.md)

  - [Usar DMARC para validar el correo electrónico](use-dmarc-to-validate-email.md)

- Siempre que sea posible, se recomienda entregar el correo electrónico de su dominio directamente a Microsoft 365. En otras palabras, apunte Microsoft 365 registro MX del dominio a Microsoft 365. Exchange Online Protection (EOP) puede proporcionar la mejor protección para los usuarios de la nube cuando su correo se entrega directamente a Microsoft 365. Si debe usar un sistema de higiene de correo electrónico de terceros delante de EOP, use filtrado mejorado para conectores. Para obtener instrucciones, consulte [Enhanced Filtering for Connectors in Exchange Online](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).

- Los usuarios deben usar el complemento [Report Message o](enable-the-report-message-add-in.md) el complemento Report [Phishing](enable-the-report-phish-add-in.md) para notificar mensajes a Microsoft, que puede entrenar nuestro sistema. Los administradores también deben aprovechar las [capacidades de envío de](admin-submission.md) administrador.

- La autenticación multifactor (MFA) es una buena forma de evitar cuentas comprometidas. Debe considerar la posibilidad de habilitar MFA para todos los usuarios. Para un enfoque por fases, empiece habilitando MFA para los usuarios más confidenciales (administradores, ejecutivos, etc.) antes de habilitar MFA para todos los usuarios. Para obtener instrucciones, vea [Configurar la autenticación multifactor](../../admin/security-and-compliance/set-up-multi-factor-authentication.md).

- Los atacantes suelen usar reglas de reenvío a destinatarios externos para extraer datos. Use la **información revisar reglas de reenvío** de buzones en [Puntuación](../defender/microsoft-secure-score.md) segura de Microsoft para buscar e incluso impedir el reenvío de reglas a destinatarios externos. Para obtener más información, vea [Mitigating Client External Forwarding Rules with Secure Score](/archive/blogs/office365security/mitigating-client-external-forwarding-rules-with-secure-score).
