---
title: Implementación basada en Intune para Microsoft Defender para Endpoint en Mac
description: Instale Microsoft Defender para Endpoint en Mac mediante Microsoft Intune.
keywords: microsoft, defender, Microsoft Defender para Endpoint, mac, instalación, implementación, desinstalación, intune, jamf, macos, catalina, mojave, high sierra
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
ms.openlocfilehash: 5aeffdaff39c2f10dfa5164764bff38e99c00010
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2021
ms.locfileid: "52684224"
---
# <a name="intune-based-deployment-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="1cb7b-104">Implementación basada en Intune para Microsoft Defender para endpoint en macOS</span><span class="sxs-lookup"><span data-stu-id="1cb7b-104">Intune-based deployment for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1cb7b-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="1cb7b-105">**Applies to:**</span></span>

- [<span data-ttu-id="1cb7b-106">Microsoft Defender para punto de conexión en macOS</span><span class="sxs-lookup"><span data-stu-id="1cb7b-106">Microsoft Defender for Endpoint on macOS</span></span>](microsoft-defender-endpoint-mac.md)

<span data-ttu-id="1cb7b-107">En este tema se describe cómo implementar Microsoft Defender para Endpoint en macOS a través de Intune.</span><span class="sxs-lookup"><span data-stu-id="1cb7b-107">This topic describes how to deploy Microsoft Defender for Endpoint on macOS through Intune.</span></span> <span data-ttu-id="1cb7b-108">Una implementación correcta requiere la finalización de todos los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="1cb7b-108">A successful deployment requires the completion of all of the following steps:</span></span>

