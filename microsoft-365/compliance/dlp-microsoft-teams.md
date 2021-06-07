---
title: Prevención de pérdida de datos y Microsoft Teams.
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Microsoft Teams chats y canales admiten directivas de prevención de pérdida de datos (DLP).
ms.openlocfilehash: 6467ae7fdfc9c8636bd306efde5cb89c100e5e6c
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782566"
---
# <a name="data-loss-prevention-and-microsoft-teams"></a><span data-ttu-id="03869-103">Prevención de pérdida de datos y Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="03869-103">Data loss prevention and Microsoft Teams</span></span>

<span data-ttu-id="03869-104">Si su organización tiene prevención de pérdida de datos (DLP), puede definir directivas que impidan que los usuarios compartan información confidencial en una sesión de chat o canal de Microsoft Teams datos.</span><span class="sxs-lookup"><span data-stu-id="03869-104">If your organization has data loss prevention (DLP), you can define policies that prevent people from sharing sensitive information in a Microsoft Teams channel or chat session.</span></span> <span data-ttu-id="03869-105">Estos son algunos ejemplos de cómo funciona esta protección:</span><span class="sxs-lookup"><span data-stu-id="03869-105">Here are some examples of how this protection works:</span></span>

- <span data-ttu-id="03869-106">**Ejemplo 1: Protección de información confidencial en mensajes**.</span><span class="sxs-lookup"><span data-stu-id="03869-106">**Example 1: Protecting sensitive information in messages**.</span></span> <span data-ttu-id="03869-107">Supongamos que alguien intenta compartir información confidencial en un Teams chat o canal con invitados (usuarios externos).</span><span class="sxs-lookup"><span data-stu-id="03869-107">Suppose that someone attempts to share sensitive information in a Teams chat or channel with guests (external users).</span></span> <span data-ttu-id="03869-108">Si tiene una directiva DLP definida para evitarlo, se eliminan los mensajes con información confidencial que se envían a usuarios externos.</span><span class="sxs-lookup"><span data-stu-id="03869-108">If you have a DLP policy defined to prevent this, messages with sensitive information that are sent to external users are deleted.</span></span> <span data-ttu-id="03869-109">Esto sucede automáticamente y en segundos, según cómo se configura la directiva DLP.</span><span class="sxs-lookup"><span data-stu-id="03869-109">This happens automatically, and within seconds, according to how your DLP policy is configured.</span></span>

    > [!NOTE]
    > <span data-ttu-id="03869-110">DLP para Microsoft Teams bloquea el contenido confidencial cuando se comparte con Microsoft Teams usuarios que tienen:</span><span class="sxs-lookup"><span data-stu-id="03869-110">DLP for Microsoft Teams blocks sensitive content when shared with Microsoft Teams users who have:</span></span><br/><span data-ttu-id="03869-111">- [acceso de invitado](/MicrosoftTeams/guest-access) en equipos y canales; o</span><span class="sxs-lookup"><span data-stu-id="03869-111">- [guest access](/MicrosoftTeams/guest-access) in teams and channels; or</span></span><br/><span data-ttu-id="03869-112">- [acceso externo en](/MicrosoftTeams/manage-external-access) reuniones y sesiones de chat.</span><span class="sxs-lookup"><span data-stu-id="03869-112">- [external access](/MicrosoftTeams/manage-external-access) in meetings and chat sessions.</span></span> <p><span data-ttu-id="03869-113">DLP para sesiones de chat externas solo funcionará si el remitente y el receptor están en modo de solo Teams y usando Microsoft Teams [federación nativa](/microsoftteams/manage-external-access).</span><span class="sxs-lookup"><span data-stu-id="03869-113">DLP for external chat sessions will only work if both the sender and the receiver are in Teams Only mode and using [Microsoft Teams native federation](/microsoftteams/manage-external-access).</span></span> <span data-ttu-id="03869-114">DLP para Teams no bloquea los [](/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability#interoperability-of-teams-and-skype-for-business) mensajes en interoperabilidad con Skype Empresarial o sesiones de chat federadas no nativas.</span><span class="sxs-lookup"><span data-stu-id="03869-114">DLP for Teams does not block messages in [interop](/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability#interoperability-of-teams-and-skype-for-business) with Skype for Business or non-native federated chat sessions.</span></span>

- <span data-ttu-id="03869-115">**Ejemplo 2: Protección de información confidencial en documentos**.</span><span class="sxs-lookup"><span data-stu-id="03869-115">**Example 2: Protecting sensitive information in documents**.</span></span> <span data-ttu-id="03869-116">Supongamos que alguien intenta compartir un documento con invitados en un canal Microsoft Teams chat y que el documento contiene información confidencial.</span><span class="sxs-lookup"><span data-stu-id="03869-116">Suppose that someone attempts to share a document with guests in a Microsoft Teams channel or chat, and the document contains sensitive information.</span></span> <span data-ttu-id="03869-117">Si tiene una directiva DLP definida para evitarlo, el documento no se abrirá para esos usuarios.</span><span class="sxs-lookup"><span data-stu-id="03869-117">If you have a DLP policy defined to prevent this, the document won't open for those users.</span></span> <span data-ttu-id="03869-118">La directiva DLP debe incluir SharePoint y OneDrive para poder establecer la protección.</span><span class="sxs-lookup"><span data-stu-id="03869-118">Your DLP policy must include SharePoint and OneDrive in order for protection to be in place.</span></span> <span data-ttu-id="03869-119">Este es un ejemplo de DLP para SharePoint que se muestra en Microsoft Teams y, por lo tanto, requiere que los usuarios tienen licencia para dlp Office 365 (incluido en Office 365 E3), pero no requiere que los usuarios puedan obtener una licencia para Cumplimiento avanzado de Office 365).</span><span class="sxs-lookup"><span data-stu-id="03869-119">This is an example of DLP for SharePoint that shows up in Microsoft Teams, and therefore requires that users are licensed for Office 365 DLP (included in Office 365 E3), but does not require users to be licensed for Office 365 Advanced Compliance.)</span></span>

## <a name="dlp-licensing-for-microsoft-teams"></a><span data-ttu-id="03869-120">Licencias DLP para Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="03869-120">DLP Licensing for Microsoft Teams</span></span>

<span data-ttu-id="03869-121">[Las capacidades de prevención](dlp-learn-about-dlp.md) de pérdida de datos se ampliaron para incluir Microsoft Teams chat y mensajes de canal, **incluidos** los mensajes de canal privado para:</span><span class="sxs-lookup"><span data-stu-id="03869-121">[Data loss prevention](dlp-learn-about-dlp.md) capabilities were extended to include Microsoft Teams chat and channel messages, **including private channel messages** for:</span></span>

- <span data-ttu-id="03869-122">Office 365 E5/A5</span><span class="sxs-lookup"><span data-stu-id="03869-122">Office 365 E5/A5</span></span>
- <span data-ttu-id="03869-123">Microsoft 365 E5/A5</span><span class="sxs-lookup"><span data-stu-id="03869-123">Microsoft 365 E5/A5</span></span>
- <span data-ttu-id="03869-124">Gobierno y protección de información de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="03869-124">Microsoft 365 Information Protection and Governance</span></span>
- <span data-ttu-id="03869-125">Cumplimiento avanzado de Office 365</span><span class="sxs-lookup"><span data-stu-id="03869-125">Office 365 Advanced Compliance</span></span>

<span data-ttu-id="03869-126">Office 365 y Microsoft 365 E3 protección DLP para SharePoint Online, OneDrive y Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="03869-126">Office 365 and Microsoft 365 E3 include DLP protection for SharePoint Online, OneDrive, and Exchange Online.</span></span> <span data-ttu-id="03869-127">Esto también incluye archivos que se comparten a través de Teams porque Teams usa SharePoint Online y OneDrive para compartir archivos.</span><span class="sxs-lookup"><span data-stu-id="03869-127">This also includes files that are shared through Teams because Teams uses SharePoint Online and OneDrive to share files.</span></span>

<span data-ttu-id="03869-128">La compatibilidad con la protección DLP en Teams chat requiere E5.</span><span class="sxs-lookup"><span data-stu-id="03869-128">Support for DLP protection in Teams Chat requires E5.</span></span>

<span data-ttu-id="03869-129">Para obtener más información sobre los requisitos de licencias, consulte [Instrucciones de licencias de Microsoft 365 del nivel de espacio empresarial](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span><span class="sxs-lookup"><span data-stu-id="03869-129">To learn more about licensing requirements, see [Microsoft 365 Tenant-Level Services Licensing Guidance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="03869-130">DLP solo se aplica a los mensajes reales en el subproceso de chat o canal.</span><span class="sxs-lookup"><span data-stu-id="03869-130">DLP applies only to the actual messages in the chat or channel thread.</span></span> <span data-ttu-id="03869-131">Las notificaciones de actividad , que incluyen una vista previa de  mensaje breve y aparecen según la configuración de notificación de un usuario, no se incluyen en Teams DLP.</span><span class="sxs-lookup"><span data-stu-id="03869-131">Activity notifications -- which include a short message preview and appear based on a user's notification settings -- are **not** included in Teams DLP.</span></span> <span data-ttu-id="03869-132">Cualquier información confidencial presente en la parte del mensaje que aparece en la vista previa permanecerá visible en la notificación incluso después de que se haya aplicado la directiva DLP y se haya quitado la información confidencial del mensaje en sí.</span><span class="sxs-lookup"><span data-stu-id="03869-132">Any sensitive information present in the part of the message that appears in the preview will remain visible in the notification even after the DLP policy has been applied and removed sensitive information the message itself.</span></span>

## <a name="scope-of-dlp-protection"></a><span data-ttu-id="03869-133">Ámbito de la protección DLP</span><span class="sxs-lookup"><span data-stu-id="03869-133">Scope of DLP protection</span></span>

<span data-ttu-id="03869-134">La protección DLP se aplica de forma diferente a Teams entidades.</span><span class="sxs-lookup"><span data-stu-id="03869-134">DLP protection are applied differently to Teams entities.</span></span>

|<span data-ttu-id="03869-135">Cuentas de usuario/Grupos/Lista</span><span class="sxs-lookup"><span data-stu-id="03869-135">User Accounts/Groups/List</span></span>  |<span data-ttu-id="03869-136">Teams Entidad</span><span class="sxs-lookup"><span data-stu-id="03869-136">Teams Entity</span></span> |<span data-ttu-id="03869-137">Protección DLP disponible</span><span class="sxs-lookup"><span data-stu-id="03869-137">DLP protection available</span></span>|
|---------|---------|---------|
|<span data-ttu-id="03869-138">cuentas de usuario individuales</span><span class="sxs-lookup"><span data-stu-id="03869-138">individual user accounts</span></span>     |<span data-ttu-id="03869-139">Chats de 1:1/n</span><span class="sxs-lookup"><span data-stu-id="03869-139">1:1/n chats</span></span>         |<span data-ttu-id="03869-140">sí</span><span class="sxs-lookup"><span data-stu-id="03869-140">yes</span></span>         |
|     |<span data-ttu-id="03869-141">chats generales</span><span class="sxs-lookup"><span data-stu-id="03869-141">general chats</span></span>         |<span data-ttu-id="03869-142">no</span><span class="sxs-lookup"><span data-stu-id="03869-142">no</span></span>         |
|     |<span data-ttu-id="03869-143">canales privados</span><span class="sxs-lookup"><span data-stu-id="03869-143">private channels</span></span>         |<span data-ttu-id="03869-144">sí</span><span class="sxs-lookup"><span data-stu-id="03869-144">yes</span></span>         |
|<span data-ttu-id="03869-145">grupos de seguridad/listas de distribución</span><span class="sxs-lookup"><span data-stu-id="03869-145">security groups/distribution lists</span></span>  | <span data-ttu-id="03869-146">Chats de 1:1/n</span><span class="sxs-lookup"><span data-stu-id="03869-146">1:1/n chats</span></span>         |<span data-ttu-id="03869-147">sí</span><span class="sxs-lookup"><span data-stu-id="03869-147">yes</span></span>         |
|     |<span data-ttu-id="03869-148">chats generales</span><span class="sxs-lookup"><span data-stu-id="03869-148">general chats</span></span>         |<span data-ttu-id="03869-149">no</span><span class="sxs-lookup"><span data-stu-id="03869-149">no</span></span>         |
|     |<span data-ttu-id="03869-150">canales privados</span><span class="sxs-lookup"><span data-stu-id="03869-150">private channels</span></span>         |<span data-ttu-id="03869-151">sí</span><span class="sxs-lookup"><span data-stu-id="03869-151">yes</span></span>        |
|<span data-ttu-id="03869-152">Microsoft 365 grupo</span><span class="sxs-lookup"><span data-stu-id="03869-152">Microsoft 365 group</span></span>    |<span data-ttu-id="03869-153">Chats de 1:1/n</span><span class="sxs-lookup"><span data-stu-id="03869-153">1:1/n chats</span></span>          |<span data-ttu-id="03869-154">no</span><span class="sxs-lookup"><span data-stu-id="03869-154">no</span></span>         |
|     |<span data-ttu-id="03869-155">chats generales</span><span class="sxs-lookup"><span data-stu-id="03869-155">general chats</span></span>          |<span data-ttu-id="03869-156">sí</span><span class="sxs-lookup"><span data-stu-id="03869-156">yes</span></span>        |
|     |<span data-ttu-id="03869-157">canales privados</span><span class="sxs-lookup"><span data-stu-id="03869-157">private channels</span></span>|<span data-ttu-id="03869-158">no</span><span class="sxs-lookup"><span data-stu-id="03869-158">no</span></span>| 


## <a name="policy-tips-help-educate-users"></a><span data-ttu-id="03869-159">Las sugerencias de directiva ayudan a educar a los usuarios</span><span class="sxs-lookup"><span data-stu-id="03869-159">Policy tips help educate users</span></span>

<span data-ttu-id="03869-160">De forma similar a cómo funciona DLP en [Exchange, Outlook, Outlook](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web)en la web , [SharePoint Online,](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites)sitios de OneDrive para la Empresa y clientes de escritorio de [Office,](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs)aparecen sugerencias de directiva cuando se desencadena una acción con una directiva DLP.</span><span class="sxs-lookup"><span data-stu-id="03869-160">Similar to how DLP works in [Exchange, Outlook, Outlook on the web](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web), [SharePoint Online, OneDrive for Business sites](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites), and [Office desktop clients](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs), policy tips appear when an action triggers with a DLP policy.</span></span> <span data-ttu-id="03869-161">Este es un ejemplo de una sugerencia de directiva:</span><span class="sxs-lookup"><span data-stu-id="03869-161">Here's an example of a policy tip:</span></span>

![Notificación de mensaje bloqueado en Teams](../media/dlp-teams-blockedmessage-notification.png)

<span data-ttu-id="03869-163">Aquí, el remitente intentó compartir un número de seguridad social en un canal Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="03869-163">Here, the sender attempted to share a social security number in a Microsoft Teams channel.</span></span> <span data-ttu-id="03869-164">El **vínculo ¿Qué puedo hacer?** abre un cuadro de diálogo que proporciona opciones para que el remitente resuelva el problema.</span><span class="sxs-lookup"><span data-stu-id="03869-164">The **What can I do?** link opens a dialog box that provides options for the sender to resolve the issue.</span></span> <span data-ttu-id="03869-165">Tenga en cuenta que, el remitente puede optar por invalidar la directiva o notificar a un administrador que la revise y resuelva.</span><span class="sxs-lookup"><span data-stu-id="03869-165">Notice that, the sender can opt to override the policy, or notify an admin to review and resolve it.</span></span>

![Opciones para resolver el mensaje bloqueado](../media/dlp-teams-blockedmessage-possibleactions.png)

<span data-ttu-id="03869-167">En su organización, puede elegir permitir que los usuarios invalide una directiva DLP.</span><span class="sxs-lookup"><span data-stu-id="03869-167">In your organization, you can choose to allow users to override a DLP policy.</span></span> <span data-ttu-id="03869-168">Al configurar las directivas DLP, puede usar las sugerencias de directiva predeterminadas o personalizar [las sugerencias de directiva](#to-customize-policy-tips) para su organización.</span><span class="sxs-lookup"><span data-stu-id="03869-168">When you configure your DLP policies, you can use the default policy tips, or [customize policy tips](#to-customize-policy-tips) for your organization.</span></span>

<span data-ttu-id="03869-169">Volviendo a nuestro ejemplo, donde un remitente compartió un número de seguridad social en un canal de Teams, esto es lo que vio el destinatario:</span><span class="sxs-lookup"><span data-stu-id="03869-169">Returning to our example, where a sender shared a social security number in a Teams channel, here's what the recipient saw:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="03869-170">![Mensaje bloqueado](../media/dlp-teams-blockedmessage-notification-to-user.png)</span><span class="sxs-lookup"><span data-stu-id="03869-170">![Message blocked](../media/dlp-teams-blockedmessage-notification-to-user.png)</span></span>

### <a name="to-customize-policy-tips"></a><span data-ttu-id="03869-171">Personalizar sugerencias de directiva</span><span class="sxs-lookup"><span data-stu-id="03869-171">To customize policy tips</span></span>

<span data-ttu-id="03869-172">Para llevar a cabo esta tarea, debe tener asignado un rol de administración que tenga permisos para editar directivas DLP.</span><span class="sxs-lookup"><span data-stu-id="03869-172">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="03869-173">Para obtener más información vea [Permisos](data-loss-prevention-policies.md#permissions).</span><span class="sxs-lookup"><span data-stu-id="03869-173">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="03869-174">Vaya al Centro de cumplimiento ( [https://compliance.microsoft.com](https://compliance.microsoft.com) ) e inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="03869-174">Go to the Compliance Center ([https://compliance.microsoft.com](https://compliance.microsoft.com)) and sign in.</span></span>

2. <span data-ttu-id="03869-175">Haga clic en **Prevención de pérdida de datos** > **Directiva**.</span><span class="sxs-lookup"><span data-stu-id="03869-175">Choose **Data loss prevention** > **Policy**.</span></span>

3. <span data-ttu-id="03869-176">Seleccione una directiva y, junto a **Configuración de directiva,** elija **Editar**.</span><span class="sxs-lookup"><span data-stu-id="03869-176">Select a policy, and next to **Policy settings**, choose **Edit**.</span></span>

4. <span data-ttu-id="03869-177">Cree una nueva regla o edite una regla existente para la directiva.</span><span class="sxs-lookup"><span data-stu-id="03869-177">Either create a new rule, or edit an existing rule for the policy.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="03869-178">![Edición de una regla para una directiva](../media/dlp-teams-editrule.png)</span><span class="sxs-lookup"><span data-stu-id="03869-178">![Editing a rule for a policy](../media/dlp-teams-editrule.png)</span></span>

5. <span data-ttu-id="03869-179">En la **pestaña Notificaciones de usuario,** seleccione **Personalizar el** texto del correo electrónico o Personalizar las opciones de texto de **sugerencia de** directiva.</span><span class="sxs-lookup"><span data-stu-id="03869-179">On the **User notifications** tab, select **Customize the email text** and/or **Customize the policy tip text** options.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="03869-180">![Personalizar notificaciones de usuario y sugerencias de directivas](../media/dlp-teams-editrule-usernotifications.png)</span><span class="sxs-lookup"><span data-stu-id="03869-180">![Customize user notifications and policy tips](../media/dlp-teams-editrule-usernotifications.png)</span></span><br/>  

6. <span data-ttu-id="03869-181">Especifique el texto que desea usar para notificaciones por correo electrónico o sugerencias de directiva y, a continuación, **elija Guardar**.</span><span class="sxs-lookup"><span data-stu-id="03869-181">Specify the text you want to use for email notifications and/or policy tips, and then choose **Save**.</span></span>

7. <span data-ttu-id="03869-182">En la **pestaña Configuración de** directiva, elija **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="03869-182">On the **Policy settings** tab, choose **Save**.</span></span>

<span data-ttu-id="03869-183">Espere aproximadamente una hora para que los cambios funcionen en su centro de datos y se sincronicen con cuentas de usuario.</span><span class="sxs-lookup"><span data-stu-id="03869-183">Allow approximately one hour for your changes to work their way through your data center and sync to user accounts.</span></span>
 <!-- why are these syncing to user accounts? -->

## <a name="add-microsoft-teams-as-a-location-to-existing-dlp-policies"></a><span data-ttu-id="03869-184">Agregar Microsoft Teams como una ubicación a las directivas DLP existentes</span><span class="sxs-lookup"><span data-stu-id="03869-184">Add Microsoft Teams as a location to existing DLP policies</span></span>

<span data-ttu-id="03869-185">Para llevar a cabo esta tarea, debe tener asignado un rol de administración que tenga permisos para editar directivas DLP.</span><span class="sxs-lookup"><span data-stu-id="03869-185">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="03869-186">Para obtener más información vea [Permisos](data-loss-prevention-policies.md#permissions).</span><span class="sxs-lookup"><span data-stu-id="03869-186">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="03869-187">Vaya al Centro de cumplimiento ( [https://compliance.microsoft.com](https://compliance.microsoft.com) ) e inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="03869-187">Go to the Compliance Center ([https://compliance.microsoft.com](https://compliance.microsoft.com)) and sign in.</span></span>

2. <span data-ttu-id="03869-188">Haga clic en **Prevención de pérdida de datos** > **Directiva**.</span><span class="sxs-lookup"><span data-stu-id="03869-188">Choose **Data loss prevention** > **Policy**.</span></span>

3. <span data-ttu-id="03869-189">Seleccione una directiva y vea los valores en **Ubicaciones**.</span><span class="sxs-lookup"><span data-stu-id="03869-189">Select a policy, and look at the values under **Locations**.</span></span> <span data-ttu-id="03869-190">Si ves **Teams chat y mensajes de canal,** estás todo configurado.</span><span class="sxs-lookup"><span data-stu-id="03869-190">If you see **Teams chat and channel messages**, you're all set.</span></span> <span data-ttu-id="03869-191">Si no lo hace, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="03869-191">If you don't, click **Edit**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="03869-192">![Ubicaciones de la directiva existente](../media/dlp-teams-editexistingpolicy.png)</span><span class="sxs-lookup"><span data-stu-id="03869-192">![Locations for existing policy](../media/dlp-teams-editexistingpolicy.png)</span></span>

4. <span data-ttu-id="03869-193">En la **columna Estado,** active la directiva para los **mensajes Teams chat y canal**.</span><span class="sxs-lookup"><span data-stu-id="03869-193">In the **Status** column, turn the policy on for **Teams chat and channel messages**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="03869-194">![DLP para Teams chats y canales](../media/dlp-teams-addteamschatschannels.png)</span><span class="sxs-lookup"><span data-stu-id="03869-194">![DLP for Teams chats and channels](../media/dlp-teams-addteamschatschannels.png)</span></span>

5. <span data-ttu-id="03869-195">En la **pestaña Elegir ubicaciones,** mantenga la configuración predeterminada de todas las cuentas o seleccione **Permitirme elegir ubicaciones específicas.**</span><span class="sxs-lookup"><span data-stu-id="03869-195">On the **Choose locations** tab, keep the default setting of all accounts, or select **Let me choose specific locations**.</span></span> <span data-ttu-id="03869-196">Puede especificar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="03869-196">You can specify:</span></span>

    1. <span data-ttu-id="03869-197">hasta 1000 cuentas individuales para incluir o excluir</span><span class="sxs-lookup"><span data-stu-id="03869-197">up to 1000 individual accounts to include or exclude</span></span>
    1. <span data-ttu-id="03869-198">listas de distribución y grupos de seguridad para incluir o excluir.</span><span class="sxs-lookup"><span data-stu-id="03869-198">distribution lists and security groups to include or exclude.</span></span> 
    <!-- 1. the shared mailbox of a shared channel. **This is a public preview feature.**--> 
    
6. <span data-ttu-id="03869-199">A continuación, elija **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="03869-199">Then choose **Next**.</span></span>

7. <span data-ttu-id="03869-200">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="03869-200">Click **Save**.</span></span>

<span data-ttu-id="03869-201">Espere aproximadamente una hora para que los cambios funcionen en su centro de datos y se sincronicen con cuentas de usuario.</span><span class="sxs-lookup"><span data-stu-id="03869-201">Allow approximately one hour for your changes to work their way through your data center and sync to user accounts.</span></span>
<!-- again, why user accounts? -->

## <a name="define-a-new-dlp-policy-for-microsoft-teams"></a><span data-ttu-id="03869-202">Crear una directiva DLP con Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="03869-202">Define a new DLP policy for Microsoft Teams</span></span>

<span data-ttu-id="03869-203">Para llevar a cabo esta tarea, debe tener asignado un rol de administración que tenga permisos para editar directivas DLP.</span><span class="sxs-lookup"><span data-stu-id="03869-203">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="03869-204">Para obtener más información vea [Permisos](data-loss-prevention-policies.md#permissions).</span><span class="sxs-lookup"><span data-stu-id="03869-204">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="03869-205">Vaya al Centro de cumplimiento ( [https://compliance.microsoft.com](https://compliance.microsoft.com) ) e inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="03869-205">Go to the Compliance Center ([https://compliance.microsoft.com](https://compliance.microsoft.com)) and sign in.</span></span>

2. <span data-ttu-id="03869-206">Elija **Prevención de pérdida de datos** > **Directiva** > **+ Crear una directiva**.</span><span class="sxs-lookup"><span data-stu-id="03869-206">Choose **Data loss prevention** > **Policy** > **+ Create a policy**.</span></span>

3. <span data-ttu-id="03869-207">Elija una [plantilla](data-loss-prevention-policies.md#dlp-policy-templates)y, a continuación, **elija Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="03869-207">Choose a [template](data-loss-prevention-policies.md#dlp-policy-templates), and then choose **Next**.</span></span>

    <span data-ttu-id="03869-208">En nuestro ejemplo, elegimos la plantilla Datos de información de identificación personal de Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="03869-208">In our example, we chose the U.S. Personally Identifiable Information Data template.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="03869-209">![Plantilla de privacidad para la directiva DLP](../media/dlp-teams-createnewpolicy-template.png)</span><span class="sxs-lookup"><span data-stu-id="03869-209">![Privacy template for DLP policy](../media/dlp-teams-createnewpolicy-template.png)</span></span><br/>

4. <span data-ttu-id="03869-210">En la **pestaña Nombre de la directiva,** especifique un nombre y una descripción para la directiva y, a continuación, elija **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="03869-210">On the **Name your policy** tab, specify a name and description for the policy, and then choose **Next**.</span></span>

5. <span data-ttu-id="03869-211">En la **pestaña Elegir ubicaciones,** mantenga la configuración predeterminada de todas las cuentas o seleccione **Permitirme elegir ubicaciones específicas.**</span><span class="sxs-lookup"><span data-stu-id="03869-211">On the **Choose locations** tab, keep the default setting of all accounts, or select **Let me choose specific locations**.</span></span> <span data-ttu-id="03869-212">Puede especificar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="03869-212">You can specify:</span></span>

    1. <span data-ttu-id="03869-213">hasta 1000 cuentas individuales para incluir o excluir</span><span class="sxs-lookup"><span data-stu-id="03869-213">up to 1000 individual accounts to include or exclude</span></span>
    1. <span data-ttu-id="03869-214">listas de distribución y grupos de seguridad para incluir o excluir.</span><span class="sxs-lookup"><span data-stu-id="03869-214">distribution lists and security groups to include or exclude.</span></span> <span data-ttu-id="03869-215">**Se trata de una característica de vista previa pública.**</span><span class="sxs-lookup"><span data-stu-id="03869-215">**This is a public preview feature.**</span></span>
    <!-- 1. the shared mailbox of a shared channel. **This is a public preview feature.**-->  

    ![Ubicaciones de directivas DLP](../media/dlp-teams-selectlocationsnewpolicy.png)

    > [!NOTE]
    > <span data-ttu-id="03869-217">Si desea asegurarse de que los documentos que contienen información confidencial no  se compartan de forma inadecuada en Teams, asegúrese de que SharePoint sitios y cuentas **de OneDrive** estén activados, junto con los mensajes de **chat** y canal Teams .</span><span class="sxs-lookup"><span data-stu-id="03869-217">If you want to make sure documents that contain sensitive information are not shared inappropriately in Teams, make sure **SharePoint sites** and **OneDrive accounts** are turned on, along with **Teams chat and channel messages**.</span></span>

6. <span data-ttu-id="03869-218">En la **pestaña Configuración de** directiva, en Personalizar el tipo de contenido que desea proteger, mantenga la configuración sencilla predeterminada o elija Usar configuración avanzada y, a continuación, elija **Siguiente**.  </span><span class="sxs-lookup"><span data-stu-id="03869-218">On the **Policy settings** tab, under **Customize the type of content you want to protect**, keep the default simple settings, or choose **Use advanced settings**, and then choose **Next**.</span></span> <span data-ttu-id="03869-219">Si elige la configuración avanzada, puede crear o editar reglas para la directiva.</span><span class="sxs-lookup"><span data-stu-id="03869-219">If you choose advanced settings, you can create or edit rules for your policy.</span></span> <span data-ttu-id="03869-220">Para obtener ayuda con esto, vea [Configuración sencilla frente a configuración avanzada](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings).</span><span class="sxs-lookup"><span data-stu-id="03869-220">To get help with this, see [Simple settings vs. advanced settings](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings).</span></span>

7.  <span data-ttu-id="03869-221">En la **pestaña Configuración de** directiva, en ¿Qué desea hacer si detectamos información **confidencial?**, revise la configuración.</span><span class="sxs-lookup"><span data-stu-id="03869-221">On the **Policy settings** tab, under **What do you want to do if we detect sensitive info?**, review the settings.</span></span> <span data-ttu-id="03869-222">Aquí es donde puede elegir mantener las sugerencias de directiva [predeterminadas](use-notifications-and-policy-tips.md)y las notificaciones de correo electrónico, o personalizarlas.</span><span class="sxs-lookup"><span data-stu-id="03869-222">Here's where you can choose to keep default [policy tips and email notifications](use-notifications-and-policy-tips.md), or customize them.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="03869-223">![Configuración de directiva DLP con sugerencias y notificaciones](../media/dlp-teams-policysettings-tipsemails.png)</span><span class="sxs-lookup"><span data-stu-id="03869-223">![DLP policy settings with tips and notifications](../media/dlp-teams-policysettings-tipsemails.png)</span></span>

    <span data-ttu-id="03869-224">Cuando haya terminado de revisar o editar la configuración, elija **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="03869-224">When you're finished reviewing or editing settings, choose **Next**.</span></span>

8. <span data-ttu-id="03869-225">En la **pestaña** Configuración de directiva, en ¿Desea activar la directiva o probar primero **las cosas?**, elija si desea activar la [directiva,](dlp-overview-plan-for-dlp.md#policy-deployment)probarla primero o mantenerla desactivada por ahora y, a continuación, elija **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="03869-225">On the **Policy settings** tab, under **Do you want to turn on the policy or test things out first?**, choose whether to turn the policy on, [test it first](dlp-overview-plan-for-dlp.md#policy-deployment), or keep it turned off for now, and then choose **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="03869-226">![Especificar si se debe activar la directiva](../media/dlp-teams-policysettings-turnonnow.png)</span><span class="sxs-lookup"><span data-stu-id="03869-226">![Specify whether to turn the policy on](../media/dlp-teams-policysettings-turnonnow.png)</span></span>

9. <span data-ttu-id="03869-227">En la **pestaña Revisar la configuración,** revisa la configuración de la nueva directiva.</span><span class="sxs-lookup"><span data-stu-id="03869-227">On the **Review your settings** tab, review the settings for your new policy.</span></span> <span data-ttu-id="03869-228">Elija **Editar** para realizar cambios.</span><span class="sxs-lookup"><span data-stu-id="03869-228">Choose **Edit** to make changes.</span></span> <span data-ttu-id="03869-229">Cuando haya terminado, elija **Crear**.</span><span class="sxs-lookup"><span data-stu-id="03869-229">When you're finished, choose **Create**.</span></span>

<span data-ttu-id="03869-230">Espere aproximadamente una hora para que la nueva directiva funcione en su centro de datos y se sincronice con cuentas de usuario.</span><span class="sxs-lookup"><span data-stu-id="03869-230">Allow approximately one hour for your new policy to work its way through your data center and sync to user accounts.</span></span>

## <a name="prevent-external-access-to-sensitive-documents"></a><span data-ttu-id="03869-231">Evitar el acceso externo a documentos confidenciales</span><span class="sxs-lookup"><span data-stu-id="03869-231">Prevent external access to sensitive documents</span></span>

<span data-ttu-id="03869-232">Para asegurarse de que SharePoint documentos que contienen información confidencial no puedan tener acceso los invitados externos desde SharePoint o Teams de forma predeterminada, seleccione lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="03869-232">To ensure that SharePoint documents that contain sensitive information cannot be accessed by external guests either from SharePoint or Teams by default, select the following:</span></span>

- <span data-ttu-id="03869-233">Puede asegurarse de que los documentos están protegidos hasta que DLP los examina y los marca como seguros para compartir marcando los nuevos archivos [como confidenciales de forma predeterminada.](/sharepoint/sensitive-by-default)</span><span class="sxs-lookup"><span data-stu-id="03869-233">You can ensure that documents are protected until DLP scans and marks them as safe to share by [marking new files as sensitive by default](/sharepoint/sensitive-by-default).</span></span>

- <span data-ttu-id="03869-234">Estructura recomendada de directiva DLP</span><span class="sxs-lookup"><span data-stu-id="03869-234">Recommended DLP policy structure</span></span>

    - <span data-ttu-id="03869-235">**Condiciones**</span><span class="sxs-lookup"><span data-stu-id="03869-235">**Conditions**</span></span>
        - <span data-ttu-id="03869-236">El contenido contiene cualquiera de estos tipos de información confidencial: [Seleccionar todo lo que se aplica]</span><span class="sxs-lookup"><span data-stu-id="03869-236">Content contains any of these sensitive information types: [Select all that apply]</span></span>
        
        - <span data-ttu-id="03869-237">El contenido se comparte Microsoft 365 con personas de fuera de mi organización</span><span class="sxs-lookup"><span data-stu-id="03869-237">Content is shared from Microsoft 365 with people outside my organization</span></span>
        
          > [!div class="mx-imgBorder"]
          > <span data-ttu-id="03869-238">![Condiciones dlp para detectar el uso compartido externo de contenido confidencial](../media/dlp-teams-external-sharing/external-condition.png)</span><span class="sxs-lookup"><span data-stu-id="03869-238">![DLP conditions to detect external sharing of sensitive content](../media/dlp-teams-external-sharing/external-condition.png)</span></span>

    - <span data-ttu-id="03869-239">**Actions**</span><span class="sxs-lookup"><span data-stu-id="03869-239">**Actions**</span></span>
        - <span data-ttu-id="03869-240">Restringir el acceso de usuarios externos al contenido</span><span class="sxs-lookup"><span data-stu-id="03869-240">Restrict access to the content for external users</span></span>
        
        - <span data-ttu-id="03869-241">Notificar a los usuarios con sugerencias de directiva y correo electrónico</span><span class="sxs-lookup"><span data-stu-id="03869-241">Notify users with email and policy tips</span></span>
        
        - <span data-ttu-id="03869-242">Enviar informes de incidentes al administrador</span><span class="sxs-lookup"><span data-stu-id="03869-242">Send incident reports to the Administrator</span></span>
        
        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="03869-243">![Acción DLP para bloquear el uso compartido externo de contenido confidencial](../media/dlp-teams-external-sharing/external-action.png)</span><span class="sxs-lookup"><span data-stu-id="03869-243">![DLP action to block external sharing of sensitive content](../media/dlp-teams-external-sharing/external-action.png)</span></span>

<span data-ttu-id="03869-244">Directiva DLP en acción al intentar compartir un documento en SharePoint que contiene información confidencial con un invitado externo:</span><span class="sxs-lookup"><span data-stu-id="03869-244">DLP policy in action when attempting to share a document in SharePoint that contains sensitive information with an external guest:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="03869-245">![Uso compartido externo bloqueado](../media/dlp-teams-external-sharing/external-sharing-blocked.png)</span><span class="sxs-lookup"><span data-stu-id="03869-245">![External sharing blocked](../media/dlp-teams-external-sharing/external-sharing-blocked.png)</span></span>


<span data-ttu-id="03869-246">Directiva DLP en acción cuando el invitado intenta abrir un documento en Teams con bloqueo externo:</span><span class="sxs-lookup"><span data-stu-id="03869-246">DLP policy in action when guest attempts to open a document in Teams with block external:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="03869-247">![Acceso externo bloqueado](../media/dlp-teams-external-sharing/external-access-blocked.png)</span><span class="sxs-lookup"><span data-stu-id="03869-247">![External access blocked](../media/dlp-teams-external-sharing/external-access-blocked.png)</span></span>

## <a name="related-articles"></a><span data-ttu-id="03869-248">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="03869-248">Related articles</span></span>

- [<span data-ttu-id="03869-249">Crear, probar y optimizar una directiva DLP</span><span class="sxs-lookup"><span data-stu-id="03869-249">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="03869-250">Enviar notificaciones de email y mostrar sugerencias para directivas DLP</span><span class="sxs-lookup"><span data-stu-id="03869-250">Send email notifications and show policy tips for DLP policies</span></span>](use-notifications-and-policy-tips.md)
