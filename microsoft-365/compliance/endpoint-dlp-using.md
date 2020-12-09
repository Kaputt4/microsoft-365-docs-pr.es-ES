---
title: Uso de la prevención de perdida de datos en punto de conexión
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/21/2020
audience: ITPro
ms.topic: article
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
description: Aprenda cómo configurar las directivas de prevención de pérdida de datos (DLP) para usar las ubicaciones de la Prevención de pérdida de datos de los puntos de conexión (EPDLP) de Microsoft 365.
ms.openlocfilehash: 0a6883bd785141af6f198f0cd871c11794618e27
ms.sourcegitcommit: 4debeb8f0fce67f361676340fc390f1b283a3069
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2020
ms.locfileid: "49561687"
---
# <a name="using-endpoint-data-loss-prevention"></a><span data-ttu-id="0ba4f-103">Uso de la prevención de pérdida de datos en punto de conexión</span><span class="sxs-lookup"><span data-stu-id="0ba4f-103">Using Endpoint data loss prevention</span></span>

<span data-ttu-id="0ba4f-104">Este artículo le guiará a través de tres escenarios donde puede crear y modificar una directiva DLP que use dispositivos como una ubicación.</span><span class="sxs-lookup"><span data-stu-id="0ba4f-104">This article walks you through three scenarios where you create and modify a DLP policy that uses devices as a location.</span></span>

## <a name="dlp-settings"></a><span data-ttu-id="0ba4f-105">Configuración DLP</span><span class="sxs-lookup"><span data-stu-id="0ba4f-105">DLP settings</span></span>

<span data-ttu-id="0ba4f-106">Antes de empezar, configure las opciones de configuración DLP que se aplican a todas las directivas DLP para dispositivos.</span><span class="sxs-lookup"><span data-stu-id="0ba4f-106">Before you get started you should set up your DLP settings which are applied to all DLP policies for devices.</span></span> <span data-ttu-id="0ba4f-107">Debe configurarlas si tiene previsto crear directivas que cumplan con lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0ba4f-107">You must configure these if you intend to create policies that enforce:</span></span>

- <span data-ttu-id="0ba4f-108">restricciones de salida de la nube</span><span class="sxs-lookup"><span data-stu-id="0ba4f-108">cloud egress restrictions</span></span>
- <span data-ttu-id="0ba4f-109">restricciones de aplicaciones no permitidas</span><span class="sxs-lookup"><span data-stu-id="0ba4f-109">unallowed apps restrictions</span></span>

<span data-ttu-id="0ba4f-110">O bien</span><span class="sxs-lookup"><span data-stu-id="0ba4f-110">Or</span></span>

- <span data-ttu-id="0ba4f-111">Si desea excluir de la supervisión las rutas de archivo ruidosas</span><span class="sxs-lookup"><span data-stu-id="0ba4f-111">If you want to exclude noisy file paths from monitoring</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="0ba4f-112">![Configuración DLP](../media/endpoint-dlp-1-using-dlp-settings.png)</span><span class="sxs-lookup"><span data-stu-id="0ba4f-112">![DLP settings](../media/endpoint-dlp-1-using-dlp-settings.png)</span></span>

### <a name="file-path-exclusions"></a><span data-ttu-id="0ba4f-113">Exclusiones de ruta de archivo</span><span class="sxs-lookup"><span data-stu-id="0ba4f-113">File path exclusions</span></span>

<span data-ttu-id="0ba4f-114">Es posible que quiera excluir determinadas rutas de supervisión DLP, alertas DLP y aplicación de directivas DLP en sus dispositivos, ya sea porque tienen demasiado ruido o no contienen archivos que le interesan.</span><span class="sxs-lookup"><span data-stu-id="0ba4f-114">You may want to exclude certain paths from DLP monitoring, DLP alerting, and DLP policy enforcement on your devices because they are too noisy or don’t contain files you are interested in.</span></span> <span data-ttu-id="0ba4f-115">Los archivos en esas ubicaciones no se auditarán y los archivos que se creen o modifiquen en esas ubicaciones no se someterán a la aplicación de directivas DLP.</span><span class="sxs-lookup"><span data-stu-id="0ba4f-115">Files in those locations will not be audited and any files that are created or modified in those locations will not be subject to DLP policy enforcement.</span></span> <span data-ttu-id="0ba4f-116">Puede configurar exclusiones de ruta en configuración DLP.</span><span class="sxs-lookup"><span data-stu-id="0ba4f-116">You can configure path exclusions in DLP settings.</span></span>

<span data-ttu-id="0ba4f-117">Puede usar esta lógica para crear sus rutas de exclusión:</span><span class="sxs-lookup"><span data-stu-id="0ba4f-117">You can use this logic to construct your exclusion paths:</span></span>

