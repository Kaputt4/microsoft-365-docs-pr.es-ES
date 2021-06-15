---
title: Códigos de error e IDs de eventos antivirus de Microsoft Defender
description: Buscar las causas y soluciones de los Antivirus de Microsoft Defender de eventos y errores
keywords: event, error code, siem, logging, troubleshooting, wef, windows event forwarding
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/11/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: cba7a9d6ed23ac1dc72ef6cbcecfdfc7a0f4c60b
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926288"
---
# <a name="review-event-logs-and-error-codes-to-troubleshoot-issues-with-microsoft-defender-antivirus"></a><span data-ttu-id="76b19-104">Revisar registros de sucesos y códigos de error para solucionar problemas del Antivirus de Windows Defender</span><span class="sxs-lookup"><span data-stu-id="76b19-104">Review event logs and error codes to troubleshoot issues with Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="76b19-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="76b19-105">**Applies to:**</span></span>

- [<span data-ttu-id="76b19-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="76b19-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="76b19-107">Si encuentra un problema con Antivirus de Microsoft Defender, puede buscar en las tablas de este tema un problema de coincidencia y una posible solución.</span><span class="sxs-lookup"><span data-stu-id="76b19-107">If you encounter a problem with Microsoft Defender Antivirus, you can search the tables in this topic to find a matching issue and potential solution.</span></span>

<span data-ttu-id="76b19-108">La lista de tablas:</span><span class="sxs-lookup"><span data-stu-id="76b19-108">The tables list:</span></span>

- <span data-ttu-id="76b19-109">[Antivirus de Microsoft Defender de eventos](#windows-defender-av-ids) (estos se aplican a Windows 10 y Windows Server 2016)</span><span class="sxs-lookup"><span data-stu-id="76b19-109">[Microsoft Defender Antivirus event IDs](#windows-defender-av-ids) (these apply to both Windows 10 and Windows Server 2016)</span></span>
- [<span data-ttu-id="76b19-110">Antivirus de Microsoft Defender de error de cliente</span><span class="sxs-lookup"><span data-stu-id="76b19-110">Microsoft Defender Antivirus client error codes</span></span>](#error-codes)
- [<span data-ttu-id="76b19-111">Códigos Antivirus de Microsoft Defender de error de cliente internos (usados por Microsoft durante el desarrollo y las pruebas)</span><span class="sxs-lookup"><span data-stu-id="76b19-111">Internal Microsoft Defender Antivirus client error codes (used by Microsoft during development and testing)</span></span>](#internal-error-codes)

> [!TIP]
> <span data-ttu-id="76b19-112">También puede visitar el sitio web de demostración de Microsoft Defender para endpoint [en demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) para confirmar que funcionan las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="76b19-112">You can also visit the Microsoft Defender for Endpoint demo website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the following features are working:</span></span>
> 
> - <span data-ttu-id="76b19-113">Protección entregada en la nube</span><span class="sxs-lookup"><span data-stu-id="76b19-113">Cloud-delivered protection</span></span>
> - <span data-ttu-id="76b19-114">Aprendizaje rápido (incluido Bloquear a primera vista)</span><span class="sxs-lookup"><span data-stu-id="76b19-114">Fast learning (including Block at first sight)</span></span>
> - <span data-ttu-id="76b19-115">Bloqueo de aplicaciones potencialmente no deseado</span><span class="sxs-lookup"><span data-stu-id="76b19-115">Potentially unwanted application blocking</span></span>

<a id="windows-defender-av-ids"></a>
## <a name="microsoft-defender-antivirus-event-ids"></a><span data-ttu-id="76b19-116">Antivirus de Microsoft Defender de eventos</span><span class="sxs-lookup"><span data-stu-id="76b19-116">Microsoft Defender Antivirus event IDs</span></span>

<span data-ttu-id="76b19-117">Antivirus de Microsoft Defender registra los IDs de eventos en el Windows de eventos.</span><span class="sxs-lookup"><span data-stu-id="76b19-117">Microsoft Defender Antivirus records event IDs in the Windows event log.</span></span>

<span data-ttu-id="76b19-118">Puede ver directamente el registro de eventos, o si tiene una herramienta de administración de eventos y información de seguridad (SIEM) de terceros, también puede usar los [IDs](troubleshoot-microsoft-defender-antivirus.md#windows-defender-av-ids) de eventos de cliente de Antivirus de Microsoft Defender para revisar eventos y errores específicos de los puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="76b19-118">You can directly view the event log, or if you have a third-party security information and event management (SIEM) tool, you can also consume [Microsoft Defender Antivirus client event IDs](troubleshoot-microsoft-defender-antivirus.md#windows-defender-av-ids) to review specific events and errors from your endpoints.</span></span>

<span data-ttu-id="76b19-119">En la tabla de esta sección se enumeran los principales Antivirus de Microsoft Defender de eventos y, siempre que sea posible, proporciona soluciones sugeridas para corregir o resolver el error.</span><span class="sxs-lookup"><span data-stu-id="76b19-119">The table in this section lists the main Microsoft Defender Antivirus event IDs and, where possible, provides suggested solutions to fix or resolve the error.</span></span> 

## <a name="to-view-a-microsoft-defender-antivirus-event"></a><span data-ttu-id="76b19-120">Para ver un evento Antivirus de Microsoft Defender evento</span><span class="sxs-lookup"><span data-stu-id="76b19-120">To view a Microsoft Defender Antivirus event</span></span>

1.  <span data-ttu-id="76b19-121">Abra **el Visor de eventos**.</span><span class="sxs-lookup"><span data-stu-id="76b19-121">Open **Event Viewer**.</span></span>
2.  <span data-ttu-id="76b19-122">En el árbol de consola, expanda **Registros de** aplicaciones y servicios , a continuación, **Microsoft**, a continuación, **Windows**, a continuación, **Windows Defender**.</span><span class="sxs-lookup"><span data-stu-id="76b19-122">In the console tree, expand **Applications and Services Logs**, then **Microsoft**, then **Windows**, then **Windows Defender**.</span></span>
3.  <span data-ttu-id="76b19-123">Haga doble clic en **Operativo**.</span><span class="sxs-lookup"><span data-stu-id="76b19-123">Double-click on **Operational**.</span></span>
4.  <span data-ttu-id="76b19-124">En el panel de detalles, vea la lista de eventos individuales para buscar el evento.</span><span class="sxs-lookup"><span data-stu-id="76b19-124">In the details pane, view the list of individual events to find your event.</span></span>
5.  <span data-ttu-id="76b19-125">Haga clic en el evento para ver detalles específicos sobre un evento en el panel inferior, en las **pestañas General** **y** Detalles.</span><span class="sxs-lookup"><span data-stu-id="76b19-125">Click the event to see specific details about an event in the lower pane, under the **General** and **Details** tabs.</span></span>

<table> 
<tr>
<th colspan="2" ><span data-ttu-id="76b19-126">Identificador de evento: 1000</span><span class="sxs-lookup"><span data-stu-id="76b19-126">Event ID: 1000</span></span></th>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-127">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="76b19-127">Symbolic name:</span></span>
</td>
<td><span data-ttu-id="76b19-128">
<b>MALWAREPROTECTION_SCAN_STARTED</b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-128">
<b>MALWAREPROTECTION_SCAN_STARTED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-129">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="76b19-129">Message:</span></span>
</td>
<td ><span data-ttu-id="76b19-130">
<b>Se inició un examen de antimalware. </b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-130">
<b>An antimalware scan started. </b>
</span></span></td>
</tr>
<tr>
<td >
<span data-ttu-id="76b19-131">Descripción:</span><span class="sxs-lookup"><span data-stu-id="76b19-131">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="76b19-132">
<dt>Id. de examen: &lt; Número de identificador del &gt; examen correspondiente.</dt> 
<dt> Tipo de examen: &lt; Tipo de examen , por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="76b19-132">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="76b19-133">Antivirus</span><span class="sxs-lookup"><span data-stu-id="76b19-133">Antivirus</span></span></li>
<li><span data-ttu-id="76b19-134">Antispyware</span><span class="sxs-lookup"><span data-stu-id="76b19-134">Antispyware</span></span></li>
<li><span data-ttu-id="76b19-135">Antimalware</span><span class="sxs-lookup"><span data-stu-id="76b19-135">Antimalware</span></span></li>
</ul><span data-ttu-id="76b19-136">
</dt>
<dt>Parámetros de examen: &lt; parámetros de examen , por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="76b19-136">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="76b19-137">Examen completo</span><span class="sxs-lookup"><span data-stu-id="76b19-137">Full scan</span></span></li>
<li><span data-ttu-id="76b19-138">Examen rápido</span><span class="sxs-lookup"><span data-stu-id="76b19-138">Quick scan</span></span></li>
<li><span data-ttu-id="76b19-139">Examen del cliente</span><span class="sxs-lookup"><span data-stu-id="76b19-139">Customer scan</span></span></li>
</ul><span data-ttu-id="76b19-140">
</dt>
<dt>Recursos de examen: &lt; Recursos (como archivos/directorios/BHO) que se &gt; examinaron.</dt> 
<dt>Usuario: &lt; Dominio &gt; \& lt; Usuario &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="76b19-140">
</dt>
<dt>Scan Resources: &lt;Resources (such as files/directories/BHO) that were scanned.&gt;</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="76b19-141">Identificador de evento: 1001</span><span class="sxs-lookup"><span data-stu-id="76b19-141">Event ID: 1001</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="76b19-142">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="76b19-142">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="76b19-143">
<b>MALWAREPROTECTION_SCAN_COMPLETED</b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-143">
<b>MALWAREPROTECTION_SCAN_COMPLETED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-144">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="76b19-144">Message:</span></span>
</td>
<td ><span data-ttu-id="76b19-145">
<b>Se ha finalizado un examen de antimalware.</b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-145">
<b>An antimalware scan finished.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-146">Descripción:</span><span class="sxs-lookup"><span data-stu-id="76b19-146">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="76b19-147">
<dt>Id. de examen: &lt; Número de identificador del &gt; examen correspondiente.</dt> 
<dt> Tipo de examen: &lt; Tipo de examen , por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="76b19-147">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="76b19-148">Antivirus</span><span class="sxs-lookup"><span data-stu-id="76b19-148">Antivirus</span></span></li>
<li><span data-ttu-id="76b19-149">Antispyware</span><span class="sxs-lookup"><span data-stu-id="76b19-149">Antispyware</span></span></li>
<li><span data-ttu-id="76b19-150">Antimalware</span><span class="sxs-lookup"><span data-stu-id="76b19-150">Antimalware</span></span></li>
</ul><span data-ttu-id="76b19-151">
</dt>
<dt>Parámetros de examen: &lt; parámetros de examen , por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="76b19-151">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="76b19-152">Examen completo</span><span class="sxs-lookup"><span data-stu-id="76b19-152">Full scan</span></span></li>
<li><span data-ttu-id="76b19-153">Examen rápido</span><span class="sxs-lookup"><span data-stu-id="76b19-153">Quick scan</span></span></li>
<li><span data-ttu-id="76b19-154">Examen del cliente</span><span class="sxs-lookup"><span data-stu-id="76b19-154">Customer scan</span></span></li>
</ul><span data-ttu-id="76b19-155">
</dt>
<dt>Usuario: &lt; Dominio &gt; \& lt; Tiempo &gt; </dt>
<dt>de examen del usuario: la &lt; duración de un examen. &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="76b19-155">
</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Scan Time: &lt;The duration of a scan.&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="76b19-156">Identificador de evento: 1002</span><span class="sxs-lookup"><span data-stu-id="76b19-156">Event ID: 1002</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="76b19-157">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="76b19-157">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="76b19-158">
<b>MALWAREPROTECTION_SCAN_CANCELLED </b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-158">
<b>MALWAREPROTECTION_SCAN_CANCELLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-159">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="76b19-159">Message:</span></span>
</td>
<td ><span data-ttu-id="76b19-160">
<b>Antes de finalizar, se detuvo un examen antimalware. </b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-160">
<b>An antimalware scan was stopped before it finished. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-161">Descripción:</span><span class="sxs-lookup"><span data-stu-id="76b19-161">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="76b19-162">
<dt>Id. de examen: &lt; Número de identificador del &gt; examen correspondiente.</dt> 
<dt> Tipo de examen: &lt; Tipo de examen , por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="76b19-162">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="76b19-163">Antivirus</span><span class="sxs-lookup"><span data-stu-id="76b19-163">Antivirus</span></span></li>
<li><span data-ttu-id="76b19-164">Antispyware</span><span class="sxs-lookup"><span data-stu-id="76b19-164">Antispyware</span></span></li>
<li><span data-ttu-id="76b19-165">Antimalware</span><span class="sxs-lookup"><span data-stu-id="76b19-165">Antimalware</span></span></li>
</ul><span data-ttu-id="76b19-166">
</dt>
<dt>Parámetros de examen: &lt; parámetros de examen , por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="76b19-166">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="76b19-167">Examen completo</span><span class="sxs-lookup"><span data-stu-id="76b19-167">Full scan</span></span></li>
<li><span data-ttu-id="76b19-168">Examen rápido</span><span class="sxs-lookup"><span data-stu-id="76b19-168">Quick scan</span></span></li>
<li><span data-ttu-id="76b19-169">Examen del cliente</span><span class="sxs-lookup"><span data-stu-id="76b19-169">Customer scan</span></span></li>
</ul><span data-ttu-id="76b19-170">
</dt>
<dt>Usuario: &lt; Dominio &gt; &amp; lt; Tiempo &gt; </dt>
<dt>de examen del usuario: la &lt; duración de un examen. &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="76b19-170">
</dt>
<dt>User: &lt;Domain&gt;&amp;lt;User&gt;</dt>
<dt>Scan Time: &lt;The duration of a scan.&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="76b19-171">Identificador de evento: 1003</span><span class="sxs-lookup"><span data-stu-id="76b19-171">Event ID: 1003</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="76b19-172">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="76b19-172">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="76b19-173">
<b>MALWAREPROTECTION_SCAN_PAUSED </b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-173">
<b>MALWAREPROTECTION_SCAN_PAUSED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-174">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="76b19-174">Message:</span></span>
</td>
<td ><span data-ttu-id="76b19-175">
<b>Se ha pausado un examen antimalware. </b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-175">
<b>An antimalware scan was paused. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-176">Descripción:</span><span class="sxs-lookup"><span data-stu-id="76b19-176">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="76b19-177">
<dt>Id. de examen: &lt; Número de identificador del &gt; examen correspondiente.</dt> 
<dt> Tipo de examen: &lt; Tipo de examen , por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="76b19-177">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="76b19-178">Antivirus</span><span class="sxs-lookup"><span data-stu-id="76b19-178">Antivirus</span></span></li>
<li><span data-ttu-id="76b19-179">Antispyware</span><span class="sxs-lookup"><span data-stu-id="76b19-179">Antispyware</span></span></li>
<li><span data-ttu-id="76b19-180">Antimalware</span><span class="sxs-lookup"><span data-stu-id="76b19-180">Antimalware</span></span></li>
</ul><span data-ttu-id="76b19-181">
</dt>
<dt>Parámetros de examen: &lt; parámetros de examen , por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="76b19-181">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="76b19-182">Examen completo</span><span class="sxs-lookup"><span data-stu-id="76b19-182">Full scan</span></span></li>
<li><span data-ttu-id="76b19-183">Examen rápido</span><span class="sxs-lookup"><span data-stu-id="76b19-183">Quick scan</span></span></li>
<li><span data-ttu-id="76b19-184">Examen del cliente</span><span class="sxs-lookup"><span data-stu-id="76b19-184">Customer scan</span></span></li>
</ul><span data-ttu-id="76b19-185">
</dt>
<dt>Usuario: &lt; Dominio &gt; \& lt; Usuario&gt;</dt>
</span><span class="sxs-lookup"><span data-stu-id="76b19-185">
</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="76b19-186">Identificador de evento: 1004</span><span class="sxs-lookup"><span data-stu-id="76b19-186">Event ID: 1004</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="76b19-187">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="76b19-187">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="76b19-188">
<b>MALWAREPROTECTION_SCAN_RESUMED </b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-188">
<b>MALWAREPROTECTION_SCAN_RESUMED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-189">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="76b19-189">Message:</span></span>
</td>
<td ><span data-ttu-id="76b19-190">
<b>Se reanudó un examen antimalware. </b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-190">
<b>An antimalware scan was resumed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-191">Descripción:</span><span class="sxs-lookup"><span data-stu-id="76b19-191">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="76b19-192">
<dt>Id. de examen: &lt; Número de identificador del &gt; examen correspondiente.</dt> 
<dt> Tipo de examen: &lt; Tipo de examen , por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="76b19-192">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="76b19-193">Antivirus</span><span class="sxs-lookup"><span data-stu-id="76b19-193">Antivirus</span></span></li>
<li><span data-ttu-id="76b19-194">Antispyware</span><span class="sxs-lookup"><span data-stu-id="76b19-194">Antispyware</span></span></li>
<li><span data-ttu-id="76b19-195">Antimalware</span><span class="sxs-lookup"><span data-stu-id="76b19-195">Antimalware</span></span></li>
</ul><span data-ttu-id="76b19-196">
</dt>
<dt>Parámetros de examen: &lt; parámetros de examen , por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="76b19-196">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="76b19-197">Examen completo</span><span class="sxs-lookup"><span data-stu-id="76b19-197">Full scan</span></span></li>
<li><span data-ttu-id="76b19-198">Examen rápido</span><span class="sxs-lookup"><span data-stu-id="76b19-198">Quick scan</span></span></li>
<li><span data-ttu-id="76b19-199">Examen del cliente</span><span class="sxs-lookup"><span data-stu-id="76b19-199">Customer scan</span></span></li>
</ul><span data-ttu-id="76b19-200">
</dt>
<dt>Usuario: &lt; Dominio &gt; \& lt; Usuario&gt;</dt>
</span><span class="sxs-lookup"><span data-stu-id="76b19-200">
</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="76b19-201">Identificador de evento: 1005</span><span class="sxs-lookup"><span data-stu-id="76b19-201">Event ID: 1005</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="76b19-202">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="76b19-202">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="76b19-203">
<b>MALWAREPROTECTION_SCAN_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-203">
<b>MALWAREPROTECTION_SCAN_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-204">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="76b19-204">Message:</span></span>
</td>
<td ><span data-ttu-id="76b19-205">
<b>Error en un examen antimalware. </b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-205">
<b>An antimalware scan failed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-206">Descripción:</span><span class="sxs-lookup"><span data-stu-id="76b19-206">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="76b19-207">
<dt>Id. de examen: &lt; Número de identificador del &gt; examen correspondiente.</dt> 
<dt> Tipo de examen: &lt; Tipo de examen , por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="76b19-207">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="76b19-208">Antivirus</span><span class="sxs-lookup"><span data-stu-id="76b19-208">Antivirus</span></span></li>
<li><span data-ttu-id="76b19-209">Antispyware</span><span class="sxs-lookup"><span data-stu-id="76b19-209">Antispyware</span></span></li>
<li><span data-ttu-id="76b19-210">Antimalware</span><span class="sxs-lookup"><span data-stu-id="76b19-210">Antimalware</span></span></li>
</ul><span data-ttu-id="76b19-211">
</dt>
<dt>Parámetros de examen: &lt; parámetros de examen , por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="76b19-211">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="76b19-212">Examen completo</span><span class="sxs-lookup"><span data-stu-id="76b19-212">Full scan</span></span></li>
<li><span data-ttu-id="76b19-213">Examen rápido</span><span class="sxs-lookup"><span data-stu-id="76b19-213">Quick scan</span></span></li>
<li><span data-ttu-id="76b19-214">Examen del cliente</span><span class="sxs-lookup"><span data-stu-id="76b19-214">Customer scan</span></span></li>
</ul><span data-ttu-id="76b19-215">
</dt>
<dt>Usuario: &lt; Dominio &gt; \& lt; Código &gt; </dt>
<dt>de error del usuario: Código de error &lt; Código de resultado asociado con el estado de &gt; amenaza. Valores HRESULT estándar.</dt> 
<dt>Descripción del error: &lt; Descripción del error &gt; Descripción del error.</dt>
</span><span class="sxs-lookup"><span data-stu-id="76b19-215">
</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-216">Acción del usuario:</span><span class="sxs-lookup"><span data-stu-id="76b19-216">User action:</span></span>
</td>
<td >
<span data-ttu-id="76b19-217">El cliente antivirus encontró un error y se detuvo el examen actual.</span><span class="sxs-lookup"><span data-stu-id="76b19-217">The antivirus client encountered an error, and the current scan has stopped.</span></span> <span data-ttu-id="76b19-218">El examen puede producir un error debido a un problema del lado cliente.</span><span class="sxs-lookup"><span data-stu-id="76b19-218">The scan might fail due to a client-side issue.</span></span> <span data-ttu-id="76b19-219">Este registro de evento incluye el identificador de examen, el tipo de examen (Antivirus de Microsoft Defender, antispyware, antimalware), los parámetros de examen, el usuario que inició el examen, el código de error y una descripción del error.</span><span class="sxs-lookup"><span data-stu-id="76b19-219">This event record includes the scan ID, type of scan (Microsoft Defender Antivirus, antispyware, antimalware), scan parameters, the user that started the scan, the error code, and a description of the error.</span></span>
<span data-ttu-id="76b19-220">Para solucionar este evento:</span><span class="sxs-lookup"><span data-stu-id="76b19-220">To troubleshoot this event:</span></span>
<ol>
<li><span data-ttu-id="76b19-221">Vuelva a ejecutar el examen.</span><span class="sxs-lookup"><span data-stu-id="76b19-221">Run the scan again.</span></span></li>
<li><span data-ttu-id="76b19-222">Si se produce un error de la misma manera, vaya <b></b> al sitio de soporte técnico de <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft</a>, escriba el número de error en el cuadro Buscar para buscar el código de error.</span><span class="sxs-lookup"><span data-stu-id="76b19-222">If it fails in the same way, go to the <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft Support site</a>, enter the error number in the <b>Search</b> box to look for the error code.</span></span></li>
<li><span data-ttu-id="76b19-223">Contactar al <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Soporte técnico de Microsoft</a>.</span><span class="sxs-lookup"><span data-stu-id="76b19-223">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="76b19-224">Identificador de evento: 1006</span><span class="sxs-lookup"><span data-stu-id="76b19-224">Event ID: 1006</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="76b19-225">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="76b19-225">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="76b19-226">
<b>MALWAREPROTECTION_MALWARE_DETECTED </b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-226">
<b>MALWAREPROTECTION_MALWARE_DETECTED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-227">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="76b19-227">Message:</span></span>
</td>
<td ><span data-ttu-id="76b19-228">
<b>El motor de antimalware encontró malware u otro software potencialmente no deseado. </b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-228">
<b>The antimalware engine found malware or other potentially unwanted software. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-229">Descripción:</span><span class="sxs-lookup"><span data-stu-id="76b19-229">Description:</span></span>
</td>
<td >
<span data-ttu-id="76b19-230">Para obtener más información, vea los artículos siguientes: </span><span class="sxs-lookup"><span data-stu-id="76b19-230">For more information, see the following:</span></span>
<dl><span data-ttu-id="76b19-231">
<dt>Nombre: &lt; Id. &gt; de</dt>
<dt>nombre de &lt; amenaza: Gravedad del id. &gt; </dt>de 
<dt> amenaza: gravedad , por &lt; &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="76b19-231">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="76b19-232">Bajo</span><span class="sxs-lookup"><span data-stu-id="76b19-232">Low</span></span></li>
<li><span data-ttu-id="76b19-233">Moderado</span><span class="sxs-lookup"><span data-stu-id="76b19-233">Moderate</span></span></li>
<li><span data-ttu-id="76b19-234">Alta</span><span class="sxs-lookup"><span data-stu-id="76b19-234">High</span></span></li>
<li><span data-ttu-id="76b19-235">Grave</span><span class="sxs-lookup"><span data-stu-id="76b19-235">Severe</span></span></li>
</ul><span data-ttu-id="76b19-236">
</dt>
<dt>Categoría: &lt; Descripción de &gt; categoría , por ejemplo, cualquier tipo de amenaza o malware.</dt> 
<dt>Ruta de acceso: &lt; Origen &gt; de detección</dt>de ruta de 
<dt> acceso de &lt; archivo: Origen de &gt; detección, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="76b19-236">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span><ul>
<li><span data-ttu-id="76b19-237">Unknown</span><span class="sxs-lookup"><span data-stu-id="76b19-237">Unknown</span></span></li>
<li><span data-ttu-id="76b19-238">Equipo local</span><span class="sxs-lookup"><span data-stu-id="76b19-238">Local computer</span></span></li>
<li><span data-ttu-id="76b19-239">Recurso compartido de red</span><span class="sxs-lookup"><span data-stu-id="76b19-239">Network share</span></span></li>
<li><span data-ttu-id="76b19-240">Internet</span><span class="sxs-lookup"><span data-stu-id="76b19-240">Internet</span></span></li>
<li><span data-ttu-id="76b19-241">Tráfico entrante</span><span class="sxs-lookup"><span data-stu-id="76b19-241">Incoming traffic</span></span></li>
<li><span data-ttu-id="76b19-242">Tráfico saliente</span><span class="sxs-lookup"><span data-stu-id="76b19-242">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="76b19-243">
</dt>
<dt>Tipo de &lt; detección: Tipo de &gt; detección , por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="76b19-243">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="76b19-244">Heurística</span><span class="sxs-lookup"><span data-stu-id="76b19-244">Heuristics</span></span></li>
<li><span data-ttu-id="76b19-245">Generic</span><span class="sxs-lookup"><span data-stu-id="76b19-245">Generic</span></span></li>
<li><span data-ttu-id="76b19-246">Concreto</span><span class="sxs-lookup"><span data-stu-id="76b19-246">Concrete</span></span></li>
<li><span data-ttu-id="76b19-247">Firma dinámica</span><span class="sxs-lookup"><span data-stu-id="76b19-247">Dynamic signature</span></span></li>
</ul><span data-ttu-id="76b19-248">
</dt>
<dt>Origen de &lt; detección: origen de &gt; detección por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="76b19-248">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="76b19-249">Usuario: usuario iniciado</span><span class="sxs-lookup"><span data-stu-id="76b19-249">User: user initiated</span></span></li>
<li><span data-ttu-id="76b19-250">Sistema: sistema iniciado</span><span class="sxs-lookup"><span data-stu-id="76b19-250">System: system initiated</span></span></li>
<li><span data-ttu-id="76b19-251">En tiempo real: componente en tiempo real iniciado</span><span class="sxs-lookup"><span data-stu-id="76b19-251">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="76b19-252">IOAV: Descargas de IE y Outlook datos adjuntos de Express iniciados</span><span class="sxs-lookup"><span data-stu-id="76b19-252">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="76b19-253">NIS: sistema de inspección de red</span><span class="sxs-lookup"><span data-stu-id="76b19-253">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="76b19-254">IEPROTECT: IE - IExtensionValidation; esto protege contra controles de páginas web malintencionadas</span><span class="sxs-lookup"><span data-stu-id="76b19-254">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="76b19-255">Antimalware de inicio anticipado (ELAM).</span><span class="sxs-lookup"><span data-stu-id="76b19-255">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="76b19-256">Esto incluye malware detectado por la secuencia de arranque</span><span class="sxs-lookup"><span data-stu-id="76b19-256">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="76b19-257">Atestación remota</span><span class="sxs-lookup"><span data-stu-id="76b19-257">Remote attestation</span></span></li>
</ul><span data-ttu-id="76b19-258">Interfaz de examen antimalware (AMSI).</span><span class="sxs-lookup"><span data-stu-id="76b19-258">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="76b19-259">Se usa principalmente para proteger scripts (PS, VBS), aunque también pueden invocarse por terceros.</span><span class="sxs-lookup"><span data-stu-id="76b19-259">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="76b19-260">Estado de </dt> 
<dt>UAC: Usuario &lt; &gt; de</dt>
<dt>estado: Dominio &lt; &gt; \& lt; Nombre &gt; </dt>del proceso de usuario: proceso en la versión de firma
<dt> &lt; &gt; PID:</dt>versión de
<dt> &lt; definición &gt; </dt>Versión del
<dt>motor: Antimalware Engine &lt; versión &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="76b19-260">UAC</dt>
<dt>Status: &lt;Status&gt;</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="76b19-261">Identificador de evento: 1007</span><span class="sxs-lookup"><span data-stu-id="76b19-261">Event ID: 1007</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="76b19-262">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="76b19-262">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="76b19-263">
<b>MALWAREPROTECTION_MALWARE_ACTION_TAKEN </b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-263">
<b>MALWAREPROTECTION_MALWARE_ACTION_TAKEN </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-264">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="76b19-264">Message:</span></span>
</td>
<td ><span data-ttu-id="76b19-265">
<b>La plataforma antimalware realizó una acción para proteger el sistema de malware u otro software potencialmente no deseado. </b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-265">
<b>The antimalware platform performed an action to protect your system from malware or other potentially unwanted software. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-266">Descripción:</span><span class="sxs-lookup"><span data-stu-id="76b19-266">Description:</span></span>
</td>
<td >
<span data-ttu-id="76b19-267">Antivirus de Microsoft Defender ha tomado medidas para proteger esta máquina de malware u otro software potencialmente no deseado.</span><span class="sxs-lookup"><span data-stu-id="76b19-267">Microsoft Defender Antivirus has taken action to protect this machine from malware or other potentially unwanted software.</span></span> <span data-ttu-id="76b19-268">Para obtener más información, vea los artículos siguientes: </span><span class="sxs-lookup"><span data-stu-id="76b19-268">For more information, see the following:</span></span>
<dl><span data-ttu-id="76b19-269">
<dt>Usuario: &lt; Dominio &gt; \& lt; Nombre &gt; </dt>
<dt>de usuario: &lt; Identificador de nombre &gt; de</dt>
<dt>amenaza: &lt; &gt; Id.</dt>de amenaza 
<dt> Gravedad: Gravedad , por &lt; &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="76b19-269">
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="76b19-270">Bajo</span><span class="sxs-lookup"><span data-stu-id="76b19-270">Low</span></span></li>
<li><span data-ttu-id="76b19-271">Moderado</span><span class="sxs-lookup"><span data-stu-id="76b19-271">Moderate</span></span></li>
<li><span data-ttu-id="76b19-272">Alta</span><span class="sxs-lookup"><span data-stu-id="76b19-272">High</span></span></li>
<li><span data-ttu-id="76b19-273">Grave</span><span class="sxs-lookup"><span data-stu-id="76b19-273">Severe</span></span></li>
</ul><span data-ttu-id="76b19-274">
</dt>
<dt>Categoría: &lt; Descripción de &gt; categoría , por ejemplo, cualquier tipo de amenaza o malware.</dt> 
<dt> Action: &lt; Action , por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="76b19-274">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Action: &lt;Action&gt;, for example:</span></span><ul>
<li><span data-ttu-id="76b19-275">Clean: el recurso se ha limpiado</span><span class="sxs-lookup"><span data-stu-id="76b19-275">Clean: The resource was cleaned</span></span></li>
<li><span data-ttu-id="76b19-276">Cuarentena: el recurso se ha puesto en cuarentena</span><span class="sxs-lookup"><span data-stu-id="76b19-276">Quarantine: The resource was quarantined</span></span></li>
<li><span data-ttu-id="76b19-277">Quitar: se eliminó el recurso</span><span class="sxs-lookup"><span data-stu-id="76b19-277">Remove: The resource was deleted</span></span></li>
<li><span data-ttu-id="76b19-278">Permitir: se permitió que el recurso se ejecutara o existiera</span><span class="sxs-lookup"><span data-stu-id="76b19-278">Allow: The resource was allowed to execute/exist</span></span></li>
<li><span data-ttu-id="76b19-279">Definido por el usuario: acción definida por el usuario que normalmente es una de esta lista de acciones que el usuario ha especificado</span><span class="sxs-lookup"><span data-stu-id="76b19-279">User defined: User-defined action that is normally one from this list of actions that the user has specified</span></span></li>
<li><span data-ttu-id="76b19-280">Sin acción: sin acción</span><span class="sxs-lookup"><span data-stu-id="76b19-280">No action: No action</span></span></li>
<li><span data-ttu-id="76b19-281">Bloquear: se bloqueó el recurso para que no se ejecutara</span><span class="sxs-lookup"><span data-stu-id="76b19-281">Block: The resource was blocked from executing</span></span></li>
</ul><span data-ttu-id="76b19-282">
</dt>
<dt>Estado: &lt; Status &gt; </dt>
<dt>Signature Version: &lt; Definition version &gt; </dt>Engine
<dt>Version: Antimalware Engine &lt; version &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="76b19-282">
</dt>
<dt>Status: &lt;Status&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="76b19-283">Identificador de evento: 1008</span><span class="sxs-lookup"><span data-stu-id="76b19-283">Event ID: 1008</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="76b19-284">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="76b19-284">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="76b19-285">
<b>MALWAREPROTECTION_MALWARE_ACTION_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-285">
<b>MALWAREPROTECTION_MALWARE_ACTION_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-286">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="76b19-286">Message:</span></span>
</td>
<td ><span data-ttu-id="76b19-287">
<b>La plataforma antimalware intentó realizar una acción para proteger el sistema de malware u otro software potencialmente no deseado, pero la acción falló.</b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-287">
<b>The antimalware platform attempted to perform an action to protect your system from malware or other potentially unwanted software, but the action failed.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-288">Descripción:</span><span class="sxs-lookup"><span data-stu-id="76b19-288">Description:</span></span>
</td>
<td >
<span data-ttu-id="76b19-289">Antivirus de Microsoft Defender ha encontrado un error al tomar medidas en malware u otro software potencialmente no deseado.</span><span class="sxs-lookup"><span data-stu-id="76b19-289">Microsoft Defender Antivirus has encountered an error when taking action on malware or other potentially unwanted software.</span></span> <span data-ttu-id="76b19-290">Para obtener más información, vea los artículos siguientes: </span><span class="sxs-lookup"><span data-stu-id="76b19-290">For more information, see the following:</span></span>
<dl><span data-ttu-id="76b19-291">
<dt>Usuario: &lt; Dominio &gt; \& lt; Nombre &gt; </dt>
<dt>de usuario: &lt; Identificador de nombre &gt; de</dt>
<dt>amenaza: &lt; &gt; Id.</dt>de amenaza 
<dt> Gravedad: Gravedad , por &lt; &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="76b19-291">
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="76b19-292">Bajo</span><span class="sxs-lookup"><span data-stu-id="76b19-292">Low</span></span></li>
<li><span data-ttu-id="76b19-293">Moderado</span><span class="sxs-lookup"><span data-stu-id="76b19-293">Moderate</span></span></li>
<li><span data-ttu-id="76b19-294">Alta</span><span class="sxs-lookup"><span data-stu-id="76b19-294">High</span></span></li>
<li><span data-ttu-id="76b19-295">Grave</span><span class="sxs-lookup"><span data-stu-id="76b19-295">Severe</span></span></li>
</ul><span data-ttu-id="76b19-296">
</dt>
<dt>Categoría: &lt; Descripción de &gt; categoría , por ejemplo, cualquier tipo de amenaza o malware.</dt> 
<dt>Ruta de acceso: &lt; Ruta &gt; de acceso</dt> 
<dt> de archivo &lt; Acción: Acción , por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="76b19-296">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Action: &lt;Action&gt;, for example:</span></span><ul>
<li><span data-ttu-id="76b19-297">Clean: el recurso se ha limpiado</span><span class="sxs-lookup"><span data-stu-id="76b19-297">Clean: The resource was cleaned</span></span></li>
<li><span data-ttu-id="76b19-298">Cuarentena: el recurso se ha puesto en cuarentena</span><span class="sxs-lookup"><span data-stu-id="76b19-298">Quarantine: The resource was quarantined</span></span></li>
<li><span data-ttu-id="76b19-299">Quitar: se eliminó el recurso</span><span class="sxs-lookup"><span data-stu-id="76b19-299">Remove: The resource was deleted</span></span></li>
<li><span data-ttu-id="76b19-300">Permitir: se permitió que el recurso se ejecutara o existiera</span><span class="sxs-lookup"><span data-stu-id="76b19-300">Allow: The resource was allowed to execute/exist</span></span></li>
<li><span data-ttu-id="76b19-301">Definido por el usuario: acción definida por el usuario que normalmente es una de esta lista de acciones que el usuario ha especificado</span><span class="sxs-lookup"><span data-stu-id="76b19-301">User defined: User-defined action that is normally one from this list of actions that the user has specified</span></span></li>
<li><span data-ttu-id="76b19-302">Sin acción: sin acción</span><span class="sxs-lookup"><span data-stu-id="76b19-302">No action: No action</span></span></li>
<li><span data-ttu-id="76b19-303">Bloquear: se bloqueó el recurso para que no se ejecutara</span><span class="sxs-lookup"><span data-stu-id="76b19-303">Block: The resource was blocked from executing</span></span></li>
</ul><span data-ttu-id="76b19-304">
</dt>
<dt>Código de error: &lt; Código de error &gt; Código de resultado asociado con el estado de amenaza. Valores HRESULT estándar. </dt> 
<dt>Descripción del error: &lt; Descripción del error Descripción del &gt; error.</dt> 
<dt>Estado: &lt; Status &gt; </dt>
<dt>Signature Version: &lt; Definition version &gt; </dt>Engine
<dt>Version: Antimalware Engine &lt; version &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="76b19-304">
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
<th colspan="2"><span data-ttu-id="76b19-305">Identificador de evento: 1009</span><span class="sxs-lookup"><span data-stu-id="76b19-305">Event ID: 1009</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="76b19-306">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="76b19-306">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="76b19-307">
<b>MALWAREPROTECTION_QUARANTINE_RESTORE </b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-307">
<b>MALWAREPROTECTION_QUARANTINE_RESTORE </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-308">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="76b19-308">Message:</span></span>
</td>
<td ><span data-ttu-id="76b19-309">
<b>La plataforma antimalware restauró un elemento de cuarentena. </b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-309">
<b>The antimalware platform restored an item from quarantine. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-310">Descripción:</span><span class="sxs-lookup"><span data-stu-id="76b19-310">Description:</span></span>
</td>
<td >
<span data-ttu-id="76b19-311">Antivirus de Microsoft Defender ha restaurado un elemento de cuarentena.</span><span class="sxs-lookup"><span data-stu-id="76b19-311">Microsoft Defender Antivirus has restored an item from quarantine.</span></span> <span data-ttu-id="76b19-312">Para obtener más información, vea los artículos siguientes: </span><span class="sxs-lookup"><span data-stu-id="76b19-312">For more information, see the following:</span></span>
<dl><span data-ttu-id="76b19-313">
<dt>Nombre: &lt; Id. &gt; de</dt>
<dt>nombre de &lt; amenaza: Gravedad del id. &gt; </dt>de 
<dt> amenaza: gravedad , por &lt; &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="76b19-313">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="76b19-314">Bajo</span><span class="sxs-lookup"><span data-stu-id="76b19-314">Low</span></span></li>
<li><span data-ttu-id="76b19-315">Moderado</span><span class="sxs-lookup"><span data-stu-id="76b19-315">Moderate</span></span></li>
<li><span data-ttu-id="76b19-316">Alta</span><span class="sxs-lookup"><span data-stu-id="76b19-316">High</span></span></li>
<li><span data-ttu-id="76b19-317">Grave</span><span class="sxs-lookup"><span data-stu-id="76b19-317">Severe</span></span></li>
</ul><span data-ttu-id="76b19-318">
</dt>
<dt>Categoría: &lt; Descripción de &gt; categoría , por ejemplo, cualquier tipo de amenaza o malware.</dt> 
<dt>Ruta de acceso: &lt; Usuario &gt; de ruta de</dt>
<dt>acceso de &lt; archivo: Dominio &gt; \& lt; User &gt; </dt>
<dt>Signature Version: &lt; Definition version &gt; </dt>Engine
<dt>Version: Antimalware Engine &lt; version &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="76b19-318">
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
<th colspan="2"><span data-ttu-id="76b19-319">Identificador de evento: 1010</span><span class="sxs-lookup"><span data-stu-id="76b19-319">Event ID: 1010</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="76b19-320">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="76b19-320">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="76b19-321">
<b>MALWAREPROTECTION_QUARANTINE_RESTORE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-321">
<b>MALWAREPROTECTION_QUARANTINE_RESTORE_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-322">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="76b19-322">Message:</span></span>
</td>
<td ><span data-ttu-id="76b19-323">
<b>La plataforma antimalware no pudo restaurar un elemento de cuarentena. </b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-323">
<b>The antimalware platform could not restore an item from quarantine. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-324">Descripción:</span><span class="sxs-lookup"><span data-stu-id="76b19-324">Description:</span></span>
</td>
<td >
<span data-ttu-id="76b19-325">Antivirus de Microsoft Defender ha encontrado un error al intentar restaurar un elemento desde la cuarentena.</span><span class="sxs-lookup"><span data-stu-id="76b19-325">Microsoft Defender Antivirus has encountered an error trying to restore an item from quarantine.</span></span> <span data-ttu-id="76b19-326">Para obtener más información, vea los artículos siguientes: </span><span class="sxs-lookup"><span data-stu-id="76b19-326">For more information, see the following:</span></span>
<dl><span data-ttu-id="76b19-327">
<dt>Nombre: &lt; Id. &gt; de</dt>
<dt>nombre de &lt; amenaza: Gravedad del id. &gt; </dt>de 
<dt> amenaza: gravedad , por &lt; &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="76b19-327">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="76b19-328">Bajo</span><span class="sxs-lookup"><span data-stu-id="76b19-328">Low</span></span></li>
<li><span data-ttu-id="76b19-329">Moderado</span><span class="sxs-lookup"><span data-stu-id="76b19-329">Moderate</span></span></li>
<li><span data-ttu-id="76b19-330">Alta</span><span class="sxs-lookup"><span data-stu-id="76b19-330">High</span></span></li>
<li><span data-ttu-id="76b19-331">Grave</span><span class="sxs-lookup"><span data-stu-id="76b19-331">Severe</span></span></li>
</ul><span data-ttu-id="76b19-332">
</dt>
<dt>Categoría: &lt; Descripción de &gt; categoría , por ejemplo, cualquier tipo de amenaza o malware.</dt> 
<dt>Ruta de acceso: &lt; Usuario &gt; de ruta de</dt>
<dt>acceso de &lt; archivo: Dominio &gt; \& lt; Código &gt; </dt>
<dt>de error del usuario: Código de error &lt; Código de resultado asociado con el estado de &gt; amenaza. Valores HRESULT estándar. </dt> 
<dt>Descripción del error: &lt; Descripción del error Descripción del &gt; error.</dt> 
<dt>Versión de firma: &lt; Versión &gt; de definición</dt>
<dt>Versión del motor: &lt; Antimalware Engine versión &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="76b19-332">
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
<th colspan="2"><span data-ttu-id="76b19-333">Identificador de evento: 1011</span><span class="sxs-lookup"><span data-stu-id="76b19-333">Event ID: 1011</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="76b19-334">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="76b19-334">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="76b19-335">
<b>MALWAREPROTECTION_QUARANTINE_DELETE</b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-335">
<b>MALWAREPROTECTION_QUARANTINE_DELETE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-336">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="76b19-336">Message:</span></span>
</td>
<td ><span data-ttu-id="76b19-337">
<b>La plataforma antimalware eliminó un elemento de la cuarentena. </b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-337">
<b>The antimalware platform deleted an item from quarantine. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-338">Descripción:</span><span class="sxs-lookup"><span data-stu-id="76b19-338">Description:</span></span>
</td>
<td >
<span data-ttu-id="76b19-339">Antivirus de Microsoft Defender ha eliminado un elemento de la cuarentena.</span><span class="sxs-lookup"><span data-stu-id="76b19-339">Microsoft Defender Antivirus has deleted an item from quarantine.</span></span><br/><span data-ttu-id="76b19-340">Para obtener más información, vea los artículos siguientes: </span><span class="sxs-lookup"><span data-stu-id="76b19-340">For more information, see the following:</span></span>
<dl><span data-ttu-id="76b19-341">
<dt>Nombre: &lt; Id. &gt; de</dt>
<dt>nombre de &lt; amenaza: Gravedad del id. &gt; </dt>de 
<dt> amenaza: gravedad , por &lt; &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="76b19-341">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="76b19-342">Bajo</span><span class="sxs-lookup"><span data-stu-id="76b19-342">Low</span></span></li>
<li><span data-ttu-id="76b19-343">Moderado</span><span class="sxs-lookup"><span data-stu-id="76b19-343">Moderate</span></span></li>
<li><span data-ttu-id="76b19-344">Alta</span><span class="sxs-lookup"><span data-stu-id="76b19-344">High</span></span></li>
<li><span data-ttu-id="76b19-345">Grave</span><span class="sxs-lookup"><span data-stu-id="76b19-345">Severe</span></span></li>
</ul><span data-ttu-id="76b19-346">
</dt>
<dt>Categoría: &lt; Descripción de &gt; categoría , por ejemplo, cualquier tipo de amenaza o malware.</dt> 
<dt>Ruta de acceso: &lt; Usuario &gt; de ruta de</dt>
<dt>acceso de &lt; archivo: Dominio &gt; \& lt; User &gt; </dt>
<dt>Signature Version: &lt; Definition version &gt; </dt>Engine
<dt>Version: Antimalware Engine &lt; version &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="76b19-346">
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
<th colspan="2"><span data-ttu-id="76b19-347">Identificador de evento: 1012</span><span class="sxs-lookup"><span data-stu-id="76b19-347">Event ID: 1012</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="76b19-348">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="76b19-348">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="76b19-349">
<b>MALWAREPROTECTION_QUARANTINE_DELETE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-349">
<b>MALWAREPROTECTION_QUARANTINE_DELETE_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-350">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="76b19-350">Message:</span></span>
</td>
<td ><span data-ttu-id="76b19-351">
<b>La plataforma antimalware no pudo eliminar un elemento de la cuarentena.</b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-351">
<b>The antimalware platform could not delete an item from quarantine.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-352">Descripción:</span><span class="sxs-lookup"><span data-stu-id="76b19-352">Description:</span></span>
</td>
<td >
<span data-ttu-id="76b19-353">Antivirus de Microsoft Defender ha encontrado un error al intentar eliminar un elemento de la cuarentena.</span><span class="sxs-lookup"><span data-stu-id="76b19-353">Microsoft Defender Antivirus has encountered an error trying to delete an item from quarantine.</span></span>
<span data-ttu-id="76b19-354">Para obtener más información, vea los artículos siguientes: </span><span class="sxs-lookup"><span data-stu-id="76b19-354">For more information, see the following:</span></span>
<dl><span data-ttu-id="76b19-355">
<dt>Nombre: &lt; Id. &gt; de</dt>
<dt>nombre de &lt; amenaza: Gravedad del id. &gt; </dt>de 
<dt> amenaza: gravedad , por &lt; &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="76b19-355">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="76b19-356">Bajo</span><span class="sxs-lookup"><span data-stu-id="76b19-356">Low</span></span></li>
<li><span data-ttu-id="76b19-357">Moderado</span><span class="sxs-lookup"><span data-stu-id="76b19-357">Moderate</span></span></li>
<li><span data-ttu-id="76b19-358">Alta</span><span class="sxs-lookup"><span data-stu-id="76b19-358">High</span></span></li>
<li><span data-ttu-id="76b19-359">Grave</span><span class="sxs-lookup"><span data-stu-id="76b19-359">Severe</span></span></li>
</ul><span data-ttu-id="76b19-360">
</dt>
<dt>Categoría: &lt; Descripción de &gt; categoría , por ejemplo, cualquier tipo de amenaza o malware.</dt> 
<dt>Ruta de acceso: &lt; Usuario &gt; de ruta de</dt>
<dt>acceso de &lt; archivo: Dominio &gt; \& lt; Código &gt; </dt>
<dt>de error del usuario: Código de error &lt; Código de resultado asociado con el estado de &gt; amenaza. Valores HRESULT estándar. </dt> 
<dt>Descripción del error: &lt; Descripción del error Descripción del &gt; error.</dt> 
<dt>Versión de firma: &lt; Versión &gt; de definición</dt>
<dt>Versión del motor: &lt; Antimalware Engine versión &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="76b19-360">
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
<th colspan="2"><span data-ttu-id="76b19-361">Identificador de evento: 1013</span><span class="sxs-lookup"><span data-stu-id="76b19-361">Event ID: 1013</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="76b19-362">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="76b19-362">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="76b19-363">
<b>MALWAREPROTECTION_MALWARE_HISTORY_DELETE </b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-363">
<b>MALWAREPROTECTION_MALWARE_HISTORY_DELETE </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-364">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="76b19-364">Message:</span></span>
</td>
<td ><span data-ttu-id="76b19-365">
<b>La plataforma antimalware eliminó el historial de malware y otro software potencialmente no deseado.</b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-365">
<b>The antimalware platform deleted history of malware and other potentially unwanted software.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-366">Descripción:</span><span class="sxs-lookup"><span data-stu-id="76b19-366">Description:</span></span>
</td>
<td >
<span data-ttu-id="76b19-367">Antivirus de Microsoft Defender ha eliminado el historial de malware y otro software potencialmente no deseado.</span><span class="sxs-lookup"><span data-stu-id="76b19-367">Microsoft Defender Antivirus has removed history of malware and other potentially unwanted software.</span></span>
<dl><span data-ttu-id="76b19-368">
<dt>Hora: hora en la que se produjo el evento, por ejemplo, cuando se purga el historial. Este parámetro no se usa en eventos de amenazas para que no haya confusión con respecto a si es tiempo de corrección o tiempo de infección. Para ellos, los llamamos específicamente tiempo de acción o tiempo de detección.</dt> 
<dt>Usuario: &lt; Dominio &gt; \& lt; Usuario &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="76b19-368">
<dt>Time: The time when the event occurred, for example when the history is purged. This parameter is not used in threat events so that there is no confusion regarding whether it is remediation time or infection time. For those, we specifically call them as Action Time or Detection Time.</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="76b19-369">Identificador de evento: 1014</span><span class="sxs-lookup"><span data-stu-id="76b19-369">Event ID: 1014</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="76b19-370">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="76b19-370">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="76b19-371">
<b>MALWAREPROTECTION_MALWARE_HISTORY_DELETE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-371">
<b>MALWAREPROTECTION_MALWARE_HISTORY_DELETE_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-372">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="76b19-372">Message:</span></span>
</td>
<td >
<span data-ttu-id="76b19-373">La plataforma antimalware no pudo eliminar el historial de malware y otro software potencialmente no deseado.</span><span class="sxs-lookup"><span data-stu-id="76b19-373">The antimalware platform could not delete history of malware and other potentially unwanted software.</span></span>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-374">Descripción:</span><span class="sxs-lookup"><span data-stu-id="76b19-374">Description:</span></span>
</td>
<td >
<span data-ttu-id="76b19-375">Antivirus de Microsoft Defender ha encontrado un error al intentar quitar el historial de malware y otro software potencialmente no deseado.</span><span class="sxs-lookup"><span data-stu-id="76b19-375">Microsoft Defender Antivirus has encountered an error trying to remove history of malware and other potentially unwanted software.</span></span>
<dl><span data-ttu-id="76b19-376">
<dt>Hora: hora en la que se produjo el evento, por ejemplo, cuando se purga el historial. Este parámetro no se usa en eventos de amenazas para que no haya confusión con respecto a si es tiempo de corrección o tiempo de infección. Para ellos, los llamamos específicamente tiempo de acción o tiempo de detección.</dt> 
<dt>Usuario: &lt; Dominio &gt; \& lt; Código &gt; </dt>
<dt>de error del usuario: Código de error &lt; Código de resultado asociado con el estado de &gt; amenaza. Valores HRESULT estándar. </dt> 
<dt>Descripción del error: &lt; Descripción del error Descripción del &gt; error.</dt>
</span><span class="sxs-lookup"><span data-stu-id="76b19-376">
<dt>Time: The time when the event occurred, for example when the history is purged. This parameter is not used in threat events so that there is no confusion regarding whether it is remediation time or infection time. For those, we specifically call them as Action Time or Detection Time.</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values. </dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="76b19-377">Identificador de evento: 1015</span><span class="sxs-lookup"><span data-stu-id="76b19-377">Event ID: 1015</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="76b19-378">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="76b19-378">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="76b19-379">
<b>MALWAREPROTECTION_BEHAVIOR_DETECTED </b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-379">
<b>MALWAREPROTECTION_BEHAVIOR_DETECTED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-380">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="76b19-380">Message:</span></span>
</td>
<td ><span data-ttu-id="76b19-381">
<b>La plataforma antimalware detectó un comportamiento sospechoso.</b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-381">
<b>The antimalware platform detected suspicious behavior.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-382">Descripción:</span><span class="sxs-lookup"><span data-stu-id="76b19-382">Description:</span></span>
</td>
<td >
<span data-ttu-id="76b19-383">Antivirus de Microsoft Defender ha detectado un comportamiento sospechoso.</span><span class="sxs-lookup"><span data-stu-id="76b19-383">Microsoft Defender Antivirus has detected a suspicious behavior.</span></span><br/><span data-ttu-id="76b19-384">Para obtener más información, vea los artículos siguientes: </span><span class="sxs-lookup"><span data-stu-id="76b19-384">For more information, see the following:</span></span>
<dl><span data-ttu-id="76b19-385">
<dt>Nombre: &lt; Id. &gt; de</dt>
<dt>nombre de &lt; amenaza: Gravedad del id. &gt; </dt>de 
<dt> amenaza: gravedad , por &lt; &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="76b19-385">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="76b19-386">Bajo</span><span class="sxs-lookup"><span data-stu-id="76b19-386">Low</span></span></li>
<li><span data-ttu-id="76b19-387">Moderado</span><span class="sxs-lookup"><span data-stu-id="76b19-387">Moderate</span></span></li>
<li><span data-ttu-id="76b19-388">Alta</span><span class="sxs-lookup"><span data-stu-id="76b19-388">High</span></span></li>
<li><span data-ttu-id="76b19-389">Grave</span><span class="sxs-lookup"><span data-stu-id="76b19-389">Severe</span></span></li>
</ul><span data-ttu-id="76b19-390">
</dt>
<dt>Categoría: &lt; Descripción de &gt; categoría , por ejemplo, cualquier tipo de amenaza o malware.</dt> 
<dt>Ruta de acceso: &lt; Origen &gt; de detección</dt>de ruta de 
<dt> acceso de &lt; archivo: Origen de &gt; detección, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="76b19-390">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="76b19-391">Unknown</span><span class="sxs-lookup"><span data-stu-id="76b19-391">Unknown</span></span></li>
<li><span data-ttu-id="76b19-392">Equipo local</span><span class="sxs-lookup"><span data-stu-id="76b19-392">Local computer</span></span></li>
<li><span data-ttu-id="76b19-393">Recurso compartido de red</span><span class="sxs-lookup"><span data-stu-id="76b19-393">Network share</span></span></li>
<li><span data-ttu-id="76b19-394">Internet</span><span class="sxs-lookup"><span data-stu-id="76b19-394">Internet</span></span></li>
<li><span data-ttu-id="76b19-395">Tráfico entrante</span><span class="sxs-lookup"><span data-stu-id="76b19-395">Incoming traffic</span></span></li>
<li><span data-ttu-id="76b19-396">Tráfico saliente</span><span class="sxs-lookup"><span data-stu-id="76b19-396">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="76b19-397">
</dt>
<dt>Tipo de &lt; detección: Tipo de &gt; detección , por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="76b19-397">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="76b19-398">Heurística</span><span class="sxs-lookup"><span data-stu-id="76b19-398">Heuristics</span></span></li>
<li><span data-ttu-id="76b19-399">Generic</span><span class="sxs-lookup"><span data-stu-id="76b19-399">Generic</span></span></li>
<li><span data-ttu-id="76b19-400">Concreto</span><span class="sxs-lookup"><span data-stu-id="76b19-400">Concrete</span></span></li>
<li><span data-ttu-id="76b19-401">Firma dinámica</span><span class="sxs-lookup"><span data-stu-id="76b19-401">Dynamic signature</span></span></li>
</ul><span data-ttu-id="76b19-402">
</dt>
<dt>Origen de &lt; detección: origen de &gt; detección por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="76b19-402">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="76b19-403">Usuario: usuario iniciado</span><span class="sxs-lookup"><span data-stu-id="76b19-403">User: user initiated</span></span></li>
<li><span data-ttu-id="76b19-404">Sistema: sistema iniciado</span><span class="sxs-lookup"><span data-stu-id="76b19-404">System: system initiated</span></span></li>
<li><span data-ttu-id="76b19-405">En tiempo real: componente en tiempo real iniciado</span><span class="sxs-lookup"><span data-stu-id="76b19-405">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="76b19-406">IOAV: Descargas de IE y Outlook datos adjuntos de Express iniciados</span><span class="sxs-lookup"><span data-stu-id="76b19-406">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="76b19-407">NIS: sistema de inspección de red</span><span class="sxs-lookup"><span data-stu-id="76b19-407">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="76b19-408">IEPROTECT: IE - IExtensionValidation; esto protege contra controles de páginas web malintencionadas</span><span class="sxs-lookup"><span data-stu-id="76b19-408">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="76b19-409">Antimalware de inicio anticipado (ELAM).</span><span class="sxs-lookup"><span data-stu-id="76b19-409">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="76b19-410">Esto incluye malware detectado por la secuencia de arranque</span><span class="sxs-lookup"><span data-stu-id="76b19-410">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="76b19-411">Atestación remota</span><span class="sxs-lookup"><span data-stu-id="76b19-411">Remote attestation</span></span></li>
</ul><span data-ttu-id="76b19-412">Interfaz de examen antimalware (AMSI).</span><span class="sxs-lookup"><span data-stu-id="76b19-412">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="76b19-413">Se usa principalmente para proteger scripts (PS, VBS), aunque también pueden invocarse por terceros.</span><span class="sxs-lookup"><span data-stu-id="76b19-413">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="76b19-414">Estado de </dt> 
<dt>UAC: Usuario &lt; &gt; de</dt>
<dt>estado: Dominio &lt; &gt; \& lt; Nombre &gt; </dt>del proceso de usuario: proceso en el identificador de firma
<dt> &lt; &gt; PID:</dt>
<dt>Gravedad de coincidencia de enumeración.</dt> 
<dt>Versión de firma: &lt; Versión &gt; de definición</dt>Versión del
<dt> &lt; motor: &gt; Antimalware Engine versión Fidelity</dt>
<dt>Label:</dt>Nombre del archivo de
<dt>destino: Nombre de archivo del &lt; &gt; archivo.</dt>
</span><span class="sxs-lookup"><span data-stu-id="76b19-414">UAC</dt>
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
<th colspan="2"><span data-ttu-id="76b19-415">Identificador de evento: 1116</span><span class="sxs-lookup"><span data-stu-id="76b19-415">Event ID: 1116</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="76b19-416">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="76b19-416">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="76b19-417">
<b>MALWAREPROTECTION_STATE_MALWARE_DETECTED</b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-417">
<b>MALWAREPROTECTION_STATE_MALWARE_DETECTED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-418">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="76b19-418">Message:</span></span>
</td>
<td ><span data-ttu-id="76b19-419">
<b>La plataforma antimalware detectó malware u otro software potencialmente no deseado. </b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-419">
<b>The antimalware platform detected malware or other potentially unwanted software. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-420">Descripción:</span><span class="sxs-lookup"><span data-stu-id="76b19-420">Description:</span></span>
</td>
<td >
<span data-ttu-id="76b19-421">Antivirus de Microsoft Defender ha detectado malware u otro software potencialmente no deseado.</span><span class="sxs-lookup"><span data-stu-id="76b19-421">Microsoft Defender Antivirus has detected malware or other potentially unwanted software.</span></span><br/><span data-ttu-id="76b19-422">Para obtener más información, vea los artículos siguientes: </span><span class="sxs-lookup"><span data-stu-id="76b19-422">For more information, see the following:</span></span>
<dl><span data-ttu-id="76b19-423">
<dt>Nombre: &lt; Id. &gt; de</dt>
<dt>nombre de &lt; amenaza: Gravedad del id. &gt; </dt>de 
<dt> amenaza: gravedad , por &lt; &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="76b19-423">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="76b19-424">Bajo</span><span class="sxs-lookup"><span data-stu-id="76b19-424">Low</span></span></li>
<li><span data-ttu-id="76b19-425">Moderado</span><span class="sxs-lookup"><span data-stu-id="76b19-425">Moderate</span></span></li>
<li><span data-ttu-id="76b19-426">Alta</span><span class="sxs-lookup"><span data-stu-id="76b19-426">High</span></span></li>
<li><span data-ttu-id="76b19-427">Grave</span><span class="sxs-lookup"><span data-stu-id="76b19-427">Severe</span></span></li>
</ul><span data-ttu-id="76b19-428">
</dt>
<dt>Categoría: &lt; Descripción de &gt; categoría , por ejemplo, cualquier tipo de amenaza o malware.</dt> 
<dt>Ruta de acceso: &lt; Origen &gt; de detección</dt>de ruta de 
<dt> acceso de &lt; archivo: Origen de &gt; detección, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="76b19-428">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="76b19-429">Unknown</span><span class="sxs-lookup"><span data-stu-id="76b19-429">Unknown</span></span></li>
<li><span data-ttu-id="76b19-430">Equipo local</span><span class="sxs-lookup"><span data-stu-id="76b19-430">Local computer</span></span></li>
<li><span data-ttu-id="76b19-431">Recurso compartido de red</span><span class="sxs-lookup"><span data-stu-id="76b19-431">Network share</span></span></li>
<li><span data-ttu-id="76b19-432">Internet</span><span class="sxs-lookup"><span data-stu-id="76b19-432">Internet</span></span></li>
<li><span data-ttu-id="76b19-433">Tráfico entrante</span><span class="sxs-lookup"><span data-stu-id="76b19-433">Incoming traffic</span></span></li>
<li><span data-ttu-id="76b19-434">Tráfico saliente</span><span class="sxs-lookup"><span data-stu-id="76b19-434">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="76b19-435">
</dt>
<dt>Tipo de &lt; detección: Tipo de &gt; detección , por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="76b19-435">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="76b19-436">Heurística</span><span class="sxs-lookup"><span data-stu-id="76b19-436">Heuristics</span></span></li>
<li><span data-ttu-id="76b19-437">Generic</span><span class="sxs-lookup"><span data-stu-id="76b19-437">Generic</span></span></li>
<li><span data-ttu-id="76b19-438">Concreto</span><span class="sxs-lookup"><span data-stu-id="76b19-438">Concrete</span></span></li>
<li><span data-ttu-id="76b19-439">Firma dinámica</span><span class="sxs-lookup"><span data-stu-id="76b19-439">Dynamic signature</span></span></li>
</ul><span data-ttu-id="76b19-440">
</dt>
<dt>Origen de &lt; detección: origen de &gt; detección por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="76b19-440">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="76b19-441">Usuario: usuario iniciado</span><span class="sxs-lookup"><span data-stu-id="76b19-441">User: user initiated</span></span></li>
<li><span data-ttu-id="76b19-442">Sistema: sistema iniciado</span><span class="sxs-lookup"><span data-stu-id="76b19-442">System: system initiated</span></span></li>
<li><span data-ttu-id="76b19-443">En tiempo real: componente en tiempo real iniciado</span><span class="sxs-lookup"><span data-stu-id="76b19-443">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="76b19-444">IOAV: Descargas de IE y Outlook datos adjuntos de Express iniciados</span><span class="sxs-lookup"><span data-stu-id="76b19-444">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="76b19-445">NIS: sistema de inspección de red</span><span class="sxs-lookup"><span data-stu-id="76b19-445">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="76b19-446">IEPROTECT: IE - IExtensionValidation; esto protege contra controles de páginas web malintencionadas</span><span class="sxs-lookup"><span data-stu-id="76b19-446">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="76b19-447">Antimalware de inicio anticipado (ELAM).</span><span class="sxs-lookup"><span data-stu-id="76b19-447">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="76b19-448">Esto incluye malware detectado por la secuencia de arranque</span><span class="sxs-lookup"><span data-stu-id="76b19-448">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="76b19-449">Atestación remota</span><span class="sxs-lookup"><span data-stu-id="76b19-449">Remote attestation</span></span></li>
</ul><span data-ttu-id="76b19-450">Interfaz de examen antimalware (AMSI).</span><span class="sxs-lookup"><span data-stu-id="76b19-450">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="76b19-451">Se usa principalmente para proteger scripts (PS, VBS), aunque también pueden invocarse por terceros.</span><span class="sxs-lookup"><span data-stu-id="76b19-451">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="76b19-452">Usuario de </dt> 
<dt>UAC: Dominio &lt; &gt; \& lt; Nombre &gt; </dt>del proceso de usuario: proceso en la versión de firma
<dt> &lt; &gt; PID:</dt>versión de
<dt> &lt; definición &gt; </dt>Versión del
<dt>motor: Antimalware Engine &lt; versión &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="76b19-452">UAC</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-453">Acción del usuario:</span><span class="sxs-lookup"><span data-stu-id="76b19-453">User action:</span></span>
</td>
<td >
<span data-ttu-id="76b19-454">No se requiere ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="76b19-454">No action is required.</span></span> <span data-ttu-id="76b19-455">Antivirus de Microsoft Defender suspender y tomar medidas rutinarias en esta amenaza.</span><span class="sxs-lookup"><span data-stu-id="76b19-455">Microsoft Defender Antivirus can suspend and take routine action on this threat.</span></span> <span data-ttu-id="76b19-456">Si desea quitar la amenaza manualmente, en la interfaz Antivirus de Microsoft Defender, haga clic en <b>Limpiar equipo</b>.</span><span class="sxs-lookup"><span data-stu-id="76b19-456">If you want to remove the threat manually, in the Microsoft Defender Antivirus interface, click <b>Clean Computer</b>.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="76b19-457">Identificador de evento: 1117</span><span class="sxs-lookup"><span data-stu-id="76b19-457">Event ID: 1117</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="76b19-458">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="76b19-458">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="76b19-459">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_TAKEN </b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-459">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_TAKEN </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-460">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="76b19-460">Message:</span></span>
</td>
<td ><span data-ttu-id="76b19-461">
<b>La plataforma antimalware realizó una acción para proteger el sistema de malware u otro software potencialmente no deseado. </b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-461">
<b>The antimalware platform performed an action to protect your system from malware or other potentially unwanted software. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-462">Descripción:</span><span class="sxs-lookup"><span data-stu-id="76b19-462">Description:</span></span>
</td>
<td >
<span data-ttu-id="76b19-463">Antivirus de Microsoft Defender ha tomado medidas para proteger esta máquina de malware u otro software potencialmente no deseado.</span><span class="sxs-lookup"><span data-stu-id="76b19-463">Microsoft Defender Antivirus has taken action to protect this machine from malware or other potentially unwanted software.</span></span><br/><span data-ttu-id="76b19-464">Para obtener más información, vea los artículos siguientes: </span><span class="sxs-lookup"><span data-stu-id="76b19-464">For more information, see the following:</span></span>
<dl><span data-ttu-id="76b19-465">
<dt>Nombre: &lt; Id. &gt; de</dt>
<dt>nombre de &lt; amenaza: Gravedad del id. &gt; </dt>de 
<dt> amenaza: gravedad , por &lt; &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="76b19-465">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="76b19-466">Bajo</span><span class="sxs-lookup"><span data-stu-id="76b19-466">Low</span></span></li>
<li><span data-ttu-id="76b19-467">Moderado</span><span class="sxs-lookup"><span data-stu-id="76b19-467">Moderate</span></span></li>
<li><span data-ttu-id="76b19-468">Alta</span><span class="sxs-lookup"><span data-stu-id="76b19-468">High</span></span></li>
<li><span data-ttu-id="76b19-469">Grave</span><span class="sxs-lookup"><span data-stu-id="76b19-469">Severe</span></span></li>
</ul><span data-ttu-id="76b19-470">
</dt>
<dt>Categoría: &lt; Descripción de &gt; categoría , por ejemplo, cualquier tipo de amenaza o malware.</dt> 
<dt>Ruta de acceso: &lt; Origen &gt; de detección</dt>de ruta de 
<dt> acceso de &lt; archivo: Origen de &gt; detección, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="76b19-470">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="76b19-471">Unknown</span><span class="sxs-lookup"><span data-stu-id="76b19-471">Unknown</span></span></li>
<li><span data-ttu-id="76b19-472">Equipo local</span><span class="sxs-lookup"><span data-stu-id="76b19-472">Local computer</span></span></li>
<li><span data-ttu-id="76b19-473">Recurso compartido de red</span><span class="sxs-lookup"><span data-stu-id="76b19-473">Network share</span></span></li>
<li><span data-ttu-id="76b19-474">Internet</span><span class="sxs-lookup"><span data-stu-id="76b19-474">Internet</span></span></li>
<li><span data-ttu-id="76b19-475">Tráfico entrante</span><span class="sxs-lookup"><span data-stu-id="76b19-475">Incoming traffic</span></span></li>
<li><span data-ttu-id="76b19-476">Tráfico saliente</span><span class="sxs-lookup"><span data-stu-id="76b19-476">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="76b19-477">
</dt>
<dt>Tipo de &lt; detección: Tipo de &gt; detección , por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="76b19-477">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="76b19-478">Heurística</span><span class="sxs-lookup"><span data-stu-id="76b19-478">Heuristics</span></span></li>
<li><span data-ttu-id="76b19-479">Generic</span><span class="sxs-lookup"><span data-stu-id="76b19-479">Generic</span></span></li>
<li><span data-ttu-id="76b19-480">Concreto</span><span class="sxs-lookup"><span data-stu-id="76b19-480">Concrete</span></span></li>
<li><span data-ttu-id="76b19-481">Firma dinámica</span><span class="sxs-lookup"><span data-stu-id="76b19-481">Dynamic signature</span></span></li>
</ul><span data-ttu-id="76b19-482">
</dt>
<dt>Origen de &lt; detección: origen de &gt; detección por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="76b19-482">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="76b19-483">Usuario: usuario iniciado</span><span class="sxs-lookup"><span data-stu-id="76b19-483">User: user initiated</span></span></li>
<li><span data-ttu-id="76b19-484">Sistema: sistema iniciado</span><span class="sxs-lookup"><span data-stu-id="76b19-484">System: system initiated</span></span></li>
<li><span data-ttu-id="76b19-485">En tiempo real: componente en tiempo real iniciado</span><span class="sxs-lookup"><span data-stu-id="76b19-485">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="76b19-486">IOAV: Descargas de IE y Outlook datos adjuntos de Express iniciados</span><span class="sxs-lookup"><span data-stu-id="76b19-486">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="76b19-487">NIS: sistema de inspección de red</span><span class="sxs-lookup"><span data-stu-id="76b19-487">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="76b19-488">IEPROTECT: IE - IExtensionValidation; esto protege contra controles de páginas web malintencionadas</span><span class="sxs-lookup"><span data-stu-id="76b19-488">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="76b19-489">Antimalware de inicio anticipado (ELAM).</span><span class="sxs-lookup"><span data-stu-id="76b19-489">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="76b19-490">Esto incluye malware detectado por la secuencia de arranque</span><span class="sxs-lookup"><span data-stu-id="76b19-490">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="76b19-491">Atestación remota</span><span class="sxs-lookup"><span data-stu-id="76b19-491">Remote attestation</span></span></li>
</ul><span data-ttu-id="76b19-492">Interfaz de examen antimalware (AMSI).</span><span class="sxs-lookup"><span data-stu-id="76b19-492">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="76b19-493">Se usa principalmente para proteger scripts (PS, VBS), aunque también pueden invocarse por terceros.</span><span class="sxs-lookup"><span data-stu-id="76b19-493">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="76b19-494">Usuario de </dt> 
<dt>UAC: Dominio &lt; &gt; \& lt; Nombre &gt; </dt>
<dt>del proceso de usuario: Proceso en la &lt; acción &gt; pid:</dt>Acción , por 
<dt> &lt; &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="76b19-494">UAC</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Action: &lt;Action&gt;, for example:</span></span><ul>
<li><span data-ttu-id="76b19-495">Clean: el recurso se ha limpiado</span><span class="sxs-lookup"><span data-stu-id="76b19-495">Clean: The resource was cleaned</span></span></li>
<li><span data-ttu-id="76b19-496">Cuarentena: el recurso se ha puesto en cuarentena</span><span class="sxs-lookup"><span data-stu-id="76b19-496">Quarantine: The resource was quarantined</span></span></li>
<li><span data-ttu-id="76b19-497">Quitar: se eliminó el recurso</span><span class="sxs-lookup"><span data-stu-id="76b19-497">Remove: The resource was deleted</span></span></li>
<li><span data-ttu-id="76b19-498">Permitir: se permitió que el recurso se ejecutara o existiera</span><span class="sxs-lookup"><span data-stu-id="76b19-498">Allow: The resource was allowed to execute/exist</span></span></li>
<li><span data-ttu-id="76b19-499">Definido por el usuario: acción definida por el usuario que normalmente es una de esta lista de acciones que el usuario ha especificado</span><span class="sxs-lookup"><span data-stu-id="76b19-499">User defined: User-defined action that is normally one from this list of actions that the user has specified</span></span></li>
<li><span data-ttu-id="76b19-500">Sin acción: sin acción</span><span class="sxs-lookup"><span data-stu-id="76b19-500">No action: No action</span></span></li>
<li><span data-ttu-id="76b19-501">Bloquear: se bloqueó el recurso para que no se ejecutara</span><span class="sxs-lookup"><span data-stu-id="76b19-501">Block: The resource was blocked from executing</span></span></li>
</ul><span data-ttu-id="76b19-502">
</dt>
<dt>Estado de la acción: &lt; Descripción de &gt; acciones adicionales</dt>
<dt>Código de error: &lt; Código de error Código de resultado asociado con el estado de &gt; amenaza. Valores HRESULT estándar.</dt> 
<dt>Descripción del error: &lt; Descripción del error &gt; Descripción del error.</dt> 
<dt>Versión de firma: &lt; &gt;</dt>Versión de definición Versión del
<dt>motor: &lt; Antimalware Engine &gt; </dt> versión NOTA: siempre que Antivirus de Microsoft Defender, Microsoft Security Essentials, Herramienta de eliminación de software malintencionado o System Center Endpoint Protection detecte un malware, restaurará la siguiente configuración del sistema y los servicios que el malware podría haber cambiado:</span><span class="sxs-lookup"><span data-stu-id="76b19-502">
</dt>
<dt>Action Status: &lt;Description of additional actions&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt> NOTE: Whenever Microsoft Defender Antivirus, Microsoft Security Essentials, Malicious Software Removal Tool, or System Center Endpoint Protection detects a malware, it will restore the following system settings and services that the malware might have changed:</span></span><ul>
<li><span data-ttu-id="76b19-503">Configuración predeterminada de Internet Explorer o Microsoft Edge configuración</span><span class="sxs-lookup"><span data-stu-id="76b19-503">Default Internet Explorer or Microsoft Edge setting</span></span></li>
<li><span data-ttu-id="76b19-504">Configuración del control de acceso de usuario</span><span class="sxs-lookup"><span data-stu-id="76b19-504">User Access Control settings</span></span></li>
<li><span data-ttu-id="76b19-505">Configuración de Chrome</span><span class="sxs-lookup"><span data-stu-id="76b19-505">Chrome settings</span></span></li>
<li><span data-ttu-id="76b19-506">Datos de control de arranque</span><span class="sxs-lookup"><span data-stu-id="76b19-506">Boot Control Data</span></span></li>
<li><span data-ttu-id="76b19-507">Configuración del Registro regedit y administrador de tareas</span><span class="sxs-lookup"><span data-stu-id="76b19-507">Regedit and Task Manager registry settings</span></span></li>
<li><span data-ttu-id="76b19-508">Windows Actualización, servicio de transferencia inteligente en segundo plano y servicio de llamadas de procedimiento remoto</span><span class="sxs-lookup"><span data-stu-id="76b19-508">Windows Update, Background Intelligent Transfer Service, and Remote Procedure Call service</span></span></li>
<li><span data-ttu-id="76b19-509">Windows Archivos del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="76b19-509">Windows Operating System files</span></span></li></ul>
<span data-ttu-id="76b19-510">El contexto anterior se aplica a las siguientes versiones de cliente y servidor:</span><span class="sxs-lookup"><span data-stu-id="76b19-510">The above context applies to the following client and server versions:</span></span>
<table>
<tr>
<th><span data-ttu-id="76b19-511">Sistema operativo</span><span class="sxs-lookup"><span data-stu-id="76b19-511">Operating system</span></span></th>
<th><span data-ttu-id="76b19-512">Versión del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="76b19-512">Operating system version</span></span></th>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-513">Sistema operativo cliente</span><span class="sxs-lookup"><span data-stu-id="76b19-513">Client Operating System</span></span>
</td>
<td>
<span data-ttu-id="76b19-514">Windows Vista (Service Pack 1 o Service Pack 2), Windows 7 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="76b19-514">Windows Vista (Service Pack 1, or Service Pack 2), Windows 7 and later</span></span>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-515">Sistema operativo del servidor</span><span class="sxs-lookup"><span data-stu-id="76b19-515">Server Operating System</span></span>
</td>
<td>
<span data-ttu-id="76b19-516">Windows Server 2008, Windows Server 2008 R2, Windows Server 2012 y Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="76b19-516">Windows Server 2008, Windows Server 2008 R2, Windows Server 2012, and Windows Server 2016</span></span>
</td>
</tr>
</table>
</dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-517">Acción del usuario:</span><span class="sxs-lookup"><span data-stu-id="76b19-517">User action:</span></span>
</td>
<td >
<span data-ttu-id="76b19-518">No es necesario realizar ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="76b19-518">No action is necessary.</span></span> <span data-ttu-id="76b19-519">Antivirus de Microsoft Defender o ha puesto en cuarentena una amenaza.</span><span class="sxs-lookup"><span data-stu-id="76b19-519">Microsoft Defender Antivirus removed or quarantined a threat.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="76b19-520">Identificador de evento: 1118</span><span class="sxs-lookup"><span data-stu-id="76b19-520">Event ID: 1118</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="76b19-521">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="76b19-521">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="76b19-522">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-522">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-523">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="76b19-523">Message:</span></span>
</td>
<td ><span data-ttu-id="76b19-524">
<b>La plataforma antimalware intentó realizar una acción para proteger el sistema de malware u otro software potencialmente no deseado, pero la acción falló. </b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-524">
<b>The antimalware platform attempted to perform an action to protect your system from malware or other potentially unwanted software, but the action failed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-525">Descripción:</span><span class="sxs-lookup"><span data-stu-id="76b19-525">Description:</span></span>
</td>
<td >
<span data-ttu-id="76b19-526">Antivirus de Microsoft Defender ha encontrado un error no crítico al tomar medidas en malware u otro software potencialmente no deseado.</span><span class="sxs-lookup"><span data-stu-id="76b19-526">Microsoft Defender Antivirus has encountered a non-critical error when taking action on malware or other potentially unwanted software.</span></span><br/><span data-ttu-id="76b19-527">Para obtener más información, vea los artículos siguientes: </span><span class="sxs-lookup"><span data-stu-id="76b19-527">For more information, see the following:</span></span>
<dl><span data-ttu-id="76b19-528">
<dt>Nombre: &lt; Id. &gt; de</dt>
<dt>nombre de &lt; amenaza: Gravedad del id. &gt; </dt>de 
<dt> amenaza: gravedad , por &lt; &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="76b19-528">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="76b19-529">Bajo</span><span class="sxs-lookup"><span data-stu-id="76b19-529">Low</span></span></li>
<li><span data-ttu-id="76b19-530">Moderado</span><span class="sxs-lookup"><span data-stu-id="76b19-530">Moderate</span></span></li>
<li><span data-ttu-id="76b19-531">Alta</span><span class="sxs-lookup"><span data-stu-id="76b19-531">High</span></span></li>
<li><span data-ttu-id="76b19-532">Grave</span><span class="sxs-lookup"><span data-stu-id="76b19-532">Severe</span></span></li>
</ul><span data-ttu-id="76b19-533">
</dt>
<dt>Categoría: &lt; Descripción de &gt; categoría , por ejemplo, cualquier tipo de amenaza o malware.</dt> 
<dt>Ruta de acceso: &lt; Origen &gt; de detección</dt>de ruta de 
<dt> acceso de &lt; archivo: Origen de &gt; detección, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="76b19-533">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="76b19-534">Unknown</span><span class="sxs-lookup"><span data-stu-id="76b19-534">Unknown</span></span></li>
<li><span data-ttu-id="76b19-535">Equipo local</span><span class="sxs-lookup"><span data-stu-id="76b19-535">Local computer</span></span></li>
<li><span data-ttu-id="76b19-536">Recurso compartido de red</span><span class="sxs-lookup"><span data-stu-id="76b19-536">Network share</span></span></li>
<li><span data-ttu-id="76b19-537">Internet</span><span class="sxs-lookup"><span data-stu-id="76b19-537">Internet</span></span></li>
<li><span data-ttu-id="76b19-538">Tráfico entrante</span><span class="sxs-lookup"><span data-stu-id="76b19-538">Incoming traffic</span></span></li>
<li><span data-ttu-id="76b19-539">Tráfico saliente</span><span class="sxs-lookup"><span data-stu-id="76b19-539">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="76b19-540">
</dt>
<dt>Tipo de &lt; detección: Tipo de &gt; detección , por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="76b19-540">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="76b19-541">Heurística</span><span class="sxs-lookup"><span data-stu-id="76b19-541">Heuristics</span></span></li>
<li><span data-ttu-id="76b19-542">Generic</span><span class="sxs-lookup"><span data-stu-id="76b19-542">Generic</span></span></li>
<li><span data-ttu-id="76b19-543">Concreto</span><span class="sxs-lookup"><span data-stu-id="76b19-543">Concrete</span></span></li>
<li><span data-ttu-id="76b19-544">Firma dinámica</span><span class="sxs-lookup"><span data-stu-id="76b19-544">Dynamic signature</span></span></li>
</ul><span data-ttu-id="76b19-545">
</dt>
<dt>Origen de &lt; detección: origen de &gt; detección por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="76b19-545">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="76b19-546">Usuario: usuario iniciado</span><span class="sxs-lookup"><span data-stu-id="76b19-546">User: user initiated</span></span></li>
<li><span data-ttu-id="76b19-547">Sistema: sistema iniciado</span><span class="sxs-lookup"><span data-stu-id="76b19-547">System: system initiated</span></span></li>
<li><span data-ttu-id="76b19-548">En tiempo real: componente en tiempo real iniciado</span><span class="sxs-lookup"><span data-stu-id="76b19-548">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="76b19-549">IOAV: Descargas de IE y Outlook datos adjuntos de Express iniciados</span><span class="sxs-lookup"><span data-stu-id="76b19-549">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="76b19-550">NIS: sistema de inspección de red</span><span class="sxs-lookup"><span data-stu-id="76b19-550">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="76b19-551">IEPROTECT: IE - IExtensionValidation; esto protege contra controles de páginas web malintencionadas</span><span class="sxs-lookup"><span data-stu-id="76b19-551">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="76b19-552">Antimalware de inicio anticipado (ELAM).</span><span class="sxs-lookup"><span data-stu-id="76b19-552">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="76b19-553">Esto incluye malware detectado por la secuencia de arranque</span><span class="sxs-lookup"><span data-stu-id="76b19-553">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="76b19-554">Atestación remota</span><span class="sxs-lookup"><span data-stu-id="76b19-554">Remote attestation</span></span></li>
</ul><span data-ttu-id="76b19-555">Interfaz de examen antimalware (AMSI).</span><span class="sxs-lookup"><span data-stu-id="76b19-555">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="76b19-556">Se usa principalmente para proteger scripts (PS, VBS), aunque también pueden invocarse por terceros.</span><span class="sxs-lookup"><span data-stu-id="76b19-556">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="76b19-557">Usuario de </dt> 
<dt>UAC: Dominio &lt; &gt; \& lt; Nombre &gt; </dt>
<dt>del proceso de usuario: Proceso en la &lt; acción &gt; pid:</dt>Acción , por 
<dt> &lt; &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="76b19-557">UAC</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Action: &lt;Action&gt;, for example:</span></span><ul>
<li><span data-ttu-id="76b19-558">Clean: el recurso se ha limpiado</span><span class="sxs-lookup"><span data-stu-id="76b19-558">Clean: The resource was cleaned</span></span></li>
<li><span data-ttu-id="76b19-559">Cuarentena: el recurso se ha puesto en cuarentena</span><span class="sxs-lookup"><span data-stu-id="76b19-559">Quarantine: The resource was quarantined</span></span></li>
<li><span data-ttu-id="76b19-560">Quitar: se eliminó el recurso</span><span class="sxs-lookup"><span data-stu-id="76b19-560">Remove: The resource was deleted</span></span></li>
<li><span data-ttu-id="76b19-561">Permitir: se permitió que el recurso se ejecutara o existiera</span><span class="sxs-lookup"><span data-stu-id="76b19-561">Allow: The resource was allowed to execute/exist</span></span></li>
<li><span data-ttu-id="76b19-562">Definido por el usuario: acción definida por el usuario que normalmente es una de esta lista de acciones que el usuario ha especificado</span><span class="sxs-lookup"><span data-stu-id="76b19-562">User defined: User-defined action that is normally one from this list of actions that the user has specified</span></span></li>
<li><span data-ttu-id="76b19-563">Sin acción: sin acción</span><span class="sxs-lookup"><span data-stu-id="76b19-563">No action: No action</span></span></li>
<li><span data-ttu-id="76b19-564">Bloquear: se bloqueó el recurso para que no se ejecutara</span><span class="sxs-lookup"><span data-stu-id="76b19-564">Block: The resource was blocked from executing</span></span></li>
</ul><span data-ttu-id="76b19-565">
</dt>
<dt>Estado de la acción: &lt; Descripción de &gt; acciones adicionales</dt>
<dt>Código de error: &lt; Código de error Código de resultado asociado con el estado de &gt; amenaza. Valores HRESULT estándar.</dt> 
<dt>Descripción del error: &lt; Descripción del error &gt; Descripción del error.</dt> 
<dt>Versión de firma: &lt; Versión &gt; de definición</dt>
<dt>Versión del motor: &lt; Antimalware Engine versión &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="76b19-565">
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
<span data-ttu-id="76b19-566">Acción del usuario:</span><span class="sxs-lookup"><span data-stu-id="76b19-566">User action:</span></span>
</td>
<td >
<span data-ttu-id="76b19-567">No es necesario realizar ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="76b19-567">No action is necessary.</span></span> <span data-ttu-id="76b19-568">Antivirus de Microsoft Defender no pudo completar una tarea relacionada con la corrección de malware.</span><span class="sxs-lookup"><span data-stu-id="76b19-568">Microsoft Defender Antivirus failed to complete a task related to the malware remediation.</span></span> <span data-ttu-id="76b19-569">No se trata de un error crítico.</span><span class="sxs-lookup"><span data-stu-id="76b19-569">This is not a critical failure.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="76b19-570">Identificador de evento: 1119</span><span class="sxs-lookup"><span data-stu-id="76b19-570">Event ID: 1119</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="76b19-571">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="76b19-571">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="76b19-572">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_CRITICALLY_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-572">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_CRITICALLY_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-573">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="76b19-573">Message:</span></span>
</td>
<td ><span data-ttu-id="76b19-574">
<b>La plataforma antimalware encontró un error crítico al intentar tomar medidas en malware u otro software potencialmente no deseado. Hay más detalles en el mensaje de evento.</b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-574">
<b>The antimalware platform encountered a critical error when trying to take action on malware or other potentially unwanted software. There are more details in the event message.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-575">Descripción:</span><span class="sxs-lookup"><span data-stu-id="76b19-575">Description:</span></span>
</td>
<td >
<span data-ttu-id="76b19-576">Antivirus de Microsoft Defender ha encontrado un error crítico al tomar medidas en malware u otro software potencialmente no deseado.</span><span class="sxs-lookup"><span data-stu-id="76b19-576">Microsoft Defender Antivirus has encountered a critical error when taking action on malware or other potentially unwanted software.</span></span><br/><span data-ttu-id="76b19-577">Para obtener más información, vea los artículos siguientes: </span><span class="sxs-lookup"><span data-stu-id="76b19-577">For more information, see the following:</span></span>
<dl><span data-ttu-id="76b19-578">
<dt>Nombre: &lt; Id. &gt; de</dt>
<dt>nombre de &lt; amenaza: Gravedad del id. &gt; </dt>de 
<dt> amenaza: gravedad , por &lt; &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="76b19-578">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="76b19-579">Bajo</span><span class="sxs-lookup"><span data-stu-id="76b19-579">Low</span></span></li>
<li><span data-ttu-id="76b19-580">Moderado</span><span class="sxs-lookup"><span data-stu-id="76b19-580">Moderate</span></span></li>
<li><span data-ttu-id="76b19-581">Alta</span><span class="sxs-lookup"><span data-stu-id="76b19-581">High</span></span></li>
<li><span data-ttu-id="76b19-582">Grave</span><span class="sxs-lookup"><span data-stu-id="76b19-582">Severe</span></span></li>
</ul><span data-ttu-id="76b19-583">
</dt>
<dt>Categoría: &lt; Descripción de &gt; categoría , por ejemplo, cualquier tipo de amenaza o malware.</dt> 
<dt>Ruta de acceso: &lt; Origen &gt; de detección</dt>de ruta de 
<dt> acceso de &lt; archivo: Origen de &gt; detección, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="76b19-583">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="76b19-584">Unknown</span><span class="sxs-lookup"><span data-stu-id="76b19-584">Unknown</span></span></li>
<li><span data-ttu-id="76b19-585">Equipo local</span><span class="sxs-lookup"><span data-stu-id="76b19-585">Local computer</span></span></li>
<li><span data-ttu-id="76b19-586">Recurso compartido de red</span><span class="sxs-lookup"><span data-stu-id="76b19-586">Network share</span></span></li>
<li><span data-ttu-id="76b19-587">Internet</span><span class="sxs-lookup"><span data-stu-id="76b19-587">Internet</span></span></li>
<li><span data-ttu-id="76b19-588">Tráfico entrante</span><span class="sxs-lookup"><span data-stu-id="76b19-588">Incoming traffic</span></span></li>
<li><span data-ttu-id="76b19-589">Tráfico saliente</span><span class="sxs-lookup"><span data-stu-id="76b19-589">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="76b19-590">
</dt>
<dt>Tipo de &lt; detección: Tipo de &gt; detección , por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="76b19-590">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="76b19-591">Heurística</span><span class="sxs-lookup"><span data-stu-id="76b19-591">Heuristics</span></span></li>
<li><span data-ttu-id="76b19-592">Generic</span><span class="sxs-lookup"><span data-stu-id="76b19-592">Generic</span></span></li>
<li><span data-ttu-id="76b19-593">Concreto</span><span class="sxs-lookup"><span data-stu-id="76b19-593">Concrete</span></span></li>
<li><span data-ttu-id="76b19-594">Firma dinámica</span><span class="sxs-lookup"><span data-stu-id="76b19-594">Dynamic signature</span></span></li>
</ul><span data-ttu-id="76b19-595">
</dt>
<dt>Origen de &lt; detección: origen de &gt; detección por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="76b19-595">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="76b19-596">Usuario: usuario iniciado</span><span class="sxs-lookup"><span data-stu-id="76b19-596">User: user initiated</span></span></li>
<li><span data-ttu-id="76b19-597">Sistema: sistema iniciado</span><span class="sxs-lookup"><span data-stu-id="76b19-597">System: system initiated</span></span></li>
<li><span data-ttu-id="76b19-598">En tiempo real: componente en tiempo real iniciado</span><span class="sxs-lookup"><span data-stu-id="76b19-598">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="76b19-599">IOAV: Descargas de IE y Outlook datos adjuntos de Express iniciados</span><span class="sxs-lookup"><span data-stu-id="76b19-599">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="76b19-600">NIS: sistema de inspección de red</span><span class="sxs-lookup"><span data-stu-id="76b19-600">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="76b19-601">IEPROTECT: IE - IExtensionValidation; esto protege contra controles de páginas web malintencionadas</span><span class="sxs-lookup"><span data-stu-id="76b19-601">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="76b19-602">Antimalware de inicio anticipado (ELAM).</span><span class="sxs-lookup"><span data-stu-id="76b19-602">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="76b19-603">Esto incluye malware detectado por la secuencia de arranque</span><span class="sxs-lookup"><span data-stu-id="76b19-603">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="76b19-604">Atestación remota</span><span class="sxs-lookup"><span data-stu-id="76b19-604">Remote attestation</span></span></li>
</ul><span data-ttu-id="76b19-605">Interfaz de examen antimalware (AMSI).</span><span class="sxs-lookup"><span data-stu-id="76b19-605">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="76b19-606">Se usa principalmente para proteger scripts (PS, VBS), aunque también pueden invocarse por terceros.</span><span class="sxs-lookup"><span data-stu-id="76b19-606">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="76b19-607">Usuario de </dt> 
<dt>UAC: Dominio &lt; &gt; \& lt; Nombre &gt; </dt>
<dt>del proceso de usuario: Proceso en la &lt; acción &gt; pid:</dt>Acción , por 
<dt> &lt; &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="76b19-607">UAC</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Action: &lt;Action&gt;, for example:</span></span><ul>
<li><span data-ttu-id="76b19-608">Clean: el recurso se ha limpiado</span><span class="sxs-lookup"><span data-stu-id="76b19-608">Clean: The resource was cleaned</span></span></li>
<li><span data-ttu-id="76b19-609">Cuarentena: el recurso se ha puesto en cuarentena</span><span class="sxs-lookup"><span data-stu-id="76b19-609">Quarantine: The resource was quarantined</span></span></li>
<li><span data-ttu-id="76b19-610">Quitar: se eliminó el recurso</span><span class="sxs-lookup"><span data-stu-id="76b19-610">Remove: The resource was deleted</span></span></li>
<li><span data-ttu-id="76b19-611">Permitir: se permitió que el recurso se ejecutara o existiera</span><span class="sxs-lookup"><span data-stu-id="76b19-611">Allow: The resource was allowed to execute/exist</span></span></li>
<li><span data-ttu-id="76b19-612">Definido por el usuario: acción definida por el usuario que normalmente es una de esta lista de acciones que el usuario ha especificado</span><span class="sxs-lookup"><span data-stu-id="76b19-612">User defined: User-defined action that is normally one from this list of actions that the user has specified</span></span></li>
<li><span data-ttu-id="76b19-613">Sin acción: sin acción</span><span class="sxs-lookup"><span data-stu-id="76b19-613">No action: No action</span></span></li>
<li><span data-ttu-id="76b19-614">Bloquear: se bloqueó el recurso para que no se ejecutara</span><span class="sxs-lookup"><span data-stu-id="76b19-614">Block: The resource was blocked from executing</span></span></li>
</ul><span data-ttu-id="76b19-615">
</dt>
<dt>Estado de la acción: &lt; Descripción de &gt; acciones adicionales</dt>
<dt>Código de error: &lt; Código de error Código de resultado asociado con el estado de &gt; amenaza. Valores HRESULT estándar.</dt> 
<dt>Descripción del error: &lt; Descripción del error &gt; Descripción del error.</dt> 
<dt>Versión de firma: &lt; Versión &gt; de definición</dt>
<dt>Versión del motor: &lt; Antimalware Engine versión &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="76b19-615">
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
<span data-ttu-id="76b19-616">Acción del usuario:</span><span class="sxs-lookup"><span data-stu-id="76b19-616">User action:</span></span>
</td>
<td >
<span data-ttu-id="76b19-617">El Antivirus de Microsoft Defender encontró este error debido a problemas críticos.</span><span class="sxs-lookup"><span data-stu-id="76b19-617">The Microsoft Defender Antivirus client encountered this error due to critical issues.</span></span> <span data-ttu-id="76b19-618">Es posible que el extremo no esté protegido.</span><span class="sxs-lookup"><span data-stu-id="76b19-618">The endpoint might not be protected.</span></span> <span data-ttu-id="76b19-619">Revise la descripción del error y, a continuación, siga los <b>pasos de acción de usuario</b> pertinentes a continuación.</span><span class="sxs-lookup"><span data-stu-id="76b19-619">Review the error description then follow the relevant <b>User action</b> steps below.</span></span>
<table>
<tr>
<th><span data-ttu-id="76b19-620">Acción</span><span class="sxs-lookup"><span data-stu-id="76b19-620">Action</span></span></th>
<th><span data-ttu-id="76b19-621">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="76b19-621">User action</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="76b19-622">
<b>Quitar</b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-622">
<b>Remove</b>
</span></span></td>
<td>
<span data-ttu-id="76b19-623">Actualice las definiciones y compruebe que la eliminación se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="76b19-623">Update the definitions then verify that the removal was successful.</span></span>
</td>
</tr>
<tr>
<td><span data-ttu-id="76b19-624">
<b>Limpiar</b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-624">
<b>Clean</b>
</span></span></td>
<td>
<span data-ttu-id="76b19-625">Actualice las definiciones y compruebe que la corrección se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="76b19-625">Update the definitions then verify that the remediation was successful.</span></span>
</td>
</tr>
<tr>
<td><span data-ttu-id="76b19-626">
<b>Cuarentena</b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-626">
<b>Quarantine</b>
</span></span></td>
<td>
<span data-ttu-id="76b19-627">Actualice las definiciones y compruebe que el usuario tiene permiso para acceder a los recursos necesarios.</span><span class="sxs-lookup"><span data-stu-id="76b19-627">Update the definitions and verify that the user has permission to access the necessary resources.</span></span>
</td>
</tr>
<tr>
<td><span data-ttu-id="76b19-628">
<b>Permitir</b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-628">
<b>Allow</b>
</span></span></td>
<td>
<span data-ttu-id="76b19-629">Compruebe que el usuario tiene permiso para obtener acceso a los recursos necesarios.</span><span class="sxs-lookup"><span data-stu-id="76b19-629">Verify that the user has permission to access the necessary resources.</span></span>
</td>
</tr>
</table>

<span data-ttu-id="76b19-630">Si este evento persiste:</span><span class="sxs-lookup"><span data-stu-id="76b19-630">If this event persists:</span></span><ol>
<li><span data-ttu-id="76b19-631">Vuelva a ejecutar el examen.</span><span class="sxs-lookup"><span data-stu-id="76b19-631">Run the scan again.</span></span></li>
<li><span data-ttu-id="76b19-632">Si se produce un error de la misma manera, vaya <b></b> al sitio de soporte técnico de <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft</a>, escriba el número de error en el cuadro Buscar para buscar el código de error.</span><span class="sxs-lookup"><span data-stu-id="76b19-632">If it fails in the same way, go to the <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft Support site</a>, enter the error number in the <b>Search</b> box to look for the error code.</span></span></li>
<li><span data-ttu-id="76b19-633">Contactar al <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Soporte técnico de Microsoft</a>.</span><span class="sxs-lookup"><span data-stu-id="76b19-633">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="76b19-634">Identificador de evento: 1120</span><span class="sxs-lookup"><span data-stu-id="76b19-634">Event ID: 1120</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="76b19-635">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="76b19-635">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="76b19-636">
<b>MALWAREPROTECTION_THREAT_HASH</b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-636">
<b>MALWAREPROTECTION_THREAT_HASH</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-637">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="76b19-637">Message:</span></span>
</td>
<td ><span data-ttu-id="76b19-638">
<b>Antivirus de Microsoft Defender ha deducido los hashes de un recurso de amenaza.</b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-638">
<b>Microsoft Defender Antivirus has deduced the hashes for a threat resource.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-639">Descripción:</span><span class="sxs-lookup"><span data-stu-id="76b19-639">Description:</span></span>
</td>
<td >
<span data-ttu-id="76b19-640">Antivirus de Microsoft Defender cliente está en funcionamiento en un estado correcto.</span><span class="sxs-lookup"><span data-stu-id="76b19-640">Microsoft Defender Antivirus client is up and running in a healthy state.</span></span>
<dl><span data-ttu-id="76b19-641">
<dt>Versión actual de la plataforma: &lt; Ruta de &gt; acceso de</dt>recurso de amenaza de la
<dt> &lt; &gt; versión</dt>actual de la plataforma:
<dt>hashes de ruta: &lt; hashes &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="76b19-641">
<dt>Current Platform Version: &lt;Current platform version&gt;</dt>
<dt>Threat Resource Path: &lt;Path&gt;</dt>
<dt>Hashes: &lt;Hashes&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td></td>
<td >
<div class="alert"><span data-ttu-id="76b19-642"><b>Nota: Este evento solo se registrará si se establece la siguiente directiva: <b>ThreatFileHashLogging sin signo</b>.</span><span class="sxs-lookup"><span data-stu-id="76b19-642"><b>Note: This event will only be logged if the following policy is set: <b>ThreatFileHashLogging     unsigned</b>.</span></span></div>
<div> </div>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="76b19-643">Identificador de evento: 1150</span><span class="sxs-lookup"><span data-stu-id="76b19-643">Event ID: 1150</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="76b19-644">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="76b19-644">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="76b19-645">
<b>MALWAREPROTECTION_SERVICE_HEALTHY</b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-645">
<b>MALWAREPROTECTION_SERVICE_HEALTHY</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-646">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="76b19-646">Message:</span></span>
</td>
<td ><span data-ttu-id="76b19-647">
<b>Si la plataforma antimalware notifica el estado a una plataforma de supervisión, este evento indica que la plataforma antimalware se está ejecutando y en un estado correcto. </b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-647">
<b>If your antimalware platform reports status to a monitoring platform, this event indicates that the antimalware platform is running and in a healthy state. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-648">Descripción:</span><span class="sxs-lookup"><span data-stu-id="76b19-648">Description:</span></span>
</td>
<td >
<span data-ttu-id="76b19-649">Antivirus de Microsoft Defender cliente está en funcionamiento en un estado correcto.</span><span class="sxs-lookup"><span data-stu-id="76b19-649">Microsoft Defender Antivirus client is up and running in a healthy state.</span></span>
<dl><span data-ttu-id="76b19-650">
<dt>Versión de la plataforma: &lt; Versión de &gt; la plataforma actual</dt>Versión de firma: Versión del motor
<dt> &lt; de &gt; </dt>la versión de definición:
<dt>Antimalware Engine &lt; versión &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="76b19-650">
<dt>Platform Version: &lt;Current platform version&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-651">Acción del usuario:</span><span class="sxs-lookup"><span data-stu-id="76b19-651">User action:</span></span>
</td>
<td >
<span data-ttu-id="76b19-652">No es necesario realizar ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="76b19-652">No action is necessary.</span></span> <span data-ttu-id="76b19-653">El Antivirus de Microsoft Defender está en buen estado.</span><span class="sxs-lookup"><span data-stu-id="76b19-653">The Microsoft Defender Antivirus client is in a healthy state.</span></span> <span data-ttu-id="76b19-654">Este evento se notifica cada hora.</span><span class="sxs-lookup"><span data-stu-id="76b19-654">This event is reported on an hourly basis.</span></span>
</td>
</tr>

<tr>
<th colspan="2"><span data-ttu-id="76b19-655">Identificador de evento: 1151</span><span class="sxs-lookup"><span data-stu-id="76b19-655">Event ID: 1151</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="76b19-656">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="76b19-656">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="76b19-657">
<b>MALWAREPROTECTION_SERVICE_HEALTH_REPORT</b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-657">
<b>MALWAREPROTECTION_SERVICE_HEALTH_REPORT</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-658">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="76b19-658">Message:</span></span>
</td>
<td ><span data-ttu-id="76b19-659">
<b>Endpoint Protection de estado del cliente (hora UTC)</b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-659">
<b>Endpoint Protection client health report (time in UTC) </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-660">Descripción:</span><span class="sxs-lookup"><span data-stu-id="76b19-660">Description:</span></span>
</td>
<td >
<span data-ttu-id="76b19-661">Informe de estado del cliente antivirus.</span><span class="sxs-lookup"><span data-stu-id="76b19-661">Antivirus client health report.</span></span>
<dl><span data-ttu-id="76b19-662">
<dt>Versión de la plataforma: &lt; &gt;</dt>Versión actual del motor de la
<dt>plataforma: &lt; versión &gt; </dt>Antimalware Engine Versión del motor de inspección en tiempo real de
<dt>red: &lt; &gt; </dt>Versión de firma del motor de inspección en tiempo real de red
<dt>Versión &lt; &gt; </dt>de firma antivirus versión de firma
<dt> &lt; antispyware: &gt; </dt>versión de firma antispyware Versión de firma de inspección en tiempo real
<dt>de red: &lt; &gt; </dt>Estado rtp de la firma de inspección en tiempo real de red: protección en tiempo real estado (habilitado o
<dt> &lt; &gt; deshabilitado)</dt>Estado de
<dt>la OA: Estado de IOAV de estado de acceso &lt; &gt; (habilitado</dt>o deshabilitado): Descargas de
<dt>I Outlook E y estado de datos adjuntos rápidos &lt; &gt; (habilitados</dt>o deshabilitados) estado BM: Estado de supervisión del comportamiento (habilitado o
<dt> &lt; &gt; deshabilitado)</dt>Antigüedad de firma del antivirus: antigüedad de firma del
<dt>antivirus &lt; &gt; (en días) </dt>Antigüedad de firma antispyware: Antigüedad de firma 
<dt> &lt; antispyware &gt; (en días)</dt>Última antigüedad del examen rápido: Última antigüedad del examen rápido
<dt> &lt; &gt; (en días)</dt>Última antigüedad completa del examen: Última antigüedad completa del examen
<dt> &lt; &gt; (en días)</dt>Tiempo de creación de firmas
<dt>antivirus: ? &lt; Hora de &gt; creación de firmas antivirus</dt>Tiempo de
<dt>creación de firmas antispyware: ? &lt; Hora de creación &gt; de firmas antispyware</dt>
<dt>Última hora de inicio del examen rápido: ? &lt; Última hora de &gt; inicio del examen rápido</dt>Última hora de finalización del examen
<dt>rápido: ? &lt; Última &gt; hora</dt>de finalización del examen rápido Último origen de examen rápido: Último origen de examen rápido (0 = el examen no se&#39;se ha ejecutado, 1 = iniciado por el
<dt> &lt; &gt; usuario, 2 =</dt>iniciado por el sistema) Última hora de inicio del examen
<dt>completo: ? &lt; Última hora de &gt; inicio del examen completo</dt>Última hora de finalización del examen
<dt>completo: ? &lt; Última &gt; hora</dt>de finalización del examen completo Último origen de examen completo: Último origen de examen completo (0 = el examen no se&#39;no se ha ejecutado, 1 = iniciado por el
<dt> &lt; &gt; usuario, 2 =</dt>iniciado por el sistema) Estado del producto: Para la solución de problemas interna 
<dt></span><span class="sxs-lookup"><span data-stu-id="76b19-662">
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

<tr><span data-ttu-id="76b19-663">
<th colspan="2">Identificador de evento: 2000</span><span class="sxs-lookup"><span data-stu-id="76b19-663">
<th colspan="2">Event ID: 2000</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="76b19-664">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="76b19-664">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="76b19-665">
<b>MALWAREPROTECTION_SIGNATURE_UPDATED </b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-665">
<b>MALWAREPROTECTION_SIGNATURE_UPDATED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-666">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="76b19-666">Message:</span></span>
</td>
<td ><span data-ttu-id="76b19-667">
<b>Las definiciones de antimalware se actualizaron correctamente. </b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-667">
<b>The antimalware definitions updated successfully. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-668">Descripción:</span><span class="sxs-lookup"><span data-stu-id="76b19-668">Description:</span></span>
</td>
<td >
<span data-ttu-id="76b19-669">Se ha actualizado la versión de firma del antivirus.</span><span class="sxs-lookup"><span data-stu-id="76b19-669">Antivirus signature version has been updated.</span></span>
<dl><span data-ttu-id="76b19-670">
<dt>Versión de firma actual: &lt; Versión de &gt; firma actual</dt>
<dt>Versión de firma anterior: Versión de firma &lt; anterior &gt; </dt>Tipo de 
<dt> firma: Tipo de firma , por &lt; &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="76b19-670">
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Previous Signature Version: &lt;Previous signature version&gt;</dt>
<dt>Signature Type: &lt;Signature type&gt;, for example:</span></span> <ul>
<li><span data-ttu-id="76b19-671">Antivirus</span><span class="sxs-lookup"><span data-stu-id="76b19-671">Antivirus</span></span></li>
<li><span data-ttu-id="76b19-672">Antispyware</span><span class="sxs-lookup"><span data-stu-id="76b19-672">Antispyware</span></span></li>
<li><span data-ttu-id="76b19-673">Antimalware</span><span class="sxs-lookup"><span data-stu-id="76b19-673">Antimalware</span></span></li>
<li><span data-ttu-id="76b19-674">Sistema de inspección de red</span><span class="sxs-lookup"><span data-stu-id="76b19-674">Network Inspection System</span></span></li>
</ul><span data-ttu-id="76b19-675">
</dt>
<dt>Tipo de actualización: &lt; Tipo de &gt; actualización , Completo o Delta.</dt> 
<dt>Usuario: &lt; Dominio &gt; \& lt; Versión &gt; </dt>
<dt>del motor actual del usuario: versión actual del &lt; &gt; motor</dt>Versión anterior del
<dt>motor: Versión anterior del &lt; motor &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="76b19-675">
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
<span data-ttu-id="76b19-676">Acción del usuario:</span><span class="sxs-lookup"><span data-stu-id="76b19-676">User action:</span></span>
</td>
<td >
<span data-ttu-id="76b19-677">No es necesario realizar ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="76b19-677">No action is necessary.</span></span> <span data-ttu-id="76b19-678">El Antivirus de Microsoft Defender está en buen estado.</span><span class="sxs-lookup"><span data-stu-id="76b19-678">The Microsoft Defender Antivirus client is in a healthy state.</span></span> <span data-ttu-id="76b19-679">Este evento se notifica cuando las firmas se actualizan correctamente.</span><span class="sxs-lookup"><span data-stu-id="76b19-679">This event is reported when signatures are successfully updated.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="76b19-680">Identificador de evento: 2001</span><span class="sxs-lookup"><span data-stu-id="76b19-680">Event ID: 2001</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="76b19-681">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="76b19-681">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="76b19-682">
<b>MALWAREPROTECTION_SIGNATURE_UPDATE_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-682">
<b>MALWAREPROTECTION_SIGNATURE_UPDATE_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-683">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="76b19-683">Message:</span></span>
</td>
<td ><span data-ttu-id="76b19-684">
<b>Error en la actualización de inteligencia de seguridad. </b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-684">
<b>The security intelligence update failed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-685">Descripción:</span><span class="sxs-lookup"><span data-stu-id="76b19-685">Description:</span></span>
</td>
<td >
<span data-ttu-id="76b19-686">Antivirus de Microsoft Defender ha encontrado un error al intentar actualizar firmas.</span><span class="sxs-lookup"><span data-stu-id="76b19-686">Microsoft Defender Antivirus has encountered an error trying to update signatures.</span></span>
<dl><span data-ttu-id="76b19-687">
<dt>Nueva versión de inteligencia de seguridad: &lt; Nuevo número &gt; de versión</dt>
<dt>Versión de inteligencia de seguridad anterior: Versión &lt; &gt; anterior</dt>Update 
<dt> Source: Update source , por &lt; &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="76b19-687">
<dt>New security intelligence version: &lt;New version number&gt;</dt>
<dt>Previous security intelligence version: &lt;Previous version&gt;</dt>
<dt>Update Source: &lt;Update source&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="76b19-688">Carpeta de actualización de inteligencia de seguridad</span><span class="sxs-lookup"><span data-stu-id="76b19-688">Security intelligence update folder</span></span></li>
<li><span data-ttu-id="76b19-689">Servidor de actualización de inteligencia de seguridad interna</span><span class="sxs-lookup"><span data-stu-id="76b19-689">Internal security intelligence update server</span></span></li>
<li><span data-ttu-id="76b19-690">Microsoft Update Server</span><span class="sxs-lookup"><span data-stu-id="76b19-690">Microsoft Update Server</span></span></li>
<li><span data-ttu-id="76b19-691">Compartir archivos</span><span class="sxs-lookup"><span data-stu-id="76b19-691">File share</span></span></li>
<li><span data-ttu-id="76b19-692">Centro de protección contra malware de Microsoft (MMPC)</span><span class="sxs-lookup"><span data-stu-id="76b19-692">Microsoft Malware Protection Center (MMPC)</span></span></li>
</ul><span data-ttu-id="76b19-693">
</dt>
<dt>Update Stage: &lt; Update stage , por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="76b19-693">
</dt>
<dt>Update Stage: &lt;Update stage&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="76b19-694">Búsqueda</span><span class="sxs-lookup"><span data-stu-id="76b19-694">Search</span></span></li>
<li><span data-ttu-id="76b19-695">Descargar</span><span class="sxs-lookup"><span data-stu-id="76b19-695">Download</span></span></li>
<li><span data-ttu-id="76b19-696">Instalar</span><span class="sxs-lookup"><span data-stu-id="76b19-696">Install</span></span></li>
</ul><span data-ttu-id="76b19-697">
</dt>Ruta de acceso de origen: nombre del recurso compartido de archivos para convención de nomenclatura universal (UNC), nombre del servidor 
<dt>para Windows Server Update Services (WSUS)/Microsoft Update/ADL.</dt> 
<dt> Tipo de firma: &lt; Tipo de firma , por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="76b19-697">
</dt>
<dt>Source Path: File share name for Universal Naming Convention (UNC), server name for Windows Server Update Services (WSUS)/Microsoft Update/ADL.</dt>
<dt>Signature Type: &lt;Signature type&gt;, for example:</span></span> <ul>
<li><span data-ttu-id="76b19-698">Antivirus</span><span class="sxs-lookup"><span data-stu-id="76b19-698">Antivirus</span></span></li>
<li><span data-ttu-id="76b19-699">Antispyware</span><span class="sxs-lookup"><span data-stu-id="76b19-699">Antispyware</span></span></li>
<li><span data-ttu-id="76b19-700">Antimalware</span><span class="sxs-lookup"><span data-stu-id="76b19-700">Antimalware</span></span></li>
<li><span data-ttu-id="76b19-701">Sistema de inspección de red</span><span class="sxs-lookup"><span data-stu-id="76b19-701">Network Inspection System</span></span></li>
</ul><span data-ttu-id="76b19-702">
</dt>
<dt>Tipo de actualización: &lt; Tipo de &gt; actualización , Completo o Delta.</dt> 
<dt>Usuario: &lt; Dominio &gt; \& lt; Versión &gt; </dt>
<dt>actual del motor del usuario: &lt; &gt; Versión</dt>actual del motor Versión anterior del motor: Versión
<dt> &lt; anterior &gt; </dt>del motor Código de error: Código de error Código de
<dt>resultado asociado con el estado de la &lt; &gt; amenaza. Valores HRESULT estándar.</dt> 
<dt>Descripción del error: &lt; Descripción del error &gt; Descripción del error.</dt>
</span><span class="sxs-lookup"><span data-stu-id="76b19-702">
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
<span data-ttu-id="76b19-703">Acción del usuario:</span><span class="sxs-lookup"><span data-stu-id="76b19-703">User action:</span></span>
</td>
<td >
<span data-ttu-id="76b19-704">Este error se produce cuando hay un problema al actualizar definiciones.</span><span class="sxs-lookup"><span data-stu-id="76b19-704">This error occurs when there is a problem updating definitions.</span></span>
<span data-ttu-id="76b19-705">Para solucionar este evento:</span><span class="sxs-lookup"><span data-stu-id="76b19-705">To troubleshoot this event:</span></span>
<ol>
<li><span data-ttu-id="76b19-706"><a href="manage-updates-baselines-microsoft-defender-antivirus.md" data-raw-source="[Update definitions](manage-updates-baselines-microsoft-defender-antivirus.md)">Actualice las definiciones</a> y fuerza un nuevo análisis directamente en el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="76b19-706"><a href="manage-updates-baselines-microsoft-defender-antivirus.md" data-raw-source="[Update definitions](manage-updates-baselines-microsoft-defender-antivirus.md)">Update definitions</a> and force a rescan directly on the endpoint.</span></span></li>
<li><span data-ttu-id="76b19-707">Revisa las entradas del archivo %Windir%\WindowsUpdate.log para obtener más información sobre este error.</span><span class="sxs-lookup"><span data-stu-id="76b19-707">Review the entries in the %Windir%\WindowsUpdate.log file for more information about this error.</span></span></li>
<li><span data-ttu-id="76b19-708">Contactar al <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Soporte técnico de Microsoft</a>.</span><span class="sxs-lookup"><span data-stu-id="76b19-708">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="76b19-709">Identificador de evento: 2002</span><span class="sxs-lookup"><span data-stu-id="76b19-709">Event ID: 2002</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="76b19-710">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="76b19-710">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="76b19-711">
<b>MALWAREPROTECTION_ENGINE_UPDATED</b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-711">
<b>MALWAREPROTECTION_ENGINE_UPDATED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-712">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="76b19-712">Message:</span></span>
</td>
<td ><span data-ttu-id="76b19-713">
<b>El motor de antimalware se actualizó correctamente. </b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-713">
<b>The antimalware engine updated successfully. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-714">Descripción:</span><span class="sxs-lookup"><span data-stu-id="76b19-714">Description:</span></span>
</td>
<td >
<span data-ttu-id="76b19-715">Antivirus de Microsoft Defender versión del motor se ha actualizado.</span><span class="sxs-lookup"><span data-stu-id="76b19-715">Microsoft Defender Antivirus engine version has been updated.</span></span>
<dl><span data-ttu-id="76b19-716">
<dt>Versión actual del motor: &lt; Versión actual &gt; del motor</dt>
<dt>Versión anterior del motor: &lt; &gt; Versión anterior</dt>del motor Tipo de motor: Tipo de motor , motor antimalware o motor del sistema de inspección de
<dt> &lt; &gt; red.</dt> 
<dt>Usuario: &lt; Dominio &gt; \& lt; Usuario &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="76b19-716">
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Previous Engine Version: &lt;Previous engine version&gt;</dt>
<dt>Engine Type: &lt;Engine type&gt;, either antimalware engine or Network Inspection System engine.</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-717">Acción del usuario:</span><span class="sxs-lookup"><span data-stu-id="76b19-717">User action:</span></span>
</td>
<td >
<span data-ttu-id="76b19-718">No es necesario realizar ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="76b19-718">No action is necessary.</span></span> <span data-ttu-id="76b19-719">El Antivirus de Microsoft Defender está en buen estado.</span><span class="sxs-lookup"><span data-stu-id="76b19-719">The Microsoft Defender Antivirus client is in a healthy state.</span></span> <span data-ttu-id="76b19-720">Este evento se notifica cuando el motor de antimalware se actualiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="76b19-720">This event is reported when the antimalware engine is successfully updated.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="76b19-721">Identificador de evento: 2003</span><span class="sxs-lookup"><span data-stu-id="76b19-721">Event ID: 2003</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="76b19-722">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="76b19-722">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="76b19-723">
<b>MALWAREPROTECTION_ENGINE_UPDATE_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-723">
<b>MALWAREPROTECTION_ENGINE_UPDATE_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-724">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="76b19-724">Message:</span></span>
</td>
<td ><span data-ttu-id="76b19-725">
<b>Error en la actualización del motor de antimalware. </b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-725">
<b>The antimalware engine update failed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-726">Descripción:</span><span class="sxs-lookup"><span data-stu-id="76b19-726">Description:</span></span>
</td>
<td >
<span data-ttu-id="76b19-727">Antivirus de Microsoft Defender ha encontrado un error al intentar actualizar el motor.</span><span class="sxs-lookup"><span data-stu-id="76b19-727">Microsoft Defender Antivirus has encountered an error trying to update the engine.</span></span>
<dl><span data-ttu-id="76b19-728">
<dt>Nueva versión del motor:</dt>
<dt>Versión anterior del motor: &lt; &gt; </dt>Versión anterior del motor Tipo de motor: Tipo de motor , motor antimalware o motor del sistema de inspección de
<dt> &lt; &gt; red.</dt> 
<dt>Usuario: &lt; Dominio &gt; \& lt; Código &gt; </dt>
<dt>de error del usuario: Código de error &lt; Código de resultado asociado con el estado de &gt; amenaza. Valores HRESULT estándar.</dt> 
<dt>Descripción del error: &lt; Descripción del error &gt; Descripción del error.</dt>
</span><span class="sxs-lookup"><span data-stu-id="76b19-728">
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
<span data-ttu-id="76b19-729">Acción del usuario:</span><span class="sxs-lookup"><span data-stu-id="76b19-729">User action:</span></span>
</td>
<td >
<span data-ttu-id="76b19-730">Error Antivirus de Microsoft Defender actualización de cliente.</span><span class="sxs-lookup"><span data-stu-id="76b19-730">The Microsoft Defender Antivirus client update failed.</span></span> <span data-ttu-id="76b19-731">Este evento se produce cuando el cliente no se actualiza.</span><span class="sxs-lookup"><span data-stu-id="76b19-731">This event occurs when the client fails to update itself.</span></span> <span data-ttu-id="76b19-732">Este evento suele deberse a una interrupción en la conectividad de red durante una actualización.</span><span class="sxs-lookup"><span data-stu-id="76b19-732">This event is usually due to an interruption in network connectivity during an update.</span></span>
<span data-ttu-id="76b19-733">Para solucionar este evento:</span><span class="sxs-lookup"><span data-stu-id="76b19-733">To troubleshoot this event:</span></span>
<ol>
<li><span data-ttu-id="76b19-734"><a href="manage-updates-baselines-microsoft-defender-antivirus.md" data-raw-source="[Update definitions](manage-updates-baselines-microsoft-defender-antivirus.md)">Actualice las definiciones</a> y fuerza un nuevo análisis directamente en el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="76b19-734"><a href="manage-updates-baselines-microsoft-defender-antivirus.md" data-raw-source="[Update definitions](manage-updates-baselines-microsoft-defender-antivirus.md)">Update definitions</a> and force a rescan directly on the endpoint.</span></span></li>
<li><span data-ttu-id="76b19-735">Contactar al <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Soporte técnico de Microsoft</a>.</span><span class="sxs-lookup"><span data-stu-id="76b19-735">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="76b19-736">Identificador de evento: 2004</span><span class="sxs-lookup"><span data-stu-id="76b19-736">Event ID: 2004</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="76b19-737">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="76b19-737">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="76b19-738">
<b>MALWAREPROTECTION_SIGNATURE_REVERSION</b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-738">
<b>MALWAREPROTECTION_SIGNATURE_REVERSION</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-739">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="76b19-739">Message:</span></span>
</td>
<td ><span data-ttu-id="76b19-740">
<b>Hubo un problema al cargar definiciones de antimalware. El motor de antimalware intentará cargar el último conjunto de definiciones bien conocido.</b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-740">
<b>There was a problem loading antimalware definitions. The antimalware engine will attempt to load the last-known good set of definitions.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-741">Descripción:</span><span class="sxs-lookup"><span data-stu-id="76b19-741">Description:</span></span>
</td>
<td >
<span data-ttu-id="76b19-742">Antivirus de Microsoft Defender ha encontrado un error al intentar cargar firmas e intentará volver a un conjunto de firmas conocido.</span><span class="sxs-lookup"><span data-stu-id="76b19-742">Microsoft Defender Antivirus has encountered an error trying to load signatures and will attempt reverting back to a known-good set of signatures.</span></span>
<dl><span data-ttu-id="76b19-743">
<dt>Firmas intentadas:</dt>
<dt>Código de error: Código de error Código de resultado asociado con el estado de &lt; &gt; amenaza. Valores HRESULT estándar.</dt> 
<dt>Descripción del error: &lt; Descripción del error &gt; Descripción del error.</dt> 
<dt>Versión de firma: &lt; Versión &gt; de definición</dt>
<dt>Versión del motor: &lt; versión &gt; del motor antimalware</dt>
</span><span class="sxs-lookup"><span data-stu-id="76b19-743">
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
<span data-ttu-id="76b19-744">Acción del usuario:</span><span class="sxs-lookup"><span data-stu-id="76b19-744">User action:</span></span>
</td>
<td >
<span data-ttu-id="76b19-745">El Antivirus de Microsoft Defender intentó descargar e instalar el archivo de definiciones más reciente y falló.</span><span class="sxs-lookup"><span data-stu-id="76b19-745">The Microsoft Defender Antivirus client attempted to download and install the latest definitions file and failed.</span></span> <span data-ttu-id="76b19-746">Este error puede producirse cuando el cliente encuentra un error al intentar cargar las definiciones o si el archivo está dañado.</span><span class="sxs-lookup"><span data-stu-id="76b19-746">This error can occur when the client encounters an error while trying to load the definitions, or if the file is corrupt.</span></span> <span data-ttu-id="76b19-747">Antivirus de Microsoft Defender intentará volver a un conjunto de definiciones conocido.</span><span class="sxs-lookup"><span data-stu-id="76b19-747">Microsoft Defender Antivirus will attempt to revert back to a known-good set of definitions.</span></span>
<span data-ttu-id="76b19-748">Para solucionar este evento:</span><span class="sxs-lookup"><span data-stu-id="76b19-748">To troubleshoot this event:</span></span>
<ol>
<li><span data-ttu-id="76b19-749">Reinicie el equipo e inténtelo de nuevo.</span><span class="sxs-lookup"><span data-stu-id="76b19-749">Restart the computer and try again.</span></span></li>
<li><span data-ttu-id="76b19-750">Descargue las definiciones más recientes del <a href="https://aka.ms/wdsi">Inteligencia de seguridad de Microsoft sitio</a>.</span><span class="sxs-lookup"><span data-stu-id="76b19-750">Download the latest definitions from the <a href="https://aka.ms/wdsi">Microsoft Security Intelligence site</a>.</span></span>
<span data-ttu-id="76b19-751">Nota: El tamaño del archivo de definiciones descargado del sitio puede superar los 60 MB y no debe usarse como solución a largo plazo para actualizar definiciones.</span><span class="sxs-lookup"><span data-stu-id="76b19-751">Note: The size of the definitions file downloaded from the site can exceed 60 MB and should not be used as a long-term solution for updating definitions.</span></span>
</li>
<li><span data-ttu-id="76b19-752">Contactar al <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Soporte técnico de Microsoft</a>.</span><span class="sxs-lookup"><span data-stu-id="76b19-752">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="76b19-753">Identificador de evento: 2005</span><span class="sxs-lookup"><span data-stu-id="76b19-753">Event ID: 2005</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="76b19-754">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="76b19-754">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="76b19-755">
<b>MALWAREPROTECTION_ENGINE_UPDATE_PLATFORMOUTOFDATE</b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-755">
<b>MALWAREPROTECTION_ENGINE_UPDATE_PLATFORMOUTOFDATE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-756">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="76b19-756">Message:</span></span>
</td>
<td ><span data-ttu-id="76b19-757">
<b>El motor de antimalware no se pudo cargar porque la plataforma antimalware no está actualizada. La plataforma antimalware cargará el último motor antimalware bueno conocido e intentará actualizarlo.</b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-757">
<b>The antimalware engine failed to load because the antimalware platform is out of date. The antimalware platform will load the last-known good antimalware engine and attempt to update.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-758">Descripción:</span><span class="sxs-lookup"><span data-stu-id="76b19-758">Description:</span></span>
</td>
<td >
<span data-ttu-id="76b19-759">Antivirus de Microsoft Defender no se pudo cargar el motor de antimalware porque no se admite la versión actual de la plataforma.</span><span class="sxs-lookup"><span data-stu-id="76b19-759">Microsoft Defender Antivirus could not load antimalware engine because current platform version is not supported.</span></span> <span data-ttu-id="76b19-760">Antivirus de Microsoft Defender volverá al último motor conocido y se intenta actualizar la plataforma.</span><span class="sxs-lookup"><span data-stu-id="76b19-760">Microsoft Defender Antivirus will revert back to the last known-good engine and a platform update will be attempted.</span></span>
<dl><span data-ttu-id="76b19-761">
<dt>Versión actual de la plataforma: &lt; versión actual de la plataforma&gt;</dt>
</span><span class="sxs-lookup"><span data-stu-id="76b19-761">
<dt>Current Platform Version: &lt;Current platform version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="76b19-762">Identificador de evento: 2006</span><span class="sxs-lookup"><span data-stu-id="76b19-762">Event ID: 2006</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="76b19-763">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="76b19-763">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="76b19-764">
<b>MALWAREPROTECTION_PLATFORM_UPDATE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-764">
<b>MALWAREPROTECTION_PLATFORM_UPDATE_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-765">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="76b19-765">Message:</span></span>
</td>
<td ><span data-ttu-id="76b19-766">
<b>Error en la actualización de la plataforma. </b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-766">
<b>The platform update failed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-767">Descripción:</span><span class="sxs-lookup"><span data-stu-id="76b19-767">Description:</span></span>
</td>
<td >
<span data-ttu-id="76b19-768">Antivirus de Microsoft Defender ha encontrado un error al intentar actualizar la plataforma.</span><span class="sxs-lookup"><span data-stu-id="76b19-768">Microsoft Defender Antivirus has encountered an error trying to update the platform.</span></span>
<dl><span data-ttu-id="76b19-769">
<dt>Versión actual de la plataforma: &lt; Versión actual &gt; de la plataforma</dt>
<dt>Código de error: Código de error &lt; Código de resultado asociado con el estado de &gt; amenaza. Valores HRESULT estándar.</dt> 
<dt>Descripción del error: &lt; Descripción del error &gt; Descripción del error.</dt>
</span><span class="sxs-lookup"><span data-stu-id="76b19-769">
<dt>Current Platform Version: &lt;Current platform version&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="76b19-770">Identificador de evento: 2007</span><span class="sxs-lookup"><span data-stu-id="76b19-770">Event ID: 2007</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="76b19-771">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="76b19-771">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="76b19-772">
<b>MALWAREPROTECTION_PLATFORM_ALMOSTOUTOFDATE</b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-772">
<b>MALWAREPROTECTION_PLATFORM_ALMOSTOUTOFDATE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-773">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="76b19-773">Message:</span></span>
</td>
<td ><span data-ttu-id="76b19-774">
<b>La plataforma pronto estará des actualizada. Descargue la plataforma más reciente para mantener la protección actualizada.</b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-774">
<b>The platform will soon be out of date. Download the latest platform to maintain up-to-date protection.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-775">Descripción:</span><span class="sxs-lookup"><span data-stu-id="76b19-775">Description:</span></span>
</td>
<td >
<span data-ttu-id="76b19-776">Antivirus de Microsoft Defender pronto necesitará una versión de plataforma más reciente para admitir versiones futuras del motor de antimalware.</span><span class="sxs-lookup"><span data-stu-id="76b19-776">Microsoft Defender Antivirus will soon require a newer platform version to support future versions of the antimalware engine.</span></span> <span data-ttu-id="76b19-777">Descargue la plataforma Antivirus de Microsoft Defender para mantener el mejor nivel de protección disponible.</span><span class="sxs-lookup"><span data-stu-id="76b19-777">Download the latest Microsoft Defender Antivirus platform to maintain the best level of protection available.</span></span>
<dl><span data-ttu-id="76b19-778">
<dt>Versión actual de la plataforma: &lt; versión actual de la plataforma&gt;</dt>
</span><span class="sxs-lookup"><span data-stu-id="76b19-778">
<dt>Current Platform Version: &lt;Current platform version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="76b19-779">Identificador de evento: 2010</span><span class="sxs-lookup"><span data-stu-id="76b19-779">Event ID: 2010</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="76b19-780">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="76b19-780">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="76b19-781">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_UPDATED </b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-781">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_UPDATED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-782">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="76b19-782">Message:</span></span>
</td>
<td ><span data-ttu-id="76b19-783">
<b>El motor de antimalware usaba el servicio de firma dinámica para obtener definiciones adicionales. </b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-783">
<b>The antimalware engine used the Dynamic Signature Service to get additional definitions. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-784">Descripción:</span><span class="sxs-lookup"><span data-stu-id="76b19-784">Description:</span></span>
</td>
<td >
<span data-ttu-id="76b19-785">Antivirus de Microsoft Defender <i>servicio de firma dinámica</i> para recuperar firmas adicionales para ayudar a proteger el equipo.</span><span class="sxs-lookup"><span data-stu-id="76b19-785">Microsoft Defender Antivirus used <i>Dynamic Signature Service</i> to retrieve additional signatures to help protect your machine.</span></span>
<dl><span data-ttu-id="76b19-786">
<dt>Versión de firma actual: &lt; Versión de &gt; firma actual</dt> 
<dt> Tipo de firma: Tipo de firma , &lt; por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="76b19-786">
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Signature Type: &lt;Signature type&gt;, for example:</span></span> <ul>
<li><span data-ttu-id="76b19-787">Antivirus</span><span class="sxs-lookup"><span data-stu-id="76b19-787">Antivirus</span></span></li>
<li><span data-ttu-id="76b19-788">Antispyware</span><span class="sxs-lookup"><span data-stu-id="76b19-788">Antispyware</span></span></li>
<li><span data-ttu-id="76b19-789">Antimalware</span><span class="sxs-lookup"><span data-stu-id="76b19-789">Antimalware</span></span></li>
<li><span data-ttu-id="76b19-790">Sistema de inspección de red</span><span class="sxs-lookup"><span data-stu-id="76b19-790">Network Inspection System</span></span></li>
</ul><span data-ttu-id="76b19-791">
</dt>
<dt>Versión actual del motor: &lt; Versión actual &gt; del motor</dt> 
<dt> Tipo de firma dinámica: Tipo de firma &lt; dinámica , por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="76b19-791">
</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Dynamic Signature Type: &lt;Dynamic signature type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="76b19-792">Versión</span><span class="sxs-lookup"><span data-stu-id="76b19-792">Version</span></span></li>
<li><span data-ttu-id="76b19-793">Timestamp</span><span class="sxs-lookup"><span data-stu-id="76b19-793">Timestamp</span></span></li>
<li><span data-ttu-id="76b19-794">Sin límite</span><span class="sxs-lookup"><span data-stu-id="76b19-794">No limit</span></span></li>
<li><span data-ttu-id="76b19-795">Duración</span><span class="sxs-lookup"><span data-stu-id="76b19-795">Duration</span></span></li>
</ul><span data-ttu-id="76b19-796">
</dt>
<dt>Ruta de persistencia: &lt; Path &gt; </dt>
<dt>Dynamic Signature Version: &lt; Version number &gt; </dt>Dynamic Signature Compilation
<dt>Timestamp: &lt; &gt; Timestamp</dt> 
<dt> Persistence Limit Type: &lt; Persistence limit type , for &gt; example:</span><span class="sxs-lookup"><span data-stu-id="76b19-796">
</dt>
<dt>Persistence Path: &lt;Path&gt;</dt>
<dt>Dynamic Signature Version: &lt;Version number&gt;</dt>
<dt>Dynamic Signature Compilation Timestamp: &lt;Timestamp&gt;</dt>
<dt>Persistence Limit Type: &lt;Persistence limit type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="76b19-797">Versión de VDM</span><span class="sxs-lookup"><span data-stu-id="76b19-797">VDM version</span></span></li>
<li><span data-ttu-id="76b19-798">Timestamp</span><span class="sxs-lookup"><span data-stu-id="76b19-798">Timestamp</span></span></li>
<li><span data-ttu-id="76b19-799">Sin límite</span><span class="sxs-lookup"><span data-stu-id="76b19-799">No limit</span></span></li>
</ul><span data-ttu-id="76b19-800">
</dt>
<dt>Límite de persistencia: límite de persistencia de la firma fastpath.</dt>
</span><span class="sxs-lookup"><span data-stu-id="76b19-800">
</dt>
<dt>Persistence Limit: Persistence limit of the fastpath signature.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="76b19-801">Identificador de evento: 2011</span><span class="sxs-lookup"><span data-stu-id="76b19-801">Event ID: 2011</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="76b19-802">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="76b19-802">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="76b19-803">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_DELETED </b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-803">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_DELETED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-804">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="76b19-804">Message:</span></span>
</td>
<td ><span data-ttu-id="76b19-805">
<b>El servicio de firma dinámica eliminó las definiciones dinámicas des actualizadas. </b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-805">
<b>The Dynamic Signature Service deleted the out-of-date dynamic definitions. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-806">Descripción:</span><span class="sxs-lookup"><span data-stu-id="76b19-806">Description:</span></span>
</td>
<td >
<span data-ttu-id="76b19-807">Antivirus de Microsoft Defender <i>servicio de firma dinámica para</i> descartar firmas obsoletas.</span><span class="sxs-lookup"><span data-stu-id="76b19-807">Microsoft Defender Antivirus used <i>Dynamic Signature Service</i> to discard obsolete signatures.</span></span>
<dl><span data-ttu-id="76b19-808">
<dt>Versión de firma actual: &lt; Versión de &gt; firma actual</dt> 
<dt> Tipo de firma: Tipo de firma , &lt; por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="76b19-808">
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Signature Type: &lt;Signature type&gt;, for example:</span></span> <ul>
<li><span data-ttu-id="76b19-809">Antivirus</span><span class="sxs-lookup"><span data-stu-id="76b19-809">Antivirus</span></span></li>
<li><span data-ttu-id="76b19-810">Antispyware</span><span class="sxs-lookup"><span data-stu-id="76b19-810">Antispyware</span></span></li>
<li><span data-ttu-id="76b19-811">Antimalware</span><span class="sxs-lookup"><span data-stu-id="76b19-811">Antimalware</span></span></li>
<li><span data-ttu-id="76b19-812">Sistema de inspección de red</span><span class="sxs-lookup"><span data-stu-id="76b19-812">Network Inspection System</span></span></li>
</ul><span data-ttu-id="76b19-813">
</dt>
<dt>Versión actual del motor: &lt; Versión actual &gt; del motor</dt> 
<dt> Tipo de firma dinámica: Tipo de firma &lt; dinámica , por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="76b19-813">
</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Dynamic Signature Type: &lt;Dynamic signature type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="76b19-814">Versión</span><span class="sxs-lookup"><span data-stu-id="76b19-814">Version</span></span></li>
<li><span data-ttu-id="76b19-815">Timestamp</span><span class="sxs-lookup"><span data-stu-id="76b19-815">Timestamp</span></span></li>
<li><span data-ttu-id="76b19-816">Sin límite</span><span class="sxs-lookup"><span data-stu-id="76b19-816">No limit</span></span></li>
<li><span data-ttu-id="76b19-817">Duración</span><span class="sxs-lookup"><span data-stu-id="76b19-817">Duration</span></span></li>
</ul><span data-ttu-id="76b19-818">
</dt>
<dt>Ruta de persistencia: &lt; Path &gt; </dt>
<dt>Dynamic Signature Version: &lt; Version &gt; number</dt>Dynamic Signature Compilation
<dt>Timestamp: &lt; Timestamp &gt; </dt>Removal
<dt>Reason:</dt> 
<dt> Persistence Limit Type: &lt; Persistence limit type , for &gt; example:</span><span class="sxs-lookup"><span data-stu-id="76b19-818">
</dt>
<dt>Persistence Path: &lt;Path&gt;</dt>
<dt>Dynamic Signature Version: &lt;Version number&gt;</dt>
<dt>Dynamic Signature Compilation Timestamp: &lt;Timestamp&gt;</dt>
<dt>Removal Reason:</dt>
<dt>Persistence Limit Type: &lt;Persistence limit type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="76b19-819">Versión de VDM</span><span class="sxs-lookup"><span data-stu-id="76b19-819">VDM version</span></span></li>
<li><span data-ttu-id="76b19-820">Timestamp</span><span class="sxs-lookup"><span data-stu-id="76b19-820">Timestamp</span></span></li>
<li><span data-ttu-id="76b19-821">Sin límite</span><span class="sxs-lookup"><span data-stu-id="76b19-821">No limit</span></span></li>
</ul><span data-ttu-id="76b19-822">
</dt>
<dt>Límite de persistencia: límite de persistencia de la firma fastpath.</dt>
</span><span class="sxs-lookup"><span data-stu-id="76b19-822">
</dt>
<dt>Persistence Limit: Persistence limit of the fastpath signature.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-823">Acción del usuario:</span><span class="sxs-lookup"><span data-stu-id="76b19-823">User action:</span></span>
</td>
<td >
<span data-ttu-id="76b19-824">No es necesario realizar ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="76b19-824">No action is necessary.</span></span> <span data-ttu-id="76b19-825">El Antivirus de Microsoft Defender está en buen estado.</span><span class="sxs-lookup"><span data-stu-id="76b19-825">The Microsoft Defender Antivirus client is in a healthy state.</span></span> <span data-ttu-id="76b19-826">Este evento se notifica cuando el servicio de firma dinámica elimina correctamente definiciones dinámicas des actualizadas.</span><span class="sxs-lookup"><span data-stu-id="76b19-826">This event is reported when the Dynamic Signature Service successfully deletes out-of-date dynamic definitions.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="76b19-827">Identificador de evento: 2012</span><span class="sxs-lookup"><span data-stu-id="76b19-827">Event ID: 2012</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="76b19-828">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="76b19-828">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="76b19-829">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_UPDATE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-829">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_UPDATE_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-830">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="76b19-830">Message:</span></span>
</td>
<td ><span data-ttu-id="76b19-831">
<b>El motor de antimalware encontró un error al intentar usar el servicio de firma dinámica. </b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-831">
<b>The antimalware engine encountered an error when trying to use the Dynamic Signature Service. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-832">Descripción:</span><span class="sxs-lookup"><span data-stu-id="76b19-832">Description:</span></span>
</td>
<td >
<span data-ttu-id="76b19-833">Antivirus de Microsoft Defender ha encontrado un error al intentar usar <i>el servicio de firma dinámica</i>.</span><span class="sxs-lookup"><span data-stu-id="76b19-833">Microsoft Defender Antivirus has encountered an error trying to use <i>Dynamic Signature Service</i>.</span></span>
<dl><span data-ttu-id="76b19-834">
<dt>Versión de firma actual: &lt; Versión de &gt; firma actual</dt> 
<dt> Tipo de firma: Tipo de firma , &lt; por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="76b19-834">
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Signature Type: &lt;Signature type&gt;, for example:</span></span> <ul>
<li><span data-ttu-id="76b19-835">Antivirus</span><span class="sxs-lookup"><span data-stu-id="76b19-835">Antivirus</span></span></li>
<li><span data-ttu-id="76b19-836">Antispyware</span><span class="sxs-lookup"><span data-stu-id="76b19-836">Antispyware</span></span></li>
<li><span data-ttu-id="76b19-837">Antimalware</span><span class="sxs-lookup"><span data-stu-id="76b19-837">Antimalware</span></span></li>
<li><span data-ttu-id="76b19-838">Sistema de inspección de red</span><span class="sxs-lookup"><span data-stu-id="76b19-838">Network Inspection System</span></span></li>
</ul><span data-ttu-id="76b19-839">
</dt>
<dt>Versión actual del motor: &lt; Versión del &gt; motor actual</dt>
<dt>Código de error: Código de error &lt; Código de resultado asociado con el estado de &gt; amenaza. Valores HRESULT estándar.</dt> 
<dt>Descripción del error: &lt; Descripción del error &gt; Descripción del error.</dt> 
<dt> Tipo de firma dinámica: &lt; Tipo de firma dinámica , por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="76b19-839">
</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Dynamic Signature Type: &lt;Dynamic signature type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="76b19-840">Versión</span><span class="sxs-lookup"><span data-stu-id="76b19-840">Version</span></span></li>
<li><span data-ttu-id="76b19-841">Timestamp</span><span class="sxs-lookup"><span data-stu-id="76b19-841">Timestamp</span></span></li>
<li><span data-ttu-id="76b19-842">Sin límite</span><span class="sxs-lookup"><span data-stu-id="76b19-842">No limit</span></span></li>
<li><span data-ttu-id="76b19-843">Duración</span><span class="sxs-lookup"><span data-stu-id="76b19-843">Duration</span></span></li>
</ul><span data-ttu-id="76b19-844">
</dt>
<dt>Ruta de persistencia: &lt; Path &gt; </dt>
<dt>Dynamic Signature Version: &lt; Version number &gt; </dt>Dynamic Signature Compilation
<dt>Timestamp: &lt; &gt; Timestamp</dt> 
<dt> Persistence Limit Type: &lt; Persistence limit type , for &gt; example:</span><span class="sxs-lookup"><span data-stu-id="76b19-844">
</dt>
<dt>Persistence Path: &lt;Path&gt;</dt>
<dt>Dynamic Signature Version: &lt;Version number&gt;</dt>
<dt>Dynamic Signature Compilation Timestamp: &lt;Timestamp&gt;</dt>
<dt>Persistence Limit Type: &lt;Persistence limit type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="76b19-845">Versión de VDM</span><span class="sxs-lookup"><span data-stu-id="76b19-845">VDM version</span></span></li>
<li><span data-ttu-id="76b19-846">Timestamp</span><span class="sxs-lookup"><span data-stu-id="76b19-846">Timestamp</span></span></li>
<li><span data-ttu-id="76b19-847">Sin límite</span><span class="sxs-lookup"><span data-stu-id="76b19-847">No limit</span></span></li>
</ul><span data-ttu-id="76b19-848">
</dt>
<dt>Límite de persistencia: límite de persistencia de la firma fastpath.</dt>
</span><span class="sxs-lookup"><span data-stu-id="76b19-848">
</dt>
<dt>Persistence Limit: Persistence limit of the fastpath signature.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-849">Acción del usuario:</span><span class="sxs-lookup"><span data-stu-id="76b19-849">User action:</span></span>
</td>
<td >
<span data-ttu-id="76b19-850">Comprueba la configuración de conectividad a Internet.</span><span class="sxs-lookup"><span data-stu-id="76b19-850">Check your Internet connectivity settings.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="76b19-851">Identificador de evento: 2013</span><span class="sxs-lookup"><span data-stu-id="76b19-851">Event ID: 2013</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="76b19-852">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="76b19-852">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="76b19-853">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_DELETED_ALL </b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-853">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_DELETED_ALL </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-854">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="76b19-854">Message:</span></span>
</td>
<td ><span data-ttu-id="76b19-855">
<b>El servicio de firma dinámica eliminó todas las definiciones dinámicas. </b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-855">
<b>The Dynamic Signature Service deleted all dynamic definitions. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-856">Descripción:</span><span class="sxs-lookup"><span data-stu-id="76b19-856">Description:</span></span>
</td>
<td >
<span data-ttu-id="76b19-857">Antivirus de Microsoft Defender descarta todas las firmas <i>del servicio de firma</i> dinámica.</span><span class="sxs-lookup"><span data-stu-id="76b19-857">Microsoft Defender Antivirus discarded all <i>Dynamic Signature Service</i> signatures.</span></span>
<dl><span data-ttu-id="76b19-858">
<dt>Versión actual de la firma: &lt; versión actual de la firma&gt;</dt>
</span><span class="sxs-lookup"><span data-stu-id="76b19-858">
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="76b19-859">Identificador de evento: 2020</span><span class="sxs-lookup"><span data-stu-id="76b19-859">Event ID: 2020</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="76b19-860">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="76b19-860">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="76b19-861">
<b>MALWAREPROTECTION_CLOUD_CLEAN_RESTORE_FILE_DOWNLOADED </b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-861">
<b>MALWAREPROTECTION_CLOUD_CLEAN_RESTORE_FILE_DOWNLOADED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-862">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="76b19-862">Message:</span></span>
</td>
<td ><span data-ttu-id="76b19-863">
<b>El motor de antimalware descargó un archivo limpio. </b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-863">
<b>The antimalware engine downloaded a clean file. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-864">Descripción:</span><span class="sxs-lookup"><span data-stu-id="76b19-864">Description:</span></span>
</td>
<td >
<span data-ttu-id="76b19-865">Antivirus de Microsoft Defender descargado un archivo limpio.</span><span class="sxs-lookup"><span data-stu-id="76b19-865">Microsoft Defender Antivirus downloaded a clean file.</span></span>
<dl><span data-ttu-id="76b19-866">
<dt>Nombre de archivo: &lt; Nombre de &gt; archivo Nombre del archivo.</dt> 
<dt>Versión de firma actual: &lt; Versión actual &gt; del motor</dt>
<dt>de firma Actual: versión actual del &lt; motor &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="76b19-866">
<dt>Filename: &lt;File name&gt; Name of the file.</dt>
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="76b19-867">Identificador de evento: 2021</span><span class="sxs-lookup"><span data-stu-id="76b19-867">Event ID: 2021</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="76b19-868">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="76b19-868">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="76b19-869">
<b>MALWAREPROTECTION_CLOUD_CLEAN_RESTORE_FILE_DOWNLOAD_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-869">
<b>MALWAREPROTECTION_CLOUD_CLEAN_RESTORE_FILE_DOWNLOAD_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-870">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="76b19-870">Message:</span></span>
</td>
<td ><span data-ttu-id="76b19-871">
<b>El motor de antimalware no pudo descargar un archivo limpio. </b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-871">
<b>The antimalware engine failed to download a clean file. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-872">Descripción:</span><span class="sxs-lookup"><span data-stu-id="76b19-872">Description:</span></span>
</td>
<td >
<span data-ttu-id="76b19-873">Antivirus de Microsoft Defender ha encontrado un error al intentar descargar un archivo limpio.</span><span class="sxs-lookup"><span data-stu-id="76b19-873">Microsoft Defender Antivirus has encountered an error trying to download a clean file.</span></span>
<dl><span data-ttu-id="76b19-874">
<dt>Nombre de archivo: &lt; Nombre de &gt; archivo Nombre del archivo.</dt> 
<dt>Versión de firma actual: &lt; Versión de &gt; firma actual</dt>
<dt>Versión actual del motor: Versión actual &lt; del &gt; </dt>motor Código de error: Código de
<dt>error Código de resultado asociado con el estado de &lt; &gt; amenaza. Valores HRESULT estándar.</dt> 
<dt>Descripción del error: &lt; Descripción del error &gt; Descripción del error.</dt>
</span><span class="sxs-lookup"><span data-stu-id="76b19-874">
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
<span data-ttu-id="76b19-875">Acción del usuario:</span><span class="sxs-lookup"><span data-stu-id="76b19-875">User action:</span></span>
</td>
<td >
<span data-ttu-id="76b19-876">Comprueba la configuración de conectividad a Internet.</span><span class="sxs-lookup"><span data-stu-id="76b19-876">Check your Internet connectivity settings.</span></span>
<span data-ttu-id="76b19-877">El Antivirus de Microsoft Defender encontró un error al usar el servicio de firma dinámica para descargar las definiciones más recientes en una amenaza específica.</span><span class="sxs-lookup"><span data-stu-id="76b19-877">The Microsoft Defender Antivirus client encountered an error when using the Dynamic Signature Service to download the latest definitions to a specific threat.</span></span> <span data-ttu-id="76b19-878">Es probable que este error se deba a un problema de conectividad de red.</span><span class="sxs-lookup"><span data-stu-id="76b19-878">This error is likely caused by a network connectivity issue.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="76b19-879">Identificador de evento: 2030</span><span class="sxs-lookup"><span data-stu-id="76b19-879">Event ID: 2030</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="76b19-880">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="76b19-880">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="76b19-881">
<b>MALWAREPROTECTION_OFFLINE_SCAN_INSTALLED</b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-881">
<b>MALWAREPROTECTION_OFFLINE_SCAN_INSTALLED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-882">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="76b19-882">Message:</span></span>
</td>
<td ><span data-ttu-id="76b19-883">
<b>El motor de antimalware se descargó y está configurado para ejecutarse sin conexión en el siguiente reinicio del sistema.</b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-883">
<b>The antimalware engine was downloaded and is configured to run offline on the next system restart.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-884">Descripción:</span><span class="sxs-lookup"><span data-stu-id="76b19-884">Description:</span></span>
</td>
<td >
<span data-ttu-id="76b19-885">Antivirus de Microsoft Defender descargado y configurado antivirus sin conexión para que se ejecute en el siguiente reinicio.</span><span class="sxs-lookup"><span data-stu-id="76b19-885">Microsoft Defender Antivirus downloaded and configured offline antivirus to run on the next reboot.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="76b19-886">Identificador de evento: 2031</span><span class="sxs-lookup"><span data-stu-id="76b19-886">Event ID: 2031</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="76b19-887">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="76b19-887">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="76b19-888">
<b>MALWAREPROTECTION_OFFLINE_SCAN_INSTALL_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-888">
<b>MALWAREPROTECTION_OFFLINE_SCAN_INSTALL_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-889">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="76b19-889">Message:</span></span>
</td>
<td ><span data-ttu-id="76b19-890">
<b>El motor de antimalware no pudo descargar ni configurar un examen sin conexión.</b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-890">
<b>The antimalware engine was unable to download and configure an offline scan.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-891">Descripción:</span><span class="sxs-lookup"><span data-stu-id="76b19-891">Description:</span></span>
</td>
<td >
<span data-ttu-id="76b19-892">Antivirus de Microsoft Defender ha encontrado un error al intentar descargar y configurar antivirus sin conexión.</span><span class="sxs-lookup"><span data-stu-id="76b19-892">Microsoft Defender Antivirus has encountered an error trying to download and configure offline antivirus.</span></span>
<dl><span data-ttu-id="76b19-893">
<dt>Código de error: &lt; Código de error &gt; Código de resultado asociado con el estado de amenaza. Valores HRESULT estándar.</dt> 
<dt>Descripción del error: &lt; Descripción del error &gt; Descripción del error.</dt>
</span><span class="sxs-lookup"><span data-stu-id="76b19-893">
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="76b19-894">Identificador de evento: 2040</span><span class="sxs-lookup"><span data-stu-id="76b19-894">Event ID: 2040</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="76b19-895">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="76b19-895">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="76b19-896">
<b>MALWAREPROTECTION_OS_EXPIRING </b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-896">
<b>MALWAREPROTECTION_OS_EXPIRING </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-897">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="76b19-897">Message:</span></span>
</td>
<td ><span data-ttu-id="76b19-898">
<b>La compatibilidad con antimalware para esta versión del sistema operativo finalizará próximamente. </b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-898">
<b>Antimalware support for this operating system version will soon end. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-899">Descripción:</span><span class="sxs-lookup"><span data-stu-id="76b19-899">Description:</span></span>
</td>
<td >
<span data-ttu-id="76b19-900">La compatibilidad con el sistema operativo expirará en breve.</span><span class="sxs-lookup"><span data-stu-id="76b19-900">The support for your operating system will expire shortly.</span></span> <span data-ttu-id="76b19-901">Ejecutar Antivirus de Microsoft Defender en un sistema operativo no compatible no es una solución adecuada para protegerse contra amenazas.</span><span class="sxs-lookup"><span data-stu-id="76b19-901">Running Microsoft Defender Antivirus on an out of support operating system is not an adequate solution to protect against threats.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="76b19-902">Identificador de evento: 2041</span><span class="sxs-lookup"><span data-stu-id="76b19-902">Event ID: 2041</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="76b19-903">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="76b19-903">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="76b19-904">
<b>MALWAREPROTECTION_OS_EOL </b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-904">
<b>MALWAREPROTECTION_OS_EOL </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-905">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="76b19-905">Message:</span></span>
</td>
<td ><span data-ttu-id="76b19-906">
<b>La compatibilidad con antimalware para este sistema operativo ha finalizado. Debe actualizar el sistema operativo para que la compatibilidad continúe. </b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-906">
<b>Antimalware support for this operating system has ended. You must upgrade the operating system for continued support. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-907">Descripción:</span><span class="sxs-lookup"><span data-stu-id="76b19-907">Description:</span></span>
</td>
<td >
<span data-ttu-id="76b19-908">La compatibilidad con el sistema operativo ha expirado.</span><span class="sxs-lookup"><span data-stu-id="76b19-908">The support for your operating system has expired.</span></span> <span data-ttu-id="76b19-909">Ejecutar Antivirus de Microsoft Defender en un sistema operativo no compatible no es una solución adecuada para protegerse contra amenazas.</span><span class="sxs-lookup"><span data-stu-id="76b19-909">Running Microsoft Defender Antivirus on an out of support operating system is not an adequate solution to protect against threats.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="76b19-910">Identificador de evento: 2042</span><span class="sxs-lookup"><span data-stu-id="76b19-910">Event ID: 2042</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="76b19-911">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="76b19-911">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="76b19-912">
<b>MALWAREPROTECTION_PROTECTION_EOL </b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-912">
<b>MALWAREPROTECTION_PROTECTION_EOL </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-913">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="76b19-913">Message:</span></span>
</td>
<td ><span data-ttu-id="76b19-914">
<b>El motor de antimalware ya no es compatible con este sistema operativo y ya no protege el sistema contra malware. </b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-914">
<b>The antimalware engine no longer supports this operating system, and is no longer protecting your system from malware. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-915">Descripción:</span><span class="sxs-lookup"><span data-stu-id="76b19-915">Description:</span></span>
</td>
<td >
<span data-ttu-id="76b19-916">La compatibilidad con el sistema operativo ha expirado.</span><span class="sxs-lookup"><span data-stu-id="76b19-916">The support for your operating system has expired.</span></span> <span data-ttu-id="76b19-917">Antivirus de Microsoft Defender ya no se admite en el sistema operativo, ha dejado de funcionar y no protege contra amenazas de malware.</span><span class="sxs-lookup"><span data-stu-id="76b19-917">Microsoft Defender Antivirus is no longer supported on your operating system, has stopped functioning, and is not protecting against malware threats.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="76b19-918">Identificador de evento: 3002</span><span class="sxs-lookup"><span data-stu-id="76b19-918">Event ID: 3002</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="76b19-919">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="76b19-919">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="76b19-920">
<b>MALWAREPROTECTION_RTP_FEATURE_FAILURE </b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-920">
<b>MALWAREPROTECTION_RTP_FEATURE_FAILURE </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-921">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="76b19-921">Message:</span></span>
</td>
<td ><span data-ttu-id="76b19-922">
<b>La protección en tiempo real encontró un error y produjo un error.</b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-922">
<b>Real-time protection encountered an error and failed.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-923">Descripción:</span><span class="sxs-lookup"><span data-stu-id="76b19-923">Description:</span></span>
</td>
<td >
<span data-ttu-id="76b19-924">Antivirus de Microsoft Defender Real-Time de protección ha encontrado un error y ha producido un error.</span><span class="sxs-lookup"><span data-stu-id="76b19-924">Microsoft Defender Antivirus Real-Time Protection feature has encountered an error and failed.</span></span>
<dl><span data-ttu-id="76b19-925">
<dt>Característica: &lt; Característica , por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="76b19-925">
<dt>Feature: &lt;Feature&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="76b19-926">En Access</span><span class="sxs-lookup"><span data-stu-id="76b19-926">On Access</span></span></li>
<li><span data-ttu-id="76b19-927">Descargas de Internet Explorer y datos adjuntos de Microsoft Outlook Express</span><span class="sxs-lookup"><span data-stu-id="76b19-927">Internet Explorer downloads and Microsoft Outlook Express attachments</span></span></li>
<li><span data-ttu-id="76b19-928">Supervisión del comportamiento</span><span class="sxs-lookup"><span data-stu-id="76b19-928">Behavior monitoring</span></span></li>
<li><span data-ttu-id="76b19-929">Sistema de inspección de red</span><span class="sxs-lookup"><span data-stu-id="76b19-929">Network Inspection System</span></span></li>
</ul><span data-ttu-id="76b19-930">
</dt>
<dt>Código de error: &lt; Código de error &gt; Código de resultado asociado con el estado de amenaza. Valores HRESULT estándar.</dt> 
<dt>Descripción del error: &lt; Descripción del error &gt; Descripción del error.</dt> 
<dt>Motivo: el motivo Antivirus de Microsoft Defender protección en tiempo real ha reiniciado una característica.</dt>
</span><span class="sxs-lookup"><span data-stu-id="76b19-930">
</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Reason: The reason Microsoft Defender Antivirus real-time protection has restarted a feature.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-931">Acción del usuario:</span><span class="sxs-lookup"><span data-stu-id="76b19-931">User action:</span></span>
</td>
<td >
<span data-ttu-id="76b19-932">Debe reiniciar el sistema y, a continuación, ejecutar un examen completo porque&#39;es posible que el sistema no se protegió durante algún tiempo.</span><span class="sxs-lookup"><span data-stu-id="76b19-932">You should restart the system then run a full scan because it&#39;s possible the system was not protected for some time.</span></span>
<span data-ttu-id="76b19-933">La Antivirus de Microsoft Defender cliente&#39;la característica de protección en tiempo real encontró un error porque uno de los servicios no se pudo iniciar.</span><span class="sxs-lookup"><span data-stu-id="76b19-933">The Microsoft Defender Antivirus client&#39;s real-time protection feature encountered an error because one of the services failed to start.</span></span> <span data-ttu-id="76b19-934">Si le sigue un identificador de evento 3007, el error fue temporal y el cliente antimalware se recuperó del error.</span><span class="sxs-lookup"><span data-stu-id="76b19-934">If it is followed by a 3007 event ID, the failure was temporary and the antimalware client recovered from the failure.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="76b19-935">Identificador de evento: 3007</span><span class="sxs-lookup"><span data-stu-id="76b19-935">Event ID: 3007</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="76b19-936">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="76b19-936">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="76b19-937">
<b>MALWAREPROTECTION_RTP_FEATURE_RECOVERED</b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-937">
<b>MALWAREPROTECTION_RTP_FEATURE_RECOVERED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-938">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="76b19-938">Message:</span></span>
</td>
<td ><span data-ttu-id="76b19-939">
<b>Protección en tiempo real recuperada de un error. Se recomienda ejecutar un examen completo del sistema cuando vea este error. </b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-939">
<b>Real-time protection recovered from a failure. We recommend running a full system scan when you see this error. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-940">Descripción:</span><span class="sxs-lookup"><span data-stu-id="76b19-940">Description:</span></span>
</td>
<td >
<span data-ttu-id="76b19-941">Antivirus de Microsoft Defender Protección en tiempo real ha reiniciado una característica.</span><span class="sxs-lookup"><span data-stu-id="76b19-941">Microsoft Defender Antivirus Real-time Protection has restarted a feature.</span></span> <span data-ttu-id="76b19-942">Se recomienda ejecutar un examen completo del sistema para detectar los elementos que se hayan perdido mientras este agente estaba abajo.</span><span class="sxs-lookup"><span data-stu-id="76b19-942">It is recommended that you run a full system scan to detect any items that may have been missed while this agent was down.</span></span>
<dl><span data-ttu-id="76b19-943">
<dt>Característica: &lt; Característica , por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="76b19-943">
<dt>Feature: &lt;Feature&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="76b19-944">En Access</span><span class="sxs-lookup"><span data-stu-id="76b19-944">On Access</span></span></li>
<li><span data-ttu-id="76b19-945">Descargas de IE y Outlook datos adjuntos de Express</span><span class="sxs-lookup"><span data-stu-id="76b19-945">IE downloads and Outlook Express attachments</span></span></li>
<li><span data-ttu-id="76b19-946">Supervisión del comportamiento</span><span class="sxs-lookup"><span data-stu-id="76b19-946">Behavior monitoring</span></span></li>
<li><span data-ttu-id="76b19-947">Sistema de inspección de red</span><span class="sxs-lookup"><span data-stu-id="76b19-947">Network Inspection System</span></span></li>
</ul><span data-ttu-id="76b19-948">
</dt>
<dt>Motivo: el motivo Antivirus de Microsoft Defender protección en tiempo real ha reiniciado una característica.</dt>
</span><span class="sxs-lookup"><span data-stu-id="76b19-948">
</dt>
<dt>Reason: The reason Microsoft Defender Antivirus real-time protection has restarted a feature.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-949">Acción del usuario:</span><span class="sxs-lookup"><span data-stu-id="76b19-949">User action:</span></span>
</td>
<td >
<span data-ttu-id="76b19-950">Se ha reiniciado la característica de protección en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="76b19-950">The real-time protection feature has restarted.</span></span> <span data-ttu-id="76b19-951">Si este evento se produce de nuevo, póngase en contacto <a href="https://go.microsoft.com/fwlink/?LinkId=215491">con el Soporte técnico de Microsoft</a>.</span><span class="sxs-lookup"><span data-stu-id="76b19-951">If this event happens again, contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="76b19-952">Identificador de evento: 5000</span><span class="sxs-lookup"><span data-stu-id="76b19-952">Event ID: 5000</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="76b19-953">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="76b19-953">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="76b19-954">
<b>MALWAREPROTECTION_RTP_ENABLED </b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-954">
<b>MALWAREPROTECTION_RTP_ENABLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-955">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="76b19-955">Message:</span></span>
</td>
<td ><span data-ttu-id="76b19-956">
<b>La protección en tiempo real está habilitada. </b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-956">
<b>Real-time protection is enabled. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-957">Descripción:</span><span class="sxs-lookup"><span data-stu-id="76b19-957">Description:</span></span>
</td>
<td >
<span data-ttu-id="76b19-958">Antivirus de Microsoft Defender de protección en tiempo real en busca de malware y otro software potencialmente no deseado.</span><span class="sxs-lookup"><span data-stu-id="76b19-958">Microsoft Defender Antivirus real-time protection scanning for malware and other potentially unwanted software was enabled.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="76b19-959">Identificador de evento: 5001</span><span class="sxs-lookup"><span data-stu-id="76b19-959">Event ID: 5001</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="76b19-960">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="76b19-960">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="76b19-961">
<b>MALWAREPROTECTION_RTP_DISABLED</b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-961">
<b>MALWAREPROTECTION_RTP_DISABLED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-962">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="76b19-962">Message:</span></span>
</td>
<td ><span data-ttu-id="76b19-963">
<b>La protección en tiempo real está deshabilitada. </b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-963">
<b>Real-time protection is disabled. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-964">Descripción:</span><span class="sxs-lookup"><span data-stu-id="76b19-964">Description:</span></span>
</td>
<td >
<span data-ttu-id="76b19-965">Antivirus de Microsoft Defender de protección en tiempo real en busca de malware y otro software potencialmente no deseado se deshabilitó.</span><span class="sxs-lookup"><span data-stu-id="76b19-965">Microsoft Defender Antivirus real-time protection scanning for malware and other potentially unwanted software was disabled.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="76b19-966">Identificador de evento: 5004</span><span class="sxs-lookup"><span data-stu-id="76b19-966">Event ID: 5004</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="76b19-967">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="76b19-967">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="76b19-968">
<b>MALWAREPROTECTION_RTP_FEATURE_CONFIGURED </b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-968">
<b>MALWAREPROTECTION_RTP_FEATURE_CONFIGURED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-969">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="76b19-969">Message:</span></span>
</td>
<td ><span data-ttu-id="76b19-970">
<b>La configuración de protección en tiempo real cambió. </b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-970">
<b>The real-time protection configuration changed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-971">Descripción:</span><span class="sxs-lookup"><span data-stu-id="76b19-971">Description:</span></span>
</td>
<td >
<span data-ttu-id="76b19-972">Antivirus de Microsoft Defender configuración de características de protección en tiempo real ha cambiado.</span><span class="sxs-lookup"><span data-stu-id="76b19-972">Microsoft Defender Antivirus real-time protection feature configuration has changed.</span></span>
<dl><span data-ttu-id="76b19-973">
<dt>Característica: &lt; Característica , por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="76b19-973">
<dt>Feature: &lt;Feature&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="76b19-974">En Access</span><span class="sxs-lookup"><span data-stu-id="76b19-974">On Access</span></span></li>
<li><span data-ttu-id="76b19-975">Descargas de IE y Outlook datos adjuntos de Express</span><span class="sxs-lookup"><span data-stu-id="76b19-975">IE downloads and Outlook Express attachments</span></span></li>
<li><span data-ttu-id="76b19-976">Supervisión del comportamiento</span><span class="sxs-lookup"><span data-stu-id="76b19-976">Behavior monitoring</span></span></li>
<li><span data-ttu-id="76b19-977">Sistema de inspección de red</span><span class="sxs-lookup"><span data-stu-id="76b19-977">Network Inspection System</span></span></li>
</ul><span data-ttu-id="76b19-978">
</dt>
<dt>Configuración: </dt>
</span><span class="sxs-lookup"><span data-stu-id="76b19-978">
</dt>
<dt>Configuration: </dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="76b19-979">Identificador de evento: 5007</span><span class="sxs-lookup"><span data-stu-id="76b19-979">Event ID: 5007</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="76b19-980">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="76b19-980">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="76b19-981">
<b>MALWAREPROTECTION_CONFIG_CHANGED </b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-981">
<b>MALWAREPROTECTION_CONFIG_CHANGED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-982">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="76b19-982">Message:</span></span>
</td>
<td ><span data-ttu-id="76b19-983">
<b>Se cambió la configuración de la plataforma antimalware.</b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-983">
<b>The antimalware platform configuration changed.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-984">Descripción:</span><span class="sxs-lookup"><span data-stu-id="76b19-984">Description:</span></span>
</td>
<td >
<span data-ttu-id="76b19-985">Antivirus de Microsoft Defender configuración ha cambiado.</span><span class="sxs-lookup"><span data-stu-id="76b19-985">Microsoft Defender Antivirus configuration has changed.</span></span> <span data-ttu-id="76b19-986">Si se trata de un evento inesperado, debe revisar la configuración, ya que puede ser el resultado de malware.</span><span class="sxs-lookup"><span data-stu-id="76b19-986">If this is an unexpected event, you should review the settings as this may be the result of malware.</span></span>
<dl><span data-ttu-id="76b19-987">
<dt>Valor antiguo: &lt; Número de valor antiguo &gt; Valor de configuración del antivirus anterior.</dt> 
<dt>Nuevo valor: &lt; Nuevo número de valor &gt; Nuevo valor de configuración antivirus.</dt>
</span><span class="sxs-lookup"><span data-stu-id="76b19-987">
<dt>Old value: &lt;Old value number&gt; Old antivirus configuration value.</dt>
<dt>New value: &lt;New value number&gt; New antivirus configuration value.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="76b19-988">Identificador de evento: 5008</span><span class="sxs-lookup"><span data-stu-id="76b19-988">Event ID: 5008</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="76b19-989">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="76b19-989">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="76b19-990">
<b>MALWAREPROTECTION_ENGINE_FAILURE</b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-990">
<b>MALWAREPROTECTION_ENGINE_FAILURE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-991">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="76b19-991">Message:</span></span>
</td>
<td ><span data-ttu-id="76b19-992">
<b>El motor de antimalware encontró un error y produjo un error.</b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-992">
<b>The antimalware engine encountered an error and failed.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-993">Descripción:</span><span class="sxs-lookup"><span data-stu-id="76b19-993">Description:</span></span>
</td>
<td >
<span data-ttu-id="76b19-994">Antivirus de Microsoft Defender motor se ha terminado debido a un error inesperado.</span><span class="sxs-lookup"><span data-stu-id="76b19-994">Microsoft Defender Antivirus engine has been terminated due to an unexpected error.</span></span>
<dl><span data-ttu-id="76b19-995">
<dt>Tipo de error: &lt; Tipo de &gt; error , por ejemplo: Bloquear o bloquear código</dt>de
<dt>excepción: &lt; Código de &gt; error</dt>
<dt>Recurso: &lt; recurso &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="76b19-995">
<dt>Failure Type: &lt;Failure type&gt;, for example: Crash or Hang</dt>
<dt>Exception Code: &lt;Error code&gt;</dt>
<dt>Resource: &lt;Resource&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-996">Acción del usuario:</span><span class="sxs-lookup"><span data-stu-id="76b19-996">User action:</span></span>
</td>
<td >
<span data-ttu-id="76b19-997">Para solucionar este evento:</span><span class="sxs-lookup"><span data-stu-id="76b19-997">To troubleshoot this event:</span></span><ol>
<li><span data-ttu-id="76b19-998">Intente reiniciar el servicio.</span><span class="sxs-lookup"><span data-stu-id="76b19-998">Try to restart the service.</span></span><ul>
<li><span data-ttu-id="76b19-999">Para antimalware, antivirus y spyware, en un símbolo del sistema con privilegios elevados, escriba <b>net stop msmpsvc</b>y, a continuación, escriba <b>net start msmpsvc</b> para reiniciar el motor de antimalware.</span><span class="sxs-lookup"><span data-stu-id="76b19-999">For antimalware, antivirus and spyware, at an elevated command prompt, type <b>net stop msmpsvc</b>, and then type <b>net start msmpsvc</b> to restart the antimalware engine.</span></span></li>
<li><span data-ttu-id="76b19-1000">Para el sistema <i>de</i>inspección de red , en un símbolo del sistema con privilegios elevados, escriba <b>net start nissrv</b>y, a continuación, escriba <b>net start nissrv</b> para reiniciar el motor del sistema de inspección de red mediante el archivo NiSSRV.exe. <i></i></span><span class="sxs-lookup"><span data-stu-id="76b19-1000">For the <i>Network Inspection System</i>, at an elevated command prompt, type <b>net start nissrv</b>, and then type <b>net start nissrv</b> to restart the <i>Network Inspection System</i> engine by using the NiSSRV.exe file.</span></span>
</li>
</ul>
</li>
<li><span data-ttu-id="76b19-1001">Si se produce un error de la misma manera, busque el código de <b></b> error accediendo al Sitio de soporte técnico de <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft</a> y especificando el número de error en el cuadro Búsqueda y póngase en contacto con el Soporte técnico <a href="https://go.microsoft.com/fwlink/?LinkId=215491">de Microsoft</a>.</span><span class="sxs-lookup"><span data-stu-id="76b19-1001">If it fails in the same way, look up the error code by accessing the <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft Support Site</a>  and entering the error number in the <b>Search</b> box, and contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span></li>
</ol>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-1002">Acción del usuario:</span><span class="sxs-lookup"><span data-stu-id="76b19-1002">User action:</span></span>
</td>
<td >
<span data-ttu-id="76b19-1003">El Antivirus de Microsoft Defender cliente se detuvo debido a un error inesperado.</span><span class="sxs-lookup"><span data-stu-id="76b19-1003">The Microsoft Defender Antivirus client engine stopped due to an unexpected error.</span></span>
<span data-ttu-id="76b19-1004">Para solucionar este evento:</span><span class="sxs-lookup"><span data-stu-id="76b19-1004">To troubleshoot this event:</span></span>
<ol>
<li><span data-ttu-id="76b19-1005">Vuelva a ejecutar el examen.</span><span class="sxs-lookup"><span data-stu-id="76b19-1005">Run the scan again.</span></span></li>
<li><span data-ttu-id="76b19-1006">Si se produce un error de la misma manera, vaya <b></b> al sitio de soporte técnico de <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft</a>, escriba el número de error en el cuadro Buscar para buscar el código de error.</span><span class="sxs-lookup"><span data-stu-id="76b19-1006">If it fails in the same way, go to the <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft Support site</a>, enter the error number in the <b>Search</b> box to look for the error code.</span></span></li>
<li><span data-ttu-id="76b19-1007">Contactar al <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Soporte técnico de Microsoft</a>.</span><span class="sxs-lookup"><span data-stu-id="76b19-1007">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="76b19-1008">Identificador de evento: 5009</span><span class="sxs-lookup"><span data-stu-id="76b19-1008">Event ID: 5009</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="76b19-1009">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="76b19-1009">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="76b19-1010">
<b>MALWAREPROTECTION_ANTISPYWARE_ENABLED </b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-1010">
<b>MALWAREPROTECTION_ANTISPYWARE_ENABLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-1011">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="76b19-1011">Message:</span></span>
</td>
<td ><span data-ttu-id="76b19-1012">
<b>El examen de malware y otro software potencialmente no deseado está habilitado. </b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-1012">
<b>Scanning for malware and other potentially unwanted software is enabled. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-1013">Descripción:</span><span class="sxs-lookup"><span data-stu-id="76b19-1013">Description:</span></span>
</td>
<td >
<span data-ttu-id="76b19-1014">Antivirus de Microsoft Defender se ha habilitado el examen de malware y otro software potencialmente no deseado.</span><span class="sxs-lookup"><span data-stu-id="76b19-1014">Microsoft Defender Antivirus scanning for malware and other potentially unwanted software has been enabled.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="76b19-1015">Identificador de evento: 5010</span><span class="sxs-lookup"><span data-stu-id="76b19-1015">Event ID: 5010</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="76b19-1016">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="76b19-1016">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="76b19-1017">
<b>MALWAREPROTECTION_ANTISPYWARE_DISABLED </b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-1017">
<b>MALWAREPROTECTION_ANTISPYWARE_DISABLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-1018">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="76b19-1018">Message:</span></span>
</td>
<td ><span data-ttu-id="76b19-1019">
<b>El examen de malware y otro software potencialmente no deseado está deshabilitado.</b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-1019">
<b>Scanning for malware and other potentially unwanted software is disabled.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-1020">Descripción:</span><span class="sxs-lookup"><span data-stu-id="76b19-1020">Description:</span></span>
</td>
<td >
<span data-ttu-id="76b19-1021">Antivirus de Microsoft Defender de búsqueda de malware y otro software potencialmente no deseado está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="76b19-1021">Microsoft Defender Antivirus scanning for malware and other potentially unwanted software is disabled.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="76b19-1022">Identificador de evento: 5011</span><span class="sxs-lookup"><span data-stu-id="76b19-1022">Event ID: 5011</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="76b19-1023">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="76b19-1023">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="76b19-1024">
<b>MALWAREPROTECTION_ANTIVIRUS_ENABLED</b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-1024">
<b>MALWAREPROTECTION_ANTIVIRUS_ENABLED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-1025">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="76b19-1025">Message:</span></span>
</td>
<td ><span data-ttu-id="76b19-1026">
<b>El examen de virus está habilitado.</b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-1026">
<b>Scanning for viruses is enabled.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-1027">Descripción:</span><span class="sxs-lookup"><span data-stu-id="76b19-1027">Description:</span></span>
</td>
<td >
<span data-ttu-id="76b19-1028">Antivirus de Microsoft Defender se ha habilitado el examen de virus.</span><span class="sxs-lookup"><span data-stu-id="76b19-1028">Microsoft Defender Antivirus scanning for viruses has been enabled.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="76b19-1029">Identificador de evento: 5012</span><span class="sxs-lookup"><span data-stu-id="76b19-1029">Event ID: 5012</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="76b19-1030">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="76b19-1030">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="76b19-1031">
<b>MALWAREPROTECTION_ANTIVIRUS_DISABLED </b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-1031">
<b>MALWAREPROTECTION_ANTIVIRUS_DISABLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-1032">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="76b19-1032">Message:</span></span>
</td>
<td ><span data-ttu-id="76b19-1033">
<b>El examen de virus está deshabilitado. </b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-1033">
<b>Scanning for viruses is disabled. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-1034">Descripción:</span><span class="sxs-lookup"><span data-stu-id="76b19-1034">Description:</span></span>
</td>
<td >
<span data-ttu-id="76b19-1035">Antivirus de Microsoft Defender está deshabilitado el examen de virus.</span><span class="sxs-lookup"><span data-stu-id="76b19-1035">Microsoft Defender Antivirus scanning for viruses is disabled.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="76b19-1036">Identificador de evento: 5100</span><span class="sxs-lookup"><span data-stu-id="76b19-1036">Event ID: 5100</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="76b19-1037">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="76b19-1037">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="76b19-1038">
<b>MALWAREPROTECTION_EXPIRATION_WARNING_STATE </b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-1038">
<b>MALWAREPROTECTION_EXPIRATION_WARNING_STATE </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-1039">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="76b19-1039">Message:</span></span>
</td>
<td ><span data-ttu-id="76b19-1040">
<b>La plataforma antimalware expirará pronto. </b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-1040">
<b>The antimalware platform will expire soon. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-1041">Descripción:</span><span class="sxs-lookup"><span data-stu-id="76b19-1041">Description:</span></span>
</td>
<td >
<span data-ttu-id="76b19-1042">Antivirus de Microsoft Defender ha entrado en un período de gracia y expirará pronto.</span><span class="sxs-lookup"><span data-stu-id="76b19-1042">Microsoft Defender Antivirus has entered a grace period and will soon expire.</span></span> <span data-ttu-id="76b19-1043">Después de expirar, este programa deshabilitará la protección contra virus, spyware y otro software potencialmente no deseado.</span><span class="sxs-lookup"><span data-stu-id="76b19-1043">After expiration, this program will disable protection against viruses, spyware, and other potentially unwanted software.</span></span>
<dl><span data-ttu-id="76b19-1044">
<dt>Motivo de expiración: el Antivirus de Microsoft Defender expirará.</dt> 
<dt>Fecha de expiración: la Antivirus de Microsoft Defender expirará.</dt>
</span><span class="sxs-lookup"><span data-stu-id="76b19-1044">
<dt>Expiration Reason: The reason Microsoft Defender Antivirus will expire.</dt>
<dt>Expiration Date: The date Microsoft Defender Antivirus will expire.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="76b19-1045">Identificador de evento: 5101</span><span class="sxs-lookup"><span data-stu-id="76b19-1045">Event ID: 5101</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="76b19-1046">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="76b19-1046">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="76b19-1047">
<b>MALWAREPROTECTION_DISABLED_EXPIRED_STATE </b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-1047">
<b>MALWAREPROTECTION_DISABLED_EXPIRED_STATE </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-1048">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="76b19-1048">Message:</span></span>
</td>
<td ><span data-ttu-id="76b19-1049">
<b>La plataforma antimalware ha expirado. </b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-1049">
<b>The antimalware platform is expired. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-1050">Descripción:</span><span class="sxs-lookup"><span data-stu-id="76b19-1050">Description:</span></span>
</td>
<td >
<span data-ttu-id="76b19-1051">Antivirus de Microsoft Defender período de gracia ha expirado.</span><span class="sxs-lookup"><span data-stu-id="76b19-1051">Microsoft Defender Antivirus grace period has expired.</span></span> <span data-ttu-id="76b19-1052">La protección contra virus, spyware y otro software potencialmente no deseado está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="76b19-1052">Protection against viruses, spyware, and other potentially unwanted software is disabled.</span></span>
<dl><span data-ttu-id="76b19-1053">
<dt>Motivo de expiración:</dt>
<dt>Fecha de expiración: </dt>Código de error: Código de error Código de resultado asociado con el estado de la 
<dt> &lt; &gt; amenaza. Valores HRESULT estándar.</dt> 
<dt>Descripción del error: &lt; Descripción del error &gt; Descripción del error.</dt>
</span><span class="sxs-lookup"><span data-stu-id="76b19-1053">
<dt>Expiration Reason:</dt>
<dt>Expiration Date: </dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr><span data-ttu-id="76b19-1054">
</table>

<a id="error-codes"></a>
##Antivirus de Microsoft Defender de error de cliente Si Antivirus de Microsoft Defender experimenta algún problema, normalmente le dará un código de error para ayudarle a solucionar el problema.</span><span class="sxs-lookup"><span data-stu-id="76b19-1054">
</table>

<a id="error-codes"></a>
## Microsoft Defender Antivirus client error codes If Microsoft Defender Antivirus experiences any issues it will usually give you an error code to help you troubleshoot the issue.</span></span> <span data-ttu-id="76b19-1055">En la mayoría de los casos, un error significa que hubo un problema al instalar una actualización.</span><span class="sxs-lookup"><span data-stu-id="76b19-1055">Most often an error means there was a problem installing an update.</span></span>
<span data-ttu-id="76b19-1056">En esta sección se proporciona la siguiente información sobre Antivirus de Microsoft Defender errores de cliente.</span><span class="sxs-lookup"><span data-stu-id="76b19-1056">This section provides the following information about Microsoft Defender Antivirus client errors.</span></span>
<span data-ttu-id="76b19-1057">-   El código de error -   El posible motivo del error Consejo sobre qué hacer -   ahora</span><span class="sxs-lookup"><span data-stu-id="76b19-1057">-   The error code -   The possible reason for the error -   Advice on what to do now</span></span>

<span data-ttu-id="76b19-1058">Use la información de estas tablas para ayudar a solucionar Antivirus de Microsoft Defender códigos de error.</span><span class="sxs-lookup"><span data-stu-id="76b19-1058">Use the information in these tables to help troubleshoot Microsoft Defender Antivirus error codes.</span></span>


<table> 
<tr>
<th colspan="2"><span data-ttu-id="76b19-1059">Código de error: 0x80508007</span><span class="sxs-lookup"><span data-stu-id="76b19-1059">Error code: 0x80508007</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="76b19-1060">Mensaje</span><span class="sxs-lookup"><span data-stu-id="76b19-1060">Message</span></span></td>
<td><span data-ttu-id="76b19-1061">
<b>ERR_MP_NO_MEMORY </b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-1061">
<b>ERR_MP_NO_MEMORY </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-1062">Posible motivo</span><span class="sxs-lookup"><span data-stu-id="76b19-1062">Possible reason</span></span>
</td>
<td>
<span data-ttu-id="76b19-1063">Este error indica que es posible que se haya quedo sin memoria.</span><span class="sxs-lookup"><span data-stu-id="76b19-1063">This error indicates that you might have run out of memory.</span></span> 
</td>
</tr>
<tr>
<td><span data-ttu-id="76b19-1064">Solución</span><span class="sxs-lookup"><span data-stu-id="76b19-1064">Resolution</span></span></td>
<td>
<ol>
<li><span data-ttu-id="76b19-1065">Comprueba la memoria disponible en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="76b19-1065">Check the available memory on your device.</span></span></li>
<li><span data-ttu-id="76b19-1066">Cierra todas las aplicaciones no usadas que se estén ejecutando para liberar memoria en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="76b19-1066">Close any unused applications that are running to free up memory on your device.</span></span></li>
<li><span data-ttu-id="76b19-1067">Reinicie el dispositivo y vuelva a ejecutar el examen.</span><span class="sxs-lookup"><span data-stu-id="76b19-1067">Restart the device and run the scan again.</span></span> 
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="76b19-1068">Código de error: 0x8050800C</span><span class="sxs-lookup"><span data-stu-id="76b19-1068">Error code: 0x8050800C</span></span></th>
</tr><tr><td><span data-ttu-id="76b19-1069">Mensaje</span><span class="sxs-lookup"><span data-stu-id="76b19-1069">Message</span></span></td>
<td><span data-ttu-id="76b19-1070"><b>ERR_MP_BAD_INPUT_DATA</b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-1070"><b>ERR_MP_BAD_INPUT_DATA</b>
</span></span></td></tr><tr><td><span data-ttu-id="76b19-1071">Posible motivo</span><span class="sxs-lookup"><span data-stu-id="76b19-1071">Possible reason</span></span></td>
<td>
<span data-ttu-id="76b19-1072">Este error indica que puede haber un problema con el producto de seguridad.</span><span class="sxs-lookup"><span data-stu-id="76b19-1072">This error indicates that there might be a problem with your security product.</span></span>
</td>
</tr><tr><td><span data-ttu-id="76b19-1073">Solución</span><span class="sxs-lookup"><span data-stu-id="76b19-1073">Resolution</span></span></td><td>
<ol>
<li><span data-ttu-id="76b19-1074">Actualice las definiciones.</span><span class="sxs-lookup"><span data-stu-id="76b19-1074">Update the definitions.</span></span> <span data-ttu-id="76b19-1075">Cualquiera de las dos:</span><span class="sxs-lookup"><span data-stu-id="76b19-1075">Either:</span></span><ol>
<li><span data-ttu-id="76b19-1076">Haga clic <b>en el botón Actualizar definiciones</b> de la <b>ficha</b> Actualizar en Antivirus de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="76b19-1076">Click the <b>Update definitions</b> button on the <b>Update</b> tab in Microsoft Defender Antivirus.</span></span> <img src="images/defender-updatedefs2.png" alt="Update definitions in Microsoft Defender Antivirus"/><span data-ttu-id="76b19-1077">O bien</span><span class="sxs-lookup"><span data-stu-id="76b19-1077">Or,</span></span>
</li>
<li><span data-ttu-id="76b19-1078">Descargue las definiciones más recientes del <a href="https://aka.ms/wdsi">Inteligencia de seguridad de Microsoft sitio</a>.</span><span class="sxs-lookup"><span data-stu-id="76b19-1078">Download the latest definitions from the <a href="https://aka.ms/wdsi">Microsoft Security Intelligence site</a>.</span></span>
<span data-ttu-id="76b19-1079">Nota: El tamaño del archivo de definiciones descargado del sitio puede superar los 60 MB y no debe usarse como solución a largo plazo para actualizar definiciones.</span><span class="sxs-lookup"><span data-stu-id="76b19-1079">Note: The size of the definitions file downloaded from the site can exceed 60 MB and should not be used as a long-term solution for updating definitions.</span></span>
</li>
</ol>
</li>
<li><span data-ttu-id="76b19-1080">Ejecute un examen completo.</span><span class="sxs-lookup"><span data-stu-id="76b19-1080">Run a full scan.</span></span>
</li>
<li><span data-ttu-id="76b19-1081">Reinicie el dispositivo e inténtelo de nuevo.</span><span class="sxs-lookup"><span data-stu-id="76b19-1081">Restart the device and try again.</span></span></li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="76b19-1082">Código de error: 0x80508020</span><span class="sxs-lookup"><span data-stu-id="76b19-1082">Error code: 0x80508020</span></span></th>
</tr><tr><td><span data-ttu-id="76b19-1083">Mensaje</span><span class="sxs-lookup"><span data-stu-id="76b19-1083">Message</span></span></td>
<td><span data-ttu-id="76b19-1084"><b>ERR_MP_BAD_CONFIGURATION </b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-1084"><b>ERR_MP_BAD_CONFIGURATION </b>
</span></span></td></tr><tr><td><span data-ttu-id="76b19-1085">Posible motivo</span><span class="sxs-lookup"><span data-stu-id="76b19-1085">Possible reason</span></span></td>
<td>
<span data-ttu-id="76b19-1086">Este error indica que puede haber un error de configuración del motor; normalmente, esto está relacionado con datos de entrada que no permiten que el motor funcione correctamente.</span><span class="sxs-lookup"><span data-stu-id="76b19-1086">This error indicates that there might be an engine configuration error; commonly, this is related to input data that does not allow the engine to function properly.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="76b19-1087">Código de error: 0x805080211</span><span class="sxs-lookup"><span data-stu-id="76b19-1087">Error code: 0x805080211</span></span>
</th>
</tr><tr><td><span data-ttu-id="76b19-1088">Mensaje</span><span class="sxs-lookup"><span data-stu-id="76b19-1088">Message</span></span></td>
<td><span data-ttu-id="76b19-1089"><b>ERR_MP_QUARANTINE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-1089"><b>ERR_MP_QUARANTINE_FAILED </b>
</span></span></td></tr><tr><td><span data-ttu-id="76b19-1090">Posible motivo</span><span class="sxs-lookup"><span data-stu-id="76b19-1090">Possible reason</span></span></td>
<td>
<span data-ttu-id="76b19-1091">Este error indica que Antivirus de Microsoft Defender no pudo poner en cuarentena una amenaza.</span><span class="sxs-lookup"><span data-stu-id="76b19-1091">This error indicates that Microsoft Defender Antivirus failed to quarantine a threat.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="76b19-1092">Código de error: 0x80508022</span><span class="sxs-lookup"><span data-stu-id="76b19-1092">Error code: 0x80508022</span></span>
</th>
</tr><tr><td><span data-ttu-id="76b19-1093">Mensaje</span><span class="sxs-lookup"><span data-stu-id="76b19-1093">Message</span></span></td>
<td><span data-ttu-id="76b19-1094"><b>ERR_MP_REBOOT_REQUIRED </b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-1094"><b>ERR_MP_REBOOT_REQUIRED </b>
</span></span></td></tr><tr><td><span data-ttu-id="76b19-1095">Posible motivo</span><span class="sxs-lookup"><span data-stu-id="76b19-1095">Possible reason</span></span></td>
<td>
<span data-ttu-id="76b19-1096">Este error indica que se requiere un reinicio para completar la eliminación de amenazas.</span><span class="sxs-lookup"><span data-stu-id="76b19-1096">This error indicates that a reboot is required to complete threat removal.</span></span> 
</td>
</tr>
<tr>
<th colspan="2">
<span data-ttu-id="76b19-1097">0x80508023</span><span class="sxs-lookup"><span data-stu-id="76b19-1097">0x80508023</span></span>
</th>
</tr><tr><td><span data-ttu-id="76b19-1098">Mensaje</span><span class="sxs-lookup"><span data-stu-id="76b19-1098">Message</span></span></td>
<td><span data-ttu-id="76b19-1099"><b>ERR_MP_THREAT_NOT_FOUND </b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-1099"><b>ERR_MP_THREAT_NOT_FOUND </b>
</span></span></td></tr><tr><td><span data-ttu-id="76b19-1100">Posible motivo</span><span class="sxs-lookup"><span data-stu-id="76b19-1100">Possible reason</span></span></td>
<td>
<span data-ttu-id="76b19-1101">Este error indica que es posible que la amenaza ya no esté presente en los medios o que el malware pueda impedir que se pueda examinar el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="76b19-1101">This error indicates that the threat might no longer be present on the media, or malware might be stopping you from scanning your device.</span></span> 
</tr><tr><td><span data-ttu-id="76b19-1102">Solución</span><span class="sxs-lookup"><span data-stu-id="76b19-1102">Resolution</span></span>
</td>
<td>
<span data-ttu-id="76b19-1103">Ejecute el <a href="https://www.microsoft.com/security/scanner/default.aspx">Examen de seguridad de Microsoft,</a> a continuación, actualice el software de seguridad e inténtelo de nuevo.</span><span class="sxs-lookup"><span data-stu-id="76b19-1103">Run the <a href="https://www.microsoft.com/security/scanner/default.aspx">Microsoft Safety Scanner</a> then update your security software and try again.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="76b19-1104">Código de error: 0x80508024</span><span class="sxs-lookup"><span data-stu-id="76b19-1104">Error code: 0x80508024</span></span> </th></tr>
<tr>
<td><span data-ttu-id="76b19-1105">Mensaje</span><span class="sxs-lookup"><span data-stu-id="76b19-1105">Message</span></span></td>
<td><span data-ttu-id="76b19-1106"><b>ERR_MP_FULL_SCAN_REQUIRED </b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-1106"><b>ERR_MP_FULL_SCAN_REQUIRED </b>
</span></span></td></tr><tr><td><span data-ttu-id="76b19-1107">Posible motivo</span><span class="sxs-lookup"><span data-stu-id="76b19-1107">Possible reason</span></span></td>
<td>
<span data-ttu-id="76b19-1108">Este error indica que puede ser necesario realizar un examen completo del sistema.</span><span class="sxs-lookup"><span data-stu-id="76b19-1108">This error indicates that a full system scan might be required.</span></span> 
</td></tr>
<tr>
<td><span data-ttu-id="76b19-1109">Solución</span><span class="sxs-lookup"><span data-stu-id="76b19-1109">Resolution</span></span></td><td>
<span data-ttu-id="76b19-1110">Ejecute un examen completo del sistema.</span><span class="sxs-lookup"><span data-stu-id="76b19-1110">Run a full system scan.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="76b19-1111">Código de error: 0x80508025</span><span class="sxs-lookup"><span data-stu-id="76b19-1111">Error code: 0x80508025</span></span>
</th>
</tr><tr><td><span data-ttu-id="76b19-1112">Mensaje</span><span class="sxs-lookup"><span data-stu-id="76b19-1112">Message</span></span></td>
<td><span data-ttu-id="76b19-1113"><b>ERR_MP_MANUAL_STEPS_REQUIRED </b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-1113"><b>ERR_MP_MANUAL_STEPS_REQUIRED </b>
</span></span></td></tr><tr><td><span data-ttu-id="76b19-1114">Posible motivo</span><span class="sxs-lookup"><span data-stu-id="76b19-1114">Possible reason</span></span></td>
<td>
<span data-ttu-id="76b19-1115">Este error indica que se requieren pasos manuales para completar la eliminación de amenazas.</span><span class="sxs-lookup"><span data-stu-id="76b19-1115">This error indicates that manual steps are required to complete threat removal.</span></span> 
</td></tr><tr><td><span data-ttu-id="76b19-1116">Solución</span><span class="sxs-lookup"><span data-stu-id="76b19-1116">Resolution</span></span></td><td>
<span data-ttu-id="76b19-1117">Siga los pasos de corrección manuales descritos en la Enciclopedia de Protección contra malware <a href="https://www.microsoft.com/security/portal/threat/Threats.aspx">de Microsoft</a>.</span><span class="sxs-lookup"><span data-stu-id="76b19-1117">Follow the manual remediation steps outlined in the <a href="https://www.microsoft.com/security/portal/threat/Threats.aspx">Microsoft Malware Protection Encyclopedia</a>.</span></span> <span data-ttu-id="76b19-1118">Puede encontrar un vínculo específico de la amenaza en el historial de eventos.</span><span class="sxs-lookup"><span data-stu-id="76b19-1118">You can find a threat-specific link in the event history.</span></span><br/></td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="76b19-1119">Código de error: 0x80508026</span><span class="sxs-lookup"><span data-stu-id="76b19-1119">Error code: 0x80508026</span></span>
</th>
</tr><tr><td><span data-ttu-id="76b19-1120">Mensaje</span><span class="sxs-lookup"><span data-stu-id="76b19-1120">Message</span></span></td>
<td><span data-ttu-id="76b19-1121"><b>ERR_MP_REMOVE_NOT_SUPPORTED </b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-1121"><b>ERR_MP_REMOVE_NOT_SUPPORTED </b>
</span></span></td></tr><tr><td><span data-ttu-id="76b19-1122">Posible motivo</span><span class="sxs-lookup"><span data-stu-id="76b19-1122">Possible reason</span></span></td>
<td>
<span data-ttu-id="76b19-1123">Este error indica que es posible que no se pueda quitar dentro del tipo de contenedor.</span><span class="sxs-lookup"><span data-stu-id="76b19-1123">This error indicates that removal inside the container type might not be not supported.</span></span> 
</td></tr><tr><td><span data-ttu-id="76b19-1124">Solución</span><span class="sxs-lookup"><span data-stu-id="76b19-1124">Resolution</span></span></td><td>
<span data-ttu-id="76b19-1125">Antivirus de Microsoft Defender no es capaz de corregir las amenazas detectadas dentro del archivo.</span><span class="sxs-lookup"><span data-stu-id="76b19-1125">Microsoft Defender Antivirus is not able to remediate threats detected inside the archive.</span></span> <span data-ttu-id="76b19-1126">Considere la posibilidad de quitar manualmente los recursos detectados.</span><span class="sxs-lookup"><span data-stu-id="76b19-1126">Consider manually removing the detected resources.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="76b19-1127">Código de error: 0x80508027</span><span class="sxs-lookup"><span data-stu-id="76b19-1127">Error code: 0x80508027</span></span>
</th>
</tr><tr><td><span data-ttu-id="76b19-1128">Mensaje</span><span class="sxs-lookup"><span data-stu-id="76b19-1128">Message</span></span></td>
<td><span data-ttu-id="76b19-1129"><b>ERR_MP_REMOVE_LOW_MEDIUM_DISABLED </b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-1129"><b>ERR_MP_REMOVE_LOW_MEDIUM_DISABLED </b>
</span></span></td></tr><tr><td><span data-ttu-id="76b19-1130">Posible motivo</span><span class="sxs-lookup"><span data-stu-id="76b19-1130">Possible reason</span></span></td>
<td>
<span data-ttu-id="76b19-1131">Este error indica que la eliminación de amenazas medias y bajas podría deshabilitarse.</span><span class="sxs-lookup"><span data-stu-id="76b19-1131">This error indicates that removal of low and medium threats might be disabled.</span></span> 
</td></tr><tr><td><span data-ttu-id="76b19-1132">Solución</span><span class="sxs-lookup"><span data-stu-id="76b19-1132">Resolution</span></span></td><td>
<span data-ttu-id="76b19-1133">Compruebe las amenazas detectadas y resuelvalas según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="76b19-1133">Check the detected threats and resolve them as required.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="76b19-1134">Código de error: 0x80508029</span><span class="sxs-lookup"><span data-stu-id="76b19-1134">Error code: 0x80508029</span></span>
</th>
</tr><tr><td><span data-ttu-id="76b19-1135">Mensaje</span><span class="sxs-lookup"><span data-stu-id="76b19-1135">Message</span></span></td>
<td><span data-ttu-id="76b19-1136"><b>ERROR_MP_RESCAN_REQUIRED </b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-1136"><b>ERROR_MP_RESCAN_REQUIRED </b>
</span></span></td></tr><tr><td><span data-ttu-id="76b19-1137">Posible motivo</span><span class="sxs-lookup"><span data-stu-id="76b19-1137">Possible reason</span></span></td>
<td>
<span data-ttu-id="76b19-1138">Este error indica que es necesario volver a examinar la amenaza.</span><span class="sxs-lookup"><span data-stu-id="76b19-1138">This error indicates a rescan of the threat is required.</span></span> 
</td></tr><tr><td><span data-ttu-id="76b19-1139">Solución</span><span class="sxs-lookup"><span data-stu-id="76b19-1139">Resolution</span></span></td><td>
<span data-ttu-id="76b19-1140">Ejecute un examen completo del sistema.</span><span class="sxs-lookup"><span data-stu-id="76b19-1140">Run a full system scan.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="76b19-1141">Código de error: 0x80508030</span><span class="sxs-lookup"><span data-stu-id="76b19-1141">Error code: 0x80508030</span></span>
</th>
</tr><tr><td><span data-ttu-id="76b19-1142">Mensaje</span><span class="sxs-lookup"><span data-stu-id="76b19-1142">Message</span></span></td>
<td><span data-ttu-id="76b19-1143"><b>ERROR_MP_CALLISTO_REQUIRED </b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-1143"><b>ERROR_MP_CALLISTO_REQUIRED </b>
</span></span></td></tr><tr><td><span data-ttu-id="76b19-1144">Posible motivo</span><span class="sxs-lookup"><span data-stu-id="76b19-1144">Possible reason</span></span></td>
<td>
<span data-ttu-id="76b19-1145">Este error indica que es necesario realizar un examen sin conexión.</span><span class="sxs-lookup"><span data-stu-id="76b19-1145">This error indicates that an offline scan is required.</span></span> 
</td></tr><tr><td><span data-ttu-id="76b19-1146">Solución</span><span class="sxs-lookup"><span data-stu-id="76b19-1146">Resolution</span></span></td><td>
<span data-ttu-id="76b19-1147">Ejecute sin conexión Antivirus de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="76b19-1147">Run offline Microsoft Defender Antivirus.</span></span> <span data-ttu-id="76b19-1148">Puede leer sobre cómo hacerlo en el artículo <a href="https://windows.microsoft.com/windows/what-is-windows-defender-offline">sin conexión Antivirus de Microsoft Defender .</a></span><span class="sxs-lookup"><span data-stu-id="76b19-1148">You can read about how to do this in the <a href="https://windows.microsoft.com/windows/what-is-windows-defender-offline">offline Microsoft Defender Antivirus article</a>.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="76b19-1149">Código de error: 0x80508031</span><span class="sxs-lookup"><span data-stu-id="76b19-1149">Error code: 0x80508031</span></span>
</th>
</tr><tr><td><span data-ttu-id="76b19-1150">Mensaje</span><span class="sxs-lookup"><span data-stu-id="76b19-1150">Message</span></span></td>
<td><span data-ttu-id="76b19-1151"><b>ERROR_MP_PLATFORM_OUTDATED</span><span class="sxs-lookup"><span data-stu-id="76b19-1151"><b>ERROR_MP_PLATFORM_OUTDATED</span></span><br/></b>
</td></tr><tr><td><span data-ttu-id="76b19-1152">Posible motivo</span><span class="sxs-lookup"><span data-stu-id="76b19-1152">Possible reason</span></span></td>
<td>
<span data-ttu-id="76b19-1153">Este error indica que Antivirus de Microsoft Defender no admite la versión actual de la plataforma y requiere una nueva versión de la plataforma.</span><span class="sxs-lookup"><span data-stu-id="76b19-1153">This error indicates that Microsoft Defender Antivirus does not support the current version of the platform and requires a new version of the platform.</span></span> 
</td></tr><tr><td><span data-ttu-id="76b19-1154">Solución</span><span class="sxs-lookup"><span data-stu-id="76b19-1154">Resolution</span></span></td><td>
<span data-ttu-id="76b19-1155">Solo puede usar Antivirus de Microsoft Defender en Windows 10.</span><span class="sxs-lookup"><span data-stu-id="76b19-1155">You can only use Microsoft Defender Antivirus in Windows 10.</span></span> <span data-ttu-id="76b19-1156">Para Windows 8, Windows 7 y Windows Vista, puede usar <a href="https://www.microsoft.com/server-cloud/system-center/endpoint-protection-2012.aspx">System Center Endpoint Protection</a>.</span><span class="sxs-lookup"><span data-stu-id="76b19-1156">For Windows 8, Windows 7 and Windows Vista, you can use <a href="https://www.microsoft.com/server-cloud/system-center/endpoint-protection-2012.aspx">System Center Endpoint Protection</a>.</span></span><br/></td>
</tr>
</table><span data-ttu-id="76b19-1157">

<a id="internal-error-codes"></a>Los siguientes códigos de error se usan durante las pruebas internas de Antivirus de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="76b19-1157">

<a id="internal-error-codes"></a> The following error codes are used during internal testing of Microsoft Defender Antivirus.</span></span>

<span data-ttu-id="76b19-1158">Si ve estos errores, puede [](manage-updates-baselines-microsoft-defender-antivirus.md) intentar actualizar definiciones y forzar un nuevo análisis directamente en el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="76b19-1158">If you see these errors, you can try to [update definitions](manage-updates-baselines-microsoft-defender-antivirus.md) and force a rescan directly on the endpoint.</span></span>


<table> 
<tr>
<th colspan="3"><span data-ttu-id="76b19-1159">Códigos de error internos</span><span class="sxs-lookup"><span data-stu-id="76b19-1159">Internal error codes</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="76b19-1160"><b>Código de error</b></span><span class="sxs-lookup"><span data-stu-id="76b19-1160"><b>Error code</b></span></span></th>
<th><span data-ttu-id="76b19-1161">Mensaje mostrado</span><span class="sxs-lookup"><span data-stu-id="76b19-1161">Message displayed</span></span></th>
<th><span data-ttu-id="76b19-1162">Posible motivo de error y resolución</span><span class="sxs-lookup"><span data-stu-id="76b19-1162">Possible reason for error and resolution</span></span></th>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-1163">0x80501004</span><span class="sxs-lookup"><span data-stu-id="76b19-1163">0x80501004</span></span>
</td>
<td><span data-ttu-id="76b19-1164">
<b>ERROR_MP_NO_INTERNET_CONN </b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-1164">
<b>ERROR_MP_NO_INTERNET_CONN </b>
</span></span></td>
<td>
<span data-ttu-id="76b19-1165">Compruebe la conexión a Internet y vuelva a ejecutar el examen.</span><span class="sxs-lookup"><span data-stu-id="76b19-1165">Check your Internet connection, then run the scan again.</span></span>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-1166">0x80501000</span><span class="sxs-lookup"><span data-stu-id="76b19-1166">0x80501000</span></span>
</td>
<td><span data-ttu-id="76b19-1167">
<b>ERROR_MP_UI_CONSOLIDATION_BAS</b> E</span><span class="sxs-lookup"><span data-stu-id="76b19-1167">
<b>ERROR_MP_UI_CONSOLIDATION_BAS</b>E</span></span>
</td>
<td rowspan="34">
<span data-ttu-id="76b19-1168">Se trata de un error interno.</span><span class="sxs-lookup"><span data-stu-id="76b19-1168">This is an internal error.</span></span> <span data-ttu-id="76b19-1169">La causa no está claramente definida.</span><span class="sxs-lookup"><span data-stu-id="76b19-1169">The cause is not clearly defined.</span></span>
</td>
<td rowspan="36">

</td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-1170">0x80501001</span><span class="sxs-lookup"><span data-stu-id="76b19-1170">0x80501001</span></span>
</td>
<td><span data-ttu-id="76b19-1171">
<b>ERROR_MP_ACTIONS_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-1171">
<b>ERROR_MP_ACTIONS_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-1172">0x80501002</span><span class="sxs-lookup"><span data-stu-id="76b19-1172">0x80501002</span></span>
</td>
<td><span data-ttu-id="76b19-1173">
<b>ERROR_MP_NOENGINE</b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-1173">
<b>ERROR_MP_NOENGINE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-1174">0x80501003</span><span class="sxs-lookup"><span data-stu-id="76b19-1174">0x80501003</span></span>
</td>
<td><span data-ttu-id="76b19-1175">
<b>ERROR_MP_ACTIVE_THREATS</b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-1175">
<b>ERROR_MP_ACTIVE_THREATS</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-1176">0x805011011</span><span class="sxs-lookup"><span data-stu-id="76b19-1176">0x805011011</span></span>
</td>
<td><span data-ttu-id="76b19-1177">
<b>MP_ERROR_CODE_LUA_CANCELLED </b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-1177">
<b>MP_ERROR_CODE_LUA_CANCELLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-1178">0x80501101</span><span class="sxs-lookup"><span data-stu-id="76b19-1178">0x80501101</span></span>
</td>
<td><span data-ttu-id="76b19-1179">
<b>ERROR_LUA_CANCELLATION </b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-1179">
<b>ERROR_LUA_CANCELLATION </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-1180">0x80501102</span><span class="sxs-lookup"><span data-stu-id="76b19-1180">0x80501102</span></span>
</td>
<td><span data-ttu-id="76b19-1181">
<b>MP_ERROR_CODE_ALREADY_SHUTDOWN</b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-1181">
<b>MP_ERROR_CODE_ALREADY_SHUTDOWN</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-1182">0x80501103</span><span class="sxs-lookup"><span data-stu-id="76b19-1182">0x80501103</span></span>
</td>
<td><span data-ttu-id="76b19-1183">
<b>MP_ERROR_CODE_RDEVICE_S_ASYNC_CALL_PENDING </b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-1183">
<b>MP_ERROR_CODE_RDEVICE_S_ASYNC_CALL_PENDING </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-1184">0x80501104</span><span class="sxs-lookup"><span data-stu-id="76b19-1184">0x80501104</span></span>
</td>
<td><span data-ttu-id="76b19-1185">
<b>MP_ERROR_CODE_CANCELLED</b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-1185">
<b>MP_ERROR_CODE_CANCELLED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-1186">0x80501105</span><span class="sxs-lookup"><span data-stu-id="76b19-1186">0x80501105</span></span>
</td>
<td><span data-ttu-id="76b19-1187">
<b>MP_ERROR_CODE_NO_TARGETOS</b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-1187">
<b>MP_ERROR_CODE_NO_TARGETOS</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-1188">0x80501106</span><span class="sxs-lookup"><span data-stu-id="76b19-1188">0x80501106</span></span>
</td>
<td><span data-ttu-id="76b19-1189">
<b>MP_ERROR_CODE_BAD_REGEXP</b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-1189">
<b>MP_ERROR_CODE_BAD_REGEXP</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-1190">0x80501107</span><span class="sxs-lookup"><span data-stu-id="76b19-1190">0x80501107</span></span>
</td>
<td><span data-ttu-id="76b19-1191">
<b>MP_ERROR_TEST_INDUCED_ERROR</b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-1191">
<b>MP_ERROR_TEST_INDUCED_ERROR</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-1192">0x80501108</span><span class="sxs-lookup"><span data-stu-id="76b19-1192">0x80501108</span></span>
</td>
<td><span data-ttu-id="76b19-1193">
<b>MP_ERROR_SIG_BACKUP_DISABLED</b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-1193">
<b>MP_ERROR_SIG_BACKUP_DISABLED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-1194">0x80508001</span><span class="sxs-lookup"><span data-stu-id="76b19-1194">0x80508001</span></span>
</td>
<td><span data-ttu-id="76b19-1195">
<b>ERR_MP_BAD_INIT_MODULES</b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-1195">
<b>ERR_MP_BAD_INIT_MODULES</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-1196">0x80508002</span><span class="sxs-lookup"><span data-stu-id="76b19-1196">0x80508002</span></span>
</td>
<td><span data-ttu-id="76b19-1197">
<b>ERR_MP_BAD_DATABASE</b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-1197">
<b>ERR_MP_BAD_DATABASE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-1198">0x80508004</span><span class="sxs-lookup"><span data-stu-id="76b19-1198">0x80508004</span></span>
</td>
<td><span data-ttu-id="76b19-1199">
<b>ERR_MP_BAD_UFS </b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-1199">
<b>ERR_MP_BAD_UFS </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-1200">0x8050800C</span><span class="sxs-lookup"><span data-stu-id="76b19-1200">0x8050800C</span></span>
</td>
<td><span data-ttu-id="76b19-1201">
<b>ERR_MP_BAD_INPUT_DATA</b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-1201">
<b>ERR_MP_BAD_INPUT_DATA</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-1202">0x8050800D</span><span class="sxs-lookup"><span data-stu-id="76b19-1202">0x8050800D</span></span>
</td>
<td><span data-ttu-id="76b19-1203">
<b>ERR_MP_BAD_GLOBAL_STORAGE</b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-1203">
<b>ERR_MP_BAD_GLOBAL_STORAGE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-1204">0x8050800E</span><span class="sxs-lookup"><span data-stu-id="76b19-1204">0x8050800E</span></span>
</td>
<td><span data-ttu-id="76b19-1205">
<b>ERR_MP_OBSOLETE</b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-1205">
<b>ERR_MP_OBSOLETE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-1206">0x8050800F</span><span class="sxs-lookup"><span data-stu-id="76b19-1206">0x8050800F</span></span>
</td>
<td><span data-ttu-id="76b19-1207">
<b>ERR_MP_NOT_SUPPORTED</b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-1207">
<b>ERR_MP_NOT_SUPPORTED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-1208">0x8050800F 0x80508010</span><span class="sxs-lookup"><span data-stu-id="76b19-1208">0x8050800F 0x80508010</span></span>
</td>
<td><span data-ttu-id="76b19-1209">
<b>ERR_MP_NO_MORE_ITEMS </b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-1209">
<b>ERR_MP_NO_MORE_ITEMS </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-1210">0x80508011</span><span class="sxs-lookup"><span data-stu-id="76b19-1210">0x80508011</span></span>
</td>
<td><span data-ttu-id="76b19-1211">
<b>ERR_MP_DUPLICATE_SCANID</b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-1211">
<b>ERR_MP_DUPLICATE_SCANID</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-1212">0x80508012</span><span class="sxs-lookup"><span data-stu-id="76b19-1212">0x80508012</span></span>
</td>
<td><span data-ttu-id="76b19-1213">
<b>ERR_MP_BAD_SCANID</b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-1213">
<b>ERR_MP_BAD_SCANID</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-1214">0x80508013</span><span class="sxs-lookup"><span data-stu-id="76b19-1214">0x80508013</span></span>
</td>
<td><span data-ttu-id="76b19-1215">
<b>ERR_MP_BAD_USERDB_VERSION</b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-1215">
<b>ERR_MP_BAD_USERDB_VERSION</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-1216">0x80508014</span><span class="sxs-lookup"><span data-stu-id="76b19-1216">0x80508014</span></span>
</td>
<td><span data-ttu-id="76b19-1217">
<b>ERR_MP_RESTORE_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-1217">
<b>ERR_MP_RESTORE_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-1218">0x80508016</span><span class="sxs-lookup"><span data-stu-id="76b19-1218">0x80508016</span></span>
</td>
<td><span data-ttu-id="76b19-1219">
<b>ERR_MP_BAD_ACTION</b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-1219">
<b>ERR_MP_BAD_ACTION</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-1220">0x80508019</span><span class="sxs-lookup"><span data-stu-id="76b19-1220">0x80508019</span></span>
</td>
<td><span data-ttu-id="76b19-1221">
<b>ERR_MP_NOT_FOUND</b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-1221">
<b>ERR_MP_NOT_FOUND</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-1222">0x80509001</span><span class="sxs-lookup"><span data-stu-id="76b19-1222">0x80509001</span></span>
</td>
<td><span data-ttu-id="76b19-1223">
<b>ERR_RELO_BAD_EHANDLE</b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-1223">
<b>ERR_RELO_BAD_EHANDLE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-1224">0x80509003</span><span class="sxs-lookup"><span data-stu-id="76b19-1224">0x80509003</span></span>
</td>
<td><span data-ttu-id="76b19-1225">
<b>ERR_RELO_KERNEL_NOT_LOADED</b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-1225">
<b>ERR_RELO_KERNEL_NOT_LOADED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-1226">0x8050A001</span><span class="sxs-lookup"><span data-stu-id="76b19-1226">0x8050A001</span></span>
</td>
<td><span data-ttu-id="76b19-1227">
<b>ERR_MP_BADDB_OPEN</b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-1227">
<b>ERR_MP_BADDB_OPEN</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-1228">0x8050A002</span><span class="sxs-lookup"><span data-stu-id="76b19-1228">0x8050A002</span></span>
</td>
<td><span data-ttu-id="76b19-1229">
<b>ERR_MP_BADDB_HEADER</b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-1229">
<b>ERR_MP_BADDB_HEADER</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-1230">0x8050A003</span><span class="sxs-lookup"><span data-stu-id="76b19-1230">0x8050A003</span></span>
</td>
<td><span data-ttu-id="76b19-1231">
<b>ERR_MP_BADDB_OLDENGINE</b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-1231">
<b>ERR_MP_BADDB_OLDENGINE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-1232">0x8050A004</span><span class="sxs-lookup"><span data-stu-id="76b19-1232">0x8050A004</span></span>
</td>
<td><span data-ttu-id="76b19-1233">
<b>ERR_MP_BADDB_CONTENT </b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-1233">
<b>ERR_MP_BADDB_CONTENT </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-1234">0x8050A005</span><span class="sxs-lookup"><span data-stu-id="76b19-1234">0x8050A005</span></span>
</td>
<td><span data-ttu-id="76b19-1235">
<b>ERR_MP_BADDB_NOTSIGNED</b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-1235">
<b>ERR_MP_BADDB_NOTSIGNED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-1236">0x8050801</span><span class="sxs-lookup"><span data-stu-id="76b19-1236">0x8050801</span></span>
</td>
<td><span data-ttu-id="76b19-1237">
<b>ERR_MP_REMOVE_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-1237">
<b>ERR_MP_REMOVE_FAILED</b>
</span></span></td>
<td>
<span data-ttu-id="76b19-1238">Se trata de un error interno.</span><span class="sxs-lookup"><span data-stu-id="76b19-1238">This is an internal error.</span></span> <span data-ttu-id="76b19-1239">Puede desencadenarse cuando la eliminación de malware no se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="76b19-1239">It might be triggered when malware removal is not successful.</span></span> 
</td>
</tr>
<tr>
<td>
<span data-ttu-id="76b19-1240">0x80508018</span><span class="sxs-lookup"><span data-stu-id="76b19-1240">0x80508018</span></span>
</td>
<td><span data-ttu-id="76b19-1241">
<b>ERR_MP_SCAN_ABORTED </b>
</span><span class="sxs-lookup"><span data-stu-id="76b19-1241">
<b>ERR_MP_SCAN_ABORTED </b>
</span></span></td>
<td>
<span data-ttu-id="76b19-1242">Se trata de un error interno.</span><span class="sxs-lookup"><span data-stu-id="76b19-1242">This is an internal error.</span></span> <span data-ttu-id="76b19-1243">Puede que se haya desencadenado cuando un examen no se completa.</span><span class="sxs-lookup"><span data-stu-id="76b19-1243">It might have triggered when a scan fails to complete.</span></span> 
</td>
</tr>
</table>

## <a name="related-topics"></a><span data-ttu-id="76b19-1244">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="76b19-1244">Related topics</span></span>

- [<span data-ttu-id="76b19-1245">Informe sobre la Antivirus de Microsoft Defender protección</span><span class="sxs-lookup"><span data-stu-id="76b19-1245">Report on Microsoft Defender Antivirus protection</span></span>](report-monitor-microsoft-defender-antivirus.md)
- [<span data-ttu-id="76b19-1246">Antivirus de Microsoft Defender en Windows 10</span><span class="sxs-lookup"><span data-stu-id="76b19-1246">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)