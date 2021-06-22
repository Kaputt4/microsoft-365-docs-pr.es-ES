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
ms.openlocfilehash: f2258b165c3d61f809288003f4a536ffe160ea59
ms.sourcegitcommit: d34cac68537d6e1c65be757956646e73dea6e1ab
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/22/2021
ms.locfileid: "53061827"
---
# <a name="step-1---prevent-a-former-employee-from-logging-in-and-block-access-to-microsoft-365-services"></a><span data-ttu-id="da9bc-103">Paso 1: impedir que un antiguo empleado inicia sesión y bloquee el acceso a Microsoft 365 servicios</span><span class="sxs-lookup"><span data-stu-id="da9bc-103">Step 1 - Prevent a former employee from logging in and block access to Microsoft 365 services</span></span>

<span data-ttu-id="da9bc-104">Si necesita impedir inmediatamente el acceso de inicio de sesión de un usuario, debe restablecer su contraseña.</span><span class="sxs-lookup"><span data-stu-id="da9bc-104">If you need to immediately prevent a user's sign-in access, you should reset their password.</span></span> <span data-ttu-id="da9bc-105">En este paso, fuerza la salida del usuario de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="da9bc-105">In this step, force a sign out of the user from Microsoft 365.</span></span>

> [!NOTE]
> <span data-ttu-id="da9bc-106">Debe ser un administrador global para iniciar el inicio de sesión para otros administradores.</span><span class="sxs-lookup"><span data-stu-id="da9bc-106">You need to be a global administrator to initiate sign-out for other administrators.</span></span> <span data-ttu-id="da9bc-107">Para usuarios que no son administradores, puede usar un administrador de usuarios o un usuario de administrador del departamento de soporte técnico para realizar esta acción.</span><span class="sxs-lookup"><span data-stu-id="da9bc-107">For non administrator users, you can use a User Administrator or a Helpdesk Administrator user to perform this action.</span></span> [<span data-ttu-id="da9bc-108">Más información sobre los roles de administrador</span><span class="sxs-lookup"><span data-stu-id="da9bc-108">Learn more about the Admin Roles</span></span>](about-admin-roles.md)

