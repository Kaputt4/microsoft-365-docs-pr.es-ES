---
title: Novedades de Microsoft Defender para Endpoint para Mac
description: Obtenga información sobre los cambios principales de versiones anteriores de Microsoft Defender para Endpoint para Mac.
keywords: microsoft, defender, atp, mac, installation, macos, whatsnew
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: security
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
ms.openlocfilehash: be906baca3a54183e22fa3b4ee424a9d8fc6957a
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2021
ms.locfileid: "51198698"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="06c8a-104">Novedades de Microsoft Defender para Endpoint para Mac</span><span class="sxs-lookup"><span data-stu-id="06c8a-104">What's new in Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="06c8a-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="06c8a-105">**Applies to:**</span></span>
- [<span data-ttu-id="06c8a-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="06c8a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="06c8a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="06c8a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="06c8a-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="06c8a-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="06c8a-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="06c8a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

> [!IMPORTANT]
> <span data-ttu-id="06c8a-110">En macOS 11 (Big Sur), Microsoft Defender para Endpoint requiere perfiles de configuración adicionales.</span><span class="sxs-lookup"><span data-stu-id="06c8a-110">On macOS 11 (Big Sur), Microsoft Defender for Endpoint requires additional configuration profiles.</span></span> <span data-ttu-id="06c8a-111">Si es un cliente existente que actualiza desde versiones anteriores de macOS, asegúrese de implementar los perfiles de configuración adicionales enumerados en [esta página](mac-sysext-policies.md).</span><span class="sxs-lookup"><span data-stu-id="06c8a-111">If you are an existing customer upgrading from earlier versions of macOS, make sure to deploy the additional configuration profiles listed on [this page](mac-sysext-policies.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="06c8a-112">La compatibilidad con macOS 10.13 (High Sierra) se interrumpirá el 15 de febrero de 2021.</span><span class="sxs-lookup"><span data-stu-id="06c8a-112">Support for macOS 10.13 (High Sierra) will be discontinued on February 15th, 2021.</span></span>

## <a name="1012279-20121012122790"></a><span data-ttu-id="06c8a-113">101.22.79 (20.121012.12279.0)</span><span class="sxs-lookup"><span data-stu-id="06c8a-113">101.22.79 (20.121012.12279.0)</span></span>

- <span data-ttu-id="06c8a-114">Mejoras de rendimiento & correcciones de errores</span><span class="sxs-lookup"><span data-stu-id="06c8a-114">Performance improvements & bug fixes</span></span>

## <a name="1011988-20121011119880"></a><span data-ttu-id="06c8a-115">101.19.88 (20.121011.11988.0)</span><span class="sxs-lookup"><span data-stu-id="06c8a-115">101.19.88 (20.121011.11988.0)</span></span>

- <span data-ttu-id="06c8a-116">Mejoras de rendimiento & correcciones de errores</span><span class="sxs-lookup"><span data-stu-id="06c8a-116">Performance improvements & bug fixes</span></span>

## <a name="1011948-20120121119480"></a><span data-ttu-id="06c8a-117">101.19.48 (20.120121.11948.0)</span><span class="sxs-lookup"><span data-stu-id="06c8a-117">101.19.48 (20.120121.11948.0)</span></span>

> [!NOTE]
> <span data-ttu-id="06c8a-118">La sintaxis de la herramienta de línea de comandos antigua ha quedado en desuso con esta versión.</span><span class="sxs-lookup"><span data-stu-id="06c8a-118">The old command-line tool syntax has been deprecated with this release.</span></span> <span data-ttu-id="06c8a-119">Para obtener información sobre la nueva sintaxis, vea [Resources](mac-resources.md#configuring-from-the-command-line).</span><span class="sxs-lookup"><span data-stu-id="06c8a-119">For information on the new syntax, see [Resources](mac-resources.md#configuring-from-the-command-line).</span></span>

- <span data-ttu-id="06c8a-120">Se agregó un nuevo modificador de línea de comandos para deshabilitar la extensión de red: `mdatp system-extension network-filter disable` .</span><span class="sxs-lookup"><span data-stu-id="06c8a-120">Added a new command-line switch to disable the network extension: `mdatp system-extension network-filter disable`.</span></span> <span data-ttu-id="06c8a-121">Este comando puede ser útil para solucionar problemas de red que podrían estar relacionados con Microsoft Defender para Endpoint para Mac</span><span class="sxs-lookup"><span data-stu-id="06c8a-121">This command can be useful to troubleshoot networking issues that could be related to Microsoft Defender for Endpoint for Mac</span></span>
- <span data-ttu-id="06c8a-122">Mejoras de rendimiento & correcciones de errores</span><span class="sxs-lookup"><span data-stu-id="06c8a-122">Performance improvements & bug fixes</span></span>

## <a name="1011921-20120101119210"></a><span data-ttu-id="06c8a-123">101.19.21 (20.120101.11921.0)</span><span class="sxs-lookup"><span data-stu-id="06c8a-123">101.19.21 (20.120101.11921.0)</span></span>

- <span data-ttu-id="06c8a-124">Correcciones de errores</span><span class="sxs-lookup"><span data-stu-id="06c8a-124">Bug fixes</span></span>

## <a name="1011526-20120102115260"></a><span data-ttu-id="06c8a-125">101.15.26 (20.120102.11526.0)</span><span class="sxs-lookup"><span data-stu-id="06c8a-125">101.15.26 (20.120102.11526.0)</span></span>

- <span data-ttu-id="06c8a-126">Se mejoró la confiabilidad del agente al ejecutarse en macOS 11 Big Sur</span><span class="sxs-lookup"><span data-stu-id="06c8a-126">Improved the reliability of the agent when running on macOS 11 Big Sur</span></span>
- <span data-ttu-id="06c8a-127">Se agregó un nuevo modificador de línea de comandos ( `--ignore-exclusions` ) para omitir las exclusiones av durante los exámenes personalizados ( `mdatp scan custom` )</span><span class="sxs-lookup"><span data-stu-id="06c8a-127">Added a new command-line switch (`--ignore-exclusions`) to ignore AV exclusions during custom scans (`mdatp scan custom`)</span></span>
- <span data-ttu-id="06c8a-128">Mejoras de rendimiento & correcciones de errores</span><span class="sxs-lookup"><span data-stu-id="06c8a-128">Performance improvements & bug fixes</span></span>

## <a name="1011375-20120101113750"></a><span data-ttu-id="06c8a-129">101.13.75 (20.120101.11375.0)</span><span class="sxs-lookup"><span data-stu-id="06c8a-129">101.13.75 (20.120101.11375.0)</span></span>

- <span data-ttu-id="06c8a-130">Se quitaron las condiciones cuando Microsoft Defender para endpoint desencadenaba un error de macOS 11 (Big Sur) que se manifestó en un estado de pánico del kernel</span><span class="sxs-lookup"><span data-stu-id="06c8a-130">Removed conditions when Microsoft Defender for Endpoint was triggering a macOS 11 (Big Sur) bug that manifests into a kernel panic</span></span>
- <span data-ttu-id="06c8a-131">Se ha corregido una pérdida de memoria en la extensión del sistema Endpoint Security cuando se ejecutaba en mac 11 (Big Sur)</span><span class="sxs-lookup"><span data-stu-id="06c8a-131">Fixed a memory leak in the Endpoint Security system extension when running on mac 11 (Big Sur)</span></span>
- <span data-ttu-id="06c8a-132">Correcciones de errores</span><span class="sxs-lookup"><span data-stu-id="06c8a-132">Bug fixes</span></span>

## <a name="1011072"></a><span data-ttu-id="06c8a-133">101.10.72</span><span class="sxs-lookup"><span data-stu-id="06c8a-133">101.10.72</span></span>

- <span data-ttu-id="06c8a-134">Correcciones de errores</span><span class="sxs-lookup"><span data-stu-id="06c8a-134">Bug fixes</span></span>

## <a name="1010961"></a><span data-ttu-id="06c8a-135">101.09.61</span><span class="sxs-lookup"><span data-stu-id="06c8a-135">101.09.61</span></span>

- <span data-ttu-id="06c8a-136">Se agregó una nueva preferencia administrada para [deshabilitar la opción para enviar comentarios](mac-preferences.md#show--hide-option-to-send-feedback)</span><span class="sxs-lookup"><span data-stu-id="06c8a-136">Added a new managed preference for [disabling the option to send feedback](mac-preferences.md#show--hide-option-to-send-feedback)</span></span>
- <span data-ttu-id="06c8a-137">El icono del menú Estado ahora muestra un estado correcto cuando se administra la configuración del producto.</span><span class="sxs-lookup"><span data-stu-id="06c8a-137">Status menu icon now shows a healthy state when the product settings are managed.</span></span> <span data-ttu-id="06c8a-138">Anteriormente, el icono del menú de estado mostraba un estado de advertencia o error, aunque la configuración del producto la administraba el administrador.</span><span class="sxs-lookup"><span data-stu-id="06c8a-138">Previously, the status menu icon was displaying a warning or error state, even though the product settings were managed by the administrator</span></span>
- <span data-ttu-id="06c8a-139">Mejoras de rendimiento & correcciones de errores</span><span class="sxs-lookup"><span data-stu-id="06c8a-139">Performance improvements & bug fixes</span></span>

## <a name="1010950"></a><span data-ttu-id="06c8a-140">101.09.50</span><span class="sxs-lookup"><span data-stu-id="06c8a-140">101.09.50</span></span>

- <span data-ttu-id="06c8a-141">Esta versión del producto se validó en macOS Big Sur 11 beta 9</span><span class="sxs-lookup"><span data-stu-id="06c8a-141">This product version has been validated on macOS Big Sur 11 beta 9</span></span>

- <span data-ttu-id="06c8a-142">La nueva sintaxis de la `mdatp` herramienta de línea de comandos es ahora la predeterminada.</span><span class="sxs-lookup"><span data-stu-id="06c8a-142">The new syntax for the `mdatp` command-line tool is now the default one.</span></span> <span data-ttu-id="06c8a-143">Para obtener más información sobre la nueva sintaxis, vea [Resources for Microsoft Defender for Endpoint for Mac](mac-resources.md#configuring-from-the-command-line)</span><span class="sxs-lookup"><span data-stu-id="06c8a-143">For more information on the new syntax, see [Resources for Microsoft Defender for Endpoint for Mac](mac-resources.md#configuring-from-the-command-line)</span></span>

  > [!NOTE]
  > <span data-ttu-id="06c8a-144">La sintaxis de la herramienta de línea de comandos antigua se quitará del producto el 1 de enero **de 2021**.</span><span class="sxs-lookup"><span data-stu-id="06c8a-144">The old command-line tool syntax will be removed from the product on **January 1st, 2021**.</span></span>

- <span data-ttu-id="06c8a-145">Extendido con un nuevo parámetro ( ) que permite guardar los registros de `mdatp diagnostic create` diagnóstico en un directorio `--path [directory]` diferente</span><span class="sxs-lookup"><span data-stu-id="06c8a-145">Extended `mdatp diagnostic create` with a new parameter (`--path [directory]`) that allows the diagnostic logs to be saved to a different directory</span></span>
- <span data-ttu-id="06c8a-146">Mejoras de rendimiento & correcciones de errores</span><span class="sxs-lookup"><span data-stu-id="06c8a-146">Performance improvements & bug fixes</span></span>

## <a name="1010949"></a><span data-ttu-id="06c8a-147">101.09.49</span><span class="sxs-lookup"><span data-stu-id="06c8a-147">101.09.49</span></span>

- <span data-ttu-id="06c8a-148">Mejoras en la interfaz de usuario para diferenciar las exclusiones administradas por el administrador de TI frente a las exclusiones definidas por el usuario local</span><span class="sxs-lookup"><span data-stu-id="06c8a-148">User interface improvements to differentiate exclusions that are managed by the IT administrator versus exclusions defined by the local user</span></span>
- <span data-ttu-id="06c8a-149">Uso mejorado de la CPU durante exámenes a petición</span><span class="sxs-lookup"><span data-stu-id="06c8a-149">Improved CPU utilization during on-demand scans</span></span>
- <span data-ttu-id="06c8a-150">Mejoras de rendimiento & correcciones de errores</span><span class="sxs-lookup"><span data-stu-id="06c8a-150">Performance improvements & bug fixes</span></span>

## <a name="1010723"></a><span data-ttu-id="06c8a-151">101.07.23</span><span class="sxs-lookup"><span data-stu-id="06c8a-151">101.07.23</span></span>

- <span data-ttu-id="06c8a-152">Se agregaron nuevos campos a la salida de para comprobar el estado del modo pasivo y el id. `mdatp --health` de grupo de EDR</span><span class="sxs-lookup"><span data-stu-id="06c8a-152">Added new fields to the output of `mdatp --health` for checking the status of passive mode and the EDR group ID</span></span>

  > [!NOTE]
  > <span data-ttu-id="06c8a-153">`mdatp --health` se reemplazará con `mdatp health` en una actualización futura del producto.</span><span class="sxs-lookup"><span data-stu-id="06c8a-153">`mdatp --health` will be replaced with `mdatp health` in a future product update.</span></span>

- <span data-ttu-id="06c8a-154">Se ha corregido un error en el que el envío automático de muestra no estaba marcado como administrado en la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="06c8a-154">Fixed a bug where automatic sample submission was not marked as managed in the user interface</span></span>
- <span data-ttu-id="06c8a-155">Se agregó una nueva configuración para controlar la retención de elementos en el historial de análisis del antivirus.</span><span class="sxs-lookup"><span data-stu-id="06c8a-155">Added new settings for controlling the retention of items in the antivirus scan history.</span></span> <span data-ttu-id="06c8a-156">Ahora puede especificar [el número de días para](mac-preferences.md#antivirus-scan-history-retention-in-days) conservar elementos en el historial de análisis y especificar el número máximo de elementos en el historial de [examen](mac-preferences.md#maximum-number-of-items-in-the-antivirus-scan-history)</span><span class="sxs-lookup"><span data-stu-id="06c8a-156">You can now [specify the number of days to retain items in the scan history](mac-preferences.md#antivirus-scan-history-retention-in-days) and [specify the maximum number of items in the scan history](mac-preferences.md#maximum-number-of-items-in-the-antivirus-scan-history)</span></span>
- <span data-ttu-id="06c8a-157">Correcciones de errores</span><span class="sxs-lookup"><span data-stu-id="06c8a-157">Bug fixes</span></span>

## <a name="1010663"></a><span data-ttu-id="06c8a-158">101.06.63</span><span class="sxs-lookup"><span data-stu-id="06c8a-158">101.06.63</span></span>

- <span data-ttu-id="06c8a-159">Se ha abordado una regresión de rendimiento introducida en la versión `101.05.17` .</span><span class="sxs-lookup"><span data-stu-id="06c8a-159">Addressed a performance regression introduced in version `101.05.17`.</span></span> <span data-ttu-id="06c8a-160">La regresión se introdujo con la corrección para eliminar los problemas del kernel que algunos clientes han observado al acceder a recursos compartidos SMB.</span><span class="sxs-lookup"><span data-stu-id="06c8a-160">The regression was introduced with the fix to eliminate the kernel panics some customers have observed when accessing SMB shares.</span></span> <span data-ttu-id="06c8a-161">Hemos revertido este cambio de código y estamos investigando formas alternativas de eliminar los problemas del kernel.</span><span class="sxs-lookup"><span data-stu-id="06c8a-161">We have reverted this code change and are investigating alternative ways to eliminate the kernel panics.</span></span>

## <a name="1010517"></a><span data-ttu-id="06c8a-162">101.05.17</span><span class="sxs-lookup"><span data-stu-id="06c8a-162">101.05.17</span></span>

> [!IMPORTANT]
> <span data-ttu-id="06c8a-163">Estamos trabajando en una sintaxis nueva y mejorada para la herramienta `mdatp` de línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="06c8a-163">We are working on a new and enhanced syntax for the `mdatp` command-line tool.</span></span> <span data-ttu-id="06c8a-164">La nueva sintaxis es actualmente la predeterminada en los canales de actualización rápida e interna lenta de Insider.</span><span class="sxs-lookup"><span data-stu-id="06c8a-164">The new syntax is currently the default in the Insider Fast and Insider Slow update channels.</span></span> <span data-ttu-id="06c8a-165">Le recomendamos que se famliliarize con esta nueva sintaxis.</span><span class="sxs-lookup"><span data-stu-id="06c8a-165">We encourage you to famliliarize yourself with this new syntax.</span></span>
> 
> <span data-ttu-id="06c8a-166">Seguiremos dando soporte a la sintaxis antigua en paralelo con la nueva sintaxis y proporcionaremos más comunicación en torno al plan de desuso de la sintaxis antigua en los próximos meses.</span><span class="sxs-lookup"><span data-stu-id="06c8a-166">We will continue supporting the old syntax in parallel with the new syntax and will provide more communication around the deprecation plan for the old syntax in the upcoming months.</span></span>

- <span data-ttu-id="06c8a-167">Se ha solucionado un problema de kernel que se produjo a veces al acceder a recursos compartidos de archivos SMB</span><span class="sxs-lookup"><span data-stu-id="06c8a-167">Addressed a kernel panic that occurred sometimes when accessing SMB file shares</span></span>
- <span data-ttu-id="06c8a-168">Mejoras de rendimiento & correcciones de errores</span><span class="sxs-lookup"><span data-stu-id="06c8a-168">Performance improvements & bug fixes</span></span>

## <a name="1010516"></a><span data-ttu-id="06c8a-169">101.05.16</span><span class="sxs-lookup"><span data-stu-id="06c8a-169">101.05.16</span></span>

- <span data-ttu-id="06c8a-170">Mejoras en la lógica de examen rápido para reducir significativamente el número de archivos analizados</span><span class="sxs-lookup"><span data-stu-id="06c8a-170">Improvements to quick scan logic to significantly reduce the number of scanned files</span></span>
- <span data-ttu-id="06c8a-171">Se [agregó compatibilidad de autocompletion](mac-resources.md#how-to-enable-autocompletion) para la herramienta de línea de comandos</span><span class="sxs-lookup"><span data-stu-id="06c8a-171">Added [autocompletion support](mac-resources.md#how-to-enable-autocompletion) for the command-line tool</span></span>
- <span data-ttu-id="06c8a-172">Correcciones de errores</span><span class="sxs-lookup"><span data-stu-id="06c8a-172">Bug fixes</span></span>

## <a name="1010312"></a><span data-ttu-id="06c8a-173">101.03.12</span><span class="sxs-lookup"><span data-stu-id="06c8a-173">101.03.12</span></span>

- <span data-ttu-id="06c8a-174">Mejoras de rendimiento & correcciones de errores</span><span class="sxs-lookup"><span data-stu-id="06c8a-174">Performance improvements & bug fixes</span></span>

## <a name="1010154"></a><span data-ttu-id="06c8a-175">101.01.54</span><span class="sxs-lookup"><span data-stu-id="06c8a-175">101.01.54</span></span>

- <span data-ttu-id="06c8a-176">Mejoras en la compatibilidad con Time Machine</span><span class="sxs-lookup"><span data-stu-id="06c8a-176">Improvements around compatibility with Time Machine</span></span>
- <span data-ttu-id="06c8a-177">Mejoras de accesibilidad</span><span class="sxs-lookup"><span data-stu-id="06c8a-177">Accessibility improvements</span></span>
- <span data-ttu-id="06c8a-178">Mejoras de rendimiento & correcciones de errores</span><span class="sxs-lookup"><span data-stu-id="06c8a-178">Performance improvements & bug fixes</span></span>

## <a name="1010031"></a><span data-ttu-id="06c8a-179">101.00.31</span><span class="sxs-lookup"><span data-stu-id="06c8a-179">101.00.31</span></span>

- <span data-ttu-id="06c8a-180">Experiencia de [incorporación de productos mejorada para usuarios de Intune](https://docs.microsoft.com/mem/intune/apps/apps-advanced-threat-protection-macos)</span><span class="sxs-lookup"><span data-stu-id="06c8a-180">Improved [product onboarding experience for Intune users](https://docs.microsoft.com/mem/intune/apps/apps-advanced-threat-protection-macos)</span></span>
- <span data-ttu-id="06c8a-181">Las [exclusiones antivirus ahora admiten caracteres comodín](mac-exclusions.md#supported-exclusion-types)</span><span class="sxs-lookup"><span data-stu-id="06c8a-181">Antivirus [exclusions now support wildcards](mac-exclusions.md#supported-exclusion-types)</span></span>
- <span data-ttu-id="06c8a-182">Se agregó la capacidad de desencadenar exámenes antivirus desde el menú contextual de macOS.</span><span class="sxs-lookup"><span data-stu-id="06c8a-182">Added the ability to trigger antivirus scans from the macOS contextual menu.</span></span> <span data-ttu-id="06c8a-183">Ahora puedes hacer clic con el botón secundario en un archivo o una carpeta en Finder y seleccionar **Examinar con Microsoft Defender para endpoint**</span><span class="sxs-lookup"><span data-stu-id="06c8a-183">You can now right-click a file or a folder in Finder and select **Scan with Microsoft Defender for Endpoint**</span></span>
- <span data-ttu-id="06c8a-184">Las degradaciones de productos locales ahora son explícitamente no permitidos por el instalador.</span><span class="sxs-lookup"><span data-stu-id="06c8a-184">In-place product downgrades are now explicitly disallowed by the installer.</span></span> <span data-ttu-id="06c8a-185">Si necesita degradar, desinstale primero la versión existente y vuelva a configurar el dispositivo</span><span class="sxs-lookup"><span data-stu-id="06c8a-185">If you need to downgrade, first uninstall the existing version and reconfigure your device</span></span>
- <span data-ttu-id="06c8a-186">Otras mejoras de rendimiento & correcciones de errores</span><span class="sxs-lookup"><span data-stu-id="06c8a-186">Other performance improvements & bug fixes</span></span>

## <a name="1009027"></a><span data-ttu-id="06c8a-187">100.90.27</span><span class="sxs-lookup"><span data-stu-id="06c8a-187">100.90.27</span></span>

- <span data-ttu-id="06c8a-188">Ahora puedes establecer [un canal](mac-updates.md#set-the-channel-name) de actualización para Microsoft Defender para Endpoint para Mac que sea diferente del canal de actualización de todo el sistema</span><span class="sxs-lookup"><span data-stu-id="06c8a-188">You can now [set an update channel](mac-updates.md#set-the-channel-name) for Microsoft Defender for Endpoint for Mac that is different from the system-wide update channel</span></span>
- <span data-ttu-id="06c8a-189">Icono de nuevo producto</span><span class="sxs-lookup"><span data-stu-id="06c8a-189">New product icon</span></span>
- <span data-ttu-id="06c8a-190">Otras mejoras en la experiencia del usuario</span><span class="sxs-lookup"><span data-stu-id="06c8a-190">Other user experience improvements</span></span>
- <span data-ttu-id="06c8a-191">Correcciones de errores</span><span class="sxs-lookup"><span data-stu-id="06c8a-191">Bug fixes</span></span>

## <a name="1008692"></a><span data-ttu-id="06c8a-192">100.86.92</span><span class="sxs-lookup"><span data-stu-id="06c8a-192">100.86.92</span></span>

- <span data-ttu-id="06c8a-193">Mejoras en la compatibilidad con Time Machine</span><span class="sxs-lookup"><span data-stu-id="06c8a-193">Improvements around compatibility with Time Machine</span></span>
- <span data-ttu-id="06c8a-194">Se ha corregido un problema en el que el producto a veces no limpiaba todos los archivos durante `/Library/Application Support/Microsoft/Defender` la desinstalación</span><span class="sxs-lookup"><span data-stu-id="06c8a-194">Addressed an issue where the product was sometimes not cleaning all files under `/Library/Application Support/Microsoft/Defender` during uninstallation</span></span>
- <span data-ttu-id="06c8a-195">Se ha reducido el uso de cpu del producto cuando los productos de Microsoft se actualizan a través de Microsoft AutoUpdate</span><span class="sxs-lookup"><span data-stu-id="06c8a-195">Reduced the CPU utilization of the product when Microsoft products are updated through Microsoft AutoUpdate</span></span>
- <span data-ttu-id="06c8a-196">Otras mejoras de rendimiento & correcciones de errores</span><span class="sxs-lookup"><span data-stu-id="06c8a-196">Other performance improvements & bug fixes</span></span>

## <a name="1008691"></a><span data-ttu-id="06c8a-197">100.86.91</span><span class="sxs-lookup"><span data-stu-id="06c8a-197">100.86.91</span></span>

> [!CAUTION]
> <span data-ttu-id="06c8a-198">Para garantizar la protección más completa para los dispositivos macOS y en línea con que Apple detenga la entrega de actualizaciones de seguridad nativas de macOS en versiones del sistema operativo anteriores a [actual – 2], la implementación y las actualizaciones de MDATP para Mac ya no se admiten en macOS Sierra [10.12].</span><span class="sxs-lookup"><span data-stu-id="06c8a-198">To ensure the most complete protection for your macOS devices and in alignment with Apple stopping delivery of macOS native security updates to OS versions older than [current – 2], MDATP for Mac deployment and updates will no longer be supported on macOS Sierra [10.12].</span></span> <span data-ttu-id="06c8a-199">Las actualizaciones y mejoras de MDATP para Mac se entregarán a dispositivos que ejecutan versiones de Catalina [10.15], Mojave [10.14] y High Sierra [10.13].</span><span class="sxs-lookup"><span data-stu-id="06c8a-199">MDATP for Mac updates and enhancements will be delivered to devices running versions Catalina [10.15], Mojave [10.14], and High Sierra [10.13].</span></span> 
>
> <span data-ttu-id="06c8a-200">Si ya tienes MDATP para Mac implementado en tus dispositivos Sierra [10.12], actualiza a la versión más reciente de macOS para eliminar los riesgos de pérdida de protección.</span><span class="sxs-lookup"><span data-stu-id="06c8a-200">If you already have MDATP for Mac deployed to your Sierra [10.12] devices, please upgrade to the latest macOS version to eliminate risks of losing protection.</span></span>

- <span data-ttu-id="06c8a-201">Mejoras de rendimiento & correcciones de errores</span><span class="sxs-lookup"><span data-stu-id="06c8a-201">Performance improvements & bug fixes</span></span>

## <a name="1008373"></a><span data-ttu-id="06c8a-202">100.83.73</span><span class="sxs-lookup"><span data-stu-id="06c8a-202">100.83.73</span></span>

- <span data-ttu-id="06c8a-203">Se agregaron más controles para los administradores de TI en torno a la administración de [exclusiones,](mac-preferences.md#exclusion-merge-policy)la [administración](mac-preferences.md#threat-type-settings-merge-policy)de la configuración del tipo de amenaza y las [acciones de amenazas no permitidos](mac-preferences.md#disallowed-threat-actions)</span><span class="sxs-lookup"><span data-stu-id="06c8a-203">Added more controls for IT administrators around [management of exclusions](mac-preferences.md#exclusion-merge-policy), [management of threat type settings](mac-preferences.md#threat-type-settings-merge-policy), and [disallowed threat actions](mac-preferences.md#disallowed-threat-actions)</span></span>
- <span data-ttu-id="06c8a-204">Cuando el acceso a disco completo no está habilitado en el dispositivo, ahora se muestra una advertencia en el menú de estado</span><span class="sxs-lookup"><span data-stu-id="06c8a-204">When Full Disk Access is not enabled on the device, a warning is now displayed in the status menu</span></span>
- <span data-ttu-id="06c8a-205">Mejoras de rendimiento & correcciones de errores</span><span class="sxs-lookup"><span data-stu-id="06c8a-205">Performance improvements & bug fixes</span></span>

## <a name="1008260"></a><span data-ttu-id="06c8a-206">100.82.60</span><span class="sxs-lookup"><span data-stu-id="06c8a-206">100.82.60</span></span>

- <span data-ttu-id="06c8a-207">Se ha corregido un problema por el que el producto no se iniciaba después de una actualización de definición.</span><span class="sxs-lookup"><span data-stu-id="06c8a-207">Addressed an issue where the product fails to start following a definition update.</span></span>

## <a name="1008042"></a><span data-ttu-id="06c8a-208">100.80.42</span><span class="sxs-lookup"><span data-stu-id="06c8a-208">100.80.42</span></span>

- <span data-ttu-id="06c8a-209">Correcciones de errores</span><span class="sxs-lookup"><span data-stu-id="06c8a-209">Bug fixes</span></span>

## <a name="1007942"></a><span data-ttu-id="06c8a-210">100.79.42</span><span class="sxs-lookup"><span data-stu-id="06c8a-210">100.79.42</span></span>

- <span data-ttu-id="06c8a-211">Se ha corregido un problema por el que Microsoft Defender para Endpoint para Mac a veces interfiría con time machine</span><span class="sxs-lookup"><span data-stu-id="06c8a-211">Fixed an issue where Microsoft Defender for Endpoint for Mac was sometimes interfering with Time Machine</span></span>
- <span data-ttu-id="06c8a-212">Se agregó un nuevo modificador a la utilidad de línea de comandos para probar la conectividad con el servicio back-end</span><span class="sxs-lookup"><span data-stu-id="06c8a-212">Added a new switch to the command-line utility for testing the connectivity with the backend service</span></span>
  ```bash
  mdatp connectivity test
  ```
- <span data-ttu-id="06c8a-213">Se agregó la capacidad de ver el historial completo de amenazas en la interfaz de usuario (se puede obtener acceso desde la **vista Historial de** protección)</span><span class="sxs-lookup"><span data-stu-id="06c8a-213">Added ability to view the full threat history in the user interface (can be accessed from the **Protection history** view)</span></span>
- <span data-ttu-id="06c8a-214">Mejoras de rendimiento & correcciones de errores</span><span class="sxs-lookup"><span data-stu-id="06c8a-214">Performance improvements & bug fixes</span></span>

## <a name="1007215"></a><span data-ttu-id="06c8a-215">100.72.15</span><span class="sxs-lookup"><span data-stu-id="06c8a-215">100.72.15</span></span>

- <span data-ttu-id="06c8a-216">Correcciones de errores</span><span class="sxs-lookup"><span data-stu-id="06c8a-216">Bug fixes</span></span>

## <a name="1007099"></a><span data-ttu-id="06c8a-217">100.70.99</span><span class="sxs-lookup"><span data-stu-id="06c8a-217">100.70.99</span></span>

- <span data-ttu-id="06c8a-218">Se ha corregido un problema que afectaba a la capacidad de algunos usuarios de actualizar a macOS Catalina cuando la protección en tiempo real está habilitada.</span><span class="sxs-lookup"><span data-stu-id="06c8a-218">Addressed an issue that impacts the ability of some users to upgrade to macOS Catalina when real-time protection is enabled.</span></span> <span data-ttu-id="06c8a-219">Este problema esporádico se debe a que Microsoft Defender para los archivos de bloqueo de extremo dentro del paquete de actualización de Catalina al analizarlos en busca de amenazas, lo que provocó errores en la secuencia de actualización.</span><span class="sxs-lookup"><span data-stu-id="06c8a-219">This sporadic issue was caused by Microsoft Defender for Endpoint locking files within Catalina upgrade package while scanning them for threats, which led to failures in the upgrade sequence.</span></span>

## <a name="1006899"></a><span data-ttu-id="06c8a-220">100.68.99</span><span class="sxs-lookup"><span data-stu-id="06c8a-220">100.68.99</span></span>

- <span data-ttu-id="06c8a-221">Se agregó la capacidad de configurar la funcionalidad antivirus para que se ejecute en [modo pasivo](mac-preferences.md#enable--disable-passive-mode)</span><span class="sxs-lookup"><span data-stu-id="06c8a-221">Added the ability to configure the antivirus functionality to run in [passive mode](mac-preferences.md#enable--disable-passive-mode)</span></span>
- <span data-ttu-id="06c8a-222">Mejoras de rendimiento & correcciones de errores</span><span class="sxs-lookup"><span data-stu-id="06c8a-222">Performance improvements & bug fixes</span></span>

## <a name="1006528"></a><span data-ttu-id="06c8a-223">100.65.28</span><span class="sxs-lookup"><span data-stu-id="06c8a-223">100.65.28</span></span>

- <span data-ttu-id="06c8a-224">Se agregó compatibilidad con macOS Catalina</span><span class="sxs-lookup"><span data-stu-id="06c8a-224">Added support for macOS Catalina</span></span>

  > [!CAUTION]
  > <span data-ttu-id="06c8a-225">macOS 10.15 (Catalina) contiene nuevas mejoras de seguridad y privacidad.</span><span class="sxs-lookup"><span data-stu-id="06c8a-225">macOS 10.15 (Catalina) contains new security and privacy enhancements.</span></span> <span data-ttu-id="06c8a-226">A partir de esta versión, de forma predeterminada, las aplicaciones no pueden acceder a determinadas ubicaciones del disco (como Documentos, Descargas, Escritorio, etc.) sin consentimiento explícito.</span><span class="sxs-lookup"><span data-stu-id="06c8a-226">Beginning with this version, by default, applications are not able to access certain locations on disk (such as Documents, Downloads, Desktop, etc.) without explicit consent.</span></span> <span data-ttu-id="06c8a-227">En ausencia de este consentimiento, Microsoft Defender para Endpoint no puede proteger completamente el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="06c8a-227">In the absence of this consent, Microsoft Defender for Endpoint is not able to fully protect your device.</span></span>
  >
  > <span data-ttu-id="06c8a-228">El mecanismo para conceder este consentimiento depende de cómo implementó Microsoft Defender para endpoint:</span><span class="sxs-lookup"><span data-stu-id="06c8a-228">The mechanism for granting this consent depends on how you deployed Microsoft Defender for Endpoint:</span></span>
  >
  > - <span data-ttu-id="06c8a-229">Para las implementaciones manuales, vea las instrucciones actualizadas en el [tema Implementación](mac-install-manually.md#how-to-allow-full-disk-access) manual.</span><span class="sxs-lookup"><span data-stu-id="06c8a-229">For manual deployments, see the updated instructions in the [Manual deployment](mac-install-manually.md#how-to-allow-full-disk-access) topic.</span></span>
  > - <span data-ttu-id="06c8a-230">Para las implementaciones administradas, vea las instrucciones actualizadas en los temas de implementación basada en [JAMF](mac-install-with-jamf.md) y [microsoft Intune.](mac-install-with-intune.md#create-system-configuration-profiles)</span><span class="sxs-lookup"><span data-stu-id="06c8a-230">For managed deployments, see the updated instructions in the [JAMF-based deployment](mac-install-with-jamf.md) and [Microsoft Intune-based deployment](mac-install-with-intune.md#create-system-configuration-profiles) topics.</span></span>

- <span data-ttu-id="06c8a-231">Mejoras de rendimiento & correcciones de errores</span><span class="sxs-lookup"><span data-stu-id="06c8a-231">Performance improvements & bug fixes</span></span>
