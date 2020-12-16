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
ms.openlocfilehash: 1dac32505144c3966ad2219cc69a33ba29f194dc
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/15/2020
ms.locfileid: "49682631"
---
# <a name="learn-about-microsoft-365-endpoint-data-loss-prevention"></a><span data-ttu-id="27f03-104">Obtenga más información sobre la prevención de pérdida de datos de Microsoft 365 de punto de conexión</span><span class="sxs-lookup"><span data-stu-id="27f03-104">Learn about Microsoft 365 Endpoint data loss prevention</span></span>

<span data-ttu-id="27f03-105">Puede usar la prevención de pérdida de datos (DLP) de Microsoft 365 para supervisar las acciones que se realizan en elementos que ha determinado que son confidenciales y para ayudar a evitar el uso compartido accidental de estos elementos.</span><span class="sxs-lookup"><span data-stu-id="27f03-105">You can use Microsoft 365 data loss prevention (DLP) to monitor the actions that are being taken on items you've determined to be sensitive and to help prevent the unintentional sharing of those items.</span></span> <span data-ttu-id="27f03-106">Para obtener más información sobre DLP, consulte [Información general sobre la prevención de pérdida de datos](data-loss-prevention-policies.md).</span><span class="sxs-lookup"><span data-stu-id="27f03-106">For more information on DLP, see [Overview of data loss prevention](data-loss-prevention-policies.md).</span></span>

<span data-ttu-id="27f03-107">**La prevención de pérdida de datos en punto de conexión** (Endpoint DLP) amplía la supervisión de la actividad y las capacidades de protección de DLP a elementos confidenciales que estén en dispositivos con Windows 10.</span><span class="sxs-lookup"><span data-stu-id="27f03-107">**Endpoint data loss prevention** (Endpoint DLP) extends the activity monitoring and protection capabilities of DLP to sensitive items that are on Windows 10 devices.</span></span> <span data-ttu-id="27f03-108">Una vez que los dispositivos están incorporados en las soluciones del Centro de cumplimiento de Microsoft 365, la información sobre las acciones de los usuarios relacionadas con los elementos confidenciales se hace visible en el[explorador de actividades](data-classification-activity-explorer.md), y se pueden aplicar acciones de protección a estos elementos mediante [directivas DLP](create-test-tune-dlp-policy.md).</span><span class="sxs-lookup"><span data-stu-id="27f03-108">Once devices are onboarded into the Microsoft 365 compliance solutions, the information about what users are doing with sensitive items is made visible in [activity explorer](data-classification-activity-explorer.md) and you can enforce protective actions on those items via [DLP policies](create-test-tune-dlp-policy.md).</span></span>

## <a name="endpoint-activities-you-can-monitor-and-take-action-on"></a><span data-ttu-id="27f03-109">Actividades en punto de conexión que puede supervisar y sobre las que puede tomar medidas</span><span class="sxs-lookup"><span data-stu-id="27f03-109">Endpoint activities you can monitor and take action on</span></span>

<span data-ttu-id="27f03-110">DLP en punto de conexión de Microsoft le permite auditar y administrar los siguientes tipos de actividades que los usuarios llevan a cabo en elementos confidenciales de los dispositivos que ejecutan Windows 10.</span><span class="sxs-lookup"><span data-stu-id="27f03-110">Microsoft Endpoint DLP enables you to audit and manage the following types of activities users take on sensitive items on devices running Windows 10.</span></span>


