---
title: Ajustar protección contra phishing
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
description: Los administradores pueden aprender a identificar los motivos por los que se obtuvo un mensaje de suplantación de identidad (phishing) en Microsoft 365 y qué hacer para evitar más mensajes de suplantación de identidad en el futuro.
ms.openlocfilehash: b7a68eb3ab3cf7dbb7156059416cca04d80bb3a8
ms.sourcegitcommit: 2de6e07ec55d78a5c5cf2f45732ae68acf058bcf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/05/2020
ms.locfileid: "44588445"
---
# <a name="tune-anti-phishing-protection"></a>Ajustar protección contra phishing

Aunque Microsoft 365 incluye una variedad de características antiphishing que están habilitadas de forma predeterminada, es posible que algunos mensajes de suplantación de identidad sigan teniendo acceso a sus buzones. En este tema se describe qué se puede hacer para descubrir por qué ha recibido un mensaje de suplantación de identidad (phishing) y qué se puede hacer para ajustar la configuración antiphishing en la organización de Microsoft 365 _sin empeorar los elementos por accidente_.

## <a name="first-things-first-deal-with-any-compromised-accounts-and-make-sure-you-block-any-more-phishing-messages-from-getting-through"></a>Primero lo primero: tratar con todas las cuentas comprometidas y asegurarse de que se impide el acceso a otros mensajes de suplantación de identidad

Si la cuenta de un destinatario se viera comprometida como resultado del mensaje de suplantación de identidad (phishing), siga los pasos de [respuesta a una cuenta de correo electrónico en peligro en Microsoft 365](responding-to-a-compromised-email-account.md).

Si su suscripción incluye la protección contra amenazas avanzada (ATP), puede usar la [inteligencia sobre amenazas de Office 365](office-365-ti.md) para identificar a otros usuarios que también recibieron el mensaje de suplantación de identidad (phishing). Tiene opciones adicionales para bloquear los mensajes de suplantación de identidad:

- [Vínculos seguros de ATP](set-up-atp-safe-links-policies.md)

- [Datos adjuntos seguros ATP](set-up-atp-safe-attachments-policies.md)

- [Directivas antiphishing de ATP en Microsoft 365](configure-atp-anti-phishing-policies.md). Tenga en cuenta que puede aumentar temporalmente los **umbrales de suplantación de identidad (phishing) avanzada** de la Directiva de **estándar** a **agresivo**, **más agresivo**o **más agresivo**.

Compruebe que estas características de ATP están activadas.

## <a name="report-the-phishing-message-to-microsoft"></a>Informar del mensaje de suplantación de identidad a Microsoft

