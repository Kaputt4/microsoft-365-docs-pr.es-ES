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
ms.openlocfilehash: 5f2bdb32d2afde3d0d40261cd3ecf30740dc0ccf
ms.sourcegitcommit: c70067b4ef9c6f8f04aca68c35bb5141857c4e4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2021
ms.locfileid: "53029482"
---
# <a name="view-mail-flow-reports-in-the-reports-dashboard-in-security--compliance-center"></a><span data-ttu-id="a1bba-103">Ver informes de flujo de correo en el panel Informes del Centro de & cumplimiento</span><span class="sxs-lookup"><span data-stu-id="a1bba-103">View mail flow reports in the Reports dashboard in Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="a1bba-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="a1bba-104">**Applies to**</span></span>
- [<span data-ttu-id="a1bba-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="a1bba-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="a1bba-106">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="a1bba-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="a1bba-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a1bba-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="a1bba-108">La mayoría de los informes que se describen en este tema están disponibles en el Centro de administración de Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="a1bba-108">The majority of the reports that are described in this topic are available in the Exchange admin center (EAC).</span></span> <span data-ttu-id="a1bba-109">Para obtener más información, vea [Informes de flujo de correo en el nuevo Centro de administración de Exchange](/exchange/monitoring/mail-flow-reports/mail-flow-reports).</span><span class="sxs-lookup"><span data-stu-id="a1bba-109">For more information, see [Mail flow reports in the new Exchange admin center](/exchange/monitoring/mail-flow-reports/mail-flow-reports).</span></span> <span data-ttu-id="a1bba-110">El [informe de reglas de transporte de Exchange](view-email-security-reports.md#exchange-transport-rule-report) está disponible en el portal de Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="a1bba-110">The [Exchange transport rule report](view-email-security-reports.md#exchange-transport-rule-report) is available in the Microsoft 365 Defender portal.</span></span>

<span data-ttu-id="a1bba-111">Además de los informes de flujo [](mail-flow-insights-v2.md) de correo que están disponibles en el panel flujo de correo en el Centro de seguridad y cumplimiento de &, hay una variedad de informes de flujo de correo adicionales disponibles en el panel informes para ayudarle a supervisar su organización de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a1bba-111">In addition to the mail flow reports that are available in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center, a variety of additional mail flow reports are available in the Reports dashboard to help you monitor your Microsoft 365 organization.</span></span>

<span data-ttu-id="a1bba-112">Si tiene los permisos [necesarios,](#what-permissions-are-needed-to-view-these-reports)puede ver estos informes en el Centro de seguridad [& cumplimiento](https://protection.office.com) yendo al **Panel de** \> **informes**.</span><span class="sxs-lookup"><span data-stu-id="a1bba-112">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the [Security & Compliance Center](https://protection.office.com) by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="a1bba-113">Para ir directamente al panel Informes, abra <https://protection.office.com/insightdashboard> .</span><span class="sxs-lookup"><span data-stu-id="a1bba-113">To go directly to the Reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![Panel de informes en el Centro de seguridad & cumplimiento](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="connector-report"></a><span data-ttu-id="a1bba-115">Informe del conector</span><span class="sxs-lookup"><span data-stu-id="a1bba-115">Connector report</span></span>

<span data-ttu-id="a1bba-116">El **informe connector muestra** la actividad de flujo de correo en los conectores entrantes y [salientes configurados](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) para la organización.</span><span class="sxs-lookup"><span data-stu-id="a1bba-116">The **Connector report** shows mail flow activity on the [inbound and outbound connectors](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) that are configured for your organization.</span></span>

<span data-ttu-id="a1bba-117">Para ver el informe, abra el Centro de  [seguridad & cumplimiento,](https://protection.office.com)vaya al Panel \> **de informes** y seleccione **Informe de conector**.</span><span class="sxs-lookup"><span data-stu-id="a1bba-117">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Connector report**.</span></span> <span data-ttu-id="a1bba-118">Para ir directamente al informe, abra <https://protection.office.com/reportv2?id=ConnectorReport> .</span><span class="sxs-lookup"><span data-stu-id="a1bba-118">To go directly to the report, open <https://protection.office.com/reportv2?id=ConnectorReport>.</span></span>

![Widget de informe de conector en el panel Informes](../../media/connector-report-widget.png)

### <a name="report-view-for-the-connector-report"></a><span data-ttu-id="a1bba-120">Vista Informe para el informe de Connector</span><span class="sxs-lookup"><span data-stu-id="a1bba-120">Report view for the Connector report</span></span>

<span data-ttu-id="a1bba-121">Los siguientes gráficos están disponibles en la vista informe:</span><span class="sxs-lookup"><span data-stu-id="a1bba-121">The following charts are available in report view:</span></span>

- <span data-ttu-id="a1bba-122">**Ver datos por: Flujo de correo:** este gráfico muestra el número de mensajes entrantes y salientes organizados por:</span><span class="sxs-lookup"><span data-stu-id="a1bba-122">**View data by: Mail flow**: This chart shows the number of inbound and outbound messages organized by:</span></span>

  - <span data-ttu-id="a1bba-123">**Total**</span><span class="sxs-lookup"><span data-stu-id="a1bba-123">**Total**</span></span>
  - <span data-ttu-id="a1bba-124">**Desde Internet sin conector**</span><span class="sxs-lookup"><span data-stu-id="a1bba-124">**From the internet without a connector**</span></span>
  - <span data-ttu-id="a1bba-125">**A Internet sin conector**</span><span class="sxs-lookup"><span data-stu-id="a1bba-125">**To the internet without a connector**</span></span>
  - <span data-ttu-id="a1bba-126">Un conector específico que haya configurado.</span><span class="sxs-lookup"><span data-stu-id="a1bba-126">A specific connector that you've configured.</span></span>

  <span data-ttu-id="a1bba-127">Para aislar los datos del gráfico, use el control **Mostrar datos para** seleccionar una de estas opciones o Todo el flujo de **correo**.</span><span class="sxs-lookup"><span data-stu-id="a1bba-127">To isolate the data in the chart, use the **Show data for** control to select one of these options or **All mail flow**.</span></span>

  ![Ver datos por flujo de correo en el informe de Connector](../../media/connector-report-view-data-by-mail-flow.png)

- <span data-ttu-id="a1bba-129">**Ver datos por: uso de TLS:** este gráfico muestra el porcentaje de uso de la versión seguridad de la capa de transporte (TLS) para el flujo de correo.</span><span class="sxs-lookup"><span data-stu-id="a1bba-129">**View data by: TLS usage**: This chart shows the percentage of Transport Layer Security (TLS) version usage for mail flow.</span></span>

  <span data-ttu-id="a1bba-130">Para aislar los datos del gráfico, use el control **Mostrar datos** para seleccionar una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="a1bba-130">To isolate the data in the chart, use the **Show data for** control to select one of the following options:</span></span>

  - <span data-ttu-id="a1bba-131">**Todo el flujo de correo**</span><span class="sxs-lookup"><span data-stu-id="a1bba-131">**All mail flow**</span></span>
  - <span data-ttu-id="a1bba-132">**Desde Internet sin conector**</span><span class="sxs-lookup"><span data-stu-id="a1bba-132">**From the internet without a connector**</span></span>
  - <span data-ttu-id="a1bba-133">**A Internet sin conector**</span><span class="sxs-lookup"><span data-stu-id="a1bba-133">**To the internet without a connector**</span></span>
  - <span data-ttu-id="a1bba-134">Un conector específico que haya configurado.</span><span class="sxs-lookup"><span data-stu-id="a1bba-134">A specific connector that you've configured.</span></span>

  ![Ver datos por uso de TLS en el informe de Connector](../../media/connector-report-view-data-by-tls-usage.png)

<span data-ttu-id="a1bba-136">Si hace clic **en Filtros** en una vista de informe, puede especificar un intervalo de fechas con Fecha **de inicio** y Fecha **de finalización.**</span><span class="sxs-lookup"><span data-stu-id="a1bba-136">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-connector-report"></a><span data-ttu-id="a1bba-137">Vista de tabla Detalles del informe de Connector</span><span class="sxs-lookup"><span data-stu-id="a1bba-137">Details table view for the Connector report</span></span>

<span data-ttu-id="a1bba-138">Si hace clic **en Ver tabla de detalles** en una vista de informe, se muestra la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="a1bba-138">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="a1bba-139">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="a1bba-139">**Date**</span></span>
- <span data-ttu-id="a1bba-140">**Dirección y nombre del conector**</span><span class="sxs-lookup"><span data-stu-id="a1bba-140">**Connector direction and name**</span></span>
- <span data-ttu-id="a1bba-141">**Tipo de conector**</span><span class="sxs-lookup"><span data-stu-id="a1bba-141">**Connector type**</span></span>
- <span data-ttu-id="a1bba-142">**¿TLS forzada?**: El valor **True** o **False**.</span><span class="sxs-lookup"><span data-stu-id="a1bba-142">**Forced TLS?**: The value **True** or **False**.</span></span>
- <span data-ttu-id="a1bba-143">**Sin TLS** (porcentaje)</span><span class="sxs-lookup"><span data-stu-id="a1bba-143">**No TLS** (percentage)</span></span>
- <span data-ttu-id="a1bba-144">**TLS 1.0** (porcentaje)</span><span class="sxs-lookup"><span data-stu-id="a1bba-144">**TLS 1.0** (percentage)</span></span>
- <span data-ttu-id="a1bba-145">**TLS 1.1** (porcentaje)</span><span class="sxs-lookup"><span data-stu-id="a1bba-145">**TLS 1.1** (percentage)</span></span>
- <span data-ttu-id="a1bba-146">**TLS 1.2** (porcentaje)</span><span class="sxs-lookup"><span data-stu-id="a1bba-146">**TLS 1.2** (percentage)</span></span>
- <span data-ttu-id="a1bba-147">**Volumen:** el número de mensajes.</span><span class="sxs-lookup"><span data-stu-id="a1bba-147">**Volume**: The number of messages.</span></span>

<span data-ttu-id="a1bba-148">Si hace clic **en Filtros en** una vista de tabla de detalles, puede especificar un intervalo de fechas con Fecha de **inicio** y Fecha **de finalización.**</span><span class="sxs-lookup"><span data-stu-id="a1bba-148">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="a1bba-149">Para volver a la vista informe, haga clic **en Ver informe**.</span><span class="sxs-lookup"><span data-stu-id="a1bba-149">To go back to the report view, click **View report**.</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="a1bba-150">Informe de reglas de transporte de Exchange</span><span class="sxs-lookup"><span data-stu-id="a1bba-150">Exchange transport rule report</span></span>

<span data-ttu-id="a1bba-151">El **informe de reglas de transporte de Exchange** muestra el efecto de las reglas de flujo de correo (también conocidas como reglas de transporte) en los mensajes entrantes y salientes de la organización.</span><span class="sxs-lookup"><span data-stu-id="a1bba-151">The **Exchange transport rule report** shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="a1bba-152">Para ver el informe, abra el Centro de  [seguridad & cumplimiento,](https://protection.office.com)vaya al Panel de informes y seleccione Regla de transporte \>  de **Exchange**.</span><span class="sxs-lookup"><span data-stu-id="a1bba-152">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Exchange Transport rule**.</span></span> <span data-ttu-id="a1bba-153">Para ir directamente al informe, abra <https://protection.office.com/reportv2?id=ETRRuleReport> .</span><span class="sxs-lookup"><span data-stu-id="a1bba-153">To go directly to the report, open <https://protection.office.com/reportv2?id=ETRRuleReport>.</span></span>

![Widget de regla de transporte de Exchange en el panel Informes](../../media/transport-rule-report-widget.png)

### <a name="report-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="a1bba-155">Vista Informe para el informe de reglas de transporte de Exchange</span><span class="sxs-lookup"><span data-stu-id="a1bba-155">Report view for the Exchange transport rule report</span></span>

<span data-ttu-id="a1bba-156">Los siguientes gráficos están disponibles en la vista informe:</span><span class="sxs-lookup"><span data-stu-id="a1bba-156">The following charts are available in report view:</span></span>

- <span data-ttu-id="a1bba-157">**Ver datos por: reglas de transporte de** \> Exchange **Dividir por: Dirección:** este gráfico  muestra  el número de mensajes entrantes y salientes que se vieron afectados por las reglas de transporte.</span><span class="sxs-lookup"><span data-stu-id="a1bba-157">**View data by: Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by transport rules.</span></span>

- <span data-ttu-id="a1bba-158">**Ver datos por: reglas de transporte de** \> Exchange **Dividir por: Gravedad:** este gráfico muestra  el número de mensajes de gravedad alta y media y **de gravedad** baja.</span><span class="sxs-lookup"><span data-stu-id="a1bba-158">**View data by: Exchange transport rules** \> **Break down by: Severity**: This chart shows the number of **High severity** and **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="a1bba-159">El nivel de gravedad se establece como una acción en la regla (**Auditar** esta regla con el nivel de gravedad o _SetAuditSeverity_).</span><span class="sxs-lookup"><span data-stu-id="a1bba-159">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="a1bba-160">Para obtener más información, vea [Acciones de regla de flujo de correo en Exchange Online](//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span><span class="sxs-lookup"><span data-stu-id="a1bba-160">For more information, see [Mail flow rule actions in Exchange Online](//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="a1bba-161">**Ver datos por: reglas de transporte** \> de DLP Exchange **Dividir por: Dirección:** este gráfico  muestra  el número de mensajes entrantes y salientes que se vieron afectados por las reglas de transporte de prevención de pérdida de datos (DLP).</span><span class="sxs-lookup"><span data-stu-id="a1bba-161">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) transport rules.</span></span> <span data-ttu-id="a1bba-162">Puede refinar aún más el gráfico seleccionando una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="a1bba-162">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="a1bba-163">**Mostrar datos para: todas las reglas de transporte DLP**</span><span class="sxs-lookup"><span data-stu-id="a1bba-163">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="a1bba-164">**Mostrar datos para: usuarios en peligro**</span><span class="sxs-lookup"><span data-stu-id="a1bba-164">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="a1bba-165">**Mostrar datos para: Bajo volumen de contenido detectado por la Ley Patriota de EE.UU.**</span><span class="sxs-lookup"><span data-stu-id="a1bba-165">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

- <span data-ttu-id="a1bba-166">**Ver datos por: reglas de transporte** \> de DLP Exchange **Dividir por: Dirección:** esta vista muestra el número de mensajes  de gravedad alta y media y de gravedad baja que se vieron afectados por las reglas de transporte DLP. </span><span class="sxs-lookup"><span data-stu-id="a1bba-166">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This view shows the number of **High severity** and **Medium severity**, and **Low severity** messages that were affected by DLP transport rules.</span></span> <span data-ttu-id="a1bba-167">Puede refinar aún más el gráfico seleccionando una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="a1bba-167">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="a1bba-168">**Mostrar datos para: todas las reglas de transporte DLP**</span><span class="sxs-lookup"><span data-stu-id="a1bba-168">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="a1bba-169">**Mostrar datos para: usuarios en peligro**</span><span class="sxs-lookup"><span data-stu-id="a1bba-169">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="a1bba-170">**Mostrar datos para: Bajo volumen de contenido detectado por la Ley Patriota de EE.UU.**</span><span class="sxs-lookup"><span data-stu-id="a1bba-170">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

<span data-ttu-id="a1bba-171">Si hace clic **en Filtros** en una vista de informe, puede modificar los resultados con los siguientes filtros::</span><span class="sxs-lookup"><span data-stu-id="a1bba-171">If you click **Filters** in a report view, you can modify the results with the following filters::</span></span>

- <span data-ttu-id="a1bba-172">**Fecha de inicio** y **fecha de finalización**</span><span class="sxs-lookup"><span data-stu-id="a1bba-172">**Start date** and **End date**</span></span>
- <span data-ttu-id="a1bba-173">Valores de dirección</span><span class="sxs-lookup"><span data-stu-id="a1bba-173">Direction values</span></span>
- <span data-ttu-id="a1bba-174">Valores de gravedad</span><span class="sxs-lookup"><span data-stu-id="a1bba-174">Severity values</span></span>

![Vista Informe en el informe de reglas de transporte de Exchange](../../media/transport-rule-report-report-view.png)

### <a name="details-table-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="a1bba-176">Vista de tabla de detalles para el informe de reglas de transporte de Exchange</span><span class="sxs-lookup"><span data-stu-id="a1bba-176">Details table view for the Exchange transport rule report</span></span>

<span data-ttu-id="a1bba-177">Si hace clic **en Ver tabla de detalles,** la información que se muestra depende del gráfico que estaba mirando:</span><span class="sxs-lookup"><span data-stu-id="a1bba-177">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="a1bba-178">**Ver datos por: Reglas de transporte de Exchange:**</span><span class="sxs-lookup"><span data-stu-id="a1bba-178">**View data by: Exchange Transport rules**:</span></span>

  - <span data-ttu-id="a1bba-179">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="a1bba-179">**Date**</span></span>
  - <span data-ttu-id="a1bba-180">**Regla de transporte**</span><span class="sxs-lookup"><span data-stu-id="a1bba-180">**Transport rule**</span></span>
  - <span data-ttu-id="a1bba-181">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="a1bba-181">**Subject**</span></span>
  - <span data-ttu-id="a1bba-182">**Dirección del remitente**</span><span class="sxs-lookup"><span data-stu-id="a1bba-182">**Sender address**</span></span>
  - <span data-ttu-id="a1bba-183">**Dirección de destinatario**</span><span class="sxs-lookup"><span data-stu-id="a1bba-183">**Recipient address**</span></span>
  - <span data-ttu-id="a1bba-184">**Gravedad**</span><span class="sxs-lookup"><span data-stu-id="a1bba-184">**Severity**</span></span>
  - <span data-ttu-id="a1bba-185">**Dirección**</span><span class="sxs-lookup"><span data-stu-id="a1bba-185">**Direction**</span></span>

- <span data-ttu-id="a1bba-186">**Ver datos por: Reglas de transporte de Dlp Exchange**:</span><span class="sxs-lookup"><span data-stu-id="a1bba-186">**View data by: DLP Exchange transport rules**:</span></span>

  - <span data-ttu-id="a1bba-187">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="a1bba-187">**Date**</span></span>
  - <span data-ttu-id="a1bba-188">**Directiva DLP**</span><span class="sxs-lookup"><span data-stu-id="a1bba-188">**DLP policy**</span></span>
  - <span data-ttu-id="a1bba-189">**Regla de transporte**</span><span class="sxs-lookup"><span data-stu-id="a1bba-189">**Transport rule**</span></span>
  - <span data-ttu-id="a1bba-190">**Asunto**</span><span class="sxs-lookup"><span data-stu-id="a1bba-190">**Subject**</span></span>
  - <span data-ttu-id="a1bba-191">**Dirección del remitente**</span><span class="sxs-lookup"><span data-stu-id="a1bba-191">**Sender address**</span></span>
  - <span data-ttu-id="a1bba-192">**Dirección de destinatario**</span><span class="sxs-lookup"><span data-stu-id="a1bba-192">**Recipient address**</span></span>
  - <span data-ttu-id="a1bba-193">**Gravedad**</span><span class="sxs-lookup"><span data-stu-id="a1bba-193">**Severity**</span></span>
  - <span data-ttu-id="a1bba-194">**Dirección**</span><span class="sxs-lookup"><span data-stu-id="a1bba-194">**Direction**</span></span>

<span data-ttu-id="a1bba-195">Si hace clic **en Filtros en** una vista de tabla de detalles, puede modificar los resultados con los filtros siguientes:</span><span class="sxs-lookup"><span data-stu-id="a1bba-195">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="a1bba-196">**Fecha de inicio** y **fecha de finalización**</span><span class="sxs-lookup"><span data-stu-id="a1bba-196">**Start date** and **End date**</span></span>
- <span data-ttu-id="a1bba-197">Valores de dirección</span><span class="sxs-lookup"><span data-stu-id="a1bba-197">Direction values</span></span>
- <span data-ttu-id="a1bba-198">Valores de gravedad</span><span class="sxs-lookup"><span data-stu-id="a1bba-198">Severity values</span></span>

<span data-ttu-id="a1bba-199">Para volver a la vista informe, haga clic **en Ver informe**.</span><span class="sxs-lookup"><span data-stu-id="a1bba-199">To go back to the report view, click **View report**.</span></span>

## <a name="forwarding-report"></a><span data-ttu-id="a1bba-200">Informe de reenvío</span><span class="sxs-lookup"><span data-stu-id="a1bba-200">Forwarding report</span></span>

<span data-ttu-id="a1bba-201">El **informe de reenvío** muestra los mensajes reenviados automáticamente a dominios externos desde Exchange Online buzones de correo.</span><span class="sxs-lookup"><span data-stu-id="a1bba-201">The **Forwarding report** shows your organization's automatically forwarded messages to external domains from Exchange Online mailboxes.</span></span> <span data-ttu-id="a1bba-202">Los mensajes reenviados pueden suponer un riesgo de seguridad o cumplimiento, e indicar una cuenta comprometida.</span><span class="sxs-lookup"><span data-stu-id="a1bba-202">Forwarded messages can pose a security or compliance risk, and might indicate a compromised account.</span></span>

<span data-ttu-id="a1bba-203">Para ver el informe, abra el Centro de  [seguridad & cumplimiento,](https://protection.office.com)vaya al Panel de informes y seleccione \>  **Reenviar informe**.</span><span class="sxs-lookup"><span data-stu-id="a1bba-203">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Forwarding report**.</span></span> <span data-ttu-id="a1bba-204">Para ir directamente al informe, abra <https://protection.office.com/reportv2?id=MailFlowForwarding> .</span><span class="sxs-lookup"><span data-stu-id="a1bba-204">To go directly to the report, open <https://protection.office.com/reportv2?id=MailFlowForwarding>.</span></span>

![Widget de informe de reenvío en el panel Informes](../../media/forwarding-report-widget.png)

### <a name="report-view-for-the-forwarding-report"></a><span data-ttu-id="a1bba-206">Vista Informe para el informe de reenvío</span><span class="sxs-lookup"><span data-stu-id="a1bba-206">Report view for the Forwarding report</span></span>

<span data-ttu-id="a1bba-207">Los gráficos siguientes están disponibles en la vista informe:</span><span class="sxs-lookup"><span data-stu-id="a1bba-207">The following charts are available in the report view:</span></span>

- <span data-ttu-id="a1bba-208">**Mostrar datos para: Métodos de reenvío:** se muestran los siguientes métodos:</span><span class="sxs-lookup"><span data-stu-id="a1bba-208">**Show data for: Forwarding methods**: The following methods are shown:</span></span>

  - <span data-ttu-id="a1bba-209">**Regla de transporte:** también conocida como reglas [de flujo de correo](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span><span class="sxs-lookup"><span data-stu-id="a1bba-209">**Transport rule**: Also known as [mail flow rules](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span></span>
  - <span data-ttu-id="a1bba-210">**Regla de buzón:** también conocida como [reglas de bandeja de entrada](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).</span><span class="sxs-lookup"><span data-stu-id="a1bba-210">**Mailbox rule**: Also known as [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).</span></span>

  ![Vista De métodos de reenvío en el informe de reenvío](../../media/forwarding-report-forwarding-methods.png)

- <span data-ttu-id="a1bba-212">**Mostrar datos para: Dominios de reenvío:** esta vista muestra los dominios de destinatario que son los destinos para el reenvío.</span><span class="sxs-lookup"><span data-stu-id="a1bba-212">**Show data for: Forwarding domains**: This view shows the recipient domains that are the destinations for forwarding.</span></span>

  ![Vista De dominios de reenvío en el informe de reenvío](../../media/forwarding-report-forwarding-domains.png)

- <span data-ttu-id="a1bba-214">**Mostrar datos para: Reenviadores:** se muestran los siguientes reenviadores:</span><span class="sxs-lookup"><span data-stu-id="a1bba-214">**Show data for: Forwarders**: The following forwarders are shown:</span></span>

  - <span data-ttu-id="a1bba-215">**Regla de transporte**</span><span class="sxs-lookup"><span data-stu-id="a1bba-215">**Transport rule**</span></span>
  - <span data-ttu-id="a1bba-216">El buzón que contiene la regla de la Bandeja de entrada de reenvío.</span><span class="sxs-lookup"><span data-stu-id="a1bba-216">The mailbox that contains the forwarding Inbox rule.</span></span>

  ![Vista Reenviadores en el informe de reenvío](../../media/forwarding-report-forwarders.png)

<span data-ttu-id="a1bba-218">Si hace clic **en Filtros** en una vista de informe, puede especificar un intervalo de fechas con Fecha **de inicio** y Fecha **de finalización.**</span><span class="sxs-lookup"><span data-stu-id="a1bba-218">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-report"></a><span data-ttu-id="a1bba-219">Vista de tabla Detalles del informe de reenvío</span><span class="sxs-lookup"><span data-stu-id="a1bba-219">Details table view for the Forwarding report</span></span>

<span data-ttu-id="a1bba-220">Si hace clic **en Ver tabla de detalles** en una vista de informe, se muestra la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="a1bba-220">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="a1bba-221">**Reenviadores:** la regla **de transporte** de valor o el buzón que contiene la regla de la Bandeja de entrada de reenvío.</span><span class="sxs-lookup"><span data-stu-id="a1bba-221">**Forwarders**: The value **Transport rule** or the mailbox that contains the forwarding Inbox rule.</span></span>
- <span data-ttu-id="a1bba-222">**Tipo de reenvío:** la regla **de buzón de correo** de valor o la regla de **transporte**.</span><span class="sxs-lookup"><span data-stu-id="a1bba-222">**Forwarding type**: The value **Mailbox rule** or **Transport rule**.</span></span>
- <span data-ttu-id="a1bba-223">**Nombre de destinatario**</span><span class="sxs-lookup"><span data-stu-id="a1bba-223">**Recipient name**</span></span>
- <span data-ttu-id="a1bba-224">**Dominio del destinatario**</span><span class="sxs-lookup"><span data-stu-id="a1bba-224">**Recipient domain**</span></span>
- <span data-ttu-id="a1bba-225">**Detalles:** este es el valor GUID de la regla de flujo de correo o el valor RuleIdentity de la regla Bandeja de entrada.</span><span class="sxs-lookup"><span data-stu-id="a1bba-225">**Details**: This is the GUID value of the mail flow rule, or the RuleIdentity value of the Inbox rule.</span></span>
- <span data-ttu-id="a1bba-226">**Count**</span><span class="sxs-lookup"><span data-stu-id="a1bba-226">**Count**</span></span>
- <span data-ttu-id="a1bba-227">**Primera fecha de reenvío**</span><span class="sxs-lookup"><span data-stu-id="a1bba-227">**First forward date**</span></span>

<span data-ttu-id="a1bba-228">Si hace clic **en Filtros en** una vista de tabla de detalles, puede especificar un intervalo de fechas con Fecha de **inicio** y Fecha **de finalización.**</span><span class="sxs-lookup"><span data-stu-id="a1bba-228">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="a1bba-229">Para volver a la vista informes, haga clic **en Ver informe**.</span><span class="sxs-lookup"><span data-stu-id="a1bba-229">To go back to the reports view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="a1bba-230">Informe de estado de flujo de correo</span><span class="sxs-lookup"><span data-stu-id="a1bba-230">Mailflow status report</span></span>

<span data-ttu-id="a1bba-231">El **informe de estado de flujo** de correo es similar al informe de correo electrónico enviado y recibido, con información adicional sobre el correo electrónico permitido o bloqueado en el perímetro. [](#sent-and-received-email-report)</span><span class="sxs-lookup"><span data-stu-id="a1bba-231">The **Mailflow status report** is similar to the [Sent and received email report](#sent-and-received-email-report), with additional information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="a1bba-232">Este es el único informe que contiene información de protección perimetral y muestra cuánto correo electrónico se bloquea antes de que se le permita entrar en el servicio para su evaluación por parte de Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="a1bba-232">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="a1bba-233">Es importante comprender que si un mensaje se envía a cinco destinatarios, lo contamos como cinco mensajes diferentes y no un mensaje.</span><span class="sxs-lookup"><span data-stu-id="a1bba-233">It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>
<span data-ttu-id="a1bba-234">Para ver el informe, abra el Centro de  [seguridad & cumplimiento,](https://protection.office.com)vaya al Panel de informes y seleccione Informe de estado de flujo \>  **de correo**.</span><span class="sxs-lookup"><span data-stu-id="a1bba-234">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Mailflow status report**.</span></span> <span data-ttu-id="a1bba-235">Para ir directamente al informe **de estado de flujo de correo**, abra <https://protection.office.com/mailflowStatusReport> .</span><span class="sxs-lookup"><span data-stu-id="a1bba-235">To go directly to the **Mail flow status report**, open <https://protection.office.com/mailflowStatusReport>.</span></span>

![Widget de informe de estado de flujo de correo en el panel Informes](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="a1bba-237">Vista de tipo para el informe de estado de flujo de correo</span><span class="sxs-lookup"><span data-stu-id="a1bba-237">Type view for the Mailflow status report</span></span>

<span data-ttu-id="a1bba-238">Al abrir el informe, la **pestaña Tipo** está seleccionada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="a1bba-238">When you open the report, the **Type** tab is selected by default.</span></span> <span data-ttu-id="a1bba-239">De forma predeterminada, esta vista contiene un gráfico y una tabla de datos configurada con los filtros siguientes:</span><span class="sxs-lookup"><span data-stu-id="a1bba-239">By default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="a1bba-240">**Fecha:** los últimos 7 días.</span><span class="sxs-lookup"><span data-stu-id="a1bba-240">**Date**: The last 7 days.</span></span>
- <span data-ttu-id="a1bba-241">**Dirección**:</span><span class="sxs-lookup"><span data-stu-id="a1bba-241">**Direction**:</span></span>

  - <span data-ttu-id="a1bba-242">**Entrante**</span><span class="sxs-lookup"><span data-stu-id="a1bba-242">**Inbound**</span></span>
  - <span data-ttu-id="a1bba-243">**Saliente**</span><span class="sxs-lookup"><span data-stu-id="a1bba-243">**Outbound**</span></span>
  - <span data-ttu-id="a1bba-244">**Intra-org:** este recuento es para mensajes dentro de un espacio empresarial, es decir,</span><span class="sxs-lookup"><span data-stu-id="a1bba-244">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="a1bba-245">sender abc@domain.com al destinatario xyz@domain.com (se cuenta por separado de **Entrante** y **Saliente**)</span><span class="sxs-lookup"><span data-stu-id="a1bba-245">sender abc@domain.com sends to recipient xyz@domain.com  (counted separately from **Inbound** and **Outbound**)</span></span>

- <span data-ttu-id="a1bba-246">**Tipo**:</span><span class="sxs-lookup"><span data-stu-id="a1bba-246">**Type**:</span></span>

  - <span data-ttu-id="a1bba-247">**Correo bueno**</span><span class="sxs-lookup"><span data-stu-id="a1bba-247">**Good mail**</span></span>
  - <span data-ttu-id="a1bba-248">**Malware**</span><span class="sxs-lookup"><span data-stu-id="a1bba-248">**Malware**</span></span>
  - <span data-ttu-id="a1bba-249">**Correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="a1bba-249">**Spam**</span></span>
  - <span data-ttu-id="a1bba-250">**Protección perimetral**</span><span class="sxs-lookup"><span data-stu-id="a1bba-250">**Edge protection**</span></span>
  - <span data-ttu-id="a1bba-251">**Mensajes de regla**</span><span class="sxs-lookup"><span data-stu-id="a1bba-251">**Rule messages**</span></span>
  - <span data-ttu-id="a1bba-252">**Correo de suplantación de identidad**</span><span class="sxs-lookup"><span data-stu-id="a1bba-252">**Phishing email**</span></span>

<span data-ttu-id="a1bba-253">El gráfico está organizado por los **valores Type.**</span><span class="sxs-lookup"><span data-stu-id="a1bba-253">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="a1bba-254">Puede cambiar estos filtros haciendo clic en **Filtrar** o haciendo clic en un valor de la leyenda del gráfico.</span><span class="sxs-lookup"><span data-stu-id="a1bba-254">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span>

<span data-ttu-id="a1bba-255">La tabla de datos contiene la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="a1bba-255">The data table contains the following information:</span></span>

- <span data-ttu-id="a1bba-256">**Dirección**</span><span class="sxs-lookup"><span data-stu-id="a1bba-256">**Direction**</span></span>
- <span data-ttu-id="a1bba-257">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="a1bba-257">**Type**</span></span>
- <span data-ttu-id="a1bba-258">**24 horas**</span><span class="sxs-lookup"><span data-stu-id="a1bba-258">**24 hours**</span></span>
- <span data-ttu-id="a1bba-259">**3 días**</span><span class="sxs-lookup"><span data-stu-id="a1bba-259">**3 days**</span></span>
- <span data-ttu-id="a1bba-260">**7 días**</span><span class="sxs-lookup"><span data-stu-id="a1bba-260">**7 days**</span></span>
- <span data-ttu-id="a1bba-261">**15 días**</span><span class="sxs-lookup"><span data-stu-id="a1bba-261">**15 days**</span></span>
- <span data-ttu-id="a1bba-262">**30 días**</span><span class="sxs-lookup"><span data-stu-id="a1bba-262">**30 days**</span></span>

<span data-ttu-id="a1bba-263">Si hace clic **en Elegir una categoría para obtener más información,** puede seleccionar entre los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="a1bba-263">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="a1bba-264">**Correo electrónico de suplantación** de identidad : esta selección le lleva al informe [de estado de protección contra amenazas](view-email-security-reports.md#threat-protection-status-report).</span><span class="sxs-lookup"><span data-stu-id="a1bba-264">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="a1bba-265">**Malware en el correo** electrónico: esta selección le lleva al informe [de estado de protección contra amenazas](view-email-security-reports.md#threat-protection-status-report).</span><span class="sxs-lookup"><span data-stu-id="a1bba-265">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="a1bba-266">**Detecciones de correo** no deseado: esta selección le lleva al informe [Detecciones de correo no deseado](view-email-security-reports.md#spam-detections-report).</span><span class="sxs-lookup"><span data-stu-id="a1bba-266">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="a1bba-267">**Correo no deseado bloqueado** perimetral: esta selección le lleva al informe [Detecciones de correo no deseado](view-email-security-reports.md#spam-detections-report).</span><span class="sxs-lookup"><span data-stu-id="a1bba-267">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="a1bba-268">**Exportar**:</span><span class="sxs-lookup"><span data-stu-id="a1bba-268">**Export**:</span></span>

<span data-ttu-id="a1bba-269">Para la vista de detalles, solo puede exportar datos durante un día.</span><span class="sxs-lookup"><span data-stu-id="a1bba-269">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="a1bba-270">Por lo tanto, si desea exportar datos durante 7 días, debe realizar 7 acciones de exportación diferentes.</span><span class="sxs-lookup"><span data-stu-id="a1bba-270">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="a1bba-271">Cada archivo .csv exportada está limitado a 150 000 filas.</span><span class="sxs-lookup"><span data-stu-id="a1bba-271">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="a1bba-272">Si los datos de ese día contienen más de 150.000 filas, se crearán varios .csv archivos.</span><span class="sxs-lookup"><span data-stu-id="a1bba-272">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![Vista De tipo en el informe de estado de flujo de correo](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="a1bba-274">Vista Dirección del informe de estado de flujo de correo</span><span class="sxs-lookup"><span data-stu-id="a1bba-274">Direction view for the Mailflow status report</span></span>

<span data-ttu-id="a1bba-275">Si hace clic en la **pestaña Dirección,** se usan los mismos filtros predeterminados de la **vista** Tipo.</span><span class="sxs-lookup"><span data-stu-id="a1bba-275">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="a1bba-276">El gráfico está organizado por valores **direction.**</span><span class="sxs-lookup"><span data-stu-id="a1bba-276">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="a1bba-277">Puede cambiar estos filtros haciendo clic en **Filtrar** o haciendo clic en un valor de la leyenda del gráfico.</span><span class="sxs-lookup"><span data-stu-id="a1bba-277">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span> <span data-ttu-id="a1bba-278">Se usan los mismos filtros de **la vista** Tipo.</span><span class="sxs-lookup"><span data-stu-id="a1bba-278">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="a1bba-279">La tabla de datos contiene la misma información de la **vista** Tipo.</span><span class="sxs-lookup"><span data-stu-id="a1bba-279">The data table contains same information from the **Type** view.</span></span>

<span data-ttu-id="a1bba-280">La **categoría Elegir una categoría para obtener más detalles** sobre las selecciones y el comportamiento disponibles son los mismos que la **vista** Tipo.</span><span class="sxs-lookup"><span data-stu-id="a1bba-280">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

<span data-ttu-id="a1bba-281">**Exportar**:</span><span class="sxs-lookup"><span data-stu-id="a1bba-281">**Export**:</span></span>

<span data-ttu-id="a1bba-282">Para la vista de detalles, solo puede exportar datos durante un día.</span><span class="sxs-lookup"><span data-stu-id="a1bba-282">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="a1bba-283">Por lo tanto, si desea exportar datos durante 7 días, debe realizar 7 acciones de exportación diferentes.</span><span class="sxs-lookup"><span data-stu-id="a1bba-283">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="a1bba-284">Cada archivo .csv exportada está limitado a 150 000 filas.</span><span class="sxs-lookup"><span data-stu-id="a1bba-284">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="a1bba-285">Si los datos de ese día contienen más de 150.000 filas, se crearán varios .csv archivos.</span><span class="sxs-lookup"><span data-stu-id="a1bba-285">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![Vista Dirección en el informe de estado de flujo de correo](../../media/mail-flow-status-report-direction-view.png)

### <a name="funnel-view-for-the-mailflow-status-report"></a><span data-ttu-id="a1bba-287">Vista embudo para el informe de estado de flujo de correo</span><span class="sxs-lookup"><span data-stu-id="a1bba-287">Funnel view for the Mailflow status report</span></span>

<span data-ttu-id="a1bba-288">La **vista Embudo** muestra cómo las características de protección contra amenazas de correo electrónico de Microsoft filtran el correo electrónico entrante y saliente en su organización.</span><span class="sxs-lookup"><span data-stu-id="a1bba-288">The **Funnel** view shows you how Microsoft's email threat protection features filter incoming and outgoing email in your organization.</span></span> <span data-ttu-id="a1bba-289">Proporciona detalles sobre el recuento total de correo electrónico y cómo afectan a este recuento las características de protección contra amenazas configuradas, como la protección perimetral, el antimalware, la suplantación de identidad (phishing), el correo no deseado y la suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="a1bba-289">It provides details on the total email count, and how the configured threat protection features, including edge protection, anti-malware, anti-phishing, anti-spam, and anti-spoofing affect this count.</span></span>

<span data-ttu-id="a1bba-290">Si hace clic en la **pestaña Embudo,** de forma predeterminada, esta vista contiene un gráfico y una tabla de datos configurada con los filtros siguientes:</span><span class="sxs-lookup"><span data-stu-id="a1bba-290">If you click the **Funnel** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="a1bba-291">**Fecha:** los últimos 7 días.</span><span class="sxs-lookup"><span data-stu-id="a1bba-291">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="a1bba-292">**Dirección**:</span><span class="sxs-lookup"><span data-stu-id="a1bba-292">**Direction**:</span></span>

  - <span data-ttu-id="a1bba-293">**Entrante**</span><span class="sxs-lookup"><span data-stu-id="a1bba-293">**Inbound**</span></span>
  - <span data-ttu-id="a1bba-294">**Saliente**</span><span class="sxs-lookup"><span data-stu-id="a1bba-294">**Outbound**</span></span>
  - <span data-ttu-id="a1bba-295">**Intra-org:** este recuento es para los mensajes enviados dentro de un espacio empresarial; Es decir, el remitente abc@domain.com al destinatario xyz@domain.com (se cuenta por separado de Entrante y Saliente).</span><span class="sxs-lookup"><span data-stu-id="a1bba-295">**Intra-org**: This count is for messages sent within a tenant; i.e, sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound).</span></span>

<span data-ttu-id="a1bba-296">La vista de agregado y la vista de tabla de datos permiten 90 días de filtrado.</span><span class="sxs-lookup"><span data-stu-id="a1bba-296">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="a1bba-297">Si hace clic **en Filtrar,** puede filtrar tanto el gráfico como la tabla de datos.</span><span class="sxs-lookup"><span data-stu-id="a1bba-297">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="a1bba-298">Este gráfico muestra el recuento de correo electrónico organizado por:</span><span class="sxs-lookup"><span data-stu-id="a1bba-298">This chart shows the email count organized by:</span></span>

- <span data-ttu-id="a1bba-299">**Correo electrónico total**</span><span class="sxs-lookup"><span data-stu-id="a1bba-299">**Total email**</span></span>
- <span data-ttu-id="a1bba-300">**Correo electrónico después de la protección perimetral**</span><span class="sxs-lookup"><span data-stu-id="a1bba-300">**Email after edge protection**</span></span>
- <span data-ttu-id="a1bba-301">**Correo electrónico después de antimalware, reputación de archivo, bloqueo de tipo de archivo**</span><span class="sxs-lookup"><span data-stu-id="a1bba-301">**Email after anti-malware, file reputation, file type block**</span></span>
- <span data-ttu-id="a1bba-302">**Correo electrónico después de anti phish, reputación url, suplantación de marca, anti suplantación de identidad**</span><span class="sxs-lookup"><span data-stu-id="a1bba-302">**Email after anti-phish, URL reputation, brand impersonation, anti-spoof**</span></span>
- <span data-ttu-id="a1bba-303">**Correo electrónico después de correo no deseado, filtrado masivo de correo**</span><span class="sxs-lookup"><span data-stu-id="a1bba-303">**Email after anti-spam, bulk mail filtering**</span></span>
- <span data-ttu-id="a1bba-304">**Correo electrónico después de la suplantación de usuario y dominio**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="a1bba-304">**Email after user and domain impersonation**<sup>1</sup></span></span>
- <span data-ttu-id="a1bba-305">**Email after file and URL detonation**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="a1bba-305">**Email after file and URL detonation**<sup>1</sup></span></span>
- <span data-ttu-id="a1bba-306">**Correo electrónico detectado como benigno después de la protección posterior a la entrega (url click time protection)**</span><span class="sxs-lookup"><span data-stu-id="a1bba-306">**Email detected as benign after post-delivery protection (URL click time protection)**</span></span>

<span data-ttu-id="a1bba-307"><sup>1</sup> Defender para Office 365 solo</span><span class="sxs-lookup"><span data-stu-id="a1bba-307"><sup>1</sup> Defender for Office 365 only</span></span>

<span data-ttu-id="a1bba-308">Para ver el correo electrónico filtrado por EOP o Defender Office 365 por separado, haga clic en el valor de la leyenda del gráfico.</span><span class="sxs-lookup"><span data-stu-id="a1bba-308">To view the email filtered by EOP or Defender for Office 365 separately, click on the value in the chart legend.</span></span>

<span data-ttu-id="a1bba-309">La tabla de datos contiene la siguiente información, que se muestra en orden de fecha descendente:</span><span class="sxs-lookup"><span data-stu-id="a1bba-309">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="a1bba-310">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="a1bba-310">**Date**</span></span>
- <span data-ttu-id="a1bba-311">**Correo electrónico total**</span><span class="sxs-lookup"><span data-stu-id="a1bba-311">**Total email**</span></span>
- <span data-ttu-id="a1bba-312">**Protección perimetral**</span><span class="sxs-lookup"><span data-stu-id="a1bba-312">**Edge protection**</span></span>
- <span data-ttu-id="a1bba-313">**Antimalware, reputación de archivo, bloque de tipo de archivo:**</span><span class="sxs-lookup"><span data-stu-id="a1bba-313">**Anti-malware, file reputation, file type block**:</span></span>
  - <span data-ttu-id="a1bba-314">**Reputación del archivo:** mensajes filtrados debido a la identificación de un archivo adjunto por otros clientes de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a1bba-314">**File reputation**: Messages filtered due to identification of an attached file by other Microsoft customers.</span></span>
  - <span data-ttu-id="a1bba-315">**Bloque de tipo de** archivo: mensajes filtrados debido al tipo de archivo malintencionado identificado en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="a1bba-315">**File type block**: Messages filtered due to the type of malicious file identified in the message.</span></span>
- <span data-ttu-id="a1bba-316">**Anti-phish, reputación url, suplantación de marca, suplantación de identidad:**</span><span class="sxs-lookup"><span data-stu-id="a1bba-316">**Anti-phish, URL reputation, Brand impersonation, anti-spoof**:</span></span>
  - <span data-ttu-id="a1bba-317">**Reputación de la dirección URL:** mensajes filtrados debido a la identificación de la dirección URL por otros clientes de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a1bba-317">**URL reputation**: Messages filtered due to the identification of the URL by other Microsoft customers.</span></span>
  - <span data-ttu-id="a1bba-318">**Suplantación de marca:** mensajes filtrados debido al mensaje procedente de remitentes de suplantación de marca conocidos.</span><span class="sxs-lookup"><span data-stu-id="a1bba-318">**Brand impersonation**: Messages filtered due to the message coming from well-known brand impersonating senders.</span></span>
  - <span data-ttu-id="a1bba-319">**Anti-spoof:** mensajes filtrados debido a que el mensaje intenta suplantar un dominio al que pertenece el destinatario o un dominio que el remitente del mensaje no posee.</span><span class="sxs-lookup"><span data-stu-id="a1bba-319">**Anti-spoof**: Messages filtered due to the message attempting to spoof a domain that the recipient belongs to, or a domain that the message sender doesn't own.</span></span>
- <span data-ttu-id="a1bba-320">**Antispam, filtrado masivo de correo:**</span><span class="sxs-lookup"><span data-stu-id="a1bba-320">**Anti-spam, bulk mail filtering**:</span></span>
  - <span data-ttu-id="a1bba-321">**Filtrado masivo de correo:** mensajes filtrados debido a un intento de entregar correo masivo a sus destinatarios.</span><span class="sxs-lookup"><span data-stu-id="a1bba-321">**Bulk mail filtering**: Messages filtered due to an attempt to deliver bulk mail to its recipients.</span></span>
- <span data-ttu-id="a1bba-322">**Suplantación de usuario y dominio (Defender para Office 365):**</span><span class="sxs-lookup"><span data-stu-id="a1bba-322">**User and domain impersonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="a1bba-323">Suplantación de **usuario:** mensajes filtrados debido a un intento de suplantar a un usuario (remitente de mensajes) que se define en la configuración de protección de suplantación de una directiva contra suplantación.</span><span class="sxs-lookup"><span data-stu-id="a1bba-323">**User impersonation**: Messages filtered due to an attempt to impersonate a user (message sender) that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
  - <span data-ttu-id="a1bba-324">**Suplantación** de dominio: mensajes filtrados debido a un intento de suplantar un dominio definido en la configuración de protección de suplantación de una directiva contra suplantación.</span><span class="sxs-lookup"><span data-stu-id="a1bba-324">**Domain impersonation**: Messages filtered due to an attempt to impersonate a domain that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
- <span data-ttu-id="a1bba-325">**Detonación de archivos y direcciones URL (Defender para Office 365):**</span><span class="sxs-lookup"><span data-stu-id="a1bba-325">**File and URL detonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="a1bba-326">**Detonación de archivos:** mensajes filtrados por una directiva Caja fuerte datos adjuntos.</span><span class="sxs-lookup"><span data-stu-id="a1bba-326">**File detonation**: Messages filtered by a Safe Attachments policy.</span></span>
  - <span data-ttu-id="a1bba-327">**Detonación de dirección URL:** mensaje filtrado por una directiva Caja fuerte vínculos.</span><span class="sxs-lookup"><span data-stu-id="a1bba-327">**URL detonation**: Message filtered by a Safe Links policy.</span></span>
- <span data-ttu-id="a1bba-328">**Protección posterior a la entrega y ZAP (ATP) o ZAP (EOP):** ZAP indica la purga automática de cero horas.</span><span class="sxs-lookup"><span data-stu-id="a1bba-328">**Post-delivery protection and ZAP (ATP), or ZAP (EOP)**: ZAP indicates zero hour auto-purge.</span></span>

<span data-ttu-id="a1bba-329">Si selecciona una fila en la tabla de datos, se muestra un desglose adicional de los recuentos de correo electrónico en el menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="a1bba-329">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="a1bba-330">**Exportar**:</span><span class="sxs-lookup"><span data-stu-id="a1bba-330">**Export**:</span></span>

<span data-ttu-id="a1bba-331">Después de hacer **clic en Exportar** en **Opciones,** puede seleccionar uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="a1bba-331">After you click **Export** under **Options**, you can select one of the following values:</span></span>

- <span data-ttu-id="a1bba-332">**Resumen (con datos de los últimos 90 días como máximo)**</span><span class="sxs-lookup"><span data-stu-id="a1bba-332">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="a1bba-333">**Detalles (con datos de los últimos 30 días como máximo)**</span><span class="sxs-lookup"><span data-stu-id="a1bba-333">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="a1bba-334">En **Fecha**, elija un rango y, a continuación, haga clic **en Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="a1bba-334">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="a1bba-335">Los datos de los filtros actuales se exportarán a un .csv archivo.</span><span class="sxs-lookup"><span data-stu-id="a1bba-335">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="a1bba-336">Cada archivo .csv exportada está limitado a 150 000 filas.</span><span class="sxs-lookup"><span data-stu-id="a1bba-336">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="a1bba-337">Si los datos contienen más de 150 000 filas, se crearán varios .csv archivos.</span><span class="sxs-lookup"><span data-stu-id="a1bba-337">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![Vista embudo en el informe de estado de flujo de correo](../../media/mail-flow-status-report-funnel-view.png)

### <a name="tech-view-for-the-mailflow-status-report"></a><span data-ttu-id="a1bba-339">Vista técnica del informe de estado del flujo de correo</span><span class="sxs-lookup"><span data-stu-id="a1bba-339">Tech view for the Mailflow status report</span></span>

<span data-ttu-id="a1bba-340">La **vista Tech es** similar a la vista **Embudo,** lo que proporciona más detalles pormenorizados para las características de protección contra amenazas configuradas.</span><span class="sxs-lookup"><span data-stu-id="a1bba-340">The **Tech view** is similar to the **Funnel** view, providing more granular details for the configured threat protections features.</span></span> <span data-ttu-id="a1bba-341">En el gráfico, puede ver cómo se clasifican los mensajes en las distintas etapas de protección contra amenazas.</span><span class="sxs-lookup"><span data-stu-id="a1bba-341">From the chart, you can see how messages are categorized at the different stages of threat protection.</span></span>

<span data-ttu-id="a1bba-342">Si hace clic en la **pestaña Vista técnica,** de forma predeterminada, esta vista contiene un gráfico y una tabla de datos configurada con los filtros siguientes:</span><span class="sxs-lookup"><span data-stu-id="a1bba-342">If you click the **Tech view** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="a1bba-343">**Fecha:** los últimos 7 días.</span><span class="sxs-lookup"><span data-stu-id="a1bba-343">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="a1bba-344">**Dirección**:</span><span class="sxs-lookup"><span data-stu-id="a1bba-344">**Direction**:</span></span>

  - <span data-ttu-id="a1bba-345">**Entrante**</span><span class="sxs-lookup"><span data-stu-id="a1bba-345">**Inbound**</span></span>
  - <span data-ttu-id="a1bba-346">**Saliente**</span><span class="sxs-lookup"><span data-stu-id="a1bba-346">**Outbound**</span></span>
  - <span data-ttu-id="a1bba-347">**Intra-org:** este recuento es para mensajes dentro de un espacio empresarial, es decir,</span><span class="sxs-lookup"><span data-stu-id="a1bba-347">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="a1bba-348">remitente abc@domain.com al destinatario xyz@domain.com (se cuenta por separado de Entrante y Saliente)</span><span class="sxs-lookup"><span data-stu-id="a1bba-348">sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound)</span></span>

<span data-ttu-id="a1bba-349">La vista de agregado y la vista de tabla de datos permiten 90 días de filtrado.</span><span class="sxs-lookup"><span data-stu-id="a1bba-349">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="a1bba-350">Si hace clic **en Filtrar,** puede filtrar tanto el gráfico como la tabla de datos.</span><span class="sxs-lookup"><span data-stu-id="a1bba-350">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="a1bba-351">En este gráfico se muestran los mensajes organizados en las siguientes categorías:</span><span class="sxs-lookup"><span data-stu-id="a1bba-351">This chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="a1bba-352">**Correo electrónico total**</span><span class="sxs-lookup"><span data-stu-id="a1bba-352">**Total email**</span></span>
- <span data-ttu-id="a1bba-353">**Edge allow** y **Edge filtered**</span><span class="sxs-lookup"><span data-stu-id="a1bba-353">**Edge allow** and **Edge filtered**</span></span>
- <span data-ttu-id="a1bba-354">**No malware**, **Caja fuerte attachments detection**, <sup>\*</sup> **Anti-malware engine detection** y Rule **messages**</span><span class="sxs-lookup"><span data-stu-id="a1bba-354">**Not malware**, **Safe Attachments detection**<sup>\*</sup>, **Anti-malware engine detection**, and **Rule messages**</span></span>
- <span data-ttu-id="a1bba-355">**No phish**, **error DMARC,** **detección de suplantación,** detección **de suplantación** y detección **de suplantación** de identidad</span><span class="sxs-lookup"><span data-stu-id="a1bba-355">**Not phish**, **DMARC failure**, **Impersonation detection**, **Spoof detection**, and **Phish detection**</span></span>
- <span data-ttu-id="a1bba-356">**No hay detección con detonación de dirección URL** y **detonación de url**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a1bba-356">**No detection with URL detonation** and **URL detonation detection**<sup>\*</sup></span></span>
- <span data-ttu-id="a1bba-357">**No correo no** deseado y  **correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="a1bba-357">**Not spam** and  **Spam**</span></span>
- <span data-ttu-id="a1bba-358">**Correo electrónico no malintencionado,** **Caja fuerte de detección de vínculos y** <sup>\*</sup> **ZAP**</span><span class="sxs-lookup"><span data-stu-id="a1bba-358">**Non-malicious email**, **Safe Links detection**<sup>\*</sup>, and **ZAP**</span></span>

<span data-ttu-id="a1bba-359"><sup>\*</sup>Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="a1bba-359"><sup>\*</sup> Defender for Office 365</span></span>

<span data-ttu-id="a1bba-360">Al pasar el mouse sobre una categoría del gráfico, puede ver el número de mensajes de esa categoría.</span><span class="sxs-lookup"><span data-stu-id="a1bba-360">When you hover over a category in the chart, you can see the number of messages in that category.</span></span>

<span data-ttu-id="a1bba-361">La tabla de datos contiene la siguiente información, que se muestra en orden de fecha descendente:</span><span class="sxs-lookup"><span data-stu-id="a1bba-361">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="a1bba-362">**Fecha**</span><span class="sxs-lookup"><span data-stu-id="a1bba-362">**Date**</span></span>
- <span data-ttu-id="a1bba-363">**Correo electrónico total**</span><span class="sxs-lookup"><span data-stu-id="a1bba-363">**Total email**</span></span>
- <span data-ttu-id="a1bba-364">**Perímetro filtrado**</span><span class="sxs-lookup"><span data-stu-id="a1bba-364">**Edge filtered**</span></span>
- <span data-ttu-id="a1bba-365">**Motor antimalware, Caja fuerte datos adjuntos, regla filtrada:**</span><span class="sxs-lookup"><span data-stu-id="a1bba-365">**Anti-malware engine, Safe Attachments, rule filtered**:</span></span>
  - <span data-ttu-id="a1bba-366">**Regla filtrada:** mensajes filtrados debido a reglas de flujo de correo (también conocidas como reglas de transporte).</span><span class="sxs-lookup"><span data-stu-id="a1bba-366">**Rule filtered**: Messages filtered due to  mail flow rules (also known as transport rules).</span></span>
- <span data-ttu-id="a1bba-367">**DMARC, suplantación, suplantación, suplantación de identidad filtrada:**</span><span class="sxs-lookup"><span data-stu-id="a1bba-367">**DMARC, impersonation, spoof, phish filtered**:</span></span>
  - <span data-ttu-id="a1bba-368">**DMARC:** mensajes filtrados debido a que el mensaje no ha fallado en la comprobación de autenticación de DMARC.</span><span class="sxs-lookup"><span data-stu-id="a1bba-368">**DMARC**: Messages filtered due to the message failing its DMARC authentication check.</span></span>
- <span data-ttu-id="a1bba-369">**Detección de detonación de url**</span><span class="sxs-lookup"><span data-stu-id="a1bba-369">**URL detonation detection**</span></span>
- <span data-ttu-id="a1bba-370">**Filtrado contra correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="a1bba-370">**Anti-spam filtered**</span></span>
- <span data-ttu-id="a1bba-371">**ZAP quitado**</span><span class="sxs-lookup"><span data-stu-id="a1bba-371">**ZAP removed**</span></span>
- <span data-ttu-id="a1bba-372">**Detección por Caja fuerte vínculos**</span><span class="sxs-lookup"><span data-stu-id="a1bba-372">**Detection by Safe Links**</span></span>

<span data-ttu-id="a1bba-373">Si selecciona una fila en la tabla de datos, se muestra un desglose adicional de los recuentos de correo electrónico en el menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="a1bba-373">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="a1bba-374">**Exportar**:</span><span class="sxs-lookup"><span data-stu-id="a1bba-374">**Export**:</span></span>

<span data-ttu-id="a1bba-375">Al hacer **clic en** Exportar , en **Opciones,** puede seleccionar uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="a1bba-375">On clicking **Export**, under **Options** you can select one of the following values:</span></span>

- <span data-ttu-id="a1bba-376">**Resumen (con datos de los últimos 90 días como máximo)**</span><span class="sxs-lookup"><span data-stu-id="a1bba-376">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="a1bba-377">**Detalles (con datos de los últimos 30 días como máximo)**</span><span class="sxs-lookup"><span data-stu-id="a1bba-377">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="a1bba-378">En **Fecha**, elija un rango y, a continuación, haga clic **en Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="a1bba-378">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="a1bba-379">Los datos de los filtros actuales se exportarán a un .csv archivo.</span><span class="sxs-lookup"><span data-stu-id="a1bba-379">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="a1bba-380">Cada archivo .csv exportada está limitado a 150 000 filas.</span><span class="sxs-lookup"><span data-stu-id="a1bba-380">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="a1bba-381">Si los datos contienen más de 150 000 filas, se crearán varios .csv archivos.</span><span class="sxs-lookup"><span data-stu-id="a1bba-381">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![Vista técnica en el informe de estado del flujo de correo](../../media/mail-flow-status-report-Tech-view.png)

## <a name="sent-and-received-email-report"></a><span data-ttu-id="a1bba-383">Informe de correo electrónico enviado y recibido</span><span class="sxs-lookup"><span data-stu-id="a1bba-383">Sent and received email report</span></span>

<span data-ttu-id="a1bba-384">El **informe de correo electrónico** enviado y recibido es un informe inteligente que muestra información sobre el correo electrónico entrante y saliente, incluidas detecciones de correo no deseado, malware y correo electrónico identificado como "bueno".</span><span class="sxs-lookup"><span data-stu-id="a1bba-384">The **Sent and received email** report is a smart report that shows information about incoming and outgoing email, including spam detections, malware, and email identified as "good."</span></span> <span data-ttu-id="a1bba-385">La diferencia entre este informe y el informe de estado [de flujo](#mailflow-status-report) de correo es: este informe no incluye datos sobre los mensajes bloqueados por la protección perimetral.</span><span class="sxs-lookup"><span data-stu-id="a1bba-385">The difference between this report and the [Mailflow status report](#mailflow-status-report) is: this report doesn't include data about messages blocked by edge protection.</span></span>

<span data-ttu-id="a1bba-386">**Nota:** Es importante comprender que si un mensaje se envía a cinco destinatarios, lo contamos como un mensaje.</span><span class="sxs-lookup"><span data-stu-id="a1bba-386">**Note**: It's important to understand that if a message is sent to five recipients we count it as one message.</span></span>

<span data-ttu-id="a1bba-387">La vista de agregado y la vista de detalles del informe permiten 90 días de filtrado.</span><span class="sxs-lookup"><span data-stu-id="a1bba-387">The aggregate view and the detail view of the report allow for 90 days of filtering.</span></span>

<span data-ttu-id="a1bba-388">Para ver el informe, abra el Centro de  [seguridad & cumplimiento,](https://protection.office.com)vaya al Panel de informes y seleccione Correo electrónico enviado \>  y **recibido.**</span><span class="sxs-lookup"><span data-stu-id="a1bba-388">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Sent and received email**.</span></span> <span data-ttu-id="a1bba-389">Para ir directamente al informe, abra <https://protection.office.com/reportv2?id=SentAndReceivedMailATP> .</span><span class="sxs-lookup"><span data-stu-id="a1bba-389">To go directly to the report, open <https://protection.office.com/reportv2?id=SentAndReceivedMailATP>.</span></span>

![Widget de correo electrónico enviado y recibido en el panel Informes](../../media/sent-and-received-email-report-widget.png)

### <a name="report-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="a1bba-391">Vista Informe para el informe de correo electrónico enviado y recibido</span><span class="sxs-lookup"><span data-stu-id="a1bba-391">Report view for the Sent and received email report</span></span>

<span data-ttu-id="a1bba-392">Los gráficos siguientes están disponibles en la vista informe:</span><span class="sxs-lookup"><span data-stu-id="a1bba-392">The following charts are available in the report view:</span></span>

- <span data-ttu-id="a1bba-393">**Dividir por: Tipo**: El gráfico muestra todas las categorías disponibles:</span><span class="sxs-lookup"><span data-stu-id="a1bba-393">**Break down by: Type**: The chart shows all available categories:</span></span>

  - <span data-ttu-id="a1bba-394">**Total**</span><span class="sxs-lookup"><span data-stu-id="a1bba-394">**Total**</span></span>
  - <span data-ttu-id="a1bba-395">**Correo bueno**</span><span class="sxs-lookup"><span data-stu-id="a1bba-395">**Good mail**</span></span>
  - <span data-ttu-id="a1bba-396">**Malware (antimalware)** (EOP)</span><span class="sxs-lookup"><span data-stu-id="a1bba-396">**Malware (anti-malware)** (EOP)</span></span>
  - <span data-ttu-id="a1bba-397">**Detecciones de correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="a1bba-397">**Spam detections**</span></span>
  - <span data-ttu-id="a1bba-398">**Mensajes de regla**</span><span class="sxs-lookup"><span data-stu-id="a1bba-398">**Rule messages**</span></span>
  - <span data-ttu-id="a1bba-399">**Malware avanzado** (Microsoft Defender para Office 365)</span><span class="sxs-lookup"><span data-stu-id="a1bba-399">**Advanced malware** (Microsoft Defender for Office 365)</span></span>

  <span data-ttu-id="a1bba-400">Cuando mantiene el mouse sobre un día (punto de datos) en el gráfico, puede ver los detalles de ese día.</span><span class="sxs-lookup"><span data-stu-id="a1bba-400">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![Vista de tipo en el informe de correo electrónico enviado y recibido](../../media/sent-and-received-email-report-type-view.png)

- <span data-ttu-id="a1bba-402">**Dividir por: Dirección:** el gráfico muestra **datos totales,** **entrantes** **y salientes.**</span><span class="sxs-lookup"><span data-stu-id="a1bba-402">**Break down by: Direction**: The chart shows **Total**, **Inbound**, and **Outbound** data.</span></span> <span data-ttu-id="a1bba-403">Cuando mantiene el mouse sobre un día (punto de datos) en el gráfico, puede ver los detalles de ese día.</span><span class="sxs-lookup"><span data-stu-id="a1bba-403">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![Vista Dirección en el informe de correo electrónico enviado y recibido](../../media/sent-and-received-email-report-direction-view.png)

- <span data-ttu-id="a1bba-405">**Explorar en profundidad** \> **Malware (antimalware):** esta selección le lleva al informe [de detecciones de malware](view-email-security-reports.md#malware-detections-report).</span><span class="sxs-lookup"><span data-stu-id="a1bba-405">**Drill down by** \> **Malware (anti-malware)**: This selection takes you to the [Malware detections report](view-email-security-reports.md#malware-detections-report).</span></span>

- <span data-ttu-id="a1bba-406">**Explorar en profundidad** \> **Detecciones de correo** no deseado): esta selección le lleva al informe Detecciones [de correo no deseado](view-email-security-reports.md#spam-detections-report).</span><span class="sxs-lookup"><span data-stu-id="a1bba-406">**Drill down by** \> **Spam detections)**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="a1bba-407">Si hace clic **en Filtros** en una vista de informe, puede modificar los resultados con los filtros siguientes:</span><span class="sxs-lookup"><span data-stu-id="a1bba-407">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="a1bba-408">**Fecha de inicio** y **fecha de finalización**</span><span class="sxs-lookup"><span data-stu-id="a1bba-408">**Start date** and **End date**</span></span>
- <span data-ttu-id="a1bba-409">Valores de dirección</span><span class="sxs-lookup"><span data-stu-id="a1bba-409">Direction values</span></span>
- <span data-ttu-id="a1bba-410">Valores de tipo</span><span class="sxs-lookup"><span data-stu-id="a1bba-410">Type values</span></span>

<span data-ttu-id="a1bba-411">Para volver a la vista informe, haga clic **en Ver informe**.</span><span class="sxs-lookup"><span data-stu-id="a1bba-411">To go back to the report view, click **View report**.</span></span>

### <a name="details-table-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="a1bba-412">Vista de tabla De detalles para el informe de correo electrónico enviado y recibido</span><span class="sxs-lookup"><span data-stu-id="a1bba-412">Details table view for the Sent and received email report</span></span>

<span data-ttu-id="a1bba-413">Si hace clic **en Ver tabla de detalles** en la vista Dividir **por:** Dirección o Dividir **por: Dirección,** se muestra la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="a1bba-413">If you click **View details table** in the **Break down by: Direction** or **Break down by: Direction** view, the following information is shown:</span></span>

- <span data-ttu-id="a1bba-414">**Fecha (UTC)**</span><span class="sxs-lookup"><span data-stu-id="a1bba-414">**Date (UTC)**</span></span>
- <span data-ttu-id="a1bba-415">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="a1bba-415">**Type**</span></span>
- <span data-ttu-id="a1bba-416">**Dirección**</span><span class="sxs-lookup"><span data-stu-id="a1bba-416">**Direction**</span></span>
- <span data-ttu-id="a1bba-417">**Recuento de mensajes**</span><span class="sxs-lookup"><span data-stu-id="a1bba-417">**Message count**</span></span>

<span data-ttu-id="a1bba-418">Si hace clic **en Filtros en** una vista de tabla de detalles, puede modificar los resultados con los filtros siguientes:</span><span class="sxs-lookup"><span data-stu-id="a1bba-418">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="a1bba-419">**Fecha de inicio** y **fecha de finalización**</span><span class="sxs-lookup"><span data-stu-id="a1bba-419">**Start date** and **End date**</span></span>
- <span data-ttu-id="a1bba-420">Valores de dirección</span><span class="sxs-lookup"><span data-stu-id="a1bba-420">Direction values</span></span>
- <span data-ttu-id="a1bba-421">Valores de tipo</span><span class="sxs-lookup"><span data-stu-id="a1bba-421">Type values</span></span>

<span data-ttu-id="a1bba-422">Para volver a la vista informe, haga clic **en Ver informe**.</span><span class="sxs-lookup"><span data-stu-id="a1bba-422">To go back to the report view, click **View report**.</span></span>

## <a name="top-senders-and-recipients-report"></a><span data-ttu-id="a1bba-423">Informe de remitentes y destinatarios principales</span><span class="sxs-lookup"><span data-stu-id="a1bba-423">Top senders and recipients report</span></span>

<span data-ttu-id="a1bba-424">El **informe Principales remitentes y destinatarios** es un gráfico circular que muestra los principales remitentes y destinatarios de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="a1bba-424">The **Top senders and recipients** report is a pie chart showing your top email senders and recipients.</span></span>

<span data-ttu-id="a1bba-425">Para ver el informe, abra el Centro de  [seguridad & cumplimiento,](https://protection.office.com)vaya al Panel de informes y seleccione Principales \>  **remitentes y destinatarios.**</span><span class="sxs-lookup"><span data-stu-id="a1bba-425">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top senders and recipients**.</span></span> <span data-ttu-id="a1bba-426">Para ir directamente al informe, abra <https://protection.office.com/reportv2?id=TopSenderRecipientsATP> .</span><span class="sxs-lookup"><span data-stu-id="a1bba-426">To go directly to the report, open <https://protection.office.com/reportv2?id=TopSenderRecipientsATP>.</span></span>

![Widget Principales remitentes y destinatarios en el panel Informes](../../media/top-senders-and-recipients-widget.png)

### <a name="report-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="a1bba-428">Vista Informe para el informe de destinatarios y remitentes principales</span><span class="sxs-lookup"><span data-stu-id="a1bba-428">Report view for the Top senders and recipient report</span></span>

<span data-ttu-id="a1bba-429">Los gráficos siguientes están disponibles en la vista informe:</span><span class="sxs-lookup"><span data-stu-id="a1bba-429">The following charts are available in the report view:</span></span>

- <span data-ttu-id="a1bba-430">**Mostrar datos para \> los principales remitentes de correo**</span><span class="sxs-lookup"><span data-stu-id="a1bba-430">**Show data for \> Top mail senders**</span></span>
- <span data-ttu-id="a1bba-431">**Mostrar datos para \> los principales destinatarios de correo**</span><span class="sxs-lookup"><span data-stu-id="a1bba-431">**Show data for \> Top mail recipients**</span></span>
- <span data-ttu-id="a1bba-432">**Mostrar datos para los \> principales destinatarios de correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="a1bba-432">**Show data for \> Top spam recipients**</span></span>
- <span data-ttu-id="a1bba-433">**Mostrar datos para \> Principales destinatarios de malware** (EOP)</span><span class="sxs-lookup"><span data-stu-id="a1bba-433">**Show data for \> Top malware recipients** (EOP)</span></span>
- <span data-ttu-id="a1bba-434">**Mostrar datos para \> los destinatarios principales de malware (Defender para Office 365)**</span><span class="sxs-lookup"><span data-stu-id="a1bba-434">**Show data for \> Top malware recipients (Defender for Office 365)**</span></span>

<span data-ttu-id="a1bba-435">La composición del gráfico circular cambia en función de estas selecciones.</span><span class="sxs-lookup"><span data-stu-id="a1bba-435">The composition of the pie chart changes based on these selections.</span></span>

<span data-ttu-id="a1bba-436">Al pasar el mouse sobre una cuña en el gráfico circular, puede ver un recuento de mensajes enviados o recibidos.</span><span class="sxs-lookup"><span data-stu-id="a1bba-436">When you hover over a wedge in the pie chart, you can see a count of messages sent or received.</span></span>

<span data-ttu-id="a1bba-437">Si hace clic **en Filtros** en una vista de informe, puede especificar un intervalo de fechas con Fecha **de inicio** y Fecha **de finalización.**</span><span class="sxs-lookup"><span data-stu-id="a1bba-437">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

![Gráfico circular en la vista Informe del informe Principales remitentes y destinatarios](../../media/top-senders-and-recipients-report-view.png)

### <a name="details-table-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="a1bba-439">Vista de tabla Detalles para el informe de destinatarios y remitentes principales</span><span class="sxs-lookup"><span data-stu-id="a1bba-439">Details table view for the Top senders and recipient report</span></span>

<span data-ttu-id="a1bba-440">Si hace clic **en Ver tabla de detalles,** la información que se muestra depende del gráfico que estaba mirando:</span><span class="sxs-lookup"><span data-stu-id="a1bba-440">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="a1bba-441">**Mostrar datos para \> los principales remitentes de correo**</span><span class="sxs-lookup"><span data-stu-id="a1bba-441">**Show data for \> Top mail senders**</span></span>

  - <span data-ttu-id="a1bba-442">**Principales remitentes de correo**</span><span class="sxs-lookup"><span data-stu-id="a1bba-442">**Top mail senders**</span></span>
  - <span data-ttu-id="a1bba-443">**Count**</span><span class="sxs-lookup"><span data-stu-id="a1bba-443">**Count**</span></span>

- <span data-ttu-id="a1bba-444">**Mostrar datos para \> los principales destinatarios de correo**</span><span class="sxs-lookup"><span data-stu-id="a1bba-444">**Show data for \> Top mail recipients**</span></span>

  - <span data-ttu-id="a1bba-445">**Principales destinatarios de correo**</span><span class="sxs-lookup"><span data-stu-id="a1bba-445">**Top mail recipients**</span></span>
  - <span data-ttu-id="a1bba-446">**Count**</span><span class="sxs-lookup"><span data-stu-id="a1bba-446">**Count**</span></span>

- <span data-ttu-id="a1bba-447">**Mostrar datos para los \> principales destinatarios de correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="a1bba-447">**Show data for \> Top spam recipients**</span></span>

  - <span data-ttu-id="a1bba-448">**Principales destinatarios de correo no deseado**</span><span class="sxs-lookup"><span data-stu-id="a1bba-448">**Top spam recipients**</span></span>
  - <span data-ttu-id="a1bba-449">**Count**</span><span class="sxs-lookup"><span data-stu-id="a1bba-449">**Count**</span></span>

- <span data-ttu-id="a1bba-450">**Mostrar datos para \> Principales destinatarios de malware** (EOP)</span><span class="sxs-lookup"><span data-stu-id="a1bba-450">**Show data for \> Top malware recipients** (EOP)</span></span>

  - <span data-ttu-id="a1bba-451">**Principales destinatarios de malware**</span><span class="sxs-lookup"><span data-stu-id="a1bba-451">**Top malware recipients**</span></span>
  - <span data-ttu-id="a1bba-452">**Count**</span><span class="sxs-lookup"><span data-stu-id="a1bba-452">**Count**</span></span>

- <span data-ttu-id="a1bba-453">**Mostrar datos para \> los destinatarios principales de malware (Defender para Office 365)**</span><span class="sxs-lookup"><span data-stu-id="a1bba-453">**Show data for \> Top malware recipients (Defender for Office 365)**</span></span>

  - <span data-ttu-id="a1bba-454">**Principales destinatarios de malware (Defender para Office 365)**</span><span class="sxs-lookup"><span data-stu-id="a1bba-454">**Top malware recipients (Defender for Office 365)**</span></span>
  - <span data-ttu-id="a1bba-455">**Count**</span><span class="sxs-lookup"><span data-stu-id="a1bba-455">**Count**</span></span>

<span data-ttu-id="a1bba-456">Si hace clic **en Filtros en** una vista de tabla de detalles, puede especificar un intervalo de fechas con Fecha de **inicio** y Fecha **de finalización.**</span><span class="sxs-lookup"><span data-stu-id="a1bba-456">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="a1bba-457">Para volver a la vista informe, haga clic **en Ver informe**.</span><span class="sxs-lookup"><span data-stu-id="a1bba-457">To go back to the report view, click **View report**.</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="a1bba-458">¿Qué permisos se necesitan para ver estos informes?</span><span class="sxs-lookup"><span data-stu-id="a1bba-458">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="a1bba-459">Para ver y usar los informes descritos en este artículo, debe ser miembro de uno de los siguientes grupos de roles en el Centro de seguridad & cumplimiento:</span><span class="sxs-lookup"><span data-stu-id="a1bba-459">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Security & Compliance Center:</span></span>

- <span data-ttu-id="a1bba-460">**Administración de organizaciones**</span><span class="sxs-lookup"><span data-stu-id="a1bba-460">**Organization Management**</span></span>
- <span data-ttu-id="a1bba-461">**Administrador de seguridad**</span><span class="sxs-lookup"><span data-stu-id="a1bba-461">**Security Administrator**</span></span>
- <span data-ttu-id="a1bba-462">**Lector de seguridad**</span><span class="sxs-lookup"><span data-stu-id="a1bba-462">**Security Reader**</span></span>
- <span data-ttu-id="a1bba-463">**Lector global**</span><span class="sxs-lookup"><span data-stu-id="a1bba-463">**Global Reader**</span></span>

<span data-ttu-id="a1bba-464">Para obtener más información, vea [Permisos en el Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="a1bba-464">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

> [!NOTE]
> <span data-ttu-id="a1bba-465">Agregar usuarios al rol correspondiente de Azure Active Directory en el Centro de administración de Microsoft 365 otorga a los usuarios los permisos necesarios en el Centro de seguridad y cumplimiento _y_ permisos para otras características de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a1bba-465">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="a1bba-466">Para obtener más información, vea [Sobre los roles de administrador](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="a1bba-466">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="a1bba-467">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="a1bba-467">Related topics</span></span>

[<span data-ttu-id="a1bba-468">Informes inteligentes y reportes en el Centro de seguridad y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="a1bba-468">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="a1bba-469">Reportes de flujo de Correo en el Centro de seguridad y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="a1bba-469">Mail flow insights in the Security & Compliance Center</span></span>](mail-flow-insights-v2.md)

[<span data-ttu-id="a1bba-470">Ver informes de seguridad de correo electrónico en el Centro de seguridad y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="a1bba-470">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)

[<span data-ttu-id="a1bba-471">Ver informes de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="a1bba-471">View reports for Microsoft Defender for Office 365</span></span>](view-reports-for-mdo.md)
