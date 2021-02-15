---
title: Configurar la protección contra la suplantación de identidad
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
description: Obtenga información sobre cómo configurar la protección contra la suplantación de identidad.
ms.openlocfilehash: bcb6b8bac316b4b74c505656cb9a93e7a87e0830
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49927879"
---
# <a name="set-up-anti-phishing"></a>Configurar directivas contra suplantación de identidad

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWvt9r?autoplay=false]

La suplantación de identidad (phishing) es un ataque malintencionado en el que un correo electrónico parece enviado desde un origen conocido, pero intenta recopilar su información personal. De forma predeterminada, Microsoft 365 incluye alguna protección contra la suplantación de identidad, pero puede aumentar esa protección refinando la configuración. Echemos un vistazo.

## <a name="try-it"></a>¿Se atreve?

1. En el centro de administración en [https://admin.microsoft.com](https://admin.microsoft.com) , seleccione **Seguridad**, Administración **de amenazas**, **Directiva** y, a continuación, **Protección contra suplantación de identidad de ATP.**
1. Seleccione **Directiva predeterminada para** refinarla.
1. En la **sección Suplantación,** seleccione **Editar**.
1. Vaya a **Agregar dominios para proteger y** seleccione el botón de alternancia para incluir automáticamente los dominios de su propiedad.
1. Vaya a **Acciones,** abra la lista desplegable Si un usuario suplantado envía el correo electrónico y elija la acción que desee.

    Abra la lista desplegable Si un dominio **suplantado** envía correo electrónico y elige la acción que quieras.
1. Seleccione **Activar sugerencias de seguridad de suplantación.** Elija si se deben proporcionar sugerencias a los usuarios cuando el sistema detecte usuarios suplantados, dominios o caracteres inusuales. Seleccione **Guardar**.
1. Seleccione **inteligencia de** buzones de correo y compruebe que está activada. Esto permite que el correo electrónico sea más eficaz mediante el aprendizaje de patrones de uso.
1. Elija **Agregar remitentes y dominios de confianza.** Aquí puede agregar direcciones de correo electrónico o dominios que no deben clasificarse como suplantación.
1. Elija **Revisar la configuración,** asegúrese de que todo sea correcto, seleccione **Guardar** y, a continuación, **cerrar.**

    Su organización ahora tiene una mejor protección contra las amenazas de suplantación de identidad.