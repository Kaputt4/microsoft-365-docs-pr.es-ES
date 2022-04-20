---
title: Quitarse de la lista de remitentes bloqueados y la dirección 5.7.511 Errores de acceso denegado
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 04/18/2016
audience: ITPro
ms.topic: troubleshooting
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: 0bcecdd4-3343-4cc0-9e58-e19d4de515e8
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: En este artículo, aprenderá a usar el portal de deslist para quitarse de la lista de remitentes bloqueados Microsoft 365. Esta es la mejor respuesta para solucionar los errores de acceso denegado 5.7.511.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 43637f8eb72d078223236f78b45034218e34bcbc
ms.sourcegitcommit: 45bc65972d4007b2aa7760d4457a0d2699f81926
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2022
ms.locfileid: "64971140"
---
# <a name="use-the-delist-portal-to-remove-yourself-from-the-blocked-senders-list-and-address-57511-access-denied-errors"></a>Use el portal de deslist para quitarse de la lista de remitentes bloqueados y la dirección 5.7.511 Errores de acceso denegado

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

¿Recibe un mensaje de error al intentar enviar un correo electrónico a un destinatario cuya dirección de correo electrónico está en Microsoft 365 (por ejemplo, y la dirección 5.7.511 Acceso denegado)? Si cree que no debería recibir el mensaje de error, puede usar el portal de deslist para quitarse de la lista de remitentes bloqueados.

## <a name="what-is-the-blocked-senders-list"></a>¿Cuál es la lista de remitentes bloqueados?

Microsoft usa la lista de remitentes bloqueados para proteger a sus clientes contra el spam, la suplantación de identidad y los ataques de phishing. La dirección IP del servidor de correo, es decir, la dirección que usa el servidor de correo para identificarse en Internet, se etiquetó como una amenaza potencial para Microsoft 365 por una de las diversas razones. Cuando Microsoft 365 agrega la dirección IP a la lista, impide toda comunicación adicional entre la dirección IP y cualquiera de nuestros clientes a través de nuestros centros de datos.

Sabrá que lo hemos agregado a la lista cuando reciba una respuesta a un mensaje de correo que incluya un error similar al siguiente:

> 550 5.7.606-649 Acceso denegado, prohibido enviar ip [_dirección IP_] (por ejemplo, 5.7.511 Acceso denegado): Para solicitar la eliminación de esta lista, visite <https://sender.office.com/> y siga las instrucciones. Para más información, consulte [Informes de no entrega de correo electrónico en Exchange Online](/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online).

donde _dirección IP_ es la dirección IP del equipo en el que se ejecuta el servidor de correo.

## <a name="verify-senders-before-removing-them-from-the-blocked-senders-list"></a>Comprobación de remitentes antes de quitarlos de la lista de remitentes bloqueados

Hay buenas razones para que los remitentes terminen en la lista de remitentes bloqueados, pero pueden producirse errores. Eche un vistazo a este vídeo para obtener una explicación equilibrada de los remitentes bloqueados y la deslisting.
<p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWMhvD]

## <a name="to-use-delist-portal-to-remove-yourself-from-the-blocked-senders-list-after-errors-like-57511-access-denied"></a>Para usar el portal de deslist para quitarse de la lista de remitentes bloqueados (después de errores como 5.7.511 Access denegado)

1. En un explorador web, vaya a <https://sender.office.com>.

2. Siga las instrucciones que se indican en la página. Asegúrese de que usa la dirección de correo electrónico a la que se envió el mensaje de error, así como la dirección IP especificada en el mensaje de error. Solo se puede especificar una dirección de correo electrónico y una dirección IP por visita.

3. Haga clic en **Enviar**.

    El portal enviará un correo electrónico a la dirección que indique. El mensaje será similar al siguiente:

    :::image type="content" source="../../media/bf13e4f7-f68c-4e46-baa7-b6ab4cfc13f3.png" alt-text="El correo electrónico recibido al enviar una solicitud a través del portal de deslist" lightbox="../../media/bf13e4f7-f68c-4e46-baa7-b6ab4cfc13f3.png":::

4. Haga clic en el vínculo de confirmación que aparece en el correo electrónico que le ha enviado el portal de eliminación de la lista.

    Regresará al portal de eliminación de la lista.

5. En el portal de eliminación de la lista, haga clic en **Quitar de la lista una IP**.

    Después de quitar la dirección IP de la lista de remitentes bloqueados, los mensajes de correo electrónico de esa dirección IP se entregarán a los destinatarios que usan Microsoft 365. Por lo tanto, asegúrese de que el correo electrónico enviado desde esa dirección IP no es ofensivo ni malintencionado; de lo contrario, es posible que se vuelva a bloquear la dirección IP.

    > [!NOTE]
    > Pueden pasar hasta 24 horas o los resultados pueden variar ampliamente antes de eliminar las restricciones.

Consulte [Creación de listas de remitentes seguros en EOP](create-safe-sender-lists-in-office-365.md) y [Protección contra correo no deseado saliente en EOP](outbound-spam-controls.md) para evitar que se bloquee una dirección IP.

### <a name="how-do-fix-error-code-57511"></a>Corrección del código de error 5.7.511

Si se produce un problema al entregar un mensaje de correo electrónico que envió, Office 365 o Microsoft 365 le enviará un correo electrónico para informarle. El correo electrónico que reciba es una notificación de estado de entrega, que también se conoce como DSN o mensaje de devolución. Un informe de no entrega (NDR) es el tipo de notificación de estado más común e indica que un mensaje no se entregó. En determinadas situaciones, Microsoft debe realizar investigaciones adicionales contra el tráfico desde la dirección IP y, si recibe el código NDR 5.7.511, **no** podrá usar el portal de deslist.

> 550 5.7.511 Acceso denegado, remitente prohibido[xxx.xxx.xxx.xxx]. Para solicitar la eliminación de esta lista, reenvíe este mensaje a delist@messaging.microsoft.com. Para obtener más información, vaya a <https://go.microsoft.com/fwlink/?LinkId=526653>.

En el correo electrónico para solicitar la eliminación de esta lista, proporcione el código NDR completo y la dirección IP. Microsoft se pondrá en contacto con usted en un plazo de 48 horas con los pasos siguientes.

## <a name="more-information"></a>Más información

El formulario de deslisting para **Outlook.com, el servicio de consumidor** se puede encontrar [aquí](https://support.microsoft.com/supportrequestform/8ad563e3-288e-2a61-8122-3ba03d6b8d75). Asegúrese de leer primero las [preguntas más frecuentes](https://sendersupport.olc.protection.outlook.com/pm/troubleshooting.aspx) sobre la dirección del _envío_ .
