---
title: Responder a una cuenta de correo electrónico en peligro en Office 365
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.collection:
- o365_security_incident_response
- M365-security-compliance
ms.custom: TopSMBIssues
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
description: Aprenda a reconocer y responder a una cuenta de correo electrónico en peligro en Office 365
ms.openlocfilehash: 76ce2cd9b942403f5d25b7f356740cce6c2acad7
ms.sourcegitcommit: 5710ce729c55d95b8b452d99ffb7ea92b5cb254a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2019
ms.locfileid: "39971517"
---
# <a name="responding-to-a-compromised-email-account-in-office-365"></a><span data-ttu-id="60c0b-103">Responder a una cuenta de correo electrónico en peligro en Office 365</span><span class="sxs-lookup"><span data-stu-id="60c0b-103">Responding to a Compromised Email Account in Office 365</span></span>

<span data-ttu-id="60c0b-104">**Resumen** Aprenda a reconocer y responder a una cuenta de correo electrónico en peligro en Office 365</span><span class="sxs-lookup"><span data-stu-id="60c0b-104">**Summary** Learn how to recognize and respond to a compromised email account in Office 365.</span></span>

## <a name="what-is-a-compromised-email-account-in-office-365"></a><span data-ttu-id="60c0b-105">¿Qué es una cuenta de correo electrónico en peligro en Office 365?</span><span class="sxs-lookup"><span data-stu-id="60c0b-105">What is a Compromised Email Account in Office 365?</span></span>

<span data-ttu-id="60c0b-106">El acceso a los buzones, los datos y otros servicios de Office 365 se controla mediante el uso de credenciales, como un nombre de usuario y contraseña o PIN.</span><span class="sxs-lookup"><span data-stu-id="60c0b-106">Access to Office 365 mailboxes, data and other services, is controlled through the use of credentials, for example a user name and password or PIN.</span></span> <span data-ttu-id="60c0b-107">Cuando alguien que no sea el usuario roba estas credenciales, se considera que las credenciales robadas suponen un riesgo.</span><span class="sxs-lookup"><span data-stu-id="60c0b-107">When someone other than the intended user steals those credentials, the stolen credentials are considered to be compromised.</span></span> <span data-ttu-id="60c0b-108">Con ellas, el atacante puede iniciar sesión como el usuario original y realizar acciones ilícitas.</span><span class="sxs-lookup"><span data-stu-id="60c0b-108">With them the attacker can sign in as the original user and perform illicit actions.</span></span>
<span data-ttu-id="60c0b-109">Con las credenciales robadas, el atacante puede obtener acceso a archivos en OneDrive del usuario, las carpetas de SharePoint o el buzón de Office 365 del usuario.</span><span class="sxs-lookup"><span data-stu-id="60c0b-109">Using the stolen credentials, the attacker can access the user’s Office 365 mailbox, SharePoint folders, or files in the user's OneDrive.</span></span> <span data-ttu-id="60c0b-110">Una acción habitual es que el atacante envíe correos electrónicos como el usuario original a destinatarios tanto dentro como fuera de la organización.</span><span class="sxs-lookup"><span data-stu-id="60c0b-110">One action commonly seen is the attacker sending emails as the original user to recipients both inside and outside of the organization.</span></span> <span data-ttu-id="60c0b-111">Cuando el atacante envía datos a destinatarios externos, se denomina "exfiltración" de datos.</span><span class="sxs-lookup"><span data-stu-id="60c0b-111">When the attacker emails data to external recipients, this is called data exfiltration.</span></span>

## <a name="symptoms-of-a-compromised-office-365-email-account"></a><span data-ttu-id="60c0b-112">Síntomas de una cuenta de correo electrónico en peligro de Office 365</span><span class="sxs-lookup"><span data-stu-id="60c0b-112">Symptoms of a Compromised Office 365 Email Account</span></span>

<span data-ttu-id="60c0b-113">Los usuarios pueden observar e informar sobre actividad inusual en sus buzones de Office 365.</span><span class="sxs-lookup"><span data-stu-id="60c0b-113">Users might notice and report unusual activity in their Office 365 mailboxes.</span></span> <span data-ttu-id="60c0b-114">Estos son algunos síntomas comunes:</span><span class="sxs-lookup"><span data-stu-id="60c0b-114">Here are some common symptoms:</span></span>

