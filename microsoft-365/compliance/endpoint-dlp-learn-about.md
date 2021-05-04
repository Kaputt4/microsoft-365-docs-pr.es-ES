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
ms.openlocfilehash: b5aa6c737bc54129ce49378a7dcaf81e9d5c612f
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114108"
---
# <a name="learn-about-microsoft-365-endpoint-data-loss-prevention"></a><span data-ttu-id="b00e6-104">Obtenga más información sobre la prevención de pérdida de datos de Microsoft 365 de punto de conexión</span><span class="sxs-lookup"><span data-stu-id="b00e6-104">Learn about Microsoft 365 Endpoint data loss prevention</span></span>

<span data-ttu-id="b00e6-105">Puede usar la prevención de pérdida de datos (DLP) de Microsoft 365 para supervisar las acciones que se realizan en elementos que ha determinado que son confidenciales y para ayudar a evitar el uso compartido accidental de estos elementos.</span><span class="sxs-lookup"><span data-stu-id="b00e6-105">You can use Microsoft 365 data loss prevention (DLP) to monitor the actions that are being taken on items you've determined to be sensitive and to help prevent the unintentional sharing of those items.</span></span> <span data-ttu-id="b00e6-106">Para más información sobre DLP en punto de conexión de Microsoft, consulte [Obtenga más información acerca de la prevención contra la pérdida de datos](dlp-learn-about-dlp.md).</span><span class="sxs-lookup"><span data-stu-id="b00e6-106">For more information on DLP, see [Learn about data loss prevention](dlp-learn-about-dlp.md).</span></span>

<span data-ttu-id="b00e6-107">**La prevención de pérdida de datos en punto de conexión** (Endpoint DLP) amplía la supervisión de la actividad y las capacidades de protección de DLP a elementos confidenciales que estén en dispositivos con Windows 10.</span><span class="sxs-lookup"><span data-stu-id="b00e6-107">**Endpoint data loss prevention** (Endpoint DLP) extends the activity monitoring and protection capabilities of DLP to sensitive items that are on Windows 10 devices.</span></span> <span data-ttu-id="b00e6-108">Una vez que los dispositivos están incorporados en las soluciones del Centro de cumplimiento de Microsoft 365, la información sobre las acciones de los usuarios relacionadas con los elementos confidenciales se hace visible en el[explorador de actividades](data-classification-activity-explorer.md), y se pueden aplicar acciones de protección a estos elementos mediante [directivas DLP](create-test-tune-dlp-policy.md).</span><span class="sxs-lookup"><span data-stu-id="b00e6-108">Once devices are onboarded into the Microsoft 365 compliance solutions, the information about what users are doing with sensitive items is made visible in [activity explorer](data-classification-activity-explorer.md) and you can enforce protective actions on those items via [DLP policies](create-test-tune-dlp-policy.md).</span></span>

## <a name="endpoint-activities-you-can-monitor-and-take-action-on"></a><span data-ttu-id="b00e6-109">Actividades en punto de conexión que puede supervisar y sobre las que puede tomar medidas</span><span class="sxs-lookup"><span data-stu-id="b00e6-109">Endpoint activities you can monitor and take action on</span></span>

<span data-ttu-id="b00e6-110">DLP en punto de conexión de Microsoft le permite auditar y administrar los siguientes tipos de actividades que los usuarios llevan a cabo en elementos confidenciales de los dispositivos que ejecutan Windows 10.</span><span class="sxs-lookup"><span data-stu-id="b00e6-110">Microsoft Endpoint DLP enables you to audit and manage the following types of activities users take on sensitive items on devices running Windows 10.</span></span> 

