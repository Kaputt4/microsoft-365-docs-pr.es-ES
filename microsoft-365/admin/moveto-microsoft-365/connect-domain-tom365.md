---
title: Conectar su dominio a Microsoft 365
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- scotvorg
- highpri
- M365-subscription-management
- Adm_O365
ms.custom:
- VSBFY23
- AdminSurgePortfolio
- adminvideo
- admindeeplinkMAC
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Obtenga información sobre cómo conectar su dominio a Microsoft 365.
ms.openlocfilehash: 604a1edb14276c38b36ed81e63238bf93c0d7699
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68188535"
---
# <a name="connect-your-domain-to-microsoft-365-for-business"></a>Conectar el dominio a Microsoft 365 para empresas

Consulte [ayuda de Microsoft 365 para pequeñas empresas](https://go.microsoft.com/fwlink/?linkid=2197659) en YouTube.

## <a name="watch-connect-your-domain-to-microsoft-365"></a>Inspección: Conexión del dominio a Microsoft 365

Consulte este vídeo y otros en nuestro [canal de YouTube](https://go.microsoft.com/fwlink/?linkid=2198216).

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LFpy?autoplay=false]

Una vez que haya configurado Microsoft 365 y movido los datos de correo electrónico desde Google Workspace, puede conectar su dominio a Microsoft 365. 

En primer lugar, tendrá que eliminar los registros DNS existentes de Google y, a continuación, podemos agregar nuevos registros DNS de Microsoft 365.

1. Inicie sesión en la consola de administración de Google Workspace en [admin.google.com](https://admin.google.com).
1. Seleccione **Dominios**, **Administrar dominios**, **Ver detalles**, **Administrar dominio** y **DNS** en la navegación izquierda.
1. Desplácese hacia abajo hasta **Registros sintéticos**, abra **Google Workspace**, seleccione **Eliminar** y, luego, **Eliminar** de nuevo.
1. Desplácese hacia abajo hasta **Registros de recursos personalizados** y elimine los registros DNS existentes que aparezcan, incluidos los que haya creado anteriormente para Microsoft 365.
1. Ve al [Centro de administración de Microsoft 365](https://admin.microsoft.com).
1. En el panel de navegación izquierdo, elija **Mostrar todos los** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">**dominios**</a> **de configuración** > .
1. A continuación, elija el dominio predeterminado.
1. Seleccione **Continuar configuración** y, a continuación, para conectar el dominio, elija  **Continuar**.
1. Desplácese hacia abajo para ver los registros DNS que deben copiarse en Google.
1. Abra **Registros MX** y, en **Puntos para dirección o valor**, copie el registro.
1. Vuelva a Google y, en la sección **Registros de recursos personalizados** , abra la lista desplegable Tipo de registro y seleccione **MX**.
1. En el campo **Datos** , pegue el registro que copió.
1. A continuación, seleccione **Aceptar**.
1. Repita el proceso para los registros CNAME y TXT y agregue los valores en la página de administración de DNS de Google.
1. Vuelva al Centro de administración de Microsoft 365 y seleccione **Continuar**.

    La configuración del dominio está completa.