- <span data-ttu-id="60c0b-115">Actividad sospechosa, como correos electrónicos eliminados o que faltan.</span><span class="sxs-lookup"><span data-stu-id="60c0b-115">Suspicious activity, such as missing or deleted emails.</span></span>

- <span data-ttu-id="60c0b-116">Otros usuarios pueden recibir correos electrónicos de la cuenta en peligro sin que el correo electrónico correspondiente aparezca en la carpeta **Elementos enviados** del remitente.</span><span class="sxs-lookup"><span data-stu-id="60c0b-116">Other users might receive emails from the compromised account without the corresponding email existing in the **Sent Items** folder of the sender.</span></span>

- <span data-ttu-id="60c0b-117">La presencia de reglas de bandeja de entrada que no se han creado por el usuario o el administrador.</span><span class="sxs-lookup"><span data-stu-id="60c0b-117">The presence of inbox rules that weren't created by the intended user or the administrator.</span></span> <span data-ttu-id="60c0b-118">Estas reglas pueden reenviar automáticamente correos electrónicos a direcciones desconocidas o moverlos a las carpetas de **Notas**, **Correo no deseado** o **Suscripciones RSS**.</span><span class="sxs-lookup"><span data-stu-id="60c0b-118">These rules may automatically forward emails to unknown addresses or move them to the **Notes**, **Junk Email**, or **RSS Subscriptions** folders.</span></span>

- <span data-ttu-id="60c0b-119">El nombre para mostrar del usuario puede cambiarse en la lista Global de direcciones.</span><span class="sxs-lookup"><span data-stu-id="60c0b-119">The user's display name might be changed in the Global Address List.</span></span>

- <span data-ttu-id="60c0b-120">El buzón del usuario está bloqueado para enviar correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="60c0b-120">The user's mailbox is blocked from sending email.</span></span>

- <span data-ttu-id="60c0b-121">Las carpetas de Elementos enviados o Elementos eliminados en Microsoft Outlook o Outlook en la Web (anteriormente conocido como Outlook Web App) contienen mensajes comunes de cuentas robadas, como "Estoy atascado en Londres, envíame dinero".</span><span class="sxs-lookup"><span data-stu-id="60c0b-121">The Sent or Deleted Items folders in Microsoft Outlook or Outlook on the web (formerly known as Outlook Web App) contain common hacked-account messages, such as "I'm stuck in London, send money."</span></span>

- <span data-ttu-id="60c0b-122">Se han realizado cambios inusuales en el perfil, como el nombre, el número de teléfono o el código postal.</span><span class="sxs-lookup"><span data-stu-id="60c0b-122">Unusual profile changes, such as the name, the telephone number, or the postal code were updated.</span></span>

- <span data-ttu-id="60c0b-123">Cambios inusuales de credenciales, como múltiples cambios de contraseña requeridos.</span><span class="sxs-lookup"><span data-stu-id="60c0b-123">Unusual credential changes, such as multiple password changes are required.</span></span>

- <span data-ttu-id="60c0b-124">Se ha agregado recientemente el reenvío de correo.</span><span class="sxs-lookup"><span data-stu-id="60c0b-124">Mail forwarding was recently added.</span></span>

- <span data-ttu-id="60c0b-125">Se ha agregado recientemente una firma inusual, como una firma de entidad bancaria falsa o una firma de recetas de medicamentos.</span><span class="sxs-lookup"><span data-stu-id="60c0b-125">An unusual signature was recently added, such as a fake banking signature or a prescription drug signature.</span></span>

<span data-ttu-id="60c0b-126">Si un usuario informa de los síntomas anteriores, debería realizar una mayor investigación.</span><span class="sxs-lookup"><span data-stu-id="60c0b-126">If a user reports any of the above symptoms, you should perform further investigation.</span></span> <span data-ttu-id="60c0b-127">El Centro de seguridad y cumplimiento de Microsoft 365 y el Portal de Azure ofrecen herramientas para ayudarle a investigar la actividad de una cuenta de usuario que crea que puede estar en riesgo.</span><span class="sxs-lookup"><span data-stu-id="60c0b-127">The Microsoft 365 Security & Compliance Center and the Azure Portal offer tools to help you investigate the activity of a user account that you suspect may be compromised.</span></span>

