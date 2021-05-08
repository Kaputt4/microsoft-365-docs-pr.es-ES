---
title: Códigos de error e IDs de eventos antivirus de Microsoft Defender
description: Buscar las causas y soluciones de los Antivirus de Microsoft Defender de eventos y errores
keywords: event, error code, siem, logging, troubleshooting, wef, windows event forwarding
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/11/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: cd222760f3a5cc005c679bf28365237cc70e8950
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275353"
---
# <a name="review-event-logs-and-error-codes-to-troubleshoot-issues-with-microsoft-defender-antivirus"></a><span data-ttu-id="bbca0-104">Revisar registros de sucesos y códigos de error para solucionar problemas del Antivirus de Windows Defender</span><span class="sxs-lookup"><span data-stu-id="bbca0-104">Review event logs and error codes to troubleshoot issues with Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="bbca0-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="bbca0-105">**Applies to:**</span></span>

- [<span data-ttu-id="bbca0-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="bbca0-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="bbca0-107">Si encuentra un problema con Antivirus de Microsoft Defender, puede buscar en las tablas de este tema un problema de coincidencia y una posible solución.</span><span class="sxs-lookup"><span data-stu-id="bbca0-107">If you encounter a problem with Microsoft Defender Antivirus, you can search the tables in this topic to find a matching issue and potential solution.</span></span>

<span data-ttu-id="bbca0-108">La lista de tablas:</span><span class="sxs-lookup"><span data-stu-id="bbca0-108">The tables list:</span></span>

- <span data-ttu-id="bbca0-109">[Antivirus de Microsoft Defender de eventos](#windows-defender-av-ids) (estos se aplican a Windows 10 y Windows Server 2016)</span><span class="sxs-lookup"><span data-stu-id="bbca0-109">[Microsoft Defender Antivirus event IDs](#windows-defender-av-ids) (these apply to both Windows 10 and Windows Server 2016)</span></span>
- [<span data-ttu-id="bbca0-110">Antivirus de Microsoft Defender de error de cliente</span><span class="sxs-lookup"><span data-stu-id="bbca0-110">Microsoft Defender Antivirus client error codes</span></span>](#error-codes)
- [<span data-ttu-id="bbca0-111">Códigos Antivirus de Microsoft Defender de error de cliente internos (usados por Microsoft durante el desarrollo y las pruebas)</span><span class="sxs-lookup"><span data-stu-id="bbca0-111">Internal Microsoft Defender Antivirus client error codes (used by Microsoft during development and testing)</span></span>](#internal-error-codes)

> [!TIP]
> <span data-ttu-id="bbca0-112">También puede visitar el sitio web de demostración de Microsoft Defender para endpoint [en demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) para confirmar que funcionan las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="bbca0-112">You can also visit the Microsoft Defender for Endpoint demo website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the following features are working:</span></span>
> 
> - <span data-ttu-id="bbca0-113">Protección entregada en la nube</span><span class="sxs-lookup"><span data-stu-id="bbca0-113">Cloud-delivered protection</span></span>
> - <span data-ttu-id="bbca0-114">Aprendizaje rápido (incluido Bloquear a primera vista)</span><span class="sxs-lookup"><span data-stu-id="bbca0-114">Fast learning (including Block at first sight)</span></span>
> - <span data-ttu-id="bbca0-115">Bloqueo de aplicaciones potencialmente no deseado</span><span class="sxs-lookup"><span data-stu-id="bbca0-115">Potentially unwanted application blocking</span></span>

<a id="windows-defender-av-ids"></a>
## <a name="microsoft-defender-antivirus-event-ids"></a><span data-ttu-id="bbca0-116">Antivirus de Microsoft Defender de eventos</span><span class="sxs-lookup"><span data-stu-id="bbca0-116">Microsoft Defender Antivirus event IDs</span></span>

<span data-ttu-id="bbca0-117">Antivirus de Microsoft Defender registra los IDs de eventos en el Windows de eventos.</span><span class="sxs-lookup"><span data-stu-id="bbca0-117">Microsoft Defender Antivirus records event IDs in the Windows event log.</span></span>

<span data-ttu-id="bbca0-118">Puede ver directamente el registro de eventos, o si tiene una herramienta de administración de eventos y información de seguridad (SIEM) de terceros, también puede usar los [IDs](troubleshoot-microsoft-defender-antivirus.md#windows-defender-av-ids) de eventos de cliente de Antivirus de Microsoft Defender para revisar eventos y errores específicos de los puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="bbca0-118">You can directly view the event log, or if you have a third-party security information and event management (SIEM) tool, you can also consume [Microsoft Defender Antivirus client event IDs](troubleshoot-microsoft-defender-antivirus.md#windows-defender-av-ids) to review specific events and errors from your endpoints.</span></span>

<span data-ttu-id="bbca0-119">En la tabla de esta sección se enumeran los principales Antivirus de Microsoft Defender de eventos y, siempre que sea posible, proporciona soluciones sugeridas para corregir o resolver el error.</span><span class="sxs-lookup"><span data-stu-id="bbca0-119">The table in this section lists the main Microsoft Defender Antivirus event IDs and, where possible, provides suggested solutions to fix or resolve the error.</span></span> 

## <a name="to-view-a-microsoft-defender-antivirus-event"></a><span data-ttu-id="bbca0-120">Para ver un evento Antivirus de Microsoft Defender evento</span><span class="sxs-lookup"><span data-stu-id="bbca0-120">To view a Microsoft Defender Antivirus event</span></span>

1.  <span data-ttu-id="bbca0-121">Abra **el Visor de eventos**.</span><span class="sxs-lookup"><span data-stu-id="bbca0-121">Open **Event Viewer**.</span></span>
2.  <span data-ttu-id="bbca0-122">En el árbol de consola, expanda **Registros de** aplicaciones y servicios , a continuación, **Microsoft**, a continuación, **Windows**, a continuación, **Windows Defender**.</span><span class="sxs-lookup"><span data-stu-id="bbca0-122">In the console tree, expand **Applications and Services Logs**, then **Microsoft**, then **Windows**, then **Windows Defender**.</span></span>
3.  <span data-ttu-id="bbca0-123">Haga doble clic en **Operativo**.</span><span class="sxs-lookup"><span data-stu-id="bbca0-123">Double-click on **Operational**.</span></span>
4.  <span data-ttu-id="bbca0-124">En el panel de detalles, vea la lista de eventos individuales para buscar el evento.</span><span class="sxs-lookup"><span data-stu-id="bbca0-124">In the details pane, view the list of individual events to find your event.</span></span>
5.  <span data-ttu-id="bbca0-125">Haga clic en el evento para ver detalles específicos sobre un evento en el panel inferior, en las **pestañas General** **y** Detalles.</span><span class="sxs-lookup"><span data-stu-id="bbca0-125">Click the event to see specific details about an event in the lower pane, under the **General** and **Details** tabs.</span></span>

<table> 
<tr>
<th colspan="2" ><span data-ttu-id="bbca0-126">Identificador de evento: 1000</span><span class="sxs-lookup"><span data-stu-id="bbca0-126">Event ID: 1000</span></span></th>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-127">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="bbca0-127">Symbolic name:</span></span>
</td>
<td><span data-ttu-id="bbca0-128">
<b>MALWAREPROTECTION_SCAN_STARTED</b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-128">
<b>MALWAREPROTECTION_SCAN_STARTED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-129">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="bbca0-129">Message:</span></span>
</td>
<td ><span data-ttu-id="bbca0-130">
<b>Se inició un examen de antimalware. </b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-130">
<b>An antimalware scan started. </b>
</span></span></td>
</tr>
<tr>
<td >
<span data-ttu-id="bbca0-131">Descripción:</span><span class="sxs-lookup"><span data-stu-id="bbca0-131">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="bbca0-132">
<dt>Id. de examen: &lt; Número de identificador del &gt; examen correspondiente.</dt> 
<dt> Tipo de examen: &lt; Tipo de examen , por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bbca0-132">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="bbca0-133">Antivirus</span><span class="sxs-lookup"><span data-stu-id="bbca0-133">Antivirus</span></span></li>
<li><span data-ttu-id="bbca0-134">Antispyware</span><span class="sxs-lookup"><span data-stu-id="bbca0-134">Antispyware</span></span></li>
<li><span data-ttu-id="bbca0-135">Antimalware</span><span class="sxs-lookup"><span data-stu-id="bbca0-135">Antimalware</span></span></li>
</ul><span data-ttu-id="bbca0-136">
</dt>
<dt>Parámetros de examen: &lt; parámetros de examen , por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bbca0-136">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="bbca0-137">Examen completo</span><span class="sxs-lookup"><span data-stu-id="bbca0-137">Full scan</span></span></li>
<li><span data-ttu-id="bbca0-138">Examen rápido</span><span class="sxs-lookup"><span data-stu-id="bbca0-138">Quick scan</span></span></li>
<li><span data-ttu-id="bbca0-139">Examen del cliente</span><span class="sxs-lookup"><span data-stu-id="bbca0-139">Customer scan</span></span></li>
</ul><span data-ttu-id="bbca0-140">
</dt>
<dt>Recursos de examen: &lt; Recursos (como archivos/directorios/BHO) que se &gt; examinaron.</dt> 
<dt>Usuario: &lt; Dominio &gt; \& lt; Usuario &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-140">
</dt>
<dt>Scan Resources: &lt;Resources (such as files/directories/BHO) that were scanned.&gt;</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="bbca0-141">Identificador de evento: 1001</span><span class="sxs-lookup"><span data-stu-id="bbca0-141">Event ID: 1001</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="bbca0-142">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="bbca0-142">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="bbca0-143">
<b>MALWAREPROTECTION_SCAN_COMPLETED</b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-143">
<b>MALWAREPROTECTION_SCAN_COMPLETED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-144">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="bbca0-144">Message:</span></span>
</td>
<td ><span data-ttu-id="bbca0-145">
<b>Se ha finalizado un examen de antimalware.</b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-145">
<b>An antimalware scan finished.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-146">Descripción:</span><span class="sxs-lookup"><span data-stu-id="bbca0-146">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="bbca0-147">
<dt>Id. de examen: &lt; Número de identificador del &gt; examen correspondiente.</dt> 
<dt> Tipo de examen: &lt; Tipo de examen , por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bbca0-147">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="bbca0-148">Antivirus</span><span class="sxs-lookup"><span data-stu-id="bbca0-148">Antivirus</span></span></li>
<li><span data-ttu-id="bbca0-149">Antispyware</span><span class="sxs-lookup"><span data-stu-id="bbca0-149">Antispyware</span></span></li>
<li><span data-ttu-id="bbca0-150">Antimalware</span><span class="sxs-lookup"><span data-stu-id="bbca0-150">Antimalware</span></span></li>
</ul><span data-ttu-id="bbca0-151">
</dt>
<dt>Parámetros de examen: &lt; parámetros de examen , por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bbca0-151">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="bbca0-152">Examen completo</span><span class="sxs-lookup"><span data-stu-id="bbca0-152">Full scan</span></span></li>
<li><span data-ttu-id="bbca0-153">Examen rápido</span><span class="sxs-lookup"><span data-stu-id="bbca0-153">Quick scan</span></span></li>
<li><span data-ttu-id="bbca0-154">Examen del cliente</span><span class="sxs-lookup"><span data-stu-id="bbca0-154">Customer scan</span></span></li>
</ul><span data-ttu-id="bbca0-155">
</dt>
<dt>Usuario: &lt; Dominio &gt; \& lt; Tiempo &gt; </dt>
<dt>de examen del usuario: la &lt; duración de un examen. &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-155">
</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Scan Time: &lt;The duration of a scan.&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="bbca0-156">Identificador de evento: 1002</span><span class="sxs-lookup"><span data-stu-id="bbca0-156">Event ID: 1002</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="bbca0-157">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="bbca0-157">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="bbca0-158">
<b>MALWAREPROTECTION_SCAN_CANCELLED </b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-158">
<b>MALWAREPROTECTION_SCAN_CANCELLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-159">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="bbca0-159">Message:</span></span>
</td>
<td ><span data-ttu-id="bbca0-160">
<b>Antes de finalizar, se detuvo un examen antimalware. </b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-160">
<b>An antimalware scan was stopped before it finished. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-161">Descripción:</span><span class="sxs-lookup"><span data-stu-id="bbca0-161">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="bbca0-162">
<dt>Id. de examen: &lt; Número de identificador del &gt; examen correspondiente.</dt> 
<dt> Tipo de examen: &lt; Tipo de examen , por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bbca0-162">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="bbca0-163">Antivirus</span><span class="sxs-lookup"><span data-stu-id="bbca0-163">Antivirus</span></span></li>
<li><span data-ttu-id="bbca0-164">Antispyware</span><span class="sxs-lookup"><span data-stu-id="bbca0-164">Antispyware</span></span></li>
<li><span data-ttu-id="bbca0-165">Antimalware</span><span class="sxs-lookup"><span data-stu-id="bbca0-165">Antimalware</span></span></li>
</ul><span data-ttu-id="bbca0-166">
</dt>
<dt>Parámetros de examen: &lt; parámetros de examen , por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bbca0-166">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="bbca0-167">Examen completo</span><span class="sxs-lookup"><span data-stu-id="bbca0-167">Full scan</span></span></li>
<li><span data-ttu-id="bbca0-168">Examen rápido</span><span class="sxs-lookup"><span data-stu-id="bbca0-168">Quick scan</span></span></li>
<li><span data-ttu-id="bbca0-169">Examen del cliente</span><span class="sxs-lookup"><span data-stu-id="bbca0-169">Customer scan</span></span></li>
</ul><span data-ttu-id="bbca0-170">
</dt>
<dt>Usuario: &lt; Dominio &gt; &amp; lt; Tiempo &gt; </dt>
<dt>de examen del usuario: la &lt; duración de un examen. &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-170">
</dt>
<dt>User: &lt;Domain&gt;&amp;lt;User&gt;</dt>
<dt>Scan Time: &lt;The duration of a scan.&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="bbca0-171">Identificador de evento: 1003</span><span class="sxs-lookup"><span data-stu-id="bbca0-171">Event ID: 1003</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="bbca0-172">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="bbca0-172">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="bbca0-173">
<b>MALWAREPROTECTION_SCAN_PAUSED </b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-173">
<b>MALWAREPROTECTION_SCAN_PAUSED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-174">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="bbca0-174">Message:</span></span>
</td>
<td ><span data-ttu-id="bbca0-175">
<b>Se ha pausado un examen antimalware. </b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-175">
<b>An antimalware scan was paused. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-176">Descripción:</span><span class="sxs-lookup"><span data-stu-id="bbca0-176">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="bbca0-177">
<dt>Id. de examen: &lt; Número de identificador del &gt; examen correspondiente.</dt> 
<dt> Tipo de examen: &lt; Tipo de examen , por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bbca0-177">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="bbca0-178">Antivirus</span><span class="sxs-lookup"><span data-stu-id="bbca0-178">Antivirus</span></span></li>
<li><span data-ttu-id="bbca0-179">Antispyware</span><span class="sxs-lookup"><span data-stu-id="bbca0-179">Antispyware</span></span></li>
<li><span data-ttu-id="bbca0-180">Antimalware</span><span class="sxs-lookup"><span data-stu-id="bbca0-180">Antimalware</span></span></li>
</ul><span data-ttu-id="bbca0-181">
</dt>
<dt>Parámetros de examen: &lt; parámetros de examen , por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bbca0-181">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="bbca0-182">Examen completo</span><span class="sxs-lookup"><span data-stu-id="bbca0-182">Full scan</span></span></li>
<li><span data-ttu-id="bbca0-183">Examen rápido</span><span class="sxs-lookup"><span data-stu-id="bbca0-183">Quick scan</span></span></li>
<li><span data-ttu-id="bbca0-184">Examen del cliente</span><span class="sxs-lookup"><span data-stu-id="bbca0-184">Customer scan</span></span></li>
</ul><span data-ttu-id="bbca0-185">
</dt>
<dt>Usuario: &lt; Dominio &gt; \& lt; Usuario&gt;</dt>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-185">
</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="bbca0-186">Identificador de evento: 1004</span><span class="sxs-lookup"><span data-stu-id="bbca0-186">Event ID: 1004</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="bbca0-187">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="bbca0-187">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="bbca0-188">
<b>MALWAREPROTECTION_SCAN_RESUMED </b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-188">
<b>MALWAREPROTECTION_SCAN_RESUMED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-189">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="bbca0-189">Message:</span></span>
</td>
<td ><span data-ttu-id="bbca0-190">
<b>Se reanudó un examen antimalware. </b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-190">
<b>An antimalware scan was resumed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-191">Descripción:</span><span class="sxs-lookup"><span data-stu-id="bbca0-191">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="bbca0-192">
<dt>Id. de examen: &lt; Número de identificador del &gt; examen correspondiente.</dt> 
<dt> Tipo de examen: &lt; Tipo de examen , por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bbca0-192">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="bbca0-193">Antivirus</span><span class="sxs-lookup"><span data-stu-id="bbca0-193">Antivirus</span></span></li>
<li><span data-ttu-id="bbca0-194">Antispyware</span><span class="sxs-lookup"><span data-stu-id="bbca0-194">Antispyware</span></span></li>
<li><span data-ttu-id="bbca0-195">Antimalware</span><span class="sxs-lookup"><span data-stu-id="bbca0-195">Antimalware</span></span></li>
</ul><span data-ttu-id="bbca0-196">
</dt>
<dt>Parámetros de examen: &lt; parámetros de examen , por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bbca0-196">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="bbca0-197">Examen completo</span><span class="sxs-lookup"><span data-stu-id="bbca0-197">Full scan</span></span></li>
<li><span data-ttu-id="bbca0-198">Examen rápido</span><span class="sxs-lookup"><span data-stu-id="bbca0-198">Quick scan</span></span></li>
<li><span data-ttu-id="bbca0-199">Examen del cliente</span><span class="sxs-lookup"><span data-stu-id="bbca0-199">Customer scan</span></span></li>
</ul><span data-ttu-id="bbca0-200">
</dt>
<dt>Usuario: &lt; Dominio &gt; \& lt; Usuario&gt;</dt>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-200">
</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="bbca0-201">Identificador de evento: 1005</span><span class="sxs-lookup"><span data-stu-id="bbca0-201">Event ID: 1005</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="bbca0-202">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="bbca0-202">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="bbca0-203">
<b>MALWAREPROTECTION_SCAN_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-203">
<b>MALWAREPROTECTION_SCAN_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-204">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="bbca0-204">Message:</span></span>
</td>
<td ><span data-ttu-id="bbca0-205">
<b>Error en un examen antimalware. </b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-205">
<b>An antimalware scan failed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-206">Descripción:</span><span class="sxs-lookup"><span data-stu-id="bbca0-206">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="bbca0-207">
<dt>Id. de examen: &lt; Número de identificador del &gt; examen correspondiente.</dt> 
<dt> Tipo de examen: &lt; Tipo de examen , por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bbca0-207">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="bbca0-208">Antivirus</span><span class="sxs-lookup"><span data-stu-id="bbca0-208">Antivirus</span></span></li>
<li><span data-ttu-id="bbca0-209">Antispyware</span><span class="sxs-lookup"><span data-stu-id="bbca0-209">Antispyware</span></span></li>
<li><span data-ttu-id="bbca0-210">Antimalware</span><span class="sxs-lookup"><span data-stu-id="bbca0-210">Antimalware</span></span></li>
</ul><span data-ttu-id="bbca0-211">
</dt>
<dt>Parámetros de examen: &lt; parámetros de examen , por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bbca0-211">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="bbca0-212">Examen completo</span><span class="sxs-lookup"><span data-stu-id="bbca0-212">Full scan</span></span></li>
<li><span data-ttu-id="bbca0-213">Examen rápido</span><span class="sxs-lookup"><span data-stu-id="bbca0-213">Quick scan</span></span></li>
<li><span data-ttu-id="bbca0-214">Examen del cliente</span><span class="sxs-lookup"><span data-stu-id="bbca0-214">Customer scan</span></span></li>
</ul><span data-ttu-id="bbca0-215">
</dt>
<dt>Usuario: &lt; Dominio &gt; \& lt; Código &gt; </dt>
<dt>de error del usuario: Código de error &lt; Código de resultado asociado con el estado de &gt; amenaza. Valores HRESULT estándar.</dt> 
<dt>Descripción del error: &lt; Descripción del error &gt; Descripción del error.</dt>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-215">
</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-216">Acción del usuario:</span><span class="sxs-lookup"><span data-stu-id="bbca0-216">User action:</span></span>
</td>
<td >
<span data-ttu-id="bbca0-217">El cliente antivirus encontró un error y se detuvo el examen actual.</span><span class="sxs-lookup"><span data-stu-id="bbca0-217">The antivirus client encountered an error, and the current scan has stopped.</span></span> <span data-ttu-id="bbca0-218">El examen puede producir un error debido a un problema del lado cliente.</span><span class="sxs-lookup"><span data-stu-id="bbca0-218">The scan might fail due to a client-side issue.</span></span> <span data-ttu-id="bbca0-219">Este registro de evento incluye el identificador de examen, el tipo de examen (Antivirus de Microsoft Defender, antispyware, antimalware), los parámetros de examen, el usuario que inició el examen, el código de error y una descripción del error.</span><span class="sxs-lookup"><span data-stu-id="bbca0-219">This event record includes the scan ID, type of scan (Microsoft Defender Antivirus, antispyware, antimalware), scan parameters, the user that started the scan, the error code, and a description of the error.</span></span>
<span data-ttu-id="bbca0-220">Para solucionar este evento:</span><span class="sxs-lookup"><span data-stu-id="bbca0-220">To troubleshoot this event:</span></span>
<ol>
<li><span data-ttu-id="bbca0-221">Vuelva a ejecutar el examen.</span><span class="sxs-lookup"><span data-stu-id="bbca0-221">Run the scan again.</span></span></li>
<li><span data-ttu-id="bbca0-222">Si se produce un error de la misma manera, vaya <b></b> al sitio de soporte técnico de <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft</a>, escriba el número de error en el cuadro Buscar para buscar el código de error.</span><span class="sxs-lookup"><span data-stu-id="bbca0-222">If it fails in the same way, go to the <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft Support site</a>, enter the error number in the <b>Search</b> box to look for the error code.</span></span></li>
<li><span data-ttu-id="bbca0-223">Contactar al <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Soporte técnico de Microsoft</a>.</span><span class="sxs-lookup"><span data-stu-id="bbca0-223">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="bbca0-224">Identificador de evento: 1006</span><span class="sxs-lookup"><span data-stu-id="bbca0-224">Event ID: 1006</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="bbca0-225">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="bbca0-225">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="bbca0-226">
<b>MALWAREPROTECTION_MALWARE_DETECTED </b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-226">
<b>MALWAREPROTECTION_MALWARE_DETECTED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-227">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="bbca0-227">Message:</span></span>
</td>
<td ><span data-ttu-id="bbca0-228">
<b>El motor de antimalware encontró malware u otro software potencialmente no deseado. </b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-228">
<b>The antimalware engine found malware or other potentially unwanted software. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-229">Descripción:</span><span class="sxs-lookup"><span data-stu-id="bbca0-229">Description:</span></span>
</td>
<td >
<span data-ttu-id="bbca0-230">Para obtener más información, vea los artículos siguientes: </span><span class="sxs-lookup"><span data-stu-id="bbca0-230">For more information, see the following:</span></span>
<dl><span data-ttu-id="bbca0-231">
<dt>Nombre: &lt; Id. &gt; de</dt>
<dt>nombre de &lt; amenaza: Gravedad del id. &gt; </dt>de 
<dt> amenaza: gravedad , por &lt; &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bbca0-231">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="bbca0-232">Bajo</span><span class="sxs-lookup"><span data-stu-id="bbca0-232">Low</span></span></li>
<li><span data-ttu-id="bbca0-233">Moderado</span><span class="sxs-lookup"><span data-stu-id="bbca0-233">Moderate</span></span></li>
<li><span data-ttu-id="bbca0-234">Alto</span><span class="sxs-lookup"><span data-stu-id="bbca0-234">High</span></span></li>
<li><span data-ttu-id="bbca0-235">Grave</span><span class="sxs-lookup"><span data-stu-id="bbca0-235">Severe</span></span></li>
</ul><span data-ttu-id="bbca0-236">
</dt>
<dt>Categoría: &lt; Descripción de &gt; categoría , por ejemplo, cualquier tipo de amenaza o malware.</dt> 
<dt>Ruta de acceso: &lt; Origen &gt; de detección</dt>de ruta de 
<dt> acceso de &lt; archivo: Origen de &gt; detección, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bbca0-236">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span><ul>
<li><span data-ttu-id="bbca0-237">Desconocido</span><span class="sxs-lookup"><span data-stu-id="bbca0-237">Unknown</span></span></li>
<li><span data-ttu-id="bbca0-238">Equipo local</span><span class="sxs-lookup"><span data-stu-id="bbca0-238">Local computer</span></span></li>
<li><span data-ttu-id="bbca0-239">Recurso compartido de red</span><span class="sxs-lookup"><span data-stu-id="bbca0-239">Network share</span></span></li>
<li><span data-ttu-id="bbca0-240">Internet</span><span class="sxs-lookup"><span data-stu-id="bbca0-240">Internet</span></span></li>
<li><span data-ttu-id="bbca0-241">Tráfico entrante</span><span class="sxs-lookup"><span data-stu-id="bbca0-241">Incoming traffic</span></span></li>
<li><span data-ttu-id="bbca0-242">Tráfico saliente</span><span class="sxs-lookup"><span data-stu-id="bbca0-242">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="bbca0-243">
</dt>
<dt>Tipo de &lt; detección: Tipo de &gt; detección , por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bbca0-243">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="bbca0-244">Heurística</span><span class="sxs-lookup"><span data-stu-id="bbca0-244">Heuristics</span></span></li>
<li><span data-ttu-id="bbca0-245">Generic</span><span class="sxs-lookup"><span data-stu-id="bbca0-245">Generic</span></span></li>
<li><span data-ttu-id="bbca0-246">Concreto</span><span class="sxs-lookup"><span data-stu-id="bbca0-246">Concrete</span></span></li>
<li><span data-ttu-id="bbca0-247">Firma dinámica</span><span class="sxs-lookup"><span data-stu-id="bbca0-247">Dynamic signature</span></span></li>
</ul><span data-ttu-id="bbca0-248">
</dt>
<dt>Origen de &lt; detección: origen de &gt; detección por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bbca0-248">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="bbca0-249">Usuario: usuario iniciado</span><span class="sxs-lookup"><span data-stu-id="bbca0-249">User: user initiated</span></span></li>
<li><span data-ttu-id="bbca0-250">Sistema: sistema iniciado</span><span class="sxs-lookup"><span data-stu-id="bbca0-250">System: system initiated</span></span></li>
<li><span data-ttu-id="bbca0-251">En tiempo real: componente en tiempo real iniciado</span><span class="sxs-lookup"><span data-stu-id="bbca0-251">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="bbca0-252">IOAV: Descargas de IE y Outlook datos adjuntos de Express iniciados</span><span class="sxs-lookup"><span data-stu-id="bbca0-252">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="bbca0-253">NIS: sistema de inspección de red</span><span class="sxs-lookup"><span data-stu-id="bbca0-253">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="bbca0-254">IEPROTECT: IE - IExtensionValidation; esto protege contra controles de páginas web malintencionadas</span><span class="sxs-lookup"><span data-stu-id="bbca0-254">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="bbca0-255">Antimalware de inicio anticipado (ELAM).</span><span class="sxs-lookup"><span data-stu-id="bbca0-255">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="bbca0-256">Esto incluye malware detectado por la secuencia de arranque</span><span class="sxs-lookup"><span data-stu-id="bbca0-256">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="bbca0-257">Atestación remota</span><span class="sxs-lookup"><span data-stu-id="bbca0-257">Remote attestation</span></span></li>
</ul><span data-ttu-id="bbca0-258">Interfaz de examen antimalware (AMSI).</span><span class="sxs-lookup"><span data-stu-id="bbca0-258">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="bbca0-259">Se usa principalmente para proteger scripts (PS, VBS), aunque también pueden invocarse por terceros.</span><span class="sxs-lookup"><span data-stu-id="bbca0-259">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="bbca0-260">Estado de </dt> 
<dt>UAC: Usuario &lt; &gt; de</dt>
<dt>estado: Dominio &lt; &gt; \& lt; Nombre &gt; </dt>del proceso de usuario: proceso en la versión de firma
<dt> &lt; &gt; PID:</dt>versión de
<dt> &lt; definición &gt; </dt>Versión del
<dt>motor: Antimalware Engine &lt; versión &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-260">UAC</dt>
<dt>Status: &lt;Status&gt;</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="bbca0-261">Identificador de evento: 1007</span><span class="sxs-lookup"><span data-stu-id="bbca0-261">Event ID: 1007</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="bbca0-262">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="bbca0-262">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="bbca0-263">
<b>MALWAREPROTECTION_MALWARE_ACTION_TAKEN </b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-263">
<b>MALWAREPROTECTION_MALWARE_ACTION_TAKEN </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-264">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="bbca0-264">Message:</span></span>
</td>
<td ><span data-ttu-id="bbca0-265">
<b>La plataforma antimalware realizó una acción para proteger el sistema de malware u otro software potencialmente no deseado. </b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-265">
<b>The antimalware platform performed an action to protect your system from malware or other potentially unwanted software. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-266">Descripción:</span><span class="sxs-lookup"><span data-stu-id="bbca0-266">Description:</span></span>
</td>
<td >
<span data-ttu-id="bbca0-267">Antivirus de Microsoft Defender ha tomado medidas para proteger esta máquina de malware u otro software potencialmente no deseado.</span><span class="sxs-lookup"><span data-stu-id="bbca0-267">Microsoft Defender Antivirus has taken action to protect this machine from malware or other potentially unwanted software.</span></span> <span data-ttu-id="bbca0-268">Para obtener más información, vea los artículos siguientes: </span><span class="sxs-lookup"><span data-stu-id="bbca0-268">For more information, see the following:</span></span>
<dl><span data-ttu-id="bbca0-269">
<dt>Usuario: &lt; Dominio &gt; \& lt; Nombre &gt; </dt>
<dt>de usuario: &lt; Identificador de nombre &gt; de</dt>
<dt>amenaza: &lt; &gt; Id.</dt>de amenaza 
<dt> Gravedad: Gravedad , por &lt; &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bbca0-269">
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="bbca0-270">Bajo</span><span class="sxs-lookup"><span data-stu-id="bbca0-270">Low</span></span></li>
<li><span data-ttu-id="bbca0-271">Moderado</span><span class="sxs-lookup"><span data-stu-id="bbca0-271">Moderate</span></span></li>
<li><span data-ttu-id="bbca0-272">Alto</span><span class="sxs-lookup"><span data-stu-id="bbca0-272">High</span></span></li>
<li><span data-ttu-id="bbca0-273">Grave</span><span class="sxs-lookup"><span data-stu-id="bbca0-273">Severe</span></span></li>
</ul><span data-ttu-id="bbca0-274">
</dt>
<dt>Categoría: &lt; Descripción de &gt; categoría , por ejemplo, cualquier tipo de amenaza o malware.</dt> 
<dt> Action: &lt; Action , por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bbca0-274">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Action: &lt;Action&gt;, for example:</span></span><ul>
<li><span data-ttu-id="bbca0-275">Clean: el recurso se ha limpiado</span><span class="sxs-lookup"><span data-stu-id="bbca0-275">Clean: The resource was cleaned</span></span></li>
<li><span data-ttu-id="bbca0-276">Cuarentena: el recurso se ha puesto en cuarentena</span><span class="sxs-lookup"><span data-stu-id="bbca0-276">Quarantine: The resource was quarantined</span></span></li>
<li><span data-ttu-id="bbca0-277">Quitar: se eliminó el recurso</span><span class="sxs-lookup"><span data-stu-id="bbca0-277">Remove: The resource was deleted</span></span></li>
<li><span data-ttu-id="bbca0-278">Permitir: se permitió que el recurso se ejecutara o existiera</span><span class="sxs-lookup"><span data-stu-id="bbca0-278">Allow: The resource was allowed to execute/exist</span></span></li>
<li><span data-ttu-id="bbca0-279">Definido por el usuario: acción definida por el usuario que normalmente es una de esta lista de acciones que el usuario ha especificado</span><span class="sxs-lookup"><span data-stu-id="bbca0-279">User defined: User-defined action that is normally one from this list of actions that the user has specified</span></span></li>
<li><span data-ttu-id="bbca0-280">Sin acción: sin acción</span><span class="sxs-lookup"><span data-stu-id="bbca0-280">No action: No action</span></span></li>
<li><span data-ttu-id="bbca0-281">Bloquear: se bloqueó el recurso para que no se ejecutara</span><span class="sxs-lookup"><span data-stu-id="bbca0-281">Block: The resource was blocked from executing</span></span></li>
</ul><span data-ttu-id="bbca0-282">
</dt>
<dt>Estado: &lt; Status &gt; </dt>
<dt>Signature Version: &lt; Definition version &gt; </dt>Engine
<dt>Version: Antimalware Engine &lt; version &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-282">
</dt>
<dt>Status: &lt;Status&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="bbca0-283">Identificador de evento: 1008</span><span class="sxs-lookup"><span data-stu-id="bbca0-283">Event ID: 1008</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="bbca0-284">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="bbca0-284">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="bbca0-285">
<b>MALWAREPROTECTION_MALWARE_ACTION_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-285">
<b>MALWAREPROTECTION_MALWARE_ACTION_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-286">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="bbca0-286">Message:</span></span>
</td>
<td ><span data-ttu-id="bbca0-287">
<b>La plataforma antimalware intentó realizar una acción para proteger el sistema de malware u otro software potencialmente no deseado, pero la acción falló.</b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-287">
<b>The antimalware platform attempted to perform an action to protect your system from malware or other potentially unwanted software, but the action failed.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-288">Descripción:</span><span class="sxs-lookup"><span data-stu-id="bbca0-288">Description:</span></span>
</td>
<td >
<span data-ttu-id="bbca0-289">Antivirus de Microsoft Defender ha encontrado un error al tomar medidas en malware u otro software potencialmente no deseado.</span><span class="sxs-lookup"><span data-stu-id="bbca0-289">Microsoft Defender Antivirus has encountered an error when taking action on malware or other potentially unwanted software.</span></span> <span data-ttu-id="bbca0-290">Para obtener más información, vea los artículos siguientes: </span><span class="sxs-lookup"><span data-stu-id="bbca0-290">For more information, see the following:</span></span>
<dl><span data-ttu-id="bbca0-291">
<dt>Usuario: &lt; Dominio &gt; \& lt; Nombre &gt; </dt>
<dt>de usuario: &lt; Identificador de nombre &gt; de</dt>
<dt>amenaza: &lt; &gt; Id.</dt>de amenaza 
<dt> Gravedad: Gravedad , por &lt; &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bbca0-291">
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="bbca0-292">Bajo</span><span class="sxs-lookup"><span data-stu-id="bbca0-292">Low</span></span></li>
<li><span data-ttu-id="bbca0-293">Moderado</span><span class="sxs-lookup"><span data-stu-id="bbca0-293">Moderate</span></span></li>
<li><span data-ttu-id="bbca0-294">Alto</span><span class="sxs-lookup"><span data-stu-id="bbca0-294">High</span></span></li>
<li><span data-ttu-id="bbca0-295">Grave</span><span class="sxs-lookup"><span data-stu-id="bbca0-295">Severe</span></span></li>
</ul><span data-ttu-id="bbca0-296">
</dt>
<dt>Categoría: &lt; Descripción de &gt; categoría , por ejemplo, cualquier tipo de amenaza o malware.</dt> 
<dt>Ruta de acceso: &lt; Ruta &gt; de acceso</dt> 
<dt> de archivo &lt; Acción: Acción , por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bbca0-296">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Action: &lt;Action&gt;, for example:</span></span><ul>
<li><span data-ttu-id="bbca0-297">Clean: el recurso se ha limpiado</span><span class="sxs-lookup"><span data-stu-id="bbca0-297">Clean: The resource was cleaned</span></span></li>
<li><span data-ttu-id="bbca0-298">Cuarentena: el recurso se ha puesto en cuarentena</span><span class="sxs-lookup"><span data-stu-id="bbca0-298">Quarantine: The resource was quarantined</span></span></li>
<li><span data-ttu-id="bbca0-299">Quitar: se eliminó el recurso</span><span class="sxs-lookup"><span data-stu-id="bbca0-299">Remove: The resource was deleted</span></span></li>
<li><span data-ttu-id="bbca0-300">Permitir: se permitió que el recurso se ejecutara o existiera</span><span class="sxs-lookup"><span data-stu-id="bbca0-300">Allow: The resource was allowed to execute/exist</span></span></li>
<li><span data-ttu-id="bbca0-301">Definido por el usuario: acción definida por el usuario que normalmente es una de esta lista de acciones que el usuario ha especificado</span><span class="sxs-lookup"><span data-stu-id="bbca0-301">User defined: User-defined action that is normally one from this list of actions that the user has specified</span></span></li>
<li><span data-ttu-id="bbca0-302">Sin acción: sin acción</span><span class="sxs-lookup"><span data-stu-id="bbca0-302">No action: No action</span></span></li>
<li><span data-ttu-id="bbca0-303">Bloquear: se bloqueó el recurso para que no se ejecutara</span><span class="sxs-lookup"><span data-stu-id="bbca0-303">Block: The resource was blocked from executing</span></span></li>
</ul><span data-ttu-id="bbca0-304">
</dt>
<dt>Código de error: &lt; Código de error &gt; Código de resultado asociado con el estado de amenaza. Valores HRESULT estándar. </dt> 
<dt>Descripción del error: &lt; Descripción del error Descripción del &gt; error.</dt> 
<dt>Estado: &lt; Status &gt; </dt>
<dt>Signature Version: &lt; Definition version &gt; </dt>Engine
<dt>Version: Antimalware Engine &lt; version &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-304">
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
<th colspan="2"><span data-ttu-id="bbca0-305">Identificador de evento: 1009</span><span class="sxs-lookup"><span data-stu-id="bbca0-305">Event ID: 1009</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="bbca0-306">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="bbca0-306">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="bbca0-307">
<b>MALWAREPROTECTION_QUARANTINE_RESTORE </b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-307">
<b>MALWAREPROTECTION_QUARANTINE_RESTORE </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-308">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="bbca0-308">Message:</span></span>
</td>
<td ><span data-ttu-id="bbca0-309">
<b>La plataforma antimalware restauró un elemento de cuarentena. </b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-309">
<b>The antimalware platform restored an item from quarantine. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-310">Descripción:</span><span class="sxs-lookup"><span data-stu-id="bbca0-310">Description:</span></span>
</td>
<td >
<span data-ttu-id="bbca0-311">Antivirus de Microsoft Defender ha restaurado un elemento de cuarentena.</span><span class="sxs-lookup"><span data-stu-id="bbca0-311">Microsoft Defender Antivirus has restored an item from quarantine.</span></span> <span data-ttu-id="bbca0-312">Para obtener más información, vea los artículos siguientes: </span><span class="sxs-lookup"><span data-stu-id="bbca0-312">For more information, see the following:</span></span>
<dl><span data-ttu-id="bbca0-313">
<dt>Nombre: &lt; Id. &gt; de</dt>
<dt>nombre de &lt; amenaza: Gravedad del id. &gt; </dt>de 
<dt> amenaza: gravedad , por &lt; &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bbca0-313">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="bbca0-314">Bajo</span><span class="sxs-lookup"><span data-stu-id="bbca0-314">Low</span></span></li>
<li><span data-ttu-id="bbca0-315">Moderado</span><span class="sxs-lookup"><span data-stu-id="bbca0-315">Moderate</span></span></li>
<li><span data-ttu-id="bbca0-316">Alto</span><span class="sxs-lookup"><span data-stu-id="bbca0-316">High</span></span></li>
<li><span data-ttu-id="bbca0-317">Grave</span><span class="sxs-lookup"><span data-stu-id="bbca0-317">Severe</span></span></li>
</ul><span data-ttu-id="bbca0-318">
</dt>
<dt>Categoría: &lt; Descripción de &gt; categoría , por ejemplo, cualquier tipo de amenaza o malware.</dt> 
<dt>Ruta de acceso: &lt; Usuario &gt; de ruta de</dt>
<dt>acceso de &lt; archivo: Dominio &gt; \& lt; User &gt; </dt>
<dt>Signature Version: &lt; Definition version &gt; </dt>Engine
<dt>Version: Antimalware Engine &lt; version &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-318">
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
<th colspan="2"><span data-ttu-id="bbca0-319">Identificador de evento: 1010</span><span class="sxs-lookup"><span data-stu-id="bbca0-319">Event ID: 1010</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="bbca0-320">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="bbca0-320">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="bbca0-321">
<b>MALWAREPROTECTION_QUARANTINE_RESTORE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-321">
<b>MALWAREPROTECTION_QUARANTINE_RESTORE_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-322">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="bbca0-322">Message:</span></span>
</td>
<td ><span data-ttu-id="bbca0-323">
<b>La plataforma antimalware no pudo restaurar un elemento de cuarentena. </b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-323">
<b>The antimalware platform could not restore an item from quarantine. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-324">Descripción:</span><span class="sxs-lookup"><span data-stu-id="bbca0-324">Description:</span></span>
</td>
<td >
<span data-ttu-id="bbca0-325">Antivirus de Microsoft Defender ha encontrado un error al intentar restaurar un elemento desde la cuarentena.</span><span class="sxs-lookup"><span data-stu-id="bbca0-325">Microsoft Defender Antivirus has encountered an error trying to restore an item from quarantine.</span></span> <span data-ttu-id="bbca0-326">Para obtener más información, vea los artículos siguientes: </span><span class="sxs-lookup"><span data-stu-id="bbca0-326">For more information, see the following:</span></span>
<dl><span data-ttu-id="bbca0-327">
<dt>Nombre: &lt; Id. &gt; de</dt>
<dt>nombre de &lt; amenaza: Gravedad del id. &gt; </dt>de 
<dt> amenaza: gravedad , por &lt; &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bbca0-327">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="bbca0-328">Bajo</span><span class="sxs-lookup"><span data-stu-id="bbca0-328">Low</span></span></li>
<li><span data-ttu-id="bbca0-329">Moderado</span><span class="sxs-lookup"><span data-stu-id="bbca0-329">Moderate</span></span></li>
<li><span data-ttu-id="bbca0-330">Alto</span><span class="sxs-lookup"><span data-stu-id="bbca0-330">High</span></span></li>
<li><span data-ttu-id="bbca0-331">Grave</span><span class="sxs-lookup"><span data-stu-id="bbca0-331">Severe</span></span></li>
</ul><span data-ttu-id="bbca0-332">
</dt>
<dt>Categoría: &lt; Descripción de &gt; categoría , por ejemplo, cualquier tipo de amenaza o malware.</dt> 
<dt>Ruta de acceso: &lt; Usuario &gt; de ruta de</dt>
<dt>acceso de &lt; archivo: Dominio &gt; \& lt; Código &gt; </dt>
<dt>de error del usuario: Código de error &lt; Código de resultado asociado con el estado de &gt; amenaza. Valores HRESULT estándar. </dt> 
<dt>Descripción del error: &lt; Descripción del error Descripción del &gt; error.</dt> 
<dt>Versión de firma: &lt; Versión &gt; de definición</dt>
<dt>Versión del motor: &lt; Antimalware Engine versión &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-332">
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
<th colspan="2"><span data-ttu-id="bbca0-333">Identificador de evento: 1011</span><span class="sxs-lookup"><span data-stu-id="bbca0-333">Event ID: 1011</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="bbca0-334">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="bbca0-334">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="bbca0-335">
<b>MALWAREPROTECTION_QUARANTINE_DELETE</b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-335">
<b>MALWAREPROTECTION_QUARANTINE_DELETE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-336">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="bbca0-336">Message:</span></span>
</td>
<td ><span data-ttu-id="bbca0-337">
<b>La plataforma antimalware eliminó un elemento de la cuarentena. </b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-337">
<b>The antimalware platform deleted an item from quarantine. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-338">Descripción:</span><span class="sxs-lookup"><span data-stu-id="bbca0-338">Description:</span></span>
</td>
<td >
<span data-ttu-id="bbca0-339">Antivirus de Microsoft Defender ha eliminado un elemento de la cuarentena.</span><span class="sxs-lookup"><span data-stu-id="bbca0-339">Microsoft Defender Antivirus has deleted an item from quarantine.</span></span><br/><span data-ttu-id="bbca0-340">Para obtener más información, vea los artículos siguientes: </span><span class="sxs-lookup"><span data-stu-id="bbca0-340">For more information, see the following:</span></span>
<dl><span data-ttu-id="bbca0-341">
<dt>Nombre: &lt; Id. &gt; de</dt>
<dt>nombre de &lt; amenaza: Gravedad del id. &gt; </dt>de 
<dt> amenaza: gravedad , por &lt; &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bbca0-341">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="bbca0-342">Bajo</span><span class="sxs-lookup"><span data-stu-id="bbca0-342">Low</span></span></li>
<li><span data-ttu-id="bbca0-343">Moderado</span><span class="sxs-lookup"><span data-stu-id="bbca0-343">Moderate</span></span></li>
<li><span data-ttu-id="bbca0-344">Alto</span><span class="sxs-lookup"><span data-stu-id="bbca0-344">High</span></span></li>
<li><span data-ttu-id="bbca0-345">Grave</span><span class="sxs-lookup"><span data-stu-id="bbca0-345">Severe</span></span></li>
</ul><span data-ttu-id="bbca0-346">
</dt>
<dt>Categoría: &lt; Descripción de &gt; categoría , por ejemplo, cualquier tipo de amenaza o malware.</dt> 
<dt>Ruta de acceso: &lt; Usuario &gt; de ruta de</dt>
<dt>acceso de &lt; archivo: Dominio &gt; \& lt; User &gt; </dt>
<dt>Signature Version: &lt; Definition version &gt; </dt>Engine
<dt>Version: Antimalware Engine &lt; version &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-346">
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
<th colspan="2"><span data-ttu-id="bbca0-347">Identificador de evento: 1012</span><span class="sxs-lookup"><span data-stu-id="bbca0-347">Event ID: 1012</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="bbca0-348">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="bbca0-348">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="bbca0-349">
<b>MALWAREPROTECTION_QUARANTINE_DELETE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-349">
<b>MALWAREPROTECTION_QUARANTINE_DELETE_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-350">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="bbca0-350">Message:</span></span>
</td>
<td ><span data-ttu-id="bbca0-351">
<b>La plataforma antimalware no pudo eliminar un elemento de la cuarentena.</b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-351">
<b>The antimalware platform could not delete an item from quarantine.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-352">Descripción:</span><span class="sxs-lookup"><span data-stu-id="bbca0-352">Description:</span></span>
</td>
<td >
<span data-ttu-id="bbca0-353">Antivirus de Microsoft Defender ha encontrado un error al intentar eliminar un elemento de la cuarentena.</span><span class="sxs-lookup"><span data-stu-id="bbca0-353">Microsoft Defender Antivirus has encountered an error trying to delete an item from quarantine.</span></span>
<span data-ttu-id="bbca0-354">Para obtener más información, vea los artículos siguientes: </span><span class="sxs-lookup"><span data-stu-id="bbca0-354">For more information, see the following:</span></span>
<dl><span data-ttu-id="bbca0-355">
<dt>Nombre: &lt; Id. &gt; de</dt>
<dt>nombre de &lt; amenaza: Gravedad del id. &gt; </dt>de 
<dt> amenaza: gravedad , por &lt; &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bbca0-355">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="bbca0-356">Bajo</span><span class="sxs-lookup"><span data-stu-id="bbca0-356">Low</span></span></li>
<li><span data-ttu-id="bbca0-357">Moderado</span><span class="sxs-lookup"><span data-stu-id="bbca0-357">Moderate</span></span></li>
<li><span data-ttu-id="bbca0-358">Alto</span><span class="sxs-lookup"><span data-stu-id="bbca0-358">High</span></span></li>
<li><span data-ttu-id="bbca0-359">Grave</span><span class="sxs-lookup"><span data-stu-id="bbca0-359">Severe</span></span></li>
</ul><span data-ttu-id="bbca0-360">
</dt>
<dt>Categoría: &lt; Descripción de &gt; categoría , por ejemplo, cualquier tipo de amenaza o malware.</dt> 
<dt>Ruta de acceso: &lt; Usuario &gt; de ruta de</dt>
<dt>acceso de &lt; archivo: Dominio &gt; \& lt; Código &gt; </dt>
<dt>de error del usuario: Código de error &lt; Código de resultado asociado con el estado de &gt; amenaza. Valores HRESULT estándar. </dt> 
<dt>Descripción del error: &lt; Descripción del error Descripción del &gt; error.</dt> 
<dt>Versión de firma: &lt; Versión &gt; de definición</dt>
<dt>Versión del motor: &lt; Antimalware Engine versión &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-360">
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
<th colspan="2"><span data-ttu-id="bbca0-361">Identificador de evento: 1013</span><span class="sxs-lookup"><span data-stu-id="bbca0-361">Event ID: 1013</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="bbca0-362">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="bbca0-362">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="bbca0-363">
<b>MALWAREPROTECTION_MALWARE_HISTORY_DELETE </b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-363">
<b>MALWAREPROTECTION_MALWARE_HISTORY_DELETE </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-364">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="bbca0-364">Message:</span></span>
</td>
<td ><span data-ttu-id="bbca0-365">
<b>La plataforma antimalware eliminó el historial de malware y otro software potencialmente no deseado.</b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-365">
<b>The antimalware platform deleted history of malware and other potentially unwanted software.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-366">Descripción:</span><span class="sxs-lookup"><span data-stu-id="bbca0-366">Description:</span></span>
</td>
<td >
<span data-ttu-id="bbca0-367">Antivirus de Microsoft Defender ha eliminado el historial de malware y otro software potencialmente no deseado.</span><span class="sxs-lookup"><span data-stu-id="bbca0-367">Microsoft Defender Antivirus has removed history of malware and other potentially unwanted software.</span></span>
<dl><span data-ttu-id="bbca0-368">
<dt>Hora: hora en la que se produjo el evento, por ejemplo, cuando se purga el historial. Este parámetro no se usa en eventos de amenazas para que no haya confusión con respecto a si es tiempo de corrección o tiempo de infección. Para ellos, los llamamos específicamente tiempo de acción o tiempo de detección.</dt> 
<dt>Usuario: &lt; Dominio &gt; \& lt; Usuario &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-368">
<dt>Time: The time when the event occurred, for example when the history is purged. This parameter is not used in threat events so that there is no confusion regarding whether it is remediation time or infection time. For those, we specifically call them as Action Time or Detection Time.</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="bbca0-369">Identificador de evento: 1014</span><span class="sxs-lookup"><span data-stu-id="bbca0-369">Event ID: 1014</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="bbca0-370">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="bbca0-370">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="bbca0-371">
<b>MALWAREPROTECTION_MALWARE_HISTORY_DELETE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-371">
<b>MALWAREPROTECTION_MALWARE_HISTORY_DELETE_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-372">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="bbca0-372">Message:</span></span>
</td>
<td >
<span data-ttu-id="bbca0-373">La plataforma antimalware no pudo eliminar el historial de malware y otro software potencialmente no deseado.</span><span class="sxs-lookup"><span data-stu-id="bbca0-373">The antimalware platform could not delete history of malware and other potentially unwanted software.</span></span>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-374">Descripción:</span><span class="sxs-lookup"><span data-stu-id="bbca0-374">Description:</span></span>
</td>
<td >
<span data-ttu-id="bbca0-375">Antivirus de Microsoft Defender ha encontrado un error al intentar quitar el historial de malware y otro software potencialmente no deseado.</span><span class="sxs-lookup"><span data-stu-id="bbca0-375">Microsoft Defender Antivirus has encountered an error trying to remove history of malware and other potentially unwanted software.</span></span>
<dl><span data-ttu-id="bbca0-376">
<dt>Hora: hora en la que se produjo el evento, por ejemplo, cuando se purga el historial. Este parámetro no se usa en eventos de amenazas para que no haya confusión con respecto a si es tiempo de corrección o tiempo de infección. Para ellos, los llamamos específicamente tiempo de acción o tiempo de detección.</dt> 
<dt>Usuario: &lt; Dominio &gt; \& lt; Código &gt; </dt>
<dt>de error del usuario: Código de error &lt; Código de resultado asociado con el estado de &gt; amenaza. Valores HRESULT estándar. </dt> 
<dt>Descripción del error: &lt; Descripción del error Descripción del &gt; error.</dt>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-376">
<dt>Time: The time when the event occurred, for example when the history is purged. This parameter is not used in threat events so that there is no confusion regarding whether it is remediation time or infection time. For those, we specifically call them as Action Time or Detection Time.</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values. </dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="bbca0-377">Identificador de evento: 1015</span><span class="sxs-lookup"><span data-stu-id="bbca0-377">Event ID: 1015</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="bbca0-378">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="bbca0-378">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="bbca0-379">
<b>MALWAREPROTECTION_BEHAVIOR_DETECTED </b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-379">
<b>MALWAREPROTECTION_BEHAVIOR_DETECTED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-380">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="bbca0-380">Message:</span></span>
</td>
<td ><span data-ttu-id="bbca0-381">
<b>La plataforma antimalware detectó un comportamiento sospechoso.</b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-381">
<b>The antimalware platform detected suspicious behavior.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-382">Descripción:</span><span class="sxs-lookup"><span data-stu-id="bbca0-382">Description:</span></span>
</td>
<td >
<span data-ttu-id="bbca0-383">Antivirus de Microsoft Defender ha detectado un comportamiento sospechoso.</span><span class="sxs-lookup"><span data-stu-id="bbca0-383">Microsoft Defender Antivirus has detected a suspicious behavior.</span></span><br/><span data-ttu-id="bbca0-384">Para obtener más información, vea los artículos siguientes: </span><span class="sxs-lookup"><span data-stu-id="bbca0-384">For more information, see the following:</span></span>
<dl><span data-ttu-id="bbca0-385">
<dt>Nombre: &lt; Id. &gt; de</dt>
<dt>nombre de &lt; amenaza: Gravedad del id. &gt; </dt>de 
<dt> amenaza: gravedad , por &lt; &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bbca0-385">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="bbca0-386">Bajo</span><span class="sxs-lookup"><span data-stu-id="bbca0-386">Low</span></span></li>
<li><span data-ttu-id="bbca0-387">Moderado</span><span class="sxs-lookup"><span data-stu-id="bbca0-387">Moderate</span></span></li>
<li><span data-ttu-id="bbca0-388">Alto</span><span class="sxs-lookup"><span data-stu-id="bbca0-388">High</span></span></li>
<li><span data-ttu-id="bbca0-389">Grave</span><span class="sxs-lookup"><span data-stu-id="bbca0-389">Severe</span></span></li>
</ul><span data-ttu-id="bbca0-390">
</dt>
<dt>Categoría: &lt; Descripción de &gt; categoría , por ejemplo, cualquier tipo de amenaza o malware.</dt> 
<dt>Ruta de acceso: &lt; Origen &gt; de detección</dt>de ruta de 
<dt> acceso de &lt; archivo: Origen de &gt; detección, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bbca0-390">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="bbca0-391">Desconocido</span><span class="sxs-lookup"><span data-stu-id="bbca0-391">Unknown</span></span></li>
<li><span data-ttu-id="bbca0-392">Equipo local</span><span class="sxs-lookup"><span data-stu-id="bbca0-392">Local computer</span></span></li>
<li><span data-ttu-id="bbca0-393">Recurso compartido de red</span><span class="sxs-lookup"><span data-stu-id="bbca0-393">Network share</span></span></li>
<li><span data-ttu-id="bbca0-394">Internet</span><span class="sxs-lookup"><span data-stu-id="bbca0-394">Internet</span></span></li>
<li><span data-ttu-id="bbca0-395">Tráfico entrante</span><span class="sxs-lookup"><span data-stu-id="bbca0-395">Incoming traffic</span></span></li>
<li><span data-ttu-id="bbca0-396">Tráfico saliente</span><span class="sxs-lookup"><span data-stu-id="bbca0-396">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="bbca0-397">
</dt>
<dt>Tipo de &lt; detección: Tipo de &gt; detección , por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bbca0-397">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="bbca0-398">Heurística</span><span class="sxs-lookup"><span data-stu-id="bbca0-398">Heuristics</span></span></li>
<li><span data-ttu-id="bbca0-399">Generic</span><span class="sxs-lookup"><span data-stu-id="bbca0-399">Generic</span></span></li>
<li><span data-ttu-id="bbca0-400">Concreto</span><span class="sxs-lookup"><span data-stu-id="bbca0-400">Concrete</span></span></li>
<li><span data-ttu-id="bbca0-401">Firma dinámica</span><span class="sxs-lookup"><span data-stu-id="bbca0-401">Dynamic signature</span></span></li>
</ul><span data-ttu-id="bbca0-402">
</dt>
<dt>Origen de &lt; detección: origen de &gt; detección por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bbca0-402">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="bbca0-403">Usuario: usuario iniciado</span><span class="sxs-lookup"><span data-stu-id="bbca0-403">User: user initiated</span></span></li>
<li><span data-ttu-id="bbca0-404">Sistema: sistema iniciado</span><span class="sxs-lookup"><span data-stu-id="bbca0-404">System: system initiated</span></span></li>
<li><span data-ttu-id="bbca0-405">En tiempo real: componente en tiempo real iniciado</span><span class="sxs-lookup"><span data-stu-id="bbca0-405">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="bbca0-406">IOAV: Descargas de IE y Outlook datos adjuntos de Express iniciados</span><span class="sxs-lookup"><span data-stu-id="bbca0-406">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="bbca0-407">NIS: sistema de inspección de red</span><span class="sxs-lookup"><span data-stu-id="bbca0-407">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="bbca0-408">IEPROTECT: IE - IExtensionValidation; esto protege contra controles de páginas web malintencionadas</span><span class="sxs-lookup"><span data-stu-id="bbca0-408">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="bbca0-409">Antimalware de inicio anticipado (ELAM).</span><span class="sxs-lookup"><span data-stu-id="bbca0-409">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="bbca0-410">Esto incluye malware detectado por la secuencia de arranque</span><span class="sxs-lookup"><span data-stu-id="bbca0-410">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="bbca0-411">Atestación remota</span><span class="sxs-lookup"><span data-stu-id="bbca0-411">Remote attestation</span></span></li>
</ul><span data-ttu-id="bbca0-412">Interfaz de examen antimalware (AMSI).</span><span class="sxs-lookup"><span data-stu-id="bbca0-412">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="bbca0-413">Se usa principalmente para proteger scripts (PS, VBS), aunque también pueden invocarse por terceros.</span><span class="sxs-lookup"><span data-stu-id="bbca0-413">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="bbca0-414">Estado de </dt> 
<dt>UAC: Usuario &lt; &gt; de</dt>
<dt>estado: Dominio &lt; &gt; \& lt; Nombre &gt; </dt>del proceso de usuario: proceso en el identificador de firma
<dt> &lt; &gt; PID:</dt>
<dt>Gravedad de coincidencia de enumeración.</dt> 
<dt>Versión de firma: &lt; Versión &gt; de definición</dt>Versión del
<dt> &lt; motor: &gt; Antimalware Engine versión Fidelity</dt>
<dt>Label:</dt>Nombre del archivo de
<dt>destino: Nombre de archivo del &lt; &gt; archivo.</dt>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-414">UAC</dt>
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
<th colspan="2"><span data-ttu-id="bbca0-415">Identificador de evento: 1116</span><span class="sxs-lookup"><span data-stu-id="bbca0-415">Event ID: 1116</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="bbca0-416">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="bbca0-416">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="bbca0-417">
<b>MALWAREPROTECTION_STATE_MALWARE_DETECTED</b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-417">
<b>MALWAREPROTECTION_STATE_MALWARE_DETECTED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-418">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="bbca0-418">Message:</span></span>
</td>
<td ><span data-ttu-id="bbca0-419">
<b>La plataforma antimalware detectó malware u otro software potencialmente no deseado. </b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-419">
<b>The antimalware platform detected malware or other potentially unwanted software. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-420">Descripción:</span><span class="sxs-lookup"><span data-stu-id="bbca0-420">Description:</span></span>
</td>
<td >
<span data-ttu-id="bbca0-421">Antivirus de Microsoft Defender ha detectado malware u otro software potencialmente no deseado.</span><span class="sxs-lookup"><span data-stu-id="bbca0-421">Microsoft Defender Antivirus has detected malware or other potentially unwanted software.</span></span><br/><span data-ttu-id="bbca0-422">Para obtener más información, vea los artículos siguientes: </span><span class="sxs-lookup"><span data-stu-id="bbca0-422">For more information, see the following:</span></span>
<dl><span data-ttu-id="bbca0-423">
<dt>Nombre: &lt; Id. &gt; de</dt>
<dt>nombre de &lt; amenaza: Gravedad del id. &gt; </dt>de 
<dt> amenaza: gravedad , por &lt; &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bbca0-423">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="bbca0-424">Bajo</span><span class="sxs-lookup"><span data-stu-id="bbca0-424">Low</span></span></li>
<li><span data-ttu-id="bbca0-425">Moderado</span><span class="sxs-lookup"><span data-stu-id="bbca0-425">Moderate</span></span></li>
<li><span data-ttu-id="bbca0-426">Alto</span><span class="sxs-lookup"><span data-stu-id="bbca0-426">High</span></span></li>
<li><span data-ttu-id="bbca0-427">Grave</span><span class="sxs-lookup"><span data-stu-id="bbca0-427">Severe</span></span></li>
</ul><span data-ttu-id="bbca0-428">
</dt>
<dt>Categoría: &lt; Descripción de &gt; categoría , por ejemplo, cualquier tipo de amenaza o malware.</dt> 
<dt>Ruta de acceso: &lt; Origen &gt; de detección</dt>de ruta de 
<dt> acceso de &lt; archivo: Origen de &gt; detección, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bbca0-428">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="bbca0-429">Desconocido</span><span class="sxs-lookup"><span data-stu-id="bbca0-429">Unknown</span></span></li>
<li><span data-ttu-id="bbca0-430">Equipo local</span><span class="sxs-lookup"><span data-stu-id="bbca0-430">Local computer</span></span></li>
<li><span data-ttu-id="bbca0-431">Recurso compartido de red</span><span class="sxs-lookup"><span data-stu-id="bbca0-431">Network share</span></span></li>
<li><span data-ttu-id="bbca0-432">Internet</span><span class="sxs-lookup"><span data-stu-id="bbca0-432">Internet</span></span></li>
<li><span data-ttu-id="bbca0-433">Tráfico entrante</span><span class="sxs-lookup"><span data-stu-id="bbca0-433">Incoming traffic</span></span></li>
<li><span data-ttu-id="bbca0-434">Tráfico saliente</span><span class="sxs-lookup"><span data-stu-id="bbca0-434">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="bbca0-435">
</dt>
<dt>Tipo de &lt; detección: Tipo de &gt; detección , por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bbca0-435">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="bbca0-436">Heurística</span><span class="sxs-lookup"><span data-stu-id="bbca0-436">Heuristics</span></span></li>
<li><span data-ttu-id="bbca0-437">Generic</span><span class="sxs-lookup"><span data-stu-id="bbca0-437">Generic</span></span></li>
<li><span data-ttu-id="bbca0-438">Concreto</span><span class="sxs-lookup"><span data-stu-id="bbca0-438">Concrete</span></span></li>
<li><span data-ttu-id="bbca0-439">Firma dinámica</span><span class="sxs-lookup"><span data-stu-id="bbca0-439">Dynamic signature</span></span></li>
</ul><span data-ttu-id="bbca0-440">
</dt>
<dt>Origen de &lt; detección: origen de &gt; detección por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bbca0-440">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="bbca0-441">Usuario: usuario iniciado</span><span class="sxs-lookup"><span data-stu-id="bbca0-441">User: user initiated</span></span></li>
<li><span data-ttu-id="bbca0-442">Sistema: sistema iniciado</span><span class="sxs-lookup"><span data-stu-id="bbca0-442">System: system initiated</span></span></li>
<li><span data-ttu-id="bbca0-443">En tiempo real: componente en tiempo real iniciado</span><span class="sxs-lookup"><span data-stu-id="bbca0-443">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="bbca0-444">IOAV: Descargas de IE y Outlook datos adjuntos de Express iniciados</span><span class="sxs-lookup"><span data-stu-id="bbca0-444">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="bbca0-445">NIS: sistema de inspección de red</span><span class="sxs-lookup"><span data-stu-id="bbca0-445">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="bbca0-446">IEPROTECT: IE - IExtensionValidation; esto protege contra controles de páginas web malintencionadas</span><span class="sxs-lookup"><span data-stu-id="bbca0-446">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="bbca0-447">Antimalware de inicio anticipado (ELAM).</span><span class="sxs-lookup"><span data-stu-id="bbca0-447">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="bbca0-448">Esto incluye malware detectado por la secuencia de arranque</span><span class="sxs-lookup"><span data-stu-id="bbca0-448">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="bbca0-449">Atestación remota</span><span class="sxs-lookup"><span data-stu-id="bbca0-449">Remote attestation</span></span></li>
</ul><span data-ttu-id="bbca0-450">Interfaz de examen antimalware (AMSI).</span><span class="sxs-lookup"><span data-stu-id="bbca0-450">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="bbca0-451">Se usa principalmente para proteger scripts (PS, VBS), aunque también pueden invocarse por terceros.</span><span class="sxs-lookup"><span data-stu-id="bbca0-451">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="bbca0-452">Usuario de </dt> 
<dt>UAC: Dominio &lt; &gt; \& lt; Nombre &gt; </dt>del proceso de usuario: proceso en la versión de firma
<dt> &lt; &gt; PID:</dt>versión de
<dt> &lt; definición &gt; </dt>Versión del
<dt>motor: Antimalware Engine &lt; versión &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-452">UAC</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-453">Acción del usuario:</span><span class="sxs-lookup"><span data-stu-id="bbca0-453">User action:</span></span>
</td>
<td >
<span data-ttu-id="bbca0-454">No se requiere ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="bbca0-454">No action is required.</span></span> <span data-ttu-id="bbca0-455">Antivirus de Microsoft Defender suspender y tomar medidas rutinarias en esta amenaza.</span><span class="sxs-lookup"><span data-stu-id="bbca0-455">Microsoft Defender Antivirus can suspend and take routine action on this threat.</span></span> <span data-ttu-id="bbca0-456">Si desea quitar la amenaza manualmente, en la interfaz Antivirus de Microsoft Defender, haga clic en <b>Limpiar equipo</b>.</span><span class="sxs-lookup"><span data-stu-id="bbca0-456">If you want to remove the threat manually, in the Microsoft Defender Antivirus interface, click <b>Clean Computer</b>.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="bbca0-457">Identificador de evento: 1117</span><span class="sxs-lookup"><span data-stu-id="bbca0-457">Event ID: 1117</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="bbca0-458">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="bbca0-458">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="bbca0-459">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_TAKEN </b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-459">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_TAKEN </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-460">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="bbca0-460">Message:</span></span>
</td>
<td ><span data-ttu-id="bbca0-461">
<b>La plataforma antimalware realizó una acción para proteger el sistema de malware u otro software potencialmente no deseado. </b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-461">
<b>The antimalware platform performed an action to protect your system from malware or other potentially unwanted software. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-462">Descripción:</span><span class="sxs-lookup"><span data-stu-id="bbca0-462">Description:</span></span>
</td>
<td >
<span data-ttu-id="bbca0-463">Antivirus de Microsoft Defender ha tomado medidas para proteger esta máquina de malware u otro software potencialmente no deseado.</span><span class="sxs-lookup"><span data-stu-id="bbca0-463">Microsoft Defender Antivirus has taken action to protect this machine from malware or other potentially unwanted software.</span></span><br/><span data-ttu-id="bbca0-464">Para obtener más información, vea los artículos siguientes: </span><span class="sxs-lookup"><span data-stu-id="bbca0-464">For more information, see the following:</span></span>
<dl><span data-ttu-id="bbca0-465">
<dt>Nombre: &lt; Id. &gt; de</dt>
<dt>nombre de &lt; amenaza: Gravedad del id. &gt; </dt>de 
<dt> amenaza: gravedad , por &lt; &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bbca0-465">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="bbca0-466">Bajo</span><span class="sxs-lookup"><span data-stu-id="bbca0-466">Low</span></span></li>
<li><span data-ttu-id="bbca0-467">Moderado</span><span class="sxs-lookup"><span data-stu-id="bbca0-467">Moderate</span></span></li>
<li><span data-ttu-id="bbca0-468">Alto</span><span class="sxs-lookup"><span data-stu-id="bbca0-468">High</span></span></li>
<li><span data-ttu-id="bbca0-469">Grave</span><span class="sxs-lookup"><span data-stu-id="bbca0-469">Severe</span></span></li>
</ul><span data-ttu-id="bbca0-470">
</dt>
<dt>Categoría: &lt; Descripción de &gt; categoría , por ejemplo, cualquier tipo de amenaza o malware.</dt> 
<dt>Ruta de acceso: &lt; Origen &gt; de detección</dt>de ruta de 
<dt> acceso de &lt; archivo: Origen de &gt; detección, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bbca0-470">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="bbca0-471">Desconocido</span><span class="sxs-lookup"><span data-stu-id="bbca0-471">Unknown</span></span></li>
<li><span data-ttu-id="bbca0-472">Equipo local</span><span class="sxs-lookup"><span data-stu-id="bbca0-472">Local computer</span></span></li>
<li><span data-ttu-id="bbca0-473">Recurso compartido de red</span><span class="sxs-lookup"><span data-stu-id="bbca0-473">Network share</span></span></li>
<li><span data-ttu-id="bbca0-474">Internet</span><span class="sxs-lookup"><span data-stu-id="bbca0-474">Internet</span></span></li>
<li><span data-ttu-id="bbca0-475">Tráfico entrante</span><span class="sxs-lookup"><span data-stu-id="bbca0-475">Incoming traffic</span></span></li>
<li><span data-ttu-id="bbca0-476">Tráfico saliente</span><span class="sxs-lookup"><span data-stu-id="bbca0-476">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="bbca0-477">
</dt>
<dt>Tipo de &lt; detección: Tipo de &gt; detección , por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bbca0-477">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="bbca0-478">Heurística</span><span class="sxs-lookup"><span data-stu-id="bbca0-478">Heuristics</span></span></li>
<li><span data-ttu-id="bbca0-479">Generic</span><span class="sxs-lookup"><span data-stu-id="bbca0-479">Generic</span></span></li>
<li><span data-ttu-id="bbca0-480">Concreto</span><span class="sxs-lookup"><span data-stu-id="bbca0-480">Concrete</span></span></li>
<li><span data-ttu-id="bbca0-481">Firma dinámica</span><span class="sxs-lookup"><span data-stu-id="bbca0-481">Dynamic signature</span></span></li>
</ul><span data-ttu-id="bbca0-482">
</dt>
<dt>Origen de &lt; detección: origen de &gt; detección por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bbca0-482">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="bbca0-483">Usuario: usuario iniciado</span><span class="sxs-lookup"><span data-stu-id="bbca0-483">User: user initiated</span></span></li>
<li><span data-ttu-id="bbca0-484">Sistema: sistema iniciado</span><span class="sxs-lookup"><span data-stu-id="bbca0-484">System: system initiated</span></span></li>
<li><span data-ttu-id="bbca0-485">En tiempo real: componente en tiempo real iniciado</span><span class="sxs-lookup"><span data-stu-id="bbca0-485">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="bbca0-486">IOAV: Descargas de IE y Outlook datos adjuntos de Express iniciados</span><span class="sxs-lookup"><span data-stu-id="bbca0-486">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="bbca0-487">NIS: sistema de inspección de red</span><span class="sxs-lookup"><span data-stu-id="bbca0-487">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="bbca0-488">IEPROTECT: IE - IExtensionValidation; esto protege contra controles de páginas web malintencionadas</span><span class="sxs-lookup"><span data-stu-id="bbca0-488">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="bbca0-489">Antimalware de inicio anticipado (ELAM).</span><span class="sxs-lookup"><span data-stu-id="bbca0-489">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="bbca0-490">Esto incluye malware detectado por la secuencia de arranque</span><span class="sxs-lookup"><span data-stu-id="bbca0-490">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="bbca0-491">Atestación remota</span><span class="sxs-lookup"><span data-stu-id="bbca0-491">Remote attestation</span></span></li>
</ul><span data-ttu-id="bbca0-492">Interfaz de examen antimalware (AMSI).</span><span class="sxs-lookup"><span data-stu-id="bbca0-492">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="bbca0-493">Se usa principalmente para proteger scripts (PS, VBS), aunque también pueden invocarse por terceros.</span><span class="sxs-lookup"><span data-stu-id="bbca0-493">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="bbca0-494">Usuario de </dt> 
<dt>UAC: Dominio &lt; &gt; \& lt; Nombre &gt; </dt>
<dt>del proceso de usuario: Proceso en la &lt; acción &gt; pid:</dt>Acción , por 
<dt> &lt; &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bbca0-494">UAC</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Action: &lt;Action&gt;, for example:</span></span><ul>
<li><span data-ttu-id="bbca0-495">Clean: el recurso se ha limpiado</span><span class="sxs-lookup"><span data-stu-id="bbca0-495">Clean: The resource was cleaned</span></span></li>
<li><span data-ttu-id="bbca0-496">Cuarentena: el recurso se ha puesto en cuarentena</span><span class="sxs-lookup"><span data-stu-id="bbca0-496">Quarantine: The resource was quarantined</span></span></li>
<li><span data-ttu-id="bbca0-497">Quitar: se eliminó el recurso</span><span class="sxs-lookup"><span data-stu-id="bbca0-497">Remove: The resource was deleted</span></span></li>
<li><span data-ttu-id="bbca0-498">Permitir: se permitió que el recurso se ejecutara o existiera</span><span class="sxs-lookup"><span data-stu-id="bbca0-498">Allow: The resource was allowed to execute/exist</span></span></li>
<li><span data-ttu-id="bbca0-499">Definido por el usuario: acción definida por el usuario que normalmente es una de esta lista de acciones que el usuario ha especificado</span><span class="sxs-lookup"><span data-stu-id="bbca0-499">User defined: User-defined action that is normally one from this list of actions that the user has specified</span></span></li>
<li><span data-ttu-id="bbca0-500">Sin acción: sin acción</span><span class="sxs-lookup"><span data-stu-id="bbca0-500">No action: No action</span></span></li>
<li><span data-ttu-id="bbca0-501">Bloquear: se bloqueó el recurso para que no se ejecutara</span><span class="sxs-lookup"><span data-stu-id="bbca0-501">Block: The resource was blocked from executing</span></span></li>
</ul><span data-ttu-id="bbca0-502">
</dt>
<dt>Estado de la acción: &lt; Descripción de &gt; acciones adicionales</dt>
<dt>Código de error: &lt; Código de error Código de resultado asociado con el estado de &gt; amenaza. Valores HRESULT estándar.</dt> 
<dt>Descripción del error: &lt; Descripción del error &gt; Descripción del error.</dt> 
<dt>Versión de firma: &lt; &gt;</dt>Versión de definición Versión del
<dt>motor: &lt; Antimalware Engine &gt; </dt> versión NOTA: siempre que Antivirus de Microsoft Defender, Microsoft Security Essentials, Herramienta de eliminación de software malintencionado o System Center Endpoint Protection detecte un malware, restaurará la siguiente configuración del sistema y los servicios que el malware podría haber cambiado:</span><span class="sxs-lookup"><span data-stu-id="bbca0-502">
</dt>
<dt>Action Status: &lt;Description of additional actions&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt> NOTE: Whenever Microsoft Defender Antivirus, Microsoft Security Essentials, Malicious Software Removal Tool, or System Center Endpoint Protection detects a malware, it will restore the following system settings and services that the malware might have changed:</span></span><ul>
<li><span data-ttu-id="bbca0-503">Configuración predeterminada de Internet Explorer o Microsoft Edge configuración</span><span class="sxs-lookup"><span data-stu-id="bbca0-503">Default Internet Explorer or Microsoft Edge setting</span></span></li>
<li><span data-ttu-id="bbca0-504">Configuración del control de acceso de usuario</span><span class="sxs-lookup"><span data-stu-id="bbca0-504">User Access Control settings</span></span></li>
<li><span data-ttu-id="bbca0-505">Configuración de Chrome</span><span class="sxs-lookup"><span data-stu-id="bbca0-505">Chrome settings</span></span></li>
<li><span data-ttu-id="bbca0-506">Datos de control de arranque</span><span class="sxs-lookup"><span data-stu-id="bbca0-506">Boot Control Data</span></span></li>
<li><span data-ttu-id="bbca0-507">Configuración del Registro regedit y administrador de tareas</span><span class="sxs-lookup"><span data-stu-id="bbca0-507">Regedit and Task Manager registry settings</span></span></li>
<li><span data-ttu-id="bbca0-508">Windows Actualización, servicio de transferencia inteligente en segundo plano y servicio de llamadas de procedimiento remoto</span><span class="sxs-lookup"><span data-stu-id="bbca0-508">Windows Update, Background Intelligent Transfer Service, and Remote Procedure Call service</span></span></li>
<li><span data-ttu-id="bbca0-509">Windows Archivos del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="bbca0-509">Windows Operating System files</span></span></li></ul>
<span data-ttu-id="bbca0-510">El contexto anterior se aplica a las siguientes versiones de cliente y servidor:</span><span class="sxs-lookup"><span data-stu-id="bbca0-510">The above context applies to the following client and server versions:</span></span>
<table>
<tr>
<th><span data-ttu-id="bbca0-511">Sistema operativo</span><span class="sxs-lookup"><span data-stu-id="bbca0-511">Operating system</span></span></th>
<th><span data-ttu-id="bbca0-512">Versión del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="bbca0-512">Operating system version</span></span></th>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-513">Sistema operativo cliente</span><span class="sxs-lookup"><span data-stu-id="bbca0-513">Client Operating System</span></span>
</td>
<td>
<span data-ttu-id="bbca0-514">Windows Vista (Service Pack 1 o Service Pack 2), Windows 7 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="bbca0-514">Windows Vista (Service Pack 1, or Service Pack 2), Windows 7 and later</span></span>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-515">Sistema operativo del servidor</span><span class="sxs-lookup"><span data-stu-id="bbca0-515">Server Operating System</span></span>
</td>
<td>
<span data-ttu-id="bbca0-516">Windows Server 2008, Windows Server 2008 R2, Windows Server 2012 y Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="bbca0-516">Windows Server 2008, Windows Server 2008 R2, Windows Server 2012, and Windows Server 2016</span></span>
</td>
</tr>
</table>
</dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-517">Acción del usuario:</span><span class="sxs-lookup"><span data-stu-id="bbca0-517">User action:</span></span>
</td>
<td >
<span data-ttu-id="bbca0-518">No es necesario realizar ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="bbca0-518">No action is necessary.</span></span> <span data-ttu-id="bbca0-519">Antivirus de Microsoft Defender o ha puesto en cuarentena una amenaza.</span><span class="sxs-lookup"><span data-stu-id="bbca0-519">Microsoft Defender Antivirus removed or quarantined a threat.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="bbca0-520">Identificador de evento: 1118</span><span class="sxs-lookup"><span data-stu-id="bbca0-520">Event ID: 1118</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="bbca0-521">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="bbca0-521">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="bbca0-522">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-522">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-523">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="bbca0-523">Message:</span></span>
</td>
<td ><span data-ttu-id="bbca0-524">
<b>La plataforma antimalware intentó realizar una acción para proteger el sistema de malware u otro software potencialmente no deseado, pero la acción falló. </b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-524">
<b>The antimalware platform attempted to perform an action to protect your system from malware or other potentially unwanted software, but the action failed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-525">Descripción:</span><span class="sxs-lookup"><span data-stu-id="bbca0-525">Description:</span></span>
</td>
<td >
<span data-ttu-id="bbca0-526">Antivirus de Microsoft Defender ha encontrado un error no crítico al tomar medidas en malware u otro software potencialmente no deseado.</span><span class="sxs-lookup"><span data-stu-id="bbca0-526">Microsoft Defender Antivirus has encountered a non-critical error when taking action on malware or other potentially unwanted software.</span></span><br/><span data-ttu-id="bbca0-527">Para obtener más información, vea los artículos siguientes: </span><span class="sxs-lookup"><span data-stu-id="bbca0-527">For more information, see the following:</span></span>
<dl><span data-ttu-id="bbca0-528">
<dt>Nombre: &lt; Id. &gt; de</dt>
<dt>nombre de &lt; amenaza: Gravedad del id. &gt; </dt>de 
<dt> amenaza: gravedad , por &lt; &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bbca0-528">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="bbca0-529">Bajo</span><span class="sxs-lookup"><span data-stu-id="bbca0-529">Low</span></span></li>
<li><span data-ttu-id="bbca0-530">Moderado</span><span class="sxs-lookup"><span data-stu-id="bbca0-530">Moderate</span></span></li>
<li><span data-ttu-id="bbca0-531">Alto</span><span class="sxs-lookup"><span data-stu-id="bbca0-531">High</span></span></li>
<li><span data-ttu-id="bbca0-532">Grave</span><span class="sxs-lookup"><span data-stu-id="bbca0-532">Severe</span></span></li>
</ul><span data-ttu-id="bbca0-533">
</dt>
<dt>Categoría: &lt; Descripción de &gt; categoría , por ejemplo, cualquier tipo de amenaza o malware.</dt> 
<dt>Ruta de acceso: &lt; Origen &gt; de detección</dt>de ruta de 
<dt> acceso de &lt; archivo: Origen de &gt; detección, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bbca0-533">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="bbca0-534">Desconocido</span><span class="sxs-lookup"><span data-stu-id="bbca0-534">Unknown</span></span></li>
<li><span data-ttu-id="bbca0-535">Equipo local</span><span class="sxs-lookup"><span data-stu-id="bbca0-535">Local computer</span></span></li>
<li><span data-ttu-id="bbca0-536">Recurso compartido de red</span><span class="sxs-lookup"><span data-stu-id="bbca0-536">Network share</span></span></li>
<li><span data-ttu-id="bbca0-537">Internet</span><span class="sxs-lookup"><span data-stu-id="bbca0-537">Internet</span></span></li>
<li><span data-ttu-id="bbca0-538">Tráfico entrante</span><span class="sxs-lookup"><span data-stu-id="bbca0-538">Incoming traffic</span></span></li>
<li><span data-ttu-id="bbca0-539">Tráfico saliente</span><span class="sxs-lookup"><span data-stu-id="bbca0-539">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="bbca0-540">
</dt>
<dt>Tipo de &lt; detección: Tipo de &gt; detección , por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bbca0-540">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="bbca0-541">Heurística</span><span class="sxs-lookup"><span data-stu-id="bbca0-541">Heuristics</span></span></li>
<li><span data-ttu-id="bbca0-542">Generic</span><span class="sxs-lookup"><span data-stu-id="bbca0-542">Generic</span></span></li>
<li><span data-ttu-id="bbca0-543">Concreto</span><span class="sxs-lookup"><span data-stu-id="bbca0-543">Concrete</span></span></li>
<li><span data-ttu-id="bbca0-544">Firma dinámica</span><span class="sxs-lookup"><span data-stu-id="bbca0-544">Dynamic signature</span></span></li>
</ul><span data-ttu-id="bbca0-545">
</dt>
<dt>Origen de &lt; detección: origen de &gt; detección por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bbca0-545">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="bbca0-546">Usuario: usuario iniciado</span><span class="sxs-lookup"><span data-stu-id="bbca0-546">User: user initiated</span></span></li>
<li><span data-ttu-id="bbca0-547">Sistema: sistema iniciado</span><span class="sxs-lookup"><span data-stu-id="bbca0-547">System: system initiated</span></span></li>
<li><span data-ttu-id="bbca0-548">En tiempo real: componente en tiempo real iniciado</span><span class="sxs-lookup"><span data-stu-id="bbca0-548">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="bbca0-549">IOAV: Descargas de IE y Outlook datos adjuntos de Express iniciados</span><span class="sxs-lookup"><span data-stu-id="bbca0-549">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="bbca0-550">NIS: sistema de inspección de red</span><span class="sxs-lookup"><span data-stu-id="bbca0-550">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="bbca0-551">IEPROTECT: IE - IExtensionValidation; esto protege contra controles de páginas web malintencionadas</span><span class="sxs-lookup"><span data-stu-id="bbca0-551">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="bbca0-552">Antimalware de inicio anticipado (ELAM).</span><span class="sxs-lookup"><span data-stu-id="bbca0-552">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="bbca0-553">Esto incluye malware detectado por la secuencia de arranque</span><span class="sxs-lookup"><span data-stu-id="bbca0-553">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="bbca0-554">Atestación remota</span><span class="sxs-lookup"><span data-stu-id="bbca0-554">Remote attestation</span></span></li>
</ul><span data-ttu-id="bbca0-555">Interfaz de examen antimalware (AMSI).</span><span class="sxs-lookup"><span data-stu-id="bbca0-555">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="bbca0-556">Se usa principalmente para proteger scripts (PS, VBS), aunque también pueden invocarse por terceros.</span><span class="sxs-lookup"><span data-stu-id="bbca0-556">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="bbca0-557">Usuario de </dt> 
<dt>UAC: Dominio &lt; &gt; \& lt; Nombre &gt; </dt>
<dt>del proceso de usuario: Proceso en la &lt; acción &gt; pid:</dt>Acción , por 
<dt> &lt; &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bbca0-557">UAC</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Action: &lt;Action&gt;, for example:</span></span><ul>
<li><span data-ttu-id="bbca0-558">Clean: el recurso se ha limpiado</span><span class="sxs-lookup"><span data-stu-id="bbca0-558">Clean: The resource was cleaned</span></span></li>
<li><span data-ttu-id="bbca0-559">Cuarentena: el recurso se ha puesto en cuarentena</span><span class="sxs-lookup"><span data-stu-id="bbca0-559">Quarantine: The resource was quarantined</span></span></li>
<li><span data-ttu-id="bbca0-560">Quitar: se eliminó el recurso</span><span class="sxs-lookup"><span data-stu-id="bbca0-560">Remove: The resource was deleted</span></span></li>
<li><span data-ttu-id="bbca0-561">Permitir: se permitió que el recurso se ejecutara o existiera</span><span class="sxs-lookup"><span data-stu-id="bbca0-561">Allow: The resource was allowed to execute/exist</span></span></li>
<li><span data-ttu-id="bbca0-562">Definido por el usuario: acción definida por el usuario que normalmente es una de esta lista de acciones que el usuario ha especificado</span><span class="sxs-lookup"><span data-stu-id="bbca0-562">User defined: User-defined action that is normally one from this list of actions that the user has specified</span></span></li>
<li><span data-ttu-id="bbca0-563">Sin acción: sin acción</span><span class="sxs-lookup"><span data-stu-id="bbca0-563">No action: No action</span></span></li>
<li><span data-ttu-id="bbca0-564">Bloquear: se bloqueó el recurso para que no se ejecutara</span><span class="sxs-lookup"><span data-stu-id="bbca0-564">Block: The resource was blocked from executing</span></span></li>
</ul><span data-ttu-id="bbca0-565">
</dt>
<dt>Estado de la acción: &lt; Descripción de &gt; acciones adicionales</dt>
<dt>Código de error: &lt; Código de error Código de resultado asociado con el estado de &gt; amenaza. Valores HRESULT estándar.</dt> 
<dt>Descripción del error: &lt; Descripción del error &gt; Descripción del error.</dt> 
<dt>Versión de firma: &lt; Versión &gt; de definición</dt>
<dt>Versión del motor: &lt; Antimalware Engine versión &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-565">
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
<span data-ttu-id="bbca0-566">Acción del usuario:</span><span class="sxs-lookup"><span data-stu-id="bbca0-566">User action:</span></span>
</td>
<td >
<span data-ttu-id="bbca0-567">No es necesario realizar ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="bbca0-567">No action is necessary.</span></span> <span data-ttu-id="bbca0-568">Antivirus de Microsoft Defender no pudo completar una tarea relacionada con la corrección de malware.</span><span class="sxs-lookup"><span data-stu-id="bbca0-568">Microsoft Defender Antivirus failed to complete a task related to the malware remediation.</span></span> <span data-ttu-id="bbca0-569">No se trata de un error crítico.</span><span class="sxs-lookup"><span data-stu-id="bbca0-569">This is not a critical failure.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="bbca0-570">Identificador de evento: 1119</span><span class="sxs-lookup"><span data-stu-id="bbca0-570">Event ID: 1119</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="bbca0-571">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="bbca0-571">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="bbca0-572">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_CRITICALLY_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-572">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_CRITICALLY_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-573">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="bbca0-573">Message:</span></span>
</td>
<td ><span data-ttu-id="bbca0-574">
<b>La plataforma antimalware encontró un error crítico al intentar tomar medidas en malware u otro software potencialmente no deseado. Hay más detalles en el mensaje de evento.</b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-574">
<b>The antimalware platform encountered a critical error when trying to take action on malware or other potentially unwanted software. There are more details in the event message.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-575">Descripción:</span><span class="sxs-lookup"><span data-stu-id="bbca0-575">Description:</span></span>
</td>
<td >
<span data-ttu-id="bbca0-576">Antivirus de Microsoft Defender ha encontrado un error crítico al tomar medidas en malware u otro software potencialmente no deseado.</span><span class="sxs-lookup"><span data-stu-id="bbca0-576">Microsoft Defender Antivirus has encountered a critical error when taking action on malware or other potentially unwanted software.</span></span><br/><span data-ttu-id="bbca0-577">Para obtener más información, vea los artículos siguientes: </span><span class="sxs-lookup"><span data-stu-id="bbca0-577">For more information, see the following:</span></span>
<dl><span data-ttu-id="bbca0-578">
<dt>Nombre: &lt; Id. &gt; de</dt>
<dt>nombre de &lt; amenaza: Gravedad del id. &gt; </dt>de 
<dt> amenaza: gravedad , por &lt; &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bbca0-578">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="bbca0-579">Bajo</span><span class="sxs-lookup"><span data-stu-id="bbca0-579">Low</span></span></li>
<li><span data-ttu-id="bbca0-580">Moderado</span><span class="sxs-lookup"><span data-stu-id="bbca0-580">Moderate</span></span></li>
<li><span data-ttu-id="bbca0-581">Alto</span><span class="sxs-lookup"><span data-stu-id="bbca0-581">High</span></span></li>
<li><span data-ttu-id="bbca0-582">Grave</span><span class="sxs-lookup"><span data-stu-id="bbca0-582">Severe</span></span></li>
</ul><span data-ttu-id="bbca0-583">
</dt>
<dt>Categoría: &lt; Descripción de &gt; categoría , por ejemplo, cualquier tipo de amenaza o malware.</dt> 
<dt>Ruta de acceso: &lt; Origen &gt; de detección</dt>de ruta de 
<dt> acceso de &lt; archivo: Origen de &gt; detección, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bbca0-583">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="bbca0-584">Desconocido</span><span class="sxs-lookup"><span data-stu-id="bbca0-584">Unknown</span></span></li>
<li><span data-ttu-id="bbca0-585">Equipo local</span><span class="sxs-lookup"><span data-stu-id="bbca0-585">Local computer</span></span></li>
<li><span data-ttu-id="bbca0-586">Recurso compartido de red</span><span class="sxs-lookup"><span data-stu-id="bbca0-586">Network share</span></span></li>
<li><span data-ttu-id="bbca0-587">Internet</span><span class="sxs-lookup"><span data-stu-id="bbca0-587">Internet</span></span></li>
<li><span data-ttu-id="bbca0-588">Tráfico entrante</span><span class="sxs-lookup"><span data-stu-id="bbca0-588">Incoming traffic</span></span></li>
<li><span data-ttu-id="bbca0-589">Tráfico saliente</span><span class="sxs-lookup"><span data-stu-id="bbca0-589">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="bbca0-590">
</dt>
<dt>Tipo de &lt; detección: Tipo de &gt; detección , por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bbca0-590">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="bbca0-591">Heurística</span><span class="sxs-lookup"><span data-stu-id="bbca0-591">Heuristics</span></span></li>
<li><span data-ttu-id="bbca0-592">Generic</span><span class="sxs-lookup"><span data-stu-id="bbca0-592">Generic</span></span></li>
<li><span data-ttu-id="bbca0-593">Concreto</span><span class="sxs-lookup"><span data-stu-id="bbca0-593">Concrete</span></span></li>
<li><span data-ttu-id="bbca0-594">Firma dinámica</span><span class="sxs-lookup"><span data-stu-id="bbca0-594">Dynamic signature</span></span></li>
</ul><span data-ttu-id="bbca0-595">
</dt>
<dt>Origen de &lt; detección: origen de &gt; detección por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bbca0-595">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="bbca0-596">Usuario: usuario iniciado</span><span class="sxs-lookup"><span data-stu-id="bbca0-596">User: user initiated</span></span></li>
<li><span data-ttu-id="bbca0-597">Sistema: sistema iniciado</span><span class="sxs-lookup"><span data-stu-id="bbca0-597">System: system initiated</span></span></li>
<li><span data-ttu-id="bbca0-598">En tiempo real: componente en tiempo real iniciado</span><span class="sxs-lookup"><span data-stu-id="bbca0-598">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="bbca0-599">IOAV: Descargas de IE y Outlook datos adjuntos de Express iniciados</span><span class="sxs-lookup"><span data-stu-id="bbca0-599">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="bbca0-600">NIS: sistema de inspección de red</span><span class="sxs-lookup"><span data-stu-id="bbca0-600">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="bbca0-601">IEPROTECT: IE - IExtensionValidation; esto protege contra controles de páginas web malintencionadas</span><span class="sxs-lookup"><span data-stu-id="bbca0-601">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="bbca0-602">Antimalware de inicio anticipado (ELAM).</span><span class="sxs-lookup"><span data-stu-id="bbca0-602">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="bbca0-603">Esto incluye malware detectado por la secuencia de arranque</span><span class="sxs-lookup"><span data-stu-id="bbca0-603">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="bbca0-604">Atestación remota</span><span class="sxs-lookup"><span data-stu-id="bbca0-604">Remote attestation</span></span></li>
</ul><span data-ttu-id="bbca0-605">Interfaz de examen antimalware (AMSI).</span><span class="sxs-lookup"><span data-stu-id="bbca0-605">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="bbca0-606">Se usa principalmente para proteger scripts (PS, VBS), aunque también pueden invocarse por terceros.</span><span class="sxs-lookup"><span data-stu-id="bbca0-606">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="bbca0-607">Usuario de </dt> 
<dt>UAC: Dominio &lt; &gt; \& lt; Nombre &gt; </dt>
<dt>del proceso de usuario: Proceso en la &lt; acción &gt; pid:</dt>Acción , por 
<dt> &lt; &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bbca0-607">UAC</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Action: &lt;Action&gt;, for example:</span></span><ul>
<li><span data-ttu-id="bbca0-608">Clean: el recurso se ha limpiado</span><span class="sxs-lookup"><span data-stu-id="bbca0-608">Clean: The resource was cleaned</span></span></li>
<li><span data-ttu-id="bbca0-609">Cuarentena: el recurso se ha puesto en cuarentena</span><span class="sxs-lookup"><span data-stu-id="bbca0-609">Quarantine: The resource was quarantined</span></span></li>
<li><span data-ttu-id="bbca0-610">Quitar: se eliminó el recurso</span><span class="sxs-lookup"><span data-stu-id="bbca0-610">Remove: The resource was deleted</span></span></li>
<li><span data-ttu-id="bbca0-611">Permitir: se permitió que el recurso se ejecutara o existiera</span><span class="sxs-lookup"><span data-stu-id="bbca0-611">Allow: The resource was allowed to execute/exist</span></span></li>
<li><span data-ttu-id="bbca0-612">Definido por el usuario: acción definida por el usuario que normalmente es una de esta lista de acciones que el usuario ha especificado</span><span class="sxs-lookup"><span data-stu-id="bbca0-612">User defined: User-defined action that is normally one from this list of actions that the user has specified</span></span></li>
<li><span data-ttu-id="bbca0-613">Sin acción: sin acción</span><span class="sxs-lookup"><span data-stu-id="bbca0-613">No action: No action</span></span></li>
<li><span data-ttu-id="bbca0-614">Bloquear: se bloqueó el recurso para que no se ejecutara</span><span class="sxs-lookup"><span data-stu-id="bbca0-614">Block: The resource was blocked from executing</span></span></li>
</ul><span data-ttu-id="bbca0-615">
</dt>
<dt>Estado de la acción: &lt; Descripción de &gt; acciones adicionales</dt>
<dt>Código de error: &lt; Código de error Código de resultado asociado con el estado de &gt; amenaza. Valores HRESULT estándar.</dt> 
<dt>Descripción del error: &lt; Descripción del error &gt; Descripción del error.</dt> 
<dt>Versión de firma: &lt; Versión &gt; de definición</dt>
<dt>Versión del motor: &lt; Antimalware Engine versión &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-615">
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
<span data-ttu-id="bbca0-616">Acción del usuario:</span><span class="sxs-lookup"><span data-stu-id="bbca0-616">User action:</span></span>
</td>
<td >
<span data-ttu-id="bbca0-617">El Antivirus de Microsoft Defender encontró este error debido a problemas críticos.</span><span class="sxs-lookup"><span data-stu-id="bbca0-617">The Microsoft Defender Antivirus client encountered this error due to critical issues.</span></span> <span data-ttu-id="bbca0-618">Es posible que el extremo no esté protegido.</span><span class="sxs-lookup"><span data-stu-id="bbca0-618">The endpoint might not be protected.</span></span> <span data-ttu-id="bbca0-619">Revise la descripción del error y, a continuación, siga los <b>pasos de acción de usuario</b> pertinentes a continuación.</span><span class="sxs-lookup"><span data-stu-id="bbca0-619">Review the error description then follow the relevant <b>User action</b> steps below.</span></span>
<table>
<tr>
<th><span data-ttu-id="bbca0-620">Acción</span><span class="sxs-lookup"><span data-stu-id="bbca0-620">Action</span></span></th>
<th><span data-ttu-id="bbca0-621">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="bbca0-621">User action</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="bbca0-622">
<b>Quitar</b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-622">
<b>Remove</b>
</span></span></td>
<td>
<span data-ttu-id="bbca0-623">Actualice las definiciones y compruebe que la eliminación se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="bbca0-623">Update the definitions then verify that the removal was successful.</span></span>
</td>
</tr>
<tr>
<td><span data-ttu-id="bbca0-624">
<b>Limpiar</b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-624">
<b>Clean</b>
</span></span></td>
<td>
<span data-ttu-id="bbca0-625">Actualice las definiciones y compruebe que la corrección se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="bbca0-625">Update the definitions then verify that the remediation was successful.</span></span>
</td>
</tr>
<tr>
<td><span data-ttu-id="bbca0-626">
<b>Cuarentena</b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-626">
<b>Quarantine</b>
</span></span></td>
<td>
<span data-ttu-id="bbca0-627">Actualice las definiciones y compruebe que el usuario tiene permiso para acceder a los recursos necesarios.</span><span class="sxs-lookup"><span data-stu-id="bbca0-627">Update the definitions and verify that the user has permission to access the necessary resources.</span></span>
</td>
</tr>
<tr>
<td><span data-ttu-id="bbca0-628">
<b>Permitir</b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-628">
<b>Allow</b>
</span></span></td>
<td>
<span data-ttu-id="bbca0-629">Compruebe que el usuario tiene permiso para obtener acceso a los recursos necesarios.</span><span class="sxs-lookup"><span data-stu-id="bbca0-629">Verify that the user has permission to access the necessary resources.</span></span>
</td>
</tr>
</table>

<span data-ttu-id="bbca0-630">Si este evento persiste:</span><span class="sxs-lookup"><span data-stu-id="bbca0-630">If this event persists:</span></span><ol>
<li><span data-ttu-id="bbca0-631">Vuelva a ejecutar el examen.</span><span class="sxs-lookup"><span data-stu-id="bbca0-631">Run the scan again.</span></span></li>
<li><span data-ttu-id="bbca0-632">Si se produce un error de la misma manera, vaya <b></b> al sitio de soporte técnico de <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft</a>, escriba el número de error en el cuadro Buscar para buscar el código de error.</span><span class="sxs-lookup"><span data-stu-id="bbca0-632">If it fails in the same way, go to the <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft Support site</a>, enter the error number in the <b>Search</b> box to look for the error code.</span></span></li>
<li><span data-ttu-id="bbca0-633">Contactar al <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Soporte técnico de Microsoft</a>.</span><span class="sxs-lookup"><span data-stu-id="bbca0-633">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="bbca0-634">Identificador de evento: 1120</span><span class="sxs-lookup"><span data-stu-id="bbca0-634">Event ID: 1120</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="bbca0-635">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="bbca0-635">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="bbca0-636">
<b>MALWAREPROTECTION_THREAT_HASH</b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-636">
<b>MALWAREPROTECTION_THREAT_HASH</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-637">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="bbca0-637">Message:</span></span>
</td>
<td ><span data-ttu-id="bbca0-638">
<b>Antivirus de Microsoft Defender ha deducido los hashes de un recurso de amenaza.</b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-638">
<b>Microsoft Defender Antivirus has deduced the hashes for a threat resource.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-639">Descripción:</span><span class="sxs-lookup"><span data-stu-id="bbca0-639">Description:</span></span>
</td>
<td >
<span data-ttu-id="bbca0-640">Antivirus de Microsoft Defender cliente está en funcionamiento en un estado correcto.</span><span class="sxs-lookup"><span data-stu-id="bbca0-640">Microsoft Defender Antivirus client is up and running in a healthy state.</span></span>
<dl><span data-ttu-id="bbca0-641">
<dt>Versión actual de la plataforma: &lt; Ruta de &gt; acceso de</dt>recurso de amenaza de la
<dt> &lt; &gt; versión</dt>actual de la plataforma:
<dt>hashes de ruta: &lt; hashes &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-641">
<dt>Current Platform Version: &lt;Current platform version&gt;</dt>
<dt>Threat Resource Path: &lt;Path&gt;</dt>
<dt>Hashes: &lt;Hashes&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td></td>
<td >
<div class="alert"><span data-ttu-id="bbca0-642"><b>Nota: Este evento solo se registrará si se establece la siguiente directiva: <b>ThreatFileHashLogging sin signo</b>.</span><span class="sxs-lookup"><span data-stu-id="bbca0-642"><b>Note: This event will only be logged if the following policy is set: <b>ThreatFileHashLogging     unsigned</b>.</span></span></div>
<div> </div>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="bbca0-643">Identificador de evento: 1150</span><span class="sxs-lookup"><span data-stu-id="bbca0-643">Event ID: 1150</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="bbca0-644">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="bbca0-644">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="bbca0-645">
<b>MALWAREPROTECTION_SERVICE_HEALTHY</b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-645">
<b>MALWAREPROTECTION_SERVICE_HEALTHY</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-646">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="bbca0-646">Message:</span></span>
</td>
<td ><span data-ttu-id="bbca0-647">
<b>Si la plataforma antimalware notifica el estado a una plataforma de supervisión, este evento indica que la plataforma antimalware se está ejecutando y en un estado correcto. </b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-647">
<b>If your antimalware platform reports status to a monitoring platform, this event indicates that the antimalware platform is running and in a healthy state. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-648">Descripción:</span><span class="sxs-lookup"><span data-stu-id="bbca0-648">Description:</span></span>
</td>
<td >
<span data-ttu-id="bbca0-649">Antivirus de Microsoft Defender cliente está en funcionamiento en un estado correcto.</span><span class="sxs-lookup"><span data-stu-id="bbca0-649">Microsoft Defender Antivirus client is up and running in a healthy state.</span></span>
<dl><span data-ttu-id="bbca0-650">
<dt>Versión de la plataforma: &lt; Versión de &gt; la plataforma actual</dt>Versión de firma: Versión del motor
<dt> &lt; de &gt; </dt>la versión de definición:
<dt>Antimalware Engine &lt; versión &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-650">
<dt>Platform Version: &lt;Current platform version&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-651">Acción del usuario:</span><span class="sxs-lookup"><span data-stu-id="bbca0-651">User action:</span></span>
</td>
<td >
<span data-ttu-id="bbca0-652">No es necesario realizar ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="bbca0-652">No action is necessary.</span></span> <span data-ttu-id="bbca0-653">El Antivirus de Microsoft Defender está en buen estado.</span><span class="sxs-lookup"><span data-stu-id="bbca0-653">The Microsoft Defender Antivirus client is in a healthy state.</span></span> <span data-ttu-id="bbca0-654">Este evento se notifica cada hora.</span><span class="sxs-lookup"><span data-stu-id="bbca0-654">This event is reported on an hourly basis.</span></span>
</td>
</tr>

<tr>
<th colspan="2"><span data-ttu-id="bbca0-655">Identificador de evento: 1151</span><span class="sxs-lookup"><span data-stu-id="bbca0-655">Event ID: 1151</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="bbca0-656">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="bbca0-656">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="bbca0-657">
<b>MALWAREPROTECTION_SERVICE_HEALTH_REPORT</b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-657">
<b>MALWAREPROTECTION_SERVICE_HEALTH_REPORT</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-658">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="bbca0-658">Message:</span></span>
</td>
<td ><span data-ttu-id="bbca0-659">
<b>Endpoint Protection de estado del cliente (hora UTC)</b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-659">
<b>Endpoint Protection client health report (time in UTC) </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-660">Descripción:</span><span class="sxs-lookup"><span data-stu-id="bbca0-660">Description:</span></span>
</td>
<td >
<span data-ttu-id="bbca0-661">Informe de estado del cliente antivirus.</span><span class="sxs-lookup"><span data-stu-id="bbca0-661">Antivirus client health report.</span></span>
<dl><span data-ttu-id="bbca0-662">
<dt>Versión de la plataforma: &lt; &gt;</dt>Versión actual del motor de la
<dt>plataforma: &lt; &gt; </dt>versión Antimalware Engine Versión del motor de inspección en tiempo real de
<dt> &lt; &gt; red:</dt>Versión de firma del motor de inspección en tiempo real de red
<dt>Versión &lt; &gt; </dt>de firma antivirus Versión de firma
<dt>antispyware: Versión de firma &lt; antispyware &gt; </dt>Versión de firma de inspección en tiempo
<dt>real: &lt; &gt; </dt>Estado RTP de la firma de inspección en tiempo real de red: Estado de OA de protección en tiempo real (habilitado o
<dt> &lt; &gt; deshabilitado):</dt>Estado de IOAV de estado de acceso (habilitado o
<dt> &lt; &gt; deshabilitado):</dt>I Descargas de Outlook Express Attachments state
<dt> &lt; &gt; (Enabled or Disabled)</dt>Estado DE LA BM: Estado de supervisión del comportamiento (habilitado o
<dt> &lt; &gt; deshabilitado)</dt>Antigüedad de firma
<dt>antivirus: &lt; &gt; </dt>Antigüedad de firma antispyware antivirus (en días) Antigüedad de firma
<dt> &lt; antispyware &gt; (en días)</dt>Última antigüedad del examen rápido: Última antigüedad del examen rápido
<dt> &lt; &gt; (en días)</dt>Última antigüedad completa del examen
<dt> &lt; &gt; (en días)</dt>Tiempo de creación de firmas
<dt>antivirus: ? &lt; Hora de &gt; creación de firmas antivirus</dt>Tiempo de
<dt>creación de firmas antispyware: ? &lt; Hora de creación &gt; de firmas antispyware</dt>
<dt>Última hora de inicio del examen rápido: ? &lt; Última hora de &gt; inicio del examen rápido</dt>Última hora de finalización del examen
<dt>rápido: ? &lt; Última &gt; hora</dt>de finalización del examen rápido Último origen de examen rápido: Último origen de examen rápido (0 = el examen no se&#39;se ha ejecutado, 1 = iniciado por el
<dt> &lt; &gt; usuario, 2 =</dt>iniciado por el sistema) Última hora de inicio del examen
<dt>completo: ? &lt; Última hora de &gt; inicio del examen completo</dt>Última hora de finalización del examen
<dt>completo: ? &lt; Última &gt; hora</dt>de finalización del examen completo Último origen de examen completo: Último origen de examen completo (0 = el examen no se&#39;no se ha ejecutado, 1 = iniciado por el
<dt> &lt; &gt; usuario, 2 =</dt>iniciado por el sistema) Estado del producto: Para la solución de problemas interna 
<dt></span><span class="sxs-lookup"><span data-stu-id="bbca0-662">
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

<tr><span data-ttu-id="bbca0-663">
<th colspan="2">Identificador de evento: 2000</span><span class="sxs-lookup"><span data-stu-id="bbca0-663">
<th colspan="2">Event ID: 2000</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="bbca0-664">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="bbca0-664">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="bbca0-665">
<b>MALWAREPROTECTION_SIGNATURE_UPDATED </b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-665">
<b>MALWAREPROTECTION_SIGNATURE_UPDATED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-666">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="bbca0-666">Message:</span></span>
</td>
<td ><span data-ttu-id="bbca0-667">
<b>Las definiciones de antimalware se actualizaron correctamente. </b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-667">
<b>The antimalware definitions updated successfully. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-668">Descripción:</span><span class="sxs-lookup"><span data-stu-id="bbca0-668">Description:</span></span>
</td>
<td >
<span data-ttu-id="bbca0-669">Se ha actualizado la versión de firma del antivirus.</span><span class="sxs-lookup"><span data-stu-id="bbca0-669">Antivirus signature version has been updated.</span></span>
<dl><span data-ttu-id="bbca0-670">
<dt>Versión de firma actual: &lt; Versión de &gt; firma actual</dt>
<dt>Versión de firma anterior: Versión de firma &lt; anterior &gt; </dt>Tipo de 
<dt> firma: Tipo de firma , por &lt; &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bbca0-670">
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Previous Signature Version: &lt;Previous signature version&gt;</dt>
<dt>Signature Type: &lt;Signature type&gt;, for example:</span></span> <ul>
<li><span data-ttu-id="bbca0-671">Antivirus</span><span class="sxs-lookup"><span data-stu-id="bbca0-671">Antivirus</span></span></li>
<li><span data-ttu-id="bbca0-672">Antispyware</span><span class="sxs-lookup"><span data-stu-id="bbca0-672">Antispyware</span></span></li>
<li><span data-ttu-id="bbca0-673">Antimalware</span><span class="sxs-lookup"><span data-stu-id="bbca0-673">Antimalware</span></span></li>
<li><span data-ttu-id="bbca0-674">Sistema de inspección de red</span><span class="sxs-lookup"><span data-stu-id="bbca0-674">Network Inspection System</span></span></li>
</ul><span data-ttu-id="bbca0-675">
</dt>
<dt>Tipo de actualización: &lt; Tipo de &gt; actualización , Completo o Delta.</dt> 
<dt>Usuario: &lt; Dominio &gt; \& lt; Versión &gt; </dt>
<dt>del motor actual del usuario: versión actual del &lt; &gt; motor</dt>Versión anterior del
<dt>motor: Versión anterior del &lt; motor &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-675">
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
<span data-ttu-id="bbca0-676">Acción del usuario:</span><span class="sxs-lookup"><span data-stu-id="bbca0-676">User action:</span></span>
</td>
<td >
<span data-ttu-id="bbca0-677">No es necesario realizar ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="bbca0-677">No action is necessary.</span></span> <span data-ttu-id="bbca0-678">El Antivirus de Microsoft Defender está en buen estado.</span><span class="sxs-lookup"><span data-stu-id="bbca0-678">The Microsoft Defender Antivirus client is in a healthy state.</span></span> <span data-ttu-id="bbca0-679">Este evento se notifica cuando las firmas se actualizan correctamente.</span><span class="sxs-lookup"><span data-stu-id="bbca0-679">This event is reported when signatures are successfully updated.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="bbca0-680">Identificador de evento: 2001</span><span class="sxs-lookup"><span data-stu-id="bbca0-680">Event ID: 2001</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="bbca0-681">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="bbca0-681">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="bbca0-682">
<b>MALWAREPROTECTION_SIGNATURE_UPDATE_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-682">
<b>MALWAREPROTECTION_SIGNATURE_UPDATE_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-683">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="bbca0-683">Message:</span></span>
</td>
<td ><span data-ttu-id="bbca0-684">
<b>Error en la actualización de inteligencia de seguridad. </b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-684">
<b>The security intelligence update failed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-685">Descripción:</span><span class="sxs-lookup"><span data-stu-id="bbca0-685">Description:</span></span>
</td>
<td >
<span data-ttu-id="bbca0-686">Antivirus de Microsoft Defender ha encontrado un error al intentar actualizar firmas.</span><span class="sxs-lookup"><span data-stu-id="bbca0-686">Microsoft Defender Antivirus has encountered an error trying to update signatures.</span></span>
<dl><span data-ttu-id="bbca0-687">
<dt>Nueva versión de inteligencia de seguridad: &lt; Nuevo número &gt; de versión</dt>
<dt>Versión de inteligencia de seguridad anterior: Versión &lt; &gt; anterior</dt>Update 
<dt> Source: Update source , por &lt; &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bbca0-687">
<dt>New security intelligence version: &lt;New version number&gt;</dt>
<dt>Previous security intelligence version: &lt;Previous version&gt;</dt>
<dt>Update Source: &lt;Update source&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="bbca0-688">Carpeta de actualización de inteligencia de seguridad</span><span class="sxs-lookup"><span data-stu-id="bbca0-688">Security intelligence update folder</span></span></li>
<li><span data-ttu-id="bbca0-689">Servidor de actualización de inteligencia de seguridad interna</span><span class="sxs-lookup"><span data-stu-id="bbca0-689">Internal security intelligence update server</span></span></li>
<li><span data-ttu-id="bbca0-690">Microsoft Update Server</span><span class="sxs-lookup"><span data-stu-id="bbca0-690">Microsoft Update Server</span></span></li>
<li><span data-ttu-id="bbca0-691">Compartir archivos</span><span class="sxs-lookup"><span data-stu-id="bbca0-691">File share</span></span></li>
<li><span data-ttu-id="bbca0-692">Centro de protección contra malware de Microsoft (MMPC)</span><span class="sxs-lookup"><span data-stu-id="bbca0-692">Microsoft Malware Protection Center (MMPC)</span></span></li>
</ul><span data-ttu-id="bbca0-693">
</dt>
<dt>Update Stage: &lt; Update stage , por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bbca0-693">
</dt>
<dt>Update Stage: &lt;Update stage&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="bbca0-694">Búsqueda</span><span class="sxs-lookup"><span data-stu-id="bbca0-694">Search</span></span></li>
<li><span data-ttu-id="bbca0-695">Descargar</span><span class="sxs-lookup"><span data-stu-id="bbca0-695">Download</span></span></li>
<li><span data-ttu-id="bbca0-696">Instalar</span><span class="sxs-lookup"><span data-stu-id="bbca0-696">Install</span></span></li>
</ul><span data-ttu-id="bbca0-697">
</dt>Ruta de acceso de origen: nombre del recurso compartido de archivos para convención de nomenclatura universal (UNC), nombre del servidor 
<dt>para Windows Server Update Services (WSUS)/Microsoft Update/ADL.</dt> 
<dt> Tipo de firma: &lt; Tipo de firma , por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bbca0-697">
</dt>
<dt>Source Path: File share name for Universal Naming Convention (UNC), server name for Windows Server Update Services (WSUS)/Microsoft Update/ADL.</dt>
<dt>Signature Type: &lt;Signature type&gt;, for example:</span></span> <ul>
<li><span data-ttu-id="bbca0-698">Antivirus</span><span class="sxs-lookup"><span data-stu-id="bbca0-698">Antivirus</span></span></li>
<li><span data-ttu-id="bbca0-699">Antispyware</span><span class="sxs-lookup"><span data-stu-id="bbca0-699">Antispyware</span></span></li>
<li><span data-ttu-id="bbca0-700">Antimalware</span><span class="sxs-lookup"><span data-stu-id="bbca0-700">Antimalware</span></span></li>
<li><span data-ttu-id="bbca0-701">Sistema de inspección de red</span><span class="sxs-lookup"><span data-stu-id="bbca0-701">Network Inspection System</span></span></li>
</ul><span data-ttu-id="bbca0-702">
</dt>
<dt>Tipo de actualización: &lt; Tipo de &gt; actualización , Completo o Delta.</dt> 
<dt>Usuario: &lt; Dominio &gt; \& lt; Versión &gt; </dt>
<dt>actual del motor del usuario: &lt; &gt; Versión</dt>actual del motor Versión anterior del motor: Versión
<dt> &lt; anterior &gt; </dt>del motor Código de error: Código de error Código de
<dt>resultado asociado con el estado de la &lt; &gt; amenaza. Valores HRESULT estándar.</dt> 
<dt>Descripción del error: &lt; Descripción del error &gt; Descripción del error.</dt>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-702">
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
<span data-ttu-id="bbca0-703">Acción del usuario:</span><span class="sxs-lookup"><span data-stu-id="bbca0-703">User action:</span></span>
</td>
<td >
<span data-ttu-id="bbca0-704">Este error se produce cuando hay un problema al actualizar definiciones.</span><span class="sxs-lookup"><span data-stu-id="bbca0-704">This error occurs when there is a problem updating definitions.</span></span>
<span data-ttu-id="bbca0-705">Para solucionar este evento:</span><span class="sxs-lookup"><span data-stu-id="bbca0-705">To troubleshoot this event:</span></span>
<ol>
<li><span data-ttu-id="bbca0-706"><a href="manage-updates-baselines-microsoft-defender-antivirus.md" data-raw-source="[Update definitions](manage-updates-baselines-microsoft-defender-antivirus.md)">Actualice las definiciones</a> y fuerza un nuevo análisis directamente en el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="bbca0-706"><a href="manage-updates-baselines-microsoft-defender-antivirus.md" data-raw-source="[Update definitions](manage-updates-baselines-microsoft-defender-antivirus.md)">Update definitions</a> and force a rescan directly on the endpoint.</span></span></li>
<li><span data-ttu-id="bbca0-707">Revisa las entradas del archivo %Windir%\WindowsUpdate.log para obtener más información sobre este error.</span><span class="sxs-lookup"><span data-stu-id="bbca0-707">Review the entries in the %Windir%\WindowsUpdate.log file for more information about this error.</span></span></li>
<li><span data-ttu-id="bbca0-708">Contactar al <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Soporte técnico de Microsoft</a>.</span><span class="sxs-lookup"><span data-stu-id="bbca0-708">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="bbca0-709">Identificador de evento: 2002</span><span class="sxs-lookup"><span data-stu-id="bbca0-709">Event ID: 2002</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="bbca0-710">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="bbca0-710">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="bbca0-711">
<b>MALWAREPROTECTION_ENGINE_UPDATED</b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-711">
<b>MALWAREPROTECTION_ENGINE_UPDATED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-712">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="bbca0-712">Message:</span></span>
</td>
<td ><span data-ttu-id="bbca0-713">
<b>El motor de antimalware se actualizó correctamente. </b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-713">
<b>The antimalware engine updated successfully. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-714">Descripción:</span><span class="sxs-lookup"><span data-stu-id="bbca0-714">Description:</span></span>
</td>
<td >
<span data-ttu-id="bbca0-715">Antivirus de Microsoft Defender versión del motor se ha actualizado.</span><span class="sxs-lookup"><span data-stu-id="bbca0-715">Microsoft Defender Antivirus engine version has been updated.</span></span>
<dl><span data-ttu-id="bbca0-716">
<dt>Versión actual del motor: &lt; Versión actual &gt; del motor</dt>
<dt>Versión anterior del motor: &lt; &gt; Versión anterior</dt>del motor Tipo de motor: Tipo de motor , motor antimalware o motor del sistema de inspección de
<dt> &lt; &gt; red.</dt> 
<dt>Usuario: &lt; Dominio &gt; \& lt; Usuario &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-716">
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Previous Engine Version: &lt;Previous engine version&gt;</dt>
<dt>Engine Type: &lt;Engine type&gt;, either antimalware engine or Network Inspection System engine.</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-717">Acción del usuario:</span><span class="sxs-lookup"><span data-stu-id="bbca0-717">User action:</span></span>
</td>
<td >
<span data-ttu-id="bbca0-718">No es necesario realizar ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="bbca0-718">No action is necessary.</span></span> <span data-ttu-id="bbca0-719">El Antivirus de Microsoft Defender está en buen estado.</span><span class="sxs-lookup"><span data-stu-id="bbca0-719">The Microsoft Defender Antivirus client is in a healthy state.</span></span> <span data-ttu-id="bbca0-720">Este evento se notifica cuando el motor de antimalware se actualiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="bbca0-720">This event is reported when the antimalware engine is successfully updated.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="bbca0-721">Identificador de evento: 2003</span><span class="sxs-lookup"><span data-stu-id="bbca0-721">Event ID: 2003</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="bbca0-722">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="bbca0-722">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="bbca0-723">
<b>MALWAREPROTECTION_ENGINE_UPDATE_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-723">
<b>MALWAREPROTECTION_ENGINE_UPDATE_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-724">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="bbca0-724">Message:</span></span>
</td>
<td ><span data-ttu-id="bbca0-725">
<b>Error en la actualización del motor de antimalware. </b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-725">
<b>The antimalware engine update failed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-726">Descripción:</span><span class="sxs-lookup"><span data-stu-id="bbca0-726">Description:</span></span>
</td>
<td >
<span data-ttu-id="bbca0-727">Antivirus de Microsoft Defender ha encontrado un error al intentar actualizar el motor.</span><span class="sxs-lookup"><span data-stu-id="bbca0-727">Microsoft Defender Antivirus has encountered an error trying to update the engine.</span></span>
<dl><span data-ttu-id="bbca0-728">
<dt>Nueva versión del motor:</dt>
<dt>Versión anterior del motor: &lt; &gt; </dt>Versión anterior del motor Tipo de motor: Tipo de motor , motor antimalware o motor del sistema de inspección de
<dt> &lt; &gt; red.</dt> 
<dt>Usuario: &lt; Dominio &gt; \& lt; Código &gt; </dt>
<dt>de error del usuario: Código de error &lt; Código de resultado asociado con el estado de &gt; amenaza. Valores HRESULT estándar.</dt> 
<dt>Descripción del error: &lt; Descripción del error &gt; Descripción del error.</dt>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-728">
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
<span data-ttu-id="bbca0-729">Acción del usuario:</span><span class="sxs-lookup"><span data-stu-id="bbca0-729">User action:</span></span>
</td>
<td >
<span data-ttu-id="bbca0-730">Error Antivirus de Microsoft Defender actualización de cliente.</span><span class="sxs-lookup"><span data-stu-id="bbca0-730">The Microsoft Defender Antivirus client update failed.</span></span> <span data-ttu-id="bbca0-731">Este evento se produce cuando el cliente no se actualiza.</span><span class="sxs-lookup"><span data-stu-id="bbca0-731">This event occurs when the client fails to update itself.</span></span> <span data-ttu-id="bbca0-732">Este evento suele deberse a una interrupción en la conectividad de red durante una actualización.</span><span class="sxs-lookup"><span data-stu-id="bbca0-732">This event is usually due to an interruption in network connectivity during an update.</span></span>
<span data-ttu-id="bbca0-733">Para solucionar este evento:</span><span class="sxs-lookup"><span data-stu-id="bbca0-733">To troubleshoot this event:</span></span>
<ol>
<li><span data-ttu-id="bbca0-734"><a href="manage-updates-baselines-microsoft-defender-antivirus.md" data-raw-source="[Update definitions](manage-updates-baselines-microsoft-defender-antivirus.md)">Actualice las definiciones</a> y fuerza un nuevo análisis directamente en el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="bbca0-734"><a href="manage-updates-baselines-microsoft-defender-antivirus.md" data-raw-source="[Update definitions](manage-updates-baselines-microsoft-defender-antivirus.md)">Update definitions</a> and force a rescan directly on the endpoint.</span></span></li>
<li><span data-ttu-id="bbca0-735">Contactar al <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Soporte técnico de Microsoft</a>.</span><span class="sxs-lookup"><span data-stu-id="bbca0-735">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="bbca0-736">Identificador de evento: 2004</span><span class="sxs-lookup"><span data-stu-id="bbca0-736">Event ID: 2004</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="bbca0-737">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="bbca0-737">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="bbca0-738">
<b>MALWAREPROTECTION_SIGNATURE_REVERSION</b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-738">
<b>MALWAREPROTECTION_SIGNATURE_REVERSION</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-739">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="bbca0-739">Message:</span></span>
</td>
<td ><span data-ttu-id="bbca0-740">
<b>Hubo un problema al cargar definiciones de antimalware. El motor de antimalware intentará cargar el último conjunto de definiciones bien conocido.</b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-740">
<b>There was a problem loading antimalware definitions. The antimalware engine will attempt to load the last-known good set of definitions.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-741">Descripción:</span><span class="sxs-lookup"><span data-stu-id="bbca0-741">Description:</span></span>
</td>
<td >
<span data-ttu-id="bbca0-742">Antivirus de Microsoft Defender ha encontrado un error al intentar cargar firmas e intentará volver a un conjunto de firmas conocido.</span><span class="sxs-lookup"><span data-stu-id="bbca0-742">Microsoft Defender Antivirus has encountered an error trying to load signatures and will attempt reverting back to a known-good set of signatures.</span></span>
<dl><span data-ttu-id="bbca0-743">
<dt>Firmas intentadas:</dt>
<dt>Código de error: Código de error Código de resultado asociado con el estado de &lt; &gt; amenaza. Valores HRESULT estándar.</dt> 
<dt>Descripción del error: &lt; Descripción del error &gt; Descripción del error.</dt> 
<dt>Versión de firma: &lt; Versión &gt; de definición</dt>
<dt>Versión del motor: &lt; versión &gt; del motor antimalware</dt>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-743">
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
<span data-ttu-id="bbca0-744">Acción del usuario:</span><span class="sxs-lookup"><span data-stu-id="bbca0-744">User action:</span></span>
</td>
<td >
<span data-ttu-id="bbca0-745">El Antivirus de Microsoft Defender intentó descargar e instalar el archivo de definiciones más reciente y falló.</span><span class="sxs-lookup"><span data-stu-id="bbca0-745">The Microsoft Defender Antivirus client attempted to download and install the latest definitions file and failed.</span></span> <span data-ttu-id="bbca0-746">Este error puede producirse cuando el cliente encuentra un error al intentar cargar las definiciones o si el archivo está dañado.</span><span class="sxs-lookup"><span data-stu-id="bbca0-746">This error can occur when the client encounters an error while trying to load the definitions, or if the file is corrupt.</span></span> <span data-ttu-id="bbca0-747">Antivirus de Microsoft Defender intentará volver a un conjunto de definiciones conocido.</span><span class="sxs-lookup"><span data-stu-id="bbca0-747">Microsoft Defender Antivirus will attempt to revert back to a known-good set of definitions.</span></span>
<span data-ttu-id="bbca0-748">Para solucionar este evento:</span><span class="sxs-lookup"><span data-stu-id="bbca0-748">To troubleshoot this event:</span></span>
<ol>
<li><span data-ttu-id="bbca0-749">Reinicie el equipo e inténtelo de nuevo.</span><span class="sxs-lookup"><span data-stu-id="bbca0-749">Restart the computer and try again.</span></span></li>
<li><span data-ttu-id="bbca0-750">Descargue las definiciones más recientes del <a href="https://aka.ms/wdsi">Inteligencia de seguridad de Microsoft sitio</a>.</span><span class="sxs-lookup"><span data-stu-id="bbca0-750">Download the latest definitions from the <a href="https://aka.ms/wdsi">Microsoft Security Intelligence site</a>.</span></span>
<span data-ttu-id="bbca0-751">Nota: El tamaño del archivo de definiciones descargado del sitio puede superar los 60 MB y no debe usarse como solución a largo plazo para actualizar definiciones.</span><span class="sxs-lookup"><span data-stu-id="bbca0-751">Note: The size of the definitions file downloaded from the site can exceed 60 MB and should not be used as a long-term solution for updating definitions.</span></span>
</li>
<li><span data-ttu-id="bbca0-752">Contactar al <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Soporte técnico de Microsoft</a>.</span><span class="sxs-lookup"><span data-stu-id="bbca0-752">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="bbca0-753">Identificador de evento: 2005</span><span class="sxs-lookup"><span data-stu-id="bbca0-753">Event ID: 2005</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="bbca0-754">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="bbca0-754">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="bbca0-755">
<b>MALWAREPROTECTION_ENGINE_UPDATE_PLATFORMOUTOFDATE</b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-755">
<b>MALWAREPROTECTION_ENGINE_UPDATE_PLATFORMOUTOFDATE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-756">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="bbca0-756">Message:</span></span>
</td>
<td ><span data-ttu-id="bbca0-757">
<b>El motor de antimalware no se pudo cargar porque la plataforma antimalware no está actualizada. La plataforma antimalware cargará el último motor antimalware bueno conocido e intentará actualizarlo.</b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-757">
<b>The antimalware engine failed to load because the antimalware platform is out of date. The antimalware platform will load the last-known good antimalware engine and attempt to update.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-758">Descripción:</span><span class="sxs-lookup"><span data-stu-id="bbca0-758">Description:</span></span>
</td>
<td >
<span data-ttu-id="bbca0-759">Antivirus de Microsoft Defender no se pudo cargar el motor de antimalware porque no se admite la versión actual de la plataforma.</span><span class="sxs-lookup"><span data-stu-id="bbca0-759">Microsoft Defender Antivirus could not load antimalware engine because current platform version is not supported.</span></span> <span data-ttu-id="bbca0-760">Antivirus de Microsoft Defender volverá al último motor conocido y se intenta actualizar la plataforma.</span><span class="sxs-lookup"><span data-stu-id="bbca0-760">Microsoft Defender Antivirus will revert back to the last known-good engine and a platform update will be attempted.</span></span>
<dl><span data-ttu-id="bbca0-761">
<dt>Versión actual de la plataforma: &lt; versión actual de la plataforma&gt;</dt>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-761">
<dt>Current Platform Version: &lt;Current platform version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="bbca0-762">Identificador de evento: 2006</span><span class="sxs-lookup"><span data-stu-id="bbca0-762">Event ID: 2006</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="bbca0-763">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="bbca0-763">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="bbca0-764">
<b>MALWAREPROTECTION_PLATFORM_UPDATE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-764">
<b>MALWAREPROTECTION_PLATFORM_UPDATE_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-765">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="bbca0-765">Message:</span></span>
</td>
<td ><span data-ttu-id="bbca0-766">
<b>Error en la actualización de la plataforma. </b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-766">
<b>The platform update failed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-767">Descripción:</span><span class="sxs-lookup"><span data-stu-id="bbca0-767">Description:</span></span>
</td>
<td >
<span data-ttu-id="bbca0-768">Antivirus de Microsoft Defender ha encontrado un error al intentar actualizar la plataforma.</span><span class="sxs-lookup"><span data-stu-id="bbca0-768">Microsoft Defender Antivirus has encountered an error trying to update the platform.</span></span>
<dl><span data-ttu-id="bbca0-769">
<dt>Versión actual de la plataforma: &lt; Versión actual &gt; de la plataforma</dt>
<dt>Código de error: Código de error &lt; Código de resultado asociado con el estado de &gt; amenaza. Valores HRESULT estándar.</dt> 
<dt>Descripción del error: &lt; Descripción del error &gt; Descripción del error.</dt>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-769">
<dt>Current Platform Version: &lt;Current platform version&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="bbca0-770">Identificador de evento: 2007</span><span class="sxs-lookup"><span data-stu-id="bbca0-770">Event ID: 2007</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="bbca0-771">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="bbca0-771">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="bbca0-772">
<b>MALWAREPROTECTION_PLATFORM_ALMOSTOUTOFDATE</b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-772">
<b>MALWAREPROTECTION_PLATFORM_ALMOSTOUTOFDATE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-773">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="bbca0-773">Message:</span></span>
</td>
<td ><span data-ttu-id="bbca0-774">
<b>La plataforma pronto estará des actualizada. Descargue la plataforma más reciente para mantener la protección actualizada.</b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-774">
<b>The platform will soon be out of date. Download the latest platform to maintain up-to-date protection.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-775">Descripción:</span><span class="sxs-lookup"><span data-stu-id="bbca0-775">Description:</span></span>
</td>
<td >
<span data-ttu-id="bbca0-776">Antivirus de Microsoft Defender pronto necesitará una versión de plataforma más reciente para admitir versiones futuras del motor de antimalware.</span><span class="sxs-lookup"><span data-stu-id="bbca0-776">Microsoft Defender Antivirus will soon require a newer platform version to support future versions of the antimalware engine.</span></span> <span data-ttu-id="bbca0-777">Descargue la plataforma Antivirus de Microsoft Defender para mantener el mejor nivel de protección disponible.</span><span class="sxs-lookup"><span data-stu-id="bbca0-777">Download the latest Microsoft Defender Antivirus platform to maintain the best level of protection available.</span></span>
<dl><span data-ttu-id="bbca0-778">
<dt>Versión actual de la plataforma: &lt; versión actual de la plataforma&gt;</dt>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-778">
<dt>Current Platform Version: &lt;Current platform version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="bbca0-779">Identificador de evento: 2010</span><span class="sxs-lookup"><span data-stu-id="bbca0-779">Event ID: 2010</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="bbca0-780">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="bbca0-780">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="bbca0-781">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_UPDATED </b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-781">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_UPDATED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-782">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="bbca0-782">Message:</span></span>
</td>
<td ><span data-ttu-id="bbca0-783">
<b>El motor de antimalware usaba el servicio de firma dinámica para obtener definiciones adicionales. </b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-783">
<b>The antimalware engine used the Dynamic Signature Service to get additional definitions. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-784">Descripción:</span><span class="sxs-lookup"><span data-stu-id="bbca0-784">Description:</span></span>
</td>
<td >
<span data-ttu-id="bbca0-785">Antivirus de Microsoft Defender <i>servicio de firma dinámica</i> para recuperar firmas adicionales para ayudar a proteger el equipo.</span><span class="sxs-lookup"><span data-stu-id="bbca0-785">Microsoft Defender Antivirus used <i>Dynamic Signature Service</i> to retrieve additional signatures to help protect your machine.</span></span>
<dl><span data-ttu-id="bbca0-786">
<dt>Versión de firma actual: &lt; Versión de &gt; firma actual</dt> 
<dt> Tipo de firma: Tipo de firma , &lt; por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bbca0-786">
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Signature Type: &lt;Signature type&gt;, for example:</span></span> <ul>
<li><span data-ttu-id="bbca0-787">Antivirus</span><span class="sxs-lookup"><span data-stu-id="bbca0-787">Antivirus</span></span></li>
<li><span data-ttu-id="bbca0-788">Antispyware</span><span class="sxs-lookup"><span data-stu-id="bbca0-788">Antispyware</span></span></li>
<li><span data-ttu-id="bbca0-789">Antimalware</span><span class="sxs-lookup"><span data-stu-id="bbca0-789">Antimalware</span></span></li>
<li><span data-ttu-id="bbca0-790">Sistema de inspección de red</span><span class="sxs-lookup"><span data-stu-id="bbca0-790">Network Inspection System</span></span></li>
</ul><span data-ttu-id="bbca0-791">
</dt>
<dt>Versión actual del motor: &lt; Versión actual &gt; del motor</dt> 
<dt> Tipo de firma dinámica: Tipo de firma &lt; dinámica , por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bbca0-791">
</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Dynamic Signature Type: &lt;Dynamic signature type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="bbca0-792">Versión</span><span class="sxs-lookup"><span data-stu-id="bbca0-792">Version</span></span></li>
<li><span data-ttu-id="bbca0-793">Timestamp</span><span class="sxs-lookup"><span data-stu-id="bbca0-793">Timestamp</span></span></li>
<li><span data-ttu-id="bbca0-794">Sin límite</span><span class="sxs-lookup"><span data-stu-id="bbca0-794">No limit</span></span></li>
<li><span data-ttu-id="bbca0-795">Duración</span><span class="sxs-lookup"><span data-stu-id="bbca0-795">Duration</span></span></li>
</ul><span data-ttu-id="bbca0-796">
</dt>
<dt>Ruta de persistencia: &lt; Path &gt; </dt>
<dt>Dynamic Signature Version: &lt; Version number &gt; </dt>Dynamic Signature Compilation
<dt>Timestamp: &lt; &gt; Timestamp</dt> 
<dt> Persistence Limit Type: &lt; Persistence limit type , for &gt; example:</span><span class="sxs-lookup"><span data-stu-id="bbca0-796">
</dt>
<dt>Persistence Path: &lt;Path&gt;</dt>
<dt>Dynamic Signature Version: &lt;Version number&gt;</dt>
<dt>Dynamic Signature Compilation Timestamp: &lt;Timestamp&gt;</dt>
<dt>Persistence Limit Type: &lt;Persistence limit type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="bbca0-797">Versión de VDM</span><span class="sxs-lookup"><span data-stu-id="bbca0-797">VDM version</span></span></li>
<li><span data-ttu-id="bbca0-798">Timestamp</span><span class="sxs-lookup"><span data-stu-id="bbca0-798">Timestamp</span></span></li>
<li><span data-ttu-id="bbca0-799">Sin límite</span><span class="sxs-lookup"><span data-stu-id="bbca0-799">No limit</span></span></li>
</ul><span data-ttu-id="bbca0-800">
</dt>
<dt>Límite de persistencia: límite de persistencia de la firma fastpath.</dt>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-800">
</dt>
<dt>Persistence Limit: Persistence limit of the fastpath signature.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="bbca0-801">Identificador de evento: 2011</span><span class="sxs-lookup"><span data-stu-id="bbca0-801">Event ID: 2011</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="bbca0-802">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="bbca0-802">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="bbca0-803">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_DELETED </b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-803">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_DELETED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-804">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="bbca0-804">Message:</span></span>
</td>
<td ><span data-ttu-id="bbca0-805">
<b>El servicio de firma dinámica eliminó las definiciones dinámicas des actualizadas. </b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-805">
<b>The Dynamic Signature Service deleted the out-of-date dynamic definitions. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-806">Descripción:</span><span class="sxs-lookup"><span data-stu-id="bbca0-806">Description:</span></span>
</td>
<td >
<span data-ttu-id="bbca0-807">Antivirus de Microsoft Defender <i>servicio de firma dinámica para</i> descartar firmas obsoletas.</span><span class="sxs-lookup"><span data-stu-id="bbca0-807">Microsoft Defender Antivirus used <i>Dynamic Signature Service</i> to discard obsolete signatures.</span></span>
<dl><span data-ttu-id="bbca0-808">
<dt>Versión de firma actual: &lt; Versión de &gt; firma actual</dt> 
<dt> Tipo de firma: Tipo de firma , &lt; por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bbca0-808">
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Signature Type: &lt;Signature type&gt;, for example:</span></span> <ul>
<li><span data-ttu-id="bbca0-809">Antivirus</span><span class="sxs-lookup"><span data-stu-id="bbca0-809">Antivirus</span></span></li>
<li><span data-ttu-id="bbca0-810">Antispyware</span><span class="sxs-lookup"><span data-stu-id="bbca0-810">Antispyware</span></span></li>
<li><span data-ttu-id="bbca0-811">Antimalware</span><span class="sxs-lookup"><span data-stu-id="bbca0-811">Antimalware</span></span></li>
<li><span data-ttu-id="bbca0-812">Sistema de inspección de red</span><span class="sxs-lookup"><span data-stu-id="bbca0-812">Network Inspection System</span></span></li>
</ul><span data-ttu-id="bbca0-813">
</dt>
<dt>Versión actual del motor: &lt; Versión actual &gt; del motor</dt> 
<dt> Tipo de firma dinámica: Tipo de firma &lt; dinámica , por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bbca0-813">
</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Dynamic Signature Type: &lt;Dynamic signature type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="bbca0-814">Versión</span><span class="sxs-lookup"><span data-stu-id="bbca0-814">Version</span></span></li>
<li><span data-ttu-id="bbca0-815">Timestamp</span><span class="sxs-lookup"><span data-stu-id="bbca0-815">Timestamp</span></span></li>
<li><span data-ttu-id="bbca0-816">Sin límite</span><span class="sxs-lookup"><span data-stu-id="bbca0-816">No limit</span></span></li>
<li><span data-ttu-id="bbca0-817">Duración</span><span class="sxs-lookup"><span data-stu-id="bbca0-817">Duration</span></span></li>
</ul><span data-ttu-id="bbca0-818">
</dt>
<dt>Ruta de persistencia: &lt; Path &gt; </dt>
<dt>Dynamic Signature Version: &lt; Version &gt; number</dt>Dynamic Signature Compilation
<dt>Timestamp: &lt; Timestamp &gt; </dt>Removal
<dt>Reason:</dt> 
<dt> Persistence Limit Type: &lt; Persistence limit type , for &gt; example:</span><span class="sxs-lookup"><span data-stu-id="bbca0-818">
</dt>
<dt>Persistence Path: &lt;Path&gt;</dt>
<dt>Dynamic Signature Version: &lt;Version number&gt;</dt>
<dt>Dynamic Signature Compilation Timestamp: &lt;Timestamp&gt;</dt>
<dt>Removal Reason:</dt>
<dt>Persistence Limit Type: &lt;Persistence limit type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="bbca0-819">Versión de VDM</span><span class="sxs-lookup"><span data-stu-id="bbca0-819">VDM version</span></span></li>
<li><span data-ttu-id="bbca0-820">Timestamp</span><span class="sxs-lookup"><span data-stu-id="bbca0-820">Timestamp</span></span></li>
<li><span data-ttu-id="bbca0-821">Sin límite</span><span class="sxs-lookup"><span data-stu-id="bbca0-821">No limit</span></span></li>
</ul><span data-ttu-id="bbca0-822">
</dt>
<dt>Límite de persistencia: límite de persistencia de la firma fastpath.</dt>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-822">
</dt>
<dt>Persistence Limit: Persistence limit of the fastpath signature.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-823">Acción del usuario:</span><span class="sxs-lookup"><span data-stu-id="bbca0-823">User action:</span></span>
</td>
<td >
<span data-ttu-id="bbca0-824">No es necesario realizar ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="bbca0-824">No action is necessary.</span></span> <span data-ttu-id="bbca0-825">El Antivirus de Microsoft Defender está en buen estado.</span><span class="sxs-lookup"><span data-stu-id="bbca0-825">The Microsoft Defender Antivirus client is in a healthy state.</span></span> <span data-ttu-id="bbca0-826">Este evento se notifica cuando el servicio de firma dinámica elimina correctamente definiciones dinámicas des actualizadas.</span><span class="sxs-lookup"><span data-stu-id="bbca0-826">This event is reported when the Dynamic Signature Service successfully deletes out-of-date dynamic definitions.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="bbca0-827">Identificador de evento: 2012</span><span class="sxs-lookup"><span data-stu-id="bbca0-827">Event ID: 2012</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="bbca0-828">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="bbca0-828">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="bbca0-829">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_UPDATE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-829">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_UPDATE_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-830">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="bbca0-830">Message:</span></span>
</td>
<td ><span data-ttu-id="bbca0-831">
<b>El motor de antimalware encontró un error al intentar usar el servicio de firma dinámica. </b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-831">
<b>The antimalware engine encountered an error when trying to use the Dynamic Signature Service. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-832">Descripción:</span><span class="sxs-lookup"><span data-stu-id="bbca0-832">Description:</span></span>
</td>
<td >
<span data-ttu-id="bbca0-833">Antivirus de Microsoft Defender ha encontrado un error al intentar usar <i>el servicio de firma dinámica</i>.</span><span class="sxs-lookup"><span data-stu-id="bbca0-833">Microsoft Defender Antivirus has encountered an error trying to use <i>Dynamic Signature Service</i>.</span></span>
<dl><span data-ttu-id="bbca0-834">
<dt>Versión de firma actual: &lt; Versión de &gt; firma actual</dt> 
<dt> Tipo de firma: Tipo de firma , &lt; por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bbca0-834">
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Signature Type: &lt;Signature type&gt;, for example:</span></span> <ul>
<li><span data-ttu-id="bbca0-835">Antivirus</span><span class="sxs-lookup"><span data-stu-id="bbca0-835">Antivirus</span></span></li>
<li><span data-ttu-id="bbca0-836">Antispyware</span><span class="sxs-lookup"><span data-stu-id="bbca0-836">Antispyware</span></span></li>
<li><span data-ttu-id="bbca0-837">Antimalware</span><span class="sxs-lookup"><span data-stu-id="bbca0-837">Antimalware</span></span></li>
<li><span data-ttu-id="bbca0-838">Sistema de inspección de red</span><span class="sxs-lookup"><span data-stu-id="bbca0-838">Network Inspection System</span></span></li>
</ul><span data-ttu-id="bbca0-839">
</dt>
<dt>Versión actual del motor: &lt; Versión del &gt; motor actual</dt>
<dt>Código de error: Código de error &lt; Código de resultado asociado con el estado de &gt; amenaza. Valores HRESULT estándar.</dt> 
<dt>Descripción del error: &lt; Descripción del error &gt; Descripción del error.</dt> 
<dt> Tipo de firma dinámica: &lt; Tipo de firma dinámica , por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bbca0-839">
</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Dynamic Signature Type: &lt;Dynamic signature type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="bbca0-840">Versión</span><span class="sxs-lookup"><span data-stu-id="bbca0-840">Version</span></span></li>
<li><span data-ttu-id="bbca0-841">Timestamp</span><span class="sxs-lookup"><span data-stu-id="bbca0-841">Timestamp</span></span></li>
<li><span data-ttu-id="bbca0-842">Sin límite</span><span class="sxs-lookup"><span data-stu-id="bbca0-842">No limit</span></span></li>
<li><span data-ttu-id="bbca0-843">Duración</span><span class="sxs-lookup"><span data-stu-id="bbca0-843">Duration</span></span></li>
</ul><span data-ttu-id="bbca0-844">
</dt>
<dt>Ruta de persistencia: &lt; Path &gt; </dt>
<dt>Dynamic Signature Version: &lt; Version number &gt; </dt>Dynamic Signature Compilation
<dt>Timestamp: &lt; &gt; Timestamp</dt> 
<dt> Persistence Limit Type: &lt; Persistence limit type , for &gt; example:</span><span class="sxs-lookup"><span data-stu-id="bbca0-844">
</dt>
<dt>Persistence Path: &lt;Path&gt;</dt>
<dt>Dynamic Signature Version: &lt;Version number&gt;</dt>
<dt>Dynamic Signature Compilation Timestamp: &lt;Timestamp&gt;</dt>
<dt>Persistence Limit Type: &lt;Persistence limit type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="bbca0-845">Versión de VDM</span><span class="sxs-lookup"><span data-stu-id="bbca0-845">VDM version</span></span></li>
<li><span data-ttu-id="bbca0-846">Timestamp</span><span class="sxs-lookup"><span data-stu-id="bbca0-846">Timestamp</span></span></li>
<li><span data-ttu-id="bbca0-847">Sin límite</span><span class="sxs-lookup"><span data-stu-id="bbca0-847">No limit</span></span></li>
</ul><span data-ttu-id="bbca0-848">
</dt>
<dt>Límite de persistencia: límite de persistencia de la firma fastpath.</dt>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-848">
</dt>
<dt>Persistence Limit: Persistence limit of the fastpath signature.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-849">Acción del usuario:</span><span class="sxs-lookup"><span data-stu-id="bbca0-849">User action:</span></span>
</td>
<td >
<span data-ttu-id="bbca0-850">Comprueba la configuración de conectividad a Internet.</span><span class="sxs-lookup"><span data-stu-id="bbca0-850">Check your Internet connectivity settings.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="bbca0-851">Identificador de evento: 2013</span><span class="sxs-lookup"><span data-stu-id="bbca0-851">Event ID: 2013</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="bbca0-852">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="bbca0-852">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="bbca0-853">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_DELETED_ALL </b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-853">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_DELETED_ALL </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-854">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="bbca0-854">Message:</span></span>
</td>
<td ><span data-ttu-id="bbca0-855">
<b>El servicio de firma dinámica eliminó todas las definiciones dinámicas. </b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-855">
<b>The Dynamic Signature Service deleted all dynamic definitions. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-856">Descripción:</span><span class="sxs-lookup"><span data-stu-id="bbca0-856">Description:</span></span>
</td>
<td >
<span data-ttu-id="bbca0-857">Antivirus de Microsoft Defender descarta todas las firmas <i>del servicio de firma</i> dinámica.</span><span class="sxs-lookup"><span data-stu-id="bbca0-857">Microsoft Defender Antivirus discarded all <i>Dynamic Signature Service</i> signatures.</span></span>
<dl><span data-ttu-id="bbca0-858">
<dt>Versión actual de la firma: &lt; versión actual de la firma&gt;</dt>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-858">
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="bbca0-859">Identificador de evento: 2020</span><span class="sxs-lookup"><span data-stu-id="bbca0-859">Event ID: 2020</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="bbca0-860">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="bbca0-860">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="bbca0-861">
<b>MALWAREPROTECTION_CLOUD_CLEAN_RESTORE_FILE_DOWNLOADED </b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-861">
<b>MALWAREPROTECTION_CLOUD_CLEAN_RESTORE_FILE_DOWNLOADED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-862">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="bbca0-862">Message:</span></span>
</td>
<td ><span data-ttu-id="bbca0-863">
<b>El motor de antimalware descargó un archivo limpio. </b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-863">
<b>The antimalware engine downloaded a clean file. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-864">Descripción:</span><span class="sxs-lookup"><span data-stu-id="bbca0-864">Description:</span></span>
</td>
<td >
<span data-ttu-id="bbca0-865">Antivirus de Microsoft Defender descargado un archivo limpio.</span><span class="sxs-lookup"><span data-stu-id="bbca0-865">Microsoft Defender Antivirus downloaded a clean file.</span></span>
<dl><span data-ttu-id="bbca0-866">
<dt>Nombre de archivo: &lt; Nombre de &gt; archivo Nombre del archivo.</dt> 
<dt>Versión de firma actual: &lt; Versión actual &gt; del motor</dt>
<dt>de firma Actual: versión actual del &lt; motor &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-866">
<dt>Filename: &lt;File name&gt; Name of the file.</dt>
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="bbca0-867">Identificador de evento: 2021</span><span class="sxs-lookup"><span data-stu-id="bbca0-867">Event ID: 2021</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="bbca0-868">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="bbca0-868">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="bbca0-869">
<b>MALWAREPROTECTION_CLOUD_CLEAN_RESTORE_FILE_DOWNLOAD_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-869">
<b>MALWAREPROTECTION_CLOUD_CLEAN_RESTORE_FILE_DOWNLOAD_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-870">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="bbca0-870">Message:</span></span>
</td>
<td ><span data-ttu-id="bbca0-871">
<b>El motor de antimalware no pudo descargar un archivo limpio. </b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-871">
<b>The antimalware engine failed to download a clean file. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-872">Descripción:</span><span class="sxs-lookup"><span data-stu-id="bbca0-872">Description:</span></span>
</td>
<td >
<span data-ttu-id="bbca0-873">Antivirus de Microsoft Defender ha encontrado un error al intentar descargar un archivo limpio.</span><span class="sxs-lookup"><span data-stu-id="bbca0-873">Microsoft Defender Antivirus has encountered an error trying to download a clean file.</span></span>
<dl><span data-ttu-id="bbca0-874">
<dt>Nombre de archivo: &lt; Nombre de &gt; archivo Nombre del archivo.</dt> 
<dt>Versión de firma actual: &lt; Versión de &gt; firma actual</dt>
<dt>Versión actual del motor: Versión actual &lt; del &gt; </dt>motor Código de error: Código de
<dt>error Código de resultado asociado con el estado de &lt; &gt; amenaza. Valores HRESULT estándar.</dt> 
<dt>Descripción del error: &lt; Descripción del error &gt; Descripción del error.</dt>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-874">
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
<span data-ttu-id="bbca0-875">Acción del usuario:</span><span class="sxs-lookup"><span data-stu-id="bbca0-875">User action:</span></span>
</td>
<td >
<span data-ttu-id="bbca0-876">Comprueba la configuración de conectividad a Internet.</span><span class="sxs-lookup"><span data-stu-id="bbca0-876">Check your Internet connectivity settings.</span></span>
<span data-ttu-id="bbca0-877">El Antivirus de Microsoft Defender encontró un error al usar el servicio de firma dinámica para descargar las definiciones más recientes en una amenaza específica.</span><span class="sxs-lookup"><span data-stu-id="bbca0-877">The Microsoft Defender Antivirus client encountered an error when using the Dynamic Signature Service to download the latest definitions to a specific threat.</span></span> <span data-ttu-id="bbca0-878">Es probable que este error se deba a un problema de conectividad de red.</span><span class="sxs-lookup"><span data-stu-id="bbca0-878">This error is likely caused by a network connectivity issue.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="bbca0-879">Identificador de evento: 2030</span><span class="sxs-lookup"><span data-stu-id="bbca0-879">Event ID: 2030</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="bbca0-880">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="bbca0-880">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="bbca0-881">
<b>MALWAREPROTECTION_OFFLINE_SCAN_INSTALLED</b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-881">
<b>MALWAREPROTECTION_OFFLINE_SCAN_INSTALLED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-882">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="bbca0-882">Message:</span></span>
</td>
<td ><span data-ttu-id="bbca0-883">
<b>El motor de antimalware se descargó y está configurado para ejecutarse sin conexión en el siguiente reinicio del sistema.</b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-883">
<b>The antimalware engine was downloaded and is configured to run offline on the next system restart.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-884">Descripción:</span><span class="sxs-lookup"><span data-stu-id="bbca0-884">Description:</span></span>
</td>
<td >
<span data-ttu-id="bbca0-885">Antivirus de Microsoft Defender descargado y configurado antivirus sin conexión para que se ejecute en el siguiente reinicio.</span><span class="sxs-lookup"><span data-stu-id="bbca0-885">Microsoft Defender Antivirus downloaded and configured offline antivirus to run on the next reboot.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="bbca0-886">Identificador de evento: 2031</span><span class="sxs-lookup"><span data-stu-id="bbca0-886">Event ID: 2031</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="bbca0-887">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="bbca0-887">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="bbca0-888">
<b>MALWAREPROTECTION_OFFLINE_SCAN_INSTALL_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-888">
<b>MALWAREPROTECTION_OFFLINE_SCAN_INSTALL_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-889">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="bbca0-889">Message:</span></span>
</td>
<td ><span data-ttu-id="bbca0-890">
<b>El motor de antimalware no pudo descargar ni configurar un examen sin conexión.</b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-890">
<b>The antimalware engine was unable to download and configure an offline scan.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-891">Descripción:</span><span class="sxs-lookup"><span data-stu-id="bbca0-891">Description:</span></span>
</td>
<td >
<span data-ttu-id="bbca0-892">Antivirus de Microsoft Defender ha encontrado un error al intentar descargar y configurar antivirus sin conexión.</span><span class="sxs-lookup"><span data-stu-id="bbca0-892">Microsoft Defender Antivirus has encountered an error trying to download and configure offline antivirus.</span></span>
<dl><span data-ttu-id="bbca0-893">
<dt>Código de error: &lt; Código de error &gt; Código de resultado asociado con el estado de amenaza. Valores HRESULT estándar.</dt> 
<dt>Descripción del error: &lt; Descripción del error &gt; Descripción del error.</dt>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-893">
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="bbca0-894">Identificador de evento: 2040</span><span class="sxs-lookup"><span data-stu-id="bbca0-894">Event ID: 2040</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="bbca0-895">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="bbca0-895">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="bbca0-896">
<b>MALWAREPROTECTION_OS_EXPIRING </b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-896">
<b>MALWAREPROTECTION_OS_EXPIRING </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-897">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="bbca0-897">Message:</span></span>
</td>
<td ><span data-ttu-id="bbca0-898">
<b>La compatibilidad con antimalware para esta versión del sistema operativo finalizará próximamente. </b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-898">
<b>Antimalware support for this operating system version will soon end. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-899">Descripción:</span><span class="sxs-lookup"><span data-stu-id="bbca0-899">Description:</span></span>
</td>
<td >
<span data-ttu-id="bbca0-900">La compatibilidad con el sistema operativo expirará en breve.</span><span class="sxs-lookup"><span data-stu-id="bbca0-900">The support for your operating system will expire shortly.</span></span> <span data-ttu-id="bbca0-901">Ejecutar Antivirus de Microsoft Defender en un sistema operativo no compatible no es una solución adecuada para protegerse contra amenazas.</span><span class="sxs-lookup"><span data-stu-id="bbca0-901">Running Microsoft Defender Antivirus on an out of support operating system is not an adequate solution to protect against threats.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="bbca0-902">Identificador de evento: 2041</span><span class="sxs-lookup"><span data-stu-id="bbca0-902">Event ID: 2041</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="bbca0-903">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="bbca0-903">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="bbca0-904">
<b>MALWAREPROTECTION_OS_EOL </b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-904">
<b>MALWAREPROTECTION_OS_EOL </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-905">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="bbca0-905">Message:</span></span>
</td>
<td ><span data-ttu-id="bbca0-906">
<b>La compatibilidad con antimalware para este sistema operativo ha finalizado. Debe actualizar el sistema operativo para que la compatibilidad continúe. </b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-906">
<b>Antimalware support for this operating system has ended. You must upgrade the operating system for continued support. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-907">Descripción:</span><span class="sxs-lookup"><span data-stu-id="bbca0-907">Description:</span></span>
</td>
<td >
<span data-ttu-id="bbca0-908">La compatibilidad con el sistema operativo ha expirado.</span><span class="sxs-lookup"><span data-stu-id="bbca0-908">The support for your operating system has expired.</span></span> <span data-ttu-id="bbca0-909">Ejecutar Antivirus de Microsoft Defender en un sistema operativo no compatible no es una solución adecuada para protegerse contra amenazas.</span><span class="sxs-lookup"><span data-stu-id="bbca0-909">Running Microsoft Defender Antivirus on an out of support operating system is not an adequate solution to protect against threats.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="bbca0-910">Identificador de evento: 2042</span><span class="sxs-lookup"><span data-stu-id="bbca0-910">Event ID: 2042</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="bbca0-911">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="bbca0-911">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="bbca0-912">
<b>MALWAREPROTECTION_PROTECTION_EOL </b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-912">
<b>MALWAREPROTECTION_PROTECTION_EOL </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-913">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="bbca0-913">Message:</span></span>
</td>
<td ><span data-ttu-id="bbca0-914">
<b>El motor de antimalware ya no es compatible con este sistema operativo y ya no protege el sistema contra malware. </b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-914">
<b>The antimalware engine no longer supports this operating system, and is no longer protecting your system from malware. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-915">Descripción:</span><span class="sxs-lookup"><span data-stu-id="bbca0-915">Description:</span></span>
</td>
<td >
<span data-ttu-id="bbca0-916">La compatibilidad con el sistema operativo ha expirado.</span><span class="sxs-lookup"><span data-stu-id="bbca0-916">The support for your operating system has expired.</span></span> <span data-ttu-id="bbca0-917">Antivirus de Microsoft Defender ya no se admite en el sistema operativo, ha dejado de funcionar y no protege contra amenazas de malware.</span><span class="sxs-lookup"><span data-stu-id="bbca0-917">Microsoft Defender Antivirus is no longer supported on your operating system, has stopped functioning, and is not protecting against malware threats.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="bbca0-918">Identificador de evento: 3002</span><span class="sxs-lookup"><span data-stu-id="bbca0-918">Event ID: 3002</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="bbca0-919">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="bbca0-919">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="bbca0-920">
<b>MALWAREPROTECTION_RTP_FEATURE_FAILURE </b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-920">
<b>MALWAREPROTECTION_RTP_FEATURE_FAILURE </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-921">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="bbca0-921">Message:</span></span>
</td>
<td ><span data-ttu-id="bbca0-922">
<b>La protección en tiempo real encontró un error y produjo un error.</b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-922">
<b>Real-time protection encountered an error and failed.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-923">Descripción:</span><span class="sxs-lookup"><span data-stu-id="bbca0-923">Description:</span></span>
</td>
<td >
<span data-ttu-id="bbca0-924">Antivirus de Microsoft Defender Real-Time de protección ha encontrado un error y ha producido un error.</span><span class="sxs-lookup"><span data-stu-id="bbca0-924">Microsoft Defender Antivirus Real-Time Protection feature has encountered an error and failed.</span></span>
<dl><span data-ttu-id="bbca0-925">
<dt>Característica: &lt; Característica , por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bbca0-925">
<dt>Feature: &lt;Feature&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="bbca0-926">En Access</span><span class="sxs-lookup"><span data-stu-id="bbca0-926">On Access</span></span></li>
<li><span data-ttu-id="bbca0-927">Descargas de Internet Explorer y datos adjuntos de Microsoft Outlook Express</span><span class="sxs-lookup"><span data-stu-id="bbca0-927">Internet Explorer downloads and Microsoft Outlook Express attachments</span></span></li>
<li><span data-ttu-id="bbca0-928">Supervisión del comportamiento</span><span class="sxs-lookup"><span data-stu-id="bbca0-928">Behavior monitoring</span></span></li>
<li><span data-ttu-id="bbca0-929">Sistema de inspección de red</span><span class="sxs-lookup"><span data-stu-id="bbca0-929">Network Inspection System</span></span></li>
</ul><span data-ttu-id="bbca0-930">
</dt>
<dt>Código de error: &lt; Código de error &gt; Código de resultado asociado con el estado de amenaza. Valores HRESULT estándar.</dt> 
<dt>Descripción del error: &lt; Descripción del error &gt; Descripción del error.</dt> 
<dt>Motivo: el motivo Antivirus de Microsoft Defender protección en tiempo real ha reiniciado una característica.</dt>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-930">
</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Reason: The reason Microsoft Defender Antivirus real-time protection has restarted a feature.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-931">Acción del usuario:</span><span class="sxs-lookup"><span data-stu-id="bbca0-931">User action:</span></span>
</td>
<td >
<span data-ttu-id="bbca0-932">Debe reiniciar el sistema y, a continuación, ejecutar un examen completo porque&#39;es posible que el sistema no se protegió durante algún tiempo.</span><span class="sxs-lookup"><span data-stu-id="bbca0-932">You should restart the system then run a full scan because it&#39;s possible the system was not protected for some time.</span></span>
<span data-ttu-id="bbca0-933">La Antivirus de Microsoft Defender cliente&#39;la característica de protección en tiempo real encontró un error porque uno de los servicios no se pudo iniciar.</span><span class="sxs-lookup"><span data-stu-id="bbca0-933">The Microsoft Defender Antivirus client&#39;s real-time protection feature encountered an error because one of the services failed to start.</span></span> <span data-ttu-id="bbca0-934">Si le sigue un identificador de evento 3007, el error fue temporal y el cliente antimalware se recuperó del error.</span><span class="sxs-lookup"><span data-stu-id="bbca0-934">If it is followed by a 3007 event ID, the failure was temporary and the antimalware client recovered from the failure.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="bbca0-935">Identificador de evento: 3007</span><span class="sxs-lookup"><span data-stu-id="bbca0-935">Event ID: 3007</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="bbca0-936">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="bbca0-936">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="bbca0-937">
<b>MALWAREPROTECTION_RTP_FEATURE_RECOVERED</b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-937">
<b>MALWAREPROTECTION_RTP_FEATURE_RECOVERED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-938">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="bbca0-938">Message:</span></span>
</td>
<td ><span data-ttu-id="bbca0-939">
<b>Protección en tiempo real recuperada de un error. Se recomienda ejecutar un examen completo del sistema cuando vea este error. </b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-939">
<b>Real-time protection recovered from a failure. We recommend running a full system scan when you see this error. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-940">Descripción:</span><span class="sxs-lookup"><span data-stu-id="bbca0-940">Description:</span></span>
</td>
<td >
<span data-ttu-id="bbca0-941">Antivirus de Microsoft Defender Protección en tiempo real ha reiniciado una característica.</span><span class="sxs-lookup"><span data-stu-id="bbca0-941">Microsoft Defender Antivirus Real-time Protection has restarted a feature.</span></span> <span data-ttu-id="bbca0-942">Se recomienda ejecutar un examen completo del sistema para detectar los elementos que se hayan perdido mientras este agente estaba abajo.</span><span class="sxs-lookup"><span data-stu-id="bbca0-942">It is recommended that you run a full system scan to detect any items that may have been missed while this agent was down.</span></span>
<dl><span data-ttu-id="bbca0-943">
<dt>Característica: &lt; Característica , por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bbca0-943">
<dt>Feature: &lt;Feature&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="bbca0-944">En Access</span><span class="sxs-lookup"><span data-stu-id="bbca0-944">On Access</span></span></li>
<li><span data-ttu-id="bbca0-945">Descargas de IE y Outlook datos adjuntos de Express</span><span class="sxs-lookup"><span data-stu-id="bbca0-945">IE downloads and Outlook Express attachments</span></span></li>
<li><span data-ttu-id="bbca0-946">Supervisión del comportamiento</span><span class="sxs-lookup"><span data-stu-id="bbca0-946">Behavior monitoring</span></span></li>
<li><span data-ttu-id="bbca0-947">Sistema de inspección de red</span><span class="sxs-lookup"><span data-stu-id="bbca0-947">Network Inspection System</span></span></li>
</ul><span data-ttu-id="bbca0-948">
</dt>
<dt>Motivo: el motivo Antivirus de Microsoft Defender protección en tiempo real ha reiniciado una característica.</dt>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-948">
</dt>
<dt>Reason: The reason Microsoft Defender Antivirus real-time protection has restarted a feature.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-949">Acción del usuario:</span><span class="sxs-lookup"><span data-stu-id="bbca0-949">User action:</span></span>
</td>
<td >
<span data-ttu-id="bbca0-950">Se ha reiniciado la característica de protección en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="bbca0-950">The real-time protection feature has restarted.</span></span> <span data-ttu-id="bbca0-951">Si este evento se produce de nuevo, póngase en contacto <a href="https://go.microsoft.com/fwlink/?LinkId=215491">con el Soporte técnico de Microsoft</a>.</span><span class="sxs-lookup"><span data-stu-id="bbca0-951">If this event happens again, contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="bbca0-952">Identificador de evento: 5000</span><span class="sxs-lookup"><span data-stu-id="bbca0-952">Event ID: 5000</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="bbca0-953">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="bbca0-953">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="bbca0-954">
<b>MALWAREPROTECTION_RTP_ENABLED </b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-954">
<b>MALWAREPROTECTION_RTP_ENABLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-955">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="bbca0-955">Message:</span></span>
</td>
<td ><span data-ttu-id="bbca0-956">
<b>La protección en tiempo real está habilitada. </b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-956">
<b>Real-time protection is enabled. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-957">Descripción:</span><span class="sxs-lookup"><span data-stu-id="bbca0-957">Description:</span></span>
</td>
<td >
<span data-ttu-id="bbca0-958">Antivirus de Microsoft Defender de protección en tiempo real en busca de malware y otro software potencialmente no deseado.</span><span class="sxs-lookup"><span data-stu-id="bbca0-958">Microsoft Defender Antivirus real-time protection scanning for malware and other potentially unwanted software was enabled.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="bbca0-959">Identificador de evento: 5001</span><span class="sxs-lookup"><span data-stu-id="bbca0-959">Event ID: 5001</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="bbca0-960">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="bbca0-960">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="bbca0-961">
<b>MALWAREPROTECTION_RTP_DISABLED</b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-961">
<b>MALWAREPROTECTION_RTP_DISABLED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-962">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="bbca0-962">Message:</span></span>
</td>
<td ><span data-ttu-id="bbca0-963">
<b>La protección en tiempo real está deshabilitada. </b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-963">
<b>Real-time protection is disabled. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-964">Descripción:</span><span class="sxs-lookup"><span data-stu-id="bbca0-964">Description:</span></span>
</td>
<td >
<span data-ttu-id="bbca0-965">Antivirus de Microsoft Defender de protección en tiempo real en busca de malware y otro software potencialmente no deseado se deshabilitó.</span><span class="sxs-lookup"><span data-stu-id="bbca0-965">Microsoft Defender Antivirus real-time protection scanning for malware and other potentially unwanted software was disabled.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="bbca0-966">Identificador de evento: 5004</span><span class="sxs-lookup"><span data-stu-id="bbca0-966">Event ID: 5004</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="bbca0-967">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="bbca0-967">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="bbca0-968">
<b>MALWAREPROTECTION_RTP_FEATURE_CONFIGURED </b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-968">
<b>MALWAREPROTECTION_RTP_FEATURE_CONFIGURED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-969">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="bbca0-969">Message:</span></span>
</td>
<td ><span data-ttu-id="bbca0-970">
<b>La configuración de protección en tiempo real cambió. </b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-970">
<b>The real-time protection configuration changed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-971">Descripción:</span><span class="sxs-lookup"><span data-stu-id="bbca0-971">Description:</span></span>
</td>
<td >
<span data-ttu-id="bbca0-972">Antivirus de Microsoft Defender configuración de características de protección en tiempo real ha cambiado.</span><span class="sxs-lookup"><span data-stu-id="bbca0-972">Microsoft Defender Antivirus real-time protection feature configuration has changed.</span></span>
<dl><span data-ttu-id="bbca0-973">
<dt>Característica: &lt; Característica , por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bbca0-973">
<dt>Feature: &lt;Feature&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="bbca0-974">En Access</span><span class="sxs-lookup"><span data-stu-id="bbca0-974">On Access</span></span></li>
<li><span data-ttu-id="bbca0-975">Descargas de IE y Outlook datos adjuntos de Express</span><span class="sxs-lookup"><span data-stu-id="bbca0-975">IE downloads and Outlook Express attachments</span></span></li>
<li><span data-ttu-id="bbca0-976">Supervisión del comportamiento</span><span class="sxs-lookup"><span data-stu-id="bbca0-976">Behavior monitoring</span></span></li>
<li><span data-ttu-id="bbca0-977">Sistema de inspección de red</span><span class="sxs-lookup"><span data-stu-id="bbca0-977">Network Inspection System</span></span></li>
</ul><span data-ttu-id="bbca0-978">
</dt>
<dt>Configuración: </dt>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-978">
</dt>
<dt>Configuration: </dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="bbca0-979">Identificador de evento: 5007</span><span class="sxs-lookup"><span data-stu-id="bbca0-979">Event ID: 5007</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="bbca0-980">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="bbca0-980">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="bbca0-981">
<b>MALWAREPROTECTION_CONFIG_CHANGED </b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-981">
<b>MALWAREPROTECTION_CONFIG_CHANGED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-982">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="bbca0-982">Message:</span></span>
</td>
<td ><span data-ttu-id="bbca0-983">
<b>Se cambió la configuración de la plataforma antimalware.</b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-983">
<b>The antimalware platform configuration changed.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-984">Descripción:</span><span class="sxs-lookup"><span data-stu-id="bbca0-984">Description:</span></span>
</td>
<td >
<span data-ttu-id="bbca0-985">Antivirus de Microsoft Defender configuración ha cambiado.</span><span class="sxs-lookup"><span data-stu-id="bbca0-985">Microsoft Defender Antivirus configuration has changed.</span></span> <span data-ttu-id="bbca0-986">Si se trata de un evento inesperado, debe revisar la configuración, ya que puede ser el resultado de malware.</span><span class="sxs-lookup"><span data-stu-id="bbca0-986">If this is an unexpected event, you should review the settings as this may be the result of malware.</span></span>
<dl><span data-ttu-id="bbca0-987">
<dt>Valor antiguo: &lt; Número de valor antiguo &gt; Valor de configuración del antivirus anterior.</dt> 
<dt>Nuevo valor: &lt; Nuevo número de valor &gt; Nuevo valor de configuración antivirus.</dt>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-987">
<dt>Old value: &lt;Old value number&gt; Old antivirus configuration value.</dt>
<dt>New value: &lt;New value number&gt; New antivirus configuration value.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="bbca0-988">Identificador de evento: 5008</span><span class="sxs-lookup"><span data-stu-id="bbca0-988">Event ID: 5008</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="bbca0-989">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="bbca0-989">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="bbca0-990">
<b>MALWAREPROTECTION_ENGINE_FAILURE</b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-990">
<b>MALWAREPROTECTION_ENGINE_FAILURE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-991">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="bbca0-991">Message:</span></span>
</td>
<td ><span data-ttu-id="bbca0-992">
<b>El motor de antimalware encontró un error y produjo un error.</b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-992">
<b>The antimalware engine encountered an error and failed.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-993">Descripción:</span><span class="sxs-lookup"><span data-stu-id="bbca0-993">Description:</span></span>
</td>
<td >
<span data-ttu-id="bbca0-994">Antivirus de Microsoft Defender motor se ha terminado debido a un error inesperado.</span><span class="sxs-lookup"><span data-stu-id="bbca0-994">Microsoft Defender Antivirus engine has been terminated due to an unexpected error.</span></span>
<dl><span data-ttu-id="bbca0-995">
<dt>Tipo de error: &lt; Tipo de &gt; error , por ejemplo: Bloquear o bloquear código</dt>de
<dt>excepción: &lt; Código de &gt; error</dt>
<dt>Recurso: &lt; recurso &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-995">
<dt>Failure Type: &lt;Failure type&gt;, for example: Crash or Hang</dt>
<dt>Exception Code: &lt;Error code&gt;</dt>
<dt>Resource: &lt;Resource&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-996">Acción del usuario:</span><span class="sxs-lookup"><span data-stu-id="bbca0-996">User action:</span></span>
</td>
<td >
<span data-ttu-id="bbca0-997">Para solucionar este evento:</span><span class="sxs-lookup"><span data-stu-id="bbca0-997">To troubleshoot this event:</span></span><ol>
<li><span data-ttu-id="bbca0-998">Intente reiniciar el servicio.</span><span class="sxs-lookup"><span data-stu-id="bbca0-998">Try to restart the service.</span></span><ul>
<li><span data-ttu-id="bbca0-999">Para antimalware, antivirus y spyware, en un símbolo del sistema con privilegios elevados, escriba <b>net stop msmpsvc</b>y, a continuación, escriba <b>net start msmpsvc</b> para reiniciar el motor de antimalware.</span><span class="sxs-lookup"><span data-stu-id="bbca0-999">For antimalware, antivirus and spyware, at an elevated command prompt, type <b>net stop msmpsvc</b>, and then type <b>net start msmpsvc</b> to restart the antimalware engine.</span></span></li>
<li><span data-ttu-id="bbca0-1000">Para el sistema <i>de</i>inspección de red , en un símbolo del sistema con privilegios elevados, escriba <b>net start nissrv</b>y, a continuación, escriba <b>net start nissrv</b> para reiniciar el motor del sistema de inspección de red mediante el archivo NiSSRV.exe. <i></i></span><span class="sxs-lookup"><span data-stu-id="bbca0-1000">For the <i>Network Inspection System</i>, at an elevated command prompt, type <b>net start nissrv</b>, and then type <b>net start nissrv</b> to restart the <i>Network Inspection System</i> engine by using the NiSSRV.exe file.</span></span>
</li>
</ul>
</li>
<li><span data-ttu-id="bbca0-1001">Si se produce un error de la misma manera, busque el código de <b></b> error accediendo al Sitio de soporte técnico de <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft</a> y especificando el número de error en el cuadro Búsqueda y póngase en contacto con el Soporte técnico <a href="https://go.microsoft.com/fwlink/?LinkId=215491">de Microsoft</a>.</span><span class="sxs-lookup"><span data-stu-id="bbca0-1001">If it fails in the same way, look up the error code by accessing the <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft Support Site</a>  and entering the error number in the <b>Search</b> box, and contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span></li>
</ol>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-1002">Acción del usuario:</span><span class="sxs-lookup"><span data-stu-id="bbca0-1002">User action:</span></span>
</td>
<td >
<span data-ttu-id="bbca0-1003">El Antivirus de Microsoft Defender cliente se detuvo debido a un error inesperado.</span><span class="sxs-lookup"><span data-stu-id="bbca0-1003">The Microsoft Defender Antivirus client engine stopped due to an unexpected error.</span></span>
<span data-ttu-id="bbca0-1004">Para solucionar este evento:</span><span class="sxs-lookup"><span data-stu-id="bbca0-1004">To troubleshoot this event:</span></span>
<ol>
<li><span data-ttu-id="bbca0-1005">Vuelva a ejecutar el examen.</span><span class="sxs-lookup"><span data-stu-id="bbca0-1005">Run the scan again.</span></span></li>
<li><span data-ttu-id="bbca0-1006">Si se produce un error de la misma manera, vaya <b></b> al sitio de soporte técnico de <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft</a>, escriba el número de error en el cuadro Buscar para buscar el código de error.</span><span class="sxs-lookup"><span data-stu-id="bbca0-1006">If it fails in the same way, go to the <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft Support site</a>, enter the error number in the <b>Search</b> box to look for the error code.</span></span></li>
<li><span data-ttu-id="bbca0-1007">Contactar al <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Soporte técnico de Microsoft</a>.</span><span class="sxs-lookup"><span data-stu-id="bbca0-1007">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="bbca0-1008">Identificador de evento: 5009</span><span class="sxs-lookup"><span data-stu-id="bbca0-1008">Event ID: 5009</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="bbca0-1009">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="bbca0-1009">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="bbca0-1010">
<b>MALWAREPROTECTION_ANTISPYWARE_ENABLED </b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-1010">
<b>MALWAREPROTECTION_ANTISPYWARE_ENABLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-1011">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="bbca0-1011">Message:</span></span>
</td>
<td ><span data-ttu-id="bbca0-1012">
<b>El examen de malware y otro software potencialmente no deseado está habilitado. </b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-1012">
<b>Scanning for malware and other potentially unwanted software is enabled. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-1013">Descripción:</span><span class="sxs-lookup"><span data-stu-id="bbca0-1013">Description:</span></span>
</td>
<td >
<span data-ttu-id="bbca0-1014">Antivirus de Microsoft Defender se ha habilitado el examen de malware y otro software potencialmente no deseado.</span><span class="sxs-lookup"><span data-stu-id="bbca0-1014">Microsoft Defender Antivirus scanning for malware and other potentially unwanted software has been enabled.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="bbca0-1015">Identificador de evento: 5010</span><span class="sxs-lookup"><span data-stu-id="bbca0-1015">Event ID: 5010</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="bbca0-1016">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="bbca0-1016">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="bbca0-1017">
<b>MALWAREPROTECTION_ANTISPYWARE_DISABLED </b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-1017">
<b>MALWAREPROTECTION_ANTISPYWARE_DISABLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-1018">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="bbca0-1018">Message:</span></span>
</td>
<td ><span data-ttu-id="bbca0-1019">
<b>El examen de malware y otro software potencialmente no deseado está deshabilitado.</b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-1019">
<b>Scanning for malware and other potentially unwanted software is disabled.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-1020">Descripción:</span><span class="sxs-lookup"><span data-stu-id="bbca0-1020">Description:</span></span>
</td>
<td >
<span data-ttu-id="bbca0-1021">Antivirus de Microsoft Defender de búsqueda de malware y otro software potencialmente no deseado está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="bbca0-1021">Microsoft Defender Antivirus scanning for malware and other potentially unwanted software is disabled.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="bbca0-1022">Identificador de evento: 5011</span><span class="sxs-lookup"><span data-stu-id="bbca0-1022">Event ID: 5011</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="bbca0-1023">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="bbca0-1023">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="bbca0-1024">
<b>MALWAREPROTECTION_ANTIVIRUS_ENABLED</b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-1024">
<b>MALWAREPROTECTION_ANTIVIRUS_ENABLED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-1025">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="bbca0-1025">Message:</span></span>
</td>
<td ><span data-ttu-id="bbca0-1026">
<b>El examen de virus está habilitado.</b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-1026">
<b>Scanning for viruses is enabled.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-1027">Descripción:</span><span class="sxs-lookup"><span data-stu-id="bbca0-1027">Description:</span></span>
</td>
<td >
<span data-ttu-id="bbca0-1028">Antivirus de Microsoft Defender se ha habilitado el examen de virus.</span><span class="sxs-lookup"><span data-stu-id="bbca0-1028">Microsoft Defender Antivirus scanning for viruses has been enabled.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="bbca0-1029">Identificador de evento: 5012</span><span class="sxs-lookup"><span data-stu-id="bbca0-1029">Event ID: 5012</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="bbca0-1030">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="bbca0-1030">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="bbca0-1031">
<b>MALWAREPROTECTION_ANTIVIRUS_DISABLED </b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-1031">
<b>MALWAREPROTECTION_ANTIVIRUS_DISABLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-1032">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="bbca0-1032">Message:</span></span>
</td>
<td ><span data-ttu-id="bbca0-1033">
<b>El examen de virus está deshabilitado. </b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-1033">
<b>Scanning for viruses is disabled. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-1034">Descripción:</span><span class="sxs-lookup"><span data-stu-id="bbca0-1034">Description:</span></span>
</td>
<td >
<span data-ttu-id="bbca0-1035">Antivirus de Microsoft Defender está deshabilitado el examen de virus.</span><span class="sxs-lookup"><span data-stu-id="bbca0-1035">Microsoft Defender Antivirus scanning for viruses is disabled.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="bbca0-1036">Identificador de evento: 5100</span><span class="sxs-lookup"><span data-stu-id="bbca0-1036">Event ID: 5100</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="bbca0-1037">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="bbca0-1037">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="bbca0-1038">
<b>MALWAREPROTECTION_EXPIRATION_WARNING_STATE </b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-1038">
<b>MALWAREPROTECTION_EXPIRATION_WARNING_STATE </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-1039">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="bbca0-1039">Message:</span></span>
</td>
<td ><span data-ttu-id="bbca0-1040">
<b>La plataforma antimalware expirará pronto. </b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-1040">
<b>The antimalware platform will expire soon. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-1041">Descripción:</span><span class="sxs-lookup"><span data-stu-id="bbca0-1041">Description:</span></span>
</td>
<td >
<span data-ttu-id="bbca0-1042">Antivirus de Microsoft Defender ha entrado en un período de gracia y expirará pronto.</span><span class="sxs-lookup"><span data-stu-id="bbca0-1042">Microsoft Defender Antivirus has entered a grace period and will soon expire.</span></span> <span data-ttu-id="bbca0-1043">Después de expirar, este programa deshabilitará la protección contra virus, spyware y otro software potencialmente no deseado.</span><span class="sxs-lookup"><span data-stu-id="bbca0-1043">After expiration, this program will disable protection against viruses, spyware, and other potentially unwanted software.</span></span>
<dl><span data-ttu-id="bbca0-1044">
<dt>Motivo de expiración: el Antivirus de Microsoft Defender expirará.</dt> 
<dt>Fecha de expiración: la Antivirus de Microsoft Defender expirará.</dt>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-1044">
<dt>Expiration Reason: The reason Microsoft Defender Antivirus will expire.</dt>
<dt>Expiration Date: The date Microsoft Defender Antivirus will expire.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="bbca0-1045">Identificador de evento: 5101</span><span class="sxs-lookup"><span data-stu-id="bbca0-1045">Event ID: 5101</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="bbca0-1046">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="bbca0-1046">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="bbca0-1047">
<b>MALWAREPROTECTION_DISABLED_EXPIRED_STATE </b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-1047">
<b>MALWAREPROTECTION_DISABLED_EXPIRED_STATE </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-1048">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="bbca0-1048">Message:</span></span>
</td>
<td ><span data-ttu-id="bbca0-1049">
<b>La plataforma antimalware ha expirado. </b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-1049">
<b>The antimalware platform is expired. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-1050">Descripción:</span><span class="sxs-lookup"><span data-stu-id="bbca0-1050">Description:</span></span>
</td>
<td >
<span data-ttu-id="bbca0-1051">Antivirus de Microsoft Defender período de gracia ha expirado.</span><span class="sxs-lookup"><span data-stu-id="bbca0-1051">Microsoft Defender Antivirus grace period has expired.</span></span> <span data-ttu-id="bbca0-1052">La protección contra virus, spyware y otro software potencialmente no deseado está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="bbca0-1052">Protection against viruses, spyware, and other potentially unwanted software is disabled.</span></span>
<dl><span data-ttu-id="bbca0-1053">
<dt>Motivo de expiración:</dt>
<dt>Fecha de expiración: </dt>Código de error: Código de error Código de resultado asociado con el estado de la 
<dt> &lt; &gt; amenaza. Valores HRESULT estándar.</dt> 
<dt>Descripción del error: &lt; Descripción del error &gt; Descripción del error.</dt>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-1053">
<dt>Expiration Reason:</dt>
<dt>Expiration Date: </dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr><span data-ttu-id="bbca0-1054">
</table>

<a id="error-codes"></a>
##Antivirus de Microsoft Defender de error de cliente Si Antivirus de Microsoft Defender experimenta algún problema, normalmente le dará un código de error para ayudarle a solucionar el problema.</span><span class="sxs-lookup"><span data-stu-id="bbca0-1054">
</table>

<a id="error-codes"></a>
## Microsoft Defender Antivirus client error codes If Microsoft Defender Antivirus experiences any issues it will usually give you an error code to help you troubleshoot the issue.</span></span> <span data-ttu-id="bbca0-1055">En la mayoría de los casos, un error significa que hubo un problema al instalar una actualización.</span><span class="sxs-lookup"><span data-stu-id="bbca0-1055">Most often an error means there was a problem installing an update.</span></span>
<span data-ttu-id="bbca0-1056">En esta sección se proporciona la siguiente información sobre Antivirus de Microsoft Defender errores de cliente.</span><span class="sxs-lookup"><span data-stu-id="bbca0-1056">This section provides the following information about Microsoft Defender Antivirus client errors.</span></span>
<span data-ttu-id="bbca0-1057">-   El código de error -   El posible motivo del error Consejo sobre qué hacer -   ahora</span><span class="sxs-lookup"><span data-stu-id="bbca0-1057">-   The error code -   The possible reason for the error -   Advice on what to do now</span></span>

<span data-ttu-id="bbca0-1058">Use la información de estas tablas para ayudar a solucionar Antivirus de Microsoft Defender códigos de error.</span><span class="sxs-lookup"><span data-stu-id="bbca0-1058">Use the information in these tables to help troubleshoot Microsoft Defender Antivirus error codes.</span></span>


<table> 
<tr>
<th colspan="2"><span data-ttu-id="bbca0-1059">Código de error: 0x80508007</span><span class="sxs-lookup"><span data-stu-id="bbca0-1059">Error code: 0x80508007</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="bbca0-1060">Message</span><span class="sxs-lookup"><span data-stu-id="bbca0-1060">Message</span></span></td>
<td><span data-ttu-id="bbca0-1061">
<b>ERR_MP_NO_MEMORY </b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-1061">
<b>ERR_MP_NO_MEMORY </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-1062">Posible motivo</span><span class="sxs-lookup"><span data-stu-id="bbca0-1062">Possible reason</span></span>
</td>
<td>
<span data-ttu-id="bbca0-1063">Este error indica que es posible que se haya quedo sin memoria.</span><span class="sxs-lookup"><span data-stu-id="bbca0-1063">This error indicates that you might have run out of memory.</span></span> 
</td>
</tr>
<tr>
<td><span data-ttu-id="bbca0-1064">Solución</span><span class="sxs-lookup"><span data-stu-id="bbca0-1064">Resolution</span></span></td>
<td>
<ol>
<li><span data-ttu-id="bbca0-1065">Comprueba la memoria disponible en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="bbca0-1065">Check the available memory on your device.</span></span></li>
<li><span data-ttu-id="bbca0-1066">Cierra todas las aplicaciones no usadas que se estén ejecutando para liberar memoria en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="bbca0-1066">Close any unused applications that are running to free up memory on your device.</span></span></li>
<li><span data-ttu-id="bbca0-1067">Reinicie el dispositivo y vuelva a ejecutar el examen.</span><span class="sxs-lookup"><span data-stu-id="bbca0-1067">Restart the device and run the scan again.</span></span> 
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="bbca0-1068">Código de error: 0x8050800C</span><span class="sxs-lookup"><span data-stu-id="bbca0-1068">Error code: 0x8050800C</span></span></th>
</tr><tr><td><span data-ttu-id="bbca0-1069">Message</span><span class="sxs-lookup"><span data-stu-id="bbca0-1069">Message</span></span></td>
<td><span data-ttu-id="bbca0-1070"><b>ERR_MP_BAD_INPUT_DATA</b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-1070"><b>ERR_MP_BAD_INPUT_DATA</b>
</span></span></td></tr><tr><td><span data-ttu-id="bbca0-1071">Posible motivo</span><span class="sxs-lookup"><span data-stu-id="bbca0-1071">Possible reason</span></span></td>
<td>
<span data-ttu-id="bbca0-1072">Este error indica que puede haber un problema con el producto de seguridad.</span><span class="sxs-lookup"><span data-stu-id="bbca0-1072">This error indicates that there might be a problem with your security product.</span></span>
</td>
</tr><tr><td><span data-ttu-id="bbca0-1073">Solución</span><span class="sxs-lookup"><span data-stu-id="bbca0-1073">Resolution</span></span></td><td>
<ol>
<li><span data-ttu-id="bbca0-1074">Actualice las definiciones.</span><span class="sxs-lookup"><span data-stu-id="bbca0-1074">Update the definitions.</span></span> <span data-ttu-id="bbca0-1075">Cualquiera de las dos:</span><span class="sxs-lookup"><span data-stu-id="bbca0-1075">Either:</span></span><ol>
<li><span data-ttu-id="bbca0-1076">Haga clic <b>en el botón Actualizar definiciones</b> de la <b>ficha</b> Actualizar en Antivirus de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="bbca0-1076">Click the <b>Update definitions</b> button on the <b>Update</b> tab in Microsoft Defender Antivirus.</span></span> <img src="images/defender-updatedefs2.png" alt="Update definitions in Microsoft Defender Antivirus"/><span data-ttu-id="bbca0-1077">O bien</span><span class="sxs-lookup"><span data-stu-id="bbca0-1077">Or,</span></span>
</li>
<li><span data-ttu-id="bbca0-1078">Descargue las definiciones más recientes del <a href="https://aka.ms/wdsi">Inteligencia de seguridad de Microsoft sitio</a>.</span><span class="sxs-lookup"><span data-stu-id="bbca0-1078">Download the latest definitions from the <a href="https://aka.ms/wdsi">Microsoft Security Intelligence site</a>.</span></span>
<span data-ttu-id="bbca0-1079">Nota: El tamaño del archivo de definiciones descargado del sitio puede superar los 60 MB y no debe usarse como solución a largo plazo para actualizar definiciones.</span><span class="sxs-lookup"><span data-stu-id="bbca0-1079">Note: The size of the definitions file downloaded from the site can exceed 60 MB and should not be used as a long-term solution for updating definitions.</span></span>
</li>
</ol>
</li>
<li><span data-ttu-id="bbca0-1080">Ejecute un examen completo.</span><span class="sxs-lookup"><span data-stu-id="bbca0-1080">Run a full scan.</span></span>
</li>
<li><span data-ttu-id="bbca0-1081">Reinicie el dispositivo e inténtelo de nuevo.</span><span class="sxs-lookup"><span data-stu-id="bbca0-1081">Restart the device and try again.</span></span></li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="bbca0-1082">Código de error: 0x80508020</span><span class="sxs-lookup"><span data-stu-id="bbca0-1082">Error code: 0x80508020</span></span></th>
</tr><tr><td><span data-ttu-id="bbca0-1083">Message</span><span class="sxs-lookup"><span data-stu-id="bbca0-1083">Message</span></span></td>
<td><span data-ttu-id="bbca0-1084"><b>ERR_MP_BAD_CONFIGURATION </b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-1084"><b>ERR_MP_BAD_CONFIGURATION </b>
</span></span></td></tr><tr><td><span data-ttu-id="bbca0-1085">Posible motivo</span><span class="sxs-lookup"><span data-stu-id="bbca0-1085">Possible reason</span></span></td>
<td>
<span data-ttu-id="bbca0-1086">Este error indica que puede haber un error de configuración del motor; normalmente, esto está relacionado con datos de entrada que no permiten que el motor funcione correctamente.</span><span class="sxs-lookup"><span data-stu-id="bbca0-1086">This error indicates that there might be an engine configuration error; commonly, this is related to input data that does not allow the engine to function properly.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="bbca0-1087">Código de error: 0x805080211</span><span class="sxs-lookup"><span data-stu-id="bbca0-1087">Error code: 0x805080211</span></span>
</th>
</tr><tr><td><span data-ttu-id="bbca0-1088">Message</span><span class="sxs-lookup"><span data-stu-id="bbca0-1088">Message</span></span></td>
<td><span data-ttu-id="bbca0-1089"><b>ERR_MP_QUARANTINE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-1089"><b>ERR_MP_QUARANTINE_FAILED </b>
</span></span></td></tr><tr><td><span data-ttu-id="bbca0-1090">Posible motivo</span><span class="sxs-lookup"><span data-stu-id="bbca0-1090">Possible reason</span></span></td>
<td>
<span data-ttu-id="bbca0-1091">Este error indica que Antivirus de Microsoft Defender no pudo poner en cuarentena una amenaza.</span><span class="sxs-lookup"><span data-stu-id="bbca0-1091">This error indicates that Microsoft Defender Antivirus failed to quarantine a threat.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="bbca0-1092">Código de error: 0x80508022</span><span class="sxs-lookup"><span data-stu-id="bbca0-1092">Error code: 0x80508022</span></span>
</th>
</tr><tr><td><span data-ttu-id="bbca0-1093">Message</span><span class="sxs-lookup"><span data-stu-id="bbca0-1093">Message</span></span></td>
<td><span data-ttu-id="bbca0-1094"><b>ERR_MP_REBOOT_REQUIRED </b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-1094"><b>ERR_MP_REBOOT_REQUIRED </b>
</span></span></td></tr><tr><td><span data-ttu-id="bbca0-1095">Posible motivo</span><span class="sxs-lookup"><span data-stu-id="bbca0-1095">Possible reason</span></span></td>
<td>
<span data-ttu-id="bbca0-1096">Este error indica que se requiere un reinicio para completar la eliminación de amenazas.</span><span class="sxs-lookup"><span data-stu-id="bbca0-1096">This error indicates that a reboot is required to complete threat removal.</span></span> 
</td>
</tr>
<tr>
<th colspan="2">
<span data-ttu-id="bbca0-1097">0x80508023</span><span class="sxs-lookup"><span data-stu-id="bbca0-1097">0x80508023</span></span>
</th>
</tr><tr><td><span data-ttu-id="bbca0-1098">Message</span><span class="sxs-lookup"><span data-stu-id="bbca0-1098">Message</span></span></td>
<td><span data-ttu-id="bbca0-1099"><b>ERR_MP_THREAT_NOT_FOUND </b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-1099"><b>ERR_MP_THREAT_NOT_FOUND </b>
</span></span></td></tr><tr><td><span data-ttu-id="bbca0-1100">Posible motivo</span><span class="sxs-lookup"><span data-stu-id="bbca0-1100">Possible reason</span></span></td>
<td>
<span data-ttu-id="bbca0-1101">Este error indica que es posible que la amenaza ya no esté presente en los medios o que el malware pueda impedir que se pueda examinar el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="bbca0-1101">This error indicates that the threat might no longer be present on the media, or malware might be stopping you from scanning your device.</span></span> 
</tr><tr><td><span data-ttu-id="bbca0-1102">Solución</span><span class="sxs-lookup"><span data-stu-id="bbca0-1102">Resolution</span></span>
</td>
<td>
<span data-ttu-id="bbca0-1103">Ejecute el <a href="https://www.microsoft.com/security/scanner/default.aspx">Examen de seguridad de Microsoft,</a> a continuación, actualice el software de seguridad e inténtelo de nuevo.</span><span class="sxs-lookup"><span data-stu-id="bbca0-1103">Run the <a href="https://www.microsoft.com/security/scanner/default.aspx">Microsoft Safety Scanner</a> then update your security software and try again.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="bbca0-1104">Código de error: 0x80508024</span><span class="sxs-lookup"><span data-stu-id="bbca0-1104">Error code: 0x80508024</span></span> </th></tr>
<tr>
<td><span data-ttu-id="bbca0-1105">Message</span><span class="sxs-lookup"><span data-stu-id="bbca0-1105">Message</span></span></td>
<td><span data-ttu-id="bbca0-1106"><b>ERR_MP_FULL_SCAN_REQUIRED </b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-1106"><b>ERR_MP_FULL_SCAN_REQUIRED </b>
</span></span></td></tr><tr><td><span data-ttu-id="bbca0-1107">Posible motivo</span><span class="sxs-lookup"><span data-stu-id="bbca0-1107">Possible reason</span></span></td>
<td>
<span data-ttu-id="bbca0-1108">Este error indica que puede ser necesario realizar un examen completo del sistema.</span><span class="sxs-lookup"><span data-stu-id="bbca0-1108">This error indicates that a full system scan might be required.</span></span> 
</td></tr>
<tr>
<td><span data-ttu-id="bbca0-1109">Solución</span><span class="sxs-lookup"><span data-stu-id="bbca0-1109">Resolution</span></span></td><td>
<span data-ttu-id="bbca0-1110">Ejecute un examen completo del sistema.</span><span class="sxs-lookup"><span data-stu-id="bbca0-1110">Run a full system scan.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="bbca0-1111">Código de error: 0x80508025</span><span class="sxs-lookup"><span data-stu-id="bbca0-1111">Error code: 0x80508025</span></span>
</th>
</tr><tr><td><span data-ttu-id="bbca0-1112">Message</span><span class="sxs-lookup"><span data-stu-id="bbca0-1112">Message</span></span></td>
<td><span data-ttu-id="bbca0-1113"><b>ERR_MP_MANUAL_STEPS_REQUIRED </b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-1113"><b>ERR_MP_MANUAL_STEPS_REQUIRED </b>
</span></span></td></tr><tr><td><span data-ttu-id="bbca0-1114">Posible motivo</span><span class="sxs-lookup"><span data-stu-id="bbca0-1114">Possible reason</span></span></td>
<td>
<span data-ttu-id="bbca0-1115">Este error indica que se requieren pasos manuales para completar la eliminación de amenazas.</span><span class="sxs-lookup"><span data-stu-id="bbca0-1115">This error indicates that manual steps are required to complete threat removal.</span></span> 
</td></tr><tr><td><span data-ttu-id="bbca0-1116">Solución</span><span class="sxs-lookup"><span data-stu-id="bbca0-1116">Resolution</span></span></td><td>
<span data-ttu-id="bbca0-1117">Siga los pasos de corrección manuales descritos en la Enciclopedia de Protección contra malware <a href="https://www.microsoft.com/security/portal/threat/Threats.aspx">de Microsoft</a>.</span><span class="sxs-lookup"><span data-stu-id="bbca0-1117">Follow the manual remediation steps outlined in the <a href="https://www.microsoft.com/security/portal/threat/Threats.aspx">Microsoft Malware Protection Encyclopedia</a>.</span></span> <span data-ttu-id="bbca0-1118">Puede encontrar un vínculo específico de la amenaza en el historial de eventos.</span><span class="sxs-lookup"><span data-stu-id="bbca0-1118">You can find a threat-specific link in the event history.</span></span><br/></td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="bbca0-1119">Código de error: 0x80508026</span><span class="sxs-lookup"><span data-stu-id="bbca0-1119">Error code: 0x80508026</span></span>
</th>
</tr><tr><td><span data-ttu-id="bbca0-1120">Message</span><span class="sxs-lookup"><span data-stu-id="bbca0-1120">Message</span></span></td>
<td><span data-ttu-id="bbca0-1121"><b>ERR_MP_REMOVE_NOT_SUPPORTED </b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-1121"><b>ERR_MP_REMOVE_NOT_SUPPORTED </b>
</span></span></td></tr><tr><td><span data-ttu-id="bbca0-1122">Posible motivo</span><span class="sxs-lookup"><span data-stu-id="bbca0-1122">Possible reason</span></span></td>
<td>
<span data-ttu-id="bbca0-1123">Este error indica que es posible que no se pueda quitar dentro del tipo de contenedor.</span><span class="sxs-lookup"><span data-stu-id="bbca0-1123">This error indicates that removal inside the container type might not be not supported.</span></span> 
</td></tr><tr><td><span data-ttu-id="bbca0-1124">Solución</span><span class="sxs-lookup"><span data-stu-id="bbca0-1124">Resolution</span></span></td><td>
<span data-ttu-id="bbca0-1125">Antivirus de Microsoft Defender no es capaz de corregir las amenazas detectadas dentro del archivo.</span><span class="sxs-lookup"><span data-stu-id="bbca0-1125">Microsoft Defender Antivirus is not able to remediate threats detected inside the archive.</span></span> <span data-ttu-id="bbca0-1126">Considere la posibilidad de quitar manualmente los recursos detectados.</span><span class="sxs-lookup"><span data-stu-id="bbca0-1126">Consider manually removing the detected resources.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="bbca0-1127">Código de error: 0x80508027</span><span class="sxs-lookup"><span data-stu-id="bbca0-1127">Error code: 0x80508027</span></span>
</th>
</tr><tr><td><span data-ttu-id="bbca0-1128">Message</span><span class="sxs-lookup"><span data-stu-id="bbca0-1128">Message</span></span></td>
<td><span data-ttu-id="bbca0-1129"><b>ERR_MP_REMOVE_LOW_MEDIUM_DISABLED </b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-1129"><b>ERR_MP_REMOVE_LOW_MEDIUM_DISABLED </b>
</span></span></td></tr><tr><td><span data-ttu-id="bbca0-1130">Posible motivo</span><span class="sxs-lookup"><span data-stu-id="bbca0-1130">Possible reason</span></span></td>
<td>
<span data-ttu-id="bbca0-1131">Este error indica que la eliminación de amenazas medias y bajas podría deshabilitarse.</span><span class="sxs-lookup"><span data-stu-id="bbca0-1131">This error indicates that removal of low and medium threats might be disabled.</span></span> 
</td></tr><tr><td><span data-ttu-id="bbca0-1132">Solución</span><span class="sxs-lookup"><span data-stu-id="bbca0-1132">Resolution</span></span></td><td>
<span data-ttu-id="bbca0-1133">Compruebe las amenazas detectadas y resuelvalas según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="bbca0-1133">Check the detected threats and resolve them as required.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="bbca0-1134">Código de error: 0x80508029</span><span class="sxs-lookup"><span data-stu-id="bbca0-1134">Error code: 0x80508029</span></span>
</th>
</tr><tr><td><span data-ttu-id="bbca0-1135">Message</span><span class="sxs-lookup"><span data-stu-id="bbca0-1135">Message</span></span></td>
<td><span data-ttu-id="bbca0-1136"><b>ERROR_MP_RESCAN_REQUIRED </b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-1136"><b>ERROR_MP_RESCAN_REQUIRED </b>
</span></span></td></tr><tr><td><span data-ttu-id="bbca0-1137">Posible motivo</span><span class="sxs-lookup"><span data-stu-id="bbca0-1137">Possible reason</span></span></td>
<td>
<span data-ttu-id="bbca0-1138">Este error indica que es necesario volver a examinar la amenaza.</span><span class="sxs-lookup"><span data-stu-id="bbca0-1138">This error indicates a rescan of the threat is required.</span></span> 
</td></tr><tr><td><span data-ttu-id="bbca0-1139">Solución</span><span class="sxs-lookup"><span data-stu-id="bbca0-1139">Resolution</span></span></td><td>
<span data-ttu-id="bbca0-1140">Ejecute un examen completo del sistema.</span><span class="sxs-lookup"><span data-stu-id="bbca0-1140">Run a full system scan.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="bbca0-1141">Código de error: 0x80508030</span><span class="sxs-lookup"><span data-stu-id="bbca0-1141">Error code: 0x80508030</span></span>
</th>
</tr><tr><td><span data-ttu-id="bbca0-1142">Message</span><span class="sxs-lookup"><span data-stu-id="bbca0-1142">Message</span></span></td>
<td><span data-ttu-id="bbca0-1143"><b>ERROR_MP_CALLISTO_REQUIRED </b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-1143"><b>ERROR_MP_CALLISTO_REQUIRED </b>
</span></span></td></tr><tr><td><span data-ttu-id="bbca0-1144">Posible motivo</span><span class="sxs-lookup"><span data-stu-id="bbca0-1144">Possible reason</span></span></td>
<td>
<span data-ttu-id="bbca0-1145">Este error indica que es necesario realizar un examen sin conexión.</span><span class="sxs-lookup"><span data-stu-id="bbca0-1145">This error indicates that an offline scan is required.</span></span> 
</td></tr><tr><td><span data-ttu-id="bbca0-1146">Solución</span><span class="sxs-lookup"><span data-stu-id="bbca0-1146">Resolution</span></span></td><td>
<span data-ttu-id="bbca0-1147">Ejecute sin conexión Antivirus de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="bbca0-1147">Run offline Microsoft Defender Antivirus.</span></span> <span data-ttu-id="bbca0-1148">Puede leer sobre cómo hacerlo en el artículo <a href="https://windows.microsoft.com/windows/what-is-windows-defender-offline">sin conexión Antivirus de Microsoft Defender .</a></span><span class="sxs-lookup"><span data-stu-id="bbca0-1148">You can read about how to do this in the <a href="https://windows.microsoft.com/windows/what-is-windows-defender-offline">offline Microsoft Defender Antivirus article</a>.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="bbca0-1149">Código de error: 0x80508031</span><span class="sxs-lookup"><span data-stu-id="bbca0-1149">Error code: 0x80508031</span></span>
</th>
</tr><tr><td><span data-ttu-id="bbca0-1150">Message</span><span class="sxs-lookup"><span data-stu-id="bbca0-1150">Message</span></span></td>
<td><span data-ttu-id="bbca0-1151"><b>ERROR_MP_PLATFORM_OUTDATED</span><span class="sxs-lookup"><span data-stu-id="bbca0-1151"><b>ERROR_MP_PLATFORM_OUTDATED</span></span><br/></b>
</td></tr><tr><td><span data-ttu-id="bbca0-1152">Posible motivo</span><span class="sxs-lookup"><span data-stu-id="bbca0-1152">Possible reason</span></span></td>
<td>
<span data-ttu-id="bbca0-1153">Este error indica que Antivirus de Microsoft Defender no admite la versión actual de la plataforma y requiere una nueva versión de la plataforma.</span><span class="sxs-lookup"><span data-stu-id="bbca0-1153">This error indicates that Microsoft Defender Antivirus does not support the current version of the platform and requires a new version of the platform.</span></span> 
</td></tr><tr><td><span data-ttu-id="bbca0-1154">Solución</span><span class="sxs-lookup"><span data-stu-id="bbca0-1154">Resolution</span></span></td><td>
<span data-ttu-id="bbca0-1155">Solo puede usar Antivirus de Microsoft Defender en Windows 10.</span><span class="sxs-lookup"><span data-stu-id="bbca0-1155">You can only use Microsoft Defender Antivirus in Windows 10.</span></span> <span data-ttu-id="bbca0-1156">Para Windows 8, Windows 7 y Windows Vista, puede usar <a href="https://www.microsoft.com/server-cloud/system-center/endpoint-protection-2012.aspx">System Center Endpoint Protection</a>.</span><span class="sxs-lookup"><span data-stu-id="bbca0-1156">For Windows 8, Windows 7 and Windows Vista, you can use <a href="https://www.microsoft.com/server-cloud/system-center/endpoint-protection-2012.aspx">System Center Endpoint Protection</a>.</span></span><br/></td>
</tr>
</table><span data-ttu-id="bbca0-1157">

<a id="internal-error-codes"></a>Los siguientes códigos de error se usan durante las pruebas internas de Antivirus de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="bbca0-1157">

<a id="internal-error-codes"></a> The following error codes are used during internal testing of Microsoft Defender Antivirus.</span></span>

<span data-ttu-id="bbca0-1158">Si ve estos errores, puede [](manage-updates-baselines-microsoft-defender-antivirus.md) intentar actualizar definiciones y forzar un nuevo análisis directamente en el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="bbca0-1158">If you see these errors, you can try to [update definitions](manage-updates-baselines-microsoft-defender-antivirus.md) and force a rescan directly on the endpoint.</span></span>


<table> 
<tr>
<th colspan="3"><span data-ttu-id="bbca0-1159">Códigos de error internos</span><span class="sxs-lookup"><span data-stu-id="bbca0-1159">Internal error codes</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="bbca0-1160"><b>Código de error</b></span><span class="sxs-lookup"><span data-stu-id="bbca0-1160"><b>Error code</b></span></span></th>
<th><span data-ttu-id="bbca0-1161">Mensaje mostrado</span><span class="sxs-lookup"><span data-stu-id="bbca0-1161">Message displayed</span></span></th>
<th><span data-ttu-id="bbca0-1162">Posible motivo de error y resolución</span><span class="sxs-lookup"><span data-stu-id="bbca0-1162">Possible reason for error and resolution</span></span></th>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-1163">0x80501004</span><span class="sxs-lookup"><span data-stu-id="bbca0-1163">0x80501004</span></span>
</td>
<td><span data-ttu-id="bbca0-1164">
<b>ERROR_MP_NO_INTERNET_CONN </b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-1164">
<b>ERROR_MP_NO_INTERNET_CONN </b>
</span></span></td>
<td>
<span data-ttu-id="bbca0-1165">Compruebe la conexión a Internet y vuelva a ejecutar el examen.</span><span class="sxs-lookup"><span data-stu-id="bbca0-1165">Check your Internet connection, then run the scan again.</span></span>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-1166">0x80501000</span><span class="sxs-lookup"><span data-stu-id="bbca0-1166">0x80501000</span></span>
</td>
<td><span data-ttu-id="bbca0-1167">
<b>ERROR_MP_UI_CONSOLIDATION_BAS</b> E</span><span class="sxs-lookup"><span data-stu-id="bbca0-1167">
<b>ERROR_MP_UI_CONSOLIDATION_BAS</b>E</span></span>
</td>
<td rowspan="34">
<span data-ttu-id="bbca0-1168">Se trata de un error interno.</span><span class="sxs-lookup"><span data-stu-id="bbca0-1168">This is an internal error.</span></span> <span data-ttu-id="bbca0-1169">La causa no está claramente definida.</span><span class="sxs-lookup"><span data-stu-id="bbca0-1169">The cause is not clearly defined.</span></span>
</td>
<td rowspan="36">

</td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-1170">0x80501001</span><span class="sxs-lookup"><span data-stu-id="bbca0-1170">0x80501001</span></span>
</td>
<td><span data-ttu-id="bbca0-1171">
<b>ERROR_MP_ACTIONS_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-1171">
<b>ERROR_MP_ACTIONS_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-1172">0x80501002</span><span class="sxs-lookup"><span data-stu-id="bbca0-1172">0x80501002</span></span>
</td>
<td><span data-ttu-id="bbca0-1173">
<b>ERROR_MP_NOENGINE</b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-1173">
<b>ERROR_MP_NOENGINE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-1174">0x80501003</span><span class="sxs-lookup"><span data-stu-id="bbca0-1174">0x80501003</span></span>
</td>
<td><span data-ttu-id="bbca0-1175">
<b>ERROR_MP_ACTIVE_THREATS</b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-1175">
<b>ERROR_MP_ACTIVE_THREATS</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-1176">0x805011011</span><span class="sxs-lookup"><span data-stu-id="bbca0-1176">0x805011011</span></span>
</td>
<td><span data-ttu-id="bbca0-1177">
<b>MP_ERROR_CODE_LUA_CANCELLED </b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-1177">
<b>MP_ERROR_CODE_LUA_CANCELLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-1178">0x80501101</span><span class="sxs-lookup"><span data-stu-id="bbca0-1178">0x80501101</span></span>
</td>
<td><span data-ttu-id="bbca0-1179">
<b>ERROR_LUA_CANCELLATION </b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-1179">
<b>ERROR_LUA_CANCELLATION </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-1180">0x80501102</span><span class="sxs-lookup"><span data-stu-id="bbca0-1180">0x80501102</span></span>
</td>
<td><span data-ttu-id="bbca0-1181">
<b>MP_ERROR_CODE_ALREADY_SHUTDOWN</b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-1181">
<b>MP_ERROR_CODE_ALREADY_SHUTDOWN</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-1182">0x80501103</span><span class="sxs-lookup"><span data-stu-id="bbca0-1182">0x80501103</span></span>
</td>
<td><span data-ttu-id="bbca0-1183">
<b>MP_ERROR_CODE_RDEVICE_S_ASYNC_CALL_PENDING </b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-1183">
<b>MP_ERROR_CODE_RDEVICE_S_ASYNC_CALL_PENDING </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-1184">0x80501104</span><span class="sxs-lookup"><span data-stu-id="bbca0-1184">0x80501104</span></span>
</td>
<td><span data-ttu-id="bbca0-1185">
<b>MP_ERROR_CODE_CANCELLED</b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-1185">
<b>MP_ERROR_CODE_CANCELLED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-1186">0x80501105</span><span class="sxs-lookup"><span data-stu-id="bbca0-1186">0x80501105</span></span>
</td>
<td><span data-ttu-id="bbca0-1187">
<b>MP_ERROR_CODE_NO_TARGETOS</b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-1187">
<b>MP_ERROR_CODE_NO_TARGETOS</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-1188">0x80501106</span><span class="sxs-lookup"><span data-stu-id="bbca0-1188">0x80501106</span></span>
</td>
<td><span data-ttu-id="bbca0-1189">
<b>MP_ERROR_CODE_BAD_REGEXP</b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-1189">
<b>MP_ERROR_CODE_BAD_REGEXP</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-1190">0x80501107</span><span class="sxs-lookup"><span data-stu-id="bbca0-1190">0x80501107</span></span>
</td>
<td><span data-ttu-id="bbca0-1191">
<b>MP_ERROR_TEST_INDUCED_ERROR</b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-1191">
<b>MP_ERROR_TEST_INDUCED_ERROR</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-1192">0x80501108</span><span class="sxs-lookup"><span data-stu-id="bbca0-1192">0x80501108</span></span>
</td>
<td><span data-ttu-id="bbca0-1193">
<b>MP_ERROR_SIG_BACKUP_DISABLED</b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-1193">
<b>MP_ERROR_SIG_BACKUP_DISABLED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-1194">0x80508001</span><span class="sxs-lookup"><span data-stu-id="bbca0-1194">0x80508001</span></span>
</td>
<td><span data-ttu-id="bbca0-1195">
<b>ERR_MP_BAD_INIT_MODULES</b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-1195">
<b>ERR_MP_BAD_INIT_MODULES</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-1196">0x80508002</span><span class="sxs-lookup"><span data-stu-id="bbca0-1196">0x80508002</span></span>
</td>
<td><span data-ttu-id="bbca0-1197">
<b>ERR_MP_BAD_DATABASE</b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-1197">
<b>ERR_MP_BAD_DATABASE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-1198">0x80508004</span><span class="sxs-lookup"><span data-stu-id="bbca0-1198">0x80508004</span></span>
</td>
<td><span data-ttu-id="bbca0-1199">
<b>ERR_MP_BAD_UFS </b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-1199">
<b>ERR_MP_BAD_UFS </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-1200">0x8050800C</span><span class="sxs-lookup"><span data-stu-id="bbca0-1200">0x8050800C</span></span>
</td>
<td><span data-ttu-id="bbca0-1201">
<b>ERR_MP_BAD_INPUT_DATA</b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-1201">
<b>ERR_MP_BAD_INPUT_DATA</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-1202">0x8050800D</span><span class="sxs-lookup"><span data-stu-id="bbca0-1202">0x8050800D</span></span>
</td>
<td><span data-ttu-id="bbca0-1203">
<b>ERR_MP_BAD_GLOBAL_STORAGE</b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-1203">
<b>ERR_MP_BAD_GLOBAL_STORAGE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-1204">0x8050800E</span><span class="sxs-lookup"><span data-stu-id="bbca0-1204">0x8050800E</span></span>
</td>
<td><span data-ttu-id="bbca0-1205">
<b>ERR_MP_OBSOLETE</b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-1205">
<b>ERR_MP_OBSOLETE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-1206">0x8050800F</span><span class="sxs-lookup"><span data-stu-id="bbca0-1206">0x8050800F</span></span>
</td>
<td><span data-ttu-id="bbca0-1207">
<b>ERR_MP_NOT_SUPPORTED</b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-1207">
<b>ERR_MP_NOT_SUPPORTED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-1208">0x8050800F 0x80508010</span><span class="sxs-lookup"><span data-stu-id="bbca0-1208">0x8050800F 0x80508010</span></span>
</td>
<td><span data-ttu-id="bbca0-1209">
<b>ERR_MP_NO_MORE_ITEMS </b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-1209">
<b>ERR_MP_NO_MORE_ITEMS </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-1210">0x80508011</span><span class="sxs-lookup"><span data-stu-id="bbca0-1210">0x80508011</span></span>
</td>
<td><span data-ttu-id="bbca0-1211">
<b>ERR_MP_DUPLICATE_SCANID</b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-1211">
<b>ERR_MP_DUPLICATE_SCANID</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-1212">0x80508012</span><span class="sxs-lookup"><span data-stu-id="bbca0-1212">0x80508012</span></span>
</td>
<td><span data-ttu-id="bbca0-1213">
<b>ERR_MP_BAD_SCANID</b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-1213">
<b>ERR_MP_BAD_SCANID</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-1214">0x80508013</span><span class="sxs-lookup"><span data-stu-id="bbca0-1214">0x80508013</span></span>
</td>
<td><span data-ttu-id="bbca0-1215">
<b>ERR_MP_BAD_USERDB_VERSION</b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-1215">
<b>ERR_MP_BAD_USERDB_VERSION</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-1216">0x80508014</span><span class="sxs-lookup"><span data-stu-id="bbca0-1216">0x80508014</span></span>
</td>
<td><span data-ttu-id="bbca0-1217">
<b>ERR_MP_RESTORE_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-1217">
<b>ERR_MP_RESTORE_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-1218">0x80508016</span><span class="sxs-lookup"><span data-stu-id="bbca0-1218">0x80508016</span></span>
</td>
<td><span data-ttu-id="bbca0-1219">
<b>ERR_MP_BAD_ACTION</b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-1219">
<b>ERR_MP_BAD_ACTION</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-1220">0x80508019</span><span class="sxs-lookup"><span data-stu-id="bbca0-1220">0x80508019</span></span>
</td>
<td><span data-ttu-id="bbca0-1221">
<b>ERR_MP_NOT_FOUND</b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-1221">
<b>ERR_MP_NOT_FOUND</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-1222">0x80509001</span><span class="sxs-lookup"><span data-stu-id="bbca0-1222">0x80509001</span></span>
</td>
<td><span data-ttu-id="bbca0-1223">
<b>ERR_RELO_BAD_EHANDLE</b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-1223">
<b>ERR_RELO_BAD_EHANDLE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-1224">0x80509003</span><span class="sxs-lookup"><span data-stu-id="bbca0-1224">0x80509003</span></span>
</td>
<td><span data-ttu-id="bbca0-1225">
<b>ERR_RELO_KERNEL_NOT_LOADED</b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-1225">
<b>ERR_RELO_KERNEL_NOT_LOADED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-1226">0x8050A001</span><span class="sxs-lookup"><span data-stu-id="bbca0-1226">0x8050A001</span></span>
</td>
<td><span data-ttu-id="bbca0-1227">
<b>ERR_MP_BADDB_OPEN</b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-1227">
<b>ERR_MP_BADDB_OPEN</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-1228">0x8050A002</span><span class="sxs-lookup"><span data-stu-id="bbca0-1228">0x8050A002</span></span>
</td>
<td><span data-ttu-id="bbca0-1229">
<b>ERR_MP_BADDB_HEADER</b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-1229">
<b>ERR_MP_BADDB_HEADER</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-1230">0x8050A003</span><span class="sxs-lookup"><span data-stu-id="bbca0-1230">0x8050A003</span></span>
</td>
<td><span data-ttu-id="bbca0-1231">
<b>ERR_MP_BADDB_OLDENGINE</b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-1231">
<b>ERR_MP_BADDB_OLDENGINE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-1232">0x8050A004</span><span class="sxs-lookup"><span data-stu-id="bbca0-1232">0x8050A004</span></span>
</td>
<td><span data-ttu-id="bbca0-1233">
<b>ERR_MP_BADDB_CONTENT </b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-1233">
<b>ERR_MP_BADDB_CONTENT </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-1234">0x8050A005</span><span class="sxs-lookup"><span data-stu-id="bbca0-1234">0x8050A005</span></span>
</td>
<td><span data-ttu-id="bbca0-1235">
<b>ERR_MP_BADDB_NOTSIGNED</b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-1235">
<b>ERR_MP_BADDB_NOTSIGNED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-1236">0x8050801</span><span class="sxs-lookup"><span data-stu-id="bbca0-1236">0x8050801</span></span>
</td>
<td><span data-ttu-id="bbca0-1237">
<b>ERR_MP_REMOVE_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-1237">
<b>ERR_MP_REMOVE_FAILED</b>
</span></span></td>
<td>
<span data-ttu-id="bbca0-1238">Se trata de un error interno.</span><span class="sxs-lookup"><span data-stu-id="bbca0-1238">This is an internal error.</span></span> <span data-ttu-id="bbca0-1239">Puede desencadenarse cuando la eliminación de malware no se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="bbca0-1239">It might be triggered when malware removal is not successful.</span></span> 
</td>
</tr>
<tr>
<td>
<span data-ttu-id="bbca0-1240">0x80508018</span><span class="sxs-lookup"><span data-stu-id="bbca0-1240">0x80508018</span></span>
</td>
<td><span data-ttu-id="bbca0-1241">
<b>ERR_MP_SCAN_ABORTED </b>
</span><span class="sxs-lookup"><span data-stu-id="bbca0-1241">
<b>ERR_MP_SCAN_ABORTED </b>
</span></span></td>
<td>
<span data-ttu-id="bbca0-1242">Se trata de un error interno.</span><span class="sxs-lookup"><span data-stu-id="bbca0-1242">This is an internal error.</span></span> <span data-ttu-id="bbca0-1243">Puede que se haya desencadenado cuando un examen no se completa.</span><span class="sxs-lookup"><span data-stu-id="bbca0-1243">It might have triggered when a scan fails to complete.</span></span> 
</td>
</tr>
</table>

## <a name="related-topics"></a><span data-ttu-id="bbca0-1244">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="bbca0-1244">Related topics</span></span>

- [<span data-ttu-id="bbca0-1245">Informe sobre la Antivirus de Microsoft Defender protección</span><span class="sxs-lookup"><span data-stu-id="bbca0-1245">Report on Microsoft Defender Antivirus protection</span></span>](report-monitor-microsoft-defender-antivirus.md)
- [<span data-ttu-id="bbca0-1246">Antivirus de Microsoft Defender en Windows 10</span><span class="sxs-lookup"><span data-stu-id="bbca0-1246">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)