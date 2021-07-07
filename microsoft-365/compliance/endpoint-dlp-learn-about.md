---
title: Obtenga más información sobre la Prevención de pérdida de datos de Microsoft 365 de punto de conexión
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/21/2020
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: 'La Prevención de pérdida de datos en punto de conexión de Microsoft 365 amplía la supervisión de las actividades de archivo y de las acciones de protección de estos archivos en los puntos de conexión. Los archivos se hacen visibles en las soluciones de cumplimiento de Microsoft 365 '
ms.openlocfilehash: c97368dd48515dc787dbac66aa93844889efbdbc
ms.sourcegitcommit: 8b0718f5607ab509092cb80bda854010d885c54f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/07/2021
ms.locfileid: "53314421"
---
# <a name="learn-about-microsoft-365-endpoint-data-loss-prevention"></a><span data-ttu-id="44858-104">Obtenga más información sobre la prevención de pérdida de datos de Microsoft 365 de punto de conexión</span><span class="sxs-lookup"><span data-stu-id="44858-104">Learn about Microsoft 365 Endpoint data loss prevention</span></span>

<span data-ttu-id="44858-105">Puede usar la prevención de pérdida de datos (DLP) de Microsoft 365 para supervisar las acciones que se realizan en elementos que ha determinado que son confidenciales y para ayudar a evitar el uso compartido accidental de estos elementos.</span><span class="sxs-lookup"><span data-stu-id="44858-105">You can use Microsoft 365 data loss prevention (DLP) to monitor the actions that are being taken on items you've determined to be sensitive and to help prevent the unintentional sharing of those items.</span></span> <span data-ttu-id="44858-106">Para más información sobre DLP en punto de conexión de Microsoft, consulte [Obtenga más información acerca de la prevención contra la pérdida de datos](dlp-learn-about-dlp.md).</span><span class="sxs-lookup"><span data-stu-id="44858-106">For more information on DLP, see [Learn about data loss prevention](dlp-learn-about-dlp.md).</span></span>

<span data-ttu-id="44858-107">**La prevención de pérdida de datos en punto de conexión** (Endpoint DLP) amplía la supervisión de la actividad y las capacidades de protección de DLP a elementos confidenciales que estén en dispositivos con Windows 10.</span><span class="sxs-lookup"><span data-stu-id="44858-107">**Endpoint data loss prevention** (Endpoint DLP) extends the activity monitoring and protection capabilities of DLP to sensitive items that are on Windows 10 devices.</span></span> <span data-ttu-id="44858-108">Una vez que los dispositivos están incorporados en las soluciones del Centro de cumplimiento de Microsoft 365, la información sobre las acciones de los usuarios relacionadas con los elementos confidenciales se hace visible en el[explorador de actividades](data-classification-activity-explorer.md), y se pueden aplicar acciones de protección a estos elementos mediante [directivas DLP](create-test-tune-dlp-policy.md).</span><span class="sxs-lookup"><span data-stu-id="44858-108">Once devices are onboarded into the Microsoft 365 compliance solutions, the information about what users are doing with sensitive items is made visible in [activity explorer](data-classification-activity-explorer.md) and you can enforce protective actions on those items via [DLP policies](create-test-tune-dlp-policy.md).</span></span>

