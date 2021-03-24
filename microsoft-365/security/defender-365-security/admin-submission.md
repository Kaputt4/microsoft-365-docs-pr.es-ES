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
description: Los administradores pueden aprender a usar el portal de envíos en el Centro de seguridad y cumplimiento de & para enviar correos electrónicos sospechosos, correos de suplantación de identidad sospechosos, correo no deseado y otros mensajes, direcciones URL y archivos potencialmente dañinos a Microsoft para su análisis.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3dd566de3ba4b4281b19c423b8623f081c378bca
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51073688"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="f08e8-103">Usar el Envío para administradores para enviar correo no deseado, de suplantación de identidad, direcciones URL y archivos sospechosos a Microsoft</span><span class="sxs-lookup"><span data-stu-id="f08e8-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="f08e8-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="f08e8-104">**Applies to**</span></span>
- [<span data-ttu-id="f08e8-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="f08e8-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="f08e8-106">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="f08e8-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)


<span data-ttu-id="f08e8-107">En las organizaciones de Microsoft 365 con buzones en Exchange Online, los administradores pueden usar el portal de envíos en el Centro de seguridad y cumplimiento de & para enviar mensajes de correo electrónico, direcciones URL y datos adjuntos a Microsoft para examinarlos.</span><span class="sxs-lookup"><span data-stu-id="f08e8-107">In Microsoft 365 organizations with mailboxes in Exchange Online, admins can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="f08e8-108">Cuando envíe un mensaje de correo electrónico, recibirá:</span><span class="sxs-lookup"><span data-stu-id="f08e8-108">When you submit an email message, you will get:</span></span>

1. <span data-ttu-id="f08e8-109">**Comprobación de autenticación de** correo electrónico: detalles sobre si la autenticación de correo electrónico se ha pasado o no cuando se entregó.</span><span class="sxs-lookup"><span data-stu-id="f08e8-109">**Email authentication check**: Details on whether email authentication passed or failed when it was delivered.</span></span>
2. <span data-ttu-id="f08e8-110">**Aciertos de** directiva: información sobre las directivas que pueden haber permitido o bloqueado el correo electrónico entrante en su inquilino, invalidando nuestros veredictos de filtro de servicio.</span><span class="sxs-lookup"><span data-stu-id="f08e8-110">**Policy hits**: Information about any policies that may have allowed or blocked the incoming email into your tenant, overriding our service filter verdicts.</span></span>
3. <span data-ttu-id="f08e8-111">**Reputación/detonación de carga:** examen de las direcciones URL y los datos adjuntos del mensaje.</span><span class="sxs-lookup"><span data-stu-id="f08e8-111">**Payload reputation/detonation**: Examination of any URLs and attachments in the message.</span></span>
4. <span data-ttu-id="f08e8-112">**Análisis del calificador:** revisión realizada por calificadores humanos para confirmar si los mensajes son malintencionados o no.</span><span class="sxs-lookup"><span data-stu-id="f08e8-112">**Grader analysis**: Review done by human graders in order to confirm whether or not messages are malicious.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f08e8-113">El análisis de reputación/detonación y calificador de carga no se realiza en todos los inquilinos.</span><span class="sxs-lookup"><span data-stu-id="f08e8-113">Payload reputation/detonation and grader analysis are not done in all tenants.</span></span> <span data-ttu-id="f08e8-114">La información se bloquea para que no salga de la organización cuando los datos no deben salir del límite del espacio empresarial con fines de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="f08e8-114">Information is blocked from going outside the organization when data is not supposed to leave the tenant boundary for compliance purposes.</span></span>

<span data-ttu-id="f08e8-115">Para obtener otras formas de enviar mensajes de correo electrónico, direcciones URL y datos adjuntos a Microsoft, vea [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="f08e8-115">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f08e8-116">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="f08e8-116">What do you need to know before you begin?</span></span>

- <span data-ttu-id="f08e8-117">Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="f08e8-117">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="f08e8-118">Para ir directamente a la **página Envío,** use <https://protection.office.com/reportsubmission> .</span><span class="sxs-lookup"><span data-stu-id="f08e8-118">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="f08e8-119">Para enviar mensajes y archivos a Microsoft, debe ser miembro de uno de los siguientes grupos de roles:</span><span class="sxs-lookup"><span data-stu-id="f08e8-119">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="f08e8-120">**Administración de la organización** o **Administrador de seguridad** en el [Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="f08e8-120">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  - <span data-ttu-id="f08e8-121">**Administración de la** organización [en Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="f08e8-121">**Organization Management** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

    <span data-ttu-id="f08e8-122">Tenga en cuenta que la pertenencia a este grupo de roles es necesaria para ver los [envíos](#view-user-submissions-to-the-custom-mailbox) de usuarios al buzón personalizado, tal como se describe más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="f08e8-122">Note that membership in this role group is required to [View user submissions to the custom mailbox](#view-user-submissions-to-the-custom-mailbox) as described later in this article.</span></span>

- <span data-ttu-id="f08e8-123">Para obtener más información acerca de cómo los usuarios pueden enviar mensajes y archivos a Microsoft, vea [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="f08e8-123">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="f08e8-124">Informar de contenido sospechoso a Microsoft</span><span class="sxs-lookup"><span data-stu-id="f08e8-124">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="f08e8-125">En el Centro de seguridad &  cumplimiento, vaya a \> **Envíos** de administración de amenazas , compruebe que está en la pestaña **Envíos** de administrador y, a continuación, haga clic en **Nuevo envío**.</span><span class="sxs-lookup"><span data-stu-id="f08e8-125">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

2. <span data-ttu-id="f08e8-126">Use **El menú desplegable** Nuevo envío que parece enviar el mensaje, la dirección URL o los datos adjuntos, tal como se describe en las secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="f08e8-126">Use **New submission** flyout that appears to submit the message, URL, or attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="f08e8-127">Enviar un correo electrónico cuestionable a Microsoft</span><span class="sxs-lookup"><span data-stu-id="f08e8-127">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="f08e8-128">En la **sección Tipo de objeto,** seleccione **Correo electrónico**.</span><span class="sxs-lookup"><span data-stu-id="f08e8-128">In the **Object type** section, select **Email**.</span></span> <span data-ttu-id="f08e8-129">En la **sección Formato de** envío, use una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="f08e8-129">In the **Submission format** section, use one of the following options:</span></span>

   - <span data-ttu-id="f08e8-130">**Id.** de mensaje de red: se trata de un valor GUID que está disponible en el encabezado **X-MS-Exchange-Organization-Network-Message-Id** del mensaje o en el encabezado **X-MS-Office365-Filtering-Correlation-Id** en mensajes en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="f08e8-130">**Network Message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message, or in the **X-MS-Office365-Filtering-Correlation-Id** header in quarantined messages.</span></span>

   - <span data-ttu-id="f08e8-131">**Archivo:** haga clic **en Elegir archivo**.</span><span class="sxs-lookup"><span data-stu-id="f08e8-131">**File**: Click **Choose file**.</span></span> <span data-ttu-id="f08e8-132">En el cuadro de diálogo que se abre, busque y seleccione el archivo .eml o .msg y, a continuación, haga clic **en Abrir**.</span><span class="sxs-lookup"><span data-stu-id="f08e8-132">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="f08e8-133">Los administradores con Defender para Office 365 Plan 1 o Plan 2 pueden enviar mensajes tan antiguos como 30 días.</span><span class="sxs-lookup"><span data-stu-id="f08e8-133">Admins with Defender for Office 365 Plan 1 or Plan 2 are able to submit messages as old as 30 days.</span></span> <span data-ttu-id="f08e8-134">Otros administradores solo podrán volver 7 días atrás.</span><span class="sxs-lookup"><span data-stu-id="f08e8-134">Other admins will only be able to go back 7 days.</span></span>

2. <span data-ttu-id="f08e8-135">En la **sección Destinatarios,** especifique uno o varios destinatarios con los que desea ejecutar una comprobación de directiva.</span><span class="sxs-lookup"><span data-stu-id="f08e8-135">In the **Recipients** section, specify one or more recipients that you would like to run a policy check against.</span></span> <span data-ttu-id="f08e8-136">La comprobación de directivas determinará si el correo electrónico omitió el examen debido a directivas de usuario u organización.</span><span class="sxs-lookup"><span data-stu-id="f08e8-136">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="f08e8-137">En la **sección Motivo del envío,** seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="f08e8-137">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="f08e8-138">**No se debería haber bloqueado**</span><span class="sxs-lookup"><span data-stu-id="f08e8-138">**Should not have been blocked**</span></span>

   - <span data-ttu-id="f08e8-139">**Debería haber sido bloqueado:** Seleccione **Correo no deseado,** **Suplantación** de identidad o **Malware.**</span><span class="sxs-lookup"><span data-stu-id="f08e8-139">**Should have been blocked**: Select **Spam**, **Phishing**, or **Malware**.</span></span> <span data-ttu-id="f08e8-140">Si no está seguro, use su mejor criterio.</span><span class="sxs-lookup"><span data-stu-id="f08e8-140">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="f08e8-141">Cuando haya terminado, haga clic en el **botón Enviar.**</span><span class="sxs-lookup"><span data-stu-id="f08e8-141">When you're finished, click the **Submit** button.</span></span>

   ![Ejemplo de envío de url](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="f08e8-143">Enviar una dirección URL sospechosa a Microsoft</span><span class="sxs-lookup"><span data-stu-id="f08e8-143">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="f08e8-144">En la **sección Tipo de objeto,** seleccione **Dirección URL**.</span><span class="sxs-lookup"><span data-stu-id="f08e8-144">In the **Object type** section, select **URL**.</span></span> <span data-ttu-id="f08e8-145">En el cuadro que aparece, escriba la dirección URL completa (por ejemplo, `https://www.fabrikam.com/marketing.html` ).</span><span class="sxs-lookup"><span data-stu-id="f08e8-145">In the box that appears, enter the full URL (for example, `https://www.fabrikam.com/marketing.html`).</span></span>

2. <span data-ttu-id="f08e8-146">En la **sección Motivo del envío,** seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="f08e8-146">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="f08e8-147">**No se debería haber bloqueado**</span><span class="sxs-lookup"><span data-stu-id="f08e8-147">**Should not have been blocked**</span></span>

   - <span data-ttu-id="f08e8-148">**Debería haber sido bloqueado:** Seleccione **Phishing** o **Malware**.</span><span class="sxs-lookup"><span data-stu-id="f08e8-148">**Should have been blocked**: Select **Phishing** or **Malware**.</span></span>

3. <span data-ttu-id="f08e8-149">Cuando haya terminado, haga clic en el **botón Enviar.**</span><span class="sxs-lookup"><span data-stu-id="f08e8-149">When you're finished, click the **Submit** button.</span></span>

   ![Ejemplo de envío de correo electrónico](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="f08e8-151">Enviar un archivo sospechoso a Microsoft</span><span class="sxs-lookup"><span data-stu-id="f08e8-151">Submit a suspected file to Microsoft</span></span>

1. <span data-ttu-id="f08e8-152">En la **sección Tipo de objeto,** seleccione **Datos adjuntos**.</span><span class="sxs-lookup"><span data-stu-id="f08e8-152">In the **Object type** section, select **Attachment**.</span></span>

2. <span data-ttu-id="f08e8-153">Haga clic **en Elegir archivo**.</span><span class="sxs-lookup"><span data-stu-id="f08e8-153">Click **Choose File**.</span></span> <span data-ttu-id="f08e8-154">En el cuadro de diálogo que se abre, busque y seleccione el archivo y, a continuación, haga clic en **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="f08e8-154">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="f08e8-155">En la **sección Motivo del envío,** seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="f08e8-155">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="f08e8-156">**No se debería haber bloqueado**</span><span class="sxs-lookup"><span data-stu-id="f08e8-156">**Should not have been blocked**</span></span>

   - <span data-ttu-id="f08e8-157">**Debería haber sido bloqueado:** **el malware** es la única opción y se selecciona automáticamente.</span><span class="sxs-lookup"><span data-stu-id="f08e8-157">**Should have been blocked**: **Malware** is the only choice, and is automatically selected..</span></span>

4. <span data-ttu-id="f08e8-158">Cuando haya terminado, haga clic en el **botón Enviar.**</span><span class="sxs-lookup"><span data-stu-id="f08e8-158">When you're finished, click the **Submit** button.</span></span>

   ![Ejemplo de envío de datos adjuntos](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a><span data-ttu-id="f08e8-160">Ver envíos de administrador</span><span class="sxs-lookup"><span data-stu-id="f08e8-160">View admin submissions</span></span>

<span data-ttu-id="f08e8-161">En el Centro de seguridad &  cumplimiento, vaya a \> **Envíos** de administración de amenazas , compruebe que está en la pestaña **Envíos** de administrador y, a continuación, haga clic en **Nuevo envío**.</span><span class="sxs-lookup"><span data-stu-id="f08e8-161">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="f08e8-162">Cerca de la parte superior de la página, puede escribir una fecha de inicio, una fecha de finalización y ( de forma predeterminada) puede filtrar por identificador de envío **(un** valor GUID que se asigna a cada envío) especificando un valor en el cuadro y haciendo clic en el botón Actualizar ![ ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="f08e8-162">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** (a GUID value that's assigned to every submission) by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="f08e8-163">Update</span><span class="sxs-lookup"><span data-stu-id="f08e8-163">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="f08e8-164">Para cambiar los criterios de filtro, haga clic en el botón **Identificador de** envío y elija uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="f08e8-164">To change the filter criteria, click the **Submission ID** button and choose one of the following values:</span></span>

- <span data-ttu-id="f08e8-165">**Sender**</span><span class="sxs-lookup"><span data-stu-id="f08e8-165">**Sender**</span></span>
- <span data-ttu-id="f08e8-166">**Asunto/DIRECCIÓN URL/Nombre de archivo**</span><span class="sxs-lookup"><span data-stu-id="f08e8-166">**Subject/URL/File name**</span></span>
- <span data-ttu-id="f08e8-167">**Enviado por**</span><span class="sxs-lookup"><span data-stu-id="f08e8-167">**Submitted by**</span></span>
- <span data-ttu-id="f08e8-168">**Tipo de envío**</span><span class="sxs-lookup"><span data-stu-id="f08e8-168">**Submission type**</span></span>
- <span data-ttu-id="f08e8-169">**Estado**</span><span class="sxs-lookup"><span data-stu-id="f08e8-169">**Status**</span></span>

![Opciones de filtro para envíos de administrador](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="f08e8-171">Para exportar los resultados, haga clic **en Exportar** cerca de la parte superior de la página y seleccione Datos **del gráfico** o **Tabla**.</span><span class="sxs-lookup"><span data-stu-id="f08e8-171">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="f08e8-172">En el cuadro de diálogo que aparece, guarde el archivo .csv.</span><span class="sxs-lookup"><span data-stu-id="f08e8-172">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="f08e8-173">Debajo del gráfico, hay tres pestañas: **Correo** electrónico (predeterminado), **DIRECCIÓN URL** y **Datos adjuntos**.</span><span class="sxs-lookup"><span data-stu-id="f08e8-173">Below the graph, there are three tabs: **Email** (default), **URL**, and **Attachment**.</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="f08e8-174">Ver envíos de correo electrónico de administrador</span><span class="sxs-lookup"><span data-stu-id="f08e8-174">View admin email submissions</span></span>

<span data-ttu-id="f08e8-175">Haga clic en **la pestaña Correo** electrónico.</span><span class="sxs-lookup"><span data-stu-id="f08e8-175">Click the **Email** tab.</span></span>

<span data-ttu-id="f08e8-176">Puede hacer clic en el **botón Opciones de columna** cerca de la parte inferior de la página para agregar o quitar columnas de la vista:</span><span class="sxs-lookup"><span data-stu-id="f08e8-176">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="f08e8-177">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="f08e8-177">**Date**</span></span>
- <span data-ttu-id="f08e8-178">**Identificador de envío:** valor GUID que se asigna a cada envío.</span><span class="sxs-lookup"><span data-stu-id="f08e8-178">**Submission ID**: A GUID value that's assigned to every submission.</span></span>
- <span data-ttu-id="f08e8-179">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f08e8-179">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="f08e8-180">**Asunto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f08e8-180">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="f08e8-181">**Sender**</span><span class="sxs-lookup"><span data-stu-id="f08e8-181">**Sender**</span></span>
- <span data-ttu-id="f08e8-182">**IP del remitente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f08e8-182">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="f08e8-183">**Tipo de envío**</span><span class="sxs-lookup"><span data-stu-id="f08e8-183">**Submission type**</span></span>
- <span data-ttu-id="f08e8-184">**Motivo de entrega**</span><span class="sxs-lookup"><span data-stu-id="f08e8-184">**Delivery reason**</span></span>
- <span data-ttu-id="f08e8-185">**Estado**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f08e8-185">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="f08e8-186"><sup>\*</sup> Si hace clic en este valor, se muestra información detallada en un menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="f08e8-186"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

#### <a name="admin-submission-rescan-details"></a><span data-ttu-id="f08e8-187">Detalles de reescaneo de envío de administrador</span><span class="sxs-lookup"><span data-stu-id="f08e8-187">Admin submission rescan details</span></span>

<span data-ttu-id="f08e8-188">Los mensajes que se envían en envíos de administración se examinan de nuevo y los resultados se muestran en el menú desplegable de detalles:</span><span class="sxs-lookup"><span data-stu-id="f08e8-188">Messages that are submitted in admin submissions are rescanned and results shown in the details flyout:</span></span>

- <span data-ttu-id="f08e8-189">Si hubo un error en la autenticación de correo electrónico del remitente en el momento de la entrega.</span><span class="sxs-lookup"><span data-stu-id="f08e8-189">If there was a failure in the sender's email authentication at the time of delivery.</span></span>
- <span data-ttu-id="f08e8-190">Información sobre los aciertos de directiva que puedan haber afectado o invalidado el veredicto de un mensaje.</span><span class="sxs-lookup"><span data-stu-id="f08e8-190">Information about any policy hits that could have affected or overridden the verdict of a message.</span></span>
- <span data-ttu-id="f08e8-191">Actualice los resultados de cancelación para ver si las direcciones URL o los archivos contenidos en el mensaje son malintencionados o no.</span><span class="sxs-lookup"><span data-stu-id="f08e8-191">Current detonation results to see if the URLs or files contained in the message were malicious or not.</span></span>
- <span data-ttu-id="f08e8-192">Comentarios de los calificadores.</span><span class="sxs-lookup"><span data-stu-id="f08e8-192">Feedback from graders.</span></span>

<span data-ttu-id="f08e8-193">Si se encontró una invalidación, se volverá a ejecutar una detección que se completará en unos minutos.</span><span class="sxs-lookup"><span data-stu-id="f08e8-193">If an override was found, the rescan should complete in several minutes.</span></span> <span data-ttu-id="f08e8-194">Si no hubo un problema en la autenticación o entrega de correo electrónico no se vio afectado por una invalidación, los comentarios de los calificadores podrían tardar hasta un día.</span><span class="sxs-lookup"><span data-stu-id="f08e8-194">If there wasn't a problem in email authentication or delivery wasn't affected by an override, then the feedback from graders could take up to a day.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="f08e8-195">Ver envíos de url de administrador</span><span class="sxs-lookup"><span data-stu-id="f08e8-195">View admin URL submissions</span></span>

<span data-ttu-id="f08e8-196">Haga clic en la **pestaña Dirección** URL.</span><span class="sxs-lookup"><span data-stu-id="f08e8-196">Click the **URL** tab.</span></span>

<span data-ttu-id="f08e8-197">Puede hacer clic en el **botón Opciones de columna** cerca de la parte inferior de la página para agregar o quitar columnas de la vista:</span><span class="sxs-lookup"><span data-stu-id="f08e8-197">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="f08e8-198">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="f08e8-198">**Date**</span></span>
- <span data-ttu-id="f08e8-199">**Identificador de envío**</span><span class="sxs-lookup"><span data-stu-id="f08e8-199">**Submission ID**</span></span>
- <span data-ttu-id="f08e8-200">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f08e8-200">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="f08e8-201">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f08e8-201">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="f08e8-202">**Tipo de envío**</span><span class="sxs-lookup"><span data-stu-id="f08e8-202">**Submission type**</span></span>
- <span data-ttu-id="f08e8-203">**Estado**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f08e8-203">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="f08e8-204"><sup>\*</sup> Si hace clic en este valor, se muestra información detallada en un menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="f08e8-204"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-attachment-submissions"></a><span data-ttu-id="f08e8-205">Ver envíos de datos adjuntos de administrador</span><span class="sxs-lookup"><span data-stu-id="f08e8-205">View admin attachment submissions</span></span>

<span data-ttu-id="f08e8-206">Haga clic en **la pestaña Datos** adjuntos.</span><span class="sxs-lookup"><span data-stu-id="f08e8-206">Click the **Attachments** tab.</span></span>

<span data-ttu-id="f08e8-207">Puede hacer clic en el **botón Opciones de columna** cerca de la parte inferior de la página para agregar o quitar columnas de la vista:</span><span class="sxs-lookup"><span data-stu-id="f08e8-207">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="f08e8-208">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="f08e8-208">**Date**</span></span>
- <span data-ttu-id="f08e8-209">**Identificador de envío**</span><span class="sxs-lookup"><span data-stu-id="f08e8-209">**Submission ID**</span></span>
- <span data-ttu-id="f08e8-210">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f08e8-210">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="f08e8-211">**Nombre de archivo**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f08e8-211">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="f08e8-212">**Tipo de envío**</span><span class="sxs-lookup"><span data-stu-id="f08e8-212">**Submission type**</span></span>
- <span data-ttu-id="f08e8-213">**Estado**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f08e8-213">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="f08e8-214"><sup>\*</sup> Si hace clic en este valor, se muestra información detallada en un menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="f08e8-214"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="f08e8-215">Ver envíos de usuario a Microsoft</span><span class="sxs-lookup"><span data-stu-id="f08e8-215">View user submissions to Microsoft</span></span>

<span data-ttu-id="f08e8-216">Si ha implementado el complemento Report [Message](enable-the-report-message-add-in.md), el complemento [Report Phishing](enable-the-report-phish-add-in.md)o los usuarios usan los informes integrados en Outlook [en la web,](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)puede ver qué usuarios están informando en la pestaña **Envíos** de usuario.</span><span class="sxs-lookup"><span data-stu-id="f08e8-216">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), the [Report Phishing add-in](enable-the-report-phish-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="f08e8-217">En el Centro de & cumplimiento, vaya a **Envíos de administración** \> **de amenazas**.</span><span class="sxs-lookup"><span data-stu-id="f08e8-217">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="f08e8-218">Seleccione la **pestaña Envíos de** usuario y, a continuación, haga clic **en Nuevo envío.**</span><span class="sxs-lookup"><span data-stu-id="f08e8-218">Select the **User submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="f08e8-219">Puede hacer clic en el **botón Opciones de columna** cerca de la parte inferior de la página para agregar o quitar columnas de la vista:</span><span class="sxs-lookup"><span data-stu-id="f08e8-219">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="f08e8-220">**Enviado en**</span><span class="sxs-lookup"><span data-stu-id="f08e8-220">**Submitted on**</span></span>
- <span data-ttu-id="f08e8-221">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f08e8-221">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="f08e8-222">**Asunto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f08e8-222">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="f08e8-223">**Sender**</span><span class="sxs-lookup"><span data-stu-id="f08e8-223">**Sender**</span></span>
- <span data-ttu-id="f08e8-224">**IP del remitente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f08e8-224">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="f08e8-225">**Tipo de envío**</span><span class="sxs-lookup"><span data-stu-id="f08e8-225">**Submission type**</span></span>

<span data-ttu-id="f08e8-226"><sup>\*</sup> Si hace clic en este valor, se muestra información detallada en un menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="f08e8-226"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="f08e8-227">Cerca de la parte superior de la página, puede escribir una fecha de  inicio, una fecha de finalización y , de forma predeterminada, puede filtrar por remitente especificando un valor en el cuadro y haciendo clic en el botón ![ Actualizar ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="f08e8-227">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="f08e8-228">Update</span><span class="sxs-lookup"><span data-stu-id="f08e8-228">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="f08e8-229">Para cambiar los criterios de filtro, haga clic en el **botón Remitente** y elija uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="f08e8-229">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="f08e8-230">**Dominio del remitente**</span><span class="sxs-lookup"><span data-stu-id="f08e8-230">**Sender domain**</span></span>
- <span data-ttu-id="f08e8-231">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="f08e8-231">**Subject**</span></span>
- <span data-ttu-id="f08e8-232">**Enviado por**</span><span class="sxs-lookup"><span data-stu-id="f08e8-232">**Submitted by**</span></span>
- <span data-ttu-id="f08e8-233">**Tipo de envío**</span><span class="sxs-lookup"><span data-stu-id="f08e8-233">**Submission type**</span></span>
- <span data-ttu-id="f08e8-234">**IP del remitente**</span><span class="sxs-lookup"><span data-stu-id="f08e8-234">**Sender IP**</span></span>

![Opciones de filtro para envíos de usuarios](../../media/user-submissions-filter-options.png)

<span data-ttu-id="f08e8-236">Para exportar los resultados, haga clic **en Exportar** cerca de la parte superior de la página y seleccione Datos **del gráfico** o **Tabla**.</span><span class="sxs-lookup"><span data-stu-id="f08e8-236">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="f08e8-237">En el cuadro de diálogo que aparece, guarde el archivo .csv.</span><span class="sxs-lookup"><span data-stu-id="f08e8-237">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="f08e8-238">Ver envíos de usuario al buzón personalizado</span><span class="sxs-lookup"><span data-stu-id="f08e8-238">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="f08e8-239">**Si** ha configurado un [buzón](user-submission.md) personalizado para recibir mensajes notificados por el usuario, puede ver y enviar también mensajes que se entregaron al buzón de informes.</span><span class="sxs-lookup"><span data-stu-id="f08e8-239">**If** you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="f08e8-240">En el Centro de & cumplimiento, vaya a **Envíos de administración** \> **de amenazas**.</span><span class="sxs-lookup"><span data-stu-id="f08e8-240">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="f08e8-241">Seleccione la **pestaña Buzón personalizado.**</span><span class="sxs-lookup"><span data-stu-id="f08e8-241">Select the **Custom mailbox** tab.</span></span>

<span data-ttu-id="f08e8-242">Puede hacer clic en el **botón Opciones de columna** cerca de la parte inferior de la página para agregar o quitar columnas de la vista:</span><span class="sxs-lookup"><span data-stu-id="f08e8-242">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="f08e8-243">**Enviado en**</span><span class="sxs-lookup"><span data-stu-id="f08e8-243">**Submitted on**</span></span>
- <span data-ttu-id="f08e8-244">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f08e8-244">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="f08e8-245">**Asunto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f08e8-245">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="f08e8-246">**Sender**</span><span class="sxs-lookup"><span data-stu-id="f08e8-246">**Sender**</span></span>
- <span data-ttu-id="f08e8-247">**IP del remitente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f08e8-247">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="f08e8-248">**Tipo de envío**</span><span class="sxs-lookup"><span data-stu-id="f08e8-248">**Submission type**</span></span>

<span data-ttu-id="f08e8-249">Cerca de la parte superior de la página, puede escribir una fecha de inicio, una fecha de finalización y puede filtrar por **Enviado** especificando un valor en el cuadro y haciendo clic en el botón ![ Actualizar ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="f08e8-249">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="f08e8-250">Update</span><span class="sxs-lookup"><span data-stu-id="f08e8-250">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="f08e8-251">Para exportar los resultados, haga clic **en Exportar** cerca de la parte superior de la página y seleccione Datos **del gráfico** o **Tabla**.</span><span class="sxs-lookup"><span data-stu-id="f08e8-251">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="f08e8-252">En el cuadro de diálogo que aparece, guarde el archivo .csv.</span><span class="sxs-lookup"><span data-stu-id="f08e8-252">In the dialog that appears, save the .csv file.</span></span>

## <a name="undo-user-submissions"></a><span data-ttu-id="f08e8-253">Deshacer envíos de usuarios</span><span class="sxs-lookup"><span data-stu-id="f08e8-253">Undo user submissions</span></span>

<span data-ttu-id="f08e8-254">Una vez que un usuario envía un correo electrónico sospechoso al buzón personalizado, el usuario y el administrador no tienen ninguna opción para deshacer el envío.</span><span class="sxs-lookup"><span data-stu-id="f08e8-254">Once a user submits a suspicious email to the custom mailbox, the user and admin don't have an option to undo the submission.</span></span> <span data-ttu-id="f08e8-255">Si el usuario desea recuperar el correo electrónico, estará disponible para su recuperación en las carpetas Elementos eliminados o Correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="f08e8-255">If the user would like to recover the email, it will be available for recovery in the Deleted Items or Junk Email folders.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="f08e8-256">Enviar mensajes a Microsoft desde el buzón personalizado</span><span class="sxs-lookup"><span data-stu-id="f08e8-256">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="f08e8-257">Si ha configurado el buzón personalizado para interceptar mensajes notificados por el usuario sin enviar los mensajes a Microsoft, puede buscar y enviar mensajes específicos a Microsoft para su análisis.</span><span class="sxs-lookup"><span data-stu-id="f08e8-257">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="f08e8-258">Esto mueve de forma eficaz un envío de usuario a un envío de administrador.</span><span class="sxs-lookup"><span data-stu-id="f08e8-258">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="f08e8-259">En la **pestaña Buzón personalizado,** seleccione un  mensaje en la lista, haga clic en el botón Acción y realice una de las siguientes selecciones:</span><span class="sxs-lookup"><span data-stu-id="f08e8-259">On the **Custom mailbox** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="f08e8-260">**Informe limpio**</span><span class="sxs-lookup"><span data-stu-id="f08e8-260">**Report clean**</span></span>
- <span data-ttu-id="f08e8-261">**Report phishing**</span><span class="sxs-lookup"><span data-stu-id="f08e8-261">**Report phishing**</span></span>
- <span data-ttu-id="f08e8-262">**Informar de malware**</span><span class="sxs-lookup"><span data-stu-id="f08e8-262">**Report malware**</span></span>
- <span data-ttu-id="f08e8-263">**Notificar correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="f08e8-263">**Report spam**</span></span>

![Opciones en el botón Acción](../../media/user-submission-custom-mailbox-action-button.png)