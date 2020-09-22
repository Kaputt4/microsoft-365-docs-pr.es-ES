---
title: Ver informes para la protección contra amenazas avanzada
f1.keywords:
- CSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e47e838c-d99e-4c0b-b9aa-e66c4fae902f
ms.collection:
- M365-security-compliance
description: Busque y use informes de la protección contra amenazas avanzada de Office 365 en el centro de seguridad y &amp; cumplimiento.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 90da02c8aa3d50f62bdf4be8c466962da828b23d
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "48196602"
---
# <a name="view-reports-for-office-365-advanced-threat-protection"></a><span data-ttu-id="3c8f4-103">Ver informes para la protección contra amenazas avanzada de Office 365</span><span class="sxs-lookup"><span data-stu-id="3c8f4-103">View reports for Office 365 Advanced Threat Protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="3c8f4-104">Las organizaciones de protección contra amenazas avanzada (ATP) de Office 365 (por ejemplo, las suscripciones de Microsoft 365 E5 o el plan de ATP 1 o ATP del plan 2) contienen una variedad de informes relacionados con la seguridad.</span><span class="sxs-lookup"><span data-stu-id="3c8f4-104">Office 365 Advanced Threat Protection (ATP) organizations (for example, Microsoft 365 E5 subscriptions or ATP Plan 1 or ATP Plan 2 add-ons) contain a variety of security-related reports.</span></span> <span data-ttu-id="3c8f4-105">Si dispone de los [permisos necesarios](#what-permissions-are-needed-to-view-the-atp-reports), puede ver estos informes en el centro de seguridad & cumplimiento desde el panel de **informes** \> **Dashboard**.</span><span class="sxs-lookup"><span data-stu-id="3c8f4-105">If you have the [necessary permissions](#what-permissions-are-needed-to-view-the-atp-reports), you can view these reports in the Security & Compliance Center by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="3c8f4-106">Para ir directamente al panel informes, Abra <https://protection.office.com/insightdashboard> .</span><span class="sxs-lookup"><span data-stu-id="3c8f4-106">To go directly to the Reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![Panel informes en el centro de seguridad & cumplimiento](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="advanced-threat-protection-file-types-report"></a><span data-ttu-id="3c8f4-108">Informe de tipos de archivos de Protección contra amenazas avanzada</span><span class="sxs-lookup"><span data-stu-id="3c8f4-108">Advanced Threat Protection file types report</span></span>

<span data-ttu-id="3c8f4-109">El informe de **tipos de archivo de protección contra amenazas avanzada** muestra el tipo de archivos que los [datos adjuntos seguros de ATP](atp-safe-attachments.md)han detectado como malintencionados.</span><span class="sxs-lookup"><span data-stu-id="3c8f4-109">The **Advanced Threat Protection file types report** report shows you the type of files detected as malicious by [ATP Safe Attachments](atp-safe-attachments.md).</span></span>

 <span data-ttu-id="3c8f4-110">La vista agregada del informe permite 90 días de filtrado, mientras que la vista de detalles solo permite 10 días de filtrado.</span><span class="sxs-lookup"><span data-stu-id="3c8f4-110">The aggregate view of the report allows for 90 days of filtering, while the detail view only allows for 10 days of filtering.</span></span>

