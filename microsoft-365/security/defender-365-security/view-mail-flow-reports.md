---
title: Ver informes de flujo de correo en el panel Informes
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Los administradores pueden obtener información sobre los informes de flujo de correo que están disponibles en el panel Informes del Centro de seguridad & cumplimiento.
ms.custom: ''
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 13871908c3b09660906b9233d23495830cf31ba9
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51070976"
---
# <a name="view-mail-flow-reports-in-the-reports-dashboard-in-security--compliance-center"></a><span data-ttu-id="293bb-103">Ver informes de flujo de correo en el panel Informes del Centro de & cumplimiento</span><span class="sxs-lookup"><span data-stu-id="293bb-103">View mail flow reports in the Reports dashboard in Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="293bb-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="293bb-104">**Applies to**</span></span>
- [<span data-ttu-id="293bb-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="293bb-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="293bb-106">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="293bb-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="293bb-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="293bb-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="293bb-108">Además de los informes de flujo [](mail-flow-insights-v2.md) de correo que están disponibles en el panel flujo de correo en el Centro de seguridad y cumplimiento de &, hay una variedad de informes de flujo de correo adicionales disponibles en el panel informes para ayudarle a supervisar su organización de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="293bb-108">In addition to the mail flow reports that are available in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center, a variety of additional mail flow reports are available in the Reports dashboard to help you monitor your Microsoft 365 organization.</span></span>

<span data-ttu-id="293bb-109">Si tiene los permisos [necesarios,](#what-permissions-are-needed-to-view-these-reports)puede ver estos informes en el Centro de seguridad [& cumplimiento](https://protection.office.com) yendo al **Panel de** \> **informes**.</span><span class="sxs-lookup"><span data-stu-id="293bb-109">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the [Security & Compliance Center](https://protection.office.com) by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="293bb-110">Para ir directamente al panel Informes, abra <https://protection.office.com/insightdashboard> .</span><span class="sxs-lookup"><span data-stu-id="293bb-110">To go directly to the Reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![Panel de informes en el Centro de seguridad & cumplimiento](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="connector-report"></a><span data-ttu-id="293bb-112">Informe del conector</span><span class="sxs-lookup"><span data-stu-id="293bb-112">Connector report</span></span>

<span data-ttu-id="293bb-113">El **informe connector muestra** la actividad de flujo de correo en los conectores entrantes y [salientes configurados](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) para la organización.</span><span class="sxs-lookup"><span data-stu-id="293bb-113">The **Connector report** shows mail flow activity on the [inbound and outbound connectors](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) that are configured for your organization.</span></span>

<span data-ttu-id="293bb-114">Para ver el informe, abra el Centro de  [seguridad & cumplimiento,](https://protection.office.com)vaya al Panel \> **de informes** y seleccione **Informe de conector**.</span><span class="sxs-lookup"><span data-stu-id="293bb-114">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Connector report**.</span></span> <span data-ttu-id="293bb-115">Para ir directamente al informe, abra <https://protection.office.com/reportv2?id=ConnectorReport> .</span><span class="sxs-lookup"><span data-stu-id="293bb-115">To go directly to the report, open <https://protection.office.com/reportv2?id=ConnectorReport>.</span></span>

![Widget de informe de conector en el panel Informes](../../media/connector-report-widget.png)

### <a name="report-view-for-the-connector-report"></a><span data-ttu-id="293bb-117">Vista Informe para el informe de Connector</span><span class="sxs-lookup"><span data-stu-id="293bb-117">Report view for the Connector report</span></span>

<span data-ttu-id="293bb-118">Los siguientes gráficos están disponibles en la vista informe:</span><span class="sxs-lookup"><span data-stu-id="293bb-118">The following charts are available in report view:</span></span>

- <span data-ttu-id="293bb-119">**Ver datos por: Flujo de correo:** este gráfico muestra el número de mensajes entrantes y salientes organizados por:</span><span class="sxs-lookup"><span data-stu-id="293bb-119">**View data by: Mail flow**: This chart shows the number of inbound and outbound messages organized by:</span></span>

  - <span data-ttu-id="293bb-120">**Total**</span><span class="sxs-lookup"><span data-stu-id="293bb-120">**Total**</span></span>
  - <span data-ttu-id="293bb-121">**Desde Internet sin conector**</span><span class="sxs-lookup"><span data-stu-id="293bb-121">**From the internet without a connector**</span></span>
  - <span data-ttu-id="293bb-122">**A Internet sin conector**</span><span class="sxs-lookup"><span data-stu-id="293bb-122">**To the internet without a connector**</span></span>
  - <span data-ttu-id="293bb-123">Un conector específico que haya configurado.</span><span class="sxs-lookup"><span data-stu-id="293bb-123">A specific connector that you've configured.</span></span>

  <span data-ttu-id="293bb-124">Para aislar los datos del gráfico, use el control **Mostrar datos para** seleccionar una de estas opciones o Todo el flujo de **correo**.</span><span class="sxs-lookup"><span data-stu-id="293bb-124">To isolate the data in the chart, use the **Show data for** control to select one of these options or **All mail flow**.</span></span>

  ![Ver datos por flujo de correo en el informe de Connector](../../media/connector-report-view-data-by-mail-flow.png)

- <span data-ttu-id="293bb-126">**Ver datos por: uso de TLS:** este gráfico muestra el porcentaje de uso de la versión seguridad de la capa de transporte (TLS) para el flujo de correo.</span><span class="sxs-lookup"><span data-stu-id="293bb-126">**View data by: TLS usage**: This chart shows the percentage of Transport Layer Security (TLS) version usage for mail flow.</span></span>

  <span data-ttu-id="293bb-127">Para aislar los datos del gráfico, use el control **Mostrar datos** para seleccionar una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="293bb-127">To isolate the data in the chart, use the **Show data for** control to select one of the following options:</span></span>

  - <span data-ttu-id="293bb-128">**Todo el flujo de correo**</span><span class="sxs-lookup"><span data-stu-id="293bb-128">**All mail flow**</span></span>
  - <span data-ttu-id="293bb-129">**Desde Internet sin conector**</span><span class="sxs-lookup"><span data-stu-id="293bb-129">**From the internet without a connector**</span></span>
  - <span data-ttu-id="293bb-130">**A Internet sin conector**</span><span class="sxs-lookup"><span data-stu-id="293bb-130">**To the internet without a connector**</span></span>
  - <span data-ttu-id="293bb-131">Un conector específico que haya configurado.</span><span class="sxs-lookup"><span data-stu-id="293bb-131">A specific connector that you've configured.</span></span>

  ![Ver datos por uso de TLS en el informe de Connector](../../media/connector-report-view-data-by-tls-usage.png)

<span data-ttu-id="293bb-133">Si hace clic **en Filtros** en una vista de informe, puede especificar un intervalo de fechas con Fecha **de inicio** y Fecha **de finalización.**</span><span class="sxs-lookup"><span data-stu-id="293bb-133">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-connector-report"></a><span data-ttu-id="293bb-134">Vista de tabla Detalles del informe de Connector</span><span class="sxs-lookup"><span data-stu-id="293bb-134">Details table view for the Connector report</span></span>

<span data-ttu-id="293bb-135">Si hace clic **en Ver tabla de detalles** en una vista de informe, se muestra la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="293bb-135">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="293bb-136">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="293bb-136">**Date**</span></span>
- <span data-ttu-id="293bb-137">**Dirección y nombre del conector**</span><span class="sxs-lookup"><span data-stu-id="293bb-137">**Connector direction and name**</span></span>
- <span data-ttu-id="293bb-138">**Tipo de conector**</span><span class="sxs-lookup"><span data-stu-id="293bb-138">**Connector type**</span></span>
- <span data-ttu-id="293bb-139">**¿TLS forzada?**: El valor **True** o **False**.</span><span class="sxs-lookup"><span data-stu-id="293bb-139">**Forced TLS?**: The value **True** or **False**.</span></span>
- <span data-ttu-id="293bb-140">**Sin TLS** (porcentaje)</span><span class="sxs-lookup"><span data-stu-id="293bb-140">**No TLS** (percentage)</span></span>
- <span data-ttu-id="293bb-141">**TLS 1.0** (porcentaje)</span><span class="sxs-lookup"><span data-stu-id="293bb-141">**TLS 1.0** (percentage)</span></span>
- <span data-ttu-id="293bb-142">**TLS 1.1** (porcentaje)</span><span class="sxs-lookup"><span data-stu-id="293bb-142">**TLS 1.1** (percentage)</span></span>
- <span data-ttu-id="293bb-143">**TLS 1.2** (porcentaje)</span><span class="sxs-lookup"><span data-stu-id="293bb-143">**TLS 1.2** (percentage)</span></span>
- <span data-ttu-id="293bb-144">**Volumen:** el número de mensajes.</span><span class="sxs-lookup"><span data-stu-id="293bb-144">**Volume**: The number of messages.</span></span>

<span data-ttu-id="293bb-145">Si hace clic **en Filtros en** una vista de tabla de detalles, puede especificar un intervalo de fechas con Fecha de **inicio** y Fecha **de finalización.**</span><span class="sxs-lookup"><span data-stu-id="293bb-145">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="293bb-146">Para volver a la vista informe, haga clic **en Ver informe**.</span><span class="sxs-lookup"><span data-stu-id="293bb-146">To go back to the report view, click **View report**.</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="293bb-147">Informe de reglas de transporte de Exchange</span><span class="sxs-lookup"><span data-stu-id="293bb-147">Exchange transport rule report</span></span>

<span data-ttu-id="293bb-148">El **informe de reglas de transporte de Exchange** muestra el efecto de las reglas de flujo de correo (también conocidas como reglas de transporte) en los mensajes entrantes y salientes de la organización.</span><span class="sxs-lookup"><span data-stu-id="293bb-148">The **Exchange transport rule report** shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="293bb-149">Para ver el informe, abra el Centro de  [seguridad & cumplimiento,](https://protection.office.com)vaya al Panel de informes y seleccione Regla de transporte \>  de **Exchange**.</span><span class="sxs-lookup"><span data-stu-id="293bb-149">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Exchange Transport rule**.</span></span> <span data-ttu-id="293bb-150">Para ir directamente al informe, abra <https://protection.office.com/reportv2?id=ETRRuleReport> .</span><span class="sxs-lookup"><span data-stu-id="293bb-150">To go directly to the report, open <https://protection.office.com/reportv2?id=ETRRuleReport>.</span></span>

![Widget de regla de transporte de Exchange en el panel Informes](../../media/transport-rule-report-widget.png)

### <a name="report-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="293bb-152">Vista Informe para el informe de reglas de transporte de Exchange</span><span class="sxs-lookup"><span data-stu-id="293bb-152">Report view for the Exchange transport rule report</span></span>

<span data-ttu-id="293bb-153">Los siguientes gráficos están disponibles en la vista informe:</span><span class="sxs-lookup"><span data-stu-id="293bb-153">The following charts are available in report view:</span></span>

- <span data-ttu-id="293bb-154">**Ver datos por: reglas de transporte de** \> Exchange **Dividir por: Dirección:** este gráfico  muestra  el número de mensajes entrantes y salientes que se vieron afectados por las reglas de transporte.</span><span class="sxs-lookup"><span data-stu-id="293bb-154">**View data by: Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by transport rules.</span></span>

- <span data-ttu-id="293bb-155">**Ver datos por: reglas de transporte de** \> Exchange **Dividir por: Gravedad:** este gráfico muestra  el número de mensajes de gravedad alta y media y **de gravedad** baja.</span><span class="sxs-lookup"><span data-stu-id="293bb-155">**View data by: Exchange transport rules** \> **Break down by: Severity**: This chart shows the number of **High severity** and **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="293bb-156">El nivel de gravedad se establece como una acción en la regla (**Auditar** esta regla con el nivel de gravedad o _SetAuditSeverity_).</span><span class="sxs-lookup"><span data-stu-id="293bb-156">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="293bb-157">Para obtener más información, vea [Acciones de regla de flujo de correo en Exchange Online](//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span><span class="sxs-lookup"><span data-stu-id="293bb-157">For more information, see [Mail flow rule actions in Exchange Online](//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="293bb-158">**Ver datos por: reglas de transporte** \> de DLP Exchange **Dividir por: Dirección:** este gráfico  muestra  el número de mensajes entrantes y salientes que se vieron afectados por las reglas de transporte de prevención de pérdida de datos (DLP).</span><span class="sxs-lookup"><span data-stu-id="293bb-158">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) transport rules.</span></span> <span data-ttu-id="293bb-159">Puede refinar aún más el gráfico seleccionando una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="293bb-159">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="293bb-160">**Mostrar datos para: todas las reglas de transporte DLP**</span><span class="sxs-lookup"><span data-stu-id="293bb-160">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="293bb-161">**Mostrar datos para: usuarios en peligro**</span><span class="sxs-lookup"><span data-stu-id="293bb-161">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="293bb-162">**Mostrar datos para: Bajo volumen de contenido detectado por la Ley Patriota de EE.UU.**</span><span class="sxs-lookup"><span data-stu-id="293bb-162">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

- <span data-ttu-id="293bb-163">**Ver datos por: reglas de transporte** \> de DLP Exchange **Dividir por: Dirección:** esta vista muestra el número de mensajes  de gravedad alta y media y de gravedad baja que se vieron afectados por las reglas de transporte DLP. </span><span class="sxs-lookup"><span data-stu-id="293bb-163">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This view shows the number of **High severity** and **Medium severity**, and **Low severity** messages that were affected by DLP transport rules.</span></span> <span data-ttu-id="293bb-164">Puede refinar aún más el gráfico seleccionando una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="293bb-164">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="293bb-165">**Mostrar datos para: todas las reglas de transporte DLP**</span><span class="sxs-lookup"><span data-stu-id="293bb-165">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="293bb-166">**Mostrar datos para: usuarios en peligro**</span><span class="sxs-lookup"><span data-stu-id="293bb-166">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="293bb-167">**Mostrar datos para: Bajo volumen de contenido detectado por la Ley Patriota de EE.UU.**</span><span class="sxs-lookup"><span data-stu-id="293bb-167">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

<span data-ttu-id="293bb-168">Si hace clic **en Filtros** en una vista de informe, puede modificar los resultados con los siguientes filtros::</span><span class="sxs-lookup"><span data-stu-id="293bb-168">If you click **Filters** in a report view, you can modify the results with the following filters::</span></span>

- <span data-ttu-id="293bb-169">**Fecha de inicio** y **fecha de finalización**</span><span class="sxs-lookup"><span data-stu-id="293bb-169">**Start date** and **End date**</span></span>
- <span data-ttu-id="293bb-170">Valores de dirección</span><span class="sxs-lookup"><span data-stu-id="293bb-170">Direction values</span></span>
- <span data-ttu-id="293bb-171">Valores de gravedad</span><span class="sxs-lookup"><span data-stu-id="293bb-171">Severity values</span></span>

![Vista Informe en el informe de reglas de transporte de Exchange](../../media/transport-rule-report-report-view.png)

### <a name="details-table-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="293bb-173">Vista de tabla de detalles para el informe de reglas de transporte de Exchange</span><span class="sxs-lookup"><span data-stu-id="293bb-173">Details table view for the Exchange transport rule report</span></span>

<span data-ttu-id="293bb-174">Si hace clic **en Ver tabla de detalles,** la información que se muestra depende del gráfico que estaba mirando:</span><span class="sxs-lookup"><span data-stu-id="293bb-174">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="293bb-175">**Ver datos por: Reglas de transporte de Exchange:**</span><span class="sxs-lookup"><span data-stu-id="293bb-175">**View data by: Exchange Transport rules**:</span></span>

  - <span data-ttu-id="293bb-176">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="293bb-176">**Date**</span></span>
  - <span data-ttu-id="293bb-177">**Regla de transporte**</span><span class="sxs-lookup"><span data-stu-id="293bb-177">**Transport rule**</span></span>
  - <span data-ttu-id="293bb-178">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="293bb-178">**Subject**</span></span>
  - <span data-ttu-id="293bb-179">**Dirección del remitente**</span><span class="sxs-lookup"><span data-stu-id="293bb-179">**Sender address**</span></span>
  - <span data-ttu-id="293bb-180">**Dirección de destinatario**</span><span class="sxs-lookup"><span data-stu-id="293bb-180">**Recipient address**</span></span>
  - <span data-ttu-id="293bb-181">**Gravedad**</span><span class="sxs-lookup"><span data-stu-id="293bb-181">**Severity**</span></span>
  - <span data-ttu-id="293bb-182">**Dirección**</span><span class="sxs-lookup"><span data-stu-id="293bb-182">**Direction**</span></span>

- <span data-ttu-id="293bb-183">**Ver datos por: Reglas de transporte de Dlp Exchange**:</span><span class="sxs-lookup"><span data-stu-id="293bb-183">**View data by: DLP Exchange transport rules**:</span></span>

  - <span data-ttu-id="293bb-184">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="293bb-184">**Date**</span></span>
  - <span data-ttu-id="293bb-185">**Directiva DLP**</span><span class="sxs-lookup"><span data-stu-id="293bb-185">**DLP policy**</span></span>
  - <span data-ttu-id="293bb-186">**Regla de transporte**</span><span class="sxs-lookup"><span data-stu-id="293bb-186">**Transport rule**</span></span>
  - <span data-ttu-id="293bb-187">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="293bb-187">**Subject**</span></span>
  - <span data-ttu-id="293bb-188">**Dirección del remitente**</span><span class="sxs-lookup"><span data-stu-id="293bb-188">**Sender address**</span></span>
  - <span data-ttu-id="293bb-189">**Dirección de destinatario**</span><span class="sxs-lookup"><span data-stu-id="293bb-189">**Recipient address**</span></span>
  - <span data-ttu-id="293bb-190">**Gravedad**</span><span class="sxs-lookup"><span data-stu-id="293bb-190">**Severity**</span></span>
  - <span data-ttu-id="293bb-191">**Dirección**</span><span class="sxs-lookup"><span data-stu-id="293bb-191">**Direction**</span></span>

<span data-ttu-id="293bb-192">Si hace clic **en Filtros en** una vista de tabla de detalles, puede modificar los resultados con los filtros siguientes:</span><span class="sxs-lookup"><span data-stu-id="293bb-192">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="293bb-193">**Fecha de inicio** y **fecha de finalización**</span><span class="sxs-lookup"><span data-stu-id="293bb-193">**Start date** and **End date**</span></span>
- <span data-ttu-id="293bb-194">Valores de dirección</span><span class="sxs-lookup"><span data-stu-id="293bb-194">Direction values</span></span>
- <span data-ttu-id="293bb-195">Valores de gravedad</span><span class="sxs-lookup"><span data-stu-id="293bb-195">Severity values</span></span>

<span data-ttu-id="293bb-196">Para volver a la vista informe, haga clic **en Ver informe**.</span><span class="sxs-lookup"><span data-stu-id="293bb-196">To go back to the report view, click **View report**.</span></span>

## <a name="forwarding-report"></a><span data-ttu-id="293bb-197">Informe de reenvío</span><span class="sxs-lookup"><span data-stu-id="293bb-197">Forwarding report</span></span>

<span data-ttu-id="293bb-198">El **informe de reenvío** muestra los mensajes reenviados automáticamente de la organización a dominios externos desde buzones de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="293bb-198">The **Forwarding report** shows your organization's automatically forwarded messages to external domains from Exchange Online mailboxes.</span></span> <span data-ttu-id="293bb-199">Los mensajes reenviados pueden suponer un riesgo de seguridad o cumplimiento, e indicar una cuenta comprometida.</span><span class="sxs-lookup"><span data-stu-id="293bb-199">Forwarded messages can pose a security or compliance risk, and might indicate a compromised account.</span></span>

<span data-ttu-id="293bb-200">Para ver el informe, abra el Centro de  [seguridad & cumplimiento,](https://protection.office.com)vaya al Panel de informes y seleccione \>  **Reenviar informe**.</span><span class="sxs-lookup"><span data-stu-id="293bb-200">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Forwarding report**.</span></span> <span data-ttu-id="293bb-201">Para ir directamente al informe, abra <https://protection.office.com/reportv2?id=MailFlowForwarding> .</span><span class="sxs-lookup"><span data-stu-id="293bb-201">To go directly to the report, open <https://protection.office.com/reportv2?id=MailFlowForwarding>.</span></span>

![Widget de informe de reenvío en el panel Informes](../../media/forwarding-report-widget.png)

### <a name="report-view-for-the-forwarding-report"></a><span data-ttu-id="293bb-203">Vista Informe para el informe de reenvío</span><span class="sxs-lookup"><span data-stu-id="293bb-203">Report view for the Forwarding report</span></span>

<span data-ttu-id="293bb-204">Los gráficos siguientes están disponibles en la vista informe:</span><span class="sxs-lookup"><span data-stu-id="293bb-204">The following charts are available in the report view:</span></span>

- <span data-ttu-id="293bb-205">**Mostrar datos para: Métodos de reenvío:** se muestran los siguientes métodos:</span><span class="sxs-lookup"><span data-stu-id="293bb-205">**Show data for: Forwarding methods**: The following methods are shown:</span></span>

  - <span data-ttu-id="293bb-206">**Regla de transporte:** también conocida como reglas [de flujo de correo](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span><span class="sxs-lookup"><span data-stu-id="293bb-206">**Transport rule**: Also known as [mail flow rules](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span></span>
  - <span data-ttu-id="293bb-207">**Regla de buzón:** también conocida como [reglas de bandeja de entrada](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).</span><span class="sxs-lookup"><span data-stu-id="293bb-207">**Mailbox rule**: Also known as [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).</span></span>

  ![Vista De métodos de reenvío en el informe de reenvío](../../media/forwarding-report-forwarding-methods.png)

- <span data-ttu-id="293bb-209">**Mostrar datos para: Dominios de reenvío:** esta vista muestra los dominios de destinatario que son los destinos para el reenvío.</span><span class="sxs-lookup"><span data-stu-id="293bb-209">**Show data for: Forwarding domains**: This view shows the recipient domains that are the destinations for forwarding.</span></span>

  ![Vista De dominios de reenvío en el informe de reenvío](../../media/forwarding-report-forwarding-domains.png)

- <span data-ttu-id="293bb-211">**Mostrar datos para: Reenviadores:** se muestran los siguientes reenviadores:</span><span class="sxs-lookup"><span data-stu-id="293bb-211">**Show data for: Forwarders**: The following forwarders are shown:</span></span>

  - <span data-ttu-id="293bb-212">**Regla de transporte**</span><span class="sxs-lookup"><span data-stu-id="293bb-212">**Transport rule**</span></span>
  - <span data-ttu-id="293bb-213">El buzón que contiene la regla de la Bandeja de entrada de reenvío.</span><span class="sxs-lookup"><span data-stu-id="293bb-213">The mailbox that contains the forwarding Inbox rule.</span></span>

  ![Vista Reenviadores en el informe de reenvío](../../media/forwarding-report-forwarders.png)

<span data-ttu-id="293bb-215">Si hace clic **en Filtros** en una vista de informe, puede especificar un intervalo de fechas con Fecha **de inicio** y Fecha **de finalización.**</span><span class="sxs-lookup"><span data-stu-id="293bb-215">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-report"></a><span data-ttu-id="293bb-216">Vista de tabla Detalles del informe de reenvío</span><span class="sxs-lookup"><span data-stu-id="293bb-216">Details table view for the Forwarding report</span></span>

<span data-ttu-id="293bb-217">Si hace clic **en Ver tabla de detalles** en una vista de informe, se muestra la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="293bb-217">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="293bb-218">**Reenviadores:** la regla **de transporte** de valor o el buzón que contiene la regla de la Bandeja de entrada de reenvío.</span><span class="sxs-lookup"><span data-stu-id="293bb-218">**Forwarders**: The value **Transport rule** or the mailbox that contains the forwarding Inbox rule.</span></span>
- <span data-ttu-id="293bb-219">**Tipo de reenvío:** la regla **de buzón de correo** de valor o la regla de **transporte**.</span><span class="sxs-lookup"><span data-stu-id="293bb-219">**Forwarding type**: The value **Mailbox rule** or **Transport rule**.</span></span>
- <span data-ttu-id="293bb-220">**Nombre de destinatario**</span><span class="sxs-lookup"><span data-stu-id="293bb-220">**Recipient name**</span></span>
- <span data-ttu-id="293bb-221">**Dominio del destinatario**</span><span class="sxs-lookup"><span data-stu-id="293bb-221">**Recipient domain**</span></span>
- <span data-ttu-id="293bb-222">**Detalles:** este es el valor GUID de la regla de flujo de correo o el valor RuleIdentity de la regla Bandeja de entrada.</span><span class="sxs-lookup"><span data-stu-id="293bb-222">**Details**: This is the GUID value of the mail flow rule, or the RuleIdentity value of the Inbox rule.</span></span>
- <span data-ttu-id="293bb-223">**Count**</span><span class="sxs-lookup"><span data-stu-id="293bb-223">**Count**</span></span>
- <span data-ttu-id="293bb-224">**Primera fecha de reenvío**</span><span class="sxs-lookup"><span data-stu-id="293bb-224">**First forward date**</span></span>

<span data-ttu-id="293bb-225">Si hace clic **en Filtros en** una vista de tabla de detalles, puede especificar un intervalo de fechas con Fecha de **inicio** y Fecha **de finalización.**</span><span class="sxs-lookup"><span data-stu-id="293bb-225">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="293bb-226">Para volver a la vista informes, haga clic **en Ver informe**.</span><span class="sxs-lookup"><span data-stu-id="293bb-226">To go back to the reports view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="293bb-227">Informe de estado de flujo de correo</span><span class="sxs-lookup"><span data-stu-id="293bb-227">Mailflow status report</span></span>

<span data-ttu-id="293bb-228">El **informe de estado de flujo** de correo es similar al informe de correo electrónico enviado y recibido, con información adicional sobre el correo electrónico permitido o bloqueado en el perímetro. [](#sent-and-received-email-report)</span><span class="sxs-lookup"><span data-stu-id="293bb-228">The **Mailflow status report** is similar to the [Sent and received email report](#sent-and-received-email-report), with additional information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="293bb-229">Este es el único informe que contiene información de protección perimetral y muestra cuánto correo electrónico se bloquea antes de que exchange Online Protection (EOP) pueda evaluarlo.</span><span class="sxs-lookup"><span data-stu-id="293bb-229">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="293bb-230">Es importante comprender que si un mensaje se envía a cinco destinatarios, lo contamos como cinco mensajes diferentes y no un mensaje.</span><span class="sxs-lookup"><span data-stu-id="293bb-230">It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>
<span data-ttu-id="293bb-231">Para ver el informe, abra el Centro de  [seguridad & cumplimiento,](https://protection.office.com)vaya al Panel de informes y seleccione Informe de estado de flujo \>  **de correo**.</span><span class="sxs-lookup"><span data-stu-id="293bb-231">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Mailflow status report**.</span></span> <span data-ttu-id="293bb-232">Para ir directamente al informe **de estado de flujo de correo**, abra <https://protection.office.com/mailflowStatusReport> .</span><span class="sxs-lookup"><span data-stu-id="293bb-232">To go directly to the **Mail flow status report**, open <https://protection.office.com/mailflowStatusReport>.</span></span>

![Widget de informe de estado de flujo de correo en el panel Informes](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="293bb-234">Vista de tipo para el informe de estado de flujo de correo</span><span class="sxs-lookup"><span data-stu-id="293bb-234">Type view for the Mailflow status report</span></span>

<span data-ttu-id="293bb-235">Al abrir el informe, la **pestaña Tipo** está seleccionada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="293bb-235">When you open the report, the **Type** tab is selected by default.</span></span> <span data-ttu-id="293bb-236">De forma predeterminada, esta vista contiene un gráfico y una tabla de datos configurada con los filtros siguientes:</span><span class="sxs-lookup"><span data-stu-id="293bb-236">By default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="293bb-237">**Fecha:** los últimos 7 días.</span><span class="sxs-lookup"><span data-stu-id="293bb-237">**Date**: The last 7 days.</span></span>
- <span data-ttu-id="293bb-238">**Dirección**:</span><span class="sxs-lookup"><span data-stu-id="293bb-238">**Direction**:</span></span>

  - <span data-ttu-id="293bb-239">**Entrada**</span><span class="sxs-lookup"><span data-stu-id="293bb-239">**Inbound**</span></span>
  - <span data-ttu-id="293bb-240">**Saliente**</span><span class="sxs-lookup"><span data-stu-id="293bb-240">**Outbound**</span></span>
  - <span data-ttu-id="293bb-241">**Intra-org:** este recuento es para mensajes dentro de un espacio empresarial, es decir,</span><span class="sxs-lookup"><span data-stu-id="293bb-241">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="293bb-242">sender abc@domain.com al destinatario xyz@domain.com (se cuenta por separado de **Entrante** y **Saliente**)</span><span class="sxs-lookup"><span data-stu-id="293bb-242">sender abc@domain.com sends to recipient xyz@domain.com  (counted separately from **Inbound** and **Outbound**)</span></span>

- <span data-ttu-id="293bb-243">**Tipo**:</span><span class="sxs-lookup"><span data-stu-id="293bb-243">**Type**:</span></span>

  - <span data-ttu-id="293bb-244">**Correo bueno**</span><span class="sxs-lookup"><span data-stu-id="293bb-244">**Good mail**</span></span>
  - <span data-ttu-id="293bb-245">**Malware**</span><span class="sxs-lookup"><span data-stu-id="293bb-245">**Malware**</span></span>
  - <span data-ttu-id="293bb-246">**Correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="293bb-246">**Spam**</span></span>
  - <span data-ttu-id="293bb-247">**Protección perimetral**</span><span class="sxs-lookup"><span data-stu-id="293bb-247">**Edge protection**</span></span>
  - <span data-ttu-id="293bb-248">**Mensajes de regla**</span><span class="sxs-lookup"><span data-stu-id="293bb-248">**Rule messages**</span></span>
  - <span data-ttu-id="293bb-249">**Correo de suplantación de identidad**</span><span class="sxs-lookup"><span data-stu-id="293bb-249">**Phishing email**</span></span>

<span data-ttu-id="293bb-250">El gráfico está organizado por los **valores Type.**</span><span class="sxs-lookup"><span data-stu-id="293bb-250">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="293bb-251">Puede cambiar estos filtros haciendo clic en **Filtrar** o haciendo clic en un valor de la leyenda del gráfico.</span><span class="sxs-lookup"><span data-stu-id="293bb-251">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span>

<span data-ttu-id="293bb-252">La tabla de datos contiene la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="293bb-252">The data table contains the following information:</span></span>

- <span data-ttu-id="293bb-253">**Dirección**</span><span class="sxs-lookup"><span data-stu-id="293bb-253">**Direction**</span></span>
- <span data-ttu-id="293bb-254">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="293bb-254">**Type**</span></span>
- <span data-ttu-id="293bb-255">**24 horas**</span><span class="sxs-lookup"><span data-stu-id="293bb-255">**24 hours**</span></span>
- <span data-ttu-id="293bb-256">**3 días**</span><span class="sxs-lookup"><span data-stu-id="293bb-256">**3 days**</span></span>
- <span data-ttu-id="293bb-257">**7 días**</span><span class="sxs-lookup"><span data-stu-id="293bb-257">**7 days**</span></span>
- <span data-ttu-id="293bb-258">**15 días**</span><span class="sxs-lookup"><span data-stu-id="293bb-258">**15 days**</span></span>
- <span data-ttu-id="293bb-259">**30 días**</span><span class="sxs-lookup"><span data-stu-id="293bb-259">**30 days**</span></span>

<span data-ttu-id="293bb-260">Si hace clic **en Elegir una categoría para obtener más información,** puede seleccionar entre los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="293bb-260">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="293bb-261">**Correo electrónico de suplantación** de identidad : esta selección le lleva al informe [de estado de protección contra amenazas](view-email-security-reports.md#threat-protection-status-report).</span><span class="sxs-lookup"><span data-stu-id="293bb-261">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="293bb-262">**Malware en el correo** electrónico: esta selección le lleva al informe [de estado de protección contra amenazas](view-email-security-reports.md#threat-protection-status-report).</span><span class="sxs-lookup"><span data-stu-id="293bb-262">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="293bb-263">**Detecciones de correo** no deseado: esta selección le lleva al informe [Detecciones de correo no deseado](view-email-security-reports.md#spam-detections-report).</span><span class="sxs-lookup"><span data-stu-id="293bb-263">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="293bb-264">**Correo no deseado bloqueado** perimetral: esta selección le lleva al informe [Detecciones de correo no deseado](view-email-security-reports.md#spam-detections-report).</span><span class="sxs-lookup"><span data-stu-id="293bb-264">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="293bb-265">**Exportar**:</span><span class="sxs-lookup"><span data-stu-id="293bb-265">**Export**:</span></span>

<span data-ttu-id="293bb-266">Para la vista de detalles, solo puede exportar datos durante un día.</span><span class="sxs-lookup"><span data-stu-id="293bb-266">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="293bb-267">Por lo tanto, si desea exportar datos durante 7 días, debe realizar 7 acciones de exportación diferentes.</span><span class="sxs-lookup"><span data-stu-id="293bb-267">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="293bb-268">Cada archivo .csv exportado está limitado a 150 000 filas.</span><span class="sxs-lookup"><span data-stu-id="293bb-268">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="293bb-269">Si los datos de ese día contienen más de 150 000 filas, se crearán varios archivos .csv.</span><span class="sxs-lookup"><span data-stu-id="293bb-269">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="293bb-270">Vista De tipo en el informe de estado de flujo de correo</span><span class="sxs-lookup"><span data-stu-id="293bb-270">Type view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="293bb-271">Vista Dirección del informe de estado de flujo de correo</span><span class="sxs-lookup"><span data-stu-id="293bb-271">Direction view for the Mailflow status report</span></span>

<span data-ttu-id="293bb-272">Si hace clic en la **pestaña Dirección,** se usan los mismos filtros predeterminados de la **vista** Tipo.</span><span class="sxs-lookup"><span data-stu-id="293bb-272">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="293bb-273">El gráfico está organizado por valores **direction.**</span><span class="sxs-lookup"><span data-stu-id="293bb-273">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="293bb-274">Puede cambiar estos filtros haciendo clic en **Filtrar** o haciendo clic en un valor de la leyenda del gráfico.</span><span class="sxs-lookup"><span data-stu-id="293bb-274">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span> <span data-ttu-id="293bb-275">Se usan los mismos filtros de **la vista** Tipo.</span><span class="sxs-lookup"><span data-stu-id="293bb-275">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="293bb-276">La tabla de datos contiene la misma información de la **vista** Tipo.</span><span class="sxs-lookup"><span data-stu-id="293bb-276">The data table contains same information from the **Type** view.</span></span>

<span data-ttu-id="293bb-277">La **categoría Elegir una categoría para obtener más detalles** sobre las selecciones y el comportamiento disponibles son los mismos que la **vista** Tipo.</span><span class="sxs-lookup"><span data-stu-id="293bb-277">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

<span data-ttu-id="293bb-278">**Exportar**:</span><span class="sxs-lookup"><span data-stu-id="293bb-278">**Export**:</span></span>

<span data-ttu-id="293bb-279">Para la vista de detalles, solo puede exportar datos durante un día.</span><span class="sxs-lookup"><span data-stu-id="293bb-279">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="293bb-280">Por lo tanto, si desea exportar datos durante 7 días, debe realizar 7 acciones de exportación diferentes.</span><span class="sxs-lookup"><span data-stu-id="293bb-280">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="293bb-281">Cada archivo .csv exportado está limitado a 150 000 filas.</span><span class="sxs-lookup"><span data-stu-id="293bb-281">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="293bb-282">Si los datos de ese día contienen más de 150 000 filas, se crearán varios archivos .csv.</span><span class="sxs-lookup"><span data-stu-id="293bb-282">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="293bb-283">Vista Dirección en el informe de estado de flujo de correo</span><span class="sxs-lookup"><span data-stu-id="293bb-283">Direction view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-direction-view.png)

### <a name="funnel-view-for-the-mailflow-status-report"></a><span data-ttu-id="293bb-284">Vista embudo para el informe de estado de flujo de correo</span><span class="sxs-lookup"><span data-stu-id="293bb-284">Funnel view for the Mailflow status report</span></span>

<span data-ttu-id="293bb-285">La **vista Embudo** muestra cómo las características de protección contra amenazas de correo electrónico de Microsoft filtran el correo electrónico entrante y saliente en su organización.</span><span class="sxs-lookup"><span data-stu-id="293bb-285">The **Funnel** view shows you how Microsoft's email threat protection features filter incoming and outgoing email in your organization.</span></span> <span data-ttu-id="293bb-286">Proporciona detalles sobre el recuento total de correo electrónico y cómo afectan a este recuento las características de protección contra amenazas configuradas, como la protección perimetral, el antimalware, la suplantación de identidad (phishing), el correo no deseado y la suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="293bb-286">It provides details on the total email count, and how the configured threat protection features, including edge protection, anti-malware, anti-phishing, anti-spam, and anti-spoofing affect this count.</span></span>

<span data-ttu-id="293bb-287">Si hace clic en la **pestaña Embudo,** de forma predeterminada, esta vista contiene un gráfico y una tabla de datos configurada con los filtros siguientes:</span><span class="sxs-lookup"><span data-stu-id="293bb-287">If you click the **Funnel** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="293bb-288">**Fecha:** los últimos 7 días.</span><span class="sxs-lookup"><span data-stu-id="293bb-288">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="293bb-289">**Dirección**:</span><span class="sxs-lookup"><span data-stu-id="293bb-289">**Direction**:</span></span>

  - <span data-ttu-id="293bb-290">**Entrada**</span><span class="sxs-lookup"><span data-stu-id="293bb-290">**Inbound**</span></span>
  - <span data-ttu-id="293bb-291">**Saliente**</span><span class="sxs-lookup"><span data-stu-id="293bb-291">**Outbound**</span></span>
  - <span data-ttu-id="293bb-292">**Intra-org:** este recuento es para los mensajes enviados dentro de un espacio empresarial; Es decir, el remitente abc@domain.com al destinatario xyz@domain.com (se cuenta por separado de Entrante y Saliente).</span><span class="sxs-lookup"><span data-stu-id="293bb-292">**Intra-org**: This count is for messages sent within a tenant; i.e, sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound).</span></span>

<span data-ttu-id="293bb-293">La vista de agregado y la vista de tabla de datos permiten 90 días de filtrado.</span><span class="sxs-lookup"><span data-stu-id="293bb-293">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="293bb-294">Si hace clic **en Filtrar,** puede filtrar tanto el gráfico como la tabla de datos.</span><span class="sxs-lookup"><span data-stu-id="293bb-294">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="293bb-295">Este gráfico muestra el recuento de correo electrónico organizado por:</span><span class="sxs-lookup"><span data-stu-id="293bb-295">This chart shows the email count organized by:</span></span>

- <span data-ttu-id="293bb-296">**Correo electrónico total**</span><span class="sxs-lookup"><span data-stu-id="293bb-296">**Total email**</span></span>
- <span data-ttu-id="293bb-297">**Correo electrónico después de la protección perimetral**</span><span class="sxs-lookup"><span data-stu-id="293bb-297">**Email after edge protection**</span></span>
- <span data-ttu-id="293bb-298">**Correo electrónico después de antimalware, reputación de archivo, bloqueo de tipo de archivo**</span><span class="sxs-lookup"><span data-stu-id="293bb-298">**Email after anti-malware, file reputation, file type block**</span></span>
- <span data-ttu-id="293bb-299">**Correo electrónico después de anti phish, reputación url, suplantación de marca, anti suplantación de identidad**</span><span class="sxs-lookup"><span data-stu-id="293bb-299">**Email after anti-phish, URL reputation, brand impersonation, anti-spoof**</span></span>
- <span data-ttu-id="293bb-300">**Correo electrónico después de correo no deseado, filtrado masivo de correo**</span><span class="sxs-lookup"><span data-stu-id="293bb-300">**Email after anti-spam, bulk mail filtering**</span></span>
- <span data-ttu-id="293bb-301">**Correo electrónico después de la suplantación de usuario y dominio**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="293bb-301">**Email after user and domain impersonation**<sup>1</sup></span></span>
- <span data-ttu-id="293bb-302">**Email after file and URL detonation**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="293bb-302">**Email after file and URL detonation**<sup>1</sup></span></span>
- <span data-ttu-id="293bb-303">**Correo electrónico detectado como benigno después de la protección posterior a la entrega (url click time protection)**</span><span class="sxs-lookup"><span data-stu-id="293bb-303">**Email detected as benign after post-delivery protection (URL click time protection)**</span></span>

<span data-ttu-id="293bb-304"><sup>1</sup> Defender solo para Office 365</span><span class="sxs-lookup"><span data-stu-id="293bb-304"><sup>1</sup> Defender for Office 365 only</span></span>

<span data-ttu-id="293bb-305">Para ver el correo electrónico filtrado por EOP o Defender para Office 365 por separado, haga clic en el valor de la leyenda del gráfico.</span><span class="sxs-lookup"><span data-stu-id="293bb-305">To view the email filtered by EOP or Defender for Office 365 separately, click on the value in the chart legend.</span></span>

<span data-ttu-id="293bb-306">La tabla de datos contiene la siguiente información, que se muestra en orden de fecha descendente:</span><span class="sxs-lookup"><span data-stu-id="293bb-306">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="293bb-307">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="293bb-307">**Date**</span></span>
- <span data-ttu-id="293bb-308">**Correo electrónico total**</span><span class="sxs-lookup"><span data-stu-id="293bb-308">**Total email**</span></span>
- <span data-ttu-id="293bb-309">**Protección perimetral**</span><span class="sxs-lookup"><span data-stu-id="293bb-309">**Edge protection**</span></span>
- <span data-ttu-id="293bb-310">**Antimalware, reputación de archivo, bloque de tipo de archivo:**</span><span class="sxs-lookup"><span data-stu-id="293bb-310">**Anti-malware, file reputation, file type block**:</span></span>
  - <span data-ttu-id="293bb-311">**Reputación del archivo:** mensajes filtrados debido a la identificación de un archivo adjunto por otros clientes de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="293bb-311">**File reputation**: Messages filtered due to identification of an attached file by other Microsoft customers.</span></span>
  - <span data-ttu-id="293bb-312">**Bloque de tipo de** archivo: mensajes filtrados debido al tipo de archivo malintencionado identificado en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="293bb-312">**File type block**: Messages filtered due to the type of malicious file identified in the message.</span></span>
- <span data-ttu-id="293bb-313">**Anti-phish, reputación url, suplantación de marca, suplantación de identidad:**</span><span class="sxs-lookup"><span data-stu-id="293bb-313">**Anti-phish, URL reputation, Brand impersonation, anti-spoof**:</span></span>
  - <span data-ttu-id="293bb-314">**Reputación de la dirección URL:** mensajes filtrados debido a la identificación de la dirección URL por otros clientes de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="293bb-314">**URL reputation**: Messages filtered due to the identification of the URL by other Microsoft customers.</span></span>
  - <span data-ttu-id="293bb-315">**Suplantación de marca:** mensajes filtrados debido al mensaje procedente de remitentes de suplantación de marca conocidos.</span><span class="sxs-lookup"><span data-stu-id="293bb-315">**Brand impersonation**: Messages filtered due to the message coming from well-known brand impersonating senders.</span></span>
  - <span data-ttu-id="293bb-316">**Anti-spoof:** mensajes filtrados debido a que el mensaje intenta suplantar un dominio al que pertenece el destinatario o un dominio que el remitente del mensaje no posee.</span><span class="sxs-lookup"><span data-stu-id="293bb-316">**Anti-spoof**: Messages filtered due to the message attempting to spoof a domain that the recipient belongs to, or a domain that the message sender doesn't own.</span></span>
- <span data-ttu-id="293bb-317">**Antispam, filtrado masivo de correo:**</span><span class="sxs-lookup"><span data-stu-id="293bb-317">**Anti-spam, bulk mail filtering**:</span></span>
  - <span data-ttu-id="293bb-318">**Filtrado masivo de correo:** mensajes filtrados debido a un intento de entregar correo masivo a sus destinatarios.</span><span class="sxs-lookup"><span data-stu-id="293bb-318">**Bulk mail filtering**: Messages filtered due to an attempt to deliver bulk mail to its recipients.</span></span>
- <span data-ttu-id="293bb-319">**Suplantación de usuario y dominio (Defender para Office 365):**</span><span class="sxs-lookup"><span data-stu-id="293bb-319">**User and domain impersonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="293bb-320">Suplantación de **usuario:** mensajes filtrados debido a un intento de suplantar a un usuario (remitente de mensajes) que se define en la configuración de protección de suplantación de una directiva contra suplantación.</span><span class="sxs-lookup"><span data-stu-id="293bb-320">**User impersonation**: Messages filtered due to an attempt to impersonate a user (message sender) that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
  - <span data-ttu-id="293bb-321">**Suplantación** de dominio: mensajes filtrados debido a un intento de suplantar un dominio definido en la configuración de protección de suplantación de una directiva contra suplantación.</span><span class="sxs-lookup"><span data-stu-id="293bb-321">**Domain impersonation**: Messages filtered due to an attempt to impersonate a domain that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
- <span data-ttu-id="293bb-322">**Detonación de archivos y direcciones URL (Defender para Office 365):**</span><span class="sxs-lookup"><span data-stu-id="293bb-322">**File and URL detonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="293bb-323">**Detonación de archivos:** mensajes filtrados por una directiva de datos adjuntos seguros.</span><span class="sxs-lookup"><span data-stu-id="293bb-323">**File detonation**: Messages filtered by a Safe Attachments policy.</span></span>
  - <span data-ttu-id="293bb-324">**Detonación de dirección URL:** mensaje filtrado por una directiva de vínculos seguros.</span><span class="sxs-lookup"><span data-stu-id="293bb-324">**URL detonation**: Message filtered by a Safe Links policy.</span></span>
- <span data-ttu-id="293bb-325">**Protección posterior a la entrega y ZAP (ATP) o ZAP (EOP):** ZAP indica la purga automática de cero horas.</span><span class="sxs-lookup"><span data-stu-id="293bb-325">**Post-delivery protection and ZAP (ATP), or ZAP (EOP)**: ZAP indicates zero hour auto-purge.</span></span>

<span data-ttu-id="293bb-326">Si selecciona una fila en la tabla de datos, se muestra un desglose adicional de los recuentos de correo electrónico en el menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="293bb-326">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="293bb-327">**Exportar**:</span><span class="sxs-lookup"><span data-stu-id="293bb-327">**Export**:</span></span>

<span data-ttu-id="293bb-328">Después de hacer **clic en Exportar** en **Opciones,** puede seleccionar uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="293bb-328">After you click **Export** under **Options**, you can select one of the following values:</span></span>

- <span data-ttu-id="293bb-329">**Resumen (con datos de los últimos 90 días como máximo)**</span><span class="sxs-lookup"><span data-stu-id="293bb-329">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="293bb-330">**Detalles (con datos de los últimos 30 días como máximo)**</span><span class="sxs-lookup"><span data-stu-id="293bb-330">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="293bb-331">En **Fecha**, elija un rango y, a continuación, haga clic **en Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="293bb-331">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="293bb-332">Los datos de los filtros actuales se exportarán a un archivo .csv.</span><span class="sxs-lookup"><span data-stu-id="293bb-332">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="293bb-333">Cada archivo .csv exportado está limitado a 150 000 filas.</span><span class="sxs-lookup"><span data-stu-id="293bb-333">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="293bb-334">Si los datos contienen más de 150 000 filas, se crearán varios archivos .csv.</span><span class="sxs-lookup"><span data-stu-id="293bb-334">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![<span data-ttu-id="293bb-335">Vista embudo en el informe de estado de flujo de correo</span><span class="sxs-lookup"><span data-stu-id="293bb-335">Funnel view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-funnel-view.png)

### <a name="tech-view-for-the-mailflow-status-report"></a><span data-ttu-id="293bb-336">Vista técnica del informe de estado del flujo de correo</span><span class="sxs-lookup"><span data-stu-id="293bb-336">Tech view for the Mailflow status report</span></span>

<span data-ttu-id="293bb-337">La **vista Tech es** similar a la vista **Embudo,** lo que proporciona más detalles pormenorizados para las características de protección contra amenazas configuradas.</span><span class="sxs-lookup"><span data-stu-id="293bb-337">The **Tech view** is similar to the **Funnel** view, providing more granular details for the configured threat protections features.</span></span> <span data-ttu-id="293bb-338">En el gráfico, puede ver cómo se clasifican los mensajes en las distintas etapas de protección contra amenazas.</span><span class="sxs-lookup"><span data-stu-id="293bb-338">From the chart, you can see how messages are categorized at the different stages of threat protection.</span></span>

<span data-ttu-id="293bb-339">Si hace clic en la **pestaña Vista técnica,** de forma predeterminada, esta vista contiene un gráfico y una tabla de datos configurada con los filtros siguientes:</span><span class="sxs-lookup"><span data-stu-id="293bb-339">If you click the **Tech view** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="293bb-340">**Fecha:** los últimos 7 días.</span><span class="sxs-lookup"><span data-stu-id="293bb-340">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="293bb-341">**Dirección**:</span><span class="sxs-lookup"><span data-stu-id="293bb-341">**Direction**:</span></span>

  - <span data-ttu-id="293bb-342">**Entrada**</span><span class="sxs-lookup"><span data-stu-id="293bb-342">**Inbound**</span></span>
  - <span data-ttu-id="293bb-343">**Saliente**</span><span class="sxs-lookup"><span data-stu-id="293bb-343">**Outbound**</span></span>
  - <span data-ttu-id="293bb-344">**Intra-org:** este recuento es para mensajes dentro de un espacio empresarial, es decir,</span><span class="sxs-lookup"><span data-stu-id="293bb-344">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="293bb-345">remitente abc@domain.com al destinatario xyz@domain.com (se cuenta por separado de Entrante y Saliente)</span><span class="sxs-lookup"><span data-stu-id="293bb-345">sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound)</span></span>

<span data-ttu-id="293bb-346">La vista de agregado y la vista de tabla de datos permiten 90 días de filtrado.</span><span class="sxs-lookup"><span data-stu-id="293bb-346">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="293bb-347">Si hace clic **en Filtrar,** puede filtrar tanto el gráfico como la tabla de datos.</span><span class="sxs-lookup"><span data-stu-id="293bb-347">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="293bb-348">En este gráfico se muestran los mensajes organizados en las siguientes categorías:</span><span class="sxs-lookup"><span data-stu-id="293bb-348">This chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="293bb-349">**Correo electrónico total**</span><span class="sxs-lookup"><span data-stu-id="293bb-349">**Total email**</span></span>
- <span data-ttu-id="293bb-350">**Edge allow** y **Edge filtered**</span><span class="sxs-lookup"><span data-stu-id="293bb-350">**Edge allow** and **Edge filtered**</span></span>
- <span data-ttu-id="293bb-351">**No malware,** **detección de datos adjuntos seguros,** detección de motores <sup>\*</sup> **antimalware** y **mensajes de regla**</span><span class="sxs-lookup"><span data-stu-id="293bb-351">**Not malware**, **Safe Attachments detection**<sup>\*</sup>, **Anti-malware engine detection**, and **Rule messages**</span></span>
- <span data-ttu-id="293bb-352">**No phish**, **error DMARC,** **detección de suplantación,** detección **de suplantación** y detección **de suplantación** de identidad</span><span class="sxs-lookup"><span data-stu-id="293bb-352">**Not phish**, **DMARC failure**, **Impersonation detection**, **Spoof detection**, and **Phish detection**</span></span>
- <span data-ttu-id="293bb-353">**No hay detección con detonación de dirección URL** y **detonación de url**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="293bb-353">**No detection with URL detonation** and **URL detonation detection**<sup>\*</sup></span></span>
- <span data-ttu-id="293bb-354">**No correo no** deseado y  **correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="293bb-354">**Not spam** and  **Spam**</span></span>
- <span data-ttu-id="293bb-355">**Correo electrónico no malintencionado,** **detección de vínculos seguros** <sup>\*</sup> y **ZAP**</span><span class="sxs-lookup"><span data-stu-id="293bb-355">**Non-malicious email**, **Safe Links detection**<sup>\*</sup>, and **ZAP**</span></span>

<span data-ttu-id="293bb-356"><sup>\*</sup> Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="293bb-356"><sup>\*</sup> Defender for Office 365</span></span>

<span data-ttu-id="293bb-357">Al pasar el mouse sobre una categoría del gráfico, puede ver el número de mensajes de esa categoría.</span><span class="sxs-lookup"><span data-stu-id="293bb-357">When you hover over a category in the chart, you can see the number of messages in that category.</span></span>

<span data-ttu-id="293bb-358">La tabla de datos contiene la siguiente información, que se muestra en orden de fecha descendente:</span><span class="sxs-lookup"><span data-stu-id="293bb-358">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="293bb-359">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="293bb-359">**Date**</span></span>
- <span data-ttu-id="293bb-360">**Correo electrónico total**</span><span class="sxs-lookup"><span data-stu-id="293bb-360">**Total email**</span></span>
- <span data-ttu-id="293bb-361">**Perímetro filtrado**</span><span class="sxs-lookup"><span data-stu-id="293bb-361">**Edge filtered**</span></span>
- <span data-ttu-id="293bb-362">**Motor antimalware, Datos adjuntos seguros, regla filtrada:**</span><span class="sxs-lookup"><span data-stu-id="293bb-362">**Anti-malware engine, Safe Attachments, rule filtered**:</span></span>
  - <span data-ttu-id="293bb-363">**Regla filtrada:** mensajes filtrados debido a reglas de flujo de correo (también conocidas como reglas de transporte).</span><span class="sxs-lookup"><span data-stu-id="293bb-363">**Rule filtered**: Messages filtered due to  mail flow rules (also known as transport rules).</span></span>
- <span data-ttu-id="293bb-364">**DMARC, suplantación, suplantación, suplantación de identidad filtrada:**</span><span class="sxs-lookup"><span data-stu-id="293bb-364">**DMARC, impersonation, spoof, phish filtered**:</span></span>
  - <span data-ttu-id="293bb-365">**DMARC:** mensajes filtrados debido a que el mensaje no ha fallado en la comprobación de autenticación de DMARC.</span><span class="sxs-lookup"><span data-stu-id="293bb-365">**DMARC**: Messages filtered due to the message failing its DMARC authentication check.</span></span>
- <span data-ttu-id="293bb-366">**Detección de detonación de url**</span><span class="sxs-lookup"><span data-stu-id="293bb-366">**URL detonation detection**</span></span>
- <span data-ttu-id="293bb-367">**Filtrado contra correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="293bb-367">**Anti-spam filtered**</span></span>
- <span data-ttu-id="293bb-368">**ZAP quitado**</span><span class="sxs-lookup"><span data-stu-id="293bb-368">**ZAP removed**</span></span>
- <span data-ttu-id="293bb-369">**Detección por vínculos seguros**</span><span class="sxs-lookup"><span data-stu-id="293bb-369">**Detection by Safe Links**</span></span>

<span data-ttu-id="293bb-370">Si selecciona una fila en la tabla de datos, se muestra un desglose adicional de los recuentos de correo electrónico en el menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="293bb-370">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="293bb-371">**Exportar**:</span><span class="sxs-lookup"><span data-stu-id="293bb-371">**Export**:</span></span>

<span data-ttu-id="293bb-372">Al hacer **clic en** Exportar , en **Opciones,** puede seleccionar uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="293bb-372">On clicking **Export**, under **Options** you can select one of the following values:</span></span>

- <span data-ttu-id="293bb-373">**Resumen (con datos de los últimos 90 días como máximo)**</span><span class="sxs-lookup"><span data-stu-id="293bb-373">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="293bb-374">**Detalles (con datos de los últimos 30 días como máximo)**</span><span class="sxs-lookup"><span data-stu-id="293bb-374">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="293bb-375">En **Fecha**, elija un rango y, a continuación, haga clic **en Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="293bb-375">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="293bb-376">Los datos de los filtros actuales se exportarán a un archivo .csv.</span><span class="sxs-lookup"><span data-stu-id="293bb-376">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="293bb-377">Cada archivo .csv exportado está limitado a 150 000 filas.</span><span class="sxs-lookup"><span data-stu-id="293bb-377">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="293bb-378">Si los datos contienen más de 150 000 filas, se crearán varios archivos .csv.</span><span class="sxs-lookup"><span data-stu-id="293bb-378">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![<span data-ttu-id="293bb-379">Vista técnica en el informe de estado del flujo de correo</span><span class="sxs-lookup"><span data-stu-id="293bb-379">Tech view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-Tech-view.png)

## <a name="sent-and-received-email-report"></a><span data-ttu-id="293bb-380">Informe de correo electrónico enviado y recibido</span><span class="sxs-lookup"><span data-stu-id="293bb-380">Sent and received email report</span></span>

<span data-ttu-id="293bb-381">El **informe de correo electrónico** enviado y recibido es un informe inteligente que muestra información sobre el correo electrónico entrante y saliente, incluidas detecciones de correo no deseado, malware y correo electrónico identificado como "bueno".</span><span class="sxs-lookup"><span data-stu-id="293bb-381">The **Sent and received email** report is a smart report that shows information about incoming and outgoing email, including spam detections, malware, and email identified as "good."</span></span> <span data-ttu-id="293bb-382">La diferencia entre este informe y el informe de estado [de flujo](#mailflow-status-report) de correo es: este informe no incluye datos sobre los mensajes bloqueados por la protección perimetral. Es importante comprender que si un mensaje se envía a cinco destinatarios, lo contamos como un mensaje.</span><span class="sxs-lookup"><span data-stu-id="293bb-382">The difference between this report and the [Mailflow status report](#mailflow-status-report) is: this report doesn't include data about messages blocked by edge protection.It's important to understand that if a message is sent to five recipients we count it as one message.</span></span>

<span data-ttu-id="293bb-383">La vista de agregado y la vista de detalles del informe permiten 90 días de filtrado.</span><span class="sxs-lookup"><span data-stu-id="293bb-383">The aggregate view and the detail view of the report allow for 90 days of filtering.</span></span>

<span data-ttu-id="293bb-384">Para ver el informe, abra el Centro de  [seguridad & cumplimiento,](https://protection.office.com)vaya al Panel de informes y seleccione Correo electrónico enviado \>  y **recibido.**</span><span class="sxs-lookup"><span data-stu-id="293bb-384">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Sent and received email**.</span></span> <span data-ttu-id="293bb-385">Para ir directamente al informe, abra <https://protection.office.com/reportv2?id=SentAndReceivedMailATP> .</span><span class="sxs-lookup"><span data-stu-id="293bb-385">To go directly to the report, open <https://protection.office.com/reportv2?id=SentAndReceivedMailATP>.</span></span>

![Widget de correo electrónico enviado y recibido en el panel Informes](../../media/sent-and-received-email-report-widget.png)

### <a name="report-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="293bb-387">Vista Informe para el informe de correo electrónico enviado y recibido</span><span class="sxs-lookup"><span data-stu-id="293bb-387">Report view for the Sent and received email report</span></span>

<span data-ttu-id="293bb-388">Los gráficos siguientes están disponibles en la vista informe:</span><span class="sxs-lookup"><span data-stu-id="293bb-388">The following charts are available in the report view:</span></span>

- <span data-ttu-id="293bb-389">**Dividir por: Tipo**: El gráfico muestra todas las categorías disponibles:</span><span class="sxs-lookup"><span data-stu-id="293bb-389">**Break down by: Type**: The chart shows all available categories:</span></span>

  - <span data-ttu-id="293bb-390">**Total**</span><span class="sxs-lookup"><span data-stu-id="293bb-390">**Total**</span></span>
  - <span data-ttu-id="293bb-391">**Correo bueno**</span><span class="sxs-lookup"><span data-stu-id="293bb-391">**Good mail**</span></span>
  - <span data-ttu-id="293bb-392">**Malware (antimalware)** (EOP)</span><span class="sxs-lookup"><span data-stu-id="293bb-392">**Malware (anti-malware)** (EOP)</span></span>
  - <span data-ttu-id="293bb-393">**Detecciones de correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="293bb-393">**Spam detections**</span></span>
  - <span data-ttu-id="293bb-394">**Mensajes de regla**</span><span class="sxs-lookup"><span data-stu-id="293bb-394">**Rule messages**</span></span>
  - <span data-ttu-id="293bb-395">**Malware avanzado** (Microsoft Defender para Office 365)</span><span class="sxs-lookup"><span data-stu-id="293bb-395">**Advanced malware** (Microsoft Defender for Office 365)</span></span>

  <span data-ttu-id="293bb-396">Cuando mantiene el mouse sobre un día (punto de datos) en el gráfico, puede ver los detalles de ese día.</span><span class="sxs-lookup"><span data-stu-id="293bb-396">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![Vista de tipo en el informe de correo electrónico enviado y recibido](../../media/sent-and-received-email-report-type-view.png)

- <span data-ttu-id="293bb-398">**Dividir por: Dirección:** el gráfico muestra **datos totales,** **entrantes** **y salientes.**</span><span class="sxs-lookup"><span data-stu-id="293bb-398">**Break down by: Direction**: The chart shows **Total**, **Inbound**, and **Outbound** data.</span></span> <span data-ttu-id="293bb-399">Cuando mantiene el mouse sobre un día (punto de datos) en el gráfico, puede ver los detalles de ese día.</span><span class="sxs-lookup"><span data-stu-id="293bb-399">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![Vista Dirección en el informe de correo electrónico enviado y recibido](../../media/sent-and-received-email-report-direction-view.png)

- <span data-ttu-id="293bb-401">**Explorar en profundidad** \> **Malware (antimalware):** esta selección le lleva a las detecciones [de malware en el informe de correo electrónico](view-email-security-reports.md#malware-detections-in-email-report).</span><span class="sxs-lookup"><span data-stu-id="293bb-401">**Drill down by** \> **Malware (anti-malware)**: This selection takes you to the [Malware detections in email report](view-email-security-reports.md#malware-detections-in-email-report).</span></span>

- <span data-ttu-id="293bb-402">**Explorar en profundidad** \> **Detecciones de correo** no deseado): esta selección le lleva al informe Detecciones [de correo no deseado](view-email-security-reports.md#spam-detections-report).</span><span class="sxs-lookup"><span data-stu-id="293bb-402">**Drill down by** \> **Spam detections)**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="293bb-403">Si hace clic **en Filtros** en una vista de informe, puede modificar los resultados con los filtros siguientes:</span><span class="sxs-lookup"><span data-stu-id="293bb-403">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="293bb-404">**Fecha de inicio** y **fecha de finalización**</span><span class="sxs-lookup"><span data-stu-id="293bb-404">**Start date** and **End date**</span></span>
- <span data-ttu-id="293bb-405">Valores de dirección</span><span class="sxs-lookup"><span data-stu-id="293bb-405">Direction values</span></span>
- <span data-ttu-id="293bb-406">Valores de tipo</span><span class="sxs-lookup"><span data-stu-id="293bb-406">Type values</span></span>

<span data-ttu-id="293bb-407">Para volver a la vista informe, haga clic **en Ver informe**.</span><span class="sxs-lookup"><span data-stu-id="293bb-407">To go back to the report view, click **View report**.</span></span>

### <a name="details-table-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="293bb-408">Vista de tabla De detalles para el informe de correo electrónico enviado y recibido</span><span class="sxs-lookup"><span data-stu-id="293bb-408">Details table view for the Sent and received email report</span></span>

<span data-ttu-id="293bb-409">Si hace clic **en Ver tabla de detalles** en la vista Dividir **por:** Dirección o Dividir **por: Dirección,** se muestra la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="293bb-409">If you click **View details table** in the **Break down by: Direction** or **Break down by: Direction** view, the following information is shown:</span></span>

- <span data-ttu-id="293bb-410">**Fecha (UTC)**</span><span class="sxs-lookup"><span data-stu-id="293bb-410">**Date (UTC)**</span></span>
- <span data-ttu-id="293bb-411">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="293bb-411">**Type**</span></span>
- <span data-ttu-id="293bb-412">**Dirección**</span><span class="sxs-lookup"><span data-stu-id="293bb-412">**Direction**</span></span>
- <span data-ttu-id="293bb-413">**Recuento de mensajes**</span><span class="sxs-lookup"><span data-stu-id="293bb-413">**Message count**</span></span>

<span data-ttu-id="293bb-414">Si hace clic **en Filtros en** una vista de tabla de detalles, puede modificar los resultados con los filtros siguientes:</span><span class="sxs-lookup"><span data-stu-id="293bb-414">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="293bb-415">**Fecha de inicio** y **fecha de finalización**</span><span class="sxs-lookup"><span data-stu-id="293bb-415">**Start date** and **End date**</span></span>
- <span data-ttu-id="293bb-416">Valores de dirección</span><span class="sxs-lookup"><span data-stu-id="293bb-416">Direction values</span></span>
- <span data-ttu-id="293bb-417">Valores de tipo</span><span class="sxs-lookup"><span data-stu-id="293bb-417">Type values</span></span>

<span data-ttu-id="293bb-418">Para volver a la vista informe, haga clic **en Ver informe**.</span><span class="sxs-lookup"><span data-stu-id="293bb-418">To go back to the report view, click **View report**.</span></span>

## <a name="top-senders-and-recipients-report"></a><span data-ttu-id="293bb-419">Informe de remitentes y destinatarios principales</span><span class="sxs-lookup"><span data-stu-id="293bb-419">Top senders and recipients report</span></span>

<span data-ttu-id="293bb-420">El **informe Principales remitentes y destinatarios** es un gráfico circular que muestra los principales remitentes y destinatarios de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="293bb-420">The **Top senders and recipients** report is a pie chart showing your top email senders and recipients.</span></span>

<span data-ttu-id="293bb-421">Para ver el informe, abra el Centro de  [seguridad & cumplimiento,](https://protection.office.com)vaya al Panel de informes y seleccione Principales \>  **remitentes y destinatarios.**</span><span class="sxs-lookup"><span data-stu-id="293bb-421">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top senders and recipients**.</span></span> <span data-ttu-id="293bb-422">Para ir directamente al informe, abra <https://protection.office.com/reportv2?id=TopSenderRecipientsATP> .</span><span class="sxs-lookup"><span data-stu-id="293bb-422">To go directly to the report, open <https://protection.office.com/reportv2?id=TopSenderRecipientsATP>.</span></span>

![Widget Principales remitentes y destinatarios en el panel Informes](../../media/top-senders-and-recipients-widget.png)

### <a name="report-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="293bb-424">Vista Informe para el informe de destinatarios y remitentes principales</span><span class="sxs-lookup"><span data-stu-id="293bb-424">Report view for the Top senders and recipient report</span></span>

<span data-ttu-id="293bb-425">Los gráficos siguientes están disponibles en la vista informe:</span><span class="sxs-lookup"><span data-stu-id="293bb-425">The following charts are available in the report view:</span></span>

- <span data-ttu-id="293bb-426">**Mostrar datos para \> los principales remitentes de correo**</span><span class="sxs-lookup"><span data-stu-id="293bb-426">**Show data for \> Top mail senders**</span></span>
- <span data-ttu-id="293bb-427">**Mostrar datos para \> los principales destinatarios de correo**</span><span class="sxs-lookup"><span data-stu-id="293bb-427">**Show data for \> Top mail recipients**</span></span>
- <span data-ttu-id="293bb-428">**Mostrar datos para los \> principales destinatarios de correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="293bb-428">**Show data for \> Top spam recipients**</span></span>
- <span data-ttu-id="293bb-429">**Mostrar datos para \> Principales destinatarios de malware** (EOP)</span><span class="sxs-lookup"><span data-stu-id="293bb-429">**Show data for \> Top malware recipients** (EOP)</span></span>
- <span data-ttu-id="293bb-430">**Mostrar datos para \> los principales destinatarios de malware (Defender para Office 365)**</span><span class="sxs-lookup"><span data-stu-id="293bb-430">**Show data for \> Top malware recipients (Defender for Office 365)**</span></span>

<span data-ttu-id="293bb-431">La composición del gráfico circular cambia en función de estas selecciones.</span><span class="sxs-lookup"><span data-stu-id="293bb-431">The composition of the pie chart changes based on these selections.</span></span>

<span data-ttu-id="293bb-432">Al pasar el mouse sobre una cuña en el gráfico circular, puede ver un recuento de mensajes enviados o recibidos.</span><span class="sxs-lookup"><span data-stu-id="293bb-432">When you hover over a wedge in the pie chart, you can see a count of messages sent or received.</span></span>

<span data-ttu-id="293bb-433">Si hace clic **en Filtros** en una vista de informe, puede especificar un intervalo de fechas con Fecha **de inicio** y Fecha **de finalización.**</span><span class="sxs-lookup"><span data-stu-id="293bb-433">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

![Gráfico circular en la vista Informe del informe Principales remitentes y destinatarios](../../media/top-senders-and-recipients-report-view.png)

### <a name="details-table-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="293bb-435">Vista de tabla Detalles para el informe de destinatarios y remitentes principales</span><span class="sxs-lookup"><span data-stu-id="293bb-435">Details table view for the Top senders and recipient report</span></span>

<span data-ttu-id="293bb-436">Si hace clic **en Ver tabla de detalles,** la información que se muestra depende del gráfico que estaba mirando:</span><span class="sxs-lookup"><span data-stu-id="293bb-436">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="293bb-437">**Mostrar datos para \> los principales remitentes de correo**</span><span class="sxs-lookup"><span data-stu-id="293bb-437">**Show data for \> Top mail senders**</span></span>

  - <span data-ttu-id="293bb-438">**Principales remitentes de correo**</span><span class="sxs-lookup"><span data-stu-id="293bb-438">**Top mail senders**</span></span>
  - <span data-ttu-id="293bb-439">**Count**</span><span class="sxs-lookup"><span data-stu-id="293bb-439">**Count**</span></span>

- <span data-ttu-id="293bb-440">**Mostrar datos para \> los principales destinatarios de correo**</span><span class="sxs-lookup"><span data-stu-id="293bb-440">**Show data for \> Top mail recipients**</span></span>

  - <span data-ttu-id="293bb-441">**Principales destinatarios de correo**</span><span class="sxs-lookup"><span data-stu-id="293bb-441">**Top mail recipients**</span></span>
  - <span data-ttu-id="293bb-442">**Count**</span><span class="sxs-lookup"><span data-stu-id="293bb-442">**Count**</span></span>

- <span data-ttu-id="293bb-443">**Mostrar datos para los \> principales destinatarios de correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="293bb-443">**Show data for \> Top spam recipients**</span></span>

  - <span data-ttu-id="293bb-444">**Principales destinatarios de correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="293bb-444">**Top spam recipients**</span></span>
  - <span data-ttu-id="293bb-445">**Count**</span><span class="sxs-lookup"><span data-stu-id="293bb-445">**Count**</span></span>

- <span data-ttu-id="293bb-446">**Mostrar datos para \> Principales destinatarios de malware** (EOP)</span><span class="sxs-lookup"><span data-stu-id="293bb-446">**Show data for \> Top malware recipients** (EOP)</span></span>

  - <span data-ttu-id="293bb-447">**Principales destinatarios de malware**</span><span class="sxs-lookup"><span data-stu-id="293bb-447">**Top malware recipients**</span></span>
  - <span data-ttu-id="293bb-448">**Count**</span><span class="sxs-lookup"><span data-stu-id="293bb-448">**Count**</span></span>

- <span data-ttu-id="293bb-449">**Mostrar datos para \> los principales destinatarios de malware (Defender para Office 365)**</span><span class="sxs-lookup"><span data-stu-id="293bb-449">**Show data for \> Top malware recipients (Defender for Office 365)**</span></span>

  - <span data-ttu-id="293bb-450">**Principales destinatarios de malware (Defender para Office 365)**</span><span class="sxs-lookup"><span data-stu-id="293bb-450">**Top malware recipients (Defender for Office 365)**</span></span>
  - <span data-ttu-id="293bb-451">**Count**</span><span class="sxs-lookup"><span data-stu-id="293bb-451">**Count**</span></span>

<span data-ttu-id="293bb-452">Si hace clic **en Filtros en** una vista de tabla de detalles, puede especificar un intervalo de fechas con Fecha de **inicio** y Fecha **de finalización.**</span><span class="sxs-lookup"><span data-stu-id="293bb-452">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="293bb-453">Para volver a la vista informe, haga clic **en Ver informe**.</span><span class="sxs-lookup"><span data-stu-id="293bb-453">To go back to the report view, click **View report**.</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="293bb-454">¿Qué permisos se necesitan para ver estos informes?</span><span class="sxs-lookup"><span data-stu-id="293bb-454">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="293bb-455">Para ver y usar los informes descritos en este artículo, debe ser miembro de uno de los siguientes grupos de roles en el Centro de seguridad & cumplimiento:</span><span class="sxs-lookup"><span data-stu-id="293bb-455">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Security & Compliance Center:</span></span>

- <span data-ttu-id="293bb-456">**Administración de organizaciones**</span><span class="sxs-lookup"><span data-stu-id="293bb-456">**Organization Management**</span></span>
- <span data-ttu-id="293bb-457">**Administrador de seguridad**</span><span class="sxs-lookup"><span data-stu-id="293bb-457">**Security Administrator**</span></span>
- <span data-ttu-id="293bb-458">**Lector de seguridad**</span><span class="sxs-lookup"><span data-stu-id="293bb-458">**Security Reader**</span></span>
- <span data-ttu-id="293bb-459">**Lector global**</span><span class="sxs-lookup"><span data-stu-id="293bb-459">**Global Reader**</span></span>

<span data-ttu-id="293bb-460">Para más información, consulte [Permisos en el Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="293bb-460">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

> [!NOTE]
> <span data-ttu-id="293bb-461">Agregar usuarios al rol correspondiente de Azure Active Directory en el Centro de administración de Microsoft 365 otorga a los usuarios los permisos necesarios en el Centro de seguridad y cumplimiento _y_ permisos para otras características de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="293bb-461">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="293bb-462">Para más información, vea [Sobre los roles de administrador](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="293bb-462">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="293bb-463">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="293bb-463">Related topics</span></span>

[<span data-ttu-id="293bb-464">Informes inteligentes y reportes en el Centro de seguridad y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="293bb-464">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="293bb-465">Reportes de flujo de Correo en el Centro de seguridad y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="293bb-465">Mail flow insights in the Security & Compliance Center</span></span>](mail-flow-insights-v2.md)

[<span data-ttu-id="293bb-466">Ver informes de seguridad de correo electrónico en el Centro de seguridad y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="293bb-466">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)

[<span data-ttu-id="293bb-467">Ver informes de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="293bb-467">View reports for Microsoft Defender for Office 365</span></span>](view-reports-for-mdo.md)
