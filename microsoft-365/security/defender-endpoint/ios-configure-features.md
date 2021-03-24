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
ms.openlocfilehash: 8b9f4372321bfa17ce5c11081ca274a3360e18dd
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072315"
---
# <a name="configure-microsoft-defender-for-endpoint-for-ios-features"></a><span data-ttu-id="c2557-104">Configurar Microsoft Defender para endpoint para características de iOS</span><span class="sxs-lookup"><span data-stu-id="c2557-104">Configure Microsoft Defender for Endpoint for iOS features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c2557-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="c2557-105">**Applies to:**</span></span>
- [<span data-ttu-id="c2557-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="c2557-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="c2557-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c2557-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="c2557-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="c2557-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="c2557-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="c2557-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

> [!NOTE]
> <span data-ttu-id="c2557-110">Defender para endpoint para iOS usaría una VPN para proporcionar la característica de protección web.</span><span class="sxs-lookup"><span data-stu-id="c2557-110">Defender for Endpoint for iOS would use a VPN in order to provide the Web Protection feature.</span></span> <span data-ttu-id="c2557-111">No se trata de una VPN normal y es una VPN local o auto-looping que no toma tráfico fuera del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c2557-111">This is not a regular VPN and is a local/self-looping VPN that does not take traffic outside the device.</span></span>

## <a name="conditional-access-with-defender-for-endpoint-for-ios"></a><span data-ttu-id="c2557-112">Acceso condicional con Defender para endpoint para iOS</span><span class="sxs-lookup"><span data-stu-id="c2557-112">Conditional Access with Defender for Endpoint for iOS</span></span>  
<span data-ttu-id="c2557-113">Microsoft Defender para endpoint para iOS junto con Microsoft Intune y Azure Active Directory permite aplicar el cumplimiento de dispositivos y las directivas de acceso condicional en función de los niveles de riesgo del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c2557-113">Microsoft Defender for Endpoint for iOS along with Microsoft Intune and Azure Active Directory enables enforcing Device compliance and Conditional Access policies based on device risk levels.</span></span> <span data-ttu-id="c2557-114">Defender for Endpoint es una solución de Mobile Threat Defense (MTD) que puedes implementar para aprovechar esta funcionalidad a través de Intune.</span><span class="sxs-lookup"><span data-stu-id="c2557-114">Defender for Endpoint is a Mobile Threat Defense (MTD) solution that you can deploy to leverage this capability via Intune.</span></span>

<span data-ttu-id="c2557-115">Para obtener más información acerca de cómo configurar el acceso condicional con Defender para endpoint para iOS, consulte [Defender for Endpoint e Intune](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection).</span><span class="sxs-lookup"><span data-stu-id="c2557-115">For more information about how to set up Conditional Access with Defender for Endpoint for iOS, see [Defender for Endpoint and Intune](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection).</span></span>

## <a name="web-protection-and-vpn"></a><span data-ttu-id="c2557-116">Protección web y VPN</span><span class="sxs-lookup"><span data-stu-id="c2557-116">Web Protection and VPN</span></span>

<span data-ttu-id="c2557-117">De forma predeterminada, Defender para endpoint para iOS incluye y habilita la característica de protección web.</span><span class="sxs-lookup"><span data-stu-id="c2557-117">By default, Defender for Endpoint for iOS includes and enables the web protection feature.</span></span> <span data-ttu-id="c2557-118">[La protección web](web-protection-overview.md) ayuda a proteger los dispositivos contra amenazas web y a proteger a los usuarios de ataques de phishing.</span><span class="sxs-lookup"><span data-stu-id="c2557-118">[Web protection](web-protection-overview.md) helps to secure devices against web threats and protect users from phishing attacks.</span></span> <span data-ttu-id="c2557-119">Defender for Endpoint para iOS usa una VPN para proporcionar esta protección.</span><span class="sxs-lookup"><span data-stu-id="c2557-119">Defender for Endpoint for iOS uses a VPN in order to provide this protection.</span></span> <span data-ttu-id="c2557-120">Tenga en cuenta que se trata de una VPN local y, a diferencia de la VPN tradicional, el tráfico de red no se envía fuera del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c2557-120">Please note this is a local VPN and unlike traditional VPN, network traffic is not sent outside the device.</span></span>

<span data-ttu-id="c2557-121">Aunque está habilitado de forma predeterminada, puede haber algunos casos que requieran deshabilitar VPN.</span><span class="sxs-lookup"><span data-stu-id="c2557-121">While enabled by default, there might be some cases that require you to disable VPN.</span></span> <span data-ttu-id="c2557-122">Por ejemplo, quieres ejecutar algunas aplicaciones que no funcionan cuando se configura una VPN.</span><span class="sxs-lookup"><span data-stu-id="c2557-122">For example, you want to run some apps that do not work when a VPN is configured.</span></span> <span data-ttu-id="c2557-123">En tales casos, puedes optar por deshabilitar VPN desde la aplicación en el dispositivo siguiendo los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="c2557-123">In such cases, you can choose to disable VPN from the app on the device by following the steps below:</span></span>

1. <span data-ttu-id="c2557-124">En el dispositivo iOS, abre la aplicación **Configuración,** haz clic o pulsa **General** y, a continuación, **VPN.**</span><span class="sxs-lookup"><span data-stu-id="c2557-124">On your iOS device, open the **Settings** app, click or tap **General** and then **VPN**.</span></span>
1. <span data-ttu-id="c2557-125">Haz clic o pulsa en el botón "i" de ATP de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="c2557-125">Click or tap the "i" button for Microsoft Defender ATP.</span></span>
1. <span data-ttu-id="c2557-126">Desactiva **Conectar a petición para** deshabilitar VPN.</span><span class="sxs-lookup"><span data-stu-id="c2557-126">Toggle off **Connect On Demand** to disable VPN.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="c2557-127">![Configuración de VPN conectarse a petición](images/ios-vpn-config.png)</span><span class="sxs-lookup"><span data-stu-id="c2557-127">![VPN config connect on demand](images/ios-vpn-config.png)</span></span>

> [!NOTE]
> <span data-ttu-id="c2557-128">La protección web no estará disponible cuando la VPN esté deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="c2557-128">Web Protection will not be available when VPN is disabled.</span></span> <span data-ttu-id="c2557-129">Para volver a habilitar Protección web, abra la aplicación Microsoft Defender para endpoint en el dispositivo y haga clic o pulse **Iniciar VPN**.</span><span class="sxs-lookup"><span data-stu-id="c2557-129">To re-enable Web Protection, open the Microsoft Defender for Endpoint app on the device and click or tap **Start VPN**.</span></span>

## <a name="co-existence-of-multiple-vpn-profiles"></a><span data-ttu-id="c2557-130">Coexistencia de varios perfiles vpn</span><span class="sxs-lookup"><span data-stu-id="c2557-130">Co-existence of multiple VPN profiles</span></span>

<span data-ttu-id="c2557-131">Apple iOS no admite varias VPN de todo el dispositivo para estar activas simultáneamente.</span><span class="sxs-lookup"><span data-stu-id="c2557-131">Apple iOS does not support multiple device-wide VPNs to be active simultaneously.</span></span> <span data-ttu-id="c2557-132">Aunque pueden existir varios perfiles de VPN en el dispositivo, solo una VPN puede estar activa a la vez.</span><span class="sxs-lookup"><span data-stu-id="c2557-132">While multiple VPN profiles can exist on the device, only one VPN can be active at a time.</span></span>


## <a name="configure-compliance-policy-against-jailbroken-devices"></a><span data-ttu-id="c2557-133">Configurar la directiva de cumplimiento en dispositivos con jailbreak</span><span class="sxs-lookup"><span data-stu-id="c2557-133">Configure compliance policy against jailbroken devices</span></span>

<span data-ttu-id="c2557-134">Para proteger los datos corporativos de acceso en dispositivos iOS con jailbreak, le recomendamos que configure la siguiente directiva de cumplimiento en Intune.</span><span class="sxs-lookup"><span data-stu-id="c2557-134">To protect corporate data from being accessed on jailbroken iOS devices, we recommend that you set up the following compliance policy on Intune.</span></span>

> [!NOTE]
> <span data-ttu-id="c2557-135">En este momento, Microsoft Defender para Endpoint para iOS no proporciona protección contra escenarios de jailbreak.</span><span class="sxs-lookup"><span data-stu-id="c2557-135">At this time Microsoft Defender for Endpoint for iOS does not provide protection against jailbreak scenarios.</span></span> <span data-ttu-id="c2557-136">Si se usa en un dispositivo con jailbreak, en escenarios específicos, los datos que usa la aplicación como el identificador de correo electrónico corporativo y la imagen de perfil corporativo (si está disponible) se pueden exponer localmente</span><span class="sxs-lookup"><span data-stu-id="c2557-136">If used on a jailbroken device, then in specific scenarios data that is used by the application like your corporate email id and corporate profile picture (if available) can be exposed locally</span></span>

<span data-ttu-id="c2557-137">Siga los pasos siguientes para crear una directiva de cumplimiento contra dispositivos con jailbreak.</span><span class="sxs-lookup"><span data-stu-id="c2557-137">Follow the steps below to create a compliance policy against jailbroken devices.</span></span>

1. <span data-ttu-id="c2557-138">En [el Centro de administración de Microsoft Endpoint Manager,](https://go.microsoft.com/fwlink/?linkid=2109431)vaya a Directivas **de** cumplimiento  ->  **de dispositivos** Crear  ->  **directiva**.</span><span class="sxs-lookup"><span data-stu-id="c2557-138">In [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), go to **Devices** -> **Compliance policies** -> **Create Policy**.</span></span> <span data-ttu-id="c2557-139">Seleccione "iOS/iPadOS" como plataforma y haga clic **en Crear**.</span><span class="sxs-lookup"><span data-stu-id="c2557-139">Select "iOS/iPadOS" as platform and click **Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="c2557-140">![Crear directiva](images/ios-jb-policy.png)</span><span class="sxs-lookup"><span data-stu-id="c2557-140">![Create Policy](images/ios-jb-policy.png)</span></span>

2. <span data-ttu-id="c2557-141">Especifique un nombre de la directiva, por ejemplo, "Compliance Policy for Jailbreak".</span><span class="sxs-lookup"><span data-stu-id="c2557-141">Specify a name of the policy, for example "Compliance Policy for Jailbreak".</span></span>
3. <span data-ttu-id="c2557-142">En la página Configuración de cumplimiento, haga clic para expandir **la sección Estado del** dispositivo y haga clic en **Bloquear** para el **campo Dispositivos con jailbreak.**</span><span class="sxs-lookup"><span data-stu-id="c2557-142">In the compliance settings page, click to expand **Device Health** section and click **Block** for **Jailbroken devices** field.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="c2557-143">![Configuración de directiva](images/ios-jb-settings.png)</span><span class="sxs-lookup"><span data-stu-id="c2557-143">![Policy Settings](images/ios-jb-settings.png)</span></span>

4. <span data-ttu-id="c2557-144">En la *sección Acción por* incumplimiento, seleccione las acciones según sus requisitos y seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="c2557-144">In the *Action for noncompliance* section, select the actions as per your requirements and select **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="c2557-145">![Acciones de directiva](images/ios-jb-actions.png)</span><span class="sxs-lookup"><span data-stu-id="c2557-145">![Policy Actions](images/ios-jb-actions.png)</span></span>

5. <span data-ttu-id="c2557-146">En la *sección Asignaciones,* seleccione los grupos de usuarios que desea incluir para esta directiva y, a continuación, **seleccione Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="c2557-146">In the *Assignments* section, select the user groups that you want to include for this policy and then select **Next**.</span></span>
6. <span data-ttu-id="c2557-147">En la **sección Review+Create,** compruebe que toda la información especificada es correcta y, a continuación, **seleccione Crear**.</span><span class="sxs-lookup"><span data-stu-id="c2557-147">In the **Review+Create** section, verify that all the information entered is correct and then select **Create**.</span></span>

## <a name="configure-custom-indicators"></a><span data-ttu-id="c2557-148">Configurar indicadores personalizados</span><span class="sxs-lookup"><span data-stu-id="c2557-148">Configure custom indicators</span></span>

<span data-ttu-id="c2557-149">Defender for Endpoint for iOS permite a los administradores configurar indicadores personalizados en dispositivos iOS.</span><span class="sxs-lookup"><span data-stu-id="c2557-149">Defender for Endpoint for iOS enables admins to configure custom indicators on iOS devices as well.</span></span> <span data-ttu-id="c2557-150">Para obtener más información sobre cómo configurar indicadores personalizados, vea [Administrar indicadores](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-indicators).</span><span class="sxs-lookup"><span data-stu-id="c2557-150">For more information on how to configure custom indicators, see [Manage indicators](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-indicators).</span></span>

> [!NOTE]
> <span data-ttu-id="c2557-151">Defender para endpoint para iOS admite la creación de indicadores personalizados solo para direcciones IP y direcciones URL/dominios.</span><span class="sxs-lookup"><span data-stu-id="c2557-151">Defender for Endpoint for iOS supports creating custom indicators only for IP addresses and URLs/domains.</span></span>

## <a name="report-unsafe-site"></a><span data-ttu-id="c2557-152">Informe de sitio no seguro</span><span class="sxs-lookup"><span data-stu-id="c2557-152">Report unsafe site</span></span>

<span data-ttu-id="c2557-153">Los sitios web de suplantación de identidad suplantan sitios web de confianza con el fin de obtener su información personal o financiera.</span><span class="sxs-lookup"><span data-stu-id="c2557-153">Phishing websites impersonate trustworthy websites for the purpose of obtaining your personal or financial information.</span></span> <span data-ttu-id="c2557-154">Visita la [página Proporcionar comentarios sobre la protección de](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) red si quieres informar de un sitio web que podría ser un sitio de suplantación de identidad.</span><span class="sxs-lookup"><span data-stu-id="c2557-154">Visit the [Provide feedback about network protection](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) page if you want to report a website that could be a phishing site.</span></span>
