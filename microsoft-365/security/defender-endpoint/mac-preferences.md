---
title: Establecer preferencias para Microsoft Defender para Endpoint en Mac
description: Configurar MMicrosoft Defender para Endpoint en Mac en organizaciones empresariales.
keywords: microsoft, defender, Microsoft Defender para Endpoint, mac, management, preferences, enterprise, intune, jamf, macos, catalina, mojave, high sierra
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
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: b706cb8dbd43d545768c1c573021b5ef401e3c09
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2021
ms.locfileid: "52346407"
---
# <a name="set-preferences-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="f7553-104">Establecer preferencias para Microsoft Defender para endpoint en macOS</span><span class="sxs-lookup"><span data-stu-id="f7553-104">Set preferences for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f7553-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="f7553-105">**Applies to:**</span></span>

- [<span data-ttu-id="f7553-106">Microsoft Defender para punto de conexión en macOS</span><span class="sxs-lookup"><span data-stu-id="f7553-106">Microsoft Defender for Endpoint on macOS</span></span>](microsoft-defender-endpoint-mac.md)

>[!IMPORTANT]
><span data-ttu-id="f7553-107">Este artículo contiene instrucciones sobre cómo establecer las preferencias de Microsoft Defender para Endpoint en macOS en organizaciones empresariales.</span><span class="sxs-lookup"><span data-stu-id="f7553-107">This article contains instructions for how to set preferences for Microsoft Defender for Endpoint on macOS in enterprise organizations.</span></span> <span data-ttu-id="f7553-108">Para configurar Microsoft Defender para endpoint en macOS mediante la interfaz de línea de comandos, vea [Resources](mac-resources.md#configuring-from-the-command-line).</span><span class="sxs-lookup"><span data-stu-id="f7553-108">To configure Microsoft Defender for Endpoint on macOS using the command-line interface, see [Resources](mac-resources.md#configuring-from-the-command-line).</span></span>

## <a name="summary"></a><span data-ttu-id="f7553-109">Resumen</span><span class="sxs-lookup"><span data-stu-id="f7553-109">Summary</span></span>

<span data-ttu-id="f7553-110">En organizaciones empresariales, Microsoft Defender para Endpoint en macOS se puede administrar a través de un perfil de configuración que se implementa mediante una de varias herramientas de administración.</span><span class="sxs-lookup"><span data-stu-id="f7553-110">In enterprise organizations, Microsoft Defender for Endpoint on macOS can be managed through a configuration profile that is deployed by using one of several management tools.</span></span> <span data-ttu-id="f7553-111">Las preferencias administradas por el equipo de operaciones de seguridad tienen prioridad sobre las preferencias que se establecen localmente en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f7553-111">Preferences that are managed by your security operations team take precedence over preferences that are set locally on the device.</span></span> <span data-ttu-id="f7553-112">Cambiar las preferencias que se establecen a través del perfil de configuración requiere privilegios escalados y no está disponible para usuarios sin permisos administrativos.</span><span class="sxs-lookup"><span data-stu-id="f7553-112">Changing the preferences that are set through the configuration profile requires escalated privileges and is not available for users without administrative permissions.</span></span>

<span data-ttu-id="f7553-113">En este artículo se describe la estructura del perfil de configuración, se incluye un perfil recomendado que puede usar para empezar y se proporcionan instrucciones sobre cómo implementar el perfil.</span><span class="sxs-lookup"><span data-stu-id="f7553-113">This article describes the structure of the configuration profile, includes a recommended profile that you can use to get started, and provides instructions on how to deploy the profile.</span></span>

## <a name="configuration-profile-structure"></a><span data-ttu-id="f7553-114">Estructura de perfiles de configuración</span><span class="sxs-lookup"><span data-stu-id="f7553-114">Configuration profile structure</span></span>

<span data-ttu-id="f7553-115">El perfil de configuración es un *archivo .plist* que consta de entradas identificadas por una clave (que indica el nombre de la preferencia), seguido de un valor, que depende de la naturaleza de la preferencia.</span><span class="sxs-lookup"><span data-stu-id="f7553-115">The configuration profile is a *.plist* file that consists of entries identified by a key (which denotes the name of the preference), followed by a value, which depends on the nature of the preference.</span></span> <span data-ttu-id="f7553-116">Los valores pueden ser simples (como un valor numérico) o complejos, como una lista anidada de preferencias.</span><span class="sxs-lookup"><span data-stu-id="f7553-116">Values can either be simple (such as a numerical value) or complex, such as a nested list of preferences.</span></span>

>[!CAUTION]
><span data-ttu-id="f7553-117">El diseño del perfil de configuración depende de la consola de administración que se use.</span><span class="sxs-lookup"><span data-stu-id="f7553-117">The layout of the configuration profile depends on the management console that you are using.</span></span> <span data-ttu-id="f7553-118">Las secciones siguientes contienen ejemplos de perfiles de configuración para JAMF e Intune.</span><span class="sxs-lookup"><span data-stu-id="f7553-118">The following sections contain examples of configuration profiles for JAMF and Intune.</span></span>

<span data-ttu-id="f7553-119">El nivel superior del perfil de configuración incluye las preferencias de todo el producto y las entradas para las subáreas de Microsoft Defender para endpoint, que se explican con más detalle en las secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="f7553-119">The top level of the configuration profile includes product-wide preferences and entries for subareas of Microsoft Defender for Endpoint, which are explained in more detail in the next sections.</span></span>

### <a name="antivirus-engine-preferences"></a><span data-ttu-id="f7553-120">Preferencias del motor antivirus</span><span class="sxs-lookup"><span data-stu-id="f7553-120">Antivirus engine preferences</span></span>

<span data-ttu-id="f7553-121">La *sección antivirusEngine* del perfil de configuración se usa para administrar las preferencias del componente antivirus de Microsoft Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="f7553-121">The *antivirusEngine* section of the configuration profile is used to manage the preferences of the antivirus component of Microsoft Defender for Endpoint.</span></span>

|<span data-ttu-id="f7553-122">Sección</span><span class="sxs-lookup"><span data-stu-id="f7553-122">Section</span></span>|<span data-ttu-id="f7553-123">Valor</span><span class="sxs-lookup"><span data-stu-id="f7553-123">Value</span></span>|
|:---|:---|
| <span data-ttu-id="f7553-124">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="f7553-124">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="f7553-125">**Clave**</span><span class="sxs-lookup"><span data-stu-id="f7553-125">**Key**</span></span> | <span data-ttu-id="f7553-126">antivirusEngine</span><span class="sxs-lookup"><span data-stu-id="f7553-126">antivirusEngine</span></span> |
| <span data-ttu-id="f7553-127">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="f7553-127">**Data type**</span></span> | <span data-ttu-id="f7553-128">Diccionario (preferencia anidada)</span><span class="sxs-lookup"><span data-stu-id="f7553-128">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="f7553-129">**Comments**</span><span class="sxs-lookup"><span data-stu-id="f7553-129">**Comments**</span></span> | <span data-ttu-id="f7553-130">Vea las secciones siguientes para obtener una descripción del contenido del diccionario.</span><span class="sxs-lookup"><span data-stu-id="f7553-130">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="enable--disable-real-time-protection"></a><span data-ttu-id="f7553-131">Habilitar o deshabilitar la protección en tiempo real</span><span class="sxs-lookup"><span data-stu-id="f7553-131">Enable / disable real-time protection</span></span>

<span data-ttu-id="f7553-132">Especifique si se va a habilitar la protección en tiempo real, que examina los archivos a medida que se accede a ellos.</span><span class="sxs-lookup"><span data-stu-id="f7553-132">Specify whether to enable real-time protection, which scans files as they are accessed.</span></span>

|<span data-ttu-id="f7553-133">Sección</span><span class="sxs-lookup"><span data-stu-id="f7553-133">Section</span></span>|<span data-ttu-id="f7553-134">Valor</span><span class="sxs-lookup"><span data-stu-id="f7553-134">Value</span></span>|
|:---|:---|
| <span data-ttu-id="f7553-135">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="f7553-135">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="f7553-136">**Clave**</span><span class="sxs-lookup"><span data-stu-id="f7553-136">**Key**</span></span> | <span data-ttu-id="f7553-137">enableRealTimeProtection</span><span class="sxs-lookup"><span data-stu-id="f7553-137">enableRealTimeProtection</span></span> |
| <span data-ttu-id="f7553-138">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="f7553-138">**Data type**</span></span> | <span data-ttu-id="f7553-139">Booleano</span><span class="sxs-lookup"><span data-stu-id="f7553-139">Boolean</span></span> |
| <span data-ttu-id="f7553-140">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="f7553-140">**Possible values**</span></span> | <span data-ttu-id="f7553-141">true (valor predeterminado)</span><span class="sxs-lookup"><span data-stu-id="f7553-141">true (default)</span></span> <br/> <span data-ttu-id="f7553-142">false</span><span class="sxs-lookup"><span data-stu-id="f7553-142">false</span></span> |

#### <a name="enable--disable-passive-mode"></a><span data-ttu-id="f7553-143">Habilitar o deshabilitar el modo pasivo</span><span class="sxs-lookup"><span data-stu-id="f7553-143">Enable / disable passive mode</span></span>

<span data-ttu-id="f7553-144">Especifique si el motor antivirus se ejecuta en modo pasivo.</span><span class="sxs-lookup"><span data-stu-id="f7553-144">Specify whether the antivirus engine runs in passive mode.</span></span> <span data-ttu-id="f7553-145">El modo pasivo tiene las siguientes implicaciones:</span><span class="sxs-lookup"><span data-stu-id="f7553-145">Passive mode has the following implications:</span></span> 
- <span data-ttu-id="f7553-146">La protección en tiempo real está desactivada</span><span class="sxs-lookup"><span data-stu-id="f7553-146">Real-time protection is turned off</span></span>
- <span data-ttu-id="f7553-147">El examen a petición está activado</span><span class="sxs-lookup"><span data-stu-id="f7553-147">On-demand scanning is turned on</span></span>
- <span data-ttu-id="f7553-148">La corrección automática de amenazas está desactivada</span><span class="sxs-lookup"><span data-stu-id="f7553-148">Automatic threat remediation is turned off</span></span>
- <span data-ttu-id="f7553-149">Las actualizaciones de inteligencia de seguridad están activadas</span><span class="sxs-lookup"><span data-stu-id="f7553-149">Security intelligence updates are turned on</span></span>
- <span data-ttu-id="f7553-150">El icono del menú Estado está oculto</span><span class="sxs-lookup"><span data-stu-id="f7553-150">Status menu icon is hidden</span></span>

|<span data-ttu-id="f7553-151">Sección</span><span class="sxs-lookup"><span data-stu-id="f7553-151">Section</span></span>|<span data-ttu-id="f7553-152">Valor</span><span class="sxs-lookup"><span data-stu-id="f7553-152">Value</span></span>|
|:---|:---|
| <span data-ttu-id="f7553-153">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="f7553-153">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="f7553-154">**Clave**</span><span class="sxs-lookup"><span data-stu-id="f7553-154">**Key**</span></span> | <span data-ttu-id="f7553-155">passiveMode</span><span class="sxs-lookup"><span data-stu-id="f7553-155">passiveMode</span></span> |
| <span data-ttu-id="f7553-156">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="f7553-156">**Data type**</span></span> | <span data-ttu-id="f7553-157">Booleano</span><span class="sxs-lookup"><span data-stu-id="f7553-157">Boolean</span></span> |
| <span data-ttu-id="f7553-158">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="f7553-158">**Possible values**</span></span> | <span data-ttu-id="f7553-159">false (predeterminado)</span><span class="sxs-lookup"><span data-stu-id="f7553-159">false (default)</span></span> <br/> <span data-ttu-id="f7553-160">true</span><span class="sxs-lookup"><span data-stu-id="f7553-160">true</span></span> |
| <span data-ttu-id="f7553-161">**Comments**</span><span class="sxs-lookup"><span data-stu-id="f7553-161">**Comments**</span></span> | <span data-ttu-id="f7553-162">Disponible en Microsoft Defender para endpoint versión 100.67.60 o posterior.</span><span class="sxs-lookup"><span data-stu-id="f7553-162">Available in Microsoft Defender for Endpoint version 100.67.60 or higher.</span></span> |

#### <a name="exclusion-merge-policy"></a><span data-ttu-id="f7553-163">Directiva de combinación de exclusión</span><span class="sxs-lookup"><span data-stu-id="f7553-163">Exclusion merge policy</span></span>

<span data-ttu-id="f7553-164">Especifique la directiva de combinación para exclusiones.</span><span class="sxs-lookup"><span data-stu-id="f7553-164">Specify the merge policy for exclusions.</span></span> <span data-ttu-id="f7553-165">Puede ser una combinación de exclusiones definidas por el administrador y definidas por el usuario ( ) o solo `merge` exclusiones definidas por el administrador ( `admin_only` ).</span><span class="sxs-lookup"><span data-stu-id="f7553-165">This can be a combination of administrator-defined and user-defined exclusions (`merge`) or only administrator-defined exclusions (`admin_only`).</span></span> <span data-ttu-id="f7553-166">Esta configuración se puede usar para restringir que los usuarios locales definan sus propias exclusiones.</span><span class="sxs-lookup"><span data-stu-id="f7553-166">This setting can be used to restrict local users from defining their own exclusions.</span></span>

|<span data-ttu-id="f7553-167">Sección</span><span class="sxs-lookup"><span data-stu-id="f7553-167">Section</span></span>|<span data-ttu-id="f7553-168">Valor</span><span class="sxs-lookup"><span data-stu-id="f7553-168">Value</span></span>|
|:---|:---|
| <span data-ttu-id="f7553-169">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="f7553-169">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="f7553-170">**Clave**</span><span class="sxs-lookup"><span data-stu-id="f7553-170">**Key**</span></span> | <span data-ttu-id="f7553-171">exclusionsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="f7553-171">exclusionsMergePolicy</span></span> |
| <span data-ttu-id="f7553-172">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="f7553-172">**Data type**</span></span> | <span data-ttu-id="f7553-173">Cadena</span><span class="sxs-lookup"><span data-stu-id="f7553-173">String</span></span> |
| <span data-ttu-id="f7553-174">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="f7553-174">**Possible values**</span></span> | <span data-ttu-id="f7553-175">merge (valor predeterminado)</span><span class="sxs-lookup"><span data-stu-id="f7553-175">merge (default)</span></span> <br/> <span data-ttu-id="f7553-176">admin_only</span><span class="sxs-lookup"><span data-stu-id="f7553-176">admin_only</span></span> |
| <span data-ttu-id="f7553-177">**Comments**</span><span class="sxs-lookup"><span data-stu-id="f7553-177">**Comments**</span></span> | <span data-ttu-id="f7553-178">Disponible en Microsoft Defender para endpoint versión 100.83.73 o posterior.</span><span class="sxs-lookup"><span data-stu-id="f7553-178">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="scan-exclusions"></a><span data-ttu-id="f7553-179">Exclusiones de examen</span><span class="sxs-lookup"><span data-stu-id="f7553-179">Scan exclusions</span></span>

<span data-ttu-id="f7553-180">Especifique las entidades que no se han analizado.</span><span class="sxs-lookup"><span data-stu-id="f7553-180">Specify entities excluded from being scanned.</span></span> <span data-ttu-id="f7553-181">Las exclusiones se pueden especificar por rutas de acceso completas, extensiones o nombres de archivo.</span><span class="sxs-lookup"><span data-stu-id="f7553-181">Exclusions can be specified by full paths, extensions, or file names.</span></span>
<span data-ttu-id="f7553-182">(Las exclusiones se especifican como una matriz de elementos, el administrador puede especificar tantos elementos como sea necesario, en cualquier orden).</span><span class="sxs-lookup"><span data-stu-id="f7553-182">(Exclusions are specified as an array of items, administrator can specify as many elements as necessary, in any order.)</span></span>

|<span data-ttu-id="f7553-183">Sección</span><span class="sxs-lookup"><span data-stu-id="f7553-183">Section</span></span>|<span data-ttu-id="f7553-184">Valor</span><span class="sxs-lookup"><span data-stu-id="f7553-184">Value</span></span>|
|:---|:---|
| <span data-ttu-id="f7553-185">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="f7553-185">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="f7553-186">**Clave**</span><span class="sxs-lookup"><span data-stu-id="f7553-186">**Key**</span></span> | <span data-ttu-id="f7553-187">exclusiones</span><span class="sxs-lookup"><span data-stu-id="f7553-187">exclusions</span></span> |
| <span data-ttu-id="f7553-188">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="f7553-188">**Data type**</span></span> | <span data-ttu-id="f7553-189">Diccionario (preferencia anidada)</span><span class="sxs-lookup"><span data-stu-id="f7553-189">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="f7553-190">**Comments**</span><span class="sxs-lookup"><span data-stu-id="f7553-190">**Comments**</span></span> | <span data-ttu-id="f7553-191">Vea las secciones siguientes para obtener una descripción del contenido del diccionario.</span><span class="sxs-lookup"><span data-stu-id="f7553-191">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="type-of-exclusion"></a><span data-ttu-id="f7553-192">Tipo de exclusión</span><span class="sxs-lookup"><span data-stu-id="f7553-192">Type of exclusion</span></span>

<span data-ttu-id="f7553-193">Especifique el contenido excluido de ser examinado por tipo.</span><span class="sxs-lookup"><span data-stu-id="f7553-193">Specify content excluded from being scanned by type.</span></span>

|<span data-ttu-id="f7553-194">Sección</span><span class="sxs-lookup"><span data-stu-id="f7553-194">Section</span></span>|<span data-ttu-id="f7553-195">Valor</span><span class="sxs-lookup"><span data-stu-id="f7553-195">Value</span></span>|
|:---|:---|
| <span data-ttu-id="f7553-196">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="f7553-196">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="f7553-197">**Clave**</span><span class="sxs-lookup"><span data-stu-id="f7553-197">**Key**</span></span> | <span data-ttu-id="f7553-198">$type</span><span class="sxs-lookup"><span data-stu-id="f7553-198">$type</span></span> |
| <span data-ttu-id="f7553-199">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="f7553-199">**Data type**</span></span> | <span data-ttu-id="f7553-200">Cadena</span><span class="sxs-lookup"><span data-stu-id="f7553-200">String</span></span> |
| <span data-ttu-id="f7553-201">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="f7553-201">**Possible values**</span></span> | <span data-ttu-id="f7553-202">excludedPath</span><span class="sxs-lookup"><span data-stu-id="f7553-202">excludedPath</span></span> <br/> <span data-ttu-id="f7553-203">excludedFileExtension</span><span class="sxs-lookup"><span data-stu-id="f7553-203">excludedFileExtension</span></span> <br/> <span data-ttu-id="f7553-204">excludedFileName</span><span class="sxs-lookup"><span data-stu-id="f7553-204">excludedFileName</span></span> |

##### <a name="path-to-excluded-content"></a><span data-ttu-id="f7553-205">Ruta de acceso al contenido excluido</span><span class="sxs-lookup"><span data-stu-id="f7553-205">Path to excluded content</span></span>

<span data-ttu-id="f7553-206">Especifique el contenido excluido de ser examinado por la ruta de acceso de archivo completa.</span><span class="sxs-lookup"><span data-stu-id="f7553-206">Specify content excluded from being scanned by full file path.</span></span>

|<span data-ttu-id="f7553-207">Sección</span><span class="sxs-lookup"><span data-stu-id="f7553-207">Section</span></span>|<span data-ttu-id="f7553-208">Valor</span><span class="sxs-lookup"><span data-stu-id="f7553-208">Value</span></span>|
|:---|:---|
| <span data-ttu-id="f7553-209">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="f7553-209">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="f7553-210">**Clave**</span><span class="sxs-lookup"><span data-stu-id="f7553-210">**Key**</span></span> | <span data-ttu-id="f7553-211">path</span><span class="sxs-lookup"><span data-stu-id="f7553-211">path</span></span> |
| <span data-ttu-id="f7553-212">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="f7553-212">**Data type**</span></span> | <span data-ttu-id="f7553-213">Cadena</span><span class="sxs-lookup"><span data-stu-id="f7553-213">String</span></span> |
| <span data-ttu-id="f7553-214">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="f7553-214">**Possible values**</span></span> | <span data-ttu-id="f7553-215">rutas de acceso válidas</span><span class="sxs-lookup"><span data-stu-id="f7553-215">valid paths</span></span> |
| <span data-ttu-id="f7553-216">**Comments**</span><span class="sxs-lookup"><span data-stu-id="f7553-216">**Comments**</span></span> | <span data-ttu-id="f7553-217">Aplicable solo *si $type* *se excluyePath*</span><span class="sxs-lookup"><span data-stu-id="f7553-217">Applicable only if *$type* is *excludedPath*</span></span> |

## <a name="supported-exclusion-types"></a><span data-ttu-id="f7553-218">Tipos de exclusión admitidos</span><span class="sxs-lookup"><span data-stu-id="f7553-218">Supported exclusion types</span></span>

<span data-ttu-id="f7553-219">En la tabla siguiente se muestran los tipos de exclusión admitidos por Defender para Endpoint en Mac.</span><span class="sxs-lookup"><span data-stu-id="f7553-219">The follow table shows the exclusion types supported by Defender for Endpoint on Mac.</span></span>

<span data-ttu-id="f7553-220">Exclusión</span><span class="sxs-lookup"><span data-stu-id="f7553-220">Exclusion</span></span> | <span data-ttu-id="f7553-221">Definición</span><span class="sxs-lookup"><span data-stu-id="f7553-221">Definition</span></span> | <span data-ttu-id="f7553-222">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="f7553-222">Examples</span></span>
---|---|---
<span data-ttu-id="f7553-223">Extensión de archivo</span><span class="sxs-lookup"><span data-stu-id="f7553-223">File extension</span></span> | <span data-ttu-id="f7553-224">Todos los archivos con la extensión, en cualquier lugar del dispositivo</span><span class="sxs-lookup"><span data-stu-id="f7553-224">All files with the extension, anywhere on the device</span></span> | `.test`
<span data-ttu-id="f7553-225">Archivo</span><span class="sxs-lookup"><span data-stu-id="f7553-225">File</span></span> | <span data-ttu-id="f7553-226">Un archivo específico identificado por la ruta de acceso completa</span><span class="sxs-lookup"><span data-stu-id="f7553-226">A specific file identified by the full path</span></span> | `/var/log/test.log`<br/>`/var/log/*.log`<br/>`/var/log/install.?.log`
<span data-ttu-id="f7553-227">Carpeta</span><span class="sxs-lookup"><span data-stu-id="f7553-227">Folder</span></span> | <span data-ttu-id="f7553-228">Todos los archivos de la carpeta especificada (recursivamente)</span><span class="sxs-lookup"><span data-stu-id="f7553-228">All files under the specified folder (recursively)</span></span> | `/var/log/`<br/>`/var/*/`
<span data-ttu-id="f7553-229">Proceso</span><span class="sxs-lookup"><span data-stu-id="f7553-229">Process</span></span> | <span data-ttu-id="f7553-230">Un proceso específico (especificado por la ruta de acceso completa o el nombre de archivo) y todos los archivos abiertos por él</span><span class="sxs-lookup"><span data-stu-id="f7553-230">A specific process (specified either by the full path or file name) and all files opened by it</span></span> | `/bin/cat`<br/>`cat`<br/>`c?t`

> [!IMPORTANT]
> <span data-ttu-id="f7553-231">Las rutas anteriores deben ser vínculos duros, no vínculos simbólicos, para poder excluirse correctamente.</span><span class="sxs-lookup"><span data-stu-id="f7553-231">The paths above must be hard links, not symbolic links, in order to be successfully excluded.</span></span> <span data-ttu-id="f7553-232">Puede comprobar si una ruta de acceso es un vínculo simbólico ejecutando `file <path-name>` .</span><span class="sxs-lookup"><span data-stu-id="f7553-232">You can check if a path is a symbolic link by running `file <path-name>`.</span></span>

<span data-ttu-id="f7553-233">Las exclusiones de archivos, carpetas y procesos admiten los siguientes caracteres comodín:</span><span class="sxs-lookup"><span data-stu-id="f7553-233">File, folder, and process exclusions support the following wildcards:</span></span>

<span data-ttu-id="f7553-234">Carácter comodín</span><span class="sxs-lookup"><span data-stu-id="f7553-234">Wildcard</span></span> | <span data-ttu-id="f7553-235">Descripción</span><span class="sxs-lookup"><span data-stu-id="f7553-235">Description</span></span> | <span data-ttu-id="f7553-236">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f7553-236">Example</span></span> | <span data-ttu-id="f7553-237">Coincidencias</span><span class="sxs-lookup"><span data-stu-id="f7553-237">Matches</span></span> | <span data-ttu-id="f7553-238">No coincide</span><span class="sxs-lookup"><span data-stu-id="f7553-238">Does not match</span></span>
---|---|---|---|---
\* |    <span data-ttu-id="f7553-239">Coincide con cualquier número de caracteres, incluido ninguno (tenga en cuenta que cuando se usa este comodín dentro de una ruta de acceso, solo sustituirá una carpeta)</span><span class="sxs-lookup"><span data-stu-id="f7553-239">Matches any number of any characters including none (note that when this wildcard is used inside a path it will substitute only one folder)</span></span> | `/var/\*/\*.log` | `/var/log/system.log` | `/var/log/nested/system.log`
<span data-ttu-id="f7553-240">?</span><span class="sxs-lookup"><span data-stu-id="f7553-240">?</span></span> | <span data-ttu-id="f7553-241">Coincide con cualquier carácter</span><span class="sxs-lookup"><span data-stu-id="f7553-241">Matches any single character</span></span> | `file?.log` | `file1.log`<br/>`file2.log` | `file123.log`

##### <a name="path-type-file--directory"></a><span data-ttu-id="f7553-242">Tipo de ruta de acceso (archivo/directorio)</span><span class="sxs-lookup"><span data-stu-id="f7553-242">Path type (file / directory)</span></span>

<span data-ttu-id="f7553-243">Indica si la *propiedad path* hace referencia a un archivo o directorio.</span><span class="sxs-lookup"><span data-stu-id="f7553-243">Indicate if the *path* property refers to a file or directory.</span></span> 

|<span data-ttu-id="f7553-244">Sección</span><span class="sxs-lookup"><span data-stu-id="f7553-244">Section</span></span>|<span data-ttu-id="f7553-245">Valor</span><span class="sxs-lookup"><span data-stu-id="f7553-245">Value</span></span>|
|:---|:---|
| <span data-ttu-id="f7553-246">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="f7553-246">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="f7553-247">**Clave**</span><span class="sxs-lookup"><span data-stu-id="f7553-247">**Key**</span></span> | <span data-ttu-id="f7553-248">isDirectory</span><span class="sxs-lookup"><span data-stu-id="f7553-248">isDirectory</span></span> |
| <span data-ttu-id="f7553-249">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="f7553-249">**Data type**</span></span> | <span data-ttu-id="f7553-250">Booleano</span><span class="sxs-lookup"><span data-stu-id="f7553-250">Boolean</span></span> |
| <span data-ttu-id="f7553-251">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="f7553-251">**Possible values**</span></span> | <span data-ttu-id="f7553-252">false (predeterminado)</span><span class="sxs-lookup"><span data-stu-id="f7553-252">false (default)</span></span> <br/> <span data-ttu-id="f7553-253">true</span><span class="sxs-lookup"><span data-stu-id="f7553-253">true</span></span> |
| <span data-ttu-id="f7553-254">**Comments**</span><span class="sxs-lookup"><span data-stu-id="f7553-254">**Comments**</span></span> | <span data-ttu-id="f7553-255">Aplicable solo *si $type* *se excluyePath*</span><span class="sxs-lookup"><span data-stu-id="f7553-255">Applicable only if *$type* is *excludedPath*</span></span> |

##### <a name="file-extension-excluded-from-the-scan"></a><span data-ttu-id="f7553-256">Extensión de archivo excluida del examen</span><span class="sxs-lookup"><span data-stu-id="f7553-256">File extension excluded from the scan</span></span>

<span data-ttu-id="f7553-257">Especifique el contenido excluido de la extensión de archivo.</span><span class="sxs-lookup"><span data-stu-id="f7553-257">Specify content excluded from being scanned by file extension.</span></span>

|<span data-ttu-id="f7553-258">Sección</span><span class="sxs-lookup"><span data-stu-id="f7553-258">Section</span></span>|<span data-ttu-id="f7553-259">Valor</span><span class="sxs-lookup"><span data-stu-id="f7553-259">Value</span></span>|
|:---|:---|
| <span data-ttu-id="f7553-260">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="f7553-260">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="f7553-261">**Clave**</span><span class="sxs-lookup"><span data-stu-id="f7553-261">**Key**</span></span> | <span data-ttu-id="f7553-262">extensión</span><span class="sxs-lookup"><span data-stu-id="f7553-262">extension</span></span> |
| <span data-ttu-id="f7553-263">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="f7553-263">**Data type**</span></span> | <span data-ttu-id="f7553-264">Cadena</span><span class="sxs-lookup"><span data-stu-id="f7553-264">String</span></span> |
| <span data-ttu-id="f7553-265">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="f7553-265">**Possible values**</span></span> | <span data-ttu-id="f7553-266">extensiones de archivo válidas</span><span class="sxs-lookup"><span data-stu-id="f7553-266">valid file extensions</span></span> |
| <span data-ttu-id="f7553-267">**Comments**</span><span class="sxs-lookup"><span data-stu-id="f7553-267">**Comments**</span></span> | <span data-ttu-id="f7553-268">Aplicable solo *si $type* *se excluyeFileExtension*</span><span class="sxs-lookup"><span data-stu-id="f7553-268">Applicable only if *$type* is *excludedFileExtension*</span></span> |

##### <a name="process-excluded-from-the-scan"></a><span data-ttu-id="f7553-269">Proceso excluido del examen</span><span class="sxs-lookup"><span data-stu-id="f7553-269">Process excluded from the scan</span></span>

<span data-ttu-id="f7553-270">Especifique un proceso para el que se excluya toda la actividad de archivo del examen.</span><span class="sxs-lookup"><span data-stu-id="f7553-270">Specify a process for which all file activity is excluded from scanning.</span></span> <span data-ttu-id="f7553-271">El proceso puede especificarse por su nombre (por ejemplo) o por la ruta de acceso `cat` completa (por ejemplo, `/bin/cat` ).</span><span class="sxs-lookup"><span data-stu-id="f7553-271">The process can be specified either by its name (e.g. `cat`) or full path (e.g. `/bin/cat`).</span></span>

|<span data-ttu-id="f7553-272">Sección</span><span class="sxs-lookup"><span data-stu-id="f7553-272">Section</span></span>|<span data-ttu-id="f7553-273">Valor</span><span class="sxs-lookup"><span data-stu-id="f7553-273">Value</span></span>|
|:---|:---|
| <span data-ttu-id="f7553-274">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="f7553-274">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="f7553-275">**Clave**</span><span class="sxs-lookup"><span data-stu-id="f7553-275">**Key**</span></span> | <span data-ttu-id="f7553-276">name</span><span class="sxs-lookup"><span data-stu-id="f7553-276">name</span></span> |
| <span data-ttu-id="f7553-277">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="f7553-277">**Data type**</span></span> | <span data-ttu-id="f7553-278">Cadena</span><span class="sxs-lookup"><span data-stu-id="f7553-278">String</span></span> |
| <span data-ttu-id="f7553-279">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="f7553-279">**Possible values**</span></span> | <span data-ttu-id="f7553-280">cualquier cadena</span><span class="sxs-lookup"><span data-stu-id="f7553-280">any string</span></span> |
| <span data-ttu-id="f7553-281">**Comments**</span><span class="sxs-lookup"><span data-stu-id="f7553-281">**Comments**</span></span> | <span data-ttu-id="f7553-282">Aplicable solo *si $type* *se excluyeFileName*</span><span class="sxs-lookup"><span data-stu-id="f7553-282">Applicable only if *$type* is *excludedFileName*</span></span> |

#### <a name="allowed-threats"></a><span data-ttu-id="f7553-283">Amenazas permitidas</span><span class="sxs-lookup"><span data-stu-id="f7553-283">Allowed threats</span></span>

<span data-ttu-id="f7553-284">Especifica las amenazas por nombre que no estén bloqueadas por Defender para Endpoint en Mac.</span><span class="sxs-lookup"><span data-stu-id="f7553-284">Specify threats by name that are not blocked by Defender for Endpoint on Mac.</span></span> <span data-ttu-id="f7553-285">Estas amenazas podrán ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="f7553-285">These threats will be allowed to run.</span></span>

|<span data-ttu-id="f7553-286">Sección</span><span class="sxs-lookup"><span data-stu-id="f7553-286">Section</span></span>|<span data-ttu-id="f7553-287">Valor</span><span class="sxs-lookup"><span data-stu-id="f7553-287">Value</span></span>|
|:---|:---|
| <span data-ttu-id="f7553-288">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="f7553-288">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="f7553-289">**Clave**</span><span class="sxs-lookup"><span data-stu-id="f7553-289">**Key**</span></span> | <span data-ttu-id="f7553-290">allowedThreats</span><span class="sxs-lookup"><span data-stu-id="f7553-290">allowedThreats</span></span> |
| <span data-ttu-id="f7553-291">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="f7553-291">**Data type**</span></span> | <span data-ttu-id="f7553-292">Matriz de cadenas</span><span class="sxs-lookup"><span data-stu-id="f7553-292">Array of strings</span></span> |

#### <a name="disallowed-threat-actions"></a><span data-ttu-id="f7553-293">Acciones de amenazas no permitidos</span><span class="sxs-lookup"><span data-stu-id="f7553-293">Disallowed threat actions</span></span>

<span data-ttu-id="f7553-294">Restringe las acciones que el usuario local de un dispositivo puede realizar cuando se detectan amenazas.</span><span class="sxs-lookup"><span data-stu-id="f7553-294">Restricts the actions that the local user of a device can take when threats are detected.</span></span> <span data-ttu-id="f7553-295">Las acciones incluidas en esta lista no se muestran en la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="f7553-295">The actions included in this list are not displayed in the user interface.</span></span>

|<span data-ttu-id="f7553-296">Sección</span><span class="sxs-lookup"><span data-stu-id="f7553-296">Section</span></span>|<span data-ttu-id="f7553-297">Valor</span><span class="sxs-lookup"><span data-stu-id="f7553-297">Value</span></span>|
|:---|:---|
| <span data-ttu-id="f7553-298">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="f7553-298">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="f7553-299">**Clave**</span><span class="sxs-lookup"><span data-stu-id="f7553-299">**Key**</span></span> | <span data-ttu-id="f7553-300">disallowedThreatActions</span><span class="sxs-lookup"><span data-stu-id="f7553-300">disallowedThreatActions</span></span> |
| <span data-ttu-id="f7553-301">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="f7553-301">**Data type**</span></span> | <span data-ttu-id="f7553-302">Matriz de cadenas</span><span class="sxs-lookup"><span data-stu-id="f7553-302">Array of strings</span></span> |
| <span data-ttu-id="f7553-303">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="f7553-303">**Possible values**</span></span> | <span data-ttu-id="f7553-304">permitir (restringe a los usuarios permitir amenazas)</span><span class="sxs-lookup"><span data-stu-id="f7553-304">allow (restricts users from allowing threats)</span></span> <br/> <span data-ttu-id="f7553-305">restore (restringe a los usuarios la restauración de amenazas desde la cuarentena)</span><span class="sxs-lookup"><span data-stu-id="f7553-305">restore (restricts users from restoring threats from the quarantine)</span></span> |
| <span data-ttu-id="f7553-306">**Comments**</span><span class="sxs-lookup"><span data-stu-id="f7553-306">**Comments**</span></span> | <span data-ttu-id="f7553-307">Disponible en Microsoft Defender para endpoint versión 100.83.73 o posterior.</span><span class="sxs-lookup"><span data-stu-id="f7553-307">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="threat-type-settings"></a><span data-ttu-id="f7553-308">Configuración del tipo de amenaza</span><span class="sxs-lookup"><span data-stu-id="f7553-308">Threat type settings</span></span>

<span data-ttu-id="f7553-309">Especifica cómo se controlan determinados tipos de amenazas por Microsoft Defender para Endpoint en macOS.</span><span class="sxs-lookup"><span data-stu-id="f7553-309">Specify how certain threat types are handled by Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="f7553-310">Sección</span><span class="sxs-lookup"><span data-stu-id="f7553-310">Section</span></span>|<span data-ttu-id="f7553-311">Valor</span><span class="sxs-lookup"><span data-stu-id="f7553-311">Value</span></span>|
|:---|:---|
| <span data-ttu-id="f7553-312">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="f7553-312">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="f7553-313">**Clave**</span><span class="sxs-lookup"><span data-stu-id="f7553-313">**Key**</span></span> | <span data-ttu-id="f7553-314">threatTypeSettings</span><span class="sxs-lookup"><span data-stu-id="f7553-314">threatTypeSettings</span></span> |
| <span data-ttu-id="f7553-315">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="f7553-315">**Data type**</span></span> | <span data-ttu-id="f7553-316">Diccionario (preferencia anidada)</span><span class="sxs-lookup"><span data-stu-id="f7553-316">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="f7553-317">**Comments**</span><span class="sxs-lookup"><span data-stu-id="f7553-317">**Comments**</span></span> | <span data-ttu-id="f7553-318">Vea las secciones siguientes para obtener una descripción del contenido del diccionario.</span><span class="sxs-lookup"><span data-stu-id="f7553-318">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="threat-type"></a><span data-ttu-id="f7553-319">Tipo de amenaza</span><span class="sxs-lookup"><span data-stu-id="f7553-319">Threat type</span></span>

<span data-ttu-id="f7553-320">Especifique tipos de amenazas.</span><span class="sxs-lookup"><span data-stu-id="f7553-320">Specify threat types.</span></span>

|<span data-ttu-id="f7553-321">Sección</span><span class="sxs-lookup"><span data-stu-id="f7553-321">Section</span></span>|<span data-ttu-id="f7553-322">Valor</span><span class="sxs-lookup"><span data-stu-id="f7553-322">Value</span></span>|
|:---|:---|
| <span data-ttu-id="f7553-323">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="f7553-323">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="f7553-324">**Clave**</span><span class="sxs-lookup"><span data-stu-id="f7553-324">**Key**</span></span> | <span data-ttu-id="f7553-325">clave</span><span class="sxs-lookup"><span data-stu-id="f7553-325">key</span></span> |
| <span data-ttu-id="f7553-326">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="f7553-326">**Data type**</span></span> | <span data-ttu-id="f7553-327">Cadena</span><span class="sxs-lookup"><span data-stu-id="f7553-327">String</span></span> |
| <span data-ttu-id="f7553-328">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="f7553-328">**Possible values**</span></span> | <span data-ttu-id="f7553-329">potentially_unwanted_application</span><span class="sxs-lookup"><span data-stu-id="f7553-329">potentially_unwanted_application</span></span> <br/> <span data-ttu-id="f7553-330">archive_bomb</span><span class="sxs-lookup"><span data-stu-id="f7553-330">archive_bomb</span></span> |

##### <a name="action-to-take"></a><span data-ttu-id="f7553-331">Acción que puede realizar</span><span class="sxs-lookup"><span data-stu-id="f7553-331">Action to take</span></span>

<span data-ttu-id="f7553-332">Especifique qué acción realizar cuando se detecte una amenaza del tipo especificado en la sección anterior.</span><span class="sxs-lookup"><span data-stu-id="f7553-332">Specify what action to take when a threat of the type specified in the preceding section is detected.</span></span> <span data-ttu-id="f7553-333">Seleccione una de las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="f7553-333">Choose from the following options:</span></span>

- <span data-ttu-id="f7553-334">**Auditoría:** el dispositivo no está protegido contra este tipo de amenaza, pero se registra una entrada sobre la amenaza.</span><span class="sxs-lookup"><span data-stu-id="f7553-334">**Audit**: your device is not protected against this type of threat, but an entry about the threat is logged.</span></span>
- <span data-ttu-id="f7553-335">**Bloquear:** el dispositivo está protegido contra este tipo de amenaza y se te notificará en la interfaz de usuario y en la consola de seguridad.</span><span class="sxs-lookup"><span data-stu-id="f7553-335">**Block**: your device is protected against this type of threat and you are notified in the user interface and the security console.</span></span>
- <span data-ttu-id="f7553-336">**Desactivado:** el dispositivo no está protegido contra este tipo de amenaza y no se registra nada.</span><span class="sxs-lookup"><span data-stu-id="f7553-336">**Off**: your device is not protected against this type of threat and nothing is logged.</span></span>

|<span data-ttu-id="f7553-337">Sección</span><span class="sxs-lookup"><span data-stu-id="f7553-337">Section</span></span>|<span data-ttu-id="f7553-338">Valor</span><span class="sxs-lookup"><span data-stu-id="f7553-338">Value</span></span>|
|:---|:---|
| <span data-ttu-id="f7553-339">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="f7553-339">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="f7553-340">**Clave**</span><span class="sxs-lookup"><span data-stu-id="f7553-340">**Key**</span></span> | <span data-ttu-id="f7553-341">valor</span><span class="sxs-lookup"><span data-stu-id="f7553-341">value</span></span> |
| <span data-ttu-id="f7553-342">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="f7553-342">**Data type**</span></span> | <span data-ttu-id="f7553-343">Cadena</span><span class="sxs-lookup"><span data-stu-id="f7553-343">String</span></span> |
| <span data-ttu-id="f7553-344">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="f7553-344">**Possible values**</span></span> | <span data-ttu-id="f7553-345">auditoría (valor predeterminado)</span><span class="sxs-lookup"><span data-stu-id="f7553-345">audit (default)</span></span> <br/> <span data-ttu-id="f7553-346">bloque</span><span class="sxs-lookup"><span data-stu-id="f7553-346">block</span></span> <br/> <span data-ttu-id="f7553-347">off</span><span class="sxs-lookup"><span data-stu-id="f7553-347">off</span></span> |

#### <a name="threat-type-settings-merge-policy"></a><span data-ttu-id="f7553-348">Directiva de combinación de configuración de tipo de amenaza</span><span class="sxs-lookup"><span data-stu-id="f7553-348">Threat type settings merge policy</span></span>

<span data-ttu-id="f7553-349">Especifique la directiva de combinación para la configuración del tipo de amenaza.</span><span class="sxs-lookup"><span data-stu-id="f7553-349">Specify the merge policy for threat type settings.</span></span> <span data-ttu-id="f7553-350">Puede ser una combinación de opciones definidas por el administrador y definidas por el usuario ( ) o solo opciones definidas `merge` por el administrador ( `admin_only` ).</span><span class="sxs-lookup"><span data-stu-id="f7553-350">This can be a combination of administrator-defined and user-defined settings (`merge`) or only administrator-defined settings (`admin_only`).</span></span> <span data-ttu-id="f7553-351">Esta configuración se puede usar para restringir que los usuarios locales definan su propia configuración para diferentes tipos de amenazas.</span><span class="sxs-lookup"><span data-stu-id="f7553-351">This setting can be used to restrict local users from defining their own settings for different threat types.</span></span>

|<span data-ttu-id="f7553-352">Sección</span><span class="sxs-lookup"><span data-stu-id="f7553-352">Section</span></span>|<span data-ttu-id="f7553-353">Valor</span><span class="sxs-lookup"><span data-stu-id="f7553-353">Value</span></span>|
|:---|:---|
| <span data-ttu-id="f7553-354">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="f7553-354">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="f7553-355">**Clave**</span><span class="sxs-lookup"><span data-stu-id="f7553-355">**Key**</span></span> | <span data-ttu-id="f7553-356">threatTypeSettingsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="f7553-356">threatTypeSettingsMergePolicy</span></span> |
| <span data-ttu-id="f7553-357">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="f7553-357">**Data type**</span></span> | <span data-ttu-id="f7553-358">Cadena</span><span class="sxs-lookup"><span data-stu-id="f7553-358">String</span></span> |
| <span data-ttu-id="f7553-359">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="f7553-359">**Possible values**</span></span> | <span data-ttu-id="f7553-360">merge (valor predeterminado)</span><span class="sxs-lookup"><span data-stu-id="f7553-360">merge (default)</span></span> <br/> <span data-ttu-id="f7553-361">admin_only</span><span class="sxs-lookup"><span data-stu-id="f7553-361">admin_only</span></span> |
| <span data-ttu-id="f7553-362">**Comments**</span><span class="sxs-lookup"><span data-stu-id="f7553-362">**Comments**</span></span> | <span data-ttu-id="f7553-363">Disponible en Microsoft Defender para endpoint versión 100.83.73 o posterior.</span><span class="sxs-lookup"><span data-stu-id="f7553-363">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="antivirus-scan-history-retention-in-days"></a><span data-ttu-id="f7553-364">Retención del historial de examen antivirus (en días)</span><span class="sxs-lookup"><span data-stu-id="f7553-364">Antivirus scan history retention (in days)</span></span>

<span data-ttu-id="f7553-365">Especifica el número de días que los resultados se conservan en el historial de examen del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f7553-365">Specify the number of days that results are retained in the scan history on the device.</span></span> <span data-ttu-id="f7553-366">Los resultados del examen antiguos se quitan del historial.</span><span class="sxs-lookup"><span data-stu-id="f7553-366">Old scan results are removed from the history.</span></span> <span data-ttu-id="f7553-367">Archivos antiguos en cuarentena que también se quitan del disco.</span><span class="sxs-lookup"><span data-stu-id="f7553-367">Old quarantined files that are also removed from the disk.</span></span>

|<span data-ttu-id="f7553-368">Sección</span><span class="sxs-lookup"><span data-stu-id="f7553-368">Section</span></span>|<span data-ttu-id="f7553-369">Valor</span><span class="sxs-lookup"><span data-stu-id="f7553-369">Value</span></span>|
|:---|:---|
| <span data-ttu-id="f7553-370">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="f7553-370">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="f7553-371">**Clave**</span><span class="sxs-lookup"><span data-stu-id="f7553-371">**Key**</span></span> | <span data-ttu-id="f7553-372">scanResultsRetentionDays</span><span class="sxs-lookup"><span data-stu-id="f7553-372">scanResultsRetentionDays</span></span> |
| <span data-ttu-id="f7553-373">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="f7553-373">**Data type**</span></span> | <span data-ttu-id="f7553-374">Cadena</span><span class="sxs-lookup"><span data-stu-id="f7553-374">String</span></span> |
| <span data-ttu-id="f7553-375">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="f7553-375">**Possible values**</span></span> | <span data-ttu-id="f7553-376">90 (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="f7553-376">90 (default).</span></span> <span data-ttu-id="f7553-377">Los valores permitidos van de 1 día a 180 días.</span><span class="sxs-lookup"><span data-stu-id="f7553-377">Allowed values are from 1 day to 180 days.</span></span> |
| <span data-ttu-id="f7553-378">**Comments**</span><span class="sxs-lookup"><span data-stu-id="f7553-378">**Comments**</span></span> | <span data-ttu-id="f7553-379">Disponible en Microsoft Defender para endpoint versión 101.07.23 o posterior.</span><span class="sxs-lookup"><span data-stu-id="f7553-379">Available in Microsoft Defender for Endpoint version 101.07.23 or higher.</span></span> |

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a><span data-ttu-id="f7553-380">Número máximo de elementos en el historial de examen antivirus</span><span class="sxs-lookup"><span data-stu-id="f7553-380">Maximum number of items in the antivirus scan history</span></span>

<span data-ttu-id="f7553-381">Especifique el número máximo de entradas que se deben conservar en el historial de examen.</span><span class="sxs-lookup"><span data-stu-id="f7553-381">Specify the maximum number of entries to keep in the scan history.</span></span> <span data-ttu-id="f7553-382">Las entradas incluyen todos los exámenes a petición realizados en el pasado y todas las detecciones de antivirus.</span><span class="sxs-lookup"><span data-stu-id="f7553-382">Entries include all on-demand scans performed in the past and all antivirus detections.</span></span>

|<span data-ttu-id="f7553-383">Sección</span><span class="sxs-lookup"><span data-stu-id="f7553-383">Section</span></span>|<span data-ttu-id="f7553-384">Valor</span><span class="sxs-lookup"><span data-stu-id="f7553-384">Value</span></span>|
|:---|:---|
| <span data-ttu-id="f7553-385">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="f7553-385">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="f7553-386">**Clave**</span><span class="sxs-lookup"><span data-stu-id="f7553-386">**Key**</span></span> | <span data-ttu-id="f7553-387">scanHistoryMaximumItems</span><span class="sxs-lookup"><span data-stu-id="f7553-387">scanHistoryMaximumItems</span></span> |
| <span data-ttu-id="f7553-388">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="f7553-388">**Data type**</span></span> | <span data-ttu-id="f7553-389">Cadena</span><span class="sxs-lookup"><span data-stu-id="f7553-389">String</span></span> |
| <span data-ttu-id="f7553-390">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="f7553-390">**Possible values**</span></span> | <span data-ttu-id="f7553-391">10000 (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="f7553-391">10000 (default).</span></span> <span data-ttu-id="f7553-392">Los valores permitidos van de 5000 elementos a 15000 elementos.</span><span class="sxs-lookup"><span data-stu-id="f7553-392">Allowed values are from 5000 items to 15000 items.</span></span> |
| <span data-ttu-id="f7553-393">**Comments**</span><span class="sxs-lookup"><span data-stu-id="f7553-393">**Comments**</span></span> | <span data-ttu-id="f7553-394">Disponible en Microsoft Defender para endpoint versión 101.07.23 o posterior.</span><span class="sxs-lookup"><span data-stu-id="f7553-394">Available in Microsoft Defender for Endpoint version 101.07.23 or higher.</span></span> |

### <a name="cloud-delivered-protection-preferences"></a><span data-ttu-id="f7553-395">Preferencias de protección entregadas en la nube</span><span class="sxs-lookup"><span data-stu-id="f7553-395">Cloud-delivered protection preferences</span></span>

<span data-ttu-id="f7553-396">Configure las características de protección controlada por la nube de Microsoft Defender para Endpoint en macOS.</span><span class="sxs-lookup"><span data-stu-id="f7553-396">Configure the cloud-driven protection features of Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="f7553-397">Sección</span><span class="sxs-lookup"><span data-stu-id="f7553-397">Section</span></span>|<span data-ttu-id="f7553-398">Valor</span><span class="sxs-lookup"><span data-stu-id="f7553-398">Value</span></span>|
|:---|:---|
| <span data-ttu-id="f7553-399">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="f7553-399">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="f7553-400">**Clave**</span><span class="sxs-lookup"><span data-stu-id="f7553-400">**Key**</span></span> | <span data-ttu-id="f7553-401">cloudService</span><span class="sxs-lookup"><span data-stu-id="f7553-401">cloudService</span></span> |
| <span data-ttu-id="f7553-402">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="f7553-402">**Data type**</span></span> | <span data-ttu-id="f7553-403">Diccionario (preferencia anidada)</span><span class="sxs-lookup"><span data-stu-id="f7553-403">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="f7553-404">**Comments**</span><span class="sxs-lookup"><span data-stu-id="f7553-404">**Comments**</span></span> | <span data-ttu-id="f7553-405">Vea las secciones siguientes para obtener una descripción del contenido del diccionario.</span><span class="sxs-lookup"><span data-stu-id="f7553-405">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="enable--disable-cloud-delivered-protection"></a><span data-ttu-id="f7553-406">Habilitar o deshabilitar la protección entregada en la nube</span><span class="sxs-lookup"><span data-stu-id="f7553-406">Enable / disable cloud-delivered protection</span></span>

<span data-ttu-id="f7553-407">Especifica si se va a habilitar la protección entregada en la nube del dispositivo o no.</span><span class="sxs-lookup"><span data-stu-id="f7553-407">Specify whether to enable cloud-delivered protection the device or not.</span></span> <span data-ttu-id="f7553-408">Para mejorar la seguridad de los servicios, se recomienda mantener activada esta característica.</span><span class="sxs-lookup"><span data-stu-id="f7553-408">To improve the security of your services, we recommend keeping this feature turned on.</span></span>

|<span data-ttu-id="f7553-409">Sección</span><span class="sxs-lookup"><span data-stu-id="f7553-409">Section</span></span>|<span data-ttu-id="f7553-410">Valor</span><span class="sxs-lookup"><span data-stu-id="f7553-410">Value</span></span>|
|:---|:---|
| <span data-ttu-id="f7553-411">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="f7553-411">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="f7553-412">**Clave**</span><span class="sxs-lookup"><span data-stu-id="f7553-412">**Key**</span></span> | <span data-ttu-id="f7553-413">habilitado</span><span class="sxs-lookup"><span data-stu-id="f7553-413">enabled</span></span> |
| <span data-ttu-id="f7553-414">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="f7553-414">**Data type**</span></span> | <span data-ttu-id="f7553-415">Booleano</span><span class="sxs-lookup"><span data-stu-id="f7553-415">Boolean</span></span> |
| <span data-ttu-id="f7553-416">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="f7553-416">**Possible values**</span></span> | <span data-ttu-id="f7553-417">true (valor predeterminado)</span><span class="sxs-lookup"><span data-stu-id="f7553-417">true (default)</span></span> <br/> <span data-ttu-id="f7553-418">false</span><span class="sxs-lookup"><span data-stu-id="f7553-418">false</span></span> |

#### <a name="diagnostic-collection-level"></a><span data-ttu-id="f7553-419">Nivel de colección de diagnóstico</span><span class="sxs-lookup"><span data-stu-id="f7553-419">Diagnostic collection level</span></span>

<span data-ttu-id="f7553-420">Los datos de diagnóstico se usan para mantener Microsoft Defender for Endpoint seguro y actualizado, detectar, diagnosticar y corregir problemas y también realizar mejoras en el producto.</span><span class="sxs-lookup"><span data-stu-id="f7553-420">Diagnostic data is used to keep Microsoft Defender for Endpoint secure and up-to-date, detect, diagnose and fix problems, and also make product improvements.</span></span> <span data-ttu-id="f7553-421">Esta configuración determina el nivel de diagnóstico enviado por Microsoft Defender para Endpoint a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f7553-421">This setting determines the level of diagnostics sent by Microsoft Defender for Endpoint to Microsoft.</span></span>

|<span data-ttu-id="f7553-422">Sección</span><span class="sxs-lookup"><span data-stu-id="f7553-422">Section</span></span>|<span data-ttu-id="f7553-423">Valor</span><span class="sxs-lookup"><span data-stu-id="f7553-423">Value</span></span>|
|:---|:---|
| <span data-ttu-id="f7553-424">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="f7553-424">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="f7553-425">**Clave**</span><span class="sxs-lookup"><span data-stu-id="f7553-425">**Key**</span></span> | <span data-ttu-id="f7553-426">diagnosticLevel</span><span class="sxs-lookup"><span data-stu-id="f7553-426">diagnosticLevel</span></span> |
| <span data-ttu-id="f7553-427">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="f7553-427">**Data type**</span></span> | <span data-ttu-id="f7553-428">Cadena</span><span class="sxs-lookup"><span data-stu-id="f7553-428">String</span></span> |
| <span data-ttu-id="f7553-429">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="f7553-429">**Possible values**</span></span> | <span data-ttu-id="f7553-430">opcional (predeterminado)</span><span class="sxs-lookup"><span data-stu-id="f7553-430">optional (default)</span></span> <br/> <span data-ttu-id="f7553-431">necesario</span><span class="sxs-lookup"><span data-stu-id="f7553-431">required</span></span> |

#### <a name="enable--disable-automatic-sample-submissions"></a><span data-ttu-id="f7553-432">Habilitar o deshabilitar envíos de ejemplo automáticos</span><span class="sxs-lookup"><span data-stu-id="f7553-432">Enable / disable automatic sample submissions</span></span>

<span data-ttu-id="f7553-433">Determina si se envían muestras sospechosas (que probablemente contengan amenazas) a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f7553-433">Determines whether suspicious samples (that are likely to contain threats) are sent to Microsoft.</span></span> <span data-ttu-id="f7553-434">Se le preguntará si es probable que el archivo enviado contenga información personal.</span><span class="sxs-lookup"><span data-stu-id="f7553-434">You are prompted if the submitted file is likely to contain personal information.</span></span>

|<span data-ttu-id="f7553-435">Sección</span><span class="sxs-lookup"><span data-stu-id="f7553-435">Section</span></span>|<span data-ttu-id="f7553-436">Valor</span><span class="sxs-lookup"><span data-stu-id="f7553-436">Value</span></span>|
|:---|:---|
| <span data-ttu-id="f7553-437">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="f7553-437">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="f7553-438">**Clave**</span><span class="sxs-lookup"><span data-stu-id="f7553-438">**Key**</span></span> | <span data-ttu-id="f7553-439">automaticSampleSubmission</span><span class="sxs-lookup"><span data-stu-id="f7553-439">automaticSampleSubmission</span></span> |
| <span data-ttu-id="f7553-440">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="f7553-440">**Data type**</span></span> | <span data-ttu-id="f7553-441">Booleano</span><span class="sxs-lookup"><span data-stu-id="f7553-441">Boolean</span></span> |
| <span data-ttu-id="f7553-442">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="f7553-442">**Possible values**</span></span> | <span data-ttu-id="f7553-443">true (valor predeterminado)</span><span class="sxs-lookup"><span data-stu-id="f7553-443">true (default)</span></span> <br/> <span data-ttu-id="f7553-444">false</span><span class="sxs-lookup"><span data-stu-id="f7553-444">false</span></span> |

#### <a name="enable--disable-automatic-security-intelligence-updates"></a><span data-ttu-id="f7553-445">Habilitar o deshabilitar actualizaciones automáticas de inteligencia de seguridad</span><span class="sxs-lookup"><span data-stu-id="f7553-445">Enable / disable automatic security intelligence updates</span></span>

<span data-ttu-id="f7553-446">Determina si las actualizaciones de inteligencia de seguridad se instalan automáticamente:</span><span class="sxs-lookup"><span data-stu-id="f7553-446">Determines whether security intelligence updates are installed automatically:</span></span>

|<span data-ttu-id="f7553-447">Sección</span><span class="sxs-lookup"><span data-stu-id="f7553-447">Section</span></span>|<span data-ttu-id="f7553-448">Valor</span><span class="sxs-lookup"><span data-stu-id="f7553-448">Value</span></span>|
|:---|:---|
| <span data-ttu-id="f7553-449">**Clave**</span><span class="sxs-lookup"><span data-stu-id="f7553-449">**Key**</span></span> | <span data-ttu-id="f7553-450">automaticDefinitionUpdateEnabled</span><span class="sxs-lookup"><span data-stu-id="f7553-450">automaticDefinitionUpdateEnabled</span></span> |
| <span data-ttu-id="f7553-451">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="f7553-451">**Data type**</span></span> | <span data-ttu-id="f7553-452">Booleano</span><span class="sxs-lookup"><span data-stu-id="f7553-452">Boolean</span></span> |
| <span data-ttu-id="f7553-453">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="f7553-453">**Possible values**</span></span> | <span data-ttu-id="f7553-454">true (valor predeterminado)</span><span class="sxs-lookup"><span data-stu-id="f7553-454">true (default)</span></span> <br/> <span data-ttu-id="f7553-455">false</span><span class="sxs-lookup"><span data-stu-id="f7553-455">false</span></span> |

### <a name="user-interface-preferences"></a><span data-ttu-id="f7553-456">Preferencias de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="f7553-456">User interface preferences</span></span>

<span data-ttu-id="f7553-457">Administrar las preferencias de la interfaz de usuario de Microsoft Defender para Endpoint en macOS.</span><span class="sxs-lookup"><span data-stu-id="f7553-457">Manage the preferences for the user interface of Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="f7553-458">Sección</span><span class="sxs-lookup"><span data-stu-id="f7553-458">Section</span></span>|<span data-ttu-id="f7553-459">Valor</span><span class="sxs-lookup"><span data-stu-id="f7553-459">Value</span></span>|
|:---|:---|
| <span data-ttu-id="f7553-460">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="f7553-460">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="f7553-461">**Clave**</span><span class="sxs-lookup"><span data-stu-id="f7553-461">**Key**</span></span> | <span data-ttu-id="f7553-462">userInterface</span><span class="sxs-lookup"><span data-stu-id="f7553-462">userInterface</span></span> |
| <span data-ttu-id="f7553-463">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="f7553-463">**Data type**</span></span> | <span data-ttu-id="f7553-464">Diccionario (preferencia anidada)</span><span class="sxs-lookup"><span data-stu-id="f7553-464">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="f7553-465">**Comments**</span><span class="sxs-lookup"><span data-stu-id="f7553-465">**Comments**</span></span> | <span data-ttu-id="f7553-466">Vea las secciones siguientes para obtener una descripción del contenido del diccionario.</span><span class="sxs-lookup"><span data-stu-id="f7553-466">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="show--hide-status-menu-icon"></a><span data-ttu-id="f7553-467">Mostrar u ocultar icono de menú de estado</span><span class="sxs-lookup"><span data-stu-id="f7553-467">Show / hide status menu icon</span></span>

<span data-ttu-id="f7553-468">Especifique si desea mostrar u ocultar el icono del menú de estado en la esquina superior derecha de la pantalla.</span><span class="sxs-lookup"><span data-stu-id="f7553-468">Specify whether to show or hide the status menu icon in the top-right corner of the screen.</span></span>

|<span data-ttu-id="f7553-469">Sección</span><span class="sxs-lookup"><span data-stu-id="f7553-469">Section</span></span>|<span data-ttu-id="f7553-470">Valor</span><span class="sxs-lookup"><span data-stu-id="f7553-470">Value</span></span>|
|:---|:---|
| <span data-ttu-id="f7553-471">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="f7553-471">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="f7553-472">**Clave**</span><span class="sxs-lookup"><span data-stu-id="f7553-472">**Key**</span></span> | <span data-ttu-id="f7553-473">hideStatusMenuIcon</span><span class="sxs-lookup"><span data-stu-id="f7553-473">hideStatusMenuIcon</span></span> |
| <span data-ttu-id="f7553-474">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="f7553-474">**Data type**</span></span> | <span data-ttu-id="f7553-475">Booleano</span><span class="sxs-lookup"><span data-stu-id="f7553-475">Boolean</span></span> |
| <span data-ttu-id="f7553-476">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="f7553-476">**Possible values**</span></span> | <span data-ttu-id="f7553-477">false (predeterminado)</span><span class="sxs-lookup"><span data-stu-id="f7553-477">false (default)</span></span> <br/> <span data-ttu-id="f7553-478">true</span><span class="sxs-lookup"><span data-stu-id="f7553-478">true</span></span> |

#### <a name="show--hide-option-to-send-feedback"></a><span data-ttu-id="f7553-479">Mostrar u ocultar opción para enviar comentarios</span><span class="sxs-lookup"><span data-stu-id="f7553-479">Show / hide option to send feedback</span></span>

<span data-ttu-id="f7553-480">Especifica si los usuarios pueden enviar comentarios a Microsoft yendo a `Help`  >  `Send Feedback` .</span><span class="sxs-lookup"><span data-stu-id="f7553-480">Specify whether users can submit feedback to Microsoft by going to `Help` > `Send Feedback`.</span></span>

|<span data-ttu-id="f7553-481">Sección</span><span class="sxs-lookup"><span data-stu-id="f7553-481">Section</span></span>|<span data-ttu-id="f7553-482">Valor</span><span class="sxs-lookup"><span data-stu-id="f7553-482">Value</span></span>|
|:---|:---|
| <span data-ttu-id="f7553-483">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="f7553-483">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="f7553-484">**Clave**</span><span class="sxs-lookup"><span data-stu-id="f7553-484">**Key**</span></span> | <span data-ttu-id="f7553-485">userInitiatedFeedback</span><span class="sxs-lookup"><span data-stu-id="f7553-485">userInitiatedFeedback</span></span> |
| <span data-ttu-id="f7553-486">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="f7553-486">**Data type**</span></span> | <span data-ttu-id="f7553-487">Cadena</span><span class="sxs-lookup"><span data-stu-id="f7553-487">String</span></span> |
| <span data-ttu-id="f7553-488">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="f7553-488">**Possible values**</span></span> | <span data-ttu-id="f7553-489">habilitado (predeterminado)</span><span class="sxs-lookup"><span data-stu-id="f7553-489">enabled (default)</span></span> <br/> <span data-ttu-id="f7553-490">deshabilitado</span><span class="sxs-lookup"><span data-stu-id="f7553-490">disabled</span></span> |
| <span data-ttu-id="f7553-491">**Comments**</span><span class="sxs-lookup"><span data-stu-id="f7553-491">**Comments**</span></span> | <span data-ttu-id="f7553-492">Disponible en Microsoft Defender para endpoint versión 101.19.61 o posterior.</span><span class="sxs-lookup"><span data-stu-id="f7553-492">Available in Microsoft Defender for Endpoint version 101.19.61 or higher.</span></span> |

### <a name="endpoint-detection-and-response-preferences"></a><span data-ttu-id="f7553-493">Preferencias de detección y respuesta de extremos</span><span class="sxs-lookup"><span data-stu-id="f7553-493">Endpoint detection and response preferences</span></span>

<span data-ttu-id="f7553-494">Administrar las preferencias del componente detección y respuesta de puntos de conexión (EDR) de Microsoft Defender para endpoint en macOS.</span><span class="sxs-lookup"><span data-stu-id="f7553-494">Manage the preferences of the endpoint detection and response (EDR) component of Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="f7553-495">Sección</span><span class="sxs-lookup"><span data-stu-id="f7553-495">Section</span></span>|<span data-ttu-id="f7553-496">Valor</span><span class="sxs-lookup"><span data-stu-id="f7553-496">Value</span></span>|
|:---|:---|
| <span data-ttu-id="f7553-497">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="f7553-497">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="f7553-498">**Clave**</span><span class="sxs-lookup"><span data-stu-id="f7553-498">**Key**</span></span> | <span data-ttu-id="f7553-499">edr</span><span class="sxs-lookup"><span data-stu-id="f7553-499">edr</span></span> |
| <span data-ttu-id="f7553-500">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="f7553-500">**Data type**</span></span> | <span data-ttu-id="f7553-501">Diccionario (preferencia anidada)</span><span class="sxs-lookup"><span data-stu-id="f7553-501">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="f7553-502">**Comments**</span><span class="sxs-lookup"><span data-stu-id="f7553-502">**Comments**</span></span> | <span data-ttu-id="f7553-503">Vea las secciones siguientes para obtener una descripción del contenido del diccionario.</span><span class="sxs-lookup"><span data-stu-id="f7553-503">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="device-tags"></a><span data-ttu-id="f7553-504">Etiquetas de dispositivo</span><span class="sxs-lookup"><span data-stu-id="f7553-504">Device tags</span></span>

<span data-ttu-id="f7553-505">Especifique un nombre de etiqueta y su valor.</span><span class="sxs-lookup"><span data-stu-id="f7553-505">Specify a tag name and its value.</span></span> 

- <span data-ttu-id="f7553-506">La etiqueta GROUP, etiqueta el dispositivo con el valor especificado.</span><span class="sxs-lookup"><span data-stu-id="f7553-506">The GROUP tag, tags the device with the specified value.</span></span> <span data-ttu-id="f7553-507">La etiqueta se refleja en el portal en la página del dispositivo y se puede usar para filtrar y agrupar dispositivos.</span><span class="sxs-lookup"><span data-stu-id="f7553-507">The tag is reflected in the portal under the device page and can be used for filtering and grouping devices.</span></span>

|<span data-ttu-id="f7553-508">Sección</span><span class="sxs-lookup"><span data-stu-id="f7553-508">Section</span></span>|<span data-ttu-id="f7553-509">Valor</span><span class="sxs-lookup"><span data-stu-id="f7553-509">Value</span></span>|
|:---|:---|
| <span data-ttu-id="f7553-510">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="f7553-510">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="f7553-511">**Clave**</span><span class="sxs-lookup"><span data-stu-id="f7553-511">**Key**</span></span> | <span data-ttu-id="f7553-512">tags</span><span class="sxs-lookup"><span data-stu-id="f7553-512">tags</span></span> |
| <span data-ttu-id="f7553-513">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="f7553-513">**Data type**</span></span> | <span data-ttu-id="f7553-514">Diccionario (preferencia anidada)</span><span class="sxs-lookup"><span data-stu-id="f7553-514">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="f7553-515">**Comments**</span><span class="sxs-lookup"><span data-stu-id="f7553-515">**Comments**</span></span> | <span data-ttu-id="f7553-516">Vea las secciones siguientes para obtener una descripción del contenido del diccionario.</span><span class="sxs-lookup"><span data-stu-id="f7553-516">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="type-of-tag"></a><span data-ttu-id="f7553-517">Tipo de etiqueta</span><span class="sxs-lookup"><span data-stu-id="f7553-517">Type of tag</span></span>

<span data-ttu-id="f7553-518">Especifica el tipo de etiqueta</span><span class="sxs-lookup"><span data-stu-id="f7553-518">Specifies the type of tag</span></span>

|<span data-ttu-id="f7553-519">Sección</span><span class="sxs-lookup"><span data-stu-id="f7553-519">Section</span></span>|<span data-ttu-id="f7553-520">Valor</span><span class="sxs-lookup"><span data-stu-id="f7553-520">Value</span></span>|
|:---|:---|
| <span data-ttu-id="f7553-521">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="f7553-521">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="f7553-522">**Clave**</span><span class="sxs-lookup"><span data-stu-id="f7553-522">**Key**</span></span> | <span data-ttu-id="f7553-523">clave</span><span class="sxs-lookup"><span data-stu-id="f7553-523">key</span></span> |
| <span data-ttu-id="f7553-524">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="f7553-524">**Data type**</span></span> | <span data-ttu-id="f7553-525">Cadena</span><span class="sxs-lookup"><span data-stu-id="f7553-525">String</span></span> |
| <span data-ttu-id="f7553-526">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="f7553-526">**Possible values**</span></span> | `GROUP` |

##### <a name="value-of-tag"></a><span data-ttu-id="f7553-527">Valor de etiqueta</span><span class="sxs-lookup"><span data-stu-id="f7553-527">Value of tag</span></span>

<span data-ttu-id="f7553-528">Especifica el valor de la etiqueta</span><span class="sxs-lookup"><span data-stu-id="f7553-528">Specifies the value of tag</span></span>

|<span data-ttu-id="f7553-529">Sección</span><span class="sxs-lookup"><span data-stu-id="f7553-529">Section</span></span>|<span data-ttu-id="f7553-530">Valor</span><span class="sxs-lookup"><span data-stu-id="f7553-530">Value</span></span>|
|:---|:---|
| <span data-ttu-id="f7553-531">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="f7553-531">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="f7553-532">**Clave**</span><span class="sxs-lookup"><span data-stu-id="f7553-532">**Key**</span></span> | <span data-ttu-id="f7553-533">valor</span><span class="sxs-lookup"><span data-stu-id="f7553-533">value</span></span> |
| <span data-ttu-id="f7553-534">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="f7553-534">**Data type**</span></span> | <span data-ttu-id="f7553-535">Cadena</span><span class="sxs-lookup"><span data-stu-id="f7553-535">String</span></span> |
| <span data-ttu-id="f7553-536">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="f7553-536">**Possible values**</span></span> | <span data-ttu-id="f7553-537">cualquier cadena</span><span class="sxs-lookup"><span data-stu-id="f7553-537">any string</span></span> |

> [!IMPORTANT]  
> - <span data-ttu-id="f7553-538">Solo se puede establecer un valor por tipo de etiqueta.</span><span class="sxs-lookup"><span data-stu-id="f7553-538">Only one value per tag type can be set.</span></span>
> - <span data-ttu-id="f7553-539">El tipo de etiquetas es único y no debe repetirse en el mismo perfil de configuración.</span><span class="sxs-lookup"><span data-stu-id="f7553-539">Type of tags are unique, and should not be repeated in the same configuration profile.</span></span>

## <a name="recommended-configuration-profile"></a><span data-ttu-id="f7553-540">Perfil de configuración recomendado</span><span class="sxs-lookup"><span data-stu-id="f7553-540">Recommended configuration profile</span></span>

<span data-ttu-id="f7553-541">Para empezar, se recomienda la siguiente configuración para que la empresa aproveche todas las características de protección que proporciona Microsoft Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="f7553-541">To get started, we recommend the following configuration for your enterprise to take advantage of all protection features that Microsoft Defender for Endpoint provides.</span></span>

<span data-ttu-id="f7553-542">El siguiente perfil de configuración (o, en el caso de JAMF, una lista de propiedades que podría cargarse en el perfil de configuración de configuración personalizada) será:</span><span class="sxs-lookup"><span data-stu-id="f7553-542">The following configuration profile (or, in case of JAMF, a property list that could be uploaded into the custom settings configuration profile) will:</span></span>
- <span data-ttu-id="f7553-543">Habilitar la protección en tiempo real (RTP)</span><span class="sxs-lookup"><span data-stu-id="f7553-543">Enable real-time protection (RTP)</span></span>
- <span data-ttu-id="f7553-544">Especifique cómo se controlan los siguientes tipos de amenazas:</span><span class="sxs-lookup"><span data-stu-id="f7553-544">Specify how the following threat types are handled:</span></span>
  - <span data-ttu-id="f7553-545">**Las aplicaciones potencialmente no deseadas (PUA)** están bloqueadas</span><span class="sxs-lookup"><span data-stu-id="f7553-545">**Potentially unwanted applications (PUA)** are blocked</span></span>
  - <span data-ttu-id="f7553-546">**Las bombas de archivo** (archivo con una tasa de compresión alta) se auditan en Microsoft Defender para los registros de punto de conexión</span><span class="sxs-lookup"><span data-stu-id="f7553-546">**Archive bombs** (file with a high compression rate) are audited to Microsoft Defender for Endpoint logs</span></span>
- <span data-ttu-id="f7553-547">Habilitar actualizaciones automáticas de inteligencia de seguridad</span><span class="sxs-lookup"><span data-stu-id="f7553-547">Enable automatic security intelligence updates</span></span>
- <span data-ttu-id="f7553-548">Habilitar la protección proporcionada en la nube</span><span class="sxs-lookup"><span data-stu-id="f7553-548">Enable cloud-delivered protection</span></span>
- <span data-ttu-id="f7553-549">Habilitar el envío automático de muestra</span><span class="sxs-lookup"><span data-stu-id="f7553-549">Enable automatic sample submission</span></span>

### <a name="property-list-for-jamf-configuration-profile"></a><span data-ttu-id="f7553-550">Lista de propiedades para el perfil de configuración de JAMF</span><span class="sxs-lookup"><span data-stu-id="f7553-550">Property list for JAMF configuration profile</span></span>

```XML
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>antivirusEngine</key>
    <dict>
        <key>enableRealTimeProtection</key>
        <true/>
        <key>threatTypeSettings</key>
        <array>
            <dict>
                <key>key</key>
                <string>potentially_unwanted_application</string>
                <key>value</key>
                <string>block</string>
            </dict>
            <dict>
                <key>key</key>
                <string>archive_bomb</string>
                <key>value</key>
                <string>audit</string>
            </dict>
        </array>
    </dict>
    <key>cloudService</key>
    <dict>
        <key>enabled</key>
        <true/>
        <key>automaticSampleSubmission</key>
        <true/>
        <key>automaticDefinitionUpdateEnabled</key>
        <true/>
    </dict>
</dict>
</plist>
```

### <a name="intune-profile"></a><span data-ttu-id="f7553-551">Perfil de Intune</span><span class="sxs-lookup"><span data-stu-id="f7553-551">Intune profile</span></span>

```XML
<?xml version="1.0" encoding="utf-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1">
    <dict>
        <key>PayloadUUID</key>
        <string>C4E6A782-0C8D-44AB-A025-EB893987A295</string>
        <key>PayloadType</key>
        <string>Configuration</string>
        <key>PayloadOrganization</key>
        <string>Microsoft</string>
        <key>PayloadIdentifier</key>
        <string>com.microsoft.wdav</string>
        <key>PayloadDisplayName</key>
        <string>Microsoft Defender for Endpoint settings</string>
        <key>PayloadDescription</key>
        <string>Microsoft Defender for Endpoint configuration settings</string>
        <key>PayloadVersion</key>
        <integer>1</integer>
        <key>PayloadEnabled</key>
        <true/>
        <key>PayloadRemovalDisallowed</key>
        <true/>
        <key>PayloadScope</key>
        <string>System</string>
        <key>PayloadContent</key>
        <array>
            <dict>
                <key>PayloadUUID</key>
                <string>99DBC2BC-3B3A-46A2-A413-C8F9BB9A7295</string>
                <key>PayloadType</key>
                <string>com.microsoft.wdav</string>
                <key>PayloadOrganization</key>
                <string>Microsoft</string>
                <key>PayloadIdentifier</key>
                <string>com.microsoft.wdav</string>
                <key>PayloadDisplayName</key>
                <string>Microsoft Defender for Endpoint configuration settings</string>
                <key>PayloadDescription</key>
                <string/>
                <key>PayloadVersion</key>
                <integer>1</integer>
                <key>PayloadEnabled</key>
                <true/>
                <key>antivirusEngine</key>
                <dict>
                    <key>enableRealTimeProtection</key>
                    <true/>
                    <key>threatTypeSettings</key>
                    <array>
                        <dict>
                            <key>key</key>
                            <string>potentially_unwanted_application</string>
                            <key>value</key>
                            <string>block</string>
                        </dict>
                        <dict>
                            <key>key</key>
                            <string>archive_bomb</string>
                            <key>value</key>
                            <string>audit</string>
                        </dict>
                    </array>
                </dict>
                <key>cloudService</key>
                <dict>
                    <key>enabled</key>
                    <true/>
                    <key>automaticSampleSubmission</key>
                    <true/>
                    <key>automaticDefinitionUpdateEnabled</key>
                    <true/>
                </dict>
            </dict>
        </array>
    </dict>
</plist>
```

## <a name="full-configuration-profile-example"></a><span data-ttu-id="f7553-552">Ejemplo de perfil de configuración completa</span><span class="sxs-lookup"><span data-stu-id="f7553-552">Full configuration profile example</span></span>

<span data-ttu-id="f7553-553">Las plantillas siguientes contienen entradas para todas las configuraciones descritas en este documento y se pueden usar para escenarios más avanzados en los que desea tener más control sobre Microsoft Defender para Endpoint en macOS.</span><span class="sxs-lookup"><span data-stu-id="f7553-553">The following templates contain entries for all settings described in this document and can be used for more advanced scenarios where you want more control over Microsoft Defender for Endpoint on macOS.</span></span>

### <a name="property-list-for-jamf-configuration-profile"></a><span data-ttu-id="f7553-554">Lista de propiedades para el perfil de configuración de JAMF</span><span class="sxs-lookup"><span data-stu-id="f7553-554">Property list for JAMF configuration profile</span></span>

```XML
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>antivirusEngine</key>
    <dict>
        <key>enableRealTimeProtection</key>
        <true/>
        <key>passiveMode</key>
        <false/>
        <key>exclusions</key>
        <array>
            <dict>
                <key>$type</key>
                <string>excludedPath</string>
                <key>isDirectory</key>
                <false/>
                <key>path</key>
                <string>/var/log/system.log</string>
            </dict>
            <dict>
                <key>$type</key>
                <string>excludedPath</string>
                <key>isDirectory</key>
                <true/>
                <key>path</key>
                <string>/home</string>
            </dict>
            <dict>
                <key>$type</key>
                <string>excludedPath</string>
                <key>isDirectory</key>
                <true/>
                <key>path</key>
                <string>/Users/*/git</string>
            </dict>
            <dict>
                <key>$type</key>
                <string>excludedFileExtension</string>
                <key>extension</key>
                <string>pdf</string>
            </dict>
            <dict>
                <key>$type</key>
                <string>excludedFileName</string>
                <key>name</key>
                <string>cat</string>
            </dict>
        </array>
        <key>exclusionsMergePolicy</key>
        <string>merge</string>
        <key>allowedThreats</key>
        <array>
            <string>EICAR-Test-File (not a virus)</string>
        </array>
        <key>disallowedThreatActions</key>
        <array>
            <string>allow</string>
            <string>restore</string>
        </array>
        <key>threatTypeSettings</key>
        <array>
            <dict>
                <key>key</key>
                <string>potentially_unwanted_application</string>
                <key>value</key>
                <string>block</string>
            </dict>
            <dict>
                <key>key</key>
                <string>archive_bomb</string>
                <key>value</key>
                <string>audit</string>
            </dict>
        </array>
        <key>threatTypeSettingsMergePolicy</key>
        <string>merge</string>
    </dict>
    <key>cloudService</key>
    <dict>
        <key>enabled</key>
        <true/>
        <key>diagnosticLevel</key>
        <string>optional</string>
        <key>automaticSampleSubmission</key>
        <true/>
        <key>automaticDefinitionUpdateEnabled</key>
        <true/>
    </dict>
    <key>edr</key>
    <dict>
        <key>tags</key>
        <array>
            <dict>
                <key>key</key>
                <string>GROUP</string>
                <key>value</key>
                <string>ExampleTag</string>
            </dict>
        </array>
    </dict>
    <key>userInterface</key>
    <dict>
        <key>hideStatusMenuIcon</key>
        <false/>
        <key>userInitiatedFeedback</key>
        <string>enabled</string>
    </dict>
</dict>
</plist>
```

### <a name="intune-profile"></a><span data-ttu-id="f7553-555">Perfil de Intune</span><span class="sxs-lookup"><span data-stu-id="f7553-555">Intune profile</span></span>

```XML
        <key>PayloadUUID</key>
        <string>C4E6A782-0C8D-44AB-A025-EB893987A295</string>
        <key>PayloadType</key>
        <string>Configuration</string>
        <key>PayloadOrganization</key>
        <string>Microsoft</string>
        <key>PayloadIdentifier</key>
        <string>C4E6A782-0C8D-44AB-A025-EB893987A295</string>
        <key>PayloadDisplayName</key>
        <string>Microsoft Defender for Endpoint settings</string>
        <key>PayloadDescription</key>
        <string>Microsoft Defender for Endpoint configuration settings</string>
        <key>PayloadVersion</key>
        <integer>1</integer>
        <key>PayloadEnabled</key>
        <true/>
        <key>PayloadRemovalDisallowed</key>
        <true/>
        <key>PayloadScope</key>
        <string>System</string>
        <key>PayloadContent</key>
        <array>
            <dict>
                <key>PayloadUUID</key>
                <string>99DBC2BC-3B3A-46A2-A413-C8F9BB9A7295</string>
                <key>PayloadType</key>
                <string>com.microsoft.wdav</string>
                <key>PayloadOrganization</key>
                <string>Microsoft</string>
                <key>PayloadIdentifier</key>
                <string>99DBC2BC-3B3A-46A2-A413-C8F9BB9A7295</string>
                <key>PayloadDisplayName</key>
                <string>Microsoft Defender for Endpoint configuration settings</string>
                <key>PayloadDescription</key>
                <string/>
                <key>PayloadVersion</key>
                <integer>1</integer>
                <key>PayloadEnabled</key>
                <true/>
                <key>antivirusEngine</key>
                <dict>
                    <key>enableRealTimeProtection</key>
                    <true/>
                    <key>passiveMode</key>
                    <false/>
                    <key>exclusions</key>
                    <array>
                        <dict>
                            <key>$type</key>
                            <string>excludedPath</string>
                            <key>isDirectory</key>
                            <false/>
                            <key>path</key>
                            <string>/var/log/system.log</string>
                        </dict>
                        <dict>
                            <key>$type</key>
                            <string>excludedPath</string>
                            <key>isDirectory</key>
                            <true/>
                            <key>path</key>
                            <string>/home</string>
                        </dict>
                        <dict>
                            <key>$type</key>
                            <string>excludedPath</string>
                            <key>isDirectory</key>
                            <true/>
                            <key>path</key>
                            <string>/Users/*/git</string>
                        </dict>
                        <dict>
                            <key>$type</key>
                            <string>excludedFileExtension</string>
                            <key>extension</key>
                            <string>pdf</string>
                        </dict>
                        <dict>
                            <key>$type</key>
                            <string>excludedFileName</string>
                            <key>name</key>
                            <string>cat</string>
                        </dict>
                    </array>
                    <key>exclusionsMergePolicy</key>
                    <string>merge</string>
                    <key>allowedThreats</key>
                    <array>
                        <string>EICAR-Test-File (not a virus)</string>
                    </array>
                    <key>disallowedThreatActions</key>
                    <array>
                        <string>allow</string>
                        <string>restore</string>
                    </array>
                    <key>threatTypeSettings</key>
                    <array>
                        <dict>
                            <key>key</key>
                            <string>potentially_unwanted_application</string>
                            <key>value</key>
                            <string>block</string>
                        </dict>
                        <dict>
                            <key>key</key>
                            <string>archive_bomb</string>
                            <key>value</key>
                            <string>audit</string>
                        </dict>
                    </array>
                    <key>threatTypeSettingsMergePolicy</key>
                    <string>merge</string>
                </dict>
                <key>cloudService</key>
                <dict>
                    <key>enabled</key>
                    <true/>
                    <key>diagnosticLevel</key>
                    <string>optional</string>
                    <key>automaticSampleSubmission</key>
                    <true/>
                    <key>automaticDefinitionUpdateEnabled</key>
                    <true/>
                </dict>
                <key>edr</key>
                <dict>
                    <key>tags</key>
                    <array>
                        <dict>
                            <key>key</key>
                            <string>GROUP</string>
                            <key>value</key>
                            <string>ExampleTag</string>
                        </dict>
                    </array>
                </dict>
                <key>userInterface</key>
                <dict>
                    <key>hideStatusMenuIcon</key>
                    <false/>
                    <key>userInitiatedFeedback</key>
                    <string>enabled</string>
                </dict>
            </dict>
        </array>
```

## <a name="property-list-validation"></a><span data-ttu-id="f7553-556">Validación de lista de propiedades</span><span class="sxs-lookup"><span data-stu-id="f7553-556">Property list validation</span></span>

<span data-ttu-id="f7553-557">La lista de propiedades debe ser un archivo *.plist* válido.</span><span class="sxs-lookup"><span data-stu-id="f7553-557">The property list must be a valid *.plist* file.</span></span> <span data-ttu-id="f7553-558">Esto se puede comprobar ejecutando:</span><span class="sxs-lookup"><span data-stu-id="f7553-558">This can be checked by executing:</span></span>

```bash
plutil -lint com.microsoft.wdav.plist
```
```Output
com.microsoft.wdav.plist: OK
```

<span data-ttu-id="f7553-559">Si el archivo está bien formado, el comando anterior genera `OK` y devuelve un código de salida de `0` .</span><span class="sxs-lookup"><span data-stu-id="f7553-559">If the file is well-formed, the above command outputs `OK` and returns an exit code of `0`.</span></span> <span data-ttu-id="f7553-560">De lo contrario, se muestra un error que describe el problema y el comando devuelve un código de salida de `1` .</span><span class="sxs-lookup"><span data-stu-id="f7553-560">Otherwise, an error that describes the issue is displayed and the command returns an exit code of `1`.</span></span>

## <a name="configuration-profile-deployment"></a><span data-ttu-id="f7553-561">Implementación de perfiles de configuración</span><span class="sxs-lookup"><span data-stu-id="f7553-561">Configuration profile deployment</span></span>

<span data-ttu-id="f7553-562">Una vez que haya creado el perfil de configuración para su empresa, puede implementarlo a través de la consola de administración que usa su empresa.</span><span class="sxs-lookup"><span data-stu-id="f7553-562">Once you've built the configuration profile for your enterprise, you can deploy it through the management console that your enterprise is using.</span></span> <span data-ttu-id="f7553-563">En las secciones siguientes se proporcionan instrucciones sobre cómo implementar este perfil con JAMF e Intune.</span><span class="sxs-lookup"><span data-stu-id="f7553-563">The following sections provide instructions on how to deploy this profile using JAMF and Intune.</span></span>

### <a name="jamf-deployment"></a><span data-ttu-id="f7553-564">Implementación de JAMF</span><span class="sxs-lookup"><span data-stu-id="f7553-564">JAMF deployment</span></span>

<span data-ttu-id="f7553-565">En la consola JAMF, abra **Perfiles** de configuración de equipos , vaya al perfil de configuración que desea usar y, a  >  continuación, seleccione **Custom Configuración**.</span><span class="sxs-lookup"><span data-stu-id="f7553-565">From the JAMF console, open **Computers** > **Configuration Profiles**, navigate to the configuration profile you'd like to use, then select **Custom Settings**.</span></span> <span data-ttu-id="f7553-566">Cree una entrada con `com.microsoft.wdav` como dominio de preferencia y cargue el *.plist* generado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="f7553-566">Create an entry with `com.microsoft.wdav` as the preference domain and upload the *.plist* produced earlier.</span></span>

>[!CAUTION]
><span data-ttu-id="f7553-567">Debes escribir el dominio de preferencia correcto ( ); de lo contrario, Microsoft Defender no reconocerá las `com.microsoft.wdav` preferencias para endpoint.</span><span class="sxs-lookup"><span data-stu-id="f7553-567">You must enter the correct preference domain (`com.microsoft.wdav`); otherwise, the preferences will not be recognized by Microsoft Defender for Endpoint.</span></span>

### <a name="intune-deployment"></a><span data-ttu-id="f7553-568">Implementación de Intune</span><span class="sxs-lookup"><span data-stu-id="f7553-568">Intune deployment</span></span>

1. <span data-ttu-id="f7553-569">Abra **Administrar configuración** de  >  **dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="f7553-569">Open **Manage** > **Device configuration**.</span></span> <span data-ttu-id="f7553-570">Seleccione **Administrar**  >  **perfiles Crear**  >  **perfil**.</span><span class="sxs-lookup"><span data-stu-id="f7553-570">Select **Manage** > **Profiles** > **Create Profile**.</span></span>

2. <span data-ttu-id="f7553-571">Elija un nombre para el perfil.</span><span class="sxs-lookup"><span data-stu-id="f7553-571">Choose a name for the profile.</span></span> <span data-ttu-id="f7553-572">Cambiar **Platform=macOS** a **Profile type=Custom**.</span><span class="sxs-lookup"><span data-stu-id="f7553-572">Change **Platform=macOS** to **Profile type=Custom**.</span></span> <span data-ttu-id="f7553-573">Seleccione Configurar.</span><span class="sxs-lookup"><span data-stu-id="f7553-573">Select Configure.</span></span>

3. <span data-ttu-id="f7553-574">Guarde el .plist generado anteriormente como `com.microsoft.wdav.xml` .</span><span class="sxs-lookup"><span data-stu-id="f7553-574">Save the .plist produced earlier as `com.microsoft.wdav.xml`.</span></span>

4. <span data-ttu-id="f7553-575">Escriba `com.microsoft.wdav` como el nombre del perfil de configuración **personalizado**.</span><span class="sxs-lookup"><span data-stu-id="f7553-575">Enter `com.microsoft.wdav` as the **custom configuration profile name**.</span></span>

5. <span data-ttu-id="f7553-576">Abra el perfil de configuración y cargue el `com.microsoft.wdav.xml` archivo.</span><span class="sxs-lookup"><span data-stu-id="f7553-576">Open the configuration profile and upload the `com.microsoft.wdav.xml` file.</span></span> <span data-ttu-id="f7553-577">(Este archivo se creó en el paso 3).</span><span class="sxs-lookup"><span data-stu-id="f7553-577">(This file was created in step 3.)</span></span>

6. <span data-ttu-id="f7553-578">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f7553-578">Select **OK**.</span></span>

7. <span data-ttu-id="f7553-579">Seleccione **Administrar**  >  **asignaciones**.</span><span class="sxs-lookup"><span data-stu-id="f7553-579">Select **Manage** > **Assignments**.</span></span> <span data-ttu-id="f7553-580">En la **pestaña Incluir,** seleccione **Asignar a todos los usuarios & Todos los dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="f7553-580">In the **Include** tab, select **Assign to All Users & All devices**.</span></span>

>[!CAUTION]
><span data-ttu-id="f7553-581">Debe escribir el nombre del perfil de configuración personalizado correcto; de lo contrario, Microsoft Defender no reconocerá estas preferencias para endpoint.</span><span class="sxs-lookup"><span data-stu-id="f7553-581">You must enter the correct custom configuration profile name; otherwise, these preferences will not be recognized by Microsoft Defender for Endpoint.</span></span>

## <a name="resources"></a><span data-ttu-id="f7553-582">Recursos</span><span class="sxs-lookup"><span data-stu-id="f7553-582">Resources</span></span>

- [<span data-ttu-id="f7553-583">Referencia de los perfiles de configuración (documentación para desarrolladores de Apple)</span><span class="sxs-lookup"><span data-stu-id="f7553-583">Configuration Profile Reference (Apple developer documentation)</span></span>](https://developer.apple.com/business/documentation/Configuration-Profile-Reference.pdf)
