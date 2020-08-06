---
title: Ver informes de flujo de correo en el panel de informes
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
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Los administradores pueden obtener información sobre los informes de flujo de correo que están disponibles en el panel informes del centro de seguridad & cumplimiento.
ms.custom: ''
ms.openlocfilehash: 69b2c3383862860b4616d95c2a6a1bb3a525d842
ms.sourcegitcommit: c04f1207cfaddac2a9abef38967c17d689756a96
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2020
ms.locfileid: "46578023"
---
# <a name="view-mail-flow-reports-in-the-reports-dashboard-in-security--compliance-center"></a><span data-ttu-id="aa9ca-103">Ver informes de flujo de correo en el panel informes del centro de seguridad & cumplimiento</span><span class="sxs-lookup"><span data-stu-id="aa9ca-103">View mail flow reports in the Reports dashboard in Security & Compliance Center</span></span>

<span data-ttu-id="aa9ca-104">Además de los informes de flujo de correo que están disponibles en el [panel del flujo de correo](mail-flow-insights-v2.md) en el centro de seguridad & cumplimiento, hay disponible una variedad de informes de flujo de correo adicionales en el panel de informes para ayudarle a supervisar su organización de 365 de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="aa9ca-104">In addition to the mail flow reports that are available in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center, a variety of additional mail flow reports are available in the Reports dashboard to help you monitor your Microsoft 365 organization.</span></span>

