---
title: Proteger las aplicaciones de Office en iOS
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
description: Obtenga información sobre cómo proteger las aplicaciones de Office en iOS con Microsoft 365 empresa Premium.
ms.openlocfilehash: 1703faa7cd7731f0779bacc3d2fa3ad3e4556910
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/17/2020
ms.locfileid: "49702654"
---
# <a name="secure-office-apps-on-ios"></a>Proteger las aplicaciones de Office en iOS

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FLvZ?autoplay=false]

Puede configurar una directiva de acceso de usuario que requiera que los usuarios móviles escriban un PIN o una huella digital para iniciar sesión, y también se cifran los archivos de trabajo almacenados en sus dispositivos.

## <a name="try-it"></a>¿Se atreve?

1. Inicie sesión en el Centro de administración de Microsoft 365.
1. En **directivas**, elija **Agregar Directiva**.
1. En el panel **Agregar Directiva** , escriba un nombre en **nombre de directiva** y elija el tipo de directiva que desee en **tipo de directiva**.
1. Active administrar la forma en que **los usuarios obtienen acceso a los archivos de Office en dispositivos móviles** y asegúrese de que estén activadas las tres opciones siguientes:
    - **Requerir una huella digital o un PIN para obtener acceso a las aplicaciones de Office**
    - **Proteger los archivos de trabajo cuando se pierden o se roban dispositivos**
    - **Cifrar archivos de trabajo**

1. En **los archivos de estas aplicaciones estarán protegidos**, seleccione las aplicaciones de Office que quiera proteger en los dispositivos móviles.
1. En ¿ **quién recibirá esta configuración?**, todos los usuarios están seleccionados de forma predeterminada, pero puede elegir **cambiar** para seleccionar los grupos de seguridad que haya creado.
1. Para finalizar la creación de la Directiva, elija **Agregar**.
1. En la página **Agregar Directiva** , elija **cerrar**.
1. En la Página principal del centro de administración, confirme que se ha agregado la nueva Directiva eligiendo **directivas** y revisando la Directiva en la página **directivas** .