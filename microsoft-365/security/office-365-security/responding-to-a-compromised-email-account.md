---
title: Responder a una cuenta de correo electrónico en peligro
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.collection:
- o365_security_incident_response
- M365-security-compliance
- m365solution-smb
ms.custom:
- TopSMBIssues
- seo-marvel-apr2020
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
description: Aprenda a reconocer y responder a una cuenta de correo electrónico comprometida utilizando las herramientas disponibles en Microsoft 365.
ms.openlocfilehash: cfd20b0d5e6e13343346761b9b909a333b9a6ff5
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827522"
---
# <a name="responding-to-a-compromised-email-account"></a><span data-ttu-id="46446-103">Responder a una cuenta de correo electrónico en peligro</span><span class="sxs-lookup"><span data-stu-id="46446-103">Responding to a Compromised Email Account</span></span>

<span data-ttu-id="46446-104">**Resumen** Aprenda a reconocer y responder a una cuenta de correo electrónico en peligro en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="46446-104">**Summary** Learn how to recognize and respond to a compromised email account in Microsoft 365.</span></span>

## <a name="what-is-a-compromised-email-account-in-microsoft-365"></a><span data-ttu-id="46446-105">¿Qué es una cuenta de correo electrónico en peligro en Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="46446-105">What is a Compromised Email Account in Microsoft 365?</span></span>

<span data-ttu-id="46446-106">El acceso a los buzones, los datos y otros servicios de Microsoft 365 se controla mediante el uso de credenciales, como un nombre de usuario y contraseña o PIN.</span><span class="sxs-lookup"><span data-stu-id="46446-106">Access to Microsoft 365 mailboxes, data and other services, is controlled through the use of credentials, for example a user name and password or PIN.</span></span> <span data-ttu-id="46446-107">Cuando alguien que no sea el usuario roba estas credenciales, se considera que las credenciales robadas suponen un riesgo.</span><span class="sxs-lookup"><span data-stu-id="46446-107">When someone other than the intended user steals those credentials, the stolen credentials are considered to be compromised.</span></span> <span data-ttu-id="46446-108">Con ellas, el atacante puede iniciar sesión como el usuario original y realizar acciones ilícitas.</span><span class="sxs-lookup"><span data-stu-id="46446-108">With them the attacker can sign in as the original user and perform illicit actions.</span></span>
<span data-ttu-id="46446-109">Con las credenciales robadas, el atacante puede obtener acceso a archivos en OneDrive del usuario, las carpetas de SharePoint o el buzón de Microsoft 365 del usuario.</span><span class="sxs-lookup"><span data-stu-id="46446-109">Using the stolen credentials, the attacker can access the user's Microsoft 365 mailbox, SharePoint folders, or files in the user's OneDrive.</span></span> <span data-ttu-id="46446-110">Una acción habitual es que el atacante envíe correos electrónicos como el usuario original a destinatarios tanto dentro como fuera de la organización.</span><span class="sxs-lookup"><span data-stu-id="46446-110">One action commonly seen is the attacker sending emails as the original user to recipients both inside and outside of the organization.</span></span> <span data-ttu-id="46446-111">Cuando el atacante envía datos a destinatarios externos, se denomina "exfiltración" de datos.</span><span class="sxs-lookup"><span data-stu-id="46446-111">When the attacker emails data to external recipients, this is called data exfiltration.</span></span>

## <a name="symptoms-of-a-compromised-microsoft-email-account"></a><span data-ttu-id="46446-112">Síntomas de una cuenta de correo electrónico de Microsoft en peligro</span><span class="sxs-lookup"><span data-stu-id="46446-112">Symptoms of a Compromised Microsoft Email Account</span></span>

<span data-ttu-id="46446-113">Los usuarios pueden observar e informar sobre actividad inusual en sus buzones de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="46446-113">Users might notice and report unusual activity in their Microsoft 365 mailboxes.</span></span> <span data-ttu-id="46446-114">Estos son algunos síntomas comunes:</span><span class="sxs-lookup"><span data-stu-id="46446-114">Here are some common symptoms:</span></span>

- <span data-ttu-id="46446-115">Actividad sospechosa, como correos electrónicos eliminados o que faltan.</span><span class="sxs-lookup"><span data-stu-id="46446-115">Suspicious activity, such as missing or deleted emails.</span></span>

- <span data-ttu-id="46446-116">Otros usuarios pueden recibir correos electrónicos de la cuenta en peligro sin que el correo electrónico correspondiente aparezca en la carpeta **Elementos enviados** del remitente.</span><span class="sxs-lookup"><span data-stu-id="46446-116">Other users might receive emails from the compromised account without the corresponding email existing in the **Sent Items** folder of the sender.</span></span>

