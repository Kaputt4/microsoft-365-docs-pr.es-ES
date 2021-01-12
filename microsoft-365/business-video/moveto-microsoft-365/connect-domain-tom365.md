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
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Obtenga información sobre cómo conectar su dominio a Microsoft 365.
ms.openlocfilehash: c7827b93b56560579b31bd2abb5a852467565103
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794707"
---
# <a name="connect-your-domain-to-microsoft-365-for-business"></a>Conectar su dominio a Microsoft 365 para empresas

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LFpy?autoplay=false]

Una vez que haya configurado Microsoft 365 y movido los datos de correo electrónico de Google Workspace, puede conectar su dominio a Microsoft 365. 

Primero tendrá que eliminar los registros DNS existentes de Google y, a continuación, podemos agregar nuevos registros DNS de Microsoft 365.

## <a name="try-it"></a>¿Se atreve?

1. Inicie sesión en la consola de administración de Google Workspace [en admin.google.com.](https://admin.google.com)
1. Seleccione **Dominios**, **Administrar dominios**, Ver **detalles,** **Administrar dominio** y, a continuación, **DNS** en el panel de navegación izquierdo.
1. Desplácese hacia abajo **hasta registros sintéticos,** **abra Google Workspace,** **seleccione Eliminar** y, a continuación, **vuelva a** eliminar.
1. Desplácese hacia abajo **hasta Registros** de recursos personalizados y elimine los registros DNS existentes que aparezcan, incluidos los que haya creado anteriormente para Microsoft 365.
1. Vaya al Centro [de administración de Microsoft 365.](https://admin.microsoft.com)
1. En el panel de navegación izquierdo, elija Mostrar **todo**, **Configuración**, **Dominios**.
1. A continuación, elija su dominio predeterminado.
1. Seleccione **Continuar configuración** y, a continuación, para conectar su dominio, elija  **Continuar**.
1. Desplácese hacia abajo para ver los registros DNS que deben copiarse en Google.
1. Abra **Registros MX** y, en Puntos para dirección o **valor,** copie el registro.
1. Vuelva a Google y, en la sección Registros de **recursos personalizados,** abra la lista desplegable de tipos de registro y seleccione **MX**.
1. En el **campo** Datos, pegue el registro que copió.
1. A continuación, seleccione **Aceptar**.
1. Repita el proceso para los registros CNAME y TXT y agregue los valores en la página de administración de DNS de Google.
1. Vuelva al Centro de administración de Microsoft 365 y seleccione **Continuar.**

    La configuración del dominio se ha completado.