---
title: Aplicar Antivirus de Microsoft Defender actualizaciones después de determinados eventos
description: Administrar cómo Antivirus de Microsoft Defender actualizaciones de inteligencia de seguridad después del inicio o de recibir informes de detección entregados en la nube.
keywords: actualizaciones, protección, forzar actualizaciones, eventos, inicio, buscar más recientes, notificaciones
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/17/2018
ms.reviewer: pahuijbr
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 624e32bfebfce02021f1dcb1dbdde9446472239a
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274705"
---
# <a name="manage-event-based-forced-updates"></a><span data-ttu-id="6d452-104">Administrar las actualizaciones forzadas basadas en eventos</span><span class="sxs-lookup"><span data-stu-id="6d452-104">Manage event-based forced updates</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="6d452-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="6d452-105">**Applies to:**</span></span>

- [<span data-ttu-id="6d452-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="6d452-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="6d452-107">Antivirus de Microsoft Defender permite determinar si las actualizaciones deben producirse (o no) después de determinados eventos, como al iniciarse o después de recibir informes específicos del servicio de protección entregado en la nube.</span><span class="sxs-lookup"><span data-stu-id="6d452-107">Microsoft Defender Antivirus allows you to determine if updates should (or should not) occur after certain events, such as at startup or after receiving specific reports from the cloud-delivered protection service.</span></span>

## <a name="check-for-protection-updates-before-running-a-scan"></a><span data-ttu-id="6d452-108">Buscar actualizaciones de protección antes de ejecutar un examen</span><span class="sxs-lookup"><span data-stu-id="6d452-108">Check for protection updates before running a scan</span></span>

<span data-ttu-id="6d452-109">Puede usar Microsoft Endpoint Configuration Manager, directiva de grupo, cmdlets de PowerShell y WMI para forzar a Antivirus de Microsoft Defender a comprobar y descargar actualizaciones de protección antes de ejecutar un examen programado.</span><span class="sxs-lookup"><span data-stu-id="6d452-109">You can use Microsoft Endpoint Configuration Manager, Group Policy, PowerShell cmdlets, and WMI to force Microsoft Defender Antivirus to check and download protection updates before running a scheduled scan.</span></span>

### <a name="use-configuration-manager-to-check-for-protection-updates-before-running-a-scan"></a><span data-ttu-id="6d452-110">Usar Configuration Manager para buscar actualizaciones de protección antes de ejecutar un examen</span><span class="sxs-lookup"><span data-stu-id="6d452-110">Use Configuration Manager to check for protection updates before running a scan</span></span>

1. <span data-ttu-id="6d452-111">En la consola Microsoft Endpoint Manager, abra la directiva de antimalware  que desea cambiar (haga clic en Activos y cumplimiento en el panel de navegación de la izquierda y, a continuación, expanda el árbol a Información general Endpoint Protection Directivas  >    >  **antimalware**)</span><span class="sxs-lookup"><span data-stu-id="6d452-111">On your Microsoft Endpoint Manager console, open the antimalware policy you want to change (click **Assets and Compliance** in the navigation pane on the left, then expand the tree to **Overview** > **Endpoint Protection** > **Antimalware Policies**)</span></span>

2. <span data-ttu-id="6d452-112">Vaya a la **sección Exámenes programados** y establezca **Comprobar las últimas** actualizaciones de inteligencia de seguridad antes de ejecutar un examen en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="6d452-112">Go to the **Scheduled scans** section and set **Check for the latest security intelligence updates before running a scan** to **Yes**.</span></span>

3. <span data-ttu-id="6d452-113">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6d452-113">Click **OK**.</span></span>

4. <span data-ttu-id="6d452-114">[Implemente la directiva actualizada como de costumbre.](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers)</span><span class="sxs-lookup"><span data-stu-id="6d452-114">[Deploy the updated policy as usual](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers).</span></span>

### <a name="use-group-policy-to-check-for-protection-updates-before-running-a-scan"></a><span data-ttu-id="6d452-115">Usar la directiva de grupo para buscar actualizaciones de protección antes de ejecutar un examen</span><span class="sxs-lookup"><span data-stu-id="6d452-115">Use Group Policy to check for protection updates before running a scan</span></span>

1. <span data-ttu-id="6d452-116">En el equipo de administración de directivas de grupo, abra la Consola de administración de directivas de [grupo,](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)haga clic con el botón secundario en el objeto de directiva de grupo que desea configurar y haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="6d452-116">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="6d452-117">Con el **Editor de administración de directivas de grupo,** vaya a Configuración del **equipo**.</span><span class="sxs-lookup"><span data-stu-id="6d452-117">Using the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="6d452-118">Haga clic **en Directivas** **y, a continuación, en Plantillas administrativas.**</span><span class="sxs-lookup"><span data-stu-id="6d452-118">Click **Policies** then **Administrative templates**.</span></span>

4. <span data-ttu-id="6d452-119">Expanda el árbol para Windows **componentes**  >  **Antivirus de Microsoft Defender**  >  **Scan**.</span><span class="sxs-lookup"><span data-stu-id="6d452-119">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Scan**.</span></span>

5. <span data-ttu-id="6d452-120">Haga doble clic **en Comprobar las definiciones de virus** y spyware más recientes antes de ejecutar un examen programado y establezca la opción en **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="6d452-120">Double-click **Check for the latest virus and spyware definitions before running a scheduled scan** and set the option to **Enabled**.</span></span>

6. <span data-ttu-id="6d452-121">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6d452-121">Click **OK**.</span></span>

### <a name="use-powershell-cmdlets-to-check-for-protection-updates-before-running-a-scan"></a><span data-ttu-id="6d452-122">Usar cmdlets de PowerShell para buscar actualizaciones de protección antes de ejecutar un examen</span><span class="sxs-lookup"><span data-stu-id="6d452-122">Use PowerShell cmdlets to check for protection updates before running a scan</span></span>

<span data-ttu-id="6d452-123">Use los cmdlets siguientes:</span><span class="sxs-lookup"><span data-stu-id="6d452-123">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -CheckForSignaturesBeforeRunningScan
```

<span data-ttu-id="6d452-124">Para más información, consulte [Usar cmdlets de PowerShell para configurar y ejecutar Antivirus de Microsoft Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md) y [cmdlets de Defender](/powershell/module/defender/index).</span><span class="sxs-lookup"><span data-stu-id="6d452-124">For more information, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/index).</span></span>

### <a name="use-windows-management-instruction-wmi-to-check-for-protection-updates-before-running-a-scan"></a><span data-ttu-id="6d452-125">Use Windows Management Instruction (WMI) para buscar actualizaciones de protección antes de ejecutar un examen</span><span class="sxs-lookup"><span data-stu-id="6d452-125">Use Windows Management Instruction (WMI) to check for protection updates before running a scan</span></span>

<span data-ttu-id="6d452-126">Utilice el [ **método Set** de la **clase MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) para las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="6d452-126">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
CheckForSignaturesBeforeRunningScan
```

<span data-ttu-id="6d452-127">Para obtener más información, [vea Windows Defender API wmiv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span><span class="sxs-lookup"><span data-stu-id="6d452-127">For more information, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

## <a name="check-for-protection-updates-on-startup"></a><span data-ttu-id="6d452-128">Buscar actualizaciones de protección al inicio</span><span class="sxs-lookup"><span data-stu-id="6d452-128">Check for protection updates on startup</span></span>

<span data-ttu-id="6d452-129">Puedes usar la directiva de grupo para forzar Antivirus de Microsoft Defender para comprobar y descargar actualizaciones de protección cuando se inicia la máquina.</span><span class="sxs-lookup"><span data-stu-id="6d452-129">You can use Group Policy to force Microsoft Defender Antivirus to check and download protection updates when the machine is started.</span></span>

1. <span data-ttu-id="6d452-130">En el equipo de administración de directivas de grupo, abra la Consola de administración de directivas de [grupo,](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)haga clic con el botón secundario en el objeto de directiva de grupo que desea configurar y haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="6d452-130">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="6d452-131">Con el **Editor de administración de directivas de grupo,** vaya a Configuración del **equipo**.</span><span class="sxs-lookup"><span data-stu-id="6d452-131">Using the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="6d452-132">Haga clic **en Directivas** **y, a continuación, en Plantillas administrativas.**</span><span class="sxs-lookup"><span data-stu-id="6d452-132">Click **Policies** then **Administrative templates**.</span></span>

4. <span data-ttu-id="6d452-133">Expanda el árbol para Windows **componentes Antivirus de Microsoft Defender** actualizaciones  >    >  **de inteligencia de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="6d452-133">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Security Intelligence Updates**.</span></span>

5. <span data-ttu-id="6d452-134">Haz doble clic **en Comprobar las definiciones de virus y spyware** más recientes al iniciar y establece la opción en **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="6d452-134">Double-click **Check for the latest virus and spyware definitions on startup** and set the option to **Enabled**.</span></span> 

6. <span data-ttu-id="6d452-135">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6d452-135">Click **OK**.</span></span>

<span data-ttu-id="6d452-136">También puede usar la directiva de grupo, PowerShell o WMI para configurar Antivirus de Microsoft Defender para buscar actualizaciones en el inicio incluso cuando no se esté ejecutando.</span><span class="sxs-lookup"><span data-stu-id="6d452-136">You can also use Group Policy, PowerShell, or WMI to configure Microsoft Defender Antivirus to check for updates at startup even when it is not running.</span></span>

### <a name="use-group-policy-to-download-updates-when-microsoft-defender-antivirus-is-not-present"></a><span data-ttu-id="6d452-137">Usar la directiva de grupo para descargar actualizaciones Antivirus de Microsoft Defender no está presente</span><span class="sxs-lookup"><span data-stu-id="6d452-137">Use Group Policy to download updates when Microsoft Defender Antivirus is not present</span></span>

1. <span data-ttu-id="6d452-138">En el equipo de administración de directivas de grupo, abra la Consola de administración de directivas de [grupo,](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)haga clic con el botón secundario en el objeto de directiva de grupo que desea configurar y haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="6d452-138">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="6d452-139">Con el **Editor de administración de directivas de** grupo, vaya a Configuración del **equipo**.</span><span class="sxs-lookup"><span data-stu-id="6d452-139">Using the **Group Policy Management Editor**, go to **Computer configuration**.</span></span>

3. <span data-ttu-id="6d452-140">Haga clic **en Directivas** **y, a continuación, en Plantillas administrativas.**</span><span class="sxs-lookup"><span data-stu-id="6d452-140">Click **Policies** then **Administrative templates**.</span></span>

4. <span data-ttu-id="6d452-141">Expanda el árbol para Windows **componentes Antivirus de Microsoft Defender** actualizaciones  >    >  **de inteligencia de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="6d452-141">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Security Intelligence Updates**.</span></span>

5. <span data-ttu-id="6d452-142">Haz doble clic en **Iniciar actualización de inteligencia de seguridad al** inicio y establece la opción en **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="6d452-142">Double-click **Initiate security intelligence update on startup** and set the option to **Enabled**.</span></span>

6. <span data-ttu-id="6d452-143">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6d452-143">Click **OK**.</span></span>

### <a name="use-powershell-cmdlets-to-download-updates-when-microsoft-defender-antivirus-is-not-present"></a><span data-ttu-id="6d452-144">Usar cmdlets de PowerShell para descargar actualizaciones Antivirus de Microsoft Defender no está presente</span><span class="sxs-lookup"><span data-stu-id="6d452-144">Use PowerShell cmdlets to download updates when Microsoft Defender Antivirus is not present</span></span>

<span data-ttu-id="6d452-145">Use los cmdlets siguientes:</span><span class="sxs-lookup"><span data-stu-id="6d452-145">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -SignatureDisableUpdateOnStartupWithoutEngine
```

<span data-ttu-id="6d452-146">Para obtener más información, vea [Use PowerShell cmdlets to manage Antivirus de Microsoft Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md) and Defender [cmdlets](/powershell/module/defender/index) para obtener más información sobre cómo usar PowerShell con Antivirus de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="6d452-146">For more information, see [Use PowerShell cmdlets to manage Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/index) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi-to-download-updates-when-microsoft-defender-antivirus-is-not-present"></a><span data-ttu-id="6d452-147">Use Windows Management Instruction (WMI) para descargar actualizaciones Antivirus de Microsoft Defender no está presente</span><span class="sxs-lookup"><span data-stu-id="6d452-147">Use Windows Management Instruction (WMI) to download updates when Microsoft Defender Antivirus is not present</span></span>

<span data-ttu-id="6d452-148">Utilice el [ **método Set** de la **clase MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) para las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="6d452-148">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
SignatureDisableUpdateOnStartupWithoutEngine
```

<span data-ttu-id="6d452-149">Para obtener más información, [vea Windows Defender API wmiv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span><span class="sxs-lookup"><span data-stu-id="6d452-149">For more information, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

<a id="cloud-report-updates"></a>

## <a name="allow-ad-hoc-changes-to-protection-based-on-cloud-delivered-protection"></a><span data-ttu-id="6d452-150">Permitir cambios ad hoc en la protección basada en la protección entregada en la nube</span><span class="sxs-lookup"><span data-stu-id="6d452-150">Allow ad hoc changes to protection based on cloud-delivered protection</span></span>

<span data-ttu-id="6d452-151">Microsoft Defender AV puede realizar cambios en su protección en función de la protección entregada en la nube.</span><span class="sxs-lookup"><span data-stu-id="6d452-151">Microsoft Defender AV can make changes to its protection based on cloud-delivered protection.</span></span> <span data-ttu-id="6d452-152">Estos cambios pueden producirse fuera de las actualizaciones de protección normales o programadas.</span><span class="sxs-lookup"><span data-stu-id="6d452-152">Such changes can occur outside of normal or scheduled protection updates.</span></span>

<span data-ttu-id="6d452-153">Si ha habilitado la protección de entrega en la nube, Microsoft Defender AV enviará archivos de los que es sospechoso a la Windows Defender nube.</span><span class="sxs-lookup"><span data-stu-id="6d452-153">If you have enabled cloud-delivered protection, Microsoft Defender AV will send files it is suspicious about to the Windows Defender cloud.</span></span> <span data-ttu-id="6d452-154">Si el servicio en la nube informa de que el archivo es malintencionado y el archivo se detecta en una actualización de protección reciente, puede usar la directiva de grupo para configurar Microsoft Defender AV para recibir automáticamente esa actualización de protección.</span><span class="sxs-lookup"><span data-stu-id="6d452-154">If the cloud service reports that the file is malicious, and the file is detected in a recent protection update, you can use Group Policy to configure Microsoft Defender AV to automatically receive that protection update.</span></span> <span data-ttu-id="6d452-155">También se pueden aplicar otras actualizaciones de protección importantes.</span><span class="sxs-lookup"><span data-stu-id="6d452-155">Other important protection updates can also be applied.</span></span>

### <a name="use-group-policy-to-automatically-download-recent-updates-based-on-cloud-delivered-protection"></a><span data-ttu-id="6d452-156">Usar la directiva de grupo para descargar automáticamente las actualizaciones recientes basadas en la protección entregada en la nube</span><span class="sxs-lookup"><span data-stu-id="6d452-156">Use Group Policy to automatically download recent updates based on cloud-delivered protection</span></span>

1. <span data-ttu-id="6d452-157">En el equipo de administración de directivas de grupo, abra la Consola de administración de directivas de [grupo,](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)haga clic con el botón secundario en el objeto de directiva de grupo que desea configurar y haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="6d452-157">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="6d452-158">Con el **Editor de administración de directivas de grupo,** vaya a Configuración del **equipo**.</span><span class="sxs-lookup"><span data-stu-id="6d452-158">Using the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="6d452-159">Haga clic **en Directivas** **y, a continuación, en Plantillas administrativas.**</span><span class="sxs-lookup"><span data-stu-id="6d452-159">Click **Policies** then **Administrative templates**.</span></span>

4. <span data-ttu-id="6d452-160">Expanda el árbol para Windows **componentes Antivirus de Microsoft Defender** actualizaciones  >    >  **de inteligencia de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="6d452-160">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Security Intelligence Updates**.</span></span>

5. <span data-ttu-id="6d452-161">Haga doble clic en Permitir actualizaciones de inteligencia de seguridad en tiempo real basadas en informes **de Microsoft MAPS** y establezca la opción en **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="6d452-161">Double-click **Allow real-time security intelligence updates based on reports to Microsoft MAPS** and set the option to **Enabled**.</span></span> <span data-ttu-id="6d452-162">Después, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6d452-162">Then click **OK**.</span></span>

6. <span data-ttu-id="6d452-163">**Permitir que las notificaciones deshabilite informes basados en definiciones en Microsoft MAPS** y establezca la opción en **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="6d452-163">**Allow notifications to disable definitions-based reports to Microsoft MAPS** and set the option to **Enabled**.</span></span> <span data-ttu-id="6d452-164">Después, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6d452-164">Then click **OK**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="6d452-165">**Permitir que las notificaciones deshabilite los informes basados** en definiciones permite a Microsoft MAPS deshabilitar esas definiciones conocidas por causar informes falsos positivos.</span><span class="sxs-lookup"><span data-stu-id="6d452-165">**Allow notifications to disable definitions based reports** enables Microsoft MAPS to disable those definitions known to cause false-positive reports.</span></span> <span data-ttu-id="6d452-166">Debe configurar el equipo para que se una a Microsoft MAPS para que esta función funcione.</span><span class="sxs-lookup"><span data-stu-id="6d452-166">You must configure your computer to join Microsoft MAPS for this function to work.</span></span>

## <a name="see-also"></a><span data-ttu-id="6d452-167">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6d452-167">See also</span></span>

- [<span data-ttu-id="6d452-168">Implementar Antivirus de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="6d452-168">Deploy Microsoft Defender Antivirus</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)
- [<span data-ttu-id="6d452-169">Administrar Antivirus de Microsoft Defender actualizaciones y aplicar líneas base</span><span class="sxs-lookup"><span data-stu-id="6d452-169">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>](manage-updates-baselines-microsoft-defender-antivirus.md)
- [<span data-ttu-id="6d452-170">Administrar cuándo se deben descargar y aplicar las actualizaciones de protección</span><span class="sxs-lookup"><span data-stu-id="6d452-170">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md)
- [<span data-ttu-id="6d452-171">Administrar actualizaciones de puntos de conexión que están des actualizadas</span><span class="sxs-lookup"><span data-stu-id="6d452-171">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [<span data-ttu-id="6d452-172">Administrar las actualizaciones de dispositivos móviles y máquinas virtuales</span><span class="sxs-lookup"><span data-stu-id="6d452-172">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [<span data-ttu-id="6d452-173">Antivirus de Microsoft Defender en Windows 10</span><span class="sxs-lookup"><span data-stu-id="6d452-173">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)