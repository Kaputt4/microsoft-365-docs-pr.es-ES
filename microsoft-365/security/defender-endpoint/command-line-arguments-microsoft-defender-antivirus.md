---
title: Usar la línea de comandos para administrar Antivirus de Microsoft Defender
description: Ejecute los exámenes de Antivirus de Microsoft Defender y configure la protección de próxima generación con una utilidad de línea de comandos dedicada.
keywords: ejecutar el examen de Windows Defender, ejecutar el examen antivirus desde la línea de comandos, ejecutar el examen de Windows Defender desde la línea de comandos, mpcmdrun, defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ksarens
manager: dansimp
ms.date: 03/19/2021
ms.technology: mde
ms.openlocfilehash: 2b20227ac27b90d142d263dfa4522aa41319b9d5
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691085"
---
# <a name="configure-and-manage-microsoft-defender-antivirus-with-the-mpcmdrunexe-command-line-tool"></a><span data-ttu-id="1b72e-104">Configurar y administrar Antivirus de Microsoft Defender con la mpcmdrun.exe de línea de comandos</span><span class="sxs-lookup"><span data-stu-id="1b72e-104">Configure and manage Microsoft Defender Antivirus with the mpcmdrun.exe command-line tool</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="1b72e-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="1b72e-105">**Applies to:**</span></span>

