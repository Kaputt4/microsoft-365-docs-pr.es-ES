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
ms.openlocfilehash: 1b8454107b6a2737f1236a066c3a24a2b9c776cb
ms.sourcegitcommit: 1244bbc4a3d150d37980cab153505ca462fa7ddc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/26/2021
ms.locfileid: "51222662"
---
# <a name="review-events-and-errors-using-event-viewer"></a><span data-ttu-id="caecf-104">Revisar eventos y errores con el Visor de eventos</span><span class="sxs-lookup"><span data-stu-id="caecf-104">Review events and errors using Event Viewer</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="caecf-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="caecf-105">**Applies to:**</span></span>
- <span data-ttu-id="caecf-106">Visor de eventos</span><span class="sxs-lookup"><span data-stu-id="caecf-106">Event Viewer</span></span>
- [<span data-ttu-id="caecf-107">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="caecf-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="caecf-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="caecf-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="caecf-109">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="caecf-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="caecf-110">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="caecf-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)

<span data-ttu-id="caecf-111">Puedes revisar los IDs de eventos en el [Visor de eventos](https://msdn.microsoft.com/library/aa745633(v=bts.10).aspx) en dispositivos individuales.</span><span class="sxs-lookup"><span data-stu-id="caecf-111">You can review event IDs in the [Event Viewer](https://msdn.microsoft.com/library/aa745633(v=bts.10).aspx) on individual devices.</span></span>

<span data-ttu-id="caecf-112">Por ejemplo, si los dispositivos no aparecen en la lista Dispositivos, es posible que deba buscar los ID de eventos en los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="caecf-112">For example, if devices aren't appearing in the **Devices list**, you might need to look for event IDs on the devices.</span></span> <span data-ttu-id="caecf-113">A continuación, puede usar esta tabla para determinar los pasos de solución de problemas adicionales.</span><span class="sxs-lookup"><span data-stu-id="caecf-113">You can then use this table to determine further troubleshooting steps.</span></span>

<span data-ttu-id="caecf-114">**Abra el Visor de eventos y busque el registro de eventos de servicio de Microsoft Defender para puntos de conexión:**</span><span class="sxs-lookup"><span data-stu-id="caecf-114">**Open Event Viewer and find the Microsoft Defender for Endpoint service event log:**</span></span>

1. <span data-ttu-id="caecf-115">Haga **clic en** Inicio en el menú Windows, escriba Visor de **eventos** y presione **Entrar**.</span><span class="sxs-lookup"><span data-stu-id="caecf-115">Click **Start** on the Windows menu, type **Event Viewer**, and press **Enter**.</span></span>

2. <span data-ttu-id="caecf-116">En la lista de registros, en **Resumen del registro,** desplácese hasta que vea **Microsoft-Windows-SENSE/Operational**.</span><span class="sxs-lookup"><span data-stu-id="caecf-116">In the log list, under **Log Summary**, scroll until you see **Microsoft-Windows-SENSE/Operational**.</span></span> <span data-ttu-id="caecf-117">Haga doble clic en el elemento para abrir el registro.</span><span class="sxs-lookup"><span data-stu-id="caecf-117">Double-click the item to open the log.</span></span>

   <span data-ttu-id="caecf-118">a.</span><span class="sxs-lookup"><span data-stu-id="caecf-118">a.</span></span>  <span data-ttu-id="caecf-119">También puede acceder al registro expandiendo Registros de aplicaciones y servicios  >  **Microsoft**  >  **Windows**  >  **SENSE** y haga clic en **Operativo**.</span><span class="sxs-lookup"><span data-stu-id="caecf-119">You can also access the log by expanding **Applications and Services Logs** > **Microsoft** > **Windows** > **SENSE** and click on **Operational**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="caecf-120">SENSE es el nombre interno que se usa para hacer referencia al sensor de comportamiento que potencia Microsoft Defender para Endpoint.</span><span class="sxs-lookup"><span data-stu-id="caecf-120">SENSE is the internal name used to refer to the behavioral sensor that powers Microsoft Defender for Endpoint.</span></span>

3. <span data-ttu-id="caecf-121">Los eventos registrados por el servicio aparecerán en el registro.</span><span class="sxs-lookup"><span data-stu-id="caecf-121">Events recorded by the service will appear in the log.</span></span> <span data-ttu-id="caecf-122">Vea la tabla siguiente para obtener una lista de eventos registrados por el servicio.</span><span class="sxs-lookup"><span data-stu-id="caecf-122">See the following table for a list of events recorded by the service.</span></span>

<table>
<tbody style="vertical-align:top;">
<tr>
<th><span data-ttu-id="caecf-123">Identificador de evento</span><span class="sxs-lookup"><span data-stu-id="caecf-123">Event ID</span></span></th>
<th><span data-ttu-id="caecf-124">Message</span><span class="sxs-lookup"><span data-stu-id="caecf-124">Message</span></span></th>
<th><span data-ttu-id="caecf-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="caecf-125">Description</span></span></th>
<th><span data-ttu-id="caecf-126">Acción</span><span class="sxs-lookup"><span data-stu-id="caecf-126">Action</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="caecf-127">1</span><span class="sxs-lookup"><span data-stu-id="caecf-127">1</span></span></td>
<td><span data-ttu-id="caecf-128">Se inició el servicio de Microsoft Defender para puntos de conexión <code>variable</code> (versión).</span><span class="sxs-lookup"><span data-stu-id="caecf-128">Microsoft Defender for Endpoint service started (Version <code>variable</code>).</span></span></td>
<td><span data-ttu-id="caecf-129">Se produce durante el inicio, apagado y durante la incorporación del sistema.</span><span class="sxs-lookup"><span data-stu-id="caecf-129">Occurs during system startup, shut down, and during onboarding.</span></span></td>
<td><span data-ttu-id="caecf-130">Notificación de funcionamiento normal; no se requiere ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="caecf-130">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="caecf-131">2</span><span class="sxs-lookup"><span data-stu-id="caecf-131">2</span></span></td>
<td><span data-ttu-id="caecf-132">Cierre del servicio de Microsoft Defender para puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="caecf-132">Microsoft Defender for Endpoint service shutdown.</span></span></td>
<td><span data-ttu-id="caecf-133">Se produce cuando el dispositivo se apaga o se apaga.</span><span class="sxs-lookup"><span data-stu-id="caecf-133">Occurs when the device is shut down or offboarded.</span></span></td>
<td><span data-ttu-id="caecf-134">Notificación de funcionamiento normal; no se requiere ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="caecf-134">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="caecf-135">3</span><span class="sxs-lookup"><span data-stu-id="caecf-135">3</span></span></td>
<td><span data-ttu-id="caecf-136">Microsoft Defender para el servicio de extremo no se pudo iniciar.</span><span class="sxs-lookup"><span data-stu-id="caecf-136">Microsoft Defender for Endpoint service failed to start.</span></span> <span data-ttu-id="caecf-137">Código de error: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="caecf-137">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="caecf-138">El servicio no se ha empezado.</span><span class="sxs-lookup"><span data-stu-id="caecf-138">Service didn't start.</span></span></td>
<td><span data-ttu-id="caecf-139">Revise otros mensajes para determinar posibles causas y pasos de solución de problemas.</span><span class="sxs-lookup"><span data-stu-id="caecf-139">Review other messages to determine possible cause and troubleshooting steps.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="caecf-140">4 </span><span class="sxs-lookup"><span data-stu-id="caecf-140">4</span></span></td>
<td><span data-ttu-id="caecf-141">Microsoft Defender para el servicio de extremo se puso en contacto con el servidor en <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="caecf-141">Microsoft Defender for Endpoint service contacted the server at <code>variable</code>.</span></span></td>
<td><span data-ttu-id="caecf-142">Variable = dirección URL de los servidores de procesamiento de Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="caecf-142">Variable = URL of the Defender for Endpoint processing servers.</span></span><br>
<span data-ttu-id="caecf-143">Esta dirección URL coincidirá con la que se ve en el Firewall o la actividad de red.</span><span class="sxs-lookup"><span data-stu-id="caecf-143">This URL will match that seen in the Firewall or network activity.</span></span></td>
<td><span data-ttu-id="caecf-144">Notificación de funcionamiento normal; no se requiere ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="caecf-144">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="caecf-145">5 </span><span class="sxs-lookup"><span data-stu-id="caecf-145">5</span></span></td>
<td><span data-ttu-id="caecf-146">Microsoft Defender para el servicio de extremo no se pudo conectar al servidor en <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="caecf-146">Microsoft Defender for Endpoint service failed to connect to the server at <code>variable</code>.</span></span></td>
<td><span data-ttu-id="caecf-147">Variable = dirección URL de los servidores de procesamiento de Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="caecf-147">Variable = URL of the Defender for Endpoint processing servers.</span></span><br>
<span data-ttu-id="caecf-148">El servicio no pudo ponerse en contacto con los servidores de procesamiento externos en esa dirección URL.</span><span class="sxs-lookup"><span data-stu-id="caecf-148">The service couldn't contact the external processing servers at that URL.</span></span></td>
<td><span data-ttu-id="caecf-149">Compruebe la conexión a la dirección URL.</span><span class="sxs-lookup"><span data-stu-id="caecf-149">Check the connection to the URL.</span></span> <span data-ttu-id="caecf-150">Consulte <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">Configure proxy and Internet connectivity</a>.</span><span class="sxs-lookup"><span data-stu-id="caecf-150">See <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">Configure proxy and Internet connectivity</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="caecf-151">6 </span><span class="sxs-lookup"><span data-stu-id="caecf-151">6</span></span></td>
<td><span data-ttu-id="caecf-152">El servicio de Microsoft Defender para puntos de conexión no está incorporado y no se encontraron parámetros de incorporación.</span><span class="sxs-lookup"><span data-stu-id="caecf-152">Microsoft Defender for Endpoint service is not onboarded and no onboarding parameters were found.</span></span></td>
<td><span data-ttu-id="caecf-153">El dispositivo no se incorporó correctamente y no se va a informar al portal.</span><span class="sxs-lookup"><span data-stu-id="caecf-153">The device didn't onboard correctly and won't be reporting to the portal.</span></span></td>
<td><span data-ttu-id="caecf-154">La incorporación debe ejecutarse antes de iniciar el servicio.</span><span class="sxs-lookup"><span data-stu-id="caecf-154">Onboarding must be run before starting the service.</span></span><br>
<span data-ttu-id="caecf-155">Compruebe que la configuración de incorporación y los scripts se implementaron correctamente.</span><span class="sxs-lookup"><span data-stu-id="caecf-155">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="caecf-156">Intente volver a implementar los paquetes de configuración.</span><span class="sxs-lookup"><span data-stu-id="caecf-156">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="caecf-157">Consulta <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Incorporación de dispositivos Windows 10</a>.</span><span class="sxs-lookup"><span data-stu-id="caecf-157">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="caecf-158">7 </span><span class="sxs-lookup"><span data-stu-id="caecf-158">7</span></span></td>
<td><span data-ttu-id="caecf-159">Microsoft Defender para el servicio de extremo no pudo leer los parámetros de incorporación.</span><span class="sxs-lookup"><span data-stu-id="caecf-159">Microsoft Defender for Endpoint service failed to read the onboarding parameters.</span></span> <span data-ttu-id="caecf-160">Error: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="caecf-160">Failure: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="caecf-161">Variable = descripción detallada del error.</span><span class="sxs-lookup"><span data-stu-id="caecf-161">Variable = detailed error description.</span></span> <span data-ttu-id="caecf-162">El dispositivo no se incorporó correctamente y no se va a informar al portal.</span><span class="sxs-lookup"><span data-stu-id="caecf-162">The device didn't onboard correctly and won't be reporting to the portal.</span></span></td>
<td><span data-ttu-id="caecf-163">Compruebe que la configuración de incorporación y los scripts se implementaron correctamente.</span><span class="sxs-lookup"><span data-stu-id="caecf-163">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="caecf-164">Intente volver a implementar los paquetes de configuración.</span><span class="sxs-lookup"><span data-stu-id="caecf-164">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="caecf-165">Consulta <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Incorporación de dispositivos Windows 10</a>.</span><span class="sxs-lookup"><span data-stu-id="caecf-165">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="caecf-166">8 </span><span class="sxs-lookup"><span data-stu-id="caecf-166">8</span></span></td>
<td><span data-ttu-id="caecf-167">Microsoft Defender para el servicio de extremo no pudo limpiar su configuración.</span><span class="sxs-lookup"><span data-stu-id="caecf-167">Microsoft Defender for Endpoint service failed to clean its configuration.</span></span> <span data-ttu-id="caecf-168">Código de error: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="caecf-168">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="caecf-169"><b>Durante la incorporación:</b> El servicio no pudo limpiar su configuración durante la incorporación.</span><span class="sxs-lookup"><span data-stu-id="caecf-169"><b>During onboarding:</b> The service failed to clean its configuration during the onboarding.</span></span> <span data-ttu-id="caecf-170">El proceso de incorporación continúa.</span><span class="sxs-lookup"><span data-stu-id="caecf-170">The onboarding process continues.</span></span> <br><br> <span data-ttu-id="caecf-171"><b>Durante el offboarding:</b> El servicio no pudo limpiar su configuración durante el offboarding.</span><span class="sxs-lookup"><span data-stu-id="caecf-171"><b>During offboarding:</b> The service failed to clean its configuration during the offboarding.</span></span> <span data-ttu-id="caecf-172">El proceso de offboarding ha finalizado, pero el servicio sigue ejecutándose.</span><span class="sxs-lookup"><span data-stu-id="caecf-172">The offboarding process finished but the service keeps running.</span></span>
 </td>
<td><span data-ttu-id="caecf-173"><b>Incorporación:</b> No se requiere ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="caecf-173"><b>Onboarding:</b> No action required.</span></span> <br><br> <span data-ttu-id="caecf-174"><b>Offboarding:</b> Reinicie el sistema.</span><span class="sxs-lookup"><span data-stu-id="caecf-174"><b>Offboarding:</b> Reboot the system.</span></span><br>
<span data-ttu-id="caecf-175">Consulta <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Incorporación de dispositivos Windows 10</a>.</span><span class="sxs-lookup"><span data-stu-id="caecf-175">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="caecf-176">9 </span><span class="sxs-lookup"><span data-stu-id="caecf-176">9</span></span></td>
<td><span data-ttu-id="caecf-177">Microsoft Defender para el servicio de extremo no pudo cambiar su tipo de inicio.</span><span class="sxs-lookup"><span data-stu-id="caecf-177">Microsoft Defender for Endpoint service failed to change its start type.</span></span> <span data-ttu-id="caecf-178">Código de error: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="caecf-178">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="caecf-179"><b>Durante la incorporación:</b> El dispositivo no se incorporó correctamente y no se va a informar al portal.</span><span class="sxs-lookup"><span data-stu-id="caecf-179"><b>During onboarding:</b> The device didn't onboard correctly and won't be reporting to the portal.</span></span> <br><br><span data-ttu-id="caecf-180"><b>Durante el offboarding:</b> No se pudo cambiar el tipo de inicio del servicio.</span><span class="sxs-lookup"><span data-stu-id="caecf-180"><b>During offboarding:</b> Failed to change the service start type.</span></span> <span data-ttu-id="caecf-181">El proceso de offboarding continúa.</span><span class="sxs-lookup"><span data-stu-id="caecf-181">The offboarding process continues.</span></span> </td>
<td><span data-ttu-id="caecf-182">Compruebe que la configuración de incorporación y los scripts se implementaron correctamente.</span><span class="sxs-lookup"><span data-stu-id="caecf-182">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="caecf-183">Intente volver a implementar los paquetes de configuración.</span><span class="sxs-lookup"><span data-stu-id="caecf-183">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="caecf-184">Consulta <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Incorporación de dispositivos Windows 10</a>.</span><span class="sxs-lookup"><span data-stu-id="caecf-184">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="caecf-185">10  </span><span class="sxs-lookup"><span data-stu-id="caecf-185">10</span></span></td>
<td><span data-ttu-id="caecf-186">Microsoft Defender para el servicio de extremo no pudo conservar la información de incorporación.</span><span class="sxs-lookup"><span data-stu-id="caecf-186">Microsoft Defender for Endpoint service failed to persist the onboarding information.</span></span> <span data-ttu-id="caecf-187">Código de error: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="caecf-187">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="caecf-188">El dispositivo no se incorporó correctamente y no se va a informar al portal.</span><span class="sxs-lookup"><span data-stu-id="caecf-188">The device didn't onboard correctly and won't be reporting to the portal.</span></span></td>
<td><span data-ttu-id="caecf-189">Compruebe que la configuración de incorporación y los scripts se implementaron correctamente.</span><span class="sxs-lookup"><span data-stu-id="caecf-189">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="caecf-190">Intente volver a implementar los paquetes de configuración.</span><span class="sxs-lookup"><span data-stu-id="caecf-190">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="caecf-191">Consulta <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Incorporación de dispositivos Windows 10</a>.</span><span class="sxs-lookup"><span data-stu-id="caecf-191">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="caecf-192">11</span><span class="sxs-lookup"><span data-stu-id="caecf-192">11</span></span></td>
<td><span data-ttu-id="caecf-193">Se completó la incorporación o la incorporación de Defender para el servicio de extremo.</span><span class="sxs-lookup"><span data-stu-id="caecf-193">Onboarding or re-onboarding of Defender for Endpoint service completed.</span></span></td>
<td><span data-ttu-id="caecf-194">El dispositivo se incorporó correctamente.</span><span class="sxs-lookup"><span data-stu-id="caecf-194">The device onboarded correctly.</span></span></td>
<td><span data-ttu-id="caecf-195">Notificación de funcionamiento normal; no se requiere ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="caecf-195">Normal operating notification; no action required.</span></span><br>
<span data-ttu-id="caecf-196">El dispositivo puede tardar varias horas en aparecer en el portal.</span><span class="sxs-lookup"><span data-stu-id="caecf-196">It may take several hours for the device to appear in the portal.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="caecf-197">12 </span><span class="sxs-lookup"><span data-stu-id="caecf-197">12</span></span></td>
<td><span data-ttu-id="caecf-198">Microsoft Defender para endpoint no pudo aplicar la configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="caecf-198">Microsoft Defender for Endpoint failed to apply the default configuration.</span></span></td>
<td><span data-ttu-id="caecf-199">El servicio no pudo aplicar la configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="caecf-199">Service was unable to apply the default configuration.</span></span></td>
<td><span data-ttu-id="caecf-200">Este error debe resolverse después de un breve período de tiempo.</span><span class="sxs-lookup"><span data-stu-id="caecf-200">This error should resolve after a short period of time.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="caecf-201">13</span><span class="sxs-lookup"><span data-stu-id="caecf-201">13</span></span></td>
<td><span data-ttu-id="caecf-202">Microsoft Defender para el identificador de dispositivo de extremo calculado: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="caecf-202">Microsoft Defender for Endpoint device ID calculated: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="caecf-203">Proceso operativo normal.</span><span class="sxs-lookup"><span data-stu-id="caecf-203">Normal operating process.</span></span></td>
<td><span data-ttu-id="caecf-204">Notificación de funcionamiento normal; no se requiere ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="caecf-204">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="caecf-205">15 </span><span class="sxs-lookup"><span data-stu-id="caecf-205">15</span></span></td>
<td><span data-ttu-id="caecf-206">Microsoft Defender para endpoint no puede iniciar el canal de comandos con dirección URL: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="caecf-206">Microsoft Defender for Endpoint cannot start command channel with URL: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="caecf-207">Variable = dirección URL de los servidores de procesamiento de Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="caecf-207">Variable = URL of the Defender for Endpoint processing servers.</span></span><br>
<span data-ttu-id="caecf-208">El servicio no pudo ponerse en contacto con los servidores de procesamiento externos en esa dirección URL.</span><span class="sxs-lookup"><span data-stu-id="caecf-208">The service couldn't contact the external processing servers at that URL.</span></span></td>
<td><span data-ttu-id="caecf-209">Compruebe la conexión a la dirección URL.</span><span class="sxs-lookup"><span data-stu-id="caecf-209">Check the connection to the URL.</span></span> <span data-ttu-id="caecf-210">Consulte <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">Configure proxy and Internet connectivity</a>.</span><span class="sxs-lookup"><span data-stu-id="caecf-210">See <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">Configure proxy and Internet connectivity</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="caecf-211">17 </span><span class="sxs-lookup"><span data-stu-id="caecf-211">17</span></span></td>
<td><span data-ttu-id="caecf-212">Microsoft Defender para el servicio de extremo no pudo cambiar la ubicación del servicio Telemetría y experiencias del usuario conectado.</span><span class="sxs-lookup"><span data-stu-id="caecf-212">Microsoft Defender for Endpoint service failed to change the Connected User Experiences and Telemetry service location.</span></span> <span data-ttu-id="caecf-213">Código de error: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="caecf-213">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="caecf-214">Se produjo un error con el servicio de telemetría de Windows.</span><span class="sxs-lookup"><span data-stu-id="caecf-214">An error occurred with the Windows telemetry service.</span></span></td>
<td><span data-ttu-id="caecf-215"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Asegúrese de que el servicio de datos de diagnóstico está habilitado.</a></span><span class="sxs-lookup"><span data-stu-id="caecf-215"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Ensure the diagnostic data service is enabled</a>.</span></span><br>
<span data-ttu-id="caecf-216">Compruebe que la configuración de incorporación y los scripts se implementaron correctamente.</span><span class="sxs-lookup"><span data-stu-id="caecf-216">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="caecf-217">Intente volver a implementar los paquetes de configuración.</span><span class="sxs-lookup"><span data-stu-id="caecf-217">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="caecf-218">Consulta <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Incorporación de dispositivos Windows 10</a>.</span><span class="sxs-lookup"><span data-stu-id="caecf-218">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="caecf-219">18 </span><span class="sxs-lookup"><span data-stu-id="caecf-219">18</span></span></td>
<td><span data-ttu-id="caecf-220">OOBE (Windows Welcome) se ha completado.</span><span class="sxs-lookup"><span data-stu-id="caecf-220">OOBE (Windows Welcome) is completed.</span></span></td>
<td><span data-ttu-id="caecf-221">El servicio solo se iniciará después de que las actualizaciones de Windows terminen de instalarse.</span><span class="sxs-lookup"><span data-stu-id="caecf-221">Service will only start after any Windows updates have finished installing.</span></span></td>
<td><span data-ttu-id="caecf-222">Notificación de funcionamiento normal; no se requiere ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="caecf-222">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="caecf-223">19</span><span class="sxs-lookup"><span data-stu-id="caecf-223">19</span></span></td>
<td><span data-ttu-id="caecf-224">OOBE (Windows Welcome) aún no se ha completado.</span><span class="sxs-lookup"><span data-stu-id="caecf-224">OOBE (Windows Welcome) has not yet completed.</span></span></td>
<td><span data-ttu-id="caecf-225">El servicio solo se iniciará después de que las actualizaciones de Windows terminen de instalarse.</span><span class="sxs-lookup"><span data-stu-id="caecf-225">Service will only start after any Windows updates have finished installing.</span></span></td>
<td><span data-ttu-id="caecf-226">Notificación de funcionamiento normal; no se requiere ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="caecf-226">Normal operating notification; no action required.</span></span><br>
<span data-ttu-id="caecf-227">Si este error persiste después de reiniciar el sistema, asegúrate de que todas las actualizaciones de Windows se han instalado por completo.</span><span class="sxs-lookup"><span data-stu-id="caecf-227">If this error persists after a system restart, ensure all Windows updates have full installed.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="caecf-228">20</span><span class="sxs-lookup"><span data-stu-id="caecf-228">20</span></span></td>
<td><span data-ttu-id="caecf-229">No se puede esperar a que se complete OOBE (Windows Welcome).</span><span class="sxs-lookup"><span data-stu-id="caecf-229">Cannot wait for OOBE (Windows Welcome) to complete.</span></span> <span data-ttu-id="caecf-230">Código de error: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="caecf-230">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="caecf-231">Error interno.</span><span class="sxs-lookup"><span data-stu-id="caecf-231">Internal error.</span></span></td>
<td><span data-ttu-id="caecf-232">Si este error persiste después de reiniciar el sistema, asegúrate de que todas las actualizaciones de Windows se han instalado por completo.</span><span class="sxs-lookup"><span data-stu-id="caecf-232">If this error persists after a system restart, ensure all Windows updates have full installed.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="caecf-233">25</span><span class="sxs-lookup"><span data-stu-id="caecf-233">25</span></span></td>
<td><span data-ttu-id="caecf-234">Microsoft Defender para el servicio de extremo no pudo restablecer el estado de mantenimiento en el Registro.</span><span class="sxs-lookup"><span data-stu-id="caecf-234">Microsoft Defender for Endpoint service failed to reset health status in the registry.</span></span> <span data-ttu-id="caecf-235">Código de error: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="caecf-235">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="caecf-236">El dispositivo no se incorporó correctamente.</span><span class="sxs-lookup"><span data-stu-id="caecf-236">The device didn't onboard correctly.</span></span>
<span data-ttu-id="caecf-237">Se presentará en el portal, pero es posible que el servicio no aparezca como registrado en SCCM o en el Registro.</span><span class="sxs-lookup"><span data-stu-id="caecf-237">It will report to the portal, however the service may not appear as registered in SCCM or the registry.</span></span></td>
<td><span data-ttu-id="caecf-238">Compruebe que la configuración de incorporación y los scripts se implementaron correctamente.</span><span class="sxs-lookup"><span data-stu-id="caecf-238">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="caecf-239">Intente volver a implementar los paquetes de configuración.</span><span class="sxs-lookup"><span data-stu-id="caecf-239">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="caecf-240">Consulta <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Incorporación de dispositivos Windows 10</a>.</span><span class="sxs-lookup"><span data-stu-id="caecf-240">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="caecf-241">26</span><span class="sxs-lookup"><span data-stu-id="caecf-241">26</span></span></td>
<td><span data-ttu-id="caecf-242">Microsoft Defender para el servicio de extremo no pudo establecer el estado de incorporación en el Registro.</span><span class="sxs-lookup"><span data-stu-id="caecf-242">Microsoft Defender for Endpoint service failed to set the onboarding status in the registry.</span></span> <span data-ttu-id="caecf-243">Código de error: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="caecf-243">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="caecf-244">El dispositivo no se incorporó correctamente.</span><span class="sxs-lookup"><span data-stu-id="caecf-244">The device didn't onboard correctly.</span></span><br>
<span data-ttu-id="caecf-245">Se presentará en el portal, pero es posible que el servicio no aparezca como registrado en SCCM o en el Registro.</span><span class="sxs-lookup"><span data-stu-id="caecf-245">It will report to the portal, however the service may not appear as registered in SCCM or the registry.</span></span></td>
<td><span data-ttu-id="caecf-246">Compruebe que la configuración de incorporación y los scripts se implementaron correctamente.</span><span class="sxs-lookup"><span data-stu-id="caecf-246">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="caecf-247">Intente volver a implementar los paquetes de configuración.</span><span class="sxs-lookup"><span data-stu-id="caecf-247">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="caecf-248">Consulta <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Incorporación de dispositivos Windows 10</a>.</span><span class="sxs-lookup"><span data-stu-id="caecf-248">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="caecf-249">27</span><span class="sxs-lookup"><span data-stu-id="caecf-249">27</span></span></td>
<td><span data-ttu-id="caecf-250">El servicio de Microsoft Defender para puntos de conexión no pudo habilitar el modo consciente de SENSE en El Antivirus de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="caecf-250">Microsoft Defender for Endpoint service failed to enable SENSE aware mode in Microsoft Defender Antivirus.</span></span> <span data-ttu-id="caecf-251">Error en el proceso de incorporación.</span><span class="sxs-lookup"><span data-stu-id="caecf-251">Onboarding process failed.</span></span> <span data-ttu-id="caecf-252">Código de error: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="caecf-252">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="caecf-253">Normalmente, Antivirus de Microsoft Defender entrará en un estado pasivo especial si otro producto antimalware en tiempo real se ejecuta correctamente en el dispositivo y el dispositivo informa a Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="caecf-253">Normally, Microsoft Defender Antivirus will enter a special passive state if another real-time antimalware product is running properly on the device, and the device is reporting to Defender for Endpoint.</span></span></td>
<td><span data-ttu-id="caecf-254">Compruebe que la configuración de incorporación y los scripts se implementaron correctamente.</span><span class="sxs-lookup"><span data-stu-id="caecf-254">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="caecf-255">Intente volver a implementar los paquetes de configuración.</span><span class="sxs-lookup"><span data-stu-id="caecf-255">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="caecf-256">Consulta <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Incorporación de dispositivos Windows 10</a>.</span><span class="sxs-lookup"><span data-stu-id="caecf-256">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span><br>
<span data-ttu-id="caecf-257">Asegúrese de que la protección antimalware en tiempo real se está ejecutando correctamente.</span><span class="sxs-lookup"><span data-stu-id="caecf-257">Ensure real-time antimalware protection is running properly.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="caecf-258">28</span><span class="sxs-lookup"><span data-stu-id="caecf-258">28</span></span></td>
<td><span data-ttu-id="caecf-259">Error en el registro del servicio de telemetría y experiencias de usuario conectado de Microsoft Defender para puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="caecf-259">Microsoft Defender for Endpoint Connected User Experiences and Telemetry service registration failed.</span></span> <span data-ttu-id="caecf-260">Código de error: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="caecf-260">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="caecf-261">Se produjo un error con el servicio de telemetría de Windows.</span><span class="sxs-lookup"><span data-stu-id="caecf-261">An error occurred with the Windows telemetry service.</span></span></td>
<td><span data-ttu-id="caecf-262"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Asegúrese de que el servicio de datos de diagnóstico está habilitado.</a></span><span class="sxs-lookup"><span data-stu-id="caecf-262"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Ensure the diagnostic data service is enabled</a>.</span></span><br>
<span data-ttu-id="caecf-263">Compruebe que la configuración de incorporación y los scripts se implementaron correctamente.</span><span class="sxs-lookup"><span data-stu-id="caecf-263">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="caecf-264">Intente volver a implementar los paquetes de configuración.</span><span class="sxs-lookup"><span data-stu-id="caecf-264">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="caecf-265">Consulta <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Incorporación de dispositivos Windows 10</a>.</span><span class="sxs-lookup"><span data-stu-id="caecf-265">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="caecf-266">29</span><span class="sxs-lookup"><span data-stu-id="caecf-266">29</span></span></td>
<td><span data-ttu-id="caecf-267">No se pudieron leer los parámetros de offboarding.</span><span class="sxs-lookup"><span data-stu-id="caecf-267">Failed to read the offboarding parameters.</span></span> <span data-ttu-id="caecf-268">Tipo de error: %1, Código de error: %2, Descripción: %3</span><span class="sxs-lookup"><span data-stu-id="caecf-268">Error type: %1, Error code: %2, Description: %3</span></span> </td>
<td><span data-ttu-id="caecf-269">Este evento se produce cuando el sistema&#39;leer los parámetros de offboarding.</span><span class="sxs-lookup"><span data-stu-id="caecf-269">This event occurs when the system can&#39;t read the offboarding parameters.</span></span></td>
<td><span data-ttu-id="caecf-270">Asegúrate de que el dispositivo tiene acceso a Internet y, a continuación, vuelve a ejecutar todo el proceso de offboarding.</span><span class="sxs-lookup"><span data-stu-id="caecf-270">Ensure the device has Internet access, then run the entire offboarding process again.</span></span> <span data-ttu-id="caecf-271">Asegúrese de que el paquete de offboarding no ha expirado.</span><span class="sxs-lookup"><span data-stu-id="caecf-271">Ensure the offboarding package hasn't expired.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="caecf-272">30</span><span class="sxs-lookup"><span data-stu-id="caecf-272">30</span></span></td>
<td><span data-ttu-id="caecf-273">Microsoft Defender para el servicio de extremo no pudo deshabilitar el modo consciente de SENSE en Antivirus de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="caecf-273">Microsoft Defender for Endpoint service failed to disable SENSE aware mode in Microsoft Defender Antivirus.</span></span> <span data-ttu-id="caecf-274">Código de error: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="caecf-274">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="caecf-275">Normalmente, Antivirus de Microsoft Defender entrará en un estado pasivo especial si otro producto antimalware en tiempo real se ejecuta correctamente en el dispositivo y el dispositivo informa a Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="caecf-275">Normally, Microsoft Defender Antivirus will enter a special passive state if another real-time antimalware product is running properly on the device, and the device is reporting to Defender for Endpoint.</span></span></td>
<td><span data-ttu-id="caecf-276">Compruebe que la configuración de incorporación y los scripts se implementaron correctamente.</span><span class="sxs-lookup"><span data-stu-id="caecf-276">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="caecf-277">Intente volver a implementar los paquetes de configuración.</span><span class="sxs-lookup"><span data-stu-id="caecf-277">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="caecf-278">Consulta <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Incorporación de dispositivos Windows 10</a></span><span class="sxs-lookup"><span data-stu-id="caecf-278">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a></span></span><br>
<span data-ttu-id="caecf-279">Asegúrese de que la protección antimalware en tiempo real se está ejecutando correctamente.</span><span class="sxs-lookup"><span data-stu-id="caecf-279">Ensure real-time antimalware protection is running properly.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="caecf-280">31</span><span class="sxs-lookup"><span data-stu-id="caecf-280">31</span></span></td>
<td><span data-ttu-id="caecf-281">Error en la anulación de la registro de Microsoft Defender para experiencias de usuario conectadas a puntos de conexión y servicio de telemetría.</span><span class="sxs-lookup"><span data-stu-id="caecf-281">Microsoft Defender for Endpoint Connected User Experiences and Telemetry service unregistration failed.</span></span> <span data-ttu-id="caecf-282">Código de error: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="caecf-282">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="caecf-283">Se produjo un error con el servicio de telemetría de Windows durante la incorporación.</span><span class="sxs-lookup"><span data-stu-id="caecf-283">An error occurred with the Windows telemetry service during onboarding.</span></span> <span data-ttu-id="caecf-284">El proceso de offboarding continúa.</span><span class="sxs-lookup"><span data-stu-id="caecf-284">The offboarding process continues.</span></span></td>
<td><span data-ttu-id="caecf-285"><a href="troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled" data-raw-source="[Check for errors with the Windows telemetry service](troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled)">Compruebe si hay errores con el servicio de telemetría de Windows</a>.</span><span class="sxs-lookup"><span data-stu-id="caecf-285"><a href="troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled" data-raw-source="[Check for errors with the Windows telemetry service](troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled)">Check for errors with the Windows telemetry service</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="caecf-286">32</span><span class="sxs-lookup"><span data-stu-id="caecf-286">32</span></span></td>
<td><span data-ttu-id="caecf-287">Microsoft Defender para el servicio de extremo no pudo solicitar que se detuviera después del proceso de desaborde.</span><span class="sxs-lookup"><span data-stu-id="caecf-287">Microsoft Defender for Endpoint service failed to request to stop itself after offboarding process.</span></span> <span data-ttu-id="caecf-288">Código de error: %1</span><span class="sxs-lookup"><span data-stu-id="caecf-288">Failure code: %1</span></span></td>
<td><span data-ttu-id="caecf-289">Se produjo un error durante el offboarding.</span><span class="sxs-lookup"><span data-stu-id="caecf-289">An error occurred during offboarding.</span></span></td>
<td><span data-ttu-id="caecf-290">Reinicie el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="caecf-290">Reboot the device.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="caecf-291">33</span><span class="sxs-lookup"><span data-stu-id="caecf-291">33</span></span></td>
<td><span data-ttu-id="caecf-292">Microsoft Defender para el servicio de extremo no pudo conservar EL GUID DE SENSE.</span><span class="sxs-lookup"><span data-stu-id="caecf-292">Microsoft Defender for Endpoint service failed to persist SENSE GUID.</span></span> <span data-ttu-id="caecf-293">Código de error: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="caecf-293">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="caecf-294">Se usa un identificador único para representar cada dispositivo que está informando al portal.</span><span class="sxs-lookup"><span data-stu-id="caecf-294">A unique identifier is used to represent each device that is reporting to the portal.</span></span><br>
<span data-ttu-id="caecf-295">Si el identificador no persiste, es posible que el mismo dispositivo aparezca dos veces en el portal.</span><span class="sxs-lookup"><span data-stu-id="caecf-295">If the identifier doesn't persist, the same device might appear twice in the portal.</span></span></td>
<td><span data-ttu-id="caecf-296">Compruebe los permisos del Registro en el dispositivo para asegurarse de que el servicio puede actualizar el Registro.</span><span class="sxs-lookup"><span data-stu-id="caecf-296">Check registry permissions on the device to ensure the service can update the registry.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="caecf-297">34</span><span class="sxs-lookup"><span data-stu-id="caecf-297">34</span></span></td>
<td><span data-ttu-id="caecf-298">Microsoft Defender para el servicio de extremo no pudo agregarse a sí mismo como dependencia del servicio de telemetría y experiencias del usuario conectado, lo que provocó un error en el proceso de incorporación.</span><span class="sxs-lookup"><span data-stu-id="caecf-298">Microsoft Defender for Endpoint service failed to add itself as a dependency on the Connected User Experiences and Telemetry service, causing onboarding process to fail.</span></span> <span data-ttu-id="caecf-299">Código de error: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="caecf-299">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="caecf-300">Se produjo un error con el servicio de telemetría de Windows.</span><span class="sxs-lookup"><span data-stu-id="caecf-300">An error occurred with the Windows telemetry service.</span></span></td>
<td><span data-ttu-id="caecf-301"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Asegúrese de que el servicio de datos de diagnóstico está habilitado.</a></span><span class="sxs-lookup"><span data-stu-id="caecf-301"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Ensure the diagnostic data service is enabled</a>.</span></span><br>
<span data-ttu-id="caecf-302">Compruebe que la configuración de incorporación y los scripts se implementaron correctamente.</span><span class="sxs-lookup"><span data-stu-id="caecf-302">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="caecf-303">Intente volver a implementar los paquetes de configuración.</span><span class="sxs-lookup"><span data-stu-id="caecf-303">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="caecf-304">Consulta <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Incorporación de dispositivos Windows 10</a>.</span><span class="sxs-lookup"><span data-stu-id="caecf-304">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="caecf-305">35</span><span class="sxs-lookup"><span data-stu-id="caecf-305">35</span></span></td>
<td><span data-ttu-id="caecf-306">Microsoft Defender para el servicio de extremo no pudo quitarse a sí mismo como dependencia del servicio telemetría y experiencias del usuario conectado.</span><span class="sxs-lookup"><span data-stu-id="caecf-306">Microsoft Defender for Endpoint service failed to remove itself as a dependency on the Connected User Experiences and Telemetry service.</span></span> <span data-ttu-id="caecf-307">Código de error: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="caecf-307">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="caecf-308">Se produjo un error con el servicio de telemetría de Windows durante el offboarding.</span><span class="sxs-lookup"><span data-stu-id="caecf-308">An error occurred with the Windows telemetry service during offboarding.</span></span> <span data-ttu-id="caecf-309">El proceso de offboarding continúa.</span><span class="sxs-lookup"><span data-stu-id="caecf-309">The offboarding process continues.</span></span>
</td>
<td><span data-ttu-id="caecf-310">Compruebe si hay errores con el servicio de datos de diagnóstico de Windows.</span><span class="sxs-lookup"><span data-stu-id="caecf-310">Check for errors with the Windows diagnostic data service.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="caecf-311">36</span><span class="sxs-lookup"><span data-stu-id="caecf-311">36</span></span></td>
<td><span data-ttu-id="caecf-312">El registro del servicio de telemetría y experiencias de usuario conectado de Microsoft Defender para endpoints se ha correcto.</span><span class="sxs-lookup"><span data-stu-id="caecf-312">Microsoft Defender for Endpoint Connected User Experiences and Telemetry service registration succeeded.</span></span> <span data-ttu-id="caecf-313">Código de finalización: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="caecf-313">Completion code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="caecf-314">El registro de Defender para endpoint con el servicio de telemetría y experiencias del usuario conectado se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="caecf-314">Registering Defender for Endpoint with the Connected User Experiences and Telemetry service completed successfully.</span></span></td>
<td><span data-ttu-id="caecf-315">Notificación de funcionamiento normal; no se requiere ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="caecf-315">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="caecf-316">37</span><span class="sxs-lookup"><span data-stu-id="caecf-316">37</span></span></td>
<td><span data-ttu-id="caecf-317">El módulo De punto de conexión A de Microsoft Defender está a punto de superar su cuota.</span><span class="sxs-lookup"><span data-stu-id="caecf-317">Microsoft Defender for Endpoint A module is about to exceed its quota.</span></span> <span data-ttu-id="caecf-318">Módulo: %1, Cuota: {%2} {%3}, Porcentaje de utilización de la cuota: %4.</span><span class="sxs-lookup"><span data-stu-id="caecf-318">Module: %1, Quota: {%2} {%3}, Percentage of quota utilization: %4.</span></span></td>
<td><span data-ttu-id="caecf-319">El dispositivo casi ha usado su cuota asignada de la ventana actual de 24 horas.</span><span class="sxs-lookup"><span data-stu-id="caecf-319">The device has almost used its allocated quota of the current 24-hour window.</span></span> <span data-ttu-id="caecf-320">Está a punto de limitarse.</span><span class="sxs-lookup"><span data-stu-id="caecf-320">It’s about to be throttled.</span></span></td>
<td><span data-ttu-id="caecf-321">Notificación de funcionamiento normal; no se requiere ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="caecf-321">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="caecf-322">38</span><span class="sxs-lookup"><span data-stu-id="caecf-322">38</span></span></td>
<td><span data-ttu-id="caecf-323">La conexión de red se identifica como baja.</span><span class="sxs-lookup"><span data-stu-id="caecf-323">Network connection is identified as low.</span></span> <span data-ttu-id="caecf-324">Microsoft Defender para endpoint se pondrá en contacto con el servidor cada %1 minuto.</span><span class="sxs-lookup"><span data-stu-id="caecf-324">Microsoft Defender for Endpoint will contact the server every %1 minutes.</span></span> <span data-ttu-id="caecf-325">Conexión medida: %2, Internet disponible: %3, red gratuita disponible: %4.</span><span class="sxs-lookup"><span data-stu-id="caecf-325">Metered connection: %2, internet available: %3, free network available: %4.</span></span></td>
<td><span data-ttu-id="caecf-326">El dispositivo usa una red de pago y medición y se pondrá en contacto con el servidor con menos frecuencia.</span><span class="sxs-lookup"><span data-stu-id="caecf-326">The device is using a metered/paid network and will be contacting the server less frequently.</span></span></td>
<td><span data-ttu-id="caecf-327">Notificación de funcionamiento normal; no se requiere ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="caecf-327">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="caecf-328">39</span><span class="sxs-lookup"><span data-stu-id="caecf-328">39</span></span></td>
<td><span data-ttu-id="caecf-329">La conexión de red se identifica como normal.</span><span class="sxs-lookup"><span data-stu-id="caecf-329">Network connection is identified as normal.</span></span> <span data-ttu-id="caecf-330">Microsoft Defender para endpoint se pondrá en contacto con el servidor cada %1 minuto.</span><span class="sxs-lookup"><span data-stu-id="caecf-330">Microsoft Defender for Endpoint will contact the server every %1 minutes.</span></span> <span data-ttu-id="caecf-331">Conexión medida: %2, Internet disponible: %3, red gratuita disponible: %4.</span><span class="sxs-lookup"><span data-stu-id="caecf-331">Metered connection: %2, internet available: %3, free network available: %4.</span></span></td>
<td><span data-ttu-id="caecf-332">El dispositivo no usa una conexión de pago o de medición y se pondrá en contacto con el servidor como de costumbre.</span><span class="sxs-lookup"><span data-stu-id="caecf-332">The device isn't using a metered/paid connection and will contact the server as usual.</span></span></td>
<td><span data-ttu-id="caecf-333">Notificación de funcionamiento normal; no se requiere ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="caecf-333">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="caecf-334">40</span><span class="sxs-lookup"><span data-stu-id="caecf-334">40</span></span></td>
<td><span data-ttu-id="caecf-335">El estado de la batería se identifica como bajo.</span><span class="sxs-lookup"><span data-stu-id="caecf-335">Battery state is identified as low.</span></span> <span data-ttu-id="caecf-336">Microsoft Defender para endpoint se pondrá en contacto con el servidor cada %1 minuto.</span><span class="sxs-lookup"><span data-stu-id="caecf-336">Microsoft Defender for Endpoint will contact the server every %1 minutes.</span></span> <span data-ttu-id="caecf-337">Estado de la batería: %2.</span><span class="sxs-lookup"><span data-stu-id="caecf-337">Battery state: %2.</span></span></td>
<td><span data-ttu-id="caecf-338">El dispositivo tiene un nivel de batería bajo y se pondrá en contacto con el servidor con menos frecuencia.</span><span class="sxs-lookup"><span data-stu-id="caecf-338">The device has low battery level and will contact the server less frequently.</span></span></td>
<td><span data-ttu-id="caecf-339">Notificación de funcionamiento normal; no se requiere ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="caecf-339">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="caecf-340">41</span><span class="sxs-lookup"><span data-stu-id="caecf-340">41</span></span></td>
<td><span data-ttu-id="caecf-341">El estado de la batería se identifica como normal.</span><span class="sxs-lookup"><span data-stu-id="caecf-341">Battery state is identified as normal.</span></span> <span data-ttu-id="caecf-342">Microsoft Defender para endpoint se pondrá en contacto con el servidor cada %1 minuto.</span><span class="sxs-lookup"><span data-stu-id="caecf-342">Microsoft Defender for Endpoint will contact the server every %1 minutes.</span></span> <span data-ttu-id="caecf-343">Estado de la batería: %2.</span><span class="sxs-lookup"><span data-stu-id="caecf-343">Battery state: %2.</span></span></td>
<td><span data-ttu-id="caecf-344">El dispositivo no tiene bajo nivel de batería y se pondrá en contacto con el servidor como de costumbre.</span><span class="sxs-lookup"><span data-stu-id="caecf-344">The device doesn’t have low battery level and will contact the server as usual.</span></span></td>
<td><span data-ttu-id="caecf-345">Notificación de funcionamiento normal; no se requiere ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="caecf-345">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="caecf-346">42</span><span class="sxs-lookup"><span data-stu-id="caecf-346">42</span></span></td>
<td><span data-ttu-id="caecf-347">El componente WDATP de Microsoft Defender para extremo no pudo realizar la acción.</span><span class="sxs-lookup"><span data-stu-id="caecf-347">Microsoft Defender for Endpoint WDATP component failed to perform action.</span></span> <span data-ttu-id="caecf-348">Componente: %1, Acción: %2, Tipo de excepción: %3, Mensaje de excepción: %4</span><span class="sxs-lookup"><span data-stu-id="caecf-348">Component: %1, Action: %2, Exception Type: %3, Exception message: %4</span></span></td>
<td><span data-ttu-id="caecf-349">Error interno.</span><span class="sxs-lookup"><span data-stu-id="caecf-349">Internal error.</span></span> <span data-ttu-id="caecf-350">No se pudo iniciar el servicio.</span><span class="sxs-lookup"><span data-stu-id="caecf-350">The service failed to start.</span></span></td>
<td><span data-ttu-id="caecf-351">Si este error persiste, póngase en contacto con el soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="caecf-351">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="caecf-352">43</span><span class="sxs-lookup"><span data-stu-id="caecf-352">43</span></span></td>
<td><span data-ttu-id="caecf-353">El componente WDATP de Microsoft Defender para extremo no pudo realizar la acción.</span><span class="sxs-lookup"><span data-stu-id="caecf-353">Microsoft Defender for Endpoint WDATP component failed to perform action.</span></span> <span data-ttu-id="caecf-354">Componente: %1, Acción: %2, Tipo de excepción: %3, Error de excepción: %4, Mensaje de excepción: %5</span><span class="sxs-lookup"><span data-stu-id="caecf-354">Component: %1, Action: %2, Exception Type: %3, Exception Error: %4, Exception message: %5</span></span></td>
<td><span data-ttu-id="caecf-355">Error interno.</span><span class="sxs-lookup"><span data-stu-id="caecf-355">Internal error.</span></span> <span data-ttu-id="caecf-356">No se pudo iniciar el servicio.</span><span class="sxs-lookup"><span data-stu-id="caecf-356">The service failed to start.</span></span></td>
<td><span data-ttu-id="caecf-357">Si este error persiste, póngase en contacto con el soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="caecf-357">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="caecf-358">44</span><span class="sxs-lookup"><span data-stu-id="caecf-358">44</span></span></td>
<td><span data-ttu-id="caecf-359">Offboarding of Defender for Endpoint service completed.</span><span class="sxs-lookup"><span data-stu-id="caecf-359">Offboarding of Defender for Endpoint service completed.</span></span></td>
<td><span data-ttu-id="caecf-360">El servicio se ha desactivado.</span><span class="sxs-lookup"><span data-stu-id="caecf-360">The service was offboarded.</span></span></td>
<td><span data-ttu-id="caecf-361">Notificación de funcionamiento normal; no se requiere ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="caecf-361">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="caecf-362">45</span><span class="sxs-lookup"><span data-stu-id="caecf-362">45</span></span></td>
<td><span data-ttu-id="caecf-363">Error al registrar e iniciar la sesión de seguimiento de eventos [%1].</span><span class="sxs-lookup"><span data-stu-id="caecf-363">Failed to register and to start the event trace session [%1].</span></span> <span data-ttu-id="caecf-364">Código de error: %2</span><span class="sxs-lookup"><span data-stu-id="caecf-364">Error code: %2</span></span></td>
<td><span data-ttu-id="caecf-365">Se produjo un error al iniciar el servicio al crear la sesión etw.</span><span class="sxs-lookup"><span data-stu-id="caecf-365">An error occurred on service startup while creating ETW session.</span></span> <span data-ttu-id="caecf-366">Esto provocó un error de inicio del servicio.</span><span class="sxs-lookup"><span data-stu-id="caecf-366">This caused service start-up failure.</span></span></td>
<td><span data-ttu-id="caecf-367">Si este error persiste, póngase en contacto con el soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="caecf-367">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="caecf-368">46</span><span class="sxs-lookup"><span data-stu-id="caecf-368">46</span></span></td>
<td><span data-ttu-id="caecf-369">No se pudo registrar e iniciar la sesión de seguimiento de eventos [%1] debido a la falta de recursos.</span><span class="sxs-lookup"><span data-stu-id="caecf-369">Failed to register and start the event trace session [%1] due to lack of resources.</span></span> <span data-ttu-id="caecf-370">Código de error: %2.</span><span class="sxs-lookup"><span data-stu-id="caecf-370">Error code: %2.</span></span> <span data-ttu-id="caecf-371">Esto es más probable porque hay demasiadas sesiones de seguimiento de eventos activos.</span><span class="sxs-lookup"><span data-stu-id="caecf-371">This is most likely because there are too many active event trace sessions.</span></span> <span data-ttu-id="caecf-372">El servicio reintentará en 1 minuto.</span><span class="sxs-lookup"><span data-stu-id="caecf-372">The service will retry in 1 minute.</span></span></td>
<td><span data-ttu-id="caecf-373">Se produjo un error al iniciar el servicio al crear una sesión de ETW debido a la falta de recursos.</span><span class="sxs-lookup"><span data-stu-id="caecf-373">An error occurred on service startup while creating ETW session due to lack of resources.</span></span> <span data-ttu-id="caecf-374">El servicio se inició y se está ejecutando, pero no informa de ningún evento de sensor hasta que se inicia la sesión etw.</span><span class="sxs-lookup"><span data-stu-id="caecf-374">The service started and is running, but won't report any sensor event until the ETW session is started.</span></span></td>
<td><span data-ttu-id="caecf-375">Notificación de funcionamiento normal; no se requiere ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="caecf-375">Normal operating notification; no action required.</span></span> <span data-ttu-id="caecf-376">El servicio intentará iniciar la sesión cada minuto.</span><span class="sxs-lookup"><span data-stu-id="caecf-376">The service will try to start the session every minute.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="caecf-377">47</span><span class="sxs-lookup"><span data-stu-id="caecf-377">47</span></span></td>
<td><span data-ttu-id="caecf-378">Se registró correctamente e inició la sesión de seguimiento de eventos, recuperada después de intentos fallidos anteriores.</span><span class="sxs-lookup"><span data-stu-id="caecf-378">Successfully registered and started the event trace session - recovered after previous failed attempts.</span></span></td>
<td><span data-ttu-id="caecf-379">Este evento sigue al evento anterior después de iniciar correctamente la sesión etw.</span><span class="sxs-lookup"><span data-stu-id="caecf-379">This event follows the previous event after successfully starting of the ETW session.</span></span></td>
<td><span data-ttu-id="caecf-380">Notificación de funcionamiento normal; no se requiere ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="caecf-380">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="caecf-381">48</span><span class="sxs-lookup"><span data-stu-id="caecf-381">48</span></span></td>
<td><span data-ttu-id="caecf-382">No se pudo agregar un proveedor [%1] a la sesión de seguimiento de eventos [%2].</span><span class="sxs-lookup"><span data-stu-id="caecf-382">Failed to add a provider [%1] to event trace session [%2].</span></span> <span data-ttu-id="caecf-383">Código de error: %3.</span><span class="sxs-lookup"><span data-stu-id="caecf-383">Error code: %3.</span></span> <span data-ttu-id="caecf-384">Esto significa que los eventos de este proveedor no se notifican.</span><span class="sxs-lookup"><span data-stu-id="caecf-384">This means that events from this provider will not be reported.</span></span></td>
<td><span data-ttu-id="caecf-385">No se pudo agregar un proveedor a la sesión de ETW.</span><span class="sxs-lookup"><span data-stu-id="caecf-385">Failed to add a provider to ETW session.</span></span> <span data-ttu-id="caecf-386">Como resultado, no se notifican los eventos del proveedor.</span><span class="sxs-lookup"><span data-stu-id="caecf-386">As a result, the provider events aren’t reported.</span></span></td>
<td><span data-ttu-id="caecf-387">Compruebe el código de error.</span><span class="sxs-lookup"><span data-stu-id="caecf-387">Check the error code.</span></span> <span data-ttu-id="caecf-388">Si el error persiste, póngase en contacto con el soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="caecf-388">If the error persists contact Support.</span></span></td>
</tr>
</tr>
<tr>
   <td><span data-ttu-id="caecf-389">49</span><span class="sxs-lookup"><span data-stu-id="caecf-389">49</span></span></td>
   <td><span data-ttu-id="caecf-390">Comando de configuración de nube no válido recibido e ignorado.</span><span class="sxs-lookup"><span data-stu-id="caecf-390">Invalid cloud configuration command received and ignored.</span></span> <span data-ttu-id="caecf-391">Versión: %1, estado: %2, código de error: %3, mensaje: %4</span><span class="sxs-lookup"><span data-stu-id="caecf-391">Version: %1, status: %2, error code: %3, message: %4</span></span></td>
   <td><span data-ttu-id="caecf-392">Se ha recibido un archivo de configuración no válido del servicio en la nube que se ha omitido.</span><span class="sxs-lookup"><span data-stu-id="caecf-392">Received an invalid configuration file from the cloud service that was ignored.</span></span></td>
   <td><span data-ttu-id="caecf-393">Si este error persiste, póngase en contacto con el soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="caecf-393">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="caecf-394">50</span><span class="sxs-lookup"><span data-stu-id="caecf-394">50</span></span></td>
   <td><span data-ttu-id="caecf-395">Nueva configuración de nube aplicada correctamente.</span><span class="sxs-lookup"><span data-stu-id="caecf-395">New cloud configuration applied successfully.</span></span> <span data-ttu-id="caecf-396">Versión: %1.</span><span class="sxs-lookup"><span data-stu-id="caecf-396">Version: %1.</span></span></td>
   <td><span data-ttu-id="caecf-397">Se aplicó correctamente una nueva configuración desde el servicio en la nube.</span><span class="sxs-lookup"><span data-stu-id="caecf-397">Successfully applied a new configuration from the cloud service.</span></span></td>
   <td><span data-ttu-id="caecf-398">Notificación de funcionamiento normal; no se requiere ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="caecf-398">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="caecf-399">51</span><span class="sxs-lookup"><span data-stu-id="caecf-399">51</span></span></td>
   <td><span data-ttu-id="caecf-400">No se pudo aplicar la nueva configuración de nube, versión: %1.</span><span class="sxs-lookup"><span data-stu-id="caecf-400">New cloud configuration failed to apply, version: %1.</span></span> <span data-ttu-id="caecf-401">Se aplicó correctamente la última configuración correcta conocida, versión %2.</span><span class="sxs-lookup"><span data-stu-id="caecf-401">Successfully applied the last known good configuration, version %2.</span></span></td>
   <td><span data-ttu-id="caecf-402">Se ha recibido un archivo de configuración mal del servicio en la nube.</span><span class="sxs-lookup"><span data-stu-id="caecf-402">Received a bad configuration file from the cloud service.</span></span> <span data-ttu-id="caecf-403">La última configuración correcta conocida se aplicó correctamente.</span><span class="sxs-lookup"><span data-stu-id="caecf-403">Last known good configuration was applied successfully.</span></span></td>
   <td><span data-ttu-id="caecf-404">Si este error persiste, póngase en contacto con el soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="caecf-404">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="caecf-405">52</span><span class="sxs-lookup"><span data-stu-id="caecf-405">52</span></span></td>
   <td><span data-ttu-id="caecf-406">No se pudo aplicar la nueva configuración de nube, versión: %1.</span><span class="sxs-lookup"><span data-stu-id="caecf-406">New cloud configuration failed to apply, version: %1.</span></span> <span data-ttu-id="caecf-407">Tampoco se pudo aplicar la última configuración correcta conocida, versión %2.</span><span class="sxs-lookup"><span data-stu-id="caecf-407">Also failed to apply last known good configuration, version %2.</span></span> <span data-ttu-id="caecf-408">Se aplicó correctamente la configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="caecf-408">Successfully applied the default configuration.</span></span></td>
   <td><span data-ttu-id="caecf-409">Se ha recibido un archivo de configuración mal del servicio en la nube.</span><span class="sxs-lookup"><span data-stu-id="caecf-409">Received a bad configuration file from the cloud service.</span></span> <span data-ttu-id="caecf-410">No se pudo aplicar la última configuración buena conocida y se aplicó la configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="caecf-410">Failed to apply the last known good configuration - and the default configuration was applied.</span></span></td>
   <td><span data-ttu-id="caecf-411">El servicio intentará descargar un nuevo archivo de configuración en 5 minutos.</span><span class="sxs-lookup"><span data-stu-id="caecf-411">The service will attempt to download a new configuration file within 5 minutes.</span></span> <span data-ttu-id="caecf-412">Si no ve el evento #50: póngase en contacto con el soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="caecf-412">If you don't see event #50 - contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="caecf-413">53</span><span class="sxs-lookup"><span data-stu-id="caecf-413">53</span></span></td>
   <td><span data-ttu-id="caecf-414">Configuración de nube cargada desde el almacenamiento persistente, versión: %1.</span><span class="sxs-lookup"><span data-stu-id="caecf-414">Cloud configuration loaded from persistent storage, version: %1.</span></span></td>
   <td><span data-ttu-id="caecf-415">La configuración se cargó desde el almacenamiento persistente al iniciar el servicio.</span><span class="sxs-lookup"><span data-stu-id="caecf-415">The configuration was loaded from persistent storage on service startup.</span></span></td>
   <td><span data-ttu-id="caecf-416">Notificación de funcionamiento normal; no se requiere ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="caecf-416">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="caecf-417">55</span><span class="sxs-lookup"><span data-stu-id="caecf-417">55</span></span></td>
   <td><span data-ttu-id="caecf-418">No se pudo crear el registrador automático de ETW seguro.</span><span class="sxs-lookup"><span data-stu-id="caecf-418">Failed to create the Secure ETW autologger.</span></span> <span data-ttu-id="caecf-419">Código de error: %1</span><span class="sxs-lookup"><span data-stu-id="caecf-419">Failure code: %1</span></span></td>
   <td><span data-ttu-id="caecf-420">No se pudo crear el registrador ETW seguro.</span><span class="sxs-lookup"><span data-stu-id="caecf-420">Failed to create the secure ETW logger.</span></span></td>
   <td><span data-ttu-id="caecf-421">Reinicie el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="caecf-421">Reboot the device.</span></span> <span data-ttu-id="caecf-422">Si este error persiste, póngase en contacto con el soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="caecf-422">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="caecf-423">56</span><span class="sxs-lookup"><span data-stu-id="caecf-423">56</span></span></td>
   <td><span data-ttu-id="caecf-424">No se pudo quitar el registrador automático de ETW seguro.</span><span class="sxs-lookup"><span data-stu-id="caecf-424">Failed to remove the Secure ETW autologger.</span></span> <span data-ttu-id="caecf-425">Código de error: %1</span><span class="sxs-lookup"><span data-stu-id="caecf-425">Failure code: %1</span></span></td>
   <td><span data-ttu-id="caecf-426">No se pudo quitar la sesión de ETW segura en el offboarding.</span><span class="sxs-lookup"><span data-stu-id="caecf-426">Failed to remove the secure ETW session on offboarding.</span></span></td>
   <td><span data-ttu-id="caecf-427">Póngase en contacto con el soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="caecf-427">Contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="caecf-428">57</span><span class="sxs-lookup"><span data-stu-id="caecf-428">57</span></span></td>
   <td><span data-ttu-id="caecf-429">Captura de una instantánea de la máquina para solucionar problemas.</span><span class="sxs-lookup"><span data-stu-id="caecf-429">Capturing a snapshot of the machine for troubleshooting purposes.</span></span></td>
   <td><span data-ttu-id="caecf-430">Se está recopilando un paquete de investigación, también conocido como paquete forense.</span><span class="sxs-lookup"><span data-stu-id="caecf-430">An investigation package, also known as forensics package, is being collected.</span></span></td>
   <td><span data-ttu-id="caecf-431">Notificación de funcionamiento normal; no se requiere ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="caecf-431">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="caecf-432">59</span><span class="sxs-lookup"><span data-stu-id="caecf-432">59</span></span></td>
   <td><span data-ttu-id="caecf-433">Comando inicio: %1</span><span class="sxs-lookup"><span data-stu-id="caecf-433">Starting command: %1</span></span></td>
   <td><span data-ttu-id="caecf-434">Iniciar la ejecución del comando de respuesta.</span><span class="sxs-lookup"><span data-stu-id="caecf-434">Starting response command execution.</span></span></td>
   <td><span data-ttu-id="caecf-435">Notificación de funcionamiento normal; no se requiere ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="caecf-435">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="caecf-436">60</span><span class="sxs-lookup"><span data-stu-id="caecf-436">60</span></span></td>
   <td><span data-ttu-id="caecf-437">Error al ejecutar el comando %1, error: %2.</span><span class="sxs-lookup"><span data-stu-id="caecf-437">Failed to run command %1, error: %2.</span></span></td>
   <td><span data-ttu-id="caecf-438">Error al ejecutar el comando response.</span><span class="sxs-lookup"><span data-stu-id="caecf-438">Failed to execute response command.</span></span></td>
   <td><span data-ttu-id="caecf-439">Si este error persiste, póngase en contacto con el soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="caecf-439">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="caecf-440">61</span><span class="sxs-lookup"><span data-stu-id="caecf-440">61</span></span></td>
   <td><span data-ttu-id="caecf-441">Los parámetros de comando de la colección de datos no son válidos: SasUri: %1, compressionLevel: %2.</span><span class="sxs-lookup"><span data-stu-id="caecf-441">Data collection command parameters are invalid: SasUri: %1, compressionLevel: %2.</span></span></td>
   <td><span data-ttu-id="caecf-442">No se pudo leer ni analizar los argumentos del comando de colección de datos (argumentos no válidos).</span><span class="sxs-lookup"><span data-stu-id="caecf-442">Failed to read or parse the data collection command arguments (invalid arguments).</span></span></td>
   <td><span data-ttu-id="caecf-443">Si este error persiste, póngase en contacto con el soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="caecf-443">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="caecf-444">62</span><span class="sxs-lookup"><span data-stu-id="caecf-444">62</span></span></td>
   <td><span data-ttu-id="caecf-445">No se pudo iniciar el servicio de telemetría y experiencias de usuario conectado.</span><span class="sxs-lookup"><span data-stu-id="caecf-445">Failed to start Connected User Experiences and Telemetry service.</span></span> <span data-ttu-id="caecf-446">Código de error: %1</span><span class="sxs-lookup"><span data-stu-id="caecf-446">Failure code: %1</span></span></td>
   <td><span data-ttu-id="caecf-447">No se pudo iniciar el servicio de telemetría y experiencias de usuario conectados (diagtrack).</span><span class="sxs-lookup"><span data-stu-id="caecf-447">Connected User Experiences and Telemetry (diagtrack) service failed to start.</span></span> <span data-ttu-id="caecf-448">La telemetría que no sea de Microsoft Defender para puntos de conexión no se enviará desde este equipo.</span><span class="sxs-lookup"><span data-stu-id="caecf-448">Non-Microsoft Defender for Endpoint telemetry won't be sent from this machine.</span></span></td>
   <td><span data-ttu-id="caecf-449">Busque más sugerencias de solución de problemas en el registro de eventos: Microsoft-Windows-UniversalTelemetryClient/Operational.</span><span class="sxs-lookup"><span data-stu-id="caecf-449">Look for more troubleshooting hints in the event log: Microsoft-Windows-UniversalTelemetryClient/Operational.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="caecf-450">63</span><span class="sxs-lookup"><span data-stu-id="caecf-450">63</span></span></td>
   <td><span data-ttu-id="caecf-451">Actualizar el tipo de inicio del servicio externo.</span><span class="sxs-lookup"><span data-stu-id="caecf-451">Updating the start type of external service.</span></span> <span data-ttu-id="caecf-452">Nombre: %1, tipo de inicio real: %2, tipo de inicio esperado: %3, código de salida: %4</span><span class="sxs-lookup"><span data-stu-id="caecf-452">Name: %1, actual start type: %2, expected start type: %3, exit code: %4</span></span></td>
   <td><span data-ttu-id="caecf-453">Tipo de inicio actualizado del servicio externo.</span><span class="sxs-lookup"><span data-stu-id="caecf-453">Updated start type of the external service.</span></span></td>
   <td><span data-ttu-id="caecf-454">Notificación de funcionamiento normal; no se requiere ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="caecf-454">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="caecf-455">64</span><span class="sxs-lookup"><span data-stu-id="caecf-455">64</span></span></td>
   <td><span data-ttu-id="caecf-456">Inicio del servicio externo detenido.</span><span class="sxs-lookup"><span data-stu-id="caecf-456">Starting stopped external service.</span></span> <span data-ttu-id="caecf-457">Nombre: %1, código de salida: %2</span><span class="sxs-lookup"><span data-stu-id="caecf-457">Name: %1, exit code: %2</span></span></td>
   <td><span data-ttu-id="caecf-458">Iniciar un servicio externo.</span><span class="sxs-lookup"><span data-stu-id="caecf-458">Starting an external service.</span></span></td>
   <td><span data-ttu-id="caecf-459">Notificación de funcionamiento normal; no se requiere ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="caecf-459">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="caecf-460">65</span><span class="sxs-lookup"><span data-stu-id="caecf-460">65</span></span></td>
   <td><span data-ttu-id="caecf-461">No se pudo cargar el controlador de minifiltro de componentes de eventos de seguridad de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="caecf-461">Failed to load Microsoft Security Events Component Minifilter driver.</span></span> <span data-ttu-id="caecf-462">Código de error: %1</span><span class="sxs-lookup"><span data-stu-id="caecf-462">Failure code: %1</span></span></td>
   <td><span data-ttu-id="caecf-463">No se pudo cargar MsSecFlt.sys minifiltro del sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="caecf-463">Failed to load MsSecFlt.sys filesystem minifilter.</span></span></td>
   <td><span data-ttu-id="caecf-464">Reinicie el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="caecf-464">Reboot the device.</span></span> <span data-ttu-id="caecf-465">Si este error persiste, póngase en contacto con el soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="caecf-465">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="caecf-466">66</span><span class="sxs-lookup"><span data-stu-id="caecf-466">66</span></span></td>
   <td><span data-ttu-id="caecf-467">Actualización de directivas: Modo de latencia - %1</span><span class="sxs-lookup"><span data-stu-id="caecf-467">Policy update: Latency mode - %1</span></span></td>
   <td><span data-ttu-id="caecf-468">Se actualizó C# de frecuencia de conexión C de C&C.</span><span class="sxs-lookup"><span data-stu-id="caecf-468">The C&C connection frequency policy was updated.</span></span></td>
   <td><span data-ttu-id="caecf-469">Notificación de funcionamiento normal; no se requiere ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="caecf-469">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="caecf-470">68</span><span class="sxs-lookup"><span data-stu-id="caecf-470">68</span></span></td>
   <td><span data-ttu-id="caecf-471">El tipo de inicio del servicio es inesperado.</span><span class="sxs-lookup"><span data-stu-id="caecf-471">The start type of the service is unexpected.</span></span> <span data-ttu-id="caecf-472">Nombre del servicio: %1, tipo de inicio real: %2, tipo de inicio esperado: %3</span><span class="sxs-lookup"><span data-stu-id="caecf-472">Service name: %1, actual start type: %2, expected start type: %3</span></span></td>
   <td><span data-ttu-id="caecf-473">Tipo de inicio de servicio externo inesperado.</span><span class="sxs-lookup"><span data-stu-id="caecf-473">Unexpected external service start type.</span></span></td>
   <td><span data-ttu-id="caecf-474">Corregir el tipo de inicio del servicio externo.</span><span class="sxs-lookup"><span data-stu-id="caecf-474">Fix the external service start type.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="caecf-475">69</span><span class="sxs-lookup"><span data-stu-id="caecf-475">69</span></span></td>
   <td><span data-ttu-id="caecf-476">El servicio se detiene.</span><span class="sxs-lookup"><span data-stu-id="caecf-476">The service is stopped.</span></span> <span data-ttu-id="caecf-477">Nombre del servicio: %1</span><span class="sxs-lookup"><span data-stu-id="caecf-477">Service name: %1</span></span></td>
   <td><span data-ttu-id="caecf-478">Se detiene el servicio externo.</span><span class="sxs-lookup"><span data-stu-id="caecf-478">The external service is stopped.</span></span></td>
   <td><span data-ttu-id="caecf-479">Inicie el servicio externo.</span><span class="sxs-lookup"><span data-stu-id="caecf-479">Start the external service.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="caecf-480">70</span><span class="sxs-lookup"><span data-stu-id="caecf-480">70</span></span></td>
   <td><span data-ttu-id="caecf-481">Actualización de directivas: permitir la colección de muestras - %1</span><span class="sxs-lookup"><span data-stu-id="caecf-481">Policy update: Allow sample collection - %1</span></span></td>
   <td><span data-ttu-id="caecf-482">Se actualizó la directiva de colección de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="caecf-482">The sample collection policy was updated.</span></span></td>
   <td><span data-ttu-id="caecf-483">Notificación de funcionamiento normal; no se requiere ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="caecf-483">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="caecf-484">71</span><span class="sxs-lookup"><span data-stu-id="caecf-484">71</span></span></td>
   <td><span data-ttu-id="caecf-485">Se ha ejecutado correctamente el comando: %1</span><span class="sxs-lookup"><span data-stu-id="caecf-485">Succeeded to run command: %1</span></span></td>
   <td><span data-ttu-id="caecf-486">El comando se ejecutó correctamente.</span><span class="sxs-lookup"><span data-stu-id="caecf-486">The command was executed successfully.</span></span></td>
   <td><span data-ttu-id="caecf-487">Notificación de funcionamiento normal; no se requiere ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="caecf-487">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="caecf-488">72</span><span class="sxs-lookup"><span data-stu-id="caecf-488">72</span></span></td>
   <td><span data-ttu-id="caecf-489">Se intentó enviar el primer informe de perfil completo del equipo.</span><span class="sxs-lookup"><span data-stu-id="caecf-489">Tried to send first full machine profile report.</span></span> <span data-ttu-id="caecf-490">Código de resultado: %1</span><span class="sxs-lookup"><span data-stu-id="caecf-490">Result code: %1</span></span></td>
   <td><span data-ttu-id="caecf-491">Solo informativo.</span><span class="sxs-lookup"><span data-stu-id="caecf-491">Informational only.</span></span></td>
   <td><span data-ttu-id="caecf-492">Notificación de funcionamiento normal; no se requiere ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="caecf-492">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="caecf-493">73</span><span class="sxs-lookup"><span data-stu-id="caecf-493">73</span></span></td>
   <td><span data-ttu-id="caecf-494">Sense starting for platform: %1</span><span class="sxs-lookup"><span data-stu-id="caecf-494">Sense starting for platform: %1</span></span></td>
   <td><span data-ttu-id="caecf-495">Solo informativo.</span><span class="sxs-lookup"><span data-stu-id="caecf-495">Informational only.</span></span></td>
   <td><span data-ttu-id="caecf-496">Notificación de funcionamiento normal; no se requiere ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="caecf-496">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="caecf-497">74</span><span class="sxs-lookup"><span data-stu-id="caecf-497">74</span></span></td>
   <td><span data-ttu-id="caecf-498">La etiqueta de dispositivo en el Registro supera el límite de longitud.</span><span class="sxs-lookup"><span data-stu-id="caecf-498">Device tag in registry exceeds length limit.</span></span> <span data-ttu-id="caecf-499">Nombre de etiqueta: %2.</span><span class="sxs-lookup"><span data-stu-id="caecf-499">Tag name: %2.</span></span> <span data-ttu-id="caecf-500">Límite de longitud: %1.</span><span class="sxs-lookup"><span data-stu-id="caecf-500">Length limit: %1.</span></span></td>
   <td><span data-ttu-id="caecf-501">La etiqueta de dispositivo supera el límite de longitud.</span><span class="sxs-lookup"><span data-stu-id="caecf-501">The device tag exceeds the length limit.</span></span></td>
   <td><span data-ttu-id="caecf-502">Usa una etiqueta de dispositivo más corta.</span><span class="sxs-lookup"><span data-stu-id="caecf-502">Use a shorter device tag.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="caecf-503">81</span><span class="sxs-lookup"><span data-stu-id="caecf-503">81</span></span></td>
   <td><span data-ttu-id="caecf-504">No se pudo crear Windows Defender registrador automático etw de protección contra amenazas avanzada.</span><span class="sxs-lookup"><span data-stu-id="caecf-504">Failed to create Windows Defender Advanced Threat Protection ETW autologger.</span></span> <span data-ttu-id="caecf-505">Código de error: %1</span><span class="sxs-lookup"><span data-stu-id="caecf-505">Failure code: %1</span></span></td>
   <td><span data-ttu-id="caecf-506">No se pudo crear la sesión etw.</span><span class="sxs-lookup"><span data-stu-id="caecf-506">Failed to create the ETW session.</span></span></td>
   <td><span data-ttu-id="caecf-507">Reinicie el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="caecf-507">Reboot the device.</span></span> <span data-ttu-id="caecf-508">Si este error persiste, póngase en contacto con el soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="caecf-508">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="caecf-509">82</span><span class="sxs-lookup"><span data-stu-id="caecf-509">82</span></span></td>
   <td><span data-ttu-id="caecf-510">No se pudo quitar Windows Defender registrador automático etw de protección contra amenazas avanzada.</span><span class="sxs-lookup"><span data-stu-id="caecf-510">Failed to remove Windows Defender Advanced Threat Protection ETW autologger.</span></span> <span data-ttu-id="caecf-511">Código de error: %1</span><span class="sxs-lookup"><span data-stu-id="caecf-511">Failure code: %1</span></span></td>
   <td><span data-ttu-id="caecf-512">No se pudo eliminar la sesión etw.</span><span class="sxs-lookup"><span data-stu-id="caecf-512">Failed to delete the ETW session.</span></span></td>
   <td><span data-ttu-id="caecf-513">Póngase en contacto con el soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="caecf-513">Contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="caecf-514">84</span><span class="sxs-lookup"><span data-stu-id="caecf-514">84</span></span></td>
   <td><span data-ttu-id="caecf-515">Establece Windows Defender modo de ejecución de Antivirus.</span><span class="sxs-lookup"><span data-stu-id="caecf-515">Set Windows Defender Antivirus running mode.</span></span> <span data-ttu-id="caecf-516">Forzar el modo pasivo: %1, código de resultado: %2.</span><span class="sxs-lookup"><span data-stu-id="caecf-516">Force passive mode: %1, result code: %2.</span></span></td>
   <td><span data-ttu-id="caecf-517">Establece el modo de ejecución del defensor (activo o pasivo).</span><span class="sxs-lookup"><span data-stu-id="caecf-517">Set defender running mode (active or passive).</span></span></td>
   <td><span data-ttu-id="caecf-518">Notificación de funcionamiento normal; no se requiere ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="caecf-518">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="caecf-519">85</span><span class="sxs-lookup"><span data-stu-id="caecf-519">85</span></span></td>
   <td><span data-ttu-id="caecf-520">No se pudo desencadenar Windows Defender ejecutable de protección contra amenazas avanzada.</span><span class="sxs-lookup"><span data-stu-id="caecf-520">Failed to trigger Windows Defender Advanced Threat Protection executable.</span></span> <span data-ttu-id="caecf-521">Código de error: %1</span><span class="sxs-lookup"><span data-stu-id="caecf-521">Failure code: %1</span></span></td>
   <td><span data-ttu-id="caecf-522">Error al ejecutar el archivo ejecutable SenseIR.</span><span class="sxs-lookup"><span data-stu-id="caecf-522">Starring SenseIR executable failed.</span></span></td>
   <td><span data-ttu-id="caecf-523">Reinicie el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="caecf-523">Reboot the device.</span></span> <span data-ttu-id="caecf-524">Si este error persiste, póngase en contacto con el soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="caecf-524">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="caecf-525">86</span><span class="sxs-lookup"><span data-stu-id="caecf-525">86</span></span></td>
   <td><span data-ttu-id="caecf-526">Al iniciar de nuevo se detuvo el servicio externo que debería estar en servicio.</span><span class="sxs-lookup"><span data-stu-id="caecf-526">Starting again stopped external service that should be up.</span></span> <span data-ttu-id="caecf-527">Nombre: %1, código de salida: %2</span><span class="sxs-lookup"><span data-stu-id="caecf-527">Name: %1, exit code: %2</span></span></td>
   <td><span data-ttu-id="caecf-528">Iniciar el servicio externo de nuevo.</span><span class="sxs-lookup"><span data-stu-id="caecf-528">Starting the external service again.</span></span></td>
   <td><span data-ttu-id="caecf-529">Notificación de funcionamiento normal; no se requiere ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="caecf-529">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="caecf-530">87</span><span class="sxs-lookup"><span data-stu-id="caecf-530">87</span></span></td>
   <td><span data-ttu-id="caecf-531">No se puede iniciar el servicio externo.</span><span class="sxs-lookup"><span data-stu-id="caecf-531">Cannot start the external service.</span></span> <span data-ttu-id="caecf-532">Nombre: %1</span><span class="sxs-lookup"><span data-stu-id="caecf-532">Name: %1</span></span></td>
   <td><span data-ttu-id="caecf-533">No se pudo iniciar el servicio externo.</span><span class="sxs-lookup"><span data-stu-id="caecf-533">Failed to start the external service.</span></span></td>
   <td><span data-ttu-id="caecf-534">Póngase en contacto con el soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="caecf-534">Contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="caecf-535">88</span><span class="sxs-lookup"><span data-stu-id="caecf-535">88</span></span></td>
   <td><span data-ttu-id="caecf-536">Actualizar el tipo de inicio del servicio externo de nuevo.</span><span class="sxs-lookup"><span data-stu-id="caecf-536">Updating the start type of external service again.</span></span> <span data-ttu-id="caecf-537">Nombre: %1, tipo de inicio real: %2, tipo de inicio esperado: %3, código de salida: %4</span><span class="sxs-lookup"><span data-stu-id="caecf-537">Name: %1, actual start type: %2, expected start type: %3, exit code: %4</span></span></td>
   <td><span data-ttu-id="caecf-538">Se actualizó el tipo de inicio del servicio externo.</span><span class="sxs-lookup"><span data-stu-id="caecf-538">Updated the start type of the external service.</span></span></td>
   <td><span data-ttu-id="caecf-539">Notificación de funcionamiento normal; no se requiere ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="caecf-539">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="caecf-540">89</span><span class="sxs-lookup"><span data-stu-id="caecf-540">89</span></span></td>
   <td><span data-ttu-id="caecf-541">No se puede actualizar el tipo de inicio del servicio externo.</span><span class="sxs-lookup"><span data-stu-id="caecf-541">Cannot update the start type of external service.</span></span> <span data-ttu-id="caecf-542">Nombre: %1, tipo de inicio real: %2, tipo de inicio esperado: %3</span><span class="sxs-lookup"><span data-stu-id="caecf-542">Name: %1, actual start type: %2, expected start type: %3</span></span></td>
   <td><span data-ttu-id="caecf-543">No se puede actualizar el tipo de inicio del servicio externo.</span><span class="sxs-lookup"><span data-stu-id="caecf-543">Can't update the start type of the external service.</span></span></td>
   <td><span data-ttu-id="caecf-544">Póngase en contacto con el soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="caecf-544">Contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="caecf-545">90</span><span class="sxs-lookup"><span data-stu-id="caecf-545">90</span></span></td>
   <td><span data-ttu-id="caecf-546">No se pudo configurar System Guard Runtime Monitor para conectarse al servicio en la nube en la región geográfica %1.</span><span class="sxs-lookup"><span data-stu-id="caecf-546">Failed to configure System Guard Runtime Monitor to connect to cloud service in geo-region %1.</span></span> <span data-ttu-id="caecf-547">Código de error: %2</span><span class="sxs-lookup"><span data-stu-id="caecf-547">Failure code: %2</span></span></td>
   <td><span data-ttu-id="caecf-548">System Guard Runtime Monitor no enviará datos de atestación al servicio en la nube.</span><span class="sxs-lookup"><span data-stu-id="caecf-548">System Guard Runtime Monitor won't send attestation data to the cloud service.</span></span></td>
   <td><span data-ttu-id="caecf-549">Compruebe los permisos en la ruta de registro: "HKLM\Software\Microsoft\Windows\CurrentVersion\Sgrm".</span><span class="sxs-lookup"><span data-stu-id="caecf-549">Check the permissions on register path: "HKLM\Software\Microsoft\Windows\CurrentVersion\Sgrm".</span></span> <span data-ttu-id="caecf-550">Si no se detecta ningún problema, póngase en contacto con el soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="caecf-550">If no issues spotted, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="caecf-551">91</span><span class="sxs-lookup"><span data-stu-id="caecf-551">91</span></span></td>
   <td><span data-ttu-id="caecf-552">No se pudo quitar la información de región geográfica del Monitor de tiempo de ejecución de System Guard.</span><span class="sxs-lookup"><span data-stu-id="caecf-552">Failed to remove System Guard Runtime Monitor geo-region information.</span></span> <span data-ttu-id="caecf-553">Código de error: %1</span><span class="sxs-lookup"><span data-stu-id="caecf-553">Failure code: %1</span></span></td>
   <td><span data-ttu-id="caecf-554">System Guard Runtime Monitor no enviará datos de atestación al servicio en la nube.</span><span class="sxs-lookup"><span data-stu-id="caecf-554">System Guard Runtime Monitor won't send attestation data to the cloud service.</span></span></td>
   <td><span data-ttu-id="caecf-555">Compruebe los permisos en la ruta de registro: "HKLM\Software\Microsoft\Windows\CurrentVersion\Sgrm".</span><span class="sxs-lookup"><span data-stu-id="caecf-555">Check the permissions on register path: "HKLM\Software\Microsoft\Windows\CurrentVersion\Sgrm".</span></span> <span data-ttu-id="caecf-556">Si no se detecta ningún problema, póngase en contacto con el soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="caecf-556">If no issues spotted, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="caecf-557">92</span><span class="sxs-lookup"><span data-stu-id="caecf-557">92</span></span></td>
   <td><span data-ttu-id="caecf-558">Detener el envío de la cuota de datos cibernéticos del sensor porque se supera la cuota de datos.</span><span class="sxs-lookup"><span data-stu-id="caecf-558">Stopping sending sensor cyber data quota because data quota is exceeded.</span></span> <span data-ttu-id="caecf-559">Se reanudará el envío una vez que pase el período de cuota.</span><span class="sxs-lookup"><span data-stu-id="caecf-559">Will resume sending once quota period passes.</span></span> <span data-ttu-id="caecf-560">Máscara de estado: %1</span><span class="sxs-lookup"><span data-stu-id="caecf-560">State Mask: %1</span></span></td>
   <td><span data-ttu-id="caecf-561">Supere el límite de limitación.</span><span class="sxs-lookup"><span data-stu-id="caecf-561">Exceed throttling limit.</span></span></td>
   <td><span data-ttu-id="caecf-562">Notificación de funcionamiento normal; no se requiere ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="caecf-562">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="caecf-563">93</span><span class="sxs-lookup"><span data-stu-id="caecf-563">93</span></span></td>
   <td><span data-ttu-id="caecf-564">Reanudación del envío de datos cibernéticos del sensor.</span><span class="sxs-lookup"><span data-stu-id="caecf-564">Resuming sending sensor cyber data.</span></span> <span data-ttu-id="caecf-565">Máscara de estado: %1</span><span class="sxs-lookup"><span data-stu-id="caecf-565">State Mask: %1</span></span></td>
   <td><span data-ttu-id="caecf-566">Reanudar el envío de datos cibernéticos.</span><span class="sxs-lookup"><span data-stu-id="caecf-566">Resume cyber data submission.</span></span></td>
   <td><span data-ttu-id="caecf-567">Notificación de funcionamiento normal; no se requiere ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="caecf-567">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="caecf-568">94</span><span class="sxs-lookup"><span data-stu-id="caecf-568">94</span></span></td>
   <td><span data-ttu-id="caecf-569">Windows Defender ejecutable de protección contra amenazas avanzada</span><span class="sxs-lookup"><span data-stu-id="caecf-569">Windows Defender Advanced Threat Protection executable has started</span></span></td>
   <td><span data-ttu-id="caecf-570">Se ha iniciado el archivo ejecutable senseCE.</span><span class="sxs-lookup"><span data-stu-id="caecf-570">The SenseCE executable has started.</span></span></td>
   <td><span data-ttu-id="caecf-571">Notificación de funcionamiento normal; no se requiere ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="caecf-571">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="caecf-572">95</span><span class="sxs-lookup"><span data-stu-id="caecf-572">95</span></span></td>
   <td><span data-ttu-id="caecf-573">Windows Defender ejecutable de protección contra amenazas avanzada ha finalizado</span><span class="sxs-lookup"><span data-stu-id="caecf-573">Windows Defender Advanced Threat Protection executable has ended</span></span></td>
   <td><span data-ttu-id="caecf-574">El archivo ejecutable senseCE ha finalizado.</span><span class="sxs-lookup"><span data-stu-id="caecf-574">The SenseCE executable has ended.</span></span></td>
   <td><span data-ttu-id="caecf-575">Notificación de funcionamiento normal; no se requiere ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="caecf-575">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="caecf-576">96</span><span class="sxs-lookup"><span data-stu-id="caecf-576">96</span></span></td>
   <td><span data-ttu-id="caecf-577">Windows Defender la protección contra amenazas avanzada init ha llamado.</span><span class="sxs-lookup"><span data-stu-id="caecf-577">Windows Defender Advanced Threat Protection Init has called.</span></span> <span data-ttu-id="caecf-578">Código de resultado: %2</span><span class="sxs-lookup"><span data-stu-id="caecf-578">Result code: %2</span></span></td>
   <td><span data-ttu-id="caecf-579">El ejecutable senseCE ha llamado inicialización de MCE.</span><span class="sxs-lookup"><span data-stu-id="caecf-579">The SenseCE executable has called MCE initialization.</span></span></td>
   <td><span data-ttu-id="caecf-580">Notificación de funcionamiento normal; no se requiere ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="caecf-580">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="caecf-581">97</span><span class="sxs-lookup"><span data-stu-id="caecf-581">97</span></span></td>
   <td><span data-ttu-id="caecf-582">Hay problemas de conectividad a la nube para el escenario DLP</span><span class="sxs-lookup"><span data-stu-id="caecf-582">There are connectivity issues to the Cloud for the DLP scenario</span></span></td>
   <td><span data-ttu-id="caecf-583">Hay problemas de conectividad de red que afectan al flujo de clasificación dlp.</span><span class="sxs-lookup"><span data-stu-id="caecf-583">There are network connectivity issues that affect the DLP classification flow.</span></span></td>
   <td><span data-ttu-id="caecf-584">Compruebe la conectividad de red.</span><span class="sxs-lookup"><span data-stu-id="caecf-584">Check the network connectivity.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="caecf-585">98</span><span class="sxs-lookup"><span data-stu-id="caecf-585">98</span></span></td>
   <td><span data-ttu-id="caecf-586">Se ha restaurado la conectividad a la nube para el escenario DLP</span><span class="sxs-lookup"><span data-stu-id="caecf-586">The connectivity to the Cloud for the DLP scenario has been restored</span></span></td>
   <td><span data-ttu-id="caecf-587">La conectividad a la red se restauró y el flujo de clasificación dlp puede continuar.</span><span class="sxs-lookup"><span data-stu-id="caecf-587">The connectivity to the network was restored and the DLP classification flow can continue.</span></span></td>
   <td><span data-ttu-id="caecf-588">Notificación de funcionamiento normal; no se requiere ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="caecf-588">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="caecf-589">99</span><span class="sxs-lookup"><span data-stu-id="caecf-589">99</span></span></td>
   <td><span data-ttu-id="caecf-590">Sense ha encontrado el siguiente error al comunicarse con el servidor: (%1).</span><span class="sxs-lookup"><span data-stu-id="caecf-590">Sense has encountered the following error while communicating with server: (%1).</span></span> <span data-ttu-id="caecf-591">Resultado: (%2)</span><span class="sxs-lookup"><span data-stu-id="caecf-591">Result: (%2)</span></span></td>
   <td><span data-ttu-id="caecf-592">Se ha producido un error de comunicación.</span><span class="sxs-lookup"><span data-stu-id="caecf-592">A communication error occurred.</span></span></td>
   <td><span data-ttu-id="caecf-593">Compruebe los siguientes eventos en el registro de eventos para obtener más detalles.</span><span class="sxs-lookup"><span data-stu-id="caecf-593">Check the following events in the event log for further details.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="caecf-594">100</span><span class="sxs-lookup"><span data-stu-id="caecf-594">100</span></span></td>
   <td><span data-ttu-id="caecf-595">Windows Defender ejecutable de Protección contra amenazas avanzada no se pudo iniciar.</span><span class="sxs-lookup"><span data-stu-id="caecf-595">Windows Defender Advanced Threat Protection executable failed to start.</span></span> <span data-ttu-id="caecf-596">Código de error: %1</span><span class="sxs-lookup"><span data-stu-id="caecf-596">Failure code: %1</span></span></td>
   <td><span data-ttu-id="caecf-597">El archivo ejecutable senseCE no se ha podido iniciar.</span><span class="sxs-lookup"><span data-stu-id="caecf-597">The SenseCE executable has failed to start.</span></span></td>
   <td><span data-ttu-id="caecf-598">Reinicie el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="caecf-598">Reboot the device.</span></span> <span data-ttu-id="caecf-599">Si este error persiste, póngase en contacto con el soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="caecf-599">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="caecf-600">102</span><span class="sxs-lookup"><span data-stu-id="caecf-600">102</span></span></td>
   <td><span data-ttu-id="caecf-601">Windows Defender se ha iniciado el ejecutable de detección y respuesta de red de protección contra amenazas avanzada</span><span class="sxs-lookup"><span data-stu-id="caecf-601">Windows Defender Advanced Threat Protection Network Detection and Response executable has started</span></span></td>
   <td><span data-ttu-id="caecf-602">Se ha iniciado el archivo ejecutable SenseNdr.</span><span class="sxs-lookup"><span data-stu-id="caecf-602">The SenseNdr executable has started.</span></span></td>
   <td><span data-ttu-id="caecf-603">Notificación de funcionamiento normal; no se requiere ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="caecf-603">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="caecf-604">103</span><span class="sxs-lookup"><span data-stu-id="caecf-604">103</span></span></td>
   <td><span data-ttu-id="caecf-605">Windows Defender ejecutable de detección y respuesta de red de protección contra amenazas avanzada ha finalizado</span><span class="sxs-lookup"><span data-stu-id="caecf-605">Windows Defender Advanced Threat Protection Network Detection and Response executable has ended</span></span></td>
   <td><span data-ttu-id="caecf-606">El archivo ejecutable SenseNdr ha finalizado.</span><span class="sxs-lookup"><span data-stu-id="caecf-606">The SenseNdr executable has ended.</span></span></td>
   <td><span data-ttu-id="caecf-607">Notificación de funcionamiento normal; no se requiere ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="caecf-607">Normal operating notification; no action required.</span></span></td>
</tr>
</tbody>
</table>

><span data-ttu-id="caecf-608">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="caecf-608">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="caecf-609">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="caecf-609">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-eventerrorcodes-belowfoldlink)

## <a name="related-topics"></a><span data-ttu-id="caecf-610">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="caecf-610">Related topics</span></span>
- [<span data-ttu-id="caecf-611">Incorporación de dispositivos Windows 10</span><span class="sxs-lookup"><span data-stu-id="caecf-611">Onboard Windows 10 devices</span></span>](configure-endpoints.md)
- [<span data-ttu-id="caecf-612">Configurar el proxy de dispositivo y la configuración de conectividad a Internet</span><span class="sxs-lookup"><span data-stu-id="caecf-612">Configure device proxy and Internet connectivity settings</span></span>](configure-proxy-internet.md)
- [<span data-ttu-id="caecf-613">Solucionar problemas de Microsoft Defender para el extremo</span><span class="sxs-lookup"><span data-stu-id="caecf-613">Troubleshoot Microsoft Defender for Endpoint</span></span>](troubleshoot-onboarding.md)
