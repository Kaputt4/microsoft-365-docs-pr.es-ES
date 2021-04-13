---
title: Programar exámenes rápidos y completos regulares con Antivirus de Microsoft Defender
description: Configurar exámenes periódicos (programados), incluso cuándo deben ejecutarse y si se ejecutan como exámenes rápidos o completos
keywords: examen rápido, examen completo, rápido vs completo, examen de programación, diario, semanal, hora, programado, periódico, regular
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 11/02/2020
ms.reviewer: pauhijbr
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 66907fca7a117eeba7ca0b9bd95d59af24c31341
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691303"
---
# <a name="configure-scheduled-quick-or-full-microsoft-defender-antivirus-scans"></a><span data-ttu-id="b2af4-104">Configurar exámenes programados rápidos o completos de Antivirus de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="b2af4-104">Configure scheduled quick or full Microsoft Defender Antivirus scans</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="b2af4-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="b2af4-105">**Applies to:**</span></span>

- [<span data-ttu-id="b2af4-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="b2af4-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)


> [!NOTE]
> <span data-ttu-id="b2af4-107">De forma predeterminada, Antivirus de Microsoft Defender busca una actualización 15 minutos antes de la hora de los exámenes programados.</span><span class="sxs-lookup"><span data-stu-id="b2af4-107">By default, Microsoft Defender Antivirus checks for an update 15 minutes before the time of any scheduled scans.</span></span> <span data-ttu-id="b2af4-108">Puede administrar [la programación de cuándo se](manage-protection-update-schedule-microsoft-defender-antivirus.md) deben descargar y aplicar las actualizaciones de protección para invalidar este valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="b2af4-108">You can [Manage the schedule for when protection updates should be downloaded and applied](manage-protection-update-schedule-microsoft-defender-antivirus.md) to override this default.</span></span> 

<span data-ttu-id="b2af4-109">Además de la protección siempre activa [](run-scan-microsoft-defender-antivirus.md) en tiempo real y los exámenes a petición, puede configurar exámenes regulares programados.</span><span class="sxs-lookup"><span data-stu-id="b2af4-109">In addition to always-on real-time protection and [on-demand](run-scan-microsoft-defender-antivirus.md) scans, you can set up regular, scheduled scans.</span></span> 

<span data-ttu-id="b2af4-110">Puede configurar el tipo de examen, cuándo debe producirse el [](manage-protection-updates-microsoft-defender-antivirus.md) examen y si el examen debe producirse después de una actualización de protección o si se está utilizando el extremo.</span><span class="sxs-lookup"><span data-stu-id="b2af4-110">You can configure the type of scan, when the scan should occur, and if the scan should occur after a [protection update](manage-protection-updates-microsoft-defender-antivirus.md) or if the endpoint is being used.</span></span> <span data-ttu-id="b2af4-111">También puede especificar cuándo deben producirse exámenes especiales para completar la corrección.</span><span class="sxs-lookup"><span data-stu-id="b2af4-111">You can also specify when special scans to complete remediation should occur.</span></span>

<span data-ttu-id="b2af4-112">En este artículo se describe cómo configurar exámenes programados con directiva de grupo, cmdlets de PowerShell y WMI.</span><span class="sxs-lookup"><span data-stu-id="b2af4-112">This article describes how to configure scheduled scans with Group Policy, PowerShell cmdlets, and WMI.</span></span> <span data-ttu-id="b2af4-113">También puede configurar exámenes de programación con [Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scheduled-scans-settings) o Microsoft [Intune](/mem/intune/configuration/device-restrictions-windows-10).</span><span class="sxs-lookup"><span data-stu-id="b2af4-113">You can also configure schedules scans with [Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scheduled-scans-settings) or [Microsoft Intune](/mem/intune/configuration/device-restrictions-windows-10).</span></span>

## <a name="to-configure-the-group-policy-settings-described-in-this-article"></a><span data-ttu-id="b2af4-114">Para configurar las opciones de directiva de grupo descritas en este artículo</span><span class="sxs-lookup"><span data-stu-id="b2af4-114">To configure the Group Policy settings described in this article</span></span>

1.  <span data-ttu-id="b2af4-115">En el equipo de administración de directivas de grupo, abra la Consola de administración de directivas de [grupo,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))haga clic con el botón secundario en el objeto de directiva de grupo que desea configurar y haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="b2af4-115">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

3.  <span data-ttu-id="b2af4-116">En el **Editor de administración de directivas de grupo** vaya a Configuración del **equipo.**</span><span class="sxs-lookup"><span data-stu-id="b2af4-116">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

