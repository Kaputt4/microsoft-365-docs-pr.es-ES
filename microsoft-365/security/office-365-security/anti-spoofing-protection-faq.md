---
title: Preguntas más frecuentes sobre protección contra la suplantación de identidad
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
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Preguntas más frecuentes y respuestas para administradores acerca de la protección contra la suplantación de identidad en Exchange Online y Exchange Online Protection (EOP) independiente.
ms.openlocfilehash: b39e48fd57b899e6296d40ab10aac265cb4165a3
ms.sourcegitcommit: 9ed3283dd6dd959faeca5c22613f9126261b9590
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2020
ms.locfileid: "43529892"
---
# <a name="anti-spoofing-protection-faq-in-office-365"></a>Preguntas más frecuentes sobre protección contra la suplantación de identidad en Office 365

En este tema se proporcionan preguntas frecuentes y respuestas sobre la protección contra la suplantación de identidad para los clientes de Office 365 con buzones en Exchange online o los clientes independientes de Exchange Online Protection (EOP) sin buzones de correo de Exchange Online.

Para preguntas y respuestas sobre la protección contra correo no deseado, consulte [preguntas más frecuentes sobre protección contra correo no deseado](anti-spam-protection-faq.md).

Para obtener preguntas y respuestas sobre la protección antimalware, consulte [preguntas más frecuentes sobre la protección contra malware en Office 365](anti-malware-protection-faq-eop.md)

## <a name="why-did-microsoft-choose-to-junk-unauthenticated-inbound-email"></a>¿Por qué eligió Microsoft el correo electrónico no deseado sin autenticar?

Debido al impacto de los ataques de suplantación de identidad (phishing) y debido a que la autenticación de correo electrónico ha estado por encima de los 15 años, Microsoft cree que el riesgo de continuar permitiendo el correo entrante no autenticado es mayor que el riesgo de perder correo entrante.

## <a name="does-junking-unauthenticated-inbound-email-cause-legitimate-email-to-be-marked-as-spam"></a>¿El correo electrónico entrante no autenticado no está autenticado hacer que el correo electrónico legítimo se marque como correo no deseado?

Cuando Microsoft habilitaba esta característica en 2018, se han producido algunos falsos positivos (los mensajes correctos se marcaron como no válidos). Sin embargo, con el tiempo, los remitentes ajustados a los nuevos requisitos de autenticación del remitente y el número de mensajes que se identificaron de forma insignificante como falsificado se convirtió en despreciable en la mayoría de las rutas de correo electrónico.

Microsoft ha adoptado primero los nuevos requisitos de autenticación de correo electrónico varias semanas antes de implementarlos para los clientes. Aunque hubo complicaciones al principio, se fueron reduciendo gradualmente.

## <a name="is-spoof-intelligence-available-to-office-365-customers-without-atp"></a>¿Está disponible inteligencia de suplantación de identidad para los clientes de Office 365 sin ATP?

Sí. A partir del 2018 de octubre, la inteligencia de identidad está disponible para todas las organizaciones con buzones de correo de Exchange Online y organizaciones independientes de EOP sin buzones de correo de Exchange Online.

La tecnología contra la suplantación de identidad se implementó inicialmente en organizaciones que tenían suscripciones de Office 365 Enterprise E5 o el complemento de protección contra amenazas avanzada (ATP) de Office 365 para su suscripción.

## <a name="how-can-i-report-spam-or-non-spam-messages-back-to-microsoft"></a>¿Cómo señalar mensajes de correo no deseado o correo deseado a Microsoft?

Consulte [Notificar mensajes y archivos a Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="im-an-admin-and-i-dont-know-all-of-sources-for-messages-in-my-email-domain"></a>Soy Administrador y no conozco todos los orígenes de los mensajes de mi dominio de correo electrónico.

Ve [que no conoces todos los orígenes de tu correo electrónico](email-validation-and-authentication.md#you-dont-know-all-sources-for-your-email).

## <a name="what-happens-if-i-disable-anti-spoofing-protection-for-my-organization"></a>¿Qué sucede si se deshabilita la protección contra la suplantación de identidad para mi organización?

Esto no se recomienda porque estará expuesto a más intentos de mensajes de phishing y spam. No todos los casos de phishing son spoofing y no todos los spoofing pasarán sin detectarse. Pero, el riesgo será mayor que para un cliente que habilita la protección contra la suplantación.

Ahora que hay disponible un [filtrado mejorado para los conectores](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) , ya no se recomienda desactivar la protección contra la suplantación de identidad si el registro MX apunta a otro servidor o servicio antes de entregar el correo electrónico a EOP.

## <a name="does-anti-spoofing-protection-mean-i-will-be-protected-from-all-phishing"></a>¿La protección contra la suplantación de identidad supone que estoy protegido contra la suplantación de identidad (phishing)?

Lamentablemente, no. Los atacantes se adaptarán a usar otras técnicas (por ejemplo, cuentas o cuentas comprometidas en los servicios de correo electrónico gratuitos). Sin embargo, la protección contra suplantación de identidad funciona mucho mejor para detectar estos otros tipos de métodos de suplantación de identidad. Las capas de protección de Office 365 están diseñadas y se compilan de forma conjunta.

## <a name="do-other-large-email-services-block-unauthenticated-inbound-email"></a>¿Otros servicios de correo electrónico grandes bloquean el correo electrónico entrante no autenticado?

Casi todos los servicios de correo electrónico grandes implementan las comprobaciones tradicionales de SPF, DKIM y DMARC. Algunos servicios tienen otras comprobaciones más estrictas, pero pocos van tan lejos de Office 365 para bloquear el correo no autenticado y tratarlos como mensajes falsificados. Sin embargo, la industria está cada vez más consciente de los problemas con el correo no autenticado, especialmente debido al problema de la suplantación de identidad.

## <a name="do-i-still-need-to-enable-the-advanced-spam-filter-setting-spf-record-hard-fail-_markasspamspfrecordhardfail_-if-i-enable-anti-spoofing"></a>¿Necesito habilitar la configuración avanzada de filtro de correo no deseado "registro SPF: error grave" (_MarkAsSpamSpfRecordHardFail_) si habilito la suplantación de identidad (phishing)?

No. Esta configuración de ASF ya no es necesaria porque la suplantación de identidad no solo considera un error de disco duro SPF, sino un conjunto mucho más amplio de criterios. Si habilita la protección contra la suplantación y la opción de **Registro de SPF: error grave** (_MarkAsSpamSpfRecordHardFail_), es probable que reciba más falsos positivos.

Le recomendamos que deshabilite esta característica ya que proporciona casi ninguna ventaja para detectar correo no deseado o de suplantación de identidad (phishing) y, en cambio, generará principalmente falsos positivos. Para obtener más información, consulte [Configuración del filtro de correo no deseado avanzado (ASF) en Office 365](advanced-spam-filtering-asf-options.md).

## <a name="does-sender-rewriting-scheme-help-fix-forwarded-email"></a>¿Ayuda el esquema de reescritura de remitentes a corregir el correo electrónico reenviado?

SRS solo soluciona parcialmente el problema del correo electrónico reenviado. Al volver a escribir el **correo SMTP desde**, SRS puede asegurarse de que el mensaje reenviado pasa SPF en el siguiente destino. Sin embargo, como la suplantación de identidad se basa en la dirección **from** en combinación con el dominio **de firma de correo** electrónico o de firma DKIM (u otras señales), no es suficiente evitar que el correo electrónico reenviado por SRS se marque como falso.
