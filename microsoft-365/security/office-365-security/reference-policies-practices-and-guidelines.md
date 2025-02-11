---
title: Referencia Políticas, prácticas y directrices
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: ff3f140b-b005-445f-bfe0-7bc3f328aaf0
ms.collection:
- m365-security
description: Microsoft ha desarrollado varias directivas, procedimientos y ha adoptado varios procedimientos recomendados del sector para ayudar a proteger a nuestros usuarios frente a correos electrónicos abusivos, no deseados o malintencionados.
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: 8cea8a26c318c7832f28f9ffaa0a740837d5894c
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68091705"
---
# <a name="reference-policies-practices-and-guidelines"></a>Referencia: Políticas, prácticas y directrices

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Microsoft se centra en ayudarle a que disfrute de la experiencia web de usuario más confiable. Por ello, Microsoft ha desarrollado diversas políticas y procedimientos, y adoptado varias prácticas recomendadas del sector para ayudar a proteger a nuestros usuarios de correo electrónico abusivo, no deseado o malintencionado. Los remitentes que intentan enviar correo electrónico a los usuarios deben asegurarse de que comprenden por completo y siguen las instrucciones de este artículo para ayudar en este esfuerzo y ayudar a evitar posibles problemas de entrega.

Si no cumple estas políticas y directrices, es posible que nuestro equipo de soporte técnico no pueda ayudarle. Si cumple las directrices, prácticas y políticas que se presentan en este artículo y sigue experimentando problemas de entrega basados en su dirección IP de remitente, siga los pasos para enviar una solicitud de eliminación de la lista. Para obtener instrucciones, consulte [Uso del portal de deslist para quitarse de la lista de remitentes bloqueados](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).

## <a name="general-microsoft-policies"></a>Directivas generales de Microsoft

Email enviados a los usuarios de Microsoft 365 deben cumplir todas las directivas de Microsoft que rigen la transmisión y el uso de correo electrónico de Microsoft 365.

- Términos de servicios aplicables a Microsoft 365; en particular, la prohibición de usar el servicio para enviar correo no deseado o distribuir malware.

- [Acuerdo de servicios de Microsoft](https://www.microsoft.com/servicesagreement/)

## <a name="governmental-regulations"></a>Regulaciones gubernamentales

Email enviados a los usuarios de Microsoft 365 deben cumplir todas las leyes y regulaciones aplicables que rigen las comunicaciones por correo electrónico en la jurisdicción aplicable.

- [Ley estadounidense CAN-SPAM: guía de cumplimiento para empresas](https://www.ftc.gov/tips-advice/business-center/guidance/can-spam-act-compliance-guide-business)

- [Respuestas y responsabilidades de "Anular suscripción": el personal de marketing de correo electrónico debe respetar las solicitudes de "Cancelar suscripción"](https://www.lawpublish.com/ftc-emai-marketers-unsubscribe-claims.html)

## <a name="technical-guidelines"></a>Directrices técnicas

Email enviados a Microsoft 365 deben cumplir las recomendaciones aplicables enumeradas en los documentos siguientes (algunos vínculos solo están disponibles en inglés).

- [RFC 2505: Recomendaciones frente a correo electrónico no deseado para MTA de SMTP](https://www.ietf.org/rfc/rfc2505.txt)

- [RFC 2920: Extensión de servicio SMTP para la canalización de comandos](https://www.ietf.org/rfc/rfc2920.txt)

Además, los servidores de correo electrónico que se conectan a Microsoft 365 deben cumplir los siguientes requisitos:

- El remitente debe cumplir todas las normas técnicas para la transmisión de correo electrónico de Internet, conforme publica el Grupo de trabajo de ingeniería de Internet (IETF) de The Internet Society, incluidos RFC 5321, RFC 5322 y otros.

- Después de recibir un código de respuesta de error SMTP entre 500 y 599 (también conocido como respuesta permanente de no entrega o un NDR), el remitente no debe intentar volver a transmitir ese mensaje a ese destinatario.

- Después de varias respuestas de no entrega, el remitente debe dejar de intentar enviar correo electrónico a ese destinatario.

- Los mensajes no deben transmitirse a través de servidores proxy o de retransmisión de correo electrónico no seguros.

- El mecanismo para darse de baja de listas individuales o de todas las listas alojadas por el remitente debe estar claramente documentado y ser fácil de encontrar y usar por parte de los destinatarios.

- No se aceptarán conexiones de espacio IP dinámico.

- Los servidores de correo electrónico deben tener registros de DNS inversos válidos.

## <a name="reputation-management"></a>Administración de la reputación

Los remitentes, ISP y otros proveedores de servicios deben administrar activamente la reputación de sus direcciones IP salientes.

## <a name="microsoft-365-limits"></a>Límites de Microsoft 365

Los remitentes deben cumplir los límites de Microsoft 365 enumerados en [límites de Exchange Online Protection](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-limits).

## <a name="email-delivery-resources-and-organizations"></a>Organizaciones y recursos de entrega de correo electrónico

Microsoft actively works with industry bodies and service providers in order to improve the internet and email ecosystem. These organizations have published best practice documents that we support and recommend senders adhere to. This improves your ability to deliver email among several email service providers around the world.

- [Messaging Malware Mobile Anti-Abuse Working Group](https://www.m3aawg.org/)

- [Online Trust Alliance](https://www.internetsociety.org/ota/)

- [Email Sender & Provider Coalition](https://www.espcoalition.org/)

## <a name="abuse-and-spam-reporting"></a>Informar sobre abusos y correo no deseado

Para informar de correo electrónico ilegal, abusivo, no deseado o malintencionado, consulte [Informe de mensajes y archivos a Microsoft](report-junk-email-messages-to-microsoft.md). El envío de estos tipos de comunicaciones es una infracción de la directiva de Microsoft y se tomarán las medidas adecuadas en los informes confirmados.

## <a name="law-enforcement"></a>Cumplimiento de la ley

Si es miembro de un órgano de mantenimiento del orden público y quiere ayudar a Microsoft Corporation con documentación legal relacionada con Office 365 o si tiene preguntas sobre la documentación legal que ha enviado a Microsoft, llame al +(1) (425) 722-1299.