|<span data-ttu-id="27f03-111">actividad</span><span class="sxs-lookup"><span data-stu-id="27f03-111">activity</span></span> |<span data-ttu-id="27f03-112">description</span><span class="sxs-lookup"><span data-stu-id="27f03-112">description</span></span>  | <span data-ttu-id="27f03-113">auditables/restictable</span><span class="sxs-lookup"><span data-stu-id="27f03-113">auditable/restictable</span></span>|
|---------|---------|---------|
|<span data-ttu-id="27f03-114">cargar en el servicio en la nube o acceso por exploradores no permitidos</span><span class="sxs-lookup"><span data-stu-id="27f03-114">upload to cloud service, or access by unallowed browsers</span></span>    | <span data-ttu-id="27f03-115">Detecta cuándo un usuario intenta cargar un elemento en un dominio de servicio restringido o tener acceso a un elemento con un explorador.</span><span class="sxs-lookup"><span data-stu-id="27f03-115">Detects when a user attempts to upload an item to a restricted service domain or access an item through a browser.</span></span>  <span data-ttu-id="27f03-116">Si usa un explorador que se muestra en DLP como un explorador que no es el permitido, la actividad de carga se bloqueará y se redirigirá al usuario para usar la arista de cromo.</span><span class="sxs-lookup"><span data-stu-id="27f03-116">If they are using a browser that is listed in DLP as an being an unallowed browser, the upload activity will be blocked and the user is redirected to use Edge Chromium.</span></span> <span data-ttu-id="27f03-117">Por último, cromo puede permitir o bloquear la carga o el acceso en función de la configuración de la Directiva DLP.</span><span class="sxs-lookup"><span data-stu-id="27f03-117">Edge Chromium will then either allow or block the upload or access based on the DLP policy configuration</span></span>         |<span data-ttu-id="27f03-118">auditable y restringible</span><span class="sxs-lookup"><span data-stu-id="27f03-118">auditable and restrictable</span></span>|
|<span data-ttu-id="27f03-119">copiar a otra aplicación</span><span class="sxs-lookup"><span data-stu-id="27f03-119">copy to other app</span></span>    |<span data-ttu-id="27f03-120">Se detecta cuando un usuario intenta copiar información de un elemento protegido y, a continuación, lo pega en otra aplicación, proceso o elemento.</span><span class="sxs-lookup"><span data-stu-id="27f03-120">Detects when a user attempts to copy information from a protected item and then paste it into another app, process or item.</span></span> <span data-ttu-id="27f03-121">Esta actividad no detecta la copia y el pegado de información dentro de la misma aplicación, proceso o elemento.</span><span class="sxs-lookup"><span data-stu-id="27f03-121">Copying and pasting information within the same app, process, or item is not detected by this activity.</span></span>         | <span data-ttu-id="27f03-122">auditable y restringible</span><span class="sxs-lookup"><span data-stu-id="27f03-122">auditable and restrictable</span></span>|
|<span data-ttu-id="27f03-123">copiar en un medio extraíble USB</span><span class="sxs-lookup"><span data-stu-id="27f03-123">copy to USB removable media</span></span> |<span data-ttu-id="27f03-124">Detecta cuando un usuario intenta copiar un elemento o información en un medio extraíble o un dispositivo USB.</span><span class="sxs-lookup"><span data-stu-id="27f03-124">Detects when a user attempts to copy an item or information to removable media or USB device.</span></span>         | <span data-ttu-id="27f03-125">auditable y restringible</span><span class="sxs-lookup"><span data-stu-id="27f03-125">auditable and restrictable</span></span>|
|<span data-ttu-id="27f03-126">Copiar en un recurso compartido de red</span><span class="sxs-lookup"><span data-stu-id="27f03-126">copy to a network share</span></span>    |<span data-ttu-id="27f03-127">Detecta cuando un usuario intenta copiar un elemento en un recurso compartido de red o en una unidad de red asignada</span><span class="sxs-lookup"><span data-stu-id="27f03-127">Detects when a user attempts to copy an item to a network share or mapped network drive</span></span>         |<span data-ttu-id="27f03-128">auditable y restringible</span><span class="sxs-lookup"><span data-stu-id="27f03-128">auditable and restrictable</span></span>|
|<span data-ttu-id="27f03-129">imprimir un documento</span><span class="sxs-lookup"><span data-stu-id="27f03-129">print a document</span></span>    |<span data-ttu-id="27f03-130">Detecta cuando un usuario intenta imprimir un elemento protegido en una impresora local o de red.</span><span class="sxs-lookup"><span data-stu-id="27f03-130">Detects when a user attempts to print a protected item to a local or network printer.</span></span>| <span data-ttu-id="27f03-131">auditable y restringible</span><span class="sxs-lookup"><span data-stu-id="27f03-131">auditable and restrictable</span></span>         |
|<span data-ttu-id="27f03-132">crear un elemento</span><span class="sxs-lookup"><span data-stu-id="27f03-132">create an item</span></span>|<span data-ttu-id="27f03-133">Detecta cuándo un usuario crea un elemento</span><span class="sxs-lookup"><span data-stu-id="27f03-133">Detects when a user creates an item</span></span>| <span data-ttu-id="27f03-134">auditable</span><span class="sxs-lookup"><span data-stu-id="27f03-134">auditable</span></span>|
|<span data-ttu-id="27f03-135">cambiar el nombre de un elemento</span><span class="sxs-lookup"><span data-stu-id="27f03-135">rename an item</span></span>|<span data-ttu-id="27f03-136">Detecta cuando un usuario cambia el nombre de un elemento</span><span class="sxs-lookup"><span data-stu-id="27f03-136">Detects when a user renames an item</span></span>| <span data-ttu-id="27f03-137">auditable</span><span class="sxs-lookup"><span data-stu-id="27f03-137">auditable</span></span>|


