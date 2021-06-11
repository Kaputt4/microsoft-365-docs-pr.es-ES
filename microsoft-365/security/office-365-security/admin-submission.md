---
title: Envíos de administrador
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden aprender a usar el portal de envíos en el centro de seguridad de Microsoft 365 para enviar correos electrónicos sospechosos, correos de suplantación de identidad sospechosos, correo no deseado y otros mensajes potencialmente dañinos, direcciones URL y datos adjuntos de correo electrónico a Microsoft para volver a examinarlos.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6de6a018a96407a5690249bea15e90c2f5a0d1ed
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878693"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="4fd46-103">Usar el Envío para administradores para enviar correo no deseado, de suplantación de identidad, direcciones URL y archivos sospechosos a Microsoft</span><span class="sxs-lookup"><span data-stu-id="4fd46-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="4fd46-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="4fd46-104">**Applies to**</span></span>
- [<span data-ttu-id="4fd46-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="4fd46-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="4fd46-106">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="4fd46-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)


<span data-ttu-id="4fd46-107">En Microsoft 365 organizaciones con buzones de correo en Exchange Online, los administradores pueden usar el portal de envíos del Centro de seguridad y cumplimiento de & para enviar mensajes de correo electrónico, direcciones URL y datos adjuntos a Microsoft para examinarlos.</span><span class="sxs-lookup"><span data-stu-id="4fd46-107">In Microsoft 365 organizations with mailboxes in Exchange Online, admins can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="4fd46-108">Cuando envíe un mensaje de correo electrónico, recibirá:</span><span class="sxs-lookup"><span data-stu-id="4fd46-108">When you submit an email message, you will get:</span></span>

1. <span data-ttu-id="4fd46-109">**Comprobación de autenticación de** correo electrónico: detalles sobre si la autenticación de correo electrónico se ha pasado o no cuando se entregó.</span><span class="sxs-lookup"><span data-stu-id="4fd46-109">**Email authentication check**: Details on whether email authentication passed or failed when it was delivered.</span></span>
2. <span data-ttu-id="4fd46-110">**Aciertos de** directiva: información sobre las directivas que pueden haber permitido o bloqueado el correo electrónico entrante en su inquilino, invalidando nuestros veredictos de filtro de servicio.</span><span class="sxs-lookup"><span data-stu-id="4fd46-110">**Policy hits**: Information about any policies that may have allowed or blocked the incoming email into your tenant, overriding our service filter verdicts.</span></span>
3. <span data-ttu-id="4fd46-111">**Reputación/detonación de carga:** examen de las direcciones URL y los datos adjuntos del mensaje.</span><span class="sxs-lookup"><span data-stu-id="4fd46-111">**Payload reputation/detonation**: Examination of any URLs and attachments in the message.</span></span>
4. <span data-ttu-id="4fd46-112">**Análisis del calificador:** revisión realizada por calificadores humanos para confirmar si los mensajes son malintencionados o no.</span><span class="sxs-lookup"><span data-stu-id="4fd46-112">**Grader analysis**: Review done by human graders in order to confirm whether or not messages are malicious.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4fd46-113">El análisis de reputación/detonación y calificador de carga no se realiza en todos los inquilinos.</span><span class="sxs-lookup"><span data-stu-id="4fd46-113">Payload reputation/detonation and grader analysis are not done in all tenants.</span></span> <span data-ttu-id="4fd46-114">La información se bloquea para que no salga de la organización cuando los datos no deben salir del límite del espacio empresarial con fines de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="4fd46-114">Information is blocked from going outside the organization when data is not supposed to leave the tenant boundary for compliance purposes.</span></span>

<span data-ttu-id="4fd46-115">Para obtener otras formas de enviar mensajes de correo electrónico, direcciones URL y datos adjuntos a Microsoft, vea [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="4fd46-115">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="4fd46-116">¿Qué necesita saber antes de empezar?</span><span class="sxs-lookup"><span data-stu-id="4fd46-116">What do you need to know before you begin?</span></span>

- <span data-ttu-id="4fd46-117">Abra el centro Microsoft 365 seguridad en <https://security.microsoft.com/> .</span><span class="sxs-lookup"><span data-stu-id="4fd46-117">You open the Microsoft 365 security center at <https://security.microsoft.com/>.</span></span> <span data-ttu-id="4fd46-118">Para ir directamente a la **página Envíos,** use <https://security.microsoft.com/reportsubmission> .</span><span class="sxs-lookup"><span data-stu-id="4fd46-118">To go directly to the **Submissions** page, use <https://security.microsoft.com/reportsubmission>.</span></span>

- <span data-ttu-id="4fd46-119">Para enviar mensajes y archivos a Microsoft, debe ser miembro de uno de los siguientes grupos de roles:</span><span class="sxs-lookup"><span data-stu-id="4fd46-119">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="4fd46-120">**Administración de** la organización **o Lector de seguridad** en el Microsoft 365 de [seguridad](permissions-microsoft-365-security-center.md).</span><span class="sxs-lookup"><span data-stu-id="4fd46-120">**Organization Management** or **Security Reader** in the [Microsoft 365 security center](permissions-microsoft-365-security-center.md).</span></span>

  - <span data-ttu-id="4fd46-121">**Administración de** la [organización en Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="4fd46-121">**Organization Management** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

    <span data-ttu-id="4fd46-122">Tenga en cuenta que la pertenencia a este grupo de roles es necesaria para ver los [envíos](#view-user-submissions-to-the-custom-mailbox) de usuarios al buzón personalizado, tal como se describe más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="4fd46-122">Note that membership in this role group is required to [View user submissions to the custom mailbox](#view-user-submissions-to-the-custom-mailbox) as described later in this article.</span></span>

- <span data-ttu-id="4fd46-123">Para obtener más información acerca de cómo los usuarios pueden enviar mensajes y archivos a Microsoft, vea [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="4fd46-123">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="4fd46-124">Informar de contenido sospechoso a Microsoft</span><span class="sxs-lookup"><span data-stu-id="4fd46-124">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="4fd46-125">En el centro [Microsoft 365](../defender/overview-security-center.md)seguridad, vaya a **Envíos** y  compruebe que está en la pestaña Enviado para análisis y, a continuación, haga clic en Enviar a Microsoft para **su revisión.**</span><span class="sxs-lookup"><span data-stu-id="4fd46-125">In the [Microsoft 365 security center](../defender/overview-security-center.md), go to **Submissions** and verify that you're on the **Submitted for analysis** tab, and then click **Submit to Microsoft for review**.</span></span>

2. <span data-ttu-id="4fd46-126">Use el menú desplegable Enviar a **Microsoft** para revisión que parece enviar el mensaje, la dirección URL o los datos adjuntos de correo electrónico, tal como se describe en las secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="4fd46-126">Use the **Submit to Microsoft for review** flyout that appears to submit the message, URL, or email attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="4fd46-127">Enviar un correo electrónico cuestionable a Microsoft</span><span class="sxs-lookup"><span data-stu-id="4fd46-127">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="4fd46-128">En la **sección Seleccionar el tipo de envío,** seleccione Correo **electrónico**.</span><span class="sxs-lookup"><span data-stu-id="4fd46-128">In the **Select the submission type** section, select **Email**.</span></span> <span data-ttu-id="4fd46-129">En la **sección Agregar el identificador de mensaje de red o cargar** el archivo de correo electrónico, use una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="4fd46-129">In the **Add the network message ID or upload the email file** section, use one of the following options:</span></span>

   - <span data-ttu-id="4fd46-130">Agregar el identificador de mensaje de red de correo **electrónico:** se trata de un valor GUID que está disponible en el encabezado **X-MS-Exchange-Organization-Network-Message-Id** en el mensaje o en el encabezado **X-MS-Office365-Filtering-Correlation-Id** en mensajes en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="4fd46-130">**Add the email network message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message or in the **X-MS-Office365-Filtering-Correlation-Id** header in quarantined messages.</span></span>

   - <span data-ttu-id="4fd46-131">**Upload el archivo de correo** electrónico: haga clic en Examinar **archivos**.</span><span class="sxs-lookup"><span data-stu-id="4fd46-131">**Upload the email file**: Click **Browse files**.</span></span> <span data-ttu-id="4fd46-132">En el cuadro de diálogo que se abre, busque y seleccione el archivo .eml o .msg y, a continuación, haga clic **en Abrir**.</span><span class="sxs-lookup"><span data-stu-id="4fd46-132">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="4fd46-133">La capacidad de enviar mensajes tan antiguos como 30 días se ha suspendido temporalmente para Defender para Office 365 clientes.</span><span class="sxs-lookup"><span data-stu-id="4fd46-133">The ability to submit messages as old as 30 days has been temporarily suspended for Defender for Office 365 customers.</span></span> <span data-ttu-id="4fd46-134">Los administradores solo podrán volver 7 días atrás.</span><span class="sxs-lookup"><span data-stu-id="4fd46-134">Admins will only be able to go back 7 days.</span></span>

2. <span data-ttu-id="4fd46-135">En la **sección Elegir un destinatario con un** problema, especifique el destinatario con el que desea ejecutar una comprobación de directiva.</span><span class="sxs-lookup"><span data-stu-id="4fd46-135">In the **Choose a recipient who had an issue** section, specify the recipient that you would like to run a policy check against.</span></span> <span data-ttu-id="4fd46-136">La comprobación de directivas determinará si el correo electrónico omitió el examen debido a directivas de usuario u organización.</span><span class="sxs-lookup"><span data-stu-id="4fd46-136">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="4fd46-137">En la **sección Seleccionar un motivo para enviar a Microsoft,** seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="4fd46-137">In the **Select a reason for submitting to Microsoft** section, select one of the following options:</span></span>

   - <span data-ttu-id="4fd46-138">**No se debería haber bloqueado**</span><span class="sxs-lookup"><span data-stu-id="4fd46-138">**Should not have been blocked**</span></span>

   - <span data-ttu-id="4fd46-139">**Debería haber sido bloqueado:** Seleccione **Correo no deseado,** **Suplantación** de identidad o **Malware.**</span><span class="sxs-lookup"><span data-stu-id="4fd46-139">**Should have been blocked**: Select **Spam**, **Phishing**, or **Malware**.</span></span> <span data-ttu-id="4fd46-140">Si no está seguro, use su mejor criterio.</span><span class="sxs-lookup"><span data-stu-id="4fd46-140">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="4fd46-141">Cuando haya terminado, haga clic en el **botón Enviar.**</span><span class="sxs-lookup"><span data-stu-id="4fd46-141">When you're finished, click the **Submit** button.</span></span>

   ![Ejemplo de envío de nueva dirección URL](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="4fd46-143">Enviar una dirección URL sospechosa a Microsoft</span><span class="sxs-lookup"><span data-stu-id="4fd46-143">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="4fd46-144">En la **sección Seleccionar el tipo de envío,** seleccione DIRECCIÓN **URL**.</span><span class="sxs-lookup"><span data-stu-id="4fd46-144">In the **Select the submission type** section, select **URL**.</span></span> <span data-ttu-id="4fd46-145">En el cuadro que aparece, escriba la dirección URL completa (por ejemplo, `https://www.fabrikam.com/marketing.html` ).</span><span class="sxs-lookup"><span data-stu-id="4fd46-145">In the box that appears, enter the full URL (for example, `https://www.fabrikam.com/marketing.html`).</span></span>

2. <span data-ttu-id="4fd46-146">En la **sección Motivo del envío,** seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="4fd46-146">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="4fd46-147">**No se debería haber bloqueado**</span><span class="sxs-lookup"><span data-stu-id="4fd46-147">**Should not have been blocked**</span></span>

   - <span data-ttu-id="4fd46-148">**Debería haber sido bloqueado:** Seleccione **Phishing** o **Malware**.</span><span class="sxs-lookup"><span data-stu-id="4fd46-148">**Should have been blocked**: Select **Phishing** or **Malware**.</span></span>

3. <span data-ttu-id="4fd46-149">Cuando haya terminado, haga clic en el **botón Enviar.**</span><span class="sxs-lookup"><span data-stu-id="4fd46-149">When you're finished, click the **Submit** button.</span></span>

   ![Ejemplo de nuevo envío de correo electrónico](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-email-attachment-to-microsoft"></a><span data-ttu-id="4fd46-151">Enviar datos adjuntos de correo electrónico sospechosos a Microsoft</span><span class="sxs-lookup"><span data-stu-id="4fd46-151">Submit a suspected email attachment to Microsoft</span></span>

1. <span data-ttu-id="4fd46-152">En la **sección Seleccionar el tipo de envío,** seleccione Datos **adjuntos de correo electrónico**.</span><span class="sxs-lookup"><span data-stu-id="4fd46-152">In the **Select the submission type** section, select **Email attachment**.</span></span>

2. <span data-ttu-id="4fd46-153">Haga clic **en Elegir archivo**.</span><span class="sxs-lookup"><span data-stu-id="4fd46-153">Click **Choose File**.</span></span> <span data-ttu-id="4fd46-154">En el cuadro de diálogo que se abre, busque y seleccione el archivo y, a continuación, haga clic en **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="4fd46-154">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="4fd46-155">En la **sección Motivo del envío,** seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="4fd46-155">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="4fd46-156">**No se debería haber bloqueado**</span><span class="sxs-lookup"><span data-stu-id="4fd46-156">**Should not have been blocked**</span></span>

   - <span data-ttu-id="4fd46-157">**Debería haber sido bloqueado:** **el malware** es la única opción y se selecciona automáticamente.</span><span class="sxs-lookup"><span data-stu-id="4fd46-157">**Should have been blocked**: **Malware** is the only choice, and is automatically selected.</span></span>

4. <span data-ttu-id="4fd46-158">Cuando haya terminado, haga clic en el **botón Enviar.**</span><span class="sxs-lookup"><span data-stu-id="4fd46-158">When you're finished, click the **Submit** button.</span></span>

   ![Ejemplo de nuevo envío de datos adjuntos](../../media/submission-file-flyout.PNG)

## <a name="view-items-submitted-for-analysis"></a><span data-ttu-id="4fd46-160">Ver elementos enviados para el análisis</span><span class="sxs-lookup"><span data-stu-id="4fd46-160">View items Submitted for analysis</span></span>

<span data-ttu-id="4fd46-161">En el Microsoft 365 de seguridad, vaya a **Envíos** y compruebe que está en la pestaña **Enviado para análisis**</span><span class="sxs-lookup"><span data-stu-id="4fd46-161">In the Microsoft 365 security center, go to **Submissions**, and verify that you're on the **Submitted for analysis** tab</span></span>

<span data-ttu-id="4fd46-162">En la barra de comandos en el centro de la página, puede escribir una fecha de inicio, una fecha de finalización y ,de forma predeterminada, puede filtrar por identificador de envío **(un** valor GUID asignado a cada envío) especificando un valor en el cuadro y haciendo clic en el botón Actualizar ![ ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="4fd46-162">In the command bar in the middle of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** (a GUID value that's assigned to every submission) by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="4fd46-163">Update</span><span class="sxs-lookup"><span data-stu-id="4fd46-163">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="4fd46-164">Para cambiar los criterios de filtro, haga clic en **el botón Filtrar** y elija uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="4fd46-164">To change the filter criteria, click the **Filter** button and choose one of the following values:</span></span>

- <span data-ttu-id="4fd46-165">**Sender**</span><span class="sxs-lookup"><span data-stu-id="4fd46-165">**Sender**</span></span>
- <span data-ttu-id="4fd46-166">**Asunto/DIRECCIÓN URL/Nombre de archivo**</span><span class="sxs-lookup"><span data-stu-id="4fd46-166">**Subject/URL/File name**</span></span>
- <span data-ttu-id="4fd46-167">**Enviado por**</span><span class="sxs-lookup"><span data-stu-id="4fd46-167">**Submitted by**</span></span>
- <span data-ttu-id="4fd46-168">**Tipo de envío**</span><span class="sxs-lookup"><span data-stu-id="4fd46-168">**Submission type**</span></span>
- <span data-ttu-id="4fd46-169">**Estado**</span><span class="sxs-lookup"><span data-stu-id="4fd46-169">**Status**</span></span>

![Nuevas opciones de filtro para envíos de administrador](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="4fd46-171">Para exportar los resultados, haga clic **en Exportar** cerca de la parte superior de la página y seleccione Datos **del gráfico** o **Tabla**.</span><span class="sxs-lookup"><span data-stu-id="4fd46-171">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="4fd46-172">En el cuadro de diálogo que aparece, guarde el .csv archivo.</span><span class="sxs-lookup"><span data-stu-id="4fd46-172">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="4fd46-173">Debajo del gráfico, hay tres pestañas: **Correo** electrónico (predeterminado), **DIRECCIÓN URL** y Datos adjuntos de **correo electrónico**.</span><span class="sxs-lookup"><span data-stu-id="4fd46-173">Below the graph, there are three tabs: **Email** (default), **URL**, and **Email attachment**.</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="4fd46-174">Ver envíos de correo electrónico de administrador</span><span class="sxs-lookup"><span data-stu-id="4fd46-174">View admin email submissions</span></span>

<span data-ttu-id="4fd46-175">Puede hacer clic en el **botón Personalizar columnas** cerca de la parte inferior de la página para agregar o quitar columnas de la vista:</span><span class="sxs-lookup"><span data-stu-id="4fd46-175">You can click the **Customize columns** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="4fd46-176">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="4fd46-176">**Date**</span></span>
- <span data-ttu-id="4fd46-177">**Identificador de envío:** valor GUID que se asigna a cada envío.</span><span class="sxs-lookup"><span data-stu-id="4fd46-177">**Submission ID**: A GUID value that's assigned to every submission.</span></span>
- <span data-ttu-id="4fd46-178">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4fd46-178">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="4fd46-179">**Asunto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4fd46-179">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="4fd46-180">**Sender**</span><span class="sxs-lookup"><span data-stu-id="4fd46-180">**Sender**</span></span>
- <span data-ttu-id="4fd46-181">**IP del remitente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4fd46-181">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="4fd46-182">**Tipo de envío**</span><span class="sxs-lookup"><span data-stu-id="4fd46-182">**Submission type**</span></span>
- <span data-ttu-id="4fd46-183">**Motivo de entrega**</span><span class="sxs-lookup"><span data-stu-id="4fd46-183">**Delivery reason**</span></span>
- <span data-ttu-id="4fd46-184">**Estado**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4fd46-184">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="4fd46-185"><sup>\*</sup> Si hace clic en este valor, se muestra información detallada en un menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="4fd46-185"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

#### <a name="admin-submission-rescan-details"></a><span data-ttu-id="4fd46-186">Detalles de reescaneo de envío de administrador</span><span class="sxs-lookup"><span data-stu-id="4fd46-186">Admin submission rescan details</span></span>

<span data-ttu-id="4fd46-187">Los mensajes que se envían en envíos de administrador se examinan de nuevo y los resultados se muestran en el menú desplegable de detalles de envíos:</span><span class="sxs-lookup"><span data-stu-id="4fd46-187">Messages that are submitted in admin submissions are rescanned and results shown in the submissions detail flyout:</span></span>

- <span data-ttu-id="4fd46-188">Si hubo un error en la autenticación de correo electrónico del remitente en el momento de la entrega.</span><span class="sxs-lookup"><span data-stu-id="4fd46-188">If there was a failure in the sender's email authentication at the time of delivery.</span></span>
- <span data-ttu-id="4fd46-189">Información sobre los aciertos de directiva que puedan haber afectado o invalidado el veredicto de un mensaje.</span><span class="sxs-lookup"><span data-stu-id="4fd46-189">Information about any policy hits that could have affected or overridden the verdict of a message.</span></span>
- <span data-ttu-id="4fd46-190">Actualice los resultados de cancelación para ver si las direcciones URL o los archivos contenidos en el mensaje son malintencionados o no.</span><span class="sxs-lookup"><span data-stu-id="4fd46-190">Current detonation results to see if the URLs or files contained in the message were malicious or not.</span></span>
- <span data-ttu-id="4fd46-191">Comentarios de los calificadores.</span><span class="sxs-lookup"><span data-stu-id="4fd46-191">Feedback from graders.</span></span>

<span data-ttu-id="4fd46-192">Si se encontró una invalidación, se volverá a ejecutar una detección que se completará en unos minutos.</span><span class="sxs-lookup"><span data-stu-id="4fd46-192">If an override was found, the rescan should complete in several minutes.</span></span> <span data-ttu-id="4fd46-193">Si no hubo un problema en la autenticación o entrega de correo electrónico no se vio afectado por una invalidación, los comentarios de los calificadores podrían tardar hasta un día.</span><span class="sxs-lookup"><span data-stu-id="4fd46-193">If there wasn't a problem in email authentication or delivery wasn't affected by an override, then the feedback from graders could take up to a day.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="4fd46-194">Ver envíos de url de administrador</span><span class="sxs-lookup"><span data-stu-id="4fd46-194">View admin URL submissions</span></span>

<span data-ttu-id="4fd46-195">Haga clic en la **pestaña Dirección** URL.</span><span class="sxs-lookup"><span data-stu-id="4fd46-195">Click the **URL** tab.</span></span>

<span data-ttu-id="4fd46-196">Puede hacer clic en el **botón Opciones de columna** cerca de la parte inferior de la página para agregar o quitar columnas de la vista:</span><span class="sxs-lookup"><span data-stu-id="4fd46-196">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="4fd46-197">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="4fd46-197">**Date**</span></span>
- <span data-ttu-id="4fd46-198">**Identificador de envío**</span><span class="sxs-lookup"><span data-stu-id="4fd46-198">**Submission ID**</span></span>
- <span data-ttu-id="4fd46-199">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4fd46-199">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="4fd46-200">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4fd46-200">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="4fd46-201">**Tipo de envío**</span><span class="sxs-lookup"><span data-stu-id="4fd46-201">**Submission type**</span></span>
- <span data-ttu-id="4fd46-202">**Estado**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4fd46-202">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="4fd46-203"><sup>\*</sup> Si hace clic en este valor, se muestra información detallada en un menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="4fd46-203"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-email-attachment-submissions"></a><span data-ttu-id="4fd46-204">Ver envíos de datos adjuntos de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="4fd46-204">View email attachment submissions</span></span>

<span data-ttu-id="4fd46-205">Haga clic en **la pestaña Datos** adjuntos.</span><span class="sxs-lookup"><span data-stu-id="4fd46-205">Click the **Attachments** tab.</span></span>

<span data-ttu-id="4fd46-206">Puede hacer clic en el **botón Opciones de columna** cerca de la parte inferior de la página para agregar o quitar columnas de la vista:</span><span class="sxs-lookup"><span data-stu-id="4fd46-206">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="4fd46-207">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="4fd46-207">**Date**</span></span>
- <span data-ttu-id="4fd46-208">**Identificador de envío**</span><span class="sxs-lookup"><span data-stu-id="4fd46-208">**Submission ID**</span></span>
- <span data-ttu-id="4fd46-209">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4fd46-209">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="4fd46-210">**Nombre de archivo**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4fd46-210">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="4fd46-211">**Tipo de envío**</span><span class="sxs-lookup"><span data-stu-id="4fd46-211">**Submission type**</span></span>
- <span data-ttu-id="4fd46-212">**Estado**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4fd46-212">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="4fd46-213"><sup>\*</sup> Si hace clic en este valor, se muestra información detallada en un menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="4fd46-213"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="4fd46-214">Ver envíos de usuario a Microsoft</span><span class="sxs-lookup"><span data-stu-id="4fd46-214">View user submissions to Microsoft</span></span>

<span data-ttu-id="4fd46-215">Si ha implementado el complemento Report [Message](enable-the-report-message-add-in.md), el complemento [Report Phishing](enable-the-report-phish-add-in.md)o los usuarios usan los informes integrados en Outlook en la [web,](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)puede ver lo que los usuarios están informando en la pestaña **Envíos** de usuarios.</span><span class="sxs-lookup"><span data-stu-id="4fd46-215">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), the [Report Phishing add-in](enable-the-report-phish-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="4fd46-216">En el Centro de & cumplimiento, vaya a **Envíos de administración** \> **de amenazas**.</span><span class="sxs-lookup"><span data-stu-id="4fd46-216">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="4fd46-217">Seleccione la **pestaña Envíos de** usuario y, a continuación, haga clic **en Nuevo envío.**</span><span class="sxs-lookup"><span data-stu-id="4fd46-217">Select the **User submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="4fd46-218">Puede hacer clic en el **botón Opciones de columna** cerca de la parte inferior de la página para agregar o quitar columnas de la vista:</span><span class="sxs-lookup"><span data-stu-id="4fd46-218">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="4fd46-219">**Enviado en**</span><span class="sxs-lookup"><span data-stu-id="4fd46-219">**Submitted on**</span></span>
- <span data-ttu-id="4fd46-220">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4fd46-220">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="4fd46-221">**Asunto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4fd46-221">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="4fd46-222">**Sender**</span><span class="sxs-lookup"><span data-stu-id="4fd46-222">**Sender**</span></span>
- <span data-ttu-id="4fd46-223">**IP del remitente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4fd46-223">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="4fd46-224">**Tipo de envío**</span><span class="sxs-lookup"><span data-stu-id="4fd46-224">**Submission type**</span></span>

<span data-ttu-id="4fd46-225"><sup>\*</sup> Si hace clic en este valor, se muestra información detallada en un menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="4fd46-225"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="4fd46-226">Cerca de la parte superior de la página, puede escribir una fecha de  inicio, una fecha de finalización y , de forma predeterminada, puede filtrar por remitente especificando un valor en el cuadro y haciendo clic en el botón ![ Actualizar ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="4fd46-226">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="4fd46-227">Update</span><span class="sxs-lookup"><span data-stu-id="4fd46-227">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="4fd46-228">Para cambiar los criterios de filtro, haga clic en el **botón Remitente** y elija uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="4fd46-228">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="4fd46-229">**Dominio del remitente**</span><span class="sxs-lookup"><span data-stu-id="4fd46-229">**Sender domain**</span></span>
- <span data-ttu-id="4fd46-230">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="4fd46-230">**Subject**</span></span>
- <span data-ttu-id="4fd46-231">**Enviado por**</span><span class="sxs-lookup"><span data-stu-id="4fd46-231">**Submitted by**</span></span>
- <span data-ttu-id="4fd46-232">**Tipo de envío**</span><span class="sxs-lookup"><span data-stu-id="4fd46-232">**Submission type**</span></span>
- <span data-ttu-id="4fd46-233">**IP del remitente**</span><span class="sxs-lookup"><span data-stu-id="4fd46-233">**Sender IP**</span></span>

![Nuevas opciones de filtro para envíos de usuarios](../../media/user-submissions-filter-options.png)

<span data-ttu-id="4fd46-235">Para exportar los resultados, haga clic **en Exportar** cerca de la parte superior de la página y seleccione Datos **del gráfico** o **Tabla**.</span><span class="sxs-lookup"><span data-stu-id="4fd46-235">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="4fd46-236">En el cuadro de diálogo que aparece, guarde el .csv archivo.</span><span class="sxs-lookup"><span data-stu-id="4fd46-236">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="4fd46-237">Ver envíos de usuario al buzón personalizado</span><span class="sxs-lookup"><span data-stu-id="4fd46-237">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="4fd46-238">**Si** ha configurado un [buzón](user-submission.md) personalizado para recibir mensajes notificados por el usuario, puede ver y enviar también mensajes que se entregaron al buzón de informes.</span><span class="sxs-lookup"><span data-stu-id="4fd46-238">**If** you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="4fd46-239">En el Centro de & cumplimiento, vaya a **Envíos de administración** \> **de amenazas**.</span><span class="sxs-lookup"><span data-stu-id="4fd46-239">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="4fd46-240">Seleccione la **pestaña Buzón personalizado.**</span><span class="sxs-lookup"><span data-stu-id="4fd46-240">Select the **Custom mailbox** tab.</span></span>

<span data-ttu-id="4fd46-241">Puede hacer clic en el **botón Opciones de columna** cerca de la parte inferior de la página para agregar o quitar columnas de la vista:</span><span class="sxs-lookup"><span data-stu-id="4fd46-241">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="4fd46-242">**Enviado en**</span><span class="sxs-lookup"><span data-stu-id="4fd46-242">**Submitted on**</span></span>
- <span data-ttu-id="4fd46-243">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4fd46-243">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="4fd46-244">**Asunto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4fd46-244">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="4fd46-245">**Sender**</span><span class="sxs-lookup"><span data-stu-id="4fd46-245">**Sender**</span></span>
- <span data-ttu-id="4fd46-246">**IP del remitente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4fd46-246">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="4fd46-247">**Tipo de envío**</span><span class="sxs-lookup"><span data-stu-id="4fd46-247">**Submission type**</span></span>

<span data-ttu-id="4fd46-248">Cerca de la parte superior de la página, puede escribir una fecha de inicio, una fecha de finalización y puede filtrar por **Enviado** especificando un valor en el cuadro y haciendo clic en el botón ![ Actualizar ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="4fd46-248">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="4fd46-249">Update</span><span class="sxs-lookup"><span data-stu-id="4fd46-249">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="4fd46-250">Para exportar los resultados, haga clic **en Exportar** cerca de la parte superior de la página y seleccione Datos **del gráfico** o **Tabla**.</span><span class="sxs-lookup"><span data-stu-id="4fd46-250">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="4fd46-251">En el cuadro de diálogo que aparece, guarde el .csv archivo.</span><span class="sxs-lookup"><span data-stu-id="4fd46-251">In the dialog that appears, save the .csv file.</span></span>

> [!NOTE]
> <span data-ttu-id="4fd46-252">Si las organizaciones están configuradas para enviar solo al buzón personalizado, los mensajes notificados no se enviarán para volver a examinarse y los resultados en el portal de mensajes notificados por el usuario siempre estarán vacíos.</span><span class="sxs-lookup"><span data-stu-id="4fd46-252">If organizations are configured to send to custom mailbox only, reported messages will not be sent for rescan and results in the User reported messages portal will always be empty.</span></span>

## <a name="undo-user-submissions"></a><span data-ttu-id="4fd46-253">Deshacer envíos de usuarios</span><span class="sxs-lookup"><span data-stu-id="4fd46-253">Undo user submissions</span></span>

<span data-ttu-id="4fd46-254">Una vez que un usuario envía un correo electrónico sospechoso al buzón personalizado, el usuario y el administrador no tienen ninguna opción para deshacer el envío.</span><span class="sxs-lookup"><span data-stu-id="4fd46-254">Once a user submits a suspicious email to the custom mailbox, the user and admin don't have an option to undo the submission.</span></span> <span data-ttu-id="4fd46-255">Si el usuario desea recuperar el correo electrónico, estará disponible para su recuperación en las carpetas Elementos eliminados o Correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="4fd46-255">If the user would like to recover the email, it will be available for recovery in the Deleted Items or Junk Email folders.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="4fd46-256">Enviar mensajes a Microsoft desde el buzón personalizado</span><span class="sxs-lookup"><span data-stu-id="4fd46-256">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="4fd46-257">Si ha configurado el buzón personalizado para interceptar mensajes notificados por el usuario sin enviar los mensajes a Microsoft, puede buscar y enviar mensajes específicos a Microsoft para su análisis.</span><span class="sxs-lookup"><span data-stu-id="4fd46-257">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="4fd46-258">Esto mueve de forma eficaz un envío de usuario a un envío de administrador.</span><span class="sxs-lookup"><span data-stu-id="4fd46-258">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="4fd46-259">En la **pestaña Mensajes notificados por** el usuario, seleccione un mensaje en la lista, haga clic en el botón Acción y realice una de las siguientes selecciones: </span><span class="sxs-lookup"><span data-stu-id="4fd46-259">On the **User reported messages** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="4fd46-260">**Informe limpio**</span><span class="sxs-lookup"><span data-stu-id="4fd46-260">**Report clean**</span></span>
- <span data-ttu-id="4fd46-261">**Report phishing**</span><span class="sxs-lookup"><span data-stu-id="4fd46-261">**Report phishing**</span></span>
- <span data-ttu-id="4fd46-262">**Informar de malware**</span><span class="sxs-lookup"><span data-stu-id="4fd46-262">**Report malware**</span></span>
- <span data-ttu-id="4fd46-263">**Notificar correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="4fd46-263">**Report spam**</span></span>

![Nuevas opciones en el botón Acción](../../media/user-submission-custom-mailbox-action-button.png)
