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
ms.openlocfilehash: 00f6bdac66ae286bf55a875599f7097b14b06cb3
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861556"
---
# <a name="set-preferences-for-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="d0525-104">Establecer preferencias para Microsoft Defender para endpoint en Linux</span><span class="sxs-lookup"><span data-stu-id="d0525-104">Set preferences for Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="d0525-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="d0525-105">**Applies to:**</span></span>
- [<span data-ttu-id="d0525-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="d0525-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="d0525-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d0525-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="d0525-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="d0525-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="d0525-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="d0525-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

>[!IMPORTANT]
><span data-ttu-id="d0525-110">Este tema contiene instrucciones sobre cómo establecer las preferencias de Defender para Endpoint en Linux en entornos empresariales.</span><span class="sxs-lookup"><span data-stu-id="d0525-110">This topic contains instructions for how to set preferences for Defender for Endpoint on Linux in enterprise environments.</span></span> <span data-ttu-id="d0525-111">Si estás interesado en configurar el producto en un dispositivo desde la línea de comandos, consulta [Recursos](linux-resources.md#configure-from-the-command-line).</span><span class="sxs-lookup"><span data-stu-id="d0525-111">If you are interested in configuring the product on a device from the command-line, see [Resources](linux-resources.md#configure-from-the-command-line).</span></span>

<span data-ttu-id="d0525-112">En entornos empresariales, Defender para Endpoint en Linux se puede administrar a través de un perfil de configuración.</span><span class="sxs-lookup"><span data-stu-id="d0525-112">In enterprise environments, Defender for Endpoint on Linux can be managed through a configuration profile.</span></span> <span data-ttu-id="d0525-113">Este perfil se implementa desde la herramienta de administración que prefiera.</span><span class="sxs-lookup"><span data-stu-id="d0525-113">This profile is deployed from the management tool of your choice.</span></span> <span data-ttu-id="d0525-114">Las preferencias administradas por la empresa tienen prioridad sobre las establecidas localmente en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d0525-114">Preferences managed by the enterprise take precedence over the ones set locally on the device.</span></span> <span data-ttu-id="d0525-115">En otras palabras, los usuarios de su empresa no pueden cambiar las preferencias que se establecen a través de este perfil de configuración.</span><span class="sxs-lookup"><span data-stu-id="d0525-115">In other words, users in your enterprise are not able to change preferences that are set through this configuration profile.</span></span>

<span data-ttu-id="d0525-116">En este artículo se describe la estructura de este perfil (incluido un perfil recomendado que puede usar para empezar) e instrucciones sobre cómo implementar el perfil.</span><span class="sxs-lookup"><span data-stu-id="d0525-116">This article describes the structure of this profile (including a recommended profile that you can use to get started) and instructions on how to deploy the profile.</span></span>

## <a name="configuration-profile-structure"></a><span data-ttu-id="d0525-117">Estructura de perfiles de configuración</span><span class="sxs-lookup"><span data-stu-id="d0525-117">Configuration profile structure</span></span>

<span data-ttu-id="d0525-118">El perfil de configuración es un archivo .json que consta de entradas identificadas por una clave (que indica el nombre de la preferencia), seguido de un valor, que depende de la naturaleza de la preferencia.</span><span class="sxs-lookup"><span data-stu-id="d0525-118">The configuration profile is a .json file that consists of entries identified by a key (which denotes the name of the preference), followed by a value, which depends on the nature of the preference.</span></span> <span data-ttu-id="d0525-119">Los valores pueden ser simples, como un valor numérico o complejos, como una lista anidada de preferencias.</span><span class="sxs-lookup"><span data-stu-id="d0525-119">Values can be simple, such as a numerical value, or complex, such as a nested list of preferences.</span></span>

<span data-ttu-id="d0525-120">Normalmente, se usa una herramienta de administración de configuración para insertar un archivo con el nombre ```mdatp_managed.json``` en la ubicación ```/etc/opt/microsoft/mdatp/managed/``` .</span><span class="sxs-lookup"><span data-stu-id="d0525-120">Typically, you would use a configuration management tool to push a file with the name ```mdatp_managed.json``` at the location ```/etc/opt/microsoft/mdatp/managed/```.</span></span>

<span data-ttu-id="d0525-121">El nivel superior del perfil de configuración incluye las preferencias de todo el producto y las entradas para las subáreas del producto, que se explican con más detalle en las secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="d0525-121">The top level of the configuration profile includes product-wide preferences and entries for subareas of the product, which are explained in more detail in the next sections.</span></span>

### <a name="antivirus-engine-preferences"></a><span data-ttu-id="d0525-122">Preferencias del motor antivirus</span><span class="sxs-lookup"><span data-stu-id="d0525-122">Antivirus engine preferences</span></span>

<span data-ttu-id="d0525-123">La *sección antivirusEngine* del perfil de configuración se usa para administrar las preferencias del componente antivirus del producto.</span><span class="sxs-lookup"><span data-stu-id="d0525-123">The *antivirusEngine* section of the configuration profile is used to manage the preferences of the antivirus component of the product.</span></span>

|||
|:---|:---|
| <span data-ttu-id="d0525-124">**Clave**</span><span class="sxs-lookup"><span data-stu-id="d0525-124">**Key**</span></span> | <span data-ttu-id="d0525-125">antivirusEngine</span><span class="sxs-lookup"><span data-stu-id="d0525-125">antivirusEngine</span></span> |
| <span data-ttu-id="d0525-126">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="d0525-126">**Data type**</span></span> | <span data-ttu-id="d0525-127">Diccionario (preferencia anidada)</span><span class="sxs-lookup"><span data-stu-id="d0525-127">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="d0525-128">**Comments**</span><span class="sxs-lookup"><span data-stu-id="d0525-128">**Comments**</span></span> | <span data-ttu-id="d0525-129">Vea las secciones siguientes para obtener una descripción del contenido del diccionario.</span><span class="sxs-lookup"><span data-stu-id="d0525-129">See the following sections for a description of the dictionary contents.</span></span> |
|||

#### <a name="enable--disable-real-time-protection"></a><span data-ttu-id="d0525-130">Habilitar o deshabilitar la protección en tiempo real</span><span class="sxs-lookup"><span data-stu-id="d0525-130">Enable / disable real-time protection</span></span>

<span data-ttu-id="d0525-131">Determina si la protección en tiempo real (examinar archivos a medida que se accede a ellos) está habilitada o no.</span><span class="sxs-lookup"><span data-stu-id="d0525-131">Determines whether real-time protection (scan files as they are accessed) is enabled or not.</span></span>

|||
|:---|:---|
| <span data-ttu-id="d0525-132">**Clave**</span><span class="sxs-lookup"><span data-stu-id="d0525-132">**Key**</span></span> | <span data-ttu-id="d0525-133">enableRealTimeProtection</span><span class="sxs-lookup"><span data-stu-id="d0525-133">enableRealTimeProtection</span></span> |
| <span data-ttu-id="d0525-134">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="d0525-134">**Data type**</span></span> | <span data-ttu-id="d0525-135">Booleano</span><span class="sxs-lookup"><span data-stu-id="d0525-135">Boolean</span></span> |
| <span data-ttu-id="d0525-136">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="d0525-136">**Possible values**</span></span> | <span data-ttu-id="d0525-137">true (valor predeterminado)</span><span class="sxs-lookup"><span data-stu-id="d0525-137">true (default)</span></span> <br/> <span data-ttu-id="d0525-138">false</span><span class="sxs-lookup"><span data-stu-id="d0525-138">false</span></span> |
|||

#### <a name="enable--disable-passive-mode"></a><span data-ttu-id="d0525-139">Habilitar o deshabilitar el modo pasivo</span><span class="sxs-lookup"><span data-stu-id="d0525-139">Enable / disable passive mode</span></span>

<span data-ttu-id="d0525-140">Determina si el motor antivirus se ejecuta en modo pasivo o no.</span><span class="sxs-lookup"><span data-stu-id="d0525-140">Determines whether the antivirus engine runs in passive mode or not.</span></span> <span data-ttu-id="d0525-141">En modo pasivo:</span><span class="sxs-lookup"><span data-stu-id="d0525-141">In passive mode:</span></span>
- <span data-ttu-id="d0525-142">La protección en tiempo real está desactivada.</span><span class="sxs-lookup"><span data-stu-id="d0525-142">Real-time protection is turned off.</span></span>
- <span data-ttu-id="d0525-143">El examen a petición está activado.</span><span class="sxs-lookup"><span data-stu-id="d0525-143">On-demand scanning is turned on.</span></span>
- <span data-ttu-id="d0525-144">La corrección automática de amenazas está desactivada.</span><span class="sxs-lookup"><span data-stu-id="d0525-144">Automatic threat remediation is turned off.</span></span>
- <span data-ttu-id="d0525-145">Las actualizaciones de inteligencia de seguridad están activadas.</span><span class="sxs-lookup"><span data-stu-id="d0525-145">Security intelligence updates are turned on.</span></span>
- <span data-ttu-id="d0525-146">El icono del menú Estado está oculto.</span><span class="sxs-lookup"><span data-stu-id="d0525-146">Status menu icon is hidden.</span></span>

|||
|:---|:---|
| <span data-ttu-id="d0525-147">**Clave**</span><span class="sxs-lookup"><span data-stu-id="d0525-147">**Key**</span></span> | <span data-ttu-id="d0525-148">passiveMode</span><span class="sxs-lookup"><span data-stu-id="d0525-148">passiveMode</span></span> |
| <span data-ttu-id="d0525-149">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="d0525-149">**Data type**</span></span> | <span data-ttu-id="d0525-150">Booleano</span><span class="sxs-lookup"><span data-stu-id="d0525-150">Boolean</span></span> |
| <span data-ttu-id="d0525-151">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="d0525-151">**Possible values**</span></span> | <span data-ttu-id="d0525-152">false (predeterminado)</span><span class="sxs-lookup"><span data-stu-id="d0525-152">false (default)</span></span> <br/> <span data-ttu-id="d0525-153">true</span><span class="sxs-lookup"><span data-stu-id="d0525-153">true</span></span> |
| <span data-ttu-id="d0525-154">**Comments**</span><span class="sxs-lookup"><span data-stu-id="d0525-154">**Comments**</span></span> | <span data-ttu-id="d0525-155">Disponible en Defender para endpoint versión 100.67.60 o posterior.</span><span class="sxs-lookup"><span data-stu-id="d0525-155">Available in Defender for Endpoint version 100.67.60 or higher.</span></span> |
|||

#### <a name="exclusion-merge-policy"></a><span data-ttu-id="d0525-156">Directiva de combinación de exclusión</span><span class="sxs-lookup"><span data-stu-id="d0525-156">Exclusion merge policy</span></span>

<span data-ttu-id="d0525-157">Especifica la directiva de combinación para exclusiones.</span><span class="sxs-lookup"><span data-stu-id="d0525-157">Specifies the merge policy for exclusions.</span></span> <span data-ttu-id="d0525-158">Puede ser una combinación de exclusiones definidas por el administrador y definidas por el usuario ( ) o solo `merge` exclusiones definidas por el administrador ( `admin_only` ).</span><span class="sxs-lookup"><span data-stu-id="d0525-158">It can be a combination of administrator-defined and user-defined exclusions (`merge`) or only administrator-defined exclusions (`admin_only`).</span></span> <span data-ttu-id="d0525-159">Esta configuración se puede usar para restringir que los usuarios locales definan sus propias exclusiones.</span><span class="sxs-lookup"><span data-stu-id="d0525-159">This setting can be used to restrict local users from defining their own exclusions.</span></span>

|||
|:---|:---|
| <span data-ttu-id="d0525-160">**Clave**</span><span class="sxs-lookup"><span data-stu-id="d0525-160">**Key**</span></span> | <span data-ttu-id="d0525-161">exclusionsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="d0525-161">exclusionsMergePolicy</span></span> |
| <span data-ttu-id="d0525-162">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="d0525-162">**Data type**</span></span> | <span data-ttu-id="d0525-163">Cadena</span><span class="sxs-lookup"><span data-stu-id="d0525-163">String</span></span> |
| <span data-ttu-id="d0525-164">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="d0525-164">**Possible values**</span></span> | <span data-ttu-id="d0525-165">merge (valor predeterminado)</span><span class="sxs-lookup"><span data-stu-id="d0525-165">merge (default)</span></span> <br/> <span data-ttu-id="d0525-166">admin_only</span><span class="sxs-lookup"><span data-stu-id="d0525-166">admin_only</span></span> |
| <span data-ttu-id="d0525-167">**Comments**</span><span class="sxs-lookup"><span data-stu-id="d0525-167">**Comments**</span></span> | <span data-ttu-id="d0525-168">Disponible en Defender para endpoint versión 100.83.73 o posterior.</span><span class="sxs-lookup"><span data-stu-id="d0525-168">Available in Defender for Endpoint version 100.83.73 or higher.</span></span> |
|||

#### <a name="scan-exclusions"></a><span data-ttu-id="d0525-169">Exclusiones de examen</span><span class="sxs-lookup"><span data-stu-id="d0525-169">Scan exclusions</span></span>

<span data-ttu-id="d0525-170">Entidades que se han excluido del examen.</span><span class="sxs-lookup"><span data-stu-id="d0525-170">Entities that have been excluded from the scan.</span></span> <span data-ttu-id="d0525-171">Las exclusiones se pueden especificar por rutas de acceso completas, extensiones o nombres de archivo.</span><span class="sxs-lookup"><span data-stu-id="d0525-171">Exclusions can be specified by full paths, extensions, or file names.</span></span>
<span data-ttu-id="d0525-172">(Las exclusiones se especifican como una matriz de elementos, el administrador puede especificar tantos elementos como sea necesario, en cualquier orden).</span><span class="sxs-lookup"><span data-stu-id="d0525-172">(Exclusions are specified as an array of items, administrator can specify as many elements as necessary, in any order.)</span></span>

|||
|:---|:---|
| <span data-ttu-id="d0525-173">**Clave**</span><span class="sxs-lookup"><span data-stu-id="d0525-173">**Key**</span></span> | <span data-ttu-id="d0525-174">exclusiones</span><span class="sxs-lookup"><span data-stu-id="d0525-174">exclusions</span></span> |
| <span data-ttu-id="d0525-175">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="d0525-175">**Data type**</span></span> | <span data-ttu-id="d0525-176">Diccionario (preferencia anidada)</span><span class="sxs-lookup"><span data-stu-id="d0525-176">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="d0525-177">**Comments**</span><span class="sxs-lookup"><span data-stu-id="d0525-177">**Comments**</span></span> | <span data-ttu-id="d0525-178">Vea las secciones siguientes para obtener una descripción del contenido del diccionario.</span><span class="sxs-lookup"><span data-stu-id="d0525-178">See the following sections for a description of the dictionary contents.</span></span> |
|||

<span data-ttu-id="d0525-179">**Tipo de exclusión**</span><span class="sxs-lookup"><span data-stu-id="d0525-179">**Type of exclusion**</span></span>

<span data-ttu-id="d0525-180">Especifica el tipo de contenido excluido del examen.</span><span class="sxs-lookup"><span data-stu-id="d0525-180">Specifies the type of content excluded from the scan.</span></span>

|||
|:---|:---|
| <span data-ttu-id="d0525-181">**Clave**</span><span class="sxs-lookup"><span data-stu-id="d0525-181">**Key**</span></span> | <span data-ttu-id="d0525-182">$type</span><span class="sxs-lookup"><span data-stu-id="d0525-182">$type</span></span> |
| <span data-ttu-id="d0525-183">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="d0525-183">**Data type**</span></span> | <span data-ttu-id="d0525-184">Cadena</span><span class="sxs-lookup"><span data-stu-id="d0525-184">String</span></span> |
| <span data-ttu-id="d0525-185">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="d0525-185">**Possible values**</span></span> | <span data-ttu-id="d0525-186">excludedPath</span><span class="sxs-lookup"><span data-stu-id="d0525-186">excludedPath</span></span> <br/> <span data-ttu-id="d0525-187">excludedFileExtension</span><span class="sxs-lookup"><span data-stu-id="d0525-187">excludedFileExtension</span></span> <br/> <span data-ttu-id="d0525-188">excludedFileName</span><span class="sxs-lookup"><span data-stu-id="d0525-188">excludedFileName</span></span> |
|||

<span data-ttu-id="d0525-189">**Ruta de acceso al contenido excluido**</span><span class="sxs-lookup"><span data-stu-id="d0525-189">**Path to excluded content**</span></span>

<span data-ttu-id="d0525-190">Se usa para excluir contenido del examen por ruta de acceso de archivo completa.</span><span class="sxs-lookup"><span data-stu-id="d0525-190">Used to exclude content from the scan by full file path.</span></span>

|||
|:---|:---|
| <span data-ttu-id="d0525-191">**Clave**</span><span class="sxs-lookup"><span data-stu-id="d0525-191">**Key**</span></span> | <span data-ttu-id="d0525-192">path</span><span class="sxs-lookup"><span data-stu-id="d0525-192">path</span></span> |
| <span data-ttu-id="d0525-193">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="d0525-193">**Data type**</span></span> | <span data-ttu-id="d0525-194">Cadena</span><span class="sxs-lookup"><span data-stu-id="d0525-194">String</span></span> |
| <span data-ttu-id="d0525-195">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="d0525-195">**Possible values**</span></span> | <span data-ttu-id="d0525-196">rutas de acceso válidas</span><span class="sxs-lookup"><span data-stu-id="d0525-196">valid paths</span></span> |
| <span data-ttu-id="d0525-197">**Comments**</span><span class="sxs-lookup"><span data-stu-id="d0525-197">**Comments**</span></span> | <span data-ttu-id="d0525-198">Aplicable solo *si $type* *se excluyePath*</span><span class="sxs-lookup"><span data-stu-id="d0525-198">Applicable only if *$type* is *excludedPath*</span></span> |
|||

<span data-ttu-id="d0525-199">**Tipo de ruta de acceso (archivo/directorio)**</span><span class="sxs-lookup"><span data-stu-id="d0525-199">**Path type (file / directory)**</span></span>

<span data-ttu-id="d0525-200">Indica si la *propiedad path* hace referencia a un archivo o directorio.</span><span class="sxs-lookup"><span data-stu-id="d0525-200">Indicates if the *path* property refers to a file or directory.</span></span>

|||
|:---|:---|
| <span data-ttu-id="d0525-201">**Clave**</span><span class="sxs-lookup"><span data-stu-id="d0525-201">**Key**</span></span> | <span data-ttu-id="d0525-202">isDirectory</span><span class="sxs-lookup"><span data-stu-id="d0525-202">isDirectory</span></span> |
| <span data-ttu-id="d0525-203">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="d0525-203">**Data type**</span></span> | <span data-ttu-id="d0525-204">Booleano</span><span class="sxs-lookup"><span data-stu-id="d0525-204">Boolean</span></span> |
| <span data-ttu-id="d0525-205">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="d0525-205">**Possible values**</span></span> | <span data-ttu-id="d0525-206">false (predeterminado)</span><span class="sxs-lookup"><span data-stu-id="d0525-206">false (default)</span></span> <br/> <span data-ttu-id="d0525-207">true</span><span class="sxs-lookup"><span data-stu-id="d0525-207">true</span></span> |
| <span data-ttu-id="d0525-208">**Comments**</span><span class="sxs-lookup"><span data-stu-id="d0525-208">**Comments**</span></span> | <span data-ttu-id="d0525-209">Aplicable solo *si $type* *se excluyePath*</span><span class="sxs-lookup"><span data-stu-id="d0525-209">Applicable only if *$type* is *excludedPath*</span></span> |
|||

<span data-ttu-id="d0525-210">**Extensión de archivo excluida del examen**</span><span class="sxs-lookup"><span data-stu-id="d0525-210">**File extension excluded from the scan**</span></span>

<span data-ttu-id="d0525-211">Se usa para excluir contenido del examen por extensión de archivo.</span><span class="sxs-lookup"><span data-stu-id="d0525-211">Used to exclude content from the scan by file extension.</span></span>

|||
|:---|:---|
| <span data-ttu-id="d0525-212">**Clave**</span><span class="sxs-lookup"><span data-stu-id="d0525-212">**Key**</span></span> | <span data-ttu-id="d0525-213">extensión</span><span class="sxs-lookup"><span data-stu-id="d0525-213">extension</span></span> |
| <span data-ttu-id="d0525-214">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="d0525-214">**Data type**</span></span> | <span data-ttu-id="d0525-215">Cadena</span><span class="sxs-lookup"><span data-stu-id="d0525-215">String</span></span> |
| <span data-ttu-id="d0525-216">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="d0525-216">**Possible values**</span></span> | <span data-ttu-id="d0525-217">extensiones de archivo válidas</span><span class="sxs-lookup"><span data-stu-id="d0525-217">valid file extensions</span></span> |
| <span data-ttu-id="d0525-218">**Comments**</span><span class="sxs-lookup"><span data-stu-id="d0525-218">**Comments**</span></span> | <span data-ttu-id="d0525-219">Aplicable solo *si $type* *se excluyeFileExtension*</span><span class="sxs-lookup"><span data-stu-id="d0525-219">Applicable only if *$type* is *excludedFileExtension*</span></span> |
|||

<span data-ttu-id="d0525-220">**Proceso excluido del examen**</span><span class="sxs-lookup"><span data-stu-id="d0525-220">**Process excluded from the scan**</span></span>

<span data-ttu-id="d0525-221">Especifica un proceso para el que se excluye toda la actividad de archivo del examen.</span><span class="sxs-lookup"><span data-stu-id="d0525-221">Specifies a process for which all file activity is excluded from scanning.</span></span> <span data-ttu-id="d0525-222">El proceso se puede especificar por su nombre (por ejemplo, ) o la ruta de acceso `cat` completa (por ejemplo, `/bin/cat` ).</span><span class="sxs-lookup"><span data-stu-id="d0525-222">The process can be specified either by its name (for example, `cat`) or full path (for example, `/bin/cat`).</span></span>

|||
|:---|:---|
| <span data-ttu-id="d0525-223">**Clave**</span><span class="sxs-lookup"><span data-stu-id="d0525-223">**Key**</span></span> | <span data-ttu-id="d0525-224">name</span><span class="sxs-lookup"><span data-stu-id="d0525-224">name</span></span> |
| <span data-ttu-id="d0525-225">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="d0525-225">**Data type**</span></span> | <span data-ttu-id="d0525-226">Cadena</span><span class="sxs-lookup"><span data-stu-id="d0525-226">String</span></span> |
| <span data-ttu-id="d0525-227">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="d0525-227">**Possible values**</span></span> | <span data-ttu-id="d0525-228">cualquier cadena</span><span class="sxs-lookup"><span data-stu-id="d0525-228">any string</span></span> |
| <span data-ttu-id="d0525-229">**Comments**</span><span class="sxs-lookup"><span data-stu-id="d0525-229">**Comments**</span></span> | <span data-ttu-id="d0525-230">Aplicable solo *si $type* *se excluyeFileName*</span><span class="sxs-lookup"><span data-stu-id="d0525-230">Applicable only if *$type* is *excludedFileName*</span></span> |
|||

#### <a name="allowed-threats"></a><span data-ttu-id="d0525-231">Amenazas permitidas</span><span class="sxs-lookup"><span data-stu-id="d0525-231">Allowed threats</span></span>

<span data-ttu-id="d0525-232">Lista de amenazas (identificadas por su nombre) que no están bloqueadas por el producto y que en su lugar pueden ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="d0525-232">List of threats (identified by their name) that are not blocked by the product and are instead allowed to run.</span></span>

|||
|:---|:---|
| <span data-ttu-id="d0525-233">**Clave**</span><span class="sxs-lookup"><span data-stu-id="d0525-233">**Key**</span></span> | <span data-ttu-id="d0525-234">allowedThreats</span><span class="sxs-lookup"><span data-stu-id="d0525-234">allowedThreats</span></span> |
| <span data-ttu-id="d0525-235">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="d0525-235">**Data type**</span></span> | <span data-ttu-id="d0525-236">Matriz de cadenas</span><span class="sxs-lookup"><span data-stu-id="d0525-236">Array of strings</span></span> |
|||

#### <a name="disallowed-threat-actions"></a><span data-ttu-id="d0525-237">Acciones de amenazas no permitidos</span><span class="sxs-lookup"><span data-stu-id="d0525-237">Disallowed threat actions</span></span>

<span data-ttu-id="d0525-238">Restringe las acciones que el usuario local de un dispositivo puede realizar cuando se detectan amenazas.</span><span class="sxs-lookup"><span data-stu-id="d0525-238">Restricts the actions that the local user of a device can take when threats are detected.</span></span> <span data-ttu-id="d0525-239">Las acciones incluidas en esta lista no se muestran en la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="d0525-239">The actions included in this list are not displayed in the user interface.</span></span>

|||
|:---|:---|
| <span data-ttu-id="d0525-240">**Clave**</span><span class="sxs-lookup"><span data-stu-id="d0525-240">**Key**</span></span> | <span data-ttu-id="d0525-241">disallowedThreatActions</span><span class="sxs-lookup"><span data-stu-id="d0525-241">disallowedThreatActions</span></span> |
| <span data-ttu-id="d0525-242">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="d0525-242">**Data type**</span></span> | <span data-ttu-id="d0525-243">Matriz de cadenas</span><span class="sxs-lookup"><span data-stu-id="d0525-243">Array of strings</span></span> |
| <span data-ttu-id="d0525-244">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="d0525-244">**Possible values**</span></span> | <span data-ttu-id="d0525-245">permitir (restringe a los usuarios permitir amenazas)</span><span class="sxs-lookup"><span data-stu-id="d0525-245">allow (restricts users from allowing threats)</span></span> <br/> <span data-ttu-id="d0525-246">restore (restringe a los usuarios la restauración de amenazas desde la cuarentena)</span><span class="sxs-lookup"><span data-stu-id="d0525-246">restore (restricts users from restoring threats from the quarantine)</span></span> |
| <span data-ttu-id="d0525-247">**Comments**</span><span class="sxs-lookup"><span data-stu-id="d0525-247">**Comments**</span></span> | <span data-ttu-id="d0525-248">Disponible en Defender para endpoint versión 100.83.73 o posterior.</span><span class="sxs-lookup"><span data-stu-id="d0525-248">Available in Defender for Endpoint version 100.83.73 or higher.</span></span> |
|||

#### <a name="threat-type-settings"></a><span data-ttu-id="d0525-249">Configuración del tipo de amenaza</span><span class="sxs-lookup"><span data-stu-id="d0525-249">Threat type settings</span></span>

<span data-ttu-id="d0525-250">La *preferencia threatTypeSettings* en el motor antivirus se usa para controlar cómo el producto controla determinados tipos de amenazas.</span><span class="sxs-lookup"><span data-stu-id="d0525-250">The *threatTypeSettings* preference in the antivirus engine is used to control how certain threat types are handled by the product.</span></span>

|||
|:---|:---|
| <span data-ttu-id="d0525-251">**Clave**</span><span class="sxs-lookup"><span data-stu-id="d0525-251">**Key**</span></span> | <span data-ttu-id="d0525-252">threatTypeSettings</span><span class="sxs-lookup"><span data-stu-id="d0525-252">threatTypeSettings</span></span> |
| <span data-ttu-id="d0525-253">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="d0525-253">**Data type**</span></span> | <span data-ttu-id="d0525-254">Diccionario (preferencia anidada)</span><span class="sxs-lookup"><span data-stu-id="d0525-254">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="d0525-255">**Comments**</span><span class="sxs-lookup"><span data-stu-id="d0525-255">**Comments**</span></span> | <span data-ttu-id="d0525-256">Vea las secciones siguientes para obtener una descripción del contenido del diccionario.</span><span class="sxs-lookup"><span data-stu-id="d0525-256">See the following sections for a description of the dictionary contents.</span></span> |
|||

<span data-ttu-id="d0525-257">**Tipo de amenaza**</span><span class="sxs-lookup"><span data-stu-id="d0525-257">**Threat type**</span></span>

<span data-ttu-id="d0525-258">Tipo de amenaza para la que se configura el comportamiento.</span><span class="sxs-lookup"><span data-stu-id="d0525-258">Type of threat for which the behavior is configured.</span></span>

|||
|:---|:---|
| <span data-ttu-id="d0525-259">**Clave**</span><span class="sxs-lookup"><span data-stu-id="d0525-259">**Key**</span></span> | <span data-ttu-id="d0525-260">clave</span><span class="sxs-lookup"><span data-stu-id="d0525-260">key</span></span> |
| <span data-ttu-id="d0525-261">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="d0525-261">**Data type**</span></span> | <span data-ttu-id="d0525-262">Cadena</span><span class="sxs-lookup"><span data-stu-id="d0525-262">String</span></span> |
| <span data-ttu-id="d0525-263">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="d0525-263">**Possible values**</span></span> | <span data-ttu-id="d0525-264">potentially_unwanted_application</span><span class="sxs-lookup"><span data-stu-id="d0525-264">potentially_unwanted_application</span></span> <br/> <span data-ttu-id="d0525-265">archive_bomb</span><span class="sxs-lookup"><span data-stu-id="d0525-265">archive_bomb</span></span> |
|||

<span data-ttu-id="d0525-266">**Acción que puede realizar**</span><span class="sxs-lookup"><span data-stu-id="d0525-266">**Action to take**</span></span>

<span data-ttu-id="d0525-267">Acción que se debe realizar al encontrarse con una amenaza del tipo especificado en la sección anterior.</span><span class="sxs-lookup"><span data-stu-id="d0525-267">Action to take when coming across a threat of the type specified in the preceding section.</span></span> <span data-ttu-id="d0525-268">Puede ser:</span><span class="sxs-lookup"><span data-stu-id="d0525-268">Can be:</span></span>

- <span data-ttu-id="d0525-269">**Auditoría:** el dispositivo no está protegido contra este tipo de amenaza, pero se registra una entrada sobre la amenaza.</span><span class="sxs-lookup"><span data-stu-id="d0525-269">**Audit**: The device is not protected against this type of threat, but an entry about the threat is logged.</span></span>
- <span data-ttu-id="d0525-270">**Bloquear:** el dispositivo está protegido contra este tipo de amenaza y se te notificará en la consola de seguridad.</span><span class="sxs-lookup"><span data-stu-id="d0525-270">**Block**: The device is protected against this type of threat and you are notified in the security console.</span></span>
- <span data-ttu-id="d0525-271">**Desactivado:** el dispositivo no está protegido contra este tipo de amenaza y no se registra nada.</span><span class="sxs-lookup"><span data-stu-id="d0525-271">**Off**: The device is not protected against this type of threat and nothing is logged.</span></span>

|||
|:---|:---|
| <span data-ttu-id="d0525-272">**Clave**</span><span class="sxs-lookup"><span data-stu-id="d0525-272">**Key**</span></span> | <span data-ttu-id="d0525-273">valor</span><span class="sxs-lookup"><span data-stu-id="d0525-273">value</span></span> |
| <span data-ttu-id="d0525-274">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="d0525-274">**Data type**</span></span> | <span data-ttu-id="d0525-275">Cadena</span><span class="sxs-lookup"><span data-stu-id="d0525-275">String</span></span> |
| <span data-ttu-id="d0525-276">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="d0525-276">**Possible values**</span></span> | <span data-ttu-id="d0525-277">auditoría (valor predeterminado)</span><span class="sxs-lookup"><span data-stu-id="d0525-277">audit (default)</span></span> <br/> <span data-ttu-id="d0525-278">bloque</span><span class="sxs-lookup"><span data-stu-id="d0525-278">block</span></span> <br/> <span data-ttu-id="d0525-279">off</span><span class="sxs-lookup"><span data-stu-id="d0525-279">off</span></span> |
|||

#### <a name="threat-type-settings-merge-policy"></a><span data-ttu-id="d0525-280">Directiva de combinación de configuración de tipo de amenaza</span><span class="sxs-lookup"><span data-stu-id="d0525-280">Threat type settings merge policy</span></span>

<span data-ttu-id="d0525-281">Especifica la directiva de combinación para la configuración del tipo de amenaza.</span><span class="sxs-lookup"><span data-stu-id="d0525-281">Specifies the merge policy for threat type settings.</span></span> <span data-ttu-id="d0525-282">Puede ser una combinación de opciones definidas por el administrador y definidas por el usuario ( ) o solo opciones definidas `merge` por el administrador ( `admin_only` ).</span><span class="sxs-lookup"><span data-stu-id="d0525-282">This can be a combination of administrator-defined and user-defined settings (`merge`) or only administrator-defined settings (`admin_only`).</span></span> <span data-ttu-id="d0525-283">Esta configuración se puede usar para restringir que los usuarios locales definan su propia configuración para diferentes tipos de amenazas.</span><span class="sxs-lookup"><span data-stu-id="d0525-283">This setting can be used to restrict local users from defining their own settings for different threat types.</span></span>

|||
|:---|:---|
| <span data-ttu-id="d0525-284">**Clave**</span><span class="sxs-lookup"><span data-stu-id="d0525-284">**Key**</span></span> | <span data-ttu-id="d0525-285">threatTypeSettingsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="d0525-285">threatTypeSettingsMergePolicy</span></span> |
| <span data-ttu-id="d0525-286">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="d0525-286">**Data type**</span></span> | <span data-ttu-id="d0525-287">Cadena</span><span class="sxs-lookup"><span data-stu-id="d0525-287">String</span></span> |
| <span data-ttu-id="d0525-288">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="d0525-288">**Possible values**</span></span> | <span data-ttu-id="d0525-289">merge (valor predeterminado)</span><span class="sxs-lookup"><span data-stu-id="d0525-289">merge (default)</span></span> <br/> <span data-ttu-id="d0525-290">admin_only</span><span class="sxs-lookup"><span data-stu-id="d0525-290">admin_only</span></span> |
| <span data-ttu-id="d0525-291">**Comments**</span><span class="sxs-lookup"><span data-stu-id="d0525-291">**Comments**</span></span> | <span data-ttu-id="d0525-292">Disponible en Defender para endpoint versión 100.83.73 o posterior.</span><span class="sxs-lookup"><span data-stu-id="d0525-292">Available in Defender for Endpoint version 100.83.73 or higher.</span></span> |
|||

#### <a name="antivirus-scan-history-retention-in-days"></a><span data-ttu-id="d0525-293">Retención del historial de examen antivirus (en días)</span><span class="sxs-lookup"><span data-stu-id="d0525-293">Antivirus scan history retention (in days)</span></span>

<span data-ttu-id="d0525-294">Especifica el número de días que los resultados se conservan en el historial de examen del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d0525-294">Specify the number of days that results are retained in the scan history on the device.</span></span> <span data-ttu-id="d0525-295">Los resultados del examen antiguos se quitan del historial.</span><span class="sxs-lookup"><span data-stu-id="d0525-295">Old scan results are removed from the history.</span></span> <span data-ttu-id="d0525-296">Archivos antiguos en cuarentena que también se quitan del disco.</span><span class="sxs-lookup"><span data-stu-id="d0525-296">Old quarantined files that are also removed from the disk.</span></span>

|||
|:---|:---|
| <span data-ttu-id="d0525-297">**Clave**</span><span class="sxs-lookup"><span data-stu-id="d0525-297">**Key**</span></span> | <span data-ttu-id="d0525-298">scanResultsRetentionDays</span><span class="sxs-lookup"><span data-stu-id="d0525-298">scanResultsRetentionDays</span></span> |
| <span data-ttu-id="d0525-299">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="d0525-299">**Data type**</span></span> | <span data-ttu-id="d0525-300">Cadena</span><span class="sxs-lookup"><span data-stu-id="d0525-300">String</span></span> |
| <span data-ttu-id="d0525-301">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="d0525-301">**Possible values**</span></span> | <span data-ttu-id="d0525-302">90 (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="d0525-302">90 (default).</span></span> <span data-ttu-id="d0525-303">Los valores permitidos van de 1 día a 180 días.</span><span class="sxs-lookup"><span data-stu-id="d0525-303">Allowed values are from 1 day to 180 days.</span></span> |
| <span data-ttu-id="d0525-304">**Comments**</span><span class="sxs-lookup"><span data-stu-id="d0525-304">**Comments**</span></span> | <span data-ttu-id="d0525-305">Disponible en Defender para endpoint versión 101.04.76 o posterior.</span><span class="sxs-lookup"><span data-stu-id="d0525-305">Available in Defender for Endpoint version 101.04.76 or higher.</span></span> |
|||

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a><span data-ttu-id="d0525-306">Número máximo de elementos en el historial de examen antivirus</span><span class="sxs-lookup"><span data-stu-id="d0525-306">Maximum number of items in the antivirus scan history</span></span>

<span data-ttu-id="d0525-307">Especifique el número máximo de entradas que se deben conservar en el historial de examen.</span><span class="sxs-lookup"><span data-stu-id="d0525-307">Specify the maximum number of entries to keep in the scan history.</span></span> <span data-ttu-id="d0525-308">Las entradas incluyen todos los exámenes a petición realizados en el pasado y todas las detecciones de antivirus.</span><span class="sxs-lookup"><span data-stu-id="d0525-308">Entries include all on-demand scans performed in the past and all antivirus detections.</span></span>

|||
|:---|:---|
| <span data-ttu-id="d0525-309">**Clave**</span><span class="sxs-lookup"><span data-stu-id="d0525-309">**Key**</span></span> | <span data-ttu-id="d0525-310">scanHistoryMaximumItems</span><span class="sxs-lookup"><span data-stu-id="d0525-310">scanHistoryMaximumItems</span></span> |
| <span data-ttu-id="d0525-311">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="d0525-311">**Data type**</span></span> | <span data-ttu-id="d0525-312">Cadena</span><span class="sxs-lookup"><span data-stu-id="d0525-312">String</span></span> |
| <span data-ttu-id="d0525-313">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="d0525-313">**Possible values**</span></span> | <span data-ttu-id="d0525-314">10000 (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="d0525-314">10000 (default).</span></span> <span data-ttu-id="d0525-315">Los valores permitidos van de 5000 elementos a 15000 elementos.</span><span class="sxs-lookup"><span data-stu-id="d0525-315">Allowed values are from 5000 items to 15000 items.</span></span> |
| <span data-ttu-id="d0525-316">**Comments**</span><span class="sxs-lookup"><span data-stu-id="d0525-316">**Comments**</span></span> | <span data-ttu-id="d0525-317">Disponible en Defender para endpoint versión 101.04.76 o posterior.</span><span class="sxs-lookup"><span data-stu-id="d0525-317">Available in Defender for Endpoint version 101.04.76 or higher.</span></span> |
|||

### <a name="cloud-delivered-protection-preferences"></a><span data-ttu-id="d0525-318">Preferencias de protección entregadas en la nube</span><span class="sxs-lookup"><span data-stu-id="d0525-318">Cloud-delivered protection preferences</span></span>

<span data-ttu-id="d0525-319">La *entrada cloudService* en el perfil de configuración se usa para configurar la característica de protección controlada por la nube del producto.</span><span class="sxs-lookup"><span data-stu-id="d0525-319">The *cloudService* entry in the configuration profile is used to configure the cloud-driven protection feature of the product.</span></span>

|||
|:---|:---|
| <span data-ttu-id="d0525-320">**Clave**</span><span class="sxs-lookup"><span data-stu-id="d0525-320">**Key**</span></span> | <span data-ttu-id="d0525-321">cloudService</span><span class="sxs-lookup"><span data-stu-id="d0525-321">cloudService</span></span> |
| <span data-ttu-id="d0525-322">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="d0525-322">**Data type**</span></span> | <span data-ttu-id="d0525-323">Diccionario (preferencia anidada)</span><span class="sxs-lookup"><span data-stu-id="d0525-323">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="d0525-324">**Comments**</span><span class="sxs-lookup"><span data-stu-id="d0525-324">**Comments**</span></span> | <span data-ttu-id="d0525-325">Vea las secciones siguientes para obtener una descripción del contenido del diccionario.</span><span class="sxs-lookup"><span data-stu-id="d0525-325">See the following sections for a description of the dictionary contents.</span></span> |
|||

#### <a name="enable--disable-cloud-delivered-protection"></a><span data-ttu-id="d0525-326">Habilitar o deshabilitar la protección de entrega en la nube</span><span class="sxs-lookup"><span data-stu-id="d0525-326">Enable / disable cloud delivered protection</span></span>

<span data-ttu-id="d0525-327">Determina si la protección entregada en la nube está habilitada en el dispositivo o no.</span><span class="sxs-lookup"><span data-stu-id="d0525-327">Determines whether cloud-delivered protection is enabled on the device or not.</span></span> <span data-ttu-id="d0525-328">Para mejorar la seguridad de los servicios, se recomienda mantener activada esta característica.</span><span class="sxs-lookup"><span data-stu-id="d0525-328">To improve the security of your services, we recommend keeping this feature turned on.</span></span>

|||
|:---|:---|
| <span data-ttu-id="d0525-329">**Clave**</span><span class="sxs-lookup"><span data-stu-id="d0525-329">**Key**</span></span> | <span data-ttu-id="d0525-330">habilitado</span><span class="sxs-lookup"><span data-stu-id="d0525-330">enabled</span></span> |
| <span data-ttu-id="d0525-331">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="d0525-331">**Data type**</span></span> | <span data-ttu-id="d0525-332">Booleano</span><span class="sxs-lookup"><span data-stu-id="d0525-332">Boolean</span></span> |
| <span data-ttu-id="d0525-333">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="d0525-333">**Possible values**</span></span> | <span data-ttu-id="d0525-334">true (valor predeterminado)</span><span class="sxs-lookup"><span data-stu-id="d0525-334">true (default)</span></span> <br/> <span data-ttu-id="d0525-335">false</span><span class="sxs-lookup"><span data-stu-id="d0525-335">false</span></span> |
|||

#### <a name="diagnostic-collection-level"></a><span data-ttu-id="d0525-336">Nivel de colección de diagnóstico</span><span class="sxs-lookup"><span data-stu-id="d0525-336">Diagnostic collection level</span></span>

<span data-ttu-id="d0525-337">Los datos de diagnóstico se usan para mantener Defender for Endpoint seguro y actualizado, detectar, diagnosticar y corregir problemas y también realizar mejoras en el producto.</span><span class="sxs-lookup"><span data-stu-id="d0525-337">Diagnostic data is used to keep Defender for Endpoint secure and up-to-date, detect, diagnose and fix problems, and also make product improvements.</span></span> <span data-ttu-id="d0525-338">Esta configuración determina el nivel de diagnóstico enviado por el producto a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d0525-338">This setting determines the level of diagnostics sent by the product to Microsoft.</span></span>

|||
|:---|:---|
| <span data-ttu-id="d0525-339">**Clave**</span><span class="sxs-lookup"><span data-stu-id="d0525-339">**Key**</span></span> | <span data-ttu-id="d0525-340">diagnosticLevel</span><span class="sxs-lookup"><span data-stu-id="d0525-340">diagnosticLevel</span></span> |
| <span data-ttu-id="d0525-341">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="d0525-341">**Data type**</span></span> | <span data-ttu-id="d0525-342">Cadena</span><span class="sxs-lookup"><span data-stu-id="d0525-342">String</span></span> |
| <span data-ttu-id="d0525-343">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="d0525-343">**Possible values**</span></span> | <span data-ttu-id="d0525-344">opcional (predeterminado)</span><span class="sxs-lookup"><span data-stu-id="d0525-344">optional (default)</span></span> <br/> <span data-ttu-id="d0525-345">necesario</span><span class="sxs-lookup"><span data-stu-id="d0525-345">required</span></span> |
|||

#### <a name="enable--disable-automatic-sample-submissions"></a><span data-ttu-id="d0525-346">Habilitar o deshabilitar envíos de ejemplo automáticos</span><span class="sxs-lookup"><span data-stu-id="d0525-346">Enable / disable automatic sample submissions</span></span>

<span data-ttu-id="d0525-347">Determina si se envían muestras sospechosas (que probablemente contengan amenazas) a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d0525-347">Determines whether suspicious samples (that are likely to contain threats) are sent to Microsoft.</span></span> <span data-ttu-id="d0525-348">Existen tres niveles para controlar el envío de muestra:</span><span class="sxs-lookup"><span data-stu-id="d0525-348">There are three levels for controlling sample submission:</span></span>

- <span data-ttu-id="d0525-349">**Ninguno:** no se envían muestras sospechosas a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d0525-349">**None**: no suspicious samples are submitted to Microsoft.</span></span>
- <span data-ttu-id="d0525-350">**Caja fuerte:** solo se envían automáticamente muestras sospechosas que no contienen información de identificación personal (PII).</span><span class="sxs-lookup"><span data-stu-id="d0525-350">**Safe**: only suspicious samples that do not contain personally identifiable information (PII) are submitted automatically.</span></span> <span data-ttu-id="d0525-351">Este es el valor predeterminado para esta configuración.</span><span class="sxs-lookup"><span data-stu-id="d0525-351">This is the default value for this setting.</span></span>
- <span data-ttu-id="d0525-352">**All**: todas las muestras sospechosas se envían a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d0525-352">**All**: all suspicious samples are submitted to Microsoft.</span></span>

|||
|:---|:---|
| <span data-ttu-id="d0525-353">**Clave**</span><span class="sxs-lookup"><span data-stu-id="d0525-353">**Key**</span></span> | <span data-ttu-id="d0525-354">automaticSampleSubmissionConsent</span><span class="sxs-lookup"><span data-stu-id="d0525-354">automaticSampleSubmissionConsent</span></span> |
| <span data-ttu-id="d0525-355">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="d0525-355">**Data type**</span></span> | <span data-ttu-id="d0525-356">Cadena</span><span class="sxs-lookup"><span data-stu-id="d0525-356">String</span></span> |
| <span data-ttu-id="d0525-357">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="d0525-357">**Possible values**</span></span> | <span data-ttu-id="d0525-358">ninguno</span><span class="sxs-lookup"><span data-stu-id="d0525-358">none</span></span> <br/> <span data-ttu-id="d0525-359">safe (valor predeterminado)</span><span class="sxs-lookup"><span data-stu-id="d0525-359">safe (default)</span></span> <br/> <span data-ttu-id="d0525-360">all</span><span class="sxs-lookup"><span data-stu-id="d0525-360">all</span></span> |
|||

#### <a name="enable--disable-automatic-security-intelligence-updates"></a><span data-ttu-id="d0525-361">Habilitar o deshabilitar actualizaciones automáticas de inteligencia de seguridad</span><span class="sxs-lookup"><span data-stu-id="d0525-361">Enable / disable automatic security intelligence updates</span></span>

<span data-ttu-id="d0525-362">Determina si las actualizaciones de inteligencia de seguridad se instalan automáticamente:</span><span class="sxs-lookup"><span data-stu-id="d0525-362">Determines whether security intelligence updates are installed automatically:</span></span>

|||
|:---|:---|
| <span data-ttu-id="d0525-363">**Clave**</span><span class="sxs-lookup"><span data-stu-id="d0525-363">**Key**</span></span> | <span data-ttu-id="d0525-364">automaticDefinitionUpdateEnabled</span><span class="sxs-lookup"><span data-stu-id="d0525-364">automaticDefinitionUpdateEnabled</span></span> |
| <span data-ttu-id="d0525-365">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="d0525-365">**Data type**</span></span> | <span data-ttu-id="d0525-366">Booleano</span><span class="sxs-lookup"><span data-stu-id="d0525-366">Boolean</span></span> |
| <span data-ttu-id="d0525-367">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="d0525-367">**Possible values**</span></span> | <span data-ttu-id="d0525-368">true (valor predeterminado)</span><span class="sxs-lookup"><span data-stu-id="d0525-368">true (default)</span></span> <br/> <span data-ttu-id="d0525-369">false</span><span class="sxs-lookup"><span data-stu-id="d0525-369">false</span></span> |
|||

## <a name="recommended-configuration-profile"></a><span data-ttu-id="d0525-370">Perfil de configuración recomendado</span><span class="sxs-lookup"><span data-stu-id="d0525-370">Recommended configuration profile</span></span>

<span data-ttu-id="d0525-371">Para empezar, recomendamos el siguiente perfil de configuración para que la empresa aproveche todas las características de protección que proporciona Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="d0525-371">To get started, we recommend the following configuration profile for your enterprise to take advantage of all protection features that Defender for Endpoint provides.</span></span>

<span data-ttu-id="d0525-372">El siguiente perfil de configuración será:</span><span class="sxs-lookup"><span data-stu-id="d0525-372">The following configuration profile will:</span></span>

- <span data-ttu-id="d0525-373">Habilitar la protección en tiempo real (RTP)</span><span class="sxs-lookup"><span data-stu-id="d0525-373">Enable real-time protection (RTP)</span></span>
- <span data-ttu-id="d0525-374">Especifique cómo se controlan los siguientes tipos de amenazas:</span><span class="sxs-lookup"><span data-stu-id="d0525-374">Specify how the following threat types are handled:</span></span>
  - <span data-ttu-id="d0525-375">**Las aplicaciones potencialmente no deseadas (PUA)** están bloqueadas</span><span class="sxs-lookup"><span data-stu-id="d0525-375">**Potentially unwanted applications (PUA)** are blocked</span></span>
  - <span data-ttu-id="d0525-376">**Las bomba de archivo** (archivo con una tasa de compresión alta) se auditan en los registros del producto</span><span class="sxs-lookup"><span data-stu-id="d0525-376">**Archive bombs** (file with a high compression rate) are audited to the product logs</span></span>
- <span data-ttu-id="d0525-377">Habilitar actualizaciones automáticas de inteligencia de seguridad</span><span class="sxs-lookup"><span data-stu-id="d0525-377">Enable automatic security intelligence updates</span></span>
- <span data-ttu-id="d0525-378">Habilitar la protección proporcionada en la nube</span><span class="sxs-lookup"><span data-stu-id="d0525-378">Enable cloud-delivered protection</span></span>
- <span data-ttu-id="d0525-379">Habilitar el envío automático de muestra en `safe` el nivel</span><span class="sxs-lookup"><span data-stu-id="d0525-379">Enable automatic sample submission at `safe` level</span></span>

### <a name="sample-profile"></a><span data-ttu-id="d0525-380">Perfil de ejemplo</span><span class="sxs-lookup"><span data-stu-id="d0525-380">Sample profile</span></span>

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

## <a name="full-configuration-profile-example"></a><span data-ttu-id="d0525-381">Ejemplo de perfil de configuración completa</span><span class="sxs-lookup"><span data-stu-id="d0525-381">Full configuration profile example</span></span>

<span data-ttu-id="d0525-382">El siguiente perfil de configuración contiene entradas para todas las opciones descritas en este documento y se puede usar para escenarios más avanzados en los que desea tener más control sobre el producto.</span><span class="sxs-lookup"><span data-stu-id="d0525-382">The following configuration profile contains entries for all settings described in this document and can be used for more advanced scenarios where you want more control over the product.</span></span>

### <a name="full-profile"></a><span data-ttu-id="d0525-383">Perfil completo</span><span class="sxs-lookup"><span data-stu-id="d0525-383">Full profile</span></span>

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

## <a name="configuration-profile-validation"></a><span data-ttu-id="d0525-384">Validación de perfiles de configuración</span><span class="sxs-lookup"><span data-stu-id="d0525-384">Configuration profile validation</span></span>

<span data-ttu-id="d0525-385">El perfil de configuración debe ser un archivo con formato JSON válido.</span><span class="sxs-lookup"><span data-stu-id="d0525-385">The configuration profile must be a valid JSON-formatted file.</span></span> <span data-ttu-id="d0525-386">Hay varias herramientas que se pueden usar para comprobar esto.</span><span class="sxs-lookup"><span data-stu-id="d0525-386">There are a number of tools that can be used to verify this.</span></span> <span data-ttu-id="d0525-387">Por ejemplo, si has `python` instalado en el dispositivo:</span><span class="sxs-lookup"><span data-stu-id="d0525-387">For example, if you have `python` installed on your device:</span></span>

```bash
python -m json.tool mdatp_managed.json
```

<span data-ttu-id="d0525-388">Si el JSON está bien formado, el comando anterior lo devuelve al Terminal y devuelve un código de salida de `0` .</span><span class="sxs-lookup"><span data-stu-id="d0525-388">If the JSON is well-formed, the above command outputs it back to the Terminal and returns an exit code of `0`.</span></span> <span data-ttu-id="d0525-389">De lo contrario, se muestra un error que describe el problema y el comando devuelve un código de salida de `1` .</span><span class="sxs-lookup"><span data-stu-id="d0525-389">Otherwise, an error that describes the issue is displayed and the command returns an exit code of `1`.</span></span>

## <a name="verifying-that-the-mdatp_managedjson-file-is-working-as-expected"></a><span data-ttu-id="d0525-390">Comprobar que el archivo mdatp_managed.jsestá funcionando según lo esperado</span><span class="sxs-lookup"><span data-stu-id="d0525-390">Verifying that the mdatp_managed.json file is working as expected</span></span>
<span data-ttu-id="d0525-391">Para comprobar que el /etc/opt/microsoft/mdatp/managed/mdatp_managed.json funciona correctamente, debería ver "[administrado]" junto a esta configuración:</span><span class="sxs-lookup"><span data-stu-id="d0525-391">To verify that your /etc/opt/microsoft/mdatp/managed/mdatp_managed.json is working properly, you should see "[managed]" next to these settings:</span></span>
- <span data-ttu-id="d0525-392">cloud_enabled</span><span class="sxs-lookup"><span data-stu-id="d0525-392">cloud_enabled</span></span>
- <span data-ttu-id="d0525-393">cloud_automatic_sample_submission_consent</span><span class="sxs-lookup"><span data-stu-id="d0525-393">cloud_automatic_sample_submission_consent</span></span>
- <span data-ttu-id="d0525-394">passice_mode_enabled</span><span class="sxs-lookup"><span data-stu-id="d0525-394">passice_mode_enabled</span></span>
- <span data-ttu-id="d0525-395">real_time_protection_enabled</span><span class="sxs-lookup"><span data-stu-id="d0525-395">real_time_protection_enabled</span></span>
- <span data-ttu-id="d0525-396">automatic_definition_update_enabled</span><span class="sxs-lookup"><span data-stu-id="d0525-396">automatic_definition_update_enabled</span></span>

> [!NOTE]
> <span data-ttu-id="d0525-397">Para que mdatp_managed.jsse haga efectivo, no es necesario reiniciar el wdavdaemon.</span><span class="sxs-lookup"><span data-stu-id="d0525-397">For the mdatp_managed.json to take effect, no restart of the wdavdaemon is required.</span></span>

## <a name="configuration-profile-deployment"></a><span data-ttu-id="d0525-398">Implementación de perfiles de configuración</span><span class="sxs-lookup"><span data-stu-id="d0525-398">Configuration profile deployment</span></span>

<span data-ttu-id="d0525-399">Una vez que haya creado el perfil de configuración para su empresa, puede implementarlo a través de la herramienta de administración que usa su empresa.</span><span class="sxs-lookup"><span data-stu-id="d0525-399">Once you've built the configuration profile for your enterprise, you can deploy it through the management tool that your enterprise is using.</span></span> <span data-ttu-id="d0525-400">Defender para endpoint en Linux lee la configuración administrada del archivo */etc/opt/microsoft/mdatp/managed/mdatp_managed.json.*</span><span class="sxs-lookup"><span data-stu-id="d0525-400">Defender for Endpoint on Linux reads the managed configuration from the */etc/opt/microsoft/mdatp/managed/mdatp_managed.json* file.</span></span>
