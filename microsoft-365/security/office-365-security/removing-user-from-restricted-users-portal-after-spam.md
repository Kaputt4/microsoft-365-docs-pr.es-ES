---
title: Quitar usuarios bloqueados del portal de Usuarios restringidos
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
f1_keywords:
- ms.exch.eac.ActionCenter.Restricted.Users.RestrictedUsers
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 712cfcc1-31e8-4e51-8561-b64258a8f1e5
ms.collection:
- M365-security-compliance
description: Los administradores pueden aprender a quitar usuarios de la página Usuarios restringidos en el portal de Microsoft 365 Defender. Se agregan usuarios al portal de Usuarios restringidos para el envío correo no deseado saliente, normalmente porque la cuenta se ha visto comprometida.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 924db948103a4d3b45c499f433961762a45931af
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2021
ms.locfileid: "53082857"
---
# <a name="remove-blocked-users-from-the-restricted-users-portal-in-microsoft-365"></a><span data-ttu-id="bbc38-104">Quitar usuarios bloqueados del portal de Usuarios restringidos en Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="bbc38-104">Remove blocked users from the Restricted users portal in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="bbc38-105">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="bbc38-105">**Applies to**</span></span>
- [<span data-ttu-id="bbc38-106">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="bbc38-106">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="bbc38-107">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="bbc38-107">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="bbc38-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bbc38-108">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="bbc38-109">Si un usuario supera uno de los límites de envío saliente, como se especifica en [límites del servicio](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) o en [directivas de correo no deseado saliente](configure-the-outbound-spam-policy.md), el usuario no puede enviar correos electrónicos, pero aún podrá recibirlos.</span><span class="sxs-lookup"><span data-stu-id="bbc38-109">If a user exceeds one of the outbound sending limits as specified in [the service limits](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) or in [outbound spam policies](configure-the-outbound-spam-policy.md), the user is restricted from sending email, but they can still receive email.</span></span>

<span data-ttu-id="bbc38-110">El usuario se agrega a la página **Usuarios restringidos** en el portal de Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="bbc38-110">The user is added to the **Restricted users** page in the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="bbc38-111">Al intentar enviar un correo electrónico, el mensaje se devuelve en un informe de no entrega (también conocido como NDR o mensajes de devolución) con el código de error [5.1.8](/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/fix-error-code-5-1-8-in-exchange-online) y el texto siguiente:</span><span class="sxs-lookup"><span data-stu-id="bbc38-111">When they try to send email, the message is returned in a non-delivery report (also known as an NDR or bounce messages) with the error code [5.1.8](/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/fix-error-code-5-1-8-in-exchange-online) and the following text:</span></span>

> <span data-ttu-id="bbc38-112">"No se pudo entregar el mensaje porque el remitente no es válido.</span><span class="sxs-lookup"><span data-stu-id="bbc38-112">"Your message couldn't be delivered because you weren't recognized as a valid sender.</span></span> <span data-ttu-id="bbc38-113">La razón más común para este caso es que la dirección de correo electrónico sea sospechosa de que está enviando correo no deseado y ya no se le permite enviar correo.</span><span class="sxs-lookup"><span data-stu-id="bbc38-113">The most common reason for this is that your email address is suspected of sending spam and it's no longer allowed to send email.</span></span>  <span data-ttu-id="bbc38-114">Póngase en contacto con su administrador, para obtener ayuda.</span><span class="sxs-lookup"><span data-stu-id="bbc38-114">Contact  your email admin for assistance.</span></span> <span data-ttu-id="bbc38-115">El servidor remoto devolvió "550 5.1.8 acceso denegado, remitente incorrecto de correo saliente".</span><span class="sxs-lookup"><span data-stu-id="bbc38-115">Remote Server returned '550 5.1.8 Access denied, bad outbound sender."</span></span>

<span data-ttu-id="bbc38-116">Los administradores pueden quitar usuarios de la página Usuarios restringidos en Microsoft 365 Defender o en PowerShell de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="bbc38-116">Admins can remove users from the Restricted users page in the Microsoft 365 Defender or in Exchange Online PowerShell.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="bbc38-117">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="bbc38-117">What do you need to know before you begin?</span></span>

- <span data-ttu-id="bbc38-118">Abra el portal de Microsoft 365 Defender en <https://security.microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="bbc38-118">You open the Microsoft 365 Defender portal at <https://security.microsoft.com>.</span></span> <span data-ttu-id="bbc38-119">Para ir directamente a la página **Usuarios restringidos**, use <https://security.microsoft.com/restrictedusers>.</span><span class="sxs-lookup"><span data-stu-id="bbc38-119">Too go directly to the **Restricted users** page, use <https://security.microsoft.com/restrictedusers>.</span></span>

- <span data-ttu-id="bbc38-120">Para conectarse al PowerShell de Exchange Online, consulte [Conectarse a PowerShell de Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="bbc38-120">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="bbc38-121">Debe tener permisos asignados en la **Exchange Online** antes de poder realizar los procedimientos de este artículo:</span><span class="sxs-lookup"><span data-stu-id="bbc38-121">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="bbc38-122">Para quitar usuarios del portal de Usuarios restringidos, debe ser miembro de los grupos de roles **Administración de la organización** o **Administrador de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="bbc38-122">To remove users from the Restricted users portal, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="bbc38-123">Para obtener acceso de solo lectura al portal de Usuarios restringidos, tiene que ser miembro de los grupos de roles **Lector global** o **Lector de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="bbc38-123">For read-only access to the Restricted users portal, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="bbc38-124">Para obtener más información, vea los [permisos en Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="bbc38-124">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  >
  > - <span data-ttu-id="bbc38-125">Agregar usuarios al rol de Azure Active Directory correspondiente en el Centro de administración de Microsoft 365 la cual proporciona a los usuarios los permisos necesarios _y_ para otras características de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bbc38-125">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="bbc38-126">Para obtener más información, vea [Sobre los roles de administrador](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="bbc38-126">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  >
  > - <span data-ttu-id="bbc38-127">El grupo de roles **Administración de organización de solo lectura** en [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) también proporciona acceso de solo lectura a la característica.</span><span class="sxs-lookup"><span data-stu-id="bbc38-127">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="bbc38-128">Un remitente que supera los límites de correo electrónico saliente es un indicador de una cuenta comprometida.</span><span class="sxs-lookup"><span data-stu-id="bbc38-128">A sender exceeding the outbound email limits is an indicator of a compromised account.</span></span> <span data-ttu-id="bbc38-129">Antes de quitar el usuario del portal de Usuarios restringidos, asegúrese de seguir los pasos necesarios para recuperar el control de su cuenta.</span><span class="sxs-lookup"><span data-stu-id="bbc38-129">Before you remove the user from the Restricted users portal, be sure to follow the required steps to regain control of their account.</span></span> <span data-ttu-id="bbc38-130">Para obtener más información, consulte [Responder a una cuenta de correo electrónico comprometida en Office 365](responding-to-a-compromised-email-account.md).</span><span class="sxs-lookup"><span data-stu-id="bbc38-130">For more information, see [Responding to a compromised email account in Office 365](responding-to-a-compromised-email-account.md).</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-remove-a-user-from-the-restricted-users-list"></a><span data-ttu-id="bbc38-131">Usar el portal de Microsoft 365 Defender para quitar un usuario de la lista de Usuarios restringidos</span><span class="sxs-lookup"><span data-stu-id="bbc38-131">Use the Microsoft 365 Defender portal to remove a user from the Restricted users list</span></span>

1. <span data-ttu-id="bbc38-132">En el portal de Microsoft 365 Defender, vaya a **Correo electrónico y colaboración** > **Revisar** > **Usuarios restringidos**.</span><span class="sxs-lookup"><span data-stu-id="bbc38-132">In the Microsoft 365 Defender portal, go to **Email & collaboration** > **Review** > **Restricted users**.</span></span>

2. <span data-ttu-id="bbc38-133">En la página **Usuarios restringidos**, haga clic en el usuario que desea desbloquear para buscarlo y seleccionarlo.</span><span class="sxs-lookup"><span data-stu-id="bbc38-133">On the **Restricted users** page, find and select the user that you want to unblock by clicking on the user.</span></span>

3. <span data-ttu-id="bbc38-134">Haga clic en la acción **Desbloquear** que aparece.</span><span class="sxs-lookup"><span data-stu-id="bbc38-134">Click the **Unblock** action that appears.</span></span>

4. <span data-ttu-id="bbc38-135">En el control flotante **Desbloquear usuario** que aparece, lea los detalles sobre la cuenta restringida.</span><span class="sxs-lookup"><span data-stu-id="bbc38-135">In the **Unblock user** flyout that appears, read the details about the restricted account.</span></span> <span data-ttu-id="bbc38-136">Debe revisar las recomendaciones para asegurarse de que está llevando a cabo las acciones adecuadas en caso de que la cuenta se vea comprometida.</span><span class="sxs-lookup"><span data-stu-id="bbc38-136">You should go through the recommendations to ensure you're taking the proper actions in case the account is compromised.</span></span>

   <span data-ttu-id="bbc38-137">Cuando termine, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="bbc38-137">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="bbc38-138">En la siguiente pantalla encontrará recomendaciones para evitar que la cuenta se vea comprometida en el futuro.</span><span class="sxs-lookup"><span data-stu-id="bbc38-138">The next screen has recommendations to help prevent future compromise.</span></span> <span data-ttu-id="bbc38-139">Habilitar la autenticación multi factor (MFA) y restablecer la contraseña es una buena defensa.</span><span class="sxs-lookup"><span data-stu-id="bbc38-139">Enabling multi-factor authentication (MFA) and resetting the password are a good defense.</span></span>

   <span data-ttu-id="bbc38-140">Cuando haya terminado, haga clic en **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="bbc38-140">When you're finished, click **Submit**.</span></span>

6. <span data-ttu-id="bbc38-141">Haga clic en **Sí** para confirmar el cambio.</span><span class="sxs-lookup"><span data-stu-id="bbc38-141">Click **Yes** to confirm the change.</span></span>

   > [!NOTE]
   > <span data-ttu-id="bbc38-142">Puede que el usuario pasen hasta 24 horas hasta la eliminación de todas las restricciones del usuario.</span><span class="sxs-lookup"><span data-stu-id="bbc38-142">It might take up to 24 hours for all restrictions to be removed from the user.</span></span>

## <a name="verify-the-alert-settings-for-restricted-users"></a><span data-ttu-id="bbc38-143">Comprobar la configuración de alertas para usuarios restringidos</span><span class="sxs-lookup"><span data-stu-id="bbc38-143">Verify the alert settings for restricted users</span></span>

<span data-ttu-id="bbc38-144">La directiva de alerta predeterminada denominada **Usuario con restricción de envío de correo electrónico** notificará automáticamente a los administradores cuando se bloquee el envío de correo saliente por parte de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="bbc38-144">The default alert policy named **User restricted from sending email** will automatically notify admins when users are blocked from sending outbound mail.</span></span> <span data-ttu-id="bbc38-145">Puede comprobar esta configuración y agregar usuarios adicionales a los que notificar.</span><span class="sxs-lookup"><span data-stu-id="bbc38-145">You can verify these settings and add additional users to notify.</span></span> <span data-ttu-id="bbc38-146">Para obtener más información sobre las directivas de alerta, consulte [Directivas de alerta en Microsoft 365](../../compliance/alert-policies.md).</span><span class="sxs-lookup"><span data-stu-id="bbc38-146">For more information about alert policies, see [Alert policies in Microsoft 365](../../compliance/alert-policies.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bbc38-147">Para que las alertas funcionen, debe activarse la búsqueda de registros de auditoría.</span><span class="sxs-lookup"><span data-stu-id="bbc38-147">For alerts to work, audit log search must to be turned on.</span></span> <span data-ttu-id="bbc38-148">Para obtener más información, consulte [ Desactivar o activar la búsqueda de registros de auditoría](../../compliance/turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="bbc38-148">For more information, see [Turn the audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

1. <span data-ttu-id="bbc38-149">En el portal de Microsoft 365 Defender, vaya a **Correo electrónico y colaboración** \> **Directivas y reglas** \> **directiva de alertas**.</span><span class="sxs-lookup"><span data-stu-id="bbc38-149">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Policies & rules** \> **Alert policy**.</span></span>

2. <span data-ttu-id="bbc38-150">En la página **Directiva de alertas**, busque y seleccione la alerta denominada **Usuario no puede enviar correo electrónico**.</span><span class="sxs-lookup"><span data-stu-id="bbc38-150">On the **Alert policy** page, find and select the alert named **User restricted from sending email**.</span></span> <span data-ttu-id="bbc38-151">Puede ordenar las directivas por nombre o usar el **Cuadro de búsqueda** para buscar la directiva.</span><span class="sxs-lookup"><span data-stu-id="bbc38-151">You can sort the policies by name, or use the **Search box** to find the policy.</span></span>

3. <span data-ttu-id="bbc38-152">En el control flotante **Usuario no puede enviar correo electrónico** que aparece, compruebe o configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="bbc38-152">In the **User restricted from sending email** flyout that appears, verify or configure the following settings:</span></span>
   - <span data-ttu-id="bbc38-153">**Estado**: Compruebe que la alerta está activada![Activación](../../media/scc-toggle-on.png).</span><span class="sxs-lookup"><span data-stu-id="bbc38-153">**Status**: Verify the alert is turned on ![Toggle on](../../media/scc-toggle-on.png).</span></span>
   - <span data-ttu-id="bbc38-154">**Destinatarios de correo electrónico**: Haga clic en **Editar** y compruebe o configure las siguientes opciones en el control flotante **Editar destinatarios** que aparece:</span><span class="sxs-lookup"><span data-stu-id="bbc38-154">**Email recipients**: Click **Edit** and verify or configure the following settings in the **Edit recipients** flyout that appears:</span></span>
     - <span data-ttu-id="bbc38-155">**Enviar notificaciones por correo electrónico**: compruebe que está seleccionado (**Activado**).</span><span class="sxs-lookup"><span data-stu-id="bbc38-155">**Send email notifications**: Verify this is selected (**On**).</span></span>
     - <span data-ttu-id="bbc38-156">**Destinatarios de correo electrónico**: El valor predeterminado es **TenantAdmins** (lo que significa miembros de **Administrador global**).</span><span class="sxs-lookup"><span data-stu-id="bbc38-156">**Email recipients**: The default value is **TenantAdmins** (meaning, **Global admin** members).</span></span> <span data-ttu-id="bbc38-157">Para agregar más destinatarios, haga clic en un área en blanco del cuadro.</span><span class="sxs-lookup"><span data-stu-id="bbc38-157">To add more recipients, click in a blank area of the box.</span></span> <span data-ttu-id="bbc38-158">Se mostrará una lista de destinatarios y puede empezar a escribir un nombre para filtrar y seleccionar un destinatario.</span><span class="sxs-lookup"><span data-stu-id="bbc38-158">A list of recipients will appear, and you can start typing a name to filter and select a recipient.</span></span> <span data-ttu-id="bbc38-159">Para quitar un destinatario existente del cuadro, haga clic en el ![Icono quitar](../../media/m365-cc-sc-remove-selection-icon.png) junto a su nombre.</span><span class="sxs-lookup"><span data-stu-id="bbc38-159">You can remove an existing recipient from the box by clicking ![Remove icon](../../media/m365-cc-sc-remove-selection-icon.png) next to their name.</span></span>
     - <span data-ttu-id="bbc38-160">**Límite diario de notificaciones**: El valor predeterminado es **Sin límite**, pero puede seleccionar un límite para el número máximo de notificaciones al día.</span><span class="sxs-lookup"><span data-stu-id="bbc38-160">**Daily notification limit**: The default value is **No limit** but you can select a limit for the maximum number of notifications per day.</span></span>

     <span data-ttu-id="bbc38-161">Cuando haya terminado, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="bbc38-161">When you're finished, click **Save**.</span></span>

4. <span data-ttu-id="bbc38-162">Vuelva al control flotante **Usuario con restricción de envío de correo electrónico** y haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="bbc38-162">Back on the **User restricted from sending email** flyout, click **Close**.</span></span>

## <a name="use-exchange-online-powershell-to-view-and-remove-users-from-the-restricted-users-list"></a><span data-ttu-id="bbc38-163">Usar PowerShell de Exchange Online para ver y quitar usuarios de la lista de Usuarios restringidos</span><span class="sxs-lookup"><span data-stu-id="bbc38-163">Use Exchange Online PowerShell to view and remove users from the Restricted users list</span></span>

<span data-ttu-id="bbc38-164">Para ver la lista de usuarios a los que se les ha restringido el envío de correo electrónico, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="bbc38-164">To view this list of users that are restricted from sending email, run the following command:</span></span>

```powershell
Get-BlockedSenderAddress
```

<span data-ttu-id="bbc38-165">Para ver los detalles de un usuario específico, sustituya \<emailaddress\> por su dirección de correo electrónico y ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="bbc38-165">To view details about a specific user, replace \<emailaddress\> with their email address and run the following command:</span></span>

```powershell
Get-BlockedSenderAddress -SenderAddress <emailaddress>
```

<span data-ttu-id="bbc38-166">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Get-BlockedSenderAddress](/powershell/module/exchange/get-blockedsenderaddress).</span><span class="sxs-lookup"><span data-stu-id="bbc38-166">For detailed syntax and parameter information, see [Get-BlockedSenderAddress](/powershell/module/exchange/get-blockedsenderaddress).</span></span>

<span data-ttu-id="bbc38-167">Para quitar a un usuario de la lista de Usuarios restringidos, sustituya \<emailaddress\> por su dirección de correo electrónico y ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="bbc38-167">To remove a user from the Restricted users list, replace \<emailaddress\> with their email address and run the following command:</span></span>

```powershell
Remove-BlockedSenderAddress -SenderAddress <emailaddress>
```

<span data-ttu-id="bbc38-168">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Remove-BlockedSenderAddress](/powershell/module/exchange/remove-blockedsenderaddress).</span><span class="sxs-lookup"><span data-stu-id="bbc38-168">For detailed syntax and parameter information, see [Remove-BlockedSenderAddress](/powershell/module/exchange/remove-blockedsenderaddress).</span></span>