> [!TIP]
> <span data-ttu-id="44858-109">Si está buscando el control de dispositivos para el almacenamiento extraíble, consulte [Control de dispositivo de Microsoft Defender para punto de conexión extraíble en el control de acceso de almacenamiento](../security/defender-endpoint/device-control-removable-storage-access-control.md#microsoft-defender-for-endpoint-device-control-removable-storage-access-control).</span><span class="sxs-lookup"><span data-stu-id="44858-109">If you are looking for device control for removable storage, see [Microsoft Defender for Endpoint Device Control Removable Storage Access Control](../security/defender-endpoint/device-control-removable-storage-access-control.md#microsoft-defender-for-endpoint-device-control-removable-storage-access-control).</span></span>

## <a name="endpoint-activities-you-can-monitor-and-take-action-on"></a><span data-ttu-id="44858-110">Actividades en punto de conexión que puede supervisar y sobre las que puede tomar medidas</span><span class="sxs-lookup"><span data-stu-id="44858-110">Endpoint activities you can monitor and take action on</span></span>

<span data-ttu-id="44858-111">DLP en punto de conexión de Microsoft le permite auditar y administrar los siguientes tipos de actividades que los usuarios llevan a cabo en elementos confidenciales de los dispositivos que ejecutan Windows 10.</span><span class="sxs-lookup"><span data-stu-id="44858-111">Microsoft Endpoint DLP enables you to audit and manage the following types of activities users take on sensitive items on devices running Windows 10.</span></span>

|<span data-ttu-id="44858-112">Actividad</span><span class="sxs-lookup"><span data-stu-id="44858-112">Activity</span></span> |<span data-ttu-id="44858-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="44858-113">Description</span></span>  | <span data-ttu-id="44858-114">Auditable/Restringible</span><span class="sxs-lookup"><span data-stu-id="44858-114">Auditable/restictable</span></span>|
|---------|---------|---------|
|<span data-ttu-id="44858-115">cargar en el servicio en la nube o acceso por exploradores no permitidos</span><span class="sxs-lookup"><span data-stu-id="44858-115">upload to cloud service, or access by unallowed browsers</span></span>    | <span data-ttu-id="44858-116">Detecta cuándo un usuario intenta cargar un elemento en un dominio de servicio restringido o tener acceso a un elemento con un explorador.</span><span class="sxs-lookup"><span data-stu-id="44858-116">Detects when a user attempts to upload an item to a restricted service domain or access an item through a browser.</span></span>  <span data-ttu-id="44858-117">Si usa un explorador que se muestra en DLP como un explorador que no es el permitido, la actividad de carga se bloqueará y se redirigirá al usuario para usar la arista de cromo.</span><span class="sxs-lookup"><span data-stu-id="44858-117">If they are using a browser that is listed in DLP as an being an unallowed browser, the upload activity will be blocked and the user is redirected to use Edge Chromium.</span></span> <span data-ttu-id="44858-118">Por último, cromo puede permitir o bloquear la carga o el acceso en función de la configuración de la Directiva DLP.</span><span class="sxs-lookup"><span data-stu-id="44858-118">Edge Chromium will then either allow or block the upload or access based on the DLP policy configuration</span></span>         |<span data-ttu-id="44858-119">auditable y restringible</span><span class="sxs-lookup"><span data-stu-id="44858-119">auditable and restrictable</span></span>|
|<span data-ttu-id="44858-120">copiar a otra aplicación</span><span class="sxs-lookup"><span data-stu-id="44858-120">copy to other app</span></span>    |<span data-ttu-id="44858-121">Se detecta cuando un usuario intenta copiar información de un elemento protegido y, a continuación, lo pega en otra aplicación, proceso o elemento.</span><span class="sxs-lookup"><span data-stu-id="44858-121">Detects when a user attempts to copy information from a protected item and then paste it into another app, process or item.</span></span> <span data-ttu-id="44858-122">Esta actividad no detecta la copia y el pegado de información dentro de la misma aplicación, proceso o elemento.</span><span class="sxs-lookup"><span data-stu-id="44858-122">Copying and pasting information within the same app, process, or item is not detected by this activity.</span></span>         | <span data-ttu-id="44858-123">auditable y restringible</span><span class="sxs-lookup"><span data-stu-id="44858-123">auditable and restrictable</span></span>|
|<span data-ttu-id="44858-124">copiar en un medio extraíble USB</span><span class="sxs-lookup"><span data-stu-id="44858-124">copy to USB removable media</span></span> |<span data-ttu-id="44858-125">Detecta cuando un usuario intenta copiar un elemento o información en un medio extraíble o un dispositivo USB.</span><span class="sxs-lookup"><span data-stu-id="44858-125">Detects when a user attempts to copy an item or information to removable media or USB device.</span></span>         | <span data-ttu-id="44858-126">auditable y restringible</span><span class="sxs-lookup"><span data-stu-id="44858-126">auditable and restrictable</span></span>|
|<span data-ttu-id="44858-127">Copiar en un recurso compartido de red</span><span class="sxs-lookup"><span data-stu-id="44858-127">copy to a network share</span></span>    |<span data-ttu-id="44858-128">Detecta cuando un usuario intenta copiar un elemento en un recurso compartido de red o en una unidad de red asignada</span><span class="sxs-lookup"><span data-stu-id="44858-128">Detects when a user attempts to copy an item to a network share or mapped network drive</span></span>         |<span data-ttu-id="44858-129">auditable y restringible</span><span class="sxs-lookup"><span data-stu-id="44858-129">auditable and restrictable</span></span>|
|<span data-ttu-id="44858-130">imprimir un documento</span><span class="sxs-lookup"><span data-stu-id="44858-130">print a document</span></span>    |<span data-ttu-id="44858-131">Detecta cuando un usuario intenta imprimir un elemento protegido en una impresora local o de red.</span><span class="sxs-lookup"><span data-stu-id="44858-131">Detects when a user attempts to print a protected item to a local or network printer.</span></span>| <span data-ttu-id="44858-132">auditable y restringible</span><span class="sxs-lookup"><span data-stu-id="44858-132">auditable and restrictable</span></span>         |
|<span data-ttu-id="44858-133">copiar a una sesión remota</span><span class="sxs-lookup"><span data-stu-id="44858-133">copy to a remote session</span></span>|<span data-ttu-id="44858-134">Detecta cuando un usuario intenta copiar un elemento a una sesión de escritorio remoto</span><span class="sxs-lookup"><span data-stu-id="44858-134">Detects when a user attempts to copy an item to a remote desktop session</span></span> |  <span data-ttu-id="44858-135">auditable y restringible</span><span class="sxs-lookup"><span data-stu-id="44858-135">auditable and restrictable</span></span>|
|<span data-ttu-id="44858-136">copiar en un dispositivo Bluetooth</span><span class="sxs-lookup"><span data-stu-id="44858-136">copy to a Bluetooth device</span></span>|<span data-ttu-id="44858-137">Detecta cuando un usuario intenta copiar un elemento en una aplicación Bluetooth no permitida (según se define en la lista de aplicaciones de Bluetooth no permitidas en la configuración del punto de conexión DLP).</span><span class="sxs-lookup"><span data-stu-id="44858-137">Detects when a user attempts to copy an item to an unallowed Bluetooth app (as defined in the list of unallowed Bluetooth aps in Endpoint DLP settings).</span></span>| <span data-ttu-id="44858-138">auditable y restringible</span><span class="sxs-lookup"><span data-stu-id="44858-138">auditable and restrictable</span></span>|
|<span data-ttu-id="44858-139">crear un elemento</span><span class="sxs-lookup"><span data-stu-id="44858-139">create an item</span></span>|<span data-ttu-id="44858-140">Detecta cuándo un usuario crea un elemento</span><span class="sxs-lookup"><span data-stu-id="44858-140">Detects when a user creates an item</span></span>| <span data-ttu-id="44858-141">auditable</span><span class="sxs-lookup"><span data-stu-id="44858-141">auditable</span></span>|
|<span data-ttu-id="44858-142">cambiar el nombre de un elemento</span><span class="sxs-lookup"><span data-stu-id="44858-142">rename an item</span></span>|<span data-ttu-id="44858-143">Detecta cuando un usuario cambia el nombre de un elemento</span><span class="sxs-lookup"><span data-stu-id="44858-143">Detects when a user renames an item</span></span>| <span data-ttu-id="44858-144">auditable</span><span class="sxs-lookup"><span data-stu-id="44858-144">auditable</span></span>|

## <a name="monitored-files"></a><span data-ttu-id="44858-145">Archivos supervisados</span><span class="sxs-lookup"><span data-stu-id="44858-145">Monitored files</span></span>

<span data-ttu-id="44858-146">La DLP en punto de conexión admite la supervisión de estos tipos de archivo:</span><span class="sxs-lookup"><span data-stu-id="44858-146">Endpoint DLP supports monitoring of these file types:</span></span>

- <span data-ttu-id="44858-147">archivos de Word</span><span class="sxs-lookup"><span data-stu-id="44858-147">Word files</span></span>
- <span data-ttu-id="44858-148">archivos de PowerPoint</span><span class="sxs-lookup"><span data-stu-id="44858-148">PowerPoint files</span></span>
- <span data-ttu-id="44858-149">archivos de Excel</span><span class="sxs-lookup"><span data-stu-id="44858-149">Excel files</span></span>
- <span data-ttu-id="44858-150">archivos PDF</span><span class="sxs-lookup"><span data-stu-id="44858-150">PDF files</span></span>
- <span data-ttu-id="44858-151">archivos .csv</span><span class="sxs-lookup"><span data-stu-id="44858-151">.csv files</span></span>
- <span data-ttu-id="44858-152">archivos .tsv</span><span class="sxs-lookup"><span data-stu-id="44858-152">.tsv files</span></span>
- <span data-ttu-id="44858-153">archivos .txt</span><span class="sxs-lookup"><span data-stu-id="44858-153">.txt files</span></span>
- <span data-ttu-id="44858-154">archivos .rtf</span><span class="sxs-lookup"><span data-stu-id="44858-154">.rtf files</span></span>
- <span data-ttu-id="44858-155">archivos .c</span><span class="sxs-lookup"><span data-stu-id="44858-155">.c files</span></span>
- <span data-ttu-id="44858-156">archivos .class</span><span class="sxs-lookup"><span data-stu-id="44858-156">.class files</span></span>
- <span data-ttu-id="44858-157">archivos .cpp</span><span class="sxs-lookup"><span data-stu-id="44858-157">.cpp files</span></span>
- <span data-ttu-id="44858-158">archivos .cs</span><span class="sxs-lookup"><span data-stu-id="44858-158">.cs files</span></span>
- <span data-ttu-id="44858-159">archivos .h</span><span class="sxs-lookup"><span data-stu-id="44858-159">.h files</span></span>
- <span data-ttu-id="44858-160">archivos .java</span><span class="sxs-lookup"><span data-stu-id="44858-160">.java files</span></span>

<span data-ttu-id="44858-161">De forma predeterminada, la DLP en punto de conexión audita las actividades para estos tipos de archivo, incluso si no hay una coincidencia de directiva.</span><span class="sxs-lookup"><span data-stu-id="44858-161">By default, endpoint DLP audits the activities for these file types, even if there isn't a policy match.</span></span> <span data-ttu-id="44858-162">Si solo quiere supervisar los datos de las coincidencias de directivas, puede desactivar **Auditar siempre para la actividad de archivos de los dispositivos** en la configuración global de DLP en punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="44858-162">If you only want monitoring data from policy matches, you can turn off the **Always audit file activity for devices** in the endpoint DLP global settings.</span></span> <span data-ttu-id="44858-163">Si esta configuración está instalada, las actividades de cualquier archivo Word, PowerPoint, Excel, PDF y .csv siempre se auditan, incluso si el dispositivo no está dirigido por ninguna directiva.</span><span class="sxs-lookup"><span data-stu-id="44858-163">If this setting is on, activities on any Word, PowerPoint, Excel, PDF, and .csv file are always audited even if the device is not targeted by any policy.</span></span>

<span data-ttu-id="44858-164">DLP en punto de conexión supervisa la actividad basada en un tipo de extensiones multipropósito de correo Internet (MIME), por lo que las actividades se capturan incluso si se cambia la extensión de archivo.</span><span class="sxs-lookup"><span data-stu-id="44858-164">Endpoint DLP monitors activity-based on MIME type, so activities will be captured even if the file extension is changed.</span></span>

## <a name="whats-different-in-endpoint-dlp"></a><span data-ttu-id="44858-165">¿Qué es diferente en DLP en punto de conexión?</span><span class="sxs-lookup"><span data-stu-id="44858-165">What's different in Endpoint DLP</span></span>

<span data-ttu-id="44858-166">Debe tener en cuenta algunos conceptos adicionales antes de profundizar en DLP en punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="44858-166">There are a few extra concepts that you need to be aware of before you dig into Endpoint DLP.</span></span>

### <a name="enabling-device-management"></a><span data-ttu-id="44858-167">Habilitar la administración de dispositivos</span><span class="sxs-lookup"><span data-stu-id="44858-167">Enabling Device management</span></span>

<span data-ttu-id="44858-168">La administración de dispositivos es la funcionalidad que permite la colección de telemetría desde dispositivos y la incluye en las soluciones de cumplimiento de Microsoft 365 como DLP en punto de conexión y la [administración de riesgos internos](insider-risk-management.md).</span><span class="sxs-lookup"><span data-stu-id="44858-168">Device management is the functionality that enables the collection of telemetry from devices and brings it into Microsoft 365 compliance solutions like Endpoint DLP and [Insider Risk management](insider-risk-management.md).</span></span> <span data-ttu-id="44858-169">Necesitará incorporar todos los dispositivos que quiera usar como ubicaciones en directivas DLP.</span><span class="sxs-lookup"><span data-stu-id="44858-169">You'll need to onboard all devices you want to use as locations in DLP policies.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="44858-170">![habilitar la administración de dispositivos](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span><span class="sxs-lookup"><span data-stu-id="44858-170">![enable device management](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span></span>

<span data-ttu-id="44858-171">La incorporación y la retirada se controlan mediante scripts que se descargan desde el centro de administración de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="44858-171">Onboarding and offboarding are handled via scripts you download from the Device management center.</span></span> <span data-ttu-id="44858-172">El centro tiene scripts personalizados para cada uno de estos métodos de implementación:</span><span class="sxs-lookup"><span data-stu-id="44858-172">The center has custom scripts for each of these deployment methods:</span></span>

- <span data-ttu-id="44858-173">script local (hasta 10 equipos)</span><span class="sxs-lookup"><span data-stu-id="44858-173">local script (up to 10 machines)</span></span>
- <span data-ttu-id="44858-174">Directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="44858-174">Group policy</span></span>
- <span data-ttu-id="44858-175">System Center Configuration Manager (versión 1610 o posterior)</span><span class="sxs-lookup"><span data-stu-id="44858-175">System Center Configuration Manager (version 1610 or later)</span></span>
- <span data-ttu-id="44858-176">Administración de dispositivos móviles/Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="44858-176">Mobile Device Management/Microsoft Intune</span></span>
- <span data-ttu-id="44858-177">Scripts de incorporación de VDI para equipos no persistentes</span><span class="sxs-lookup"><span data-stu-id="44858-177">VDI onboarding scripts for non-persistent machines</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="44858-178">![página de incorporación de dispositivos](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)</span><span class="sxs-lookup"><span data-stu-id="44858-178">![device onboarding page](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)</span></span>

 <span data-ttu-id="44858-179">Use los procedimientos descritos en [Introducción a DLP en punto de conexión de Microsoft 365](endpoint-dlp-getting-started.md) para incorporar dispositivos.</span><span class="sxs-lookup"><span data-stu-id="44858-179">Use the procedures in [Getting started with Microsoft 365 Endpoint DLP](endpoint-dlp-getting-started.md) to onboard devices.</span></span>

<span data-ttu-id="44858-180">Si incorporó dispositivos a través de [Protección contra amenazas avanzada de Microsoft Defender](/windows/security/threat-protection/), estos dispositivos se mostrarán automáticamente en la lista de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="44858-180">If you have onboarded devices through [Microsoft Defender for Endpoint](/windows/security/threat-protection/), those devices will automatically show up in the list of devices.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="44858-181">![lista de dispositivos administrados](../media/endpoint-dlp-learn-about-2-device-list.png)</span><span class="sxs-lookup"><span data-stu-id="44858-181">![managed devices list](../media/endpoint-dlp-learn-about-2-device-list.png)</span></span>

### <a name="viewing-endpoint-dlp-data"></a><span data-ttu-id="44858-182">Visualizar datos de DLP en punto de conexión</span><span class="sxs-lookup"><span data-stu-id="44858-182">Viewing Endpoint DLP data</span></span>

<span data-ttu-id="44858-183">Puede ver las alertas relacionadas con las directivas DLP ejecutadas en los dispositivos de punto de conexión si va al [Panel de administración de alertas de DLP](dlp-configure-view-alerts-policies.md).</span><span class="sxs-lookup"><span data-stu-id="44858-183">You can view alerts related to DLP policies enforced on endpoint devices by going to the [DLP Alerts Management Dashboard](dlp-configure-view-alerts-policies.md).</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="44858-184">![Información de la alerta](../media/Alert-info-1.png)</span><span class="sxs-lookup"><span data-stu-id="44858-184">![Alert info](../media/Alert-info-1.png)</span></span>

<span data-ttu-id="44858-185">También puede ver los detalles del evento asociado con metadatos enriquecidos en el mismo panel</span><span class="sxs-lookup"><span data-stu-id="44858-185">You can also view details of the associated event with rich metadata in the same dashboard</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="44858-186">![información del evento](../media/Event-info-1.png)</span><span class="sxs-lookup"><span data-stu-id="44858-186">![event info](../media/Event-info-1.png)</span></span>

<span data-ttu-id="44858-187">Una vez que se incorpora un dispositivo, la información sobre las actividades auditadas fluye al explorador de actividad, incluso antes de que configure e implemente las directivas DLP que tienen dispositivos como ubicación.</span><span class="sxs-lookup"><span data-stu-id="44858-187">Once a device is onboarded, information about audited activities flows into Activity explorer even before you configure and deploy any DLP policies that have devices as a location.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="44858-188">![eventos de DLP en punto de conexión en el explorador de actividad](../media/endpoint-dlp-learn-about-4-activity-explorer.png)</span><span class="sxs-lookup"><span data-stu-id="44858-188">![endpoint dlp events in activity explorer](../media/endpoint-dlp-learn-about-4-activity-explorer.png)</span></span>

<span data-ttu-id="44858-189">DLP en punto de conexión recopila información exhaustiva sobre la actividad auditada.</span><span class="sxs-lookup"><span data-stu-id="44858-189">Endpoint DLP collects extensive information on audited activity.</span></span>

<span data-ttu-id="44858-190">Por ejemplo, si se copia un archivo a un medio USB extraíble, vería estos atributos en los detalles de actividad:</span><span class="sxs-lookup"><span data-stu-id="44858-190">For example, if a file is copied to removable USB media, you'd see these attributes in the activity details:</span></span>

- <span data-ttu-id="44858-191">tipo de actividad</span><span class="sxs-lookup"><span data-stu-id="44858-191">activity type</span></span>
- <span data-ttu-id="44858-192">IP del cliente</span><span class="sxs-lookup"><span data-stu-id="44858-192">client IP</span></span>
- <span data-ttu-id="44858-193">ruta de acceso del archivo de destino</span><span class="sxs-lookup"><span data-stu-id="44858-193">target file path</span></span>
- <span data-ttu-id="44858-194">ocurrió una marca de tiempo</span><span class="sxs-lookup"><span data-stu-id="44858-194">happened timestamp</span></span>
- <span data-ttu-id="44858-195">nombre de archivo</span><span class="sxs-lookup"><span data-stu-id="44858-195">file name</span></span>
- <span data-ttu-id="44858-196">usuario</span><span class="sxs-lookup"><span data-stu-id="44858-196">user</span></span>
- <span data-ttu-id="44858-197">extensión de archivo</span><span class="sxs-lookup"><span data-stu-id="44858-197">file extension</span></span>
- <span data-ttu-id="44858-198">tamaño de archivo</span><span class="sxs-lookup"><span data-stu-id="44858-198">file size</span></span>
- <span data-ttu-id="44858-199">tipo de información confidencial (si corresponde)</span><span class="sxs-lookup"><span data-stu-id="44858-199">sensitive information type (if applicable)</span></span>
- <span data-ttu-id="44858-200">valor sha1</span><span class="sxs-lookup"><span data-stu-id="44858-200">sha1 value</span></span>
- <span data-ttu-id="44858-201">valor sha256</span><span class="sxs-lookup"><span data-stu-id="44858-201">sha256 value</span></span>
- <span data-ttu-id="44858-202">nombre de archivo anterior</span><span class="sxs-lookup"><span data-stu-id="44858-202">previous file name</span></span>
- <span data-ttu-id="44858-203">ubicación</span><span class="sxs-lookup"><span data-stu-id="44858-203">location</span></span>
- <span data-ttu-id="44858-204">primario</span><span class="sxs-lookup"><span data-stu-id="44858-204">parent</span></span>
- <span data-ttu-id="44858-205">ruta de acceso al archivo</span><span class="sxs-lookup"><span data-stu-id="44858-205">filepath</span></span>
- <span data-ttu-id="44858-206">tipo de ubicación de origen</span><span class="sxs-lookup"><span data-stu-id="44858-206">source location type</span></span>
- <span data-ttu-id="44858-207">plataforma</span><span class="sxs-lookup"><span data-stu-id="44858-207">platform</span></span>
- <span data-ttu-id="44858-208">nombre de dispositivo</span><span class="sxs-lookup"><span data-stu-id="44858-208">device name</span></span>
- <span data-ttu-id="44858-209">tipo de ubicación de destino</span><span class="sxs-lookup"><span data-stu-id="44858-209">destination location type</span></span>
- <span data-ttu-id="44858-210">aplicación que realizó la copia</span><span class="sxs-lookup"><span data-stu-id="44858-210">application that performed the copy</span></span>
- <span data-ttu-id="44858-211">Id. de dispositivo de Microsoft Defender para punto de conexión (si corresponde)</span><span class="sxs-lookup"><span data-stu-id="44858-211">Microsoft Defender for Endpoint device ID (if applicable)</span></span>
- <span data-ttu-id="44858-212">fabricante del dispositivo multimedia extraíble</span><span class="sxs-lookup"><span data-stu-id="44858-212">removable media device manufacturer</span></span>
- <span data-ttu-id="44858-213">modelo del dispositivo multimedia extraíble</span><span class="sxs-lookup"><span data-stu-id="44858-213">removable media device model</span></span>
- <span data-ttu-id="44858-214">número de serie del dispositivo multimedia extraíble</span><span class="sxs-lookup"><span data-stu-id="44858-214">removable media device serial number</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="44858-215">![copiar a los atributos de actividad del USB](../media/endpoint-dlp-learn-about-5-activity-attributes.png)</span><span class="sxs-lookup"><span data-stu-id="44858-215">![copy to usb activity attributes](../media/endpoint-dlp-learn-about-5-activity-attributes.png)</span></span>

## <a name="next-steps"></a><span data-ttu-id="44858-216">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="44858-216">Next steps</span></span>

<span data-ttu-id="44858-217">Ahora que ya conoce DLP en punto de conexión, estos son los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="44858-217">Now that you've learned about Endpoint DLP, your next steps are:</span></span>

1. [<span data-ttu-id="44858-218">Introducción a la prevención de pérdida de datos en punto de conexión de Microsoft</span><span class="sxs-lookup"><span data-stu-id="44858-218">Getting started with Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
2. [<span data-ttu-id="44858-219">Uso de la prevención de pérdida de datos en punto de conexión de Microsoft</span><span class="sxs-lookup"><span data-stu-id="44858-219">Using Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)

## <a name="see-also"></a><span data-ttu-id="44858-220">Consulte también</span><span class="sxs-lookup"><span data-stu-id="44858-220">See also</span></span>

- [<span data-ttu-id="44858-221">Introducción a la prevención de pérdida de datos en punto de conexión de Microsoft</span><span class="sxs-lookup"><span data-stu-id="44858-221">Getting started with Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
- [<span data-ttu-id="44858-222">Uso de la prevención de pérdida de datos en punto de conexión de Microsoft</span><span class="sxs-lookup"><span data-stu-id="44858-222">Using Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="44858-223">Obtenga más información acerca de la prevención contra la pérdida de datos</span><span class="sxs-lookup"><span data-stu-id="44858-223">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="44858-224">Crear, probar y optimizar una directiva DLP</span><span class="sxs-lookup"><span data-stu-id="44858-224">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="44858-225">Introducción al explorador de actividad</span><span class="sxs-lookup"><span data-stu-id="44858-225">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="44858-226">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="44858-226">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/)
- [<span data-ttu-id="44858-227">Administración de riesgos internos</span><span class="sxs-lookup"><span data-stu-id="44858-227">Insider Risk management</span></span>](insider-risk-management.md)
