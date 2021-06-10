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
# <a name="review-event-logs-and-error-codes-to-troubleshoot-issues-with-microsoft-defender-antivirus"></a><span data-ttu-id="0e5a6-104">Revisar registros de sucesos y códigos de error para solucionar problemas del Antivirus de Windows Defender</span><span class="sxs-lookup"><span data-stu-id="0e5a6-104">Review event logs and error codes to troubleshoot issues with Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="0e5a6-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="0e5a6-105">**Applies to:**</span></span>

- [<span data-ttu-id="0e5a6-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="0e5a6-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="0e5a6-107">Si encuentra un problema con Antivirus de Microsoft Defender, puede buscar en las tablas de este tema un problema de coincidencia y una posible solución.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-107">If you encounter a problem with Microsoft Defender Antivirus, you can search the tables in this topic to find a matching issue and potential solution.</span></span>

<span data-ttu-id="0e5a6-108">La lista de tablas:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-108">The tables list:</span></span>

- <span data-ttu-id="0e5a6-109">[Antivirus de Microsoft Defender de eventos](#windows-defender-av-ids) (estos se aplican a Windows 10 y Windows Server 2016)</span><span class="sxs-lookup"><span data-stu-id="0e5a6-109">[Microsoft Defender Antivirus event IDs](#windows-defender-av-ids) (these apply to both Windows 10 and Windows Server 2016)</span></span>
- [<span data-ttu-id="0e5a6-110">Antivirus de Microsoft Defender de error de cliente</span><span class="sxs-lookup"><span data-stu-id="0e5a6-110">Microsoft Defender Antivirus client error codes</span></span>](#error-codes)
- [<span data-ttu-id="0e5a6-111">Códigos Antivirus de Microsoft Defender de error de cliente internos (usados por Microsoft durante el desarrollo y las pruebas)</span><span class="sxs-lookup"><span data-stu-id="0e5a6-111">Internal Microsoft Defender Antivirus client error codes (used by Microsoft during development and testing)</span></span>](#internal-error-codes)

> [!TIP]
> <span data-ttu-id="0e5a6-112">También puede visitar el sitio web de demostración de Microsoft Defender para endpoint [en demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) para confirmar que funcionan las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-112">You can also visit the Microsoft Defender for Endpoint demo website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the following features are working:</span></span>
> 
> - <span data-ttu-id="0e5a6-113">Protección entregada en la nube</span><span class="sxs-lookup"><span data-stu-id="0e5a6-113">Cloud-delivered protection</span></span>
> - <span data-ttu-id="0e5a6-114">Aprendizaje rápido (incluido Bloquear a primera vista)</span><span class="sxs-lookup"><span data-stu-id="0e5a6-114">Fast learning (including Block at first sight)</span></span>
> - <span data-ttu-id="0e5a6-115">Bloqueo de aplicaciones potencialmente no deseado</span><span class="sxs-lookup"><span data-stu-id="0e5a6-115">Potentially unwanted application blocking</span></span>

<a id="windows-defender-av-ids"></a>
## <a name="microsoft-defender-antivirus-event-ids"></a><span data-ttu-id="0e5a6-116">Antivirus de Microsoft Defender de eventos</span><span class="sxs-lookup"><span data-stu-id="0e5a6-116">Microsoft Defender Antivirus event IDs</span></span>

<span data-ttu-id="0e5a6-117">Antivirus de Microsoft Defender registra los IDs de eventos en el Windows de eventos.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-117">Microsoft Defender Antivirus records event IDs in the Windows event log.</span></span>

<span data-ttu-id="0e5a6-118">Puede ver directamente el registro de eventos, o si tiene una herramienta de administración de eventos y información de seguridad (SIEM) de terceros, también puede usar los [IDs](troubleshoot-microsoft-defender-antivirus.md#windows-defender-av-ids) de eventos de cliente de Antivirus de Microsoft Defender para revisar eventos y errores específicos de los puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-118">You can directly view the event log, or if you have a third-party security information and event management (SIEM) tool, you can also consume [Microsoft Defender Antivirus client event IDs](troubleshoot-microsoft-defender-antivirus.md#windows-defender-av-ids) to review specific events and errors from your endpoints.</span></span>

<span data-ttu-id="0e5a6-119">En la tabla de esta sección se enumeran los principales Antivirus de Microsoft Defender de eventos y, siempre que sea posible, proporciona soluciones sugeridas para corregir o resolver el error.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-119">The table in this section lists the main Microsoft Defender Antivirus event IDs and, where possible, provides suggested solutions to fix or resolve the error.</span></span> 

## <a name="to-view-a-microsoft-defender-antivirus-event"></a><span data-ttu-id="0e5a6-120">Para ver un evento Antivirus de Microsoft Defender evento</span><span class="sxs-lookup"><span data-stu-id="0e5a6-120">To view a Microsoft Defender Antivirus event</span></span>

1.  <span data-ttu-id="0e5a6-121">Abra **el Visor de eventos**.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-121">Open **Event Viewer**.</span></span>
2.  <span data-ttu-id="0e5a6-122">En el árbol de consola, expanda **Registros de** aplicaciones y servicios , a continuación, **Microsoft**, a continuación, **Windows**, a continuación, **Windows Defender**.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-122">In the console tree, expand **Applications and Services Logs**, then **Microsoft**, then **Windows**, then **Windows Defender**.</span></span>
3.  <span data-ttu-id="0e5a6-123">Haga doble clic en **Operativo**.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-123">Double-click on **Operational**.</span></span>
4.  <span data-ttu-id="0e5a6-124">En el panel de detalles, vea la lista de eventos individuales para buscar el evento.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-124">In the details pane, view the list of individual events to find your event.</span></span>
5.  <span data-ttu-id="0e5a6-125">Haga clic en el evento para ver detalles específicos sobre un evento en el panel inferior, en las **pestañas General** **y** Detalles.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-125">Click the event to see specific details about an event in the lower pane, under the **General** and **Details** tabs.</span></span>

<table> 
<tr>
<th colspan="2" ><span data-ttu-id="0e5a6-126">Identificador de evento: 1000</span><span class="sxs-lookup"><span data-stu-id="0e5a6-126">Event ID: 1000</span></span></th>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-127">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-127">Symbolic name:</span></span>
</td>
<td><span data-ttu-id="0e5a6-128">
<b>MALWAREPROTECTION_SCAN_STARTED</b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-128">
<b>MALWAREPROTECTION_SCAN_STARTED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-129">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-129">Message:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-130">
<b>Se inició un examen de antimalware. </b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-130">
<b>An antimalware scan started. </b>
</span></span></td>
</tr>
<tr>
<td >
<span data-ttu-id="0e5a6-131">Descripción:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-131">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="0e5a6-132">
<dt>Id. de examen: &lt; Número de identificador del &gt; examen correspondiente.</dt> 
<dt> Tipo de examen: &lt; Tipo de examen , por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-132">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="0e5a6-133">Antivirus</span><span class="sxs-lookup"><span data-stu-id="0e5a6-133">Antivirus</span></span></li>
<li><span data-ttu-id="0e5a6-134">Antispyware</span><span class="sxs-lookup"><span data-stu-id="0e5a6-134">Antispyware</span></span></li>
<li><span data-ttu-id="0e5a6-135">Antimalware</span><span class="sxs-lookup"><span data-stu-id="0e5a6-135">Antimalware</span></span></li>
</ul><span data-ttu-id="0e5a6-136">
</dt>
<dt>Parámetros de examen: &lt; parámetros de examen , por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-136">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="0e5a6-137">Examen completo</span><span class="sxs-lookup"><span data-stu-id="0e5a6-137">Full scan</span></span></li>
<li><span data-ttu-id="0e5a6-138">Examen rápido</span><span class="sxs-lookup"><span data-stu-id="0e5a6-138">Quick scan</span></span></li>
<li><span data-ttu-id="0e5a6-139">Examen del cliente</span><span class="sxs-lookup"><span data-stu-id="0e5a6-139">Customer scan</span></span></li>
</ul><span data-ttu-id="0e5a6-140">
</dt>
<dt>Recursos de examen: &lt; Recursos (como archivos/directorios/BHO) que se &gt; examinaron.</dt> 
<dt>Usuario: &lt; Dominio &gt; \& lt; Usuario &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-140">
</dt>
<dt>Scan Resources: &lt;Resources (such as files/directories/BHO) that were scanned.&gt;</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="0e5a6-141">Identificador de evento: 1001</span><span class="sxs-lookup"><span data-stu-id="0e5a6-141">Event ID: 1001</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="0e5a6-142">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-142">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-143">
<b>MALWAREPROTECTION_SCAN_COMPLETED</b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-143">
<b>MALWAREPROTECTION_SCAN_COMPLETED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-144">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-144">Message:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-145">
<b>Se ha finalizado un examen de antimalware.</b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-145">
<b>An antimalware scan finished.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-146">Descripción:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-146">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="0e5a6-147">
<dt>Id. de examen: &lt; Número de identificador del &gt; examen correspondiente.</dt> 
<dt> Tipo de examen: &lt; Tipo de examen , por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-147">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="0e5a6-148">Antivirus</span><span class="sxs-lookup"><span data-stu-id="0e5a6-148">Antivirus</span></span></li>
<li><span data-ttu-id="0e5a6-149">Antispyware</span><span class="sxs-lookup"><span data-stu-id="0e5a6-149">Antispyware</span></span></li>
<li><span data-ttu-id="0e5a6-150">Antimalware</span><span class="sxs-lookup"><span data-stu-id="0e5a6-150">Antimalware</span></span></li>
</ul><span data-ttu-id="0e5a6-151">
</dt>
<dt>Parámetros de examen: &lt; parámetros de examen , por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-151">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="0e5a6-152">Examen completo</span><span class="sxs-lookup"><span data-stu-id="0e5a6-152">Full scan</span></span></li>
<li><span data-ttu-id="0e5a6-153">Examen rápido</span><span class="sxs-lookup"><span data-stu-id="0e5a6-153">Quick scan</span></span></li>
<li><span data-ttu-id="0e5a6-154">Examen del cliente</span><span class="sxs-lookup"><span data-stu-id="0e5a6-154">Customer scan</span></span></li>
</ul><span data-ttu-id="0e5a6-155">
</dt>
<dt>Usuario: &lt; Dominio &gt; \& lt; Tiempo &gt; </dt>
<dt>de examen del usuario: la &lt; duración de un examen. &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-155">
</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Scan Time: &lt;The duration of a scan.&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="0e5a6-156">Identificador de evento: 1002</span><span class="sxs-lookup"><span data-stu-id="0e5a6-156">Event ID: 1002</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="0e5a6-157">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-157">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-158">
<b>MALWAREPROTECTION_SCAN_CANCELLED </b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-158">
<b>MALWAREPROTECTION_SCAN_CANCELLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-159">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-159">Message:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-160">
<b>Antes de finalizar, se detuvo un examen antimalware. </b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-160">
<b>An antimalware scan was stopped before it finished. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-161">Descripción:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-161">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="0e5a6-162">
<dt>Id. de examen: &lt; Número de identificador del &gt; examen correspondiente.</dt> 
<dt> Tipo de examen: &lt; Tipo de examen , por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-162">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="0e5a6-163">Antivirus</span><span class="sxs-lookup"><span data-stu-id="0e5a6-163">Antivirus</span></span></li>
<li><span data-ttu-id="0e5a6-164">Antispyware</span><span class="sxs-lookup"><span data-stu-id="0e5a6-164">Antispyware</span></span></li>
<li><span data-ttu-id="0e5a6-165">Antimalware</span><span class="sxs-lookup"><span data-stu-id="0e5a6-165">Antimalware</span></span></li>
</ul><span data-ttu-id="0e5a6-166">
</dt>
<dt>Parámetros de examen: &lt; parámetros de examen , por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-166">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="0e5a6-167">Examen completo</span><span class="sxs-lookup"><span data-stu-id="0e5a6-167">Full scan</span></span></li>
<li><span data-ttu-id="0e5a6-168">Examen rápido</span><span class="sxs-lookup"><span data-stu-id="0e5a6-168">Quick scan</span></span></li>
<li><span data-ttu-id="0e5a6-169">Examen del cliente</span><span class="sxs-lookup"><span data-stu-id="0e5a6-169">Customer scan</span></span></li>
</ul><span data-ttu-id="0e5a6-170">
</dt>
<dt>Usuario: &lt; Dominio &gt; &amp; lt; Tiempo &gt; </dt>
<dt>de examen del usuario: la &lt; duración de un examen. &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-170">
</dt>
<dt>User: &lt;Domain&gt;&amp;lt;User&gt;</dt>
<dt>Scan Time: &lt;The duration of a scan.&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="0e5a6-171">Identificador de evento: 1003</span><span class="sxs-lookup"><span data-stu-id="0e5a6-171">Event ID: 1003</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="0e5a6-172">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-172">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-173">
<b>MALWAREPROTECTION_SCAN_PAUSED </b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-173">
<b>MALWAREPROTECTION_SCAN_PAUSED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-174">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-174">Message:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-175">
<b>Se ha pausado un examen antimalware. </b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-175">
<b>An antimalware scan was paused. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-176">Descripción:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-176">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="0e5a6-177">
<dt>Id. de examen: &lt; Número de identificador del &gt; examen correspondiente.</dt> 
<dt> Tipo de examen: &lt; Tipo de examen , por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-177">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="0e5a6-178">Antivirus</span><span class="sxs-lookup"><span data-stu-id="0e5a6-178">Antivirus</span></span></li>
<li><span data-ttu-id="0e5a6-179">Antispyware</span><span class="sxs-lookup"><span data-stu-id="0e5a6-179">Antispyware</span></span></li>
<li><span data-ttu-id="0e5a6-180">Antimalware</span><span class="sxs-lookup"><span data-stu-id="0e5a6-180">Antimalware</span></span></li>
</ul><span data-ttu-id="0e5a6-181">
</dt>
<dt>Parámetros de examen: &lt; parámetros de examen , por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-181">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="0e5a6-182">Examen completo</span><span class="sxs-lookup"><span data-stu-id="0e5a6-182">Full scan</span></span></li>
<li><span data-ttu-id="0e5a6-183">Examen rápido</span><span class="sxs-lookup"><span data-stu-id="0e5a6-183">Quick scan</span></span></li>
<li><span data-ttu-id="0e5a6-184">Examen del cliente</span><span class="sxs-lookup"><span data-stu-id="0e5a6-184">Customer scan</span></span></li>
</ul><span data-ttu-id="0e5a6-185">
</dt>
<dt>Usuario: &lt; Dominio &gt; \& lt; Usuario&gt;</dt>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-185">
</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="0e5a6-186">Identificador de evento: 1004</span><span class="sxs-lookup"><span data-stu-id="0e5a6-186">Event ID: 1004</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="0e5a6-187">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-187">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-188">
<b>MALWAREPROTECTION_SCAN_RESUMED </b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-188">
<b>MALWAREPROTECTION_SCAN_RESUMED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-189">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-189">Message:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-190">
<b>Se reanudó un examen antimalware. </b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-190">
<b>An antimalware scan was resumed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-191">Descripción:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-191">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="0e5a6-192">
<dt>Id. de examen: &lt; Número de identificador del &gt; examen correspondiente.</dt> 
<dt> Tipo de examen: &lt; Tipo de examen , por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-192">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="0e5a6-193">Antivirus</span><span class="sxs-lookup"><span data-stu-id="0e5a6-193">Antivirus</span></span></li>
<li><span data-ttu-id="0e5a6-194">Antispyware</span><span class="sxs-lookup"><span data-stu-id="0e5a6-194">Antispyware</span></span></li>
<li><span data-ttu-id="0e5a6-195">Antimalware</span><span class="sxs-lookup"><span data-stu-id="0e5a6-195">Antimalware</span></span></li>
</ul><span data-ttu-id="0e5a6-196">
</dt>
<dt>Parámetros de examen: &lt; parámetros de examen , por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-196">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="0e5a6-197">Examen completo</span><span class="sxs-lookup"><span data-stu-id="0e5a6-197">Full scan</span></span></li>
<li><span data-ttu-id="0e5a6-198">Examen rápido</span><span class="sxs-lookup"><span data-stu-id="0e5a6-198">Quick scan</span></span></li>
<li><span data-ttu-id="0e5a6-199">Examen del cliente</span><span class="sxs-lookup"><span data-stu-id="0e5a6-199">Customer scan</span></span></li>
</ul><span data-ttu-id="0e5a6-200">
</dt>
<dt>Usuario: &lt; Dominio &gt; \& lt; Usuario&gt;</dt>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-200">
</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="0e5a6-201">Identificador de evento: 1005</span><span class="sxs-lookup"><span data-stu-id="0e5a6-201">Event ID: 1005</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="0e5a6-202">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-202">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-203">
<b>MALWAREPROTECTION_SCAN_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-203">
<b>MALWAREPROTECTION_SCAN_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-204">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-204">Message:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-205">
<b>Error en un examen antimalware. </b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-205">
<b>An antimalware scan failed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-206">Descripción:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-206">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="0e5a6-207">
<dt>Id. de examen: &lt; Número de identificador del &gt; examen correspondiente.</dt> 
<dt> Tipo de examen: &lt; Tipo de examen , por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-207">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="0e5a6-208">Antivirus</span><span class="sxs-lookup"><span data-stu-id="0e5a6-208">Antivirus</span></span></li>
<li><span data-ttu-id="0e5a6-209">Antispyware</span><span class="sxs-lookup"><span data-stu-id="0e5a6-209">Antispyware</span></span></li>
<li><span data-ttu-id="0e5a6-210">Antimalware</span><span class="sxs-lookup"><span data-stu-id="0e5a6-210">Antimalware</span></span></li>
</ul><span data-ttu-id="0e5a6-211">
</dt>
<dt>Parámetros de examen: &lt; parámetros de examen , por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-211">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="0e5a6-212">Examen completo</span><span class="sxs-lookup"><span data-stu-id="0e5a6-212">Full scan</span></span></li>
<li><span data-ttu-id="0e5a6-213">Examen rápido</span><span class="sxs-lookup"><span data-stu-id="0e5a6-213">Quick scan</span></span></li>
<li><span data-ttu-id="0e5a6-214">Examen del cliente</span><span class="sxs-lookup"><span data-stu-id="0e5a6-214">Customer scan</span></span></li>
</ul><span data-ttu-id="0e5a6-215">
</dt>
<dt>Usuario: &lt; Dominio &gt; \& lt; Código &gt; </dt>
<dt>de error del usuario: Código de error &lt; Código de resultado asociado con el estado de &gt; amenaza. Valores HRESULT estándar.</dt> 
<dt>Descripción del error: &lt; Descripción del error &gt; Descripción del error.</dt>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-215">
</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-216">Acción del usuario:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-216">User action:</span></span>
</td>
<td >
<span data-ttu-id="0e5a6-217">El cliente antivirus encontró un error y se detuvo el examen actual.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-217">The antivirus client encountered an error, and the current scan has stopped.</span></span> <span data-ttu-id="0e5a6-218">El examen puede producir un error debido a un problema del lado cliente.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-218">The scan might fail due to a client-side issue.</span></span> <span data-ttu-id="0e5a6-219">Este registro de evento incluye el identificador de examen, el tipo de examen (Antivirus de Microsoft Defender, antispyware, antimalware), los parámetros de examen, el usuario que inició el examen, el código de error y una descripción del error.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-219">This event record includes the scan ID, type of scan (Microsoft Defender Antivirus, antispyware, antimalware), scan parameters, the user that started the scan, the error code, and a description of the error.</span></span>
<span data-ttu-id="0e5a6-220">Para solucionar este evento:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-220">To troubleshoot this event:</span></span>
<ol>
<li><span data-ttu-id="0e5a6-221">Vuelva a ejecutar el examen.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-221">Run the scan again.</span></span></li>
<li><span data-ttu-id="0e5a6-222">Si se produce un error de la misma manera, vaya <b></b> al sitio de soporte técnico de <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft</a>, escriba el número de error en el cuadro Buscar para buscar el código de error.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-222">If it fails in the same way, go to the <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft Support site</a>, enter the error number in the <b>Search</b> box to look for the error code.</span></span></li>
<li><span data-ttu-id="0e5a6-223">Contactar al <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Soporte técnico de Microsoft</a>.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-223">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="0e5a6-224">Identificador de evento: 1006</span><span class="sxs-lookup"><span data-stu-id="0e5a6-224">Event ID: 1006</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="0e5a6-225">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-225">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-226">
<b>MALWAREPROTECTION_MALWARE_DETECTED </b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-226">
<b>MALWAREPROTECTION_MALWARE_DETECTED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-227">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-227">Message:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-228">
<b>El motor de antimalware encontró malware u otro software potencialmente no deseado. </b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-228">
<b>The antimalware engine found malware or other potentially unwanted software. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-229">Descripción:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-229">Description:</span></span>
</td>
<td >
<span data-ttu-id="0e5a6-230">Para obtener más información, vea los artículos siguientes: </span><span class="sxs-lookup"><span data-stu-id="0e5a6-230">For more information, see the following:</span></span>
<dl><span data-ttu-id="0e5a6-231">
<dt>Nombre: &lt; Id. &gt; de</dt>
<dt>nombre de &lt; amenaza: Gravedad del id. &gt; </dt>de 
<dt> amenaza: gravedad , por &lt; &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-231">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="0e5a6-232">Bajo</span><span class="sxs-lookup"><span data-stu-id="0e5a6-232">Low</span></span></li>
<li><span data-ttu-id="0e5a6-233">Moderado</span><span class="sxs-lookup"><span data-stu-id="0e5a6-233">Moderate</span></span></li>
<li><span data-ttu-id="0e5a6-234">Alto</span><span class="sxs-lookup"><span data-stu-id="0e5a6-234">High</span></span></li>
<li><span data-ttu-id="0e5a6-235">Grave</span><span class="sxs-lookup"><span data-stu-id="0e5a6-235">Severe</span></span></li>
</ul><span data-ttu-id="0e5a6-236">
</dt>
<dt>Categoría: &lt; Descripción de &gt; categoría , por ejemplo, cualquier tipo de amenaza o malware.</dt> 
<dt>Ruta de acceso: &lt; Origen &gt; de detección</dt>de ruta de 
<dt> acceso de &lt; archivo: Origen de &gt; detección, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-236">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span><ul>
<li><span data-ttu-id="0e5a6-237">Unknown</span><span class="sxs-lookup"><span data-stu-id="0e5a6-237">Unknown</span></span></li>
<li><span data-ttu-id="0e5a6-238">Equipo local</span><span class="sxs-lookup"><span data-stu-id="0e5a6-238">Local computer</span></span></li>
<li><span data-ttu-id="0e5a6-239">Recurso compartido de red</span><span class="sxs-lookup"><span data-stu-id="0e5a6-239">Network share</span></span></li>
<li><span data-ttu-id="0e5a6-240">Internet</span><span class="sxs-lookup"><span data-stu-id="0e5a6-240">Internet</span></span></li>
<li><span data-ttu-id="0e5a6-241">Tráfico entrante</span><span class="sxs-lookup"><span data-stu-id="0e5a6-241">Incoming traffic</span></span></li>
<li><span data-ttu-id="0e5a6-242">Tráfico saliente</span><span class="sxs-lookup"><span data-stu-id="0e5a6-242">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="0e5a6-243">
</dt>
<dt>Tipo de &lt; detección: Tipo de &gt; detección , por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-243">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="0e5a6-244">Heurística</span><span class="sxs-lookup"><span data-stu-id="0e5a6-244">Heuristics</span></span></li>
<li><span data-ttu-id="0e5a6-245">Generic</span><span class="sxs-lookup"><span data-stu-id="0e5a6-245">Generic</span></span></li>
<li><span data-ttu-id="0e5a6-246">Concreto</span><span class="sxs-lookup"><span data-stu-id="0e5a6-246">Concrete</span></span></li>
<li><span data-ttu-id="0e5a6-247">Firma dinámica</span><span class="sxs-lookup"><span data-stu-id="0e5a6-247">Dynamic signature</span></span></li>
</ul><span data-ttu-id="0e5a6-248">
</dt>
<dt>Origen de &lt; detección: origen de &gt; detección por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-248">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="0e5a6-249">Usuario: usuario iniciado</span><span class="sxs-lookup"><span data-stu-id="0e5a6-249">User: user initiated</span></span></li>
<li><span data-ttu-id="0e5a6-250">Sistema: sistema iniciado</span><span class="sxs-lookup"><span data-stu-id="0e5a6-250">System: system initiated</span></span></li>
<li><span data-ttu-id="0e5a6-251">En tiempo real: componente en tiempo real iniciado</span><span class="sxs-lookup"><span data-stu-id="0e5a6-251">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="0e5a6-252">IOAV: Descargas de IE y Outlook datos adjuntos de Express iniciados</span><span class="sxs-lookup"><span data-stu-id="0e5a6-252">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="0e5a6-253">NIS: sistema de inspección de red</span><span class="sxs-lookup"><span data-stu-id="0e5a6-253">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="0e5a6-254">IEPROTECT: IE - IExtensionValidation; esto protege contra controles de páginas web malintencionadas</span><span class="sxs-lookup"><span data-stu-id="0e5a6-254">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="0e5a6-255">Antimalware de inicio anticipado (ELAM).</span><span class="sxs-lookup"><span data-stu-id="0e5a6-255">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="0e5a6-256">Esto incluye malware detectado por la secuencia de arranque</span><span class="sxs-lookup"><span data-stu-id="0e5a6-256">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="0e5a6-257">Atestación remota</span><span class="sxs-lookup"><span data-stu-id="0e5a6-257">Remote attestation</span></span></li>
</ul><span data-ttu-id="0e5a6-258">Interfaz de examen antimalware (AMSI).</span><span class="sxs-lookup"><span data-stu-id="0e5a6-258">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="0e5a6-259">Se usa principalmente para proteger scripts (PS, VBS), aunque también pueden invocarse por terceros.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-259">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="0e5a6-260">Estado de </dt> 
<dt>UAC: Usuario &lt; &gt; de</dt>
<dt>estado: Dominio &lt; &gt; \& lt; Nombre &gt; </dt>del proceso de usuario: proceso en la versión de firma
<dt> &lt; &gt; PID:</dt>versión de
<dt> &lt; definición &gt; </dt>Versión del
<dt>motor: Antimalware Engine &lt; versión &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-260">UAC</dt>
<dt>Status: &lt;Status&gt;</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="0e5a6-261">Identificador de evento: 1007</span><span class="sxs-lookup"><span data-stu-id="0e5a6-261">Event ID: 1007</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="0e5a6-262">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-262">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-263">
<b>MALWAREPROTECTION_MALWARE_ACTION_TAKEN </b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-263">
<b>MALWAREPROTECTION_MALWARE_ACTION_TAKEN </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-264">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-264">Message:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-265">
<b>La plataforma antimalware realizó una acción para proteger el sistema de malware u otro software potencialmente no deseado. </b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-265">
<b>The antimalware platform performed an action to protect your system from malware or other potentially unwanted software. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-266">Descripción:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-266">Description:</span></span>
</td>
<td >
<span data-ttu-id="0e5a6-267">Antivirus de Microsoft Defender ha tomado medidas para proteger esta máquina de malware u otro software potencialmente no deseado.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-267">Microsoft Defender Antivirus has taken action to protect this machine from malware or other potentially unwanted software.</span></span> <span data-ttu-id="0e5a6-268">Para obtener más información, vea los artículos siguientes: </span><span class="sxs-lookup"><span data-stu-id="0e5a6-268">For more information, see the following:</span></span>
<dl><span data-ttu-id="0e5a6-269">
<dt>Usuario: &lt; Dominio &gt; \& lt; Nombre &gt; </dt>
<dt>de usuario: &lt; Identificador de nombre &gt; de</dt>
<dt>amenaza: &lt; &gt; Id.</dt>de amenaza 
<dt> Gravedad: Gravedad , por &lt; &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-269">
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="0e5a6-270">Bajo</span><span class="sxs-lookup"><span data-stu-id="0e5a6-270">Low</span></span></li>
<li><span data-ttu-id="0e5a6-271">Moderado</span><span class="sxs-lookup"><span data-stu-id="0e5a6-271">Moderate</span></span></li>
<li><span data-ttu-id="0e5a6-272">Alto</span><span class="sxs-lookup"><span data-stu-id="0e5a6-272">High</span></span></li>
<li><span data-ttu-id="0e5a6-273">Grave</span><span class="sxs-lookup"><span data-stu-id="0e5a6-273">Severe</span></span></li>
</ul><span data-ttu-id="0e5a6-274">
</dt>
<dt>Categoría: &lt; Descripción de &gt; categoría , por ejemplo, cualquier tipo de amenaza o malware.</dt> 
<dt> Action: &lt; Action , por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-274">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Action: &lt;Action&gt;, for example:</span></span><ul>
<li><span data-ttu-id="0e5a6-275">Clean: el recurso se ha limpiado</span><span class="sxs-lookup"><span data-stu-id="0e5a6-275">Clean: The resource was cleaned</span></span></li>
<li><span data-ttu-id="0e5a6-276">Cuarentena: el recurso se ha puesto en cuarentena</span><span class="sxs-lookup"><span data-stu-id="0e5a6-276">Quarantine: The resource was quarantined</span></span></li>
<li><span data-ttu-id="0e5a6-277">Quitar: se eliminó el recurso</span><span class="sxs-lookup"><span data-stu-id="0e5a6-277">Remove: The resource was deleted</span></span></li>
<li><span data-ttu-id="0e5a6-278">Permitir: se permitió que el recurso se ejecutara o existiera</span><span class="sxs-lookup"><span data-stu-id="0e5a6-278">Allow: The resource was allowed to execute/exist</span></span></li>
<li><span data-ttu-id="0e5a6-279">Definido por el usuario: acción definida por el usuario que normalmente es una de esta lista de acciones que el usuario ha especificado</span><span class="sxs-lookup"><span data-stu-id="0e5a6-279">User defined: User-defined action that is normally one from this list of actions that the user has specified</span></span></li>
<li><span data-ttu-id="0e5a6-280">Sin acción: sin acción</span><span class="sxs-lookup"><span data-stu-id="0e5a6-280">No action: No action</span></span></li>
<li><span data-ttu-id="0e5a6-281">Bloquear: se bloqueó el recurso para que no se ejecutara</span><span class="sxs-lookup"><span data-stu-id="0e5a6-281">Block: The resource was blocked from executing</span></span></li>
</ul><span data-ttu-id="0e5a6-282">
</dt>
<dt>Estado: &lt; Status &gt; </dt>
<dt>Signature Version: &lt; Definition version &gt; </dt>Engine
<dt>Version: Antimalware Engine &lt; version &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-282">
</dt>
<dt>Status: &lt;Status&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="0e5a6-283">Identificador de evento: 1008</span><span class="sxs-lookup"><span data-stu-id="0e5a6-283">Event ID: 1008</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="0e5a6-284">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-284">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-285">
<b>MALWAREPROTECTION_MALWARE_ACTION_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-285">
<b>MALWAREPROTECTION_MALWARE_ACTION_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-286">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-286">Message:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-287">
<b>La plataforma antimalware intentó realizar una acción para proteger el sistema de malware u otro software potencialmente no deseado, pero la acción falló.</b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-287">
<b>The antimalware platform attempted to perform an action to protect your system from malware or other potentially unwanted software, but the action failed.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-288">Descripción:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-288">Description:</span></span>
</td>
<td >
<span data-ttu-id="0e5a6-289">Antivirus de Microsoft Defender ha encontrado un error al tomar medidas en malware u otro software potencialmente no deseado.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-289">Microsoft Defender Antivirus has encountered an error when taking action on malware or other potentially unwanted software.</span></span> <span data-ttu-id="0e5a6-290">Para obtener más información, vea los artículos siguientes: </span><span class="sxs-lookup"><span data-stu-id="0e5a6-290">For more information, see the following:</span></span>
<dl><span data-ttu-id="0e5a6-291">
<dt>Usuario: &lt; Dominio &gt; \& lt; Nombre &gt; </dt>
<dt>de usuario: &lt; Identificador de nombre &gt; de</dt>
<dt>amenaza: &lt; &gt; Id.</dt>de amenaza 
<dt> Gravedad: Gravedad , por &lt; &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-291">
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="0e5a6-292">Bajo</span><span class="sxs-lookup"><span data-stu-id="0e5a6-292">Low</span></span></li>
<li><span data-ttu-id="0e5a6-293">Moderado</span><span class="sxs-lookup"><span data-stu-id="0e5a6-293">Moderate</span></span></li>
<li><span data-ttu-id="0e5a6-294">Alto</span><span class="sxs-lookup"><span data-stu-id="0e5a6-294">High</span></span></li>
<li><span data-ttu-id="0e5a6-295">Grave</span><span class="sxs-lookup"><span data-stu-id="0e5a6-295">Severe</span></span></li>
</ul><span data-ttu-id="0e5a6-296">
</dt>
<dt>Categoría: &lt; Descripción de &gt; categoría , por ejemplo, cualquier tipo de amenaza o malware.</dt> 
<dt>Ruta de acceso: &lt; Ruta &gt; de acceso</dt> 
<dt> de archivo &lt; Acción: Acción , por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-296">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Action: &lt;Action&gt;, for example:</span></span><ul>
<li><span data-ttu-id="0e5a6-297">Clean: el recurso se ha limpiado</span><span class="sxs-lookup"><span data-stu-id="0e5a6-297">Clean: The resource was cleaned</span></span></li>
<li><span data-ttu-id="0e5a6-298">Cuarentena: el recurso se ha puesto en cuarentena</span><span class="sxs-lookup"><span data-stu-id="0e5a6-298">Quarantine: The resource was quarantined</span></span></li>
<li><span data-ttu-id="0e5a6-299">Quitar: se eliminó el recurso</span><span class="sxs-lookup"><span data-stu-id="0e5a6-299">Remove: The resource was deleted</span></span></li>
<li><span data-ttu-id="0e5a6-300">Permitir: se permitió que el recurso se ejecutara o existiera</span><span class="sxs-lookup"><span data-stu-id="0e5a6-300">Allow: The resource was allowed to execute/exist</span></span></li>
<li><span data-ttu-id="0e5a6-301">Definido por el usuario: acción definida por el usuario que normalmente es una de esta lista de acciones que el usuario ha especificado</span><span class="sxs-lookup"><span data-stu-id="0e5a6-301">User defined: User-defined action that is normally one from this list of actions that the user has specified</span></span></li>
<li><span data-ttu-id="0e5a6-302">Sin acción: sin acción</span><span class="sxs-lookup"><span data-stu-id="0e5a6-302">No action: No action</span></span></li>
<li><span data-ttu-id="0e5a6-303">Bloquear: se bloqueó el recurso para que no se ejecutara</span><span class="sxs-lookup"><span data-stu-id="0e5a6-303">Block: The resource was blocked from executing</span></span></li>
</ul><span data-ttu-id="0e5a6-304">
</dt>
<dt>Código de error: &lt; Código de error &gt; Código de resultado asociado con el estado de amenaza. Valores HRESULT estándar. </dt> 
<dt>Descripción del error: &lt; Descripción del error Descripción del &gt; error.</dt> 
<dt>Estado: &lt; Status &gt; </dt>
<dt>Signature Version: &lt; Definition version &gt; </dt>Engine
<dt>Version: Antimalware Engine &lt; version &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-304">
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
<th colspan="2"><span data-ttu-id="0e5a6-305">Identificador de evento: 1009</span><span class="sxs-lookup"><span data-stu-id="0e5a6-305">Event ID: 1009</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="0e5a6-306">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-306">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-307">
<b>MALWAREPROTECTION_QUARANTINE_RESTORE </b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-307">
<b>MALWAREPROTECTION_QUARANTINE_RESTORE </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-308">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-308">Message:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-309">
<b>La plataforma antimalware restauró un elemento de cuarentena. </b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-309">
<b>The antimalware platform restored an item from quarantine. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-310">Descripción:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-310">Description:</span></span>
</td>
<td >
<span data-ttu-id="0e5a6-311">Antivirus de Microsoft Defender ha restaurado un elemento de cuarentena.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-311">Microsoft Defender Antivirus has restored an item from quarantine.</span></span> <span data-ttu-id="0e5a6-312">Para obtener más información, vea los artículos siguientes: </span><span class="sxs-lookup"><span data-stu-id="0e5a6-312">For more information, see the following:</span></span>
<dl><span data-ttu-id="0e5a6-313">
<dt>Nombre: &lt; Id. &gt; de</dt>
<dt>nombre de &lt; amenaza: Gravedad del id. &gt; </dt>de 
<dt> amenaza: gravedad , por &lt; &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-313">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="0e5a6-314">Bajo</span><span class="sxs-lookup"><span data-stu-id="0e5a6-314">Low</span></span></li>
<li><span data-ttu-id="0e5a6-315">Moderado</span><span class="sxs-lookup"><span data-stu-id="0e5a6-315">Moderate</span></span></li>
<li><span data-ttu-id="0e5a6-316">Alto</span><span class="sxs-lookup"><span data-stu-id="0e5a6-316">High</span></span></li>
<li><span data-ttu-id="0e5a6-317">Grave</span><span class="sxs-lookup"><span data-stu-id="0e5a6-317">Severe</span></span></li>
</ul><span data-ttu-id="0e5a6-318">
</dt>
<dt>Categoría: &lt; Descripción de &gt; categoría , por ejemplo, cualquier tipo de amenaza o malware.</dt> 
<dt>Ruta de acceso: &lt; Usuario &gt; de ruta de</dt>
<dt>acceso de &lt; archivo: Dominio &gt; \& lt; User &gt; </dt>
<dt>Signature Version: &lt; Definition version &gt; </dt>Engine
<dt>Version: Antimalware Engine &lt; version &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-318">
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
<th colspan="2"><span data-ttu-id="0e5a6-319">Identificador de evento: 1010</span><span class="sxs-lookup"><span data-stu-id="0e5a6-319">Event ID: 1010</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="0e5a6-320">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-320">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-321">
<b>MALWAREPROTECTION_QUARANTINE_RESTORE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-321">
<b>MALWAREPROTECTION_QUARANTINE_RESTORE_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-322">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-322">Message:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-323">
<b>La plataforma antimalware no pudo restaurar un elemento de cuarentena. </b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-323">
<b>The antimalware platform could not restore an item from quarantine. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-324">Descripción:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-324">Description:</span></span>
</td>
<td >
<span data-ttu-id="0e5a6-325">Antivirus de Microsoft Defender ha encontrado un error al intentar restaurar un elemento desde la cuarentena.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-325">Microsoft Defender Antivirus has encountered an error trying to restore an item from quarantine.</span></span> <span data-ttu-id="0e5a6-326">Para obtener más información, vea los artículos siguientes: </span><span class="sxs-lookup"><span data-stu-id="0e5a6-326">For more information, see the following:</span></span>
<dl><span data-ttu-id="0e5a6-327">
<dt>Nombre: &lt; Id. &gt; de</dt>
<dt>nombre de &lt; amenaza: Gravedad del id. &gt; </dt>de 
<dt> amenaza: gravedad , por &lt; &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-327">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="0e5a6-328">Bajo</span><span class="sxs-lookup"><span data-stu-id="0e5a6-328">Low</span></span></li>
<li><span data-ttu-id="0e5a6-329">Moderado</span><span class="sxs-lookup"><span data-stu-id="0e5a6-329">Moderate</span></span></li>
<li><span data-ttu-id="0e5a6-330">Alto</span><span class="sxs-lookup"><span data-stu-id="0e5a6-330">High</span></span></li>
<li><span data-ttu-id="0e5a6-331">Grave</span><span class="sxs-lookup"><span data-stu-id="0e5a6-331">Severe</span></span></li>
</ul><span data-ttu-id="0e5a6-332">
</dt>
<dt>Categoría: &lt; Descripción de &gt; categoría , por ejemplo, cualquier tipo de amenaza o malware.</dt> 
<dt>Ruta de acceso: &lt; Usuario &gt; de ruta de</dt>
<dt>acceso de &lt; archivo: Dominio &gt; \& lt; Código &gt; </dt>
<dt>de error del usuario: Código de error &lt; Código de resultado asociado con el estado de &gt; amenaza. Valores HRESULT estándar. </dt> 
<dt>Descripción del error: &lt; Descripción del error Descripción del &gt; error.</dt> 
<dt>Versión de firma: &lt; Versión &gt; de definición</dt>
<dt>Versión del motor: &lt; Antimalware Engine versión &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-332">
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
<th colspan="2"><span data-ttu-id="0e5a6-333">Identificador de evento: 1011</span><span class="sxs-lookup"><span data-stu-id="0e5a6-333">Event ID: 1011</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="0e5a6-334">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-334">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-335">
<b>MALWAREPROTECTION_QUARANTINE_DELETE</b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-335">
<b>MALWAREPROTECTION_QUARANTINE_DELETE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-336">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-336">Message:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-337">
<b>La plataforma antimalware eliminó un elemento de la cuarentena. </b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-337">
<b>The antimalware platform deleted an item from quarantine. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-338">Descripción:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-338">Description:</span></span>
</td>
<td >
<span data-ttu-id="0e5a6-339">Antivirus de Microsoft Defender ha eliminado un elemento de la cuarentena.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-339">Microsoft Defender Antivirus has deleted an item from quarantine.</span></span><br/><span data-ttu-id="0e5a6-340">Para obtener más información, vea los artículos siguientes: </span><span class="sxs-lookup"><span data-stu-id="0e5a6-340">For more information, see the following:</span></span>
<dl><span data-ttu-id="0e5a6-341">
<dt>Nombre: &lt; Id. &gt; de</dt>
<dt>nombre de &lt; amenaza: Gravedad del id. &gt; </dt>de 
<dt> amenaza: gravedad , por &lt; &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-341">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="0e5a6-342">Bajo</span><span class="sxs-lookup"><span data-stu-id="0e5a6-342">Low</span></span></li>
<li><span data-ttu-id="0e5a6-343">Moderado</span><span class="sxs-lookup"><span data-stu-id="0e5a6-343">Moderate</span></span></li>
<li><span data-ttu-id="0e5a6-344">Alto</span><span class="sxs-lookup"><span data-stu-id="0e5a6-344">High</span></span></li>
<li><span data-ttu-id="0e5a6-345">Grave</span><span class="sxs-lookup"><span data-stu-id="0e5a6-345">Severe</span></span></li>
</ul><span data-ttu-id="0e5a6-346">
</dt>
<dt>Categoría: &lt; Descripción de &gt; categoría , por ejemplo, cualquier tipo de amenaza o malware.</dt> 
<dt>Ruta de acceso: &lt; Usuario &gt; de ruta de</dt>
<dt>acceso de &lt; archivo: Dominio &gt; \& lt; User &gt; </dt>
<dt>Signature Version: &lt; Definition version &gt; </dt>Engine
<dt>Version: Antimalware Engine &lt; version &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-346">
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
<th colspan="2"><span data-ttu-id="0e5a6-347">Identificador de evento: 1012</span><span class="sxs-lookup"><span data-stu-id="0e5a6-347">Event ID: 1012</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="0e5a6-348">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-348">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-349">
<b>MALWAREPROTECTION_QUARANTINE_DELETE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-349">
<b>MALWAREPROTECTION_QUARANTINE_DELETE_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-350">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-350">Message:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-351">
<b>La plataforma antimalware no pudo eliminar un elemento de la cuarentena.</b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-351">
<b>The antimalware platform could not delete an item from quarantine.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-352">Descripción:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-352">Description:</span></span>
</td>
<td >
<span data-ttu-id="0e5a6-353">Antivirus de Microsoft Defender ha encontrado un error al intentar eliminar un elemento de la cuarentena.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-353">Microsoft Defender Antivirus has encountered an error trying to delete an item from quarantine.</span></span>
<span data-ttu-id="0e5a6-354">Para obtener más información, vea los artículos siguientes: </span><span class="sxs-lookup"><span data-stu-id="0e5a6-354">For more information, see the following:</span></span>
<dl><span data-ttu-id="0e5a6-355">
<dt>Nombre: &lt; Id. &gt; de</dt>
<dt>nombre de &lt; amenaza: Gravedad del id. &gt; </dt>de 
<dt> amenaza: gravedad , por &lt; &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-355">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="0e5a6-356">Bajo</span><span class="sxs-lookup"><span data-stu-id="0e5a6-356">Low</span></span></li>
<li><span data-ttu-id="0e5a6-357">Moderado</span><span class="sxs-lookup"><span data-stu-id="0e5a6-357">Moderate</span></span></li>
<li><span data-ttu-id="0e5a6-358">Alto</span><span class="sxs-lookup"><span data-stu-id="0e5a6-358">High</span></span></li>
<li><span data-ttu-id="0e5a6-359">Grave</span><span class="sxs-lookup"><span data-stu-id="0e5a6-359">Severe</span></span></li>
</ul><span data-ttu-id="0e5a6-360">
</dt>
<dt>Categoría: &lt; Descripción de &gt; categoría , por ejemplo, cualquier tipo de amenaza o malware.</dt> 
<dt>Ruta de acceso: &lt; Usuario &gt; de ruta de</dt>
<dt>acceso de &lt; archivo: Dominio &gt; \& lt; Código &gt; </dt>
<dt>de error del usuario: Código de error &lt; Código de resultado asociado con el estado de &gt; amenaza. Valores HRESULT estándar. </dt> 
<dt>Descripción del error: &lt; Descripción del error Descripción del &gt; error.</dt> 
<dt>Versión de firma: &lt; Versión &gt; de definición</dt>
<dt>Versión del motor: &lt; Antimalware Engine versión &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-360">
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
<th colspan="2"><span data-ttu-id="0e5a6-361">Identificador de evento: 1013</span><span class="sxs-lookup"><span data-stu-id="0e5a6-361">Event ID: 1013</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="0e5a6-362">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-362">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-363">
<b>MALWAREPROTECTION_MALWARE_HISTORY_DELETE </b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-363">
<b>MALWAREPROTECTION_MALWARE_HISTORY_DELETE </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-364">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-364">Message:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-365">
<b>La plataforma antimalware eliminó el historial de malware y otro software potencialmente no deseado.</b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-365">
<b>The antimalware platform deleted history of malware and other potentially unwanted software.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-366">Descripción:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-366">Description:</span></span>
</td>
<td >
<span data-ttu-id="0e5a6-367">Antivirus de Microsoft Defender ha eliminado el historial de malware y otro software potencialmente no deseado.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-367">Microsoft Defender Antivirus has removed history of malware and other potentially unwanted software.</span></span>
<dl><span data-ttu-id="0e5a6-368">
<dt>Hora: hora en la que se produjo el evento, por ejemplo, cuando se purga el historial. Este parámetro no se usa en eventos de amenazas para que no haya confusión con respecto a si es tiempo de corrección o tiempo de infección. Para ellos, los llamamos específicamente tiempo de acción o tiempo de detección.</dt> 
<dt>Usuario: &lt; Dominio &gt; \& lt; Usuario &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-368">
<dt>Time: The time when the event occurred, for example when the history is purged. This parameter is not used in threat events so that there is no confusion regarding whether it is remediation time or infection time. For those, we specifically call them as Action Time or Detection Time.</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="0e5a6-369">Identificador de evento: 1014</span><span class="sxs-lookup"><span data-stu-id="0e5a6-369">Event ID: 1014</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="0e5a6-370">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-370">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-371">
<b>MALWAREPROTECTION_MALWARE_HISTORY_DELETE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-371">
<b>MALWAREPROTECTION_MALWARE_HISTORY_DELETE_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-372">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-372">Message:</span></span>
</td>
<td >
<span data-ttu-id="0e5a6-373">La plataforma antimalware no pudo eliminar el historial de malware y otro software potencialmente no deseado.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-373">The antimalware platform could not delete history of malware and other potentially unwanted software.</span></span>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-374">Descripción:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-374">Description:</span></span>
</td>
<td >
<span data-ttu-id="0e5a6-375">Antivirus de Microsoft Defender ha encontrado un error al intentar quitar el historial de malware y otro software potencialmente no deseado.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-375">Microsoft Defender Antivirus has encountered an error trying to remove history of malware and other potentially unwanted software.</span></span>
<dl><span data-ttu-id="0e5a6-376">
<dt>Hora: hora en la que se produjo el evento, por ejemplo, cuando se purga el historial. Este parámetro no se usa en eventos de amenazas para que no haya confusión con respecto a si es tiempo de corrección o tiempo de infección. Para ellos, los llamamos específicamente tiempo de acción o tiempo de detección.</dt> 
<dt>Usuario: &lt; Dominio &gt; \& lt; Código &gt; </dt>
<dt>de error del usuario: Código de error &lt; Código de resultado asociado con el estado de &gt; amenaza. Valores HRESULT estándar. </dt> 
<dt>Descripción del error: &lt; Descripción del error Descripción del &gt; error.</dt>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-376">
<dt>Time: The time when the event occurred, for example when the history is purged. This parameter is not used in threat events so that there is no confusion regarding whether it is remediation time or infection time. For those, we specifically call them as Action Time or Detection Time.</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values. </dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="0e5a6-377">Identificador de evento: 1015</span><span class="sxs-lookup"><span data-stu-id="0e5a6-377">Event ID: 1015</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="0e5a6-378">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-378">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-379">
<b>MALWAREPROTECTION_BEHAVIOR_DETECTED </b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-379">
<b>MALWAREPROTECTION_BEHAVIOR_DETECTED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-380">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-380">Message:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-381">
<b>La plataforma antimalware detectó un comportamiento sospechoso.</b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-381">
<b>The antimalware platform detected suspicious behavior.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-382">Descripción:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-382">Description:</span></span>
</td>
<td >
<span data-ttu-id="0e5a6-383">Antivirus de Microsoft Defender ha detectado un comportamiento sospechoso.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-383">Microsoft Defender Antivirus has detected a suspicious behavior.</span></span><br/><span data-ttu-id="0e5a6-384">Para obtener más información, vea los artículos siguientes: </span><span class="sxs-lookup"><span data-stu-id="0e5a6-384">For more information, see the following:</span></span>
<dl><span data-ttu-id="0e5a6-385">
<dt>Nombre: &lt; Id. &gt; de</dt>
<dt>nombre de &lt; amenaza: Gravedad del id. &gt; </dt>de 
<dt> amenaza: gravedad , por &lt; &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-385">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="0e5a6-386">Bajo</span><span class="sxs-lookup"><span data-stu-id="0e5a6-386">Low</span></span></li>
<li><span data-ttu-id="0e5a6-387">Moderado</span><span class="sxs-lookup"><span data-stu-id="0e5a6-387">Moderate</span></span></li>
<li><span data-ttu-id="0e5a6-388">Alto</span><span class="sxs-lookup"><span data-stu-id="0e5a6-388">High</span></span></li>
<li><span data-ttu-id="0e5a6-389">Grave</span><span class="sxs-lookup"><span data-stu-id="0e5a6-389">Severe</span></span></li>
</ul><span data-ttu-id="0e5a6-390">
</dt>
<dt>Categoría: &lt; Descripción de &gt; categoría , por ejemplo, cualquier tipo de amenaza o malware.</dt> 
<dt>Ruta de acceso: &lt; Origen &gt; de detección</dt>de ruta de 
<dt> acceso de &lt; archivo: Origen de &gt; detección, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-390">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="0e5a6-391">Unknown</span><span class="sxs-lookup"><span data-stu-id="0e5a6-391">Unknown</span></span></li>
<li><span data-ttu-id="0e5a6-392">Equipo local</span><span class="sxs-lookup"><span data-stu-id="0e5a6-392">Local computer</span></span></li>
<li><span data-ttu-id="0e5a6-393">Recurso compartido de red</span><span class="sxs-lookup"><span data-stu-id="0e5a6-393">Network share</span></span></li>
<li><span data-ttu-id="0e5a6-394">Internet</span><span class="sxs-lookup"><span data-stu-id="0e5a6-394">Internet</span></span></li>
<li><span data-ttu-id="0e5a6-395">Tráfico entrante</span><span class="sxs-lookup"><span data-stu-id="0e5a6-395">Incoming traffic</span></span></li>
<li><span data-ttu-id="0e5a6-396">Tráfico saliente</span><span class="sxs-lookup"><span data-stu-id="0e5a6-396">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="0e5a6-397">
</dt>
<dt>Tipo de &lt; detección: Tipo de &gt; detección , por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-397">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="0e5a6-398">Heurística</span><span class="sxs-lookup"><span data-stu-id="0e5a6-398">Heuristics</span></span></li>
<li><span data-ttu-id="0e5a6-399">Generic</span><span class="sxs-lookup"><span data-stu-id="0e5a6-399">Generic</span></span></li>
<li><span data-ttu-id="0e5a6-400">Concreto</span><span class="sxs-lookup"><span data-stu-id="0e5a6-400">Concrete</span></span></li>
<li><span data-ttu-id="0e5a6-401">Firma dinámica</span><span class="sxs-lookup"><span data-stu-id="0e5a6-401">Dynamic signature</span></span></li>
</ul><span data-ttu-id="0e5a6-402">
</dt>
<dt>Origen de &lt; detección: origen de &gt; detección por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-402">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="0e5a6-403">Usuario: usuario iniciado</span><span class="sxs-lookup"><span data-stu-id="0e5a6-403">User: user initiated</span></span></li>
<li><span data-ttu-id="0e5a6-404">Sistema: sistema iniciado</span><span class="sxs-lookup"><span data-stu-id="0e5a6-404">System: system initiated</span></span></li>
<li><span data-ttu-id="0e5a6-405">En tiempo real: componente en tiempo real iniciado</span><span class="sxs-lookup"><span data-stu-id="0e5a6-405">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="0e5a6-406">IOAV: Descargas de IE y Outlook datos adjuntos de Express iniciados</span><span class="sxs-lookup"><span data-stu-id="0e5a6-406">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="0e5a6-407">NIS: sistema de inspección de red</span><span class="sxs-lookup"><span data-stu-id="0e5a6-407">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="0e5a6-408">IEPROTECT: IE - IExtensionValidation; esto protege contra controles de páginas web malintencionadas</span><span class="sxs-lookup"><span data-stu-id="0e5a6-408">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="0e5a6-409">Antimalware de inicio anticipado (ELAM).</span><span class="sxs-lookup"><span data-stu-id="0e5a6-409">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="0e5a6-410">Esto incluye malware detectado por la secuencia de arranque</span><span class="sxs-lookup"><span data-stu-id="0e5a6-410">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="0e5a6-411">Atestación remota</span><span class="sxs-lookup"><span data-stu-id="0e5a6-411">Remote attestation</span></span></li>
</ul><span data-ttu-id="0e5a6-412">Interfaz de examen antimalware (AMSI).</span><span class="sxs-lookup"><span data-stu-id="0e5a6-412">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="0e5a6-413">Se usa principalmente para proteger scripts (PS, VBS), aunque también pueden invocarse por terceros.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-413">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="0e5a6-414">Estado de </dt> 
<dt>UAC: Usuario &lt; &gt; de</dt>
<dt>estado: Dominio &lt; &gt; \& lt; Nombre &gt; </dt>del proceso de usuario: proceso en el identificador de firma
<dt> &lt; &gt; PID:</dt>
<dt>Gravedad de coincidencia de enumeración.</dt> 
<dt>Versión de firma: &lt; Versión &gt; de definición</dt>Versión del
<dt> &lt; motor: &gt; Antimalware Engine versión Fidelity</dt>
<dt>Label:</dt>Nombre del archivo de
<dt>destino: Nombre de archivo del &lt; &gt; archivo.</dt>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-414">UAC</dt>
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
<th colspan="2"><span data-ttu-id="0e5a6-415">Identificador de evento: 1116</span><span class="sxs-lookup"><span data-stu-id="0e5a6-415">Event ID: 1116</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="0e5a6-416">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-416">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-417">
<b>MALWAREPROTECTION_STATE_MALWARE_DETECTED</b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-417">
<b>MALWAREPROTECTION_STATE_MALWARE_DETECTED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-418">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-418">Message:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-419">
<b>La plataforma antimalware detectó malware u otro software potencialmente no deseado. </b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-419">
<b>The antimalware platform detected malware or other potentially unwanted software. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-420">Descripción:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-420">Description:</span></span>
</td>
<td >
<span data-ttu-id="0e5a6-421">Antivirus de Microsoft Defender ha detectado malware u otro software potencialmente no deseado.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-421">Microsoft Defender Antivirus has detected malware or other potentially unwanted software.</span></span><br/><span data-ttu-id="0e5a6-422">Para obtener más información, vea los artículos siguientes: </span><span class="sxs-lookup"><span data-stu-id="0e5a6-422">For more information, see the following:</span></span>
<dl><span data-ttu-id="0e5a6-423">
<dt>Nombre: &lt; Id. &gt; de</dt>
<dt>nombre de &lt; amenaza: Gravedad del id. &gt; </dt>de 
<dt> amenaza: gravedad , por &lt; &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-423">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="0e5a6-424">Bajo</span><span class="sxs-lookup"><span data-stu-id="0e5a6-424">Low</span></span></li>
<li><span data-ttu-id="0e5a6-425">Moderado</span><span class="sxs-lookup"><span data-stu-id="0e5a6-425">Moderate</span></span></li>
<li><span data-ttu-id="0e5a6-426">Alto</span><span class="sxs-lookup"><span data-stu-id="0e5a6-426">High</span></span></li>
<li><span data-ttu-id="0e5a6-427">Grave</span><span class="sxs-lookup"><span data-stu-id="0e5a6-427">Severe</span></span></li>
</ul><span data-ttu-id="0e5a6-428">
</dt>
<dt>Categoría: &lt; Descripción de &gt; categoría , por ejemplo, cualquier tipo de amenaza o malware.</dt> 
<dt>Ruta de acceso: &lt; Origen &gt; de detección</dt>de ruta de 
<dt> acceso de &lt; archivo: Origen de &gt; detección, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-428">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="0e5a6-429">Unknown</span><span class="sxs-lookup"><span data-stu-id="0e5a6-429">Unknown</span></span></li>
<li><span data-ttu-id="0e5a6-430">Equipo local</span><span class="sxs-lookup"><span data-stu-id="0e5a6-430">Local computer</span></span></li>
<li><span data-ttu-id="0e5a6-431">Recurso compartido de red</span><span class="sxs-lookup"><span data-stu-id="0e5a6-431">Network share</span></span></li>
<li><span data-ttu-id="0e5a6-432">Internet</span><span class="sxs-lookup"><span data-stu-id="0e5a6-432">Internet</span></span></li>
<li><span data-ttu-id="0e5a6-433">Tráfico entrante</span><span class="sxs-lookup"><span data-stu-id="0e5a6-433">Incoming traffic</span></span></li>
<li><span data-ttu-id="0e5a6-434">Tráfico saliente</span><span class="sxs-lookup"><span data-stu-id="0e5a6-434">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="0e5a6-435">
</dt>
<dt>Tipo de &lt; detección: Tipo de &gt; detección , por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-435">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="0e5a6-436">Heurística</span><span class="sxs-lookup"><span data-stu-id="0e5a6-436">Heuristics</span></span></li>
<li><span data-ttu-id="0e5a6-437">Generic</span><span class="sxs-lookup"><span data-stu-id="0e5a6-437">Generic</span></span></li>
<li><span data-ttu-id="0e5a6-438">Concreto</span><span class="sxs-lookup"><span data-stu-id="0e5a6-438">Concrete</span></span></li>
<li><span data-ttu-id="0e5a6-439">Firma dinámica</span><span class="sxs-lookup"><span data-stu-id="0e5a6-439">Dynamic signature</span></span></li>
</ul><span data-ttu-id="0e5a6-440">
</dt>
<dt>Origen de &lt; detección: origen de &gt; detección por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-440">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="0e5a6-441">Usuario: usuario iniciado</span><span class="sxs-lookup"><span data-stu-id="0e5a6-441">User: user initiated</span></span></li>
<li><span data-ttu-id="0e5a6-442">Sistema: sistema iniciado</span><span class="sxs-lookup"><span data-stu-id="0e5a6-442">System: system initiated</span></span></li>
<li><span data-ttu-id="0e5a6-443">En tiempo real: componente en tiempo real iniciado</span><span class="sxs-lookup"><span data-stu-id="0e5a6-443">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="0e5a6-444">IOAV: Descargas de IE y Outlook datos adjuntos de Express iniciados</span><span class="sxs-lookup"><span data-stu-id="0e5a6-444">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="0e5a6-445">NIS: sistema de inspección de red</span><span class="sxs-lookup"><span data-stu-id="0e5a6-445">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="0e5a6-446">IEPROTECT: IE - IExtensionValidation; esto protege contra controles de páginas web malintencionadas</span><span class="sxs-lookup"><span data-stu-id="0e5a6-446">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="0e5a6-447">Antimalware de inicio anticipado (ELAM).</span><span class="sxs-lookup"><span data-stu-id="0e5a6-447">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="0e5a6-448">Esto incluye malware detectado por la secuencia de arranque</span><span class="sxs-lookup"><span data-stu-id="0e5a6-448">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="0e5a6-449">Atestación remota</span><span class="sxs-lookup"><span data-stu-id="0e5a6-449">Remote attestation</span></span></li>
</ul><span data-ttu-id="0e5a6-450">Interfaz de examen antimalware (AMSI).</span><span class="sxs-lookup"><span data-stu-id="0e5a6-450">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="0e5a6-451">Se usa principalmente para proteger scripts (PS, VBS), aunque también pueden invocarse por terceros.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-451">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="0e5a6-452">Usuario de </dt> 
<dt>UAC: Dominio &lt; &gt; \& lt; Nombre &gt; </dt>del proceso de usuario: proceso en la versión de firma
<dt> &lt; &gt; PID:</dt>versión de
<dt> &lt; definición &gt; </dt>Versión del
<dt>motor: Antimalware Engine &lt; versión &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-452">UAC</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-453">Acción del usuario:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-453">User action:</span></span>
</td>
<td >
<span data-ttu-id="0e5a6-454">No se requiere ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-454">No action is required.</span></span> <span data-ttu-id="0e5a6-455">Antivirus de Microsoft Defender suspender y tomar medidas rutinarias en esta amenaza.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-455">Microsoft Defender Antivirus can suspend and take routine action on this threat.</span></span> <span data-ttu-id="0e5a6-456">Si desea quitar la amenaza manualmente, en la interfaz Antivirus de Microsoft Defender, haga clic en <b>Limpiar equipo</b>.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-456">If you want to remove the threat manually, in the Microsoft Defender Antivirus interface, click <b>Clean Computer</b>.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="0e5a6-457">Identificador de evento: 1117</span><span class="sxs-lookup"><span data-stu-id="0e5a6-457">Event ID: 1117</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="0e5a6-458">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-458">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-459">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_TAKEN </b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-459">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_TAKEN </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-460">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-460">Message:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-461">
<b>La plataforma antimalware realizó una acción para proteger el sistema de malware u otro software potencialmente no deseado. </b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-461">
<b>The antimalware platform performed an action to protect your system from malware or other potentially unwanted software. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-462">Descripción:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-462">Description:</span></span>
</td>
<td >
<span data-ttu-id="0e5a6-463">Antivirus de Microsoft Defender ha tomado medidas para proteger esta máquina de malware u otro software potencialmente no deseado.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-463">Microsoft Defender Antivirus has taken action to protect this machine from malware or other potentially unwanted software.</span></span><br/><span data-ttu-id="0e5a6-464">Para obtener más información, vea los artículos siguientes: </span><span class="sxs-lookup"><span data-stu-id="0e5a6-464">For more information, see the following:</span></span>
<dl><span data-ttu-id="0e5a6-465">
<dt>Nombre: &lt; Id. &gt; de</dt>
<dt>nombre de &lt; amenaza: Gravedad del id. &gt; </dt>de 
<dt> amenaza: gravedad , por &lt; &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-465">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="0e5a6-466">Bajo</span><span class="sxs-lookup"><span data-stu-id="0e5a6-466">Low</span></span></li>
<li><span data-ttu-id="0e5a6-467">Moderado</span><span class="sxs-lookup"><span data-stu-id="0e5a6-467">Moderate</span></span></li>
<li><span data-ttu-id="0e5a6-468">Alto</span><span class="sxs-lookup"><span data-stu-id="0e5a6-468">High</span></span></li>
<li><span data-ttu-id="0e5a6-469">Grave</span><span class="sxs-lookup"><span data-stu-id="0e5a6-469">Severe</span></span></li>
</ul><span data-ttu-id="0e5a6-470">
</dt>
<dt>Categoría: &lt; Descripción de &gt; categoría , por ejemplo, cualquier tipo de amenaza o malware.</dt> 
<dt>Ruta de acceso: &lt; Origen &gt; de detección</dt>de ruta de 
<dt> acceso de &lt; archivo: Origen de &gt; detección, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-470">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="0e5a6-471">Unknown</span><span class="sxs-lookup"><span data-stu-id="0e5a6-471">Unknown</span></span></li>
<li><span data-ttu-id="0e5a6-472">Equipo local</span><span class="sxs-lookup"><span data-stu-id="0e5a6-472">Local computer</span></span></li>
<li><span data-ttu-id="0e5a6-473">Recurso compartido de red</span><span class="sxs-lookup"><span data-stu-id="0e5a6-473">Network share</span></span></li>
<li><span data-ttu-id="0e5a6-474">Internet</span><span class="sxs-lookup"><span data-stu-id="0e5a6-474">Internet</span></span></li>
<li><span data-ttu-id="0e5a6-475">Tráfico entrante</span><span class="sxs-lookup"><span data-stu-id="0e5a6-475">Incoming traffic</span></span></li>
<li><span data-ttu-id="0e5a6-476">Tráfico saliente</span><span class="sxs-lookup"><span data-stu-id="0e5a6-476">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="0e5a6-477">
</dt>
<dt>Tipo de &lt; detección: Tipo de &gt; detección , por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-477">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="0e5a6-478">Heurística</span><span class="sxs-lookup"><span data-stu-id="0e5a6-478">Heuristics</span></span></li>
<li><span data-ttu-id="0e5a6-479">Generic</span><span class="sxs-lookup"><span data-stu-id="0e5a6-479">Generic</span></span></li>
<li><span data-ttu-id="0e5a6-480">Concreto</span><span class="sxs-lookup"><span data-stu-id="0e5a6-480">Concrete</span></span></li>
<li><span data-ttu-id="0e5a6-481">Firma dinámica</span><span class="sxs-lookup"><span data-stu-id="0e5a6-481">Dynamic signature</span></span></li>
</ul><span data-ttu-id="0e5a6-482">
</dt>
<dt>Origen de &lt; detección: origen de &gt; detección por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-482">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="0e5a6-483">Usuario: usuario iniciado</span><span class="sxs-lookup"><span data-stu-id="0e5a6-483">User: user initiated</span></span></li>
<li><span data-ttu-id="0e5a6-484">Sistema: sistema iniciado</span><span class="sxs-lookup"><span data-stu-id="0e5a6-484">System: system initiated</span></span></li>
<li><span data-ttu-id="0e5a6-485">En tiempo real: componente en tiempo real iniciado</span><span class="sxs-lookup"><span data-stu-id="0e5a6-485">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="0e5a6-486">IOAV: Descargas de IE y Outlook datos adjuntos de Express iniciados</span><span class="sxs-lookup"><span data-stu-id="0e5a6-486">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="0e5a6-487">NIS: sistema de inspección de red</span><span class="sxs-lookup"><span data-stu-id="0e5a6-487">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="0e5a6-488">IEPROTECT: IE - IExtensionValidation; esto protege contra controles de páginas web malintencionadas</span><span class="sxs-lookup"><span data-stu-id="0e5a6-488">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="0e5a6-489">Antimalware de inicio anticipado (ELAM).</span><span class="sxs-lookup"><span data-stu-id="0e5a6-489">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="0e5a6-490">Esto incluye malware detectado por la secuencia de arranque</span><span class="sxs-lookup"><span data-stu-id="0e5a6-490">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="0e5a6-491">Atestación remota</span><span class="sxs-lookup"><span data-stu-id="0e5a6-491">Remote attestation</span></span></li>
</ul><span data-ttu-id="0e5a6-492">Interfaz de examen antimalware (AMSI).</span><span class="sxs-lookup"><span data-stu-id="0e5a6-492">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="0e5a6-493">Se usa principalmente para proteger scripts (PS, VBS), aunque también pueden invocarse por terceros.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-493">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="0e5a6-494">Usuario de </dt> 
<dt>UAC: Dominio &lt; &gt; \& lt; Nombre &gt; </dt>
<dt>del proceso de usuario: Proceso en la &lt; acción &gt; pid:</dt>Acción , por 
<dt> &lt; &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-494">UAC</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Action: &lt;Action&gt;, for example:</span></span><ul>
<li><span data-ttu-id="0e5a6-495">Clean: el recurso se ha limpiado</span><span class="sxs-lookup"><span data-stu-id="0e5a6-495">Clean: The resource was cleaned</span></span></li>
<li><span data-ttu-id="0e5a6-496">Cuarentena: el recurso se ha puesto en cuarentena</span><span class="sxs-lookup"><span data-stu-id="0e5a6-496">Quarantine: The resource was quarantined</span></span></li>
<li><span data-ttu-id="0e5a6-497">Quitar: se eliminó el recurso</span><span class="sxs-lookup"><span data-stu-id="0e5a6-497">Remove: The resource was deleted</span></span></li>
<li><span data-ttu-id="0e5a6-498">Permitir: se permitió que el recurso se ejecutara o existiera</span><span class="sxs-lookup"><span data-stu-id="0e5a6-498">Allow: The resource was allowed to execute/exist</span></span></li>
<li><span data-ttu-id="0e5a6-499">Definido por el usuario: acción definida por el usuario que normalmente es una de esta lista de acciones que el usuario ha especificado</span><span class="sxs-lookup"><span data-stu-id="0e5a6-499">User defined: User-defined action that is normally one from this list of actions that the user has specified</span></span></li>
<li><span data-ttu-id="0e5a6-500">Sin acción: sin acción</span><span class="sxs-lookup"><span data-stu-id="0e5a6-500">No action: No action</span></span></li>
<li><span data-ttu-id="0e5a6-501">Bloquear: se bloqueó el recurso para que no se ejecutara</span><span class="sxs-lookup"><span data-stu-id="0e5a6-501">Block: The resource was blocked from executing</span></span></li>
</ul><span data-ttu-id="0e5a6-502">
</dt>
<dt>Estado de la acción: &lt; Descripción de &gt; acciones adicionales</dt>
<dt>Código de error: &lt; Código de error Código de resultado asociado con el estado de &gt; amenaza. Valores HRESULT estándar.</dt> 
<dt>Descripción del error: &lt; Descripción del error &gt; Descripción del error.</dt> 
<dt>Versión de firma: &lt; &gt;</dt>Versión de definición Versión del
<dt>motor: &lt; Antimalware Engine &gt; </dt> versión NOTA: siempre que Antivirus de Microsoft Defender, Microsoft Security Essentials, Herramienta de eliminación de software malintencionado o System Center Endpoint Protection detecte un malware, restaurará la siguiente configuración del sistema y los servicios que el malware podría haber cambiado:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-502">
</dt>
<dt>Action Status: &lt;Description of additional actions&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt> NOTE: Whenever Microsoft Defender Antivirus, Microsoft Security Essentials, Malicious Software Removal Tool, or System Center Endpoint Protection detects a malware, it will restore the following system settings and services that the malware might have changed:</span></span><ul>
<li><span data-ttu-id="0e5a6-503">Configuración predeterminada de Internet Explorer o Microsoft Edge configuración</span><span class="sxs-lookup"><span data-stu-id="0e5a6-503">Default Internet Explorer or Microsoft Edge setting</span></span></li>
<li><span data-ttu-id="0e5a6-504">Configuración del control de acceso de usuario</span><span class="sxs-lookup"><span data-stu-id="0e5a6-504">User Access Control settings</span></span></li>
<li><span data-ttu-id="0e5a6-505">Configuración de Chrome</span><span class="sxs-lookup"><span data-stu-id="0e5a6-505">Chrome settings</span></span></li>
<li><span data-ttu-id="0e5a6-506">Datos de control de arranque</span><span class="sxs-lookup"><span data-stu-id="0e5a6-506">Boot Control Data</span></span></li>
<li><span data-ttu-id="0e5a6-507">Configuración del Registro regedit y administrador de tareas</span><span class="sxs-lookup"><span data-stu-id="0e5a6-507">Regedit and Task Manager registry settings</span></span></li>
<li><span data-ttu-id="0e5a6-508">Windows Actualización, servicio de transferencia inteligente en segundo plano y servicio de llamadas de procedimiento remoto</span><span class="sxs-lookup"><span data-stu-id="0e5a6-508">Windows Update, Background Intelligent Transfer Service, and Remote Procedure Call service</span></span></li>
<li><span data-ttu-id="0e5a6-509">Windows Archivos del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="0e5a6-509">Windows Operating System files</span></span></li></ul>
<span data-ttu-id="0e5a6-510">El contexto anterior se aplica a las siguientes versiones de cliente y servidor:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-510">The above context applies to the following client and server versions:</span></span>
<table>
<tr>
<th><span data-ttu-id="0e5a6-511">Sistema operativo</span><span class="sxs-lookup"><span data-stu-id="0e5a6-511">Operating system</span></span></th>
<th><span data-ttu-id="0e5a6-512">Versión del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="0e5a6-512">Operating system version</span></span></th>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-513">Sistema operativo cliente</span><span class="sxs-lookup"><span data-stu-id="0e5a6-513">Client Operating System</span></span>
</td>
<td>
<span data-ttu-id="0e5a6-514">Windows Vista (Service Pack 1 o Service Pack 2), Windows 7 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="0e5a6-514">Windows Vista (Service Pack 1, or Service Pack 2), Windows 7 and later</span></span>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-515">Sistema operativo del servidor</span><span class="sxs-lookup"><span data-stu-id="0e5a6-515">Server Operating System</span></span>
</td>
<td>
<span data-ttu-id="0e5a6-516">Windows Server 2008, Windows Server 2008 R2, Windows Server 2012 y Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="0e5a6-516">Windows Server 2008, Windows Server 2008 R2, Windows Server 2012, and Windows Server 2016</span></span>
</td>
</tr>
</table>
</dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-517">Acción del usuario:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-517">User action:</span></span>
</td>
<td >
<span data-ttu-id="0e5a6-518">No es necesario realizar ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-518">No action is necessary.</span></span> <span data-ttu-id="0e5a6-519">Antivirus de Microsoft Defender o ha puesto en cuarentena una amenaza.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-519">Microsoft Defender Antivirus removed or quarantined a threat.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="0e5a6-520">Identificador de evento: 1118</span><span class="sxs-lookup"><span data-stu-id="0e5a6-520">Event ID: 1118</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="0e5a6-521">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-521">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-522">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-522">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-523">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-523">Message:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-524">
<b>La plataforma antimalware intentó realizar una acción para proteger el sistema de malware u otro software potencialmente no deseado, pero la acción falló. </b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-524">
<b>The antimalware platform attempted to perform an action to protect your system from malware or other potentially unwanted software, but the action failed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-525">Descripción:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-525">Description:</span></span>
</td>
<td >
<span data-ttu-id="0e5a6-526">Antivirus de Microsoft Defender ha encontrado un error no crítico al tomar medidas en malware u otro software potencialmente no deseado.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-526">Microsoft Defender Antivirus has encountered a non-critical error when taking action on malware or other potentially unwanted software.</span></span><br/><span data-ttu-id="0e5a6-527">Para obtener más información, vea los artículos siguientes: </span><span class="sxs-lookup"><span data-stu-id="0e5a6-527">For more information, see the following:</span></span>
<dl><span data-ttu-id="0e5a6-528">
<dt>Nombre: &lt; Id. &gt; de</dt>
<dt>nombre de &lt; amenaza: Gravedad del id. &gt; </dt>de 
<dt> amenaza: gravedad , por &lt; &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-528">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="0e5a6-529">Bajo</span><span class="sxs-lookup"><span data-stu-id="0e5a6-529">Low</span></span></li>
<li><span data-ttu-id="0e5a6-530">Moderado</span><span class="sxs-lookup"><span data-stu-id="0e5a6-530">Moderate</span></span></li>
<li><span data-ttu-id="0e5a6-531">Alto</span><span class="sxs-lookup"><span data-stu-id="0e5a6-531">High</span></span></li>
<li><span data-ttu-id="0e5a6-532">Grave</span><span class="sxs-lookup"><span data-stu-id="0e5a6-532">Severe</span></span></li>
</ul><span data-ttu-id="0e5a6-533">
</dt>
<dt>Categoría: &lt; Descripción de &gt; categoría , por ejemplo, cualquier tipo de amenaza o malware.</dt> 
<dt>Ruta de acceso: &lt; Origen &gt; de detección</dt>de ruta de 
<dt> acceso de &lt; archivo: Origen de &gt; detección, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-533">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="0e5a6-534">Unknown</span><span class="sxs-lookup"><span data-stu-id="0e5a6-534">Unknown</span></span></li>
<li><span data-ttu-id="0e5a6-535">Equipo local</span><span class="sxs-lookup"><span data-stu-id="0e5a6-535">Local computer</span></span></li>
<li><span data-ttu-id="0e5a6-536">Recurso compartido de red</span><span class="sxs-lookup"><span data-stu-id="0e5a6-536">Network share</span></span></li>
<li><span data-ttu-id="0e5a6-537">Internet</span><span class="sxs-lookup"><span data-stu-id="0e5a6-537">Internet</span></span></li>
<li><span data-ttu-id="0e5a6-538">Tráfico entrante</span><span class="sxs-lookup"><span data-stu-id="0e5a6-538">Incoming traffic</span></span></li>
<li><span data-ttu-id="0e5a6-539">Tráfico saliente</span><span class="sxs-lookup"><span data-stu-id="0e5a6-539">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="0e5a6-540">
</dt>
<dt>Tipo de &lt; detección: Tipo de &gt; detección , por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-540">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="0e5a6-541">Heurística</span><span class="sxs-lookup"><span data-stu-id="0e5a6-541">Heuristics</span></span></li>
<li><span data-ttu-id="0e5a6-542">Generic</span><span class="sxs-lookup"><span data-stu-id="0e5a6-542">Generic</span></span></li>
<li><span data-ttu-id="0e5a6-543">Concreto</span><span class="sxs-lookup"><span data-stu-id="0e5a6-543">Concrete</span></span></li>
<li><span data-ttu-id="0e5a6-544">Firma dinámica</span><span class="sxs-lookup"><span data-stu-id="0e5a6-544">Dynamic signature</span></span></li>
</ul><span data-ttu-id="0e5a6-545">
</dt>
<dt>Origen de &lt; detección: origen de &gt; detección por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-545">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="0e5a6-546">Usuario: usuario iniciado</span><span class="sxs-lookup"><span data-stu-id="0e5a6-546">User: user initiated</span></span></li>
<li><span data-ttu-id="0e5a6-547">Sistema: sistema iniciado</span><span class="sxs-lookup"><span data-stu-id="0e5a6-547">System: system initiated</span></span></li>
<li><span data-ttu-id="0e5a6-548">En tiempo real: componente en tiempo real iniciado</span><span class="sxs-lookup"><span data-stu-id="0e5a6-548">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="0e5a6-549">IOAV: Descargas de IE y Outlook datos adjuntos de Express iniciados</span><span class="sxs-lookup"><span data-stu-id="0e5a6-549">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="0e5a6-550">NIS: sistema de inspección de red</span><span class="sxs-lookup"><span data-stu-id="0e5a6-550">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="0e5a6-551">IEPROTECT: IE - IExtensionValidation; esto protege contra controles de páginas web malintencionadas</span><span class="sxs-lookup"><span data-stu-id="0e5a6-551">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="0e5a6-552">Antimalware de inicio anticipado (ELAM).</span><span class="sxs-lookup"><span data-stu-id="0e5a6-552">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="0e5a6-553">Esto incluye malware detectado por la secuencia de arranque</span><span class="sxs-lookup"><span data-stu-id="0e5a6-553">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="0e5a6-554">Atestación remota</span><span class="sxs-lookup"><span data-stu-id="0e5a6-554">Remote attestation</span></span></li>
</ul><span data-ttu-id="0e5a6-555">Interfaz de examen antimalware (AMSI).</span><span class="sxs-lookup"><span data-stu-id="0e5a6-555">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="0e5a6-556">Se usa principalmente para proteger scripts (PS, VBS), aunque también pueden invocarse por terceros.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-556">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="0e5a6-557">Usuario de </dt> 
<dt>UAC: Dominio &lt; &gt; \& lt; Nombre &gt; </dt>
<dt>del proceso de usuario: Proceso en la &lt; acción &gt; pid:</dt>Acción , por 
<dt> &lt; &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-557">UAC</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Action: &lt;Action&gt;, for example:</span></span><ul>
<li><span data-ttu-id="0e5a6-558">Clean: el recurso se ha limpiado</span><span class="sxs-lookup"><span data-stu-id="0e5a6-558">Clean: The resource was cleaned</span></span></li>
<li><span data-ttu-id="0e5a6-559">Cuarentena: el recurso se ha puesto en cuarentena</span><span class="sxs-lookup"><span data-stu-id="0e5a6-559">Quarantine: The resource was quarantined</span></span></li>
<li><span data-ttu-id="0e5a6-560">Quitar: se eliminó el recurso</span><span class="sxs-lookup"><span data-stu-id="0e5a6-560">Remove: The resource was deleted</span></span></li>
<li><span data-ttu-id="0e5a6-561">Permitir: se permitió que el recurso se ejecutara o existiera</span><span class="sxs-lookup"><span data-stu-id="0e5a6-561">Allow: The resource was allowed to execute/exist</span></span></li>
<li><span data-ttu-id="0e5a6-562">Definido por el usuario: acción definida por el usuario que normalmente es una de esta lista de acciones que el usuario ha especificado</span><span class="sxs-lookup"><span data-stu-id="0e5a6-562">User defined: User-defined action that is normally one from this list of actions that the user has specified</span></span></li>
<li><span data-ttu-id="0e5a6-563">Sin acción: sin acción</span><span class="sxs-lookup"><span data-stu-id="0e5a6-563">No action: No action</span></span></li>
<li><span data-ttu-id="0e5a6-564">Bloquear: se bloqueó el recurso para que no se ejecutara</span><span class="sxs-lookup"><span data-stu-id="0e5a6-564">Block: The resource was blocked from executing</span></span></li>
</ul><span data-ttu-id="0e5a6-565">
</dt>
<dt>Estado de la acción: &lt; Descripción de &gt; acciones adicionales</dt>
<dt>Código de error: &lt; Código de error Código de resultado asociado con el estado de &gt; amenaza. Valores HRESULT estándar.</dt> 
<dt>Descripción del error: &lt; Descripción del error &gt; Descripción del error.</dt> 
<dt>Versión de firma: &lt; Versión &gt; de definición</dt>
<dt>Versión del motor: &lt; Antimalware Engine versión &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-565">
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
<span data-ttu-id="0e5a6-566">Acción del usuario:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-566">User action:</span></span>
</td>
<td >
<span data-ttu-id="0e5a6-567">No es necesario realizar ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-567">No action is necessary.</span></span> <span data-ttu-id="0e5a6-568">Antivirus de Microsoft Defender no pudo completar una tarea relacionada con la corrección de malware.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-568">Microsoft Defender Antivirus failed to complete a task related to the malware remediation.</span></span> <span data-ttu-id="0e5a6-569">No se trata de un error crítico.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-569">This is not a critical failure.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="0e5a6-570">Identificador de evento: 1119</span><span class="sxs-lookup"><span data-stu-id="0e5a6-570">Event ID: 1119</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="0e5a6-571">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-571">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-572">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_CRITICALLY_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-572">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_CRITICALLY_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-573">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-573">Message:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-574">
<b>La plataforma antimalware encontró un error crítico al intentar tomar medidas en malware u otro software potencialmente no deseado. Hay más detalles en el mensaje de evento.</b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-574">
<b>The antimalware platform encountered a critical error when trying to take action on malware or other potentially unwanted software. There are more details in the event message.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-575">Descripción:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-575">Description:</span></span>
</td>
<td >
<span data-ttu-id="0e5a6-576">Antivirus de Microsoft Defender ha encontrado un error crítico al tomar medidas en malware u otro software potencialmente no deseado.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-576">Microsoft Defender Antivirus has encountered a critical error when taking action on malware or other potentially unwanted software.</span></span><br/><span data-ttu-id="0e5a6-577">Para obtener más información, vea los artículos siguientes: </span><span class="sxs-lookup"><span data-stu-id="0e5a6-577">For more information, see the following:</span></span>
<dl><span data-ttu-id="0e5a6-578">
<dt>Nombre: &lt; Id. &gt; de</dt>
<dt>nombre de &lt; amenaza: Gravedad del id. &gt; </dt>de 
<dt> amenaza: gravedad , por &lt; &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-578">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="0e5a6-579">Bajo</span><span class="sxs-lookup"><span data-stu-id="0e5a6-579">Low</span></span></li>
<li><span data-ttu-id="0e5a6-580">Moderado</span><span class="sxs-lookup"><span data-stu-id="0e5a6-580">Moderate</span></span></li>
<li><span data-ttu-id="0e5a6-581">Alto</span><span class="sxs-lookup"><span data-stu-id="0e5a6-581">High</span></span></li>
<li><span data-ttu-id="0e5a6-582">Grave</span><span class="sxs-lookup"><span data-stu-id="0e5a6-582">Severe</span></span></li>
</ul><span data-ttu-id="0e5a6-583">
</dt>
<dt>Categoría: &lt; Descripción de &gt; categoría , por ejemplo, cualquier tipo de amenaza o malware.</dt> 
<dt>Ruta de acceso: &lt; Origen &gt; de detección</dt>de ruta de 
<dt> acceso de &lt; archivo: Origen de &gt; detección, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-583">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="0e5a6-584">Unknown</span><span class="sxs-lookup"><span data-stu-id="0e5a6-584">Unknown</span></span></li>
<li><span data-ttu-id="0e5a6-585">Equipo local</span><span class="sxs-lookup"><span data-stu-id="0e5a6-585">Local computer</span></span></li>
<li><span data-ttu-id="0e5a6-586">Recurso compartido de red</span><span class="sxs-lookup"><span data-stu-id="0e5a6-586">Network share</span></span></li>
<li><span data-ttu-id="0e5a6-587">Internet</span><span class="sxs-lookup"><span data-stu-id="0e5a6-587">Internet</span></span></li>
<li><span data-ttu-id="0e5a6-588">Tráfico entrante</span><span class="sxs-lookup"><span data-stu-id="0e5a6-588">Incoming traffic</span></span></li>
<li><span data-ttu-id="0e5a6-589">Tráfico saliente</span><span class="sxs-lookup"><span data-stu-id="0e5a6-589">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="0e5a6-590">
</dt>
<dt>Tipo de &lt; detección: Tipo de &gt; detección , por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-590">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="0e5a6-591">Heurística</span><span class="sxs-lookup"><span data-stu-id="0e5a6-591">Heuristics</span></span></li>
<li><span data-ttu-id="0e5a6-592">Generic</span><span class="sxs-lookup"><span data-stu-id="0e5a6-592">Generic</span></span></li>
<li><span data-ttu-id="0e5a6-593">Concreto</span><span class="sxs-lookup"><span data-stu-id="0e5a6-593">Concrete</span></span></li>
<li><span data-ttu-id="0e5a6-594">Firma dinámica</span><span class="sxs-lookup"><span data-stu-id="0e5a6-594">Dynamic signature</span></span></li>
</ul><span data-ttu-id="0e5a6-595">
</dt>
<dt>Origen de &lt; detección: origen de &gt; detección por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-595">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="0e5a6-596">Usuario: usuario iniciado</span><span class="sxs-lookup"><span data-stu-id="0e5a6-596">User: user initiated</span></span></li>
<li><span data-ttu-id="0e5a6-597">Sistema: sistema iniciado</span><span class="sxs-lookup"><span data-stu-id="0e5a6-597">System: system initiated</span></span></li>
<li><span data-ttu-id="0e5a6-598">En tiempo real: componente en tiempo real iniciado</span><span class="sxs-lookup"><span data-stu-id="0e5a6-598">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="0e5a6-599">IOAV: Descargas de IE y Outlook datos adjuntos de Express iniciados</span><span class="sxs-lookup"><span data-stu-id="0e5a6-599">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="0e5a6-600">NIS: sistema de inspección de red</span><span class="sxs-lookup"><span data-stu-id="0e5a6-600">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="0e5a6-601">IEPROTECT: IE - IExtensionValidation; esto protege contra controles de páginas web malintencionadas</span><span class="sxs-lookup"><span data-stu-id="0e5a6-601">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="0e5a6-602">Antimalware de inicio anticipado (ELAM).</span><span class="sxs-lookup"><span data-stu-id="0e5a6-602">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="0e5a6-603">Esto incluye malware detectado por la secuencia de arranque</span><span class="sxs-lookup"><span data-stu-id="0e5a6-603">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="0e5a6-604">Atestación remota</span><span class="sxs-lookup"><span data-stu-id="0e5a6-604">Remote attestation</span></span></li>
</ul><span data-ttu-id="0e5a6-605">Interfaz de examen antimalware (AMSI).</span><span class="sxs-lookup"><span data-stu-id="0e5a6-605">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="0e5a6-606">Se usa principalmente para proteger scripts (PS, VBS), aunque también pueden invocarse por terceros.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-606">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="0e5a6-607">Usuario de </dt> 
<dt>UAC: Dominio &lt; &gt; \& lt; Nombre &gt; </dt>
<dt>del proceso de usuario: Proceso en la &lt; acción &gt; pid:</dt>Acción , por 
<dt> &lt; &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-607">UAC</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Action: &lt;Action&gt;, for example:</span></span><ul>
<li><span data-ttu-id="0e5a6-608">Clean: el recurso se ha limpiado</span><span class="sxs-lookup"><span data-stu-id="0e5a6-608">Clean: The resource was cleaned</span></span></li>
<li><span data-ttu-id="0e5a6-609">Cuarentena: el recurso se ha puesto en cuarentena</span><span class="sxs-lookup"><span data-stu-id="0e5a6-609">Quarantine: The resource was quarantined</span></span></li>
<li><span data-ttu-id="0e5a6-610">Quitar: se eliminó el recurso</span><span class="sxs-lookup"><span data-stu-id="0e5a6-610">Remove: The resource was deleted</span></span></li>
<li><span data-ttu-id="0e5a6-611">Permitir: se permitió que el recurso se ejecutara o existiera</span><span class="sxs-lookup"><span data-stu-id="0e5a6-611">Allow: The resource was allowed to execute/exist</span></span></li>
<li><span data-ttu-id="0e5a6-612">Definido por el usuario: acción definida por el usuario que normalmente es una de esta lista de acciones que el usuario ha especificado</span><span class="sxs-lookup"><span data-stu-id="0e5a6-612">User defined: User-defined action that is normally one from this list of actions that the user has specified</span></span></li>
<li><span data-ttu-id="0e5a6-613">Sin acción: sin acción</span><span class="sxs-lookup"><span data-stu-id="0e5a6-613">No action: No action</span></span></li>
<li><span data-ttu-id="0e5a6-614">Bloquear: se bloqueó el recurso para que no se ejecutara</span><span class="sxs-lookup"><span data-stu-id="0e5a6-614">Block: The resource was blocked from executing</span></span></li>
</ul><span data-ttu-id="0e5a6-615">
</dt>
<dt>Estado de la acción: &lt; Descripción de &gt; acciones adicionales</dt>
<dt>Código de error: &lt; Código de error Código de resultado asociado con el estado de &gt; amenaza. Valores HRESULT estándar.</dt> 
<dt>Descripción del error: &lt; Descripción del error &gt; Descripción del error.</dt> 
<dt>Versión de firma: &lt; Versión &gt; de definición</dt>
<dt>Versión del motor: &lt; Antimalware Engine versión &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-615">
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
<span data-ttu-id="0e5a6-616">Acción del usuario:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-616">User action:</span></span>
</td>
<td >
<span data-ttu-id="0e5a6-617">El Antivirus de Microsoft Defender encontró este error debido a problemas críticos.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-617">The Microsoft Defender Antivirus client encountered this error due to critical issues.</span></span> <span data-ttu-id="0e5a6-618">Es posible que el extremo no esté protegido.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-618">The endpoint might not be protected.</span></span> <span data-ttu-id="0e5a6-619">Revise la descripción del error y, a continuación, siga los <b>pasos de acción de usuario</b> pertinentes a continuación.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-619">Review the error description then follow the relevant <b>User action</b> steps below.</span></span>
<table>
<tr>
<th><span data-ttu-id="0e5a6-620">Acción</span><span class="sxs-lookup"><span data-stu-id="0e5a6-620">Action</span></span></th>
<th><span data-ttu-id="0e5a6-621">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="0e5a6-621">User action</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="0e5a6-622">
<b>Quitar</b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-622">
<b>Remove</b>
</span></span></td>
<td>
<span data-ttu-id="0e5a6-623">Actualice las definiciones y compruebe que la eliminación se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-623">Update the definitions then verify that the removal was successful.</span></span>
</td>
</tr>
<tr>
<td><span data-ttu-id="0e5a6-624">
<b>Limpiar</b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-624">
<b>Clean</b>
</span></span></td>
<td>
<span data-ttu-id="0e5a6-625">Actualice las definiciones y compruebe que la corrección se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-625">Update the definitions then verify that the remediation was successful.</span></span>
</td>
</tr>
<tr>
<td><span data-ttu-id="0e5a6-626">
<b>Cuarentena</b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-626">
<b>Quarantine</b>
</span></span></td>
<td>
<span data-ttu-id="0e5a6-627">Actualice las definiciones y compruebe que el usuario tiene permiso para acceder a los recursos necesarios.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-627">Update the definitions and verify that the user has permission to access the necessary resources.</span></span>
</td>
</tr>
<tr>
<td><span data-ttu-id="0e5a6-628">
<b>Permitir</b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-628">
<b>Allow</b>
</span></span></td>
<td>
<span data-ttu-id="0e5a6-629">Compruebe que el usuario tiene permiso para obtener acceso a los recursos necesarios.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-629">Verify that the user has permission to access the necessary resources.</span></span>
</td>
</tr>
</table>

<span data-ttu-id="0e5a6-630">Si este evento persiste:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-630">If this event persists:</span></span><ol>
<li><span data-ttu-id="0e5a6-631">Vuelva a ejecutar el examen.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-631">Run the scan again.</span></span></li>
<li><span data-ttu-id="0e5a6-632">Si se produce un error de la misma manera, vaya <b></b> al sitio de soporte técnico de <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft</a>, escriba el número de error en el cuadro Buscar para buscar el código de error.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-632">If it fails in the same way, go to the <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft Support site</a>, enter the error number in the <b>Search</b> box to look for the error code.</span></span></li>
<li><span data-ttu-id="0e5a6-633">Contactar al <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Soporte técnico de Microsoft</a>.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-633">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="0e5a6-634">Identificador de evento: 1120</span><span class="sxs-lookup"><span data-stu-id="0e5a6-634">Event ID: 1120</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="0e5a6-635">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-635">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-636">
<b>MALWAREPROTECTION_THREAT_HASH</b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-636">
<b>MALWAREPROTECTION_THREAT_HASH</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-637">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-637">Message:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-638">
<b>Antivirus de Microsoft Defender ha deducido los hashes de un recurso de amenaza.</b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-638">
<b>Microsoft Defender Antivirus has deduced the hashes for a threat resource.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-639">Descripción:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-639">Description:</span></span>
</td>
<td >
<span data-ttu-id="0e5a6-640">Antivirus de Microsoft Defender cliente está en funcionamiento en un estado correcto.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-640">Microsoft Defender Antivirus client is up and running in a healthy state.</span></span>
<dl><span data-ttu-id="0e5a6-641">
<dt>Versión actual de la plataforma: &lt; Ruta de &gt; acceso de</dt>recurso de amenaza de la
<dt> &lt; &gt; versión</dt>actual de la plataforma:
<dt>hashes de ruta: &lt; hashes &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-641">
<dt>Current Platform Version: &lt;Current platform version&gt;</dt>
<dt>Threat Resource Path: &lt;Path&gt;</dt>
<dt>Hashes: &lt;Hashes&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td></td>
<td >
<div class="alert"><span data-ttu-id="0e5a6-642"><b>Nota: Este evento solo se registrará si se establece la siguiente directiva: <b>ThreatFileHashLogging sin signo</b>.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-642"><b>Note: This event will only be logged if the following policy is set: <b>ThreatFileHashLogging     unsigned</b>.</span></span></div>
<div> </div>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="0e5a6-643">Identificador de evento: 1150</span><span class="sxs-lookup"><span data-stu-id="0e5a6-643">Event ID: 1150</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="0e5a6-644">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-644">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-645">
<b>MALWAREPROTECTION_SERVICE_HEALTHY</b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-645">
<b>MALWAREPROTECTION_SERVICE_HEALTHY</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-646">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-646">Message:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-647">
<b>Si la plataforma antimalware notifica el estado a una plataforma de supervisión, este evento indica que la plataforma antimalware se está ejecutando y en un estado correcto. </b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-647">
<b>If your antimalware platform reports status to a monitoring platform, this event indicates that the antimalware platform is running and in a healthy state. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-648">Descripción:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-648">Description:</span></span>
</td>
<td >
<span data-ttu-id="0e5a6-649">Antivirus de Microsoft Defender cliente está en funcionamiento en un estado correcto.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-649">Microsoft Defender Antivirus client is up and running in a healthy state.</span></span>
<dl><span data-ttu-id="0e5a6-650">
<dt>Versión de la plataforma: &lt; Versión de &gt; la plataforma actual</dt>Versión de firma: Versión del motor
<dt> &lt; de &gt; </dt>la versión de definición:
<dt>Antimalware Engine &lt; versión &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-650">
<dt>Platform Version: &lt;Current platform version&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-651">Acción del usuario:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-651">User action:</span></span>
</td>
<td >
<span data-ttu-id="0e5a6-652">No es necesario realizar ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-652">No action is necessary.</span></span> <span data-ttu-id="0e5a6-653">El Antivirus de Microsoft Defender está en buen estado.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-653">The Microsoft Defender Antivirus client is in a healthy state.</span></span> <span data-ttu-id="0e5a6-654">Este evento se notifica cada hora.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-654">This event is reported on an hourly basis.</span></span>
</td>
</tr>

<tr>
<th colspan="2"><span data-ttu-id="0e5a6-655">Identificador de evento: 1151</span><span class="sxs-lookup"><span data-stu-id="0e5a6-655">Event ID: 1151</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="0e5a6-656">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-656">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-657">
<b>MALWAREPROTECTION_SERVICE_HEALTH_REPORT</b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-657">
<b>MALWAREPROTECTION_SERVICE_HEALTH_REPORT</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-658">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-658">Message:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-659">
<b>Endpoint Protection de estado del cliente (hora UTC)</b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-659">
<b>Endpoint Protection client health report (time in UTC) </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-660">Descripción:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-660">Description:</span></span>
</td>
<td >
<span data-ttu-id="0e5a6-661">Informe de estado del cliente antivirus.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-661">Antivirus client health report.</span></span>
<dl><span data-ttu-id="0e5a6-662">
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
<dt></span><span class="sxs-lookup"><span data-stu-id="0e5a6-662">
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

<tr><span data-ttu-id="0e5a6-663">
<th colspan="2">Identificador de evento: 2000</span><span class="sxs-lookup"><span data-stu-id="0e5a6-663">
<th colspan="2">Event ID: 2000</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="0e5a6-664">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-664">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-665">
<b>MALWAREPROTECTION_SIGNATURE_UPDATED </b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-665">
<b>MALWAREPROTECTION_SIGNATURE_UPDATED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-666">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-666">Message:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-667">
<b>Las definiciones de antimalware se actualizaron correctamente. </b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-667">
<b>The antimalware definitions updated successfully. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-668">Descripción:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-668">Description:</span></span>
</td>
<td >
<span data-ttu-id="0e5a6-669">Se ha actualizado la versión de firma del antivirus.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-669">Antivirus signature version has been updated.</span></span>
<dl><span data-ttu-id="0e5a6-670">
<dt>Versión de firma actual: &lt; Versión de &gt; firma actual</dt>
<dt>Versión de firma anterior: Versión de firma &lt; anterior &gt; </dt>Tipo de 
<dt> firma: Tipo de firma , por &lt; &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-670">
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Previous Signature Version: &lt;Previous signature version&gt;</dt>
<dt>Signature Type: &lt;Signature type&gt;, for example:</span></span> <ul>
<li><span data-ttu-id="0e5a6-671">Antivirus</span><span class="sxs-lookup"><span data-stu-id="0e5a6-671">Antivirus</span></span></li>
<li><span data-ttu-id="0e5a6-672">Antispyware</span><span class="sxs-lookup"><span data-stu-id="0e5a6-672">Antispyware</span></span></li>
<li><span data-ttu-id="0e5a6-673">Antimalware</span><span class="sxs-lookup"><span data-stu-id="0e5a6-673">Antimalware</span></span></li>
<li><span data-ttu-id="0e5a6-674">Sistema de inspección de red</span><span class="sxs-lookup"><span data-stu-id="0e5a6-674">Network Inspection System</span></span></li>
</ul><span data-ttu-id="0e5a6-675">
</dt>
<dt>Tipo de actualización: &lt; Tipo de &gt; actualización , Completo o Delta.</dt> 
<dt>Usuario: &lt; Dominio &gt; \& lt; Versión &gt; </dt>
<dt>del motor actual del usuario: versión actual del &lt; &gt; motor</dt>Versión anterior del
<dt>motor: Versión anterior del &lt; motor &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-675">
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
<span data-ttu-id="0e5a6-676">Acción del usuario:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-676">User action:</span></span>
</td>
<td >
<span data-ttu-id="0e5a6-677">No es necesario realizar ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-677">No action is necessary.</span></span> <span data-ttu-id="0e5a6-678">El Antivirus de Microsoft Defender está en buen estado.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-678">The Microsoft Defender Antivirus client is in a healthy state.</span></span> <span data-ttu-id="0e5a6-679">Este evento se notifica cuando las firmas se actualizan correctamente.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-679">This event is reported when signatures are successfully updated.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="0e5a6-680">Identificador de evento: 2001</span><span class="sxs-lookup"><span data-stu-id="0e5a6-680">Event ID: 2001</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="0e5a6-681">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-681">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-682">
<b>MALWAREPROTECTION_SIGNATURE_UPDATE_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-682">
<b>MALWAREPROTECTION_SIGNATURE_UPDATE_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-683">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-683">Message:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-684">
<b>Error en la actualización de inteligencia de seguridad. </b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-684">
<b>The security intelligence update failed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-685">Descripción:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-685">Description:</span></span>
</td>
<td >
<span data-ttu-id="0e5a6-686">Antivirus de Microsoft Defender ha encontrado un error al intentar actualizar firmas.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-686">Microsoft Defender Antivirus has encountered an error trying to update signatures.</span></span>
<dl><span data-ttu-id="0e5a6-687">
<dt>Nueva versión de inteligencia de seguridad: &lt; Nuevo número &gt; de versión</dt>
<dt>Versión de inteligencia de seguridad anterior: Versión &lt; &gt; anterior</dt>Update 
<dt> Source: Update source , por &lt; &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-687">
<dt>New security intelligence version: &lt;New version number&gt;</dt>
<dt>Previous security intelligence version: &lt;Previous version&gt;</dt>
<dt>Update Source: &lt;Update source&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="0e5a6-688">Carpeta de actualización de inteligencia de seguridad</span><span class="sxs-lookup"><span data-stu-id="0e5a6-688">Security intelligence update folder</span></span></li>
<li><span data-ttu-id="0e5a6-689">Servidor de actualización de inteligencia de seguridad interna</span><span class="sxs-lookup"><span data-stu-id="0e5a6-689">Internal security intelligence update server</span></span></li>
<li><span data-ttu-id="0e5a6-690">Microsoft Update Server</span><span class="sxs-lookup"><span data-stu-id="0e5a6-690">Microsoft Update Server</span></span></li>
<li><span data-ttu-id="0e5a6-691">Compartir archivos</span><span class="sxs-lookup"><span data-stu-id="0e5a6-691">File share</span></span></li>
<li><span data-ttu-id="0e5a6-692">Centro de protección contra malware de Microsoft (MMPC)</span><span class="sxs-lookup"><span data-stu-id="0e5a6-692">Microsoft Malware Protection Center (MMPC)</span></span></li>
</ul><span data-ttu-id="0e5a6-693">
</dt>
<dt>Update Stage: &lt; Update stage , por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-693">
</dt>
<dt>Update Stage: &lt;Update stage&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="0e5a6-694">Búsqueda</span><span class="sxs-lookup"><span data-stu-id="0e5a6-694">Search</span></span></li>
<li><span data-ttu-id="0e5a6-695">Descargar</span><span class="sxs-lookup"><span data-stu-id="0e5a6-695">Download</span></span></li>
<li><span data-ttu-id="0e5a6-696">Instalar</span><span class="sxs-lookup"><span data-stu-id="0e5a6-696">Install</span></span></li>
</ul><span data-ttu-id="0e5a6-697">
</dt>Ruta de acceso de origen: nombre del recurso compartido de archivos para convención de nomenclatura universal (UNC), nombre del servidor 
<dt>para Windows Server Update Services (WSUS)/Microsoft Update/ADL.</dt> 
<dt> Tipo de firma: &lt; Tipo de firma , por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-697">
</dt>
<dt>Source Path: File share name for Universal Naming Convention (UNC), server name for Windows Server Update Services (WSUS)/Microsoft Update/ADL.</dt>
<dt>Signature Type: &lt;Signature type&gt;, for example:</span></span> <ul>
<li><span data-ttu-id="0e5a6-698">Antivirus</span><span class="sxs-lookup"><span data-stu-id="0e5a6-698">Antivirus</span></span></li>
<li><span data-ttu-id="0e5a6-699">Antispyware</span><span class="sxs-lookup"><span data-stu-id="0e5a6-699">Antispyware</span></span></li>
<li><span data-ttu-id="0e5a6-700">Antimalware</span><span class="sxs-lookup"><span data-stu-id="0e5a6-700">Antimalware</span></span></li>
<li><span data-ttu-id="0e5a6-701">Sistema de inspección de red</span><span class="sxs-lookup"><span data-stu-id="0e5a6-701">Network Inspection System</span></span></li>
</ul><span data-ttu-id="0e5a6-702">
</dt>
<dt>Tipo de actualización: &lt; Tipo de &gt; actualización , Completo o Delta.</dt> 
<dt>Usuario: &lt; Dominio &gt; \& lt; Versión &gt; </dt>
<dt>actual del motor del usuario: &lt; &gt; Versión</dt>actual del motor Versión anterior del motor: Versión
<dt> &lt; anterior &gt; </dt>del motor Código de error: Código de error Código de
<dt>resultado asociado con el estado de la &lt; &gt; amenaza. Valores HRESULT estándar.</dt> 
<dt>Descripción del error: &lt; Descripción del error &gt; Descripción del error.</dt>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-702">
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
<span data-ttu-id="0e5a6-703">Acción del usuario:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-703">User action:</span></span>
</td>
<td >
<span data-ttu-id="0e5a6-704">Este error se produce cuando hay un problema al actualizar definiciones.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-704">This error occurs when there is a problem updating definitions.</span></span>
<span data-ttu-id="0e5a6-705">Para solucionar este evento:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-705">To troubleshoot this event:</span></span>
<ol>
<li><span data-ttu-id="0e5a6-706"><a href="manage-updates-baselines-microsoft-defender-antivirus.md" data-raw-source="[Update definitions](manage-updates-baselines-microsoft-defender-antivirus.md)">Actualice las definiciones</a> y fuerza un nuevo análisis directamente en el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-706"><a href="manage-updates-baselines-microsoft-defender-antivirus.md" data-raw-source="[Update definitions](manage-updates-baselines-microsoft-defender-antivirus.md)">Update definitions</a> and force a rescan directly on the endpoint.</span></span></li>
<li><span data-ttu-id="0e5a6-707">Revisa las entradas del archivo %Windir%\WindowsUpdate.log para obtener más información sobre este error.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-707">Review the entries in the %Windir%\WindowsUpdate.log file for more information about this error.</span></span></li>
<li><span data-ttu-id="0e5a6-708">Contactar al <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Soporte técnico de Microsoft</a>.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-708">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="0e5a6-709">Identificador de evento: 2002</span><span class="sxs-lookup"><span data-stu-id="0e5a6-709">Event ID: 2002</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="0e5a6-710">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-710">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-711">
<b>MALWAREPROTECTION_ENGINE_UPDATED</b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-711">
<b>MALWAREPROTECTION_ENGINE_UPDATED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-712">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-712">Message:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-713">
<b>El motor de antimalware se actualizó correctamente. </b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-713">
<b>The antimalware engine updated successfully. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-714">Descripción:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-714">Description:</span></span>
</td>
<td >
<span data-ttu-id="0e5a6-715">Antivirus de Microsoft Defender versión del motor se ha actualizado.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-715">Microsoft Defender Antivirus engine version has been updated.</span></span>
<dl><span data-ttu-id="0e5a6-716">
<dt>Versión actual del motor: &lt; Versión actual &gt; del motor</dt>
<dt>Versión anterior del motor: &lt; &gt; Versión anterior</dt>del motor Tipo de motor: Tipo de motor , motor antimalware o motor del sistema de inspección de
<dt> &lt; &gt; red.</dt> 
<dt>Usuario: &lt; Dominio &gt; \& lt; Usuario &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-716">
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Previous Engine Version: &lt;Previous engine version&gt;</dt>
<dt>Engine Type: &lt;Engine type&gt;, either antimalware engine or Network Inspection System engine.</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-717">Acción del usuario:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-717">User action:</span></span>
</td>
<td >
<span data-ttu-id="0e5a6-718">No es necesario realizar ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-718">No action is necessary.</span></span> <span data-ttu-id="0e5a6-719">El Antivirus de Microsoft Defender está en buen estado.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-719">The Microsoft Defender Antivirus client is in a healthy state.</span></span> <span data-ttu-id="0e5a6-720">Este evento se notifica cuando el motor de antimalware se actualiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-720">This event is reported when the antimalware engine is successfully updated.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="0e5a6-721">Identificador de evento: 2003</span><span class="sxs-lookup"><span data-stu-id="0e5a6-721">Event ID: 2003</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="0e5a6-722">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-722">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-723">
<b>MALWAREPROTECTION_ENGINE_UPDATE_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-723">
<b>MALWAREPROTECTION_ENGINE_UPDATE_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-724">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-724">Message:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-725">
<b>Error en la actualización del motor de antimalware. </b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-725">
<b>The antimalware engine update failed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-726">Descripción:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-726">Description:</span></span>
</td>
<td >
<span data-ttu-id="0e5a6-727">Antivirus de Microsoft Defender ha encontrado un error al intentar actualizar el motor.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-727">Microsoft Defender Antivirus has encountered an error trying to update the engine.</span></span>
<dl><span data-ttu-id="0e5a6-728">
<dt>Nueva versión del motor:</dt>
<dt>Versión anterior del motor: &lt; &gt; </dt>Versión anterior del motor Tipo de motor: Tipo de motor , motor antimalware o motor del sistema de inspección de
<dt> &lt; &gt; red.</dt> 
<dt>Usuario: &lt; Dominio &gt; \& lt; Código &gt; </dt>
<dt>de error del usuario: Código de error &lt; Código de resultado asociado con el estado de &gt; amenaza. Valores HRESULT estándar.</dt> 
<dt>Descripción del error: &lt; Descripción del error &gt; Descripción del error.</dt>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-728">
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
<span data-ttu-id="0e5a6-729">Acción del usuario:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-729">User action:</span></span>
</td>
<td >
<span data-ttu-id="0e5a6-730">Error Antivirus de Microsoft Defender actualización de cliente.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-730">The Microsoft Defender Antivirus client update failed.</span></span> <span data-ttu-id="0e5a6-731">Este evento se produce cuando el cliente no se actualiza.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-731">This event occurs when the client fails to update itself.</span></span> <span data-ttu-id="0e5a6-732">Este evento suele deberse a una interrupción en la conectividad de red durante una actualización.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-732">This event is usually due to an interruption in network connectivity during an update.</span></span>
<span data-ttu-id="0e5a6-733">Para solucionar este evento:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-733">To troubleshoot this event:</span></span>
<ol>
<li><span data-ttu-id="0e5a6-734"><a href="manage-updates-baselines-microsoft-defender-antivirus.md" data-raw-source="[Update definitions](manage-updates-baselines-microsoft-defender-antivirus.md)">Actualice las definiciones</a> y fuerza un nuevo análisis directamente en el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-734"><a href="manage-updates-baselines-microsoft-defender-antivirus.md" data-raw-source="[Update definitions](manage-updates-baselines-microsoft-defender-antivirus.md)">Update definitions</a> and force a rescan directly on the endpoint.</span></span></li>
<li><span data-ttu-id="0e5a6-735">Contactar al <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Soporte técnico de Microsoft</a>.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-735">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="0e5a6-736">Identificador de evento: 2004</span><span class="sxs-lookup"><span data-stu-id="0e5a6-736">Event ID: 2004</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="0e5a6-737">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-737">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-738">
<b>MALWAREPROTECTION_SIGNATURE_REVERSION</b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-738">
<b>MALWAREPROTECTION_SIGNATURE_REVERSION</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-739">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-739">Message:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-740">
<b>Hubo un problema al cargar definiciones de antimalware. El motor de antimalware intentará cargar el último conjunto de definiciones bien conocido.</b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-740">
<b>There was a problem loading antimalware definitions. The antimalware engine will attempt to load the last-known good set of definitions.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-741">Descripción:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-741">Description:</span></span>
</td>
<td >
<span data-ttu-id="0e5a6-742">Antivirus de Microsoft Defender ha encontrado un error al intentar cargar firmas e intentará volver a un conjunto de firmas conocido.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-742">Microsoft Defender Antivirus has encountered an error trying to load signatures and will attempt reverting back to a known-good set of signatures.</span></span>
<dl><span data-ttu-id="0e5a6-743">
<dt>Firmas intentadas:</dt>
<dt>Código de error: Código de error Código de resultado asociado con el estado de &lt; &gt; amenaza. Valores HRESULT estándar.</dt> 
<dt>Descripción del error: &lt; Descripción del error &gt; Descripción del error.</dt> 
<dt>Versión de firma: &lt; Versión &gt; de definición</dt>
<dt>Versión del motor: &lt; versión &gt; del motor antimalware</dt>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-743">
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
<span data-ttu-id="0e5a6-744">Acción del usuario:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-744">User action:</span></span>
</td>
<td >
<span data-ttu-id="0e5a6-745">El Antivirus de Microsoft Defender intentó descargar e instalar el archivo de definiciones más reciente y falló.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-745">The Microsoft Defender Antivirus client attempted to download and install the latest definitions file and failed.</span></span> <span data-ttu-id="0e5a6-746">Este error puede producirse cuando el cliente encuentra un error al intentar cargar las definiciones o si el archivo está dañado.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-746">This error can occur when the client encounters an error while trying to load the definitions, or if the file is corrupt.</span></span> <span data-ttu-id="0e5a6-747">Antivirus de Microsoft Defender intentará volver a un conjunto de definiciones conocido.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-747">Microsoft Defender Antivirus will attempt to revert back to a known-good set of definitions.</span></span>
<span data-ttu-id="0e5a6-748">Para solucionar este evento:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-748">To troubleshoot this event:</span></span>
<ol>
<li><span data-ttu-id="0e5a6-749">Reinicie el equipo e inténtelo de nuevo.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-749">Restart the computer and try again.</span></span></li>
<li><span data-ttu-id="0e5a6-750">Descargue las definiciones más recientes del <a href="https://aka.ms/wdsi">Inteligencia de seguridad de Microsoft sitio</a>.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-750">Download the latest definitions from the <a href="https://aka.ms/wdsi">Microsoft Security Intelligence site</a>.</span></span>
<span data-ttu-id="0e5a6-751">Nota: El tamaño del archivo de definiciones descargado del sitio puede superar los 60 MB y no debe usarse como solución a largo plazo para actualizar definiciones.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-751">Note: The size of the definitions file downloaded from the site can exceed 60 MB and should not be used as a long-term solution for updating definitions.</span></span>
</li>
<li><span data-ttu-id="0e5a6-752">Contactar al <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Soporte técnico de Microsoft</a>.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-752">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="0e5a6-753">Identificador de evento: 2005</span><span class="sxs-lookup"><span data-stu-id="0e5a6-753">Event ID: 2005</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="0e5a6-754">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-754">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-755">
<b>MALWAREPROTECTION_ENGINE_UPDATE_PLATFORMOUTOFDATE</b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-755">
<b>MALWAREPROTECTION_ENGINE_UPDATE_PLATFORMOUTOFDATE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-756">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-756">Message:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-757">
<b>El motor de antimalware no se pudo cargar porque la plataforma antimalware no está actualizada. La plataforma antimalware cargará el último motor antimalware bueno conocido e intentará actualizarlo.</b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-757">
<b>The antimalware engine failed to load because the antimalware platform is out of date. The antimalware platform will load the last-known good antimalware engine and attempt to update.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-758">Descripción:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-758">Description:</span></span>
</td>
<td >
<span data-ttu-id="0e5a6-759">Antivirus de Microsoft Defender no se pudo cargar el motor de antimalware porque no se admite la versión actual de la plataforma.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-759">Microsoft Defender Antivirus could not load antimalware engine because current platform version is not supported.</span></span> <span data-ttu-id="0e5a6-760">Antivirus de Microsoft Defender volverá al último motor conocido y se intenta actualizar la plataforma.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-760">Microsoft Defender Antivirus will revert back to the last known-good engine and a platform update will be attempted.</span></span>
<dl><span data-ttu-id="0e5a6-761">
<dt>Versión actual de la plataforma: &lt; versión actual de la plataforma&gt;</dt>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-761">
<dt>Current Platform Version: &lt;Current platform version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="0e5a6-762">Identificador de evento: 2006</span><span class="sxs-lookup"><span data-stu-id="0e5a6-762">Event ID: 2006</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="0e5a6-763">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-763">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-764">
<b>MALWAREPROTECTION_PLATFORM_UPDATE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-764">
<b>MALWAREPROTECTION_PLATFORM_UPDATE_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-765">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-765">Message:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-766">
<b>Error en la actualización de la plataforma. </b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-766">
<b>The platform update failed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-767">Descripción:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-767">Description:</span></span>
</td>
<td >
<span data-ttu-id="0e5a6-768">Antivirus de Microsoft Defender ha encontrado un error al intentar actualizar la plataforma.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-768">Microsoft Defender Antivirus has encountered an error trying to update the platform.</span></span>
<dl><span data-ttu-id="0e5a6-769">
<dt>Versión actual de la plataforma: &lt; Versión actual &gt; de la plataforma</dt>
<dt>Código de error: Código de error &lt; Código de resultado asociado con el estado de &gt; amenaza. Valores HRESULT estándar.</dt> 
<dt>Descripción del error: &lt; Descripción del error &gt; Descripción del error.</dt>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-769">
<dt>Current Platform Version: &lt;Current platform version&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="0e5a6-770">Identificador de evento: 2007</span><span class="sxs-lookup"><span data-stu-id="0e5a6-770">Event ID: 2007</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="0e5a6-771">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-771">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-772">
<b>MALWAREPROTECTION_PLATFORM_ALMOSTOUTOFDATE</b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-772">
<b>MALWAREPROTECTION_PLATFORM_ALMOSTOUTOFDATE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-773">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-773">Message:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-774">
<b>La plataforma pronto estará des actualizada. Descargue la plataforma más reciente para mantener la protección actualizada.</b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-774">
<b>The platform will soon be out of date. Download the latest platform to maintain up-to-date protection.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-775">Descripción:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-775">Description:</span></span>
</td>
<td >
<span data-ttu-id="0e5a6-776">Antivirus de Microsoft Defender pronto necesitará una versión de plataforma más reciente para admitir versiones futuras del motor de antimalware.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-776">Microsoft Defender Antivirus will soon require a newer platform version to support future versions of the antimalware engine.</span></span> <span data-ttu-id="0e5a6-777">Descargue la plataforma Antivirus de Microsoft Defender para mantener el mejor nivel de protección disponible.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-777">Download the latest Microsoft Defender Antivirus platform to maintain the best level of protection available.</span></span>
<dl><span data-ttu-id="0e5a6-778">
<dt>Versión actual de la plataforma: &lt; versión actual de la plataforma&gt;</dt>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-778">
<dt>Current Platform Version: &lt;Current platform version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="0e5a6-779">Identificador de evento: 2010</span><span class="sxs-lookup"><span data-stu-id="0e5a6-779">Event ID: 2010</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="0e5a6-780">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-780">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-781">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_UPDATED </b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-781">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_UPDATED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-782">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-782">Message:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-783">
<b>El motor de antimalware usaba el servicio de firma dinámica para obtener definiciones adicionales. </b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-783">
<b>The antimalware engine used the Dynamic Signature Service to get additional definitions. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-784">Descripción:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-784">Description:</span></span>
</td>
<td >
<span data-ttu-id="0e5a6-785">Antivirus de Microsoft Defender <i>servicio de firma dinámica</i> para recuperar firmas adicionales para ayudar a proteger el equipo.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-785">Microsoft Defender Antivirus used <i>Dynamic Signature Service</i> to retrieve additional signatures to help protect your machine.</span></span>
<dl><span data-ttu-id="0e5a6-786">
<dt>Versión de firma actual: &lt; Versión de &gt; firma actual</dt> 
<dt> Tipo de firma: Tipo de firma , &lt; por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-786">
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Signature Type: &lt;Signature type&gt;, for example:</span></span> <ul>
<li><span data-ttu-id="0e5a6-787">Antivirus</span><span class="sxs-lookup"><span data-stu-id="0e5a6-787">Antivirus</span></span></li>
<li><span data-ttu-id="0e5a6-788">Antispyware</span><span class="sxs-lookup"><span data-stu-id="0e5a6-788">Antispyware</span></span></li>
<li><span data-ttu-id="0e5a6-789">Antimalware</span><span class="sxs-lookup"><span data-stu-id="0e5a6-789">Antimalware</span></span></li>
<li><span data-ttu-id="0e5a6-790">Sistema de inspección de red</span><span class="sxs-lookup"><span data-stu-id="0e5a6-790">Network Inspection System</span></span></li>
</ul><span data-ttu-id="0e5a6-791">
</dt>
<dt>Versión actual del motor: &lt; Versión actual &gt; del motor</dt> 
<dt> Tipo de firma dinámica: Tipo de firma &lt; dinámica , por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-791">
</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Dynamic Signature Type: &lt;Dynamic signature type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="0e5a6-792">Versión</span><span class="sxs-lookup"><span data-stu-id="0e5a6-792">Version</span></span></li>
<li><span data-ttu-id="0e5a6-793">Timestamp</span><span class="sxs-lookup"><span data-stu-id="0e5a6-793">Timestamp</span></span></li>
<li><span data-ttu-id="0e5a6-794">Sin límite</span><span class="sxs-lookup"><span data-stu-id="0e5a6-794">No limit</span></span></li>
<li><span data-ttu-id="0e5a6-795">Duración</span><span class="sxs-lookup"><span data-stu-id="0e5a6-795">Duration</span></span></li>
</ul><span data-ttu-id="0e5a6-796">
</dt>
<dt>Ruta de persistencia: &lt; Path &gt; </dt>
<dt>Dynamic Signature Version: &lt; Version number &gt; </dt>Dynamic Signature Compilation
<dt>Timestamp: &lt; &gt; Timestamp</dt> 
<dt> Persistence Limit Type: &lt; Persistence limit type , for &gt; example:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-796">
</dt>
<dt>Persistence Path: &lt;Path&gt;</dt>
<dt>Dynamic Signature Version: &lt;Version number&gt;</dt>
<dt>Dynamic Signature Compilation Timestamp: &lt;Timestamp&gt;</dt>
<dt>Persistence Limit Type: &lt;Persistence limit type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="0e5a6-797">Versión de VDM</span><span class="sxs-lookup"><span data-stu-id="0e5a6-797">VDM version</span></span></li>
<li><span data-ttu-id="0e5a6-798">Timestamp</span><span class="sxs-lookup"><span data-stu-id="0e5a6-798">Timestamp</span></span></li>
<li><span data-ttu-id="0e5a6-799">Sin límite</span><span class="sxs-lookup"><span data-stu-id="0e5a6-799">No limit</span></span></li>
</ul><span data-ttu-id="0e5a6-800">
</dt>
<dt>Límite de persistencia: límite de persistencia de la firma fastpath.</dt>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-800">
</dt>
<dt>Persistence Limit: Persistence limit of the fastpath signature.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="0e5a6-801">Identificador de evento: 2011</span><span class="sxs-lookup"><span data-stu-id="0e5a6-801">Event ID: 2011</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="0e5a6-802">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-802">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-803">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_DELETED </b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-803">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_DELETED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-804">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-804">Message:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-805">
<b>El servicio de firma dinámica eliminó las definiciones dinámicas des actualizadas. </b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-805">
<b>The Dynamic Signature Service deleted the out-of-date dynamic definitions. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-806">Descripción:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-806">Description:</span></span>
</td>
<td >
<span data-ttu-id="0e5a6-807">Antivirus de Microsoft Defender <i>servicio de firma dinámica para</i> descartar firmas obsoletas.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-807">Microsoft Defender Antivirus used <i>Dynamic Signature Service</i> to discard obsolete signatures.</span></span>
<dl><span data-ttu-id="0e5a6-808">
<dt>Versión de firma actual: &lt; Versión de &gt; firma actual</dt> 
<dt> Tipo de firma: Tipo de firma , &lt; por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-808">
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Signature Type: &lt;Signature type&gt;, for example:</span></span> <ul>
<li><span data-ttu-id="0e5a6-809">Antivirus</span><span class="sxs-lookup"><span data-stu-id="0e5a6-809">Antivirus</span></span></li>
<li><span data-ttu-id="0e5a6-810">Antispyware</span><span class="sxs-lookup"><span data-stu-id="0e5a6-810">Antispyware</span></span></li>
<li><span data-ttu-id="0e5a6-811">Antimalware</span><span class="sxs-lookup"><span data-stu-id="0e5a6-811">Antimalware</span></span></li>
<li><span data-ttu-id="0e5a6-812">Sistema de inspección de red</span><span class="sxs-lookup"><span data-stu-id="0e5a6-812">Network Inspection System</span></span></li>
</ul><span data-ttu-id="0e5a6-813">
</dt>
<dt>Versión actual del motor: &lt; Versión actual &gt; del motor</dt> 
<dt> Tipo de firma dinámica: Tipo de firma &lt; dinámica , por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-813">
</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Dynamic Signature Type: &lt;Dynamic signature type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="0e5a6-814">Versión</span><span class="sxs-lookup"><span data-stu-id="0e5a6-814">Version</span></span></li>
<li><span data-ttu-id="0e5a6-815">Timestamp</span><span class="sxs-lookup"><span data-stu-id="0e5a6-815">Timestamp</span></span></li>
<li><span data-ttu-id="0e5a6-816">Sin límite</span><span class="sxs-lookup"><span data-stu-id="0e5a6-816">No limit</span></span></li>
<li><span data-ttu-id="0e5a6-817">Duración</span><span class="sxs-lookup"><span data-stu-id="0e5a6-817">Duration</span></span></li>
</ul><span data-ttu-id="0e5a6-818">
</dt>
<dt>Ruta de persistencia: &lt; Path &gt; </dt>
<dt>Dynamic Signature Version: &lt; Version &gt; number</dt>Dynamic Signature Compilation
<dt>Timestamp: &lt; Timestamp &gt; </dt>Removal
<dt>Reason:</dt> 
<dt> Persistence Limit Type: &lt; Persistence limit type , for &gt; example:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-818">
</dt>
<dt>Persistence Path: &lt;Path&gt;</dt>
<dt>Dynamic Signature Version: &lt;Version number&gt;</dt>
<dt>Dynamic Signature Compilation Timestamp: &lt;Timestamp&gt;</dt>
<dt>Removal Reason:</dt>
<dt>Persistence Limit Type: &lt;Persistence limit type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="0e5a6-819">Versión de VDM</span><span class="sxs-lookup"><span data-stu-id="0e5a6-819">VDM version</span></span></li>
<li><span data-ttu-id="0e5a6-820">Timestamp</span><span class="sxs-lookup"><span data-stu-id="0e5a6-820">Timestamp</span></span></li>
<li><span data-ttu-id="0e5a6-821">Sin límite</span><span class="sxs-lookup"><span data-stu-id="0e5a6-821">No limit</span></span></li>
</ul><span data-ttu-id="0e5a6-822">
</dt>
<dt>Límite de persistencia: límite de persistencia de la firma fastpath.</dt>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-822">
</dt>
<dt>Persistence Limit: Persistence limit of the fastpath signature.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-823">Acción del usuario:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-823">User action:</span></span>
</td>
<td >
<span data-ttu-id="0e5a6-824">No es necesario realizar ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-824">No action is necessary.</span></span> <span data-ttu-id="0e5a6-825">El Antivirus de Microsoft Defender está en buen estado.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-825">The Microsoft Defender Antivirus client is in a healthy state.</span></span> <span data-ttu-id="0e5a6-826">Este evento se notifica cuando el servicio de firma dinámica elimina correctamente definiciones dinámicas des actualizadas.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-826">This event is reported when the Dynamic Signature Service successfully deletes out-of-date dynamic definitions.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="0e5a6-827">Identificador de evento: 2012</span><span class="sxs-lookup"><span data-stu-id="0e5a6-827">Event ID: 2012</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="0e5a6-828">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-828">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-829">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_UPDATE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-829">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_UPDATE_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-830">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-830">Message:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-831">
<b>El motor de antimalware encontró un error al intentar usar el servicio de firma dinámica. </b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-831">
<b>The antimalware engine encountered an error when trying to use the Dynamic Signature Service. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-832">Descripción:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-832">Description:</span></span>
</td>
<td >
<span data-ttu-id="0e5a6-833">Antivirus de Microsoft Defender ha encontrado un error al intentar usar <i>el servicio de firma dinámica</i>.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-833">Microsoft Defender Antivirus has encountered an error trying to use <i>Dynamic Signature Service</i>.</span></span>
<dl><span data-ttu-id="0e5a6-834">
<dt>Versión de firma actual: &lt; Versión de &gt; firma actual</dt> 
<dt> Tipo de firma: Tipo de firma , &lt; por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-834">
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Signature Type: &lt;Signature type&gt;, for example:</span></span> <ul>
<li><span data-ttu-id="0e5a6-835">Antivirus</span><span class="sxs-lookup"><span data-stu-id="0e5a6-835">Antivirus</span></span></li>
<li><span data-ttu-id="0e5a6-836">Antispyware</span><span class="sxs-lookup"><span data-stu-id="0e5a6-836">Antispyware</span></span></li>
<li><span data-ttu-id="0e5a6-837">Antimalware</span><span class="sxs-lookup"><span data-stu-id="0e5a6-837">Antimalware</span></span></li>
<li><span data-ttu-id="0e5a6-838">Sistema de inspección de red</span><span class="sxs-lookup"><span data-stu-id="0e5a6-838">Network Inspection System</span></span></li>
</ul><span data-ttu-id="0e5a6-839">
</dt>
<dt>Versión actual del motor: &lt; Versión del &gt; motor actual</dt>
<dt>Código de error: Código de error &lt; Código de resultado asociado con el estado de &gt; amenaza. Valores HRESULT estándar.</dt> 
<dt>Descripción del error: &lt; Descripción del error &gt; Descripción del error.</dt> 
<dt> Tipo de firma dinámica: &lt; Tipo de firma dinámica , por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-839">
</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Dynamic Signature Type: &lt;Dynamic signature type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="0e5a6-840">Versión</span><span class="sxs-lookup"><span data-stu-id="0e5a6-840">Version</span></span></li>
<li><span data-ttu-id="0e5a6-841">Timestamp</span><span class="sxs-lookup"><span data-stu-id="0e5a6-841">Timestamp</span></span></li>
<li><span data-ttu-id="0e5a6-842">Sin límite</span><span class="sxs-lookup"><span data-stu-id="0e5a6-842">No limit</span></span></li>
<li><span data-ttu-id="0e5a6-843">Duración</span><span class="sxs-lookup"><span data-stu-id="0e5a6-843">Duration</span></span></li>
</ul><span data-ttu-id="0e5a6-844">
</dt>
<dt>Ruta de persistencia: &lt; Path &gt; </dt>
<dt>Dynamic Signature Version: &lt; Version number &gt; </dt>Dynamic Signature Compilation
<dt>Timestamp: &lt; &gt; Timestamp</dt> 
<dt> Persistence Limit Type: &lt; Persistence limit type , for &gt; example:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-844">
</dt>
<dt>Persistence Path: &lt;Path&gt;</dt>
<dt>Dynamic Signature Version: &lt;Version number&gt;</dt>
<dt>Dynamic Signature Compilation Timestamp: &lt;Timestamp&gt;</dt>
<dt>Persistence Limit Type: &lt;Persistence limit type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="0e5a6-845">Versión de VDM</span><span class="sxs-lookup"><span data-stu-id="0e5a6-845">VDM version</span></span></li>
<li><span data-ttu-id="0e5a6-846">Timestamp</span><span class="sxs-lookup"><span data-stu-id="0e5a6-846">Timestamp</span></span></li>
<li><span data-ttu-id="0e5a6-847">Sin límite</span><span class="sxs-lookup"><span data-stu-id="0e5a6-847">No limit</span></span></li>
</ul><span data-ttu-id="0e5a6-848">
</dt>
<dt>Límite de persistencia: límite de persistencia de la firma fastpath.</dt>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-848">
</dt>
<dt>Persistence Limit: Persistence limit of the fastpath signature.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-849">Acción del usuario:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-849">User action:</span></span>
</td>
<td >
<span data-ttu-id="0e5a6-850">Comprueba la configuración de conectividad a Internet.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-850">Check your Internet connectivity settings.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="0e5a6-851">Identificador de evento: 2013</span><span class="sxs-lookup"><span data-stu-id="0e5a6-851">Event ID: 2013</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="0e5a6-852">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-852">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-853">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_DELETED_ALL </b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-853">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_DELETED_ALL </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-854">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-854">Message:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-855">
<b>El servicio de firma dinámica eliminó todas las definiciones dinámicas. </b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-855">
<b>The Dynamic Signature Service deleted all dynamic definitions. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-856">Descripción:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-856">Description:</span></span>
</td>
<td >
<span data-ttu-id="0e5a6-857">Antivirus de Microsoft Defender descarta todas las firmas <i>del servicio de firma</i> dinámica.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-857">Microsoft Defender Antivirus discarded all <i>Dynamic Signature Service</i> signatures.</span></span>
<dl><span data-ttu-id="0e5a6-858">
<dt>Versión actual de la firma: &lt; versión actual de la firma&gt;</dt>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-858">
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="0e5a6-859">Identificador de evento: 2020</span><span class="sxs-lookup"><span data-stu-id="0e5a6-859">Event ID: 2020</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="0e5a6-860">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-860">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-861">
<b>MALWAREPROTECTION_CLOUD_CLEAN_RESTORE_FILE_DOWNLOADED </b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-861">
<b>MALWAREPROTECTION_CLOUD_CLEAN_RESTORE_FILE_DOWNLOADED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-862">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-862">Message:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-863">
<b>El motor de antimalware descargó un archivo limpio. </b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-863">
<b>The antimalware engine downloaded a clean file. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-864">Descripción:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-864">Description:</span></span>
</td>
<td >
<span data-ttu-id="0e5a6-865">Antivirus de Microsoft Defender descargado un archivo limpio.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-865">Microsoft Defender Antivirus downloaded a clean file.</span></span>
<dl><span data-ttu-id="0e5a6-866">
<dt>Nombre de archivo: &lt; Nombre de &gt; archivo Nombre del archivo.</dt> 
<dt>Versión de firma actual: &lt; Versión actual &gt; del motor</dt>
<dt>de firma Actual: versión actual del &lt; motor &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-866">
<dt>Filename: &lt;File name&gt; Name of the file.</dt>
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="0e5a6-867">Identificador de evento: 2021</span><span class="sxs-lookup"><span data-stu-id="0e5a6-867">Event ID: 2021</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="0e5a6-868">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-868">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-869">
<b>MALWAREPROTECTION_CLOUD_CLEAN_RESTORE_FILE_DOWNLOAD_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-869">
<b>MALWAREPROTECTION_CLOUD_CLEAN_RESTORE_FILE_DOWNLOAD_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-870">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-870">Message:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-871">
<b>El motor de antimalware no pudo descargar un archivo limpio. </b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-871">
<b>The antimalware engine failed to download a clean file. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-872">Descripción:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-872">Description:</span></span>
</td>
<td >
<span data-ttu-id="0e5a6-873">Antivirus de Microsoft Defender ha encontrado un error al intentar descargar un archivo limpio.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-873">Microsoft Defender Antivirus has encountered an error trying to download a clean file.</span></span>
<dl><span data-ttu-id="0e5a6-874">
<dt>Nombre de archivo: &lt; Nombre de &gt; archivo Nombre del archivo.</dt> 
<dt>Versión de firma actual: &lt; Versión de &gt; firma actual</dt>
<dt>Versión actual del motor: Versión actual &lt; del &gt; </dt>motor Código de error: Código de
<dt>error Código de resultado asociado con el estado de &lt; &gt; amenaza. Valores HRESULT estándar.</dt> 
<dt>Descripción del error: &lt; Descripción del error &gt; Descripción del error.</dt>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-874">
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
<span data-ttu-id="0e5a6-875">Acción del usuario:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-875">User action:</span></span>
</td>
<td >
<span data-ttu-id="0e5a6-876">Comprueba la configuración de conectividad a Internet.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-876">Check your Internet connectivity settings.</span></span>
<span data-ttu-id="0e5a6-877">El Antivirus de Microsoft Defender encontró un error al usar el servicio de firma dinámica para descargar las definiciones más recientes en una amenaza específica.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-877">The Microsoft Defender Antivirus client encountered an error when using the Dynamic Signature Service to download the latest definitions to a specific threat.</span></span> <span data-ttu-id="0e5a6-878">Es probable que este error se deba a un problema de conectividad de red.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-878">This error is likely caused by a network connectivity issue.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="0e5a6-879">Identificador de evento: 2030</span><span class="sxs-lookup"><span data-stu-id="0e5a6-879">Event ID: 2030</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="0e5a6-880">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-880">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-881">
<b>MALWAREPROTECTION_OFFLINE_SCAN_INSTALLED</b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-881">
<b>MALWAREPROTECTION_OFFLINE_SCAN_INSTALLED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-882">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-882">Message:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-883">
<b>El motor de antimalware se descargó y está configurado para ejecutarse sin conexión en el siguiente reinicio del sistema.</b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-883">
<b>The antimalware engine was downloaded and is configured to run offline on the next system restart.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-884">Descripción:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-884">Description:</span></span>
</td>
<td >
<span data-ttu-id="0e5a6-885">Antivirus de Microsoft Defender descargado y configurado antivirus sin conexión para que se ejecute en el siguiente reinicio.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-885">Microsoft Defender Antivirus downloaded and configured offline antivirus to run on the next reboot.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="0e5a6-886">Identificador de evento: 2031</span><span class="sxs-lookup"><span data-stu-id="0e5a6-886">Event ID: 2031</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="0e5a6-887">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-887">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-888">
<b>MALWAREPROTECTION_OFFLINE_SCAN_INSTALL_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-888">
<b>MALWAREPROTECTION_OFFLINE_SCAN_INSTALL_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-889">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-889">Message:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-890">
<b>El motor de antimalware no pudo descargar ni configurar un examen sin conexión.</b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-890">
<b>The antimalware engine was unable to download and configure an offline scan.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-891">Descripción:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-891">Description:</span></span>
</td>
<td >
<span data-ttu-id="0e5a6-892">Antivirus de Microsoft Defender ha encontrado un error al intentar descargar y configurar antivirus sin conexión.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-892">Microsoft Defender Antivirus has encountered an error trying to download and configure offline antivirus.</span></span>
<dl><span data-ttu-id="0e5a6-893">
<dt>Código de error: &lt; Código de error &gt; Código de resultado asociado con el estado de amenaza. Valores HRESULT estándar.</dt> 
<dt>Descripción del error: &lt; Descripción del error &gt; Descripción del error.</dt>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-893">
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="0e5a6-894">Identificador de evento: 2040</span><span class="sxs-lookup"><span data-stu-id="0e5a6-894">Event ID: 2040</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="0e5a6-895">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-895">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-896">
<b>MALWAREPROTECTION_OS_EXPIRING </b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-896">
<b>MALWAREPROTECTION_OS_EXPIRING </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-897">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-897">Message:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-898">
<b>La compatibilidad con antimalware para esta versión del sistema operativo finalizará próximamente. </b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-898">
<b>Antimalware support for this operating system version will soon end. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-899">Descripción:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-899">Description:</span></span>
</td>
<td >
<span data-ttu-id="0e5a6-900">La compatibilidad con el sistema operativo expirará en breve.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-900">The support for your operating system will expire shortly.</span></span> <span data-ttu-id="0e5a6-901">Ejecutar Antivirus de Microsoft Defender en un sistema operativo no compatible no es una solución adecuada para protegerse contra amenazas.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-901">Running Microsoft Defender Antivirus on an out of support operating system is not an adequate solution to protect against threats.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="0e5a6-902">Identificador de evento: 2041</span><span class="sxs-lookup"><span data-stu-id="0e5a6-902">Event ID: 2041</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="0e5a6-903">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-903">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-904">
<b>MALWAREPROTECTION_OS_EOL </b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-904">
<b>MALWAREPROTECTION_OS_EOL </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-905">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-905">Message:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-906">
<b>La compatibilidad con antimalware para este sistema operativo ha finalizado. Debe actualizar el sistema operativo para que la compatibilidad continúe. </b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-906">
<b>Antimalware support for this operating system has ended. You must upgrade the operating system for continued support. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-907">Descripción:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-907">Description:</span></span>
</td>
<td >
<span data-ttu-id="0e5a6-908">La compatibilidad con el sistema operativo ha expirado.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-908">The support for your operating system has expired.</span></span> <span data-ttu-id="0e5a6-909">Ejecutar Antivirus de Microsoft Defender en un sistema operativo no compatible no es una solución adecuada para protegerse contra amenazas.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-909">Running Microsoft Defender Antivirus on an out of support operating system is not an adequate solution to protect against threats.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="0e5a6-910">Identificador de evento: 2042</span><span class="sxs-lookup"><span data-stu-id="0e5a6-910">Event ID: 2042</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="0e5a6-911">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-911">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-912">
<b>MALWAREPROTECTION_PROTECTION_EOL </b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-912">
<b>MALWAREPROTECTION_PROTECTION_EOL </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-913">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-913">Message:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-914">
<b>El motor de antimalware ya no es compatible con este sistema operativo y ya no protege el sistema contra malware. </b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-914">
<b>The antimalware engine no longer supports this operating system, and is no longer protecting your system from malware. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-915">Descripción:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-915">Description:</span></span>
</td>
<td >
<span data-ttu-id="0e5a6-916">La compatibilidad con el sistema operativo ha expirado.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-916">The support for your operating system has expired.</span></span> <span data-ttu-id="0e5a6-917">Antivirus de Microsoft Defender ya no se admite en el sistema operativo, ha dejado de funcionar y no protege contra amenazas de malware.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-917">Microsoft Defender Antivirus is no longer supported on your operating system, has stopped functioning, and is not protecting against malware threats.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="0e5a6-918">Identificador de evento: 3002</span><span class="sxs-lookup"><span data-stu-id="0e5a6-918">Event ID: 3002</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="0e5a6-919">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-919">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-920">
<b>MALWAREPROTECTION_RTP_FEATURE_FAILURE </b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-920">
<b>MALWAREPROTECTION_RTP_FEATURE_FAILURE </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-921">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-921">Message:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-922">
<b>La protección en tiempo real encontró un error y produjo un error.</b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-922">
<b>Real-time protection encountered an error and failed.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-923">Descripción:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-923">Description:</span></span>
</td>
<td >
<span data-ttu-id="0e5a6-924">Antivirus de Microsoft Defender Real-Time de protección ha encontrado un error y ha producido un error.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-924">Microsoft Defender Antivirus Real-Time Protection feature has encountered an error and failed.</span></span>
<dl><span data-ttu-id="0e5a6-925">
<dt>Característica: &lt; Característica , por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-925">
<dt>Feature: &lt;Feature&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="0e5a6-926">En Access</span><span class="sxs-lookup"><span data-stu-id="0e5a6-926">On Access</span></span></li>
<li><span data-ttu-id="0e5a6-927">Descargas de Internet Explorer y datos adjuntos de Microsoft Outlook Express</span><span class="sxs-lookup"><span data-stu-id="0e5a6-927">Internet Explorer downloads and Microsoft Outlook Express attachments</span></span></li>
<li><span data-ttu-id="0e5a6-928">Supervisión del comportamiento</span><span class="sxs-lookup"><span data-stu-id="0e5a6-928">Behavior monitoring</span></span></li>
<li><span data-ttu-id="0e5a6-929">Sistema de inspección de red</span><span class="sxs-lookup"><span data-stu-id="0e5a6-929">Network Inspection System</span></span></li>
</ul><span data-ttu-id="0e5a6-930">
</dt>
<dt>Código de error: &lt; Código de error &gt; Código de resultado asociado con el estado de amenaza. Valores HRESULT estándar.</dt> 
<dt>Descripción del error: &lt; Descripción del error &gt; Descripción del error.</dt> 
<dt>Motivo: el motivo Antivirus de Microsoft Defender protección en tiempo real ha reiniciado una característica.</dt>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-930">
</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Reason: The reason Microsoft Defender Antivirus real-time protection has restarted a feature.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-931">Acción del usuario:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-931">User action:</span></span>
</td>
<td >
<span data-ttu-id="0e5a6-932">Debe reiniciar el sistema y, a continuación, ejecutar un examen completo porque&#39;es posible que el sistema no se protegió durante algún tiempo.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-932">You should restart the system then run a full scan because it&#39;s possible the system was not protected for some time.</span></span>
<span data-ttu-id="0e5a6-933">La Antivirus de Microsoft Defender cliente&#39;la característica de protección en tiempo real encontró un error porque uno de los servicios no se pudo iniciar.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-933">The Microsoft Defender Antivirus client&#39;s real-time protection feature encountered an error because one of the services failed to start.</span></span> <span data-ttu-id="0e5a6-934">Si le sigue un identificador de evento 3007, el error fue temporal y el cliente antimalware se recuperó del error.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-934">If it is followed by a 3007 event ID, the failure was temporary and the antimalware client recovered from the failure.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="0e5a6-935">Identificador de evento: 3007</span><span class="sxs-lookup"><span data-stu-id="0e5a6-935">Event ID: 3007</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="0e5a6-936">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-936">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-937">
<b>MALWAREPROTECTION_RTP_FEATURE_RECOVERED</b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-937">
<b>MALWAREPROTECTION_RTP_FEATURE_RECOVERED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-938">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-938">Message:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-939">
<b>Protección en tiempo real recuperada de un error. Se recomienda ejecutar un examen completo del sistema cuando vea este error. </b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-939">
<b>Real-time protection recovered from a failure. We recommend running a full system scan when you see this error. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-940">Descripción:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-940">Description:</span></span>
</td>
<td >
<span data-ttu-id="0e5a6-941">Antivirus de Microsoft Defender Protección en tiempo real ha reiniciado una característica.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-941">Microsoft Defender Antivirus Real-time Protection has restarted a feature.</span></span> <span data-ttu-id="0e5a6-942">Se recomienda ejecutar un examen completo del sistema para detectar los elementos que se hayan perdido mientras este agente estaba abajo.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-942">It is recommended that you run a full system scan to detect any items that may have been missed while this agent was down.</span></span>
<dl><span data-ttu-id="0e5a6-943">
<dt>Característica: &lt; Característica , por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-943">
<dt>Feature: &lt;Feature&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="0e5a6-944">En Access</span><span class="sxs-lookup"><span data-stu-id="0e5a6-944">On Access</span></span></li>
<li><span data-ttu-id="0e5a6-945">Descargas de IE y Outlook datos adjuntos de Express</span><span class="sxs-lookup"><span data-stu-id="0e5a6-945">IE downloads and Outlook Express attachments</span></span></li>
<li><span data-ttu-id="0e5a6-946">Supervisión del comportamiento</span><span class="sxs-lookup"><span data-stu-id="0e5a6-946">Behavior monitoring</span></span></li>
<li><span data-ttu-id="0e5a6-947">Sistema de inspección de red</span><span class="sxs-lookup"><span data-stu-id="0e5a6-947">Network Inspection System</span></span></li>
</ul><span data-ttu-id="0e5a6-948">
</dt>
<dt>Motivo: el motivo Antivirus de Microsoft Defender protección en tiempo real ha reiniciado una característica.</dt>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-948">
</dt>
<dt>Reason: The reason Microsoft Defender Antivirus real-time protection has restarted a feature.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-949">Acción del usuario:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-949">User action:</span></span>
</td>
<td >
<span data-ttu-id="0e5a6-950">Se ha reiniciado la característica de protección en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-950">The real-time protection feature has restarted.</span></span> <span data-ttu-id="0e5a6-951">Si este evento se produce de nuevo, póngase en contacto <a href="https://go.microsoft.com/fwlink/?LinkId=215491">con el Soporte técnico de Microsoft</a>.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-951">If this event happens again, contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="0e5a6-952">Identificador de evento: 5000</span><span class="sxs-lookup"><span data-stu-id="0e5a6-952">Event ID: 5000</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="0e5a6-953">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-953">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-954">
<b>MALWAREPROTECTION_RTP_ENABLED </b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-954">
<b>MALWAREPROTECTION_RTP_ENABLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-955">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-955">Message:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-956">
<b>La protección en tiempo real está habilitada. </b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-956">
<b>Real-time protection is enabled. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-957">Descripción:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-957">Description:</span></span>
</td>
<td >
<span data-ttu-id="0e5a6-958">Antivirus de Microsoft Defender de protección en tiempo real en busca de malware y otro software potencialmente no deseado.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-958">Microsoft Defender Antivirus real-time protection scanning for malware and other potentially unwanted software was enabled.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="0e5a6-959">Identificador de evento: 5001</span><span class="sxs-lookup"><span data-stu-id="0e5a6-959">Event ID: 5001</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="0e5a6-960">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-960">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-961">
<b>MALWAREPROTECTION_RTP_DISABLED</b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-961">
<b>MALWAREPROTECTION_RTP_DISABLED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-962">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-962">Message:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-963">
<b>La protección en tiempo real está deshabilitada. </b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-963">
<b>Real-time protection is disabled. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-964">Descripción:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-964">Description:</span></span>
</td>
<td >
<span data-ttu-id="0e5a6-965">Antivirus de Microsoft Defender de protección en tiempo real en busca de malware y otro software potencialmente no deseado se deshabilitó.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-965">Microsoft Defender Antivirus real-time protection scanning for malware and other potentially unwanted software was disabled.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="0e5a6-966">Identificador de evento: 5004</span><span class="sxs-lookup"><span data-stu-id="0e5a6-966">Event ID: 5004</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="0e5a6-967">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-967">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-968">
<b>MALWAREPROTECTION_RTP_FEATURE_CONFIGURED </b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-968">
<b>MALWAREPROTECTION_RTP_FEATURE_CONFIGURED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-969">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-969">Message:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-970">
<b>La configuración de protección en tiempo real cambió. </b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-970">
<b>The real-time protection configuration changed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-971">Descripción:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-971">Description:</span></span>
</td>
<td >
<span data-ttu-id="0e5a6-972">Antivirus de Microsoft Defender configuración de características de protección en tiempo real ha cambiado.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-972">Microsoft Defender Antivirus real-time protection feature configuration has changed.</span></span>
<dl><span data-ttu-id="0e5a6-973">
<dt>Característica: &lt; Característica , por &gt; ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-973">
<dt>Feature: &lt;Feature&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="0e5a6-974">En Access</span><span class="sxs-lookup"><span data-stu-id="0e5a6-974">On Access</span></span></li>
<li><span data-ttu-id="0e5a6-975">Descargas de IE y Outlook datos adjuntos de Express</span><span class="sxs-lookup"><span data-stu-id="0e5a6-975">IE downloads and Outlook Express attachments</span></span></li>
<li><span data-ttu-id="0e5a6-976">Supervisión del comportamiento</span><span class="sxs-lookup"><span data-stu-id="0e5a6-976">Behavior monitoring</span></span></li>
<li><span data-ttu-id="0e5a6-977">Sistema de inspección de red</span><span class="sxs-lookup"><span data-stu-id="0e5a6-977">Network Inspection System</span></span></li>
</ul><span data-ttu-id="0e5a6-978">
</dt>
<dt>Configuración: </dt>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-978">
</dt>
<dt>Configuration: </dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="0e5a6-979">Identificador de evento: 5007</span><span class="sxs-lookup"><span data-stu-id="0e5a6-979">Event ID: 5007</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="0e5a6-980">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-980">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-981">
<b>MALWAREPROTECTION_CONFIG_CHANGED </b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-981">
<b>MALWAREPROTECTION_CONFIG_CHANGED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-982">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-982">Message:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-983">
<b>Se cambió la configuración de la plataforma antimalware.</b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-983">
<b>The antimalware platform configuration changed.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-984">Descripción:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-984">Description:</span></span>
</td>
<td >
<span data-ttu-id="0e5a6-985">Antivirus de Microsoft Defender configuración ha cambiado.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-985">Microsoft Defender Antivirus configuration has changed.</span></span> <span data-ttu-id="0e5a6-986">Si se trata de un evento inesperado, debe revisar la configuración, ya que puede ser el resultado de malware.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-986">If this is an unexpected event, you should review the settings as this may be the result of malware.</span></span>
<dl><span data-ttu-id="0e5a6-987">
<dt>Valor antiguo: &lt; Número de valor antiguo &gt; Valor de configuración del antivirus anterior.</dt> 
<dt>Nuevo valor: &lt; Nuevo número de valor &gt; Nuevo valor de configuración antivirus.</dt>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-987">
<dt>Old value: &lt;Old value number&gt; Old antivirus configuration value.</dt>
<dt>New value: &lt;New value number&gt; New antivirus configuration value.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="0e5a6-988">Identificador de evento: 5008</span><span class="sxs-lookup"><span data-stu-id="0e5a6-988">Event ID: 5008</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="0e5a6-989">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-989">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-990">
<b>MALWAREPROTECTION_ENGINE_FAILURE</b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-990">
<b>MALWAREPROTECTION_ENGINE_FAILURE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-991">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-991">Message:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-992">
<b>El motor de antimalware encontró un error y produjo un error.</b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-992">
<b>The antimalware engine encountered an error and failed.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-993">Descripción:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-993">Description:</span></span>
</td>
<td >
<span data-ttu-id="0e5a6-994">Antivirus de Microsoft Defender motor se ha terminado debido a un error inesperado.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-994">Microsoft Defender Antivirus engine has been terminated due to an unexpected error.</span></span>
<dl><span data-ttu-id="0e5a6-995">
<dt>Tipo de error: &lt; Tipo de &gt; error , por ejemplo: Bloquear o bloquear código</dt>de
<dt>excepción: &lt; Código de &gt; error</dt>
<dt>Recurso: &lt; recurso &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-995">
<dt>Failure Type: &lt;Failure type&gt;, for example: Crash or Hang</dt>
<dt>Exception Code: &lt;Error code&gt;</dt>
<dt>Resource: &lt;Resource&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-996">Acción del usuario:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-996">User action:</span></span>
</td>
<td >
<span data-ttu-id="0e5a6-997">Para solucionar este evento:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-997">To troubleshoot this event:</span></span><ol>
<li><span data-ttu-id="0e5a6-998">Intente reiniciar el servicio.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-998">Try to restart the service.</span></span><ul>
<li><span data-ttu-id="0e5a6-999">Para antimalware, antivirus y spyware, en un símbolo del sistema con privilegios elevados, escriba <b>net stop msmpsvc</b>y, a continuación, escriba <b>net start msmpsvc</b> para reiniciar el motor de antimalware.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-999">For antimalware, antivirus and spyware, at an elevated command prompt, type <b>net stop msmpsvc</b>, and then type <b>net start msmpsvc</b> to restart the antimalware engine.</span></span></li>
<li><span data-ttu-id="0e5a6-1000">Para el sistema <i>de</i>inspección de red , en un símbolo del sistema con privilegios elevados, escriba <b>net start nissrv</b>y, a continuación, escriba <b>net start nissrv</b> para reiniciar el motor del sistema de inspección de red mediante el archivo NiSSRV.exe. <i></i></span><span class="sxs-lookup"><span data-stu-id="0e5a6-1000">For the <i>Network Inspection System</i>, at an elevated command prompt, type <b>net start nissrv</b>, and then type <b>net start nissrv</b> to restart the <i>Network Inspection System</i> engine by using the NiSSRV.exe file.</span></span>
</li>
</ul>
</li>
<li><span data-ttu-id="0e5a6-1001">Si se produce un error de la misma manera, busque el código de <b></b> error accediendo al Sitio de soporte técnico de <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft</a> y especificando el número de error en el cuadro Búsqueda y póngase en contacto con el Soporte técnico <a href="https://go.microsoft.com/fwlink/?LinkId=215491">de Microsoft</a>.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1001">If it fails in the same way, look up the error code by accessing the <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft Support Site</a>  and entering the error number in the <b>Search</b> box, and contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span></li>
</ol>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-1002">Acción del usuario:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1002">User action:</span></span>
</td>
<td >
<span data-ttu-id="0e5a6-1003">El Antivirus de Microsoft Defender cliente se detuvo debido a un error inesperado.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1003">The Microsoft Defender Antivirus client engine stopped due to an unexpected error.</span></span>
<span data-ttu-id="0e5a6-1004">Para solucionar este evento:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1004">To troubleshoot this event:</span></span>
<ol>
<li><span data-ttu-id="0e5a6-1005">Vuelva a ejecutar el examen.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1005">Run the scan again.</span></span></li>
<li><span data-ttu-id="0e5a6-1006">Si se produce un error de la misma manera, vaya <b></b> al sitio de soporte técnico de <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft</a>, escriba el número de error en el cuadro Buscar para buscar el código de error.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1006">If it fails in the same way, go to the <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft Support site</a>, enter the error number in the <b>Search</b> box to look for the error code.</span></span></li>
<li><span data-ttu-id="0e5a6-1007">Contactar al <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Soporte técnico de Microsoft</a>.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1007">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="0e5a6-1008">Identificador de evento: 5009</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1008">Event ID: 5009</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="0e5a6-1009">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1009">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-1010">
<b>MALWAREPROTECTION_ANTISPYWARE_ENABLED </b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1010">
<b>MALWAREPROTECTION_ANTISPYWARE_ENABLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-1011">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1011">Message:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-1012">
<b>El examen de malware y otro software potencialmente no deseado está habilitado. </b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1012">
<b>Scanning for malware and other potentially unwanted software is enabled. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-1013">Descripción:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1013">Description:</span></span>
</td>
<td >
<span data-ttu-id="0e5a6-1014">Antivirus de Microsoft Defender se ha habilitado el examen de malware y otro software potencialmente no deseado.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1014">Microsoft Defender Antivirus scanning for malware and other potentially unwanted software has been enabled.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="0e5a6-1015">Identificador de evento: 5010</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1015">Event ID: 5010</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="0e5a6-1016">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1016">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-1017">
<b>MALWAREPROTECTION_ANTISPYWARE_DISABLED </b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1017">
<b>MALWAREPROTECTION_ANTISPYWARE_DISABLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-1018">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1018">Message:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-1019">
<b>El examen de malware y otro software potencialmente no deseado está deshabilitado.</b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1019">
<b>Scanning for malware and other potentially unwanted software is disabled.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-1020">Descripción:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1020">Description:</span></span>
</td>
<td >
<span data-ttu-id="0e5a6-1021">Antivirus de Microsoft Defender de búsqueda de malware y otro software potencialmente no deseado está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1021">Microsoft Defender Antivirus scanning for malware and other potentially unwanted software is disabled.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="0e5a6-1022">Identificador de evento: 5011</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1022">Event ID: 5011</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="0e5a6-1023">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1023">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-1024">
<b>MALWAREPROTECTION_ANTIVIRUS_ENABLED</b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1024">
<b>MALWAREPROTECTION_ANTIVIRUS_ENABLED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-1025">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1025">Message:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-1026">
<b>El examen de virus está habilitado.</b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1026">
<b>Scanning for viruses is enabled.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-1027">Descripción:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1027">Description:</span></span>
</td>
<td >
<span data-ttu-id="0e5a6-1028">Antivirus de Microsoft Defender se ha habilitado el examen de virus.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1028">Microsoft Defender Antivirus scanning for viruses has been enabled.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="0e5a6-1029">Identificador de evento: 5012</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1029">Event ID: 5012</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="0e5a6-1030">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1030">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-1031">
<b>MALWAREPROTECTION_ANTIVIRUS_DISABLED </b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1031">
<b>MALWAREPROTECTION_ANTIVIRUS_DISABLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-1032">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1032">Message:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-1033">
<b>El examen de virus está deshabilitado. </b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1033">
<b>Scanning for viruses is disabled. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-1034">Descripción:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1034">Description:</span></span>
</td>
<td >
<span data-ttu-id="0e5a6-1035">Antivirus de Microsoft Defender está deshabilitado el examen de virus.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1035">Microsoft Defender Antivirus scanning for viruses is disabled.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="0e5a6-1036">Identificador de evento: 5100</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1036">Event ID: 5100</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="0e5a6-1037">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1037">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-1038">
<b>MALWAREPROTECTION_EXPIRATION_WARNING_STATE </b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1038">
<b>MALWAREPROTECTION_EXPIRATION_WARNING_STATE </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-1039">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1039">Message:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-1040">
<b>La plataforma antimalware expirará pronto. </b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1040">
<b>The antimalware platform will expire soon. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-1041">Descripción:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1041">Description:</span></span>
</td>
<td >
<span data-ttu-id="0e5a6-1042">Antivirus de Microsoft Defender ha entrado en un período de gracia y expirará pronto.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1042">Microsoft Defender Antivirus has entered a grace period and will soon expire.</span></span> <span data-ttu-id="0e5a6-1043">Después de expirar, este programa deshabilitará la protección contra virus, spyware y otro software potencialmente no deseado.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1043">After expiration, this program will disable protection against viruses, spyware, and other potentially unwanted software.</span></span>
<dl><span data-ttu-id="0e5a6-1044">
<dt>Motivo de expiración: el Antivirus de Microsoft Defender expirará.</dt> 
<dt>Fecha de expiración: la Antivirus de Microsoft Defender expirará.</dt>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1044">
<dt>Expiration Reason: The reason Microsoft Defender Antivirus will expire.</dt>
<dt>Expiration Date: The date Microsoft Defender Antivirus will expire.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="0e5a6-1045">Identificador de evento: 5101</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1045">Event ID: 5101</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="0e5a6-1046">Nombre simbólico:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1046">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-1047">
<b>MALWAREPROTECTION_DISABLED_EXPIRED_STATE </b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1047">
<b>MALWAREPROTECTION_DISABLED_EXPIRED_STATE </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-1048">Mensaje:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1048">Message:</span></span>
</td>
<td ><span data-ttu-id="0e5a6-1049">
<b>La plataforma antimalware ha expirado. </b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1049">
<b>The antimalware platform is expired. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-1050">Descripción:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1050">Description:</span></span>
</td>
<td >
<span data-ttu-id="0e5a6-1051">Antivirus de Microsoft Defender período de gracia ha expirado.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1051">Microsoft Defender Antivirus grace period has expired.</span></span> <span data-ttu-id="0e5a6-1052">La protección contra virus, spyware y otro software potencialmente no deseado está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1052">Protection against viruses, spyware, and other potentially unwanted software is disabled.</span></span>
<dl><span data-ttu-id="0e5a6-1053">
<dt>Motivo de expiración:</dt>
<dt>Fecha de expiración: </dt>Código de error: Código de error Código de resultado asociado con el estado de la 
<dt> &lt; &gt; amenaza. Valores HRESULT estándar.</dt> 
<dt>Descripción del error: &lt; Descripción del error &gt; Descripción del error.</dt>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1053">
<dt>Expiration Reason:</dt>
<dt>Expiration Date: </dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr><span data-ttu-id="0e5a6-1054">
</table>

<a id="error-codes"></a>
##Antivirus de Microsoft Defender de error de cliente Si Antivirus de Microsoft Defender experimenta algún problema, normalmente le dará un código de error para ayudarle a solucionar el problema.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1054">
</table>

<a id="error-codes"></a>
## Microsoft Defender Antivirus client error codes If Microsoft Defender Antivirus experiences any issues it will usually give you an error code to help you troubleshoot the issue.</span></span> <span data-ttu-id="0e5a6-1055">En la mayoría de los casos, un error significa que hubo un problema al instalar una actualización.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1055">Most often an error means there was a problem installing an update.</span></span>
<span data-ttu-id="0e5a6-1056">En esta sección se proporciona la siguiente información sobre Antivirus de Microsoft Defender errores de cliente.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1056">This section provides the following information about Microsoft Defender Antivirus client errors.</span></span>
<span data-ttu-id="0e5a6-1057">-   El código de error -   El posible motivo del error Consejo sobre qué hacer -   ahora</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1057">-   The error code -   The possible reason for the error -   Advice on what to do now</span></span>

<span data-ttu-id="0e5a6-1058">Use la información de estas tablas para ayudar a solucionar Antivirus de Microsoft Defender códigos de error.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1058">Use the information in these tables to help troubleshoot Microsoft Defender Antivirus error codes.</span></span>


<table> 
<tr>
<th colspan="2"><span data-ttu-id="0e5a6-1059">Código de error: 0x80508007</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1059">Error code: 0x80508007</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="0e5a6-1060">Mensaje</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1060">Message</span></span></td>
<td><span data-ttu-id="0e5a6-1061">
<b>ERR_MP_NO_MEMORY </b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1061">
<b>ERR_MP_NO_MEMORY </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-1062">Posible motivo</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1062">Possible reason</span></span>
</td>
<td>
<span data-ttu-id="0e5a6-1063">Este error indica que es posible que se haya quedo sin memoria.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1063">This error indicates that you might have run out of memory.</span></span> 
</td>
</tr>
<tr>
<td><span data-ttu-id="0e5a6-1064">Solución</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1064">Resolution</span></span></td>
<td>
<ol>
<li><span data-ttu-id="0e5a6-1065">Comprueba la memoria disponible en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1065">Check the available memory on your device.</span></span></li>
<li><span data-ttu-id="0e5a6-1066">Cierra todas las aplicaciones no usadas que se estén ejecutando para liberar memoria en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1066">Close any unused applications that are running to free up memory on your device.</span></span></li>
<li><span data-ttu-id="0e5a6-1067">Reinicie el dispositivo y vuelva a ejecutar el examen.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1067">Restart the device and run the scan again.</span></span> 
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="0e5a6-1068">Código de error: 0x8050800C</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1068">Error code: 0x8050800C</span></span></th>
</tr><tr><td><span data-ttu-id="0e5a6-1069">Mensaje</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1069">Message</span></span></td>
<td><span data-ttu-id="0e5a6-1070"><b>ERR_MP_BAD_INPUT_DATA</b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1070"><b>ERR_MP_BAD_INPUT_DATA</b>
</span></span></td></tr><tr><td><span data-ttu-id="0e5a6-1071">Posible motivo</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1071">Possible reason</span></span></td>
<td>
<span data-ttu-id="0e5a6-1072">Este error indica que puede haber un problema con el producto de seguridad.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1072">This error indicates that there might be a problem with your security product.</span></span>
</td>
</tr><tr><td><span data-ttu-id="0e5a6-1073">Solución</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1073">Resolution</span></span></td><td>
<ol>
<li><span data-ttu-id="0e5a6-1074">Actualice las definiciones.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1074">Update the definitions.</span></span> <span data-ttu-id="0e5a6-1075">Cualquiera de las dos:</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1075">Either:</span></span><ol>
<li><span data-ttu-id="0e5a6-1076">Haga clic <b>en el botón Actualizar definiciones</b> de la <b>ficha</b> Actualizar en Antivirus de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1076">Click the <b>Update definitions</b> button on the <b>Update</b> tab in Microsoft Defender Antivirus.</span></span> <img src="images/defender-updatedefs2.png" alt="Update definitions in Microsoft Defender Antivirus"/><span data-ttu-id="0e5a6-1077">O bien</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1077">Or,</span></span>
</li>
<li><span data-ttu-id="0e5a6-1078">Descargue las definiciones más recientes del <a href="https://aka.ms/wdsi">Inteligencia de seguridad de Microsoft sitio</a>.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1078">Download the latest definitions from the <a href="https://aka.ms/wdsi">Microsoft Security Intelligence site</a>.</span></span>
<span data-ttu-id="0e5a6-1079">Nota: El tamaño del archivo de definiciones descargado del sitio puede superar los 60 MB y no debe usarse como solución a largo plazo para actualizar definiciones.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1079">Note: The size of the definitions file downloaded from the site can exceed 60 MB and should not be used as a long-term solution for updating definitions.</span></span>
</li>
</ol>
</li>
<li><span data-ttu-id="0e5a6-1080">Ejecute un examen completo.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1080">Run a full scan.</span></span>
</li>
<li><span data-ttu-id="0e5a6-1081">Reinicie el dispositivo e inténtelo de nuevo.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1081">Restart the device and try again.</span></span></li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="0e5a6-1082">Código de error: 0x80508020</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1082">Error code: 0x80508020</span></span></th>
</tr><tr><td><span data-ttu-id="0e5a6-1083">Mensaje</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1083">Message</span></span></td>
<td><span data-ttu-id="0e5a6-1084"><b>ERR_MP_BAD_CONFIGURATION </b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1084"><b>ERR_MP_BAD_CONFIGURATION </b>
</span></span></td></tr><tr><td><span data-ttu-id="0e5a6-1085">Posible motivo</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1085">Possible reason</span></span></td>
<td>
<span data-ttu-id="0e5a6-1086">Este error indica que puede haber un error de configuración del motor; normalmente, esto está relacionado con datos de entrada que no permiten que el motor funcione correctamente.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1086">This error indicates that there might be an engine configuration error; commonly, this is related to input data that does not allow the engine to function properly.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="0e5a6-1087">Código de error: 0x805080211</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1087">Error code: 0x805080211</span></span>
</th>
</tr><tr><td><span data-ttu-id="0e5a6-1088">Mensaje</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1088">Message</span></span></td>
<td><span data-ttu-id="0e5a6-1089"><b>ERR_MP_QUARANTINE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1089"><b>ERR_MP_QUARANTINE_FAILED </b>
</span></span></td></tr><tr><td><span data-ttu-id="0e5a6-1090">Posible motivo</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1090">Possible reason</span></span></td>
<td>
<span data-ttu-id="0e5a6-1091">Este error indica que Antivirus de Microsoft Defender no pudo poner en cuarentena una amenaza.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1091">This error indicates that Microsoft Defender Antivirus failed to quarantine a threat.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="0e5a6-1092">Código de error: 0x80508022</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1092">Error code: 0x80508022</span></span>
</th>
</tr><tr><td><span data-ttu-id="0e5a6-1093">Mensaje</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1093">Message</span></span></td>
<td><span data-ttu-id="0e5a6-1094"><b>ERR_MP_REBOOT_REQUIRED </b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1094"><b>ERR_MP_REBOOT_REQUIRED </b>
</span></span></td></tr><tr><td><span data-ttu-id="0e5a6-1095">Posible motivo</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1095">Possible reason</span></span></td>
<td>
<span data-ttu-id="0e5a6-1096">Este error indica que se requiere un reinicio para completar la eliminación de amenazas.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1096">This error indicates that a reboot is required to complete threat removal.</span></span> 
</td>
</tr>
<tr>
<th colspan="2">
<span data-ttu-id="0e5a6-1097">0x80508023</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1097">0x80508023</span></span>
</th>
</tr><tr><td><span data-ttu-id="0e5a6-1098">Mensaje</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1098">Message</span></span></td>
<td><span data-ttu-id="0e5a6-1099"><b>ERR_MP_THREAT_NOT_FOUND </b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1099"><b>ERR_MP_THREAT_NOT_FOUND </b>
</span></span></td></tr><tr><td><span data-ttu-id="0e5a6-1100">Posible motivo</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1100">Possible reason</span></span></td>
<td>
<span data-ttu-id="0e5a6-1101">Este error indica que es posible que la amenaza ya no esté presente en los medios o que el malware pueda impedir que se pueda examinar el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1101">This error indicates that the threat might no longer be present on the media, or malware might be stopping you from scanning your device.</span></span> 
</tr><tr><td><span data-ttu-id="0e5a6-1102">Solución</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1102">Resolution</span></span>
</td>
<td>
<span data-ttu-id="0e5a6-1103">Ejecute el <a href="https://www.microsoft.com/security/scanner/default.aspx">Examen de seguridad de Microsoft,</a> a continuación, actualice el software de seguridad e inténtelo de nuevo.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1103">Run the <a href="https://www.microsoft.com/security/scanner/default.aspx">Microsoft Safety Scanner</a> then update your security software and try again.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="0e5a6-1104">Código de error: 0x80508024</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1104">Error code: 0x80508024</span></span> </th></tr>
<tr>
<td><span data-ttu-id="0e5a6-1105">Mensaje</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1105">Message</span></span></td>
<td><span data-ttu-id="0e5a6-1106"><b>ERR_MP_FULL_SCAN_REQUIRED </b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1106"><b>ERR_MP_FULL_SCAN_REQUIRED </b>
</span></span></td></tr><tr><td><span data-ttu-id="0e5a6-1107">Posible motivo</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1107">Possible reason</span></span></td>
<td>
<span data-ttu-id="0e5a6-1108">Este error indica que puede ser necesario realizar un examen completo del sistema.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1108">This error indicates that a full system scan might be required.</span></span> 
</td></tr>
<tr>
<td><span data-ttu-id="0e5a6-1109">Solución</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1109">Resolution</span></span></td><td>
<span data-ttu-id="0e5a6-1110">Ejecute un examen completo del sistema.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1110">Run a full system scan.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="0e5a6-1111">Código de error: 0x80508025</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1111">Error code: 0x80508025</span></span>
</th>
</tr><tr><td><span data-ttu-id="0e5a6-1112">Mensaje</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1112">Message</span></span></td>
<td><span data-ttu-id="0e5a6-1113"><b>ERR_MP_MANUAL_STEPS_REQUIRED </b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1113"><b>ERR_MP_MANUAL_STEPS_REQUIRED </b>
</span></span></td></tr><tr><td><span data-ttu-id="0e5a6-1114">Posible motivo</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1114">Possible reason</span></span></td>
<td>
<span data-ttu-id="0e5a6-1115">Este error indica que se requieren pasos manuales para completar la eliminación de amenazas.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1115">This error indicates that manual steps are required to complete threat removal.</span></span> 
</td></tr><tr><td><span data-ttu-id="0e5a6-1116">Solución</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1116">Resolution</span></span></td><td>
<span data-ttu-id="0e5a6-1117">Siga los pasos de corrección manuales descritos en la Enciclopedia de Protección contra malware <a href="https://www.microsoft.com/security/portal/threat/Threats.aspx">de Microsoft</a>.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1117">Follow the manual remediation steps outlined in the <a href="https://www.microsoft.com/security/portal/threat/Threats.aspx">Microsoft Malware Protection Encyclopedia</a>.</span></span> <span data-ttu-id="0e5a6-1118">Puede encontrar un vínculo específico de la amenaza en el historial de eventos.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1118">You can find a threat-specific link in the event history.</span></span><br/></td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="0e5a6-1119">Código de error: 0x80508026</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1119">Error code: 0x80508026</span></span>
</th>
</tr><tr><td><span data-ttu-id="0e5a6-1120">Mensaje</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1120">Message</span></span></td>
<td><span data-ttu-id="0e5a6-1121"><b>ERR_MP_REMOVE_NOT_SUPPORTED </b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1121"><b>ERR_MP_REMOVE_NOT_SUPPORTED </b>
</span></span></td></tr><tr><td><span data-ttu-id="0e5a6-1122">Posible motivo</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1122">Possible reason</span></span></td>
<td>
<span data-ttu-id="0e5a6-1123">Este error indica que es posible que no se pueda quitar dentro del tipo de contenedor.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1123">This error indicates that removal inside the container type might not be not supported.</span></span> 
</td></tr><tr><td><span data-ttu-id="0e5a6-1124">Solución</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1124">Resolution</span></span></td><td>
<span data-ttu-id="0e5a6-1125">Antivirus de Microsoft Defender no es capaz de corregir las amenazas detectadas dentro del archivo.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1125">Microsoft Defender Antivirus is not able to remediate threats detected inside the archive.</span></span> <span data-ttu-id="0e5a6-1126">Considere la posibilidad de quitar manualmente los recursos detectados.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1126">Consider manually removing the detected resources.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="0e5a6-1127">Código de error: 0x80508027</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1127">Error code: 0x80508027</span></span>
</th>
</tr><tr><td><span data-ttu-id="0e5a6-1128">Mensaje</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1128">Message</span></span></td>
<td><span data-ttu-id="0e5a6-1129"><b>ERR_MP_REMOVE_LOW_MEDIUM_DISABLED </b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1129"><b>ERR_MP_REMOVE_LOW_MEDIUM_DISABLED </b>
</span></span></td></tr><tr><td><span data-ttu-id="0e5a6-1130">Posible motivo</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1130">Possible reason</span></span></td>
<td>
<span data-ttu-id="0e5a6-1131">Este error indica que la eliminación de amenazas medias y bajas podría deshabilitarse.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1131">This error indicates that removal of low and medium threats might be disabled.</span></span> 
</td></tr><tr><td><span data-ttu-id="0e5a6-1132">Solución</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1132">Resolution</span></span></td><td>
<span data-ttu-id="0e5a6-1133">Compruebe las amenazas detectadas y resuelvalas según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1133">Check the detected threats and resolve them as required.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="0e5a6-1134">Código de error: 0x80508029</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1134">Error code: 0x80508029</span></span>
</th>
</tr><tr><td><span data-ttu-id="0e5a6-1135">Mensaje</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1135">Message</span></span></td>
<td><span data-ttu-id="0e5a6-1136"><b>ERROR_MP_RESCAN_REQUIRED </b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1136"><b>ERROR_MP_RESCAN_REQUIRED </b>
</span></span></td></tr><tr><td><span data-ttu-id="0e5a6-1137">Posible motivo</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1137">Possible reason</span></span></td>
<td>
<span data-ttu-id="0e5a6-1138">Este error indica que es necesario volver a examinar la amenaza.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1138">This error indicates a rescan of the threat is required.</span></span> 
</td></tr><tr><td><span data-ttu-id="0e5a6-1139">Solución</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1139">Resolution</span></span></td><td>
<span data-ttu-id="0e5a6-1140">Ejecute un examen completo del sistema.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1140">Run a full system scan.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="0e5a6-1141">Código de error: 0x80508030</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1141">Error code: 0x80508030</span></span>
</th>
</tr><tr><td><span data-ttu-id="0e5a6-1142">Mensaje</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1142">Message</span></span></td>
<td><span data-ttu-id="0e5a6-1143"><b>ERROR_MP_CALLISTO_REQUIRED </b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1143"><b>ERROR_MP_CALLISTO_REQUIRED </b>
</span></span></td></tr><tr><td><span data-ttu-id="0e5a6-1144">Posible motivo</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1144">Possible reason</span></span></td>
<td>
<span data-ttu-id="0e5a6-1145">Este error indica que es necesario realizar un examen sin conexión.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1145">This error indicates that an offline scan is required.</span></span> 
</td></tr><tr><td><span data-ttu-id="0e5a6-1146">Solución</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1146">Resolution</span></span></td><td>
<span data-ttu-id="0e5a6-1147">Ejecute sin conexión Antivirus de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1147">Run offline Microsoft Defender Antivirus.</span></span> <span data-ttu-id="0e5a6-1148">Puede leer sobre cómo hacerlo en el artículo <a href="https://windows.microsoft.com/windows/what-is-windows-defender-offline">sin conexión Antivirus de Microsoft Defender .</a></span><span class="sxs-lookup"><span data-stu-id="0e5a6-1148">You can read about how to do this in the <a href="https://windows.microsoft.com/windows/what-is-windows-defender-offline">offline Microsoft Defender Antivirus article</a>.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="0e5a6-1149">Código de error: 0x80508031</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1149">Error code: 0x80508031</span></span>
</th>
</tr><tr><td><span data-ttu-id="0e5a6-1150">Mensaje</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1150">Message</span></span></td>
<td><span data-ttu-id="0e5a6-1151"><b>ERROR_MP_PLATFORM_OUTDATED</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1151"><b>ERROR_MP_PLATFORM_OUTDATED</span></span><br/></b>
</td></tr><tr><td><span data-ttu-id="0e5a6-1152">Posible motivo</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1152">Possible reason</span></span></td>
<td>
<span data-ttu-id="0e5a6-1153">Este error indica que Antivirus de Microsoft Defender no admite la versión actual de la plataforma y requiere una nueva versión de la plataforma.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1153">This error indicates that Microsoft Defender Antivirus does not support the current version of the platform and requires a new version of the platform.</span></span> 
</td></tr><tr><td><span data-ttu-id="0e5a6-1154">Solución</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1154">Resolution</span></span></td><td>
<span data-ttu-id="0e5a6-1155">Solo puede usar Antivirus de Microsoft Defender en Windows 10.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1155">You can only use Microsoft Defender Antivirus in Windows 10.</span></span> <span data-ttu-id="0e5a6-1156">Para Windows 8, Windows 7 y Windows Vista, puede usar <a href="https://www.microsoft.com/server-cloud/system-center/endpoint-protection-2012.aspx">System Center Endpoint Protection</a>.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1156">For Windows 8, Windows 7 and Windows Vista, you can use <a href="https://www.microsoft.com/server-cloud/system-center/endpoint-protection-2012.aspx">System Center Endpoint Protection</a>.</span></span><br/></td>
</tr>
</table><span data-ttu-id="0e5a6-1157">

<a id="internal-error-codes"></a>Los siguientes códigos de error se usan durante las pruebas internas de Antivirus de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1157">

<a id="internal-error-codes"></a> The following error codes are used during internal testing of Microsoft Defender Antivirus.</span></span>

<span data-ttu-id="0e5a6-1158">Si ve estos errores, puede [](manage-updates-baselines-microsoft-defender-antivirus.md) intentar actualizar definiciones y forzar un nuevo análisis directamente en el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1158">If you see these errors, you can try to [update definitions](manage-updates-baselines-microsoft-defender-antivirus.md) and force a rescan directly on the endpoint.</span></span>


<table> 
<tr>
<th colspan="3"><span data-ttu-id="0e5a6-1159">Códigos de error internos</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1159">Internal error codes</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="0e5a6-1160"><b>Código de error</b></span><span class="sxs-lookup"><span data-stu-id="0e5a6-1160"><b>Error code</b></span></span></th>
<th><span data-ttu-id="0e5a6-1161">Mensaje mostrado</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1161">Message displayed</span></span></th>
<th><span data-ttu-id="0e5a6-1162">Posible motivo de error y resolución</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1162">Possible reason for error and resolution</span></span></th>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-1163">0x80501004</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1163">0x80501004</span></span>
</td>
<td><span data-ttu-id="0e5a6-1164">
<b>ERROR_MP_NO_INTERNET_CONN </b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1164">
<b>ERROR_MP_NO_INTERNET_CONN </b>
</span></span></td>
<td>
<span data-ttu-id="0e5a6-1165">Compruebe la conexión a Internet y vuelva a ejecutar el examen.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1165">Check your Internet connection, then run the scan again.</span></span>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-1166">0x80501000</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1166">0x80501000</span></span>
</td>
<td><span data-ttu-id="0e5a6-1167">
<b>ERROR_MP_UI_CONSOLIDATION_BAS</b> E</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1167">
<b>ERROR_MP_UI_CONSOLIDATION_BAS</b>E</span></span>
</td>
<td rowspan="34">
<span data-ttu-id="0e5a6-1168">Se trata de un error interno.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1168">This is an internal error.</span></span> <span data-ttu-id="0e5a6-1169">La causa no está claramente definida.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1169">The cause is not clearly defined.</span></span>
</td>
<td rowspan="36">

</td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-1170">0x80501001</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1170">0x80501001</span></span>
</td>
<td><span data-ttu-id="0e5a6-1171">
<b>ERROR_MP_ACTIONS_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1171">
<b>ERROR_MP_ACTIONS_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-1172">0x80501002</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1172">0x80501002</span></span>
</td>
<td><span data-ttu-id="0e5a6-1173">
<b>ERROR_MP_NOENGINE</b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1173">
<b>ERROR_MP_NOENGINE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-1174">0x80501003</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1174">0x80501003</span></span>
</td>
<td><span data-ttu-id="0e5a6-1175">
<b>ERROR_MP_ACTIVE_THREATS</b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1175">
<b>ERROR_MP_ACTIVE_THREATS</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-1176">0x805011011</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1176">0x805011011</span></span>
</td>
<td><span data-ttu-id="0e5a6-1177">
<b>MP_ERROR_CODE_LUA_CANCELLED </b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1177">
<b>MP_ERROR_CODE_LUA_CANCELLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-1178">0x80501101</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1178">0x80501101</span></span>
</td>
<td><span data-ttu-id="0e5a6-1179">
<b>ERROR_LUA_CANCELLATION </b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1179">
<b>ERROR_LUA_CANCELLATION </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-1180">0x80501102</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1180">0x80501102</span></span>
</td>
<td><span data-ttu-id="0e5a6-1181">
<b>MP_ERROR_CODE_ALREADY_SHUTDOWN</b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1181">
<b>MP_ERROR_CODE_ALREADY_SHUTDOWN</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-1182">0x80501103</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1182">0x80501103</span></span>
</td>
<td><span data-ttu-id="0e5a6-1183">
<b>MP_ERROR_CODE_RDEVICE_S_ASYNC_CALL_PENDING </b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1183">
<b>MP_ERROR_CODE_RDEVICE_S_ASYNC_CALL_PENDING </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-1184">0x80501104</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1184">0x80501104</span></span>
</td>
<td><span data-ttu-id="0e5a6-1185">
<b>MP_ERROR_CODE_CANCELLED</b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1185">
<b>MP_ERROR_CODE_CANCELLED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-1186">0x80501105</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1186">0x80501105</span></span>
</td>
<td><span data-ttu-id="0e5a6-1187">
<b>MP_ERROR_CODE_NO_TARGETOS</b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1187">
<b>MP_ERROR_CODE_NO_TARGETOS</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-1188">0x80501106</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1188">0x80501106</span></span>
</td>
<td><span data-ttu-id="0e5a6-1189">
<b>MP_ERROR_CODE_BAD_REGEXP</b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1189">
<b>MP_ERROR_CODE_BAD_REGEXP</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-1190">0x80501107</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1190">0x80501107</span></span>
</td>
<td><span data-ttu-id="0e5a6-1191">
<b>MP_ERROR_TEST_INDUCED_ERROR</b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1191">
<b>MP_ERROR_TEST_INDUCED_ERROR</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-1192">0x80501108</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1192">0x80501108</span></span>
</td>
<td><span data-ttu-id="0e5a6-1193">
<b>MP_ERROR_SIG_BACKUP_DISABLED</b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1193">
<b>MP_ERROR_SIG_BACKUP_DISABLED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-1194">0x80508001</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1194">0x80508001</span></span>
</td>
<td><span data-ttu-id="0e5a6-1195">
<b>ERR_MP_BAD_INIT_MODULES</b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1195">
<b>ERR_MP_BAD_INIT_MODULES</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-1196">0x80508002</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1196">0x80508002</span></span>
</td>
<td><span data-ttu-id="0e5a6-1197">
<b>ERR_MP_BAD_DATABASE</b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1197">
<b>ERR_MP_BAD_DATABASE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-1198">0x80508004</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1198">0x80508004</span></span>
</td>
<td><span data-ttu-id="0e5a6-1199">
<b>ERR_MP_BAD_UFS </b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1199">
<b>ERR_MP_BAD_UFS </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-1200">0x8050800C</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1200">0x8050800C</span></span>
</td>
<td><span data-ttu-id="0e5a6-1201">
<b>ERR_MP_BAD_INPUT_DATA</b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1201">
<b>ERR_MP_BAD_INPUT_DATA</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-1202">0x8050800D</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1202">0x8050800D</span></span>
</td>
<td><span data-ttu-id="0e5a6-1203">
<b>ERR_MP_BAD_GLOBAL_STORAGE</b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1203">
<b>ERR_MP_BAD_GLOBAL_STORAGE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-1204">0x8050800E</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1204">0x8050800E</span></span>
</td>
<td><span data-ttu-id="0e5a6-1205">
<b>ERR_MP_OBSOLETE</b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1205">
<b>ERR_MP_OBSOLETE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-1206">0x8050800F</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1206">0x8050800F</span></span>
</td>
<td><span data-ttu-id="0e5a6-1207">
<b>ERR_MP_NOT_SUPPORTED</b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1207">
<b>ERR_MP_NOT_SUPPORTED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-1208">0x8050800F 0x80508010</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1208">0x8050800F 0x80508010</span></span>
</td>
<td><span data-ttu-id="0e5a6-1209">
<b>ERR_MP_NO_MORE_ITEMS </b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1209">
<b>ERR_MP_NO_MORE_ITEMS </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-1210">0x80508011</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1210">0x80508011</span></span>
</td>
<td><span data-ttu-id="0e5a6-1211">
<b>ERR_MP_DUPLICATE_SCANID</b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1211">
<b>ERR_MP_DUPLICATE_SCANID</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-1212">0x80508012</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1212">0x80508012</span></span>
</td>
<td><span data-ttu-id="0e5a6-1213">
<b>ERR_MP_BAD_SCANID</b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1213">
<b>ERR_MP_BAD_SCANID</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-1214">0x80508013</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1214">0x80508013</span></span>
</td>
<td><span data-ttu-id="0e5a6-1215">
<b>ERR_MP_BAD_USERDB_VERSION</b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1215">
<b>ERR_MP_BAD_USERDB_VERSION</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-1216">0x80508014</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1216">0x80508014</span></span>
</td>
<td><span data-ttu-id="0e5a6-1217">
<b>ERR_MP_RESTORE_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1217">
<b>ERR_MP_RESTORE_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-1218">0x80508016</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1218">0x80508016</span></span>
</td>
<td><span data-ttu-id="0e5a6-1219">
<b>ERR_MP_BAD_ACTION</b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1219">
<b>ERR_MP_BAD_ACTION</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-1220">0x80508019</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1220">0x80508019</span></span>
</td>
<td><span data-ttu-id="0e5a6-1221">
<b>ERR_MP_NOT_FOUND</b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1221">
<b>ERR_MP_NOT_FOUND</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-1222">0x80509001</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1222">0x80509001</span></span>
</td>
<td><span data-ttu-id="0e5a6-1223">
<b>ERR_RELO_BAD_EHANDLE</b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1223">
<b>ERR_RELO_BAD_EHANDLE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-1224">0x80509003</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1224">0x80509003</span></span>
</td>
<td><span data-ttu-id="0e5a6-1225">
<b>ERR_RELO_KERNEL_NOT_LOADED</b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1225">
<b>ERR_RELO_KERNEL_NOT_LOADED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-1226">0x8050A001</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1226">0x8050A001</span></span>
</td>
<td><span data-ttu-id="0e5a6-1227">
<b>ERR_MP_BADDB_OPEN</b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1227">
<b>ERR_MP_BADDB_OPEN</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-1228">0x8050A002</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1228">0x8050A002</span></span>
</td>
<td><span data-ttu-id="0e5a6-1229">
<b>ERR_MP_BADDB_HEADER</b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1229">
<b>ERR_MP_BADDB_HEADER</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-1230">0x8050A003</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1230">0x8050A003</span></span>
</td>
<td><span data-ttu-id="0e5a6-1231">
<b>ERR_MP_BADDB_OLDENGINE</b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1231">
<b>ERR_MP_BADDB_OLDENGINE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-1232">0x8050A004</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1232">0x8050A004</span></span>
</td>
<td><span data-ttu-id="0e5a6-1233">
<b>ERR_MP_BADDB_CONTENT </b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1233">
<b>ERR_MP_BADDB_CONTENT </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-1234">0x8050A005</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1234">0x8050A005</span></span>
</td>
<td><span data-ttu-id="0e5a6-1235">
<b>ERR_MP_BADDB_NOTSIGNED</b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1235">
<b>ERR_MP_BADDB_NOTSIGNED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-1236">0x8050801</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1236">0x8050801</span></span>
</td>
<td><span data-ttu-id="0e5a6-1237">
<b>ERR_MP_REMOVE_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1237">
<b>ERR_MP_REMOVE_FAILED</b>
</span></span></td>
<td>
<span data-ttu-id="0e5a6-1238">Se trata de un error interno.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1238">This is an internal error.</span></span> <span data-ttu-id="0e5a6-1239">Puede desencadenarse cuando la eliminación de malware no se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1239">It might be triggered when malware removal is not successful.</span></span> 
</td>
</tr>
<tr>
<td>
<span data-ttu-id="0e5a6-1240">0x80508018</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1240">0x80508018</span></span>
</td>
<td><span data-ttu-id="0e5a6-1241">
<b>ERR_MP_SCAN_ABORTED </b>
</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1241">
<b>ERR_MP_SCAN_ABORTED </b>
</span></span></td>
<td>
<span data-ttu-id="0e5a6-1242">Se trata de un error interno.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1242">This is an internal error.</span></span> <span data-ttu-id="0e5a6-1243">Puede que se haya desencadenado cuando un examen no se completa.</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1243">It might have triggered when a scan fails to complete.</span></span> 
</td>
</tr>
</table>

## <a name="related-topics"></a><span data-ttu-id="0e5a6-1244">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1244">Related topics</span></span>

- [<span data-ttu-id="0e5a6-1245">Informe sobre la Antivirus de Microsoft Defender protección</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1245">Report on Microsoft Defender Antivirus protection</span></span>](report-monitor-microsoft-defender-antivirus.md)
- [<span data-ttu-id="0e5a6-1246">Antivirus de Microsoft Defender en Windows 10</span><span class="sxs-lookup"><span data-stu-id="0e5a6-1246">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)