|<span data-ttu-id="b00e6-111">Actividad</span><span class="sxs-lookup"><span data-stu-id="b00e6-111">Activity</span></span> |<span data-ttu-id="b00e6-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="b00e6-112">Description</span></span>  | <span data-ttu-id="b00e6-113">Auditable/Restringible</span><span class="sxs-lookup"><span data-stu-id="b00e6-113">Auditable/restictable</span></span>|
|---------|---------|---------|
|<span data-ttu-id="b00e6-114">cargar en el servicio en la nube o acceso por exploradores no permitidos</span><span class="sxs-lookup"><span data-stu-id="b00e6-114">upload to cloud service, or access by unallowed browsers</span></span>    | <span data-ttu-id="b00e6-115">Detecta cuándo un usuario intenta cargar un elemento en un dominio de servicio restringido o tener acceso a un elemento con un explorador.</span><span class="sxs-lookup"><span data-stu-id="b00e6-115">Detects when a user attempts to upload an item to a restricted service domain or access an item through a browser.</span></span>  <span data-ttu-id="b00e6-116">Si usa un explorador que se muestra en DLP como un explorador que no es el permitido, la actividad de carga se bloqueará y se redirigirá al usuario para usar la arista de cromo.</span><span class="sxs-lookup"><span data-stu-id="b00e6-116">If they are using a browser that is listed in DLP as an being an unallowed browser, the upload activity will be blocked and the user is redirected to use Edge Chromium.</span></span> <span data-ttu-id="b00e6-117">Por último, cromo puede permitir o bloquear la carga o el acceso en función de la configuración de la Directiva DLP.</span><span class="sxs-lookup"><span data-stu-id="b00e6-117">Edge Chromium will then either allow or block the upload or access based on the DLP policy configuration</span></span>         |<span data-ttu-id="b00e6-118">auditable y restringible</span><span class="sxs-lookup"><span data-stu-id="b00e6-118">auditable and restrictable</span></span>|
|<span data-ttu-id="b00e6-119">copiar a otra aplicación</span><span class="sxs-lookup"><span data-stu-id="b00e6-119">copy to other app</span></span>    |<span data-ttu-id="b00e6-120">Se detecta cuando un usuario intenta copiar información de un elemento protegido y, a continuación, lo pega en otra aplicación, proceso o elemento.</span><span class="sxs-lookup"><span data-stu-id="b00e6-120">Detects when a user attempts to copy information from a protected item and then paste it into another app, process or item.</span></span> <span data-ttu-id="b00e6-121">Esta actividad no detecta la copia y el pegado de información dentro de la misma aplicación, proceso o elemento.</span><span class="sxs-lookup"><span data-stu-id="b00e6-121">Copying and pasting information within the same app, process, or item is not detected by this activity.</span></span>         | <span data-ttu-id="b00e6-122">auditable y restringible</span><span class="sxs-lookup"><span data-stu-id="b00e6-122">auditable and restrictable</span></span>|
|<span data-ttu-id="b00e6-123">copiar en un medio extraíble USB</span><span class="sxs-lookup"><span data-stu-id="b00e6-123">copy to USB removable media</span></span> |<span data-ttu-id="b00e6-124">Detecta cuando un usuario intenta copiar un elemento o información en un medio extraíble o un dispositivo USB.</span><span class="sxs-lookup"><span data-stu-id="b00e6-124">Detects when a user attempts to copy an item or information to removable media or USB device.</span></span>         | <span data-ttu-id="b00e6-125">auditable y restringible</span><span class="sxs-lookup"><span data-stu-id="b00e6-125">auditable and restrictable</span></span>|
|<span data-ttu-id="b00e6-126">Copiar en un recurso compartido de red</span><span class="sxs-lookup"><span data-stu-id="b00e6-126">copy to a network share</span></span>    |<span data-ttu-id="b00e6-127">Detecta cuando un usuario intenta copiar un elemento en un recurso compartido de red o en una unidad de red asignada</span><span class="sxs-lookup"><span data-stu-id="b00e6-127">Detects when a user attempts to copy an item to a network share or mapped network drive</span></span>         |<span data-ttu-id="b00e6-128">auditable y restringible</span><span class="sxs-lookup"><span data-stu-id="b00e6-128">auditable and restrictable</span></span>|
|<span data-ttu-id="b00e6-129">imprimir un documento</span><span class="sxs-lookup"><span data-stu-id="b00e6-129">print a document</span></span>    |<span data-ttu-id="b00e6-130">Detecta cuando un usuario intenta imprimir un elemento protegido en una impresora local o de red.</span><span class="sxs-lookup"><span data-stu-id="b00e6-130">Detects when a user attempts to print a protected item to a local or network printer.</span></span>| <span data-ttu-id="b00e6-131">auditable y restringible</span><span class="sxs-lookup"><span data-stu-id="b00e6-131">auditable and restrictable</span></span>         |
|<span data-ttu-id="b00e6-132">copiar a una sesión remota</span><span class="sxs-lookup"><span data-stu-id="b00e6-132">copy to a remote session</span></span>|<span data-ttu-id="b00e6-133">Detecta cuando un usuario intenta copiar un elemento a una sesión de escritorio remoto</span><span class="sxs-lookup"><span data-stu-id="b00e6-133">Detects when a user attempts to copy an item to a remote desktop session</span></span> |  <span data-ttu-id="b00e6-134">auditable y restringible</span><span class="sxs-lookup"><span data-stu-id="b00e6-134">auditable and restrictable</span></span>|
|<span data-ttu-id="b00e6-135">copiar en un dispositivo Bluetooth</span><span class="sxs-lookup"><span data-stu-id="b00e6-135">copy to a Bluetooth device</span></span>|<span data-ttu-id="b00e6-136">Detecta cuando un usuario intenta copiar un elemento en una aplicación Bluetooth no permitida (según se define en la lista de aplicaciones de Bluetooth no permitidas en la configuración del punto de conexión DLP).</span><span class="sxs-lookup"><span data-stu-id="b00e6-136">Detects when a user attempts to copy an item to an unallowed Bluetooth app (as defined in the list of unallowed Bluetooth aps in Endpoint DLP settings).</span></span>| <span data-ttu-id="b00e6-137">auditable y restringible</span><span class="sxs-lookup"><span data-stu-id="b00e6-137">auditable and restrictable</span></span>|
|<span data-ttu-id="b00e6-138">crear un elemento</span><span class="sxs-lookup"><span data-stu-id="b00e6-138">create an item</span></span>|<span data-ttu-id="b00e6-139">Detecta cuándo un usuario crea un elemento</span><span class="sxs-lookup"><span data-stu-id="b00e6-139">Detects when a user creates an item</span></span>| <span data-ttu-id="b00e6-140">auditable</span><span class="sxs-lookup"><span data-stu-id="b00e6-140">auditable</span></span>|
|<span data-ttu-id="b00e6-141">cambiar el nombre de un elemento</span><span class="sxs-lookup"><span data-stu-id="b00e6-141">rename an item</span></span>|<span data-ttu-id="b00e6-142">Detecta cuando un usuario cambia el nombre de un elemento</span><span class="sxs-lookup"><span data-stu-id="b00e6-142">Detects when a user renames an item</span></span>| <span data-ttu-id="b00e6-143">auditable</span><span class="sxs-lookup"><span data-stu-id="b00e6-143">auditable</span></span>|

 ## <a name="monitored-files"></a><span data-ttu-id="b00e6-144">Archivos supervisados</span><span class="sxs-lookup"><span data-stu-id="b00e6-144">Monitored files</span></span>