- [<span data-ttu-id="1b72e-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="1b72e-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="1b72e-107">Puede realizar varias funciones de Antivirus de Microsoft Defender con la herramienta de línea de comandos dedicada **mpcmdrun.exe**.</span><span class="sxs-lookup"><span data-stu-id="1b72e-107">You can perform various Microsoft Defender Antivirus functions with the dedicated command-line tool **mpcmdrun.exe**.</span></span> <span data-ttu-id="1b72e-108">Esta utilidad es útil cuando desea automatizar el uso de Antivirus de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="1b72e-108">This utility is useful when you want to automate Microsoft Defender Antivirus use.</span></span> <span data-ttu-id="1b72e-109">Puede encontrar la utilidad en `%ProgramFiles%\Windows Defender\MpCmdRun.exe` .</span><span class="sxs-lookup"><span data-stu-id="1b72e-109">You can find the utility in `%ProgramFiles%\Windows Defender\MpCmdRun.exe`.</span></span> <span data-ttu-id="1b72e-110">Debe ejecutarlo desde un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="1b72e-110">You must run it from a command prompt.</span></span>

> [!NOTE]
> <span data-ttu-id="1b72e-111">Es posible que deba abrir una versión de nivel de administrador del símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="1b72e-111">You might need to open an administrator-level version of the command prompt.</span></span> <span data-ttu-id="1b72e-112">Cuando busque símbolo **del sistema en** el menú Inicio, elija Ejecutar como **administrador**.</span><span class="sxs-lookup"><span data-stu-id="1b72e-112">When you search for **Command Prompt** on the Start menu, choose **Run as administrator**.</span></span>
> <span data-ttu-id="1b72e-113">Si está ejecutando una versión actualizada de Microsoft Defender Platform, ejecute `**MpCmdRun**` desde la siguiente ubicación: `C:\ProgramData\Microsoft\Windows Defender\Platform\<version>` .</span><span class="sxs-lookup"><span data-stu-id="1b72e-113">If you're running an updated Microsoft Defender Platform version, run `**MpCmdRun**` from the following location: `C:\ProgramData\Microsoft\Windows Defender\Platform\<version>`.</span></span>

<span data-ttu-id="1b72e-114">La utilidad tiene los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="1b72e-114">The utility has the following commands:</span></span>

```console
MpCmdRun.exe [command] [-options]
```
<span data-ttu-id="1b72e-115">Aquí le mostramos un ejemplo:</span><span class="sxs-lookup"><span data-stu-id="1b72e-115">Here's an example:</span></span>

```console
MpCmdRun.exe -Scan -ScanType 2
``` 

| <span data-ttu-id="1b72e-116">Comando</span><span class="sxs-lookup"><span data-stu-id="1b72e-116">Command</span></span>  | <span data-ttu-id="1b72e-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="1b72e-117">Description</span></span>   |
|:----|:----|
| <span data-ttu-id="1b72e-118">`-?`**o**`-h`</span><span class="sxs-lookup"><span data-stu-id="1b72e-118">`-?` **or** `-h`</span></span>   | <span data-ttu-id="1b72e-119">Muestra todas las opciones disponibles para esta herramienta</span><span class="sxs-lookup"><span data-stu-id="1b72e-119">Displays all available options for this tool</span></span> |
| `-Scan [-ScanType [0\|1\|2\|3]] [-File <path> [-DisableRemediation] [-BootSectorScan] [-CpuThrottling]] [-Timeout <days>] [-Cancel]` | <span data-ttu-id="1b72e-120">Busca software malintencionado.</span><span class="sxs-lookup"><span data-stu-id="1b72e-120">Scans for malicious software.</span></span> <span data-ttu-id="1b72e-121">Los valores **de ScanType** son: **0** Valor predeterminado, según la configuración, **-1** Examen rápido, **-2** Examen completo, **-3** Examen personalizado de archivos y directorios.</span><span class="sxs-lookup"><span data-stu-id="1b72e-121">Values for **ScanType** are: **0** Default, according to your configuration, **-1** Quick scan, **-2** Full scan, **-3** File and directory custom scan.</span></span>  <span data-ttu-id="1b72e-122">CpuThrottling respetará la limitación de CPU configurada desde la directiva</span><span class="sxs-lookup"><span data-stu-id="1b72e-122">CpuThrottling will honor the configured CPU throttling from policy</span></span> |
| `-Trace [-Grouping #] [-Level #]` | <span data-ttu-id="1b72e-123">Inicia el seguimiento de diagnóstico</span><span class="sxs-lookup"><span data-stu-id="1b72e-123">Starts diagnostic tracing</span></span> |
| `-GetFiles [-SupportLogLocation <path>]` | <span data-ttu-id="1b72e-124">Recopila información de soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="1b72e-124">Collects support information.</span></span> <span data-ttu-id="1b72e-125">Vea '[collecting diagnostic data](collect-diagnostic-data.md)'</span><span class="sxs-lookup"><span data-stu-id="1b72e-125">See '[collecting diagnostic data](collect-diagnostic-data.md)'</span></span>  |
| `-GetFilesDiagTrack`  | <span data-ttu-id="1b72e-126">Igual que `-GetFiles` , pero salidas a la carpeta temporal de DiagTrack</span><span class="sxs-lookup"><span data-stu-id="1b72e-126">Same as `-GetFiles`, but outputs to temporary DiagTrack folder</span></span> |
| `-RemoveDefinitions [-All]` | <span data-ttu-id="1b72e-127">Restaura la inteligencia de seguridad instalada a una copia de seguridad anterior o al conjunto predeterminado original</span><span class="sxs-lookup"><span data-stu-id="1b72e-127">Restores the installed Security intelligence to a previous backup copy or to the original default set</span></span> |
| `-RemoveDefinitions [-DynamicSignatures]` | <span data-ttu-id="1b72e-128">Quita solo la inteligencia de seguridad descargada dinámicamente</span><span class="sxs-lookup"><span data-stu-id="1b72e-128">Removes only the dynamically downloaded Security intelligence</span></span> |
| `-RemoveDefinitions [-Engine]` | <span data-ttu-id="1b72e-129">Restaura el motor instalado anterior</span><span class="sxs-lookup"><span data-stu-id="1b72e-129">Restores the previous installed engine</span></span> |
| `-SignatureUpdate [-UNC \| -MMPC]` | <span data-ttu-id="1b72e-130">Comprueba si hay nuevas actualizaciones de inteligencia de seguridad</span><span class="sxs-lookup"><span data-stu-id="1b72e-130">Checks for new Security intelligence updates</span></span> |
| `-Restore  [-ListAll \| [[-Name <name>] [-All] \| [-FilePath <filePath>]] [-Path <path>]]` | <span data-ttu-id="1b72e-131">Restaura o enumera elementos en cuarentena</span><span class="sxs-lookup"><span data-stu-id="1b72e-131">Restores or lists quarantined item(s)</span></span> |
| `-AddDynamicSignature [-Path]` | <span data-ttu-id="1b72e-132">Carga inteligencia de seguridad dinámica</span><span class="sxs-lookup"><span data-stu-id="1b72e-132">Loads dynamic Security intelligence</span></span> |
| `-ListAllDynamicSignatures` | <span data-ttu-id="1b72e-133">Enumera la inteligencia de seguridad dinámica cargada</span><span class="sxs-lookup"><span data-stu-id="1b72e-133">Lists the loaded dynamic Security intelligence</span></span> |
| `-RemoveDynamicSignature [-SignatureSetID]` | <span data-ttu-id="1b72e-134">Quita la inteligencia de seguridad dinámica</span><span class="sxs-lookup"><span data-stu-id="1b72e-134">Removes dynamic Security intelligence</span></span> |
| `-CheckExclusion -path <path>` | <span data-ttu-id="1b72e-135">Comprueba si se excluye una ruta de acceso</span><span class="sxs-lookup"><span data-stu-id="1b72e-135">Checks whether a path is excluded</span></span> |
| `-ValidateMapsConnection` | <span data-ttu-id="1b72e-136">Comprueba que la red puede comunicarse con el servicio en la nube antivirus de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="1b72e-136">Verifies that your network can communicate with the Microsoft Defender Antivirus cloud service.</span></span> <span data-ttu-id="1b72e-137">Este comando solo funcionará en Windows 10, versión 1703 o posterior.</span><span class="sxs-lookup"><span data-stu-id="1b72e-137">This command will only work on Windows 10, version 1703 or higher.</span></span>|


## <a name="common-errors-in-running-commands-via-mpcmdrunexe"></a><span data-ttu-id="1b72e-138">Errores comunes al ejecutar comandos mediante mpcmdrun.exe</span><span class="sxs-lookup"><span data-stu-id="1b72e-138">Common errors in running commands via mpcmdrun.exe</span></span> 

|<span data-ttu-id="1b72e-139">Mensaje de error</span><span class="sxs-lookup"><span data-stu-id="1b72e-139">Error message</span></span> | <span data-ttu-id="1b72e-140">Posible motivo</span><span class="sxs-lookup"><span data-stu-id="1b72e-140">Possible reason</span></span>
|:----|:----|
| `ValidateMapsConnection failed (800106BA) or 0x800106BA` | <span data-ttu-id="1b72e-141">El servicio Antivirus de Microsoft Defender está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="1b72e-141">The Microsoft Defender Antivirus service is disabled.</span></span> <span data-ttu-id="1b72e-142">Habilite el servicio e inténtelo de nuevo.</span><span class="sxs-lookup"><span data-stu-id="1b72e-142">Enable the service and try again.</span></span> <br>   <span data-ttu-id="1b72e-143">**Nota:**  En Windows 10 1909 o versiones anteriores, y Windows Server 2019 o versiones anteriores, el servicio se llamaba servicio "Windows Defender Antivirus".</span><span class="sxs-lookup"><span data-stu-id="1b72e-143">**Note:**  In Windows 10 1909 or older, and Windows Server 2019 or older, the service used to be called "Windows Defender Antivirus" service.</span></span>|
| `0x80070667` | <span data-ttu-id="1b72e-144">Estás ejecutando el comando desde un equipo que es `-ValidateMapsConnection` Windows 10 versión 1607 o posterior, o Windows Server 2016 o posterior.</span><span class="sxs-lookup"><span data-stu-id="1b72e-144">You're running the `-ValidateMapsConnection` command from a computer that is Windows 10 version 1607 or older, or Windows Server 2016 or older.</span></span> <span data-ttu-id="1b72e-145">Ejecute el comando desde un equipo que sea Windows 10 versión 1703 o posterior, o Windows Server 2019 o posterior.</span><span class="sxs-lookup"><span data-stu-id="1b72e-145">Run the command from a machine that is Windows 10 version 1703 or newer, or Windows Server 2019 or newer.</span></span>|
| `'MpCmdRun' is not recognized as an internal or external command, operable program or batch file.` | <span data-ttu-id="1b72e-146">La herramienta debe ejecutarse desde: o (donde puede diferir dado que las actualizaciones de la plataforma `%ProgramFiles%\Windows Defender` `C:\ProgramData\Microsoft\Windows Defender\Platform\4.18.2012.4-0` son `2012.4-0` mensuales excepto marzo)</span><span class="sxs-lookup"><span data-stu-id="1b72e-146">The tool needs to be run from either: `%ProgramFiles%\Windows Defender` or `C:\ProgramData\Microsoft\Windows Defender\Platform\4.18.2012.4-0` (where `2012.4-0` might differ since platform updates are monthly except for March)</span></span>|
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80070005 httpcode=450)` | <span data-ttu-id="1b72e-147">No hay suficientes privilegios.</span><span class="sxs-lookup"><span data-stu-id="1b72e-147">Not enough privileges.</span></span> <span data-ttu-id="1b72e-148">Use el símbolo del sistema (cmd.exe) como administrador.</span><span class="sxs-lookup"><span data-stu-id="1b72e-148">Use the command prompt (cmd.exe) as an administrator.</span></span>|
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80070006 httpcode=451)` | <span data-ttu-id="1b72e-149">El firewall bloquea la conexión o realiza una inspección SSL.</span><span class="sxs-lookup"><span data-stu-id="1b72e-149">The firewall is blocking the connection or conducting SSL inspection.</span></span> |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80004005 httpcode=450)` | <span data-ttu-id="1b72e-150">Posibles problemas relacionados con la red, como problemas de resolución de nombres</span><span class="sxs-lookup"><span data-stu-id="1b72e-150">Possible network-related issues, like name resolution problems</span></span>|
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=0x80508015` | <span data-ttu-id="1b72e-151">El firewall bloquea la conexión o realiza una inspección SSL.</span><span class="sxs-lookup"><span data-stu-id="1b72e-151">The firewall is blocking the connection or conducting SSL inspection.</span></span> |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=800722F0D` | <span data-ttu-id="1b72e-152">El firewall bloquea la conexión o realiza una inspección SSL.</span><span class="sxs-lookup"><span data-stu-id="1b72e-152">The firewall is blocking the connection or conducting SSL inspection.</span></span> |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80072EE7 httpcode=451)` | <span data-ttu-id="1b72e-153">El firewall bloquea la conexión o realiza una inspección SSL.</span><span class="sxs-lookup"><span data-stu-id="1b72e-153">The firewall is blocking the connection or conducting SSL inspection.</span></span> |

## <a name="see-also"></a><span data-ttu-id="1b72e-154">Vea también</span><span class="sxs-lookup"><span data-stu-id="1b72e-154">See also</span></span>

- [<span data-ttu-id="1b72e-155">Configurar características de Antivirus de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="1b72e-155">Configure Microsoft Defender Antivirus features</span></span>](configure-microsoft-defender-antivirus-features.md)
- [<span data-ttu-id="1b72e-156">Administrar antivirus de Microsoft Defender en su empresa</span><span class="sxs-lookup"><span data-stu-id="1b72e-156">Manage Microsoft Defender Antivirus in your business</span></span>](configuration-management-reference-microsoft-defender-antivirus.md)
- [<span data-ttu-id="1b72e-157">Temas de referencia para herramientas de administración y configuración</span><span class="sxs-lookup"><span data-stu-id="1b72e-157">Reference topics for management and configuration tools</span></span>](configuration-management-reference-microsoft-defender-antivirus.md)
- [<span data-ttu-id="1b72e-158">Antivirus de Microsoft Defender en Windows 10</span><span class="sxs-lookup"><span data-stu-id="1b72e-158">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)