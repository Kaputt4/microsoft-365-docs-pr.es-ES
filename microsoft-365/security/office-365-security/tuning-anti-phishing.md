---
title: Ajustar protección contra phishing
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.localizationpriority: medium
search.appverid: ''
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
- MET150
description: Los administradores pueden aprender a identificar las razones por las que un mensaje de suplantación de identidad (phishing) ha pasado por Microsoft 365 y cómo hacerlo para evitar más mensajes de suplantación de identidad (phishing) en el futuro.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7c39d3f4b3ee6fb98cadcd5518a81710402c1cb3
ms.sourcegitcommit: 725a92b0b1555572b306b285a0e7a7614d34e5e5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2022
ms.locfileid: "65647763"
---
# <a name="tune-anti-phishing-protection"></a>Ajustar protección contra phishing

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Aunque Microsoft 365 incluye una variedad de características anti-phishing que están habilitadas de forma predeterminada, es posible que algunos mensajes de suplantación de identidad (phishing) puedan seguir a través de los buzones de correo. En este tema se describe lo que puede hacer para descubrir por qué ha pasado un mensaje de suplantación de identidad (phishing) y lo que puede hacer para ajustar la configuración de anti-phishing en su organización de Microsoft 365 _sin que las cosas empeoren accidentalmente_.

## <a name="first-things-first-deal-with-any-compromised-accounts-and-make-sure-you-block-any-more-phishing-messages-from-getting-through"></a>Lo primero es lo primero: tratar con las cuentas en peligro y asegurarse de que impide que más mensajes de suplantación de identidad (phishing) pasen

Si la cuenta de un destinatario se vio comprometida como resultado del mensaje de phishing, siga los pasos descritos en [Responder a una cuenta de correo electrónico en peligro en Microsoft 365](responding-to-a-compromised-email-account.md).

Si la suscripción incluye Microsoft Defender para Office 365, puede usar [Office 365 Threat Intelligence](office-365-ti.md) para identificar a otros usuarios que también recibieron el mensaje de phishing. Tiene opciones adicionales para bloquear los mensajes de phishing:

- [vínculos de Caja fuerte en Microsoft Defender para Office 365](set-up-safe-links-policies.md)

- [datos adjuntos de Caja fuerte en Microsoft Defender para Office 365](set-up-safe-attachments-policies.md)

- [Directivas contra suplantación de identidad en Microsoft Defender para Office 365](configure-mdo-anti-phishing-policies.md). Tenga en cuenta que puede aumentar temporalmente los **umbrales de suplantación de identidad avanzada** en la directiva de **Estándar** a **Agresivo**, **Más agresivo** o **Más agresivo**.

Compruebe que estas características de Defender para Office 365 están activadas.

## <a name="report-the-phishing-message-to-microsoft"></a>Notificar el mensaje de suplantación de identidad a Microsoft