<span data-ttu-id="b00e6-145">La DLP en punto de conexión admite la supervisión de estos tipos de archivo:</span><span class="sxs-lookup"><span data-stu-id="b00e6-145">Endpoint DLP supports monitoring of these file types:</span></span>

- <span data-ttu-id="b00e6-146">archivos de Word</span><span class="sxs-lookup"><span data-stu-id="b00e6-146">Word files</span></span>
- <span data-ttu-id="b00e6-147">archivos de PowerPoint</span><span class="sxs-lookup"><span data-stu-id="b00e6-147">PowerPoint files</span></span>
- <span data-ttu-id="b00e6-148">archivos de Excel</span><span class="sxs-lookup"><span data-stu-id="b00e6-148">Excel files</span></span>
- <span data-ttu-id="b00e6-149">archivos PDF</span><span class="sxs-lookup"><span data-stu-id="b00e6-149">PDF files</span></span>
- <span data-ttu-id="b00e6-150">archivos .csv</span><span class="sxs-lookup"><span data-stu-id="b00e6-150">.csv files</span></span>
- <span data-ttu-id="b00e6-151">archivos .tsv</span><span class="sxs-lookup"><span data-stu-id="b00e6-151">.tsv files</span></span>
- <span data-ttu-id="b00e6-152">archivos .txt</span><span class="sxs-lookup"><span data-stu-id="b00e6-152">.txt files</span></span>
- <span data-ttu-id="b00e6-153">archivos .rtf</span><span class="sxs-lookup"><span data-stu-id="b00e6-153">.rtf files</span></span>
- <span data-ttu-id="b00e6-154">archivos .c</span><span class="sxs-lookup"><span data-stu-id="b00e6-154">.c files</span></span>
- <span data-ttu-id="b00e6-155">archivos .class</span><span class="sxs-lookup"><span data-stu-id="b00e6-155">.class files</span></span>
- <span data-ttu-id="b00e6-156">archivos .cpp</span><span class="sxs-lookup"><span data-stu-id="b00e6-156">.cpp files</span></span>
- <span data-ttu-id="b00e6-157">archivos .cs</span><span class="sxs-lookup"><span data-stu-id="b00e6-157">.cs files</span></span>
- <span data-ttu-id="b00e6-158">archivos .h</span><span class="sxs-lookup"><span data-stu-id="b00e6-158">.h files</span></span>
- <span data-ttu-id="b00e6-159">archivos .java</span><span class="sxs-lookup"><span data-stu-id="b00e6-159">.java files</span></span>
 
