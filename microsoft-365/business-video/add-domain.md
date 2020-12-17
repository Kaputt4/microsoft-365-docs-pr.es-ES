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
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Obtenga información sobre cómo agregar otro dominio a la suscripción.
ms.openlocfilehash: 16f6c4e416ede560d69014e320eb32c4453fd3f5
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/17/2020
ms.locfileid: "49702787"
---
# <a name="add-another-domain"></a>Agregar otro dominio

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4dN8c?autoplay=false]

Es posible que su empresa necesite varios nombres de dominio para diferentes propósitos. Por ejemplo, es posible que desee agregar una ortografía diferente al nombre de la compañía, ya que los clientes ya la usan y sus comunicaciones no han podido llegar a su nombre.

## <a name="try-it"></a>¿Se atreve?

1. En el centro de administración de Microsoft 365, elija **instalar**.
1. En **obtener el dominio personalizado configurado**, seleccione **Ver**.
1. Elija **administrar** y, a continuación, **Agregar dominio**.
1. Escriba el nuevo nombre de dominio que desea agregar y, a continuación, seleccione **siguiente**.
1. Inicie sesión en su registrador de dominios, en este caso GoDaddy, y luego seleccione **siguiente**.
1. Si se le solicita, inicie sesión en su registrador y, a continuación, elija **autorizar**.
1. Elija **Agregar los registros DNS por mí** y, después, seleccione **siguiente**.
1. Elija los servicios para el nuevo dominio y desactive las casillas de verificación de los servicios que se controlarán mediante un dominio diferente. Por ejemplo, si solo quiere usar el nuevo dominio para el correo electrónico, elija **Exchange** y desactive las casillas de verificación de **Skype empresarial** y **Administración de dispositivos móviles para Office 365**.
1. Seleccione **siguiente**, **autorice**, **siguiente** y, a continuación, **Finalizar**. Se ha agregado el nuevo dominio.

Para recibir correo electrónico en su nuevo dominio, tendrá que agregar un nuevo alias de correo electrónico para cada usuario:

1. Seleccione **usuarios**, **usuarios activos** y, a continuación, seleccione el usuario al que se asignará el nuevo alias.
1. Seleccione **administrar alias de correo electrónico** y, a continuación, **agregue un alias**.
1. Escriba el nombre de usuario y, a continuación, elija el nuevo dominio en la lista desplegable.
1. Seleccione **Guardar cambios** y, a continuación, cierre la ventana.
1. Repita estos pasos para cada usuario que deba recibir correo electrónico en el nuevo dominio.