## <a name="whats-different-in-endpoint-dlp"></a><span data-ttu-id="27f03-138">¿Qué es diferente en DLP en punto de conexión?</span><span class="sxs-lookup"><span data-stu-id="27f03-138">What's different in Endpoint DLP</span></span>

<span data-ttu-id="27f03-139">Debe tener en cuenta algunos conceptos adicionales antes de profundizar en DLP en punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="27f03-139">There are a few extra concepts that you need to be aware of before you dig into Endpoint DLP.</span></span>

### <a name="enabling-device-management"></a><span data-ttu-id="27f03-140">Habilitar la administración de dispositivos</span><span class="sxs-lookup"><span data-stu-id="27f03-140">Enabling Device management</span></span>

<span data-ttu-id="27f03-141">La administración de dispositivos es la funcionalidad que permite la colección de telemetría desde dispositivos y la incluye en las soluciones de cumplimiento de Microsoft 365 como DLP en punto de conexión y la [administración de riesgos internos](insider-risk-management.md).</span><span class="sxs-lookup"><span data-stu-id="27f03-141">Device management is the functionality that enables the collection of telemetry from devices and brings it into Microsoft 365 compliance solutions like Endpoint DLP and [Insider Risk management](insider-risk-management.md).</span></span> <span data-ttu-id="27f03-142">Necesitará incorporar todos los dispositivos que quiera usar como ubicaciones en directivas DLP.</span><span class="sxs-lookup"><span data-stu-id="27f03-142">You'll need to onboard all devices you want to use as locations in DLP policies.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="27f03-143">![habilitar la administración de dispositivos](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span><span class="sxs-lookup"><span data-stu-id="27f03-143">![enable device management](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span></span>

<span data-ttu-id="27f03-144">La incorporación y la retirada se controlan mediante scripts que se descargan desde el centro de administración de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="27f03-144">Onboarding and offboarding are handled via scripts you download from the Device management center.</span></span> <span data-ttu-id="27f03-145">El centro tiene scripts personalizados para cada uno de estos métodos de implementación:</span><span class="sxs-lookup"><span data-stu-id="27f03-145">The center has custom scripts for each of these deployment methods:</span></span>

- <span data-ttu-id="27f03-146">script local (hasta 10 equipos)</span><span class="sxs-lookup"><span data-stu-id="27f03-146">local script (up to 10 machines)</span></span>
- <span data-ttu-id="27f03-147">Directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="27f03-147">Group policy</span></span>
- <span data-ttu-id="27f03-148">System Center Configuration Manager (versión 1610 o posterior)</span><span class="sxs-lookup"><span data-stu-id="27f03-148">System Center Configuration Manager (version 1610 or later)</span></span>
- <span data-ttu-id="27f03-149">Administración de dispositivos móviles/Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="27f03-149">Mobile Device Management/Microsoft Intune</span></span>
- <span data-ttu-id="27f03-150">Scripts de incorporación de VDI para equipos no persistentes</span><span class="sxs-lookup"><span data-stu-id="27f03-150">VDI onboarding scripts for non-persistent machines</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="27f03-151">![página de incorporación de dispositivos](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)</span><span class="sxs-lookup"><span data-stu-id="27f03-151">![device onboarding page](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)</span></span>

 <span data-ttu-id="27f03-152">Use los procedimientos descritos en [Introducción a DLP en punto de conexión de Microsoft 365](endpoint-dlp-getting-started.md) para incorporar dispositivos.</span><span class="sxs-lookup"><span data-stu-id="27f03-152">Use the procedures in [Getting started with Microsoft 365 Endpoint DLP](endpoint-dlp-getting-started.md) to onboard devices.</span></span>

