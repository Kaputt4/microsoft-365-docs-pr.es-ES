---
title: Recursos de Microsoft Defender para endpoint en Linux
ms.reviewer: ''
description: Describe recursos para Microsoft Defender para Endpoint en Linux, como cómo desinstalarlo, cómo recopilar registros de diagnóstico, comandos cli y problemas conocidos con el producto.
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
ms.openlocfilehash: 176ee89c8d60a1515855296e2565f0649f908a33
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933330"
---
# <a name="resources"></a><span data-ttu-id="6caab-104">Recursos</span><span class="sxs-lookup"><span data-stu-id="6caab-104">Resources</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="6caab-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="6caab-105">**Applies to:**</span></span>
- [<span data-ttu-id="6caab-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="6caab-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="6caab-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6caab-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="6caab-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="6caab-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="6caab-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="6caab-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="collect-diagnostic-information"></a><span data-ttu-id="6caab-110">Recopilar información de diagnóstico</span><span class="sxs-lookup"><span data-stu-id="6caab-110">Collect diagnostic information</span></span>

<span data-ttu-id="6caab-111">Si puede reproducir un problema, aumente primero el nivel de registro, ejecute el sistema durante algún tiempo y, a continuación, restaure el nivel de registro en el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="6caab-111">If you can reproduce a problem, first increase the logging level, run the system for some time, and then restore the logging level to the default.</span></span>

1. <span data-ttu-id="6caab-112">Aumentar el nivel de registro:</span><span class="sxs-lookup"><span data-stu-id="6caab-112">Increase logging level:</span></span>

   ```bash
   mdatp log level set --level debug
   ```

   ```Output
   Log level configured successfully
   ```

2. <span data-ttu-id="6caab-113">Reproduce el problema.</span><span class="sxs-lookup"><span data-stu-id="6caab-113">Reproduce the problem.</span></span>

3. <span data-ttu-id="6caab-114">Ejecute el siguiente comando para realizar una copia de seguridad de Defender para los registros del extremo.</span><span class="sxs-lookup"><span data-stu-id="6caab-114">Run the following command to back up Defender for Endpoint's logs.</span></span> <span data-ttu-id="6caab-115">Los archivos se almacenarán dentro de un .zip archivo.</span><span class="sxs-lookup"><span data-stu-id="6caab-115">The files will be stored inside of a .zip archive.</span></span>

   ```bash
   sudo mdatp diagnostic create
   ```

    <span data-ttu-id="6caab-116">Este comando también imprimirá la ruta de acceso del archivo a la copia de seguridad después de que la operación se realice correctamente:</span><span class="sxs-lookup"><span data-stu-id="6caab-116">This command will also print out the file path to the backup after the operation succeeds:</span></span>

   ```Output
   Diagnostic file created: <path to file>
   ```

4. <span data-ttu-id="6caab-117">Restaurar nivel de registro:</span><span class="sxs-lookup"><span data-stu-id="6caab-117">Restore logging level:</span></span>

   ```bash
   mdatp log level set --level info
   ```
   ```Output
   Log level configured successfully
   ```

## <a name="log-installation-issues"></a><span data-ttu-id="6caab-118">Problemas de instalación del registro</span><span class="sxs-lookup"><span data-stu-id="6caab-118">Log installation issues</span></span>

<span data-ttu-id="6caab-119">Si se produce un error durante la instalación, el instalador solo informará de un error general.</span><span class="sxs-lookup"><span data-stu-id="6caab-119">If an error occurs during installation, the installer will only report a general failure.</span></span>

<span data-ttu-id="6caab-120">El registro detallado se guardará en `/var/log/microsoft/mdatp_install.log` .</span><span class="sxs-lookup"><span data-stu-id="6caab-120">The detailed log will be saved to `/var/log/microsoft/mdatp_install.log`.</span></span> <span data-ttu-id="6caab-121">Si tiene problemas durante la instalación, envíenos este archivo para que podamos diagnosticar la causa.</span><span class="sxs-lookup"><span data-stu-id="6caab-121">If you experience issues during installation, send us this file so we can help diagnose the cause.</span></span>

## <a name="uninstall"></a><span data-ttu-id="6caab-122">Desinstalar</span><span class="sxs-lookup"><span data-stu-id="6caab-122">Uninstall</span></span>

<span data-ttu-id="6caab-123">Hay varias maneras de desinstalar Defender for Endpoint en Linux.</span><span class="sxs-lookup"><span data-stu-id="6caab-123">There are several ways to uninstall Defender for Endpoint on Linux.</span></span> <span data-ttu-id="6caab-124">Si usa una herramienta de configuración como Puppet, siga las instrucciones de desinstalación del paquete para la herramienta de configuración.</span><span class="sxs-lookup"><span data-stu-id="6caab-124">If you are using a configuration tool such as Puppet, follow the package uninstallation instructions for the configuration tool.</span></span>

### <a name="manual-uninstallation"></a><span data-ttu-id="6caab-125">Desinstalación manual</span><span class="sxs-lookup"><span data-stu-id="6caab-125">Manual uninstallation</span></span>

- <span data-ttu-id="6caab-126">`sudo yum remove mdatp` para RHEL y variantes (CentOS y Oracle Linux).</span><span class="sxs-lookup"><span data-stu-id="6caab-126">`sudo yum remove mdatp` for RHEL and variants(CentOS and Oracle Linux).</span></span>
- <span data-ttu-id="6caab-127">`sudo zypper remove mdatp` para SLES y variantes.</span><span class="sxs-lookup"><span data-stu-id="6caab-127">`sudo zypper remove mdatp` for SLES and variants.</span></span>
- <span data-ttu-id="6caab-128">`sudo apt-get purge mdatp` para sistemas Ubuntu y Debian.</span><span class="sxs-lookup"><span data-stu-id="6caab-128">`sudo apt-get purge mdatp` for Ubuntu and Debian systems.</span></span>

## <a name="configure-from-the-command-line"></a><span data-ttu-id="6caab-129">Configurar desde la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="6caab-129">Configure from the command line</span></span>

<span data-ttu-id="6caab-130">Las tareas importantes, como controlar la configuración del producto y desencadenar exámenes a petición, se pueden realizar desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="6caab-130">Important tasks, such as controlling product settings and triggering on-demand scans, can be done from the command line.</span></span>

### <a name="global-options"></a><span data-ttu-id="6caab-131">Opciones globales</span><span class="sxs-lookup"><span data-stu-id="6caab-131">Global options</span></span>

<span data-ttu-id="6caab-132">De forma predeterminada, la herramienta de línea de comandos genera el resultado en formato legible.</span><span class="sxs-lookup"><span data-stu-id="6caab-132">By default, the command-line tool outputs the result in human-readable format.</span></span> <span data-ttu-id="6caab-133">Además, la herramienta también admite la salida del resultado como JSON, lo que resulta útil para escenarios de automatización.</span><span class="sxs-lookup"><span data-stu-id="6caab-133">In addition, the tool also supports outputting the result as JSON, which is useful for automation scenarios.</span></span> <span data-ttu-id="6caab-134">Para cambiar el resultado a JSON, pase `--output json` a cualquiera de los comandos siguientes.</span><span class="sxs-lookup"><span data-stu-id="6caab-134">To change the output to JSON, pass `--output json` to any of the below commands.</span></span>

### <a name="supported-commands"></a><span data-ttu-id="6caab-135">Comandos admitidos</span><span class="sxs-lookup"><span data-stu-id="6caab-135">Supported commands</span></span>

<span data-ttu-id="6caab-136">En la tabla siguiente se enumeran los comandos de algunos de los escenarios más comunes.</span><span class="sxs-lookup"><span data-stu-id="6caab-136">The following table lists commands for some of the most common scenarios.</span></span> <span data-ttu-id="6caab-137">Ejecute `mdatp help` desde terminal para ver la lista completa de comandos admitidos.</span><span class="sxs-lookup"><span data-stu-id="6caab-137">Run `mdatp help` from the Terminal to view the full list of supported commands.</span></span>

|<span data-ttu-id="6caab-138">Group</span><span class="sxs-lookup"><span data-stu-id="6caab-138">Group</span></span>                 |<span data-ttu-id="6caab-139">Escenario</span><span class="sxs-lookup"><span data-stu-id="6caab-139">Scenario</span></span>                                                |<span data-ttu-id="6caab-140">Comando</span><span class="sxs-lookup"><span data-stu-id="6caab-140">Command</span></span>                                                                |
|----------------------|--------------------------------------------------------|-----------------------------------------------------------------------|
|<span data-ttu-id="6caab-141">Configuración</span><span class="sxs-lookup"><span data-stu-id="6caab-141">Configuration</span></span>         |<span data-ttu-id="6caab-142">Activar/desactivar la protección en tiempo real</span><span class="sxs-lookup"><span data-stu-id="6caab-142">Turn on/off real-time protection</span></span>                        |`mdatp config real-time-protection --value [enabled\|disabled]`        |
|<span data-ttu-id="6caab-143">Configuración</span><span class="sxs-lookup"><span data-stu-id="6caab-143">Configuration</span></span>         |<span data-ttu-id="6caab-144">Activar/desactivar la supervisión del comportamiento</span><span class="sxs-lookup"><span data-stu-id="6caab-144">Turn on/off behavior monitoring</span></span>                         |`mdatp config behavior-monitoring --value [enabled\|disabled]` 
|<span data-ttu-id="6caab-145">Configuración</span><span class="sxs-lookup"><span data-stu-id="6caab-145">Configuration</span></span>         |<span data-ttu-id="6caab-146">Activar/desactivar la protección en la nube</span><span class="sxs-lookup"><span data-stu-id="6caab-146">Turn on/off cloud protection</span></span>                            |`mdatp config cloud --value [enabled\|disabled]`                       |
|<span data-ttu-id="6caab-147">Configuración</span><span class="sxs-lookup"><span data-stu-id="6caab-147">Configuration</span></span>         |<span data-ttu-id="6caab-148">Activar/desactivar diagnósticos de productos</span><span class="sxs-lookup"><span data-stu-id="6caab-148">Turn on/off product diagnostics</span></span>                         |`mdatp config cloud-diagnostic --value [enabled\|disabled]`            |
|<span data-ttu-id="6caab-149">Configuración</span><span class="sxs-lookup"><span data-stu-id="6caab-149">Configuration</span></span>         |<span data-ttu-id="6caab-150">Activar/desactivar el envío automático de muestra</span><span class="sxs-lookup"><span data-stu-id="6caab-150">Turn on/off automatic sample submission</span></span>                 |`mdatp config cloud-automatic-sample-submission [enabled\|disabled]`   |
|<span data-ttu-id="6caab-151">Configuración</span><span class="sxs-lookup"><span data-stu-id="6caab-151">Configuration</span></span>         |<span data-ttu-id="6caab-152">Activar/desactivar el modo pasivo de AV</span><span class="sxs-lookup"><span data-stu-id="6caab-152">Turn on/off AV passive mode</span></span>                             |`mdatp config passive-mode --value [enabled\|disabled]`                |
|<span data-ttu-id="6caab-153">Configuración</span><span class="sxs-lookup"><span data-stu-id="6caab-153">Configuration</span></span>         |<span data-ttu-id="6caab-154">Agregar o quitar una exclusión antivirus para una extensión de archivo</span><span class="sxs-lookup"><span data-stu-id="6caab-154">Add/remove an antivirus exclusion for a file extension</span></span>  |`mdatp exclusion extension [add\|remove] --name [extension]`           |
|<span data-ttu-id="6caab-155">Configuración</span><span class="sxs-lookup"><span data-stu-id="6caab-155">Configuration</span></span>         |<span data-ttu-id="6caab-156">Agregar o quitar una exclusión antivirus para un archivo</span><span class="sxs-lookup"><span data-stu-id="6caab-156">Add/remove an antivirus exclusion for a file</span></span>            |`mdatp exclusion file [add\|remove] --path [path-to-file]`             |
|<span data-ttu-id="6caab-157">Configuración</span><span class="sxs-lookup"><span data-stu-id="6caab-157">Configuration</span></span>         |<span data-ttu-id="6caab-158">Agregar o quitar una exclusión antivirus para un directorio</span><span class="sxs-lookup"><span data-stu-id="6caab-158">Add/remove an antivirus exclusion for a directory</span></span>       |`mdatp exclusion folder [add\|remove] --path [path-to-directory]`      |
|<span data-ttu-id="6caab-159">Configuración</span><span class="sxs-lookup"><span data-stu-id="6caab-159">Configuration</span></span>         |<span data-ttu-id="6caab-160">Agregar o quitar una exclusión antivirus para un proceso</span><span class="sxs-lookup"><span data-stu-id="6caab-160">Add/remove an antivirus exclusion for a process</span></span>         |`mdatp exclusion process [add\|remove] --path [path-to-process]`<br/>`mdatp exclusion process [add\|remove] --name [process-name]` |
|<span data-ttu-id="6caab-161">Configuración</span><span class="sxs-lookup"><span data-stu-id="6caab-161">Configuration</span></span>         |<span data-ttu-id="6caab-162">Enumerar todas las exclusiones de antivirus</span><span class="sxs-lookup"><span data-stu-id="6caab-162">List all antivirus exclusions</span></span>                           |`mdatp exclusion list`                                                 |
|<span data-ttu-id="6caab-163">Configuración</span><span class="sxs-lookup"><span data-stu-id="6caab-163">Configuration</span></span>         |<span data-ttu-id="6caab-164">Agregar un nombre de amenaza a la lista permitida</span><span class="sxs-lookup"><span data-stu-id="6caab-164">Add a threat name to the allowed list</span></span>                   |`mdatp threat allowed add --name [threat-name]`                        |
|<span data-ttu-id="6caab-165">Configuración</span><span class="sxs-lookup"><span data-stu-id="6caab-165">Configuration</span></span>         |<span data-ttu-id="6caab-166">Quitar un nombre de amenaza de la lista permitida</span><span class="sxs-lookup"><span data-stu-id="6caab-166">Remove a threat name from the allowed list</span></span>              |`mdatp threat allowed remove --name [threat-name]`                     |
|<span data-ttu-id="6caab-167">Configuración</span><span class="sxs-lookup"><span data-stu-id="6caab-167">Configuration</span></span>         |<span data-ttu-id="6caab-168">Enumerar todos los nombres de amenazas permitidos</span><span class="sxs-lookup"><span data-stu-id="6caab-168">List all allowed threat names</span></span>                           |`mdatp threat allowed list`                                            |
|<span data-ttu-id="6caab-169">Configuración</span><span class="sxs-lookup"><span data-stu-id="6caab-169">Configuration</span></span>         |<span data-ttu-id="6caab-170">Activar la protección de LA PUA</span><span class="sxs-lookup"><span data-stu-id="6caab-170">Turn on PUA protection</span></span>                                  |`mdatp threat policy set --type potentially_unwanted_application --action block` |
|<span data-ttu-id="6caab-171">Configuración</span><span class="sxs-lookup"><span data-stu-id="6caab-171">Configuration</span></span>         |<span data-ttu-id="6caab-172">Desactivar la protección de LA PUA</span><span class="sxs-lookup"><span data-stu-id="6caab-172">Turn off PUA protection</span></span>                                 |`mdatp threat policy set --type potentially_unwanted_application --action off` |
|<span data-ttu-id="6caab-173">Configuración</span><span class="sxs-lookup"><span data-stu-id="6caab-173">Configuration</span></span>         |<span data-ttu-id="6caab-174">Activar el modo de auditoría para la protección de PUA</span><span class="sxs-lookup"><span data-stu-id="6caab-174">Turn on audit mode for PUA protection</span></span>                   |`mdatp threat policy set --type potentially_unwanted_application --action audit` |
|<span data-ttu-id="6caab-175">Diagnostics</span><span class="sxs-lookup"><span data-stu-id="6caab-175">Diagnostics</span></span>           |<span data-ttu-id="6caab-176">Cambiar el nivel de registro</span><span class="sxs-lookup"><span data-stu-id="6caab-176">Change the log level</span></span>                                    |`mdatp log level set --level verbose [error|warning|info|verbose]`     |
|<span data-ttu-id="6caab-177">Diagnostics</span><span class="sxs-lookup"><span data-stu-id="6caab-177">Diagnostics</span></span>           |<span data-ttu-id="6caab-178">Generar registros de diagnóstico</span><span class="sxs-lookup"><span data-stu-id="6caab-178">Generate diagnostic logs</span></span>                                |`mdatp diagnostic create --path [directory]`                           |
|<span data-ttu-id="6caab-179">Salud</span><span class="sxs-lookup"><span data-stu-id="6caab-179">Health</span></span>                |<span data-ttu-id="6caab-180">Comprobar el estado del producto</span><span class="sxs-lookup"><span data-stu-id="6caab-180">Check the product's health</span></span>                              |`mdatp health`                                                         |
|<span data-ttu-id="6caab-181">Protección</span><span class="sxs-lookup"><span data-stu-id="6caab-181">Protection</span></span>            |<span data-ttu-id="6caab-182">Examinar una ruta de acceso</span><span class="sxs-lookup"><span data-stu-id="6caab-182">Scan a path</span></span>                                             |`mdatp scan custom --path [path] [--ignore-exclusions]`                |
|<span data-ttu-id="6caab-183">Protección</span><span class="sxs-lookup"><span data-stu-id="6caab-183">Protection</span></span>            |<span data-ttu-id="6caab-184">Realizar un examen rápido</span><span class="sxs-lookup"><span data-stu-id="6caab-184">Do a quick scan</span></span>                                         |`mdatp scan quick`                                                     |
|<span data-ttu-id="6caab-185">Protección</span><span class="sxs-lookup"><span data-stu-id="6caab-185">Protection</span></span>            |<span data-ttu-id="6caab-186">Realizar un examen completo</span><span class="sxs-lookup"><span data-stu-id="6caab-186">Do a full scan</span></span>                                          |`mdatp scan full`                                                      |
|<span data-ttu-id="6caab-187">Protección</span><span class="sxs-lookup"><span data-stu-id="6caab-187">Protection</span></span>            |<span data-ttu-id="6caab-188">Cancelar un examen a petición en curso</span><span class="sxs-lookup"><span data-stu-id="6caab-188">Cancel an ongoing on-demand scan</span></span>                        |`mdatp scan cancel`                                                    |
|<span data-ttu-id="6caab-189">Protección</span><span class="sxs-lookup"><span data-stu-id="6caab-189">Protection</span></span>            |<span data-ttu-id="6caab-190">Solicitar una actualización de inteligencia de seguridad</span><span class="sxs-lookup"><span data-stu-id="6caab-190">Request a security intelligence update</span></span>                  |`mdatp definitions update`                                             |
|<span data-ttu-id="6caab-191">Historial de protección</span><span class="sxs-lookup"><span data-stu-id="6caab-191">Protection history</span></span>    |<span data-ttu-id="6caab-192">Imprimir el historial de protección completo</span><span class="sxs-lookup"><span data-stu-id="6caab-192">Print the full protection history</span></span>                       |`mdatp threat list`                                                    |
|<span data-ttu-id="6caab-193">Historial de protección</span><span class="sxs-lookup"><span data-stu-id="6caab-193">Protection history</span></span>    |<span data-ttu-id="6caab-194">Obtener detalles de amenazas</span><span class="sxs-lookup"><span data-stu-id="6caab-194">Get threat details</span></span>                                      |`mdatp threat get --id [threat-id]`                                    |
|<span data-ttu-id="6caab-195">Administración de cuarentena</span><span class="sxs-lookup"><span data-stu-id="6caab-195">Quarantine management</span></span> |<span data-ttu-id="6caab-196">Enumerar todos los archivos en cuarentena</span><span class="sxs-lookup"><span data-stu-id="6caab-196">List all quarantined files</span></span>                              |`mdatp threat quarantine list`                                         |
|<span data-ttu-id="6caab-197">Administración de cuarentena</span><span class="sxs-lookup"><span data-stu-id="6caab-197">Quarantine management</span></span> |<span data-ttu-id="6caab-198">Quitar todos los archivos de la cuarentena</span><span class="sxs-lookup"><span data-stu-id="6caab-198">Remove all files from the quarantine</span></span>                    |`mdatp threat quarantine remove-all`                                   |
|<span data-ttu-id="6caab-199">Administración de cuarentena</span><span class="sxs-lookup"><span data-stu-id="6caab-199">Quarantine management</span></span> |<span data-ttu-id="6caab-200">Agregar un archivo detectado como una amenaza a la cuarentena</span><span class="sxs-lookup"><span data-stu-id="6caab-200">Add a file detected as a threat to the quarantine</span></span>       |`mdatp threat quarantine add --id [threat-id]`                         |
|<span data-ttu-id="6caab-201">Administración de cuarentena</span><span class="sxs-lookup"><span data-stu-id="6caab-201">Quarantine management</span></span> |<span data-ttu-id="6caab-202">Quitar un archivo detectado como una amenaza de la cuarentena</span><span class="sxs-lookup"><span data-stu-id="6caab-202">Remove a file detected as a threat from the quarantine</span></span>  |`mdatp threat quarantine remove --id [threat-id]`                      |
|<span data-ttu-id="6caab-203">Administración de cuarentena</span><span class="sxs-lookup"><span data-stu-id="6caab-203">Quarantine management</span></span> |<span data-ttu-id="6caab-204">Restaurar un archivo desde la cuarentena</span><span class="sxs-lookup"><span data-stu-id="6caab-204">Restore a file from the quarantine</span></span>                      |`mdatp threat quarantine restore --id [threat-id]`                     |
|<span data-ttu-id="6caab-205">Detección y respuesta de extremos</span><span class="sxs-lookup"><span data-stu-id="6caab-205">Endpoint Detection and Response</span></span> |<span data-ttu-id="6caab-206">Establecer la vista previa anticipada (sin usar)</span><span class="sxs-lookup"><span data-stu-id="6caab-206">Set early preview (unused)</span></span>                    |`mdatp edr early-preview [enable|disable]`                             |
|<span data-ttu-id="6caab-207">Detección y respuesta de extremos</span><span class="sxs-lookup"><span data-stu-id="6caab-207">Endpoint Detection and Response</span></span> |<span data-ttu-id="6caab-208">Establecer group-id</span><span class="sxs-lookup"><span data-stu-id="6caab-208">Set group-id</span></span>                                  |`mdatp edr group-ids --group-id [group-id]`                            |
|<span data-ttu-id="6caab-209">Detección y respuesta de extremos</span><span class="sxs-lookup"><span data-stu-id="6caab-209">Endpoint Detection and Response</span></span> |<span data-ttu-id="6caab-210">Establecer o quitar etiqueta, solo `GROUP` compatible</span><span class="sxs-lookup"><span data-stu-id="6caab-210">Set/Remove tag, only `GROUP` supported</span></span>        |`mdatp edr tag set --name GROUP --value [tag]`                         |
|<span data-ttu-id="6caab-211">Detección y respuesta de extremos</span><span class="sxs-lookup"><span data-stu-id="6caab-211">Endpoint Detection and Response</span></span> |<span data-ttu-id="6caab-212">exclusiones de lista (raíz)</span><span class="sxs-lookup"><span data-stu-id="6caab-212">list exclusions (root)</span></span>                        |`mdatp edr exclusion list [processes|paths|extensions|all]`            |

## <a name="microsoft-defender-for-endpoint-portal-information"></a><span data-ttu-id="6caab-213">Información del portal de Microsoft Defender para puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="6caab-213">Microsoft Defender for Endpoint portal information</span></span>

<span data-ttu-id="6caab-214">En el portal de Defender para endpoint, verá dos categorías de información:</span><span class="sxs-lookup"><span data-stu-id="6caab-214">In the Defender for Endpoint portal, you'll see two categories of information:</span></span>

- <span data-ttu-id="6caab-215">Alertas antivirus, incluidas:</span><span class="sxs-lookup"><span data-stu-id="6caab-215">Antivirus alerts, including:</span></span>
  - <span data-ttu-id="6caab-216">Gravedad</span><span class="sxs-lookup"><span data-stu-id="6caab-216">Severity</span></span>
  - <span data-ttu-id="6caab-217">Tipo de examen</span><span class="sxs-lookup"><span data-stu-id="6caab-217">Scan type</span></span>
  - <span data-ttu-id="6caab-218">Información del dispositivo (nombre de host, identificador de dispositivo, identificador de inquilino, versión de aplicación y tipo de sistema operativo)</span><span class="sxs-lookup"><span data-stu-id="6caab-218">Device information (hostname, device identifier, tenant identifier, app version, and OS type)</span></span>
  - <span data-ttu-id="6caab-219">Información de archivo (nombre, ruta de acceso, tamaño y hash)</span><span class="sxs-lookup"><span data-stu-id="6caab-219">File information (name, path, size, and hash)</span></span>
  - <span data-ttu-id="6caab-220">Información sobre amenazas (nombre, tipo y estado)</span><span class="sxs-lookup"><span data-stu-id="6caab-220">Threat information (name, type, and state)</span></span>
- <span data-ttu-id="6caab-221">Información del dispositivo, incluida:</span><span class="sxs-lookup"><span data-stu-id="6caab-221">Device information, including:</span></span>
  - <span data-ttu-id="6caab-222">Identificador de dispositivo</span><span class="sxs-lookup"><span data-stu-id="6caab-222">Device identifier</span></span>
  - <span data-ttu-id="6caab-223">Identificador de inquilino</span><span class="sxs-lookup"><span data-stu-id="6caab-223">Tenant identifier</span></span>
  - <span data-ttu-id="6caab-224">Versión de la aplicación</span><span class="sxs-lookup"><span data-stu-id="6caab-224">App version</span></span>
  - <span data-ttu-id="6caab-225">Nombre de host</span><span class="sxs-lookup"><span data-stu-id="6caab-225">Hostname</span></span>
  - <span data-ttu-id="6caab-226">Tipo de sistema operativo</span><span class="sxs-lookup"><span data-stu-id="6caab-226">OS type</span></span>
  - <span data-ttu-id="6caab-227">Versión del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="6caab-227">OS version</span></span>
  - <span data-ttu-id="6caab-228">Modelo de equipo</span><span class="sxs-lookup"><span data-stu-id="6caab-228">Computer model</span></span>
  - <span data-ttu-id="6caab-229">Arquitectura del procesador</span><span class="sxs-lookup"><span data-stu-id="6caab-229">Processor architecture</span></span>
  - <span data-ttu-id="6caab-230">Si el dispositivo es una máquina virtual</span><span class="sxs-lookup"><span data-stu-id="6caab-230">Whether the device is a virtual machine</span></span>

### <a name="known-issues"></a><span data-ttu-id="6caab-231">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="6caab-231">Known issues</span></span>

- <span data-ttu-id="6caab-232">Es posible que vea "Sin datos de sensor, comunicaciones deficientes" en la página de información de la máquina del portal de Centro de seguridad de Microsoft Defender, aunque el producto funciona como se esperaba.</span><span class="sxs-lookup"><span data-stu-id="6caab-232">You might see "No sensor data, impaired communications" in the machine information page of the Microsoft Defender Security Center portal, even though the product is working as expected.</span></span> <span data-ttu-id="6caab-233">Estamos trabajando en solucionar este problema.</span><span class="sxs-lookup"><span data-stu-id="6caab-233">We are working on addressing this issue.</span></span>
- <span data-ttu-id="6caab-234">Los usuarios que han iniciado sesión no aparecen en Centro de seguridad de Microsoft Defender portal.</span><span class="sxs-lookup"><span data-stu-id="6caab-234">Logged on users do not appear in the Microsoft Defender Security Center portal.</span></span>
- <span data-ttu-id="6caab-235">En las distribuciones de SUSE, si se produce un error en la instalación de *libatomic1,* debe validar que el sistema operativo está registrado:</span><span class="sxs-lookup"><span data-stu-id="6caab-235">In SUSE distributions, if the installation of *libatomic1* fails, you should validate that your OS is registered:</span></span>

   ```bash
   sudo SUSEConnect --status-text
   ```
