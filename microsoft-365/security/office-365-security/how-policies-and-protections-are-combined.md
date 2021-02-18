---
title: Orden y prioridad de la protección de correo electrónico
keywords: seguridad, malware, Microsoft 365, M365, centro de seguridad, ATP, ATP de Microsoft Defender, ATP de Office 365, Azure ATP
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
description: Los administradores pueden obtener información sobre el orden de aplicación de las protecciones en Exchange Online Protection (EOP) y cómo el valor de prioridad de las directivas de protección determina qué directiva se aplica.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ec21be03280a8b7da122569d51186efc1f756a69
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286842"
---
# <a name="order-and-precedence-of-email-protection"></a>Orden y prioridad de la protección de correo electrónico

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

En organizaciones de Microsoft 365 con buzones en Exchange Online o organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online, el correo electrónico entrante puede estar marcado por varias formas de protección. Por ejemplo, las directivas contra suplantación de identidad integradas en EOP que están disponibles para todos los clientes de Microsoft 365 y las directivas anti-phishing más sólidas que están disponibles para Microsoft Defender para los clientes de Office 365. Los mensajes también pasan a través de varios exámenes de detección de malware, correo no deseado, suplantación de identidad, etc. Dada toda esta actividad, puede haber cierta confusión en cuanto a la directiva que se aplica.

En general, una directiva que se aplica a un mensaje se identifica en el encabezado **X-Forefront-Antispam-Report** en la propiedad **CAT (Category).** Para obtener más información, vea [Encabezados de mensajes de correo no deseado](anti-spam-message-headers.md).

Existen dos factores principales que determinan qué directiva se aplica a un mensaje:

- **La prioridad del tipo de protección de correo** electrónico: este orden no se puede configurar y se describe en la tabla siguiente:

  ****

  |Priority|Protección de correo electrónico|Categoría|Dónde administrar|
  |---|---|---|---|
  |1 |Malware|CAT:MALW|[Configurar directivas antimalware en EOP](configure-anti-malware-policies.md)|
  |2 |Phishing|CAT:PHSH|[Configuración de directivas contra correo no deseado en EOP](configure-your-spam-filter-policies.md)|
  |3 |Correo no deseado de alta confianza|CAT:HSPM|[Configuración de directivas contra correo no deseado en EOP](configure-your-spam-filter-policies.md)|
  |4 |Suplantación|CAT:SPOOF|[Configurar la inteligencia de suplantación de seguridad en EOP](learn-about-spoof-intelligence.md)|
  |5<sup>\*</sup>|Suplantación de usuario (usuarios protegidos)|UIMP|[Configurar directivas contra la suplantación de identidad en Microsoft Defender para Office 365](configure-atp-anti-phishing-policies.md)|
  |6<sup>\*</sup>|Suplantación de dominio (dominios protegidos)|DIMP|[Configurar directivas contra la suplantación de identidad en Microsoft Defender para Office 365](configure-atp-anti-phishing-policies.md)|
  |7 |Correo no deseado|CAT:SPM|[Configuración de directivas contra correo no deseado en EOP](configure-your-spam-filter-policies.md)|
  |8 |Masivo|CAT:BULK|[Configuración de directivas contra correo no deseado en EOP](configure-your-spam-filter-policies.md)|
  |

  <sup>\*</sup> Estas características solo están disponibles en las directivas contra suplantación de identidad en Microsoft Defender para Office 365.

- La prioridad de la **directiva:** para cada tipo de protección (correo no deseado, antimalware, anti-phishing, etc.), hay una directiva predeterminada que se aplica a todos los usuarios, pero puede crear directivas personalizadas que se apliquen a usuarios específicos. Cada directiva personalizada tiene un valor de prioridad que determina el orden en que se aplican las directivas. La directiva predeterminada siempre se aplica en último lugar.

  Si un usuario se define en varias directivas del mismo tipo, solo se le aplica la directiva con la prioridad más alta. Las directivas restantes de ese tipo no se evalúan para el usuario (incluida la directiva predeterminada).

Por ejemplo, considere las siguientes directivas contra suplantación de identidad en Microsoft Defender para Office 365 que se aplican a los mismos usuarios y un mensaje que se identifica como suplantación de identidad de usuario y suplantación de identidad:

  ****

  |Nombre de directiva|Priority|Suplantación de usuario|Directiva contra la suplantación|
  |---|---|---|---|
  |Directiva A|1 |Activada|Desactivada|
  |Directiva B|2 |Desactivada|Activada|
  |

1. El mensaje se marca y se trata como suplantación de identidad, ya que la suplantación de identidad tiene una prioridad mayor (4) que la suplantación de usuario (5).
2. La directiva A se aplica a los usuarios porque tiene una prioridad mayor que la directiva B.
3. En función de la configuración de la directiva A, no se toma ninguna acción en el mensaje, porque la protección contra la suplantación está desactivada en la directiva.
4. El procesamiento de directivas se detiene, por lo que la directiva B nunca se aplica a los usuarios.

Dado que es posible que los mismos usuarios se incluyan intencionadamente o sin querer en varias directivas personalizadas del mismo tipo, use las siguientes directrices de diseño para las directivas personalizadas:

- Asigne una prioridad más alta a las directivas que se aplican a un número reducido de usuarios y una prioridad inferior a las directivas que se aplican a un gran número de usuarios. Recuerde que la directiva predeterminada siempre se aplica en último lugar.
- Configure las directivas de mayor prioridad para que tengan una configuración más estricta o más especializada que las directivas de menor prioridad.
- Considere la posibilidad de usar menos directivas personalizadas (solo use directivas personalizadas para los usuarios que requieran una configuración más estricta o más especializada).
