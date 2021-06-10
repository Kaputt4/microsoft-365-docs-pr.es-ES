---
title: Configurar la protección contra suplantación de identidad (phishing)
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
description: Obtenga información sobre cómo configurar la protección contra suplantación de identidad (phishing).
ms.openlocfilehash: 32494eda4496d99e5e5f4def213ba7876f6c3183
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580419"
---
# <a name="set-up-anti-phishing"></a>Configurar directivas contra suplantación de identidad

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWvt9r?autoplay=false]

La suplantación de identidad (phishing) es un ataque malintencionado en el que un correo electrónico parece enviado desde un origen conocido, pero intenta recopilar su información personal. De forma predeterminada, Microsoft 365 protección contra suplantación de identidad (phishing), pero puede aumentar esa protección refinando la configuración. Echemos un vistazo.

## <a name="try-it"></a>¿Se atreve?

1. En el Centro de administración en , seleccione Seguridad , Administración de amenazas , Directiva y, a continuación, [https://admin.microsoft.com](https://admin.microsoft.com) ATP  **Anti-phishing**.  
1. Seleccione **Directiva predeterminada para** refinarla.
1. En la **sección Suplantación,** seleccione **Editar**.
1. Ve **a Agregar dominios para proteger y** seleccionar la alternancia para incluir automáticamente los dominios que posees.
1. Vaya a **Acciones**, abra la lista desplegable Si un usuario **suplantado** envía el correo electrónico y elija la acción que desee.

    Abra la lista desplegable Si un dominio **suplantado envía** el correo electrónico y elige la acción que quieras.
1. Seleccione **Activar sugerencias de seguridad de suplantación.** Elija si se deben proporcionar sugerencias a los usuarios cuando el sistema detecte usuarios suplantados, dominios o caracteres inusuales. Seleccione **Guardar**.
1. Seleccione **Inteligencia de buzones** y compruebe que está activada. Esto permite que el correo electrónico sea más eficiente mediante el aprendizaje de patrones de uso.
1. Elija **Agregar remitentes y dominios de confianza.** Aquí puede agregar direcciones de correo electrónico o dominios que no deben clasificarse como suplantación.
1. Elija **Revisar la configuración,** asegúrese de que todo es correcto, **seleccione Guardar** y, a continuación, **Cerrar**.

    Su organización ahora tiene una mejor protección frente a las amenazas de suplantación de identidad.