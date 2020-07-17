---
title: Responder a una cuenta de correo electrónico en peligro
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.collection:
- o365_security_incident_response
- M365-security-compliance
ms.custom:
- TopSMBIssues
- seo-marvel-apr2020
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
description: Aprenda a reconocer y responder a una cuenta de correo electrónico comprometida utilizando las herramientas disponibles en Microsoft 365.
ms.openlocfilehash: f9d7b1dbcd9b54ca9b1bdca9e4a800be24286654
ms.sourcegitcommit: 09a500a44d8723f8f2be87d9ad4ce7e453c5192b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2020
ms.locfileid: "45094815"
---
# <a name="responding-to-a-compromised-email-account"></a><span data-ttu-id="0dc5d-103">Responder a una cuenta de correo electrónico en peligro</span><span class="sxs-lookup"><span data-stu-id="0dc5d-103">Responding to a Compromised Email Account</span></span>

<span data-ttu-id="0dc5d-104">**Resumen** Aprenda a reconocer y responder a una cuenta de correo electrónico en peligro en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0dc5d-104">**Summary** Learn how to recognize and respond to a compromised email account in Microsoft 365.</span></span>

## <a name="what-is-a-compromised-email-account-in-microsoft-365"></a><span data-ttu-id="0dc5d-105">¿Qué es una cuenta de correo electrónico en peligro en Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="0dc5d-105">What is a Compromised Email Account in Microsoft 365?</span></span>

<span data-ttu-id="0dc5d-106">El acceso a los buzones, los datos y otros servicios de Microsoft 365 se controla mediante el uso de credenciales, como un nombre de usuario y contraseña o PIN.</span><span class="sxs-lookup"><span data-stu-id="0dc5d-106">Access to Microsoft 365 mailboxes, data and other services, is controlled through the use of credentials, for example a user name and password or PIN.</span></span> <span data-ttu-id="0dc5d-107">Cuando alguien que no sea el usuario roba estas credenciales, se considera que las credenciales robadas suponen un riesgo.</span><span class="sxs-lookup"><span data-stu-id="0dc5d-107">When someone other than the intended user steals those credentials, the stolen credentials are considered to be compromised.</span></span> <span data-ttu-id="0dc5d-108">Con ellas, el atacante puede iniciar sesión como el usuario original y realizar acciones ilícitas.</span><span class="sxs-lookup"><span data-stu-id="0dc5d-108">With them the attacker can sign in as the original user and perform illicit actions.</span></span>
<span data-ttu-id="0dc5d-109">Con las credenciales robadas, el atacante puede obtener acceso a archivos en OneDrive del usuario, las carpetas de SharePoint o el buzón de Microsoft 365 del usuario.</span><span class="sxs-lookup"><span data-stu-id="0dc5d-109">Using the stolen credentials, the attacker can access the user's Microsoft 365 mailbox, SharePoint folders, or files in the user's OneDrive.</span></span> <span data-ttu-id="0dc5d-110">Una acción habitual es que el atacante envíe correos electrónicos como el usuario original a destinatarios tanto dentro como fuera de la organización.</span><span class="sxs-lookup"><span data-stu-id="0dc5d-110">One action commonly seen is the attacker sending emails as the original user to recipients both inside and outside of the organization.</span></span> <span data-ttu-id="0dc5d-111">Cuando el atacante envía datos a destinatarios externos, se denomina "exfiltración" de datos.</span><span class="sxs-lookup"><span data-stu-id="0dc5d-111">When the attacker emails data to external recipients, this is called data exfiltration.</span></span>

## <a name="symptoms-of-a-compromised-microsoft-email-account"></a><span data-ttu-id="0dc5d-112">Síntomas de una cuenta de correo electrónico de Microsoft en peligro</span><span class="sxs-lookup"><span data-stu-id="0dc5d-112">Symptoms of a Compromised Microsoft Email Account</span></span>

<span data-ttu-id="0dc5d-113">Los usuarios pueden observar e informar sobre actividad inusual en sus buzones de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0dc5d-113">Users might notice and report unusual activity in their Microsoft 365 mailboxes.</span></span> <span data-ttu-id="0dc5d-114">Estos son algunos síntomas comunes:</span><span class="sxs-lookup"><span data-stu-id="0dc5d-114">Here are some common symptoms:</span></span>

