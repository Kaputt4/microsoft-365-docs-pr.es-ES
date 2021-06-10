---
title: Configurar las directivas de Microsoft Defender para endpoint en macOS en Jamf Pro
description: Obtenga información sobre cómo configurar las directivas de Microsoft Defender para endpoint en macOS en Jamf Pro
keywords: policies, microsoft, defender, Microsoft Defender for Endpoint, mac, installation, deploy, uninstallation, intune, jamfpro, macos, catalina, mojave, high sierra
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
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: e26bb85fc74b6be49a9f8116792a7f28e8fa7e05
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842271"
---
# <a name="set-up-the-microsoft-defender-for-endpoint-on-macos-policies-in-jamf-pro"></a><span data-ttu-id="b7027-104">Configurar las directivas de Microsoft Defender para endpoint en macOS en Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="b7027-104">Set up the Microsoft Defender for Endpoint on macOS policies in Jamf Pro</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="b7027-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="b7027-105">**Applies to:**</span></span>

- [<span data-ttu-id="b7027-106">Defender para endpoint en Mac</span><span class="sxs-lookup"><span data-stu-id="b7027-106">Defender for Endpoint on Mac</span></span>](microsoft-defender-endpoint-mac.md)

<span data-ttu-id="b7027-107">Esta página le guiará a través de los pasos que debe seguir para configurar directivas de macOS en Jamf Pro.</span><span class="sxs-lookup"><span data-stu-id="b7027-107">This page will guide you through the steps you need to take to set up macOS policies in Jamf Pro.</span></span>

<span data-ttu-id="b7027-108">Deberá seguir los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="b7027-108">You'll need to take the following steps:</span></span>