1. <span data-ttu-id="da9bc-109">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="da9bc-109">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="da9bc-110">Seleccione el cuadro situado junto al nombre del usuario y, a continuación, seleccione **Restablecer contraseña.**</span><span class="sxs-lookup"><span data-stu-id="da9bc-110">Select the box next to the user's name, and then select **Reset password**.</span></span>
3. <span data-ttu-id="da9bc-111">Escriba una nueva contraseña y, a continuación, **seleccione Restablecer**.</span><span class="sxs-lookup"><span data-stu-id="da9bc-111">Enter a new password, and then select **Reset**.</span></span> <span data-ttu-id="da9bc-112">(No se lo envíe).</span><span class="sxs-lookup"><span data-stu-id="da9bc-112">(Don't send it to them.)</span></span>
4. <span data-ttu-id="da9bc-113">Seleccione el nombre del usuario para ir al  panel de propiedades y, en la pestaña Cuenta, seleccione **Cerrar sesión de todas las sesiones**.</span><span class="sxs-lookup"><span data-stu-id="da9bc-113">Select the user's name to go to their properties pane, and on the **Account** tab, select **Sign out of all sessions**.</span></span>

<span data-ttu-id="da9bc-114">Dentro de una hora , o después de salir de la página Microsoft 365 actual en la que se encuentran, se les pedirá que inicien sesión de nuevo.</span><span class="sxs-lookup"><span data-stu-id="da9bc-114">Within an hour - or after they leave the current Microsoft 365 page they are on - they're prompted to sign in again.</span></span> <span data-ttu-id="da9bc-115">Un token de acceso es bueno durante una hora, por lo que la escala de tiempo depende de cuánto tiempo queda en ese token y de si navegan fuera de su página web actual.</span><span class="sxs-lookup"><span data-stu-id="da9bc-115">An access token is good for an hour, so the timeline depends on how much time is left on that token, and whether they navigate out of their current webpage.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="da9bc-116">Si el usuario está en Outlook en la Web, simplemente haciendo clic en su buzón, es posible que no se eche inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="da9bc-116">If the user is in Outlook on the web, just clicking around in their mailbox, they may not be kicked out immediately.</span></span> <span data-ttu-id="da9bc-117">Tan pronto como seleccionen un icono diferente, como OneDrive, o actualicen su explorador, se inicia el inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="da9bc-117">As soon as they select a different tile, such as OneDrive, or refresh their browser, the sign-out is initiated.</span></span>
  
<span data-ttu-id="da9bc-118">Para usar PowerShell para cerrar la sesión de un usuario inmediatamente, consulte el cmdlet [Revoke-AzureADUserAllRefreshToken.](/powershell/module/azuread/revoke-azureaduserallrefreshtoken)</span><span class="sxs-lookup"><span data-stu-id="da9bc-118">To use PowerShell to sign out a user immediately, see the [Revoke-AzureADUserAllRefreshToken](/powershell/module/azuread/revoke-azureaduserallrefreshtoken) cmdlet.</span></span>
  
<span data-ttu-id="da9bc-119">Para obtener más información sobre cuánto se tarda en quitar a un usuario del correo, vea [Todo lo que debe saber sobre el cierre de la sesión de un empleado](remove-former-employee-step-7.md#what-you-need-to-know-about-terminating-an-employees-email-session).</span><span class="sxs-lookup"><span data-stu-id="da9bc-119">For more information about how long it takes to get someone out of email, see [What you need to know about terminating an employee's email session](remove-former-employee-step-7.md#what-you-need-to-know-about-terminating-an-employees-email-session).</span></span>

## <a name="block-a-former-employees-access-to-microsoft-365-services"></a><span data-ttu-id="da9bc-120">Bloquear el acceso de un antiguo empleado a Microsoft 365 servicios</span><span class="sxs-lookup"><span data-stu-id="da9bc-120">Block a former employee's access to Microsoft 365 services</span></span>

> [!IMPORTANT]
 > <span data-ttu-id="da9bc-121">El bloqueo de una cuenta puede tardar hasta 24 horas en tener efecto.</span><span class="sxs-lookup"><span data-stu-id="da9bc-121">Blocking an account can take up to 24 hours to take effect.</span></span> <span data-ttu-id="da9bc-122">Si necesita impedir inmediatamente el acceso de inicio de sesión de un usuario, siga los pasos anteriores y restablezca su contraseña.</span><span class="sxs-lookup"><span data-stu-id="da9bc-122">If you need to immediately prevent a user's sign-in access, follow the steps above and reset their password.</span></span>

1. <span data-ttu-id="da9bc-123">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="da9bc-123">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="da9bc-124">Seleccione el nombre del empleado que desea bloquear y, bajo el nombre del usuario, seleccione el símbolo para **Bloquear este usuario**.</span><span class="sxs-lookup"><span data-stu-id="da9bc-124">Select the name of the employee that you want to block, and under the user's name, select the symbol for **Block this user**.</span></span>
3. <span data-ttu-id="da9bc-125">Seleccione **Bloquear al usuario para que no inicie sesión** y, a continuación, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="da9bc-125">Select **Block the user from signing in**, and then select **Save**.</span></span>

## <a name="block-a-former-employees-access-to-email-exchange-online"></a><span data-ttu-id="da9bc-126">Bloquear el acceso de un antiguo empleado al correo electrónico (Exchange Online)</span><span class="sxs-lookup"><span data-stu-id="da9bc-126">Block a former employee's access to email (Exchange Online)</span></span>

<span data-ttu-id="da9bc-127">Si tiene correo electrónico como parte de su suscripción Microsoft 365, inicie sesión en el Centro de administración de Exchange y siga estos pasos para impedir que el antiguo empleado tenga acceso a su correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="da9bc-127">If you have email as part of your Microsoft 365 subscription, sign in to the Exchange admin center and follow these steps to block your former employee from accessing their email.</span></span>
  
1. <span data-ttu-id="da9bc-128">Vaya al <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Centro de administración de Exchange</a>.</span><span class="sxs-lookup"><span data-stu-id="da9bc-128">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>
2. <span data-ttu-id="da9bc-129">En el Centro de administración de Exchange, vaya a **Destinatarios** \> **Buzones**.</span><span class="sxs-lookup"><span data-stu-id="da9bc-129">In the Exchange admin center, navigate to **Recipients** \> **Mailboxes**.</span></span>
3. <span data-ttu-id="da9bc-130">Haga doble clic en el usuario y vaya a la página **Características del buzón.**</span><span class="sxs-lookup"><span data-stu-id="da9bc-130">Double-click the user and go to the **Mailbox features** page.</span></span> <span data-ttu-id="da9bc-131">En **Dispositivos móviles,** **selecciona Deshabilitar Exchange ActiveSync** y Deshabilitar **OWA** para dispositivos y responde **Sí** a ambos cuando se le pida.</span><span class="sxs-lookup"><span data-stu-id="da9bc-131">Under **Mobile Devices**, select **Disable Exchange ActiveSync** and **Disable OWA for Devices,** and answer **Yes** to both when prompted.</span></span>
4. <span data-ttu-id="da9bc-132">En **Conectividad de correo** electrónico, seleccione **Deshabilitar** y responder **Sí** cuando se le pida.</span><span class="sxs-lookup"><span data-stu-id="da9bc-132">Under **Email Connectivity**, select **Disable** and answer **Yes** when prompted.</span></span>
