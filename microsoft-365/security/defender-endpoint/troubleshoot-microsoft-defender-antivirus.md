---
title: Códigos de error e IDs de eventos antivirus de Microsoft Defender
description: Buscar las causas y soluciones para los errores y los IDs de eventos de Antivirus de Microsoft Defender
keywords: event, error code, siem, logging, troubleshooting, wef, windows event forwarding
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/11/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: f7e8d6428360e5fe45a377f3ed6611a76f0a7911
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765820"
---
# <a name="review-event-logs-and-error-codes-to-troubleshoot-issues-with-microsoft-defender-antivirus"></a><span data-ttu-id="719cf-104">Revisar los registros de eventos y los códigos de error para solucionar problemas con Antivirus de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="719cf-104">Review event logs and error codes to troubleshoot issues with Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="719cf-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="719cf-105">**Applies to:**</span></span>

- [<span data-ttu-id="719cf-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="719cf-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="719cf-107">Si encuentra un problema con Microsoft Defender Antivirus, puede buscar en las tablas de este tema para encontrar un problema de coincidencia y una posible solución.</span><span class="sxs-lookup"><span data-stu-id="719cf-107">If you encounter a problem with Microsoft Defender Antivirus, you can search the tables in this topic to find a matching issue and potential solution.</span></span>

<span data-ttu-id="719cf-108">La lista de tablas:</span><span class="sxs-lookup"><span data-stu-id="719cf-108">The tables list:</span></span>

- <span data-ttu-id="719cf-109">[IDs de eventos](#windows-defender-av-ids) de Antivirus de Microsoft Defender (se aplican a Windows 10 y Windows Server 2016)</span><span class="sxs-lookup"><span data-stu-id="719cf-109">[Microsoft Defender Antivirus event IDs](#windows-defender-av-ids) (these apply to both Windows 10 and Windows Server 2016)</span></span>
- [<span data-ttu-id="719cf-110">Códigos de error de cliente de Antivirus de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="719cf-110">Microsoft Defender Antivirus client error codes</span></span>](#error-codes)
- [<span data-ttu-id="719cf-111">Códigos de error de cliente de Antivirus de Microsoft Defender internos (usados por Microsoft durante el desarrollo y las pruebas)</span><span class="sxs-lookup"><span data-stu-id="719cf-111">Internal Microsoft Defender Antivirus client error codes (used by Microsoft during development and testing)</span></span>](#internal-error-codes)

> [!TIP]
> <span data-ttu-id="719cf-112">También puede visitar el sitio web de demostración de Microsoft Defender para endpoint [en demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) para confirmar que funcionan las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="719cf-112">You can also visit the Microsoft Defender for Endpoint demo website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the following features are working:</span></span>
> 
> - <span data-ttu-id="719cf-113">Protección entregada en la nube</span><span class="sxs-lookup"><span data-stu-id="719cf-113">Cloud-delivered protection</span></span>
> - <span data-ttu-id="719cf-114">Aprendizaje rápido (incluido Bloquear a primera vista)</span><span class="sxs-lookup"><span data-stu-id="719cf-114">Fast learning (including Block at first sight)</span></span>
> - <span data-ttu-id="719cf-115">Bloqueo de aplicaciones potencialmente no deseado</span><span class="sxs-lookup"><span data-stu-id="719cf-115">Potentially unwanted application blocking</span></span>

<a id="windows-defender-av-ids"></a>
## <a name="microsoft-defender-antivirus-event-ids"></a><span data-ttu-id="719cf-116">IDs de eventos de Antivirus de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="719cf-116">Microsoft Defender Antivirus event IDs</span></span>

<span data-ttu-id="719cf-117">Antivirus de Microsoft Defender registra los IDs de eventos en el registro de eventos de Windows.</span><span class="sxs-lookup"><span data-stu-id="719cf-117">Microsoft Defender Antivirus records event IDs in the Windows event log.</span></span>

<span data-ttu-id="719cf-118">Puede ver directamente el registro de eventos, o si tiene una herramienta de administración de eventos y información de seguridad (SIEM) de terceros, también puede usar los [IDs](troubleshoot-microsoft-defender-antivirus.md#windows-defender-av-ids) de eventos del cliente antivirus de Microsoft Defender para revisar eventos y errores específicos de los puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="719cf-118">You can directly view the event log, or if you have a third-party security information and event management (SIEM) tool, you can also consume [Microsoft Defender Antivirus client event IDs](troubleshoot-microsoft-defender-antivirus.md#windows-defender-av-ids) to review specific events and errors from your endpoints.</span></span>

<span data-ttu-id="719cf-119">En la tabla de esta sección se enumeran los principales IDs de eventos de Antivirus de Microsoft Defender y, siempre que sea posible, se proporcionan soluciones sugeridas para corregir o resolver el error.</span><span class="sxs-lookup"><span data-stu-id="719cf-119">The table in this section lists the main Microsoft Defender Antivirus event IDs and, where possible, provides suggested solutions to fix or resolve the error.</span></span> 

## <a name="to-view-a-microsoft-defender-antivirus-event"></a><span data-ttu-id="719cf-120">Para ver un evento antivirus de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="719cf-120">To view a Microsoft Defender Antivirus event</span></span>

1.  <span data-ttu-id="719cf-121">Abra **el Visor de eventos**.</span><span class="sxs-lookup"><span data-stu-id="719cf-121">Open **Event Viewer**.</span></span>
2.  <span data-ttu-id="719cf-122">En el árbol de consola, expanda **Registros de aplicaciones y** servicios , a continuación, **Microsoft**, a continuación, **Windows** y, a continuación, **Windows Defender**.</span><span class="sxs-lookup"><span data-stu-id="719cf-122">In the console tree, expand **Applications and Services Logs**, then **Microsoft**, then **Windows**, then **Windows Defender**.</span></span>
3.  <span data-ttu-id="719cf-123">Haga doble clic en **Operativo**.</span><span class="sxs-lookup"><span data-stu-id="719cf-123">Double-click on **Operational**.</span></span>
4.  <span data-ttu-id="719cf-124">En el panel de detalles, vea la lista de eventos individuales para buscar el evento.</span><span class="sxs-lookup"><span data-stu-id="719cf-124">In the details pane, view the list of individual events to find your event.</span></span>
5.  <span data-ttu-id="719cf-125">Haga clic en el evento para ver detalles específicos sobre un evento en el panel inferior, en las **pestañas General** **y** Detalles.</span><span class="sxs-lookup"><span data-stu-id="719cf-125">Click the event to see specific details about an event in the lower pane, under the **General** and **Details** tabs.</span></span>

<table> 
<tr>
<th colspan="2" ><span data-ttu-id="719cf-126">Identificador de evento: 1000</span><span class="sxs-lookup"><span data-stu-id="719cf-126">Event ID: 1000</span></span></th>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-127">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="719cf-127">Symbolic name:</span></span>
</td>
<td><span data-ttu-id="719cf-128">
<b>MALWAREPROTECTION_SCAN_STARTED</b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-128">
<b>MALWAREPROTECTION_SCAN_STARTED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-129">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="719cf-129">Message:</span></span>
</td>
<td ><span data-ttu-id="719cf-130">
<b>Se inició un examen de antimalware. </b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-130">
<b>An antimalware scan started. </b>
</span></span></td>
</tr>
<tr>
<td >
<span data-ttu-id="719cf-131">Descripción:</span><span class="sxs-lookup"><span data-stu-id="719cf-131">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="719cf-132">
<dt>Id. de examen: &lt; Número de identificador del &gt; examen correspondiente.</dt> 
<dt> Tipo de examen: &lt; Tipo de examen , por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="719cf-132">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="719cf-133">Antivirus</span><span class="sxs-lookup"><span data-stu-id="719cf-133">Antivirus</span></span></li>
<li><span data-ttu-id="719cf-134">Antispyware</span><span class="sxs-lookup"><span data-stu-id="719cf-134">Antispyware</span></span></li>
<li><span data-ttu-id="719cf-135">Antimalware</span><span class="sxs-lookup"><span data-stu-id="719cf-135">Antimalware</span></span></li>
</ul><span data-ttu-id="719cf-136">
</dt>
<dt>Parámetros de examen: &lt; parámetros de examen , por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="719cf-136">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="719cf-137">Examen completo</span><span class="sxs-lookup"><span data-stu-id="719cf-137">Full scan</span></span></li>
<li><span data-ttu-id="719cf-138">Examen rápido</span><span class="sxs-lookup"><span data-stu-id="719cf-138">Quick scan</span></span></li>
<li><span data-ttu-id="719cf-139">Examen del cliente</span><span class="sxs-lookup"><span data-stu-id="719cf-139">Customer scan</span></span></li>
</ul><span data-ttu-id="719cf-140">
</dt>
<dt>Recursos de examen: &lt; Recursos (como archivos/directorios/BHO) que se &gt; examinaron.</dt> 
<dt>Usuario: &lt; Dominio &gt; \& lt; Usuario &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="719cf-140">
</dt>
<dt>Scan Resources: &lt;Resources (such as files/directories/BHO) that were scanned.&gt;</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="719cf-141">Identificador de evento: 1001</span><span class="sxs-lookup"><span data-stu-id="719cf-141">Event ID: 1001</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="719cf-142">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="719cf-142">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="719cf-143">
<b>MALWAREPROTECTION_SCAN_COMPLETED</b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-143">
<b>MALWAREPROTECTION_SCAN_COMPLETED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-144">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="719cf-144">Message:</span></span>
</td>
<td ><span data-ttu-id="719cf-145">
<b>Se ha finalizado un examen de antimalware.</b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-145">
<b>An antimalware scan finished.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-146">Descripción:</span><span class="sxs-lookup"><span data-stu-id="719cf-146">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="719cf-147">
<dt>Id. de examen: &lt; Número de identificador del &gt; examen correspondiente.</dt> 
<dt> Tipo de examen: &lt; Tipo de examen , por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="719cf-147">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="719cf-148">Antivirus</span><span class="sxs-lookup"><span data-stu-id="719cf-148">Antivirus</span></span></li>
<li><span data-ttu-id="719cf-149">Antispyware</span><span class="sxs-lookup"><span data-stu-id="719cf-149">Antispyware</span></span></li>
<li><span data-ttu-id="719cf-150">Antimalware</span><span class="sxs-lookup"><span data-stu-id="719cf-150">Antimalware</span></span></li>
</ul><span data-ttu-id="719cf-151">
</dt>
<dt>Parámetros de examen: &lt; parámetros de examen , por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="719cf-151">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="719cf-152">Examen completo</span><span class="sxs-lookup"><span data-stu-id="719cf-152">Full scan</span></span></li>
<li><span data-ttu-id="719cf-153">Examen rápido</span><span class="sxs-lookup"><span data-stu-id="719cf-153">Quick scan</span></span></li>
<li><span data-ttu-id="719cf-154">Examen del cliente</span><span class="sxs-lookup"><span data-stu-id="719cf-154">Customer scan</span></span></li>
</ul><span data-ttu-id="719cf-155">
</dt>
<dt>Usuario: &lt; Dominio &gt; \& lt; Tiempo &gt; </dt>
<dt>de examen del usuario: la &lt; duración de un examen. &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="719cf-155">
</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Scan Time: &lt;The duration of a scan.&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="719cf-156">Identificador de evento: 1002</span><span class="sxs-lookup"><span data-stu-id="719cf-156">Event ID: 1002</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="719cf-157">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="719cf-157">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="719cf-158">
<b>MALWAREPROTECTION_SCAN_CANCELLED </b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-158">
<b>MALWAREPROTECTION_SCAN_CANCELLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-159">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="719cf-159">Message:</span></span>
</td>
<td ><span data-ttu-id="719cf-160">
<b>Antes de finalizar, se detuvo un examen antimalware. </b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-160">
<b>An antimalware scan was stopped before it finished. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-161">Descripción:</span><span class="sxs-lookup"><span data-stu-id="719cf-161">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="719cf-162">
<dt>Id. de examen: &lt; Número de identificador del &gt; examen correspondiente.</dt> 
<dt> Tipo de examen: &lt; Tipo de examen , por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="719cf-162">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="719cf-163">Antivirus</span><span class="sxs-lookup"><span data-stu-id="719cf-163">Antivirus</span></span></li>
<li><span data-ttu-id="719cf-164">Antispyware</span><span class="sxs-lookup"><span data-stu-id="719cf-164">Antispyware</span></span></li>
<li><span data-ttu-id="719cf-165">Antimalware</span><span class="sxs-lookup"><span data-stu-id="719cf-165">Antimalware</span></span></li>
</ul><span data-ttu-id="719cf-166">
</dt>
<dt>Parámetros de examen: &lt; parámetros de examen , por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="719cf-166">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="719cf-167">Examen completo</span><span class="sxs-lookup"><span data-stu-id="719cf-167">Full scan</span></span></li>
<li><span data-ttu-id="719cf-168">Examen rápido</span><span class="sxs-lookup"><span data-stu-id="719cf-168">Quick scan</span></span></li>
<li><span data-ttu-id="719cf-169">Examen del cliente</span><span class="sxs-lookup"><span data-stu-id="719cf-169">Customer scan</span></span></li>
</ul><span data-ttu-id="719cf-170">
</dt>
<dt>Usuario: &lt; Dominio &gt; &amp; lt; Tiempo &gt; </dt>
<dt>de examen del usuario: la &lt; duración de un examen. &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="719cf-170">
</dt>
<dt>User: &lt;Domain&gt;&amp;lt;User&gt;</dt>
<dt>Scan Time: &lt;The duration of a scan.&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="719cf-171">Identificador de evento: 1003</span><span class="sxs-lookup"><span data-stu-id="719cf-171">Event ID: 1003</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="719cf-172">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="719cf-172">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="719cf-173">
<b>MALWAREPROTECTION_SCAN_PAUSED </b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-173">
<b>MALWAREPROTECTION_SCAN_PAUSED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-174">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="719cf-174">Message:</span></span>
</td>
<td ><span data-ttu-id="719cf-175">
<b>Se ha pausado un examen antimalware. </b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-175">
<b>An antimalware scan was paused. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-176">Descripción:</span><span class="sxs-lookup"><span data-stu-id="719cf-176">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="719cf-177">
<dt>Id. de examen: &lt; Número de identificador del &gt; examen correspondiente.</dt> 
<dt> Tipo de examen: &lt; Tipo de examen , por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="719cf-177">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="719cf-178">Antivirus</span><span class="sxs-lookup"><span data-stu-id="719cf-178">Antivirus</span></span></li>
<li><span data-ttu-id="719cf-179">Antispyware</span><span class="sxs-lookup"><span data-stu-id="719cf-179">Antispyware</span></span></li>
<li><span data-ttu-id="719cf-180">Antimalware</span><span class="sxs-lookup"><span data-stu-id="719cf-180">Antimalware</span></span></li>
</ul><span data-ttu-id="719cf-181">
</dt>
<dt>Parámetros de examen: &lt; parámetros de examen , por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="719cf-181">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="719cf-182">Examen completo</span><span class="sxs-lookup"><span data-stu-id="719cf-182">Full scan</span></span></li>
<li><span data-ttu-id="719cf-183">Examen rápido</span><span class="sxs-lookup"><span data-stu-id="719cf-183">Quick scan</span></span></li>
<li><span data-ttu-id="719cf-184">Examen del cliente</span><span class="sxs-lookup"><span data-stu-id="719cf-184">Customer scan</span></span></li>
</ul><span data-ttu-id="719cf-185">
</dt>
<dt>Usuario: &lt; Dominio &gt; \& lt; Usuario&gt;</dt>
</span><span class="sxs-lookup"><span data-stu-id="719cf-185">
</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="719cf-186">Identificador de evento: 1004</span><span class="sxs-lookup"><span data-stu-id="719cf-186">Event ID: 1004</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="719cf-187">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="719cf-187">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="719cf-188">
<b>MALWAREPROTECTION_SCAN_RESUMED </b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-188">
<b>MALWAREPROTECTION_SCAN_RESUMED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-189">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="719cf-189">Message:</span></span>
</td>
<td ><span data-ttu-id="719cf-190">
<b>Se reanudó un examen antimalware. </b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-190">
<b>An antimalware scan was resumed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-191">Descripción:</span><span class="sxs-lookup"><span data-stu-id="719cf-191">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="719cf-192">
<dt>Id. de examen: &lt; Número de identificador del &gt; examen correspondiente.</dt> 
<dt> Tipo de examen: &lt; Tipo de examen , por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="719cf-192">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="719cf-193">Antivirus</span><span class="sxs-lookup"><span data-stu-id="719cf-193">Antivirus</span></span></li>
<li><span data-ttu-id="719cf-194">Antispyware</span><span class="sxs-lookup"><span data-stu-id="719cf-194">Antispyware</span></span></li>
<li><span data-ttu-id="719cf-195">Antimalware</span><span class="sxs-lookup"><span data-stu-id="719cf-195">Antimalware</span></span></li>
</ul><span data-ttu-id="719cf-196">
</dt>
<dt>Parámetros de examen: &lt; parámetros de examen , por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="719cf-196">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="719cf-197">Examen completo</span><span class="sxs-lookup"><span data-stu-id="719cf-197">Full scan</span></span></li>
<li><span data-ttu-id="719cf-198">Examen rápido</span><span class="sxs-lookup"><span data-stu-id="719cf-198">Quick scan</span></span></li>
<li><span data-ttu-id="719cf-199">Examen del cliente</span><span class="sxs-lookup"><span data-stu-id="719cf-199">Customer scan</span></span></li>
</ul><span data-ttu-id="719cf-200">
</dt>
<dt>Usuario: &lt; Dominio &gt; \& lt; Usuario&gt;</dt>
</span><span class="sxs-lookup"><span data-stu-id="719cf-200">
</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="719cf-201">Identificador de evento: 1005</span><span class="sxs-lookup"><span data-stu-id="719cf-201">Event ID: 1005</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="719cf-202">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="719cf-202">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="719cf-203">
<b>MALWAREPROTECTION_SCAN_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-203">
<b>MALWAREPROTECTION_SCAN_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-204">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="719cf-204">Message:</span></span>
</td>
<td ><span data-ttu-id="719cf-205">
<b>Error en un examen antimalware. </b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-205">
<b>An antimalware scan failed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-206">Descripción:</span><span class="sxs-lookup"><span data-stu-id="719cf-206">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="719cf-207">
<dt>Id. de examen: &lt; Número de identificador del &gt; examen correspondiente.</dt> 
<dt> Tipo de examen: &lt; Tipo de examen , por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="719cf-207">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="719cf-208">Antivirus</span><span class="sxs-lookup"><span data-stu-id="719cf-208">Antivirus</span></span></li>
<li><span data-ttu-id="719cf-209">Antispyware</span><span class="sxs-lookup"><span data-stu-id="719cf-209">Antispyware</span></span></li>
<li><span data-ttu-id="719cf-210">Antimalware</span><span class="sxs-lookup"><span data-stu-id="719cf-210">Antimalware</span></span></li>
</ul><span data-ttu-id="719cf-211">
</dt>
<dt>Parámetros de examen: &lt; parámetros de examen , por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="719cf-211">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="719cf-212">Examen completo</span><span class="sxs-lookup"><span data-stu-id="719cf-212">Full scan</span></span></li>
<li><span data-ttu-id="719cf-213">Examen rápido</span><span class="sxs-lookup"><span data-stu-id="719cf-213">Quick scan</span></span></li>
<li><span data-ttu-id="719cf-214">Examen del cliente</span><span class="sxs-lookup"><span data-stu-id="719cf-214">Customer scan</span></span></li>
</ul><span data-ttu-id="719cf-215">
</dt>
<dt>Usuario: &lt; Dominio &gt; \& lt; Código &gt; </dt>
<dt>de error del usuario: Código de error &lt; Código de resultado asociado con el estado de &gt; amenaza. Valores HRESULT estándar.</dt> 
<dt>Descripción del error: &lt; Descripción del error &gt; Descripción del error.</dt>
</span><span class="sxs-lookup"><span data-stu-id="719cf-215">
</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-216">Acción del usuario:</span><span class="sxs-lookup"><span data-stu-id="719cf-216">User action:</span></span>
</td>
<td >
<span data-ttu-id="719cf-217">El cliente antivirus encontró un error y se detuvo el examen actual.</span><span class="sxs-lookup"><span data-stu-id="719cf-217">The antivirus client encountered an error, and the current scan has stopped.</span></span> <span data-ttu-id="719cf-218">El examen puede producir un error debido a un problema del lado cliente.</span><span class="sxs-lookup"><span data-stu-id="719cf-218">The scan might fail due to a client-side issue.</span></span> <span data-ttu-id="719cf-219">Este registro de evento incluye el identificador de examen, el tipo de examen (Antivirus de Microsoft Defender, antispyware, antimalware), parámetros de examen, el usuario que inició el examen, el código de error y una descripción del error.</span><span class="sxs-lookup"><span data-stu-id="719cf-219">This event record includes the scan ID, type of scan (Microsoft Defender Antivirus, antispyware, antimalware), scan parameters, the user that started the scan, the error code, and a description of the error.</span></span>
<span data-ttu-id="719cf-220">Para solucionar este evento:</span><span class="sxs-lookup"><span data-stu-id="719cf-220">To troubleshoot this event:</span></span>
<ol>
<li><span data-ttu-id="719cf-221">Vuelva a ejecutar el examen.</span><span class="sxs-lookup"><span data-stu-id="719cf-221">Run the scan again.</span></span></li>
<li><span data-ttu-id="719cf-222">Si se produce un error de la misma manera, vaya <b></b> al sitio de soporte técnico de <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft</a>, escriba el número de error en el cuadro Buscar para buscar el código de error.</span><span class="sxs-lookup"><span data-stu-id="719cf-222">If it fails in the same way, go to the <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft Support site</a>, enter the error number in the <b>Search</b> box to look for the error code.</span></span></li>
<li><span data-ttu-id="719cf-223">Contactar al <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Soporte técnico de Microsoft</a>.</span><span class="sxs-lookup"><span data-stu-id="719cf-223">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="719cf-224">Identificador de evento: 1006</span><span class="sxs-lookup"><span data-stu-id="719cf-224">Event ID: 1006</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="719cf-225">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="719cf-225">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="719cf-226">
<b>MALWAREPROTECTION_MALWARE_DETECTED </b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-226">
<b>MALWAREPROTECTION_MALWARE_DETECTED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-227">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="719cf-227">Message:</span></span>
</td>
<td ><span data-ttu-id="719cf-228">
<b>El motor de antimalware encontró malware u otro software potencialmente no deseado. </b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-228">
<b>The antimalware engine found malware or other potentially unwanted software. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-229">Descripción:</span><span class="sxs-lookup"><span data-stu-id="719cf-229">Description:</span></span>
</td>
<td >
<span data-ttu-id="719cf-230">Para obtener más información, vea los artículos siguientes: </span><span class="sxs-lookup"><span data-stu-id="719cf-230">For more information, see the following:</span></span>
<dl><span data-ttu-id="719cf-231">
<dt>Nombre: &lt; Id. &gt; de</dt>
<dt>nombre de &lt; amenaza: Gravedad del id. &gt; </dt>de 
<dt> amenaza: gravedad , por &lt; &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="719cf-231">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="719cf-232">Bajo</span><span class="sxs-lookup"><span data-stu-id="719cf-232">Low</span></span></li>
<li><span data-ttu-id="719cf-233">Moderado</span><span class="sxs-lookup"><span data-stu-id="719cf-233">Moderate</span></span></li>
<li><span data-ttu-id="719cf-234">Alto</span><span class="sxs-lookup"><span data-stu-id="719cf-234">High</span></span></li>
<li><span data-ttu-id="719cf-235">Grave</span><span class="sxs-lookup"><span data-stu-id="719cf-235">Severe</span></span></li>
</ul><span data-ttu-id="719cf-236">
</dt>
<dt>Categoría: &lt; Descripción de &gt; categoría , por ejemplo, cualquier tipo de amenaza o malware.</dt> 
<dt>Ruta de acceso: &lt; Origen &gt; de detección</dt>de ruta de 
<dt> acceso de &lt; archivo: Origen de &gt; detección, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="719cf-236">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span><ul>
<li><span data-ttu-id="719cf-237">Unknown</span><span class="sxs-lookup"><span data-stu-id="719cf-237">Unknown</span></span></li>
<li><span data-ttu-id="719cf-238">Equipo local</span><span class="sxs-lookup"><span data-stu-id="719cf-238">Local computer</span></span></li>
<li><span data-ttu-id="719cf-239">Recurso compartido de red</span><span class="sxs-lookup"><span data-stu-id="719cf-239">Network share</span></span></li>
<li><span data-ttu-id="719cf-240">Internet</span><span class="sxs-lookup"><span data-stu-id="719cf-240">Internet</span></span></li>
<li><span data-ttu-id="719cf-241">Tráfico entrante</span><span class="sxs-lookup"><span data-stu-id="719cf-241">Incoming traffic</span></span></li>
<li><span data-ttu-id="719cf-242">Tráfico saliente</span><span class="sxs-lookup"><span data-stu-id="719cf-242">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="719cf-243">
</dt>
<dt>Tipo de &lt; detección: Tipo de &gt; detección , por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="719cf-243">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="719cf-244">Heurística</span><span class="sxs-lookup"><span data-stu-id="719cf-244">Heuristics</span></span></li>
<li><span data-ttu-id="719cf-245">Generic</span><span class="sxs-lookup"><span data-stu-id="719cf-245">Generic</span></span></li>
<li><span data-ttu-id="719cf-246">Concreto</span><span class="sxs-lookup"><span data-stu-id="719cf-246">Concrete</span></span></li>
<li><span data-ttu-id="719cf-247">Firma dinámica</span><span class="sxs-lookup"><span data-stu-id="719cf-247">Dynamic signature</span></span></li>
</ul><span data-ttu-id="719cf-248">
</dt>
<dt>Origen de &lt; detección: origen de &gt; detección por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="719cf-248">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="719cf-249">Usuario: usuario iniciado</span><span class="sxs-lookup"><span data-stu-id="719cf-249">User: user initiated</span></span></li>
<li><span data-ttu-id="719cf-250">Sistema: sistema iniciado</span><span class="sxs-lookup"><span data-stu-id="719cf-250">System: system initiated</span></span></li>
<li><span data-ttu-id="719cf-251">En tiempo real: componente en tiempo real iniciado</span><span class="sxs-lookup"><span data-stu-id="719cf-251">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="719cf-252">IOAV: Descargas de IE y datos adjuntos de Outlook Express iniciados</span><span class="sxs-lookup"><span data-stu-id="719cf-252">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="719cf-253">NIS: sistema de inspección de red</span><span class="sxs-lookup"><span data-stu-id="719cf-253">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="719cf-254">IEPROTECT: IE - IExtensionValidation; esto protege contra controles de páginas web malintencionadas</span><span class="sxs-lookup"><span data-stu-id="719cf-254">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="719cf-255">Antimalware de inicio anticipado (ELAM).</span><span class="sxs-lookup"><span data-stu-id="719cf-255">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="719cf-256">Esto incluye malware detectado por la secuencia de arranque</span><span class="sxs-lookup"><span data-stu-id="719cf-256">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="719cf-257">Atestación remota</span><span class="sxs-lookup"><span data-stu-id="719cf-257">Remote attestation</span></span></li>
</ul><span data-ttu-id="719cf-258">Interfaz de examen antimalware (AMSI).</span><span class="sxs-lookup"><span data-stu-id="719cf-258">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="719cf-259">Se usa principalmente para proteger scripts (PS, VBS), aunque también pueden invocarse por terceros.</span><span class="sxs-lookup"><span data-stu-id="719cf-259">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="719cf-260">Estado de </dt> 
<dt>UAC: Usuario &lt; &gt; de</dt>
<dt>estado: Dominio &lt; &gt; \& lt; Nombre &gt; </dt>del proceso de usuario: proceso en la versión de firma
<dt> &lt; &gt; PID:</dt>versión
<dt> &lt; de &gt; </dt>definición Versión del
<dt>motor: versión del motor &lt; &gt; antimalware</dt>
</span><span class="sxs-lookup"><span data-stu-id="719cf-260">UAC</dt>
<dt>Status: &lt;Status&gt;</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="719cf-261">Identificador de evento: 1007</span><span class="sxs-lookup"><span data-stu-id="719cf-261">Event ID: 1007</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="719cf-262">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="719cf-262">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="719cf-263">
<b>MALWAREPROTECTION_MALWARE_ACTION_TAKEN </b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-263">
<b>MALWAREPROTECTION_MALWARE_ACTION_TAKEN </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-264">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="719cf-264">Message:</span></span>
</td>
<td ><span data-ttu-id="719cf-265">
<b>La plataforma antimalware realizó una acción para proteger el sistema de malware u otro software potencialmente no deseado. </b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-265">
<b>The antimalware platform performed an action to protect your system from malware or other potentially unwanted software. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-266">Descripción:</span><span class="sxs-lookup"><span data-stu-id="719cf-266">Description:</span></span>
</td>
<td >
<span data-ttu-id="719cf-267">Antivirus de Microsoft Defender ha tomado medidas para proteger esta máquina de malware u otro software potencialmente no deseado.</span><span class="sxs-lookup"><span data-stu-id="719cf-267">Microsoft Defender Antivirus has taken action to protect this machine from malware or other potentially unwanted software.</span></span> <span data-ttu-id="719cf-268">Para obtener más información, vea los artículos siguientes: </span><span class="sxs-lookup"><span data-stu-id="719cf-268">For more information, see the following:</span></span>
<dl><span data-ttu-id="719cf-269">
<dt>Usuario: &lt; Dominio &gt; \& lt; Nombre &gt; </dt>
<dt>de usuario: &lt; Identificador de nombre &gt; de</dt>
<dt>amenaza: &lt; &gt; Id.</dt>de amenaza 
<dt> Gravedad: Gravedad , por &lt; &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="719cf-269">
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="719cf-270">Bajo</span><span class="sxs-lookup"><span data-stu-id="719cf-270">Low</span></span></li>
<li><span data-ttu-id="719cf-271">Moderado</span><span class="sxs-lookup"><span data-stu-id="719cf-271">Moderate</span></span></li>
<li><span data-ttu-id="719cf-272">Alto</span><span class="sxs-lookup"><span data-stu-id="719cf-272">High</span></span></li>
<li><span data-ttu-id="719cf-273">Grave</span><span class="sxs-lookup"><span data-stu-id="719cf-273">Severe</span></span></li>
</ul><span data-ttu-id="719cf-274">
</dt>
<dt>Categoría: &lt; Descripción de &gt; categoría , por ejemplo, cualquier tipo de amenaza o malware.</dt> 
<dt> Action: &lt; Action , por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="719cf-274">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Action: &lt;Action&gt;, for example:</span></span><ul>
<li><span data-ttu-id="719cf-275">Clean: el recurso se ha limpiado</span><span class="sxs-lookup"><span data-stu-id="719cf-275">Clean: The resource was cleaned</span></span></li>
<li><span data-ttu-id="719cf-276">Cuarentena: el recurso se ha puesto en cuarentena</span><span class="sxs-lookup"><span data-stu-id="719cf-276">Quarantine: The resource was quarantined</span></span></li>
<li><span data-ttu-id="719cf-277">Quitar: se eliminó el recurso</span><span class="sxs-lookup"><span data-stu-id="719cf-277">Remove: The resource was deleted</span></span></li>
<li><span data-ttu-id="719cf-278">Permitir: se permitió que el recurso se ejecutara o existiera</span><span class="sxs-lookup"><span data-stu-id="719cf-278">Allow: The resource was allowed to execute/exist</span></span></li>
<li><span data-ttu-id="719cf-279">Definido por el usuario: acción definida por el usuario que normalmente es una de esta lista de acciones que el usuario ha especificado</span><span class="sxs-lookup"><span data-stu-id="719cf-279">User defined: User-defined action that is normally one from this list of actions that the user has specified</span></span></li>
<li><span data-ttu-id="719cf-280">Sin acción: sin acción</span><span class="sxs-lookup"><span data-stu-id="719cf-280">No action: No action</span></span></li>
<li><span data-ttu-id="719cf-281">Bloquear: se bloqueó el recurso para que no se ejecutara</span><span class="sxs-lookup"><span data-stu-id="719cf-281">Block: The resource was blocked from executing</span></span></li>
</ul><span data-ttu-id="719cf-282">
</dt>
<dt>Estado: &lt; Status &gt; </dt>
<dt>Signature Version: &lt; Definition version &gt; </dt>Engine
<dt>Version: &lt; Antimalware Engine version &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="719cf-282">
</dt>
<dt>Status: &lt;Status&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="719cf-283">Identificador de evento: 1008</span><span class="sxs-lookup"><span data-stu-id="719cf-283">Event ID: 1008</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="719cf-284">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="719cf-284">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="719cf-285">
<b>MALWAREPROTECTION_MALWARE_ACTION_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-285">
<b>MALWAREPROTECTION_MALWARE_ACTION_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-286">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="719cf-286">Message:</span></span>
</td>
<td ><span data-ttu-id="719cf-287">
<b>La plataforma antimalware intentó realizar una acción para proteger el sistema de malware u otro software potencialmente no deseado, pero la acción falló.</b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-287">
<b>The antimalware platform attempted to perform an action to protect your system from malware or other potentially unwanted software, but the action failed.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-288">Descripción:</span><span class="sxs-lookup"><span data-stu-id="719cf-288">Description:</span></span>
</td>
<td >
<span data-ttu-id="719cf-289">Antivirus de Microsoft Defender ha encontrado un error al tomar medidas en malware u otro software potencialmente no deseado.</span><span class="sxs-lookup"><span data-stu-id="719cf-289">Microsoft Defender Antivirus has encountered an error when taking action on malware or other potentially unwanted software.</span></span> <span data-ttu-id="719cf-290">Para obtener más información, vea los artículos siguientes: </span><span class="sxs-lookup"><span data-stu-id="719cf-290">For more information, see the following:</span></span>
<dl><span data-ttu-id="719cf-291">
<dt>Usuario: &lt; Dominio &gt; \& lt; Nombre &gt; </dt>
<dt>de usuario: &lt; Identificador de nombre &gt; de</dt>
<dt>amenaza: &lt; &gt; Id.</dt>de amenaza 
<dt> Gravedad: Gravedad , por &lt; &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="719cf-291">
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="719cf-292">Bajo</span><span class="sxs-lookup"><span data-stu-id="719cf-292">Low</span></span></li>
<li><span data-ttu-id="719cf-293">Moderado</span><span class="sxs-lookup"><span data-stu-id="719cf-293">Moderate</span></span></li>
<li><span data-ttu-id="719cf-294">Alto</span><span class="sxs-lookup"><span data-stu-id="719cf-294">High</span></span></li>
<li><span data-ttu-id="719cf-295">Grave</span><span class="sxs-lookup"><span data-stu-id="719cf-295">Severe</span></span></li>
</ul><span data-ttu-id="719cf-296">
</dt>
<dt>Categoría: &lt; Descripción de &gt; categoría , por ejemplo, cualquier tipo de amenaza o malware.</dt> 
<dt>Ruta de acceso: &lt; Ruta &gt; de acceso</dt> 
<dt> de archivo &lt; Acción: Acción , por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="719cf-296">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Action: &lt;Action&gt;, for example:</span></span><ul>
<li><span data-ttu-id="719cf-297">Clean: el recurso se ha limpiado</span><span class="sxs-lookup"><span data-stu-id="719cf-297">Clean: The resource was cleaned</span></span></li>
<li><span data-ttu-id="719cf-298">Cuarentena: el recurso se ha puesto en cuarentena</span><span class="sxs-lookup"><span data-stu-id="719cf-298">Quarantine: The resource was quarantined</span></span></li>
<li><span data-ttu-id="719cf-299">Quitar: se eliminó el recurso</span><span class="sxs-lookup"><span data-stu-id="719cf-299">Remove: The resource was deleted</span></span></li>
<li><span data-ttu-id="719cf-300">Permitir: se permitió que el recurso se ejecutara o existiera</span><span class="sxs-lookup"><span data-stu-id="719cf-300">Allow: The resource was allowed to execute/exist</span></span></li>
<li><span data-ttu-id="719cf-301">Definido por el usuario: acción definida por el usuario que normalmente es una de esta lista de acciones que el usuario ha especificado</span><span class="sxs-lookup"><span data-stu-id="719cf-301">User defined: User-defined action that is normally one from this list of actions that the user has specified</span></span></li>
<li><span data-ttu-id="719cf-302">Sin acción: sin acción</span><span class="sxs-lookup"><span data-stu-id="719cf-302">No action: No action</span></span></li>
<li><span data-ttu-id="719cf-303">Bloquear: se bloqueó el recurso para que no se ejecutara</span><span class="sxs-lookup"><span data-stu-id="719cf-303">Block: The resource was blocked from executing</span></span></li>
</ul><span data-ttu-id="719cf-304">
</dt>
<dt>Código de error: &lt; Código de error &gt; Código de resultado asociado con el estado de amenaza. Valores HRESULT estándar. </dt> 
<dt>Descripción del error: &lt; Descripción del error Descripción del &gt; error.</dt> 
<dt>Estado: &lt; Status &gt; </dt>
<dt>Signature Version: &lt; Definition version &gt; </dt>Engine
<dt>Version: &lt; Antimalware Engine version &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="719cf-304">
</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values. </dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Status: &lt;Status&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="719cf-305">Identificador de evento: 1009</span><span class="sxs-lookup"><span data-stu-id="719cf-305">Event ID: 1009</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="719cf-306">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="719cf-306">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="719cf-307">
<b>MALWAREPROTECTION_QUARANTINE_RESTORE </b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-307">
<b>MALWAREPROTECTION_QUARANTINE_RESTORE </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-308">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="719cf-308">Message:</span></span>
</td>
<td ><span data-ttu-id="719cf-309">
<b>La plataforma antimalware restauró un elemento de cuarentena. </b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-309">
<b>The antimalware platform restored an item from quarantine. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-310">Descripción:</span><span class="sxs-lookup"><span data-stu-id="719cf-310">Description:</span></span>
</td>
<td >
<span data-ttu-id="719cf-311">Antivirus de Microsoft Defender ha restaurado un elemento de cuarentena.</span><span class="sxs-lookup"><span data-stu-id="719cf-311">Microsoft Defender Antivirus has restored an item from quarantine.</span></span> <span data-ttu-id="719cf-312">Para obtener más información, vea los artículos siguientes: </span><span class="sxs-lookup"><span data-stu-id="719cf-312">For more information, see the following:</span></span>
<dl><span data-ttu-id="719cf-313">
<dt>Nombre: &lt; Id. &gt; de</dt>
<dt>nombre de &lt; amenaza: Gravedad del id. &gt; </dt>de 
<dt> amenaza: gravedad , por &lt; &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="719cf-313">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="719cf-314">Bajo</span><span class="sxs-lookup"><span data-stu-id="719cf-314">Low</span></span></li>
<li><span data-ttu-id="719cf-315">Moderado</span><span class="sxs-lookup"><span data-stu-id="719cf-315">Moderate</span></span></li>
<li><span data-ttu-id="719cf-316">Alto</span><span class="sxs-lookup"><span data-stu-id="719cf-316">High</span></span></li>
<li><span data-ttu-id="719cf-317">Grave</span><span class="sxs-lookup"><span data-stu-id="719cf-317">Severe</span></span></li>
</ul><span data-ttu-id="719cf-318">
</dt>
<dt>Categoría: &lt; Descripción de &gt; categoría , por ejemplo, cualquier tipo de amenaza o malware.</dt> 
<dt>Ruta de acceso: &lt; Usuario &gt; de ruta de</dt>
<dt>acceso de &lt; archivo: Dominio &gt; \& lt; User &gt; </dt>
<dt>Signature Version: &lt; Definition version &gt; </dt>Engine
<dt>Version: &lt; Antimalware Engine version &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="719cf-318">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="719cf-319">Identificador de evento: 1010</span><span class="sxs-lookup"><span data-stu-id="719cf-319">Event ID: 1010</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="719cf-320">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="719cf-320">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="719cf-321">
<b>MALWAREPROTECTION_QUARANTINE_RESTORE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-321">
<b>MALWAREPROTECTION_QUARANTINE_RESTORE_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-322">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="719cf-322">Message:</span></span>
</td>
<td ><span data-ttu-id="719cf-323">
<b>La plataforma antimalware no pudo restaurar un elemento de cuarentena. </b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-323">
<b>The antimalware platform could not restore an item from quarantine. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-324">Descripción:</span><span class="sxs-lookup"><span data-stu-id="719cf-324">Description:</span></span>
</td>
<td >
<span data-ttu-id="719cf-325">Antivirus de Microsoft Defender ha encontrado un error al intentar restaurar un elemento desde la cuarentena.</span><span class="sxs-lookup"><span data-stu-id="719cf-325">Microsoft Defender Antivirus has encountered an error trying to restore an item from quarantine.</span></span> <span data-ttu-id="719cf-326">Para obtener más información, vea los artículos siguientes: </span><span class="sxs-lookup"><span data-stu-id="719cf-326">For more information, see the following:</span></span>
<dl><span data-ttu-id="719cf-327">
<dt>Nombre: &lt; Id. &gt; de</dt>
<dt>nombre de &lt; amenaza: Gravedad del id. &gt; </dt>de 
<dt> amenaza: gravedad , por &lt; &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="719cf-327">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="719cf-328">Bajo</span><span class="sxs-lookup"><span data-stu-id="719cf-328">Low</span></span></li>
<li><span data-ttu-id="719cf-329">Moderado</span><span class="sxs-lookup"><span data-stu-id="719cf-329">Moderate</span></span></li>
<li><span data-ttu-id="719cf-330">Alto</span><span class="sxs-lookup"><span data-stu-id="719cf-330">High</span></span></li>
<li><span data-ttu-id="719cf-331">Grave</span><span class="sxs-lookup"><span data-stu-id="719cf-331">Severe</span></span></li>
</ul><span data-ttu-id="719cf-332">
</dt>
<dt>Categoría: &lt; Descripción de &gt; categoría , por ejemplo, cualquier tipo de amenaza o malware.</dt> 
<dt>Ruta de acceso: &lt; Usuario &gt; de ruta de</dt>
<dt>acceso de &lt; archivo: Dominio &gt; \& lt; Código &gt; </dt>
<dt>de error del usuario: Código de error &lt; Código de resultado asociado con el estado de &gt; amenaza. Valores HRESULT estándar. </dt> 
<dt>Descripción del error: &lt; Descripción del error Descripción del &gt; error.</dt> 
<dt>Versión de firma: &lt; Versión &gt; de definición</dt>
<dt>Versión del motor: &lt; versión &gt; del motor antimalware</dt>
</span><span class="sxs-lookup"><span data-stu-id="719cf-332">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values. </dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="719cf-333">Identificador de evento: 1011</span><span class="sxs-lookup"><span data-stu-id="719cf-333">Event ID: 1011</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="719cf-334">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="719cf-334">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="719cf-335">
<b>MALWAREPROTECTION_QUARANTINE_DELETE</b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-335">
<b>MALWAREPROTECTION_QUARANTINE_DELETE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-336">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="719cf-336">Message:</span></span>
</td>
<td ><span data-ttu-id="719cf-337">
<b>La plataforma antimalware eliminó un elemento de la cuarentena. </b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-337">
<b>The antimalware platform deleted an item from quarantine. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-338">Descripción:</span><span class="sxs-lookup"><span data-stu-id="719cf-338">Description:</span></span>
</td>
<td >
<span data-ttu-id="719cf-339">Antivirus de Microsoft Defender ha eliminado un elemento de la cuarentena.</span><span class="sxs-lookup"><span data-stu-id="719cf-339">Microsoft Defender Antivirus has deleted an item from quarantine.</span></span><br/><span data-ttu-id="719cf-340">Para obtener más información, vea los artículos siguientes: </span><span class="sxs-lookup"><span data-stu-id="719cf-340">For more information, see the following:</span></span>
<dl><span data-ttu-id="719cf-341">
<dt>Nombre: &lt; Id. &gt; de</dt>
<dt>nombre de &lt; amenaza: Gravedad del id. &gt; </dt>de 
<dt> amenaza: gravedad , por &lt; &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="719cf-341">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="719cf-342">Bajo</span><span class="sxs-lookup"><span data-stu-id="719cf-342">Low</span></span></li>
<li><span data-ttu-id="719cf-343">Moderado</span><span class="sxs-lookup"><span data-stu-id="719cf-343">Moderate</span></span></li>
<li><span data-ttu-id="719cf-344">Alto</span><span class="sxs-lookup"><span data-stu-id="719cf-344">High</span></span></li>
<li><span data-ttu-id="719cf-345">Grave</span><span class="sxs-lookup"><span data-stu-id="719cf-345">Severe</span></span></li>
</ul><span data-ttu-id="719cf-346">
</dt>
<dt>Categoría: &lt; Descripción de &gt; categoría , por ejemplo, cualquier tipo de amenaza o malware.</dt> 
<dt>Ruta de acceso: &lt; Usuario &gt; de ruta de</dt>
<dt>acceso de &lt; archivo: Dominio &gt; \& lt; User &gt; </dt>
<dt>Signature Version: &lt; Definition version &gt; </dt>Engine
<dt>Version: &lt; Antimalware Engine version &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="719cf-346">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="719cf-347">Identificador de evento: 1012</span><span class="sxs-lookup"><span data-stu-id="719cf-347">Event ID: 1012</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="719cf-348">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="719cf-348">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="719cf-349">
<b>MALWAREPROTECTION_QUARANTINE_DELETE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-349">
<b>MALWAREPROTECTION_QUARANTINE_DELETE_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-350">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="719cf-350">Message:</span></span>
</td>
<td ><span data-ttu-id="719cf-351">
<b>La plataforma antimalware no pudo eliminar un elemento de la cuarentena.</b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-351">
<b>The antimalware platform could not delete an item from quarantine.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-352">Descripción:</span><span class="sxs-lookup"><span data-stu-id="719cf-352">Description:</span></span>
</td>
<td >
<span data-ttu-id="719cf-353">Antivirus de Microsoft Defender ha encontrado un error al intentar eliminar un elemento de la cuarentena.</span><span class="sxs-lookup"><span data-stu-id="719cf-353">Microsoft Defender Antivirus has encountered an error trying to delete an item from quarantine.</span></span>
<span data-ttu-id="719cf-354">Para obtener más información, vea los artículos siguientes: </span><span class="sxs-lookup"><span data-stu-id="719cf-354">For more information, see the following:</span></span>
<dl><span data-ttu-id="719cf-355">
<dt>Nombre: &lt; Id. &gt; de</dt>
<dt>nombre de &lt; amenaza: Gravedad del id. &gt; </dt>de 
<dt> amenaza: gravedad , por &lt; &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="719cf-355">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="719cf-356">Bajo</span><span class="sxs-lookup"><span data-stu-id="719cf-356">Low</span></span></li>
<li><span data-ttu-id="719cf-357">Moderado</span><span class="sxs-lookup"><span data-stu-id="719cf-357">Moderate</span></span></li>
<li><span data-ttu-id="719cf-358">Alto</span><span class="sxs-lookup"><span data-stu-id="719cf-358">High</span></span></li>
<li><span data-ttu-id="719cf-359">Grave</span><span class="sxs-lookup"><span data-stu-id="719cf-359">Severe</span></span></li>
</ul><span data-ttu-id="719cf-360">
</dt>
<dt>Categoría: &lt; Descripción de &gt; categoría , por ejemplo, cualquier tipo de amenaza o malware.</dt> 
<dt>Ruta de acceso: &lt; Usuario &gt; de ruta de</dt>
<dt>acceso de &lt; archivo: Dominio &gt; \& lt; Código &gt; </dt>
<dt>de error del usuario: Código de error &lt; Código de resultado asociado con el estado de &gt; amenaza. Valores HRESULT estándar. </dt> 
<dt>Descripción del error: &lt; Descripción del error Descripción del &gt; error.</dt> 
<dt>Versión de firma: &lt; Versión &gt; de definición</dt>
<dt>Versión del motor: &lt; versión &gt; del motor antimalware</dt>
</span><span class="sxs-lookup"><span data-stu-id="719cf-360">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values. </dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="719cf-361">Identificador de evento: 1013</span><span class="sxs-lookup"><span data-stu-id="719cf-361">Event ID: 1013</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="719cf-362">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="719cf-362">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="719cf-363">
<b>MALWAREPROTECTION_MALWARE_HISTORY_DELETE </b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-363">
<b>MALWAREPROTECTION_MALWARE_HISTORY_DELETE </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-364">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="719cf-364">Message:</span></span>
</td>
<td ><span data-ttu-id="719cf-365">
<b>La plataforma antimalware eliminó el historial de malware y otro software potencialmente no deseado.</b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-365">
<b>The antimalware platform deleted history of malware and other potentially unwanted software.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-366">Descripción:</span><span class="sxs-lookup"><span data-stu-id="719cf-366">Description:</span></span>
</td>
<td >
<span data-ttu-id="719cf-367">Antivirus de Microsoft Defender ha eliminado el historial de malware y otro software potencialmente no deseado.</span><span class="sxs-lookup"><span data-stu-id="719cf-367">Microsoft Defender Antivirus has removed history of malware and other potentially unwanted software.</span></span>
<dl><span data-ttu-id="719cf-368">
<dt>Hora: hora en la que se produjo el evento, por ejemplo, cuando se purga el historial. Este parámetro no se usa en eventos de amenazas para que no haya confusión con respecto a si es tiempo de corrección o tiempo de infección. Para ellos, los llamamos específicamente tiempo de acción o tiempo de detección.</dt> 
<dt>Usuario: &lt; Dominio &gt; \& lt; Usuario &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="719cf-368">
<dt>Time: The time when the event occurred, for example when the history is purged. This parameter is not used in threat events so that there is no confusion regarding whether it is remediation time or infection time. For those, we specifically call them as Action Time or Detection Time.</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="719cf-369">Identificador de evento: 1014</span><span class="sxs-lookup"><span data-stu-id="719cf-369">Event ID: 1014</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="719cf-370">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="719cf-370">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="719cf-371">
<b>MALWAREPROTECTION_MALWARE_HISTORY_DELETE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-371">
<b>MALWAREPROTECTION_MALWARE_HISTORY_DELETE_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-372">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="719cf-372">Message:</span></span>
</td>
<td >
<span data-ttu-id="719cf-373">La plataforma antimalware no pudo eliminar el historial de malware y otro software potencialmente no deseado.</span><span class="sxs-lookup"><span data-stu-id="719cf-373">The antimalware platform could not delete history of malware and other potentially unwanted software.</span></span>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-374">Descripción:</span><span class="sxs-lookup"><span data-stu-id="719cf-374">Description:</span></span>
</td>
<td >
<span data-ttu-id="719cf-375">Antivirus de Microsoft Defender ha encontrado un error al intentar quitar el historial de malware y otro software potencialmente no deseado.</span><span class="sxs-lookup"><span data-stu-id="719cf-375">Microsoft Defender Antivirus has encountered an error trying to remove history of malware and other potentially unwanted software.</span></span>
<dl><span data-ttu-id="719cf-376">
<dt>Hora: hora en la que se produjo el evento, por ejemplo, cuando se purga el historial. Este parámetro no se usa en eventos de amenazas para que no haya confusión con respecto a si es tiempo de corrección o tiempo de infección. Para ellos, los llamamos específicamente tiempo de acción o tiempo de detección.</dt> 
<dt>Usuario: &lt; Dominio &gt; \& lt; Código &gt; </dt>
<dt>de error del usuario: Código de error &lt; Código de resultado asociado con el estado de &gt; amenaza. Valores HRESULT estándar. </dt> 
<dt>Descripción del error: &lt; Descripción del error Descripción del &gt; error.</dt>
</span><span class="sxs-lookup"><span data-stu-id="719cf-376">
<dt>Time: The time when the event occurred, for example when the history is purged. This parameter is not used in threat events so that there is no confusion regarding whether it is remediation time or infection time. For those, we specifically call them as Action Time or Detection Time.</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values. </dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="719cf-377">Identificador de evento: 1015</span><span class="sxs-lookup"><span data-stu-id="719cf-377">Event ID: 1015</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="719cf-378">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="719cf-378">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="719cf-379">
<b>MALWAREPROTECTION_BEHAVIOR_DETECTED </b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-379">
<b>MALWAREPROTECTION_BEHAVIOR_DETECTED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-380">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="719cf-380">Message:</span></span>
</td>
<td ><span data-ttu-id="719cf-381">
<b>La plataforma antimalware detectó un comportamiento sospechoso.</b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-381">
<b>The antimalware platform detected suspicious behavior.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-382">Descripción:</span><span class="sxs-lookup"><span data-stu-id="719cf-382">Description:</span></span>
</td>
<td >
<span data-ttu-id="719cf-383">Antivirus de Microsoft Defender ha detectado un comportamiento sospechoso.</span><span class="sxs-lookup"><span data-stu-id="719cf-383">Microsoft Defender Antivirus has detected a suspicious behavior.</span></span><br/><span data-ttu-id="719cf-384">Para obtener más información, vea los artículos siguientes: </span><span class="sxs-lookup"><span data-stu-id="719cf-384">For more information, see the following:</span></span>
<dl><span data-ttu-id="719cf-385">
<dt>Nombre: &lt; Id. &gt; de</dt>
<dt>nombre de &lt; amenaza: Gravedad del id. &gt; </dt>de 
<dt> amenaza: gravedad , por &lt; &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="719cf-385">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="719cf-386">Bajo</span><span class="sxs-lookup"><span data-stu-id="719cf-386">Low</span></span></li>
<li><span data-ttu-id="719cf-387">Moderado</span><span class="sxs-lookup"><span data-stu-id="719cf-387">Moderate</span></span></li>
<li><span data-ttu-id="719cf-388">Alto</span><span class="sxs-lookup"><span data-stu-id="719cf-388">High</span></span></li>
<li><span data-ttu-id="719cf-389">Grave</span><span class="sxs-lookup"><span data-stu-id="719cf-389">Severe</span></span></li>
</ul><span data-ttu-id="719cf-390">
</dt>
<dt>Categoría: &lt; Descripción de &gt; categoría , por ejemplo, cualquier tipo de amenaza o malware.</dt> 
<dt>Ruta de acceso: &lt; Origen &gt; de detección</dt>de ruta de 
<dt> acceso de &lt; archivo: Origen de &gt; detección, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="719cf-390">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="719cf-391">Unknown</span><span class="sxs-lookup"><span data-stu-id="719cf-391">Unknown</span></span></li>
<li><span data-ttu-id="719cf-392">Equipo local</span><span class="sxs-lookup"><span data-stu-id="719cf-392">Local computer</span></span></li>
<li><span data-ttu-id="719cf-393">Recurso compartido de red</span><span class="sxs-lookup"><span data-stu-id="719cf-393">Network share</span></span></li>
<li><span data-ttu-id="719cf-394">Internet</span><span class="sxs-lookup"><span data-stu-id="719cf-394">Internet</span></span></li>
<li><span data-ttu-id="719cf-395">Tráfico entrante</span><span class="sxs-lookup"><span data-stu-id="719cf-395">Incoming traffic</span></span></li>
<li><span data-ttu-id="719cf-396">Tráfico saliente</span><span class="sxs-lookup"><span data-stu-id="719cf-396">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="719cf-397">
</dt>
<dt>Tipo de &lt; detección: Tipo de &gt; detección , por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="719cf-397">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="719cf-398">Heurística</span><span class="sxs-lookup"><span data-stu-id="719cf-398">Heuristics</span></span></li>
<li><span data-ttu-id="719cf-399">Generic</span><span class="sxs-lookup"><span data-stu-id="719cf-399">Generic</span></span></li>
<li><span data-ttu-id="719cf-400">Concreto</span><span class="sxs-lookup"><span data-stu-id="719cf-400">Concrete</span></span></li>
<li><span data-ttu-id="719cf-401">Firma dinámica</span><span class="sxs-lookup"><span data-stu-id="719cf-401">Dynamic signature</span></span></li>
</ul><span data-ttu-id="719cf-402">
</dt>
<dt>Origen de &lt; detección: origen de &gt; detección por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="719cf-402">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="719cf-403">Usuario: usuario iniciado</span><span class="sxs-lookup"><span data-stu-id="719cf-403">User: user initiated</span></span></li>
<li><span data-ttu-id="719cf-404">Sistema: sistema iniciado</span><span class="sxs-lookup"><span data-stu-id="719cf-404">System: system initiated</span></span></li>
<li><span data-ttu-id="719cf-405">En tiempo real: componente en tiempo real iniciado</span><span class="sxs-lookup"><span data-stu-id="719cf-405">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="719cf-406">IOAV: Descargas de IE y datos adjuntos de Outlook Express iniciados</span><span class="sxs-lookup"><span data-stu-id="719cf-406">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="719cf-407">NIS: sistema de inspección de red</span><span class="sxs-lookup"><span data-stu-id="719cf-407">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="719cf-408">IEPROTECT: IE - IExtensionValidation; esto protege contra controles de páginas web malintencionadas</span><span class="sxs-lookup"><span data-stu-id="719cf-408">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="719cf-409">Antimalware de inicio anticipado (ELAM).</span><span class="sxs-lookup"><span data-stu-id="719cf-409">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="719cf-410">Esto incluye malware detectado por la secuencia de arranque</span><span class="sxs-lookup"><span data-stu-id="719cf-410">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="719cf-411">Atestación remota</span><span class="sxs-lookup"><span data-stu-id="719cf-411">Remote attestation</span></span></li>
</ul><span data-ttu-id="719cf-412">Interfaz de examen antimalware (AMSI).</span><span class="sxs-lookup"><span data-stu-id="719cf-412">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="719cf-413">Se usa principalmente para proteger scripts (PS, VBS), aunque también pueden invocarse por terceros.</span><span class="sxs-lookup"><span data-stu-id="719cf-413">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="719cf-414">Estado de </dt> 
<dt>UAC: Usuario &lt; &gt; de</dt>
<dt>estado: Dominio &lt; &gt; \& lt; Nombre &gt; </dt>del proceso de usuario: proceso en el identificador de firma
<dt> &lt; &gt; PID:</dt>
<dt>Gravedad de coincidencia de enumeración.</dt> 
<dt>Versión de firma: &lt; Versión &gt; de definición</dt>
<dt>Engine Version: &lt; Antimalware Engine version &gt; </dt>Fidelity
<dt>Label:</dt>
<dt>Target File Name: File name Name of the &lt; &gt; file.</dt>
</span><span class="sxs-lookup"><span data-stu-id="719cf-414">UAC</dt>
<dt>Status: &lt;Status&gt;</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Signature ID: Enumeration matching severity.</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
<dt>Fidelity Label:</dt>
<dt>Target File Name: &lt;File name&gt; Name of the file.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="719cf-415">Identificador de evento: 1116</span><span class="sxs-lookup"><span data-stu-id="719cf-415">Event ID: 1116</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="719cf-416">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="719cf-416">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="719cf-417">
<b>MALWAREPROTECTION_STATE_MALWARE_DETECTED</b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-417">
<b>MALWAREPROTECTION_STATE_MALWARE_DETECTED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-418">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="719cf-418">Message:</span></span>
</td>
<td ><span data-ttu-id="719cf-419">
<b>La plataforma antimalware detectó malware u otro software potencialmente no deseado. </b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-419">
<b>The antimalware platform detected malware or other potentially unwanted software. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-420">Descripción:</span><span class="sxs-lookup"><span data-stu-id="719cf-420">Description:</span></span>
</td>
<td >
<span data-ttu-id="719cf-421">Antivirus de Microsoft Defender ha detectado malware u otro software potencialmente no deseado.</span><span class="sxs-lookup"><span data-stu-id="719cf-421">Microsoft Defender Antivirus has detected malware or other potentially unwanted software.</span></span><br/><span data-ttu-id="719cf-422">Para obtener más información, vea los artículos siguientes: </span><span class="sxs-lookup"><span data-stu-id="719cf-422">For more information, see the following:</span></span>
<dl><span data-ttu-id="719cf-423">
<dt>Nombre: &lt; Id. &gt; de</dt>
<dt>nombre de &lt; amenaza: Gravedad del id. &gt; </dt>de 
<dt> amenaza: gravedad , por &lt; &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="719cf-423">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="719cf-424">Bajo</span><span class="sxs-lookup"><span data-stu-id="719cf-424">Low</span></span></li>
<li><span data-ttu-id="719cf-425">Moderado</span><span class="sxs-lookup"><span data-stu-id="719cf-425">Moderate</span></span></li>
<li><span data-ttu-id="719cf-426">Alto</span><span class="sxs-lookup"><span data-stu-id="719cf-426">High</span></span></li>
<li><span data-ttu-id="719cf-427">Grave</span><span class="sxs-lookup"><span data-stu-id="719cf-427">Severe</span></span></li>
</ul><span data-ttu-id="719cf-428">
</dt>
<dt>Categoría: &lt; Descripción de &gt; categoría , por ejemplo, cualquier tipo de amenaza o malware.</dt> 
<dt>Ruta de acceso: &lt; Origen &gt; de detección</dt>de ruta de 
<dt> acceso de &lt; archivo: Origen de &gt; detección, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="719cf-428">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="719cf-429">Unknown</span><span class="sxs-lookup"><span data-stu-id="719cf-429">Unknown</span></span></li>
<li><span data-ttu-id="719cf-430">Equipo local</span><span class="sxs-lookup"><span data-stu-id="719cf-430">Local computer</span></span></li>
<li><span data-ttu-id="719cf-431">Recurso compartido de red</span><span class="sxs-lookup"><span data-stu-id="719cf-431">Network share</span></span></li>
<li><span data-ttu-id="719cf-432">Internet</span><span class="sxs-lookup"><span data-stu-id="719cf-432">Internet</span></span></li>
<li><span data-ttu-id="719cf-433">Tráfico entrante</span><span class="sxs-lookup"><span data-stu-id="719cf-433">Incoming traffic</span></span></li>
<li><span data-ttu-id="719cf-434">Tráfico saliente</span><span class="sxs-lookup"><span data-stu-id="719cf-434">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="719cf-435">
</dt>
<dt>Tipo de &lt; detección: Tipo de &gt; detección , por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="719cf-435">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="719cf-436">Heurística</span><span class="sxs-lookup"><span data-stu-id="719cf-436">Heuristics</span></span></li>
<li><span data-ttu-id="719cf-437">Generic</span><span class="sxs-lookup"><span data-stu-id="719cf-437">Generic</span></span></li>
<li><span data-ttu-id="719cf-438">Concreto</span><span class="sxs-lookup"><span data-stu-id="719cf-438">Concrete</span></span></li>
<li><span data-ttu-id="719cf-439">Firma dinámica</span><span class="sxs-lookup"><span data-stu-id="719cf-439">Dynamic signature</span></span></li>
</ul><span data-ttu-id="719cf-440">
</dt>
<dt>Origen de &lt; detección: origen de &gt; detección por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="719cf-440">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="719cf-441">Usuario: usuario iniciado</span><span class="sxs-lookup"><span data-stu-id="719cf-441">User: user initiated</span></span></li>
<li><span data-ttu-id="719cf-442">Sistema: sistema iniciado</span><span class="sxs-lookup"><span data-stu-id="719cf-442">System: system initiated</span></span></li>
<li><span data-ttu-id="719cf-443">En tiempo real: componente en tiempo real iniciado</span><span class="sxs-lookup"><span data-stu-id="719cf-443">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="719cf-444">IOAV: Descargas de IE y datos adjuntos de Outlook Express iniciados</span><span class="sxs-lookup"><span data-stu-id="719cf-444">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="719cf-445">NIS: sistema de inspección de red</span><span class="sxs-lookup"><span data-stu-id="719cf-445">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="719cf-446">IEPROTECT: IE - IExtensionValidation; esto protege contra controles de páginas web malintencionadas</span><span class="sxs-lookup"><span data-stu-id="719cf-446">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="719cf-447">Antimalware de inicio anticipado (ELAM).</span><span class="sxs-lookup"><span data-stu-id="719cf-447">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="719cf-448">Esto incluye malware detectado por la secuencia de arranque</span><span class="sxs-lookup"><span data-stu-id="719cf-448">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="719cf-449">Atestación remota</span><span class="sxs-lookup"><span data-stu-id="719cf-449">Remote attestation</span></span></li>
</ul><span data-ttu-id="719cf-450">Interfaz de examen antimalware (AMSI).</span><span class="sxs-lookup"><span data-stu-id="719cf-450">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="719cf-451">Se usa principalmente para proteger scripts (PS, VBS), aunque también pueden invocarse por terceros.</span><span class="sxs-lookup"><span data-stu-id="719cf-451">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="719cf-452">Usuario de </dt> 
<dt>UAC: Dominio &lt; &gt; \& lt; Nombre &gt; </dt>del proceso de usuario: proceso en la versión de firma
<dt> &lt; &gt; PID:</dt>versión
<dt> &lt; de &gt; </dt>definición Versión del
<dt>motor: versión del motor &lt; &gt; antimalware</dt>
</span><span class="sxs-lookup"><span data-stu-id="719cf-452">UAC</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-453">Acción del usuario:</span><span class="sxs-lookup"><span data-stu-id="719cf-453">User action:</span></span>
</td>
<td >
<span data-ttu-id="719cf-454">No se requiere ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="719cf-454">No action is required.</span></span> <span data-ttu-id="719cf-455">Antivirus de Microsoft Defender puede suspender y tomar medidas rutinarias en esta amenaza.</span><span class="sxs-lookup"><span data-stu-id="719cf-455">Microsoft Defender Antivirus can suspend and take routine action on this threat.</span></span> <span data-ttu-id="719cf-456">Si desea quitar la amenaza manualmente, en la interfaz antivirus de Microsoft Defender, haga clic <b>en Limpiar equipo</b>.</span><span class="sxs-lookup"><span data-stu-id="719cf-456">If you want to remove the threat manually, in the Microsoft Defender Antivirus interface, click <b>Clean Computer</b>.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="719cf-457">Identificador de evento: 1117</span><span class="sxs-lookup"><span data-stu-id="719cf-457">Event ID: 1117</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="719cf-458">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="719cf-458">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="719cf-459">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_TAKEN </b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-459">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_TAKEN </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-460">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="719cf-460">Message:</span></span>
</td>
<td ><span data-ttu-id="719cf-461">
<b>La plataforma antimalware realizó una acción para proteger el sistema de malware u otro software potencialmente no deseado. </b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-461">
<b>The antimalware platform performed an action to protect your system from malware or other potentially unwanted software. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-462">Descripción:</span><span class="sxs-lookup"><span data-stu-id="719cf-462">Description:</span></span>
</td>
<td >
<span data-ttu-id="719cf-463">Antivirus de Microsoft Defender ha tomado medidas para proteger esta máquina de malware u otro software potencialmente no deseado.</span><span class="sxs-lookup"><span data-stu-id="719cf-463">Microsoft Defender Antivirus has taken action to protect this machine from malware or other potentially unwanted software.</span></span><br/><span data-ttu-id="719cf-464">Para obtener más información, vea los artículos siguientes: </span><span class="sxs-lookup"><span data-stu-id="719cf-464">For more information, see the following:</span></span>
<dl><span data-ttu-id="719cf-465">
<dt>Nombre: &lt; Id. &gt; de</dt>
<dt>nombre de &lt; amenaza: Gravedad del id. &gt; </dt>de 
<dt> amenaza: gravedad , por &lt; &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="719cf-465">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="719cf-466">Bajo</span><span class="sxs-lookup"><span data-stu-id="719cf-466">Low</span></span></li>
<li><span data-ttu-id="719cf-467">Moderado</span><span class="sxs-lookup"><span data-stu-id="719cf-467">Moderate</span></span></li>
<li><span data-ttu-id="719cf-468">Alto</span><span class="sxs-lookup"><span data-stu-id="719cf-468">High</span></span></li>
<li><span data-ttu-id="719cf-469">Grave</span><span class="sxs-lookup"><span data-stu-id="719cf-469">Severe</span></span></li>
</ul><span data-ttu-id="719cf-470">
</dt>
<dt>Categoría: &lt; Descripción de &gt; categoría , por ejemplo, cualquier tipo de amenaza o malware.</dt> 
<dt>Ruta de acceso: &lt; Origen &gt; de detección</dt>de ruta de 
<dt> acceso de &lt; archivo: Origen de &gt; detección, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="719cf-470">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="719cf-471">Unknown</span><span class="sxs-lookup"><span data-stu-id="719cf-471">Unknown</span></span></li>
<li><span data-ttu-id="719cf-472">Equipo local</span><span class="sxs-lookup"><span data-stu-id="719cf-472">Local computer</span></span></li>
<li><span data-ttu-id="719cf-473">Recurso compartido de red</span><span class="sxs-lookup"><span data-stu-id="719cf-473">Network share</span></span></li>
<li><span data-ttu-id="719cf-474">Internet</span><span class="sxs-lookup"><span data-stu-id="719cf-474">Internet</span></span></li>
<li><span data-ttu-id="719cf-475">Tráfico entrante</span><span class="sxs-lookup"><span data-stu-id="719cf-475">Incoming traffic</span></span></li>
<li><span data-ttu-id="719cf-476">Tráfico saliente</span><span class="sxs-lookup"><span data-stu-id="719cf-476">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="719cf-477">
</dt>
<dt>Tipo de &lt; detección: Tipo de &gt; detección , por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="719cf-477">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="719cf-478">Heurística</span><span class="sxs-lookup"><span data-stu-id="719cf-478">Heuristics</span></span></li>
<li><span data-ttu-id="719cf-479">Generic</span><span class="sxs-lookup"><span data-stu-id="719cf-479">Generic</span></span></li>
<li><span data-ttu-id="719cf-480">Concreto</span><span class="sxs-lookup"><span data-stu-id="719cf-480">Concrete</span></span></li>
<li><span data-ttu-id="719cf-481">Firma dinámica</span><span class="sxs-lookup"><span data-stu-id="719cf-481">Dynamic signature</span></span></li>
</ul><span data-ttu-id="719cf-482">
</dt>
<dt>Origen de &lt; detección: origen de &gt; detección por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="719cf-482">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="719cf-483">Usuario: usuario iniciado</span><span class="sxs-lookup"><span data-stu-id="719cf-483">User: user initiated</span></span></li>
<li><span data-ttu-id="719cf-484">Sistema: sistema iniciado</span><span class="sxs-lookup"><span data-stu-id="719cf-484">System: system initiated</span></span></li>
<li><span data-ttu-id="719cf-485">En tiempo real: componente en tiempo real iniciado</span><span class="sxs-lookup"><span data-stu-id="719cf-485">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="719cf-486">IOAV: Descargas de IE y datos adjuntos de Outlook Express iniciados</span><span class="sxs-lookup"><span data-stu-id="719cf-486">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="719cf-487">NIS: sistema de inspección de red</span><span class="sxs-lookup"><span data-stu-id="719cf-487">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="719cf-488">IEPROTECT: IE - IExtensionValidation; esto protege contra controles de páginas web malintencionadas</span><span class="sxs-lookup"><span data-stu-id="719cf-488">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="719cf-489">Antimalware de inicio anticipado (ELAM).</span><span class="sxs-lookup"><span data-stu-id="719cf-489">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="719cf-490">Esto incluye malware detectado por la secuencia de arranque</span><span class="sxs-lookup"><span data-stu-id="719cf-490">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="719cf-491">Atestación remota</span><span class="sxs-lookup"><span data-stu-id="719cf-491">Remote attestation</span></span></li>
</ul><span data-ttu-id="719cf-492">Interfaz de examen antimalware (AMSI).</span><span class="sxs-lookup"><span data-stu-id="719cf-492">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="719cf-493">Se usa principalmente para proteger scripts (PS, VBS), aunque también pueden invocarse por terceros.</span><span class="sxs-lookup"><span data-stu-id="719cf-493">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="719cf-494">Usuario de </dt> 
<dt>UAC: Dominio &lt; &gt; \& lt; Nombre &gt; </dt>
<dt>del proceso de usuario: Proceso en la &lt; acción &gt; pid:</dt>Acción , por 
<dt> &lt; &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="719cf-494">UAC</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Action: &lt;Action&gt;, for example:</span></span><ul>
<li><span data-ttu-id="719cf-495">Clean: el recurso se ha limpiado</span><span class="sxs-lookup"><span data-stu-id="719cf-495">Clean: The resource was cleaned</span></span></li>
<li><span data-ttu-id="719cf-496">Cuarentena: el recurso se ha puesto en cuarentena</span><span class="sxs-lookup"><span data-stu-id="719cf-496">Quarantine: The resource was quarantined</span></span></li>
<li><span data-ttu-id="719cf-497">Quitar: se eliminó el recurso</span><span class="sxs-lookup"><span data-stu-id="719cf-497">Remove: The resource was deleted</span></span></li>
<li><span data-ttu-id="719cf-498">Permitir: se permitió que el recurso se ejecutara o existiera</span><span class="sxs-lookup"><span data-stu-id="719cf-498">Allow: The resource was allowed to execute/exist</span></span></li>
<li><span data-ttu-id="719cf-499">Definido por el usuario: acción definida por el usuario que normalmente es una de esta lista de acciones que el usuario ha especificado</span><span class="sxs-lookup"><span data-stu-id="719cf-499">User defined: User-defined action that is normally one from this list of actions that the user has specified</span></span></li>
<li><span data-ttu-id="719cf-500">Sin acción: sin acción</span><span class="sxs-lookup"><span data-stu-id="719cf-500">No action: No action</span></span></li>
<li><span data-ttu-id="719cf-501">Bloquear: se bloqueó el recurso para que no se ejecutara</span><span class="sxs-lookup"><span data-stu-id="719cf-501">Block: The resource was blocked from executing</span></span></li>
</ul><span data-ttu-id="719cf-502">
</dt>
<dt>Estado de la acción: &lt; Descripción de &gt; acciones adicionales</dt>
<dt>Código de error: &lt; Código de error Código de resultado asociado con el estado de &gt; amenaza. Valores HRESULT estándar.</dt> 
<dt>Descripción del error: &lt; Descripción del error &gt; Descripción del error.</dt> 
<dt>Versión de firma: &lt; &gt;</dt>Versión del motor de definición: versión del motor
<dt> &lt; &gt; antimalware</dt> NOTA: siempre que Antivirus de Microsoft Defender, Microsoft Security Essentials, Herramienta de eliminación de software malintencionado o System Center Endpoint Protection detecte un malware, restaurará la siguiente configuración del sistema y los servicios que el malware podría haber cambiado:</span><span class="sxs-lookup"><span data-stu-id="719cf-502">
</dt>
<dt>Action Status: &lt;Description of additional actions&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt> NOTE: Whenever Microsoft Defender Antivirus, Microsoft Security Essentials, Malicious Software Removal Tool, or System Center Endpoint Protection detects a malware, it will restore the following system settings and services that the malware might have changed:</span></span><ul>
<li><span data-ttu-id="719cf-503">Configuración predeterminada de Internet Explorer o Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="719cf-503">Default Internet Explorer or Microsoft Edge setting</span></span></li>
<li><span data-ttu-id="719cf-504">Configuración del control de acceso de usuario</span><span class="sxs-lookup"><span data-stu-id="719cf-504">User Access Control settings</span></span></li>
<li><span data-ttu-id="719cf-505">Configuración de Chrome</span><span class="sxs-lookup"><span data-stu-id="719cf-505">Chrome settings</span></span></li>
<li><span data-ttu-id="719cf-506">Datos de control de arranque</span><span class="sxs-lookup"><span data-stu-id="719cf-506">Boot Control Data</span></span></li>
<li><span data-ttu-id="719cf-507">Configuración del Registro regedit y administrador de tareas</span><span class="sxs-lookup"><span data-stu-id="719cf-507">Regedit and Task Manager registry settings</span></span></li>
<li><span data-ttu-id="719cf-508">Windows Update, el servicio de transferencia inteligente en segundo plano y el servicio de llamadas de procedimiento remoto</span><span class="sxs-lookup"><span data-stu-id="719cf-508">Windows Update, Background Intelligent Transfer Service, and Remote Procedure Call service</span></span></li>
<li><span data-ttu-id="719cf-509">Archivos del sistema operativo Windows</span><span class="sxs-lookup"><span data-stu-id="719cf-509">Windows Operating System files</span></span></li></ul>
<span data-ttu-id="719cf-510">El contexto anterior se aplica a las siguientes versiones de cliente y servidor:</span><span class="sxs-lookup"><span data-stu-id="719cf-510">The above context applies to the following client and server versions:</span></span>
<table>
<tr>
<th><span data-ttu-id="719cf-511">Sistema operativo</span><span class="sxs-lookup"><span data-stu-id="719cf-511">Operating system</span></span></th>
<th><span data-ttu-id="719cf-512">Versión del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="719cf-512">Operating system version</span></span></th>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-513">Sistema operativo cliente</span><span class="sxs-lookup"><span data-stu-id="719cf-513">Client Operating System</span></span>
</td>
<td>
<span data-ttu-id="719cf-514">Windows Vista (Service Pack 1 o Service Pack 2), Windows 7 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="719cf-514">Windows Vista (Service Pack 1, or Service Pack 2), Windows 7 and later</span></span>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-515">Sistema operativo del servidor</span><span class="sxs-lookup"><span data-stu-id="719cf-515">Server Operating System</span></span>
</td>
<td>
<span data-ttu-id="719cf-516">Windows Server 2008, Windows Server 2008 R2, Windows Server 2012 y Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="719cf-516">Windows Server 2008, Windows Server 2008 R2, Windows Server 2012, and Windows Server 2016</span></span>
</td>
</tr>
</table>
</dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-517">Acción del usuario:</span><span class="sxs-lookup"><span data-stu-id="719cf-517">User action:</span></span>
</td>
<td >
<span data-ttu-id="719cf-518">No es necesario realizar ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="719cf-518">No action is necessary.</span></span> <span data-ttu-id="719cf-519">Antivirus de Microsoft Defender eliminó o en cuarentena una amenaza.</span><span class="sxs-lookup"><span data-stu-id="719cf-519">Microsoft Defender Antivirus removed or quarantined a threat.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="719cf-520">Identificador de evento: 1118</span><span class="sxs-lookup"><span data-stu-id="719cf-520">Event ID: 1118</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="719cf-521">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="719cf-521">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="719cf-522">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-522">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-523">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="719cf-523">Message:</span></span>
</td>
<td ><span data-ttu-id="719cf-524">
<b>La plataforma antimalware intentó realizar una acción para proteger el sistema de malware u otro software potencialmente no deseado, pero la acción falló. </b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-524">
<b>The antimalware platform attempted to perform an action to protect your system from malware or other potentially unwanted software, but the action failed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-525">Descripción:</span><span class="sxs-lookup"><span data-stu-id="719cf-525">Description:</span></span>
</td>
<td >
<span data-ttu-id="719cf-526">Antivirus de Microsoft Defender ha encontrado un error no crítico al tomar medidas en malware u otro software potencialmente no deseado.</span><span class="sxs-lookup"><span data-stu-id="719cf-526">Microsoft Defender Antivirus has encountered a non-critical error when taking action on malware or other potentially unwanted software.</span></span><br/><span data-ttu-id="719cf-527">Para obtener más información, vea los artículos siguientes: </span><span class="sxs-lookup"><span data-stu-id="719cf-527">For more information, see the following:</span></span>
<dl><span data-ttu-id="719cf-528">
<dt>Nombre: &lt; Id. &gt; de</dt>
<dt>nombre de &lt; amenaza: Gravedad del id. &gt; </dt>de 
<dt> amenaza: gravedad , por &lt; &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="719cf-528">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="719cf-529">Bajo</span><span class="sxs-lookup"><span data-stu-id="719cf-529">Low</span></span></li>
<li><span data-ttu-id="719cf-530">Moderado</span><span class="sxs-lookup"><span data-stu-id="719cf-530">Moderate</span></span></li>
<li><span data-ttu-id="719cf-531">Alto</span><span class="sxs-lookup"><span data-stu-id="719cf-531">High</span></span></li>
<li><span data-ttu-id="719cf-532">Grave</span><span class="sxs-lookup"><span data-stu-id="719cf-532">Severe</span></span></li>
</ul><span data-ttu-id="719cf-533">
</dt>
<dt>Categoría: &lt; Descripción de &gt; categoría , por ejemplo, cualquier tipo de amenaza o malware.</dt> 
<dt>Ruta de acceso: &lt; Origen &gt; de detección</dt>de ruta de 
<dt> acceso de &lt; archivo: Origen de &gt; detección, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="719cf-533">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="719cf-534">Unknown</span><span class="sxs-lookup"><span data-stu-id="719cf-534">Unknown</span></span></li>
<li><span data-ttu-id="719cf-535">Equipo local</span><span class="sxs-lookup"><span data-stu-id="719cf-535">Local computer</span></span></li>
<li><span data-ttu-id="719cf-536">Recurso compartido de red</span><span class="sxs-lookup"><span data-stu-id="719cf-536">Network share</span></span></li>
<li><span data-ttu-id="719cf-537">Internet</span><span class="sxs-lookup"><span data-stu-id="719cf-537">Internet</span></span></li>
<li><span data-ttu-id="719cf-538">Tráfico entrante</span><span class="sxs-lookup"><span data-stu-id="719cf-538">Incoming traffic</span></span></li>
<li><span data-ttu-id="719cf-539">Tráfico saliente</span><span class="sxs-lookup"><span data-stu-id="719cf-539">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="719cf-540">
</dt>
<dt>Tipo de &lt; detección: Tipo de &gt; detección , por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="719cf-540">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="719cf-541">Heurística</span><span class="sxs-lookup"><span data-stu-id="719cf-541">Heuristics</span></span></li>
<li><span data-ttu-id="719cf-542">Generic</span><span class="sxs-lookup"><span data-stu-id="719cf-542">Generic</span></span></li>
<li><span data-ttu-id="719cf-543">Concreto</span><span class="sxs-lookup"><span data-stu-id="719cf-543">Concrete</span></span></li>
<li><span data-ttu-id="719cf-544">Firma dinámica</span><span class="sxs-lookup"><span data-stu-id="719cf-544">Dynamic signature</span></span></li>
</ul><span data-ttu-id="719cf-545">
</dt>
<dt>Origen de &lt; detección: origen de &gt; detección por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="719cf-545">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="719cf-546">Usuario: usuario iniciado</span><span class="sxs-lookup"><span data-stu-id="719cf-546">User: user initiated</span></span></li>
<li><span data-ttu-id="719cf-547">Sistema: sistema iniciado</span><span class="sxs-lookup"><span data-stu-id="719cf-547">System: system initiated</span></span></li>
<li><span data-ttu-id="719cf-548">En tiempo real: componente en tiempo real iniciado</span><span class="sxs-lookup"><span data-stu-id="719cf-548">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="719cf-549">IOAV: Descargas de IE y datos adjuntos de Outlook Express iniciados</span><span class="sxs-lookup"><span data-stu-id="719cf-549">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="719cf-550">NIS: sistema de inspección de red</span><span class="sxs-lookup"><span data-stu-id="719cf-550">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="719cf-551">IEPROTECT: IE - IExtensionValidation; esto protege contra controles de páginas web malintencionadas</span><span class="sxs-lookup"><span data-stu-id="719cf-551">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="719cf-552">Antimalware de inicio anticipado (ELAM).</span><span class="sxs-lookup"><span data-stu-id="719cf-552">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="719cf-553">Esto incluye malware detectado por la secuencia de arranque</span><span class="sxs-lookup"><span data-stu-id="719cf-553">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="719cf-554">Atestación remota</span><span class="sxs-lookup"><span data-stu-id="719cf-554">Remote attestation</span></span></li>
</ul><span data-ttu-id="719cf-555">Interfaz de examen antimalware (AMSI).</span><span class="sxs-lookup"><span data-stu-id="719cf-555">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="719cf-556">Se usa principalmente para proteger scripts (PS, VBS), aunque también pueden invocarse por terceros.</span><span class="sxs-lookup"><span data-stu-id="719cf-556">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="719cf-557">Usuario de </dt> 
<dt>UAC: Dominio &lt; &gt; \& lt; Nombre &gt; </dt>
<dt>del proceso de usuario: Proceso en la &lt; acción &gt; pid:</dt>Acción , por 
<dt> &lt; &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="719cf-557">UAC</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Action: &lt;Action&gt;, for example:</span></span><ul>
<li><span data-ttu-id="719cf-558">Clean: el recurso se ha limpiado</span><span class="sxs-lookup"><span data-stu-id="719cf-558">Clean: The resource was cleaned</span></span></li>
<li><span data-ttu-id="719cf-559">Cuarentena: el recurso se ha puesto en cuarentena</span><span class="sxs-lookup"><span data-stu-id="719cf-559">Quarantine: The resource was quarantined</span></span></li>
<li><span data-ttu-id="719cf-560">Quitar: se eliminó el recurso</span><span class="sxs-lookup"><span data-stu-id="719cf-560">Remove: The resource was deleted</span></span></li>
<li><span data-ttu-id="719cf-561">Permitir: se permitió que el recurso se ejecutara o existiera</span><span class="sxs-lookup"><span data-stu-id="719cf-561">Allow: The resource was allowed to execute/exist</span></span></li>
<li><span data-ttu-id="719cf-562">Definido por el usuario: acción definida por el usuario que normalmente es una de esta lista de acciones que el usuario ha especificado</span><span class="sxs-lookup"><span data-stu-id="719cf-562">User defined: User-defined action that is normally one from this list of actions that the user has specified</span></span></li>
<li><span data-ttu-id="719cf-563">Sin acción: sin acción</span><span class="sxs-lookup"><span data-stu-id="719cf-563">No action: No action</span></span></li>
<li><span data-ttu-id="719cf-564">Bloquear: se bloqueó el recurso para que no se ejecutara</span><span class="sxs-lookup"><span data-stu-id="719cf-564">Block: The resource was blocked from executing</span></span></li>
</ul><span data-ttu-id="719cf-565">
</dt>
<dt>Estado de la acción: &lt; Descripción de &gt; acciones adicionales</dt>
<dt>Código de error: &lt; Código de error Código de resultado asociado con el estado de &gt; amenaza. Valores HRESULT estándar.</dt> 
<dt>Descripción del error: &lt; Descripción del error &gt; Descripción del error.</dt> 
<dt>Versión de firma: &lt; Versión &gt; de definición</dt>
<dt>Versión del motor: &lt; versión &gt; del motor antimalware</dt>
</span><span class="sxs-lookup"><span data-stu-id="719cf-565">
</dt>
<dt>Action Status: &lt;Description of additional actions&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-566">Acción del usuario:</span><span class="sxs-lookup"><span data-stu-id="719cf-566">User action:</span></span>
</td>
<td >
<span data-ttu-id="719cf-567">No es necesario realizar ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="719cf-567">No action is necessary.</span></span> <span data-ttu-id="719cf-568">Antivirus de Microsoft Defender no pudo completar una tarea relacionada con la corrección de malware.</span><span class="sxs-lookup"><span data-stu-id="719cf-568">Microsoft Defender Antivirus failed to complete a task related to the malware remediation.</span></span> <span data-ttu-id="719cf-569">No se trata de un error crítico.</span><span class="sxs-lookup"><span data-stu-id="719cf-569">This is not a critical failure.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="719cf-570">Identificador de evento: 1119</span><span class="sxs-lookup"><span data-stu-id="719cf-570">Event ID: 1119</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="719cf-571">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="719cf-571">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="719cf-572">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_CRITICALLY_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-572">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_CRITICALLY_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-573">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="719cf-573">Message:</span></span>
</td>
<td ><span data-ttu-id="719cf-574">
<b>La plataforma antimalware encontró un error crítico al intentar tomar medidas en malware u otro software potencialmente no deseado. Hay más detalles en el mensaje de evento.</b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-574">
<b>The antimalware platform encountered a critical error when trying to take action on malware or other potentially unwanted software. There are more details in the event message.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-575">Descripción:</span><span class="sxs-lookup"><span data-stu-id="719cf-575">Description:</span></span>
</td>
<td >
<span data-ttu-id="719cf-576">Antivirus de Microsoft Defender ha encontrado un error crítico al tomar medidas en malware u otro software potencialmente no deseado.</span><span class="sxs-lookup"><span data-stu-id="719cf-576">Microsoft Defender Antivirus has encountered a critical error when taking action on malware or other potentially unwanted software.</span></span><br/><span data-ttu-id="719cf-577">Para obtener más información, vea los artículos siguientes: </span><span class="sxs-lookup"><span data-stu-id="719cf-577">For more information, see the following:</span></span>
<dl><span data-ttu-id="719cf-578">
<dt>Nombre: &lt; Id. &gt; de</dt>
<dt>nombre de &lt; amenaza: Gravedad del id. &gt; </dt>de 
<dt> amenaza: gravedad , por &lt; &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="719cf-578">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="719cf-579">Bajo</span><span class="sxs-lookup"><span data-stu-id="719cf-579">Low</span></span></li>
<li><span data-ttu-id="719cf-580">Moderado</span><span class="sxs-lookup"><span data-stu-id="719cf-580">Moderate</span></span></li>
<li><span data-ttu-id="719cf-581">Alto</span><span class="sxs-lookup"><span data-stu-id="719cf-581">High</span></span></li>
<li><span data-ttu-id="719cf-582">Grave</span><span class="sxs-lookup"><span data-stu-id="719cf-582">Severe</span></span></li>
</ul><span data-ttu-id="719cf-583">
</dt>
<dt>Categoría: &lt; Descripción de &gt; categoría , por ejemplo, cualquier tipo de amenaza o malware.</dt> 
<dt>Ruta de acceso: &lt; Origen &gt; de detección</dt>de ruta de 
<dt> acceso de &lt; archivo: Origen de &gt; detección, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="719cf-583">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="719cf-584">Unknown</span><span class="sxs-lookup"><span data-stu-id="719cf-584">Unknown</span></span></li>
<li><span data-ttu-id="719cf-585">Equipo local</span><span class="sxs-lookup"><span data-stu-id="719cf-585">Local computer</span></span></li>
<li><span data-ttu-id="719cf-586">Recurso compartido de red</span><span class="sxs-lookup"><span data-stu-id="719cf-586">Network share</span></span></li>
<li><span data-ttu-id="719cf-587">Internet</span><span class="sxs-lookup"><span data-stu-id="719cf-587">Internet</span></span></li>
<li><span data-ttu-id="719cf-588">Tráfico entrante</span><span class="sxs-lookup"><span data-stu-id="719cf-588">Incoming traffic</span></span></li>
<li><span data-ttu-id="719cf-589">Tráfico saliente</span><span class="sxs-lookup"><span data-stu-id="719cf-589">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="719cf-590">
</dt>
<dt>Tipo de &lt; detección: Tipo de &gt; detección , por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="719cf-590">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="719cf-591">Heurística</span><span class="sxs-lookup"><span data-stu-id="719cf-591">Heuristics</span></span></li>
<li><span data-ttu-id="719cf-592">Generic</span><span class="sxs-lookup"><span data-stu-id="719cf-592">Generic</span></span></li>
<li><span data-ttu-id="719cf-593">Concreto</span><span class="sxs-lookup"><span data-stu-id="719cf-593">Concrete</span></span></li>
<li><span data-ttu-id="719cf-594">Firma dinámica</span><span class="sxs-lookup"><span data-stu-id="719cf-594">Dynamic signature</span></span></li>
</ul><span data-ttu-id="719cf-595">
</dt>
<dt>Origen de &lt; detección: origen de &gt; detección por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="719cf-595">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="719cf-596">Usuario: usuario iniciado</span><span class="sxs-lookup"><span data-stu-id="719cf-596">User: user initiated</span></span></li>
<li><span data-ttu-id="719cf-597">Sistema: sistema iniciado</span><span class="sxs-lookup"><span data-stu-id="719cf-597">System: system initiated</span></span></li>
<li><span data-ttu-id="719cf-598">En tiempo real: componente en tiempo real iniciado</span><span class="sxs-lookup"><span data-stu-id="719cf-598">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="719cf-599">IOAV: Descargas de IE y datos adjuntos de Outlook Express iniciados</span><span class="sxs-lookup"><span data-stu-id="719cf-599">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="719cf-600">NIS: sistema de inspección de red</span><span class="sxs-lookup"><span data-stu-id="719cf-600">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="719cf-601">IEPROTECT: IE - IExtensionValidation; esto protege contra controles de páginas web malintencionadas</span><span class="sxs-lookup"><span data-stu-id="719cf-601">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="719cf-602">Antimalware de inicio anticipado (ELAM).</span><span class="sxs-lookup"><span data-stu-id="719cf-602">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="719cf-603">Esto incluye malware detectado por la secuencia de arranque</span><span class="sxs-lookup"><span data-stu-id="719cf-603">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="719cf-604">Atestación remota</span><span class="sxs-lookup"><span data-stu-id="719cf-604">Remote attestation</span></span></li>
</ul><span data-ttu-id="719cf-605">Interfaz de examen antimalware (AMSI).</span><span class="sxs-lookup"><span data-stu-id="719cf-605">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="719cf-606">Se usa principalmente para proteger scripts (PS, VBS), aunque también pueden invocarse por terceros.</span><span class="sxs-lookup"><span data-stu-id="719cf-606">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="719cf-607">Usuario de </dt> 
<dt>UAC: Dominio &lt; &gt; \& lt; Nombre &gt; </dt>
<dt>del proceso de usuario: Proceso en la &lt; acción &gt; pid:</dt>Acción , por 
<dt> &lt; &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="719cf-607">UAC</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Action: &lt;Action&gt;, for example:</span></span><ul>
<li><span data-ttu-id="719cf-608">Clean: el recurso se ha limpiado</span><span class="sxs-lookup"><span data-stu-id="719cf-608">Clean: The resource was cleaned</span></span></li>
<li><span data-ttu-id="719cf-609">Cuarentena: el recurso se ha puesto en cuarentena</span><span class="sxs-lookup"><span data-stu-id="719cf-609">Quarantine: The resource was quarantined</span></span></li>
<li><span data-ttu-id="719cf-610">Quitar: se eliminó el recurso</span><span class="sxs-lookup"><span data-stu-id="719cf-610">Remove: The resource was deleted</span></span></li>
<li><span data-ttu-id="719cf-611">Permitir: se permitió que el recurso se ejecutara o existiera</span><span class="sxs-lookup"><span data-stu-id="719cf-611">Allow: The resource was allowed to execute/exist</span></span></li>
<li><span data-ttu-id="719cf-612">Definido por el usuario: acción definida por el usuario que normalmente es una de esta lista de acciones que el usuario ha especificado</span><span class="sxs-lookup"><span data-stu-id="719cf-612">User defined: User-defined action that is normally one from this list of actions that the user has specified</span></span></li>
<li><span data-ttu-id="719cf-613">Sin acción: sin acción</span><span class="sxs-lookup"><span data-stu-id="719cf-613">No action: No action</span></span></li>
<li><span data-ttu-id="719cf-614">Bloquear: se bloqueó el recurso para que no se ejecutara</span><span class="sxs-lookup"><span data-stu-id="719cf-614">Block: The resource was blocked from executing</span></span></li>
</ul><span data-ttu-id="719cf-615">
</dt>
<dt>Estado de la acción: &lt; Descripción de &gt; acciones adicionales</dt>
<dt>Código de error: &lt; Código de error Código de resultado asociado con el estado de &gt; amenaza. Valores HRESULT estándar.</dt> 
<dt>Descripción del error: &lt; Descripción del error &gt; Descripción del error.</dt> 
<dt>Versión de firma: &lt; Versión &gt; de definición</dt>
<dt>Versión del motor: &lt; versión &gt; del motor antimalware</dt>
</span><span class="sxs-lookup"><span data-stu-id="719cf-615">
</dt>
<dt>Action Status: &lt;Description of additional actions&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-616">Acción del usuario:</span><span class="sxs-lookup"><span data-stu-id="719cf-616">User action:</span></span>
</td>
<td >
<span data-ttu-id="719cf-617">El cliente antivirus de Microsoft Defender encontró este error debido a problemas críticos.</span><span class="sxs-lookup"><span data-stu-id="719cf-617">The Microsoft Defender Antivirus client encountered this error due to critical issues.</span></span> <span data-ttu-id="719cf-618">Es posible que el extremo no esté protegido.</span><span class="sxs-lookup"><span data-stu-id="719cf-618">The endpoint might not be protected.</span></span> <span data-ttu-id="719cf-619">Revise la descripción del error y, a continuación, siga los <b>pasos de acción de usuario</b> pertinentes a continuación.</span><span class="sxs-lookup"><span data-stu-id="719cf-619">Review the error description then follow the relevant <b>User action</b> steps below.</span></span>
<table>
<tr>
<th><span data-ttu-id="719cf-620">Acción</span><span class="sxs-lookup"><span data-stu-id="719cf-620">Action</span></span></th>
<th><span data-ttu-id="719cf-621">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="719cf-621">User action</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="719cf-622">
<b>Quitar</b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-622">
<b>Remove</b>
</span></span></td>
<td>
<span data-ttu-id="719cf-623">Actualice las definiciones y compruebe que la eliminación se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="719cf-623">Update the definitions then verify that the removal was successful.</span></span>
</td>
</tr>
<tr>
<td><span data-ttu-id="719cf-624">
<b>Limpiar</b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-624">
<b>Clean</b>
</span></span></td>
<td>
<span data-ttu-id="719cf-625">Actualice las definiciones y compruebe que la corrección se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="719cf-625">Update the definitions then verify that the remediation was successful.</span></span>
</td>
</tr>
<tr>
<td><span data-ttu-id="719cf-626">
<b>Cuarentena</b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-626">
<b>Quarantine</b>
</span></span></td>
<td>
<span data-ttu-id="719cf-627">Actualice las definiciones y compruebe que el usuario tiene permiso para acceder a los recursos necesarios.</span><span class="sxs-lookup"><span data-stu-id="719cf-627">Update the definitions and verify that the user has permission to access the necessary resources.</span></span>
</td>
</tr>
<tr>
<td><span data-ttu-id="719cf-628">
<b>Permitir</b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-628">
<b>Allow</b>
</span></span></td>
<td>
<span data-ttu-id="719cf-629">Compruebe que el usuario tiene permiso para obtener acceso a los recursos necesarios.</span><span class="sxs-lookup"><span data-stu-id="719cf-629">Verify that the user has permission to access the necessary resources.</span></span>
</td>
</tr>
</table>

<span data-ttu-id="719cf-630">Si este evento persiste:</span><span class="sxs-lookup"><span data-stu-id="719cf-630">If this event persists:</span></span><ol>
<li><span data-ttu-id="719cf-631">Vuelva a ejecutar el examen.</span><span class="sxs-lookup"><span data-stu-id="719cf-631">Run the scan again.</span></span></li>
<li><span data-ttu-id="719cf-632">Si se produce un error de la misma manera, vaya <b></b> al sitio de soporte técnico de <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft</a>, escriba el número de error en el cuadro Buscar para buscar el código de error.</span><span class="sxs-lookup"><span data-stu-id="719cf-632">If it fails in the same way, go to the <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft Support site</a>, enter the error number in the <b>Search</b> box to look for the error code.</span></span></li>
<li><span data-ttu-id="719cf-633">Contactar al <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Soporte técnico de Microsoft</a>.</span><span class="sxs-lookup"><span data-stu-id="719cf-633">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="719cf-634">Identificador de evento: 1120</span><span class="sxs-lookup"><span data-stu-id="719cf-634">Event ID: 1120</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="719cf-635">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="719cf-635">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="719cf-636">
<b>MALWAREPROTECTION_THREAT_HASH</b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-636">
<b>MALWAREPROTECTION_THREAT_HASH</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-637">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="719cf-637">Message:</span></span>
</td>
<td ><span data-ttu-id="719cf-638">
<b>Antivirus de Microsoft Defender ha deducido los hashes de un recurso de amenaza.</b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-638">
<b>Microsoft Defender Antivirus has deduced the hashes for a threat resource.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-639">Descripción:</span><span class="sxs-lookup"><span data-stu-id="719cf-639">Description:</span></span>
</td>
<td >
<span data-ttu-id="719cf-640">El cliente antivirus de Microsoft Defender está en funcionamiento en buen estado.</span><span class="sxs-lookup"><span data-stu-id="719cf-640">Microsoft Defender Antivirus client is up and running in a healthy state.</span></span>
<dl><span data-ttu-id="719cf-641">
<dt>Versión actual de la plataforma: &lt; Ruta de &gt; acceso de</dt>recurso de amenaza de la
<dt> &lt; &gt; versión</dt>actual de la plataforma:
<dt>hashes de ruta: &lt; hashes &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="719cf-641">
<dt>Current Platform Version: &lt;Current platform version&gt;</dt>
<dt>Threat Resource Path: &lt;Path&gt;</dt>
<dt>Hashes: &lt;Hashes&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td></td>
<td >
<div class="alert"><span data-ttu-id="719cf-642"><b>Nota: Este evento solo se registrará si se establece la siguiente directiva: <b>ThreatFileHashLogging sin signo</b>.</span><span class="sxs-lookup"><span data-stu-id="719cf-642"><b>Note: This event will only be logged if the following policy is set: <b>ThreatFileHashLogging     unsigned</b>.</span></span></div>
<div> </div>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="719cf-643">Identificador de evento: 1150</span><span class="sxs-lookup"><span data-stu-id="719cf-643">Event ID: 1150</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="719cf-644">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="719cf-644">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="719cf-645">
<b>MALWAREPROTECTION_SERVICE_HEALTHY</b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-645">
<b>MALWAREPROTECTION_SERVICE_HEALTHY</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-646">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="719cf-646">Message:</span></span>
</td>
<td ><span data-ttu-id="719cf-647">
<b>Si la plataforma antimalware notifica el estado a una plataforma de supervisión, este evento indica que la plataforma antimalware se está ejecutando y en un estado correcto. </b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-647">
<b>If your antimalware platform reports status to a monitoring platform, this event indicates that the antimalware platform is running and in a healthy state. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-648">Descripción:</span><span class="sxs-lookup"><span data-stu-id="719cf-648">Description:</span></span>
</td>
<td >
<span data-ttu-id="719cf-649">El cliente antivirus de Microsoft Defender está en funcionamiento en buen estado.</span><span class="sxs-lookup"><span data-stu-id="719cf-649">Microsoft Defender Antivirus client is up and running in a healthy state.</span></span>
<dl><span data-ttu-id="719cf-650">
<dt>Versión de la plataforma: &lt; Versión de &gt; la plataforma actual</dt>Versión de firma: Versión del motor
<dt>de la &lt; &gt; </dt>
<dt> &lt; &gt; versión de definición: versión del motor antimalware</dt>
</span><span class="sxs-lookup"><span data-stu-id="719cf-650">
<dt>Platform Version: &lt;Current platform version&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-651">Acción del usuario:</span><span class="sxs-lookup"><span data-stu-id="719cf-651">User action:</span></span>
</td>
<td >
<span data-ttu-id="719cf-652">No es necesario realizar ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="719cf-652">No action is necessary.</span></span> <span data-ttu-id="719cf-653">El cliente antivirus de Microsoft Defender está en buen estado.</span><span class="sxs-lookup"><span data-stu-id="719cf-653">The Microsoft Defender Antivirus client is in a healthy state.</span></span> <span data-ttu-id="719cf-654">Este evento se notifica cada hora.</span><span class="sxs-lookup"><span data-stu-id="719cf-654">This event is reported on an hourly basis.</span></span>
</td>
</tr>

<tr>
<th colspan="2"><span data-ttu-id="719cf-655">Identificador de evento: 1151</span><span class="sxs-lookup"><span data-stu-id="719cf-655">Event ID: 1151</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="719cf-656">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="719cf-656">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="719cf-657">
<b>MALWAREPROTECTION_SERVICE_HEALTH_REPORT</b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-657">
<b>MALWAREPROTECTION_SERVICE_HEALTH_REPORT</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-658">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="719cf-658">Message:</span></span>
</td>
<td ><span data-ttu-id="719cf-659">
<b>Informe de estado del cliente de Endpoint Protection (hora UTC) </b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-659">
<b>Endpoint Protection client health report (time in UTC) </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-660">Descripción:</span><span class="sxs-lookup"><span data-stu-id="719cf-660">Description:</span></span>
</td>
<td >
<span data-ttu-id="719cf-661">Informe de estado del cliente antivirus.</span><span class="sxs-lookup"><span data-stu-id="719cf-661">Antivirus client health report.</span></span>
<dl><span data-ttu-id="719cf-662">
<dt>Versión de la plataforma: &lt; &gt;</dt>Versión actual de la plataforma Versión del motor: Versión del motor
<dt> &lt; &gt; antimalware</dt>Versión del motor de inspección en tiempo real
<dt>de red: &lt; &gt; </dt>Versión de firma del motor de inspección en tiempo real de red
<dt>Versión &lt; &gt; </dt>de firma antivirus Versión de firma
<dt> &lt; &gt; antispyware Versión</dt>de firma de inspección en tiempo
<dt>real: &lt; &gt; </dt>Estado rtp de la firma de inspección en tiempo real de red: Estado de protección en tiempo real (habilitado o
<dt> &lt; &gt; deshabilitado)</dt>Estado
<dt>de OA: Estado de IOAV en tiempo real (habilitado o &lt; &gt; deshabilitado):</dt>Estado de las descargas de IE y los datos adjuntos de Outlook Express (habilitados o deshabilitados): Estado de supervisión del comportamiento (habilitado o
<dt> &lt; &gt; deshabilitado)</dt>Antigüedad de firma del antivirus
<dt> &lt; &gt; (en días)</dt>Antigüedad de firma antispyware: Antigüedad de firma
<dt> &lt; antispyware &gt; (en días)</dt>Última antigüedad del examen rápido: Última antigüedad del examen rápido
<dt> &lt; &gt; (en días)</dt>Última antigüedad completa del examen( en
<dt> &lt; &gt; días)</dt>Tiempo de creación de firmas
<dt> &lt; &gt; </dt>
<dt>antivirus: ? &lt; Hora de &gt; creación de firmas antivirus</dt>Tiempo de
<dt>creación de firmas antispyware: ? &lt; Hora de creación &gt; de firmas antispyware</dt>
<dt>Última hora de inicio del examen rápido: ? &lt; Última hora de &gt; inicio del examen rápido</dt>Última hora de finalización del examen
<dt>rápido: ? &lt; Última &gt; hora</dt>de finalización del examen rápido Último origen de examen rápido: Último origen de examen rápido (0 = el examen no se&#39;se ha ejecutado, 1 = iniciado por el
<dt> &lt; &gt; usuario, 2 =</dt>iniciado por el sistema) Última hora de inicio del examen
<dt>completo: ? &lt; Última hora de &gt; inicio del examen completo</dt>Última hora de finalización del examen
<dt>completo: ? &lt; Última &gt; hora</dt>de finalización del examen completo Último origen de examen completo: Último origen de examen completo (0 = el examen no se&#39;no se ha ejecutado, 1 = iniciado por el
<dt> &lt; &gt; usuario, 2 =</dt>iniciado por el sistema) Estado del producto: Para la solución de problemas interna 
<dt></span><span class="sxs-lookup"><span data-stu-id="719cf-662">
<dt>Platform Version: &lt;Current platform version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
<dt>Network Realtime Inspection engine version: &lt;Network Realtime Inspection engine version&gt;</dt>
<dt>Antivirus signature version: &lt;Antivirus signature version&gt;</dt>
<dt>Antispyware signature version: &lt;Antispyware signature version&gt;</dt>
<dt>Network Realtime Inspection signature version: &lt;Network Realtime Inspection signature version&gt;</dt>
<dt>RTP state: &lt;Realtime protection state&gt; (Enabled or Disabled)</dt>
<dt>OA state: &lt;On Access state&gt; (Enabled or Disabled)</dt>
<dt>IOAV state: &lt;IE Downloads and Outlook Express Attachments state&gt; (Enabled or Disabled)</dt>
<dt>BM state: &lt;Behavior Monitoring state&gt; (Enabled or Disabled)</dt>
<dt>Antivirus signature age: &lt;Antivirus signature age&gt; (in days)</dt>
<dt>Antispyware signature age: &lt;Antispyware signature age&gt; (in days)</dt>
<dt>Last quick scan age: &lt;Last quick scan age&gt; (in days)</dt>
<dt>Last full scan age: &lt;Last full scan age&gt; (in days)</dt>
<dt>Antivirus signature creation time: ?&lt;Antivirus signature creation time&gt;</dt>
<dt>Antispyware signature creation time: ?&lt;Antispyware signature creation time&gt;</dt>
<dt>Last quick scan start time: ?&lt;Last quick scan start time&gt;</dt>
<dt>Last quick scan end time: ?&lt;Last quick scan end time&gt;</dt>
<dt>Last quick scan source: &lt;Last quick scan source&gt; (0 = scan didn&#39;t run, 1 = user initiated, 2 = system initiated)</dt>
<dt>Last full scan start time: ?&lt;Last full scan start time&gt;</dt>
<dt>Last full scan end time: ?&lt;Last full scan end time&gt;</dt>
<dt>Last full scan source: &lt;Last full scan source&gt; (0 = scan didn&#39;t run, 1 = user initiated, 2 = system initiated)</dt>
<dt>Product status: For internal troubleshooting</span></span>
</dl>
</td>
</tr>

<tr><span data-ttu-id="719cf-663">
<th colspan="2">Identificador de evento: 2000</span><span class="sxs-lookup"><span data-stu-id="719cf-663">
<th colspan="2">Event ID: 2000</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="719cf-664">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="719cf-664">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="719cf-665">
<b>MALWAREPROTECTION_SIGNATURE_UPDATED </b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-665">
<b>MALWAREPROTECTION_SIGNATURE_UPDATED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-666">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="719cf-666">Message:</span></span>
</td>
<td ><span data-ttu-id="719cf-667">
<b>Las definiciones de antimalware se actualizaron correctamente. </b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-667">
<b>The antimalware definitions updated successfully. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-668">Descripción:</span><span class="sxs-lookup"><span data-stu-id="719cf-668">Description:</span></span>
</td>
<td >
<span data-ttu-id="719cf-669">Se ha actualizado la versión de firma del antivirus.</span><span class="sxs-lookup"><span data-stu-id="719cf-669">Antivirus signature version has been updated.</span></span>
<dl><span data-ttu-id="719cf-670">
<dt>Versión de firma actual: &lt; Versión de &gt; firma actual</dt>
<dt>Versión de firma anterior: Versión de firma &lt; anterior &gt; </dt>Tipo de 
<dt> firma: Tipo de firma , por &lt; &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="719cf-670">
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Previous Signature Version: &lt;Previous signature version&gt;</dt>
<dt>Signature Type: &lt;Signature type&gt;, for example:</span></span> <ul>
<li><span data-ttu-id="719cf-671">Antivirus</span><span class="sxs-lookup"><span data-stu-id="719cf-671">Antivirus</span></span></li>
<li><span data-ttu-id="719cf-672">Antispyware</span><span class="sxs-lookup"><span data-stu-id="719cf-672">Antispyware</span></span></li>
<li><span data-ttu-id="719cf-673">Antimalware</span><span class="sxs-lookup"><span data-stu-id="719cf-673">Antimalware</span></span></li>
<li><span data-ttu-id="719cf-674">Sistema de inspección de red</span><span class="sxs-lookup"><span data-stu-id="719cf-674">Network Inspection System</span></span></li>
</ul><span data-ttu-id="719cf-675">
</dt>
<dt>Tipo de actualización: &lt; Tipo de &gt; actualización , Completo o Delta.</dt> 
<dt>Usuario: &lt; Dominio &gt; \& lt; Versión &gt; </dt>
<dt>del motor actual del usuario: versión actual del &lt; &gt; motor</dt>Versión anterior del
<dt>motor: Versión anterior del &lt; motor &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="719cf-675">
</dt>
<dt>Update Type: &lt;Update type&gt;, either Full or Delta.</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Previous Engine Version: &lt;Previous engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-676">Acción del usuario:</span><span class="sxs-lookup"><span data-stu-id="719cf-676">User action:</span></span>
</td>
<td >
<span data-ttu-id="719cf-677">No es necesario realizar ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="719cf-677">No action is necessary.</span></span> <span data-ttu-id="719cf-678">El cliente antivirus de Microsoft Defender está en buen estado.</span><span class="sxs-lookup"><span data-stu-id="719cf-678">The Microsoft Defender Antivirus client is in a healthy state.</span></span> <span data-ttu-id="719cf-679">Este evento se notifica cuando las firmas se actualizan correctamente.</span><span class="sxs-lookup"><span data-stu-id="719cf-679">This event is reported when signatures are successfully updated.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="719cf-680">Identificador de evento: 2001</span><span class="sxs-lookup"><span data-stu-id="719cf-680">Event ID: 2001</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="719cf-681">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="719cf-681">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="719cf-682">
<b>MALWAREPROTECTION_SIGNATURE_UPDATE_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-682">
<b>MALWAREPROTECTION_SIGNATURE_UPDATE_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-683">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="719cf-683">Message:</span></span>
</td>
<td ><span data-ttu-id="719cf-684">
<b>Error en la actualización de inteligencia de seguridad. </b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-684">
<b>The security intelligence update failed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-685">Descripción:</span><span class="sxs-lookup"><span data-stu-id="719cf-685">Description:</span></span>
</td>
<td >
<span data-ttu-id="719cf-686">Antivirus de Microsoft Defender ha encontrado un error al intentar actualizar firmas.</span><span class="sxs-lookup"><span data-stu-id="719cf-686">Microsoft Defender Antivirus has encountered an error trying to update signatures.</span></span>
<dl><span data-ttu-id="719cf-687">
<dt>Nueva versión de inteligencia de seguridad: &lt; Nuevo número &gt; de versión</dt>
<dt>Versión de inteligencia de seguridad anterior: Versión &lt; &gt; anterior</dt>Update 
<dt> Source: Update source , por &lt; &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="719cf-687">
<dt>New security intelligence version: &lt;New version number&gt;</dt>
<dt>Previous security intelligence version: &lt;Previous version&gt;</dt>
<dt>Update Source: &lt;Update source&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="719cf-688">Carpeta de actualización de inteligencia de seguridad</span><span class="sxs-lookup"><span data-stu-id="719cf-688">Security intelligence update folder</span></span></li>
<li><span data-ttu-id="719cf-689">Servidor de actualización de inteligencia de seguridad interna</span><span class="sxs-lookup"><span data-stu-id="719cf-689">Internal security intelligence update server</span></span></li>
<li><span data-ttu-id="719cf-690">Microsoft Update Server</span><span class="sxs-lookup"><span data-stu-id="719cf-690">Microsoft Update Server</span></span></li>
<li><span data-ttu-id="719cf-691">Compartir archivos</span><span class="sxs-lookup"><span data-stu-id="719cf-691">File share</span></span></li>
<li><span data-ttu-id="719cf-692">Centro de protección contra malware de Microsoft (MMPC)</span><span class="sxs-lookup"><span data-stu-id="719cf-692">Microsoft Malware Protection Center (MMPC)</span></span></li>
</ul><span data-ttu-id="719cf-693">
</dt>
<dt>Update Stage: &lt; Update stage , por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="719cf-693">
</dt>
<dt>Update Stage: &lt;Update stage&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="719cf-694">Búsqueda</span><span class="sxs-lookup"><span data-stu-id="719cf-694">Search</span></span></li>
<li><span data-ttu-id="719cf-695">Descargar</span><span class="sxs-lookup"><span data-stu-id="719cf-695">Download</span></span></li>
<li><span data-ttu-id="719cf-696">Instalar</span><span class="sxs-lookup"><span data-stu-id="719cf-696">Install</span></span></li>
</ul><span data-ttu-id="719cf-697">
</dt>Ruta de acceso de origen: nombre del recurso compartido de archivos para convención de nomenclatura universal (UNC), nombre del servidor de 
<dt>Windows Server Update Services (WSUS)/Microsoft Update/ADL.</dt> 
<dt> Tipo de firma: &lt; Tipo de firma , por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="719cf-697">
</dt>
<dt>Source Path: File share name for Universal Naming Convention (UNC), server name for Windows Server Update Services (WSUS)/Microsoft Update/ADL.</dt>
<dt>Signature Type: &lt;Signature type&gt;, for example:</span></span> <ul>
<li><span data-ttu-id="719cf-698">Antivirus</span><span class="sxs-lookup"><span data-stu-id="719cf-698">Antivirus</span></span></li>
<li><span data-ttu-id="719cf-699">Antispyware</span><span class="sxs-lookup"><span data-stu-id="719cf-699">Antispyware</span></span></li>
<li><span data-ttu-id="719cf-700">Antimalware</span><span class="sxs-lookup"><span data-stu-id="719cf-700">Antimalware</span></span></li>
<li><span data-ttu-id="719cf-701">Sistema de inspección de red</span><span class="sxs-lookup"><span data-stu-id="719cf-701">Network Inspection System</span></span></li>
</ul><span data-ttu-id="719cf-702">
</dt>
<dt>Tipo de actualización: &lt; Tipo de &gt; actualización , Completo o Delta.</dt> 
<dt>Usuario: &lt; Dominio &gt; \& lt; Versión &gt; </dt>
<dt>actual del motor del usuario: &lt; &gt; Versión</dt>actual del motor Versión anterior del motor: Versión
<dt> &lt; anterior &gt; </dt>del motor Código de error: Código de error Código de
<dt>resultado asociado con el estado de la &lt; &gt; amenaza. Valores HRESULT estándar.</dt> 
<dt>Descripción del error: &lt; Descripción del error &gt; Descripción del error.</dt>
</span><span class="sxs-lookup"><span data-stu-id="719cf-702">
</dt>
<dt>Update Type: &lt;Update type&gt;, either Full or Delta.</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Previous Engine Version: &lt;Previous engine version&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-703">Acción del usuario:</span><span class="sxs-lookup"><span data-stu-id="719cf-703">User action:</span></span>
</td>
<td >
<span data-ttu-id="719cf-704">Este error se produce cuando hay un problema al actualizar definiciones.</span><span class="sxs-lookup"><span data-stu-id="719cf-704">This error occurs when there is a problem updating definitions.</span></span>
<span data-ttu-id="719cf-705">Para solucionar este evento:</span><span class="sxs-lookup"><span data-stu-id="719cf-705">To troubleshoot this event:</span></span>
<ol>
<li><span data-ttu-id="719cf-706"><a href="manage-updates-baselines-microsoft-defender-antivirus.md" data-raw-source="[Update definitions](manage-updates-baselines-microsoft-defender-antivirus.md)">Actualice las definiciones</a> y fuerza un nuevo análisis directamente en el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="719cf-706"><a href="manage-updates-baselines-microsoft-defender-antivirus.md" data-raw-source="[Update definitions](manage-updates-baselines-microsoft-defender-antivirus.md)">Update definitions</a> and force a rescan directly on the endpoint.</span></span></li>
<li><span data-ttu-id="719cf-707">Revisa las entradas del archivo %Windir%\WindowsUpdate.log para obtener más información sobre este error.</span><span class="sxs-lookup"><span data-stu-id="719cf-707">Review the entries in the %Windir%\WindowsUpdate.log file for more information about this error.</span></span></li>
<li><span data-ttu-id="719cf-708">Contactar al <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Soporte técnico de Microsoft</a>.</span><span class="sxs-lookup"><span data-stu-id="719cf-708">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="719cf-709">Identificador de evento: 2002</span><span class="sxs-lookup"><span data-stu-id="719cf-709">Event ID: 2002</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="719cf-710">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="719cf-710">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="719cf-711">
<b>MALWAREPROTECTION_ENGINE_UPDATED</b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-711">
<b>MALWAREPROTECTION_ENGINE_UPDATED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-712">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="719cf-712">Message:</span></span>
</td>
<td ><span data-ttu-id="719cf-713">
<b>El motor de antimalware se actualizó correctamente. </b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-713">
<b>The antimalware engine updated successfully. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-714">Descripción:</span><span class="sxs-lookup"><span data-stu-id="719cf-714">Description:</span></span>
</td>
<td >
<span data-ttu-id="719cf-715">Se ha actualizado la versión del motor de Antivirus de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="719cf-715">Microsoft Defender Antivirus engine version has been updated.</span></span>
<dl><span data-ttu-id="719cf-716">
<dt>Versión actual del motor: &lt; Versión actual &gt; del motor</dt>
<dt>Versión anterior del motor: &lt; &gt; Versión anterior</dt>del motor Tipo de motor: Tipo de motor , motor antimalware o motor del sistema de inspección de
<dt> &lt; &gt; red.</dt> 
<dt>Usuario: &lt; Dominio &gt; \& lt; Usuario &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="719cf-716">
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Previous Engine Version: &lt;Previous engine version&gt;</dt>
<dt>Engine Type: &lt;Engine type&gt;, either antimalware engine or Network Inspection System engine.</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-717">Acción del usuario:</span><span class="sxs-lookup"><span data-stu-id="719cf-717">User action:</span></span>
</td>
<td >
<span data-ttu-id="719cf-718">No es necesario realizar ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="719cf-718">No action is necessary.</span></span> <span data-ttu-id="719cf-719">El cliente antivirus de Microsoft Defender está en buen estado.</span><span class="sxs-lookup"><span data-stu-id="719cf-719">The Microsoft Defender Antivirus client is in a healthy state.</span></span> <span data-ttu-id="719cf-720">Este evento se notifica cuando el motor de antimalware se actualiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="719cf-720">This event is reported when the antimalware engine is successfully updated.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="719cf-721">Identificador de evento: 2003</span><span class="sxs-lookup"><span data-stu-id="719cf-721">Event ID: 2003</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="719cf-722">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="719cf-722">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="719cf-723">
<b>MALWAREPROTECTION_ENGINE_UPDATE_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-723">
<b>MALWAREPROTECTION_ENGINE_UPDATE_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-724">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="719cf-724">Message:</span></span>
</td>
<td ><span data-ttu-id="719cf-725">
<b>Error en la actualización del motor de antimalware. </b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-725">
<b>The antimalware engine update failed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-726">Descripción:</span><span class="sxs-lookup"><span data-stu-id="719cf-726">Description:</span></span>
</td>
<td >
<span data-ttu-id="719cf-727">Antivirus de Microsoft Defender ha encontrado un error al intentar actualizar el motor.</span><span class="sxs-lookup"><span data-stu-id="719cf-727">Microsoft Defender Antivirus has encountered an error trying to update the engine.</span></span>
<dl><span data-ttu-id="719cf-728">
<dt>Nueva versión del motor:</dt>
<dt>Versión anterior del motor: &lt; &gt; </dt>Versión anterior del motor Tipo de motor: Tipo de motor , motor antimalware o motor del sistema de inspección de
<dt> &lt; &gt; red.</dt> 
<dt>Usuario: &lt; Dominio &gt; \& lt; Código &gt; </dt>
<dt>de error del usuario: Código de error &lt; Código de resultado asociado con el estado de &gt; amenaza. Valores HRESULT estándar.</dt> 
<dt>Descripción del error: &lt; Descripción del error &gt; Descripción del error.</dt>
</span><span class="sxs-lookup"><span data-stu-id="719cf-728">
<dt>New Engine Version:</dt>
<dt>Previous Engine Version: &lt;Previous engine version&gt;</dt>
<dt>Engine Type: &lt;Engine type&gt;, either antimalware engine or Network Inspection System engine.</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-729">Acción del usuario:</span><span class="sxs-lookup"><span data-stu-id="719cf-729">User action:</span></span>
</td>
<td >
<span data-ttu-id="719cf-730">Error en la actualización del cliente de Antivirus de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="719cf-730">The Microsoft Defender Antivirus client update failed.</span></span> <span data-ttu-id="719cf-731">Este evento se produce cuando el cliente no se actualiza.</span><span class="sxs-lookup"><span data-stu-id="719cf-731">This event occurs when the client fails to update itself.</span></span> <span data-ttu-id="719cf-732">Este evento suele deberse a una interrupción en la conectividad de red durante una actualización.</span><span class="sxs-lookup"><span data-stu-id="719cf-732">This event is usually due to an interruption in network connectivity during an update.</span></span>
<span data-ttu-id="719cf-733">Para solucionar este evento:</span><span class="sxs-lookup"><span data-stu-id="719cf-733">To troubleshoot this event:</span></span>
<ol>
<li><span data-ttu-id="719cf-734"><a href="manage-updates-baselines-microsoft-defender-antivirus.md" data-raw-source="[Update definitions](manage-updates-baselines-microsoft-defender-antivirus.md)">Actualice las definiciones</a> y fuerza un nuevo análisis directamente en el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="719cf-734"><a href="manage-updates-baselines-microsoft-defender-antivirus.md" data-raw-source="[Update definitions](manage-updates-baselines-microsoft-defender-antivirus.md)">Update definitions</a> and force a rescan directly on the endpoint.</span></span></li>
<li><span data-ttu-id="719cf-735">Contactar al <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Soporte técnico de Microsoft</a>.</span><span class="sxs-lookup"><span data-stu-id="719cf-735">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="719cf-736">Identificador de evento: 2004</span><span class="sxs-lookup"><span data-stu-id="719cf-736">Event ID: 2004</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="719cf-737">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="719cf-737">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="719cf-738">
<b>MALWAREPROTECTION_SIGNATURE_REVERSION</b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-738">
<b>MALWAREPROTECTION_SIGNATURE_REVERSION</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-739">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="719cf-739">Message:</span></span>
</td>
<td ><span data-ttu-id="719cf-740">
<b>Hubo un problema al cargar definiciones de antimalware. El motor de antimalware intentará cargar el último conjunto de definiciones bien conocido.</b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-740">
<b>There was a problem loading antimalware definitions. The antimalware engine will attempt to load the last-known good set of definitions.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-741">Descripción:</span><span class="sxs-lookup"><span data-stu-id="719cf-741">Description:</span></span>
</td>
<td >
<span data-ttu-id="719cf-742">Antivirus de Microsoft Defender ha encontrado un error al intentar cargar firmas e intentará volver a un conjunto de firmas conocido.</span><span class="sxs-lookup"><span data-stu-id="719cf-742">Microsoft Defender Antivirus has encountered an error trying to load signatures and will attempt reverting back to a known-good set of signatures.</span></span>
<dl><span data-ttu-id="719cf-743">
<dt>Firmas intentadas:</dt>
<dt>Código de error: Código de error Código de resultado asociado con el estado de &lt; &gt; amenaza. Valores HRESULT estándar.</dt> 
<dt>Descripción del error: &lt; Descripción del error &gt; Descripción del error.</dt> 
<dt>Versión de firma: &lt; Versión &gt; de definición</dt>
<dt>Versión del motor: &lt; versión &gt; del motor antimalware</dt>
</span><span class="sxs-lookup"><span data-stu-id="719cf-743">
<dt>Signatures Attempted:</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-744">Acción del usuario:</span><span class="sxs-lookup"><span data-stu-id="719cf-744">User action:</span></span>
</td>
<td >
<span data-ttu-id="719cf-745">El cliente de Antivirus de Microsoft Defender intentó descargar e instalar el archivo de definiciones más reciente y falló.</span><span class="sxs-lookup"><span data-stu-id="719cf-745">The Microsoft Defender Antivirus client attempted to download and install the latest definitions file and failed.</span></span> <span data-ttu-id="719cf-746">Este error puede producirse cuando el cliente encuentra un error al intentar cargar las definiciones o si el archivo está dañado.</span><span class="sxs-lookup"><span data-stu-id="719cf-746">This error can occur when the client encounters an error while trying to load the definitions, or if the file is corrupt.</span></span> <span data-ttu-id="719cf-747">Antivirus de Microsoft Defender intentará volver a un conjunto de definiciones conocido.</span><span class="sxs-lookup"><span data-stu-id="719cf-747">Microsoft Defender Antivirus will attempt to revert back to a known-good set of definitions.</span></span>
<span data-ttu-id="719cf-748">Para solucionar este evento:</span><span class="sxs-lookup"><span data-stu-id="719cf-748">To troubleshoot this event:</span></span>
<ol>
<li><span data-ttu-id="719cf-749">Reinicie el equipo e inténtelo de nuevo.</span><span class="sxs-lookup"><span data-stu-id="719cf-749">Restart the computer and try again.</span></span></li>
<li><span data-ttu-id="719cf-750">Descargue las definiciones más recientes del sitio <a href="https://aka.ms/wdsi">de Inteligencia de seguridad de Microsoft</a>.</span><span class="sxs-lookup"><span data-stu-id="719cf-750">Download the latest definitions from the <a href="https://aka.ms/wdsi">Microsoft Security Intelligence site</a>.</span></span>
<span data-ttu-id="719cf-751">Nota: El tamaño del archivo de definiciones descargado del sitio puede superar los 60 MB y no debe usarse como solución a largo plazo para actualizar definiciones.</span><span class="sxs-lookup"><span data-stu-id="719cf-751">Note: The size of the definitions file downloaded from the site can exceed 60 MB and should not be used as a long-term solution for updating definitions.</span></span>
</li>
<li><span data-ttu-id="719cf-752">Contactar al <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Soporte técnico de Microsoft</a>.</span><span class="sxs-lookup"><span data-stu-id="719cf-752">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="719cf-753">Identificador de evento: 2005</span><span class="sxs-lookup"><span data-stu-id="719cf-753">Event ID: 2005</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="719cf-754">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="719cf-754">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="719cf-755">
<b>MALWAREPROTECTION_ENGINE_UPDATE_PLATFORMOUTOFDATE</b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-755">
<b>MALWAREPROTECTION_ENGINE_UPDATE_PLATFORMOUTOFDATE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-756">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="719cf-756">Message:</span></span>
</td>
<td ><span data-ttu-id="719cf-757">
<b>El motor de antimalware no se pudo cargar porque la plataforma antimalware no está actualizada. La plataforma antimalware cargará el último motor antimalware bueno conocido e intentará actualizarlo.</b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-757">
<b>The antimalware engine failed to load because the antimalware platform is out of date. The antimalware platform will load the last-known good antimalware engine and attempt to update.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-758">Descripción:</span><span class="sxs-lookup"><span data-stu-id="719cf-758">Description:</span></span>
</td>
<td >
<span data-ttu-id="719cf-759">Antivirus de Microsoft Defender no pudo cargar el motor de antimalware porque no se admite la versión actual de la plataforma.</span><span class="sxs-lookup"><span data-stu-id="719cf-759">Microsoft Defender Antivirus could not load antimalware engine because current platform version is not supported.</span></span> <span data-ttu-id="719cf-760">Antivirus de Microsoft Defender volverá al último motor conocido y se intenta actualizar la plataforma.</span><span class="sxs-lookup"><span data-stu-id="719cf-760">Microsoft Defender Antivirus will revert back to the last known-good engine and a platform update will be attempted.</span></span>
<dl><span data-ttu-id="719cf-761">
<dt>Versión actual de la plataforma: &lt; versión actual de la plataforma&gt;</dt>
</span><span class="sxs-lookup"><span data-stu-id="719cf-761">
<dt>Current Platform Version: &lt;Current platform version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="719cf-762">Identificador de evento: 2006</span><span class="sxs-lookup"><span data-stu-id="719cf-762">Event ID: 2006</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="719cf-763">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="719cf-763">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="719cf-764">
<b>MALWAREPROTECTION_PLATFORM_UPDATE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-764">
<b>MALWAREPROTECTION_PLATFORM_UPDATE_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-765">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="719cf-765">Message:</span></span>
</td>
<td ><span data-ttu-id="719cf-766">
<b>Error en la actualización de la plataforma. </b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-766">
<b>The platform update failed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-767">Descripción:</span><span class="sxs-lookup"><span data-stu-id="719cf-767">Description:</span></span>
</td>
<td >
<span data-ttu-id="719cf-768">Antivirus de Microsoft Defender ha encontrado un error al intentar actualizar la plataforma.</span><span class="sxs-lookup"><span data-stu-id="719cf-768">Microsoft Defender Antivirus has encountered an error trying to update the platform.</span></span>
<dl><span data-ttu-id="719cf-769">
<dt>Versión actual de la plataforma: &lt; Versión actual &gt; de la plataforma</dt>
<dt>Código de error: Código de error &lt; Código de resultado asociado con el estado de &gt; amenaza. Valores HRESULT estándar.</dt> 
<dt>Descripción del error: &lt; Descripción del error &gt; Descripción del error.</dt>
</span><span class="sxs-lookup"><span data-stu-id="719cf-769">
<dt>Current Platform Version: &lt;Current platform version&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="719cf-770">Identificador de evento: 2007</span><span class="sxs-lookup"><span data-stu-id="719cf-770">Event ID: 2007</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="719cf-771">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="719cf-771">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="719cf-772">
<b>MALWAREPROTECTION_PLATFORM_ALMOSTOUTOFDATE</b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-772">
<b>MALWAREPROTECTION_PLATFORM_ALMOSTOUTOFDATE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-773">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="719cf-773">Message:</span></span>
</td>
<td ><span data-ttu-id="719cf-774">
<b>La plataforma pronto estará des actualizada. Descargue la plataforma más reciente para mantener la protección actualizada.</b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-774">
<b>The platform will soon be out of date. Download the latest platform to maintain up-to-date protection.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-775">Descripción:</span><span class="sxs-lookup"><span data-stu-id="719cf-775">Description:</span></span>
</td>
<td >
<span data-ttu-id="719cf-776">Antivirus de Microsoft Defender necesitará pronto una versión de plataforma más reciente para admitir versiones futuras del motor de antimalware.</span><span class="sxs-lookup"><span data-stu-id="719cf-776">Microsoft Defender Antivirus will soon require a newer platform version to support future versions of the antimalware engine.</span></span> <span data-ttu-id="719cf-777">Descargue la plataforma antivirus de Microsoft Defender más reciente para mantener el mejor nivel de protección disponible.</span><span class="sxs-lookup"><span data-stu-id="719cf-777">Download the latest Microsoft Defender Antivirus platform to maintain the best level of protection available.</span></span>
<dl><span data-ttu-id="719cf-778">
<dt>Versión actual de la plataforma: &lt; versión actual de la plataforma&gt;</dt>
</span><span class="sxs-lookup"><span data-stu-id="719cf-778">
<dt>Current Platform Version: &lt;Current platform version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="719cf-779">Identificador de evento: 2010</span><span class="sxs-lookup"><span data-stu-id="719cf-779">Event ID: 2010</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="719cf-780">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="719cf-780">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="719cf-781">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_UPDATED </b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-781">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_UPDATED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-782">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="719cf-782">Message:</span></span>
</td>
<td ><span data-ttu-id="719cf-783">
<b>El motor de antimalware usaba el servicio de firma dinámica para obtener definiciones adicionales. </b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-783">
<b>The antimalware engine used the Dynamic Signature Service to get additional definitions. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-784">Descripción:</span><span class="sxs-lookup"><span data-stu-id="719cf-784">Description:</span></span>
</td>
<td >
<span data-ttu-id="719cf-785">El Antivirus de Microsoft Defender <i>usó el Servicio de firmas dinámicas</i> para recuperar firmas adicionales para ayudar a proteger el equipo.</span><span class="sxs-lookup"><span data-stu-id="719cf-785">Microsoft Defender Antivirus used <i>Dynamic Signature Service</i> to retrieve additional signatures to help protect your machine.</span></span>
<dl><span data-ttu-id="719cf-786">
<dt>Versión de firma actual: &lt; Versión de &gt; firma actual</dt> 
<dt> Tipo de firma: Tipo de firma , &lt; por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="719cf-786">
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Signature Type: &lt;Signature type&gt;, for example:</span></span> <ul>
<li><span data-ttu-id="719cf-787">Antivirus</span><span class="sxs-lookup"><span data-stu-id="719cf-787">Antivirus</span></span></li>
<li><span data-ttu-id="719cf-788">Antispyware</span><span class="sxs-lookup"><span data-stu-id="719cf-788">Antispyware</span></span></li>
<li><span data-ttu-id="719cf-789">Antimalware</span><span class="sxs-lookup"><span data-stu-id="719cf-789">Antimalware</span></span></li>
<li><span data-ttu-id="719cf-790">Sistema de inspección de red</span><span class="sxs-lookup"><span data-stu-id="719cf-790">Network Inspection System</span></span></li>
</ul><span data-ttu-id="719cf-791">
</dt>
<dt>Versión actual del motor: &lt; Versión actual &gt; del motor</dt> 
<dt> Tipo de firma dinámica: Tipo de firma &lt; dinámica , por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="719cf-791">
</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Dynamic Signature Type: &lt;Dynamic signature type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="719cf-792">Version</span><span class="sxs-lookup"><span data-stu-id="719cf-792">Version</span></span></li>
<li><span data-ttu-id="719cf-793">Timestamp</span><span class="sxs-lookup"><span data-stu-id="719cf-793">Timestamp</span></span></li>
<li><span data-ttu-id="719cf-794">Sin límite</span><span class="sxs-lookup"><span data-stu-id="719cf-794">No limit</span></span></li>
<li><span data-ttu-id="719cf-795">Duración</span><span class="sxs-lookup"><span data-stu-id="719cf-795">Duration</span></span></li>
</ul><span data-ttu-id="719cf-796">
</dt>
<dt>Ruta de persistencia: &lt; Path &gt; </dt>
<dt>Dynamic Signature Version: &lt; Version number &gt; </dt>Dynamic Signature Compilation
<dt>Timestamp: &lt; &gt; Timestamp</dt> 
<dt> Persistence Limit Type: &lt; Persistence limit type , for &gt; example:</span><span class="sxs-lookup"><span data-stu-id="719cf-796">
</dt>
<dt>Persistence Path: &lt;Path&gt;</dt>
<dt>Dynamic Signature Version: &lt;Version number&gt;</dt>
<dt>Dynamic Signature Compilation Timestamp: &lt;Timestamp&gt;</dt>
<dt>Persistence Limit Type: &lt;Persistence limit type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="719cf-797">Versión de VDM</span><span class="sxs-lookup"><span data-stu-id="719cf-797">VDM version</span></span></li>
<li><span data-ttu-id="719cf-798">Timestamp</span><span class="sxs-lookup"><span data-stu-id="719cf-798">Timestamp</span></span></li>
<li><span data-ttu-id="719cf-799">Sin límite</span><span class="sxs-lookup"><span data-stu-id="719cf-799">No limit</span></span></li>
</ul><span data-ttu-id="719cf-800">
</dt>
<dt>Límite de persistencia: límite de persistencia de la firma fastpath.</dt>
</span><span class="sxs-lookup"><span data-stu-id="719cf-800">
</dt>
<dt>Persistence Limit: Persistence limit of the fastpath signature.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="719cf-801">Identificador de evento: 2011</span><span class="sxs-lookup"><span data-stu-id="719cf-801">Event ID: 2011</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="719cf-802">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="719cf-802">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="719cf-803">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_DELETED </b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-803">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_DELETED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-804">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="719cf-804">Message:</span></span>
</td>
<td ><span data-ttu-id="719cf-805">
<b>El servicio de firma dinámica eliminó las definiciones dinámicas des actualizadas. </b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-805">
<b>The Dynamic Signature Service deleted the out-of-date dynamic definitions. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-806">Descripción:</span><span class="sxs-lookup"><span data-stu-id="719cf-806">Description:</span></span>
</td>
<td >
<span data-ttu-id="719cf-807">El Antivirus de Microsoft Defender <i>usó el servicio de firmas dinámicas</i> para descartar firmas obsoletas.</span><span class="sxs-lookup"><span data-stu-id="719cf-807">Microsoft Defender Antivirus used <i>Dynamic Signature Service</i> to discard obsolete signatures.</span></span>
<dl><span data-ttu-id="719cf-808">
<dt>Versión de firma actual: &lt; Versión de &gt; firma actual</dt> 
<dt> Tipo de firma: Tipo de firma , &lt; por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="719cf-808">
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Signature Type: &lt;Signature type&gt;, for example:</span></span> <ul>
<li><span data-ttu-id="719cf-809">Antivirus</span><span class="sxs-lookup"><span data-stu-id="719cf-809">Antivirus</span></span></li>
<li><span data-ttu-id="719cf-810">Antispyware</span><span class="sxs-lookup"><span data-stu-id="719cf-810">Antispyware</span></span></li>
<li><span data-ttu-id="719cf-811">Antimalware</span><span class="sxs-lookup"><span data-stu-id="719cf-811">Antimalware</span></span></li>
<li><span data-ttu-id="719cf-812">Sistema de inspección de red</span><span class="sxs-lookup"><span data-stu-id="719cf-812">Network Inspection System</span></span></li>
</ul><span data-ttu-id="719cf-813">
</dt>
<dt>Versión actual del motor: &lt; Versión actual &gt; del motor</dt> 
<dt> Tipo de firma dinámica: Tipo de firma &lt; dinámica , por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="719cf-813">
</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Dynamic Signature Type: &lt;Dynamic signature type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="719cf-814">Version</span><span class="sxs-lookup"><span data-stu-id="719cf-814">Version</span></span></li>
<li><span data-ttu-id="719cf-815">Timestamp</span><span class="sxs-lookup"><span data-stu-id="719cf-815">Timestamp</span></span></li>
<li><span data-ttu-id="719cf-816">Sin límite</span><span class="sxs-lookup"><span data-stu-id="719cf-816">No limit</span></span></li>
<li><span data-ttu-id="719cf-817">Duración</span><span class="sxs-lookup"><span data-stu-id="719cf-817">Duration</span></span></li>
</ul><span data-ttu-id="719cf-818">
</dt>
<dt>Ruta de persistencia: &lt; Path &gt; </dt>
<dt>Dynamic Signature Version: &lt; Version &gt; number</dt>Dynamic Signature Compilation
<dt>Timestamp: &lt; Timestamp &gt; </dt>Removal
<dt>Reason:</dt> 
<dt> Persistence Limit Type: &lt; Persistence limit type , for &gt; example:</span><span class="sxs-lookup"><span data-stu-id="719cf-818">
</dt>
<dt>Persistence Path: &lt;Path&gt;</dt>
<dt>Dynamic Signature Version: &lt;Version number&gt;</dt>
<dt>Dynamic Signature Compilation Timestamp: &lt;Timestamp&gt;</dt>
<dt>Removal Reason:</dt>
<dt>Persistence Limit Type: &lt;Persistence limit type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="719cf-819">Versión de VDM</span><span class="sxs-lookup"><span data-stu-id="719cf-819">VDM version</span></span></li>
<li><span data-ttu-id="719cf-820">Timestamp</span><span class="sxs-lookup"><span data-stu-id="719cf-820">Timestamp</span></span></li>
<li><span data-ttu-id="719cf-821">Sin límite</span><span class="sxs-lookup"><span data-stu-id="719cf-821">No limit</span></span></li>
</ul><span data-ttu-id="719cf-822">
</dt>
<dt>Límite de persistencia: límite de persistencia de la firma fastpath.</dt>
</span><span class="sxs-lookup"><span data-stu-id="719cf-822">
</dt>
<dt>Persistence Limit: Persistence limit of the fastpath signature.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-823">Acción del usuario:</span><span class="sxs-lookup"><span data-stu-id="719cf-823">User action:</span></span>
</td>
<td >
<span data-ttu-id="719cf-824">No es necesario realizar ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="719cf-824">No action is necessary.</span></span> <span data-ttu-id="719cf-825">El cliente antivirus de Microsoft Defender está en buen estado.</span><span class="sxs-lookup"><span data-stu-id="719cf-825">The Microsoft Defender Antivirus client is in a healthy state.</span></span> <span data-ttu-id="719cf-826">Este evento se notifica cuando el servicio de firma dinámica elimina correctamente definiciones dinámicas des actualizadas.</span><span class="sxs-lookup"><span data-stu-id="719cf-826">This event is reported when the Dynamic Signature Service successfully deletes out-of-date dynamic definitions.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="719cf-827">Identificador de evento: 2012</span><span class="sxs-lookup"><span data-stu-id="719cf-827">Event ID: 2012</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="719cf-828">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="719cf-828">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="719cf-829">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_UPDATE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-829">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_UPDATE_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-830">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="719cf-830">Message:</span></span>
</td>
<td ><span data-ttu-id="719cf-831">
<b>El motor de antimalware encontró un error al intentar usar el servicio de firma dinámica. </b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-831">
<b>The antimalware engine encountered an error when trying to use the Dynamic Signature Service. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-832">Descripción:</span><span class="sxs-lookup"><span data-stu-id="719cf-832">Description:</span></span>
</td>
<td >
<span data-ttu-id="719cf-833">Antivirus de Microsoft Defender ha encontrado un error al intentar usar <i>el servicio de firma dinámica</i>.</span><span class="sxs-lookup"><span data-stu-id="719cf-833">Microsoft Defender Antivirus has encountered an error trying to use <i>Dynamic Signature Service</i>.</span></span>
<dl><span data-ttu-id="719cf-834">
<dt>Versión de firma actual: &lt; Versión de &gt; firma actual</dt> 
<dt> Tipo de firma: Tipo de firma , &lt; por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="719cf-834">
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Signature Type: &lt;Signature type&gt;, for example:</span></span> <ul>
<li><span data-ttu-id="719cf-835">Antivirus</span><span class="sxs-lookup"><span data-stu-id="719cf-835">Antivirus</span></span></li>
<li><span data-ttu-id="719cf-836">Antispyware</span><span class="sxs-lookup"><span data-stu-id="719cf-836">Antispyware</span></span></li>
<li><span data-ttu-id="719cf-837">Antimalware</span><span class="sxs-lookup"><span data-stu-id="719cf-837">Antimalware</span></span></li>
<li><span data-ttu-id="719cf-838">Sistema de inspección de red</span><span class="sxs-lookup"><span data-stu-id="719cf-838">Network Inspection System</span></span></li>
</ul><span data-ttu-id="719cf-839">
</dt>
<dt>Versión actual del motor: &lt; Versión del &gt; motor actual</dt>
<dt>Código de error: Código de error &lt; Código de resultado asociado con el estado de &gt; amenaza. Valores HRESULT estándar.</dt> 
<dt>Descripción del error: &lt; Descripción del error &gt; Descripción del error.</dt> 
<dt> Tipo de firma dinámica: &lt; Tipo de firma dinámica , por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="719cf-839">
</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Dynamic Signature Type: &lt;Dynamic signature type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="719cf-840">Version</span><span class="sxs-lookup"><span data-stu-id="719cf-840">Version</span></span></li>
<li><span data-ttu-id="719cf-841">Timestamp</span><span class="sxs-lookup"><span data-stu-id="719cf-841">Timestamp</span></span></li>
<li><span data-ttu-id="719cf-842">Sin límite</span><span class="sxs-lookup"><span data-stu-id="719cf-842">No limit</span></span></li>
<li><span data-ttu-id="719cf-843">Duración</span><span class="sxs-lookup"><span data-stu-id="719cf-843">Duration</span></span></li>
</ul><span data-ttu-id="719cf-844">
</dt>
<dt>Ruta de persistencia: &lt; Path &gt; </dt>
<dt>Dynamic Signature Version: &lt; Version number &gt; </dt>Dynamic Signature Compilation
<dt>Timestamp: &lt; &gt; Timestamp</dt> 
<dt> Persistence Limit Type: &lt; Persistence limit type , for &gt; example:</span><span class="sxs-lookup"><span data-stu-id="719cf-844">
</dt>
<dt>Persistence Path: &lt;Path&gt;</dt>
<dt>Dynamic Signature Version: &lt;Version number&gt;</dt>
<dt>Dynamic Signature Compilation Timestamp: &lt;Timestamp&gt;</dt>
<dt>Persistence Limit Type: &lt;Persistence limit type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="719cf-845">Versión de VDM</span><span class="sxs-lookup"><span data-stu-id="719cf-845">VDM version</span></span></li>
<li><span data-ttu-id="719cf-846">Timestamp</span><span class="sxs-lookup"><span data-stu-id="719cf-846">Timestamp</span></span></li>
<li><span data-ttu-id="719cf-847">Sin límite</span><span class="sxs-lookup"><span data-stu-id="719cf-847">No limit</span></span></li>
</ul><span data-ttu-id="719cf-848">
</dt>
<dt>Límite de persistencia: límite de persistencia de la firma fastpath.</dt>
</span><span class="sxs-lookup"><span data-stu-id="719cf-848">
</dt>
<dt>Persistence Limit: Persistence limit of the fastpath signature.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-849">Acción del usuario:</span><span class="sxs-lookup"><span data-stu-id="719cf-849">User action:</span></span>
</td>
<td >
<span data-ttu-id="719cf-850">Comprueba la configuración de conectividad a Internet.</span><span class="sxs-lookup"><span data-stu-id="719cf-850">Check your Internet connectivity settings.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="719cf-851">Identificador de evento: 2013</span><span class="sxs-lookup"><span data-stu-id="719cf-851">Event ID: 2013</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="719cf-852">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="719cf-852">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="719cf-853">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_DELETED_ALL </b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-853">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_DELETED_ALL </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-854">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="719cf-854">Message:</span></span>
</td>
<td ><span data-ttu-id="719cf-855">
<b>El servicio de firma dinámica eliminó todas las definiciones dinámicas. </b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-855">
<b>The Dynamic Signature Service deleted all dynamic definitions. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-856">Descripción:</span><span class="sxs-lookup"><span data-stu-id="719cf-856">Description:</span></span>
</td>
<td >
<span data-ttu-id="719cf-857">El Antivirus de Microsoft Defender descartó todas <i>las firmas del servicio de firmas</i> dinámicas.</span><span class="sxs-lookup"><span data-stu-id="719cf-857">Microsoft Defender Antivirus discarded all <i>Dynamic Signature Service</i> signatures.</span></span>
<dl><span data-ttu-id="719cf-858">
<dt>Versión actual de la firma: &lt; versión actual de la firma&gt;</dt>
</span><span class="sxs-lookup"><span data-stu-id="719cf-858">
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="719cf-859">Identificador de evento: 2020</span><span class="sxs-lookup"><span data-stu-id="719cf-859">Event ID: 2020</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="719cf-860">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="719cf-860">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="719cf-861">
<b>MALWAREPROTECTION_CLOUD_CLEAN_RESTORE_FILE_DOWNLOADED </b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-861">
<b>MALWAREPROTECTION_CLOUD_CLEAN_RESTORE_FILE_DOWNLOADED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-862">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="719cf-862">Message:</span></span>
</td>
<td ><span data-ttu-id="719cf-863">
<b>El motor de antimalware descargó un archivo limpio. </b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-863">
<b>The antimalware engine downloaded a clean file. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-864">Descripción:</span><span class="sxs-lookup"><span data-stu-id="719cf-864">Description:</span></span>
</td>
<td >
<span data-ttu-id="719cf-865">Antivirus de Microsoft Defender descargó un archivo limpio.</span><span class="sxs-lookup"><span data-stu-id="719cf-865">Microsoft Defender Antivirus downloaded a clean file.</span></span>
<dl><span data-ttu-id="719cf-866">
<dt>Nombre de archivo: &lt; Nombre de &gt; archivo Nombre del archivo.</dt> 
<dt>Versión de firma actual: &lt; Versión actual &gt; del motor</dt>
<dt>de firma Actual: versión actual del &lt; motor &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="719cf-866">
<dt>Filename: &lt;File name&gt; Name of the file.</dt>
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="719cf-867">Identificador de evento: 2021</span><span class="sxs-lookup"><span data-stu-id="719cf-867">Event ID: 2021</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="719cf-868">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="719cf-868">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="719cf-869">
<b>MALWAREPROTECTION_CLOUD_CLEAN_RESTORE_FILE_DOWNLOAD_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-869">
<b>MALWAREPROTECTION_CLOUD_CLEAN_RESTORE_FILE_DOWNLOAD_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-870">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="719cf-870">Message:</span></span>
</td>
<td ><span data-ttu-id="719cf-871">
<b>El motor de antimalware no pudo descargar un archivo limpio. </b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-871">
<b>The antimalware engine failed to download a clean file. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-872">Descripción:</span><span class="sxs-lookup"><span data-stu-id="719cf-872">Description:</span></span>
</td>
<td >
<span data-ttu-id="719cf-873">Antivirus de Microsoft Defender ha encontrado un error al intentar descargar un archivo limpio.</span><span class="sxs-lookup"><span data-stu-id="719cf-873">Microsoft Defender Antivirus has encountered an error trying to download a clean file.</span></span>
<dl><span data-ttu-id="719cf-874">
<dt>Nombre de archivo: &lt; Nombre de &gt; archivo Nombre del archivo.</dt> 
<dt>Versión de firma actual: &lt; Versión de &gt; firma actual</dt>
<dt>Versión actual del motor: Versión actual &lt; del &gt; </dt>motor Código de error: Código de
<dt>error Código de resultado asociado con el estado de &lt; &gt; amenaza. Valores HRESULT estándar.</dt> 
<dt>Descripción del error: &lt; Descripción del error &gt; Descripción del error.</dt>
</span><span class="sxs-lookup"><span data-stu-id="719cf-874">
<dt>Filename: &lt;File name&gt; Name of the file.</dt>
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-875">Acción del usuario:</span><span class="sxs-lookup"><span data-stu-id="719cf-875">User action:</span></span>
</td>
<td >
<span data-ttu-id="719cf-876">Comprueba la configuración de conectividad a Internet.</span><span class="sxs-lookup"><span data-stu-id="719cf-876">Check your Internet connectivity settings.</span></span>
<span data-ttu-id="719cf-877">El cliente de Antivirus de Microsoft Defender encontró un error al usar el servicio de firma dinámica para descargar las definiciones más recientes en una amenaza específica.</span><span class="sxs-lookup"><span data-stu-id="719cf-877">The Microsoft Defender Antivirus client encountered an error when using the Dynamic Signature Service to download the latest definitions to a specific threat.</span></span> <span data-ttu-id="719cf-878">Es probable que este error se deba a un problema de conectividad de red.</span><span class="sxs-lookup"><span data-stu-id="719cf-878">This error is likely caused by a network connectivity issue.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="719cf-879">Identificador de evento: 2030</span><span class="sxs-lookup"><span data-stu-id="719cf-879">Event ID: 2030</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="719cf-880">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="719cf-880">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="719cf-881">
<b>MALWAREPROTECTION_OFFLINE_SCAN_INSTALLED</b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-881">
<b>MALWAREPROTECTION_OFFLINE_SCAN_INSTALLED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-882">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="719cf-882">Message:</span></span>
</td>
<td ><span data-ttu-id="719cf-883">
<b>El motor de antimalware se descargó y está configurado para ejecutarse sin conexión en el siguiente reinicio del sistema.</b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-883">
<b>The antimalware engine was downloaded and is configured to run offline on the next system restart.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-884">Descripción:</span><span class="sxs-lookup"><span data-stu-id="719cf-884">Description:</span></span>
</td>
<td >
<span data-ttu-id="719cf-885">Antivirus de Microsoft Defender descargado y configurado antivirus sin conexión para que se ejecute en el siguiente reinicio.</span><span class="sxs-lookup"><span data-stu-id="719cf-885">Microsoft Defender Antivirus downloaded and configured offline antivirus to run on the next reboot.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="719cf-886">Identificador de evento: 2031</span><span class="sxs-lookup"><span data-stu-id="719cf-886">Event ID: 2031</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="719cf-887">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="719cf-887">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="719cf-888">
<b>MALWAREPROTECTION_OFFLINE_SCAN_INSTALL_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-888">
<b>MALWAREPROTECTION_OFFLINE_SCAN_INSTALL_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-889">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="719cf-889">Message:</span></span>
</td>
<td ><span data-ttu-id="719cf-890">
<b>El motor de antimalware no pudo descargar ni configurar un examen sin conexión.</b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-890">
<b>The antimalware engine was unable to download and configure an offline scan.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-891">Descripción:</span><span class="sxs-lookup"><span data-stu-id="719cf-891">Description:</span></span>
</td>
<td >
<span data-ttu-id="719cf-892">Antivirus de Microsoft Defender ha encontrado un error al intentar descargar y configurar antivirus sin conexión.</span><span class="sxs-lookup"><span data-stu-id="719cf-892">Microsoft Defender Antivirus has encountered an error trying to download and configure offline antivirus.</span></span>
<dl><span data-ttu-id="719cf-893">
<dt>Código de error: &lt; Código de error &gt; Código de resultado asociado con el estado de amenaza. Valores HRESULT estándar.</dt> 
<dt>Descripción del error: &lt; Descripción del error &gt; Descripción del error.</dt>
</span><span class="sxs-lookup"><span data-stu-id="719cf-893">
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="719cf-894">Identificador de evento: 2040</span><span class="sxs-lookup"><span data-stu-id="719cf-894">Event ID: 2040</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="719cf-895">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="719cf-895">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="719cf-896">
<b>MALWAREPROTECTION_OS_EXPIRING </b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-896">
<b>MALWAREPROTECTION_OS_EXPIRING </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-897">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="719cf-897">Message:</span></span>
</td>
<td ><span data-ttu-id="719cf-898">
<b>La compatibilidad con antimalware para esta versión del sistema operativo finalizará próximamente. </b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-898">
<b>Antimalware support for this operating system version will soon end. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-899">Descripción:</span><span class="sxs-lookup"><span data-stu-id="719cf-899">Description:</span></span>
</td>
<td >
<span data-ttu-id="719cf-900">La compatibilidad con el sistema operativo expirará en breve.</span><span class="sxs-lookup"><span data-stu-id="719cf-900">The support for your operating system will expire shortly.</span></span> <span data-ttu-id="719cf-901">Ejecutar Antivirus de Microsoft Defender en un sistema operativo no compatible no es una solución adecuada para protegerse contra amenazas.</span><span class="sxs-lookup"><span data-stu-id="719cf-901">Running Microsoft Defender Antivirus on an out of support operating system is not an adequate solution to protect against threats.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="719cf-902">Identificador de evento: 2041</span><span class="sxs-lookup"><span data-stu-id="719cf-902">Event ID: 2041</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="719cf-903">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="719cf-903">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="719cf-904">
<b>MALWAREPROTECTION_OS_EOL </b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-904">
<b>MALWAREPROTECTION_OS_EOL </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-905">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="719cf-905">Message:</span></span>
</td>
<td ><span data-ttu-id="719cf-906">
<b>La compatibilidad con antimalware para este sistema operativo ha finalizado. Debe actualizar el sistema operativo para que la compatibilidad continúe. </b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-906">
<b>Antimalware support for this operating system has ended. You must upgrade the operating system for continued support. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-907">Descripción:</span><span class="sxs-lookup"><span data-stu-id="719cf-907">Description:</span></span>
</td>
<td >
<span data-ttu-id="719cf-908">La compatibilidad con el sistema operativo ha expirado.</span><span class="sxs-lookup"><span data-stu-id="719cf-908">The support for your operating system has expired.</span></span> <span data-ttu-id="719cf-909">Ejecutar Antivirus de Microsoft Defender en un sistema operativo no compatible no es una solución adecuada para protegerse contra amenazas.</span><span class="sxs-lookup"><span data-stu-id="719cf-909">Running Microsoft Defender Antivirus on an out of support operating system is not an adequate solution to protect against threats.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="719cf-910">Identificador de evento: 2042</span><span class="sxs-lookup"><span data-stu-id="719cf-910">Event ID: 2042</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="719cf-911">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="719cf-911">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="719cf-912">
<b>MALWAREPROTECTION_PROTECTION_EOL </b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-912">
<b>MALWAREPROTECTION_PROTECTION_EOL </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-913">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="719cf-913">Message:</span></span>
</td>
<td ><span data-ttu-id="719cf-914">
<b>El motor de antimalware ya no es compatible con este sistema operativo y ya no protege el sistema contra malware. </b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-914">
<b>The antimalware engine no longer supports this operating system, and is no longer protecting your system from malware. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-915">Descripción:</span><span class="sxs-lookup"><span data-stu-id="719cf-915">Description:</span></span>
</td>
<td >
<span data-ttu-id="719cf-916">La compatibilidad con el sistema operativo ha expirado.</span><span class="sxs-lookup"><span data-stu-id="719cf-916">The support for your operating system has expired.</span></span> <span data-ttu-id="719cf-917">Antivirus de Microsoft Defender ya no es compatible con el sistema operativo, ha dejado de funcionar y no protege contra amenazas de malware.</span><span class="sxs-lookup"><span data-stu-id="719cf-917">Microsoft Defender Antivirus is no longer supported on your operating system, has stopped functioning, and is not protecting against malware threats.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="719cf-918">Identificador de evento: 3002</span><span class="sxs-lookup"><span data-stu-id="719cf-918">Event ID: 3002</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="719cf-919">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="719cf-919">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="719cf-920">
<b>MALWAREPROTECTION_RTP_FEATURE_FAILURE </b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-920">
<b>MALWAREPROTECTION_RTP_FEATURE_FAILURE </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-921">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="719cf-921">Message:</span></span>
</td>
<td ><span data-ttu-id="719cf-922">
<b>La protección en tiempo real encontró un error y produjo un error.</b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-922">
<b>Real-time protection encountered an error and failed.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-923">Descripción:</span><span class="sxs-lookup"><span data-stu-id="719cf-923">Description:</span></span>
</td>
<td >
<span data-ttu-id="719cf-924">La característica de protección Real-Time Antivirus de Microsoft Defender ha encontrado un error y ha producido un error.</span><span class="sxs-lookup"><span data-stu-id="719cf-924">Microsoft Defender Antivirus Real-Time Protection feature has encountered an error and failed.</span></span>
<dl><span data-ttu-id="719cf-925">
<dt>Característica: &lt; Característica , por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="719cf-925">
<dt>Feature: &lt;Feature&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="719cf-926">En Access</span><span class="sxs-lookup"><span data-stu-id="719cf-926">On Access</span></span></li>
<li><span data-ttu-id="719cf-927">Descargas de Internet Explorer y datos adjuntos de Microsoft Outlook Express</span><span class="sxs-lookup"><span data-stu-id="719cf-927">Internet Explorer downloads and Microsoft Outlook Express attachments</span></span></li>
<li><span data-ttu-id="719cf-928">Supervisión del comportamiento</span><span class="sxs-lookup"><span data-stu-id="719cf-928">Behavior monitoring</span></span></li>
<li><span data-ttu-id="719cf-929">Sistema de inspección de red</span><span class="sxs-lookup"><span data-stu-id="719cf-929">Network Inspection System</span></span></li>
</ul><span data-ttu-id="719cf-930">
</dt>
<dt>Código de error: &lt; Código de error &gt; Código de resultado asociado con el estado de amenaza. Valores HRESULT estándar.</dt> 
<dt>Descripción del error: &lt; Descripción del error &gt; Descripción del error.</dt> Motivo: el motivo por el que la protección en tiempo real de Antivirus de 
<dt>Microsoft Defender ha reiniciado una característica.</dt>
</span><span class="sxs-lookup"><span data-stu-id="719cf-930">
</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Reason: The reason Microsoft Defender Antivirus real-time protection has restarted a feature.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-931">Acción del usuario:</span><span class="sxs-lookup"><span data-stu-id="719cf-931">User action:</span></span>
</td>
<td >
<span data-ttu-id="719cf-932">Debe reiniciar el sistema y, a continuación, ejecutar un examen completo porque&#39;es posible que el sistema no se protegió durante algún tiempo.</span><span class="sxs-lookup"><span data-stu-id="719cf-932">You should restart the system then run a full scan because it&#39;s possible the system was not protected for some time.</span></span>
<span data-ttu-id="719cf-933">El cliente antivirus de Microsoft Defender&#39;la característica de protección en tiempo real encontró un error porque uno de los servicios no se pudo iniciar.</span><span class="sxs-lookup"><span data-stu-id="719cf-933">The Microsoft Defender Antivirus client&#39;s real-time protection feature encountered an error because one of the services failed to start.</span></span> <span data-ttu-id="719cf-934">Si le sigue un identificador de evento 3007, el error fue temporal y el cliente antimalware se recuperó del error.</span><span class="sxs-lookup"><span data-stu-id="719cf-934">If it is followed by a 3007 event ID, the failure was temporary and the antimalware client recovered from the failure.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="719cf-935">Identificador de evento: 3007</span><span class="sxs-lookup"><span data-stu-id="719cf-935">Event ID: 3007</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="719cf-936">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="719cf-936">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="719cf-937">
<b>MALWAREPROTECTION_RTP_FEATURE_RECOVERED</b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-937">
<b>MALWAREPROTECTION_RTP_FEATURE_RECOVERED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-938">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="719cf-938">Message:</span></span>
</td>
<td ><span data-ttu-id="719cf-939">
<b>Protección en tiempo real recuperada de un error. Se recomienda ejecutar un examen completo del sistema cuando vea este error. </b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-939">
<b>Real-time protection recovered from a failure. We recommend running a full system scan when you see this error. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-940">Descripción:</span><span class="sxs-lookup"><span data-stu-id="719cf-940">Description:</span></span>
</td>
<td >
<span data-ttu-id="719cf-941">Protección en tiempo real de Antivirus de Microsoft Defender ha reiniciado una característica.</span><span class="sxs-lookup"><span data-stu-id="719cf-941">Microsoft Defender Antivirus Real-time Protection has restarted a feature.</span></span> <span data-ttu-id="719cf-942">Se recomienda ejecutar un examen completo del sistema para detectar los elementos que se hayan perdido mientras este agente estaba abajo.</span><span class="sxs-lookup"><span data-stu-id="719cf-942">It is recommended that you run a full system scan to detect any items that may have been missed while this agent was down.</span></span>
<dl><span data-ttu-id="719cf-943">
<dt>Característica: &lt; Característica , por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="719cf-943">
<dt>Feature: &lt;Feature&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="719cf-944">En Access</span><span class="sxs-lookup"><span data-stu-id="719cf-944">On Access</span></span></li>
<li><span data-ttu-id="719cf-945">Descargas de IE y datos adjuntos de Outlook Express</span><span class="sxs-lookup"><span data-stu-id="719cf-945">IE downloads and Outlook Express attachments</span></span></li>
<li><span data-ttu-id="719cf-946">Supervisión del comportamiento</span><span class="sxs-lookup"><span data-stu-id="719cf-946">Behavior monitoring</span></span></li>
<li><span data-ttu-id="719cf-947">Sistema de inspección de red</span><span class="sxs-lookup"><span data-stu-id="719cf-947">Network Inspection System</span></span></li>
</ul><span data-ttu-id="719cf-948">
</dt>
<dt>Motivo: el motivo por el que la protección en tiempo real de Antivirus de Microsoft Defender ha reiniciado una característica.</dt>
</span><span class="sxs-lookup"><span data-stu-id="719cf-948">
</dt>
<dt>Reason: The reason Microsoft Defender Antivirus real-time protection has restarted a feature.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-949">Acción del usuario:</span><span class="sxs-lookup"><span data-stu-id="719cf-949">User action:</span></span>
</td>
<td >
<span data-ttu-id="719cf-950">Se ha reiniciado la característica de protección en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="719cf-950">The real-time protection feature has restarted.</span></span> <span data-ttu-id="719cf-951">Si este evento se produce de nuevo, póngase en contacto <a href="https://go.microsoft.com/fwlink/?LinkId=215491">con el Soporte técnico de Microsoft</a>.</span><span class="sxs-lookup"><span data-stu-id="719cf-951">If this event happens again, contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="719cf-952">Identificador de evento: 5000</span><span class="sxs-lookup"><span data-stu-id="719cf-952">Event ID: 5000</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="719cf-953">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="719cf-953">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="719cf-954">
<b>MALWAREPROTECTION_RTP_ENABLED </b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-954">
<b>MALWAREPROTECTION_RTP_ENABLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-955">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="719cf-955">Message:</span></span>
</td>
<td ><span data-ttu-id="719cf-956">
<b>La protección en tiempo real está habilitada. </b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-956">
<b>Real-time protection is enabled. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-957">Descripción:</span><span class="sxs-lookup"><span data-stu-id="719cf-957">Description:</span></span>
</td>
<td >
<span data-ttu-id="719cf-958">Se ha habilitado el examen de protección en tiempo real de Antivirus de Microsoft Defender en busca de malware y otro software potencialmente no deseado.</span><span class="sxs-lookup"><span data-stu-id="719cf-958">Microsoft Defender Antivirus real-time protection scanning for malware and other potentially unwanted software was enabled.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="719cf-959">Identificador de evento: 5001</span><span class="sxs-lookup"><span data-stu-id="719cf-959">Event ID: 5001</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="719cf-960">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="719cf-960">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="719cf-961">
<b>MALWAREPROTECTION_RTP_DISABLED</b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-961">
<b>MALWAREPROTECTION_RTP_DISABLED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-962">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="719cf-962">Message:</span></span>
</td>
<td ><span data-ttu-id="719cf-963">
<b>La protección en tiempo real está deshabilitada. </b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-963">
<b>Real-time protection is disabled. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-964">Descripción:</span><span class="sxs-lookup"><span data-stu-id="719cf-964">Description:</span></span>
</td>
<td >
<span data-ttu-id="719cf-965">Se deshabilitó el examen de protección en tiempo real de Antivirus de Microsoft Defender en busca de malware y otro software potencialmente no deseado.</span><span class="sxs-lookup"><span data-stu-id="719cf-965">Microsoft Defender Antivirus real-time protection scanning for malware and other potentially unwanted software was disabled.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="719cf-966">Identificador de evento: 5004</span><span class="sxs-lookup"><span data-stu-id="719cf-966">Event ID: 5004</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="719cf-967">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="719cf-967">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="719cf-968">
<b>MALWAREPROTECTION_RTP_FEATURE_CONFIGURED </b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-968">
<b>MALWAREPROTECTION_RTP_FEATURE_CONFIGURED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-969">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="719cf-969">Message:</span></span>
</td>
<td ><span data-ttu-id="719cf-970">
<b>La configuración de protección en tiempo real cambió. </b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-970">
<b>The real-time protection configuration changed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-971">Descripción:</span><span class="sxs-lookup"><span data-stu-id="719cf-971">Description:</span></span>
</td>
<td >
<span data-ttu-id="719cf-972">La configuración de la característica de protección en tiempo real de Antivirus de Microsoft Defender ha cambiado.</span><span class="sxs-lookup"><span data-stu-id="719cf-972">Microsoft Defender Antivirus real-time protection feature configuration has changed.</span></span>
<dl><span data-ttu-id="719cf-973">
<dt>Característica: &lt; Característica , por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="719cf-973">
<dt>Feature: &lt;Feature&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="719cf-974">En Access</span><span class="sxs-lookup"><span data-stu-id="719cf-974">On Access</span></span></li>
<li><span data-ttu-id="719cf-975">Descargas de IE y datos adjuntos de Outlook Express</span><span class="sxs-lookup"><span data-stu-id="719cf-975">IE downloads and Outlook Express attachments</span></span></li>
<li><span data-ttu-id="719cf-976">Supervisión del comportamiento</span><span class="sxs-lookup"><span data-stu-id="719cf-976">Behavior monitoring</span></span></li>
<li><span data-ttu-id="719cf-977">Sistema de inspección de red</span><span class="sxs-lookup"><span data-stu-id="719cf-977">Network Inspection System</span></span></li>
</ul><span data-ttu-id="719cf-978">
</dt>
<dt>Configuración: </dt>
</span><span class="sxs-lookup"><span data-stu-id="719cf-978">
</dt>
<dt>Configuration: </dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="719cf-979">Identificador de evento: 5007</span><span class="sxs-lookup"><span data-stu-id="719cf-979">Event ID: 5007</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="719cf-980">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="719cf-980">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="719cf-981">
<b>MALWAREPROTECTION_CONFIG_CHANGED </b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-981">
<b>MALWAREPROTECTION_CONFIG_CHANGED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-982">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="719cf-982">Message:</span></span>
</td>
<td ><span data-ttu-id="719cf-983">
<b>Se cambió la configuración de la plataforma antimalware.</b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-983">
<b>The antimalware platform configuration changed.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-984">Descripción:</span><span class="sxs-lookup"><span data-stu-id="719cf-984">Description:</span></span>
</td>
<td >
<span data-ttu-id="719cf-985">La configuración de Antivirus de Microsoft Defender ha cambiado.</span><span class="sxs-lookup"><span data-stu-id="719cf-985">Microsoft Defender Antivirus configuration has changed.</span></span> <span data-ttu-id="719cf-986">Si se trata de un evento inesperado, debe revisar la configuración, ya que puede ser el resultado de malware.</span><span class="sxs-lookup"><span data-stu-id="719cf-986">If this is an unexpected event, you should review the settings as this may be the result of malware.</span></span>
<dl><span data-ttu-id="719cf-987">
<dt>Valor antiguo: &lt; Número de valor antiguo &gt; Valor de configuración del antivirus anterior.</dt> 
<dt>Nuevo valor: &lt; Nuevo número de valor &gt; Nuevo valor de configuración antivirus.</dt>
</span><span class="sxs-lookup"><span data-stu-id="719cf-987">
<dt>Old value: &lt;Old value number&gt; Old antivirus configuration value.</dt>
<dt>New value: &lt;New value number&gt; New antivirus configuration value.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="719cf-988">Identificador de evento: 5008</span><span class="sxs-lookup"><span data-stu-id="719cf-988">Event ID: 5008</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="719cf-989">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="719cf-989">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="719cf-990">
<b>MALWAREPROTECTION_ENGINE_FAILURE</b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-990">
<b>MALWAREPROTECTION_ENGINE_FAILURE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-991">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="719cf-991">Message:</span></span>
</td>
<td ><span data-ttu-id="719cf-992">
<b>El motor de antimalware encontró un error y produjo un error.</b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-992">
<b>The antimalware engine encountered an error and failed.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-993">Descripción:</span><span class="sxs-lookup"><span data-stu-id="719cf-993">Description:</span></span>
</td>
<td >
<span data-ttu-id="719cf-994">El motor antivirus de Microsoft Defender ha finalizado debido a un error inesperado.</span><span class="sxs-lookup"><span data-stu-id="719cf-994">Microsoft Defender Antivirus engine has been terminated due to an unexpected error.</span></span>
<dl><span data-ttu-id="719cf-995">
<dt>Tipo de error: &lt; Tipo de &gt; error , por ejemplo: Bloquear o bloquear código</dt>de
<dt>excepción: &lt; Código de &gt; error</dt>
<dt>Recurso: &lt; recurso &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="719cf-995">
<dt>Failure Type: &lt;Failure type&gt;, for example: Crash or Hang</dt>
<dt>Exception Code: &lt;Error code&gt;</dt>
<dt>Resource: &lt;Resource&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-996">Acción del usuario:</span><span class="sxs-lookup"><span data-stu-id="719cf-996">User action:</span></span>
</td>
<td >
<span data-ttu-id="719cf-997">Para solucionar este evento:</span><span class="sxs-lookup"><span data-stu-id="719cf-997">To troubleshoot this event:</span></span><ol>
<li><span data-ttu-id="719cf-998">Intente reiniciar el servicio.</span><span class="sxs-lookup"><span data-stu-id="719cf-998">Try to restart the service.</span></span><ul>
<li><span data-ttu-id="719cf-999">Para antimalware, antivirus y spyware, en un símbolo del sistema con privilegios elevados, escriba <b>net stop msmpsvc</b>y, a continuación, escriba <b>net start msmpsvc</b> para reiniciar el motor de antimalware.</span><span class="sxs-lookup"><span data-stu-id="719cf-999">For antimalware, antivirus and spyware, at an elevated command prompt, type <b>net stop msmpsvc</b>, and then type <b>net start msmpsvc</b> to restart the antimalware engine.</span></span></li>
<li><span data-ttu-id="719cf-1000">Para el sistema <i>de</i>inspección de red , en un símbolo del sistema con privilegios elevados, escriba <b>net start nissrv</b>y, a continuación, escriba <b>net start nissrv</b> para reiniciar el motor del sistema de inspección de red mediante el archivo NiSSRV.exe. <i></i></span><span class="sxs-lookup"><span data-stu-id="719cf-1000">For the <i>Network Inspection System</i>, at an elevated command prompt, type <b>net start nissrv</b>, and then type <b>net start nissrv</b> to restart the <i>Network Inspection System</i> engine by using the NiSSRV.exe file.</span></span>
</li>
</ul>
</li>
<li><span data-ttu-id="719cf-1001">Si se produce un error de la misma manera, busque el código de <b></b> error accediendo al Sitio de soporte técnico de <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft</a> y especificando el número de error en el cuadro Búsqueda y póngase en contacto con el Soporte técnico <a href="https://go.microsoft.com/fwlink/?LinkId=215491">de Microsoft</a>.</span><span class="sxs-lookup"><span data-stu-id="719cf-1001">If it fails in the same way, look up the error code by accessing the <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft Support Site</a>  and entering the error number in the <b>Search</b> box, and contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span></li>
</ol>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-1002">Acción del usuario:</span><span class="sxs-lookup"><span data-stu-id="719cf-1002">User action:</span></span>
</td>
<td >
<span data-ttu-id="719cf-1003">El motor de cliente de Antivirus de Microsoft Defender se detuvo debido a un error inesperado.</span><span class="sxs-lookup"><span data-stu-id="719cf-1003">The Microsoft Defender Antivirus client engine stopped due to an unexpected error.</span></span>
<span data-ttu-id="719cf-1004">Para solucionar este evento:</span><span class="sxs-lookup"><span data-stu-id="719cf-1004">To troubleshoot this event:</span></span>
<ol>
<li><span data-ttu-id="719cf-1005">Vuelva a ejecutar el examen.</span><span class="sxs-lookup"><span data-stu-id="719cf-1005">Run the scan again.</span></span></li>
<li><span data-ttu-id="719cf-1006">Si se produce un error de la misma manera, vaya <b></b> al sitio de soporte técnico de <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft</a>, escriba el número de error en el cuadro Buscar para buscar el código de error.</span><span class="sxs-lookup"><span data-stu-id="719cf-1006">If it fails in the same way, go to the <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft Support site</a>, enter the error number in the <b>Search</b> box to look for the error code.</span></span></li>
<li><span data-ttu-id="719cf-1007">Contactar al <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Soporte técnico de Microsoft</a>.</span><span class="sxs-lookup"><span data-stu-id="719cf-1007">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="719cf-1008">Identificador de evento: 5009</span><span class="sxs-lookup"><span data-stu-id="719cf-1008">Event ID: 5009</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="719cf-1009">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="719cf-1009">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="719cf-1010">
<b>MALWAREPROTECTION_ANTISPYWARE_ENABLED </b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-1010">
<b>MALWAREPROTECTION_ANTISPYWARE_ENABLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-1011">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="719cf-1011">Message:</span></span>
</td>
<td ><span data-ttu-id="719cf-1012">
<b>El examen de malware y otro software potencialmente no deseado está habilitado. </b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-1012">
<b>Scanning for malware and other potentially unwanted software is enabled. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-1013">Descripción:</span><span class="sxs-lookup"><span data-stu-id="719cf-1013">Description:</span></span>
</td>
<td >
<span data-ttu-id="719cf-1014">Se ha habilitado el examen del antivirus de Microsoft Defender en busca de malware y otro software potencialmente no deseado.</span><span class="sxs-lookup"><span data-stu-id="719cf-1014">Microsoft Defender Antivirus scanning for malware and other potentially unwanted software has been enabled.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="719cf-1015">Identificador de evento: 5010</span><span class="sxs-lookup"><span data-stu-id="719cf-1015">Event ID: 5010</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="719cf-1016">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="719cf-1016">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="719cf-1017">
<b>MALWAREPROTECTION_ANTISPYWARE_DISABLED </b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-1017">
<b>MALWAREPROTECTION_ANTISPYWARE_DISABLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-1018">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="719cf-1018">Message:</span></span>
</td>
<td ><span data-ttu-id="719cf-1019">
<b>El examen de malware y otro software potencialmente no deseado está deshabilitado.</b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-1019">
<b>Scanning for malware and other potentially unwanted software is disabled.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-1020">Descripción:</span><span class="sxs-lookup"><span data-stu-id="719cf-1020">Description:</span></span>
</td>
<td >
<span data-ttu-id="719cf-1021">El examen del antivirus de Microsoft Defender en busca de malware y otro software potencialmente no deseado está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="719cf-1021">Microsoft Defender Antivirus scanning for malware and other potentially unwanted software is disabled.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="719cf-1022">Identificador de evento: 5011</span><span class="sxs-lookup"><span data-stu-id="719cf-1022">Event ID: 5011</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="719cf-1023">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="719cf-1023">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="719cf-1024">
<b>MALWAREPROTECTION_ANTIVIRUS_ENABLED</b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-1024">
<b>MALWAREPROTECTION_ANTIVIRUS_ENABLED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-1025">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="719cf-1025">Message:</span></span>
</td>
<td ><span data-ttu-id="719cf-1026">
<b>El examen de virus está habilitado.</b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-1026">
<b>Scanning for viruses is enabled.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-1027">Descripción:</span><span class="sxs-lookup"><span data-stu-id="719cf-1027">Description:</span></span>
</td>
<td >
<span data-ttu-id="719cf-1028">Se ha habilitado el examen antivirus de Microsoft Defender en busca de virus.</span><span class="sxs-lookup"><span data-stu-id="719cf-1028">Microsoft Defender Antivirus scanning for viruses has been enabled.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="719cf-1029">Identificador de evento: 5012</span><span class="sxs-lookup"><span data-stu-id="719cf-1029">Event ID: 5012</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="719cf-1030">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="719cf-1030">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="719cf-1031">
<b>MALWAREPROTECTION_ANTIVIRUS_DISABLED </b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-1031">
<b>MALWAREPROTECTION_ANTIVIRUS_DISABLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-1032">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="719cf-1032">Message:</span></span>
</td>
<td ><span data-ttu-id="719cf-1033">
<b>El examen de virus está deshabilitado. </b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-1033">
<b>Scanning for viruses is disabled. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-1034">Descripción:</span><span class="sxs-lookup"><span data-stu-id="719cf-1034">Description:</span></span>
</td>
<td >
<span data-ttu-id="719cf-1035">El examen del Antivirus de Microsoft Defender en busca de virus está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="719cf-1035">Microsoft Defender Antivirus scanning for viruses is disabled.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="719cf-1036">Identificador de evento: 5100</span><span class="sxs-lookup"><span data-stu-id="719cf-1036">Event ID: 5100</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="719cf-1037">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="719cf-1037">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="719cf-1038">
<b>MALWAREPROTECTION_EXPIRATION_WARNING_STATE </b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-1038">
<b>MALWAREPROTECTION_EXPIRATION_WARNING_STATE </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-1039">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="719cf-1039">Message:</span></span>
</td>
<td ><span data-ttu-id="719cf-1040">
<b>La plataforma antimalware expirará pronto. </b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-1040">
<b>The antimalware platform will expire soon. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-1041">Descripción:</span><span class="sxs-lookup"><span data-stu-id="719cf-1041">Description:</span></span>
</td>
<td >
<span data-ttu-id="719cf-1042">Antivirus de Microsoft Defender ha entrado en un período de gracia y expirará pronto.</span><span class="sxs-lookup"><span data-stu-id="719cf-1042">Microsoft Defender Antivirus has entered a grace period and will soon expire.</span></span> <span data-ttu-id="719cf-1043">Después de expirar, este programa deshabilitará la protección contra virus, spyware y otro software potencialmente no deseado.</span><span class="sxs-lookup"><span data-stu-id="719cf-1043">After expiration, this program will disable protection against viruses, spyware, and other potentially unwanted software.</span></span>
<dl><span data-ttu-id="719cf-1044">
<dt>Motivo de expiración: el motivo por el que el Antivirus de Microsoft Defender expirará.</dt> 
<dt>Fecha de expiración: la fecha en que expirará Antivirus de Microsoft Defender.</dt>
</span><span class="sxs-lookup"><span data-stu-id="719cf-1044">
<dt>Expiration Reason: The reason Microsoft Defender Antivirus will expire.</dt>
<dt>Expiration Date: The date Microsoft Defender Antivirus will expire.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="719cf-1045">Identificador de evento: 5101</span><span class="sxs-lookup"><span data-stu-id="719cf-1045">Event ID: 5101</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="719cf-1046">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="719cf-1046">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="719cf-1047">
<b>MALWAREPROTECTION_DISABLED_EXPIRED_STATE </b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-1047">
<b>MALWAREPROTECTION_DISABLED_EXPIRED_STATE </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-1048">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="719cf-1048">Message:</span></span>
</td>
<td ><span data-ttu-id="719cf-1049">
<b>La plataforma antimalware ha expirado. </b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-1049">
<b>The antimalware platform is expired. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-1050">Descripción:</span><span class="sxs-lookup"><span data-stu-id="719cf-1050">Description:</span></span>
</td>
<td >
<span data-ttu-id="719cf-1051">El período de gracia de Antivirus de Microsoft Defender ha expirado.</span><span class="sxs-lookup"><span data-stu-id="719cf-1051">Microsoft Defender Antivirus grace period has expired.</span></span> <span data-ttu-id="719cf-1052">La protección contra virus, spyware y otro software potencialmente no deseado está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="719cf-1052">Protection against viruses, spyware, and other potentially unwanted software is disabled.</span></span>
<dl><span data-ttu-id="719cf-1053">
<dt>Motivo de expiración:</dt>
<dt>Fecha de expiración: </dt>Código de error: Código de error Código de resultado asociado con el estado de la 
<dt> &lt; &gt; amenaza. Valores HRESULT estándar.</dt> 
<dt>Descripción del error: &lt; Descripción del error &gt; Descripción del error.</dt>
</span><span class="sxs-lookup"><span data-stu-id="719cf-1053">
<dt>Expiration Reason:</dt>
<dt>Expiration Date: </dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr><span data-ttu-id="719cf-1054">
</table>

<a id="error-codes"></a>
## Códigos de error de cliente de Antivirus de Microsoft Defender Si Antivirus de Microsoft Defender experimenta algún problema, normalmente le dará un código de error para ayudarle a solucionar el problema.</span><span class="sxs-lookup"><span data-stu-id="719cf-1054">
</table>

<a id="error-codes"></a>
## Microsoft Defender Antivirus client error codes If Microsoft Defender Antivirus experiences any issues it will usually give you an error code to help you troubleshoot the issue.</span></span> <span data-ttu-id="719cf-1055">En la mayoría de los casos, un error significa que hubo un problema al instalar una actualización.</span><span class="sxs-lookup"><span data-stu-id="719cf-1055">Most often an error means there was a problem installing an update.</span></span>
<span data-ttu-id="719cf-1056">En esta sección se proporciona la siguiente información acerca de los errores de cliente de Antivirus de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="719cf-1056">This section provides the following information about Microsoft Defender Antivirus client errors.</span></span>
<span data-ttu-id="719cf-1057">-   El código de error -   El posible motivo del error Consejo sobre qué hacer -   ahora</span><span class="sxs-lookup"><span data-stu-id="719cf-1057">-   The error code -   The possible reason for the error -   Advice on what to do now</span></span>

<span data-ttu-id="719cf-1058">Use la información de estas tablas para solucionar problemas de códigos de error de Antivirus de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="719cf-1058">Use the information in these tables to help troubleshoot Microsoft Defender Antivirus error codes.</span></span>


<table> 
<tr>
<th colspan="2"><span data-ttu-id="719cf-1059">Código de error: 0x80508007</span><span class="sxs-lookup"><span data-stu-id="719cf-1059">Error code: 0x80508007</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="719cf-1060">Message</span><span class="sxs-lookup"><span data-stu-id="719cf-1060">Message</span></span></td>
<td><span data-ttu-id="719cf-1061">
<b>ERR_MP_NO_MEMORY </b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-1061">
<b>ERR_MP_NO_MEMORY </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-1062">Posible motivo</span><span class="sxs-lookup"><span data-stu-id="719cf-1062">Possible reason</span></span>
</td>
<td>
<span data-ttu-id="719cf-1063">Este error indica que es posible que se haya quedo sin memoria.</span><span class="sxs-lookup"><span data-stu-id="719cf-1063">This error indicates that you might have run out of memory.</span></span> 
</td>
</tr>
<tr>
<td><span data-ttu-id="719cf-1064">Solución</span><span class="sxs-lookup"><span data-stu-id="719cf-1064">Resolution</span></span></td>
<td>
<ol>
<li><span data-ttu-id="719cf-1065">Comprueba la memoria disponible en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="719cf-1065">Check the available memory on your device.</span></span></li>
<li><span data-ttu-id="719cf-1066">Cierra todas las aplicaciones no usadas que se estén ejecutando para liberar memoria en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="719cf-1066">Close any unused applications that are running to free up memory on your device.</span></span></li>
<li><span data-ttu-id="719cf-1067">Reinicie el dispositivo y vuelva a ejecutar el examen.</span><span class="sxs-lookup"><span data-stu-id="719cf-1067">Restart the device and run the scan again.</span></span> 
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="719cf-1068">Código de error: 0x8050800C</span><span class="sxs-lookup"><span data-stu-id="719cf-1068">Error code: 0x8050800C</span></span></th>
</tr><tr><td><span data-ttu-id="719cf-1069">Message</span><span class="sxs-lookup"><span data-stu-id="719cf-1069">Message</span></span></td>
<td><span data-ttu-id="719cf-1070"><b>ERR_MP_BAD_INPUT_DATA</b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-1070"><b>ERR_MP_BAD_INPUT_DATA</b>
</span></span></td></tr><tr><td><span data-ttu-id="719cf-1071">Posible motivo</span><span class="sxs-lookup"><span data-stu-id="719cf-1071">Possible reason</span></span></td>
<td>
<span data-ttu-id="719cf-1072">Este error indica que puede haber un problema con el producto de seguridad.</span><span class="sxs-lookup"><span data-stu-id="719cf-1072">This error indicates that there might be a problem with your security product.</span></span>
</td>
</tr><tr><td><span data-ttu-id="719cf-1073">Solución</span><span class="sxs-lookup"><span data-stu-id="719cf-1073">Resolution</span></span></td><td>
<ol>
<li><span data-ttu-id="719cf-1074">Actualice las definiciones.</span><span class="sxs-lookup"><span data-stu-id="719cf-1074">Update the definitions.</span></span> <span data-ttu-id="719cf-1075">Cualquiera de las dos:</span><span class="sxs-lookup"><span data-stu-id="719cf-1075">Either:</span></span><ol>
<li><span data-ttu-id="719cf-1076">Haga clic en <b>el botón Actualizar definiciones</b> de la <b>pestaña</b> Actualizar del Antivirus de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="719cf-1076">Click the <b>Update definitions</b> button on the <b>Update</b> tab in Microsoft Defender Antivirus.</span></span> <img src="images/defender-updatedefs2.png" alt="Update definitions in Microsoft Defender Antivirus"/><span data-ttu-id="719cf-1077">O bien</span><span class="sxs-lookup"><span data-stu-id="719cf-1077">Or,</span></span>
</li>
<li><span data-ttu-id="719cf-1078">Descargue las definiciones más recientes del sitio <a href="https://aka.ms/wdsi">de Inteligencia de seguridad de Microsoft</a>.</span><span class="sxs-lookup"><span data-stu-id="719cf-1078">Download the latest definitions from the <a href="https://aka.ms/wdsi">Microsoft Security Intelligence site</a>.</span></span>
<span data-ttu-id="719cf-1079">Nota: El tamaño del archivo de definiciones descargado del sitio puede superar los 60 MB y no debe usarse como solución a largo plazo para actualizar definiciones.</span><span class="sxs-lookup"><span data-stu-id="719cf-1079">Note: The size of the definitions file downloaded from the site can exceed 60 MB and should not be used as a long-term solution for updating definitions.</span></span>
</li>
</ol>
</li>
<li><span data-ttu-id="719cf-1080">Ejecute un examen completo.</span><span class="sxs-lookup"><span data-stu-id="719cf-1080">Run a full scan.</span></span>
</li>
<li><span data-ttu-id="719cf-1081">Reinicie el dispositivo e inténtelo de nuevo.</span><span class="sxs-lookup"><span data-stu-id="719cf-1081">Restart the device and try again.</span></span></li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="719cf-1082">Código de error: 0x80508020</span><span class="sxs-lookup"><span data-stu-id="719cf-1082">Error code: 0x80508020</span></span></th>
</tr><tr><td><span data-ttu-id="719cf-1083">Message</span><span class="sxs-lookup"><span data-stu-id="719cf-1083">Message</span></span></td>
<td><span data-ttu-id="719cf-1084"><b>ERR_MP_BAD_CONFIGURATION </b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-1084"><b>ERR_MP_BAD_CONFIGURATION </b>
</span></span></td></tr><tr><td><span data-ttu-id="719cf-1085">Posible motivo</span><span class="sxs-lookup"><span data-stu-id="719cf-1085">Possible reason</span></span></td>
<td>
<span data-ttu-id="719cf-1086">Este error indica que puede haber un error de configuración del motor; normalmente, esto está relacionado con datos de entrada que no permiten que el motor funcione correctamente.</span><span class="sxs-lookup"><span data-stu-id="719cf-1086">This error indicates that there might be an engine configuration error; commonly, this is related to input data that does not allow the engine to function properly.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="719cf-1087">Código de error: 0x805080211</span><span class="sxs-lookup"><span data-stu-id="719cf-1087">Error code: 0x805080211</span></span>
</th>
</tr><tr><td><span data-ttu-id="719cf-1088">Message</span><span class="sxs-lookup"><span data-stu-id="719cf-1088">Message</span></span></td>
<td><span data-ttu-id="719cf-1089"><b>ERR_MP_QUARANTINE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-1089"><b>ERR_MP_QUARANTINE_FAILED </b>
</span></span></td></tr><tr><td><span data-ttu-id="719cf-1090">Posible motivo</span><span class="sxs-lookup"><span data-stu-id="719cf-1090">Possible reason</span></span></td>
<td>
<span data-ttu-id="719cf-1091">Este error indica que antivirus de Microsoft Defender no pudo poner en cuarentena una amenaza.</span><span class="sxs-lookup"><span data-stu-id="719cf-1091">This error indicates that Microsoft Defender Antivirus failed to quarantine a threat.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="719cf-1092">Código de error: 0x80508022</span><span class="sxs-lookup"><span data-stu-id="719cf-1092">Error code: 0x80508022</span></span>
</th>
</tr><tr><td><span data-ttu-id="719cf-1093">Message</span><span class="sxs-lookup"><span data-stu-id="719cf-1093">Message</span></span></td>
<td><span data-ttu-id="719cf-1094"><b>ERR_MP_REBOOT_REQUIRED </b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-1094"><b>ERR_MP_REBOOT_REQUIRED </b>
</span></span></td></tr><tr><td><span data-ttu-id="719cf-1095">Posible motivo</span><span class="sxs-lookup"><span data-stu-id="719cf-1095">Possible reason</span></span></td>
<td>
<span data-ttu-id="719cf-1096">Este error indica que se requiere un reinicio para completar la eliminación de amenazas.</span><span class="sxs-lookup"><span data-stu-id="719cf-1096">This error indicates that a reboot is required to complete threat removal.</span></span> 
</td>
</tr>
<tr>
<th colspan="2">
<span data-ttu-id="719cf-1097">0x80508023</span><span class="sxs-lookup"><span data-stu-id="719cf-1097">0x80508023</span></span>
</th>
</tr><tr><td><span data-ttu-id="719cf-1098">Message</span><span class="sxs-lookup"><span data-stu-id="719cf-1098">Message</span></span></td>
<td><span data-ttu-id="719cf-1099"><b>ERR_MP_THREAT_NOT_FOUND </b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-1099"><b>ERR_MP_THREAT_NOT_FOUND </b>
</span></span></td></tr><tr><td><span data-ttu-id="719cf-1100">Posible motivo</span><span class="sxs-lookup"><span data-stu-id="719cf-1100">Possible reason</span></span></td>
<td>
<span data-ttu-id="719cf-1101">Este error indica que es posible que la amenaza ya no esté presente en los medios o que el malware pueda impedir que se pueda examinar el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="719cf-1101">This error indicates that the threat might no longer be present on the media, or malware might be stopping you from scanning your device.</span></span> 
</tr><tr><td><span data-ttu-id="719cf-1102">Solución</span><span class="sxs-lookup"><span data-stu-id="719cf-1102">Resolution</span></span>
</td>
<td>
<span data-ttu-id="719cf-1103">Ejecute el <a href="https://www.microsoft.com/security/scanner/default.aspx">Escáner de seguridad de Microsoft</a> y, a continuación, actualice el software de seguridad e inténtelo de nuevo.</span><span class="sxs-lookup"><span data-stu-id="719cf-1103">Run the <a href="https://www.microsoft.com/security/scanner/default.aspx">Microsoft Safety Scanner</a> then update your security software and try again.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="719cf-1104">Código de error: 0x80508024</span><span class="sxs-lookup"><span data-stu-id="719cf-1104">Error code: 0x80508024</span></span> </th></tr>
<tr>
<td><span data-ttu-id="719cf-1105">Message</span><span class="sxs-lookup"><span data-stu-id="719cf-1105">Message</span></span></td>
<td><span data-ttu-id="719cf-1106"><b>ERR_MP_FULL_SCAN_REQUIRED </b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-1106"><b>ERR_MP_FULL_SCAN_REQUIRED </b>
</span></span></td></tr><tr><td><span data-ttu-id="719cf-1107">Posible motivo</span><span class="sxs-lookup"><span data-stu-id="719cf-1107">Possible reason</span></span></td>
<td>
<span data-ttu-id="719cf-1108">Este error indica que puede ser necesario realizar un examen completo del sistema.</span><span class="sxs-lookup"><span data-stu-id="719cf-1108">This error indicates that a full system scan might be required.</span></span> 
</td></tr>
<tr>
<td><span data-ttu-id="719cf-1109">Solución</span><span class="sxs-lookup"><span data-stu-id="719cf-1109">Resolution</span></span></td><td>
<span data-ttu-id="719cf-1110">Ejecute un examen completo del sistema.</span><span class="sxs-lookup"><span data-stu-id="719cf-1110">Run a full system scan.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="719cf-1111">Código de error: 0x80508025</span><span class="sxs-lookup"><span data-stu-id="719cf-1111">Error code: 0x80508025</span></span>
</th>
</tr><tr><td><span data-ttu-id="719cf-1112">Message</span><span class="sxs-lookup"><span data-stu-id="719cf-1112">Message</span></span></td>
<td><span data-ttu-id="719cf-1113"><b>ERR_MP_MANUAL_STEPS_REQUIRED </b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-1113"><b>ERR_MP_MANUAL_STEPS_REQUIRED </b>
</span></span></td></tr><tr><td><span data-ttu-id="719cf-1114">Posible motivo</span><span class="sxs-lookup"><span data-stu-id="719cf-1114">Possible reason</span></span></td>
<td>
<span data-ttu-id="719cf-1115">Este error indica que se requieren pasos manuales para completar la eliminación de amenazas.</span><span class="sxs-lookup"><span data-stu-id="719cf-1115">This error indicates that manual steps are required to complete threat removal.</span></span> 
</td></tr><tr><td><span data-ttu-id="719cf-1116">Solución</span><span class="sxs-lookup"><span data-stu-id="719cf-1116">Resolution</span></span></td><td>
<span data-ttu-id="719cf-1117">Siga los pasos de corrección manuales descritos en la Enciclopedia de Protección contra malware <a href="https://www.microsoft.com/security/portal/threat/Threats.aspx">de Microsoft</a>.</span><span class="sxs-lookup"><span data-stu-id="719cf-1117">Follow the manual remediation steps outlined in the <a href="https://www.microsoft.com/security/portal/threat/Threats.aspx">Microsoft Malware Protection Encyclopedia</a>.</span></span> <span data-ttu-id="719cf-1118">Puede encontrar un vínculo específico de la amenaza en el historial de eventos.</span><span class="sxs-lookup"><span data-stu-id="719cf-1118">You can find a threat-specific link in the event history.</span></span><br/></td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="719cf-1119">Código de error: 0x80508026</span><span class="sxs-lookup"><span data-stu-id="719cf-1119">Error code: 0x80508026</span></span>
</th>
</tr><tr><td><span data-ttu-id="719cf-1120">Message</span><span class="sxs-lookup"><span data-stu-id="719cf-1120">Message</span></span></td>
<td><span data-ttu-id="719cf-1121"><b>ERR_MP_REMOVE_NOT_SUPPORTED </b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-1121"><b>ERR_MP_REMOVE_NOT_SUPPORTED </b>
</span></span></td></tr><tr><td><span data-ttu-id="719cf-1122">Posible motivo</span><span class="sxs-lookup"><span data-stu-id="719cf-1122">Possible reason</span></span></td>
<td>
<span data-ttu-id="719cf-1123">Este error indica que es posible que no se pueda quitar dentro del tipo de contenedor.</span><span class="sxs-lookup"><span data-stu-id="719cf-1123">This error indicates that removal inside the container type might not be not supported.</span></span> 
</td></tr><tr><td><span data-ttu-id="719cf-1124">Solución</span><span class="sxs-lookup"><span data-stu-id="719cf-1124">Resolution</span></span></td><td>
<span data-ttu-id="719cf-1125">Antivirus de Microsoft Defender no es capaz de corregir las amenazas detectadas dentro del archivo.</span><span class="sxs-lookup"><span data-stu-id="719cf-1125">Microsoft Defender Antivirus is not able to remediate threats detected inside the archive.</span></span> <span data-ttu-id="719cf-1126">Considere la posibilidad de quitar manualmente los recursos detectados.</span><span class="sxs-lookup"><span data-stu-id="719cf-1126">Consider manually removing the detected resources.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="719cf-1127">Código de error: 0x80508027</span><span class="sxs-lookup"><span data-stu-id="719cf-1127">Error code: 0x80508027</span></span>
</th>
</tr><tr><td><span data-ttu-id="719cf-1128">Message</span><span class="sxs-lookup"><span data-stu-id="719cf-1128">Message</span></span></td>
<td><span data-ttu-id="719cf-1129"><b>ERR_MP_REMOVE_LOW_MEDIUM_DISABLED </b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-1129"><b>ERR_MP_REMOVE_LOW_MEDIUM_DISABLED </b>
</span></span></td></tr><tr><td><span data-ttu-id="719cf-1130">Posible motivo</span><span class="sxs-lookup"><span data-stu-id="719cf-1130">Possible reason</span></span></td>
<td>
<span data-ttu-id="719cf-1131">Este error indica que la eliminación de amenazas medias y bajas podría deshabilitarse.</span><span class="sxs-lookup"><span data-stu-id="719cf-1131">This error indicates that removal of low and medium threats might be disabled.</span></span> 
</td></tr><tr><td><span data-ttu-id="719cf-1132">Solución</span><span class="sxs-lookup"><span data-stu-id="719cf-1132">Resolution</span></span></td><td>
<span data-ttu-id="719cf-1133">Compruebe las amenazas detectadas y resuelvalas según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="719cf-1133">Check the detected threats and resolve them as required.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="719cf-1134">Código de error: 0x80508029</span><span class="sxs-lookup"><span data-stu-id="719cf-1134">Error code: 0x80508029</span></span>
</th>
</tr><tr><td><span data-ttu-id="719cf-1135">Message</span><span class="sxs-lookup"><span data-stu-id="719cf-1135">Message</span></span></td>
<td><span data-ttu-id="719cf-1136"><b>ERROR_MP_RESCAN_REQUIRED </b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-1136"><b>ERROR_MP_RESCAN_REQUIRED </b>
</span></span></td></tr><tr><td><span data-ttu-id="719cf-1137">Posible motivo</span><span class="sxs-lookup"><span data-stu-id="719cf-1137">Possible reason</span></span></td>
<td>
<span data-ttu-id="719cf-1138">Este error indica que es necesario volver a examinar la amenaza.</span><span class="sxs-lookup"><span data-stu-id="719cf-1138">This error indicates a rescan of the threat is required.</span></span> 
</td></tr><tr><td><span data-ttu-id="719cf-1139">Solución</span><span class="sxs-lookup"><span data-stu-id="719cf-1139">Resolution</span></span></td><td>
<span data-ttu-id="719cf-1140">Ejecute un examen completo del sistema.</span><span class="sxs-lookup"><span data-stu-id="719cf-1140">Run a full system scan.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="719cf-1141">Código de error: 0x80508030</span><span class="sxs-lookup"><span data-stu-id="719cf-1141">Error code: 0x80508030</span></span>
</th>
</tr><tr><td><span data-ttu-id="719cf-1142">Message</span><span class="sxs-lookup"><span data-stu-id="719cf-1142">Message</span></span></td>
<td><span data-ttu-id="719cf-1143"><b>ERROR_MP_CALLISTO_REQUIRED </b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-1143"><b>ERROR_MP_CALLISTO_REQUIRED </b>
</span></span></td></tr><tr><td><span data-ttu-id="719cf-1144">Posible motivo</span><span class="sxs-lookup"><span data-stu-id="719cf-1144">Possible reason</span></span></td>
<td>
<span data-ttu-id="719cf-1145">Este error indica que es necesario realizar un examen sin conexión.</span><span class="sxs-lookup"><span data-stu-id="719cf-1145">This error indicates that an offline scan is required.</span></span> 
</td></tr><tr><td><span data-ttu-id="719cf-1146">Solución</span><span class="sxs-lookup"><span data-stu-id="719cf-1146">Resolution</span></span></td><td>
<span data-ttu-id="719cf-1147">Ejecute el Antivirus de Microsoft Defender sin conexión.</span><span class="sxs-lookup"><span data-stu-id="719cf-1147">Run offline Microsoft Defender Antivirus.</span></span> <span data-ttu-id="719cf-1148">Puede leer sobre cómo hacerlo en el artículo de <a href="https://windows.microsoft.com/windows/what-is-windows-defender-offline">Antivirus de Microsoft Defender sin conexión.</a></span><span class="sxs-lookup"><span data-stu-id="719cf-1148">You can read about how to do this in the <a href="https://windows.microsoft.com/windows/what-is-windows-defender-offline">offline Microsoft Defender Antivirus article</a>.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="719cf-1149">Código de error: 0x80508031</span><span class="sxs-lookup"><span data-stu-id="719cf-1149">Error code: 0x80508031</span></span>
</th>
</tr><tr><td><span data-ttu-id="719cf-1150">Message</span><span class="sxs-lookup"><span data-stu-id="719cf-1150">Message</span></span></td>
<td><span data-ttu-id="719cf-1151"><b>ERROR_MP_PLATFORM_OUTDATED</span><span class="sxs-lookup"><span data-stu-id="719cf-1151"><b>ERROR_MP_PLATFORM_OUTDATED</span></span><br/></b>
</td></tr><tr><td><span data-ttu-id="719cf-1152">Posible motivo</span><span class="sxs-lookup"><span data-stu-id="719cf-1152">Possible reason</span></span></td>
<td>
<span data-ttu-id="719cf-1153">Este error indica que Antivirus de Microsoft Defender no admite la versión actual de la plataforma y requiere una nueva versión de la plataforma.</span><span class="sxs-lookup"><span data-stu-id="719cf-1153">This error indicates that Microsoft Defender Antivirus does not support the current version of the platform and requires a new version of the platform.</span></span> 
</td></tr><tr><td><span data-ttu-id="719cf-1154">Solución</span><span class="sxs-lookup"><span data-stu-id="719cf-1154">Resolution</span></span></td><td>
<span data-ttu-id="719cf-1155">Solo puedes usar Antivirus de Microsoft Defender en Windows 10.</span><span class="sxs-lookup"><span data-stu-id="719cf-1155">You can only use Microsoft Defender Antivirus in Windows 10.</span></span> <span data-ttu-id="719cf-1156">Para Windows 8, Windows 7 y Windows Vista, puedes usar <a href="https://www.microsoft.com/server-cloud/system-center/endpoint-protection-2012.aspx">System Center Endpoint Protection</a>.</span><span class="sxs-lookup"><span data-stu-id="719cf-1156">For Windows 8, Windows 7 and Windows Vista, you can use <a href="https://www.microsoft.com/server-cloud/system-center/endpoint-protection-2012.aspx">System Center Endpoint Protection</a>.</span></span><br/></td>
</tr>
</table><span data-ttu-id="719cf-1157">

<a id="internal-error-codes"></a> Los siguientes códigos de error se usan durante las pruebas internas del Antivirus de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="719cf-1157">

<a id="internal-error-codes"></a> The following error codes are used during internal testing of Microsoft Defender Antivirus.</span></span>

<span data-ttu-id="719cf-1158">Si ve estos errores, puede [](manage-updates-baselines-microsoft-defender-antivirus.md) intentar actualizar definiciones y forzar un nuevo análisis directamente en el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="719cf-1158">If you see these errors, you can try to [update definitions](manage-updates-baselines-microsoft-defender-antivirus.md) and force a rescan directly on the endpoint.</span></span>


<table> 
<tr>
<th colspan="3"><span data-ttu-id="719cf-1159">Códigos de error internos</span><span class="sxs-lookup"><span data-stu-id="719cf-1159">Internal error codes</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="719cf-1160"><b>Código de error</b></span><span class="sxs-lookup"><span data-stu-id="719cf-1160"><b>Error code</b></span></span></th>
<th><span data-ttu-id="719cf-1161">Mensaje mostrado</span><span class="sxs-lookup"><span data-stu-id="719cf-1161">Message displayed</span></span></th>
<th><span data-ttu-id="719cf-1162">Posible motivo de error y resolución</span><span class="sxs-lookup"><span data-stu-id="719cf-1162">Possible reason for error and resolution</span></span></th>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-1163">0x80501004</span><span class="sxs-lookup"><span data-stu-id="719cf-1163">0x80501004</span></span>
</td>
<td><span data-ttu-id="719cf-1164">
<b>ERROR_MP_NO_INTERNET_CONN </b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-1164">
<b>ERROR_MP_NO_INTERNET_CONN </b>
</span></span></td>
<td>
<span data-ttu-id="719cf-1165">Compruebe la conexión a Internet y vuelva a ejecutar el examen.</span><span class="sxs-lookup"><span data-stu-id="719cf-1165">Check your Internet connection, then run the scan again.</span></span>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-1166">0x80501000</span><span class="sxs-lookup"><span data-stu-id="719cf-1166">0x80501000</span></span>
</td>
<td><span data-ttu-id="719cf-1167">
<b>ERROR_MP_UI_CONSOLIDATION_BAS</b> E</span><span class="sxs-lookup"><span data-stu-id="719cf-1167">
<b>ERROR_MP_UI_CONSOLIDATION_BAS</b>E</span></span>
</td>
<td rowspan="34">
<span data-ttu-id="719cf-1168">Se trata de un error interno.</span><span class="sxs-lookup"><span data-stu-id="719cf-1168">This is an internal error.</span></span> <span data-ttu-id="719cf-1169">La causa no está claramente definida.</span><span class="sxs-lookup"><span data-stu-id="719cf-1169">The cause is not clearly defined.</span></span>
</td>
<td rowspan="36">

</td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-1170">0x80501001</span><span class="sxs-lookup"><span data-stu-id="719cf-1170">0x80501001</span></span>
</td>
<td><span data-ttu-id="719cf-1171">
<b>ERROR_MP_ACTIONS_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-1171">
<b>ERROR_MP_ACTIONS_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-1172">0x80501002</span><span class="sxs-lookup"><span data-stu-id="719cf-1172">0x80501002</span></span>
</td>
<td><span data-ttu-id="719cf-1173">
<b>ERROR_MP_NOENGINE</b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-1173">
<b>ERROR_MP_NOENGINE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-1174">0x80501003</span><span class="sxs-lookup"><span data-stu-id="719cf-1174">0x80501003</span></span>
</td>
<td><span data-ttu-id="719cf-1175">
<b>ERROR_MP_ACTIVE_THREATS</b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-1175">
<b>ERROR_MP_ACTIVE_THREATS</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-1176">0x805011011</span><span class="sxs-lookup"><span data-stu-id="719cf-1176">0x805011011</span></span>
</td>
<td><span data-ttu-id="719cf-1177">
<b>MP_ERROR_CODE_LUA_CANCELLED </b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-1177">
<b>MP_ERROR_CODE_LUA_CANCELLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-1178">0x80501101</span><span class="sxs-lookup"><span data-stu-id="719cf-1178">0x80501101</span></span>
</td>
<td><span data-ttu-id="719cf-1179">
<b>ERROR_LUA_CANCELLATION </b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-1179">
<b>ERROR_LUA_CANCELLATION </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-1180">0x80501102</span><span class="sxs-lookup"><span data-stu-id="719cf-1180">0x80501102</span></span>
</td>
<td><span data-ttu-id="719cf-1181">
<b>MP_ERROR_CODE_ALREADY_SHUTDOWN</b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-1181">
<b>MP_ERROR_CODE_ALREADY_SHUTDOWN</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-1182">0x80501103</span><span class="sxs-lookup"><span data-stu-id="719cf-1182">0x80501103</span></span>
</td>
<td><span data-ttu-id="719cf-1183">
<b>MP_ERROR_CODE_RDEVICE_S_ASYNC_CALL_PENDING </b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-1183">
<b>MP_ERROR_CODE_RDEVICE_S_ASYNC_CALL_PENDING </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-1184">0x80501104</span><span class="sxs-lookup"><span data-stu-id="719cf-1184">0x80501104</span></span>
</td>
<td><span data-ttu-id="719cf-1185">
<b>MP_ERROR_CODE_CANCELLED</b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-1185">
<b>MP_ERROR_CODE_CANCELLED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-1186">0x80501105</span><span class="sxs-lookup"><span data-stu-id="719cf-1186">0x80501105</span></span>
</td>
<td><span data-ttu-id="719cf-1187">
<b>MP_ERROR_CODE_NO_TARGETOS</b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-1187">
<b>MP_ERROR_CODE_NO_TARGETOS</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-1188">0x80501106</span><span class="sxs-lookup"><span data-stu-id="719cf-1188">0x80501106</span></span>
</td>
<td><span data-ttu-id="719cf-1189">
<b>MP_ERROR_CODE_BAD_REGEXP</b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-1189">
<b>MP_ERROR_CODE_BAD_REGEXP</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-1190">0x80501107</span><span class="sxs-lookup"><span data-stu-id="719cf-1190">0x80501107</span></span>
</td>
<td><span data-ttu-id="719cf-1191">
<b>MP_ERROR_TEST_INDUCED_ERROR</b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-1191">
<b>MP_ERROR_TEST_INDUCED_ERROR</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-1192">0x80501108</span><span class="sxs-lookup"><span data-stu-id="719cf-1192">0x80501108</span></span>
</td>
<td><span data-ttu-id="719cf-1193">
<b>MP_ERROR_SIG_BACKUP_DISABLED</b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-1193">
<b>MP_ERROR_SIG_BACKUP_DISABLED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-1194">0x80508001</span><span class="sxs-lookup"><span data-stu-id="719cf-1194">0x80508001</span></span>
</td>
<td><span data-ttu-id="719cf-1195">
<b>ERR_MP_BAD_INIT_MODULES</b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-1195">
<b>ERR_MP_BAD_INIT_MODULES</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-1196">0x80508002</span><span class="sxs-lookup"><span data-stu-id="719cf-1196">0x80508002</span></span>
</td>
<td><span data-ttu-id="719cf-1197">
<b>ERR_MP_BAD_DATABASE</b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-1197">
<b>ERR_MP_BAD_DATABASE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-1198">0x80508004</span><span class="sxs-lookup"><span data-stu-id="719cf-1198">0x80508004</span></span>
</td>
<td><span data-ttu-id="719cf-1199">
<b>ERR_MP_BAD_UFS </b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-1199">
<b>ERR_MP_BAD_UFS </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-1200">0x8050800C</span><span class="sxs-lookup"><span data-stu-id="719cf-1200">0x8050800C</span></span>
</td>
<td><span data-ttu-id="719cf-1201">
<b>ERR_MP_BAD_INPUT_DATA</b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-1201">
<b>ERR_MP_BAD_INPUT_DATA</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-1202">0x8050800D</span><span class="sxs-lookup"><span data-stu-id="719cf-1202">0x8050800D</span></span>
</td>
<td><span data-ttu-id="719cf-1203">
<b>ERR_MP_BAD_GLOBAL_STORAGE</b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-1203">
<b>ERR_MP_BAD_GLOBAL_STORAGE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-1204">0x8050800E</span><span class="sxs-lookup"><span data-stu-id="719cf-1204">0x8050800E</span></span>
</td>
<td><span data-ttu-id="719cf-1205">
<b>ERR_MP_OBSOLETE</b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-1205">
<b>ERR_MP_OBSOLETE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-1206">0x8050800F</span><span class="sxs-lookup"><span data-stu-id="719cf-1206">0x8050800F</span></span>
</td>
<td><span data-ttu-id="719cf-1207">
<b>ERR_MP_NOT_SUPPORTED</b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-1207">
<b>ERR_MP_NOT_SUPPORTED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-1208">0x8050800F 0x80508010</span><span class="sxs-lookup"><span data-stu-id="719cf-1208">0x8050800F 0x80508010</span></span>
</td>
<td><span data-ttu-id="719cf-1209">
<b>ERR_MP_NO_MORE_ITEMS </b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-1209">
<b>ERR_MP_NO_MORE_ITEMS </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-1210">0x80508011</span><span class="sxs-lookup"><span data-stu-id="719cf-1210">0x80508011</span></span>
</td>
<td><span data-ttu-id="719cf-1211">
<b>ERR_MP_DUPLICATE_SCANID</b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-1211">
<b>ERR_MP_DUPLICATE_SCANID</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-1212">0x80508012</span><span class="sxs-lookup"><span data-stu-id="719cf-1212">0x80508012</span></span>
</td>
<td><span data-ttu-id="719cf-1213">
<b>ERR_MP_BAD_SCANID</b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-1213">
<b>ERR_MP_BAD_SCANID</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-1214">0x80508013</span><span class="sxs-lookup"><span data-stu-id="719cf-1214">0x80508013</span></span>
</td>
<td><span data-ttu-id="719cf-1215">
<b>ERR_MP_BAD_USERDB_VERSION</b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-1215">
<b>ERR_MP_BAD_USERDB_VERSION</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-1216">0x80508014</span><span class="sxs-lookup"><span data-stu-id="719cf-1216">0x80508014</span></span>
</td>
<td><span data-ttu-id="719cf-1217">
<b>ERR_MP_RESTORE_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-1217">
<b>ERR_MP_RESTORE_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-1218">0x80508016</span><span class="sxs-lookup"><span data-stu-id="719cf-1218">0x80508016</span></span>
</td>
<td><span data-ttu-id="719cf-1219">
<b>ERR_MP_BAD_ACTION</b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-1219">
<b>ERR_MP_BAD_ACTION</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-1220">0x80508019</span><span class="sxs-lookup"><span data-stu-id="719cf-1220">0x80508019</span></span>
</td>
<td><span data-ttu-id="719cf-1221">
<b>ERR_MP_NOT_FOUND</b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-1221">
<b>ERR_MP_NOT_FOUND</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-1222">0x80509001</span><span class="sxs-lookup"><span data-stu-id="719cf-1222">0x80509001</span></span>
</td>
<td><span data-ttu-id="719cf-1223">
<b>ERR_RELO_BAD_EHANDLE</b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-1223">
<b>ERR_RELO_BAD_EHANDLE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-1224">0x80509003</span><span class="sxs-lookup"><span data-stu-id="719cf-1224">0x80509003</span></span>
</td>
<td><span data-ttu-id="719cf-1225">
<b>ERR_RELO_KERNEL_NOT_LOADED</b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-1225">
<b>ERR_RELO_KERNEL_NOT_LOADED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-1226">0x8050A001</span><span class="sxs-lookup"><span data-stu-id="719cf-1226">0x8050A001</span></span>
</td>
<td><span data-ttu-id="719cf-1227">
<b>ERR_MP_BADDB_OPEN</b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-1227">
<b>ERR_MP_BADDB_OPEN</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-1228">0x8050A002</span><span class="sxs-lookup"><span data-stu-id="719cf-1228">0x8050A002</span></span>
</td>
<td><span data-ttu-id="719cf-1229">
<b>ERR_MP_BADDB_HEADER</b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-1229">
<b>ERR_MP_BADDB_HEADER</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-1230">0x8050A003</span><span class="sxs-lookup"><span data-stu-id="719cf-1230">0x8050A003</span></span>
</td>
<td><span data-ttu-id="719cf-1231">
<b>ERR_MP_BADDB_OLDENGINE</b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-1231">
<b>ERR_MP_BADDB_OLDENGINE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-1232">0x8050A004</span><span class="sxs-lookup"><span data-stu-id="719cf-1232">0x8050A004</span></span>
</td>
<td><span data-ttu-id="719cf-1233">
<b>ERR_MP_BADDB_CONTENT </b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-1233">
<b>ERR_MP_BADDB_CONTENT </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-1234">0x8050A005</span><span class="sxs-lookup"><span data-stu-id="719cf-1234">0x8050A005</span></span>
</td>
<td><span data-ttu-id="719cf-1235">
<b>ERR_MP_BADDB_NOTSIGNED</b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-1235">
<b>ERR_MP_BADDB_NOTSIGNED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-1236">0x8050801</span><span class="sxs-lookup"><span data-stu-id="719cf-1236">0x8050801</span></span>
</td>
<td><span data-ttu-id="719cf-1237">
<b>ERR_MP_REMOVE_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-1237">
<b>ERR_MP_REMOVE_FAILED</b>
</span></span></td>
<td>
<span data-ttu-id="719cf-1238">Se trata de un error interno.</span><span class="sxs-lookup"><span data-stu-id="719cf-1238">This is an internal error.</span></span> <span data-ttu-id="719cf-1239">Puede desencadenarse cuando la eliminación de malware no se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="719cf-1239">It might be triggered when malware removal is not successful.</span></span> 
</td>
</tr>
<tr>
<td>
<span data-ttu-id="719cf-1240">0x80508018</span><span class="sxs-lookup"><span data-stu-id="719cf-1240">0x80508018</span></span>
</td>
<td><span data-ttu-id="719cf-1241">
<b>ERR_MP_SCAN_ABORTED </b>
</span><span class="sxs-lookup"><span data-stu-id="719cf-1241">
<b>ERR_MP_SCAN_ABORTED </b>
</span></span></td>
<td>
<span data-ttu-id="719cf-1242">Se trata de un error interno.</span><span class="sxs-lookup"><span data-stu-id="719cf-1242">This is an internal error.</span></span> <span data-ttu-id="719cf-1243">Puede que se haya desencadenado cuando un examen no se completa.</span><span class="sxs-lookup"><span data-stu-id="719cf-1243">It might have triggered when a scan fails to complete.</span></span> 
</td>
</tr>
</table>

## <a name="related-topics"></a><span data-ttu-id="719cf-1244">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="719cf-1244">Related topics</span></span>

- [<span data-ttu-id="719cf-1245">Informe sobre la protección antivirus de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="719cf-1245">Report on Microsoft Defender Antivirus protection</span></span>](report-monitor-microsoft-defender-antivirus.md)
- [<span data-ttu-id="719cf-1246">Antivirus de Microsoft Defender en Windows 10</span><span class="sxs-lookup"><span data-stu-id="719cf-1246">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)