Informar de los mensajes de suplantación de identidad resulta útil para ajustar los filtros que se usan para proteger a todos los clientes de Microsoft 365. Para obtener instrucciones, consulte [informes de mensajes y archivos a Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="inspect-the-message-headers"></a>Inspeccionar los encabezados del mensaje

Puede examinar los encabezados del mensaje de suplantación de identidad (phishing) para ver si hay algo que puede hacer usted mismo para evitar que lleguen más mensajes de suplantación de identidad. En otras palabras, el examen de los encabezados de los mensajes puede ayudarle a identificar cualquier configuración de su organización que sea responsable de permitir los mensajes de suplantación de identidad (phishing) en.

En concreto, debe comprobar el campo de encabezado **X-Forefront-antispam-Report** en los encabezados de mensaje para ver si hay indicios de correo no deseado o de filtrado de phish en el valor de veredicto de filtrado de correo no deseado (SFV). Los mensajes que omiten el filtrado tendrán una entrada de `SCL:-1` , lo que significa que una de las configuraciones ha permitido este mensaje mediante la anulación del correo no deseado o los veredictos que el servicio ha determinado. Para obtener más información sobre cómo obtener los encabezados de los mensajes y la lista completa de todos los encabezados de mensajes contra correo no deseado y antiphishing disponibles, vea [encabezados de mensajes de correo no deseado en Microsoft 365](anti-spam-message-headers.md).

## <a name="best-practices-to-stay-protected"></a>Procedimientos recomendados para mantener la protección

- En una base mensual, ejecute [calificación segura](../mtp/microsoft-secure-score.md) para evaluar la configuración de seguridad de la organización.

- Revise periódicamente el [Informe de inteligencia simulada](learn-about-spoof-intelligence.md) y [Configure inteligencia de identidad](set-up-anti-phishing-policies.md#spoof-settings) para **poner en cuarentena** los mensajes sospechosos en lugar de entregarlos en la carpeta de correo no deseado del usuario.

- Revise periódicamente el [Informe de estado de protección contra amenazas](view-reports-for-atp.md#threat-protection-status-report).

- Algunos clientes permiten accidentalmente los mensajes de suplantación de identidad mediante la colocación de sus propios dominios en la lista Permitir remitente o permitir dominio en las directivas contra correo no deseado. Si decide hacerlo, debe extremar las precauciones. Aunque esta configuración permitirá el acceso a algunos mensajes legítimos, también permitirá mensajes malintencionados que normalmente bloquearía el correo no deseado y los filtros de phish.

  La mejor forma de tratar con los mensajes legítimos que están bloqueados por Microsoft 365 (falsos positivos) que implican a los remitentes de su dominio es configurar completamente y por completo los registros de DMARC, DKIM y DMARC en DNS para _todos_ los dominios de correo electrónico:

  - Compruebe que el registro SPF identifica _todos los_ orígenes de correo electrónico de los remitentes de su dominio (no olvide los servicios de terceros).

  - Use error ( \- ) para asegurarse de que los sistemas de correo electrónico que están configurados para ello rechacen a los remitentes no autorizados. Puede usar [inteligencia de suplantación de identidad](learn-about-spoof-intelligence.md) para identificar a los remitentes que usan su dominio para que pueda incluir remitentes de terceros autorizados en su registro de SPF.

  Para obtener instrucciones de configuración, consulte:
  
  - [Configurar SPF para ayudar a evitar la suplantación de identidad](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

  - [Usar DKIM para validar el correo electrónico saliente enviado desde su dominio personalizado](use-dkim-to-validate-outbound-email.md)

  - [Usar DMARC para validar el correo electrónico](use-dmarc-to-validate-email.md)

- Siempre que sea posible, se recomienda entregar el correo electrónico del dominio directamente a Microsoft 365. En otras palabras, señale el registro MX del dominio de Microsoft 365 a Microsoft 365. Exchange Online Protection (EOP) puede proporcionar la mejor protección para los usuarios de la nube cuando el correo se entrega directamente a Microsoft 365. Si debe usar un sistema de protección de correo electrónico de terceros delante de EOP, use el filtrado mejorado para los conectores. Para obtener instrucciones, vea [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).

- La autenticación multifactor (MFA) es una buena forma de evitar cuentas comprometidas. Debe considerar seriamente habilitar MFA para todos los usuarios. Para un enfoque por fases, empiece por habilitar la MFA para los usuarios más confidenciales (administradores, ejecutivos, etc.) antes de habilitar MFA para todos los usuarios. Para obtener instrucciones, vea [set up multi-factor Authentication](../../admin/security-and-compliance/set-up-multi-factor-authentication.md).

- Los intrusos suelen usar las reglas de reenvío a los destinatarios externos para extraer datos. Use la información de **reglas de reenvío de buzón de correo de revisión** de la [puntuación segura de Microsoft](../mtp/microsoft-secure-score.md) para buscar e incluso impedir el reenvío de reglas a destinatarios externos. Para obtener más información, consulte [Mitigating Client external Forwarding Rules with Secure score](https://docs.microsoft.com/archive/blogs/office365security/mitigating-client-external-forwarding-rules-with-secure-score).