Informar de mensajes de suplantación de identidad es útil para ajustar los filtros que se usan para proteger a todos los clientes de Microsoft 365. Para obtener instrucciones, consulte [Notificar mensajes y archivos a Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="inspect-the-message-headers"></a>Inspección de los encabezados de mensaje

Puede examinar los encabezados del mensaje de suplantación de identidad (phishing) para ver si hay algo que pueda hacer usted mismo para evitar que aparezcan más mensajes de phishing. En otras palabras, examinar los encabezados de mensajes puede ayudarle a identificar cualquier configuración de su organización que fuera responsable de permitir los mensajes de suplantación de identidad en .

En concreto, debe comprobar el campo encabezado **X-Forefront-Antispam-Report** en los encabezados de mensaje para obtener indicaciones de filtrado omitido para correo no deseado o suplantación de identidad (phishing) en el valor de Veredicto de filtrado de correo no deseado (SFV). Los mensajes que omiten el filtrado tendrán una entrada de `SCL:-1`, lo que significa que una de sus configuraciones permitió este mensaje mediante la invalidación de los veredictos de spam o phishing determinados por el servicio. Para obtener más información sobre cómo obtener encabezados de mensaje y la lista completa de todos los encabezados de mensajes antispam y antispam disponibles, consulte [Encabezados de mensajes antispam en Microsoft 365](anti-spam-message-headers.md).

## <a name="best-practices-to-stay-protected"></a>Procedimientos recomendados para mantenerse protegido

- Cada mes, ejecute [Puntuación de seguridad](../defender/microsoft-secure-score.md) para evaluar la configuración de seguridad de su organización.

- Para los mensajes que terminan en cuarentena por error o para los mensajes que se permiten a través de, se recomienda buscar esos mensajes en [el Explorador de amenazas y las detecciones en tiempo real](threat-explorer.md). Puede buscar por remitente, destinatario o identificador de mensaje. Después de localizar el mensaje, vaya a los detalles haciendo clic en el asunto. En el caso de un mensaje en cuarentena, busque cuál era la "tecnología de detección" para que pueda usar el método adecuado para invalidar. Para obtener un mensaje permitido, busque qué directiva permitió el mensaje.

- El correo electrónico de remitentes suplantados (la dirección De del mensaje no coincide con el origen del mensaje) se clasifica como suplantación de identidad (phishing) en Defender para Office 365. A veces, la suplantación de identidad es benigna y, a veces, los usuarios no quieren que los mensajes de remitentes suplantados específicos se pongan en cuarentena. Para minimizar el impacto en los usuarios, revise periódicamente la [información de inteligencia sobre suplantación](learn-about-spoof-intelligence.md) de identidad, la pestaña **Suplantación** de identidad en la [Lista de permitidos o bloqueados](tenant-allow-block-list.md) de [inquilinos y el informe Detecciones de suplantación de identidad](view-email-security-reports.md#spoof-detections-report). Una vez que haya revisado y bloqueado remitentes suplantados y haya realizado las invalidaciones necesarias, puede estar seguro de configurar la [inteligencia de suplantación de identidad en las directivas anti phishing](set-up-anti-phishing-policies.md#spoof-settings) para **poner en cuarentena** los mensajes sospechosos en lugar de entregarlos a la carpeta correo electrónico no deseado del usuario.

- Puede repetir el paso anterior para Suplantación (dominio o usuario) en Microsoft Defender para Office 365. El informe de suplantación se encuentra en El **panel** \> **de administración de** \> amenazas **Ideas**.

- Revise periódicamente el [informe Estado de protección contra amenazas](view-reports-for-mdo.md#threat-protection-status-report).

- Algunos clientes permiten involuntariamente mensajes de suplantación de identidad mediante la colocación de sus propios dominios en la lista Permitir remitente o Permitir dominio en directivas contra correo no deseado. Aunque esta configuración permitirá algunos mensajes legítimos a través de, también permitirá mensajes malintencionados que normalmente estarían bloqueados por los filtros de spam o phishing. En lugar de permitir el dominio, debe corregir el problema subyacente.

  La mejor manera de tratar los mensajes legítimos bloqueados por Microsoft 365 (falsos positivos) que implican remitentes en su dominio es configurar completamente los registros SPF, DKIM y DMARC en DNS para _todos los_ dominios de correo electrónico:

  - Compruebe que el registro SPF identifica _todos los_ orígenes de correo electrónico de los remitentes de su dominio (no olvide servicios de terceros).

  - Use un error duro (\-todo) para asegurarse de que los sistemas de correo electrónico que están configurados para hacerlo rechazan los remitentes no autorizados. Puede usar la [información de inteligencia de](learn-about-spoof-intelligence.md) suplantación de identidad para ayudar a identificar los remitentes que usan su dominio, de modo que pueda incluir remitentes de terceros autorizados en el registro SPF.

  Para obtener instrucciones de configuración, consulte:

  - [Configurar SPF para ayudar a evitar la suplantación de identidad](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

  - [Usar DKIM para validar el correo electrónico saliente enviado desde su dominio personalizado](use-dkim-to-validate-outbound-email.md)

  - [Usar DMARC para validar el correo electrónico](use-dmarc-to-validate-email.md)

- Siempre que sea posible, te recomendamos que envíes correo electrónico para tu dominio directamente a Microsoft 365. En otras palabras, apunte el registro MX del dominio de Microsoft 365 a Microsoft 365. Exchange Online Protection (EOP) puede proporcionar la mejor protección para los usuarios en la nube cuando su correo se entrega directamente a Microsoft 365. Si debe usar un sistema de higiene de correo electrónico de terceros delante de EOP, use Filtrado mejorado para conectores. Para obtener instrucciones, consulte [Filtrado mejorado para conectores en Exchange Online](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).

- Los usuarios deben usar el [complemento Mensaje](enable-the-report-message-add-in.md) de informe o el [complemento De suplantación de identidad](enable-the-report-phish-add-in.md) de informe para informar de mensajes a Microsoft, que puede entrenar nuestro sistema. Los administradores también deben aprovechar las funcionalidades de [envío de Administración](admin-submission.md).

- La autenticación multifactor (MFA) es una buena manera de evitar cuentas en peligro. Debe considerar la posibilidad de habilitar MFA para todos los usuarios. Para un enfoque por fases, empiece por habilitar MFA para los usuarios más confidenciales (administradores, ejecutivos, etc.) antes de habilitar MFA para todos los usuarios. Para obtener instrucciones, consulte [Configuración de la autenticación multifactor](../../admin/security-and-compliance/set-up-multi-factor-authentication.md).

- Los atacantes suelen usar reglas de reenvío a destinatarios externos para extraer datos. Use la información **revisar las reglas de reenvío de buzones** en [Puntuación segura de Microsoft](../defender/microsoft-secure-score.md) para buscar e incluso impedir el reenvío de reglas a destinatarios externos. Para obtener más información, vea [Mitigating Client External Forwarding Rules with Secure Score (Mitigación de reglas de reenvío externo de cliente con puntuación segura).](/archive/blogs/office365security/mitigating-client-external-forwarding-rules-with-secure-score)
