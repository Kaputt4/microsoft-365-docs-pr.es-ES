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
ms.openlocfilehash: cbd95ed3ee70b69b395f73c83852a9f37a269f0b
ms.sourcegitcommit: 5a1cb7d95070eef47d401a4693cc137a90550a5e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "52259492"
---
# <a name="using-endpoint-data-loss-prevention"></a><span data-ttu-id="4c06c-103">Uso de la prevención de pérdida de datos en punto de conexión</span><span class="sxs-lookup"><span data-stu-id="4c06c-103">Using Endpoint data loss prevention</span></span>

<span data-ttu-id="4c06c-104">Este artículo le guiará a través de tres escenarios donde puede crear y modificar una directiva DLP que use dispositivos como una ubicación.</span><span class="sxs-lookup"><span data-stu-id="4c06c-104">This article walks you through three scenarios where you create and modify a DLP policy that uses devices as a location.</span></span>

## <a name="dlp-settings"></a><span data-ttu-id="4c06c-105">Configuración DLP</span><span class="sxs-lookup"><span data-stu-id="4c06c-105">DLP settings</span></span>

<span data-ttu-id="4c06c-106">Antes de empezar, configure las opciones de configuración DLP que se aplican a todas las directivas DLP para dispositivos.</span><span class="sxs-lookup"><span data-stu-id="4c06c-106">Before you get started you should set up your DLP settings which are applied to all DLP policies for devices.</span></span> <span data-ttu-id="4c06c-107">Debe configurarlas si tiene previsto crear directivas que cumplan con lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4c06c-107">You must configure these if you intend to create policies that enforce:</span></span>

- <span data-ttu-id="4c06c-108">restricciones de salida de la nube</span><span class="sxs-lookup"><span data-stu-id="4c06c-108">cloud egress restrictions</span></span>
- <span data-ttu-id="4c06c-109">restricciones de aplicaciones no permitidas</span><span class="sxs-lookup"><span data-stu-id="4c06c-109">unallowed apps restrictions</span></span>

<span data-ttu-id="4c06c-110">O bien</span><span class="sxs-lookup"><span data-stu-id="4c06c-110">Or</span></span>

- <span data-ttu-id="4c06c-111">Si desea excluir de la supervisión las rutas de archivo ruidosas</span><span class="sxs-lookup"><span data-stu-id="4c06c-111">If you want to exclude noisy file paths from monitoring</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="4c06c-112">![Configuración DLP](../media/endpoint-dlp-1-using-dlp-settings.png)</span><span class="sxs-lookup"><span data-stu-id="4c06c-112">![DLP settings](../media/endpoint-dlp-1-using-dlp-settings.png)</span></span>

### <a name="file-path-exclusions"></a><span data-ttu-id="4c06c-113">Exclusiones de ruta de archivo</span><span class="sxs-lookup"><span data-stu-id="4c06c-113">File path exclusions</span></span>

<span data-ttu-id="4c06c-114">Es posible que quiera excluir determinadas rutas de supervisión DLP, alertas DLP y aplicación de directivas DLP en sus dispositivos, ya sea porque tienen demasiado ruido o no contienen archivos que le interesan.</span><span class="sxs-lookup"><span data-stu-id="4c06c-114">You may want to exclude certain paths from DLP monitoring, DLP alerting, and DLP policy enforcement on your devices because they are too noisy or don’t contain files you are interested in.</span></span> <span data-ttu-id="4c06c-115">Los archivos en esas ubicaciones no se auditarán y los archivos que se creen o modifiquen en esas ubicaciones no se someterán a la aplicación de directivas DLP.</span><span class="sxs-lookup"><span data-stu-id="4c06c-115">Files in those locations will not be audited and any files that are created or modified in those locations will not be subject to DLP policy enforcement.</span></span> <span data-ttu-id="4c06c-116">Puede configurar exclusiones de ruta en configuración DLP.</span><span class="sxs-lookup"><span data-stu-id="4c06c-116">You can configure path exclusions in DLP settings.</span></span>

<span data-ttu-id="4c06c-117">Puede usar esta lógica para crear sus rutas de exclusión:</span><span class="sxs-lookup"><span data-stu-id="4c06c-117">You can use this logic to construct your exclusion paths:</span></span>

- <span data-ttu-id="4c06c-118">Una ruta de archivo es válida cuando termina en "\". Esto incluye solo a los archivos que se encuentran directamente dentro de la carpeta.</span><span class="sxs-lookup"><span data-stu-id="4c06c-118">Valid file path that ends with ‘\’, which means only files directly under folder.</span></span> <br/><span data-ttu-id="4c06c-119">Por ejemplo: C:\Temp</span><span class="sxs-lookup"><span data-stu-id="4c06c-119">For example: C:\Temp</span></span>\