- <span data-ttu-id="0ba4f-118">Una ruta de archivo es válida cuando termina en "\". Esto incluye solo a los archivos que se encuentran directamente dentro de la carpeta.</span><span class="sxs-lookup"><span data-stu-id="0ba4f-118">Valid file path that ends with ‘\’, which means only files directly under folder.</span></span> <br/><span data-ttu-id="0ba4f-119">Por ejemplo: C:\Temp</span><span class="sxs-lookup"><span data-stu-id="0ba4f-119">For example: C:\Temp</span></span>\

- <span data-ttu-id="0ba4f-120">Una ruta de archivo es válida cuando termina en "\*". Esto incluye solo a los archivos que se encuentran dentro de las subcarpetas, además de los archivos ubicados directamente dentro de la carpeta.</span><span class="sxs-lookup"><span data-stu-id="0ba4f-120">Valid file path that ends with ‘\*’, which means only files under sub-folders, besides the files directly under the folder.</span></span> <br/><span data-ttu-id="0ba4f-121">Por ejemplo: C:\Temp\*</span><span class="sxs-lookup"><span data-stu-id="0ba4f-121">For example: C:\Temp\*</span></span>

- <span data-ttu-id="0ba4f-122">Una ruta de archivo es válida cuando termina sin "\" o "\*". Esto incluye a todos los archivos que se encuentran directamente dentro de la carpeta o subcarpetas.</span><span class="sxs-lookup"><span data-stu-id="0ba4f-122">Valid file path that ends without ‘\’ or ‘\*’, which means all files directly under folder and all sub-folders.</span></span> <br/><span data-ttu-id="0ba4f-123">Por ejemplo: C:\Temp</span><span class="sxs-lookup"><span data-stu-id="0ba4f-123">For example: C:\Temp</span></span>

- <span data-ttu-id="0ba4f-124">Una ruta con comodín con "\" en cada lado.</span><span class="sxs-lookup"><span data-stu-id="0ba4f-124">A path with wildcard between ‘\’ from each side.</span></span> <br/><span data-ttu-id="0ba4f-125">Por ejemplo: C:\Usuarios\*\Escritorio</span><span class="sxs-lookup"><span data-stu-id="0ba4f-125">For example: C:\Users\*\Desktop</span></span>\

- <span data-ttu-id="0ba4f-126">Una ruta con comodín con "\" en cada lado y con "(número)" para dar un número exacto de subcarpetas.</span><span class="sxs-lookup"><span data-stu-id="0ba4f-126">A path with wildcard between ‘\’ from each side and with ‘(number)’ to give exact number of subfolders.</span></span> <br/><span data-ttu-id="0ba4f-127">Por ejemplo: C:\Usuarios\*(1)\Descargas</span><span class="sxs-lookup"><span data-stu-id="0ba4f-127">For example: C:\Users\*(1)\Downloads</span></span>\

- <span data-ttu-id="0ba4f-128">Una ruta con variables de entorno del SISTEMA.</span><span class="sxs-lookup"><span data-stu-id="0ba4f-128">A path with SYSTEM environment variables.</span></span> <br/><span data-ttu-id="0ba4f-129">Por ejemplo: %SystemDrive%\Test\*</span><span class="sxs-lookup"><span data-stu-id="0ba4f-129">For example: %SystemDrive%\Test\*</span></span>

- <span data-ttu-id="0ba4f-130">Una combinación de todas las anteriores.</span><span class="sxs-lookup"><span data-stu-id="0ba4f-130">A mix of all the above.</span></span> <br/><span data-ttu-id="0ba4f-131">Por ejemplo: %SystemDrive%\Users\*\Documents\*(2)\Sub</span><span class="sxs-lookup"><span data-stu-id="0ba4f-131">For example: %SystemDrive%\Users\*\Documents\*(2)\Sub</span></span>\

### <a name="unallowed-apps"></a><span data-ttu-id="0ba4f-132">Aplicaciones no permitidas</span><span class="sxs-lookup"><span data-stu-id="0ba4f-132">Unallowed apps</span></span>

<span data-ttu-id="0ba4f-133">Cuando la configuración de **Acceso por aplicaciones y exploradores no permitidos** de una directiva esté activada y los usuarios intenten usar estas aplicaciones para acceder a un archivo protegido, la actividad se permitirá, se bloqueará, o se bloqueará pero los usuarios podrán invalidar la restricción.</span><span class="sxs-lookup"><span data-stu-id="0ba4f-133">When a policy's **Access by unallowed apps and browsers** setting is turned on and users attempt to use these apps to access a protected file, the activity will be allowed, blocked, or blocked but users can override the restriction.</span></span> <span data-ttu-id="0ba4f-134">Toda actividad es auditada y está disponible para su revisión en el explorador de actividades.</span><span class="sxs-lookup"><span data-stu-id="0ba4f-134">All activity is audited and available to review in activity explorer.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0ba4f-135">No incluya la ruta de acceso al archivo ejecutable, solo el nombre del archivo ejecutable (por ejemplo, browser.exe).</span><span class="sxs-lookup"><span data-stu-id="0ba4f-135">Do not include the path to the executable, but only the executable name (such as browser.exe).</span></span>


