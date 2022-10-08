---
title: Servicios para clientes que no envían correo a Microsoft 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: 19fd3e0f-8dbf-4049-a810-2c8ee6cefd48
ms.collection:
- m365-security
description: Para ayudar a mantener la confianza del usuario en el uso del correo electrónico, Microsoft ha puesto en marcha distintas políticas y tecnologías para ayudar a proteger a nuestros usuarios.
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: 428e1c0096811fa13674a47fec2cdf777642e12f
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68088473"
---
# <a name="services-for-non-customers-sending-mail-to-microsoft-365"></a>Servicios para clientes que no envían correo a Microsoft 365

El abuso de correo electrónico, correo electrónico no deseado y correos electrónicos fraudulentos (phishing) siguen sobrecargando todo el ecosistema de correo electrónico. Para ayudar a mantener la confianza del usuario en el uso del correo electrónico, Microsoft ha puesto en marcha varias directivas y tecnologías para ayudar a proteger a nuestros usuarios. Sin embargo, Microsoft entiende que el correo electrónico legítimo no debería verse afectado negativamente. Por lo tanto, hemos establecido un conjunto de servicios para ayudar a los remitentes a mejorar su capacidad de entregar correo electrónico a los usuarios de Microsoft 365 mediante la administración proactiva de su reputación de envío.

Esta información general proporciona información sobre las ventajas que proporcionamos a su organización incluso si no es cliente.

## <a name="sender-solutions"></a>Soluciones de remitente

|Servicio|Ventajas|
|---|---|
|En este contenido de la Ayuda en línea|se ofrece: <ul><li>Punto de partida para cualquier pregunta relacionada con la entrega de comunicaciones a los usuarios de EOP.</li><li>Incluye una guía en línea sencilla con nuestras directivas y requisitos.</li><li>Información general de los filtros de correo electrónico no deseado y las tecnologías de autenticación empleadas por Microsoft.</li><ul>|
|[Soporte técnico de Microsoft](#microsoft-support)|Proporciona soporte de autoayuda y escalamiento para problemas de entrega.|
|[Portal de lista de direcciones IP no deseados](#anti-spam-ip-delist-portal)|A tool to submit IP delist request. Before submitting this request it is the sender's responsibility to ensure that any further mail originating from the IP in question is not abusive or malicious.|
|[Notificación de abusos y spam relativos a correos electrónicos no deseados procedentes de Exchange Online](#abuse-and-spam-reporting-for-junk-email-originating-from-exchange-online)|Evita que el correo no deseado y otros correos no deseados se envíen desde Exchange Online y abarrotando Internet y su sistema de correo.|

## <a name="microsoft-support"></a>Soporte técnico de Microsoft

Microsoft ofrece varias opciones de soporte técnico para las personas que tienen problemas para enviar correo a los destinatarios de Microsoft 365. Le recomendamos que haga lo siguiente:

- Siga las instrucciones de cualquier informe de no entrega que reciba.

- Consulte los problemas más comunes que los no clientes encuentran en [Correo de solución de problemas enviado a Office 365](troubleshooting-mail-sent-to-office-365.md).

- Use el [portal de deslist de Microsoft 365](https://sender.office.com) para enviar una solicitud para que la dirección IP se quite de la lista del remitente bloqueado.

- Lea los [foros de la comunidad de Microsoft](https://community.office365.com/f/).

- Póngase en contacto con el cliente que está intentando enviar por correo electrónico mediante otro método y pídale que se ponga en contacto con Soporte técnico de Microsoft y abra una incidencia de soporte técnico en su nombre. En algunos casos, por motivos legales, el Soporte técnico de Microsoft debe ponerse directamente en contacto con el remitente que posee el espacio de IP que está bloqueado. Sin embargo, normalmente los no clientes no pueden abrir incidencias de soporte técnico.

  Para obtener más información acerca del Soporte técnico de Microsoft para Office 365, consulte [Soporte técnico](/office365/servicedescriptions/office-365-platform-service-description/support).

## <a name="anti-spam-ip-delist-portal"></a>Portal de lista de direcciones IP no deseados

Este es un portal de autoservicio que puede usar para quitarse de la lista de remitentes bloqueados de Microsoft 365. Use este portal si recibe un mensaje de error al intentar enviar un correo electrónico a un destinatario cuya dirección de correo electrónico está en Microsoft 365 y no cree que debería hacerlo. Para más información, consulte [Usar el portal de eliminación de la lista para quitarse de la lista de remitentes bloqueados](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).

## <a name="abuse-and-spam-reporting-for-junk-email-originating-from-exchange-online"></a>Notificación de abusos y spam relativos a correos electrónicos no deseados procedentes de Exchange Online

A veces, terceros usan Microsoft 365 para enviar correo no deseado, en violación de nuestros términos de uso y directiva. Si recibe correo electrónico no deseado de Office 365, puede informar de estos mensajes a Microsoft. Para obtener instrucciones, consulte [Notificar mensajes y archivos a Microsoft](report-junk-email-messages-to-microsoft.md).
