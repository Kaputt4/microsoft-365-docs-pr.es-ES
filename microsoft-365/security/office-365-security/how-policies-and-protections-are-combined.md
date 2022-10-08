---
title: Orden y prioridad de la protección por correo electrónico
keywords: security, malware, Microsoft 365, M365, security center, Microsoft 365 Defender portal, Microsoft Defender para punto de conexión, Microsoft Defender para Office 365, Microsoft Defender for Identity
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.localizationpriority: medium
ms.collection:
- m365-security
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden obtener información sobre el orden de las protecciones de la aplicación en Exchange Online Protection (EOP) y cómo el valor de prioridad de las directivas de protección determina qué directiva se aplica.
ms.subservice: mdo
ms.service: microsoft-365-security
search.appverid: met150
ms.openlocfilehash: 5bb3f1a8b15c2d6407ba09ffd2fafaa1987c010f
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68082601"
---
# <a name="order-and-precedence-of-email-protection"></a>Orden y prioridad de la protección por correo electrónico

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

En las organizaciones de Microsoft 365 con buzones en Exchange Online o organizaciones independientes de Exchange Online Protection (EOP) sin buzones de correo Exchange Online, el correo electrónico entrante puede marcarse mediante varias formas de protección. Por ejemplo, las directivas integradas contra phishing en EOP que están disponibles para todos los clientes de Microsoft 365 y las directivas anti phishing más sólidas que están disponibles para Microsoft Defender para Office 365 clientes. Los mensajes también pasan a través de varios exámenes de detección de malware, spam, phishing, etc. Dada toda esta actividad, puede haber cierta confusión en cuanto a qué directiva se aplica.

En general, una directiva que se aplica a un mensaje se identifica en el encabezado **X-Forefront-Antispam-Report** de la propiedad **CAT (Category).** Para obtener más información, vea [Encabezados de mensajes de correo no deseado](anti-spam-message-headers.md).

Hay dos factores principales que determinan qué directiva se aplica a un mensaje:

- **Orden de procesamiento del tipo de protección de correo electrónico**: este pedido no es configurable y se describe en la tabla siguiente:

  |Order|protección Email|Categoría|Dónde administrar|
  |:---:|---|---|---|
  |1|Malware|CAT:MALW|[Configuración de directivas antimalware en EOP](configure-anti-malware-policies.md)|
  |2|Phishing|CAT:PHSH|[Configuración de directivas contra correo no deseado en EOP](configure-your-spam-filter-policies.md)|
  |3|Correo no deseado de alta confianza|CAT:HSPM|[Configuración de directivas contra correo no deseado en EOP](configure-your-spam-filter-policies.md)|
  |4|Suplantación|CAT:SPOOF|[Información de inteligencia sobre suplantación de identidad en EOP](learn-about-spoof-intelligence.md)|
  |5<sup>\*</sup>|Suplantación de usuario (usuarios protegidos)|UIMP|[Configuración de directivas contra phishing en Microsoft Defender para Office 365](configure-mdo-anti-phishing-policies.md)|
  |6<sup>\*</sup>|Suplantación de dominio (dominios protegidos)|DIMP|[Configuración de directivas contra phishing en Microsoft Defender para Office 365](configure-mdo-anti-phishing-policies.md)|
  |7 |Correo no deseado|CAT:SPM|[Configuración de directivas contra correo no deseado en EOP](configure-your-spam-filter-policies.md)|
  |8 |Masivo|CAT:BULK|[Configuración de directivas contra correo no deseado en EOP](configure-your-spam-filter-policies.md)|

  <sup>\*</sup>Estas características solo están disponibles en las directivas contra suplantación de identidad en Microsoft Defender para Office 365.

- **La prioridad de la directiva**: para cada tipo de directiva (antispam, antimalware, anti-phishing, etc.), hay una directiva predeterminada que se aplica a todos, pero puede crear directivas personalizadas que se apliquen a usuarios específicos (destinatarios). Cada directiva personalizada tiene un valor de prioridad que determina el orden en el que se aplican las directivas. La directiva predeterminada siempre se aplica en último lugar.

  > [!IMPORTANT]
  > Si un destinatario se define en varias directivas del mismo tipo (antispam, anti phishing, etc.), solo se aplica al destinatario la directiva con la prioridad más alta. Las directivas restantes de ese tipo no se evalúan para el destinatario (incluida la directiva predeterminada).

Por ejemplo, considere las siguientes **directivas contra suplantación de identidad** en Microsoft Defender para Office 365 **que se aplican a los mismos usuarios** y un mensaje que se identifica como **suplantación de usuario y suplantación de identidad**:

|Nombre de la directiva|Prioridad|Suplantación de usuario|Protección contra la suplantación de identidad|
|---|:---:|:---:|:---:|
|Directiva A|1|Activada|Desactivada|
|Directiva B|2|Desactivada|Activada|

1. El mensaje se identifica como suplantación, porque la suplantación (4) se evalúa antes de la suplantación de usuario (5).
2. La directiva A se aplica primero porque tiene una prioridad mayor que la directiva B.
3. En función de la configuración de la directiva A, no se realiza ninguna acción en el mensaje porque la protección contra la suplantación está desactivada.
4. El procesamiento de directivas contra phishing se detiene para todos los destinatarios incluidos, por lo que la directiva B nunca se aplica a los destinatarios que también están en la directiva A.

Dado que los mismos usuarios podrían incluirse intencionada o involuntariamente en varias directivas del mismo tipo, use las siguientes directrices de diseño para directivas personalizadas:

- Asigne una prioridad más alta a las directivas que se aplican a un pequeño número de usuarios y una prioridad menor a las directivas que se aplican a un gran número de usuarios. Recuerde que la directiva predeterminada siempre se aplica en último lugar.
- Configure las directivas de mayor prioridad para que tengan una configuración más estricta o más especializada que las directivas de prioridad inferior.
- Considere la posibilidad de usar menos directivas personalizadas (solo use directivas personalizadas para los usuarios que requieran una configuración más estricta o más especializada).
