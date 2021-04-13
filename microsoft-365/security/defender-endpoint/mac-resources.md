---
title: Recursos para ATP de Microsoft Defender para Mac
description: Recursos para ATP de Microsoft Defender para Mac, como cómo desinstalarlo, cómo recopilar registros de diagnóstico, comandos de CLI y problemas conocidos con el producto.
keywords: microsoft, defender, atp, mac, installation, deploy, uninstallation, intune, jamf, macos, catalina, mojave, high sierra
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
ms.openlocfilehash: 71ebe48fdbb8f9995ef2f3429cb8a824ed76f244
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689646"
---
# <a name="resources-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="92efb-104">Recursos para Microsoft Defender para endpoint en macOS</span><span class="sxs-lookup"><span data-stu-id="92efb-104">Resources for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="92efb-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="92efb-105">**Applies to:**</span></span>
- [<span data-ttu-id="92efb-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="92efb-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="92efb-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="92efb-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="92efb-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="92efb-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="92efb-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="92efb-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="collecting-diagnostic-information"></a><span data-ttu-id="92efb-110">Recopilación de información de diagnóstico</span><span class="sxs-lookup"><span data-stu-id="92efb-110">Collecting diagnostic information</span></span>

<span data-ttu-id="92efb-111">Si puede reproducir un problema, aumente el nivel de registro, ejecute el sistema durante algún tiempo y restaure el nivel de registro en el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="92efb-111">If you can reproduce a problem, increase the logging level, run the system for some time, and restore the logging level to the default.</span></span>

1. <span data-ttu-id="92efb-112">Aumentar el nivel de registro:</span><span class="sxs-lookup"><span data-stu-id="92efb-112">Increase logging level:</span></span>

   ```bash
   mdatp log level set --level verbose
   ```

   ```Output
   Log level configured successfully
   ```

2. <span data-ttu-id="92efb-113">Reproducir el problema</span><span class="sxs-lookup"><span data-stu-id="92efb-113">Reproduce the problem</span></span>

3. <span data-ttu-id="92efb-114">Ejecute `sudo mdatp diagnostic create` para realizar una copia de seguridad de los registros de Microsoft Defender para puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="92efb-114">Run `sudo mdatp diagnostic create` to back up the Microsoft Defender for Endpoint logs.</span></span> <span data-ttu-id="92efb-115">Los archivos se almacenarán dentro de un archivo .zip.</span><span class="sxs-lookup"><span data-stu-id="92efb-115">The files will be stored inside a .zip archive.</span></span> <span data-ttu-id="92efb-116">Este comando también imprimirá la ruta de acceso del archivo a la copia de seguridad después de que la operación se realice correctamente.</span><span class="sxs-lookup"><span data-stu-id="92efb-116">This command will also print out the file path to the backup after the operation succeeds.</span></span>

   > [!TIP]
   > <span data-ttu-id="92efb-117">De forma predeterminada, los registros de diagnóstico se guardan en `/Library/Application Support/Microsoft/Defender/wdavdiag/` .</span><span class="sxs-lookup"><span data-stu-id="92efb-117">By default, diagnostic logs are saved to `/Library/Application Support/Microsoft/Defender/wdavdiag/`.</span></span> <span data-ttu-id="92efb-118">Para cambiar el directorio donde se guardan los registros de diagnóstico, pase al `--path [directory]` comando siguiente, reemplazando `[directory]` por el directorio deseado.</span><span class="sxs-lookup"><span data-stu-id="92efb-118">To change the directory where diagnostic logs are saved, pass `--path [directory]` to the below command, replacing `[directory]` with the desired directory.</span></span>

   ```bash
   sudo mdatp diagnostic create
   ```
   ```console
   Diagnostic file created: "/Library/Application Support/Microsoft/Defender/wdavdiag/932e68a8-8f2e-4ad0-a7f2-65eb97c0de01.zip"
   ```

4. <span data-ttu-id="92efb-119">Restaurar nivel de registro:</span><span class="sxs-lookup"><span data-stu-id="92efb-119">Restore logging level:</span></span>

   ```bash
   mdatp log level set --level info
   ```
   ```console
   Log level configured successfully
   ```

## <a name="logging-installation-issues"></a><span data-ttu-id="92efb-120">Problemas de instalación de registro</span><span class="sxs-lookup"><span data-stu-id="92efb-120">Logging installation issues</span></span>

<span data-ttu-id="92efb-121">Si se produce un error durante la instalación, el instalador solo informará de un error general.</span><span class="sxs-lookup"><span data-stu-id="92efb-121">If an error occurs during installation, the installer will only report a general failure.</span></span>

<span data-ttu-id="92efb-122">El registro detallado se guardará en `/Library/Logs/Microsoft/mdatp/install.log` .</span><span class="sxs-lookup"><span data-stu-id="92efb-122">The detailed log will be saved to `/Library/Logs/Microsoft/mdatp/install.log`.</span></span> <span data-ttu-id="92efb-123">Si tiene problemas durante la instalación, envíenos este archivo para que podamos diagnosticar la causa.</span><span class="sxs-lookup"><span data-stu-id="92efb-123">If you experience issues during installation, send us this file so we can help diagnose the cause.</span></span>

## <a name="uninstalling"></a><span data-ttu-id="92efb-124">Desinstalación</span><span class="sxs-lookup"><span data-stu-id="92efb-124">Uninstalling</span></span>

<span data-ttu-id="92efb-125">Hay varias maneras de desinstalar Microsoft Defender para Endpoint en macOS.</span><span class="sxs-lookup"><span data-stu-id="92efb-125">There are several ways to uninstall Microsoft Defender for Endpoint on macOS.</span></span> <span data-ttu-id="92efb-126">Tenga en cuenta que aunque la desinstalación administrada centralmente está disponible en JAMF, todavía no está disponible para Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="92efb-126">Note that while centrally managed uninstall is available on JAMF, it is not yet available for Microsoft Intune.</span></span>

### <a name="interactive-uninstallation"></a><span data-ttu-id="92efb-127">Desinstalación interactiva</span><span class="sxs-lookup"><span data-stu-id="92efb-127">Interactive uninstallation</span></span>

- <span data-ttu-id="92efb-128">Abre **Finder > aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="92efb-128">Open **Finder > Applications**.</span></span> <span data-ttu-id="92efb-129">Haga clic con el botón **secundario en Microsoft Defender ATP > Mover a la papelera**.</span><span class="sxs-lookup"><span data-stu-id="92efb-129">Right click on **Microsoft Defender ATP > Move to Trash**.</span></span>

### <a name="from-the-command-line"></a><span data-ttu-id="92efb-130">Desde la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="92efb-130">From the command line</span></span>

- ```sudo rm -rf '/Applications/Microsoft Defender ATP.app'```
- ```sudo rm -rf '/Library/Application Support/Microsoft/Defender/'```

## <a name="configuring-from-the-command-line"></a><span data-ttu-id="92efb-131">Configuración desde la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="92efb-131">Configuring from the command line</span></span>

<span data-ttu-id="92efb-132">Las tareas importantes, como controlar la configuración del producto y desencadenar exámenes a petición, se pueden realizar desde la línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="92efb-132">Important tasks, such as controlling product settings and triggering on-demand scans, can be done from the command line:</span></span>

|<span data-ttu-id="92efb-133">Grupo</span><span class="sxs-lookup"><span data-stu-id="92efb-133">Group</span></span>        |<span data-ttu-id="92efb-134">Escenario</span><span class="sxs-lookup"><span data-stu-id="92efb-134">Scenario</span></span>                                   |<span data-ttu-id="92efb-135">Comando</span><span class="sxs-lookup"><span data-stu-id="92efb-135">Command</span></span>                                                                           |
|-------------|-------------------------------------------|----------------------------------------------------------------------------------|
|<span data-ttu-id="92efb-136">Configuración</span><span class="sxs-lookup"><span data-stu-id="92efb-136">Configuration</span></span>|<span data-ttu-id="92efb-137">Activar/desactivar la protección en tiempo real</span><span class="sxs-lookup"><span data-stu-id="92efb-137">Turn on/off real-time protection</span></span>           |`mdatp config real-time-protection --value [enabled/disabled]`                    |
|<span data-ttu-id="92efb-138">Configuración</span><span class="sxs-lookup"><span data-stu-id="92efb-138">Configuration</span></span>|<span data-ttu-id="92efb-139">Activar/desactivar la protección en la nube</span><span class="sxs-lookup"><span data-stu-id="92efb-139">Turn on/off cloud protection</span></span>               |`mdatp config cloud --value [enabled/disabled]`                                   |
|<span data-ttu-id="92efb-140">Configuración</span><span class="sxs-lookup"><span data-stu-id="92efb-140">Configuration</span></span>|<span data-ttu-id="92efb-141">Activar/desactivar diagnósticos de productos</span><span class="sxs-lookup"><span data-stu-id="92efb-141">Turn on/off product diagnostics</span></span>            |`mdatp config cloud-diagnostic --value [enabled/disabled]`                        |
|<span data-ttu-id="92efb-142">Configuración</span><span class="sxs-lookup"><span data-stu-id="92efb-142">Configuration</span></span>|<span data-ttu-id="92efb-143">Activar/desactivar el envío automático de muestra</span><span class="sxs-lookup"><span data-stu-id="92efb-143">Turn on/off automatic sample submission</span></span>    |`mdatp config cloud-automatic-sample-submission --value [enabled/disabled]`       |
|<span data-ttu-id="92efb-144">Configuración</span><span class="sxs-lookup"><span data-stu-id="92efb-144">Configuration</span></span>|<span data-ttu-id="92efb-145">Agregar un nombre de amenaza a la lista permitida</span><span class="sxs-lookup"><span data-stu-id="92efb-145">Add a threat name to the allowed list</span></span>      |`mdatp threat allowed add --name [threat-name]`                                   |
|<span data-ttu-id="92efb-146">Configuración</span><span class="sxs-lookup"><span data-stu-id="92efb-146">Configuration</span></span>|<span data-ttu-id="92efb-147">Quitar un nombre de amenaza de la lista permitida</span><span class="sxs-lookup"><span data-stu-id="92efb-147">Remove a threat name from the allowed list</span></span> |`mdatp threat allowed remove --name [threat-name]`                                |
|<span data-ttu-id="92efb-148">Configuración</span><span class="sxs-lookup"><span data-stu-id="92efb-148">Configuration</span></span>|<span data-ttu-id="92efb-149">Enumerar todos los nombres de amenazas permitidos</span><span class="sxs-lookup"><span data-stu-id="92efb-149">List all allowed threat names</span></span>              |`mdatp threat allowed list`                                                       |
|<span data-ttu-id="92efb-150">Configuración</span><span class="sxs-lookup"><span data-stu-id="92efb-150">Configuration</span></span>|<span data-ttu-id="92efb-151">Activar la protección de LA PUA</span><span class="sxs-lookup"><span data-stu-id="92efb-151">Turn on PUA protection</span></span>                     |`mdatp threat policy set --type potentially_unwanted_application -- action block` |
|<span data-ttu-id="92efb-152">Configuración</span><span class="sxs-lookup"><span data-stu-id="92efb-152">Configuration</span></span>|<span data-ttu-id="92efb-153">Desactivar la protección de LA PUA</span><span class="sxs-lookup"><span data-stu-id="92efb-153">Turn off PUA protection</span></span>                    |`mdatp threat policy set --type potentially_unwanted_application -- action off`   |
|<span data-ttu-id="92efb-154">Configuración</span><span class="sxs-lookup"><span data-stu-id="92efb-154">Configuration</span></span>|<span data-ttu-id="92efb-155">Activar el modo de auditoría para la protección de PUA</span><span class="sxs-lookup"><span data-stu-id="92efb-155">Turn on audit mode for PUA protection</span></span>      |`mdatp threat policy set --type potentially_unwanted_application -- action audit` |
|<span data-ttu-id="92efb-156">Configuración</span><span class="sxs-lookup"><span data-stu-id="92efb-156">Configuration</span></span>|<span data-ttu-id="92efb-157">Activar/desactivar passiveMode</span><span class="sxs-lookup"><span data-stu-id="92efb-157">Turn on/off passiveMode</span></span>                    |`mdatp config passive-mode --value enabled [enabled/disabled]`                    |
|<span data-ttu-id="92efb-158">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="92efb-158">Diagnostics</span></span>  |<span data-ttu-id="92efb-159">Cambiar el nivel de registro</span><span class="sxs-lookup"><span data-stu-id="92efb-159">Change the log level</span></span>                       |`mdatp log level set --level [error/warning/info/verbose]`                        |
|<span data-ttu-id="92efb-160">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="92efb-160">Diagnostics</span></span>  |<span data-ttu-id="92efb-161">Generar registros de diagnóstico</span><span class="sxs-lookup"><span data-stu-id="92efb-161">Generate diagnostic logs</span></span>                   |`mdatp diagnostic create --path [directory]`                                      |
|<span data-ttu-id="92efb-162">Salud</span><span class="sxs-lookup"><span data-stu-id="92efb-162">Health</span></span>       |<span data-ttu-id="92efb-163">Comprobar el estado del producto</span><span class="sxs-lookup"><span data-stu-id="92efb-163">Check the product's health</span></span>                 |`mdatp health`                                                                    |
|<span data-ttu-id="92efb-164">Salud</span><span class="sxs-lookup"><span data-stu-id="92efb-164">Health</span></span>       |<span data-ttu-id="92efb-165">Buscar un atributo de producto spefic</span><span class="sxs-lookup"><span data-stu-id="92efb-165">Check for a spefic product attribute</span></span>       |`mdatp health --field [attribute: healthy/licensed/engine_version...]`            |
|<span data-ttu-id="92efb-166">Protection</span><span class="sxs-lookup"><span data-stu-id="92efb-166">Protection</span></span>   |<span data-ttu-id="92efb-167">Examinar una ruta de acceso</span><span class="sxs-lookup"><span data-stu-id="92efb-167">Scan a path</span></span>                                |`mdatp scan custom --path [path] [--ignore-exclusions]`                           |
|<span data-ttu-id="92efb-168">Protection</span><span class="sxs-lookup"><span data-stu-id="92efb-168">Protection</span></span>   |<span data-ttu-id="92efb-169">Realizar un examen rápido</span><span class="sxs-lookup"><span data-stu-id="92efb-169">Do a quick scan</span></span>                            |`mdatp scan quick`                                                                |
|<span data-ttu-id="92efb-170">Protection</span><span class="sxs-lookup"><span data-stu-id="92efb-170">Protection</span></span>   |<span data-ttu-id="92efb-171">Realizar un examen completo</span><span class="sxs-lookup"><span data-stu-id="92efb-171">Do a full scan</span></span>                             |`mdatp scan full`                                                                 |
|<span data-ttu-id="92efb-172">Protection</span><span class="sxs-lookup"><span data-stu-id="92efb-172">Protection</span></span>   |<span data-ttu-id="92efb-173">Cancelar un examen a petición en curso</span><span class="sxs-lookup"><span data-stu-id="92efb-173">Cancel an ongoing on-demand scan</span></span>           |`mdatp scan cancel`                                                               |
|<span data-ttu-id="92efb-174">Protection</span><span class="sxs-lookup"><span data-stu-id="92efb-174">Protection</span></span>   |<span data-ttu-id="92efb-175">Solicitar una actualización de inteligencia de seguridad</span><span class="sxs-lookup"><span data-stu-id="92efb-175">Request a security intelligence update</span></span>     |`mdatp definitions update`                                                        |
|<span data-ttu-id="92efb-176">EDR</span><span class="sxs-lookup"><span data-stu-id="92efb-176">EDR</span></span>          |<span data-ttu-id="92efb-177">Agregar etiqueta de grupo al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="92efb-177">Add group tag to device.</span></span> <span data-ttu-id="92efb-178">Las etiquetas EDR se usan para administrar grupos de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="92efb-178">EDR tags are used for managing device groups.</span></span> <span data-ttu-id="92efb-179">Para obtener más información, visite https://docs.microsoft.com/microsoft-365/security/defender-endpoint/machine-groups</span><span class="sxs-lookup"><span data-stu-id="92efb-179">For more information, please visit https://docs.microsoft.com/microsoft-365/security/defender-endpoint/machine-groups</span></span> |`mdatp edr tag set --name GROUP --value [name]` |
|<span data-ttu-id="92efb-180">EDR</span><span class="sxs-lookup"><span data-stu-id="92efb-180">EDR</span></span>          |<span data-ttu-id="92efb-181">Quitar etiqueta de grupo del dispositivo</span><span class="sxs-lookup"><span data-stu-id="92efb-181">Remove group tag from device</span></span>               |`mdatp edr tag remove --tag-name [name]`                                          |
|<span data-ttu-id="92efb-182">EDR</span><span class="sxs-lookup"><span data-stu-id="92efb-182">EDR</span></span>          |<span data-ttu-id="92efb-183">Agregar id. de grupo</span><span class="sxs-lookup"><span data-stu-id="92efb-183">Add Group ID</span></span>                               |`mdatp edr group-ids --group-id [group]`                                          |

### <a name="how-to-enable-autocompletion"></a><span data-ttu-id="92efb-184">Cómo habilitar la autocompleción</span><span class="sxs-lookup"><span data-stu-id="92efb-184">How to enable autocompletion</span></span>

<span data-ttu-id="92efb-185">Para habilitar la autocompleción en bash, ejecute el siguiente comando y reinicie la sesión de Terminal:</span><span class="sxs-lookup"><span data-stu-id="92efb-185">To enable autocompletion in bash, run the following command and restart the Terminal session:</span></span>

```bash
echo "source /Applications/Microsoft\ Defender\ ATP.app/Contents/Resources/Tools/mdatp_completion.bash" >> ~/.bash_profile
```

<span data-ttu-id="92efb-186">Para habilitar la autocompleción en zsh:</span><span class="sxs-lookup"><span data-stu-id="92efb-186">To enable autocompletion in zsh:</span></span>

- <span data-ttu-id="92efb-187">Comprueba si la autocompleción está habilitada en el dispositivo:</span><span class="sxs-lookup"><span data-stu-id="92efb-187">Check whether autocompletion is enabled on your device:</span></span>

   ```zsh
   cat ~/.zshrc | grep autoload
   ```

- <span data-ttu-id="92efb-188">Si el comando anterior no produce ningún resultado, puede habilitar la autocompleción con el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="92efb-188">If the preceding command does not produce any output, you can enable autocompletion using the following command:</span></span>

   ```zsh
   echo "autoload -Uz compinit && compinit" >> ~/.zshrc
   ```

- <span data-ttu-id="92efb-189">Ejecute los siguientes comandos para habilitar la autocompleción para Microsoft Defender para Endpoint en macOS y reinicie la sesión de Terminal:</span><span class="sxs-lookup"><span data-stu-id="92efb-189">Run the following commands to enable autocompletion for Microsoft Defender for Endpoint on macOS and restart the Terminal session:</span></span>

   ```zsh
   sudo mkdir -p /usr/local/share/zsh/site-functions
   ```
   ```zsh
   sudo ln -svf "/Applications/Microsoft Defender ATP.app/Contents/Resources/Tools/mdatp_completion.zsh" /usr/local/share/zsh/site-functions/_mdatp
   ```

## <a name="client-microsoft-defender-for-endpoint-quarantine-directory"></a><span data-ttu-id="92efb-190">Directorio de cuarentena cliente de Microsoft Defender para extremo</span><span class="sxs-lookup"><span data-stu-id="92efb-190">Client Microsoft Defender for Endpoint quarantine directory</span></span>

<span data-ttu-id="92efb-191">`/Library/Application Support/Microsoft/Defender/quarantine/` contiene los archivos en cuarentena por `mdatp` .</span><span class="sxs-lookup"><span data-stu-id="92efb-191">`/Library/Application Support/Microsoft/Defender/quarantine/` contains the files quarantined by `mdatp`.</span></span> <span data-ttu-id="92efb-192">Los archivos se denominan después del trackingId de amenazas.</span><span class="sxs-lookup"><span data-stu-id="92efb-192">The files are named after the threat trackingId.</span></span> <span data-ttu-id="92efb-193">El trackingIds actual se muestra con `mdatp threat list` .</span><span class="sxs-lookup"><span data-stu-id="92efb-193">The current trackingIds is shown with `mdatp threat list`.</span></span>

## <a name="microsoft-defender-for-endpoint-portal-information"></a><span data-ttu-id="92efb-194">Información del portal de Microsoft Defender para puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="92efb-194">Microsoft Defender for Endpoint portal information</span></span>

<span data-ttu-id="92efb-195">[Las capacidades de EDR](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/edr-capabilities-for-macos-have-now-arrived/ba-p/1047801)para macOS ya han llegado, en el blog de Microsoft Defender para endpoints, proporciona instrucciones detalladas sobre lo que se espera en Microsoft Defender para endpoint Security Center.</span><span class="sxs-lookup"><span data-stu-id="92efb-195">[EDR capabilities for macOS have now arrived](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/edr-capabilities-for-macos-have-now-arrived/ba-p/1047801), on the Microsoft Defender for Endpoint blog, provides detailed guidance on what to expect in Microsoft Defender for Endpoint Security Center.</span></span>
