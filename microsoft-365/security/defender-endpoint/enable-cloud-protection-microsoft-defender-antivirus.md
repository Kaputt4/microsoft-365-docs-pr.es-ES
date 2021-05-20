---
title: Active la protección suministrada por la nube en Antivirus de Microsoft Defender
description: Active la protección entregada en la nube para beneficiarse de funciones de protección rápidas y avanzadas.
keywords: Antivirus de Microsoft Defender, antimalware, seguridad, nube, bloque a primera vista
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.date: 05/18/2021
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 8c45fb4b60e3c20c2001cc0008ecc8154e854273
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572062"
---
# <a name="turn-on-cloud-delivered-protection"></a><span data-ttu-id="3bbe4-104">Activar la protección proporcionada en la nube</span><span class="sxs-lookup"><span data-stu-id="3bbe4-104">Turn on cloud-delivered protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3bbe4-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="3bbe4-105">**Applies to:**</span></span>

- [<span data-ttu-id="3bbe4-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="3bbe4-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

> [!NOTE]
> <span data-ttu-id="3bbe4-107">El servicio en la nube Antivirus de Microsoft Defender es un mecanismo para ofrecer protección actualizada a la red y los puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="3bbe4-107">The Microsoft Defender Antivirus cloud service is a mechanism for delivering updated protection to your network and endpoints.</span></span> <span data-ttu-id="3bbe4-108">Aunque se denomina servicio en la nube, no es simplemente protección para los archivos almacenados en la nube; más bien, utiliza recursos distribuidos y aprendizaje automático para ofrecer protección a sus puntos de conexión a un ritmo mucho más rápido que las actualizaciones de inteligencia de seguridad tradicionales.</span><span class="sxs-lookup"><span data-stu-id="3bbe4-108">Although it is called a cloud service, it is not simply protection for files stored in the cloud; rather, it uses distributed resources and machine learning to deliver protection to your endpoints at a rate that is far faster than traditional Security intelligence updates.</span></span>

<span data-ttu-id="3bbe4-109">Antivirus de Microsoft Defender utiliza múltiples tecnologías de detección y prevención para ofrecer una protección precisa, en tiempo real e inteligente.</span><span class="sxs-lookup"><span data-stu-id="3bbe4-109">Microsoft Defender Antivirus uses multiple detection and prevention technologies to deliver accurate, real-time, and intelligent protection.</span></span> <span data-ttu-id="3bbe4-110">[Conozca las tecnologías avanzadas en el núcleo de la protección de próxima generación de Microsoft Defender for Endpoint.](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)</span><span class="sxs-lookup"><span data-stu-id="3bbe4-110">[Get to know the advanced technologies at the core of Microsoft Defender for Endpoint next-generation protection](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/).</span></span>

<span data-ttu-id="3bbe4-111">Puede activar o desactivar Antivirus de Microsoft Defender protección entregada en la nube de varias maneras:</span><span class="sxs-lookup"><span data-stu-id="3bbe4-111">You can turn Microsoft Defender Antivirus cloud-delivered protection on or off in several ways:</span></span>

- <span data-ttu-id="3bbe4-112">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="3bbe4-112">Microsoft Intune</span></span>
- <span data-ttu-id="3bbe4-113">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="3bbe4-113">Microsoft Endpoint Manager</span></span>
- <span data-ttu-id="3bbe4-114">Directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="3bbe4-114">Group Policy</span></span>
- <span data-ttu-id="3bbe4-115">Cmdlets de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3bbe4-115">PowerShell cmdlets.</span></span>

 <span data-ttu-id="3bbe4-116">También puede activarlo o desactivarlo en clientes individuales con la aplicación Seguridad de Windows.</span><span class="sxs-lookup"><span data-stu-id="3bbe4-116">You can also turn it on or off in individual clients with the Windows Security app.</span></span>

<span data-ttu-id="3bbe4-117">Consulte [Usar la protección entregada en la nube por Microsoft](cloud-protection-microsoft-defender-antivirus.md) para obtener información general sobre Antivirus de Microsoft Defender protección entregada en la nube.</span><span class="sxs-lookup"><span data-stu-id="3bbe4-117">See [Use Microsoft cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) for an overview of Microsoft Defender Antivirus cloud-delivered protection.</span></span>

<span data-ttu-id="3bbe4-118">Para obtener más información acerca de los requisitos específicos de conectividad de red para garantizar que los puntos de conexión pueden conectarse al servicio de protección entregado en la nube, consulte [Configurar y validar conexiones de red.](configure-network-connections-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="3bbe4-118">For more information about the specific network-connectivity requirements to ensure your endpoints can connect to the cloud-delivered protection service, see [Configure and validate network connections](configure-network-connections-microsoft-defender-antivirus.md).</span></span>

> [!NOTE]
> <span data-ttu-id="3bbe4-119">En Windows 10, no hay diferencia entre las opciones de informes **básico** y **avanzado** que se describen en este tema.</span><span class="sxs-lookup"><span data-stu-id="3bbe4-119">In Windows 10, there is no difference between the **Basic** and **Advanced** reporting options described in this topic.</span></span> <span data-ttu-id="3bbe4-120">Esta es una distinción heredada y la elección de cualquiera de las configuraciones dará como resultado el mismo nivel de protección entregada en la nube.</span><span class="sxs-lookup"><span data-stu-id="3bbe4-120">This is a legacy distinction and choosing either setting will result in the same level of cloud-delivered protection.</span></span> <span data-ttu-id="3bbe4-121">No hay diferencia en el tipo o cantidad de información que se comparte.</span><span class="sxs-lookup"><span data-stu-id="3bbe4-121">There is no difference in the type or amount of information that is shared.</span></span> <span data-ttu-id="3bbe4-122">Para obtener más información sobre lo que recopilamos, consulte la [Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?linkid=521839).</span><span class="sxs-lookup"><span data-stu-id="3bbe4-122">For more information on what we collect, see the [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=521839).</span></span>

## <a name="use-intune-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="3bbe4-123">Utilice Intune para activar la protección suministrada por la nube</span><span class="sxs-lookup"><span data-stu-id="3bbe4-123">Use Intune to turn on cloud-delivered protection</span></span>

1. <span data-ttu-id="3bbe4-124">Vaya al centro de administración de Microsoft Endpoint Manager ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) e inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="3bbe4-124">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>

2. <span data-ttu-id="3bbe4-125">En el panel **Inicio,** seleccione **Configuración del dispositivo > Perfiles**.</span><span class="sxs-lookup"><span data-stu-id="3bbe4-125">On the **Home** pane, select **Device configuration > Profiles**.</span></span>

3. <span data-ttu-id="3bbe4-126">Seleccione el tipo de perfil **Restricciones de dispositivo** que desea configurar.</span><span class="sxs-lookup"><span data-stu-id="3bbe4-126">Select the **Device restrictions** profile type you want to configure.</span></span> <span data-ttu-id="3bbe4-127">Si necesita crear un nuevo tipo de perfil **restricciones de dispositivo,** consulte [Configurar la configuración de restricción de dispositivos en Microsoft Intune](/intune/device-restrictions-configure).</span><span class="sxs-lookup"><span data-stu-id="3bbe4-127">If you need to create a new **Device restrictions** profile type, see [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).</span></span>

4. <span data-ttu-id="3bbe4-128">Seleccione **Configuración** de  >  **propiedades: Editar**  >  **Antivirus de Microsoft Defender**.</span><span class="sxs-lookup"><span data-stu-id="3bbe4-128">Select **Properties** > **Configuration settings: Edit** > **Microsoft Defender Antivirus**.</span></span>

5. <span data-ttu-id="3bbe4-129">En el conmutador **de protección entregado en la nube,** seleccione **Habilitar**.</span><span class="sxs-lookup"><span data-stu-id="3bbe4-129">On the **Cloud-delivered protection** switch, select **Enable**.</span></span>

6. <span data-ttu-id="3bbe4-130">En el menú desplegable **Solicitar usuarios antes del envío de ejemplo,** seleccione Enviar todos los datos **automáticamente.**</span><span class="sxs-lookup"><span data-stu-id="3bbe4-130">In the **Prompt users before sample submission** dropdown, select **Send all data automatically**.</span></span>

<span data-ttu-id="3bbe4-131">Para obtener más información acerca de los perfiles de dispositivo de Intune, incluida la forma de crear y configurar sus configuraciones, consulte [¿Qué son Microsoft Intune perfiles de dispositivo?](/intune/device-profiles)</span><span class="sxs-lookup"><span data-stu-id="3bbe4-131">For more information about Intune device profiles, including how to create and configure their settings, see [What are Microsoft Intune device profiles?](/intune/device-profiles)</span></span>

## <a name="use-microsoft-endpoint-manager-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="3bbe4-132">Utilice Microsoft Endpoint Manager para activar la protección suministrada por la nube</span><span class="sxs-lookup"><span data-stu-id="3bbe4-132">Use Microsoft Endpoint Manager to turn on cloud-delivered protection</span></span>

1. <span data-ttu-id="3bbe4-133">Vaya al centro de administración de Microsoft Endpoint Manager ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) e inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="3bbe4-133">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>