### <a name="browser-and-domain-restrictions"></a><span data-ttu-id="0ba4f-136">Restricciones del dominio y del explorador:</span><span class="sxs-lookup"><span data-stu-id="0ba4f-136">Browser and domain restrictions</span></span>
<span data-ttu-id="0ba4f-137">Restrinja el uso compartido de los archivos confidenciales que coincidan con las directivas con dominios de servicio en la nube sin restricciones.</span><span class="sxs-lookup"><span data-stu-id="0ba4f-137">Restrict sensitive files that match your policies from being shared with unrestricted cloud service domains.</span></span>

#### <a name="service-domains"></a><span data-ttu-id="0ba4f-138">Dominios de servicio</span><span class="sxs-lookup"><span data-stu-id="0ba4f-138">Service domains</span></span>

<span data-ttu-id="0ba4f-139">Puede controlar si los archivos confidenciales protegidos por sus directivas se pueden cargar en dominios de servicio específicos de Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="0ba4f-139">You can control whether sensitive files protected by your policies can be uploaded to specific service domains from Microsoft Edge.</span></span>

<span data-ttu-id="0ba4f-140">Si el modo de lista está configurado en **Bloquear**, el usuario no podrá cargar elementos confidenciales a esos dominios.</span><span class="sxs-lookup"><span data-stu-id="0ba4f-140">If the list mode is set to **Block**, then user will not be able to upload sensitive items to those domains.</span></span> <span data-ttu-id="0ba4f-141">Cuando se bloquea una acción de carga porque un elemento coincide con una directiva DLP, la DLP genera una advertencia o bloquea la carga del elemento confidencial.</span><span class="sxs-lookup"><span data-stu-id="0ba4f-141">When an upload action is blocked because an item matches a DLP policy, DLP will either generate a warning or block the upload of the sensitive item.</span></span>

<span data-ttu-id="0ba4f-142">Si el modo de lista está configurado en **Permitir**, los usuarios podrán cargar elementos confidenciales \**_solo_* _ a dichos dominios y no se permitirá el acceso de carga a los demás dominios.</span><span class="sxs-lookup"><span data-stu-id="0ba4f-142">If the list mode is set to **Allow**, then users will be able to upload sensitive items \**_only_* _ to those domains, and upload access to all other domains is not allowed.</span></span>

#### <a name="unallowed-browsers"></a><span data-ttu-id="0ba4f-143">Exploradores no permitidos</span><span class="sxs-lookup"><span data-stu-id="0ba4f-143">Unallowed browsers</span></span>

<span data-ttu-id="0ba4f-144">Agregue exploradores, identificados por sus nombres ejecutables, que no tendrán acceso a los archivos que cumplan las condiciones de una directiva DLP aplicada cuya restricción de carga a servicios en la nube esté configurada para bloquearse o bloquear una invalidación.</span><span class="sxs-lookup"><span data-stu-id="0ba4f-144">You add browsers, identified by their executable names, that will be blocked from accessing files that match the conditions of an enforced a DLP policy where the upload to cloud services restriction is set to block or block override.</span></span> <span data-ttu-id="0ba4f-145">Cuando estos exploradores no puedan acceder a un archivo, los usuarios finales verán una notificación del sistema que les pedirá que abran el archivo a través de Edge Chromium.</span><span class="sxs-lookup"><span data-stu-id="0ba4f-145">When these browsers are blocked from accessing a file, the end users will see a toast notification asking them to open the file through Edge Chromium.</span></span>

### <a name="always-audit-file-activity-from-onboarded-devices"></a><span data-ttu-id="0ba4f-146">Auditar siempre la actividad de archivos de los dispositivos integrados</span><span class="sxs-lookup"><span data-stu-id="0ba4f-146">Always audit file activity from onboarded devices</span></span>

<span data-ttu-id="0ba4f-147">Controle si la actividad DLP de Office, los archivos PDF y CSV se auditan automáticamente y están disponibles para su revisión en la telemetría de auditoría y en el explorador de actividad de los dispositivos integrados.</span><span class="sxs-lookup"><span data-stu-id="0ba4f-147">Control whether DLP activity for Office, PDF, and CSV files is automatically audited and available for review in the audit telemetry and the Activity Explorer from onboarded devices.</span></span> 

<span data-ttu-id="0ba4f-148">Si está activado (predeterminado), la actividad de archivo siempre se audita en los dispositivos integrados, independientemente de si están o no incluidos en una directiva DLP activa.</span><span class="sxs-lookup"><span data-stu-id="0ba4f-148">If this is turned On (the default), file activity is always audited for onboarded devices, regardless of whether or not they are included in an active DLP policy.</span></span>
<span data-ttu-id="0ba4f-149">Si está desactivado, la actividad de archivo se audita en los dispositivos integrados, solo si están incluidos en una directiva DLP activa.</span><span class="sxs-lookup"><span data-stu-id="0ba4f-149">If this is turned off, file activity is audited for onboarded devices only when they are included in an active DLP policy.</span></span> 