- <span data-ttu-id="4c06c-120">Una ruta de archivo es válida cuando termina en "\*". Esto incluye solo a los archivos que se encuentran dentro de las subcarpetas, además de los archivos ubicados directamente dentro de la carpeta.</span><span class="sxs-lookup"><span data-stu-id="4c06c-120">Valid file path that ends with ‘\*’, which means only files under sub-folders, besides the files directly under the folder.</span></span> <br/><span data-ttu-id="4c06c-121">Por ejemplo: C:\Temp\*</span><span class="sxs-lookup"><span data-stu-id="4c06c-121">For example: C:\Temp\*</span></span>

- <span data-ttu-id="4c06c-122">Una ruta de archivo es válida cuando termina sin "\" o "\*". Esto incluye a todos los archivos que se encuentran directamente dentro de la carpeta o subcarpetas.</span><span class="sxs-lookup"><span data-stu-id="4c06c-122">Valid file path that ends without ‘\’ or ‘\*’, which means all files directly under folder and all sub-folders.</span></span> <br/><span data-ttu-id="4c06c-123">Por ejemplo: C:\Temp</span><span class="sxs-lookup"><span data-stu-id="4c06c-123">For example: C:\Temp</span></span>

- <span data-ttu-id="4c06c-124">Una ruta con comodín con "\" en cada lado.</span><span class="sxs-lookup"><span data-stu-id="4c06c-124">A path with wildcard between ‘\’ from each side.</span></span> <br/><span data-ttu-id="4c06c-125">Por ejemplo: C:\Usuarios\*\Escritorio</span><span class="sxs-lookup"><span data-stu-id="4c06c-125">For example: C:\Users\*\Desktop</span></span>\

- <span data-ttu-id="4c06c-126">Una ruta con comodín con "\" en cada lado y con "(número)" para dar un número exacto de subcarpetas.</span><span class="sxs-lookup"><span data-stu-id="4c06c-126">A path with wildcard between ‘\’ from each side and with ‘(number)’ to give exact number of subfolders.</span></span> <br/><span data-ttu-id="4c06c-127">Por ejemplo: C:\Usuarios\*(1)\Descargas</span><span class="sxs-lookup"><span data-stu-id="4c06c-127">For example: C:\Users\*(1)\Downloads</span></span>\

- <span data-ttu-id="4c06c-128">Una ruta con variables de entorno del SISTEMA.</span><span class="sxs-lookup"><span data-stu-id="4c06c-128">A path with SYSTEM environment variables.</span></span> <br/><span data-ttu-id="4c06c-129">Por ejemplo: %SystemDrive%\Test\*</span><span class="sxs-lookup"><span data-stu-id="4c06c-129">For example: %SystemDrive%\Test\*</span></span>

- <span data-ttu-id="4c06c-130">Una combinación de todas las anteriores.</span><span class="sxs-lookup"><span data-stu-id="4c06c-130">A mix of all the above.</span></span> <br/><span data-ttu-id="4c06c-131">Por ejemplo: %SystemDrive%\Users\*\Documents\*(2)\Sub</span><span class="sxs-lookup"><span data-stu-id="4c06c-131">For example: %SystemDrive%\Users\*\Documents\*(2)\Sub</span></span>\

### <a name="unallowed-apps"></a><span data-ttu-id="4c06c-132">Aplicaciones no permitidas</span><span class="sxs-lookup"><span data-stu-id="4c06c-132">Unallowed apps</span></span>

<span data-ttu-id="4c06c-133">Cuando la configuración de **Acceso por aplicaciones y exploradores no permitidos** de una directiva esté activada y los usuarios intenten usar estas aplicaciones para acceder a un archivo protegido, la actividad se permitirá, se bloqueará, o se bloqueará pero los usuarios podrán invalidar la restricción.</span><span class="sxs-lookup"><span data-stu-id="4c06c-133">When a policy's **Access by unallowed apps and browsers** setting is turned on and users attempt to use these apps to access a protected file, the activity will be allowed, blocked, or blocked but users can override the restriction.</span></span> <span data-ttu-id="4c06c-134">Toda actividad es auditada y está disponible para su revisión en el explorador de actividades.</span><span class="sxs-lookup"><span data-stu-id="4c06c-134">All activity is audited and available to review in activity explorer.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4c06c-135">No incluya la ruta de acceso al archivo ejecutable, solo el nombre del archivo ejecutable (por ejemplo, browser.exe).</span><span class="sxs-lookup"><span data-stu-id="4c06c-135">Do not include the path to the executable, but only the executable name (such as browser.exe).</span></span>