- <span data-ttu-id="0dc5d-115">Actividad sospechosa, como correos electrónicos eliminados o que faltan.</span><span class="sxs-lookup"><span data-stu-id="0dc5d-115">Suspicious activity, such as missing or deleted emails.</span></span>

- <span data-ttu-id="0dc5d-116">Otros usuarios pueden recibir correos electrónicos de la cuenta en peligro sin que el correo electrónico correspondiente aparezca en la carpeta **Elementos enviados** del remitente.</span><span class="sxs-lookup"><span data-stu-id="0dc5d-116">Other users might receive emails from the compromised account without the corresponding email existing in the **Sent Items** folder of the sender.</span></span>

- <span data-ttu-id="0dc5d-117">La presencia de reglas de bandeja de entrada que no se han creado por el usuario o el administrador.</span><span class="sxs-lookup"><span data-stu-id="0dc5d-117">The presence of inbox rules that weren't created by the intended user or the administrator.</span></span> <span data-ttu-id="0dc5d-118">Estas reglas pueden reenviar automáticamente correos electrónicos a direcciones desconocidas o moverlos a las carpetas de **Notas**, **Correo no deseado** o **Suscripciones RSS**.</span><span class="sxs-lookup"><span data-stu-id="0dc5d-118">These rules may automatically forward emails to unknown addresses or move them to the **Notes**, **Junk Email**, or **RSS Subscriptions** folders.</span></span>

- <span data-ttu-id="0dc5d-119">El nombre para mostrar del usuario puede cambiarse en la lista Global de direcciones.</span><span class="sxs-lookup"><span data-stu-id="0dc5d-119">The user's display name might be changed in the Global Address List.</span></span>

- <span data-ttu-id="0dc5d-120">El buzón del usuario está bloqueado para enviar correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="0dc5d-120">The user's mailbox is blocked from sending email.</span></span>

- <span data-ttu-id="0dc5d-121">Las carpetas de Elementos enviados o Elementos eliminados en Microsoft Outlook o Outlook en la Web (anteriormente conocido como Outlook Web App) contienen mensajes comunes de cuentas robadas, como "Estoy atascado en Londres, envíame dinero".</span><span class="sxs-lookup"><span data-stu-id="0dc5d-121">The Sent or Deleted Items folders in Microsoft Outlook or Outlook on the web (formerly known as Outlook Web App) contain common hacked-account messages, such as "I'm stuck in London, send money."</span></span>

- <span data-ttu-id="0dc5d-122">Se han realizado cambios inusuales en el perfil, como el nombre, el número de teléfono o el código postal.</span><span class="sxs-lookup"><span data-stu-id="0dc5d-122">Unusual profile changes, such as the name, the telephone number, or the postal code were updated.</span></span>

- <span data-ttu-id="0dc5d-123">Cambios inusuales de credenciales, como múltiples cambios de contraseña requeridos.</span><span class="sxs-lookup"><span data-stu-id="0dc5d-123">Unusual credential changes, such as multiple password changes are required.</span></span>

- <span data-ttu-id="0dc5d-124">Se ha agregado recientemente el reenvío de correo.</span><span class="sxs-lookup"><span data-stu-id="0dc5d-124">Mail forwarding was recently added.</span></span>

- <span data-ttu-id="0dc5d-125">Se ha agregado recientemente una firma inusual, como una firma de entidad bancaria falsa o una firma de recetas de medicamentos.</span><span class="sxs-lookup"><span data-stu-id="0dc5d-125">An unusual signature was recently added, such as a fake banking signature or a prescription drug signature.</span></span>

<span data-ttu-id="0dc5d-126">Si un usuario informa de los síntomas anteriores, debería realizar una mayor investigación.</span><span class="sxs-lookup"><span data-stu-id="0dc5d-126">If a user reports any of the above symptoms, you should perform further investigation.</span></span> <span data-ttu-id="0dc5d-127">El Centro de seguridad y cumplimiento de Microsoft 365 y el Portal de Azure ofrecen herramientas para ayudarle a investigar la actividad de una cuenta de usuario que crea que puede estar en riesgo.</span><span class="sxs-lookup"><span data-stu-id="0dc5d-127">The Microsoft 365 Security & Compliance Center and the Azure Portal offer tools to help you investigate the activity of a user account that you suspect may be compromised.</span></span>