## <a name="tying-dlp-settings-together"></a><span data-ttu-id="0ba4f-150">Vincular las opciones de configuración DLP</span><span class="sxs-lookup"><span data-stu-id="0ba4f-150">Tying DLP settings together</span></span>

<span data-ttu-id="0ba4f-151">Con la DLP de los puntos de conexión y el Explorador web Edge Chromium, puede restringir el uso compartido no intencionado de elementos confidenciales a las aplicaciones y servicios en la nube no permitidos.</span><span class="sxs-lookup"><span data-stu-id="0ba4f-151">With Endpoint DLP and Edge Chromium Web browser, you can restrict unintentional sharing of sensitive items to unallowed cloud apps and services.</span></span> <span data-ttu-id="0ba4f-152">Edge Chromium comprende cuándo un elemento está restringido por una directiva DLP de los puntos de conexión y aplica las restricciones de acceso.</span><span class="sxs-lookup"><span data-stu-id="0ba4f-152">Edge Chromium understands when an item is restricted by an Endpoint DLP policy and enforces access restrictions.</span></span>

<span data-ttu-id="0ba4f-153">Cuando usa la DLP de los puntos de conexión como una ubicación en una directiva DLP configurada correctamente y en el explorador Edge Chromium, los exploradores no permitidos que haya definido en esta configuración no tendrán acceso a los elementos confidenciales que coincidan con los controles de la directiva DLP.</span><span class="sxs-lookup"><span data-stu-id="0ba4f-153">When you use Endpoint DLP as a location in a properly configured DLP policy and the Edge Chromium browser, the unallowed browsers that you've defined in these settings will be prevented from accessing the sensitive items that match your DLP policy controls.</span></span> <span data-ttu-id="0ba4f-154">En su lugar, los usuarios serán redirigidos para usar Edge Chromium y Edge Chromium, con su reconocimiento de las restricciones impuestas por DLP, podrá bloquear o restringir actividades cuando se cumplan las condiciones de la directiva DLP.</span><span class="sxs-lookup"><span data-stu-id="0ba4f-154">Instead, users will be redirected to use Edge Chromium and Edge Chromium, with its understanding of DLP imposed restrictions, can block or restrict activities when the conditions in the DLP policy are met.</span></span>

<span data-ttu-id="0ba4f-155">Para usar esta restricción, tendrá que configurar tres partes importantes:</span><span class="sxs-lookup"><span data-stu-id="0ba4f-155">To use this restriction you’ll need to configure three important pieces:</span></span>

1. <span data-ttu-id="0ba4f-156">Especifique los sitios (servicios, dominios y direcciones IP) con los que no quiere que se compartan elementos confidenciales.</span><span class="sxs-lookup"><span data-stu-id="0ba4f-156">Specify the places – services, domains, IP addresses – that you want to prevent sensitive items from being shared to.</span></span>

2. <span data-ttu-id="0ba4f-157">Agregue los exploradores que no tienen permitido acceder a ciertos elementos confidenciales cuando se produzca una coincidencia de directiva DLP.</span><span class="sxs-lookup"><span data-stu-id="0ba4f-157">Add the browsers that aren’t allowed to access certain sensitive items when a DLP policy match occurs.</span></span>

3. <span data-ttu-id="0ba4f-158">Configure directivas DLP para definir los tipos de elementos confidenciales que deberían tener carga restringida a estos lugares activando _ *Cargar en los servicios en la nube*\* y **Acceso desde un explorador no permitido**.</span><span class="sxs-lookup"><span data-stu-id="0ba4f-158">Configure DLP policies to define the kinds of sensitive items for which upload should be restricted to these places by turning on _ *Upload to cloud services*\* and **Access from unallowed browser**.</span></span>

<span data-ttu-id="0ba4f-159">Puede continuar agregando nuevos servicios, aplicaciones y directivas para ampliar y aumentar las restricciones para satisfacer las necesidades de su empresa y proteger los datos confidenciales.</span><span class="sxs-lookup"><span data-stu-id="0ba4f-159">You can continue to add new services, apps, and policies to extend and augment your restrictions to meet your business needs and protect sensitive data.</span></span> 

<span data-ttu-id="0ba4f-160">Esta configuración garantizará que sus datos estén seguros, evitando así las restricciones innecesarias que impiden o restringen a los usuarios el acceso y el uso compartido de elementos no confidenciales.</span><span class="sxs-lookup"><span data-stu-id="0ba4f-160">This configuration will help ensure your data remains safe while also avoiding unnecessary restrictions that prevent or restrict users from accessing and sharing non-sensitive items.</span></span>