### <a name="browser-and-domain-restrictions"></a><span data-ttu-id="4c06c-136">Restricciones del dominio y del explorador:</span><span class="sxs-lookup"><span data-stu-id="4c06c-136">Browser and domain restrictions</span></span>
<span data-ttu-id="4c06c-137">Restrinja el uso compartido de los archivos confidenciales que coincidan con las directivas con dominios de servicio en la nube sin restricciones.</span><span class="sxs-lookup"><span data-stu-id="4c06c-137">Restrict sensitive files that match your policies from being shared with unrestricted cloud service domains.</span></span>

#### <a name="service-domains"></a><span data-ttu-id="4c06c-138">Dominios de servicio</span><span class="sxs-lookup"><span data-stu-id="4c06c-138">Service domains</span></span>

<span data-ttu-id="4c06c-139">Puede controlar si los archivos confidenciales protegidos por sus directivas se pueden cargar en dominios de servicio específicos de Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="4c06c-139">You can control whether sensitive files protected by your policies can be uploaded to specific service domains from Microsoft Edge.</span></span>

<span data-ttu-id="4c06c-140">Si el modo de lista está configurado en **Bloquear**, el usuario no podrá cargar elementos confidenciales a esos dominios.</span><span class="sxs-lookup"><span data-stu-id="4c06c-140">If the list mode is set to **Block**, then user will not be able to upload sensitive items to those domains.</span></span> <span data-ttu-id="4c06c-141">Cuando se bloquea una acción de carga porque un elemento coincide con una directiva DLP, la DLP genera una advertencia o bloquea la carga del elemento confidencial.</span><span class="sxs-lookup"><span data-stu-id="4c06c-141">When an upload action is blocked because an item matches a DLP policy, DLP will either generate a warning or block the upload of the sensitive item.</span></span>

<span data-ttu-id="4c06c-142">Si el modo de lista está configurado en **Permitir**, los usuarios podrán cargar elementos confidenciales **_solo_** a dichos dominios y no se permitirá el acceso de carga a los demás dominios.</span><span class="sxs-lookup"><span data-stu-id="4c06c-142">If the list mode is set to **Allow**, then users will be able to upload sensitive items **_only_** to those domains, and upload access to all other domains is not allowed.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4c06c-143">Cuando el modo de restricción del servicio esté establecido en "Permitir", debe tener al menos un dominio de servicio configurado antes de que las restricciones se apliquen.</span><span class="sxs-lookup"><span data-stu-id="4c06c-143">When the service restriction mode is set to "Allow", you must have at least one service domain configured before restrictions are enforced.</span></span>

#### <a name="unallowed-browsers"></a><span data-ttu-id="4c06c-144">Exploradores no permitidos</span><span class="sxs-lookup"><span data-stu-id="4c06c-144">Unallowed browsers</span></span>

<span data-ttu-id="4c06c-145">Agregue exploradores, identificados por sus nombres ejecutables, que no tendrán acceso a los archivos que cumplan las condiciones de una directiva DLP aplicada cuya restricción de carga a servicios en la nube esté configurada para bloquearse o bloquear una invalidación.</span><span class="sxs-lookup"><span data-stu-id="4c06c-145">You add browsers, identified by their executable names, that will be blocked from accessing files that match the conditions of an enforced a DLP policy where the upload to cloud services restriction is set to block or block override.</span></span> <span data-ttu-id="4c06c-146">Cuando estos exploradores no puedan acceder a un archivo, los usuarios finales verán una notificación del sistema que les pedirá que abran el archivo a través de Edge Chromium.</span><span class="sxs-lookup"><span data-stu-id="4c06c-146">When these browsers are blocked from accessing a file, the end users will see a toast notification asking them to open the file through Edge Chromium.</span></span>

### <a name="business-justification-in-policy-tips"></a><span data-ttu-id="4c06c-147">Justificaciones empresariales en sugerencias de directivas</span><span class="sxs-lookup"><span data-stu-id="4c06c-147">Business justification in policy tips</span></span>

<span data-ttu-id="4c06c-148">Puede controlar cómo interactúan los usuarios con la opción de justificación empresarial en las notificaciones de sugerencias de directiva DLP.</span><span class="sxs-lookup"><span data-stu-id="4c06c-148">You can control how users interact with the business justification option in DLP policy tip notifications.</span></span> <span data-ttu-id="4c06c-149">Esta opción aparece cuando los usuarios realizan una actividad que está protegida por la configuración **Bloquear con anulación** en una directiva DLP.</span><span class="sxs-lookup"><span data-stu-id="4c06c-149">This option appears when users perform an activity that's protected by the **Block with override** setting in a DLP policy.</span></span> <span data-ttu-id="4c06c-150">Puede elegir entre una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="4c06c-150">You can choose from one the following options:</span></span>

