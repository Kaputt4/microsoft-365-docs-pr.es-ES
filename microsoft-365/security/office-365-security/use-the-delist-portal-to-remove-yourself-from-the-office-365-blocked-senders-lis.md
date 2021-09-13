---
title: Quitarse de la lista de remitentes bloqueados
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 04/18/2016
audience: ITPro
ms.topic: troubleshooting
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0bcecdd4-3343-4cc0-9e58-e19d4de515e8
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: En este artículo, aprenderá a usar el portal de deslist para quitarse de la lista Microsoft 365 remitentes bloqueados.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0e825c859253b759e5436dbc5419f98f0c863fa3
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/12/2021
ms.locfileid: "59213217"
---
# <a name="use-the-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a>Usar el portal de eliminación de la lista para quitarse de la lista de remitentes bloqueados

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

¿Recibe un mensaje de error cuando intenta enviar un correo electrónico a un destinatario cuya dirección de correo electrónico está en Microsoft 365? Si cree que no debe recibir el mensaje de error, puede usar el portal de deslist para quitarse de la lista de remitentes bloqueados.

## <a name="what-is-the-blocked-senders-list"></a>¿Qué es la lista de remitentes bloqueados?

Microsoft usa la lista de remitentes bloqueados para proteger a sus clientes contra el spam, la suplantación de identidad y los ataques de phishing. La dirección IP del servidor de correo, es decir, la dirección que el servidor de correo usa para identificarse en Internet, se etiquetó como una amenaza potencial para Microsoft 365 por una variedad de motivos. Cuando Microsoft 365 la dirección IP a la lista, impide toda comunicación adicional entre la dirección IP y cualquiera de nuestros clientes a través de nuestros centros de datos.

Sabrá que lo hemos agregado a la lista cuando reciba una respuesta a un mensaje de correo que incluya un error similar al siguiente:

> 550 5.7.606-649 Acceso denegado, prohibido enviar IP [_IP address_]; para solicitar la eliminación de esta lista, visite <https://sender.office.com/> y siga las instrucciones. Para más información, consulte [Informes de no entrega de correo electrónico en Exchange Online](/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online).

donde _dirección IP_ es la dirección IP del equipo en el que se ejecuta el servidor de correo.

### <a name="to-use-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a>Para usar el portal de deslist para quitarse de la lista de remitentes bloqueados

1. En un explorador web, vaya a <https://sender.office.com>.

2. Siga las instrucciones que se indican en la página. Asegúrese de que usa la dirección de correo electrónico a la que se envió el mensaje de error, así como la dirección IP especificada en el mensaje de error. Solo se puede especificar una dirección de correo electrónico y una dirección IP por visita.

3. Haga clic en **Enviar**.

    El portal enviará un correo electrónico a la dirección que indique. El mensaje será similar al siguiente:

    ![Captura de pantalla del correo electrónico recibido al enviar una solicitud a través del portal de deslist.](../../media/bf13e4f7-f68c-4e46-baa7-b6ab4cfc13f3.png)

4. Haga clic en el vínculo de confirmación que aparece en el correo electrónico que le ha enviado el portal de eliminación de la lista.

    Regresará al portal de eliminación de la lista.

5. En el portal de eliminación de la lista, haga clic en **Quitar de la lista una IP**.

    Después de quitar la dirección IP de la lista de remitentes bloqueados, los mensajes de correo electrónico de esa dirección IP se entregarán a los destinatarios que usan Microsoft 365. Por lo tanto, asegúrese de que el correo electrónico enviado desde esa dirección IP no es ofensivo ni malintencionado; de lo contrario, es posible que se vuelva a bloquear la dirección IP.

    > [!NOTE]
    > Pueden pasar hasta 24 horas o los resultados pueden variar ampliamente antes de eliminar las restricciones.

Consulta [Crear listas de remitentes seguros en EOP](create-safe-sender-lists-in-office-365.md) y Protección contra correo no deseado saliente en [EOP](outbound-spam-controls.md) para evitar que se bloquee una IP.

## <a name="more-information"></a>Más información

El formulario de deslisting **para Outlook.com, el servicio de** consumidor se puede encontrar [aquí](https://support.microsoft.com/supportrequestform/8ad563e3-288e-2a61-8122-3ba03d6b8d75). Asegúrese de leer primero las [preguntas más frecuentes](https://sendersupport.olc.protection.outlook.com/pm/troubleshooting.aspx) para obtener la dirección *del* envío.
