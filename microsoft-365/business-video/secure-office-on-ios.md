---
title: Proteger aplicaciones de Office en iOS
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
description: Obtenga información sobre cómo proteger las aplicaciones de Office en iOS con Microsoft 365 Empresa Premium.
ms.openlocfilehash: fd7fdd32500f9a2362ac29059abe9424d045c206
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928035"
---
# <a name="secure-office-apps-on-ios"></a>Proteger aplicaciones de Office en iOS

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FLvZ?autoplay=false]

Puede configurar una directiva de acceso de usuario que requiera que los usuarios móviles escriban un PIN o huella digital para iniciar sesión, y también cifre los archivos de trabajo almacenados en sus dispositivos.

## <a name="try-it"></a>¿Se atreve?

1. Inicie sesión en el Centro de administración de Microsoft 365.
1. En **Directivas,** elija **Agregar directiva.**
1. En el **panel Agregar directiva,** escriba un nombre en **Nombre** de directiva y elija el tipo de directiva que desee en Tipo **de directiva.**
1. Active Administrar el **modo en que los usuarios acceden a** los archivos de Office en dispositivos móviles y, a continuación, asegúrese de que están activadas las tres opciones siguientes:
    - **Requerir una huella digital o un PIN para obtener acceso a las aplicaciones de Office**
    - **Proteger los archivos de trabajo cuando se pierden o roban dispositivos**
    - **Cifrar archivos de trabajo**

1. En **Archivos de estas aplicaciones se protegerán,** seleccione las aplicaciones de Office que desea proteger en dispositivos móviles.
1. Under **Who will get these settings?**, all users are selected by default, but you can choose **Change** to select any security groups you've created.
1. Para terminar de crear la directiva, elija **Agregar**.
1. En la **página Agregar directiva,** elija **Cerrar**.
1. En la página principal del centro de administración, confirme  que se ha agregado la nueva directiva eligiendo Directivas y revisando la directiva en la **página** Directivas.