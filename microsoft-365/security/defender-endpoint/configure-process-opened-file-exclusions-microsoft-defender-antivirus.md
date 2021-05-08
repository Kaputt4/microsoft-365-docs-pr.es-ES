---
title: Configurar exclusiones para archivos abiertos por procesos específicos
description: Puede excluir archivos de los exámenes si se han abierto mediante un proceso específico.
keywords: Antivirus de Microsoft Defender, proceso, exclusión, archivos, exámenes
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 2fdc646cf616ff6a6fa36a83be3d2b1dd0432fbe
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274621"
---
# <a name="configure-exclusions-for-files-opened-by-processes"></a><span data-ttu-id="1d3c6-104">Configurar exclusiones para archivos abiertos por procesos</span><span class="sxs-lookup"><span data-stu-id="1d3c6-104">Configure exclusions for files opened by processes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="1d3c6-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="1d3c6-105">**Applies to:**</span></span>

- [<span data-ttu-id="1d3c6-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="1d3c6-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="1d3c6-107">Puede excluir los archivos abiertos por procesos específicos de los exámenes del Antivirus de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="1d3c6-107">You can exclude files that have been opened by specific processes from Microsoft Defender Antivirus scans.</span></span> <span data-ttu-id="1d3c6-108">Consulta [Recomendaciones para definir exclusiones antes](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions) de definir las listas de exclusión.</span><span class="sxs-lookup"><span data-stu-id="1d3c6-108">See [Recommendations for defining exclusions](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions) before defining your exclusion lists.</span></span>

<span data-ttu-id="1d3c6-109">En este artículo se describe cómo configurar listas de exclusión.</span><span class="sxs-lookup"><span data-stu-id="1d3c6-109">This article describes how to configure exclusion lists.</span></span> 

## <a name="examples-of-exclusions"></a><span data-ttu-id="1d3c6-110">Ejemplos de exclusiones</span><span class="sxs-lookup"><span data-stu-id="1d3c6-110">Examples of exclusions</span></span>

|<span data-ttu-id="1d3c6-111">Exclusión</span><span class="sxs-lookup"><span data-stu-id="1d3c6-111">Exclusion</span></span> | <span data-ttu-id="1d3c6-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1d3c6-112">Example</span></span> |
|---|---|
|<span data-ttu-id="1d3c6-113">Cualquier archivo del equipo que abra cualquier proceso con un nombre de archivo específico</span><span class="sxs-lookup"><span data-stu-id="1d3c6-113">Any file on the machine that is opened by any process with a specific file name</span></span> | <span data-ttu-id="1d3c6-114">Especificar `test.exe` excluiría los archivos abiertos por:</span><span class="sxs-lookup"><span data-stu-id="1d3c6-114">Specifying `test.exe` would exclude files opened by:</span></span> <br/>`c:\sample\test.exe`<br/>`d:\internal\files\test.exe` |  
|<span data-ttu-id="1d3c6-115">Cualquier archivo del equipo que abra cualquier proceso en una carpeta específica</span><span class="sxs-lookup"><span data-stu-id="1d3c6-115">Any file on the machine that is opened by any process under a specific folder</span></span> | <span data-ttu-id="1d3c6-116">Especificar `c:\test\sample\*` excluiría los archivos abiertos por:</span><span class="sxs-lookup"><span data-stu-id="1d3c6-116">Specifying `c:\test\sample\*` would exclude files opened by:</span></span><br/>`c:\test\sample\test.exe`<br/>`c:\test\sample\test2.exe`<br/>`c:\test\sample\utility.exe` | 
|<span data-ttu-id="1d3c6-117">Cualquier archivo del equipo que se abra mediante un proceso específico en una carpeta específica</span><span class="sxs-lookup"><span data-stu-id="1d3c6-117">Any file on the machine that is opened by a specific process in a specific folder</span></span> | <span data-ttu-id="1d3c6-118">Especificar `c:\test\process.exe` excluiría los archivos solo abiertos por `c:\test\process.exe`</span><span class="sxs-lookup"><span data-stu-id="1d3c6-118">Specifying `c:\test\process.exe` would exclude files only opened by `c:\test\process.exe`</span></span> |


<span data-ttu-id="1d3c6-119">Al agregar un proceso a la lista de exclusión de procesos, Antivirus de Microsoft Defender no examinará los archivos abiertos por ese proceso, independientemente de dónde se encuentran los archivos.</span><span class="sxs-lookup"><span data-stu-id="1d3c6-119">When you add a process to the process exclusion list, Microsoft Defender Antivirus won't scan files opened by that process, no matter where the files are located.</span></span> <span data-ttu-id="1d3c6-120">Sin embargo, el proceso en sí se examinará a menos que también se haya agregado a la lista [de exclusión de archivos](configure-extension-file-exclusions-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="1d3c6-120">The process itself, however, will be scanned unless it has also been added to the [file exclusion list](configure-extension-file-exclusions-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="1d3c6-121">Las exclusiones solo se aplican a la protección y supervisión siempre activas [en tiempo real.](configure-real-time-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="1d3c6-121">The exclusions only apply to [always-on real-time protection and monitoring](configure-real-time-protection-microsoft-defender-antivirus.md).</span></span> <span data-ttu-id="1d3c6-122">No se aplican a exámenes programados o a petición.</span><span class="sxs-lookup"><span data-stu-id="1d3c6-122">They don't apply to scheduled or on-demand scans.</span></span>

<span data-ttu-id="1d3c6-123">Los cambios realizados con la directiva de grupo en las listas de exclusión **se mostrarán** en las listas de la [aplicación Seguridad de Windows](microsoft-defender-security-center-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="1d3c6-123">Changes made with Group Policy to the exclusion lists **will show** in the lists in the [Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span> <span data-ttu-id="1d3c6-124">Sin embargo, los cambios realizados en la aplicación Seguridad de Windows **no se mostrarán** en las listas de directivas de grupo.</span><span class="sxs-lookup"><span data-stu-id="1d3c6-124">However, changes made in the Windows Security app **will not show** in the Group Policy lists.</span></span>

<span data-ttu-id="1d3c6-125">Puedes agregar, quitar y revisar las listas de exclusiones en La directiva de grupo, Microsoft Endpoint Configuration Manager, Microsoft Intune y con la aplicación Seguridad de Windows, y puedes usar caracteres comodín para personalizar aún más las listas.</span><span class="sxs-lookup"><span data-stu-id="1d3c6-125">You can add, remove, and review the lists for exclusions in Group Policy, Microsoft Endpoint Configuration Manager, Microsoft Intune, and with the Windows Security app, and you can use wildcards to further customize the lists.</span></span>

<span data-ttu-id="1d3c6-126">También puede usar cmdlets de PowerShell y WMI para configurar las listas de exclusión, incluida la revisión de las listas.</span><span class="sxs-lookup"><span data-stu-id="1d3c6-126">You can also use PowerShell cmdlets and WMI to configure the exclusion lists, including reviewing your lists.</span></span>

<span data-ttu-id="1d3c6-127">De forma predeterminada, los cambios locales realizados en las listas (por usuarios con privilegios de administrador; los cambios realizados con PowerShell y WMI) se combinarán con las listas definidas (e implementadas) por la directiva de grupo, Configuration Manager o Intune.</span><span class="sxs-lookup"><span data-stu-id="1d3c6-127">By default, local changes made to the lists (by users with administrator privileges; changes made with PowerShell and WMI) will be merged with the lists as defined (and deployed) by Group Policy, Configuration Manager, or Intune.</span></span> <span data-ttu-id="1d3c6-128">Las listas de directivas de grupo tendrán prioridad en caso de conflictos.</span><span class="sxs-lookup"><span data-stu-id="1d3c6-128">The Group Policy lists will take precedence in the case of conflicts.</span></span>

<span data-ttu-id="1d3c6-129">Puede configurar cómo se combinan las listas de [exclusiones definidas local](configure-local-policy-overrides-microsoft-defender-antivirus.md#merge-lists) y globalmente para permitir que los cambios locales invaliden la configuración de implementación administrada.</span><span class="sxs-lookup"><span data-stu-id="1d3c6-129">You can [configure how locally and globally defined exclusions lists are merged](configure-local-policy-overrides-microsoft-defender-antivirus.md#merge-lists) to allow local changes to override managed deployment settings.</span></span>

## <a name="configure-the-list-of-exclusions-for-files-opened-by-specified-processes"></a><span data-ttu-id="1d3c6-130">Configurar la lista de exclusiones de archivos abiertos por procesos especificados</span><span class="sxs-lookup"><span data-stu-id="1d3c6-130">Configure the list of exclusions for files opened by specified processes</span></span>

### <a name="use-microsoft-intune-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a><span data-ttu-id="1d3c6-131">Usar Microsoft Intune para excluir de los exámenes los archivos abiertos por procesos especificados</span><span class="sxs-lookup"><span data-stu-id="1d3c6-131">Use Microsoft Intune to exclude files that have been opened by specified processes from scans</span></span>

<span data-ttu-id="1d3c6-132">Para [obtener más información,](/intune/device-restrictions-configure) consulta Configurar la configuración de restricción de dispositivos de Microsoft Intune y Antivirus de Microsoft Defender para [Windows 10 en Intune.](/intune/device-restrictions-windows-10#microsoft-defender-antivirus)</span><span class="sxs-lookup"><span data-stu-id="1d3c6-132">See [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure) and [Microsoft Defender Antivirus device restriction settings for Windows 10 in Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus) for more details.</span></span>

### <a name="use-microsoft-endpoint-manager-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a><span data-ttu-id="1d3c6-133">Usar Microsoft Endpoint Manager para excluir de los exámenes los archivos abiertos por procesos especificados</span><span class="sxs-lookup"><span data-stu-id="1d3c6-133">Use Microsoft Endpoint Manager to exclude files that have been opened by specified processes from scans</span></span>

<span data-ttu-id="1d3c6-134">Vea [How to create and deploy antimalware policies: Exclusion settings](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings) para obtener más información sobre cómo configurar Microsoft Endpoint Manager (rama actual).</span><span class="sxs-lookup"><span data-stu-id="1d3c6-134">See [How to create and deploy antimalware policies: Exclusion settings](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings) for details on configuring Microsoft Endpoint Manager (current branch).</span></span>

### <a name="use-group-policy-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a><span data-ttu-id="1d3c6-135">Usar la directiva de grupo para excluir de los exámenes los archivos abiertos por procesos especificados</span><span class="sxs-lookup"><span data-stu-id="1d3c6-135">Use Group Policy to exclude files that have been opened by specified processes from scans</span></span>

1. <span data-ttu-id="1d3c6-136">En el equipo de administración de directivas de grupo, abra la Consola de administración de directivas de [grupo,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))haga clic con el botón secundario en el objeto de directiva de grupo que desea configurar y haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="1d3c6-136">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="1d3c6-137">En el **Editor de administración de directivas de grupo,** vaya a Configuración del equipo **y** haga clic en **Plantillas administrativas.**</span><span class="sxs-lookup"><span data-stu-id="1d3c6-137">In the **Group Policy Management Editor** go to **Computer configuration** and click **Administrative templates**.</span></span>

3. <span data-ttu-id="1d3c6-138">Expande el árbol a **componentes de Windows > de Microsoft Defender Antivirus > exclusiones**.</span><span class="sxs-lookup"><span data-stu-id="1d3c6-138">Expand the tree to **Windows components > Microsoft Defender Antivirus > Exclusions**.</span></span>

4. <span data-ttu-id="1d3c6-139">Haga doble clic **en Exclusiones de proceso** y agregue las exclusiones:</span><span class="sxs-lookup"><span data-stu-id="1d3c6-139">Double-click **Process Exclusions** and add the exclusions:</span></span>

    1. <span data-ttu-id="1d3c6-140">Establezca la opción en **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="1d3c6-140">Set the option to **Enabled**.</span></span>
    2. <span data-ttu-id="1d3c6-141">En la **sección Opciones,** haga clic **en Mostrar...**.</span><span class="sxs-lookup"><span data-stu-id="1d3c6-141">Under the **Options** section, click **Show...**.</span></span>
    3. <span data-ttu-id="1d3c6-142">Escriba cada proceso en su propia línea en la **columna Nombre de** valor.</span><span class="sxs-lookup"><span data-stu-id="1d3c6-142">Enter each process on its own line under the **Value name** column.</span></span> <span data-ttu-id="1d3c6-143">Vea la tabla de ejemplo para ver los distintos tipos de exclusiones de procesos.</span><span class="sxs-lookup"><span data-stu-id="1d3c6-143">See the example table for the different types of process exclusions.</span></span>  <span data-ttu-id="1d3c6-144">Escriba **0 en** la **columna Valor** para todos los procesos.</span><span class="sxs-lookup"><span data-stu-id="1d3c6-144">Enter **0** in the **Value** column for all processes.</span></span>

5. <span data-ttu-id="1d3c6-145">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1d3c6-145">Click **OK**.</span></span>

### <a name="use-powershell-cmdlets-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a><span data-ttu-id="1d3c6-146">Usar cmdlets de PowerShell para excluir archivos abiertos por procesos especificados de exámenes</span><span class="sxs-lookup"><span data-stu-id="1d3c6-146">Use PowerShell cmdlets to exclude files that have been opened by specified processes from scans</span></span>

<span data-ttu-id="1d3c6-147">El uso de PowerShell para agregar o quitar exclusiones de archivos abiertos por procesos requiere el uso de una combinación de tres cmdlets con el `-ExclusionProcess` parámetro.</span><span class="sxs-lookup"><span data-stu-id="1d3c6-147">Using PowerShell to add or remove exclusions for files that have been opened by processes requires using a combination of three cmdlets with the `-ExclusionProcess` parameter.</span></span> <span data-ttu-id="1d3c6-148">Los cmdlets están todos en el [módulo Defender](/powershell/module/defender/).</span><span class="sxs-lookup"><span data-stu-id="1d3c6-148">The cmdlets are all in the [Defender module](/powershell/module/defender/).</span></span>

<span data-ttu-id="1d3c6-149">El formato de los cmdlets es:</span><span class="sxs-lookup"><span data-stu-id="1d3c6-149">The format for the cmdlets is:</span></span>

```PowerShell
<cmdlet> -ExclusionProcess "<item>"
```

<span data-ttu-id="1d3c6-150">Se permite lo siguiente como \<cmdlet> :</span><span class="sxs-lookup"><span data-stu-id="1d3c6-150">The following are allowed as the \<cmdlet>:</span></span>

|<span data-ttu-id="1d3c6-151">Acción de configuración</span><span class="sxs-lookup"><span data-stu-id="1d3c6-151">Configuration action</span></span> | <span data-ttu-id="1d3c6-152">Cmdlet de PowerShell</span><span class="sxs-lookup"><span data-stu-id="1d3c6-152">PowerShell cmdlet</span></span> |
|---|---|
|<span data-ttu-id="1d3c6-153">Crear o sobrescribir la lista</span><span class="sxs-lookup"><span data-stu-id="1d3c6-153">Create or overwrite the list</span></span> | `Set-MpPreference` |
|<span data-ttu-id="1d3c6-154">Agregar a la lista</span><span class="sxs-lookup"><span data-stu-id="1d3c6-154">Add to the list</span></span> | `Add-MpPreference` |
|<span data-ttu-id="1d3c6-155">Quitar elementos de la lista</span><span class="sxs-lookup"><span data-stu-id="1d3c6-155">Remove items from the list</span></span> | `Remove-MpPreference` |

>[!IMPORTANT]
><span data-ttu-id="1d3c6-156">Si ha creado una lista, ya sea con o con el `Set-MpPreference` `Add-MpPreference` cmdlet de nuevo `Set-MpPreference` sobrescribirá la lista existente.</span><span class="sxs-lookup"><span data-stu-id="1d3c6-156">If you have created a list, either with `Set-MpPreference` or `Add-MpPreference`, using the `Set-MpPreference` cmdlet again will overwrite the existing list.</span></span>

<span data-ttu-id="1d3c6-157">Por ejemplo, el siguiente fragmento de código provocaría que los exámenes antivirus de Microsoft Defender excluyan cualquier archivo abierto por el proceso especificado:</span><span class="sxs-lookup"><span data-stu-id="1d3c6-157">For example, the following code snippet would cause Microsoft Defender AV scans to exclude any file that is opened by the specified process:</span></span>

```PowerShell
Add-MpPreference -ExclusionProcess "c:\internal\test.exe"
```

<span data-ttu-id="1d3c6-158">Para obtener más información sobre cómo usar PowerShell con Antivirus de Microsoft Defender, vea Manage antivirus with PowerShell cmdlets and [Microsoft Defender Antivirus cmdlets](/powershell/module/defender).</span><span class="sxs-lookup"><span data-stu-id="1d3c6-158">For more information on how to use PowerShell with Microsoft Defender Antivirus, see Manage antivirus with PowerShell cmdlets and [Microsoft Defender Antivirus cmdlets](/powershell/module/defender).</span></span>

### <a name="use-windows-management-instruction-wmi-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a><span data-ttu-id="1d3c6-159">Usar Windows Management Instruction (WMI) para excluir de los exámenes los archivos abiertos por procesos especificados</span><span class="sxs-lookup"><span data-stu-id="1d3c6-159">Use Windows Management Instruction (WMI) to exclude files that have been opened by specified processes from scans</span></span>

<span data-ttu-id="1d3c6-160">Utilice los [ **métodos Set**, **Add** y **Remove** de **la clase MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) para las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="1d3c6-160">Use the [**Set**, **Add**, and **Remove** methods of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ExclusionProcess
```

<span data-ttu-id="1d3c6-161">El uso **de Set**, **Add** y **Remove** es análogo a sus equivalentes en PowerShell: , `Set-MpPreference` y `Add-MpPreference` `Remove-MpPreference` .</span><span class="sxs-lookup"><span data-stu-id="1d3c6-161">The use of **Set**, **Add**, and **Remove** is analogous to their counterparts in PowerShell: `Set-MpPreference`, `Add-MpPreference`, and `Remove-MpPreference`.</span></span>

<span data-ttu-id="1d3c6-162">Para obtener más información y parámetros permitidos,  [vea Windows Defender API wmiv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span><span class="sxs-lookup"><span data-stu-id="1d3c6-162">For more information and allowed parameters, see  [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

### <a name="use-the-windows-security-app-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a><span data-ttu-id="1d3c6-163">Usar la aplicación Seguridad de Windows para excluir los archivos abiertos por procesos especificados de los exámenes</span><span class="sxs-lookup"><span data-stu-id="1d3c6-163">Use the Windows Security app to exclude files that have been opened by specified processes from scans</span></span>

<span data-ttu-id="1d3c6-164">Consulta [Agregar exclusiones en la aplicación Seguridad de Windows](microsoft-defender-security-center-antivirus.md) para obtener instrucciones.</span><span class="sxs-lookup"><span data-stu-id="1d3c6-164">See [Add exclusions in the Windows Security app](microsoft-defender-security-center-antivirus.md) for instructions.</span></span>

## <a name="use-wildcards-in-the-process-exclusion-list"></a><span data-ttu-id="1d3c6-165">Usar caracteres comodín en la lista de exclusión de procesos</span><span class="sxs-lookup"><span data-stu-id="1d3c6-165">Use wildcards in the process exclusion list</span></span>

<span data-ttu-id="1d3c6-166">El uso de caracteres comodín en la lista de exclusión de procesos es diferente de su uso en otras listas de exclusión.</span><span class="sxs-lookup"><span data-stu-id="1d3c6-166">The use of wildcards in the process exclusion list is different from their use in other exclusion lists.</span></span>

<span data-ttu-id="1d3c6-167">En concreto, no puede usar el signo de interrogación ( ) comodín y el asterisco ( ) comodín solo se puede usar al final `?` de una ruta de acceso `*` completa.</span><span class="sxs-lookup"><span data-stu-id="1d3c6-167">In particular, you cannot use the question mark (`?`) wildcard, and the asterisk (`*`) wildcard can only be used at the end of a complete path.</span></span> <span data-ttu-id="1d3c6-168">Todavía puede usar variables de entorno (como ) como caracteres comodín al `%ALLUSERSPROFILE%` definir elementos en la lista de exclusión de procesos.</span><span class="sxs-lookup"><span data-stu-id="1d3c6-168">You can still use environment variables (such as `%ALLUSERSPROFILE%`) as wildcards when defining items in the process exclusion list.</span></span>

<span data-ttu-id="1d3c6-169">En la tabla siguiente se describe cómo se pueden usar los caracteres comodín en la lista de exclusión de procesos:</span><span class="sxs-lookup"><span data-stu-id="1d3c6-169">The following table describes how the wildcards can be used in the process exclusion list:</span></span>

|<span data-ttu-id="1d3c6-170">Carácter comodín</span><span class="sxs-lookup"><span data-stu-id="1d3c6-170">Wildcard</span></span> | <span data-ttu-id="1d3c6-171">Uso de ejemplo</span><span class="sxs-lookup"><span data-stu-id="1d3c6-171">Example use</span></span> | <span data-ttu-id="1d3c6-172">Coincidencias de ejemplo</span><span class="sxs-lookup"><span data-stu-id="1d3c6-172">Example matches</span></span> |
|:---|:---|:---|
|<span data-ttu-id="1d3c6-173">`*` (asterisco)</span><span class="sxs-lookup"><span data-stu-id="1d3c6-173">`*` (asterisk)</span></span> <br/><br/> <span data-ttu-id="1d3c6-174">Reemplaza cualquier número de caracteres</span><span class="sxs-lookup"><span data-stu-id="1d3c6-174">Replaces any number of characters</span></span> | `C:\MyData\*` | <span data-ttu-id="1d3c6-175">Cualquier archivo abierto por `C:\MyData\file.exe`</span><span class="sxs-lookup"><span data-stu-id="1d3c6-175">Any file opened by `C:\MyData\file.exe`</span></span> |
|<span data-ttu-id="1d3c6-176">Variables de entorno</span><span class="sxs-lookup"><span data-stu-id="1d3c6-176">Environment variables</span></span> <br/><br/> <span data-ttu-id="1d3c6-177">La variable definida se rellena como una ruta de acceso cuando se evalúa la exclusión</span><span class="sxs-lookup"><span data-stu-id="1d3c6-177">The defined variable is populated as a path when the exclusion is evaluated</span></span> | `%ALLUSERSPROFILE%\CustomLogFiles\file.exe` | <span data-ttu-id="1d3c6-178">Cualquier archivo abierto por `C:\ProgramData\CustomLogFiles\file.exe`</span><span class="sxs-lookup"><span data-stu-id="1d3c6-178">Any file opened by `C:\ProgramData\CustomLogFiles\file.exe`</span></span> |

## <a name="review-the-list-of-exclusions"></a><span data-ttu-id="1d3c6-179">Revisar la lista de exclusiones</span><span class="sxs-lookup"><span data-stu-id="1d3c6-179">Review the list of exclusions</span></span>

<span data-ttu-id="1d3c6-180">Puede recuperar los elementos de la lista de exclusión con MpCmdRun, PowerShell, [Microsoft Endpoint Configuration Manager,](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings) [Intune](/intune/device-restrictions-configure)o la aplicación seguridad [de Windows](microsoft-defender-security-center-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="1d3c6-180">You can retrieve the items in the exclusion list with MpCmdRun, PowerShell, [Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings), [Intune](/intune/device-restrictions-configure), or the [Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span>

<span data-ttu-id="1d3c6-181">Si usa PowerShell, puede recuperar la lista de dos maneras:</span><span class="sxs-lookup"><span data-stu-id="1d3c6-181">If you use PowerShell, you can retrieve the list in two ways:</span></span>

- <span data-ttu-id="1d3c6-182">Recupera el estado de todas las preferencias de Antivirus de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="1d3c6-182">Retrieve the status of all Microsoft Defender Antivirus preferences.</span></span> <span data-ttu-id="1d3c6-183">Cada una de las listas se mostrará en líneas independientes, pero los elementos de cada lista se combinarán en la misma línea.</span><span class="sxs-lookup"><span data-stu-id="1d3c6-183">Each of the lists will be displayed on separate lines, but the items within each list will be combined into the same line.</span></span>
- <span data-ttu-id="1d3c6-184">Escribe el estado de todas las preferencias en una variable y usa esa variable para llamar solo a la lista específica que te interesa.</span><span class="sxs-lookup"><span data-stu-id="1d3c6-184">Write the status of all preferences to a variable, and use that variable to only call the specific list you are interested in.</span></span> <span data-ttu-id="1d3c6-185">Cada uso de `Add-MpPreference` se escribe en una nueva línea.</span><span class="sxs-lookup"><span data-stu-id="1d3c6-185">Each use of `Add-MpPreference` is written to a new line.</span></span>

### <a name="validate-the-exclusion-list-by-using-mpcmdrun"></a><span data-ttu-id="1d3c6-186">Validar la lista de exclusión mediante MpCmdRun</span><span class="sxs-lookup"><span data-stu-id="1d3c6-186">Validate the exclusion list by using MpCmdRun</span></span>

<span data-ttu-id="1d3c6-187">Para comprobar las exclusiones con la herramienta de línea de [comandos ](./command-line-arguments-microsoft-defender-antivirus.md?branch=v-anbic-wdav-new-mpcmdrun-options)mpcmdrun.exe, use el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="1d3c6-187">To check exclusions with the dedicated [command-line tool mpcmdrun.exe](./command-line-arguments-microsoft-defender-antivirus.md?branch=v-anbic-wdav-new-mpcmdrun-options), use the following command:</span></span>

```DOS
MpCmdRun.exe -CheckExclusion -path <path>
```

> [!NOTE]
> <span data-ttu-id="1d3c6-188">Para comprobar exclusiones con MpCmdRun, es necesario microsoft Defender Antivirus CAMP versión 4.18.1812.3 (publicado en diciembre de 2018) o posterior.</span><span class="sxs-lookup"><span data-stu-id="1d3c6-188">Checking exclusions with MpCmdRun requires Microsoft Defender Antivirus CAMP version 4.18.1812.3 (released in December 2018) or later.</span></span>


### <a name="review-the-list-of-exclusions-alongside-all-other-microsoft-defender-antivirus-preferences-by-using-powershell"></a><span data-ttu-id="1d3c6-189">Revise la lista de exclusiones junto con todas las demás preferencias de Antivirus de Microsoft Defender con PowerShell</span><span class="sxs-lookup"><span data-stu-id="1d3c6-189">Review the list of exclusions alongside all other Microsoft Defender Antivirus preferences by using PowerShell</span></span>

<span data-ttu-id="1d3c6-190">Use el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="1d3c6-190">Use the following cmdlet:</span></span>

```PowerShell
Get-MpPreference
```

<span data-ttu-id="1d3c6-191">Consulte [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and Defender [cmdlets](/powershell/module/defender) para obtener más información sobre cómo usar PowerShell con Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="1d3c6-191">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="retrieve-a-specific-exclusions-list-by-using-powershell"></a><span data-ttu-id="1d3c6-192">Recuperar una lista de exclusiones específica mediante PowerShell</span><span class="sxs-lookup"><span data-stu-id="1d3c6-192">Retrieve a specific exclusions list by using PowerShell</span></span>

<span data-ttu-id="1d3c6-193">Use el siguiente fragmento de código (escriba cada línea como un comando independiente); reemplace **WDAVprefs** por la etiqueta que desee nombrar la variable:</span><span class="sxs-lookup"><span data-stu-id="1d3c6-193">Use the following code snippet (enter each line as a separate command); replace **WDAVprefs** with whatever label you want to name the variable:</span></span>

```PowerShell
$WDAVprefs = Get-MpPreference
$WDAVprefs.ExclusionProcess
```

<span data-ttu-id="1d3c6-194">Consulte [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and Defender [cmdlets](/powershell/module/defender) para obtener más información sobre cómo usar PowerShell con Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="1d3c6-194">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

## <a name="related-articles"></a><span data-ttu-id="1d3c6-195">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="1d3c6-195">Related articles</span></span>

- [<span data-ttu-id="1d3c6-196">Configurar y validar exclusiones en exámenes de Antivirus de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="1d3c6-196">Configure and validate exclusions in Microsoft Defender Antivirus scans</span></span>](configure-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="1d3c6-197">Configurar y validar exclusiones según el nombre de archivo, la extensión y la ubicación de la carpeta</span><span class="sxs-lookup"><span data-stu-id="1d3c6-197">Configure and validate exclusions based on file name, extension, and folder location</span></span>](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="1d3c6-198">Configurar exclusiones de Antivirus de Microsoft Defender en Windows Server</span><span class="sxs-lookup"><span data-stu-id="1d3c6-198">Configure Microsoft Defender Antivirus exclusions on Windows Server</span></span>](configure-server-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="1d3c6-199">Errores comunes para evitarlos cuando se definen exclusiones</span><span class="sxs-lookup"><span data-stu-id="1d3c6-199">Common mistakes to avoid when defining exclusions</span></span>](common-exclusion-mistakes-microsoft-defender-antivirus.md)
- [<span data-ttu-id="1d3c6-200">Personalizar, iniciar y revisar los resultados de los exámenes y la corrección del Antivirus de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="1d3c6-200">Customize, initiate, and review the results of Microsoft Defender Antivirus scans and remediation</span></span>](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="1d3c6-201">Antivirus de Microsoft Defender en Windows 10</span><span class="sxs-lookup"><span data-stu-id="1d3c6-201">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)