1. [<span data-ttu-id="1cb7b-109">Descargar el paquete de incorporación</span><span class="sxs-lookup"><span data-stu-id="1cb7b-109">Download the onboarding package</span></span>](#download-the-onboarding-package)
1. [<span data-ttu-id="1cb7b-110">Configuración del dispositivo cliente</span><span class="sxs-lookup"><span data-stu-id="1cb7b-110">Client device setup</span></span>](#client-device-setup)
1. [<span data-ttu-id="1cb7b-111">Aprobar extensiones del sistema</span><span class="sxs-lookup"><span data-stu-id="1cb7b-111">Approve system extensions</span></span>](#approve-system-extensions)
1. [<span data-ttu-id="1cb7b-112">Crear perfiles de configuración del sistema</span><span class="sxs-lookup"><span data-stu-id="1cb7b-112">Create System Configuration profiles</span></span>](#create-system-configuration-profiles)
1. [<span data-ttu-id="1cb7b-113">Publicar aplicación</span><span class="sxs-lookup"><span data-stu-id="1cb7b-113">Publish application</span></span>](#publish-application)

## <a name="prerequisites-and-system-requirements"></a><span data-ttu-id="1cb7b-114">Requisitos previos y requisitos del sistema</span><span class="sxs-lookup"><span data-stu-id="1cb7b-114">Prerequisites and system requirements</span></span>

<span data-ttu-id="1cb7b-115">Antes de empezar, consulta la página principal de Microsoft Defender para Endpoint [en macOS](microsoft-defender-endpoint-mac.md) para obtener una descripción de los requisitos previos y los requisitos del sistema para la versión de software actual.</span><span class="sxs-lookup"><span data-stu-id="1cb7b-115">Before you get started, see [the main Microsoft Defender for Endpoint on macOS page](microsoft-defender-endpoint-mac.md) for a description of prerequisites and system requirements for the current software version.</span></span>

## <a name="overview"></a><span data-ttu-id="1cb7b-116">Información general</span><span class="sxs-lookup"><span data-stu-id="1cb7b-116">Overview</span></span>

<span data-ttu-id="1cb7b-117">En la tabla siguiente se resumen los pasos que debe seguir para implementar y administrar Microsoft Defender para Endpoint en Macs, a través de Intune.</span><span class="sxs-lookup"><span data-stu-id="1cb7b-117">The following table summarizes the steps you would need to take to deploy and manage Microsoft Defender for Endpoint on Macs, via Intune.</span></span> <span data-ttu-id="1cb7b-118">Los pasos más detallados están disponibles a continuación.</span><span class="sxs-lookup"><span data-stu-id="1cb7b-118">More detailed steps are available below.</span></span>

| <span data-ttu-id="1cb7b-119">Paso</span><span class="sxs-lookup"><span data-stu-id="1cb7b-119">Step</span></span> | <span data-ttu-id="1cb7b-120">Nombres de archivo de ejemplo</span><span class="sxs-lookup"><span data-stu-id="1cb7b-120">Sample file names</span></span> | <span data-ttu-id="1cb7b-121">BundleIdentifier</span><span class="sxs-lookup"><span data-stu-id="1cb7b-121">BundleIdentifier</span></span> |
|-|-|-|
| [<span data-ttu-id="1cb7b-122">Descargar el paquete de incorporación</span><span class="sxs-lookup"><span data-stu-id="1cb7b-122">Download the onboarding package</span></span>](#download-the-onboarding-package) | <span data-ttu-id="1cb7b-123">WindowsDefenderATPOnboarding__MDATP_wdav.atp.xml</span><span class="sxs-lookup"><span data-stu-id="1cb7b-123">WindowsDefenderATPOnboarding__MDATP_wdav.atp.xml</span></span> | <span data-ttu-id="1cb7b-124">com.microsoft.wdav.atp</span><span class="sxs-lookup"><span data-stu-id="1cb7b-124">com.microsoft.wdav.atp</span></span> |
| [<span data-ttu-id="1cb7b-125">Aprobar extensión del sistema para Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="1cb7b-125">Approve System Extension for Microsoft Defender for Endpoint</span></span>](#approve-system-extensions) | <span data-ttu-id="1cb7b-126">MDATP_SysExt.xml</span><span class="sxs-lookup"><span data-stu-id="1cb7b-126">MDATP_SysExt.xml</span></span> | <span data-ttu-id="1cb7b-127">N/D</span><span class="sxs-lookup"><span data-stu-id="1cb7b-127">N/A</span></span> |
| [<span data-ttu-id="1cb7b-128">Aprobar extensión de kernel para Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="1cb7b-128">Approve Kernel Extension for Microsoft Defender for Endpoint</span></span>](#download-the-onboarding-package) | <span data-ttu-id="1cb7b-129">MDATP_KExt.xml</span><span class="sxs-lookup"><span data-stu-id="1cb7b-129">MDATP_KExt.xml</span></span> | <span data-ttu-id="1cb7b-130">N/D</span><span class="sxs-lookup"><span data-stu-id="1cb7b-130">N/A</span></span> |
| [<span data-ttu-id="1cb7b-131">Conceder acceso en disco completo a Microsoft Defender para endpoint</span><span class="sxs-lookup"><span data-stu-id="1cb7b-131">Grant full disk access to Microsoft Defender for Endpoint</span></span>](#full-disk-access) | <span data-ttu-id="1cb7b-132">MDATP_tcc_Catalina_or_newer.xml</span><span class="sxs-lookup"><span data-stu-id="1cb7b-132">MDATP_tcc_Catalina_or_newer.xml</span></span> | <span data-ttu-id="1cb7b-133">com.microsoft.wdav.tcc</span><span class="sxs-lookup"><span data-stu-id="1cb7b-133">com.microsoft.wdav.tcc</span></span> |
| [<span data-ttu-id="1cb7b-134">Directiva de extensión de red</span><span class="sxs-lookup"><span data-stu-id="1cb7b-134">Network Extension policy</span></span>](#network-filter) | <span data-ttu-id="1cb7b-135">MDATP_NetExt.xml</span><span class="sxs-lookup"><span data-stu-id="1cb7b-135">MDATP_NetExt.xml</span></span> | <span data-ttu-id="1cb7b-136">N/D</span><span class="sxs-lookup"><span data-stu-id="1cb7b-136">N/A</span></span> |
| [<span data-ttu-id="1cb7b-137">Configurar Microsoft AutoUpdate (MAU)</span><span class="sxs-lookup"><span data-stu-id="1cb7b-137">Configure Microsoft AutoUpdate (MAU)</span></span>](mac-updates.md#intune) | <span data-ttu-id="1cb7b-138">MDATP_Microsoft_AutoUpdate.xml</span><span class="sxs-lookup"><span data-stu-id="1cb7b-138">MDATP_Microsoft_AutoUpdate.xml</span></span> | <span data-ttu-id="1cb7b-139">com.microsoft.autoupdate2</span><span class="sxs-lookup"><span data-stu-id="1cb7b-139">com.microsoft.autoupdate2</span></span> |
| [<span data-ttu-id="1cb7b-140">Configuración de Microsoft Defender para puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="1cb7b-140">Microsoft Defender for Endpoint configuration settings</span></span>](mac-preferences.md#intune-profile-1)<br/><br/> <span data-ttu-id="1cb7b-141">**Nota:** Si está planeando ejecutar un ANTIVIRUS de terceros para macOS, establezca `passiveMode` en `true` .</span><span class="sxs-lookup"><span data-stu-id="1cb7b-141">**Note:** If you're planning to run a third-party AV for macOS, set `passiveMode` to `true`.</span></span> | <span data-ttu-id="1cb7b-142">MDATP_WDAV_and_exclusion_settings_Preferences.xml</span><span class="sxs-lookup"><span data-stu-id="1cb7b-142">MDATP_WDAV_and_exclusion_settings_Preferences.xml</span></span> | <span data-ttu-id="1cb7b-143">com.microsoft.wdav</span><span class="sxs-lookup"><span data-stu-id="1cb7b-143">com.microsoft.wdav</span></span> |
| [<span data-ttu-id="1cb7b-144">Configurar Microsoft Defender para notificaciones de punto de conexión y MS AutoUpdate (MAU)</span><span class="sxs-lookup"><span data-stu-id="1cb7b-144">Configure Microsoft Defender for Endpoint and MS AutoUpdate (MAU) notifications</span></span>](mac-updates.md) | <span data-ttu-id="1cb7b-145">MDATP_MDAV_Tray_and_AutoUpdate2.mobileconfig</span><span class="sxs-lookup"><span data-stu-id="1cb7b-145">MDATP_MDAV_Tray_and_AutoUpdate2.mobileconfig</span></span> | <span data-ttu-id="1cb7b-146">com.microsoft.autoupdate2 o com.microsoft.wdav.tray</span><span class="sxs-lookup"><span data-stu-id="1cb7b-146">com.microsoft.autoupdate2 or com.microsoft.wdav.tray</span></span> |


## <a name="download-the-onboarding-package"></a><span data-ttu-id="1cb7b-147">Descargar el paquete de incorporación</span><span class="sxs-lookup"><span data-stu-id="1cb7b-147">Download the onboarding package</span></span>

<span data-ttu-id="1cb7b-148">Descargue los paquetes de incorporación desde Centro de seguridad de Microsoft Defender:</span><span class="sxs-lookup"><span data-stu-id="1cb7b-148">Download the onboarding packages from Microsoft Defender Security Center:</span></span>

1. <span data-ttu-id="1cb7b-149">En Centro de seguridad de Microsoft Defender, vaya **a Configuración** Incorporación de  >  **administración de**  >  **dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="1cb7b-149">In Microsoft Defender Security Center, go to **Settings** > **Device Management** > **Onboarding**.</span></span>

2. <span data-ttu-id="1cb7b-150">Establezca el sistema operativo en **macOS** y el método de implementación en Administración de dispositivos móviles **/ Microsoft Intune**.</span><span class="sxs-lookup"><span data-stu-id="1cb7b-150">Set the operating system to **macOS** and the deployment method to **Mobile Device Management / Microsoft Intune**.</span></span>

    ![Captura de pantalla de configuración de incorporación](images/atp-mac-install.png)

3. <span data-ttu-id="1cb7b-152">Seleccione **Descargar paquete de incorporación**.</span><span class="sxs-lookup"><span data-stu-id="1cb7b-152">Select **Download onboarding package**.</span></span> <span data-ttu-id="1cb7b-153">Guárdelo _WindowsDefenderATPOnboardingPackage.zip_ en el mismo directorio.</span><span class="sxs-lookup"><span data-stu-id="1cb7b-153">Save it as _WindowsDefenderATPOnboardingPackage.zip_ to the same directory.</span></span>

4. <span data-ttu-id="1cb7b-154">Extraiga el contenido del .zip archivo:</span><span class="sxs-lookup"><span data-stu-id="1cb7b-154">Extract the contents of the .zip file:</span></span>

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

## <a name="create-system-configuration-profiles"></a><span data-ttu-id="1cb7b-155">Crear perfiles de configuración del sistema</span><span class="sxs-lookup"><span data-stu-id="1cb7b-155">Create System Configuration profiles</span></span>

<span data-ttu-id="1cb7b-156">El siguiente paso es crear perfiles de configuración del sistema que Necesita Microsoft Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="1cb7b-156">The next step is to create system configuration profiles that Microsoft Defender for Endpoint needs.</span></span>
<span data-ttu-id="1cb7b-157">En el [Centro Microsoft Endpoint Manager administración,](https://endpoint.microsoft.com/)abra **Perfiles de** configuración de  >  **dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="1cb7b-157">In the [Microsoft Endpoint Manager admin center](https://endpoint.microsoft.com/), open **Devices** > **Configuration profiles**.</span></span>

### <a name="onboarding-blob"></a><span data-ttu-id="1cb7b-158">Blob de incorporación</span><span class="sxs-lookup"><span data-stu-id="1cb7b-158">Onboarding blob</span></span>

<span data-ttu-id="1cb7b-159">Este perfil contiene una información de licencia para Microsoft Defender para Endpoint, sin que informe de que no tiene licencia.</span><span class="sxs-lookup"><span data-stu-id="1cb7b-159">This profile contains a license information for Microsoft Defender for Endpoint, without it it will report that it is not licensed.</span></span>

1. <span data-ttu-id="1cb7b-160">Seleccione **Crear perfil en** **Perfiles de configuración**.</span><span class="sxs-lookup"><span data-stu-id="1cb7b-160">Select **Create Profile** under **Configuration Profiles**.</span></span>
1. <span data-ttu-id="1cb7b-161">Seleccione **Plataforma** = **macOS**, Tipo de perfil  = **Plantillas**.</span><span class="sxs-lookup"><span data-stu-id="1cb7b-161">Select **Platform**=**macOS**, **Profile type**=**Templates**.</span></span> <span data-ttu-id="1cb7b-162">**Nombre de plantilla** = **Personalizado**.</span><span class="sxs-lookup"><span data-stu-id="1cb7b-162">**Template name**=**Custom**.</span></span> <span data-ttu-id="1cb7b-163">Haga clic en **Crear**.</span><span class="sxs-lookup"><span data-stu-id="1cb7b-163">Click **Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="1cb7b-164">![Creación de perfiles de configuración personalizados](images/mdatp-6-systemconfigurationprofiles-1.png)</span><span class="sxs-lookup"><span data-stu-id="1cb7b-164">![Custom Configuration Profile creation](images/mdatp-6-systemconfigurationprofiles-1.png)</span></span>

1. <span data-ttu-id="1cb7b-165">Elija un nombre para el perfil, por ejemplo, "MDATP incorporación para macOS".</span><span class="sxs-lookup"><span data-stu-id="1cb7b-165">Choose a name for the profile, e.g., "MDATP onboarding for macOS".</span></span> <span data-ttu-id="1cb7b-166">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="1cb7b-166">Click **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="1cb7b-167">![Perfil de configuración personalizado: nombre](images/mdatp-6-systemconfigurationprofiles-2.png)</span><span class="sxs-lookup"><span data-stu-id="1cb7b-167">![Custom Configuration Profile - name](images/mdatp-6-systemconfigurationprofiles-2.png)</span></span>

1. <span data-ttu-id="1cb7b-168">Elija un nombre para el nombre del perfil de configuración, por ejemplo, "MDATP incorporación para macOS".</span><span class="sxs-lookup"><span data-stu-id="1cb7b-168">Choose a name for the configuration profile name, e.g., "MDATP onboarding for macOS".</span></span>
1. <span data-ttu-id="1cb7b-169">Seleccione intune/WindowsDefenderATPOnboarding.xml que extrajo del paquete de incorporación anterior como archivo de perfil de configuración.</span><span class="sxs-lookup"><span data-stu-id="1cb7b-169">Select intune/WindowsDefenderATPOnboarding.xml that you extracted from the onboarding package above as configuration profile file.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="1cb7b-170">![Importar una configuración desde un archivo para perfil de configuración personalizado](images/mdatp-6-systemconfigurationprofiles.png)</span><span class="sxs-lookup"><span data-stu-id="1cb7b-170">![Import a configuration from a file for Custom Configuration Profile](images/mdatp-6-systemconfigurationprofiles.png)</span></span>

1. <span data-ttu-id="1cb7b-171">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="1cb7b-171">Click **Next**.</span></span>
1. <span data-ttu-id="1cb7b-172">Asignar dispositivos en la **pestaña** Asignación. Haga clic **en Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="1cb7b-172">Assign devices on the **Assignment** tab. Click **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="1cb7b-173">![Perfil de configuración personalizado: asignación](images/mdatp-6-systemconfigurationprofiles-2.png)</span><span class="sxs-lookup"><span data-stu-id="1cb7b-173">![Custom Configuration Profile - assignment](images/mdatp-6-systemconfigurationprofiles-2.png)</span></span>

1. <span data-ttu-id="1cb7b-174">Revisar y **crear**.</span><span class="sxs-lookup"><span data-stu-id="1cb7b-174">Review and **Create**.</span></span>
1. <span data-ttu-id="1cb7b-175">Abra   >  **perfiles de configuración de dispositivos,** puede ver el perfil creado allí.</span><span class="sxs-lookup"><span data-stu-id="1cb7b-175">Open **Devices** > **Configuration profiles**, you can see your created profile there.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="1cb7b-176">![Perfil de configuración personalizado: listo](images/mdatp-6-systemconfigurationprofiles-3.png)</span><span class="sxs-lookup"><span data-stu-id="1cb7b-176">![Custom Configuration Profile - done](images/mdatp-6-systemconfigurationprofiles-3.png)</span></span>

### <a name="approve-system-extensions"></a><span data-ttu-id="1cb7b-177">Aprobar extensiones del sistema</span><span class="sxs-lookup"><span data-stu-id="1cb7b-177">Approve System Extensions</span></span>

<span data-ttu-id="1cb7b-178">Este perfil es necesario para macOS 10.15 (Catalina) o posterior.</span><span class="sxs-lookup"><span data-stu-id="1cb7b-178">This profile is needed for macOS 10.15 (Catalina) or newer.</span></span> <span data-ttu-id="1cb7b-179">Se omitirá en macOS antiguos.</span><span class="sxs-lookup"><span data-stu-id="1cb7b-179">It will be ignored on older macOS.</span></span>

1. <span data-ttu-id="1cb7b-180">Seleccione **Crear perfil en** **Perfiles de configuración**.</span><span class="sxs-lookup"><span data-stu-id="1cb7b-180">Select **Create Profile** under **Configuration Profiles**.</span></span>
1. <span data-ttu-id="1cb7b-181">Seleccione **Plataforma** = **macOS**, Tipo de perfil  = **Plantillas**.</span><span class="sxs-lookup"><span data-stu-id="1cb7b-181">Select **Platform**=**macOS**, **Profile type**=**Templates**.</span></span> <span data-ttu-id="1cb7b-182">**Nombre de plantilla** = **Extensiones**.</span><span class="sxs-lookup"><span data-stu-id="1cb7b-182">**Template name**=**Extensions**.</span></span> <span data-ttu-id="1cb7b-183">Haga clic en **Crear**.</span><span class="sxs-lookup"><span data-stu-id="1cb7b-183">Click **Create**.</span></span>
1. <span data-ttu-id="1cb7b-184">En la **pestaña Conceptos** básicos, asigne un nombre a este nuevo perfil.</span><span class="sxs-lookup"><span data-stu-id="1cb7b-184">In the **Basics** tab, give a name to this new profile.</span></span>
1. <span data-ttu-id="1cb7b-185">En la **pestaña Configuración,** expanda **Extensiones del sistema** agregue las siguientes entradas en la sección Extensiones **permitidas del** sistema:</span><span class="sxs-lookup"><span data-stu-id="1cb7b-185">In the **Configuration settings** tab, expand **System Extensions** add the following entries in the **Allowed system extensions** section:</span></span>

    <span data-ttu-id="1cb7b-186">Identificador de agrupación</span><span class="sxs-lookup"><span data-stu-id="1cb7b-186">Bundle identifier</span></span>         | <span data-ttu-id="1cb7b-187">Identificador de equipo</span><span class="sxs-lookup"><span data-stu-id="1cb7b-187">Team identifier</span></span>
    --------------------------|----------------
    <span data-ttu-id="1cb7b-188">com.microsoft.wdav.epsext</span><span class="sxs-lookup"><span data-stu-id="1cb7b-188">com.microsoft.wdav.epsext</span></span> | <span data-ttu-id="1cb7b-189">UBF8T346G9</span><span class="sxs-lookup"><span data-stu-id="1cb7b-189">UBF8T346G9</span></span>
    <span data-ttu-id="1cb7b-190">com.microsoft.wdav.netext</span><span class="sxs-lookup"><span data-stu-id="1cb7b-190">com.microsoft.wdav.netext</span></span> | <span data-ttu-id="1cb7b-191">UBF8T346G9</span><span class="sxs-lookup"><span data-stu-id="1cb7b-191">UBF8T346G9</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="1cb7b-192">![Configuración de extensión del sistema](images/mac-system-extension-intune2.png)</span><span class="sxs-lookup"><span data-stu-id="1cb7b-192">![System extension settings](images/mac-system-extension-intune2.png)</span></span>

1. <span data-ttu-id="1cb7b-193">En la **pestaña Asignaciones,** asigne este perfil a **Todos los usuarios & Todos los dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="1cb7b-193">In the **Assignments** tab, assign this profile to **All Users & All devices**.</span></span>
1. <span data-ttu-id="1cb7b-194">Revise y cree este perfil de configuración.</span><span class="sxs-lookup"><span data-stu-id="1cb7b-194">Review and create this configuration profile.</span></span>

### <a name="kernel-extensions"></a><span data-ttu-id="1cb7b-195">Extensiones de kernel</span><span class="sxs-lookup"><span data-stu-id="1cb7b-195">Kernel Extensions</span></span>

<span data-ttu-id="1cb7b-196">Este perfil es necesario para macOS 10.15 (Catalina) o versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="1cb7b-196">This profile is needed for macOS 10.15 (Catalina) or older.</span></span> <span data-ttu-id="1cb7b-197">Se omitirá en macOS más reciente.</span><span class="sxs-lookup"><span data-stu-id="1cb7b-197">It will be ignored on newer macOS.</span></span>

> [!CAUTION]
> <span data-ttu-id="1cb7b-198">Los dispositivos Apple Silicon (M1) no son compatibles con KEXT.</span><span class="sxs-lookup"><span data-stu-id="1cb7b-198">Apple Silicon (M1) devices do not support KEXT.</span></span> <span data-ttu-id="1cb7b-199">La instalación de un perfil de configuración que consta de directivas KEXT producirá un error en estos dispositivos.</span><span class="sxs-lookup"><span data-stu-id="1cb7b-199">Installation of a configuration profile consisting KEXT policies will fail on these devices.</span></span>

1. <span data-ttu-id="1cb7b-200">Seleccione **Crear perfil en** **Perfiles de configuración**.</span><span class="sxs-lookup"><span data-stu-id="1cb7b-200">Select **Create Profile** under **Configuration Profiles**.</span></span>
1. <span data-ttu-id="1cb7b-201">Seleccione **Plataforma** = **macOS**, Tipo de perfil  = **Plantillas**.</span><span class="sxs-lookup"><span data-stu-id="1cb7b-201">Select **Platform**=**macOS**, **Profile type**=**Templates**.</span></span> <span data-ttu-id="1cb7b-202">**Nombre de plantilla** = **Extensiones**.</span><span class="sxs-lookup"><span data-stu-id="1cb7b-202">**Template name**=**Extensions**.</span></span> <span data-ttu-id="1cb7b-203">Haga clic en **Crear**.</span><span class="sxs-lookup"><span data-stu-id="1cb7b-203">Click **Create**.</span></span>
1. <span data-ttu-id="1cb7b-204">En la **pestaña Conceptos** básicos, asigne un nombre a este nuevo perfil.</span><span class="sxs-lookup"><span data-stu-id="1cb7b-204">In the **Basics** tab, give a name to this new profile.</span></span>
1. <span data-ttu-id="1cb7b-205">En la **pestaña Configuración,** expanda **Extensiones de kernel**.</span><span class="sxs-lookup"><span data-stu-id="1cb7b-205">In the **Configuration settings** tab, expand **Kernel Extensions**.</span></span>
1. <span data-ttu-id="1cb7b-206">Establezca **el identificador de** equipo en **UBF8T346G9** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="1cb7b-206">Set **Team identifier** to **UBF8T346G9** and click **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="1cb7b-207">![Configuración de extensión de kernel](images/mac-kernel-extension-intune2.png)</span><span class="sxs-lookup"><span data-stu-id="1cb7b-207">![Kernel extension settings](images/mac-kernel-extension-intune2.png)</span></span>

1. <span data-ttu-id="1cb7b-208">En la **pestaña Asignaciones,** asigne este perfil a **Todos los usuarios & Todos los dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="1cb7b-208">In the **Assignments** tab, assign this profile to **All Users & All devices**.</span></span>
1. <span data-ttu-id="1cb7b-209">Revise y cree este perfil de configuración.</span><span class="sxs-lookup"><span data-stu-id="1cb7b-209">Review and create this configuration profile.</span></span>

### <a name="full-disk-access"></a><span data-ttu-id="1cb7b-210">Acceso en disco completo</span><span class="sxs-lookup"><span data-stu-id="1cb7b-210">Full Disk Access</span></span>

   > [!CAUTION]
   > <span data-ttu-id="1cb7b-211">macOS 10.15 (Catalina) contiene nuevas mejoras de seguridad y privacidad.</span><span class="sxs-lookup"><span data-stu-id="1cb7b-211">macOS 10.15 (Catalina) contains new security and privacy enhancements.</span></span> <span data-ttu-id="1cb7b-212">A partir de esta versión, de forma predeterminada, las aplicaciones no pueden acceder a determinadas ubicaciones del disco (como Documentos, Descargas, Escritorio, etc.) sin consentimiento explícito.</span><span class="sxs-lookup"><span data-stu-id="1cb7b-212">Beginning with this version, by default, applications are not able to access certain locations on disk (such as Documents, Downloads, Desktop, etc.) without explicit consent.</span></span> <span data-ttu-id="1cb7b-213">En ausencia de este consentimiento, Microsoft Defender para Endpoint no puede proteger completamente el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="1cb7b-213">In the absence of this consent, Microsoft Defender for Endpoint is not able to fully protect your device.</span></span>
   >
   > <span data-ttu-id="1cb7b-214">Este perfil de configuración concede acceso en disco completo a Microsoft Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="1cb7b-214">This configuration profile grants Full Disk Access to Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="1cb7b-215">Si configuró anteriormente Microsoft Defender para Endpoint a través de Intune, se recomienda actualizar la implementación con este perfil de configuración.</span><span class="sxs-lookup"><span data-stu-id="1cb7b-215">If you previously configured Microsoft Defender for Endpoint through Intune, we recommend you update the deployment with this configuration profile.</span></span>

<span data-ttu-id="1cb7b-216">Descargue [**fulldisk.mobileconfig**](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/fulldisk.mobileconfig) desde [nuestro repositorio GitHub archivo](https://github.com/microsoft/mdatp-xplat/tree/master/macos/mobileconfig/profiles).</span><span class="sxs-lookup"><span data-stu-id="1cb7b-216">Download [**fulldisk.mobileconfig**](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/fulldisk.mobileconfig) from [our GitHub repository](https://github.com/microsoft/mdatp-xplat/tree/master/macos/mobileconfig/profiles).</span></span>

<span data-ttu-id="1cb7b-217">Siga las instrucciones para incorporar [blobs](#onboarding-blob) desde arriba, usando "MDATP Full Disk Access" como nombre de perfil y **descargado fulldisk.mobileconfig** como nombre de perfil de configuración.</span><span class="sxs-lookup"><span data-stu-id="1cb7b-217">Follow the instructions for [Onboarding blob](#onboarding-blob) from above, using "MDATP Full Disk Access" as profile name, and downloaded **fulldisk.mobileconfig** as Configuration profile name.</span></span>

### <a name="network-filter"></a><span data-ttu-id="1cb7b-218">Filtro de red</span><span class="sxs-lookup"><span data-stu-id="1cb7b-218">Network Filter</span></span>

<span data-ttu-id="1cb7b-219">Como parte de las capacidades de detección y respuesta de puntos de conexión, Microsoft Defender para endpoint en macOS inspecciona el tráfico de sockets e informa de esta información al portal Centro de seguridad de Microsoft Defender web.</span><span class="sxs-lookup"><span data-stu-id="1cb7b-219">As part of the Endpoint Detection and Response capabilities, Microsoft Defender for Endpoint on macOS inspects socket traffic and reports this information to the Microsoft Defender Security Center portal.</span></span> <span data-ttu-id="1cb7b-220">La siguiente directiva permite que la extensión de red realice esta funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="1cb7b-220">The following policy allows the network extension to perform this functionality.</span></span>

<span data-ttu-id="1cb7b-221">Descargue [**netfilter.mobileconfig**](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/netfilter.mobileconfig) desde [nuestro GitHub de archivos](https://github.com/microsoft/mdatp-xplat/tree/master/macos/mobileconfig/profiles).</span><span class="sxs-lookup"><span data-stu-id="1cb7b-221">Download [**netfilter.mobileconfig**](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/netfilter.mobileconfig) from [our GitHub repository](https://github.com/microsoft/mdatp-xplat/tree/master/macos/mobileconfig/profiles).</span></span>

<span data-ttu-id="1cb7b-222">Siga las instrucciones para incorporar [blobs](#onboarding-blob) desde arriba, usando "MDATP Network Filter" como nombre de perfil y **descargado netfilter.mobileconfig** como nombre de perfil de configuración.</span><span class="sxs-lookup"><span data-stu-id="1cb7b-222">Follow the instructions for [Onboarding blob](#onboarding-blob) from above, using "MDATP Network Filter" as profile name, and downloaded **netfilter.mobileconfig** as Configuration profile name.</span></span>

### <a name="notifications"></a><span data-ttu-id="1cb7b-223">Notificaciones</span><span class="sxs-lookup"><span data-stu-id="1cb7b-223">Notifications</span></span>

<span data-ttu-id="1cb7b-224">Este perfil se usa para permitir que Microsoft Defender para Endpoint en macOS y Microsoft Auto Update muestren notificaciones en la interfaz de usuario en macOS 10.15 (Catalina) o versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="1cb7b-224">This profile is used to allow Microsoft Defender for Endpoint on macOS and Microsoft Auto Update to display notifications in UI on macOS 10.15 (Catalina) or newer.</span></span>

<span data-ttu-id="1cb7b-225">Descargue [**notif.mobileconfig**](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/notif.mobileconfig) desde [nuestro repositorio GitHub archivo](https://github.com/microsoft/mdatp-xplat/tree/master/macos/mobileconfig/profiles).</span><span class="sxs-lookup"><span data-stu-id="1cb7b-225">Download [**notif.mobileconfig**](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/notif.mobileconfig) from [our GitHub repository](https://github.com/microsoft/mdatp-xplat/tree/master/macos/mobileconfig/profiles).</span></span>

<span data-ttu-id="1cb7b-226">Siga las instrucciones para incorporar [blobs](#onboarding-blob) desde arriba, usando "MDATP Network Filter" como nombre de perfil y descargado **notif.mobileconfig** como nombre de perfil de configuración.</span><span class="sxs-lookup"><span data-stu-id="1cb7b-226">Follow the instructions for [Onboarding blob](#onboarding-blob) from above, using "MDATP Network Filter" as profile name, and downloaded **notif.mobileconfig** as Configuration profile name.</span></span>

### <a name="view-status"></a><span data-ttu-id="1cb7b-227">Ver estado</span><span class="sxs-lookup"><span data-stu-id="1cb7b-227">View Status</span></span>

<span data-ttu-id="1cb7b-228">Una vez que los cambios de Intune se propaguen a los dispositivos inscritos, puede verlos en **Estado**  >  **del dispositivo de supervisión:**</span><span class="sxs-lookup"><span data-stu-id="1cb7b-228">Once the Intune changes are propagated to the enrolled devices, you can see them listed under **Monitor** > **Device status**:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="1cb7b-229">![Vista del estado del dispositivo en monitor](images/mdatp-7-devicestatusblade.png)</span><span class="sxs-lookup"><span data-stu-id="1cb7b-229">![View of Device Status in Monitor](images/mdatp-7-devicestatusblade.png)</span></span>

## <a name="publish-application"></a><span data-ttu-id="1cb7b-230">Publicar aplicación</span><span class="sxs-lookup"><span data-stu-id="1cb7b-230">Publish application</span></span>

<span data-ttu-id="1cb7b-231">Este paso permite implementar Microsoft Defender para Endpoint en equipos inscritos.</span><span class="sxs-lookup"><span data-stu-id="1cb7b-231">This step enables deploying Microsoft Defender for Endpoint to enrolled machines.</span></span>

1. <span data-ttu-id="1cb7b-232">En el [Centro Microsoft Endpoint Manager administración,](https://endpoint.microsoft.com/)abra **Aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="1cb7b-232">In the [Microsoft Endpoint Manager admin center](https://endpoint.microsoft.com/), open **Apps**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="1cb7b-233">![Listo para crear aplicación](images/mdatp-8-app-before.png)</span><span class="sxs-lookup"><span data-stu-id="1cb7b-233">![Ready to create application](images/mdatp-8-app-before.png)</span></span>

1. <span data-ttu-id="1cb7b-234">Seleccione Por plataforma > macOS > Agregar.</span><span class="sxs-lookup"><span data-stu-id="1cb7b-234">Select By platform > macOS > Add.</span></span>
1. <span data-ttu-id="1cb7b-235">Elija **Tipo de** aplicación = **macOS**, haga clic en **Seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="1cb7b-235">Choose **App type**=**macOS**, click **Select**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="1cb7b-236">![Especificar tipo de aplicación](images/mdatp-9-app-type.png)</span><span class="sxs-lookup"><span data-stu-id="1cb7b-236">![Specify application type](images/mdatp-9-app-type.png)</span></span>

1. <span data-ttu-id="1cb7b-237">Mantenga los valores predeterminados, haga clic **en Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="1cb7b-237">Keep default values, click **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="1cb7b-238">![Propiedades de la aplicación](images/mdatp-10-properties.png)</span><span class="sxs-lookup"><span data-stu-id="1cb7b-238">![Application properties](images/mdatp-10-properties.png)</span></span>

1. <span data-ttu-id="1cb7b-239">Agregar asignaciones, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="1cb7b-239">Add assignments, click **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="1cb7b-240">![Captura de pantalla de información de asignaciones de Intune](images/mdatp-11-assignments.png)</span><span class="sxs-lookup"><span data-stu-id="1cb7b-240">![Intune assignments info screenshot](images/mdatp-11-assignments.png)</span></span>

1. <span data-ttu-id="1cb7b-241">Revisar y **crear**.</span><span class="sxs-lookup"><span data-stu-id="1cb7b-241">Review and **Create**.</span></span>
1. <span data-ttu-id="1cb7b-242">Puedes visitar **Aplicaciones**  >  **por plataforma**  >  **macOS** para verlo en la lista de todas las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="1cb7b-242">You can visit **Apps** > **By platform** > **macOS** to see it on the list of all applications.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="1cb7b-243">![Lista de aplicaciones](images/mdatp-12-applications.png)</span><span class="sxs-lookup"><span data-stu-id="1cb7b-243">![Applications list](images/mdatp-12-applications.png)</span></span>

<span data-ttu-id="1cb7b-244">(Puede encontrar información detallada en la página de Intune para la implementación [de Defender](/mem/intune/apps/apps-advanced-threat-protection-macos)).)</span><span class="sxs-lookup"><span data-stu-id="1cb7b-244">(You can find detailed information on the [Intune's page for Defender deployment](/mem/intune/apps/apps-advanced-threat-protection-macos).)</span></span>

   > [!CAUTION]
   > <span data-ttu-id="1cb7b-245">Debe crear todos los perfiles de configuración necesarios e insertarlos en todas las máquinas, como se explicó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="1cb7b-245">You have to create all required configuration profiles and push them to all machines, as explained above.</span></span>

## <a name="client-device-setup"></a><span data-ttu-id="1cb7b-246">Configuración del dispositivo cliente</span><span class="sxs-lookup"><span data-stu-id="1cb7b-246">Client device setup</span></span>

<span data-ttu-id="1cb7b-247">No necesitas ningún aprovisionamiento especial para un dispositivo Mac más allá de una instalación [Portal de empresa estándar.](/intune-user-help/enroll-your-device-in-intune-macos-cp)</span><span class="sxs-lookup"><span data-stu-id="1cb7b-247">You don't need any special provisioning for a Mac device beyond a standard [Company Portal installation](/intune-user-help/enroll-your-device-in-intune-macos-cp).</span></span>

1. <span data-ttu-id="1cb7b-248">Confirme la administración de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="1cb7b-248">Confirm device management.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="1cb7b-249">![Confirmar captura de pantalla de administración de dispositivos](images/mdatp-3-confirmdevicemgmt.png)</span><span class="sxs-lookup"><span data-stu-id="1cb7b-249">![Confirm device management screenshot](images/mdatp-3-confirmdevicemgmt.png)</span></span>

    <span data-ttu-id="1cb7b-250">Seleccione **Abrir preferencias del sistema,** busque **Perfil de administración** en la lista y seleccione **Aprobar...**. El perfil de administración se mostrará como **Verificado**:</span><span class="sxs-lookup"><span data-stu-id="1cb7b-250">Select **Open System Preferences**, locate **Management Profile** on the list, and select **Approve...**. Your Management Profile would be displayed as **Verified**:</span></span>

    ![Captura de pantalla del perfil de administración](images/mdatp-4-managementprofile.png)

2. <span data-ttu-id="1cb7b-252">Seleccione **Continuar** y complete la inscripción.</span><span class="sxs-lookup"><span data-stu-id="1cb7b-252">Select **Continue** and complete the enrollment.</span></span>

   <span data-ttu-id="1cb7b-253">Ahora puede inscribir más dispositivos.</span><span class="sxs-lookup"><span data-stu-id="1cb7b-253">You may now enroll more devices.</span></span> <span data-ttu-id="1cb7b-254">También puede inscribirlos más adelante, una vez que haya terminado de aprovisionar paquetes de aplicación y configuración del sistema.</span><span class="sxs-lookup"><span data-stu-id="1cb7b-254">You can also enroll them later, after you have finished provisioning system configuration and application packages.</span></span>

3. <span data-ttu-id="1cb7b-255">En Intune, abra **Administrar**  >  **dispositivos**  >  **Todos los dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="1cb7b-255">In Intune, open **Manage** > **Devices** > **All devices**.</span></span> <span data-ttu-id="1cb7b-256">Aquí puedes ver el dispositivo entre los que aparecen en la lista:</span><span class="sxs-lookup"><span data-stu-id="1cb7b-256">Here you can see your device among those listed:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1cb7b-257">![Captura de pantalla Agregar dispositivos](images/mdatp-5-alldevices.png)</span><span class="sxs-lookup"><span data-stu-id="1cb7b-257">![Add Devices screenshot](images/mdatp-5-alldevices.png)</span></span>

## <a name="verify-client-device-state"></a><span data-ttu-id="1cb7b-258">Comprobar el estado del dispositivo cliente</span><span class="sxs-lookup"><span data-stu-id="1cb7b-258">Verify client device state</span></span>

1. <span data-ttu-id="1cb7b-259">Después de implementar los perfiles de configuración en los dispositivos, abre **Perfiles** de  >  **preferencias del sistema** en tu dispositivo Mac.</span><span class="sxs-lookup"><span data-stu-id="1cb7b-259">After the configuration profiles are deployed to your devices, open **System Preferences** > **Profiles** on your Mac device.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="1cb7b-260">![Captura de pantalla Preferencias del sistema](images/mdatp-13-systempreferences.png)</span><span class="sxs-lookup"><span data-stu-id="1cb7b-260">![System Preferences screenshot](images/mdatp-13-systempreferences.png)</span></span>

    ![Captura de pantalla Perfiles de preferencias del sistema](images/mdatp-14-systempreferencesprofiles.png)

2. <span data-ttu-id="1cb7b-262">Compruebe que los siguientes perfiles de configuración están presentes e instalados.</span><span class="sxs-lookup"><span data-stu-id="1cb7b-262">Verify that the following configuration profiles are present and installed.</span></span> <span data-ttu-id="1cb7b-263">El **perfil de administración** debe ser el perfil del sistema de Intune.</span><span class="sxs-lookup"><span data-stu-id="1cb7b-263">The **Management Profile** should be the Intune system profile.</span></span> <span data-ttu-id="1cb7b-264">_Wdav-config y_ _wdav-kext_ son perfiles de configuración del sistema que se agregaron en Intune:</span><span class="sxs-lookup"><span data-stu-id="1cb7b-264">_Wdav-config_ and _wdav-kext_ are system configuration profiles that were added in Intune:</span></span>

    ![Captura de pantalla de perfiles](images/mdatp-15-managementprofileconfig.png)

3. <span data-ttu-id="1cb7b-266">También debería ver el icono de Microsoft Defender para endpoint en la esquina superior derecha:</span><span class="sxs-lookup"><span data-stu-id="1cb7b-266">You should also see the Microsoft Defender for Endpoint icon in the top-right corner:</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="1cb7b-267">![Icono de Microsoft Defender para endpoint en la captura de pantalla de la barra de estado](images/mdatp-icon-bar.png)</span><span class="sxs-lookup"><span data-stu-id="1cb7b-267">![Microsoft Defender for Endpoint icon in status bar screenshot](images/mdatp-icon-bar.png)</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="1cb7b-268">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="1cb7b-268">Troubleshooting</span></span>

<span data-ttu-id="1cb7b-269">Problema: no se encontró ninguna licencia.</span><span class="sxs-lookup"><span data-stu-id="1cb7b-269">Issue: No license found.</span></span>

<span data-ttu-id="1cb7b-270">Solución: siga los pasos anteriores para crear un perfil de dispositivo mediante WindowsDefenderATPOnboarding.xml.</span><span class="sxs-lookup"><span data-stu-id="1cb7b-270">Solution: Follow the steps above to create a device profile using WindowsDefenderATPOnboarding.xml.</span></span>

## <a name="logging-installation-issues"></a><span data-ttu-id="1cb7b-271">Problemas de instalación de registro</span><span class="sxs-lookup"><span data-stu-id="1cb7b-271">Logging installation issues</span></span>

<span data-ttu-id="1cb7b-272">Para obtener más información sobre cómo encontrar el registro generado automáticamente que crea el instalador cuando se produce un error, vea [Logging installation issues](mac-resources.md#logging-installation-issues).</span><span class="sxs-lookup"><span data-stu-id="1cb7b-272">For more information on how to find the automatically generated log that is created by the installer when an error occurs, see [Logging installation issues](mac-resources.md#logging-installation-issues).</span></span>

## <a name="uninstallation"></a><span data-ttu-id="1cb7b-273">Desinstalación</span><span class="sxs-lookup"><span data-stu-id="1cb7b-273">Uninstallation</span></span>

<span data-ttu-id="1cb7b-274">Consulta [Desinstalar para obtener](mac-resources.md#uninstalling) más información sobre cómo quitar Microsoft Defender para Endpoint en macOS de los dispositivos cliente.</span><span class="sxs-lookup"><span data-stu-id="1cb7b-274">See [Uninstalling](mac-resources.md#uninstalling) for details on how to remove Microsoft Defender for Endpoint on macOS from client devices.</span></span>
