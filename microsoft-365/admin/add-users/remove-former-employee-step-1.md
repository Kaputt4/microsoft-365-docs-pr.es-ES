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
ms.openlocfilehash: 8eb41c3b449e63284371aaf168262307a4c21941
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2021
ms.locfileid: "52535955"
---
# <a name="step-1---prevent-a-former-employee-from-logging-in-and-block-access-to-microsoft-365-services"></a><span data-ttu-id="441cd-103">Paso 1: impedir que un antiguo empleado inicia sesión y bloquee el acceso a Microsoft 365 servicios</span><span class="sxs-lookup"><span data-stu-id="441cd-103">Step 1 - Prevent a former employee from logging in and block access to Microsoft 365 services</span></span>

<span data-ttu-id="441cd-104">Si necesita impedir inmediatamente el acceso de inicio de sesión de un usuario, debe restablecer su contraseña.</span><span class="sxs-lookup"><span data-stu-id="441cd-104">If you need to immediately prevent a user's sign-in access, you should reset their password.</span></span> <span data-ttu-id="441cd-105">En este paso, fuerza la salida del usuario de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="441cd-105">In this step, force a sign out of the user from Microsoft 365.</span></span>

> [!NOTE]
> <span data-ttu-id="441cd-106">Debe ser un administrador global para iniciar la sesión.</span><span class="sxs-lookup"><span data-stu-id="441cd-106">You need to be a global administrator to initiate sign-out.</span></span>

