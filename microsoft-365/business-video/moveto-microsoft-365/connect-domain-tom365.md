---
title: Conectar su dominio a Microsoft 365
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
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
- admindeeplinkMAC
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Obtenga información sobre cómo conectar su dominio a Microsoft 365.
ms.openlocfilehash: 377bb0444582f8efe15583fa522eceb9d675e474
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/12/2021
ms.locfileid: "59211270"
---
# <a name="connect-your-domain-to-microsoft-365-for-business"></a>Conectar el dominio para Microsoft 365 para empresas

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LFpy?autoplay=false]

Una vez que hayas configurado Microsoft 365 y movido los datos de correo electrónico desde Google Workspace, puedes conectar tu dominio a Microsoft 365. 

Primero tendrá que eliminar los registros DNS existentes de Google y, a continuación, podemos agregar nuevos registros DNS desde Microsoft 365.

## <a name="try-it"></a>¿Se atreve?

1. Inicie sesión en la consola de administración de Google Workspace [en admin.google.com](https://admin.google.com).
1. Seleccione **Dominios**, **Administrar dominios**, Ver **detalles**, Administrar **dominio** y, a continuación, **DNS** en la navegación izquierda.
1. Desplácese hacia abajo **hasta Registros sintéticos,** abra **Google Workspace**, **seleccione Eliminar** y, a continuación, **Vuelva a** eliminar.
1. Desplácese hacia abajo **hasta Registros de** recursos personalizados y elimine los registros DNS existentes que aparezcan, incluidos los que haya creado anteriormente para Microsoft 365.
1. Vaya a la [Centro de administración de Microsoft 365](https://admin.microsoft.com).
1. En el panel de navegación izquierdo, elija Mostrar  >  **todos los Configuración**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">**dominios**</a>.
1. A continuación, elija el dominio predeterminado.
1. Seleccione **Continuar la configuración** y, a continuación, para conectar el dominio, elija  **Continuar**.
1. Desplácese hacia abajo para ver los registros DNS que deben copiarse en Google.
1. Abra **Registros MX** y, en Puntos para dirección o **valor,** copie el registro.
1. Vuelva a Google y, en la sección Registros de recursos **personalizados,** abra el desplegable tipo de registro y seleccione **MX**.
1. En el **campo Datos,** pegue el registro que copió.
1. A continuación, seleccione **Aceptar**.
1. Repita el proceso para los registros CNAME y TXT y agregue los valores en la página de administración de DNS de Google.
1. Vuelva a la Centro de administración de Microsoft 365 y seleccione **Continuar**.

    La configuración del dominio se ha completado.