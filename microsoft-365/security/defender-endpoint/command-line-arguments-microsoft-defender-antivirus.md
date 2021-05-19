---
title: Use la línea de comandos para administrar Antivirus de Microsoft Defender
description: Ejecute Antivirus de Microsoft Defender y configure la protección de próxima generación con una utilidad de línea de comandos dedicada.
keywords: ejecutar el examen de Windows Defender, ejecutar el examen antivirus desde la línea de comandos, ejecutar el examen de Windows Defender desde la línea de comandos, mpcmdrun, defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ksarens
manager: dansimp
ms.date: 05/17/2021
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: eb7fa7fdf5b88bd9361176003817116bcbb1a087
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538908"
---
# <a name="configure-and-manage-microsoft-defender-antivirus-with-the-mpcmdrunexe-command-line-tool"></a><span data-ttu-id="f2b7d-104">Configurar y administrar Antivirus de Microsoft Defender con la mpcmdrun.exe de línea de comandos</span><span class="sxs-lookup"><span data-stu-id="f2b7d-104">Configure and manage Microsoft Defender Antivirus with the mpcmdrun.exe command-line tool</span></span>

<span data-ttu-id="f2b7d-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="f2b7d-105">**Applies to:**</span></span>

- [<span data-ttu-id="f2b7d-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="f2b7d-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="f2b7d-107">Puede realizar varias funciones Antivirus de Microsoft Defender con la herramienta de línea de comandos dedicada **mpcmdrun.exe**.</span><span class="sxs-lookup"><span data-stu-id="f2b7d-107">You can perform various Microsoft Defender Antivirus functions with the dedicated command-line tool **mpcmdrun.exe**.</span></span> <span data-ttu-id="f2b7d-108">Esta utilidad es útil cuando desea automatizar el Antivirus de Microsoft Defender uso.</span><span class="sxs-lookup"><span data-stu-id="f2b7d-108">This utility is useful when you want to automate Microsoft Defender Antivirus use.</span></span> <span data-ttu-id="f2b7d-109">Puede encontrar la utilidad en `%ProgramFiles%\Windows Defender\MpCmdRun.exe` .</span><span class="sxs-lookup"><span data-stu-id="f2b7d-109">You can find the utility in `%ProgramFiles%\Windows Defender\MpCmdRun.exe`.</span></span> <span data-ttu-id="f2b7d-110">Debe ejecutarlo desde un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="f2b7d-110">You must run it from a command prompt.</span></span>

> [!NOTE]
> <span data-ttu-id="f2b7d-111">Es posible que deba abrir una versión de nivel de administrador del símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="f2b7d-111">You might need to open an administrator-level version of the command prompt.</span></span> <span data-ttu-id="f2b7d-112">Cuando busque símbolo **del sistema en** el menú Inicio, elija Ejecutar como **administrador**.</span><span class="sxs-lookup"><span data-stu-id="f2b7d-112">When you search for **Command Prompt** on the Start menu, choose **Run as administrator**.</span></span>
> <span data-ttu-id="f2b7d-113">Si está ejecutando una versión actualizada de Microsoft Defender Platform, ejecute `**MpCmdRun**` desde la siguiente ubicación: `C:\ProgramData\Microsoft\Windows Defender\Platform\<antimalware platform version>` .</span><span class="sxs-lookup"><span data-stu-id="f2b7d-113">If you're running an updated Microsoft Defender Platform version, run `**MpCmdRun**` from the following location: `C:\ProgramData\Microsoft\Windows Defender\Platform\<antimalware platform version>`.</span></span>
> <span data-ttu-id="f2b7d-114">Para obtener más información acerca de la plataforma antimalware, [vea Antivirus de Microsoft Defender actualizaciones y líneas base](manage-updates-baselines-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="f2b7d-114">For more information about the antimalware platform, see [Microsoft Defender Antivirus updates and baselines](manage-updates-baselines-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="f2b7d-115">La utilidad MpCmdRun usa la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="f2b7d-115">The MpCmdRun utility uses the following syntax:</span></span>

```console
MpCmdRun.exe [command] [-options]
```

<span data-ttu-id="f2b7d-116">Aquí le mostramos un ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f2b7d-116">Here's an example:</span></span>

```console
MpCmdRun.exe -Scan -ScanType 2
``` 

| <span data-ttu-id="f2b7d-117">Comando</span><span class="sxs-lookup"><span data-stu-id="f2b7d-117">Command</span></span>  | <span data-ttu-id="f2b7d-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="f2b7d-118">Description</span></span>   |
|:----|:----|
| <span data-ttu-id="f2b7d-119">`-?`**o**`-h`</span><span class="sxs-lookup"><span data-stu-id="f2b7d-119">`-?` **or** `-h`</span></span>   | <span data-ttu-id="f2b7d-120">Muestra todas las opciones disponibles para esta herramienta</span><span class="sxs-lookup"><span data-stu-id="f2b7d-120">Displays all available options for this tool</span></span> |
| `-Scan [-ScanType [0\|1\|2\|3]] [-File <path> [-DisableRemediation] [-BootSectorScan] [-CpuThrottling]] [-Timeout <days>] [-Cancel]` | <span data-ttu-id="f2b7d-121">Busca software malintencionado.</span><span class="sxs-lookup"><span data-stu-id="f2b7d-121">Scans for malicious software.</span></span> <span data-ttu-id="f2b7d-122">Los valores **de ScanType** son:</span><span class="sxs-lookup"><span data-stu-id="f2b7d-122">Values for **ScanType** are:</span></span><p><span data-ttu-id="f2b7d-123">**0** Valor predeterminado, según la configuración</span><span class="sxs-lookup"><span data-stu-id="f2b7d-123">**0** Default, according to your configuration</span></span><p><span data-ttu-id="f2b7d-124">**-1** Examen rápido</span><span class="sxs-lookup"><span data-stu-id="f2b7d-124">**-1** Quick scan</span></span><p><span data-ttu-id="f2b7d-125">**-2** Examen completo</span><span class="sxs-lookup"><span data-stu-id="f2b7d-125">**-2** Full scan</span></span><p><span data-ttu-id="f2b7d-126">**-3** Examen personalizado de archivos y directorios.</span><span class="sxs-lookup"><span data-stu-id="f2b7d-126">**-3** File and directory custom scan.</span></span><p><span data-ttu-id="f2b7d-127">CpuThrottling respetará la limitación de CPU configurada desde la directiva</span><span class="sxs-lookup"><span data-stu-id="f2b7d-127">CpuThrottling will honor the configured CPU throttling from policy</span></span> |
| `-Trace [-Grouping #] [-Level #]` | <span data-ttu-id="f2b7d-128">Inicia el seguimiento de diagnóstico</span><span class="sxs-lookup"><span data-stu-id="f2b7d-128">Starts diagnostic tracing</span></span> |
| `-GetFiles [-SupportLogLocation <path>]` | <span data-ttu-id="f2b7d-129">Recopila información de soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="f2b7d-129">Collects support information.</span></span> <span data-ttu-id="f2b7d-130">Vea '[collecting diagnostic data](collect-diagnostic-data.md)'</span><span class="sxs-lookup"><span data-stu-id="f2b7d-130">See '[collecting diagnostic data](collect-diagnostic-data.md)'</span></span>  |
| `-GetFilesDiagTrack`  | <span data-ttu-id="f2b7d-131">Igual que `-GetFiles` , pero salidas a la carpeta temporal de DiagTrack</span><span class="sxs-lookup"><span data-stu-id="f2b7d-131">Same as `-GetFiles`, but outputs to temporary DiagTrack folder</span></span> |
| `-RemoveDefinitions [-All]` | <span data-ttu-id="f2b7d-132">Restaura la inteligencia de seguridad instalada a una copia de seguridad anterior o al conjunto predeterminado original</span><span class="sxs-lookup"><span data-stu-id="f2b7d-132">Restores the installed Security intelligence to a previous backup copy or to the original default set</span></span> |
| `-RemoveDefinitions [-DynamicSignatures]` | <span data-ttu-id="f2b7d-133">Quita solo la inteligencia de seguridad descargada dinámicamente</span><span class="sxs-lookup"><span data-stu-id="f2b7d-133">Removes only the dynamically downloaded Security intelligence</span></span> |
| `-RemoveDefinitions [-Engine]` | <span data-ttu-id="f2b7d-134">Restaura el motor instalado anterior</span><span class="sxs-lookup"><span data-stu-id="f2b7d-134">Restores the previous installed engine</span></span> |
| `-SignatureUpdate [-UNC \| -MMPC]` | <span data-ttu-id="f2b7d-135">Comprueba si hay nuevas actualizaciones de inteligencia de seguridad</span><span class="sxs-lookup"><span data-stu-id="f2b7d-135">Checks for new Security intelligence updates</span></span> |
| `-Restore  [-ListAll \| [[-Name <name>] [-All] \| [-FilePath <filePath>]] [-Path <path>]]` | <span data-ttu-id="f2b7d-136">Restaura o enumera elementos en cuarentena</span><span class="sxs-lookup"><span data-stu-id="f2b7d-136">Restores or lists quarantined item(s)</span></span> |
| `-AddDynamicSignature [-Path]` | <span data-ttu-id="f2b7d-137">Carga inteligencia de seguridad dinámica</span><span class="sxs-lookup"><span data-stu-id="f2b7d-137">Loads dynamic Security intelligence</span></span> |
| `-ListAllDynamicSignatures` | <span data-ttu-id="f2b7d-138">Enumera la inteligencia de seguridad dinámica cargada</span><span class="sxs-lookup"><span data-stu-id="f2b7d-138">Lists the loaded dynamic Security intelligence</span></span> |
| `-RemoveDynamicSignature [-SignatureSetID]` | <span data-ttu-id="f2b7d-139">Quita la inteligencia de seguridad dinámica</span><span class="sxs-lookup"><span data-stu-id="f2b7d-139">Removes dynamic Security intelligence</span></span> |
| `-CheckExclusion -path <path>` | <span data-ttu-id="f2b7d-140">Comprueba si se excluye una ruta de acceso</span><span class="sxs-lookup"><span data-stu-id="f2b7d-140">Checks whether a path is excluded</span></span> |
| `-ValidateMapsConnection` | <span data-ttu-id="f2b7d-141">Comprueba que la red se puede comunicar con el Antivirus de Microsoft Defender de nube.</span><span class="sxs-lookup"><span data-stu-id="f2b7d-141">Verifies that your network can communicate with the Microsoft Defender Antivirus cloud service.</span></span> <span data-ttu-id="f2b7d-142">Este comando solo funcionará en Windows 10 versión 1703 o posterior.</span><span class="sxs-lookup"><span data-stu-id="f2b7d-142">This command will only work on Windows 10, version 1703 or higher.</span></span>|


## <a name="common-errors-in-running-commands-via-mpcmdrunexe"></a><span data-ttu-id="f2b7d-143">Errores comunes al ejecutar comandos mediante mpcmdrun.exe</span><span class="sxs-lookup"><span data-stu-id="f2b7d-143">Common errors in running commands via mpcmdrun.exe</span></span> 

|<span data-ttu-id="f2b7d-144">Mensaje de error</span><span class="sxs-lookup"><span data-stu-id="f2b7d-144">Error message</span></span> | <span data-ttu-id="f2b7d-145">Posible motivo</span><span class="sxs-lookup"><span data-stu-id="f2b7d-145">Possible reason</span></span>
|:----|:----|
| `ValidateMapsConnection failed (800106BA) or 0x800106BA` | <span data-ttu-id="f2b7d-146">El Antivirus de Microsoft Defender está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="f2b7d-146">The Microsoft Defender Antivirus service is disabled.</span></span> <span data-ttu-id="f2b7d-147">Habilite el servicio e inténtelo de nuevo.</span><span class="sxs-lookup"><span data-stu-id="f2b7d-147">Enable the service and try again.</span></span> <br>   <span data-ttu-id="f2b7d-148">**Nota:**  En Windows 10 1909 o versiones anteriores, y Windows Server 2019 o versiones anteriores, el servicio se llamaba servicio Antivirus de Windows Defender *anterior.*</span><span class="sxs-lookup"><span data-stu-id="f2b7d-148">**Note:**  In Windows 10 1909 or older, and Windows Server 2019 or older, the service used to be called the *Windows Defender Antivirus* service.</span></span>|
| `0x80070667` | <span data-ttu-id="f2b7d-149">Está ejecutando el comando desde un equipo que Windows 10 versión 1607 o anterior, o Windows Server 2016 `-ValidateMapsConnection` o posterior.</span><span class="sxs-lookup"><span data-stu-id="f2b7d-149">You're running the `-ValidateMapsConnection` command from a computer that is Windows 10 version 1607 or older, or Windows Server 2016 or older.</span></span> <span data-ttu-id="f2b7d-150">Ejecute el comando desde un equipo que Windows 10 versión 1703 o posterior, o Windows Server 2019 o posterior.</span><span class="sxs-lookup"><span data-stu-id="f2b7d-150">Run the command from a machine that is Windows 10 version 1703 or newer, or Windows Server 2019 or newer.</span></span>|
| `'MpCmdRun' is not recognized as an internal or external command, operable program or batch file.` | <span data-ttu-id="f2b7d-151">La herramienta debe ejecutarse desde: o (donde puede diferir dado que las actualizaciones de la plataforma `%ProgramFiles%\Windows Defender` `C:\ProgramData\Microsoft\Windows Defender\Platform\4.18.2012.4-0` son `2012.4-0` mensuales excepto marzo)</span><span class="sxs-lookup"><span data-stu-id="f2b7d-151">The tool needs to be run from either: `%ProgramFiles%\Windows Defender` or `C:\ProgramData\Microsoft\Windows Defender\Platform\4.18.2012.4-0` (where `2012.4-0` might differ since platform updates are monthly except for March)</span></span>|
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80070005 httpcode=450)` | <span data-ttu-id="f2b7d-152">No hay suficientes privilegios.</span><span class="sxs-lookup"><span data-stu-id="f2b7d-152">Not enough privileges.</span></span> <span data-ttu-id="f2b7d-153">Use el símbolo del sistema (cmd.exe) como administrador.</span><span class="sxs-lookup"><span data-stu-id="f2b7d-153">Use the command prompt (cmd.exe) as an administrator.</span></span>|
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80070006 httpcode=451)` | <span data-ttu-id="f2b7d-154">El firewall bloquea la conexión o realiza una inspección SSL.</span><span class="sxs-lookup"><span data-stu-id="f2b7d-154">The firewall is blocking the connection or conducting SSL inspection.</span></span> |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80004005 httpcode=450)` | <span data-ttu-id="f2b7d-155">Posibles problemas relacionados con la red, como problemas de resolución de nombres</span><span class="sxs-lookup"><span data-stu-id="f2b7d-155">Possible network-related issues, like name resolution problems</span></span>|
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=0x80508015` | <span data-ttu-id="f2b7d-156">El firewall bloquea la conexión o realiza una inspección SSL.</span><span class="sxs-lookup"><span data-stu-id="f2b7d-156">The firewall is blocking the connection or conducting SSL inspection.</span></span> |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=800722F0D` | <span data-ttu-id="f2b7d-157">El firewall bloquea la conexión o realiza una inspección SSL.</span><span class="sxs-lookup"><span data-stu-id="f2b7d-157">The firewall is blocking the connection or conducting SSL inspection.</span></span> |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80072EE7 httpcode=451)` | <span data-ttu-id="f2b7d-158">El firewall bloquea la conexión o realiza una inspección SSL.</span><span class="sxs-lookup"><span data-stu-id="f2b7d-158">The firewall is blocking the connection or conducting SSL inspection.</span></span> |

## <a name="see-also"></a><span data-ttu-id="f2b7d-159">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f2b7d-159">See also</span></span>

- [<span data-ttu-id="f2b7d-160">Configurar las funciones del Antivirus de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="f2b7d-160">Configure Microsoft Defender Antivirus features</span></span>](configure-microsoft-defender-antivirus-features.md)
- [<span data-ttu-id="f2b7d-161">Administrar Antivirus de Microsoft Defender en su empresa</span><span class="sxs-lookup"><span data-stu-id="f2b7d-161">Manage Microsoft Defender Antivirus in your business</span></span>](configuration-management-reference-microsoft-defender-antivirus.md)
- [<span data-ttu-id="f2b7d-162">Temas de referencia para herramientas de administración y configuración</span><span class="sxs-lookup"><span data-stu-id="f2b7d-162">Reference topics for management and configuration tools</span></span>](configuration-management-reference-microsoft-defender-antivirus.md)
- [<span data-ttu-id="f2b7d-163">Antivirus de Microsoft Defender en Windows 10</span><span class="sxs-lookup"><span data-stu-id="f2b7d-163">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)