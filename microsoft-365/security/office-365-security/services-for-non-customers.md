---
title: Servicios para no clientes que envían correo a Microsoft 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 19fd3e0f-8dbf-4049-a810-2c8ee6cefd48
ms.collection:
- M365-security-compliance
description: Para ayudar a mantener la confianza del usuario en el uso del correo electrónico, Microsoft ha puesto en marcha distintas políticas y tecnologías para ayudar a proteger a nuestros usuarios.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3213cae1b04b3f1a1b861e8f2cfc698576013546
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2021
ms.locfileid: "51207370"
---
# <a name="services-for-non-customers-sending-mail-to-microsoft-365"></a>Servicios para no clientes que envían correo a Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


El abuso de correo electrónico, correo electrónico no deseado y correos electrónicos fraudulentos (phishing) siguen sobrecargando todo el ecosistema de correo electrónico. Para ayudar a mantener la confianza de los usuarios en el uso del correo electrónico, Microsoft ha puesto en marcha varias directivas y tecnologías para ayudar a proteger a nuestros usuarios. Sin embargo, Microsoft entiende que el correo electrónico legítimo no debería verse afectado negativamente. Por lo tanto, hemos establecido un conjunto de servicios para ayudar a los remitentes a mejorar su capacidad para entregar correo electrónico a Microsoft 365 usuarios mediante la administración proactiva de su reputación de envío.

Esta introducción proporciona información sobre las ventajas que proporcionamos a su organización incluso si no es cliente.

## <a name="sender-solutions"></a>Soluciones de remitente

****

|Servicio|Ventajas|
|---|---|
|En este contenido de la Ayuda en línea|se ofrece: <ul><li>Un punto de partida para cualquier pregunta relacionada con la entrega de comunicaciones a los usuarios de EOP.</li><li>Incluye una guía en línea sencilla con nuestras directivas y requisitos.</li><li>Información general sobre los filtros de correo no deseado y las tecnologías de autenticación empleadas por Microsoft.</li><ul>|
|[Soporte técnico de Microsoft](#microsoft-support)|Proporciona soporte de autoayuda y escalamiento para problemas de entrega.|
|[Portal de lista ip contra correo no deseado](#anti-spam-ip-delist-portal)|Una herramienta para enviar solicitudes de eliminación de IP de la lista. Antes de enviar esta solicitud, es responsabilidad del remitente asegurarse de que cualquier otro mensaje procedente de la dirección IP en cuestión no es abusivo ni malintencionado.|
|[Notificación de abusos y spam relativos a correos electrónicos no deseados procedentes de Exchange Online](#abuse-and-spam-reporting-for-junk-email-originating-from-exchange-online)|Evita que el correo no deseado y otros correos no deseados se envíen Exchange Online y abarrote Internet y su sistema de correo.|
|

## <a name="microsoft-support"></a>Soporte técnico de Microsoft

Microsoft ofrece varias opciones de soporte técnico para las personas que tienen problemas para enviar correo a Microsoft 365 destinatarios. Le recomendamos que haga lo siguiente:

- Siga las instrucciones de cualquier informe de no entrega que reciba.

- Consulte los problemas más comunes que los no clientes encuentran en [Correo de solución de problemas enviado a Office 365](troubleshooting-mail-sent-to-office-365.md).

- Use el [Microsoft 365 de deslist para](https://sender.office.com) enviar una solicitud para que se quite la IP de la lista del remitente bloqueado.

- Lea los [foros de la comunidad de Microsoft](https://community.office365.com/f/).

- Póngase en contacto con el cliente que está intentando enviar por correo electrónico con otro método y pídale que se puso en contacto con el Soporte técnico de Microsoft y abra un vale de soporte técnico en su nombre. En algunos casos, por motivos legales, el Soporte técnico de Microsoft debe ponerse directamente en contacto con el remitente que posee el espacio de IP que está bloqueado. Sin embargo, normalmente los no clientes no pueden abrir incidencias de soporte técnico.

  Para obtener más información acerca del Soporte técnico de Microsoft para Office 365, consulte [Soporte técnico](/office365/servicedescriptions/office-365-platform-service-description/support).

## <a name="anti-spam-ip-delist-portal"></a>Portal de lista ip contra correo no deseado

Este es un portal de autoservicio que puede usar para quitarse de la lista Microsoft 365 remitentes bloqueados. Use este portal si recibe un mensaje de error al intentar enviar un correo electrónico a un destinatario cuya dirección de correo electrónico está en Microsoft 365 y no cree que debería estarlo. Para más información, consulte [Usar el portal de eliminación de la lista para quitarse de la lista de remitentes bloqueados](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).

## <a name="abuse-and-spam-reporting-for-junk-email-originating-from-exchange-online"></a>Notificación de abusos y spam relativos a correos electrónicos no deseados procedentes de Exchange Online

A veces, Microsoft365 es usado por terceros para enviar correo electrónico no deseado, en violación de nuestros términos de uso y directiva. Si recibe algún correo electrónico no deseado de Office 365, puede notificar estos mensajes a Microsoft. Para obtener instrucciones, vea [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).