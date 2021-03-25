---
title: Ver informes de seguridad de correo electrónico en el Centro de seguridad y cumplimiento
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 3a137e28-1174-42d5-99af-f18868b43e86
ms.collection:
- M365-security-compliance
description: Obtenga información sobre cómo buscar y usar informes de seguridad de correo electrónico para su organización. Los informes de seguridad de correo electrónico están disponibles en el Centro de seguridad & cumplimiento.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5d9f6d12fef8a2ef6241fbbd5e0e2a980284e9cc
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2021
ms.locfileid: "51207259"
---
# <a name="view-email-security-reports-in-the-security--compliance-center"></a><span data-ttu-id="754d9-104">Ver informes de seguridad de correo electrónico en el Centro de seguridad y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="754d9-104">View email security reports in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="754d9-105">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="754d9-105">**Applies to**</span></span>
- [<span data-ttu-id="754d9-106">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="754d9-106">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="754d9-107">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="754d9-107">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="754d9-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="754d9-108">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="754d9-109">Hay varios informes disponibles en el Centro de seguridad y cumplimiento de & para ayudarle [a](https://protection.office.com) ver cómo las características de seguridad del correo electrónico, como el correo no deseado, antimalware y las características de cifrado en Microsoft 365 protegen su organización.</span><span class="sxs-lookup"><span data-stu-id="754d9-109">A variety of reports are available in the [Security & Compliance Center](https://protection.office.com) to help you see how email security features, such as anti-spam, anti-malware, and encryption features in Microsoft 365 are protecting your organization.</span></span> <span data-ttu-id="754d9-110">Si tiene los permisos [necesarios,](#what-permissions-are-needed-to-view-these-reports)puede ver estos informes en el Centro de seguridad & cumplimiento yendo al **Panel de** \> **informes**.</span><span class="sxs-lookup"><span data-stu-id="754d9-110">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the Security & Compliance Center by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="754d9-111">Para ir directamente al panel Informes, abra <https://protection.office.com/insightdashboard> .</span><span class="sxs-lookup"><span data-stu-id="754d9-111">To go directly to the Reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![Panel de informes en el Centro de seguridad & cumplimiento](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="compromised-users-report"></a><span data-ttu-id="754d9-113">Informe de usuarios comprometidos</span><span class="sxs-lookup"><span data-stu-id="754d9-113">Compromised users report</span></span>

> [!NOTE]
> <span data-ttu-id="754d9-114">Este informe está disponible en organizaciones de Microsoft 365 con buzones de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="754d9-114">This report is available in Microsoft 365 organizations with Exchange Online mailboxes.</span></span> <span data-ttu-id="754d9-115">No está disponible en organizaciones independientes de Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="754d9-115">It's not available in standalone Exchange Online Protection (EOP) organizations.</span></span>

<span data-ttu-id="754d9-116">El **informe Usuarios comprometidos** muestra el número de  cuentas  de usuario que se marcaron como Sospechosas o Restringidas en los últimos 7 días.</span><span class="sxs-lookup"><span data-stu-id="754d9-116">The **Compromised users** report shows shows the number of user accounts that were marked as **Suspicious** or **Restricted** within the last 7 days.</span></span> <span data-ttu-id="754d9-117">Las cuentas en cualquiera de estos estados son problemáticas o incluso están en peligro.</span><span class="sxs-lookup"><span data-stu-id="754d9-117">Accounts in either of these states are problematic or even compromised.</span></span> <span data-ttu-id="754d9-118">Con el uso frecuente, puede usar el informe para detectar picos e incluso tendencias en cuentas sospechosas o restringidas.</span><span class="sxs-lookup"><span data-stu-id="754d9-118">With frequent use, you can use the report to spot spikes, and even trends, in suspicious or restricted accounts.</span></span> <span data-ttu-id="754d9-119">Para obtener más información acerca de los usuarios en peligro, vea [Responder a una cuenta de correo electrónico comprometida.](responding-to-a-compromised-email-account.md)</span><span class="sxs-lookup"><span data-stu-id="754d9-119">For more information about compromised users, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

![Widget Usuarios comprometidos en el panel Informes](../../media/compromised-users-report-widget.png)

<span data-ttu-id="754d9-121">La vista de agregado muestra los datos de los últimos 90 días y la vista de detalles muestra los datos de los últimos 30 días.</span><span class="sxs-lookup"><span data-stu-id="754d9-121">The aggregate view shows data for the last 90 days and the detail view shows data for the last 30 days.</span></span>

<span data-ttu-id="754d9-122">Para ver el informe, abra el Centro de  [seguridad & cumplimiento,](https://protection.office.com)vaya al Panel de informes y seleccione \>  **Usuarios comprometidos.**</span><span class="sxs-lookup"><span data-stu-id="754d9-122">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Compromised users**.</span></span> <span data-ttu-id="754d9-123">Para ir directamente al informe, abra <https://protection.office.com/reportv2?id=CompromisedUsers> .</span><span class="sxs-lookup"><span data-stu-id="754d9-123">To go directly to the report, open <https://protection.office.com/reportv2?id=CompromisedUsers>.</span></span>

<span data-ttu-id="754d9-124">Puede filtrar tanto el gráfico como la tabla de detalles haciendo clic en **Filtros** y seleccionando uno o varios de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="754d9-124">You can filter both the chart and the details table by clicking **Filters** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="754d9-125">**Fecha de inicio** y **fecha de finalización**</span><span class="sxs-lookup"><span data-stu-id="754d9-125">**Start date** and **End date**</span></span>

- <span data-ttu-id="754d9-126">**Sospechoso:** la cuenta de usuario ha enviado un correo electrónico sospechoso y corre el riesgo de que se le restringa el envío de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="754d9-126">**Suspicious**: The user account has sent suspicious email and is at risk of being restricted from sending email.</span></span>

- <span data-ttu-id="754d9-127">**Restringido:** la cuenta de usuario se ha restringido para enviar correo electrónico debido a patrones altamente sospechosos.</span><span class="sxs-lookup"><span data-stu-id="754d9-127">**Restricted**: The user account has been restricted from sending email due to highly suspicious patterns.</span></span>

![Vista Informe en el informe usuarios comprometidos](../../media/compromised-users-report-activity-view.png)

<span data-ttu-id="754d9-129">Si hace clic **en Ver tabla de detalles,** puede ver los siguientes detalles:</span><span class="sxs-lookup"><span data-stu-id="754d9-129">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="754d9-130">**Tiempo de creación**</span><span class="sxs-lookup"><span data-stu-id="754d9-130">**Creation time**</span></span>
- <span data-ttu-id="754d9-131">**Nombre de usuario**</span><span class="sxs-lookup"><span data-stu-id="754d9-131">**User ID**</span></span>
- <span data-ttu-id="754d9-132">**Acción**</span><span class="sxs-lookup"><span data-stu-id="754d9-132">**Action**</span></span>

<span data-ttu-id="754d9-133">Para volver a la vista informe, haga clic **en Ver informe**.</span><span class="sxs-lookup"><span data-stu-id="754d9-133">To go back to the report view, click **View report**.</span></span>

## <a name="encryption-report"></a><span data-ttu-id="754d9-134">Informe de cifrado</span><span class="sxs-lookup"><span data-stu-id="754d9-134">Encryption report</span></span>

<span data-ttu-id="754d9-135">El **informe de cifrado** está disponible en EOP (suscripciones con buzones en Exchange Online o EOP independiente sin buzones de Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="754d9-135">The **Encryption report** is available in EOP (subscriptions with mailboxes in Exchange Online or standalone EOP without Exchange Online mailboxes).</span></span> <span data-ttu-id="754d9-136">El equipo de seguridad de su organización puede usar la información de este informe para identificar patrones y aplicar o ajustar proactivamente directivas para mensajes de correo electrónico confidenciales.</span><span class="sxs-lookup"><span data-stu-id="754d9-136">Your organization's security team can use information in this report to identify patterns and proactively apply or adjust policies for sensitive email messages.</span></span> <span data-ttu-id="754d9-137">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="754d9-137">For example:</span></span>

- <span data-ttu-id="754d9-138">Si ve un gran número de mensajes de correo electrónico cifrados por los usuarios, es posible que desee agregar una directiva de cifrado para automatizar el cifrado en determinados casos de uso.</span><span class="sxs-lookup"><span data-stu-id="754d9-138">If you see a high number of email messages encrypted by users, you might want to add an encryption policy to automate encryption for certain use cases.</span></span> <span data-ttu-id="754d9-139">Para obtener más información, vea Definir reglas de flujo de correo para cifrar mensajes de correo [electrónico en Microsoft 365](../../compliance/define-mail-flow-rules-to-encrypt-email.md).</span><span class="sxs-lookup"><span data-stu-id="754d9-139">For more information, see [Define mail flow rules to encrypt email messages in Microsoft 365](../../compliance/define-mail-flow-rules-to-encrypt-email.md).</span></span>

- <span data-ttu-id="754d9-140">Si tiene varias plantillas de cifrado disponibles, pero nadie las usa, puede explorar si los usuarios necesitan formación en características.</span><span class="sxs-lookup"><span data-stu-id="754d9-140">If you have a number of encryption templates available but no one is using them, you might explore whether users need feature training.</span></span>

<span data-ttu-id="754d9-141">La vista de agregado permite filtrar durante los últimos 90 días, mientras que la vista de detalles permite filtrar durante 10 días.</span><span class="sxs-lookup"><span data-stu-id="754d9-141">The aggregate view allows filtering for the last 90 days, while the detail view allows filtering for 10 days.</span></span>

<span data-ttu-id="754d9-142">Para ver el informe, abra el Centro de  [seguridad & cumplimiento,](https://protection.office.com)vaya al Panel \> **de informes** y seleccione **Informe de cifrado**.</span><span class="sxs-lookup"><span data-stu-id="754d9-142">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Encryption report**.</span></span> <span data-ttu-id="754d9-143">Para ir directamente al informe, abra <https://protection.office.com/reportv2?id=EncryptionReport> .</span><span class="sxs-lookup"><span data-stu-id="754d9-143">To go directly to the report, open <https://protection.office.com/reportv2?id=EncryptionReport>.</span></span>

<span data-ttu-id="754d9-144">Para obtener más información sobre el cifrado, vea [Cifrado de correo electrónico en Microsoft 365](../../compliance/email-encryption.md).</span><span class="sxs-lookup"><span data-stu-id="754d9-144">To learn more about encryption, see [Email encryption in Microsoft 365](../../compliance/email-encryption.md).</span></span>

### <a name="report-view-for-the-encryption-report"></a><span data-ttu-id="754d9-145">Vista Informe para el informe de cifrado</span><span class="sxs-lookup"><span data-stu-id="754d9-145">Report view for the Encryption report</span></span>

<span data-ttu-id="754d9-146">Puede usar los siguientes filtros en el gráfico:</span><span class="sxs-lookup"><span data-stu-id="754d9-146">You can use the following filters on the chart:</span></span>

- <span data-ttu-id="754d9-147">**Ver datos por: Informe de cifrado de** mensajes y Dividir **por: Método de cifrado:** Los siguientes métodos de cifrado están disponibles:</span><span class="sxs-lookup"><span data-stu-id="754d9-147">**View data by: Message Encryption Report** and **Break down by: Encryption method**: The following encryption methods are available:</span></span>

  - <span data-ttu-id="754d9-148">**Cifrado por usuario**</span><span class="sxs-lookup"><span data-stu-id="754d9-148">**Encryption by user**</span></span>
  - <span data-ttu-id="754d9-149">**Cifrado por directiva**</span><span class="sxs-lookup"><span data-stu-id="754d9-149">**Encryption by policy**</span></span>

  <span data-ttu-id="754d9-150">Si hace clic **en Filtros,** puede modificar el gráfico con los filtros siguientes:</span><span class="sxs-lookup"><span data-stu-id="754d9-150">If you click **Filters**, you can modify the chart with the following filters:</span></span>

  - <span data-ttu-id="754d9-151">**Fecha de inicio** y **fecha de finalización**</span><span class="sxs-lookup"><span data-stu-id="754d9-151">**Start date** and **End date**</span></span>
  - <span data-ttu-id="754d9-152">Método de cifrado.</span><span class="sxs-lookup"><span data-stu-id="754d9-152">Encryption method.</span></span>
  - <span data-ttu-id="754d9-153">Plantilla de cifrado.</span><span class="sxs-lookup"><span data-stu-id="754d9-153">Encryption template.</span></span>

- <span data-ttu-id="754d9-154">**Ver datos por: Informe de cifrado de** mensajes y Dividir **por: Plantilla de cifrado**: Los siguientes métodos de cifrado están disponibles:</span><span class="sxs-lookup"><span data-stu-id="754d9-154">**View data by: Message Encryption Report** and **Break down by: Encryption template**: The following encryption methods are available:</span></span>

  - <span data-ttu-id="754d9-155">**No reenviar**</span><span class="sxs-lookup"><span data-stu-id="754d9-155">**Do not forward**</span></span>
  - <span data-ttu-id="754d9-156">**Cifrar solo**</span><span class="sxs-lookup"><span data-stu-id="754d9-156">**Encrypt only**</span></span>
  - <span data-ttu-id="754d9-157">**OME anterior**</span><span class="sxs-lookup"><span data-stu-id="754d9-157">**OME previous**</span></span>
  - <span data-ttu-id="754d9-158">**Personalizados**</span><span class="sxs-lookup"><span data-stu-id="754d9-158">**Custom**</span></span>

  <span data-ttu-id="754d9-159">Si hace clic **en Filtros,** puede modificar el gráfico con los filtros siguientes:</span><span class="sxs-lookup"><span data-stu-id="754d9-159">If you click **Filters**, you can modify the chart with the following filters:</span></span>

  - <span data-ttu-id="754d9-160">**Fecha de inicio** y **fecha de finalización**</span><span class="sxs-lookup"><span data-stu-id="754d9-160">**Start date** and **End date**</span></span>
  - <span data-ttu-id="754d9-161">Método de cifrado</span><span class="sxs-lookup"><span data-stu-id="754d9-161">Encryption method</span></span>
  - <span data-ttu-id="754d9-162">Plantilla de cifrado</span><span class="sxs-lookup"><span data-stu-id="754d9-162">Encryption template</span></span>

- <span data-ttu-id="754d9-163">**Ver datos por: Principales 5** dominios de destinatarios: esta vista muestra un gráfico circular con recuentos de mensajes enviados para los 5 dominios de destinatarios principales.</span><span class="sxs-lookup"><span data-stu-id="754d9-163">**View data by: Top 5 recipient domains**: This view shows a pie chart with sent message counts for the top 5 recipient domains.</span></span>

  <span data-ttu-id="754d9-164">Si hace clic **en Filtros,** puede seleccionar una **fecha de inicio y** una fecha de **finalización.**</span><span class="sxs-lookup"><span data-stu-id="754d9-164">If you click **Filters**, you can select a **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-encryption-report"></a><span data-ttu-id="754d9-165">Vista de tabla Detalles del informe de cifrado</span><span class="sxs-lookup"><span data-stu-id="754d9-165">Details table view for the Encryption report</span></span>

<span data-ttu-id="754d9-166">Si hace clic **en Ver tabla de detalles,** la información que se muestra depende del gráfico que estaba mirando:</span><span class="sxs-lookup"><span data-stu-id="754d9-166">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="754d9-167">**Dividir por: Método de cifrado o** Dividir **por: Plantilla de cifrado**: Se muestra la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="754d9-167">**Break down by: Encryption method** or **Break down by: Encryption template**: The following information is shown:</span></span>

  - <span data-ttu-id="754d9-168">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="754d9-168">**Date**</span></span>
  - <span data-ttu-id="754d9-169">**Dirección del remitente**</span><span class="sxs-lookup"><span data-stu-id="754d9-169">**Sender address**</span></span>
  - <span data-ttu-id="754d9-170">**Plantilla de cifrado**</span><span class="sxs-lookup"><span data-stu-id="754d9-170">**Encryption template**</span></span>
  - <span data-ttu-id="754d9-171">**Método de cifrado**</span><span class="sxs-lookup"><span data-stu-id="754d9-171">**Encryption method**</span></span>
  - <span data-ttu-id="754d9-172">**Dirección de destinatario**</span><span class="sxs-lookup"><span data-stu-id="754d9-172">**Recipient address**</span></span>
  - <span data-ttu-id="754d9-173">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="754d9-173">**Subject**</span></span>

- <span data-ttu-id="754d9-174">**Ver datos por: Dominios de destinatarios principales:**</span><span class="sxs-lookup"><span data-stu-id="754d9-174">**View data by: Top 5 recipient domains**:</span></span>

  - <span data-ttu-id="754d9-175">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="754d9-175">**Date**</span></span>
  - <span data-ttu-id="754d9-176">**Dominio del destinatario**</span><span class="sxs-lookup"><span data-stu-id="754d9-176">**Recipient domain**</span></span>
  - <span data-ttu-id="754d9-177">**Recuento de mensajes**</span><span class="sxs-lookup"><span data-stu-id="754d9-177">**Message count**</span></span>

<span data-ttu-id="754d9-178">Si hace clic **en Filtros en** una vista de tabla de detalles, puede modificar los resultados con los filtros siguientes:</span><span class="sxs-lookup"><span data-stu-id="754d9-178">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="754d9-179">**Fecha de inicio** y **fecha de finalización**</span><span class="sxs-lookup"><span data-stu-id="754d9-179">**Start date** and **End date**</span></span>
- <span data-ttu-id="754d9-180">Método de cifrado</span><span class="sxs-lookup"><span data-stu-id="754d9-180">Encryption method</span></span>
- <span data-ttu-id="754d9-181">Plantilla de cifrado</span><span class="sxs-lookup"><span data-stu-id="754d9-181">Encryption template</span></span>

<span data-ttu-id="754d9-182">Para volver a la vista informe, haga clic **en Ver informe**.</span><span class="sxs-lookup"><span data-stu-id="754d9-182">To go back to the report view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="754d9-183">Informe de estado de flujo de correo</span><span class="sxs-lookup"><span data-stu-id="754d9-183">Mailflow status report</span></span>

<span data-ttu-id="754d9-184">El **informe de estado de flujo de** correo contiene información sobre malware, correo no deseado, phishing y mensajes bloqueados perimetrales.</span><span class="sxs-lookup"><span data-stu-id="754d9-184">The **Mailflow status report** contains information about malware, spam, phishing and edge blocked messages.</span></span> <span data-ttu-id="754d9-185">Para obtener más información, vea [Mailflow status report](view-mail-flow-reports.md#mailflow-status-report).</span><span class="sxs-lookup"><span data-stu-id="754d9-185">For more details, see [Mailflow status report](view-mail-flow-reports.md#mailflow-status-report).</span></span>

## <a name="malware-detections-in-email-report"></a><span data-ttu-id="754d9-186">Detecciones de malware en el informe de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="754d9-186">Malware detections in email report</span></span>

<span data-ttu-id="754d9-187">El **informe Detecciones de** malware en el correo electrónico muestra información sobre detecciones de malware en mensajes de correo electrónico entrantes y salientes (malware detectado por Exchange Online Protection o EOP).</span><span class="sxs-lookup"><span data-stu-id="754d9-187">The **Malware detections in email** report shows information about malware detections in incoming and outgoing email messages (malware detected by Exchange Online Protection or EOP).</span></span> <span data-ttu-id="754d9-188">Para obtener más información acerca de la protección contra malware en EOP, vea [Protección contra malware en EOP](anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="754d9-188">For more information about malware protection in EOP, see [Anti-malware protection in EOP](anti-malware-protection.md).</span></span>

 <span data-ttu-id="754d9-189">El filtro de vista agregado permite 90 días, mientras que el filtro de tabla de detalles solo permite 10 días.</span><span class="sxs-lookup"><span data-stu-id="754d9-189">The aggregate view filter allows for 90 days, while the details table filter only allows for 10 days.</span></span>

<span data-ttu-id="754d9-190">Para ver el informe, abra el Centro de  [seguridad y & cumplimiento,](https://protection.office.com)vaya al Panel de informes y seleccione Detecciones de \>  malware en el **correo electrónico**.</span><span class="sxs-lookup"><span data-stu-id="754d9-190">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Malware detections in email**.</span></span> <span data-ttu-id="754d9-191">Para ir directamente al informe, abra <https://protection.office.com/reportv2?id=MalwareDetections> .</span><span class="sxs-lookup"><span data-stu-id="754d9-191">To go directly to the report, open <https://protection.office.com/reportv2?id=MalwareDetections>.</span></span>

![Detecciones de malware en el widget de correo electrónico en el panel Informes](../../media/malware-detections-widget.png)

<span data-ttu-id="754d9-193">Puede filtrar tanto el gráfico como la tabla de detalles haciendo clic **en Filtros** y seleccionando:</span><span class="sxs-lookup"><span data-stu-id="754d9-193">You can filter both the chart and the details table by clicking **Filters** and selecting:</span></span>

- <span data-ttu-id="754d9-194">**Fecha de inicio** y **fecha de finalización**</span><span class="sxs-lookup"><span data-stu-id="754d9-194">**Start date** and **End date**</span></span>
- <span data-ttu-id="754d9-195">**Entrada**</span><span class="sxs-lookup"><span data-stu-id="754d9-195">**Inbound**</span></span>
- <span data-ttu-id="754d9-196">**Saliente**</span><span class="sxs-lookup"><span data-stu-id="754d9-196">**Outbound**</span></span>

![Vista Informe en el informe de detección de malware en el correo electrónico](../../media/malware-detections-report-view.png)

<span data-ttu-id="754d9-198">Si hace clic **en Ver tabla de detalles,** puede ver los siguientes detalles:</span><span class="sxs-lookup"><span data-stu-id="754d9-198">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="754d9-199">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="754d9-199">**Date**</span></span>
- <span data-ttu-id="754d9-200">**Dirección del remitente**</span><span class="sxs-lookup"><span data-stu-id="754d9-200">**Sender address**</span></span>
- <span data-ttu-id="754d9-201">**Dirección de destinatario**</span><span class="sxs-lookup"><span data-stu-id="754d9-201">**Recipient address**</span></span>
- <span data-ttu-id="754d9-202">**Id. de** mensaje: disponible en el **campo de encabezado Id. de** mensaje en el encabezado del mensaje y debe ser único.</span><span class="sxs-lookup"><span data-stu-id="754d9-202">**Message ID**: Available in the **Message-ID** header field in the message header and should be unique.</span></span> <span data-ttu-id="754d9-203">Un valor de ejemplo es `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (tenga en cuenta los corchetes angulares).</span><span class="sxs-lookup"><span data-stu-id="754d9-203">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
- <span data-ttu-id="754d9-204">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="754d9-204">**Subject**</span></span>
- <span data-ttu-id="754d9-205">**Filename**</span><span class="sxs-lookup"><span data-stu-id="754d9-205">**Filename**</span></span>
- <span data-ttu-id="754d9-206">**Nombre de malware**</span><span class="sxs-lookup"><span data-stu-id="754d9-206">**Malware name**</span></span>

<span data-ttu-id="754d9-207">Para volver a la vista informe, haga clic **en Ver informe**.</span><span class="sxs-lookup"><span data-stu-id="754d9-207">To go back to the report view, click **View report**.</span></span>

## <a name="mail-latency-report"></a><span data-ttu-id="754d9-208">Informe de latencia de correo</span><span class="sxs-lookup"><span data-stu-id="754d9-208">Mail latency report</span></span>

<span data-ttu-id="754d9-209">El **informe de latencia de correo** contiene información sobre la latencia de entrega y detonación de correo experimentada en su organización.</span><span class="sxs-lookup"><span data-stu-id="754d9-209">The **Mail latency report** contains information on the mail delivery and detonation latency experienced within your organization.</span></span> <span data-ttu-id="754d9-210">Para obtener más información, vea [Informe de latencia de correo](view-reports-for-mdo.md#mail-latency-report).</span><span class="sxs-lookup"><span data-stu-id="754d9-210">For more information, see [Mail latency report](view-reports-for-mdo.md#mail-latency-report).</span></span>

## <a name="sent-and-received-email-report"></a><span data-ttu-id="754d9-211">Informe de correo electrónico enviado y recibido</span><span class="sxs-lookup"><span data-stu-id="754d9-211">Sent and received email report</span></span>

<span data-ttu-id="754d9-212">El **informe de correo electrónico** enviado y recibido contiene información sobre malware, correo no deseado, reglas de flujo de correo (también conocidas como reglas de transporte) y detecciones avanzadas de malware después de que el correo electrónico entre en el servicio.</span><span class="sxs-lookup"><span data-stu-id="754d9-212">The **Sent and received email** report contains information about malware, spam, mail flow rules (also known as transport rules), and advanced malware detections after email enters the service.</span></span> <span data-ttu-id="754d9-213">Para obtener más información, vea [Sent and received email report](view-mail-flow-reports.md#sent-and-received-email-report).</span><span class="sxs-lookup"><span data-stu-id="754d9-213">For more information, see [Sent and received email report](view-mail-flow-reports.md#sent-and-received-email-report).</span></span>

## <a name="spam-detections-report"></a><span data-ttu-id="754d9-214">Informe de detecciones de correo no deseado</span><span class="sxs-lookup"><span data-stu-id="754d9-214">Spam detections report</span></span>

<span data-ttu-id="754d9-215">El **informe Detecciones de** correo no deseado muestra los mensajes de correo electrónico no deseado bloqueados por EOP.</span><span class="sxs-lookup"><span data-stu-id="754d9-215">The **Spam detections** report shows spam email messages that were blocked by EOP.</span></span> <span data-ttu-id="754d9-216">Los mensajes se cuentan individualmente, no por destinatario.</span><span class="sxs-lookup"><span data-stu-id="754d9-216">Messages are counted individually, not per recipient.</span></span> <span data-ttu-id="754d9-217">Por ejemplo, si el mismo mensaje de correo no deseado se envió a 100 destinatarios de la organización, cuenta como un mensaje.</span><span class="sxs-lookup"><span data-stu-id="754d9-217">For example, if the same spam message was sent to 100 recipients in your organization, it counts as one message.</span></span>

<span data-ttu-id="754d9-218">La vista de agregado permite el filtrado de 90 días, mientras que la tabla de detalles permite el filtrado de 10 días.</span><span class="sxs-lookup"><span data-stu-id="754d9-218">The aggregate view allows for 90 days filtering, while the details table allows for 10 days filtering.</span></span>

<span data-ttu-id="754d9-219">Para ver el informe, abra el Centro de  [seguridad & cumplimiento,](https://protection.office.com)vaya al Panel de informes y seleccione Detecciones de correo \>  no **deseado.**</span><span class="sxs-lookup"><span data-stu-id="754d9-219">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Spam detections**.</span></span> <span data-ttu-id="754d9-220">Para ir directamente al informe, abra <https://protection.office.com/reportv2?id=SpamDetections> .</span><span class="sxs-lookup"><span data-stu-id="754d9-220">To go directly to the report, open <https://protection.office.com/reportv2?id=SpamDetections>.</span></span>

![Widget de detecciones de correo no deseado en el panel Informes](../../media/spam-detections-report-widget.png)

<span data-ttu-id="754d9-222">Para obtener más información acerca de la protección contra correo no deseado, vea [Protección contra correo no deseado en EOP](anti-spam-protection.md).</span><span class="sxs-lookup"><span data-stu-id="754d9-222">For more information about anti-spam protection, see [Anti-spam protection in EOP](anti-spam-protection.md).</span></span>

### <a name="report-view-for-the-spam-detections-report"></a><span data-ttu-id="754d9-223">Vista Informe para el informe de detecciones de correo no deseado</span><span class="sxs-lookup"><span data-stu-id="754d9-223">Report view for the Spam detections report</span></span>

<span data-ttu-id="754d9-224">Los gráficos siguientes están disponibles en la vista informe:</span><span class="sxs-lookup"><span data-stu-id="754d9-224">The following charts are available in the report view:</span></span>

- <span data-ttu-id="754d9-225">**Dividir por: Acción:** se muestran los siguientes tipos de eventos:</span><span class="sxs-lookup"><span data-stu-id="754d9-225">**Break down by: Action**: The following event types are shown:</span></span>

  - <span data-ttu-id="754d9-226">**Filtrado de contenido de correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="754d9-226">**Spam content filtered**</span></span>
  - <span data-ttu-id="754d9-227">**Bloqueo ip de correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="754d9-227">**Spam IP block**</span></span>
  - <span data-ttu-id="754d9-228">**Bloqueo de sobre de correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="754d9-228">**Spam envelope block**</span></span>
  - <span data-ttu-id="754d9-229">**Filtro DBEB de correo no** deseado: bloqueo perimetral basado en directorios (DBEB)</span><span class="sxs-lookup"><span data-stu-id="754d9-229">**Spam DBEB filter**: Directory based edge blocking (DBEB)</span></span>

  <span data-ttu-id="754d9-230">Cuando mantiene el mouse sobre un día (punto de datos) en el gráfico, puede ver cuántos elementos se bloquearon ese día, así como cómo se clasifican esos elementos.</span><span class="sxs-lookup"><span data-stu-id="754d9-230">When you hover over a day (data point) in the chart, you can see how many items were blocked that day, as well as how those items are categorized.</span></span>

  ![Vista Acción en el informe de detecciones de correo no deseado](../../media/spam-detections-report-action-view.png)

- <span data-ttu-id="754d9-232">**Dividir por: Dirección:** se muestran las siguientes direcciones:</span><span class="sxs-lookup"><span data-stu-id="754d9-232">**Break down by: Direction**: The following directions are shown:</span></span>

  - <span data-ttu-id="754d9-233">**Entrada**</span><span class="sxs-lookup"><span data-stu-id="754d9-233">**Inbound**</span></span>
  - <span data-ttu-id="754d9-234">**Saliente**</span><span class="sxs-lookup"><span data-stu-id="754d9-234">**Outbound**</span></span>

  ![Vista Dirección en el informe de detecciones de correo no deseado](../../media/spam-detections-report-direction-view.png)

<span data-ttu-id="754d9-236">Si hace clic **en Filtros** en una vista de informe, puede modificar los resultados con los filtros siguientes:</span><span class="sxs-lookup"><span data-stu-id="754d9-236">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="754d9-237">**Fecha de inicio** y **fecha de finalización**</span><span class="sxs-lookup"><span data-stu-id="754d9-237">**Start date** and **End date**</span></span>
- <span data-ttu-id="754d9-238">Valores de dirección</span><span class="sxs-lookup"><span data-stu-id="754d9-238">Direction values</span></span>
- <span data-ttu-id="754d9-239">Valores de tipo de evento</span><span class="sxs-lookup"><span data-stu-id="754d9-239">Event type values</span></span>

### <a name="details-table-view-for-the-spam-detections-report"></a><span data-ttu-id="754d9-240">Vista de tabla Detalles del informe de detecciones de correo no deseado</span><span class="sxs-lookup"><span data-stu-id="754d9-240">Details table view for the Spam detections report</span></span>

<span data-ttu-id="754d9-241">Si hace clic en **Ver tabla de detalles** en cualquier vista de informe, se muestra la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="754d9-241">If you click **View details table** in any report view, the following information is shown:</span></span>

- <span data-ttu-id="754d9-242">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="754d9-242">**Date**</span></span>
- <span data-ttu-id="754d9-243">**Dirección del remitente**</span><span class="sxs-lookup"><span data-stu-id="754d9-243">**Sender address**</span></span>
- <span data-ttu-id="754d9-244">**Dirección de destinatario**</span><span class="sxs-lookup"><span data-stu-id="754d9-244">**Recipient address**</span></span>
- <span data-ttu-id="754d9-245">**Tipo de evento**</span><span class="sxs-lookup"><span data-stu-id="754d9-245">**Event type**</span></span>
- <span data-ttu-id="754d9-246">**Acción**</span><span class="sxs-lookup"><span data-stu-id="754d9-246">**Action**</span></span>
- <span data-ttu-id="754d9-247">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="754d9-247">**Subject**</span></span>

<span data-ttu-id="754d9-248">Si hace clic **en Filtros** en una tabla de detalles, puede modificar los resultados con los filtros siguientes:</span><span class="sxs-lookup"><span data-stu-id="754d9-248">If you click **Filters** in a details table, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="754d9-249">**Fecha de inicio** y **fecha de finalización**</span><span class="sxs-lookup"><span data-stu-id="754d9-249">**Start date** and **End date**</span></span>
- <span data-ttu-id="754d9-250">Valores de dirección</span><span class="sxs-lookup"><span data-stu-id="754d9-250">Direction values</span></span>
- <span data-ttu-id="754d9-251">Valores de tipo de evento</span><span class="sxs-lookup"><span data-stu-id="754d9-251">Event type values</span></span>

<span data-ttu-id="754d9-252">Para volver a la vista informe, haga clic **en Ver informe**.</span><span class="sxs-lookup"><span data-stu-id="754d9-252">To go back to the report view, click **View report**.</span></span>

## <a name="spoof-detections-report"></a><span data-ttu-id="754d9-253">Informe de detecciones de suplantación</span><span class="sxs-lookup"><span data-stu-id="754d9-253">Spoof detections report</span></span>

<span data-ttu-id="754d9-254">El **informe de** detecciones de suplantación muestra cuántos mensajes de correo suplantación de suplantación se detectaron y de esos, que se consideraron "buenos" (correo suplantación de suplantación realizado por motivos profesionales legítimos).</span><span class="sxs-lookup"><span data-stu-id="754d9-254">The **Spoof detections** report shows how many spoof mail messages were detected, and of those, which ones were considered "good" (spoof mail done for legitimate business reasons).</span></span> <span data-ttu-id="754d9-255">Para obtener más información acerca de la suplantación, vea Protección contra la suplantación [en EOP](anti-spoofing-protection.md).</span><span class="sxs-lookup"><span data-stu-id="754d9-255">For more information about spoofing, see [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="754d9-256">La vista agregada del informe permite 90 días de filtrado, mientras que la vista de detalles solo permite diez días de filtrado.</span><span class="sxs-lookup"><span data-stu-id="754d9-256">The aggregate view of the report allows for 90 days of filtering, while the detail view only allows for ten days of filtering.</span></span>

<span data-ttu-id="754d9-257">Para ver el informe, abra el Centro de  [seguridad & cumplimiento,](https://protection.office.com)vaya al Panel de informes y \>  seleccione **Detecciones de suplantación de seguridad.**</span><span class="sxs-lookup"><span data-stu-id="754d9-257">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Spoof detections**.</span></span> <span data-ttu-id="754d9-258">Para ir directamente al informe, abra <https://protection.office.com/reportv2?id=SpoofMailReport> .</span><span class="sxs-lookup"><span data-stu-id="754d9-258">To go directly to the report, open <https://protection.office.com/reportv2?id=SpoofMailReport>.</span></span>

![Widget Detecciones de suplantación en el panel Informes](../../media/spoof-detections-widget.png)

<span data-ttu-id="754d9-260">Cuando mantiene el mouse sobre un día (punto de datos) en el gráfico, puede ver cuántos mensajes de correo suplantación se han recibido.</span><span class="sxs-lookup"><span data-stu-id="754d9-260">When you hover over a day (data point) in the chart, you can see how many spoof mail messages came through.</span></span>

<span data-ttu-id="754d9-261">Puede filtrar tanto el gráfico como la tabla de detalles haciendo clic en **Filtros** y seleccionando uno o varios de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="754d9-261">You can filter both the chart and the details table by clicking **Filters** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="754d9-262">**Fecha de inicio** y **fecha de finalización**</span><span class="sxs-lookup"><span data-stu-id="754d9-262">**Start date** and **End date**</span></span>

- <span data-ttu-id="754d9-263">**Correo bueno**</span><span class="sxs-lookup"><span data-stu-id="754d9-263">**Good mail**</span></span>

- <span data-ttu-id="754d9-264">**Capturado como correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="754d9-264">**Caught as spam**</span></span>

![Vista Informe en el informe Detecciones de suplantación](../../media/spoof-detections-report-view.png)

<span data-ttu-id="754d9-266">Si hace clic **en Ver tabla de detalles,** puede ver los siguientes detalles:</span><span class="sxs-lookup"><span data-stu-id="754d9-266">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="754d9-267">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="754d9-267">**Date**</span></span>
- <span data-ttu-id="754d9-268">**Remitente suplantado**</span><span class="sxs-lookup"><span data-stu-id="754d9-268">**Spoofed sender**</span></span>
- <span data-ttu-id="754d9-269">**Remitente verdadero**</span><span class="sxs-lookup"><span data-stu-id="754d9-269">**True sender**</span></span>
- <span data-ttu-id="754d9-270">**IP del remitente**</span><span class="sxs-lookup"><span data-stu-id="754d9-270">**Sender IP**</span></span>
- <span data-ttu-id="754d9-271">**Acción**</span><span class="sxs-lookup"><span data-stu-id="754d9-271">**Action**</span></span>
- <span data-ttu-id="754d9-272">**Recuento de mensajes**</span><span class="sxs-lookup"><span data-stu-id="754d9-272">**Message count**</span></span>

<span data-ttu-id="754d9-273">Para volver a la vista informe, haga clic **en Ver informe**.</span><span class="sxs-lookup"><span data-stu-id="754d9-273">To go back to the report view, click **View report**.</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="754d9-274">Informe de estado de protección contra amenazas</span><span class="sxs-lookup"><span data-stu-id="754d9-274">Threat protection status report</span></span>

<span data-ttu-id="754d9-275">El **informe de estado de** protección contra amenazas está disponible en EOP y Microsoft Defender para Office 365; sin embargo, los informes contienen datos diferentes.</span><span class="sxs-lookup"><span data-stu-id="754d9-275">The **Threat protection status** report is available in both EOP and Microsoft Defender for Office 365; however, the reports contain different data.</span></span> <span data-ttu-id="754d9-276">Por ejemplo, los clientes de EOP pueden ver información sobre malware detectado en el correo electrónico, pero no información sobre archivos malintencionados detectados por datos adjuntos seguros para [SharePoint, OneDrive](mdo-for-spo-odb-and-teams.md)y Microsoft Teams .</span><span class="sxs-lookup"><span data-stu-id="754d9-276">For example, EOP customers can view information about malware detected in email, but not information about malicious files detected by [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="754d9-277">El informe proporciona el recuento de mensajes de correo electrónico con contenido malintencionado, como archivos o direcciones de sitio web (URL) bloqueadas por el motor [](safe-attachments.md)antimalware, purga automática de hora cero [(ZAP)](zero-hour-auto-purge.md)y características de Defender para Office 365 como vínculos [seguros,](safe-links.md)datos adjuntos seguros y anti [phishing.](set-up-anti-phishing-policies.md)</span><span class="sxs-lookup"><span data-stu-id="754d9-277">The report provides the count of email messages with malicious content, such as files or website addresses (URLs) that were blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and Defender for Office 365 features like [Safe Links](safe-links.md), [Safe Attachments](safe-attachments.md), and [Anti-phishing](set-up-anti-phishing-policies.md).</span></span> <span data-ttu-id="754d9-278">Puede usar esta información para identificar tendencias o determinar si las directivas de la organización necesitan ajustes.</span><span class="sxs-lookup"><span data-stu-id="754d9-278">You can use this information to identify trends or determine whether organization policies need adjustment.</span></span>

<span data-ttu-id="754d9-279">**Nota:** Es importante comprender que si un mensaje se envía a cinco destinatarios, lo contamos como cinco mensajes diferentes y no un mensaje.</span><span class="sxs-lookup"><span data-stu-id="754d9-279">**Note**: It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>

<span data-ttu-id="754d9-280">Para ver el informe, abra el Centro de  [seguridad & cumplimiento,](https://protection.office.com)vaya al Panel de informes y seleccione Estado de protección \>  **contra amenazas**.</span><span class="sxs-lookup"><span data-stu-id="754d9-280">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Threat protection status**.</span></span> <span data-ttu-id="754d9-281">Para ir directamente al informe, abra una de las siguientes direcciones URL:</span><span class="sxs-lookup"><span data-stu-id="754d9-281">To go directly to the report, open one of the following URLs:</span></span>

- <span data-ttu-id="754d9-282">Microsoft Defender para Office 365: <https://protection.office.com/reportv2?id=TPSAggregateReportATP></span><span class="sxs-lookup"><span data-stu-id="754d9-282">Microsoft Defender for Office 365: <https://protection.office.com/reportv2?id=TPSAggregateReportATP></span></span>
- <span data-ttu-id="754d9-283">EOP: <https://protection.office.com/reportv2?id=TPSAggregateReport></span><span class="sxs-lookup"><span data-stu-id="754d9-283">EOP: <https://protection.office.com/reportv2?id=TPSAggregateReport></span></span>

![Widget de estado de protección contra amenazas en el panel Informes](../../media/threat-protection-status-report-widget.png)

<span data-ttu-id="754d9-285">De forma predeterminada, el gráfico muestra los datos de los últimos 7 días.</span><span class="sxs-lookup"><span data-stu-id="754d9-285">By default, the chart shows data for the past 7 days.</span></span> <span data-ttu-id="754d9-286">Si hace clic **en Filtros,** puede seleccionar un intervalo de fechas de 90 días (las suscripciones de prueba podrían limitarse a 30 días).</span><span class="sxs-lookup"><span data-stu-id="754d9-286">If you click **Filters**, you can select a 90 day date range (trial subscriptions might be limited to 30 days).</span></span> <span data-ttu-id="754d9-287">La vista de tabla de detalles permite filtrar durante 30 días.</span><span class="sxs-lookup"><span data-stu-id="754d9-287">The details table view allows filtering for 30 days.</span></span>

### <a name="report-view-for-the-threat-protection-status-report"></a><span data-ttu-id="754d9-288">Vista Informe para el informe de estado de protección contra amenazas</span><span class="sxs-lookup"><span data-stu-id="754d9-288">Report view for the Threat protection status report</span></span>

<span data-ttu-id="754d9-289">Las vistas siguientes están disponibles:</span><span class="sxs-lookup"><span data-stu-id="754d9-289">The following views are available:</span></span>

- <span data-ttu-id="754d9-290">**Ver datos por: Información general:** se muestra la siguiente información de detección:</span><span class="sxs-lookup"><span data-stu-id="754d9-290">**View data by: Overview**: The following detection information is shown:</span></span>

  - <span data-ttu-id="754d9-291">**Malware de correo electrónico**</span><span class="sxs-lookup"><span data-stu-id="754d9-291">**Email malware**</span></span>
  - <span data-ttu-id="754d9-292">**Phish de correo electrónico**</span><span class="sxs-lookup"><span data-stu-id="754d9-292">**Email phish**</span></span>
  - <span data-ttu-id="754d9-293">**Malware de contenido**</span><span class="sxs-lookup"><span data-stu-id="754d9-293">**Content malware**</span></span>

  ![Vista general en el informe de estado de protección contra amenazas](../../media/threat-protection-status-report-overview-view.png)

- <span data-ttu-id="754d9-295">**Ver datos por: Contenido \> Malware**<sup>1:</sup>Se muestra la siguiente información para organizaciones de Microsoft Defender para Office 365:</span><span class="sxs-lookup"><span data-stu-id="754d9-295">**View data by: Content \> Malware**<sup>1</sup>: The following information is shown for Microsoft Defender for Office 365 organizations:</span></span>

  - <span data-ttu-id="754d9-296">**Motor antimalware:** archivos malintencionados detectados en Sharepoint, OneDrive y Microsoft Teams mediante la detección de virus integrada [en Microsoft 365](virus-detection-in-spo.md).</span><span class="sxs-lookup"><span data-stu-id="754d9-296">**Anti-malware engine**: Malicious files detected in Sharepoint, OneDrive, and Microsoft Teams by the [built-in virus detection in Microsoft 365](virus-detection-in-spo.md).</span></span>
  - <span data-ttu-id="754d9-297">**Detonación de archivos:** archivos malintencionados detectados por datos adjuntos seguros para [SharePoint, OneDrive y Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="754d9-297">**File detonation**: Malicious files detected by [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

  ![Vista de malware de contenido en el informe de estado de protección contra amenazas](../../media/threat-protection-status-report-content-malware-view.png)

- <span data-ttu-id="754d9-299">**Ver datos por: Invalidación de** mensaje: se muestra la siguiente información de motivo de invalidación:</span><span class="sxs-lookup"><span data-stu-id="754d9-299">**View data by: Message Override**: The following override reason information is shown:</span></span>

  - <span data-ttu-id="754d9-300">**Omitir localmente**</span><span class="sxs-lookup"><span data-stu-id="754d9-300">**On-premises skip**</span></span>
  - <span data-ttu-id="754d9-301">**Permitir IP**</span><span class="sxs-lookup"><span data-stu-id="754d9-301">**IP Allow**</span></span>
  - <span data-ttu-id="754d9-302">**Regla de flujo de correo**</span><span class="sxs-lookup"><span data-stu-id="754d9-302">**Mail flow rule**</span></span>
  - <span data-ttu-id="754d9-303">**Permitir remitente**</span><span class="sxs-lookup"><span data-stu-id="754d9-303">**Sender allow**</span></span>
  - <span data-ttu-id="754d9-304">**Permitir dominio**</span><span class="sxs-lookup"><span data-stu-id="754d9-304">**Domain allow**</span></span>
  - <span data-ttu-id="754d9-305">**ZAP no habilitado**</span><span class="sxs-lookup"><span data-stu-id="754d9-305">**ZAP not enabled**</span></span>
  - <span data-ttu-id="754d9-306">**Carpeta de correo no deseado no habilitada**</span><span class="sxs-lookup"><span data-stu-id="754d9-306">**Junk Mail folder not enabled**</span></span>
  - <span data-ttu-id="754d9-307">**Remitente seguro del usuario**</span><span class="sxs-lookup"><span data-stu-id="754d9-307">**User Safe Sender**</span></span>
  - <span data-ttu-id="754d9-308">**Dominio seguro del usuario**</span><span class="sxs-lookup"><span data-stu-id="754d9-308">**User Safe Domain**</span></span>

  ![Vista De invalidación de mensajes en el informe de estado de protección contra amenazas](../../media/threat-protection-status-report-message-override-view.png)

- <span data-ttu-id="754d9-310">**Dividir por: Tecnología de detección** y **Ver datos por: Email \> Phish**: Se muestra la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="754d9-310">**Break down by: Detection technology** and **View data by: Email \> Phish**: The following information is shown:</span></span>

  - <span data-ttu-id="754d9-311">**Reputación** de url generada por ATP <sup>1:</sup>Reputación de url malintencionada generada a partir de detonaciones de Defender para Office 365 en otros clientes de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="754d9-311">**ATP-generated URL reputation**<sup>1</sup>: Malicious URL reputation generated from Defender for Office 365 detonations in other Microsoft 365 customers.</span></span>
  - <span data-ttu-id="754d9-312">**Filtro de phishing** avanzado: señales de suplantación de identidad basadas en el aprendizaje automático.</span><span class="sxs-lookup"><span data-stu-id="754d9-312">**Advanced phish filter**: Phishing signals based on machine learning.</span></span>
  - <span data-ttu-id="754d9-313">**Anti-spoof: error dmarc:** error de autenticación dmarc en mensajes.</span><span class="sxs-lookup"><span data-stu-id="754d9-313">**Anti-spoof - DMARC failure**: DMARC authentication failure on messages.</span></span>
  - <span data-ttu-id="754d9-314">**Anti-spoof - intra-org**: El remitente está intentando suplantación del dominio de destinatario.</span><span class="sxs-lookup"><span data-stu-id="754d9-314">**Anti-spoof - intra-org**: Sender is trying to spoof the recipient domain.</span></span>
  - <span data-ttu-id="754d9-315">**Anti-spoof - external domain**: Sender is trying to spoof some other domain.</span><span class="sxs-lookup"><span data-stu-id="754d9-315">**Anti-spoof - external domain**: Sender is trying to spoof some other domain.</span></span>
  - <span data-ttu-id="754d9-316">**Suplantación de marca:** suplantación de marcas conocidas basadas en remitentes.</span><span class="sxs-lookup"><span data-stu-id="754d9-316">**Brand impersonation**: Impersonation of well-known brands based on senders.</span></span>
  - <span data-ttu-id="754d9-317">**Suplantación de dominio**<sup>1:</sup>suplantación de dominios que el cliente posee o define.</span><span class="sxs-lookup"><span data-stu-id="754d9-317">**Domain impersonation**<sup>1</sup>: Impersonation of domains that the customer owns or defines.</span></span>
  - <span data-ttu-id="754d9-318">**Reputación de dirección URL de EOP:** reputación de url malintencionada.</span><span class="sxs-lookup"><span data-stu-id="754d9-318">**EOP URL reputation**: Malicious URL reputation.</span></span>
  - <span data-ttu-id="754d9-319">**Filtro de phishing** general: señales de suplantación de identidad basadas en reglas de analista.</span><span class="sxs-lookup"><span data-stu-id="754d9-319">**General phish filter**: Phishing signals based on analyst rules.</span></span>
  - <span data-ttu-id="754d9-320">**Otros**</span><span class="sxs-lookup"><span data-stu-id="754d9-320">**Others**</span></span>
  - <span data-ttu-id="754d9-321">**Phish ZAP**<sup>2:</sup>Purga automática de cero horas de mensajes de suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="754d9-321">**Phish ZAP**<sup>2</sup>: Zero hour auto purge of phishing messages.</span></span>
  - <span data-ttu-id="754d9-322">**Detonación de dirección URL**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="754d9-322">**URL detonation**<sup>1</sup></span></span>
  - <span data-ttu-id="754d9-323">**Suplantación de usuario**<sup>1:</sup>suplantación de usuarios definida por el administrador o aprendida a través de la inteligencia de buzones.</span><span class="sxs-lookup"><span data-stu-id="754d9-323">**User impersonation**<sup>1</sup>: Impersonation of users defined by admin or learned through mailbox intelligence.</span></span>

  ![Vista de tecnología de detección para correo electrónico de suplantación de identidad (phishing) en el informe de estado de protección contra amenazas](../../media/threat-protection-status-report-phishing-detection-tech-view.png)

- <span data-ttu-id="754d9-325">**Dividir por: Tecnología de detección** y **Ver datos por: Malware \> de correo** electrónico : Se muestra la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="754d9-325">**Break down by: Detection technology** and **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="754d9-326">**Reputación de archivo generada por ATP**<sup>1:</sup>Toda la reputación de archivos malintencionados generada por Detonaciones de Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="754d9-326">**ATP-generated file reputation**<sup>1</sup>: All malicious file reputation generated by Defender for Office 365 detonations.</span></span>
  - <span data-ttu-id="754d9-327">**Motor antimalware**<sup>1:</sup>Detección de motores antimalware.</span><span class="sxs-lookup"><span data-stu-id="754d9-327">**Anti-malware engine**<sup>1</sup>: Detection from anti-malware engines.</span></span>
  - <span data-ttu-id="754d9-328">Bloque de tipo de archivo de directiva **antimalware:** se trata de mensajes de correo electrónico filtrados debido al tipo de archivo malintencionado identificado en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="754d9-328">**Anti-malware policy file type block**: These are email messages filtered out due to the type of malicious file identified in the message.</span></span>
  - <span data-ttu-id="754d9-329">**Detonación de archivos**<sup>1:</sup>Detección por datos adjuntos seguros.</span><span class="sxs-lookup"><span data-stu-id="754d9-329">**File detonation**<sup>1</sup>: Detection by Safe Attachments.</span></span>
  - <span data-ttu-id="754d9-330">**Reputación de archivos malintencionados**</span><span class="sxs-lookup"><span data-stu-id="754d9-330">**Malicious file reputation**</span></span>
  - <span data-ttu-id="754d9-331">**MALWARE ZAP**<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="754d9-331">**Malware ZAP**<sup>2</sup></span></span>
  - <span data-ttu-id="754d9-332">**Otros**</span><span class="sxs-lookup"><span data-stu-id="754d9-332">**Others**</span></span>

  ![Vista de tecnología de detección de malware en el informe de estado de protección contra amenazas](../../media/threat-protection-status-report-malware-detection-tech-view.png)

- <span data-ttu-id="754d9-334">**Dividir por: Tipo de directiva** y Ver datos **por: Email \> Phish** o **View data by: Email \> Malware**: Se muestra la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="754d9-334">**Break down by: Policy type** and **View data by: Email \> Phish** or **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="754d9-335">**Antimalware**</span><span class="sxs-lookup"><span data-stu-id="754d9-335">**Anti-malware**</span></span>
  - <span data-ttu-id="754d9-336">**Datos adjuntos**<sup>seguros 1</sup></span><span class="sxs-lookup"><span data-stu-id="754d9-336">**Safe Attachments**<sup>1</sup></span></span>
  - <span data-ttu-id="754d9-337">**Anti-phish**</span><span class="sxs-lookup"><span data-stu-id="754d9-337">**Anti-phish**</span></span>
  - <span data-ttu-id="754d9-338">**Contra correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="754d9-338">**Anti-spam**</span></span>
  - <span data-ttu-id="754d9-339">**Regla de flujo de** correo (también conocida como regla de transporte)</span><span class="sxs-lookup"><span data-stu-id="754d9-339">**Mail flow rule** (also known as a transport rule)</span></span>
  - <span data-ttu-id="754d9-340">**Otros**</span><span class="sxs-lookup"><span data-stu-id="754d9-340">**Others**</span></span>

  ![Vista de tipo de directiva para correo electrónico de suplantación de identidad (phishing) en el informe de estado de protección contra amenazas](../../media/threat-protection-status-report-phishing-policy-type-view.png)

- <span data-ttu-id="754d9-342">**Dividir por: Estado de** entrega y Ver datos por: Correo electrónico **\> Phish** o Ver datos **por: Malware de \> correo** electrónico : Se muestra la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="754d9-342">**Break down by: Delivery status** and **View data by: Email \> Phish** or **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="754d9-343">**Error en la entrega**</span><span class="sxs-lookup"><span data-stu-id="754d9-343">**Delivery failed**</span></span>
  - <span data-ttu-id="754d9-344">**Se ha descartado**</span><span class="sxs-lookup"><span data-stu-id="754d9-344">**Dropped**</span></span>
  - <span data-ttu-id="754d9-345">**Reenviado**</span><span class="sxs-lookup"><span data-stu-id="754d9-345">**Forwarded**</span></span>
  - <span data-ttu-id="754d9-346">**Buzón hospedado: carpeta personalizada**</span><span class="sxs-lookup"><span data-stu-id="754d9-346">**Hosted mailbox: Custom folder**</span></span>
  - <span data-ttu-id="754d9-347">**Buzón hospedado: elementos eliminados**</span><span class="sxs-lookup"><span data-stu-id="754d9-347">**Hosted mailbox: Deleted items**</span></span>
  - <span data-ttu-id="754d9-348">**Buzón hospedado: Bandeja de entrada**</span><span class="sxs-lookup"><span data-stu-id="754d9-348">**Hosted mailbox: Inbox**</span></span>
  - <span data-ttu-id="754d9-349">**Buzón hospedado: correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="754d9-349">**Hosted mailbox: Junk**</span></span>
  - <span data-ttu-id="754d9-350">**Servidor local: entregado**</span><span class="sxs-lookup"><span data-stu-id="754d9-350">**On-premises server: Delivered**</span></span>
  - <span data-ttu-id="754d9-351">**Cuarentena**</span><span class="sxs-lookup"><span data-stu-id="754d9-351">**Quarantine**</span></span>

  ![Vista Estado de entrega para correo electrónico de suplantación de identidad (phishing) en el informe de estado de protección contra amenazas](../../media/threat-protection-status-report-phishing-delivery-status-view.png)

<span data-ttu-id="754d9-353"><sup>1</sup> Defender solo para Office 365</span><span class="sxs-lookup"><span data-stu-id="754d9-353"><sup>1</sup> Defender for Office 365 only</span></span>

<span data-ttu-id="754d9-354"><sup>2</sup> La purga automática de hora cero (ZAP) no está disponible en EOP independiente (solo funciona en buzones de Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="754d9-354"><sup>2</sup> Zero-hour auto purge (ZAP) isn't available in standalone EOP (it only works in Exchange Online mailboxes).</span></span>

<span data-ttu-id="754d9-355">Si hace clic **en Filtros,** los filtros disponibles dependen del gráfico que esté mirando:</span><span class="sxs-lookup"><span data-stu-id="754d9-355">If you click **Filters**, the filters available depends on the chart you were looking at:</span></span>

- <span data-ttu-id="754d9-356">Para **Ver datos por: Malware \> de** contenido, puede modificar el informe por fecha **de** inicio y fecha de **finalización,** y el valor **Detección.**</span><span class="sxs-lookup"><span data-stu-id="754d9-356">For **View data by: Content \> Malware**, you can modify the report by **Start date** and **End date**, and the **Detection** value.</span></span>

- <span data-ttu-id="754d9-357">Para **Ver datos por: Invalidación de** mensajes, puede modificar el informe con los filtros siguientes:</span><span class="sxs-lookup"><span data-stu-id="754d9-357">For **View data by: Message Override**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="754d9-358">**Fecha de inicio** y **fecha de finalización**</span><span class="sxs-lookup"><span data-stu-id="754d9-358">**Start date** and **End date**</span></span>
  - <span data-ttu-id="754d9-359">**Motivo de invalidación**</span><span class="sxs-lookup"><span data-stu-id="754d9-359">**Override Reason**</span></span>
  - <span data-ttu-id="754d9-360">**Etiqueta:** filtre los resultados por usuarios o grupos a los que se aplicó la etiqueta de usuario especificada (incluidas las cuentas de prioridad).</span><span class="sxs-lookup"><span data-stu-id="754d9-360">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="754d9-361">Para obtener más información acerca de las etiquetas de usuario, vea [Etiquetas de usuario](user-tags.md).</span><span class="sxs-lookup"><span data-stu-id="754d9-361">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="754d9-362">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="754d9-362">**Domain**</span></span>

- <span data-ttu-id="754d9-363">Para el resto de vistas, puede modificar el informe con los filtros siguientes:</span><span class="sxs-lookup"><span data-stu-id="754d9-363">For all other views, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="754d9-364">**Fecha de inicio** y **fecha de finalización**</span><span class="sxs-lookup"><span data-stu-id="754d9-364">**Start date** and **End date**</span></span>
  - <span data-ttu-id="754d9-365">**Detección**</span><span class="sxs-lookup"><span data-stu-id="754d9-365">**Detection**</span></span>
  - <span data-ttu-id="754d9-366">**Protegido por**: **ATP** o **EOP**</span><span class="sxs-lookup"><span data-stu-id="754d9-366">**Protected by**: **ATP** or **EOP**</span></span>
  - <span data-ttu-id="754d9-367">**Etiqueta:** filtre los resultados por usuarios o grupos a los que se aplicó la etiqueta de usuario especificada (incluidas las cuentas de prioridad).</span><span class="sxs-lookup"><span data-stu-id="754d9-367">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="754d9-368">Para obtener más información acerca de las etiquetas de usuario, vea [Etiquetas de usuario](user-tags.md).</span><span class="sxs-lookup"><span data-stu-id="754d9-368">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="754d9-369">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="754d9-369">**Domain**</span></span>

### <a name="details-table-view-for-the-threat-protection-status-report"></a><span data-ttu-id="754d9-370">Vista de tabla Detalles del informe de estado de protección contra amenazas</span><span class="sxs-lookup"><span data-stu-id="754d9-370">Details table view for the Threat protection status report</span></span>

<span data-ttu-id="754d9-371">Si hace clic **en Ver tabla de detalles,** la información que se muestra depende del gráfico que estaba mirando:</span><span class="sxs-lookup"><span data-stu-id="754d9-371">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="754d9-372">**Ver datos por: Información general:** No **hay disponible** el botón Ver tabla de detalles.</span><span class="sxs-lookup"><span data-stu-id="754d9-372">**View data by: Overview**: No **View details table** button is available.</span></span>

- <span data-ttu-id="754d9-373">**Ver datos por: Contenido \> Malware**:</span><span class="sxs-lookup"><span data-stu-id="754d9-373">**View data by: Content \> Malware**:</span></span>

  - <span data-ttu-id="754d9-374">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="754d9-374">**Date**</span></span>
  - <span data-ttu-id="754d9-375">**Location**</span><span class="sxs-lookup"><span data-stu-id="754d9-375">**Location**</span></span>
  - <span data-ttu-id="754d9-376">**Dirigido por**</span><span class="sxs-lookup"><span data-stu-id="754d9-376">**Directed by**</span></span>
  - <span data-ttu-id="754d9-377">**Nombre de malware**</span><span class="sxs-lookup"><span data-stu-id="754d9-377">**Malware name**</span></span>

  <span data-ttu-id="754d9-378">Si hace clic **en Filtros** en esta  vista, puede modificar el informe por fecha de inicio y fecha de **finalización,** y el valor **Detección.**</span><span class="sxs-lookup"><span data-stu-id="754d9-378">If you click **Filters** in this view, you can modify the report by **Start date** and **End date**, and the **Detection** value.</span></span>

- <span data-ttu-id="754d9-379">**Ver datos por: Invalidación de mensaje**:</span><span class="sxs-lookup"><span data-stu-id="754d9-379">**View data by: Message Override**:</span></span>

  - <span data-ttu-id="754d9-380">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="754d9-380">**Date**</span></span>
  - <span data-ttu-id="754d9-381">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="754d9-381">**Subject**</span></span>
  - <span data-ttu-id="754d9-382">**Remitente**</span><span class="sxs-lookup"><span data-stu-id="754d9-382">**Sender**</span></span>
  - <span data-ttu-id="754d9-383">**Destinatarios**</span><span class="sxs-lookup"><span data-stu-id="754d9-383">**Recipients**</span></span>
  - <span data-ttu-id="754d9-384">**Detectado por**</span><span class="sxs-lookup"><span data-stu-id="754d9-384">**Detected by**</span></span>
  - <span data-ttu-id="754d9-385">**Motivo de invalidación**</span><span class="sxs-lookup"><span data-stu-id="754d9-385">**Override Reason**</span></span>
  - <span data-ttu-id="754d9-386">**Origen de la transacción**</span><span class="sxs-lookup"><span data-stu-id="754d9-386">**Source of Compromise**</span></span>
  - <span data-ttu-id="754d9-387">**Tags**</span><span class="sxs-lookup"><span data-stu-id="754d9-387">**Tags**</span></span>

  <span data-ttu-id="754d9-388">Si hace clic **en Filtros** en esta vista, puede modificar el informe con los filtros siguientes:</span><span class="sxs-lookup"><span data-stu-id="754d9-388">If you click **Filters** in this view, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="754d9-389">**Fecha de inicio** y **fecha de finalización**</span><span class="sxs-lookup"><span data-stu-id="754d9-389">**Start date** and **End date**</span></span>
  - <span data-ttu-id="754d9-390">**Motivo de invalidación**</span><span class="sxs-lookup"><span data-stu-id="754d9-390">**Override Reason**</span></span>
  - <span data-ttu-id="754d9-391">**Etiqueta:** filtre los resultados por usuarios o grupos a los que se aplicó la etiqueta de usuario especificada (incluidas las cuentas de prioridad).</span><span class="sxs-lookup"><span data-stu-id="754d9-391">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="754d9-392">Para obtener más información acerca de las etiquetas de usuario, vea [Etiquetas de usuario](user-tags.md).</span><span class="sxs-lookup"><span data-stu-id="754d9-392">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="754d9-393">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="754d9-393">**Domain**</span></span>
  - <span data-ttu-id="754d9-394">**Destinatarios** (tenga en cuenta que esta propiedad filtrable solo está disponible en la vista de tabla de detalles)</span><span class="sxs-lookup"><span data-stu-id="754d9-394">**Recipients** (Note that this filterable property is only available in the details table view)</span></span>

- <span data-ttu-id="754d9-395">Todos los demás gráficos:</span><span class="sxs-lookup"><span data-stu-id="754d9-395">All other charts:</span></span>

  - <span data-ttu-id="754d9-396">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="754d9-396">**Date**</span></span>
  - <span data-ttu-id="754d9-397">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="754d9-397">**Subject**</span></span>
  - <span data-ttu-id="754d9-398">**Remitente**</span><span class="sxs-lookup"><span data-stu-id="754d9-398">**Sender**</span></span>
  - <span data-ttu-id="754d9-399">**Destinatarios**</span><span class="sxs-lookup"><span data-stu-id="754d9-399">**Recipients**</span></span>
  - <span data-ttu-id="754d9-400">**Detectado por**</span><span class="sxs-lookup"><span data-stu-id="754d9-400">**Detected by**</span></span>
  - <span data-ttu-id="754d9-401">**Estado de entrega**</span><span class="sxs-lookup"><span data-stu-id="754d9-401">**Delivery Status**</span></span>
  - <span data-ttu-id="754d9-402">**Origen de la transacción**</span><span class="sxs-lookup"><span data-stu-id="754d9-402">**Source of Compromise**</span></span>
  - <span data-ttu-id="754d9-403">**Tags**</span><span class="sxs-lookup"><span data-stu-id="754d9-403">**Tags**</span></span>

  <span data-ttu-id="754d9-404">Si hace clic **en Filtros,** puede modificar el informe con los filtros siguientes:</span><span class="sxs-lookup"><span data-stu-id="754d9-404">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="754d9-405">**Fecha de inicio** y **fecha de finalización**</span><span class="sxs-lookup"><span data-stu-id="754d9-405">**Start date** and **End date**</span></span>
  - <span data-ttu-id="754d9-406">**Detección**</span><span class="sxs-lookup"><span data-stu-id="754d9-406">**Detection**</span></span>
  - <span data-ttu-id="754d9-407">**Protegido por**: **Defender para Office 365** o **EOP**</span><span class="sxs-lookup"><span data-stu-id="754d9-407">**Protected by**: **Defender for Office 365** or **EOP**</span></span>
  - <span data-ttu-id="754d9-408">**Etiqueta:** filtre los resultados por usuarios o grupos a los que se aplicó la etiqueta de usuario especificada (incluidas las cuentas de prioridad).</span><span class="sxs-lookup"><span data-stu-id="754d9-408">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="754d9-409">Para obtener más información acerca de las etiquetas de usuario, vea [Etiquetas de usuario](user-tags.md).</span><span class="sxs-lookup"><span data-stu-id="754d9-409">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="754d9-410">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="754d9-410">**Domain**</span></span>
  - <span data-ttu-id="754d9-411">**Destinatarios** (tenga en cuenta que esta propiedad filtrable solo está disponible en la vista de tabla de detalles)</span><span class="sxs-lookup"><span data-stu-id="754d9-411">**Recipients** (Note that this filterable property is only available in the details table view)</span></span>

## <a name="top-malware-report"></a><span data-ttu-id="754d9-412">Informe de malware superior</span><span class="sxs-lookup"><span data-stu-id="754d9-412">Top malware report</span></span>

<span data-ttu-id="754d9-413">El **informe de malware** top muestra los distintos tipos de malware detectados por la protección [antimalware en EOP](anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="754d9-413">The **Top malware** report shows the various kinds of malware that was detected by [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

<span data-ttu-id="754d9-414">Para ver el informe, abra el Centro de  [seguridad & cumplimiento,](https://protection.office.com)vaya al Panel \> **de informes** y seleccione Top **malware**.</span><span class="sxs-lookup"><span data-stu-id="754d9-414">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top malware**.</span></span> <span data-ttu-id="754d9-415">Para ir directamente al informe, abra <https://protection.office.com/reportv2?id=TopMalware> .</span><span class="sxs-lookup"><span data-stu-id="754d9-415">To go directly to the report, open <https://protection.office.com/reportv2?id=TopMalware>.</span></span>

![Widget de malware superior en el panel Informes](../../media/top-malware-report-widget.png)

<span data-ttu-id="754d9-417">Al pasar el mouse sobre una cuña en el gráfico circular, puede ver el nombre de un tipo de malware y cuántos mensajes se detectaron como que tienen ese malware.</span><span class="sxs-lookup"><span data-stu-id="754d9-417">When you hover over a wedge in the pie chart, you can see the name of a kind of malware and how many messages were detected as having that malware.</span></span>

![Vista de informe de malware superior](../../media/top-malware-report-view.png)

<span data-ttu-id="754d9-419">Si hace clic **en Ver tabla de detalles,** puede ver los siguientes detalles:</span><span class="sxs-lookup"><span data-stu-id="754d9-419">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="754d9-420">**Malware superior**</span><span class="sxs-lookup"><span data-stu-id="754d9-420">**Top malware**</span></span>
- <span data-ttu-id="754d9-421">**Count**</span><span class="sxs-lookup"><span data-stu-id="754d9-421">**Count**</span></span>

<span data-ttu-id="754d9-422">Si hace clic **en Filtros en** la vista informe o en la vista tabla detalles, puede especificar un intervalo de fechas con **Fecha** de inicio y Fecha **de finalización.**</span><span class="sxs-lookup"><span data-stu-id="754d9-422">If you click **Filters** in the report view or details table view, you can specify a date range with **Start date** and **End date**.</span></span>

## <a name="url-threat-protection-report"></a><span data-ttu-id="754d9-423">Informe de protección contra amenazas de url</span><span class="sxs-lookup"><span data-stu-id="754d9-423">URL threat protection report</span></span>

<span data-ttu-id="754d9-424">El **informe de protección contra amenazas de dirección URL** está disponible en Microsoft Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="754d9-424">The **URL threat protection report** is available in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="754d9-425">Para obtener más información, vea [Informe de protección contra amenazas de url](view-reports-for-mdo.md#url-threat-protection-report).</span><span class="sxs-lookup"><span data-stu-id="754d9-425">For more information, see [URL threat protection report](view-reports-for-mdo.md#url-threat-protection-report).</span></span>

## <a name="user-reported-messages-report"></a><span data-ttu-id="754d9-426">Informe de mensajes notificados por el usuario</span><span class="sxs-lookup"><span data-stu-id="754d9-426">User-reported messages report</span></span>

<span data-ttu-id="754d9-427">El **informe** de mensajes notificados por el usuario muestra información sobre los mensajes de correo electrónico que los usuarios han notificado como correo no deseado, intentos de suplantación de identidad o correo bueno mediante el complemento Report [Message o](enable-the-report-message-add-in.md) el complemento Report [Phishing](enable-the-report-phish-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="754d9-427">The **User-reported messages** report shows information about email messages that users have reported as junk, phishing attempts, or good mail by using the [Report Message add-in](enable-the-report-message-add-in.md) or [The Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>

<span data-ttu-id="754d9-428">Los detalles están disponibles para cada mensaje, incluido el motivo de entrega, como una excepción de directiva de correo no deseado o una regla de flujo de correo configurada para su organización.</span><span class="sxs-lookup"><span data-stu-id="754d9-428">Details are available for each message, including the delivery reason, such a spam policy exception or mail flow rule configured for your organization.</span></span> <span data-ttu-id="754d9-429">Para ver detalles, seleccione un elemento en la lista de  informes de usuario y, a continuación, vea la información en las pestañas Resumen **y** Detalles.</span><span class="sxs-lookup"><span data-stu-id="754d9-429">To view details, select an item in the user-reports list, and then view the information on the **Summary** and **Details** tabs.</span></span>

![El informe User-Reported mensajes muestra los mensajes que los usuarios etiquetan como correo no deseado, no como correo no deseado o intentos de suplantación de identidad.](../../media/ad5e9a3d-b833-419c-bcc9-3425d9604ead.png)

<span data-ttu-id="754d9-431">Para ver este informe, en el Centro de [seguridad & cumplimiento](https://protection.office.com), realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="754d9-431">To view this report, in the [Security & Compliance Center](https://protection.office.com), do one of the following:</span></span>

- <span data-ttu-id="754d9-432">Vaya a **Administración de amenazas** \> **Mensajes** \> **notificados por el usuario.**</span><span class="sxs-lookup"><span data-stu-id="754d9-432">Go to **Threat management** \> **Dashboard** \> **User-reported messages**.</span></span>

- <span data-ttu-id="754d9-433">Vaya a **Administración de amenazas** \> **Revisar** \> **mensajes notificados por el usuario**.</span><span class="sxs-lookup"><span data-stu-id="754d9-433">Go to **Threat management** \> **Review** \> **User-reported messages**.</span></span>

![En el Centro de seguridad & cumplimiento, elija Administración de amenazas \> Revisar \> mensajes notificados por el usuario](../../media/e372c57c-1414-4616-957b-bc933b8c8711.png)

> [!IMPORTANT]
> <span data-ttu-id="754d9-435">Para que el informe de mensajes notificados  por el usuario funcione correctamente, el registro de auditoría debe estar activado para el entorno de Office 365.</span><span class="sxs-lookup"><span data-stu-id="754d9-435">In order for the User-reported messages report to work correctly, **audit logging must be turned on** for your Office 365 environment.</span></span> <span data-ttu-id="754d9-436">Esto lo suele hacer alguien que tiene el rol Registros de auditoría asignado en Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="754d9-436">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="754d9-437">Para obtener más información, vea Activar o desactivar la búsqueda del registro de auditoría de [Microsoft 365](../../compliance/turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="754d9-437">For more information, see [Turn Microsoft 365 audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="754d9-438">¿Qué permisos se necesitan para ver estos informes?</span><span class="sxs-lookup"><span data-stu-id="754d9-438">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="754d9-439">Para ver y usar los informes descritos en este artículo, debe ser miembro de uno de los siguientes grupos de roles en el Centro de seguridad & cumplimiento:</span><span class="sxs-lookup"><span data-stu-id="754d9-439">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Security & Compliance Center:</span></span>

- <span data-ttu-id="754d9-440">**Administración de organizaciones**</span><span class="sxs-lookup"><span data-stu-id="754d9-440">**Organization Management**</span></span>
- <span data-ttu-id="754d9-441">**Administrador de seguridad**</span><span class="sxs-lookup"><span data-stu-id="754d9-441">**Security Administrator**</span></span>
- <span data-ttu-id="754d9-442">**Lector de seguridad**</span><span class="sxs-lookup"><span data-stu-id="754d9-442">**Security Reader**</span></span>
- <span data-ttu-id="754d9-443">**Lector global**</span><span class="sxs-lookup"><span data-stu-id="754d9-443">**Global Reader**</span></span>

<span data-ttu-id="754d9-444">Para más información, consulte [Permisos en el Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="754d9-444">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="754d9-445">**Nota:** Agregar usuarios al rol de Azure Active Directory correspondiente en el Centro de administración de Microsoft  365 proporciona a los usuarios los permisos necesarios en el Centro de seguridad & cumplimiento y permisos para otras características de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="754d9-445">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="754d9-446">Para más información, consulte[Sobre los roles de administrador](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="754d9-446">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="754d9-447">¿Qué ocurre si los informes no muestran datos?</span><span class="sxs-lookup"><span data-stu-id="754d9-447">What if the reports aren't showing data?</span></span>

<span data-ttu-id="754d9-448">Si no ve datos en los informes, compruebe que las directivas están configuradas correctamente.</span><span class="sxs-lookup"><span data-stu-id="754d9-448">If you are not seeing data in your reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="754d9-449">Para obtener más información, vea [Protect against threats](protect-against-threats.md).</span><span class="sxs-lookup"><span data-stu-id="754d9-449">To learn more, see [Protect against threats](protect-against-threats.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="754d9-450">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="754d9-450">Related topics</span></span>

[<span data-ttu-id="754d9-451">Protección contra correo no deseado y antimalware en EOP</span><span class="sxs-lookup"><span data-stu-id="754d9-451">Anti-spam and anti-malware protection in EOP</span></span>](anti-spam-and-anti-malware-protection.md)

[<span data-ttu-id="754d9-452">Informes inteligentes y reportes en el Centro de seguridad y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="754d9-452">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="754d9-453">Ver informes de flujo de correo en el Centro de seguridad & cumplimiento</span><span class="sxs-lookup"><span data-stu-id="754d9-453">View mail flow reports in the Security & Compliance Center</span></span>](view-mail-flow-reports.md)

[<span data-ttu-id="754d9-454">Ver informes de Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="754d9-454">View reports for Defender for Office 365</span></span>](view-reports-for-mdo.md)
