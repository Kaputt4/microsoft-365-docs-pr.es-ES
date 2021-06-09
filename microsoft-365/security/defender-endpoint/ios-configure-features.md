---
title: Configurar Microsoft Defender para endpoint en características de iOS
description: Describe cómo implementar Microsoft Defender para endpoint en características de iOS
keywords: microsoft, defender, Microsoft Defender para Endpoint, ios, configure, features, ios
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: d32d40ac8ce086caedd53e0a69aac2a3025dc702
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842259"
---
# <a name="configure-microsoft-defender-for-endpoint-on-ios-features"></a><span data-ttu-id="e1dad-104">Configurar Microsoft Defender para endpoint en características de iOS</span><span class="sxs-lookup"><span data-stu-id="e1dad-104">Configure Microsoft Defender for Endpoint on iOS features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e1dad-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="e1dad-105">**Applies to:**</span></span>
- [<span data-ttu-id="e1dad-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="e1dad-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="e1dad-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e1dad-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="e1dad-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="e1dad-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="e1dad-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="e1dad-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

> [!NOTE]
> <span data-ttu-id="e1dad-110">Defender para endpoint en iOS usaría una VPN para proporcionar la característica de protección web.</span><span class="sxs-lookup"><span data-stu-id="e1dad-110">Defender for Endpoint on iOS would use a VPN in order to provide the Web Protection feature.</span></span> <span data-ttu-id="e1dad-111">No se trata de una VPN normal y es una VPN local o auto-looping que no toma tráfico fuera del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e1dad-111">This is not a regular VPN and is a local/self-looping VPN that does not take traffic outside the device.</span></span>

## <a name="conditional-access-with-defender-for-endpoint-on-ios"></a><span data-ttu-id="e1dad-112">Acceso condicional con Defender para endpoint en iOS</span><span class="sxs-lookup"><span data-stu-id="e1dad-112">Conditional Access with Defender for Endpoint on iOS</span></span>  
<span data-ttu-id="e1dad-113">Microsoft Defender para endpoint en iOS junto con Microsoft Intune y Azure Active Directory permite aplicar el cumplimiento de dispositivos y las directivas de acceso condicional en función de la puntuación de riesgo del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e1dad-113">Microsoft Defender for Endpoint on iOS along with Microsoft Intune and Azure Active Directory enables enforcing Device compliance and Conditional Access policies based on device risk score.</span></span> <span data-ttu-id="e1dad-114">Defender for Endpoint es una solución de Mobile Threat Defense (MTD) que puedes implementar para aprovechar esta funcionalidad a través de Intune.</span><span class="sxs-lookup"><span data-stu-id="e1dad-114">Defender for Endpoint is a Mobile Threat Defense (MTD) solution that you can deploy to leverage this capability via Intune.</span></span>

<span data-ttu-id="e1dad-115">Para obtener más información acerca de cómo configurar el acceso condicional con Defender para endpoint en iOS, vea [Defender for Endpoint e Intune](/mem/intune/protect/advanced-threat-protection).</span><span class="sxs-lookup"><span data-stu-id="e1dad-115">For more information about how to set up Conditional Access with Defender for Endpoint on iOS, see [Defender for Endpoint and Intune](/mem/intune/protect/advanced-threat-protection).</span></span>

### <a name="jailbreak-detection-by-microsoft-defender-for-endpoint"></a><span data-ttu-id="e1dad-116">Detección de jailbreak por Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="e1dad-116">Jailbreak detection by Microsoft Defender for Endpoint</span></span>
<span data-ttu-id="e1dad-117">Microsoft Defender para endpoint tiene la capacidad de detectar dispositivos administrados y no administrados que están liberados.</span><span class="sxs-lookup"><span data-stu-id="e1dad-117">Microsoft Defender for Endpoint has the capability of detecting unmanaged and managed devices that are jailbroken.</span></span> <span data-ttu-id="e1dad-118">Si se detecta que un dispositivo está liberado, se notifica una alerta de alto riesgo al Centro de seguridad y si el acceso condicional se configura en función de la puntuación de riesgo del dispositivo, se bloqueará el acceso al dispositivo a los datos corporativos.</span><span class="sxs-lookup"><span data-stu-id="e1dad-118">If a device is detected to be jailbroken, a **High**-risk alert will be reported to Security Center and if Conditional Access is setup based on device risk score, then the device will be blocked from accessing corporate data.</span></span>

## <a name="web-protection-and-vpn"></a><span data-ttu-id="e1dad-119">Protección web y VPN</span><span class="sxs-lookup"><span data-stu-id="e1dad-119">Web Protection and VPN</span></span>

<span data-ttu-id="e1dad-120">De forma predeterminada, Defender para endpoint en iOS incluye y habilita la característica de protección web.</span><span class="sxs-lookup"><span data-stu-id="e1dad-120">By default, Defender for Endpoint on iOS includes and enables the web protection feature.</span></span> <span data-ttu-id="e1dad-121">[La protección web](web-protection-overview.md) ayuda a proteger los dispositivos contra amenazas web y a proteger a los usuarios de ataques de phishing.</span><span class="sxs-lookup"><span data-stu-id="e1dad-121">[Web protection](web-protection-overview.md) helps to secure devices against web threats and protect users from phishing attacks.</span></span> <span data-ttu-id="e1dad-122">Defender para endpoint en iOS usa una VPN para proporcionar esta protección.</span><span class="sxs-lookup"><span data-stu-id="e1dad-122">Defender for Endpoint on iOS uses a VPN in order to provide this protection.</span></span> <span data-ttu-id="e1dad-123">Tenga en cuenta que se trata de una VPN local y, a diferencia de la VPN tradicional, el tráfico de red no se envía fuera del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e1dad-123">Please note this is a local VPN and unlike traditional VPN, network traffic is not sent outside the device.</span></span>

<span data-ttu-id="e1dad-124">Aunque está habilitado de forma predeterminada, puede haber algunos casos que requieran deshabilitar VPN.</span><span class="sxs-lookup"><span data-stu-id="e1dad-124">While enabled by default, there might be some cases that require you to disable VPN.</span></span> <span data-ttu-id="e1dad-125">Por ejemplo, quieres ejecutar algunas aplicaciones que no funcionan cuando se configura una VPN.</span><span class="sxs-lookup"><span data-stu-id="e1dad-125">For example, you want to run some apps that do not work when a VPN is configured.</span></span> <span data-ttu-id="e1dad-126">En tales casos, puedes optar por deshabilitar VPN desde la aplicación en el dispositivo siguiendo los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="e1dad-126">In such cases, you can choose to disable VPN from the app on the device by following the steps below:</span></span>

1. <span data-ttu-id="e1dad-127">En el dispositivo iOS, abre la **aplicación Configuración,** haz clic o pulsa **General** y, a continuación, **VPN.**</span><span class="sxs-lookup"><span data-stu-id="e1dad-127">On your iOS device, open the **Settings** app, click or tap **General** and then **VPN**.</span></span>
1. <span data-ttu-id="e1dad-128">Haga clic o pulse en el botón "i" de Microsoft Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="e1dad-128">Click or tap the "i" button for Microsoft Defender for Endpoint.</span></span>
1. <span data-ttu-id="e1dad-129">Desactiva la **Conectar a petición** para deshabilitar VPN.</span><span class="sxs-lookup"><span data-stu-id="e1dad-129">Toggle off **Connect On Demand** to disable VPN.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="e1dad-130">![Configuración de VPN conectarse a petición](images/ios-vpn-config.png)</span><span class="sxs-lookup"><span data-stu-id="e1dad-130">![VPN config connect on demand](images/ios-vpn-config.png)</span></span>

> [!NOTE]
> <span data-ttu-id="e1dad-131">La protección web no estará disponible cuando la VPN esté deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="e1dad-131">Web Protection will not be available when VPN is disabled.</span></span> <span data-ttu-id="e1dad-132">Para volver a habilitar Protección web, abra la aplicación Microsoft Defender para endpoint en el dispositivo y haga clic o pulse **Iniciar VPN**.</span><span class="sxs-lookup"><span data-stu-id="e1dad-132">To re-enable Web Protection, open the Microsoft Defender for Endpoint app on the device and click or tap **Start VPN**.</span></span>

## <a name="co-existence-of-multiple-vpn-profiles"></a><span data-ttu-id="e1dad-133">Coexistencia de varios perfiles vpn</span><span class="sxs-lookup"><span data-stu-id="e1dad-133">Co-existence of multiple VPN profiles</span></span>

<span data-ttu-id="e1dad-134">Apple iOS no admite varias VPN de todo el dispositivo para estar activas simultáneamente.</span><span class="sxs-lookup"><span data-stu-id="e1dad-134">Apple iOS does not support multiple device-wide VPNs to be active simultaneously.</span></span> <span data-ttu-id="e1dad-135">Aunque pueden existir varios perfiles de VPN en el dispositivo, solo una VPN puede estar activa a la vez.</span><span class="sxs-lookup"><span data-stu-id="e1dad-135">While multiple VPN profiles can exist on the device, only one VPN can be active at a time.</span></span>


## <a name="configure-compliance-policy-against-jailbroken-devices"></a><span data-ttu-id="e1dad-136">Configurar la directiva de cumplimiento en dispositivos con jailbreak</span><span class="sxs-lookup"><span data-stu-id="e1dad-136">Configure compliance policy against jailbroken devices</span></span>

<span data-ttu-id="e1dad-137">Para proteger los datos corporativos de acceso en dispositivos iOS con jailbreak, le recomendamos que configure la siguiente directiva de cumplimiento en Intune.</span><span class="sxs-lookup"><span data-stu-id="e1dad-137">To protect corporate data from being accessed on jailbroken iOS devices, we recommend that you set up the following compliance policy on Intune.</span></span>

> [!NOTE]
> <span data-ttu-id="e1dad-138">La detección de jailbreak es una funcionalidad proporcionada por Microsoft Defender para Endpoint en iOS.</span><span class="sxs-lookup"><span data-stu-id="e1dad-138">Jailbreak detection is a capability provided by Microsoft Defender for Endpoint on iOS.</span></span> <span data-ttu-id="e1dad-139">Sin embargo, se recomienda configurar esta directiva como una capa adicional de defensa frente a escenarios de jailbreak.</span><span class="sxs-lookup"><span data-stu-id="e1dad-139">However, we recommend that you setup this policy as an additional layer of defense against jailbreak scenarios.</span></span>

<span data-ttu-id="e1dad-140">Siga los pasos siguientes para crear una directiva de cumplimiento contra dispositivos con jailbreak.</span><span class="sxs-lookup"><span data-stu-id="e1dad-140">Follow the steps below to create a compliance policy against jailbroken devices.</span></span>

1. <span data-ttu-id="e1dad-141">En [Microsoft Endpoint Manager de administración,](https://go.microsoft.com/fwlink/?linkid=2109431)vaya a **Directivas de** cumplimiento de  ->  **dispositivos** Crear  ->  **directiva**.</span><span class="sxs-lookup"><span data-stu-id="e1dad-141">In [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), go to **Devices** -> **Compliance policies** -> **Create Policy**.</span></span> <span data-ttu-id="e1dad-142">Seleccione "iOS/iPadOS" como plataforma y haga clic **en Crear**.</span><span class="sxs-lookup"><span data-stu-id="e1dad-142">Select "iOS/iPadOS" as platform and click **Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="e1dad-143">![Crear directiva](images/ios-jb-policy.png)</span><span class="sxs-lookup"><span data-stu-id="e1dad-143">![Create Policy](images/ios-jb-policy.png)</span></span>

2. <span data-ttu-id="e1dad-144">Especifique un nombre de la directiva, por ejemplo, "Compliance Policy for Jailbreak".</span><span class="sxs-lookup"><span data-stu-id="e1dad-144">Specify a name of the policy, for example "Compliance Policy for Jailbreak".</span></span>
3. <span data-ttu-id="e1dad-145">En la página Configuración de cumplimiento, haga clic para expandir **la sección Estado del** dispositivo y haga clic en **Bloquear** para el **campo Dispositivos con jailbreak.**</span><span class="sxs-lookup"><span data-stu-id="e1dad-145">In the compliance settings page, click to expand **Device Health** section and click **Block** for **Jailbroken devices** field.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="e1dad-146">![Directiva Configuración](images/ios-jb-settings.png)</span><span class="sxs-lookup"><span data-stu-id="e1dad-146">![Policy Settings](images/ios-jb-settings.png)</span></span>

4. <span data-ttu-id="e1dad-147">En la *sección Acción por* incumplimiento, seleccione las acciones según sus requisitos y seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e1dad-147">In the *Action for noncompliance* section, select the actions as per your requirements and select **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="e1dad-148">![Acciones de directiva](images/ios-jb-actions.png)</span><span class="sxs-lookup"><span data-stu-id="e1dad-148">![Policy Actions](images/ios-jb-actions.png)</span></span>

5. <span data-ttu-id="e1dad-149">En la *sección Asignaciones,* seleccione los grupos de usuarios que desea incluir para esta directiva y, a continuación, **seleccione Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e1dad-149">In the *Assignments* section, select the user groups that you want to include for this policy and then select **Next**.</span></span>
6. <span data-ttu-id="e1dad-150">En la **sección Review+Create,** compruebe que toda la información especificada es correcta y, a continuación, **seleccione Crear**.</span><span class="sxs-lookup"><span data-stu-id="e1dad-150">In the **Review+Create** section, verify that all the information entered is correct and then select **Create**.</span></span>

## <a name="configure-custom-indicators"></a><span data-ttu-id="e1dad-151">Configurar indicadores personalizados</span><span class="sxs-lookup"><span data-stu-id="e1dad-151">Configure custom indicators</span></span>

<span data-ttu-id="e1dad-152">Defender para endpoint en iOS permite a los administradores configurar indicadores personalizados en dispositivos iOS también.</span><span class="sxs-lookup"><span data-stu-id="e1dad-152">Defender for Endpoint on iOS enables admins to configure custom indicators on iOS devices as well.</span></span> <span data-ttu-id="e1dad-153">Para obtener más información sobre cómo configurar indicadores personalizados, vea [Administrar indicadores](/microsoft-365/security/defender-endpoint/manage-indicators).</span><span class="sxs-lookup"><span data-stu-id="e1dad-153">For more information on how to configure custom indicators, see [Manage indicators](/microsoft-365/security/defender-endpoint/manage-indicators).</span></span>

> [!NOTE]
> <span data-ttu-id="e1dad-154">Defender para endpoint en iOS admite la creación de indicadores personalizados solo para direcciones IP y direcciones URL/dominios.</span><span class="sxs-lookup"><span data-stu-id="e1dad-154">Defender for Endpoint on iOS supports creating custom indicators only for IP addresses and URLs/domains.</span></span>

## <a name="report-unsafe-site"></a><span data-ttu-id="e1dad-155">Informe de sitio no seguro</span><span class="sxs-lookup"><span data-stu-id="e1dad-155">Report unsafe site</span></span>

<span data-ttu-id="e1dad-156">Los sitios web de suplantación de identidad suplantan sitios web de confianza con el fin de obtener su información personal o financiera.</span><span class="sxs-lookup"><span data-stu-id="e1dad-156">Phishing websites impersonate trustworthy websites for the purpose of obtaining your personal or financial information.</span></span> <span data-ttu-id="e1dad-157">Visita la [página Proporcionar comentarios sobre la protección de](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) red si quieres informar de un sitio web que podría ser un sitio de suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="e1dad-157">Visit the [Provide feedback about network protection](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) page if you want to report a website that could be a phishing site.</span></span>

