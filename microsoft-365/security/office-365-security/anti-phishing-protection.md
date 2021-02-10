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
description: Los administradores pueden obtener información sobre las características de protección contra suplantación de identidad en Exchange Online Protection (EOP) y Microsoft Defender para Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f42ea3159dc5ed975852aaca10ce6f344b71d749
ms.sourcegitcommit: 3dc795ea862b180484f76b3eb5d046e74041252b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/10/2021
ms.locfileid: "50175640"
---
# <a name="anti-phishing-protection-in-microsoft-365"></a>Protección contra la suplantación de identidad en Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

*La suplantación* de identidad es un ataque de correo electrónico que intenta robar información confidencial en mensajes que parecen ser de remitentes legítimos o de confianza. Hay categorías específicas de suplantación de identidad. Por ejemplo:

- La suplantación de identidad **(phishing)** usa contenido específico y personalizado que se adapta específicamente a los destinatarios de destino (normalmente, después de que el atacante los reconoce).

- **La whaling** se dirige a ejecutivos u otros destinos de alto valor dentro de una organización para un efecto máximo.

- El correo electrónico empresarial en peligro **(BEC)** usa remitentes de confianza falsificados (responsables financieros, clientes, socios de confianza, etc.) para engañar a los destinatarios para aprobar pagos, transferir fondos o revelar datos de clientes.

- **El ransomware** que cifra los datos y exige el pago para descifrarlo casi siempre comienza en los mensajes de suplantación de identidad. La protección contra la suplantación de identidad no puede ayudarle a descifrar archivos cifrados, pero puede ayudar a detectar los mensajes de suplantación de identidad iniciales asociados con la campaña ransomware. Para obtener más información acerca de la recuperación de un ataque de ransomware, vea [Recuperarse de un ataque de ransomware en Microsoft 365](recover-from-ransomware.md).

Con la creciente complejidad de los ataques, incluso es difícil para los usuarios formados identificar mensajes de suplantación de identidad sofisticados. Afortunadamente, Exchange Online Protection (EOP) y las características adicionales de Microsoft Defender para Office 365 pueden ayudar.

## <a name="anti-phishing-protection-in-eop"></a>Protección contra la suplantación de identidad en EOP

EOP (es decir, organizaciones de Microsoft 365 sin Microsoft Defender para Office 365) contiene características que pueden ayudar a proteger su organización de las amenazas de suplantación de identidad:

- **Inteligencia contra la suplantación de identidad**: revisa mensajes falsificados de remitentes en dominios internos y externos y permite o bloquea el acceso de los remitentes. Para obtener más información, vea [Configurar la inteligencia de suplantación de seguridad en EOP.](learn-about-spoof-intelligence.md)

- Directivas contra la suplantación de identidad en **EOP:** activar o desactivar la inteligencia de suplantación de identidad, activar o desactivar la identificación de remitentes no autenticados en Outlook y especificar la acción para los remitentes suplantados bloqueados (mover a la carpeta o cuarentena de correo no deseado). Para obtener más información, vea [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).

- Autenticación de correo electrónico **implícita:** EOP mejora las comprobaciones de autenticación de correo electrónico estándar para el correo electrónico entrante ([SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md)y [DMARC](use-dmarc-to-validate-email.md)) con reputación del remitente, historial de remitentes, historial de destinatarios, análisis de comportamiento y otras técnicas avanzadas para ayudar a identificar remitentes falsificados. Para obtener más información, consulte [Autenticación de correo electrónico de Microsoft 365](email-validation-and-authentication.md).

## <a name="additional-anti-phishing-protection-in-microsoft-defender-for-office-365"></a>Protección contra suplantación de identidad adicional en Microsoft Defender para Office 365

Microsoft Defender para Office 365 contiene características adicionales y más avanzadas contra la suplantación de identidad:

- Directivas contra la suplantación de identidad en Microsoft Defender para **Office 365:** crear nuevas directivas personalizadas, configurar las opciones de protección contra la suplantación (proteger a los usuarios y dominios de la suplantación), la configuración de inteligencia de buzones y los umbrales de suplantación de identidad avanzados ajustables. Para obtener más información, vea [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md). Para obtener más información sobre las diferencias entre las directivas contra suplantación de identidad en EOP y las directivas contra suplantación de identidad en Defender para Office 365, vea Directivas contra suplantación de identidad en [Microsoft 365.](set-up-anti-phishing-policies.md)

- **Vistas de la** campaña: el aprendizaje automático y otras heurísticas identifican y analizan los mensajes implicados en ataques de suplantación de identidad coordinados contra todo el servicio y su organización. Para obtener más información, vea [Vistas de campaña en Microsoft Defender para Office 365.](campaigns.md)

- **Simulador de ataques:** los administradores pueden crear mensajes de suplantación de identidad falsos y enviarlos a usuarios internos como una herramienta educativa. Para obtener más información, vea [Simulador de ataques en Microsoft Defender para Office 365.](attack-simulator.md)

## <a name="other-anti-phishing-resources"></a>Otros recursos contra la suplantación de identidad

- Para los usuarios finales: [protéjase contra esquemas de suplantación de identidad (phishing) y otras formas de fraude en línea.](https://support.microsoft.com/office/be0de46a-29cd-4c59-aaaf-136cf177d593)

- [Cómo Microsoft 365 valida la dirección De para evitar la suplantación de identidad](how-office-365-validates-the-from-address.md).
