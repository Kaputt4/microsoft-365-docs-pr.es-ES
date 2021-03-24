---
title: Preguntas frecuentes sobre la protección contra la suplantación de identidad
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Los administradores pueden ver preguntas y respuestas más frecuentes sobre la protección contra la suplantación en Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a5843ee7f791fbc2c37914194b153fdd05866d0a
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51073576"
---
# <a name="anti-spoofing-protection-faq"></a>Preguntas frecuentes sobre la protección contra la suplantación de identidad

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

En este artículo se proporcionan preguntas y respuestas más frecuentes sobre la protección contra la suplantación de dominio para organizaciones de Microsoft 365 con buzones en Exchange Online o organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online.

Para obtener preguntas y respuestas sobre la protección contra correo no deseado, consulte Preguntas más frecuentes sobre protección [contra correo no deseado](anti-spam-protection-faq.md).

Para obtener preguntas y respuestas sobre la protección antimalware, consulta Preguntas más frecuentes sobre protección [contra malware](anti-malware-protection-faq-eop.md)

## <a name="why-did-microsoft-choose-to-junk-unauthenticated-inbound-email"></a>¿Por qué Microsoft optó por correo electrónico entrante no autenticado no autenticado?

Microsoft cree que el riesgo de seguir permitir el correo electrónico entrante no autenticado es mayor que el riesgo de perder el correo electrónico entrante legítimo.

## <a name="does-junking-unauthenticated-inbound-email-cause-legitimate-email-to-be-marked-as-spam"></a>¿El correo electrónico entrante no autenticado no autenticado hace que el correo electrónico legítimo se marque como correo no deseado?

Cuando Microsoft ha habilitado esta característica en 2018, se han producido algunos falsos positivos (los mensajes buenos se marcaron como negativos). Sin embargo, con el tiempo, los remitentes se ajustaron a los requisitos. El número de mensajes que se identificaron erróneamente como suplantados se volvió insignificante para la mayoría de las rutas de correo electrónico.

Microsoft adoptó por primera vez los nuevos requisitos de autenticación de correo electrónico varias semanas antes de implementarlo en los clientes. Aunque hubo complicaciones al principio, se fueron reduciendo gradualmente.

## <a name="is-spoof-intelligence-available-to-microsoft-365-customers-without-defender-for-office-365"></a>¿La inteligencia de suplantación está disponible para los clientes de Microsoft 365 sin Defender para Office 365?

Sí. A partir de octubre de 2018, la inteligencia de suplantación está disponible para todas las organizaciones con buzones en Exchange Online y organizaciones EOP independientes sin buzones de Exchange Online.

## <a name="how-can-i-report-spam-or-non-spam-messages-back-to-microsoft"></a>¿Cómo señalar mensajes de correo no deseado o correo deseado a Microsoft?

Consulte [Notificar mensajes y archivos a Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="im-an-admin-and-i-dont-know-all-of-sources-for-messages-in-my-email-domain"></a>Soy administrador y no sé todos los orígenes de mensajes en mi dominio de correo electrónico.

Vea [You don't know all sources for your email](email-validation-and-authentication.md#you-dont-know-all-sources-for-your-email).

## <a name="what-happens-if-i-disable-anti-spoofing-protection-for-my-organization"></a>¿Qué sucede si deshabilito la protección contra la suplantación de mi organización?

No se recomienda deshabilitar la protección contra la suplantación. Deshabilitar la protección permitirá que se entreguen más mensajes de suplantación de identidad y correo no deseado en la organización. No todo el phishing es suplantación de identidad y no se pierden todos los mensajes suplantados. Sin embargo, el riesgo será mayor.

Ahora que el filtrado mejorado para conectores está disponible, ya no [recomendamos](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) desactivar la protección contra la suplantación cuando el correo electrónico se enruta a través de otro servicio antes de EOP.

## <a name="does-anti-spoofing-protection-mean-i-will-be-protected-from-all-phishing"></a>¿La protección contra la suplantación significa que voy a estar protegido de todo el phishing?

Desafortunadamente, no. Los atacantes se adaptarán para usar otras técnicas (por ejemplo, cuentas comprometidas o cuentas en servicios de correo electrónico gratuitos). Sin embargo, la protección contra suplantación de identidad (phishing) funciona mucho mejor para detectar estos otros tipos de métodos de suplantación de identidad. Las capas de protección de EOP están diseñadas funcionan juntas y se crean unas sobre otras.

## <a name="do-other-large-email-services-block-unauthenticated-inbound-email"></a>¿Otros servicios de correo electrónico grandes bloquean el correo electrónico entrante no autenticado?

Casi todos los servicios de correo electrónico grandes implementan comprobaciones tradicionales de SPF, DKIM y DMARC. Algunos servicios tienen otras comprobaciones más estrictas, pero pocos van tan lejos como EOP para bloquear el correo electrónico no autenticado y tratarlos como mensajes suplantados. Sin embargo, el sector es cada vez más consciente de los problemas con el correo electrónico no autenticado, especialmente debido al problema de phishing.

## <a name="do-i-still-need-to-enable-the-advanced-spam-filter-setting-spf-record-hard-fail-_markasspamspfrecordhardfail_-if-i-enable-anti-spoofing"></a>¿Todavía necesito habilitar la configuración de filtro de correo no deseado avanzado "Registro SPF: error duro" (_MarkAsSpamSpfRecordHardFail_) si se habilita la suplantación de seguridad?

No. Esta configuración de ASF ya no es necesaria. La protección contra la suplantación considera que el SPF no funciona correctamente y un conjunto de criterios mucho más amplio. Si habilita la protección contra la suplantación y la opción de **Registro de SPF: error grave** (_MarkAsSpamSpfRecordHardFail_), es probable que reciba más falsos positivos.

Le recomendamos que deshabilite esta característica, ya que no proporciona casi ninguna ventaja adicional para detectar correo no deseado o mensajes de suplantación de identidad (phishing) y, en su lugar, generaría principalmente falsos positivos. Para obtener más información, [vea Advanced Spam Filter (ASF) settings in EOP](advanced-spam-filtering-asf-options.md).

## <a name="does-sender-rewriting-scheme-help-fix-forwarded-email"></a>¿Ayuda el esquema de reescritura del remitente a corregir el correo electrónico reenviado?

SRS solo soluciona parcialmente el problema del correo electrónico reenviado. Al volver a escribir smtp **mail from**, SRS puede asegurarse de que el mensaje reenviado pasa SPF en el siguiente destino. Sin embargo, dado que la anti suplantación se basa en la dirección **From** en combinación con el dominio de firma **MAIL FROM** o DKIM (u otras señales), no basta con impedir que el correo electrónico reenviado de SRS se marque como suplantado.