- <span data-ttu-id="46446-117">La presencia de reglas de bandeja de entrada que no se han creado por el usuario o el administrador.</span><span class="sxs-lookup"><span data-stu-id="46446-117">The presence of inbox rules that weren't created by the intended user or the administrator.</span></span> <span data-ttu-id="46446-118">Estas reglas pueden reenviar automáticamente correos electrónicos a direcciones desconocidas o moverlos a las carpetas de **Notas**, **Correo no deseado** o **Suscripciones RSS**.</span><span class="sxs-lookup"><span data-stu-id="46446-118">These rules may automatically forward emails to unknown addresses or move them to the **Notes**, **Junk Email**, or **RSS Subscriptions** folders.</span></span>

- <span data-ttu-id="46446-119">El nombre para mostrar del usuario puede cambiarse en la lista Global de direcciones.</span><span class="sxs-lookup"><span data-stu-id="46446-119">The user's display name might be changed in the Global Address List.</span></span>

- <span data-ttu-id="46446-120">El buzón del usuario está bloqueado para enviar correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="46446-120">The user's mailbox is blocked from sending email.</span></span>

- <span data-ttu-id="46446-121">Las carpetas de Elementos enviados o Elementos eliminados en Microsoft Outlook o Outlook en la Web (anteriormente conocido como Outlook Web App) contienen mensajes comunes de cuentas robadas, como "Estoy atascado en Londres, envíame dinero".</span><span class="sxs-lookup"><span data-stu-id="46446-121">The Sent or Deleted Items folders in Microsoft Outlook or Outlook on the web (formerly known as Outlook Web App) contain common hacked-account messages, such as "I'm stuck in London, send money."</span></span>

- <span data-ttu-id="46446-122">Se han realizado cambios inusuales en el perfil, como el nombre, el número de teléfono o el código postal.</span><span class="sxs-lookup"><span data-stu-id="46446-122">Unusual profile changes, such as the name, the telephone number, or the postal code were updated.</span></span>

- <span data-ttu-id="46446-123">Cambios inusuales de credenciales, como múltiples cambios de contraseña requeridos.</span><span class="sxs-lookup"><span data-stu-id="46446-123">Unusual credential changes, such as multiple password changes are required.</span></span>

- <span data-ttu-id="46446-124">Se ha agregado recientemente el reenvío de correo.</span><span class="sxs-lookup"><span data-stu-id="46446-124">Mail forwarding was recently added.</span></span>

- <span data-ttu-id="46446-125">Se ha agregado recientemente una firma inusual, como una firma de entidad bancaria falsa o una firma de recetas de medicamentos.</span><span class="sxs-lookup"><span data-stu-id="46446-125">An unusual signature was recently added, such as a fake banking signature or a prescription drug signature.</span></span>

<span data-ttu-id="46446-126">Si un usuario informa de los síntomas anteriores, debería realizar una mayor investigación.</span><span class="sxs-lookup"><span data-stu-id="46446-126">If a user reports any of the above symptoms, you should perform further investigation.</span></span> <span data-ttu-id="46446-127">El Centro de seguridad y cumplimiento de Microsoft 365 y el Portal de Azure ofrecen herramientas para ayudarle a investigar la actividad de una cuenta de usuario que crea que puede estar en riesgo.</span><span class="sxs-lookup"><span data-stu-id="46446-127">The Microsoft 365 Security & Compliance Center and the Azure Portal offer tools to help you investigate the activity of a user account that you suspect may be compromised.</span></span>

- <span data-ttu-id="46446-128">**Registros de auditoría unificados en el Centro de seguridad y cumplimiento**: revise todas las actividades de la cuenta sospechosa, filtre los resultados con un rango de fechas que abarque desde antes de que se produjese la actividad sospechosa hasta la fecha actual.</span><span class="sxs-lookup"><span data-stu-id="46446-128">**Unified Audit Logs in the Security & Compliance Center**: Review all the activities for the suspected account by filtering the results for the date range spanning from immediately before the suspicious activity occurred to the current date.</span></span> <span data-ttu-id="46446-129">No filtre las actividades durante la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="46446-129">Do not filter on the activities during the search.</span></span>