<span data-ttu-id="b00e6-160">De forma predeterminada, la DLP en punto de conexión audita las actividades para estos tipos de archivo, incluso si no hay una coincidencia de directiva.</span><span class="sxs-lookup"><span data-stu-id="b00e6-160">By default, endpoint DLP audits the activities for these file types, even if there isn't a policy match.</span></span> <span data-ttu-id="b00e6-161">Si solo quiere supervisar los datos de las coincidencias de directivas, puede desactivar **Auditar siempre para la actividad de archivos de los dispositivos** en la configuración global de DLP en punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="b00e6-161">If you only want monitoring data from policy matches, you can turn off the **Always audit file activity for devices** in the endpoint DLP global settings.</span></span> <span data-ttu-id="b00e6-162">Si esta configuración está instalada, las actividades de cualquier archivo Word, PowerPoint, Excel, PDF y .csv siempre se auditan, incluso si el dispositivo no está dirigido por ninguna directiva.</span><span class="sxs-lookup"><span data-stu-id="b00e6-162">If this setting is on, activities on any Word, PowerPoint, Excel, PDF, and .csv file are always audited even if the device is not targeted by any policy.</span></span>

<span data-ttu-id="b00e6-163">DLP en punto de conexión supervisa la actividad basada en un tipo de extensiones multipropósito de correo Internet (MIME), por lo que las actividades se capturan incluso si se cambia la extensión de archivo.</span><span class="sxs-lookup"><span data-stu-id="b00e6-163">Endpoint DLP monitors activity-based on MIME type, so activities will be captured even if the file extension is changed.</span></span> 

## <a name="whats-different-in-endpoint-dlp"></a><span data-ttu-id="b00e6-164">¿Qué es diferente en DLP en punto de conexión?</span><span class="sxs-lookup"><span data-stu-id="b00e6-164">What's different in Endpoint DLP</span></span>

<span data-ttu-id="b00e6-165">Debe tener en cuenta algunos conceptos adicionales antes de profundizar en DLP en punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="b00e6-165">There are a few extra concepts that you need to be aware of before you dig into Endpoint DLP.</span></span>

### <a name="enabling-device-management"></a><span data-ttu-id="b00e6-166">Habilitar la administración de dispositivos</span><span class="sxs-lookup"><span data-stu-id="b00e6-166">Enabling Device management</span></span>

<span data-ttu-id="b00e6-167">La administración de dispositivos es la funcionalidad que permite la colección de telemetría desde dispositivos y la incluye en las soluciones de cumplimiento de Microsoft 365 como DLP en punto de conexión y la [administración de riesgos internos](insider-risk-management.md).</span><span class="sxs-lookup"><span data-stu-id="b00e6-167">Device management is the functionality that enables the collection of telemetry from devices and brings it into Microsoft 365 compliance solutions like Endpoint DLP and [Insider Risk management](insider-risk-management.md).</span></span> <span data-ttu-id="b00e6-168">Necesitará incorporar todos los dispositivos que quiera usar como ubicaciones en directivas DLP.</span><span class="sxs-lookup"><span data-stu-id="b00e6-168">You'll need to onboard all devices you want to use as locations in DLP policies.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="b00e6-169">![habilitar la administración de dispositivos](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span><span class="sxs-lookup"><span data-stu-id="b00e6-169">![enable device management](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span></span>

