---
title: Detener el reenvío automático de correos electrónicos
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
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Obtenga información sobre cómo detener el reenvío automático de correo electrónico.
ms.openlocfilehash: 0683e133f6c261dc19cc098b13be298cd8086001
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/17/2020
ms.locfileid: "49702594"
---
# <a name="stop-email-auto-forward"></a>Detener el reenvío automático de correo electrónico

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2W6kS?autoplay=false]

Si un pirata informático obtiene acceso al buzón de un usuario, puede reenviar automáticamente el correo electrónico del usuario a una dirección externa y robar información de propietario. Para detener esto, cree una regla de flujo de correo.

## <a name="try-it"></a>¿Se atreve?

1. En el centro de administración de 365 de Microsoft, seleccione **Exchange**, **flujo de correo** y, en la ficha **reglas** , seleccione el signo más y elija **crear una nueva regla**.
1. Seleccione **más opciones**. Asigne un nombre a la nueva regla.
1. A continuación, abra la lista desplegable para **aplicar esta regla si**, seleccione **el remitente** y, a continuación, **es interno externo**.
1. Seleccione **dentro de la organización** y, después, haga clic en **Aceptar**.
1. Elija **Agregar condición**, abra la lista desplegable, seleccione **las propiedades del mensaje** y, a continuación, **incluya el tipo de mensaje**.
1. Abra la lista desplegable **Seleccionar tipo de mensaje** , elija **reenvío automático** y **Aceptar**.
1. Abra la lista desplegable **haga lo siguiente** , seleccione **bloquear el mensaje** y, a continuación, **rechazar el mensaje e incluir una explicación**.
1. Escriba el texto del mensaje para su explicación y, después, seleccione **Aceptar**.
1. Desplácese hasta la parte inferior y seleccione **Guardar**.

    Se ha creado la regla y los hackers ya no podrán reenviar mensajes automáticamente.