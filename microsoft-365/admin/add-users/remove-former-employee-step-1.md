---
title: 'Paso 1: impedir que un empleado inicia sesión en Microsoft 365'
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
- Adm_TOC
- SPO_Content
ms.custom:
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Bloquear el acceso a los servicios Microsoft 365 un antiguo empleado.
ms.openlocfilehash: cdba6dcaf239e94cf33f3bf88e7f217b4793bfd6
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2021
ms.locfileid: "52840855"
---
# <a name="step-1---prevent-a-former-employee-from-logging-in-and-block-access-to-microsoft-365-services"></a>Paso 1: impedir que un antiguo empleado inicia sesión y bloquee el acceso a Microsoft 365 servicios

Si necesita impedir inmediatamente el acceso de inicio de sesión de un usuario, debe restablecer su contraseña. En este paso, fuerza la salida del usuario de Microsoft 365.

> [!NOTE]
> Debe ser un administrador global para iniciar el inicio de sesión para otros administradores. Para usuarios que no son administradores, puede usar un administrador de usuarios o un usuario de administrador del departamento de soporte técnico para realizar esta acción. [Más información sobre los roles de administrador](about-admin-roles.md)

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.
2. Seleccione el cuadro situado junto al nombre del usuario y, a continuación, seleccione **Restablecer contraseña.**
3. Escriba una nueva contraseña y, a continuación, **seleccione Restablecer**. (No se lo envíe).
4. Seleccione el nombre del usuario para ir al panel de propiedades y, en la pestaña **Cuenta,** seleccione **Iniciar la sesión.**

Dentro de una hora , o después de salir de la página Microsoft 365 actual en la que se encuentran, se les pedirá que inicien sesión de nuevo. Un token de acceso es bueno durante una hora, por lo que la escala de tiempo depende de cuánto tiempo queda en ese token y de si navegan fuera de su página web actual.
  
> [!IMPORTANT]
> Si el usuario está en Outlook en la web, haciendo clic en su buzón, es posible que no se eche inmediatamente. Tan pronto como seleccionen un icono diferente, como OneDrive, o actualicen su explorador, se inicia el inicio de sesión.
  
Para usar PowerShell para cerrar la sesión de un usuario inmediatamente, consulte el cmdlet [Revoke-AzureADUserAllRefreshToken.](/powershell/module/azuread/revoke-azureaduserallrefreshtoken)
  
Para obtener más información sobre cuánto se tarda en quitar a un usuario del correo, vea [Todo lo que debe saber sobre el cierre de la sesión de un empleado](remove-former-employee-step-7.md#what-you-need-to-know-about-terminating-an-employees-email-session).

## <a name="block-a-former-employees-access-to-microsoft-365-services"></a>Bloquear el acceso de un antiguo empleado a Microsoft 365 servicios

> [!IMPORTANT]
 > El bloqueo de una cuenta puede tardar hasta 24 horas en tener efecto. Si necesita impedir inmediatamente el acceso de inicio de sesión de un usuario, siga los pasos anteriores y restablezca su contraseña.

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.
2. Seleccione el nombre del empleado que desea bloquear y, bajo el nombre del usuario, seleccione el símbolo para **Bloquear este usuario**.
3. Seleccione **Bloquear al usuario para que no inicie sesión** y, a continuación, seleccione **Guardar**.

## <a name="block-a-former-employees-access-to-email-exchange-online"></a>Bloquear el acceso de un antiguo empleado al correo electrónico (Exchange Online)

Si tiene correo electrónico como parte de su suscripción Microsoft 365, inicie sesión en el Centro de administración de Exchange y siga estos pasos para impedir que el antiguo empleado tenga acceso a su correo electrónico.
  
1. Vaya al <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Centro de administración de Exchange</a>.
2. En el Centro de administración de Exchange, vaya a **Destinatarios** \> **Buzones**.
3. Haga doble clic en el usuario y vaya a la página **Características del buzón.** En **Dispositivos móviles,** **selecciona Deshabilitar Exchange ActiveSync** y Deshabilitar **OWA** para dispositivos y responde **Sí** a ambos cuando se le pida.
4. En **Conectividad de correo** electrónico, seleccione **Deshabilitar** y responder **Sí** cuando se le pida.
