---
title: Configurar Antivirus de Microsoft Defender exclusiones en Windows Server
ms.reviewer: ''
manager: dansimp
description: Windows El servidor incluye exclusiones automáticas, según el rol de servidor. También puede agregar exclusiones personalizadas.
keywords: exclusiones, servidor, exclusiones automáticas, automáticas, personalizadas, exámenes, Antivirus de Microsoft Defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.technology: mde
ms.date: 02/10/2021
ms.topic: article
ms.openlocfilehash: f82da8eb0dcba39404c2b7f191e166aa78357cee
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274765"
---
# <a name="configure-microsoft-defender-antivirus-exclusions-on-windows-server"></a><span data-ttu-id="c3074-105">Configurar Antivirus de Microsoft Defender exclusiones en Windows Server</span><span class="sxs-lookup"><span data-stu-id="c3074-105">Configure Microsoft Defender Antivirus exclusions on Windows Server</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c3074-106">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="c3074-106">**Applies to:**</span></span>

- [<span data-ttu-id="c3074-107">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="c3074-107">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="c3074-108">Antivirus de Microsoft Defender en Windows Server 2016 y Windows Server 2019 lo inscribe automáticamente en determinadas exclusiones, tal como lo define el rol de servidor especificado.</span><span class="sxs-lookup"><span data-stu-id="c3074-108">Microsoft Defender Antivirus on Windows Server 2016 and Windows Server 2019 automatically enrolls you in certain exclusions, as defined by your specified server role.</span></span> <span data-ttu-id="c3074-109">Estas exclusiones no aparecen en las listas de exclusión estándar que se muestran en la [Seguridad de Windows aplicación](microsoft-defender-security-center-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="c3074-109">These exclusions do not appear in the standard exclusion lists that are shown in the [Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span>

> [!NOTE]
> <span data-ttu-id="c3074-110">Las exclusiones automáticas solo se aplican al examen de protección en tiempo real (RTP).</span><span class="sxs-lookup"><span data-stu-id="c3074-110">Automatic exclusions only apply to Real-time protection (RTP) scanning.</span></span> <span data-ttu-id="c3074-111">Las exclusiones automáticas no se respetan durante un examen completo/rápido o a petición.</span><span class="sxs-lookup"><span data-stu-id="c3074-111">Automatic exclusions are not honored during a Full/Quick or On-demand scan.</span></span>

<span data-ttu-id="c3074-112">Además de las exclusiones automáticas definidas por roles de servidor, puede agregar o quitar exclusiones personalizadas.</span><span class="sxs-lookup"><span data-stu-id="c3074-112">In addition to server role-defined automatic exclusions, you can add or remove custom exclusions.</span></span> <span data-ttu-id="c3074-113">Para ello, consulte estos artículos:</span><span class="sxs-lookup"><span data-stu-id="c3074-113">To do that, refer to these articles:</span></span>
- [<span data-ttu-id="c3074-114">Configurar y validar exclusiones según el nombre de archivo, la extensión y la ubicación de la carpeta</span><span class="sxs-lookup"><span data-stu-id="c3074-114">Configure and validate exclusions based on file name, extension, and folder location</span></span>](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="c3074-115">Configurar y validar exclusiones para archivos abiertos por procesos</span><span class="sxs-lookup"><span data-stu-id="c3074-115">Configure and validate exclusions for files opened by processes</span></span>](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)

## <a name="a-few-points-to-keep-in-mind"></a><span data-ttu-id="c3074-116">Algunos puntos a tener en cuenta</span><span class="sxs-lookup"><span data-stu-id="c3074-116">A few points to keep in mind</span></span>

<span data-ttu-id="c3074-117">Tenga en cuenta los siguientes puntos importantes:</span><span class="sxs-lookup"><span data-stu-id="c3074-117">Keep the following important points in mind:</span></span>

- <span data-ttu-id="c3074-118">Las exclusiones personalizadas tienen prioridad sobre las exclusiones automáticas.</span><span class="sxs-lookup"><span data-stu-id="c3074-118">Custom exclusions take precedence over automatic exclusions.</span></span>
- <span data-ttu-id="c3074-119">Las exclusiones automáticas solo se aplican al examen de protección en tiempo real (RTP).</span><span class="sxs-lookup"><span data-stu-id="c3074-119">Automatic exclusions only apply to Real-time protection (RTP) scanning.</span></span> <span data-ttu-id="c3074-120">Las exclusiones automáticas no se respetan durante un examen completo/rápido o a petición.</span><span class="sxs-lookup"><span data-stu-id="c3074-120">Automatic exclusions are not honored during a Full/Quick or On-demand scan.</span></span>
- <span data-ttu-id="c3074-121">Las exclusiones personalizadas y duplicadas no están en conflicto con las exclusiones automáticas.</span><span class="sxs-lookup"><span data-stu-id="c3074-121">Custom and duplicate exclusions do not conflict with automatic exclusions.</span></span>
- <span data-ttu-id="c3074-122">Antivirus de Microsoft Defender usa las herramientas de administración y mantenimiento de imágenes de implementación (DISM) para determinar qué roles están instalados en el equipo.</span><span class="sxs-lookup"><span data-stu-id="c3074-122">Microsoft Defender Antivirus uses the Deployment Image Servicing and Management (DISM) tools to determine which roles are installed on your computer.</span></span>

## <a name="opt-out-of-automatic-exclusions"></a><span data-ttu-id="c3074-123">No participar en exclusiones automáticas</span><span class="sxs-lookup"><span data-stu-id="c3074-123">Opt out of automatic exclusions</span></span>

<span data-ttu-id="c3074-124">En Windows Server 2016 y Windows Server 2019, las exclusiones predefinidas que entregan las actualizaciones de inteligencia de seguridad solo excluyen las rutas predeterminadas para un rol o característica.</span><span class="sxs-lookup"><span data-stu-id="c3074-124">In Windows Server 2016 and Windows Server 2019, the predefined exclusions delivered by Security intelligence updates only exclude the default paths for a role or feature.</span></span> <span data-ttu-id="c3074-125">Si instaló un rol o una característica en una ruta de acceso personalizada o desea controlar manualmente el conjunto de exclusiones, asegúrese de no participar en las exclusiones automáticas que se entregan en Actualizaciones de inteligencia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="c3074-125">If you installed a role or feature in a custom path, or you want to manually control the set of exclusions, make sure to opt out of the automatic exclusions delivered in Security intelligence updates.</span></span> <span data-ttu-id="c3074-126">Pero tenga en cuenta que las exclusiones que se entregan automáticamente están optimizadas para los roles Windows Server 2016 y 2019.</span><span class="sxs-lookup"><span data-stu-id="c3074-126">But keep in mind that the exclusions that are delivered automatically are optimized for Windows Server 2016 and 2019 roles.</span></span> <span data-ttu-id="c3074-127">Consulte [Recomendaciones para definir exclusiones antes](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions) de definir las listas de exclusión.</span><span class="sxs-lookup"><span data-stu-id="c3074-127">See [Recommendations for defining exclusions](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions) before defining your exclusion lists.</span></span>

> [!WARNING]
> <span data-ttu-id="c3074-128">La exclusión automática puede afectar negativamente al rendimiento o provocar daños en los datos.</span><span class="sxs-lookup"><span data-stu-id="c3074-128">Opting out of automatic exclusions may adversely impact performance, or result in data corruption.</span></span> <span data-ttu-id="c3074-129">Las exclusiones que se entregan automáticamente se optimizan para Windows Server 2016 y Windows roles de Server 2019.</span><span class="sxs-lookup"><span data-stu-id="c3074-129">The exclusions that are delivered automatically are optimized for Windows Server 2016 and Windows Server 2019 roles.</span></span>

<span data-ttu-id="c3074-130">Dado que las exclusiones predefinidas solo excluyen las rutas predeterminadas **,** si mueve NTDS y SYSVOL a otra unidad o ruta de acceso que sea diferente de la ruta de acceso *original,* debe agregar exclusiones manualmente con la información aquí [.](configure-extension-file-exclusions-microsoft-defender-antivirus.md#configure-the-list-of-exclusions-based-on-folder-name-or-file-extension)</span><span class="sxs-lookup"><span data-stu-id="c3074-130">Because predefined exclusions only exclude **default paths**, if you move NTDS and SYSVOL to another drive or path that is *different from the original path*, you must add exclusions manually using the information [here](configure-extension-file-exclusions-microsoft-defender-antivirus.md#configure-the-list-of-exclusions-based-on-folder-name-or-file-extension) .</span></span>

<span data-ttu-id="c3074-131">Puede deshabilitar las listas de exclusión automática con la directiva de grupo, los cmdlets de PowerShell y WMI.</span><span class="sxs-lookup"><span data-stu-id="c3074-131">You can disable the automatic exclusion lists with Group Policy, PowerShell cmdlets, and WMI.</span></span>

### <a name="use-group-policy-to-disable-the-auto-exclusions-list-on-windows-server-2016-and-windows-server-2019"></a><span data-ttu-id="c3074-132">Usar la directiva de grupo para deshabilitar la lista de exclusiones automáticas en Windows Server 2016 y Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="c3074-132">Use Group Policy to disable the auto-exclusions list on Windows Server 2016 and Windows Server 2019</span></span>

1. <span data-ttu-id="c3074-133">En el equipo de administración de directivas de grupo, abra la [Consola de administración de directivas de grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc725752(v=ws.11)).</span><span class="sxs-lookup"><span data-stu-id="c3074-133">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc725752(v=ws.11)).</span></span> <span data-ttu-id="c3074-134">Haga clic con el botón secundario en el objeto de directiva de grupo que desea configurar y, a continuación, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="c3074-134">Right-click the Group Policy Object you want to configure, and then click **Edit**.</span></span>
2. <span data-ttu-id="c3074-135">En el **Editor de administración de directivas de** grupo, vaya a Configuración **del** equipo y, a continuación, haga clic en **Plantillas administrativas.**</span><span class="sxs-lookup"><span data-stu-id="c3074-135">In the **Group Policy Management Editor** go to **Computer configuration**, and then click **Administrative templates**.</span></span>
3. <span data-ttu-id="c3074-136">Expanda el árbol para **Windows componentes**  >  **Antivirus de Microsoft Defender**  >  **exclusiones**.</span><span class="sxs-lookup"><span data-stu-id="c3074-136">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Exclusions**.</span></span>
4. <span data-ttu-id="c3074-137">Haga doble clic **en Desactivar exclusiones automáticas** y establezca la opción en **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="c3074-137">Double-click **Turn off Auto Exclusions**, and set the option to **Enabled**.</span></span> <span data-ttu-id="c3074-138">Después, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c3074-138">Then click **OK**.</span></span> 

### <a name="use-powershell-cmdlets-to-disable-the-auto-exclusions-list-on-windows-server-2016-and-2019"></a><span data-ttu-id="c3074-139">Usar cmdlets de PowerShell para deshabilitar la lista de exclusiones automáticas en Windows Server 2016 y 2019</span><span class="sxs-lookup"><span data-stu-id="c3074-139">Use PowerShell cmdlets to disable the auto-exclusions list on Windows Server 2016 and 2019</span></span>

<span data-ttu-id="c3074-140">Use los cmdlets siguientes:</span><span class="sxs-lookup"><span data-stu-id="c3074-140">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -DisableAutoExclusions $true
```

<span data-ttu-id="c3074-141">Para obtener más información, consulte los siguientes recursos:</span><span class="sxs-lookup"><span data-stu-id="c3074-141">To learn more, see the following resources:</span></span>

- <span data-ttu-id="c3074-142">[Use cmdlets de PowerShell para configurar y ejecutar Antivirus de Microsoft Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="c3074-142">[Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md).</span></span>
- <span data-ttu-id="c3074-143">[Use PowerShell con Antivirus de Microsoft Defender](/powershell/module/defender/).</span><span class="sxs-lookup"><span data-stu-id="c3074-143">[Use PowerShell with Microsoft Defender Antivirus](/powershell/module/defender/).</span></span>

### <a name="use-windows-management-instruction-wmi-to-disable-the-auto-exclusions-list-on-windows-server-2016-and-windows-server-2019"></a><span data-ttu-id="c3074-144">Use Windows Management Instruction (WMI) para deshabilitar la lista de exclusiones automáticas en Windows Server 2016 y Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="c3074-144">Use Windows Management Instruction (WMI) to disable the auto-exclusions list on Windows Server 2016 and Windows Server 2019</span></span>

<span data-ttu-id="c3074-145">Utilice el **método Set** de la [clase MSFT_MpPreference](/previous-versions/windows/desktop/defender/msft-mppreference) para las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="c3074-145">Use the **Set** method of the [MSFT_MpPreference](/previous-versions/windows/desktop/defender/msft-mppreference) class for the following properties:</span></span>

```WMI
DisableAutoExclusions
```

<span data-ttu-id="c3074-146">Vea lo siguiente para obtener más información y parámetros permitidos:</span><span class="sxs-lookup"><span data-stu-id="c3074-146">See the following for more information and allowed parameters:</span></span>
- [<span data-ttu-id="c3074-147">Windows Defender API wmiv2</span><span class="sxs-lookup"><span data-stu-id="c3074-147">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="list-of-automatic-exclusions"></a><span data-ttu-id="c3074-148">Lista de exclusiones automáticas</span><span class="sxs-lookup"><span data-stu-id="c3074-148">List of automatic exclusions</span></span>

<span data-ttu-id="c3074-149">Las secciones siguientes contienen las exclusiones que se entregan con rutas de acceso de archivo de exclusiones automáticas y tipos de archivo.</span><span class="sxs-lookup"><span data-stu-id="c3074-149">The following sections contain the exclusions that are delivered with automatic exclusions file paths and file types.</span></span>

### <a name="default-exclusions-for-all-roles"></a><span data-ttu-id="c3074-150">Exclusiones predeterminadas para todos los roles</span><span class="sxs-lookup"><span data-stu-id="c3074-150">Default exclusions for all roles</span></span>

<span data-ttu-id="c3074-151">En esta sección se enumeran las exclusiones predeterminadas para todos los Windows Server 2016 y 2019.</span><span class="sxs-lookup"><span data-stu-id="c3074-151">This section lists the default exclusions for all Windows Server 2016 and 2019 roles.</span></span>

> [!NOTE]
> <span data-ttu-id="c3074-152">Las ubicaciones predeterminadas pueden ser diferentes de las que se enumeran en este artículo.</span><span class="sxs-lookup"><span data-stu-id="c3074-152">The default locations could be different than what's listed in this article.</span></span>

#### <a name="windows-tempedb-files"></a><span data-ttu-id="c3074-153">Windows Archivos "temp.edb"</span><span class="sxs-lookup"><span data-stu-id="c3074-153">Windows "temp.edb" files</span></span>

- `%windir%\SoftwareDistribution\Datastore\*\tmp.edb`
- `%ProgramData%\Microsoft\Search\Data\Applications\Windows\*\*.log`

#### <a name="windows-update-files-or-automatic-update-files"></a><span data-ttu-id="c3074-154">Windows Actualizar archivos o archivos de actualización automática</span><span class="sxs-lookup"><span data-stu-id="c3074-154">Windows Update files or Automatic Update files</span></span>

- `%windir%\SoftwareDistribution\Datastore\*\Datastore.edb`
- `%windir%\SoftwareDistribution\Datastore\*\edb.chk`
- `%windir%\SoftwareDistribution\Datastore\*\edb\*.log`
- `%windir%\SoftwareDistribution\Datastore\*\Edb\*.jrs`
- `%windir%\SoftwareDistribution\Datastore\*\Res\*.log`

#### <a name="windows-security-files"></a><span data-ttu-id="c3074-155">Seguridad de Windows archivos</span><span class="sxs-lookup"><span data-stu-id="c3074-155">Windows Security files</span></span>

- `%windir%\Security\database\*.chk`
- `%windir%\Security\database\*.edb`
- `%windir%\Security\database\*.jrs`
- `%windir%\Security\database\*.log`
- `%windir%\Security\database\*.sdb`

#### <a name="group-policy-files"></a><span data-ttu-id="c3074-156">Archivos de directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="c3074-156">Group Policy files</span></span>

- `%allusersprofile%\NTUser.pol`
- `%SystemRoot%\System32\GroupPolicy\Machine\registry.pol`
- `%SystemRoot%\System32\GroupPolicy\User\registry.pol`

#### <a name="wins-files"></a><span data-ttu-id="c3074-157">Archivos WINS</span><span class="sxs-lookup"><span data-stu-id="c3074-157">WINS files</span></span>

- `%systemroot%\System32\Wins\*\*.chk`
- `%systemroot%\System32\Wins\*\*.log`
- `%systemroot%\System32\Wins\*\*.mdb`
- `%systemroot%\System32\LogFiles\`
- `%systemroot%\SysWow64\LogFiles\`

#### <a name="file-replication-service-frs-exclusions"></a><span data-ttu-id="c3074-158">Exclusiones del Servicio de replicación de archivos (FRS)</span><span class="sxs-lookup"><span data-stu-id="c3074-158">File Replication Service (FRS) exclusions</span></span>

- <span data-ttu-id="c3074-159">Archivos en la carpeta de trabajo servicio de replicación de archivos (FRS).</span><span class="sxs-lookup"><span data-stu-id="c3074-159">Files in the File Replication Service (FRS) working folder.</span></span> <span data-ttu-id="c3074-160">La carpeta de trabajo de FRS se especifica en la clave del Registro `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NtFrs\Parameters\Working Directory`</span><span class="sxs-lookup"><span data-stu-id="c3074-160">The FRS working folder is specified in the registry key `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NtFrs\Parameters\Working Directory`</span></span>

  - `%windir%\Ntfrs\jet\sys\*\edb.chk`
  - `%windir%\Ntfrs\jet\*\Ntfrs.jdb`
  - `%windir%\Ntfrs\jet\log\*\*.log`

- <span data-ttu-id="c3074-161">Archivos de registro de base de datos FRS.</span><span class="sxs-lookup"><span data-stu-id="c3074-161">FRS Database log files.</span></span> <span data-ttu-id="c3074-162">La carpeta de archivos de registro de base de datos FRS se especifica en la clave del Registro `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\Ntfrs\Parameters\DB Log File Directory`</span><span class="sxs-lookup"><span data-stu-id="c3074-162">The FRS Database log file folder is specified in the registry key `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\Ntfrs\Parameters\DB Log File Directory`</span></span>

  - `%windir%\Ntfrs\*\Edb\*.log`

- <span data-ttu-id="c3074-163">La carpeta de almacenamiento provisional de FRS.</span><span class="sxs-lookup"><span data-stu-id="c3074-163">The FRS staging folder.</span></span> <span data-ttu-id="c3074-164">La carpeta provisional se especifica en la clave del Registro `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NtFrs\Parameters\Replica Sets\GUID\Replica Set Stage`</span><span class="sxs-lookup"><span data-stu-id="c3074-164">The staging folder is specified in the registry key `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NtFrs\Parameters\Replica Sets\GUID\Replica Set Stage`</span></span>

  - `%systemroot%\Sysvol\*\Ntfrs_cmp*\`

- <span data-ttu-id="c3074-165">La carpeta de preinstalación frs.</span><span class="sxs-lookup"><span data-stu-id="c3074-165">The FRS preinstall folder.</span></span> <span data-ttu-id="c3074-166">Esta carpeta se especifica mediante la carpeta `Replica_root\DO_NOT_REMOVE_NtFrs_PreInstall_Directory`</span><span class="sxs-lookup"><span data-stu-id="c3074-166">This folder is specified by the folder `Replica_root\DO_NOT_REMOVE_NtFrs_PreInstall_Directory`</span></span>

  - `%systemroot%\SYSVOL\domain\DO_NOT_REMOVE_NtFrs_PreInstall_Directory\*\Ntfrs*\`

- <span data-ttu-id="c3074-167">La base de datos de replicación del sistema de archivos distribuido (DFSR) y las carpetas de trabajo.</span><span class="sxs-lookup"><span data-stu-id="c3074-167">The Distributed File System Replication (DFSR) database and working folders.</span></span> <span data-ttu-id="c3074-168">Estas carpetas se especifican mediante la clave del Registro `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\DFSR\Parameters\Replication Groups\GUID\Replica Set Configuration File`</span><span class="sxs-lookup"><span data-stu-id="c3074-168">These folders are specified by the registry key `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\DFSR\Parameters\Replication Groups\GUID\Replica Set Configuration File`</span></span>

  > [!NOTE]
  > <span data-ttu-id="c3074-169">Para las ubicaciones personalizadas, vea [Opt out of automatic exclusions](#opt-out-of-automatic-exclusions).</span><span class="sxs-lookup"><span data-stu-id="c3074-169">For custom locations, see [Opt out of automatic exclusions](#opt-out-of-automatic-exclusions).</span></span>

  - `%systemdrive%\System Volume Information\DFSR\$db_normal$`
  - `%systemdrive%\System Volume Information\DFSR\FileIDTable_*`
  - `%systemdrive%\System Volume Information\DFSR\SimilarityTable_*`
  - `%systemdrive%\System Volume Information\DFSR\*.XML`
  - `%systemdrive%\System Volume Information\DFSR\$db_dirty$`
  - `%systemdrive%\System Volume Information\DFSR\$db_clean$`
  - `%systemdrive%\System Volume Information\DFSR\$db_lostl$`
  - `%systemdrive%\System Volume Information\DFSR\Dfsr.db`
  - `%systemdrive%\System Volume Information\DFSR\*.frx`
  - `%systemdrive%\System Volume Information\DFSR\*.log`
  - `%systemdrive%\System Volume Information\DFSR\Fsr*.jrs`
  - `%systemdrive%\System Volume Information\DFSR\Tmp.edb`

#### <a name="process-exclusions"></a><span data-ttu-id="c3074-170">Exclusiones de procesos</span><span class="sxs-lookup"><span data-stu-id="c3074-170">Process exclusions</span></span>

- `%systemroot%\System32\dfsr.exe`
- `%systemroot%\System32\dfsrs.exe`

#### <a name="hyper-v-exclusions"></a><span data-ttu-id="c3074-171">Exclusiones de Hyper-V</span><span class="sxs-lookup"><span data-stu-id="c3074-171">Hyper-V exclusions</span></span>

<span data-ttu-id="c3074-172">En la tabla siguiente se enumeran las exclusiones de tipo de archivo, las exclusiones de carpetas y las exclusiones de proceso que se entregan automáticamente al instalar el rol de Hyper-V.</span><span class="sxs-lookup"><span data-stu-id="c3074-172">The following table lists the file type exclusions, folder exclusions, and process exclusions that are delivered automatically when you install the Hyper-V role.</span></span>

|<span data-ttu-id="c3074-173">Exclusiones de tipos de archivo</span><span class="sxs-lookup"><span data-stu-id="c3074-173">File type exclusions</span></span> |<span data-ttu-id="c3074-174">Exclusiones de carpetas</span><span class="sxs-lookup"><span data-stu-id="c3074-174">Folder exclusions</span></span>  | <span data-ttu-id="c3074-175">Process exclusions</span><span class="sxs-lookup"><span data-stu-id="c3074-175">Process exclusions</span></span> |
|:--|:--|:--|
| `*.vhd` <br/> `*.vhdx` <br/> `*.avhd` <br/> `*.avhdx` <br/> `*.vsv` <br/> `*.iso` <br/> `*.rct` <br/> `*.vmcx` <br/> `*.vmrs` | `%ProgramData%\Microsoft\Windows\Hyper-V` <br/> `%ProgramFiles%\Hyper-V` <br/> `%SystemDrive%\ProgramData\Microsoft\Windows\Hyper-V\Snapshots` <br/> `%Public%\Documents\Hyper-V\Virtual Hard Disks` | `%systemroot%\System32\Vmms.exe` <br/> `%systemroot%\System32\Vmwp.exe` |

#### <a name="sysvol-files"></a><span data-ttu-id="c3074-176">Archivos SYSVOL</span><span class="sxs-lookup"><span data-stu-id="c3074-176">SYSVOL files</span></span>

- `%systemroot%\Sysvol\Domain\*.adm`
- `%systemroot%\Sysvol\Domain\*.admx`
- `%systemroot%\Sysvol\Domain\*.adml`
- `%systemroot%\Sysvol\Domain\Registry.pol`
- `%systemroot%\Sysvol\Domain\*.aas`
- `%systemroot%\Sysvol\Domain\*.inf`
- `%systemroot%\Sysvol\Domain\*Scripts.ini`
- `%systemroot%\Sysvol\Domain\*.ins`
- `%systemroot%\Sysvol\Domain\Oscfilter.ini`


### <a name="active-directory-exclusions"></a><span data-ttu-id="c3074-177">Exclusiones de Active Directory</span><span class="sxs-lookup"><span data-stu-id="c3074-177">Active Directory exclusions</span></span>

<span data-ttu-id="c3074-178">En esta sección se enumeran las exclusiones que se entregan automáticamente al instalar los Servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c3074-178">This section lists the exclusions that are delivered automatically when you install Active Directory Domain Services.</span></span>

#### <a name="ntds-database-files"></a><span data-ttu-id="c3074-179">Archivos de base de datos NTDS</span><span class="sxs-lookup"><span data-stu-id="c3074-179">NTDS database files</span></span>

<span data-ttu-id="c3074-180">Los archivos de base de datos se especifican en la clave del Registro `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\DSA Database File`</span><span class="sxs-lookup"><span data-stu-id="c3074-180">The database files are specified in the registry key `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\DSA Database File`</span></span>

- `%windir%\Ntds\ntds.dit`
- `%windir%\Ntds\ntds.pat`

#### <a name="the-ad-ds-transaction-log-files"></a><span data-ttu-id="c3074-181">Los archivos de registro de transacciones de AD DS</span><span class="sxs-lookup"><span data-stu-id="c3074-181">The AD DS transaction log files</span></span>

<span data-ttu-id="c3074-182">Los archivos de registro de transacciones se especifican en la clave del Registro `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\Database Log Files Path`</span><span class="sxs-lookup"><span data-stu-id="c3074-182">The transaction log files are specified in the registry key `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\Database Log Files Path`</span></span>

- `%windir%\Ntds\EDB*.log`
- `%windir%\Ntds\Res*.log`
- `%windir%\Ntds\Edb*.jrs`
- `%windir%\Ntds\Ntds*.pat`
- `%windir%\Ntds\TEMP.edb`

#### <a name="the-ntds-working-folder"></a><span data-ttu-id="c3074-183">La carpeta de trabajo NTDS</span><span class="sxs-lookup"><span data-stu-id="c3074-183">The NTDS working folder</span></span>

<span data-ttu-id="c3074-184">Esta carpeta se especifica en la clave del Registro `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\DSA Working Directory`</span><span class="sxs-lookup"><span data-stu-id="c3074-184">This folder is specified in the registry key `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\DSA Working Directory`</span></span>

- `%windir%\Ntds\Temp.edb`
- `%windir%\Ntds\Edb.chk`

#### <a name="process-exclusions-for-ad-ds-and-ad-ds-related-support-files"></a><span data-ttu-id="c3074-185">Exclusiones de procesos para archivos de soporte técnico relacionados con AD DS y AD DS</span><span class="sxs-lookup"><span data-stu-id="c3074-185">Process exclusions for AD DS and AD DS-related support files</span></span>

- `%systemroot%\System32\ntfrs.exe`
- `%systemroot%\System32\lsass.exe`

### <a name="dhcp-server-exclusions"></a><span data-ttu-id="c3074-186">Exclusiones del servidor DHCP</span><span class="sxs-lookup"><span data-stu-id="c3074-186">DHCP Server exclusions</span></span>

<span data-ttu-id="c3074-187">En esta sección se enumeran las exclusiones que se entregan automáticamente al instalar el rol de servidor DHCP.</span><span class="sxs-lookup"><span data-stu-id="c3074-187">This section lists the exclusions that are delivered automatically when you install the DHCP Server role.</span></span> <span data-ttu-id="c3074-188">Las ubicaciones de archivos del servidor DHCP se especifican mediante los parámetros *DatabasePath*, *DhcpLogFilePath* y *BackupDatabasePath* en la clave del Registro. `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\DHCPServer\Parameters`</span><span class="sxs-lookup"><span data-stu-id="c3074-188">The DHCP Server file locations are specified by the *DatabasePath*, *DhcpLogFilePath*, and *BackupDatabasePath* parameters in the registry key `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\DHCPServer\Parameters`</span></span>

- `%systemroot%\System32\DHCP\*\*.mdb`
- `%systemroot%\System32\DHCP\*\*.pat`
- `%systemroot%\System32\DHCP\*\*.log`
- `%systemroot%\System32\DHCP\*\*.chk`
- `%systemroot%\System32\DHCP\*\*.edb`

### <a name="dns-server-exclusions"></a><span data-ttu-id="c3074-189">Exclusiones del servidor DNS</span><span class="sxs-lookup"><span data-stu-id="c3074-189">DNS Server exclusions</span></span>

<span data-ttu-id="c3074-190">En esta sección se enumeran las exclusiones de archivos y carpetas y las exclusiones de proceso que se entregan automáticamente al instalar el rol servidor DNS.</span><span class="sxs-lookup"><span data-stu-id="c3074-190">This section lists the file and folder exclusions and the process exclusions that are delivered automatically when you install the DNS Server role.</span></span>

#### <a name="file-and-folder-exclusions-for-the-dns-server-role"></a><span data-ttu-id="c3074-191">Exclusiones de archivos y carpetas para el rol servidor DNS</span><span class="sxs-lookup"><span data-stu-id="c3074-191">File and folder exclusions for the DNS Server role</span></span>

- `%systemroot%\System32\Dns\*\*.log`
- `%systemroot%\System32\Dns\*\*.dns`
- `%systemroot%\System32\Dns\*\*.scc`
- `%systemroot%\System32\Dns\*\BOOT`

#### <a name="process-exclusions-for-the-dns-server-role"></a><span data-ttu-id="c3074-192">Procesar exclusiones para el rol de servidor DNS</span><span class="sxs-lookup"><span data-stu-id="c3074-192">Process exclusions for the DNS Server role</span></span>

- `%systemroot%\System32\dns.exe`

### <a name="file-and-storage-services-exclusions"></a><span data-ttu-id="c3074-193">Exclusiones de Storage de archivos y servicios</span><span class="sxs-lookup"><span data-stu-id="c3074-193">File and Storage Services exclusions</span></span>

<span data-ttu-id="c3074-194">En esta sección se enumeran las exclusiones de archivos y carpetas que se entregan automáticamente al instalar el rol Archivo y Storage servicios.</span><span class="sxs-lookup"><span data-stu-id="c3074-194">This section lists the file and folder exclusions that are delivered automatically when you install the File and Storage Services role.</span></span> <span data-ttu-id="c3074-195">Las exclusiones enumeradas a continuación no incluyen exclusiones para el rol Agrupación en clústeres.</span><span class="sxs-lookup"><span data-stu-id="c3074-195">The exclusions listed below do not include exclusions for the Clustering role.</span></span>

- `%SystemDrive%\ClusterStorage`
- `%clusterserviceaccount%\Local Settings\Temp`
- `%SystemDrive%\mscs`

### <a name="print-server-exclusions"></a><span data-ttu-id="c3074-196">Exclusiones del servidor de impresión</span><span class="sxs-lookup"><span data-stu-id="c3074-196">Print Server exclusions</span></span>

<span data-ttu-id="c3074-197">En esta sección se enumeran las exclusiones de tipo de archivo, las exclusiones de carpetas y las exclusiones de proceso que se entregan automáticamente al instalar el rol Servidor de impresión.</span><span class="sxs-lookup"><span data-stu-id="c3074-197">This section lists the file type exclusions, folder exclusions, and the process exclusions that are delivered automatically when you install the Print Server role.</span></span>

#### <a name="file-type-exclusions"></a><span data-ttu-id="c3074-198">Exclusiones de tipos de archivo</span><span class="sxs-lookup"><span data-stu-id="c3074-198">File type exclusions</span></span>

- `*.shd`
- `*.spl`

#### <a name="folder-exclusions"></a><span data-ttu-id="c3074-199">Exclusiones de carpetas</span><span class="sxs-lookup"><span data-stu-id="c3074-199">Folder exclusions</span></span>

<span data-ttu-id="c3074-200">Esta carpeta se especifica en la clave del Registro `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Print\Printers\DefaultSpoolDirectory`</span><span class="sxs-lookup"><span data-stu-id="c3074-200">This folder is specified in the registry key `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Print\Printers\DefaultSpoolDirectory`</span></span>

- `%system32%\spool\printers\*`

#### <a name="process-exclusions"></a><span data-ttu-id="c3074-201">Exclusiones de procesos</span><span class="sxs-lookup"><span data-stu-id="c3074-201">Process exclusions</span></span>

- `spoolsv.exe`

### <a name="web-server-exclusions"></a><span data-ttu-id="c3074-202">Exclusiones de servidor web</span><span class="sxs-lookup"><span data-stu-id="c3074-202">Web Server exclusions</span></span>

<span data-ttu-id="c3074-203">En esta sección se enumeran las exclusiones de carpetas y las exclusiones de proceso que se entregan automáticamente al instalar el rol servidor web.</span><span class="sxs-lookup"><span data-stu-id="c3074-203">This section lists the folder exclusions and the process exclusions that are delivered automatically when you install the Web Server role.</span></span>

#### <a name="folder-exclusions"></a><span data-ttu-id="c3074-204">Exclusiones de carpetas</span><span class="sxs-lookup"><span data-stu-id="c3074-204">Folder exclusions</span></span>

- `%SystemRoot%\IIS Temporary Compressed Files`
- `%SystemDrive%\inetpub\temp\IIS Temporary Compressed Files`
- `%SystemDrive%\inetpub\temp\ASP Compiled Templates`
- `%systemDrive%\inetpub\logs`
- `%systemDrive%\inetpub\wwwroot`

#### <a name="process-exclusions"></a><span data-ttu-id="c3074-205">Process exclusions</span><span class="sxs-lookup"><span data-stu-id="c3074-205">Process exclusions</span></span>

- `%SystemRoot%\system32\inetsrv\w3wp.exe`
- `%SystemRoot%\SysWOW64\inetsrv\w3wp.exe`
- `%SystemDrive%\PHP5433\php-cgi.exe`

#### <a name="turning-off-scanning-of-files-in-the-sysvolsysvol-folder-or-the-sysvol_dfsrsysvol-folder"></a><span data-ttu-id="c3074-206">Desactivar el examen de archivos en la carpeta Sysvol\Sysvol o en la carpeta SYSVOL_DFSR\Sysvol</span><span class="sxs-lookup"><span data-stu-id="c3074-206">Turning off scanning of files in the Sysvol\Sysvol folder or the SYSVOL_DFSR\Sysvol folder</span></span>

<span data-ttu-id="c3074-207">La ubicación actual de la carpeta or y todas las subcarpetas es el destino de reeplo de sistema de archivos `Sysvol\Sysvol` de la raíz del conjunto de `SYSVOL_DFSR\Sysvol` réplicas.</span><span class="sxs-lookup"><span data-stu-id="c3074-207">The current location of the `Sysvol\Sysvol` or `SYSVOL_DFSR\Sysvol` folder and all the subfolders is the file system reparse target of the replica set root.</span></span> <span data-ttu-id="c3074-208">Las `Sysvol\Sysvol` `SYSVOL_DFSR\Sysvol` carpetas y usan las siguientes ubicaciones de forma predeterminada:</span><span class="sxs-lookup"><span data-stu-id="c3074-208">The `Sysvol\Sysvol` and `SYSVOL_DFSR\Sysvol` folders use the following locations by default:</span></span>

- `%systemroot%\Sysvol\Domain`
- `%systemroot%\Sysvol_DFSR\Domain`

<span data-ttu-id="c3074-209">El recurso compartido NETLOGON hace referencia a la ruta de acceso al recurso compartido NETLOGON y puede determinarse mediante el nombre del valor `SYSVOL` SysVol en la siguiente subclave: `HKEY_LOCAL_MACHINE\SYSTEM\ControlSet001\Services\Netlogon\Parameters`</span><span class="sxs-lookup"><span data-stu-id="c3074-209">The path to the currently active `SYSVOL` is referenced by the NETLOGON share and can be determined by the SysVol value name in the following subkey: `HKEY_LOCAL_MACHINE\SYSTEM\ControlSet001\Services\Netlogon\Parameters`</span></span>

<span data-ttu-id="c3074-210">Excluya los siguientes archivos de esta carpeta y todas sus subcarpetas:</span><span class="sxs-lookup"><span data-stu-id="c3074-210">Exclude the following files from this folder and all its subfolders:</span></span>

- `*.adm`
- `*.admx`
- `*.adml`
- `Registry.pol`
- `Registry.tmp`
- `*.aas`
- `*.inf`
- `Scripts.ini`
- `*.ins`
- `Oscfilter.ini`

### <a name="windows-server-update-services-exclusions"></a><span data-ttu-id="c3074-211">Windows Server Update Services exclusiones</span><span class="sxs-lookup"><span data-stu-id="c3074-211">Windows Server Update Services exclusions</span></span>

<span data-ttu-id="c3074-212">En esta sección se enumeran las exclusiones de carpetas que se entregan automáticamente al instalar el rol Windows Server Update Services (WSUS).</span><span class="sxs-lookup"><span data-stu-id="c3074-212">This section lists the folder exclusions that are delivered automatically when you install the Windows Server Update Services (WSUS) role.</span></span> <span data-ttu-id="c3074-213">La carpeta WSUS se especifica en la clave del Registro `HKEY_LOCAL_MACHINE\Software\Microsoft\Update Services\Server\Setup`</span><span class="sxs-lookup"><span data-stu-id="c3074-213">The WSUS folder is specified in the registry key `HKEY_LOCAL_MACHINE\Software\Microsoft\Update Services\Server\Setup`</span></span>

- `%systemroot%\WSUS\WSUSContent`
- `%systemroot%\WSUS\UpdateServicesDBFiles`
- `%systemroot%\SoftwareDistribution\Datastore`
- `%systemroot%\SoftwareDistribution\Download`

## <a name="see-also"></a><span data-ttu-id="c3074-214">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c3074-214">See also</span></span>

- [<span data-ttu-id="c3074-215">Configurar y validar exclusiones para Antivirus de Microsoft Defender exámenes</span><span class="sxs-lookup"><span data-stu-id="c3074-215">Configure and validate exclusions for Microsoft Defender Antivirus scans</span></span>](configure-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="c3074-216">Configurar y validar exclusiones según el nombre de archivo, la extensión y la ubicación de la carpeta</span><span class="sxs-lookup"><span data-stu-id="c3074-216">Configure and validate exclusions based on file name, extension, and folder location</span></span>](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="c3074-217">Configurar y validar exclusiones para archivos abiertos por procesos</span><span class="sxs-lookup"><span data-stu-id="c3074-217">Configure and validate exclusions for files opened by processes</span></span>](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="c3074-218">Errores comunes para evitarlos cuando se definen exclusiones</span><span class="sxs-lookup"><span data-stu-id="c3074-218">Common mistakes to avoid when defining exclusions</span></span>](common-exclusion-mistakes-microsoft-defender-antivirus.md)
- [<span data-ttu-id="c3074-219">Personalizar, iniciar y revisar los resultados de Antivirus de Microsoft Defender análisis y corrección</span><span class="sxs-lookup"><span data-stu-id="c3074-219">Customize, initiate, and review the results of Microsoft Defender Antivirus scans and remediation</span></span>](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="c3074-220">Antivirus de Microsoft Defender en Windows 10</span><span class="sxs-lookup"><span data-stu-id="c3074-220">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)