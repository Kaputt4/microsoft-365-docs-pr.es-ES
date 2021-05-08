---
title: Bloquear aplicaciones potencialmente no deseadas con Antivirus de Microsoft Defender
description: Habilite la característica antivirus de aplicaciones potencialmente no deseadas (PUA) para bloquear software no deseado como, por ejemplo, adware.
keywords: pua, habilitar, software no deseado, aplicaciones no deseadas, barra de herramientas del explorador, detectar, bloquear, Antivirus de Microsoft Defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: detect
ms.sitesec: library
localization_priority: Priority
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
audience: ITPro
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: fbd897b025db2317dd1c213e5adf5d64ba88e7ac
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275245"
---
# <a name="detect-and-block-potentially-unwanted-applications"></a><span data-ttu-id="9134c-104">Detectar y bloquear aplicaciones potencialmente no deseadas</span><span class="sxs-lookup"><span data-stu-id="9134c-104">Detect and block potentially unwanted applications</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="9134c-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="9134c-105">**Applies to:**</span></span>

- [<span data-ttu-id="9134c-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="9134c-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- [<span data-ttu-id="9134c-107">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="9134c-107">Microsoft Edge</span></span>](/microsoft-edge/deploy/microsoft-edge)

<span data-ttu-id="9134c-108">Las aplicaciones potencialmente no deseadas (PUA) son una categoría de software que puede hacer que su equipo funcione lentamente, muestre anuncios inesperados o, en el peor de los casos, instale otro software que pueda ser inesperado o no deseado.</span><span class="sxs-lookup"><span data-stu-id="9134c-108">Potentially unwanted applications (PUA) are a category of software that can cause your machine to run slowly, display unexpected ads, or at worst, install other software that might be unexpected or unwanted.</span></span> <span data-ttu-id="9134c-109">PUA no se considera un virus, malware u otro tipo de amenaza, pero puede realizar acciones en los puntos de conexión que afecten negativamente al rendimiento o al uso de los puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="9134c-109">PUA is not considered a virus, malware, or other type of threat, but it might perform actions on endpoints that adversely affect endpoint performance or use.</span></span> <span data-ttu-id="9134c-110">El término *PUA* también puede hacer referencia a una aplicación que tenga mala reputación, según la evaluación de Microsoft Defender para punto de conexión, debido a determinados tipos de comportamiento no deseado.</span><span class="sxs-lookup"><span data-stu-id="9134c-110">The term *PUA* can also refer to an application that has a poor reputation, as assessed by Microsoft Defender for Endpoint, due to certain kinds of undesirable behavior.</span></span>

<span data-ttu-id="9134c-111">Estos son algunos ejemplos:</span><span class="sxs-lookup"><span data-stu-id="9134c-111">Here are some examples:</span></span>

- <span data-ttu-id="9134c-112">**Software de publicidad**, que muestra anuncios o promociones, incluido software que inserta anuncios en páginas web.</span><span class="sxs-lookup"><span data-stu-id="9134c-112">**Advertising software** that displays advertisements or promotions, including software that inserts advertisements to webpages.</span></span>
- <span data-ttu-id="9134c-113">**Software de agrupación**, que ofrece instalar otro software que no está firmado digitalmente por la misma entidad.</span><span class="sxs-lookup"><span data-stu-id="9134c-113">**Bundling software** that offers to install other software that is not digitally signed by the same entity.</span></span> <span data-ttu-id="9134c-114">Además, existe software que ofrece instalar otro software que se considera PUA.</span><span class="sxs-lookup"><span data-stu-id="9134c-114">Also, software that offers to install other software that qualifies as PUA.</span></span>
- <span data-ttu-id="9134c-115">**Software de evasión**, que intenta evitar activamente que los productos de seguridad lo detecten, incluido software que se comporta de forma diferente en presencia de productos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="9134c-115">**Evasion software** that actively tries to evade detection by security products, including software that behaves differently in the presence of security products.</span></span>

> [!TIP]
> <span data-ttu-id="9134c-116">Para obtener más ejemplos y una explicación de los criterios que usamos para etiquetar aplicaciones para que las características de seguridad les presten especial atención, consulte [Cómo identifica Microsoft el malware y las aplicaciones potencialmente no deseadas](/windows/security/threat-protection/intelligence/criteria).</span><span class="sxs-lookup"><span data-stu-id="9134c-116">For more examples and a discussion of the criteria we use to label applications for special attention from security features, see [How Microsoft identifies malware and potentially unwanted applications](/windows/security/threat-protection/intelligence/criteria).</span></span>

<span data-ttu-id="9134c-117">Las aplicaciones potencialmente no deseadas pueden aumentar el riesgo de que su red se infecte con malware real, puede hacer que sea más difícil identificar infecciones de malware o que se pierdan recursos de TI al limpiar las infecciones.</span><span class="sxs-lookup"><span data-stu-id="9134c-117">Potentially unwanted applications can increase the risk of your network being infected with actual malware, make malware infections harder to identify, or waste IT resources in cleaning them up.</span></span> <span data-ttu-id="9134c-118">La protección contra PUA es compatible con Windows 10, Windows Server 2019 y Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="9134c-118">PUA protection is supported on Windows 10, Windows Server 2019, and Windows Server 2016.</span></span> <span data-ttu-id="9134c-119">En Windows 10 (versión 2004 y posteriores), Antivirus de Microsoft Defender bloquea las aplicaciones que se consideran PUA para dispositivos Enterprise (E5) de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="9134c-119">In Windows 10 (version 2004 and later), Microsoft Defender Antivirus blocks apps that are considered PUA for Enterprise (E5) devices by default.</span></span>

## <a name="microsoft-edge"></a><span data-ttu-id="9134c-120">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="9134c-120">Microsoft Edge</span></span>

<span data-ttu-id="9134c-121">El nuevo [Microsoft Edge](https://support.microsoft.com/microsoft-edge/get-to-know-microsoft-edge-3f4bb0ff-58de-2188-55c0-f560b7e20bea), basado Chromium, bloquea las descargas de aplicaciones potencialmente no deseadas y las direcciones URL de recursos asociados.</span><span class="sxs-lookup"><span data-stu-id="9134c-121">The [new Microsoft Edge](https://support.microsoft.com/microsoft-edge/get-to-know-microsoft-edge-3f4bb0ff-58de-2188-55c0-f560b7e20bea), which is Chromium-based, blocks potentially unwanted application downloads and associated resource URLs.</span></span> <span data-ttu-id="9134c-122">Esta característica se ofrece a través de [SmartScreen de Microsoft Defender](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview).</span><span class="sxs-lookup"><span data-stu-id="9134c-122">This feature is provided via [Microsoft Defender SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview).</span></span>

### <a name="enable-pua-protection-in-chromium-based-microsoft-edge"></a><span data-ttu-id="9134c-123">Habilitar la protección de PUA en Microsoft Edge basado en Chromium</span><span class="sxs-lookup"><span data-stu-id="9134c-123">Enable PUA protection in Chromium-based Microsoft Edge</span></span>

<span data-ttu-id="9134c-124">Si bien la protección de aplicaciones potencialmente no deseadas en Microsoft Edge (basada en Chromium, versión 80.0.361.50) está desactivada de manera predeterminada, se puede activar fácilmente desde el explorador.</span><span class="sxs-lookup"><span data-stu-id="9134c-124">Although potentially unwanted application protection in Microsoft Edge (Chromium-based, version 80.0.361.50) is turned off by default, it can easily be turned on from within the browser.</span></span>

1. <span data-ttu-id="9134c-125">En el explorador Edge, seleccione los puntos suspensivos y, después, elija **Configuración**.</span><span class="sxs-lookup"><span data-stu-id="9134c-125">In your Edge browser, select the ellipses, and then choose **Settings**.</span></span>

2. <span data-ttu-id="9134c-126">Seleccione **Privacidad, búsqueda y servicios**.</span><span class="sxs-lookup"><span data-stu-id="9134c-126">Select **Privacy, search, and services**.</span></span>

3. <span data-ttu-id="9134c-127">En la sección **Seguridad**, active **Bloquear aplicaciones potencialmente no deseadas**.</span><span class="sxs-lookup"><span data-stu-id="9134c-127">Under the **Security** section, turn on **Block potentially unwanted apps**.</span></span>

> [!TIP]
> <span data-ttu-id="9134c-128">Si ejecuta Microsoft Edge (basado en Chromium), puede explorar de forma segura la característica de bloqueo de direcciones URL de la protección contra PUA. Puede probarla en una de nuestras [Páginas de demostración de SmartScreen de Microsoft Defender](https://demo.smartscreen.msft.net/).</span><span class="sxs-lookup"><span data-stu-id="9134c-128">If you are running Microsoft Edge (Chromium-based), you can safely explore the URL-blocking feature of PUA protection by testing it out on one of our [Microsoft Defender SmartScreen demo pages](https://demo.smartscreen.msft.net/).</span></span>

### <a name="block-urls-with-microsoft-defender-smartscreen"></a><span data-ttu-id="9134c-129">Bloquear direcciones URL con SmartScreen de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="9134c-129">Block URLs with Microsoft Defender SmartScreen</span></span>

<span data-ttu-id="9134c-130">En Edge basado en Chromium con la protección activada contra PUA, SmartScreen de Microsoft Defender le protege de direcciones URL asociadas a PUA.</span><span class="sxs-lookup"><span data-stu-id="9134c-130">In Chromium-based Edge with PUA protection turned on, Microsoft Defender SmartScreen protects you from PUA-associated URLs.</span></span>

<span data-ttu-id="9134c-131">Los administradores de seguridad pueden [configurar](/DeployEdge/configure-microsoft-edge) la manera en la que Microsoft Edge y SmartScreen de Microsoft Defender trabajan juntos para proteger a grupos de usuarios frente a direcciones URL asociadas a PUA.</span><span class="sxs-lookup"><span data-stu-id="9134c-131">Security admins can [configure](/DeployEdge/configure-microsoft-edge) how Microsoft Edge and Microsoft Defender SmartScreen work together to protect groups of users from PUA-associated URLs.</span></span> <span data-ttu-id="9134c-132">Hay disponibles varias opciones de [configuración de directiva de grupo](/DeployEdge/microsoft-edge-policies#smartscreen-settings) expresamente para SmartScreen de Microsoft Defender, incluida una [configuración para bloquear PUA](/DeployEdge/microsoft-edge-policies#smartscreenpuaenabled).</span><span class="sxs-lookup"><span data-stu-id="9134c-132">There are several [group policy settings](/DeployEdge/microsoft-edge-policies#smartscreen-settings) explicitly for Microsoft Defender SmartScreen available, including [one for blocking PUA](/DeployEdge/microsoft-edge-policies#smartscreenpuaenabled).</span></span> <span data-ttu-id="9134c-133">Además, los administradores pueden [configurar SmartScreen de Microsoft Defender](/microsoft-edge/deploy/available-policies?source=docs#configure-windows-defender-smartscreen) en general, con la configuración de directiva de grupo para activar o desactivar SmartScreen de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="9134c-133">In addition, admins can [configure Microsoft Defender SmartScreen](/microsoft-edge/deploy/available-policies?source=docs#configure-windows-defender-smartscreen) as a whole, using group policy settings to turn Microsoft Defender SmartScreen on or off.</span></span>

<span data-ttu-id="9134c-134">Aunque Microsoft Defender para punto de conexión tiene su propia lista de bloqueo basada en un conjunto de datos administrado por Microsoft, puede personalizar esta lista según su propia inteligencia sobre amenazas.</span><span class="sxs-lookup"><span data-stu-id="9134c-134">Although Microsoft Defender for Endpoint has its own blocklist based upon a data set managed by Microsoft, you can customize this list based on your own threat intelligence.</span></span> <span data-ttu-id="9134c-135">Si [crea y administra indicadores](manage-indicators.md) en el portal de Microsoft Defender para punto de conexión, SmartScreen de Microsoft Defender respetará la nueva configuración.</span><span class="sxs-lookup"><span data-stu-id="9134c-135">If you [create and manage indicators](manage-indicators.md) in the Microsoft Defender for Endpoint portal, Microsoft Defender SmartScreen respects the new settings.</span></span>

## <a name="microsoft-defender-antivirus-and-pua-protection"></a><span data-ttu-id="9134c-136">Antivirus de Microsoft Defender y protección contra PUA</span><span class="sxs-lookup"><span data-stu-id="9134c-136">Microsoft Defender Antivirus and PUA protection</span></span>

<span data-ttu-id="9134c-137">La característica de protección contra aplicaciones potencialmente no deseadas (PUA) de Antivirus de Microsoft Defender puede detectar y bloquear PUA en los puntos de conexión de su red.</span><span class="sxs-lookup"><span data-stu-id="9134c-137">The potentially unwanted application (PUA) protection feature in Microsoft Defender Antivirus can detect and block PUA on endpoints in your network.</span></span>

> [!NOTE]
> <span data-ttu-id="9134c-138">Esta característica está disponible en Windows 10, Windows Server 2019 y Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="9134c-138">This feature is available in Windows 10, Windows Server 2019, and Windows Server 2016.</span></span>

<span data-ttu-id="9134c-139">Antivirus de Microsoft Defender bloquea los archivos PUA que se detecten y cualquier intento de descargarlos, moverlos, ejecutarlos o instalarlos.</span><span class="sxs-lookup"><span data-stu-id="9134c-139">Microsoft Defender Antivirus blocks detected PUA files and any attempts to download, move, run, or install them.</span></span> <span data-ttu-id="9134c-140">A continuación, los archivos PUA bloqueados se ponen en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="9134c-140">Blocked PUA files are then moved to quarantine.</span></span> <span data-ttu-id="9134c-141">Cuando se detecta un archivo PUA en un punto de conexión, Antivirus de Microsoft Defender envía una notificación al usuario ([a menos que se hayan deshabilitado las notificaciones](configure-notifications-microsoft-defender-antivirus.md)) en el mismo formato de otras detecciones de amenazas.</span><span class="sxs-lookup"><span data-stu-id="9134c-141">When a PUA file is detected on an endpoint, Microsoft Defender Antivirus sends a notification to the user ([unless notifications have been disabled](configure-notifications-microsoft-defender-antivirus.md)) in the same format as other threat detections.</span></span> <span data-ttu-id="9134c-142">A la notificación se antepone `PUA:` para indicar su contenido.</span><span class="sxs-lookup"><span data-stu-id="9134c-142">The notification is prefaced with `PUA:` to indicate its content.</span></span>

<span data-ttu-id="9134c-143">La notificación aparece en la [lista habitual de cuarentena dentro de la aplicación de Seguridad de Windows](microsoft-defender-security-center-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="9134c-143">The notification appears in the usual [quarantine list within the Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span>

## <a name="configure-pua-protection-in-microsoft-defender-antivirus"></a><span data-ttu-id="9134c-144">Configurar la protección contra PUA en Antivirus de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="9134c-144">Configure PUA protection in Microsoft Defender Antivirus</span></span>

<span data-ttu-id="9134c-145">Puede habilitar la protección contra PUA con [Microsoft Intune](/mem/intune/protect/device-protect), [Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection), [Directiva de grupo](/azure/active-directory-domain-services/manage-group-policy) o mediante [cmdlets de PowerShell](/powershell/module/defender/?preserve-view=true&view=win10-ps).</span><span class="sxs-lookup"><span data-stu-id="9134c-145">You can enable PUA protection with [Microsoft Intune](/mem/intune/protect/device-protect), [Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection), [Group Policy](/azure/active-directory-domain-services/manage-group-policy), or via [PowerShell cmdlets](/powershell/module/defender/?preserve-view=true&view=win10-ps).</span></span>

<span data-ttu-id="9134c-146">También puede usar la protección contra PUA en modo de auditoría para detectar aplicaciones potencialmente no deseadas sin bloquearlas.</span><span class="sxs-lookup"><span data-stu-id="9134c-146">You can also use PUA protection in audit mode to detect potentially unwanted applications without blocking them.</span></span> <span data-ttu-id="9134c-147">Las detecciones se capturan en el registro de eventos de Windows.</span><span class="sxs-lookup"><span data-stu-id="9134c-147">The detections are captured in the Windows event log.</span></span>

> [!TIP]
> <span data-ttu-id="9134c-148">Visite el sitio web de demostración de Microsoft Defender para punto de conexión en [demo.wd.microsoft.com](https://demo.wd.microsoft.com/Page/UrlRep) para confirmar que la característica funciona y verla en acción.</span><span class="sxs-lookup"><span data-stu-id="9134c-148">Visit the Microsoft Defender for Endpoint demo website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com/Page/UrlRep) to confirm that the feature is working, and see it in action.</span></span>

<span data-ttu-id="9134c-149">La protección contra PUA en el modo de auditoría es útil si su empresa está realizando una comprobación interna de cumplimiento de seguridad de software y quiere evitar falsos positivos.</span><span class="sxs-lookup"><span data-stu-id="9134c-149">PUA protection in audit mode is useful if your company is conducting an internal software security compliance check and you'd like to avoid any false positives.</span></span>

### <a name="use-intune-to-configure-pua-protection"></a><span data-ttu-id="9134c-150">Usar Intune para configurar la protección contra PUA</span><span class="sxs-lookup"><span data-stu-id="9134c-150">Use Intune to configure PUA protection</span></span>

<span data-ttu-id="9134c-151">Consulte [Configurar la configuración de restricciones de dispositivo en Microsoft Intune](/intune/device-restrictions-configure) y la [Configuración de restricciones de dispositivo de Antivirus de Microsoft Defender para Windows 10 en Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus) para más información.</span><span class="sxs-lookup"><span data-stu-id="9134c-151">See [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure) and [Microsoft Defender Antivirus device restriction settings for Windows 10 in Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus) for more details.</span></span>

### <a name="use-configuration-manager-to-configure-pua-protection"></a><span data-ttu-id="9134c-152">Usar Configuration Manager para configurar la protección contra PUA</span><span class="sxs-lookup"><span data-stu-id="9134c-152">Use Configuration Manager to configure PUA protection</span></span>

<span data-ttu-id="9134c-153">La protección contra PUA está habilitada de forma predeterminada en Microsoft Endpoint Manager (rama actual).</span><span class="sxs-lookup"><span data-stu-id="9134c-153">PUA protection is enabled by default in the Microsoft Endpoint Manager (Current Branch).</span></span>

<span data-ttu-id="9134c-154">Consulte [Información sobre cómo crear e implementar directivas de antimalware: configuración de análisis programados](/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings) para obtener más información sobre cómo configurar Microsoft Endpoint Manager (rama actual).</span><span class="sxs-lookup"><span data-stu-id="9134c-154">See [How to create and deploy antimalware policies: Scheduled scans settings](/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings) for details on configuring Microsoft Endpoint Manager (Current Branch).</span></span>

<span data-ttu-id="9134c-155">Para System Center 2012 Configuration Manager, consulte [Cómo implementar una directiva de protección de aplicaciones potencialmente no deseadas para Endpoint Protection en Configuration Manager](/previous-versions/system-center/system-center-2012-R2/hh508770(v=technet.10)#BKMK_PUA).</span><span class="sxs-lookup"><span data-stu-id="9134c-155">For System Center 2012 Configuration Manager, see [How to Deploy Potentially Unwanted Application Protection Policy for Endpoint Protection in Configuration Manager](/previous-versions/system-center/system-center-2012-R2/hh508770(v=technet.10)#BKMK_PUA).</span></span>

> [!NOTE]
> <span data-ttu-id="9134c-156">Los eventos de PUA bloqueados por Antivirus de Microsoft Defender se notifican en el Visor de eventos de Windows, en lugar de en Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="9134c-156">PUA events blocked by Microsoft Defender Antivirus are reported in the Windows Event Viewer and not in Microsoft Endpoint Configuration Manager.</span></span>

### <a name="use-group-policy-to-configure-pua-protection"></a><span data-ttu-id="9134c-157">Usar una directiva de grupo para configurar la protección contra PUA</span><span class="sxs-lookup"><span data-stu-id="9134c-157">Use Group Policy to configure PUA protection</span></span>

1. <span data-ttu-id="9134c-158">Descargue e instale [Plantillas administrativas (.admx) para la actualización de octubre de 2020 de Windows 10 (20H2)](https://www.microsoft.com/download/details.aspx?id=102157)</span><span class="sxs-lookup"><span data-stu-id="9134c-158">Download and install [Administrative Templates (.admx) for Windows 10 October 2020 Update (20H2)](https://www.microsoft.com/download/details.aspx?id=102157)</span></span>

2. <span data-ttu-id="9134c-159">En el equipo de administración de directivas de grupo, abra la [Consola de administración de directivas de grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span><span class="sxs-lookup"><span data-stu-id="9134c-159">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

3. <span data-ttu-id="9134c-160">Seleccione el objeto de directiva de grupo que quiera configurar y, después, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="9134c-160">Select the Group Policy Object you want to configure, and then choose **Edit**.</span></span>

4. <span data-ttu-id="9134c-161">En el **Editor de administración de directiva de grupo**, vaya a **Configuración del equipo** y seleccione **Plantillas administrativas**.</span><span class="sxs-lookup"><span data-stu-id="9134c-161">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

5. <span data-ttu-id="9134c-162">Expanda el árbol en **Componentes de Windows** > **Antivirus de Microsoft Defender**.</span><span class="sxs-lookup"><span data-stu-id="9134c-162">Expand the tree to **Windows Components** > **Microsoft Defender Antivirus**.</span></span>

6. <span data-ttu-id="9134c-163">Haga doble clic en **Configurar la detección de aplicaciones potencialmente no deseadas**.</span><span class="sxs-lookup"><span data-stu-id="9134c-163">Double-click **Configure detection for potentially unwanted applications**.</span></span>

7. <span data-ttu-id="9134c-164">Seleccione **Habilitado** para habilitar la protección contra PUA.</span><span class="sxs-lookup"><span data-stu-id="9134c-164">Select **Enabled** to enable PUA protection.</span></span>

8. <span data-ttu-id="9134c-165">En **Opciones**, seleccione **Bloquear** para bloquear aplicaciones potencialmente no deseadas o seleccione **Modo de auditoría** para probar cómo funciona la configuración en su entorno.</span><span class="sxs-lookup"><span data-stu-id="9134c-165">In **Options**, select **Block** to block potentially unwanted applications, or select **Audit Mode** to test how the setting works in your environment.</span></span> <span data-ttu-id="9134c-166">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9134c-166">Select **OK**.</span></span>

9. <span data-ttu-id="9134c-167">Implemente el objeto de directiva de grupo como lo haría normalmente.</span><span class="sxs-lookup"><span data-stu-id="9134c-167">Deploy your Group Policy object as you usually do.</span></span>

### <a name="use-powershell-cmdlets-to-configure-pua-protection"></a><span data-ttu-id="9134c-168">Usar cmdlets de PowerShell para configurar la protección contra PUA</span><span class="sxs-lookup"><span data-stu-id="9134c-168">Use PowerShell cmdlets to configure PUA protection</span></span>

#### <a name="to-enable-pua-protection"></a><span data-ttu-id="9134c-169">Para habilitar la protección contra PUA</span><span class="sxs-lookup"><span data-stu-id="9134c-169">To enable PUA protection</span></span>

```PowerShell
Set-MpPreference -PUAProtection Enabled
```

<span data-ttu-id="9134c-170">Al establecer el valor de este cmdlet en `Enabled`, se activa la característica si se había deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="9134c-170">Setting the value for this cmdlet to `Enabled` turns on the feature if it has been disabled.</span></span>

#### <a name="to-set-pua-protection-to-audit-mode"></a><span data-ttu-id="9134c-171">Para configurar la protección contra PUA en modo de auditoría</span><span class="sxs-lookup"><span data-stu-id="9134c-171">To set PUA protection to audit mode</span></span>

```PowerShell
Set-MpPreference -PUAProtection AuditMode
```

<span data-ttu-id="9134c-172">Al establecer `AuditMode` se detectan las PUA sin bloquearlas.</span><span class="sxs-lookup"><span data-stu-id="9134c-172">Setting `AuditMode` detects PUAs without blocking them.</span></span>

#### <a name="to-disable-pua-protection"></a><span data-ttu-id="9134c-173">Para deshabilitar la protección contra PUA</span><span class="sxs-lookup"><span data-stu-id="9134c-173">To disable PUA protection</span></span>

<span data-ttu-id="9134c-174">Se recomienda mantener activada la protección contra PUA.</span><span class="sxs-lookup"><span data-stu-id="9134c-174">We recommend keeping PUA protection turned on.</span></span> <span data-ttu-id="9134c-175">Sin embargo, puede desactivarla con el cmdlet siguiente:</span><span class="sxs-lookup"><span data-stu-id="9134c-175">However, you can turn it off by using the following cmdlet:</span></span>

```PowerShell
Set-MpPreference -PUAProtection Disabled
```

<span data-ttu-id="9134c-176">Al establecer el valor de este cmdlet en `Disabled`, se desactiva la característica si se había habilitado.</span><span class="sxs-lookup"><span data-stu-id="9134c-176">Setting the value for this cmdlet to `Disabled` turns off the feature if it has been enabled.</span></span>

<span data-ttu-id="9134c-177">Para más información, consulte [Usar cmdlets de PowerShell para configurar y ejecutar Antivirus de Microsoft Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md) y [cmdlets de Defender](/powershell/module/defender/index).</span><span class="sxs-lookup"><span data-stu-id="9134c-177">For more information, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/index).</span></span>

## <a name="view-pua-events-using-powershell"></a><span data-ttu-id="9134c-178">Ver eventos de PUA con PowerShell</span><span class="sxs-lookup"><span data-stu-id="9134c-178">View PUA events using PowerShell</span></span>

<span data-ttu-id="9134c-179">Los eventos de PUA se notifican en el Visor de eventos de Windows, en lugar de en Microsoft Endpoint Manager o Intune.</span><span class="sxs-lookup"><span data-stu-id="9134c-179">PUA events are reported in the Windows Event Viewer, but not in Microsoft Endpoint Manager or in Intune.</span></span> <span data-ttu-id="9134c-180">Asimismo, puede usar el cmdlet `Get-MpThreat` para ver las amenazas que Antivirus de Microsoft Defender ha administrado.</span><span class="sxs-lookup"><span data-stu-id="9134c-180">You can also use the `Get-MpThreat` cmdlet to view threats that Microsoft Defender Antivirus handled.</span></span> <span data-ttu-id="9134c-181">Aquí le mostramos un ejemplo:</span><span class="sxs-lookup"><span data-stu-id="9134c-181">Here's an example:</span></span>

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

## <a name="get-email-notifications-about-pua-detections"></a><span data-ttu-id="9134c-182">Obtener notificaciones de correo electrónico sobre las detecciones de PUA</span><span class="sxs-lookup"><span data-stu-id="9134c-182">Get email notifications about PUA detections</span></span>

<span data-ttu-id="9134c-183">Puede activar las notificaciones de correo electrónico para recibir un correo electrónico sobre las detecciones de PUA.</span><span class="sxs-lookup"><span data-stu-id="9134c-183">You can turn on email notifications to receive mail about PUA detections.</span></span>

<span data-ttu-id="9134c-184">Consulte [Solucionar id. de evento](troubleshoot-microsoft-defender-antivirus.md) para obtener más información sobre cómo ver los eventos de Antivirus de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="9134c-184">See [Troubleshoot event IDs](troubleshoot-microsoft-defender-antivirus.md) for details on viewing Microsoft Defender Antivirus events.</span></span> <span data-ttu-id="9134c-185">Los eventos de PUA se registran en el id. de evento **1160**.</span><span class="sxs-lookup"><span data-stu-id="9134c-185">PUA events are recorded under event ID **1160**.</span></span>

## <a name="view-pua-events-using-advanced-hunting"></a><span data-ttu-id="9134c-186">Ver eventos de PUA con la búsqueda avanzada de amenazas</span><span class="sxs-lookup"><span data-stu-id="9134c-186">View PUA events using advanced hunting</span></span>

<span data-ttu-id="9134c-187">Si usa [Microsoft Defender para punto de conexión](microsoft-defender-endpoint.md), puede usar una consulta de búsqueda avanzada de amenazas para ver eventos de PUA.</span><span class="sxs-lookup"><span data-stu-id="9134c-187">If you're using [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md), you can use an advanced hunting query to view PUA events.</span></span> <span data-ttu-id="9134c-188">Esta es una consulta de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="9134c-188">Here's an example query:</span></span>

```console
DeviceEvents
| where ActionType == "AntivirusDetection"
| extend x = parse_json(AdditionalFields)
| evaluate bag_unpack(x)
| where ThreatName startswith_cs 'PUA:'
| project Timestamp, DeviceName, FolderPath, FileName, SHA256, ThreatName, WasExecutingWhileDetected, WasRemediated
```

<span data-ttu-id="9134c-189">Para más información sobre la búsqueda avanzada de amenazas, consulte [Buscar amenazas de forma proactiva con la búsqueda avanzada de amenazas](advanced-hunting-overview.md).</span><span class="sxs-lookup"><span data-stu-id="9134c-189">To learn more about advanced hunting, see [Proactively hunt for threats with advanced hunting](advanced-hunting-overview.md).</span></span>

## <a name="exclude-files-from-pua-protection"></a><span data-ttu-id="9134c-190">Excluir archivos de la protección contra PUA</span><span class="sxs-lookup"><span data-stu-id="9134c-190">Exclude files from PUA protection</span></span>

<span data-ttu-id="9134c-191">A veces, la protección contra PUA bloquea un archivo por error, o se requiere una característica de una PUA para completar una tarea.</span><span class="sxs-lookup"><span data-stu-id="9134c-191">Sometimes a file is erroneously blocked by PUA protection, or a feature of a PUA is required to complete a task.</span></span> <span data-ttu-id="9134c-192">En estos casos, se puede agregar un archivo a una lista de exclusiones.</span><span class="sxs-lookup"><span data-stu-id="9134c-192">In these cases, a file can be added to an exclusion list.</span></span>

<span data-ttu-id="9134c-193">Para más información, consulte [Configurar y validar exclusiones según la extensión de archivo y la ubicación de carpeta](configure-extension-file-exclusions-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="9134c-193">For more information, see [Configure and validate exclusions based on file extension and folder location](configure-extension-file-exclusions-microsoft-defender-antivirus.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="9134c-194">Vea también</span><span class="sxs-lookup"><span data-stu-id="9134c-194">See also</span></span>

- [<span data-ttu-id="9134c-195">Protección de última generación</span><span class="sxs-lookup"><span data-stu-id="9134c-195">Next-generation protection</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="9134c-196">Configurar la protección en tiempo real, heurística y de comportamiento</span><span class="sxs-lookup"><span data-stu-id="9134c-196">Configure behavioral, heuristic, and real-time protection</span></span>](configure-protection-features-microsoft-defender-antivirus.md)