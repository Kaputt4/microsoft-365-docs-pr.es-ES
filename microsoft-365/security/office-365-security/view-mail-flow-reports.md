---
title: Ver informes de flujo de correo en el panel de informes
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
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
ms.openlocfilehash: d33bd62e9a06385bf3448b7744031ae030dbe3ca
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "48195848"
---
# <a name="view-mail-flow-reports-in-the-reports-dashboard-in-security--compliance-center"></a><span data-ttu-id="13484-103">Ver informes de flujo de correo en el panel informes del centro de seguridad & cumplimiento</span><span class="sxs-lookup"><span data-stu-id="13484-103">View mail flow reports in the Reports dashboard in Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="13484-104">Además de los informes de flujo de correo que están disponibles en el [panel del flujo de correo](mail-flow-insights-v2.md) en el centro de seguridad & cumplimiento, hay disponible una variedad de informes de flujo de correo adicionales en el panel de informes para ayudarle a supervisar su organización de 365 de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="13484-104">In addition to the mail flow reports that are available in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center, a variety of additional mail flow reports are available in the Reports dashboard to help you monitor your Microsoft 365 organization.</span></span>

<span data-ttu-id="13484-105">Si dispone de los [permisos necesarios](#what-permissions-are-needed-to-view-these-reports), puede ver estos informes en el [centro de seguridad & cumplimiento](https://office.protection.com) desde el panel de **informes** \> **Dashboard**.</span><span class="sxs-lookup"><span data-stu-id="13484-105">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the [Security & Compliance Center](https://office.protection.com) by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="13484-106">Para ir directamente al panel informes, Abra <https://protection.office.com/insightdashboard> .</span><span class="sxs-lookup"><span data-stu-id="13484-106">To go directly to the Reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![Panel de informes en el centro de seguridad & cumplimiento](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="connector-report"></a><span data-ttu-id="13484-108">Informe de conector</span><span class="sxs-lookup"><span data-stu-id="13484-108">Connector report</span></span>

<span data-ttu-id="13484-109">El **Informe de conectores** muestra la actividad de flujo de correo en los [conectores entrantes y](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) salientes que están configurados para su organización.</span><span class="sxs-lookup"><span data-stu-id="13484-109">The **Connector report** shows mail flow activity on the [inbound and outbound connectors](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) that are configured for your organization.</span></span>

<span data-ttu-id="13484-110">Para ver el informe, abra el [centro de seguridad & cumplimiento](https://protection.office.com), vaya **Reports** al \> **Panel** informes y seleccione **Informe de conector**.</span><span class="sxs-lookup"><span data-stu-id="13484-110">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Connector report**.</span></span> <span data-ttu-id="13484-111">Para ir directamente al informe, Abra <https://protection.office.com/reportv2?id=ConnectorReport> .</span><span class="sxs-lookup"><span data-stu-id="13484-111">To go directly to the report, open <https://protection.office.com/reportv2?id=ConnectorReport>.</span></span>

![Widget de informe de conectores en el panel de informes](../../media/connector-report-widget.png)

### <a name="report-view-for-the-connector-report"></a><span data-ttu-id="13484-113">Vista informes para el informe de conector</span><span class="sxs-lookup"><span data-stu-id="13484-113">Report view for the Connector report</span></span>

<span data-ttu-id="13484-114">Los siguientes gráficos están disponibles en la vista de informe:</span><span class="sxs-lookup"><span data-stu-id="13484-114">The following charts are available in report view:</span></span>

- <span data-ttu-id="13484-115">**Ver datos por: flujo del correo**: en este gráfico se muestra el número de mensajes entrantes y salientes organizados por:</span><span class="sxs-lookup"><span data-stu-id="13484-115">**View data by: Mail flow**: This chart shows the number of inbound and outbound messages organized by:</span></span>

  - <span data-ttu-id="13484-116">**Total**</span><span class="sxs-lookup"><span data-stu-id="13484-116">**Total**</span></span>
  - <span data-ttu-id="13484-117">**De Internet sin conector**</span><span class="sxs-lookup"><span data-stu-id="13484-117">**From the internet without a connector**</span></span>
  - <span data-ttu-id="13484-118">**A Internet sin conector**</span><span class="sxs-lookup"><span data-stu-id="13484-118">**To the internet without a connector**</span></span>
  - <span data-ttu-id="13484-119">Un conector específico que haya configurado.</span><span class="sxs-lookup"><span data-stu-id="13484-119">A specific connector that you've configured.</span></span>

  <span data-ttu-id="13484-120">Para aislar los datos del gráfico, use el control **Mostrar datos para** para seleccionar una de estas opciones o **todo el flujo de correo**.</span><span class="sxs-lookup"><span data-stu-id="13484-120">To isolate the data in the chart, use the **Show data for** control to select one of these options or **All mail flow**.</span></span>

  ![Ver los datos por flujo de correo en el informe de conectores](../../media/connector-report-view-data-by-mail-flow.png)

- <span data-ttu-id="13484-122">**Ver datos por: uso de TLS**: en este gráfico se muestra el porcentaje de uso de la versión de seguridad de la capa de transporte (TLS) para el flujo de correo.</span><span class="sxs-lookup"><span data-stu-id="13484-122">**View data by: TLS usage**: This chart shows the percentage of Transport Layer Security (TLS) version usage for mail flow.</span></span>

  <span data-ttu-id="13484-123">Para aislar los datos del gráfico, use el control **Mostrar datos para** para seleccionar una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="13484-123">To isolate the data in the chart, use the **Show data for** control to select one of the following options:</span></span>

  - <span data-ttu-id="13484-124">**Todo el flujo de correo**</span><span class="sxs-lookup"><span data-stu-id="13484-124">**All mail flow**</span></span>
  - <span data-ttu-id="13484-125">**De Internet sin conector**</span><span class="sxs-lookup"><span data-stu-id="13484-125">**From the internet without a connector**</span></span>
  - <span data-ttu-id="13484-126">**A Internet sin conector**</span><span class="sxs-lookup"><span data-stu-id="13484-126">**To the internet without a connector**</span></span>
  - <span data-ttu-id="13484-127">Un conector específico que haya configurado.</span><span class="sxs-lookup"><span data-stu-id="13484-127">A specific connector that you've configured.</span></span>

  ![Ver datos por uso de TLS en el informe de conectores](../../media/connector-report-view-data-by-tls-usage.png)

<span data-ttu-id="13484-129">Si hace clic en **filtros** en una vista de informe, puede especificar un intervalo de fechas con **fecha de inicio** y fecha de **finalización**.</span><span class="sxs-lookup"><span data-stu-id="13484-129">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-connector-report"></a><span data-ttu-id="13484-130">Vista de tabla de detalles para el informe de conector</span><span class="sxs-lookup"><span data-stu-id="13484-130">Details table view for the Connector report</span></span>

<span data-ttu-id="13484-131">Si hace clic en **ver tabla de detalles** en una vista de informe, se mostrará la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="13484-131">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="13484-132">**Date**</span><span class="sxs-lookup"><span data-stu-id="13484-132">**Date**</span></span>
- <span data-ttu-id="13484-133">**Dirección y nombre del conector**</span><span class="sxs-lookup"><span data-stu-id="13484-133">**Connector direction and name**</span></span>
- <span data-ttu-id="13484-134">**Tipo de conector**</span><span class="sxs-lookup"><span data-stu-id="13484-134">**Connector type**</span></span>
- <span data-ttu-id="13484-135">**¿TLS forzado?**: el valor **true** o **false**.</span><span class="sxs-lookup"><span data-stu-id="13484-135">**Forced TLS?**: The value **True** or **False**.</span></span>
- <span data-ttu-id="13484-136">**Sin TLS** (porcentaje)</span><span class="sxs-lookup"><span data-stu-id="13484-136">**No TLS** (percentage)</span></span>
- <span data-ttu-id="13484-137">**TLS 1,0** (porcentaje)</span><span class="sxs-lookup"><span data-stu-id="13484-137">**TLS 1.0** (percentage)</span></span>
- <span data-ttu-id="13484-138">**TLS 1,1** (porcentaje)</span><span class="sxs-lookup"><span data-stu-id="13484-138">**TLS 1.1** (percentage)</span></span>
- <span data-ttu-id="13484-139">**TLS 1,2** (porcentaje)</span><span class="sxs-lookup"><span data-stu-id="13484-139">**TLS 1.2** (percentage)</span></span>
- <span data-ttu-id="13484-140">**Volumen**: el número de mensajes.</span><span class="sxs-lookup"><span data-stu-id="13484-140">**Volume**: The number of messages.</span></span>

<span data-ttu-id="13484-141">Si hace clic en **filtros** en una vista de tabla de detalles, puede especificar un intervalo de fechas con **fecha de inicio** y fecha de **finalización**.</span><span class="sxs-lookup"><span data-stu-id="13484-141">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="13484-142">Para volver a la vista de informe, haga clic en **Ver informe**.</span><span class="sxs-lookup"><span data-stu-id="13484-142">To go back to the report view, click **View report**.</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="13484-143">Informe de reglas de transporte de Exchange</span><span class="sxs-lookup"><span data-stu-id="13484-143">Exchange transport rule report</span></span>

<span data-ttu-id="13484-144">El **Informe de reglas de transporte de Exchange** muestra el efecto de las reglas de flujo de correo (también conocidas como reglas de transporte) en los mensajes entrantes y salientes de la organización.</span><span class="sxs-lookup"><span data-stu-id="13484-144">The **Exchange transport rule report** shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="13484-145">Para ver el informe, abra el [centro de seguridad & cumplimiento](https://protection.office.com), vaya **Reports** al \> **Panel** informes y seleccione regla de **transporte de Exchange**.</span><span class="sxs-lookup"><span data-stu-id="13484-145">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Exchange Transport rule**.</span></span> <span data-ttu-id="13484-146">Para ir directamente al informe, Abra <https://protection.office.com/reportv2?id=ETRRuleReport> .</span><span class="sxs-lookup"><span data-stu-id="13484-146">To go directly to the report, open <https://protection.office.com/reportv2?id=ETRRuleReport>.</span></span>

![Widget de regla de transporte de Exchange en el panel informes](../../media/transport-rule-report-widget.png)

### <a name="report-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="13484-148">Vista informes para el informe de reglas de transporte de Exchange</span><span class="sxs-lookup"><span data-stu-id="13484-148">Report view for the Exchange transport rule report</span></span>

<span data-ttu-id="13484-149">Los siguientes gráficos están disponibles en la vista de informe:</span><span class="sxs-lookup"><span data-stu-id="13484-149">The following charts are available in report view:</span></span>

- <span data-ttu-id="13484-150">**Ver datos por: reglas** \> de transporte de Exchange **Desglose por: Dirección: en**este gráfico se muestra el número de mensajes **entrantes** y **salientes** que se vieron afectados por las reglas de transporte.</span><span class="sxs-lookup"><span data-stu-id="13484-150">**View data by: Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by transport rules.</span></span>

- <span data-ttu-id="13484-151">**Ver datos por: reglas** \> de transporte de Exchange **Desglose por: gravedad: en**este gráfico se muestra el número de gravedad **alta** y **mediana**y los mensajes de **gravedad baja** .</span><span class="sxs-lookup"><span data-stu-id="13484-151">**View data by: Exchange transport rules** \> **Break down by: Severity**: This chart shows the number of **High severity** and **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="13484-152">El nivel de gravedad se establece como una acción en la regla (**auditar esta regla con el nivel de gravedad** o _SetAuditSeverity_).</span><span class="sxs-lookup"><span data-stu-id="13484-152">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="13484-153">Para obtener más información, vea [acciones de las reglas de flujo de correo en Exchange Online](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span><span class="sxs-lookup"><span data-stu-id="13484-153">For more information, see [Mail flow rule actions in Exchange Online](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="13484-154">**Ver datos por: reglas de transporte de Exchange de DLP** \> **Desglose por: Dirección: en**este gráfico se muestra el número de mensajes **entrantes** y **salientes** que se vieron afectados por las reglas de transporte de prevención de pérdida de datos (DLP).</span><span class="sxs-lookup"><span data-stu-id="13484-154">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) transport rules.</span></span> <span data-ttu-id="13484-155">Puede refinar aún más el gráfico si selecciona una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="13484-155">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="13484-156">**Mostrar datos para: todas las reglas de transporte de DLP**</span><span class="sxs-lookup"><span data-stu-id="13484-156">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="13484-157">**Mostrar datos para: usuarios comprometidos**</span><span class="sxs-lookup"><span data-stu-id="13484-157">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="13484-158">**Mostrar datos para: bajo volumen de contenido detectado Patriot Act de Estados Unidos**</span><span class="sxs-lookup"><span data-stu-id="13484-158">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

- <span data-ttu-id="13484-159">**Ver datos por: reglas de transporte de Exchange de DLP** \> **Dividir por: dirección**: esta vista muestra el número de gravedad **alta** y **mediana**y los mensajes de **gravedad baja** que se vieron afectados por las reglas de transporte de DLP.</span><span class="sxs-lookup"><span data-stu-id="13484-159">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This view shows the number of **High severity** and **Medium severity**, and **Low severity** messages that were affected by DLP transport rules.</span></span> <span data-ttu-id="13484-160">Puede refinar aún más el gráfico si selecciona una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="13484-160">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="13484-161">**Mostrar datos para: todas las reglas de transporte de DLP**</span><span class="sxs-lookup"><span data-stu-id="13484-161">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="13484-162">**Mostrar datos para: usuarios comprometidos**</span><span class="sxs-lookup"><span data-stu-id="13484-162">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="13484-163">**Mostrar datos para: bajo volumen de contenido detectado Patriot Act de Estados Unidos**</span><span class="sxs-lookup"><span data-stu-id="13484-163">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

<span data-ttu-id="13484-164">Si hace clic en **filtros** en una vista de informe, puede modificar los resultados con los siguientes filtros::</span><span class="sxs-lookup"><span data-stu-id="13484-164">If you click **Filters** in a report view, you can modify the results with the following filters::</span></span>

- <span data-ttu-id="13484-165">**Fecha de inicio** y **fecha de finalización**</span><span class="sxs-lookup"><span data-stu-id="13484-165">**Start date** and **End date**</span></span>
- <span data-ttu-id="13484-166">Valores de dirección</span><span class="sxs-lookup"><span data-stu-id="13484-166">Direction values</span></span>
- <span data-ttu-id="13484-167">Valores de gravedad</span><span class="sxs-lookup"><span data-stu-id="13484-167">Severity values</span></span>

![Vista de informe en el informe de reglas de transporte de Exchange](../../media/transport-rule-report-report-view.png)

### <a name="details-table-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="13484-169">Vista de tabla de detalles para el informe de regla de transporte de Exchange</span><span class="sxs-lookup"><span data-stu-id="13484-169">Details table view for the Exchange transport rule report</span></span>

<span data-ttu-id="13484-170">Si hace clic en **ver tabla de detalles**, la información que se muestra depende del gráfico que estaba viendo:</span><span class="sxs-lookup"><span data-stu-id="13484-170">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="13484-171">**Ver datos por: reglas de transporte de Exchange**:</span><span class="sxs-lookup"><span data-stu-id="13484-171">**View data by: Exchange Transport rules**:</span></span>

  - <span data-ttu-id="13484-172">**Date**</span><span class="sxs-lookup"><span data-stu-id="13484-172">**Date**</span></span>
  - <span data-ttu-id="13484-173">**Regla de transporte**</span><span class="sxs-lookup"><span data-stu-id="13484-173">**Transport rule**</span></span>
  - <span data-ttu-id="13484-174">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="13484-174">**Subject**</span></span>
  - <span data-ttu-id="13484-175">**Dirección del remitente**</span><span class="sxs-lookup"><span data-stu-id="13484-175">**Sender address**</span></span>
  - <span data-ttu-id="13484-176">**Dirección del destinatario**</span><span class="sxs-lookup"><span data-stu-id="13484-176">**Recipient address**</span></span>
  - <span data-ttu-id="13484-177">**Gravedad**</span><span class="sxs-lookup"><span data-stu-id="13484-177">**Severity**</span></span>
  - <span data-ttu-id="13484-178">**Dirección**</span><span class="sxs-lookup"><span data-stu-id="13484-178">**Direction**</span></span>

- <span data-ttu-id="13484-179">**Ver datos por: reglas de transporte de DLP de Exchange**:</span><span class="sxs-lookup"><span data-stu-id="13484-179">**View data by: DLP Exchange transport rules**:</span></span>

  - <span data-ttu-id="13484-180">**Date**</span><span class="sxs-lookup"><span data-stu-id="13484-180">**Date**</span></span>
  - <span data-ttu-id="13484-181">**Directiva DLP**</span><span class="sxs-lookup"><span data-stu-id="13484-181">**DLP policy**</span></span>
  - <span data-ttu-id="13484-182">**Regla de transporte**</span><span class="sxs-lookup"><span data-stu-id="13484-182">**Transport rule**</span></span>
  - <span data-ttu-id="13484-183">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="13484-183">**Subject**</span></span>
  - <span data-ttu-id="13484-184">**Dirección del remitente**</span><span class="sxs-lookup"><span data-stu-id="13484-184">**Sender address**</span></span>
  - <span data-ttu-id="13484-185">**Dirección del destinatario**</span><span class="sxs-lookup"><span data-stu-id="13484-185">**Recipient address**</span></span>
  - <span data-ttu-id="13484-186">**Gravedad**</span><span class="sxs-lookup"><span data-stu-id="13484-186">**Severity**</span></span>
  - <span data-ttu-id="13484-187">**Dirección**</span><span class="sxs-lookup"><span data-stu-id="13484-187">**Direction**</span></span>

<span data-ttu-id="13484-188">Si hace clic en **filtros** en una vista de tabla de detalles, puede modificar los resultados con los filtros siguientes:</span><span class="sxs-lookup"><span data-stu-id="13484-188">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="13484-189">**Fecha de inicio** y **fecha de finalización**</span><span class="sxs-lookup"><span data-stu-id="13484-189">**Start date** and **End date**</span></span>
- <span data-ttu-id="13484-190">Valores de dirección</span><span class="sxs-lookup"><span data-stu-id="13484-190">Direction values</span></span>
- <span data-ttu-id="13484-191">Valores de gravedad</span><span class="sxs-lookup"><span data-stu-id="13484-191">Severity values</span></span>

<span data-ttu-id="13484-192">Para volver a la vista de informe, haga clic en **Ver informe**.</span><span class="sxs-lookup"><span data-stu-id="13484-192">To go back to the report view, click **View report**.</span></span>

## <a name="forwarding-report"></a><span data-ttu-id="13484-193">Reenvío de informes</span><span class="sxs-lookup"><span data-stu-id="13484-193">Forwarding report</span></span>

<span data-ttu-id="13484-194">El **Informe de reenvío** muestra los mensajes reenviados automáticamente de la organización a dominios externos de los buzones de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="13484-194">The **Forwarding report** shows your organization's automatically forwarded messages to external domains from Exchange Online mailboxes.</span></span> <span data-ttu-id="13484-195">Los mensajes reenviados pueden suponer un riesgo de seguridad o de cumplimiento, y pueden indicar una cuenta en peligro.</span><span class="sxs-lookup"><span data-stu-id="13484-195">Forwarded messages can pose a security or compliance risk, and might indicate a compromised account.</span></span>

<span data-ttu-id="13484-196">Para ver el informe, abra el [centro de seguridad & cumplimiento](https://protection.office.com), vaya **Reports** al \> **Panel** informes y seleccione **reenviar Informe**.</span><span class="sxs-lookup"><span data-stu-id="13484-196">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Forwarding report**.</span></span> <span data-ttu-id="13484-197">Para ir directamente al informe, Abra <https://protection.office.com/reportv2?id=MailFlowForwarding> .</span><span class="sxs-lookup"><span data-stu-id="13484-197">To go directly to the report, open <https://protection.office.com/reportv2?id=MailFlowForwarding>.</span></span>

![Reenvío del widget de informe en el panel informes](../../media/forwarding-report-widget.png)

### <a name="report-view-for-the-forwarding-report"></a><span data-ttu-id="13484-199">Vista informes para el informe de reenvío</span><span class="sxs-lookup"><span data-stu-id="13484-199">Report view for the Forwarding report</span></span>

<span data-ttu-id="13484-200">Los siguientes gráficos están disponibles en la vista de informe:</span><span class="sxs-lookup"><span data-stu-id="13484-200">The following charts are available in the report view:</span></span>

- <span data-ttu-id="13484-201">**Mostrar datos para: métodos de reenvío**: se muestran los métodos siguientes:</span><span class="sxs-lookup"><span data-stu-id="13484-201">**Show data for: Forwarding methods**: The following methods are shown:</span></span>

  - <span data-ttu-id="13484-202">**Regla de transporte**: también conocida como [reglas de flujo de correo](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span><span class="sxs-lookup"><span data-stu-id="13484-202">**Transport rule**: Also known as [mail flow rules](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span></span>
  - <span data-ttu-id="13484-203">**Regla de buzón de correo**: también conocida como reglas de la [bandeja de entrada](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).</span><span class="sxs-lookup"><span data-stu-id="13484-203">**Mailbox rule**: Also known as [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).</span></span>

  ![Vista de métodos de reenvío en el informe de reenvío](../../media/forwarding-report-forwarding-methods.png)

- <span data-ttu-id="13484-205">**Mostrar datos de: dominios de reenvío**: esta vista muestra los dominios de destinatario que son los destinos para el reenvío.</span><span class="sxs-lookup"><span data-stu-id="13484-205">**Show data for: Forwarding domains**: This view shows the recipient domains that are the destinations for forwarding.</span></span>

  ![Vista de dominios de reenvío en el informe de reenvío](../../media/forwarding-report-forwarding-domains.png)

- <span data-ttu-id="13484-207">**Mostrar datos para: reenviadores**: se muestran los siguientes reenviadores:</span><span class="sxs-lookup"><span data-stu-id="13484-207">**Show data for: Forwarders**: The following forwarders are shown:</span></span>

  - <span data-ttu-id="13484-208">**Regla de transporte**</span><span class="sxs-lookup"><span data-stu-id="13484-208">**Transport rule**</span></span>
  - <span data-ttu-id="13484-209">El buzón de correo que contiene la regla de reenvío de la bandeja de entrada.</span><span class="sxs-lookup"><span data-stu-id="13484-209">The mailbox that contains the forwarding Inbox rule.</span></span>

  ![Vista de reenvíos en el informe de reenvío](../../media/forwarding-report-forwarders.png)

<span data-ttu-id="13484-211">Si hace clic en **filtros** en una vista de informe, puede especificar un intervalo de fechas con **fecha de inicio** y fecha de **finalización**.</span><span class="sxs-lookup"><span data-stu-id="13484-211">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-report"></a><span data-ttu-id="13484-212">Vista de tabla de detalles para el informe de reenvío</span><span class="sxs-lookup"><span data-stu-id="13484-212">Details table view for the Forwarding report</span></span>

<span data-ttu-id="13484-213">Si hace clic en **ver tabla de detalles** en una vista de informe, se mostrará la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="13484-213">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="13484-214">**Reenviadores**: la **regla de transporte** de valor o el buzón que contiene la regla de reenvío de la bandeja de entrada.</span><span class="sxs-lookup"><span data-stu-id="13484-214">**Forwarders**: The value **Transport rule** or the mailbox that contains the forwarding Inbox rule.</span></span>
- <span data-ttu-id="13484-215">**Tipo de reenvío**: regla de **buzón de correo** de valor o regla de **transporte**.</span><span class="sxs-lookup"><span data-stu-id="13484-215">**Forwarding type**: The value **Mailbox rule** or **Transport rule**.</span></span>
- <span data-ttu-id="13484-216">**Nombre de destinatario**</span><span class="sxs-lookup"><span data-stu-id="13484-216">**Recipient name**</span></span>
- <span data-ttu-id="13484-217">**Dominio del destinatario**</span><span class="sxs-lookup"><span data-stu-id="13484-217">**Recipient domain**</span></span>
- <span data-ttu-id="13484-218">**Detalles**: este es el valor de GUID de la regla de flujo de correo o el valor RuleIdentity de la regla de bandeja de entrada.</span><span class="sxs-lookup"><span data-stu-id="13484-218">**Details**: This is the GUID value of the mail flow rule, or the RuleIdentity value of the Inbox rule.</span></span>
- <span data-ttu-id="13484-219">**Count**</span><span class="sxs-lookup"><span data-stu-id="13484-219">**Count**</span></span>
- <span data-ttu-id="13484-220">**Primera fecha de reenvío**</span><span class="sxs-lookup"><span data-stu-id="13484-220">**First forward date**</span></span>

<span data-ttu-id="13484-221">Si hace clic en **filtros** en una vista de tabla de detalles, puede especificar un intervalo de fechas con **fecha de inicio** y fecha de **finalización**.</span><span class="sxs-lookup"><span data-stu-id="13484-221">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="13484-222">Para volver a la vista informes, haga clic en **Ver informe**.</span><span class="sxs-lookup"><span data-stu-id="13484-222">To go back to the reports view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="13484-223">Informe de estado de flujo de notificación</span><span class="sxs-lookup"><span data-stu-id="13484-223">Mailflow status report</span></span>

<span data-ttu-id="13484-224">El **Informe de estado de flujo** de correo es similar al [Informe de correo electrónico enviado y recibido](#sent-and-received-email-report), con información adicional sobre el correo electrónico permitido o bloqueado en el servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="13484-224">The **Mailflow status report** is similar to the [Sent and received email report](#sent-and-received-email-report), with additional information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="13484-225">Este es el único informe que contiene información sobre la protección perimetral y muestra la cantidad de correo electrónico que se bloquea antes de que se permita el servicio para su evaluación por parte de Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="13484-225">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="13484-226">Es importante comprender que si un mensaje se envía a cinco destinatarios, se cuenta como cinco mensajes diferentes y no un mensaje.</span><span class="sxs-lookup"><span data-stu-id="13484-226">It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>
<span data-ttu-id="13484-227">Para ver el informe, abra el [centro de seguridad & cumplimiento](https://protection.office.com), vaya **Reports** al \> **Panel** informes y seleccione informe de **Estado de flujo**de información.</span><span class="sxs-lookup"><span data-stu-id="13484-227">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Mailflow status report**.</span></span> <span data-ttu-id="13484-228">Para ir directamente al **Informe de estado del flujo de correo**, Abra <https://protection.office.com/mailflowStatusReport> .</span><span class="sxs-lookup"><span data-stu-id="13484-228">To go directly to the **Mail flow status report**, open <https://protection.office.com/mailflowStatusReport>.</span></span>

![Widget de informe de estado de flujo de registros en el panel informes](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="13484-230">Tipo de vista para el informe de estado de flujo de información</span><span class="sxs-lookup"><span data-stu-id="13484-230">Type view for the Mailflow status report</span></span>

<span data-ttu-id="13484-231">Al abrir el informe, la ficha **tipo** se selecciona de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="13484-231">When you open the report, the **Type** tab is selected by default.</span></span> <span data-ttu-id="13484-232">De forma predeterminada, esta vista contiene un gráfico y una tabla de datos que se configura con los siguientes filtros:</span><span class="sxs-lookup"><span data-stu-id="13484-232">By default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="13484-233">**Fecha**: los últimos 7 días.</span><span class="sxs-lookup"><span data-stu-id="13484-233">**Date**: The last 7 days.</span></span>
- <span data-ttu-id="13484-234">**Dirección**:</span><span class="sxs-lookup"><span data-stu-id="13484-234">**Direction**:</span></span>

  - <span data-ttu-id="13484-235">**Entrada**</span><span class="sxs-lookup"><span data-stu-id="13484-235">**Inbound**</span></span>
  - <span data-ttu-id="13484-236">**Saliente**</span><span class="sxs-lookup"><span data-stu-id="13484-236">**Outbound**</span></span>
  - <span data-ttu-id="13484-237">**Dentro de la organización**: este recuento es para los mensajes dentro de un espacio empresarial es decir</span><span class="sxs-lookup"><span data-stu-id="13484-237">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="13484-238">el remitente abc@domain.com envía al destinatario xyz@domain.com (cuenta por separado de **entrada** y de **salida**)</span><span class="sxs-lookup"><span data-stu-id="13484-238">sender abc@domain.com sends to recipient xyz@domain.com  (counted separately from **Inbound** and **Outbound**)</span></span>

- <span data-ttu-id="13484-239">**Tipo**:</span><span class="sxs-lookup"><span data-stu-id="13484-239">**Type**:</span></span>

  - <span data-ttu-id="13484-240">**Correo bueno**</span><span class="sxs-lookup"><span data-stu-id="13484-240">**Good mail**</span></span>
  - <span data-ttu-id="13484-241">**Malware**</span><span class="sxs-lookup"><span data-stu-id="13484-241">**Malware**</span></span>
  - <span data-ttu-id="13484-242">**Correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="13484-242">**Spam**</span></span>
  - <span data-ttu-id="13484-243">**Protección perimetral**</span><span class="sxs-lookup"><span data-stu-id="13484-243">**Edge protection**</span></span>
  - <span data-ttu-id="13484-244">**Mensajes de regla**</span><span class="sxs-lookup"><span data-stu-id="13484-244">**Rule messages**</span></span>
  - <span data-ttu-id="13484-245">**Correo de suplantación de identidad**</span><span class="sxs-lookup"><span data-stu-id="13484-245">**Phishing email**</span></span>

<span data-ttu-id="13484-246">El gráfico se organiza por los valores de **tipo** .</span><span class="sxs-lookup"><span data-stu-id="13484-246">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="13484-247">Puede cambiar estos filtros haciendo clic en **filtrar** o haciendo clic en un valor de la leyenda del gráfico.</span><span class="sxs-lookup"><span data-stu-id="13484-247">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span>

<span data-ttu-id="13484-248">La tabla de datos contiene la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="13484-248">The data table contains the following information:</span></span>

- <span data-ttu-id="13484-249">**Dirección**</span><span class="sxs-lookup"><span data-stu-id="13484-249">**Direction**</span></span>
- <span data-ttu-id="13484-250">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="13484-250">**Type**</span></span>
- <span data-ttu-id="13484-251">**24 horas**</span><span class="sxs-lookup"><span data-stu-id="13484-251">**24 hours**</span></span>
- <span data-ttu-id="13484-252">**3 días**</span><span class="sxs-lookup"><span data-stu-id="13484-252">**3 days**</span></span>
- <span data-ttu-id="13484-253">**7 días**</span><span class="sxs-lookup"><span data-stu-id="13484-253">**7 days**</span></span>
- <span data-ttu-id="13484-254">**15 días**</span><span class="sxs-lookup"><span data-stu-id="13484-254">**15 days**</span></span>
- <span data-ttu-id="13484-255">**30 días**</span><span class="sxs-lookup"><span data-stu-id="13484-255">**30 days**</span></span>

<span data-ttu-id="13484-256">Si hace clic en **elegir una categoría para obtener más información**, puede seleccionar uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="13484-256">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="13484-257">**Correo electrónico de suplantación de identidad**: esta selección le lleva al [Informe de estado de protección contra amenazas](view-email-security-reports.md#threat-protection-status-report).</span><span class="sxs-lookup"><span data-stu-id="13484-257">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="13484-258">**Malware en correo electrónico**: esta selección le lleva al [Informe de estado de protección contra amenazas](view-email-security-reports.md#threat-protection-status-report).</span><span class="sxs-lookup"><span data-stu-id="13484-258">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="13484-259">**Detecciones de correo no deseado**: esta selección le lleva al [Informe de detecciones de correo no deseado](view-email-security-reports.md#spam-detections-report).</span><span class="sxs-lookup"><span data-stu-id="13484-259">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="13484-260">**Correo no deseado de Edge bloqueado**: esta selección le lleva al [Informe de detecciones de correo no deseado](view-email-security-reports.md#spam-detections-report).</span><span class="sxs-lookup"><span data-stu-id="13484-260">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="13484-261">**Exportar**:</span><span class="sxs-lookup"><span data-stu-id="13484-261">**Export**:</span></span>

<span data-ttu-id="13484-262">Para la vista de detalles, solo puede exportar datos de un día.</span><span class="sxs-lookup"><span data-stu-id="13484-262">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="13484-263">Por lo tanto, si desea exportar datos durante 7 días, necesitará hacer 7 acciones de exportación diferentes.</span><span class="sxs-lookup"><span data-stu-id="13484-263">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="13484-264">Cada archivo. csv exportado está limitado a 150.000 filas.</span><span class="sxs-lookup"><span data-stu-id="13484-264">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="13484-265">Si los datos de ese día contienen más de 150.000 filas, se crearán varios archivos. csv.</span><span class="sxs-lookup"><span data-stu-id="13484-265">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="13484-266">Tipo ver en el informe de estado de flujo de información</span><span class="sxs-lookup"><span data-stu-id="13484-266">Type view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="13484-267">Vista de dirección para el informe de estado de flujo de información</span><span class="sxs-lookup"><span data-stu-id="13484-267">Direction view for the Mailflow status report</span></span>

<span data-ttu-id="13484-268">Si hace clic en la ficha **Dirección** , se usarán los mismos filtros predeterminados de la vista de **tipos** .</span><span class="sxs-lookup"><span data-stu-id="13484-268">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="13484-269">El gráfico está organizado por valores de **Dirección** .</span><span class="sxs-lookup"><span data-stu-id="13484-269">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="13484-270">Puede cambiar estos filtros haciendo clic en **filtrar** o haciendo clic en un valor de la leyenda del gráfico.</span><span class="sxs-lookup"><span data-stu-id="13484-270">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span> <span data-ttu-id="13484-271">Se usan los mismos filtros de la vista **tipo** .</span><span class="sxs-lookup"><span data-stu-id="13484-271">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="13484-272">La tabla de datos contiene la misma información de la vista de **tipo** .</span><span class="sxs-lookup"><span data-stu-id="13484-272">The data table contains same information from the **Type** view.</span></span>

<span data-ttu-id="13484-273">El comportamiento seleccionar **una categoría para obtener más información sobre** las selecciones disponibles y el comportamiento es el mismo que el de la vista **tipo** .</span><span class="sxs-lookup"><span data-stu-id="13484-273">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

<span data-ttu-id="13484-274">**Exportar**:</span><span class="sxs-lookup"><span data-stu-id="13484-274">**Export**:</span></span>

<span data-ttu-id="13484-275">Para la vista de detalles, solo puede exportar datos de un día.</span><span class="sxs-lookup"><span data-stu-id="13484-275">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="13484-276">Por lo tanto, si desea exportar datos durante 7 días, necesitará hacer 7 acciones de exportación diferentes.</span><span class="sxs-lookup"><span data-stu-id="13484-276">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="13484-277">Cada archivo. csv exportado está limitado a 150.000 filas.</span><span class="sxs-lookup"><span data-stu-id="13484-277">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="13484-278">Si los datos de ese día contienen más de 150.000 filas, se crearán varios archivos. csv.</span><span class="sxs-lookup"><span data-stu-id="13484-278">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="13484-279">Vista de dirección en el informe de estado de flujo de notificación</span><span class="sxs-lookup"><span data-stu-id="13484-279">Direction view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-direction-view.png)

### <a name="funnel-view-for-the-mailflow-status-report"></a><span data-ttu-id="13484-280">Vista de embudo para el informe de estado de flujo de información</span><span class="sxs-lookup"><span data-stu-id="13484-280">Funnel view for the Mailflow status report</span></span>

<span data-ttu-id="13484-281">La vista de **embudo** muestra cómo las características de protección contra amenazas de correo electrónico de Microsoft filtran el correo entrante y saliente de su organización.</span><span class="sxs-lookup"><span data-stu-id="13484-281">The **Funnel** view shows you how Microsoft's email threat protection features filter incoming and outgoing email in your organization.</span></span> <span data-ttu-id="13484-282">Proporciona detalles sobre el recuento de correo electrónico total y cómo las características de protección contra amenazas configuradas, incluida la protección perimetral, anti-malware, antiphishing, contra correo no deseado y contra la suplantación de identidad afectan a este recuento.</span><span class="sxs-lookup"><span data-stu-id="13484-282">It provides details on the total email count, and how the configured threat protection features, including edge protection, anti-malware, anti-phishing, anti-spam, and anti-spoofing affect this count.</span></span>

<span data-ttu-id="13484-283">Si hace clic en la ficha **embudo** , de forma predeterminada, esta vista contendrá un gráfico y una tabla de datos configurada con los siguientes filtros:</span><span class="sxs-lookup"><span data-stu-id="13484-283">If you click the **Funnel** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="13484-284">**Fecha**: los últimos 7 días.</span><span class="sxs-lookup"><span data-stu-id="13484-284">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="13484-285">**Dirección**:</span><span class="sxs-lookup"><span data-stu-id="13484-285">**Direction**:</span></span>

  - <span data-ttu-id="13484-286">**Entrada**</span><span class="sxs-lookup"><span data-stu-id="13484-286">**Inbound**</span></span>
  - <span data-ttu-id="13484-287">**Saliente**</span><span class="sxs-lookup"><span data-stu-id="13484-287">**Outbound**</span></span>
  - <span data-ttu-id="13484-288">**Dentro de la organización**: este recuento es para los mensajes enviados en un espacio empresarial; es decir, el abc@domain.com del remitente envía al destinatario xyz@domain.com (contado por separado de entrante y saliente).</span><span class="sxs-lookup"><span data-stu-id="13484-288">**Intra-org**: This count is for messages sent within a tenant; i.e, sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound).</span></span>

<span data-ttu-id="13484-289">La vista agregada y la vista de tabla de datos permiten 90 días de filtrado.</span><span class="sxs-lookup"><span data-stu-id="13484-289">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="13484-290">Si hace clic en **filtrar**, puede filtrar tanto el gráfico como la tabla de datos.</span><span class="sxs-lookup"><span data-stu-id="13484-290">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="13484-291">Este gráfico muestra el número de correos electrónicos organizados por:</span><span class="sxs-lookup"><span data-stu-id="13484-291">This chart shows the email count organized by:</span></span>

- <span data-ttu-id="13484-292">**Correo electrónico total**</span><span class="sxs-lookup"><span data-stu-id="13484-292">**Total email**</span></span>
- <span data-ttu-id="13484-293">**Correo electrónico tras la protección perimetral**</span><span class="sxs-lookup"><span data-stu-id="13484-293">**Email after edge protection**</span></span>
- <span data-ttu-id="13484-294">**Correo electrónico después de anti-malware, reputación de archivo, bloque de tipo de archivo**</span><span class="sxs-lookup"><span data-stu-id="13484-294">**Email after anti-malware, file reputation, file type block**</span></span>
- <span data-ttu-id="13484-295">**Correo electrónico después de antiphishing, reputación de dirección URL, suplantación de marca, anti-falseamiento**</span><span class="sxs-lookup"><span data-stu-id="13484-295">**Email after anti-phish, URL reputation, brand impersonation, anti-spoof**</span></span>
- <span data-ttu-id="13484-296">**Correo electrónico después de la protección contra correo no deseado, filtrado de correo masivo**</span><span class="sxs-lookup"><span data-stu-id="13484-296">**Email after anti-spam, bulk mail filtering**</span></span>
- <span data-ttu-id="13484-297">**Correo electrónico después de suplantación de usuario y dominio**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="13484-297">**Email after user and domain impersonation**<sup>1</sup></span></span>
- <span data-ttu-id="13484-298">**Correo electrónico después de detonación de archivo y URL**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="13484-298">**Email after file and URL detonation**<sup>1</sup></span></span>
- <span data-ttu-id="13484-299">**Correo electrónico detectado como benigno después de la protección tras la entrega (dirección URL, clic en protección del tiempo)**</span><span class="sxs-lookup"><span data-stu-id="13484-299">**Email detected as benign after post-delivery protection (URL click time protection)**</span></span>

<span data-ttu-id="13484-300"><sup>1</sup> solo para ATP de Office 365</span><span class="sxs-lookup"><span data-stu-id="13484-300"><sup>1</sup> Office 365 ATP only</span></span>

<span data-ttu-id="13484-301">Para ver el correo electrónico filtrado por EOP o ATP por separado, haga clic en el valor de la leyenda del gráfico.</span><span class="sxs-lookup"><span data-stu-id="13484-301">To view the email filtered by EOP or ATP separately, click on the value in the chart legend.</span></span>

<span data-ttu-id="13484-302">La tabla de datos contiene la siguiente información, que se muestra en orden de fecha descendente:</span><span class="sxs-lookup"><span data-stu-id="13484-302">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="13484-303">**Date**</span><span class="sxs-lookup"><span data-stu-id="13484-303">**Date**</span></span>
- <span data-ttu-id="13484-304">**Correo electrónico total**</span><span class="sxs-lookup"><span data-stu-id="13484-304">**Total email**</span></span>
- <span data-ttu-id="13484-305">**Protección perimetral**</span><span class="sxs-lookup"><span data-stu-id="13484-305">**Edge protection**</span></span>
- <span data-ttu-id="13484-306">**Anti-malware, reputación de archivos, bloque de tipo de archivo**</span><span class="sxs-lookup"><span data-stu-id="13484-306">**Anti-malware, file reputation, file type block**</span></span>
- <span data-ttu-id="13484-307">**Anti-phish, reputación de dirección URL, suplantación de marca, antifalsificación**</span><span class="sxs-lookup"><span data-stu-id="13484-307">**Anti-phish, URL reputation, Brand impersonation, anti-spoof**</span></span>
- <span data-ttu-id="13484-308">**Contra correo electrónico no deseado, filtrado de correo masivo**</span><span class="sxs-lookup"><span data-stu-id="13484-308">**Anti-spam, bulk mail filtering**</span></span>
- <span data-ttu-id="13484-309">**Suplantación de usuario y dominio (ATP)**</span><span class="sxs-lookup"><span data-stu-id="13484-309">**User and domain impersonation (ATP)**</span></span>
- <span data-ttu-id="13484-310">**Detonación de archivo y dirección URL (ATP)**</span><span class="sxs-lookup"><span data-stu-id="13484-310">**File and URL detonation (ATP)**</span></span>
- <span data-ttu-id="13484-311">**Protección tras entrega y ZAP (ATP) o ZAP (EOP)**</span><span class="sxs-lookup"><span data-stu-id="13484-311">**Post-delivery protection and ZAP (ATP), or ZAP (EOP)**</span></span>

<span data-ttu-id="13484-312">Si selecciona una fila en la tabla de datos, se muestra un desglose de los recuentos de correo electrónico en el control flotante.</span><span class="sxs-lookup"><span data-stu-id="13484-312">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="13484-313">**Exportar**:</span><span class="sxs-lookup"><span data-stu-id="13484-313">**Export**:</span></span>

<span data-ttu-id="13484-314">Después de hacer clic en **exportar** en **Opciones**, puede seleccionar uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="13484-314">After you click **Export** under **Options**, you can select one of the following values:</span></span>

- <span data-ttu-id="13484-315">**Resumen (con datos para los últimos 90 días como máximo)**</span><span class="sxs-lookup"><span data-stu-id="13484-315">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="13484-316">**Detalles (con datos de 30 últimos días como máximo)**</span><span class="sxs-lookup"><span data-stu-id="13484-316">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="13484-317">En **fecha**, elija un rango y, a continuación, haga clic en **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="13484-317">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="13484-318">Los datos de los filtros actuales se exportarán a un archivo. csv.</span><span class="sxs-lookup"><span data-stu-id="13484-318">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="13484-319">Cada archivo. csv exportado está limitado a 150.000 filas.</span><span class="sxs-lookup"><span data-stu-id="13484-319">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="13484-320">Si los datos contienen más de 150.000 filas, se crearán varios archivos. csv.</span><span class="sxs-lookup"><span data-stu-id="13484-320">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![<span data-ttu-id="13484-321">Vista de embudo en el informe de estado de flujo de notificación</span><span class="sxs-lookup"><span data-stu-id="13484-321">Funnel view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-funnel-view.png)

### <a name="tech-view-for-the-mailflow-status-report"></a><span data-ttu-id="13484-322">Vista técnica del informe de estado de flujo de información</span><span class="sxs-lookup"><span data-stu-id="13484-322">Tech view for the Mailflow status report</span></span>

<span data-ttu-id="13484-323">La **vista técnica** es similar a la vista de **embudo** y proporciona detalles más granulares para las características de protección contra amenazas configuradas.</span><span class="sxs-lookup"><span data-stu-id="13484-323">The **Tech view** is similar to the **Funnel** view, providing more granular details for the configured threat protections features.</span></span> <span data-ttu-id="13484-324">Desde el gráfico, puede ver cómo se clasifican los mensajes en las diferentes etapas de la protección contra amenazas.</span><span class="sxs-lookup"><span data-stu-id="13484-324">From the chart, you can see how messages are categorized at the different stages of threat protection.</span></span>

<span data-ttu-id="13484-325">Si hace clic en la pestaña **vista técnica** , de forma predeterminada, esta vista contendrá un gráfico y una tabla de datos configurada con los siguientes filtros:</span><span class="sxs-lookup"><span data-stu-id="13484-325">If you click the **Tech view** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="13484-326">**Fecha**: los últimos 7 días.</span><span class="sxs-lookup"><span data-stu-id="13484-326">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="13484-327">**Dirección**:</span><span class="sxs-lookup"><span data-stu-id="13484-327">**Direction**:</span></span>

  - <span data-ttu-id="13484-328">**Entrada**</span><span class="sxs-lookup"><span data-stu-id="13484-328">**Inbound**</span></span>
  - <span data-ttu-id="13484-329">**Saliente**</span><span class="sxs-lookup"><span data-stu-id="13484-329">**Outbound**</span></span>
  - <span data-ttu-id="13484-330">**Dentro de la organización**: este recuento es para los mensajes dentro de un espacio empresarial es decir</span><span class="sxs-lookup"><span data-stu-id="13484-330">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="13484-331">el remitente abc@domain.com envía al destinatario xyz@domain.com (cuenta por separado de entrada y de salida)</span><span class="sxs-lookup"><span data-stu-id="13484-331">sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound)</span></span>

<span data-ttu-id="13484-332">La vista agregada y la vista de tabla de datos permiten 90 días de filtrado.</span><span class="sxs-lookup"><span data-stu-id="13484-332">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="13484-333">Si hace clic en **filtrar**, puede filtrar tanto el gráfico como la tabla de datos.</span><span class="sxs-lookup"><span data-stu-id="13484-333">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="13484-334">Este gráfico muestra los mensajes organizados en las siguientes categorías:</span><span class="sxs-lookup"><span data-stu-id="13484-334">This chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="13484-335">**Correo electrónico total**</span><span class="sxs-lookup"><span data-stu-id="13484-335">**Total email**</span></span>
- <span data-ttu-id="13484-336">**Límite permitido, perimetral filtrado**</span><span class="sxs-lookup"><span data-stu-id="13484-336">**Edge allow, edge filtered**</span></span>
- <span data-ttu-id="13484-337">**No es malware, detección de datos adjuntos seguros (ATP), detección del motor antimalware, bloqueo de reglas**</span><span class="sxs-lookup"><span data-stu-id="13484-337">**Not malware, Safe attachments detection (ATP), Anti-malware engine detection, rule block**</span></span>
- <span data-ttu-id="13484-338">**No phish, error de DMARC, detección de suplantación, detección de suplantación de identidad, detección de phish**</span><span class="sxs-lookup"><span data-stu-id="13484-338">**Not phish, DMARC failure, impersonation detection, spoof detection, phish detection**</span></span>
- <span data-ttu-id="13484-339">**Sin detección con detonación de dirección URL, detección de detonación de dirección URL (ATP)**</span><span class="sxs-lookup"><span data-stu-id="13484-339">**No detection with URL detonation, URL detonation detection (ATP)**</span></span>
- <span data-ttu-id="13484-340">**No es correo no deseado, correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="13484-340">**Not spam, spam**</span></span>
- <span data-ttu-id="13484-341">**Correo electrónico no malintencionado, detección de vínculos seguros (ATP), ZAP**</span><span class="sxs-lookup"><span data-stu-id="13484-341">**Non-malicious email, safe links detection (ATP), ZAP**</span></span>

<span data-ttu-id="13484-342">Cuando desplaza el puntero sobre una categoría del gráfico, puede ver el número de mensajes que hay en esa categoría.</span><span class="sxs-lookup"><span data-stu-id="13484-342">When you hover over a category in the chart, you can see the number of messages in that category.</span></span>

<span data-ttu-id="13484-343">La tabla de datos contiene la siguiente información, que se muestra en orden de fecha descendente:</span><span class="sxs-lookup"><span data-stu-id="13484-343">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="13484-344">**Date**</span><span class="sxs-lookup"><span data-stu-id="13484-344">**Date**</span></span>
- <span data-ttu-id="13484-345">**Correo electrónico total**</span><span class="sxs-lookup"><span data-stu-id="13484-345">**Total email**</span></span>
- <span data-ttu-id="13484-346">**Borde filtrado**</span><span class="sxs-lookup"><span data-stu-id="13484-346">**Edge filtered**</span></span>
- <span data-ttu-id="13484-347">**Motor antimalware, datos adjuntos seguros, regla filtrado**</span><span class="sxs-lookup"><span data-stu-id="13484-347">**Anti-malware engine, safe attachments, rule filtered**</span></span>
- <span data-ttu-id="13484-348">**DMARC, suplantación, falsificación, phish filtrado**</span><span class="sxs-lookup"><span data-stu-id="13484-348">**DMARC, impersonation, spoof, phish filtered**</span></span>
- <span data-ttu-id="13484-349">**Detección de detonación de dirección URL**</span><span class="sxs-lookup"><span data-stu-id="13484-349">**URL detonation detection**</span></span>
- <span data-ttu-id="13484-350">**Filtrado contra correo electrónico no deseado**</span><span class="sxs-lookup"><span data-stu-id="13484-350">**Anti-spam filtered**</span></span>
- <span data-ttu-id="13484-351">**ZAP quitado**</span><span class="sxs-lookup"><span data-stu-id="13484-351">**ZAP removed**</span></span>
- <span data-ttu-id="13484-352">**Detección por vínculos seguros**</span><span class="sxs-lookup"><span data-stu-id="13484-352">**Detection by safe links**</span></span>

<span data-ttu-id="13484-353">Si selecciona una fila en la tabla de datos, se muestra un desglose de los recuentos de correo electrónico en el control flotante.</span><span class="sxs-lookup"><span data-stu-id="13484-353">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="13484-354">**Exportar**:</span><span class="sxs-lookup"><span data-stu-id="13484-354">**Export**:</span></span>

<span data-ttu-id="13484-355">Al hacer clic en **exportar**, en **Opciones** , puede seleccionar uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="13484-355">On clicking **Export**, under **Options** you can select one of the following values:</span></span>

- <span data-ttu-id="13484-356">**Resumen (con datos para los últimos 90 días como máximo)**</span><span class="sxs-lookup"><span data-stu-id="13484-356">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="13484-357">**Detalles (con datos de 30 últimos días como máximo)**</span><span class="sxs-lookup"><span data-stu-id="13484-357">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="13484-358">En **fecha**, elija un rango y, a continuación, haga clic en **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="13484-358">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="13484-359">Los datos de los filtros actuales se exportarán a un archivo. csv.</span><span class="sxs-lookup"><span data-stu-id="13484-359">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="13484-360">Cada archivo. csv exportado está limitado a 150.000 filas.</span><span class="sxs-lookup"><span data-stu-id="13484-360">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="13484-361">Si los datos contienen más de 150.000 filas, se crearán varios archivos. csv.</span><span class="sxs-lookup"><span data-stu-id="13484-361">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![<span data-ttu-id="13484-362">Vista de Tech en el informe de estado de flujo de información</span><span class="sxs-lookup"><span data-stu-id="13484-362">Tech view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-Tech-view.png)

## <a name="sent-and-received-email-report"></a><span data-ttu-id="13484-363">Informe de correo electrónico enviado y recibido</span><span class="sxs-lookup"><span data-stu-id="13484-363">Sent and received email report</span></span>

<span data-ttu-id="13484-364">El informe de **correo electrónico enviado y recibido** es un informe inteligente que muestra información sobre el correo electrónico entrante y saliente, incluidas las detecciones de correo no deseado, malware y el correo electrónico identificado como "bueno".</span><span class="sxs-lookup"><span data-stu-id="13484-364">The **Sent and received email** report is a smart report that shows information about incoming and outgoing email, including spam detections, malware, and email identified as "good."</span></span> <span data-ttu-id="13484-365">La diferencia entre este informe y el [Informe de estado de flujo](#mailflow-status-report) de correos es la siguiente: este informe no incluye datos sobre los mensajes bloqueados por la protección perimetral. Es importante comprender que si un mensaje se envía a cinco destinatarios, se cuenta como un mensaje.</span><span class="sxs-lookup"><span data-stu-id="13484-365">The difference between this report and the [Mailflow status report](#mailflow-status-report) is: this report doesn't include data about messages blocked by edge protection.It's important to understand that if a message is sent to five recipients we count it as one message.</span></span>

<span data-ttu-id="13484-366">La vista agregada y la vista de detalles del informe permiten 90 días de filtrado.</span><span class="sxs-lookup"><span data-stu-id="13484-366">The aggregate view and the detail view of the report allow for 90 days of filtering.</span></span>

<span data-ttu-id="13484-367">Para ver el informe, abra el [centro de seguridad & cumplimiento](https://protection.office.com), vaya **Reports** al \> **Panel** informes y seleccione **correo electrónico enviado y recibido**.</span><span class="sxs-lookup"><span data-stu-id="13484-367">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Sent and received email**.</span></span> <span data-ttu-id="13484-368">Para ir directamente al informe, Abra <https://protection.office.com/reportv2?id=SentAndReceivedMailATP> .</span><span class="sxs-lookup"><span data-stu-id="13484-368">To go directly to the report, open <https://protection.office.com/reportv2?id=SentAndReceivedMailATP>.</span></span>

![Widget de correo electrónico enviado y recibido en el panel de informes](../../media/sent-and-received-email-report-widget.png)

### <a name="report-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="13484-370">Vista informes para el informe de correo electrónico enviado y recibido</span><span class="sxs-lookup"><span data-stu-id="13484-370">Report view for the Sent and received email report</span></span>

<span data-ttu-id="13484-371">Los siguientes gráficos están disponibles en la vista de informe:</span><span class="sxs-lookup"><span data-stu-id="13484-371">The following charts are available in the report view:</span></span>

- <span data-ttu-id="13484-372">**Dividir por: escriba**: el gráfico muestra todas las categorías disponibles:</span><span class="sxs-lookup"><span data-stu-id="13484-372">**Break down by: Type**: The chart shows all available categories:</span></span>

  - <span data-ttu-id="13484-373">**Total**</span><span class="sxs-lookup"><span data-stu-id="13484-373">**Total**</span></span>
  - <span data-ttu-id="13484-374">**Correo bueno**</span><span class="sxs-lookup"><span data-stu-id="13484-374">**Good mail**</span></span>
  - <span data-ttu-id="13484-375">**Malware (anti-malware)** (EOP)</span><span class="sxs-lookup"><span data-stu-id="13484-375">**Malware (anti-malware)** (EOP)</span></span>
  - <span data-ttu-id="13484-376">**Detecciones de correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="13484-376">**Spam detections**</span></span>
  - <span data-ttu-id="13484-377">**Mensajes de regla**</span><span class="sxs-lookup"><span data-stu-id="13484-377">**Rule messages**</span></span>
  - <span data-ttu-id="13484-378">**Malware avanzado** (Office 365 ATP)</span><span class="sxs-lookup"><span data-stu-id="13484-378">**Advanced malware** (Office 365 ATP)</span></span>

  <span data-ttu-id="13484-379">Al pasar el mouse sobre un día (punto de datos) del gráfico, puede ver los detalles de ese día.</span><span class="sxs-lookup"><span data-stu-id="13484-379">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![Tipo ver en el informe de correo electrónico enviado y recibido](../../media/sent-and-received-email-report-type-view.png)

- <span data-ttu-id="13484-381">**Desglose por: dirección**: el gráfico muestra los datos **totales**, **entrantes**y **salientes** .</span><span class="sxs-lookup"><span data-stu-id="13484-381">**Break down by: Direction**: The chart shows **Total**, **Inbound**, and **Outbound** data.</span></span> <span data-ttu-id="13484-382">Al pasar el mouse sobre un día (punto de datos) del gráfico, puede ver los detalles de ese día.</span><span class="sxs-lookup"><span data-stu-id="13484-382">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![Vista de dirección en el informe de correo electrónico enviados y recibidos](../../media/sent-and-received-email-report-direction-view.png)

- <span data-ttu-id="13484-384">**Explorar en profundidad por** \> **Malware (anti-malware)**: esta selección le lleva a las [detecciones de malware en el informe de correo electrónico](view-email-security-reports.md#malware-detections-in-email-report).</span><span class="sxs-lookup"><span data-stu-id="13484-384">**Drill down by** \> **Malware (anti-malware)**: This selection takes you to the [Malware detections in email report](view-email-security-reports.md#malware-detections-in-email-report).</span></span>

- <span data-ttu-id="13484-385">**Explorar en profundidad por** \> **Detecciones de correo no deseado)**: esta selección le lleva al [Informe de detecciones de correo no deseado](view-email-security-reports.md#spam-detections-report).</span><span class="sxs-lookup"><span data-stu-id="13484-385">**Drill down by** \> **Spam detections)**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="13484-386">Si hace clic en **filtros** en una vista de informe, puede modificar los resultados con los siguientes filtros:</span><span class="sxs-lookup"><span data-stu-id="13484-386">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="13484-387">**Fecha de inicio** y **fecha de finalización**</span><span class="sxs-lookup"><span data-stu-id="13484-387">**Start date** and **End date**</span></span>
- <span data-ttu-id="13484-388">Valores de dirección</span><span class="sxs-lookup"><span data-stu-id="13484-388">Direction values</span></span>
- <span data-ttu-id="13484-389">Valores de tipo</span><span class="sxs-lookup"><span data-stu-id="13484-389">Type values</span></span>

<span data-ttu-id="13484-390">Para volver a la vista de informe, haga clic en **Ver informe**.</span><span class="sxs-lookup"><span data-stu-id="13484-390">To go back to the report view, click **View report**.</span></span>

### <a name="details-table-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="13484-391">Vista de tabla de detalles para el informe de correo electrónico enviado y recibido</span><span class="sxs-lookup"><span data-stu-id="13484-391">Details table view for the Sent and received email report</span></span>

<span data-ttu-id="13484-392">Si hace clic en **ver tabla de detalles** en el cuadro **desglosar por: dirección** o **dividir por:** vista de dirección, se muestra la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="13484-392">If you click **View details table** in the **Break down by: Direction** or **Break down by: Direction** view, the following information is shown:</span></span>

- <span data-ttu-id="13484-393">**Fecha (UTC)**</span><span class="sxs-lookup"><span data-stu-id="13484-393">**Date (UTC)**</span></span>
- <span data-ttu-id="13484-394">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="13484-394">**Type**</span></span>
- <span data-ttu-id="13484-395">**Dirección**</span><span class="sxs-lookup"><span data-stu-id="13484-395">**Direction**</span></span>
- <span data-ttu-id="13484-396">**Número de mensajes**</span><span class="sxs-lookup"><span data-stu-id="13484-396">**Message count**</span></span>

<span data-ttu-id="13484-397">Si hace clic en **filtros** en una vista de tabla de detalles, puede modificar los resultados con los filtros siguientes:</span><span class="sxs-lookup"><span data-stu-id="13484-397">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="13484-398">**Fecha de inicio** y **fecha de finalización**</span><span class="sxs-lookup"><span data-stu-id="13484-398">**Start date** and **End date**</span></span>
- <span data-ttu-id="13484-399">Valores de dirección</span><span class="sxs-lookup"><span data-stu-id="13484-399">Direction values</span></span>
- <span data-ttu-id="13484-400">Valores de tipo</span><span class="sxs-lookup"><span data-stu-id="13484-400">Type values</span></span>

<span data-ttu-id="13484-401">Para volver a la vista de informe, haga clic en **Ver informe**.</span><span class="sxs-lookup"><span data-stu-id="13484-401">To go back to the report view, click **View report**.</span></span>

## <a name="top-senders-and-recipients-report"></a><span data-ttu-id="13484-402">Informe de remitentes y destinatarios principales</span><span class="sxs-lookup"><span data-stu-id="13484-402">Top senders and recipients report</span></span>

<span data-ttu-id="13484-403">El informe de **remitentes y destinatarios principales** es un gráfico circular que muestra los principales remitentes y destinatarios de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="13484-403">The **Top senders and recipients** report is a pie chart showing your top email senders and recipients.</span></span>

<span data-ttu-id="13484-404">Para ver el informe, abra el [centro de seguridad & cumplimiento](https://protection.office.com), vaya **Reports** al \> **Panel** informes y seleccione **principales remitentes y destinatarios**.</span><span class="sxs-lookup"><span data-stu-id="13484-404">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top senders and recipients**.</span></span> <span data-ttu-id="13484-405">Para ir directamente al informe, Abra <https://protection.office.com/reportv2?id=TopSenderRecipientsATP> .</span><span class="sxs-lookup"><span data-stu-id="13484-405">To go directly to the report, open <https://protection.office.com/reportv2?id=TopSenderRecipientsATP>.</span></span>

![Widgets principales remitentes y destinatarios en el panel informes](../../media/top-senders-and-recipients-widget.png)

### <a name="report-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="13484-407">Vista informes para los principales informes de remitentes y destinatarios</span><span class="sxs-lookup"><span data-stu-id="13484-407">Report view for the Top senders and recipient report</span></span>

<span data-ttu-id="13484-408">Los siguientes gráficos están disponibles en la vista de informe:</span><span class="sxs-lookup"><span data-stu-id="13484-408">The following charts are available in the report view:</span></span>

- <span data-ttu-id="13484-409">**Mostrar datos para los \> remitentes de correo principales**</span><span class="sxs-lookup"><span data-stu-id="13484-409">**Show data for \> Top mail senders**</span></span>
- <span data-ttu-id="13484-410">**Mostrar datos para los \> principales destinatarios de correo**</span><span class="sxs-lookup"><span data-stu-id="13484-410">**Show data for \> Top mail recipients**</span></span>
- <span data-ttu-id="13484-411">**Mostrar datos para los \> principales destinatarios de correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="13484-411">**Show data for \> Top spam recipients**</span></span>
- <span data-ttu-id="13484-412">**Mostrar datos para \> Destinatarios principales de malware** (EOP)</span><span class="sxs-lookup"><span data-stu-id="13484-412">**Show data for \> Top malware recipients** (EOP)</span></span>
- <span data-ttu-id="13484-413">**Mostrar datos para \> Principales destinatarios de malware (ATP)** (Office 365 ATP)</span><span class="sxs-lookup"><span data-stu-id="13484-413">**Show data for \> Top malware recipients (ATP)** (Office 365 ATP)</span></span>

<span data-ttu-id="13484-414">La composición del gráfico circular cambia en función de estas selecciones.</span><span class="sxs-lookup"><span data-stu-id="13484-414">The composition of the pie chart changes based on these selections.</span></span>

<span data-ttu-id="13484-415">Cuando desplaza el puntero sobre una cuña del gráfico circular, puede ver un recuento de los mensajes enviados o recibidos.</span><span class="sxs-lookup"><span data-stu-id="13484-415">When you hover over a wedge in the pie chart, you can see a count of messages sent or received.</span></span>

<span data-ttu-id="13484-416">Si hace clic en **filtros** en una vista de informe, puede especificar un intervalo de fechas con **fecha de inicio** y fecha de **finalización**.</span><span class="sxs-lookup"><span data-stu-id="13484-416">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

![Gráfico circular en la vista de informe en el informe de remitentes y destinatarios principales](../../media/top-senders-and-recipients-report-view.png)

### <a name="details-table-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="13484-418">Vista de tabla de detalles para el informe de remitentes y destinatarios principales</span><span class="sxs-lookup"><span data-stu-id="13484-418">Details table view for the Top senders and recipient report</span></span>

<span data-ttu-id="13484-419">Si hace clic en **ver tabla de detalles**, la información que se muestra depende del gráfico que estaba viendo:</span><span class="sxs-lookup"><span data-stu-id="13484-419">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="13484-420">**Mostrar datos para los \> remitentes de correo principales**</span><span class="sxs-lookup"><span data-stu-id="13484-420">**Show data for \> Top mail senders**</span></span>

  - <span data-ttu-id="13484-421">**Principales remitentes de correo**</span><span class="sxs-lookup"><span data-stu-id="13484-421">**Top mail senders**</span></span>
  - <span data-ttu-id="13484-422">**Count**</span><span class="sxs-lookup"><span data-stu-id="13484-422">**Count**</span></span>

- <span data-ttu-id="13484-423">**Mostrar datos para los \> principales destinatarios de correo**</span><span class="sxs-lookup"><span data-stu-id="13484-423">**Show data for \> Top mail recipients**</span></span>

  - <span data-ttu-id="13484-424">**Destinatarios principales de correo**</span><span class="sxs-lookup"><span data-stu-id="13484-424">**Top mail recipients**</span></span>
  - <span data-ttu-id="13484-425">**Count**</span><span class="sxs-lookup"><span data-stu-id="13484-425">**Count**</span></span>

- <span data-ttu-id="13484-426">**Mostrar datos para los \> principales destinatarios de correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="13484-426">**Show data for \> Top spam recipients**</span></span>

  - <span data-ttu-id="13484-427">**Principales destinatarios de correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="13484-427">**Top spam recipients**</span></span>
  - <span data-ttu-id="13484-428">**Count**</span><span class="sxs-lookup"><span data-stu-id="13484-428">**Count**</span></span>

- <span data-ttu-id="13484-429">**Mostrar datos para \> Destinatarios principales de malware** (EOP)</span><span class="sxs-lookup"><span data-stu-id="13484-429">**Show data for \> Top malware recipients** (EOP)</span></span>

  - <span data-ttu-id="13484-430">**Destinatarios principales de malware**</span><span class="sxs-lookup"><span data-stu-id="13484-430">**Top malware recipients**</span></span>
  - <span data-ttu-id="13484-431">**Count**</span><span class="sxs-lookup"><span data-stu-id="13484-431">**Count**</span></span>

- <span data-ttu-id="13484-432">**Mostrar datos para \> Principales destinatarios de malware (ATP)** (Office 365 ATP)</span><span class="sxs-lookup"><span data-stu-id="13484-432">**Show data for \> Top malware recipients (ATP)** (Office 365 ATP)</span></span>

  - <span data-ttu-id="13484-433">**Destinatarios principales de malware (ATP)**</span><span class="sxs-lookup"><span data-stu-id="13484-433">**Top malware recipients (ATP)**</span></span>
  - <span data-ttu-id="13484-434">**Count**</span><span class="sxs-lookup"><span data-stu-id="13484-434">**Count**</span></span>

<span data-ttu-id="13484-435">Si hace clic en **filtros** en una vista de tabla de detalles, puede especificar un intervalo de fechas con **fecha de inicio** y fecha de **finalización**.</span><span class="sxs-lookup"><span data-stu-id="13484-435">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="13484-436">Para volver a la vista de informe, haga clic en **Ver informe**.</span><span class="sxs-lookup"><span data-stu-id="13484-436">To go back to the report view, click **View report**.</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="13484-437">¿Qué permisos se necesitan para ver estos informes?</span><span class="sxs-lookup"><span data-stu-id="13484-437">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="13484-438">Para ver y usar los informes, debe ser miembro del grupo de roles especificado en el centro de seguridad & cumplimiento **y** en Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="13484-438">To view and use the reports, you need to be a member of the specified role group in the Security & Compliance Center **and** in Exchange Online.</span></span>

- <span data-ttu-id="13484-439">En el centro de seguridad & cumplimiento, debe ser miembro de uno de los siguientes grupos de roles:</span><span class="sxs-lookup"><span data-stu-id="13484-439">In the Security & Compliance Center, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="13484-440">-Organization Management-administrador de seguridad (también puede hacerlo en el [centro de administración de Azure Active Directory](https://aad.portal.azure.com) -lector de seguridad</span><span class="sxs-lookup"><span data-stu-id="13484-440">-Organization Management -Security Administrator (you can also do this in the [Azure Active Directory admin center](https://aad.portal.azure.com) -Security Reader</span></span>

  <span data-ttu-id="13484-441">Para obtener más información, vea [Permisos en el Centro de seguridad y cumplimiento](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span><span class="sxs-lookup"><span data-stu-id="13484-441">For more information, see [Permissions in the Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span></span>

- <span data-ttu-id="13484-442">En Exchange Online, debe ser miembro de uno de los siguientes grupos de roles:</span><span class="sxs-lookup"><span data-stu-id="13484-442">In Exchange Online, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="13484-443">-Administración de la organización: administración de la organización de solo vista-destinatarios de solo vista-administración de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="13484-443">-Organization Management -View-only Organization Management -View-Only Recipients -Compliance Management</span></span>

<span data-ttu-id="13484-444">Para obtener más información, consulte [Permissions in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) y [Manage role Groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span><span class="sxs-lookup"><span data-stu-id="13484-444">For more information, see [Permissions in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) and [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

## <a name="related-topics"></a><span data-ttu-id="13484-445">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="13484-445">Related topics</span></span>

[<span data-ttu-id="13484-446">Informes inteligentes y reportes en el Centro de seguridad y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="13484-446">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="13484-447">Reportes de flujo de Correo en el Centro de seguridad y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="13484-447">Mail flow insights in the Security & Compliance Center</span></span>](mail-flow-insights-v2.md)

[<span data-ttu-id="13484-448">Ver informes de seguridad de correo electrónico en el Centro de seguridad y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="13484-448">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)

[<span data-ttu-id="13484-449">Ver informes para la protección contra amenazas avanzada de Office 365</span><span class="sxs-lookup"><span data-stu-id="13484-449">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)
