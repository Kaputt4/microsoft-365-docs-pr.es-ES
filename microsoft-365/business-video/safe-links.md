---
title: Administrar vínculos seguros
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
description: Obtenga información sobre cómo administrar vínculos seguros para proteger su empresa de sitios malintencionados.
ms.openlocfilehash: eabb2c1f71b1183867ffcb005ba4f7e44ed6e4b7
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/17/2020
ms.locfileid: "49702664"
---
# <a name="manage-safe-links"></a>Administrar vínculos seguros

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWvdwy?autoplay=false]

Microsoft defender para Office 365, anteriormente llamado Microsoft 365 ATP o protección contra amenazas avanzada, ayuda a proteger su empresa contra sitios malintencionados cuando los usuarios hacen clic en vínculos en aplicaciones de Office.

## <a name="try-it"></a>¿Se atreve?

1. Vaya al [centro de administración](https://admin.microsoft.com)y seleccione **configurar**.
1. Desplácese hacia abajo para **aumentar la protección frente a amenazas avanzadas**. Seleccione **Ver**, **administrar** y, a continuación, **vínculos seguros ATP**.
1. En **directivas que se aplican a toda la organización**, elija la directiva **predeterminada** y, a continuación, seleccione el icono **Editar** .
1. Escriba una dirección URL que desee bloquear.
1. Seleccione **usar vínculos seguros en las aplicaciones de Office, Office para iOS y Android**; Seleccione no **realizar seguimiento cuando los usuarios hagan clic en vínculos seguros**; y seleccione no **permitir que los usuarios hagan clic en vínculos seguros a la dirección URL original**. Es posible que ya estén seleccionados si configura la directiva predeterminada. Haga clic en **Guardar**.
1. En **directivas que se aplican a destinatarios específicos**, seleccione **regla de vínculos a prueba** de errores recomendada y, a continuación, seleccione el icono **Editar** .
1. Seleccione **configuración**, desplácese hacia abajo, escriba la dirección URL que no desea que se compruebe y, a continuación, seleccione el icono **Agregar** .
1. Seleccione **se aplica a** y, a continuación, seleccione el nombre de dominio. Seleccione los dominios adicionales a los que quiera aplicar la regla. Seleccione **Agregar**, **Aceptar** y, a continuación, **Guardar**.

Los vínculos seguros ATP ahora están configurados. Espere hasta 30 minutos para que los cambios surtan efecto.

Cuando un usuario recibe un correo electrónico con vínculos, se examinan los vínculos. Si los vínculos se consideran seguros, se puede hacer clic en ellos. Sin embargo, si el vínculo se encuentra en la lista de bloqueados, los usuarios verán un mensaje que indica que se ha bloqueado.