---
title: 'Paso 1: Impedir que un antiguo empleado inicie sesión y bloquee el acceso a los servicios de Microsoft 365'
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- Tier1
- scotvorg
- M365-subscription-management
- Adm_O365
- Adm_TOC
- SPO_Content
ms.custom:
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
- m365solution-removeemployee
- admindeeplinkEXCHANGE
search.appverid:
- BCS160
- MET150
- MOE150
description: Los administradores globales pueden impedir que un antiguo empleado inicie sesión y bloquear su acceso a los servicios de Microsoft 365.
ms.openlocfilehash: 6f59c4295f98164c152e2b42ddf08a07d8bc9eee
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2022
ms.locfileid: "68721788"
---
# <a name="step-1---prevent-a-former-employee-from-logging-in-and-block-access-to-microsoft-365-services"></a>Paso 1: Impedir que un antiguo empleado inicie sesión y bloquee el acceso a los servicios de Microsoft 365

Si necesita impedir inmediatamente el acceso de inicio de sesión de un usuario, debe restablecer su contraseña. En este paso, fuerce el cierre de sesión del usuario de Microsoft 365.

> [!NOTE]
> Debe ser administrador global para iniciar el cierre de sesión de otros administradores. Para los usuarios que no son administradores, puede usar un administrador de usuarios o un usuario de administrador del departamento de soporte técnico para realizar esta acción. [Más información sobre los roles de Administración](about-admin-roles.md)

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.
2. Seleccione el cuadro situado junto al nombre del usuario y, a continuación, seleccione **Restablecer contraseña**.
3. Escriba una nueva contraseña y, a continuación, seleccione **Restablecer**. (No se lo envíes).
4. Seleccione el nombre del usuario para ir al panel de propiedades y, en la pestaña **Cuenta** , seleccione **Cerrar sesión de todas las sesiones**.

En un plazo de una hora, o después de salir de la página actual de Microsoft 365 en la que se encuentra, se les pedirá que vuelvan a iniciar sesión. Un token de acceso es bueno durante una hora, por lo que la escala de tiempo depende de cuánto tiempo queda en ese token y de si salen de su página web actual.
  
> [!IMPORTANT]
> Si el usuario está en Outlook en la Web, simplemente haciendo clic en su buzón, es posible que no se le eche inmediatamente. En cuanto seleccionan un icono diferente, como OneDrive, o actualizan su explorador, se inicia el cierre de sesión.
  
Para usar PowerShell para cerrar la sesión de un usuario inmediatamente, consulte el cmdlet [Revoke-AzureADUserAllRefreshToken](/powershell/module/azuread/revoke-azureaduserallrefreshtoken) .
  
Para obtener más información sobre cuánto se tarda en quitar a un usuario del correo, vea [Todo lo que debe saber sobre el cierre de la sesión de un empleado](remove-former-employee-step-7.md#what-you-need-to-know-about-terminating-an-employees-email-session).

## <a name="block-a-former-employees-access-to-microsoft-365-services"></a>Bloquear el acceso de un antiguo empleado a los servicios de Microsoft 365

> [!IMPORTANT]
 > Bloquear una cuenta puede tardar hasta 24 horas en surtir efecto. Si necesita impedir inmediatamente el acceso de inicio de sesión de un usuario, siga los pasos anteriores y restablezca su contraseña.

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.
2. Seleccione el nombre del empleado que desea bloquear y, bajo el nombre del usuario, seleccione el símbolo **Bloquear este usuario**.
3. Seleccione **Bloquear el inicio de sesión del usuario** y, a continuación, seleccione **Guardar**.

## <a name="block-a-former-employees-access-to-email-exchange-online"></a>Bloquear el acceso de un antiguo empleado al correo electrónico (Exchange Online)

Si tiene correo electrónico como parte de su suscripción a Microsoft 365, inicie sesión en el <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Centro de administración de Exchange</a> y siga estos pasos para impedir que el antiguo empleado acceda a su correo electrónico.
  
1. Vaya al Centro de administración de Exchange > **buzones de destinatarios**\>.<a href="https://go.microsoft.com/fwlink/?linkid=2183135" target="_blank"></a>
1. Seleccione el buzón de usuario de la lista y, a continuación, en el *panel Detalles* (en el lado derecho), seleccione **Administrar la configuración de aplicaciones de correo electrónico** en **Email aplicaciones**. **Desactive** el control deslizante para todas las opciones; **Dispositivos móviles (Exchange ActiveSync),** **Outlook en la Web**, **escritorio de Outlook (MAPI),** **servicios web de Exchange**, **POP3** e **IMAP**.
1. Seleccione **Guardar**.

## <a name="related-content"></a>Contenido relacionado

[Centro de administración de Exchange en Exchange Online](/exchange/exchange-admin-center) (artículo)\

[Restauración de un usuario](restore-user.md) (artículo)
