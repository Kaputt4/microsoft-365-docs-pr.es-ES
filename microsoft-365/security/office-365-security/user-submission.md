---
title: Especificar un buzón para envíos de usuarios de mensajes de correo no deseado y suplantación de identidad
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Los administradores pueden aprender a configurar un buzón para recopilar correo electrónico no deseado y suplantación de identidad que son notificados por los usuarios.
ms.openlocfilehash: 38fa16b5270273813b4549b0c3c9baaa1b05b098
ms.sourcegitcommit: 6007dbe2cf758c683de399f94023122c678bcada
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2020
ms.locfileid: "44224558"
---
# <a name="specify-a-mailbox-for-user-submissions-of-spam-and-phishing-messages-in-exchange-online"></a><span data-ttu-id="52a19-103">Especificar un buzón para envíos de usuarios de correo no deseado y mensajes de suplantación de identidad en Exchange Online</span><span class="sxs-lookup"><span data-stu-id="52a19-103">Specify a mailbox for user submissions of spam and phishing messages in Exchange Online</span></span>

<span data-ttu-id="52a19-104">En Microsoft 365 organizaciones con buzones de correo de Exchange Online, puede especificar un buzón para recibir mensajes que los usuarios notifican como malintencionados o no malintencionados.</span><span class="sxs-lookup"><span data-stu-id="52a19-104">In Microsoft 365 organizations with Exchange Online mailboxes, you can specify a mailbox to receive messages that users report as malicious or not malicious.</span></span> <span data-ttu-id="52a19-105">Cuando los usuarios envían mensajes con las distintas opciones de informes, puede usar este buzón de correo para interceptar mensajes (enviar solo al buzón personalizado) o recibir copias de los mensajes (enviar al buzón de correo personalizado y Microsoft).</span><span class="sxs-lookup"><span data-stu-id="52a19-105">When users submit messages using the various reporting options, you can use this mailbox to intercept messages (send to the custom mailbox only) or receive copies of messages (send to the custom mailbox and Microsoft).</span></span> <span data-ttu-id="52a19-106">Esta característica funciona con las siguientes opciones de informe de mensajes:</span><span class="sxs-lookup"><span data-stu-id="52a19-106">This feature works with the following message reporting options:</span></span>

- [<span data-ttu-id="52a19-107">El complemento de mensajes de informe</span><span class="sxs-lookup"><span data-stu-id="52a19-107">The Report Message add-in</span></span>](enable-the-report-message-add-in.md)

