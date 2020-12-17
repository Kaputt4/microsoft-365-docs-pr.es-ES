---
title: Administración de directivas de dispositivo de Windows 10 Pro con Microsoft 365 empresa Premium
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
description: Obtenga información sobre cómo administrar las directivas de dispositivo de Windows 10 Pro con Microsoft 365 empresa Premium.
ms.openlocfilehash: 9052859f03035a76bf69b7c8c23c75ae00353846
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/17/2020
ms.locfileid: "49703192"
---
# <a name="manage-windows-10-pro-device-policies"></a>Administrar directivas de dispositivo de Windows 10 Pro

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FYSL?autoplay=false]

Puede usar Microsoft 365 Business para asegurarse de que el antivirus de Windows Defender está activado en dispositivos con Windows 10 y que las actualizaciones de Microsoft se descargan automáticamente en los dispositivos de los usuarios.

## <a name="try-it"></a>¿Se atreve?

1. Inicie sesión en el Centro de administración de Microsoft 365.
1. En **directivas**, elija Agregar Directiva.
1. En el panel **Agregar Directiva** , escriba un nombre en **nombre** de la Directiva y, a continuación, seleccione **configuración de dispositivo Windows 10** en **tipo de directiva**.
1. Elija **proteger dispositivos Windows 10** para ver las configuraciones secundarias.
1. Asegúrate de que **proteger los equipos PC contra virus y otras amenazas con el antivirus de Windows Defender** y **mantener los dispositivos con Windows 10 actualizados automáticamente** está activado.
1. En ¿ **quién recibirá esta configuración?**, todos los usuarios están seleccionados de forma predeterminada, pero puede elegir **cambiar** para seleccionar los grupos de seguridad que haya creado.
1. Para finalizar la creación de la Directiva, elija **Agregar**.
1. En la página **Agregar Directiva** , elija **cerrar**.
1. En la Página principal del centro de administración, confirme que se ha agregado la nueva Directiva eligiendo **directivas** y revisando la Directiva en la página **directivas** .
1. Para comprobar que la Directiva ha surtido efecto, en el dispositivo Windows 10 de un usuario, vaya a Windows Update, elija **Opciones avanzadas** y confirme que la configuración está atenuada.

    A continuación, haga clic en **elegir cómo se van a entregar las actualizaciones** y asegúrese de que la configuración está atenuada y aparece el mensaje siguiente: **algunas opciones de configuración están ocultas o están administradas por la organización**.

