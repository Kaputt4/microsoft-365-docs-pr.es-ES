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
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Los administradores pueden ver las preguntas más frecuentes y sus respuestas sobre la protección contra la suplantación de identidad en Exchange Online Protection (EOP).
ms.openlocfilehash: 207fa9b12c2b39571c72397abfb6a64fe992b43e
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "48199116"
---
# <a name="anti-spoofing-protection-faq"></a>Preguntas frecuentes sobre la protección contra la suplantación de identidad

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


En este artículo se proporcionan preguntas frecuentes y respuestas sobre la protección contra la suplantación de identidad para las organizaciones de Microsoft 365 con buzones en Exchange online o las organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online.

Para preguntas y respuestas sobre la protección contra correo no deseado, consulte [preguntas más frecuentes sobre protección contra correo no deseado](anti-spam-protection-faq.md).

Para preguntas y respuestas sobre la protección antimalware, consulte [preguntas más frecuentes sobre protección contra malware](anti-malware-protection-faq-eop.md)

## <a name="why-did-microsoft-choose-to-junk-unauthenticated-inbound-email"></a>¿Por qué eligió Microsoft el correo electrónico no deseado sin autenticar?

Microsoft cree que el riesgo de continuar permitiendo el correo electrónico entrante no autenticado es mayor que el riesgo de perder el correo entrante legítimo.

## <a name="does-junking-unauthenticated-inbound-email-cause-legitimate-email-to-be-marked-as-spam"></a>¿El correo electrónico entrante no autenticado no está autenticado hacer que el correo electrónico legítimo se marque como correo no deseado?

Cuando Microsoft habilitaba esta característica en 2018, se han producido algunos falsos positivos (los mensajes correctos se marcaron como no válidos). Sin embargo, con el tiempo, los remitentes se ajustan a los requisitos. El número de mensajes que se han identificado como falsificados se convirtió en despreciable en la mayoría de las rutas de correo electrónico.

Microsoft ha adoptado primero los nuevos requisitos de autenticación de correo electrónico varias semanas antes de implementarlos para los clientes. Aunque hubo complicaciones al principio, se fueron reduciendo gradualmente.

## <a name="is-spoof-intelligence-available-to-microsoft-365-customers-without-atp"></a>¿Está disponible inteligencia de suplantación de identidad para los clientes de Microsoft 365 sin ATP?

Sí. A partir del 2018 de octubre, la inteligencia de identidad está disponible para todas las organizaciones con buzones en Exchange Online y organizaciones independientes de EOP sin buzones de correo de Exchange Online.

La tecnología contra la suplantación de identidad solo estaba inicialmente disponible en la protección contra amenazas avanzada de Office 365. Por ejemplo, las suscripciones de Microsoft E5 o los complementos de ATP.

## <a name="how-can-i-report-spam-or-non-spam-messages-back-to-microsoft"></a>¿Cómo señalar mensajes de correo no deseado o correo deseado a Microsoft?

Consulte [Notificar mensajes y archivos a Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="im-an-admin-and-i-dont-know-all-of-sources-for-messages-in-my-email-domain"></a>Soy Administrador y no conozco todos los orígenes de los mensajes de mi dominio de correo electrónico.

Ve [que no conoces todos los orígenes de tu correo electrónico](email-validation-and-authentication.md#you-dont-know-all-sources-for-your-email).

## <a name="what-happens-if-i-disable-anti-spoofing-protection-for-my-organization"></a>¿Qué sucede si se deshabilita la protección contra la suplantación de identidad para mi organización?

No se recomienda deshabilitar la protección contra la suplantación de identidad. La deshabilitación de la protección permitirá que se entreguen más mensajes de suplantación de identidad y de correo no deseado en la organización. No todos los suplantadores de identidad suplantan suplantación y no todos los mensajes suplantados se pierden. Sin embargo, el riesgo será mayor.

Ahora que hay disponible [filtrado mejorado para los conectores](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) , ya no se recomienda desactivar la protección contra la suplantación de identidad cuando el correo electrónico se enruta a través de otro servicio antes de EOP.

## <a name="does-anti-spoofing-protection-mean-i-will-be-protected-from-all-phishing"></a>¿La protección contra la suplantación de identidad supone que estoy protegido contra la suplantación de identidad (phishing)?

Lamentablemente, no. Los atacantes se adaptarán a usar otras técnicas (por ejemplo, cuentas o cuentas comprometidas en los servicios de correo electrónico gratuitos). Sin embargo, la protección contra suplantación de identidad funciona mucho mejor para detectar estos otros tipos de métodos de suplantación de identidad. Las capas de protección en EOP están diseñadas y se compilan de forma conjunta.

## <a name="do-other-large-email-services-block-unauthenticated-inbound-email"></a>¿Otros servicios de correo electrónico grandes bloquean el correo electrónico entrante no autenticado?

Casi todos los servicios de correo electrónico grandes implementan las comprobaciones tradicionales de SPF, DKIM y DMARC. Algunos servicios tienen otras comprobaciones más estrictas, pero pocos en lo que se refieren a EOP para bloquear el correo no autenticado y tratarlos como mensajes falsificados. Sin embargo, la industria está cada vez más consciente de los problemas con el correo no autenticado, especialmente debido al problema de la suplantación de identidad.

## <a name="do-i-still-need-to-enable-the-advanced-spam-filter-setting-spf-record-hard-fail-_markasspamspfrecordhardfail_-if-i-enable-anti-spoofing"></a>¿Necesito habilitar la configuración avanzada de filtro de correo no deseado "registro SPF: error grave" (_MarkAsSpamSpfRecordHardFail_) si habilito la suplantación de identidad (phishing)?

No. Esta configuración de ASF ya no es necesaria. La protección contra la suplantación de identidad considera el disco duro SPF produce un error y un conjunto de criterios mucho más amplio. Si habilita la protección contra la suplantación y la opción de **Registro de SPF: error grave** (_MarkAsSpamSpfRecordHardFail_), es probable que reciba más falsos positivos.

Le recomendamos que deshabilite esta característica ya que proporciona casi ninguna ventaja para detectar correo no deseado o de suplantación de identidad (phishing) y, en cambio, generará principalmente falsos positivos. Para obtener más información, vea [configuración del filtro de correo no deseado avanzado (ASF) en EOP](advanced-spam-filtering-asf-options.md).

## <a name="does-sender-rewriting-scheme-help-fix-forwarded-email"></a>¿Ayuda el esquema de reescritura de remitentes a corregir el correo electrónico reenviado?

SRS solo soluciona parcialmente el problema del correo electrónico reenviado. Al volver a escribir el **correo SMTP desde**, SRS puede asegurarse de que el mensaje reenviado pasa SPF en el siguiente destino. Sin embargo, como la suplantación de identidad se basa en la dirección **from** en combinación con el dominio **de firma de correo** electrónico o de firma DKIM (u otras señales), no es suficiente evitar que el correo electrónico reenviado por SRS se marque como falso.