- <span data-ttu-id="60c0b-128">Registros de auditoría unificados de Office 365 en el Centro de seguridad y cumplimiento: revise todas las actividades de la cuenta sospechosa, filtre los resultados con un rango de fechas que abarque desde antes de que se produjese la actividad sospechosa hasta la fecha actual.</span><span class="sxs-lookup"><span data-stu-id="60c0b-128">Office 365 Unified Audit Logs in the Security & Compliance Center - Review all the activities for the suspected account by filtering the results for the date range spanning from immediately before the suspicious activity occurred to the current date.</span></span> <span data-ttu-id="60c0b-129">No filtre las actividades durante la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="60c0b-129">Do not filter on the activities during the search.</span></span>

- <span data-ttu-id="60c0b-130">Use los registros de inicio de sesión de Azure AD y otros informes de riesgos que están disponibles en el portal de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="60c0b-130">Use the Azure AD Sign-in logs and other risk reports that are available in the Azure AD portal.</span></span> <span data-ttu-id="60c0b-131">Examine los valores de estas columnas:</span><span class="sxs-lookup"><span data-stu-id="60c0b-131">Examine the values in these columns:</span></span>

  - <span data-ttu-id="60c0b-132">Revise la dirección IP</span><span class="sxs-lookup"><span data-stu-id="60c0b-132">Review IP address</span></span>

  - <span data-ttu-id="60c0b-133">ubicaciones de inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="60c0b-133">sign-in locations</span></span>

  - <span data-ttu-id="60c0b-134">horas de inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="60c0b-134">sign-in times</span></span>

  - <span data-ttu-id="60c0b-135">inicios de sesión correctos y fallidos</span><span class="sxs-lookup"><span data-stu-id="60c0b-135">sign-in success or failure</span></span>

## <a name="how-to-secure-and-restore-email-function-to-a-suspected-compromised-office-365-account-and-mailbox"></a><span data-ttu-id="60c0b-136">Cómo proteger y restaurar la función de correo electrónico a un buzón o una cuenta de Office 365 en peligro</span><span class="sxs-lookup"><span data-stu-id="60c0b-136">How to secure and restore email function to a suspected compromised Office 365 account and mailbox</span></span>

