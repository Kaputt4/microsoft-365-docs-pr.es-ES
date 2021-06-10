---
title: Revisar eventos y errores con el Visor de eventos
description: Obtenga descripciones y pasos de solución de problemas adicionales (si es necesario) para todos los eventos notificados por el servicio de Microsoft Defender para puntos de conexión.
keywords: troubleshoot, event viewer, log summary, failure code, failed, Microsoft Defender for Endpoint service, can't start, broken, can't start
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 05/21/2018
ms.technology: mde
ms.openlocfilehash: a8b7268e89470a85a34015967b69abb1818fe64f
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933846"
---
# <a name="review-events-and-errors-using-event-viewer"></a><span data-ttu-id="5bfcd-104">Revisar eventos y errores con el Visor de eventos</span><span class="sxs-lookup"><span data-stu-id="5bfcd-104">Review events and errors using Event Viewer</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="5bfcd-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="5bfcd-105">**Applies to:**</span></span>
- <span data-ttu-id="5bfcd-106">Visor de eventos</span><span class="sxs-lookup"><span data-stu-id="5bfcd-106">Event Viewer</span></span>
- [<span data-ttu-id="5bfcd-107">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="5bfcd-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="5bfcd-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5bfcd-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="5bfcd-109">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="5bfcd-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="5bfcd-110">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)

<span data-ttu-id="5bfcd-111">Puedes revisar los IDs de eventos en el [Visor de eventos](https://msdn.microsoft.com/library/aa745633(v=bts.10).aspx) en dispositivos individuales.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-111">You can review event IDs in the [Event Viewer](https://msdn.microsoft.com/library/aa745633(v=bts.10).aspx) on individual devices.</span></span>

<span data-ttu-id="5bfcd-112">Por ejemplo, si los dispositivos no aparecen en la lista Dispositivos, es posible que deba buscar los ID de eventos en los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-112">For example, if devices aren't appearing in the **Devices list**, you might need to look for event IDs on the devices.</span></span> <span data-ttu-id="5bfcd-113">A continuación, puede usar esta tabla para determinar los pasos de solución de problemas adicionales.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-113">You can then use this table to determine further troubleshooting steps.</span></span>

<span data-ttu-id="5bfcd-114">**Abra el Visor de eventos y busque el registro de eventos de servicio de Microsoft Defender para puntos de conexión:**</span><span class="sxs-lookup"><span data-stu-id="5bfcd-114">**Open Event Viewer and find the Microsoft Defender for Endpoint service event log:**</span></span>

1. <span data-ttu-id="5bfcd-115">Haga **clic en** Inicio en Windows menú, escriba Visor de **eventos** y presione **Entrar**.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-115">Click **Start** on the Windows menu, type **Event Viewer**, and press **Enter**.</span></span>

2. <span data-ttu-id="5bfcd-116">En la lista de registros, en **Resumen del registro,** desplácese hasta que vea **Microsoft-Windows-SENSE/Operational**.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-116">In the log list, under **Log Summary**, scroll until you see **Microsoft-Windows-SENSE/Operational**.</span></span> <span data-ttu-id="5bfcd-117">Haga doble clic en el elemento para abrir el registro.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-117">Double-click the item to open the log.</span></span>

   <span data-ttu-id="5bfcd-118">a.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-118">a.</span></span>  <span data-ttu-id="5bfcd-119">También puede obtener acceso al registro expandiendo **Registros** de aplicaciones y servicios  >  **microsoft**  >  **Windows**  >  **SENSE** y haga clic en **Operativo**.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-119">You can also access the log by expanding **Applications and Services Logs** > **Microsoft** > **Windows** > **SENSE** and click on **Operational**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="5bfcd-120">SENSE es el nombre interno que se usa para hacer referencia al sensor de comportamiento que potencia Microsoft Defender para Endpoint.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-120">SENSE is the internal name used to refer to the behavioral sensor that powers Microsoft Defender for Endpoint.</span></span>

3. <span data-ttu-id="5bfcd-121">Los eventos registrados por el servicio aparecerán en el registro.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-121">Events recorded by the service will appear in the log.</span></span> <span data-ttu-id="5bfcd-122">Vea la tabla siguiente para obtener una lista de eventos registrados por el servicio.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-122">See the following table for a list of events recorded by the service.</span></span>

<table>
<tbody style="vertical-align:top;">
<tr>
<th><span data-ttu-id="5bfcd-123">Identificador de evento</span><span class="sxs-lookup"><span data-stu-id="5bfcd-123">Event ID</span></span></th>
<th><span data-ttu-id="5bfcd-124">Mensaje</span><span class="sxs-lookup"><span data-stu-id="5bfcd-124">Message</span></span></th>
<th><span data-ttu-id="5bfcd-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="5bfcd-125">Description</span></span></th>
<th><span data-ttu-id="5bfcd-126">Acción</span><span class="sxs-lookup"><span data-stu-id="5bfcd-126">Action</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="5bfcd-127">1</span><span class="sxs-lookup"><span data-stu-id="5bfcd-127">1</span></span></td>
<td><span data-ttu-id="5bfcd-128">Se inició el servicio de Microsoft Defender para puntos de conexión <code>variable</code> (versión).</span><span class="sxs-lookup"><span data-stu-id="5bfcd-128">Microsoft Defender for Endpoint service started (Version <code>variable</code>).</span></span></td>
<td><span data-ttu-id="5bfcd-129">Se produce durante el inicio, apagado y durante la incorporación del sistema.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-129">Occurs during system startup, shut down, and during onboarding.</span></span></td>
<td><span data-ttu-id="5bfcd-130">Notificación de funcionamiento normal; no se requiere ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-130">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfcd-131">2</span><span class="sxs-lookup"><span data-stu-id="5bfcd-131">2</span></span></td>
<td><span data-ttu-id="5bfcd-132">Cierre del servicio de Microsoft Defender para puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-132">Microsoft Defender for Endpoint service shutdown.</span></span></td>
<td><span data-ttu-id="5bfcd-133">Se produce cuando el dispositivo se apaga o se apaga.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-133">Occurs when the device is shut down or offboarded.</span></span></td>
<td><span data-ttu-id="5bfcd-134">Notificación de funcionamiento normal; no se requiere ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-134">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfcd-135">3</span><span class="sxs-lookup"><span data-stu-id="5bfcd-135">3</span></span></td>
<td><span data-ttu-id="5bfcd-136">Microsoft Defender para el servicio de extremo no se pudo iniciar.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-136">Microsoft Defender for Endpoint service failed to start.</span></span> <span data-ttu-id="5bfcd-137">Código de error: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="5bfcd-137">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="5bfcd-138">El servicio no se ha empezado.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-138">Service didn't start.</span></span></td>
<td><span data-ttu-id="5bfcd-139">Revise otros mensajes para determinar posibles causas y pasos de solución de problemas.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-139">Review other messages to determine possible cause and troubleshooting steps.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfcd-140">4 </span><span class="sxs-lookup"><span data-stu-id="5bfcd-140">4</span></span></td>
<td><span data-ttu-id="5bfcd-141">Microsoft Defender para el servicio de extremo se puso en contacto con el servidor en <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="5bfcd-141">Microsoft Defender for Endpoint service contacted the server at <code>variable</code>.</span></span></td>
<td><span data-ttu-id="5bfcd-142">Variable = dirección URL de los servidores de procesamiento de Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-142">Variable = URL of the Defender for Endpoint processing servers.</span></span><br>
<span data-ttu-id="5bfcd-143">Esta dirección URL coincidirá con la que se ve en el Firewall o la actividad de red.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-143">This URL will match that seen in the Firewall or network activity.</span></span></td>
<td><span data-ttu-id="5bfcd-144">Notificación de funcionamiento normal; no se requiere ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-144">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfcd-145">5 </span><span class="sxs-lookup"><span data-stu-id="5bfcd-145">5</span></span></td>
<td><span data-ttu-id="5bfcd-146">Microsoft Defender para el servicio de extremo no se pudo conectar al servidor en <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="5bfcd-146">Microsoft Defender for Endpoint service failed to connect to the server at <code>variable</code>.</span></span></td>
<td><span data-ttu-id="5bfcd-147">Variable = dirección URL de los servidores de procesamiento de Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-147">Variable = URL of the Defender for Endpoint processing servers.</span></span><br>
<span data-ttu-id="5bfcd-148">El servicio no pudo ponerse en contacto con los servidores de procesamiento externos en esa dirección URL.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-148">The service couldn't contact the external processing servers at that URL.</span></span></td>
<td><span data-ttu-id="5bfcd-149">Compruebe la conexión a la dirección URL.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-149">Check the connection to the URL.</span></span> <span data-ttu-id="5bfcd-150">Consulte <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">Configure proxy and Internet connectivity</a>.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-150">See <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">Configure proxy and Internet connectivity</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfcd-151">6 </span><span class="sxs-lookup"><span data-stu-id="5bfcd-151">6</span></span></td>
<td><span data-ttu-id="5bfcd-152">El servicio de Microsoft Defender para puntos de conexión no está incorporado y no se encontraron parámetros de incorporación.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-152">Microsoft Defender for Endpoint service is not onboarded and no onboarding parameters were found.</span></span></td>
<td><span data-ttu-id="5bfcd-153">El dispositivo no se incorporó correctamente y no se va a informar al portal.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-153">The device didn't onboard correctly and won't be reporting to the portal.</span></span></td>
<td><span data-ttu-id="5bfcd-154">La incorporación debe ejecutarse antes de iniciar el servicio.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-154">Onboarding must be run before starting the service.</span></span><br>
<span data-ttu-id="5bfcd-155">Compruebe que la configuración de incorporación y los scripts se implementaron correctamente.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-155">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="5bfcd-156">Intente volver a implementar los paquetes de configuración.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-156">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="5bfcd-157">Consulta <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Incorporación Windows 10 dispositivos</a>.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-157">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfcd-158">7 </span><span class="sxs-lookup"><span data-stu-id="5bfcd-158">7</span></span></td>
<td><span data-ttu-id="5bfcd-159">Microsoft Defender para el servicio de extremo no pudo leer los parámetros de incorporación.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-159">Microsoft Defender for Endpoint service failed to read the onboarding parameters.</span></span> <span data-ttu-id="5bfcd-160">Error: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="5bfcd-160">Failure: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="5bfcd-161">Variable = descripción detallada del error.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-161">Variable = detailed error description.</span></span> <span data-ttu-id="5bfcd-162">El dispositivo no se incorporó correctamente y no se va a informar al portal.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-162">The device didn't onboard correctly and won't be reporting to the portal.</span></span></td>
<td><span data-ttu-id="5bfcd-163">Compruebe que la configuración de incorporación y los scripts se implementaron correctamente.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-163">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="5bfcd-164">Intente volver a implementar los paquetes de configuración.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-164">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="5bfcd-165">Consulta <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Incorporación Windows 10 dispositivos</a>.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-165">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfcd-166">8 </span><span class="sxs-lookup"><span data-stu-id="5bfcd-166">8</span></span></td>
<td><span data-ttu-id="5bfcd-167">Microsoft Defender para el servicio de extremo no pudo limpiar su configuración.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-167">Microsoft Defender for Endpoint service failed to clean its configuration.</span></span> <span data-ttu-id="5bfcd-168">Código de error: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="5bfcd-168">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="5bfcd-169"><b>Durante la incorporación:</b> El servicio no pudo limpiar su configuración durante la incorporación.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-169"><b>During onboarding:</b> The service failed to clean its configuration during the onboarding.</span></span> <span data-ttu-id="5bfcd-170">El proceso de incorporación continúa.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-170">The onboarding process continues.</span></span> <br><br> <span data-ttu-id="5bfcd-171"><b>Durante el offboarding:</b> El servicio no pudo limpiar su configuración durante el offboarding.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-171"><b>During offboarding:</b> The service failed to clean its configuration during the offboarding.</span></span> <span data-ttu-id="5bfcd-172">El proceso de offboarding ha finalizado, pero el servicio sigue ejecutándose.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-172">The offboarding process finished but the service keeps running.</span></span>
 </td>
<td><span data-ttu-id="5bfcd-173"><b>Incorporación:</b> No se requiere ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-173"><b>Onboarding:</b> No action required.</span></span> <br><br> <span data-ttu-id="5bfcd-174"><b>Offboarding:</b> Reinicie el sistema.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-174"><b>Offboarding:</b> Reboot the system.</span></span><br>
<span data-ttu-id="5bfcd-175">Consulta <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Incorporación Windows 10 dispositivos</a>.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-175">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfcd-176">9 </span><span class="sxs-lookup"><span data-stu-id="5bfcd-176">9</span></span></td>
<td><span data-ttu-id="5bfcd-177">Microsoft Defender para el servicio de extremo no pudo cambiar su tipo de inicio.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-177">Microsoft Defender for Endpoint service failed to change its start type.</span></span> <span data-ttu-id="5bfcd-178">Código de error: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="5bfcd-178">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="5bfcd-179"><b>Durante la incorporación:</b> El dispositivo no se incorporó correctamente y no se va a informar al portal.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-179"><b>During onboarding:</b> The device didn't onboard correctly and won't be reporting to the portal.</span></span> <br><br><span data-ttu-id="5bfcd-180"><b>Durante el offboarding:</b> No se pudo cambiar el tipo de inicio del servicio.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-180"><b>During offboarding:</b> Failed to change the service start type.</span></span> <span data-ttu-id="5bfcd-181">El proceso de offboarding continúa.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-181">The offboarding process continues.</span></span> </td>
<td><span data-ttu-id="5bfcd-182">Compruebe que la configuración de incorporación y los scripts se implementaron correctamente.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-182">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="5bfcd-183">Intente volver a implementar los paquetes de configuración.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-183">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="5bfcd-184">Consulta <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Incorporación Windows 10 dispositivos</a>.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-184">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfcd-185">10</span><span class="sxs-lookup"><span data-stu-id="5bfcd-185">10</span></span></td>
<td><span data-ttu-id="5bfcd-186">Microsoft Defender para el servicio de extremo no pudo conservar la información de incorporación.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-186">Microsoft Defender for Endpoint service failed to persist the onboarding information.</span></span> <span data-ttu-id="5bfcd-187">Código de error: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="5bfcd-187">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="5bfcd-188">El dispositivo no se incorporó correctamente y no se va a informar al portal.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-188">The device didn't onboard correctly and won't be reporting to the portal.</span></span></td>
<td><span data-ttu-id="5bfcd-189">Compruebe que la configuración de incorporación y los scripts se implementaron correctamente.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-189">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="5bfcd-190">Intente volver a implementar los paquetes de configuración.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-190">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="5bfcd-191">Consulta <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Incorporación Windows 10 dispositivos</a>.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-191">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfcd-192">11</span><span class="sxs-lookup"><span data-stu-id="5bfcd-192">11</span></span></td>
<td><span data-ttu-id="5bfcd-193">Se completó la incorporación o la incorporación de Defender para el servicio de extremo.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-193">Onboarding or re-onboarding of Defender for Endpoint service completed.</span></span></td>
<td><span data-ttu-id="5bfcd-194">El dispositivo se incorporó correctamente.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-194">The device onboarded correctly.</span></span></td>
<td><span data-ttu-id="5bfcd-195">Notificación de funcionamiento normal; no se requiere ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-195">Normal operating notification; no action required.</span></span><br>
<span data-ttu-id="5bfcd-196">El dispositivo puede tardar varias horas en aparecer en el portal.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-196">It may take several hours for the device to appear in the portal.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfcd-197">12 </span><span class="sxs-lookup"><span data-stu-id="5bfcd-197">12</span></span></td>
<td><span data-ttu-id="5bfcd-198">Microsoft Defender para endpoint no pudo aplicar la configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-198">Microsoft Defender for Endpoint failed to apply the default configuration.</span></span></td>
<td><span data-ttu-id="5bfcd-199">El servicio no pudo aplicar la configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-199">Service was unable to apply the default configuration.</span></span></td>
<td><span data-ttu-id="5bfcd-200">Este error debe resolverse después de un breve período de tiempo.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-200">This error should resolve after a short period of time.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfcd-201">13</span><span class="sxs-lookup"><span data-stu-id="5bfcd-201">13</span></span></td>
<td><span data-ttu-id="5bfcd-202">Microsoft Defender para el identificador de dispositivo de extremo calculado: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="5bfcd-202">Microsoft Defender for Endpoint device ID calculated: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="5bfcd-203">Proceso operativo normal.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-203">Normal operating process.</span></span></td>
<td><span data-ttu-id="5bfcd-204">Notificación de funcionamiento normal; no se requiere ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-204">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfcd-205">15</span><span class="sxs-lookup"><span data-stu-id="5bfcd-205">15</span></span></td>
<td><span data-ttu-id="5bfcd-206">Microsoft Defender para endpoint no puede iniciar el canal de comandos con dirección URL: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="5bfcd-206">Microsoft Defender for Endpoint cannot start command channel with URL: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="5bfcd-207">Variable = dirección URL de los servidores de procesamiento de Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-207">Variable = URL of the Defender for Endpoint processing servers.</span></span><br>
<span data-ttu-id="5bfcd-208">El servicio no pudo ponerse en contacto con los servidores de procesamiento externos en esa dirección URL.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-208">The service couldn't contact the external processing servers at that URL.</span></span></td>
<td><span data-ttu-id="5bfcd-209">Compruebe la conexión a la dirección URL.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-209">Check the connection to the URL.</span></span> <span data-ttu-id="5bfcd-210">Consulte <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">Configure proxy and Internet connectivity</a>.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-210">See <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">Configure proxy and Internet connectivity</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfcd-211">17 </span><span class="sxs-lookup"><span data-stu-id="5bfcd-211">17</span></span></td>
<td><span data-ttu-id="5bfcd-212">Microsoft Defender para el servicio de extremo no pudo cambiar la ubicación del servicio Telemetría y experiencias del usuario conectado.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-212">Microsoft Defender for Endpoint service failed to change the Connected User Experiences and Telemetry service location.</span></span> <span data-ttu-id="5bfcd-213">Código de error: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="5bfcd-213">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="5bfcd-214">Se produjo un error con el servicio Windows telemetría.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-214">An error occurred with the Windows telemetry service.</span></span></td>
<td><span data-ttu-id="5bfcd-215"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Asegúrese de que el servicio de datos de diagnóstico está habilitado.</a></span><span class="sxs-lookup"><span data-stu-id="5bfcd-215"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Ensure the diagnostic data service is enabled</a>.</span></span><br>
<span data-ttu-id="5bfcd-216">Compruebe que la configuración de incorporación y los scripts se implementaron correctamente.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-216">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="5bfcd-217">Intente volver a implementar los paquetes de configuración.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-217">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="5bfcd-218">Consulta <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Incorporación Windows 10 dispositivos</a>.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-218">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfcd-219">18 </span><span class="sxs-lookup"><span data-stu-id="5bfcd-219">18</span></span></td>
<td><span data-ttu-id="5bfcd-220">OOBE (Windows bienvenida) se ha completado.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-220">OOBE (Windows Welcome) is completed.</span></span></td>
<td><span data-ttu-id="5bfcd-221">El servicio solo se iniciará después de que Windows actualizaciones haya terminado de instalarse.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-221">Service will only start after any Windows updates have finished installing.</span></span></td>
<td><span data-ttu-id="5bfcd-222">Notificación de funcionamiento normal; no se requiere ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-222">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfcd-223">19</span><span class="sxs-lookup"><span data-stu-id="5bfcd-223">19</span></span></td>
<td><span data-ttu-id="5bfcd-224">OOBE (Windows bienvenida) aún no se ha completado.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-224">OOBE (Windows Welcome) has not yet completed.</span></span></td>
<td><span data-ttu-id="5bfcd-225">El servicio solo se iniciará después de que Windows actualizaciones haya terminado de instalarse.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-225">Service will only start after any Windows updates have finished installing.</span></span></td>
<td><span data-ttu-id="5bfcd-226">Notificación de funcionamiento normal; no se requiere ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-226">Normal operating notification; no action required.</span></span><br>
<span data-ttu-id="5bfcd-227">Si este error persiste después de reiniciar el sistema, asegúrese de que todas Windows actualizaciones se han instalado por completo.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-227">If this error persists after a system restart, ensure all Windows updates have full installed.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfcd-228">20</span><span class="sxs-lookup"><span data-stu-id="5bfcd-228">20</span></span></td>
<td><span data-ttu-id="5bfcd-229">No se puede esperar a que se complete la OOBE (Windows welcome).</span><span class="sxs-lookup"><span data-stu-id="5bfcd-229">Cannot wait for OOBE (Windows Welcome) to complete.</span></span> <span data-ttu-id="5bfcd-230">Código de error: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="5bfcd-230">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="5bfcd-231">Error interno.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-231">Internal error.</span></span></td>
<td><span data-ttu-id="5bfcd-232">Si este error persiste después de reiniciar el sistema, asegúrese de que todas Windows actualizaciones se han instalado por completo.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-232">If this error persists after a system restart, ensure all Windows updates have full installed.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfcd-233">25</span><span class="sxs-lookup"><span data-stu-id="5bfcd-233">25</span></span></td>
<td><span data-ttu-id="5bfcd-234">Microsoft Defender para el servicio de extremo no pudo restablecer el estado de mantenimiento en el Registro.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-234">Microsoft Defender for Endpoint service failed to reset health status in the registry.</span></span> <span data-ttu-id="5bfcd-235">Código de error: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="5bfcd-235">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="5bfcd-236">El dispositivo no se incorporó correctamente.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-236">The device didn't onboard correctly.</span></span>
<span data-ttu-id="5bfcd-237">Se presentará en el portal, pero es posible que el servicio no aparezca como registrado en SCCM o en el Registro.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-237">It will report to the portal, however the service may not appear as registered in SCCM or the registry.</span></span></td>
<td><span data-ttu-id="5bfcd-238">Compruebe que la configuración de incorporación y los scripts se implementaron correctamente.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-238">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="5bfcd-239">Intente volver a implementar los paquetes de configuración.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-239">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="5bfcd-240">Consulta <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Incorporación Windows 10 dispositivos</a>.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-240">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfcd-241">26</span><span class="sxs-lookup"><span data-stu-id="5bfcd-241">26</span></span></td>
<td><span data-ttu-id="5bfcd-242">Microsoft Defender para el servicio de extremo no pudo establecer el estado de incorporación en el Registro.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-242">Microsoft Defender for Endpoint service failed to set the onboarding status in the registry.</span></span> <span data-ttu-id="5bfcd-243">Código de error: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="5bfcd-243">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="5bfcd-244">El dispositivo no se incorporó correctamente.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-244">The device didn't onboard correctly.</span></span><br>
<span data-ttu-id="5bfcd-245">Se presentará en el portal, pero es posible que el servicio no aparezca como registrado en SCCM o en el Registro.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-245">It will report to the portal, however the service may not appear as registered in SCCM or the registry.</span></span></td>
<td><span data-ttu-id="5bfcd-246">Compruebe que la configuración de incorporación y los scripts se implementaron correctamente.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-246">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="5bfcd-247">Intente volver a implementar los paquetes de configuración.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-247">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="5bfcd-248">Consulta <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Incorporación Windows 10 dispositivos</a>.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-248">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfcd-249">27</span><span class="sxs-lookup"><span data-stu-id="5bfcd-249">27</span></span></td>
<td><span data-ttu-id="5bfcd-250">El servicio de Microsoft Defender para puntos de conexión no pudo habilitar el modo consciente de SENSE en Antivirus de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-250">Microsoft Defender for Endpoint service failed to enable SENSE aware mode in Microsoft Defender Antivirus.</span></span> <span data-ttu-id="5bfcd-251">Error en el proceso de incorporación.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-251">Onboarding process failed.</span></span> <span data-ttu-id="5bfcd-252">Código de error: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="5bfcd-252">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="5bfcd-253">Normalmente, Antivirus de Microsoft Defender un estado pasivo especial si otro producto antimalware en tiempo real se ejecuta correctamente en el dispositivo y el dispositivo informa a Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-253">Normally, Microsoft Defender Antivirus will enter a special passive state if another real-time antimalware product is running properly on the device, and the device is reporting to Defender for Endpoint.</span></span></td>
<td><span data-ttu-id="5bfcd-254">Compruebe que la configuración de incorporación y los scripts se implementaron correctamente.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-254">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="5bfcd-255">Intente volver a implementar los paquetes de configuración.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-255">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="5bfcd-256">Consulta <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Incorporación Windows 10 dispositivos</a>.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-256">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span><br>
<span data-ttu-id="5bfcd-257">Asegúrese de que la protección antimalware en tiempo real se está ejecutando correctamente.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-257">Ensure real-time antimalware protection is running properly.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfcd-258">28</span><span class="sxs-lookup"><span data-stu-id="5bfcd-258">28</span></span></td>
<td><span data-ttu-id="5bfcd-259">Error en el registro del servicio de telemetría y experiencias de usuario conectado de Microsoft Defender para puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-259">Microsoft Defender for Endpoint Connected User Experiences and Telemetry service registration failed.</span></span> <span data-ttu-id="5bfcd-260">Código de error: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="5bfcd-260">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="5bfcd-261">Se produjo un error con el servicio Windows telemetría.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-261">An error occurred with the Windows telemetry service.</span></span></td>
<td><span data-ttu-id="5bfcd-262"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Asegúrese de que el servicio de datos de diagnóstico está habilitado.</a></span><span class="sxs-lookup"><span data-stu-id="5bfcd-262"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Ensure the diagnostic data service is enabled</a>.</span></span><br>
<span data-ttu-id="5bfcd-263">Compruebe que la configuración de incorporación y los scripts se implementaron correctamente.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-263">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="5bfcd-264">Intente volver a implementar los paquetes de configuración.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-264">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="5bfcd-265">Consulta <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Incorporación Windows 10 dispositivos</a>.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-265">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfcd-266">29</span><span class="sxs-lookup"><span data-stu-id="5bfcd-266">29</span></span></td>
<td><span data-ttu-id="5bfcd-267">No se pudieron leer los parámetros de offboarding.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-267">Failed to read the offboarding parameters.</span></span> <span data-ttu-id="5bfcd-268">Tipo de error: %1, Código de error: %2, Descripción: %3</span><span class="sxs-lookup"><span data-stu-id="5bfcd-268">Error type: %1, Error code: %2, Description: %3</span></span> </td>
<td><span data-ttu-id="5bfcd-269">Este evento se produce cuando el sistema&#39;leer los parámetros de offboarding.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-269">This event occurs when the system can&#39;t read the offboarding parameters.</span></span></td>
<td><span data-ttu-id="5bfcd-270">Asegúrate de que el dispositivo tiene acceso a Internet y, a continuación, vuelve a ejecutar todo el proceso de offboarding.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-270">Ensure the device has Internet access, then run the entire offboarding process again.</span></span> <span data-ttu-id="5bfcd-271">Asegúrese de que el paquete de offboarding no ha expirado.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-271">Ensure the offboarding package hasn't expired.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfcd-272">30</span><span class="sxs-lookup"><span data-stu-id="5bfcd-272">30</span></span></td>
<td><span data-ttu-id="5bfcd-273">Microsoft Defender para el servicio de extremo no pudo deshabilitar el modo consciente de SENSE en Antivirus de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-273">Microsoft Defender for Endpoint service failed to disable SENSE aware mode in Microsoft Defender Antivirus.</span></span> <span data-ttu-id="5bfcd-274">Código de error: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="5bfcd-274">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="5bfcd-275">Normalmente, Antivirus de Microsoft Defender un estado pasivo especial si otro producto antimalware en tiempo real se ejecuta correctamente en el dispositivo y el dispositivo informa a Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-275">Normally, Microsoft Defender Antivirus will enter a special passive state if another real-time antimalware product is running properly on the device, and the device is reporting to Defender for Endpoint.</span></span></td>
<td><span data-ttu-id="5bfcd-276">Compruebe que la configuración de incorporación y los scripts se implementaron correctamente.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-276">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="5bfcd-277">Intente volver a implementar los paquetes de configuración.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-277">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="5bfcd-278">Consulta <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Incorporación Windows 10 dispositivos</a></span><span class="sxs-lookup"><span data-stu-id="5bfcd-278">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a></span></span><br>
<span data-ttu-id="5bfcd-279">Asegúrese de que la protección antimalware en tiempo real se está ejecutando correctamente.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-279">Ensure real-time antimalware protection is running properly.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfcd-280">31</span><span class="sxs-lookup"><span data-stu-id="5bfcd-280">31</span></span></td>
<td><span data-ttu-id="5bfcd-281">Error en la anulación de la registro de Microsoft Defender para experiencias de usuario conectadas a puntos de conexión y servicio de telemetría.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-281">Microsoft Defender for Endpoint Connected User Experiences and Telemetry service unregistration failed.</span></span> <span data-ttu-id="5bfcd-282">Código de error: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="5bfcd-282">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="5bfcd-283">Se produjo un error con el Windows de telemetría durante la incorporación.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-283">An error occurred with the Windows telemetry service during onboarding.</span></span> <span data-ttu-id="5bfcd-284">El proceso de offboarding continúa.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-284">The offboarding process continues.</span></span></td>
<td><span data-ttu-id="5bfcd-285"><a href="troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled" data-raw-source="[Check for errors with the Windows telemetry service](troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled)">Compruebe si hay errores con el servicio Windows telemetría</a>.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-285"><a href="troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled" data-raw-source="[Check for errors with the Windows telemetry service](troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled)">Check for errors with the Windows telemetry service</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfcd-286">32</span><span class="sxs-lookup"><span data-stu-id="5bfcd-286">32</span></span></td>
<td><span data-ttu-id="5bfcd-287">Microsoft Defender para el servicio de extremo no pudo solicitar que se detuviera después del proceso de desaborde.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-287">Microsoft Defender for Endpoint service failed to request to stop itself after offboarding process.</span></span> <span data-ttu-id="5bfcd-288">Código de error: %1</span><span class="sxs-lookup"><span data-stu-id="5bfcd-288">Failure code: %1</span></span></td>
<td><span data-ttu-id="5bfcd-289">Se produjo un error durante el offboarding.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-289">An error occurred during offboarding.</span></span></td>
<td><span data-ttu-id="5bfcd-290">Reinicie el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-290">Reboot the device.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfcd-291">33</span><span class="sxs-lookup"><span data-stu-id="5bfcd-291">33</span></span></td>
<td><span data-ttu-id="5bfcd-292">Microsoft Defender para el servicio de extremo no pudo conservar EL GUID DE SENSE.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-292">Microsoft Defender for Endpoint service failed to persist SENSE GUID.</span></span> <span data-ttu-id="5bfcd-293">Código de error: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="5bfcd-293">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="5bfcd-294">Se usa un identificador único para representar cada dispositivo que está informando al portal.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-294">A unique identifier is used to represent each device that is reporting to the portal.</span></span><br>
<span data-ttu-id="5bfcd-295">Si el identificador no persiste, es posible que el mismo dispositivo aparezca dos veces en el portal.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-295">If the identifier doesn't persist, the same device might appear twice in the portal.</span></span></td>
<td><span data-ttu-id="5bfcd-296">Compruebe los permisos del Registro en el dispositivo para asegurarse de que el servicio puede actualizar el Registro.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-296">Check registry permissions on the device to ensure the service can update the registry.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfcd-297">34</span><span class="sxs-lookup"><span data-stu-id="5bfcd-297">34</span></span></td>
<td><span data-ttu-id="5bfcd-298">Microsoft Defender para el servicio de extremo no pudo agregarse a sí mismo como dependencia del servicio de telemetría y experiencias del usuario conectado, lo que provocó un error en el proceso de incorporación.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-298">Microsoft Defender for Endpoint service failed to add itself as a dependency on the Connected User Experiences and Telemetry service, causing onboarding process to fail.</span></span> <span data-ttu-id="5bfcd-299">Código de error: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="5bfcd-299">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="5bfcd-300">Se produjo un error con el servicio Windows telemetría.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-300">An error occurred with the Windows telemetry service.</span></span></td>
<td><span data-ttu-id="5bfcd-301"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Asegúrese de que el servicio de datos de diagnóstico está habilitado.</a></span><span class="sxs-lookup"><span data-stu-id="5bfcd-301"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Ensure the diagnostic data service is enabled</a>.</span></span><br>
<span data-ttu-id="5bfcd-302">Compruebe que la configuración de incorporación y los scripts se implementaron correctamente.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-302">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="5bfcd-303">Intente volver a implementar los paquetes de configuración.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-303">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="5bfcd-304">Consulta <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Incorporación Windows 10 dispositivos</a>.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-304">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfcd-305">35</span><span class="sxs-lookup"><span data-stu-id="5bfcd-305">35</span></span></td>
<td><span data-ttu-id="5bfcd-306">Microsoft Defender para el servicio de extremo no pudo quitarse a sí mismo como dependencia del servicio telemetría y experiencias del usuario conectado.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-306">Microsoft Defender for Endpoint service failed to remove itself as a dependency on the Connected User Experiences and Telemetry service.</span></span> <span data-ttu-id="5bfcd-307">Código de error: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="5bfcd-307">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="5bfcd-308">Se produjo un error con el Windows de telemetría durante el offboarding.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-308">An error occurred with the Windows telemetry service during offboarding.</span></span> <span data-ttu-id="5bfcd-309">El proceso de offboarding continúa.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-309">The offboarding process continues.</span></span>
</td>
<td><span data-ttu-id="5bfcd-310">Compruebe si hay errores con el Windows de datos de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-310">Check for errors with the Windows diagnostic data service.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfcd-311">36</span><span class="sxs-lookup"><span data-stu-id="5bfcd-311">36</span></span></td>
<td><span data-ttu-id="5bfcd-312">El registro del servicio de telemetría y experiencias de usuario conectado de Microsoft Defender para endpoints se ha correcto.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-312">Microsoft Defender for Endpoint Connected User Experiences and Telemetry service registration succeeded.</span></span> <span data-ttu-id="5bfcd-313">Código de finalización: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="5bfcd-313">Completion code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="5bfcd-314">El registro de Defender para endpoint con el servicio de telemetría y experiencias del usuario conectado se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-314">Registering Defender for Endpoint with the Connected User Experiences and Telemetry service completed successfully.</span></span></td>
<td><span data-ttu-id="5bfcd-315">Notificación de funcionamiento normal; no se requiere ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-315">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfcd-316">37</span><span class="sxs-lookup"><span data-stu-id="5bfcd-316">37</span></span></td>
<td><span data-ttu-id="5bfcd-317">El módulo De punto de conexión A de Microsoft Defender está a punto de superar su cuota.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-317">Microsoft Defender for Endpoint A module is about to exceed its quota.</span></span> <span data-ttu-id="5bfcd-318">Módulo: %1, Cuota: {%2} {%3}, Porcentaje de utilización de la cuota: %4.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-318">Module: %1, Quota: {%2} {%3}, Percentage of quota utilization: %4.</span></span></td>
<td><span data-ttu-id="5bfcd-319">El dispositivo casi ha usado su cuota asignada de la ventana actual de 24 horas.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-319">The device has almost used its allocated quota of the current 24-hour window.</span></span> <span data-ttu-id="5bfcd-320">Está a punto de limitarse.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-320">It’s about to be throttled.</span></span></td>
<td><span data-ttu-id="5bfcd-321">Notificación de funcionamiento normal; no se requiere ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-321">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfcd-322">38</span><span class="sxs-lookup"><span data-stu-id="5bfcd-322">38</span></span></td>
<td><span data-ttu-id="5bfcd-323">La conexión de red se identifica como baja.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-323">Network connection is identified as low.</span></span> <span data-ttu-id="5bfcd-324">Microsoft Defender para endpoint se pondrá en contacto con el servidor cada %1 minuto.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-324">Microsoft Defender for Endpoint will contact the server every %1 minutes.</span></span> <span data-ttu-id="5bfcd-325">Conexión medida: %2, Internet disponible: %3, red gratuita disponible: %4.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-325">Metered connection: %2, internet available: %3, free network available: %4.</span></span></td>
<td><span data-ttu-id="5bfcd-326">El dispositivo usa una red de pago y medición y se pondrá en contacto con el servidor con menos frecuencia.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-326">The device is using a metered/paid network and will be contacting the server less frequently.</span></span></td>
<td><span data-ttu-id="5bfcd-327">Notificación de funcionamiento normal; no se requiere ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-327">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfcd-328">39</span><span class="sxs-lookup"><span data-stu-id="5bfcd-328">39</span></span></td>
<td><span data-ttu-id="5bfcd-329">La conexión de red se identifica como normal.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-329">Network connection is identified as normal.</span></span> <span data-ttu-id="5bfcd-330">Microsoft Defender para endpoint se pondrá en contacto con el servidor cada %1 minuto.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-330">Microsoft Defender for Endpoint will contact the server every %1 minutes.</span></span> <span data-ttu-id="5bfcd-331">Conexión medida: %2, Internet disponible: %3, red gratuita disponible: %4.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-331">Metered connection: %2, internet available: %3, free network available: %4.</span></span></td>
<td><span data-ttu-id="5bfcd-332">El dispositivo no usa una conexión de pago o de medición y se pondrá en contacto con el servidor como de costumbre.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-332">The device isn't using a metered/paid connection and will contact the server as usual.</span></span></td>
<td><span data-ttu-id="5bfcd-333">Notificación de funcionamiento normal; no se requiere ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-333">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfcd-334">40</span><span class="sxs-lookup"><span data-stu-id="5bfcd-334">40</span></span></td>
<td><span data-ttu-id="5bfcd-335">El estado de la batería se identifica como bajo.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-335">Battery state is identified as low.</span></span> <span data-ttu-id="5bfcd-336">Microsoft Defender para endpoint se pondrá en contacto con el servidor cada %1 minuto.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-336">Microsoft Defender for Endpoint will contact the server every %1 minutes.</span></span> <span data-ttu-id="5bfcd-337">Estado de la batería: %2.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-337">Battery state: %2.</span></span></td>
<td><span data-ttu-id="5bfcd-338">El dispositivo tiene un nivel de batería bajo y se pondrá en contacto con el servidor con menos frecuencia.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-338">The device has low battery level and will contact the server less frequently.</span></span></td>
<td><span data-ttu-id="5bfcd-339">Notificación de funcionamiento normal; no se requiere ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-339">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfcd-340">41</span><span class="sxs-lookup"><span data-stu-id="5bfcd-340">41</span></span></td>
<td><span data-ttu-id="5bfcd-341">El estado de la batería se identifica como normal.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-341">Battery state is identified as normal.</span></span> <span data-ttu-id="5bfcd-342">Microsoft Defender para endpoint se pondrá en contacto con el servidor cada %1 minuto.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-342">Microsoft Defender for Endpoint will contact the server every %1 minutes.</span></span> <span data-ttu-id="5bfcd-343">Estado de la batería: %2.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-343">Battery state: %2.</span></span></td>
<td><span data-ttu-id="5bfcd-344">El dispositivo no tiene bajo nivel de batería y se pondrá en contacto con el servidor como de costumbre.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-344">The device doesn’t have low battery level and will contact the server as usual.</span></span></td>
<td><span data-ttu-id="5bfcd-345">Notificación de funcionamiento normal; no se requiere ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-345">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfcd-346">42</span><span class="sxs-lookup"><span data-stu-id="5bfcd-346">42</span></span></td>
<td><span data-ttu-id="5bfcd-347">El componente de Microsoft Defender para extremo no pudo realizar la acción.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-347">Microsoft Defender for Endpoint component failed to perform action.</span></span> <span data-ttu-id="5bfcd-348">Componente: %1, Acción: %2, Tipo de excepción: %3, Mensaje de excepción: %4</span><span class="sxs-lookup"><span data-stu-id="5bfcd-348">Component: %1, Action: %2, Exception Type: %3, Exception message: %4</span></span></td>
<td><span data-ttu-id="5bfcd-349">Error interno.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-349">Internal error.</span></span> <span data-ttu-id="5bfcd-350">No se pudo iniciar el servicio.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-350">The service failed to start.</span></span></td>
<td><span data-ttu-id="5bfcd-351">Si este error persiste, póngase en contacto con el soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-351">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfcd-352">43</span><span class="sxs-lookup"><span data-stu-id="5bfcd-352">43</span></span></td>
<td><span data-ttu-id="5bfcd-353">El componente de Microsoft Defender para extremo no pudo realizar la acción.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-353">Microsoft Defender for Endpoint component failed to perform action.</span></span> <span data-ttu-id="5bfcd-354">Componente: %1, Acción: %2, Tipo de excepción: %3, Error de excepción: %4, Mensaje de excepción: %5</span><span class="sxs-lookup"><span data-stu-id="5bfcd-354">Component: %1, Action: %2, Exception Type: %3, Exception Error: %4, Exception message: %5</span></span></td>
<td><span data-ttu-id="5bfcd-355">Error interno.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-355">Internal error.</span></span> <span data-ttu-id="5bfcd-356">No se pudo iniciar el servicio.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-356">The service failed to start.</span></span></td>
<td><span data-ttu-id="5bfcd-357">Si este error persiste, póngase en contacto con el soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-357">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfcd-358">44</span><span class="sxs-lookup"><span data-stu-id="5bfcd-358">44</span></span></td>
<td><span data-ttu-id="5bfcd-359">Offboarding of Defender for Endpoint service completed.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-359">Offboarding of Defender for Endpoint service completed.</span></span></td>
<td><span data-ttu-id="5bfcd-360">El servicio se ha desactivado.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-360">The service was offboarded.</span></span></td>
<td><span data-ttu-id="5bfcd-361">Notificación de funcionamiento normal; no se requiere ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-361">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfcd-362">45</span><span class="sxs-lookup"><span data-stu-id="5bfcd-362">45</span></span></td>
<td><span data-ttu-id="5bfcd-363">Error al registrar e iniciar la sesión de seguimiento de eventos [%1].</span><span class="sxs-lookup"><span data-stu-id="5bfcd-363">Failed to register and to start the event trace session [%1].</span></span> <span data-ttu-id="5bfcd-364">Código de error: %2</span><span class="sxs-lookup"><span data-stu-id="5bfcd-364">Error code: %2</span></span></td>
<td><span data-ttu-id="5bfcd-365">Se produjo un error al iniciar el servicio al crear la sesión etw.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-365">An error occurred on service startup while creating ETW session.</span></span> <span data-ttu-id="5bfcd-366">Esto provocó un error de inicio del servicio.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-366">This caused service start-up failure.</span></span></td>
<td><span data-ttu-id="5bfcd-367">Si este error persiste, póngase en contacto con el soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-367">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfcd-368">46</span><span class="sxs-lookup"><span data-stu-id="5bfcd-368">46</span></span></td>
<td><span data-ttu-id="5bfcd-369">No se pudo registrar e iniciar la sesión de seguimiento de eventos [%1] debido a la falta de recursos.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-369">Failed to register and start the event trace session [%1] due to lack of resources.</span></span> <span data-ttu-id="5bfcd-370">Código de error: %2.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-370">Error code: %2.</span></span> <span data-ttu-id="5bfcd-371">Esto es más probable porque hay demasiadas sesiones de seguimiento de eventos activos.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-371">This is most likely because there are too many active event trace sessions.</span></span> <span data-ttu-id="5bfcd-372">El servicio reintentará en 1 minuto.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-372">The service will retry in 1 minute.</span></span></td>
<td><span data-ttu-id="5bfcd-373">Se produjo un error al iniciar el servicio al crear una sesión de ETW debido a la falta de recursos.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-373">An error occurred on service startup while creating ETW session due to lack of resources.</span></span> <span data-ttu-id="5bfcd-374">El servicio se inició y se está ejecutando, pero no informa de ningún evento de sensor hasta que se inicia la sesión etw.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-374">The service started and is running, but won't report any sensor event until the ETW session is started.</span></span></td>
<td><span data-ttu-id="5bfcd-375">Notificación de funcionamiento normal; no se requiere ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-375">Normal operating notification; no action required.</span></span> <span data-ttu-id="5bfcd-376">El servicio intentará iniciar la sesión cada minuto.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-376">The service will try to start the session every minute.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfcd-377">47</span><span class="sxs-lookup"><span data-stu-id="5bfcd-377">47</span></span></td>
<td><span data-ttu-id="5bfcd-378">Se registró correctamente e inició la sesión de seguimiento de eventos, recuperada después de intentos fallidos anteriores.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-378">Successfully registered and started the event trace session - recovered after previous failed attempts.</span></span></td>
<td><span data-ttu-id="5bfcd-379">Este evento sigue al evento anterior después de iniciar correctamente la sesión etw.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-379">This event follows the previous event after successfully starting of the ETW session.</span></span></td>
<td><span data-ttu-id="5bfcd-380">Notificación de funcionamiento normal; no se requiere ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-380">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5bfcd-381">48</span><span class="sxs-lookup"><span data-stu-id="5bfcd-381">48</span></span></td>
<td><span data-ttu-id="5bfcd-382">No se pudo agregar un proveedor [%1] a la sesión de seguimiento de eventos [%2].</span><span class="sxs-lookup"><span data-stu-id="5bfcd-382">Failed to add a provider [%1] to event trace session [%2].</span></span> <span data-ttu-id="5bfcd-383">Código de error: %3.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-383">Error code: %3.</span></span> <span data-ttu-id="5bfcd-384">Esto significa que los eventos de este proveedor no se notifican.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-384">This means that events from this provider will not be reported.</span></span></td>
<td><span data-ttu-id="5bfcd-385">No se pudo agregar un proveedor a la sesión de ETW.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-385">Failed to add a provider to ETW session.</span></span> <span data-ttu-id="5bfcd-386">Como resultado, no se notifican los eventos del proveedor.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-386">As a result, the provider events aren’t reported.</span></span></td>
<td><span data-ttu-id="5bfcd-387">Compruebe el código de error.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-387">Check the error code.</span></span> <span data-ttu-id="5bfcd-388">Si el error persiste, póngase en contacto con el soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-388">If the error persists contact Support.</span></span></td>
</tr>
</tr>
<tr>
   <td><span data-ttu-id="5bfcd-389">49</span><span class="sxs-lookup"><span data-stu-id="5bfcd-389">49</span></span></td>
   <td><span data-ttu-id="5bfcd-390">Comando de configuración de nube no válido recibido e ignorado.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-390">Invalid cloud configuration command received and ignored.</span></span> <span data-ttu-id="5bfcd-391">Versión: %1, estado: %2, código de error: %3, mensaje: %4</span><span class="sxs-lookup"><span data-stu-id="5bfcd-391">Version: %1, status: %2, error code: %3, message: %4</span></span></td>
   <td><span data-ttu-id="5bfcd-392">Se ha recibido un archivo de configuración no válido del servicio en la nube que se ha omitido.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-392">Received an invalid configuration file from the cloud service that was ignored.</span></span></td>
   <td><span data-ttu-id="5bfcd-393">Si este error persiste, póngase en contacto con el soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-393">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="5bfcd-394">50</span><span class="sxs-lookup"><span data-stu-id="5bfcd-394">50</span></span></td>
   <td><span data-ttu-id="5bfcd-395">Nueva configuración de nube aplicada correctamente.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-395">New cloud configuration applied successfully.</span></span> <span data-ttu-id="5bfcd-396">Versión: %1.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-396">Version: %1.</span></span></td>
   <td><span data-ttu-id="5bfcd-397">Se aplicó correctamente una nueva configuración desde el servicio en la nube.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-397">Successfully applied a new configuration from the cloud service.</span></span></td>
   <td><span data-ttu-id="5bfcd-398">Notificación de funcionamiento normal; no se requiere ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-398">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="5bfcd-399">51</span><span class="sxs-lookup"><span data-stu-id="5bfcd-399">51</span></span></td>
   <td><span data-ttu-id="5bfcd-400">No se pudo aplicar la nueva configuración de nube, versión: %1.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-400">New cloud configuration failed to apply, version: %1.</span></span> <span data-ttu-id="5bfcd-401">Se aplicó correctamente la última configuración correcta conocida, versión %2.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-401">Successfully applied the last known good configuration, version %2.</span></span></td>
   <td><span data-ttu-id="5bfcd-402">Se ha recibido un archivo de configuración mal del servicio en la nube.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-402">Received a bad configuration file from the cloud service.</span></span> <span data-ttu-id="5bfcd-403">La última configuración correcta conocida se aplicó correctamente.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-403">Last known good configuration was applied successfully.</span></span></td>
   <td><span data-ttu-id="5bfcd-404">Si este error persiste, póngase en contacto con el soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-404">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="5bfcd-405">52</span><span class="sxs-lookup"><span data-stu-id="5bfcd-405">52</span></span></td>
   <td><span data-ttu-id="5bfcd-406">No se pudo aplicar la nueva configuración de nube, versión: %1.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-406">New cloud configuration failed to apply, version: %1.</span></span> <span data-ttu-id="5bfcd-407">Tampoco se pudo aplicar la última configuración correcta conocida, versión %2.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-407">Also failed to apply last known good configuration, version %2.</span></span> <span data-ttu-id="5bfcd-408">Se aplicó correctamente la configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-408">Successfully applied the default configuration.</span></span></td>
   <td><span data-ttu-id="5bfcd-409">Se ha recibido un archivo de configuración mal del servicio en la nube.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-409">Received a bad configuration file from the cloud service.</span></span> <span data-ttu-id="5bfcd-410">No se pudo aplicar la última configuración buena conocida y se aplicó la configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-410">Failed to apply the last known good configuration - and the default configuration was applied.</span></span></td>
   <td><span data-ttu-id="5bfcd-411">El servicio intentará descargar un nuevo archivo de configuración en 5 minutos.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-411">The service will attempt to download a new configuration file within 5 minutes.</span></span> <span data-ttu-id="5bfcd-412">Si no ve el evento #50: póngase en contacto con el soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-412">If you don't see event #50 - contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="5bfcd-413">53</span><span class="sxs-lookup"><span data-stu-id="5bfcd-413">53</span></span></td>
   <td><span data-ttu-id="5bfcd-414">Configuración de nube cargada desde el almacenamiento persistente, versión: %1.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-414">Cloud configuration loaded from persistent storage, version: %1.</span></span></td>
   <td><span data-ttu-id="5bfcd-415">La configuración se cargó desde el almacenamiento persistente al iniciar el servicio.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-415">The configuration was loaded from persistent storage on service startup.</span></span></td>
   <td><span data-ttu-id="5bfcd-416">Notificación de funcionamiento normal; no se requiere ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-416">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="5bfcd-417">55</span><span class="sxs-lookup"><span data-stu-id="5bfcd-417">55</span></span></td>
   <td><span data-ttu-id="5bfcd-418">No se pudo crear el registrador automático de ETW seguro.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-418">Failed to create the Secure ETW autologger.</span></span> <span data-ttu-id="5bfcd-419">Código de error: %1</span><span class="sxs-lookup"><span data-stu-id="5bfcd-419">Failure code: %1</span></span></td>
   <td><span data-ttu-id="5bfcd-420">No se pudo crear el registrador ETW seguro.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-420">Failed to create the secure ETW logger.</span></span></td>
   <td><span data-ttu-id="5bfcd-421">Reinicie el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-421">Reboot the device.</span></span> <span data-ttu-id="5bfcd-422">Si este error persiste, póngase en contacto con el soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-422">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="5bfcd-423">56</span><span class="sxs-lookup"><span data-stu-id="5bfcd-423">56</span></span></td>
   <td><span data-ttu-id="5bfcd-424">No se pudo quitar el registrador automático de ETW seguro.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-424">Failed to remove the Secure ETW autologger.</span></span> <span data-ttu-id="5bfcd-425">Código de error: %1</span><span class="sxs-lookup"><span data-stu-id="5bfcd-425">Failure code: %1</span></span></td>
   <td><span data-ttu-id="5bfcd-426">No se pudo quitar la sesión de ETW segura en el offboarding.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-426">Failed to remove the secure ETW session on offboarding.</span></span></td>
   <td><span data-ttu-id="5bfcd-427">Póngase en contacto con el soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-427">Contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="5bfcd-428">57</span><span class="sxs-lookup"><span data-stu-id="5bfcd-428">57</span></span></td>
   <td><span data-ttu-id="5bfcd-429">Captura de una instantánea de la máquina para solucionar problemas.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-429">Capturing a snapshot of the machine for troubleshooting purposes.</span></span></td>
   <td><span data-ttu-id="5bfcd-430">Se está recopilando un paquete de investigación, también conocido como paquete forense.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-430">An investigation package, also known as forensics package, is being collected.</span></span></td>
   <td><span data-ttu-id="5bfcd-431">Notificación de funcionamiento normal; no se requiere ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-431">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="5bfcd-432">59</span><span class="sxs-lookup"><span data-stu-id="5bfcd-432">59</span></span></td>
   <td><span data-ttu-id="5bfcd-433">Comando inicio: %1</span><span class="sxs-lookup"><span data-stu-id="5bfcd-433">Starting command: %1</span></span></td>
   <td><span data-ttu-id="5bfcd-434">Iniciar la ejecución del comando de respuesta.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-434">Starting response command execution.</span></span></td>
   <td><span data-ttu-id="5bfcd-435">Notificación de funcionamiento normal; no se requiere ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-435">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="5bfcd-436">60</span><span class="sxs-lookup"><span data-stu-id="5bfcd-436">60</span></span></td>
   <td><span data-ttu-id="5bfcd-437">Error al ejecutar el comando %1, error: %2.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-437">Failed to run command %1, error: %2.</span></span></td>
   <td><span data-ttu-id="5bfcd-438">Error al ejecutar el comando response.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-438">Failed to execute response command.</span></span></td>
   <td><span data-ttu-id="5bfcd-439">Si este error persiste, póngase en contacto con el soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-439">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="5bfcd-440">61</span><span class="sxs-lookup"><span data-stu-id="5bfcd-440">61</span></span></td>
   <td><span data-ttu-id="5bfcd-441">Los parámetros de comando de la colección de datos no son válidos: SasUri: %1, compressionLevel: %2.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-441">Data collection command parameters are invalid: SasUri: %1, compressionLevel: %2.</span></span></td>
   <td><span data-ttu-id="5bfcd-442">No se pudo leer ni analizar los argumentos del comando de colección de datos (argumentos no válidos).</span><span class="sxs-lookup"><span data-stu-id="5bfcd-442">Failed to read or parse the data collection command arguments (invalid arguments).</span></span></td>
   <td><span data-ttu-id="5bfcd-443">Si este error persiste, póngase en contacto con el soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-443">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="5bfcd-444">62</span><span class="sxs-lookup"><span data-stu-id="5bfcd-444">62</span></span></td>
   <td><span data-ttu-id="5bfcd-445">No se pudo iniciar el servicio de telemetría y experiencias de usuario conectado.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-445">Failed to start Connected User Experiences and Telemetry service.</span></span> <span data-ttu-id="5bfcd-446">Código de error: %1</span><span class="sxs-lookup"><span data-stu-id="5bfcd-446">Failure code: %1</span></span></td>
   <td><span data-ttu-id="5bfcd-447">No se pudo iniciar el servicio de telemetría y experiencias de usuario conectados (diagtrack).</span><span class="sxs-lookup"><span data-stu-id="5bfcd-447">Connected User Experiences and Telemetry (diagtrack) service failed to start.</span></span> <span data-ttu-id="5bfcd-448">La telemetría que no sea de Microsoft Defender para puntos de conexión no se enviará desde este equipo.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-448">Non-Microsoft Defender for Endpoint telemetry won't be sent from this machine.</span></span></td>
   <td><span data-ttu-id="5bfcd-449">Busque más sugerencias de solución de problemas en el registro de eventos: Microsoft-Windows-UniversalTelemetryClient/Operational.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-449">Look for more troubleshooting hints in the event log: Microsoft-Windows-UniversalTelemetryClient/Operational.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="5bfcd-450">63</span><span class="sxs-lookup"><span data-stu-id="5bfcd-450">63</span></span></td>
   <td><span data-ttu-id="5bfcd-451">Actualizar el tipo de inicio del servicio externo.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-451">Updating the start type of external service.</span></span> <span data-ttu-id="5bfcd-452">Nombre: %1, tipo de inicio real: %2, tipo de inicio esperado: %3, código de salida: %4</span><span class="sxs-lookup"><span data-stu-id="5bfcd-452">Name: %1, actual start type: %2, expected start type: %3, exit code: %4</span></span></td>
   <td><span data-ttu-id="5bfcd-453">Tipo de inicio actualizado del servicio externo.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-453">Updated start type of the external service.</span></span></td>
   <td><span data-ttu-id="5bfcd-454">Notificación de funcionamiento normal; no se requiere ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-454">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="5bfcd-455">64</span><span class="sxs-lookup"><span data-stu-id="5bfcd-455">64</span></span></td>
   <td><span data-ttu-id="5bfcd-456">Inicio del servicio externo detenido.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-456">Starting stopped external service.</span></span> <span data-ttu-id="5bfcd-457">Nombre: %1, código de salida: %2</span><span class="sxs-lookup"><span data-stu-id="5bfcd-457">Name: %1, exit code: %2</span></span></td>
   <td><span data-ttu-id="5bfcd-458">Iniciar un servicio externo.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-458">Starting an external service.</span></span></td>
   <td><span data-ttu-id="5bfcd-459">Notificación de funcionamiento normal; no se requiere ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-459">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="5bfcd-460">65</span><span class="sxs-lookup"><span data-stu-id="5bfcd-460">65</span></span></td>
   <td><span data-ttu-id="5bfcd-461">No se pudo cargar el controlador de minifiltro de componentes de eventos de seguridad de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-461">Failed to load Microsoft Security Events Component Minifilter driver.</span></span> <span data-ttu-id="5bfcd-462">Código de error: %1</span><span class="sxs-lookup"><span data-stu-id="5bfcd-462">Failure code: %1</span></span></td>
   <td><span data-ttu-id="5bfcd-463">No se pudo cargar MsSecFlt.sys minifiltro del sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-463">Failed to load MsSecFlt.sys filesystem minifilter.</span></span></td>
   <td><span data-ttu-id="5bfcd-464">Reinicie el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-464">Reboot the device.</span></span> <span data-ttu-id="5bfcd-465">Si este error persiste, póngase en contacto con el soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-465">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="5bfcd-466">66</span><span class="sxs-lookup"><span data-stu-id="5bfcd-466">66</span></span></td>
   <td><span data-ttu-id="5bfcd-467">Actualización de directivas: Modo de latencia - %1</span><span class="sxs-lookup"><span data-stu-id="5bfcd-467">Policy update: Latency mode - %1</span></span></td>
   <td><span data-ttu-id="5bfcd-468">Se actualizó C# de frecuencia de conexión C de C&C.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-468">The C&C connection frequency policy was updated.</span></span></td>
   <td><span data-ttu-id="5bfcd-469">Notificación de funcionamiento normal; no se requiere ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-469">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="5bfcd-470">68</span><span class="sxs-lookup"><span data-stu-id="5bfcd-470">68</span></span></td>
   <td><span data-ttu-id="5bfcd-471">El tipo de inicio del servicio es inesperado.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-471">The start type of the service is unexpected.</span></span> <span data-ttu-id="5bfcd-472">Nombre del servicio: %1, tipo de inicio real: %2, tipo de inicio esperado: %3</span><span class="sxs-lookup"><span data-stu-id="5bfcd-472">Service name: %1, actual start type: %2, expected start type: %3</span></span></td>
   <td><span data-ttu-id="5bfcd-473">Tipo de inicio de servicio externo inesperado.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-473">Unexpected external service start type.</span></span></td>
   <td><span data-ttu-id="5bfcd-474">Corregir el tipo de inicio del servicio externo.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-474">Fix the external service start type.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="5bfcd-475">69</span><span class="sxs-lookup"><span data-stu-id="5bfcd-475">69</span></span></td>
   <td><span data-ttu-id="5bfcd-476">El servicio se detiene.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-476">The service is stopped.</span></span> <span data-ttu-id="5bfcd-477">Nombre del servicio: %1</span><span class="sxs-lookup"><span data-stu-id="5bfcd-477">Service name: %1</span></span></td>
   <td><span data-ttu-id="5bfcd-478">Se detiene el servicio externo.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-478">The external service is stopped.</span></span></td>
   <td><span data-ttu-id="5bfcd-479">Inicie el servicio externo.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-479">Start the external service.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="5bfcd-480">70</span><span class="sxs-lookup"><span data-stu-id="5bfcd-480">70</span></span></td>
   <td><span data-ttu-id="5bfcd-481">Actualización de directivas: permitir la colección de muestras - %1</span><span class="sxs-lookup"><span data-stu-id="5bfcd-481">Policy update: Allow sample collection - %1</span></span></td>
   <td><span data-ttu-id="5bfcd-482">Se actualizó la directiva de colección de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-482">The sample collection policy was updated.</span></span></td>
   <td><span data-ttu-id="5bfcd-483">Notificación de funcionamiento normal; no se requiere ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-483">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="5bfcd-484">71</span><span class="sxs-lookup"><span data-stu-id="5bfcd-484">71</span></span></td>
   <td><span data-ttu-id="5bfcd-485">Se ha ejecutado correctamente el comando: %1</span><span class="sxs-lookup"><span data-stu-id="5bfcd-485">Succeeded to run command: %1</span></span></td>
   <td><span data-ttu-id="5bfcd-486">El comando se ejecutó correctamente.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-486">The command was executed successfully.</span></span></td>
   <td><span data-ttu-id="5bfcd-487">Notificación de funcionamiento normal; no se requiere ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-487">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="5bfcd-488">72</span><span class="sxs-lookup"><span data-stu-id="5bfcd-488">72</span></span></td>
   <td><span data-ttu-id="5bfcd-489">Se intentó enviar el primer informe de perfil completo del equipo.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-489">Tried to send first full machine profile report.</span></span> <span data-ttu-id="5bfcd-490">Código de resultado: %1</span><span class="sxs-lookup"><span data-stu-id="5bfcd-490">Result code: %1</span></span></td>
   <td><span data-ttu-id="5bfcd-491">Solo informativo.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-491">Informational only.</span></span></td>
   <td><span data-ttu-id="5bfcd-492">Notificación de funcionamiento normal; no se requiere ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-492">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="5bfcd-493">73</span><span class="sxs-lookup"><span data-stu-id="5bfcd-493">73</span></span></td>
   <td><span data-ttu-id="5bfcd-494">Sense starting for platform: %1</span><span class="sxs-lookup"><span data-stu-id="5bfcd-494">Sense starting for platform: %1</span></span></td>
   <td><span data-ttu-id="5bfcd-495">Solo informativo.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-495">Informational only.</span></span></td>
   <td><span data-ttu-id="5bfcd-496">Notificación de funcionamiento normal; no se requiere ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-496">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="5bfcd-497">74</span><span class="sxs-lookup"><span data-stu-id="5bfcd-497">74</span></span></td>
   <td><span data-ttu-id="5bfcd-498">La etiqueta de dispositivo en el Registro supera el límite de longitud.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-498">Device tag in registry exceeds length limit.</span></span> <span data-ttu-id="5bfcd-499">Nombre de etiqueta: %2.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-499">Tag name: %2.</span></span> <span data-ttu-id="5bfcd-500">Límite de longitud: %1.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-500">Length limit: %1.</span></span></td>
   <td><span data-ttu-id="5bfcd-501">La etiqueta de dispositivo supera el límite de longitud.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-501">The device tag exceeds the length limit.</span></span></td>
   <td><span data-ttu-id="5bfcd-502">Usa una etiqueta de dispositivo más corta.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-502">Use a shorter device tag.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="5bfcd-503">81</span><span class="sxs-lookup"><span data-stu-id="5bfcd-503">81</span></span></td>
   <td><span data-ttu-id="5bfcd-504">No se pudo crear el registrador automático de ETW de Microsoft Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-504">Failed to create Microsoft Defender for Endpoint ETW autologger.</span></span> <span data-ttu-id="5bfcd-505">Código de error: %1</span><span class="sxs-lookup"><span data-stu-id="5bfcd-505">Failure code: %1</span></span></td>
   <td><span data-ttu-id="5bfcd-506">No se pudo crear la sesión etw.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-506">Failed to create the ETW session.</span></span></td>
   <td><span data-ttu-id="5bfcd-507">Reinicie el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-507">Reboot the device.</span></span> <span data-ttu-id="5bfcd-508">Si este error persiste, póngase en contacto con el soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-508">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="5bfcd-509">82</span><span class="sxs-lookup"><span data-stu-id="5bfcd-509">82</span></span></td>
   <td><span data-ttu-id="5bfcd-510">No se pudo quitar el registrador automático de ETW de Microsoft Defender para extremo.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-510">Failed to remove Microsoft Defender for Endpoint ETW autologger.</span></span> <span data-ttu-id="5bfcd-511">Código de error: %1</span><span class="sxs-lookup"><span data-stu-id="5bfcd-511">Failure code: %1</span></span></td>
   <td><span data-ttu-id="5bfcd-512">No se pudo eliminar la sesión etw.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-512">Failed to delete the ETW session.</span></span></td>
   <td><span data-ttu-id="5bfcd-513">Póngase en contacto con el soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-513">Contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="5bfcd-514">84</span><span class="sxs-lookup"><span data-stu-id="5bfcd-514">84</span></span></td>
   <td><span data-ttu-id="5bfcd-515">Establece Antivirus de Windows Defender modo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-515">Set Windows Defender Antivirus running mode.</span></span> <span data-ttu-id="5bfcd-516">Forzar el modo pasivo: %1, código de resultado: %2.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-516">Force passive mode: %1, result code: %2.</span></span></td>
   <td><span data-ttu-id="5bfcd-517">Establece el modo de ejecución del defensor (activo o pasivo).</span><span class="sxs-lookup"><span data-stu-id="5bfcd-517">Set defender running mode (active or passive).</span></span></td>
   <td><span data-ttu-id="5bfcd-518">Notificación de funcionamiento normal; no se requiere ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-518">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="5bfcd-519">85</span><span class="sxs-lookup"><span data-stu-id="5bfcd-519">85</span></span></td>
   <td><span data-ttu-id="5bfcd-520">No se pudo desencadenar el ejecutable de Microsoft Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-520">Failed to trigger Microsoft Defender for Endpoint executable.</span></span> <span data-ttu-id="5bfcd-521">Código de error: %1</span><span class="sxs-lookup"><span data-stu-id="5bfcd-521">Failure code: %1</span></span></td>
   <td><span data-ttu-id="5bfcd-522">Error al ejecutar el archivo ejecutable SenseIR.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-522">Starring SenseIR executable failed.</span></span></td>
   <td><span data-ttu-id="5bfcd-523">Reinicie el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-523">Reboot the device.</span></span> <span data-ttu-id="5bfcd-524">Si este error persiste, póngase en contacto con el soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-524">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="5bfcd-525">86</span><span class="sxs-lookup"><span data-stu-id="5bfcd-525">86</span></span></td>
   <td><span data-ttu-id="5bfcd-526">Al iniciar de nuevo se detuvo el servicio externo que debería estar en servicio.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-526">Starting again stopped external service that should be up.</span></span> <span data-ttu-id="5bfcd-527">Nombre: %1, código de salida: %2</span><span class="sxs-lookup"><span data-stu-id="5bfcd-527">Name: %1, exit code: %2</span></span></td>
   <td><span data-ttu-id="5bfcd-528">Iniciar el servicio externo de nuevo.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-528">Starting the external service again.</span></span></td>
   <td><span data-ttu-id="5bfcd-529">Notificación de funcionamiento normal; no se requiere ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-529">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="5bfcd-530">87</span><span class="sxs-lookup"><span data-stu-id="5bfcd-530">87</span></span></td>
   <td><span data-ttu-id="5bfcd-531">No se puede iniciar el servicio externo.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-531">Cannot start the external service.</span></span> <span data-ttu-id="5bfcd-532">Nombre: %1</span><span class="sxs-lookup"><span data-stu-id="5bfcd-532">Name: %1</span></span></td>
   <td><span data-ttu-id="5bfcd-533">No se pudo iniciar el servicio externo.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-533">Failed to start the external service.</span></span></td>
   <td><span data-ttu-id="5bfcd-534">Póngase en contacto con el soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-534">Contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="5bfcd-535">88</span><span class="sxs-lookup"><span data-stu-id="5bfcd-535">88</span></span></td>
   <td><span data-ttu-id="5bfcd-536">Actualizar el tipo de inicio del servicio externo de nuevo.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-536">Updating the start type of external service again.</span></span> <span data-ttu-id="5bfcd-537">Nombre: %1, tipo de inicio real: %2, tipo de inicio esperado: %3, código de salida: %4</span><span class="sxs-lookup"><span data-stu-id="5bfcd-537">Name: %1, actual start type: %2, expected start type: %3, exit code: %4</span></span></td>
   <td><span data-ttu-id="5bfcd-538">Se actualizó el tipo de inicio del servicio externo.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-538">Updated the start type of the external service.</span></span></td>
   <td><span data-ttu-id="5bfcd-539">Notificación de funcionamiento normal; no se requiere ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-539">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="5bfcd-540">89</span><span class="sxs-lookup"><span data-stu-id="5bfcd-540">89</span></span></td>
   <td><span data-ttu-id="5bfcd-541">No se puede actualizar el tipo de inicio del servicio externo.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-541">Cannot update the start type of external service.</span></span> <span data-ttu-id="5bfcd-542">Nombre: %1, tipo de inicio real: %2, tipo de inicio esperado: %3</span><span class="sxs-lookup"><span data-stu-id="5bfcd-542">Name: %1, actual start type: %2, expected start type: %3</span></span></td>
   <td><span data-ttu-id="5bfcd-543">No se puede actualizar el tipo de inicio del servicio externo.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-543">Can't update the start type of the external service.</span></span></td>
   <td><span data-ttu-id="5bfcd-544">Póngase en contacto con el soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-544">Contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="5bfcd-545">90</span><span class="sxs-lookup"><span data-stu-id="5bfcd-545">90</span></span></td>
   <td><span data-ttu-id="5bfcd-546">No se pudo configurar System Guard Runtime Monitor para conectarse al servicio en la nube en la región geográfica %1.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-546">Failed to configure System Guard Runtime Monitor to connect to cloud service in geo-region %1.</span></span> <span data-ttu-id="5bfcd-547">Código de error: %2</span><span class="sxs-lookup"><span data-stu-id="5bfcd-547">Failure code: %2</span></span></td>
   <td><span data-ttu-id="5bfcd-548">System Guard Runtime Monitor no enviará datos de atestación al servicio en la nube.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-548">System Guard Runtime Monitor won't send attestation data to the cloud service.</span></span></td>
   <td><span data-ttu-id="5bfcd-549">Compruebe los permisos en la ruta de registro: "HKLM\Software\Microsoft\Windows\CurrentVersion\Sgrm".</span><span class="sxs-lookup"><span data-stu-id="5bfcd-549">Check the permissions on register path: "HKLM\Software\Microsoft\Windows\CurrentVersion\Sgrm".</span></span> <span data-ttu-id="5bfcd-550">Si no se detecta ningún problema, póngase en contacto con el soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-550">If no issues spotted, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="5bfcd-551">91</span><span class="sxs-lookup"><span data-stu-id="5bfcd-551">91</span></span></td>
   <td><span data-ttu-id="5bfcd-552">No se pudo quitar la información de región geográfica del Monitor de tiempo de ejecución de System Guard.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-552">Failed to remove System Guard Runtime Monitor geo-region information.</span></span> <span data-ttu-id="5bfcd-553">Código de error: %1</span><span class="sxs-lookup"><span data-stu-id="5bfcd-553">Failure code: %1</span></span></td>
   <td><span data-ttu-id="5bfcd-554">System Guard Runtime Monitor no enviará datos de atestación al servicio en la nube.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-554">System Guard Runtime Monitor won't send attestation data to the cloud service.</span></span></td>
   <td><span data-ttu-id="5bfcd-555">Compruebe los permisos en la ruta de registro: "HKLM\Software\Microsoft\Windows\CurrentVersion\Sgrm".</span><span class="sxs-lookup"><span data-stu-id="5bfcd-555">Check the permissions on register path: "HKLM\Software\Microsoft\Windows\CurrentVersion\Sgrm".</span></span> <span data-ttu-id="5bfcd-556">Si no se detecta ningún problema, póngase en contacto con el soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-556">If no issues spotted, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="5bfcd-557">92</span><span class="sxs-lookup"><span data-stu-id="5bfcd-557">92</span></span></td>
   <td><span data-ttu-id="5bfcd-558">Detener el envío de la cuota de datos cibernéticos del sensor porque se supera la cuota de datos.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-558">Stopping sending sensor cyber data quota because data quota is exceeded.</span></span> <span data-ttu-id="5bfcd-559">Se reanudará el envío una vez que pase el período de cuota.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-559">Will resume sending once quota period passes.</span></span> <span data-ttu-id="5bfcd-560">Máscara de estado: %1</span><span class="sxs-lookup"><span data-stu-id="5bfcd-560">State Mask: %1</span></span></td>
   <td><span data-ttu-id="5bfcd-561">Supere el límite de limitación.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-561">Exceed throttling limit.</span></span></td>
   <td><span data-ttu-id="5bfcd-562">Notificación de funcionamiento normal; no se requiere ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-562">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="5bfcd-563">93</span><span class="sxs-lookup"><span data-stu-id="5bfcd-563">93</span></span></td>
   <td><span data-ttu-id="5bfcd-564">Reanudación del envío de datos cibernéticos del sensor.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-564">Resuming sending sensor cyber data.</span></span> <span data-ttu-id="5bfcd-565">Máscara de estado: %1</span><span class="sxs-lookup"><span data-stu-id="5bfcd-565">State Mask: %1</span></span></td>
   <td><span data-ttu-id="5bfcd-566">Reanudar el envío de datos cibernéticos.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-566">Resume cyber data submission.</span></span></td>
   <td><span data-ttu-id="5bfcd-567">Notificación de funcionamiento normal; no se requiere ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-567">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="5bfcd-568">94</span><span class="sxs-lookup"><span data-stu-id="5bfcd-568">94</span></span></td>
   <td><span data-ttu-id="5bfcd-569">Se ha iniciado el ejecutable de Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="5bfcd-569">Microsoft Defender for Endpoint executable has started</span></span></td>
   <td><span data-ttu-id="5bfcd-570">Se ha iniciado el archivo ejecutable senseCE.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-570">The SenseCE executable has started.</span></span></td>
   <td><span data-ttu-id="5bfcd-571">Notificación de funcionamiento normal; no se requiere ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-571">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="5bfcd-572">95</span><span class="sxs-lookup"><span data-stu-id="5bfcd-572">95</span></span></td>
   <td><span data-ttu-id="5bfcd-573">El ejecutable de Microsoft Defender para endpoint ha finalizado</span><span class="sxs-lookup"><span data-stu-id="5bfcd-573">Microsoft Defender for Endpoint executable has ended</span></span></td>
   <td><span data-ttu-id="5bfcd-574">El archivo ejecutable senseCE ha finalizado.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-574">The SenseCE executable has ended.</span></span></td>
   <td><span data-ttu-id="5bfcd-575">Notificación de funcionamiento normal; no se requiere ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-575">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="5bfcd-576">96</span><span class="sxs-lookup"><span data-stu-id="5bfcd-576">96</span></span></td>
   <td><span data-ttu-id="5bfcd-577">Microsoft Defender para Endpoint Init ha llamado.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-577">Microsoft Defender for Endpoint Init has called.</span></span> <span data-ttu-id="5bfcd-578">Código de resultado: %2</span><span class="sxs-lookup"><span data-stu-id="5bfcd-578">Result code: %2</span></span></td>
   <td><span data-ttu-id="5bfcd-579">El ejecutable senseCE ha llamado inicialización de MCE.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-579">The SenseCE executable has called MCE initialization.</span></span></td>
   <td><span data-ttu-id="5bfcd-580">Notificación de funcionamiento normal; no se requiere ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-580">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="5bfcd-581">97</span><span class="sxs-lookup"><span data-stu-id="5bfcd-581">97</span></span></td>
   <td><span data-ttu-id="5bfcd-582">Hay problemas de conectividad a la nube para el escenario DLP</span><span class="sxs-lookup"><span data-stu-id="5bfcd-582">There are connectivity issues to the Cloud for the DLP scenario</span></span></td>
   <td><span data-ttu-id="5bfcd-583">Hay problemas de conectividad de red que afectan al flujo de clasificación dlp.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-583">There are network connectivity issues that affect the DLP classification flow.</span></span></td>
   <td><span data-ttu-id="5bfcd-584">Compruebe la conectividad de red.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-584">Check the network connectivity.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="5bfcd-585">98</span><span class="sxs-lookup"><span data-stu-id="5bfcd-585">98</span></span></td>
   <td><span data-ttu-id="5bfcd-586">Se ha restaurado la conectividad a la nube para el escenario DLP</span><span class="sxs-lookup"><span data-stu-id="5bfcd-586">The connectivity to the Cloud for the DLP scenario has been restored</span></span></td>
   <td><span data-ttu-id="5bfcd-587">La conectividad a la red se restauró y el flujo de clasificación dlp puede continuar.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-587">The connectivity to the network was restored and the DLP classification flow can continue.</span></span></td>
   <td><span data-ttu-id="5bfcd-588">Notificación de funcionamiento normal; no se requiere ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-588">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="5bfcd-589">99</span><span class="sxs-lookup"><span data-stu-id="5bfcd-589">99</span></span></td>
   <td><span data-ttu-id="5bfcd-590">Sense ha encontrado el siguiente error al comunicarse con el servidor: (%1).</span><span class="sxs-lookup"><span data-stu-id="5bfcd-590">Sense has encountered the following error while communicating with server: (%1).</span></span> <span data-ttu-id="5bfcd-591">Resultado: (%2)</span><span class="sxs-lookup"><span data-stu-id="5bfcd-591">Result: (%2)</span></span></td>
   <td><span data-ttu-id="5bfcd-592">Se ha producido un error de comunicación.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-592">A communication error occurred.</span></span></td>
   <td><span data-ttu-id="5bfcd-593">Compruebe los siguientes eventos en el registro de eventos para obtener más detalles.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-593">Check the following events in the event log for further details.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="5bfcd-594">100</span><span class="sxs-lookup"><span data-stu-id="5bfcd-594">100</span></span></td>
   <td><span data-ttu-id="5bfcd-595">El ejecutable de Microsoft Defender para extremo no se pudo iniciar.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-595">Microsoft Defender for Endpoint executable failed to start.</span></span> <span data-ttu-id="5bfcd-596">Código de error: %1</span><span class="sxs-lookup"><span data-stu-id="5bfcd-596">Failure code: %1</span></span></td>
   <td><span data-ttu-id="5bfcd-597">El archivo ejecutable senseCE no se ha podido iniciar.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-597">The SenseCE executable has failed to start.</span></span></td>
   <td><span data-ttu-id="5bfcd-598">Reinicie el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-598">Reboot the device.</span></span> <span data-ttu-id="5bfcd-599">Si este error persiste, póngase en contacto con el soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-599">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="5bfcd-600">102</span><span class="sxs-lookup"><span data-stu-id="5bfcd-600">102</span></span></td>
   <td><span data-ttu-id="5bfcd-601">Se ha iniciado el ejecutable de Microsoft Defender para detección y respuesta de red de extremo</span><span class="sxs-lookup"><span data-stu-id="5bfcd-601">Microsoft Defender for Endpoint Network Detection and Response executable has started</span></span></td>
   <td><span data-ttu-id="5bfcd-602">Se ha iniciado el archivo ejecutable SenseNdr.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-602">The SenseNdr executable has started.</span></span></td>
   <td><span data-ttu-id="5bfcd-603">Notificación de funcionamiento normal; no se requiere ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-603">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="5bfcd-604">103</span><span class="sxs-lookup"><span data-stu-id="5bfcd-604">103</span></span></td>
   <td><span data-ttu-id="5bfcd-605">El ejecutable de Microsoft Defender para detección y respuesta de la red de extremo ha finalizado</span><span class="sxs-lookup"><span data-stu-id="5bfcd-605">Microsoft Defender for Endpoint Network Detection and Response executable has ended</span></span></td>
   <td><span data-ttu-id="5bfcd-606">El archivo ejecutable SenseNdr ha finalizado.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-606">The SenseNdr executable has ended.</span></span></td>
   <td><span data-ttu-id="5bfcd-607">Notificación de funcionamiento normal; no se requiere ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-607">Normal operating notification; no action required.</span></span></td>
</tr>
</tbody>
</table>

><span data-ttu-id="5bfcd-608">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="5bfcd-608">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="5bfcd-609">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="5bfcd-609">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-eventerrorcodes-belowfoldlink)

## <a name="related-topics"></a><span data-ttu-id="5bfcd-610">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="5bfcd-610">Related topics</span></span>
- [<span data-ttu-id="5bfcd-611">Incorporar dispositivos Windows 10 mediante la directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="5bfcd-611">Onboard Windows 10 devices</span></span>](configure-endpoints.md)
- [<span data-ttu-id="5bfcd-612">Configurar las opciones de proxy de dispositivo y de conectividad a Internet</span><span class="sxs-lookup"><span data-stu-id="5bfcd-612">Configure device proxy and Internet connectivity settings</span></span>](configure-proxy-internet.md)
- [<span data-ttu-id="5bfcd-613">Solucionar problemas de Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="5bfcd-613">Troubleshoot Microsoft Defender for Endpoint</span></span>](troubleshoot-onboarding.md)
