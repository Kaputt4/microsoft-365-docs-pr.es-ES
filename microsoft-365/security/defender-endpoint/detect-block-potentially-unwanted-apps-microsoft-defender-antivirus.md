---
title: Bloquear aplicaciones potencialmente no deseadas con Antivirus de Microsoft Defender
description: Habilite la característica antivirus de aplicaciones potencialmente no deseadas (PUA) para bloquear software no deseado como el software publicitario.
keywords: pua, enable, software no deseado, aplicaciones no deseadas, adware, barra de herramientas del explorador, detectar, bloquear, Antivirus de Microsoft Defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: detect
ms.sitesec: library
localization_priority: priority
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
audience: ITPro
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 20d4767f9813b741c55109d617f78302feaa0f7e
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765028"
---
# <a name="detect-and-block-potentially-unwanted-applications"></a><span data-ttu-id="a1646-104">Detectar y bloquear aplicaciones potencialmente no deseadas</span><span class="sxs-lookup"><span data-stu-id="a1646-104">Detect and block potentially unwanted applications</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="a1646-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="a1646-105">**Applies to:**</span></span>

- [<span data-ttu-id="a1646-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="a1646-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- [<span data-ttu-id="a1646-107">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="a1646-107">Microsoft Edge</span></span>](/microsoft-edge/deploy/microsoft-edge)

> [!NOTE]
> <span data-ttu-id="a1646-108">Las aplicaciones potencialmente no deseadas (PUA) son una categoría de software que puede hacer que el equipo se ejecute lentamente, muestre anuncios inesperados o, en el peor de los casos, instale otro software que pueda ser inesperado o no deseado.</span><span class="sxs-lookup"><span data-stu-id="a1646-108">Potentially unwanted applications (PUA) are a category of software that can cause your machine to run slowly, display unexpected ads, or at worst, install other software which might be unexpected or unwanted.</span></span> <span data-ttu-id="a1646-109">De forma predeterminada en Windows 10 (versión 2004 y versiones posteriores), Antivirus de Microsoft Defender bloquea aplicaciones que se consideran PUA, para dispositivos Enterprise (E5).</span><span class="sxs-lookup"><span data-stu-id="a1646-109">By default in Windows 10 (version 2004 and later), Microsoft Defender Antivirus blocks apps that are considered PUA, for Enterprise (E5) devices.</span></span>

<span data-ttu-id="a1646-110">Las aplicaciones potencialmente no deseadas (PUA) no se consideran virus, malware u otros tipos de amenazas, pero pueden realizar acciones en puntos de conexión que afecten negativamente al rendimiento o uso de los puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="a1646-110">Potentially unwanted applications (PUA) are not considered viruses, malware, or other types of threats, but they might perform actions on endpoints which adversely affect endpoint performance or use.</span></span> <span data-ttu-id="a1646-111">_LA PUA_ también puede hacer referencia a una aplicación que tiene una mala reputación, según lo evaluado por Microsoft Defender para Endpoint, debido a ciertos tipos de comportamiento no deseado.</span><span class="sxs-lookup"><span data-stu-id="a1646-111">_PUA_ can also refer to an application that has a poor reputation, as assessed by Microsoft Defender for Endpoint, due to certain kinds of undesirable behavior.</span></span>

<span data-ttu-id="a1646-112">Estos son algunos ejemplos:</span><span class="sxs-lookup"><span data-stu-id="a1646-112">Here are some examples:</span></span>

- <span data-ttu-id="a1646-113">**Software de** publicidad que muestra anuncios o promociones, incluido el software que inserta anuncios en páginas web.</span><span class="sxs-lookup"><span data-stu-id="a1646-113">**Advertising software** that displays advertisements or promotions, including software that inserts advertisements to webpages.</span></span>
- <span data-ttu-id="a1646-114">**Agrupación de software** que ofrece instalar otro software que no está firmado digitalmente por la misma entidad.</span><span class="sxs-lookup"><span data-stu-id="a1646-114">**Bundling software** that offers to install other software that is not digitally signed by the same entity.</span></span> <span data-ttu-id="a1646-115">Además, software que ofrece instalar otro software que califique como PUA.</span><span class="sxs-lookup"><span data-stu-id="a1646-115">Also, software that offers to install other software that qualify as PUA.</span></span>
- <span data-ttu-id="a1646-116">**Software de evasión** que intenta eludir activamente la detección por parte de productos de seguridad, incluido el software que se comporta de forma diferente en presencia de productos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="a1646-116">**Evasion software** that actively tries to evade detection by security products, including software that behaves differently in the presence of security products.</span></span>

> [!TIP]
> <span data-ttu-id="a1646-117">Para obtener más ejemplos y una explicación de los criterios que usamos para etiquetar las aplicaciones para una atención especial de las características de seguridad, vea [How Microsoft identifies malware and potentially unwanted applications](/windows/security/threat-protection/intelligence/criteria).</span><span class="sxs-lookup"><span data-stu-id="a1646-117">For more examples and a discussion of the criteria we use to label applications for special attention from security features, see [How Microsoft identifies malware and potentially unwanted applications](/windows/security/threat-protection/intelligence/criteria).</span></span>

<span data-ttu-id="a1646-118">Las aplicaciones potencialmente no deseadas pueden aumentar el riesgo de que la red se infecte con malware real, dificultar la identificación de las infecciones de malware o desperdiciar recursos de TI al limpiarlas.</span><span class="sxs-lookup"><span data-stu-id="a1646-118">Potentially unwanted applications can increase the risk of your network being infected with actual malware, make malware infections harder to identify, or waste IT resources in cleaning them up.</span></span> <span data-ttu-id="a1646-119">La protección pua se admite en Windows 10, Windows Server 2019 y Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="a1646-119">PUA protection is supported on Windows 10, Windows Server 2019, and Windows Server 2016.</span></span>

## <a name="microsoft-edge"></a><span data-ttu-id="a1646-120">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="a1646-120">Microsoft Edge</span></span>

<span data-ttu-id="a1646-121">El [nuevo Microsoft Edge,](https://support.microsoft.com/microsoft-edge/get-to-know-microsoft-edge-3f4bb0ff-58de-2188-55c0-f560b7e20bea)basado en Chromium, bloquea las descargas de aplicaciones potencialmente no deseadas y las direcciones URL de recursos asociadas.</span><span class="sxs-lookup"><span data-stu-id="a1646-121">The [new Microsoft Edge](https://support.microsoft.com/microsoft-edge/get-to-know-microsoft-edge-3f4bb0ff-58de-2188-55c0-f560b7e20bea), which is Chromium-based, blocks potentially unwanted application downloads and associated resource URLs.</span></span> <span data-ttu-id="a1646-122">Esta característica se proporciona a través [de SmartScreen de Microsoft Defender.](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview)</span><span class="sxs-lookup"><span data-stu-id="a1646-122">This feature is provided via [Microsoft Defender SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview).</span></span>

### <a name="enable-pua-protection-in-chromium-based-microsoft-edge"></a><span data-ttu-id="a1646-123">Habilitar la protección de PUA en Microsoft Edge basado en Chromium</span><span class="sxs-lookup"><span data-stu-id="a1646-123">Enable PUA protection in Chromium-based Microsoft Edge</span></span>

<span data-ttu-id="a1646-124">Aunque la protección de aplicaciones potencialmente no deseada en Microsoft Edge (basada en Chromium, versión 80.0.361.50) está desactivada de forma predeterminada, se puede desactivar fácilmente desde el explorador.</span><span class="sxs-lookup"><span data-stu-id="a1646-124">Although potentially unwanted application protection in Microsoft Edge (Chromium-based, version 80.0.361.50) is turned off by default, it can easily be turned on from within the browser.</span></span>

1. <span data-ttu-id="a1646-125">Seleccione los puntos suspensivos y, a continuación, **elija Configuración**.</span><span class="sxs-lookup"><span data-stu-id="a1646-125">Select the ellipses, and then choose **Settings**.</span></span>
2. <span data-ttu-id="a1646-126">Seleccione **Privacidad, búsqueda y servicios**.</span><span class="sxs-lookup"><span data-stu-id="a1646-126">Select **Privacy, search, and services**.</span></span>
3. <span data-ttu-id="a1646-127">En la **sección Seguridad,** activa **Bloquear aplicaciones potencialmente no deseadas.**</span><span class="sxs-lookup"><span data-stu-id="a1646-127">Under the **Security** section, turn on **Block potentially unwanted apps**.</span></span>

> [!TIP]
> <span data-ttu-id="a1646-128">Si ejecuta Microsoft Edge (basado en Chromium), puede explorar con seguridad la característica de bloqueo de direcciones URL de la protección pua mediante la prueba en una de nuestras páginas de demostración de SmartScreen de [Microsoft Defender.](https://demo.smartscreen.msft.net/)</span><span class="sxs-lookup"><span data-stu-id="a1646-128">If you are running Microsoft Edge (Chromium-based), you can safely explore the URL-blocking feature of PUA protection by testing it out on one of our [Microsoft Defender SmartScreen demo pages](https://demo.smartscreen.msft.net/).</span></span>

### <a name="blocking-urls-with-microsoft-defender-smartscreen"></a><span data-ttu-id="a1646-129">Bloquear direcciones URL con SmartScreen de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="a1646-129">Blocking URLs with Microsoft Defender SmartScreen</span></span>

<span data-ttu-id="a1646-130">En Chromium-based Edge with PUA protection turned on, Microsoft Defender SmartScreen te protege de las direcciones URL asociadas a PUA.</span><span class="sxs-lookup"><span data-stu-id="a1646-130">In Chromium-based Edge with PUA protection turned on, Microsoft Defender SmartScreen protects you from PUA-associated URLs.</span></span>

<span data-ttu-id="a1646-131">Los administradores de seguridad pueden [configurar](/DeployEdge/configure-microsoft-edge) el modo en que Microsoft Edge y SmartScreen de Microsoft Defender trabajan juntos para proteger grupos de usuarios de direcciones URL asociadas a PUA.</span><span class="sxs-lookup"><span data-stu-id="a1646-131">Security admins can [configure](/DeployEdge/configure-microsoft-edge) how Microsoft Edge and Microsoft Defender SmartScreen work together to protect groups of users from PUA-associated URLs.</span></span> <span data-ttu-id="a1646-132">Hay varias opciones [de configuración de directiva de grupo](/DeployEdge/microsoft-edge-policies#smartscreen-settings) explícitamente disponibles para SmartScreen de Microsoft Defender, incluida una para bloquear [PUA](/DeployEdge/microsoft-edge-policies#smartscreenpuaenabled).</span><span class="sxs-lookup"><span data-stu-id="a1646-132">There are several [group policy settings](/DeployEdge/microsoft-edge-policies#smartscreen-settings) explicitly for Microsoft Defender SmartScreen available, including [one for blocking PUA](/DeployEdge/microsoft-edge-policies#smartscreenpuaenabled).</span></span> <span data-ttu-id="a1646-133">Además, los administradores pueden configurar [SmartScreen](/microsoft-edge/deploy/available-policies?source=docs#configure-windows-defender-smartscreen) de Microsoft Defender en su conjunto, mediante la configuración de directiva de grupo para activar o desactivar SmartScreen de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="a1646-133">In addition, admins can [configure Microsoft Defender SmartScreen](/microsoft-edge/deploy/available-policies?source=docs#configure-windows-defender-smartscreen) as a whole, using group policy settings to turn Microsoft Defender SmartScreen on or off.</span></span>

<span data-ttu-id="a1646-134">Aunque Microsoft Defender para endpoint tiene su propia lista de bloqueo basada en un conjunto de datos administrado por Microsoft, puede personalizar esta lista en función de su propia inteligencia de amenazas.</span><span class="sxs-lookup"><span data-stu-id="a1646-134">Although Microsoft Defender for Endpoint has its own block list based upon a data set managed by Microsoft, you can customize this list based on your own threat intelligence.</span></span> <span data-ttu-id="a1646-135">Si crea [y administra indicadores en](/microsoft-365/security/defender-endpoint/manage-indicators) el portal de Microsoft Defender para endpoints, SmartScreen de Microsoft Defender respeta la nueva configuración.</span><span class="sxs-lookup"><span data-stu-id="a1646-135">If you [create and manage indicators](/microsoft-365/security/defender-endpoint/manage-indicators) in the Microsoft Defender for Endpoint portal, Microsoft Defender SmartScreen respects the new settings.</span></span>

## <a name="microsoft-defender-antivirus"></a><span data-ttu-id="a1646-136">Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="a1646-136">Microsoft Defender Antivirus</span></span>

<span data-ttu-id="a1646-137">La característica de protección de aplicaciones potencialmente no deseadas (PUA) en Antivirus de Microsoft Defender puede detectar y bloquear LASA en puntos de conexión de la red.</span><span class="sxs-lookup"><span data-stu-id="a1646-137">The potentially unwanted application (PUA) protection feature in Microsoft Defender Antivirus can detect and block PUAs on endpoints in your network.</span></span>

> [!NOTE]
> <span data-ttu-id="a1646-138">Esta característica está disponible en Windows 10, Windows Server 2019 y Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="a1646-138">This feature is available in Windows 10, Windows Server 2019, and Windows Server 2016.</span></span>

<span data-ttu-id="a1646-139">Antivirus de Microsoft Defender bloquea los archivos PUA detectados y cualquier intento de descargarlos, moverlos, ejecutarlos o instalarlos.</span><span class="sxs-lookup"><span data-stu-id="a1646-139">Microsoft Defender Antivirus blocks detected PUA files and any attempts to download, move, run, or install them.</span></span> <span data-ttu-id="a1646-140">Los archivos PUA bloqueados se mueven a la cuarentena.</span><span class="sxs-lookup"><span data-stu-id="a1646-140">Blocked PUA files are then moved to quarantine.</span></span> <span data-ttu-id="a1646-141">Cuando se detecta un archivo PUA en un punto de conexión, Antivirus de Microsoft Defender envía una notificación al usuario ( a menos que las notificaciones se hayan deshabilitado ) en el mismo formato que[otras](configure-notifications-microsoft-defender-antivirus.md)detecciones de amenazas.</span><span class="sxs-lookup"><span data-stu-id="a1646-141">When a PUA file is detected on an endpoint, Microsoft Defender Antivirus sends a notification to the user ([unless notifications have been disabled](configure-notifications-microsoft-defender-antivirus.md)) in the same format as other threat detections.</span></span> <span data-ttu-id="a1646-142">La notificación está precedida de para `PUA:` indicar su contenido.</span><span class="sxs-lookup"><span data-stu-id="a1646-142">The notification is prefaced with `PUA:` to indicate its content.</span></span>

<span data-ttu-id="a1646-143">La notificación aparece en la lista de [cuarentena habitual dentro de la aplicación Seguridad de Windows](microsoft-defender-security-center-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="a1646-143">The notification appears in the usual [quarantine list within the Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span>

### <a name="configure-pua-protection-in-microsoft-defender-antivirus"></a><span data-ttu-id="a1646-144">Configurar la protección de LA PUA en Antivirus de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="a1646-144">Configure PUA protection in Microsoft Defender Antivirus</span></span>

<span data-ttu-id="a1646-145">Puede habilitar la protección de PUA con [Microsoft Intune,](/mem/intune/protect/device-protect) [Microsoft Endpoint Configuration Manager,](/mem/configmgr/protect/deploy-use/endpoint-protection) [directiva](/azure/active-directory-domain-services/manage-group-policy)de grupo o mediante [cmdlets de PowerShell](/powershell/module/defender/?preserve-view=true&view=win10-ps).</span><span class="sxs-lookup"><span data-stu-id="a1646-145">You can enable PUA protection with [Microsoft Intune](/mem/intune/protect/device-protect), [Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection), [Group Policy](/azure/active-directory-domain-services/manage-group-policy), or via [PowerShell cmdlets](/powershell/module/defender/?preserve-view=true&view=win10-ps).</span></span>

<span data-ttu-id="a1646-146">También puede usar la protección pua en modo auditoría para detectar aplicaciones potencialmente no deseadas sin bloquearlas.</span><span class="sxs-lookup"><span data-stu-id="a1646-146">You can also use PUA protection in audit mode to detect potentially unwanted applications without blocking them.</span></span> <span data-ttu-id="a1646-147">Las detecciones se capturan en el registro de eventos de Windows.</span><span class="sxs-lookup"><span data-stu-id="a1646-147">The detections are captured in the Windows event log.</span></span>

> [!TIP]
> <span data-ttu-id="a1646-148">Visite el sitio web de demostración de Microsoft Defender para endpoint en [demo.wd.microsoft.com](https://demo.wd.microsoft.com/Page/UrlRep) para confirmar que la característica funciona y verla en acción.</span><span class="sxs-lookup"><span data-stu-id="a1646-148">Visit the Microsoft Defender for Endpoint demo website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com/Page/UrlRep) to confirm that the feature is working, and see it in action.</span></span>

<span data-ttu-id="a1646-149">La protección de PUA en modo auditoría es útil si su empresa realiza una comprobación de cumplimiento de seguridad de software interna y desea evitar falsos positivos.</span><span class="sxs-lookup"><span data-stu-id="a1646-149">PUA protection in audit mode is useful if your company is conducting an internal software security compliance check and you'd like to avoid any false positives.</span></span>

#### <a name="use-intune-to-configure-pua-protection"></a><span data-ttu-id="a1646-150">Usar Intune para configurar la protección de PUA</span><span class="sxs-lookup"><span data-stu-id="a1646-150">Use Intune to configure PUA protection</span></span>

<span data-ttu-id="a1646-151">Para [obtener más información,](/intune/device-restrictions-configure) consulta Configurar la configuración de restricción de dispositivos de Microsoft Intune y Antivirus de Microsoft Defender para [Windows 10 en Intune.](/intune/device-restrictions-windows-10#microsoft-defender-antivirus)</span><span class="sxs-lookup"><span data-stu-id="a1646-151">See [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure) and [Microsoft Defender Antivirus device restriction settings for Windows 10 in Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus) for more details.</span></span>

#### <a name="use-configuration-manager-to-configure-pua-protection"></a><span data-ttu-id="a1646-152">Usar Configuration Manager para configurar la protección de PUA</span><span class="sxs-lookup"><span data-stu-id="a1646-152">Use Configuration Manager to configure PUA protection</span></span>

<span data-ttu-id="a1646-153">La protección pua está habilitada de forma predeterminada en Microsoft Endpoint Manager (rama actual).</span><span class="sxs-lookup"><span data-stu-id="a1646-153">PUA protection is enabled by default in the Microsoft Endpoint Manager (Current Branch).</span></span>

<span data-ttu-id="a1646-154">Vea [How to create and deploy antimalware policies: Scheduled scans settings](/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings) for details on configuring Microsoft Endpoint Manager (Current Branch).</span><span class="sxs-lookup"><span data-stu-id="a1646-154">See [How to create and deploy antimalware policies: Scheduled scans settings](/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings) for details on configuring Microsoft Endpoint Manager (Current Branch).</span></span>

<span data-ttu-id="a1646-155">Para System Center 2012 Configuration Manager, consulte [How to Deploy Potentially Unwanted Application Protection Policy for Endpoint Protection in Configuration Manager](/previous-versions/system-center/system-center-2012-R2/hh508770(v=technet.10)#BKMK_PUA).</span><span class="sxs-lookup"><span data-stu-id="a1646-155">For System Center 2012 Configuration Manager, see [How to Deploy Potentially Unwanted Application Protection Policy for Endpoint Protection in Configuration Manager](/previous-versions/system-center/system-center-2012-R2/hh508770(v=technet.10)#BKMK_PUA).</span></span>

> [!NOTE]
> <span data-ttu-id="a1646-156">Los eventos de PUA bloqueados por Antivirus de Microsoft Defender se notifican en el Visor de eventos de Windows y no en Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="a1646-156">PUA events blocked by Microsoft Defender Antivirus are reported in the Windows Event Viewer and not in Microsoft Endpoint Configuration Manager.</span></span>

#### <a name="use-group-policy-to-configure-pua-protection"></a><span data-ttu-id="a1646-157">Usar la directiva de grupo para configurar la protección de LA PUA</span><span class="sxs-lookup"><span data-stu-id="a1646-157">Use Group Policy to configure PUA protection</span></span>

1. <span data-ttu-id="a1646-158">Descargar e instalar [plantillas administrativas (.admx) para Windows 10 October 2020 Update (20H2)](https://www.microsoft.com/download/details.aspx?id=102157)</span><span class="sxs-lookup"><span data-stu-id="a1646-158">Download and install [Administrative Templates (.admx) for Windows 10 October 2020 Update (20H2)](https://www.microsoft.com/download/details.aspx?id=102157)</span></span>

2. <span data-ttu-id="a1646-159">En el equipo de administración de directivas de grupo, abra la Consola [de administración de directivas de grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span><span class="sxs-lookup"><span data-stu-id="a1646-159">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

3. <span data-ttu-id="a1646-160">Seleccione el objeto de directiva de grupo que desea configurar y, a continuación, elija **Editar**.</span><span class="sxs-lookup"><span data-stu-id="a1646-160">Select the Group Policy Object you want to configure, and then choose **Edit**.</span></span>

4. <span data-ttu-id="a1646-161">En el **Editor de administración de directivas de** grupo, vaya a Configuración del equipo **y** seleccione **Plantillas administrativas.**</span><span class="sxs-lookup"><span data-stu-id="a1646-161">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

5. <span data-ttu-id="a1646-162">Expande el árbol a **Componentes de Windows** Antivirus de Microsoft  >  **Defender**.</span><span class="sxs-lookup"><span data-stu-id="a1646-162">Expand the tree to **Windows Components** > **Microsoft Defender Antivirus**.</span></span>

6. <span data-ttu-id="a1646-163">Haga doble clic en **Configurar la detección para aplicaciones potencialmente no deseadas.**</span><span class="sxs-lookup"><span data-stu-id="a1646-163">Double-click **Configure detection for potentially unwanted applications**.</span></span>

7. <span data-ttu-id="a1646-164">Seleccione **Habilitado para** habilitar la protección de LA PUA.</span><span class="sxs-lookup"><span data-stu-id="a1646-164">Select **Enabled** to enable PUA protection.</span></span>

8. <span data-ttu-id="a1646-165">En **Opciones,** seleccione **Bloquear para** bloquear aplicaciones potencialmente no deseadas o seleccione **Modo** de auditoría para probar el funcionamiento de la configuración en el entorno.</span><span class="sxs-lookup"><span data-stu-id="a1646-165">In **Options**, select **Block** to block potentially unwanted applications, or select **Audit Mode** to test how the setting works in your environment.</span></span> <span data-ttu-id="a1646-166">Elija **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a1646-166">Select **OK**.</span></span>

9. <span data-ttu-id="a1646-167">Implemente el objeto de directiva de grupo como suele hacer.</span><span class="sxs-lookup"><span data-stu-id="a1646-167">Deploy your Group Policy object as you usually do.</span></span>

#### <a name="use-powershell-cmdlets-to-configure-pua-protection"></a><span data-ttu-id="a1646-168">Usar cmdlets de PowerShell para configurar la protección de PUA</span><span class="sxs-lookup"><span data-stu-id="a1646-168">Use PowerShell cmdlets to configure PUA protection</span></span>

##### <a name="to-enable-pua-protection"></a><span data-ttu-id="a1646-169">Para habilitar la protección de PUA</span><span class="sxs-lookup"><span data-stu-id="a1646-169">To enable PUA protection</span></span>

```PowerShell
Set-MpPreference -PUAProtection Enabled
```

<span data-ttu-id="a1646-170">Establecer el valor de este cmdlet `Enabled` para que se activa la característica si se ha deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="a1646-170">Setting the value for this cmdlet to `Enabled` turns the feature on if it has been disabled.</span></span>

##### <a name="to-set-pua-protection-to-audit-mode"></a><span data-ttu-id="a1646-171">Para establecer la protección de LA PUA en modo auditoría</span><span class="sxs-lookup"><span data-stu-id="a1646-171">To set PUA protection to audit mode</span></span>

```PowerShell
Set-MpPreference -PUAProtection AuditMode
```

<span data-ttu-id="a1646-172">La `AuditMode` configuración detecta LAS PUA sin bloquearlas.</span><span class="sxs-lookup"><span data-stu-id="a1646-172">Setting `AuditMode` detects PUAs without blocking them.</span></span>

##### <a name="to-disable-pua-protection"></a><span data-ttu-id="a1646-173">Para deshabilitar la protección de PUA</span><span class="sxs-lookup"><span data-stu-id="a1646-173">To disable PUA protection</span></span>

<span data-ttu-id="a1646-174">Se recomienda mantener activada la protección de PUA.</span><span class="sxs-lookup"><span data-stu-id="a1646-174">We recommend keeping PUA protection turned on.</span></span> <span data-ttu-id="a1646-175">Sin embargo, puede desactivarlo con el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="a1646-175">However, you can turn it off by using the following cmdlet:</span></span>

```PowerShell
Set-MpPreference -PUAProtection Disabled
```

<span data-ttu-id="a1646-176">Establecer el valor de este cmdlet `Disabled` para desactivar la característica si se ha habilitado.</span><span class="sxs-lookup"><span data-stu-id="a1646-176">Setting the value for this cmdlet to `Disabled` turns the feature off if it has been enabled.</span></span>

<span data-ttu-id="a1646-177">Consulte [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and Defender [cmdlets](/powershell/module/defender/index) para obtener más información sobre cómo usar PowerShell con Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="a1646-177">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/index) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

## <a name="view-pua-events"></a><span data-ttu-id="a1646-178">Ver eventos pua</span><span class="sxs-lookup"><span data-stu-id="a1646-178">View PUA events</span></span>

<span data-ttu-id="a1646-179">Los eventos PUA se notifican en el Visor de eventos de Windows, pero no en Microsoft Endpoint Manager ni en Intune.</span><span class="sxs-lookup"><span data-stu-id="a1646-179">PUA events are reported in the Windows Event Viewer, but not in Microsoft Endpoint Manager or in Intune.</span></span> <span data-ttu-id="a1646-180">También puede usar el `Get-MpThreat` cmdlet para ver las amenazas que controló Antivirus de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="a1646-180">You can also use the `Get-MpThreat` cmdlet to view threats that Microsoft Defender Antivirus handled.</span></span> <span data-ttu-id="a1646-181">Aquí le mostramos un ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a1646-181">Here's an example:</span></span>

```console
CategoryID       : 27
DidThreatExecute : False
IsActive         : False
Resources        : {webfile:_q:\Builds\Dalton_Download_Manager_3223905758.exe|http://d18yzm5yb8map8.cloudfront.net/
                    fo4yue@kxqdw/Dalton_Download_Manager.exe|pid:14196,ProcessStart:132378130057195714}
RollupStatus     : 33
SchemaVersion    : 1.0.0.0
SeverityID       : 1
ThreatID         : 213927
ThreatName       : PUA:Win32/InstallCore
TypeID           : 0
PSComputerName   :
```

<span data-ttu-id="a1646-182">Puedes activar las notificaciones de correo electrónico para recibir correo sobre detecciones de PUA.</span><span class="sxs-lookup"><span data-stu-id="a1646-182">You can turn on email notifications to receive mail about PUA detections.</span></span>

<span data-ttu-id="a1646-183">Consulta [Solucionar problemas de los IDs de eventos](troubleshoot-microsoft-defender-antivirus.md) para obtener más información sobre cómo ver los eventos del Antivirus de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="a1646-183">See [Troubleshoot event IDs](troubleshoot-microsoft-defender-antivirus.md) for details on viewing Microsoft Defender Antivirus events.</span></span> <span data-ttu-id="a1646-184">Los eventos PUA se registran con el identificador **de evento 1160**.</span><span class="sxs-lookup"><span data-stu-id="a1646-184">PUA events are recorded under event ID **1160**.</span></span>

## <a name="excluding-files"></a><span data-ttu-id="a1646-185">Excluir archivos</span><span class="sxs-lookup"><span data-stu-id="a1646-185">Excluding files</span></span>

<span data-ttu-id="a1646-186">A veces, la protección de PUA bloquea erróneamente un archivo o se requiere una característica de una PUA para completar una tarea.</span><span class="sxs-lookup"><span data-stu-id="a1646-186">Sometimes a file is erroneously blocked by PUA protection, or a feature of a PUA is required to complete a task.</span></span> <span data-ttu-id="a1646-187">En estos casos, se puede agregar un archivo a una lista de exclusión.</span><span class="sxs-lookup"><span data-stu-id="a1646-187">In these cases, a file can be added to an exclusion list.</span></span>

<span data-ttu-id="a1646-188">Para obtener más información, vea [Configure and validate exclusions based on file extension and folder location](configure-extension-file-exclusions-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="a1646-188">For more information, see [Configure and validate exclusions based on file extension and folder location](configure-extension-file-exclusions-microsoft-defender-antivirus.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a1646-189">Vea también</span><span class="sxs-lookup"><span data-stu-id="a1646-189">See also</span></span>

- [<span data-ttu-id="a1646-190">Protección de última generación</span><span class="sxs-lookup"><span data-stu-id="a1646-190">Next-generation protection</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="a1646-191">Configurar la protección de comportamiento, heurística y en tiempo real</span><span class="sxs-lookup"><span data-stu-id="a1646-191">Configure behavioral, heuristic, and real-time protection</span></span>](configure-protection-features-microsoft-defender-antivirus.md)