- <span data-ttu-id="4c06c-151">De forma predeterminada, los usuarios pueden seleccionar una justificación integrada o introducir su propio texto.</span><span class="sxs-lookup"><span data-stu-id="4c06c-151">By default, users can select either a built-in justification, or enter their own text.</span></span>
- <span data-ttu-id="4c06c-152">Los usuarios solo pueden seleccionar una justificación integrada.</span><span class="sxs-lookup"><span data-stu-id="4c06c-152">Users can only select a built-in justification.</span></span>
- <span data-ttu-id="4c06c-153">Los usuarios solo pueden introducir su propia justificación.</span><span class="sxs-lookup"><span data-stu-id="4c06c-153">Users can only enter their own justification.</span></span>


## <a name="tying-dlp-settings-together"></a><span data-ttu-id="4c06c-154">Vincular las opciones de configuración DLP</span><span class="sxs-lookup"><span data-stu-id="4c06c-154">Tying DLP settings together</span></span>

<span data-ttu-id="4c06c-155">Con la DLP de los puntos de conexión y el Explorador web Edge Chromium, puede restringir el uso compartido no intencionado de elementos confidenciales a las aplicaciones y servicios en la nube no permitidos.</span><span class="sxs-lookup"><span data-stu-id="4c06c-155">With Endpoint DLP and Edge Chromium Web browser, you can restrict unintentional sharing of sensitive items to unallowed cloud apps and services.</span></span> <span data-ttu-id="4c06c-156">Edge Chromium comprende cuándo un elemento está restringido por una directiva DLP de los puntos de conexión y aplica las restricciones de acceso.</span><span class="sxs-lookup"><span data-stu-id="4c06c-156">Edge Chromium understands when an item is restricted by an Endpoint DLP policy and enforces access restrictions.</span></span>

<span data-ttu-id="4c06c-157">Cuando usa la DLP de los puntos de conexión como una ubicación en una directiva DLP configurada correctamente y en el explorador Edge Chromium, los exploradores no permitidos que haya definido en esta configuración no tendrán acceso a los elementos confidenciales que coincidan con los controles de la directiva DLP.</span><span class="sxs-lookup"><span data-stu-id="4c06c-157">When you use Endpoint DLP as a location in a properly configured DLP policy and the Edge Chromium browser, the unallowed browsers that you've defined in these settings will be prevented from accessing the sensitive items that match your DLP policy controls.</span></span> <span data-ttu-id="4c06c-158">En su lugar, los usuarios serán redirigidos para usar Edge Chromium y Edge Chromium, con su reconocimiento de las restricciones impuestas por DLP, podrá bloquear o restringir actividades cuando se cumplan las condiciones de la directiva DLP.</span><span class="sxs-lookup"><span data-stu-id="4c06c-158">Instead, users will be redirected to use Edge Chromium and Edge Chromium, with its understanding of DLP imposed restrictions, can block or restrict activities when the conditions in the DLP policy are met.</span></span>

<span data-ttu-id="4c06c-159">Para usar esta restricción, tendrá que configurar tres partes importantes:</span><span class="sxs-lookup"><span data-stu-id="4c06c-159">To use this restriction you’ll need to configure three important pieces:</span></span>

1. <span data-ttu-id="4c06c-160">Especifique los sitios (servicios, dominios y direcciones IP) con los que no quiere que se compartan elementos confidenciales.</span><span class="sxs-lookup"><span data-stu-id="4c06c-160">Specify the places – services, domains, IP addresses – that you want to prevent sensitive items from being shared to.</span></span>

2. <span data-ttu-id="4c06c-161">Agregue los exploradores que no tienen permitido acceder a ciertos elementos confidenciales cuando se produzca una coincidencia de directiva DLP.</span><span class="sxs-lookup"><span data-stu-id="4c06c-161">Add the browsers that aren’t allowed to access certain sensitive items when a DLP policy match occurs.</span></span>

3. <span data-ttu-id="4c06c-162">Configure directivas DLP para definir los tipos de elementos confidenciales que deberían tener carga restringida a estos lugares activando **Cargar a los servicios en la nube** y **Acceso desde un explorador no permitido**.</span><span class="sxs-lookup"><span data-stu-id="4c06c-162">Configure DLP policies to define the kinds of sensitive items for which upload should be restricted to these places by turning on **Upload to cloud services** and **Access from unallowed browser**.</span></span>

<span data-ttu-id="4c06c-163">Puede continuar agregando nuevos servicios, aplicaciones y directivas para ampliar y aumentar las restricciones para satisfacer las necesidades de su empresa y proteger los datos confidenciales.</span><span class="sxs-lookup"><span data-stu-id="4c06c-163">You can continue to add new services, apps, and policies to extend and augment your restrictions to meet your business needs and protect sensitive data.</span></span> 

