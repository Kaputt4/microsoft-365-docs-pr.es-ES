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
ms.openlocfilehash: a3711018034bcabdde10c21b3c968c3e813d0565
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245262"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-ios"></a><span data-ttu-id="711fb-104">Implementar Microsoft Defender para endpoint en iOS</span><span class="sxs-lookup"><span data-stu-id="711fb-104">Deploy Microsoft Defender for Endpoint on iOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="711fb-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="711fb-105">**Applies to:**</span></span>
- [<span data-ttu-id="711fb-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="711fb-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="711fb-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="711fb-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="711fb-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="711fb-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="711fb-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="711fb-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="711fb-110">En este tema se describe la implementación de Defender for Endpoint en iOS en Portal de empresa de Intune dispositivos inscritos.</span><span class="sxs-lookup"><span data-stu-id="711fb-110">This topic describes deploying Defender for Endpoint on iOS on Intune Company Portal enrolled devices.</span></span> <span data-ttu-id="711fb-111">Para obtener más información acerca de la inscripción de dispositivos de Intune, consulte [Inscribir dispositivos iOS/iPadOS en Intune.](https://docs.microsoft.com/mem/intune/enrollment/ios-enroll)</span><span class="sxs-lookup"><span data-stu-id="711fb-111">For more information about Intune device enrollment, see [Enroll iOS/iPadOS devices in Intune](https://docs.microsoft.com/mem/intune/enrollment/ios-enroll).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="711fb-112">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="711fb-112">Before you begin</span></span>

- <span data-ttu-id="711fb-113">Asegúrese de tener acceso al Centro de administración [de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).</span><span class="sxs-lookup"><span data-stu-id="711fb-113">Ensure you have access to [Microsoft Endpoint manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431).</span></span>

- <span data-ttu-id="711fb-114">Asegúrese de que la inscripción de iOS se realiza para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="711fb-114">Ensure iOS enrollment is done for your users.</span></span> <span data-ttu-id="711fb-115">Los usuarios deben tener asignada una licencia de Defender for Endpoint para poder usar Defender para Endpoint en iOS.</span><span class="sxs-lookup"><span data-stu-id="711fb-115">Users need to have a Defender for Endpoint license assigned in order to use Defender for Endpoint on iOS.</span></span> <span data-ttu-id="711fb-116">Consulte [Asignar licencias a los usuarios para](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign) obtener instrucciones sobre cómo asignar licencias.</span><span class="sxs-lookup"><span data-stu-id="711fb-116">Refer to [Assign licenses to users](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign) for instructions on how to assign licenses.</span></span>

> [!NOTE]
> <span data-ttu-id="711fb-117">Microsoft Defender para endpoint en iOS ya está disponible en [la Tienda de aplicaciones de Apple](https://aka.ms/mdatpiosappstore).</span><span class="sxs-lookup"><span data-stu-id="711fb-117">Microsoft Defender for Endpoint on iOS is now available in the [Apple App Store](https://aka.ms/mdatpiosappstore).</span></span>

## <a name="deployment-steps"></a><span data-ttu-id="711fb-118">Pasos para la implementación</span><span class="sxs-lookup"><span data-stu-id="711fb-118">Deployment steps</span></span>

<span data-ttu-id="711fb-119">Implemente Defender para endpoint en iOS mediante Portal de empresa de Intune.</span><span class="sxs-lookup"><span data-stu-id="711fb-119">Deploy Defender for Endpoint on iOS via Intune Company Portal.</span></span>

### <a name="add-ios-store-app"></a><span data-ttu-id="711fb-120">Agregar aplicación de la tienda iOS</span><span class="sxs-lookup"><span data-stu-id="711fb-120">Add iOS store app</span></span>

1. <span data-ttu-id="711fb-121">En [el Centro de administración de Microsoft Endpoint Manager,](https://go.microsoft.com/fwlink/?linkid=2109431)vaya a **Aplicaciones**  ->  **iOS/iPadOS** Agregar aplicación de la  ->    ->  **tienda iOS** y haga clic en Seleccionar .</span><span class="sxs-lookup"><span data-stu-id="711fb-121">In [Microsoft Endpoint manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), go to **Apps** -> **iOS/iPadOS** -> **Add** -> **iOS store app** and click **Select**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="711fb-122">![Imagen de Microsoft Endpoint Manager Admin Center1](images/ios-deploy-1.png)</span><span class="sxs-lookup"><span data-stu-id="711fb-122">![Image of Microsoft Endpoint Manager Admin Center1](images/ios-deploy-1.png)</span></span>

1. <span data-ttu-id="711fb-123">En la página Agregar aplicación, haga clic en **Buscar en la Tienda de** aplicaciones y escriba Punto de conexión de Microsoft **Defender** en la barra de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="711fb-123">On the Add app page, click on **Search the App Store** and type **Microsoft Defender Endpoint** in the search bar.</span></span> <span data-ttu-id="711fb-124">En la sección resultados de búsqueda, haga clic en *Extremo de Microsoft Defender* y haga clic en **Seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="711fb-124">In the search results section, click on *Microsoft Defender Endpoint* and click **Select**.</span></span>

1. <span data-ttu-id="711fb-125">Seleccione **iOS 11.0** como sistema operativo Mínimo.</span><span class="sxs-lookup"><span data-stu-id="711fb-125">Select **iOS 11.0** as the Minimum operating system.</span></span> <span data-ttu-id="711fb-126">Revisa el resto de información sobre la aplicación y haz clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="711fb-126">Review the rest of information about the app and click **Next**.</span></span>

1. <span data-ttu-id="711fb-127">En la *sección Asignaciones,* vaya a la **sección Obligatorio** y seleccione Agregar **grupo**.</span><span class="sxs-lookup"><span data-stu-id="711fb-127">In the *Assignments* section, go to the **Required** section and select **Add group**.</span></span> <span data-ttu-id="711fb-128">A continuación, puedes elegir los grupos de usuarios a los que quieres dirigirte Defender para Endpoint en la aplicación iOS.</span><span class="sxs-lookup"><span data-stu-id="711fb-128">You can then choose the user group(s) that you would like to target Defender for Endpoint on iOS app.</span></span> <span data-ttu-id="711fb-129">Haga clic **en Seleccionar** y, a **continuación, en Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="711fb-129">Click **Select** and then **Next**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="711fb-130">El grupo de usuarios seleccionado debe estar formado por usuarios inscritos en Intune.</span><span class="sxs-lookup"><span data-stu-id="711fb-130">The selected user group should consist of Intune enrolled users.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="711fb-131">![Imagen de Microsoft Endpoint Manager Admin Center2](images/ios-deploy-2.png)</span><span class="sxs-lookup"><span data-stu-id="711fb-131">![Image of Microsoft Endpoint Manager Admin Center2](images/ios-deploy-2.png)</span></span>

1. <span data-ttu-id="711fb-132">En la *sección Revisar + Crear,* compruebe que toda la información especificada es correcta y, a continuación, **seleccione Crear**.</span><span class="sxs-lookup"><span data-stu-id="711fb-132">In the *Review + Create* section, verify that all the information entered is correct and then select **Create**.</span></span> <span data-ttu-id="711fb-133">En unos instantes, la aplicación Defender for Endpoint debe crearse correctamente y una notificación debe aparecer en la esquina superior derecha de la página.</span><span class="sxs-lookup"><span data-stu-id="711fb-133">In a few moments, the Defender for Endpoint app should be created successfully, and a notification should show up at the top-right corner of the page.</span></span>

1. <span data-ttu-id="711fb-134">En la página de información de la aplicación  que se muestra, en la sección **Supervisar,** seleccione Estado de instalación del dispositivo para comprobar que la instalación del dispositivo se ha completado correctamente.</span><span class="sxs-lookup"><span data-stu-id="711fb-134">In the app information page that is displayed, in the **Monitor** section, select **Device install status** to verify that the device installation has completed successfully.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="711fb-135">![Imagen de Microsoft Endpoint Manager Admin Center3](images/ios-deploy-3.png)</span><span class="sxs-lookup"><span data-stu-id="711fb-135">![Image of Microsoft Endpoint Manager Admin Center3](images/ios-deploy-3.png)</span></span>

## <a name="auto-onboarding-of-vpn-profile-simplified-onboarding"></a><span data-ttu-id="711fb-136">Incorporación automática del perfil vpn (incorporación simplificada)</span><span class="sxs-lookup"><span data-stu-id="711fb-136">Auto-Onboarding of VPN profile (Simplified Onboarding)</span></span>

> [!NOTE]
> <span data-ttu-id="711fb-137">La incorporación automática del perfil VPN está actualmente en versión preliminar y los pasos mencionados en esta sección pueden modificarse considerablemente antes de su lanzamiento comercial.</span><span class="sxs-lookup"><span data-stu-id="711fb-137">Auto-onboarding of VPN profile is currently in preview and the steps mentioned in this section may be substantially modified before it's commercially released.</span></span>

<span data-ttu-id="711fb-138">Los administradores pueden configurar automáticamente el perfil de VPN.</span><span class="sxs-lookup"><span data-stu-id="711fb-138">Admins can configure auto-setup of VPN profile.</span></span> <span data-ttu-id="711fb-139">Esto configurará automáticamente el perfil de DEFENDER para ENDPOINT VPN sin que el usuario lo haga durante la incorporación.</span><span class="sxs-lookup"><span data-stu-id="711fb-139">This will automatically setup the Defender for Endpoint VPN profile without having the user to do so while onboarding.</span></span> <span data-ttu-id="711fb-140">Tenga en cuenta que la VPN se usa para proporcionar la característica de Protección web.</span><span class="sxs-lookup"><span data-stu-id="711fb-140">Note that VPN is used in order to provide the Web Protection feature.</span></span> <span data-ttu-id="711fb-141">No se trata de una VPN normal y es una VPN local o auto-looping que no toma tráfico fuera del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="711fb-141">This is not a regular VPN and is a local/self-looping VPN that does not take traffic outside the device.</span></span>

1. <span data-ttu-id="711fb-142">En [el Centro de administración de Microsoft Endpoint Manager,](https://go.microsoft.com/fwlink/?linkid=2109431)vaya a **Perfiles** de configuración  ->  **de dispositivos** Crear aplicación de  ->    ->  **la tienda iOS** y haga clic **en Seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="711fb-142">In [Microsoft Endpoint manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), go to **Devices** -> **Configuration Profiles** -> **Create** -> **iOS store app** and click **Select**.</span></span>
1. <span data-ttu-id="711fb-143">Elija **Plataforma** como **iOS/iPadOS** y **Tipo de perfil** como **VPN.**</span><span class="sxs-lookup"><span data-stu-id="711fb-143">Choose **Platform** as **iOS/iPadOS** and **Profile type** as **VPN**.</span></span> <span data-ttu-id="711fb-144">Haga clic en **Crear**.</span><span class="sxs-lookup"><span data-stu-id="711fb-144">Click **Create**.</span></span>
1. <span data-ttu-id="711fb-145">Escriba un nombre para el perfil y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="711fb-145">Type a name for the profile and click **Next**.</span></span>
1. <span data-ttu-id="711fb-146">Seleccione **VPN personalizada para** tipo de conexión y, en la sección Vpn **base,** escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="711fb-146">Select **Custom VPN** for Connection Type and in the **Base VPN** section, enter the following:</span></span>
    - <span data-ttu-id="711fb-147">Connection Name = Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="711fb-147">Connection Name = Microsoft Defender for Endpoint</span></span>
    - <span data-ttu-id="711fb-148">Dirección del servidor VPN = 127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="711fb-148">VPN server address = 127.0.0.1</span></span>
    - <span data-ttu-id="711fb-149">Método Auth = "Nombre de usuario y contraseña"</span><span class="sxs-lookup"><span data-stu-id="711fb-149">Auth method = "Username and password"</span></span>
    - <span data-ttu-id="711fb-150">Túnel dividido = Deshabilitar</span><span class="sxs-lookup"><span data-stu-id="711fb-150">Split Tunneling = Disable</span></span>
    - <span data-ttu-id="711fb-151">Identificador de VPN = com.microsoft.scmx</span><span class="sxs-lookup"><span data-stu-id="711fb-151">VPN identifier = com.microsoft.scmx</span></span>
    - <span data-ttu-id="711fb-152">En los pares clave-valor, escriba la clave **AutoOnboard** y establezca el valor en **True**.</span><span class="sxs-lookup"><span data-stu-id="711fb-152">In the key-value pairs, enter the key **AutoOnboard** and set the value to **True**.</span></span>
    - <span data-ttu-id="711fb-153">Tipo de VPN automática = VPN a petición</span><span class="sxs-lookup"><span data-stu-id="711fb-153">Type of Automatic VPN = On-demand VPN</span></span>
    - <span data-ttu-id="711fb-154">Haga **clic en** Agregar para reglas **a** petición y seleccione Quiero hacer lo siguiente = **Establecer VPN**, Quiero restringir a = Todos los **dominios**.</span><span class="sxs-lookup"><span data-stu-id="711fb-154">Click **Add** for **On Demand Rules** and select **I want to do the following = Establish VPN**, **I want to restrict to = All domains**.</span></span>

    ![Captura de pantalla de la configuración de perfil vpn](images/ios-deploy-8.png)

1. <span data-ttu-id="711fb-156">Haga clic en Siguiente y asigne el perfil a los usuarios de destino.</span><span class="sxs-lookup"><span data-stu-id="711fb-156">Click Next and assign the profile to targeted users.</span></span>
1. <span data-ttu-id="711fb-157">En la *sección Revisar + Crear,* compruebe que toda la información especificada es correcta y, a continuación, **seleccione Crear**.</span><span class="sxs-lookup"><span data-stu-id="711fb-157">In the *Review + Create* section, verify that all the information entered is correct and then select **Create**.</span></span>

## <a name="complete-onboarding-and-check-status"></a><span data-ttu-id="711fb-158">Completar la incorporación y comprobar el estado</span><span class="sxs-lookup"><span data-stu-id="711fb-158">Complete onboarding and check status</span></span>

1. <span data-ttu-id="711fb-159">Una vez que Defender para Endpoint en iOS se haya instalado en el dispositivo, verás el icono de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="711fb-159">Once Defender for Endpoint on iOS has been installed on the device, you  will see the app icon.</span></span>

    ![Captura de pantalla de una descripción de teléfono inteligente generada automáticamente](images/41627a709700c324849bf7e13510c516.png)

2. <span data-ttu-id="711fb-161">Pulsa el icono de la aplicación Defender para endpoint y sigue las instrucciones en pantalla para completar los pasos de incorporación.</span><span class="sxs-lookup"><span data-stu-id="711fb-161">Tap the Defender for Endpoint app icon and follow the on-screen instructions to complete the onboarding steps.</span></span> <span data-ttu-id="711fb-162">Los detalles incluyen la aceptación por parte del usuario final de los permisos de iOS requeridos por Defender para endpoint en iOS.</span><span class="sxs-lookup"><span data-stu-id="711fb-162">The details include end-user acceptance of iOS permissions required by Defender for Endpoint on iOS.</span></span>

3. <span data-ttu-id="711fb-163">Tras la incorporación correcta, el dispositivo empezará a aparecer en la lista dispositivos de Centro de seguridad de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="711fb-163">Upon successful onboarding, the device will start showing up on the Devices list in Microsoft Defender Security Center.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="711fb-164">![Captura de pantalla de una descripción de teléfono móvil generada automáticamente](images/e07f270419f7b1e5ee6744f8b38ddeaf.png)</span><span class="sxs-lookup"><span data-stu-id="711fb-164">![A screenshot of a cell phone Description automatically generated](images/e07f270419f7b1e5ee6744f8b38ddeaf.png)</span></span>

## <a name="configure-microsoft-defender-for-endpoint-for-supervised-mode"></a><span data-ttu-id="711fb-165">Configurar Microsoft Defender para el punto de conexión para el modo supervisado</span><span class="sxs-lookup"><span data-stu-id="711fb-165">Configure Microsoft Defender for Endpoint for Supervised Mode</span></span>

<span data-ttu-id="711fb-166">La aplicación Microsoft Defender para endpoint en iOS tiene capacidad especializada en dispositivos iOS/iPadOS supervisados, dadas las capacidades de administración mejoradas que proporciona la plataforma en estos tipos de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="711fb-166">The Microsoft Defender for Endpoint on iOS app has specialized ability on supervised iOS/iPadOS devices, given the increased management capabilities provided by the platform on these types of devices.</span></span> <span data-ttu-id="711fb-167">Para aprovechar estas capacidades, la aplicación Defender for Endpoint debe saber si un dispositivo está en modo supervisado.</span><span class="sxs-lookup"><span data-stu-id="711fb-167">To take advantage of these capabilities, the Defender for Endpoint app needs to know if a device is in Supervised Mode.</span></span>

### <a name="configure-supervised-mode-via-intune"></a><span data-ttu-id="711fb-168">Configurar el modo supervisado a través de Intune</span><span class="sxs-lookup"><span data-stu-id="711fb-168">Configure Supervised Mode via Intune</span></span>

<span data-ttu-id="711fb-169">Intune te permite configurar la aplicación Defender para iOS a través de una directiva de configuración de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="711fb-169">Intune allows you to configure the Defender for iOS app through an App Configuration policy.</span></span>

   > [!NOTE]
   > <span data-ttu-id="711fb-170">Esta directiva de configuración de aplicaciones para dispositivos supervisados solo se aplica a dispositivos administrados y debe estar dirigida a todos los dispositivos iOS administrados como procedimiento recomendado.</span><span class="sxs-lookup"><span data-stu-id="711fb-170">This app configuration policy for supervised devices is applicable only to managed devices and should be targeted for all managed iOS devices as a best practice.</span></span>

1. <span data-ttu-id="711fb-171">Inicie sesión en el Centro [Microsoft Endpoint Manager administración](https://go.microsoft.com/fwlink/?linkid=2109431) y vaya a Directivas de configuración de   >  **aplicaciones**  >  **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="711fb-171">Sign in to the [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431) and go to **Apps** > **App configuration policies** > **Add**.</span></span> <span data-ttu-id="711fb-172">Haga clic en **Dispositivos administrados.**</span><span class="sxs-lookup"><span data-stu-id="711fb-172">Click on **Managed devices**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="711fb-173">![Imagen de Microsoft Endpoint Manager Admin Center4](images/ios-deploy-4.png)</span><span class="sxs-lookup"><span data-stu-id="711fb-173">![Image of Microsoft Endpoint Manager Admin Center4](images/ios-deploy-4.png)</span></span>

1. <span data-ttu-id="711fb-174">En la *página Crear directiva de configuración de aplicaciones,* proporcione la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="711fb-174">In the *Create app configuration policy* page, provide the following information:</span></span>
    - <span data-ttu-id="711fb-175">Nombre de la directiva</span><span class="sxs-lookup"><span data-stu-id="711fb-175">Policy Name</span></span>
    - <span data-ttu-id="711fb-176">Plataforma: seleccione iOS/iPadOS</span><span class="sxs-lookup"><span data-stu-id="711fb-176">Platform: Select iOS/iPadOS</span></span>
    - <span data-ttu-id="711fb-177">Aplicación dirigida: seleccione **ATP de Microsoft Defender** de la lista</span><span class="sxs-lookup"><span data-stu-id="711fb-177">Targeted app: Select **Microsoft Defender ATP** from the list</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="711fb-178">![Imagen de Microsoft Endpoint Manager Admin Center5](images/ios-deploy-5.png)</span><span class="sxs-lookup"><span data-stu-id="711fb-178">![Image of Microsoft Endpoint Manager Admin Center5](images/ios-deploy-5.png)</span></span>

1. <span data-ttu-id="711fb-179">En la siguiente pantalla, seleccione **Usar diseñador de configuraciones** como formato.</span><span class="sxs-lookup"><span data-stu-id="711fb-179">In the next screen, select **Use configuration designer** as the format.</span></span> <span data-ttu-id="711fb-180">Especifique la siguiente propiedad:</span><span class="sxs-lookup"><span data-stu-id="711fb-180">Specify the following property:</span></span>
    - <span data-ttu-id="711fb-181">Clave de configuración: se supervisa</span><span class="sxs-lookup"><span data-stu-id="711fb-181">Configuration Key: issupervised</span></span>
    - <span data-ttu-id="711fb-182">Tipo de valor: String</span><span class="sxs-lookup"><span data-stu-id="711fb-182">Value type: String</span></span>
    - <span data-ttu-id="711fb-183">Valor de configuración: {{issupervised}}</span><span class="sxs-lookup"><span data-stu-id="711fb-183">Configuration Value: {{issupervised}}</span></span>
    
    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="711fb-184">![Imagen de Microsoft Endpoint Manager Admin Center6](images/ios-deploy-6.png)</span><span class="sxs-lookup"><span data-stu-id="711fb-184">![Image of Microsoft Endpoint Manager Admin Center6](images/ios-deploy-6.png)</span></span>

1. <span data-ttu-id="711fb-185">Haga **clic en** Siguiente para abrir la página **Etiquetas de ámbito.**</span><span class="sxs-lookup"><span data-stu-id="711fb-185">Click **Next** to open the **Scope tags** page.</span></span> <span data-ttu-id="711fb-186">Las etiquetas de ámbito son opcionales.</span><span class="sxs-lookup"><span data-stu-id="711fb-186">Scope tags are optional.</span></span> <span data-ttu-id="711fb-187">Haga clic en **Siguiente** para continuar.</span><span class="sxs-lookup"><span data-stu-id="711fb-187">Click **Next** to continue.</span></span>

1. <span data-ttu-id="711fb-188">En la **página Asignaciones,** seleccione los grupos que recibirán este perfil.</span><span class="sxs-lookup"><span data-stu-id="711fb-188">On the **Assignments** page, select the groups that will receive this profile.</span></span> <span data-ttu-id="711fb-189">Para este escenario, es mejor usar todos los dispositivos como **destino.**</span><span class="sxs-lookup"><span data-stu-id="711fb-189">For this scenario, it is best practice to target **All Devices**.</span></span> <span data-ttu-id="711fb-190">Para obtener más información sobre la asignación de perfiles, vea [Asignar perfiles de usuario y dispositivo.](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign)</span><span class="sxs-lookup"><span data-stu-id="711fb-190">For more information on assigning profiles, see [Assign user and device profiles](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign).</span></span>

   <span data-ttu-id="711fb-191">Al implementar en grupos de usuarios, un usuario debe iniciar sesión en un dispositivo antes de que se aplique la directiva.</span><span class="sxs-lookup"><span data-stu-id="711fb-191">When deploying to user groups, a user must sign in to a device before the policy applies.</span></span>

   <span data-ttu-id="711fb-192">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="711fb-192">Click **Next**.</span></span>

1. <span data-ttu-id="711fb-193">En la **página Revisar y crear,** cuando haya terminado, elija **Crear**.</span><span class="sxs-lookup"><span data-stu-id="711fb-193">On the **Review + create** page, when you're done, choose **Create**.</span></span> <span data-ttu-id="711fb-194">El nuevo perfil se muestra en la lista de perfiles de configuración.</span><span class="sxs-lookup"><span data-stu-id="711fb-194">The new profile is displayed in the list of configuration profiles.</span></span>

1. <span data-ttu-id="711fb-195">A continuación, para obtener funcionalidades mejoradas contra la suplantación de identidad, puede implementar un perfil personalizado en los dispositivos iOS supervisados.</span><span class="sxs-lookup"><span data-stu-id="711fb-195">Next, for enhanced Anti-phishing capabilities, you can deploy a custom profile on the supervised iOS devices.</span></span> <span data-ttu-id="711fb-196">Siga los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="711fb-196">Follow the steps below:</span></span>
    - <span data-ttu-id="711fb-197">Descargar el perfil de configuración desde [https://aka.ms/mdatpiossupervisedprofile](https://aka.ms/mdatpiossupervisedprofile)</span><span class="sxs-lookup"><span data-stu-id="711fb-197">Download the config profile from [https://aka.ms/mdatpiossupervisedprofile](https://aka.ms/mdatpiossupervisedprofile)</span></span>
    - <span data-ttu-id="711fb-198">Vaya a  ->  **Dispositivos iOS/iPadOS**  ->  **Configuration profiles**  ->  **Create Profile**</span><span class="sxs-lookup"><span data-stu-id="711fb-198">Navigate to **Devices** -> **iOS/iPadOS** -> **Configuration profiles** -> **Create Profile**</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="711fb-199">![Imagen de Microsoft Endpoint Manager Centro de administración7](images/ios-deploy-7.png)</span><span class="sxs-lookup"><span data-stu-id="711fb-199">![Image of Microsoft Endpoint Manager Admin Center7](images/ios-deploy-7.png)</span></span>

    - <span data-ttu-id="711fb-200">Proporcione un nombre del perfil.</span><span class="sxs-lookup"><span data-stu-id="711fb-200">Provide a name of the profile.</span></span> <span data-ttu-id="711fb-201">Cuando se le pida que importe un archivo de perfil de configuración, seleccione el que se descargó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="711fb-201">When prompted to import a Configuration profile file, select the one downloaded above.</span></span>
    - <span data-ttu-id="711fb-202">En la **sección Asignación,** selecciona el grupo de dispositivos al que quieres aplicar este perfil.</span><span class="sxs-lookup"><span data-stu-id="711fb-202">In the **Assignment** section, select the device group to which you want to apply this profile.</span></span> <span data-ttu-id="711fb-203">Como práctica recomendada, esto debe aplicarse a todos los dispositivos iOS administrados.</span><span class="sxs-lookup"><span data-stu-id="711fb-203">As a best practice, this should be applied to all managed iOS devices.</span></span> <span data-ttu-id="711fb-204">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="711fb-204">Click **Next**.</span></span>
    - <span data-ttu-id="711fb-205">En la **página Revisar y crear,** cuando haya terminado, elija **Crear**.</span><span class="sxs-lookup"><span data-stu-id="711fb-205">On the **Review + create** page, when you're done, choose **Create**.</span></span> <span data-ttu-id="711fb-206">El nuevo perfil se muestra en la lista de perfiles de configuración.</span><span class="sxs-lookup"><span data-stu-id="711fb-206">The new profile is displayed in the list of configuration profiles.</span></span>

## <a name="next-steps"></a><span data-ttu-id="711fb-207">Siguientes pasos</span><span class="sxs-lookup"><span data-stu-id="711fb-207">Next Steps</span></span>

[<span data-ttu-id="711fb-208">Configurar Defender para endpoint en características de iOS</span><span class="sxs-lookup"><span data-stu-id="711fb-208">Configure Defender for Endpoint on iOS features</span></span>](ios-configure-features.md)
