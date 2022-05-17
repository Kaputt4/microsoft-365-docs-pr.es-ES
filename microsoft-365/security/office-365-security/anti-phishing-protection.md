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
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: 75af74b2-c7ea-4556-a912-8c48e07271d3
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- TopSMBIssues
- seo-marvel-apr2020
description: Los administradores pueden obtener información sobre las características de protección contra phishing en Exchange Online Protection (EOP) y Microsoft Defender para Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8d62d2a32342aa6d409e49d790af717b1ccf7d61
ms.sourcegitcommit: 9255a7e8b398f92d8dae09886ae95dc8577bf29a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2022
ms.locfileid: "65438759"
---
# <a name="anti-phishing-protection-in-microsoft-365"></a>Protección contra suplantación de identidad en Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

*Phishing* es un ataque de correo electrónico que intenta robar información confidencial en mensajes que parecen ser de remitentes legítimos o de confianza. Hay categorías específicas de phishing. Por ejemplo:

- **La suplantación de identidad (phishing** ) de Spear usa contenido personalizado y centrado que se adapta específicamente a los destinatarios de destino (normalmente, después del reconocimiento de los destinatarios por parte del atacante).

- **El phishing de altos cargos** se dirige a ejecutivos u otros objetivos de alto valor dentro de una organización para obtener el máximo efecto.

- **El compromiso por correo electrónico empresarial (BEC)** usa remitentes de confianza falsificados (responsables financieros, clientes, asociados de confianza, etc.) para engañar a los destinatarios para que aprueben pagos, transfieran fondos o revelen datos de clientes. Obtenga más información con [este vídeo](https://www.youtube.com/watch?v=8Kn31h9HwIQ&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=2).

- **Ransomware** que cifra los datos y exige el pago para descifrarlos casi siempre comienza en los mensajes de phishing. La protección contra la suplantación de identidad no puede ayudarle a descifrar archivos cifrados, pero puede ayudar a detectar los mensajes iniciales de suplantación de identidad (phishing) asociados a la campaña de ransomware. Para obtener más información sobre cómo recuperarse de un ataque de ransomware, vea [Recuperarse de un ataque de ransomware en Microsoft 365](recover-from-ransomware.md).

Con la creciente complejidad de los ataques, incluso es difícil que los usuarios entrenados identifiquen mensajes sofisticados de phishing. Afortunadamente, Exchange Online Protection (EOP) y las características adicionales de Microsoft Defender para Office 365 pueden ayudar.

## <a name="anti-phishing-protection-in-eop"></a>Protección contra phishing en EOP

EOP (es decir, Microsoft 365 organizaciones sin Microsoft Defender para Office 365) contiene características que pueden ayudar a proteger su organización frente a amenazas de suplantación de identidad (phishing):

- **Inteligencia de suplantación** de identidad: use la información de inteligencia de suplantación de identidad para revisar los remitentes suplantados detectados en los mensajes de dominios externos e internos, y permitir o bloquear manualmente los remitentes detectados. Para obtener más información, consulte [Información de inteligencia contra la suplantación de identidad en EOP](learn-about-spoof-intelligence.md).

- **Directivas contra suplantación de identidad (phishing) en EOP**: active o desactive la inteligencia de suplantación de identidad, active o desactive los indicadores de remitente no autenticados en Outlook y especifique la acción para los remitentes falsificados bloqueados. Para obtener más información, consulte [Configuración de directivas contra suplantación de identidad en EOP](configure-anti-phishing-policies-eop.md).

- **Permitir o bloquear remitentes a los que se les ha suplantado la identidad en la lista de permitidos y bloqueados del espacio empresarial**: al invalidar el veredicto en la información de inteligencia contra la suplantación de identidad, el remitente a que se la ha suplantado la identidad se convierte en una entrada manual de permitido o bloqueado que solo aparece en la pestaña **Suplantación de identidad** en la lista de permitidos o bloqueados del espacio empresarial. También puede crear entradas de permitidos o bloqueados manualmente para remitentes de suplantación de identidad antes de que la inteligencia contra la suplantación de identidad los detecte. Para obtener más información, consulte [Administrar la lista de permitidos y bloqueados del espacio empresarial en EOP](tenant-allow-block-list.md).

- **Autenticación implícita de correo electrónico**: EOP mejora las comprobaciones de autenticación de correo electrónico estándar para el correo electrónico entrante ([SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md) y [DMARC](use-dmarc-to-validate-email.md) con reputación del remitente, historial de remitentes, historial de destinatarios, análisis de comportamiento y otras técnicas avanzadas para ayudar a identificar remitentes falsificados. Para obtener más información, consulte [Autenticación de correo electrónico de Microsoft 365](email-validation-and-authentication.md).

## <a name="additional-anti-phishing-protection-in-microsoft-defender-for-office-365"></a>Protección adicional contra phishing en Microsoft Defender para Office 365

Microsoft Defender para Office 365 contiene características contra phishing adicionales y más avanzadas:

- **Directivas contra suplantación de identidad en Microsoft Defender para Office 365**: configure la configuración de protección de suplantación para remitentes y dominios de remitente de mensajes específicos, opciones de inteligencia de buzones y umbrales de suplantación de identidad avanzados ajustables. Para obtener más información, consulte [Configuración de directivas contra suplantación de identidad en Microsoft Defender para Office 365](configure-mdo-anti-phishing-policies.md). Para obtener más información sobre las diferencias entre las directivas anti phishing en EOP y las directivas contra phishing en Defender para Office 365, consulte [Directivas contra suplantación de identidad en Microsoft 365](set-up-anti-phishing-policies.md).
- **Vistas de campaña**: El aprendizaje automático y otras heurísticas identifican y analizan los mensajes implicados en ataques de suplantación de identidad (phishing) coordinados contra todo el servicio y su organización. Para obtener más información, consulte [Vistas de campaña en Microsoft Defender para Office 365](campaigns.md).
- **Entrenamiento de simulación de ataques**: los administradores pueden crear mensajes de suplantación de identidad falsos y enviarlos a usuarios internos como una herramienta de educación. Para obtener más información, consulte [Simulación de un ataque de suplantación de identidad (phishing).](attack-simulation-training.md)

## <a name="other-anti-phishing-resources"></a>Otros recursos contra la suplantación de identidad

- Para los usuarios finales: [protéjase de los esquemas de suplantación de identidad (phishing) y otras formas de fraude en línea](https://support.microsoft.com/office/be0de46a-29cd-4c59-aaaf-136cf177d593).

- [Cómo Microsoft 365 valida la dirección Desde para evitar la suplantación de identidad (phishing](how-office-365-validates-the-from-address.md)).
