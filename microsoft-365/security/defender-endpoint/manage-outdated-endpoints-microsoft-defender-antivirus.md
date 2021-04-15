---
title: Aplicar actualizaciones de protección antivirus de Microsoft Defender a puntos de conexión no actualizados
description: Defina cuándo y cómo deben aplicarse las actualizaciones para los puntos de conexión que no se han actualizado en un tiempo.
keywords: actualizaciones, protección, desactualizado, obsoleto, antiguo, de ponerse al día
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 81c7fb2bb7cd20fea3f343097811078ed744c3eb
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765376"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-scans-for-endpoints-that-are-out-of-date"></a><span data-ttu-id="504dc-104">Administrar actualizaciones y exámenes de Antivirus de Microsoft Defender en busca de puntos de conexión que están des actualizados</span><span class="sxs-lookup"><span data-stu-id="504dc-104">Manage Microsoft Defender Antivirus updates and scans for endpoints that are out of date</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="504dc-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="504dc-105">**Applies to:**</span></span>

- [<span data-ttu-id="504dc-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="504dc-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="504dc-107">Antivirus de Microsoft Defender te permite definir cuánto tiempo un punto de conexión puede evitar una actualización o cuántos exámenes puede perder antes de que sea necesario actualizarse y examinarse por sí mismo.</span><span class="sxs-lookup"><span data-stu-id="504dc-107">Microsoft Defender Antivirus lets you define how long an endpoint can avoid an update or how many scans it can miss before it is required to update and scan itself.</span></span> <span data-ttu-id="504dc-108">Esto es especialmente útil en entornos donde los dispositivos no suelen estar conectados a una red corporativa o externa, o dispositivos que no se usan a diario.</span><span class="sxs-lookup"><span data-stu-id="504dc-108">This is especially useful in environments where devices are not often connected to a corporate or external network, or devices that are not used on a daily basis.</span></span>

<span data-ttu-id="504dc-109">Por ejemplo, un empleado que usa un equipo determinado está en pausa durante tres días y no inicia sesión en su equipo durante ese tiempo.</span><span class="sxs-lookup"><span data-stu-id="504dc-109">For example, an employee that uses a particular PC is on break for three days and does not log on to their PC during that time.</span></span>

<span data-ttu-id="504dc-110">Cuando el usuario vuelva al trabajo e inicie sesión en su equipo, Antivirus de Microsoft Defender comprobará y descargará inmediatamente las actualizaciones de protección más recientes y ejecutará un examen.</span><span class="sxs-lookup"><span data-stu-id="504dc-110">When the user returns to work and logs on to their PC, Microsoft Defender Antivirus will immediately check and download the latest protection updates, and run a scan.</span></span>

## <a name="set-up-catch-up-protection-updates-for-endpoints-that-havent-updated-for-a-while"></a><span data-ttu-id="504dc-111">Configurar actualizaciones de protección de ponerse al día para puntos de conexión que no se han actualizado durante un tiempo</span><span class="sxs-lookup"><span data-stu-id="504dc-111">Set up catch-up protection updates for endpoints that haven't updated for a while</span></span>

<span data-ttu-id="504dc-112">Si Antivirus de Microsoft Defender no descargó actualizaciones de protección durante un período especificado, puede configurarlo para comprobar y descargar automáticamente la actualización más reciente en el siguiente inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="504dc-112">If Microsoft Defender Antivirus did not download protection updates for a specified period, you can set it up to automatically check and download the latest update at the next log on.</span></span> <span data-ttu-id="504dc-113">Esto resulta útil si ha deshabilitado [globalmente las descargas](manage-event-based-updates-microsoft-defender-antivirus.md)automáticas de actualizaciones al iniciar .</span><span class="sxs-lookup"><span data-stu-id="504dc-113">This is useful if you have [globally disabled automatic update downloads on startup](manage-event-based-updates-microsoft-defender-antivirus.md).</span></span>

### <a name="use-configuration-manager-to-configure-catch-up-protection-updates"></a><span data-ttu-id="504dc-114">Usar Configuration Manager para configurar actualizaciones de protección de ponerse al día</span><span class="sxs-lookup"><span data-stu-id="504dc-114">Use Configuration Manager to configure catch-up protection updates</span></span>

1.  <span data-ttu-id="504dc-115">En la consola de Microsoft Endpoint Manager, abra la  directiva de antimalware que desea cambiar (haga clic en Activos y cumplimiento en el panel de navegación de la izquierda y, a continuación, expanda el árbol a **Overview**  >  **Endpoint Protection**  >  **Antimalware Policies**)</span><span class="sxs-lookup"><span data-stu-id="504dc-115">On your Microsoft Endpoint Manager console, open the antimalware policy you want to change (click **Assets and Compliance** in the navigation pane on the left, then expand the tree to **Overview** > **Endpoint Protection** > **Antimalware Policies**)</span></span>

2.  <span data-ttu-id="504dc-116">Vaya a la **sección Actualizaciones de inteligencia de** seguridad y configure las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="504dc-116">Go to the **Security intelligence updates** section and configure the following settings:</span></span>

    1. <span data-ttu-id="504dc-117">Establece Forzar una actualización de inteligencia de seguridad si el equipo cliente está sin conexión durante más de dos actualizaciones **programadas consecutivas** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="504dc-117">Set **Force a security intelligence update if the client computer is offline for more than two consecutive scheduled updates** to **Yes**.</span></span>
    2. <span data-ttu-id="504dc-118">For the  **If Configuration Manager is used as a source for security intelligence updates...**, specify the hours before which the protection updates delivered by Configuration Manager should be considered out-of-date.</span><span class="sxs-lookup"><span data-stu-id="504dc-118">For the  **If Configuration Manager is used as a source for security intelligence updates...**, specify the hours before which the protection updates delivered by Configuration Manager should be considered out-of-date.</span></span> <span data-ttu-id="504dc-119">Esto hará que se utilice la siguiente ubicación de actualización, en función del orden de origen [de reserva definido.](manage-protection-updates-microsoft-defender-antivirus.md#fallback-order)</span><span class="sxs-lookup"><span data-stu-id="504dc-119">This will cause the next update location to be used, based on the defined [fallback source order](manage-protection-updates-microsoft-defender-antivirus.md#fallback-order).</span></span>

3. <span data-ttu-id="504dc-120">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="504dc-120">Click **OK**.</span></span>

4.  <span data-ttu-id="504dc-121">[Implemente la directiva actualizada como de costumbre.](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers)</span><span class="sxs-lookup"><span data-stu-id="504dc-121">[Deploy the updated policy as usual](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers).</span></span>

### <a name="use-group-policy-to-enable-and-configure-the-catch-up-update-feature"></a><span data-ttu-id="504dc-122">Usar la directiva de grupo para habilitar y configurar la característica de actualización de ponerse al día</span><span class="sxs-lookup"><span data-stu-id="504dc-122">Use Group Policy to enable and configure the catch-up update feature</span></span>

1. <span data-ttu-id="504dc-123">En el equipo de administración de directivas de grupo, abra la Consola de administración de directivas de [grupo,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))haga clic con el botón secundario en el objeto de directiva de grupo que desea configurar y haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="504dc-123">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="504dc-124">En el **Editor de administración de directivas de grupo** vaya a Configuración del **equipo.**</span><span class="sxs-lookup"><span data-stu-id="504dc-124">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="504dc-125">Haga clic **en Directivas** **y, a continuación, en Plantillas administrativas.**</span><span class="sxs-lookup"><span data-stu-id="504dc-125">Click **Policies** then **Administrative templates**.</span></span>

4. <span data-ttu-id="504dc-126">Expande el árbol a **componentes de Windows > Actualizaciones de firmas > antivirus de Microsoft Defender.**</span><span class="sxs-lookup"><span data-stu-id="504dc-126">Expand the tree to **Windows components > Microsoft Defender Antivirus > Signature Updates**.</span></span>

5. <span data-ttu-id="504dc-127">Haga doble clic en **la opción Definir el número** de días después de los cuales es necesaria una actualización de inteligencia de seguridad de ponerse al día y establezca la opción en **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="504dc-127">Double-click the **Define the number of days after which a catch-up security intelligence update is required** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="504dc-128">Escribe el número de días después de los cuales quieres que Microsoft Defender AV compruebe y descargue la actualización de protección más reciente.</span><span class="sxs-lookup"><span data-stu-id="504dc-128">Enter the number of days after which you want Microsoft Defender AV to check for and download the latest protection update.</span></span>

6. <span data-ttu-id="504dc-129">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="504dc-129">Click **OK**.</span></span>

### <a name="use-powershell-cmdlets-to-configure-catch-up-protection-updates"></a><span data-ttu-id="504dc-130">Usar cmdlets de PowerShell para configurar actualizaciones de protección de ponerse al día</span><span class="sxs-lookup"><span data-stu-id="504dc-130">Use PowerShell cmdlets to configure catch-up protection updates</span></span>

<span data-ttu-id="504dc-131">Use los cmdlets siguientes:</span><span class="sxs-lookup"><span data-stu-id="504dc-131">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -SignatureUpdateCatchupInterval
```

<span data-ttu-id="504dc-132">Consulte [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md)  and Defender [cmdlets](/powershell/module/defender/) para obtener más información sobre cómo usar PowerShell con Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="504dc-132">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md)  and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi-to-configure-catch-up-protection-updates"></a><span data-ttu-id="504dc-133">Usar Instrucciones de administración de Windows (WMI) para configurar actualizaciones de protección de ponerse al día</span><span class="sxs-lookup"><span data-stu-id="504dc-133">Use Windows Management Instruction (WMI) to configure catch-up protection updates</span></span>

<span data-ttu-id="504dc-134">Utilice el [ **método Set** de la **clase MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) para las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="504dc-134">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
SignatureUpdateCatchupInterval
```

<span data-ttu-id="504dc-135">Vea lo siguiente para obtener más información y parámetros permitidos:</span><span class="sxs-lookup"><span data-stu-id="504dc-135">See the following for more information and allowed parameters:</span></span>
- [<span data-ttu-id="504dc-136">Windows Defender API WMIv2</span><span class="sxs-lookup"><span data-stu-id="504dc-136">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


## <a name="set-the-number-of-days-before-protection-is-reported-as-out-of-date"></a><span data-ttu-id="504dc-137">Establecer el número de días antes de que se notifica la protección como desaprotección</span><span class="sxs-lookup"><span data-stu-id="504dc-137">Set the number of days before protection is reported as out-of-date</span></span>

<span data-ttu-id="504dc-138">También puede especificar el número de días después de los cuales la protección de Antivirus de Microsoft Defender se considera antigua o desaprotección.</span><span class="sxs-lookup"><span data-stu-id="504dc-138">You can also specify the number of days after which Microsoft Defender Antivirus protection is considered old or out-of-date.</span></span> <span data-ttu-id="504dc-139">Después del número de días especificado, el cliente se presentará como desa fecha y mostrará un error al usuario del equipo.</span><span class="sxs-lookup"><span data-stu-id="504dc-139">After the specified number of days, the client will report itself as out-of-date, and show an error to the user of the PC.</span></span> <span data-ttu-id="504dc-140">También puede provocar que Antivirus de Microsoft Defender intente descargar una actualización de otros orígenes (en función del orden de origen de reserva [definido),](manage-protection-updates-microsoft-defender-antivirus.md#fallback-order)como cuando se usa MMPC como origen secundario después de establecer WSUS o Microsoft Update como el primer origen.</span><span class="sxs-lookup"><span data-stu-id="504dc-140">It may also cause Microsoft Defender Antivirus to attempt to download an update from other sources (based on the defined [fallback source order](manage-protection-updates-microsoft-defender-antivirus.md#fallback-order)), such as when using MMPC as a secondary source after setting WSUS or Microsoft Update as the first source.</span></span>

### <a name="use-group-policy-to-specify-the-number-of-days-before-protection-is-considered-out-of-date"></a><span data-ttu-id="504dc-141">Usar la directiva de grupo para especificar el número de días antes de que la protección se considere des actualizada</span><span class="sxs-lookup"><span data-stu-id="504dc-141">Use Group Policy to specify the number of days before protection is considered out-of-date</span></span>

1.  <span data-ttu-id="504dc-142">En el equipo de administración de directivas de grupo, abra la Consola de administración de directivas de [grupo,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))haga clic con el botón secundario en el objeto de directiva de grupo que desea configurar y haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="504dc-142">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

3.  <span data-ttu-id="504dc-143">En el **Editor de administración de directivas de grupo** vaya a Configuración del **equipo.**</span><span class="sxs-lookup"><span data-stu-id="504dc-143">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

4.  <span data-ttu-id="504dc-144">Haga clic **en Directivas** **y, a continuación, en Plantillas administrativas.**</span><span class="sxs-lookup"><span data-stu-id="504dc-144">Click **Policies** then **Administrative templates**.</span></span>

5.  <span data-ttu-id="504dc-145">Expande el árbol a **componentes de Windows > Microsoft Defender Antivirus > de firmas y** configura las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="504dc-145">Expand the tree to **Windows components > Microsoft Defender Antivirus > Signature Updates** and configure the following settings:</span></span>

    1.  <span data-ttu-id="504dc-146">Haga doble clic en Definir el número de días antes de que las definiciones de spyware se consideren **des actualizadas** y establezca la opción en **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="504dc-146">Double-click **Define the number of days before spyware definitions are considered out of date** and set the option to **Enabled**.</span></span> <span data-ttu-id="504dc-147">Escriba el número de días después de los cuales desea que Microsoft Defender AV considere que la inteligencia de seguridad de spyware está des actualizada.</span><span class="sxs-lookup"><span data-stu-id="504dc-147">Enter the number of days after which you want Microsoft Defender AV to consider spyware Security intelligence to be out-of-date.</span></span>

    2. <span data-ttu-id="504dc-148">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="504dc-148">Click **OK**.</span></span>

    3.  <span data-ttu-id="504dc-149">Haga doble clic en Definir el número de días antes de que las definiciones de virus se consideren **des actualizadas** y establezca la opción en **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="504dc-149">Double-click **Define the number of days before virus definitions are considered out of date** and set the option to **Enabled**.</span></span> <span data-ttu-id="504dc-150">Escriba el número de días después de los cuales desea que Microsoft Defender AV considere que la inteligencia de seguridad de virus está des actualizada.</span><span class="sxs-lookup"><span data-stu-id="504dc-150">Enter the number of days after which you want Microsoft Defender AV to consider virus Security intelligence to be out-of-date.</span></span>

    4. <span data-ttu-id="504dc-151">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="504dc-151">Click **OK**.</span></span>


## <a name="set-up-catch-up-scans-for-endpoints-that-have-not-been-scanned-for-a-while"></a><span data-ttu-id="504dc-152">Configurar exámenes de ponerse al día para los puntos de conexión que no se han analizado durante un tiempo</span><span class="sxs-lookup"><span data-stu-id="504dc-152">Set up catch-up scans for endpoints that have not been scanned for a while</span></span>

<span data-ttu-id="504dc-153">Puedes establecer el número de exámenes programados consecutivos que se pueden perder antes de que Antivirus de Microsoft Defender forzará un examen.</span><span class="sxs-lookup"><span data-stu-id="504dc-153">You can set the number of consecutive scheduled scans that can be missed before Microsoft Defender Antivirus will force a scan.</span></span>

<span data-ttu-id="504dc-154">El proceso para habilitar esta característica es:</span><span class="sxs-lookup"><span data-stu-id="504dc-154">The process for enabling this feature is:</span></span>

1. <span data-ttu-id="504dc-155">Configure al menos un examen programado (consulte el [tema Programar exámenes).](scheduled-catch-up-scans-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="504dc-155">Set up at least one scheduled scan (see the [Schedule scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md) topic).</span></span>
2. <span data-ttu-id="504dc-156">Habilite la característica de examen de ponerse al día.</span><span class="sxs-lookup"><span data-stu-id="504dc-156">Enable the catch-up scan feature.</span></span>
3. <span data-ttu-id="504dc-157">Defina el número de exámenes que se pueden omitir antes de que se produzca un examen de ponerse al día.</span><span class="sxs-lookup"><span data-stu-id="504dc-157">Define the number of scans that can be skipped before a catch-up scan occurs.</span></span>

<span data-ttu-id="504dc-158">Esta característica se puede habilitar para exámenes completos y rápidos.</span><span class="sxs-lookup"><span data-stu-id="504dc-158">This feature can be enabled for both full and quick scans.</span></span>

### <a name="use-group-policy-to-enable-and-configure-the-catch-up-scan-feature"></a><span data-ttu-id="504dc-159">Usar la directiva de grupo para habilitar y configurar la característica de examen de ponerse al día</span><span class="sxs-lookup"><span data-stu-id="504dc-159">Use Group Policy to enable and configure the catch-up scan feature</span></span>

1.  <span data-ttu-id="504dc-160">Asegúrese de haber configurado al menos un examen programado.</span><span class="sxs-lookup"><span data-stu-id="504dc-160">Ensure you have set up at least one scheduled scan.</span></span>

2.  <span data-ttu-id="504dc-161">En el equipo de administración de directivas de grupo, abra la Consola de administración de directivas de [grupo,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))haga clic con el botón secundario en el objeto de directiva de grupo que desea configurar y haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="504dc-161">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

3.  <span data-ttu-id="504dc-162">En el **Editor de administración de directivas de grupo** vaya a Configuración del **equipo.**</span><span class="sxs-lookup"><span data-stu-id="504dc-162">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

4.  <span data-ttu-id="504dc-163">Haga clic **en Directivas** **y, a continuación, en Plantillas administrativas.**</span><span class="sxs-lookup"><span data-stu-id="504dc-163">Click **Policies** then **Administrative templates**.</span></span>

5.  <span data-ttu-id="504dc-164">Expande el árbol a **componentes de Windows > Antivirus > Antivirus** de Microsoft Defender y configura las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="504dc-164">Expand the tree to **Windows components > Microsoft Defender Antivirus > Scan** and configure the following settings:</span></span>

    1.  <span data-ttu-id="504dc-165">Si ha configurado los exámenes rápidos programados, haga doble clic en la configuración Activar detección rápida y establezca la opción en **Habilitado**. </span><span class="sxs-lookup"><span data-stu-id="504dc-165">If you have set up scheduled quick scans, double-click the **Turn on catch-up quick scan** setting and set the option to **Enabled**.</span></span> 
    2. <span data-ttu-id="504dc-166">Si ha configurado exámenes completos programados,  haga doble clic en la configuración Activar examen completo de puesta al día y establezca la opción en **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="504dc-166">If you have set up scheduled full scans, double-click the **Turn on catch-up full scan** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="504dc-167">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="504dc-167">Click **OK**.</span></span>
    3. <span data-ttu-id="504dc-168">Haga doble clic en **la opción Definir el** número de días después de los cuales se forzará la configuración de un examen de puesta al día y establezca la opción en **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="504dc-168">Double-click the **Define the number of days after which a catch-up scan is forced** setting and set the option to **Enabled**.</span></span> 
    4. <span data-ttu-id="504dc-169">Escriba el número de exámenes que se pueden perder antes de que se ejecute automáticamente un examen cuando el siguiente usuario inicie sesión en el equipo.</span><span class="sxs-lookup"><span data-stu-id="504dc-169">Enter the number of scans that can be missed before a scan will be automatically run when the user next logs on to the PC.</span></span> <span data-ttu-id="504dc-170">El tipo de examen que se ejecuta viene determinado por el parámetro **Specify the scan type to use for a scheduled scan** (vea el tema Schedule [scans).](scheduled-catch-up-scans-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="504dc-170">The type of scan that is run is determined by the **Specify the scan type to use for a scheduled scan** (see the [Schedule scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md) topic).</span></span> <span data-ttu-id="504dc-171">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="504dc-171">Click **OK**.</span></span>

> [!NOTE]
> <span data-ttu-id="504dc-172">El título de configuración de directiva de grupo hace referencia al número de días.</span><span class="sxs-lookup"><span data-stu-id="504dc-172">The Group Policy setting title refers to the number of days.</span></span> <span data-ttu-id="504dc-173">Sin embargo, la configuración se aplica al número de exámenes (no días) antes de que se ejecute el examen de puesta al día.</span><span class="sxs-lookup"><span data-stu-id="504dc-173">The setting, however, is applied to the number of scans (not days) before the catch-up scan will be run.</span></span>

### <a name="use-powershell-cmdlets-to-configure-catch-up-scans"></a><span data-ttu-id="504dc-174">Usar cmdlets de PowerShell para configurar exámenes de ponerse al día</span><span class="sxs-lookup"><span data-stu-id="504dc-174">Use PowerShell cmdlets to configure catch-up scans</span></span>

<span data-ttu-id="504dc-175">Use los cmdlets siguientes:</span><span class="sxs-lookup"><span data-stu-id="504dc-175">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -DisableCatchupFullScan
Set-MpPreference -DisableCatchupQuickScan

```

<span data-ttu-id="504dc-176">Consulte [Use PowerShell cmdlets to manage Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md)  and Defender [cmdlets](/powershell/module/defender/) para obtener más información sobre cómo usar PowerShell con Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="504dc-176">See [Use PowerShell cmdlets to manage Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md)  and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi-to-configure-catch-up-scans"></a><span data-ttu-id="504dc-177">Usar instrucciones de administración de Windows (WMI) para configurar exámenes de ponerse al día</span><span class="sxs-lookup"><span data-stu-id="504dc-177">Use Windows Management Instruction (WMI) to configure catch-up scans</span></span>

<span data-ttu-id="504dc-178">Utilice el [ **método Set** de la **clase MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) para las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="504dc-178">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
DisableCatchupFullScan
DisableCatchupQuickScan
```

<span data-ttu-id="504dc-179">Vea lo siguiente para obtener más información y parámetros permitidos:</span><span class="sxs-lookup"><span data-stu-id="504dc-179">See the following for more information and allowed parameters:</span></span>
- [<span data-ttu-id="504dc-180">Windows Defender API WMIv2</span><span class="sxs-lookup"><span data-stu-id="504dc-180">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


### <a name="use-configuration-manager-to-configure-catch-up-scans"></a><span data-ttu-id="504dc-181">Usar Configuration Manager para configurar exámenes de ponerse al día</span><span class="sxs-lookup"><span data-stu-id="504dc-181">Use Configuration Manager to configure catch-up scans</span></span>

1.  <span data-ttu-id="504dc-182">En la consola de Microsoft Endpoint Manager, abra la  directiva de antimalware que desea cambiar (haga clic en Activos y cumplimiento en el panel de navegación de la izquierda y, a continuación, expanda el árbol a **Overview**  >  **Endpoint Protection**  >  **Antimalware Policies**)</span><span class="sxs-lookup"><span data-stu-id="504dc-182">On your Microsoft Endpoint Manager console, open the antimalware policy you want to change (click **Assets and Compliance** in the navigation pane on the left, then expand the tree to **Overview** > **Endpoint Protection** > **Antimalware Policies**)</span></span>

2.  <span data-ttu-id="504dc-183">Vaya a la **sección Exámenes programados** y Forzar un examen del tipo de examen seleccionado si el equipo cliente **está sin conexión...** a **Sí**.</span><span class="sxs-lookup"><span data-stu-id="504dc-183">Go to the **Scheduled scans** section and **Force a scan of the selected scan type if client computer is offline...** to **Yes**.</span></span> 

3. <span data-ttu-id="504dc-184">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="504dc-184">Click **OK**.</span></span>

4.  <span data-ttu-id="504dc-185">[Implemente la directiva actualizada como de costumbre.](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers)</span><span class="sxs-lookup"><span data-stu-id="504dc-185">[Deploy the updated policy as usual](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers).</span></span>

## <a name="related-articles"></a><span data-ttu-id="504dc-186">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="504dc-186">Related articles</span></span>

- [<span data-ttu-id="504dc-187">Implementar antivirus de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="504dc-187">Deploy Microsoft Defender Antivirus</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)
- [<span data-ttu-id="504dc-188">Administrar actualizaciones de Antivirus de Microsoft Defender y aplicar líneas base</span><span class="sxs-lookup"><span data-stu-id="504dc-188">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>](manage-updates-baselines-microsoft-defender-antivirus.md)
- [<span data-ttu-id="504dc-189">Administrar cuándo se deben descargar y aplicar las actualizaciones de protección</span><span class="sxs-lookup"><span data-stu-id="504dc-189">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md)
- [<span data-ttu-id="504dc-190">Administrar actualizaciones forzadas basadas en eventos</span><span class="sxs-lookup"><span data-stu-id="504dc-190">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md)
- [<span data-ttu-id="504dc-191">Administrar actualizaciones para dispositivos móviles y máquinas virtuales (VM)</span><span class="sxs-lookup"><span data-stu-id="504dc-191">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [<span data-ttu-id="504dc-192">Antivirus de Microsoft Defender en Windows 10</span><span class="sxs-lookup"><span data-stu-id="504dc-192">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)