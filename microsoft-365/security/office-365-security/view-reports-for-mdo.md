---
title: Ver informes de Defender para Office 365
f1.keywords:
- CSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e47e838c-d99e-4c0b-b9aa-e66c4fae902f
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Los administradores pueden aprender a buscar y usar defender para Office 365 informes que están disponibles en el portal Microsoft 365 Defender web.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5b9279614571c123ad92f1684f86175b410c6c5c
ms.sourcegitcommit: bc64d9f619259bd0a94e43a9010aae5cffb4d6c4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2021
ms.locfileid: "53022861"
---
# <a name="view-defender-for-office-365-reports-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="f7111-103">Ver Defender para obtener Office 365 informes en el portal Microsoft 365 Defender web</span><span class="sxs-lookup"><span data-stu-id="f7111-103">View Defender for Office 365 reports in the Microsoft 365 Defender portal</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="f7111-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="f7111-104">**Applies to**</span></span>
- [<span data-ttu-id="f7111-105">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="f7111-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="f7111-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f7111-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="f7111-107">Microsoft Defender para organizaciones Office 365 (por ejemplo, suscripciones Microsoft 365 E5 o Microsoft Defender para Office 365 Plan 1 o Microsoft Defender para complementos del Plan 2 de Office 365) contienen una variedad de informes relacionados con la seguridad.</span><span class="sxs-lookup"><span data-stu-id="f7111-107">Microsoft Defender for Office 365 organizations (for example, Microsoft 365 E5 subscriptions or Microsoft Defender for Office 365 Plan 1 or Microsoft Defender for Office 365 Plan 2 add-ons) contain a variety of security-related reports.</span></span> <span data-ttu-id="f7111-108">Si tiene los [permisos](#what-permissions-are-needed-to-view-the-defender-for-office-365-reports)necesarios, puede ver estos informes en el  portal de Microsoft 365 Defender yendo a Informes de correo electrónico & colaboración Correo electrónico & informes \>  \> **de colaboración**.</span><span class="sxs-lookup"><span data-stu-id="f7111-108">If you have the [necessary permissions](#what-permissions-are-needed-to-view-the-defender-for-office-365-reports), you can view these reports in the Microsoft 365 Defender portal by going to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="f7111-109">Para ir directamente a la página **Informes de colaboración & correo** electrónico, abra <https://security.microsoft.com/emailandcollabreport> .</span><span class="sxs-lookup"><span data-stu-id="f7111-109">To go directly to the **Email & collaboration reports** page, open <https://security.microsoft.com/emailandcollabreport>.</span></span>

![Página & informes de colaboración de correo electrónico en el portal de Microsoft 365 Defender web](../../media/email-collaboration-reports.png)

> [!NOTE]
>
> <span data-ttu-id="f7111-111">Los informes de seguridad de correo electrónico que no requieren Defender para Office 365 se describen en Ver informes de seguridad de correo electrónico [en el portal Microsoft 365 Defender correo](view-email-security-reports.md)electrónico .</span><span class="sxs-lookup"><span data-stu-id="f7111-111">Email security reports that don't require Defender for Office 365 are described in [View email security reports in the Microsoft 365 Defender portal](view-email-security-reports.md).</span></span>
>
> <span data-ttu-id="f7111-112">Los informes relacionados con el flujo de correo se encuentran ahora en el Centro Exchange administración (EAC).</span><span class="sxs-lookup"><span data-stu-id="f7111-112">Reports that are related to mail flow are now in the Exchange admin center (EAC).</span></span> <span data-ttu-id="f7111-113">Para obtener más información acerca de estos informes, vea Informes de flujo de correo [en el nuevo centro Exchange administración.](/exchange/monitoring/mail-flow-reports/mail-flow-reports)</span><span class="sxs-lookup"><span data-stu-id="f7111-113">For more information about these reports, see [Mail flow reports in the new Exchange admin center](/exchange/monitoring/mail-flow-reports/mail-flow-reports).</span></span>

## <a name="safe-attachments-file-types-report"></a><span data-ttu-id="f7111-114">Caja fuerte Informe de tipos de archivo de datos adjuntos</span><span class="sxs-lookup"><span data-stu-id="f7111-114">Safe Attachments file types report</span></span>

> [!NOTE]
> <span data-ttu-id="f7111-115">El **informe Caja fuerte tipos de archivos adjuntos** desaparecerá finalmente.</span><span class="sxs-lookup"><span data-stu-id="f7111-115">The **Safe Attachments file types report** will eventually go away.</span></span> <span data-ttu-id="f7111-116">La misma información está disponible en el informe [de estado de protección contra amenazas](#threat-protection-status-report).</span><span class="sxs-lookup"><span data-stu-id="f7111-116">The same information is available in the [Threat protection status report](#threat-protection-status-report).</span></span>

## <a name="safe-attachments-message-disposition-report"></a><span data-ttu-id="f7111-117">Caja fuerte Informe de eliminación de mensajes de datos adjuntos</span><span class="sxs-lookup"><span data-stu-id="f7111-117">Safe Attachments message disposition report</span></span>

> [!NOTE]
> <span data-ttu-id="f7111-118">El **Caja fuerte de eliminación** de mensajes de datos adjuntos desaparecerá.</span><span class="sxs-lookup"><span data-stu-id="f7111-118">The **Safe Attachments message disposition report** will eventually go away.</span></span> <span data-ttu-id="f7111-119">La misma información está disponible en el informe [de estado de protección contra amenazas](#threat-protection-status-report).</span><span class="sxs-lookup"><span data-stu-id="f7111-119">The same information is available in the [Threat protection status report](#threat-protection-status-report).</span></span>

## <a name="mail-latency-report"></a><span data-ttu-id="f7111-120">Informe de latencia de correo</span><span class="sxs-lookup"><span data-stu-id="f7111-120">Mail latency report</span></span>

<span data-ttu-id="f7111-121">El **informe de latencia de** correo muestra una vista agregada de la latencia de entrega y detonación de correo experimentada en su organización.</span><span class="sxs-lookup"><span data-stu-id="f7111-121">The **Mail latency report** shows you an aggregate view of the mail delivery and detonation latency experienced within your organization.</span></span> <span data-ttu-id="f7111-122">Los tiempos de entrega de correo en el servicio se ven afectados por una serie de factores y el tiempo de entrega absoluto en segundos a menudo no es un buen indicador de éxito o un problema.</span><span class="sxs-lookup"><span data-stu-id="f7111-122">Mail delivery times in the service are affected by a number of factors, and the absolute delivery time in seconds is often not a good indicator of success or a problem.</span></span> <span data-ttu-id="f7111-123">Un tiempo de entrega lento en un día puede considerarse un promedio de tiempo de entrega en otro día, o viceversa.</span><span class="sxs-lookup"><span data-stu-id="f7111-123">A slow delivery time on one day might be considered an average delivery time on another day, or vice-versa.</span></span> <span data-ttu-id="f7111-124">Esto intenta calificar la entrega de mensajes en función de datos estadísticos sobre los tiempos de entrega observados de otros mensajes.</span><span class="sxs-lookup"><span data-stu-id="f7111-124">This tries to qualify message delivery based on statistical data about the observed delivery times of other messages.</span></span>

<span data-ttu-id="f7111-125">La latencia de red y del lado cliente no se incluyen.</span><span class="sxs-lookup"><span data-stu-id="f7111-125">Client side and network latency are not included.</span></span>

<span data-ttu-id="f7111-126">Para ver el informe, abra el [portal de Microsoft 365 Defender](https://security.microsoft.com), vaya a **Informes** de correo electrónico & \> **colaboración** Correo & \> **informes de colaboración.**</span><span class="sxs-lookup"><span data-stu-id="f7111-126">To view the report, open the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="f7111-127">En la página **Informes de colaboración &** correo electrónico, busque Informe de latencia **de** correo y, a continuación, haga clic en **Ver detalles**.</span><span class="sxs-lookup"><span data-stu-id="f7111-127">On the **Email & collaboration reports** page, find **Mail latency report** and then click **View details**.</span></span> <span data-ttu-id="f7111-128">Para ir directamente al informe, abra <https://security.microsoft.com/mailLatencyReport> .</span><span class="sxs-lookup"><span data-stu-id="f7111-128">To go directly to the report, open <https://security.microsoft.com/mailLatencyReport>.</span></span>

![Widget de informe de latencia de correo en la página Informes de colaboración & correo electrónico](../../media/mail-latency-report-widget.png)

<span data-ttu-id="f7111-130">En la **página Informe de latencia de** correo, las pestañas siguientes están disponibles en la página Informe de latencia **de** correo:</span><span class="sxs-lookup"><span data-stu-id="f7111-130">On the **Mail latency report** page, the following tabs are available on the **Mail latency report** page:</span></span>

- <span data-ttu-id="f7111-131">**Percentil 50:** este es el medio para los tiempos de entrega de mensajes.</span><span class="sxs-lookup"><span data-stu-id="f7111-131">**50th percentile**: This is the middle for message delivery times.</span></span> <span data-ttu-id="f7111-132">Puede considerar este valor como un tiempo medio de entrega.</span><span class="sxs-lookup"><span data-stu-id="f7111-132">You can consider this value as an average delivery time.</span></span> <span data-ttu-id="f7111-133">Esta pestaña está seleccionada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="f7111-133">This tab is selected by default.</span></span>
- <span data-ttu-id="f7111-134">**Percentil 90:** esto indica una latencia alta para la entrega de mensajes.</span><span class="sxs-lookup"><span data-stu-id="f7111-134">**90th percentile**: This indicates a high latency for message delivery.</span></span> <span data-ttu-id="f7111-135">Solo el 10 % de los mensajes tardaron más de este valor en entregarse.</span><span class="sxs-lookup"><span data-stu-id="f7111-135">Only 10% of messages took longer than this value to deliver.</span></span>
- <span data-ttu-id="f7111-136">**Percentil 99:** indica la latencia más alta para la entrega de mensajes.</span><span class="sxs-lookup"><span data-stu-id="f7111-136">**99th percentile**: This indicates the highest latency for message delivery.</span></span>

<span data-ttu-id="f7111-137">Independientemente de la pestaña que seleccione, el gráfico muestra los mensajes organizados en las siguientes categorías:</span><span class="sxs-lookup"><span data-stu-id="f7111-137">Regardless of the tab you select, the chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="f7111-138">**Latencia de entrega de correo**</span><span class="sxs-lookup"><span data-stu-id="f7111-138">**Mail delivery latency**</span></span>
- <span data-ttu-id="f7111-139">**Detonaciones**</span><span class="sxs-lookup"><span data-stu-id="f7111-139">**Detonations**</span></span>

<span data-ttu-id="f7111-140">Al pasar el mouse sobre una categoría del gráfico, puede ver un desglose de la latencia en cada categoría.</span><span class="sxs-lookup"><span data-stu-id="f7111-140">When you hover over a category in the chart, you can see a breakdown of the latency in each category.</span></span>

![Vista percentil 50 del informe de latencia de correo](../../media/mail-latency-report-50th-percentile-view.png)

<span data-ttu-id="f7111-142">Si hace clic **en Filtrar,** puede filtrar el gráfico y la tabla de detalles por los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="f7111-142">If you click **Filter**, you can filter both the chart and the details table by the following values:</span></span>

- <span data-ttu-id="f7111-143">**Fecha (UTC):** **fecha de inicio y** fecha de **finalización**</span><span class="sxs-lookup"><span data-stu-id="f7111-143">**Date (UTC)**: **Start date** and **End date**</span></span>
- <span data-ttu-id="f7111-144">**Vista de** mensaje: uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="f7111-144">**Message view**: One of the following values:</span></span>
  - <span data-ttu-id="f7111-145">**Todos los mensajes**</span><span class="sxs-lookup"><span data-stu-id="f7111-145">**All messages**</span></span>
  - <span data-ttu-id="f7111-146">**Mensajes que contienen datos adjuntos o direcciones URL**</span><span class="sxs-lookup"><span data-stu-id="f7111-146">**Messages that contain attachments or URLs**</span></span>
  - <span data-ttu-id="f7111-147">**Mensajes detonados**</span><span class="sxs-lookup"><span data-stu-id="f7111-147">**Detonated messages**</span></span>

<span data-ttu-id="f7111-148">Cuando haya terminado de configurar los filtros, haga clic **en Aplicar,** **Cancelar** o **Borrar filtros**.</span><span class="sxs-lookup"><span data-stu-id="f7111-148">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

<span data-ttu-id="f7111-149">En la tabla de detalles debajo del gráfico, está disponible la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="f7111-149">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="f7111-150">**Fecha (UTC)**</span><span class="sxs-lookup"><span data-stu-id="f7111-150">**Date (UTC)**</span></span>
- <span data-ttu-id="f7111-151">**Percentiles:** **50**, **90** o **99**</span><span class="sxs-lookup"><span data-stu-id="f7111-151">**Percentiles**: **50**, **90**, or **99**</span></span>
- <span data-ttu-id="f7111-152">**Recuento de mensajes**</span><span class="sxs-lookup"><span data-stu-id="f7111-152">**Message count**</span></span>
- <span data-ttu-id="f7111-153">**Latencia general**</span><span class="sxs-lookup"><span data-stu-id="f7111-153">**Overall latency**</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="f7111-154">Informe de estado de protección contra amenazas</span><span class="sxs-lookup"><span data-stu-id="f7111-154">Threat protection status report</span></span>

<span data-ttu-id="f7111-155">El **informe de estado** de protección contra amenazas es una única vista que reúne información sobre contenido malintencionado y correo electrónico malintencionado detectado y bloqueado por [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) y Microsoft Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="f7111-155">The **Threat protection status** report is a single view that brings together information about malicious content and malicious email detected and blocked by [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) and Microsoft Defender for Office 365.</span></span> <span data-ttu-id="f7111-156">Para obtener más información, vea [Informe de estado de protección contra amenazas](view-email-security-reports.md#threat-protection-status-report).</span><span class="sxs-lookup"><span data-stu-id="f7111-156">For more information, see [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>

## <a name="url-threat-protection-report"></a><span data-ttu-id="f7111-157">Informe de protección contra amenazas de url</span><span class="sxs-lookup"><span data-stu-id="f7111-157">URL threat protection report</span></span>

<span data-ttu-id="f7111-158">El **informe de protección contra** amenazas url proporciona vistas de resumen y tendencias para las amenazas detectadas y las acciones realizadas en los clics de dirección URL como parte de Caja fuerte [vínculos](safe-links.md).</span><span class="sxs-lookup"><span data-stu-id="f7111-158">The **URL threat protection report** provides summary and trend views for threats detected and actions taken on URL clicks as part of [Safe Links](safe-links.md).</span></span> <span data-ttu-id="f7111-159">Este informe no tendrá los datos de clic de los usuarios en los que la directiva de vínculos de Caja fuerte tiene seleccionada la opción No realizar seguimiento de los **clics del** usuario.</span><span class="sxs-lookup"><span data-stu-id="f7111-159">This report will not have click data from users where the Safe Links policy applied has the **Do not track user clicks** option selected.</span></span>

<span data-ttu-id="f7111-160">Para ver el informe, abra el [portal de Microsoft 365 Defender](https://security.microsoft.com), vaya a **Informes** de correo electrónico & \> **colaboración** Correo & \> **informes de colaboración.**</span><span class="sxs-lookup"><span data-stu-id="f7111-160">To view the report, open the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="f7111-161">En la página **Informes de colaboración &** correo electrónico, busque la página protección de direcciones **URL** y, a continuación, haga clic en **Ver detalles**.</span><span class="sxs-lookup"><span data-stu-id="f7111-161">On the **Email & collaboration reports** page, find **URL protection page** and then click **View details**.</span></span> <span data-ttu-id="f7111-162">Para ir directamente al informe, abra <https://security.microsoft.com/reports/URLProtectionActionReport> .</span><span class="sxs-lookup"><span data-stu-id="f7111-162">To go directly to the report, open <https://security.microsoft.com/reports/URLProtectionActionReport>.</span></span>

![Widget de informe de protección de direcciones URL en la página Informes de & de colaboración](../../media/url-protection-report-widget.png)

<span data-ttu-id="f7111-164">Las vistas disponibles en la página **informe de protección contra** amenazas de url se describen en las secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="f7111-164">The available views on the **URL threat protection** report page are described in the following sections.</span></span>

> [!NOTE]
> <span data-ttu-id="f7111-165">Se trata de un *informe de tendencias de protección,* lo que significa que los datos representan tendencias en un conjunto de datos más grande.</span><span class="sxs-lookup"><span data-stu-id="f7111-165">This is a *protection trend report*, meaning data represents trends in a larger dataset.</span></span> <span data-ttu-id="f7111-166">Como resultado, los datos de los gráficos no están disponibles en tiempo real aquí, pero los datos de la tabla de detalles lo son, por lo que puede ver una ligera discrepancia entre los dos.</span><span class="sxs-lookup"><span data-stu-id="f7111-166">As a result, the data in the charts is not available in real time here, but the data in the details table is, so you may see a slight discrepancy between the two.</span></span> <span data-ttu-id="f7111-167">Los gráficos se actualizan una vez cada cuatro horas y contienen datos de los últimos 90 días.</span><span class="sxs-lookup"><span data-stu-id="f7111-167">The charts are refreshed once every four hours and contain data for the last 90 days.</span></span>

### <a name="view-data-by-url-click-protection-action"></a><span data-ttu-id="f7111-168">Ver datos por acción de protección de clics de dirección URL</span><span class="sxs-lookup"><span data-stu-id="f7111-168">View data by URL click protection action</span></span>

![Vista de acción de protección de clic de url en el informe de protección contra amenazas de url](../../media/url-threat-protection-report-url-click-protection-action-view.png)

<span data-ttu-id="f7111-170">La **vista Ver datos por acción** de protección de clics de dirección URL muestra el número de clics de dirección URL de los usuarios de la organización y los resultados del clic:</span><span class="sxs-lookup"><span data-stu-id="f7111-170">The **View data by URL click protection action** view shows the number of URL clicks by users in the organization and the results of the click:</span></span>

- <span data-ttu-id="f7111-171">**Permitido:** se le permitió al usuario navegar a la dirección URL.</span><span class="sxs-lookup"><span data-stu-id="f7111-171">**Allowed**: The user was allowed to navigate to the URL.</span></span>
- <span data-ttu-id="f7111-172">**Bloqueado:** se bloqueó al usuario para que no navegara a la dirección URL.</span><span class="sxs-lookup"><span data-stu-id="f7111-172">**Blocked**: The user was blocked from navigating to the URL.</span></span>
- <span data-ttu-id="f7111-173">**Bloqueado y hecho clic en:** el usuario ha elegido continuar navegando a la dirección URL.</span><span class="sxs-lookup"><span data-stu-id="f7111-173">**Blocked and clicked through**: The user has chosen to continue navigating to the URL.</span></span>
- <span data-ttu-id="f7111-174">**Se ha hecho clic durante el examen:** el usuario ha hecho clic en el vínculo antes de completar el examen.</span><span class="sxs-lookup"><span data-stu-id="f7111-174">**Clicked through during scan**: The user has clicked on the link before the scan was complete.</span></span>

<span data-ttu-id="f7111-175">Un clic indica que el usuario ha hecho clic a través de la página de bloqueo en el sitio web malintencionado (los administradores pueden deshabilitar el clic en las directivas de vínculos Caja fuerte usuario).</span><span class="sxs-lookup"><span data-stu-id="f7111-175">A click indicates that the user has clicked through the block page to the malicious website (admins can disable click through in Safe Links policies).</span></span>

<span data-ttu-id="f7111-176">Si hace clic **en Filtros,** puede modificar el informe y la tabla de detalles seleccionando uno o varios de los siguientes valores en el menú desplegable que aparece:</span><span class="sxs-lookup"><span data-stu-id="f7111-176">If you click **Filters**, you can modify the report and the details table by selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="f7111-177">**Fecha (UTC):** **fecha de inicio y** fecha de **finalización**</span><span class="sxs-lookup"><span data-stu-id="f7111-177">**Date (UTC)**: **Start date** and **End date**</span></span>
- <span data-ttu-id="f7111-178">**Detección**:</span><span class="sxs-lookup"><span data-stu-id="f7111-178">**Detection**:</span></span>
  - <span data-ttu-id="f7111-179">**Permitido**</span><span class="sxs-lookup"><span data-stu-id="f7111-179">**Allowed**</span></span>
  - <span data-ttu-id="f7111-180">**Bloqueado**</span><span class="sxs-lookup"><span data-stu-id="f7111-180">**Blocked**</span></span>
  - <span data-ttu-id="f7111-181">**Bloqueado y hecho clic**</span><span class="sxs-lookup"><span data-stu-id="f7111-181">**Blocked and clicked through**</span></span>
  - <span data-ttu-id="f7111-182">**Se ha hecho clic durante el examen**</span><span class="sxs-lookup"><span data-stu-id="f7111-182">**Clicked through during scan**</span></span>
- <span data-ttu-id="f7111-183">**Dominios:** los dominios url enumerados en los resultados del informe.</span><span class="sxs-lookup"><span data-stu-id="f7111-183">**Domains**: The URL domains listed in the report results.</span></span>
- <span data-ttu-id="f7111-184">**Destinatarios**</span><span class="sxs-lookup"><span data-stu-id="f7111-184">**Recipients**</span></span>

<span data-ttu-id="f7111-185">Cuando haya terminado de configurar los filtros, haga clic **en Aplicar,** **Cancelar** o **Borrar filtros**.</span><span class="sxs-lookup"><span data-stu-id="f7111-185">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

<span data-ttu-id="f7111-186">La tabla de detalles debajo del gráfico proporciona la siguiente vista casi en tiempo real de todos los clics que se han producido en la organización durante los últimos 7 días:</span><span class="sxs-lookup"><span data-stu-id="f7111-186">The details table below the chart provides the following near-real-time view of all clicks that happened within the organization for the last 7 days:</span></span>

- <span data-ttu-id="f7111-187">**Hora de hacer clic**</span><span class="sxs-lookup"><span data-stu-id="f7111-187">**Click time**</span></span>
- <span data-ttu-id="f7111-188">**Usuario**</span><span class="sxs-lookup"><span data-stu-id="f7111-188">**User**</span></span>
- <span data-ttu-id="f7111-189">**URL**</span><span class="sxs-lookup"><span data-stu-id="f7111-189">**URL**</span></span>
- <span data-ttu-id="f7111-190">**Action**</span><span class="sxs-lookup"><span data-stu-id="f7111-190">**Action**</span></span>
- <span data-ttu-id="f7111-191">**Aplicación**</span><span class="sxs-lookup"><span data-stu-id="f7111-191">**App**</span></span>

### <a name="view-data-by-url-click-by-application"></a><span data-ttu-id="f7111-192">Ver datos por dirección URL hacer clic por aplicación</span><span class="sxs-lookup"><span data-stu-id="f7111-192">View data by URL click by application</span></span>

![Url click by application view in the URL threat protection report](../../media/url-threat-protection-report-url-click-by-application-view.png)

<span data-ttu-id="f7111-194">La **vista Ver datos por dirección URL clic** por aplicación muestra el número de clics de dirección URL de las aplicaciones que admiten Caja fuerte vínculos:</span><span class="sxs-lookup"><span data-stu-id="f7111-194">The **View data by URL click by application** view shows the number of URL clicks by apps that support Safe Links:</span></span>

- <span data-ttu-id="f7111-195">**Cliente de correo electrónico**</span><span class="sxs-lookup"><span data-stu-id="f7111-195">**Email client**</span></span>
- <span data-ttu-id="f7111-196">**PowerPoint**</span><span class="sxs-lookup"><span data-stu-id="f7111-196">**PowerPoint**</span></span>
- <span data-ttu-id="f7111-197">**Word**</span><span class="sxs-lookup"><span data-stu-id="f7111-197">**Word**</span></span>
- <span data-ttu-id="f7111-198">**Excel**</span><span class="sxs-lookup"><span data-stu-id="f7111-198">**Excel**</span></span>
- <span data-ttu-id="f7111-199">**OneNote**</span><span class="sxs-lookup"><span data-stu-id="f7111-199">**OneNote**</span></span>
- <span data-ttu-id="f7111-200">**Visio**</span><span class="sxs-lookup"><span data-stu-id="f7111-200">**Visio**</span></span>
- <span data-ttu-id="f7111-201">**Teams**</span><span class="sxs-lookup"><span data-stu-id="f7111-201">**Teams**</span></span>
- <span data-ttu-id="f7111-202">**Otros**</span><span class="sxs-lookup"><span data-stu-id="f7111-202">**Others**</span></span>

<span data-ttu-id="f7111-203">Si hace clic **en Filtros,** puede modificar el informe y la tabla de detalles seleccionando uno o varios de los siguientes valores en el menú desplegable que aparece:</span><span class="sxs-lookup"><span data-stu-id="f7111-203">If you click **Filters**, you can modify the report and the details table by selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="f7111-204">**Fecha (UTC):** **fecha de inicio y** fecha de **finalización**</span><span class="sxs-lookup"><span data-stu-id="f7111-204">**Date (UTC)**: **Start date** and **End date**</span></span>
- <span data-ttu-id="f7111-205">**Detección:** aplicaciones disponibles del gráfico.</span><span class="sxs-lookup"><span data-stu-id="f7111-205">**Detection**: Available apps from the chart.</span></span>
- <span data-ttu-id="f7111-206">**Dominios:** los dominios url enumerados en los resultados del informe.</span><span class="sxs-lookup"><span data-stu-id="f7111-206">**Domains**: The URL domains listed in the report results.</span></span>
- <span data-ttu-id="f7111-207">**Destinatarios**</span><span class="sxs-lookup"><span data-stu-id="f7111-207">**Recipients**</span></span>

<span data-ttu-id="f7111-208">Cuando haya terminado de configurar los filtros, haga clic **en Aplicar,** **Cancelar** o **Borrar filtros**.</span><span class="sxs-lookup"><span data-stu-id="f7111-208">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

<span data-ttu-id="f7111-209">La tabla de detalles debajo del gráfico proporciona la siguiente vista casi en tiempo real de todos los clics que se han producido en la organización durante los últimos 7 días:</span><span class="sxs-lookup"><span data-stu-id="f7111-209">The details table below the chart provides the following near-real-time view of all clicks that happened within the organization for the last 7 days:</span></span>

- <span data-ttu-id="f7111-210">**Hora de hacer clic**</span><span class="sxs-lookup"><span data-stu-id="f7111-210">**Click time**</span></span>
- <span data-ttu-id="f7111-211">**Usuario**</span><span class="sxs-lookup"><span data-stu-id="f7111-211">**User**</span></span>
- <span data-ttu-id="f7111-212">**URL**</span><span class="sxs-lookup"><span data-stu-id="f7111-212">**URL**</span></span>
- <span data-ttu-id="f7111-213">**Action**</span><span class="sxs-lookup"><span data-stu-id="f7111-213">**Action**</span></span>
- <span data-ttu-id="f7111-214">**Aplicación**</span><span class="sxs-lookup"><span data-stu-id="f7111-214">**App**</span></span>

## <a name="additional-reports-to-view"></a><span data-ttu-id="f7111-215">Informes adicionales para ver</span><span class="sxs-lookup"><span data-stu-id="f7111-215">Additional reports to view</span></span>

<span data-ttu-id="f7111-216">Además de los informes descritos en este artículo, hay otros informes disponibles, como se describe en la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="f7111-216">In addition to the reports described in this article, several other reports are available, as described in the following table:</span></span>

<br>

****

|<span data-ttu-id="f7111-217">Informe</span><span class="sxs-lookup"><span data-stu-id="f7111-217">Report</span></span>|<span data-ttu-id="f7111-218">Tema</span><span class="sxs-lookup"><span data-stu-id="f7111-218">Topic</span></span>|
|---|---|
|<span data-ttu-id="f7111-219">**Explorer** (Microsoft Defender para Office 365 plan 2) o detecciones en tiempo **real** (Microsoft Defender para Office 365 Plan 1)</span><span class="sxs-lookup"><span data-stu-id="f7111-219">**Explorer** (Microsoft Defender for Office 365 Plan 2) or **real-time detections** (Microsoft Defender for Office 365 Plan 1)</span></span>|[<span data-ttu-id="f7111-220">Explorador de amenazas (y detecciones en tiempo real)</span><span class="sxs-lookup"><span data-stu-id="f7111-220">Threat Explorer (and real-time detections)</span></span>](threat-explorer.md)|
|<span data-ttu-id="f7111-221">**Informes de seguridad de** correo electrónico, como el informe de remitentes y destinatarios principales, el informe de correo suplantación de identidad y el informe de detecciones de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="f7111-221">**Email security reports**, such as the Top senders and recipients report, the Spoof mail report, and the Spam detections report.</span></span>|[<span data-ttu-id="f7111-222">Ver informes de seguridad de correo electrónico en el portal Microsoft 365 Defender correo electrónico</span><span class="sxs-lookup"><span data-stu-id="f7111-222">View email security reports in the Microsoft 365 Defender portal</span></span>](view-email-security-reports.md)|
|<span data-ttu-id="f7111-223">**Informes de flujo de** correo, como el informe de reenvío, el informe de estado de flujo de correo y el informe Principales remitentes y destinatarios.</span><span class="sxs-lookup"><span data-stu-id="f7111-223">**Mail flow reports**, such as the Forwarding report, the Mailflow status report, and the Top senders and recipients report.</span></span>|[<span data-ttu-id="f7111-224">Informes de flujo de correo en el nuevo centro Exchange administración</span><span class="sxs-lookup"><span data-stu-id="f7111-224">Mail flow reports in the new Exchange admin center</span></span>](/exchange/monitoring/mail-flow-reports/mail-flow-reports)|
|<span data-ttu-id="f7111-225">**Seguimiento de direcciones URL para Caja fuerte (solo** PowerShell).</span><span class="sxs-lookup"><span data-stu-id="f7111-225">**URL trace for Safe Links** (PowerShell only).</span></span> <span data-ttu-id="f7111-226">El resultado de este cmdlet muestra los resultados de las acciones Caja fuerte links en los últimos siete días.</span><span class="sxs-lookup"><span data-stu-id="f7111-226">The output of this cmdlet shows you the results of Safe Links actions over the past seven days.</span></span>|[<span data-ttu-id="f7111-227">Get-UrlTrace</span><span class="sxs-lookup"><span data-stu-id="f7111-227">Get-UrlTrace</span></span>](/powershell/module/exchange/get-urltrace)|
|<span data-ttu-id="f7111-228">**Resultados de tráfico de correo para EOP** y Microsoft Defender para Office 365 (solo PowerShell).</span><span class="sxs-lookup"><span data-stu-id="f7111-228">**Mail traffic results for EOP and Microsoft Defender for Office 365** (PowerShell only).</span></span> <span data-ttu-id="f7111-229">El resultado de este cmdlet contiene información sobre Dominio, Fecha, Tipo de evento, Dirección, Acción y Recuento de mensajes.</span><span class="sxs-lookup"><span data-stu-id="f7111-229">The output of this cmdlet contains information about Domain, Date, Event Type, Direction, Action, and Message Count.</span></span>|[<span data-ttu-id="f7111-230">Get-MailTrafficATPReport</span><span class="sxs-lookup"><span data-stu-id="f7111-230">Get-MailTrafficATPReport</span></span>](/powershell/module/exchange/get-mailtrafficatpreport)|
|<span data-ttu-id="f7111-231">**Informes de detalles de correo para EOP y Defender para Office 365 (solo** PowerShell).</span><span class="sxs-lookup"><span data-stu-id="f7111-231">**Mail detail reports for EOP and Defender for Office 365 detections** (PowerShell only).</span></span> <span data-ttu-id="f7111-232">El resultado de este cmdlet contiene detalles sobre archivos o direcciones URL malintencionados, intentos de suplantación, suplantación y otras amenazas potenciales en el correo electrónico o los archivos.</span><span class="sxs-lookup"><span data-stu-id="f7111-232">The output of this cmdlet contains details about malicious files or URLs, phishing attempts, impersonation, and other potential threats in email or files.</span></span>|[<span data-ttu-id="f7111-233">Get-MailDetailATPReport</span><span class="sxs-lookup"><span data-stu-id="f7111-233">Get-MailDetailATPReport</span></span>](/powershell/module/exchange/get-maildetailatpreport)|
|

## <a name="what-permissions-are-needed-to-view-the-defender-for-office-365-reports"></a><span data-ttu-id="f7111-234">¿Qué permisos se necesitan para ver el Defender para Office 365 informes?</span><span class="sxs-lookup"><span data-stu-id="f7111-234">What permissions are needed to view the Defender for Office 365 reports?</span></span>

<span data-ttu-id="f7111-235">Para ver y usar los informes descritos en este artículo, debe ser miembro de uno de los siguientes grupos de roles en el portal de Microsoft 365 Defender web:</span><span class="sxs-lookup"><span data-stu-id="f7111-235">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="f7111-236">**Administración de organizaciones**</span><span class="sxs-lookup"><span data-stu-id="f7111-236">**Organization Management**</span></span>
- <span data-ttu-id="f7111-237">**Administrador de seguridad**</span><span class="sxs-lookup"><span data-stu-id="f7111-237">**Security Administrator**</span></span>
- <span data-ttu-id="f7111-238">**Lector de seguridad**</span><span class="sxs-lookup"><span data-stu-id="f7111-238">**Security Reader**</span></span>
- <span data-ttu-id="f7111-239">**Lector global**</span><span class="sxs-lookup"><span data-stu-id="f7111-239">**Global Reader**</span></span>

<span data-ttu-id="f7111-240">Para obtener más información, vea [Permissions in the Microsoft 365 Defender portal](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="f7111-240">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="f7111-241">**Nota:** Agregar usuarios al rol Azure Active Directory correspondiente en el Centro de administración de Microsoft 365 proporciona a los usuarios los permisos necesarios en el _portal_ de Microsoft 365 Defender y permisos para otras características de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f7111-241">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="f7111-242">Para obtener más información, vea [Sobre los roles de administrador](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="f7111-242">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="f7111-243">¿Qué ocurre si los informes no muestran datos?</span><span class="sxs-lookup"><span data-stu-id="f7111-243">What if the reports aren't showing data?</span></span>

<span data-ttu-id="f7111-244">Si no ve datos en defender para los informes Office 365, compruebe que las directivas están configuradas correctamente.</span><span class="sxs-lookup"><span data-stu-id="f7111-244">If you are not seeing data in your Defender for Office 365 reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="f7111-245">Su organización debe tener definidas [Caja fuerte de](set-up-safe-links-policies.md) vínculos y Caja fuerte [de](set-up-safe-attachments-policies.md) datos adjuntos para que Defender Office 365 protección esté en su lugar.</span><span class="sxs-lookup"><span data-stu-id="f7111-245">Your organization must have [Safe Links policies](set-up-safe-links-policies.md) and [Safe Attachments policies](set-up-safe-attachments-policies.md) defined in order for Defender for Office 365 protection to be in place.</span></span> <span data-ttu-id="f7111-246">Vea también Protección contra correo no deseado y [antimalware.](anti-spam-and-anti-malware-protection.md)</span><span class="sxs-lookup"><span data-stu-id="f7111-246">Also see [Anti-spam and anti-malware protection](anti-spam-and-anti-malware-protection.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="f7111-247">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="f7111-247">Related topics</span></span>

[<span data-ttu-id="f7111-248">Informes e información inteligentes en el portal Microsoft 365 Defender web</span><span class="sxs-lookup"><span data-stu-id="f7111-248">Smart reports and insights in the Microsoft 365 Defender portal</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="f7111-249">Permisos de función (Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="f7111-249">Role permissions (Azure Active Directory</span></span>](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#role-permissions)