<span data-ttu-id="b00e6-170">La incorporación y la retirada se controlan mediante scripts que se descargan desde el centro de administración de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="b00e6-170">Onboarding and offboarding are handled via scripts you download from the Device management center.</span></span> <span data-ttu-id="b00e6-171">El centro tiene scripts personalizados para cada uno de estos métodos de implementación:</span><span class="sxs-lookup"><span data-stu-id="b00e6-171">The center has custom scripts for each of these deployment methods:</span></span>

- <span data-ttu-id="b00e6-172">script local (hasta 10 equipos)</span><span class="sxs-lookup"><span data-stu-id="b00e6-172">local script (up to 10 machines)</span></span>
- <span data-ttu-id="b00e6-173">Directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="b00e6-173">Group policy</span></span>
- <span data-ttu-id="b00e6-174">System Center Configuration Manager (versión 1610 o posterior)</span><span class="sxs-lookup"><span data-stu-id="b00e6-174">System Center Configuration Manager (version 1610 or later)</span></span>
- <span data-ttu-id="b00e6-175">Administración de dispositivos móviles/Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="b00e6-175">Mobile Device Management/Microsoft Intune</span></span>
- <span data-ttu-id="b00e6-176">Scripts de incorporación de VDI para equipos no persistentes</span><span class="sxs-lookup"><span data-stu-id="b00e6-176">VDI onboarding scripts for non-persistent machines</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="b00e6-177">![página de incorporación de dispositivos](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)</span><span class="sxs-lookup"><span data-stu-id="b00e6-177">![device onboarding page](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)</span></span>

 <span data-ttu-id="b00e6-178">Use los procedimientos descritos en [Introducción a DLP en punto de conexión de Microsoft 365](endpoint-dlp-getting-started.md) para incorporar dispositivos.</span><span class="sxs-lookup"><span data-stu-id="b00e6-178">Use the procedures in [Getting started with Microsoft 365 Endpoint DLP](endpoint-dlp-getting-started.md) to onboard devices.</span></span>

<span data-ttu-id="b00e6-179">Si incorporó dispositivos a través de [Protección contra amenazas avanzada de Microsoft Defender](/windows/security/threat-protection/), estos dispositivos se mostrarán automáticamente en la lista de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="b00e6-179">If you have onboarded devices through [Microsoft Defender for Endpoint](/windows/security/threat-protection/), those devices will automatically show up in the list of devices.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="b00e6-180">![lista de dispositivos administrados](../media/endpoint-dlp-learn-about-2-device-list.png)</span><span class="sxs-lookup"><span data-stu-id="b00e6-180">![managed devices list](../media/endpoint-dlp-learn-about-2-device-list.png)</span></span>

### <a name="viewing-endpoint-dlp-data"></a><span data-ttu-id="b00e6-181">Visualizar datos de DLP en punto de conexión</span><span class="sxs-lookup"><span data-stu-id="b00e6-181">Viewing Endpoint DLP data</span></span>

<span data-ttu-id="b00e6-182">Puede ver las alertas relacionadas con las directivas DLP ejecutadas en los dispositivos de punto de conexión si va al [Panel de administración de alertas de DLP](dlp-configure-view-alerts-policies.md).</span><span class="sxs-lookup"><span data-stu-id="b00e6-182">You can view alerts related to DLP policies enforced on endpoint devices by going to the [DLP Alerts Management Dashboard](dlp-configure-view-alerts-policies.md).</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="b00e6-183">![Información de la alerta](../media/Alert-info-1.png)</span><span class="sxs-lookup"><span data-stu-id="b00e6-183">![Alert info](../media/Alert-info-1.png)</span></span>

