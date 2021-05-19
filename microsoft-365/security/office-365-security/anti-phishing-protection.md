---
title: Protección contra phishing
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 75af74b2-c7ea-4556-a912-8c48e07271d3
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- TopSMBIssues
- seo-marvel-apr2020
description: Los administradores pueden obtener información sobre las características de protección contra la suplantación de identidad en Exchange Online Protection (EOP) y Microsoft Defender para Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 290f5f7797d987fb65a99e3f9e656bfec4cf83f3
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538344"
---
# <a name="anti-phishing-protection-in-microsoft-365"></a>Protección contra suplantación de identidad en Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

*Phishing* es un ataque de correo electrónico que intenta robar información confidencial en mensajes que parecen ser de remitentes legítimos o de confianza. Hay categorías específicas de phishing. Por ejemplo:

- **La suplantación** de identidad de lanza usa contenido centrado y personalizado que está específicamente adaptado a los destinatarios dirigidos (normalmente, después del reconocimiento de los destinatarios por parte del atacante).

- **La caza de whaling** se dirige a ejecutivos u otros objetivos de alto valor dentro de una organización para obtener el máximo efecto.

- El compromiso de correo electrónico empresarial **(BEC)** usa remitentes de confianza falsificados (responsables financieros, clientes, socios de confianza, etc.) para engañar a los destinatarios para que aprueben pagos, transfieran fondos o revelen datos de clientes. Obtenga más información con [este vídeo](https://www.youtube.com/watch?v=8Kn31h9HwIQ&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=2).

- **Ransomware** que cifra los datos y exige el pago para descifrarlo casi siempre comienza en los mensajes de suplantación de identidad. La protección contra la suplantación de identidad no puede ayudarle a descifrar archivos cifrados, pero puede ayudar a detectar los mensajes de suplantación de identidad inicial asociados con la campaña de ransomware. Para obtener más información acerca de la recuperación de un ataque de ransomware, vea [Recover from a ransomware attack in Microsoft 365](recover-from-ransomware.md).

Con la creciente complejidad de los ataques, es incluso difícil para los usuarios capacitados identificar mensajes de suplantación de identidad sofisticados. Afortunadamente, Exchange Online Protection (EOP) y las características adicionales de Microsoft Defender para Office 365 pueden ayudar.

## <a name="anti-phishing-protection-in-eop"></a>Protección contra phishing en EOP

EOP (es decir, Microsoft 365 sin Microsoft Defender para Office 365) contiene características que pueden ayudar a proteger su organización de amenazas de suplantación de identidad:

- **Inteligencia** suplantada: use la información de inteligencia suplantada para revisar los remitentes suplantados detectados en mensajes de dominios externos e internos, y permitir o bloquear manualmente los remitentes detectados. Para obtener más información, vea [Spoof intelligence insight in EOP](learn-about-spoof-intelligence.md).

- Directivas contra suplantación de identidad en **EOP:** active o desactive la inteligencia de suplantación de identidad, active o desactive la identificación de remitentes no autenticados en Outlook y especifique la acción para remitentes suplantados bloqueados. Para obtener más información, vea [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).

- Permitir o bloquear remitentes suplantados en la lista de **inquilinos permitidos o bloqueados:** al invalidar el veredicto en la información  de inteligencia suplantada, el remitente suplantado se convierte en una entrada de permitir o bloquear manual que solo aparece en la pestaña Suplantación de identidad de la lista de permitidos o bloqueados del inquilino. También puede crear manualmente entradas de permitir o bloquear para remitentes suplantados antes de que los detecte la inteligencia de suplantación. Para obtener más información, vea [Manage the Tenant Allow/Block List in EOP](tenant-allow-block-list.md).

- Autenticación implícita de correo **electrónico:** EOP mejora las comprobaciones de autenticación de correo electrónico estándar para el correo electrónico entrante ([SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md)y [DMARC](use-dmarc-to-validate-email.md)) con reputación del remitente, historial de remitentes, historial de destinatarios, análisis de comportamiento y otras técnicas avanzadas para ayudar a identificar remitentes falsificados. Para obtener más información, consulte [Autenticación de correo electrónico de Microsoft 365](email-validation-and-authentication.md).

## <a name="additional-anti-phishing-protection-in-microsoft-defender-for-office-365"></a>Protección adicional contra phishing en Microsoft Defender para Office 365

Microsoft Defender para Office 365 contiene características contra phishing adicionales y más avanzadas:

- Directivas contra suplantación de identidad en **Microsoft Defender para Office 365:** Configure la configuración de protección de suplantación para remitentes de mensajes y dominios de remitente específicos, configuración de inteligencia de buzones de correo y umbrales de suplantación de identidad avanzados ajustables. Para obtener más información, vea [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md). Para obtener más información acerca de las diferencias entre las directivas contra suplantación de identidad en EOP y las directivas contra suplantación de identidad en Defender para Office 365, consulte [Anti-phishing policies in Microsoft 365](set-up-anti-phishing-policies.md).

- **Vistas de** campaña: aprendizaje automático y otras heurísticas identifican y analizan los mensajes implicados en ataques de suplantación de identidad coordinados contra todo el servicio y la organización. Para obtener más información, vea [Vistas de campaña en Microsoft Defender para Office 365](campaigns.md).

- **Simulador de ataque:** los administradores pueden crear mensajes de suplantación de identidad falsos y enviarlos a usuarios internos como una herramienta educativa. Para obtener más información, [consulte Attack Simulator in Microsoft Defender for Office 365](attack-simulator.md).

## <a name="other-anti-phishing-resources"></a>Otros recursos contra la suplantación de identidad

- Para los usuarios finales: [protéjase de esquemas de suplantación de identidad (phishing)](https://support.microsoft.com/office/be0de46a-29cd-4c59-aaaf-136cf177d593)y otras formas de fraude en línea .

- [Cómo Microsoft 365 valida la dirección From para evitar la suplantación de identidad](how-office-365-validates-the-from-address.md).
