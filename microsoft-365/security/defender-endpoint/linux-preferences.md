---
title: Establecer preferencias para ATP de Microsoft Defender para Linux
ms.reviewer: ''
description: Describe cómo configurar ATP de Microsoft Defender para Linux en empresas.
keywords: microsoft, defender, atp, linux, installation, deploy, uninstallation, puppet, ansible, linux, redhat, ubuntu, debian, sles, suse, centos
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 6ca6b3dd41b867145bfc4af331fb742be469d2a9
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "51688398"
---
# <a name="set-preferences-for-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="10ed3-104">Establecer preferencias para Microsoft Defender para endpoint en Linux</span><span class="sxs-lookup"><span data-stu-id="10ed3-104">Set preferences for Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="10ed3-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="10ed3-105">**Applies to:**</span></span>
- [<span data-ttu-id="10ed3-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="10ed3-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="10ed3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="10ed3-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="10ed3-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="10ed3-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="10ed3-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="10ed3-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

>[!IMPORTANT]
><span data-ttu-id="10ed3-110">Este tema contiene instrucciones sobre cómo establecer las preferencias de Defender para Endpoint para Linux en entornos empresariales.</span><span class="sxs-lookup"><span data-stu-id="10ed3-110">This topic contains instructions for how to set preferences for Defender for Endpoint for Linux in enterprise environments.</span></span> <span data-ttu-id="10ed3-111">Si estás interesado en configurar el producto en un dispositivo desde la línea de comandos, consulta [Recursos](linux-resources.md#configure-from-the-command-line).</span><span class="sxs-lookup"><span data-stu-id="10ed3-111">If you are interested in configuring the product on a device from the command-line, see [Resources](linux-resources.md#configure-from-the-command-line).</span></span>

<span data-ttu-id="10ed3-112">En entornos empresariales, Defender para Endpoint para Linux se puede administrar a través de un perfil de configuración.</span><span class="sxs-lookup"><span data-stu-id="10ed3-112">In enterprise environments, Defender for Endpoint for Linux can be managed through a configuration profile.</span></span> <span data-ttu-id="10ed3-113">Este perfil se implementa desde la herramienta de administración que prefiera.</span><span class="sxs-lookup"><span data-stu-id="10ed3-113">This profile is deployed from the management tool of your choice.</span></span> <span data-ttu-id="10ed3-114">Las preferencias administradas por la empresa tienen prioridad sobre las establecidas localmente en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="10ed3-114">Preferences managed by the enterprise take precedence over the ones set locally on the device.</span></span> <span data-ttu-id="10ed3-115">En otras palabras, los usuarios de su empresa no pueden cambiar las preferencias que se establecen a través de este perfil de configuración.</span><span class="sxs-lookup"><span data-stu-id="10ed3-115">In other words, users in your enterprise are not able to change preferences that are set through this configuration profile.</span></span>

<span data-ttu-id="10ed3-116">En este artículo se describe la estructura de este perfil (incluido un perfil recomendado que puede usar para empezar) e instrucciones sobre cómo implementar el perfil.</span><span class="sxs-lookup"><span data-stu-id="10ed3-116">This article describes the structure of this profile (including a recommended profile that you can use to get started) and instructions on how to deploy the profile.</span></span>

## <a name="configuration-profile-structure"></a><span data-ttu-id="10ed3-117">Estructura de perfiles de configuración</span><span class="sxs-lookup"><span data-stu-id="10ed3-117">Configuration profile structure</span></span>

<span data-ttu-id="10ed3-118">El perfil de configuración es un archivo .json que consta de entradas identificadas por una clave (que indica el nombre de la preferencia), seguido de un valor, que depende de la naturaleza de la preferencia.</span><span class="sxs-lookup"><span data-stu-id="10ed3-118">The configuration profile is a .json file that consists of entries identified by a key (which denotes the name of the preference), followed by a value, which depends on the nature of the preference.</span></span> <span data-ttu-id="10ed3-119">Los valores pueden ser simples, como un valor numérico o complejos, como una lista anidada de preferencias.</span><span class="sxs-lookup"><span data-stu-id="10ed3-119">Values can be simple, such as a numerical value, or complex, such as a nested list of preferences.</span></span>

<span data-ttu-id="10ed3-120">Normalmente, se usa una herramienta de administración de configuración para insertar un archivo con el nombre ```mdatp_managed.json``` en la ubicación ```/etc/opt/microsoft/mdatp/managed/``` .</span><span class="sxs-lookup"><span data-stu-id="10ed3-120">Typically, you would use a configuration management tool to push a file with the name ```mdatp_managed.json``` at the location ```/etc/opt/microsoft/mdatp/managed/```.</span></span>

<span data-ttu-id="10ed3-121">El nivel superior del perfil de configuración incluye las preferencias de todo el producto y las entradas para las subáreas del producto, que se explican con más detalle en las secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="10ed3-121">The top level of the configuration profile includes product-wide preferences and entries for subareas of the product, which are explained in more detail in the next sections.</span></span>

### <a name="antivirus-engine-preferences"></a><span data-ttu-id="10ed3-122">Preferencias del motor antivirus</span><span class="sxs-lookup"><span data-stu-id="10ed3-122">Antivirus engine preferences</span></span>

<span data-ttu-id="10ed3-123">La *sección antivirusEngine* del perfil de configuración se usa para administrar las preferencias del componente antivirus del producto.</span><span class="sxs-lookup"><span data-stu-id="10ed3-123">The *antivirusEngine* section of the configuration profile is used to manage the preferences of the antivirus component of the product.</span></span>

|||
|:---|:---|
| <span data-ttu-id="10ed3-124">**Key**</span><span class="sxs-lookup"><span data-stu-id="10ed3-124">**Key**</span></span> | <span data-ttu-id="10ed3-125">antivirusEngine</span><span class="sxs-lookup"><span data-stu-id="10ed3-125">antivirusEngine</span></span> |
| <span data-ttu-id="10ed3-126">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="10ed3-126">**Data type**</span></span> | <span data-ttu-id="10ed3-127">Diccionario (preferencia anidada)</span><span class="sxs-lookup"><span data-stu-id="10ed3-127">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="10ed3-128">**Comments**</span><span class="sxs-lookup"><span data-stu-id="10ed3-128">**Comments**</span></span> | <span data-ttu-id="10ed3-129">Vea las secciones siguientes para obtener una descripción del contenido del diccionario.</span><span class="sxs-lookup"><span data-stu-id="10ed3-129">See the following sections for a description of the dictionary contents.</span></span> |
|||

#### <a name="enable--disable-real-time-protection"></a><span data-ttu-id="10ed3-130">Habilitar o deshabilitar la protección en tiempo real</span><span class="sxs-lookup"><span data-stu-id="10ed3-130">Enable / disable real-time protection</span></span>

<span data-ttu-id="10ed3-131">Determina si la protección en tiempo real (examinar archivos a medida que se accede a ellos) está habilitada o no.</span><span class="sxs-lookup"><span data-stu-id="10ed3-131">Determines whether real-time protection (scan files as they are accessed) is enabled or not.</span></span>

|||
|:---|:---|
| <span data-ttu-id="10ed3-132">**Key**</span><span class="sxs-lookup"><span data-stu-id="10ed3-132">**Key**</span></span> | <span data-ttu-id="10ed3-133">enableRealTimeProtection</span><span class="sxs-lookup"><span data-stu-id="10ed3-133">enableRealTimeProtection</span></span> |
| <span data-ttu-id="10ed3-134">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="10ed3-134">**Data type**</span></span> | <span data-ttu-id="10ed3-135">Booleano</span><span class="sxs-lookup"><span data-stu-id="10ed3-135">Boolean</span></span> |
| <span data-ttu-id="10ed3-136">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="10ed3-136">**Possible values**</span></span> | <span data-ttu-id="10ed3-137">true (valor predeterminado)</span><span class="sxs-lookup"><span data-stu-id="10ed3-137">true (default)</span></span> <br/> <span data-ttu-id="10ed3-138">false</span><span class="sxs-lookup"><span data-stu-id="10ed3-138">false</span></span> |
|||

#### <a name="enable--disable-passive-mode"></a><span data-ttu-id="10ed3-139">Habilitar o deshabilitar el modo pasivo</span><span class="sxs-lookup"><span data-stu-id="10ed3-139">Enable / disable passive mode</span></span>

<span data-ttu-id="10ed3-140">Determina si el motor antivirus se ejecuta en modo pasivo o no.</span><span class="sxs-lookup"><span data-stu-id="10ed3-140">Determines whether the antivirus engine runs in passive mode or not.</span></span> <span data-ttu-id="10ed3-141">En modo pasivo:</span><span class="sxs-lookup"><span data-stu-id="10ed3-141">In passive mode:</span></span>
- <span data-ttu-id="10ed3-142">La protección en tiempo real está desactivada.</span><span class="sxs-lookup"><span data-stu-id="10ed3-142">Real-time protection is turned off.</span></span>
- <span data-ttu-id="10ed3-143">El examen a petición está activado.</span><span class="sxs-lookup"><span data-stu-id="10ed3-143">On-demand scanning is turned on.</span></span>
- <span data-ttu-id="10ed3-144">La corrección automática de amenazas está desactivada.</span><span class="sxs-lookup"><span data-stu-id="10ed3-144">Automatic threat remediation is turned off.</span></span>
- <span data-ttu-id="10ed3-145">Las actualizaciones de inteligencia de seguridad están activadas.</span><span class="sxs-lookup"><span data-stu-id="10ed3-145">Security intelligence updates are turned on.</span></span>
- <span data-ttu-id="10ed3-146">El icono del menú Estado está oculto.</span><span class="sxs-lookup"><span data-stu-id="10ed3-146">Status menu icon is hidden.</span></span>

|||
|:---|:---|
| <span data-ttu-id="10ed3-147">**Key**</span><span class="sxs-lookup"><span data-stu-id="10ed3-147">**Key**</span></span> | <span data-ttu-id="10ed3-148">passiveMode</span><span class="sxs-lookup"><span data-stu-id="10ed3-148">passiveMode</span></span> |
| <span data-ttu-id="10ed3-149">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="10ed3-149">**Data type**</span></span> | <span data-ttu-id="10ed3-150">Booleano</span><span class="sxs-lookup"><span data-stu-id="10ed3-150">Boolean</span></span> |
| <span data-ttu-id="10ed3-151">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="10ed3-151">**Possible values**</span></span> | <span data-ttu-id="10ed3-152">false (predeterminado)</span><span class="sxs-lookup"><span data-stu-id="10ed3-152">false (default)</span></span> <br/> <span data-ttu-id="10ed3-153">true</span><span class="sxs-lookup"><span data-stu-id="10ed3-153">true</span></span> |
| <span data-ttu-id="10ed3-154">**Comments**</span><span class="sxs-lookup"><span data-stu-id="10ed3-154">**Comments**</span></span> | <span data-ttu-id="10ed3-155">Disponible en Defender para endpoint versión 100.67.60 o posterior.</span><span class="sxs-lookup"><span data-stu-id="10ed3-155">Available in Defender for Endpoint version 100.67.60 or higher.</span></span> |
|||

#### <a name="exclusion-merge-policy"></a><span data-ttu-id="10ed3-156">Directiva de combinación de exclusión</span><span class="sxs-lookup"><span data-stu-id="10ed3-156">Exclusion merge policy</span></span>

<span data-ttu-id="10ed3-157">Especifica la directiva de combinación para exclusiones.</span><span class="sxs-lookup"><span data-stu-id="10ed3-157">Specifies the merge policy for exclusions.</span></span> <span data-ttu-id="10ed3-158">Puede ser una combinación de exclusiones definidas por el administrador y definidas por el usuario ( ) o solo `merge` exclusiones definidas por el administrador ( `admin_only` ).</span><span class="sxs-lookup"><span data-stu-id="10ed3-158">It can be a combination of administrator-defined and user-defined exclusions (`merge`) or only administrator-defined exclusions (`admin_only`).</span></span> <span data-ttu-id="10ed3-159">Esta configuración se puede usar para restringir que los usuarios locales definan sus propias exclusiones.</span><span class="sxs-lookup"><span data-stu-id="10ed3-159">This setting can be used to restrict local users from defining their own exclusions.</span></span>

|||
|:---|:---|
| <span data-ttu-id="10ed3-160">**Key**</span><span class="sxs-lookup"><span data-stu-id="10ed3-160">**Key**</span></span> | <span data-ttu-id="10ed3-161">exclusionsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="10ed3-161">exclusionsMergePolicy</span></span> |
| <span data-ttu-id="10ed3-162">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="10ed3-162">**Data type**</span></span> | <span data-ttu-id="10ed3-163">Cadena</span><span class="sxs-lookup"><span data-stu-id="10ed3-163">String</span></span> |
| <span data-ttu-id="10ed3-164">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="10ed3-164">**Possible values**</span></span> | <span data-ttu-id="10ed3-165">merge (valor predeterminado)</span><span class="sxs-lookup"><span data-stu-id="10ed3-165">merge (default)</span></span> <br/> <span data-ttu-id="10ed3-166">admin_only</span><span class="sxs-lookup"><span data-stu-id="10ed3-166">admin_only</span></span> |
| <span data-ttu-id="10ed3-167">**Comments**</span><span class="sxs-lookup"><span data-stu-id="10ed3-167">**Comments**</span></span> | <span data-ttu-id="10ed3-168">Disponible en Defender para endpoint versión 100.83.73 o posterior.</span><span class="sxs-lookup"><span data-stu-id="10ed3-168">Available in Defender for Endpoint version 100.83.73 or higher.</span></span> |
|||

#### <a name="scan-exclusions"></a><span data-ttu-id="10ed3-169">Exclusiones de examen</span><span class="sxs-lookup"><span data-stu-id="10ed3-169">Scan exclusions</span></span>

<span data-ttu-id="10ed3-170">Entidades que se han excluido del examen.</span><span class="sxs-lookup"><span data-stu-id="10ed3-170">Entities that have been excluded from the scan.</span></span> <span data-ttu-id="10ed3-171">Las exclusiones se pueden especificar por rutas de acceso completas, extensiones o nombres de archivo.</span><span class="sxs-lookup"><span data-stu-id="10ed3-171">Exclusions can be specified by full paths, extensions, or file names.</span></span>

|||
|:---|:---|
| <span data-ttu-id="10ed3-172">**Key**</span><span class="sxs-lookup"><span data-stu-id="10ed3-172">**Key**</span></span> | <span data-ttu-id="10ed3-173">exclusiones</span><span class="sxs-lookup"><span data-stu-id="10ed3-173">exclusions</span></span> |
| <span data-ttu-id="10ed3-174">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="10ed3-174">**Data type**</span></span> | <span data-ttu-id="10ed3-175">Diccionario (preferencia anidada)</span><span class="sxs-lookup"><span data-stu-id="10ed3-175">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="10ed3-176">**Comments**</span><span class="sxs-lookup"><span data-stu-id="10ed3-176">**Comments**</span></span> | <span data-ttu-id="10ed3-177">Vea las secciones siguientes para obtener una descripción del contenido del diccionario.</span><span class="sxs-lookup"><span data-stu-id="10ed3-177">See the following sections for a description of the dictionary contents.</span></span> |
|||

<span data-ttu-id="10ed3-178">**Tipo de exclusión**</span><span class="sxs-lookup"><span data-stu-id="10ed3-178">**Type of exclusion**</span></span>

<span data-ttu-id="10ed3-179">Especifica el tipo de contenido excluido del examen.</span><span class="sxs-lookup"><span data-stu-id="10ed3-179">Specifies the type of content excluded from the scan.</span></span>

|||
|:---|:---|
| <span data-ttu-id="10ed3-180">**Key**</span><span class="sxs-lookup"><span data-stu-id="10ed3-180">**Key**</span></span> | <span data-ttu-id="10ed3-181">$type</span><span class="sxs-lookup"><span data-stu-id="10ed3-181">$type</span></span> |
| <span data-ttu-id="10ed3-182">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="10ed3-182">**Data type**</span></span> | <span data-ttu-id="10ed3-183">Cadena</span><span class="sxs-lookup"><span data-stu-id="10ed3-183">String</span></span> |
| <span data-ttu-id="10ed3-184">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="10ed3-184">**Possible values**</span></span> | <span data-ttu-id="10ed3-185">excludedPath</span><span class="sxs-lookup"><span data-stu-id="10ed3-185">excludedPath</span></span> <br/> <span data-ttu-id="10ed3-186">excludedFileExtension</span><span class="sxs-lookup"><span data-stu-id="10ed3-186">excludedFileExtension</span></span> <br/> <span data-ttu-id="10ed3-187">excludedFileName</span><span class="sxs-lookup"><span data-stu-id="10ed3-187">excludedFileName</span></span> |
|||

<span data-ttu-id="10ed3-188">**Ruta de acceso al contenido excluido**</span><span class="sxs-lookup"><span data-stu-id="10ed3-188">**Path to excluded content**</span></span>

<span data-ttu-id="10ed3-189">Se usa para excluir contenido del examen por ruta de acceso de archivo completa.</span><span class="sxs-lookup"><span data-stu-id="10ed3-189">Used to exclude content from the scan by full file path.</span></span>

|||
|:---|:---|
| <span data-ttu-id="10ed3-190">**Key**</span><span class="sxs-lookup"><span data-stu-id="10ed3-190">**Key**</span></span> | <span data-ttu-id="10ed3-191">path</span><span class="sxs-lookup"><span data-stu-id="10ed3-191">path</span></span> |
| <span data-ttu-id="10ed3-192">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="10ed3-192">**Data type**</span></span> | <span data-ttu-id="10ed3-193">Cadena</span><span class="sxs-lookup"><span data-stu-id="10ed3-193">String</span></span> |
| <span data-ttu-id="10ed3-194">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="10ed3-194">**Possible values**</span></span> | <span data-ttu-id="10ed3-195">rutas de acceso válidas</span><span class="sxs-lookup"><span data-stu-id="10ed3-195">valid paths</span></span> |
| <span data-ttu-id="10ed3-196">**Comments**</span><span class="sxs-lookup"><span data-stu-id="10ed3-196">**Comments**</span></span> | <span data-ttu-id="10ed3-197">Aplicable solo *si $type* *se excluyePath*</span><span class="sxs-lookup"><span data-stu-id="10ed3-197">Applicable only if *$type* is *excludedPath*</span></span> |
|||

<span data-ttu-id="10ed3-198">**Tipo de ruta de acceso (archivo/directorio)**</span><span class="sxs-lookup"><span data-stu-id="10ed3-198">**Path type (file / directory)**</span></span>

<span data-ttu-id="10ed3-199">Indica si la *propiedad path* hace referencia a un archivo o directorio.</span><span class="sxs-lookup"><span data-stu-id="10ed3-199">Indicates if the *path* property refers to a file or directory.</span></span> 

|||
|:---|:---|
| <span data-ttu-id="10ed3-200">**Key**</span><span class="sxs-lookup"><span data-stu-id="10ed3-200">**Key**</span></span> | <span data-ttu-id="10ed3-201">isDirectory</span><span class="sxs-lookup"><span data-stu-id="10ed3-201">isDirectory</span></span> |
| <span data-ttu-id="10ed3-202">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="10ed3-202">**Data type**</span></span> | <span data-ttu-id="10ed3-203">Booleano</span><span class="sxs-lookup"><span data-stu-id="10ed3-203">Boolean</span></span> |
| <span data-ttu-id="10ed3-204">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="10ed3-204">**Possible values**</span></span> | <span data-ttu-id="10ed3-205">false (predeterminado)</span><span class="sxs-lookup"><span data-stu-id="10ed3-205">false (default)</span></span> <br/> <span data-ttu-id="10ed3-206">true</span><span class="sxs-lookup"><span data-stu-id="10ed3-206">true</span></span> |
| <span data-ttu-id="10ed3-207">**Comments**</span><span class="sxs-lookup"><span data-stu-id="10ed3-207">**Comments**</span></span> | <span data-ttu-id="10ed3-208">Aplicable solo *si $type* *se excluyePath*</span><span class="sxs-lookup"><span data-stu-id="10ed3-208">Applicable only if *$type* is *excludedPath*</span></span> |
|||

<span data-ttu-id="10ed3-209">**Extensión de archivo excluida del examen**</span><span class="sxs-lookup"><span data-stu-id="10ed3-209">**File extension excluded from the scan**</span></span>

<span data-ttu-id="10ed3-210">Se usa para excluir contenido del examen por extensión de archivo.</span><span class="sxs-lookup"><span data-stu-id="10ed3-210">Used to exclude content from the scan by file extension.</span></span>

|||
|:---|:---|
| <span data-ttu-id="10ed3-211">**Key**</span><span class="sxs-lookup"><span data-stu-id="10ed3-211">**Key**</span></span> | <span data-ttu-id="10ed3-212">extensión</span><span class="sxs-lookup"><span data-stu-id="10ed3-212">extension</span></span> |
| <span data-ttu-id="10ed3-213">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="10ed3-213">**Data type**</span></span> | <span data-ttu-id="10ed3-214">Cadena</span><span class="sxs-lookup"><span data-stu-id="10ed3-214">String</span></span> |
| <span data-ttu-id="10ed3-215">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="10ed3-215">**Possible values**</span></span> | <span data-ttu-id="10ed3-216">extensiones de archivo válidas</span><span class="sxs-lookup"><span data-stu-id="10ed3-216">valid file extensions</span></span> |
| <span data-ttu-id="10ed3-217">**Comments**</span><span class="sxs-lookup"><span data-stu-id="10ed3-217">**Comments**</span></span> | <span data-ttu-id="10ed3-218">Aplicable solo *si $type* *se excluyeFileExtension*</span><span class="sxs-lookup"><span data-stu-id="10ed3-218">Applicable only if *$type* is *excludedFileExtension*</span></span> |
|||

<span data-ttu-id="10ed3-219">**Proceso excluido del examen**</span><span class="sxs-lookup"><span data-stu-id="10ed3-219">**Process excluded from the scan**</span></span>

<span data-ttu-id="10ed3-220">Especifica un proceso para el que se excluye toda la actividad de archivo del examen.</span><span class="sxs-lookup"><span data-stu-id="10ed3-220">Specifies a process for which all file activity is excluded from scanning.</span></span> <span data-ttu-id="10ed3-221">El proceso se puede especificar por su nombre (por ejemplo, ) o la ruta de acceso `cat` completa (por ejemplo, `/bin/cat` ).</span><span class="sxs-lookup"><span data-stu-id="10ed3-221">The process can be specified either by its name (for example, `cat`) or full path (for example, `/bin/cat`).</span></span>

|||
|:---|:---|
| <span data-ttu-id="10ed3-222">**Key**</span><span class="sxs-lookup"><span data-stu-id="10ed3-222">**Key**</span></span> | <span data-ttu-id="10ed3-223">name</span><span class="sxs-lookup"><span data-stu-id="10ed3-223">name</span></span> |
| <span data-ttu-id="10ed3-224">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="10ed3-224">**Data type**</span></span> | <span data-ttu-id="10ed3-225">Cadena</span><span class="sxs-lookup"><span data-stu-id="10ed3-225">String</span></span> |
| <span data-ttu-id="10ed3-226">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="10ed3-226">**Possible values**</span></span> | <span data-ttu-id="10ed3-227">cualquier cadena</span><span class="sxs-lookup"><span data-stu-id="10ed3-227">any string</span></span> |
| <span data-ttu-id="10ed3-228">**Comments**</span><span class="sxs-lookup"><span data-stu-id="10ed3-228">**Comments**</span></span> | <span data-ttu-id="10ed3-229">Aplicable solo *si $type* *se excluyeFileName*</span><span class="sxs-lookup"><span data-stu-id="10ed3-229">Applicable only if *$type* is *excludedFileName*</span></span> |
|||

#### <a name="allowed-threats"></a><span data-ttu-id="10ed3-230">Amenazas permitidas</span><span class="sxs-lookup"><span data-stu-id="10ed3-230">Allowed threats</span></span>

<span data-ttu-id="10ed3-231">Lista de amenazas (identificadas por su nombre) que no están bloqueadas por el producto y que en su lugar pueden ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="10ed3-231">List of threats (identified by their name) that are not blocked by the product and are instead allowed to run.</span></span>

|||
|:---|:---|
| <span data-ttu-id="10ed3-232">**Key**</span><span class="sxs-lookup"><span data-stu-id="10ed3-232">**Key**</span></span> | <span data-ttu-id="10ed3-233">allowedThreats</span><span class="sxs-lookup"><span data-stu-id="10ed3-233">allowedThreats</span></span> |
| <span data-ttu-id="10ed3-234">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="10ed3-234">**Data type**</span></span> | <span data-ttu-id="10ed3-235">Matriz de cadenas</span><span class="sxs-lookup"><span data-stu-id="10ed3-235">Array of strings</span></span> |
|||

#### <a name="disallowed-threat-actions"></a><span data-ttu-id="10ed3-236">Acciones de amenazas no permitidos</span><span class="sxs-lookup"><span data-stu-id="10ed3-236">Disallowed threat actions</span></span>

<span data-ttu-id="10ed3-237">Restringe las acciones que el usuario local de un dispositivo puede realizar cuando se detectan amenazas.</span><span class="sxs-lookup"><span data-stu-id="10ed3-237">Restricts the actions that the local user of a device can take when threats are detected.</span></span> <span data-ttu-id="10ed3-238">Las acciones incluidas en esta lista no se muestran en la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="10ed3-238">The actions included in this list are not displayed in the user interface.</span></span>

|||
|:---|:---|
| <span data-ttu-id="10ed3-239">**Key**</span><span class="sxs-lookup"><span data-stu-id="10ed3-239">**Key**</span></span> | <span data-ttu-id="10ed3-240">disallowedThreatActions</span><span class="sxs-lookup"><span data-stu-id="10ed3-240">disallowedThreatActions</span></span> |
| <span data-ttu-id="10ed3-241">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="10ed3-241">**Data type**</span></span> | <span data-ttu-id="10ed3-242">Matriz de cadenas</span><span class="sxs-lookup"><span data-stu-id="10ed3-242">Array of strings</span></span> |
| <span data-ttu-id="10ed3-243">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="10ed3-243">**Possible values**</span></span> | <span data-ttu-id="10ed3-244">permitir (restringe a los usuarios permitir amenazas)</span><span class="sxs-lookup"><span data-stu-id="10ed3-244">allow (restricts users from allowing threats)</span></span> <br/> <span data-ttu-id="10ed3-245">restore (restringe a los usuarios la restauración de amenazas desde la cuarentena)</span><span class="sxs-lookup"><span data-stu-id="10ed3-245">restore (restricts users from restoring threats from the quarantine)</span></span> |
| <span data-ttu-id="10ed3-246">**Comments**</span><span class="sxs-lookup"><span data-stu-id="10ed3-246">**Comments**</span></span> | <span data-ttu-id="10ed3-247">Disponible en Defender para endpoint versión 100.83.73 o posterior.</span><span class="sxs-lookup"><span data-stu-id="10ed3-247">Available in Defender for Endpoint version 100.83.73 or higher.</span></span> |
|||

#### <a name="threat-type-settings"></a><span data-ttu-id="10ed3-248">Configuración del tipo de amenaza</span><span class="sxs-lookup"><span data-stu-id="10ed3-248">Threat type settings</span></span>

<span data-ttu-id="10ed3-249">La *preferencia threatTypeSettings* en el motor antivirus se usa para controlar cómo el producto controla determinados tipos de amenazas.</span><span class="sxs-lookup"><span data-stu-id="10ed3-249">The *threatTypeSettings* preference in the antivirus engine is used to control how certain threat types are handled by the product.</span></span>

|||
|:---|:---|
| <span data-ttu-id="10ed3-250">**Key**</span><span class="sxs-lookup"><span data-stu-id="10ed3-250">**Key**</span></span> | <span data-ttu-id="10ed3-251">threatTypeSettings</span><span class="sxs-lookup"><span data-stu-id="10ed3-251">threatTypeSettings</span></span> |
| <span data-ttu-id="10ed3-252">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="10ed3-252">**Data type**</span></span> | <span data-ttu-id="10ed3-253">Diccionario (preferencia anidada)</span><span class="sxs-lookup"><span data-stu-id="10ed3-253">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="10ed3-254">**Comments**</span><span class="sxs-lookup"><span data-stu-id="10ed3-254">**Comments**</span></span> | <span data-ttu-id="10ed3-255">Vea las secciones siguientes para obtener una descripción del contenido del diccionario.</span><span class="sxs-lookup"><span data-stu-id="10ed3-255">See the following sections for a description of the dictionary contents.</span></span> |
|||

<span data-ttu-id="10ed3-256">**Tipo de amenaza**</span><span class="sxs-lookup"><span data-stu-id="10ed3-256">**Threat type**</span></span>

<span data-ttu-id="10ed3-257">Tipo de amenaza para la que se configura el comportamiento.</span><span class="sxs-lookup"><span data-stu-id="10ed3-257">Type of threat for which the behavior is configured.</span></span>

|||
|:---|:---|
| <span data-ttu-id="10ed3-258">**Key**</span><span class="sxs-lookup"><span data-stu-id="10ed3-258">**Key**</span></span> | <span data-ttu-id="10ed3-259">clave</span><span class="sxs-lookup"><span data-stu-id="10ed3-259">key</span></span> |
| <span data-ttu-id="10ed3-260">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="10ed3-260">**Data type**</span></span> | <span data-ttu-id="10ed3-261">Cadena</span><span class="sxs-lookup"><span data-stu-id="10ed3-261">String</span></span> |
| <span data-ttu-id="10ed3-262">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="10ed3-262">**Possible values**</span></span> | <span data-ttu-id="10ed3-263">potentially_unwanted_application</span><span class="sxs-lookup"><span data-stu-id="10ed3-263">potentially_unwanted_application</span></span> <br/> <span data-ttu-id="10ed3-264">archive_bomb</span><span class="sxs-lookup"><span data-stu-id="10ed3-264">archive_bomb</span></span> |
|||

<span data-ttu-id="10ed3-265">**Acción que puede realizar**</span><span class="sxs-lookup"><span data-stu-id="10ed3-265">**Action to take**</span></span>

<span data-ttu-id="10ed3-266">Acción que se debe realizar al encontrarse con una amenaza del tipo especificado en la sección anterior.</span><span class="sxs-lookup"><span data-stu-id="10ed3-266">Action to take when coming across a threat of the type specified in the preceding section.</span></span> <span data-ttu-id="10ed3-267">Puede ser:</span><span class="sxs-lookup"><span data-stu-id="10ed3-267">Can be:</span></span>

- <span data-ttu-id="10ed3-268">**Auditoría:** el dispositivo no está protegido contra este tipo de amenaza, pero se registra una entrada sobre la amenaza.</span><span class="sxs-lookup"><span data-stu-id="10ed3-268">**Audit**: The device is not protected against this type of threat, but an entry about the threat is logged.</span></span>
- <span data-ttu-id="10ed3-269">**Bloquear:** el dispositivo está protegido contra este tipo de amenaza y se te notificará en la consola de seguridad.</span><span class="sxs-lookup"><span data-stu-id="10ed3-269">**Block**: The device is protected against this type of threat and you are notified in the security console.</span></span>
- <span data-ttu-id="10ed3-270">**Desactivado:** el dispositivo no está protegido contra este tipo de amenaza y no se registra nada.</span><span class="sxs-lookup"><span data-stu-id="10ed3-270">**Off**: The device is not protected against this type of threat and nothing is logged.</span></span>

|||
|:---|:---|
| <span data-ttu-id="10ed3-271">**Key**</span><span class="sxs-lookup"><span data-stu-id="10ed3-271">**Key**</span></span> | <span data-ttu-id="10ed3-272">valor</span><span class="sxs-lookup"><span data-stu-id="10ed3-272">value</span></span> |
| <span data-ttu-id="10ed3-273">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="10ed3-273">**Data type**</span></span> | <span data-ttu-id="10ed3-274">Cadena</span><span class="sxs-lookup"><span data-stu-id="10ed3-274">String</span></span> |
| <span data-ttu-id="10ed3-275">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="10ed3-275">**Possible values**</span></span> | <span data-ttu-id="10ed3-276">auditoría (valor predeterminado)</span><span class="sxs-lookup"><span data-stu-id="10ed3-276">audit (default)</span></span> <br/> <span data-ttu-id="10ed3-277">bloque</span><span class="sxs-lookup"><span data-stu-id="10ed3-277">block</span></span> <br/> <span data-ttu-id="10ed3-278">off</span><span class="sxs-lookup"><span data-stu-id="10ed3-278">off</span></span> |
|||

#### <a name="threat-type-settings-merge-policy"></a><span data-ttu-id="10ed3-279">Directiva de combinación de configuración de tipo de amenaza</span><span class="sxs-lookup"><span data-stu-id="10ed3-279">Threat type settings merge policy</span></span>

<span data-ttu-id="10ed3-280">Especifica la directiva de combinación para la configuración del tipo de amenaza.</span><span class="sxs-lookup"><span data-stu-id="10ed3-280">Specifies the merge policy for threat type settings.</span></span> <span data-ttu-id="10ed3-281">Puede ser una combinación de opciones definidas por el administrador y definidas por el usuario ( ) o solo opciones definidas `merge` por el administrador ( `admin_only` ).</span><span class="sxs-lookup"><span data-stu-id="10ed3-281">This can be a combination of administrator-defined and user-defined settings (`merge`) or only administrator-defined settings (`admin_only`).</span></span> <span data-ttu-id="10ed3-282">Esta configuración se puede usar para restringir que los usuarios locales definan su propia configuración para diferentes tipos de amenazas.</span><span class="sxs-lookup"><span data-stu-id="10ed3-282">This setting can be used to restrict local users from defining their own settings for different threat types.</span></span>

|||
|:---|:---|
| <span data-ttu-id="10ed3-283">**Key**</span><span class="sxs-lookup"><span data-stu-id="10ed3-283">**Key**</span></span> | <span data-ttu-id="10ed3-284">threatTypeSettingsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="10ed3-284">threatTypeSettingsMergePolicy</span></span> |
| <span data-ttu-id="10ed3-285">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="10ed3-285">**Data type**</span></span> | <span data-ttu-id="10ed3-286">Cadena</span><span class="sxs-lookup"><span data-stu-id="10ed3-286">String</span></span> |
| <span data-ttu-id="10ed3-287">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="10ed3-287">**Possible values**</span></span> | <span data-ttu-id="10ed3-288">merge (valor predeterminado)</span><span class="sxs-lookup"><span data-stu-id="10ed3-288">merge (default)</span></span> <br/> <span data-ttu-id="10ed3-289">admin_only</span><span class="sxs-lookup"><span data-stu-id="10ed3-289">admin_only</span></span> |
| <span data-ttu-id="10ed3-290">**Comments**</span><span class="sxs-lookup"><span data-stu-id="10ed3-290">**Comments**</span></span> | <span data-ttu-id="10ed3-291">Disponible en Defender para endpoint versión 100.83.73 o posterior.</span><span class="sxs-lookup"><span data-stu-id="10ed3-291">Available in Defender for Endpoint version 100.83.73 or higher.</span></span> |
|||

#### <a name="antivirus-scan-history-retention-in-days"></a><span data-ttu-id="10ed3-292">Retención del historial de examen antivirus (en días)</span><span class="sxs-lookup"><span data-stu-id="10ed3-292">Antivirus scan history retention (in days)</span></span>

<span data-ttu-id="10ed3-293">Especifica el número de días que los resultados se conservan en el historial de examen del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="10ed3-293">Specify the number of days that results are retained in the scan history on the device.</span></span> <span data-ttu-id="10ed3-294">Los resultados del examen antiguos se quitan del historial.</span><span class="sxs-lookup"><span data-stu-id="10ed3-294">Old scan results are removed from the history.</span></span> <span data-ttu-id="10ed3-295">Archivos antiguos en cuarentena que también se quitan del disco.</span><span class="sxs-lookup"><span data-stu-id="10ed3-295">Old quarantined files that are also removed from the disk.</span></span>

|||
|:---|:---|
| <span data-ttu-id="10ed3-296">**Key**</span><span class="sxs-lookup"><span data-stu-id="10ed3-296">**Key**</span></span> | <span data-ttu-id="10ed3-297">scanResultsRetentionDays</span><span class="sxs-lookup"><span data-stu-id="10ed3-297">scanResultsRetentionDays</span></span> |
| <span data-ttu-id="10ed3-298">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="10ed3-298">**Data type**</span></span> | <span data-ttu-id="10ed3-299">Cadena</span><span class="sxs-lookup"><span data-stu-id="10ed3-299">String</span></span> |
| <span data-ttu-id="10ed3-300">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="10ed3-300">**Possible values**</span></span> | <span data-ttu-id="10ed3-301">90 (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="10ed3-301">90 (default).</span></span> <span data-ttu-id="10ed3-302">Los valores permitidos van de 1 día a 180 días.</span><span class="sxs-lookup"><span data-stu-id="10ed3-302">Allowed values are from 1 day to 180 days.</span></span> |
| <span data-ttu-id="10ed3-303">**Comments**</span><span class="sxs-lookup"><span data-stu-id="10ed3-303">**Comments**</span></span> | <span data-ttu-id="10ed3-304">Disponible en Defender para endpoint versión 101.04.76 o posterior.</span><span class="sxs-lookup"><span data-stu-id="10ed3-304">Available in Defender for Endpoint version 101.04.76 or higher.</span></span> |
|||

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a><span data-ttu-id="10ed3-305">Número máximo de elementos en el historial de examen antivirus</span><span class="sxs-lookup"><span data-stu-id="10ed3-305">Maximum number of items in the antivirus scan history</span></span>

<span data-ttu-id="10ed3-306">Especifique el número máximo de entradas que se deben conservar en el historial de examen.</span><span class="sxs-lookup"><span data-stu-id="10ed3-306">Specify the maximum number of entries to keep in the scan history.</span></span> <span data-ttu-id="10ed3-307">Las entradas incluyen todos los exámenes a petición realizados en el pasado y todas las detecciones de antivirus.</span><span class="sxs-lookup"><span data-stu-id="10ed3-307">Entries include all on-demand scans performed in the past and all antivirus detections.</span></span>

|||
|:---|:---|
| <span data-ttu-id="10ed3-308">**Key**</span><span class="sxs-lookup"><span data-stu-id="10ed3-308">**Key**</span></span> | <span data-ttu-id="10ed3-309">scanHistoryMaximumItems</span><span class="sxs-lookup"><span data-stu-id="10ed3-309">scanHistoryMaximumItems</span></span> |
| <span data-ttu-id="10ed3-310">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="10ed3-310">**Data type**</span></span> | <span data-ttu-id="10ed3-311">Cadena</span><span class="sxs-lookup"><span data-stu-id="10ed3-311">String</span></span> |
| <span data-ttu-id="10ed3-312">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="10ed3-312">**Possible values**</span></span> | <span data-ttu-id="10ed3-313">10000 (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="10ed3-313">10000 (default).</span></span> <span data-ttu-id="10ed3-314">Los valores permitidos van de 5000 elementos a 15000 elementos.</span><span class="sxs-lookup"><span data-stu-id="10ed3-314">Allowed values are from 5000 items to 15000 items.</span></span> |
| <span data-ttu-id="10ed3-315">**Comments**</span><span class="sxs-lookup"><span data-stu-id="10ed3-315">**Comments**</span></span> | <span data-ttu-id="10ed3-316">Disponible en Defender para endpoint versión 101.04.76 o posterior.</span><span class="sxs-lookup"><span data-stu-id="10ed3-316">Available in Defender for Endpoint version 101.04.76 or higher.</span></span> |
|||

### <a name="cloud-delivered-protection-preferences"></a><span data-ttu-id="10ed3-317">Preferencias de protección entregadas en la nube</span><span class="sxs-lookup"><span data-stu-id="10ed3-317">Cloud-delivered protection preferences</span></span>

<span data-ttu-id="10ed3-318">La *entrada cloudService* en el perfil de configuración se usa para configurar la característica de protección controlada por la nube del producto.</span><span class="sxs-lookup"><span data-stu-id="10ed3-318">The *cloudService* entry in the configuration profile is used to configure the cloud-driven protection feature of the product.</span></span>

|||
|:---|:---|
| <span data-ttu-id="10ed3-319">**Key**</span><span class="sxs-lookup"><span data-stu-id="10ed3-319">**Key**</span></span> | <span data-ttu-id="10ed3-320">cloudService</span><span class="sxs-lookup"><span data-stu-id="10ed3-320">cloudService</span></span> |
| <span data-ttu-id="10ed3-321">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="10ed3-321">**Data type**</span></span> | <span data-ttu-id="10ed3-322">Diccionario (preferencia anidada)</span><span class="sxs-lookup"><span data-stu-id="10ed3-322">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="10ed3-323">**Comments**</span><span class="sxs-lookup"><span data-stu-id="10ed3-323">**Comments**</span></span> | <span data-ttu-id="10ed3-324">Vea las secciones siguientes para obtener una descripción del contenido del diccionario.</span><span class="sxs-lookup"><span data-stu-id="10ed3-324">See the following sections for a description of the dictionary contents.</span></span> |
|||

#### <a name="enable--disable-cloud-delivered-protection"></a><span data-ttu-id="10ed3-325">Habilitar o deshabilitar la protección de entrega en la nube</span><span class="sxs-lookup"><span data-stu-id="10ed3-325">Enable / disable cloud delivered protection</span></span>

<span data-ttu-id="10ed3-326">Determina si la protección entregada en la nube está habilitada en el dispositivo o no.</span><span class="sxs-lookup"><span data-stu-id="10ed3-326">Determines whether cloud-delivered protection is enabled on the device or not.</span></span> <span data-ttu-id="10ed3-327">Para mejorar la seguridad de los servicios, se recomienda mantener activada esta característica.</span><span class="sxs-lookup"><span data-stu-id="10ed3-327">To improve the security of your services, we recommend keeping this feature turned on.</span></span>

|||
|:---|:---|
| <span data-ttu-id="10ed3-328">**Key**</span><span class="sxs-lookup"><span data-stu-id="10ed3-328">**Key**</span></span> | <span data-ttu-id="10ed3-329">habilitado</span><span class="sxs-lookup"><span data-stu-id="10ed3-329">enabled</span></span> |
| <span data-ttu-id="10ed3-330">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="10ed3-330">**Data type**</span></span> | <span data-ttu-id="10ed3-331">Booleano</span><span class="sxs-lookup"><span data-stu-id="10ed3-331">Boolean</span></span> |
| <span data-ttu-id="10ed3-332">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="10ed3-332">**Possible values**</span></span> | <span data-ttu-id="10ed3-333">true (valor predeterminado)</span><span class="sxs-lookup"><span data-stu-id="10ed3-333">true (default)</span></span> <br/> <span data-ttu-id="10ed3-334">false</span><span class="sxs-lookup"><span data-stu-id="10ed3-334">false</span></span> |
|||

#### <a name="diagnostic-collection-level"></a><span data-ttu-id="10ed3-335">Nivel de colección de diagnóstico</span><span class="sxs-lookup"><span data-stu-id="10ed3-335">Diagnostic collection level</span></span>

<span data-ttu-id="10ed3-336">Los datos de diagnóstico se usan para mantener Defender for Endpoint seguro y actualizado, detectar, diagnosticar y corregir problemas y también realizar mejoras en el producto.</span><span class="sxs-lookup"><span data-stu-id="10ed3-336">Diagnostic data is used to keep Defender for Endpoint secure and up-to-date, detect, diagnose and fix problems, and also make product improvements.</span></span> <span data-ttu-id="10ed3-337">Esta configuración determina el nivel de diagnóstico enviado por el producto a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="10ed3-337">This setting determines the level of diagnostics sent by the product to Microsoft.</span></span>

|||
|:---|:---|
| <span data-ttu-id="10ed3-338">**Key**</span><span class="sxs-lookup"><span data-stu-id="10ed3-338">**Key**</span></span> | <span data-ttu-id="10ed3-339">diagnosticLevel</span><span class="sxs-lookup"><span data-stu-id="10ed3-339">diagnosticLevel</span></span> |
| <span data-ttu-id="10ed3-340">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="10ed3-340">**Data type**</span></span> | <span data-ttu-id="10ed3-341">Cadena</span><span class="sxs-lookup"><span data-stu-id="10ed3-341">String</span></span> |
| <span data-ttu-id="10ed3-342">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="10ed3-342">**Possible values**</span></span> | <span data-ttu-id="10ed3-343">opcional (predeterminado)</span><span class="sxs-lookup"><span data-stu-id="10ed3-343">optional (default)</span></span> <br/> <span data-ttu-id="10ed3-344">necesario</span><span class="sxs-lookup"><span data-stu-id="10ed3-344">required</span></span> |
|||

#### <a name="enable--disable-automatic-sample-submissions"></a><span data-ttu-id="10ed3-345">Habilitar o deshabilitar envíos de ejemplo automáticos</span><span class="sxs-lookup"><span data-stu-id="10ed3-345">Enable / disable automatic sample submissions</span></span>

<span data-ttu-id="10ed3-346">Determina si se envían muestras sospechosas (que probablemente contengan amenazas) a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="10ed3-346">Determines whether suspicious samples (that are likely to contain threats) are sent to Microsoft.</span></span> <span data-ttu-id="10ed3-347">Existen tres niveles para controlar el envío de muestra:</span><span class="sxs-lookup"><span data-stu-id="10ed3-347">There are three levels for controlling sample submission:</span></span>

- <span data-ttu-id="10ed3-348">**Ninguno:** no se envían muestras sospechosas a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="10ed3-348">**None**: no suspicious samples are submitted to Microsoft.</span></span>
- <span data-ttu-id="10ed3-349">**Seguro:** solo se envían automáticamente muestras sospechosas que no contienen información de identificación personal (PII).</span><span class="sxs-lookup"><span data-stu-id="10ed3-349">**Safe**: only suspicious samples that do not contain personally identifiable information (PII) are submitted automatically.</span></span> <span data-ttu-id="10ed3-350">Este es el valor predeterminado para esta configuración.</span><span class="sxs-lookup"><span data-stu-id="10ed3-350">This is the default value for this setting.</span></span>
- <span data-ttu-id="10ed3-351">**All**: todas las muestras sospechosas se envían a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="10ed3-351">**All**: all suspicious samples are submitted to Microsoft.</span></span>

|||
|:---|:---|
| <span data-ttu-id="10ed3-352">**Key**</span><span class="sxs-lookup"><span data-stu-id="10ed3-352">**Key**</span></span> | <span data-ttu-id="10ed3-353">automaticSampleSubmissionConsent</span><span class="sxs-lookup"><span data-stu-id="10ed3-353">automaticSampleSubmissionConsent</span></span> |
| <span data-ttu-id="10ed3-354">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="10ed3-354">**Data type**</span></span> | <span data-ttu-id="10ed3-355">Cadena</span><span class="sxs-lookup"><span data-stu-id="10ed3-355">String</span></span> |
| <span data-ttu-id="10ed3-356">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="10ed3-356">**Possible values**</span></span> | <span data-ttu-id="10ed3-357">ninguno</span><span class="sxs-lookup"><span data-stu-id="10ed3-357">none</span></span> <br/> <span data-ttu-id="10ed3-358">safe (valor predeterminado)</span><span class="sxs-lookup"><span data-stu-id="10ed3-358">safe (default)</span></span> <br/> <span data-ttu-id="10ed3-359">all</span><span class="sxs-lookup"><span data-stu-id="10ed3-359">all</span></span> |
|||

#### <a name="enable--disable-automatic-security-intelligence-updates"></a><span data-ttu-id="10ed3-360">Habilitar o deshabilitar actualizaciones automáticas de inteligencia de seguridad</span><span class="sxs-lookup"><span data-stu-id="10ed3-360">Enable / disable automatic security intelligence updates</span></span>

<span data-ttu-id="10ed3-361">Determina si las actualizaciones de inteligencia de seguridad se instalan automáticamente:</span><span class="sxs-lookup"><span data-stu-id="10ed3-361">Determines whether security intelligence updates are installed automatically:</span></span>

|||
|:---|:---|
| <span data-ttu-id="10ed3-362">**Key**</span><span class="sxs-lookup"><span data-stu-id="10ed3-362">**Key**</span></span> | <span data-ttu-id="10ed3-363">automaticDefinitionUpdateEnabled</span><span class="sxs-lookup"><span data-stu-id="10ed3-363">automaticDefinitionUpdateEnabled</span></span> |
| <span data-ttu-id="10ed3-364">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="10ed3-364">**Data type**</span></span> | <span data-ttu-id="10ed3-365">Booleano</span><span class="sxs-lookup"><span data-stu-id="10ed3-365">Boolean</span></span> |
| <span data-ttu-id="10ed3-366">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="10ed3-366">**Possible values**</span></span> | <span data-ttu-id="10ed3-367">true (valor predeterminado)</span><span class="sxs-lookup"><span data-stu-id="10ed3-367">true (default)</span></span> <br/> <span data-ttu-id="10ed3-368">false</span><span class="sxs-lookup"><span data-stu-id="10ed3-368">false</span></span> |
|||

## <a name="recommended-configuration-profile"></a><span data-ttu-id="10ed3-369">Perfil de configuración recomendado</span><span class="sxs-lookup"><span data-stu-id="10ed3-369">Recommended configuration profile</span></span>

<span data-ttu-id="10ed3-370">Para empezar, recomendamos el siguiente perfil de configuración para que la empresa aproveche todas las características de protección que proporciona Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="10ed3-370">To get started, we recommend the following configuration profile for your enterprise to take advantage of all protection features that Defender for Endpoint provides.</span></span>

<span data-ttu-id="10ed3-371">El siguiente perfil de configuración será:</span><span class="sxs-lookup"><span data-stu-id="10ed3-371">The following configuration profile will:</span></span>

- <span data-ttu-id="10ed3-372">Habilitar la protección en tiempo real (RTP)</span><span class="sxs-lookup"><span data-stu-id="10ed3-372">Enable real-time protection (RTP)</span></span>
- <span data-ttu-id="10ed3-373">Especifique cómo se controlan los siguientes tipos de amenazas:</span><span class="sxs-lookup"><span data-stu-id="10ed3-373">Specify how the following threat types are handled:</span></span>
  - <span data-ttu-id="10ed3-374">**Las aplicaciones potencialmente no deseadas (PUA)** están bloqueadas</span><span class="sxs-lookup"><span data-stu-id="10ed3-374">**Potentially unwanted applications (PUA)** are blocked</span></span>
  - <span data-ttu-id="10ed3-375">**Las bomba de archivo** (archivo con una tasa de compresión alta) se auditan en los registros del producto</span><span class="sxs-lookup"><span data-stu-id="10ed3-375">**Archive bombs** (file with a high compression rate) are audited to the product logs</span></span>
- <span data-ttu-id="10ed3-376">Habilitar actualizaciones automáticas de inteligencia de seguridad</span><span class="sxs-lookup"><span data-stu-id="10ed3-376">Enable automatic security intelligence updates</span></span>
- <span data-ttu-id="10ed3-377">Habilitar la protección de entrega en la nube</span><span class="sxs-lookup"><span data-stu-id="10ed3-377">Enable cloud-delivered protection</span></span>
- <span data-ttu-id="10ed3-378">Habilitar el envío automático de muestra en `safe` el nivel</span><span class="sxs-lookup"><span data-stu-id="10ed3-378">Enable automatic sample submission at `safe` level</span></span>

### <a name="sample-profile"></a><span data-ttu-id="10ed3-379">Perfil de ejemplo</span><span class="sxs-lookup"><span data-stu-id="10ed3-379">Sample profile</span></span>

```JSON
{
   "antivirusEngine":{
      "enableRealTimeProtection":true,
      "threatTypeSettings":[
         {
            "key":"potentially_unwanted_application",
            "value":"block"
         },
         {
            "key":"archive_bomb",
            "value":"audit"
         }
      ]
   },
   "cloudService":{
      "automaticDefinitionUpdateEnabled":true,
      "automaticSampleSubmissionConsent":"safe",
      "enabled":true
      "proxy":"http://proxy.server:port/"
   }
}
```

## <a name="full-configuration-profile-example"></a><span data-ttu-id="10ed3-380">Ejemplo de perfil de configuración completa</span><span class="sxs-lookup"><span data-stu-id="10ed3-380">Full configuration profile example</span></span>

<span data-ttu-id="10ed3-381">El siguiente perfil de configuración contiene entradas para todas las opciones descritas en este documento y se puede usar para escenarios más avanzados en los que desea tener más control sobre el producto.</span><span class="sxs-lookup"><span data-stu-id="10ed3-381">The following configuration profile contains entries for all settings described in this document and can be used for more advanced scenarios where you want more control over the product.</span></span>

### <a name="full-profile"></a><span data-ttu-id="10ed3-382">Perfil completo</span><span class="sxs-lookup"><span data-stu-id="10ed3-382">Full profile</span></span>

```JSON
{
   "antivirusEngine":{
      "enableRealTimeProtection":true,
      "passiveMode":false,
      "exclusionsMergePolicy":"merge",
      "exclusions":[
         {
            "$type":"excludedPath",
            "isDirectory":false,
            "path":"/var/log/system.log"
         },
         {
            "$type":"excludedPath",
            "isDirectory":true,
            "path":"/home"
         },
         {
            "$type":"excludedFileExtension",
            "extension":"pdf"
         },
         {
            "$type":"excludedFileName",
            "name":"cat"
         }
      ],
      "allowedThreats":[
         "EICAR-Test-File (not a virus)"
      ],
      "disallowedThreatActions":[
         "allow",
         "restore"
      ],
      "threatTypeSettingsMergePolicy":"merge",
      "threatTypeSettings":[
         {
            "key":"potentially_unwanted_application",
            "value":"block"
         },
         {
            "key":"archive_bomb",
            "value":"audit"
         }
      ]
   },
   "cloudService":{
      "enabled":true,
      "diagnosticLevel":"optional",
      "automaticSampleSubmissionConsent":"safe",
      "automaticDefinitionUpdateEnabled":true
      "proxy": "http://proxy.server:port/"
   }
}
```

## <a name="configuration-profile-validation"></a><span data-ttu-id="10ed3-383">Validación de perfiles de configuración</span><span class="sxs-lookup"><span data-stu-id="10ed3-383">Configuration profile validation</span></span>

<span data-ttu-id="10ed3-384">El perfil de configuración debe ser un archivo con formato JSON válido.</span><span class="sxs-lookup"><span data-stu-id="10ed3-384">The configuration profile must be a valid JSON-formatted file.</span></span> <span data-ttu-id="10ed3-385">Hay varias herramientas que se pueden usar para comprobar esto.</span><span class="sxs-lookup"><span data-stu-id="10ed3-385">There are a number of tools that can be used to verify this.</span></span> <span data-ttu-id="10ed3-386">Por ejemplo, si has `python` instalado en el dispositivo:</span><span class="sxs-lookup"><span data-stu-id="10ed3-386">For example, if you have `python` installed on your device:</span></span>

```bash
python -m json.tool mdatp_managed.json
```

<span data-ttu-id="10ed3-387">Si el JSON está bien formado, el comando anterior lo devuelve al Terminal y devuelve un código de salida de `0` .</span><span class="sxs-lookup"><span data-stu-id="10ed3-387">If the JSON is well-formed, the above command outputs it back to the Terminal and returns an exit code of `0`.</span></span> <span data-ttu-id="10ed3-388">De lo contrario, se muestra un error que describe el problema y el comando devuelve un código de salida de `1` .</span><span class="sxs-lookup"><span data-stu-id="10ed3-388">Otherwise, an error that describes the issue is displayed and the command returns an exit code of `1`.</span></span>

## <a name="verifying-that-the-mdatp_managedjson-file-is-working-as-expected"></a><span data-ttu-id="10ed3-389">Comprobar que el archivo mdatp_managed.jsestá funcionando según lo esperado</span><span class="sxs-lookup"><span data-stu-id="10ed3-389">Verifying that the mdatp_managed.json file is working as expected</span></span>
<span data-ttu-id="10ed3-390">Para comprobar que el /etc/opt/microsoft/mdatp/managed/mdatp_managed.json funciona correctamente, debería ver "[administrado]" junto a esta configuración:</span><span class="sxs-lookup"><span data-stu-id="10ed3-390">To verify that your /etc/opt/microsoft/mdatp/managed/mdatp_managed.json is working properly, you should see "[managed]" next to these settings:</span></span>  
- <span data-ttu-id="10ed3-391">cloud_enabled</span><span class="sxs-lookup"><span data-stu-id="10ed3-391">cloud_enabled</span></span>
- <span data-ttu-id="10ed3-392">cloud_automatic_sample_submission_consent</span><span class="sxs-lookup"><span data-stu-id="10ed3-392">cloud_automatic_sample_submission_consent</span></span>
- <span data-ttu-id="10ed3-393">passice_mode_enabled</span><span class="sxs-lookup"><span data-stu-id="10ed3-393">passice_mode_enabled</span></span>
- <span data-ttu-id="10ed3-394">real_time_protection_enabled</span><span class="sxs-lookup"><span data-stu-id="10ed3-394">real_time_protection_enabled</span></span>
- <span data-ttu-id="10ed3-395">automatic_definition_update_enabled</span><span class="sxs-lookup"><span data-stu-id="10ed3-395">automatic_definition_update_enabled</span></span>

> [!NOTE]
> <span data-ttu-id="10ed3-396">Para que mdatp_managed.jsse haga efectivo, no es necesario reiniciar el wdavdaemon.</span><span class="sxs-lookup"><span data-stu-id="10ed3-396">For the mdatp_managed.json to take effect, no restart of the wdavdaemon is required.</span></span>

## <a name="configuration-profile-deployment"></a><span data-ttu-id="10ed3-397">Implementación de perfiles de configuración</span><span class="sxs-lookup"><span data-stu-id="10ed3-397">Configuration profile deployment</span></span>

<span data-ttu-id="10ed3-398">Una vez que haya creado el perfil de configuración para su empresa, puede implementarlo a través de la herramienta de administración que usa su empresa.</span><span class="sxs-lookup"><span data-stu-id="10ed3-398">Once you've built the configuration profile for your enterprise, you can deploy it through the management tool that your enterprise is using.</span></span> <span data-ttu-id="10ed3-399">Defender para Endpoint para Linux lee la configuración administrada del archivo */etc/opt/microsoft/mdatp/managed/mdatp_managed.json.*</span><span class="sxs-lookup"><span data-stu-id="10ed3-399">Defender for Endpoint for Linux reads the managed configuration from the */etc/opt/microsoft/mdatp/managed/mdatp_managed.json* file.</span></span>
