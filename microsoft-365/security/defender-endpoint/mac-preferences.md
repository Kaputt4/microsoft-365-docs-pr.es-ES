---
title: Establecer preferencias para ATP de Microsoft Defender para Mac
description: Configurar ATP de Microsoft Defender para Mac en organizaciones empresariales.
keywords: microsoft, defender, atp, mac, management, preferences, enterprise, intune, jamf, macos, catalina, mojave, high sierra
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
ms.openlocfilehash: 578830d44a9a69c3ccafd78ceaf59ddfe100e43f
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51076931"
---
# <a name="set-preferences-for-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="9624b-104">Establecer preferencias para Microsoft Defender para Endpoint para Mac</span><span class="sxs-lookup"><span data-stu-id="9624b-104">Set preferences for Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="9624b-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="9624b-105">**Applies to:**</span></span>

- [<span data-ttu-id="9624b-106">Microsoft Defender para endpoint para Mac</span><span class="sxs-lookup"><span data-stu-id="9624b-106">Microsoft Defender for Endpoint for Mac</span></span>](microsoft-defender-endpoint-mac.md)

>[!IMPORTANT]
><span data-ttu-id="9624b-107">Este artículo contiene instrucciones sobre cómo establecer preferencias para Microsoft Defender para Endpoint para Mac en organizaciones empresariales.</span><span class="sxs-lookup"><span data-stu-id="9624b-107">This article contains instructions for how to set preferences for Microsoft Defender for Endpoint for Mac in enterprise organizations.</span></span> <span data-ttu-id="9624b-108">Para configurar Microsoft Defender para Endpoint para Mac mediante la interfaz de línea de comandos, vea [Resources](mac-resources.md#configuring-from-the-command-line).</span><span class="sxs-lookup"><span data-stu-id="9624b-108">To configure Microsoft Defender for Endpoint for Mac using the command-line interface, see [Resources](mac-resources.md#configuring-from-the-command-line).</span></span>

## <a name="summary"></a><span data-ttu-id="9624b-109">Resumen</span><span class="sxs-lookup"><span data-stu-id="9624b-109">Summary</span></span>

<span data-ttu-id="9624b-110">En organizaciones empresariales, Microsoft Defender para Endpoint para Mac se puede administrar a través de un perfil de configuración que se implementa mediante una de varias herramientas de administración.</span><span class="sxs-lookup"><span data-stu-id="9624b-110">In enterprise organizations, Microsoft Defender for Endpoint for Mac can be managed through a configuration profile that is deployed by using one of several management tools.</span></span> <span data-ttu-id="9624b-111">Las preferencias administradas por el equipo de operaciones de seguridad tienen prioridad sobre las preferencias que se establecen localmente en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="9624b-111">Preferences that are managed by your security operations team take precedence over preferences that are set locally on the device.</span></span> <span data-ttu-id="9624b-112">Cambiar las preferencias que se establecen a través del perfil de configuración requiere privilegios escalados y no está disponible para usuarios sin permisos administrativos.</span><span class="sxs-lookup"><span data-stu-id="9624b-112">Changing the preferences that are set through the configuration profile requires escalated privileges and is not available for users without administrative permissions.</span></span>

<span data-ttu-id="9624b-113">En este artículo se describe la estructura del perfil de configuración, se incluye un perfil recomendado que puede usar para empezar y se proporcionan instrucciones sobre cómo implementar el perfil.</span><span class="sxs-lookup"><span data-stu-id="9624b-113">This article describes the structure of the configuration profile, includes a recommended profile that you can use to get started, and provides instructions on how to deploy the profile.</span></span>

## <a name="configuration-profile-structure"></a><span data-ttu-id="9624b-114">Estructura de perfiles de configuración</span><span class="sxs-lookup"><span data-stu-id="9624b-114">Configuration profile structure</span></span>

<span data-ttu-id="9624b-115">El perfil de configuración es un *archivo .plist* que consta de entradas identificadas por una clave (que indica el nombre de la preferencia), seguido de un valor, que depende de la naturaleza de la preferencia.</span><span class="sxs-lookup"><span data-stu-id="9624b-115">The configuration profile is a *.plist* file that consists of entries identified by a key (which denotes the name of the preference), followed by a value, which depends on the nature of the preference.</span></span> <span data-ttu-id="9624b-116">Los valores pueden ser simples (como un valor numérico) o complejos, como una lista anidada de preferencias.</span><span class="sxs-lookup"><span data-stu-id="9624b-116">Values can either be simple (such as a numerical value) or complex, such as a nested list of preferences.</span></span>

>[!CAUTION]
><span data-ttu-id="9624b-117">El diseño del perfil de configuración depende de la consola de administración que se use.</span><span class="sxs-lookup"><span data-stu-id="9624b-117">The layout of the configuration profile depends on the management console that you are using.</span></span> <span data-ttu-id="9624b-118">Las secciones siguientes contienen ejemplos de perfiles de configuración para JAMF e Intune.</span><span class="sxs-lookup"><span data-stu-id="9624b-118">The following sections contain examples of configuration profiles for JAMF and Intune.</span></span>

<span data-ttu-id="9624b-119">El nivel superior del perfil de configuración incluye las preferencias de todo el producto y las entradas para las subáreas de Microsoft Defender para endpoint, que se explican con más detalle en las secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="9624b-119">The top level of the configuration profile includes product-wide preferences and entries for subareas of Microsoft Defender for Endpoint, which are explained in more detail in the next sections.</span></span>

### <a name="antivirus-engine-preferences"></a><span data-ttu-id="9624b-120">Preferencias del motor antivirus</span><span class="sxs-lookup"><span data-stu-id="9624b-120">Antivirus engine preferences</span></span>

<span data-ttu-id="9624b-121">La *sección antivirusEngine* del perfil de configuración se usa para administrar las preferencias del componente antivirus de Microsoft Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="9624b-121">The *antivirusEngine* section of the configuration profile is used to manage the preferences of the antivirus component of Microsoft Defender for Endpoint.</span></span>

|||
|:---|:---|
| <span data-ttu-id="9624b-122">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="9624b-122">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9624b-123">**Clave**</span><span class="sxs-lookup"><span data-stu-id="9624b-123">**Key**</span></span> | <span data-ttu-id="9624b-124">antivirusEngine</span><span class="sxs-lookup"><span data-stu-id="9624b-124">antivirusEngine</span></span> |
| <span data-ttu-id="9624b-125">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="9624b-125">**Data type**</span></span> | <span data-ttu-id="9624b-126">Diccionario (preferencia anidada)</span><span class="sxs-lookup"><span data-stu-id="9624b-126">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="9624b-127">**Comments**</span><span class="sxs-lookup"><span data-stu-id="9624b-127">**Comments**</span></span> | <span data-ttu-id="9624b-128">Vea las secciones siguientes para obtener una descripción del contenido del diccionario.</span><span class="sxs-lookup"><span data-stu-id="9624b-128">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="enable--disable-real-time-protection"></a><span data-ttu-id="9624b-129">Habilitar o deshabilitar la protección en tiempo real</span><span class="sxs-lookup"><span data-stu-id="9624b-129">Enable / disable real-time protection</span></span>

<span data-ttu-id="9624b-130">Especifique si se va a habilitar la protección en tiempo real, que examina los archivos a medida que se accede a ellos.</span><span class="sxs-lookup"><span data-stu-id="9624b-130">Specify whether to enable real-time protection, which scans files as they are accessed.</span></span>

|||
|:---|:---|
| <span data-ttu-id="9624b-131">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="9624b-131">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9624b-132">**Clave**</span><span class="sxs-lookup"><span data-stu-id="9624b-132">**Key**</span></span> | <span data-ttu-id="9624b-133">enableRealTimeProtection</span><span class="sxs-lookup"><span data-stu-id="9624b-133">enableRealTimeProtection</span></span> |
| <span data-ttu-id="9624b-134">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="9624b-134">**Data type**</span></span> | <span data-ttu-id="9624b-135">Booleano</span><span class="sxs-lookup"><span data-stu-id="9624b-135">Boolean</span></span> |
| <span data-ttu-id="9624b-136">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="9624b-136">**Possible values**</span></span> | <span data-ttu-id="9624b-137">true (valor predeterminado)</span><span class="sxs-lookup"><span data-stu-id="9624b-137">true (default)</span></span> <br/> <span data-ttu-id="9624b-138">false</span><span class="sxs-lookup"><span data-stu-id="9624b-138">false</span></span> |

#### <a name="enable--disable-passive-mode"></a><span data-ttu-id="9624b-139">Habilitar o deshabilitar el modo pasivo</span><span class="sxs-lookup"><span data-stu-id="9624b-139">Enable / disable passive mode</span></span>

<span data-ttu-id="9624b-140">Especifique si el motor antivirus se ejecuta en modo pasivo.</span><span class="sxs-lookup"><span data-stu-id="9624b-140">Specify whether the antivirus engine runs in passive mode.</span></span> <span data-ttu-id="9624b-141">El modo pasivo tiene las siguientes implicaciones:</span><span class="sxs-lookup"><span data-stu-id="9624b-141">Passive mode has the following implications:</span></span> 
- <span data-ttu-id="9624b-142">La protección en tiempo real está desactivada</span><span class="sxs-lookup"><span data-stu-id="9624b-142">Real-time protection is turned off</span></span>
- <span data-ttu-id="9624b-143">El examen a petición está activado</span><span class="sxs-lookup"><span data-stu-id="9624b-143">On-demand scanning is turned on</span></span>
- <span data-ttu-id="9624b-144">La corrección automática de amenazas está desactivada</span><span class="sxs-lookup"><span data-stu-id="9624b-144">Automatic threat remediation is turned off</span></span>
- <span data-ttu-id="9624b-145">Las actualizaciones de inteligencia de seguridad están activadas</span><span class="sxs-lookup"><span data-stu-id="9624b-145">Security intelligence updates are turned on</span></span>
- <span data-ttu-id="9624b-146">El icono del menú Estado está oculto</span><span class="sxs-lookup"><span data-stu-id="9624b-146">Status menu icon is hidden</span></span>

|||
|:---|:---|
| <span data-ttu-id="9624b-147">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="9624b-147">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9624b-148">**Clave**</span><span class="sxs-lookup"><span data-stu-id="9624b-148">**Key**</span></span> | <span data-ttu-id="9624b-149">passiveMode</span><span class="sxs-lookup"><span data-stu-id="9624b-149">passiveMode</span></span> |
| <span data-ttu-id="9624b-150">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="9624b-150">**Data type**</span></span> | <span data-ttu-id="9624b-151">Booleano</span><span class="sxs-lookup"><span data-stu-id="9624b-151">Boolean</span></span> |
| <span data-ttu-id="9624b-152">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="9624b-152">**Possible values**</span></span> | <span data-ttu-id="9624b-153">false (predeterminado)</span><span class="sxs-lookup"><span data-stu-id="9624b-153">false (default)</span></span> <br/> <span data-ttu-id="9624b-154">true</span><span class="sxs-lookup"><span data-stu-id="9624b-154">true</span></span> |
| <span data-ttu-id="9624b-155">**Comments**</span><span class="sxs-lookup"><span data-stu-id="9624b-155">**Comments**</span></span> | <span data-ttu-id="9624b-156">Disponible en Microsoft Defender para endpoint versión 100.67.60 o posterior.</span><span class="sxs-lookup"><span data-stu-id="9624b-156">Available in Microsoft Defender for Endpoint version 100.67.60 or higher.</span></span> |

#### <a name="exclusion-merge-policy"></a><span data-ttu-id="9624b-157">Directiva de combinación de exclusión</span><span class="sxs-lookup"><span data-stu-id="9624b-157">Exclusion merge policy</span></span>

<span data-ttu-id="9624b-158">Especifique la directiva de combinación para exclusiones.</span><span class="sxs-lookup"><span data-stu-id="9624b-158">Specify the merge policy for exclusions.</span></span> <span data-ttu-id="9624b-159">Puede ser una combinación de exclusiones definidas por el administrador y definidas por el usuario ( ) o solo `merge` exclusiones definidas por el administrador ( `admin_only` ).</span><span class="sxs-lookup"><span data-stu-id="9624b-159">This can be a combination of administrator-defined and user-defined exclusions (`merge`) or only administrator-defined exclusions (`admin_only`).</span></span> <span data-ttu-id="9624b-160">Esta configuración se puede usar para restringir que los usuarios locales definan sus propias exclusiones.</span><span class="sxs-lookup"><span data-stu-id="9624b-160">This setting can be used to restrict local users from defining their own exclusions.</span></span>

|||
|:---|:---|
| <span data-ttu-id="9624b-161">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="9624b-161">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9624b-162">**Clave**</span><span class="sxs-lookup"><span data-stu-id="9624b-162">**Key**</span></span> | <span data-ttu-id="9624b-163">exclusionsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="9624b-163">exclusionsMergePolicy</span></span> |
| <span data-ttu-id="9624b-164">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="9624b-164">**Data type**</span></span> | <span data-ttu-id="9624b-165">Cadena</span><span class="sxs-lookup"><span data-stu-id="9624b-165">String</span></span> |
| <span data-ttu-id="9624b-166">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="9624b-166">**Possible values**</span></span> | <span data-ttu-id="9624b-167">merge (valor predeterminado)</span><span class="sxs-lookup"><span data-stu-id="9624b-167">merge (default)</span></span> <br/> <span data-ttu-id="9624b-168">admin_only</span><span class="sxs-lookup"><span data-stu-id="9624b-168">admin_only</span></span> |
| <span data-ttu-id="9624b-169">**Comments**</span><span class="sxs-lookup"><span data-stu-id="9624b-169">**Comments**</span></span> | <span data-ttu-id="9624b-170">Disponible en Microsoft Defender para endpoint versión 100.83.73 o posterior.</span><span class="sxs-lookup"><span data-stu-id="9624b-170">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="scan-exclusions"></a><span data-ttu-id="9624b-171">Exclusiones de examen</span><span class="sxs-lookup"><span data-stu-id="9624b-171">Scan exclusions</span></span>

<span data-ttu-id="9624b-172">Especifique las entidades que no se han analizado.</span><span class="sxs-lookup"><span data-stu-id="9624b-172">Specify entities excluded from being scanned.</span></span> <span data-ttu-id="9624b-173">Las exclusiones se pueden especificar por rutas de acceso completas, extensiones o nombres de archivo.</span><span class="sxs-lookup"><span data-stu-id="9624b-173">Exclusions can be specified by full paths, extensions, or file names.</span></span>

|||
|:---|:---|
| <span data-ttu-id="9624b-174">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="9624b-174">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9624b-175">**Clave**</span><span class="sxs-lookup"><span data-stu-id="9624b-175">**Key**</span></span> | <span data-ttu-id="9624b-176">exclusiones</span><span class="sxs-lookup"><span data-stu-id="9624b-176">exclusions</span></span> |
| <span data-ttu-id="9624b-177">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="9624b-177">**Data type**</span></span> | <span data-ttu-id="9624b-178">Diccionario (preferencia anidada)</span><span class="sxs-lookup"><span data-stu-id="9624b-178">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="9624b-179">**Comments**</span><span class="sxs-lookup"><span data-stu-id="9624b-179">**Comments**</span></span> | <span data-ttu-id="9624b-180">Vea las secciones siguientes para obtener una descripción del contenido del diccionario.</span><span class="sxs-lookup"><span data-stu-id="9624b-180">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="type-of-exclusion"></a><span data-ttu-id="9624b-181">Tipo de exclusión</span><span class="sxs-lookup"><span data-stu-id="9624b-181">Type of exclusion</span></span>

<span data-ttu-id="9624b-182">Especifique el contenido excluido de ser examinado por tipo.</span><span class="sxs-lookup"><span data-stu-id="9624b-182">Specify content excluded from being scanned by type.</span></span>

|||
|:---|:---|
| <span data-ttu-id="9624b-183">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="9624b-183">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9624b-184">**Clave**</span><span class="sxs-lookup"><span data-stu-id="9624b-184">**Key**</span></span> | <span data-ttu-id="9624b-185">$type</span><span class="sxs-lookup"><span data-stu-id="9624b-185">$type</span></span> |
| <span data-ttu-id="9624b-186">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="9624b-186">**Data type**</span></span> | <span data-ttu-id="9624b-187">Cadena</span><span class="sxs-lookup"><span data-stu-id="9624b-187">String</span></span> |
| <span data-ttu-id="9624b-188">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="9624b-188">**Possible values**</span></span> | <span data-ttu-id="9624b-189">excludedPath</span><span class="sxs-lookup"><span data-stu-id="9624b-189">excludedPath</span></span> <br/> <span data-ttu-id="9624b-190">excludedFileExtension</span><span class="sxs-lookup"><span data-stu-id="9624b-190">excludedFileExtension</span></span> <br/> <span data-ttu-id="9624b-191">excludedFileName</span><span class="sxs-lookup"><span data-stu-id="9624b-191">excludedFileName</span></span> |

##### <a name="path-to-excluded-content"></a><span data-ttu-id="9624b-192">Ruta de acceso al contenido excluido</span><span class="sxs-lookup"><span data-stu-id="9624b-192">Path to excluded content</span></span>

<span data-ttu-id="9624b-193">Especifique el contenido excluido de ser examinado por la ruta de acceso de archivo completa.</span><span class="sxs-lookup"><span data-stu-id="9624b-193">Specify content excluded from being scanned by full file path.</span></span>

|||
|:---|:---|
| <span data-ttu-id="9624b-194">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="9624b-194">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9624b-195">**Clave**</span><span class="sxs-lookup"><span data-stu-id="9624b-195">**Key**</span></span> | <span data-ttu-id="9624b-196">path</span><span class="sxs-lookup"><span data-stu-id="9624b-196">path</span></span> |
| <span data-ttu-id="9624b-197">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="9624b-197">**Data type**</span></span> | <span data-ttu-id="9624b-198">Cadena</span><span class="sxs-lookup"><span data-stu-id="9624b-198">String</span></span> |
| <span data-ttu-id="9624b-199">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="9624b-199">**Possible values**</span></span> | <span data-ttu-id="9624b-200">rutas de acceso válidas</span><span class="sxs-lookup"><span data-stu-id="9624b-200">valid paths</span></span> |
| <span data-ttu-id="9624b-201">**Comments**</span><span class="sxs-lookup"><span data-stu-id="9624b-201">**Comments**</span></span> | <span data-ttu-id="9624b-202">Aplicable solo *si $type* *se excluyePath*</span><span class="sxs-lookup"><span data-stu-id="9624b-202">Applicable only if *$type* is *excludedPath*</span></span> |

##### <a name="path-type-file--directory"></a><span data-ttu-id="9624b-203">Tipo de ruta de acceso (archivo/directorio)</span><span class="sxs-lookup"><span data-stu-id="9624b-203">Path type (file / directory)</span></span>

<span data-ttu-id="9624b-204">Indica si la *propiedad path* hace referencia a un archivo o directorio.</span><span class="sxs-lookup"><span data-stu-id="9624b-204">Indicate if the *path* property refers to a file or directory.</span></span> 

|||
|:---|:---|
| <span data-ttu-id="9624b-205">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="9624b-205">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9624b-206">**Clave**</span><span class="sxs-lookup"><span data-stu-id="9624b-206">**Key**</span></span> | <span data-ttu-id="9624b-207">isDirectory</span><span class="sxs-lookup"><span data-stu-id="9624b-207">isDirectory</span></span> |
| <span data-ttu-id="9624b-208">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="9624b-208">**Data type**</span></span> | <span data-ttu-id="9624b-209">Booleano</span><span class="sxs-lookup"><span data-stu-id="9624b-209">Boolean</span></span> |
| <span data-ttu-id="9624b-210">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="9624b-210">**Possible values**</span></span> | <span data-ttu-id="9624b-211">false (predeterminado)</span><span class="sxs-lookup"><span data-stu-id="9624b-211">false (default)</span></span> <br/> <span data-ttu-id="9624b-212">true</span><span class="sxs-lookup"><span data-stu-id="9624b-212">true</span></span> |
| <span data-ttu-id="9624b-213">**Comments**</span><span class="sxs-lookup"><span data-stu-id="9624b-213">**Comments**</span></span> | <span data-ttu-id="9624b-214">Aplicable solo *si $type* *se excluyePath*</span><span class="sxs-lookup"><span data-stu-id="9624b-214">Applicable only if *$type* is *excludedPath*</span></span> |

##### <a name="file-extension-excluded-from-the-scan"></a><span data-ttu-id="9624b-215">Extensión de archivo excluida del examen</span><span class="sxs-lookup"><span data-stu-id="9624b-215">File extension excluded from the scan</span></span>

<span data-ttu-id="9624b-216">Especifique el contenido excluido de la extensión de archivo.</span><span class="sxs-lookup"><span data-stu-id="9624b-216">Specify content excluded from being scanned by file extension.</span></span>

|||
|:---|:---|
| <span data-ttu-id="9624b-217">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="9624b-217">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9624b-218">**Clave**</span><span class="sxs-lookup"><span data-stu-id="9624b-218">**Key**</span></span> | <span data-ttu-id="9624b-219">extensión</span><span class="sxs-lookup"><span data-stu-id="9624b-219">extension</span></span> |
| <span data-ttu-id="9624b-220">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="9624b-220">**Data type**</span></span> | <span data-ttu-id="9624b-221">Cadena</span><span class="sxs-lookup"><span data-stu-id="9624b-221">String</span></span> |
| <span data-ttu-id="9624b-222">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="9624b-222">**Possible values**</span></span> | <span data-ttu-id="9624b-223">extensiones de archivo válidas</span><span class="sxs-lookup"><span data-stu-id="9624b-223">valid file extensions</span></span> |
| <span data-ttu-id="9624b-224">**Comments**</span><span class="sxs-lookup"><span data-stu-id="9624b-224">**Comments**</span></span> | <span data-ttu-id="9624b-225">Aplicable solo *si $type* *se excluyeFileExtension*</span><span class="sxs-lookup"><span data-stu-id="9624b-225">Applicable only if *$type* is *excludedFileExtension*</span></span> |

##### <a name="process-excluded-from-the-scan"></a><span data-ttu-id="9624b-226">Proceso excluido del examen</span><span class="sxs-lookup"><span data-stu-id="9624b-226">Process excluded from the scan</span></span>

<span data-ttu-id="9624b-227">Especifique un proceso para el que se excluya toda la actividad de archivo del examen.</span><span class="sxs-lookup"><span data-stu-id="9624b-227">Specify a process for which all file activity is excluded from scanning.</span></span> <span data-ttu-id="9624b-228">El proceso puede especificarse por su nombre (por ejemplo) o por la ruta de acceso `cat` completa (por ejemplo, `/bin/cat` ).</span><span class="sxs-lookup"><span data-stu-id="9624b-228">The process can be specified either by its name (e.g. `cat`) or full path (e.g. `/bin/cat`).</span></span>

|||
|:---|:---|
| <span data-ttu-id="9624b-229">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="9624b-229">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9624b-230">**Clave**</span><span class="sxs-lookup"><span data-stu-id="9624b-230">**Key**</span></span> | <span data-ttu-id="9624b-231">name</span><span class="sxs-lookup"><span data-stu-id="9624b-231">name</span></span> |
| <span data-ttu-id="9624b-232">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="9624b-232">**Data type**</span></span> | <span data-ttu-id="9624b-233">Cadena</span><span class="sxs-lookup"><span data-stu-id="9624b-233">String</span></span> |
| <span data-ttu-id="9624b-234">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="9624b-234">**Possible values**</span></span> | <span data-ttu-id="9624b-235">cualquier cadena</span><span class="sxs-lookup"><span data-stu-id="9624b-235">any string</span></span> |
| <span data-ttu-id="9624b-236">**Comments**</span><span class="sxs-lookup"><span data-stu-id="9624b-236">**Comments**</span></span> | <span data-ttu-id="9624b-237">Aplicable solo *si $type* *se excluyeFileName*</span><span class="sxs-lookup"><span data-stu-id="9624b-237">Applicable only if *$type* is *excludedFileName*</span></span> |

#### <a name="allowed-threats"></a><span data-ttu-id="9624b-238">Amenazas permitidas</span><span class="sxs-lookup"><span data-stu-id="9624b-238">Allowed threats</span></span>

<span data-ttu-id="9624b-239">Especifica las amenazas por nombre que Defender for Endpoint for Mac no bloquee.</span><span class="sxs-lookup"><span data-stu-id="9624b-239">Specify threats by name that are not blocked by Defender for Endpoint for Mac.</span></span> <span data-ttu-id="9624b-240">Estas amenazas podrán ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="9624b-240">These threats will be allowed to run.</span></span>

|||
|:---|:---|
| <span data-ttu-id="9624b-241">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="9624b-241">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9624b-242">**Clave**</span><span class="sxs-lookup"><span data-stu-id="9624b-242">**Key**</span></span> | <span data-ttu-id="9624b-243">allowedThreats</span><span class="sxs-lookup"><span data-stu-id="9624b-243">allowedThreats</span></span> |
| <span data-ttu-id="9624b-244">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="9624b-244">**Data type**</span></span> | <span data-ttu-id="9624b-245">Matriz de cadenas</span><span class="sxs-lookup"><span data-stu-id="9624b-245">Array of strings</span></span> |

#### <a name="disallowed-threat-actions"></a><span data-ttu-id="9624b-246">Acciones de amenazas no permitidos</span><span class="sxs-lookup"><span data-stu-id="9624b-246">Disallowed threat actions</span></span>

<span data-ttu-id="9624b-247">Restringe las acciones que el usuario local de un dispositivo puede realizar cuando se detectan amenazas.</span><span class="sxs-lookup"><span data-stu-id="9624b-247">Restricts the actions that the local user of a device can take when threats are detected.</span></span> <span data-ttu-id="9624b-248">Las acciones incluidas en esta lista no se muestran en la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="9624b-248">The actions included in this list are not displayed in the user interface.</span></span>

|||
|:---|:---|
| <span data-ttu-id="9624b-249">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="9624b-249">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9624b-250">**Clave**</span><span class="sxs-lookup"><span data-stu-id="9624b-250">**Key**</span></span> | <span data-ttu-id="9624b-251">disallowedThreatActions</span><span class="sxs-lookup"><span data-stu-id="9624b-251">disallowedThreatActions</span></span> |
| <span data-ttu-id="9624b-252">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="9624b-252">**Data type**</span></span> | <span data-ttu-id="9624b-253">Matriz de cadenas</span><span class="sxs-lookup"><span data-stu-id="9624b-253">Array of strings</span></span> |
| <span data-ttu-id="9624b-254">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="9624b-254">**Possible values**</span></span> | <span data-ttu-id="9624b-255">permitir (restringe a los usuarios permitir amenazas)</span><span class="sxs-lookup"><span data-stu-id="9624b-255">allow (restricts users from allowing threats)</span></span> <br/> <span data-ttu-id="9624b-256">restore (restringe a los usuarios la restauración de amenazas desde la cuarentena)</span><span class="sxs-lookup"><span data-stu-id="9624b-256">restore (restricts users from restoring threats from the quarantine)</span></span> |
| <span data-ttu-id="9624b-257">**Comments**</span><span class="sxs-lookup"><span data-stu-id="9624b-257">**Comments**</span></span> | <span data-ttu-id="9624b-258">Disponible en Microsoft Defender para endpoint versión 100.83.73 o posterior.</span><span class="sxs-lookup"><span data-stu-id="9624b-258">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="threat-type-settings"></a><span data-ttu-id="9624b-259">Configuración del tipo de amenaza</span><span class="sxs-lookup"><span data-stu-id="9624b-259">Threat type settings</span></span>

<span data-ttu-id="9624b-260">Especifica cómo controla Microsoft Defender para Endpoint para Mac determinados tipos de amenazas.</span><span class="sxs-lookup"><span data-stu-id="9624b-260">Specify how certain threat types are handled by Microsoft Defender for Endpoint for Mac.</span></span>

|||
|:---|:---|
| <span data-ttu-id="9624b-261">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="9624b-261">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9624b-262">**Clave**</span><span class="sxs-lookup"><span data-stu-id="9624b-262">**Key**</span></span> | <span data-ttu-id="9624b-263">threatTypeSettings</span><span class="sxs-lookup"><span data-stu-id="9624b-263">threatTypeSettings</span></span> |
| <span data-ttu-id="9624b-264">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="9624b-264">**Data type**</span></span> | <span data-ttu-id="9624b-265">Diccionario (preferencia anidada)</span><span class="sxs-lookup"><span data-stu-id="9624b-265">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="9624b-266">**Comments**</span><span class="sxs-lookup"><span data-stu-id="9624b-266">**Comments**</span></span> | <span data-ttu-id="9624b-267">Vea las secciones siguientes para obtener una descripción del contenido del diccionario.</span><span class="sxs-lookup"><span data-stu-id="9624b-267">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="threat-type"></a><span data-ttu-id="9624b-268">Tipo de amenaza</span><span class="sxs-lookup"><span data-stu-id="9624b-268">Threat type</span></span>

<span data-ttu-id="9624b-269">Especifique tipos de amenazas.</span><span class="sxs-lookup"><span data-stu-id="9624b-269">Specify threat types.</span></span>

|||
|:---|:---|
| <span data-ttu-id="9624b-270">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="9624b-270">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9624b-271">**Clave**</span><span class="sxs-lookup"><span data-stu-id="9624b-271">**Key**</span></span> | <span data-ttu-id="9624b-272">clave</span><span class="sxs-lookup"><span data-stu-id="9624b-272">key</span></span> |
| <span data-ttu-id="9624b-273">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="9624b-273">**Data type**</span></span> | <span data-ttu-id="9624b-274">Cadena</span><span class="sxs-lookup"><span data-stu-id="9624b-274">String</span></span> |
| <span data-ttu-id="9624b-275">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="9624b-275">**Possible values**</span></span> | <span data-ttu-id="9624b-276">potentially_unwanted_application</span><span class="sxs-lookup"><span data-stu-id="9624b-276">potentially_unwanted_application</span></span> <br/> <span data-ttu-id="9624b-277">archive_bomb</span><span class="sxs-lookup"><span data-stu-id="9624b-277">archive_bomb</span></span> |

##### <a name="action-to-take"></a><span data-ttu-id="9624b-278">Acción que puede realizar</span><span class="sxs-lookup"><span data-stu-id="9624b-278">Action to take</span></span>

<span data-ttu-id="9624b-279">Especifique qué acción realizar cuando se detecte una amenaza del tipo especificado en la sección anterior.</span><span class="sxs-lookup"><span data-stu-id="9624b-279">Specify what action to take when a threat of the type specified in the preceding section is detected.</span></span> <span data-ttu-id="9624b-280">Seleccione una de las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="9624b-280">Choose from the following options:</span></span>

- <span data-ttu-id="9624b-281">**Auditoría:** el dispositivo no está protegido contra este tipo de amenaza, pero se registra una entrada sobre la amenaza.</span><span class="sxs-lookup"><span data-stu-id="9624b-281">**Audit**: your device is not protected against this type of threat, but an entry about the threat is logged.</span></span>
- <span data-ttu-id="9624b-282">**Bloquear:** el dispositivo está protegido contra este tipo de amenaza y se te notificará en la interfaz de usuario y en la consola de seguridad.</span><span class="sxs-lookup"><span data-stu-id="9624b-282">**Block**: your device is protected against this type of threat and you are notified in the user interface and the security console.</span></span>
- <span data-ttu-id="9624b-283">**Desactivado:** el dispositivo no está protegido contra este tipo de amenaza y no se registra nada.</span><span class="sxs-lookup"><span data-stu-id="9624b-283">**Off**: your device is not protected against this type of threat and nothing is logged.</span></span>

|||
|:---|:---|
| <span data-ttu-id="9624b-284">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="9624b-284">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9624b-285">**Clave**</span><span class="sxs-lookup"><span data-stu-id="9624b-285">**Key**</span></span> | <span data-ttu-id="9624b-286">valor</span><span class="sxs-lookup"><span data-stu-id="9624b-286">value</span></span> |
| <span data-ttu-id="9624b-287">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="9624b-287">**Data type**</span></span> | <span data-ttu-id="9624b-288">Cadena</span><span class="sxs-lookup"><span data-stu-id="9624b-288">String</span></span> |
| <span data-ttu-id="9624b-289">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="9624b-289">**Possible values**</span></span> | <span data-ttu-id="9624b-290">auditoría (valor predeterminado)</span><span class="sxs-lookup"><span data-stu-id="9624b-290">audit (default)</span></span> <br/> <span data-ttu-id="9624b-291">bloque</span><span class="sxs-lookup"><span data-stu-id="9624b-291">block</span></span> <br/> <span data-ttu-id="9624b-292">off</span><span class="sxs-lookup"><span data-stu-id="9624b-292">off</span></span> |

#### <a name="threat-type-settings-merge-policy"></a><span data-ttu-id="9624b-293">Directiva de combinación de configuración de tipo de amenaza</span><span class="sxs-lookup"><span data-stu-id="9624b-293">Threat type settings merge policy</span></span>

<span data-ttu-id="9624b-294">Especifique la directiva de combinación para la configuración del tipo de amenaza.</span><span class="sxs-lookup"><span data-stu-id="9624b-294">Specify the merge policy for threat type settings.</span></span> <span data-ttu-id="9624b-295">Puede ser una combinación de opciones definidas por el administrador y definidas por el usuario ( ) o solo opciones definidas `merge` por el administrador ( `admin_only` ).</span><span class="sxs-lookup"><span data-stu-id="9624b-295">This can be a combination of administrator-defined and user-defined settings (`merge`) or only administrator-defined settings (`admin_only`).</span></span> <span data-ttu-id="9624b-296">Esta configuración se puede usar para restringir que los usuarios locales definan su propia configuración para diferentes tipos de amenazas.</span><span class="sxs-lookup"><span data-stu-id="9624b-296">This setting can be used to restrict local users from defining their own settings for different threat types.</span></span>

|||
|:---|:---|
| <span data-ttu-id="9624b-297">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="9624b-297">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9624b-298">**Clave**</span><span class="sxs-lookup"><span data-stu-id="9624b-298">**Key**</span></span> | <span data-ttu-id="9624b-299">threatTypeSettingsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="9624b-299">threatTypeSettingsMergePolicy</span></span> |
| <span data-ttu-id="9624b-300">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="9624b-300">**Data type**</span></span> | <span data-ttu-id="9624b-301">Cadena</span><span class="sxs-lookup"><span data-stu-id="9624b-301">String</span></span> |
| <span data-ttu-id="9624b-302">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="9624b-302">**Possible values**</span></span> | <span data-ttu-id="9624b-303">merge (valor predeterminado)</span><span class="sxs-lookup"><span data-stu-id="9624b-303">merge (default)</span></span> <br/> <span data-ttu-id="9624b-304">admin_only</span><span class="sxs-lookup"><span data-stu-id="9624b-304">admin_only</span></span> |
| <span data-ttu-id="9624b-305">**Comments**</span><span class="sxs-lookup"><span data-stu-id="9624b-305">**Comments**</span></span> | <span data-ttu-id="9624b-306">Disponible en Microsoft Defender para endpoint versión 100.83.73 o posterior.</span><span class="sxs-lookup"><span data-stu-id="9624b-306">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="antivirus-scan-history-retention-in-days"></a><span data-ttu-id="9624b-307">Retención del historial de examen antivirus (en días)</span><span class="sxs-lookup"><span data-stu-id="9624b-307">Antivirus scan history retention (in days)</span></span>

<span data-ttu-id="9624b-308">Especifica el número de días que los resultados se conservan en el historial de examen del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="9624b-308">Specify the number of days that results are retained in the scan history on the device.</span></span> <span data-ttu-id="9624b-309">Los resultados del examen antiguos se quitan del historial.</span><span class="sxs-lookup"><span data-stu-id="9624b-309">Old scan results are removed from the history.</span></span> <span data-ttu-id="9624b-310">Archivos antiguos en cuarentena que también se quitan del disco.</span><span class="sxs-lookup"><span data-stu-id="9624b-310">Old quarantined files that are also removed from the disk.</span></span>

|||
|:---|:---|
| <span data-ttu-id="9624b-311">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="9624b-311">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9624b-312">**Clave**</span><span class="sxs-lookup"><span data-stu-id="9624b-312">**Key**</span></span> | <span data-ttu-id="9624b-313">scanResultsRetentionDays</span><span class="sxs-lookup"><span data-stu-id="9624b-313">scanResultsRetentionDays</span></span> |
| <span data-ttu-id="9624b-314">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="9624b-314">**Data type**</span></span> | <span data-ttu-id="9624b-315">Cadena</span><span class="sxs-lookup"><span data-stu-id="9624b-315">String</span></span> |
| <span data-ttu-id="9624b-316">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="9624b-316">**Possible values**</span></span> | <span data-ttu-id="9624b-317">90 (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="9624b-317">90 (default).</span></span> <span data-ttu-id="9624b-318">Los valores permitidos van de 1 día a 180 días.</span><span class="sxs-lookup"><span data-stu-id="9624b-318">Allowed values are from 1 day to 180 days.</span></span> |
| <span data-ttu-id="9624b-319">**Comments**</span><span class="sxs-lookup"><span data-stu-id="9624b-319">**Comments**</span></span> | <span data-ttu-id="9624b-320">Disponible en Microsoft Defender para endpoint versión 101.07.23 o posterior.</span><span class="sxs-lookup"><span data-stu-id="9624b-320">Available in Microsoft Defender for Endpoint version 101.07.23 or higher.</span></span> |

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a><span data-ttu-id="9624b-321">Número máximo de elementos en el historial de examen antivirus</span><span class="sxs-lookup"><span data-stu-id="9624b-321">Maximum number of items in the antivirus scan history</span></span>

<span data-ttu-id="9624b-322">Especifique el número máximo de entradas que se deben conservar en el historial de examen.</span><span class="sxs-lookup"><span data-stu-id="9624b-322">Specify the maximum number of entries to keep in the scan history.</span></span> <span data-ttu-id="9624b-323">Las entradas incluyen todos los exámenes a petición realizados en el pasado y todas las detecciones de antivirus.</span><span class="sxs-lookup"><span data-stu-id="9624b-323">Entries include all on-demand scans performed in the past and all antivirus detections.</span></span>

|||
|:---|:---|
| <span data-ttu-id="9624b-324">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="9624b-324">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9624b-325">**Clave**</span><span class="sxs-lookup"><span data-stu-id="9624b-325">**Key**</span></span> | <span data-ttu-id="9624b-326">scanHistoryMaximumItems</span><span class="sxs-lookup"><span data-stu-id="9624b-326">scanHistoryMaximumItems</span></span> |
| <span data-ttu-id="9624b-327">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="9624b-327">**Data type**</span></span> | <span data-ttu-id="9624b-328">Cadena</span><span class="sxs-lookup"><span data-stu-id="9624b-328">String</span></span> |
| <span data-ttu-id="9624b-329">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="9624b-329">**Possible values**</span></span> | <span data-ttu-id="9624b-330">10000 (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="9624b-330">10000 (default).</span></span> <span data-ttu-id="9624b-331">Los valores permitidos van de 5000 elementos a 15000 elementos.</span><span class="sxs-lookup"><span data-stu-id="9624b-331">Allowed values are from 5000 items to 15000 items.</span></span> |
| <span data-ttu-id="9624b-332">**Comments**</span><span class="sxs-lookup"><span data-stu-id="9624b-332">**Comments**</span></span> | <span data-ttu-id="9624b-333">Disponible en Microsoft Defender para endpoint versión 101.07.23 o posterior.</span><span class="sxs-lookup"><span data-stu-id="9624b-333">Available in Microsoft Defender for Endpoint version 101.07.23 or higher.</span></span> |

### <a name="cloud-delivered-protection-preferences"></a><span data-ttu-id="9624b-334">Preferencias de protección entregadas en la nube</span><span class="sxs-lookup"><span data-stu-id="9624b-334">Cloud-delivered protection preferences</span></span>

<span data-ttu-id="9624b-335">Configure las características de protección controlada por la nube de Microsoft Defender para Endpoint para Mac.</span><span class="sxs-lookup"><span data-stu-id="9624b-335">Configure the cloud-driven protection features of Microsoft Defender for Endpoint for Mac.</span></span>

|||
|:---|:---|
| <span data-ttu-id="9624b-336">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="9624b-336">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9624b-337">**Clave**</span><span class="sxs-lookup"><span data-stu-id="9624b-337">**Key**</span></span> | <span data-ttu-id="9624b-338">cloudService</span><span class="sxs-lookup"><span data-stu-id="9624b-338">cloudService</span></span> |
| <span data-ttu-id="9624b-339">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="9624b-339">**Data type**</span></span> | <span data-ttu-id="9624b-340">Diccionario (preferencia anidada)</span><span class="sxs-lookup"><span data-stu-id="9624b-340">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="9624b-341">**Comments**</span><span class="sxs-lookup"><span data-stu-id="9624b-341">**Comments**</span></span> | <span data-ttu-id="9624b-342">Vea las secciones siguientes para obtener una descripción del contenido del diccionario.</span><span class="sxs-lookup"><span data-stu-id="9624b-342">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="enable--disable-cloud-delivered-protection"></a><span data-ttu-id="9624b-343">Habilitar o deshabilitar la protección entregada en la nube</span><span class="sxs-lookup"><span data-stu-id="9624b-343">Enable / disable cloud-delivered protection</span></span>

<span data-ttu-id="9624b-344">Especifica si se va a habilitar la protección entregada en la nube del dispositivo o no.</span><span class="sxs-lookup"><span data-stu-id="9624b-344">Specify whether to enable cloud-delivered protection the device or not.</span></span> <span data-ttu-id="9624b-345">Para mejorar la seguridad de los servicios, se recomienda mantener activada esta característica.</span><span class="sxs-lookup"><span data-stu-id="9624b-345">To improve the security of your services, we recommend keeping this feature turned on.</span></span>

|||
|:---|:---|
| <span data-ttu-id="9624b-346">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="9624b-346">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9624b-347">**Clave**</span><span class="sxs-lookup"><span data-stu-id="9624b-347">**Key**</span></span> | <span data-ttu-id="9624b-348">habilitado</span><span class="sxs-lookup"><span data-stu-id="9624b-348">enabled</span></span> |
| <span data-ttu-id="9624b-349">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="9624b-349">**Data type**</span></span> | <span data-ttu-id="9624b-350">Booleano</span><span class="sxs-lookup"><span data-stu-id="9624b-350">Boolean</span></span> |
| <span data-ttu-id="9624b-351">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="9624b-351">**Possible values**</span></span> | <span data-ttu-id="9624b-352">true (valor predeterminado)</span><span class="sxs-lookup"><span data-stu-id="9624b-352">true (default)</span></span> <br/> <span data-ttu-id="9624b-353">false</span><span class="sxs-lookup"><span data-stu-id="9624b-353">false</span></span> |

#### <a name="diagnostic-collection-level"></a><span data-ttu-id="9624b-354">Nivel de colección de diagnóstico</span><span class="sxs-lookup"><span data-stu-id="9624b-354">Diagnostic collection level</span></span>

<span data-ttu-id="9624b-355">Los datos de diagnóstico se usan para mantener Microsoft Defender for Endpoint seguro y actualizado, detectar, diagnosticar y corregir problemas y también realizar mejoras en el producto.</span><span class="sxs-lookup"><span data-stu-id="9624b-355">Diagnostic data is used to keep Microsoft Defender for Endpoint secure and up-to-date, detect, diagnose and fix problems, and also make product improvements.</span></span> <span data-ttu-id="9624b-356">Esta configuración determina el nivel de diagnóstico enviado por Microsoft Defender para Endpoint a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9624b-356">This setting determines the level of diagnostics sent by Microsoft Defender for Endpoint to Microsoft.</span></span>

|||
|:---|:---|
| <span data-ttu-id="9624b-357">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="9624b-357">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9624b-358">**Clave**</span><span class="sxs-lookup"><span data-stu-id="9624b-358">**Key**</span></span> | <span data-ttu-id="9624b-359">diagnosticLevel</span><span class="sxs-lookup"><span data-stu-id="9624b-359">diagnosticLevel</span></span> |
| <span data-ttu-id="9624b-360">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="9624b-360">**Data type**</span></span> | <span data-ttu-id="9624b-361">Cadena</span><span class="sxs-lookup"><span data-stu-id="9624b-361">String</span></span> |
| <span data-ttu-id="9624b-362">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="9624b-362">**Possible values**</span></span> | <span data-ttu-id="9624b-363">opcional (predeterminado)</span><span class="sxs-lookup"><span data-stu-id="9624b-363">optional (default)</span></span> <br/> <span data-ttu-id="9624b-364">necesario</span><span class="sxs-lookup"><span data-stu-id="9624b-364">required</span></span> |

#### <a name="enable--disable-automatic-sample-submissions"></a><span data-ttu-id="9624b-365">Habilitar o deshabilitar envíos de ejemplo automáticos</span><span class="sxs-lookup"><span data-stu-id="9624b-365">Enable / disable automatic sample submissions</span></span>

<span data-ttu-id="9624b-366">Determina si se envían muestras sospechosas (que probablemente contengan amenazas) a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9624b-366">Determines whether suspicious samples (that are likely to contain threats) are sent to Microsoft.</span></span> <span data-ttu-id="9624b-367">Se le preguntará si es probable que el archivo enviado contenga información personal.</span><span class="sxs-lookup"><span data-stu-id="9624b-367">You are prompted if the submitted file is likely to contain personal information.</span></span>

|||
|:---|:---|
| <span data-ttu-id="9624b-368">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="9624b-368">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9624b-369">**Clave**</span><span class="sxs-lookup"><span data-stu-id="9624b-369">**Key**</span></span> | <span data-ttu-id="9624b-370">automaticSampleSubmission</span><span class="sxs-lookup"><span data-stu-id="9624b-370">automaticSampleSubmission</span></span> |
| <span data-ttu-id="9624b-371">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="9624b-371">**Data type**</span></span> | <span data-ttu-id="9624b-372">Booleano</span><span class="sxs-lookup"><span data-stu-id="9624b-372">Boolean</span></span> |
| <span data-ttu-id="9624b-373">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="9624b-373">**Possible values**</span></span> | <span data-ttu-id="9624b-374">true (valor predeterminado)</span><span class="sxs-lookup"><span data-stu-id="9624b-374">true (default)</span></span> <br/> <span data-ttu-id="9624b-375">false</span><span class="sxs-lookup"><span data-stu-id="9624b-375">false</span></span> |

#### <a name="enable--disable-automatic-security-intelligence-updates"></a><span data-ttu-id="9624b-376">Habilitar o deshabilitar actualizaciones automáticas de inteligencia de seguridad</span><span class="sxs-lookup"><span data-stu-id="9624b-376">Enable / disable automatic security intelligence updates</span></span>

<span data-ttu-id="9624b-377">Determina si las actualizaciones de inteligencia de seguridad se instalan automáticamente:</span><span class="sxs-lookup"><span data-stu-id="9624b-377">Determines whether security intelligence updates are installed automatically:</span></span>

|||
|:---|:---|
| <span data-ttu-id="9624b-378">**Clave**</span><span class="sxs-lookup"><span data-stu-id="9624b-378">**Key**</span></span> | <span data-ttu-id="9624b-379">automaticDefinitionUpdateEnabled</span><span class="sxs-lookup"><span data-stu-id="9624b-379">automaticDefinitionUpdateEnabled</span></span> |
| <span data-ttu-id="9624b-380">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="9624b-380">**Data type**</span></span> | <span data-ttu-id="9624b-381">Booleano</span><span class="sxs-lookup"><span data-stu-id="9624b-381">Boolean</span></span> |
| <span data-ttu-id="9624b-382">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="9624b-382">**Possible values**</span></span> | <span data-ttu-id="9624b-383">true (valor predeterminado)</span><span class="sxs-lookup"><span data-stu-id="9624b-383">true (default)</span></span> <br/> <span data-ttu-id="9624b-384">false</span><span class="sxs-lookup"><span data-stu-id="9624b-384">false</span></span> |

### <a name="user-interface-preferences"></a><span data-ttu-id="9624b-385">Preferencias de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="9624b-385">User interface preferences</span></span>

<span data-ttu-id="9624b-386">Administrar las preferencias de la interfaz de usuario de Microsoft Defender para Endpoint para Mac.</span><span class="sxs-lookup"><span data-stu-id="9624b-386">Manage the preferences for the user interface of Microsoft Defender for Endpoint for Mac.</span></span>

|||
|:---|:---|
| <span data-ttu-id="9624b-387">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="9624b-387">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9624b-388">**Clave**</span><span class="sxs-lookup"><span data-stu-id="9624b-388">**Key**</span></span> | <span data-ttu-id="9624b-389">userInterface</span><span class="sxs-lookup"><span data-stu-id="9624b-389">userInterface</span></span> |
| <span data-ttu-id="9624b-390">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="9624b-390">**Data type**</span></span> | <span data-ttu-id="9624b-391">Diccionario (preferencia anidada)</span><span class="sxs-lookup"><span data-stu-id="9624b-391">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="9624b-392">**Comments**</span><span class="sxs-lookup"><span data-stu-id="9624b-392">**Comments**</span></span> | <span data-ttu-id="9624b-393">Vea las secciones siguientes para obtener una descripción del contenido del diccionario.</span><span class="sxs-lookup"><span data-stu-id="9624b-393">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="show--hide-status-menu-icon"></a><span data-ttu-id="9624b-394">Mostrar u ocultar icono de menú de estado</span><span class="sxs-lookup"><span data-stu-id="9624b-394">Show / hide status menu icon</span></span>

<span data-ttu-id="9624b-395">Especifique si desea mostrar u ocultar el icono del menú de estado en la esquina superior derecha de la pantalla.</span><span class="sxs-lookup"><span data-stu-id="9624b-395">Specify whether to show or hide the status menu icon in the top-right corner of the screen.</span></span>

|||
|:---|:---|
| <span data-ttu-id="9624b-396">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="9624b-396">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9624b-397">**Clave**</span><span class="sxs-lookup"><span data-stu-id="9624b-397">**Key**</span></span> | <span data-ttu-id="9624b-398">hideStatusMenuIcon</span><span class="sxs-lookup"><span data-stu-id="9624b-398">hideStatusMenuIcon</span></span> |
| <span data-ttu-id="9624b-399">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="9624b-399">**Data type**</span></span> | <span data-ttu-id="9624b-400">Booleano</span><span class="sxs-lookup"><span data-stu-id="9624b-400">Boolean</span></span> |
| <span data-ttu-id="9624b-401">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="9624b-401">**Possible values**</span></span> | <span data-ttu-id="9624b-402">false (predeterminado)</span><span class="sxs-lookup"><span data-stu-id="9624b-402">false (default)</span></span> <br/> <span data-ttu-id="9624b-403">true</span><span class="sxs-lookup"><span data-stu-id="9624b-403">true</span></span> |

#### <a name="show--hide-option-to-send-feedback"></a><span data-ttu-id="9624b-404">Mostrar u ocultar opción para enviar comentarios</span><span class="sxs-lookup"><span data-stu-id="9624b-404">Show / hide option to send feedback</span></span>

<span data-ttu-id="9624b-405">Especifica si los usuarios pueden enviar comentarios a Microsoft yendo a `Help`  >  `Send Feedback` .</span><span class="sxs-lookup"><span data-stu-id="9624b-405">Specify whether users can submit feedback to Microsoft by going to `Help` > `Send Feedback`.</span></span>

|||
|:---|:---|
| <span data-ttu-id="9624b-406">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="9624b-406">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9624b-407">**Clave**</span><span class="sxs-lookup"><span data-stu-id="9624b-407">**Key**</span></span> | <span data-ttu-id="9624b-408">userInitiatedFeedback</span><span class="sxs-lookup"><span data-stu-id="9624b-408">userInitiatedFeedback</span></span> |
| <span data-ttu-id="9624b-409">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="9624b-409">**Data type**</span></span> | <span data-ttu-id="9624b-410">Cadena</span><span class="sxs-lookup"><span data-stu-id="9624b-410">String</span></span> |
| <span data-ttu-id="9624b-411">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="9624b-411">**Possible values**</span></span> | <span data-ttu-id="9624b-412">habilitado (predeterminado)</span><span class="sxs-lookup"><span data-stu-id="9624b-412">enabled (default)</span></span> <br/> <span data-ttu-id="9624b-413">deshabilitado</span><span class="sxs-lookup"><span data-stu-id="9624b-413">disabled</span></span> |
| <span data-ttu-id="9624b-414">**Comments**</span><span class="sxs-lookup"><span data-stu-id="9624b-414">**Comments**</span></span> | <span data-ttu-id="9624b-415">Disponible en Microsoft Defender para endpoint versión 101.19.61 o posterior.</span><span class="sxs-lookup"><span data-stu-id="9624b-415">Available in Microsoft Defender for Endpoint version 101.19.61 or higher.</span></span> |

### <a name="endpoint-detection-and-response-preferences"></a><span data-ttu-id="9624b-416">Preferencias de detección y respuesta de extremos</span><span class="sxs-lookup"><span data-stu-id="9624b-416">Endpoint detection and response preferences</span></span>

<span data-ttu-id="9624b-417">Administrar las preferencias del componente de detección y respuesta de puntos de conexión (EDR) de Microsoft Defender para Endpoint para Mac.</span><span class="sxs-lookup"><span data-stu-id="9624b-417">Manage the preferences of the endpoint detection and response (EDR) component of Microsoft Defender for Endpoint for Mac.</span></span>

|||
|:---|:---|
| <span data-ttu-id="9624b-418">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="9624b-418">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9624b-419">**Clave**</span><span class="sxs-lookup"><span data-stu-id="9624b-419">**Key**</span></span> | <span data-ttu-id="9624b-420">edr</span><span class="sxs-lookup"><span data-stu-id="9624b-420">edr</span></span> |
| <span data-ttu-id="9624b-421">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="9624b-421">**Data type**</span></span> | <span data-ttu-id="9624b-422">Diccionario (preferencia anidada)</span><span class="sxs-lookup"><span data-stu-id="9624b-422">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="9624b-423">**Comments**</span><span class="sxs-lookup"><span data-stu-id="9624b-423">**Comments**</span></span> | <span data-ttu-id="9624b-424">Vea las secciones siguientes para obtener una descripción del contenido del diccionario.</span><span class="sxs-lookup"><span data-stu-id="9624b-424">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="device-tags"></a><span data-ttu-id="9624b-425">Etiquetas de dispositivo</span><span class="sxs-lookup"><span data-stu-id="9624b-425">Device tags</span></span>

<span data-ttu-id="9624b-426">Especifique un nombre de etiqueta y su valor.</span><span class="sxs-lookup"><span data-stu-id="9624b-426">Specify a tag name and its value.</span></span> 

- <span data-ttu-id="9624b-427">La etiqueta GROUP, etiqueta el dispositivo con el valor especificado.</span><span class="sxs-lookup"><span data-stu-id="9624b-427">The GROUP tag, tags the device with the specified value.</span></span> <span data-ttu-id="9624b-428">La etiqueta se refleja en el portal en la página del dispositivo y se puede usar para filtrar y agrupar dispositivos.</span><span class="sxs-lookup"><span data-stu-id="9624b-428">The tag is reflected in the portal under the device page and can be used for filtering and grouping devices.</span></span>

|||
|:---|:---|
| <span data-ttu-id="9624b-429">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="9624b-429">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9624b-430">**Clave**</span><span class="sxs-lookup"><span data-stu-id="9624b-430">**Key**</span></span> | <span data-ttu-id="9624b-431">tags</span><span class="sxs-lookup"><span data-stu-id="9624b-431">tags</span></span> |
| <span data-ttu-id="9624b-432">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="9624b-432">**Data type**</span></span> | <span data-ttu-id="9624b-433">Diccionario (preferencia anidada)</span><span class="sxs-lookup"><span data-stu-id="9624b-433">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="9624b-434">**Comments**</span><span class="sxs-lookup"><span data-stu-id="9624b-434">**Comments**</span></span> | <span data-ttu-id="9624b-435">Vea las secciones siguientes para obtener una descripción del contenido del diccionario.</span><span class="sxs-lookup"><span data-stu-id="9624b-435">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="type-of-tag"></a><span data-ttu-id="9624b-436">Tipo de etiqueta</span><span class="sxs-lookup"><span data-stu-id="9624b-436">Type of tag</span></span>

<span data-ttu-id="9624b-437">Especifica el tipo de etiqueta</span><span class="sxs-lookup"><span data-stu-id="9624b-437">Specifies the type of tag</span></span>

|||
|:---|:---|
| <span data-ttu-id="9624b-438">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="9624b-438">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9624b-439">**Clave**</span><span class="sxs-lookup"><span data-stu-id="9624b-439">**Key**</span></span> | <span data-ttu-id="9624b-440">clave</span><span class="sxs-lookup"><span data-stu-id="9624b-440">key</span></span> |
| <span data-ttu-id="9624b-441">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="9624b-441">**Data type**</span></span> | <span data-ttu-id="9624b-442">Cadena</span><span class="sxs-lookup"><span data-stu-id="9624b-442">String</span></span> |
| <span data-ttu-id="9624b-443">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="9624b-443">**Possible values**</span></span> | `GROUP` |

##### <a name="value-of-tag"></a><span data-ttu-id="9624b-444">Valor de etiqueta</span><span class="sxs-lookup"><span data-stu-id="9624b-444">Value of tag</span></span>

<span data-ttu-id="9624b-445">Especifica el valor de la etiqueta</span><span class="sxs-lookup"><span data-stu-id="9624b-445">Specifies the value of tag</span></span>

|||
|:---|:---|
| <span data-ttu-id="9624b-446">**Dominio**</span><span class="sxs-lookup"><span data-stu-id="9624b-446">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9624b-447">**Clave**</span><span class="sxs-lookup"><span data-stu-id="9624b-447">**Key**</span></span> | <span data-ttu-id="9624b-448">valor</span><span class="sxs-lookup"><span data-stu-id="9624b-448">value</span></span> |
| <span data-ttu-id="9624b-449">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="9624b-449">**Data type**</span></span> | <span data-ttu-id="9624b-450">Cadena</span><span class="sxs-lookup"><span data-stu-id="9624b-450">String</span></span> |
| <span data-ttu-id="9624b-451">**Posibles valores**</span><span class="sxs-lookup"><span data-stu-id="9624b-451">**Possible values**</span></span> | <span data-ttu-id="9624b-452">cualquier cadena</span><span class="sxs-lookup"><span data-stu-id="9624b-452">any string</span></span> |

> [!IMPORTANT]  
> - <span data-ttu-id="9624b-453">Solo se puede establecer un valor por tipo de etiqueta.</span><span class="sxs-lookup"><span data-stu-id="9624b-453">Only one value per tag type can be set.</span></span>
> - <span data-ttu-id="9624b-454">El tipo de etiquetas es único y no debe repetirse en el mismo perfil de configuración.</span><span class="sxs-lookup"><span data-stu-id="9624b-454">Type of tags are unique, and should not be repeated in the same configuration profile.</span></span>

## <a name="recommended-configuration-profile"></a><span data-ttu-id="9624b-455">Perfil de configuración recomendado</span><span class="sxs-lookup"><span data-stu-id="9624b-455">Recommended configuration profile</span></span>

<span data-ttu-id="9624b-456">Para empezar, se recomienda la siguiente configuración para que la empresa aproveche todas las características de protección que proporciona Microsoft Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="9624b-456">To get started, we recommend the following configuration for your enterprise to take advantage of all protection features that Microsoft Defender for Endpoint provides.</span></span>

<span data-ttu-id="9624b-457">El siguiente perfil de configuración (o, en el caso de JAMF, una lista de propiedades que podría cargarse en el perfil de configuración de configuración personalizada) será:</span><span class="sxs-lookup"><span data-stu-id="9624b-457">The following configuration profile (or, in case of JAMF, a property list that could be uploaded into the custom settings configuration profile) will:</span></span>
- <span data-ttu-id="9624b-458">Habilitar la protección en tiempo real (RTP)</span><span class="sxs-lookup"><span data-stu-id="9624b-458">Enable real-time protection (RTP)</span></span>
- <span data-ttu-id="9624b-459">Especifique cómo se controlan los siguientes tipos de amenazas:</span><span class="sxs-lookup"><span data-stu-id="9624b-459">Specify how the following threat types are handled:</span></span>
  - <span data-ttu-id="9624b-460">**Las aplicaciones potencialmente no deseadas (PUA)** están bloqueadas</span><span class="sxs-lookup"><span data-stu-id="9624b-460">**Potentially unwanted applications (PUA)** are blocked</span></span>
  - <span data-ttu-id="9624b-461">**Las bombas de archivo** (archivo con una tasa de compresión alta) se auditan en Microsoft Defender para los registros de punto de conexión</span><span class="sxs-lookup"><span data-stu-id="9624b-461">**Archive bombs** (file with a high compression rate) are audited to Microsoft Defender for Endpoint logs</span></span>
- <span data-ttu-id="9624b-462">Habilitar actualizaciones automáticas de inteligencia de seguridad</span><span class="sxs-lookup"><span data-stu-id="9624b-462">Enable automatic security intelligence updates</span></span>
- <span data-ttu-id="9624b-463">Habilitar la protección de entrega en la nube</span><span class="sxs-lookup"><span data-stu-id="9624b-463">Enable cloud-delivered protection</span></span>
- <span data-ttu-id="9624b-464">Habilitar el envío automático de muestra</span><span class="sxs-lookup"><span data-stu-id="9624b-464">Enable automatic sample submission</span></span>

### <a name="property-list-for-jamf-configuration-profile"></a><span data-ttu-id="9624b-465">Lista de propiedades para el perfil de configuración de JAMF</span><span class="sxs-lookup"><span data-stu-id="9624b-465">Property list for JAMF configuration profile</span></span>

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

### <a name="intune-profile"></a><span data-ttu-id="9624b-466">Perfil de Intune</span><span class="sxs-lookup"><span data-stu-id="9624b-466">Intune profile</span></span>

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

## <a name="full-configuration-profile-example"></a><span data-ttu-id="9624b-467">Ejemplo de perfil de configuración completa</span><span class="sxs-lookup"><span data-stu-id="9624b-467">Full configuration profile example</span></span>

<span data-ttu-id="9624b-468">Las siguientes plantillas contienen entradas para todas las configuraciones descritas en este documento y se pueden usar para escenarios más avanzados en los que quieras tener más control sobre Microsoft Defender para Endpoint para Mac.</span><span class="sxs-lookup"><span data-stu-id="9624b-468">The following templates contain entries for all settings described in this document and can be used for more advanced scenarios where you want more control over Microsoft Defender for Endpoint for Mac.</span></span>

### <a name="property-list-for-jamf-configuration-profile"></a><span data-ttu-id="9624b-469">Lista de propiedades para el perfil de configuración de JAMF</span><span class="sxs-lookup"><span data-stu-id="9624b-469">Property list for JAMF configuration profile</span></span>

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

### <a name="intune-profile"></a><span data-ttu-id="9624b-470">Perfil de Intune</span><span class="sxs-lookup"><span data-stu-id="9624b-470">Intune profile</span></span>

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

## <a name="property-list-validation"></a><span data-ttu-id="9624b-471">Validación de lista de propiedades</span><span class="sxs-lookup"><span data-stu-id="9624b-471">Property list validation</span></span>

<span data-ttu-id="9624b-472">La lista de propiedades debe ser un archivo *.plist* válido.</span><span class="sxs-lookup"><span data-stu-id="9624b-472">The property list must be a valid *.plist* file.</span></span> <span data-ttu-id="9624b-473">Esto se puede comprobar ejecutando:</span><span class="sxs-lookup"><span data-stu-id="9624b-473">This can be checked by executing:</span></span>

```bash
plutil -lint com.microsoft.wdav.plist
```
```Output
com.microsoft.wdav.plist: OK
```

<span data-ttu-id="9624b-474">Si el archivo está bien formado, el comando anterior genera `OK` y devuelve un código de salida de `0` .</span><span class="sxs-lookup"><span data-stu-id="9624b-474">If the file is well-formed, the above command outputs `OK` and returns an exit code of `0`.</span></span> <span data-ttu-id="9624b-475">De lo contrario, se muestra un error que describe el problema y el comando devuelve un código de salida de `1` .</span><span class="sxs-lookup"><span data-stu-id="9624b-475">Otherwise, an error that describes the issue is displayed and the command returns an exit code of `1`.</span></span>

## <a name="configuration-profile-deployment"></a><span data-ttu-id="9624b-476">Implementación de perfiles de configuración</span><span class="sxs-lookup"><span data-stu-id="9624b-476">Configuration profile deployment</span></span>

<span data-ttu-id="9624b-477">Una vez que haya creado el perfil de configuración para su empresa, puede implementarlo a través de la consola de administración que usa su empresa.</span><span class="sxs-lookup"><span data-stu-id="9624b-477">Once you've built the configuration profile for your enterprise, you can deploy it through the management console that your enterprise is using.</span></span> <span data-ttu-id="9624b-478">En las secciones siguientes se proporcionan instrucciones sobre cómo implementar este perfil con JAMF e Intune.</span><span class="sxs-lookup"><span data-stu-id="9624b-478">The following sections provide instructions on how to deploy this profile using JAMF and Intune.</span></span>

### <a name="jamf-deployment"></a><span data-ttu-id="9624b-479">Implementación de JAMF</span><span class="sxs-lookup"><span data-stu-id="9624b-479">JAMF deployment</span></span>

<span data-ttu-id="9624b-480">En la consola JAMF, abra **Perfiles** de configuración de equipos, vaya al perfil de configuración que desea usar y, a  >  continuación, seleccione **Configuración personalizada**.</span><span class="sxs-lookup"><span data-stu-id="9624b-480">From the JAMF console, open **Computers** > **Configuration Profiles**, navigate to the configuration profile you'd like to use, then select **Custom Settings**.</span></span> <span data-ttu-id="9624b-481">Cree una entrada con `com.microsoft.wdav` como dominio de preferencia y cargue el *.plist* generado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="9624b-481">Create an entry with `com.microsoft.wdav` as the preference domain and upload the *.plist* produced earlier.</span></span>

>[!CAUTION]
><span data-ttu-id="9624b-482">Debes escribir el dominio de preferencia correcto ( ); de lo contrario, Microsoft Defender no reconocerá las `com.microsoft.wdav` preferencias para endpoint.</span><span class="sxs-lookup"><span data-stu-id="9624b-482">You must enter the correct preference domain (`com.microsoft.wdav`); otherwise, the preferences will not be recognized by Microsoft Defender for Endpoint.</span></span>

### <a name="intune-deployment"></a><span data-ttu-id="9624b-483">Implementación de Intune</span><span class="sxs-lookup"><span data-stu-id="9624b-483">Intune deployment</span></span>

1. <span data-ttu-id="9624b-484">Abra **Administrar configuración** de  >  **dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="9624b-484">Open **Manage** > **Device configuration**.</span></span> <span data-ttu-id="9624b-485">Seleccione **Administrar**  >  **perfiles Crear**  >  **perfil**.</span><span class="sxs-lookup"><span data-stu-id="9624b-485">Select **Manage** > **Profiles** > **Create Profile**.</span></span>

2. <span data-ttu-id="9624b-486">Elija un nombre para el perfil.</span><span class="sxs-lookup"><span data-stu-id="9624b-486">Choose a name for the profile.</span></span> <span data-ttu-id="9624b-487">Cambiar **Platform=macOS** a **Profile type=Custom**.</span><span class="sxs-lookup"><span data-stu-id="9624b-487">Change **Platform=macOS** to **Profile type=Custom**.</span></span> <span data-ttu-id="9624b-488">Seleccione Configurar.</span><span class="sxs-lookup"><span data-stu-id="9624b-488">Select Configure.</span></span>

3. <span data-ttu-id="9624b-489">Guarde el .plist generado anteriormente como `com.microsoft.wdav.xml` .</span><span class="sxs-lookup"><span data-stu-id="9624b-489">Save the .plist produced earlier as `com.microsoft.wdav.xml`.</span></span>

4. <span data-ttu-id="9624b-490">Escriba `com.microsoft.wdav` como el nombre del perfil de configuración **personalizado**.</span><span class="sxs-lookup"><span data-stu-id="9624b-490">Enter `com.microsoft.wdav` as the **custom configuration profile name**.</span></span>

5. <span data-ttu-id="9624b-491">Abra el perfil de configuración y cargue el `com.microsoft.wdav.xml` archivo.</span><span class="sxs-lookup"><span data-stu-id="9624b-491">Open the configuration profile and upload the `com.microsoft.wdav.xml` file.</span></span> <span data-ttu-id="9624b-492">(Este archivo se creó en el paso 3).</span><span class="sxs-lookup"><span data-stu-id="9624b-492">(This file was created in step 3.)</span></span>

6. <span data-ttu-id="9624b-493">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9624b-493">Select **OK**.</span></span>

7. <span data-ttu-id="9624b-494">Seleccione **Administrar**  >  **asignaciones**.</span><span class="sxs-lookup"><span data-stu-id="9624b-494">Select **Manage** > **Assignments**.</span></span> <span data-ttu-id="9624b-495">En la **pestaña Incluir,** seleccione **Asignar a todos los usuarios & Todos los dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="9624b-495">In the **Include** tab, select **Assign to All Users & All devices**.</span></span>

>[!CAUTION]
><span data-ttu-id="9624b-496">Debe escribir el nombre del perfil de configuración personalizado correcto; de lo contrario, Microsoft Defender no reconocerá estas preferencias para endpoint.</span><span class="sxs-lookup"><span data-stu-id="9624b-496">You must enter the correct custom configuration profile name; otherwise, these preferences will not be recognized by Microsoft Defender for Endpoint.</span></span>

## <a name="resources"></a><span data-ttu-id="9624b-497">Recursos</span><span class="sxs-lookup"><span data-stu-id="9624b-497">Resources</span></span>

- [<span data-ttu-id="9624b-498">Referencia de los perfiles de configuración (documentación para desarrolladores de Apple)</span><span class="sxs-lookup"><span data-stu-id="9624b-498">Configuration Profile Reference (Apple developer documentation)</span></span>](https://developer.apple.com/business/documentation/Configuration-Profile-Reference.pdf)
