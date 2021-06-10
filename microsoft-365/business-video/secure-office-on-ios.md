---
title: Proteger aplicaciones de Office en iOS
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
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
description: Obtén información sobre cómo proteger Office aplicaciones en iOS con Microsoft 365 Empresa Premium.
ms.openlocfilehash: 5a5f52f87fe63fdec6df9611a5ea44a2ecf4466b
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580467"
---
# <a name="secure-office-apps-on-ios"></a>Proteger aplicaciones de Office en iOS

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FLvZ?autoplay=false]

Puede configurar una directiva de acceso de usuario que requiera que los usuarios móviles escriban un PIN o una huella digital para iniciar sesión y también cifre los archivos de trabajo almacenados en sus dispositivos.

## <a name="try-it"></a>¿Se atreve?

1. Inicie sesión en el Centro de administración de Microsoft 365.
1. En **Directivas,** elija **Agregar directiva**.
1. En el **panel Agregar directiva,** escriba un nombre en **Nombre** de directiva y elija el tipo de directiva que desee en Tipo **de directiva**.
1. Activa Administrar **cómo los usuarios acceden Office archivos en** dispositivos móviles y, a continuación, asegúrate de que las tres opciones de configuración siguientes estén activadas:
    - **Requerir una huella digital o un PIN para obtener acceso a las aplicaciones de Office**
    - **Proteger los archivos de trabajo cuando se pierden o se roban dispositivos**
    - **Cifrar archivos de trabajo**

1. En **Archivos de estas aplicaciones se protegerán,** selecciona las Office que quieras proteger en dispositivos móviles.
1. En **Quién se obtiene esta configuración?**, todos los usuarios están  seleccionados de forma predeterminada, pero puede elegir Cambiar para seleccionar los grupos de seguridad que haya creado.
1. Para finalizar la creación de la directiva, elija **Agregar**.
1. En la **página Agregar directiva,** elija **Cerrar**.
1. En la página principal del Centro de administración, confirme  que la nueva directiva se agregó eligiendo Directivas y revisando la directiva en la **página** Directivas.