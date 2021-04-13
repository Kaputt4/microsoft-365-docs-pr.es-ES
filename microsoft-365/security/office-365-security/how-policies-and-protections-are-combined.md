---
title: Orden y prioridad de protección de correo electrónico
keywords: seguridad, malware, Microsoft 365, M365, centro de seguridad, ATP, Microsoft Defender para endpoint, ATP de Office 365, ATP de Azure
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden obtener información sobre el orden de las protecciones de la aplicación en Exchange Online Protection (EOP) y cómo el valor de prioridad en las directivas de protección determina qué directiva se aplica.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3419cba5781e7ab1042f7312c721069d88fb8767
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "51687654"
---
# <a name="order-and-precedence-of-email-protection"></a>Orden y prioridad de protección de correo electrónico

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

En organizaciones de Microsoft 365 con buzones en Exchange Online o organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online, el correo electrónico entrante puede estar marcado por varias formas de protección. Por ejemplo, las directivas contra suplantación de identidad integradas en EOP que están disponibles para todos los clientes de Microsoft 365 y las directivas contra suplantación de identidad más sólidas que están disponibles para los clientes de Microsoft Defender para Office 365. Los mensajes también pasan a través de varios exámenes de detección en busca de malware, correo no deseado, phishing, etc. Dada toda esta actividad, puede haber cierta confusión en cuanto a qué directiva se aplica.

En general, una directiva que se aplica a un mensaje se identifica en el encabezado **X-Forefront-Antispam-Report** de la propiedad **CAT (Category).** Para obtener más información, vea [Encabezados de mensajes de correo no deseado](anti-spam-message-headers.md).

Hay dos factores principales que determinan qué directiva se aplica a un mensaje:

- **La prioridad del tipo de protección de correo** electrónico: este orden no se puede configurar y se describe en la tabla siguiente:

  ****

  |Priority|Protección de correo electrónico|Categoría|Dónde administrar|
  |---|---|---|---|
  |1|Malware|CAT:MALW|[Configurar directivas antimalware en EOP](configure-anti-malware-policies.md)|
  |2|Phishing|CAT:PHSH|[Configuración de directivas contra correo no deseado en EOP](configure-your-spam-filter-policies.md)|
  |3|Correo no deseado de alta confianza|CAT:HSPM|[Configuración de directivas contra correo no deseado en EOP](configure-your-spam-filter-policies.md)|
  |4 |Suplantación|CAT:SPOOF|[Configurar la inteligencia de suplantación en EOP](learn-about-spoof-intelligence.md)|
  |5<sup>\*</sup>|Suplantación de usuario (usuarios protegidos)|UIMP|[Configurar directivas contra suplantación de identidad en Microsoft Defender para Office 365](configure-atp-anti-phishing-policies.md)|
  |6<sup>\*</sup>|Suplantación de dominio (dominios protegidos)|DIMP|[Configurar directivas contra suplantación de identidad en Microsoft Defender para Office 365](configure-atp-anti-phishing-policies.md)|
  |7 |Correo no deseado|CAT:SPM|[Configuración de directivas contra correo no deseado en EOP](configure-your-spam-filter-policies.md)|
  |8 |Masivo|CAT:BULK|[Configuración de directivas contra correo no deseado en EOP](configure-your-spam-filter-policies.md)|
  |

  <sup>\*</sup> Estas características solo están disponibles en las directivas contra suplantación de identidad en Microsoft Defender para Office 365.

- La **prioridad** de la directiva: para cada tipo de protección (antispam, antimalware, anti phishing, etc.), hay una directiva predeterminada que se aplica a todos, pero puede crear directivas personalizadas que se apliquen a usuarios específicos. Cada directiva personalizada tiene un valor de prioridad que determina el orden en que se aplican las directivas. La directiva predeterminada siempre se aplica en último lugar.

  Si un usuario se define en varias directivas del mismo tipo, solo se aplica la directiva con la prioridad más alta. Las directivas restantes de ese tipo no se evalúan para el usuario (incluida la directiva predeterminada).

Por ejemplo, considere las siguientes directivas contra suplantación de identidad en Microsoft Defender para Office 365 que se aplican a los mismos usuarios y un mensaje que se identifica como suplantación de usuario y suplantación de identidad:

  ****

  |Nombre de directiva|Priority|Suplantación de usuario|Directiva contra la suplantación|
  |---|---|---|---|
  |Directiva A|1|Activada|Desactivada|
  |Directiva B|2|Desactivada|Activada|
  |

1. El mensaje se marca y trata como suplantación de identidad, ya que la suplantación de identidad tiene una prioridad superior (4) que la suplantación de usuario (5).
2. La directiva A se aplica a los usuarios porque tiene una prioridad mayor que la directiva B.
3. Según la configuración de la directiva A, no se hace ninguna acción en el mensaje, ya que la suplantación de seguridad está desactivada en la directiva.
4. El procesamiento de directivas se detiene, por lo que la directiva B nunca se aplica a los usuarios.

Dado que es posible que los mismos usuarios se incluyan intencionadamente o sin querer en varias directivas personalizadas del mismo tipo, use las siguientes directrices de diseño para directivas personalizadas:

- Asigne una prioridad más alta a las directivas que se aplican a un número reducido de usuarios y una prioridad inferior a las directivas que se aplican a un gran número de usuarios. Recuerde que la directiva predeterminada siempre se aplica en último lugar.
- Configure las directivas de mayor prioridad para que tengan una configuración más estricta o más especializada que las directivas de prioridad inferior.
- Considere la posibilidad de usar menos directivas personalizadas (solo use directivas personalizadas para usuarios que requieran una configuración más estricta o más especializada).