- <span data-ttu-id="46446-130">**Registros de auditoría de administrador en el EAC**: en Exchange Online, puede usar el Centro de administración de Exchange (EAC) para buscar y ver las entradas del registro de auditoría del administrador.</span><span class="sxs-lookup"><span data-stu-id="46446-130">**Admin Audit logs in the EAC**: In Exchange Online, you can use the Exchange admin center (EAC) to search for and view entries in the administrator audit log.</span></span> <span data-ttu-id="46446-131">El registro de auditoría del administrador registra acciones específicas, según los cmdlets de PowerShell de Exchange Online, realizadas por administradores y usuarios que tienen asignados privilegios de administrador.</span><span class="sxs-lookup"><span data-stu-id="46446-131">The administrator audit log records specific actions, based on Exchange Online PowerShell cmdlets, performed by administrators and users who have been assigned administrative privileges.</span></span> <span data-ttu-id="46446-132">Las entradas en el registro de auditoría del administrador proporcionan información acerca del cmdlet que se ejecutó, los parámetros que se usaron, el usuario que ejecutó el cmdlet y los objetos que se vieron afectados.</span><span class="sxs-lookup"><span data-stu-id="46446-132">Entries in the administrator audit log provide you with information about what cmdlet was run, which parameters were used, who ran the cmdlet, and what objects were affected.</span></span>

- <span data-ttu-id="46446-133">**Registros de inicio de sesión de Azure AD y otros informes de riesgos en el portal de Azure AD**: examine los valores de estas columnas:</span><span class="sxs-lookup"><span data-stu-id="46446-133">**Azure AD Sign-in logs and other risk reports in the Azure AD portal**: Examine the values in these columns:</span></span>

  - <span data-ttu-id="46446-134">Revise la dirección IP</span><span class="sxs-lookup"><span data-stu-id="46446-134">Review IP address</span></span>
  - <span data-ttu-id="46446-135">ubicaciones de inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="46446-135">sign-in locations</span></span>
  - <span data-ttu-id="46446-136">horas de inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="46446-136">sign-in times</span></span>
  - <span data-ttu-id="46446-137">inicios de sesión correctos y fallidos</span><span class="sxs-lookup"><span data-stu-id="46446-137">sign-in success or failure</span></span>

## <a name="how-to-secure-and-restore-email-function-to-a-suspected-compromised-microsoft-365-account-and-mailbox"></a><span data-ttu-id="46446-138">Cómo proteger y restaurar la función de correo electrónico a un buzón o una cuenta de Microsoft 365 en peligro</span><span class="sxs-lookup"><span data-stu-id="46446-138">How to secure and restore email function to a suspected compromised Microsoft 365 account and mailbox</span></span>

