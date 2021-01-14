---
title: Ajustar protección contra phishing
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: ''
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
- MET150
description: Los administradores pueden aprender a identificar las razones por las que un mensaje de suplantación de identidad (phishing) ha pasado por Microsoft 365 y qué hacer para evitar más mensajes de suplantación de identidad en el futuro.
ms.openlocfilehash: 758945c64966763991bfdfba0d70a60ca1c2ddca
ms.sourcegitcommit: cc354fd54400be0ff0401f60bbe68ed975b69cda
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/14/2021
ms.locfileid: "49865049"
---
# <a name="tune-anti-phishing-protection"></a>Ajustar protección contra phishing

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Aunque Microsoft 365 incluye una variedad de características contra la suplantación de identidad que están habilitadas de forma predeterminada, es posible que algunos mensajes de suplantación de identidad aún puedan llegar a sus buzones. En este tema se describe lo que puede hacer para descubrir por qué ha pasado un mensaje de suplantación de identidad (phishing) y qué puede hacer para ajustar la configuración contra suplantación de identidad en su organización de Microsoft 365 sin que las cosas empeoren _accidentalmente._

## <a name="first-things-first-deal-with-any-compromised-accounts-and-make-sure-you-block-any-more-phishing-messages-from-getting-through"></a>Lo primero es lo primero: tratar con cuentas comprometidas y asegurarse de bloquear más mensajes de suplantación de identidad para que no se pasen.

Si la cuenta de un destinatario se ha visto comprometida como resultado del mensaje de suplantación de identidad, siga los pasos descritos en Responder a una cuenta de correo electrónico en peligro en [Microsoft 365.](responding-to-a-compromised-email-account.md)

Si su suscripción incluye Microsoft Defender para Office 365, puede usar inteligencia de amenazas de [Office 365](office-365-ti.md) para identificar otros usuarios que también recibieron el mensaje de suplantación de identidad. Tiene opciones adicionales para bloquear los mensajes de suplantación de identidad:

- [Vínculos seguros en Microsoft Defender para Office 365](set-up-atp-safe-links-policies.md)

- [Datos adjuntos seguros en Microsoft Defender para Office 365](set-up-atp-safe-attachments-policies.md)

- [Directivas contra suplantación de identidad en Microsoft Defender para Office 365](configure-atp-anti-phishing-policies.md). Tenga en cuenta que puede aumentar temporalmente los umbrales de  **suplantación** de identidad avanzada en la directiva de **Estándar** a **Agresivo,** Más agresivo o **Más agresivo.**

Compruebe que estas características de Defender para Office 365 están activadas.

## <a name="report-the-phishing-message-to-microsoft"></a>Notificar el mensaje de suplantación de identidad a Microsoft

Informar de mensajes de suplantación de identidad es útil para ajustar los filtros que se usan para proteger a todos los clientes de Microsoft 365. Para obtener instrucciones, vea [Notificar mensajes y archivos a Microsoft.](report-junk-email-messages-to-microsoft.md)

## <a name="inspect-the-message-headers"></a>Inspeccionar los encabezados de mensaje

Puede examinar los encabezados del mensaje de suplantación de identidad para ver si hay algo que puede hacer usted mismo para evitar que se puedan recibir más mensajes de suplantación de identidad. En otras palabras, examinar los encabezados de mensajes puede ayudarle a identificar cualquier configuración de su organización que fuera responsable de permitir la entrada de los mensajes de suplantación de identidad.

En concreto, debe comprobar el campo de encabezado **X-Forefront-Antispam-Report** en los encabezados de mensaje para obtener indicaciones de filtrado omitido de correo no deseado o suplantación de identidad en el valor de veredicto de filtrado de correo no deseado (SFV). Los mensajes que omiten el filtrado tendrán una entrada de , lo que significa que una de las opciones de configuración permitió que este mensaje pasara invalidando los veredictos de correo no deseado o de suplantación de identidad determinados por `SCL:-1` el servicio. Para obtener más información sobre cómo obtener encabezados de mensaje y la lista completa de todos los encabezados de mensajes contra correo electrónico no deseado y contra suplantación de identidad disponibles, consulte Encabezados de mensajes contra correo no deseado en [Microsoft 365.](anti-spam-message-headers.md)

## <a name="best-practices-to-stay-protected"></a>Procedimientos recomendados para mantenerse protegido

- Cada mes, ejecute puntuación [de seguridad](../mtp/microsoft-secure-score.md) para evaluar la configuración de seguridad de su organización.

