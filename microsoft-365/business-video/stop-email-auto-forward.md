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
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Obtenga información sobre cómo detener el reenvío automático de mensajes de correo electrónico.
ms.openlocfilehash: b6715cfdf8622521d977e0746cb9a340a8f70a5c
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578608"
---
# <a name="stop-email-auto-forward"></a>Detener el reenvío automático de correo electrónico

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2W6kS?autoplay=false]

Si un hacker obtiene acceso al buzón de un usuario, puede reenviar automáticamente el correo electrónico del usuario a una dirección externa y robar información de propiedad. Puede detener esto creando una regla de flujo de correo.

## <a name="try-it"></a>¿Se atreve?

1. En el Centro de administración de Microsoft 365,  seleccione **Exchange** **,** flujo de correo y, en la pestaña reglas, seleccione el signo más y elija crear una **nueva regla**.
1. Seleccione **Más opciones**. Asigne un nombre a la nueva regla.
1. A continuación, abra la lista desplegable para **aplicar esta regla** si , seleccione el **remitente** y, a continuación, sea **interno externo**.
1. Seleccione **Dentro de la organización** y, a continuación, **Aceptar**.
1. Elija **agregar condición,** abra la lista desplegable, seleccione **Las propiedades del mensaje** y, a continuación, incluya el tipo de **mensaje**.
1. Abra la **lista desplegable Seleccionar tipo** de mensaje, elija Reenvío **automático** y, a continuación, **Aceptar**.
1. Abra la lista desplegable **Hacer** lo siguiente, seleccione **Bloquear el** mensaje y, a continuación, **rechace** el mensaje e incluya una explicación .
1. Escriba el texto del mensaje para su explicación y, a continuación, seleccione **Aceptar**.
1. Desplácese hasta la parte inferior y **seleccione Guardar**.

    La regla se ha creado y los hackers ya no podrán reenviar mensajes automáticamente.