1. <span data-ttu-id="441cd-107">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="441cd-107">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="441cd-108">Seleccione el cuadro situado junto al nombre del usuario y, a continuación, seleccione **Restablecer contraseña.**</span><span class="sxs-lookup"><span data-stu-id="441cd-108">Select the box next to the user's name, and then select **Reset password**.</span></span>
3. <span data-ttu-id="441cd-109">Escriba una nueva contraseña y, a continuación, **seleccione Restablecer**.</span><span class="sxs-lookup"><span data-stu-id="441cd-109">Enter a new password, and then select **Reset**.</span></span> <span data-ttu-id="441cd-110">(No se lo envíe).</span><span class="sxs-lookup"><span data-stu-id="441cd-110">(Don't send it to them.)</span></span>
4. <span data-ttu-id="441cd-111">Seleccione el nombre del usuario para ir al panel de propiedades y, en la pestaña **Cuenta,** seleccione **Iniciar la sesión.**</span><span class="sxs-lookup"><span data-stu-id="441cd-111">Select the user's name to go to their properties pane, and on the **Account** tab, select **Initiate sign-out**.</span></span>

<span data-ttu-id="441cd-112">Dentro de una hora , o después de salir de la página Microsoft 365 actual en la que se encuentran, se les pedirá que inicien sesión de nuevo.</span><span class="sxs-lookup"><span data-stu-id="441cd-112">Within an hour - or after they leave the current Microsoft 365 page they are on - they're prompted to sign in again.</span></span> <span data-ttu-id="441cd-113">Un token de acceso es bueno durante una hora, por lo que la escala de tiempo depende de cuánto tiempo queda en ese token y de si navegan fuera de su página web actual.</span><span class="sxs-lookup"><span data-stu-id="441cd-113">An access token is good for an hour, so the timeline depends on how much time is left on that token, and whether they navigate out of their current webpage.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="441cd-114">Si el usuario está en Outlook en la web, haciendo clic en su buzón, es posible que no se eche inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="441cd-114">If the user is in Outlook on the web, just clicking around in their mailbox, they may not be kicked out immediately.</span></span> <span data-ttu-id="441cd-115">Tan pronto como seleccionen un icono diferente, como OneDrive, o actualicen su explorador, se inicia el inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="441cd-115">As soon as they select a different tile, such as OneDrive, or refresh their browser, the sign-out is initiated.</span></span>
  
<span data-ttu-id="441cd-116">Para usar PowerShell para cerrar la sesión de un usuario inmediatamente, consulte el cmdlet [Revoke-AzureADUserAllRefreshToken.](/powershell/module/azuread/revoke-azureaduserallrefreshtoken)</span><span class="sxs-lookup"><span data-stu-id="441cd-116">To use PowerShell to sign out a user immediately, see the [Revoke-AzureADUserAllRefreshToken](/powershell/module/azuread/revoke-azureaduserallrefreshtoken) cmdlet.</span></span>
  
<span data-ttu-id="441cd-117">Para obtener más información sobre cuánto se tarda en quitar a un usuario del correo, vea [Todo lo que debe saber sobre el cierre de la sesión de un empleado](remove-former-employee-step-7.md#what-you-need-to-know-about-terminating-an-employees-email-session).</span><span class="sxs-lookup"><span data-stu-id="441cd-117">For more information about how long it takes to get someone out of email, see [What you need to know about terminating an employee's email session](remove-former-employee-step-7.md#what-you-need-to-know-about-terminating-an-employees-email-session).</span></span>

## <a name="block-a-former-employees-access-to-microsoft-365-services"></a><span data-ttu-id="441cd-118">Bloquear el acceso de un antiguo empleado a Microsoft 365 servicios</span><span class="sxs-lookup"><span data-stu-id="441cd-118">Block a former employee's access to Microsoft 365 services</span></span>

> [!IMPORTANT]
 > <span data-ttu-id="441cd-119">El bloqueo de una cuenta puede tardar hasta 24 horas en tener efecto.</span><span class="sxs-lookup"><span data-stu-id="441cd-119">Blocking an account can take up to 24 hours to take effect.</span></span> <span data-ttu-id="441cd-120">Si necesita impedir inmediatamente el acceso de inicio de sesión de un usuario, siga los pasos anteriores y restablezca su contraseña.</span><span class="sxs-lookup"><span data-stu-id="441cd-120">If you need to immediately prevent a user's sign-in access, follow the steps above and reset their password.</span></span>

1. <span data-ttu-id="441cd-121">En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.</span><span class="sxs-lookup"><span data-stu-id="441cd-121">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="441cd-122">Seleccione el nombre del empleado que desea bloquear y, bajo el nombre del usuario, seleccione el símbolo para **Bloquear este usuario**.</span><span class="sxs-lookup"><span data-stu-id="441cd-122">Select the name of the employee that you want to block, and under the user's name, select the symbol for **Block this user**.</span></span>
3. <span data-ttu-id="441cd-123">Seleccione **Bloquear al usuario para que no inicie sesión** y, a continuación, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="441cd-123">Select **Block the user from signing in**, and then select **Save**.</span></span>

## <a name="block-a-former-employees-access-to-email-exchange-online"></a><span data-ttu-id="441cd-124">Bloquear el acceso de un antiguo empleado al correo electrónico (Exchange Online)</span><span class="sxs-lookup"><span data-stu-id="441cd-124">Block a former employee's access to email (Exchange Online)</span></span>

<span data-ttu-id="441cd-125">Si tiene correo electrónico como parte de su suscripción Microsoft 365, inicie sesión en el Centro de administración de Exchange y siga estos pasos para impedir que el antiguo empleado tenga acceso a su correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="441cd-125">If you have email as part of your Microsoft 365 subscription, sign in to the Exchange admin center and follow these steps to block your former employee from accessing their email.</span></span>
  
1. <span data-ttu-id="441cd-126">Vaya al <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Centro de administración de Exchange</a>.</span><span class="sxs-lookup"><span data-stu-id="441cd-126">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>
2. <span data-ttu-id="441cd-127">En el Centro de administración de Exchange, vaya a **Destinatarios** \> **Buzones**.</span><span class="sxs-lookup"><span data-stu-id="441cd-127">In the Exchange admin center, navigate to **Recipients** \> **Mailboxes**.</span></span>
3. <span data-ttu-id="441cd-128">Haga doble clic en el usuario y vaya a la página **Características del buzón.**</span><span class="sxs-lookup"><span data-stu-id="441cd-128">Double-click the user and go to the **Mailbox features** page.</span></span> <span data-ttu-id="441cd-129">En **Dispositivos móviles,** **selecciona Deshabilitar Exchange ActiveSync** y Deshabilitar **OWA** para dispositivos y responde **Sí** a ambos cuando se le pida.</span><span class="sxs-lookup"><span data-stu-id="441cd-129">Under **Mobile Devices**, select **Disable Exchange ActiveSync** and **Disable OWA for Devices,** and answer **Yes** to both when prompted.</span></span>
4. <span data-ttu-id="441cd-130">En **Conectividad de correo** electrónico, seleccione **Deshabilitar** y responder **Sí** cuando se le pida.</span><span class="sxs-lookup"><span data-stu-id="441cd-130">Under **Email Connectivity**, select **Disable** and answer **Yes** when prompted.</span></span>