<span data-ttu-id="3c8f4-111">Para ver el informe, abra el [centro de seguridad & cumplimiento](https://protection.office.com), vaya **Reports** al \> **Panel** informes y seleccione **tipos de archivo ATP de Office**.</span><span class="sxs-lookup"><span data-stu-id="3c8f4-111">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Office ATP file types**.</span></span> <span data-ttu-id="3c8f4-112">Para ir directamente al informe, Abra <https://protection.office.com/reportv2?id=ATPFileReport> .</span><span class="sxs-lookup"><span data-stu-id="3c8f4-112">To go directly to the report, open <https://protection.office.com/reportv2?id=ATPFileReport>.</span></span>

![Widget de tipos de archivo de ATP de Office en el panel informes](../../media/atp-file-types-report-widget.png)

> [!NOTE]
> <span data-ttu-id="3c8f4-114">La información de este informe también está disponible en el [Informe de disposición de mensajes de protección contra amenazas avanzada](#advanced-threat-protection-message-disposition-report).</span><span class="sxs-lookup"><span data-stu-id="3c8f4-114">The information in this report is also available in the [Advanced Threat Protection message disposition report](#advanced-threat-protection-message-disposition-report).</span></span>

### <a name="report-view-for-the-advanced-threat-protection-file-types-report"></a><span data-ttu-id="3c8f4-115">Vista informes para el informe de tipos de archivo de protección contra amenazas avanzada</span><span class="sxs-lookup"><span data-stu-id="3c8f4-115">Report view for the Advanced Threat Protection file types report</span></span>

<span data-ttu-id="3c8f4-116">Están disponibles las siguientes vistas:</span><span class="sxs-lookup"><span data-stu-id="3c8f4-116">The following views are available:</span></span>

- <span data-ttu-id="3c8f4-117">**Ver datos por: archivo**: el gráfico contiene la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="3c8f4-117">**View data by: File**: The chart contains the following information:</span></span>

  - <span data-ttu-id="3c8f4-118">**Datos adjuntos de Excel malintencionados**</span><span class="sxs-lookup"><span data-stu-id="3c8f4-118">**Malicious Excel attachments**</span></span>
  - <span data-ttu-id="3c8f4-119">**Datos adjuntos de Flash malintencionados**</span><span class="sxs-lookup"><span data-stu-id="3c8f4-119">**Malicious Flash attachments**</span></span>
  - <span data-ttu-id="3c8f4-120">**Datos adjuntos de PDF malintencionados**</span><span class="sxs-lookup"><span data-stu-id="3c8f4-120">**Malicious PDF attachments**</span></span>
  - <span data-ttu-id="3c8f4-121">**Datos adjuntos de PowerPoint malintencionados**</span><span class="sxs-lookup"><span data-stu-id="3c8f4-121">**Malicious PowerPoint attachments**</span></span>
  - <span data-ttu-id="3c8f4-122">**Direcciones URL malintencionadas**</span><span class="sxs-lookup"><span data-stu-id="3c8f4-122">**Malicious URLs**</span></span>
  - <span data-ttu-id="3c8f4-123">**Datos adjuntos de Word malintencionado**</span><span class="sxs-lookup"><span data-stu-id="3c8f4-123">**Malicious Word attachments**</span></span>
  - <span data-ttu-id="3c8f4-124">**Datos adjuntos ejecutables malintencionados**</span><span class="sxs-lookup"><span data-stu-id="3c8f4-124">**Malicious executable attachments**</span></span>
  - <span data-ttu-id="3c8f4-125">**Otros**</span><span class="sxs-lookup"><span data-stu-id="3c8f4-125">**Others**</span></span>

  <span data-ttu-id="3c8f4-126">Cuando desplaza el puntero sobre un día concreto (punto de datos), puede ver el desglose de los tipos de archivos malintencionados detectados por los [datos adjuntos seguros de ATP](atp-safe-attachments.md) y la [protección antimalware en EOP](anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="3c8f4-126">When you hover over a particular day (data point), you can see the breakdown of types of malicious files that were detected by [ATP Safe Attachments](atp-safe-attachments.md) and [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

  ![Vista de archivo en el informe de tipos de archivo ATP](../../media/atp-file-types-report-file-view.png)

  <span data-ttu-id="3c8f4-128">Si hace clic en **filtros**, puede modificar el informe con los siguientes filtros:</span><span class="sxs-lookup"><span data-stu-id="3c8f4-128">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="3c8f4-129">**Fecha de inicio** y **fecha de finalización**</span><span class="sxs-lookup"><span data-stu-id="3c8f4-129">**Start date** and **End date**</span></span>
  - <span data-ttu-id="3c8f4-130">Los mismos valores de tipo de archivo que están visibles en el gráfico.</span><span class="sxs-lookup"><span data-stu-id="3c8f4-130">The same file type values that are visible in the chart.</span></span>

- <span data-ttu-id="3c8f4-131">**Ver datos por: mensaje**: el gráfico contiene la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="3c8f4-131">**View data by: Message**: The chart contains the following information:</span></span>

  - <span data-ttu-id="3c8f4-132">**Bloquear acceso**</span><span class="sxs-lookup"><span data-stu-id="3c8f4-132">**Block access**</span></span>
  - <span data-ttu-id="3c8f4-133">**Mensajes reemplazados**</span><span class="sxs-lookup"><span data-stu-id="3c8f4-133">**Messages replaced**</span></span>
  - <span data-ttu-id="3c8f4-134">**Mensajes supervisados**</span><span class="sxs-lookup"><span data-stu-id="3c8f4-134">**Messages monitored**</span></span>
  - <span data-ttu-id="3c8f4-135">**Reemplazado por la entrega de correo electrónico dinámica**: para obtener más información, vea [entrega dinámica y vista previa con datos adjuntos seguros de ATP](dynamic-delivery-and-previewing.md).</span><span class="sxs-lookup"><span data-stu-id="3c8f4-135">**Replaced by Dynamic Email Delivery**: For more information, see [Dynamic Delivery and previewing with ATP Safe Attachments](dynamic-delivery-and-previewing.md).</span></span>

  ![Vista de mensaje en el informe de tipos de archivo ATP](../../media/atp-file-types-report-message-view.png)

  <span data-ttu-id="3c8f4-137">Si hace clic en **filtros**, puede modificar el informe con los siguientes filtros:</span><span class="sxs-lookup"><span data-stu-id="3c8f4-137">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="3c8f4-138">**Fecha de inicio** y **fecha de finalización**</span><span class="sxs-lookup"><span data-stu-id="3c8f4-138">**Start date** and **End date**</span></span>
  - <span data-ttu-id="3c8f4-139">Los mismos valores de disposición de mensajes que están disponibles en el gráfico y el valor de mensajes adicionales que se **pasan** .</span><span class="sxs-lookup"><span data-stu-id="3c8f4-139">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

### <a name="details-table-view-for-the-advanced-threat-protection-file-types-report"></a><span data-ttu-id="3c8f4-140">Vista de tabla de detalles para el informe de tipos de archivo de protección contra amenazas avanzada</span><span class="sxs-lookup"><span data-stu-id="3c8f4-140">Details table view for the Advanced Threat Protection file types report</span></span>

<span data-ttu-id="3c8f4-141">Si hace clic en **ver tabla de detalles**, el informe proporciona una vista casi en tiempo real de todos los clics que ocurren dentro de la organización durante los últimos 10 días.</span><span class="sxs-lookup"><span data-stu-id="3c8f4-141">If you click **View details table**, the report provides a near-real-time view of all clicks that happen within the organization for the last 10 days.</span></span> <span data-ttu-id="3c8f4-142">La información que se muestra depende del gráfico que estaba viendo:</span><span class="sxs-lookup"><span data-stu-id="3c8f4-142">The information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="3c8f4-143">**Ver datos por: archivo**:</span><span class="sxs-lookup"><span data-stu-id="3c8f4-143">**View data by: File**:</span></span>

  - <span data-ttu-id="3c8f4-144">**Date**</span><span class="sxs-lookup"><span data-stu-id="3c8f4-144">**Date**</span></span>
  - <span data-ttu-id="3c8f4-145">**Dirección del destinatario**</span><span class="sxs-lookup"><span data-stu-id="3c8f4-145">**Recipient address**</span></span>
  - <span data-ttu-id="3c8f4-146">**Dirección del remitente**</span><span class="sxs-lookup"><span data-stu-id="3c8f4-146">**Sender address**</span></span>
  - <span data-ttu-id="3c8f4-147">**Identificador del mensaje**: disponible en el campo de encabezado del **identificador del mensaje** en el encabezado del mensaje y debe ser único.</span><span class="sxs-lookup"><span data-stu-id="3c8f4-147">**Message ID**: Available in the **Message-ID** header field in the message header and should be unique.</span></span> <span data-ttu-id="3c8f4-148">Un valor de ejemplo es `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (observe los corchetes angulares).</span><span class="sxs-lookup"><span data-stu-id="3c8f4-148">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
  - <span data-ttu-id="3c8f4-149">**Archivo**</span><span class="sxs-lookup"><span data-stu-id="3c8f4-149">**File**</span></span>

  <span data-ttu-id="3c8f4-150">Si hace clic en **filtros**, puede modificar el informe con los siguientes filtros:</span><span class="sxs-lookup"><span data-stu-id="3c8f4-150">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="3c8f4-151">**Fecha de inicio** y **fecha de finalización**</span><span class="sxs-lookup"><span data-stu-id="3c8f4-151">**Start date** and **End date**</span></span>
  - <span data-ttu-id="3c8f4-152">Los mismos valores de tipo de archivo que están visibles en el gráfico.</span><span class="sxs-lookup"><span data-stu-id="3c8f4-152">The same file type values that are visible in the chart.</span></span>

- <span data-ttu-id="3c8f4-153">**Ver datos por: mensaje**:</span><span class="sxs-lookup"><span data-stu-id="3c8f4-153">**View data by: Message**:</span></span>

  - <span data-ttu-id="3c8f4-154">**Date**</span><span class="sxs-lookup"><span data-stu-id="3c8f4-154">**Date**</span></span>
  - <span data-ttu-id="3c8f4-155">**Dirección del destinatario**</span><span class="sxs-lookup"><span data-stu-id="3c8f4-155">**Recipient address**</span></span>
  - <span data-ttu-id="3c8f4-156">**Dirección del remitente**</span><span class="sxs-lookup"><span data-stu-id="3c8f4-156">**Sender address**</span></span>
  - <span data-ttu-id="3c8f4-157">**Id. de mensaje**</span><span class="sxs-lookup"><span data-stu-id="3c8f4-157">**Message ID**</span></span>
  - <span data-ttu-id="3c8f4-158">**Archivo**</span><span class="sxs-lookup"><span data-stu-id="3c8f4-158">**File**</span></span>
  - <span data-ttu-id="3c8f4-159">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="3c8f4-159">**Subject**</span></span>

  <span data-ttu-id="3c8f4-160">Si hace clic en **filtros**, puede modificar los resultados con los siguientes filtros:</span><span class="sxs-lookup"><span data-stu-id="3c8f4-160">If you click **Filters**, you can modify the results with the following filters:</span></span>

  - <span data-ttu-id="3c8f4-161">**Fecha de inicio** y **fecha de finalización**</span><span class="sxs-lookup"><span data-stu-id="3c8f4-161">**Start date** and **End date**</span></span>
  - <span data-ttu-id="3c8f4-162">Los mismos valores de disposición de mensajes que están disponibles en el gráfico y el valor de mensajes adicionales que se **pasan** .</span><span class="sxs-lookup"><span data-stu-id="3c8f4-162">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

<span data-ttu-id="3c8f4-163">Para volver a la vista informes, haga clic en **Ver informe**.</span><span class="sxs-lookup"><span data-stu-id="3c8f4-163">To get back to the reports view, click **View report**.</span></span>

## <a name="advanced-threat-protection-message-disposition-report"></a><span data-ttu-id="3c8f4-164">Informe de eliminación de mensajes de Protección contra amenazas avanzada</span><span class="sxs-lookup"><span data-stu-id="3c8f4-164">Advanced Threat Protection message disposition report</span></span>

<span data-ttu-id="3c8f4-165">El informe de **disposición de mensajes de ATP** muestra las acciones que se tomaron para los mensajes de correo electrónico que se detectaron con contenido malintencionado.</span><span class="sxs-lookup"><span data-stu-id="3c8f4-165">The **ATP Message Disposition** report shows you the actions that were taken for email messages that were detected as having malicious content.</span></span>

<span data-ttu-id="3c8f4-166">Para ver el informe, abra el [centro de seguridad & cumplimiento](https://protection.office.com), vaya **Reports** al \> **Panel** informes y seleccione **disposición de mensajes ATP de Office**.</span><span class="sxs-lookup"><span data-stu-id="3c8f4-166">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Office ATP message disposition**.</span></span> <span data-ttu-id="3c8f4-167">Para ir directamente al informe, Abra <https://protection.office.com/reportv2?id=ATPMessageReport> .</span><span class="sxs-lookup"><span data-stu-id="3c8f4-167">To go directly to the report, open <https://protection.office.com/reportv2?id=ATPMessageReport>.</span></span>

![Widget de disposición de mensajes de ATP de Office 365 en el panel de informes](../../media/atp-message-disposition-report-widget.png)

> [!NOTE]
> <span data-ttu-id="3c8f4-169">La información de este informe también está disponible en el [Informe de tipos de archivo de protección contra amenazas avanzada](#advanced-threat-protection-file-types-report).</span><span class="sxs-lookup"><span data-stu-id="3c8f4-169">The information in this report is also available in the [Advanced Threat Protection file types report](#advanced-threat-protection-file-types-report).</span></span>

### <a name="report-view-for-the-advanced-threat-protection-message-disposition-report"></a><span data-ttu-id="3c8f4-170">Vista informes para el informe de disposición de mensajes de protección contra amenazas avanzada</span><span class="sxs-lookup"><span data-stu-id="3c8f4-170">Report view for the Advanced Threat Protection message disposition report</span></span>

<span data-ttu-id="3c8f4-171">Están disponibles las siguientes vistas:</span><span class="sxs-lookup"><span data-stu-id="3c8f4-171">The following views are available:</span></span>

- <span data-ttu-id="3c8f4-172">**Ver datos por: mensaje**: el gráfico contiene la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="3c8f4-172">**View data by: Message**: The chart contains the following information:</span></span>

  - <span data-ttu-id="3c8f4-173">**Bloquear acceso**</span><span class="sxs-lookup"><span data-stu-id="3c8f4-173">**Block access**</span></span>
  - <span data-ttu-id="3c8f4-174">**Mensajes reemplazados**</span><span class="sxs-lookup"><span data-stu-id="3c8f4-174">**Messages replaced**</span></span>
  - <span data-ttu-id="3c8f4-175">**Mensajes supervisados**</span><span class="sxs-lookup"><span data-stu-id="3c8f4-175">**Messages monitored**</span></span>
  - <span data-ttu-id="3c8f4-176">**Reemplazado por la entrega de correo electrónico dinámica**: para obtener más información, vea [entrega dinámica y vista previa con datos adjuntos seguros de ATP](dynamic-delivery-and-previewing.md).</span><span class="sxs-lookup"><span data-stu-id="3c8f4-176">**Replaced by Dynamic Email Delivery**: For more information, see [Dynamic Delivery and previewing with ATP Safe Attachments](dynamic-delivery-and-previewing.md).</span></span>

  ![Vista de mensaje en el informe de tipos de archivo ATP](../../media/atp-file-types-report-message-view.png)

  <span data-ttu-id="3c8f4-178">Si hace clic en **filtros**, puede modificar el informe con los siguientes filtros:</span><span class="sxs-lookup"><span data-stu-id="3c8f4-178">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="3c8f4-179">**Fecha de inicio** y **fecha de finalización**</span><span class="sxs-lookup"><span data-stu-id="3c8f4-179">**Start date** and **End date**</span></span>
  - <span data-ttu-id="3c8f4-180">Los mismos valores de disposición de mensajes que están disponibles en el gráfico y el valor de mensajes adicionales que se **pasan** .</span><span class="sxs-lookup"><span data-stu-id="3c8f4-180">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

- <span data-ttu-id="3c8f4-181">**Ver datos por: archivo**: el gráfico contiene la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="3c8f4-181">**View data by: File**: The chart contains the following information:</span></span>

  - <span data-ttu-id="3c8f4-182">**Datos adjuntos de Excel malintencionados**</span><span class="sxs-lookup"><span data-stu-id="3c8f4-182">**Malicious Excel attachments**</span></span>
  - <span data-ttu-id="3c8f4-183">**Datos adjuntos de Flash malintencionados**</span><span class="sxs-lookup"><span data-stu-id="3c8f4-183">**Malicious Flash attachments**</span></span>
  - <span data-ttu-id="3c8f4-184">**Datos adjuntos de PDF malintencionados**</span><span class="sxs-lookup"><span data-stu-id="3c8f4-184">**Malicious PDF attachments**</span></span>
  - <span data-ttu-id="3c8f4-185">**Datos adjuntos de PowerPoint malintencionados**</span><span class="sxs-lookup"><span data-stu-id="3c8f4-185">**Malicious PowerPoint attachments**</span></span>
  - <span data-ttu-id="3c8f4-186">**Direcciones URL malintencionadas**</span><span class="sxs-lookup"><span data-stu-id="3c8f4-186">**Malicious URLs**</span></span>
  - <span data-ttu-id="3c8f4-187">**Datos adjuntos de Word malintencionado**</span><span class="sxs-lookup"><span data-stu-id="3c8f4-187">**Malicious Word attachments**</span></span>
  - <span data-ttu-id="3c8f4-188">**Datos adjuntos ejecutables malintencionados**</span><span class="sxs-lookup"><span data-stu-id="3c8f4-188">**Malicious executable attachments**</span></span>
  - <span data-ttu-id="3c8f4-189">**Otros**</span><span class="sxs-lookup"><span data-stu-id="3c8f4-189">**Others**</span></span>

  <span data-ttu-id="3c8f4-190">Cuando desplaza el puntero sobre un día concreto (punto de datos), puede ver el desglose de los tipos de archivos malintencionados detectados por los [datos adjuntos seguros de ATP](atp-safe-attachments.md) y la [protección antimalware en EOP](anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="3c8f4-190">When you hover over a particular day (data point), you can see the breakdown of types of malicious files that were detected by [ATP Safe Attachments](atp-safe-attachments.md) and [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

  ![Vista de archivo en el informe de tipos de archivo ATP](../../media/atp-file-types-report-file-view.png)

  <span data-ttu-id="3c8f4-192">Si hace clic en **filtros**, puede modificar el informe con los siguientes filtros:</span><span class="sxs-lookup"><span data-stu-id="3c8f4-192">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="3c8f4-193">**Fecha de inicio** y **fecha de finalización**</span><span class="sxs-lookup"><span data-stu-id="3c8f4-193">**Start date** and **End date**</span></span>
  - <span data-ttu-id="3c8f4-194">Los mismos valores de tipo de archivo que están visibles en el gráfico.</span><span class="sxs-lookup"><span data-stu-id="3c8f4-194">The same file type values that are visible in the chart.</span></span>

### <a name="details-table-view-for-the-advanced-threat-protection-message-disposition-report"></a><span data-ttu-id="3c8f4-195">Vista de tabla de detalles para el informe de disposición de mensajes de protección contra amenazas avanzada</span><span class="sxs-lookup"><span data-stu-id="3c8f4-195">Details table view for the Advanced Threat Protection message disposition report</span></span>

<span data-ttu-id="3c8f4-196">Si hace clic en **ver tabla de detalles**, el informe proporciona una vista casi en tiempo real de todos los clics que ocurren dentro de la organización durante los últimos 10 días.</span><span class="sxs-lookup"><span data-stu-id="3c8f4-196">If you click **View details table**, the report provides a near-real-time view of all clicks that happen within the organization for the last 10 days.</span></span> <span data-ttu-id="3c8f4-197">La información que se muestra depende del gráfico que estaba viendo:</span><span class="sxs-lookup"><span data-stu-id="3c8f4-197">The information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="3c8f4-198">**Ver datos por: mensaje**:</span><span class="sxs-lookup"><span data-stu-id="3c8f4-198">**View data by: Message**:</span></span>

  - <span data-ttu-id="3c8f4-199">**Date**</span><span class="sxs-lookup"><span data-stu-id="3c8f4-199">**Date**</span></span>
  - <span data-ttu-id="3c8f4-200">**Dirección del destinatario**</span><span class="sxs-lookup"><span data-stu-id="3c8f4-200">**Recipient address**</span></span>
  - <span data-ttu-id="3c8f4-201">**Dirección del remitente**</span><span class="sxs-lookup"><span data-stu-id="3c8f4-201">**Sender address**</span></span>
  - <span data-ttu-id="3c8f4-202">**Id. de mensaje**</span><span class="sxs-lookup"><span data-stu-id="3c8f4-202">**Message ID**</span></span>
  - <span data-ttu-id="3c8f4-203">**Archivo**</span><span class="sxs-lookup"><span data-stu-id="3c8f4-203">**File**</span></span>
  - <span data-ttu-id="3c8f4-204">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="3c8f4-204">**Subject**</span></span>

  <span data-ttu-id="3c8f4-205">Si hace clic en **filtros**, puede modificar los resultados con los siguientes filtros:</span><span class="sxs-lookup"><span data-stu-id="3c8f4-205">If you click **Filters**, you can modify the results with the following filters:</span></span>

  - <span data-ttu-id="3c8f4-206">**Fecha de inicio** y **fecha de finalización**</span><span class="sxs-lookup"><span data-stu-id="3c8f4-206">**Start date** and **End date**</span></span>
  - <span data-ttu-id="3c8f4-207">Los mismos valores de disposición de mensajes que están disponibles en el gráfico y el valor de mensajes adicionales que se **pasan** .</span><span class="sxs-lookup"><span data-stu-id="3c8f4-207">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

- <span data-ttu-id="3c8f4-208">**Ver datos por: archivo**:</span><span class="sxs-lookup"><span data-stu-id="3c8f4-208">**View data by: File**:</span></span>

  - <span data-ttu-id="3c8f4-209">**Date**</span><span class="sxs-lookup"><span data-stu-id="3c8f4-209">**Date**</span></span>
  - <span data-ttu-id="3c8f4-210">**Dirección del destinatario**</span><span class="sxs-lookup"><span data-stu-id="3c8f4-210">**Recipient address**</span></span>
  - <span data-ttu-id="3c8f4-211">**Dirección del remitente**</span><span class="sxs-lookup"><span data-stu-id="3c8f4-211">**Sender address**</span></span>
  - <span data-ttu-id="3c8f4-212">**Id. de mensaje**</span><span class="sxs-lookup"><span data-stu-id="3c8f4-212">**Message ID**</span></span>
  - <span data-ttu-id="3c8f4-213">**Archivo**</span><span class="sxs-lookup"><span data-stu-id="3c8f4-213">**File**</span></span>

  <span data-ttu-id="3c8f4-214">Si hace clic en **filtros**, puede modificar el informe con los siguientes filtros:</span><span class="sxs-lookup"><span data-stu-id="3c8f4-214">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="3c8f4-215">**Fecha de inicio** y **fecha de finalización**</span><span class="sxs-lookup"><span data-stu-id="3c8f4-215">**Start date** and **End date**</span></span>
  - <span data-ttu-id="3c8f4-216">Los mismos valores de tipo de archivo que están visibles en el gráfico.</span><span class="sxs-lookup"><span data-stu-id="3c8f4-216">The same file type values that are visible in the chart.</span></span>

<span data-ttu-id="3c8f4-217">Para volver a la vista informes, haga clic en **Ver informe**.</span><span class="sxs-lookup"><span data-stu-id="3c8f4-217">To get back to the reports view, click **View report**.</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="3c8f4-218">Informe de estado de protección contra amenazas</span><span class="sxs-lookup"><span data-stu-id="3c8f4-218">Threat protection status report</span></span>

<span data-ttu-id="3c8f4-219">El informe de **Estado de protección contra amenazas** es una vista única que reúne información sobre contenido malintencionado y correo electrónico malintencionado detectado y bloqueado por [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) y Office 365 ATP.</span><span class="sxs-lookup"><span data-stu-id="3c8f4-219">The **Threat protection status** report is a single view that brings together information about malicious content and malicious email detected and blocked by [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) and Office 365 ATP.</span></span> <span data-ttu-id="3c8f4-220">Para obtener más información, consulte [Informe de estado de protección contra amenazas](view-email-security-reports.md#threat-protection-status-report).</span><span class="sxs-lookup"><span data-stu-id="3c8f4-220">For more information, see [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>

## <a name="url-threat-protection-report"></a><span data-ttu-id="3c8f4-221">Informe de protección contra amenazas de URL</span><span class="sxs-lookup"><span data-stu-id="3c8f4-221">URL threat protection report</span></span>

<span data-ttu-id="3c8f4-222">El **Informe de protección contra amenazas de direcciones URL** proporciona vistas de Resumen y tendencias para las amenazas detectadas y las acciones tomadas en los clics de direcciones URL como parte de los [vínculos seguros ATP](atp-safe-links.md).</span><span class="sxs-lookup"><span data-stu-id="3c8f4-222">The **URL threat protection report** provides summary and trend views for threats detected and actions taken on URL clicks as part of [ATP Safe Links](atp-safe-links.md).</span></span> <span data-ttu-id="3c8f4-223">Este informe no tendrá hacer clic en datos de usuarios en los que la Directiva de vínculos seguros aplicada tiene seleccionada la opción no hacer **un seguimiento de los clics del usuario** .</span><span class="sxs-lookup"><span data-stu-id="3c8f4-223">This report will not have click data from users where the Safe Links policy applied has the **Do not track user clicks** option selected.</span></span>

<span data-ttu-id="3c8f4-224">Para ver el informe, abra el [centro de seguridad & cumplimiento](https://protection.office.com), vaya a **informes** de \> **Panel** y seleccione **Informe de protección de URL**.</span><span class="sxs-lookup"><span data-stu-id="3c8f4-224">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **URL protection report**.</span></span> <span data-ttu-id="3c8f4-225">Para ir directamente al informe, Abra <https://protection.office.com/reportv2?id=URLProtectionActionReport> .</span><span class="sxs-lookup"><span data-stu-id="3c8f4-225">To go directly to the report, open <https://protection.office.com/reportv2?id=URLProtectionActionReport>.</span></span>

![Widget de informe de protección de URL en el panel informes](../../media/url-protection-report-widget.png)

> [!NOTE]
> <span data-ttu-id="3c8f4-227">Se trata de un *Informe de tendencias de protección*, lo que significa que los datos representan tendencias en un conjunto de datos más grande.</span><span class="sxs-lookup"><span data-stu-id="3c8f4-227">This is a *protection trend report*, meaning data represents trends in a larger dataset.</span></span> <span data-ttu-id="3c8f4-228">Como resultado, los datos de la vista de agregado no están disponibles en tiempo real aquí, pero los datos de la vista de tabla de detalles son, por lo que es posible que vea una ligera diferencia entre las dos vistas.</span><span class="sxs-lookup"><span data-stu-id="3c8f4-228">As a result, the data in the aggregate view is not available in real time here, but the data in the details table view is, so you may see a slight discrepancy between the two views.</span></span>

### <a name="report-view-for-the-url-threat-protection-report"></a><span data-ttu-id="3c8f4-229">Vista informes para el informe de protección contra amenazas de direcciones URL</span><span class="sxs-lookup"><span data-stu-id="3c8f4-229">Report view for the URL threat protection report</span></span>

<span data-ttu-id="3c8f4-230">El informe de **protección contra amenazas de direcciones URL** tiene dos vistas agregadas que se actualizan una vez cada cuatro horas que muestra datos para los últimos 90 días:</span><span class="sxs-lookup"><span data-stu-id="3c8f4-230">The **URL threat protection** report has two aggregated views that are refreshed once every four hours that shows data for the last 90 days:</span></span>

- <span data-ttu-id="3c8f4-231">**Hacer clic en dirección URL acción de protección**: muestra el número de clics de direcciones URL por parte de los usuarios de la organización y los resultados del clic:</span><span class="sxs-lookup"><span data-stu-id="3c8f4-231">**URL click protection action**: Shows the number of URL clicks by users in the organization and the results of the click:</span></span>

  - <span data-ttu-id="3c8f4-232">**Bloqueado** (se ha bloqueado al usuario para que navegue a la dirección URL)</span><span class="sxs-lookup"><span data-stu-id="3c8f4-232">**Blocked** (the user was blocked from navigating to the URL)</span></span>
  - <span data-ttu-id="3c8f4-233">**Bloqueado y clic en**</span><span class="sxs-lookup"><span data-stu-id="3c8f4-233">**Blocked and clicked through**</span></span>
  - <span data-ttu-id="3c8f4-234">**Clic durante el examen**</span><span class="sxs-lookup"><span data-stu-id="3c8f4-234">**Clicked through during scan**</span></span>

  <span data-ttu-id="3c8f4-235">Un clic indica que el usuario ha acpulsado a través de la página de bloque al sitio Web malintencionado (los administradores pueden deshabilitar el clic en las directivas de vínculos a prueba de errores).</span><span class="sxs-lookup"><span data-stu-id="3c8f4-235">A click indicates that the user has clicked through the block page to the malicious website (admins can disable click through in Safe Links policies).</span></span>

  <span data-ttu-id="3c8f4-236">Si hace clic en **filtros**, puede modificar el informe con los siguientes filtros:</span><span class="sxs-lookup"><span data-stu-id="3c8f4-236">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="3c8f4-237">**Fecha de inicio** y **fecha de finalización**</span><span class="sxs-lookup"><span data-stu-id="3c8f4-237">**Start date** and **End date**</span></span>
  - <span data-ttu-id="3c8f4-238">Las acciones de clic en protección disponibles, más el valor **permitido** (el usuario tuvo permiso para navegar a la dirección URL).</span><span class="sxs-lookup"><span data-stu-id="3c8f4-238">The available click protection actions, plus the value **Allowed** (the user was allowed to navigate to the URL).</span></span>

  ![Vista de dirección URL haga clic en acción de protección en el informe de protección contra amenazas URL](../../media/url-threat-protection-report-url-click-protection-action-view.png)

- <span data-ttu-id="3c8f4-240">**Dirección URL haga clic en por aplicación**: muestra el número de clics de direcciones URL por aplicaciones compatibles con Office 365 ATP vínculos seguros:</span><span class="sxs-lookup"><span data-stu-id="3c8f4-240">**URL click by application**: Shows the number of URL clicks by applications that support Office 365 ATP Safe Links:</span></span>

  - <span data-ttu-id="3c8f4-241">**Cliente de correo electrónico**</span><span class="sxs-lookup"><span data-stu-id="3c8f4-241">**Email client**</span></span>
  - <span data-ttu-id="3c8f4-242">**PowerPoint**</span><span class="sxs-lookup"><span data-stu-id="3c8f4-242">**PowerPoint**</span></span>
  - <span data-ttu-id="3c8f4-243">**Word**</span><span class="sxs-lookup"><span data-stu-id="3c8f4-243">**Word**</span></span>
  - <span data-ttu-id="3c8f4-244">**Excel**</span><span class="sxs-lookup"><span data-stu-id="3c8f4-244">**Excel**</span></span>
  - <span data-ttu-id="3c8f4-245">**OneNote**</span><span class="sxs-lookup"><span data-stu-id="3c8f4-245">**OneNote**</span></span>
  - <span data-ttu-id="3c8f4-246">**Visio**</span><span class="sxs-lookup"><span data-stu-id="3c8f4-246">**Visio**</span></span>
  - <span data-ttu-id="3c8f4-247">**Teams**</span><span class="sxs-lookup"><span data-stu-id="3c8f4-247">**Teams**</span></span>
  - <span data-ttu-id="3c8f4-248">**Otros**</span><span class="sxs-lookup"><span data-stu-id="3c8f4-248">**Other**</span></span>

  <span data-ttu-id="3c8f4-249">Si hace clic en **filtros**, puede modificar el informe con los siguientes filtros:</span><span class="sxs-lookup"><span data-stu-id="3c8f4-249">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="3c8f4-250">**Fecha de inicio** y **fecha de finalización**</span><span class="sxs-lookup"><span data-stu-id="3c8f4-250">**Start date** and **End date**</span></span>
  - <span data-ttu-id="3c8f4-251">Las aplicaciones disponibles.</span><span class="sxs-lookup"><span data-stu-id="3c8f4-251">The available applications.</span></span>

### <a name="details-table-view-for-the-url-threat-protection-report"></a><span data-ttu-id="3c8f4-252">Vista de tabla de detalles para el informe de protección contra amenazas de direcciones URL</span><span class="sxs-lookup"><span data-stu-id="3c8f4-252">Details table view for the URL threat protection report</span></span>

<span data-ttu-id="3c8f4-253">Si hace clic en **ver tabla de detalles**, el informe proporciona una vista casi en tiempo real de todos los clics que ocurren dentro de la organización en los últimos 7 días con los siguientes detalles:</span><span class="sxs-lookup"><span data-stu-id="3c8f4-253">If you click **View details table**, the report provides a near-real-time view of all clicks that happen within the organization for the last 7 days with the following details:</span></span>

- <span data-ttu-id="3c8f4-254">**Haga clic en hora**</span><span class="sxs-lookup"><span data-stu-id="3c8f4-254">**Click time**</span></span>
- <span data-ttu-id="3c8f4-255">**User**</span><span class="sxs-lookup"><span data-stu-id="3c8f4-255">**User**</span></span>
- <span data-ttu-id="3c8f4-256">**URL**</span><span class="sxs-lookup"><span data-stu-id="3c8f4-256">**URL**</span></span>
- <span data-ttu-id="3c8f4-257">**Acción**</span><span class="sxs-lookup"><span data-stu-id="3c8f4-257">**Action**</span></span>
- <span data-ttu-id="3c8f4-258">**App**</span><span class="sxs-lookup"><span data-stu-id="3c8f4-258">**App**</span></span>

<span data-ttu-id="3c8f4-259">Si hace clic en **filtros** en la vista de tabla de detalles, puede filtrar por los mismos criterios que en la vista de informe y también por **dominios** o **destinatarios** separados por comas.</span><span class="sxs-lookup"><span data-stu-id="3c8f4-259">If you click **Filters** in the details table view, you can filter by the same criteria as in the report view, and also by **Domains** or **Recipients** separated by commas.</span></span>

<span data-ttu-id="3c8f4-260">Para volver a la vista informes, haga clic en **Ver informe**.</span><span class="sxs-lookup"><span data-stu-id="3c8f4-260">To get back to the reports view, click **View report**.</span></span>

## <a name="additional-reports-to-view"></a><span data-ttu-id="3c8f4-261">Informes adicionales para ver</span><span class="sxs-lookup"><span data-stu-id="3c8f4-261">Additional reports to view</span></span>

<span data-ttu-id="3c8f4-262">Además de los informes de ATP descritos en este tema, hay disponibles varios informes más, como se describe en la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="3c8f4-262">In addition to the ATP reports described in this topic, several other reports are available, as described in the following table:</span></span>

****

|<span data-ttu-id="3c8f4-263">Informe</span><span class="sxs-lookup"><span data-stu-id="3c8f4-263">Report</span></span>|<span data-ttu-id="3c8f4-264">Tema</span><span class="sxs-lookup"><span data-stu-id="3c8f4-264">Topic</span></span>|
|---|---|
|<span data-ttu-id="3c8f4-265">**Explorador** (ATP plan 2) o **detecciones en tiempo real** (plan de ATP 1)</span><span class="sxs-lookup"><span data-stu-id="3c8f4-265">**Explorer** (ATP Plan 2) or **real-time detections** (ATP Plan 1)</span></span>|[<span data-ttu-id="3c8f4-266">Explorador de amenazas (y detecciones en tiempo real)</span><span class="sxs-lookup"><span data-stu-id="3c8f4-266">Threat Explorer (and real-time detections)</span></span>](threat-explorer.md)|
|<span data-ttu-id="3c8f4-267">**Informes de seguridad de correo electrónico**, como el informe de remitentes y destinatarios principales, el informe de correo falsificado y el informe de detecciones de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="3c8f4-267">**Email security reports**, such as the Top senders and recipients report, the Spoof mail report, and the Spam detections report.</span></span>|[<span data-ttu-id="3c8f4-268">Ver informes de seguridad de correo electrónico en el Centro de seguridad y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="3c8f4-268">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)|
|<span data-ttu-id="3c8f4-269">**Informes de flujo de correo**, como el informe de reenvío, el informe de estado de flujo de correo y el informe de remitentes y destinatarios principales.</span><span class="sxs-lookup"><span data-stu-id="3c8f4-269">**Mail flow reports**, such as the Forwarding report, the Mailflow status report, and the Top senders and recipients report.</span></span>|[<span data-ttu-id="3c8f4-270">Ver informes de flujo de correo en el centro de seguridad & cumplimiento</span><span class="sxs-lookup"><span data-stu-id="3c8f4-270">View mail flow reports in the Security & Compliance Center</span></span>](view-mail-flow-reports.md)|
|<span data-ttu-id="3c8f4-271">**Seguimiento de dirección URL para vínculos seguros ATP** (solo PowerShell).</span><span class="sxs-lookup"><span data-stu-id="3c8f4-271">**URL trace for ATP Safe Links** (PowerShell only).</span></span> <span data-ttu-id="3c8f4-272">El resultado de este cmdlet muestra los resultados de las acciones de vínculos seguros de ATP en los últimos siete días.</span><span class="sxs-lookup"><span data-stu-id="3c8f4-272">The output of this cmdlet shows you the results of ATP Safe Links actions over the past seven days.</span></span>|[<span data-ttu-id="3c8f4-273">Get-UrlTrace</span><span class="sxs-lookup"><span data-stu-id="3c8f4-273">Get-UrlTrace</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-urltrace)|
|<span data-ttu-id="3c8f4-274">**Resultados del tráfico de correo para EOP y ATP** (solo PowerShell).</span><span class="sxs-lookup"><span data-stu-id="3c8f4-274">**Mail traffic results for EOP and ATP** (PowerShell only).</span></span> <span data-ttu-id="3c8f4-275">El resultado de este cmdlet contiene información sobre el dominio, la fecha, el tipo de evento, la dirección, la acción y el recuento de mensajes.</span><span class="sxs-lookup"><span data-stu-id="3c8f4-275">The output of this cmdlet contains information about Domain, Date, Event Type, Direction, Action, and Message Count.</span></span>|[<span data-ttu-id="3c8f4-276">Get-MailTrafficATPReport</span><span class="sxs-lookup"><span data-stu-id="3c8f4-276">Get-MailTrafficATPReport</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-mailtrafficatpreport)|
|<span data-ttu-id="3c8f4-277">**Informes de detalles de correo para detecciones de EOP y ATP** (solo PowerShell).</span><span class="sxs-lookup"><span data-stu-id="3c8f4-277">**Mail detail reports for EOP and ATP detections** (PowerShell only).</span></span> <span data-ttu-id="3c8f4-278">El resultado de este cmdlet contiene detalles sobre archivos malintencionados o direcciones URL, intentos de suplantación de identidad (phishing), suplantación y otras amenazas potenciales en el correo electrónico o los archivos.</span><span class="sxs-lookup"><span data-stu-id="3c8f4-278">The output of this cmdlet contains details about malicious files or URLs, phishing attempts, impersonation, and other potential threats in email or files.</span></span>|[<span data-ttu-id="3c8f4-279">Get-MailDetailATPReport</span><span class="sxs-lookup"><span data-stu-id="3c8f4-279">Get-MailDetailATPReport</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-maildetailatpreport)|
|

## <a name="what-permissions-are-needed-to-view-the-atp-reports"></a><span data-ttu-id="3c8f4-280">¿Qué permisos se necesitan para ver los informes de ATP?</span><span class="sxs-lookup"><span data-stu-id="3c8f4-280">What permissions are needed to view the ATP reports?</span></span>

<span data-ttu-id="3c8f4-281">Para poder ver y usar los informes descritos en este tema, **debe tener asignada una función adecuada para el centro de seguridad &amp; y cumplimiento y el centro de administración de Exchange**.</span><span class="sxs-lookup"><span data-stu-id="3c8f4-281">In order to view and use the reports described in this topic, **you must have an appropriate role assigned for both the Security &amp; Compliance Center and the Exchange admin center**.</span></span>

- <span data-ttu-id="3c8f4-282">Para el centro de seguridad & cumplimiento, debe tener asignada una de las siguientes funciones:</span><span class="sxs-lookup"><span data-stu-id="3c8f4-282">For the Security & Compliance Center, you must have one of the following roles assigned:</span></span>

  - <span data-ttu-id="3c8f4-283">Administración de la organización</span><span class="sxs-lookup"><span data-stu-id="3c8f4-283">Organization Management</span></span>
  - <span data-ttu-id="3c8f4-284">Administrador de seguridad (puede asignarse en el centro de administración de Azure Active Directory ( [https://aad.portal.azure.com](https://aad.portal.azure.com) ))</span><span class="sxs-lookup"><span data-stu-id="3c8f4-284">Security Administrator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span></span>
  - <span data-ttu-id="3c8f4-285">Operador de seguridad (puede asignarse en el centro de administración de Azure Active Directory ( [https://aad.portal.azure.com](https://aad.portal.azure.com) ))</span><span class="sxs-lookup"><span data-stu-id="3c8f4-285">Security Operator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span></span>
  - <span data-ttu-id="3c8f4-286">Lector de seguridad</span><span class="sxs-lookup"><span data-stu-id="3c8f4-286">Security Reader</span></span>

- <span data-ttu-id="3c8f4-287">Para Exchange Online, debe tener una de las siguientes funciones asignadas en el centro de administración de Exchange ( [https://outlook.office365.com/ecp](https://outlook.office365.com/ecp) ) o con cmdlets de PowerShell (vea [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)):</span><span class="sxs-lookup"><span data-stu-id="3c8f4-287">For Exchange Online, you must have one of the following roles assigned in either the Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) or with PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)):</span></span>

  - <span data-ttu-id="3c8f4-288">Administración de la organización</span><span class="sxs-lookup"><span data-stu-id="3c8f4-288">Organization Management</span></span>
  - <span data-ttu-id="3c8f4-289">Administración de organización de solo lectura</span><span class="sxs-lookup"><span data-stu-id="3c8f4-289">View-only Organization Management</span></span>
  - <span data-ttu-id="3c8f4-290">Rol Destinatarios con permiso de vista</span><span class="sxs-lookup"><span data-stu-id="3c8f4-290">View-Only Recipients role</span></span>
  - <span data-ttu-id="3c8f4-291">Administración de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="3c8f4-291">Compliance Management</span></span>

<span data-ttu-id="3c8f4-292">Para obtener más información, consulte los siguientes recursos:</span><span class="sxs-lookup"><span data-stu-id="3c8f4-292">To learn more, see the following resources:</span></span>

- [<span data-ttu-id="3c8f4-293">Permisos en el Centro de seguridad y cumplimiento </span><span class="sxs-lookup"><span data-stu-id="3c8f4-293">Permissions in the Security & Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)

- [<span data-ttu-id="3c8f4-294">Permisos de características de Exchange Online</span><span class="sxs-lookup"><span data-stu-id="3c8f4-294">Feature permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="3c8f4-295">¿Qué ocurre si los informes no muestran datos?</span><span class="sxs-lookup"><span data-stu-id="3c8f4-295">What if the reports aren't showing data?</span></span>

<span data-ttu-id="3c8f4-296">Si no ve datos en los informes de ATP, compruebe que las directivas estén correctamente configuradas.</span><span class="sxs-lookup"><span data-stu-id="3c8f4-296">If you are not seeing data in your ATP reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="3c8f4-297">La organización debe tener directivas de [vínculos seguros ATP](set-up-atp-safe-links-policies.md) y [directivas de datos adjuntos seguros ATP](set-up-atp-safe-attachments-policies.md) definidas para que la protección de ATP esté en su lugar.</span><span class="sxs-lookup"><span data-stu-id="3c8f4-297">Your organization must have [ATP Safe Links policies](set-up-atp-safe-links-policies.md) and [ATP Safe Attachments policies](set-up-atp-safe-attachments-policies.md) defined in order for ATP protection to be in place.</span></span> <span data-ttu-id="3c8f4-298">Consulte también [protección contra correo no deseado y antimalware en Office 365](anti-spam-and-anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="3c8f4-298">Also see [Anti-spam and anti-malware protection in Office 365](anti-spam-and-anti-malware-protection.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="3c8f4-299">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="3c8f4-299">Related topics</span></span>

[<span data-ttu-id="3c8f4-300">Informes inteligentes y reportes en el Centro de seguridad y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="3c8f4-300">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)
  
[<span data-ttu-id="3c8f4-301">Permisos de funciones (Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="3c8f4-301">Role permissions (Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#role-permissions)
