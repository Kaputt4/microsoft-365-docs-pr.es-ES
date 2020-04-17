---
title: Orden y prioridad de la protección del correo electrónico en Office 365
keywords: seguridad, malware, Microsoft 365, M365, Security Center, ATP, Microsoft defender ATP, Office 365 ATP, ATP de Azure
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: Describe el orden de aplicación de las protecciones de Office 365 y cómo el valor de prioridad en las directivas de protección determina la Directiva que se aplica.
ms.openlocfilehash: 6a95c59a5cd629b704753c6c05c9b8069d9240b1
ms.sourcegitcommit: db8702cf578b02c6fd6a2670c177b456efae4748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2020
ms.locfileid: "43537418"
---
# <a name="order-and-precedence-of-email-protection-in-office-365"></a>Orden y prioridad de la protección del correo electrónico en Office 365

En Office 365, el correo electrónico entrante es evaluado por y, por lo tanto, puede ser marcado por varias formas de protección (malware, correo no deseado, suplantación de identidad (phishing), etc.). Dada toda esta actividad, puede ser difícil determinar qué directiva se ha aplicado y en qué orden.

En general, una directiva que se aplica a un mensaje se identifica en el encabezado **X-Forefront-antispam-Report** en la propiedad **CAT (categoría)** . Para obtener más información, vea [Encabezados de mensajes de correo no deseado](anti-spam-message-headers.md).

Hay dos factores principales que determinan la Directiva que se aplica a un mensaje:

- **La prioridad del tipo de protección de correo electrónico**: este pedido no se puede configurar y se describe en la siguiente tabla:

  |||||
  |---|---|---|---|
  |**Prioridad**|**Protección de correo electrónico**|**Categoría**|**Dónde administrar**|
  |1|Malware|CAT: MALW|[Configurar directivas antimalware en Office 365](configure-anti-malware-policies.md)|
  |segundo|Phishing|CAT: PHSH|[Configuración de directivas contra correo no deseado en Office 365](configure-your-spam-filter-policies.md)|
  |3|Correo no deseado de alta confianza|CAT: HSPM|[Configuración de directivas contra correo no deseado en Office 365](configure-your-spam-filter-policies.md)|
  |4 |Suplantación|CAT: SUPLANTACIÓN DE IDENTIDAD|[Configurar inteligencia de suplantación de identidad en Office 365](learn-about-spoof-intelligence.md)|
  |5 |Correo no deseado|CAT: SPM|[Configuración de directivas contra correo no deseado en Office 365](configure-your-spam-filter-policies.md)|
  |6 |Masivo|CAT: BULK|[Configuración de directivas contra correo no deseado en Office 365](configure-your-spam-filter-policies.md)|
  |0,7<sup>\*</sup>|Suplantación de dominio (usuarios protegidos)|DIMP|[Configurar las directivas de protección contra suplantación de identidad (ATP) en Office 365](configure-atp-anti-phishing-policies.md)|
  |8,5<sup>\*</sup>|Suplantación del usuario (dominios protegidos)|UIMP|[Configurar las directivas de protección contra suplantación de identidad (ATP) en Office 365](configure-atp-anti-phishing-policies.md)|
  |

  <sup>\*</sup>Estas características solo están disponibles en las directivas contra la suplantación de identidad ATP.

- **La prioridad de la Directiva**: para cada tipo de protección (contra correo electrónico no deseado, anti-malware, antiphishing, etc.), hay una directiva predeterminada que se aplica a todos los usuarios, pero puede crear directivas personalizadas que se apliquen a usuarios específicos. Cada directiva personalizada tiene un valor de prioridad que determina el orden en el que se aplican las directivas. La directiva predeterminada siempre se aplica en último lugar.

  Si un usuario se define en varias directivas del mismo tipo, sólo se le aplica la Directiva con la prioridad más alta. El resto de las directivas de ese tipo no se evalúan para el usuario (incluida la directiva predeterminada).

Por ejemplo, considere las siguientes directivas antiphishing de ATP **que se aplican a los mismos usuarios**, y un mensaje que se identifica como suplantación de usuario e imitación:

  |||||
  |---|---|---|---|
  |**Directiva contra la suplantación de identidad ATP**|**Prioridad**|**Suplantación de usuario**|**Directiva contra la suplantación**|
  |Directiva A|1|Activada|Desactivado|
  |Directiva B|segundo|Desactivada|Activada|
  |

1. El mensaje se marca y se trata como falso, ya que la suplantación de identidad tiene una prioridad mayor (4) que la suplantación del usuario (8).
2. La Directiva A se aplica a los usuarios porque tiene una prioridad más alta que la Directiva B.
3. En función de la configuración de la Directiva A, no se lleva a cabo ninguna acción en el mensaje, ya que la suplantación de identidad está desactivada en la Directiva.
4. Se detiene el procesamiento de la Directiva, por lo que la Directiva B nunca se aplica a los usuarios.

Como es posible que los mismos usuarios se incluyan de forma intencionada o no en varias directivas personalizadas del mismo tipo, use las siguientes instrucciones de diseño para las directivas personalizadas:

- Asigne una prioridad mayor a las directivas que se aplican a un pequeño número de usuarios y una prioridad más baja a las directivas que se aplican a un gran número de usuarios. Recuerde que la directiva predeterminada siempre se aplica en último lugar.
- Configure las directivas de mayor prioridad para que tengan una configuración más estricta o más especializada que las directivas de menor prioridad.
- Considere la posibilidad de usar menos directivas personalizadas (solo use directivas personalizadas para los usuarios que requieran una configuración más estricta o más especializada).