> [!VIDEO https://videoplayercdn.osi.office.net/hub/?csid=ux-cms-en-us-msoffice&uuid=RE2jvOb&AutoPlayVideo=false]

<span data-ttu-id="60c0b-137">Incluso después de haber recuperado el acceso a su cuenta, el atacante puede haber agregado entradas traseras que permiten le permiten reanudar el control de la cuenta.</span><span class="sxs-lookup"><span data-stu-id="60c0b-137">Even after you've regained access to your account, the attacker may have added back-door entries that enable the attacker to resume control of the account.</span></span>

<span data-ttu-id="60c0b-138">Debe realizar todos los pasos siguientes para volver a tener acceso a su cuenta lo antes posible para asegurarse de que el atacante no reanude el control de su cuenta.</span><span class="sxs-lookup"><span data-stu-id="60c0b-138">You must perform all the following steps to regain access to your account the sooner the better to make sure that the hijacker doesn't resume control your account.</span></span> <span data-ttu-id="60c0b-139">Estos pasos le ayudan a quitar las entradas traseras que puede haber agregado el atacante a su cuenta.</span><span class="sxs-lookup"><span data-stu-id="60c0b-139">These steps help you remove any back-door entries that the hijacker may have added to your account.</span></span> <span data-ttu-id="60c0b-140">Después de completar estos pasos, se recomienda que ejecute una detección de virus para asegurarse de que su equipo no está en peligro.</span><span class="sxs-lookup"><span data-stu-id="60c0b-140">After you perform these steps, we recommend that you run a virus scan to make sure that your computer isn't compromised.</span></span>

### <a name="step-1-reset-the-users-password"></a><span data-ttu-id="60c0b-141">Paso 1 Restablecer la contraseña del usuario</span><span class="sxs-lookup"><span data-stu-id="60c0b-141">Step 1 Reset the user's password</span></span>

> [!WARNING]
> <span data-ttu-id="60c0b-142">No envíe la nueva contraseña al usuario en cuestión por correo electrónico, ya que el atacante todavía tiene acceso al buzón en este momento.</span><span class="sxs-lookup"><span data-stu-id="60c0b-142">Do not send the new password to the intended user through email as the attacker still has access to the mailbox at this point.</span></span>

1. <span data-ttu-id="60c0b-143">Siga los procedimientos para Restablecer una contraseña de otro usuario de Office 365 para la Empresa en [Administradores: restablecer contraseñas de Office 365 de la empresa](https://docs.microsoft.com/office365/admin/add-users/reset-passwords)</span><span class="sxs-lookup"><span data-stu-id="60c0b-143">Follow the Reset an Office 365 business password for someone else procedures in [Admins: Reset Office 365 business passwords](https://docs.microsoft.com/office365/admin/add-users/reset-passwords)</span></span>

<span data-ttu-id="60c0b-144">**Notas**:</span><span class="sxs-lookup"><span data-stu-id="60c0b-144">**Notes**:</span></span>

- <span data-ttu-id="60c0b-145">Asegúrese de que la contraseña es segura y que contiene al menos un carácter especial, al menos un número y letras mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="60c0b-145">Make sure that the password is strong and that it contains upper and lowercase letters, at least one number, and at least one special character.</span></span>

- <span data-ttu-id="60c0b-146">No vuelva a usar ninguna de las últimas cinco contraseñas.</span><span class="sxs-lookup"><span data-stu-id="60c0b-146">Don't reuse any of your last five passwords.</span></span> <span data-ttu-id="60c0b-147">Aunque el requisito de historial de contraseña le permite volver a usar una contraseña más reciente, debería seleccionar algo que el atacante no pueda adivinar.</span><span class="sxs-lookup"><span data-stu-id="60c0b-147">Even though the password history requirement lets you reuse a more recent password, you should select something that the attacker can't guess.</span></span>

- <span data-ttu-id="60c0b-148">Si la identidad local se federa con Office 365, debe cambiar la contraseña en el entorno local y, a continuación, debe notificar a su administrador del ataque.</span><span class="sxs-lookup"><span data-stu-id="60c0b-148">If your on-premises identity is federated with Office 365, you must change your password on-premises, and then you must notify your administrator of the compromise.</span></span>

> [!TIP]
> <span data-ttu-id="60c0b-149">Se recomienda que habilite la autenticación multifactor (MFA) para evitar los robos de cuenta, especialmente para las cuentas con privilegios de administrador.</span><span class="sxs-lookup"><span data-stu-id="60c0b-149">It is highly recommended that you enable Multi-Factor Authentication (MFA) in order to prevent compromise, especially for accounts with administrative privileges.</span></span>  <span data-ttu-id="60c0b-150">Puede obtener más información [aquí](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication).</span><span class="sxs-lookup"><span data-stu-id="60c0b-150">You can learn more [here](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication).</span></span>

### <a name="step-2-remove-suspicious-email-forwarding-addresses"></a><span data-ttu-id="60c0b-151">Paso 2 Eliminar direcciones de reenvío de correo electrónico sospechosas</span><span class="sxs-lookup"><span data-stu-id="60c0b-151">Step 2 Remove suspicious email forwarding addresses</span></span>

1. <span data-ttu-id="60c0b-152">Abra el **Centro de administración de Microsoft 365 > Usuarios activos**.</span><span class="sxs-lookup"><span data-stu-id="60c0b-152">Open the **Microsoft 365 admin center > Active Users**.</span></span>

2. <span data-ttu-id="60c0b-153">Busque la cuenta del usuario en cuestión y expanda **Configuración de correo**.</span><span class="sxs-lookup"><span data-stu-id="60c0b-153">Find the user account in question and expand **Mail Settings**.</span></span>

3. <span data-ttu-id="60c0b-154">Para **Reenvío de correo electrónico**, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="60c0b-154">For **Email forwarding**, click **Edit**.</span></span>

4. <span data-ttu-id="60c0b-155">Quite las direcciones de reenvío sospechosas.</span><span class="sxs-lookup"><span data-stu-id="60c0b-155">Remove any suspicious forwarding addresses.</span></span>

### <a name="step-3-disable-any-suspicious-inbox-rules"></a><span data-ttu-id="60c0b-156">Paso 3 Deshabilitar las reglas de bandeja de entrada sospechosas</span><span class="sxs-lookup"><span data-stu-id="60c0b-156">Step 3 Disable any suspicious inbox rules</span></span>

1. <span data-ttu-id="60c0b-157">Inicie sesión en el buzón del usuario con Outlook en la Web.</span><span class="sxs-lookup"><span data-stu-id="60c0b-157">Sign in to the user's mailbox using Outlook on the web.</span></span>

2. <span data-ttu-id="60c0b-158">Haga clic en el icono del engranaje y en **Correo**.</span><span class="sxs-lookup"><span data-stu-id="60c0b-158">Click on the gear icon and click **Mail**.</span></span>

3. <span data-ttu-id="60c0b-159">Haga clic en **Reglas de bandeja de entrada y barrido** y revise las reglas.</span><span class="sxs-lookup"><span data-stu-id="60c0b-159">Click **Inbox and sweep rules** and review the rules.</span></span>

4. <span data-ttu-id="60c0b-160">Deshabilite o elimine las reglas sospechosas.</span><span class="sxs-lookup"><span data-stu-id="60c0b-160">Disable or delete suspicious rules.</span></span>

### <a name="step-4-unblock-the-user-from-sending-mail"></a><span data-ttu-id="60c0b-161">Paso 4 Desbloquear el usuario para que pueda enviar correo</span><span class="sxs-lookup"><span data-stu-id="60c0b-161">Step 4 Unblock the user from sending mail</span></span>

<span data-ttu-id="60c0b-162">Si el buzón en peligro se usó de forma ilícita para enviar correo no deseado, es probable que el buzón se haya bloqueado para impedir el envío de correo.</span><span class="sxs-lookup"><span data-stu-id="60c0b-162">If the suspected compromised mailbox was used illicitly to send spam email, it is likely that the mailbox has been blocked from sending mail.</span></span>

<span data-ttu-id="60c0b-163">Para desbloquear el envío de correo de un buzón, siga los procedimientos descritos en [Quitar un usuario, un dominio o una dirección IP de una lista de bloqueados después de enviar correo no deseado](removing-user-from-restricted-users-portal-after-spam.md).</span><span class="sxs-lookup"><span data-stu-id="60c0b-163">To unblock a mailbox from sending mail, follow the procedures in [Removing a user, domain, or IP Address from a block list after sending spam email](removing-user-from-restricted-users-portal-after-spam.md).</span></span>

### <a name="step-5-optional-block-the-user-account-from-signing-in"></a><span data-ttu-id="60c0b-164">Paso 5 opcional: Bloquear la cuenta de usuario para impedir el inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="60c0b-164">Step 5 Optional: Block the user account from signing-in</span></span>

> [!IMPORTANT]
> <span data-ttu-id="60c0b-165">Puede bloquear la cuenta en peligro e impedir que inicie hasta que crea que es seguro volver a habilitar el acceso.</span><span class="sxs-lookup"><span data-stu-id="60c0b-165">You can block the suspected compromised account from signing-in until you believe it is safe to re-enable access.</span></span>

1. <span data-ttu-id="60c0b-166">Vaya al Centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="60c0b-166">Go to the Microsoft 365 admin center.</span></span>

2. <span data-ttu-id="60c0b-167">En el Centro de administración de Microsoft 365, seleccione **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="60c0b-167">In the Microsoft 365 admin center, select **Users**.</span></span>

3. <span data-ttu-id="60c0b-168">Seleccione el empleado que desee bloquear y luego elija **Editar** junto a **Estado de inicio de sesión** en el panel de usuario.</span><span class="sxs-lookup"><span data-stu-id="60c0b-168">Select the employee that you want to block, and then choose **Edit** next to **Sign-in status** in the user pane.</span></span>

4. <span data-ttu-id="60c0b-169">En el panel **Estado de inicio de sesión**, elija **Inicio de sesión bloqueado** y luego **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="60c0b-169">On the **Sign-in status** pane, choose **Sign-in blocked** and then **Save**.</span></span>

5. <span data-ttu-id="60c0b-170">En el Centro de administración, en el panel de navegación de la parte inferior izquierda, expanda **Centros de administración** y seleccione **Exchange**.</span><span class="sxs-lookup"><span data-stu-id="60c0b-170">In the Admin center, in the lower-left navigation pane, expand **Admin Centers** and select **Exchange**.</span></span>

6. <span data-ttu-id="60c0b-171">En el Centro de administración de Exchange, navegue a **Destinatarios > Recursos**.</span><span class="sxs-lookup"><span data-stu-id="60c0b-171">In the Exchange admin center, navigate to **Recipients > Mailboxes**.</span></span>

7. <span data-ttu-id="60c0b-172">Seleccione el usuario y, en la página de propiedades de usuario, en **Dispositivos móviles**, haga clic en **Deshabilitar Exchange ActiveSync** y **Deshabilitar OWA para dispositivos** y responda **Sí** a ambos.</span><span class="sxs-lookup"><span data-stu-id="60c0b-172">Select the user, and on the user properties page, under **Mobile Devices**, click **Disable Exchange ActivcSync** and **Disable OWA for Devices** and answer **yes** to both.</span></span>

8. <span data-ttu-id="60c0b-173">En **Conectividad de correo**, haga clic en **Deshabilitar** y responda **Sí**.</span><span class="sxs-lookup"><span data-stu-id="60c0b-173">Under **Email Connectivity**, **Disable** and answer **yes**.</span></span>

### <a name="step-6-optional-remove-the-suspected-compromised-account-from-all-administrative-role-groups"></a><span data-ttu-id="60c0b-174">Paso 6 opcional: Quitar la cuenta en peligro de todos los grupos de roles administrativos</span><span class="sxs-lookup"><span data-stu-id="60c0b-174">Step 6 Optional: Remove the suspected compromised account from all administrative role groups</span></span>

> [!NOTE]
> <span data-ttu-id="60c0b-175">La pertenencia a grupos de roles administrativos puede restaurarse después de haber asegurado la cuenta.</span><span class="sxs-lookup"><span data-stu-id="60c0b-175">Administrative role group membership can be restored after the account has been secured.</span></span>

1. <span data-ttu-id="60c0b-176">Inicie sesión en el Centro de administración de Microsoft 365 con una cuenta de administrador global y abra **Usuarios activos**.</span><span class="sxs-lookup"><span data-stu-id="60c0b-176">Sign in to the Microsoft 365 admin center with a global administrator account and open **Active Users**.</span></span>

2. <span data-ttu-id="60c0b-177">Busque la cuenta en peligro y compruebe manualmente si hay roles administrativos asignados a la cuenta.</span><span class="sxs-lookup"><span data-stu-id="60c0b-177">Find the suspected compromised account and manually check to see if there are any administrative roles assigned to the account.</span></span>

3. <span data-ttu-id="60c0b-178">Abra el **Centro de seguridad y cumplimiento**.</span><span class="sxs-lookup"><span data-stu-id="60c0b-178">Open the **Security & Compliance Center**.</span></span>

4. <span data-ttu-id="60c0b-179">Haga clic en **Permisos**.</span><span class="sxs-lookup"><span data-stu-id="60c0b-179">Click **Permissions**.</span></span>

5. <span data-ttu-id="60c0b-180">Revise manualmente los grupos de roles para ver si la cuenta en peligro es miembro de cualquiera de ellos.</span><span class="sxs-lookup"><span data-stu-id="60c0b-180">Manually review the role groups to see if the suspected compromised account is a member of any of them.</span></span>  <span data-ttu-id="60c0b-181">Si lo es:</span><span class="sxs-lookup"><span data-stu-id="60c0b-181">If it is: a.</span></span>

   <span data-ttu-id="60c0b-182">a.</span><span class="sxs-lookup"><span data-stu-id="60c0b-182">a.</span></span> <span data-ttu-id="60c0b-183">Haga clic en el grupo de roles y **Editar grupo de roles**.</span><span class="sxs-lookup"><span data-stu-id="60c0b-183">Click the role group and click **Edit Role Group**.</span></span>

   <span data-ttu-id="60c0b-184">b.</span><span class="sxs-lookup"><span data-stu-id="60c0b-184">b.</span></span> <span data-ttu-id="60c0b-185">Haga clic en **Elegir miembros** y **Editar** para quitar el usuario del grupo de roles.</span><span class="sxs-lookup"><span data-stu-id="60c0b-185">Click **Chose Members** and **Edit** to remove the user from the role group.</span></span>

6. <span data-ttu-id="60c0b-186">Abra el **Centro de administración de Exchange**.</span><span class="sxs-lookup"><span data-stu-id="60c0b-186">Open the **Exchange admin center**</span></span>

7. <span data-ttu-id="60c0b-187">Haga clic en **Permisos**.</span><span class="sxs-lookup"><span data-stu-id="60c0b-187">Click **Permissions**.</span></span>

8. <span data-ttu-id="60c0b-188">Revise manualmente los grupos de roles para ver si la cuenta en peligro es miembro de cualquiera de ellos.</span><span class="sxs-lookup"><span data-stu-id="60c0b-188">Manually review the role groups to see if the suspected compromised account is a member of any of them.</span></span> <span data-ttu-id="60c0b-189">Si lo es:</span><span class="sxs-lookup"><span data-stu-id="60c0b-189">If it is: a.</span></span>

   <span data-ttu-id="60c0b-190">a.</span><span class="sxs-lookup"><span data-stu-id="60c0b-190">a.</span></span> <span data-ttu-id="60c0b-191">Haga clic en el grupo de roles y en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="60c0b-191">Click the role group and click **Edit**.</span></span>

   <span data-ttu-id="60c0b-192">b.</span><span class="sxs-lookup"><span data-stu-id="60c0b-192">b.</span></span> <span data-ttu-id="60c0b-193">Use la sección **miembros** para quitar el usuario del grupo de roles.</span><span class="sxs-lookup"><span data-stu-id="60c0b-193">Use the **members** section to remove the user from the role group.</span></span>

### <a name="step-7-optional-additional-precautionary-steps"></a><span data-ttu-id="60c0b-194">Paso 7 opcional: Pasos de precauciones adicionales</span><span class="sxs-lookup"><span data-stu-id="60c0b-194">Step 7 Optional: Additional precautionary steps</span></span>

1. <span data-ttu-id="60c0b-195">Asegúrese de comprobar los elementos enviados.</span><span class="sxs-lookup"><span data-stu-id="60c0b-195">Make sure that you verify your sent items.</span></span> <span data-ttu-id="60c0b-196">Puede que tenga que informar a los usuarios de la lista de contactos de que su cuenta está comprometida.</span><span class="sxs-lookup"><span data-stu-id="60c0b-196">You may have to inform people on your contacts list that your account was compromised.</span></span> <span data-ttu-id="60c0b-197">El atacante puede haberles pedido dinero fingiendo, por ejemplo, que estaba perdido en un país distinto y necesitaba dinero, o el atacante puede enviarles un virus para obtener acceso también a sus equipos.</span><span class="sxs-lookup"><span data-stu-id="60c0b-197">The attacker may have asked them for money, spoofing, for example, that you were stranded in a different country and needed money, or the attacker may send them a virus to also hijack their computers.</span></span>

2. <span data-ttu-id="60c0b-198">Cualquier otro servicio que use esta cuenta de Exchange como cuenta de correo electrónico alternativa puede haberse comprometido también.</span><span class="sxs-lookup"><span data-stu-id="60c0b-198">Any other service that used this Exchange account as its alternative email account may have been compromised.</span></span> <span data-ttu-id="60c0b-199">En primer lugar, siga estos pasos para la suscripción de Office 365 y, a continuación, siga estos pasos para otras cuentas.</span><span class="sxs-lookup"><span data-stu-id="60c0b-199">First, perform these steps for your Office 365 subscription, and then perform these steps for your other accounts.</span></span>

3. <span data-ttu-id="60c0b-200">Asegúrese de que la información de contacto, como los números de teléfono y direcciones, es correcta.</span><span class="sxs-lookup"><span data-stu-id="60c0b-200">Make sure that your contact information, such as telephone numbers and addresses, is correct.</span></span>

## <a name="secure-office-365-like-a-cybersecurity-pro"></a><span data-ttu-id="60c0b-201">Proteger Office 365 como un profesional de ciberseguridad</span><span class="sxs-lookup"><span data-stu-id="60c0b-201">Secure Office 365 like a cybersecurity pro</span></span>

<span data-ttu-id="60c0b-202">Su suscripción a Office 365 incluye un potente conjunto de capacidades de seguridad que puede usar para proteger sus datos y los usuarios.</span><span class="sxs-lookup"><span data-stu-id="60c0b-202">Your Office 365 subscription comes with a powerful set of security capabilities that you can use to protect your data and your users.</span></span>  <span data-ttu-id="60c0b-203">Use el [Plan de seguridad de Office 365: principales prioridades para los primeros 30 días, 90 días y en adelante](security-roadmap.md) para implementar las prácticas recomendadas de Microsoft para proteger su espacio empresarial de Office 365.</span><span class="sxs-lookup"><span data-stu-id="60c0b-203">Use the [Office 365 security roadmap: Top priorities for the first 30 days, 90 days, and beyond](security-roadmap.md) to implement Microsoft recommended best practices for securing your Office 365 tenant.</span></span>

- <span data-ttu-id="60c0b-204">Tareas a realizar en los primeros 30 días.</span><span class="sxs-lookup"><span data-stu-id="60c0b-204">Tasks to accomplish in the first 30 days.</span></span>  <span data-ttu-id="60c0b-205">Estas tienen un efecto inmediato y de bajo impacto para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="60c0b-205">These have immediate affect and are low-impact to your users.</span></span>

- <span data-ttu-id="60c0b-206">Tareas para llevar a cabo en 90 días.</span><span class="sxs-lookup"><span data-stu-id="60c0b-206">Tasks to accomplish in 90 days.</span></span> <span data-ttu-id="60c0b-207">Estas tareas necesitan un poco más de tiempo para planearlas e implementarlas, pero mejoran considerablemente el nivel de seguridad.</span><span class="sxs-lookup"><span data-stu-id="60c0b-207">These take a bit more time to plan and implement but greatly improve your security posture.</span></span>

- <span data-ttu-id="60c0b-208">Más de 90 días.</span><span class="sxs-lookup"><span data-stu-id="60c0b-208">Beyond 90 days.</span></span> <span data-ttu-id="60c0b-209">Estas mejoras se crean en el trabajo de los 90 primeros días.</span><span class="sxs-lookup"><span data-stu-id="60c0b-209">These enhancements build in your first 90 days work.</span></span>

## <a name="see-also"></a><span data-ttu-id="60c0b-210">Vea también</span><span class="sxs-lookup"><span data-stu-id="60c0b-210">See also</span></span>

- [<span data-ttu-id="60c0b-211">Detectar y corregir las reglas de Outlook y ataques de inserciones de formularios personalizados en Office 365</span><span class="sxs-lookup"><span data-stu-id="60c0b-211">Detect and Remediate Outlook Rules and Custom Forms Injections Attacks in Office 365</span></span>](/security/office-365-security/detect-and-remediate-outlook-rules-forms-attack.md)

- [<span data-ttu-id="60c0b-212">Centro de Quejas de Crímenes por Internet</span><span class="sxs-lookup"><span data-stu-id="60c0b-212">Internet Crime Complaint Center</span></span>](https://www.ic3.gov/preventiontips.aspx)

- [<span data-ttu-id="60c0b-213">Bolsas de valores de EE. UU.: Fraude de suplantación de identidad</span><span class="sxs-lookup"><span data-stu-id="60c0b-213">Securities and Exchange Commission - "Phishing" Fraud</span></span>](https://www.sec.gov/investor/pubs/phishing.htm)

- <span data-ttu-id="60c0b-214">Para informar directamente a Microsoft y su administrador sobre el correo no deseado [Use el complemento Informar sobre el mensaje](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)</span><span class="sxs-lookup"><span data-stu-id="60c0b-214">To report spam email directly to Microsoft and your admin [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)</span></span>
