---
title: Establecer preferencias para Microsoft Defender para endpoint en Linux
ms.reviewer: ''
description: Describe cómo configurar Microsoft Defender para Endpoint en Linux en empresas.
keywords: microsoft, defender, Microsoft Defender para Endpoint, linux, installation, deploy, uninstallation, puppet, ansible, linux, redhat, ubuntu, debian, sles, suse, centos
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
ms.openlocfilehash: 7998e878ad03fdfb64c314dc8b7234ece46164ce
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289498"
---
# <a name="set-preferences-for-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="38ff4-104">Establecer preferencias para Microsoft Defender para endpoint en Linux</span><span class="sxs-lookup"><span data-stu-id="38ff4-104">Set preferences for Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="38ff4-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="38ff4-105">**Applies to:**</span></span>
- [<span data-ttu-id="38ff4-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="38ff4-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="38ff4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="38ff4-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="38ff4-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="38ff4-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="38ff4-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="38ff4-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

> [!IMPORTANT]
> <span data-ttu-id="38ff4-110">Este tema contiene instrucciones sobre cómo establecer las preferencias de Defender para Endpoint en Linux en entornos empresariales.</span><span class="sxs-lookup"><span data-stu-id="38ff4-110">This topic contains instructions for how to set preferences for Defender for Endpoint on Linux in enterprise environments.</span></span> <span data-ttu-id="38ff4-111">Si estás interesado en configurar el producto en un dispositivo desde la línea de comandos, consulta [Recursos](linux-resources.md#configure-from-the-command-line).</span><span class="sxs-lookup"><span data-stu-id="38ff4-111">If you are interested in configuring the product on a device from the command-line, see [Resources](linux-resources.md#configure-from-the-command-line).</span></span>

<span data-ttu-id="38ff4-112">En entornos empresariales, Defender para Endpoint en Linux se puede administrar a través de un perfil de configuración.</span><span class="sxs-lookup"><span data-stu-id="38ff4-112">In enterprise environments, Defender for Endpoint on Linux can be managed through a configuration profile.</span></span> <span data-ttu-id="38ff4-113">Este perfil se implementa desde la herramienta de administración que prefiera.</span><span class="sxs-lookup"><span data-stu-id="38ff4-113">This profile is deployed from the management tool of your choice.</span></span> <span data-ttu-id="38ff4-114">Las preferencias administradas por la empresa tienen prioridad sobre las establecidas localmente en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="38ff4-114">Preferences managed by the enterprise take precedence over the ones set locally on the device.</span></span> <span data-ttu-id="38ff4-115">En otras palabras, los usuarios de su empresa no pueden cambiar las preferencias que se establecen a través de este perfil de configuración.</span><span class="sxs-lookup"><span data-stu-id="38ff4-115">In other words, users in your enterprise are not able to change preferences that are set through this configuration profile.</span></span>

<span data-ttu-id="38ff4-116">En este artículo se describe la estructura de este perfil (incluido un perfil recomendado que puede usar para empezar) e instrucciones sobre cómo implementar el perfil.</span><span class="sxs-lookup"><span data-stu-id="38ff4-116">This article describes the structure of this profile (including a recommended profile that you can use to get started) and instructions on how to deploy the profile.</span></span>

## <a name="configuration-profile-structure"></a><span data-ttu-id="38ff4-117">Estructura de perfiles de configuración</span><span class="sxs-lookup"><span data-stu-id="38ff4-117">Configuration profile structure</span></span>

<span data-ttu-id="38ff4-118">El perfil de configuración es un archivo .json que consta de entradas identificadas por una clave (que indica el nombre de la preferencia), seguido de un valor, que depende de la naturaleza de la preferencia.</span><span class="sxs-lookup"><span data-stu-id="38ff4-118">The configuration profile is a .json file that consists of entries identified by a key (which denotes the name of the preference), followed by a value, which depends on the nature of the preference.</span></span> <span data-ttu-id="38ff4-119">Los valores pueden ser simples, como un valor numérico o complejos, como una lista anidada de preferencias.</span><span class="sxs-lookup"><span data-stu-id="38ff4-119">Values can be simple, such as a numerical value, or complex, such as a nested list of preferences.</span></span>

<span data-ttu-id="38ff4-120">Normalmente, se usa una herramienta de administración de configuración para insertar un archivo con el nombre ```mdatp_managed.json``` en la ubicación ```/etc/opt/microsoft/mdatp/managed/``` .</span><span class="sxs-lookup"><span data-stu-id="38ff4-120">Typically, you would use a configuration management tool to push a file with the name ```mdatp_managed.json``` at the location ```/etc/opt/microsoft/mdatp/managed/```.</span></span>

<span data-ttu-id="38ff4-121">El nivel superior del perfil de configuración incluye las preferencias de todo el producto y las entradas para las subáreas del producto, que se explican con más detalle en las secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="38ff4-121">The top level of the configuration profile includes product-wide preferences and entries for subareas of the product, which are explained in more detail in the next sections.</span></span>

### <a name="antivirus-engine-preferences"></a><span data-ttu-id="38ff4-122">Preferencias del motor antivirus</span><span class="sxs-lookup"><span data-stu-id="38ff4-122">Antivirus engine preferences</span></span>

<span data-ttu-id="38ff4-123">La *sección antivirusEngine* del perfil de configuración se usa para administrar las preferencias del componente antivirus del producto.</span><span class="sxs-lookup"><span data-stu-id="38ff4-123">The *antivirusEngine* section of the configuration profile is used to manage the preferences of the antivirus component of the product.</span></span>

<br>

****

|<span data-ttu-id="38ff4-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="38ff4-124">Description</span></span>|<span data-ttu-id="38ff4-125">Valor</span><span class="sxs-lookup"><span data-stu-id="38ff4-125">Value</span></span>|
|---|---|
|<span data-ttu-id="38ff4-126">**Key**</span><span class="sxs-lookup"><span data-stu-id="38ff4-126">**Key**</span></span>|<span data-ttu-id="38ff4-127">antivirusEngine</span><span class="sxs-lookup"><span data-stu-id="38ff4-127">antivirusEngine</span></span>|
|<span data-ttu-id="38ff4-128">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="38ff4-128">**Data type**</span></span>|<span data-ttu-id="38ff4-129">Diccionario (preferencia anidada)</span><span class="sxs-lookup"><span data-stu-id="38ff4-129">Dictionary (nested preference)</span></span>|
|<span data-ttu-id="38ff4-130">**Comments**</span><span class="sxs-lookup"><span data-stu-id="38ff4-130">**Comments**</span></span>|<span data-ttu-id="38ff4-131">Vea las secciones siguientes para obtener una descripción del contenido del diccionario.</span><span class="sxs-lookup"><span data-stu-id="38ff4-131">See the following sections for a description of the dictionary contents.</span></span>|
|

#### <a name="enable--disable-real-time-protection"></a><span data-ttu-id="38ff4-132">Habilitar o deshabilitar la protección en tiempo real</span><span class="sxs-lookup"><span data-stu-id="38ff4-132">Enable / disable real-time protection</span></span>

<span data-ttu-id="38ff4-133">Determina si la protección en tiempo real (examinar archivos a medida que se accede a ellos) está habilitada o no.</span><span class="sxs-lookup"><span data-stu-id="38ff4-133">Determines whether real-time protection (scan files as they are accessed) is enabled or not.</span></span>

<br>

****

|<span data-ttu-id="38ff4-134">Descripción</span><span class="sxs-lookup"><span data-stu-id="38ff4-134">Description</span></span>|<span data-ttu-id="38ff4-135">Valor</span><span class="sxs-lookup"><span data-stu-id="38ff4-135">Value</span></span>|
|---|---|
|<span data-ttu-id="38ff4-136">**Key**</span><span class="sxs-lookup"><span data-stu-id="38ff4-136">**Key**</span></span>|<span data-ttu-id="38ff4-137">enableRealTimeProtection</span><span class="sxs-lookup"><span data-stu-id="38ff4-137">enableRealTimeProtection</span></span>|
|<span data-ttu-id="38ff4-138">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="38ff4-138">**Data type**</span></span>|<span data-ttu-id="38ff4-139">Booleano</span><span class="sxs-lookup"><span data-stu-id="38ff4-139">Boolean</span></span>|
|<span data-ttu-id="38ff4-140">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="38ff4-140">**Possible values**</span></span>|<span data-ttu-id="38ff4-141">true (valor predeterminado)</span><span class="sxs-lookup"><span data-stu-id="38ff4-141">true (default)</span></span> <p> <span data-ttu-id="38ff4-142">false</span><span class="sxs-lookup"><span data-stu-id="38ff4-142">false</span></span>|
|

#### <a name="enable--disable-passive-mode"></a><span data-ttu-id="38ff4-143">Habilitar o deshabilitar el modo pasivo</span><span class="sxs-lookup"><span data-stu-id="38ff4-143">Enable / disable passive mode</span></span>

<span data-ttu-id="38ff4-144">Determina si el motor antivirus se ejecuta en modo pasivo o no.</span><span class="sxs-lookup"><span data-stu-id="38ff4-144">Determines whether the antivirus engine runs in passive mode or not.</span></span> <span data-ttu-id="38ff4-145">En modo pasivo:</span><span class="sxs-lookup"><span data-stu-id="38ff4-145">In passive mode:</span></span>

- <span data-ttu-id="38ff4-146">La protección en tiempo real está desactivada.</span><span class="sxs-lookup"><span data-stu-id="38ff4-146">Real-time protection is turned off.</span></span>
- <span data-ttu-id="38ff4-147">El examen a petición está activado.</span><span class="sxs-lookup"><span data-stu-id="38ff4-147">On-demand scanning is turned on.</span></span>
- <span data-ttu-id="38ff4-148">La corrección automática de amenazas está desactivada.</span><span class="sxs-lookup"><span data-stu-id="38ff4-148">Automatic threat remediation is turned off.</span></span>
- <span data-ttu-id="38ff4-149">Las actualizaciones de inteligencia de seguridad están activadas.</span><span class="sxs-lookup"><span data-stu-id="38ff4-149">Security intelligence updates are turned on.</span></span>
- <span data-ttu-id="38ff4-150">El icono del menú Estado está oculto.</span><span class="sxs-lookup"><span data-stu-id="38ff4-150">Status menu icon is hidden.</span></span>

<br>

****

|<span data-ttu-id="38ff4-151">Descripción</span><span class="sxs-lookup"><span data-stu-id="38ff4-151">Description</span></span>|<span data-ttu-id="38ff4-152">Valor</span><span class="sxs-lookup"><span data-stu-id="38ff4-152">Value</span></span>|
|---|---|
|<span data-ttu-id="38ff4-153">**Key**</span><span class="sxs-lookup"><span data-stu-id="38ff4-153">**Key**</span></span>|<span data-ttu-id="38ff4-154">passiveMode</span><span class="sxs-lookup"><span data-stu-id="38ff4-154">passiveMode</span></span>|
|<span data-ttu-id="38ff4-155">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="38ff4-155">**Data type**</span></span>|<span data-ttu-id="38ff4-156">Booleano</span><span class="sxs-lookup"><span data-stu-id="38ff4-156">Boolean</span></span>|
|<span data-ttu-id="38ff4-157">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="38ff4-157">**Possible values**</span></span>|<span data-ttu-id="38ff4-158">false (predeterminado)</span><span class="sxs-lookup"><span data-stu-id="38ff4-158">false (default)</span></span> <p> <span data-ttu-id="38ff4-159">true</span><span class="sxs-lookup"><span data-stu-id="38ff4-159">true</span></span>|
|<span data-ttu-id="38ff4-160">**Comments**</span><span class="sxs-lookup"><span data-stu-id="38ff4-160">**Comments**</span></span>|<span data-ttu-id="38ff4-161">Disponible en Defender para endpoint versión 100.67.60 o posterior.</span><span class="sxs-lookup"><span data-stu-id="38ff4-161">Available in Defender for Endpoint version 100.67.60 or higher.</span></span>|
|

#### <a name="exclusion-merge-policy"></a><span data-ttu-id="38ff4-162">Directiva de combinación de exclusión</span><span class="sxs-lookup"><span data-stu-id="38ff4-162">Exclusion merge policy</span></span>

<span data-ttu-id="38ff4-163">Especifica la directiva de combinación para exclusiones.</span><span class="sxs-lookup"><span data-stu-id="38ff4-163">Specifies the merge policy for exclusions.</span></span> <span data-ttu-id="38ff4-164">Puede ser una combinación de exclusiones definidas por el administrador y definidas por el usuario ( ) o solo `merge` exclusiones definidas por el administrador ( `admin_only` ).</span><span class="sxs-lookup"><span data-stu-id="38ff4-164">It can be a combination of administrator-defined and user-defined exclusions (`merge`) or only administrator-defined exclusions (`admin_only`).</span></span> <span data-ttu-id="38ff4-165">Esta configuración se puede usar para restringir que los usuarios locales definan sus propias exclusiones.</span><span class="sxs-lookup"><span data-stu-id="38ff4-165">This setting can be used to restrict local users from defining their own exclusions.</span></span>

<br>

****

|<span data-ttu-id="38ff4-166">Descripción</span><span class="sxs-lookup"><span data-stu-id="38ff4-166">Description</span></span>|<span data-ttu-id="38ff4-167">Valor</span><span class="sxs-lookup"><span data-stu-id="38ff4-167">Value</span></span>|
|---|---|
|<span data-ttu-id="38ff4-168">**Key**</span><span class="sxs-lookup"><span data-stu-id="38ff4-168">**Key**</span></span>|<span data-ttu-id="38ff4-169">exclusionsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="38ff4-169">exclusionsMergePolicy</span></span>|
|<span data-ttu-id="38ff4-170">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="38ff4-170">**Data type**</span></span>|<span data-ttu-id="38ff4-171">Cadena</span><span class="sxs-lookup"><span data-stu-id="38ff4-171">String</span></span>|
|<span data-ttu-id="38ff4-172">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="38ff4-172">**Possible values**</span></span>|<span data-ttu-id="38ff4-173">merge (valor predeterminado)</span><span class="sxs-lookup"><span data-stu-id="38ff4-173">merge (default)</span></span> <p> <span data-ttu-id="38ff4-174">admin_only</span><span class="sxs-lookup"><span data-stu-id="38ff4-174">admin_only</span></span>|
|<span data-ttu-id="38ff4-175">**Comments**</span><span class="sxs-lookup"><span data-stu-id="38ff4-175">**Comments**</span></span>|<span data-ttu-id="38ff4-176">Disponible en Defender para endpoint versión 100.83.73 o posterior.</span><span class="sxs-lookup"><span data-stu-id="38ff4-176">Available in Defender for Endpoint version 100.83.73 or higher.</span></span>|
|

#### <a name="scan-exclusions"></a><span data-ttu-id="38ff4-177">Exclusiones de examen</span><span class="sxs-lookup"><span data-stu-id="38ff4-177">Scan exclusions</span></span>

<span data-ttu-id="38ff4-178">Entidades que se han excluido del examen.</span><span class="sxs-lookup"><span data-stu-id="38ff4-178">Entities that have been excluded from the scan.</span></span> <span data-ttu-id="38ff4-179">Las exclusiones se pueden especificar por rutas de acceso completas, extensiones o nombres de archivo.</span><span class="sxs-lookup"><span data-stu-id="38ff4-179">Exclusions can be specified by full paths, extensions, or file names.</span></span>
<span data-ttu-id="38ff4-180">(Las exclusiones se especifican como una matriz de elementos, el administrador puede especificar tantos elementos como sea necesario, en cualquier orden).</span><span class="sxs-lookup"><span data-stu-id="38ff4-180">(Exclusions are specified as an array of items, administrator can specify as many elements as necessary, in any order.)</span></span>

<br>

****

|<span data-ttu-id="38ff4-181">Descripción</span><span class="sxs-lookup"><span data-stu-id="38ff4-181">Description</span></span>|<span data-ttu-id="38ff4-182">Valor</span><span class="sxs-lookup"><span data-stu-id="38ff4-182">Value</span></span>|
|---|---|
|<span data-ttu-id="38ff4-183">**Key**</span><span class="sxs-lookup"><span data-stu-id="38ff4-183">**Key**</span></span>|<span data-ttu-id="38ff4-184">exclusiones</span><span class="sxs-lookup"><span data-stu-id="38ff4-184">exclusions</span></span>|
|<span data-ttu-id="38ff4-185">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="38ff4-185">**Data type**</span></span>|<span data-ttu-id="38ff4-186">Diccionario (preferencia anidada)</span><span class="sxs-lookup"><span data-stu-id="38ff4-186">Dictionary (nested preference)</span></span>|
|<span data-ttu-id="38ff4-187">**Comments**</span><span class="sxs-lookup"><span data-stu-id="38ff4-187">**Comments**</span></span>|<span data-ttu-id="38ff4-188">Vea las secciones siguientes para obtener una descripción del contenido del diccionario.</span><span class="sxs-lookup"><span data-stu-id="38ff4-188">See the following sections for a description of the dictionary contents.</span></span>|
|

##### <a name="type-of-exclusion"></a><span data-ttu-id="38ff4-189">Tipo de exclusión</span><span class="sxs-lookup"><span data-stu-id="38ff4-189">Type of exclusion</span></span>

<span data-ttu-id="38ff4-190">Especifica el tipo de contenido excluido del examen.</span><span class="sxs-lookup"><span data-stu-id="38ff4-190">Specifies the type of content excluded from the scan.</span></span>

<br>

****

|<span data-ttu-id="38ff4-191">Descripción</span><span class="sxs-lookup"><span data-stu-id="38ff4-191">Description</span></span>|<span data-ttu-id="38ff4-192">Valor</span><span class="sxs-lookup"><span data-stu-id="38ff4-192">Value</span></span>|
|---|---|
|<span data-ttu-id="38ff4-193">**Key**</span><span class="sxs-lookup"><span data-stu-id="38ff4-193">**Key**</span></span>|<span data-ttu-id="38ff4-194">$type</span><span class="sxs-lookup"><span data-stu-id="38ff4-194">$type</span></span>|
|<span data-ttu-id="38ff4-195">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="38ff4-195">**Data type**</span></span>|<span data-ttu-id="38ff4-196">Cadena</span><span class="sxs-lookup"><span data-stu-id="38ff4-196">String</span></span>|
|<span data-ttu-id="38ff4-197">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="38ff4-197">**Possible values**</span></span>|<span data-ttu-id="38ff4-198">excludedPath</span><span class="sxs-lookup"><span data-stu-id="38ff4-198">excludedPath</span></span> <p> <span data-ttu-id="38ff4-199">excludedFileExtension</span><span class="sxs-lookup"><span data-stu-id="38ff4-199">excludedFileExtension</span></span> <p> <span data-ttu-id="38ff4-200">excludedFileName</span><span class="sxs-lookup"><span data-stu-id="38ff4-200">excludedFileName</span></span>|
|

##### <a name="path-to-excluded-content"></a><span data-ttu-id="38ff4-201">Ruta de acceso al contenido excluido</span><span class="sxs-lookup"><span data-stu-id="38ff4-201">Path to excluded content</span></span>

<span data-ttu-id="38ff4-202">Se usa para excluir contenido del examen por ruta de acceso de archivo completa.</span><span class="sxs-lookup"><span data-stu-id="38ff4-202">Used to exclude content from the scan by full file path.</span></span>

<br>

****

|<span data-ttu-id="38ff4-203">Descripción</span><span class="sxs-lookup"><span data-stu-id="38ff4-203">Description</span></span>|<span data-ttu-id="38ff4-204">Valor</span><span class="sxs-lookup"><span data-stu-id="38ff4-204">Value</span></span>|
|---|---|
|<span data-ttu-id="38ff4-205">**Key**</span><span class="sxs-lookup"><span data-stu-id="38ff4-205">**Key**</span></span>|<span data-ttu-id="38ff4-206">path</span><span class="sxs-lookup"><span data-stu-id="38ff4-206">path</span></span>|
|<span data-ttu-id="38ff4-207">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="38ff4-207">**Data type**</span></span>|<span data-ttu-id="38ff4-208">Cadena</span><span class="sxs-lookup"><span data-stu-id="38ff4-208">String</span></span>|
|<span data-ttu-id="38ff4-209">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="38ff4-209">**Possible values**</span></span>|<span data-ttu-id="38ff4-210">rutas de acceso válidas</span><span class="sxs-lookup"><span data-stu-id="38ff4-210">valid paths</span></span>|
|<span data-ttu-id="38ff4-211">**Comments**</span><span class="sxs-lookup"><span data-stu-id="38ff4-211">**Comments**</span></span>|<span data-ttu-id="38ff4-212">Aplicable solo *si $type* *se excluyePath*</span><span class="sxs-lookup"><span data-stu-id="38ff4-212">Applicable only if *$type* is *excludedPath*</span></span>|
|

##### <a name="path-type-file--directory"></a><span data-ttu-id="38ff4-213">Tipo de ruta de acceso (archivo/directorio)</span><span class="sxs-lookup"><span data-stu-id="38ff4-213">Path type (file / directory)</span></span>

<span data-ttu-id="38ff4-214">Indica si la *propiedad path* hace referencia a un archivo o directorio.</span><span class="sxs-lookup"><span data-stu-id="38ff4-214">Indicates if the *path* property refers to a file or directory.</span></span>

<br>

****

|<span data-ttu-id="38ff4-215">Descripción</span><span class="sxs-lookup"><span data-stu-id="38ff4-215">Description</span></span>|<span data-ttu-id="38ff4-216">Valor</span><span class="sxs-lookup"><span data-stu-id="38ff4-216">Value</span></span>|
|---|---|
|<span data-ttu-id="38ff4-217">**Key**</span><span class="sxs-lookup"><span data-stu-id="38ff4-217">**Key**</span></span>|<span data-ttu-id="38ff4-218">isDirectory</span><span class="sxs-lookup"><span data-stu-id="38ff4-218">isDirectory</span></span>|
|<span data-ttu-id="38ff4-219">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="38ff4-219">**Data type**</span></span>|<span data-ttu-id="38ff4-220">Booleano</span><span class="sxs-lookup"><span data-stu-id="38ff4-220">Boolean</span></span>|
|<span data-ttu-id="38ff4-221">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="38ff4-221">**Possible values**</span></span>|<span data-ttu-id="38ff4-222">false (predeterminado)</span><span class="sxs-lookup"><span data-stu-id="38ff4-222">false (default)</span></span> <p> <span data-ttu-id="38ff4-223">true</span><span class="sxs-lookup"><span data-stu-id="38ff4-223">true</span></span>|
|<span data-ttu-id="38ff4-224">**Comments**</span><span class="sxs-lookup"><span data-stu-id="38ff4-224">**Comments**</span></span>|<span data-ttu-id="38ff4-225">Aplicable solo *si $type* *se excluyePath*</span><span class="sxs-lookup"><span data-stu-id="38ff4-225">Applicable only if *$type* is *excludedPath*</span></span>|
|

##### <a name="file-extension-excluded-from-the-scan"></a><span data-ttu-id="38ff4-226">Extensión de archivo excluida del examen</span><span class="sxs-lookup"><span data-stu-id="38ff4-226">File extension excluded from the scan</span></span>

<span data-ttu-id="38ff4-227">Se usa para excluir contenido del examen por extensión de archivo.</span><span class="sxs-lookup"><span data-stu-id="38ff4-227">Used to exclude content from the scan by file extension.</span></span>

<br>

****

|<span data-ttu-id="38ff4-228">Descripción</span><span class="sxs-lookup"><span data-stu-id="38ff4-228">Description</span></span>|<span data-ttu-id="38ff4-229">Valor</span><span class="sxs-lookup"><span data-stu-id="38ff4-229">Value</span></span>|
|---|---|
|<span data-ttu-id="38ff4-230">**Key**</span><span class="sxs-lookup"><span data-stu-id="38ff4-230">**Key**</span></span>|<span data-ttu-id="38ff4-231">extensión</span><span class="sxs-lookup"><span data-stu-id="38ff4-231">extension</span></span>|
|<span data-ttu-id="38ff4-232">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="38ff4-232">**Data type**</span></span>|<span data-ttu-id="38ff4-233">Cadena</span><span class="sxs-lookup"><span data-stu-id="38ff4-233">String</span></span>|
|<span data-ttu-id="38ff4-234">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="38ff4-234">**Possible values**</span></span>|<span data-ttu-id="38ff4-235">extensiones de archivo válidas</span><span class="sxs-lookup"><span data-stu-id="38ff4-235">valid file extensions</span></span>|
|<span data-ttu-id="38ff4-236">**Comments**</span><span class="sxs-lookup"><span data-stu-id="38ff4-236">**Comments**</span></span>|<span data-ttu-id="38ff4-237">Aplicable solo *si $type* *se excluyeFileExtension*</span><span class="sxs-lookup"><span data-stu-id="38ff4-237">Applicable only if *$type* is *excludedFileExtension*</span></span>|
|

##### <a name="process-excluded-from-the-scan"></a><span data-ttu-id="38ff4-238">Proceso excluido del examen\*</span><span class="sxs-lookup"><span data-stu-id="38ff4-238">Process excluded from the scan\*</span></span>

<span data-ttu-id="38ff4-239">Especifica un proceso para el que se excluye toda la actividad de archivo del examen.</span><span class="sxs-lookup"><span data-stu-id="38ff4-239">Specifies a process for which all file activity is excluded from scanning.</span></span> <span data-ttu-id="38ff4-240">El proceso se puede especificar por su nombre (por ejemplo, ) o la ruta de acceso `cat` completa (por ejemplo, `/bin/cat` ).</span><span class="sxs-lookup"><span data-stu-id="38ff4-240">The process can be specified either by its name (for example, `cat`) or full path (for example, `/bin/cat`).</span></span>

<br>

****

|<span data-ttu-id="38ff4-241">Descripción</span><span class="sxs-lookup"><span data-stu-id="38ff4-241">Description</span></span>|<span data-ttu-id="38ff4-242">Valor</span><span class="sxs-lookup"><span data-stu-id="38ff4-242">Value</span></span>|
|---|---|
|<span data-ttu-id="38ff4-243">**Key**</span><span class="sxs-lookup"><span data-stu-id="38ff4-243">**Key**</span></span>|<span data-ttu-id="38ff4-244">name</span><span class="sxs-lookup"><span data-stu-id="38ff4-244">name</span></span>|
|<span data-ttu-id="38ff4-245">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="38ff4-245">**Data type**</span></span>|<span data-ttu-id="38ff4-246">Cadena</span><span class="sxs-lookup"><span data-stu-id="38ff4-246">String</span></span>|
|<span data-ttu-id="38ff4-247">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="38ff4-247">**Possible values**</span></span>|<span data-ttu-id="38ff4-248">cualquier cadena</span><span class="sxs-lookup"><span data-stu-id="38ff4-248">any string</span></span>|
|<span data-ttu-id="38ff4-249">**Comments**</span><span class="sxs-lookup"><span data-stu-id="38ff4-249">**Comments**</span></span>|<span data-ttu-id="38ff4-250">Aplicable solo *si $type* *se excluyeFileName*</span><span class="sxs-lookup"><span data-stu-id="38ff4-250">Applicable only if *$type* is *excludedFileName*</span></span>|
|

#### <a name="allowed-threats"></a><span data-ttu-id="38ff4-251">Amenazas permitidas</span><span class="sxs-lookup"><span data-stu-id="38ff4-251">Allowed threats</span></span>

<span data-ttu-id="38ff4-252">Lista de amenazas (identificadas por su nombre) que no están bloqueadas por el producto y que en su lugar pueden ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="38ff4-252">List of threats (identified by their name) that are not blocked by the product and are instead allowed to run.</span></span>

<br>

****

|<span data-ttu-id="38ff4-253">Descripción</span><span class="sxs-lookup"><span data-stu-id="38ff4-253">Description</span></span>|<span data-ttu-id="38ff4-254">Valor</span><span class="sxs-lookup"><span data-stu-id="38ff4-254">Value</span></span>|
|---|---|
|<span data-ttu-id="38ff4-255">**Key**</span><span class="sxs-lookup"><span data-stu-id="38ff4-255">**Key**</span></span>|<span data-ttu-id="38ff4-256">allowedThreats</span><span class="sxs-lookup"><span data-stu-id="38ff4-256">allowedThreats</span></span>|
|<span data-ttu-id="38ff4-257">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="38ff4-257">**Data type**</span></span>|<span data-ttu-id="38ff4-258">Matriz de cadenas</span><span class="sxs-lookup"><span data-stu-id="38ff4-258">Array of strings</span></span>|
|

#### <a name="disallowed-threat-actions"></a><span data-ttu-id="38ff4-259">Acciones de amenazas no permitidos</span><span class="sxs-lookup"><span data-stu-id="38ff4-259">Disallowed threat actions</span></span>

<span data-ttu-id="38ff4-260">Restringe las acciones que el usuario local de un dispositivo puede realizar cuando se detectan amenazas.</span><span class="sxs-lookup"><span data-stu-id="38ff4-260">Restricts the actions that the local user of a device can take when threats are detected.</span></span> <span data-ttu-id="38ff4-261">Las acciones incluidas en esta lista no se muestran en la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="38ff4-261">The actions included in this list are not displayed in the user interface.</span></span>

<br>

****

|<span data-ttu-id="38ff4-262">Descripción</span><span class="sxs-lookup"><span data-stu-id="38ff4-262">Description</span></span>|<span data-ttu-id="38ff4-263">Valor</span><span class="sxs-lookup"><span data-stu-id="38ff4-263">Value</span></span>|
|---|---|
|<span data-ttu-id="38ff4-264">**Key**</span><span class="sxs-lookup"><span data-stu-id="38ff4-264">**Key**</span></span>|<span data-ttu-id="38ff4-265">disallowedThreatActions</span><span class="sxs-lookup"><span data-stu-id="38ff4-265">disallowedThreatActions</span></span>|
|<span data-ttu-id="38ff4-266">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="38ff4-266">**Data type**</span></span>|<span data-ttu-id="38ff4-267">Matriz de cadenas</span><span class="sxs-lookup"><span data-stu-id="38ff4-267">Array of strings</span></span>|
|<span data-ttu-id="38ff4-268">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="38ff4-268">**Possible values**</span></span>|<span data-ttu-id="38ff4-269">permitir (restringe a los usuarios permitir amenazas)</span><span class="sxs-lookup"><span data-stu-id="38ff4-269">allow (restricts users from allowing threats)</span></span> <p> <span data-ttu-id="38ff4-270">restore (restringe a los usuarios la restauración de amenazas desde la cuarentena)</span><span class="sxs-lookup"><span data-stu-id="38ff4-270">restore (restricts users from restoring threats from the quarantine)</span></span>|
|<span data-ttu-id="38ff4-271">**Comments**</span><span class="sxs-lookup"><span data-stu-id="38ff4-271">**Comments**</span></span>|<span data-ttu-id="38ff4-272">Disponible en Defender para endpoint versión 100.83.73 o posterior.</span><span class="sxs-lookup"><span data-stu-id="38ff4-272">Available in Defender for Endpoint version 100.83.73 or higher.</span></span>|
|

#### <a name="threat-type-settings"></a><span data-ttu-id="38ff4-273">Configuración del tipo de amenaza</span><span class="sxs-lookup"><span data-stu-id="38ff4-273">Threat type settings</span></span>

<span data-ttu-id="38ff4-274">La *preferencia threatTypeSettings* en el motor antivirus se usa para controlar cómo el producto controla determinados tipos de amenazas.</span><span class="sxs-lookup"><span data-stu-id="38ff4-274">The *threatTypeSettings* preference in the antivirus engine is used to control how certain threat types are handled by the product.</span></span>

<br>

****

|<span data-ttu-id="38ff4-275">Descripción</span><span class="sxs-lookup"><span data-stu-id="38ff4-275">Description</span></span>|<span data-ttu-id="38ff4-276">Valor</span><span class="sxs-lookup"><span data-stu-id="38ff4-276">Value</span></span>|
|---|---|
|<span data-ttu-id="38ff4-277">**Key**</span><span class="sxs-lookup"><span data-stu-id="38ff4-277">**Key**</span></span>|<span data-ttu-id="38ff4-278">threatTypeSettings</span><span class="sxs-lookup"><span data-stu-id="38ff4-278">threatTypeSettings</span></span>|
|<span data-ttu-id="38ff4-279">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="38ff4-279">**Data type**</span></span>|<span data-ttu-id="38ff4-280">Diccionario (preferencia anidada)</span><span class="sxs-lookup"><span data-stu-id="38ff4-280">Dictionary (nested preference)</span></span>|
|<span data-ttu-id="38ff4-281">**Comments**</span><span class="sxs-lookup"><span data-stu-id="38ff4-281">**Comments**</span></span>|<span data-ttu-id="38ff4-282">Vea las secciones siguientes para obtener una descripción del contenido del diccionario.</span><span class="sxs-lookup"><span data-stu-id="38ff4-282">See the following sections for a description of the dictionary contents.</span></span>|
|

##### <a name="threat-type"></a><span data-ttu-id="38ff4-283">Tipo de amenaza</span><span class="sxs-lookup"><span data-stu-id="38ff4-283">Threat type</span></span>

<span data-ttu-id="38ff4-284">Tipo de amenaza para la que se configura el comportamiento.</span><span class="sxs-lookup"><span data-stu-id="38ff4-284">Type of threat for which the behavior is configured.</span></span>

<br>

****

|<span data-ttu-id="38ff4-285">Descripción</span><span class="sxs-lookup"><span data-stu-id="38ff4-285">Description</span></span>|<span data-ttu-id="38ff4-286">Valor</span><span class="sxs-lookup"><span data-stu-id="38ff4-286">Value</span></span>|
|---|---|
|<span data-ttu-id="38ff4-287">**Key**</span><span class="sxs-lookup"><span data-stu-id="38ff4-287">**Key**</span></span>|<span data-ttu-id="38ff4-288">clave</span><span class="sxs-lookup"><span data-stu-id="38ff4-288">key</span></span>|
|<span data-ttu-id="38ff4-289">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="38ff4-289">**Data type**</span></span>|<span data-ttu-id="38ff4-290">Cadena</span><span class="sxs-lookup"><span data-stu-id="38ff4-290">String</span></span>|
|<span data-ttu-id="38ff4-291">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="38ff4-291">**Possible values**</span></span>|<span data-ttu-id="38ff4-292">potentially_unwanted_application</span><span class="sxs-lookup"><span data-stu-id="38ff4-292">potentially_unwanted_application</span></span> <p> <span data-ttu-id="38ff4-293">archive_bomb</span><span class="sxs-lookup"><span data-stu-id="38ff4-293">archive_bomb</span></span>|
|

##### <a name="action-to-take"></a><span data-ttu-id="38ff4-294">Acción que puede realizar</span><span class="sxs-lookup"><span data-stu-id="38ff4-294">Action to take</span></span>

<span data-ttu-id="38ff4-295">Acción que se debe realizar al encontrarse con una amenaza del tipo especificado en la sección anterior.</span><span class="sxs-lookup"><span data-stu-id="38ff4-295">Action to take when coming across a threat of the type specified in the preceding section.</span></span> <span data-ttu-id="38ff4-296">Puede ser:</span><span class="sxs-lookup"><span data-stu-id="38ff4-296">Can be:</span></span>

- <span data-ttu-id="38ff4-297">**Auditoría:** el dispositivo no está protegido contra este tipo de amenaza, pero se registra una entrada sobre la amenaza.</span><span class="sxs-lookup"><span data-stu-id="38ff4-297">**Audit**: The device is not protected against this type of threat, but an entry about the threat is logged.</span></span>
- <span data-ttu-id="38ff4-298">**Bloquear:** el dispositivo está protegido contra este tipo de amenaza y se te notificará en la consola de seguridad.</span><span class="sxs-lookup"><span data-stu-id="38ff4-298">**Block**: The device is protected against this type of threat and you are notified in the security console.</span></span>
- <span data-ttu-id="38ff4-299">**Desactivado:** el dispositivo no está protegido contra este tipo de amenaza y no se registra nada.</span><span class="sxs-lookup"><span data-stu-id="38ff4-299">**Off**: The device is not protected against this type of threat and nothing is logged.</span></span>

<br>

****

|<span data-ttu-id="38ff4-300">Descripción</span><span class="sxs-lookup"><span data-stu-id="38ff4-300">Description</span></span>|<span data-ttu-id="38ff4-301">Valor</span><span class="sxs-lookup"><span data-stu-id="38ff4-301">Value</span></span>|
|---|---|
|<span data-ttu-id="38ff4-302">**Key**</span><span class="sxs-lookup"><span data-stu-id="38ff4-302">**Key**</span></span>|<span data-ttu-id="38ff4-303">valor</span><span class="sxs-lookup"><span data-stu-id="38ff4-303">value</span></span>|
|<span data-ttu-id="38ff4-304">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="38ff4-304">**Data type**</span></span>|<span data-ttu-id="38ff4-305">Cadena</span><span class="sxs-lookup"><span data-stu-id="38ff4-305">String</span></span>|
|<span data-ttu-id="38ff4-306">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="38ff4-306">**Possible values**</span></span>|<span data-ttu-id="38ff4-307">auditoría (valor predeterminado)</span><span class="sxs-lookup"><span data-stu-id="38ff4-307">audit (default)</span></span> <p> <span data-ttu-id="38ff4-308">bloque</span><span class="sxs-lookup"><span data-stu-id="38ff4-308">block</span></span> <p> <span data-ttu-id="38ff4-309">off</span><span class="sxs-lookup"><span data-stu-id="38ff4-309">off</span></span>|
|

#### <a name="threat-type-settings-merge-policy"></a><span data-ttu-id="38ff4-310">Directiva de combinación de configuración de tipo de amenaza</span><span class="sxs-lookup"><span data-stu-id="38ff4-310">Threat type settings merge policy</span></span>

<span data-ttu-id="38ff4-311">Especifica la directiva de combinación para la configuración del tipo de amenaza.</span><span class="sxs-lookup"><span data-stu-id="38ff4-311">Specifies the merge policy for threat type settings.</span></span> <span data-ttu-id="38ff4-312">Puede ser una combinación de opciones definidas por el administrador y definidas por el usuario ( ) o solo opciones definidas `merge` por el administrador ( `admin_only` ).</span><span class="sxs-lookup"><span data-stu-id="38ff4-312">This can be a combination of administrator-defined and user-defined settings (`merge`) or only administrator-defined settings (`admin_only`).</span></span> <span data-ttu-id="38ff4-313">Esta configuración se puede usar para restringir que los usuarios locales definan su propia configuración para diferentes tipos de amenazas.</span><span class="sxs-lookup"><span data-stu-id="38ff4-313">This setting can be used to restrict local users from defining their own settings for different threat types.</span></span>

<br>

****

|<span data-ttu-id="38ff4-314">Descripción</span><span class="sxs-lookup"><span data-stu-id="38ff4-314">Description</span></span>|<span data-ttu-id="38ff4-315">Valor</span><span class="sxs-lookup"><span data-stu-id="38ff4-315">Value</span></span>|
|---|---|
|<span data-ttu-id="38ff4-316">**Key**</span><span class="sxs-lookup"><span data-stu-id="38ff4-316">**Key**</span></span>|<span data-ttu-id="38ff4-317">threatTypeSettingsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="38ff4-317">threatTypeSettingsMergePolicy</span></span>|
|<span data-ttu-id="38ff4-318">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="38ff4-318">**Data type**</span></span>|<span data-ttu-id="38ff4-319">Cadena</span><span class="sxs-lookup"><span data-stu-id="38ff4-319">String</span></span>|
|<span data-ttu-id="38ff4-320">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="38ff4-320">**Possible values**</span></span>|<span data-ttu-id="38ff4-321">merge (valor predeterminado)</span><span class="sxs-lookup"><span data-stu-id="38ff4-321">merge (default)</span></span> <p> <span data-ttu-id="38ff4-322">admin_only</span><span class="sxs-lookup"><span data-stu-id="38ff4-322">admin_only</span></span>|
|<span data-ttu-id="38ff4-323">**Comments**</span><span class="sxs-lookup"><span data-stu-id="38ff4-323">**Comments**</span></span>|<span data-ttu-id="38ff4-324">Disponible en Defender para endpoint versión 100.83.73 o posterior.</span><span class="sxs-lookup"><span data-stu-id="38ff4-324">Available in Defender for Endpoint version 100.83.73 or higher.</span></span>|
|

#### <a name="antivirus-scan-history-retention-in-days"></a><span data-ttu-id="38ff4-325">Retención del historial de examen antivirus (en días)</span><span class="sxs-lookup"><span data-stu-id="38ff4-325">Antivirus scan history retention (in days)</span></span>

<span data-ttu-id="38ff4-326">Especifica el número de días que los resultados se conservan en el historial de examen del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="38ff4-326">Specify the number of days that results are retained in the scan history on the device.</span></span> <span data-ttu-id="38ff4-327">Los resultados del examen antiguos se quitan del historial.</span><span class="sxs-lookup"><span data-stu-id="38ff4-327">Old scan results are removed from the history.</span></span> <span data-ttu-id="38ff4-328">Archivos antiguos en cuarentena que también se quitan del disco.</span><span class="sxs-lookup"><span data-stu-id="38ff4-328">Old quarantined files that are also removed from the disk.</span></span>

<br>

****

|<span data-ttu-id="38ff4-329">Descripción</span><span class="sxs-lookup"><span data-stu-id="38ff4-329">Description</span></span>|<span data-ttu-id="38ff4-330">Valor</span><span class="sxs-lookup"><span data-stu-id="38ff4-330">Value</span></span>|
|---|---|
|<span data-ttu-id="38ff4-331">**Key**</span><span class="sxs-lookup"><span data-stu-id="38ff4-331">**Key**</span></span>|<span data-ttu-id="38ff4-332">scanResultsRetentionDays</span><span class="sxs-lookup"><span data-stu-id="38ff4-332">scanResultsRetentionDays</span></span>|
|<span data-ttu-id="38ff4-333">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="38ff4-333">**Data type**</span></span>|<span data-ttu-id="38ff4-334">Cadena</span><span class="sxs-lookup"><span data-stu-id="38ff4-334">String</span></span>|
|<span data-ttu-id="38ff4-335">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="38ff4-335">**Possible values**</span></span>|<span data-ttu-id="38ff4-336">90 (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="38ff4-336">90 (default).</span></span> <span data-ttu-id="38ff4-337">Los valores permitidos van de 1 día a 180 días.</span><span class="sxs-lookup"><span data-stu-id="38ff4-337">Allowed values are from 1 day to 180 days.</span></span>|
|<span data-ttu-id="38ff4-338">**Comments**</span><span class="sxs-lookup"><span data-stu-id="38ff4-338">**Comments**</span></span>|<span data-ttu-id="38ff4-339">Disponible en Defender para endpoint versión 101.04.76 o posterior.</span><span class="sxs-lookup"><span data-stu-id="38ff4-339">Available in Defender for Endpoint version 101.04.76 or higher.</span></span>|
|

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a><span data-ttu-id="38ff4-340">Número máximo de elementos en el historial de examen antivirus</span><span class="sxs-lookup"><span data-stu-id="38ff4-340">Maximum number of items in the antivirus scan history</span></span>

<span data-ttu-id="38ff4-341">Especifique el número máximo de entradas que se deben conservar en el historial de examen.</span><span class="sxs-lookup"><span data-stu-id="38ff4-341">Specify the maximum number of entries to keep in the scan history.</span></span> <span data-ttu-id="38ff4-342">Las entradas incluyen todos los exámenes a petición realizados en el pasado y todas las detecciones de antivirus.</span><span class="sxs-lookup"><span data-stu-id="38ff4-342">Entries include all on-demand scans performed in the past and all antivirus detections.</span></span>

<br>

****

|<span data-ttu-id="38ff4-343">Descripción</span><span class="sxs-lookup"><span data-stu-id="38ff4-343">Description</span></span>|<span data-ttu-id="38ff4-344">Valor</span><span class="sxs-lookup"><span data-stu-id="38ff4-344">Value</span></span>|
|---|---|
|<span data-ttu-id="38ff4-345">**Key**</span><span class="sxs-lookup"><span data-stu-id="38ff4-345">**Key**</span></span>|<span data-ttu-id="38ff4-346">scanHistoryMaximumItems</span><span class="sxs-lookup"><span data-stu-id="38ff4-346">scanHistoryMaximumItems</span></span>|
|<span data-ttu-id="38ff4-347">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="38ff4-347">**Data type**</span></span>|<span data-ttu-id="38ff4-348">Cadena</span><span class="sxs-lookup"><span data-stu-id="38ff4-348">String</span></span>|
|<span data-ttu-id="38ff4-349">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="38ff4-349">**Possible values**</span></span>|<span data-ttu-id="38ff4-350">10000 (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="38ff4-350">10000 (default).</span></span> <span data-ttu-id="38ff4-351">Los valores permitidos van de 5000 elementos a 15000 elementos.</span><span class="sxs-lookup"><span data-stu-id="38ff4-351">Allowed values are from 5000 items to 15000 items.</span></span>|
|<span data-ttu-id="38ff4-352">**Comments**</span><span class="sxs-lookup"><span data-stu-id="38ff4-352">**Comments**</span></span>|<span data-ttu-id="38ff4-353">Disponible en Defender para endpoint versión 101.04.76 o posterior.</span><span class="sxs-lookup"><span data-stu-id="38ff4-353">Available in Defender for Endpoint version 101.04.76 or higher.</span></span>|
|

### <a name="cloud-delivered-protection-preferences"></a><span data-ttu-id="38ff4-354">Preferencias de protección entregadas en la nube</span><span class="sxs-lookup"><span data-stu-id="38ff4-354">Cloud-delivered protection preferences</span></span>

<span data-ttu-id="38ff4-355">La *entrada cloudService* en el perfil de configuración se usa para configurar la característica de protección controlada por la nube del producto.</span><span class="sxs-lookup"><span data-stu-id="38ff4-355">The *cloudService* entry in the configuration profile is used to configure the cloud-driven protection feature of the product.</span></span>

<br>

****

|<span data-ttu-id="38ff4-356">Descripción</span><span class="sxs-lookup"><span data-stu-id="38ff4-356">Description</span></span>|<span data-ttu-id="38ff4-357">Valor</span><span class="sxs-lookup"><span data-stu-id="38ff4-357">Value</span></span>|
|---|---|
|<span data-ttu-id="38ff4-358">**Key**</span><span class="sxs-lookup"><span data-stu-id="38ff4-358">**Key**</span></span>|<span data-ttu-id="38ff4-359">cloudService</span><span class="sxs-lookup"><span data-stu-id="38ff4-359">cloudService</span></span>|
|<span data-ttu-id="38ff4-360">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="38ff4-360">**Data type**</span></span>|<span data-ttu-id="38ff4-361">Diccionario (preferencia anidada)</span><span class="sxs-lookup"><span data-stu-id="38ff4-361">Dictionary (nested preference)</span></span>|
|<span data-ttu-id="38ff4-362">**Comments**</span><span class="sxs-lookup"><span data-stu-id="38ff4-362">**Comments**</span></span>|<span data-ttu-id="38ff4-363">Vea las secciones siguientes para obtener una descripción del contenido del diccionario.</span><span class="sxs-lookup"><span data-stu-id="38ff4-363">See the following sections for a description of the dictionary contents.</span></span>|
|

#### <a name="enable--disable-cloud-delivered-protection"></a><span data-ttu-id="38ff4-364">Habilitar o deshabilitar la protección de entrega en la nube</span><span class="sxs-lookup"><span data-stu-id="38ff4-364">Enable / disable cloud delivered protection</span></span>

<span data-ttu-id="38ff4-365">Determina si la protección entregada en la nube está habilitada en el dispositivo o no.</span><span class="sxs-lookup"><span data-stu-id="38ff4-365">Determines whether cloud-delivered protection is enabled on the device or not.</span></span> <span data-ttu-id="38ff4-366">Para mejorar la seguridad de los servicios, se recomienda mantener activada esta característica.</span><span class="sxs-lookup"><span data-stu-id="38ff4-366">To improve the security of your services, we recommend keeping this feature turned on.</span></span>

<br>

****

|<span data-ttu-id="38ff4-367">Descripción</span><span class="sxs-lookup"><span data-stu-id="38ff4-367">Description</span></span>|<span data-ttu-id="38ff4-368">Valor</span><span class="sxs-lookup"><span data-stu-id="38ff4-368">Value</span></span>|
|---|---|
|<span data-ttu-id="38ff4-369">**Key**</span><span class="sxs-lookup"><span data-stu-id="38ff4-369">**Key**</span></span>|<span data-ttu-id="38ff4-370">habilitado</span><span class="sxs-lookup"><span data-stu-id="38ff4-370">enabled</span></span>|
|<span data-ttu-id="38ff4-371">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="38ff4-371">**Data type**</span></span>|<span data-ttu-id="38ff4-372">Booleano</span><span class="sxs-lookup"><span data-stu-id="38ff4-372">Boolean</span></span>|
|<span data-ttu-id="38ff4-373">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="38ff4-373">**Possible values**</span></span>|<span data-ttu-id="38ff4-374">true (valor predeterminado)</span><span class="sxs-lookup"><span data-stu-id="38ff4-374">true (default)</span></span> <p> <span data-ttu-id="38ff4-375">false</span><span class="sxs-lookup"><span data-stu-id="38ff4-375">false</span></span>|
|

#### <a name="diagnostic-collection-level"></a><span data-ttu-id="38ff4-376">Nivel de colección de diagnóstico</span><span class="sxs-lookup"><span data-stu-id="38ff4-376">Diagnostic collection level</span></span>

<span data-ttu-id="38ff4-377">Los datos de diagnóstico se usan para mantener Defender for Endpoint seguro y actualizado, detectar, diagnosticar y corregir problemas y también realizar mejoras en el producto.</span><span class="sxs-lookup"><span data-stu-id="38ff4-377">Diagnostic data is used to keep Defender for Endpoint secure and up-to-date, detect, diagnose and fix problems, and also make product improvements.</span></span> <span data-ttu-id="38ff4-378">Esta configuración determina el nivel de diagnóstico enviado por el producto a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="38ff4-378">This setting determines the level of diagnostics sent by the product to Microsoft.</span></span>

<br>

****

|<span data-ttu-id="38ff4-379">Descripción</span><span class="sxs-lookup"><span data-stu-id="38ff4-379">Description</span></span>|<span data-ttu-id="38ff4-380">Valor</span><span class="sxs-lookup"><span data-stu-id="38ff4-380">Value</span></span>|
|---|---|
|<span data-ttu-id="38ff4-381">**Key**</span><span class="sxs-lookup"><span data-stu-id="38ff4-381">**Key**</span></span>|<span data-ttu-id="38ff4-382">diagnosticLevel</span><span class="sxs-lookup"><span data-stu-id="38ff4-382">diagnosticLevel</span></span>|
|<span data-ttu-id="38ff4-383">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="38ff4-383">**Data type**</span></span>|<span data-ttu-id="38ff4-384">Cadena</span><span class="sxs-lookup"><span data-stu-id="38ff4-384">String</span></span>|
|<span data-ttu-id="38ff4-385">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="38ff4-385">**Possible values**</span></span>|<span data-ttu-id="38ff4-386">opcional (predeterminado)</span><span class="sxs-lookup"><span data-stu-id="38ff4-386">optional (default)</span></span> <p> <span data-ttu-id="38ff4-387">necesario</span><span class="sxs-lookup"><span data-stu-id="38ff4-387">required</span></span>|
|

#### <a name="enable--disable-automatic-sample-submissions"></a><span data-ttu-id="38ff4-388">Habilitar o deshabilitar envíos de ejemplo automáticos</span><span class="sxs-lookup"><span data-stu-id="38ff4-388">Enable / disable automatic sample submissions</span></span>

<span data-ttu-id="38ff4-389">Determina si se envían muestras sospechosas (que probablemente contengan amenazas) a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="38ff4-389">Determines whether suspicious samples (that are likely to contain threats) are sent to Microsoft.</span></span> <span data-ttu-id="38ff4-390">Existen tres niveles para controlar el envío de muestra:</span><span class="sxs-lookup"><span data-stu-id="38ff4-390">There are three levels for controlling sample submission:</span></span>

- <span data-ttu-id="38ff4-391">**Ninguno:** no se envían muestras sospechosas a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="38ff4-391">**None**: no suspicious samples are submitted to Microsoft.</span></span>
- <span data-ttu-id="38ff4-392">**Caja fuerte:** solo se envían automáticamente muestras sospechosas que no contienen información de identificación personal (PII).</span><span class="sxs-lookup"><span data-stu-id="38ff4-392">**Safe**: only suspicious samples that do not contain personally identifiable information (PII) are submitted automatically.</span></span> <span data-ttu-id="38ff4-393">Este es el valor predeterminado para esta configuración.</span><span class="sxs-lookup"><span data-stu-id="38ff4-393">This is the default value for this setting.</span></span>
- <span data-ttu-id="38ff4-394">**All**: todas las muestras sospechosas se envían a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="38ff4-394">**All**: all suspicious samples are submitted to Microsoft.</span></span>

<br>

****

|<span data-ttu-id="38ff4-395">Descripción</span><span class="sxs-lookup"><span data-stu-id="38ff4-395">Description</span></span>|<span data-ttu-id="38ff4-396">Valor</span><span class="sxs-lookup"><span data-stu-id="38ff4-396">Value</span></span>|
|---|---|
|<span data-ttu-id="38ff4-397">**Key**</span><span class="sxs-lookup"><span data-stu-id="38ff4-397">**Key**</span></span>|<span data-ttu-id="38ff4-398">automaticSampleSubmissionConsent</span><span class="sxs-lookup"><span data-stu-id="38ff4-398">automaticSampleSubmissionConsent</span></span>|
|<span data-ttu-id="38ff4-399">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="38ff4-399">**Data type**</span></span>|<span data-ttu-id="38ff4-400">Cadena</span><span class="sxs-lookup"><span data-stu-id="38ff4-400">String</span></span>|
|<span data-ttu-id="38ff4-401">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="38ff4-401">**Possible values**</span></span>|<span data-ttu-id="38ff4-402">ninguno</span><span class="sxs-lookup"><span data-stu-id="38ff4-402">none</span></span> <p> <span data-ttu-id="38ff4-403">safe (valor predeterminado)</span><span class="sxs-lookup"><span data-stu-id="38ff4-403">safe (default)</span></span> <p> <span data-ttu-id="38ff4-404">all</span><span class="sxs-lookup"><span data-stu-id="38ff4-404">all</span></span>|
|

#### <a name="enable--disable-automatic-security-intelligence-updates"></a><span data-ttu-id="38ff4-405">Habilitar o deshabilitar actualizaciones automáticas de inteligencia de seguridad</span><span class="sxs-lookup"><span data-stu-id="38ff4-405">Enable / disable automatic security intelligence updates</span></span>

<span data-ttu-id="38ff4-406">Determina si las actualizaciones de inteligencia de seguridad se instalan automáticamente:</span><span class="sxs-lookup"><span data-stu-id="38ff4-406">Determines whether security intelligence updates are installed automatically:</span></span>

<br>

****

|<span data-ttu-id="38ff4-407">Descripción</span><span class="sxs-lookup"><span data-stu-id="38ff4-407">Description</span></span>|<span data-ttu-id="38ff4-408">Valor</span><span class="sxs-lookup"><span data-stu-id="38ff4-408">Value</span></span>|
|---|---|
|<span data-ttu-id="38ff4-409">**Key**</span><span class="sxs-lookup"><span data-stu-id="38ff4-409">**Key**</span></span>|<span data-ttu-id="38ff4-410">automaticDefinitionUpdateEnabled</span><span class="sxs-lookup"><span data-stu-id="38ff4-410">automaticDefinitionUpdateEnabled</span></span>|
|<span data-ttu-id="38ff4-411">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="38ff4-411">**Data type**</span></span>|<span data-ttu-id="38ff4-412">Booleano</span><span class="sxs-lookup"><span data-stu-id="38ff4-412">Boolean</span></span>|
|<span data-ttu-id="38ff4-413">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="38ff4-413">**Possible values**</span></span>|<span data-ttu-id="38ff4-414">true (valor predeterminado)</span><span class="sxs-lookup"><span data-stu-id="38ff4-414">true (default)</span></span> <p> <span data-ttu-id="38ff4-415">false</span><span class="sxs-lookup"><span data-stu-id="38ff4-415">false</span></span>|
|

## <a name="recommended-configuration-profile"></a><span data-ttu-id="38ff4-416">Perfil de configuración recomendado</span><span class="sxs-lookup"><span data-stu-id="38ff4-416">Recommended configuration profile</span></span>

<span data-ttu-id="38ff4-417">Para empezar, recomendamos el siguiente perfil de configuración para que la empresa aproveche todas las características de protección que proporciona Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="38ff4-417">To get started, we recommend the following configuration profile for your enterprise to take advantage of all protection features that Defender for Endpoint provides.</span></span>

<span data-ttu-id="38ff4-418">El siguiente perfil de configuración será:</span><span class="sxs-lookup"><span data-stu-id="38ff4-418">The following configuration profile will:</span></span>

- <span data-ttu-id="38ff4-419">Habilitar la protección en tiempo real (RTP)</span><span class="sxs-lookup"><span data-stu-id="38ff4-419">Enable real-time protection (RTP)</span></span>
- <span data-ttu-id="38ff4-420">Especifique cómo se controlan los siguientes tipos de amenazas:</span><span class="sxs-lookup"><span data-stu-id="38ff4-420">Specify how the following threat types are handled:</span></span>
  - <span data-ttu-id="38ff4-421">**Las aplicaciones potencialmente no deseadas (PUA)** están bloqueadas</span><span class="sxs-lookup"><span data-stu-id="38ff4-421">**Potentially unwanted applications (PUA)** are blocked</span></span>
  - <span data-ttu-id="38ff4-422">**Las bomba de archivo** (archivo con una tasa de compresión alta) se auditan en los registros del producto</span><span class="sxs-lookup"><span data-stu-id="38ff4-422">**Archive bombs** (file with a high compression rate) are audited to the product logs</span></span>
- <span data-ttu-id="38ff4-423">Habilitar actualizaciones automáticas de inteligencia de seguridad</span><span class="sxs-lookup"><span data-stu-id="38ff4-423">Enable automatic security intelligence updates</span></span>
- <span data-ttu-id="38ff4-424">Habilitar la protección proporcionada en la nube</span><span class="sxs-lookup"><span data-stu-id="38ff4-424">Enable cloud-delivered protection</span></span>
- <span data-ttu-id="38ff4-425">Habilitar el envío automático de muestra en `safe` el nivel</span><span class="sxs-lookup"><span data-stu-id="38ff4-425">Enable automatic sample submission at `safe` level</span></span>

### <a name="sample-profile"></a><span data-ttu-id="38ff4-426">Perfil de ejemplo</span><span class="sxs-lookup"><span data-stu-id="38ff4-426">Sample profile</span></span>

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
      "enabled":true,
      "proxy":"http://proxy.server:port/"
   }
}
```

## <a name="full-configuration-profile-example"></a><span data-ttu-id="38ff4-427">Ejemplo de perfil de configuración completa</span><span class="sxs-lookup"><span data-stu-id="38ff4-427">Full configuration profile example</span></span>

<span data-ttu-id="38ff4-428">El siguiente perfil de configuración contiene entradas para todas las opciones descritas en este documento y se puede usar para escenarios más avanzados en los que desea tener más control sobre el producto.</span><span class="sxs-lookup"><span data-stu-id="38ff4-428">The following configuration profile contains entries for all settings described in this document and can be used for more advanced scenarios where you want more control over the product.</span></span>

### <a name="full-profile"></a><span data-ttu-id="38ff4-429">Perfil completo</span><span class="sxs-lookup"><span data-stu-id="38ff4-429">Full profile</span></span>

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
            "path":"/run"
         },
         {
            "$type":"excludedPath",
            "isDirectory":true,
            "path":"/home/*/git"
         },
         {
            "$type":"excludedFileExtension",
            "extension":".pdf"
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
      "automaticDefinitionUpdateEnabled":true,
      "proxy": "http://proxy.server:port/"
   }
}
```

## <a name="configuration-profile-validation"></a><span data-ttu-id="38ff4-430">Validación de perfiles de configuración</span><span class="sxs-lookup"><span data-stu-id="38ff4-430">Configuration profile validation</span></span>

<span data-ttu-id="38ff4-431">El perfil de configuración debe ser un archivo con formato JSON válido.</span><span class="sxs-lookup"><span data-stu-id="38ff4-431">The configuration profile must be a valid JSON-formatted file.</span></span> <span data-ttu-id="38ff4-432">Hay varias herramientas que se pueden usar para comprobar esto.</span><span class="sxs-lookup"><span data-stu-id="38ff4-432">There are a number of tools that can be used to verify this.</span></span> <span data-ttu-id="38ff4-433">Por ejemplo, si has `python` instalado en el dispositivo:</span><span class="sxs-lookup"><span data-stu-id="38ff4-433">For example, if you have `python` installed on your device:</span></span>

```bash
python -m json.tool mdatp_managed.json
```

<span data-ttu-id="38ff4-434">Si el JSON está bien formado, el comando anterior lo devuelve al Terminal y devuelve un código de salida de `0` .</span><span class="sxs-lookup"><span data-stu-id="38ff4-434">If the JSON is well-formed, the above command outputs it back to the Terminal and returns an exit code of `0`.</span></span> <span data-ttu-id="38ff4-435">De lo contrario, se muestra un error que describe el problema y el comando devuelve un código de salida de `1` .</span><span class="sxs-lookup"><span data-stu-id="38ff4-435">Otherwise, an error that describes the issue is displayed and the command returns an exit code of `1`.</span></span>

## <a name="verifying-that-the-mdatp_managedjson-file-is-working-as-expected"></a><span data-ttu-id="38ff4-436">Comprobar que el archivo mdatp_managed.jsestá funcionando según lo esperado</span><span class="sxs-lookup"><span data-stu-id="38ff4-436">Verifying that the mdatp_managed.json file is working as expected</span></span>

<span data-ttu-id="38ff4-437">Para comprobar que el /etc/opt/microsoft/mdatp/managed/mdatp_managed.json funciona correctamente, debería ver "[administrado]" junto a esta configuración:</span><span class="sxs-lookup"><span data-stu-id="38ff4-437">To verify that your /etc/opt/microsoft/mdatp/managed/mdatp_managed.json is working properly, you should see "[managed]" next to these settings:</span></span>

- <span data-ttu-id="38ff4-438">cloud_enabled</span><span class="sxs-lookup"><span data-stu-id="38ff4-438">cloud_enabled</span></span>
- <span data-ttu-id="38ff4-439">cloud_automatic_sample_submission_consent</span><span class="sxs-lookup"><span data-stu-id="38ff4-439">cloud_automatic_sample_submission_consent</span></span>
- <span data-ttu-id="38ff4-440">passive_mode_enabled</span><span class="sxs-lookup"><span data-stu-id="38ff4-440">passive_mode_enabled</span></span>
- <span data-ttu-id="38ff4-441">real_time_protection_enabled</span><span class="sxs-lookup"><span data-stu-id="38ff4-441">real_time_protection_enabled</span></span>
- <span data-ttu-id="38ff4-442">automatic_definition_update_enabled</span><span class="sxs-lookup"><span data-stu-id="38ff4-442">automatic_definition_update_enabled</span></span>

> [!NOTE]
> <span data-ttu-id="38ff4-443">Para que mdatp_managed.jsse haga efectivo, no es necesario reiniciar el wdavdaemon.</span><span class="sxs-lookup"><span data-stu-id="38ff4-443">For the mdatp_managed.json to take effect, no restart of the wdavdaemon is required.</span></span>

## <a name="configuration-profile-deployment"></a><span data-ttu-id="38ff4-444">Implementación de perfiles de configuración</span><span class="sxs-lookup"><span data-stu-id="38ff4-444">Configuration profile deployment</span></span>

<span data-ttu-id="38ff4-445">Una vez que haya creado el perfil de configuración para su empresa, puede implementarlo a través de la herramienta de administración que usa su empresa.</span><span class="sxs-lookup"><span data-stu-id="38ff4-445">Once you've built the configuration profile for your enterprise, you can deploy it through the management tool that your enterprise is using.</span></span> <span data-ttu-id="38ff4-446">Defender para endpoint en Linux lee la configuración administrada del archivo */etc/opt/microsoft/mdatp/managed/mdatp_managed.json.*</span><span class="sxs-lookup"><span data-stu-id="38ff4-446">Defender for Endpoint on Linux reads the managed configuration from the */etc/opt/microsoft/mdatp/managed/mdatp_managed.json* file.</span></span>
