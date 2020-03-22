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
ms.openlocfilehash: 9f2033b1ec066c1f8501ce019b8f8c7f3748fd15
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895340"
---
# <a name="order-and-precedence-of-email-protection-in-office-365"></a>Orden y prioridad de la protección del correo electrónico en Office 365

Como usuario de Office 365, es posible que el correo electrónico entrante se marque con varias formas de protección. Por ejemplo, las directivas antiphishing de EOP integradas que están disponibles para todos los clientes de Office 365 y las directivas antiphishing de ATP más sólidas que también están disponibles para los clientes de la protección contra amenazas avanzada de Office 365. Los mensajes también pasan varios exámenes de detección de malware, correo no deseado, suplantación de identidad (phishing), etc. Teniendo en cuentan toda esta actividad, puede que haya cierta confusión con respecto a qué directiva se aplica.

En general, una directiva que se aplica a un mensaje se identifica en el encabezado **X-Forefront-antispam-Report** en la propiedad **CAT (categoría)** . Para obtener más información, vea [Encabezados de mensajes de correo no deseado](anti-spam-message-headers.md).

Hay dos factores principales que determinan la Directiva que se aplica a un mensaje:

- **La prioridad del tipo de protección de correo electrónico**: este pedido no se puede configurar y se describe en la siguiente tabla:

  |||||
  |---|---|---|---|
  |**Prioridad**|**Protección de correo electrónico**|**Categoría**|**Dónde administrar**|
  |1|Malware|CAT: MALW|[Configurar directivas antimalware en Office 365](configure-anti-malware-policies.md)|
  |segundo|Phishing|CAT: PHSH|[Configurar directivas contra correo electrónico no deseado en Office 365](configure-your-spam-filter-policies.md)|
  |3|Correo no deseado de alta confianza|CAT: HSPM|[Configurar directivas contra correo electrónico no deseado en Office 365](configure-your-spam-filter-policies.md)|
  |4 |Suplantación|CAT: SUPLANTACIÓN DE IDENTIDAD|[Configurar directivas contra suplantación de identidad y directivas contra suplantación de identidad de ATP de Office 365](set-up-anti-phishing-policies.md) <Br/><br/> [Obtener más información sobre la inteligencia de suplantación de identidad](learn-about-spoof-intelligence.md)|
  |5 |Correo no deseado|CAT: SPM|[Configurar directivas contra correo electrónico no deseado en Office 365](configure-your-spam-filter-policies.md)|
  |6 |Masivo|CAT: BULK|[Configurar directivas contra correo electrónico no deseado en Office 365](configure-your-spam-filter-policies.md)|
  |0,7<sup>\*</sup>|Suplantación de dominio|DIMP|[Configurar directivas contra suplantación de identidad y directivas contra suplantación de identidad de ATP de Office 365](set-up-anti-phishing-policies.md)|
  |8,5<sup>\*</sup>|Suplantación de usuario|UIMP|[Configurar directivas contra suplantación de identidad y directivas contra suplantación de identidad de ATP de Office 365](set-up-anti-phishing-policies.md)|
  |

  <sup>\*</sup>Estas características solo están disponibles en ATP.

- **La prioridad de la Directiva**: para cada tipo de protección (contra correo electrónico no deseado, anti-malware, antiphishing, etc.), hay una directiva predeterminada que se aplica a todos los usuarios, pero puede crear directivas personalizadas que se apliquen a usuarios específicos. Cada directiva personalizada tiene un valor de prioridad que determina el orden en el que se aplican las directivas. La directiva predeterminada siempre se aplica en último lugar.

  Si un usuario se define en varias directivas personalizadas, solo se les aplica la Directiva con la prioridad más alta. Las directivas restantes no se evalúan para el usuario (incluida la directiva predeterminada).

Por ejemplo, considere las siguientes directivas contra la suplantación de identidad (phishing) **que se aplican a los mismos usuarios**, y un mensaje que se identifica como suplantación del usuario e imitación:

  |||||
  |---|---|---|---|
  |**Directiva contra correo no deseado**|**Prioridad**|**Suplantación de usuario (ATP)**|**Contra la suplantación de identidad (EOP)**|
  |Directiva A|1|Activada|Desactivado|
  |Directiva B|segundo|Desactivada|Activada|
  |

1. El mensaje se marca y se trata como falso, ya que la suplantación de identidad tiene una prioridad mayor (4) que la suplantación del usuario (8).
2. La Directiva A se aplica a los usuarios porque tiene mayor prioridad que la prioridad B.
3. En función de la configuración de la Directiva A, no se lleva a cabo ninguna acción en el mensaje, ya que la suplantación de identidad está desactivada en la Directiva.
4. Se detiene el procesamiento de la Directiva contra correo no deseado, por lo que la Directiva B nunca se aplica a los usuarios.

Como existe la posibilidad de tener muchos usuarios en muchas directivas personalizadas del mismo tipo, tenga en cuenta las siguientes directrices de diseño para las directivas personalizadas:

- Asigne una prioridad mayor a las directivas que se aplican a un pequeño número de usuarios y una prioridad más baja a las directivas que se aplican a un gran número de usuarios. Recuerde que la directiva predeterminada siempre se aplica en último lugar.
- Configure las directivas de mayor prioridad para que tengan una configuración más estricta o más especializada que las directivas de menor prioridad.
- Considere la posibilidad de usar menos directivas personalizadas (solo use directivas personalizadas para los usuarios que requieran una configuración más estricta o más especializada).
