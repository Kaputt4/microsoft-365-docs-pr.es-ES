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
# <a name="set-preferences-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="22de1-104">Establecer preferencias para Microsoft Defender para endpoint en macOS</span><span class="sxs-lookup"><span data-stu-id="22de1-104">Set preferences for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="22de1-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="22de1-105">**Applies to:**</span></span>

- [<span data-ttu-id="22de1-106">Microsoft Defender para punto de conexión en macOS</span><span class="sxs-lookup"><span data-stu-id="22de1-106">Microsoft Defender for Endpoint on macOS</span></span>](microsoft-defender-endpoint-mac.md)

>[!IMPORTANT]
><span data-ttu-id="22de1-107">Este artículo contiene instrucciones sobre cómo establecer las preferencias de Microsoft Defender para Endpoint en macOS en organizaciones empresariales.</span><span class="sxs-lookup"><span data-stu-id="22de1-107">This article contains instructions for how to set preferences for Microsoft Defender for Endpoint on macOS in enterprise organizations.</span></span> <span data-ttu-id="22de1-108">Para configurar Microsoft Defender para endpoint en macOS mediante la interfaz de línea de comandos, vea [Resources](mac-resources.md#configuring-from-the-command-line).</span><span class="sxs-lookup"><span data-stu-id="22de1-108">To configure Microsoft Defender for Endpoint on macOS using the command-line interface, see [Resources](mac-resources.md#configuring-from-the-command-line).</span></span>

## <a name="summary"></a><span data-ttu-id="22de1-109">Resumen</span><span class="sxs-lookup"><span data-stu-id="22de1-109">Summary</span></span>

<span data-ttu-id="22de1-110">En organizaciones empresariales, Microsoft Defender para Endpoint en macOS se puede administrar a través de un perfil de configuración que se implementa mediante una de varias herramientas de administración.</span><span class="sxs-lookup"><span data-stu-id="22de1-110">In enterprise organizations, Microsoft Defender for Endpoint on macOS can be managed through a configuration profile that is deployed by using one of several management tools.</span></span> <span data-ttu-id="22de1-111">Las preferencias administradas por el equipo de operaciones de seguridad tienen prioridad sobre las preferencias que se establecen localmente en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="22de1-111">Preferences that are managed by your security operations team take precedence over preferences that are set locally on the device.</span></span> <span data-ttu-id="22de1-112">Cambiar las preferencias que se establecen a través del perfil de configuración requiere privilegios escalados y no está disponible para usuarios sin permisos administrativos.</span><span class="sxs-lookup"><span data-stu-id="22de1-112">Changing the preferences that are set through the configuration profile requires escalated privileges and is not available for users without administrative permissions.</span></span>

<span data-ttu-id="22de1-113">En este artículo se describe la estructura del perfil de configuración, se incluye un perfil recomendado que puede usar para empezar y se proporcionan instrucciones sobre cómo implementar el perfil.</span><span class="sxs-lookup"><span data-stu-id="22de1-113">This article describes the structure of the configuration profile, includes a recommended profile that you can use to get started, and provides instructions on how to deploy the profile.</span></span>

## <a name="configuration-profile-structure"></a><span data-ttu-id="22de1-114">Estructura de perfiles de configuración</span><span class="sxs-lookup"><span data-stu-id="22de1-114">Configuration profile structure</span></span>

<span data-ttu-id="22de1-115">El perfil de configuración es un *archivo .plist* que consta de entradas identificadas por una clave (que indica el nombre de la preferencia), seguido de un valor, que depende de la naturaleza de la preferencia.</span><span class="sxs-lookup"><span data-stu-id="22de1-115">The configuration profile is a *.plist* file that consists of entries identified by a key (which denotes the name of the preference), followed by a value, which depends on the nature of the preference.</span></span> <span data-ttu-id="22de1-116">Los valores pueden ser simples (como un valor numérico) o complejos, como una lista anidada de preferencias.</span><span class="sxs-lookup"><span data-stu-id="22de1-116">Values can either be simple (such as a numerical value) or complex, such as a nested list of preferences.</span></span>

>[!CAUTION]
><span data-ttu-id="22de1-117">El diseño del perfil de configuración depende de la consola de administración que se use.</span><span class="sxs-lookup"><span data-stu-id="22de1-117">The layout of the configuration profile depends on the management console that you are using.</span></span> <span data-ttu-id="22de1-118">Las secciones siguientes contienen ejemplos de perfiles de configuración para JAMF e Intune.</span><span class="sxs-lookup"><span data-stu-id="22de1-118">The following sections contain examples of configuration profiles for JAMF and Intune.</span></span>

<span data-ttu-id="22de1-119">El nivel superior del perfil de configuración incluye las preferencias de todo el producto y las entradas para las subáreas de Microsoft Defender para endpoint, que se explican con más detalle en las secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="22de1-119">The top level of the configuration profile includes product-wide preferences and entries for subareas of Microsoft Defender for Endpoint, which are explained in more detail in the next sections.</span></span>

### <a name="antivirus-engine-preferences"></a><span data-ttu-id="22de1-120">Preferencias del motor antivirus</span><span class="sxs-lookup"><span data-stu-id="22de1-120">Antivirus engine preferences</span></span>

<span data-ttu-id="22de1-121">La *sección antivirusEngine* del perfil de configuración se usa para administrar las preferencias del componente antivirus de Microsoft Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="22de1-121">The *antivirusEngine* section of the configuration profile is used to manage the preferences of the antivirus component of Microsoft Defender for Endpoint.</span></span>

|<span data-ttu-id="22de1-122">Sección</span><span class="sxs-lookup"><span data-stu-id="22de1-122">Section</span></span>|<span data-ttu-id="22de1-123">Valor</span><span class="sxs-lookup"><span data-stu-id="22de1-123">Value</span></span>|
|:---|:---|
| <span data-ttu-id="22de1-124">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="22de1-124">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="22de1-125">**Key**</span><span class="sxs-lookup"><span data-stu-id="22de1-125">**Key**</span></span> | <span data-ttu-id="22de1-126">antivirusEngine</span><span class="sxs-lookup"><span data-stu-id="22de1-126">antivirusEngine</span></span> |
| <span data-ttu-id="22de1-127">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="22de1-127">**Data type**</span></span> | <span data-ttu-id="22de1-128">Diccionario (preferencia anidada)</span><span class="sxs-lookup"><span data-stu-id="22de1-128">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="22de1-129">**Comments**</span><span class="sxs-lookup"><span data-stu-id="22de1-129">**Comments**</span></span> | <span data-ttu-id="22de1-130">Vea las secciones siguientes para obtener una descripción del contenido del diccionario.</span><span class="sxs-lookup"><span data-stu-id="22de1-130">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="enable--disable-real-time-protection"></a><span data-ttu-id="22de1-131">Habilitar o deshabilitar la protección en tiempo real</span><span class="sxs-lookup"><span data-stu-id="22de1-131">Enable / disable real-time protection</span></span>

<span data-ttu-id="22de1-132">Especifique si se va a habilitar la protección en tiempo real, que examina los archivos a medida que se accede a ellos.</span><span class="sxs-lookup"><span data-stu-id="22de1-132">Specify whether to enable real-time protection, which scans files as they are accessed.</span></span>

|<span data-ttu-id="22de1-133">Sección</span><span class="sxs-lookup"><span data-stu-id="22de1-133">Section</span></span>|<span data-ttu-id="22de1-134">Valor</span><span class="sxs-lookup"><span data-stu-id="22de1-134">Value</span></span>|
|:---|:---|
| <span data-ttu-id="22de1-135">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="22de1-135">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="22de1-136">**Key**</span><span class="sxs-lookup"><span data-stu-id="22de1-136">**Key**</span></span> | <span data-ttu-id="22de1-137">enableRealTimeProtection</span><span class="sxs-lookup"><span data-stu-id="22de1-137">enableRealTimeProtection</span></span> |
| <span data-ttu-id="22de1-138">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="22de1-138">**Data type**</span></span> | <span data-ttu-id="22de1-139">Booleano</span><span class="sxs-lookup"><span data-stu-id="22de1-139">Boolean</span></span> |
| <span data-ttu-id="22de1-140">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="22de1-140">**Possible values**</span></span> | <span data-ttu-id="22de1-141">true (valor predeterminado)</span><span class="sxs-lookup"><span data-stu-id="22de1-141">true (default)</span></span> <br/> <span data-ttu-id="22de1-142">false</span><span class="sxs-lookup"><span data-stu-id="22de1-142">false</span></span> |

#### <a name="enable--disable-passive-mode"></a><span data-ttu-id="22de1-143">Habilitar o deshabilitar el modo pasivo</span><span class="sxs-lookup"><span data-stu-id="22de1-143">Enable / disable passive mode</span></span>

<span data-ttu-id="22de1-144">Especifique si el motor antivirus se ejecuta en modo pasivo.</span><span class="sxs-lookup"><span data-stu-id="22de1-144">Specify whether the antivirus engine runs in passive mode.</span></span> <span data-ttu-id="22de1-145">El modo pasivo tiene las siguientes implicaciones:</span><span class="sxs-lookup"><span data-stu-id="22de1-145">Passive mode has the following implications:</span></span> 
- <span data-ttu-id="22de1-146">La protección en tiempo real está desactivada</span><span class="sxs-lookup"><span data-stu-id="22de1-146">Real-time protection is turned off</span></span>
- <span data-ttu-id="22de1-147">El examen a petición está activado</span><span class="sxs-lookup"><span data-stu-id="22de1-147">On-demand scanning is turned on</span></span>
- <span data-ttu-id="22de1-148">La corrección automática de amenazas está desactivada</span><span class="sxs-lookup"><span data-stu-id="22de1-148">Automatic threat remediation is turned off</span></span>
- <span data-ttu-id="22de1-149">Las actualizaciones de inteligencia de seguridad están activadas</span><span class="sxs-lookup"><span data-stu-id="22de1-149">Security intelligence updates are turned on</span></span>
- <span data-ttu-id="22de1-150">El icono del menú Estado está oculto</span><span class="sxs-lookup"><span data-stu-id="22de1-150">Status menu icon is hidden</span></span>

|<span data-ttu-id="22de1-151">Sección</span><span class="sxs-lookup"><span data-stu-id="22de1-151">Section</span></span>|<span data-ttu-id="22de1-152">Valor</span><span class="sxs-lookup"><span data-stu-id="22de1-152">Value</span></span>|
|:---|:---|
| <span data-ttu-id="22de1-153">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="22de1-153">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="22de1-154">**Key**</span><span class="sxs-lookup"><span data-stu-id="22de1-154">**Key**</span></span> | <span data-ttu-id="22de1-155">passiveMode</span><span class="sxs-lookup"><span data-stu-id="22de1-155">passiveMode</span></span> |
| <span data-ttu-id="22de1-156">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="22de1-156">**Data type**</span></span> | <span data-ttu-id="22de1-157">Booleano</span><span class="sxs-lookup"><span data-stu-id="22de1-157">Boolean</span></span> |
| <span data-ttu-id="22de1-158">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="22de1-158">**Possible values**</span></span> | <span data-ttu-id="22de1-159">false (predeterminado)</span><span class="sxs-lookup"><span data-stu-id="22de1-159">false (default)</span></span> <br/> <span data-ttu-id="22de1-160">true</span><span class="sxs-lookup"><span data-stu-id="22de1-160">true</span></span> |
| <span data-ttu-id="22de1-161">**Comments**</span><span class="sxs-lookup"><span data-stu-id="22de1-161">**Comments**</span></span> | <span data-ttu-id="22de1-162">Disponible en Microsoft Defender para endpoint versión 100.67.60 o posterior.</span><span class="sxs-lookup"><span data-stu-id="22de1-162">Available in Microsoft Defender for Endpoint version 100.67.60 or higher.</span></span> |

#### <a name="exclusion-merge-policy"></a><span data-ttu-id="22de1-163">Directiva de combinación de exclusión</span><span class="sxs-lookup"><span data-stu-id="22de1-163">Exclusion merge policy</span></span>

<span data-ttu-id="22de1-164">Especifique la directiva de combinación para exclusiones.</span><span class="sxs-lookup"><span data-stu-id="22de1-164">Specify the merge policy for exclusions.</span></span> <span data-ttu-id="22de1-165">Puede ser una combinación de exclusiones definidas por el administrador y definidas por el usuario ( ) o solo `merge` exclusiones definidas por el administrador ( `admin_only` ).</span><span class="sxs-lookup"><span data-stu-id="22de1-165">This can be a combination of administrator-defined and user-defined exclusions (`merge`) or only administrator-defined exclusions (`admin_only`).</span></span> <span data-ttu-id="22de1-166">Esta configuración se puede usar para restringir que los usuarios locales definan sus propias exclusiones.</span><span class="sxs-lookup"><span data-stu-id="22de1-166">This setting can be used to restrict local users from defining their own exclusions.</span></span>

|<span data-ttu-id="22de1-167">Sección</span><span class="sxs-lookup"><span data-stu-id="22de1-167">Section</span></span>|<span data-ttu-id="22de1-168">Valor</span><span class="sxs-lookup"><span data-stu-id="22de1-168">Value</span></span>|
|:---|:---|
| <span data-ttu-id="22de1-169">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="22de1-169">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="22de1-170">**Key**</span><span class="sxs-lookup"><span data-stu-id="22de1-170">**Key**</span></span> | <span data-ttu-id="22de1-171">exclusionsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="22de1-171">exclusionsMergePolicy</span></span> |
| <span data-ttu-id="22de1-172">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="22de1-172">**Data type**</span></span> | <span data-ttu-id="22de1-173">Cadena</span><span class="sxs-lookup"><span data-stu-id="22de1-173">String</span></span> |
| <span data-ttu-id="22de1-174">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="22de1-174">**Possible values**</span></span> | <span data-ttu-id="22de1-175">merge (valor predeterminado)</span><span class="sxs-lookup"><span data-stu-id="22de1-175">merge (default)</span></span> <br/> <span data-ttu-id="22de1-176">admin_only</span><span class="sxs-lookup"><span data-stu-id="22de1-176">admin_only</span></span> |
| <span data-ttu-id="22de1-177">**Comments**</span><span class="sxs-lookup"><span data-stu-id="22de1-177">**Comments**</span></span> | <span data-ttu-id="22de1-178">Disponible en Microsoft Defender para endpoint versión 100.83.73 o posterior.</span><span class="sxs-lookup"><span data-stu-id="22de1-178">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="scan-exclusions"></a><span data-ttu-id="22de1-179">Exclusiones de examen</span><span class="sxs-lookup"><span data-stu-id="22de1-179">Scan exclusions</span></span>

<span data-ttu-id="22de1-180">Especifique las entidades que no se han analizado.</span><span class="sxs-lookup"><span data-stu-id="22de1-180">Specify entities excluded from being scanned.</span></span> <span data-ttu-id="22de1-181">Las exclusiones se pueden especificar por rutas de acceso completas, extensiones o nombres de archivo.</span><span class="sxs-lookup"><span data-stu-id="22de1-181">Exclusions can be specified by full paths, extensions, or file names.</span></span>
<span data-ttu-id="22de1-182">(Las exclusiones se especifican como una matriz de elementos, el administrador puede especificar tantos elementos como sea necesario, en cualquier orden).</span><span class="sxs-lookup"><span data-stu-id="22de1-182">(Exclusions are specified as an array of items, administrator can specify as many elements as necessary, in any order.)</span></span>

|<span data-ttu-id="22de1-183">Sección</span><span class="sxs-lookup"><span data-stu-id="22de1-183">Section</span></span>|<span data-ttu-id="22de1-184">Valor</span><span class="sxs-lookup"><span data-stu-id="22de1-184">Value</span></span>|
|:---|:---|
| <span data-ttu-id="22de1-185">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="22de1-185">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="22de1-186">**Key**</span><span class="sxs-lookup"><span data-stu-id="22de1-186">**Key**</span></span> | <span data-ttu-id="22de1-187">exclusiones</span><span class="sxs-lookup"><span data-stu-id="22de1-187">exclusions</span></span> |
| <span data-ttu-id="22de1-188">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="22de1-188">**Data type**</span></span> | <span data-ttu-id="22de1-189">Diccionario (preferencia anidada)</span><span class="sxs-lookup"><span data-stu-id="22de1-189">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="22de1-190">**Comments**</span><span class="sxs-lookup"><span data-stu-id="22de1-190">**Comments**</span></span> | <span data-ttu-id="22de1-191">Vea las secciones siguientes para obtener una descripción del contenido del diccionario.</span><span class="sxs-lookup"><span data-stu-id="22de1-191">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="type-of-exclusion"></a><span data-ttu-id="22de1-192">Tipo de exclusión</span><span class="sxs-lookup"><span data-stu-id="22de1-192">Type of exclusion</span></span>

<span data-ttu-id="22de1-193">Especifique el contenido excluido de ser examinado por tipo.</span><span class="sxs-lookup"><span data-stu-id="22de1-193">Specify content excluded from being scanned by type.</span></span>

|<span data-ttu-id="22de1-194">Sección</span><span class="sxs-lookup"><span data-stu-id="22de1-194">Section</span></span>|<span data-ttu-id="22de1-195">Valor</span><span class="sxs-lookup"><span data-stu-id="22de1-195">Value</span></span>|
|:---|:---|
| <span data-ttu-id="22de1-196">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="22de1-196">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="22de1-197">**Key**</span><span class="sxs-lookup"><span data-stu-id="22de1-197">**Key**</span></span> | <span data-ttu-id="22de1-198">$type</span><span class="sxs-lookup"><span data-stu-id="22de1-198">$type</span></span> |
| <span data-ttu-id="22de1-199">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="22de1-199">**Data type**</span></span> | <span data-ttu-id="22de1-200">Cadena</span><span class="sxs-lookup"><span data-stu-id="22de1-200">String</span></span> |
| <span data-ttu-id="22de1-201">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="22de1-201">**Possible values**</span></span> | <span data-ttu-id="22de1-202">excludedPath</span><span class="sxs-lookup"><span data-stu-id="22de1-202">excludedPath</span></span> <br/> <span data-ttu-id="22de1-203">excludedFileExtension</span><span class="sxs-lookup"><span data-stu-id="22de1-203">excludedFileExtension</span></span> <br/> <span data-ttu-id="22de1-204">excludedFileName</span><span class="sxs-lookup"><span data-stu-id="22de1-204">excludedFileName</span></span> |

##### <a name="path-to-excluded-content"></a><span data-ttu-id="22de1-205">Ruta de acceso al contenido excluido</span><span class="sxs-lookup"><span data-stu-id="22de1-205">Path to excluded content</span></span>

<span data-ttu-id="22de1-206">Especifique el contenido excluido de ser examinado por la ruta de acceso de archivo completa.</span><span class="sxs-lookup"><span data-stu-id="22de1-206">Specify content excluded from being scanned by full file path.</span></span>

|<span data-ttu-id="22de1-207">Sección</span><span class="sxs-lookup"><span data-stu-id="22de1-207">Section</span></span>|<span data-ttu-id="22de1-208">Valor</span><span class="sxs-lookup"><span data-stu-id="22de1-208">Value</span></span>|
|:---|:---|
| <span data-ttu-id="22de1-209">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="22de1-209">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="22de1-210">**Key**</span><span class="sxs-lookup"><span data-stu-id="22de1-210">**Key**</span></span> | <span data-ttu-id="22de1-211">path</span><span class="sxs-lookup"><span data-stu-id="22de1-211">path</span></span> |
| <span data-ttu-id="22de1-212">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="22de1-212">**Data type**</span></span> | <span data-ttu-id="22de1-213">Cadena</span><span class="sxs-lookup"><span data-stu-id="22de1-213">String</span></span> |
| <span data-ttu-id="22de1-214">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="22de1-214">**Possible values**</span></span> | <span data-ttu-id="22de1-215">rutas de acceso válidas</span><span class="sxs-lookup"><span data-stu-id="22de1-215">valid paths</span></span> |
| <span data-ttu-id="22de1-216">**Comments**</span><span class="sxs-lookup"><span data-stu-id="22de1-216">**Comments**</span></span> | <span data-ttu-id="22de1-217">Aplicable solo *si $type* *se excluyePath*</span><span class="sxs-lookup"><span data-stu-id="22de1-217">Applicable only if *$type* is *excludedPath*</span></span> |

## <a name="supported-exclusion-types"></a><span data-ttu-id="22de1-218">Tipos de exclusión admitidos</span><span class="sxs-lookup"><span data-stu-id="22de1-218">Supported exclusion types</span></span>

<span data-ttu-id="22de1-219">En la tabla siguiente se muestran los tipos de exclusión admitidos por Defender para Endpoint en Mac.</span><span class="sxs-lookup"><span data-stu-id="22de1-219">The follow table shows the exclusion types supported by Defender for Endpoint on Mac.</span></span>

<span data-ttu-id="22de1-220">Exclusión</span><span class="sxs-lookup"><span data-stu-id="22de1-220">Exclusion</span></span> | <span data-ttu-id="22de1-221">Definición</span><span class="sxs-lookup"><span data-stu-id="22de1-221">Definition</span></span> | <span data-ttu-id="22de1-222">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="22de1-222">Examples</span></span>
---|---|---
<span data-ttu-id="22de1-223">Extensión de archivo</span><span class="sxs-lookup"><span data-stu-id="22de1-223">File extension</span></span> | <span data-ttu-id="22de1-224">Todos los archivos con la extensión, en cualquier lugar del dispositivo</span><span class="sxs-lookup"><span data-stu-id="22de1-224">All files with the extension, anywhere on the device</span></span> | `.test`
<span data-ttu-id="22de1-225">Archivo</span><span class="sxs-lookup"><span data-stu-id="22de1-225">File</span></span> | <span data-ttu-id="22de1-226">Un archivo específico identificado por la ruta de acceso completa</span><span class="sxs-lookup"><span data-stu-id="22de1-226">A specific file identified by the full path</span></span> | `/var/log/test.log`<br/>`/var/log/*.log`<br/>`/var/log/install.?.log`
<span data-ttu-id="22de1-227">Carpeta</span><span class="sxs-lookup"><span data-stu-id="22de1-227">Folder</span></span> | <span data-ttu-id="22de1-228">Todos los archivos de la carpeta especificada (recursivamente)</span><span class="sxs-lookup"><span data-stu-id="22de1-228">All files under the specified folder (recursively)</span></span> | `/var/log/`<br/>`/var/*/`
<span data-ttu-id="22de1-229">Proceso</span><span class="sxs-lookup"><span data-stu-id="22de1-229">Process</span></span> | <span data-ttu-id="22de1-230">Un proceso específico (especificado por la ruta de acceso completa o el nombre de archivo) y todos los archivos abiertos por él</span><span class="sxs-lookup"><span data-stu-id="22de1-230">A specific process (specified either by the full path or file name) and all files opened by it</span></span> | `/bin/cat`<br/>`cat`<br/>`c?t`

> [!IMPORTANT]
> <span data-ttu-id="22de1-231">Las rutas anteriores deben ser vínculos duros, no vínculos simbólicos, para poder excluirse correctamente.</span><span class="sxs-lookup"><span data-stu-id="22de1-231">The paths above must be hard links, not symbolic links, in order to be successfully excluded.</span></span> <span data-ttu-id="22de1-232">Puede comprobar si una ruta de acceso es un vínculo simbólico ejecutando `file <path-name>` .</span><span class="sxs-lookup"><span data-stu-id="22de1-232">You can check if a path is a symbolic link by running `file <path-name>`.</span></span>

<span data-ttu-id="22de1-233">Las exclusiones de archivos, carpetas y procesos admiten los siguientes caracteres comodín:</span><span class="sxs-lookup"><span data-stu-id="22de1-233">File, folder, and process exclusions support the following wildcards:</span></span>

<span data-ttu-id="22de1-234">Carácter comodín</span><span class="sxs-lookup"><span data-stu-id="22de1-234">Wildcard</span></span> | <span data-ttu-id="22de1-235">Description</span><span class="sxs-lookup"><span data-stu-id="22de1-235">Description</span></span> | <span data-ttu-id="22de1-236">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="22de1-236">Example</span></span> | <span data-ttu-id="22de1-237">Coincidencias</span><span class="sxs-lookup"><span data-stu-id="22de1-237">Matches</span></span> | <span data-ttu-id="22de1-238">No coincide</span><span class="sxs-lookup"><span data-stu-id="22de1-238">Does not match</span></span>
---|---|---|---|---
\* |    <span data-ttu-id="22de1-239">Coincide con cualquier número de caracteres, incluido ninguno (tenga en cuenta que cuando se usa este comodín dentro de una ruta de acceso, solo sustituirá una carpeta)</span><span class="sxs-lookup"><span data-stu-id="22de1-239">Matches any number of any characters including none (note that when this wildcard is used inside a path it will substitute only one folder)</span></span> | `/var/\*/\*.log` | `/var/log/system.log` | `/var/log/nested/system.log`
<span data-ttu-id="22de1-240">?</span><span class="sxs-lookup"><span data-stu-id="22de1-240">?</span></span> | <span data-ttu-id="22de1-241">Coincide con cualquier carácter</span><span class="sxs-lookup"><span data-stu-id="22de1-241">Matches any single character</span></span> | `file?.log` | `file1.log`<br/>`file2.log` | `file123.log`

##### <a name="path-type-file--directory"></a><span data-ttu-id="22de1-242">Tipo de ruta de acceso (archivo/directorio)</span><span class="sxs-lookup"><span data-stu-id="22de1-242">Path type (file / directory)</span></span>

<span data-ttu-id="22de1-243">Indica si la *propiedad path* hace referencia a un archivo o directorio.</span><span class="sxs-lookup"><span data-stu-id="22de1-243">Indicate if the *path* property refers to a file or directory.</span></span> 

|<span data-ttu-id="22de1-244">Sección</span><span class="sxs-lookup"><span data-stu-id="22de1-244">Section</span></span>|<span data-ttu-id="22de1-245">Valor</span><span class="sxs-lookup"><span data-stu-id="22de1-245">Value</span></span>|
|:---|:---|
| <span data-ttu-id="22de1-246">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="22de1-246">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="22de1-247">**Key**</span><span class="sxs-lookup"><span data-stu-id="22de1-247">**Key**</span></span> | <span data-ttu-id="22de1-248">isDirectory</span><span class="sxs-lookup"><span data-stu-id="22de1-248">isDirectory</span></span> |
| <span data-ttu-id="22de1-249">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="22de1-249">**Data type**</span></span> | <span data-ttu-id="22de1-250">Booleano</span><span class="sxs-lookup"><span data-stu-id="22de1-250">Boolean</span></span> |
| <span data-ttu-id="22de1-251">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="22de1-251">**Possible values**</span></span> | <span data-ttu-id="22de1-252">false (predeterminado)</span><span class="sxs-lookup"><span data-stu-id="22de1-252">false (default)</span></span> <br/> <span data-ttu-id="22de1-253">true</span><span class="sxs-lookup"><span data-stu-id="22de1-253">true</span></span> |
| <span data-ttu-id="22de1-254">**Comments**</span><span class="sxs-lookup"><span data-stu-id="22de1-254">**Comments**</span></span> | <span data-ttu-id="22de1-255">Aplicable solo *si $type* *se excluyePath*</span><span class="sxs-lookup"><span data-stu-id="22de1-255">Applicable only if *$type* is *excludedPath*</span></span> |

##### <a name="file-extension-excluded-from-the-scan"></a><span data-ttu-id="22de1-256">Extensión de archivo excluida del examen</span><span class="sxs-lookup"><span data-stu-id="22de1-256">File extension excluded from the scan</span></span>

<span data-ttu-id="22de1-257">Especifique el contenido excluido de la extensión de archivo.</span><span class="sxs-lookup"><span data-stu-id="22de1-257">Specify content excluded from being scanned by file extension.</span></span>

|<span data-ttu-id="22de1-258">Sección</span><span class="sxs-lookup"><span data-stu-id="22de1-258">Section</span></span>|<span data-ttu-id="22de1-259">Valor</span><span class="sxs-lookup"><span data-stu-id="22de1-259">Value</span></span>|
|:---|:---|
| <span data-ttu-id="22de1-260">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="22de1-260">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="22de1-261">**Key**</span><span class="sxs-lookup"><span data-stu-id="22de1-261">**Key**</span></span> | <span data-ttu-id="22de1-262">extensión</span><span class="sxs-lookup"><span data-stu-id="22de1-262">extension</span></span> |
| <span data-ttu-id="22de1-263">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="22de1-263">**Data type**</span></span> | <span data-ttu-id="22de1-264">Cadena</span><span class="sxs-lookup"><span data-stu-id="22de1-264">String</span></span> |
| <span data-ttu-id="22de1-265">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="22de1-265">**Possible values**</span></span> | <span data-ttu-id="22de1-266">extensiones de archivo válidas</span><span class="sxs-lookup"><span data-stu-id="22de1-266">valid file extensions</span></span> |
| <span data-ttu-id="22de1-267">**Comments**</span><span class="sxs-lookup"><span data-stu-id="22de1-267">**Comments**</span></span> | <span data-ttu-id="22de1-268">Aplicable solo *si $type* *se excluyeFileExtension*</span><span class="sxs-lookup"><span data-stu-id="22de1-268">Applicable only if *$type* is *excludedFileExtension*</span></span> |

##### <a name="process-excluded-from-the-scan"></a><span data-ttu-id="22de1-269">Proceso excluido del examen</span><span class="sxs-lookup"><span data-stu-id="22de1-269">Process excluded from the scan</span></span>

<span data-ttu-id="22de1-270">Especifique un proceso para el que se excluya toda la actividad de archivo del examen.</span><span class="sxs-lookup"><span data-stu-id="22de1-270">Specify a process for which all file activity is excluded from scanning.</span></span> <span data-ttu-id="22de1-271">El proceso puede especificarse por su nombre (por ejemplo) o por la ruta de acceso `cat` completa (por ejemplo, `/bin/cat` ).</span><span class="sxs-lookup"><span data-stu-id="22de1-271">The process can be specified either by its name (e.g. `cat`) or full path (e.g. `/bin/cat`).</span></span>

|<span data-ttu-id="22de1-272">Sección</span><span class="sxs-lookup"><span data-stu-id="22de1-272">Section</span></span>|<span data-ttu-id="22de1-273">Valor</span><span class="sxs-lookup"><span data-stu-id="22de1-273">Value</span></span>|
|:---|:---|
| <span data-ttu-id="22de1-274">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="22de1-274">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="22de1-275">**Key**</span><span class="sxs-lookup"><span data-stu-id="22de1-275">**Key**</span></span> | <span data-ttu-id="22de1-276">name</span><span class="sxs-lookup"><span data-stu-id="22de1-276">name</span></span> |
| <span data-ttu-id="22de1-277">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="22de1-277">**Data type**</span></span> | <span data-ttu-id="22de1-278">Cadena</span><span class="sxs-lookup"><span data-stu-id="22de1-278">String</span></span> |
| <span data-ttu-id="22de1-279">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="22de1-279">**Possible values**</span></span> | <span data-ttu-id="22de1-280">cualquier cadena</span><span class="sxs-lookup"><span data-stu-id="22de1-280">any string</span></span> |
| <span data-ttu-id="22de1-281">**Comments**</span><span class="sxs-lookup"><span data-stu-id="22de1-281">**Comments**</span></span> | <span data-ttu-id="22de1-282">Aplicable solo *si $type* *se excluyeFileName*</span><span class="sxs-lookup"><span data-stu-id="22de1-282">Applicable only if *$type* is *excludedFileName*</span></span> |

#### <a name="allowed-threats"></a><span data-ttu-id="22de1-283">Amenazas permitidas</span><span class="sxs-lookup"><span data-stu-id="22de1-283">Allowed threats</span></span>

<span data-ttu-id="22de1-284">Especifica las amenazas por nombre que no estén bloqueadas por Defender para Endpoint en Mac.</span><span class="sxs-lookup"><span data-stu-id="22de1-284">Specify threats by name that are not blocked by Defender for Endpoint on Mac.</span></span> <span data-ttu-id="22de1-285">Estas amenazas podrán ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="22de1-285">These threats will be allowed to run.</span></span>

|<span data-ttu-id="22de1-286">Sección</span><span class="sxs-lookup"><span data-stu-id="22de1-286">Section</span></span>|<span data-ttu-id="22de1-287">Valor</span><span class="sxs-lookup"><span data-stu-id="22de1-287">Value</span></span>|
|:---|:---|
| <span data-ttu-id="22de1-288">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="22de1-288">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="22de1-289">**Key**</span><span class="sxs-lookup"><span data-stu-id="22de1-289">**Key**</span></span> | <span data-ttu-id="22de1-290">allowedThreats</span><span class="sxs-lookup"><span data-stu-id="22de1-290">allowedThreats</span></span> |
| <span data-ttu-id="22de1-291">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="22de1-291">**Data type**</span></span> | <span data-ttu-id="22de1-292">Matriz de cadenas</span><span class="sxs-lookup"><span data-stu-id="22de1-292">Array of strings</span></span> |

#### <a name="disallowed-threat-actions"></a><span data-ttu-id="22de1-293">Acciones de amenazas no permitidos</span><span class="sxs-lookup"><span data-stu-id="22de1-293">Disallowed threat actions</span></span>

<span data-ttu-id="22de1-294">Restringe las acciones que el usuario local de un dispositivo puede realizar cuando se detectan amenazas.</span><span class="sxs-lookup"><span data-stu-id="22de1-294">Restricts the actions that the local user of a device can take when threats are detected.</span></span> <span data-ttu-id="22de1-295">Las acciones incluidas en esta lista no se muestran en la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="22de1-295">The actions included in this list are not displayed in the user interface.</span></span>

|<span data-ttu-id="22de1-296">Sección</span><span class="sxs-lookup"><span data-stu-id="22de1-296">Section</span></span>|<span data-ttu-id="22de1-297">Valor</span><span class="sxs-lookup"><span data-stu-id="22de1-297">Value</span></span>|
|:---|:---|
| <span data-ttu-id="22de1-298">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="22de1-298">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="22de1-299">**Key**</span><span class="sxs-lookup"><span data-stu-id="22de1-299">**Key**</span></span> | <span data-ttu-id="22de1-300">disallowedThreatActions</span><span class="sxs-lookup"><span data-stu-id="22de1-300">disallowedThreatActions</span></span> |
| <span data-ttu-id="22de1-301">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="22de1-301">**Data type**</span></span> | <span data-ttu-id="22de1-302">Matriz de cadenas</span><span class="sxs-lookup"><span data-stu-id="22de1-302">Array of strings</span></span> |
| <span data-ttu-id="22de1-303">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="22de1-303">**Possible values**</span></span> | <span data-ttu-id="22de1-304">permitir (restringe a los usuarios permitir amenazas)</span><span class="sxs-lookup"><span data-stu-id="22de1-304">allow (restricts users from allowing threats)</span></span> <br/> <span data-ttu-id="22de1-305">restore (restringe a los usuarios la restauración de amenazas desde la cuarentena)</span><span class="sxs-lookup"><span data-stu-id="22de1-305">restore (restricts users from restoring threats from the quarantine)</span></span> |
| <span data-ttu-id="22de1-306">**Comments**</span><span class="sxs-lookup"><span data-stu-id="22de1-306">**Comments**</span></span> | <span data-ttu-id="22de1-307">Disponible en Microsoft Defender para endpoint versión 100.83.73 o posterior.</span><span class="sxs-lookup"><span data-stu-id="22de1-307">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="threat-type-settings"></a><span data-ttu-id="22de1-308">Configuración del tipo de amenaza</span><span class="sxs-lookup"><span data-stu-id="22de1-308">Threat type settings</span></span>

<span data-ttu-id="22de1-309">Especifica cómo se controlan determinados tipos de amenazas por Microsoft Defender para Endpoint en macOS.</span><span class="sxs-lookup"><span data-stu-id="22de1-309">Specify how certain threat types are handled by Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="22de1-310">Sección</span><span class="sxs-lookup"><span data-stu-id="22de1-310">Section</span></span>|<span data-ttu-id="22de1-311">Valor</span><span class="sxs-lookup"><span data-stu-id="22de1-311">Value</span></span>|
|:---|:---|
| <span data-ttu-id="22de1-312">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="22de1-312">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="22de1-313">**Key**</span><span class="sxs-lookup"><span data-stu-id="22de1-313">**Key**</span></span> | <span data-ttu-id="22de1-314">threatTypeSettings</span><span class="sxs-lookup"><span data-stu-id="22de1-314">threatTypeSettings</span></span> |
| <span data-ttu-id="22de1-315">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="22de1-315">**Data type**</span></span> | <span data-ttu-id="22de1-316">Diccionario (preferencia anidada)</span><span class="sxs-lookup"><span data-stu-id="22de1-316">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="22de1-317">**Comments**</span><span class="sxs-lookup"><span data-stu-id="22de1-317">**Comments**</span></span> | <span data-ttu-id="22de1-318">Vea las secciones siguientes para obtener una descripción del contenido del diccionario.</span><span class="sxs-lookup"><span data-stu-id="22de1-318">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="threat-type"></a><span data-ttu-id="22de1-319">Tipo de amenaza</span><span class="sxs-lookup"><span data-stu-id="22de1-319">Threat type</span></span>

<span data-ttu-id="22de1-320">Especifique tipos de amenazas.</span><span class="sxs-lookup"><span data-stu-id="22de1-320">Specify threat types.</span></span>

|<span data-ttu-id="22de1-321">Sección</span><span class="sxs-lookup"><span data-stu-id="22de1-321">Section</span></span>|<span data-ttu-id="22de1-322">Valor</span><span class="sxs-lookup"><span data-stu-id="22de1-322">Value</span></span>|
|:---|:---|
| <span data-ttu-id="22de1-323">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="22de1-323">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="22de1-324">**Key**</span><span class="sxs-lookup"><span data-stu-id="22de1-324">**Key**</span></span> | <span data-ttu-id="22de1-325">clave</span><span class="sxs-lookup"><span data-stu-id="22de1-325">key</span></span> |
| <span data-ttu-id="22de1-326">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="22de1-326">**Data type**</span></span> | <span data-ttu-id="22de1-327">Cadena</span><span class="sxs-lookup"><span data-stu-id="22de1-327">String</span></span> |
| <span data-ttu-id="22de1-328">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="22de1-328">**Possible values**</span></span> | <span data-ttu-id="22de1-329">potentially_unwanted_application</span><span class="sxs-lookup"><span data-stu-id="22de1-329">potentially_unwanted_application</span></span> <br/> <span data-ttu-id="22de1-330">archive_bomb</span><span class="sxs-lookup"><span data-stu-id="22de1-330">archive_bomb</span></span> |

##### <a name="action-to-take"></a><span data-ttu-id="22de1-331">Acción que puede realizar</span><span class="sxs-lookup"><span data-stu-id="22de1-331">Action to take</span></span>

<span data-ttu-id="22de1-332">Especifique qué acción realizar cuando se detecte una amenaza del tipo especificado en la sección anterior.</span><span class="sxs-lookup"><span data-stu-id="22de1-332">Specify what action to take when a threat of the type specified in the preceding section is detected.</span></span> <span data-ttu-id="22de1-333">Seleccione una de las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="22de1-333">Choose from the following options:</span></span>

- <span data-ttu-id="22de1-334">**Auditoría:** el dispositivo no está protegido contra este tipo de amenaza, pero se registra una entrada sobre la amenaza.</span><span class="sxs-lookup"><span data-stu-id="22de1-334">**Audit**: your device is not protected against this type of threat, but an entry about the threat is logged.</span></span>
- <span data-ttu-id="22de1-335">**Bloquear:** el dispositivo está protegido contra este tipo de amenaza y se te notificará en la interfaz de usuario y en la consola de seguridad.</span><span class="sxs-lookup"><span data-stu-id="22de1-335">**Block**: your device is protected against this type of threat and you are notified in the user interface and the security console.</span></span>
- <span data-ttu-id="22de1-336">**Desactivado:** el dispositivo no está protegido contra este tipo de amenaza y no se registra nada.</span><span class="sxs-lookup"><span data-stu-id="22de1-336">**Off**: your device is not protected against this type of threat and nothing is logged.</span></span>

|<span data-ttu-id="22de1-337">Sección</span><span class="sxs-lookup"><span data-stu-id="22de1-337">Section</span></span>|<span data-ttu-id="22de1-338">Valor</span><span class="sxs-lookup"><span data-stu-id="22de1-338">Value</span></span>|
|:---|:---|
| <span data-ttu-id="22de1-339">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="22de1-339">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="22de1-340">**Key**</span><span class="sxs-lookup"><span data-stu-id="22de1-340">**Key**</span></span> | <span data-ttu-id="22de1-341">valor</span><span class="sxs-lookup"><span data-stu-id="22de1-341">value</span></span> |
| <span data-ttu-id="22de1-342">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="22de1-342">**Data type**</span></span> | <span data-ttu-id="22de1-343">Cadena</span><span class="sxs-lookup"><span data-stu-id="22de1-343">String</span></span> |
| <span data-ttu-id="22de1-344">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="22de1-344">**Possible values**</span></span> | <span data-ttu-id="22de1-345">auditoría (valor predeterminado)</span><span class="sxs-lookup"><span data-stu-id="22de1-345">audit (default)</span></span> <br/> <span data-ttu-id="22de1-346">bloque</span><span class="sxs-lookup"><span data-stu-id="22de1-346">block</span></span> <br/> <span data-ttu-id="22de1-347">off</span><span class="sxs-lookup"><span data-stu-id="22de1-347">off</span></span> |

#### <a name="threat-type-settings-merge-policy"></a><span data-ttu-id="22de1-348">Directiva de combinación de configuración de tipo de amenaza</span><span class="sxs-lookup"><span data-stu-id="22de1-348">Threat type settings merge policy</span></span>

<span data-ttu-id="22de1-349">Especifique la directiva de combinación para la configuración del tipo de amenaza.</span><span class="sxs-lookup"><span data-stu-id="22de1-349">Specify the merge policy for threat type settings.</span></span> <span data-ttu-id="22de1-350">Puede ser una combinación de opciones definidas por el administrador y definidas por el usuario ( ) o solo opciones definidas `merge` por el administrador ( `admin_only` ).</span><span class="sxs-lookup"><span data-stu-id="22de1-350">This can be a combination of administrator-defined and user-defined settings (`merge`) or only administrator-defined settings (`admin_only`).</span></span> <span data-ttu-id="22de1-351">Esta configuración se puede usar para restringir que los usuarios locales definan su propia configuración para diferentes tipos de amenazas.</span><span class="sxs-lookup"><span data-stu-id="22de1-351">This setting can be used to restrict local users from defining their own settings for different threat types.</span></span>

|<span data-ttu-id="22de1-352">Sección</span><span class="sxs-lookup"><span data-stu-id="22de1-352">Section</span></span>|<span data-ttu-id="22de1-353">Valor</span><span class="sxs-lookup"><span data-stu-id="22de1-353">Value</span></span>|
|:---|:---|
| <span data-ttu-id="22de1-354">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="22de1-354">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="22de1-355">**Key**</span><span class="sxs-lookup"><span data-stu-id="22de1-355">**Key**</span></span> | <span data-ttu-id="22de1-356">threatTypeSettingsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="22de1-356">threatTypeSettingsMergePolicy</span></span> |
| <span data-ttu-id="22de1-357">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="22de1-357">**Data type**</span></span> | <span data-ttu-id="22de1-358">Cadena</span><span class="sxs-lookup"><span data-stu-id="22de1-358">String</span></span> |
| <span data-ttu-id="22de1-359">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="22de1-359">**Possible values**</span></span> | <span data-ttu-id="22de1-360">merge (valor predeterminado)</span><span class="sxs-lookup"><span data-stu-id="22de1-360">merge (default)</span></span> <br/> <span data-ttu-id="22de1-361">admin_only</span><span class="sxs-lookup"><span data-stu-id="22de1-361">admin_only</span></span> |
| <span data-ttu-id="22de1-362">**Comments**</span><span class="sxs-lookup"><span data-stu-id="22de1-362">**Comments**</span></span> | <span data-ttu-id="22de1-363">Disponible en Microsoft Defender para endpoint versión 100.83.73 o posterior.</span><span class="sxs-lookup"><span data-stu-id="22de1-363">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="antivirus-scan-history-retention-in-days"></a><span data-ttu-id="22de1-364">Retención del historial de examen antivirus (en días)</span><span class="sxs-lookup"><span data-stu-id="22de1-364">Antivirus scan history retention (in days)</span></span>

<span data-ttu-id="22de1-365">Especifica el número de días que los resultados se conservan en el historial de examen del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="22de1-365">Specify the number of days that results are retained in the scan history on the device.</span></span> <span data-ttu-id="22de1-366">Los resultados del examen antiguos se quitan del historial.</span><span class="sxs-lookup"><span data-stu-id="22de1-366">Old scan results are removed from the history.</span></span> <span data-ttu-id="22de1-367">Archivos antiguos en cuarentena que también se quitan del disco.</span><span class="sxs-lookup"><span data-stu-id="22de1-367">Old quarantined files that are also removed from the disk.</span></span>

|<span data-ttu-id="22de1-368">Sección</span><span class="sxs-lookup"><span data-stu-id="22de1-368">Section</span></span>|<span data-ttu-id="22de1-369">Valor</span><span class="sxs-lookup"><span data-stu-id="22de1-369">Value</span></span>|
|:---|:---|
| <span data-ttu-id="22de1-370">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="22de1-370">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="22de1-371">**Key**</span><span class="sxs-lookup"><span data-stu-id="22de1-371">**Key**</span></span> | <span data-ttu-id="22de1-372">scanResultsRetentionDays</span><span class="sxs-lookup"><span data-stu-id="22de1-372">scanResultsRetentionDays</span></span> |
| <span data-ttu-id="22de1-373">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="22de1-373">**Data type**</span></span> | <span data-ttu-id="22de1-374">Cadena</span><span class="sxs-lookup"><span data-stu-id="22de1-374">String</span></span> |
| <span data-ttu-id="22de1-375">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="22de1-375">**Possible values**</span></span> | <span data-ttu-id="22de1-376">90 (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="22de1-376">90 (default).</span></span> <span data-ttu-id="22de1-377">Los valores permitidos van de 1 día a 180 días.</span><span class="sxs-lookup"><span data-stu-id="22de1-377">Allowed values are from 1 day to 180 days.</span></span> |
| <span data-ttu-id="22de1-378">**Comments**</span><span class="sxs-lookup"><span data-stu-id="22de1-378">**Comments**</span></span> | <span data-ttu-id="22de1-379">Disponible en Microsoft Defender para endpoint versión 101.07.23 o posterior.</span><span class="sxs-lookup"><span data-stu-id="22de1-379">Available in Microsoft Defender for Endpoint version 101.07.23 or higher.</span></span> |

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a><span data-ttu-id="22de1-380">Número máximo de elementos en el historial de examen antivirus</span><span class="sxs-lookup"><span data-stu-id="22de1-380">Maximum number of items in the antivirus scan history</span></span>

<span data-ttu-id="22de1-381">Especifique el número máximo de entradas que se deben conservar en el historial de examen.</span><span class="sxs-lookup"><span data-stu-id="22de1-381">Specify the maximum number of entries to keep in the scan history.</span></span> <span data-ttu-id="22de1-382">Las entradas incluyen todos los exámenes a petición realizados en el pasado y todas las detecciones de antivirus.</span><span class="sxs-lookup"><span data-stu-id="22de1-382">Entries include all on-demand scans performed in the past and all antivirus detections.</span></span>

|<span data-ttu-id="22de1-383">Sección</span><span class="sxs-lookup"><span data-stu-id="22de1-383">Section</span></span>|<span data-ttu-id="22de1-384">Valor</span><span class="sxs-lookup"><span data-stu-id="22de1-384">Value</span></span>|
|:---|:---|
| <span data-ttu-id="22de1-385">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="22de1-385">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="22de1-386">**Key**</span><span class="sxs-lookup"><span data-stu-id="22de1-386">**Key**</span></span> | <span data-ttu-id="22de1-387">scanHistoryMaximumItems</span><span class="sxs-lookup"><span data-stu-id="22de1-387">scanHistoryMaximumItems</span></span> |
| <span data-ttu-id="22de1-388">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="22de1-388">**Data type**</span></span> | <span data-ttu-id="22de1-389">Cadena</span><span class="sxs-lookup"><span data-stu-id="22de1-389">String</span></span> |
| <span data-ttu-id="22de1-390">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="22de1-390">**Possible values**</span></span> | <span data-ttu-id="22de1-391">10000 (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="22de1-391">10000 (default).</span></span> <span data-ttu-id="22de1-392">Los valores permitidos van de 5000 elementos a 15000 elementos.</span><span class="sxs-lookup"><span data-stu-id="22de1-392">Allowed values are from 5000 items to 15000 items.</span></span> |
| <span data-ttu-id="22de1-393">**Comments**</span><span class="sxs-lookup"><span data-stu-id="22de1-393">**Comments**</span></span> | <span data-ttu-id="22de1-394">Disponible en Microsoft Defender para endpoint versión 101.07.23 o posterior.</span><span class="sxs-lookup"><span data-stu-id="22de1-394">Available in Microsoft Defender for Endpoint version 101.07.23 or higher.</span></span> |

### <a name="cloud-delivered-protection-preferences"></a><span data-ttu-id="22de1-395">Preferencias de protección entregadas en la nube</span><span class="sxs-lookup"><span data-stu-id="22de1-395">Cloud-delivered protection preferences</span></span>

<span data-ttu-id="22de1-396">Configure las características de protección controlada por la nube de Microsoft Defender para Endpoint en macOS.</span><span class="sxs-lookup"><span data-stu-id="22de1-396">Configure the cloud-driven protection features of Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="22de1-397">Sección</span><span class="sxs-lookup"><span data-stu-id="22de1-397">Section</span></span>|<span data-ttu-id="22de1-398">Valor</span><span class="sxs-lookup"><span data-stu-id="22de1-398">Value</span></span>|
|:---|:---|
| <span data-ttu-id="22de1-399">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="22de1-399">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="22de1-400">**Key**</span><span class="sxs-lookup"><span data-stu-id="22de1-400">**Key**</span></span> | <span data-ttu-id="22de1-401">cloudService</span><span class="sxs-lookup"><span data-stu-id="22de1-401">cloudService</span></span> |
| <span data-ttu-id="22de1-402">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="22de1-402">**Data type**</span></span> | <span data-ttu-id="22de1-403">Diccionario (preferencia anidada)</span><span class="sxs-lookup"><span data-stu-id="22de1-403">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="22de1-404">**Comments**</span><span class="sxs-lookup"><span data-stu-id="22de1-404">**Comments**</span></span> | <span data-ttu-id="22de1-405">Vea las secciones siguientes para obtener una descripción del contenido del diccionario.</span><span class="sxs-lookup"><span data-stu-id="22de1-405">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="enable--disable-cloud-delivered-protection"></a><span data-ttu-id="22de1-406">Habilitar o deshabilitar la protección entregada en la nube</span><span class="sxs-lookup"><span data-stu-id="22de1-406">Enable / disable cloud-delivered protection</span></span>

<span data-ttu-id="22de1-407">Especifica si se va a habilitar la protección entregada en la nube del dispositivo o no.</span><span class="sxs-lookup"><span data-stu-id="22de1-407">Specify whether to enable cloud-delivered protection the device or not.</span></span> <span data-ttu-id="22de1-408">Para mejorar la seguridad de los servicios, se recomienda mantener activada esta característica.</span><span class="sxs-lookup"><span data-stu-id="22de1-408">To improve the security of your services, we recommend keeping this feature turned on.</span></span>

|<span data-ttu-id="22de1-409">Sección</span><span class="sxs-lookup"><span data-stu-id="22de1-409">Section</span></span>|<span data-ttu-id="22de1-410">Valor</span><span class="sxs-lookup"><span data-stu-id="22de1-410">Value</span></span>|
|:---|:---|
| <span data-ttu-id="22de1-411">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="22de1-411">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="22de1-412">**Key**</span><span class="sxs-lookup"><span data-stu-id="22de1-412">**Key**</span></span> | <span data-ttu-id="22de1-413">habilitado</span><span class="sxs-lookup"><span data-stu-id="22de1-413">enabled</span></span> |
| <span data-ttu-id="22de1-414">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="22de1-414">**Data type**</span></span> | <span data-ttu-id="22de1-415">Booleano</span><span class="sxs-lookup"><span data-stu-id="22de1-415">Boolean</span></span> |
| <span data-ttu-id="22de1-416">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="22de1-416">**Possible values**</span></span> | <span data-ttu-id="22de1-417">true (valor predeterminado)</span><span class="sxs-lookup"><span data-stu-id="22de1-417">true (default)</span></span> <br/> <span data-ttu-id="22de1-418">false</span><span class="sxs-lookup"><span data-stu-id="22de1-418">false</span></span> |

#### <a name="diagnostic-collection-level"></a><span data-ttu-id="22de1-419">Nivel de colección de diagnóstico</span><span class="sxs-lookup"><span data-stu-id="22de1-419">Diagnostic collection level</span></span>

<span data-ttu-id="22de1-420">Los datos de diagnóstico se usan para mantener Microsoft Defender for Endpoint seguro y actualizado, detectar, diagnosticar y corregir problemas y también realizar mejoras en el producto.</span><span class="sxs-lookup"><span data-stu-id="22de1-420">Diagnostic data is used to keep Microsoft Defender for Endpoint secure and up-to-date, detect, diagnose and fix problems, and also make product improvements.</span></span> <span data-ttu-id="22de1-421">Esta configuración determina el nivel de diagnóstico enviado por Microsoft Defender para Endpoint a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="22de1-421">This setting determines the level of diagnostics sent by Microsoft Defender for Endpoint to Microsoft.</span></span>

|<span data-ttu-id="22de1-422">Sección</span><span class="sxs-lookup"><span data-stu-id="22de1-422">Section</span></span>|<span data-ttu-id="22de1-423">Valor</span><span class="sxs-lookup"><span data-stu-id="22de1-423">Value</span></span>|
|:---|:---|
| <span data-ttu-id="22de1-424">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="22de1-424">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="22de1-425">**Key**</span><span class="sxs-lookup"><span data-stu-id="22de1-425">**Key**</span></span> | <span data-ttu-id="22de1-426">diagnosticLevel</span><span class="sxs-lookup"><span data-stu-id="22de1-426">diagnosticLevel</span></span> |
| <span data-ttu-id="22de1-427">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="22de1-427">**Data type**</span></span> | <span data-ttu-id="22de1-428">Cadena</span><span class="sxs-lookup"><span data-stu-id="22de1-428">String</span></span> |
| <span data-ttu-id="22de1-429">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="22de1-429">**Possible values**</span></span> | <span data-ttu-id="22de1-430">opcional (predeterminado)</span><span class="sxs-lookup"><span data-stu-id="22de1-430">optional (default)</span></span> <br/> <span data-ttu-id="22de1-431">necesario</span><span class="sxs-lookup"><span data-stu-id="22de1-431">required</span></span> |

#### <a name="enable--disable-automatic-sample-submissions"></a><span data-ttu-id="22de1-432">Habilitar o deshabilitar envíos de ejemplo automáticos</span><span class="sxs-lookup"><span data-stu-id="22de1-432">Enable / disable automatic sample submissions</span></span>

<span data-ttu-id="22de1-433">Determina si se envían muestras sospechosas (que probablemente contengan amenazas) a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="22de1-433">Determines whether suspicious samples (that are likely to contain threats) are sent to Microsoft.</span></span> <span data-ttu-id="22de1-434">Se le preguntará si es probable que el archivo enviado contenga información personal.</span><span class="sxs-lookup"><span data-stu-id="22de1-434">You are prompted if the submitted file is likely to contain personal information.</span></span>

|<span data-ttu-id="22de1-435">Sección</span><span class="sxs-lookup"><span data-stu-id="22de1-435">Section</span></span>|<span data-ttu-id="22de1-436">Valor</span><span class="sxs-lookup"><span data-stu-id="22de1-436">Value</span></span>|
|:---|:---|
| <span data-ttu-id="22de1-437">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="22de1-437">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="22de1-438">**Key**</span><span class="sxs-lookup"><span data-stu-id="22de1-438">**Key**</span></span> | <span data-ttu-id="22de1-439">automaticSampleSubmission</span><span class="sxs-lookup"><span data-stu-id="22de1-439">automaticSampleSubmission</span></span> |
| <span data-ttu-id="22de1-440">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="22de1-440">**Data type**</span></span> | <span data-ttu-id="22de1-441">Booleano</span><span class="sxs-lookup"><span data-stu-id="22de1-441">Boolean</span></span> |
| <span data-ttu-id="22de1-442">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="22de1-442">**Possible values**</span></span> | <span data-ttu-id="22de1-443">true (valor predeterminado)</span><span class="sxs-lookup"><span data-stu-id="22de1-443">true (default)</span></span> <br/> <span data-ttu-id="22de1-444">false</span><span class="sxs-lookup"><span data-stu-id="22de1-444">false</span></span> |

#### <a name="enable--disable-automatic-security-intelligence-updates"></a><span data-ttu-id="22de1-445">Habilitar o deshabilitar actualizaciones automáticas de inteligencia de seguridad</span><span class="sxs-lookup"><span data-stu-id="22de1-445">Enable / disable automatic security intelligence updates</span></span>

<span data-ttu-id="22de1-446">Determina si las actualizaciones de inteligencia de seguridad se instalan automáticamente:</span><span class="sxs-lookup"><span data-stu-id="22de1-446">Determines whether security intelligence updates are installed automatically:</span></span>

|<span data-ttu-id="22de1-447">Sección</span><span class="sxs-lookup"><span data-stu-id="22de1-447">Section</span></span>|<span data-ttu-id="22de1-448">Valor</span><span class="sxs-lookup"><span data-stu-id="22de1-448">Value</span></span>|
|:---|:---|
| <span data-ttu-id="22de1-449">**Key**</span><span class="sxs-lookup"><span data-stu-id="22de1-449">**Key**</span></span> | <span data-ttu-id="22de1-450">automaticDefinitionUpdateEnabled</span><span class="sxs-lookup"><span data-stu-id="22de1-450">automaticDefinitionUpdateEnabled</span></span> |
| <span data-ttu-id="22de1-451">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="22de1-451">**Data type**</span></span> | <span data-ttu-id="22de1-452">Booleano</span><span class="sxs-lookup"><span data-stu-id="22de1-452">Boolean</span></span> |
| <span data-ttu-id="22de1-453">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="22de1-453">**Possible values**</span></span> | <span data-ttu-id="22de1-454">true (valor predeterminado)</span><span class="sxs-lookup"><span data-stu-id="22de1-454">true (default)</span></span> <br/> <span data-ttu-id="22de1-455">false</span><span class="sxs-lookup"><span data-stu-id="22de1-455">false</span></span> |

### <a name="user-interface-preferences"></a><span data-ttu-id="22de1-456">Preferencias de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="22de1-456">User interface preferences</span></span>

<span data-ttu-id="22de1-457">Administrar las preferencias de la interfaz de usuario de Microsoft Defender para Endpoint en macOS.</span><span class="sxs-lookup"><span data-stu-id="22de1-457">Manage the preferences for the user interface of Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="22de1-458">Sección</span><span class="sxs-lookup"><span data-stu-id="22de1-458">Section</span></span>|<span data-ttu-id="22de1-459">Valor</span><span class="sxs-lookup"><span data-stu-id="22de1-459">Value</span></span>|
|:---|:---|
| <span data-ttu-id="22de1-460">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="22de1-460">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="22de1-461">**Key**</span><span class="sxs-lookup"><span data-stu-id="22de1-461">**Key**</span></span> | <span data-ttu-id="22de1-462">userInterface</span><span class="sxs-lookup"><span data-stu-id="22de1-462">userInterface</span></span> |
| <span data-ttu-id="22de1-463">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="22de1-463">**Data type**</span></span> | <span data-ttu-id="22de1-464">Diccionario (preferencia anidada)</span><span class="sxs-lookup"><span data-stu-id="22de1-464">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="22de1-465">**Comments**</span><span class="sxs-lookup"><span data-stu-id="22de1-465">**Comments**</span></span> | <span data-ttu-id="22de1-466">Vea las secciones siguientes para obtener una descripción del contenido del diccionario.</span><span class="sxs-lookup"><span data-stu-id="22de1-466">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="show--hide-status-menu-icon"></a><span data-ttu-id="22de1-467">Mostrar u ocultar icono de menú de estado</span><span class="sxs-lookup"><span data-stu-id="22de1-467">Show / hide status menu icon</span></span>

<span data-ttu-id="22de1-468">Especifique si desea mostrar u ocultar el icono del menú de estado en la esquina superior derecha de la pantalla.</span><span class="sxs-lookup"><span data-stu-id="22de1-468">Specify whether to show or hide the status menu icon in the top-right corner of the screen.</span></span>

|<span data-ttu-id="22de1-469">Sección</span><span class="sxs-lookup"><span data-stu-id="22de1-469">Section</span></span>|<span data-ttu-id="22de1-470">Valor</span><span class="sxs-lookup"><span data-stu-id="22de1-470">Value</span></span>|
|:---|:---|
| <span data-ttu-id="22de1-471">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="22de1-471">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="22de1-472">**Key**</span><span class="sxs-lookup"><span data-stu-id="22de1-472">**Key**</span></span> | <span data-ttu-id="22de1-473">hideStatusMenuIcon</span><span class="sxs-lookup"><span data-stu-id="22de1-473">hideStatusMenuIcon</span></span> |
| <span data-ttu-id="22de1-474">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="22de1-474">**Data type**</span></span> | <span data-ttu-id="22de1-475">Booleano</span><span class="sxs-lookup"><span data-stu-id="22de1-475">Boolean</span></span> |
| <span data-ttu-id="22de1-476">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="22de1-476">**Possible values**</span></span> | <span data-ttu-id="22de1-477">false (predeterminado)</span><span class="sxs-lookup"><span data-stu-id="22de1-477">false (default)</span></span> <br/> <span data-ttu-id="22de1-478">true</span><span class="sxs-lookup"><span data-stu-id="22de1-478">true</span></span> |

#### <a name="show--hide-option-to-send-feedback"></a><span data-ttu-id="22de1-479">Mostrar u ocultar opción para enviar comentarios</span><span class="sxs-lookup"><span data-stu-id="22de1-479">Show / hide option to send feedback</span></span>

<span data-ttu-id="22de1-480">Especifica si los usuarios pueden enviar comentarios a Microsoft yendo a `Help`  >  `Send Feedback` .</span><span class="sxs-lookup"><span data-stu-id="22de1-480">Specify whether users can submit feedback to Microsoft by going to `Help` > `Send Feedback`.</span></span>

|<span data-ttu-id="22de1-481">Sección</span><span class="sxs-lookup"><span data-stu-id="22de1-481">Section</span></span>|<span data-ttu-id="22de1-482">Valor</span><span class="sxs-lookup"><span data-stu-id="22de1-482">Value</span></span>|
|:---|:---|
| <span data-ttu-id="22de1-483">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="22de1-483">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="22de1-484">**Key**</span><span class="sxs-lookup"><span data-stu-id="22de1-484">**Key**</span></span> | <span data-ttu-id="22de1-485">userInitiatedFeedback</span><span class="sxs-lookup"><span data-stu-id="22de1-485">userInitiatedFeedback</span></span> |
| <span data-ttu-id="22de1-486">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="22de1-486">**Data type**</span></span> | <span data-ttu-id="22de1-487">Cadena</span><span class="sxs-lookup"><span data-stu-id="22de1-487">String</span></span> |
| <span data-ttu-id="22de1-488">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="22de1-488">**Possible values**</span></span> | <span data-ttu-id="22de1-489">habilitado (predeterminado)</span><span class="sxs-lookup"><span data-stu-id="22de1-489">enabled (default)</span></span> <br/> <span data-ttu-id="22de1-490">deshabilitado</span><span class="sxs-lookup"><span data-stu-id="22de1-490">disabled</span></span> |
| <span data-ttu-id="22de1-491">**Comments**</span><span class="sxs-lookup"><span data-stu-id="22de1-491">**Comments**</span></span> | <span data-ttu-id="22de1-492">Disponible en Microsoft Defender para endpoint versión 101.19.61 o posterior.</span><span class="sxs-lookup"><span data-stu-id="22de1-492">Available in Microsoft Defender for Endpoint version 101.19.61 or higher.</span></span> |

### <a name="endpoint-detection-and-response-preferences"></a><span data-ttu-id="22de1-493">Preferencias de detección y respuesta de extremos</span><span class="sxs-lookup"><span data-stu-id="22de1-493">Endpoint detection and response preferences</span></span>

<span data-ttu-id="22de1-494">Administrar las preferencias del componente detección y respuesta de puntos de conexión (EDR) de Microsoft Defender para endpoint en macOS.</span><span class="sxs-lookup"><span data-stu-id="22de1-494">Manage the preferences of the endpoint detection and response (EDR) component of Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="22de1-495">Sección</span><span class="sxs-lookup"><span data-stu-id="22de1-495">Section</span></span>|<span data-ttu-id="22de1-496">Valor</span><span class="sxs-lookup"><span data-stu-id="22de1-496">Value</span></span>|
|:---|:---|
| <span data-ttu-id="22de1-497">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="22de1-497">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="22de1-498">**Key**</span><span class="sxs-lookup"><span data-stu-id="22de1-498">**Key**</span></span> | <span data-ttu-id="22de1-499">edr</span><span class="sxs-lookup"><span data-stu-id="22de1-499">edr</span></span> |
| <span data-ttu-id="22de1-500">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="22de1-500">**Data type**</span></span> | <span data-ttu-id="22de1-501">Diccionario (preferencia anidada)</span><span class="sxs-lookup"><span data-stu-id="22de1-501">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="22de1-502">**Comments**</span><span class="sxs-lookup"><span data-stu-id="22de1-502">**Comments**</span></span> | <span data-ttu-id="22de1-503">Vea las secciones siguientes para obtener una descripción del contenido del diccionario.</span><span class="sxs-lookup"><span data-stu-id="22de1-503">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="device-tags"></a><span data-ttu-id="22de1-504">Etiquetas de dispositivo</span><span class="sxs-lookup"><span data-stu-id="22de1-504">Device tags</span></span>

<span data-ttu-id="22de1-505">Especifique un nombre de etiqueta y su valor.</span><span class="sxs-lookup"><span data-stu-id="22de1-505">Specify a tag name and its value.</span></span> 

- <span data-ttu-id="22de1-506">La etiqueta GROUP, etiqueta el dispositivo con el valor especificado.</span><span class="sxs-lookup"><span data-stu-id="22de1-506">The GROUP tag, tags the device with the specified value.</span></span> <span data-ttu-id="22de1-507">La etiqueta se refleja en el portal en la página del dispositivo y se puede usar para filtrar y agrupar dispositivos.</span><span class="sxs-lookup"><span data-stu-id="22de1-507">The tag is reflected in the portal under the device page and can be used for filtering and grouping devices.</span></span>

|<span data-ttu-id="22de1-508">Sección</span><span class="sxs-lookup"><span data-stu-id="22de1-508">Section</span></span>|<span data-ttu-id="22de1-509">Valor</span><span class="sxs-lookup"><span data-stu-id="22de1-509">Value</span></span>|
|:---|:---|
| <span data-ttu-id="22de1-510">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="22de1-510">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="22de1-511">**Key**</span><span class="sxs-lookup"><span data-stu-id="22de1-511">**Key**</span></span> | <span data-ttu-id="22de1-512">tags</span><span class="sxs-lookup"><span data-stu-id="22de1-512">tags</span></span> |
| <span data-ttu-id="22de1-513">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="22de1-513">**Data type**</span></span> | <span data-ttu-id="22de1-514">Diccionario (preferencia anidada)</span><span class="sxs-lookup"><span data-stu-id="22de1-514">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="22de1-515">**Comments**</span><span class="sxs-lookup"><span data-stu-id="22de1-515">**Comments**</span></span> | <span data-ttu-id="22de1-516">Vea las secciones siguientes para obtener una descripción del contenido del diccionario.</span><span class="sxs-lookup"><span data-stu-id="22de1-516">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="type-of-tag"></a><span data-ttu-id="22de1-517">Tipo de etiqueta</span><span class="sxs-lookup"><span data-stu-id="22de1-517">Type of tag</span></span>

<span data-ttu-id="22de1-518">Especifica el tipo de etiqueta</span><span class="sxs-lookup"><span data-stu-id="22de1-518">Specifies the type of tag</span></span>

|<span data-ttu-id="22de1-519">Sección</span><span class="sxs-lookup"><span data-stu-id="22de1-519">Section</span></span>|<span data-ttu-id="22de1-520">Valor</span><span class="sxs-lookup"><span data-stu-id="22de1-520">Value</span></span>|
|:---|:---|
| <span data-ttu-id="22de1-521">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="22de1-521">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="22de1-522">**Key**</span><span class="sxs-lookup"><span data-stu-id="22de1-522">**Key**</span></span> | <span data-ttu-id="22de1-523">clave</span><span class="sxs-lookup"><span data-stu-id="22de1-523">key</span></span> |
| <span data-ttu-id="22de1-524">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="22de1-524">**Data type**</span></span> | <span data-ttu-id="22de1-525">Cadena</span><span class="sxs-lookup"><span data-stu-id="22de1-525">String</span></span> |
| <span data-ttu-id="22de1-526">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="22de1-526">**Possible values**</span></span> | `GROUP` |

##### <a name="value-of-tag"></a><span data-ttu-id="22de1-527">Valor de etiqueta</span><span class="sxs-lookup"><span data-stu-id="22de1-527">Value of tag</span></span>

<span data-ttu-id="22de1-528">Especifica el valor de la etiqueta</span><span class="sxs-lookup"><span data-stu-id="22de1-528">Specifies the value of tag</span></span>

|<span data-ttu-id="22de1-529">Sección</span><span class="sxs-lookup"><span data-stu-id="22de1-529">Section</span></span>|<span data-ttu-id="22de1-530">Valor</span><span class="sxs-lookup"><span data-stu-id="22de1-530">Value</span></span>|
|:---|:---|
| <span data-ttu-id="22de1-531">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="22de1-531">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="22de1-532">**Key**</span><span class="sxs-lookup"><span data-stu-id="22de1-532">**Key**</span></span> | <span data-ttu-id="22de1-533">valor</span><span class="sxs-lookup"><span data-stu-id="22de1-533">value</span></span> |
| <span data-ttu-id="22de1-534">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="22de1-534">**Data type**</span></span> | <span data-ttu-id="22de1-535">Cadena</span><span class="sxs-lookup"><span data-stu-id="22de1-535">String</span></span> |
| <span data-ttu-id="22de1-536">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="22de1-536">**Possible values**</span></span> | <span data-ttu-id="22de1-537">cualquier cadena</span><span class="sxs-lookup"><span data-stu-id="22de1-537">any string</span></span> |

> [!IMPORTANT]  
> - <span data-ttu-id="22de1-538">Solo se puede establecer un valor por tipo de etiqueta.</span><span class="sxs-lookup"><span data-stu-id="22de1-538">Only one value per tag type can be set.</span></span>
> - <span data-ttu-id="22de1-539">El tipo de etiquetas es único y no debe repetirse en el mismo perfil de configuración.</span><span class="sxs-lookup"><span data-stu-id="22de1-539">Type of tags are unique, and should not be repeated in the same configuration profile.</span></span>

## <a name="recommended-configuration-profile"></a><span data-ttu-id="22de1-540">Perfil de configuración recomendado</span><span class="sxs-lookup"><span data-stu-id="22de1-540">Recommended configuration profile</span></span>

<span data-ttu-id="22de1-541">Para empezar, se recomienda la siguiente configuración para que la empresa aproveche todas las características de protección que proporciona Microsoft Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="22de1-541">To get started, we recommend the following configuration for your enterprise to take advantage of all protection features that Microsoft Defender for Endpoint provides.</span></span>

<span data-ttu-id="22de1-542">El siguiente perfil de configuración (o, en el caso de JAMF, una lista de propiedades que podría cargarse en el perfil de configuración de configuración personalizada) será:</span><span class="sxs-lookup"><span data-stu-id="22de1-542">The following configuration profile (or, in case of JAMF, a property list that could be uploaded into the custom settings configuration profile) will:</span></span>
- <span data-ttu-id="22de1-543">Habilitar la protección en tiempo real (RTP)</span><span class="sxs-lookup"><span data-stu-id="22de1-543">Enable real-time protection (RTP)</span></span>
- <span data-ttu-id="22de1-544">Especifique cómo se controlan los siguientes tipos de amenazas:</span><span class="sxs-lookup"><span data-stu-id="22de1-544">Specify how the following threat types are handled:</span></span>
  - <span data-ttu-id="22de1-545">**Las aplicaciones potencialmente no deseadas (PUA)** están bloqueadas</span><span class="sxs-lookup"><span data-stu-id="22de1-545">**Potentially unwanted applications (PUA)** are blocked</span></span>
  - <span data-ttu-id="22de1-546">**Las bombas de archivo** (archivo con una tasa de compresión alta) se auditan en Microsoft Defender para los registros de punto de conexión</span><span class="sxs-lookup"><span data-stu-id="22de1-546">**Archive bombs** (file with a high compression rate) are audited to Microsoft Defender for Endpoint logs</span></span>
- <span data-ttu-id="22de1-547">Habilitar actualizaciones automáticas de inteligencia de seguridad</span><span class="sxs-lookup"><span data-stu-id="22de1-547">Enable automatic security intelligence updates</span></span>
- <span data-ttu-id="22de1-548">Habilitar la protección proporcionada en la nube</span><span class="sxs-lookup"><span data-stu-id="22de1-548">Enable cloud-delivered protection</span></span>
- <span data-ttu-id="22de1-549">Habilitar el envío automático de muestra</span><span class="sxs-lookup"><span data-stu-id="22de1-549">Enable automatic sample submission</span></span>

### <a name="property-list-for-jamf-configuration-profile"></a><span data-ttu-id="22de1-550">Lista de propiedades para el perfil de configuración de JAMF</span><span class="sxs-lookup"><span data-stu-id="22de1-550">Property list for JAMF configuration profile</span></span>

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

### <a name="intune-profile"></a><span data-ttu-id="22de1-551">Perfil de Intune</span><span class="sxs-lookup"><span data-stu-id="22de1-551">Intune profile</span></span>

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

## <a name="full-configuration-profile-example"></a><span data-ttu-id="22de1-552">Ejemplo de perfil de configuración completa</span><span class="sxs-lookup"><span data-stu-id="22de1-552">Full configuration profile example</span></span>

<span data-ttu-id="22de1-553">Las plantillas siguientes contienen entradas para todas las configuraciones descritas en este documento y se pueden usar para escenarios más avanzados en los que desea tener más control sobre Microsoft Defender para Endpoint en macOS.</span><span class="sxs-lookup"><span data-stu-id="22de1-553">The following templates contain entries for all settings described in this document and can be used for more advanced scenarios where you want more control over Microsoft Defender for Endpoint on macOS.</span></span>

### <a name="property-list-for-jamf-configuration-profile"></a><span data-ttu-id="22de1-554">Lista de propiedades para el perfil de configuración de JAMF</span><span class="sxs-lookup"><span data-stu-id="22de1-554">Property list for JAMF configuration profile</span></span>

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

### <a name="intune-profile"></a><span data-ttu-id="22de1-555">Perfil de Intune</span><span class="sxs-lookup"><span data-stu-id="22de1-555">Intune profile</span></span>

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

## <a name="property-list-validation"></a><span data-ttu-id="22de1-556">Validación de lista de propiedades</span><span class="sxs-lookup"><span data-stu-id="22de1-556">Property list validation</span></span>

<span data-ttu-id="22de1-557">La lista de propiedades debe ser un archivo *.plist* válido.</span><span class="sxs-lookup"><span data-stu-id="22de1-557">The property list must be a valid *.plist* file.</span></span> <span data-ttu-id="22de1-558">Esto se puede comprobar ejecutando:</span><span class="sxs-lookup"><span data-stu-id="22de1-558">This can be checked by executing:</span></span>

```bash
plutil -lint com.microsoft.wdav.plist
```
```Output
com.microsoft.wdav.plist: OK
```

<span data-ttu-id="22de1-559">Si el archivo está bien formado, el comando anterior genera `OK` y devuelve un código de salida de `0` .</span><span class="sxs-lookup"><span data-stu-id="22de1-559">If the file is well-formed, the above command outputs `OK` and returns an exit code of `0`.</span></span> <span data-ttu-id="22de1-560">De lo contrario, se muestra un error que describe el problema y el comando devuelve un código de salida de `1` .</span><span class="sxs-lookup"><span data-stu-id="22de1-560">Otherwise, an error that describes the issue is displayed and the command returns an exit code of `1`.</span></span>

## <a name="configuration-profile-deployment"></a><span data-ttu-id="22de1-561">Implementación de perfiles de configuración</span><span class="sxs-lookup"><span data-stu-id="22de1-561">Configuration profile deployment</span></span>

<span data-ttu-id="22de1-562">Una vez que haya creado el perfil de configuración para su empresa, puede implementarlo a través de la consola de administración que usa su empresa.</span><span class="sxs-lookup"><span data-stu-id="22de1-562">Once you've built the configuration profile for your enterprise, you can deploy it through the management console that your enterprise is using.</span></span> <span data-ttu-id="22de1-563">En las secciones siguientes se proporcionan instrucciones sobre cómo implementar este perfil con JAMF e Intune.</span><span class="sxs-lookup"><span data-stu-id="22de1-563">The following sections provide instructions on how to deploy this profile using JAMF and Intune.</span></span>

### <a name="jamf-deployment"></a><span data-ttu-id="22de1-564">Implementación de JAMF</span><span class="sxs-lookup"><span data-stu-id="22de1-564">JAMF deployment</span></span>

<span data-ttu-id="22de1-565">En la consola JAMF, abra **Perfiles** de configuración de equipos , vaya al perfil de configuración que desea usar y, a  >  continuación, seleccione **Custom Configuración**.</span><span class="sxs-lookup"><span data-stu-id="22de1-565">From the JAMF console, open **Computers** > **Configuration Profiles**, navigate to the configuration profile you'd like to use, then select **Custom Settings**.</span></span> <span data-ttu-id="22de1-566">Cree una entrada con `com.microsoft.wdav` como dominio de preferencia y cargue el *.plist* generado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="22de1-566">Create an entry with `com.microsoft.wdav` as the preference domain and upload the *.plist* produced earlier.</span></span>

>[!CAUTION]
><span data-ttu-id="22de1-567">Debes escribir el dominio de preferencia correcto ( ); de lo contrario, Microsoft Defender no reconocerá las `com.microsoft.wdav` preferencias para endpoint.</span><span class="sxs-lookup"><span data-stu-id="22de1-567">You must enter the correct preference domain (`com.microsoft.wdav`); otherwise, the preferences will not be recognized by Microsoft Defender for Endpoint.</span></span>

### <a name="intune-deployment"></a><span data-ttu-id="22de1-568">Implementación de Intune</span><span class="sxs-lookup"><span data-stu-id="22de1-568">Intune deployment</span></span>

1. <span data-ttu-id="22de1-569">Abra **Administrar configuración** de  >  **dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="22de1-569">Open **Manage** > **Device configuration**.</span></span> <span data-ttu-id="22de1-570">Seleccione **Administrar**  >  **perfiles Crear**  >  **perfil**.</span><span class="sxs-lookup"><span data-stu-id="22de1-570">Select **Manage** > **Profiles** > **Create Profile**.</span></span>

2. <span data-ttu-id="22de1-571">Elija un nombre para el perfil.</span><span class="sxs-lookup"><span data-stu-id="22de1-571">Choose a name for the profile.</span></span> <span data-ttu-id="22de1-572">Cambiar **Platform=macOS** a **Profile type=Custom**.</span><span class="sxs-lookup"><span data-stu-id="22de1-572">Change **Platform=macOS** to **Profile type=Custom**.</span></span> <span data-ttu-id="22de1-573">Seleccione Configurar.</span><span class="sxs-lookup"><span data-stu-id="22de1-573">Select Configure.</span></span>

3. <span data-ttu-id="22de1-574">Guarde el .plist generado anteriormente como `com.microsoft.wdav.xml` .</span><span class="sxs-lookup"><span data-stu-id="22de1-574">Save the .plist produced earlier as `com.microsoft.wdav.xml`.</span></span>

4. <span data-ttu-id="22de1-575">Escriba `com.microsoft.wdav` como el nombre del perfil de configuración **personalizado**.</span><span class="sxs-lookup"><span data-stu-id="22de1-575">Enter `com.microsoft.wdav` as the **custom configuration profile name**.</span></span>

5. <span data-ttu-id="22de1-576">Abra el perfil de configuración y cargue el `com.microsoft.wdav.xml` archivo.</span><span class="sxs-lookup"><span data-stu-id="22de1-576">Open the configuration profile and upload the `com.microsoft.wdav.xml` file.</span></span> <span data-ttu-id="22de1-577">(Este archivo se creó en el paso 3).</span><span class="sxs-lookup"><span data-stu-id="22de1-577">(This file was created in step 3.)</span></span>

6. <span data-ttu-id="22de1-578">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="22de1-578">Select **OK**.</span></span>

7. <span data-ttu-id="22de1-579">Seleccione **Administrar**  >  **asignaciones**.</span><span class="sxs-lookup"><span data-stu-id="22de1-579">Select **Manage** > **Assignments**.</span></span> <span data-ttu-id="22de1-580">En la **pestaña Incluir,** seleccione **Asignar a todos los usuarios & Todos los dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="22de1-580">In the **Include** tab, select **Assign to All Users & All devices**.</span></span>

>[!CAUTION]
><span data-ttu-id="22de1-581">Debe escribir el nombre del perfil de configuración personalizado correcto; de lo contrario, Microsoft Defender no reconocerá estas preferencias para endpoint.</span><span class="sxs-lookup"><span data-stu-id="22de1-581">You must enter the correct custom configuration profile name; otherwise, these preferences will not be recognized by Microsoft Defender for Endpoint.</span></span>

## <a name="resources"></a><span data-ttu-id="22de1-582">Recursos</span><span class="sxs-lookup"><span data-stu-id="22de1-582">Resources</span></span>

- [<span data-ttu-id="22de1-583">Referencia de los perfiles de configuración (documentación para desarrolladores de Apple)</span><span class="sxs-lookup"><span data-stu-id="22de1-583">Configuration Profile Reference (Apple developer documentation)</span></span>](https://developer.apple.com/business/documentation/Configuration-Profile-Reference.pdf)