## <a name="endpoint-dlp-policy-scenarios"></a><span data-ttu-id="0ba4f-161">Escenarios de directiva DLP de los puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="0ba4f-161">Endpoint DLP policy scenarios</span></span>

<span data-ttu-id="0ba4f-162">Para ayudarle a familiarizarse con las características de DLP de los puntos de conexión y cómo se muestran en las directivas DLP, hemos recopilado algunos escenarios para que los siga.</span><span class="sxs-lookup"><span data-stu-id="0ba4f-162">To help familiarize you with Endpoint DLP features and how they surface in DLP policies, we've put together some scenarios for you to follow.</span></span> <span data-ttu-id="0ba4f-163">Todo el contenido de DLP de los puntos de conexión se incorporará al conjunto de contenido principal de DLP cuando la DLP de los puntos de conexión esté disponible de manera general.</span><span class="sxs-lookup"><span data-stu-id="0ba4f-163">All the Endpoint DLP content will be folded in to the main DLP content set when Endpoint DLP becomes generally available.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0ba4f-164">Estos escenarios DLP de los puntos de conexión no son los procedimientos oficiales para crear y optimizar directivas DLP.</span><span class="sxs-lookup"><span data-stu-id="0ba4f-164">These Endpoint DLP scenarios are not the official procedures for creating and tuning DLP policies.</span></span> <span data-ttu-id="0ba4f-165">Consulte los temas siguientes cuando necesite trabajar con directivas DLP en situaciones generales:</span><span class="sxs-lookup"><span data-stu-id="0ba4f-165">Refer to the below topics when you need to work with DLP policies in general situations:</span></span>
>- [<span data-ttu-id="0ba4f-166">Información general sobre la prevención de pérdida de datos</span><span class="sxs-lookup"><span data-stu-id="0ba4f-166">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
>- [<span data-ttu-id="0ba4f-167">Introducción a la directiva predeterminada de DLP</span><span class="sxs-lookup"><span data-stu-id="0ba4f-167">Get started with the default DLP policy</span></span>](get-started-with-the-default-dlp-policy.md)
>- [<span data-ttu-id="0ba4f-168">Crear una directiva DLP a partir de una plantilla</span><span class="sxs-lookup"><span data-stu-id="0ba4f-168">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)
>- [<span data-ttu-id="0ba4f-169">Crear, probar y optimizar una directiva DLP</span><span class="sxs-lookup"><span data-stu-id="0ba4f-169">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)

### <a name="scenario-1-create-a-policy-from-a-template-audit-only"></a><span data-ttu-id="0ba4f-170">Escenario 1: crear una directiva a partir de una plantilla, solo auditoría</span><span class="sxs-lookup"><span data-stu-id="0ba4f-170">Scenario 1: Create a policy from a template, audit only</span></span>

<span data-ttu-id="0ba4f-171">Estos escenarios requieren que ya tenga dispositivos incorporados y que presenten informes al Explorador de actividades.</span><span class="sxs-lookup"><span data-stu-id="0ba4f-171">These scenarios require that you already have devices onboarded and reporting into Activity explorer.</span></span> <span data-ttu-id="0ba4f-172">Si todavía no ha incorporado sus dispositivos, consulte [Introducción a la prevención de pérdida de datos de los puntos de conexión](endpoint-dlp-getting-started.md).</span><span class="sxs-lookup"><span data-stu-id="0ba4f-172">If you haven't onboarded devices yet, see [Get started with Endpoint data loss prevention](endpoint-dlp-getting-started.md).</span></span>

1. <span data-ttu-id="0ba4f-173">Abra la [página de prevención de pérdida de datos](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span><span class="sxs-lookup"><span data-stu-id="0ba4f-173">Open the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span></span>

2. <span data-ttu-id="0ba4f-174">Elija **Crear directiva**.</span><span class="sxs-lookup"><span data-stu-id="0ba4f-174">Choose **Create policy**.</span></span>

3. <span data-ttu-id="0ba4f-175">Para este escenario, elija **Privacidad**, después **Datos de información de identificación personal (PII) de Estados Unidos**, y elija **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="0ba4f-175">For this scenario, choose **Privacy**, then **U.S. Personally Identifiable Information (PII) Data** and choose **Next**.</span></span>

4. <span data-ttu-id="0ba4f-176">Desactive el campo **Estado** para todas las ubicaciones excepto para **Dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="0ba4f-176">Toggle the **Status** field to off for all locations except **Devices**.</span></span> <span data-ttu-id="0ba4f-177">Elija **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="0ba4f-177">Choose **Next**.</span></span>

5. <span data-ttu-id="0ba4f-178">Acepte la selección predeterminada **Revisar y personalizar la configuración a partir de la plantilla** y elija **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="0ba4f-178">Accept the default **Review and customize settings from the template** selection and choose **Next**.</span></span>

6. <span data-ttu-id="0ba4f-179">Acepte los valores predeterminados **Acciones de protección** y elija **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="0ba4f-179">Accept the default **Protection actions** values and choose **Next**.</span></span>

7. <span data-ttu-id="0ba4f-180">Seleccione **Auditar o restringir actividades en dispositivos Windows** y deje las acciones configuradas en **Solo auditar**.</span><span class="sxs-lookup"><span data-stu-id="0ba4f-180">Select **Audit or restrict activities on Windows devices** and leave the actions set to **Audit only**.</span></span> <span data-ttu-id="0ba4f-181">Elija **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="0ba4f-181">Choose **Next**.</span></span>

8. <span data-ttu-id="0ba4f-182">Acepte el valor predeterminado **Me gustaría probarlo primero** y elija **Mostrar sugerencias de directiva durante el modo de prueba**.</span><span class="sxs-lookup"><span data-stu-id="0ba4f-182">Accept the default **I'd like to test it out first** value and choose **Show policy tips while in test mode**.</span></span> <span data-ttu-id="0ba4f-183">Elija **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="0ba4f-183">Choose **Next**.</span></span>

9. <span data-ttu-id="0ba4f-184">Revise la configuración y elija **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="0ba4f-184">Review your settings and choose **Submit**.</span></span>

10. <span data-ttu-id="0ba4f-185">La nueva directiva DLP se mostrará en la lista de directivas.</span><span class="sxs-lookup"><span data-stu-id="0ba4f-185">The new DLP policy will appear in the policy list.</span></span>

11. <span data-ttu-id="0ba4f-186">Compruebe que los datos de los puntos de conexión supervisados se encuentren en el Explorador de actividades.</span><span class="sxs-lookup"><span data-stu-id="0ba4f-186">Check Activity explorer for data from the monitored endpoints.</span></span> <span data-ttu-id="0ba4f-187">Configure el filtro por ubicación de los dispositivos, agregue la directiva y, después, filtre por nombre de directiva para ver el impacto de esta directiva.</span><span class="sxs-lookup"><span data-stu-id="0ba4f-187">Set the location filter for devices and add the policy, then filter by policy name to see the impact of this policy.</span></span> <span data-ttu-id="0ba4f-188">Consulte [Introducción al explorador de actividades](data-classification-activity-explorer.md), de ser necesario. </span><span class="sxs-lookup"><span data-stu-id="0ba4f-188">See, [Get started with activity explorer](data-classification-activity-explorer.md) if needed.</span></span>

12. <span data-ttu-id="0ba4f-189">Intente compartir una prueba que incluya contenido que activará la condición de datos de información de identificación personal (PII) de Estados Unidos con alguien ajeno a su organización.</span><span class="sxs-lookup"><span data-stu-id="0ba4f-189">Attempt to share a test that contains content that will trigger the U.S. Personally Identifiable Information (PII) Data condition with someone outside your organization.</span></span> <span data-ttu-id="0ba4f-190">Esto debería activar la directiva.</span><span class="sxs-lookup"><span data-stu-id="0ba4f-190">This should trigger the policy.</span></span>

13. <span data-ttu-id="0ba4f-191">Compruebe que el evento se encuentre en el Explorador de actividades.</span><span class="sxs-lookup"><span data-stu-id="0ba4f-191">Check Activity explorer for the event.</span></span>

### <a name="scenario-2-modify-the-existing-policy-set-an-alert"></a><span data-ttu-id="0ba4f-192">Escenario 2: modificar la directiva existente, configurar una alerta</span><span class="sxs-lookup"><span data-stu-id="0ba4f-192">Scenario 2: Modify the existing policy, set an alert</span></span>

1. <span data-ttu-id="0ba4f-193">Abra la [Página de prevención de pérdida de datos](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span><span class="sxs-lookup"><span data-stu-id="0ba4f-193">Open the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span></span>

2. <span data-ttu-id="0ba4f-194">Elija la directiva **Datos de información de identificación personal (PII) de Estados Unidos** que creó en el escenario 1.</span><span class="sxs-lookup"><span data-stu-id="0ba4f-194">Choose the **U.S. Personally Identifiable Information (PII) Data** policy that you created in scenario 1.</span></span>

3. <span data-ttu-id="0ba4f-195">Elija **editar directiva**.</span><span class="sxs-lookup"><span data-stu-id="0ba4f-195">Choose **edit policy**.</span></span>

4. <span data-ttu-id="0ba4f-196">Vaya a la página **Reglas de DLP avanzadas** y edite el **Bajo volumen de contenido detectado en la información de identificación personal de Estados Unidos**.</span><span class="sxs-lookup"><span data-stu-id="0ba4f-196">Go to the **Advanced DLP rules** page and edit the **Low volume of content detected U.S. Personally Identifiable Inf**.</span></span>

5. <span data-ttu-id="0ba4f-197">Desplácese hacia abajo hasta la sección **Informes de incidentes** y configure **Enviar una alerta a los administradores cuando se produzca una coincidencia de regla** en **Activado**.</span><span class="sxs-lookup"><span data-stu-id="0ba4f-197">Scroll down to the **Incident reports** section and set **Send an alert to admins when a rule match occurs** to **On**.</span></span> <span data-ttu-id="0ba4f-198">Las alertas por correo electrónico se enviarán automáticamente al administrador y a cualquier persona que agregue a la lista de destinatarios.</span><span class="sxs-lookup"><span data-stu-id="0ba4f-198">Email alerts will be automatically sent to the administrator and anyone else you add to the list of recipients.</span></span> 

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="0ba4f-199">![activar-informes-de-incidentes](../media/endpoint-dlp-2-using-dlp-incident-reports.png)</span><span class="sxs-lookup"><span data-stu-id="0ba4f-199">![turn-on-incident-reports](../media/endpoint-dlp-2-using-dlp-incident-reports.png)</span></span>
   
6. <span data-ttu-id="0ba4f-200">Para este escenario, elija **Enviar una alerta cada vez que una actividad coincida con la regla**.</span><span class="sxs-lookup"><span data-stu-id="0ba4f-200">For the purposes of this scenario, choose **Send alert every time an activity matches the rule**.</span></span>

7. <span data-ttu-id="0ba4f-201">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="0ba4f-201">Choose **Save**.</span></span>

8. <span data-ttu-id="0ba4f-202">Conserve todas las opciones de configuración anteriores eligiendo **Siguiente** y, después, **Enviar** los cambios de directiva.</span><span class="sxs-lookup"><span data-stu-id="0ba4f-202">Retain all your previous settings by choosing **Next** and then **Submit** the policy changes.</span></span>

9. <span data-ttu-id="0ba4f-203">Intente compartir una prueba que incluya contenido que activará la condición de datos de información de identificación personal (PII) de Estados Unidos con alguien ajeno a su organización.</span><span class="sxs-lookup"><span data-stu-id="0ba4f-203">Attempt to share a test that contains content that will trigger the U.S. Personally Identifiable Information (PII) Data condition with someone outside your organization.</span></span> <span data-ttu-id="0ba4f-204">Esto debería activar la directiva.</span><span class="sxs-lookup"><span data-stu-id="0ba4f-204">This should trigger the policy.</span></span>

10. <span data-ttu-id="0ba4f-205">Compruebe que el evento se encuentre en el Explorador de actividades.</span><span class="sxs-lookup"><span data-stu-id="0ba4f-205">Check Activity explorer for the event.</span></span>

### <a name="scenario-3-modify-the-existing-policy-block-the-action-with-allow-override"></a><span data-ttu-id="0ba4f-206">Caso 3: modificar la directiva existente, bloquear la acción con permitir invalidación</span><span class="sxs-lookup"><span data-stu-id="0ba4f-206">Scenario 3: Modify the existing policy, block the action with allow override</span></span>

1. <span data-ttu-id="0ba4f-207">Abra la [Página de prevención de pérdida de datos](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span><span class="sxs-lookup"><span data-stu-id="0ba4f-207">Open the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span></span>

2. <span data-ttu-id="0ba4f-208">Elija la directiva **Datos de información de identificación personal (PII) de Estados Unidos** que creó en el escenario 1.</span><span class="sxs-lookup"><span data-stu-id="0ba4f-208">Choose the **U.S. Personally Identifiable Information (PII) Data** policy that you created in scenario 1.</span></span>

3. <span data-ttu-id="0ba4f-209">Elija **editar directiva**.</span><span class="sxs-lookup"><span data-stu-id="0ba4f-209">Choose **edit policy**.</span></span>

4. <span data-ttu-id="0ba4f-210">Vaya a la página **Reglas de DLP avanzadas** y edite el **Bajo volumen de contenido detectado en la información de identificación personal de Estados Unidos**.</span><span class="sxs-lookup"><span data-stu-id="0ba4f-210">Go to the **Advanced DLP rules** page and edit the **Low volume of content detected U.S. Personally Identifiable Inf**.</span></span>

5. <span data-ttu-id="0ba4f-211">Desplácese hacia abajo hasta la sección **Auditar o restringir actividades en dispositivos Windows** y configure la acción correspondiente en **Bloquear con invalidación** para cada actividad.</span><span class="sxs-lookup"><span data-stu-id="0ba4f-211">Scroll down to the **Audit or restrict activities on Windows device** section and for each activity set the corresponding action to  **Block with override**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="0ba4f-212">![configurar bloqueo con acción de invalidación](../media/endpoint-dlp-6-using-dlp-set-blocked-with-override.png)</span><span class="sxs-lookup"><span data-stu-id="0ba4f-212">![set block with override action](../media/endpoint-dlp-6-using-dlp-set-blocked-with-override.png)</span></span>
   
6. <span data-ttu-id="0ba4f-213">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="0ba4f-213">Choose **Save**.</span></span>

7. <span data-ttu-id="0ba4f-214">Repita los pasos del 4 al 7 para el **Alto volumen de contenido detectado en la información de identificación personal de Estados Unidos**.</span><span class="sxs-lookup"><span data-stu-id="0ba4f-214">Repeat steps 4-7 for the **High volume of content detected U.S. Personally Identifiable Inf**.</span></span>

8. <span data-ttu-id="0ba4f-215">Conserve todas las opciones de configuración anteriores eligiendo **Siguiente** y, después, **Enviar** los cambios de directiva.</span><span class="sxs-lookup"><span data-stu-id="0ba4f-215">Retain all your previous settings by choosing **Next** and then **Submit** the policy changes.</span></span>

9. <span data-ttu-id="0ba4f-216">Intente compartir una prueba que incluya contenido que activará la condición de datos de información de identificación personal (PII) de Estados Unidos con alguien ajeno a su organización.</span><span class="sxs-lookup"><span data-stu-id="0ba4f-216">Attempt to share a test that contains content that will trigger the U.S. Personally Identifiable Information (PII) Data condition with someone outside your organization.</span></span> <span data-ttu-id="0ba4f-217">Esto debería activar la directiva.</span><span class="sxs-lookup"><span data-stu-id="0ba4f-217">This should trigger the policy.</span></span>

   <span data-ttu-id="0ba4f-218">Verá un elemento emergente como el siguiente en el dispositivo cliente:</span><span class="sxs-lookup"><span data-stu-id="0ba4f-218">You'll see a popup like this on the client device:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="0ba4f-219">![notificación de invalidación de cliente bloqueado por dlp en punto de conexión](../media/endpoint-dlp-3-using-dlp-client-blocked-override-notification.png)</span><span class="sxs-lookup"><span data-stu-id="0ba4f-219">![endpoint dlp client blocked override notification](../media/endpoint-dlp-3-using-dlp-client-blocked-override-notification.png)</span></span>

10. <span data-ttu-id="0ba4f-220">Compruebe que el evento se encuentre en el Explorador de actividades.</span><span class="sxs-lookup"><span data-stu-id="0ba4f-220">Check Activity explorer for the event.</span></span>

## <a name="see-also"></a><span data-ttu-id="0ba4f-221">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0ba4f-221">See also</span></span>

- [<span data-ttu-id="0ba4f-222">Obtenga más información sobre la prevención de pérdida de datos en punto de conexión</span><span class="sxs-lookup"><span data-stu-id="0ba4f-222">Learn about Endpoint data loss prevention</span></span>](endpoint-dlp-learn-about.md)
- [<span data-ttu-id="0ba4f-223">Introducción a la prevención de pérdida de datos en punto de conexión</span><span class="sxs-lookup"><span data-stu-id="0ba4f-223">Get started with Endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
- [<span data-ttu-id="0ba4f-224">Información general sobre la prevención de pérdida de datos</span><span class="sxs-lookup"><span data-stu-id="0ba4f-224">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="0ba4f-225">Crear, probar y optimizar una directiva DLP</span><span class="sxs-lookup"><span data-stu-id="0ba4f-225">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="0ba4f-226">Introducción al explorador de actividad</span><span class="sxs-lookup"><span data-stu-id="0ba4f-226">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="0ba4f-227">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="0ba4f-227">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)
- <span data-ttu-id="0ba4f-228">[Herramientas y métodos de incorporación para equipos con Windows 10](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span><span class="sxs-lookup"><span data-stu-id="0ba4f-228">[Onboarding tools and methods for Windows 10 machines](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)</span></span>
- [<span data-ttu-id="0ba4f-229">Suscripción a Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0ba4f-229">Microsoft 365 subscription</span></span>](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [<span data-ttu-id="0ba4f-230">Unido a Azure Active Directory (AAD)</span><span class="sxs-lookup"><span data-stu-id="0ba4f-230">Azure Active Directory (AAD) joined</span></span>](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join)
- [<span data-ttu-id="0ba4f-231">Descargue el nuevo Microsoft Edge basado en Chromium</span><span class="sxs-lookup"><span data-stu-id="0ba4f-231">Download the new Microsoft Edge based on Chromium</span></span>](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)
- [<span data-ttu-id="0ba4f-232">Introducción a la directiva predeterminada de DLP</span><span class="sxs-lookup"><span data-stu-id="0ba4f-232">Get started with the default DLP policy</span></span>](get-started-with-the-default-dlp-policy.md)
- [<span data-ttu-id="0ba4f-233">Crear una directiva DLP desde una plantilla</span><span class="sxs-lookup"><span data-stu-id="0ba4f-233">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)
