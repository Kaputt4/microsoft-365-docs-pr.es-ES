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
description: Los administradores pueden ver las preguntas más frecuentes y sus respuestas sobre la protección contra la suplantación en Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d2d307d201af8ad09a4faf7a865a29da8942bdf8
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288914"
---
# <a name="anti-spoofing-protection-faq"></a>Preguntas frecuentes sobre la protección contra la suplantación de identidad

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

En este artículo se proporcionan preguntas y respuestas más frecuentes sobre la protección contra la suplantación de documentos para organizaciones de Microsoft 365 con buzones en Exchange Online o organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online.

Para obtener preguntas y respuestas acerca de la protección contra correo no deseado, consulte preguntas más frecuentes sobre protección [contra correo no deseado.](anti-spam-protection-faq.md)

Para obtener preguntas y respuestas acerca de la protección antimalware, vea preguntas más frecuentes sobre protección [antimalware](anti-malware-protection-faq-eop.md)

## <a name="why-did-microsoft-choose-to-junk-unauthenticated-inbound-email"></a>Why did Microsoft choose to junk unauthenticated inbound email?

Microsoft cree que el riesgo de seguir permitir el correo electrónico entrante no autenticado es mayor que el riesgo de perder el correo electrónico entrante legítimo.

## <a name="does-junking-unauthenticated-inbound-email-cause-legitimate-email-to-be-marked-as-spam"></a>¿El correo electrónico entrante no autenticado no autenticado hace que el correo electrónico legítimo se marque como correo no deseado?

Cuando Microsoft habilitó esta característica en 2018, ocurrieron algunos falsos positivos (los mensajes buenos se marcaron como negativos). Sin embargo, con el tiempo, los remitentes se ajustaron a los requisitos. El número de mensajes que se identificaron erróneamente como suplantados se convirtió en insignificante para la mayoría de las rutas de correo electrónico.

Microsoft adoptó por primera vez los nuevos requisitos de autenticación de correo electrónico varias semanas antes de implementarlo en los clientes. Aunque hubo complicaciones al principio, se fueron reduciendo gradualmente.

## <a name="is-spoof-intelligence-available-to-microsoft-365-customers-without-defender-for-office-365"></a>¿La inteligencia contra la suplantación está disponible para los clientes de Microsoft 365 sin Defender para Office 365?

Sí. A partir de octubre de 2018, la inteligencia de suplantación de documentos está disponible para todas las organizaciones con buzones en Exchange Online y para organizaciones EOP independientes sin buzones de Exchange Online.

## <a name="how-can-i-report-spam-or-non-spam-messages-back-to-microsoft"></a>¿Cómo señalar mensajes de correo no deseado o correo deseado a Microsoft?

Consulte [Notificar mensajes y archivos a Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="im-an-admin-and-i-dont-know-all-of-sources-for-messages-in-my-email-domain"></a>Soy administrador y no sé todos los orígenes de mensajes en mi dominio de correo electrónico.

Vea [Que no conoce todos los orígenes de su correo electrónico.](email-validation-and-authentication.md#you-dont-know-all-sources-for-your-email)

## <a name="what-happens-if-i-disable-anti-spoofing-protection-for-my-organization"></a>¿Qué sucede si deshabilito la protección contra la suplantación de mi organización?

No se recomienda deshabilitar la protección contra la suplantación. Deshabilitar la protección permitirá que se entreguen más mensajes de suplantación de identidad y correo no deseado en la organización. No todo el phishing es suplantación de identidad y no se pierden todos los mensajes suplantados. Sin embargo, el riesgo será mayor.

Ahora que el filtrado mejorado para conectores está disponible, ya no [recomendamos](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) desactivar la protección contra la suplantación cuando el correo electrónico se enruta a través de otro servicio antes de EOP.

## <a name="does-anti-spoofing-protection-mean-i-will-be-protected-from-all-phishing"></a>¿Significa la protección contra la suplantación de identidad que me protegeré de toda suplantación de identidad?

Desafortunadamente, no. Los atacantes se adaptarán para usar otras técnicas (por ejemplo, cuentas o cuentas comprometidas en servicios de correo electrónico gratuitos). Sin embargo, la protección contra suplantación de identidad funciona mucho mejor para detectar estos otros tipos de métodos de suplantación de identidad. Las capas de protección de EOP están diseñadas conjuntamente y se crean unas sobre otras.

## <a name="do-other-large-email-services-block-unauthenticated-inbound-email"></a>¿Otros servicios de correo electrónico grandes bloquean el correo electrónico entrante no autenticado?

Casi todos los servicios de correo electrónico grandes implementan comprobaciones tradicionales de SPF, DKIM y DMARC. Algunos servicios tienen otras comprobaciones más estrictas, pero pocos van tan lejos como EOP para bloquear el correo electrónico no autenticado y tratarlos como mensajes suplantados. Sin embargo, el sector es cada vez más consciente de los problemas con el correo electrónico no autenticado, especialmente debido al problema de la suplantación de identidad.

## <a name="do-i-still-need-to-enable-the-advanced-spam-filter-setting-spf-record-hard-fail-_markasspamspfrecordhardfail_-if-i-enable-anti-spoofing"></a>¿Necesito habilitar la configuración del filtro de correo no deseado avanzado "Registro SPF: error" (_MarkAsSpamSpfRecordHardFail_) si se habilita la protección contra la suplantación de documentos?

No. Esta configuración de ASF ya no es necesaria. La protección contra la suplantación considera tanto errores de SPF como un conjunto mucho más amplio de criterios. Si habilita la protección contra la suplantación y la opción de **Registro de SPF: error grave** (_MarkAsSpamSpfRecordHardFail_), es probable que reciba más falsos positivos.

Le recomendamos que deshabilite esta característica, ya que no proporciona casi ninguna ventaja adicional para detectar correo no deseado o mensajes de suplantación de identidad y, en su lugar, generaría principalmente falsos positivos. Para obtener más información, vea configuración del filtro de correo no [deseado avanzado (ASF) en EOP.](advanced-spam-filtering-asf-options.md)

## <a name="does-sender-rewriting-scheme-help-fix-forwarded-email"></a>¿Ayuda el esquema de reescritura de remitentes a corregir el correo electrónico reenviado?

SRS solo soluciona parcialmente el problema del correo electrónico reenviado. Al reescribir SMTP **MAIL FROM**, SRS puede garantizar que el mensaje reenviado pase SPF en el siguiente destino. Sin embargo, dado que la protección contra la suplantación se basa en la dirección **De** en combinación con el dominio de firma **MAIL FROM** o DKIM (u otras señales), no es suficiente para evitar que el correo electrónico reenviado de SRS se marque como suplantado.