- <span data-ttu-id="0dc5d-128">**Registros de auditoría unificados en el Centro de seguridad y cumplimiento**: revise todas las actividades de la cuenta sospechosa, filtre los resultados con un rango de fechas que abarque desde antes de que se produjese la actividad sospechosa hasta la fecha actual.</span><span class="sxs-lookup"><span data-stu-id="0dc5d-128">**Unified Audit Logs in the Security & Compliance Center**: Review all the activities for the suspected account by filtering the results for the date range spanning from immediately before the suspicious activity occurred to the current date.</span></span> <span data-ttu-id="0dc5d-129">No filtre las actividades durante la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="0dc5d-129">Do not filter on the activities during the search.</span></span>

- <span data-ttu-id="0dc5d-130">**Registros de auditoría de administrador en el EAC**: en Exchange Online, puede usar el Centro de administración de Exchange (EAC) para buscar y ver las entradas del registro de auditoría del administrador.</span><span class="sxs-lookup"><span data-stu-id="0dc5d-130">**Admin Audit logs in the EAC**: In Exchange Online, you can use the Exchange admin center (EAC) to search for and view entries in the administrator audit log.</span></span> <span data-ttu-id="0dc5d-131">El registro de auditoría del administrador registra acciones específicas, según los cmdlets de PowerShell de Exchange Online, realizadas por administradores y usuarios que tienen asignados privilegios de administrador.</span><span class="sxs-lookup"><span data-stu-id="0dc5d-131">The administrator audit log records specific actions, based on Exchange Online PowerShell cmdlets, performed by administrators and users who have been assigned administrative privileges.</span></span> <span data-ttu-id="0dc5d-132">Las entradas en el registro de auditoría del administrador proporcionan información acerca del cmdlet que se ejecutó, los parámetros que se usaron, el usuario que ejecutó el cmdlet y los objetos que se vieron afectados.</span><span class="sxs-lookup"><span data-stu-id="0dc5d-132">Entries in the administrator audit log provide you with information about what cmdlet was run, which parameters were used, who ran the cmdlet, and what objects were affected.</span></span>

- <span data-ttu-id="0dc5d-133">**Registros de inicio de sesión de Azure AD y otros informes de riesgos en el portal de Azure AD**: examine los valores de estas columnas:</span><span class="sxs-lookup"><span data-stu-id="0dc5d-133">**Azure AD Sign-in logs and other risk reports in the Azure AD portal**: Examine the values in these columns:</span></span>

  - <span data-ttu-id="0dc5d-134">Revise la dirección IP</span><span class="sxs-lookup"><span data-stu-id="0dc5d-134">Review IP address</span></span>

  - <span data-ttu-id="0dc5d-135">ubicaciones de inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="0dc5d-135">sign-in locations</span></span>

  - <span data-ttu-id="0dc5d-136">horas de inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="0dc5d-136">sign-in times</span></span>

  - <span data-ttu-id="0dc5d-137">inicios de sesión correctos y fallidos</span><span class="sxs-lookup"><span data-stu-id="0dc5d-137">sign-in success or failure</span></span>

## <a name="how-to-secure-and-restore-email-function-to-a-suspected-compromised-microsoft-365-account-and-mailbox"></a><span data-ttu-id="0dc5d-138">Cómo proteger y restaurar la función de correo electrónico a un buzón o una cuenta de Microsoft 365 en peligro</span><span class="sxs-lookup"><span data-stu-id="0dc5d-138">How to secure and restore email function to a suspected compromised Microsoft 365 account and mailbox</span></span>

