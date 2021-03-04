---
title: Administrar directivas de dispositivos Windows 10 Pro con Microsoft 365 Empresa Premium
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
description: Aprende a administrar directivas de dispositivos de Windows 10 Pro con Microsoft 365 Empresa Premium.
ms.openlocfilehash: 8d3e5107c0b2dfe3a84f31b98d9bd3ff8f7c5e4f
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "50422128"
---
# <a name="manage-windows-10-pro-device-policies"></a>Administrar directivas de dispositivos Windows 10 Pro

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FYSL?autoplay=false]

Puedes usar Microsoft 365 Empresa para garantizar que Windows Defender Antivirus esté activado en dispositivos Windows 10 y que las actualizaciones de Microsoft se descarguen automáticamente en los dispositivos de los usuarios.

## <a name="try-it"></a>¿Se atreve?

1. Inicie sesión en el Centro de administración de Microsoft 365.
1. En **Directivas,** elija Agregar directiva.
1. En el **panel Agregar directiva,** escriba un nombre en **Nombre** de directiva y, a continuación, seleccione Configuración de dispositivo de **Windows 10** en **Tipo de directiva**.
1. Elige **Proteger dispositivos Windows 10** para ver la sub configuración.
1. Asegúrate de que **la Ayuda para** proteger los equipos de virus y otras amenazas mediante Windows Defender Antivirus y Mantener los dispositivos Windows **10** actualizados estén activados automáticamente.
1. En **¿Quién va a obtener esta configuración?**, todos  los usuarios están seleccionados de forma predeterminada, pero puede elegir Cambiar para seleccionar los grupos de seguridad que haya creado.
1. Para finalizar la creación de la directiva, elija **Agregar**.
1. En la **página Agregar directiva,** elija **Cerrar**.
1. En la página principal del Centro de administración, confirme  que la nueva directiva se agregó eligiendo Directivas y revisando la directiva en la **página** Directivas.
1. Para comprobar que la directiva ha tenido efecto, en el dispositivo Windows 10 de un usuario, vaya a Windows Update, elija Opciones avanzadas y confirme que la configuración está atenuada. 

    A continuación, haga clic en Elegir cómo se entregan las actualizaciones y confirme que la configuración está atenuada y aparece el siguiente mensaje: Algunas opciones de configuración están ocultas o **administradas por su organización.** 