<span data-ttu-id="b00e6-184">También puede ver los detalles del evento asociado con metadatos enriquecidos en el mismo panel</span><span class="sxs-lookup"><span data-stu-id="b00e6-184">You can also view details of the associated event with rich metadata in the same dashboard</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="b00e6-185">![información del evento](../media/Event-info-1.png)</span><span class="sxs-lookup"><span data-stu-id="b00e6-185">![event info](../media/Event-info-1.png)</span></span>

<span data-ttu-id="b00e6-186">Una vez que se incorpora un dispositivo, la información sobre las actividades auditadas fluye al explorador de actividad, incluso antes de que configure e implemente las directivas DLP que tienen dispositivos como ubicación.</span><span class="sxs-lookup"><span data-stu-id="b00e6-186">Once a device is onboarded, information about audited activities flows into Activity explorer even before you configure and deploy any DLP policies that have devices as a location.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="b00e6-187">![eventos de DLP en punto de conexión en el explorador de actividad](../media/endpoint-dlp-learn-about-4-activity-explorer.png)</span><span class="sxs-lookup"><span data-stu-id="b00e6-187">![endpoint dlp events in activity explorer](../media/endpoint-dlp-learn-about-4-activity-explorer.png)</span></span>

<span data-ttu-id="b00e6-188">DLP en punto de conexión recopila información exhaustiva sobre la actividad auditada.</span><span class="sxs-lookup"><span data-stu-id="b00e6-188">Endpoint DLP collects extensive information on audited activity.</span></span>

<span data-ttu-id="b00e6-189">Por ejemplo, si se copia un archivo a un medio USB extraíble, vería estos atributos en los detalles de actividad:</span><span class="sxs-lookup"><span data-stu-id="b00e6-189">For example, if a file is copied to removable USB media, you'd see these attributes in the activity details:</span></span>

- <span data-ttu-id="b00e6-190">tipo de actividad</span><span class="sxs-lookup"><span data-stu-id="b00e6-190">activity type</span></span>
- <span data-ttu-id="b00e6-191">IP del cliente</span><span class="sxs-lookup"><span data-stu-id="b00e6-191">client IP</span></span>
- <span data-ttu-id="b00e6-192">ruta de acceso del archivo de destino</span><span class="sxs-lookup"><span data-stu-id="b00e6-192">target file path</span></span>
- <span data-ttu-id="b00e6-193">ocurrió una marca de tiempo</span><span class="sxs-lookup"><span data-stu-id="b00e6-193">happened timestamp</span></span>
- <span data-ttu-id="b00e6-194">nombre de archivo</span><span class="sxs-lookup"><span data-stu-id="b00e6-194">file name</span></span>
- <span data-ttu-id="b00e6-195">usuario</span><span class="sxs-lookup"><span data-stu-id="b00e6-195">user</span></span>
- <span data-ttu-id="b00e6-196">extensión de archivo</span><span class="sxs-lookup"><span data-stu-id="b00e6-196">file extension</span></span>
- <span data-ttu-id="b00e6-197">tamaño de archivo</span><span class="sxs-lookup"><span data-stu-id="b00e6-197">file size</span></span>
- <span data-ttu-id="b00e6-198">tipo de información confidencial (si corresponde)</span><span class="sxs-lookup"><span data-stu-id="b00e6-198">sensitive information type (if applicable)</span></span>
- <span data-ttu-id="b00e6-199">valor sha1</span><span class="sxs-lookup"><span data-stu-id="b00e6-199">sha1 value</span></span>
- <span data-ttu-id="b00e6-200">valor sha256</span><span class="sxs-lookup"><span data-stu-id="b00e6-200">sha256 value</span></span>
- <span data-ttu-id="b00e6-201">nombre de archivo anterior</span><span class="sxs-lookup"><span data-stu-id="b00e6-201">previous file name</span></span>
- <span data-ttu-id="b00e6-202">ubicación</span><span class="sxs-lookup"><span data-stu-id="b00e6-202">location</span></span>
- <span data-ttu-id="b00e6-203">primario</span><span class="sxs-lookup"><span data-stu-id="b00e6-203">parent</span></span>
- <span data-ttu-id="b00e6-204">ruta de acceso al archivo</span><span class="sxs-lookup"><span data-stu-id="b00e6-204">filepath</span></span>
- <span data-ttu-id="b00e6-205">tipo de ubicación de origen</span><span class="sxs-lookup"><span data-stu-id="b00e6-205">source location type</span></span>
- <span data-ttu-id="b00e6-206">plataforma</span><span class="sxs-lookup"><span data-stu-id="b00e6-206">platform</span></span>
- <span data-ttu-id="b00e6-207">nombre de dispositivo</span><span class="sxs-lookup"><span data-stu-id="b00e6-207">device name</span></span>
- <span data-ttu-id="b00e6-208">tipo de ubicación de destino</span><span class="sxs-lookup"><span data-stu-id="b00e6-208">destination location type</span></span>
- <span data-ttu-id="b00e6-209">aplicación que realizó la copia</span><span class="sxs-lookup"><span data-stu-id="b00e6-209">application that performed the copy</span></span>
- <span data-ttu-id="b00e6-210">Id. de dispositivo de Microsoft Defender para punto de conexión (si corresponde)</span><span class="sxs-lookup"><span data-stu-id="b00e6-210">Microsoft Defender for Endpoint device ID (if applicable)</span></span>
- <span data-ttu-id="b00e6-211">fabricante del dispositivo multimedia extraíble</span><span class="sxs-lookup"><span data-stu-id="b00e6-211">removable media device manufacturer</span></span>
- <span data-ttu-id="b00e6-212">modelo del dispositivo multimedia extraíble</span><span class="sxs-lookup"><span data-stu-id="b00e6-212">removable media device model</span></span>
- <span data-ttu-id="b00e6-213">número de serie del dispositivo multimedia extraíble</span><span class="sxs-lookup"><span data-stu-id="b00e6-213">removable media device serial number</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="b00e6-214">![copiar a los atributos de actividad del USB](../media/endpoint-dlp-learn-about-5-activity-attributes.png)</span><span class="sxs-lookup"><span data-stu-id="b00e6-214">![copy to usb activity attributes](../media/endpoint-dlp-learn-about-5-activity-attributes.png)</span></span>