> [!VIDEO https://videoplayercdn.osi.office.net/hub/?csid=ux-cms-en-us-msoffice&uuid=RE2jvOb&AutoPlayVideo=false]

<span data-ttu-id="46446-139">Incluso después de haber recuperado el acceso a su cuenta, el atacante puede haber agregado entradas traseras que permiten le permiten reanudar el control de la cuenta.</span><span class="sxs-lookup"><span data-stu-id="46446-139">Even after you've regained access to your account, the attacker may have added back-door entries that enable the attacker to resume control of the account.</span></span>

<span data-ttu-id="46446-140">Debe realizar todos los pasos siguientes para volver a tener acceso a su cuenta lo antes posible para asegurarse de que el atacante no reanude el control de su cuenta.</span><span class="sxs-lookup"><span data-stu-id="46446-140">You must perform all the following steps to regain access to your account the sooner the better to make sure that the hijacker doesn't resume control your account.</span></span> <span data-ttu-id="46446-141">Estos pasos le ayudan a quitar las entradas traseras que puede haber agregado el atacante a su cuenta.</span><span class="sxs-lookup"><span data-stu-id="46446-141">These steps help you remove any back-door entries that the hijacker may have added to your account.</span></span> <span data-ttu-id="46446-142">Después de completar estos pasos, se recomienda que ejecute una detección de virus para asegurarse de que su equipo no está en peligro.</span><span class="sxs-lookup"><span data-stu-id="46446-142">After you perform these steps, we recommend that you run a virus scan to make sure that your computer isn't compromised.</span></span>

### <a name="step-1-reset-the-users-password"></a><span data-ttu-id="46446-143">Paso 1 Restablecer la contraseña del usuario</span><span class="sxs-lookup"><span data-stu-id="46446-143">Step 1 Reset the user's password</span></span>

<span data-ttu-id="46446-144">Siga los procedimientos que se describen en [Restablecer una contraseña de empresa para un usuario](https://docs.microsoft.com/microsoft-365/admin/add-users/reset-passwords#reset-my-admin-password).</span><span class="sxs-lookup"><span data-stu-id="46446-144">Follow the procedures in [Reset a business password for someone](https://docs.microsoft.com/microsoft-365/admin/add-users/reset-passwords#reset-my-admin-password).</span></span>

> [!IMPORTANT]
>
> - <span data-ttu-id="46446-145">No envíe la nueva contraseña al usuario en cuestión por correo electrónico, ya que el atacante todavía tiene acceso al buzón en este momento.</span><span class="sxs-lookup"><span data-stu-id="46446-145">Do not send the new password to the intended user through email as the attacker still has access to the mailbox at this point.</span></span>
>
> - <span data-ttu-id="46446-146">Asegúrese de que la contraseña es segura y que contiene al menos un carácter especial, al menos un número y letras mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="46446-146">Make sure that the password is strong and that it contains upper and lowercase letters, at least one number, and at least one special character.</span></span>
>
> - <span data-ttu-id="46446-147">No vuelva a usar ninguna de las últimas cinco contraseñas.</span><span class="sxs-lookup"><span data-stu-id="46446-147">Don't reuse any of your last five passwords.</span></span> <span data-ttu-id="46446-148">Aunque el requisito de historial de contraseña le permite volver a usar una contraseña más reciente, debería seleccionar algo que el atacante no pueda adivinar.</span><span class="sxs-lookup"><span data-stu-id="46446-148">Even though the password history requirement lets you reuse a more recent password, you should select something that the attacker can't guess.</span></span>
>
> - <span data-ttu-id="46446-149">Si la identidad local se federa con Microsoft 365, debe cambiar la contraseña en el entorno local y, a continuación, debe notificar el peligro a su administrador.</span><span class="sxs-lookup"><span data-stu-id="46446-149">If your on-premises identity is federated with Microsoft 365, you must change your password on-premises, and then you must notify your administrator of the compromise.</span></span>
>
> - <span data-ttu-id="46446-150">Asegúrese de actualizar las contraseñas de aplicación.</span><span class="sxs-lookup"><span data-stu-id="46446-150">Be sure to update app passwords.</span></span> <span data-ttu-id="46446-151">Las contraseñas de aplicación no se revocan automáticamente cuando se restablece la contraseña de una cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="46446-151">App passwords aren't automatically revoked when a user account password reset.</span></span> <span data-ttu-id="46446-152">El usuario debe eliminar las contraseñas de aplicación existentes y crear otras nuevas.</span><span class="sxs-lookup"><span data-stu-id="46446-152">The user should delete existing app passwords and create new ones.</span></span> <span data-ttu-id="46446-153">Para obtener instrucciones, consulte [Crear y eliminar contraseñas de aplicación de la página de Comprobación de seguridad adicional](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-app-passwords#create-and-delete-app-passwords-from-the-additional-security-verification-page).</span><span class="sxs-lookup"><span data-stu-id="46446-153">For instructions, see [Create and delete app passwords from the Additional security verification page](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-app-passwords#create-and-delete-app-passwords-from-the-additional-security-verification-page).</span></span>
>
> - <span data-ttu-id="46446-154">Se recomienda que habilite la autenticación multifactor (MFA) para evitar los robos de cuenta, especialmente para las cuentas con privilegios de administrador.</span><span class="sxs-lookup"><span data-stu-id="46446-154">We highly recommended that you enable Multi-Factor Authentication (MFA) in order to prevent compromise, especially for accounts with administrative privileges.</span></span> <span data-ttu-id="46446-155">Para obtener más información sobre MFA, vaya a [Configurar la autenticación multifactor](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication).</span><span class="sxs-lookup"><span data-stu-id="46446-155">To learn more about MFA, go to [Set up multi-factor authentication](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication).</span></span>

### <a name="step-2-remove-suspicious-email-forwarding-addresses"></a><span data-ttu-id="46446-156">Paso 2 Eliminar direcciones de reenvío de correo electrónico sospechosas</span><span class="sxs-lookup"><span data-stu-id="46446-156">Step 2 Remove suspicious email forwarding addresses</span></span>

1. <span data-ttu-id="46446-157">Abra el Centro de administración de Microsoft 365 en <https://admin.microsoft.com></span><span class="sxs-lookup"><span data-stu-id="46446-157">Open the Microsoft 365 admin center at <https://admin.microsoft.com></span></span>

2. <span data-ttu-id="46446-158">Vaya a **Usuarios** \> **Usuarios activos**.</span><span class="sxs-lookup"><span data-stu-id="46446-158">Go to **Users** \> **Active users**.</span></span> <span data-ttu-id="46446-159">Busque la cuenta de usuario en cuestión y seleccione el usuario (fila) sin seleccionar la casilla.</span><span class="sxs-lookup"><span data-stu-id="46446-159">Find the user account in question, and select the user (row) without selecting the checkbox.</span></span>

3. <span data-ttu-id="46446-160">En el menú desplegable de detalles que aparece, seleccione la pestaña **Correo**.</span><span class="sxs-lookup"><span data-stu-id="46446-160">In the details flyout that appears, select the **Mail** tab.</span></span>

4. <span data-ttu-id="46446-161">Si el valor en la sección **Reenvío de correo electrónico** es **Aplicado**, haga clic en **Administrar reenvío de correo electrónico**.</span><span class="sxs-lookup"><span data-stu-id="46446-161">If the value in the **Email forwarding** section is **Applied**, click **Manage email forwarding**.</span></span> <span data-ttu-id="46446-162">En el menú flotante **Administrar reenvío de correo electrónico** que aparece, desactive **Reenviar todos los correos electrónicos enviados a este buzón** y luego haga clic en **Guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="46446-162">In the **Manage email forwarding** flyout that appears, clear **Forward all email sent to this mailbox**, and then click **Save changes**.</span></span>

### <a name="step-3-disable-any-suspicious-inbox-rules"></a><span data-ttu-id="46446-163">Paso 3 Deshabilitar las reglas de bandeja de entrada sospechosas</span><span class="sxs-lookup"><span data-stu-id="46446-163">Step 3 Disable any suspicious inbox rules</span></span>

1. <span data-ttu-id="46446-164">Inicie sesión en el buzón del usuario con Outlook en la Web.</span><span class="sxs-lookup"><span data-stu-id="46446-164">Sign in to the user's mailbox using Outlook on the web.</span></span>

2. <span data-ttu-id="46446-165">Haga clic en el icono del engranaje y en **Correo**.</span><span class="sxs-lookup"><span data-stu-id="46446-165">Click on the gear icon and click **Mail**.</span></span>

3. <span data-ttu-id="46446-166">Haga clic en **Reglas de bandeja de entrada y barrido** y revise las reglas.</span><span class="sxs-lookup"><span data-stu-id="46446-166">Click **Inbox and sweep rules** and review the rules.</span></span>

4. <span data-ttu-id="46446-167">Deshabilite o elimine las reglas sospechosas.</span><span class="sxs-lookup"><span data-stu-id="46446-167">Disable or delete suspicious rules.</span></span>

### <a name="step-4-unblock-the-user-from-sending-mail"></a><span data-ttu-id="46446-168">Paso 4 Desbloquear el usuario para que pueda enviar correo</span><span class="sxs-lookup"><span data-stu-id="46446-168">Step 4 Unblock the user from sending mail</span></span>

<span data-ttu-id="46446-169">Si el buzón en peligro se usó de forma ilícita para enviar correo no deseado, es probable que el buzón se haya bloqueado para impedir el envío de correo.</span><span class="sxs-lookup"><span data-stu-id="46446-169">If the suspected compromised mailbox was used illicitly to send spam email, it is likely that the mailbox has been blocked from sending mail.</span></span>

<span data-ttu-id="46446-170">Para desbloquear el envío de correo de un buzón, siga los procedimientos descritos en [Quitar un usuario, un dominio o una dirección IP de una lista de bloqueados después de enviar correo no deseado](removing-user-from-restricted-users-portal-after-spam.md).</span><span class="sxs-lookup"><span data-stu-id="46446-170">To unblock a mailbox from sending mail, follow the procedures in [Removing a user from the Restricted Users portal after sending spam email](removing-user-from-restricted-users-portal-after-spam.md).</span></span>

### <a name="step-5-optional-block-the-user-account-from-signing-in"></a><span data-ttu-id="46446-171">Paso 5 opcional: Bloquear la cuenta de usuario para impedir el inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="46446-171">Step 5 Optional: Block the user account from signing-in</span></span>

> [!IMPORTANT]
> <span data-ttu-id="46446-172">Puede bloquear la cuenta en peligro e impedir que inicie hasta que crea que es seguro volver a habilitar el acceso.</span><span class="sxs-lookup"><span data-stu-id="46446-172">You can block the suspected compromised account from signing-in until you believe it is safe to re-enable access.</span></span>

1. <span data-ttu-id="46446-173">En el Centro de administración de Microsoft 365, vaya a **Usuarios** \> **Usuarios activos**.</span><span class="sxs-lookup"><span data-stu-id="46446-173">Open the Microsoft 365 admin center and go to **Users** \> **Active users**.</span></span>

2. <span data-ttu-id="46446-174">Busque y seleccione la cuenta de usuario, haga clic en el ![icono Más](../../media/ITPro-EAC-MoreOptionsIcon.png) y luego seleccione **Editar estado de inicio de sesión**.</span><span class="sxs-lookup"><span data-stu-id="46446-174">Find and select the user account, click ![More icon](../../media/ITPro-EAC-MoreOptionsIcon.png), and then select **Edit sign-in status**.</span></span>

3. <span data-ttu-id="46446-175">En el panel **Bloquear inicio de sesión** que aparece, seleccione **Bloquear el inicio de sesión de este usuario** y luego haga clic en **Guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="46446-175">On the **Block sign-in** pane that appears, select **Block this user from signing in**, and then click **Save changes**.</span></span>

4. <span data-ttu-id="46446-176">Abra el Centro de administración de Exchange (EAC) en <admin.protection.outlook.com/ecp/> y vaya a **Destinatarios > Buzones**.</span><span class="sxs-lookup"><span data-stu-id="46446-176">Open the Exchange admin center (EAC) at <admin.protection.outlook.com/ecp/>, and go to **Recipients > Mailboxes**.</span></span>

5. <span data-ttu-id="46446-177">Busque y seleccione el usuario.</span><span class="sxs-lookup"><span data-stu-id="46446-177">Find and select the select the user.</span></span> <span data-ttu-id="46446-178">En el panel de detalles, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="46446-178">In the details pane, do the following steps:</span></span>

   - <span data-ttu-id="46446-179">En la sección **Características de teléfono y voz**, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="46446-179">In the **Phone and voice features** section, do the following steps:</span></span>

     - <span data-ttu-id="46446-180">Seleccione **Deshabilitar Exchange ActiveSync** y, después, haga clic en **Sí** en la advertencia que aparece.</span><span class="sxs-lookup"><span data-stu-id="46446-180">Select **Disable Exchange ActiveSync** and then click **Yes** in the warning that appears.</span></span>
     - <span data-ttu-id="46446-181">Seleccione **Deshabilitar OWA para dispositivos** y después haga clic en **Sí** en la advertencia que aparece.</span><span class="sxs-lookup"><span data-stu-id="46446-181">Select **Disable OWA for Devices** and then click **Yes** in the warning that appears.</span></span>

   - <span data-ttu-id="46446-182">En la sección **Conectividad de correo electrónico** para Outlook en la Web, haga clic en **Deshabilitar** y después haga clic en **Sí** en la advertencia que aparece.</span><span class="sxs-lookup"><span data-stu-id="46446-182">In the **Email Connectivity** section for Outlook on the web, click **Disable** and then click **Yes** in the warning that appears.</span></span>

### <a name="step-6-optional-remove-the-suspected-compromised-account-from-all-administrative-role-groups"></a><span data-ttu-id="46446-183">Paso 6 opcional: Quitar la cuenta en peligro de todos los grupos de roles administrativos</span><span class="sxs-lookup"><span data-stu-id="46446-183">Step 6 Optional: Remove the suspected compromised account from all administrative role groups</span></span>

> [!NOTE]
> <span data-ttu-id="46446-184">La pertenencia a grupos de roles administrativos puede restaurarse después de haber asegurado la cuenta.</span><span class="sxs-lookup"><span data-stu-id="46446-184">Administrative role group membership can be restored after the account has been secured.</span></span>

1. <span data-ttu-id="46446-185">Inicie sesión con una cuenta de administrador global:</span><span class="sxs-lookup"><span data-stu-id="46446-185">Sign in with a global administrator account:</span></span>

2. <span data-ttu-id="46446-186">En el Centro de administración de Microsoft 365, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="46446-186">In the Microsoft 365 admin center, do the following steps:</span></span>

   1. <span data-ttu-id="46446-187">Vaya a **Usuarios** \> **Usuarios activos**.</span><span class="sxs-lookup"><span data-stu-id="46446-187">Go to **Users** \> **Active users**.</span></span>
   2. <span data-ttu-id="46446-188">Busque y seleccione la cuenta de usuario, haga clic en el ![icono Más](../../media/ITPro-EAC-MoreOptionsIcon.png) y después seleccione **Administrar roles**.</span><span class="sxs-lookup"><span data-stu-id="46446-188">Find and select the user account, click ![More icon](../../media/ITPro-EAC-MoreOptionsIcon.png), and then select **Manage roles**.</span></span>
   3. <span data-ttu-id="46446-189">Quite todos los roles administrativos que están asignados a la cuenta.</span><span class="sxs-lookup"><span data-stu-id="46446-189">Remove any administrative roles that are assigned to the account.</span></span> <span data-ttu-id="46446-190">Cuando haya terminado, haga clic en **Guardar cambios**.</span><span class="sxs-lookup"><span data-stu-id="46446-190">When you're finished, click **Save changes**.</span></span>

3. <span data-ttu-id="46446-191">En el Centro de seguridad y cumplimiento en <https://protection.office.com>, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="46446-191">In the Security & Compliance Center at <https://protection.office.com>, do the following steps:</span></span>

   <span data-ttu-id="46446-192">Seleccione **Permisos**, seleccione cada grupo de roles de la lista y busque la cuenta de usuario en la sección **Miembros** del menú flotante de detalles que aparece.</span><span class="sxs-lookup"><span data-stu-id="46446-192">Select **Permissions**, select each role group in the list and look for the user account in the **Members** section of the details flyout that appears.</span></span> <span data-ttu-id="46446-193">Si el grupo de roles contiene la cuenta de usuario, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="46446-193">If the role group contains the user account, do the following steps:</span></span>

   <span data-ttu-id="46446-194">a.</span><span class="sxs-lookup"><span data-stu-id="46446-194">a.</span></span> <span data-ttu-id="46446-195">Haga clic en **Editar** junto a **Miembros**.</span><span class="sxs-lookup"><span data-stu-id="46446-195">Click **Edit** next to **Members**.</span></span>
   <span data-ttu-id="46446-196">b.</span><span class="sxs-lookup"><span data-stu-id="46446-196">b.</span></span> <span data-ttu-id="46446-197">En el control flotante **Editar Elegir miembros** que aparece, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="46446-197">On the **Editing Choose members** flyout that appears, click **Edit**.</span></span>
   <span data-ttu-id="46446-198">c.</span><span class="sxs-lookup"><span data-stu-id="46446-198">c.</span></span> <span data-ttu-id="46446-199">En el control flotante **Elegir miembros** que aparece, seleccione la cuenta de usuario y haga clic en **Quitar**.</span><span class="sxs-lookup"><span data-stu-id="46446-199">In the **Choose members** flyout that appears, select the user account, and then click **Remove**.</span></span> <span data-ttu-id="46446-200">Cuando haya terminado, haga clic en **Listo**, **Guardar** y después en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="46446-200">When you're finished, click **Done**, **Save**, and then **Close**.</span></span>

4. <span data-ttu-id="46446-201">En el EAC, en <admin.protection.outlook.com/ecp/>, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="46446-201">In the EAC at <admin.protection.outlook.com/ecp/>, do the following steps:</span></span>

   <span data-ttu-id="46446-202">Seleccione **Permisos**, seleccione manualmente cada grupo de roles y, en el panel de detalles, compruebe las cuentas de usuario en la sección **Miembros**.</span><span class="sxs-lookup"><span data-stu-id="46446-202">Select **Permissions**, manually select each role group, and in the details pane, verify the user accounts in the **Members** section.</span></span>  <span data-ttu-id="46446-203">Si el grupo de roles contiene la cuenta de usuario, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="46446-203">If the role group contains the user account, do the following steps:</span></span>

   <span data-ttu-id="46446-204">a.</span><span class="sxs-lookup"><span data-stu-id="46446-204">a.</span></span> <span data-ttu-id="46446-205">Seleccione el grupo de roles y haga clic en **Editar** ![icono Editar](../../media/ITPro-EAC-EditIcon.png).</span><span class="sxs-lookup"><span data-stu-id="46446-205">Select the role group, click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>
   <span data-ttu-id="46446-206">b.</span><span class="sxs-lookup"><span data-stu-id="46446-206">b.</span></span> <span data-ttu-id="46446-207">En la sección **Miembro**, seleccione la cuenta de usuario y después haga clic en **Quitar** ![icono Quitar](../../media/ITPro-EAC-RemoveIcon.gif).</span><span class="sxs-lookup"><span data-stu-id="46446-207">In the **Member** section, select the user account, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span> <span data-ttu-id="46446-208">Cuando haya terminado, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="46446-208">When you're finished, click **Save**.</span></span>

### <a name="step-7-optional-additional-precautionary-steps"></a><span data-ttu-id="46446-209">Paso 7 opcional: Pasos de precauciones adicionales</span><span class="sxs-lookup"><span data-stu-id="46446-209">Step 7 Optional: Additional precautionary steps</span></span>

1. <span data-ttu-id="46446-210">Asegúrese de comprobar los elementos enviados.</span><span class="sxs-lookup"><span data-stu-id="46446-210">Make sure that you verify your sent items.</span></span> <span data-ttu-id="46446-211">Puede que tenga que informar a los usuarios de la lista de contactos de que su cuenta está comprometida.</span><span class="sxs-lookup"><span data-stu-id="46446-211">You may have to inform people on your contacts list that your account was compromised.</span></span> <span data-ttu-id="46446-212">El atacante puede haberles pedido dinero fingiendo, por ejemplo, que estaba perdido en un país distinto y necesitaba dinero, o el atacante puede enviarles un virus para obtener acceso también a sus equipos.</span><span class="sxs-lookup"><span data-stu-id="46446-212">The attacker may have asked them for money, spoofing, for example, that you were stranded in a different country and needed money, or the attacker may send them a virus to also hijack their computers.</span></span>

2. <span data-ttu-id="46446-213">Cualquier otro servicio que use esta cuenta de Exchange como cuenta de correo electrónico alternativa puede haberse comprometido también.</span><span class="sxs-lookup"><span data-stu-id="46446-213">Any other service that used this Exchange account as its alternative email account may have been compromised.</span></span> <span data-ttu-id="46446-214">En primer lugar, siga estos pasos para la suscripción de Microsoft 365 y, a continuación, siga estos pasos para otras cuentas.</span><span class="sxs-lookup"><span data-stu-id="46446-214">First, perform these steps for your Microsoft 365 subscription, and then perform these steps for your other accounts.</span></span>

3. <span data-ttu-id="46446-215">Asegúrese de que la información de contacto, como los números de teléfono y direcciones, es correcta.</span><span class="sxs-lookup"><span data-stu-id="46446-215">Make sure that your contact information, such as telephone numbers and addresses, is correct.</span></span>

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a><span data-ttu-id="46446-216">Proteger Microsoft 365 como un profesional de la ciberseguridad</span><span class="sxs-lookup"><span data-stu-id="46446-216">Secure Microsoft 365 like a cybersecurity pro</span></span>

<span data-ttu-id="46446-217">Su suscripción a Microsoft 365 incluye un potente conjunto de capacidades de seguridad que puede usar para proteger sus datos y los usuarios.</span><span class="sxs-lookup"><span data-stu-id="46446-217">Your Microsoft 365 subscription comes with a powerful set of security capabilities that you can use to protect your data and your users.</span></span>  <span data-ttu-id="46446-218">Use el [Plan de seguridad de Microsoft 365: principales prioridades para los primeros 30 días, 90 días y en adelante](security-roadmap.md) para implementar las prácticas recomendadas de Microsoft para proteger su espacio empresarial de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="46446-218">Use the [Microsoft 365 security roadmap - Top priorities for the first 30 days, 90 days, and beyond](security-roadmap.md) to implement Microsoft recommended best practices for securing your Microsoft 365 tenant.</span></span>

- <span data-ttu-id="46446-219">Tareas a realizar en los primeros 30 días.</span><span class="sxs-lookup"><span data-stu-id="46446-219">Tasks to accomplish in the first 30 days.</span></span>  <span data-ttu-id="46446-220">Estas tienen un efecto inmediato y de bajo impacto para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="46446-220">These have immediate affect and are low-impact to your users.</span></span>

- <span data-ttu-id="46446-221">Tareas para llevar a cabo en 90 días.</span><span class="sxs-lookup"><span data-stu-id="46446-221">Tasks to accomplish in 90 days.</span></span> <span data-ttu-id="46446-222">Estas tareas necesitan un poco más de tiempo para planearlas e implementarlas, pero mejoran considerablemente el nivel de seguridad.</span><span class="sxs-lookup"><span data-stu-id="46446-222">These take a bit more time to plan and implement but greatly improve your security posture.</span></span>

- <span data-ttu-id="46446-223">Más de 90 días.</span><span class="sxs-lookup"><span data-stu-id="46446-223">Beyond 90 days.</span></span> <span data-ttu-id="46446-224">Estas mejoras se crean en el trabajo de los 90 primeros días.</span><span class="sxs-lookup"><span data-stu-id="46446-224">These enhancements build in your first 90 days work.</span></span>

## <a name="see-also"></a><span data-ttu-id="46446-225">Vea también</span><span class="sxs-lookup"><span data-stu-id="46446-225">See also</span></span>

- [<span data-ttu-id="46446-226">Detectar y corregir las reglas de Outlook y ataques de inserciones de formularios personalizados en Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="46446-226">Detect and Remediate Outlook Rules and Custom Forms Injections Attacks in Microsoft 365</span></span>](detect-and-remediate-outlook-rules-forms-attack.md)

- [<span data-ttu-id="46446-227">Centro de Quejas de Crímenes por Internet</span><span class="sxs-lookup"><span data-stu-id="46446-227">Internet Crime Complaint Center</span></span>](https://www.ic3.gov/preventiontips.aspx)

- [<span data-ttu-id="46446-228">Bolsas de valores de EE. UU.: Fraude de suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="46446-228">Securities and Exchange Commission - "Phishing" Fraud</span></span>](https://www.sec.gov/investor/pubs/phishing.htm)

- <span data-ttu-id="46446-229">Para informar directamente a Microsoft y su administrador sobre el correo no deseado [Use el complemento Informar sobre el mensaje](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)</span><span class="sxs-lookup"><span data-stu-id="46446-229">To report spam email directly to Microsoft and your admin [Use the Report Message add-in](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)</span></span>
