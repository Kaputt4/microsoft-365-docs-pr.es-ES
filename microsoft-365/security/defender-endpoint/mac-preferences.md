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
ms.openlocfilehash: f13734392e4975738a0d60d38e618595b5175667
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934566"
---
# <a name="set-preferences-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="6f416-104">Establecer preferencias para Microsoft Defender para endpoint en macOS</span><span class="sxs-lookup"><span data-stu-id="6f416-104">Set preferences for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="6f416-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="6f416-105">**Applies to:**</span></span>

- [<span data-ttu-id="6f416-106">Microsoft Defender para punto de conexión en macOS</span><span class="sxs-lookup"><span data-stu-id="6f416-106">Microsoft Defender for Endpoint on macOS</span></span>](microsoft-defender-endpoint-mac.md)

>[!IMPORTANT]
><span data-ttu-id="6f416-107">Este artículo contiene instrucciones sobre cómo establecer las preferencias de Microsoft Defender para Endpoint en macOS en organizaciones empresariales.</span><span class="sxs-lookup"><span data-stu-id="6f416-107">This article contains instructions for how to set preferences for Microsoft Defender for Endpoint on macOS in enterprise organizations.</span></span> <span data-ttu-id="6f416-108">Para configurar Microsoft Defender para endpoint en macOS mediante la interfaz de línea de comandos, vea [Resources](mac-resources.md#configuring-from-the-command-line).</span><span class="sxs-lookup"><span data-stu-id="6f416-108">To configure Microsoft Defender for Endpoint on macOS using the command-line interface, see [Resources](mac-resources.md#configuring-from-the-command-line).</span></span>

## <a name="summary"></a><span data-ttu-id="6f416-109">Resumen</span><span class="sxs-lookup"><span data-stu-id="6f416-109">Summary</span></span>

<span data-ttu-id="6f416-110">En organizaciones empresariales, Microsoft Defender para Endpoint en macOS se puede administrar a través de un perfil de configuración que se implementa mediante una de varias herramientas de administración.</span><span class="sxs-lookup"><span data-stu-id="6f416-110">In enterprise organizations, Microsoft Defender for Endpoint on macOS can be managed through a configuration profile that is deployed by using one of several management tools.</span></span> <span data-ttu-id="6f416-111">Las preferencias administradas por el equipo de operaciones de seguridad tienen prioridad sobre las preferencias que se establecen localmente en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6f416-111">Preferences that are managed by your security operations team take precedence over preferences that are set locally on the device.</span></span> <span data-ttu-id="6f416-112">Cambiar las preferencias que se establecen a través del perfil de configuración requiere privilegios escalados y no está disponible para usuarios sin permisos administrativos.</span><span class="sxs-lookup"><span data-stu-id="6f416-112">Changing the preferences that are set through the configuration profile requires escalated privileges and is not available for users without administrative permissions.</span></span>

<span data-ttu-id="6f416-113">En este artículo se describe la estructura del perfil de configuración, se incluye un perfil recomendado que puede usar para empezar y se proporcionan instrucciones sobre cómo implementar el perfil.</span><span class="sxs-lookup"><span data-stu-id="6f416-113">This article describes the structure of the configuration profile, includes a recommended profile that you can use to get started, and provides instructions on how to deploy the profile.</span></span>

## <a name="configuration-profile-structure"></a><span data-ttu-id="6f416-114">Estructura de perfiles de configuración</span><span class="sxs-lookup"><span data-stu-id="6f416-114">Configuration profile structure</span></span>

<span data-ttu-id="6f416-115">El perfil de configuración es un *archivo .plist* que consta de entradas identificadas por una clave (que indica el nombre de la preferencia), seguido de un valor, que depende de la naturaleza de la preferencia.</span><span class="sxs-lookup"><span data-stu-id="6f416-115">The configuration profile is a *.plist* file that consists of entries identified by a key (which denotes the name of the preference), followed by a value, which depends on the nature of the preference.</span></span> <span data-ttu-id="6f416-116">Los valores pueden ser simples (como un valor numérico) o complejos, como una lista anidada de preferencias.</span><span class="sxs-lookup"><span data-stu-id="6f416-116">Values can either be simple (such as a numerical value) or complex, such as a nested list of preferences.</span></span>

>[!CAUTION]
><span data-ttu-id="6f416-117">El diseño del perfil de configuración depende de la consola de administración que se use.</span><span class="sxs-lookup"><span data-stu-id="6f416-117">The layout of the configuration profile depends on the management console that you are using.</span></span> <span data-ttu-id="6f416-118">Las secciones siguientes contienen ejemplos de perfiles de configuración para JAMF e Intune.</span><span class="sxs-lookup"><span data-stu-id="6f416-118">The following sections contain examples of configuration profiles for JAMF and Intune.</span></span>

<span data-ttu-id="6f416-119">El nivel superior del perfil de configuración incluye las preferencias de todo el producto y las entradas para las subáreas de Microsoft Defender para endpoint, que se explican con más detalle en las secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="6f416-119">The top level of the configuration profile includes product-wide preferences and entries for subareas of Microsoft Defender for Endpoint, which are explained in more detail in the next sections.</span></span>

### <a name="antivirus-engine-preferences"></a><span data-ttu-id="6f416-120">Preferencias del motor antivirus</span><span class="sxs-lookup"><span data-stu-id="6f416-120">Antivirus engine preferences</span></span>

<span data-ttu-id="6f416-121">La *sección antivirusEngine* del perfil de configuración se usa para administrar las preferencias del componente antivirus de Microsoft Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="6f416-121">The *antivirusEngine* section of the configuration profile is used to manage the preferences of the antivirus component of Microsoft Defender for Endpoint.</span></span>

|<span data-ttu-id="6f416-122">Section</span><span class="sxs-lookup"><span data-stu-id="6f416-122">Section</span></span>|<span data-ttu-id="6f416-123">Valor</span><span class="sxs-lookup"><span data-stu-id="6f416-123">Value</span></span>|
|:---|:---|
| <span data-ttu-id="6f416-124">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="6f416-124">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="6f416-125">**Key**</span><span class="sxs-lookup"><span data-stu-id="6f416-125">**Key**</span></span> | <span data-ttu-id="6f416-126">antivirusEngine</span><span class="sxs-lookup"><span data-stu-id="6f416-126">antivirusEngine</span></span> |
| <span data-ttu-id="6f416-127">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="6f416-127">**Data type**</span></span> | <span data-ttu-id="6f416-128">Diccionario (preferencia anidada)</span><span class="sxs-lookup"><span data-stu-id="6f416-128">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="6f416-129">**Comments**</span><span class="sxs-lookup"><span data-stu-id="6f416-129">**Comments**</span></span> | <span data-ttu-id="6f416-130">Vea las secciones siguientes para obtener una descripción del contenido del diccionario.</span><span class="sxs-lookup"><span data-stu-id="6f416-130">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="enable--disable-real-time-protection"></a><span data-ttu-id="6f416-131">Habilitar o deshabilitar la protección en tiempo real</span><span class="sxs-lookup"><span data-stu-id="6f416-131">Enable / disable real-time protection</span></span>

<span data-ttu-id="6f416-132">Especifique si se va a habilitar la protección en tiempo real, que examina los archivos a medida que se accede a ellos.</span><span class="sxs-lookup"><span data-stu-id="6f416-132">Specify whether to enable real-time protection, which scans files as they are accessed.</span></span>

|<span data-ttu-id="6f416-133">Section</span><span class="sxs-lookup"><span data-stu-id="6f416-133">Section</span></span>|<span data-ttu-id="6f416-134">Valor</span><span class="sxs-lookup"><span data-stu-id="6f416-134">Value</span></span>|
|:---|:---|
| <span data-ttu-id="6f416-135">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="6f416-135">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="6f416-136">**Key**</span><span class="sxs-lookup"><span data-stu-id="6f416-136">**Key**</span></span> | <span data-ttu-id="6f416-137">enableRealTimeProtection</span><span class="sxs-lookup"><span data-stu-id="6f416-137">enableRealTimeProtection</span></span> |
| <span data-ttu-id="6f416-138">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="6f416-138">**Data type**</span></span> | <span data-ttu-id="6f416-139">Booleano</span><span class="sxs-lookup"><span data-stu-id="6f416-139">Boolean</span></span> |
| <span data-ttu-id="6f416-140">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="6f416-140">**Possible values**</span></span> | <span data-ttu-id="6f416-141">true (valor predeterminado)</span><span class="sxs-lookup"><span data-stu-id="6f416-141">true (default)</span></span> <br/> <span data-ttu-id="6f416-142">false</span><span class="sxs-lookup"><span data-stu-id="6f416-142">false</span></span> |

#### <a name="enable--disable-passive-mode"></a><span data-ttu-id="6f416-143">Habilitar o deshabilitar el modo pasivo</span><span class="sxs-lookup"><span data-stu-id="6f416-143">Enable / disable passive mode</span></span>

<span data-ttu-id="6f416-144">Especifique si el motor antivirus se ejecuta en modo pasivo.</span><span class="sxs-lookup"><span data-stu-id="6f416-144">Specify whether the antivirus engine runs in passive mode.</span></span> <span data-ttu-id="6f416-145">El modo pasivo tiene las siguientes implicaciones:</span><span class="sxs-lookup"><span data-stu-id="6f416-145">Passive mode has the following implications:</span></span> 
- <span data-ttu-id="6f416-146">La protección en tiempo real está desactivada</span><span class="sxs-lookup"><span data-stu-id="6f416-146">Real-time protection is turned off</span></span>
- <span data-ttu-id="6f416-147">El examen a petición está activado</span><span class="sxs-lookup"><span data-stu-id="6f416-147">On-demand scanning is turned on</span></span>
- <span data-ttu-id="6f416-148">La corrección automática de amenazas está desactivada</span><span class="sxs-lookup"><span data-stu-id="6f416-148">Automatic threat remediation is turned off</span></span>
- <span data-ttu-id="6f416-149">Las actualizaciones de inteligencia de seguridad están activadas</span><span class="sxs-lookup"><span data-stu-id="6f416-149">Security intelligence updates are turned on</span></span>
- <span data-ttu-id="6f416-150">El icono del menú Estado está oculto</span><span class="sxs-lookup"><span data-stu-id="6f416-150">Status menu icon is hidden</span></span>

|<span data-ttu-id="6f416-151">Section</span><span class="sxs-lookup"><span data-stu-id="6f416-151">Section</span></span>|<span data-ttu-id="6f416-152">Valor</span><span class="sxs-lookup"><span data-stu-id="6f416-152">Value</span></span>|
|:---|:---|
| <span data-ttu-id="6f416-153">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="6f416-153">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="6f416-154">**Key**</span><span class="sxs-lookup"><span data-stu-id="6f416-154">**Key**</span></span> | <span data-ttu-id="6f416-155">passiveMode</span><span class="sxs-lookup"><span data-stu-id="6f416-155">passiveMode</span></span> |
| <span data-ttu-id="6f416-156">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="6f416-156">**Data type**</span></span> | <span data-ttu-id="6f416-157">Booleano</span><span class="sxs-lookup"><span data-stu-id="6f416-157">Boolean</span></span> |
| <span data-ttu-id="6f416-158">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="6f416-158">**Possible values**</span></span> | <span data-ttu-id="6f416-159">false (predeterminado)</span><span class="sxs-lookup"><span data-stu-id="6f416-159">false (default)</span></span> <br/> <span data-ttu-id="6f416-160">true</span><span class="sxs-lookup"><span data-stu-id="6f416-160">true</span></span> |
| <span data-ttu-id="6f416-161">**Comments**</span><span class="sxs-lookup"><span data-stu-id="6f416-161">**Comments**</span></span> | <span data-ttu-id="6f416-162">Disponible en Microsoft Defender para endpoint versión 100.67.60 o posterior.</span><span class="sxs-lookup"><span data-stu-id="6f416-162">Available in Microsoft Defender for Endpoint version 100.67.60 or higher.</span></span> |

#### <a name="exclusion-merge-policy"></a><span data-ttu-id="6f416-163">Directiva de combinación de exclusión</span><span class="sxs-lookup"><span data-stu-id="6f416-163">Exclusion merge policy</span></span>

<span data-ttu-id="6f416-164">Especifique la directiva de combinación para exclusiones.</span><span class="sxs-lookup"><span data-stu-id="6f416-164">Specify the merge policy for exclusions.</span></span> <span data-ttu-id="6f416-165">Puede ser una combinación de exclusiones definidas por el administrador y definidas por el usuario ( ) o solo `merge` exclusiones definidas por el administrador ( `admin_only` ).</span><span class="sxs-lookup"><span data-stu-id="6f416-165">This can be a combination of administrator-defined and user-defined exclusions (`merge`) or only administrator-defined exclusions (`admin_only`).</span></span> <span data-ttu-id="6f416-166">Esta configuración se puede usar para restringir que los usuarios locales definan sus propias exclusiones.</span><span class="sxs-lookup"><span data-stu-id="6f416-166">This setting can be used to restrict local users from defining their own exclusions.</span></span>

|<span data-ttu-id="6f416-167">Section</span><span class="sxs-lookup"><span data-stu-id="6f416-167">Section</span></span>|<span data-ttu-id="6f416-168">Valor</span><span class="sxs-lookup"><span data-stu-id="6f416-168">Value</span></span>|
|:---|:---|
| <span data-ttu-id="6f416-169">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="6f416-169">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="6f416-170">**Key**</span><span class="sxs-lookup"><span data-stu-id="6f416-170">**Key**</span></span> | <span data-ttu-id="6f416-171">exclusionsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="6f416-171">exclusionsMergePolicy</span></span> |
| <span data-ttu-id="6f416-172">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="6f416-172">**Data type**</span></span> | <span data-ttu-id="6f416-173">Cadena</span><span class="sxs-lookup"><span data-stu-id="6f416-173">String</span></span> |
| <span data-ttu-id="6f416-174">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="6f416-174">**Possible values**</span></span> | <span data-ttu-id="6f416-175">merge (valor predeterminado)</span><span class="sxs-lookup"><span data-stu-id="6f416-175">merge (default)</span></span> <br/> <span data-ttu-id="6f416-176">admin_only</span><span class="sxs-lookup"><span data-stu-id="6f416-176">admin_only</span></span> |
| <span data-ttu-id="6f416-177">**Comments**</span><span class="sxs-lookup"><span data-stu-id="6f416-177">**Comments**</span></span> | <span data-ttu-id="6f416-178">Disponible en Microsoft Defender para endpoint versión 100.83.73 o posterior.</span><span class="sxs-lookup"><span data-stu-id="6f416-178">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="scan-exclusions"></a><span data-ttu-id="6f416-179">Exclusiones de examen</span><span class="sxs-lookup"><span data-stu-id="6f416-179">Scan exclusions</span></span>

<span data-ttu-id="6f416-180">Especifique las entidades que no se han analizado.</span><span class="sxs-lookup"><span data-stu-id="6f416-180">Specify entities excluded from being scanned.</span></span> <span data-ttu-id="6f416-181">Las exclusiones se pueden especificar por rutas de acceso completas, extensiones o nombres de archivo.</span><span class="sxs-lookup"><span data-stu-id="6f416-181">Exclusions can be specified by full paths, extensions, or file names.</span></span>

|<span data-ttu-id="6f416-182">Section</span><span class="sxs-lookup"><span data-stu-id="6f416-182">Section</span></span>|<span data-ttu-id="6f416-183">Valor</span><span class="sxs-lookup"><span data-stu-id="6f416-183">Value</span></span>|
|:---|:---|
| <span data-ttu-id="6f416-184">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="6f416-184">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="6f416-185">**Key**</span><span class="sxs-lookup"><span data-stu-id="6f416-185">**Key**</span></span> | <span data-ttu-id="6f416-186">exclusiones</span><span class="sxs-lookup"><span data-stu-id="6f416-186">exclusions</span></span> |
| <span data-ttu-id="6f416-187">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="6f416-187">**Data type**</span></span> | <span data-ttu-id="6f416-188">Diccionario (preferencia anidada)</span><span class="sxs-lookup"><span data-stu-id="6f416-188">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="6f416-189">**Comments**</span><span class="sxs-lookup"><span data-stu-id="6f416-189">**Comments**</span></span> | <span data-ttu-id="6f416-190">Vea las secciones siguientes para obtener una descripción del contenido del diccionario.</span><span class="sxs-lookup"><span data-stu-id="6f416-190">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="type-of-exclusion"></a><span data-ttu-id="6f416-191">Tipo de exclusión</span><span class="sxs-lookup"><span data-stu-id="6f416-191">Type of exclusion</span></span>

<span data-ttu-id="6f416-192">Especifique el contenido excluido de ser examinado por tipo.</span><span class="sxs-lookup"><span data-stu-id="6f416-192">Specify content excluded from being scanned by type.</span></span>

|<span data-ttu-id="6f416-193">Section</span><span class="sxs-lookup"><span data-stu-id="6f416-193">Section</span></span>|<span data-ttu-id="6f416-194">Valor</span><span class="sxs-lookup"><span data-stu-id="6f416-194">Value</span></span>|
|:---|:---|
| <span data-ttu-id="6f416-195">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="6f416-195">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="6f416-196">**Key**</span><span class="sxs-lookup"><span data-stu-id="6f416-196">**Key**</span></span> | <span data-ttu-id="6f416-197">$type</span><span class="sxs-lookup"><span data-stu-id="6f416-197">$type</span></span> |
| <span data-ttu-id="6f416-198">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="6f416-198">**Data type**</span></span> | <span data-ttu-id="6f416-199">Cadena</span><span class="sxs-lookup"><span data-stu-id="6f416-199">String</span></span> |
| <span data-ttu-id="6f416-200">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="6f416-200">**Possible values**</span></span> | <span data-ttu-id="6f416-201">excludedPath</span><span class="sxs-lookup"><span data-stu-id="6f416-201">excludedPath</span></span> <br/> <span data-ttu-id="6f416-202">excludedFileExtension</span><span class="sxs-lookup"><span data-stu-id="6f416-202">excludedFileExtension</span></span> <br/> <span data-ttu-id="6f416-203">excludedFileName</span><span class="sxs-lookup"><span data-stu-id="6f416-203">excludedFileName</span></span> |

##### <a name="path-to-excluded-content"></a><span data-ttu-id="6f416-204">Ruta de acceso al contenido excluido</span><span class="sxs-lookup"><span data-stu-id="6f416-204">Path to excluded content</span></span>

<span data-ttu-id="6f416-205">Especifique el contenido excluido de ser examinado por la ruta de acceso de archivo completa.</span><span class="sxs-lookup"><span data-stu-id="6f416-205">Specify content excluded from being scanned by full file path.</span></span>

|<span data-ttu-id="6f416-206">Section</span><span class="sxs-lookup"><span data-stu-id="6f416-206">Section</span></span>|<span data-ttu-id="6f416-207">Valor</span><span class="sxs-lookup"><span data-stu-id="6f416-207">Value</span></span>|
|:---|:---|
| <span data-ttu-id="6f416-208">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="6f416-208">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="6f416-209">**Key**</span><span class="sxs-lookup"><span data-stu-id="6f416-209">**Key**</span></span> | <span data-ttu-id="6f416-210">path</span><span class="sxs-lookup"><span data-stu-id="6f416-210">path</span></span> |
| <span data-ttu-id="6f416-211">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="6f416-211">**Data type**</span></span> | <span data-ttu-id="6f416-212">Cadena</span><span class="sxs-lookup"><span data-stu-id="6f416-212">String</span></span> |
| <span data-ttu-id="6f416-213">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="6f416-213">**Possible values**</span></span> | <span data-ttu-id="6f416-214">rutas de acceso válidas</span><span class="sxs-lookup"><span data-stu-id="6f416-214">valid paths</span></span> |
| <span data-ttu-id="6f416-215">**Comments**</span><span class="sxs-lookup"><span data-stu-id="6f416-215">**Comments**</span></span> | <span data-ttu-id="6f416-216">Aplicable solo *si $type* *se excluyePath*</span><span class="sxs-lookup"><span data-stu-id="6f416-216">Applicable only if *$type* is *excludedPath*</span></span> |

##### <a name="path-type-file--directory"></a><span data-ttu-id="6f416-217">Tipo de ruta de acceso (archivo/directorio)</span><span class="sxs-lookup"><span data-stu-id="6f416-217">Path type (file / directory)</span></span>

<span data-ttu-id="6f416-218">Indica si la *propiedad path* hace referencia a un archivo o directorio.</span><span class="sxs-lookup"><span data-stu-id="6f416-218">Indicate if the *path* property refers to a file or directory.</span></span> 

|<span data-ttu-id="6f416-219">Section</span><span class="sxs-lookup"><span data-stu-id="6f416-219">Section</span></span>|<span data-ttu-id="6f416-220">Valor</span><span class="sxs-lookup"><span data-stu-id="6f416-220">Value</span></span>|
|:---|:---|
| <span data-ttu-id="6f416-221">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="6f416-221">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="6f416-222">**Key**</span><span class="sxs-lookup"><span data-stu-id="6f416-222">**Key**</span></span> | <span data-ttu-id="6f416-223">isDirectory</span><span class="sxs-lookup"><span data-stu-id="6f416-223">isDirectory</span></span> |
| <span data-ttu-id="6f416-224">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="6f416-224">**Data type**</span></span> | <span data-ttu-id="6f416-225">Booleano</span><span class="sxs-lookup"><span data-stu-id="6f416-225">Boolean</span></span> |
| <span data-ttu-id="6f416-226">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="6f416-226">**Possible values**</span></span> | <span data-ttu-id="6f416-227">false (predeterminado)</span><span class="sxs-lookup"><span data-stu-id="6f416-227">false (default)</span></span> <br/> <span data-ttu-id="6f416-228">true</span><span class="sxs-lookup"><span data-stu-id="6f416-228">true</span></span> |
| <span data-ttu-id="6f416-229">**Comments**</span><span class="sxs-lookup"><span data-stu-id="6f416-229">**Comments**</span></span> | <span data-ttu-id="6f416-230">Aplicable solo *si $type* *se excluyePath*</span><span class="sxs-lookup"><span data-stu-id="6f416-230">Applicable only if *$type* is *excludedPath*</span></span> |

##### <a name="file-extension-excluded-from-the-scan"></a><span data-ttu-id="6f416-231">Extensión de archivo excluida del examen</span><span class="sxs-lookup"><span data-stu-id="6f416-231">File extension excluded from the scan</span></span>

<span data-ttu-id="6f416-232">Especifique el contenido excluido de la extensión de archivo.</span><span class="sxs-lookup"><span data-stu-id="6f416-232">Specify content excluded from being scanned by file extension.</span></span>

|<span data-ttu-id="6f416-233">Section</span><span class="sxs-lookup"><span data-stu-id="6f416-233">Section</span></span>|<span data-ttu-id="6f416-234">Valor</span><span class="sxs-lookup"><span data-stu-id="6f416-234">Value</span></span>|
|:---|:---|
| <span data-ttu-id="6f416-235">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="6f416-235">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="6f416-236">**Key**</span><span class="sxs-lookup"><span data-stu-id="6f416-236">**Key**</span></span> | <span data-ttu-id="6f416-237">extensión</span><span class="sxs-lookup"><span data-stu-id="6f416-237">extension</span></span> |
| <span data-ttu-id="6f416-238">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="6f416-238">**Data type**</span></span> | <span data-ttu-id="6f416-239">Cadena</span><span class="sxs-lookup"><span data-stu-id="6f416-239">String</span></span> |
| <span data-ttu-id="6f416-240">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="6f416-240">**Possible values**</span></span> | <span data-ttu-id="6f416-241">extensiones de archivo válidas</span><span class="sxs-lookup"><span data-stu-id="6f416-241">valid file extensions</span></span> |
| <span data-ttu-id="6f416-242">**Comments**</span><span class="sxs-lookup"><span data-stu-id="6f416-242">**Comments**</span></span> | <span data-ttu-id="6f416-243">Aplicable solo *si $type* *se excluyeFileExtension*</span><span class="sxs-lookup"><span data-stu-id="6f416-243">Applicable only if *$type* is *excludedFileExtension*</span></span> |

##### <a name="process-excluded-from-the-scan"></a><span data-ttu-id="6f416-244">Proceso excluido del examen</span><span class="sxs-lookup"><span data-stu-id="6f416-244">Process excluded from the scan</span></span>

<span data-ttu-id="6f416-245">Especifique un proceso para el que se excluya toda la actividad de archivo del examen.</span><span class="sxs-lookup"><span data-stu-id="6f416-245">Specify a process for which all file activity is excluded from scanning.</span></span> <span data-ttu-id="6f416-246">El proceso puede especificarse por su nombre (por ejemplo) o por la ruta de acceso `cat` completa (por ejemplo, `/bin/cat` ).</span><span class="sxs-lookup"><span data-stu-id="6f416-246">The process can be specified either by its name (e.g. `cat`) or full path (e.g. `/bin/cat`).</span></span>

|<span data-ttu-id="6f416-247">Section</span><span class="sxs-lookup"><span data-stu-id="6f416-247">Section</span></span>|<span data-ttu-id="6f416-248">Valor</span><span class="sxs-lookup"><span data-stu-id="6f416-248">Value</span></span>|
|:---|:---|
| <span data-ttu-id="6f416-249">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="6f416-249">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="6f416-250">**Key**</span><span class="sxs-lookup"><span data-stu-id="6f416-250">**Key**</span></span> | <span data-ttu-id="6f416-251">name</span><span class="sxs-lookup"><span data-stu-id="6f416-251">name</span></span> |
| <span data-ttu-id="6f416-252">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="6f416-252">**Data type**</span></span> | <span data-ttu-id="6f416-253">Cadena</span><span class="sxs-lookup"><span data-stu-id="6f416-253">String</span></span> |
| <span data-ttu-id="6f416-254">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="6f416-254">**Possible values**</span></span> | <span data-ttu-id="6f416-255">cualquier cadena</span><span class="sxs-lookup"><span data-stu-id="6f416-255">any string</span></span> |
| <span data-ttu-id="6f416-256">**Comments**</span><span class="sxs-lookup"><span data-stu-id="6f416-256">**Comments**</span></span> | <span data-ttu-id="6f416-257">Aplicable solo *si $type* *se excluyeFileName*</span><span class="sxs-lookup"><span data-stu-id="6f416-257">Applicable only if *$type* is *excludedFileName*</span></span> |

#### <a name="allowed-threats"></a><span data-ttu-id="6f416-258">Amenazas permitidas</span><span class="sxs-lookup"><span data-stu-id="6f416-258">Allowed threats</span></span>

<span data-ttu-id="6f416-259">Especifica las amenazas por nombre que no estén bloqueadas por Defender para Endpoint en Mac.</span><span class="sxs-lookup"><span data-stu-id="6f416-259">Specify threats by name that are not blocked by Defender for Endpoint on Mac.</span></span> <span data-ttu-id="6f416-260">Estas amenazas podrán ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="6f416-260">These threats will be allowed to run.</span></span>

|<span data-ttu-id="6f416-261">Section</span><span class="sxs-lookup"><span data-stu-id="6f416-261">Section</span></span>|<span data-ttu-id="6f416-262">Valor</span><span class="sxs-lookup"><span data-stu-id="6f416-262">Value</span></span>|
|:---|:---|
| <span data-ttu-id="6f416-263">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="6f416-263">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="6f416-264">**Key**</span><span class="sxs-lookup"><span data-stu-id="6f416-264">**Key**</span></span> | <span data-ttu-id="6f416-265">allowedThreats</span><span class="sxs-lookup"><span data-stu-id="6f416-265">allowedThreats</span></span> |
| <span data-ttu-id="6f416-266">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="6f416-266">**Data type**</span></span> | <span data-ttu-id="6f416-267">Matriz de cadenas</span><span class="sxs-lookup"><span data-stu-id="6f416-267">Array of strings</span></span> |

#### <a name="disallowed-threat-actions"></a><span data-ttu-id="6f416-268">Acciones de amenazas no permitidos</span><span class="sxs-lookup"><span data-stu-id="6f416-268">Disallowed threat actions</span></span>

<span data-ttu-id="6f416-269">Restringe las acciones que el usuario local de un dispositivo puede realizar cuando se detectan amenazas.</span><span class="sxs-lookup"><span data-stu-id="6f416-269">Restricts the actions that the local user of a device can take when threats are detected.</span></span> <span data-ttu-id="6f416-270">Las acciones incluidas en esta lista no se muestran en la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="6f416-270">The actions included in this list are not displayed in the user interface.</span></span>

|<span data-ttu-id="6f416-271">Section</span><span class="sxs-lookup"><span data-stu-id="6f416-271">Section</span></span>|<span data-ttu-id="6f416-272">Valor</span><span class="sxs-lookup"><span data-stu-id="6f416-272">Value</span></span>|
|:---|:---|
| <span data-ttu-id="6f416-273">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="6f416-273">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="6f416-274">**Key**</span><span class="sxs-lookup"><span data-stu-id="6f416-274">**Key**</span></span> | <span data-ttu-id="6f416-275">disallowedThreatActions</span><span class="sxs-lookup"><span data-stu-id="6f416-275">disallowedThreatActions</span></span> |
| <span data-ttu-id="6f416-276">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="6f416-276">**Data type**</span></span> | <span data-ttu-id="6f416-277">Matriz de cadenas</span><span class="sxs-lookup"><span data-stu-id="6f416-277">Array of strings</span></span> |
| <span data-ttu-id="6f416-278">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="6f416-278">**Possible values**</span></span> | <span data-ttu-id="6f416-279">permitir (restringe a los usuarios permitir amenazas)</span><span class="sxs-lookup"><span data-stu-id="6f416-279">allow (restricts users from allowing threats)</span></span> <br/> <span data-ttu-id="6f416-280">restore (restringe a los usuarios la restauración de amenazas desde la cuarentena)</span><span class="sxs-lookup"><span data-stu-id="6f416-280">restore (restricts users from restoring threats from the quarantine)</span></span> |
| <span data-ttu-id="6f416-281">**Comments**</span><span class="sxs-lookup"><span data-stu-id="6f416-281">**Comments**</span></span> | <span data-ttu-id="6f416-282">Disponible en Microsoft Defender para endpoint versión 100.83.73 o posterior.</span><span class="sxs-lookup"><span data-stu-id="6f416-282">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="threat-type-settings"></a><span data-ttu-id="6f416-283">Configuración del tipo de amenaza</span><span class="sxs-lookup"><span data-stu-id="6f416-283">Threat type settings</span></span>

<span data-ttu-id="6f416-284">Especifica cómo se controlan determinados tipos de amenazas por Microsoft Defender para Endpoint en macOS.</span><span class="sxs-lookup"><span data-stu-id="6f416-284">Specify how certain threat types are handled by Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="6f416-285">Section</span><span class="sxs-lookup"><span data-stu-id="6f416-285">Section</span></span>|<span data-ttu-id="6f416-286">Valor</span><span class="sxs-lookup"><span data-stu-id="6f416-286">Value</span></span>|
|:---|:---|
| <span data-ttu-id="6f416-287">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="6f416-287">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="6f416-288">**Key**</span><span class="sxs-lookup"><span data-stu-id="6f416-288">**Key**</span></span> | <span data-ttu-id="6f416-289">threatTypeSettings</span><span class="sxs-lookup"><span data-stu-id="6f416-289">threatTypeSettings</span></span> |
| <span data-ttu-id="6f416-290">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="6f416-290">**Data type**</span></span> | <span data-ttu-id="6f416-291">Diccionario (preferencia anidada)</span><span class="sxs-lookup"><span data-stu-id="6f416-291">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="6f416-292">**Comments**</span><span class="sxs-lookup"><span data-stu-id="6f416-292">**Comments**</span></span> | <span data-ttu-id="6f416-293">Vea las secciones siguientes para obtener una descripción del contenido del diccionario.</span><span class="sxs-lookup"><span data-stu-id="6f416-293">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="threat-type"></a><span data-ttu-id="6f416-294">Tipo de amenaza</span><span class="sxs-lookup"><span data-stu-id="6f416-294">Threat type</span></span>

<span data-ttu-id="6f416-295">Especifique tipos de amenazas.</span><span class="sxs-lookup"><span data-stu-id="6f416-295">Specify threat types.</span></span>

|<span data-ttu-id="6f416-296">Section</span><span class="sxs-lookup"><span data-stu-id="6f416-296">Section</span></span>|<span data-ttu-id="6f416-297">Valor</span><span class="sxs-lookup"><span data-stu-id="6f416-297">Value</span></span>|
|:---|:---|
| <span data-ttu-id="6f416-298">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="6f416-298">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="6f416-299">**Key**</span><span class="sxs-lookup"><span data-stu-id="6f416-299">**Key**</span></span> | <span data-ttu-id="6f416-300">clave</span><span class="sxs-lookup"><span data-stu-id="6f416-300">key</span></span> |
| <span data-ttu-id="6f416-301">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="6f416-301">**Data type**</span></span> | <span data-ttu-id="6f416-302">Cadena</span><span class="sxs-lookup"><span data-stu-id="6f416-302">String</span></span> |
| <span data-ttu-id="6f416-303">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="6f416-303">**Possible values**</span></span> | <span data-ttu-id="6f416-304">potentially_unwanted_application</span><span class="sxs-lookup"><span data-stu-id="6f416-304">potentially_unwanted_application</span></span> <br/> <span data-ttu-id="6f416-305">archive_bomb</span><span class="sxs-lookup"><span data-stu-id="6f416-305">archive_bomb</span></span> |

##### <a name="action-to-take"></a><span data-ttu-id="6f416-306">Acción que puede realizar</span><span class="sxs-lookup"><span data-stu-id="6f416-306">Action to take</span></span>

<span data-ttu-id="6f416-307">Especifique qué acción realizar cuando se detecte una amenaza del tipo especificado en la sección anterior.</span><span class="sxs-lookup"><span data-stu-id="6f416-307">Specify what action to take when a threat of the type specified in the preceding section is detected.</span></span> <span data-ttu-id="6f416-308">Seleccione una de las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="6f416-308">Choose from the following options:</span></span>

- <span data-ttu-id="6f416-309">**Auditoría:** el dispositivo no está protegido contra este tipo de amenaza, pero se registra una entrada sobre la amenaza.</span><span class="sxs-lookup"><span data-stu-id="6f416-309">**Audit**: your device is not protected against this type of threat, but an entry about the threat is logged.</span></span>
- <span data-ttu-id="6f416-310">**Bloquear:** el dispositivo está protegido contra este tipo de amenaza y se te notificará en la interfaz de usuario y en la consola de seguridad.</span><span class="sxs-lookup"><span data-stu-id="6f416-310">**Block**: your device is protected against this type of threat and you are notified in the user interface and the security console.</span></span>
- <span data-ttu-id="6f416-311">**Desactivado:** el dispositivo no está protegido contra este tipo de amenaza y no se registra nada.</span><span class="sxs-lookup"><span data-stu-id="6f416-311">**Off**: your device is not protected against this type of threat and nothing is logged.</span></span>

|<span data-ttu-id="6f416-312">Section</span><span class="sxs-lookup"><span data-stu-id="6f416-312">Section</span></span>|<span data-ttu-id="6f416-313">Valor</span><span class="sxs-lookup"><span data-stu-id="6f416-313">Value</span></span>|
|:---|:---|
| <span data-ttu-id="6f416-314">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="6f416-314">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="6f416-315">**Key**</span><span class="sxs-lookup"><span data-stu-id="6f416-315">**Key**</span></span> | <span data-ttu-id="6f416-316">valor</span><span class="sxs-lookup"><span data-stu-id="6f416-316">value</span></span> |
| <span data-ttu-id="6f416-317">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="6f416-317">**Data type**</span></span> | <span data-ttu-id="6f416-318">Cadena</span><span class="sxs-lookup"><span data-stu-id="6f416-318">String</span></span> |
| <span data-ttu-id="6f416-319">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="6f416-319">**Possible values**</span></span> | <span data-ttu-id="6f416-320">auditoría (valor predeterminado)</span><span class="sxs-lookup"><span data-stu-id="6f416-320">audit (default)</span></span> <br/> <span data-ttu-id="6f416-321">bloque</span><span class="sxs-lookup"><span data-stu-id="6f416-321">block</span></span> <br/> <span data-ttu-id="6f416-322">off</span><span class="sxs-lookup"><span data-stu-id="6f416-322">off</span></span> |

#### <a name="threat-type-settings-merge-policy"></a><span data-ttu-id="6f416-323">Directiva de combinación de configuración de tipo de amenaza</span><span class="sxs-lookup"><span data-stu-id="6f416-323">Threat type settings merge policy</span></span>

<span data-ttu-id="6f416-324">Especifique la directiva de combinación para la configuración del tipo de amenaza.</span><span class="sxs-lookup"><span data-stu-id="6f416-324">Specify the merge policy for threat type settings.</span></span> <span data-ttu-id="6f416-325">Puede ser una combinación de opciones definidas por el administrador y definidas por el usuario ( ) o solo opciones definidas `merge` por el administrador ( `admin_only` ).</span><span class="sxs-lookup"><span data-stu-id="6f416-325">This can be a combination of administrator-defined and user-defined settings (`merge`) or only administrator-defined settings (`admin_only`).</span></span> <span data-ttu-id="6f416-326">Esta configuración se puede usar para restringir que los usuarios locales definan su propia configuración para diferentes tipos de amenazas.</span><span class="sxs-lookup"><span data-stu-id="6f416-326">This setting can be used to restrict local users from defining their own settings for different threat types.</span></span>

|<span data-ttu-id="6f416-327">Section</span><span class="sxs-lookup"><span data-stu-id="6f416-327">Section</span></span>|<span data-ttu-id="6f416-328">Valor</span><span class="sxs-lookup"><span data-stu-id="6f416-328">Value</span></span>|
|:---|:---|
| <span data-ttu-id="6f416-329">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="6f416-329">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="6f416-330">**Key**</span><span class="sxs-lookup"><span data-stu-id="6f416-330">**Key**</span></span> | <span data-ttu-id="6f416-331">threatTypeSettingsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="6f416-331">threatTypeSettingsMergePolicy</span></span> |
| <span data-ttu-id="6f416-332">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="6f416-332">**Data type**</span></span> | <span data-ttu-id="6f416-333">Cadena</span><span class="sxs-lookup"><span data-stu-id="6f416-333">String</span></span> |
| <span data-ttu-id="6f416-334">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="6f416-334">**Possible values**</span></span> | <span data-ttu-id="6f416-335">merge (valor predeterminado)</span><span class="sxs-lookup"><span data-stu-id="6f416-335">merge (default)</span></span> <br/> <span data-ttu-id="6f416-336">admin_only</span><span class="sxs-lookup"><span data-stu-id="6f416-336">admin_only</span></span> |
| <span data-ttu-id="6f416-337">**Comments**</span><span class="sxs-lookup"><span data-stu-id="6f416-337">**Comments**</span></span> | <span data-ttu-id="6f416-338">Disponible en Microsoft Defender para endpoint versión 100.83.73 o posterior.</span><span class="sxs-lookup"><span data-stu-id="6f416-338">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="antivirus-scan-history-retention-in-days"></a><span data-ttu-id="6f416-339">Retención del historial de examen antivirus (en días)</span><span class="sxs-lookup"><span data-stu-id="6f416-339">Antivirus scan history retention (in days)</span></span>

<span data-ttu-id="6f416-340">Especifica el número de días que los resultados se conservan en el historial de examen del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6f416-340">Specify the number of days that results are retained in the scan history on the device.</span></span> <span data-ttu-id="6f416-341">Los resultados del examen antiguos se quitan del historial.</span><span class="sxs-lookup"><span data-stu-id="6f416-341">Old scan results are removed from the history.</span></span> <span data-ttu-id="6f416-342">Archivos antiguos en cuarentena que también se quitan del disco.</span><span class="sxs-lookup"><span data-stu-id="6f416-342">Old quarantined files that are also removed from the disk.</span></span>

|<span data-ttu-id="6f416-343">Section</span><span class="sxs-lookup"><span data-stu-id="6f416-343">Section</span></span>|<span data-ttu-id="6f416-344">Valor</span><span class="sxs-lookup"><span data-stu-id="6f416-344">Value</span></span>|
|:---|:---|
| <span data-ttu-id="6f416-345">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="6f416-345">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="6f416-346">**Key**</span><span class="sxs-lookup"><span data-stu-id="6f416-346">**Key**</span></span> | <span data-ttu-id="6f416-347">scanResultsRetentionDays</span><span class="sxs-lookup"><span data-stu-id="6f416-347">scanResultsRetentionDays</span></span> |
| <span data-ttu-id="6f416-348">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="6f416-348">**Data type**</span></span> | <span data-ttu-id="6f416-349">Cadena</span><span class="sxs-lookup"><span data-stu-id="6f416-349">String</span></span> |
| <span data-ttu-id="6f416-350">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="6f416-350">**Possible values**</span></span> | <span data-ttu-id="6f416-351">90 (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="6f416-351">90 (default).</span></span> <span data-ttu-id="6f416-352">Los valores permitidos van de 1 día a 180 días.</span><span class="sxs-lookup"><span data-stu-id="6f416-352">Allowed values are from 1 day to 180 days.</span></span> |
| <span data-ttu-id="6f416-353">**Comments**</span><span class="sxs-lookup"><span data-stu-id="6f416-353">**Comments**</span></span> | <span data-ttu-id="6f416-354">Disponible en Microsoft Defender para endpoint versión 101.07.23 o posterior.</span><span class="sxs-lookup"><span data-stu-id="6f416-354">Available in Microsoft Defender for Endpoint version 101.07.23 or higher.</span></span> |

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a><span data-ttu-id="6f416-355">Número máximo de elementos en el historial de examen antivirus</span><span class="sxs-lookup"><span data-stu-id="6f416-355">Maximum number of items in the antivirus scan history</span></span>

<span data-ttu-id="6f416-356">Especifique el número máximo de entradas que se deben conservar en el historial de examen.</span><span class="sxs-lookup"><span data-stu-id="6f416-356">Specify the maximum number of entries to keep in the scan history.</span></span> <span data-ttu-id="6f416-357">Las entradas incluyen todos los exámenes a petición realizados en el pasado y todas las detecciones de antivirus.</span><span class="sxs-lookup"><span data-stu-id="6f416-357">Entries include all on-demand scans performed in the past and all antivirus detections.</span></span>

|<span data-ttu-id="6f416-358">Section</span><span class="sxs-lookup"><span data-stu-id="6f416-358">Section</span></span>|<span data-ttu-id="6f416-359">Valor</span><span class="sxs-lookup"><span data-stu-id="6f416-359">Value</span></span>|
|:---|:---|
| <span data-ttu-id="6f416-360">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="6f416-360">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="6f416-361">**Key**</span><span class="sxs-lookup"><span data-stu-id="6f416-361">**Key**</span></span> | <span data-ttu-id="6f416-362">scanHistoryMaximumItems</span><span class="sxs-lookup"><span data-stu-id="6f416-362">scanHistoryMaximumItems</span></span> |
| <span data-ttu-id="6f416-363">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="6f416-363">**Data type**</span></span> | <span data-ttu-id="6f416-364">Cadena</span><span class="sxs-lookup"><span data-stu-id="6f416-364">String</span></span> |
| <span data-ttu-id="6f416-365">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="6f416-365">**Possible values**</span></span> | <span data-ttu-id="6f416-366">10000 (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="6f416-366">10000 (default).</span></span> <span data-ttu-id="6f416-367">Los valores permitidos van de 5000 elementos a 15000 elementos.</span><span class="sxs-lookup"><span data-stu-id="6f416-367">Allowed values are from 5000 items to 15000 items.</span></span> |
| <span data-ttu-id="6f416-368">**Comments**</span><span class="sxs-lookup"><span data-stu-id="6f416-368">**Comments**</span></span> | <span data-ttu-id="6f416-369">Disponible en Microsoft Defender para endpoint versión 101.07.23 o posterior.</span><span class="sxs-lookup"><span data-stu-id="6f416-369">Available in Microsoft Defender for Endpoint version 101.07.23 or higher.</span></span> |

### <a name="cloud-delivered-protection-preferences"></a><span data-ttu-id="6f416-370">Preferencias de protección entregadas en la nube</span><span class="sxs-lookup"><span data-stu-id="6f416-370">Cloud-delivered protection preferences</span></span>

<span data-ttu-id="6f416-371">Configure las características de protección controlada por la nube de Microsoft Defender para Endpoint en macOS.</span><span class="sxs-lookup"><span data-stu-id="6f416-371">Configure the cloud-driven protection features of Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="6f416-372">Section</span><span class="sxs-lookup"><span data-stu-id="6f416-372">Section</span></span>|<span data-ttu-id="6f416-373">Valor</span><span class="sxs-lookup"><span data-stu-id="6f416-373">Value</span></span>|
|:---|:---|
| <span data-ttu-id="6f416-374">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="6f416-374">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="6f416-375">**Key**</span><span class="sxs-lookup"><span data-stu-id="6f416-375">**Key**</span></span> | <span data-ttu-id="6f416-376">cloudService</span><span class="sxs-lookup"><span data-stu-id="6f416-376">cloudService</span></span> |
| <span data-ttu-id="6f416-377">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="6f416-377">**Data type**</span></span> | <span data-ttu-id="6f416-378">Diccionario (preferencia anidada)</span><span class="sxs-lookup"><span data-stu-id="6f416-378">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="6f416-379">**Comments**</span><span class="sxs-lookup"><span data-stu-id="6f416-379">**Comments**</span></span> | <span data-ttu-id="6f416-380">Vea las secciones siguientes para obtener una descripción del contenido del diccionario.</span><span class="sxs-lookup"><span data-stu-id="6f416-380">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="enable--disable-cloud-delivered-protection"></a><span data-ttu-id="6f416-381">Habilitar o deshabilitar la protección entregada en la nube</span><span class="sxs-lookup"><span data-stu-id="6f416-381">Enable / disable cloud-delivered protection</span></span>

<span data-ttu-id="6f416-382">Especifica si se va a habilitar la protección entregada en la nube del dispositivo o no.</span><span class="sxs-lookup"><span data-stu-id="6f416-382">Specify whether to enable cloud-delivered protection the device or not.</span></span> <span data-ttu-id="6f416-383">Para mejorar la seguridad de los servicios, se recomienda mantener activada esta característica.</span><span class="sxs-lookup"><span data-stu-id="6f416-383">To improve the security of your services, we recommend keeping this feature turned on.</span></span>

|<span data-ttu-id="6f416-384">Section</span><span class="sxs-lookup"><span data-stu-id="6f416-384">Section</span></span>|<span data-ttu-id="6f416-385">Valor</span><span class="sxs-lookup"><span data-stu-id="6f416-385">Value</span></span>|
|:---|:---|
| <span data-ttu-id="6f416-386">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="6f416-386">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="6f416-387">**Key**</span><span class="sxs-lookup"><span data-stu-id="6f416-387">**Key**</span></span> | <span data-ttu-id="6f416-388">habilitado</span><span class="sxs-lookup"><span data-stu-id="6f416-388">enabled</span></span> |
| <span data-ttu-id="6f416-389">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="6f416-389">**Data type**</span></span> | <span data-ttu-id="6f416-390">Booleano</span><span class="sxs-lookup"><span data-stu-id="6f416-390">Boolean</span></span> |
| <span data-ttu-id="6f416-391">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="6f416-391">**Possible values**</span></span> | <span data-ttu-id="6f416-392">true (valor predeterminado)</span><span class="sxs-lookup"><span data-stu-id="6f416-392">true (default)</span></span> <br/> <span data-ttu-id="6f416-393">false</span><span class="sxs-lookup"><span data-stu-id="6f416-393">false</span></span> |

#### <a name="diagnostic-collection-level"></a><span data-ttu-id="6f416-394">Nivel de colección de diagnóstico</span><span class="sxs-lookup"><span data-stu-id="6f416-394">Diagnostic collection level</span></span>

<span data-ttu-id="6f416-395">Los datos de diagnóstico se usan para mantener Microsoft Defender for Endpoint seguro y actualizado, detectar, diagnosticar y corregir problemas y también realizar mejoras en el producto.</span><span class="sxs-lookup"><span data-stu-id="6f416-395">Diagnostic data is used to keep Microsoft Defender for Endpoint secure and up-to-date, detect, diagnose and fix problems, and also make product improvements.</span></span> <span data-ttu-id="6f416-396">Esta configuración determina el nivel de diagnóstico enviado por Microsoft Defender para Endpoint a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6f416-396">This setting determines the level of diagnostics sent by Microsoft Defender for Endpoint to Microsoft.</span></span>

|<span data-ttu-id="6f416-397">Section</span><span class="sxs-lookup"><span data-stu-id="6f416-397">Section</span></span>|<span data-ttu-id="6f416-398">Valor</span><span class="sxs-lookup"><span data-stu-id="6f416-398">Value</span></span>|
|:---|:---|
| <span data-ttu-id="6f416-399">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="6f416-399">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="6f416-400">**Key**</span><span class="sxs-lookup"><span data-stu-id="6f416-400">**Key**</span></span> | <span data-ttu-id="6f416-401">diagnosticLevel</span><span class="sxs-lookup"><span data-stu-id="6f416-401">diagnosticLevel</span></span> |
| <span data-ttu-id="6f416-402">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="6f416-402">**Data type**</span></span> | <span data-ttu-id="6f416-403">Cadena</span><span class="sxs-lookup"><span data-stu-id="6f416-403">String</span></span> |
| <span data-ttu-id="6f416-404">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="6f416-404">**Possible values**</span></span> | <span data-ttu-id="6f416-405">opcional (predeterminado)</span><span class="sxs-lookup"><span data-stu-id="6f416-405">optional (default)</span></span> <br/> <span data-ttu-id="6f416-406">necesario</span><span class="sxs-lookup"><span data-stu-id="6f416-406">required</span></span> |

#### <a name="enable--disable-automatic-sample-submissions"></a><span data-ttu-id="6f416-407">Habilitar o deshabilitar envíos de ejemplo automáticos</span><span class="sxs-lookup"><span data-stu-id="6f416-407">Enable / disable automatic sample submissions</span></span>

<span data-ttu-id="6f416-408">Determina si se envían muestras sospechosas (que probablemente contengan amenazas) a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6f416-408">Determines whether suspicious samples (that are likely to contain threats) are sent to Microsoft.</span></span> <span data-ttu-id="6f416-409">Se le preguntará si es probable que el archivo enviado contenga información personal.</span><span class="sxs-lookup"><span data-stu-id="6f416-409">You are prompted if the submitted file is likely to contain personal information.</span></span>

|<span data-ttu-id="6f416-410">Section</span><span class="sxs-lookup"><span data-stu-id="6f416-410">Section</span></span>|<span data-ttu-id="6f416-411">Valor</span><span class="sxs-lookup"><span data-stu-id="6f416-411">Value</span></span>|
|:---|:---|
| <span data-ttu-id="6f416-412">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="6f416-412">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="6f416-413">**Key**</span><span class="sxs-lookup"><span data-stu-id="6f416-413">**Key**</span></span> | <span data-ttu-id="6f416-414">automaticSampleSubmission</span><span class="sxs-lookup"><span data-stu-id="6f416-414">automaticSampleSubmission</span></span> |
| <span data-ttu-id="6f416-415">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="6f416-415">**Data type**</span></span> | <span data-ttu-id="6f416-416">Booleano</span><span class="sxs-lookup"><span data-stu-id="6f416-416">Boolean</span></span> |
| <span data-ttu-id="6f416-417">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="6f416-417">**Possible values**</span></span> | <span data-ttu-id="6f416-418">true (valor predeterminado)</span><span class="sxs-lookup"><span data-stu-id="6f416-418">true (default)</span></span> <br/> <span data-ttu-id="6f416-419">false</span><span class="sxs-lookup"><span data-stu-id="6f416-419">false</span></span> |

#### <a name="enable--disable-automatic-security-intelligence-updates"></a><span data-ttu-id="6f416-420">Habilitar o deshabilitar actualizaciones automáticas de inteligencia de seguridad</span><span class="sxs-lookup"><span data-stu-id="6f416-420">Enable / disable automatic security intelligence updates</span></span>

<span data-ttu-id="6f416-421">Determina si las actualizaciones de inteligencia de seguridad se instalan automáticamente:</span><span class="sxs-lookup"><span data-stu-id="6f416-421">Determines whether security intelligence updates are installed automatically:</span></span>

|<span data-ttu-id="6f416-422">Section</span><span class="sxs-lookup"><span data-stu-id="6f416-422">Section</span></span>|<span data-ttu-id="6f416-423">Valor</span><span class="sxs-lookup"><span data-stu-id="6f416-423">Value</span></span>|
|:---|:---|
| <span data-ttu-id="6f416-424">**Key**</span><span class="sxs-lookup"><span data-stu-id="6f416-424">**Key**</span></span> | <span data-ttu-id="6f416-425">automaticDefinitionUpdateEnabled</span><span class="sxs-lookup"><span data-stu-id="6f416-425">automaticDefinitionUpdateEnabled</span></span> |
| <span data-ttu-id="6f416-426">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="6f416-426">**Data type**</span></span> | <span data-ttu-id="6f416-427">Booleano</span><span class="sxs-lookup"><span data-stu-id="6f416-427">Boolean</span></span> |
| <span data-ttu-id="6f416-428">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="6f416-428">**Possible values**</span></span> | <span data-ttu-id="6f416-429">true (valor predeterminado)</span><span class="sxs-lookup"><span data-stu-id="6f416-429">true (default)</span></span> <br/> <span data-ttu-id="6f416-430">false</span><span class="sxs-lookup"><span data-stu-id="6f416-430">false</span></span> |

### <a name="user-interface-preferences"></a><span data-ttu-id="6f416-431">Preferencias de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="6f416-431">User interface preferences</span></span>

<span data-ttu-id="6f416-432">Administrar las preferencias de la interfaz de usuario de Microsoft Defender para Endpoint en macOS.</span><span class="sxs-lookup"><span data-stu-id="6f416-432">Manage the preferences for the user interface of Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="6f416-433">Section</span><span class="sxs-lookup"><span data-stu-id="6f416-433">Section</span></span>|<span data-ttu-id="6f416-434">Valor</span><span class="sxs-lookup"><span data-stu-id="6f416-434">Value</span></span>|
|:---|:---|
| <span data-ttu-id="6f416-435">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="6f416-435">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="6f416-436">**Key**</span><span class="sxs-lookup"><span data-stu-id="6f416-436">**Key**</span></span> | <span data-ttu-id="6f416-437">userInterface</span><span class="sxs-lookup"><span data-stu-id="6f416-437">userInterface</span></span> |
| <span data-ttu-id="6f416-438">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="6f416-438">**Data type**</span></span> | <span data-ttu-id="6f416-439">Diccionario (preferencia anidada)</span><span class="sxs-lookup"><span data-stu-id="6f416-439">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="6f416-440">**Comments**</span><span class="sxs-lookup"><span data-stu-id="6f416-440">**Comments**</span></span> | <span data-ttu-id="6f416-441">Vea las secciones siguientes para obtener una descripción del contenido del diccionario.</span><span class="sxs-lookup"><span data-stu-id="6f416-441">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="show--hide-status-menu-icon"></a><span data-ttu-id="6f416-442">Mostrar u ocultar icono de menú de estado</span><span class="sxs-lookup"><span data-stu-id="6f416-442">Show / hide status menu icon</span></span>

<span data-ttu-id="6f416-443">Especifique si desea mostrar u ocultar el icono del menú de estado en la esquina superior derecha de la pantalla.</span><span class="sxs-lookup"><span data-stu-id="6f416-443">Specify whether to show or hide the status menu icon in the top-right corner of the screen.</span></span>

|<span data-ttu-id="6f416-444">Section</span><span class="sxs-lookup"><span data-stu-id="6f416-444">Section</span></span>|<span data-ttu-id="6f416-445">Valor</span><span class="sxs-lookup"><span data-stu-id="6f416-445">Value</span></span>|
|:---|:---|
| <span data-ttu-id="6f416-446">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="6f416-446">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="6f416-447">**Key**</span><span class="sxs-lookup"><span data-stu-id="6f416-447">**Key**</span></span> | <span data-ttu-id="6f416-448">hideStatusMenuIcon</span><span class="sxs-lookup"><span data-stu-id="6f416-448">hideStatusMenuIcon</span></span> |
| <span data-ttu-id="6f416-449">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="6f416-449">**Data type**</span></span> | <span data-ttu-id="6f416-450">Booleano</span><span class="sxs-lookup"><span data-stu-id="6f416-450">Boolean</span></span> |
| <span data-ttu-id="6f416-451">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="6f416-451">**Possible values**</span></span> | <span data-ttu-id="6f416-452">false (predeterminado)</span><span class="sxs-lookup"><span data-stu-id="6f416-452">false (default)</span></span> <br/> <span data-ttu-id="6f416-453">true</span><span class="sxs-lookup"><span data-stu-id="6f416-453">true</span></span> |

#### <a name="show--hide-option-to-send-feedback"></a><span data-ttu-id="6f416-454">Mostrar u ocultar opción para enviar comentarios</span><span class="sxs-lookup"><span data-stu-id="6f416-454">Show / hide option to send feedback</span></span>

<span data-ttu-id="6f416-455">Especifica si los usuarios pueden enviar comentarios a Microsoft yendo a `Help`  >  `Send Feedback` .</span><span class="sxs-lookup"><span data-stu-id="6f416-455">Specify whether users can submit feedback to Microsoft by going to `Help` > `Send Feedback`.</span></span>

|<span data-ttu-id="6f416-456">Section</span><span class="sxs-lookup"><span data-stu-id="6f416-456">Section</span></span>|<span data-ttu-id="6f416-457">Valor</span><span class="sxs-lookup"><span data-stu-id="6f416-457">Value</span></span>|
|:---|:---|
| <span data-ttu-id="6f416-458">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="6f416-458">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="6f416-459">**Key**</span><span class="sxs-lookup"><span data-stu-id="6f416-459">**Key**</span></span> | <span data-ttu-id="6f416-460">userInitiatedFeedback</span><span class="sxs-lookup"><span data-stu-id="6f416-460">userInitiatedFeedback</span></span> |
| <span data-ttu-id="6f416-461">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="6f416-461">**Data type**</span></span> | <span data-ttu-id="6f416-462">Cadena</span><span class="sxs-lookup"><span data-stu-id="6f416-462">String</span></span> |
| <span data-ttu-id="6f416-463">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="6f416-463">**Possible values**</span></span> | <span data-ttu-id="6f416-464">habilitado (predeterminado)</span><span class="sxs-lookup"><span data-stu-id="6f416-464">enabled (default)</span></span> <br/> <span data-ttu-id="6f416-465">deshabilitado</span><span class="sxs-lookup"><span data-stu-id="6f416-465">disabled</span></span> |
| <span data-ttu-id="6f416-466">**Comments**</span><span class="sxs-lookup"><span data-stu-id="6f416-466">**Comments**</span></span> | <span data-ttu-id="6f416-467">Disponible en Microsoft Defender para endpoint versión 101.19.61 o posterior.</span><span class="sxs-lookup"><span data-stu-id="6f416-467">Available in Microsoft Defender for Endpoint version 101.19.61 or higher.</span></span> |

### <a name="endpoint-detection-and-response-preferences"></a><span data-ttu-id="6f416-468">Preferencias de detección y respuesta de extremos</span><span class="sxs-lookup"><span data-stu-id="6f416-468">Endpoint detection and response preferences</span></span>

<span data-ttu-id="6f416-469">Administrar las preferencias del componente de detección y respuesta de puntos de conexión (EDR) de Microsoft Defender para endpoint en macOS.</span><span class="sxs-lookup"><span data-stu-id="6f416-469">Manage the preferences of the endpoint detection and response (EDR) component of Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="6f416-470">Section</span><span class="sxs-lookup"><span data-stu-id="6f416-470">Section</span></span>|<span data-ttu-id="6f416-471">Valor</span><span class="sxs-lookup"><span data-stu-id="6f416-471">Value</span></span>|
|:---|:---|
| <span data-ttu-id="6f416-472">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="6f416-472">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="6f416-473">**Key**</span><span class="sxs-lookup"><span data-stu-id="6f416-473">**Key**</span></span> | <span data-ttu-id="6f416-474">edr</span><span class="sxs-lookup"><span data-stu-id="6f416-474">edr</span></span> |
| <span data-ttu-id="6f416-475">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="6f416-475">**Data type**</span></span> | <span data-ttu-id="6f416-476">Diccionario (preferencia anidada)</span><span class="sxs-lookup"><span data-stu-id="6f416-476">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="6f416-477">**Comments**</span><span class="sxs-lookup"><span data-stu-id="6f416-477">**Comments**</span></span> | <span data-ttu-id="6f416-478">Vea las secciones siguientes para obtener una descripción del contenido del diccionario.</span><span class="sxs-lookup"><span data-stu-id="6f416-478">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="device-tags"></a><span data-ttu-id="6f416-479">Etiquetas de dispositivo</span><span class="sxs-lookup"><span data-stu-id="6f416-479">Device tags</span></span>

<span data-ttu-id="6f416-480">Especifique un nombre de etiqueta y su valor.</span><span class="sxs-lookup"><span data-stu-id="6f416-480">Specify a tag name and its value.</span></span> 

- <span data-ttu-id="6f416-481">La etiqueta GROUP, etiqueta el dispositivo con el valor especificado.</span><span class="sxs-lookup"><span data-stu-id="6f416-481">The GROUP tag, tags the device with the specified value.</span></span> <span data-ttu-id="6f416-482">La etiqueta se refleja en el portal en la página del dispositivo y se puede usar para filtrar y agrupar dispositivos.</span><span class="sxs-lookup"><span data-stu-id="6f416-482">The tag is reflected in the portal under the device page and can be used for filtering and grouping devices.</span></span>

|<span data-ttu-id="6f416-483">Section</span><span class="sxs-lookup"><span data-stu-id="6f416-483">Section</span></span>|<span data-ttu-id="6f416-484">Valor</span><span class="sxs-lookup"><span data-stu-id="6f416-484">Value</span></span>|
|:---|:---|
| <span data-ttu-id="6f416-485">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="6f416-485">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="6f416-486">**Key**</span><span class="sxs-lookup"><span data-stu-id="6f416-486">**Key**</span></span> | <span data-ttu-id="6f416-487">tags</span><span class="sxs-lookup"><span data-stu-id="6f416-487">tags</span></span> |
| <span data-ttu-id="6f416-488">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="6f416-488">**Data type**</span></span> | <span data-ttu-id="6f416-489">Diccionario (preferencia anidada)</span><span class="sxs-lookup"><span data-stu-id="6f416-489">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="6f416-490">**Comments**</span><span class="sxs-lookup"><span data-stu-id="6f416-490">**Comments**</span></span> | <span data-ttu-id="6f416-491">Vea las secciones siguientes para obtener una descripción del contenido del diccionario.</span><span class="sxs-lookup"><span data-stu-id="6f416-491">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="type-of-tag"></a><span data-ttu-id="6f416-492">Tipo de etiqueta</span><span class="sxs-lookup"><span data-stu-id="6f416-492">Type of tag</span></span>

<span data-ttu-id="6f416-493">Especifica el tipo de etiqueta</span><span class="sxs-lookup"><span data-stu-id="6f416-493">Specifies the type of tag</span></span>

|<span data-ttu-id="6f416-494">Section</span><span class="sxs-lookup"><span data-stu-id="6f416-494">Section</span></span>|<span data-ttu-id="6f416-495">Valor</span><span class="sxs-lookup"><span data-stu-id="6f416-495">Value</span></span>|
|:---|:---|
| <span data-ttu-id="6f416-496">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="6f416-496">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="6f416-497">**Key**</span><span class="sxs-lookup"><span data-stu-id="6f416-497">**Key**</span></span> | <span data-ttu-id="6f416-498">clave</span><span class="sxs-lookup"><span data-stu-id="6f416-498">key</span></span> |
| <span data-ttu-id="6f416-499">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="6f416-499">**Data type**</span></span> | <span data-ttu-id="6f416-500">Cadena</span><span class="sxs-lookup"><span data-stu-id="6f416-500">String</span></span> |
| <span data-ttu-id="6f416-501">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="6f416-501">**Possible values**</span></span> | `GROUP` |

##### <a name="value-of-tag"></a><span data-ttu-id="6f416-502">Valor de etiqueta</span><span class="sxs-lookup"><span data-stu-id="6f416-502">Value of tag</span></span>

<span data-ttu-id="6f416-503">Especifica el valor de la etiqueta</span><span class="sxs-lookup"><span data-stu-id="6f416-503">Specifies the value of tag</span></span>

|<span data-ttu-id="6f416-504">Section</span><span class="sxs-lookup"><span data-stu-id="6f416-504">Section</span></span>|<span data-ttu-id="6f416-505">Valor</span><span class="sxs-lookup"><span data-stu-id="6f416-505">Value</span></span>|
|:---|:---|
| <span data-ttu-id="6f416-506">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="6f416-506">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="6f416-507">**Key**</span><span class="sxs-lookup"><span data-stu-id="6f416-507">**Key**</span></span> | <span data-ttu-id="6f416-508">valor</span><span class="sxs-lookup"><span data-stu-id="6f416-508">value</span></span> |
| <span data-ttu-id="6f416-509">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="6f416-509">**Data type**</span></span> | <span data-ttu-id="6f416-510">Cadena</span><span class="sxs-lookup"><span data-stu-id="6f416-510">String</span></span> |
| <span data-ttu-id="6f416-511">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="6f416-511">**Possible values**</span></span> | <span data-ttu-id="6f416-512">cualquier cadena</span><span class="sxs-lookup"><span data-stu-id="6f416-512">any string</span></span> |

> [!IMPORTANT]  
> - <span data-ttu-id="6f416-513">Solo se puede establecer un valor por tipo de etiqueta.</span><span class="sxs-lookup"><span data-stu-id="6f416-513">Only one value per tag type can be set.</span></span>
> - <span data-ttu-id="6f416-514">El tipo de etiquetas es único y no debe repetirse en el mismo perfil de configuración.</span><span class="sxs-lookup"><span data-stu-id="6f416-514">Type of tags are unique, and should not be repeated in the same configuration profile.</span></span>

## <a name="recommended-configuration-profile"></a><span data-ttu-id="6f416-515">Perfil de configuración recomendado</span><span class="sxs-lookup"><span data-stu-id="6f416-515">Recommended configuration profile</span></span>

<span data-ttu-id="6f416-516">Para empezar, se recomienda la siguiente configuración para que la empresa aproveche todas las características de protección que proporciona Microsoft Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="6f416-516">To get started, we recommend the following configuration for your enterprise to take advantage of all protection features that Microsoft Defender for Endpoint provides.</span></span>

<span data-ttu-id="6f416-517">El siguiente perfil de configuración (o, en el caso de JAMF, una lista de propiedades que podría cargarse en el perfil de configuración de configuración personalizada) será:</span><span class="sxs-lookup"><span data-stu-id="6f416-517">The following configuration profile (or, in case of JAMF, a property list that could be uploaded into the custom settings configuration profile) will:</span></span>
- <span data-ttu-id="6f416-518">Habilitar la protección en tiempo real (RTP)</span><span class="sxs-lookup"><span data-stu-id="6f416-518">Enable real-time protection (RTP)</span></span>
- <span data-ttu-id="6f416-519">Especifique cómo se controlan los siguientes tipos de amenazas:</span><span class="sxs-lookup"><span data-stu-id="6f416-519">Specify how the following threat types are handled:</span></span>
  - <span data-ttu-id="6f416-520">**Las aplicaciones potencialmente no deseadas (PUA)** están bloqueadas</span><span class="sxs-lookup"><span data-stu-id="6f416-520">**Potentially unwanted applications (PUA)** are blocked</span></span>
  - <span data-ttu-id="6f416-521">**Las bombas de archivo** (archivo con una tasa de compresión alta) se auditan en Microsoft Defender para los registros de punto de conexión</span><span class="sxs-lookup"><span data-stu-id="6f416-521">**Archive bombs** (file with a high compression rate) are audited to Microsoft Defender for Endpoint logs</span></span>
- <span data-ttu-id="6f416-522">Habilitar actualizaciones automáticas de inteligencia de seguridad</span><span class="sxs-lookup"><span data-stu-id="6f416-522">Enable automatic security intelligence updates</span></span>
- <span data-ttu-id="6f416-523">Habilitar la protección de entrega en la nube</span><span class="sxs-lookup"><span data-stu-id="6f416-523">Enable cloud-delivered protection</span></span>
- <span data-ttu-id="6f416-524">Habilitar el envío automático de muestra</span><span class="sxs-lookup"><span data-stu-id="6f416-524">Enable automatic sample submission</span></span>

### <a name="property-list-for-jamf-configuration-profile"></a><span data-ttu-id="6f416-525">Lista de propiedades para el perfil de configuración de JAMF</span><span class="sxs-lookup"><span data-stu-id="6f416-525">Property list for JAMF configuration profile</span></span>

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

### <a name="intune-profile"></a><span data-ttu-id="6f416-526">Perfil de Intune</span><span class="sxs-lookup"><span data-stu-id="6f416-526">Intune profile</span></span>

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

## <a name="full-configuration-profile-example"></a><span data-ttu-id="6f416-527">Ejemplo de perfil de configuración completa</span><span class="sxs-lookup"><span data-stu-id="6f416-527">Full configuration profile example</span></span>

<span data-ttu-id="6f416-528">Las plantillas siguientes contienen entradas para todas las configuraciones descritas en este documento y se pueden usar para escenarios más avanzados en los que desea tener más control sobre Microsoft Defender para Endpoint en macOS.</span><span class="sxs-lookup"><span data-stu-id="6f416-528">The following templates contain entries for all settings described in this document and can be used for more advanced scenarios where you want more control over Microsoft Defender for Endpoint on macOS.</span></span>

### <a name="property-list-for-jamf-configuration-profile"></a><span data-ttu-id="6f416-529">Lista de propiedades para el perfil de configuración de JAMF</span><span class="sxs-lookup"><span data-stu-id="6f416-529">Property list for JAMF configuration profile</span></span>

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

### <a name="intune-profile"></a><span data-ttu-id="6f416-530">Perfil de Intune</span><span class="sxs-lookup"><span data-stu-id="6f416-530">Intune profile</span></span>

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

## <a name="property-list-validation"></a><span data-ttu-id="6f416-531">Validación de lista de propiedades</span><span class="sxs-lookup"><span data-stu-id="6f416-531">Property list validation</span></span>

<span data-ttu-id="6f416-532">La lista de propiedades debe ser un archivo *.plist* válido.</span><span class="sxs-lookup"><span data-stu-id="6f416-532">The property list must be a valid *.plist* file.</span></span> <span data-ttu-id="6f416-533">Esto se puede comprobar ejecutando:</span><span class="sxs-lookup"><span data-stu-id="6f416-533">This can be checked by executing:</span></span>

```bash
plutil -lint com.microsoft.wdav.plist
```
```Output
com.microsoft.wdav.plist: OK
```

<span data-ttu-id="6f416-534">Si el archivo está bien formado, el comando anterior genera `OK` y devuelve un código de salida de `0` .</span><span class="sxs-lookup"><span data-stu-id="6f416-534">If the file is well-formed, the above command outputs `OK` and returns an exit code of `0`.</span></span> <span data-ttu-id="6f416-535">De lo contrario, se muestra un error que describe el problema y el comando devuelve un código de salida de `1` .</span><span class="sxs-lookup"><span data-stu-id="6f416-535">Otherwise, an error that describes the issue is displayed and the command returns an exit code of `1`.</span></span>

## <a name="configuration-profile-deployment"></a><span data-ttu-id="6f416-536">Implementación de perfiles de configuración</span><span class="sxs-lookup"><span data-stu-id="6f416-536">Configuration profile deployment</span></span>

<span data-ttu-id="6f416-537">Una vez que haya creado el perfil de configuración para su empresa, puede implementarlo a través de la consola de administración que usa su empresa.</span><span class="sxs-lookup"><span data-stu-id="6f416-537">Once you've built the configuration profile for your enterprise, you can deploy it through the management console that your enterprise is using.</span></span> <span data-ttu-id="6f416-538">En las secciones siguientes se proporcionan instrucciones sobre cómo implementar este perfil con JAMF e Intune.</span><span class="sxs-lookup"><span data-stu-id="6f416-538">The following sections provide instructions on how to deploy this profile using JAMF and Intune.</span></span>

### <a name="jamf-deployment"></a><span data-ttu-id="6f416-539">Implementación de JAMF</span><span class="sxs-lookup"><span data-stu-id="6f416-539">JAMF deployment</span></span>

<span data-ttu-id="6f416-540">En la consola JAMF, abra **Perfiles** de configuración de equipos, vaya al perfil de configuración que desea usar y, a  >  continuación, seleccione **Configuración personalizada**.</span><span class="sxs-lookup"><span data-stu-id="6f416-540">From the JAMF console, open **Computers** > **Configuration Profiles**, navigate to the configuration profile you'd like to use, then select **Custom Settings**.</span></span> <span data-ttu-id="6f416-541">Cree una entrada con `com.microsoft.wdav` como dominio de preferencia y cargue el *.plist* generado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="6f416-541">Create an entry with `com.microsoft.wdav` as the preference domain and upload the *.plist* produced earlier.</span></span>

>[!CAUTION]
><span data-ttu-id="6f416-542">Debes escribir el dominio de preferencia correcto ( ); de lo contrario, Microsoft Defender no reconocerá las `com.microsoft.wdav` preferencias para endpoint.</span><span class="sxs-lookup"><span data-stu-id="6f416-542">You must enter the correct preference domain (`com.microsoft.wdav`); otherwise, the preferences will not be recognized by Microsoft Defender for Endpoint.</span></span>

### <a name="intune-deployment"></a><span data-ttu-id="6f416-543">Implementación de Intune</span><span class="sxs-lookup"><span data-stu-id="6f416-543">Intune deployment</span></span>

1. <span data-ttu-id="6f416-544">Abra **Administrar configuración** de  >  **dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="6f416-544">Open **Manage** > **Device configuration**.</span></span> <span data-ttu-id="6f416-545">Seleccione **Administrar**  >  **perfiles Crear**  >  **perfil**.</span><span class="sxs-lookup"><span data-stu-id="6f416-545">Select **Manage** > **Profiles** > **Create Profile**.</span></span>

2. <span data-ttu-id="6f416-546">Elija un nombre para el perfil.</span><span class="sxs-lookup"><span data-stu-id="6f416-546">Choose a name for the profile.</span></span> <span data-ttu-id="6f416-547">Cambiar **Platform=macOS** a **Profile type=Custom**.</span><span class="sxs-lookup"><span data-stu-id="6f416-547">Change **Platform=macOS** to **Profile type=Custom**.</span></span> <span data-ttu-id="6f416-548">Seleccione Configurar.</span><span class="sxs-lookup"><span data-stu-id="6f416-548">Select Configure.</span></span>

3. <span data-ttu-id="6f416-549">Guarde el .plist generado anteriormente como `com.microsoft.wdav.xml` .</span><span class="sxs-lookup"><span data-stu-id="6f416-549">Save the .plist produced earlier as `com.microsoft.wdav.xml`.</span></span>

4. <span data-ttu-id="6f416-550">Escriba `com.microsoft.wdav` como el nombre del perfil de configuración **personalizado**.</span><span class="sxs-lookup"><span data-stu-id="6f416-550">Enter `com.microsoft.wdav` as the **custom configuration profile name**.</span></span>

5. <span data-ttu-id="6f416-551">Abra el perfil de configuración y cargue el `com.microsoft.wdav.xml` archivo.</span><span class="sxs-lookup"><span data-stu-id="6f416-551">Open the configuration profile and upload the `com.microsoft.wdav.xml` file.</span></span> <span data-ttu-id="6f416-552">(Este archivo se creó en el paso 3).</span><span class="sxs-lookup"><span data-stu-id="6f416-552">(This file was created in step 3.)</span></span>

6. <span data-ttu-id="6f416-553">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6f416-553">Select **OK**.</span></span>

7. <span data-ttu-id="6f416-554">Seleccione **Administrar**  >  **asignaciones**.</span><span class="sxs-lookup"><span data-stu-id="6f416-554">Select **Manage** > **Assignments**.</span></span> <span data-ttu-id="6f416-555">En la **pestaña Incluir,** seleccione **Asignar a todos los usuarios & Todos los dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="6f416-555">In the **Include** tab, select **Assign to All Users & All devices**.</span></span>

>[!CAUTION]
><span data-ttu-id="6f416-556">Debe escribir el nombre del perfil de configuración personalizado correcto; de lo contrario, Microsoft Defender no reconocerá estas preferencias para endpoint.</span><span class="sxs-lookup"><span data-stu-id="6f416-556">You must enter the correct custom configuration profile name; otherwise, these preferences will not be recognized by Microsoft Defender for Endpoint.</span></span>

## <a name="resources"></a><span data-ttu-id="6f416-557">Recursos</span><span class="sxs-lookup"><span data-stu-id="6f416-557">Resources</span></span>

- [<span data-ttu-id="6f416-558">Referencia de los perfiles de configuración (documentación para desarrolladores de Apple)</span><span class="sxs-lookup"><span data-stu-id="6f416-558">Configuration Profile Reference (Apple developer documentation)</span></span>](https://developer.apple.com/business/documentation/Configuration-Profile-Reference.pdf)
