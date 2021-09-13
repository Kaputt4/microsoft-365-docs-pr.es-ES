---
title: Detener el reenvío automático de mensajes de correo electrónico
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
- AdminTemplateSet
- admindeeplinkMAC
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Aprende a detener el reenvío automático de mensajes de correo mediante la creación de una regla de flujo de correo para evitar el robo de información propietaria.
ms.openlocfilehash: 5c13e43f29b6d49b13daf4eb0aa6e3d6fd8275ae
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/12/2021
ms.locfileid: "59188785"
---
# <a name="stop-email-auto-forward"></a>Detener el reenvío automático de correo electrónico

## <a name="watch-stop-auto-forwarding-emails"></a>Watch: Stop auto-forwarding emails

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2W6kS?autoplay=false]

Si un hacker obtiene acceso al buzón de un usuario, puede reenviar automáticamente el correo electrónico del usuario a una dirección externa y robar información de propiedad. Puede detener esto creando una regla de flujo de correo.

## <a name="try-it"></a>¿Se atreve?

1. En el  <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Centro de administración de Microsoft 365</a>, seleccione **Exchange**, flujo de correo y, en la pestaña reglas, seleccione el signo más y elija crear una nueva **regla**.
1. Seleccione **Más opciones**. Asigne un nombre a la nueva regla.
1. A continuación, abra la lista desplegable para **aplicar esta regla** si , seleccione el **remitente** y, a continuación, sea **interno externo**.
1. Seleccione **Dentro de la organización** y, a continuación, **Aceptar**.
1. Elija **agregar condición,** abra la lista desplegable, seleccione **Las propiedades del mensaje** y, a continuación, incluya el tipo de **mensaje**.
1. Abra la **lista desplegable Seleccionar tipo** de mensaje, elija Reenvío **automático** y, a continuación, **Aceptar**.
1. Abra la lista desplegable **Hacer** lo siguiente, seleccione **Bloquear el** mensaje y, a continuación, **rechace** el mensaje e incluya una explicación .
1. Escriba el texto del mensaje para su explicación y, a continuación, seleccione **Aceptar**.
1. Desplácese hasta la parte inferior y **seleccione Guardar**.

    La regla se ha creado y los hackers ya no podrán reenviar mensajes automáticamente.

## <a name="related-content"></a>Contenido relacionado

[Agregar otro alias de correo electrónico para un usuario](../admin/email/add-another-email-alias-for-a-user.md) (artículo)\
[Configurar el reenvío de correo electrónico en Microsoft 365](../admin/email/configure-email-forwarding.md) (artículo)\
[Buscar y corregir problemas de entrega de correo electrónico](/exchange/troubleshoot/email-delivery/email-delivery-issues) como un Office 365 administración para empresas (artículo)