<span data-ttu-id="4c06c-164">Esta configuración garantizará que sus datos estén seguros, evitando así las restricciones innecesarias que impiden o restringen a los usuarios el acceso y el uso compartido de elementos no confidenciales.</span><span class="sxs-lookup"><span data-stu-id="4c06c-164">This configuration will help ensure your data remains safe while also avoiding unnecessary restrictions that prevent or restrict users from accessing and sharing non-sensitive items.</span></span>

## <a name="endpoint-dlp-policy-scenarios"></a><span data-ttu-id="4c06c-165">Escenarios de directiva DLP de los puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="4c06c-165">Endpoint DLP policy scenarios</span></span>

<span data-ttu-id="4c06c-166">Para ayudarle a familiarizarse con las características de DLP de los puntos de conexión y cómo se muestran en las directivas DLP, hemos recopilado algunos escenarios para que los siga.</span><span class="sxs-lookup"><span data-stu-id="4c06c-166">To help familiarize you with Endpoint DLP features and how they surface in DLP policies, we've put together some scenarios for you to follow.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4c06c-167">Estos escenarios DLP de los puntos de conexión no son los procedimientos oficiales para crear y optimizar directivas DLP.</span><span class="sxs-lookup"><span data-stu-id="4c06c-167">These Endpoint DLP scenarios are not the official procedures for creating and tuning DLP policies.</span></span> <span data-ttu-id="4c06c-168">Consulte los temas siguientes cuando necesite trabajar con directivas DLP en situaciones generales:</span><span class="sxs-lookup"><span data-stu-id="4c06c-168">Refer to the below topics when you need to work with DLP policies in general situations:</span></span>

