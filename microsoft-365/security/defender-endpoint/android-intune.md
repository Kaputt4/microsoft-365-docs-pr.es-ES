---
title: Implementar Microsoft Defender para endpoint en Android con Microsoft Intune
description: Describe cómo implementar Microsoft Defender para Endpoint en Android con Microsoft Intune
keywords: microsoft, defender, atp, mde, android, instalación, implementación, desinstalación,
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 350345acbaadcdd6bc8ef901f03c419a7f8decff
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "51687726"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-android-with-microsoft-intune"></a><span data-ttu-id="19e89-104">Implementar Microsoft Defender para endpoint en Android con Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="19e89-104">Deploy Microsoft Defender for Endpoint on Android with Microsoft Intune</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="19e89-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="19e89-105">**Applies to:**</span></span>
- [<span data-ttu-id="19e89-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="19e89-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="19e89-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="19e89-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="19e89-108">¿Desea experimentar Microsoft Defender para endpoint?</span><span class="sxs-lookup"><span data-stu-id="19e89-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="19e89-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="19e89-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

<span data-ttu-id="19e89-110">Obtenga información sobre cómo implementar Defender para Endpoint para Android en dispositivos inscritos en el Portal de empresa de Intune.</span><span class="sxs-lookup"><span data-stu-id="19e89-110">Learn how to deploy Defender for Endpoint for Android on Intune Company Portal enrolled devices.</span></span> <span data-ttu-id="19e89-111">Para obtener más información acerca de la inscripción de dispositivos de Intune, consulta  [Inscribir el dispositivo](https://docs.microsoft.com/mem/intune/user-help/enroll-device-android-company-portal).</span><span class="sxs-lookup"><span data-stu-id="19e89-111">For more information about Intune device enrollment, see  [Enroll your device](https://docs.microsoft.com/mem/intune/user-help/enroll-device-android-company-portal).</span></span>

> [!NOTE]
> <span data-ttu-id="19e89-112">**Defender para Endpoint para Android ya está disponible en [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.scmx)**</span><span class="sxs-lookup"><span data-stu-id="19e89-112">**Defender for Endpoint for Android is now available on [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.scmx)**</span></span> <br>
> <span data-ttu-id="19e89-113">Puedes conectarte a Google Play desde Intune para implementar la aplicación Defender for Endpoint en los modos de inscripción administrador de dispositivos y Android Enterprise.</span><span class="sxs-lookup"><span data-stu-id="19e89-113">You can connect to Google Play from Intune to deploy Defender for Endpoint app across Device Administrator and Android Enterprise entrollment modes.</span></span>
<span data-ttu-id="19e89-114">Las actualizaciones de la aplicación son automáticas a través de Google Play.</span><span class="sxs-lookup"><span data-stu-id="19e89-114">Updates to the app are automatic via Google Play.</span></span>

## <a name="deploy-on-device-administrator-enrolled-devices"></a><span data-ttu-id="19e89-115">Implementar en dispositivos inscritos por el administrador de dispositivos</span><span class="sxs-lookup"><span data-stu-id="19e89-115">Deploy on Device Administrator enrolled devices</span></span>

<span data-ttu-id="19e89-116">**Implementar Defender para Endpoint para Android en Intune Company Portal: dispositivos inscritos por el administrador de dispositivos**</span><span class="sxs-lookup"><span data-stu-id="19e89-116">**Deploy Defender for Endpoint for Android on Intune Company Portal - Device Administrator enrolled devices**</span></span>

<span data-ttu-id="19e89-117">Obtenga información sobre cómo implementar Defender for Endpoint para Android en Intune Company Portal: dispositivos inscritos por el administrador de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="19e89-117">Learn how to deploy Defender for Endpoint for Android on Intune Company Portal - Device Administrator enrolled devices.</span></span> 

### <a name="add-as-android-store-app"></a><span data-ttu-id="19e89-118">Agregar como aplicación de la Tienda Android</span><span class="sxs-lookup"><span data-stu-id="19e89-118">Add as Android store app</span></span>

1. <span data-ttu-id="19e89-119">En [el Centro de administración de Microsoft Endpoint Manager,](https://go.microsoft.com/fwlink/?linkid=2109431) ve a **Aplicaciones** \> **Android Apps** Agregar aplicación de la tienda \> **\> Android** y elige **Seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="19e89-119">In [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431) , go to **Apps** \> **Android Apps** \> **Add \> Android store app** and choose **Select**.</span></span>

   ![Imagen del Centro de administración de Microsoft Endpoint Manager agregar aplicación de almacenamiento de Android](images/mda-addandroidstoreapp.png)

2. <span data-ttu-id="19e89-121">En la **página Agregar aplicación** y en la sección Información de *la* aplicación, escriba:</span><span class="sxs-lookup"><span data-stu-id="19e89-121">On the **Add app** page and in the *App Information* section enter:</span></span> 

   - <span data-ttu-id="19e89-122">**Name**</span><span class="sxs-lookup"><span data-stu-id="19e89-122">**Name**</span></span> 
   - <span data-ttu-id="19e89-123">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="19e89-123">**Description**</span></span>
   - <span data-ttu-id="19e89-124">**Publisher** como Microsoft.</span><span class="sxs-lookup"><span data-stu-id="19e89-124">**Publisher** as Microsoft.</span></span>
   - <span data-ttu-id="19e89-125">**Dirección URL de la Tienda de** aplicaciones como https://play.google.com/store/apps/details?id=com.microsoft.scmx (DIRECCIÓN URL de La aplicación Defender para endpoint de Google Play Store)</span><span class="sxs-lookup"><span data-stu-id="19e89-125">**App store URL** as https://play.google.com/store/apps/details?id=com.microsoft.scmx (Defender for Endpoint app Google Play Store URL)</span></span> 

   <span data-ttu-id="19e89-126">Otros campos son opcionales.</span><span class="sxs-lookup"><span data-stu-id="19e89-126">Other fields are optional.</span></span> <span data-ttu-id="19e89-127">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="19e89-127">Select **Next**.</span></span>

   ![Imagen del Centro de administración de Microsoft Endpoint Manager agregar información de la aplicación](images/mda-addappinfo.png)

3. <span data-ttu-id="19e89-129">En la *sección Asignaciones,* vaya a la **sección Obligatorio** y seleccione **Agregar grupo.**</span><span class="sxs-lookup"><span data-stu-id="19e89-129">In the *Assignments* section, go to the **Required** section and select **Add group.**</span></span> <span data-ttu-id="19e89-130">A continuación, puedes elegir los grupos de usuarios a los que te gustaría dirigirte a Defender para endpoint para la aplicación Android.</span><span class="sxs-lookup"><span data-stu-id="19e89-130">You can then choose the user group(s) that you would like to target Defender for Endpoint for Android app.</span></span> <span data-ttu-id="19e89-131">Elija **Seleccionar** y, a **continuación, Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="19e89-131">Choose **Select** and then **Next**.</span></span>

    >[!NOTE]
    ><span data-ttu-id="19e89-132">El grupo de usuarios seleccionado debe estar formado por usuarios inscritos en Intune.</span><span class="sxs-lookup"><span data-stu-id="19e89-132">The selected user group should consist of Intune enrolled users.</span></span>

    > [!div class="mx-imgBorder"]

    > ![Imagen de los grupos de usuarios seleccionados del Centro de administración de Microsoft Endpoint Manager](images/363bf30f7d69a94db578e8af0ddd044b.png)

4. <span data-ttu-id="19e89-134">En la **sección Review+Create,** compruebe que toda la información especificada es correcta y, a continuación, **seleccione Crear**.</span><span class="sxs-lookup"><span data-stu-id="19e89-134">In the **Review+Create** section, verify that all the information entered is correct and then select **Create**.</span></span>

    <span data-ttu-id="19e89-135">En unos instantes, la aplicación Defender for Endpoint se crearía correctamente y se mostraría una notificación en la esquina superior derecha de la página.</span><span class="sxs-lookup"><span data-stu-id="19e89-135">In a few moments, the Defender for Endpoint app would be created successfully, and a notification would show up at the top-right corner of the page.</span></span>

    ![Imagen de la notificación del Centro de administración de Microsoft Endpoint Manager de la aplicación de punto de conexión de defender](images/86cbe56f88bb6e93e9c63303397fc24f.png)

5. <span data-ttu-id="19e89-137">En la página de información de la aplicación  que se muestra, en la sección **Supervisar,** seleccione Estado de instalación del dispositivo para comprobar que la instalación del dispositivo se ha completado correctamente.</span><span class="sxs-lookup"><span data-stu-id="19e89-137">In the app information page that is displayed, in the **Monitor** section, select **Device install status** to verify that the device installation has completed successfully.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="19e89-138">![Imagen de instalación del dispositivo del Centro de administración de Microsoft Endpoint Manager](images/513cf5d59eaaef5d2b5bc122715b5844.png)</span><span class="sxs-lookup"><span data-stu-id="19e89-138">![Image of Microsoft Endpoint Manager Admin Center device install](images/513cf5d59eaaef5d2b5bc122715b5844.png)</span></span>

### <a name="complete-onboarding-and-check-status"></a><span data-ttu-id="19e89-139">Completar la incorporación y comprobar el estado</span><span class="sxs-lookup"><span data-stu-id="19e89-139">Complete onboarding and check status</span></span>

1. <span data-ttu-id="19e89-140">Una vez que Defender para Endpoint para Android se haya instalado en el dispositivo, verás el icono de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="19e89-140">Once Defender for Endpoint for Android has been installed on the device, you'll see the app icon.</span></span>

    ![Icono en el dispositivo móvil](images/7cf9311ad676ec5142002a4d0c2323ca.jpg)

2. <span data-ttu-id="19e89-142">Pulsa el icono de la aplicación atp de Microsoft Defender y sigue las instrucciones en pantalla para completar la incorporación de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="19e89-142">Tap the Microsoft Defender ATP app icon and follow the on-screen instructions to complete onboarding the app.</span></span> <span data-ttu-id="19e89-143">Los detalles incluyen la aceptación por parte del usuario final de los permisos de Android requeridos por Defender para Endpoint para Android.</span><span class="sxs-lookup"><span data-stu-id="19e89-143">The details include end-user acceptance of Android permissions required by Defender for Endpoint for Android.</span></span>

3. <span data-ttu-id="19e89-144">Tras la incorporación correcta, el dispositivo empezará a aparecer en la lista dispositivos del Centro de seguridad de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="19e89-144">Upon successful onboarding, the device will start showing up on the Devices list in Microsoft Defender Security Center.</span></span>

    ![Imagen del dispositivo en defender para el portal de punto de conexión](images/9fe378a1dce0f143005c3aa53d8c4f51.png)

## <a name="deploy-on-android-enterprise-enrolled-devices"></a><span data-ttu-id="19e89-146">Implementar en dispositivos inscritos en Android Enterprise</span><span class="sxs-lookup"><span data-stu-id="19e89-146">Deploy on Android Enterprise enrolled devices</span></span>

<span data-ttu-id="19e89-147">Defender para Endpoint para Android admite dispositivos inscritos en Android Enterprise.</span><span class="sxs-lookup"><span data-stu-id="19e89-147">Defender for Endpoint for Android supports Android Enterprise enrolled devices.</span></span>

<span data-ttu-id="19e89-148">Para obtener más información sobre las opciones de inscripción admitidas por Intune, vea [Opciones de inscripción](https://docs.microsoft.com/mem/intune/enrollment/android-enroll).</span><span class="sxs-lookup"><span data-stu-id="19e89-148">For more information on the enrollment options supported by Intune, see [Enrollment Options](https://docs.microsoft.com/mem/intune/enrollment/android-enroll).</span></span>

<span data-ttu-id="19e89-149">**Actualmente, los dispositivos de propiedad personal con perfil de trabajo y las inscripciones de dispositivos de usuario totalmente administrados de propiedad corporativa se admiten para la implementación.**</span><span class="sxs-lookup"><span data-stu-id="19e89-149">**Currently, Personally owned devices with work profile and Corporate-owned fully managed user device enrollments are supported for deployment.**</span></span>

## <a name="add-microsoft-defender-for-endpoint-on-android-as-a-managed-google-play-app"></a><span data-ttu-id="19e89-150">Agregar Microsoft Defender para endpoint en Android como una aplicación administrada de Google Play</span><span class="sxs-lookup"><span data-stu-id="19e89-150">Add Microsoft Defender for Endpoint on Android as a Managed Google Play app</span></span>

<span data-ttu-id="19e89-151">Sigue los pasos siguientes para agregar la aplicación Microsoft Defender para endpoint a tu Google Play administrado.</span><span class="sxs-lookup"><span data-stu-id="19e89-151">Follow the steps below to add Microsoft Defender for Endpoint app into your managed Google Play.</span></span>

1. <span data-ttu-id="19e89-152">En [el Centro de administración de Microsoft Endpoint Manager,](https://go.microsoft.com/fwlink/?linkid=2109431) ve a **Aplicaciones** para Agregar \> **aplicaciones android** y selecciona Aplicación administrada de Google \>  **Play.**</span><span class="sxs-lookup"><span data-stu-id="19e89-152">In [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431) , go to **Apps** \> **Android Apps** \> **Add** and select **Managed Google Play app**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="19e89-153">![Imagen del Centro de administración de Microsoft Endpoint Manager administrado google play](images/579ff59f31f599414cedf63051628b2e.png)</span><span class="sxs-lookup"><span data-stu-id="19e89-153">![Image of Microsoft Endpoint Manager admin center managed google play](images/579ff59f31f599414cedf63051628b2e.png)</span></span>

2. <span data-ttu-id="19e89-154">En la página administrada de Google Play que se carga posteriormente, ve al cuadro de búsqueda y busca **Microsoft Defender.**</span><span class="sxs-lookup"><span data-stu-id="19e89-154">On your managed Google Play page that loads subsequently, go to the search box and lookup **Microsoft Defender.**</span></span> <span data-ttu-id="19e89-155">La búsqueda debe mostrar la aplicación Microsoft Defender para endpoint en tu Google Play administrado.</span><span class="sxs-lookup"><span data-stu-id="19e89-155">Your search should display the Microsoft Defender for Endpoint app in your Managed Google Play.</span></span> <span data-ttu-id="19e89-156">Haz clic en la aplicación Microsoft Defender para endpoint desde el resultado de la búsqueda Aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="19e89-156">Click on the Microsoft Defender for Endpoint app from the Apps search result.</span></span>

    ![Imagen del Centro de administración de Microsoft Endpoint Manager Búsqueda de aplicaciones](images/0f79cb37900b57c3e2bb0effad1c19cb.png)

3. <span data-ttu-id="19e89-158">En la página Descripción de la aplicación que aparece a continuación, deberías poder ver los detalles de la aplicación en Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="19e89-158">In the App description page that comes up next, you should be able to see app details on Defender for Endpoint.</span></span> <span data-ttu-id="19e89-159">Revise la información de la página y, a continuación, seleccione **Aprobar**.</span><span class="sxs-lookup"><span data-stu-id="19e89-159">Review the information on the page and then select **Approve**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="19e89-160">![Captura de pantalla de un Google Play administrado](images/07e6d4119f265037e3b80a20a73b856f.png)</span><span class="sxs-lookup"><span data-stu-id="19e89-160">![A screenshot of a Managed Google Play](images/07e6d4119f265037e3b80a20a73b856f.png)</span></span>

4. <span data-ttu-id="19e89-161">Se te mostrarán los permisos que Defender for Endpoint obtiene para que funcione.</span><span class="sxs-lookup"><span data-stu-id="19e89-161">You'll be presented with the permissions that Defender for Endpoint obtains for it to work.</span></span> <span data-ttu-id="19e89-162">Repase y, a continuación, **seleccione Aprobar**.</span><span class="sxs-lookup"><span data-stu-id="19e89-162">Review them and then select **Approve**.</span></span>

    ![Una captura de pantalla de la aprobación de la aplicación de vista previa de Defender for Endpoint](images/206b3d954f06cc58b3466fb7a0bd9f74.png)

5. <span data-ttu-id="19e89-164">Se le mostrará la página Configuración de aprobación.</span><span class="sxs-lookup"><span data-stu-id="19e89-164">You'll be presented with the Approval settings page.</span></span> <span data-ttu-id="19e89-165">La página confirma tu preferencia para controlar los nuevos permisos de la aplicación que Defender for Endpoint para Android podría pedir.</span><span class="sxs-lookup"><span data-stu-id="19e89-165">The page confirms your preference to handle new app permissions that Defender for Endpoint for Android might ask.</span></span> <span data-ttu-id="19e89-166">Revisa las opciones y selecciona la opción preferida.</span><span class="sxs-lookup"><span data-stu-id="19e89-166">Review the choices and select your preferred option.</span></span> <span data-ttu-id="19e89-167">Seleccione **Listo**.</span><span class="sxs-lookup"><span data-stu-id="19e89-167">Select **Done**.</span></span>

    <span data-ttu-id="19e89-168">De forma predeterminada, Google Play administrado selecciona Mantener aprobado cuando *la aplicación solicita nuevos permisos*</span><span class="sxs-lookup"><span data-stu-id="19e89-168">By default, managed Google Play selects *Keep approved when app requests new permissions*</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="19e89-169">![Imagen de la pestaña notificaciones](images/ffecfdda1c4df14148f1526c22cc0236.png)</span><span class="sxs-lookup"><span data-stu-id="19e89-169">![Image of notifications tab](images/ffecfdda1c4df14148f1526c22cc0236.png)</span></span>

6. <span data-ttu-id="19e89-170">Después de realizar la selección de control de permisos, selecciona **Sincronizar** para sincronizar Microsoft Defender para Endpoint con la lista de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="19e89-170">After the permissions handling selection is made, select **Sync** to sync Microsoft Defender for Endpoint to your apps list.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="19e89-171">![Imagen de la página de sincronización](images/34e6b9a0dae125d085c84593140180ed.png)</span><span class="sxs-lookup"><span data-stu-id="19e89-171">![Image of sync page](images/34e6b9a0dae125d085c84593140180ed.png)</span></span>

7. <span data-ttu-id="19e89-172">La sincronización se completará en unos minutos.</span><span class="sxs-lookup"><span data-stu-id="19e89-172">The sync will complete in a few minutes.</span></span>

    ![Imagen de la aplicación Android](images/9fc07ffc150171f169dc6e57fe6f1c74.png)

8. <span data-ttu-id="19e89-174">Selecciona el **botón** Actualizar en la pantalla Aplicaciones de Android y ATP de Microsoft Defender debe estar visible en la lista de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="19e89-174">Select the **Refresh** button in the Android apps screen and Microsoft Defender ATP should be visible in the apps list.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="19e89-175">![Imagen de la lista de aplicaciones de Android](images/fa4ac18a6333335db3775630b8e6b353.png)</span><span class="sxs-lookup"><span data-stu-id="19e89-175">![Image of list of Android apps](images/fa4ac18a6333335db3775630b8e6b353.png)</span></span>

9. <span data-ttu-id="19e89-176">Defender for Endpoint admite directivas de configuración de aplicaciones para dispositivos administrados a través de Intune.</span><span class="sxs-lookup"><span data-stu-id="19e89-176">Defender for Endpoint supports App configuration policies for managed devices via Intune.</span></span> <span data-ttu-id="19e89-177">Esta funcionalidad se puede aprovechar para aplicar automáticamente los permisos de Android aplicables, por lo que el usuario final no necesita aceptar estos permisos.</span><span class="sxs-lookup"><span data-stu-id="19e89-177">This capability can be leveraged to autogrant applicable Android permission(s), so the end user does not need to accept these permission(s).</span></span>

    1. <span data-ttu-id="19e89-178">En la **página Aplicaciones,** vaya a Directiva > de configuración de **aplicaciones > Agregar > dispositivos administrados.**</span><span class="sxs-lookup"><span data-stu-id="19e89-178">In the **Apps** page, go to **Policy > App configuration policies > Add > Managed devices**.</span></span>

       ![Imagen de dispositivos administrados android del Centro de administración de Microsoft Endpoint Manager](images/android-mem.png)

    1. <span data-ttu-id="19e89-180">En la **página Crear directiva de configuración de aplicaciones,** escriba los siguientes detalles:</span><span class="sxs-lookup"><span data-stu-id="19e89-180">In the **Create app configuration policy** page, enter the following details:</span></span>
    
        - <span data-ttu-id="19e89-181">Nombre: ATP de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="19e89-181">Name: Microsoft Defender ATP.</span></span>
        - <span data-ttu-id="19e89-182">Elija **Android Enterprise** como plataforma.</span><span class="sxs-lookup"><span data-stu-id="19e89-182">Choose **Android Enterprise** as platform.</span></span>
        - <span data-ttu-id="19e89-183">Elija **Perfil de trabajo solo** como Tipo de perfil.</span><span class="sxs-lookup"><span data-stu-id="19e89-183">Choose **Work Profile only** as Profile Type.</span></span>
        - <span data-ttu-id="19e89-184">Haga **clic en Seleccionar aplicación,** elija ATP de Microsoft **Defender,** **seleccione Aceptar** y, a continuación, **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="19e89-184">Click **Select App**, choose **Microsoft Defender ATP**, select **OK** and then **Next**.</span></span>
    
        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="19e89-185">![Imagen de la página crear directiva de configuración de aplicaciones](images/android-create-app.png)</span><span class="sxs-lookup"><span data-stu-id="19e89-185">![Image of create app configuration policy page](images/android-create-app.png)</span></span>

    1. <span data-ttu-id="19e89-186">En la **página Configuración,** vaya a la sección Permisos haga clic en Agregar para ver la lista de permisos admitidos.</span><span class="sxs-lookup"><span data-stu-id="19e89-186">In the **Settings** page, go to the Permissions section click on Add to view the list of supported permissions.</span></span> <span data-ttu-id="19e89-187">En la sección Agregar permisos, seleccione los siguientes permisos:</span><span class="sxs-lookup"><span data-stu-id="19e89-187">In the Add Permissions section, select the following permissions:</span></span>

       - <span data-ttu-id="19e89-188">Almacenamiento externo (lectura)</span><span class="sxs-lookup"><span data-stu-id="19e89-188">External storage (read)</span></span>
       - <span data-ttu-id="19e89-189">Almacenamiento externo (escritura)</span><span class="sxs-lookup"><span data-stu-id="19e89-189">External storage (write)</span></span>

       <span data-ttu-id="19e89-190">A continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="19e89-190">Then select **OK**.</span></span>

       > [!div class="mx-imgBorder"]
      > <span data-ttu-id="19e89-191">![Imagen de la directiva de configuración de la aplicación de creación de aplicaciones de Android](images/android-create-app-config.png)</span><span class="sxs-lookup"><span data-stu-id="19e89-191">![Image of android create app configuration policy](images/android-create-app-config.png)</span></span>

    1. <span data-ttu-id="19e89-192">Ahora debería ver los dos permisos enumerados y ahora puede autograntar  eligiendo autogrant en la lista desplegable Estado de permisos y, a continuación, **seleccione Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="19e89-192">You should now see both the permissions listed and now you can autogrant both by choosing autogrant in the **Permission state** drop-down and then select **Next**.</span></span>

       > [!div class="mx-imgBorder"]
       > <span data-ttu-id="19e89-193">![Imagen de la directiva de configuración de creación automática de aplicaciones de Android](images/android-auto-grant.png)</span><span class="sxs-lookup"><span data-stu-id="19e89-193">![Image of android auto grant create app configuration policy](images/android-auto-grant.png)</span></span>

    1. <span data-ttu-id="19e89-194">En la **página Asignaciones,** seleccione el grupo de usuarios al que se asignaría esta directiva de configuración de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="19e89-194">In the **Assignments** page, select the user group to which this app config policy would be assigned to.</span></span> <span data-ttu-id="19e89-195">Haga **clic en Seleccionar grupos para** incluir y seleccionar el grupo aplicable y, a continuación, seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="19e89-195">Click **Select groups to include** and selecting the applicable group and then selecting **Next**.</span></span>  <span data-ttu-id="19e89-196">El grupo seleccionado aquí suele ser el mismo grupo al que asignaría Microsoft Defender para la aplicación Android de punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="19e89-196">The group selected here is usually the same group to which you would assign Microsoft Defender for Endpoint Android app.</span></span> 

       > [!div class="mx-imgBorder"]
       > <span data-ttu-id="19e89-197">![Imagen de la directiva de configuración de la aplicación de creación](images/android-select-group.png)</span><span class="sxs-lookup"><span data-stu-id="19e89-197">![Image of the create app configuration policy](images/android-select-group.png)</span></span>
    

     1. <span data-ttu-id="19e89-198">En la **página Revisar + Crear** que aparece a continuación, revise toda la información y, a continuación, seleccione **Crear**.</span><span class="sxs-lookup"><span data-stu-id="19e89-198">In the **Review + Create** page that comes up next, review all the information and then select **Create**.</span></span> <br>
    
        <span data-ttu-id="19e89-199">La directiva de configuración de la aplicación para Defender for Endpoint autogranting the storage permission is now assigned to the selected user group.</span><span class="sxs-lookup"><span data-stu-id="19e89-199">The app configuration policy for Defender for Endpoint autogranting the storage permission is now assigned to the selected user group.</span></span>

        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="19e89-200">![Imagen de la revisión de Android crear directiva de configuración de aplicaciones](images/android-review-create.png)</span><span class="sxs-lookup"><span data-stu-id="19e89-200">![Image of android review create app config policy](images/android-review-create.png)</span></span>


10. <span data-ttu-id="19e89-201">Selecciona **Aplicación ATP de Microsoft Defender** en la lista \> **Propiedades** \> **Asignaciones** \> **Editar**.</span><span class="sxs-lookup"><span data-stu-id="19e89-201">Select **Microsoft Defender ATP** app in the list \> **Properties** \> **Assignments** \> **Edit**.</span></span>

    ![Imagen de la lista de aplicaciones](images/mda-properties.png)


11. <span data-ttu-id="19e89-203">Asigna la aplicación como *una aplicación* necesaria a un grupo de usuarios.</span><span class="sxs-lookup"><span data-stu-id="19e89-203">Assign the app as a *Required* app to a user group.</span></span> <span data-ttu-id="19e89-204">Se instala automáticamente en el perfil de trabajo *durante* la próxima sincronización del dispositivo a través de la aplicación Portal de empresa.</span><span class="sxs-lookup"><span data-stu-id="19e89-204">It is automatically installed in the *work profile* during the next sync of the device via Company Portal app.</span></span> <span data-ttu-id="19e89-205">Para realizar esta asignación, vaya a la *sección* Obligatorio Agregar \> **grupo,** seleccione el grupo de usuarios y haga clic en **Seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="19e89-205">This assignment can be done by navigating to the *Required* section \> **Add group,** selecting the user group and click **Select**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="19e89-206">![Imagen de la página de la aplicación de edición](images/ea06643280075f16265a596fb9a96042.png)</span><span class="sxs-lookup"><span data-stu-id="19e89-206">![Image of edit application page](images/ea06643280075f16265a596fb9a96042.png)</span></span>


12. <span data-ttu-id="19e89-207">En la **página Editar aplicación,** revise toda la información especificada anteriormente.</span><span class="sxs-lookup"><span data-stu-id="19e89-207">In the **Edit Application** page, review all the information that was entered above.</span></span> <span data-ttu-id="19e89-208">A **continuación, seleccione Revisar + Guardar** y, a continuación, Vuelva **a** guardar para iniciar la asignación.</span><span class="sxs-lookup"><span data-stu-id="19e89-208">Then select **Review + Save** and then **Save** again to commence assignment.</span></span>

### <a name="auto-setup-of-always-on-vpn"></a><span data-ttu-id="19e89-209">Configuración automática de VPN always-on</span><span class="sxs-lookup"><span data-stu-id="19e89-209">Auto Setup of Always-on VPN</span></span> 
<span data-ttu-id="19e89-210">Defender for Endpoint admite directivas de configuración de dispositivos para dispositivos administrados a través de Intune.</span><span class="sxs-lookup"><span data-stu-id="19e89-210">Defender for Endpoint supports Device configuration policies for managed devices via Intune.</span></span> <span data-ttu-id="19e89-211">Esta funcionalidad se puede aprovechar para la configuración automática de **VPN** siempre en dispositivos inscritos en Android Enterprise, por lo que el usuario final no necesita configurar el servicio VPN durante la incorporación.</span><span class="sxs-lookup"><span data-stu-id="19e89-211">This capability can be leveraged to **Auto setup of Always-on VPN** on Android Enterprise enrolled devices, so the end user does not need to set up VPN service while onboarding.</span></span>
1.  <span data-ttu-id="19e89-212">En Dispositivos, seleccione **Perfiles de configuración**  >  **Crear**  >    >   **restricciones** de dispositivo de selección de plataforma de perfil de Android Enterprise en una de las siguientes opciones, según el tipo de inscripción del dispositivo</span><span class="sxs-lookup"><span data-stu-id="19e89-212">On **Devices**, select **Configuration Profiles** > **Create Profile** > **Platform** > **Android Enterprise** Select **Device restrictions** under one of the following, based on your device enrollment type</span></span> 
- <span data-ttu-id="19e89-213">**Perfil de trabajo totalmente administrado, dedicado y Corporate-Owned trabajo**</span><span class="sxs-lookup"><span data-stu-id="19e89-213">**Fully Managed, Dedicated, and Corporate-Owned Work Profile**</span></span>
- <span data-ttu-id="19e89-214">**Perfil de trabajo de propiedad personal**</span><span class="sxs-lookup"><span data-stu-id="19e89-214">**Personally owned Work Profile**</span></span>

<span data-ttu-id="19e89-215">Seleccione **Crear**.</span><span class="sxs-lookup"><span data-stu-id="19e89-215">Select **Create**.</span></span>
 
   > ![Imagen del perfil de configuración de dispositivos Crear](images/1autosetupofvpn.png)
    
2. <span data-ttu-id="19e89-217">**Configuración** Proporcione un **nombre y** una **descripción para** identificar de forma única el perfil de configuración.</span><span class="sxs-lookup"><span data-stu-id="19e89-217">**Configuration Settings** Provide a **Name** and a **Description** to uniquely identify the configuration profile.</span></span> 

   > ![Imagen del perfil de configuración de dispositivos Nombre y descripción](images/2autosetupofvpn.png)
   
 3. <span data-ttu-id="19e89-219">Seleccione **Conectividad** y configure VPN:</span><span class="sxs-lookup"><span data-stu-id="19e89-219">Select **Connectivity** and configure VPN:</span></span>
- <span data-ttu-id="19e89-220">Habilite **La configuración de VPN siempre** activa un cliente VPN en el perfil de trabajo para conectarse automáticamente y volver a conectarse a la VPN siempre que sea posible.</span><span class="sxs-lookup"><span data-stu-id="19e89-220">Enable **Always-on VPN** Setup a VPN client in the work profile to automatically connect and reconnect to the VPN whenever possible.</span></span> <span data-ttu-id="19e89-221">Solo se puede configurar un cliente VPN para VPN siempre en un dispositivo determinado, por lo que asegúrate de que no se implemente más de una directiva VPN siempre en un solo dispositivo.</span><span class="sxs-lookup"><span data-stu-id="19e89-221">Only one VPN client can be configured for always-on VPN on a given device, so be sure to have no more than one always-on VPN policy deployed to a single device.</span></span> 
- <span data-ttu-id="19e89-222">Seleccione **Custom** in VPN client dropdown list Custom VPN in this case is Defender for Endpoint VPN which is used to provide the Web Protection feature.</span><span class="sxs-lookup"><span data-stu-id="19e89-222">Select **Custom** in VPN client dropdown list Custom VPN in this case is Defender for Endpoint VPN which is used to provide the Web Protection feature.</span></span> 
    > [!NOTE]
    > <span data-ttu-id="19e89-223">La aplicación ATP de Microsoft Defender debe instalarse en el dispositivo del usuario para que funcione la configuración automática de esta VPN.</span><span class="sxs-lookup"><span data-stu-id="19e89-223">Microsoft Defender ATP app must be installed on user’s device, in order to functioning of auto setup of this VPN.</span></span>

- <span data-ttu-id="19e89-224">Escribe **El identificador del paquete** de la aplicación ATP de Microsoft Defender en Google Play Store.</span><span class="sxs-lookup"><span data-stu-id="19e89-224">Enter **Package ID** of the Microsoft Defender ATP app in Google Play store.</span></span> <span data-ttu-id="19e89-225">Para la dirección URL de la aplicación https://play.google.com/store/apps/details?id=com.microsoft.scmx defender, el identificador del paquete **es com.microsoft.scmx**</span><span class="sxs-lookup"><span data-stu-id="19e89-225">For the Defender app URL https://play.google.com/store/apps/details?id=com.microsoft.scmx, Package ID is **com.microsoft.scmx**</span></span>  
- <span data-ttu-id="19e89-226">**Modo de bloqueo** No configurado (predeterminado)</span><span class="sxs-lookup"><span data-stu-id="19e89-226">**Lockdown mode** Not configured (Default)</span></span> 

     ![Imagen de perfil de configuración de dispositivos habilitar VPN siempre activa](images/3autosetupofvpn.png)
   
4. <span data-ttu-id="19e89-228">**Asignación** En la  **página Asignaciones,** seleccione el grupo de usuarios al que se asignaría esta directiva de   configuración de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="19e89-228">**Assignment** In the **Assignments** page, select the user group to which this app config policy would be assigned to.</span></span> <span data-ttu-id="19e89-229">Haga **clic en** Seleccionar grupos para incluir y seleccionar el grupo aplicable y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="19e89-229">Click **Select groups** to include and selecting the applicable group and then click **Next**.</span></span> <span data-ttu-id="19e89-230">El grupo seleccionado aquí suele ser el mismo grupo al que asignaría Microsoft Defender para la aplicación Android de punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="19e89-230">The group selected here is usually the same group to which you would assign Microsoft Defender for Endpoint Android app.</span></span> 

     ![Imagen de la asignación de perfil de configuración de dispositivos](images/4autosetupofvpn.png)

5. <span data-ttu-id="19e89-232">En la **página Revisar + Crear** que aparece a continuación, revise toda la información y, a continuación, seleccione **Crear**.</span><span class="sxs-lookup"><span data-stu-id="19e89-232">In the **Review + Create** page that comes up next, review all the information and then select **Create**.</span></span> <span data-ttu-id="19e89-233">El perfil de configuración del dispositivo ahora se asigna al grupo de usuarios seleccionado.</span><span class="sxs-lookup"><span data-stu-id="19e89-233">The device configuration profile is now assigned to the selected user group.</span></span>    

    ![Imagen del perfil de configuración de dispositivos Revisar y crear](images/5autosetupofvpn.png)

## <a name="complete-onboarding-and-check-status"></a><span data-ttu-id="19e89-235">Completar la incorporación y comprobar el estado</span><span class="sxs-lookup"><span data-stu-id="19e89-235">Complete onboarding and check status</span></span>

1. <span data-ttu-id="19e89-236">Confirme el estado de instalación de Microsoft Defender para Endpoint en Android haciendo clic en **el estado de instalación del dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="19e89-236">Confirm the installation status of Microsoft Defender for Endpoint on Android by clicking on the **Device Install Status**.</span></span> <span data-ttu-id="19e89-237">Comprueba que el dispositivo se muestra aquí.</span><span class="sxs-lookup"><span data-stu-id="19e89-237">Verify that the device is displayed here.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="19e89-238">![Imagen del estado de instalación del dispositivo](images/900c0197aa59f9b7abd762ab2b32e80c.png)</span><span class="sxs-lookup"><span data-stu-id="19e89-238">![Image of device installation status](images/900c0197aa59f9b7abd762ab2b32e80c.png)</span></span>


2. <span data-ttu-id="19e89-239">En el dispositivo, puedes validar el estado de incorporación yendo al **perfil de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="19e89-239">On the device, you can validate the onboarding status by going to the **work profile**.</span></span> <span data-ttu-id="19e89-240">Confirme que Defender for Endpoint está disponible y que está inscrito en los dispositivos de propiedad **personal con perfil de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="19e89-240">Confirm that Defender for Endpoint is available and that you are enrolled to the **Personally owned devices with work profile**.</span></span>  <span data-ttu-id="19e89-241">Si estás inscrito en un dispositivo de usuario totalmente administrado propiedad de la **empresa,** tendrá un único perfil en el dispositivo donde puedes confirmar que Defender for Endpoint está disponible.</span><span class="sxs-lookup"><span data-stu-id="19e89-241">If you are enrolled to a **Corporate-owned, fully managed user device**, you will have a single profile on the device where you can confirm that Defender for Endpoint is available.</span></span>

    ![Imagen de la aplicación en un dispositivo móvil](images/c2e647fc8fa31c4f2349c76f2497bc0e.png)

3. <span data-ttu-id="19e89-243">Cuando la aplicación esté instalada, abre la aplicación y acepta los permisos y, a continuación, la incorporación debe ser correcta.</span><span class="sxs-lookup"><span data-stu-id="19e89-243">When the app is installed, open the app and accept the permissions and then your onboarding should be successful.</span></span>

    ![Imagen del dispositivo móvil con la aplicación Microsoft Defender para endpoint](images/mda-devicesafe.png)

4. <span data-ttu-id="19e89-245">En esta fase, el dispositivo se incorpora correctamente a Defender para Endpoint para Android.</span><span class="sxs-lookup"><span data-stu-id="19e89-245">At this stage the device is successfully onboarded onto Defender for Endpoint for Android.</span></span> <span data-ttu-id="19e89-246">Para comprobar esto en el Centro de seguridad de [Microsoft Defender,](https://securitycenter.microsoft.com) vaya a la **página Dispositivos.**</span><span class="sxs-lookup"><span data-stu-id="19e89-246">You can verify this on the [Microsoft Defender Security Center](https://securitycenter.microsoft.com) by navigating to the **Devices** page.</span></span>

    ![Imagen del portal de Microsoft Defender para endpoint](images/9fe378a1dce0f143005c3aa53d8c4f51.png)


## <a name="related-topics"></a><span data-ttu-id="19e89-248">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="19e89-248">Related topics</span></span>
- [<span data-ttu-id="19e89-249">Información general sobre Microsoft Defender para endpoint en Android</span><span class="sxs-lookup"><span data-stu-id="19e89-249">Overview of Microsoft Defender for Endpoint on Android</span></span>](microsoft-defender-endpoint-android.md)
- [<span data-ttu-id="19e89-250">Configurar Microsoft Defender para las características de Punto de conexión en Android</span><span class="sxs-lookup"><span data-stu-id="19e89-250">Configure Microsoft Defender for Endpoint on Android features</span></span>](android-configure.md)