<span data-ttu-id="27f03-153">Si incorporó dispositivos a través de [Protección contra amenazas avanzada de Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/), estos dispositivos se mostrarán automáticamente en la lista de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="27f03-153">If you have onboarded devices through [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/), those devices will automatically show up in the list of devices.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="27f03-154">![lista de dispositivos administrados](../media/endpoint-dlp-learn-about-2-device-list.png)</span><span class="sxs-lookup"><span data-stu-id="27f03-154">![managed devices list](../media/endpoint-dlp-learn-about-2-device-list.png)</span></span>

### <a name="viewing-endpoint-dlp-data"></a><span data-ttu-id="27f03-155">Visualizar datos de DLP en punto de conexión</span><span class="sxs-lookup"><span data-stu-id="27f03-155">Viewing Endpoint DLP data</span></span>

 <span data-ttu-id="27f03-156">DLP en punto de conexión supervisa la actividad basada en un tipo de extensiones multipropósito de correo Internet (MIME), por lo que las actividades se capturan incluso si se cambia la extensión de archivo.</span><span class="sxs-lookup"><span data-stu-id="27f03-156">Endpoint DLP monitors activity-based on MIME type, so activities will be captured even if the file extension is changed.</span></span> <span data-ttu-id="27f03-157">Actualmente, se admiten los siguientes tipos de archivo:</span><span class="sxs-lookup"><span data-stu-id="27f03-157">At this time the following file types are supported:</span></span>

- <span data-ttu-id="27f03-158">archivos de Word</span><span class="sxs-lookup"><span data-stu-id="27f03-158">Word files</span></span>
- <span data-ttu-id="27f03-159">archivos de PowerPoint</span><span class="sxs-lookup"><span data-stu-id="27f03-159">PowerPoint files</span></span>
- <span data-ttu-id="27f03-160">archivos de Excel</span><span class="sxs-lookup"><span data-stu-id="27f03-160">Excel files</span></span>
- <span data-ttu-id="27f03-161">archivos PDF</span><span class="sxs-lookup"><span data-stu-id="27f03-161">PDF files</span></span>
- <span data-ttu-id="27f03-162">archivos .csv</span><span class="sxs-lookup"><span data-stu-id="27f03-162">.csv files</span></span>
- <span data-ttu-id="27f03-163">archivos .tsv</span><span class="sxs-lookup"><span data-stu-id="27f03-163">.tsv files</span></span>
- <span data-ttu-id="27f03-164">archivos .txt</span><span class="sxs-lookup"><span data-stu-id="27f03-164">.txt files</span></span>
- <span data-ttu-id="27f03-165">archivos .rtf</span><span class="sxs-lookup"><span data-stu-id="27f03-165">.rtf files</span></span>
- <span data-ttu-id="27f03-166">archivos .c</span><span class="sxs-lookup"><span data-stu-id="27f03-166">.c files</span></span>
- <span data-ttu-id="27f03-167">archivos .class</span><span class="sxs-lookup"><span data-stu-id="27f03-167">.class files</span></span>
- <span data-ttu-id="27f03-168">archivos .cpp</span><span class="sxs-lookup"><span data-stu-id="27f03-168">.cpp files</span></span>
- <span data-ttu-id="27f03-169">archivos .cs</span><span class="sxs-lookup"><span data-stu-id="27f03-169">.cs files</span></span>
- <span data-ttu-id="27f03-170">archivos .h</span><span class="sxs-lookup"><span data-stu-id="27f03-170">.h files</span></span>
- <span data-ttu-id="27f03-171">archivos .java</span><span class="sxs-lookup"><span data-stu-id="27f03-171">.java files</span></span>

> [!NOTE]
> <span data-ttu-id="27f03-172">La DLP en punto de conexión evalúa todos los tipos de archivo anteriores según la directiva DLP y aplica las acciones de protección correspondientes.</span><span class="sxs-lookup"><span data-stu-id="27f03-172">Endpoint DLP evaluates files of all the above types against the DLP policy and applies protection actions accordingly.</span></span> <span data-ttu-id="27f03-173">Todos los archivos que coinciden con una directiva DLP, estén o no bloqueados, se auditan para todas las acciones admitidas.</span><span class="sxs-lookup"><span data-stu-id="27f03-173">All files that match a DLP policy are audited for all supported actions, even if they aren't blocked.</span></span> <span data-ttu-id="27f03-174">Además, la actividad de archivo que se lleva a cabo en cualquier archivo de Word, PowerPoint, Excel, PDF o archivo .csv se audita de forma predeterminada, independientemente de si existe una directiva DLP o si estos archivos coinciden.</span><span class="sxs-lookup"><span data-stu-id="27f03-174">In addition, file activity performed on any Word, PowerPoint, Excel, PDF, and .csv file is audited by default, independent of whether a DLP policy exists or matches these files.</span></span>

