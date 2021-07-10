---
title: Novedades de Microsoft Defender para Endpoint en Mac
description: Obtenga información sobre los cambios principales de versiones anteriores de Microsoft Defender para Endpoint en Mac.
keywords: microsoft, defender, Microsoft Defender para Endpoint, mac, installation, macos, whatsnew
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
ms.openlocfilehash: 841f22421ac81ba447dad70a68c4c7bc95605b16
ms.sourcegitcommit: 7dc3b4dec05299abb4290a6e3d1ebe0fdc622ed7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2021
ms.locfileid: "53363900"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-on-mac"></a><span data-ttu-id="c88b6-104">Novedades de Microsoft Defender para Endpoint en Mac</span><span class="sxs-lookup"><span data-stu-id="c88b6-104">What's new in Microsoft Defender for Endpoint on Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c88b6-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="c88b6-105">**Applies to:**</span></span>
- [<span data-ttu-id="c88b6-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="c88b6-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c88b6-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c88b6-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="c88b6-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="c88b6-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="c88b6-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="c88b6-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

> [!IMPORTANT]
> <span data-ttu-id="c88b6-110">En macOS 11 (Big Sur), Microsoft Defender para Endpoint requiere perfiles de configuración adicionales.</span><span class="sxs-lookup"><span data-stu-id="c88b6-110">On macOS 11 (Big Sur), Microsoft Defender for Endpoint requires additional configuration profiles.</span></span> <span data-ttu-id="c88b6-111">Si es un cliente existente que actualiza desde versiones anteriores de macOS, asegúrese de implementar los perfiles de configuración adicionales enumerados en [esta página](mac-sysext-policies.md).</span><span class="sxs-lookup"><span data-stu-id="c88b6-111">If you are an existing customer upgrading from earlier versions of macOS, make sure to deploy the additional configuration profiles listed on [this page](mac-sysext-policies.md).</span></span>

## <a name="1013420-20121051134200"></a><span data-ttu-id="c88b6-112">101.34.20 (20.121051.13420.0)</span><span class="sxs-lookup"><span data-stu-id="c88b6-112">101.34.20 (20.121051.13420.0)</span></span>

- <span data-ttu-id="c88b6-113">[El control de dispositivos para macOS](mac-device-control-overview.md) ahora está en disponibilidad general</span><span class="sxs-lookup"><span data-stu-id="c88b6-113">[Device control for macOS](mac-device-control-overview.md) is now in general availability</span></span>
- <span data-ttu-id="c88b6-114">Se ha corregido un problema por el que no se podía iniciar un examen rápido desde el menú de estado de macOS 11 (Big Sur)</span><span class="sxs-lookup"><span data-stu-id="c88b6-114">Addressed an issue where a quick scan could not be started from the status menu on macOS 11 (Big Sur)</span></span>
- <span data-ttu-id="c88b6-115">Otras correcciones de errores</span><span class="sxs-lookup"><span data-stu-id="c88b6-115">Other bug fixes</span></span>

## <a name="1013269-20121042132690"></a><span data-ttu-id="c88b6-116">101.32.69 (20.121042.13269.0)</span><span class="sxs-lookup"><span data-stu-id="c88b6-116">101.32.69 (20.121042.13269.0)</span></span>

- <span data-ttu-id="c88b6-117">Se ha corregido un problema por el que el acceso simultáneo a la cadena de teclas de Microsoft Defender para Endpoint y otras aplicaciones puede provocar daños en la cadena de teclas.</span><span class="sxs-lookup"><span data-stu-id="c88b6-117">Addressed an issue where concurrent access to the keychain from Microsoft Defender for Endpoint and other applications can lead to keychain corruption.</span></span>

## <a name="1012964-20121042129640"></a><span data-ttu-id="c88b6-118">101.29.64 (20.121042.12964.0)</span><span class="sxs-lookup"><span data-stu-id="c88b6-118">101.29.64 (20.121042.12964.0)</span></span>

- <span data-ttu-id="c88b6-119">A partir de esta versión, las amenazas detectadas durante los exámenes antivirus a petición desencadenados a través del cliente de línea de comandos se corrigen automáticamente.</span><span class="sxs-lookup"><span data-stu-id="c88b6-119">Starting with this version, threats detected during on-demand antivirus scans triggered through the command-line client are automatically remediated.</span></span> <span data-ttu-id="c88b6-120">Las amenazas detectadas durante los exámenes desencadenados a través de la interfaz de usuario aún requieren una acción manual.</span><span class="sxs-lookup"><span data-stu-id="c88b6-120">Threats detected during scans triggered through the user interface still require manual action.</span></span>
- <span data-ttu-id="c88b6-121">`mdatp diagnostic real-time-protection-statistics` ahora admite dos modificadores adicionales:</span><span class="sxs-lookup"><span data-stu-id="c88b6-121">`mdatp diagnostic real-time-protection-statistics` now supports two additional switches:</span></span>
  - <span data-ttu-id="c88b6-122">`--sort`: ordena el resultado descendente por número total de archivos analizados</span><span class="sxs-lookup"><span data-stu-id="c88b6-122">`--sort`: sorts the output descending by total number of files scanned</span></span>
  - <span data-ttu-id="c88b6-123">`--top N`: muestra los resultados N superiores (solo funciona si `--sort` también se especifica)</span><span class="sxs-lookup"><span data-stu-id="c88b6-123">`--top N`: displays the top N results (only works if `--sort` is also specified)</span></span>
- <span data-ttu-id="c88b6-124">Mejoras de rendimiento (específicamente para cuando se usa YARN) & correcciones de errores</span><span class="sxs-lookup"><span data-stu-id="c88b6-124">Performance improvements (specifically for when YARN is used) & bug fixes</span></span>

## <a name="1012750-20121022127500"></a><span data-ttu-id="c88b6-125">101.27.50 (20.121022.12750.0)</span><span class="sxs-lookup"><span data-stu-id="c88b6-125">101.27.50 (20.121022.12750.0)</span></span>

- <span data-ttu-id="c88b6-126">Corrección para dar cabida a la expiración del certificado de Apple para macOS Catalina y versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="c88b6-126">Fix to accommodate for Apple certificate expiration for macOS Catalina and earlier.</span></span> <span data-ttu-id="c88b6-127">Esta corrección restaura la & de administración de vulnerabilidades (TVM).</span><span class="sxs-lookup"><span data-stu-id="c88b6-127">This fix restores Threat & Vulnerability Management (TVM) functionality.</span></span>

## <a name="1012569-20121022125690"></a><span data-ttu-id="c88b6-128">101.25.69 (20.121022.12569.0)</span><span class="sxs-lookup"><span data-stu-id="c88b6-128">101.25.69 (20.121022.12569.0)</span></span>

- <span data-ttu-id="c88b6-129">Microsoft Defender para Endpoint en macOS ya está disponible en versión preliminar para los clientes del Gobierno de Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="c88b6-129">Microsoft Defender for Endpoint on macOS is now available in preview for US Government customers.</span></span> <span data-ttu-id="c88b6-130">Para obtener más información, vea [Microsoft Defender for Endpoint for US Government customers](gov.md).</span><span class="sxs-lookup"><span data-stu-id="c88b6-130">For more information, see [Microsoft Defender for Endpoint for US Government customers](gov.md).</span></span>
- <span data-ttu-id="c88b6-131">Mejoras de rendimiento (específicamente para la situación en la que se usa la aplicación XCode Simulator) & correcciones de errores.</span><span class="sxs-lookup"><span data-stu-id="c88b6-131">Performance improvements (specifically for the situation when the XCode Simulator app is used) & bug fixes.</span></span>

## <a name="1012364-20121021123640"></a><span data-ttu-id="c88b6-132">101.23.64 (20.121021.12364.0)</span><span class="sxs-lookup"><span data-stu-id="c88b6-132">101.23.64 (20.121021.12364.0)</span></span>

- <span data-ttu-id="c88b6-133">Se agregó una nueva opción a la herramienta de línea de comandos para ver información sobre el último examen a petición.</span><span class="sxs-lookup"><span data-stu-id="c88b6-133">Added a new option to the command-line tool to view information about the last on-demand scan.</span></span> <span data-ttu-id="c88b6-134">Para ver información sobre el último examen a petición, ejecute `mdatp health --details antivirus`</span><span class="sxs-lookup"><span data-stu-id="c88b6-134">To view information about the last on-demand scan, run `mdatp health --details antivirus`</span></span>
- <span data-ttu-id="c88b6-135">Mejoras de rendimiento & correcciones de errores</span><span class="sxs-lookup"><span data-stu-id="c88b6-135">Performance improvements & bug fixes</span></span>

## <a name="1012279-20121012122790"></a><span data-ttu-id="c88b6-136">101.22.79 (20.121012.12279.0)</span><span class="sxs-lookup"><span data-stu-id="c88b6-136">101.22.79 (20.121012.12279.0)</span></span>

- <span data-ttu-id="c88b6-137">Mejoras de rendimiento & correcciones de errores</span><span class="sxs-lookup"><span data-stu-id="c88b6-137">Performance improvements & bug fixes</span></span>

## <a name="1011988-20121011119880"></a><span data-ttu-id="c88b6-138">101.19.88 (20.121011.11988.0)</span><span class="sxs-lookup"><span data-stu-id="c88b6-138">101.19.88 (20.121011.11988.0)</span></span>

- <span data-ttu-id="c88b6-139">Mejoras de rendimiento & correcciones de errores</span><span class="sxs-lookup"><span data-stu-id="c88b6-139">Performance improvements & bug fixes</span></span>

## <a name="1011948-20120121119480"></a><span data-ttu-id="c88b6-140">101.19.48 (20.120121.11948.0)</span><span class="sxs-lookup"><span data-stu-id="c88b6-140">101.19.48 (20.120121.11948.0)</span></span>

> [!NOTE]
> <span data-ttu-id="c88b6-141">La sintaxis de la herramienta de línea de comandos antigua ha quedado en desuso con esta versión.</span><span class="sxs-lookup"><span data-stu-id="c88b6-141">The old command-line tool syntax has been deprecated with this release.</span></span> <span data-ttu-id="c88b6-142">Para obtener información sobre la nueva sintaxis, vea [Resources](mac-resources.md#configuring-from-the-command-line).</span><span class="sxs-lookup"><span data-stu-id="c88b6-142">For information on the new syntax, see [Resources](mac-resources.md#configuring-from-the-command-line).</span></span>

- <span data-ttu-id="c88b6-143">Se agregó un nuevo modificador de línea de comandos para deshabilitar la extensión de red: `mdatp system-extension network-filter disable` .</span><span class="sxs-lookup"><span data-stu-id="c88b6-143">Added a new command-line switch to disable the network extension: `mdatp system-extension network-filter disable`.</span></span> <span data-ttu-id="c88b6-144">Este comando puede ser útil para solucionar problemas de red que podrían estar relacionados con Microsoft Defender para Endpoint en Mac</span><span class="sxs-lookup"><span data-stu-id="c88b6-144">This command can be useful to troubleshoot networking issues that could be related to Microsoft Defender for Endpoint on Mac</span></span>
- <span data-ttu-id="c88b6-145">Mejoras de rendimiento & correcciones de errores</span><span class="sxs-lookup"><span data-stu-id="c88b6-145">Performance improvements & bug fixes</span></span>

## <a name="1011921-20120101119210"></a><span data-ttu-id="c88b6-146">101.19.21 (20.120101.11921.0)</span><span class="sxs-lookup"><span data-stu-id="c88b6-146">101.19.21 (20.120101.11921.0)</span></span>

- <span data-ttu-id="c88b6-147">Correcciones de errores</span><span class="sxs-lookup"><span data-stu-id="c88b6-147">Bug fixes</span></span>

## <a name="1011526-20120102115260"></a><span data-ttu-id="c88b6-148">101.15.26 (20.120102.11526.0)</span><span class="sxs-lookup"><span data-stu-id="c88b6-148">101.15.26 (20.120102.11526.0)</span></span>

- <span data-ttu-id="c88b6-149">Se mejoró la confiabilidad del agente al ejecutarse en macOS 11 Big Sur</span><span class="sxs-lookup"><span data-stu-id="c88b6-149">Improved the reliability of the agent when running on macOS 11 Big Sur</span></span>
- <span data-ttu-id="c88b6-150">Se agregó un nuevo modificador de línea de comandos ( `--ignore-exclusions` ) para omitir las exclusiones av durante los exámenes personalizados ( `mdatp scan custom` )</span><span class="sxs-lookup"><span data-stu-id="c88b6-150">Added a new command-line switch (`--ignore-exclusions`) to ignore AV exclusions during custom scans (`mdatp scan custom`)</span></span>
- <span data-ttu-id="c88b6-151">Mejoras de rendimiento & correcciones de errores</span><span class="sxs-lookup"><span data-stu-id="c88b6-151">Performance improvements & bug fixes</span></span>

## <a name="1011375-20120101113750"></a><span data-ttu-id="c88b6-152">101.13.75 (20.120101.11375.0)</span><span class="sxs-lookup"><span data-stu-id="c88b6-152">101.13.75 (20.120101.11375.0)</span></span>

- <span data-ttu-id="c88b6-153">Se quitaron las condiciones cuando Microsoft Defender para endpoint desencadenaba un error de macOS 11 (Big Sur) que se manifestó en un estado de pánico del kernel</span><span class="sxs-lookup"><span data-stu-id="c88b6-153">Removed conditions when Microsoft Defender for Endpoint was triggering a macOS 11 (Big Sur) bug that manifests into a kernel panic</span></span>
- <span data-ttu-id="c88b6-154">Se ha corregido una pérdida de memoria en la extensión del sistema Endpoint Security cuando se ejecutaba en mac 11 (Big Sur)</span><span class="sxs-lookup"><span data-stu-id="c88b6-154">Fixed a memory leak in the Endpoint Security system extension when running on mac 11 (Big Sur)</span></span>
- <span data-ttu-id="c88b6-155">Correcciones de errores</span><span class="sxs-lookup"><span data-stu-id="c88b6-155">Bug fixes</span></span>

## <a name="1011072"></a><span data-ttu-id="c88b6-156">101.10.72</span><span class="sxs-lookup"><span data-stu-id="c88b6-156">101.10.72</span></span>

- <span data-ttu-id="c88b6-157">Correcciones de errores</span><span class="sxs-lookup"><span data-stu-id="c88b6-157">Bug fixes</span></span>

## <a name="1010961"></a><span data-ttu-id="c88b6-158">101.09.61</span><span class="sxs-lookup"><span data-stu-id="c88b6-158">101.09.61</span></span>

- <span data-ttu-id="c88b6-159">Se agregó una nueva preferencia administrada para [deshabilitar la opción para enviar comentarios](mac-preferences.md#show--hide-option-to-send-feedback)</span><span class="sxs-lookup"><span data-stu-id="c88b6-159">Added a new managed preference for [disabling the option to send feedback](mac-preferences.md#show--hide-option-to-send-feedback)</span></span>
- <span data-ttu-id="c88b6-160">El icono del menú Estado ahora muestra un estado correcto cuando se administra la configuración del producto.</span><span class="sxs-lookup"><span data-stu-id="c88b6-160">Status menu icon now shows a healthy state when the product settings are managed.</span></span> <span data-ttu-id="c88b6-161">Anteriormente, el icono del menú de estado mostraba un estado de advertencia o error, aunque la configuración del producto la administraba el administrador.</span><span class="sxs-lookup"><span data-stu-id="c88b6-161">Previously, the status menu icon was displaying a warning or error state, even though the product settings were managed by the administrator</span></span>
- <span data-ttu-id="c88b6-162">Mejoras de rendimiento & correcciones de errores</span><span class="sxs-lookup"><span data-stu-id="c88b6-162">Performance improvements & bug fixes</span></span>

## <a name="1010950"></a><span data-ttu-id="c88b6-163">101.09.50</span><span class="sxs-lookup"><span data-stu-id="c88b6-163">101.09.50</span></span>

- <span data-ttu-id="c88b6-164">Esta versión del producto se validó en macOS Big Sur 11 beta 9</span><span class="sxs-lookup"><span data-stu-id="c88b6-164">This product version has been validated on macOS Big Sur 11 beta 9</span></span>

- <span data-ttu-id="c88b6-165">La nueva sintaxis de la `mdatp` herramienta de línea de comandos es ahora la predeterminada.</span><span class="sxs-lookup"><span data-stu-id="c88b6-165">The new syntax for the `mdatp` command-line tool is now the default one.</span></span> <span data-ttu-id="c88b6-166">Para obtener más información sobre la nueva sintaxis, vea [Resources for Microsoft Defender for Endpoint on macOS](mac-resources.md#configuring-from-the-command-line)</span><span class="sxs-lookup"><span data-stu-id="c88b6-166">For more information on the new syntax, see [Resources for Microsoft Defender for Endpoint on macOS](mac-resources.md#configuring-from-the-command-line)</span></span>

  > [!NOTE]
  > <span data-ttu-id="c88b6-167">La sintaxis de la herramienta de línea de comandos antigua se quitará del producto el 1 de enero **de 2021**.</span><span class="sxs-lookup"><span data-stu-id="c88b6-167">The old command-line tool syntax will be removed from the product on **January 1st, 2021**.</span></span>

- <span data-ttu-id="c88b6-168">Extendido con un nuevo parámetro ( ) que permite guardar los registros de `mdatp diagnostic create` diagnóstico en un directorio `--path [directory]` diferente</span><span class="sxs-lookup"><span data-stu-id="c88b6-168">Extended `mdatp diagnostic create` with a new parameter (`--path [directory]`) that allows the diagnostic logs to be saved to a different directory</span></span>
- <span data-ttu-id="c88b6-169">Mejoras de rendimiento & correcciones de errores</span><span class="sxs-lookup"><span data-stu-id="c88b6-169">Performance improvements & bug fixes</span></span>

## <a name="1010949"></a><span data-ttu-id="c88b6-170">101.09.49</span><span class="sxs-lookup"><span data-stu-id="c88b6-170">101.09.49</span></span>

- <span data-ttu-id="c88b6-171">Mejoras en la interfaz de usuario para diferenciar las exclusiones administradas por el administrador de TI frente a las exclusiones definidas por el usuario local</span><span class="sxs-lookup"><span data-stu-id="c88b6-171">User interface improvements to differentiate exclusions that are managed by the IT administrator versus exclusions defined by the local user</span></span>
- <span data-ttu-id="c88b6-172">Uso mejorado de la CPU durante exámenes a petición</span><span class="sxs-lookup"><span data-stu-id="c88b6-172">Improved CPU utilization during on-demand scans</span></span>
- <span data-ttu-id="c88b6-173">Mejoras de rendimiento & correcciones de errores</span><span class="sxs-lookup"><span data-stu-id="c88b6-173">Performance improvements & bug fixes</span></span>

## <a name="1010723"></a><span data-ttu-id="c88b6-174">101.07.23</span><span class="sxs-lookup"><span data-stu-id="c88b6-174">101.07.23</span></span>

- <span data-ttu-id="c88b6-175">Se agregaron nuevos campos a la salida de para comprobar el estado del modo pasivo y el `mdatp --health` EDR de grupo</span><span class="sxs-lookup"><span data-stu-id="c88b6-175">Added new fields to the output of `mdatp --health` for checking the status of passive mode and the EDR group ID</span></span>

  > [!NOTE]
  > <span data-ttu-id="c88b6-176">`mdatp --health` se reemplazará con `mdatp health` en una actualización futura del producto.</span><span class="sxs-lookup"><span data-stu-id="c88b6-176">`mdatp --health` will be replaced with `mdatp health` in a future product update.</span></span>

- <span data-ttu-id="c88b6-177">Se ha corregido un error en el que el envío automático de muestra no estaba marcado como administrado en la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="c88b6-177">Fixed a bug where automatic sample submission was not marked as managed in the user interface</span></span>
- <span data-ttu-id="c88b6-178">Se agregó una nueva configuración para controlar la retención de elementos en el historial de análisis del antivirus.</span><span class="sxs-lookup"><span data-stu-id="c88b6-178">Added new settings for controlling the retention of items in the antivirus scan history.</span></span> <span data-ttu-id="c88b6-179">Ahora puede especificar [el número de días para](mac-preferences.md#antivirus-scan-history-retention-in-days) conservar elementos en el historial de análisis y especificar el número máximo de elementos en el historial de [examen](mac-preferences.md#maximum-number-of-items-in-the-antivirus-scan-history)</span><span class="sxs-lookup"><span data-stu-id="c88b6-179">You can now [specify the number of days to retain items in the scan history](mac-preferences.md#antivirus-scan-history-retention-in-days) and [specify the maximum number of items in the scan history](mac-preferences.md#maximum-number-of-items-in-the-antivirus-scan-history)</span></span>
- <span data-ttu-id="c88b6-180">Correcciones de errores</span><span class="sxs-lookup"><span data-stu-id="c88b6-180">Bug fixes</span></span>

## <a name="1010663"></a><span data-ttu-id="c88b6-181">101.06.63</span><span class="sxs-lookup"><span data-stu-id="c88b6-181">101.06.63</span></span>

- <span data-ttu-id="c88b6-182">Se ha abordado una regresión de rendimiento introducida en la versión `101.05.17` .</span><span class="sxs-lookup"><span data-stu-id="c88b6-182">Addressed a performance regression introduced in version `101.05.17`.</span></span> <span data-ttu-id="c88b6-183">La regresión se introdujo con la corrección para eliminar los problemas del kernel que algunos clientes han observado al acceder a recursos compartidos SMB.</span><span class="sxs-lookup"><span data-stu-id="c88b6-183">The regression was introduced with the fix to eliminate the kernel panics some customers have observed when accessing SMB shares.</span></span> <span data-ttu-id="c88b6-184">Hemos revertido este cambio de código y estamos investigando formas alternativas de eliminar los problemas del kernel.</span><span class="sxs-lookup"><span data-stu-id="c88b6-184">We have reverted this code change and are investigating alternative ways to eliminate the kernel panics.</span></span>

## <a name="1010517"></a><span data-ttu-id="c88b6-185">101.05.17</span><span class="sxs-lookup"><span data-stu-id="c88b6-185">101.05.17</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c88b6-186">Estamos trabajando en una sintaxis nueva y mejorada para la herramienta `mdatp` de línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="c88b6-186">We are working on a new and enhanced syntax for the `mdatp` command-line tool.</span></span> <span data-ttu-id="c88b6-187">La nueva sintaxis es actualmente la predeterminada en los canales de actualización rápida e interna lenta de Insider.</span><span class="sxs-lookup"><span data-stu-id="c88b6-187">The new syntax is currently the default in the Insider Fast and Insider Slow update channels.</span></span> <span data-ttu-id="c88b6-188">Le recomendamos que se famliliarize con esta nueva sintaxis.</span><span class="sxs-lookup"><span data-stu-id="c88b6-188">We encourage you to famliliarize yourself with this new syntax.</span></span>
> 
> <span data-ttu-id="c88b6-189">Seguiremos dando soporte a la sintaxis antigua en paralelo con la nueva sintaxis y proporcionaremos más comunicación en torno al plan de desuso de la sintaxis antigua en los próximos meses.</span><span class="sxs-lookup"><span data-stu-id="c88b6-189">We will continue supporting the old syntax in parallel with the new syntax and will provide more communication around the deprecation plan for the old syntax in the upcoming months.</span></span>

- <span data-ttu-id="c88b6-190">Se ha solucionado un problema de kernel que se produjo a veces al acceder a recursos compartidos de archivos SMB</span><span class="sxs-lookup"><span data-stu-id="c88b6-190">Addressed a kernel panic that occurred sometimes when accessing SMB file shares</span></span>
- <span data-ttu-id="c88b6-191">Mejoras de rendimiento & correcciones de errores</span><span class="sxs-lookup"><span data-stu-id="c88b6-191">Performance improvements & bug fixes</span></span>

## <a name="1010516"></a><span data-ttu-id="c88b6-192">101.05.16</span><span class="sxs-lookup"><span data-stu-id="c88b6-192">101.05.16</span></span>

- <span data-ttu-id="c88b6-193">Mejoras en la lógica de examen rápido para reducir significativamente el número de archivos analizados</span><span class="sxs-lookup"><span data-stu-id="c88b6-193">Improvements to quick scan logic to significantly reduce the number of scanned files</span></span>
- <span data-ttu-id="c88b6-194">Se [agregó compatibilidad de autocompletion](mac-resources.md#how-to-enable-autocompletion) para la herramienta de línea de comandos</span><span class="sxs-lookup"><span data-stu-id="c88b6-194">Added [autocompletion support](mac-resources.md#how-to-enable-autocompletion) for the command-line tool</span></span>
- <span data-ttu-id="c88b6-195">Correcciones de errores</span><span class="sxs-lookup"><span data-stu-id="c88b6-195">Bug fixes</span></span>

## <a name="1010312"></a><span data-ttu-id="c88b6-196">101.03.12</span><span class="sxs-lookup"><span data-stu-id="c88b6-196">101.03.12</span></span>

- <span data-ttu-id="c88b6-197">Mejoras de rendimiento & correcciones de errores</span><span class="sxs-lookup"><span data-stu-id="c88b6-197">Performance improvements & bug fixes</span></span>

## <a name="1010154"></a><span data-ttu-id="c88b6-198">101.01.54</span><span class="sxs-lookup"><span data-stu-id="c88b6-198">101.01.54</span></span>

- <span data-ttu-id="c88b6-199">Mejoras en la compatibilidad con Time Machine</span><span class="sxs-lookup"><span data-stu-id="c88b6-199">Improvements around compatibility with Time Machine</span></span>
- <span data-ttu-id="c88b6-200">Mejoras de accesibilidad</span><span class="sxs-lookup"><span data-stu-id="c88b6-200">Accessibility improvements</span></span>
- <span data-ttu-id="c88b6-201">Mejoras de rendimiento & correcciones de errores</span><span class="sxs-lookup"><span data-stu-id="c88b6-201">Performance improvements & bug fixes</span></span>

## <a name="1010031"></a><span data-ttu-id="c88b6-202">101.00.31</span><span class="sxs-lookup"><span data-stu-id="c88b6-202">101.00.31</span></span>

- <span data-ttu-id="c88b6-203">Experiencia de [incorporación de productos mejorada para usuarios de Intune](/mem/intune/apps/apps-advanced-threat-protection-macos)</span><span class="sxs-lookup"><span data-stu-id="c88b6-203">Improved [product onboarding experience for Intune users](/mem/intune/apps/apps-advanced-threat-protection-macos)</span></span>
- <span data-ttu-id="c88b6-204">Las [exclusiones antivirus ahora admiten caracteres comodín](mac-exclusions.md#supported-exclusion-types)</span><span class="sxs-lookup"><span data-stu-id="c88b6-204">Antivirus [exclusions now support wildcards](mac-exclusions.md#supported-exclusion-types)</span></span>
- <span data-ttu-id="c88b6-205">Se agregó la capacidad de desencadenar exámenes antivirus desde el menú contextual de macOS.</span><span class="sxs-lookup"><span data-stu-id="c88b6-205">Added the ability to trigger antivirus scans from the macOS contextual menu.</span></span> <span data-ttu-id="c88b6-206">Ahora puedes hacer clic con el botón secundario en un archivo o una carpeta en Finder y seleccionar **Examinar con Microsoft Defender para endpoint**</span><span class="sxs-lookup"><span data-stu-id="c88b6-206">You can now right-click a file or a folder in Finder and select **Scan with Microsoft Defender for Endpoint**</span></span>
- <span data-ttu-id="c88b6-207">Las degradaciones de productos locales ahora son explícitamente no permitidos por el instalador.</span><span class="sxs-lookup"><span data-stu-id="c88b6-207">In-place product downgrades are now explicitly disallowed by the installer.</span></span> <span data-ttu-id="c88b6-208">Si necesita degradar, desinstale primero la versión existente y vuelva a configurar el dispositivo</span><span class="sxs-lookup"><span data-stu-id="c88b6-208">If you need to downgrade, first uninstall the existing version and reconfigure your device</span></span>
- <span data-ttu-id="c88b6-209">Otras mejoras de rendimiento & correcciones de errores</span><span class="sxs-lookup"><span data-stu-id="c88b6-209">Other performance improvements & bug fixes</span></span>

## <a name="1009027"></a><span data-ttu-id="c88b6-210">100.90.27</span><span class="sxs-lookup"><span data-stu-id="c88b6-210">100.90.27</span></span>

- <span data-ttu-id="c88b6-211">Ahora puede establecer [un canal de](mac-updates.md#set-the-channel-name) actualización para Microsoft Defender para Endpoint en macOS que sea diferente del canal de actualización de todo el sistema</span><span class="sxs-lookup"><span data-stu-id="c88b6-211">You can now [set an update channel](mac-updates.md#set-the-channel-name) for Microsoft Defender for Endpoint on macOS that is different from the system-wide update channel</span></span>
- <span data-ttu-id="c88b6-212">Icono de nuevo producto</span><span class="sxs-lookup"><span data-stu-id="c88b6-212">New product icon</span></span>
- <span data-ttu-id="c88b6-213">Otras mejoras en la experiencia del usuario</span><span class="sxs-lookup"><span data-stu-id="c88b6-213">Other user experience improvements</span></span>
- <span data-ttu-id="c88b6-214">Correcciones de errores</span><span class="sxs-lookup"><span data-stu-id="c88b6-214">Bug fixes</span></span>

## <a name="1008692"></a><span data-ttu-id="c88b6-215">100.86.92</span><span class="sxs-lookup"><span data-stu-id="c88b6-215">100.86.92</span></span>

- <span data-ttu-id="c88b6-216">Mejoras en la compatibilidad con Time Machine</span><span class="sxs-lookup"><span data-stu-id="c88b6-216">Improvements around compatibility with Time Machine</span></span>
- <span data-ttu-id="c88b6-217">Se ha corregido un problema en el que el producto a veces no limpiaba todos los archivos durante `/Library/Application Support/Microsoft/Defender` la desinstalación</span><span class="sxs-lookup"><span data-stu-id="c88b6-217">Addressed an issue where the product was sometimes not cleaning all files under `/Library/Application Support/Microsoft/Defender` during uninstallation</span></span>
- <span data-ttu-id="c88b6-218">Se ha reducido el uso de cpu del producto cuando los productos de Microsoft se actualizan a través de Microsoft AutoUpdate</span><span class="sxs-lookup"><span data-stu-id="c88b6-218">Reduced the CPU utilization of the product when Microsoft products are updated through Microsoft AutoUpdate</span></span>
- <span data-ttu-id="c88b6-219">Otras mejoras de rendimiento & correcciones de errores</span><span class="sxs-lookup"><span data-stu-id="c88b6-219">Other performance improvements & bug fixes</span></span>

## <a name="1008691"></a><span data-ttu-id="c88b6-220">100.86.91</span><span class="sxs-lookup"><span data-stu-id="c88b6-220">100.86.91</span></span>

> [!CAUTION]
> <span data-ttu-id="c88b6-221">Para garantizar la protección más completa para los dispositivos macOS y en línea con que Apple detenga la entrega de actualizaciones de seguridad nativas de macOS en versiones del sistema operativo anteriores a [actual – 2], la implementación y las actualizaciones de MDATP para Mac ya no se admiten en macOS Sierra [10.12].</span><span class="sxs-lookup"><span data-stu-id="c88b6-221">To ensure the most complete protection for your macOS devices and in alignment with Apple stopping delivery of macOS native security updates to OS versions older than [current – 2], MDATP for Mac deployment and updates will no longer be supported on macOS Sierra [10.12].</span></span> <span data-ttu-id="c88b6-222">Las actualizaciones y mejoras de MDATP para Mac se entregarán a dispositivos que ejecutan versiones de Catalina [10.15], Mojave [10.14] y High Sierra [10.13].</span><span class="sxs-lookup"><span data-stu-id="c88b6-222">MDATP for Mac updates and enhancements will be delivered to devices running versions Catalina [10.15], Mojave [10.14], and High Sierra [10.13].</span></span> 
>
> <span data-ttu-id="c88b6-223">Si ya tienes MDATP para Mac implementado en tus dispositivos Sierra [10.12], actualiza a la versión más reciente de macOS para eliminar los riesgos de pérdida de protección.</span><span class="sxs-lookup"><span data-stu-id="c88b6-223">If you already have MDATP for Mac deployed to your Sierra [10.12] devices, please upgrade to the latest macOS version to eliminate risks of losing protection.</span></span>

- <span data-ttu-id="c88b6-224">Mejoras de rendimiento & correcciones de errores</span><span class="sxs-lookup"><span data-stu-id="c88b6-224">Performance improvements & bug fixes</span></span>

## <a name="1008373"></a><span data-ttu-id="c88b6-225">100.83.73</span><span class="sxs-lookup"><span data-stu-id="c88b6-225">100.83.73</span></span>

- <span data-ttu-id="c88b6-226">Se agregaron más controles para los administradores de TI en torno a la administración de [exclusiones,](mac-preferences.md#exclusion-merge-policy)la [administración](mac-preferences.md#threat-type-settings-merge-policy)de la configuración del tipo de amenaza y las [acciones de amenazas no permitidos](mac-preferences.md#disallowed-threat-actions)</span><span class="sxs-lookup"><span data-stu-id="c88b6-226">Added more controls for IT administrators around [management of exclusions](mac-preferences.md#exclusion-merge-policy), [management of threat type settings](mac-preferences.md#threat-type-settings-merge-policy), and [disallowed threat actions](mac-preferences.md#disallowed-threat-actions)</span></span>
- <span data-ttu-id="c88b6-227">Cuando el acceso a disco completo no está habilitado en el dispositivo, ahora se muestra una advertencia en el menú de estado</span><span class="sxs-lookup"><span data-stu-id="c88b6-227">When Full Disk Access is not enabled on the device, a warning is now displayed in the status menu</span></span>
- <span data-ttu-id="c88b6-228">Mejoras de rendimiento & correcciones de errores</span><span class="sxs-lookup"><span data-stu-id="c88b6-228">Performance improvements & bug fixes</span></span>

## <a name="1008260"></a><span data-ttu-id="c88b6-229">100.82.60</span><span class="sxs-lookup"><span data-stu-id="c88b6-229">100.82.60</span></span>

- <span data-ttu-id="c88b6-230">Se ha corregido un problema por el que el producto no se iniciaba después de una actualización de definición.</span><span class="sxs-lookup"><span data-stu-id="c88b6-230">Addressed an issue where the product fails to start following a definition update.</span></span>

## <a name="1008042"></a><span data-ttu-id="c88b6-231">100.80.42</span><span class="sxs-lookup"><span data-stu-id="c88b6-231">100.80.42</span></span>

- <span data-ttu-id="c88b6-232">Correcciones de errores</span><span class="sxs-lookup"><span data-stu-id="c88b6-232">Bug fixes</span></span>

## <a name="1007942"></a><span data-ttu-id="c88b6-233">100.79.42</span><span class="sxs-lookup"><span data-stu-id="c88b6-233">100.79.42</span></span>

- <span data-ttu-id="c88b6-234">Se ha corregido un problema por el que Microsoft Defender para Endpoint en Mac a veces interfiría con time machine</span><span class="sxs-lookup"><span data-stu-id="c88b6-234">Fixed an issue where Microsoft Defender for Endpoint on Mac was sometimes interfering with Time Machine</span></span>
- <span data-ttu-id="c88b6-235">Se agregó un nuevo modificador a la utilidad de línea de comandos para probar la conectividad con el servicio back-end</span><span class="sxs-lookup"><span data-stu-id="c88b6-235">Added a new switch to the command-line utility for testing the connectivity with the backend service</span></span>
  ```bash
  mdatp connectivity test
  ```
- <span data-ttu-id="c88b6-236">Se agregó la capacidad de ver el historial completo de amenazas en la interfaz de usuario (se puede obtener acceso desde la **vista Historial de** protección)</span><span class="sxs-lookup"><span data-stu-id="c88b6-236">Added ability to view the full threat history in the user interface (can be accessed from the **Protection history** view)</span></span>
- <span data-ttu-id="c88b6-237">Mejoras de rendimiento & correcciones de errores</span><span class="sxs-lookup"><span data-stu-id="c88b6-237">Performance improvements & bug fixes</span></span>

## <a name="1007215"></a><span data-ttu-id="c88b6-238">100.72.15</span><span class="sxs-lookup"><span data-stu-id="c88b6-238">100.72.15</span></span>

- <span data-ttu-id="c88b6-239">Correcciones de errores</span><span class="sxs-lookup"><span data-stu-id="c88b6-239">Bug fixes</span></span>

## <a name="1007099"></a><span data-ttu-id="c88b6-240">100.70.99</span><span class="sxs-lookup"><span data-stu-id="c88b6-240">100.70.99</span></span>

- <span data-ttu-id="c88b6-241">Se ha corregido un problema que afectaba a la capacidad de algunos usuarios de actualizar a macOS Catalina cuando la protección en tiempo real está habilitada.</span><span class="sxs-lookup"><span data-stu-id="c88b6-241">Addressed an issue that impacts the ability of some users to upgrade to macOS Catalina when real-time protection is enabled.</span></span> <span data-ttu-id="c88b6-242">Este problema esporádico se debe a que Microsoft Defender para los archivos de bloqueo de extremo dentro del paquete de actualización de Catalina al analizarlos en busca de amenazas, lo que provocó errores en la secuencia de actualización.</span><span class="sxs-lookup"><span data-stu-id="c88b6-242">This sporadic issue was caused by Microsoft Defender for Endpoint locking files within Catalina upgrade package while scanning them for threats, which led to failures in the upgrade sequence.</span></span>

## <a name="1006899"></a><span data-ttu-id="c88b6-243">100.68.99</span><span class="sxs-lookup"><span data-stu-id="c88b6-243">100.68.99</span></span>

- <span data-ttu-id="c88b6-244">Se agregó la capacidad de configurar la funcionalidad antivirus para que se ejecute en [modo pasivo](mac-preferences.md#enable--disable-passive-mode)</span><span class="sxs-lookup"><span data-stu-id="c88b6-244">Added the ability to configure the antivirus functionality to run in [passive mode](mac-preferences.md#enable--disable-passive-mode)</span></span>
- <span data-ttu-id="c88b6-245">Mejoras de rendimiento & correcciones de errores</span><span class="sxs-lookup"><span data-stu-id="c88b6-245">Performance improvements & bug fixes</span></span>

## <a name="1006528"></a><span data-ttu-id="c88b6-246">100.65.28</span><span class="sxs-lookup"><span data-stu-id="c88b6-246">100.65.28</span></span>

- <span data-ttu-id="c88b6-247">Se agregó compatibilidad con macOS Catalina</span><span class="sxs-lookup"><span data-stu-id="c88b6-247">Added support for macOS Catalina</span></span>

  > [!CAUTION]
  > <span data-ttu-id="c88b6-248">macOS 10.15 (Catalina) contiene nuevas mejoras de seguridad y privacidad.</span><span class="sxs-lookup"><span data-stu-id="c88b6-248">macOS 10.15 (Catalina) contains new security and privacy enhancements.</span></span> <span data-ttu-id="c88b6-249">A partir de esta versión, de forma predeterminada, las aplicaciones no pueden acceder a determinadas ubicaciones del disco (como Documentos, Descargas, Escritorio, etc.) sin consentimiento explícito.</span><span class="sxs-lookup"><span data-stu-id="c88b6-249">Beginning with this version, by default, applications are not able to access certain locations on disk (such as Documents, Downloads, Desktop, etc.) without explicit consent.</span></span> <span data-ttu-id="c88b6-250">En ausencia de este consentimiento, Microsoft Defender para Endpoint no puede proteger completamente el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c88b6-250">In the absence of this consent, Microsoft Defender for Endpoint is not able to fully protect your device.</span></span>
  >
  > <span data-ttu-id="c88b6-251">El mecanismo para conceder este consentimiento depende de cómo implementó Microsoft Defender para endpoint:</span><span class="sxs-lookup"><span data-stu-id="c88b6-251">The mechanism for granting this consent depends on how you deployed Microsoft Defender for Endpoint:</span></span>
  >
  > - <span data-ttu-id="c88b6-252">Para las implementaciones manuales, vea las instrucciones actualizadas en el [tema Implementación](mac-install-manually.md#how-to-allow-full-disk-access) manual.</span><span class="sxs-lookup"><span data-stu-id="c88b6-252">For manual deployments, see the updated instructions in the [Manual deployment](mac-install-manually.md#how-to-allow-full-disk-access) topic.</span></span>
  > - <span data-ttu-id="c88b6-253">Para las implementaciones administradas, vea las instrucciones actualizadas en los temas de implementación basada en [JAMF](mac-install-with-jamf.md) [y Microsoft Intune de implementación](mac-install-with-intune.md#create-system-configuration-profiles) basada en JAMF.</span><span class="sxs-lookup"><span data-stu-id="c88b6-253">For managed deployments, see the updated instructions in the [JAMF-based deployment](mac-install-with-jamf.md) and [Microsoft Intune-based deployment](mac-install-with-intune.md#create-system-configuration-profiles) topics.</span></span>

- <span data-ttu-id="c88b6-254">Mejoras de rendimiento & correcciones de errores</span><span class="sxs-lookup"><span data-stu-id="c88b6-254">Performance improvements & bug fixes</span></span>