- <span data-ttu-id="52a19-108">[Informes integrados en Outlook en la web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (anteriormente conocido como Outlook Web App)</span><span class="sxs-lookup"><span data-stu-id="52a19-108">[Built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (formerly known as Outlook Web App)</span></span>

  > [!NOTE]
  > <span data-ttu-id="52a19-109">Si se ha [deshabilitado la generación de informes en Outlook en la web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop#disable-or-enable-junk-email-reporting-in-outlook-on-the-web), la habilitación de los envíos de usuario aquí invalidará esa configuración y permitirá a los usuarios volver a notificar los mensajes en Outlook en la Web.</span><span class="sxs-lookup"><span data-stu-id="52a19-109">If reporting has been [disabled in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop#disable-or-enable-junk-email-reporting-in-outlook-on-the-web), enabling user submissions here will override that setting and enable users to report messages in Outlook on the web again.</span></span>

<span data-ttu-id="52a19-110">También puede configurar herramientas de informes de mensajes de terceros para reenviar mensajes al buzón de correo que especifique.</span><span class="sxs-lookup"><span data-stu-id="52a19-110">You can also configure third-party message reporting tools to forward messages to the mailbox that you specify.</span></span>

<span data-ttu-id="52a19-111">La entrega de mensajes de usuario que se han informado a un buzón de correo personalizado, en lugar de hacerlo directamente a Microsoft, permite a los administradores informar de forma selectiva y selectiva a Microsoft mediante el [envío de administración](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="52a19-111">Delivering user reported messages to a custom mailbox instead of directly to Microsoft allows your admins to selectively and manually report messages to Microsoft using [Admin submission](admin-submission.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="52a19-112">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="52a19-112">What do you need to know before you begin?</span></span>

- <span data-ttu-id="52a19-113">Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="52a19-113">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="52a19-114">Para ir directamente a la página **envíos de usuarios** , use <https://protection.office.com/userSubmissionsReportMessage> .</span><span class="sxs-lookup"><span data-stu-id="52a19-114">To go directly to the **User submissions** page, use <https://protection.office.com/userSubmissionsReportMessage>.</span></span>

- <span data-ttu-id="52a19-115">Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="52a19-115">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="52a19-116">Para conectarse a PowerShell de EOP independiente, vea [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="52a19-116">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="52a19-117">Deberá tener asignados permisos antes de poder llevar a cabo estos procedimientos.</span><span class="sxs-lookup"><span data-stu-id="52a19-117">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="52a19-118">Para configurar el buzón de correo para envíos de usuarios, debe ser miembro de los grupos de roles administración de la **organización** o **Administrador de seguridad** .</span><span class="sxs-lookup"><span data-stu-id="52a19-118">To configure the mailbox for user submissions, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="52a19-119">Para obtener más información acerca de los grupos de roles en el Centro de seguridad y cumplimiento, consulte [Permisos en el Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="52a19-119">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="use-the-security--compliance-center-to-configure-the-user-submissions-mailbox"></a><span data-ttu-id="52a19-120">Usar el centro de seguridad & cumplimiento para configurar el buzón de envíos de usuarios</span><span class="sxs-lookup"><span data-stu-id="52a19-120">Use the Security & Compliance Center to configure the user submissions mailbox</span></span>

1. <span data-ttu-id="52a19-121">En el centro de seguridad & cumplimiento, vaya **Threat management** a \> **Policy** \> **envíos de usuarios**de la Directiva de administración de amenazas.</span><span class="sxs-lookup"><span data-stu-id="52a19-121">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **User submissions**.</span></span>

2. <span data-ttu-id="52a19-122">En la página **envíos de usuarios** que aparece, seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="52a19-122">In the **User submissions** page that appears, select one of the following options:</span></span>

   - <span data-ttu-id="52a19-123">**Habilitar la característica de mensaje de informe para Outlook (recomendado)**: Seleccione esta opción si usa el complemento de mensajes de informe o los informes integrados en Outlook en la web y, a continuación, configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="52a19-123">**Enable the Report Message feature for Outlook (Recommended)**: Select this option if you use the Report Message add-in or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>

     - <span data-ttu-id="52a19-124">**Personalizar el mensaje de confirmación del usuario final**: haga clic en este vínculo.</span><span class="sxs-lookup"><span data-stu-id="52a19-124">**Customize the end-user confirmation message**: Click this link.</span></span> <span data-ttu-id="52a19-125">En el control flotante **personalizar mensaje de confirmación** que aparece, configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="52a19-125">In the **Customize confirmation message** flyout that appears, configure the following settings:</span></span>

       - <span data-ttu-id="52a19-126">**Antes de enviar**: en los cuadros de mensaje **título** y **confirmación** , escriba el texto descriptivo que verán los usuarios antes de que informen de un mensaje mediante el complemento de mensajes de informe.</span><span class="sxs-lookup"><span data-stu-id="52a19-126">**Before submission**: In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see before they report a message using the Report Message add-in.</span></span> <span data-ttu-id="52a19-127">Puede usar la variable% Type% para incluir el tipo de envío (correo no deseado, correo deseado, phish, etc.).</span><span class="sxs-lookup"><span data-stu-id="52a19-127">You can use the variable %type% to include the submission type (junk, not junk, phish, etc.).</span></span>

         <span data-ttu-id="52a19-128">Como se indicó, el texto siguiente también se agrega a la notificación:</span><span class="sxs-lookup"><span data-stu-id="52a19-128">As noted, the following text is also added to the notification:</span></span>

         > <span data-ttu-id="52a19-129">El correo electrónico se enviará tal cual a Microsoft para su análisis.</span><span class="sxs-lookup"><span data-stu-id="52a19-129">Your email will be submitted as-is to Microsoft for analysis.</span></span> <span data-ttu-id="52a19-130">Algunos mensajes de correo electrónico pueden contener información personal o confidencial.</span><span class="sxs-lookup"><span data-stu-id="52a19-130">Some emails might contain personal or sensitive information.</span></span>

       - <span data-ttu-id="52a19-131">**Después del envío**: haga clic en ![ expandir icono ](../../media/scc-expand-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="52a19-131">**After submission**: Click ![Expand icon](../../media/scc-expand-icon.png).</span></span> <span data-ttu-id="52a19-132">En los cuadros de texto **título** y **confirmación** , escriba el texto descriptivo que los usuarios verán después de que informen de un mensaje mediante el complemento de mensajes de informe.</span><span class="sxs-lookup"><span data-stu-id="52a19-132">In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see after they report a message using the Report Message add-in.</span></span> <span data-ttu-id="52a19-133">Puede usar la variable% Type% para incluir el tipo de envío.</span><span class="sxs-lookup"><span data-stu-id="52a19-133">You can use the variable %type% to include the submission type.</span></span>

      <span data-ttu-id="52a19-134">Cuando haya terminado, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="52a19-134">When you're finished, click **Save**.</span></span> <span data-ttu-id="52a19-135">Para borrar estos valores, haga clic en **restaurar** de nuevo en la página **envíos de usuarios** .</span><span class="sxs-lookup"><span data-stu-id="52a19-135">To clear these values, click **Restore** back on the **User submissions** page.</span></span>

   - <span data-ttu-id="52a19-136">**Enviar los mensajes notificados a**: realice una de las siguientes selecciones:</span><span class="sxs-lookup"><span data-stu-id="52a19-136">**Send the reported messages to**: Make one of the following selections:</span></span>

     - <span data-ttu-id="52a19-137">**Microsoft (recomendado)**: no se usa el buzón de envíos de usuario (todos los mensajes que se han informado van a Microsoft).</span><span class="sxs-lookup"><span data-stu-id="52a19-137">**Microsoft (Recommended)**: The user submissions mailbox isn't used (all reported messages go to Microsoft).</span></span>

     - <span data-ttu-id="52a19-138">**Microsoft y un buzón personalizado**: en el cuadro que aparece, escriba la dirección de correo electrónico de un buzón de Exchange Online existente.</span><span class="sxs-lookup"><span data-stu-id="52a19-138">**Microsoft and a custom mailbox**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span> <span data-ttu-id="52a19-139">No se permiten los grupos de distribución.</span><span class="sxs-lookup"><span data-stu-id="52a19-139">Distribution groups are not allowed.</span></span>

     - <span data-ttu-id="52a19-140">**Buzón personalizado**: en el cuadro que aparece, escriba la dirección de correo electrónico de un buzón de Exchange Online existente.</span><span class="sxs-lookup"><span data-stu-id="52a19-140">**Custom mailbox**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span> <span data-ttu-id="52a19-141">No se permiten los grupos de distribución.</span><span class="sxs-lookup"><span data-stu-id="52a19-141">Distribution groups are not allowed.</span></span>

     <span data-ttu-id="52a19-142">Cuando haya terminado, haga clic en **confirmar**.</span><span class="sxs-lookup"><span data-stu-id="52a19-142">When you're finished, click **Confirm**.</span></span>

     ![Enviar mensajes notificados a Microsoft y a un buzón personalizado](../../media/user-submission-enable-outlook-report-message.png)

   - <span data-ttu-id="52a19-144">**Deshabilitar la característica de mensaje de informe para Outlook**: Seleccione esta opción si usa herramientas de informes de terceros en lugar del complemento de mensajes de informe o la creación de informes integrados en Outlook en la web y, a continuación, configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="52a19-144">**Disable the Report Message feature for Outlook**: Select this option if you use third-party reporting tools instead of the Report Message add-in or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>

     <span data-ttu-id="52a19-145">Seleccione **usar este buzón personalizado para recibir envíos notificados por el usuario**.</span><span class="sxs-lookup"><span data-stu-id="52a19-145">Select **Use this custom mailbox to receive user reported submissions**.</span></span> <span data-ttu-id="52a19-146">En el cuadro que aparece, escriba la dirección de correo electrónico de un buzón existente o la dirección de correo electrónico del buzón que desea crear.</span><span class="sxs-lookup"><span data-stu-id="52a19-146">In the box that appears, enter the email address of an existing mailbox, or the email address of the mailbox that you want to create.</span></span>

     <span data-ttu-id="52a19-147">Cuando haya terminado, haga clic en **confirmar**.</span><span class="sxs-lookup"><span data-stu-id="52a19-147">When you're finished, click **Confirm**.</span></span>

     ![Enviar mensajes de informes a un buzón personalizado con herramientas de terceros](../../media/user-submission-disable-outlook-report-message.png)