>- [<span data-ttu-id="4c06c-169">Obtenga más información acerca de la prevención contra la pérdida de datos</span><span class="sxs-lookup"><span data-stu-id="4c06c-169">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
>- [<span data-ttu-id="4c06c-170">Introducción a la directiva predeterminada de DLP</span><span class="sxs-lookup"><span data-stu-id="4c06c-170">Get started with the default DLP policy</span></span>](get-started-with-the-default-dlp-policy.md)
>- [<span data-ttu-id="4c06c-171">Crear una directiva DLP a partir de una plantilla</span><span class="sxs-lookup"><span data-stu-id="4c06c-171">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)
>- [<span data-ttu-id="4c06c-172">Crear, probar y optimizar una directiva DLP</span><span class="sxs-lookup"><span data-stu-id="4c06c-172">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)

### <a name="scenario-1-create-a-policy-from-a-template-audit-only"></a><span data-ttu-id="4c06c-173">Escenario 1: crear una directiva a partir de una plantilla, solo auditoría</span><span class="sxs-lookup"><span data-stu-id="4c06c-173">Scenario 1: Create a policy from a template, audit only</span></span>

<span data-ttu-id="4c06c-174">Estos escenarios requieren que ya tenga dispositivos incorporados y que presenten informes al Explorador de actividades.</span><span class="sxs-lookup"><span data-stu-id="4c06c-174">These scenarios require that you already have devices onboarded and reporting into Activity explorer.</span></span> <span data-ttu-id="4c06c-175">Si todavía no ha incorporado sus dispositivos, consulte [Introducción a la prevención de pérdida de datos de los puntos de conexión](endpoint-dlp-getting-started.md).</span><span class="sxs-lookup"><span data-stu-id="4c06c-175">If you haven't onboarded devices yet, see [Get started with Endpoint data loss prevention](endpoint-dlp-getting-started.md).</span></span>

1. <span data-ttu-id="4c06c-176">Abra la [página de prevención de pérdida de datos](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span><span class="sxs-lookup"><span data-stu-id="4c06c-176">Open the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span></span>

2. <span data-ttu-id="4c06c-177">Elija **Crear directiva**.</span><span class="sxs-lookup"><span data-stu-id="4c06c-177">Choose **Create policy**.</span></span>

3. <span data-ttu-id="4c06c-178">Para este escenario, elija **Privacidad**, después **Datos de información de identificación personal (PII) de Estados Unidos**, y elija **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="4c06c-178">For this scenario, choose **Privacy**, then **U.S. Personally Identifiable Information (PII) Data** and choose **Next**.</span></span>

4. <span data-ttu-id="4c06c-179">Desactive el campo **Estado** para todas las ubicaciones excepto para **Dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="4c06c-179">Toggle the **Status** field to off for all locations except **Devices**.</span></span> <span data-ttu-id="4c06c-180">Elija **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="4c06c-180">Choose **Next**.</span></span>

5. <span data-ttu-id="4c06c-181">Acepte la selección predeterminada **Revisar y personalizar la configuración a partir de la plantilla** y elija **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="4c06c-181">Accept the default **Review and customize settings from the template** selection and choose **Next**.</span></span>

6. <span data-ttu-id="4c06c-182">Acepte los valores predeterminados **Acciones de protección** y elija **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="4c06c-182">Accept the default **Protection actions** values and choose **Next**.</span></span>

7. <span data-ttu-id="4c06c-183">Seleccione **Auditar o restringir actividades en dispositivos Windows** y deje las acciones configuradas en **Solo auditar**.</span><span class="sxs-lookup"><span data-stu-id="4c06c-183">Select **Audit or restrict activities on Windows devices** and leave the actions set to **Audit only**.</span></span> <span data-ttu-id="4c06c-184">Elija **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="4c06c-184">Choose **Next**.</span></span>

8. <span data-ttu-id="4c06c-185">Acepte el valor predeterminado **Me gustaría probarlo primero** y elija **Mostrar sugerencias de directiva durante el modo de prueba**.</span><span class="sxs-lookup"><span data-stu-id="4c06c-185">Accept the default **I'd like to test it out first** value and choose **Show policy tips while in test mode**.</span></span> <span data-ttu-id="4c06c-186">Elija **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="4c06c-186">Choose **Next**.</span></span>

9. <span data-ttu-id="4c06c-187">Revise la configuración y elija **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="4c06c-187">Review your settings and choose **Submit**.</span></span>

10. <span data-ttu-id="4c06c-188">La nueva directiva DLP se mostrará en la lista de directivas.</span><span class="sxs-lookup"><span data-stu-id="4c06c-188">The new DLP policy will appear in the policy list.</span></span>

11. <span data-ttu-id="4c06c-189">Compruebe que los datos de los puntos de conexión supervisados se encuentren en el Explorador de actividades.</span><span class="sxs-lookup"><span data-stu-id="4c06c-189">Check Activity explorer for data from the monitored endpoints.</span></span> <span data-ttu-id="4c06c-190">Configure el filtro por ubicación de los dispositivos, agregue la directiva y, después, filtre por nombre de directiva para ver el impacto de esta directiva.</span><span class="sxs-lookup"><span data-stu-id="4c06c-190">Set the location filter for devices and add the policy, then filter by policy name to see the impact of this policy.</span></span> <span data-ttu-id="4c06c-191">Consulte [Introducción al explorador de actividades](data-classification-activity-explorer.md), de ser necesario. </span><span class="sxs-lookup"><span data-stu-id="4c06c-191">See, [Get started with activity explorer](data-classification-activity-explorer.md) if needed.</span></span>

12. <span data-ttu-id="4c06c-192">Intente compartir una prueba que incluya contenido que activará la condición de datos de información de identificación personal (PII) de Estados Unidos con alguien ajeno a su organización.</span><span class="sxs-lookup"><span data-stu-id="4c06c-192">Attempt to share a test that contains content that will trigger the U.S. Personally Identifiable Information (PII) Data condition with someone outside your organization.</span></span> <span data-ttu-id="4c06c-193">Esto debería activar la directiva.</span><span class="sxs-lookup"><span data-stu-id="4c06c-193">This should trigger the policy.</span></span>

13. <span data-ttu-id="4c06c-194">Compruebe que el evento se encuentre en el Explorador de actividades.</span><span class="sxs-lookup"><span data-stu-id="4c06c-194">Check Activity explorer for the event.</span></span>

### <a name="scenario-2-modify-the-existing-policy-set-an-alert"></a><span data-ttu-id="4c06c-195">Escenario 2: modificar la directiva existente, configurar una alerta</span><span class="sxs-lookup"><span data-stu-id="4c06c-195">Scenario 2: Modify the existing policy, set an alert</span></span>

1. <span data-ttu-id="4c06c-196">Abra la [Página de prevención de pérdida de datos](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span><span class="sxs-lookup"><span data-stu-id="4c06c-196">Open the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span></span>

2. <span data-ttu-id="4c06c-197">Elija la directiva **Datos de información de identificación personal (PII) de Estados Unidos** que creó en el escenario 1.</span><span class="sxs-lookup"><span data-stu-id="4c06c-197">Choose the **U.S. Personally Identifiable Information (PII) Data** policy that you created in scenario 1.</span></span>

3. <span data-ttu-id="4c06c-198">Elija **editar directiva**.</span><span class="sxs-lookup"><span data-stu-id="4c06c-198">Choose **edit policy**.</span></span>

4. <span data-ttu-id="4c06c-199">Vaya a la página **Reglas de DLP avanzadas** y edite el **Bajo volumen de contenido detectado en la información de identificación personal de Estados Unidos**.</span><span class="sxs-lookup"><span data-stu-id="4c06c-199">Go to the **Advanced DLP rules** page and edit the **Low volume of content detected U.S. Personally Identifiable Inf**.</span></span>

5. <span data-ttu-id="4c06c-200">Desplácese hacia abajo hasta la sección **Informes de incidentes** y configure **Enviar una alerta a los administradores cuando se produzca una coincidencia de regla** en **Activado**.</span><span class="sxs-lookup"><span data-stu-id="4c06c-200">Scroll down to the **Incident reports** section and set **Send an alert to admins when a rule match occurs** to **On**.</span></span> <span data-ttu-id="4c06c-201">Las alertas por correo electrónico se enviarán automáticamente al administrador y a cualquier persona que agregue a la lista de destinatarios.</span><span class="sxs-lookup"><span data-stu-id="4c06c-201">Email alerts will be automatically sent to the administrator and anyone else you add to the list of recipients.</span></span> 

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="4c06c-202">![activar-informes-de-incidentes](../media/endpoint-dlp-2-using-dlp-incident-reports.png)</span><span class="sxs-lookup"><span data-stu-id="4c06c-202">![turn-on-incident-reports](../media/endpoint-dlp-2-using-dlp-incident-reports.png)</span></span>
   
6. <span data-ttu-id="4c06c-203">Para este escenario, elija **Enviar una alerta cada vez que una actividad coincida con la regla**.</span><span class="sxs-lookup"><span data-stu-id="4c06c-203">For the purposes of this scenario, choose **Send alert every time an activity matches the rule**.</span></span>

7. <span data-ttu-id="4c06c-204">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="4c06c-204">Choose **Save**.</span></span>

8. <span data-ttu-id="4c06c-205">Conserve todas las opciones de configuración anteriores eligiendo **Siguiente** y, después, **Enviar** los cambios de directiva.</span><span class="sxs-lookup"><span data-stu-id="4c06c-205">Retain all your previous settings by choosing **Next** and then **Submit** the policy changes.</span></span>

9. <span data-ttu-id="4c06c-206">Intente compartir una prueba que incluya contenido que activará la condición de datos de información de identificación personal (PII) de Estados Unidos con alguien ajeno a su organización.</span><span class="sxs-lookup"><span data-stu-id="4c06c-206">Attempt to share a test that contains content that will trigger the U.S. Personally Identifiable Information (PII) Data condition with someone outside your organization.</span></span> <span data-ttu-id="4c06c-207">Esto debería activar la directiva.</span><span class="sxs-lookup"><span data-stu-id="4c06c-207">This should trigger the policy.</span></span>

10. <span data-ttu-id="4c06c-208">Compruebe que el evento se encuentre en el Explorador de actividades.</span><span class="sxs-lookup"><span data-stu-id="4c06c-208">Check Activity explorer for the event.</span></span>

### <a name="scenario-3-modify-the-existing-policy-block-the-action-with-allow-override"></a><span data-ttu-id="4c06c-209">Caso 3: modificar la directiva existente, bloquear la acción con permitir invalidación</span><span class="sxs-lookup"><span data-stu-id="4c06c-209">Scenario 3: Modify the existing policy, block the action with allow override</span></span>

1. <span data-ttu-id="4c06c-210">Abra la [Página de prevención de pérdida de datos](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span><span class="sxs-lookup"><span data-stu-id="4c06c-210">Open the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span></span>

2. <span data-ttu-id="4c06c-211">Elija la directiva **Datos de información de identificación personal (PII) de Estados Unidos** que creó en el escenario 1.</span><span class="sxs-lookup"><span data-stu-id="4c06c-211">Choose the **U.S. Personally Identifiable Information (PII) Data** policy that you created in scenario 1.</span></span>

3. <span data-ttu-id="4c06c-212">Elija **editar directiva**.</span><span class="sxs-lookup"><span data-stu-id="4c06c-212">Choose **edit policy**.</span></span>

4. <span data-ttu-id="4c06c-213">Vaya a la página **Reglas de DLP avanzadas** y edite el **Bajo volumen de contenido detectado en la información de identificación personal de Estados Unidos**.</span><span class="sxs-lookup"><span data-stu-id="4c06c-213">Go to the **Advanced DLP rules** page and edit the **Low volume of content detected U.S. Personally Identifiable Inf**.</span></span>

5. <span data-ttu-id="4c06c-214">Desplácese hacia abajo hasta la sección **Auditar o restringir actividades en dispositivos Windows** y configure la acción correspondiente en **Bloquear con invalidación** para cada actividad.</span><span class="sxs-lookup"><span data-stu-id="4c06c-214">Scroll down to the **Audit or restrict activities on Windows device** section and for each activity set the corresponding action to  **Block with override**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="4c06c-215">![configurar bloqueo con acción de invalidación](../media/endpoint-dlp-6-using-dlp-set-blocked-with-override.png)</span><span class="sxs-lookup"><span data-stu-id="4c06c-215">![set block with override action](../media/endpoint-dlp-6-using-dlp-set-blocked-with-override.png)</span></span>
   
6. <span data-ttu-id="4c06c-216">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="4c06c-216">Choose **Save**.</span></span>

7. <span data-ttu-id="4c06c-217">Repita los pasos del 4 al 7 para el **Alto volumen de contenido detectado en la información de identificación personal de Estados Unidos**.</span><span class="sxs-lookup"><span data-stu-id="4c06c-217">Repeat steps 4-7 for the **High volume of content detected U.S. Personally Identifiable Inf**.</span></span>

8. <span data-ttu-id="4c06c-218">Conserve todas las opciones de configuración anteriores eligiendo **Siguiente** y, después, **Enviar** los cambios de directiva.</span><span class="sxs-lookup"><span data-stu-id="4c06c-218">Retain all your previous settings by choosing **Next** and then **Submit** the policy changes.</span></span>

9. <span data-ttu-id="4c06c-219">Intente compartir una prueba que incluya contenido que activará la condición de datos de información de identificación personal (PII) de Estados Unidos con alguien ajeno a su organización.</span><span class="sxs-lookup"><span data-stu-id="4c06c-219">Attempt to share a test that contains content that will trigger the U.S. Personally Identifiable Information (PII) Data condition with someone outside your organization.</span></span> <span data-ttu-id="4c06c-220">Esto debería activar la directiva.</span><span class="sxs-lookup"><span data-stu-id="4c06c-220">This should trigger the policy.</span></span>

   <span data-ttu-id="4c06c-221">Verá un elemento emergente como el siguiente en el dispositivo cliente:</span><span class="sxs-lookup"><span data-stu-id="4c06c-221">You'll see a popup like this on the client device:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="4c06c-222">![notificación de invalidación de cliente bloqueado por dlp en punto de conexión](../media/endpoint-dlp-3-using-dlp-client-blocked-override-notification.png)</span><span class="sxs-lookup"><span data-stu-id="4c06c-222">![endpoint dlp client blocked override notification](../media/endpoint-dlp-3-using-dlp-client-blocked-override-notification.png)</span></span>

10. <span data-ttu-id="4c06c-223">Compruebe que el evento se encuentre en el Explorador de actividades.</span><span class="sxs-lookup"><span data-stu-id="4c06c-223">Check Activity explorer for the event.</span></span>

## <a name="see-also"></a><span data-ttu-id="4c06c-224">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4c06c-224">See also</span></span>

- [<span data-ttu-id="4c06c-225">Obtenga más información sobre la prevención de pérdida de datos en punto de conexión</span><span class="sxs-lookup"><span data-stu-id="4c06c-225">Learn about Endpoint data loss prevention</span></span>](endpoint-dlp-learn-about.md)
- [<span data-ttu-id="4c06c-226">Introducción a la prevención de pérdida de datos en punto de conexión</span><span class="sxs-lookup"><span data-stu-id="4c06c-226">Get started with Endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
- [<span data-ttu-id="4c06c-227">Obtenga más información acerca de la prevención contra la pérdida de datos</span><span class="sxs-lookup"><span data-stu-id="4c06c-227">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="4c06c-228">Crear, probar y optimizar una directiva DLP</span><span class="sxs-lookup"><span data-stu-id="4c06c-228">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="4c06c-229">Introducción al explorador de actividad</span><span class="sxs-lookup"><span data-stu-id="4c06c-229">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="4c06c-230">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="4c06c-230">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/)
- <span data-ttu-id="4c06c-231">[Herramientas y métodos de incorporación para equipos con Windows 10](/microsoft-365/compliance/dlp-configure-endpoints).</span><span class="sxs-lookup"><span data-stu-id="4c06c-231">[Onboarding tools and methods for Windows 10 machines](/microsoft-365/compliance/dlp-configure-endpoints)</span></span>
- [<span data-ttu-id="4c06c-232">Suscripción a Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4c06c-232">Microsoft 365 subscription</span></span>](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [<span data-ttu-id="4c06c-233">Unido a Azure Active Directory (AAD)</span><span class="sxs-lookup"><span data-stu-id="4c06c-233">Azure Active Directory (AAD) joined</span></span>](/azure/active-directory/devices/concept-azure-ad-join)
- [<span data-ttu-id="4c06c-234">Descargue el nuevo Microsoft Edge basado en Chromium</span><span class="sxs-lookup"><span data-stu-id="4c06c-234">Download the new Microsoft Edge based on Chromium</span></span>](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)
- [<span data-ttu-id="4c06c-235">Introducción a la directiva predeterminada de DLP</span><span class="sxs-lookup"><span data-stu-id="4c06c-235">Get started with the default DLP policy</span></span>](get-started-with-the-default-dlp-policy.md)
- [<span data-ttu-id="4c06c-236">Crear una directiva DLP desde una plantilla</span><span class="sxs-lookup"><span data-stu-id="4c06c-236">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)
