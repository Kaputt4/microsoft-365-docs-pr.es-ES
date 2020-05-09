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
description: Busque y use informes de la protección contra amenazas avanzada de Office 365 &amp; en el centro de seguridad y cumplimiento.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c202e7df274e81da5395f7466199d85443361c05
ms.sourcegitcommit: 614666afb104fc97acb4a2ee5577ef63c0de153a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/09/2020
ms.locfileid: "44173327"
---
# <a name="view-reports-for-office-365-advanced-threat-protection"></a><span data-ttu-id="cfb0f-103">Ver informes para la protección contra amenazas avanzada de Office 365</span><span class="sxs-lookup"><span data-stu-id="cfb0f-103">View reports for Office 365 Advanced Threat Protection</span></span>

<span data-ttu-id="cfb0f-104">Si la organización dispone de la [protección contra amenazas avanzada](office-365-atp.md) (ATP) de Office 365 y dispone de los [permisos necesarios](#what-permissions-are-needed-to-view-the-atp-reports), puede usar varios informes de &amp; ATP en el centro de seguridad y cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="cfb0f-104">If your organization has [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) and you have the [necessary permissions](#what-permissions-are-needed-to-view-the-atp-reports), you can use several ATP reports in the Security &amp; Compliance Center.</span></span> <span data-ttu-id="cfb0f-105">(Vaya a **Reports** \> **Panel**de informes).</span><span class="sxs-lookup"><span data-stu-id="cfb0f-105">(Go to **Reports** \> **Dashboard**.)</span></span>

![El panel &amp; del centro de seguridad y cumplimiento puede ayudarle a ver dónde está funcionando la protección contra amenazas avanzada](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

<span data-ttu-id="cfb0f-107">Los informes de ATP incluyen lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="cfb0f-107">ATP reports include the following:</span></span>

- [<span data-ttu-id="cfb0f-108">Informe de estado de protección contra amenazas</span><span class="sxs-lookup"><span data-stu-id="cfb0f-108">Threat Protection Status report</span></span>](#threat-protection-status-report)
- [<span data-ttu-id="cfb0f-109">Informe de tipos de archivos de ATP</span><span class="sxs-lookup"><span data-stu-id="cfb0f-109">ATP File Types report</span></span>](#atp-file-types-report)
- [<span data-ttu-id="cfb0f-110">Informe de disposición de mensajes ATP</span><span class="sxs-lookup"><span data-stu-id="cfb0f-110">ATP Message Disposition report</span></span>](#atp-message-disposition-report)
- <span data-ttu-id="cfb0f-111">[detección en tiempo real o explorador](threat-explorer.md) (en función de si tiene Office 365 ATP plan 1 o 2)</span><span class="sxs-lookup"><span data-stu-id="cfb0f-111">either [real-time detections or Explorer](threat-explorer.md) (depending on whether you have Office 365 ATP Plan 1 or 2)</span></span>
- <span data-ttu-id="cfb0f-112">... [etc](#additional-reports-to-view).</span><span class="sxs-lookup"><span data-stu-id="cfb0f-112">... [and more](#additional-reports-to-view).</span></span>

<span data-ttu-id="cfb0f-113">Lea este artículo para obtener información general sobre los informes de ATP y cómo usarlos.</span><span class="sxs-lookup"><span data-stu-id="cfb0f-113">Read this article to get an overview of ATP reports and how to use them.</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="cfb0f-114">Informe de estado de protección contra amenazas</span><span class="sxs-lookup"><span data-stu-id="cfb0f-114">Threat Protection Status report</span></span>

<span data-ttu-id="cfb0f-115">El informe de **Estado de protección contra amenazas** es una vista única que reúne información sobre contenido malintencionado y correo electrónico malintencionado detectado y bloqueado por [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) y [Office 365 ATP](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="cfb0f-115">The **Threat Protection Status** report is a single view that brings together information about malicious content and malicious email detected and blocked by [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) and [Office 365 ATP](office-365-atp.md).</span></span> <span data-ttu-id="cfb0f-116">Este informe es útil para ver las detecciones a lo largo del tiempo (hasta 90 días) y permite a los administradores de seguridad identificar las tendencias o determinar si las directivas necesitan ajustes.</span><span class="sxs-lookup"><span data-stu-id="cfb0f-116">This report is useful for viewing detections over time (up to 90 days), and it enables security administrators to identify trends or determine whether policies need adjustments.</span></span>

<span data-ttu-id="cfb0f-117">El informe proporciona un recuento agregado de mensajes de correo electrónico únicos con contenido malintencionado, como archivos o direcciones de sitios web (URL) bloqueados por el motor antimalware, [purgado automático de cero horas (ZAP)](zero-hour-auto-purge.md)y características de ATP, como [vínculos seguros de ATP](atp-safe-links.md), [datos adjuntos seguros](atp-safe-attachments.md)de ATP y [antiphishing de ATP](set-up-anti-phishing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="cfb0f-117">The report provides an aggregated count of unique email messages with malicious content, such as files or website addresses (URLs) that were blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and ATP features like [ATP Safe Links](atp-safe-links.md), [ATP Safe Attachments](atp-safe-attachments.md), and [ATP anti-phishing](set-up-anti-phishing-policies.md).</span></span>

<span data-ttu-id="cfb0f-118">Los filtros y los desgloses de la información permiten clasificaciones más detalladas de la información de este informe.</span><span class="sxs-lookup"><span data-stu-id="cfb0f-118">Filters and breakdowns of the information allow for more granular categorizations of the information in this report.</span></span> <span data-ttu-id="cfb0f-119">**En concreto** , se incluye un menú de "desglosar por" para las vistas de \> **phish** y **malware**del **correo** \> electrónico.</span><span class="sxs-lookup"><span data-stu-id="cfb0f-119">Specifically, there is a 'break down by' menu included for **Email** \> **Phish** and **Email** \> **Malware views**.</span></span> <span data-ttu-id="cfb0f-120">Se desglosarán los datos en:</span><span class="sxs-lookup"><span data-stu-id="cfb0f-120">It will break down the data into:</span></span>

|||
|---|---|
|<span data-ttu-id="cfb0f-121">Por tipo de detección</span><span class="sxs-lookup"><span data-stu-id="cfb0f-121">By detection type</span></span>|<span data-ttu-id="cfb0f-122">¿Qué directiva ayudó a detectar estas amenazas?</span><span class="sxs-lookup"><span data-stu-id="cfb0f-122">What policy helped catch these threats?</span></span>|
|<span data-ttu-id="cfb0f-123">Por tecnología de detección</span><span class="sxs-lookup"><span data-stu-id="cfb0f-123">By detection technology</span></span>|<span data-ttu-id="cfb0f-124">¿Qué tecnología subyacente de Microsoft capturó la amenaza?</span><span class="sxs-lookup"><span data-stu-id="cfb0f-124">What underlying Microsoft technology caught the threat?</span></span>|
|<span data-ttu-id="cfb0f-125">Por estado de entrega</span><span class="sxs-lookup"><span data-stu-id="cfb0f-125">By delivery status</span></span>|<span data-ttu-id="cfb0f-126">¿Qué ocurrió con los mensajes de correo electrónico detectados como amenazas?</span><span class="sxs-lookup"><span data-stu-id="cfb0f-126">What happened to the email messages detected as threats?</span></span>|
|

> [!TIP]
> <span data-ttu-id="cfb0f-127">El correo electrónico > phish | Las vistas de malware tienen desgloses granulares para las tecnologías de detección que se muestran, con categorías como *la reputación de archivo generado por ATP*, la *detonación de archivos*, la *detonación de dirección URL*, *anti-falseamiento: error de DMARC*, por ejemplo, útil para indicar exactamente qué característica condujo a su organización para que detecte las amenazas.</span><span class="sxs-lookup"><span data-stu-id="cfb0f-127">Both the Email > Phish | Malware views have granular breakdowns for the detection technologies shown, with categories like *ATP-generated file reputation*, *File detonation*, *URL detonation*, *Anti-spoof: DMARC failure*, for example, helpful in pinpointing exactly which feature led your organization to catch threats.</span></span>

![Informe de estado de protección contra amenazas desplegable que muestra ' dividir por '.](../../media/tp-threatProtectStatRpt-BreakDownBy.png)

<span data-ttu-id="cfb0f-129">Estas vistas le ofrecen la opción de exportar, mediante un clic de botón (en vistas de **phishing**de **correo electrónico** \> , **malware**de **correo electrónico** \> y **malware** de **contenido** \> ).</span><span class="sxs-lookup"><span data-stu-id="cfb0f-129">These views give you the option to export, via a button click (in **Email** \> **Phish**, **Email** \> **Malware**, and **Content** \> **Malware** views).</span></span> <span data-ttu-id="cfb0f-130">Los datos agregados exportados a su equipo se pueden abrir en Excel.</span><span class="sxs-lookup"><span data-stu-id="cfb0f-130">The aggregated data exported to your computer can be opened in Excel.</span></span>

![Este gráfico muestra exportar como una opción en el menú para la vista de malware, directamente entre crear programación y solicitar informe.](../../media/tp-threatProtectStatRpt-BreakDownByExport.png)

<span data-ttu-id="cfb0f-132">**Nota**: el número máximo de entradas que se pueden exportar para **phish** y **Malware** solo es inferior a 10000.</span><span class="sxs-lookup"><span data-stu-id="cfb0f-132">**Note**: The maximum number of entries that can be exported for **Phish** and **Malware** is just under 10000.</span></span> <span data-ttu-id="cfb0f-133">Si exporta una vista, se exportan sólo las entradas 10000 más recientes.</span><span class="sxs-lookup"><span data-stu-id="cfb0f-133">If you export a view, only the most recent 10000 entries are exported.</span></span>

<span data-ttu-id="cfb0f-134">En las vistas información general y mensajes de correo electrónico se muestra información en horas de procesamiento, en lugar de en 24 horas (demanda re.</span><span class="sxs-lookup"><span data-stu-id="cfb0f-134">The Overview and Emails views will display information within hours of processing rather than in 24 hours (demand re.</span></span> <span data-ttu-id="cfb0f-135">la velocidad aumentada aquí ha sido una señal clara).</span><span class="sxs-lookup"><span data-stu-id="cfb0f-135">increased speeds here has been a clear signal)!</span></span>

> [!NOTE]
> <span data-ttu-id="cfb0f-136">Un informe de estado de protección contra amenazas está disponible para los clientes que tengan [Office 365 ATP](office-365-atp.md) o [Exchange Online Protection](exchange-online-protection-eop.md) (EOP); sin embargo, la información que se muestra en el informe de estado de la protección contra amenazas para los clientes de ATP probablemente contendrá distintos datos de los que pueden ver los clientes de EOP.</span><span class="sxs-lookup"><span data-stu-id="cfb0f-136">A Threat Protection Status report is available to customers who have either [Office 365 ATP](office-365-atp.md) or [Exchange Online Protection](exchange-online-protection-eop.md) (EOP); however, the information that is displayed in the Threat Protection Status report for ATP customers will likely contain different data than what EOP customers might see.</span></span> <span data-ttu-id="cfb0f-137">Por ejemplo, el informe de estado de protección contra amenazas para los clientes de ATP contendrá información sobre [los archivos malintencionados detectados en SharePoint Online, OneDrive o Microsoft Teams](atp-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="cfb0f-137">For example, the Threat Protection Status report for ATP customers will contain information about [malicious files detected in SharePoint Online, OneDrive, or Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span> <span data-ttu-id="cfb0f-138">Esta información es específica de ATP, por lo que los clientes que tengan EOP pero no ATP no verán los detalles en el informe de estado de protección contra amenazas.</span><span class="sxs-lookup"><span data-stu-id="cfb0f-138">Such information is specific to ATP, so customers who have EOP but not ATP will not see those details in their Threat Protection Status report.</span></span>

<span data-ttu-id="cfb0f-139">Para ver el informe de estado de protección contra amenazas, en el [centro de seguridad &amp; y cumplimiento](https://protection.office.com), vaya al **Panel** \> **informes** \> **Estado de protección contra amenazas**.</span><span class="sxs-lookup"><span data-stu-id="cfb0f-139">To view the Threat Protection Status report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Threat Protection Status**.</span></span>

![Informe de estado de protección contra amenazas ATP](../../media/6bdd41eb-62e0-423b-9fd4-d1d5baf0cbd5.png)

<span data-ttu-id="cfb0f-141">Para obtener el estado detallado de un día, desplace el puntero sobre el gráfico.</span><span class="sxs-lookup"><span data-stu-id="cfb0f-141">To get detailed status for a day, hover over the graph.</span></span>

![Datos de estado de protección contra amenazas ATP para un día](../../media/d5c2c6ad-c002-4985-a032-c866e46fdea8.png)

<span data-ttu-id="cfb0f-143">De forma predeterminada, el informe de estado de protección contra amenazas muestra datos de los últimos siete días.</span><span class="sxs-lookup"><span data-stu-id="cfb0f-143">By default, the Threat Protection Status report shows data for the past seven days.</span></span> <span data-ttu-id="cfb0f-144">Sin embargo, puede elegir **filtros** y cambiar el intervalo de fechas para ver los datos de hasta 90 días.</span><span class="sxs-lookup"><span data-stu-id="cfb0f-144">However, you can choose **Filters** and change the date range to view data for up to 90 days.</span></span> <span data-ttu-id="cfb0f-145">(Si usa una suscripción de prueba, es posible que se limite a 30 días de datos).</span><span class="sxs-lookup"><span data-stu-id="cfb0f-145">(If you are using a trial subscription, you might be limited to 30 days' of data.)</span></span>

![Filtros de estado de protección contra amenazas ATP](../../media/4f703369-642b-402b-9758-b9c828283410.png)

<span data-ttu-id="cfb0f-147">También puede usar el menú **ver datos por** para cambiar la información que se muestra en el informe.</span><span class="sxs-lookup"><span data-stu-id="cfb0f-147">You can also use the **View data by** menu to change what information is displayed in the report.</span></span>

![Visualización de opciones del informe de estado de protección contra amenazas ATP](../../media/4959bf8c-d192-4542-b00b-184e101e7513.png)

## <a name="url-protection-status-report"></a><span data-ttu-id="cfb0f-149">Informe de estado de protección de URL</span><span class="sxs-lookup"><span data-stu-id="cfb0f-149">URL Protection Status report</span></span>

<span data-ttu-id="cfb0f-150">Este informe se basa en datos recopilados y se detectan amenazas, por clic (mientras que la mayoría de los informes relacionados con amenazas de correo electrónico son por datos de mensaje).</span><span class="sxs-lookup"><span data-stu-id="cfb0f-150">This report is based data collected, and threats detected, per click (whereas most other email threat related reports are per message data).</span></span> <span data-ttu-id="cfb0f-151">Este informe está diseñado para mostrar las amenazas que provienen de hipervínculos en mensajes de correo electrónico y documentos, por clic.</span><span class="sxs-lookup"><span data-stu-id="cfb0f-151">This report is designed to show threats that come from hyperlinks in email messages and documents, per click.</span></span> <span data-ttu-id="cfb0f-152">Hay dos vistas:</span><span class="sxs-lookup"><span data-stu-id="cfb0f-152">There are two views:</span></span>

|||
|---|---|
|<span data-ttu-id="cfb0f-153">Acción de clic de dirección URL en protección</span><span class="sxs-lookup"><span data-stu-id="cfb0f-153">URL click protection action</span></span>|<span data-ttu-id="cfb0f-154">Vea el número de direcciones URL bloqueadas, bloqueadas pero reemplazadas por un usuario con un clic que se ha reemplazado con un clic por un usuario y permitido.</span><span class="sxs-lookup"><span data-stu-id="cfb0f-154">See the number of URLs blocked, blocked but overridden with a click-through by a user, overridden with a click-through by a user, and allowed.</span></span>|
|<span data-ttu-id="cfb0f-155">Dirección URL haga clic por aplicación</span><span class="sxs-lookup"><span data-stu-id="cfb0f-155">URL click by application</span></span>|<span data-ttu-id="cfb0f-156">Vea la aplicación desde la que se hizo clic en la dirección URL.</span><span class="sxs-lookup"><span data-stu-id="cfb0f-156">See the application from which the URL was clicked.</span></span>|
|

<span data-ttu-id="cfb0f-157">En la tabla de detalles, podrá ver más información acerca de la hora de clic y la información del usuario.</span><span class="sxs-lookup"><span data-stu-id="cfb0f-157">In the details table, you'll be able to see more information regarding click time and user information.</span></span> <span data-ttu-id="cfb0f-158">Por último, tenga en cuenta que el informe de estado de protección de URL muestra la protección de la característica de vínculos seguros de ATP, de modo que solo los clientes que hayan habilitado vínculos seguros de ATP verán los datos reflejados en este informe.</span><span class="sxs-lookup"><span data-stu-id="cfb0f-158">Finally, keep in mind the URL Protection Status report shows the protection from ATP Safe Links feature, so only customers who have enabled ATP Safe Links will see data reflected on this report.</span></span>

> [!NOTE]
> <span data-ttu-id="cfb0f-159">Se trata de un *Informe de tendencias de protección*, lo que significa que los datos representan tendencias en un conjunto de datos más grande.</span><span class="sxs-lookup"><span data-stu-id="cfb0f-159">This is a *protection trend report*, meaning data represents trends in a larger dataset.</span></span> <span data-ttu-id="cfb0f-160">Como resultado, los datos de la vista de agregado no están disponibles en tiempo real aquí, pero los datos de la vista de tabla de detalles son, por lo que es posible que vea una ligera diferencia entre las dos vistas.</span><span class="sxs-lookup"><span data-stu-id="cfb0f-160">As a result, the data in the aggregate view is not available in real time here, but the data in the details table view is, so you may see a slight discrepancy between the two views.</span></span>

## <a name="atp-file-types-report"></a><span data-ttu-id="cfb0f-161">Informe de tipos de archivos de ATP</span><span class="sxs-lookup"><span data-stu-id="cfb0f-161">ATP File Types report</span></span>

<span data-ttu-id="cfb0f-162">El informe de **tipos de archivo de ATP** muestra el tipo de archivos que los [datos adjuntos seguros de ATP](atp-safe-attachments.md)han detectado como malintencionados.</span><span class="sxs-lookup"><span data-stu-id="cfb0f-162">The **ATP File Types** report shows you the type of files detected as malicious by [ATP Safe Attachments](atp-safe-attachments.md).</span></span>

<span data-ttu-id="cfb0f-163">Para ver este informe, en el [Centro &amp; de seguridad y cumplimiento](https://protection.office.com), vaya a los **tipos de archivo ATP**del **Panel** \> **informes** \> .</span><span class="sxs-lookup"><span data-stu-id="cfb0f-163">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **ATP File Types**.</span></span>

![Informe de tipos de archivos de ATP](../../media/6e3f5d33-79aa-4b2d-938c-6ef135d9e54c.png)
  
<span data-ttu-id="cfb0f-165">Al pasar el mouse sobre un día concreto, puede ver el desglose de los tipos de archivos malintencionados detectados por los [datos adjuntos seguros de ATP](atp-safe-attachments.md) y la [protección antimalware contra correo no deseado &amp; ](anti-spam-and-anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="cfb0f-165">When you hover over a particular day, you can see the breakdown of types of malicious files that were detected by [ATP Safe Attachments](atp-safe-attachments.md) and [anti-spam &amp; anti-malware protection](anti-spam-and-anti-malware-protection.md).</span></span>
  
![Datos del informe de tipos de archivos ATP para un día](../../media/10d18428-699a-41d2-a73e-be3a8214ada1.png)

## <a name="atp-message-disposition-report"></a><span data-ttu-id="cfb0f-167">Informe de disposición de mensajes ATP</span><span class="sxs-lookup"><span data-stu-id="cfb0f-167">ATP Message Disposition report</span></span>

<span data-ttu-id="cfb0f-168">El informe de **disposición de mensajes de ATP** muestra las acciones que se tomaron para los mensajes de correo electrónico que se detectaron con contenido malintencionado.</span><span class="sxs-lookup"><span data-stu-id="cfb0f-168">The **ATP Message Disposition** report shows you the actions that were taken for email messages that were detected as having malicious content.</span></span>

<span data-ttu-id="cfb0f-169">Para ver este informe, en el [Centro &amp; de seguridad y cumplimiento](https://protection.office.com), vaya a la **disposición de mensajes ATP**del **Panel** \> **informes** \> .</span><span class="sxs-lookup"><span data-stu-id="cfb0f-169">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **ATP Message Disposition**.</span></span>

![Informe de disposición de mensajes ATP](../../media/b0ff65c4-53d3-496d-bafa-8937a5eb69e5.png)

<span data-ttu-id="cfb0f-171">Cuando desplaza el puntero sobre una barra del gráfico, puede ver qué acciones se tomaron para el correo electrónico detectado durante ese día.</span><span class="sxs-lookup"><span data-stu-id="cfb0f-171">When you hover over a bar in the chart, you can see what actions were taken for detected email for that day.</span></span>

![Datos del informe de disposición de mensajes ATP para un día](../../media/68d2beb8-4b30-48c4-8ba6-5e8ab88ae456.png)

## <a name="additional-reports-to-view"></a><span data-ttu-id="cfb0f-173">Informes adicionales para ver</span><span class="sxs-lookup"><span data-stu-id="cfb0f-173">Additional reports to view</span></span>

<span data-ttu-id="cfb0f-174">Además de los informes de ATP descritos en este artículo, hay disponibles varios otros informes, como se describe en la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="cfb0f-174">In addition to the ATP reports described in this article, several other reports are available, as described in the following table:</span></span>

|||
|---|---|
|<span data-ttu-id="cfb0f-175">**Informe (s)**</span><span class="sxs-lookup"><span data-stu-id="cfb0f-175">**Report(s)**</span></span>|<span data-ttu-id="cfb0f-176">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="cfb0f-176">**Details**</span></span>|
|<span data-ttu-id="cfb0f-177">**Explorer** o **detección en tiempo real**: (Office 365 ATP plan 2 los clientes tienen explorador; Office 365 ATP plan 1 los clientes tienen detecciones en tiempo real.)</span><span class="sxs-lookup"><span data-stu-id="cfb0f-177">**Explorer** or **real-time detections**: (Office 365 ATP Plan 2 customers have Explorer; Office 365 ATP Plan 1 customers have real-time detections.)</span></span>|[<span data-ttu-id="cfb0f-178">Explorador de amenazas (y detecciones en tiempo real)</span><span class="sxs-lookup"><span data-stu-id="cfb0f-178">Threat Explorer (and real-time detections)</span></span>](threat-explorer.md)|
|<span data-ttu-id="cfb0f-179">**Informes de seguridad de correo electrónico**, como un informe de remitentes y destinatarios principales, un informe de correo falsificado y un informe de detecciones de correo no deseado.</span><span class="sxs-lookup"><span data-stu-id="cfb0f-179">**Email security reports**, such as a Top Senders and Recipients report, a Spoof Mail report, and a Spam Detections report.</span></span>|[<span data-ttu-id="cfb0f-180">Ver informes de seguridad de correo electrónico &amp; en el centro de seguridad y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="cfb0f-180">View email security reports in the Security &amp; Compliance Center</span></span>](view-email-security-reports.md)|
|<span data-ttu-id="cfb0f-181">**Seguimiento de dirección URL de vínculos seguros de ATP**: (este es un informe que se genera con PowerShell). Este informe muestra los resultados de las acciones de vínculos seguros de ATP en los últimos siete (7) días.</span><span class="sxs-lookup"><span data-stu-id="cfb0f-181">**ATP Safe Links URL trace**: (This is a report you generate by using PowerShell.) This report shows the results of ATP Safe Links actions over the past seven (7) days.</span></span>|[<span data-ttu-id="cfb0f-182">Referencia del cmdlet Get-UrlTrace</span><span class="sxs-lookup"><span data-stu-id="cfb0f-182">Get-UrlTrace cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-urltrace)|
|<span data-ttu-id="cfb0f-183">**Resultados de EOP y ATP**: (este es un informe personalizado que se genera con PowerShell).</span><span class="sxs-lookup"><span data-stu-id="cfb0f-183">**EOP and ATP results**: (This is a custom report you generate by using PowerShell).</span></span> <span data-ttu-id="cfb0f-184">Este informe contiene información como, por ejemplo, el dominio, la fecha, el tipo de evento, la dirección, la acción y el recuento de mensajes.</span><span class="sxs-lookup"><span data-stu-id="cfb0f-184">This report contains information, such as Domain, Date, Event Type, Direction, Action, and Message Count.</span></span>|[<span data-ttu-id="cfb0f-185">Referencia del cmdlet Get-MailTrafficATPReport</span><span class="sxs-lookup"><span data-stu-id="cfb0f-185">Get-MailTrafficATPReport cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-mailtrafficatpreport)|
|<span data-ttu-id="cfb0f-186">**Detecciones de EOP y ATP**: (este es un informe personalizado que se genera con PowerShell).</span><span class="sxs-lookup"><span data-stu-id="cfb0f-186">**EOP and ATP detections**: (This is a custom report you generate by using PowerShell).</span></span> <span data-ttu-id="cfb0f-187">Este informe contiene detalles sobre archivos malintencionados o direcciones URL, intentos de suplantación de identidad, suplantación y otras amenazas potenciales en los correos electrónicos o archivos.</span><span class="sxs-lookup"><span data-stu-id="cfb0f-187">This report contains details about malicious files or URLs, phishing attempts, impersonation, and other potential threats in email or files.</span></span>|[<span data-ttu-id="cfb0f-188">Referencia del cmdlet Get-MailDetailATPReport</span><span class="sxs-lookup"><span data-stu-id="cfb0f-188">Get-MailDetailATPReport cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-maildetailatpreport)|
|

## <a name="what-permissions-are-needed-to-view-the-atp-reports"></a><span data-ttu-id="cfb0f-189">¿Qué permisos se necesitan para ver los informes de ATP?</span><span class="sxs-lookup"><span data-stu-id="cfb0f-189">What permissions are needed to view the ATP reports?</span></span>

<span data-ttu-id="cfb0f-190">Para poder ver y usar los informes descritos en este artículo, **debe tener asignada una función adecuada para el centro de &amp; seguridad y cumplimiento y el centro de administración de Exchange**.</span><span class="sxs-lookup"><span data-stu-id="cfb0f-190">In order to view and use the reports described in this article, **you must have an appropriate role assigned for both the Security &amp; Compliance Center and the Exchange admin center**.</span></span>

- <span data-ttu-id="cfb0f-191">Para el centro &amp; de seguridad y cumplimiento, debe tener asignada una de las siguientes funciones:</span><span class="sxs-lookup"><span data-stu-id="cfb0f-191">For the Security &amp; Compliance Center, you must have one of the following roles assigned:</span></span>

  - <span data-ttu-id="cfb0f-192">Administración de la organización</span><span class="sxs-lookup"><span data-stu-id="cfb0f-192">Organization Management</span></span>
  - <span data-ttu-id="cfb0f-193">Administrador de seguridad (puede asignarse en el centro de administración de Azure Active[https://aad.portal.azure.com](https://aad.portal.azure.com)Directory ())</span><span class="sxs-lookup"><span data-stu-id="cfb0f-193">Security Administrator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span></span>
  - <span data-ttu-id="cfb0f-194">Operador de seguridad (puede asignarse en el centro de administración de Azure Active[https://aad.portal.azure.com](https://aad.portal.azure.com)Directory ())</span><span class="sxs-lookup"><span data-stu-id="cfb0f-194">Security Operator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span></span>
  - <span data-ttu-id="cfb0f-195">Lector de seguridad</span><span class="sxs-lookup"><span data-stu-id="cfb0f-195">Security Reader</span></span>

- <span data-ttu-id="cfb0f-196">Para Exchange Online, debe tener una de las siguientes funciones asignadas en el centro de administración de Exchange[https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)() o con cmdlets de PowerShell (vea [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell)):</span><span class="sxs-lookup"><span data-stu-id="cfb0f-196">For Exchange Online, you must have one of the following roles assigned in either the Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) or with PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell)):</span></span>

  - <span data-ttu-id="cfb0f-197">Administración de la organización</span><span class="sxs-lookup"><span data-stu-id="cfb0f-197">Organization Management</span></span>
  - <span data-ttu-id="cfb0f-198">Administración de organización de solo lectura</span><span class="sxs-lookup"><span data-stu-id="cfb0f-198">View-only Organization Management</span></span>
  - <span data-ttu-id="cfb0f-199">Rol Destinatarios con permiso de vista</span><span class="sxs-lookup"><span data-stu-id="cfb0f-199">View-Only Recipients role</span></span>
  - <span data-ttu-id="cfb0f-200">Administración de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="cfb0f-200">Compliance Management</span></span>

<span data-ttu-id="cfb0f-201">Para obtener más información, consulte los siguientes recursos:</span><span class="sxs-lookup"><span data-stu-id="cfb0f-201">To learn more, see the following resources:</span></span>

- [<span data-ttu-id="cfb0f-202">Permisos en el centro &amp; de seguridad y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="cfb0f-202">Permissions in the Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)

- [<span data-ttu-id="cfb0f-203">Permisos de características de Exchange Online</span><span class="sxs-lookup"><span data-stu-id="cfb0f-203">Feature permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="cfb0f-204">¿Qué ocurre si los informes no muestran datos?</span><span class="sxs-lookup"><span data-stu-id="cfb0f-204">What if the reports aren't showing data?</span></span>

<span data-ttu-id="cfb0f-205">Si no ve datos en los informes de ATP, compruebe que las directivas estén correctamente configuradas.</span><span class="sxs-lookup"><span data-stu-id="cfb0f-205">If you are not seeing data in your ATP reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="cfb0f-206">La organización debe tener directivas de [vínculos seguros ATP](set-up-atp-safe-links-policies.md) y [directivas de datos adjuntos seguros ATP](set-up-atp-safe-attachments-policies.md) definidas para que la protección de ATP esté en su lugar.</span><span class="sxs-lookup"><span data-stu-id="cfb0f-206">Your organization must have [ATP Safe Links policies](set-up-atp-safe-links-policies.md) and [ATP Safe Attachments policies](set-up-atp-safe-attachments-policies.md) defined in order for ATP protection to be in place.</span></span> <span data-ttu-id="cfb0f-207">Consulte también [protección contra correo no deseado y antimalware en Office 365](anti-spam-and-anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="cfb0f-207">Also see [Anti-spam and anti-malware protection in Office 365](anti-spam-and-anti-malware-protection.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="cfb0f-208">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="cfb0f-208">Related topics</span></span>

[<span data-ttu-id="cfb0f-209">Informes y información en el centro de seguridad &amp; y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="cfb0f-209">Reports and insights in the Security &amp; Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)
  
[<span data-ttu-id="cfb0f-210">Crear una programación para un informe en el centro &amp; de seguridad y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="cfb0f-210">Create a schedule for a report in the Security &amp; Compliance Center</span></span>](create-a-schedule-for-a-report.md)

[<span data-ttu-id="cfb0f-211">Configurar y descargar un informe personalizado en el centro de &amp; seguridad y cumplimiento</span><span class="sxs-lookup"><span data-stu-id="cfb0f-211">Set up and download a custom report in the Security &amp; Compliance Center</span></span>](set-up-and-download-a-custom-report.md)

[<span data-ttu-id="cfb0f-212">Permisos de funciones (Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="cfb0f-212">Role permissions (Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#role-permissions)
