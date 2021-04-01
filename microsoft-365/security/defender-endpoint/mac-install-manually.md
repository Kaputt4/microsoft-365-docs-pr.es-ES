---
title: Implementación manual de Microsoft Defender para endpoint para macOS
description: Instale Microsoft Defender para Endpoint para macOS manualmente desde la línea de comandos.
keywords: microsoft, defender, atp, mac, installation, deploy, uninstallation, intune, jamf, macos, catalina, mojave, high sierra
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
ms.openlocfilehash: a9e75441a8c4a336e8c657d27330c118fcac4788
ms.sourcegitcommit: 7b8104015a76e02bc215e1cf08069979c70650ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "51476322"
---
# <a name="manual-deployment-for-microsoft-defender-for-endpoint-for-macos"></a><span data-ttu-id="109be-104">Implementación manual de Microsoft Defender para endpoint para macOS</span><span class="sxs-lookup"><span data-stu-id="109be-104">Manual deployment for Microsoft Defender for Endpoint for macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="109be-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="109be-105">**Applies to:**</span></span>
- [<span data-ttu-id="109be-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="109be-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="109be-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="109be-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="109be-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="109be-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="109be-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="109be-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="109be-110">En este tema se describe cómo implementar Microsoft Defender para Endpoint para macOS manualmente.</span><span class="sxs-lookup"><span data-stu-id="109be-110">This topic describes how to deploy Microsoft Defender for Endpoint for macOS manually.</span></span> <span data-ttu-id="109be-111">Una implementación correcta requiere la finalización de todos los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="109be-111">A successful deployment requires the completion of all of the following steps:</span></span>
- [<span data-ttu-id="109be-112">Descargar paquetes de instalación e incorporación</span><span class="sxs-lookup"><span data-stu-id="109be-112">Download installation and onboarding packages</span></span>](#download-installation-and-onboarding-packages)
- [<span data-ttu-id="109be-113">Instalación de aplicaciones (macOS 10.15 y versiones anteriores)</span><span class="sxs-lookup"><span data-stu-id="109be-113">Application installation (macOS 10.15 and older versions)</span></span>](#application-installation-macos-1015-and-older-versions)
- [<span data-ttu-id="109be-114">Instalación de aplicaciones (macOS 11 y versiones más recientes)</span><span class="sxs-lookup"><span data-stu-id="109be-114">Application installation (macOS 11 and newer versions)</span></span>](#application-installation-macos-11-and-newer-versions)
- [<span data-ttu-id="109be-115">Configuración de cliente</span><span class="sxs-lookup"><span data-stu-id="109be-115">Client configuration</span></span>](#client-configuration)

## <a name="prerequisites-and-system-requirements"></a><span data-ttu-id="109be-116">Requisitos previos y requisitos del sistema</span><span class="sxs-lookup"><span data-stu-id="109be-116">Prerequisites and system requirements</span></span>

<span data-ttu-id="109be-117">Antes de empezar, consulte la página principal de Microsoft Defender para endpoint [para macOS](microsoft-defender-endpoint-mac.md) para obtener una descripción de los requisitos previos y los requisitos del sistema para la versión de software actual.</span><span class="sxs-lookup"><span data-stu-id="109be-117">Before you get started, see [the main Microsoft Defender for Endpoint for macOS page](microsoft-defender-endpoint-mac.md) for a description of prerequisites and system requirements for the current software version.</span></span>

## <a name="download-installation-and-onboarding-packages"></a><span data-ttu-id="109be-118">Descargar paquetes de instalación e incorporación</span><span class="sxs-lookup"><span data-stu-id="109be-118">Download installation and onboarding packages</span></span>

<span data-ttu-id="109be-119">Descargue los paquetes de instalación e incorporación del Centro de seguridad de Microsoft Defender:</span><span class="sxs-lookup"><span data-stu-id="109be-119">Download the installation and onboarding packages from Microsoft Defender Security Center:</span></span>

1. <span data-ttu-id="109be-120">En el Centro de seguridad de Microsoft Defender, vaya **a Configuración > Administración de dispositivos > incorporación**.</span><span class="sxs-lookup"><span data-stu-id="109be-120">In Microsoft Defender Security Center, go to **Settings > Device Management > Onboarding**.</span></span>
2. <span data-ttu-id="109be-121">En la sección 1 de la página, establezca el sistema operativo en **macOS** y el método Deployment en **Script local**.</span><span class="sxs-lookup"><span data-stu-id="109be-121">In Section 1 of the page, set operating system to **macOS** and Deployment method to **Local script**.</span></span>
3. <span data-ttu-id="109be-122">En la sección 2 de la página, seleccione **Descargar paquete de instalación**.</span><span class="sxs-lookup"><span data-stu-id="109be-122">In Section 2 of the page, select **Download installation package**.</span></span> <span data-ttu-id="109be-123">Guárdelo como wdav.pkg en un directorio local.</span><span class="sxs-lookup"><span data-stu-id="109be-123">Save it as wdav.pkg to a local directory.</span></span>
4. <span data-ttu-id="109be-124">En la sección 2 de la página, seleccione **Descargar paquete de incorporación**.</span><span class="sxs-lookup"><span data-stu-id="109be-124">In Section 2 of the page, select **Download onboarding package**.</span></span> <span data-ttu-id="109be-125">Guárdelo WindowsDefenderATPOnboardingPackage.zip en el mismo directorio.</span><span class="sxs-lookup"><span data-stu-id="109be-125">Save it as WindowsDefenderATPOnboardingPackage.zip to the same directory.</span></span>

    ![Captura de pantalla del Centro de seguridad de Microsoft Defender](images/atp-portal-onboarding-page.png)

5. <span data-ttu-id="109be-127">Desde un símbolo del sistema, compruebe que tiene los dos archivos.</span><span class="sxs-lookup"><span data-stu-id="109be-127">From a command prompt, verify that you have the two files.</span></span>
    
## <a name="application-installation-macos-1015-and-older-versions"></a><span data-ttu-id="109be-128">Instalación de aplicaciones (macOS 10.15 y versiones anteriores)</span><span class="sxs-lookup"><span data-stu-id="109be-128">Application installation (macOS 10.15 and older versions)</span></span>

<span data-ttu-id="109be-129">Para completar este proceso, debes tener privilegios de administrador en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="109be-129">To complete this process, you must have admin privileges on the device.</span></span>

1. <span data-ttu-id="109be-130">Navegue hasta el wdav.pkg descargado en Finder y ábralo.</span><span class="sxs-lookup"><span data-stu-id="109be-130">Navigate to the downloaded wdav.pkg in Finder and open it.</span></span>

    ![Captura de pantalla de instalación de aplicaciones1](images/mdatp-28-appinstall.png)

2. <span data-ttu-id="109be-132">Seleccione **Continuar,** acepte los términos de licencia y escriba la contraseña cuando se le pida.</span><span class="sxs-lookup"><span data-stu-id="109be-132">Select **Continue**, agree with the License terms, and enter the password when prompted.</span></span>

    ![Captura de pantalla de instalación de la aplicación2](images/mdatp-29-appinstalllogin.png)

   > [!IMPORTANT]
   > <span data-ttu-id="109be-134">Se le pedirá que permita que se instale un controlador de Microsoft (ya sea "System Extension Blocked" o "Installation is on hold" o ambos.</span><span class="sxs-lookup"><span data-stu-id="109be-134">You will be prompted to allow a driver from Microsoft to be installed (either "System Extension Blocked" or "Installation is on hold" or both.</span></span> <span data-ttu-id="109be-135">Se debe permitir la instalación del controlador.</span><span class="sxs-lookup"><span data-stu-id="109be-135">The driver must be allowed to be installed.</span></span>

   ![Captura de pantalla de instalación de la aplicación3](images/mdatp-30-systemextension.png)

3. <span data-ttu-id="109be-137">Seleccione **Abrir preferencias de seguridad** o Abrir preferencias del sistema > Seguridad & **privacidad**.</span><span class="sxs-lookup"><span data-stu-id="109be-137">Select **Open Security Preferences** or **Open System Preferences > Security & Privacy**.</span></span> <span data-ttu-id="109be-138">Seleccione **Permitir**:</span><span class="sxs-lookup"><span data-stu-id="109be-138">Select **Allow**:</span></span>

    ![Captura de pantalla de la ventana seguridad y privacidad](images/mdatp-31-securityprivacysettings.png)

   <span data-ttu-id="109be-140">La instalación continúa.</span><span class="sxs-lookup"><span data-stu-id="109be-140">The installation proceeds.</span></span>

   > [!CAUTION]
   > <span data-ttu-id="109be-141">Si no selecciona **Permitir,** la instalación continuará después de 5 minutos.</span><span class="sxs-lookup"><span data-stu-id="109be-141">If you don't select **Allow**, the installation will proceed after 5 minutes.</span></span> <span data-ttu-id="109be-142">Microsoft Defender para endpoint se cargará, pero algunas características, como la protección en tiempo real, se deshabilitarán.</span><span class="sxs-lookup"><span data-stu-id="109be-142">Microsoft Defender for Endpoint will be loaded, but some features, such as real-time protection, will be disabled.</span></span> <span data-ttu-id="109be-143">Consulte [Solucionar problemas de extensión del kernel](mac-support-kext.md) para obtener información sobre cómo resolver esto.</span><span class="sxs-lookup"><span data-stu-id="109be-143">See [Troubleshoot kernel extension issues](mac-support-kext.md) for information on how to resolve this.</span></span>

> [!NOTE]
> <span data-ttu-id="109be-144">macOS puede solicitar reiniciar el dispositivo tras la primera instalación de Microsoft Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="109be-144">macOS may request to reboot the device upon the first installation of Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="109be-145">La protección en tiempo real no estará disponible hasta que se reinicie el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="109be-145">Real-time protection will not be available until the device is rebooted.</span></span>

## <a name="application-installation-macos-11-and-newer-versions"></a><span data-ttu-id="109be-146">Instalación de aplicaciones (macOS 11 y versiones más recientes)</span><span class="sxs-lookup"><span data-stu-id="109be-146">Application installation (macOS 11 and newer versions)</span></span>

<span data-ttu-id="109be-147">Para completar este proceso, debes tener privilegios de administrador en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="109be-147">To complete this process, you must have admin privileges on the device.</span></span>

1. <span data-ttu-id="109be-148">Navegue hasta el wdav.pkg descargado en Finder y ábralo.</span><span class="sxs-lookup"><span data-stu-id="109be-148">Navigate to the downloaded wdav.pkg in Finder and open it.</span></span>

    ![Captura de pantalla de instalación de la aplicación4](images/big-sur-install-1.png)

2. <span data-ttu-id="109be-150">Seleccione **Continuar,** acepte los términos de licencia y escriba la contraseña cuando se le pida.</span><span class="sxs-lookup"><span data-stu-id="109be-150">Select **Continue**, agree with the License terms, and enter the password when prompted.</span></span>

3. <span data-ttu-id="109be-151">Al final del proceso de instalación, se te promocionará para aprobar las extensiones del sistema usadas por el producto.</span><span class="sxs-lookup"><span data-stu-id="109be-151">At the end of the installation process, you'll be promoted to approve the system extensions used by the product.</span></span> <span data-ttu-id="109be-152">Seleccione **Abrir preferencias de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="109be-152">Select **Open Security Preferences**.</span></span>

    ![Aprobación de extensión del sistema](images/big-sur-install-2.png)

4. <span data-ttu-id="109be-154">En la **ventana Seguridad & privacidad,** seleccione **Permitir**.</span><span class="sxs-lookup"><span data-stu-id="109be-154">From the **Security & Privacy** window, select **Allow**.</span></span>

    ![Preferencias de seguridad de extensión del sistema1](images/big-sur-install-3.png)

5. <span data-ttu-id="109be-156">Repita los pasos 3 & 4 para todas las extensiones del sistema distribuidas con Microsoft Defender para Endpoint para Mac.</span><span class="sxs-lookup"><span data-stu-id="109be-156">Repeat steps 3 & 4 for all system extensions distributed with Microsoft Defender for Endpoint for Mac.</span></span>

6. <span data-ttu-id="109be-157">Como parte de las capacidades de detección y respuesta de puntos de conexión, Microsoft Defender para Endpoint para Mac inspecciona el tráfico de sockets e informa de esta información al portal del Centro de seguridad de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="109be-157">As part of the Endpoint Detection and Response capabilities, Microsoft Defender for Endpoint for Mac inspects socket traffic and reports this information to the Microsoft Defender Security Center portal.</span></span> <span data-ttu-id="109be-158">Cuando se le pida que conceda a Microsoft Defender permisos de extremo para filtrar el tráfico de red, seleccione **Permitir**.</span><span class="sxs-lookup"><span data-stu-id="109be-158">When prompted to grant Microsoft Defender for Endpoint permissions to filter network traffic, select **Allow**.</span></span>

    ![Preferencias de seguridad de extensión del sistema2](images/big-sur-install-4.png)

7. <span data-ttu-id="109be-160">Abra **System Preferences** Security & Privacidad y vaya a la pestaña Privacidad. Conceda permiso de acceso en disco completo a Atp de Microsoft Defender y Extensión de seguridad de punto de conexión de ATP de Microsoft  >   **Defender.**   </span><span class="sxs-lookup"><span data-stu-id="109be-160">Open **System Preferences** > **Security & Privacy** and navigate to the **Privacy** tab. Grant **Full Disk Access** permission to **Microsoft Defender ATP** and **Microsoft Defender ATP Endpoint Security Extension**.</span></span>

    ![Acceso en disco completo](images/big-sur-install-5.png)

## <a name="client-configuration"></a><span data-ttu-id="109be-162">Configuración de clientes</span><span class="sxs-lookup"><span data-stu-id="109be-162">Client configuration</span></span>

1. <span data-ttu-id="109be-163">Copia wdav.pkg y MicrosoftDefenderATPOnboardingMacOs.py en el dispositivo donde implementas Microsoft Defender para Endpoint para macOS.</span><span class="sxs-lookup"><span data-stu-id="109be-163">Copy wdav.pkg and MicrosoftDefenderATPOnboardingMacOs.py to the device where you deploy Microsoft Defender for Endpoint for macOS.</span></span>

    <span data-ttu-id="109be-164">El dispositivo cliente no está asociado con org_id.</span><span class="sxs-lookup"><span data-stu-id="109be-164">The client device isn't associated with org_id.</span></span> <span data-ttu-id="109be-165">Tenga en cuenta *que el org_id* está en blanco.</span><span class="sxs-lookup"><span data-stu-id="109be-165">Note that the *org_id* attribute is blank.</span></span>

    ```bash
    mdatp health --field org_id
    ```

2. <span data-ttu-id="109be-166">Ejecute el script de Python para instalar el archivo de configuración:</span><span class="sxs-lookup"><span data-stu-id="109be-166">Run the Python script to install the configuration file:</span></span>

    ```bash
    /usr/bin/python MicrosoftDefenderATPOnboardingMacOs.py
    ```

3. <span data-ttu-id="109be-167">Compruebe que el dispositivo esté asociado a su organización e informe de un identificador de organización válido:</span><span class="sxs-lookup"><span data-stu-id="109be-167">Verify that the device is now associated with your organization and reports a valid org ID:</span></span>

    ```bash
    mdatp health --field org_id
    ```

    <span data-ttu-id="109be-168">Después de la instalación, verás el icono de Microsoft Defender en la barra de estado de macOS en la esquina superior derecha.</span><span class="sxs-lookup"><span data-stu-id="109be-168">After installation, you'll see the Microsoft Defender icon in the macOS status bar in the top-right corner.</span></span>
    
    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="109be-169">![Icono de Microsoft Defender en la captura de pantalla de la barra de estado](images/mdatp-icon-bar.png)</span><span class="sxs-lookup"><span data-stu-id="109be-169">![Microsoft Defender icon in status bar screenshot](images/mdatp-icon-bar.png)</span></span>


## <a name="how-to-allow-full-disk-access"></a><span data-ttu-id="109be-170">Cómo permitir el acceso en disco completo</span><span class="sxs-lookup"><span data-stu-id="109be-170">How to Allow Full Disk Access</span></span>

> [!CAUTION]
> <span data-ttu-id="109be-171">macOS 10.15 (Catalina) contiene nuevas mejoras de seguridad y privacidad.</span><span class="sxs-lookup"><span data-stu-id="109be-171">macOS 10.15 (Catalina) contains new security and privacy enhancements.</span></span> <span data-ttu-id="109be-172">A partir de esta versión, de forma predeterminada, las aplicaciones no pueden acceder a determinadas ubicaciones del disco (como Documentos, Descargas, Escritorio, etc.) sin consentimiento explícito.</span><span class="sxs-lookup"><span data-stu-id="109be-172">Beginning with this version, by default, applications are not able to access certain locations on disk (such as Documents, Downloads, Desktop, etc.) without explicit consent.</span></span> <span data-ttu-id="109be-173">En ausencia de este consentimiento, Microsoft Defender para Endpoint no puede proteger completamente el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="109be-173">In the absence of this consent, Microsoft Defender for Endpoint is not able to fully protect your device.</span></span>

1. <span data-ttu-id="109be-174">Para conceder el consentimiento, abra **Preferencias** del  >  **sistema Seguridad & Privacidad**  >  **Acceso** completo al  >  **disco**.</span><span class="sxs-lookup"><span data-stu-id="109be-174">To grant consent, open **System Preferences** > **Security & Privacy** > **Privacy** > **Full Disk Access**.</span></span> <span data-ttu-id="109be-175">Haga clic en el icono de bloqueo para realizar cambios (parte inferior del cuadro de diálogo).</span><span class="sxs-lookup"><span data-stu-id="109be-175">Click the lock icon to make changes (bottom of the dialog box).</span></span> <span data-ttu-id="109be-176">Seleccione Microsoft Defender para Endpoint.</span><span class="sxs-lookup"><span data-stu-id="109be-176">Select Microsoft Defender for Endpoint.</span></span>

2. <span data-ttu-id="109be-177">Ejecute una prueba de detección de ANTIVIRUS para comprobar que el dispositivo está correctamente incorporado e informando al servicio.</span><span class="sxs-lookup"><span data-stu-id="109be-177">Run an AV detection test to verify that the device is properly onboarded and reporting to the service.</span></span> <span data-ttu-id="109be-178">Realice los pasos siguientes en el dispositivo recién incorporado:</span><span class="sxs-lookup"><span data-stu-id="109be-178">Perform the following steps on the newly onboarded device:</span></span>

    1. <span data-ttu-id="109be-179">Asegúrese de que la protección en tiempo real está habilitada (lo indica un resultado de 1 al ejecutar el siguiente comando):</span><span class="sxs-lookup"><span data-stu-id="109be-179">Ensure that real-time protection is enabled (denoted by a result of 1 from running the following command):</span></span>

        ```bash
        mdatp health --field real_time_protection_enabled
        ```

    1. <span data-ttu-id="109be-180">Abra una ventana terminal.</span><span class="sxs-lookup"><span data-stu-id="109be-180">Open a Terminal window.</span></span> <span data-ttu-id="109be-181">Copie y ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="109be-181">Copy and execute the following command:</span></span>

        ```bash
        curl -o ~/Downloads/eicar.com.txt https://www.eicar.org/download/eicar.com.txt
        ```

    1. <span data-ttu-id="109be-182">Defender for Endpoint for Mac debería haber puesto el archivo en cuarentena.</span><span class="sxs-lookup"><span data-stu-id="109be-182">The file should have been quarantined by Defender for Endpoint for Mac.</span></span> <span data-ttu-id="109be-183">Use el siguiente comando para enumerar todas las amenazas detectadas:</span><span class="sxs-lookup"><span data-stu-id="109be-183">Use the following command to list all the detected threats:</span></span>

        ```bash
        mdatp threat list
        ```

3. <span data-ttu-id="109be-184">Ejecute una prueba de detección de EDR para comprobar que el dispositivo está correctamente incorporado e informando al servicio.</span><span class="sxs-lookup"><span data-stu-id="109be-184">Run an EDR detection test to verify that the device is properly onboarded and reporting to the service.</span></span> <span data-ttu-id="109be-185">Realice los pasos siguientes en el dispositivo recién incorporado:</span><span class="sxs-lookup"><span data-stu-id="109be-185">Perform the following steps on the newly onboarded device:</span></span>

   1. <span data-ttu-id="109be-186">En el explorador, como Microsoft Edge para Mac o Safari.</span><span class="sxs-lookup"><span data-stu-id="109be-186">In your browser such as Microsoft Edge for Mac or Safari.</span></span>

   1. <span data-ttu-id="109be-187">Descargue MDATP MacOS DIY.zip https://aka.ms/mdatpmacosdiy y extraiga.</span><span class="sxs-lookup"><span data-stu-id="109be-187">Download MDATP MacOS DIY.zip from https://aka.ms/mdatpmacosdiy and extract.</span></span>

      <span data-ttu-id="109be-188">Es posible que se le pida lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="109be-188">You may be prompted:</span></span>

      > <span data-ttu-id="109be-189">¿Desea permitir descargas en "mdatpclientanalyzer.blob.core.windows.net"?</span><span class="sxs-lookup"><span data-stu-id="109be-189">Do you want to allow downloads on "mdatpclientanalyzer.blob.core.windows.net"?</span></span><br/>
      > <span data-ttu-id="109be-190">Puede cambiar los sitios web que pueden descargar archivos en Preferencias de sitios web.</span><span class="sxs-lookup"><span data-stu-id="109be-190">You can change which websites can download files in Websites Preferences.</span></span>

4. <span data-ttu-id="109be-191">Haga clic **en Permitir**.</span><span class="sxs-lookup"><span data-stu-id="109be-191">Click **Allow**.</span></span>

5. <span data-ttu-id="109be-192">Abra **Descargas**.</span><span class="sxs-lookup"><span data-stu-id="109be-192">Open **Downloads**.</span></span>

6. <span data-ttu-id="109be-193">Debería ver **MDATP MacOS DIY**.</span><span class="sxs-lookup"><span data-stu-id="109be-193">You should see **MDATP MacOS DIY**.</span></span>

   > [!TIP]
   > <span data-ttu-id="109be-194">Si hace doble clic, recibirá el siguiente mensaje:</span><span class="sxs-lookup"><span data-stu-id="109be-194">If you double-click, you will get the following message:</span></span>
   > 
   > > <span data-ttu-id="109be-195">**"MDATP MacOS DIY" no se puede abrir porque el desarrollador no puede ser verificador.**</span><span class="sxs-lookup"><span data-stu-id="109be-195">**"MDATP MacOS DIY" cannot be opened because the developer cannot be verifier.**</span></span><br/>
   > > <span data-ttu-id="109be-196">macOS no puede comprobar que esta aplicación está libre de malware.</span><span class="sxs-lookup"><span data-stu-id="109be-196">macOS cannot verify that this app is free from malware.</span></span><br/>
   > > <span data-ttu-id="109be-197">**\[ Pasar a \] Cancelar papelera** **\[ \]**</span><span class="sxs-lookup"><span data-stu-id="109be-197">**\[Move to Trash\]** **\[Cancel\]**</span></span> 
  
7. <span data-ttu-id="109be-198">Haga clic en **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="109be-198">Click **Cancel**.</span></span>

8. <span data-ttu-id="109be-199">Haga clic con el botón **secundario en MDATP MacOS DIY** y, a continuación, haga clic en **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="109be-199">Right-click **MDATP MacOS DIY**, and then click **Open**.</span></span> 

    <span data-ttu-id="109be-200">El sistema debe mostrar el siguiente mensaje:</span><span class="sxs-lookup"><span data-stu-id="109be-200">The system should display the following message:</span></span>

    > <span data-ttu-id="109be-201">**macOS no puede comprobar el desarrollador de **MDATP MacOS DIY**. ¿Está seguro de que desea abrirlo?**</span><span class="sxs-lookup"><span data-stu-id="109be-201">**macOS cannot verify the developer of **MDATP MacOS DIY**. Are you sure you want to open it?**</span></span><br/>
    > <span data-ttu-id="109be-202">Al abrir esta aplicación, invalidará la seguridad del sistema, que puede exponer su equipo y su información personal a malware que pueda dañar su Mac o poner en peligro su privacidad.</span><span class="sxs-lookup"><span data-stu-id="109be-202">By opening this app, you will be overriding system security which can expose your computer and personal information to malware that may harm your Mac or compromise your privacy.</span></span>

10. <span data-ttu-id="109be-203">Haga clic en **Open** (Abrir).</span><span class="sxs-lookup"><span data-stu-id="109be-203">Click **Open**.</span></span>

    <span data-ttu-id="109be-204">El sistema debe mostrar el siguiente mensaje:</span><span class="sxs-lookup"><span data-stu-id="109be-204">The system should display the following message:</span></span>

    > <span data-ttu-id="109be-205">ATP de Microsoft Defender: archivo de prueba de BRICOLAJE de macOS EDR</span><span class="sxs-lookup"><span data-stu-id="109be-205">Microsoft Defender ATP - macOS EDR DIY test file</span></span><br/>
    > <span data-ttu-id="109be-206">La alerta correspondiente estará disponible en el portal MDATP.</span><span class="sxs-lookup"><span data-stu-id="109be-206">Corresponding alert will be available in the MDATP portal.</span></span>

11. <span data-ttu-id="109be-207">Haga clic en **Open** (Abrir).</span><span class="sxs-lookup"><span data-stu-id="109be-207">Click **Open**.</span></span>

    <span data-ttu-id="109be-208">En unos minutos se debe generar una alerta denominada "alerta de prueba de macOS EDR".</span><span class="sxs-lookup"><span data-stu-id="109be-208">In a few minutes an alert named "macOS EDR Test Alert" should be raised.</span></span>

12. <span data-ttu-id="109be-209">Vaya al Centro de seguridad de Microsoft Defender ( https://SecurityCenter.microsoft.com) .</span><span class="sxs-lookup"><span data-stu-id="109be-209">Go to Microsoft Defender Security Center (https://SecurityCenter.microsoft.com).</span></span>

13. <span data-ttu-id="109be-210">Vaya a la cola de alertas.</span><span class="sxs-lookup"><span data-stu-id="109be-210">Go to the Alert Queue.</span></span>

    :::image type="content" source="images/b8db76c2-c368-49ad-970f-dcb87534d9be.png" alt-text="Ejemplo de una alerta de prueba de macOS EDR que muestra gravedad, categoría, origen de detección y un menú de acciones contraído.":::
    
    <span data-ttu-id="109be-212">Consulta los detalles de la alerta y la escala de tiempo del dispositivo y realiza los pasos de investigación habituales.</span><span class="sxs-lookup"><span data-stu-id="109be-212">Look at the alert details and the device timeline, and perform the regular investigation steps.</span></span>

## <a name="logging-installation-issues"></a><span data-ttu-id="109be-213">Problemas de instalación de registro</span><span class="sxs-lookup"><span data-stu-id="109be-213">Logging installation issues</span></span>

<span data-ttu-id="109be-214">Consulte [Problemas de instalación de registro](mac-resources.md#logging-installation-issues) para obtener más información sobre cómo encontrar el registro generado automáticamente que crea el instalador cuando se produce un error.</span><span class="sxs-lookup"><span data-stu-id="109be-214">See [Logging installation issues](mac-resources.md#logging-installation-issues) for more information on how to find the automatically generated log that is created by the installer when an error occurs.</span></span>

## <a name="uninstallation"></a><span data-ttu-id="109be-215">Desinstalación</span><span class="sxs-lookup"><span data-stu-id="109be-215">Uninstallation</span></span>

<span data-ttu-id="109be-216">Consulta [Desinstalar para obtener](mac-resources.md#uninstalling) más información sobre cómo quitar Microsoft Defender para Endpoint para macOS de los dispositivos cliente.</span><span class="sxs-lookup"><span data-stu-id="109be-216">See [Uninstalling](mac-resources.md#uninstalling) for details on how to remove Microsoft Defender for Endpoint for macOS from client devices.</span></span>
