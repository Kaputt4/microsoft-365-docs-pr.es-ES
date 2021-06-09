---
title: Implementación basada en aplicaciones para Microsoft Defender para endpoint en iOS
ms.reviewer: ''
description: Describe cómo implementar Microsoft Defender para endpoint en iOS con una aplicación
keywords: microsoft, defender, Microsoft Defender para Endpoint, ios, app, installation, deploy, uninstallation, intune
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
ms.openlocfilehash: 371208433cbb0f65ab5a2808318c03dae6bb6d8b
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842308"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-ios"></a><span data-ttu-id="c120a-104">Implementar Microsoft Defender para endpoint en iOS</span><span class="sxs-lookup"><span data-stu-id="c120a-104">Deploy Microsoft Defender for Endpoint on iOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c120a-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="c120a-105">**Applies to:**</span></span>
- [<span data-ttu-id="c120a-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="c120a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c120a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c120a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="c120a-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="c120a-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="c120a-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="c120a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="c120a-110">En este tema se describe la implementación de Defender for Endpoint en iOS en Portal de empresa de Intune dispositivos inscritos.</span><span class="sxs-lookup"><span data-stu-id="c120a-110">This topic describes deploying Defender for Endpoint on iOS on Intune Company Portal enrolled devices.</span></span> <span data-ttu-id="c120a-111">Para obtener más información acerca de la inscripción de dispositivos de Intune, consulte [Inscribir dispositivos iOS/iPadOS en Intune.](/mem/intune/enrollment/ios-enroll)</span><span class="sxs-lookup"><span data-stu-id="c120a-111">For more information about Intune device enrollment, see [Enroll iOS/iPadOS devices in Intune](/mem/intune/enrollment/ios-enroll).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="c120a-112">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="c120a-112">Before you begin</span></span>

- <span data-ttu-id="c120a-113">Asegúrese de tener acceso al Centro de administración [de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).</span><span class="sxs-lookup"><span data-stu-id="c120a-113">Ensure you have access to [Microsoft Endpoint manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431).</span></span>

- <span data-ttu-id="c120a-114">Asegúrese de que la inscripción de iOS se realiza para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="c120a-114">Ensure iOS enrollment is done for your users.</span></span> <span data-ttu-id="c120a-115">Los usuarios deben tener asignada una licencia de Defender for Endpoint para poder usar Defender para Endpoint en iOS.</span><span class="sxs-lookup"><span data-stu-id="c120a-115">Users need to have a Defender for Endpoint license assigned in order to use Defender for Endpoint on iOS.</span></span> <span data-ttu-id="c120a-116">Consulte [Asignar licencias a los usuarios para](/azure/active-directory/users-groups-roles/licensing-groups-assign) obtener instrucciones sobre cómo asignar licencias.</span><span class="sxs-lookup"><span data-stu-id="c120a-116">Refer to [Assign licenses to users](/azure/active-directory/users-groups-roles/licensing-groups-assign) for instructions on how to assign licenses.</span></span>

> [!NOTE]
> <span data-ttu-id="c120a-117">Microsoft Defender para endpoint en iOS está disponible en [la Tienda de aplicaciones de Apple.](https://aka.ms/mdatpiosappstore)</span><span class="sxs-lookup"><span data-stu-id="c120a-117">Microsoft Defender for Endpoint on iOS is available in the [Apple App Store](https://aka.ms/mdatpiosappstore).</span></span>

## <a name="deployment-steps"></a><span data-ttu-id="c120a-118">Pasos para la implementación</span><span class="sxs-lookup"><span data-stu-id="c120a-118">Deployment steps</span></span>

<span data-ttu-id="c120a-119">Implemente Defender para endpoint en iOS mediante Portal de empresa de Intune.</span><span class="sxs-lookup"><span data-stu-id="c120a-119">Deploy Defender for Endpoint on iOS via Intune Company Portal.</span></span>

### <a name="add-ios-store-app"></a><span data-ttu-id="c120a-120">Agregar aplicación de la tienda iOS</span><span class="sxs-lookup"><span data-stu-id="c120a-120">Add iOS store app</span></span>

1. <span data-ttu-id="c120a-121">En [el Centro de administración de Microsoft Endpoint Manager,](https://go.microsoft.com/fwlink/?linkid=2109431)vaya a **Aplicaciones**  ->  **iOS/iPadOS** Agregar aplicación de la  ->    ->  **tienda iOS** y haga clic en Seleccionar .</span><span class="sxs-lookup"><span data-stu-id="c120a-121">In [Microsoft Endpoint manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), go to **Apps** -> **iOS/iPadOS** -> **Add** -> **iOS store app** and click **Select**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="c120a-122">![Imagen de Microsoft Endpoint Manager Admin Center1](images/ios-deploy-1.png)</span><span class="sxs-lookup"><span data-stu-id="c120a-122">![Image of Microsoft Endpoint Manager Admin Center1](images/ios-deploy-1.png)</span></span>

1. <span data-ttu-id="c120a-123">En la página Agregar aplicación, haga clic en **Buscar en la Tienda de** aplicaciones y escriba Punto de conexión de Microsoft **Defender** en la barra de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="c120a-123">On the Add app page, click on **Search the App Store** and type **Microsoft Defender Endpoint** in the search bar.</span></span> <span data-ttu-id="c120a-124">En la sección resultados de búsqueda, haga clic en *Extremo de Microsoft Defender* y haga clic en **Seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="c120a-124">In the search results section, click on *Microsoft Defender Endpoint* and click **Select**.</span></span>

1. <span data-ttu-id="c120a-125">Seleccione **iOS 11.0** como sistema operativo Mínimo.</span><span class="sxs-lookup"><span data-stu-id="c120a-125">Select **iOS 11.0** as the Minimum operating system.</span></span> <span data-ttu-id="c120a-126">Revisa el resto de información sobre la aplicación y haz clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="c120a-126">Review the rest of information about the app and click **Next**.</span></span>

1. <span data-ttu-id="c120a-127">En la *sección Asignaciones,* vaya a la **sección Obligatorio** y seleccione Agregar **grupo**.</span><span class="sxs-lookup"><span data-stu-id="c120a-127">In the *Assignments* section, go to the **Required** section and select **Add group**.</span></span> <span data-ttu-id="c120a-128">A continuación, puedes elegir los grupos de usuarios a los que quieres dirigirte Defender para Endpoint en la aplicación iOS.</span><span class="sxs-lookup"><span data-stu-id="c120a-128">You can then choose the user group(s) that you would like to target Defender for Endpoint on iOS app.</span></span> <span data-ttu-id="c120a-129">Haga clic **en Seleccionar** y, a **continuación, en Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="c120a-129">Click **Select** and then **Next**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c120a-130">El grupo de usuarios seleccionado debe estar formado por usuarios inscritos en Intune.</span><span class="sxs-lookup"><span data-stu-id="c120a-130">The selected user group should consist of Intune enrolled users.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="c120a-131">![Imagen de Microsoft Endpoint Manager Admin Center2](images/ios-deploy-2.png)</span><span class="sxs-lookup"><span data-stu-id="c120a-131">![Image of Microsoft Endpoint Manager Admin Center2](images/ios-deploy-2.png)</span></span>

1. <span data-ttu-id="c120a-132">En la *sección Revisar + Crear,* compruebe que toda la información especificada es correcta y, a continuación, **seleccione Crear**.</span><span class="sxs-lookup"><span data-stu-id="c120a-132">In the *Review + Create* section, verify that all the information entered is correct and then select **Create**.</span></span> <span data-ttu-id="c120a-133">En unos instantes, la aplicación Defender for Endpoint debe crearse correctamente y una notificación debe aparecer en la esquina superior derecha de la página.</span><span class="sxs-lookup"><span data-stu-id="c120a-133">In a few moments, the Defender for Endpoint app should be created successfully, and a notification should show up at the top-right corner of the page.</span></span>

1. <span data-ttu-id="c120a-134">En la página de información de la aplicación  que se muestra, en la sección **Supervisar,** seleccione Estado de instalación del dispositivo para comprobar que la instalación del dispositivo se ha completado correctamente.</span><span class="sxs-lookup"><span data-stu-id="c120a-134">In the app information page that is displayed, in the **Monitor** section, select **Device install status** to verify that the device installation has completed successfully.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="c120a-135">![Imagen de Microsoft Endpoint Manager Admin Center3](images/ios-deploy-3.png)</span><span class="sxs-lookup"><span data-stu-id="c120a-135">![Image of Microsoft Endpoint Manager Admin Center3](images/ios-deploy-3.png)</span></span>

## <a name="auto-onboarding-of-vpn-profile-simplified-onboarding"></a><span data-ttu-id="c120a-136">Incorporación automática del perfil vpn (incorporación simplificada)</span><span class="sxs-lookup"><span data-stu-id="c120a-136">Auto-Onboarding of VPN profile (Simplified Onboarding)</span></span>

<span data-ttu-id="c120a-137">Los administradores pueden configurar automáticamente el perfil de VPN.</span><span class="sxs-lookup"><span data-stu-id="c120a-137">Admins can configure auto-setup of VPN profile.</span></span> <span data-ttu-id="c120a-138">Esto configurará automáticamente el perfil de DEFENDER para ENDPOINT VPN sin que el usuario lo haga durante la incorporación.</span><span class="sxs-lookup"><span data-stu-id="c120a-138">This will automatically setup the Defender for Endpoint VPN profile without having the user to do so while onboarding.</span></span> <span data-ttu-id="c120a-139">Tenga en cuenta que la VPN se usa para proporcionar la característica de Protección web.</span><span class="sxs-lookup"><span data-stu-id="c120a-139">Note that VPN is used in order to provide the Web Protection feature.</span></span> <span data-ttu-id="c120a-140">No se trata de una VPN normal y es una VPN local o auto-looping que no toma tráfico fuera del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c120a-140">This is not a regular VPN and is a local/self-looping VPN that does not take traffic outside the device.</span></span>

1. <span data-ttu-id="c120a-141">En [el Centro de administración de Microsoft Endpoint Manager,](https://go.microsoft.com/fwlink/?linkid=2109431)vaya a **Perfiles**  ->  **de configuración de dispositivos** Crear  ->  **perfil**.</span><span class="sxs-lookup"><span data-stu-id="c120a-141">In [Microsoft Endpoint manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), go to **Devices** -> **Configuration Profiles** -> **Create Profile**.</span></span>
1. <span data-ttu-id="c120a-142">Elija **Plataforma** como **iOS/iPadOS** y **Tipo de perfil** como **VPN.**</span><span class="sxs-lookup"><span data-stu-id="c120a-142">Choose **Platform** as **iOS/iPadOS** and **Profile type** as **VPN**.</span></span> <span data-ttu-id="c120a-143">Haga clic en **Crear**.</span><span class="sxs-lookup"><span data-stu-id="c120a-143">Click **Create**.</span></span>
1. <span data-ttu-id="c120a-144">Escriba un nombre para el perfil y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="c120a-144">Type a name for the profile and click **Next**.</span></span>
1. <span data-ttu-id="c120a-145">Seleccione **VPN personalizada para** tipo de conexión y, en la sección Vpn **base,** escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c120a-145">Select **Custom VPN** for Connection Type and in the **Base VPN** section, enter the following:</span></span>
    - <span data-ttu-id="c120a-146">Connection Name = Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="c120a-146">Connection Name = Microsoft Defender for Endpoint</span></span>
    - <span data-ttu-id="c120a-147">Dirección del servidor VPN = 127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="c120a-147">VPN server address = 127.0.0.1</span></span>
    - <span data-ttu-id="c120a-148">Método Auth = "Nombre de usuario y contraseña"</span><span class="sxs-lookup"><span data-stu-id="c120a-148">Auth method = "Username and password"</span></span>
    - <span data-ttu-id="c120a-149">Túnel dividido = Deshabilitar</span><span class="sxs-lookup"><span data-stu-id="c120a-149">Split Tunneling = Disable</span></span>
    - <span data-ttu-id="c120a-150">Identificador de VPN = com.microsoft.scmx</span><span class="sxs-lookup"><span data-stu-id="c120a-150">VPN identifier = com.microsoft.scmx</span></span>
    - <span data-ttu-id="c120a-151">En los pares clave-valor, escriba la clave **AutoOnboard** y establezca el valor en **True**.</span><span class="sxs-lookup"><span data-stu-id="c120a-151">In the key-value pairs, enter the key **AutoOnboard** and set the value to **True**.</span></span>
    - <span data-ttu-id="c120a-152">Tipo de VPN automática = VPN a petición</span><span class="sxs-lookup"><span data-stu-id="c120a-152">Type of Automatic VPN = On-demand VPN</span></span>
    - <span data-ttu-id="c120a-153">Haga **clic en** Agregar para reglas **a** petición y seleccione Quiero hacer lo siguiente = **Establecer VPN**, Quiero restringir a = Todos los **dominios**.</span><span class="sxs-lookup"><span data-stu-id="c120a-153">Click **Add** for **On Demand Rules** and select **I want to do the following = Establish VPN**, **I want to restrict to = All domains**.</span></span>

    ![Captura de pantalla de la configuración de perfil vpn](images/ios-deploy-8.png)

1. <span data-ttu-id="c120a-155">Haga clic en Siguiente y asigne el perfil a los usuarios de destino.</span><span class="sxs-lookup"><span data-stu-id="c120a-155">Click Next and assign the profile to targeted users.</span></span>
1. <span data-ttu-id="c120a-156">En la *sección Revisar + Crear,* compruebe que toda la información especificada es correcta y, a continuación, **seleccione Crear**.</span><span class="sxs-lookup"><span data-stu-id="c120a-156">In the *Review + Create* section, verify that all the information entered is correct and then select **Create**.</span></span>

## <a name="complete-onboarding-and-check-status"></a><span data-ttu-id="c120a-157">Completar la incorporación y comprobar el estado</span><span class="sxs-lookup"><span data-stu-id="c120a-157">Complete onboarding and check status</span></span>

1. <span data-ttu-id="c120a-158">Una vez que Defender para Endpoint en iOS se haya instalado en el dispositivo, verás el icono de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="c120a-158">Once Defender for Endpoint on iOS has been installed on the device, you  will see the app icon.</span></span>

    ![Captura de pantalla de una descripción de teléfono inteligente generada automáticamente](images/41627a709700c324849bf7e13510c516.png)

2. <span data-ttu-id="c120a-160">Pulsa el icono de la aplicación Defender para endpoint (MSDefender) y sigue las instrucciones en pantalla para completar los pasos de incorporación.</span><span class="sxs-lookup"><span data-stu-id="c120a-160">Tap the Defender for Endpoint app icon (MSDefender) and follow the on-screen instructions to complete the onboarding steps.</span></span> <span data-ttu-id="c120a-161">Los detalles incluyen la aceptación por parte del usuario final de los permisos de iOS requeridos por Defender para endpoint en iOS.</span><span class="sxs-lookup"><span data-stu-id="c120a-161">The details include end-user acceptance of iOS permissions required by Defender for Endpoint on iOS.</span></span>

3. <span data-ttu-id="c120a-162">Tras la incorporación correcta, el dispositivo empezará a aparecer en la lista dispositivos de Centro de seguridad de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="c120a-162">Upon successful onboarding, the device will start showing up on the Devices list in Microsoft Defender Security Center.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="c120a-163">![Captura de pantalla de una descripción de teléfono móvil generada automáticamente](images/e07f270419f7b1e5ee6744f8b38ddeaf.png)</span><span class="sxs-lookup"><span data-stu-id="c120a-163">![A screenshot of a cell phone Description automatically generated](images/e07f270419f7b1e5ee6744f8b38ddeaf.png)</span></span>

## <a name="configure-microsoft-defender-for-endpoint-for-supervised-mode"></a><span data-ttu-id="c120a-164">Configurar Microsoft Defender para el punto de conexión para el modo supervisado</span><span class="sxs-lookup"><span data-stu-id="c120a-164">Configure Microsoft Defender for Endpoint for Supervised Mode</span></span>

<span data-ttu-id="c120a-165">La aplicación Microsoft Defender para endpoint en iOS tiene capacidad especializada en dispositivos iOS/iPadOS supervisados, dadas las capacidades de administración mejoradas que proporciona la plataforma en estos tipos de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="c120a-165">The Microsoft Defender for Endpoint on iOS app has specialized ability on supervised iOS/iPadOS devices, given the increased management capabilities provided by the platform on these types of devices.</span></span> <span data-ttu-id="c120a-166">Para aprovechar estas capacidades, la aplicación Defender for Endpoint debe saber si un dispositivo está en modo supervisado.</span><span class="sxs-lookup"><span data-stu-id="c120a-166">To take advantage of these capabilities, the Defender for Endpoint app needs to know if a device is in Supervised Mode.</span></span>

### <a name="configure-supervised-mode-via-intune"></a><span data-ttu-id="c120a-167">Configurar el modo supervisado a través de Intune</span><span class="sxs-lookup"><span data-stu-id="c120a-167">Configure Supervised Mode via Intune</span></span>

<span data-ttu-id="c120a-168">Intune te permite configurar la aplicación Defender para iOS a través de una directiva de configuración de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="c120a-168">Intune allows you to configure the Defender for iOS app through an App Configuration policy.</span></span>

   > [!NOTE]
   > <span data-ttu-id="c120a-169">Esta directiva de configuración de aplicaciones para dispositivos supervisados solo se aplica a dispositivos administrados y debe estar dirigida a todos los dispositivos iOS administrados como procedimiento recomendado.</span><span class="sxs-lookup"><span data-stu-id="c120a-169">This app configuration policy for supervised devices is applicable only to managed devices and should be targeted for all managed iOS devices as a best practice.</span></span>

1. <span data-ttu-id="c120a-170">Inicie sesión en el Centro [Microsoft Endpoint Manager administración](https://go.microsoft.com/fwlink/?linkid=2109431) y vaya a Directivas de configuración de   >  **aplicaciones**  >  **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="c120a-170">Sign in to the [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431) and go to **Apps** > **App configuration policies** > **Add**.</span></span> <span data-ttu-id="c120a-171">Haga clic en **Dispositivos administrados.**</span><span class="sxs-lookup"><span data-stu-id="c120a-171">Click on **Managed devices**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="c120a-172">![Imagen de Microsoft Endpoint Manager Admin Center4](images/ios-deploy-4.png)</span><span class="sxs-lookup"><span data-stu-id="c120a-172">![Image of Microsoft Endpoint Manager Admin Center4](images/ios-deploy-4.png)</span></span>

1. <span data-ttu-id="c120a-173">En la *página Crear directiva de configuración de aplicaciones,* proporcione la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="c120a-173">In the *Create app configuration policy* page, provide the following information:</span></span>
    - <span data-ttu-id="c120a-174">Nombre de la directiva</span><span class="sxs-lookup"><span data-stu-id="c120a-174">Policy Name</span></span>
    - <span data-ttu-id="c120a-175">Plataforma: seleccione iOS/iPadOS</span><span class="sxs-lookup"><span data-stu-id="c120a-175">Platform: Select iOS/iPadOS</span></span>
    - <span data-ttu-id="c120a-176">Aplicación dirigida: seleccione Punto de **conexión de Microsoft Defender** en la lista</span><span class="sxs-lookup"><span data-stu-id="c120a-176">Targeted app: Select **Microsoft Defender Endpoint** from the list</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="c120a-177">![Imagen de Microsoft Endpoint Manager Admin Center5](images/ios-deploy-5.png)</span><span class="sxs-lookup"><span data-stu-id="c120a-177">![Image of Microsoft Endpoint Manager Admin Center5](images/ios-deploy-5.png)</span></span>

1. <span data-ttu-id="c120a-178">En la siguiente pantalla, seleccione **Usar diseñador de configuraciones** como formato.</span><span class="sxs-lookup"><span data-stu-id="c120a-178">In the next screen, select **Use configuration designer** as the format.</span></span> <span data-ttu-id="c120a-179">Especifique la siguiente propiedad:</span><span class="sxs-lookup"><span data-stu-id="c120a-179">Specify the following property:</span></span>
    - <span data-ttu-id="c120a-180">Clave de configuración: se supervisa</span><span class="sxs-lookup"><span data-stu-id="c120a-180">Configuration Key: issupervised</span></span>
    - <span data-ttu-id="c120a-181">Tipo de valor: String</span><span class="sxs-lookup"><span data-stu-id="c120a-181">Value type: String</span></span>
    - <span data-ttu-id="c120a-182">Valor de configuración: {{issupervised}}</span><span class="sxs-lookup"><span data-stu-id="c120a-182">Configuration Value: {{issupervised}}</span></span>
    
    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="c120a-183">![Imagen de Microsoft Endpoint Manager Admin Center6](images/ios-deploy-6.png)</span><span class="sxs-lookup"><span data-stu-id="c120a-183">![Image of Microsoft Endpoint Manager Admin Center6](images/ios-deploy-6.png)</span></span>

1. <span data-ttu-id="c120a-184">Haga **clic en** Siguiente para abrir la página **Etiquetas de ámbito.**</span><span class="sxs-lookup"><span data-stu-id="c120a-184">Click **Next** to open the **Scope tags** page.</span></span> <span data-ttu-id="c120a-185">Las etiquetas de ámbito son opcionales.</span><span class="sxs-lookup"><span data-stu-id="c120a-185">Scope tags are optional.</span></span> <span data-ttu-id="c120a-186">Haga clic en **Siguiente** para continuar.</span><span class="sxs-lookup"><span data-stu-id="c120a-186">Click **Next** to continue.</span></span>

1. <span data-ttu-id="c120a-187">En la **página Asignaciones,** seleccione los grupos que recibirán este perfil.</span><span class="sxs-lookup"><span data-stu-id="c120a-187">On the **Assignments** page, select the groups that will receive this profile.</span></span> <span data-ttu-id="c120a-188">Para este escenario, es mejor usar todos los dispositivos como **destino.**</span><span class="sxs-lookup"><span data-stu-id="c120a-188">For this scenario, it is best practice to target **All Devices**.</span></span> <span data-ttu-id="c120a-189">Para obtener más información sobre la asignación de perfiles, vea [Asignar perfiles de usuario y dispositivo.](/mem/intune/configuration/device-profile-assign)</span><span class="sxs-lookup"><span data-stu-id="c120a-189">For more information on assigning profiles, see [Assign user and device profiles](/mem/intune/configuration/device-profile-assign).</span></span>

   <span data-ttu-id="c120a-190">Al implementar en grupos de usuarios, un usuario debe iniciar sesión en un dispositivo antes de que se aplique la directiva.</span><span class="sxs-lookup"><span data-stu-id="c120a-190">When deploying to user groups, a user must sign in to a device before the policy applies.</span></span>

   <span data-ttu-id="c120a-191">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="c120a-191">Click **Next**.</span></span>

1. <span data-ttu-id="c120a-192">En la **página Revisar y crear,** cuando haya terminado, elija **Crear**.</span><span class="sxs-lookup"><span data-stu-id="c120a-192">On the **Review + create** page, when you're done, choose **Create**.</span></span> <span data-ttu-id="c120a-193">El nuevo perfil se muestra en la lista de perfiles de configuración.</span><span class="sxs-lookup"><span data-stu-id="c120a-193">The new profile is displayed in the list of configuration profiles.</span></span>

1. <span data-ttu-id="c120a-194">A continuación, para obtener funcionalidades mejoradas contra la suplantación de identidad, puede implementar un perfil personalizado en los dispositivos iOS supervisados.</span><span class="sxs-lookup"><span data-stu-id="c120a-194">Next, for enhanced Anti-phishing capabilities, you can deploy a custom profile on the supervised iOS devices.</span></span> <span data-ttu-id="c120a-195">Siga los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="c120a-195">Follow the steps below:</span></span>
    - <span data-ttu-id="c120a-196">Descargar el perfil de configuración desde [https://aka.ms/mdatpiossupervisedprofile](https://aka.ms/mdatpiossupervisedprofile)</span><span class="sxs-lookup"><span data-stu-id="c120a-196">Download the config profile from [https://aka.ms/mdatpiossupervisedprofile](https://aka.ms/mdatpiossupervisedprofile)</span></span>
    - <span data-ttu-id="c120a-197">Vaya a  ->  **Dispositivos iOS/iPadOS**  ->  **Configuration profiles**  ->  **Create Profile**</span><span class="sxs-lookup"><span data-stu-id="c120a-197">Navigate to **Devices** -> **iOS/iPadOS** -> **Configuration profiles** -> **Create Profile**</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="c120a-198">![Imagen de Microsoft Endpoint Manager Centro de administración7](images/ios-deploy-7.png)</span><span class="sxs-lookup"><span data-stu-id="c120a-198">![Image of Microsoft Endpoint Manager Admin Center7](images/ios-deploy-7.png)</span></span>

    - <span data-ttu-id="c120a-199">Proporcione un nombre del perfil.</span><span class="sxs-lookup"><span data-stu-id="c120a-199">Provide a name of the profile.</span></span> <span data-ttu-id="c120a-200">Cuando se le pida que importe un archivo de perfil de configuración, seleccione el que se descargó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="c120a-200">When prompted to import a Configuration profile file, select the one downloaded above.</span></span>
    - <span data-ttu-id="c120a-201">En la **sección Asignación,** selecciona el grupo de dispositivos al que quieres aplicar este perfil.</span><span class="sxs-lookup"><span data-stu-id="c120a-201">In the **Assignment** section, select the device group to which you want to apply this profile.</span></span> <span data-ttu-id="c120a-202">Como práctica recomendada, esto debe aplicarse a todos los dispositivos iOS administrados.</span><span class="sxs-lookup"><span data-stu-id="c120a-202">As a best practice, this should be applied to all managed iOS devices.</span></span> <span data-ttu-id="c120a-203">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="c120a-203">Click **Next**.</span></span>
    - <span data-ttu-id="c120a-204">En la **página Revisar y crear,** cuando haya terminado, elija **Crear**.</span><span class="sxs-lookup"><span data-stu-id="c120a-204">On the **Review + create** page, when you're done, choose **Create**.</span></span> <span data-ttu-id="c120a-205">El nuevo perfil se muestra en la lista de perfiles de configuración.</span><span class="sxs-lookup"><span data-stu-id="c120a-205">The new profile is displayed in the list of configuration profiles.</span></span>

## <a name="next-steps"></a><span data-ttu-id="c120a-206">Siguientes pasos</span><span class="sxs-lookup"><span data-stu-id="c120a-206">Next Steps</span></span>

[<span data-ttu-id="c120a-207">Configurar Defender para endpoint en características de iOS</span><span class="sxs-lookup"><span data-stu-id="c120a-207">Configure Defender for Endpoint on iOS features</span></span>](ios-configure-features.md)