- Para los mensajes que terminan en cuarentena por error o para los mensajes [permitidos,](threat-explorer.md)se recomienda buscar esos mensajes en el Explorador de amenazas y las detecciones en tiempo real. Puede buscar por remitente, destinatario o id. de mensaje. Después de localizar el mensaje, vaya a los detalles haciendo clic en el asunto. Para ver un mensaje en cuarentena, vea cuál era la "tecnología de detección" para poder usar el método adecuado para invalidarlo. Para obtener un mensaje permitido, vea qué directiva permitió el mensaje.

- El correo suplantado se etiqueta como suplantación de identidad en Defender para Office 365. A veces, la suplantación de nombre es benigna y, a veces, los usuarios no desean que se ponga en cuarentena. Para minimizar el impacto en los usuarios, revise periódicamente el informe [de inteligencia de suplantación de seguridad.](learn-about-spoof-intelligence.md) Una vez que haya revisado y realizado los reemplazos necesarios, puede  estar seguro de configurar la inteligencia de suplantación para poner en cuarentena los mensajes sospechosos en lugar de entregarlos a la carpeta de correo no deseado del usuario. [](set-up-anti-phishing-policies.md#spoof-settings)

- Puede repetir el paso anterior para la suplantación (dominio o usuario). El informe de suplantación se encuentra en **Información del** panel de \> **administración de** \> **amenazas.**

- Revise periódicamente el informe [de estado de protección contra amenazas.](view-reports-for-atp.md#threat-protection-status-report)

- Algunos clientes permiten accidentalmente mensajes de suplantación de identidad (phishing) colocando sus propios dominios en la lista Permitir remitente o Permitir dominio en directivas contra correo no deseado. Aunque esta configuración permitirá la entrada de algunos mensajes legítimos, también permitirá mensajes malintencionados que normalmente estarían bloqueados por los filtros de correo no deseado o de suplantación de identidad. En lugar de permitir el dominio, debe corregir el problema subyacente.

  La mejor manera de tratar los mensajes legítimos bloqueados por Microsoft 365 (falsos positivos) que implican a remitentes en  su dominio es configurar completamente los registros SPF, DKIM y DMARC en DNS para todos los dominios de correo electrónico:

  - Compruebe que el registro  de SPF identifica todos los orígenes de correo electrónico de los remitentes de su dominio (¡no olvide los servicios de terceros!).

  - Use errores (todos) para asegurarse de que los sistemas de correo electrónico configurados para hacerlo rechazan a los \- remitentes no autorizados. Puede usar la [inteligencia de](learn-about-spoof-intelligence.md) suplantación de identidad para ayudar a identificar a los remitentes que usan su dominio de modo que pueda incluir remitentes de terceros autorizados en el registro de SPF.

  Para obtener instrucciones de configuración, vea:

  - [Configurar SPF para ayudar a evitar la suplantación de identidad](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

  - [Usar DKIM para validar el correo electrónico saliente enviado desde su dominio personalizado](use-dkim-to-validate-outbound-email.md)

  - [Usar DMARC para validar el correo electrónico](use-dmarc-to-validate-email.md)

- Siempre que sea posible, se recomienda entregar el correo electrónico de su dominio directamente a Microsoft 365. En otras palabras, apunte el registro MX de su dominio de Microsoft 365 a Microsoft 365. Exchange Online Protection (EOP) puede proporcionar la mejor protección a los usuarios de la nube cuando su correo se entrega directamente a Microsoft 365. Si debe usar un sistema de higiene de correo electrónico de terceros delante de EOP, use el filtrado mejorado para conectores. Para obtener instrucciones, consulte [Filtrado mejorado para conectores en Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).

- Los usuarios deben usar el complemento [](enable-the-report-phish-add-in.md) [informar de](enable-the-report-message-add-in.md) mensajes o el complemento de suplantación de identidad de informes para notificar mensajes a Microsoft, que puede formar nuestro sistema. Los administradores también deben aprovechar las [capacidades de envío de](admin-submission.md) administrador.

- La autenticación multifactor (MFA) es una buena forma de evitar cuentas en peligro. Considere la posibilidad de habilitar MFA para todos los usuarios. Para un enfoque por fases, empiece por habilitar MFA para los usuarios más confidenciales (administradores, ejecutivos, etc.) antes de habilitar MFA para todos los usuarios. Para obtener instrucciones, [vea Configurar la autenticación multifactor.](../../admin/security-and-compliance/set-up-multi-factor-authentication.md)

- Los atacantes suelen usar reglas de reenvío a destinatarios externos para extraer datos. Use la información **de reglas de reenvío de** buzón de correo de Revisión en [puntuación](../mtp/microsoft-secure-score.md) de seguridad de Microsoft para buscar e incluso impedir el reenvío de reglas a destinatarios externos. Para obtener más información, vea [Mitigating Client External Forwarding Rules with Secure Score](https://docs.microsoft.com/archive/blogs/office365security/mitigating-client-external-forwarding-rules-with-secure-score).
