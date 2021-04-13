---
title: Implementación basada en aplicaciones para ATP de Microsoft Defender para iOS
ms.reviewer: ''
description: Describe cómo implementar ATP de Microsoft Defender para iOS con una aplicación
keywords: microsoft, defender, atp, ios, app, installation, deploy, uninstallation, intune
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
ms.openlocfilehash: 6cfd2953e752ed9c96f7f16a3ec7ea1fd8862ab2
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689742"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-ios"></a><span data-ttu-id="0bde8-104">Implementar Microsoft Defender para endpoint en iOS</span><span class="sxs-lookup"><span data-stu-id="0bde8-104">Deploy Microsoft Defender for Endpoint on iOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0bde8-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="0bde8-105">**Applies to:**</span></span>
- [<span data-ttu-id="0bde8-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="0bde8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="0bde8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0bde8-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="0bde8-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="0bde8-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="0bde8-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="0bde8-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="0bde8-110">En este tema se describe la implementación de Defender for Endpoint para iOS en dispositivos inscritos en el Portal de empresa de Intune.</span><span class="sxs-lookup"><span data-stu-id="0bde8-110">This topic describes deploying Defender for Endpoint for iOS on Intune Company Portal enrolled devices.</span></span> <span data-ttu-id="0bde8-111">Para obtener más información acerca de la inscripción de dispositivos de Intune, consulte [Inscribir dispositivos iOS/iPadOS en Intune.](https://docs.microsoft.com/mem/intune/enrollment/ios-enroll)</span><span class="sxs-lookup"><span data-stu-id="0bde8-111">For more information about Intune device enrollment, see [Enroll iOS/iPadOS devices in Intune](https://docs.microsoft.com/mem/intune/enrollment/ios-enroll).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="0bde8-112">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="0bde8-112">Before you begin</span></span>

- <span data-ttu-id="0bde8-113">Asegúrese de tener acceso al Centro de administración [de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).</span><span class="sxs-lookup"><span data-stu-id="0bde8-113">Ensure you have access to [Microsoft Endpoint manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431).</span></span>

- <span data-ttu-id="0bde8-114">Asegúrese de que la inscripción de iOS se realiza para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="0bde8-114">Ensure iOS enrollment is done for your users.</span></span> <span data-ttu-id="0bde8-115">Los usuarios deben tener asignada una licencia de Defender for Endpoint para poder usar Defender para Endpoint para iOS.</span><span class="sxs-lookup"><span data-stu-id="0bde8-115">Users need to have a Defender for Endpoint license assigned in order to use Defender for Endpoint for iOS.</span></span> <span data-ttu-id="0bde8-116">Consulte [Asignar licencias a los usuarios para](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign) obtener instrucciones sobre cómo asignar licencias.</span><span class="sxs-lookup"><span data-stu-id="0bde8-116">Refer to [Assign licenses to users](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign) for instructions on how to assign licenses.</span></span>

> [!NOTE]
> <span data-ttu-id="0bde8-117">Atp de Microsoft Defender (Microsoft Defender para endpoint) para iOS ya está disponible en [la Tienda de aplicaciones de Apple.](https://aka.ms/mdatpiosappstore)</span><span class="sxs-lookup"><span data-stu-id="0bde8-117">Microsoft Defender ATP (Microsoft Defender for Endpoint) for iOS is now available in the [Apple App Store](https://aka.ms/mdatpiosappstore).</span></span>

## <a name="deployment-steps"></a><span data-ttu-id="0bde8-118">Pasos para la implementación</span><span class="sxs-lookup"><span data-stu-id="0bde8-118">Deployment steps</span></span>

<span data-ttu-id="0bde8-119">Implementar Defender para endpoint para iOS a través del Portal de empresa de Intune.</span><span class="sxs-lookup"><span data-stu-id="0bde8-119">Deploy Defender for Endpoint for iOS via Intune Company Portal.</span></span>

### <a name="add-ios-store-app"></a><span data-ttu-id="0bde8-120">Agregar aplicación de la tienda iOS</span><span class="sxs-lookup"><span data-stu-id="0bde8-120">Add iOS store app</span></span>

1. <span data-ttu-id="0bde8-121">En [el Centro de administración de Microsoft Endpoint Manager,](https://go.microsoft.com/fwlink/?linkid=2109431)vaya a **Aplicaciones**  ->  **iOS/iPadOS** Agregar aplicación de la  ->    ->  **tienda iOS** y haga clic en Seleccionar .</span><span class="sxs-lookup"><span data-stu-id="0bde8-121">In [Microsoft Endpoint manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), go to **Apps** -> **iOS/iPadOS** -> **Add** -> **iOS store app** and click **Select**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0bde8-122">![Imagen del Centro de administración de Microsoft Endpoint Manager1](images/ios-deploy-1.png)</span><span class="sxs-lookup"><span data-stu-id="0bde8-122">![Image of Microsoft Endpoint Manager Admin Center1](images/ios-deploy-1.png)</span></span>

1. <span data-ttu-id="0bde8-123">En la página Agregar aplicación, haga clic en **Buscar en la Tienda de** aplicaciones y escriba Punto de conexión de Microsoft **Defender** en la barra de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="0bde8-123">On the Add app page, click on **Search the App Store** and type **Microsoft Defender Endpoint** in the search bar.</span></span> <span data-ttu-id="0bde8-124">En la sección resultados de búsqueda, haga clic en *Extremo de Microsoft Defender* y haga clic en **Seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="0bde8-124">In the search results section, click on *Microsoft Defender Endpoint* and click **Select**.</span></span>

1. <span data-ttu-id="0bde8-125">Seleccione **iOS 11.0** como sistema operativo Mínimo.</span><span class="sxs-lookup"><span data-stu-id="0bde8-125">Select **iOS 11.0** as the Minimum operating system.</span></span> <span data-ttu-id="0bde8-126">Revisa el resto de información sobre la aplicación y haz clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="0bde8-126">Review the rest of information about the app and click **Next**.</span></span>

1. <span data-ttu-id="0bde8-127">En la *sección Asignaciones,* vaya a la **sección Obligatorio** y seleccione Agregar **grupo**.</span><span class="sxs-lookup"><span data-stu-id="0bde8-127">In the *Assignments* section, go to the **Required** section and select **Add group**.</span></span> <span data-ttu-id="0bde8-128">A continuación, puedes elegir los grupos de usuarios a los que quieres dirigirte defender para la aplicación De endpoint para iOS.</span><span class="sxs-lookup"><span data-stu-id="0bde8-128">You can then choose the user group(s) that you would like to target Defender for Endpoint for iOS app.</span></span> <span data-ttu-id="0bde8-129">Haga clic **en Seleccionar** y, a **continuación, en Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="0bde8-129">Click **Select** and then **Next**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0bde8-130">El grupo de usuarios seleccionado debe estar formado por usuarios inscritos en Intune.</span><span class="sxs-lookup"><span data-stu-id="0bde8-130">The selected user group should consist of Intune enrolled users.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0bde8-131">![Imagen del Centro de administración de Microsoft Endpoint Manager2](images/ios-deploy-2.png)</span><span class="sxs-lookup"><span data-stu-id="0bde8-131">![Image of Microsoft Endpoint Manager Admin Center2](images/ios-deploy-2.png)</span></span>

1. <span data-ttu-id="0bde8-132">En la *sección Revisar + Crear,* compruebe que toda la información especificada es correcta y, a continuación, **seleccione Crear**.</span><span class="sxs-lookup"><span data-stu-id="0bde8-132">In the *Review + Create* section, verify that all the information entered is correct and then select **Create**.</span></span> <span data-ttu-id="0bde8-133">En unos instantes, la aplicación Defender for Endpoint debe crearse correctamente y una notificación debe aparecer en la esquina superior derecha de la página.</span><span class="sxs-lookup"><span data-stu-id="0bde8-133">In a few moments, the Defender for Endpoint app should be created successfully, and a notification should show up at the top-right corner of the page.</span></span>

1. <span data-ttu-id="0bde8-134">En la página de información de la aplicación  que se muestra, en la sección **Supervisar,** seleccione Estado de instalación del dispositivo para comprobar que la instalación del dispositivo se ha completado correctamente.</span><span class="sxs-lookup"><span data-stu-id="0bde8-134">In the app information page that is displayed, in the **Monitor** section, select **Device install status** to verify that the device installation has completed successfully.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0bde8-135">![Imagen del Centro de administración de Microsoft Endpoint Manager3](images/ios-deploy-3.png)</span><span class="sxs-lookup"><span data-stu-id="0bde8-135">![Image of Microsoft Endpoint Manager Admin Center3](images/ios-deploy-3.png)</span></span>

## <a name="complete-onboarding-and-check-status"></a><span data-ttu-id="0bde8-136">Completar la incorporación y comprobar el estado</span><span class="sxs-lookup"><span data-stu-id="0bde8-136">Complete onboarding and check status</span></span>

1. <span data-ttu-id="0bde8-137">Una vez que Defender para Endpoint para iOS se haya instalado en el dispositivo, verás el icono de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="0bde8-137">Once Defender for Endpoint for iOS has been installed on the device, you  will see the app icon.</span></span>

    ![Captura de pantalla de una descripción de teléfono inteligente generada automáticamente](images/41627a709700c324849bf7e13510c516.png)

2. <span data-ttu-id="0bde8-139">Pulsa el icono de la aplicación Defender para endpoint y sigue las instrucciones en pantalla para completar los pasos de incorporación.</span><span class="sxs-lookup"><span data-stu-id="0bde8-139">Tap the Defender for Endpoint app icon and follow the on-screen instructions to complete the onboarding steps.</span></span> <span data-ttu-id="0bde8-140">Los detalles incluyen la aceptación por parte del usuario final de los permisos de iOS requeridos por Defender para endpoint para iOS.</span><span class="sxs-lookup"><span data-stu-id="0bde8-140">The details include end-user acceptance of iOS permissions required by Defender for Endpoint for iOS.</span></span>

3. <span data-ttu-id="0bde8-141">Tras la incorporación correcta, el dispositivo empezará a aparecer en la lista dispositivos del Centro de seguridad de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="0bde8-141">Upon successful onboarding, the device will start showing up on the Devices list in Microsoft Defender Security Center.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0bde8-142">![Captura de pantalla de una descripción de teléfono móvil generada automáticamente](images/e07f270419f7b1e5ee6744f8b38ddeaf.png)</span><span class="sxs-lookup"><span data-stu-id="0bde8-142">![A screenshot of a cell phone Description automatically generated](images/e07f270419f7b1e5ee6744f8b38ddeaf.png)</span></span>

## <a name="configure-microsoft-defender-for-endpoint-for-supervised-mode"></a><span data-ttu-id="0bde8-143">Configurar Microsoft Defender para el punto de conexión para el modo supervisado</span><span class="sxs-lookup"><span data-stu-id="0bde8-143">Configure Microsoft Defender for Endpoint for Supervised Mode</span></span>

<span data-ttu-id="0bde8-144">La aplicación Microsoft Defender para endpoint en iOS tiene capacidad especializada en dispositivos iOS/iPadOS supervisados, dadas las capacidades de administración mejoradas que proporciona la plataforma en estos tipos de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="0bde8-144">The Microsoft Defender for Endpoint on iOS app has specialized ability on supervised iOS/iPadOS devices, given the increased management capabilities provided by the platform on these types of devices.</span></span> <span data-ttu-id="0bde8-145">Para aprovechar estas capacidades, la aplicación Defender for Endpoint debe saber si un dispositivo está en modo supervisado.</span><span class="sxs-lookup"><span data-stu-id="0bde8-145">To take advantage of these capabilities, the Defender for Endpoint app needs to know if a device is in Supervised Mode.</span></span>

### <a name="configure-supervised-mode-via-intune"></a><span data-ttu-id="0bde8-146">Configurar el modo supervisado a través de Intune</span><span class="sxs-lookup"><span data-stu-id="0bde8-146">Configure Supervised Mode via Intune</span></span>

<span data-ttu-id="0bde8-147">Intune te permite configurar la aplicación Defender para iOS a través de una directiva de configuración de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="0bde8-147">Intune allows you to configure the Defender for iOS app through an App Configuration policy.</span></span>

   > [!NOTE]
   > <span data-ttu-id="0bde8-148">Esta directiva de configuración de aplicaciones para dispositivos supervisados solo se aplica a dispositivos administrados y debe estar dirigida a todos los dispositivos iOS administrados como procedimiento recomendado.</span><span class="sxs-lookup"><span data-stu-id="0bde8-148">This app configuration policy for supervised devices is applicable only to managed devices and should be targeted for all managed iOS devices as a best practice.</span></span>

1. <span data-ttu-id="0bde8-149">Inicie sesión en el Centro de administración [de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) y vaya a Directivas de configuración de   >  **aplicaciones**  >  **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="0bde8-149">Sign in to the [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431) and go to **Apps** > **App configuration policies** > **Add**.</span></span> <span data-ttu-id="0bde8-150">Haga clic en **Dispositivos administrados.**</span><span class="sxs-lookup"><span data-stu-id="0bde8-150">Click on **Managed devices**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0bde8-151">![Imagen del Centro de administración de Microsoft Endpoint Manager4](images/ios-deploy-4.png)</span><span class="sxs-lookup"><span data-stu-id="0bde8-151">![Image of Microsoft Endpoint Manager Admin Center4](images/ios-deploy-4.png)</span></span>

1. <span data-ttu-id="0bde8-152">En la *página Crear directiva de configuración de aplicaciones,* proporcione la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="0bde8-152">In the *Create app configuration policy* page, provide the following information:</span></span>
    - <span data-ttu-id="0bde8-153">Nombre de la directiva</span><span class="sxs-lookup"><span data-stu-id="0bde8-153">Policy Name</span></span>
    - <span data-ttu-id="0bde8-154">Plataforma: seleccione iOS/iPadOS</span><span class="sxs-lookup"><span data-stu-id="0bde8-154">Platform: Select iOS/iPadOS</span></span>
    - <span data-ttu-id="0bde8-155">Aplicación dirigida: seleccione **ATP de Microsoft Defender** en la lista</span><span class="sxs-lookup"><span data-stu-id="0bde8-155">Targeted app: Select **Microsoft Defender ATP** from the list</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0bde8-156">![Imagen del Centro de administración de Microsoft Endpoint Manager5](images/ios-deploy-5.png)</span><span class="sxs-lookup"><span data-stu-id="0bde8-156">![Image of Microsoft Endpoint Manager Admin Center5](images/ios-deploy-5.png)</span></span>

1. <span data-ttu-id="0bde8-157">En la siguiente pantalla, seleccione **Usar diseñador de configuraciones** como formato.</span><span class="sxs-lookup"><span data-stu-id="0bde8-157">In the next screen, select **Use configuration designer** as the format.</span></span> <span data-ttu-id="0bde8-158">Especifique la siguiente propiedad:</span><span class="sxs-lookup"><span data-stu-id="0bde8-158">Specify the following property:</span></span>
    - <span data-ttu-id="0bde8-159">Clave de configuración: se supervisa</span><span class="sxs-lookup"><span data-stu-id="0bde8-159">Configuration Key: issupervised</span></span>
    - <span data-ttu-id="0bde8-160">Tipo de valor: String</span><span class="sxs-lookup"><span data-stu-id="0bde8-160">Value type: String</span></span>
    - <span data-ttu-id="0bde8-161">Valor de configuración: {{issupervised}}</span><span class="sxs-lookup"><span data-stu-id="0bde8-161">Configuration Value: {{issupervised}}</span></span>
    
    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0bde8-162">![Imagen del Centro de administración de Microsoft Endpoint Manager6](images/ios-deploy-6.png)</span><span class="sxs-lookup"><span data-stu-id="0bde8-162">![Image of Microsoft Endpoint Manager Admin Center6](images/ios-deploy-6.png)</span></span>

1. <span data-ttu-id="0bde8-163">Haga **clic en** Siguiente para abrir la página **Etiquetas de ámbito.**</span><span class="sxs-lookup"><span data-stu-id="0bde8-163">Click **Next** to open the **Scope tags** page.</span></span> <span data-ttu-id="0bde8-164">Las etiquetas de ámbito son opcionales.</span><span class="sxs-lookup"><span data-stu-id="0bde8-164">Scope tags are optional.</span></span> <span data-ttu-id="0bde8-165">Haga clic en **Siguiente** para continuar.</span><span class="sxs-lookup"><span data-stu-id="0bde8-165">Click **Next** to continue.</span></span>

1. <span data-ttu-id="0bde8-166">En la **página Asignaciones,** seleccione los grupos que recibirán este perfil.</span><span class="sxs-lookup"><span data-stu-id="0bde8-166">On the **Assignments** page, select the groups that will receive this profile.</span></span> <span data-ttu-id="0bde8-167">Para este escenario, es mejor usar todos los dispositivos como **destino.**</span><span class="sxs-lookup"><span data-stu-id="0bde8-167">For this scenario, it is best practice to target **All Devices**.</span></span> <span data-ttu-id="0bde8-168">Para obtener más información sobre la asignación de perfiles, vea [Asignar perfiles de usuario y dispositivo.](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign)</span><span class="sxs-lookup"><span data-stu-id="0bde8-168">For more information on assigning profiles, see [Assign user and device profiles](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign).</span></span>

   <span data-ttu-id="0bde8-169">Al implementar en grupos de usuarios, un usuario debe iniciar sesión en un dispositivo antes de que se aplique la directiva.</span><span class="sxs-lookup"><span data-stu-id="0bde8-169">When deploying to user groups, a user must sign in to a device before the policy applies.</span></span>

   <span data-ttu-id="0bde8-170">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="0bde8-170">Click **Next**.</span></span>

1. <span data-ttu-id="0bde8-171">En la **página Revisar y crear,** cuando haya terminado, elija **Crear**.</span><span class="sxs-lookup"><span data-stu-id="0bde8-171">On the **Review + create** page, when you're done, choose **Create**.</span></span> <span data-ttu-id="0bde8-172">El nuevo perfil se muestra en la lista de perfiles de configuración.</span><span class="sxs-lookup"><span data-stu-id="0bde8-172">The new profile is displayed in the list of configuration profiles.</span></span>

1. <span data-ttu-id="0bde8-173">A continuación, para obtener funcionalidades mejoradas contra la suplantación de identidad, puede implementar un perfil personalizado en los dispositivos iOS supervisados.</span><span class="sxs-lookup"><span data-stu-id="0bde8-173">Next, for enhanced Anti-phishing capabilities, you can deploy a custom profile on the supervised iOS devices.</span></span> <span data-ttu-id="0bde8-174">Siga los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="0bde8-174">Follow the steps below:</span></span>
    - <span data-ttu-id="0bde8-175">Descargar el perfil de configuración desde [https://aka.ms/mdatpiossupervisedprofile](https://aka.ms/mdatpiossupervisedprofile)</span><span class="sxs-lookup"><span data-stu-id="0bde8-175">Download the config profile from [https://aka.ms/mdatpiossupervisedprofile](https://aka.ms/mdatpiossupervisedprofile)</span></span>
    - <span data-ttu-id="0bde8-176">Vaya a  ->  **Dispositivos iOS/iPadOS**  ->  **Configuration profiles**  ->  **Create Profile**</span><span class="sxs-lookup"><span data-stu-id="0bde8-176">Navigate to **Devices** -> **iOS/iPadOS** -> **Configuration profiles** -> **Create Profile**</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0bde8-177">![Imagen del Centro de administración de Microsoft Endpoint Manager7](images/ios-deploy-7.png)</span><span class="sxs-lookup"><span data-stu-id="0bde8-177">![Image of Microsoft Endpoint Manager Admin Center7](images/ios-deploy-7.png)</span></span>

    - <span data-ttu-id="0bde8-178">Proporcione un nombre del perfil.</span><span class="sxs-lookup"><span data-stu-id="0bde8-178">Provide a name of the profile.</span></span> <span data-ttu-id="0bde8-179">Cuando se le pida que importe un archivo de perfil de configuración, seleccione el que se descargó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="0bde8-179">When prompted to import a Configuration profile file, select the one downloaded above.</span></span>
    - <span data-ttu-id="0bde8-180">En la **sección Asignación,** selecciona el grupo de dispositivos al que quieres aplicar este perfil.</span><span class="sxs-lookup"><span data-stu-id="0bde8-180">In the **Assignment** section, select the device group to which you want to apply this profile.</span></span> <span data-ttu-id="0bde8-181">Como práctica recomendada, esto debe aplicarse a todos los dispositivos iOS administrados.</span><span class="sxs-lookup"><span data-stu-id="0bde8-181">As a best practice, this should be applied to all managed iOS devices.</span></span> <span data-ttu-id="0bde8-182">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="0bde8-182">Click **Next**.</span></span>
    - <span data-ttu-id="0bde8-183">En la **página Revisar y crear,** cuando haya terminado, elija **Crear**.</span><span class="sxs-lookup"><span data-stu-id="0bde8-183">On the **Review + create** page, when you're done, choose **Create**.</span></span> <span data-ttu-id="0bde8-184">El nuevo perfil se muestra en la lista de perfiles de configuración.</span><span class="sxs-lookup"><span data-stu-id="0bde8-184">The new profile is displayed in the list of configuration profiles.</span></span>

## <a name="next-steps"></a><span data-ttu-id="0bde8-185">Siguientes pasos</span><span class="sxs-lookup"><span data-stu-id="0bde8-185">Next Steps</span></span>

[<span data-ttu-id="0bde8-186">Configurar Defender para endpoint para características de iOS</span><span class="sxs-lookup"><span data-stu-id="0bde8-186">Configure Defender for Endpoint for iOS features</span></span>](ios-configure-features.md)
