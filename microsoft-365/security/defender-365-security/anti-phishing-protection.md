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
description: Los administradores pueden obtener información sobre las características de protección contra suplantación de identidad (phishing) en Exchange Online Protection (EOP) y Microsoft Defender para Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b0ca7a83e8e8d66bd58fddfc46f53df32f4f623c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51073603"
---
# <a name="anti-phishing-protection-in-microsoft-365"></a>Protección contra suplantación de identidad (phishing) en Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

*El phishing* es un ataque de correo electrónico que intenta robar información confidencial en mensajes que parecen ser de remitentes legítimos o de confianza. Hay categorías específicas de phishing. Por ejemplo:

- **La suplantación** de identidad de lanza usa contenido centrado y personalizado que está específicamente adaptado a los destinatarios dirigidos (normalmente, después del reconocimiento de los destinatarios por parte del atacante).

- **La caza de whaling** se dirige a ejecutivos u otros objetivos de alto valor dentro de una organización para obtener el máximo efecto.

- El compromiso de correo electrónico empresarial **(BEC)** usa remitentes de confianza falsificados (responsables financieros, clientes, socios de confianza, etc.) para engañar a los destinatarios para que aprueben pagos, transfieran fondos o revelen datos de clientes.

- **Ransomware** que cifra los datos y exige el pago para descifrarlo casi siempre comienza en los mensajes de suplantación de identidad. La protección contra la suplantación de identidad no puede ayudarle a descifrar archivos cifrados, pero puede ayudar a detectar los mensajes de suplantación de identidad inicial asociados con la campaña de ransomware. Para obtener más información acerca de la recuperación de un ataque de ransomware, vea [Recover from a ransomware attack in Microsoft 365](recover-from-ransomware.md).

Con la creciente complejidad de los ataques, es incluso difícil para los usuarios capacitados identificar mensajes de suplantación de identidad sofisticados. Afortunadamente, Exchange Online Protection (EOP) y las características adicionales de Microsoft Defender para Office 365 pueden ayudar.

## <a name="anti-phishing-protection-in-eop"></a>Protección contra suplantación de identidad (phishing) en EOP

EOP (es decir, organizaciones de Microsoft 365 sin Microsoft Defender para Office 365) contiene características que pueden ayudar a proteger su organización de amenazas de suplantación de identidad:

- **Inteligencia contra la suplantación de identidad**: revisa mensajes falsificados de remitentes en dominios internos y externos y permite o bloquea el acceso de los remitentes. Para obtener más información, vea [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).

- Directivas contra suplantación de identidad en **EOP:** activar o desactivar la inteligencia de suplantación de identidad, activar o desactivar la identificación de remitentes no autenticados en Outlook y especificar la acción para remitentes suplantados bloqueados (pasar a la carpeta o cuarentena de correo no deseado). Para obtener más información, vea [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).

- Autenticación implícita de correo **electrónico:** EOP mejora las comprobaciones de autenticación de correo electrónico estándar para el correo electrónico entrante ([SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md)y [DMARC](use-dmarc-to-validate-email.md)) con reputación del remitente, historial de remitentes, historial de destinatarios, análisis de comportamiento y otras técnicas avanzadas para ayudar a identificar remitentes falsificados. Para obtener más información, consulte [Autenticación de correo electrónico de Microsoft 365](email-validation-and-authentication.md).

## <a name="additional-anti-phishing-protection-in-microsoft-defender-for-office-365"></a>Protección contra suplantación de identidad adicional en Microsoft Defender para Office 365

Microsoft Defender para Office 365 contiene características adicionales y avanzadas contra la suplantación de identidad:

- Directivas contra suplantación de identidad en **Microsoft Defender para Office 365:** crear nuevas directivas personalizadas, configurar opciones contra suplantación (proteger usuarios y dominios de suplantación), configuración de inteligencia de buzones de correo y umbrales de suplantación de identidad avanzada ajustables. Para obtener más información, vea [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md). Para obtener más información acerca de las diferencias entre las directivas anti phishing en EOP y las directivas contra suplantación de identidad en Defender para Office 365, vea [Anti-phishing policies in Microsoft 365](set-up-anti-phishing-policies.md).

- **Vistas de** campaña: aprendizaje automático y otras heurísticas identifican y analizan los mensajes implicados en ataques de suplantación de identidad coordinados contra todo el servicio y la organización. Para obtener más información, vea [Vistas de campaña en Microsoft Defender para Office 365](campaigns.md).

- **Simulador de ataque:** los administradores pueden crear mensajes de suplantación de identidad falsos y enviarlos a usuarios internos como una herramienta educativa. Para obtener más información, vea [Attack Simulator in Microsoft Defender for Office 365](attack-simulator.md).

## <a name="other-anti-phishing-resources"></a>Otros recursos contra la suplantación de identidad

- Para los usuarios finales: [protéjase de esquemas de suplantación de identidad (phishing)](https://support.microsoft.com/office/be0de46a-29cd-4c59-aaaf-136cf177d593)y otras formas de fraude en línea .

- [Cómo Microsoft 365 valida la dirección De para evitar la suplantación de identidad](how-office-365-validates-the-from-address.md).