1. [<span data-ttu-id="b7027-109">Obtener el paquete de incorporación de Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="b7027-109">Get the Microsoft Defender for Endpoint onboarding package</span></span>](#step-1-get-the-microsoft-defender-for-endpoint-onboarding-package)

2. [<span data-ttu-id="b7027-110">Crear un perfil de configuración en Jamf Pro el paquete de incorporación</span><span class="sxs-lookup"><span data-stu-id="b7027-110">Create a configuration profile in Jamf Pro using the onboarding package</span></span>](#step-2-create-a-configuration-profile-in-jamf-pro-using-the-onboarding-package)

3. [<span data-ttu-id="b7027-111">Configurar Microsoft Defender para la configuración del punto de conexión</span><span class="sxs-lookup"><span data-stu-id="b7027-111">Configure Microsoft Defender for Endpoint settings</span></span>](#step-3-configure-microsoft-defender-for-endpoint-settings)

4. [<span data-ttu-id="b7027-112">Configurar Microsoft Defender para la configuración de notificación de extremo</span><span class="sxs-lookup"><span data-stu-id="b7027-112">Configure Microsoft Defender for Endpoint notification settings</span></span>](#step-4-configure-notifications-settings)

5. [<span data-ttu-id="b7027-113">Configurar Microsoft AutoUpdate (MAU)</span><span class="sxs-lookup"><span data-stu-id="b7027-113">Configure Microsoft AutoUpdate (MAU)</span></span>](#step-5-configure-microsoft-autoupdate-mau)

6. [<span data-ttu-id="b7027-114">Conceder acceso en disco completo a Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="b7027-114">Grant full disk access to Microsoft Defender for Endpoint</span></span>](#step-6-grant-full-disk-access-to-microsoft-defender-for-endpoint)

7. [<span data-ttu-id="b7027-115">Aprobar extensión de kernel para Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="b7027-115">Approve Kernel extension for Microsoft Defender for Endpoint</span></span>](#step-7-approve-kernel-extension-for-microsoft-defender-for-endpoint)

8. [<span data-ttu-id="b7027-116">Aprobar extensiones del sistema para Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="b7027-116">Approve System extensions for Microsoft Defender for Endpoint</span></span>](#step-8-approve-system-extensions-for-microsoft-defender-for-endpoint)

9. [<span data-ttu-id="b7027-117">Configurar extensión de red</span><span class="sxs-lookup"><span data-stu-id="b7027-117">Configure Network Extension</span></span>](#step-9-configure-network-extension)

10. [<span data-ttu-id="b7027-118">Programar exámenes con Microsoft Defender para endpoint en macOS</span><span class="sxs-lookup"><span data-stu-id="b7027-118">Schedule scans with Microsoft Defender for Endpoint on macOS</span></span>](/windows/security/threat-protection/microsoft-defender-atp/mac-schedule-scan-atp)

11. [<span data-ttu-id="b7027-119">Implementar Microsoft Defender para endpoint en macOS</span><span class="sxs-lookup"><span data-stu-id="b7027-119">Deploy Microsoft Defender for Endpoint on macOS</span></span>](#step-11-deploy-microsoft-defender-for-endpoint-on-macos)


## <a name="step-1-get-the-microsoft-defender-for-endpoint-onboarding-package"></a><span data-ttu-id="b7027-120">Paso 1: Obtener el paquete de incorporación de Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="b7027-120">Step 1: Get the Microsoft Defender for Endpoint onboarding package</span></span>

1. <span data-ttu-id="b7027-121">En [Centro de seguridad de Microsoft Defender](https://securitycenter.microsoft.com ), vaya **a Configuración > Onboarding**.</span><span class="sxs-lookup"><span data-stu-id="b7027-121">In [Microsoft Defender Security Center](https://securitycenter.microsoft.com ), navigate to **Settings > Onboarding**.</span></span> 

2. <span data-ttu-id="b7027-122">Seleccione macOS como sistema operativo y Administración de dispositivos móviles /Microsoft Intune como método de implementación.</span><span class="sxs-lookup"><span data-stu-id="b7027-122">Select macOS as the operating system and Mobile Device Management / Microsoft Intune as the deployment method.</span></span>

    ![Imagen de Centro de seguridad de Microsoft Defender](images/onboarding-macos.png)

3. <span data-ttu-id="b7027-124">Seleccione **Descargar paquete de incorporación** (WindowsDefenderATPOnboardingPackage.zip).</span><span class="sxs-lookup"><span data-stu-id="b7027-124">Select **Download onboarding package** (WindowsDefenderATPOnboardingPackage.zip).</span></span>

4. <span data-ttu-id="b7027-125">Extraer `WindowsDefenderATPOnboardingPackage.zip` .</span><span class="sxs-lookup"><span data-stu-id="b7027-125">Extract `WindowsDefenderATPOnboardingPackage.zip`.</span></span>

5. <span data-ttu-id="b7027-126">Copie el archivo en su ubicación preferida.</span><span class="sxs-lookup"><span data-stu-id="b7027-126">Copy the file to your preferred location.</span></span> <span data-ttu-id="b7027-127">Por ejemplo, `C:\Users\JaneDoe_or_JohnDoe.contoso\Downloads\WindowsDefenderATPOnboardingPackage_macOS_MDM_contoso\jamf\WindowsDefenderATPOnboarding.plist`.</span><span class="sxs-lookup"><span data-stu-id="b7027-127">For example,  `C:\Users\JaneDoe_or_JohnDoe.contoso\Downloads\WindowsDefenderATPOnboardingPackage_macOS_MDM_contoso\jamf\WindowsDefenderATPOnboarding.plist`.</span></span>


## <a name="step-2-create-a-configuration-profile-in-jamf-pro-using-the-onboarding-package"></a><span data-ttu-id="b7027-128">Paso 2: Crear un perfil de configuración en Jamf Pro el paquete de incorporación</span><span class="sxs-lookup"><span data-stu-id="b7027-128">Step 2: Create a configuration profile in Jamf Pro using the onboarding package</span></span>

1. <span data-ttu-id="b7027-129">Busque el archivo `WindowsDefenderATPOnboarding.plist` de la sección anterior.</span><span class="sxs-lookup"><span data-stu-id="b7027-129">Locate the file `WindowsDefenderATPOnboarding.plist` from the previous section.</span></span>

   ![Imagen del archivo WindowsDefenderATPOnboarding](images/plist-onboarding-file.png)

 
2. <span data-ttu-id="b7027-131">En el panel de Pro Jamf, seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="b7027-131">In the Jamf Pro dashboard, select **New**.</span></span>

    ![Imagen de creación de un nuevo panel de Pro Jamf](images/jamf-pro-configure-profile.png)

3. <span data-ttu-id="b7027-133">Escriba los siguientes detalles:</span><span class="sxs-lookup"><span data-stu-id="b7027-133">Enter the following details:</span></span>

   <span data-ttu-id="b7027-134">**General**</span><span class="sxs-lookup"><span data-stu-id="b7027-134">**General**</span></span>
   - <span data-ttu-id="b7027-135">Nombre: MDATP incorporación para macOS</span><span class="sxs-lookup"><span data-stu-id="b7027-135">Name: MDATP onboarding for macOS</span></span>
   - <span data-ttu-id="b7027-136">Descripción: MDATP EDR incorporación para macOS</span><span class="sxs-lookup"><span data-stu-id="b7027-136">Description: MDATP EDR onboarding for macOS</span></span>
   - <span data-ttu-id="b7027-137">Categoría: Ninguna</span><span class="sxs-lookup"><span data-stu-id="b7027-137">Category: None</span></span>
   - <span data-ttu-id="b7027-138">Método distribution: Install Automatically</span><span class="sxs-lookup"><span data-stu-id="b7027-138">Distribution Method: Install Automatically</span></span>
   - <span data-ttu-id="b7027-139">Nivel: Nivel de equipo</span><span class="sxs-lookup"><span data-stu-id="b7027-139">Level: Computer Level</span></span>

4. <span data-ttu-id="b7027-140">En **Application & Custom Configuración** seleccione **Configure**.</span><span class="sxs-lookup"><span data-stu-id="b7027-140">In **Application & Custom Settings** select **Configure**.</span></span>

    ![Imagen de configuración de la aplicación y la configuración personalizada](images/jamfpro-mac-profile.png)

5. <span data-ttu-id="b7027-142">Seleccione **Upload archivo (archivo PLIST)** y, a continuación, en **Dominio de preferencia** escriba: `com.microsoft.wdav.atp` .</span><span class="sxs-lookup"><span data-stu-id="b7027-142">Select **Upload File (PLIST file)** then in **Preference Domain** enter: `com.microsoft.wdav.atp`.</span></span> 

    ![Imagen del archivo de carga de jamfpro plist](images/jamfpro-plist-upload.png)

    ![Imagen de la propiedad de archivo de carga Archivo de lista](images/jamfpro-plist-file.png)

7. <span data-ttu-id="b7027-145">Seleccione **Abrir** y seleccione el archivo de incorporación.</span><span class="sxs-lookup"><span data-stu-id="b7027-145">Select **Open** and select the onboarding file.</span></span>

    ![Imagen del archivo de incorporación](images/jamfpro-plist-file-onboard.png)

8. <span data-ttu-id="b7027-147">Seleccione **Upload**.</span><span class="sxs-lookup"><span data-stu-id="b7027-147">Select **Upload**.</span></span> 

    ![Imagen de la carga del archivo plist](images/jamfpro-upload-plist.png)


9. <span data-ttu-id="b7027-149">Seleccione la **pestaña** Ámbito.</span><span class="sxs-lookup"><span data-stu-id="b7027-149">Select the **Scope** tab.</span></span>

    ![Imagen de la pestaña ámbito](images/jamfpro-scope-tab.png)

10. <span data-ttu-id="b7027-151">Seleccione los equipos de destino.</span><span class="sxs-lookup"><span data-stu-id="b7027-151">Select the target computers.</span></span>

    ![Imagen de los equipos de destino](images/jamfpro-target-computer.png)

    ![Imagen de los destinos](images/jamfpro-targets.png) 

11. <span data-ttu-id="b7027-154">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="b7027-154">Select **Save**.</span></span>

    ![Imagen de los equipos de destino de implementación](images/jamfpro-deployment-target.png)

    ![Imagen de los equipos de destino seleccionados](images/jamfpro-target-selected.png)

12. <span data-ttu-id="b7027-157">Seleccione **Listo**.</span><span class="sxs-lookup"><span data-stu-id="b7027-157">Select **Done**.</span></span>

    ![Imagen de los equipos de grupo de destino](images/jamfpro-target-group.png)

    ![Lista de perfiles de configuración](images/jamfpro-configuration-policies.png)

## <a name="step-3-configure-microsoft-defender-for-endpoint-settings"></a><span data-ttu-id="b7027-160">Paso 3: Configurar Microsoft Defender para la configuración del punto de conexión</span><span class="sxs-lookup"><span data-stu-id="b7027-160">Step 3: Configure Microsoft Defender for Endpoint settings</span></span>

1.  <span data-ttu-id="b7027-161">Use las siguientes opciones de configuración de Microsoft Defender para puntos de conexión:</span><span class="sxs-lookup"><span data-stu-id="b7027-161">Use the following Microsoft Defender for Endpoint configuration settings:</span></span>

    - <span data-ttu-id="b7027-162">enableRealTimeProtection</span><span class="sxs-lookup"><span data-stu-id="b7027-162">enableRealTimeProtection</span></span>
    - <span data-ttu-id="b7027-163">passiveMode</span><span class="sxs-lookup"><span data-stu-id="b7027-163">passiveMode</span></span>
    
    >[!NOTE]
    ><span data-ttu-id="b7027-164">No activado de forma predeterminada, si está planeando ejecutar un ANTIVIRUS de terceros para macOS, estafórlo en `true` .</span><span class="sxs-lookup"><span data-stu-id="b7027-164">Not turned on by default, if you are planning to run a third-party AV for macOS, set it to `true`.</span></span>

    - <span data-ttu-id="b7027-165">exclusiones</span><span class="sxs-lookup"><span data-stu-id="b7027-165">exclusions</span></span>
    - <span data-ttu-id="b7027-166">excludedPath</span><span class="sxs-lookup"><span data-stu-id="b7027-166">excludedPath</span></span>
    - <span data-ttu-id="b7027-167">excludedFileExtension</span><span class="sxs-lookup"><span data-stu-id="b7027-167">excludedFileExtension</span></span>
    - <span data-ttu-id="b7027-168">excludedFileName</span><span class="sxs-lookup"><span data-stu-id="b7027-168">excludedFileName</span></span>
    - <span data-ttu-id="b7027-169">exclusionsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="b7027-169">exclusionsMergePolicy</span></span>
    - <span data-ttu-id="b7027-170">allowedThreats</span><span class="sxs-lookup"><span data-stu-id="b7027-170">allowedThreats</span></span>
    
    >[!NOTE]
    ><span data-ttu-id="b7027-171">EICAR está en la muestra, si está pasando por una prueba de concepto, quítela especialmente si está probando EICAR.</span><span class="sxs-lookup"><span data-stu-id="b7027-171">EICAR is on the sample, if you are going through a proof-of-concept, remove it especially if you are testing EICAR.</span></span>
        
    - <span data-ttu-id="b7027-172">disallowedThreatActions</span><span class="sxs-lookup"><span data-stu-id="b7027-172">disallowedThreatActions</span></span>
    - <span data-ttu-id="b7027-173">potentially_unwanted_application</span><span class="sxs-lookup"><span data-stu-id="b7027-173">potentially_unwanted_application</span></span>
    - <span data-ttu-id="b7027-174">archive_bomb</span><span class="sxs-lookup"><span data-stu-id="b7027-174">archive_bomb</span></span>
    - <span data-ttu-id="b7027-175">cloudService</span><span class="sxs-lookup"><span data-stu-id="b7027-175">cloudService</span></span>
    - <span data-ttu-id="b7027-176">automaticSampleSubmission</span><span class="sxs-lookup"><span data-stu-id="b7027-176">automaticSampleSubmission</span></span>
    - <span data-ttu-id="b7027-177">tags</span><span class="sxs-lookup"><span data-stu-id="b7027-177">tags</span></span>
    - <span data-ttu-id="b7027-178">hideStatusMenuIcon</span><span class="sxs-lookup"><span data-stu-id="b7027-178">hideStatusMenuIcon</span></span>
    
     <span data-ttu-id="b7027-179">Para obtener información, vea [Lista de propiedades para el perfil de configuración de Jamf](mac-preferences.md#property-list-for-jamf-configuration-profile).</span><span class="sxs-lookup"><span data-stu-id="b7027-179">For information, see [Property list for Jamf configuration profile](mac-preferences.md#property-list-for-jamf-configuration-profile).</span></span>

     ```XML
     <?xml version="1.0" encoding="UTF-8"?>
     <!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
     <plist version="1.0">
     <dict>
         <key>antivirusEngine</key>
         <dict>
             <key>enableRealTimeProtection</key>
             <true/>
             <key>passiveMode</key>
             <false/>
             <key>exclusions</key>
             <array>
                 <dict>
                     <key>$type</key>
                     <string>excludedPath</string>
                     <key>isDirectory</key>
                     <false/>
                     <key>path</key>
                     <string>/var/log/system.log</string>
                 </dict>
                 <dict>
                     <key>$type</key>
                     <string>excludedPath</string>
                     <key>isDirectory</key>
                     <true/>
                     <key>path</key>
                     <string>/home</string>
                 </dict>
                 <dict>
                     <key>$type</key>
                     <string>excludedFileExtension</string>
                     <key>extension</key>
                     <string>pdf</string>
                 </dict>
                 <dict>
                     <key>$type</key>
                     <string>excludedFileName</string>
                     <key>name</key>
                     <string>cat</string>
                 </dict>
             </array>
             <key>exclusionsMergePolicy</key>
             <string>merge</string>
             <key>allowedThreats</key>
             <array>
                 <string>EICAR-Test-File (not a virus)</string>
             </array>
             <key>disallowedThreatActions</key>
             <array>
                 <string>allow</string>
                 <string>restore</string>
             </array>
             <key>threatTypeSettings</key>
             <array>
                 <dict>
                     <key>key</key>
                     <string>potentially_unwanted_application</string>
                     <key>value</key>
                     <string>block</string>
                 </dict>
                 <dict>
                     <key>key</key>
                     <string>archive_bomb</string>
                     <key>value</key>
                     <string>audit</string>
                 </dict>
             </array>
             <key>threatTypeSettingsMergePolicy</key>
             <string>merge</string>
         </dict>
         <key>cloudService</key>
         <dict>
             <key>enabled</key>
             <true/>
             <key>diagnosticLevel</key>
             <string>optional</string>
             <key>automaticSampleSubmission</key>
             <true/>
         </dict>
         <key>edr</key>
         <dict>
             <key>tags</key>
             <array>
                 <dict>
                     <key>key</key>
                     <string>GROUP</string>
                     <key>value</key>
                     <string>ExampleTag</string>
                 </dict>
             </array>
         </dict>
         <key>userInterface</key>
         <dict>
             <key>hideStatusMenuIcon</key>
             <false/>
         </dict>
     </dict>
     </plist>
     ```

2. <span data-ttu-id="b7027-180">Guarde el archivo como `MDATP_MDAV_configuration_settings.plist` .</span><span class="sxs-lookup"><span data-stu-id="b7027-180">Save the file as `MDATP_MDAV_configuration_settings.plist`.</span></span>


3.  <span data-ttu-id="b7027-181">En el panel de Pro Jamf, seleccione **General**.</span><span class="sxs-lookup"><span data-stu-id="b7027-181">In the Jamf Pro dashboard, select **General**.</span></span>

    ![Imagen del nuevo panel de Pro Jamf](images/644e0f3af40c29e80ca1443535b2fe32.png)

4. <span data-ttu-id="b7027-183">Escriba los siguientes detalles:</span><span class="sxs-lookup"><span data-stu-id="b7027-183">Enter the following details:</span></span>

    <span data-ttu-id="b7027-184">**General**</span><span class="sxs-lookup"><span data-stu-id="b7027-184">**General**</span></span>
    
    - <span data-ttu-id="b7027-185">Nombre: MDATP configuración de MDAV</span><span class="sxs-lookup"><span data-stu-id="b7027-185">Name: MDATP MDAV configuration settings</span></span>
    - <span data-ttu-id="b7027-186">Descripción:\<blank\></span><span class="sxs-lookup"><span data-stu-id="b7027-186">Description:\<blank\></span></span>
    - <span data-ttu-id="b7027-187">Categoría: Ninguno (predeterminado)</span><span class="sxs-lookup"><span data-stu-id="b7027-187">Category: None (default)</span></span>
    - <span data-ttu-id="b7027-188">Método distribution: Install Automatically (default)</span><span class="sxs-lookup"><span data-stu-id="b7027-188">Distribution Method: Install Automatically(default)</span></span>
    - <span data-ttu-id="b7027-189">Nivel: Nivel del equipo (predeterminado)</span><span class="sxs-lookup"><span data-stu-id="b7027-189">Level: Computer Level(default)</span></span>

    ![Imagen de MDATP configuración de MDAV](images/3160906404bc5a2edf84d1d015894e3b.png)

5. <span data-ttu-id="b7027-191">En **Application & Custom Configuración** seleccione **Configure**.</span><span class="sxs-lookup"><span data-stu-id="b7027-191">In **Application & Custom Settings** select **Configure**.</span></span>

    ![Imagen de la aplicación y la configuración personalizada](images/e1cc1e48ec9d5d688087b4d771e668d2.png)

6. <span data-ttu-id="b7027-193">Seleccione **Upload archivo (archivo PLIST).**</span><span class="sxs-lookup"><span data-stu-id="b7027-193">Select **Upload File (PLIST file)**.</span></span>

    ![Imagen del archivo plist de configuración](images/6f85269276b2278eca4bce84f935f87b.png)

7. <span data-ttu-id="b7027-195">En **Dominio de preferencias,** escriba , `com.microsoft.wdav` a **continuación, seleccione Upload archivo PLIST**.</span><span class="sxs-lookup"><span data-stu-id="b7027-195">In **Preferences Domain**, enter `com.microsoft.wdav`, then select  **Upload PLIST File**.</span></span>

    ![Imagen del dominio de preferencias de configuración](images/db15f147dd959e872a044184711d7d46.png)

8. <span data-ttu-id="b7027-197">Seleccione **Elegir archivo**.</span><span class="sxs-lookup"><span data-stu-id="b7027-197">Select **Choose File**.</span></span>

    ![Imagen de las opciones de configuración elija archivo](images/526e978761fc571cca06907da7b01fd6.png)

9. <span data-ttu-id="b7027-199">Seleccione el **MDATP_MDAV_configuration_settings.plist** y, a continuación, **seleccione Abrir**.</span><span class="sxs-lookup"><span data-stu-id="b7027-199">Select the **MDATP_MDAV_configuration_settings.plist**, then select **Open**.</span></span>

    ![Imagen de las opciones de configuración de mdatpmdav](images/98acea3750113b8dbab334296e833003.png)

10. <span data-ttu-id="b7027-201">Seleccione **Upload**.</span><span class="sxs-lookup"><span data-stu-id="b7027-201">Select **Upload**.</span></span>

    ![Imagen de la carga de configuración](images/0adb21c13206861ba9b30a879ade93d3.png)

    ![Imagen de la imagen de carga de opciones de configuración](images/f624de59b3cc86e3e2d32ae5de093e02.png)

    >[!NOTE]
    ><span data-ttu-id="b7027-204">Si se carga el archivo de Intune, se producirá el siguiente error:</span><span class="sxs-lookup"><span data-stu-id="b7027-204">If you happen to upload the Intune file, you'll get the following error:</span></span><br>
    ><span data-ttu-id="b7027-205">![Imagen de la carga de archivos de Intune de configuración](images/8e69f867664668796a3b2904896f0436.png)</span><span class="sxs-lookup"><span data-stu-id="b7027-205">![Image of configuration settings intune file upload](images/8e69f867664668796a3b2904896f0436.png)</span></span>


11. <span data-ttu-id="b7027-206">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="b7027-206">Select **Save**.</span></span> 

    ![Imagen de configuración Guardar imagen](images/1b6b5a4edcb42d97f1e70a6a0fa48e3a.png)

12. <span data-ttu-id="b7027-208">El archivo se carga.</span><span class="sxs-lookup"><span data-stu-id="b7027-208">The file is uploaded.</span></span>

    ![Imagen de la imagen cargada del archivo de configuración](images/33e2b2a1611fdddf6b5b79e54496e3bb.png)

    ![Imagen del archivo de configuración cargado](images/a422e57fe8d45689227e784443e51bd1.png)

13. <span data-ttu-id="b7027-211">Seleccione la **pestaña** Ámbito.</span><span class="sxs-lookup"><span data-stu-id="b7027-211">Select the **Scope** tab.</span></span>

    ![Imagen del ámbito de configuración](images/9fc17529e5577eefd773c658ec576a7d.png)

14. <span data-ttu-id="b7027-213">Seleccione **Grupo de máquinas de Contoso**.</span><span class="sxs-lookup"><span data-stu-id="b7027-213">Select **Contoso's Machine Group**.</span></span> 

15. <span data-ttu-id="b7027-214">Seleccione **Agregar** y, a continuación, **seleccione Guardar**.</span><span class="sxs-lookup"><span data-stu-id="b7027-214">Select **Add**, then select **Save**.</span></span>

    ![Imagen de configuración addsav](images/cf30438b5512ac89af1d11cbf35219a6.png)

    ![Imagen de las opciones de configuración guardar agregar](images/6f093e42856753a3955cab7ee14f12d9.png)

16. <span data-ttu-id="b7027-217">Seleccione **Listo**.</span><span class="sxs-lookup"><span data-stu-id="b7027-217">Select **Done**.</span></span> <span data-ttu-id="b7027-218">Verá el nuevo perfil **de configuración**.</span><span class="sxs-lookup"><span data-stu-id="b7027-218">You'll see the new **Configuration profile**.</span></span>

    ![Imagen de la imagen de perfil de configuración de configuración](images/dd55405106da0dfc2f50f8d4525b01c8.png)


## <a name="step-4-configure-notifications-settings"></a><span data-ttu-id="b7027-220">Paso 4: Configurar la configuración de notificaciones</span><span class="sxs-lookup"><span data-stu-id="b7027-220">Step 4: Configure notifications settings</span></span>

<span data-ttu-id="b7027-221">Estos pasos son aplicables a macOS 10.15 (Catalina) o versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="b7027-221">These steps are applicable of macOS 10.15 (Catalina) or newer.</span></span>

1. <span data-ttu-id="b7027-222">En el panel de Pro Jamf, seleccione **Equipos** y, a continuación, **Perfiles de configuración.**</span><span class="sxs-lookup"><span data-stu-id="b7027-222">In the Jamf Pro dashboard, select **Computers**, then **Configuration Profiles**.</span></span>

2. <span data-ttu-id="b7027-223">Haga **clic en** Nuevo y escriba los siguientes detalles para **Opciones:**</span><span class="sxs-lookup"><span data-stu-id="b7027-223">Click **New**, and enter the following details for **Options**:</span></span>
    
    - <span data-ttu-id="b7027-224">Ficha **General**:</span><span class="sxs-lookup"><span data-stu-id="b7027-224">Tab **General**:</span></span> 
        - <span data-ttu-id="b7027-225">**Nombre:** configuración MDATP notificación MDAV</span><span class="sxs-lookup"><span data-stu-id="b7027-225">**Name**: MDATP MDAV Notification settings</span></span>
        - <span data-ttu-id="b7027-226">**Descripción:** macOS 10.15 (Catalina) o posterior</span><span class="sxs-lookup"><span data-stu-id="b7027-226">**Description**: macOS 10.15 (Catalina) or newer</span></span>
        - <span data-ttu-id="b7027-227">**Categoría**: None *(valor predeterminado)*</span><span class="sxs-lookup"><span data-stu-id="b7027-227">**Category**: None *(default)*</span></span>
        - <span data-ttu-id="b7027-228">**Método Distribution:** Instalar automáticamente *(predeterminado)*</span><span class="sxs-lookup"><span data-stu-id="b7027-228">**Distribution Method**: Install Automatically *(default)*</span></span>
        - <span data-ttu-id="b7027-229">**Nivel:** Nivel de equipo *(predeterminado)*</span><span class="sxs-lookup"><span data-stu-id="b7027-229">**Level**: Computer Level *(default)*</span></span>

        ![Imagen de la nueva pantalla de perfil de configuración de macOS](images/c9820a5ff84aaf21635c04a23a97ca93.png)

    - <span data-ttu-id="b7027-231">Tab **Notifications**, click **Add** y escriba los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="b7027-231">Tab **Notifications**, click **Add**, and enter the following values:</span></span>
        - <span data-ttu-id="b7027-232">**Id. de agrupación:**`com.microsoft.wdav.tray`</span><span class="sxs-lookup"><span data-stu-id="b7027-232">**Bundle ID**: `com.microsoft.wdav.tray`</span></span>
        - <span data-ttu-id="b7027-233">**Alertas críticas:** haga clic **en Deshabilitar**</span><span class="sxs-lookup"><span data-stu-id="b7027-233">**Critical Alerts**: Click **Disable**</span></span>
        - <span data-ttu-id="b7027-234">**Notificaciones:** haga clic en **Habilitar**</span><span class="sxs-lookup"><span data-stu-id="b7027-234">**Notifications**: Click **Enable**</span></span>
        - <span data-ttu-id="b7027-235">**Tipo de alerta de banner:** Seleccione **Incluir** y **Temporal** *(predeterminado)*</span><span class="sxs-lookup"><span data-stu-id="b7027-235">**Banner alert type**: Select **Include** and **Temporary** *(default)*</span></span>
        - <span data-ttu-id="b7027-236">**Notificaciones en la pantalla de bloqueo:** Haga clic **en Ocultar**</span><span class="sxs-lookup"><span data-stu-id="b7027-236">**Notifications on lock screen**: Click **Hide**</span></span>
        - <span data-ttu-id="b7027-237">**Notificaciones en el Centro de notificaciones:** haga clic en **Mostrar**</span><span class="sxs-lookup"><span data-stu-id="b7027-237">**Notifications in Notification Center**: Click **Display**</span></span>
        - <span data-ttu-id="b7027-238">**Icono de aplicación de distintivo:** Haga clic en **Mostrar**</span><span class="sxs-lookup"><span data-stu-id="b7027-238">**Badge app icon**: Click **Display**</span></span>

        ![Imagen de la bandeja de notificaciones mdatpmdav de configuración](images/7f9138053dbcbf928e5182ee7b295ebe.png)

    - <span data-ttu-id="b7027-240">Tab **Notifications**, click **Add** one more time, scroll down to **New Notifications Configuración**</span><span class="sxs-lookup"><span data-stu-id="b7027-240">Tab **Notifications**, click **Add** one more time, scroll down to **New Notifications Settings**</span></span>
        - <span data-ttu-id="b7027-241">**Id. de agrupación:**`com.microsoft.autoupdate2`</span><span class="sxs-lookup"><span data-stu-id="b7027-241">**Bundle ID**: `com.microsoft.autoupdate2`</span></span>
        - <span data-ttu-id="b7027-242">Configure el resto de la configuración en los mismos valores anteriores</span><span class="sxs-lookup"><span data-stu-id="b7027-242">Configure the rest of the settings to the same values as above</span></span>

        ![Imagen de las notificaciones mdatpmdav de configuración mau](images/4bac6ce277aedfb4a674f2d9fcb2599a.png)

        <span data-ttu-id="b7027-244">Ten en cuenta que ahora tienes dos "tablas" con configuraciones de notificación, una para id. de **agrupación: com.microsoft.wdav.tray** y otra para id. de **lote: com.microsoft.autoupdate2**.</span><span class="sxs-lookup"><span data-stu-id="b7027-244">Note that now you have two 'tables' with notification configurations, one for **Bundle ID: com.microsoft.wdav.tray**, and another for **Bundle ID: com.microsoft.autoupdate2**.</span></span> <span data-ttu-id="b7027-245">Aunque puede configurar la configuración de alertas según sus **requisitos,** los IDs de agrupación deben ser exactamente los mismos que se han descrito anteriormente y el modificador **Include** debe estar **En** para notificaciones.</span><span class="sxs-lookup"><span data-stu-id="b7027-245">While you can configure alert settings per your requirements, Bundle IDs must be exactly the same as described before, and **Include** switch must be **On** for **Notifications**.</span></span>

3. <span data-ttu-id="b7027-246">Seleccione la **pestaña Ámbito** y, a continuación, **seleccione Agregar**.</span><span class="sxs-lookup"><span data-stu-id="b7027-246">Select the **Scope** tab, then select **Add**.</span></span>

    ![Imagen de la adición de ámbito de configuración](images/441aa2ecd36abadcdd8aed03556080b5.png)

4. <span data-ttu-id="b7027-248">Seleccione **Grupo de máquinas de Contoso**.</span><span class="sxs-lookup"><span data-stu-id="b7027-248">Select **Contoso's Machine Group**.</span></span> 

5. <span data-ttu-id="b7027-249">Seleccione **Agregar** y, a continuación, **seleccione Guardar**.</span><span class="sxs-lookup"><span data-stu-id="b7027-249">Select **Add**, then select **Save**.</span></span>
    
    ![Imagen de configuración de configuración de contoso machine grp save](images/09a275e321268e5e3ac0c0865d3e2db5.png)
    
    ![Imagen de las opciones de configuración agregar guardar](images/4d2d1d4ee13d3f840f425924c3df0d51.png)

6. <span data-ttu-id="b7027-252">Seleccione **Listo**.</span><span class="sxs-lookup"><span data-stu-id="b7027-252">Select **Done**.</span></span> <span data-ttu-id="b7027-253">Verá el nuevo perfil **de configuración**.</span><span class="sxs-lookup"><span data-stu-id="b7027-253">You'll see the new **Configuration profile**.</span></span>
    <span data-ttu-id="b7027-254">![Imagen de la configuración realizada img](images/633ad26b8bf24ec683c98b2feb884bdf.png)</span><span class="sxs-lookup"><span data-stu-id="b7027-254">![Image of configuration setting done img](images/633ad26b8bf24ec683c98b2feb884bdf.png)</span></span>

## <a name="step-5-configure-microsoft-autoupdate-mau"></a><span data-ttu-id="b7027-255">Paso 5: Configurar Microsoft AutoUpdate (MAU)</span><span class="sxs-lookup"><span data-stu-id="b7027-255">Step 5: Configure Microsoft AutoUpdate (MAU)</span></span>

1. <span data-ttu-id="b7027-256">Use las siguientes opciones de configuración de Microsoft Defender para puntos de conexión:</span><span class="sxs-lookup"><span data-stu-id="b7027-256">Use the following Microsoft Defender for Endpoint configuration settings:</span></span>

      ```XML
   <?xml version="1.0" encoding="UTF-8"?>
   <!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
   <plist version="1.0">
   <dict>
    <key>ChannelName</key>
    <string>Current</string>
    <key>HowToCheck</key>
    <string>AutomaticDownload</string>
    <key>EnableCheckForUpdatesButton</key>
    <true/>
    <key>DisableInsiderCheckbox</key>
    <false/>
    <key>SendAllTelemetryEnabled</key>
    <true/>
   </dict>
   </plist>
   ```

2. <span data-ttu-id="b7027-257">Guárdelo como `MDATP_MDAV_MAU_settings.plist` .</span><span class="sxs-lookup"><span data-stu-id="b7027-257">Save it as `MDATP_MDAV_MAU_settings.plist`.</span></span>

3. <span data-ttu-id="b7027-258">En el panel de Pro Jamf, seleccione **General**.</span><span class="sxs-lookup"><span data-stu-id="b7027-258">In the Jamf Pro dashboard, select **General**.</span></span> 

    ![Imagen de la imagen general de configuración](images/eaba2a23dd34f73bf59e826217ba6f15.png)

4. <span data-ttu-id="b7027-260">Escriba los siguientes detalles:</span><span class="sxs-lookup"><span data-stu-id="b7027-260">Enter the following details:</span></span>

    <span data-ttu-id="b7027-261">**General**</span><span class="sxs-lookup"><span data-stu-id="b7027-261">**General**</span></span> 
    
    - <span data-ttu-id="b7027-262">Nombre: MDATP de MDAV MAU</span><span class="sxs-lookup"><span data-stu-id="b7027-262">Name: MDATP MDAV MAU settings</span></span>
    - <span data-ttu-id="b7027-263">Descripción: Configuración de Microsoft AutoUpdate para MDATP para macOS</span><span class="sxs-lookup"><span data-stu-id="b7027-263">Description: Microsoft AutoUpdate settings for MDATP for macOS</span></span>
    - <span data-ttu-id="b7027-264">Categoría: Ninguno (predeterminado)</span><span class="sxs-lookup"><span data-stu-id="b7027-264">Category: None (default)</span></span>
    - <span data-ttu-id="b7027-265">Método distribution: Install Automatically (default)</span><span class="sxs-lookup"><span data-stu-id="b7027-265">Distribution Method: Install Automatically(default)</span></span>
    - <span data-ttu-id="b7027-266">Nivel: Nivel del equipo (predeterminado)</span><span class="sxs-lookup"><span data-stu-id="b7027-266">Level: Computer Level(default)</span></span>

5. <span data-ttu-id="b7027-267">En **Application & Custom Configuración** seleccione **Configure**.</span><span class="sxs-lookup"><span data-stu-id="b7027-267">In **Application & Custom Settings** select **Configure**.</span></span>

    ![Imagen de la aplicación de configuración y la configuración personalizada](images/1f72e9c15eaafcabf1504397e99be311.png)

6. <span data-ttu-id="b7027-269">Seleccione **Upload archivo (archivo PLIST).**</span><span class="sxs-lookup"><span data-stu-id="b7027-269">Select **Upload File (PLIST file)**.</span></span>

    ![Imagen de la configuración plist](images/1213872db5833aa8be535da57653219f.png)  

7. <span data-ttu-id="b7027-271">En **Dominio de preferencia** escriba: , luego seleccione Upload archivo `com.microsoft.autoupdate2` **PLIST**.</span><span class="sxs-lookup"><span data-stu-id="b7027-271">In **Preference Domain** enter: `com.microsoft.autoupdate2`, then select **Upload PLIST File**.</span></span>

    ![Imagen del dominio de configuración previa a la configuración](images/1213872db5833aa8be535da57653219f.png)

8. <span data-ttu-id="b7027-273">Seleccione **Elegir archivo**.</span><span class="sxs-lookup"><span data-stu-id="b7027-273">Select **Choose File**.</span></span>

    ![Imagen de choosefile de configuración de configuración](images/335aff58950ce62d1dabc289ecdce9ed.png)

9. <span data-ttu-id="b7027-275">Seleccione **MDATP_MDAV_MAU_settings.plist**.</span><span class="sxs-lookup"><span data-stu-id="b7027-275">Select **MDATP_MDAV_MAU_settings.plist**.</span></span>

    ![Imagen de la configuración mdatpmdavmau settings](images/a26bd4967cd54bb113a2c8d32894c3de.png)

10. <span data-ttu-id="b7027-277">Seleccione **Upload**.</span><span class="sxs-lookup"><span data-stu-id="b7027-277">Select **Upload**.</span></span>
    <span data-ttu-id="b7027-278">![Imagen de configuración de configuración uplimage](images/4239ca0528efb0734e4ca0b490bfb22d.png)</span><span class="sxs-lookup"><span data-stu-id="b7027-278">![Image of configuration setting uplimage](images/4239ca0528efb0734e4ca0b490bfb22d.png)</span></span>

    ![Imagen de configuración de configuración uplimg](images/4ec20e72c8aed9a4c16912e01692436a.png)

11. <span data-ttu-id="b7027-280">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="b7027-280">Select **Save**.</span></span>

    ![Imagen de la configuración saveimg](images/253274b33e74f3f5b8d475cf8692ce4e.png)

12. <span data-ttu-id="b7027-282">Seleccione la **pestaña** Ámbito.</span><span class="sxs-lookup"><span data-stu-id="b7027-282">Select the **Scope** tab.</span></span>
   
     ![Imagen de la tabla de ámbito de configuración](images/10ab98358b2d602f3f67618735fa82fb.png)

13. <span data-ttu-id="b7027-284">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="b7027-284">Select **Add**.</span></span>
    
    ![Imagen de la configuración addimg1](images/56e6f6259b9ce3c1706ed8d666ae4947.png)

    ![Imagen de la configuración addimg2](images/38c67ee1905c4747c3b26c8eba57726b.png)

    ![Imagen de la configuración addimg3](images/321ba245f14743c1d5d51c15e99deecc.png)

14. <span data-ttu-id="b7027-288">Seleccione **Listo**.</span><span class="sxs-lookup"><span data-stu-id="b7027-288">Select **Done**.</span></span>
    
    ![Imagen de configuración doneimage](images/ba44cdb77e4781aa8b940fb83e3c21f7.png)

## <a name="step-6-grant-full-disk-access-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="b7027-290">Paso 6: Conceder acceso en disco completo a Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="b7027-290">Step 6: Grant full disk access to Microsoft Defender for Endpoint</span></span>

1. <span data-ttu-id="b7027-291">En el panel de Pro Jamf, seleccione **Perfiles de configuración**.</span><span class="sxs-lookup"><span data-stu-id="b7027-291">In the Jamf Pro dashboard, select **Configuration Profiles**.</span></span>

    ![Imagen del perfil de configuración de configuración](images/264493cd01e62c7085659d6fdc26dc91.png)

2. <span data-ttu-id="b7027-293">Seleccione **+ Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="b7027-293">Select **+ New**.</span></span> 

3. <span data-ttu-id="b7027-294">Escriba los siguientes detalles:</span><span class="sxs-lookup"><span data-stu-id="b7027-294">Enter the following details:</span></span>

    <span data-ttu-id="b7027-295">**General**</span><span class="sxs-lookup"><span data-stu-id="b7027-295">**General**</span></span> 
    - <span data-ttu-id="b7027-296">Nombre: MDATP MDAV: conceder acceso en disco completo a EDR y AV</span><span class="sxs-lookup"><span data-stu-id="b7027-296">Name: MDATP MDAV - grant Full Disk Access to EDR and AV</span></span>
    - <span data-ttu-id="b7027-297">Descripción: en macOS Catalina o versiones posteriores, el nuevo control de directiva de preferencias de privacidad</span><span class="sxs-lookup"><span data-stu-id="b7027-297">Description: On macOS Catalina or newer, the new Privacy Preferences Policy Control</span></span>
    - <span data-ttu-id="b7027-298">Categoría: Ninguna</span><span class="sxs-lookup"><span data-stu-id="b7027-298">Category: None</span></span>
    - <span data-ttu-id="b7027-299">Método de distribución: Instalar automáticamente</span><span class="sxs-lookup"><span data-stu-id="b7027-299">Distribution method: Install Automatically</span></span>
    - <span data-ttu-id="b7027-300">Nivel: nivel de equipo</span><span class="sxs-lookup"><span data-stu-id="b7027-300">Level: Computer level</span></span>


    ![Imagen de la configuración general](images/ba3d40399e1a6d09214ecbb2b341923f.png)

4. <span data-ttu-id="b7027-302">En **Configurar el control de directiva de preferencias de privacidad,** seleccione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="b7027-302">In **Configure Privacy Preferences Policy Control** select **Configure**.</span></span>

    ![Imagen del control de directiva de privacidad de configuración](images/715ae7ec8d6a262c489f94d14e1e51bb.png)

5. <span data-ttu-id="b7027-304">En **Control de directiva de preferencias de** privacidad, escriba los siguientes detalles:</span><span class="sxs-lookup"><span data-stu-id="b7027-304">In **Privacy Preferences Policy Control**, enter the following details:</span></span>

    - <span data-ttu-id="b7027-305">Identificador: `com.microsoft.wdav`</span><span class="sxs-lookup"><span data-stu-id="b7027-305">Identifier: `com.microsoft.wdav`</span></span>
    - <span data-ttu-id="b7027-306">Tipo de identificador: Id. de agrupación</span><span class="sxs-lookup"><span data-stu-id="b7027-306">Identifier Type: Bundle ID</span></span>
    - <span data-ttu-id="b7027-307">Requisito de código: `identifier "com.microsoft.wdav" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span><span class="sxs-lookup"><span data-stu-id="b7027-307">Code Requirement: `identifier "com.microsoft.wdav" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span></span>


    ![Imagen de los detalles de control de la directiva de preferencias de privacidad de configuración](images/22cb439de958101c0a12f3038f905b27.png)

6. <span data-ttu-id="b7027-309">Seleccione **+ Agregar**.</span><span class="sxs-lookup"><span data-stu-id="b7027-309">Select **+ Add**.</span></span>

    ![Imagen de la configuración agregar directiva del sistema todos los archivos](images/bd93e78b74c2660a0541af4690dd9485.png)

    - <span data-ttu-id="b7027-311">En Aplicación o servicio: Establecer en **SystemPolicyAllFiles**</span><span class="sxs-lookup"><span data-stu-id="b7027-311">Under App or service: Set to **SystemPolicyAllFiles**</span></span>

    - <span data-ttu-id="b7027-312">En "access": Set to **Allow**</span><span class="sxs-lookup"><span data-stu-id="b7027-312">Under "access": Set to **Allow**</span></span>

7. <span data-ttu-id="b7027-313">Seleccione **Guardar** (no el que se encuentra en la parte inferior derecha).</span><span class="sxs-lookup"><span data-stu-id="b7027-313">Select **Save** (not the one at the bottom right).</span></span>

    ![Imagen de configuración de guardar imágenes](images/6de50b4a897408ddc6ded56a09c09fe2.png)

8. <span data-ttu-id="b7027-315">Haga clic `+` en el signo situado junto a App **Access** para agregar una nueva entrada.</span><span class="sxs-lookup"><span data-stu-id="b7027-315">Click the `+` sign next to **App Access** to add a new entry.</span></span>

    ![Imagen del acceso a la aplicación de configuración](images/tcc-add-entry.png)

9. <span data-ttu-id="b7027-317">Escriba los siguientes detalles:</span><span class="sxs-lookup"><span data-stu-id="b7027-317">Enter the following details:</span></span>

    - <span data-ttu-id="b7027-318">Identificador: `com.microsoft.wdav.epsext`</span><span class="sxs-lookup"><span data-stu-id="b7027-318">Identifier: `com.microsoft.wdav.epsext`</span></span>
    - <span data-ttu-id="b7027-319">Tipo de identificador: Id. de agrupación</span><span class="sxs-lookup"><span data-stu-id="b7027-319">Identifier Type: Bundle ID</span></span>
    - <span data-ttu-id="b7027-320">Requisito de código: `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span><span class="sxs-lookup"><span data-stu-id="b7027-320">Code Requirement: `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span></span>

10. <span data-ttu-id="b7027-321">Seleccione **+ Agregar**.</span><span class="sxs-lookup"><span data-stu-id="b7027-321">Select **+ Add**.</span></span>

    ![Imagen de la entrada tcc epsext de configuración](images/tcc-epsext-entry.png)

    - <span data-ttu-id="b7027-323">En Aplicación o servicio: Establecer en **SystemPolicyAllFiles**</span><span class="sxs-lookup"><span data-stu-id="b7027-323">Under App or service: Set to **SystemPolicyAllFiles**</span></span>

    - <span data-ttu-id="b7027-324">En "access": Set to **Allow**</span><span class="sxs-lookup"><span data-stu-id="b7027-324">Under "access": Set to **Allow**</span></span>

11. <span data-ttu-id="b7027-325">Seleccione **Guardar** (no el que se encuentra en la parte inferior derecha).</span><span class="sxs-lookup"><span data-stu-id="b7027-325">Select **Save** (not the one at the bottom right).</span></span>

    ![Imagen de la configuración tcc epsext image2](images/tcc-epsext-entry2.png)

12. <span data-ttu-id="b7027-327">Seleccione la **pestaña** Ámbito.</span><span class="sxs-lookup"><span data-stu-id="b7027-327">Select the **Scope** tab.</span></span>

    ![Imagen del ámbito de configuración](images/2c49b16cd112729b3719724f581e6882.png)

13. <span data-ttu-id="b7027-329">Seleccione **+ Agregar**.</span><span class="sxs-lookup"><span data-stu-id="b7027-329">Select **+ Add**.</span></span>

    ![Imagen de la configuración addimage](images/57cef926d1b9260fb74a5f460cee887a.png)

14. <span data-ttu-id="b7027-331">Seleccione **Grupos de** equipos > en Nombre **de** grupo > seleccione **MachineGroup de Contoso**.</span><span class="sxs-lookup"><span data-stu-id="b7027-331">Select **Computer Groups** > under **Group Name** > select **Contoso's MachineGroup**.</span></span> 

    ![Imagen de configuración de configuración contoso machinegrp](images/368d35b3d6179af92ffdbfd93b226b69.png)

15. <span data-ttu-id="b7027-333">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="b7027-333">Select **Add**.</span></span> 

16. <span data-ttu-id="b7027-334">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="b7027-334">Select **Save**.</span></span> 
    
17. <span data-ttu-id="b7027-335">Seleccione **Listo**.</span><span class="sxs-lookup"><span data-stu-id="b7027-335">Select **Done**.</span></span>
    
    ![Imagen de la configuración de donimg](images/809cef630281b64b8f07f20913b0039b.png)
    
    ![Imagen de la configuración de donimg2](images/6c8b406ee224335a8c65d06953dc756e.png)

<span data-ttu-id="b7027-338">Como alternativa, puede descargar [fulldisk.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/fulldisk.mobileconfig) y cargarlo en los perfiles de configuración de JAMF, como se describe en [Deploying Custom Configuration Profiles using Jamf Pro| Método 2: Upload un perfil de configuración a Jamf Pro](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro).</span><span class="sxs-lookup"><span data-stu-id="b7027-338">Alternatively, you can download [fulldisk.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/fulldisk.mobileconfig) and upload it to JAMF Configuration Profiles as described in [Deploying Custom Configuration Profiles using Jamf Pro|Method 2: Upload a Configuration Profile to Jamf Pro](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro).</span></span>

## <a name="step-7-approve-kernel-extension-for-microsoft-defender-for-endpoint"></a><span data-ttu-id="b7027-339">Paso 7: Aprobar extensión de kernel para Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="b7027-339">Step 7: Approve Kernel extension for Microsoft Defender for Endpoint</span></span>

> [!CAUTION]
> <span data-ttu-id="b7027-340">Los dispositivos Apple Silicon (M1) no son compatibles con KEXT.</span><span class="sxs-lookup"><span data-stu-id="b7027-340">Apple Silicon (M1) devices do not support KEXT.</span></span> <span data-ttu-id="b7027-341">La instalación de un perfil de configuración que consta de directivas KEXT producirá un error en estos dispositivos.</span><span class="sxs-lookup"><span data-stu-id="b7027-341">Installation of a configuration profile consisting KEXT policies will fail on these devices.</span></span>

1. <span data-ttu-id="b7027-342">En **perfiles de configuración,** seleccione **+ Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="b7027-342">In the **Configuration Profiles**, select **+ New**.</span></span>

    ![Captura de pantalla de una publicación de redes sociales Descripción generada automáticamente](images/6c8b406ee224335a8c65d06953dc756e.png)

2. <span data-ttu-id="b7027-344">Escriba los siguientes detalles:</span><span class="sxs-lookup"><span data-stu-id="b7027-344">Enter the following details:</span></span>

    <span data-ttu-id="b7027-345">**General**</span><span class="sxs-lookup"><span data-stu-id="b7027-345">**General**</span></span> 
    
    - <span data-ttu-id="b7027-346">Nombre: MDATP de kernel MDAV</span><span class="sxs-lookup"><span data-stu-id="b7027-346">Name: MDATP MDAV Kernel Extension</span></span>
    - <span data-ttu-id="b7027-347">Descripción: MDATP kernel (kext)</span><span class="sxs-lookup"><span data-stu-id="b7027-347">Description: MDATP kernel extension (kext)</span></span>
    - <span data-ttu-id="b7027-348">Categoría: Ninguna</span><span class="sxs-lookup"><span data-stu-id="b7027-348">Category: None</span></span>
    - <span data-ttu-id="b7027-349">Método distribution: Install Automatically</span><span class="sxs-lookup"><span data-stu-id="b7027-349">Distribution Method: Install Automatically</span></span>
    - <span data-ttu-id="b7027-350">Nivel: Nivel de equipo</span><span class="sxs-lookup"><span data-stu-id="b7027-350">Level: Computer Level</span></span>

    ![Imagen del kernel mdatpmdav de configuración](images/24e290f5fc309932cf41f3a280d22c14.png)

3. <span data-ttu-id="b7027-352">En **Configurar extensiones de kernel aprobadas,** seleccione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="b7027-352">In **Configure Approved Kernel Extensions** select **Configure**.</span></span>

    ![Imagen de configuración de configuración aprobada ext del kernel](images/30be88b63abc5e8dde11b73f1b1ade6a.png)

   
4. <span data-ttu-id="b7027-354">En **Extensiones de kernel aprobadas,** escriba los siguientes detalles:</span><span class="sxs-lookup"><span data-stu-id="b7027-354">In **Approved Kernel Extensions** Enter the following details:</span></span>

    - <span data-ttu-id="b7027-355">Nombre para mostrar: Microsoft Corp.</span><span class="sxs-lookup"><span data-stu-id="b7027-355">Display Name: Microsoft Corp.</span></span>
    - <span data-ttu-id="b7027-356">Id. de equipo: UBF8T346G9</span><span class="sxs-lookup"><span data-stu-id="b7027-356">Team ID: UBF8T346G9</span></span>

    ![Imagen de la extensión del kernel de appr de configuración](images/39cf120d3ac3652292d8d1b6d057bd60.png)

5. <span data-ttu-id="b7027-358">Seleccione la **pestaña** Ámbito.</span><span class="sxs-lookup"><span data-stu-id="b7027-358">Select the **Scope** tab.</span></span>

    ![Imagen de la pestaña ámbito de configuración img](images/0df36fc308ba569db204ee32db3fb40a.png)

6. <span data-ttu-id="b7027-360">Seleccione **+ Agregar**.</span><span class="sxs-lookup"><span data-stu-id="b7027-360">Select **+ Add**.</span></span>

7. <span data-ttu-id="b7027-361">Seleccione **Grupos de** equipos > en Nombre **de** grupo > seleccione Grupo de máquinas **de Contoso**.</span><span class="sxs-lookup"><span data-stu-id="b7027-361">Select **Computer Groups** > under **Group Name** > select **Contoso's Machine Group**.</span></span>

8. <span data-ttu-id="b7027-362">Seleccione **+ Agregar**.</span><span class="sxs-lookup"><span data-stu-id="b7027-362">Select **+ Add**.</span></span>

    ![Imagen de las opciones de configuración agregar imágenes](images/0dde8a4c41110dbc398c485433a81359.png)

9. <span data-ttu-id="b7027-364">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="b7027-364">Select **Save**.</span></span>

    ![Imagen de la configuración saveimag](images/0add8019b85a453b47fa5c402c72761b.png)

10. <span data-ttu-id="b7027-366">Seleccione **Listo**.</span><span class="sxs-lookup"><span data-stu-id="b7027-366">Select **Done**.</span></span>

    ![Imagen de configuración doneimag](images/1c9bd3f68db20b80193dac18f33c22d0.png)

<span data-ttu-id="b7027-368">Como alternativa, puede descargar [kext.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/kext.mobileconfig) y cargarlo en los perfiles de configuración de JAMF, como se describe en [Deploying Custom Configuration Profiles using Jamf Pro| Método 2: Upload un perfil de configuración a Jamf Pro](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro).</span><span class="sxs-lookup"><span data-stu-id="b7027-368">Alternatively, you can download [kext.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/kext.mobileconfig) and upload it to JAMF Configuration Profiles as described in [Deploying Custom Configuration Profiles using Jamf Pro|Method 2: Upload a Configuration Profile to Jamf Pro](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro).</span></span>

## <a name="step-8-approve-system-extensions-for-microsoft-defender-for-endpoint"></a><span data-ttu-id="b7027-369">Paso 8: Aprobar extensiones de sistema para Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="b7027-369">Step 8: Approve System extensions for Microsoft Defender for Endpoint</span></span>

1. <span data-ttu-id="b7027-370">En **perfiles de configuración,** seleccione **+ Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="b7027-370">In the **Configuration Profiles**, select **+ New**.</span></span>

    ![Captura de pantalla de una publicación de redes sociales Descripción generada automáticamente](images/6c8b406ee224335a8c65d06953dc756e.png)

2. <span data-ttu-id="b7027-372">Escriba los siguientes detalles:</span><span class="sxs-lookup"><span data-stu-id="b7027-372">Enter the following details:</span></span>

    <span data-ttu-id="b7027-373">**General**</span><span class="sxs-lookup"><span data-stu-id="b7027-373">**General**</span></span>
    
    - <span data-ttu-id="b7027-374">Nombre: MDATP mdav system extensions</span><span class="sxs-lookup"><span data-stu-id="b7027-374">Name: MDATP MDAV System Extensions</span></span>
    - <span data-ttu-id="b7027-375">Descripción: MDATP extensiones del sistema</span><span class="sxs-lookup"><span data-stu-id="b7027-375">Description: MDATP system extensions</span></span>
    - <span data-ttu-id="b7027-376">Categoría: Ninguna</span><span class="sxs-lookup"><span data-stu-id="b7027-376">Category: None</span></span>
    - <span data-ttu-id="b7027-377">Método distribution: Install Automatically</span><span class="sxs-lookup"><span data-stu-id="b7027-377">Distribution Method: Install Automatically</span></span>
    - <span data-ttu-id="b7027-378">Nivel: Nivel de equipo</span><span class="sxs-lookup"><span data-stu-id="b7027-378">Level: Computer Level</span></span>

    ![Imagen de configuración sysext new prof](images/sysext-new-profile.png)

3. <span data-ttu-id="b7027-380">En **Extensiones del sistema,** seleccione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="b7027-380">In **System Extensions** select **Configure**.</span></span>

   ![Imagen de configuración sysext config](images/sysext-configure.png)

4. <span data-ttu-id="b7027-382">En **Extensiones del sistema,** escriba los siguientes detalles:</span><span class="sxs-lookup"><span data-stu-id="b7027-382">In **System Extensions** enter the following details:</span></span>

   - <span data-ttu-id="b7027-383">Nombre para mostrar: Microsoft Corp. Extensiones del sistema</span><span class="sxs-lookup"><span data-stu-id="b7027-383">Display Name: Microsoft Corp. System Extensions</span></span>
   - <span data-ttu-id="b7027-384">Tipos de extensión del sistema: extensiones de sistema permitidas</span><span class="sxs-lookup"><span data-stu-id="b7027-384">System Extension Types: Allowed System Extensions</span></span>
   - <span data-ttu-id="b7027-385">Identificador de equipo: UBF8T346G9</span><span class="sxs-lookup"><span data-stu-id="b7027-385">Team Identifier: UBF8T346G9</span></span>
   - <span data-ttu-id="b7027-386">Extensiones de sistema permitidas:</span><span class="sxs-lookup"><span data-stu-id="b7027-386">Allowed System Extensions:</span></span>
     - <span data-ttu-id="b7027-387">**com.microsoft.wdav.epsext**</span><span class="sxs-lookup"><span data-stu-id="b7027-387">**com.microsoft.wdav.epsext**</span></span>
     - <span data-ttu-id="b7027-388">**com.microsoft.wdav.netext**</span><span class="sxs-lookup"><span data-stu-id="b7027-388">**com.microsoft.wdav.netext**</span></span>

    ![Imagen de las opciones de configuración sysextconfig2](images/sysext-configure2.png)

5. <span data-ttu-id="b7027-390">Seleccione la **pestaña** Ámbito.</span><span class="sxs-lookup"><span data-stu-id="b7027-390">Select the **Scope** tab.</span></span>

    ![Imagen del ámbito de configuración de configuraciónimage](images/0df36fc308ba569db204ee32db3fb40a.png)

6. <span data-ttu-id="b7027-392">Seleccione **+ Agregar**.</span><span class="sxs-lookup"><span data-stu-id="b7027-392">Select **+ Add**.</span></span>

7. <span data-ttu-id="b7027-393">Seleccione **Grupos de** equipos > en Nombre **de** grupo > seleccione Grupo de máquinas **de Contoso**.</span><span class="sxs-lookup"><span data-stu-id="b7027-393">Select **Computer Groups** > under **Group Name** > select **Contoso's Machine Group**.</span></span>

8. <span data-ttu-id="b7027-394">Seleccione **+ Agregar**.</span><span class="sxs-lookup"><span data-stu-id="b7027-394">Select **+ Add**.</span></span>

   ![Imagen de addima de configuración](images/0dde8a4c41110dbc398c485433a81359.png)

9. <span data-ttu-id="b7027-396">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="b7027-396">Select **Save**.</span></span>

   ![Imagen del ámbito sysext de configuración](images/sysext-scope.png)

10. <span data-ttu-id="b7027-398">Seleccione **Listo**.</span><span class="sxs-lookup"><span data-stu-id="b7027-398">Select **Done**.</span></span>

    ![Imagen de las opciones de configuración sysext-final](images/sysext-final.png)

## <a name="step-9-configure-network-extension"></a><span data-ttu-id="b7027-400">Paso 9: Configurar extensión de red</span><span class="sxs-lookup"><span data-stu-id="b7027-400">Step 9: Configure Network Extension</span></span>

<span data-ttu-id="b7027-401">Como parte de las capacidades de detección y respuesta de puntos de conexión, Microsoft Defender para endpoint en macOS inspecciona el tráfico de sockets e informa de esta información al portal Centro de seguridad de Microsoft Defender web.</span><span class="sxs-lookup"><span data-stu-id="b7027-401">As part of the Endpoint Detection and Response capabilities, Microsoft Defender for Endpoint on macOS inspects socket traffic and reports this information to the Microsoft Defender Security Center portal.</span></span> <span data-ttu-id="b7027-402">La siguiente directiva permite que la extensión de red realice esta funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="b7027-402">The following policy allows the network extension to perform this functionality.</span></span>

<span data-ttu-id="b7027-403">Estos pasos son aplicables a macOS 10.15 (Catalina) o versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="b7027-403">These steps are applicable of macOS 10.15 (Catalina) or newer.</span></span>

1. <span data-ttu-id="b7027-404">En el panel de Pro Jamf, seleccione **Equipos** y, a continuación, **Perfiles de configuración.**</span><span class="sxs-lookup"><span data-stu-id="b7027-404">In the Jamf Pro dashboard, select **Computers**, then **Configuration Profiles**.</span></span>

2. <span data-ttu-id="b7027-405">Haga **clic en** Nuevo y escriba los siguientes detalles para **Opciones:**</span><span class="sxs-lookup"><span data-stu-id="b7027-405">Click **New**, and enter the following details for **Options**:</span></span>

    - <span data-ttu-id="b7027-406">Ficha **General**:</span><span class="sxs-lookup"><span data-stu-id="b7027-406">Tab **General**:</span></span> 
        - <span data-ttu-id="b7027-407">**Name**: ATP de Microsoft Defender Network Extension</span><span class="sxs-lookup"><span data-stu-id="b7027-407">**Name**: Microsoft Defender ATP Network Extension</span></span>
        - <span data-ttu-id="b7027-408">**Descripción:** macOS 10.15 (Catalina) o posterior</span><span class="sxs-lookup"><span data-stu-id="b7027-408">**Description**: macOS 10.15 (Catalina) or newer</span></span>
        - <span data-ttu-id="b7027-409">**Categoría**: None *(valor predeterminado)*</span><span class="sxs-lookup"><span data-stu-id="b7027-409">**Category**: None *(default)*</span></span>
        - <span data-ttu-id="b7027-410">**Método Distribution:** Instalar automáticamente *(predeterminado)*</span><span class="sxs-lookup"><span data-stu-id="b7027-410">**Distribution Method**: Install Automatically *(default)*</span></span>
        - <span data-ttu-id="b7027-411">**Nivel:** Nivel de equipo *(predeterminado)*</span><span class="sxs-lookup"><span data-stu-id="b7027-411">**Level**: Computer Level *(default)*</span></span>

    - <span data-ttu-id="b7027-412">Filtro **de contenido de pestaña**:</span><span class="sxs-lookup"><span data-stu-id="b7027-412">Tab **Content Filter**:</span></span>
        - <span data-ttu-id="b7027-413">**Nombre del filtro:** ATP de Microsoft Defender filtro de contenido</span><span class="sxs-lookup"><span data-stu-id="b7027-413">**Filter Name**: Microsoft Defender ATP Content Filter</span></span>
        - <span data-ttu-id="b7027-414">**Identificador**: `com.microsoft.wdav`</span><span class="sxs-lookup"><span data-stu-id="b7027-414">**Identifier**: `com.microsoft.wdav`</span></span>
        - <span data-ttu-id="b7027-415">Dejar **en blanco dirección de** servicio , **organización**, nombre **de** usuario , **contraseña**, **certificado** (**Incluir** *no está* seleccionado)</span><span class="sxs-lookup"><span data-stu-id="b7027-415">Leave **Service Address**, **Organization**, **User Name**, **Password**, **Certificate** blank (**Include** is *not* selected)</span></span>
        - <span data-ttu-id="b7027-416">**Orden de filtro:** Inspector</span><span class="sxs-lookup"><span data-stu-id="b7027-416">**Filter Order**: Inspector</span></span>
        - <span data-ttu-id="b7027-417">**Filtro de sockets**: `com.microsoft.wdav.netext`</span><span class="sxs-lookup"><span data-stu-id="b7027-417">**Socket Filter**: `com.microsoft.wdav.netext`</span></span>
        - <span data-ttu-id="b7027-418">**Requisito designado del filtro de socket:**`identifier "com.microsoft.wdav.netext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span><span class="sxs-lookup"><span data-stu-id="b7027-418">**Socket Filter Designated Requirement**: `identifier "com.microsoft.wdav.netext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span></span>
        - <span data-ttu-id="b7027-419">Dejar **campos de filtro de** red en blanco (**Incluir** no *está* seleccionado)</span><span class="sxs-lookup"><span data-stu-id="b7027-419">Leave **Network Filter** fields blank (**Include** is *not* selected)</span></span>

        <span data-ttu-id="b7027-420">Tenga en cuenta que los valores **exactos identificador**, filtro de **socket** y filtro **de** socket designados como se especifica anteriormente.</span><span class="sxs-lookup"><span data-stu-id="b7027-420">Note that **Identifier**, **Socket Filter** and **Socket Filter Designated Requirement** exact values as specified above.</span></span>

        ![Imagen de la configuración mdatpmdav](images/netext-create-profile.png)

3. <span data-ttu-id="b7027-422">Seleccione la **pestaña** Ámbito.</span><span class="sxs-lookup"><span data-stu-id="b7027-422">Select the **Scope** tab.</span></span>

   ![Imagen de la pestaña sco de configuración](images/0df36fc308ba569db204ee32db3fb40a.png)

4. <span data-ttu-id="b7027-424">Seleccione **+ Agregar**.</span><span class="sxs-lookup"><span data-stu-id="b7027-424">Select **+ Add**.</span></span>

5. <span data-ttu-id="b7027-425">Seleccione **Grupos de** equipos > en Nombre **de** grupo > seleccione Grupo de máquinas **de Contoso**.</span><span class="sxs-lookup"><span data-stu-id="b7027-425">Select **Computer Groups** > under **Group Name** > select **Contoso's Machine Group**.</span></span>

6. <span data-ttu-id="b7027-426">Seleccione **+ Agregar**.</span><span class="sxs-lookup"><span data-stu-id="b7027-426">Select **+ Add**.</span></span>

    ![Imagen de configuración adim](images/0dde8a4c41110dbc398c485433a81359.png)

7. <span data-ttu-id="b7027-428">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="b7027-428">Select **Save**.</span></span>

    ![Imagen de la configuración de savimg netextscop](images/netext-scope.png)

8. <span data-ttu-id="b7027-430">Seleccione **Listo**.</span><span class="sxs-lookup"><span data-stu-id="b7027-430">Select **Done**.</span></span>

    ![Imagen de la configuración netextfinal](images/netext-final.png)

<span data-ttu-id="b7027-432">Como alternativa, puede descargar [netfilter.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/netfilter.mobileconfig) y cargarlo en los perfiles de configuración de JAMF, como se describe en [Deploying Custom Configuration Profiles using Jamf Pro| Método 2: Upload un perfil de configuración a Jamf Pro](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro).</span><span class="sxs-lookup"><span data-stu-id="b7027-432">Alternatively, you can download [netfilter.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/netfilter.mobileconfig) and upload it to JAMF Configuration Profiles as described in [Deploying Custom Configuration Profiles using Jamf Pro|Method 2: Upload a Configuration Profile to Jamf Pro](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro).</span></span>


## <a name="step-10-schedule-scans-with-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="b7027-433">Paso 10: Programar exámenes con Microsoft Defender para endpoint en macOS</span><span class="sxs-lookup"><span data-stu-id="b7027-433">Step 10: Schedule scans with Microsoft Defender for Endpoint on macOS</span></span>
<span data-ttu-id="b7027-434">Siga las instrucciones de [Programar exámenes con Microsoft Defender para Endpoint en macOS](/windows/security/threat-protection/microsoft-defender-atp/mac-schedule-scan-atp).</span><span class="sxs-lookup"><span data-stu-id="b7027-434">Follow the instructions on [Schedule scans with Microsoft Defender for Endpoint on macOS](/windows/security/threat-protection/microsoft-defender-atp/mac-schedule-scan-atp).</span></span>


## <a name="step-11-deploy-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="b7027-435">Paso 11: Implementar Microsoft Defender para endpoint en macOS</span><span class="sxs-lookup"><span data-stu-id="b7027-435">Step 11: Deploy Microsoft Defender for Endpoint on macOS</span></span>

1. <span data-ttu-id="b7027-436">Navegue hasta donde guardó `wdav.pkg` .</span><span class="sxs-lookup"><span data-stu-id="b7027-436">Navigate to where you saved `wdav.pkg`.</span></span>

    ![Imagen del explorador de archivos wdav pkg](images/8dde76b5463047423f8637c86b05c29d.png)

2. <span data-ttu-id="b7027-438">Cámbiele el nombre a `wdav_MDM_Contoso_200329.pkg` .</span><span class="sxs-lookup"><span data-stu-id="b7027-438">Rename it to `wdav_MDM_Contoso_200329.pkg`.</span></span>

    ![Imagen del explorador de archivos1 wdavmdmpkg](images/fb2220fed3a530f4b3ef36f600da0c27.png)

3. <span data-ttu-id="b7027-440">Abra el panel de Pro Jamf.</span><span class="sxs-lookup"><span data-stu-id="b7027-440">Open the Jamf Pro dashboard.</span></span>

    ![Imagen de la configuración jamfpro](images/990742cd9a15ca9fdd37c9f695d1b9f4.png)

4. <span data-ttu-id="b7027-442">Seleccione el equipo y haga clic en el icono de engranaje en la parte superior y, a continuación, seleccione **Administración del equipo**.</span><span class="sxs-lookup"><span data-stu-id="b7027-442">Select your computer and click the gear icon at the top, then select **Computer Management**.</span></span>

    ![Imagen de la configuración compmgmt](images/b6d671b2f18b89d96c1c8e2ea1991242.png)

5. <span data-ttu-id="b7027-444">En **Paquetes**, seleccione **+ Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="b7027-444">In **Packages**, select **+ New**.</span></span> 
    <span data-ttu-id="b7027-445">![Una imagen que contiene el paquete de descripción de aves generado automáticamente](images/57aa4d21e2ccc65466bf284701d4e961.png)</span><span class="sxs-lookup"><span data-stu-id="b7027-445">![A picture containing bird Description automatically generated package new](images/57aa4d21e2ccc65466bf284701d4e961.png)</span></span>

6. <span data-ttu-id="b7027-446">En **Nuevo paquete,** escriba los siguientes detalles:</span><span class="sxs-lookup"><span data-stu-id="b7027-446">In **New Package** Enter the following details:</span></span>

    <span data-ttu-id="b7027-447">**Ficha General**</span><span class="sxs-lookup"><span data-stu-id="b7027-447">**General tab**</span></span>
    - <span data-ttu-id="b7027-448">Nombre para mostrar: déjelo en blanco por ahora.</span><span class="sxs-lookup"><span data-stu-id="b7027-448">Display Name: Leave it blank for now.</span></span> <span data-ttu-id="b7027-449">Porque se restablecerá al elegir el paquete.</span><span class="sxs-lookup"><span data-stu-id="b7027-449">Because it will be reset when you choose your pkg.</span></span>
    - <span data-ttu-id="b7027-450">Categoría: Ninguno (predeterminado)</span><span class="sxs-lookup"><span data-stu-id="b7027-450">Category: None (default)</span></span>
    - <span data-ttu-id="b7027-451">Filename: Choose File</span><span class="sxs-lookup"><span data-stu-id="b7027-451">Filename: Choose File</span></span>

    ![Imagen de la ficha general de configuración](images/21de3658bf58b1b767a17358a3f06341.png)

    <span data-ttu-id="b7027-453">Abra el archivo y apunte a `wdav.pkg` o `wdav_MDM_Contoso_200329.pkg` .</span><span class="sxs-lookup"><span data-stu-id="b7027-453">Open the file and point it to `wdav.pkg` or `wdav_MDM_Contoso_200329.pkg`.</span></span>
    
    ![Captura de pantalla de una pantalla de equipo Descripción generada automáticamente](images/1aa5aaa0a387f4e16ce55b66facc77d1.png)

7. <span data-ttu-id="b7027-455">Seleccione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="b7027-455">Select **Open**.</span></span> <span data-ttu-id="b7027-456">Establezca el **nombre para** mostrar en Protección contra amenazas avanzada de Microsoft Defender **y Antivirus de Microsoft Defender**.</span><span class="sxs-lookup"><span data-stu-id="b7027-456">Set the **Display Name** to **Microsoft Defender Advanced Threat Protection and Microsoft Defender Antivirus**.</span></span>

    <span data-ttu-id="b7027-457">**El archivo de** manifiesto no es necesario.</span><span class="sxs-lookup"><span data-stu-id="b7027-457">**Manifest File** is not required.</span></span> <span data-ttu-id="b7027-458">Microsoft Defender para endpoint funciona sin archivo de manifiesto.</span><span class="sxs-lookup"><span data-stu-id="b7027-458">Microsoft Defender for Endpoint works without Manifest File.</span></span>
    
    <span data-ttu-id="b7027-459">**Pestaña Opciones**</span><span class="sxs-lookup"><span data-stu-id="b7027-459">**Options tab**</span></span><br> <span data-ttu-id="b7027-460">Mantenga los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="b7027-460">Keep default values.</span></span>

    <span data-ttu-id="b7027-461">**Pestaña Limitaciones**</span><span class="sxs-lookup"><span data-stu-id="b7027-461">**Limitations tab**</span></span><br> <span data-ttu-id="b7027-462">Mantenga los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="b7027-462">Keep default values.</span></span>
    
     ![Imagen de la pestaña de limitación de configuración](images/56dac54634d13b2d3948ab50e8d3ef21.png)
   
8. <span data-ttu-id="b7027-464">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="b7027-464">Select **Save**.</span></span> <span data-ttu-id="b7027-465">El paquete se carga en Jamf Pro.</span><span class="sxs-lookup"><span data-stu-id="b7027-465">The package is uploaded to Jamf Pro.</span></span> 

   ![Imagen del paquete de configuración upl jamf pro](images/33f1ecdc7d4872555418bbc3efe4b7a3.png)

   <span data-ttu-id="b7027-467">El paquete puede tardar unos minutos en estar disponible para la implementación.</span><span class="sxs-lookup"><span data-stu-id="b7027-467">It can take a few minutes for the package to be available for deployment.</span></span>
   
   ![Imagen del paquete de configuración upl](images/1626d138e6309c6e87bfaab64f5ccf7b.png)

9. <span data-ttu-id="b7027-469">Vaya a la **página Directivas.**</span><span class="sxs-lookup"><span data-stu-id="b7027-469">Navigate to the **Policies** page.</span></span>

    ![Imagen de las opciones de configuración](images/f878f8efa5ebc92d069f4b8f79f62c7f.png)

10. <span data-ttu-id="b7027-471">Seleccione **+ Nuevo** para crear una nueva directiva.</span><span class="sxs-lookup"><span data-stu-id="b7027-471">Select **+ New** to create a new policy.</span></span>

    ![Imagen de la nueva directiva de configuración](images/847b70e54ed04787e415f5180414b310.png)


11. <span data-ttu-id="b7027-473">En **General,** escriba los siguientes detalles:</span><span class="sxs-lookup"><span data-stu-id="b7027-473">In **General** Enter the following details:</span></span>

    - <span data-ttu-id="b7027-474">Nombre para mostrar: MDATP incorporación de Contoso 200329 v100.86.92 o posterior</span><span class="sxs-lookup"><span data-stu-id="b7027-474">Display name: MDATP Onboarding Contoso 200329 v100.86.92 or later</span></span>

    ![<span data-ttu-id="b7027-475">Imagen de configuraciónmdatponboard</span><span class="sxs-lookup"><span data-stu-id="b7027-475">Image of configuration settingsmdatponboard</span></span> ](images/625ba6d19e8597f05e4907298a454d28.png)

12. <span data-ttu-id="b7027-476">Seleccione **Check-in periódico**.</span><span class="sxs-lookup"><span data-stu-id="b7027-476">Select **Recurring Check-in**.</span></span> 
    
    ![Imagen de la comprobación de la recursividad de las opciones de configuración](images/68bdbc5754dfc80aa1a024dde0fce7b0.png)

  
13. <span data-ttu-id="b7027-478">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="b7027-478">Select **Save**.</span></span> 
 
14. <span data-ttu-id="b7027-479">Seleccione **Paquetes > Configurar**.</span><span class="sxs-lookup"><span data-stu-id="b7027-479">Select **Packages > Configure**.</span></span>
 
    ![Imagen de configuración del paquete de configuración configurar](images/8fb4cc03721e1efb4a15867d5241ebfb.png)

15. <span data-ttu-id="b7027-481">Seleccione el **botón** Agregar junto **a Protección contra amenazas avanzada de Microsoft Defender y Antivirus de Microsoft Defender**.</span><span class="sxs-lookup"><span data-stu-id="b7027-481">Select the **Add** button next to **Microsoft Defender Advanced Threat Protection and Microsoft Defender Antivirus**.</span></span>

    ![Imagen de las opciones de configuración MDATP y MDA add](images/526b83fbdbb31265b3d0c1e5fbbdc33a.png)

16. <span data-ttu-id="b7027-483">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="b7027-483">Select **Save**.</span></span>

    ![Imagen de configuraciónsavimg](images/9d6e5386e652e00715ff348af72671c6.png)

17. <span data-ttu-id="b7027-485">Seleccione la **pestaña** Ámbito.</span><span class="sxs-lookup"><span data-stu-id="b7027-485">Select the **Scope** tab.</span></span>  

    ![Imagen de configuración scptab](images/8d80fe378a31143db9be0bacf7ddc5a3.png)

18. <span data-ttu-id="b7027-487">Seleccione los equipos de destino.</span><span class="sxs-lookup"><span data-stu-id="b7027-487">Select the target computers.</span></span>

    ![Imagen de configuración tgtcomp](images/6eda18a64a660fa149575454e54e7156.png)

    <span data-ttu-id="b7027-489">**Scope**</span><span class="sxs-lookup"><span data-stu-id="b7027-489">**Scope**</span></span>
    
    <span data-ttu-id="b7027-490">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="b7027-490">Select **Add**.</span></span>
    
    ![Imagen de configuración ad1img](images/1c08d097829863778d562c10c5f92b67.png)

    ![Imagen de las opciones de configuración ad2img](images/216253cbfb6ae738b9f13496b9c799fd.png)

    <span data-ttu-id="b7027-493">**Autoservicio**</span><span class="sxs-lookup"><span data-stu-id="b7027-493">**Self-Service**</span></span>
    
    ![Imagen de selfservice de configuración](images/c9f85bba3e96d627fe00fc5a8363b83a.png)

19. <span data-ttu-id="b7027-495">Seleccione **Listo**.</span><span class="sxs-lookup"><span data-stu-id="b7027-495">Select **Done**.</span></span> 

    ![Imagen de las opciones de configuración do1img](images/99679a7835b0d27d0a222bc3fdaf7f3b.png)

    ![Imagen de las opciones de configuración do2img](images/632aaab79ae18d0d2b8e0c16b6ba39e2.png)