4.  <span data-ttu-id="b2af4-117">Haga clic **en Plantillas administrativas**.</span><span class="sxs-lookup"><span data-stu-id="b2af4-117">Click **Administrative templates**.</span></span>

5.  <span data-ttu-id="b2af4-118">Expande el árbol a **componentes de Windows > Antivirus** de Microsoft Defender y, a continuación, la **ubicación** especificada en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="b2af4-118">Expand the tree to **Windows components > Microsoft Defender Antivirus** and then the **Location** specified in the table below.</span></span>

6. <span data-ttu-id="b2af4-119">Haga doble clic en la configuración **de directiva** especificada en la tabla siguiente y establezca la opción en la configuración deseada.</span><span class="sxs-lookup"><span data-stu-id="b2af4-119">Double-click the policy **Setting** as specified in the table below, and set the option to your desired configuration.</span></span> 

7. <span data-ttu-id="b2af4-120">Haga **clic en** Aceptar y repita cualquier otra configuración.</span><span class="sxs-lookup"><span data-stu-id="b2af4-120">Click **OK**, and repeat for any other settings.</span></span>

<span data-ttu-id="b2af4-121">Vea también administrar cuándo [se deben](manage-protection-update-schedule-microsoft-defender-antivirus.md) descargar y aplicar las actualizaciones de protección y Evitar o permitir que los usuarios [modifiquen localmente los](configure-local-policy-overrides-microsoft-defender-antivirus.md) temas de configuración de directivas.</span><span class="sxs-lookup"><span data-stu-id="b2af4-121">Also see the [Manage when protection updates should be downloaded and applied](manage-protection-update-schedule-microsoft-defender-antivirus.md) and [Prevent or allow users to locally modify policy settings](configure-local-policy-overrides-microsoft-defender-antivirus.md) topics.</span></span>

## <a name="quick-scan-versus-full-scan-and-custom-scan"></a><span data-ttu-id="b2af4-122">Examen rápido frente a examen completo y examen personalizado</span><span class="sxs-lookup"><span data-stu-id="b2af4-122">Quick scan versus full scan and custom scan</span></span>

<span data-ttu-id="b2af4-123">Al configurar exámenes programados, puede configurar si el examen debe ser un examen completo o rápido.</span><span class="sxs-lookup"><span data-stu-id="b2af4-123">When you set up scheduled scans, you can set up whether the scan should be a full or quick scan.</span></span>

<span data-ttu-id="b2af4-124">Los exámenes rápidos examinan todas las ubicaciones donde podría haber malware registrado para empezar con el sistema, como las claves del Registro y las carpetas de inicio conocidas de Windows.</span><span class="sxs-lookup"><span data-stu-id="b2af4-124">Quick scans look at all the locations where there could be malware registered to start with the system, such as registry keys and known Windows startup folders.</span></span> 

<span data-ttu-id="b2af4-125">Combinado con la funcionalidad de protección siempre activa en tiempo [real](configure-real-time-protection-microsoft-defender-antivirus.md) , que revisa los archivos cuando se abren y cierran, y siempre que un usuario navega a una carpeta, un examen rápido ayuda a proporcionar una cobertura segura tanto para malware que comienza con el malware del sistema como del nivel de kernel.</span><span class="sxs-lookup"><span data-stu-id="b2af4-125">Combined with [always-on real-time protection capability](configure-real-time-protection-microsoft-defender-antivirus.md) - which reviews files when they are opened and closed, and whenever a user navigates to a folder - a quick scan helps provide strong coverage both for malware that starts with the system and kernel-level malware.</span></span>  

<span data-ttu-id="b2af4-126">En la mayoría de los casos, esto significa que un examen rápido es adecuado para encontrar malware que no fue detectado por la protección en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="b2af4-126">In most instances, this means a quick scan is adequate to find malware that wasn't picked up by real-time protection.</span></span>