<span data-ttu-id="27f03-175">Puede ver las alertas relacionadas con las directivas DLP ejecutadas en los dispositivos de punto de conexión si va al [Panel de administración de alertas de DLP](dlp-configure-view-alerts-policies.md).</span><span class="sxs-lookup"><span data-stu-id="27f03-175">You can view alerts related to DLP policies enforced on endpoint devices by going to the [DLP Alerts Management Dashboard](dlp-configure-view-alerts-policies.md).</span></span>

![Información de la alerta](../media/Alert-info-1.png)

<span data-ttu-id="27f03-177">También puede ver los detalles del evento asociado con metadatos enriquecidos en el mismo panel</span><span class="sxs-lookup"><span data-stu-id="27f03-177">You can also view details of the associated event with rich metadata in the same dashboard</span></span>

![información del evento](../media/Event-info-1.png)

<span data-ttu-id="27f03-179">Una vez que se incorpora un dispositivo, la información sobre las actividades auditadas fluye al explorador de actividad, incluso antes de que configure e implemente las directivas DLP que tienen dispositivos como ubicación.</span><span class="sxs-lookup"><span data-stu-id="27f03-179">Once a device is onboarded, information about audited activities flows into Activity explorer even before you configure and deploy any DLP policies that have devices as a location.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="27f03-180">![eventos de DLP en punto de conexión en el explorador de actividad](../media/endpoint-dlp-learn-about-4-activity-explorer.png)</span><span class="sxs-lookup"><span data-stu-id="27f03-180">![endpoint dlp events in activity explorer](../media/endpoint-dlp-learn-about-4-activity-explorer.png)</span></span>

<span data-ttu-id="27f03-181">DLP en punto de conexión recopila información exhaustiva sobre la actividad auditada.</span><span class="sxs-lookup"><span data-stu-id="27f03-181">Endpoint DLP collects extensive information on audited activity.</span></span>

<span data-ttu-id="27f03-182">Por ejemplo, si se copia un archivo a un medio USB extraíble, vería estos atributos en los detalles de actividad:</span><span class="sxs-lookup"><span data-stu-id="27f03-182">For example, if a file is copied to removable USB media, you'd see these attributes in the activity details:</span></span>

