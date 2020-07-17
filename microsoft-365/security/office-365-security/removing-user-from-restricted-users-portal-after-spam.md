---
title: Quitar usuarios bloqueados del portal de Usuarios restringidos
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
f1_keywords:
- ms.exch.eac.ActionCenter.Restricted.Users.RestrictedUsers
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 712cfcc1-31e8-4e51-8561-b64258a8f1e5
ms.collection:
- M365-security-compliance
description: Los administradores pueden obtener información sobre cómo quitar usuarios del portal de Usuarios restringidos en Office 365. Se agregan usuarios al portal de Usuarios restringidos para el envío correo no deseado saliente, normalmente porque la cuenta se ha visto comprometida.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 43312ee6eff9b56ac4faf8173666a1ba79b9e067
ms.sourcegitcommit: df6cc8c2eb2a65c7668f2953b0f7ec783a596d15
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/13/2020
ms.locfileid: "44726731"
---
# <a name="remove-blocked-users-from-the-restricted-users-portal-in-office-365"></a><span data-ttu-id="26367-104">Quitar usuarios bloqueados del portal de Usuarios restringidos en Office 365</span><span class="sxs-lookup"><span data-stu-id="26367-104">Remove blocked users from the Restricted Users portal in Office 365</span></span>

<span data-ttu-id="26367-105">Si un usuario supera uno de los límites de envío saliente, como se especifica en [límites del servicio](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) o en [directivas de correo no deseado saliente](configure-the-outbound-spam-policy.md), el usuario no puede enviar correos electrónicos, pero aún podrá recibirlos.</span><span class="sxs-lookup"><span data-stu-id="26367-105">If a user exceeds one of the outbound sending limits as specified in [the service limits](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) or in [outbound spam policies](configure-the-outbound-spam-policy.md), the user is restricted from sending email, but they can still receive email.</span></span>

