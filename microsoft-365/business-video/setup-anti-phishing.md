---
title: Configurar la protección contra suplantación de identidad
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
description: Obtenga información sobre cómo configurar la protección contra la suplantación de identidad.
ms.openlocfilehash: f3a1399c8a6a51c7b14af7ffea8fbaea39cd1541
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/17/2020
ms.locfileid: "49702892"
---
# <a name="set-up-anti-phishing"></a>Configurar la protección contra suplantación de identidad (phishing)

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWvt9r?autoplay=false]

La suplantación de identidad (phishing) es un ataque malintencionado en el que un mensaje de correo electrónico se ve como enviado desde un origen conocido, pero intenta recopilar información personal. De forma predeterminada, Microsoft 365 incluye alguna protección contra la suplantación de identidad (phishing), pero puede aumentar dicha protección refinando la configuración. Vamos a echar un vistazo.

## <a name="try-it"></a>¿Se atreve?

1. En el centro de administración en [https://admin.microsoft.com](https://admin.microsoft.com) , **Seleccione seguridad**, administración de **amenazas**, **Directiva** y, a continuación, **protección contra phishing ATP**.
1. Seleccione **directiva predeterminada** para redefinirla.
1. En la sección **suplantación** , seleccione **Editar**.
1. Vaya a **Agregar dominios para proteger** y seleccione el botón de alternancia para incluir automáticamente los dominios que posee.
1. Vaya a **acciones**, abra el menú desplegable **si un usuario suplantado envía un correo electrónico** y elija la acción que desee.

    Abra la lista desplegable **si el correo electrónico se envía por un dominio representado** y elija la acción que desee.
1. Seleccione **activar las sugerencias de seguridad de suplantación**. Elija si se deben proporcionar sugerencias a los usuarios cuando el sistema detecte usuarios suplantados, dominios o caracteres inusuales. Haga clic en **Guardar**.
1. Seleccione **inteligencia de buzones de correo** y compruebe que está encendido. Esto permite que el correo electrónico sea más eficaz mediante el aprendizaje de los patrones de uso.
1. Elija **Agregar remitentes y dominios de confianza**. Aquí puede agregar direcciones de correo electrónico o dominios que no deben clasificarse como suplantación.
1. Elija **revisar la configuración**, asegúrese de que todo sea correcto, seleccione **Guardar** y, después, **cerrar**.

    Su organización ahora tiene mejor protección frente a las amenazas de suplantación de identidad.