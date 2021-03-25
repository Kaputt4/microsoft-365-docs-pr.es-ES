---
title: Implementación basada en Intune para ATP de Microsoft Defender para Mac
description: Instale Microsoft Defender para Endpoint para Mac con Microsoft Intune.
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
ms.openlocfilehash: cb2923c3f2cb3f27a864fdc3c5070107998823d5
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51074883"
---
# <a name="intune-based-deployment-for-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="264bf-104">Implementación basada en Intune para Microsoft Defender para Endpoint para Mac</span><span class="sxs-lookup"><span data-stu-id="264bf-104">Intune-based deployment for Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


> [!NOTE]
> <span data-ttu-id="264bf-105">En esta documentación se explica el método heredado para implementar y configurar Microsoft Defender para Endpoint en dispositivos macOS.</span><span class="sxs-lookup"><span data-stu-id="264bf-105">This documentation explains the legacy method for deploying and configuring Microsoft Defender for Endpoint on macOS devices.</span></span> <span data-ttu-id="264bf-106">La experiencia nativa ya está disponible en la consola de MEM.</span><span class="sxs-lookup"><span data-stu-id="264bf-106">The native experience is now available in the MEM console.</span></span> <span data-ttu-id="264bf-107">La versión de la interfaz de usuario nativa en la consola de MEM proporciona a los administradores una forma mucho más sencilla de configurar e implementar la aplicación y enviarla a dispositivos macOS.</span><span class="sxs-lookup"><span data-stu-id="264bf-107">The release of the native UI in the MEM console provide admins with a much simpler way to configure and deploy the application and send it down to macOS devices.</span></span> <br> <br>
><span data-ttu-id="264bf-108">La entrada de blog [MEM simplifica la implementación de Microsoft Defender para endpoint para macOS](https://techcommunity.microsoft.com/t5/microsoft-endpoint-manager-blog/microsoft-endpoint-manager-simplifies-deployment-of-microsoft/ba-p/1322995) explica las nuevas características.</span><span class="sxs-lookup"><span data-stu-id="264bf-108">The blog post [MEM simplifies deployment of Microsoft Defender for Endpoint for macOS](https://techcommunity.microsoft.com/t5/microsoft-endpoint-manager-blog/microsoft-endpoint-manager-simplifies-deployment-of-microsoft/ba-p/1322995) explains the new features.</span></span> <span data-ttu-id="264bf-109">Para configurar la aplicación, ve a [Configuración de Microsoft Defender para Endpoint para Mac en Microsoft InTune](https://docs.microsoft.com/mem/intune/protect/antivirus-microsoft-defender-settings-macos).</span><span class="sxs-lookup"><span data-stu-id="264bf-109">To configure the app, go to [Settings for Microsoft Defender for Endpoint for Mac in Microsoft InTune](https://docs.microsoft.com/mem/intune/protect/antivirus-microsoft-defender-settings-macos).</span></span> <span data-ttu-id="264bf-110">Para implementar la aplicación, vaya [a Agregar Microsoft Defender para endpoint a dispositivos macOS con Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/apps-advanced-threat-protection-macos).</span><span class="sxs-lookup"><span data-stu-id="264bf-110">To deploy the app, go to [Add Microsoft Defender for Endpoint to macOS devices using Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/apps-advanced-threat-protection-macos).</span></span>

<span data-ttu-id="264bf-111">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="264bf-111">**Applies to:**</span></span>

- [<span data-ttu-id="264bf-112">Microsoft Defender para endpoint para Mac</span><span class="sxs-lookup"><span data-stu-id="264bf-112">Microsoft Defender for Endpoint for Mac</span></span>](microsoft-defender-endpoint-mac.md)

<span data-ttu-id="264bf-113">En este tema se describe cómo implementar Microsoft Defender para Endpoint para Mac a través de Intune.</span><span class="sxs-lookup"><span data-stu-id="264bf-113">This topic describes how to deploy Microsoft Defender for Endpoint for Mac through Intune.</span></span> <span data-ttu-id="264bf-114">Una implementación correcta requiere la finalización de todos los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="264bf-114">A successful deployment requires the completion of all of the following steps:</span></span>

1. [<span data-ttu-id="264bf-115">Descargar paquetes de instalación e incorporación</span><span class="sxs-lookup"><span data-stu-id="264bf-115">Download installation and onboarding packages</span></span>](#download-installation-and-onboarding-packages)
1. [<span data-ttu-id="264bf-116">Configuración del dispositivo cliente</span><span class="sxs-lookup"><span data-stu-id="264bf-116">Client device setup</span></span>](#client-device-setup)
1. [<span data-ttu-id="264bf-117">Aprobar extensiones del sistema</span><span class="sxs-lookup"><span data-stu-id="264bf-117">Approve system extensions</span></span>](#approve-system-extensions)
1. [<span data-ttu-id="264bf-118">Crear perfiles de configuración del sistema</span><span class="sxs-lookup"><span data-stu-id="264bf-118">Create System Configuration profiles</span></span>](#create-system-configuration-profiles)
1. [<span data-ttu-id="264bf-119">Publicar aplicación</span><span class="sxs-lookup"><span data-stu-id="264bf-119">Publish application</span></span>](#publish-application)

## <a name="prerequisites-and-system-requirements"></a><span data-ttu-id="264bf-120">Requisitos previos y requisitos del sistema</span><span class="sxs-lookup"><span data-stu-id="264bf-120">Prerequisites and system requirements</span></span>

<span data-ttu-id="264bf-121">Antes de empezar, consulta la página principal de [Microsoft Defender para](microsoft-defender-endpoint-mac.md) Endpoint para Mac para obtener una descripción de los requisitos previos y los requisitos del sistema para la versión de software actual.</span><span class="sxs-lookup"><span data-stu-id="264bf-121">Before you get started, see [the main Microsoft Defender for Endpoint for Mac page](microsoft-defender-endpoint-mac.md) for a description of prerequisites and system requirements for the current software version.</span></span>

## <a name="overview"></a><span data-ttu-id="264bf-122">Información general</span><span class="sxs-lookup"><span data-stu-id="264bf-122">Overview</span></span>

<span data-ttu-id="264bf-123">En la tabla siguiente se resumen los pasos que debe seguir para implementar y administrar Microsoft Defender para Endpoint for Macs, a través de Intune.</span><span class="sxs-lookup"><span data-stu-id="264bf-123">The following table summarizes the steps you would need to take to deploy and manage Microsoft Defender for Endpoint for Macs, via Intune.</span></span> <span data-ttu-id="264bf-124">Los pasos más detallados están disponibles a continuación.</span><span class="sxs-lookup"><span data-stu-id="264bf-124">More detailed steps are available below.</span></span>

| <span data-ttu-id="264bf-125">Paso</span><span class="sxs-lookup"><span data-stu-id="264bf-125">Step</span></span> | <span data-ttu-id="264bf-126">Nombres de archivo de ejemplo</span><span class="sxs-lookup"><span data-stu-id="264bf-126">Sample file names</span></span> | <span data-ttu-id="264bf-127">BundleIdentifier</span><span class="sxs-lookup"><span data-stu-id="264bf-127">BundleIdentifier</span></span> |
|-|-|-|
| [<span data-ttu-id="264bf-128">Descargar paquetes de instalación e incorporación</span><span class="sxs-lookup"><span data-stu-id="264bf-128">Download installation and onboarding packages</span></span>](#download-installation-and-onboarding-packages) | <span data-ttu-id="264bf-129">WindowsDefenderATPOnboarding__MDATP_wdav.atp.xml</span><span class="sxs-lookup"><span data-stu-id="264bf-129">WindowsDefenderATPOnboarding__MDATP_wdav.atp.xml</span></span> | <span data-ttu-id="264bf-130">com.microsoft.wdav.atp</span><span class="sxs-lookup"><span data-stu-id="264bf-130">com.microsoft.wdav.atp</span></span> |
| [<span data-ttu-id="264bf-131">Aprobar extensión del sistema para Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="264bf-131">Approve System Extension for Microsoft Defender for Endpoint</span></span>](#approve-system-extensions) | <span data-ttu-id="264bf-132">MDATP_SysExt.xml</span><span class="sxs-lookup"><span data-stu-id="264bf-132">MDATP_SysExt.xml</span></span> | <span data-ttu-id="264bf-133">N/D</span><span class="sxs-lookup"><span data-stu-id="264bf-133">N/A</span></span> |
| [<span data-ttu-id="264bf-134">Aprobar extensión de kernel para Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="264bf-134">Approve Kernel Extension for Microsoft Defender for Endpoint</span></span>](#download-installation-and-onboarding-packages) | <span data-ttu-id="264bf-135">MDATP_KExt.xml</span><span class="sxs-lookup"><span data-stu-id="264bf-135">MDATP_KExt.xml</span></span> | <span data-ttu-id="264bf-136">N/D</span><span class="sxs-lookup"><span data-stu-id="264bf-136">N/A</span></span> |
| [<span data-ttu-id="264bf-137">Conceder acceso en disco completo a Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="264bf-137">Grant full disk access to Microsoft Defender for Endpoint</span></span>](#create-system-configuration-profiles-step-8) | <span data-ttu-id="264bf-138">MDATP_tcc_Catalina_or_newer.xml</span><span class="sxs-lookup"><span data-stu-id="264bf-138">MDATP_tcc_Catalina_or_newer.xml</span></span> | <span data-ttu-id="264bf-139">com.microsoft.wdav.tcc</span><span class="sxs-lookup"><span data-stu-id="264bf-139">com.microsoft.wdav.tcc</span></span> |
| [<span data-ttu-id="264bf-140">Directiva de extensión de red</span><span class="sxs-lookup"><span data-stu-id="264bf-140">Network Extension policy</span></span>](#create-system-configuration-profiles-step-9) | <span data-ttu-id="264bf-141">MDATP_NetExt.xml</span><span class="sxs-lookup"><span data-stu-id="264bf-141">MDATP_NetExt.xml</span></span> | <span data-ttu-id="264bf-142">N/D</span><span class="sxs-lookup"><span data-stu-id="264bf-142">N/A</span></span> |
| [<span data-ttu-id="264bf-143">Configurar Microsoft AutoUpdate (MAU)</span><span class="sxs-lookup"><span data-stu-id="264bf-143">Configure Microsoft AutoUpdate (MAU)</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/mac-updates#intune) | <span data-ttu-id="264bf-144">MDATP_Microsoft_AutoUpdate.xml</span><span class="sxs-lookup"><span data-stu-id="264bf-144">MDATP_Microsoft_AutoUpdate.xml</span></span> | <span data-ttu-id="264bf-145">com.microsoft.autoupdate2</span><span class="sxs-lookup"><span data-stu-id="264bf-145">com.microsoft.autoupdate2</span></span> |
| [<span data-ttu-id="264bf-146">Configuración de Microsoft Defender para puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="264bf-146">Microsoft Defender for Endpoint configuration settings</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/mac-preferences#intune-profile-1)<br/><br/> <span data-ttu-id="264bf-147">**Nota:** Si está planeando ejecutar un ANTIVIRUS de terceros para macOS, establezca `passiveMode` en `true` .</span><span class="sxs-lookup"><span data-stu-id="264bf-147">**Note:** If you are planning to run a third-party AV for macOS, set `passiveMode` to `true`.</span></span> | <span data-ttu-id="264bf-148">MDATP_WDAV_and_exclusion_settings_Preferences.xml</span><span class="sxs-lookup"><span data-stu-id="264bf-148">MDATP_WDAV_and_exclusion_settings_Preferences.xml</span></span> | <span data-ttu-id="264bf-149">com.microsoft.wdav</span><span class="sxs-lookup"><span data-stu-id="264bf-149">com.microsoft.wdav</span></span> |
| [<span data-ttu-id="264bf-150">Configurar Microsoft Defender para notificaciones de punto de conexión y MS AutoUpdate (MAU)</span><span class="sxs-lookup"><span data-stu-id="264bf-150">Configure Microsoft Defender for Endpoint and MS AutoUpdate (MAU) notifications</span></span>](#create-system-configuration-profiles-step-10) | <span data-ttu-id="264bf-151">MDATP_MDAV_Tray_and_AutoUpdate2.mobileconfig</span><span class="sxs-lookup"><span data-stu-id="264bf-151">MDATP_MDAV_Tray_and_AutoUpdate2.mobileconfig</span></span> | <span data-ttu-id="264bf-152">com.microsoft.autoupdate2 o com.microsoft.wdav.tray</span><span class="sxs-lookup"><span data-stu-id="264bf-152">com.microsoft.autoupdate2 or com.microsoft.wdav.tray</span></span> |

## <a name="download-installation-and-onboarding-packages"></a><span data-ttu-id="264bf-153">Descargar paquetes de instalación e incorporación</span><span class="sxs-lookup"><span data-stu-id="264bf-153">Download installation and onboarding packages</span></span>

<span data-ttu-id="264bf-154">Descargue los paquetes de instalación e incorporación del Centro de seguridad de Microsoft Defender:</span><span class="sxs-lookup"><span data-stu-id="264bf-154">Download the installation and onboarding packages from Microsoft Defender Security Center:</span></span>

1. <span data-ttu-id="264bf-155">En el Centro de seguridad de Microsoft Defender, vaya **a Configuración** Incorporación de  >  **administración de**  >  **dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="264bf-155">In Microsoft Defender Security Center, go to **Settings** > **Device Management** > **Onboarding**.</span></span>

2. <span data-ttu-id="264bf-156">Establezca el sistema operativo en **macOS** y el método de implementación en **Administración de dispositivos móviles / Microsoft Intune**.</span><span class="sxs-lookup"><span data-stu-id="264bf-156">Set the operating system to **macOS** and the deployment method to **Mobile Device Management / Microsoft Intune**.</span></span>

    ![Captura de pantalla de configuración de incorporación](images/atp-mac-install.png)

3. <span data-ttu-id="264bf-158">Seleccione **Descargar paquete de instalación**.</span><span class="sxs-lookup"><span data-stu-id="264bf-158">Select **Download installation package**.</span></span> <span data-ttu-id="264bf-159">Guárdelo _como wdav.pkg_ en un directorio local.</span><span class="sxs-lookup"><span data-stu-id="264bf-159">Save it as _wdav.pkg_ to a local directory.</span></span>

4. <span data-ttu-id="264bf-160">Seleccione **Descargar paquete de incorporación**.</span><span class="sxs-lookup"><span data-stu-id="264bf-160">Select **Download onboarding package**.</span></span> <span data-ttu-id="264bf-161">Guárdelo _WindowsDefenderATPOnboardingPackage.zip_ en el mismo directorio.</span><span class="sxs-lookup"><span data-stu-id="264bf-161">Save it as _WindowsDefenderATPOnboardingPackage.zip_ to the same directory.</span></span>

5. <span data-ttu-id="264bf-162">Descargue **IntuneAppUtil** desde [https://docs.microsoft.com/intune/lob-apps-macos](https://docs.microsoft.com/intune/lob-apps-macos) .</span><span class="sxs-lookup"><span data-stu-id="264bf-162">Download **IntuneAppUtil** from [https://docs.microsoft.com/intune/lob-apps-macos](https://docs.microsoft.com/intune/lob-apps-macos).</span></span>

6. <span data-ttu-id="264bf-163">Desde un símbolo del sistema, compruebe que tiene los tres archivos.</span><span class="sxs-lookup"><span data-stu-id="264bf-163">From a command prompt, verify that you have the three files.</span></span>
  

    ```bash
    ls -l
    ```

    ```Output
    total 721688
    -rw-r--r--  1 test  staff     269280 Mar 15 11:25 IntuneAppUtil
    -rw-r--r--  1 test  staff      11821 Mar 15 09:23 WindowsDefenderATPOnboardingPackage.zip
    -rw-r--r--  1 test  staff  354531845 Mar 13 08:57 wdav.pkg
    ```
7. <span data-ttu-id="264bf-164">Extraiga el contenido de los archivos .zip:</span><span class="sxs-lookup"><span data-stu-id="264bf-164">Extract the contents of the .zip files:</span></span>

    ```bash
    unzip WindowsDefenderATPOnboardingPackage.zip
    ```
    ```Output
    Archive:  WindowsDefenderATPOnboardingPackage.zip
    warning:  WindowsDefenderATPOnboardingPackage.zip appears to use backslashes as path separators
      inflating: intune/kext.xml
      inflating: intune/WindowsDefenderATPOnboarding.xml
      inflating: jamf/WindowsDefenderATPOnboarding.plist
    ```

8. <span data-ttu-id="264bf-165">Convertir IntuneAppUtil en ejecutable:</span><span class="sxs-lookup"><span data-stu-id="264bf-165">Make IntuneAppUtil an executable:</span></span>

    ```bash
    chmod +x IntuneAppUtil
    ```

9. <span data-ttu-id="264bf-166">Cree el paquete wdav.pkg.intunemac a partir de wdav.pkg:</span><span class="sxs-lookup"><span data-stu-id="264bf-166">Create the wdav.pkg.intunemac package from wdav.pkg:</span></span>

    ```bash
    ./IntuneAppUtil -c wdav.pkg -o . -i "com.microsoft.wdav" -n "1.0.0"
    ```
    ```Output
    Microsoft Intune Application Utility for Mac OS X
    Version: 1.0.0.0
    Copyright 2018 Microsoft Corporation

    Creating intunemac file for /Users/test/Downloads/wdav.pkg
    Composing the intunemac file output
    Output written to ./wdav.pkg.intunemac.

    IntuneAppUtil successfully processed "wdav.pkg",
    to deploy refer to the product documentation.
    ```

## <a name="client-device-setup"></a><span data-ttu-id="264bf-167">Configuración del dispositivo cliente</span><span class="sxs-lookup"><span data-stu-id="264bf-167">Client device setup</span></span>

<span data-ttu-id="264bf-168">No necesita ningún aprovisionamiento especial para un dispositivo Mac más allá de una instalación [estándar del Portal de empresa.](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-macos-cp)</span><span class="sxs-lookup"><span data-stu-id="264bf-168">You do not need any special provisioning for a Mac device beyond a standard [Company Portal installation](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-macos-cp).</span></span>

1. <span data-ttu-id="264bf-169">Confirme la administración de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="264bf-169">Confirm device management.</span></span>

    ![Confirmar captura de pantalla de administración de dispositivos](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-3-confirmdevicemgmt)

    <span data-ttu-id="264bf-171">Seleccione **Abrir preferencias del sistema,** busque **Perfil de administración** en la lista y seleccione **Aprobar...**. El perfil de administración se mostrará como **Verificado**:</span><span class="sxs-lookup"><span data-stu-id="264bf-171">Select **Open System Preferences**, locate **Management Profile** on the list, and select **Approve...**. Your Management Profile would be displayed as **Verified**:</span></span>

    ![Captura de pantalla del perfil de administración](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-4-managementprofile)

2. <span data-ttu-id="264bf-173">Seleccione **Continuar** y complete la inscripción.</span><span class="sxs-lookup"><span data-stu-id="264bf-173">Select **Continue** and complete the enrollment.</span></span>

   <span data-ttu-id="264bf-174">Ahora puede inscribir más dispositivos.</span><span class="sxs-lookup"><span data-stu-id="264bf-174">You may now enroll more devices.</span></span> <span data-ttu-id="264bf-175">También puede inscribirlos más adelante, una vez que haya terminado de aprovisionar paquetes de aplicación y configuración del sistema.</span><span class="sxs-lookup"><span data-stu-id="264bf-175">You can also enroll them later, after you have finished provisioning system configuration and application packages.</span></span>

3. <span data-ttu-id="264bf-176">En Intune, abra **Administrar**  >  **dispositivos**  >  **Todos los dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="264bf-176">In Intune, open **Manage** > **Devices** > **All devices**.</span></span> <span data-ttu-id="264bf-177">Aquí puedes ver el dispositivo entre los que aparecen en la lista:</span><span class="sxs-lookup"><span data-stu-id="264bf-177">Here you can see your device among those listed:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="264bf-178">![Captura de pantalla Agregar dispositivos](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-5-alldevices)</span><span class="sxs-lookup"><span data-stu-id="264bf-178">![Add Devices screenshot](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-5-alldevices)</span></span>

## <a name="approve-system-extensions"></a><span data-ttu-id="264bf-179">Aprobar extensiones del sistema</span><span class="sxs-lookup"><span data-stu-id="264bf-179">Approve System Extensions</span></span>

<span data-ttu-id="264bf-180">Para aprobar las extensiones del sistema:</span><span class="sxs-lookup"><span data-stu-id="264bf-180">To approve the system extensions:</span></span>

1. <span data-ttu-id="264bf-181">En Intune, abra **Administrar configuración**  >  **de dispositivo.**</span><span class="sxs-lookup"><span data-stu-id="264bf-181">In Intune, open **Manage** > **Device configuration**.</span></span> <span data-ttu-id="264bf-182">Seleccione **Administrar**  >  **perfiles Crear**  >  **perfil**.</span><span class="sxs-lookup"><span data-stu-id="264bf-182">Select **Manage** > **Profiles** > **Create Profile**.</span></span>

2. <span data-ttu-id="264bf-183">Elija un nombre para el perfil.</span><span class="sxs-lookup"><span data-stu-id="264bf-183">Choose a name for the profile.</span></span> <span data-ttu-id="264bf-184">Cambiar **Platform=macOS** a **Profile type=Extensions**.</span><span class="sxs-lookup"><span data-stu-id="264bf-184">Change **Platform=macOS** to **Profile type=Extensions**.</span></span> <span data-ttu-id="264bf-185">Seleccione **Crear**.</span><span class="sxs-lookup"><span data-stu-id="264bf-185">Select **Create**.</span></span>

3. <span data-ttu-id="264bf-186">En la `Basics` pestaña, asigne un nombre a este nuevo perfil.</span><span class="sxs-lookup"><span data-stu-id="264bf-186">In the `Basics` tab, give a name to this new profile.</span></span>

4. <span data-ttu-id="264bf-187">En la `Configuration settings` pestaña, agregue las siguientes entradas en la `Allowed system extensions` sección:</span><span class="sxs-lookup"><span data-stu-id="264bf-187">In the `Configuration settings` tab, add the following entries in the `Allowed system extensions` section:</span></span>

    <span data-ttu-id="264bf-188">Identificador de agrupación</span><span class="sxs-lookup"><span data-stu-id="264bf-188">Bundle identifier</span></span>         | <span data-ttu-id="264bf-189">Identificador de equipo</span><span class="sxs-lookup"><span data-stu-id="264bf-189">Team identifier</span></span>
    --------------------------|----------------
    <span data-ttu-id="264bf-190">com.microsoft.wdav.epsext</span><span class="sxs-lookup"><span data-stu-id="264bf-190">com.microsoft.wdav.epsext</span></span> | <span data-ttu-id="264bf-191">UBF8T346G9</span><span class="sxs-lookup"><span data-stu-id="264bf-191">UBF8T346G9</span></span>
    <span data-ttu-id="264bf-192">com.microsoft.wdav.netext</span><span class="sxs-lookup"><span data-stu-id="264bf-192">com.microsoft.wdav.netext</span></span> | <span data-ttu-id="264bf-193">UBF8T346G9</span><span class="sxs-lookup"><span data-stu-id="264bf-193">UBF8T346G9</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="264bf-194">![Captura de pantalla de la pestaña Configuración, incluida la sección Identificadores de equipo permitidos](images/mac-system-extension-intune2.png)</span><span class="sxs-lookup"><span data-stu-id="264bf-194">![Screenshot of the Configuration settings tab, including the Allowed team identifiers section](images/mac-system-extension-intune2.png)</span></span>

5. <span data-ttu-id="264bf-195">En la `Assignments` pestaña, asigne este perfil a **Todos los usuarios & Todos los dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="264bf-195">In the `Assignments` tab, assign this profile to **All Users & All devices**.</span></span>

6. <span data-ttu-id="264bf-196">Revise y cree este perfil de configuración.</span><span class="sxs-lookup"><span data-stu-id="264bf-196">Review and create this configuration profile.</span></span>

## <a name="create-system-configuration-profiles"></a><span data-ttu-id="264bf-197">Crear perfiles de configuración del sistema</span><span class="sxs-lookup"><span data-stu-id="264bf-197">Create System Configuration profiles</span></span>

1. <span data-ttu-id="264bf-198">En Intune, abra **Administrar configuración**  >  **de dispositivo.**</span><span class="sxs-lookup"><span data-stu-id="264bf-198">In Intune, open **Manage** > **Device configuration**.</span></span> <span data-ttu-id="264bf-199">Seleccione **Administrar**  >  **perfiles Crear**  >  **perfil**.</span><span class="sxs-lookup"><span data-stu-id="264bf-199">Select **Manage** > **Profiles** > **Create Profile**.</span></span>

2. <span data-ttu-id="264bf-200">Elija un nombre para el perfil.</span><span class="sxs-lookup"><span data-stu-id="264bf-200">Choose a name for the profile.</span></span> <span data-ttu-id="264bf-201">Cambiar **Platform=macOS** a **Profile type=Custom**.</span><span class="sxs-lookup"><span data-stu-id="264bf-201">Change **Platform=macOS** to **Profile type=Custom**.</span></span> <span data-ttu-id="264bf-202">Seleccione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="264bf-202">Select **Configure**.</span></span>

3. <span data-ttu-id="264bf-203">Abra el perfil de configuración y cargue intune/kext.xml.</span><span class="sxs-lookup"><span data-stu-id="264bf-203">Open the configuration profile and upload intune/kext.xml.</span></span> <span data-ttu-id="264bf-204">Este archivo se creó en una de las secciones anteriores.</span><span class="sxs-lookup"><span data-stu-id="264bf-204">This file was created in one of the preceding sections.</span></span>

4. <span data-ttu-id="264bf-205">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="264bf-205">Select **OK**.</span></span>

    ![Captura de pantalla de perfiles de configuración del sistema](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-6-systemconfigurationprofiles)

5. <span data-ttu-id="264bf-207">Seleccione **Administrar**  >  **asignaciones**.</span><span class="sxs-lookup"><span data-stu-id="264bf-207">Select **Manage** > **Assignments**.</span></span> <span data-ttu-id="264bf-208">En la **pestaña Incluir,** seleccione **Asignar a todos los usuarios & Todos los dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="264bf-208">In the **Include** tab, select **Assign to All Users & All devices**.</span></span>

6. <span data-ttu-id="264bf-209">Repita los pasos del 1 al 5 para obtener más perfiles.</span><span class="sxs-lookup"><span data-stu-id="264bf-209">Repeat steps 1 through 5 for more profiles.</span></span>

7. <span data-ttu-id="264bf-210">Cree otro perfil, así como un nombre y cargue el archivo intune/WindowsDefenderATPOnboarding.xml.</span><span class="sxs-lookup"><span data-stu-id="264bf-210">Create another profile, give it a name, and upload the intune/WindowsDefenderATPOnboarding.xml file.</span></span>

8. <span data-ttu-id="264bf-211">Descargue `fulldisk.mobileconfig` desde nuestro repositorio de [GitHub](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/fulldisk.mobileconfig) y guárdelo como `tcc.xml` .</span><span class="sxs-lookup"><span data-stu-id="264bf-211">Download `fulldisk.mobileconfig` from [our GitHub repository](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/fulldisk.mobileconfig) and save it as `tcc.xml`.</span></span> <span data-ttu-id="264bf-212">Crear otro perfil, darle cualquier nombre y cargar este archivo en él.<a name="create-system-configuration-profiles-step-8" id = "create-system-configuration-profiles-step-8"></a></span><span class="sxs-lookup"><span data-stu-id="264bf-212">Create another profile, give it any name and upload this file to it.<a name="create-system-configuration-profiles-step-8" id = "create-system-configuration-profiles-step-8"></a></span></span>

   > [!CAUTION]
   > <span data-ttu-id="264bf-213">macOS 10.15 (Catalina) contiene nuevas mejoras de seguridad y privacidad.</span><span class="sxs-lookup"><span data-stu-id="264bf-213">macOS 10.15 (Catalina) contains new security and privacy enhancements.</span></span> <span data-ttu-id="264bf-214">A partir de esta versión, de forma predeterminada, las aplicaciones no pueden acceder a determinadas ubicaciones del disco (como Documentos, Descargas, Escritorio, etc.) sin consentimiento explícito.</span><span class="sxs-lookup"><span data-stu-id="264bf-214">Beginning with this version, by default, applications are not able to access certain locations on disk (such as Documents, Downloads, Desktop, etc.) without explicit consent.</span></span> <span data-ttu-id="264bf-215">En ausencia de este consentimiento, Microsoft Defender para Endpoint no puede proteger completamente el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="264bf-215">In the absence of this consent, Microsoft Defender for Endpoint is not able to fully protect your device.</span></span>
   >
   > <span data-ttu-id="264bf-216">Este perfil de configuración concede acceso en disco completo a Microsoft Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="264bf-216">This configuration profile grants Full Disk Access to Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="264bf-217">Si configuró anteriormente Microsoft Defender para Endpoint a través de Intune, se recomienda actualizar la implementación con este perfil de configuración.</span><span class="sxs-lookup"><span data-stu-id="264bf-217">If you previously configured Microsoft Defender for Endpoint through Intune, we recommend you update the deployment with this configuration profile.</span></span>

9. <span data-ttu-id="264bf-218">Como parte de las capacidades de detección y respuesta de puntos de conexión, Microsoft Defender para Endpoint para Mac inspecciona el tráfico de sockets e informa de esta información al portal del Centro de seguridad de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="264bf-218">As part of the Endpoint Detection and Response capabilities, Microsoft Defender for Endpoint for Mac inspects socket traffic and reports this information to the Microsoft Defender Security Center portal.</span></span> <span data-ttu-id="264bf-219">La siguiente directiva permite que la extensión de red realice esta funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="264bf-219">The following policy allows the network extension to perform this functionality.</span></span> <span data-ttu-id="264bf-220">Descargue `netfilter.mobileconfig` desde nuestro repositorio de [GitHub,](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/netfilter.mobileconfig)guárdelo como netext.xml e impleméntelo con los mismos pasos que en las secciones anteriores.</span><span class="sxs-lookup"><span data-stu-id="264bf-220">Download `netfilter.mobileconfig` from [our GitHub repository](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/netfilter.mobileconfig), save it as netext.xml and deploy it using the same steps as in the previous sections.</span></span> <a name = "create-system-configuration-profiles-step-9" id = "create-system-configuration-profiles-step-9"></a>

10. <span data-ttu-id="264bf-221">Para permitir que Microsoft Defender para Endpoint para Mac y Microsoft Auto Update muestren notificaciones en la interfaz de usuario en macOS 10.15 (Catalina), descargue desde nuestro repositorio `notif.mobileconfig` [de GitHub](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/notif.mobileconfig) e impórtelo como una carga personalizada.</span><span class="sxs-lookup"><span data-stu-id="264bf-221">To allow Microsoft Defender for Endpoint for Mac and Microsoft Auto Update to display notifications in UI on macOS 10.15 (Catalina), download `notif.mobileconfig` from [our GitHub repository](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/notif.mobileconfig) and import it as a custom payload.</span></span> <a name = "create-system-configuration-profiles-step-10" id = "create-system-configuration-profiles-step-10"></a>

11. <span data-ttu-id="264bf-222">Seleccione **Administrar > asignaciones**.</span><span class="sxs-lookup"><span data-stu-id="264bf-222">Select **Manage > Assignments**.</span></span>  <span data-ttu-id="264bf-223">En la **pestaña Incluir,** seleccione **Asignar a todos los usuarios & Todos los dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="264bf-223">In the **Include** tab, select **Assign to All Users & All devices**.</span></span>

<span data-ttu-id="264bf-224">Una vez que los cambios de Intune se propaguen a los dispositivos inscritos, puede verlos en **Estado**  >  **del dispositivo de supervisión:**</span><span class="sxs-lookup"><span data-stu-id="264bf-224">Once the Intune changes are propagated to the enrolled devices, you can see them listed under **Monitor** > **Device status**:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="264bf-225">![Captura de pantalla de kext: estado del dispositivo](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-7-devicestatusblade)</span><span class="sxs-lookup"><span data-stu-id="264bf-225">![Screenshot of kext - Device status](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-7-devicestatusblade)</span></span>

## <a name="publish-application"></a><span data-ttu-id="264bf-226">Publicar aplicación</span><span class="sxs-lookup"><span data-stu-id="264bf-226">Publish application</span></span>

1. <span data-ttu-id="264bf-227">En Intune, abra la hoja **Administrar > aplicaciones cliente.**</span><span class="sxs-lookup"><span data-stu-id="264bf-227">In Intune, open the **Manage > Client apps** blade.</span></span> <span data-ttu-id="264bf-228">Seleccione **Aplicaciones > Agregar**.</span><span class="sxs-lookup"><span data-stu-id="264bf-228">Select **Apps > Add**.</span></span>

2. <span data-ttu-id="264bf-229">Selecciona **Tipo de aplicación=Otra/Aplicación de línea de negocio.**</span><span class="sxs-lookup"><span data-stu-id="264bf-229">Select **App type=Other/Line-of-business app**.</span></span>

3. <span data-ttu-id="264bf-230">Seleccione **file=wdav.pkg.intunemac**.</span><span class="sxs-lookup"><span data-stu-id="264bf-230">Select **file=wdav.pkg.intunemac**.</span></span> <span data-ttu-id="264bf-231">Seleccione **Aceptar** para cargar.</span><span class="sxs-lookup"><span data-stu-id="264bf-231">Select **OK** to upload.</span></span>

4. <span data-ttu-id="264bf-232">Seleccione **Configurar** y agregue la información necesaria.</span><span class="sxs-lookup"><span data-stu-id="264bf-232">Select **Configure** and add the required information.</span></span>

5. <span data-ttu-id="264bf-233">Use **macOS High Sierra 10.13** como sistema operativo mínimo.</span><span class="sxs-lookup"><span data-stu-id="264bf-233">Use **macOS High Sierra 10.13** as the minimum OS.</span></span>

6. <span data-ttu-id="264bf-234">Establece *Omitir versión de la aplicación* en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="264bf-234">Set *Ignore app version* to **Yes**.</span></span> <span data-ttu-id="264bf-235">Otras opciones de configuración pueden ser cualquier valor arbitrario.</span><span class="sxs-lookup"><span data-stu-id="264bf-235">Other settings can be any arbitrary value.</span></span>

    > [!CAUTION]
    > <span data-ttu-id="264bf-236">Establecer *Omitir versión de la aplicación* en **No** afecta a la capacidad de la aplicación para recibir actualizaciones a través de Microsoft AutoUpdate.</span><span class="sxs-lookup"><span data-stu-id="264bf-236">Setting *Ignore app version* to **No** impacts the ability of the application to receive updates through Microsoft AutoUpdate.</span></span> <span data-ttu-id="264bf-237">Consulta [Implementar actualizaciones para Microsoft Defender para Endpoint para Mac](mac-updates.md) para obtener información adicional sobre cómo se actualiza el producto.</span><span class="sxs-lookup"><span data-stu-id="264bf-237">See [Deploy updates for Microsoft Defender for Endpoint for Mac](mac-updates.md) for additional information about how the product is updated.</span></span>
    >
    > <span data-ttu-id="264bf-238">Si la versión cargada por Intune es inferior a la versión del dispositivo, se instalará la versión inferior, lo que degradará eficazmente Microsoft Defender para Endpoint.</span><span class="sxs-lookup"><span data-stu-id="264bf-238">If the version uploaded by Intune is lower than the version on the device, then the lower version will be installed, effectively downgrading Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="264bf-239">Esto podría dar como resultado una aplicación que no funciona.</span><span class="sxs-lookup"><span data-stu-id="264bf-239">This could result in a non-functioning application.</span></span> <span data-ttu-id="264bf-240">Consulta [Implementar actualizaciones para Microsoft Defender para Endpoint para Mac](mac-updates.md) para obtener información adicional sobre cómo se actualiza el producto.</span><span class="sxs-lookup"><span data-stu-id="264bf-240">See [Deploy updates for Microsoft Defender for Endpoint for Mac](mac-updates.md) for additional information about how the product is updated.</span></span> <span data-ttu-id="264bf-241">Si implementaste Microsoft Defender para endpoint con *ignorar la* versión de la aplicación establecida en **No,** cámbiese a **Sí**.</span><span class="sxs-lookup"><span data-stu-id="264bf-241">If you deployed Microsoft Defender for Endpoint with *Ignore app version* set to **No**, please change it to **Yes**.</span></span> <span data-ttu-id="264bf-242">Si Microsoft Defender para endpoint aún no se puede instalar en un dispositivo cliente, desinstala Microsoft Defender para Endpoint e inserta la directiva actualizada.</span><span class="sxs-lookup"><span data-stu-id="264bf-242">If Microsoft Defender for Endpoint still cannot be installed on a client device, then uninstall Microsoft Defender for Endpoint and push the updated policy.</span></span>
     
    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="264bf-243">![Captura de pantalla de la opción Configurar información de la aplicación en el cuadro de diálogo Agregar aplicación](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-8-intuneappinfo)</span><span class="sxs-lookup"><span data-stu-id="264bf-243">![Screenshot of the Configure App information option in the Add app dialog box](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-8-intuneappinfo)</span></span>

7. <span data-ttu-id="264bf-244">Seleccione **Aceptar** y **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="264bf-244">Select **OK** and **Add**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="264bf-245">![Captura de pantalla de una introducción de ejemplo](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-9-intunepkginfo)</span><span class="sxs-lookup"><span data-stu-id="264bf-245">![Screenshot of a sample overview](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-9-intunepkginfo)</span></span>

8. <span data-ttu-id="264bf-246">Puede tardar unos minutos en cargar el paquete.</span><span class="sxs-lookup"><span data-stu-id="264bf-246">It may take a few moments to upload the package.</span></span> <span data-ttu-id="264bf-247">Una vez terminado, seleccione el paquete de la lista y vaya a **Asignaciones** y **Agregar grupo**.</span><span class="sxs-lookup"><span data-stu-id="264bf-247">After it's done, select the package from the list and go to **Assignments** and **Add group**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="264bf-248">![Captura de pantalla de aplicaciones cliente](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-10-clientapps)</span><span class="sxs-lookup"><span data-stu-id="264bf-248">![Client apps screenshot](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-10-clientapps)</span></span>

9. <span data-ttu-id="264bf-249">Cambie **el tipo de asignación** a **Obligatorio**.</span><span class="sxs-lookup"><span data-stu-id="264bf-249">Change **Assignment type** to **Required**.</span></span>

10. <span data-ttu-id="264bf-250">Seleccione **Grupos incluidos**.</span><span class="sxs-lookup"><span data-stu-id="264bf-250">Select **Included Groups**.</span></span> <span data-ttu-id="264bf-251">Selecciona **Hacer que esta aplicación sea necesaria para todos los dispositivos=Sí**.</span><span class="sxs-lookup"><span data-stu-id="264bf-251">Select **Make this app required for all devices=Yes**.</span></span> <span data-ttu-id="264bf-252">Seleccione **Seleccionar grupo para incluir y** agregar un grupo que contenga los usuarios a los que desea dirigirse.</span><span class="sxs-lookup"><span data-stu-id="264bf-252">Select **Select group to include** and add a group that contains the users you want to target.</span></span> <span data-ttu-id="264bf-253">Seleccione **Aceptar** y **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="264bf-253">Select **OK** and **Save**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="264bf-254">![Captura de pantalla de información de asignaciones de Intune](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-11-assignments)</span><span class="sxs-lookup"><span data-stu-id="264bf-254">![Intune assignments info screenshot](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-11-assignments)</span></span>

11. <span data-ttu-id="264bf-255">Después de algún tiempo, la aplicación se publicará en todos los dispositivos inscritos.</span><span class="sxs-lookup"><span data-stu-id="264bf-255">After some time the application will be published to all enrolled devices.</span></span> <span data-ttu-id="264bf-256">Puedes verlo en Monitor  >  **Device**, en **Estado de instalación del dispositivo:**</span><span class="sxs-lookup"><span data-stu-id="264bf-256">You can see it listed in **Monitor** > **Device**, under **Device install status**:</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="264bf-257">![Captura de pantalla de estado del dispositivo intune](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-12-deviceinstall)</span><span class="sxs-lookup"><span data-stu-id="264bf-257">![Intune device status screenshot](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-12-deviceinstall)</span></span>

## <a name="verify-client-device-state"></a><span data-ttu-id="264bf-258">Comprobar el estado del dispositivo cliente</span><span class="sxs-lookup"><span data-stu-id="264bf-258">Verify client device state</span></span>

1. <span data-ttu-id="264bf-259">Después de implementar los perfiles de configuración en los dispositivos, abre **Perfiles** de  >  **preferencias del sistema** en tu dispositivo Mac.</span><span class="sxs-lookup"><span data-stu-id="264bf-259">After the configuration profiles are deployed to your devices, open **System Preferences** > **Profiles** on your Mac device.</span></span>

    <span data-ttu-id="264bf-260">![Captura de pantalla Preferencias del sistema](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-13-systempreferences)</span><span class="sxs-lookup"><span data-stu-id="264bf-260">![System Preferences screenshot](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-13-systempreferences)</span></span><br/>
    <span data-ttu-id="264bf-261">![Captura de pantalla Perfiles de preferencias del sistema](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-14-systempreferencesprofiles)</span><span class="sxs-lookup"><span data-stu-id="264bf-261">![System Preferences Profiles screenshot](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-14-systempreferencesprofiles)</span></span>

2. <span data-ttu-id="264bf-262">Compruebe que los siguientes perfiles de configuración están presentes e instalados.</span><span class="sxs-lookup"><span data-stu-id="264bf-262">Verify that the following configuration profiles are present and installed.</span></span> <span data-ttu-id="264bf-263">El **perfil de administración** debe ser el perfil del sistema de Intune.</span><span class="sxs-lookup"><span data-stu-id="264bf-263">The **Management Profile** should be the Intune system profile.</span></span> <span data-ttu-id="264bf-264">_Wdav-config y_ _wdav-kext_ son perfiles de configuración del sistema que se agregaron en Intune: Captura de pantalla ![ De perfiles](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-15-managementprofileconfig)</span><span class="sxs-lookup"><span data-stu-id="264bf-264">_Wdav-config_ and _wdav-kext_ are system configuration profiles that were added in Intune: ![Profiles screenshot](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-15-managementprofileconfig)</span></span>

3. <span data-ttu-id="264bf-265">También debería ver el icono de Microsoft Defender en la esquina superior derecha:</span><span class="sxs-lookup"><span data-stu-id="264bf-265">You should also see the Microsoft Defender icon in the top-right corner:</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="264bf-266">![Icono de Microsoft Defender en la captura de pantalla de la barra de estado](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-icon-bar)</span><span class="sxs-lookup"><span data-stu-id="264bf-266">![Microsoft Defender icon in status bar screenshot](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-icon-bar)</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="264bf-267">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="264bf-267">Troubleshooting</span></span>

<span data-ttu-id="264bf-268">Problema: no se encontró ninguna licencia</span><span class="sxs-lookup"><span data-stu-id="264bf-268">Issue: No license found</span></span>

<span data-ttu-id="264bf-269">Solución: siga los pasos anteriores para crear un perfil de dispositivo con WindowsDefenderATPOnboarding.xml</span><span class="sxs-lookup"><span data-stu-id="264bf-269">Solution: Follow the steps above to create a device profile using WindowsDefenderATPOnboarding.xml</span></span>

## <a name="logging-installation-issues"></a><span data-ttu-id="264bf-270">Problemas de instalación de registro</span><span class="sxs-lookup"><span data-stu-id="264bf-270">Logging installation issues</span></span>

<span data-ttu-id="264bf-271">Para obtener más información sobre cómo encontrar el registro generado automáticamente que crea el instalador cuando se produce un error, vea [Logging installation issues](mac-resources.md#logging-installation-issues).</span><span class="sxs-lookup"><span data-stu-id="264bf-271">For more information on how to find the automatically generated log that is created by the installer when an error occurs, see [Logging installation issues](mac-resources.md#logging-installation-issues).</span></span>

## <a name="uninstallation"></a><span data-ttu-id="264bf-272">Desinstalación</span><span class="sxs-lookup"><span data-stu-id="264bf-272">Uninstallation</span></span>

<span data-ttu-id="264bf-273">Consulta [Desinstalar para obtener](mac-resources.md#uninstalling) más información sobre cómo quitar Microsoft Defender para Endpoint para Mac de los dispositivos cliente.</span><span class="sxs-lookup"><span data-stu-id="264bf-273">See [Uninstalling](mac-resources.md#uninstalling) for details on how to remove Microsoft Defender for Endpoint for Mac from client devices.</span></span>