<span data-ttu-id="26367-106">El usuario se agrega al portal de Usuarios restringidos en el Centro de seguridad y cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="26367-106">The user is added to the Restricted Users portal in the Security & Compliance Center.</span></span> <span data-ttu-id="26367-107">Al intentar enviar un correo electrónico, el mensaje se devuelve en un informe de no entrega (también conocido como NDR o mensajes de devolución) con el código de error [5.1.8](https://docs.microsoft.com/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/fix-error-code-5-1-8-in-exchange-online) y el texto siguiente:</span><span class="sxs-lookup"><span data-stu-id="26367-107">When they try to send email, the message is returned in a non-delivery report (also known as an NDR or bounce messages) with the error code [5.1.8](https://docs.microsoft.com/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/fix-error-code-5-1-8-in-exchange-online) and the following text:</span></span>

> <span data-ttu-id="26367-108">"No se pudo entregar el mensaje porque el remitente no es válido.</span><span class="sxs-lookup"><span data-stu-id="26367-108">"Your message couldn't be delivered because you weren't recognized as a valid sender.</span></span> <span data-ttu-id="26367-109">La razón más común para este caso es que la dirección de correo electrónico sea sospechosa de que está enviando correo no deseado y ya no se le permite enviar correo.</span><span class="sxs-lookup"><span data-stu-id="26367-109">The most common reason for this is that your email address is suspected of sending spam and it's no longer allowed to send email.</span></span>  <span data-ttu-id="26367-110">Póngase en contacto con su administrador, para obtener ayuda.</span><span class="sxs-lookup"><span data-stu-id="26367-110">Contact  your email admin for assistance.</span></span> <span data-ttu-id="26367-111">El servidor remoto devolvió "550 5.1.8 acceso denegado, remitente incorrecto de correo saliente".</span><span class="sxs-lookup"><span data-stu-id="26367-111">Remote Server returned '550 5.1.8 Access denied, bad outbound sender."</span></span>

<span data-ttu-id="26367-112">Los administradores pueden quitar usuarios del portal de Remitentes restringidos en el Centro de seguridad y cumplimiento o en el PowerShell de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="26367-112">Admins can remove users from the Restricted Senders portal in the Security & Compliance Center or in Exchange Online PowerShell.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="26367-113">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="26367-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="26367-114">Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="26367-114">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="26367-115">Vaya directamente a la página **Usuarios restringidos**, use <https://protection.office.com/restrictedusers>.</span><span class="sxs-lookup"><span data-stu-id="26367-115">To go directly to the **Restricted Users** page, use <https://protection.office.com/restrictedusers>.</span></span>

- <span data-ttu-id="26367-116">Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="26367-116">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="26367-117">Para poder realizar los procedimientos de este tema, deberá tener asignados los permisos necesarios:</span><span class="sxs-lookup"><span data-stu-id="26367-117">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="26367-118">Para quitar usuarios en el portal de Usuarios restringidos, debe ser miembro de uno de los siguientes grupos de funciones:</span><span class="sxs-lookup"><span data-stu-id="26367-118">To remove users from the Restricted Users portal, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="26367-119">**Administración de la organización** o **Administrador de seguridad** en el [Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="26367-119">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="26367-120">**Administración de la organización** o **Administración de higiene** en [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="26367-120">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="26367-121">Para obtener acceso de solo lectura al portal de Usuarios restringidos, deberá ser miembro de uno de los siguientes grupos de funciones:</span><span class="sxs-lookup"><span data-stu-id="26367-121">For read-only access to the Restricted Users portal, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="26367-122">**Lector de seguridad** en el [Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="26367-122">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="26367-123">**Administración de la organización de solo visualización** en [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="26367-123">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="26367-124">Un remitente que supera los límites de correo electrónico saliente es un indicador de una cuenta comprometida.</span><span class="sxs-lookup"><span data-stu-id="26367-124">A sender exceeding the outbound email limits is an indicator of a compromised account.</span></span> <span data-ttu-id="26367-125">Antes de quitar el usuario del portal de Usuarios restringidos, asegúrese de seguir los pasos necesarios para recuperar el control de su cuenta.</span><span class="sxs-lookup"><span data-stu-id="26367-125">Before you remove the user from the Restricted Users portal, be sure to follow the required steps to regain control of their account.</span></span> <span data-ttu-id="26367-126">Para obtener más información, consulte [Responder a una cuenta de correo electrónico comprometida en Office 365](responding-to-a-compromised-email-account.md).</span><span class="sxs-lookup"><span data-stu-id="26367-126">For more information, see [Responding to a compromised email account in Office 365](responding-to-a-compromised-email-account.md).</span></span>

## <a name="use-the-security--compliance-center-to-remove-a-user-from-the-restricted-users-list"></a><span data-ttu-id="26367-127">Usar el Centro de seguridad y cumplimiento para quitar a un usuario de la lista de Usuarios restringidos</span><span class="sxs-lookup"><span data-stu-id="26367-127">Use the Security & Compliance Center to remove a user from the Restricted Users list</span></span>

1. <span data-ttu-id="26367-128">En el Centro de seguridad y cumplimiento, vaya a **Administración de amenazas** \> **Revisar** \> **Usuarios restringidos**.</span><span class="sxs-lookup"><span data-stu-id="26367-128">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Restricted users**.</span></span>

2. <span data-ttu-id="26367-129">Busque y seleccione al usuario que desee desbloquear.</span><span class="sxs-lookup"><span data-stu-id="26367-129">Find and select the user that you want to unblock.</span></span> <span data-ttu-id="26367-130">En la columna **Acciones**, haga clic en **Desbloquear**.</span><span class="sxs-lookup"><span data-stu-id="26367-130">In the **Actions** column, click **Unblock**.</span></span>

3. <span data-ttu-id="26367-131">Una reaparición irá en los detalles de la cuenta cuyo envío está restringido.</span><span class="sxs-lookup"><span data-stu-id="26367-131">A fly-out will go into the details about the account whose sending is restricted.</span></span> <span data-ttu-id="26367-132">Debe revisar las recomendaciones para asegurarse de que está llevando a cabo las acciones adecuadas en caso de que la cuenta se ponga en peligro.</span><span class="sxs-lookup"><span data-stu-id="26367-132">You should go through the recommendations to ensure you're taking the proper actions in case the account is actually compromised.</span></span> <span data-ttu-id="26367-133">Seleccione **Siguiente**cuando termine.</span><span class="sxs-lookup"><span data-stu-id="26367-133">Click **Next** when done.</span></span>

4. <span data-ttu-id="26367-134">En la siguiente pantalla encontrará recomendaciones para evitar comprometer el futuro.</span><span class="sxs-lookup"><span data-stu-id="26367-134">The next screen has recommendations to help prevent future compromise.</span></span> <span data-ttu-id="26367-135">Habilitar la autenticación multi factor (MFA) y cambiar las contraseñas es una buena defensa.</span><span class="sxs-lookup"><span data-stu-id="26367-135">Enabling multi-factor authentication (MFA) and changing the passwords are a good defense.</span></span> <span data-ttu-id="26367-136">Haga clic **desbloquear usuario**cuando haya finalizado.</span><span class="sxs-lookup"><span data-stu-id="26367-136">Click **Unblock user** when done.</span></span>

5. <span data-ttu-id="26367-137">Haga clic en **Sí** para confirmar el cambio.</span><span class="sxs-lookup"><span data-stu-id="26367-137">Click **Yes** to confirm the change.</span></span>

   > [!NOTE]
   > <span data-ttu-id="26367-138">Se pueden tardar 30 minutos o más antes de quitar las restricciones.</span><span class="sxs-lookup"><span data-stu-id="26367-138">It may take 30 minutes or more before restrictions are removed.</span></span>

## <a name="verify-the-alert-settings-for-restricted-users"></a><span data-ttu-id="26367-139">Comprobar la configuración de alertas para usuarios restringidos</span><span class="sxs-lookup"><span data-stu-id="26367-139">Verify the alert settings for restricted users</span></span>

<span data-ttu-id="26367-140">La directiva de alerta predeterminada denominada **Usuario con restricción de envío de correo electrónico** notificará automáticamente a los administradores cuando se bloquee el envío de correo saliente por parte de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="26367-140">The default alert policy named **User restricted from sending email** will automatically notify admins when users are blocked from sending outbound mail.</span></span> <span data-ttu-id="26367-141">Puede comprobar esta configuración y agregar usuarios adicionales a los que notificar.</span><span class="sxs-lookup"><span data-stu-id="26367-141">You can verify these settings and add additional users to notify.</span></span> <span data-ttu-id="26367-142">Para obtener más información sobre las directivas de alerta, consulte [Directivas de alerta en el centro de seguridad y cumplimiento](../../compliance/alert-policies.md).</span><span class="sxs-lookup"><span data-stu-id="26367-142">For more information about alert policies, see [Alert policies in the security and compliance center](../../compliance/alert-policies.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="26367-143">Para que las alertas funcionen, debe activarse la búsqueda de registros de auditoría.</span><span class="sxs-lookup"><span data-stu-id="26367-143">For alerts to work, audit log search must to be turned on.</span></span> <span data-ttu-id="26367-144">Para obtener más información, consulte [ Desactivar o activar la búsqueda de registros de auditoría](../../compliance/turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="26367-144">For more information, see [Turn the audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

1. <span data-ttu-id="26367-145">En el Centro de seguridad y cumplimiento, vaya a **Alertas** \> **Directivas de alerta**.</span><span class="sxs-lookup"><span data-stu-id="26367-145">In the Security & Compliance Center, go to **Alerts** \> **Alert policies**.</span></span>

2. <span data-ttu-id="26367-146">Busque y seleccione la alerta **Usuario con restricción de envío de correo electrónico**.</span><span class="sxs-lookup"><span data-stu-id="26367-146">Find an select the **User restricted from sending email** alert.</span></span>

3. <span data-ttu-id="26367-147">En el control flotante que aparece, compruebe o configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="26367-147">In the flyout that appears, verify or configure the following settings:</span></span>

   - <span data-ttu-id="26367-148">**Estado**: Compruebe que la alerta está activada![Activación](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).</span><span class="sxs-lookup"><span data-stu-id="26367-148">**Status**: Verify the alert is turned on ![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).</span></span>

   - <span data-ttu-id="26367-149">**Destinatarios de correo electrónico**: Haga clic en **Editar** y compruebe o configure las siguientes opciones en el control flotante **Editar destinatarios** que aparece:</span><span class="sxs-lookup"><span data-stu-id="26367-149">**Email recipients**: Click **Edit** and verify or configure the following settings in the **Edit recipients** flyout that appears:</span></span>

     - <span data-ttu-id="26367-150">**Enviar notificaciones de correo electrónico**: Compruebe que la casilla de verificación está (**Activada**).</span><span class="sxs-lookup"><span data-stu-id="26367-150">**Send email notifications**: Verify the check box is selected (**On**).</span></span>

     - <span data-ttu-id="26367-151">**Destinatarios de correo electrónico**: El valor predeterminado es **TenantAdmins** (lo que significa miembros de **Administrador global**).</span><span class="sxs-lookup"><span data-stu-id="26367-151">**Email recipients**: The default value is **TenantAdmins** (meaning, **Global admin** members).</span></span> <span data-ttu-id="26367-152">Para agregar más destinatarios, haga clic en un área en blanco del cuadro.</span><span class="sxs-lookup"><span data-stu-id="26367-152">To add more recipients, click in a blank area of the box.</span></span> <span data-ttu-id="26367-153">Se mostrará una lista de destinatarios y puede empezar a escribir un nombre para filtrar y seleccionar un destinatario.</span><span class="sxs-lookup"><span data-stu-id="26367-153">A list of recipients will appear, and you can start typing a name to filter and select a recipient.</span></span> <span data-ttu-id="26367-154">Para quitar un destinatario existente del cuadro, haga clic en el ![Icono quitar](../../media/scc-remove-icon.png) junto a su nombre.</span><span class="sxs-lookup"><span data-stu-id="26367-154">You can remove an existing recipient from the box by clicking ![Remove icon](../../media/scc-remove-icon.png) next to their name.</span></span>

     - <span data-ttu-id="26367-155">**Límite diario de notificaciones**: El valor predeterminado es **Sin límite**, pero puede seleccionar un límite para el número máximo de notificaciones al día.</span><span class="sxs-lookup"><span data-stu-id="26367-155">**Daily notification limit**: The default value is **No limit** but you can select a limit for the maximum number of notifications per day.</span></span>

     <span data-ttu-id="26367-156">Cuando haya terminado, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="26367-156">When you're finished, click **Save**.</span></span>

4. <span data-ttu-id="26367-157">Vuelva al control flotante **Usuario con restricción de envío de correo electrónico** y haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="26367-157">Back on the **User restricted from sending email** flyout, click **Close**.</span></span>

## <a name="use-exchange-online-powershell-to-view-and-remove-users-from-the-restricted-users-list"></a><span data-ttu-id="26367-158">Usar PowerShell de Exchange Online para ver y quitar usuarios de la lista de Usuarios restringidos</span><span class="sxs-lookup"><span data-stu-id="26367-158">Use Exchange Online PowerShell to view and remove users from the Restricted Users list</span></span>

<span data-ttu-id="26367-159">Para ver la lista de usuarios a los que se les ha restringido el envío de correo electrónico, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="26367-159">To view this list of users that are restricted from sending email, run the following command:</span></span>

```powershell
Get-BlockedSenderAddress
```

<span data-ttu-id="26367-160">Para ver los detalles de un usuario específico, sustituya \<emailaddress\> por su dirección de correo electrónico y ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="26367-160">To view details about a specific user, replace \<emailaddress\> with their email address and run the following command:</span></span>

```powershell
Get-BlockedSenderAddress -SenderAddress <emailaddress>
```

<span data-ttu-id="26367-161">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Get-BlockedSenderAddress](https://docs.microsoft.com/powershell/module/exchange/get-blockedsenderaddress).</span><span class="sxs-lookup"><span data-stu-id="26367-161">For detailed syntax and parameter information, see [Get-BlockedSenderAddress](https://docs.microsoft.com/powershell/module/exchange/get-blockedsenderaddress).</span></span>

<span data-ttu-id="26367-162">Para quitar a un usuario de la lista de Usuarios restringidos, sustituya \<emailaddress\> por su dirección de correo electrónico y ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="26367-162">To remove a user from the Restricted Users list, replace \<emailaddress\> with their email address and run the following command:</span></span>

```powershell
Remove-BlockedSenderAddress -SenderAddress <emailaddress>
```

<span data-ttu-id="26367-163">Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Remove-BlockedSenderAddress](https://docs.microsoft.com/powershell/module/exchange/remove-blockedsenderaddress).</span><span class="sxs-lookup"><span data-stu-id="26367-163">For detailed syntax and parameter information, see [Remove-BlockedSenderAddress](https://docs.microsoft.com/powershell/module/exchange/remove-blockedsenderaddress).</span></span>