<span data-ttu-id="b2af4-127">Un examen completo puede ser útil en los puntos de conexión que han encontrado una amenaza de malware para identificar si hay componentes inactivos que requieren una limpieza más exhaustiva.</span><span class="sxs-lookup"><span data-stu-id="b2af4-127">A full scan can be useful on endpoints that have encountered a malware threat to identify if there are any inactive components that require a more thorough clean-up.</span></span> <span data-ttu-id="b2af4-128">En este caso, es posible que desee usar un examen completo al ejecutar un examen a [petición.](run-scan-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="b2af4-128">In this instance, you may want to use a full scan when running an [on-demand scan](run-scan-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="b2af4-129">Un examen personalizado le permite especificar los archivos y carpetas que desea examinar, como una unidad USB.</span><span class="sxs-lookup"><span data-stu-id="b2af4-129">A custom scan allows you to specify the files and folders to scan, such as a USB drive.</span></span> 

>[!NOTE]
><span data-ttu-id="b2af4-130">De forma predeterminada, los exámenes rápidos se ejecutan en dispositivos extraíbles montados, como unidades USB.</span><span class="sxs-lookup"><span data-stu-id="b2af4-130">By default, quick scans run on mounted removable devices, such as USB drives.</span></span>

## <a name="set-up-scheduled-scans"></a><span data-ttu-id="b2af4-131">Configurar exámenes programados</span><span class="sxs-lookup"><span data-stu-id="b2af4-131">Set up scheduled scans</span></span>

<span data-ttu-id="b2af4-132">Los exámenes programados se ejecutarán en el día y la hora que especifique.</span><span class="sxs-lookup"><span data-stu-id="b2af4-132">Scheduled scans will run at the day and time you specify.</span></span> <span data-ttu-id="b2af4-133">Puede usar la directiva de grupo, PowerShell y WMI para configurar exámenes programados.</span><span class="sxs-lookup"><span data-stu-id="b2af4-133">You can use Group Policy, PowerShell, and WMI to configure scheduled scans.</span></span>

>[!NOTE]
><span data-ttu-id="b2af4-134">Si un equipo se desconecta y se ejecuta en la batería durante un examen completo programado, el examen programado se detendrá con el evento 1002, que indica que el examen se detuvo antes de finalizar.</span><span class="sxs-lookup"><span data-stu-id="b2af4-134">If a computer is unplugged and running on battery during a scheduled full scan, the scheduled scan will stop with event 1002, which states that the scan stopped before completion.</span></span> <span data-ttu-id="b2af4-135">Antivirus de Microsoft Defender ejecutará un examen completo en la próxima hora programada.</span><span class="sxs-lookup"><span data-stu-id="b2af4-135">Microsoft Defender Antivirus will run a full scan at the next scheduled time.</span></span>

### <a name="use-group-policy-to-schedule-scans"></a><span data-ttu-id="b2af4-136">Usar directiva de grupo para programar exámenes</span><span class="sxs-lookup"><span data-stu-id="b2af4-136">Use Group Policy to schedule scans</span></span>

|<span data-ttu-id="b2af4-137">Ubicación</span><span class="sxs-lookup"><span data-stu-id="b2af4-137">Location</span></span> | <span data-ttu-id="b2af4-138">Configuración</span><span class="sxs-lookup"><span data-stu-id="b2af4-138">Setting</span></span> | <span data-ttu-id="b2af4-139">Descripción</span><span class="sxs-lookup"><span data-stu-id="b2af4-139">Description</span></span> | <span data-ttu-id="b2af4-140">Configuración predeterminada (si no está configurada)</span><span class="sxs-lookup"><span data-stu-id="b2af4-140">Default setting (if not configured)</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="b2af4-141">Examinar</span><span class="sxs-lookup"><span data-stu-id="b2af4-141">Scan</span></span> | <span data-ttu-id="b2af4-142">Especificar el tipo de examen que se usará para un examen programado</span><span class="sxs-lookup"><span data-stu-id="b2af4-142">Specify the scan type to use for a scheduled scan</span></span> | <span data-ttu-id="b2af4-143">Examen rápido</span><span class="sxs-lookup"><span data-stu-id="b2af4-143">Quick scan</span></span> |
|<span data-ttu-id="b2af4-144">Examinar</span><span class="sxs-lookup"><span data-stu-id="b2af4-144">Scan</span></span> | <span data-ttu-id="b2af4-145">Especificar el día de la semana para ejecutar un examen programado</span><span class="sxs-lookup"><span data-stu-id="b2af4-145">Specify the day of the week to run a scheduled scan</span></span> | <span data-ttu-id="b2af4-146">Especifique el día (o nunca) para ejecutar un examen.</span><span class="sxs-lookup"><span data-stu-id="b2af4-146">Specify the day (or never) to run a scan.</span></span> | <span data-ttu-id="b2af4-147">Nunca</span><span class="sxs-lookup"><span data-stu-id="b2af4-147">Never</span></span> |
|<span data-ttu-id="b2af4-148">Examinar</span><span class="sxs-lookup"><span data-stu-id="b2af4-148">Scan</span></span> | <span data-ttu-id="b2af4-149">Especificar la hora del día para ejecutar un examen programado</span><span class="sxs-lookup"><span data-stu-id="b2af4-149">Specify the time of day to run a scheduled scan</span></span> | <span data-ttu-id="b2af4-150">Especifique el número de minutos después de medianoche (por ejemplo, escriba **60** para la 1 a.m.).</span><span class="sxs-lookup"><span data-stu-id="b2af4-150">Specify the number of minutes after midnight (for example, enter **60** for 1 a.m.).</span></span> | <span data-ttu-id="b2af4-151">2 a. m.</span><span class="sxs-lookup"><span data-stu-id="b2af4-151">2 a.m.</span></span> |
|<span data-ttu-id="b2af4-152">Raíz</span><span class="sxs-lookup"><span data-stu-id="b2af4-152">Root</span></span> | <span data-ttu-id="b2af4-153">Randomize scheduled task times</span><span class="sxs-lookup"><span data-stu-id="b2af4-153">Randomize scheduled task times</span></span> |<span data-ttu-id="b2af4-154">En Antivirus de Microsoft Defender: aleatorice la hora de inicio del examen a cualquier intervalo de 0 a 4 horas.</span><span class="sxs-lookup"><span data-stu-id="b2af4-154">In Microsoft Defender Antivirus: Randomize the start time of the scan to any interval from 0 to 4 hours.</span></span> <br><span data-ttu-id="b2af4-155">En FEP/SCEP: aleatorizar a cualquier intervalo más o menos 30 minutos.</span><span class="sxs-lookup"><span data-stu-id="b2af4-155">In FEP/SCEP: randomize to any interval plus or minus 30 minutes.</span></span> <span data-ttu-id="b2af4-156">Esto puede ser útil en implementaciones de VM o VDI.</span><span class="sxs-lookup"><span data-stu-id="b2af4-156">This can be useful in VM or VDI deployments.</span></span> | <span data-ttu-id="b2af4-157">Habilitado</span><span class="sxs-lookup"><span data-stu-id="b2af4-157">Enabled</span></span> |


### <a name="use-powershell-cmdlets-to-schedule-scans"></a><span data-ttu-id="b2af4-158">Usar cmdlets de PowerShell para programar exámenes</span><span class="sxs-lookup"><span data-stu-id="b2af4-158">Use PowerShell cmdlets to schedule scans</span></span>

<span data-ttu-id="b2af4-159">Use los cmdlets siguientes:</span><span class="sxs-lookup"><span data-stu-id="b2af4-159">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanParameters
Set-MpPreference -ScanScheduleDay
Set-MpPreference -ScanScheduleTime
Set-MpPreference -RandomizeScheduleTaskTimes

```

<span data-ttu-id="b2af4-160">Consulte [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and Defender [cmdlets](/powershell/module/defender/) para obtener más información sobre cómo usar PowerShell con Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="b2af4-160">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi-to-schedule-scans"></a><span data-ttu-id="b2af4-161">Usar instrucciones de administración de Windows (WMI) para programar exámenes</span><span class="sxs-lookup"><span data-stu-id="b2af4-161">Use Windows Management Instruction (WMI) to schedule scans</span></span>

<span data-ttu-id="b2af4-162">Utilice el [ **método Set** de la **clase MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) para las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="b2af4-162">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ScanParameters
ScanScheduleDay
ScanScheduleTime
RandomizeScheduleTaskTimes
```

<span data-ttu-id="b2af4-163">Vea lo siguiente para obtener más información y parámetros permitidos:</span><span class="sxs-lookup"><span data-stu-id="b2af4-163">See the following for more information and allowed parameters:</span></span>
- [<span data-ttu-id="b2af4-164">Windows Defender API WMIv2</span><span class="sxs-lookup"><span data-stu-id="b2af4-164">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)




## <a name="start-scheduled-scans-only-when-the-endpoint-is-not-in-use"></a><span data-ttu-id="b2af4-165">Iniciar exámenes programados solo cuando el extremo no esté en uso</span><span class="sxs-lookup"><span data-stu-id="b2af4-165">Start scheduled scans only when the endpoint is not in use</span></span>

<span data-ttu-id="b2af4-166">Puede establecer que el examen programado solo se produzca cuando el extremo está activado pero no se usa con la directiva de grupo, PowerShell o WMI.</span><span class="sxs-lookup"><span data-stu-id="b2af4-166">You can set the scheduled scan to only occur when the endpoint is turned on but not in use with Group Policy, PowerShell, or WMI.</span></span>

> [!NOTE]
> <span data-ttu-id="b2af4-167">Estos exámenes no respetarán la configuración de limitación de CPU y aprovecharán al máximo los recursos disponibles para completar el examen lo más rápido posible.</span><span class="sxs-lookup"><span data-stu-id="b2af4-167">These scans will not honor the CPU throttling configuration and take full advantage of the resources available to complete the scan as fast as possible.</span></span>

### <a name="use-group-policy-to-schedule-scans"></a><span data-ttu-id="b2af4-168">Usar directiva de grupo para programar exámenes</span><span class="sxs-lookup"><span data-stu-id="b2af4-168">Use Group Policy to schedule scans</span></span>

|<span data-ttu-id="b2af4-169">Ubicación</span><span class="sxs-lookup"><span data-stu-id="b2af4-169">Location</span></span> | <span data-ttu-id="b2af4-170">Configuración</span><span class="sxs-lookup"><span data-stu-id="b2af4-170">Setting</span></span> | <span data-ttu-id="b2af4-171">Descripción</span><span class="sxs-lookup"><span data-stu-id="b2af4-171">Description</span></span> | <span data-ttu-id="b2af4-172">Configuración predeterminada (si no está configurada)</span><span class="sxs-lookup"><span data-stu-id="b2af4-172">Default setting (if not configured)</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="b2af4-173">Examinar</span><span class="sxs-lookup"><span data-stu-id="b2af4-173">Scan</span></span> | <span data-ttu-id="b2af4-174">Iniciar el examen programado solo cuando el equipo está en uso pero no está en uso</span><span class="sxs-lookup"><span data-stu-id="b2af4-174">Start the scheduled scan only when computer is on but not in use</span></span> | <span data-ttu-id="b2af4-175">Los exámenes programados no se ejecutarán, a menos que el equipo esté en uso pero no esté en uso</span><span class="sxs-lookup"><span data-stu-id="b2af4-175">Scheduled scans will not run, unless the computer is on but not in use</span></span> | <span data-ttu-id="b2af4-176">Habilitado</span><span class="sxs-lookup"><span data-stu-id="b2af4-176">Enabled</span></span> |

### <a name="use-powershell-cmdlets"></a><span data-ttu-id="b2af4-177">Usar cmdlets de PowerShell</span><span class="sxs-lookup"><span data-stu-id="b2af4-177">Use PowerShell cmdlets</span></span>

<span data-ttu-id="b2af4-178">Use los cmdlets siguientes:</span><span class="sxs-lookup"><span data-stu-id="b2af4-178">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanOnlyIfIdleEnabled
```

<span data-ttu-id="b2af4-179">Consulte [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and Defender [cmdlets](/powershell/module/defender/) para obtener más información sobre cómo usar PowerShell con Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="b2af4-179">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi"></a><span data-ttu-id="b2af4-180">Usar instrucciones de administración de Windows (WMI)</span><span class="sxs-lookup"><span data-stu-id="b2af4-180">Use Windows Management Instruction (WMI)</span></span>

<span data-ttu-id="b2af4-181">Utilice el [ **método Set** de la **clase MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) para las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="b2af4-181">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ScanOnlyIfIdleEnabled
```

<span data-ttu-id="b2af4-182">Vea lo siguiente para obtener más información y parámetros permitidos:</span><span class="sxs-lookup"><span data-stu-id="b2af4-182">See the following for more information and allowed parameters:</span></span>
- [<span data-ttu-id="b2af4-183">Windows Defender API WMIv2</span><span class="sxs-lookup"><span data-stu-id="b2af4-183">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

<a id="remed"></a>
## <a name="configure-when-full-scans-should-be-run-to-complete-remediation"></a><span data-ttu-id="b2af4-184">Configurar cuándo deben ejecutarse exámenes completos para completar la corrección</span><span class="sxs-lookup"><span data-stu-id="b2af4-184">Configure when full scans should be run to complete remediation</span></span>

<span data-ttu-id="b2af4-185">Algunas amenazas pueden requerir un examen completo para completar su eliminación y corrección.</span><span class="sxs-lookup"><span data-stu-id="b2af4-185">Some threats may require a full scan to complete their removal and remediation.</span></span> <span data-ttu-id="b2af4-186">Puede programar cuándo deben producirse estos exámenes con la directiva de grupo, PowerShell o WMI.</span><span class="sxs-lookup"><span data-stu-id="b2af4-186">You can schedule when these scans should occur with Group Policy, PowerShell, or WMI.</span></span>

### <a name="use-group-policy-to-schedule-remediation-required-scans"></a><span data-ttu-id="b2af4-187">Usar la directiva de grupo para programar exámenes necesarios para la corrección</span><span class="sxs-lookup"><span data-stu-id="b2af4-187">Use Group Policy to schedule remediation-required scans</span></span>

| <span data-ttu-id="b2af4-188">Ubicación</span><span class="sxs-lookup"><span data-stu-id="b2af4-188">Location</span></span> | <span data-ttu-id="b2af4-189">Configuración</span><span class="sxs-lookup"><span data-stu-id="b2af4-189">Setting</span></span> | <span data-ttu-id="b2af4-190">Descripción</span><span class="sxs-lookup"><span data-stu-id="b2af4-190">Description</span></span> | <span data-ttu-id="b2af4-191">Configuración predeterminada (si no está configurada)</span><span class="sxs-lookup"><span data-stu-id="b2af4-191">Default setting (if not configured)</span></span> |
|---|---|---|---|
|<span data-ttu-id="b2af4-192">Corrección</span><span class="sxs-lookup"><span data-stu-id="b2af4-192">Remediation</span></span> | <span data-ttu-id="b2af4-193">Especificar el día de la semana para ejecutar un examen completo programado para completar la corrección</span><span class="sxs-lookup"><span data-stu-id="b2af4-193">Specify the day of the week to run a scheduled full scan to complete remediation</span></span> | <span data-ttu-id="b2af4-194">Especifique el día (o nunca) para ejecutar un examen.</span><span class="sxs-lookup"><span data-stu-id="b2af4-194">Specify the day (or never) to run a scan.</span></span> | <span data-ttu-id="b2af4-195">Nunca</span><span class="sxs-lookup"><span data-stu-id="b2af4-195">Never</span></span> |
|<span data-ttu-id="b2af4-196">Corrección</span><span class="sxs-lookup"><span data-stu-id="b2af4-196">Remediation</span></span> | <span data-ttu-id="b2af4-197">Especificar la hora del día para ejecutar un examen completo programado para completar la corrección</span><span class="sxs-lookup"><span data-stu-id="b2af4-197">Specify the time of day to run a scheduled full scan to complete remediation</span></span> | <span data-ttu-id="b2af4-198">Especifique el número de minutos después de la medianoche (por ejemplo, escriba **60** para la 1 a.m.)</span><span class="sxs-lookup"><span data-stu-id="b2af4-198">Specify the number of minutes after midnight (for example, enter **60** for 1 a.m.)</span></span> | <span data-ttu-id="b2af4-199">2 a. m.</span><span class="sxs-lookup"><span data-stu-id="b2af4-199">2 a.m.</span></span> |

### <a name="use-powershell-cmdlets"></a><span data-ttu-id="b2af4-200">Usar cmdlets de PowerShell</span><span class="sxs-lookup"><span data-stu-id="b2af4-200">Use PowerShell cmdlets</span></span>

<span data-ttu-id="b2af4-201">Use los cmdlets siguientes:</span><span class="sxs-lookup"><span data-stu-id="b2af4-201">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -RemediationScheduleDay
Set-MpPreference -RemediationScheduleTime
```

<span data-ttu-id="b2af4-202">Consulte [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and Defender [cmdlets](/powershell/module/defender/) para obtener más información sobre cómo usar PowerShell con Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="b2af4-202">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi"></a><span data-ttu-id="b2af4-203">Usar instrucciones de administración de Windows (WMI)</span><span class="sxs-lookup"><span data-stu-id="b2af4-203">Use Windows Management Instruction (WMI)</span></span>

<span data-ttu-id="b2af4-204">Utilice el [ **método Set** de la **clase MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) para las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="b2af4-204">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
RemediationScheduleDay
RemediationScheduleTime
```

<span data-ttu-id="b2af4-205">Vea lo siguiente para obtener más información y parámetros permitidos:</span><span class="sxs-lookup"><span data-stu-id="b2af4-205">See the following for more information and allowed parameters:</span></span>
- [<span data-ttu-id="b2af4-206">Windows Defender API WMIv2</span><span class="sxs-lookup"><span data-stu-id="b2af4-206">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)




## <a name="set-up-daily-quick-scans"></a><span data-ttu-id="b2af4-207">Configurar exámenes rápidos diarios</span><span class="sxs-lookup"><span data-stu-id="b2af4-207">Set up daily quick scans</span></span>

<span data-ttu-id="b2af4-208">Puede habilitar un examen rápido diario que se puede ejecutar además de los otros exámenes programados con la directiva de grupo, PowerShell o WMI.</span><span class="sxs-lookup"><span data-stu-id="b2af4-208">You can enable a daily quick scan that can be run in addition to your other scheduled scans with Group Policy, PowerShell, or WMI.</span></span>


### <a name="use-group-policy-to-schedule-daily-scans"></a><span data-ttu-id="b2af4-209">Usar directiva de grupo para programar exámenes diarios</span><span class="sxs-lookup"><span data-stu-id="b2af4-209">Use Group Policy to schedule daily scans</span></span>


|<span data-ttu-id="b2af4-210">Ubicación</span><span class="sxs-lookup"><span data-stu-id="b2af4-210">Location</span></span> | <span data-ttu-id="b2af4-211">Configuración</span><span class="sxs-lookup"><span data-stu-id="b2af4-211">Setting</span></span> | <span data-ttu-id="b2af4-212">Descripción</span><span class="sxs-lookup"><span data-stu-id="b2af4-212">Description</span></span> | <span data-ttu-id="b2af4-213">Configuración predeterminada (si no está configurada)</span><span class="sxs-lookup"><span data-stu-id="b2af4-213">Default setting (if not configured)</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="b2af4-214">Examinar</span><span class="sxs-lookup"><span data-stu-id="b2af4-214">Scan</span></span> | <span data-ttu-id="b2af4-215">Especificar el intervalo para ejecutar exámenes rápidos por día</span><span class="sxs-lookup"><span data-stu-id="b2af4-215">Specify the interval to run quick scans per day</span></span> | <span data-ttu-id="b2af4-216">Especifique cuántas horas debe transcurrir antes del siguiente examen rápido.</span><span class="sxs-lookup"><span data-stu-id="b2af4-216">Specify how many hours should elapse before the next quick scan.</span></span> <span data-ttu-id="b2af4-217">Por ejemplo, para ejecutarse cada dos horas, escriba **2**, para una vez al día, escriba **24**.</span><span class="sxs-lookup"><span data-stu-id="b2af4-217">For example, to run every two hours, enter **2**, for once a day, enter **24**.</span></span> <span data-ttu-id="b2af4-218">Escriba **0** para nunca ejecutar un examen rápido diario.</span><span class="sxs-lookup"><span data-stu-id="b2af4-218">Enter **0** to never run a daily quick scan.</span></span> | <span data-ttu-id="b2af4-219">Nunca</span><span class="sxs-lookup"><span data-stu-id="b2af4-219">Never</span></span> |
|<span data-ttu-id="b2af4-220">Examinar</span><span class="sxs-lookup"><span data-stu-id="b2af4-220">Scan</span></span> | <span data-ttu-id="b2af4-221">Especificar la hora de un examen rápido diario</span><span class="sxs-lookup"><span data-stu-id="b2af4-221">Specify the time for a daily quick scan</span></span> | <span data-ttu-id="b2af4-222">Especifique el número de minutos después de la medianoche (por ejemplo, escriba **60** para la 1 a.m.)</span><span class="sxs-lookup"><span data-stu-id="b2af4-222">Specify the number of minutes after midnight (for example, enter **60** for 1 a.m.)</span></span> | <span data-ttu-id="b2af4-223">2 a. m.</span><span class="sxs-lookup"><span data-stu-id="b2af4-223">2 a.m.</span></span> |

### <a name="use-powershell-cmdlets-to-schedule-daily-scans"></a><span data-ttu-id="b2af4-224">Usar cmdlets de PowerShell para programar exámenes diarios</span><span class="sxs-lookup"><span data-stu-id="b2af4-224">Use PowerShell cmdlets to schedule daily scans</span></span>

<span data-ttu-id="b2af4-225">Use los cmdlets siguientes:</span><span class="sxs-lookup"><span data-stu-id="b2af4-225">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanScheduleQuickScanTime
```

<span data-ttu-id="b2af4-226">Consulte [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and Defender [cmdlets](/powershell/module/defender/) para obtener más información sobre cómo usar PowerShell con Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="b2af4-226">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi-to-schedule-daily-scans"></a><span data-ttu-id="b2af4-227">Usar Windows Management Instruction (WMI) para programar exámenes diarios</span><span class="sxs-lookup"><span data-stu-id="b2af4-227">Use Windows Management Instruction (WMI) to schedule daily scans</span></span>

<span data-ttu-id="b2af4-228">Utilice el [ **método Set** de la **clase MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) para las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="b2af4-228">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ScanScheduleQuickScanTime
```

<span data-ttu-id="b2af4-229">Vea lo siguiente para obtener más información y parámetros permitidos:</span><span class="sxs-lookup"><span data-stu-id="b2af4-229">See the following for more information and allowed parameters:</span></span>
- [<span data-ttu-id="b2af4-230">Windows Defender API WMIv2</span><span class="sxs-lookup"><span data-stu-id="b2af4-230">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


## <a name="enable-scans-after-protection-updates"></a><span data-ttu-id="b2af4-231">Habilitar exámenes después de actualizaciones de protección</span><span class="sxs-lookup"><span data-stu-id="b2af4-231">Enable scans after protection updates</span></span>

<span data-ttu-id="b2af4-232">Puede forzar que se produzca un examen después de cada actualización [de protección con](manage-protection-updates-microsoft-defender-antivirus.md) la directiva de grupo.</span><span class="sxs-lookup"><span data-stu-id="b2af4-232">You can force a scan to occur after every [protection update](manage-protection-updates-microsoft-defender-antivirus.md) with Group Policy.</span></span>

### <a name="use-group-policy-to-schedule-scans-after-protection-updates"></a><span data-ttu-id="b2af4-233">Usar la directiva de grupo para programar exámenes después de las actualizaciones de protección</span><span class="sxs-lookup"><span data-stu-id="b2af4-233">Use Group Policy to schedule scans after protection updates</span></span>

|<span data-ttu-id="b2af4-234">Ubicación</span><span class="sxs-lookup"><span data-stu-id="b2af4-234">Location</span></span> | <span data-ttu-id="b2af4-235">Configuración</span><span class="sxs-lookup"><span data-stu-id="b2af4-235">Setting</span></span> | <span data-ttu-id="b2af4-236">Descripción</span><span class="sxs-lookup"><span data-stu-id="b2af4-236">Description</span></span> | <span data-ttu-id="b2af4-237">Configuración predeterminada (si no está configurada)</span><span class="sxs-lookup"><span data-stu-id="b2af4-237">Default setting (if not configured)</span></span>|
|:---|:---|:---|:---|
|<span data-ttu-id="b2af4-238">Actualizaciones de firmas</span><span class="sxs-lookup"><span data-stu-id="b2af4-238">Signature updates</span></span> | <span data-ttu-id="b2af4-239">Activar el examen después de la actualización de inteligencia de seguridad</span><span class="sxs-lookup"><span data-stu-id="b2af4-239">Turn on scan after Security intelligence update</span></span> | <span data-ttu-id="b2af4-240">Un examen se realizará inmediatamente después de descargar una nueva actualización de protección</span><span class="sxs-lookup"><span data-stu-id="b2af4-240">A scan will occur immediately after a new protection update is downloaded</span></span> | <span data-ttu-id="b2af4-241">Habilitado</span><span class="sxs-lookup"><span data-stu-id="b2af4-241">Enabled</span></span> |

## <a name="see-also"></a><span data-ttu-id="b2af4-242">Vea también</span><span class="sxs-lookup"><span data-stu-id="b2af4-242">See also</span></span>
- [<span data-ttu-id="b2af4-243">Impedir o permitir que los usuarios modifiquen localmente la configuración de directiva</span><span class="sxs-lookup"><span data-stu-id="b2af4-243">Prevent or allow users to locally modify policy settings</span></span>](configure-local-policy-overrides-microsoft-defender-antivirus.md)
- [<span data-ttu-id="b2af4-244">Configurar y ejecutar exámenes de Antivirus de Microsoft Defender a petición</span><span class="sxs-lookup"><span data-stu-id="b2af4-244">Configure and run on-demand Microsoft Defender Antivirus scans</span></span>](run-scan-microsoft-defender-antivirus.md)
- [<span data-ttu-id="b2af4-245">Configurar opciones de análisis de Antivirus de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="b2af4-245">Configure Microsoft Defender Antivirus scanning options</span></span>](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [<span data-ttu-id="b2af4-246">Administrar actualizaciones de Antivirus de Microsoft Defender y aplicar líneas base</span><span class="sxs-lookup"><span data-stu-id="b2af4-246">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>](manage-updates-baselines-microsoft-defender-antivirus.md)
- [<span data-ttu-id="b2af4-247">Administrar cuándo se deben descargar y aplicar las actualizaciones de protección</span><span class="sxs-lookup"><span data-stu-id="b2af4-247">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) 
- [<span data-ttu-id="b2af4-248">Antivirus de Microsoft Defender en Windows 10</span><span class="sxs-lookup"><span data-stu-id="b2af4-248">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)