<span data-ttu-id="aa9ca-105">Si dispone de los [permisos necesarios](#what-permissions-are-needed-to-view-these-reports), puede ver estos informes en el [centro de seguridad & cumplimiento](https://office.protection.com) desde el panel de **informes** \> **Dashboard**.</span><span class="sxs-lookup"><span data-stu-id="aa9ca-105">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the [Security & Compliance Center](https://office.protection.com) by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="aa9ca-106">Para ir directamente al panel informes, Abra <https://office.protection.office.com/insightdashboard> .</span><span class="sxs-lookup"><span data-stu-id="aa9ca-106">To go directly to the Reports dashboard, open <https://office.protection.office.com/insightdashboard>.</span></span>

![Panel de informes en el centro de seguridad & cumplimiento](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="connector-report"></a><span data-ttu-id="aa9ca-108">Informe de conector</span><span class="sxs-lookup"><span data-stu-id="aa9ca-108">Connector report</span></span>

<span data-ttu-id="aa9ca-109">El **Informe de conectores** muestra la actividad de flujo de correo en los [conectores entrantes y](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) salientes que están configurados para su organización.</span><span class="sxs-lookup"><span data-stu-id="aa9ca-109">The **Connector report** shows mail flow activity on the [inbound and outbound connectors](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) that are configured for your organization.</span></span>

<span data-ttu-id="aa9ca-110">Para ver el informe, abra el [centro de seguridad & cumplimiento](https://protection.office.com), vaya **Reports** al \> **Panel** informes y seleccione **Informe de conector**.</span><span class="sxs-lookup"><span data-stu-id="aa9ca-110">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Connector report**.</span></span> <span data-ttu-id="aa9ca-111">Para ir directamente al informe, Abra <https://protection.office.com/reportv2?id=ConnectorReport> .</span><span class="sxs-lookup"><span data-stu-id="aa9ca-111">To go directly to the report, open <https://protection.office.com/reportv2?id=ConnectorReport>.</span></span>

![Widget de informe de conectores en el panel de informes](../../media/connector-report-widget.png)

### <a name="report-view-for-the-connector-report"></a><span data-ttu-id="aa9ca-113">Vista informes para el informe de conector</span><span class="sxs-lookup"><span data-stu-id="aa9ca-113">Report view for the Connector report</span></span>

<span data-ttu-id="aa9ca-114">Los siguientes gráficos están disponibles en la vista de informe:</span><span class="sxs-lookup"><span data-stu-id="aa9ca-114">The following charts are available in report view:</span></span>

- <span data-ttu-id="aa9ca-115">**Ver datos por: flujo del correo**: en este gráfico se muestra el número de mensajes entrantes y salientes organizados por:</span><span class="sxs-lookup"><span data-stu-id="aa9ca-115">**View data by: Mail flow**: This chart shows the number of inbound and outbound messages organized by:</span></span>

  - <span data-ttu-id="aa9ca-116">**Total**</span><span class="sxs-lookup"><span data-stu-id="aa9ca-116">**Total**</span></span>
  - <span data-ttu-id="aa9ca-117">**De Internet sin conector**</span><span class="sxs-lookup"><span data-stu-id="aa9ca-117">**From the internet without a connector**</span></span>
  - <span data-ttu-id="aa9ca-118">**A Internet sin conector**</span><span class="sxs-lookup"><span data-stu-id="aa9ca-118">**To the internet without a connector**</span></span>
  - <span data-ttu-id="aa9ca-119">Un conector específico que haya configurado.</span><span class="sxs-lookup"><span data-stu-id="aa9ca-119">A specific connector that you've configured.</span></span>
  
  <span data-ttu-id="aa9ca-120">Para aislar los datos del gráfico, use el control **Mostrar datos para** para seleccionar una de estas opciones o **todo el flujo de correo**.</span><span class="sxs-lookup"><span data-stu-id="aa9ca-120">To isolate the data in the chart, use the **Show data for** control to select one of these options or **All mail flow**.</span></span>

  ![Ver los datos por flujo de correo en el informe de conectores](../../media/connector-report-view-data-by-mail-flow.png)

- <span data-ttu-id="aa9ca-122">**Ver datos por: uso de TLS**: en este gráfico se muestra el porcentaje de uso de la versión de seguridad de la capa de transporte (TLS) para el flujo de correo.</span><span class="sxs-lookup"><span data-stu-id="aa9ca-122">**View data by: TLS usage**: This chart shows the percentage of Transport Layer Security (TLS) version usage for mail flow.</span></span>

  <span data-ttu-id="aa9ca-123">Para aislar los datos del gráfico, use el control **Mostrar datos para** para seleccionar una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="aa9ca-123">To isolate the data in the chart, use the **Show data for** control to select one of the following options:</span></span>

  - <span data-ttu-id="aa9ca-124">**Todo el flujo de correo**</span><span class="sxs-lookup"><span data-stu-id="aa9ca-124">**All mail flow**</span></span>
  - <span data-ttu-id="aa9ca-125">**De Internet sin conector**</span><span class="sxs-lookup"><span data-stu-id="aa9ca-125">**From the internet without a connector**</span></span>
  - <span data-ttu-id="aa9ca-126">**A Internet sin conector**</span><span class="sxs-lookup"><span data-stu-id="aa9ca-126">**To the internet without a connector**</span></span>
  - <span data-ttu-id="aa9ca-127">Un conector específico que haya configurado.</span><span class="sxs-lookup"><span data-stu-id="aa9ca-127">A specific connector that you've configured.</span></span>

  ![Ver datos por uso de TLS en el informe de conectores](../../media/connector-report-view-data-by-tls-usage.png)

<span data-ttu-id="aa9ca-129">Si hace clic en **filtros** en una vista de informe, puede especificar un intervalo de fechas con **fecha de inicio** y fecha de **finalización**.</span><span class="sxs-lookup"><span data-stu-id="aa9ca-129">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-connector-report"></a><span data-ttu-id="aa9ca-130">Vista de tabla de detalles para el informe de conector</span><span class="sxs-lookup"><span data-stu-id="aa9ca-130">Details table view for the Connector report</span></span>

<span data-ttu-id="aa9ca-131">Si hace clic en **ver tabla de detalles** en una vista de informe, se mostrará la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="aa9ca-131">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="aa9ca-132">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="aa9ca-132">**Date**</span></span>
- <span data-ttu-id="aa9ca-133">**Dirección y nombre del conector**</span><span class="sxs-lookup"><span data-stu-id="aa9ca-133">**Connector direction and name**</span></span>
- <span data-ttu-id="aa9ca-134">**Tipo de conector**</span><span class="sxs-lookup"><span data-stu-id="aa9ca-134">**Connector type**</span></span>
- <span data-ttu-id="aa9ca-135">**¿TLS forzado?**: el valor **true** o **false**.</span><span class="sxs-lookup"><span data-stu-id="aa9ca-135">**Forced TLS?**: The value **True** or **False**.</span></span>
- <span data-ttu-id="aa9ca-136">**Sin TLS** (porcentaje)</span><span class="sxs-lookup"><span data-stu-id="aa9ca-136">**No TLS** (percentage)</span></span>
- <span data-ttu-id="aa9ca-137">**TLS 1,0** (porcentaje)</span><span class="sxs-lookup"><span data-stu-id="aa9ca-137">**TLS 1.0** (percentage)</span></span>
- <span data-ttu-id="aa9ca-138">**TLS 1,1** (porcentaje)</span><span class="sxs-lookup"><span data-stu-id="aa9ca-138">**TLS 1.1** (percentage)</span></span>
- <span data-ttu-id="aa9ca-139">**TLS 1,2** (porcentaje)</span><span class="sxs-lookup"><span data-stu-id="aa9ca-139">**TLS 1.2** (percentage)</span></span>
- <span data-ttu-id="aa9ca-140">**Volumen**: el número de mensajes.</span><span class="sxs-lookup"><span data-stu-id="aa9ca-140">**Volume**: The number of messages.</span></span>

<span data-ttu-id="aa9ca-141">Si hace clic en **filtros** en una vista de tabla de detalles, puede especificar un intervalo de fechas con **fecha de inicio** y fecha de **finalización**.</span><span class="sxs-lookup"><span data-stu-id="aa9ca-141">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="aa9ca-142">Para volver a la vista de informe, haga clic en **Ver informe**.</span><span class="sxs-lookup"><span data-stu-id="aa9ca-142">To go back to the report view, click **View report**.</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="aa9ca-143">Informe de reglas de transporte de Exchange</span><span class="sxs-lookup"><span data-stu-id="aa9ca-143">Exchange transport rule report</span></span>

<span data-ttu-id="aa9ca-144">El **Informe de reglas de transporte de Exchange** muestra el efecto de las reglas de flujo de correo (también conocidas como reglas de transporte) en los mensajes entrantes y salientes de la organización.</span><span class="sxs-lookup"><span data-stu-id="aa9ca-144">The **Exchange transport rule report** shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="aa9ca-145">Para ver el informe, abra el [centro de seguridad & cumplimiento](https://protection.office.com), vaya **Reports** al \> **Panel** informes y seleccione regla de **transporte de Exchange**.</span><span class="sxs-lookup"><span data-stu-id="aa9ca-145">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Exchange Transport rule**.</span></span> <span data-ttu-id="aa9ca-146">Para ir directamente al informe, Abra <https://protection.office.com/reportv2?id=ETRRuleReport> .</span><span class="sxs-lookup"><span data-stu-id="aa9ca-146">To go directly to the report, open <https://protection.office.com/reportv2?id=ETRRuleReport>.</span></span>

![Widget de regla de transporte de Exchange en el panel informes](../../media/transport-rule-report-widget.png)

### <a name="report-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="aa9ca-148">Vista informes para el informe de reglas de transporte de Exchange</span><span class="sxs-lookup"><span data-stu-id="aa9ca-148">Report view for the Exchange transport rule report</span></span>

<span data-ttu-id="aa9ca-149">Los siguientes gráficos están disponibles en la vista de informe:</span><span class="sxs-lookup"><span data-stu-id="aa9ca-149">The following charts are available in report view:</span></span>

- <span data-ttu-id="aa9ca-150">**Ver datos por: reglas** \> de transporte de Exchange **Desglose por: Dirección: en**este gráfico se muestra el número de mensajes **entrantes** y **salientes** que se vieron afectados por las reglas de transporte.</span><span class="sxs-lookup"><span data-stu-id="aa9ca-150">**View data by: Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by transport rules.</span></span>

- <span data-ttu-id="aa9ca-151">**Ver datos por: reglas** \> de transporte de Exchange **Desglose por: gravedad: en**este gráfico se muestra el número de gravedad **alta** y **mediana**y los mensajes de **gravedad baja** .</span><span class="sxs-lookup"><span data-stu-id="aa9ca-151">**View data by: Exchange transport rules** \> **Break down by: Severity**: This chart shows the number of **High severity** and **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="aa9ca-152">El nivel de gravedad se establece como una acción en la regla (**auditar esta regla con el nivel de gravedad** o _SetAuditSeverity_).</span><span class="sxs-lookup"><span data-stu-id="aa9ca-152">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="aa9ca-153">Para obtener más información, vea [acciones de las reglas de flujo de correo en Exchange Online](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span><span class="sxs-lookup"><span data-stu-id="aa9ca-153">For more information, see [Mail flow rule actions in Exchange Online](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="aa9ca-154">**Ver datos por: reglas de transporte de Exchange de DLP** \> **Desglose por: Dirección: en**este gráfico se muestra el número de mensajes **entrantes** y **salientes** que se vieron afectados por las reglas de transporte de prevención de pérdida de datos (DLP).</span><span class="sxs-lookup"><span data-stu-id="aa9ca-154">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) transport rules.</span></span> <span data-ttu-id="aa9ca-155">Puede refinar aún más el gráfico si selecciona una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="aa9ca-155">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="aa9ca-156">**Mostrar datos para: todas las reglas de transporte de DLP**</span><span class="sxs-lookup"><span data-stu-id="aa9ca-156">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="aa9ca-157">**Mostrar datos para: usuarios comprometidos**</span><span class="sxs-lookup"><span data-stu-id="aa9ca-157">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="aa9ca-158">**Mostrar datos para: bajo volumen de contenido detectado Patriot Act de Estados Unidos**</span><span class="sxs-lookup"><span data-stu-id="aa9ca-158">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

- <span data-ttu-id="aa9ca-159">**Ver datos por: reglas de transporte de Exchange de DLP** \> **Dividir por: dirección**: esta vista muestra el número de gravedad **alta** y **mediana**y los mensajes de **gravedad baja** que se vieron afectados por las reglas de transporte de DLP.</span><span class="sxs-lookup"><span data-stu-id="aa9ca-159">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This view shows the number of **High severity** and **Medium severity**, and **Low severity** messages that were affected by DLP transport rules.</span></span> <span data-ttu-id="aa9ca-160">Puede refinar aún más el gráfico si selecciona una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="aa9ca-160">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="aa9ca-161">**Mostrar datos para: todas las reglas de transporte de DLP**</span><span class="sxs-lookup"><span data-stu-id="aa9ca-161">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="aa9ca-162">**Mostrar datos para: usuarios comprometidos**</span><span class="sxs-lookup"><span data-stu-id="aa9ca-162">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="aa9ca-163">**Mostrar datos para: bajo volumen de contenido detectado Patriot Act de Estados Unidos**</span><span class="sxs-lookup"><span data-stu-id="aa9ca-163">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

<span data-ttu-id="aa9ca-164">Si hace clic en **filtros** en una vista de informe, puede modificar los resultados con los siguientes filtros::</span><span class="sxs-lookup"><span data-stu-id="aa9ca-164">If you click **Filters** in a report view, you can modify the results with the following filters::</span></span>

- <span data-ttu-id="aa9ca-165">**Fecha de inicio** y **fecha de finalización**</span><span class="sxs-lookup"><span data-stu-id="aa9ca-165">**Start date** and **End date**</span></span>
- <span data-ttu-id="aa9ca-166">Valores de dirección</span><span class="sxs-lookup"><span data-stu-id="aa9ca-166">Direction values</span></span>
- <span data-ttu-id="aa9ca-167">Valores de gravedad</span><span class="sxs-lookup"><span data-stu-id="aa9ca-167">Severity values</span></span>

![Vista de informe en el informe de reglas de transporte de Exchange](../../media/transport-rule-report-report-view.png)

### <a name="details-table-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="aa9ca-169">Vista de tabla de detalles para el informe de regla de transporte de Exchange</span><span class="sxs-lookup"><span data-stu-id="aa9ca-169">Details table view for the Exchange transport rule report</span></span>

<span data-ttu-id="aa9ca-170">Si hace clic en **ver tabla de detalles**, la información que se muestra depende del gráfico que estaba viendo:</span><span class="sxs-lookup"><span data-stu-id="aa9ca-170">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="aa9ca-171">**Ver datos por: reglas de transporte de Exchange**:</span><span class="sxs-lookup"><span data-stu-id="aa9ca-171">**View data by: Exchange Transport rules**:</span></span>

  - <span data-ttu-id="aa9ca-172">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="aa9ca-172">**Date**</span></span>
  - <span data-ttu-id="aa9ca-173">**Regla de transporte**</span><span class="sxs-lookup"><span data-stu-id="aa9ca-173">**Transport rule**</span></span>
  - <span data-ttu-id="aa9ca-174">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="aa9ca-174">**Subject**</span></span>
  - <span data-ttu-id="aa9ca-175">**Dirección del remitente**</span><span class="sxs-lookup"><span data-stu-id="aa9ca-175">**Sender address**</span></span>
  - <span data-ttu-id="aa9ca-176">**Dirección del destinatario**</span><span class="sxs-lookup"><span data-stu-id="aa9ca-176">**Recipient address**</span></span>
  - <span data-ttu-id="aa9ca-177">**Gravedad**</span><span class="sxs-lookup"><span data-stu-id="aa9ca-177">**Severity**</span></span>
  - <span data-ttu-id="aa9ca-178">**Dirección**</span><span class="sxs-lookup"><span data-stu-id="aa9ca-178">**Direction**</span></span>

- <span data-ttu-id="aa9ca-179">**Ver datos por: reglas de transporte de DLP de Exchange**:</span><span class="sxs-lookup"><span data-stu-id="aa9ca-179">**View data by: DLP Exchange transport rules**:</span></span>

  - <span data-ttu-id="aa9ca-180">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="aa9ca-180">**Date**</span></span>
  - <span data-ttu-id="aa9ca-181">**Directiva DLP**</span><span class="sxs-lookup"><span data-stu-id="aa9ca-181">**DLP policy**</span></span>
  - <span data-ttu-id="aa9ca-182">**Regla de transporte**</span><span class="sxs-lookup"><span data-stu-id="aa9ca-182">**Transport rule**</span></span>
  - <span data-ttu-id="aa9ca-183">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="aa9ca-183">**Subject**</span></span>
  - <span data-ttu-id="aa9ca-184">**Dirección del remitente**</span><span class="sxs-lookup"><span data-stu-id="aa9ca-184">**Sender address**</span></span>
  - <span data-ttu-id="aa9ca-185">**Dirección del destinatario**</span><span class="sxs-lookup"><span data-stu-id="aa9ca-185">**Recipient address**</span></span>
  - <span data-ttu-id="aa9ca-186">**Gravedad**</span><span class="sxs-lookup"><span data-stu-id="aa9ca-186">**Severity**</span></span>
  - <span data-ttu-id="aa9ca-187">**Dirección**</span><span class="sxs-lookup"><span data-stu-id="aa9ca-187">**Direction**</span></span>

<span data-ttu-id="aa9ca-188">Si hace clic en **filtros** en una vista de tabla de detalles, puede modificar los resultados con los filtros siguientes:</span><span class="sxs-lookup"><span data-stu-id="aa9ca-188">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="aa9ca-189">**Fecha de inicio** y **fecha de finalización**</span><span class="sxs-lookup"><span data-stu-id="aa9ca-189">**Start date** and **End date**</span></span>
- <span data-ttu-id="aa9ca-190">Valores de dirección</span><span class="sxs-lookup"><span data-stu-id="aa9ca-190">Direction values</span></span>
- <span data-ttu-id="aa9ca-191">Valores de gravedad</span><span class="sxs-lookup"><span data-stu-id="aa9ca-191">Severity values</span></span>

<span data-ttu-id="aa9ca-192">Para volver a la vista de informe, haga clic en **Ver informe**.</span><span class="sxs-lookup"><span data-stu-id="aa9ca-192">To go back to the report view, click **View report**.</span></span>

## <a name="forwarding-report"></a><span data-ttu-id="aa9ca-193">Reenvío de informes</span><span class="sxs-lookup"><span data-stu-id="aa9ca-193">Forwarding report</span></span>

<span data-ttu-id="aa9ca-194">El **Informe de reenvío** muestra los mensajes reenviados automáticamente de la organización a dominios externos de los buzones de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="aa9ca-194">The **Forwarding report** shows your organization's automatically forwarded messages to external domains from Exchange Online mailboxes.</span></span> <span data-ttu-id="aa9ca-195">Los mensajes reenviados pueden suponer un riesgo de seguridad o de cumplimiento, y pueden indicar una cuenta en peligro.</span><span class="sxs-lookup"><span data-stu-id="aa9ca-195">Forwarded messages can pose a security or compliance risk, and might indicate a compromised account.</span></span>

<span data-ttu-id="aa9ca-196">Para ver el informe, abra el [centro de seguridad & cumplimiento](https://protection.office.com), vaya **Reports** al \> **Panel** informes y seleccione **reenviar Informe**.</span><span class="sxs-lookup"><span data-stu-id="aa9ca-196">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Forwarding report**.</span></span> <span data-ttu-id="aa9ca-197">Para ir directamente al informe, Abra <https://protection.office.com/reportv2?id=MailFlowForwarding> .</span><span class="sxs-lookup"><span data-stu-id="aa9ca-197">To go directly to the report, open <https://protection.office.com/reportv2?id=MailFlowForwarding>.</span></span>

![Reenvío del widget de informe en el panel informes](../../media/forwarding-report-widget.png)

### <a name="report-view-for-the-forwarding-report"></a><span data-ttu-id="aa9ca-199">Vista informes para el informe de reenvío</span><span class="sxs-lookup"><span data-stu-id="aa9ca-199">Report view for the Forwarding report</span></span>

<span data-ttu-id="aa9ca-200">Los siguientes gráficos están disponibles en la vista de informe:</span><span class="sxs-lookup"><span data-stu-id="aa9ca-200">The following charts are available in the report view:</span></span>

- <span data-ttu-id="aa9ca-201">**Mostrar datos para: métodos de reenvío**: se muestran los métodos siguientes:</span><span class="sxs-lookup"><span data-stu-id="aa9ca-201">**Show data for: Forwarding methods**: The following methods are shown:</span></span>

  - <span data-ttu-id="aa9ca-202">**Regla de transporte**: también conocida como [reglas de flujo de correo](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span><span class="sxs-lookup"><span data-stu-id="aa9ca-202">**Transport rule**: Also known as [mail flow rules](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span></span>
  - <span data-ttu-id="aa9ca-203">**Regla de buzón de correo**: también conocida como reglas de la [bandeja de entrada](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).</span><span class="sxs-lookup"><span data-stu-id="aa9ca-203">**Mailbox rule**: Also known as [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).</span></span>

  ![Vista de métodos de reenvío en el informe de reenvío](../../media/forwarding-report-forwarding-methods.png)

- <span data-ttu-id="aa9ca-205">**Mostrar datos de: dominios de reenvío**: esta vista muestra los dominios de destinatario que son los destinos para el reenvío.</span><span class="sxs-lookup"><span data-stu-id="aa9ca-205">**Show data for: Forwarding domains**: This view shows the recipient domains that are the destinations for forwarding.</span></span>

  ![Vista de dominios de reenvío en el informe de reenvío](../../media/forwarding-report-forwarding-domains.png)

- <span data-ttu-id="aa9ca-207">**Mostrar datos para: reenviadores**: se muestran los siguientes reenviadores:</span><span class="sxs-lookup"><span data-stu-id="aa9ca-207">**Show data for: Forwarders**: The following forwarders are shown:</span></span>

  - <span data-ttu-id="aa9ca-208">**Regla de transporte**</span><span class="sxs-lookup"><span data-stu-id="aa9ca-208">**Transport rule**</span></span>
  - <span data-ttu-id="aa9ca-209">El buzón de correo que contiene la regla de reenvío de la bandeja de entrada.</span><span class="sxs-lookup"><span data-stu-id="aa9ca-209">The mailbox that contains the forwarding Inbox rule.</span></span>

  ![Vista de reenvíos en el informe de reenvío](../../media/forwarding-report-forwarders.png)

<span data-ttu-id="aa9ca-211">Si hace clic en **filtros** en una vista de informe, puede especificar un intervalo de fechas con **fecha de inicio** y fecha de **finalización**.</span><span class="sxs-lookup"><span data-stu-id="aa9ca-211">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-report"></a><span data-ttu-id="aa9ca-212">Vista de tabla de detalles para el informe de reenvío</span><span class="sxs-lookup"><span data-stu-id="aa9ca-212">Details table view for the Forwarding report</span></span>

<span data-ttu-id="aa9ca-213">Si hace clic en **ver tabla de detalles** en una vista de informe, se mostrará la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="aa9ca-213">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="aa9ca-214">**Reenviadores**: la **regla de transporte** de valor o el buzón que contiene la regla de reenvío de la bandeja de entrada.</span><span class="sxs-lookup"><span data-stu-id="aa9ca-214">**Forwarders**: The value **Transport rule** or the mailbox that contains the forwarding Inbox rule.</span></span>
- <span data-ttu-id="aa9ca-215">**Tipo de reenvío**: regla de **buzón de correo** de valor o regla de **transporte**.</span><span class="sxs-lookup"><span data-stu-id="aa9ca-215">**Forwarding type**: The value **Mailbox rule** or **Transport rule**.</span></span>
- <span data-ttu-id="aa9ca-216">**Nombre de destinatario**</span><span class="sxs-lookup"><span data-stu-id="aa9ca-216">**Recipient name**</span></span>
- <span data-ttu-id="aa9ca-217">**Dominio del destinatario**</span><span class="sxs-lookup"><span data-stu-id="aa9ca-217">**Recipient domain**</span></span>
- <span data-ttu-id="aa9ca-218">**Detalles**: este es el valor de GUID de la regla de flujo de correo o el valor RuleIdentity de la regla de bandeja de entrada.</span><span class="sxs-lookup"><span data-stu-id="aa9ca-218">**Details**: This is the GUID value of the mail flow rule, or the RuleIdentity value of the Inbox rule.</span></span>
- <span data-ttu-id="aa9ca-219">**Count**</span><span class="sxs-lookup"><span data-stu-id="aa9ca-219">**Count**</span></span>
- <span data-ttu-id="aa9ca-220">**Primera fecha de reenvío**</span><span class="sxs-lookup"><span data-stu-id="aa9ca-220">**First forward date**</span></span>

<span data-ttu-id="aa9ca-221">Si hace clic en **filtros** en una vista de tabla de detalles, puede especificar un intervalo de fechas con **fecha de inicio** y fecha de **finalización**.</span><span class="sxs-lookup"><span data-stu-id="aa9ca-221">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="aa9ca-222">Para volver a la vista informes, haga clic en **Ver informe**.</span><span class="sxs-lookup"><span data-stu-id="aa9ca-222">To go back to the reports view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="aa9ca-223">Informe de estado de flujo de notificación</span><span class="sxs-lookup"><span data-stu-id="aa9ca-223">Mailflow status report</span></span>

<span data-ttu-id="aa9ca-224">El **Informe de estado de flujo** de correo es similar al [Informe de correo electrónico enviado y recibido](#sent-and-received-email-report), con información adicional sobre el correo electrónico permitido o bloqueado en el servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="aa9ca-224">The **Mailflow status report** is similar to the [Sent and received email report](#sent-and-received-email-report), with additional information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="aa9ca-225">Este es el único informe que contiene información sobre la protección perimetral y muestra la cantidad de correo electrónico que se bloquea antes de que se permita el servicio para su evaluación por parte de Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="aa9ca-225">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span>

<span data-ttu-id="aa9ca-226">Para ver el informe, abra el [centro de seguridad & cumplimiento](https://protection.office.com), vaya **Reports** al \> **Panel** informes y seleccione informe de **Estado de flujo**de información.</span><span class="sxs-lookup"><span data-stu-id="aa9ca-226">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Mailflow status report**.</span></span> <span data-ttu-id="aa9ca-227">Para ir directamente al **Informe de estado del flujo de correo**, Abra <https://protection.office.com/mailflowStatusReport> .</span><span class="sxs-lookup"><span data-stu-id="aa9ca-227">To go directly to the **Mail flow status report**, open <https://protection.office.com/mailflowStatusReport>.</span></span>

![Widget de informe de estado de flujo de registros en el panel informes](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="aa9ca-229">Tipo de vista para el informe de estado de flujo de información</span><span class="sxs-lookup"><span data-stu-id="aa9ca-229">Type view for the Mailflow status report</span></span>

<span data-ttu-id="aa9ca-230">Al abrir el informe, la ficha **tipo** se selecciona de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="aa9ca-230">When you open the report, the **Type** tab is selected by default.</span></span> <span data-ttu-id="aa9ca-231">De forma predeterminada, esta vista contiene un gráfico y una tabla de datos que se configura con los siguientes filtros:</span><span class="sxs-lookup"><span data-stu-id="aa9ca-231">By default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="aa9ca-232">**Fecha**: los últimos 7 días.</span><span class="sxs-lookup"><span data-stu-id="aa9ca-232">**Date**: The last 7 days.</span></span>
- <span data-ttu-id="aa9ca-233">**Dirección**:</span><span class="sxs-lookup"><span data-stu-id="aa9ca-233">**Direction**:</span></span>

  - <span data-ttu-id="aa9ca-234">**Entrada**</span><span class="sxs-lookup"><span data-stu-id="aa9ca-234">**Inbound**</span></span>
  - <span data-ttu-id="aa9ca-235">**Saliente**</span><span class="sxs-lookup"><span data-stu-id="aa9ca-235">**Outbound**</span></span>
  - <span data-ttu-id="aa9ca-236">**Dentro de la organización** (cuenta por separado de **entrada** y de **salida**)</span><span class="sxs-lookup"><span data-stu-id="aa9ca-236">**Intra-org** (counted separately from **Inbound** and **Outbound**)</span></span>

- <span data-ttu-id="aa9ca-237">**Tipo**:</span><span class="sxs-lookup"><span data-stu-id="aa9ca-237">**Type**:</span></span>

  - <span data-ttu-id="aa9ca-238">**Correo bueno**</span><span class="sxs-lookup"><span data-stu-id="aa9ca-238">**Good mail**</span></span>
  - <span data-ttu-id="aa9ca-239">**Malware**</span><span class="sxs-lookup"><span data-stu-id="aa9ca-239">**Malware**</span></span>
  - <span data-ttu-id="aa9ca-240">**Correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="aa9ca-240">**Spam**</span></span>
  - <span data-ttu-id="aa9ca-241">**Protección perimetral**</span><span class="sxs-lookup"><span data-stu-id="aa9ca-241">**Edge protection**</span></span>
  - <span data-ttu-id="aa9ca-242">**Mensajes de regla**</span><span class="sxs-lookup"><span data-stu-id="aa9ca-242">**Rule messages**</span></span>
  - <span data-ttu-id="aa9ca-243">**Correo de suplantación de identidad**</span><span class="sxs-lookup"><span data-stu-id="aa9ca-243">**Phishing email**</span></span>

<span data-ttu-id="aa9ca-244">El gráfico se organiza por los valores de **tipo** .</span><span class="sxs-lookup"><span data-stu-id="aa9ca-244">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="aa9ca-245">Puede cambiar estos filtros haciendo clic en **filtrar** o haciendo clic en un valor de la leyenda del gráfico.</span><span class="sxs-lookup"><span data-stu-id="aa9ca-245">You can changes these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span>

<span data-ttu-id="aa9ca-246">La tabla de datos contiene la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="aa9ca-246">The data table contains the following information:</span></span>

- <span data-ttu-id="aa9ca-247">**Dirección**</span><span class="sxs-lookup"><span data-stu-id="aa9ca-247">**Direction**</span></span>
- <span data-ttu-id="aa9ca-248">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="aa9ca-248">**Type**</span></span>
- <span data-ttu-id="aa9ca-249">**24 horas**</span><span class="sxs-lookup"><span data-stu-id="aa9ca-249">**24 hours**</span></span>
- <span data-ttu-id="aa9ca-250">**3 días**</span><span class="sxs-lookup"><span data-stu-id="aa9ca-250">**3 days**</span></span>
- <span data-ttu-id="aa9ca-251">**7 días**</span><span class="sxs-lookup"><span data-stu-id="aa9ca-251">**7 days**</span></span>
- <span data-ttu-id="aa9ca-252">**15 días**</span><span class="sxs-lookup"><span data-stu-id="aa9ca-252">**15 days**</span></span>
- <span data-ttu-id="aa9ca-253">**30 días**</span><span class="sxs-lookup"><span data-stu-id="aa9ca-253">**30 days**</span></span>

<span data-ttu-id="aa9ca-254">Si hace clic en **elegir una categoría para obtener más información**, puede seleccionar uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="aa9ca-254">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="aa9ca-255">**Correo electrónico de suplantación de identidad**: esta selección le lleva al [Informe de estado de protección contra amenazas](view-email-security-reports.md#threat-protection-status-report).</span><span class="sxs-lookup"><span data-stu-id="aa9ca-255">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="aa9ca-256">**Malware en correo electrónico**: esta selección le lleva al [Informe de estado de protección contra amenazas](view-email-security-reports.md#threat-protection-status-report).</span><span class="sxs-lookup"><span data-stu-id="aa9ca-256">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="aa9ca-257">**Detecciones de correo no deseado**: esta selección le lleva al [Informe de detecciones de correo no deseado](view-email-security-reports.md#spam-detections-report).</span><span class="sxs-lookup"><span data-stu-id="aa9ca-257">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="aa9ca-258">**Correo no deseado de Edge bloqueado**: esta selección le lleva al [Informe de detecciones de correo no deseado](view-email-security-reports.md#spam-detections-report).</span><span class="sxs-lookup"><span data-stu-id="aa9ca-258">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="aa9ca-259">**Exportar**:</span><span class="sxs-lookup"><span data-stu-id="aa9ca-259">**Export**:</span></span>

<span data-ttu-id="aa9ca-260">Para la vista de detalles, solo puede exportar datos de un día.</span><span class="sxs-lookup"><span data-stu-id="aa9ca-260">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="aa9ca-261">Por lo tanto, si desea exportar datos durante 7 días, necesitará hacer 7 acciones de exportación diferentes.</span><span class="sxs-lookup"><span data-stu-id="aa9ca-261">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="aa9ca-262">Cada archivo. csv exportado está limitado a 150.000 filas.</span><span class="sxs-lookup"><span data-stu-id="aa9ca-262">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="aa9ca-263">Si los datos de ese día contienen más de 150.000 filas, se crearán varios archivos. csv.</span><span class="sxs-lookup"><span data-stu-id="aa9ca-263">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="aa9ca-264">Tipo ver en el informe de estado de flujo de información</span><span class="sxs-lookup"><span data-stu-id="aa9ca-264">Type view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="aa9ca-265">Vista de dirección para el informe de estado de flujo de información</span><span class="sxs-lookup"><span data-stu-id="aa9ca-265">Direction view for the Mailflow status report</span></span>

<span data-ttu-id="aa9ca-266">Si hace clic en la ficha **Dirección** , se usarán los mismos filtros predeterminados de la vista de **tipos** .</span><span class="sxs-lookup"><span data-stu-id="aa9ca-266">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="aa9ca-267">El gráfico está organizado por valores de **Dirección** .</span><span class="sxs-lookup"><span data-stu-id="aa9ca-267">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="aa9ca-268">Puede cambiar estos filtros haciendo clic en **filtrar** o haciendo clic en un valor de la leyenda del gráfico.</span><span class="sxs-lookup"><span data-stu-id="aa9ca-268">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span> <span data-ttu-id="aa9ca-269">Se usan los mismos filtros de la vista **tipo** .</span><span class="sxs-lookup"><span data-stu-id="aa9ca-269">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="aa9ca-270">La tabla de datos contiene la misma información de la vista de **tipo** .</span><span class="sxs-lookup"><span data-stu-id="aa9ca-270">The data table contains same information from the **Type** view.</span></span>

<span data-ttu-id="aa9ca-271">El comportamiento seleccionar **una categoría para obtener más información sobre** las selecciones disponibles y el comportamiento es el mismo que el de la vista **tipo** .</span><span class="sxs-lookup"><span data-stu-id="aa9ca-271">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

<span data-ttu-id="aa9ca-272">**Exportar**:</span><span class="sxs-lookup"><span data-stu-id="aa9ca-272">**Export**:</span></span>

<span data-ttu-id="aa9ca-273">Para la vista de detalles, solo puede exportar datos de un día.</span><span class="sxs-lookup"><span data-stu-id="aa9ca-273">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="aa9ca-274">Por lo tanto, si desea exportar datos durante 7 días, necesitará hacer 7 acciones de exportación diferentes.</span><span class="sxs-lookup"><span data-stu-id="aa9ca-274">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="aa9ca-275">Cada archivo. csv exportado está limitado a 150.000 filas.</span><span class="sxs-lookup"><span data-stu-id="aa9ca-275">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="aa9ca-276">Si los datos de ese día contienen más de 150.000 filas, se crearán varios archivos. csv.</span><span class="sxs-lookup"><span data-stu-id="aa9ca-276">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="aa9ca-277">Vista de dirección en el informe de estado de flujo de notificación</span><span class="sxs-lookup"><span data-stu-id="aa9ca-277">Direction view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-direction-view.png)

## <a name="sent-and-received-email-report"></a><span data-ttu-id="aa9ca-278">Informe de correo electrónico enviado y recibido</span><span class="sxs-lookup"><span data-stu-id="aa9ca-278">Sent and received email report</span></span>

<span data-ttu-id="aa9ca-279">El informe de **correo electrónico enviado y recibido** es un informe inteligente que muestra información sobre el correo electrónico entrante y saliente, incluidas las detecciones de correo no deseado, malware y el correo electrónico identificado como "bueno".</span><span class="sxs-lookup"><span data-stu-id="aa9ca-279">The **Sent and received email** report is a smart report that shows information about incoming and outgoing email, including spam detections, malware, and email identified as "good."</span></span> <span data-ttu-id="aa9ca-280">La diferencia entre este informe y el [Informe de estado de flujo](#mailflow-status-report) de correos es la siguiente: este informe no incluye datos sobre los mensajes bloqueados por la protección perimetral.</span><span class="sxs-lookup"><span data-stu-id="aa9ca-280">The difference between this report and the [Mailflow status report](#mailflow-status-report) is: this report doesn't include data about messages blocked by edge protection.</span></span>

<span data-ttu-id="aa9ca-281">La vista agregada y la vista de detalles del informe permiten 90 días de filtrado.</span><span class="sxs-lookup"><span data-stu-id="aa9ca-281">The aggregate view and the detail view of the report allow for 90 days of filtering.</span></span>

<span data-ttu-id="aa9ca-282">Para ver el informe, abra el [centro de seguridad & cumplimiento](https://protection.office.com), vaya **Reports** al \> **Panel** informes y seleccione **correo electrónico enviado y recibido**.</span><span class="sxs-lookup"><span data-stu-id="aa9ca-282">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Sent and received email**.</span></span> <span data-ttu-id="aa9ca-283">Para ir directamente al informe, Abra <https://protection.office.com/reportv2?id=SentAndReceivedMailATP> .</span><span class="sxs-lookup"><span data-stu-id="aa9ca-283">To go directly to the report, open <https://protection.office.com/reportv2?id=SentAndReceivedMailATP>.</span></span>

![Widget de correo electrónico enviado y recibido en el panel de informes](../../media/sent-and-received-email-report-widget.png)

### <a name="report-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="aa9ca-285">Vista informes para el informe de correo electrónico enviado y recibido</span><span class="sxs-lookup"><span data-stu-id="aa9ca-285">Report view for the Sent and received email report</span></span>

<span data-ttu-id="aa9ca-286">Los siguientes gráficos están disponibles en la vista de informe:</span><span class="sxs-lookup"><span data-stu-id="aa9ca-286">The following charts are available in the report view:</span></span>

- <span data-ttu-id="aa9ca-287">**Dividir por: escriba**: el gráfico muestra todas las categorías disponibles:</span><span class="sxs-lookup"><span data-stu-id="aa9ca-287">**Break down by: Type**: The chart shows all available categories:</span></span>

  - <span data-ttu-id="aa9ca-288">**Total**</span><span class="sxs-lookup"><span data-stu-id="aa9ca-288">**Total**</span></span>
  - <span data-ttu-id="aa9ca-289">**Correo bueno**</span><span class="sxs-lookup"><span data-stu-id="aa9ca-289">**Good mail**</span></span>
  - <span data-ttu-id="aa9ca-290">**Malware (anti-malware)** (EOP)</span><span class="sxs-lookup"><span data-stu-id="aa9ca-290">**Malware (anti-malware)** (EOP)</span></span>
  - <span data-ttu-id="aa9ca-291">**Detecciones de correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="aa9ca-291">**Spam detections**</span></span>
  - <span data-ttu-id="aa9ca-292">**Mensajes de regla**</span><span class="sxs-lookup"><span data-stu-id="aa9ca-292">**Rule messages**</span></span>
  - <span data-ttu-id="aa9ca-293">**Malware avanzado** (Office 365 ATP)</span><span class="sxs-lookup"><span data-stu-id="aa9ca-293">**Advanced malware** (Office 365 ATP)</span></span>

  <span data-ttu-id="aa9ca-294">Al pasar el mouse sobre un día (punto de datos) del gráfico, puede ver los detalles de ese día.</span><span class="sxs-lookup"><span data-stu-id="aa9ca-294">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![Tipo ver en el informe de correo electrónico enviado y recibido](../../media/sent-and-received-email-report-type-view.png)

- <span data-ttu-id="aa9ca-296">**Desglose por: dirección**: el gráfico muestra los datos **totales**, **entrantes**y **salientes** .</span><span class="sxs-lookup"><span data-stu-id="aa9ca-296">**Break down by: Direction**: The chart shows **Total**, **Inbound**, and **Outbound** data.</span></span> <span data-ttu-id="aa9ca-297">Al pasar el mouse sobre un día (punto de datos) del gráfico, puede ver los detalles de ese día.</span><span class="sxs-lookup"><span data-stu-id="aa9ca-297">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![Vista de dirección en el informe de correo electrónico enviados y recibidos](../../media/sent-and-received-email-report-direction-view.png)

- <span data-ttu-id="aa9ca-299">**Explorar en profundidad por** \> **Malware (anti-malware)**: esta selección le lleva a las [detecciones de malware en el informe de correo electrónico](view-email-security-reports.md#malware-detections-in-email-report).</span><span class="sxs-lookup"><span data-stu-id="aa9ca-299">**Drill down by** \> **Malware (anti-malware)**: This selection takes you to the [Malware detections in email report](view-email-security-reports.md#malware-detections-in-email-report).</span></span>

- <span data-ttu-id="aa9ca-300">**Explorar en profundidad por** \> **Detecciones de correo no deseado)**: esta selección le lleva al [Informe de detecciones de correo no deseado](view-email-security-reports.md#spam-detections-report).</span><span class="sxs-lookup"><span data-stu-id="aa9ca-300">**Drill down by** \> **Spam detections)**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="aa9ca-301">Si hace clic en **filtros** en una vista de informe, puede modificar los resultados con los siguientes filtros:</span><span class="sxs-lookup"><span data-stu-id="aa9ca-301">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="aa9ca-302">**Fecha de inicio** y **fecha de finalización**</span><span class="sxs-lookup"><span data-stu-id="aa9ca-302">**Start date** and **End date**</span></span>
- <span data-ttu-id="aa9ca-303">Valores de dirección</span><span class="sxs-lookup"><span data-stu-id="aa9ca-303">Direction values</span></span>
- <span data-ttu-id="aa9ca-304">Valores de tipo</span><span class="sxs-lookup"><span data-stu-id="aa9ca-304">Type values</span></span>

<span data-ttu-id="aa9ca-305">Para volver a la vista de informe, haga clic en **Ver informe**.</span><span class="sxs-lookup"><span data-stu-id="aa9ca-305">To go back to the report view, click **View report**.</span></span>

### <a name="details-table-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="aa9ca-306">Vista de tabla de detalles para el informe de correo electrónico enviado y recibido</span><span class="sxs-lookup"><span data-stu-id="aa9ca-306">Details table view for the Sent and received email report</span></span>

<span data-ttu-id="aa9ca-307">Si hace clic en **ver tabla de detalles** en el cuadro **desglosar por: dirección** o **dividir por:** vista de dirección, se muestra la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="aa9ca-307">If you click **View details table** in the **Break down by: Direction** or **Break down by: Direction** view, the following information is shown:</span></span>

- <span data-ttu-id="aa9ca-308">**Fecha (UTC)**</span><span class="sxs-lookup"><span data-stu-id="aa9ca-308">**Date (UTC)**</span></span>
- <span data-ttu-id="aa9ca-309">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="aa9ca-309">**Type**</span></span>
- <span data-ttu-id="aa9ca-310">**Dirección**</span><span class="sxs-lookup"><span data-stu-id="aa9ca-310">**Direction**</span></span>
- <span data-ttu-id="aa9ca-311">**Número de mensajes**</span><span class="sxs-lookup"><span data-stu-id="aa9ca-311">**Message count**</span></span>

<span data-ttu-id="aa9ca-312">Si hace clic en **filtros** en una vista de tabla de detalles, puede modificar los resultados con los filtros siguientes:</span><span class="sxs-lookup"><span data-stu-id="aa9ca-312">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="aa9ca-313">**Fecha de inicio** y **fecha de finalización**</span><span class="sxs-lookup"><span data-stu-id="aa9ca-313">**Start date** and **End date**</span></span>
- <span data-ttu-id="aa9ca-314">Valores de dirección</span><span class="sxs-lookup"><span data-stu-id="aa9ca-314">Direction values</span></span>
- <span data-ttu-id="aa9ca-315">Valores de tipo</span><span class="sxs-lookup"><span data-stu-id="aa9ca-315">Type values</span></span>

<span data-ttu-id="aa9ca-316">Para volver a la vista de informe, haga clic en **Ver informe**.</span><span class="sxs-lookup"><span data-stu-id="aa9ca-316">To go back to the report view, click **View report**.</span></span>

## <a name="top-senders-and-recipients-report"></a><span data-ttu-id="aa9ca-317">Informe de remitentes y destinatarios principales</span><span class="sxs-lookup"><span data-stu-id="aa9ca-317">Top senders and recipients report</span></span>

<span data-ttu-id="aa9ca-318">El informe de **remitentes y destinatarios principales** es un gráfico circular que muestra los principales remitentes y destinatarios de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="aa9ca-318">The **Top senders and recipients** report is a pie chart showing your top email senders and recipients.</span></span>

<span data-ttu-id="aa9ca-319">Para ver el informe, abra el [centro de seguridad & cumplimiento](https://protection.office.com), vaya **Reports** al \> **Panel** informes y seleccione **principales remitentes y destinatarios**.</span><span class="sxs-lookup"><span data-stu-id="aa9ca-319">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top senders and recipients**.</span></span> <span data-ttu-id="aa9ca-320">Para ir directamente al informe, Abra <https://protection.office.com/reportv2?id=TopSenderRecipientsATP> .</span><span class="sxs-lookup"><span data-stu-id="aa9ca-320">To go directly to the report, open <https://protection.office.com/reportv2?id=TopSenderRecipientsATP>.</span></span>

![Widgets principales remitentes y destinatarios en el panel informes](../../media/top-senders-and-recipients-widget.png)

### <a name="report-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="aa9ca-322">Vista informes para los principales informes de remitentes y destinatarios</span><span class="sxs-lookup"><span data-stu-id="aa9ca-322">Report view for the Top senders and recipient report</span></span>

<span data-ttu-id="aa9ca-323">Los siguientes gráficos están disponibles en la vista de informe:</span><span class="sxs-lookup"><span data-stu-id="aa9ca-323">The following charts are available in the report view:</span></span>

- <span data-ttu-id="aa9ca-324">**Mostrar datos para los \> remitentes de correo principales**</span><span class="sxs-lookup"><span data-stu-id="aa9ca-324">**Show data for \> Top mail senders**</span></span>
- <span data-ttu-id="aa9ca-325">**Mostrar datos para los \> principales destinatarios de correo**</span><span class="sxs-lookup"><span data-stu-id="aa9ca-325">**Show data for \> Top mail recipients**</span></span>
- <span data-ttu-id="aa9ca-326">**Mostrar datos para los \> principales destinatarios de correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="aa9ca-326">**Show data for \> Top spam recipients**</span></span>
- <span data-ttu-id="aa9ca-327">**Mostrar datos para \> Destinatarios principales de malware** (EOP)</span><span class="sxs-lookup"><span data-stu-id="aa9ca-327">**Show data for \> Top malware recipients** (EOP)</span></span>
- <span data-ttu-id="aa9ca-328">**Mostrar datos para \> Principales destinatarios de malware (ATP)** (Office 365 ATP)</span><span class="sxs-lookup"><span data-stu-id="aa9ca-328">**Show data for \> Top malware recipients (ATP)** (Office 365 ATP)</span></span>

<span data-ttu-id="aa9ca-329">La composición del gráfico circular cambia en función de estas selecciones.</span><span class="sxs-lookup"><span data-stu-id="aa9ca-329">The composition of the pie chart changes based on these selections.</span></span>

<span data-ttu-id="aa9ca-330">Cuando desplaza el puntero sobre una cuña del gráfico circular, puede ver un recuento de los mensajes enviados o recibidos.</span><span class="sxs-lookup"><span data-stu-id="aa9ca-330">When you hover over a wedge in the pie chart, you can see a count of messages sent or received.</span></span>

<span data-ttu-id="aa9ca-331">Si hace clic en **filtros** en una vista de informe, puede especificar un intervalo de fechas con **fecha de inicio** y fecha de **finalización**.</span><span class="sxs-lookup"><span data-stu-id="aa9ca-331">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

![Gráfico circular en la vista de informe en el informe de remitentes y destinatarios principales](../../media/top-senders-and-recipients-report-view.png)

### <a name="details-table-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="aa9ca-333">Vista de tabla de detalles para el informe de remitentes y destinatarios principales</span><span class="sxs-lookup"><span data-stu-id="aa9ca-333">Details table view for the Top senders and recipient report</span></span>

<span data-ttu-id="aa9ca-334">Si hace clic en **ver tabla de detalles**, la información que se muestra depende del gráfico que estaba viendo:</span><span class="sxs-lookup"><span data-stu-id="aa9ca-334">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="aa9ca-335">**Mostrar datos para los \> remitentes de correo principales**</span><span class="sxs-lookup"><span data-stu-id="aa9ca-335">**Show data for \> Top mail senders**</span></span>

  - <span data-ttu-id="aa9ca-336">**Principales remitentes de correo**</span><span class="sxs-lookup"><span data-stu-id="aa9ca-336">**Top mail senders**</span></span>
  - <span data-ttu-id="aa9ca-337">**Count**</span><span class="sxs-lookup"><span data-stu-id="aa9ca-337">**Count**</span></span>

- <span data-ttu-id="aa9ca-338">**Mostrar datos para los \> principales destinatarios de correo**</span><span class="sxs-lookup"><span data-stu-id="aa9ca-338">**Show data for \> Top mail recipients**</span></span>

  - <span data-ttu-id="aa9ca-339">**Destinatarios principales de correo**</span><span class="sxs-lookup"><span data-stu-id="aa9ca-339">**Top mail recipients**</span></span>
  - <span data-ttu-id="aa9ca-340">**Count**</span><span class="sxs-lookup"><span data-stu-id="aa9ca-340">**Count**</span></span>

- <span data-ttu-id="aa9ca-341">**Mostrar datos para los \> principales destinatarios de correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="aa9ca-341">**Show data for \> Top spam recipients**</span></span>

  - <span data-ttu-id="aa9ca-342">**Principales destinatarios de correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="aa9ca-342">**Top spam recipients**</span></span>
  - <span data-ttu-id="aa9ca-343">**Count**</span><span class="sxs-lookup"><span data-stu-id="aa9ca-343">**Count**</span></span>

- <span data-ttu-id="aa9ca-344">**Mostrar datos para \> Destinatarios principales de malware** (EOP)</span><span class="sxs-lookup"><span data-stu-id="aa9ca-344">**Show data for \> Top malware recipients** (EOP)</span></span>

  - <span data-ttu-id="aa9ca-345">**Destinatarios principales de malware**</span><span class="sxs-lookup"><span data-stu-id="aa9ca-345">**Top malware recipients**</span></span>
  - <span data-ttu-id="aa9ca-346">**Count**</span><span class="sxs-lookup"><span data-stu-id="aa9ca-346">**Count**</span></span>

- <span data-ttu-id="aa9ca-347">**Mostrar datos para \> Principales destinatarios de malware (ATP)** (Office 365 ATP)</span><span class="sxs-lookup"><span data-stu-id="aa9ca-347">**Show data for \> Top malware recipients (ATP)** (Office 365 ATP)</span></span>

  - <span data-ttu-id="aa9ca-348">**Destinatarios principales de malware (ATP)**</span><span class="sxs-lookup"><span data-stu-id="aa9ca-348">**Top malware recipients (ATP)**</span></span>
  - <span data-ttu-id="aa9ca-349">**Count**</span><span class="sxs-lookup"><span data-stu-id="aa9ca-349">**Count**</span></span>

<span data-ttu-id="aa9ca-350">Si hace clic en **filtros** en una vista de tabla de detalles, puede especificar un intervalo de fechas con **fecha de inicio** y fecha de **finalización**.</span><span class="sxs-lookup"><span data-stu-id="aa9ca-350">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="aa9ca-351">Para volver a la vista de informe, haga clic en **Ver informe**.</span><span class="sxs-lookup"><span data-stu-id="aa9ca-351">To go back to the report view, click **View report**.</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="aa9ca-352">¿Qué permisos se necesitan para ver estos informes?</span><span class="sxs-lookup"><span data-stu-id="aa9ca-352">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="aa9ca-353">Para ver y usar los informes, debe ser miembro del grupo de roles especificado en el centro de seguridad & cumplimiento **y** en Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="aa9ca-353">To view and use the reports, you need to be a member of the specified role group in the Security & Compliance Center **and** in Exchange Online.</span></span>

- <span data-ttu-id="aa9ca-354">En el centro de seguridad & cumplimiento, debe ser miembro de uno de los siguientes grupos de roles:</span><span class="sxs-lookup"><span data-stu-id="aa9ca-354">In the Security & Compliance Center, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="aa9ca-355">-Organization Management-administrador de seguridad (también puede hacerlo en el [centro de administración de Azure Active Directory](https://aad.portal.azure.com) -lector de seguridad</span><span class="sxs-lookup"><span data-stu-id="aa9ca-355">-Organization Management -Security Administrator (you can also do this in the [Azure Active Directory admin center](https://aad.portal.azure.com) -Security Reader</span></span>

  <span data-ttu-id="aa9ca-356">Para obtener más información, vea [Permisos en el Centro de seguridad y cumplimiento](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span><span class="sxs-lookup"><span data-stu-id="aa9ca-356">For more information, see [Permissions in the Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span></span>

- <span data-ttu-id="aa9ca-357">En Exchange Online, debe ser miembro de uno de los siguientes grupos de roles:</span><span class="sxs-lookup"><span data-stu-id="aa9ca-357">In Exchange Online, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="aa9ca-358">-Administración de la organización: administración de la organización de solo vista-destinatarios de solo vista-administración de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="aa9ca-358">-Organization Management -View-only Organization Management -View-Only Recipients -Compliance Management</span></span>

<span data-ttu-id="aa9ca-359">Para obtener más información, consulte [Permissions in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) y [Manage role Groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span><span class="sxs-lookup"><span data-stu-id="aa9ca-359">For more information, see [Permissions in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) and [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

## <a name="related-topics"></a><span data-ttu-id="aa9ca-360">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="aa9ca-360">Related topics</span></span>

[<span data-ttu-id="aa9ca-361">Informes inteligentes y reportes en el Centro de seguridad y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="aa9ca-361">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="aa9ca-362">Reportes de flujo de Correo en el Centro de seguridad y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="aa9ca-362">Mail flow insights in the Security & Compliance Center</span></span>](mail-flow-insights-v2.md)

[<span data-ttu-id="aa9ca-363">Ver informes de seguridad de correo electrónico en el Centro de seguridad y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="aa9ca-363">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)

[<span data-ttu-id="aa9ca-364">Ver informes para la protección contra amenazas avanzada de Office 365</span><span class="sxs-lookup"><span data-stu-id="aa9ca-364">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)