- <span data-ttu-id="27f03-183">tipo de actividad</span><span class="sxs-lookup"><span data-stu-id="27f03-183">activity type</span></span>
- <span data-ttu-id="27f03-184">IP del cliente</span><span class="sxs-lookup"><span data-stu-id="27f03-184">client IP</span></span>
- <span data-ttu-id="27f03-185">ruta de acceso del archivo de destino</span><span class="sxs-lookup"><span data-stu-id="27f03-185">target file path</span></span>
- <span data-ttu-id="27f03-186">ocurrió una marca de tiempo</span><span class="sxs-lookup"><span data-stu-id="27f03-186">happened timestamp</span></span>
- <span data-ttu-id="27f03-187">nombre de archivo</span><span class="sxs-lookup"><span data-stu-id="27f03-187">file name</span></span>
- <span data-ttu-id="27f03-188">usuario</span><span class="sxs-lookup"><span data-stu-id="27f03-188">user</span></span>
- <span data-ttu-id="27f03-189">extensión de archivo</span><span class="sxs-lookup"><span data-stu-id="27f03-189">file extension</span></span>
- <span data-ttu-id="27f03-190">tamaño de archivo</span><span class="sxs-lookup"><span data-stu-id="27f03-190">file size</span></span>
- <span data-ttu-id="27f03-191">tipo de información confidencial (si corresponde)</span><span class="sxs-lookup"><span data-stu-id="27f03-191">sensitive information type (if applicable)</span></span>
- <span data-ttu-id="27f03-192">valor sha1</span><span class="sxs-lookup"><span data-stu-id="27f03-192">sha1 value</span></span>
- <span data-ttu-id="27f03-193">valor sha256</span><span class="sxs-lookup"><span data-stu-id="27f03-193">sha256 value</span></span>
- <span data-ttu-id="27f03-194">nombre de archivo anterior</span><span class="sxs-lookup"><span data-stu-id="27f03-194">previous file name</span></span>
- <span data-ttu-id="27f03-195">ubicación</span><span class="sxs-lookup"><span data-stu-id="27f03-195">location</span></span>
- <span data-ttu-id="27f03-196">primario</span><span class="sxs-lookup"><span data-stu-id="27f03-196">parent</span></span>
- <span data-ttu-id="27f03-197">ruta de acceso al archivo</span><span class="sxs-lookup"><span data-stu-id="27f03-197">filepath</span></span>
- <span data-ttu-id="27f03-198">tipo de ubicación de origen</span><span class="sxs-lookup"><span data-stu-id="27f03-198">source location type</span></span>
- <span data-ttu-id="27f03-199">plataforma</span><span class="sxs-lookup"><span data-stu-id="27f03-199">platform</span></span>
- <span data-ttu-id="27f03-200">nombre de dispositivo</span><span class="sxs-lookup"><span data-stu-id="27f03-200">device name</span></span>
- <span data-ttu-id="27f03-201">tipo de ubicación de destino</span><span class="sxs-lookup"><span data-stu-id="27f03-201">destination location type</span></span>
- <span data-ttu-id="27f03-202">aplicación que realizó la copia</span><span class="sxs-lookup"><span data-stu-id="27f03-202">application that performed the copy</span></span>
- <span data-ttu-id="27f03-203">Id. de dispositivo de Microsoft Defender para punto de conexión (si corresponde)</span><span class="sxs-lookup"><span data-stu-id="27f03-203">Microsoft Defender for Endpoint device ID (if applicable)</span></span>
- <span data-ttu-id="27f03-204">fabricante del dispositivo multimedia extraíble</span><span class="sxs-lookup"><span data-stu-id="27f03-204">removable media device manufacturer</span></span>
- <span data-ttu-id="27f03-205">modelo del dispositivo multimedia extraíble</span><span class="sxs-lookup"><span data-stu-id="27f03-205">removable media device model</span></span>
- <span data-ttu-id="27f03-206">número de serie del dispositivo multimedia extraíble</span><span class="sxs-lookup"><span data-stu-id="27f03-206">removable media device serial number</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="27f03-207">![copiar a los atributos de actividad del USB](../media/endpoint-dlp-learn-about-5-activity-attributes.png)</span><span class="sxs-lookup"><span data-stu-id="27f03-207">![copy to usb activity attributes](../media/endpoint-dlp-learn-about-5-activity-attributes.png)</span></span>

## <a name="next-steps"></a><span data-ttu-id="27f03-208">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="27f03-208">Next steps</span></span>

<span data-ttu-id="27f03-209">Ahora que ya conoce DLP en punto de conexión, estos son los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="27f03-209">Now that you've learned about Endpoint DLP, your next steps are:</span></span>

1) [<span data-ttu-id="27f03-210">Introducción a la prevención de pérdida de datos en punto de conexión de Microsoft </span><span class="sxs-lookup"><span data-stu-id="27f03-210">Getting started with Microsoft Endpoint data loss prevention </span></span>](endpoint-dlp-getting-started.md)
2) [<span data-ttu-id="27f03-211">Uso de la prevención de pérdida de datos en punto de conexión de Microsoft</span><span class="sxs-lookup"><span data-stu-id="27f03-211">Using Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)

## <a name="see-also"></a><span data-ttu-id="27f03-212">Consulte también</span><span class="sxs-lookup"><span data-stu-id="27f03-212">See also</span></span>

- [<span data-ttu-id="27f03-213">Introducción a la prevención de pérdida de datos en punto de conexión de Microsoft</span><span class="sxs-lookup"><span data-stu-id="27f03-213">Getting started with Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
- [<span data-ttu-id="27f03-214">Uso de la prevención de pérdida de datos en punto de conexión de Microsoft</span><span class="sxs-lookup"><span data-stu-id="27f03-214">Using Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="27f03-215">Información general sobre la prevención de pérdida de datos</span><span class="sxs-lookup"><span data-stu-id="27f03-215">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="27f03-216">Crear, probar y optimizar una directiva DLP</span><span class="sxs-lookup"><span data-stu-id="27f03-216">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="27f03-217">Introducción al explorador de actividad</span><span class="sxs-lookup"><span data-stu-id="27f03-217">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="27f03-218">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="27f03-218">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)
- [<span data-ttu-id="27f03-219">Administración de riesgos internos</span><span class="sxs-lookup"><span data-stu-id="27f03-219">Insider Risk management</span></span>](insider-risk-management.md)
