---
title: Administrar listas de remitentes seguros para troyanos de envío masivo de correo electrónico
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/17/2014
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: d48db4a3-9fbe-45e2-bbaa-1017ffdf96f8
ms.collection:
- M365-security-compliance
description: 'Si quiere usar listas de remitentes seguros, debe saber que Exchange Online Protection (EOP) y Outlook llevan a cabo el procesamiento de manera diferente. El servicio respeta los remitentes y los dominios seguros al inspeccionar la dirección RFC 5321.MailFrom y la dirección RFC 5322.From, mientras que Outlook agrega la dirección RFC 5322.From a la lista de remitentes seguros de un usuario. (Nota: El servicio inspecciona tanto la dirección 5321.MailFrom como la dirección 5322.From en busca de remitentes y dominios bloqueados).'
ms.openlocfilehash: 2dcfd73cc987290bbc8ca8111580a374216a843e
ms.sourcegitcommit: 5710ce729c55d95b8b452d99ffb7ea92b5cb254a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2019
ms.locfileid: "39970306"
---
# <a name="manage-safe-sender-lists-for-bulk-mailers"></a>Administrar listas de remitentes seguros para troyanos de envío masivo de correo electrónico

Si quiere usar listas de remitentes seguros, debe saber que Exchange Online Protection (EOP) y Outlook llevan a cabo el procesamiento de manera diferente. El servicio de Office 365 respeta a los remitentes y dominios seguros mediante `RFC 5321.MailFrom` la inspección de `RFC 5322.From` la dirección y la dirección, `RFC 5322.From` mientras que Outlook agrega la dirección a la lista de remitentes seguros de un usuario. (Nota: el servicio inspecciona tanto la dirección `5321.MailFrom` como `5322.From` la dirección para los remitentes y dominios bloqueados).

La `SMTP MAIL FROM` dirección, que también se conoce `RFC 5321.MailFrom address`como, es la dirección de correo electrónico que se usa para realizar comprobaciones de SPF y, si no se puede entregar el correo, la ruta de acceso a la que se entrega el mensaje resaltado. Esta es la dirección `Return-Path` de correo electrónico que se coloca de forma predeterminada en los encabezados de los mensajes, aunque es posible que el remitente designe una dirección diferente `Return-Path` .

La `From:` dirección que aparece en los encabezados del mensaje, que también `RFC 5322.From` se denomina dirección, es la dirección de correo electrónico que se muestra en el cliente de correo, como Outlook.

La mayoría de las veces, `5321.MailFrom` las `5322.From` direcciones y son las mismas. Esto es típico para la comunicación de persona a persona. No obstante, cuando el correo electrónico se envía en nombre de otra persona, las direcciones son frecuentemente diferentes. Esto generalmente ocurre con mucha frecuencia en mensajes de correo masivos.

Por ejemplo, supongamos que Blue Yonder Airlines ha contratado el viaje de Ana para enviar su publicidad por correo electrónico. Luego, obtiene un mensaje en su bandeja de entrada del remitente blueyonder@news.blueyonderairlines.com. En este ejemplo:

- La `5321.MailFrom` dirección es blueyonder.Airlines@margiestravel.com.

- La `5322.From` dirección es blueyonder@news.blueyonderairlines.com, que es lo que verá en Outlook.

Para evitar que se filtre este mensaje, puede:

- **Como usuario**: Agregue la `RFC 5322.From` dirección como un remitente seguro en Outlook.

- **Como administrador**: configurar una regla de [flujo de correo](anti-spam-protection.md#beyond-the-basics-more-ways-to-prevent-spam-in-office-365) (también denominada regla de transporte).
