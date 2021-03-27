---
title: Configurar ATP de Microsoft Defender para características de iOS
description: Describe cómo implementar ATP de Microsoft Defender para características de iOS
keywords: microsoft, defender, atp, ios, configure, features, ios
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
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 18fbc13614753ae57856a124d76bbad682ab88e5
ms.sourcegitcommit: a965c498e6b3890877f895d5197898b306092813
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/26/2021
ms.locfileid: "51379363"
---
# <a name="configure-microsoft-defender-for-endpoint-for-ios-features"></a><span data-ttu-id="e9377-104">Configurar Microsoft Defender para endpoint para características de iOS</span><span class="sxs-lookup"><span data-stu-id="e9377-104">Configure Microsoft Defender for Endpoint for iOS features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e9377-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="e9377-105">**Applies to:**</span></span>
- [<span data-ttu-id="e9377-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="e9377-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="e9377-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e9377-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="e9377-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="e9377-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="e9377-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="e9377-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

> [!NOTE]
> <span data-ttu-id="e9377-110">Defender para endpoint para iOS usaría una VPN para proporcionar la característica de protección web.</span><span class="sxs-lookup"><span data-stu-id="e9377-110">Defender for Endpoint for iOS would use a VPN in order to provide the Web Protection feature.</span></span> <span data-ttu-id="e9377-111">No se trata de una VPN normal y es una VPN local o auto-looping que no toma tráfico fuera del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e9377-111">This is not a regular VPN and is a local/self-looping VPN that does not take traffic outside the device.</span></span>

## <a name="conditional-access-with-defender-for-endpoint-for-ios"></a><span data-ttu-id="e9377-112">Acceso condicional con Defender para endpoint para iOS</span><span class="sxs-lookup"><span data-stu-id="e9377-112">Conditional Access with Defender for Endpoint for iOS</span></span>  
<span data-ttu-id="e9377-113">Microsoft Defender para endpoint para iOS junto con Microsoft Intune y Azure Active Directory permite aplicar el cumplimiento de dispositivos y las directivas de acceso condicional en función de los niveles de riesgo del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e9377-113">Microsoft Defender for Endpoint for iOS along with Microsoft Intune and Azure Active Directory enables enforcing Device compliance and Conditional Access policies based on device risk levels.</span></span> <span data-ttu-id="e9377-114">Defender for Endpoint es una solución de Mobile Threat Defense (MTD) que puedes implementar para aprovechar esta funcionalidad a través de Intune.</span><span class="sxs-lookup"><span data-stu-id="e9377-114">Defender for Endpoint is a Mobile Threat Defense (MTD) solution that you can deploy to leverage this capability via Intune.</span></span>

<span data-ttu-id="e9377-115">Para obtener más información acerca de cómo configurar el acceso condicional con Defender para endpoint para iOS, consulte [Defender for Endpoint e Intune](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection).</span><span class="sxs-lookup"><span data-stu-id="e9377-115">For more information about how to set up Conditional Access with Defender for Endpoint for iOS, see [Defender for Endpoint and Intune](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection).</span></span>

## <a name="web-protection-and-vpn"></a><span data-ttu-id="e9377-116">Protección web y VPN</span><span class="sxs-lookup"><span data-stu-id="e9377-116">Web Protection and VPN</span></span>

<span data-ttu-id="e9377-117">De forma predeterminada, Defender para endpoint para iOS incluye y habilita la característica de protección web.</span><span class="sxs-lookup"><span data-stu-id="e9377-117">By default, Defender for Endpoint for iOS includes and enables the web protection feature.</span></span> <span data-ttu-id="e9377-118">[La protección web](web-protection-overview.md) ayuda a proteger los dispositivos contra amenazas web y a proteger a los usuarios de ataques de phishing.</span><span class="sxs-lookup"><span data-stu-id="e9377-118">[Web protection](web-protection-overview.md) helps to secure devices against web threats and protect users from phishing attacks.</span></span> <span data-ttu-id="e9377-119">Defender for Endpoint para iOS usa una VPN para proporcionar esta protección.</span><span class="sxs-lookup"><span data-stu-id="e9377-119">Defender for Endpoint for iOS uses a VPN in order to provide this protection.</span></span> <span data-ttu-id="e9377-120">Tenga en cuenta que se trata de una VPN local y, a diferencia de la VPN tradicional, el tráfico de red no se envía fuera del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e9377-120">Please note this is a local VPN and unlike traditional VPN, network traffic is not sent outside the device.</span></span>

<span data-ttu-id="e9377-121">Aunque está habilitado de forma predeterminada, puede haber algunos casos que requieran deshabilitar VPN.</span><span class="sxs-lookup"><span data-stu-id="e9377-121">While enabled by default, there might be some cases that require you to disable VPN.</span></span> <span data-ttu-id="e9377-122">Por ejemplo, quieres ejecutar algunas aplicaciones que no funcionan cuando se configura una VPN.</span><span class="sxs-lookup"><span data-stu-id="e9377-122">For example, you want to run some apps that do not work when a VPN is configured.</span></span> <span data-ttu-id="e9377-123">En tales casos, puedes optar por deshabilitar VPN desde la aplicación en el dispositivo siguiendo los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="e9377-123">In such cases, you can choose to disable VPN from the app on the device by following the steps below:</span></span>

1. <span data-ttu-id="e9377-124">En el dispositivo iOS, abre la aplicación **Configuración,** haz clic o pulsa **General** y, a continuación, **VPN.**</span><span class="sxs-lookup"><span data-stu-id="e9377-124">On your iOS device, open the **Settings** app, click or tap **General** and then **VPN**.</span></span>
1. <span data-ttu-id="e9377-125">Haz clic o pulsa en el botón "i" de ATP de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="e9377-125">Click or tap the "i" button for Microsoft Defender ATP.</span></span>
1. <span data-ttu-id="e9377-126">Desactiva **Conectar a petición para** deshabilitar VPN.</span><span class="sxs-lookup"><span data-stu-id="e9377-126">Toggle off **Connect On Demand** to disable VPN.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="e9377-127">![Configuración de VPN conectarse a petición](images/ios-vpn-config.png)</span><span class="sxs-lookup"><span data-stu-id="e9377-127">![VPN config connect on demand](images/ios-vpn-config.png)</span></span>

> [!NOTE]
> <span data-ttu-id="e9377-128">La protección web no estará disponible cuando la VPN esté deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="e9377-128">Web Protection will not be available when VPN is disabled.</span></span> <span data-ttu-id="e9377-129">Para volver a habilitar Protección web, abra la aplicación Microsoft Defender para endpoint en el dispositivo y haga clic o pulse **Iniciar VPN**.</span><span class="sxs-lookup"><span data-stu-id="e9377-129">To re-enable Web Protection, open the Microsoft Defender for Endpoint app on the device and click or tap **Start VPN**.</span></span>

## <a name="co-existence-of-multiple-vpn-profiles"></a><span data-ttu-id="e9377-130">Coexistencia de varios perfiles vpn</span><span class="sxs-lookup"><span data-stu-id="e9377-130">Co-existence of multiple VPN profiles</span></span>

<span data-ttu-id="e9377-131">Apple iOS no admite varias VPN de todo el dispositivo para estar activas simultáneamente.</span><span class="sxs-lookup"><span data-stu-id="e9377-131">Apple iOS does not support multiple device-wide VPNs to be active simultaneously.</span></span> <span data-ttu-id="e9377-132">Aunque pueden existir varios perfiles de VPN en el dispositivo, solo una VPN puede estar activa a la vez.</span><span class="sxs-lookup"><span data-stu-id="e9377-132">While multiple VPN profiles can exist on the device, only one VPN can be active at a time.</span></span>


## <a name="configure-compliance-policy-against-jailbroken-devices"></a><span data-ttu-id="e9377-133">Configurar la directiva de cumplimiento en dispositivos con jailbreak</span><span class="sxs-lookup"><span data-stu-id="e9377-133">Configure compliance policy against jailbroken devices</span></span>

<span data-ttu-id="e9377-134">Para proteger los datos corporativos de acceso en dispositivos iOS con jailbreak, le recomendamos que configure la siguiente directiva de cumplimiento en Intune.</span><span class="sxs-lookup"><span data-stu-id="e9377-134">To protect corporate data from being accessed on jailbroken iOS devices, we recommend that you set up the following compliance policy on Intune.</span></span>

> [!NOTE]
> <span data-ttu-id="e9377-135">En este momento, Microsoft Defender para Endpoint para iOS no proporciona protección contra escenarios de jailbreak.</span><span class="sxs-lookup"><span data-stu-id="e9377-135">At this time Microsoft Defender for Endpoint for iOS does not provide protection against jailbreak scenarios.</span></span> <span data-ttu-id="e9377-136">Si se usa en un dispositivo con jailbreak, en escenarios específicos, los datos que usa la aplicación como el identificador de correo electrónico corporativo y la imagen de perfil corporativo (si está disponible) se pueden exponer localmente</span><span class="sxs-lookup"><span data-stu-id="e9377-136">If used on a jailbroken device, then in specific scenarios data that is used by the application like your corporate email id and corporate profile picture (if available) can be exposed locally</span></span>

<span data-ttu-id="e9377-137">Siga los pasos siguientes para crear una directiva de cumplimiento contra dispositivos con jailbreak.</span><span class="sxs-lookup"><span data-stu-id="e9377-137">Follow the steps below to create a compliance policy against jailbroken devices.</span></span>

1. <span data-ttu-id="e9377-138">En [el Centro de administración de Microsoft Endpoint Manager,](https://go.microsoft.com/fwlink/?linkid=2109431)vaya a Directivas **de** cumplimiento  ->  **de dispositivos** Crear  ->  **directiva**.</span><span class="sxs-lookup"><span data-stu-id="e9377-138">In [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), go to **Devices** -> **Compliance policies** -> **Create Policy**.</span></span> <span data-ttu-id="e9377-139">Seleccione "iOS/iPadOS" como plataforma y haga clic **en Crear**.</span><span class="sxs-lookup"><span data-stu-id="e9377-139">Select "iOS/iPadOS" as platform and click **Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="e9377-140">![Crear directiva](images/ios-jb-policy.png)</span><span class="sxs-lookup"><span data-stu-id="e9377-140">![Create Policy](images/ios-jb-policy.png)</span></span>

2. <span data-ttu-id="e9377-141">Especifique un nombre de la directiva, por ejemplo, "Compliance Policy for Jailbreak".</span><span class="sxs-lookup"><span data-stu-id="e9377-141">Specify a name of the policy, for example "Compliance Policy for Jailbreak".</span></span>
3. <span data-ttu-id="e9377-142">En la página Configuración de cumplimiento, haga clic para expandir **la sección Estado del** dispositivo y haga clic en **Bloquear** para el **campo Dispositivos con jailbreak.**</span><span class="sxs-lookup"><span data-stu-id="e9377-142">In the compliance settings page, click to expand **Device Health** section and click **Block** for **Jailbroken devices** field.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="e9377-143">![Configuración de directiva](images/ios-jb-settings.png)</span><span class="sxs-lookup"><span data-stu-id="e9377-143">![Policy Settings](images/ios-jb-settings.png)</span></span>

4. <span data-ttu-id="e9377-144">En la *sección Acción por* incumplimiento, seleccione las acciones según sus requisitos y seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e9377-144">In the *Action for noncompliance* section, select the actions as per your requirements and select **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="e9377-145">![Acciones de directiva](images/ios-jb-actions.png)</span><span class="sxs-lookup"><span data-stu-id="e9377-145">![Policy Actions](images/ios-jb-actions.png)</span></span>

5. <span data-ttu-id="e9377-146">En la *sección Asignaciones,* seleccione los grupos de usuarios que desea incluir para esta directiva y, a continuación, **seleccione Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e9377-146">In the *Assignments* section, select the user groups that you want to include for this policy and then select **Next**.</span></span>
6. <span data-ttu-id="e9377-147">En la **sección Review+Create,** compruebe que toda la información especificada es correcta y, a continuación, **seleccione Crear**.</span><span class="sxs-lookup"><span data-stu-id="e9377-147">In the **Review+Create** section, verify that all the information entered is correct and then select **Create**.</span></span>

## <a name="configure-custom-indicators"></a><span data-ttu-id="e9377-148">Configurar indicadores personalizados</span><span class="sxs-lookup"><span data-stu-id="e9377-148">Configure custom indicators</span></span>

<span data-ttu-id="e9377-149">Defender for Endpoint for iOS permite a los administradores configurar indicadores personalizados en dispositivos iOS.</span><span class="sxs-lookup"><span data-stu-id="e9377-149">Defender for Endpoint for iOS enables admins to configure custom indicators on iOS devices as well.</span></span> <span data-ttu-id="e9377-150">Para obtener más información sobre cómo configurar indicadores personalizados, vea [Administrar indicadores](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-indicators).</span><span class="sxs-lookup"><span data-stu-id="e9377-150">For more information on how to configure custom indicators, see [Manage indicators](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-indicators).</span></span>

> [!NOTE]
> <span data-ttu-id="e9377-151">Defender para endpoint para iOS admite la creación de indicadores personalizados solo para direcciones IP y direcciones URL/dominios.</span><span class="sxs-lookup"><span data-stu-id="e9377-151">Defender for Endpoint for iOS supports creating custom indicators only for IP addresses and URLs/domains.</span></span>

## <a name="report-unsafe-site"></a><span data-ttu-id="e9377-152">Informe de sitio no seguro</span><span class="sxs-lookup"><span data-stu-id="e9377-152">Report unsafe site</span></span>

<span data-ttu-id="e9377-153">Los sitios web de suplantación de identidad suplantan sitios web de confianza con el fin de obtener su información personal o financiera.</span><span class="sxs-lookup"><span data-stu-id="e9377-153">Phishing websites impersonate trustworthy websites for the purpose of obtaining your personal or financial information.</span></span> <span data-ttu-id="e9377-154">Visita la [página Proporcionar comentarios sobre la protección de](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) red si quieres informar de un sitio web que podría ser un sitio de suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="e9377-154">Visit the [Provide feedback about network protection](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) page if you want to report a website that could be a phishing site.</span></span>

## <a name="battery-consumption-issues-on-ios-when-microsoft-defender-for-endpoint-is-installed"></a><span data-ttu-id="e9377-155">Problemas de consumo de batería en iOS cuando se instala Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="e9377-155">Battery Consumption issues on iOS when Microsoft Defender for Endpoint is installed</span></span>

<span data-ttu-id="e9377-156">Apple calcula el uso de la batería por parte de una aplicación en función de una gran variedad de factores, como el uso de la CPU y la red.</span><span class="sxs-lookup"><span data-stu-id="e9377-156">The battery usage by an app is computed by Apple based on a multitude of factors including CPU and Network usage.</span></span> <span data-ttu-id="e9377-157">Microsoft Defender para endpoint usa una VPN local/loop-back en segundo plano para comprobar el tráfico web en busca de sitios web o conexiones malintencionadas.</span><span class="sxs-lookup"><span data-stu-id="e9377-157">Microsoft Defender for Endpoint uses a local/loop-back VPN in the background to check web traffic for any malicious websites or connections.</span></span> <span data-ttu-id="e9377-158">Los paquetes de red de cualquier aplicación pasan por esta comprobación y eso hace que el uso de la batería de Microsoft Defender para Endpoint se calcule incorrectamente.</span><span class="sxs-lookup"><span data-stu-id="e9377-158">Network packets from any app go through this check and that causes the battery usage of Microsoft Defender for Endpoint to be computed inaccurately.</span></span> <span data-ttu-id="e9377-159">Esto da una impresión falsa al usuario.</span><span class="sxs-lookup"><span data-stu-id="e9377-159">This gives a false impression to the user.</span></span> <span data-ttu-id="e9377-160">El consumo real de batería de Microsoft Defender para Endpoint es menor que lo que se muestra en la página Configuración de la batería en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e9377-160">The actual battery consumption of Microsoft Defender for Endpoint is lesser than what is shown on the Battery Settings page on the device.</span></span> <span data-ttu-id="e9377-161">Esto se basa en pruebas realizadas en la aplicación Microsoft Defender para Endpoint para comprender el consumo de batería.</span><span class="sxs-lookup"><span data-stu-id="e9377-161">This is based on conducted tests done on the Microsoft Defender for Endpoint app to understand battery consumption.</span></span>

<span data-ttu-id="e9377-162">Además, la VPN usada es una VPN local y, a diferencia de las VPN tradicionales, el tráfico de red no se envía fuera del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e9377-162">Also the VPN used is a local VPN and unlike traditional VPNs, network traffic is not sent outside the device.</span></span>