> [!VIDEO https://videoplayercdn.osi.office.net/hub/?csid=ux-cms-en-us-msoffice&uuid=RE2jvOb&AutoPlayVideo=false]

<span data-ttu-id="0dc5d-139">Incluso después de haber recuperado el acceso a su cuenta, el atacante puede haber agregado entradas traseras que permiten le permiten reanudar el control de la cuenta.</span><span class="sxs-lookup"><span data-stu-id="0dc5d-139">Even after you've regained access to your account, the attacker may have added back-door entries that enable the attacker to resume control of the account.</span></span>

<span data-ttu-id="0dc5d-140">Debe realizar todos los pasos siguientes para volver a tener acceso a su cuenta lo antes posible para asegurarse de que el atacante no reanude el control de su cuenta.</span><span class="sxs-lookup"><span data-stu-id="0dc5d-140">You must perform all the following steps to regain access to your account the sooner the better to make sure that the hijacker doesn't resume control your account.</span></span> <span data-ttu-id="0dc5d-141">Estos pasos le ayudan a quitar las entradas traseras que puede haber agregado el atacante a su cuenta.</span><span class="sxs-lookup"><span data-stu-id="0dc5d-141">These steps help you remove any back-door entries that the hijacker may have added to your account.</span></span> <span data-ttu-id="0dc5d-142">Después de completar estos pasos, se recomienda que ejecute una detección de virus para asegurarse de que su equipo no está en peligro.</span><span class="sxs-lookup"><span data-stu-id="0dc5d-142">After you perform these steps, we recommend that you run a virus scan to make sure that your computer isn't compromised.</span></span>

### <a name="step-1-reset-the-users-password"></a><span data-ttu-id="0dc5d-143">Paso 1 Restablecer la contraseña del usuario</span><span class="sxs-lookup"><span data-stu-id="0dc5d-143">Step 1 Reset the user's password</span></span>

> [!WARNING]
> <span data-ttu-id="0dc5d-144">No envíe la nueva contraseña al usuario en cuestión por correo electrónico, ya que el atacante todavía tiene acceso al buzón en este momento.</span><span class="sxs-lookup"><span data-stu-id="0dc5d-144">Do not send the new password to the intended user through email as the attacker still has access to the mailbox at this point.</span></span>

1. <span data-ttu-id="0dc5d-145">Siga los procedimientos para Restablecer una contraseña de aplicaciones de Microsoft 365 para otro usuario en [Restablecer contraseñas de aplicaciones de Microsoft 365 Empresa](https://docs.microsoft.com/microsoft-365/admin/add-users/reset-passwords)</span><span class="sxs-lookup"><span data-stu-id="0dc5d-145">Follow the Reset a Microsoft 365 Apps for business password for someone else procedures in [Reset Microsoft 365 Apps for business passwords](https://docs.microsoft.com/microsoft-365/admin/add-users/reset-passwords)</span></span>

<span data-ttu-id="0dc5d-146">**Notas**:</span><span class="sxs-lookup"><span data-stu-id="0dc5d-146">**Notes**:</span></span>

- <span data-ttu-id="0dc5d-147">Asegúrese de que la contraseña es segura y que contiene al menos un carácter especial, al menos un número y letras mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="0dc5d-147">Make sure that the password is strong and that it contains upper and lowercase letters, at least one number, and at least one special character.</span></span>

- <span data-ttu-id="0dc5d-148">No vuelva a usar ninguna de las últimas cinco contraseñas.</span><span class="sxs-lookup"><span data-stu-id="0dc5d-148">Don't reuse any of your last five passwords.</span></span> <span data-ttu-id="0dc5d-149">Aunque el requisito de historial de contraseña le permite volver a usar una contraseña más reciente, debería seleccionar algo que el atacante no pueda adivinar.</span><span class="sxs-lookup"><span data-stu-id="0dc5d-149">Even though the password history requirement lets you reuse a more recent password, you should select something that the attacker can't guess.</span></span>

- <span data-ttu-id="0dc5d-150">Si la identidad local se federa con Microsoft 365, debe cambiar la contraseña en el entorno local y, a continuación, debe notificar el peligro a su administrador.</span><span class="sxs-lookup"><span data-stu-id="0dc5d-150">If your on-premises identity is federated with Microsoft 365, you must change your password on-premises, and then you must notify your administrator of the compromise.</span></span>

> [!TIP]
> <span data-ttu-id="0dc5d-151">Se recomienda que habilite la autenticación multifactor (MFA) para evitar los robos de cuenta, especialmente para las cuentas con privilegios de administrador.</span><span class="sxs-lookup"><span data-stu-id="0dc5d-151">We highly recommended that you enable Multi-Factor Authentication (MFA) in order to prevent compromise, especially for accounts with administrative privileges.</span></span>  <span data-ttu-id="0dc5d-152">Para obtener más información sobre MFA, vaya a [Configurar la autenticación multifactor](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication).</span><span class="sxs-lookup"><span data-stu-id="0dc5d-152">To learn more about MFA, go to [Set up multi-factor authentication](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication).</span></span>

### <a name="step-2-remove-suspicious-email-forwarding-addresses"></a><span data-ttu-id="0dc5d-153">Paso 2 Eliminar direcciones de reenvío de correo electrónico sospechosas</span><span class="sxs-lookup"><span data-stu-id="0dc5d-153">Step 2 Remove suspicious email forwarding addresses</span></span>

1. <span data-ttu-id="0dc5d-154">Abra el **Centro de administración de Microsoft 365 > Usuarios activos**.</span><span class="sxs-lookup"><span data-stu-id="0dc5d-154">Open the **Microsoft 365 admin center > Active Users**.</span></span>

2. <span data-ttu-id="0dc5d-155">Busque la cuenta del usuario en cuestión y expanda **Configuración de correo**.</span><span class="sxs-lookup"><span data-stu-id="0dc5d-155">Find the user account in question and expand **Mail Settings**.</span></span>

3. <span data-ttu-id="0dc5d-156">Para **Reenvío de correo electrónico**, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="0dc5d-156">For **Email forwarding**, click **Edit**.</span></span>

4. <span data-ttu-id="0dc5d-157">Quite las direcciones de reenvío sospechosas.</span><span class="sxs-lookup"><span data-stu-id="0dc5d-157">Remove any suspicious forwarding addresses.</span></span>

### <a name="step-3-disable-any-suspicious-inbox-rules"></a><span data-ttu-id="0dc5d-158">Paso 3 Deshabilitar las reglas de bandeja de entrada sospechosas</span><span class="sxs-lookup"><span data-stu-id="0dc5d-158">Step 3 Disable any suspicious inbox rules</span></span>

1. <span data-ttu-id="0dc5d-159">Inicie sesión en el buzón del usuario con Outlook en la Web.</span><span class="sxs-lookup"><span data-stu-id="0dc5d-159">Sign in to the user's mailbox using Outlook on the web.</span></span>

2. <span data-ttu-id="0dc5d-160">Haga clic en el icono del engranaje y en **Correo**.</span><span class="sxs-lookup"><span data-stu-id="0dc5d-160">Click on the gear icon and click **Mail**.</span></span>

3. <span data-ttu-id="0dc5d-161">Haga clic en **Reglas de bandeja de entrada y barrido** y revise las reglas.</span><span class="sxs-lookup"><span data-stu-id="0dc5d-161">Click **Inbox and sweep rules** and review the rules.</span></span>

4. <span data-ttu-id="0dc5d-162">Deshabilite o elimine las reglas sospechosas.</span><span class="sxs-lookup"><span data-stu-id="0dc5d-162">Disable or delete suspicious rules.</span></span>

### <a name="step-4-unblock-the-user-from-sending-mail"></a><span data-ttu-id="0dc5d-163">Paso 4 Desbloquear el usuario para que pueda enviar correo</span><span class="sxs-lookup"><span data-stu-id="0dc5d-163">Step 4 Unblock the user from sending mail</span></span>

<span data-ttu-id="0dc5d-164">Si el buzón en peligro se usó de forma ilícita para enviar correo no deseado, es probable que el buzón se haya bloqueado para impedir el envío de correo.</span><span class="sxs-lookup"><span data-stu-id="0dc5d-164">If the suspected compromised mailbox was used illicitly to send spam email, it is likely that the mailbox has been blocked from sending mail.</span></span>

<span data-ttu-id="0dc5d-165">Para desbloquear el envío de correo de un buzón, siga los procedimientos descritos en [Quitar un usuario, un dominio o una dirección IP de una lista de bloqueados después de enviar correo no deseado](removing-user-from-restricted-users-portal-after-spam.md).</span><span class="sxs-lookup"><span data-stu-id="0dc5d-165">To unblock a mailbox from sending mail, follow the procedures in [Removing a user from the Restricted Users portal after sending spam email](removing-user-from-restricted-users-portal-after-spam.md).</span></span>

### <a name="step-5-optional-block-the-user-account-from-signing-in"></a><span data-ttu-id="0dc5d-166">Paso 5 opcional: Bloquear la cuenta de usuario para impedir el inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="0dc5d-166">Step 5 Optional: Block the user account from signing-in</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0dc5d-167">Puede bloquear la cuenta en peligro e impedir que inicie hasta que crea que es seguro volver a habilitar el acceso.</span><span class="sxs-lookup"><span data-stu-id="0dc5d-167">You can block the suspected compromised account from signing-in until you believe it is safe to re-enable access.</span></span>

1. <span data-ttu-id="0dc5d-168">Vaya al Centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0dc5d-168">Go to the Microsoft 365 admin center.</span></span>

2. <span data-ttu-id="0dc5d-169">En el Centro de administración de Microsoft 365, seleccione **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="0dc5d-169">In the Microsoft 365 admin center, select **Users**.</span></span>

3. <span data-ttu-id="0dc5d-170">Seleccione el empleado que desee bloquear y luego elija **Editar** junto a **Estado de inicio de sesión** en el panel de usuario.</span><span class="sxs-lookup"><span data-stu-id="0dc5d-170">Select the employee that you want to block, and then choose **Edit** next to **Sign-in status** in the user pane.</span></span>

4. <span data-ttu-id="0dc5d-171">En el panel **Estado de inicio de sesión**, elija **Inicio de sesión bloqueado** y luego **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="0dc5d-171">On the **Sign-in status** pane, choose **Sign-in blocked** and then **Save**.</span></span>

5. <span data-ttu-id="0dc5d-172">En el Centro de administración, en el panel de navegación de la parte inferior izquierda, expanda **Centros de administración** y seleccione **Exchange**.</span><span class="sxs-lookup"><span data-stu-id="0dc5d-172">In the Admin center, in the lower-left navigation pane, expand **Admin Centers** and select **Exchange**.</span></span>

6. <span data-ttu-id="0dc5d-173">En el Centro de administración de Exchange, navegue a **Destinatarios > Recursos**.</span><span class="sxs-lookup"><span data-stu-id="0dc5d-173">In the Exchange admin center, navigate to **Recipients > Mailboxes**.</span></span>

7. <span data-ttu-id="0dc5d-174">Seleccione el usuario y, en la página de propiedades de usuario, en **Dispositivos móviles**, haga clic en **Deshabilitar Exchange ActiveSync** y **Deshabilitar OWA para dispositivos** y responda **Sí** a ambos.</span><span class="sxs-lookup"><span data-stu-id="0dc5d-174">Select the user, and on the user properties page, under **Mobile Devices**, click **Disable Exchange ActivcSync** and **Disable OWA for Devices** and answer **yes** to both.</span></span>

8. <span data-ttu-id="0dc5d-175">En **Conectividad de correo**, haga clic en **Deshabilitar** y responda **Sí**.</span><span class="sxs-lookup"><span data-stu-id="0dc5d-175">Under **Email Connectivity**, **Disable** and answer **yes**.</span></span>

### <a name="step-6-optional-remove-the-suspected-compromised-account-from-all-administrative-role-groups"></a><span data-ttu-id="0dc5d-176">Paso 6 opcional: Quitar la cuenta en peligro de todos los grupos de roles administrativos</span><span class="sxs-lookup"><span data-stu-id="0dc5d-176">Step 6 Optional: Remove the suspected compromised account from all administrative role groups</span></span>

> [!NOTE]
> <span data-ttu-id="0dc5d-177">La pertenencia a grupos de roles administrativos puede restaurarse después de haber asegurado la cuenta.</span><span class="sxs-lookup"><span data-stu-id="0dc5d-177">Administrative role group membership can be restored after the account has been secured.</span></span>

1. <span data-ttu-id="0dc5d-178">Inicie sesión en el Centro de administración de Microsoft 365 con una cuenta de administrador global y abra **Usuarios activos**.</span><span class="sxs-lookup"><span data-stu-id="0dc5d-178">Sign in to the Microsoft 365 admin center with a global administrator account and open **Active Users**.</span></span>

2. <span data-ttu-id="0dc5d-179">Busque la cuenta en peligro y compruebe manualmente si hay roles administrativos asignados a la cuenta.</span><span class="sxs-lookup"><span data-stu-id="0dc5d-179">Find the suspected compromised account and manually check to see if there are any administrative roles assigned to the account.</span></span>

3. <span data-ttu-id="0dc5d-180">Abra el **Centro de seguridad y cumplimiento**.</span><span class="sxs-lookup"><span data-stu-id="0dc5d-180">Open the **Security & Compliance Center**.</span></span>

4. <span data-ttu-id="0dc5d-181">Haga clic en **Permisos**.</span><span class="sxs-lookup"><span data-stu-id="0dc5d-181">Click **Permissions**.</span></span>

5. <span data-ttu-id="0dc5d-182">Revise manualmente los grupos de roles para ver si la cuenta en peligro es miembro de cualquiera de ellos.</span><span class="sxs-lookup"><span data-stu-id="0dc5d-182">Manually review the role groups to see if the suspected compromised account is a member of any of them.</span></span>  <span data-ttu-id="0dc5d-183">Si lo es:</span><span class="sxs-lookup"><span data-stu-id="0dc5d-183">If it is:</span></span>

   <span data-ttu-id="0dc5d-184">a.</span><span class="sxs-lookup"><span data-stu-id="0dc5d-184">a.</span></span> <span data-ttu-id="0dc5d-185">Haga clic en el grupo de roles y **Editar grupo de roles**.</span><span class="sxs-lookup"><span data-stu-id="0dc5d-185">Click the role group and click **Edit Role Group**.</span></span>

   <span data-ttu-id="0dc5d-186">b.</span><span class="sxs-lookup"><span data-stu-id="0dc5d-186">b.</span></span> <span data-ttu-id="0dc5d-187">Haga clic en **Elegir miembros** y **Editar** para quitar el usuario del grupo de roles.</span><span class="sxs-lookup"><span data-stu-id="0dc5d-187">Click **Chose Members** and **Edit** to remove the user from the role group.</span></span>

6. <span data-ttu-id="0dc5d-188">Abra el **Centro de administración de Exchange**.</span><span class="sxs-lookup"><span data-stu-id="0dc5d-188">Open the **Exchange admin center**.</span></span>

7. <span data-ttu-id="0dc5d-189">Haga clic en **Permisos**.</span><span class="sxs-lookup"><span data-stu-id="0dc5d-189">Click **Permissions**.</span></span>

8. <span data-ttu-id="0dc5d-190">Revise manualmente los grupos de roles para ver si la cuenta en peligro es miembro de cualquiera de ellos.</span><span class="sxs-lookup"><span data-stu-id="0dc5d-190">Manually review the role groups to see if the suspected compromised account is a member of any of them.</span></span> <span data-ttu-id="0dc5d-191">Si lo es:</span><span class="sxs-lookup"><span data-stu-id="0dc5d-191">If it is:</span></span>

   <span data-ttu-id="0dc5d-192">a.</span><span class="sxs-lookup"><span data-stu-id="0dc5d-192">a.</span></span> <span data-ttu-id="0dc5d-193">Haga clic en el grupo de roles y en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="0dc5d-193">Click the role group and click **Edit**.</span></span>

   <span data-ttu-id="0dc5d-194">b.</span><span class="sxs-lookup"><span data-stu-id="0dc5d-194">b.</span></span> <span data-ttu-id="0dc5d-195">Use la sección **miembros** para quitar el usuario del grupo de roles.</span><span class="sxs-lookup"><span data-stu-id="0dc5d-195">Use the **members** section to remove the user from the role group.</span></span>

### <a name="step-7-optional-additional-precautionary-steps"></a><span data-ttu-id="0dc5d-196">Paso 7 opcional: Pasos de precauciones adicionales</span><span class="sxs-lookup"><span data-stu-id="0dc5d-196">Step 7 Optional: Additional precautionary steps</span></span>

1. <span data-ttu-id="0dc5d-197">Asegúrese de comprobar los elementos enviados.</span><span class="sxs-lookup"><span data-stu-id="0dc5d-197">Make sure that you verify your sent items.</span></span> <span data-ttu-id="0dc5d-198">Puede que tenga que informar a los usuarios de la lista de contactos de que su cuenta está comprometida.</span><span class="sxs-lookup"><span data-stu-id="0dc5d-198">You may have to inform people on your contacts list that your account was compromised.</span></span> <span data-ttu-id="0dc5d-199">El atacante puede haberles pedido dinero fingiendo, por ejemplo, que estaba perdido en un país distinto y necesitaba dinero, o el atacante puede enviarles un virus para obtener acceso también a sus equipos.</span><span class="sxs-lookup"><span data-stu-id="0dc5d-199">The attacker may have asked them for money, spoofing, for example, that you were stranded in a different country and needed money, or the attacker may send them a virus to also hijack their computers.</span></span>

2. <span data-ttu-id="0dc5d-200">Cualquier otro servicio que use esta cuenta de Exchange como cuenta de correo electrónico alternativa puede haberse comprometido también.</span><span class="sxs-lookup"><span data-stu-id="0dc5d-200">Any other service that used this Exchange account as its alternative email account may have been compromised.</span></span> <span data-ttu-id="0dc5d-201">En primer lugar, siga estos pasos para la suscripción de Microsoft 365 y, a continuación, siga estos pasos para otras cuentas.</span><span class="sxs-lookup"><span data-stu-id="0dc5d-201">First, perform these steps for your Microsoft 365 subscription, and then perform these steps for your other accounts.</span></span>

3. <span data-ttu-id="0dc5d-202">Asegúrese de que la información de contacto, como los números de teléfono y direcciones, es correcta.</span><span class="sxs-lookup"><span data-stu-id="0dc5d-202">Make sure that your contact information, such as telephone numbers and addresses, is correct.</span></span>

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a><span data-ttu-id="0dc5d-203">Proteger Microsoft 365 como un profesional de la ciberseguridad</span><span class="sxs-lookup"><span data-stu-id="0dc5d-203">Secure Microsoft 365 like a cybersecurity pro</span></span>

<span data-ttu-id="0dc5d-204">Su suscripción a Microsoft 365 incluye un potente conjunto de capacidades de seguridad que puede usar para proteger sus datos y los usuarios.</span><span class="sxs-lookup"><span data-stu-id="0dc5d-204">Your Microsoft 365 subscription comes with a powerful set of security capabilities that you can use to protect your data and your users.</span></span>  <span data-ttu-id="0dc5d-205">Use el [Plan de seguridad de Microsoft 365: principales prioridades para los primeros 30 días, 90 días y en adelante](security-roadmap.md) para implementar las prácticas recomendadas de Microsoft para proteger su espacio empresarial de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0dc5d-205">Use the [Microsoft 365 security roadmap - Top priorities for the first 30 days, 90 days, and beyond](security-roadmap.md) to implement Microsoft recommended best practices for securing your Microsoft 365 tenant.</span></span>

- <span data-ttu-id="0dc5d-206">Tareas a realizar en los primeros 30 días.</span><span class="sxs-lookup"><span data-stu-id="0dc5d-206">Tasks to accomplish in the first 30 days.</span></span>  <span data-ttu-id="0dc5d-207">Estas tienen un efecto inmediato y de bajo impacto para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="0dc5d-207">These have immediate affect and are low-impact to your users.</span></span>

- <span data-ttu-id="0dc5d-208">Tareas para llevar a cabo en 90 días.</span><span class="sxs-lookup"><span data-stu-id="0dc5d-208">Tasks to accomplish in 90 days.</span></span> <span data-ttu-id="0dc5d-209">Estas tareas necesitan un poco más de tiempo para planearlas e implementarlas, pero mejoran considerablemente el nivel de seguridad.</span><span class="sxs-lookup"><span data-stu-id="0dc5d-209">These take a bit more time to plan and implement but greatly improve your security posture.</span></span>

- <span data-ttu-id="0dc5d-210">Más de 90 días.</span><span class="sxs-lookup"><span data-stu-id="0dc5d-210">Beyond 90 days.</span></span> <span data-ttu-id="0dc5d-211">Estas mejoras se crean en el trabajo de los 90 primeros días.</span><span class="sxs-lookup"><span data-stu-id="0dc5d-211">These enhancements build in your first 90 days work.</span></span>

## <a name="see-also"></a><span data-ttu-id="0dc5d-212">Vea también</span><span class="sxs-lookup"><span data-stu-id="0dc5d-212">See also</span></span>

- [<span data-ttu-id="0dc5d-213">Detectar y corregir las reglas de Outlook y ataques de inserciones de formularios personalizados en Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0dc5d-213">Detect and Remediate Outlook Rules and Custom Forms Injections Attacks in Microsoft 365</span></span>](detect-and-remediate-outlook-rules-forms-attack.md)

- [<span data-ttu-id="0dc5d-214">Centro de Quejas de Crímenes por Internet</span><span class="sxs-lookup"><span data-stu-id="0dc5d-214">Internet Crime Complaint Center</span></span>](https://www.ic3.gov/preventiontips.aspx)

- [<span data-ttu-id="0dc5d-215">Bolsas de valores de EE. UU.: Fraude de suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="0dc5d-215">Securities and Exchange Commission - "Phishing" Fraud</span></span>](https://www.sec.gov/investor/pubs/phishing.htm)

- <span data-ttu-id="0dc5d-216">Para informar directamente a Microsoft y su administrador sobre el correo no deseado [Use el complemento Informar sobre el mensaje](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)</span><span class="sxs-lookup"><span data-stu-id="0dc5d-216">To report spam email directly to Microsoft and your admin [Use the Report Message add-in](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)</span></span>