2. <span data-ttu-id="3bbe4-134">Elija **Endpoint Security**  >  **Antivirus**.</span><span class="sxs-lookup"><span data-stu-id="3bbe4-134">Choose **Endpoint security** > **Antivirus**.</span></span>

3. <span data-ttu-id="3bbe4-135">Seleccione un perfil antivirus.</span><span class="sxs-lookup"><span data-stu-id="3bbe4-135">Select an antivirus profile.</span></span> <span data-ttu-id="3bbe4-136">(Si aún no tiene uno o si desea crear un nuevo perfil, consulte [Configurar la configuración de restricción de dispositivos en Microsoft Intune](/intune/device-restrictions-configure).</span><span class="sxs-lookup"><span data-stu-id="3bbe4-136">(If you don't have one yet, or if you want to create a new profile, see [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).</span></span>

4. <span data-ttu-id="3bbe4-137">Seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="3bbe4-137">Select **Properties**.</span></span> <span data-ttu-id="3bbe4-138">A continuación, junto a **Configuración ,** elija **Edit**.</span><span class="sxs-lookup"><span data-stu-id="3bbe4-138">Then, next to **Configuration settings**, choose **Edit**.</span></span>

5. <span data-ttu-id="3bbe4-139">Expanda **Protección en** la nube y, a continuación, en la lista Nivel de protección entregado en **la nube,** seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="3bbe4-139">Expand **Cloud protection**, and then in the **Cloud-delivered protection level** list, select one of the following:</span></span>
   - <span data-ttu-id="3bbe4-140">**Alto**: Aplica un fuerte nivel de detección.</span><span class="sxs-lookup"><span data-stu-id="3bbe4-140">**High**: Applies a strong level of detection.</span></span>
   - <span data-ttu-id="3bbe4-141">**Alto plus**: Utiliza el **alto** nivel y aplica medidas de protección adicionales (pueden afectar al rendimiento del cliente).</span><span class="sxs-lookup"><span data-stu-id="3bbe4-141">**High plus**: Uses the **High** level and applies additional protection measures (may impact client performance).</span></span>
   - <span data-ttu-id="3bbe4-142">**Tolerancia cero**: Bloquea todos los ejecutables desconocidos.</span><span class="sxs-lookup"><span data-stu-id="3bbe4-142">**Zero tolerance**: Blocks all unknown executables.</span></span>

6. <span data-ttu-id="3bbe4-143">Seleccione **Revisar + guardar** y, a continuación, elija **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="3bbe4-143">Select **Review + save**, then choose **Save**.</span></span>

<span data-ttu-id="3bbe4-144">Para obtener más información acerca de cómo configurar Microsoft Endpoint Configuration Manager, consulte [Cómo crear e implementar directivas antimalware: servicio de protección en la nube.](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)</span><span class="sxs-lookup"><span data-stu-id="3bbe4-144">For more information about configuring Microsoft Endpoint Configuration Manager, see [How to create and deploy antimalware policies: Cloud-protection service](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service).</span></span>

## <a name="use-group-policy-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="3bbe4-145">Utilice la directiva de grupo para activar la protección entregada en la nube</span><span class="sxs-lookup"><span data-stu-id="3bbe4-145">Use Group Policy to turn on cloud-delivered protection</span></span>

1. <span data-ttu-id="3bbe4-146">En el dispositivo de administración de directivas de grupo, abra la [Consola de administración de directivas de grupo,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))haga clic con el botón derecho en el objeto de directiva de grupo que desea configurar y seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="3bbe4-146">On your Group Policy management device, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="3bbe4-147">En el **Editor de administración de directivas de** grupo, vaya a Configuración del **equipo**.</span><span class="sxs-lookup"><span data-stu-id="3bbe4-147">In the **Group Policy Management Editor**, go to **Computer configuration**.</span></span>

3. <span data-ttu-id="3bbe4-148">Seleccione **Plantillas administrativas**.</span><span class="sxs-lookup"><span data-stu-id="3bbe4-148">Select **Administrative templates**.</span></span>

4. <span data-ttu-id="3bbe4-149">Expanda el árbol a **componentes Windows > Antivirus de Microsoft Defender > MAPS**</span><span class="sxs-lookup"><span data-stu-id="3bbe4-149">Expand the tree to **Windows components > Microsoft Defender Antivirus > MAPS**</span></span>

5. <span data-ttu-id="3bbe4-150">Haga doble clic en **Unirse a Microsoft MAPS**.</span><span class="sxs-lookup"><span data-stu-id="3bbe4-150">Double-click **Join Microsoft MAPS**.</span></span> <span data-ttu-id="3bbe4-151">Asegúrese de que la opción esté activada y establecida en **MAPAS básicos** o **MAPAS avanzados.**</span><span class="sxs-lookup"><span data-stu-id="3bbe4-151">Ensure the option is turned on and set to **Basic MAPS** or **Advanced MAPS**.</span></span> <span data-ttu-id="3bbe4-152">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3bbe4-152">Select **OK**.</span></span>

6. <span data-ttu-id="3bbe4-153">Haga doble clic en **Enviar ejemplos de archivos cuando se requiera un análisis posterior.**</span><span class="sxs-lookup"><span data-stu-id="3bbe4-153">Double-click **Send file samples when further analysis is required**.</span></span> <span data-ttu-id="3bbe4-154">Asegúrese de que la primera opción está establecida en **Habilitado** y de que las otras opciones están establecidas en:</span><span class="sxs-lookup"><span data-stu-id="3bbe4-154">Ensure that the first option is set to **Enabled** and that the other options are set to either:</span></span>

    1. <span data-ttu-id="3bbe4-155">**Enviar muestras seguras** (1)</span><span class="sxs-lookup"><span data-stu-id="3bbe4-155">**Send safe samples** (1)</span></span>
    2. <span data-ttu-id="3bbe4-156">**Enviar todas las muestras** (3)</span><span class="sxs-lookup"><span data-stu-id="3bbe4-156">**Send all samples** (3)</span></span>

        >[!NOTE]
        > <span data-ttu-id="3bbe4-157">La opción **Enviar muestras seguras** (1) significa que la mayoría de las muestras se enviarán automáticamente.</span><span class="sxs-lookup"><span data-stu-id="3bbe4-157">The **Send safe samples** (1) option means that most samples will be sent automatically.</span></span> <span data-ttu-id="3bbe4-158">Los archivos que probablemente contengan información personal seguirán solicitando y requerirán confirmación adicional.</span><span class="sxs-lookup"><span data-stu-id="3bbe4-158">Files that are likely to contain personal information will still prompt and require additional confirmation.</span></span>
        > <span data-ttu-id="3bbe4-159">Establecer la opción en **Always Prompt** (0) reducirá el estado de protección del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3bbe4-159">Setting the option to **Always Prompt** (0) will lower the protection state of the device.</span></span> <span data-ttu-id="3bbe4-160">Establecerlo en **Nunca enviar** (2) significa que la característica Bloquear a [primera vista](configure-block-at-first-sight-microsoft-defender-antivirus.md) de Microsoft Defender para endpoint no funcionará.</span><span class="sxs-lookup"><span data-stu-id="3bbe4-160">Setting it to **Never send** (2) means that the [Block at First Sight](configure-block-at-first-sight-microsoft-defender-antivirus.md) feature of Microsoft Defender for Endpoint won't work.</span></span>

7. <span data-ttu-id="3bbe4-161">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3bbe4-161">Select **OK**.</span></span>

## <a name="use-powershell-cmdlets-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="3bbe4-162">Usar cmdlets de PowerShell para activar la protección entregada en la nube</span><span class="sxs-lookup"><span data-stu-id="3bbe4-162">Use PowerShell cmdlets to turn on cloud-delivered protection</span></span>

<span data-ttu-id="3bbe4-163">Los siguientes cmdlets pueden activar la protección entregada en la nube:</span><span class="sxs-lookup"><span data-stu-id="3bbe4-163">The following cmdlets can turn on cloud-delivered protection:</span></span>

```PowerShell
Set-MpPreference -MAPSReporting Advanced
Set-MpPreference -SubmitSamplesConsent SendAllSamples
```

<span data-ttu-id="3bbe4-164">Para obtener más información sobre cómo usar PowerShell con Antivirus de Microsoft Defender, vea [Usar cmdlets de PowerShell para configurar y ejecutar cmdlets de Antivirus de Microsoft Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md) y [Defender.](/powershell/module/defender/)</span><span class="sxs-lookup"><span data-stu-id="3bbe4-164">For more information on how to use PowerShell with Microsoft Defender Antivirus, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span> <span data-ttu-id="3bbe4-165">[Directiva CSP - Defender](/windows/client-management/mdm/policy-csp-defender) también tiene más información específicamente en [-SubmitSamplesConsent](/windows/client-management/mdm/policy-csp-defender#defender-submitsamplesconsent).</span><span class="sxs-lookup"><span data-stu-id="3bbe4-165">[Policy CSP - Defender](/windows/client-management/mdm/policy-csp-defender) also has more information specifically on [-SubmitSamplesConsent](/windows/client-management/mdm/policy-csp-defender#defender-submitsamplesconsent).</span></span>

>[!NOTE]
> <span data-ttu-id="3bbe4-166">También puede establecer **-SubmitSamplesConsent** `SendSafeSamples` en (la configuración predeterminada), `NeverSend` o `AlwaysPrompt` .</span><span class="sxs-lookup"><span data-stu-id="3bbe4-166">You can also set **-SubmitSamplesConsent** to `SendSafeSamples` (the default setting), `NeverSend`, or `AlwaysPrompt`.</span></span> <span data-ttu-id="3bbe4-167">La `SendSafeSamples` configuración significa que la mayoría de las muestras se enviarán automáticamente.</span><span class="sxs-lookup"><span data-stu-id="3bbe4-167">The `SendSafeSamples` setting means that most samples will be sent automatically.</span></span> <span data-ttu-id="3bbe4-168">Los archivos que probablemente contengan información personal seguirán solicitando y requerirán confirmación adicional.</span><span class="sxs-lookup"><span data-stu-id="3bbe4-168">Files that are likely to contain personal information will still prompt and require additional confirmation.</span></span>

>[!WARNING]
> <span data-ttu-id="3bbe4-169">Configuración **-SubmitSamplesConsent** `NeverSend` a o `AlwaysPrompt` bajará el nivel de protección del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3bbe4-169">Setting **-SubmitSamplesConsent** to `NeverSend` or `AlwaysPrompt` will lower the protection level of the device.</span></span> <span data-ttu-id="3bbe4-170">Además, establecerlo `NeverSend` significa que la característica [Bloquear a primera vista](configure-block-at-first-sight-microsoft-defender-antivirus.md) de Microsoft Defender para endpoint no funcionará.</span><span class="sxs-lookup"><span data-stu-id="3bbe4-170">In addition, setting it to `NeverSend` means that the [Block at First Sight](configure-block-at-first-sight-microsoft-defender-antivirus.md) feature of Microsoft Defender for Endpoint won't work.</span></span>

## <a name="use-windows-management-instruction-wmi-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="3bbe4-171">Utilice Windows Instrucción de administración (WMI) para activar la protección suministrada en la nube</span><span class="sxs-lookup"><span data-stu-id="3bbe4-171">Use Windows Management Instruction (WMI) to turn on cloud-delivered protection</span></span>

<span data-ttu-id="3bbe4-172">Utilice el método [ **Set** de la](/previous-versions/windows/desktop/defender/set-msft-mppreference) clase MSFT_MpPreference para las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="3bbe4-172">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/defender/set-msft-mppreference) class for the following properties:</span></span>

```WMI
MAPSReporting
SubmitSamplesConsent
```

<span data-ttu-id="3bbe4-173">Para obtener más información acerca de los parámetros permitidos, vea [Windows Defender API WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="3bbe4-173">For more information about allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span></span>

## <a name="turn-on-cloud-delivered-protection-on-individual-clients-with-the-windows-security-app"></a><span data-ttu-id="3bbe4-174">Activa la protección entregada en la nube a clientes individuales con la aplicación Seguridad de Windows</span><span class="sxs-lookup"><span data-stu-id="3bbe4-174">Turn on cloud-delivered protection on individual clients with the Windows Security app</span></span>

> [!NOTE]
> <span data-ttu-id="3bbe4-175">Si la **opción Configurar invalidación de configuración local para notificar** la configuración de directiva de grupo de Microsoft MAPS está establecida en **Deshabilitado**, la configuración de protección basada en **la nube** en Windows Configuración estará atenuada y no estará disponible.</span><span class="sxs-lookup"><span data-stu-id="3bbe4-175">If the **Configure local setting override for reporting Microsoft MAPS** Group Policy setting is set to **Disabled**, then the **Cloud-based protection** setting in Windows Settings will be greyed-out and unavailable.</span></span> <span data-ttu-id="3bbe4-176">Los cambios realizados a través de un objeto de directiva de grupo deben implementarse en primer lugar en los extremos individuales antes de que se actualice la configuración en la configuración de Windows.</span><span class="sxs-lookup"><span data-stu-id="3bbe4-176">Changes made through a Group Policy Object must first be deployed to individual endpoints before the setting will be updated in Windows Settings.</span></span>

1. <span data-ttu-id="3bbe4-177">Abra la aplicación Seguridad de Windows seleccionando el icono de escudo en la barra de tareas o buscando en el menú inicio **de Defender**.</span><span class="sxs-lookup"><span data-stu-id="3bbe4-177">Open the Windows Security app by selecting the shield icon in the task bar, or by searching the start menu for **Defender**.</span></span>

2. <span data-ttu-id="3bbe4-178">Seleccione el **icono de protección contra amenazas & virus** (o el icono de escudo en la barra de menús izquierda) y, a continuación, la etiqueta de configuración de protección contra amenazas & **virus:**</span><span class="sxs-lookup"><span data-stu-id="3bbe4-178">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar) and then the **Virus & threat protection settings** label:</span></span>

    ![Captura de pantalla de la etiqueta Protección contra virus y amenazas en la aplicación Seguridad de Windows](images/defender/wdav-protection-settings-wdsc.png)

3. <span data-ttu-id="3bbe4-180">Confirme que **la protección basada en la nube** y el envío automático de **muestras** se activan. </span><span class="sxs-lookup"><span data-stu-id="3bbe4-180">Confirm that **Cloud-based Protection** and **Automatic sample submission** are switched to **On**.</span></span>

> [!NOTE]
> <span data-ttu-id="3bbe4-181">Si el envío automático de ejemplo se ha configurado con directiva de grupo, la configuración se atenuará y no estará disponible.</span><span class="sxs-lookup"><span data-stu-id="3bbe4-181">If automatic sample submission has been configured with Group Policy then the setting will be greyed-out and unavailable.</span></span>

## <a name="related-articles"></a><span data-ttu-id="3bbe4-182">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="3bbe4-182">Related articles</span></span>

- [<span data-ttu-id="3bbe4-183">Configurar el período de espera de bloqueo en la nube</span><span class="sxs-lookup"><span data-stu-id="3bbe4-183">Configure the cloud block timeout period</span></span>](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md)
- [<span data-ttu-id="3bbe4-184">Configurar bloque a primera vista</span><span class="sxs-lookup"><span data-stu-id="3bbe4-184">Configure block at first sight</span></span>](configure-block-at-first-sight-microsoft-defender-antivirus.md)
- [<span data-ttu-id="3bbe4-185">Usar cmdlets PowerShell para administrar el Antivirus de Windows Defender</span><span class="sxs-lookup"><span data-stu-id="3bbe4-185">Use PowerShell cmdlets to manage Microsoft Defender Antivirus</span></span>](use-powershell-cmdlets-microsoft-defender-antivirus.md)
- <span data-ttu-id="3bbe4-186">[Ayude a proteger Windows PC con Endpoint Protection para Microsoft Intune](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)]</span><span class="sxs-lookup"><span data-stu-id="3bbe4-186">[Help secure Windows PCs with Endpoint Protection for Microsoft Intune](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)]</span></span>
- [<span data-ttu-id="3bbe4-187">Cmdlets defensores</span><span class="sxs-lookup"><span data-stu-id="3bbe4-187">Defender cmdlets</span></span>](/powershell/module/defender/)
- [<span data-ttu-id="3bbe4-188">Utilice la protección entregada en la nube de Microsoft en Antivirus de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="3bbe4-188">Use Microsoft cloud-delivered protection in Microsoft Defender Antivirus</span></span>](cloud-protection-microsoft-defender-antivirus.md)
- [<span data-ttu-id="3bbe4-189">Cómo crear e implementar políticas antimalware: servicio de protección en la nube</span><span class="sxs-lookup"><span data-stu-id="3bbe4-189">How to create and deploy antimalware policies: Cloud-protection service</span></span>](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)
- [<span data-ttu-id="3bbe4-190">Antivirus de Microsoft Defender en Windows 10</span><span class="sxs-lookup"><span data-stu-id="3bbe4-190">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