## <a name="next-steps"></a><span data-ttu-id="b00e6-215">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="b00e6-215">Next steps</span></span>

<span data-ttu-id="b00e6-216">Ahora que ya conoce DLP en punto de conexión, estos son los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="b00e6-216">Now that you've learned about Endpoint DLP, your next steps are:</span></span>

1) [<span data-ttu-id="b00e6-217">Introducción a la prevención de pérdida de datos en punto de conexión de Microsoft </span><span class="sxs-lookup"><span data-stu-id="b00e6-217">Getting started with Microsoft Endpoint data loss prevention </span></span>](endpoint-dlp-getting-started.md)
2) [<span data-ttu-id="b00e6-218">Uso de la prevención de pérdida de datos en punto de conexión de Microsoft</span><span class="sxs-lookup"><span data-stu-id="b00e6-218">Using Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)

## <a name="see-also"></a><span data-ttu-id="b00e6-219">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b00e6-219">See also</span></span>

- [<span data-ttu-id="b00e6-220">Introducción a la prevención de pérdida de datos en punto de conexión de Microsoft</span><span class="sxs-lookup"><span data-stu-id="b00e6-220">Getting started with Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
- [<span data-ttu-id="b00e6-221">Uso de la prevención de pérdida de datos en punto de conexión de Microsoft</span><span class="sxs-lookup"><span data-stu-id="b00e6-221">Using Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="b00e6-222">Obtenga más información acerca de la prevención contra la pérdida de datos</span><span class="sxs-lookup"><span data-stu-id="b00e6-222">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="b00e6-223">Crear, probar y optimizar una directiva DLP</span><span class="sxs-lookup"><span data-stu-id="b00e6-223">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="b00e6-224">Introducción al explorador de actividad</span><span class="sxs-lookup"><span data-stu-id="b00e6-224">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="b00e6-225">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="b00e6-225">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/)
- [<span data-ttu-id="b00e6-226">Administración de riesgos internos</span><span class="sxs-lookup"><span data-stu-id="b00e6-226">Insider Risk management</span></span>](insider-risk-management.md)