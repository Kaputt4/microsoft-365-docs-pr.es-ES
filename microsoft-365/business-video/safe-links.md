---
title: Administrar vínculos seguros
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
description: Obtenga información sobre cómo administrar vínculos seguros para proteger su empresa de sitios malintencionados.
ms.openlocfilehash: ce0c1ba6e4099b6eaf4ec974938170020b8a5892
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580635"
---
# <a name="manage-safe-links"></a>Administrar vínculos seguros

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWvdwy?autoplay=false]

Microsoft Defender para Office 365 , anteriormente denominado ATP de Microsoft 365, o Protección contra amenazas avanzada, ayuda a proteger su negocio contra sitios malintencionados cuando las personas hacen clic en vínculos en aplicaciones de Office.

## <a name="try-it"></a>¿Se atreve?

1. Vaya al Centro [de administración](https://admin.microsoft.com)y seleccione **Configurar**.
1. Desplácese hacia abajo **hasta Aumentar la protección contra amenazas avanzadas.** Seleccione **Ver**, **Administrar** y, a continuación, **Vínculos seguros de ATP**.
1. En **Directivas que se aplican a toda la organización,** elija la **directiva** Predeterminada y, a continuación, seleccione el **icono** Editar.
1. Escriba una dirección URL que desee bloquear.
1. Seleccione **Usar vínculos seguros en aplicaciones de Office, Office para iOS y Android;** seleccione **No realizar un seguimiento cuando los usuarios hacen clic en vínculos seguros;** y seleccione **No permitir que los usuarios hagan clic en vínculos seguros a la dirección URL original.** Es posible que ya se seleccionen si configura la directiva predeterminada. Seleccione **Guardar**.
1. En **Directivas que se aplican a destinatarios específicos,** elija Regla de vínculos seguros **recomendados** y, a continuación, seleccione el **icono** Editar.
1. Seleccione **la configuración,** desplácese hacia abajo, escriba la dirección URL que no desea que se active y, a continuación, seleccione el **icono** Agregar.
1. Seleccione **aplicado a** y, a continuación, seleccione el nombre de dominio. Seleccione los dominios adicionales a los que desee que se aplique la regla. Seleccione **agregar**, **Aceptar** y, a **continuación, Guardar**.

Los vínculos seguros de ATP ya están configurados. Espere hasta 30 minutos para que los cambios entren en vigor.

Cuando un usuario recibe un correo electrónico con vínculos, se examinarán los vínculos. Si los vínculos se consideran seguros, se pueden hacer clic en ellos. Sin embargo, si el vínculo está en la lista de bloqueados, los usuarios verán un mensaje de que se ha bloqueado.