---
title: Agregar un dominio
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
description: Obtenga información sobre cómo agregar otro dominio a su suscripción.
ms.openlocfilehash: a5df440f3b7e28c2bdbc69f9383a8399ef193ed0
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49927615"
---
# <a name="add-another-domain"></a>Agregar otro dominio

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4dN8c?autoplay=false]

Es posible que su empresa necesite varios nombres de dominio para distintos fines. Por ejemplo, es posible que desee agregar una ortografía diferente del nombre de la compañía porque los clientes ya lo están usando y sus comunicaciones no le han podido contactar.

## <a name="try-it"></a>¿Se atreve?

1. En el Centro de administración de Microsoft 365, elija **Configurar.**
1. En **Obtener la configuración de dominio personalizado,** seleccione **Ver**.
1. Elija **Administrar** y, a continuación, **Agregar dominio.**
1. Escriba el nuevo nombre de dominio que desea agregar y, a continuación, **seleccione Siguiente**.
1. Inicie sesión en el registrador de dominios, en este caso GoDaddy y, a continuación, **seleccione Siguiente**.
1. Si se le solicita, inicie sesión en el registrador y, a continuación, elija **Autorizar**.
1. Elija **Agregar los registros DNS para mí** y, a continuación, seleccione **Siguiente**.
1. Elija los servicios para su nuevo dominio y desactive las casillas de los servicios que administrará un dominio diferente. Por ejemplo, si solo quiere usar el nuevo dominio para el correo electrónico, elija **Exchange** y desactive las casillas de **Skype** Empresarial y Administración de dispositivos móviles para **Office 365.**
1. Seleccione **Siguiente**, **Autorizar**, **Siguiente** y, a continuación, **Finalizar**. Se ha agregado el nuevo dominio.

Para recibir correo electrónico en su nuevo dominio, deberá agregar un nuevo alias de correo electrónico para cada usuario:

1. Seleccione **Usuarios,** **Usuarios activos** y, a continuación, seleccione el usuario al que se le asignará el nuevo alias.
1. Elija **Administrar alias de correo** electrónico y, a **continuación, Agregue un alias.**
1. Escriba el nombre de usuario y, a continuación, elija el nuevo dominio en la lista desplegable.
1. Seleccione **Guardar cambios** y, a continuación, cierre la ventana.
1. Repita estos pasos para cada usuario que deba recibir correo electrónico en el nuevo dominio.