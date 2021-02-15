---
title: Detener el reenvío automático de mensajes de correo electrónico
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
- okr_smb
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Obtenga información sobre cómo detener el reenvío automático de mensajes de correo electrónico.
ms.openlocfilehash: ebbe37ab5c4a60c6ac4b6ebf8877247199460fa1
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49925891"
---
# <a name="stop-email-auto-forward"></a>Detener el reenvío automático de correo electrónico

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2W6kS?autoplay=false]

Si un hacker obtiene acceso al buzón de un usuario, puede reenviar automáticamente el correo electrónico del usuario a una dirección externa y robar información propietaria. Puede detener esto creando una regla de flujo de correo.

## <a name="try-it"></a>¿Se atreve?

1. En el Centro de administración de Microsoft 365,  seleccione **Exchange** **,** flujo de correo y, en la pestaña reglas, seleccione el signo más y elija crear una **nueva regla.**
1. Seleccione **Más opciones.** Asigne un nombre a la nueva regla.
1. A continuación, abra la lista desplegable para **aplicar esta regla si**, seleccione el **remitente** y, a continuación, sea **interno externo**.
1. Seleccione **Dentro de la organización** y, a continuación, **Aceptar**.
1. Elija **agregar condición,** abra la lista desplegable, seleccione **Las propiedades del mensaje** y, a continuación, incluya el tipo de **mensaje**.
1. Abra la **lista desplegable seleccionar tipo** de mensaje, elija **Reenviar** automáticamente y, a continuación, **Aceptar.**
1. Abra la **lista desplegable Hacer** lo siguiente, seleccione Bloquear **el** mensaje y, a continuación, **rechace el** mensaje e incluya una explicación.
1. Escriba el texto del mensaje para su explicación y, a continuación, seleccione **Aceptar.**
1. Desplácese hasta la parte inferior y seleccione **Guardar**.

    Se ha creado la regla y los hackers ya no podrán reenviar mensajes automáticamente.