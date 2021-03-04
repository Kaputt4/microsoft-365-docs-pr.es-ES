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
description: Obtenga información sobre cómo proteger las aplicaciones de Office en iOS con Microsoft 365 Empresa Premium.
ms.openlocfilehash: 197041a4eb9ada65f4b6046d93f2a856cbdfb40d
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "50422116"
---
# <a name="secure-office-apps-on-ios"></a>Proteger aplicaciones de Office en iOS

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FLvZ?autoplay=false]

Puede configurar una directiva de acceso de usuario que requiera que los usuarios móviles escriban un PIN o una huella digital para iniciar sesión y también cifre los archivos de trabajo almacenados en sus dispositivos.

## <a name="try-it"></a>¿Se atreve?

1. Inicie sesión en el Centro de administración de Microsoft 365.
1. En **Directivas,** elija **Agregar directiva**.
1. En el **panel Agregar directiva,** escriba un nombre en **Nombre** de directiva y elija el tipo de directiva que desee en Tipo **de directiva**.
1. Activar Administrar **cómo los usuarios acceden a** los archivos de Office en dispositivos móviles y, a continuación, asegúrese de que las tres opciones de configuración siguientes están activadas:
    - **Requerir una huella digital o un PIN para obtener acceso a las aplicaciones de Office**
    - **Proteger los archivos de trabajo cuando se pierden o se roban dispositivos**
    - **Cifrar archivos de trabajo**

1. En **Archivos de estas aplicaciones se protegerán,** seleccione las aplicaciones de Office que desea proteger en dispositivos móviles.
1. En **¿Quién va a obtener esta configuración?**, todos  los usuarios están seleccionados de forma predeterminada, pero puede elegir Cambiar para seleccionar los grupos de seguridad que haya creado.
1. Para finalizar la creación de la directiva, elija **Agregar**.
1. En la **página Agregar directiva,** elija **Cerrar**.
1. En la página principal del Centro de administración, confirme  que la nueva directiva se agregó eligiendo Directivas y revisando la directiva en la **página** Directivas.