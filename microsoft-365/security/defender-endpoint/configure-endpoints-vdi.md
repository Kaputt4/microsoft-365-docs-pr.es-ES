---
title: Incorporar dispositivos de infraestructura de escritorio virtual (VDI) no persistente
description: Implemente el paquete de configuración en el dispositivo de infraestructura de escritorio virtual (VDI) para que se incorpore a Microsoft Defender para el servicio de extremo.
keywords: configurar dispositivos de infraestructura de escritorio virtual (VDI), vdi, administración de dispositivos, configurar Microsoft Defender para endpoint, puntos de conexión
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
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 04/16/2020
ms.technology: mde
ms.openlocfilehash: 555f96dc1f45fb6a406b5993d0b8e4a3745c283b
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339639"
---
# <a name="onboard-the-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a><span data-ttu-id="533d2-104">Incorporación de los dispositivos de infraestructura de escritorio virtual (VDI) no persistentes</span><span class="sxs-lookup"><span data-stu-id="533d2-104">Onboard the non-persistent virtual desktop infrastructure (VDI) devices</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="533d2-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="533d2-105">**Applies to:**</span></span>
- [<span data-ttu-id="533d2-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="533d2-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="533d2-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="533d2-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)
- <span data-ttu-id="533d2-108">Dispositivos de infraestructura de escritorio virtual (VDI)</span><span class="sxs-lookup"><span data-stu-id="533d2-108">Virtual desktop infrastructure (VDI) devices</span></span>
- <span data-ttu-id="533d2-109">Windows 10, Windows Server 2019, Windows Server 2008R2/2012R2/2016</span><span class="sxs-lookup"><span data-stu-id="533d2-109">Windows 10, Windows Server 2019, Windows Server 2008R2/2012R2/2016</span></span>

><span data-ttu-id="533d2-110">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="533d2-110">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="533d2-111">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="533d2-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configvdi-abovefoldlink)

## <a name="onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a><span data-ttu-id="533d2-112">Incorporar dispositivos de infraestructura de escritorio virtual (VDI) no persistente</span><span class="sxs-lookup"><span data-stu-id="533d2-112">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>

<span data-ttu-id="533d2-113">Defender for Endpoint admite la incorporación de sesiones VDI no persistentes.</span><span class="sxs-lookup"><span data-stu-id="533d2-113">Defender for Endpoint supports non-persistent VDI session onboarding.</span></span> 


<span data-ttu-id="533d2-114">Puede haber desafíos asociados al incorporar LOS VDIs.</span><span class="sxs-lookup"><span data-stu-id="533d2-114">There might be associated challenges when onboarding VDIs.</span></span> <span data-ttu-id="533d2-115">Los siguientes son los desafíos típicos de este escenario:</span><span class="sxs-lookup"><span data-stu-id="533d2-115">The following are typical challenges for this scenario:</span></span>

- <span data-ttu-id="533d2-116">Incorporación anticipada instantánea de sesiones de corta duración, que deben incorporarse a Defender for Endpoint antes del aprovisionamiento real.</span><span class="sxs-lookup"><span data-stu-id="533d2-116">Instant early onboarding of a short-lived sessions, which must be onboarded to Defender for Endpoint prior to the actual provisioning.</span></span>
- <span data-ttu-id="533d2-117">El nombre del dispositivo normalmente se reutiliza para nuevas sesiones.</span><span class="sxs-lookup"><span data-stu-id="533d2-117">The device name is typically reused for new sessions.</span></span>

<span data-ttu-id="533d2-118">Los dispositivos VDI pueden aparecer en el portal de Defender for Endpoint como:</span><span class="sxs-lookup"><span data-stu-id="533d2-118">VDI devices can appear in Defender for Endpoint portal as either:</span></span>

- <span data-ttu-id="533d2-119">Entrada única para cada dispositivo.</span><span class="sxs-lookup"><span data-stu-id="533d2-119">Single entry for each device.</span></span>

  > [!NOTE]
  > <span data-ttu-id="533d2-120">En este caso, se debe configurar el *mismo* nombre de dispositivo cuando se crea la sesión, por ejemplo, mediante un archivo de respuesta desatendido.</span><span class="sxs-lookup"><span data-stu-id="533d2-120">In this case, the *same* device name must be configured when the session is created, for example using an unattended answer file.</span></span>

- <span data-ttu-id="533d2-121">Varias entradas para cada dispositivo: una para cada sesión.</span><span class="sxs-lookup"><span data-stu-id="533d2-121">Multiple entries for each device - one for each session.</span></span>

<span data-ttu-id="533d2-122">Los siguientes pasos le guiarán a través de la incorporación de dispositivos VDI y resaltarán los pasos para entradas únicas y múltiples.</span><span class="sxs-lookup"><span data-stu-id="533d2-122">The following steps will guide you through onboarding VDI devices and will highlight steps for single and multiple entries.</span></span>

>[!WARNING]
> <span data-ttu-id="533d2-123">En los entornos en los que hay configuraciones de recursos bajos, el procedimiento de arranque de VDI puede ralentizar la incorporación del sensor Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="533d2-123">For environments where there are low resource configurations, the VDI boot procedure might slow the Defender for Endpoint sensor onboarding.</span></span> 


### <a name="for-windows-10-or-windows-server-2019"></a><span data-ttu-id="533d2-124">Para Windows 10 o Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="533d2-124">For Windows 10 or Windows Server 2019</span></span>

1.  <span data-ttu-id="533d2-125">Abra el archivo de configuración .zip VDI (*WindowsDefenderATPOnboardingPackage.zip*) que descargó del Asistente para incorporación de servicios.</span><span class="sxs-lookup"><span data-stu-id="533d2-125">Open the VDI configuration package .zip file (*WindowsDefenderATPOnboardingPackage.zip*) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="533d2-126">También puede obtener el paquete desde [Microsoft 365 Defender portal:](https://security.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="533d2-126">You can also get the package from [Microsoft 365 Defender portal](https://security.microsoft.com/):</span></span>

    1. <span data-ttu-id="533d2-127">En el panel de navegación, **seleccione Configuración**  >  **Endpoints**  >  **Device management**  >  **Onboarding**.</span><span class="sxs-lookup"><span data-stu-id="533d2-127">In the navigation pane, select **Settings** > **Endpoints** > **Device management** > **Onboarding**.</span></span>

    1. <span data-ttu-id="533d2-128">Seleccione Windows 10 como sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="533d2-128">Select Windows 10 as the operating system.</span></span>

    1.  <span data-ttu-id="533d2-129">En el **campo Método de** implementación, seleccione Scripts de incorporación de VDI para puntos de conexión no **persistentes.**</span><span class="sxs-lookup"><span data-stu-id="533d2-129">In the **Deployment method** field, select **VDI onboarding scripts for non-persistent endpoints**.</span></span>

    1. <span data-ttu-id="533d2-130">Haga **clic en Descargar paquete** y guarde el .zip archivo.</span><span class="sxs-lookup"><span data-stu-id="533d2-130">Click **Download package** and save the .zip file.</span></span>

2. <span data-ttu-id="533d2-131">Copie los archivos de la carpeta WindowsDefenderATPOnboardingPackage extraída del archivo .zip en la imagen `golden/master` de la ruta de acceso `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` .</span><span class="sxs-lookup"><span data-stu-id="533d2-131">Copy the files from the WindowsDefenderATPOnboardingPackage folder extracted from the .zip file into the `golden/master` image under the path `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup`.</span></span> 

    1. <span data-ttu-id="533d2-132">Si no implementa una sola entrada para cada dispositivo, copie WindowsDefenderATPOnboardingScript.cmd.</span><span class="sxs-lookup"><span data-stu-id="533d2-132">If you are not implementing a single entry for each device, copy WindowsDefenderATPOnboardingScript.cmd.</span></span>

    1. <span data-ttu-id="533d2-133">Si vas a implementar una sola entrada para cada dispositivo, copia tanto Onboard-NonPersistentMachine.ps1 como WindowsDefenderATPOnboardingScript.cmd.</span><span class="sxs-lookup"><span data-stu-id="533d2-133">If you are implementing a single entry for each device, copy both Onboard-NonPersistentMachine.ps1 and WindowsDefenderATPOnboardingScript.cmd.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="533d2-134">Si no ve la `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` carpeta, podría estar oculta.</span><span class="sxs-lookup"><span data-stu-id="533d2-134">If you don't see the `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` folder, it might be hidden.</span></span> <span data-ttu-id="533d2-135">Tendrás que elegir la opción Mostrar **archivos y carpetas** ocultos en el Explorador de archivos.</span><span class="sxs-lookup"><span data-stu-id="533d2-135">You'll need to choose the **Show hidden files and folders** option from File Explorer.</span></span>

3. <span data-ttu-id="533d2-136">Abra una ventana Editor de directivas de grupo local y vaya a **Configuración** del  >  **equipo Windows Configuración** inicio de  >    >  **scripts.**</span><span class="sxs-lookup"><span data-stu-id="533d2-136">Open a Local Group Policy Editor window and navigate to **Computer Configuration** > **Windows Settings** > **Scripts** > **Startup**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="533d2-137">La directiva de grupo de dominio también se puede usar para incorporar dispositivos VDI no persistentes.</span><span class="sxs-lookup"><span data-stu-id="533d2-137">Domain Group Policy may also be used for onboarding non-persistent VDI devices.</span></span>

4. <span data-ttu-id="533d2-138">Según el método que quiera implementar, siga los pasos correspondientes:</span><span class="sxs-lookup"><span data-stu-id="533d2-138">Depending on the method you'd like to implement, follow the appropriate steps:</span></span>

   - <span data-ttu-id="533d2-139">Para una sola entrada para cada dispositivo:</span><span class="sxs-lookup"><span data-stu-id="533d2-139">For single entry for each device:</span></span>
   
     <span data-ttu-id="533d2-140">Seleccione la **pestaña Scripts de PowerShell** y, a continuación, haga clic en Agregar **(el** Explorador de Windows se abrirá directamente en la ruta de acceso en la que copió el script de incorporación anteriormente).</span><span class="sxs-lookup"><span data-stu-id="533d2-140">Select the **PowerShell Scripts** tab, then click **Add** (Windows Explorer will open directly in the path where you copied the onboarding script earlier).</span></span> <span data-ttu-id="533d2-141">Navegue a la incorporación del script de PowerShell `Onboard-NonPersistentMachine.ps1` .</span><span class="sxs-lookup"><span data-stu-id="533d2-141">Navigate to onboarding PowerShell script `Onboard-NonPersistentMachine.ps1`.</span></span> <span data-ttu-id="533d2-142">No es necesario especificar el otro archivo, ya que se desencadenará automáticamente.</span><span class="sxs-lookup"><span data-stu-id="533d2-142">There is no need to specify the other file, as it will be triggered automatically.</span></span>
   
   - <span data-ttu-id="533d2-143">Para varias entradas para cada dispositivo:</span><span class="sxs-lookup"><span data-stu-id="533d2-143">For multiple entries for each device:</span></span>
   
     <span data-ttu-id="533d2-144">Seleccione la **pestaña Scripts** y, a continuación, haga clic en Agregar **(Windows** Explorer se abrirá directamente en la ruta de acceso en la que copió el script de incorporación anteriormente).</span><span class="sxs-lookup"><span data-stu-id="533d2-144">Select the **Scripts** tab, then click **Add** (Windows Explorer will open directly in the path where you copied the onboarding script earlier).</span></span> <span data-ttu-id="533d2-145">Vaya al script bash de incorporación `WindowsDefenderATPOnboardingScript.cmd` .</span><span class="sxs-lookup"><span data-stu-id="533d2-145">Navigate to the onboarding bash script `WindowsDefenderATPOnboardingScript.cmd`.</span></span>

5. <span data-ttu-id="533d2-146">Pruebe la solución:</span><span class="sxs-lookup"><span data-stu-id="533d2-146">Test your solution:</span></span>

   1. <span data-ttu-id="533d2-147">Crea un grupo de servidores con un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="533d2-147">Create a pool with one device.</span></span>
      
   1. <span data-ttu-id="533d2-148">Inicie sesión en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="533d2-148">Logon to device.</span></span>
      
   1. <span data-ttu-id="533d2-149">Cierre sesión desde el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="533d2-149">Logoff from device.</span></span>

   1. <span data-ttu-id="533d2-150">Inicie sesión en el dispositivo con otro usuario.</span><span class="sxs-lookup"><span data-stu-id="533d2-150">Logon to device with another user.</span></span>
      
   1. <span data-ttu-id="533d2-151">Según el método que quiera implementar, siga los pasos correspondientes:</span><span class="sxs-lookup"><span data-stu-id="533d2-151">Depending on the method you'd like to implement, follow the appropriate steps:</span></span>
   
      - <span data-ttu-id="533d2-152">Para una sola entrada para cada dispositivo:</span><span class="sxs-lookup"><span data-stu-id="533d2-152">For single entry for each device:</span></span> 
    
        <span data-ttu-id="533d2-153">Compruebe solo una entrada en Microsoft 365 Defender portal.</span><span class="sxs-lookup"><span data-stu-id="533d2-153">Check only one entry in Microsoft 365 Defender portal.</span></span>

      - <span data-ttu-id="533d2-154">Para varias entradas para cada dispositivo:</span><span class="sxs-lookup"><span data-stu-id="533d2-154">For multiple entries for each device:</span></span> 
       
        <span data-ttu-id="533d2-155">Compruebe varias entradas en Microsoft 365 Defender portal.</span><span class="sxs-lookup"><span data-stu-id="533d2-155">Check multiple entries in Microsoft 365 Defender portal.</span></span>

6. <span data-ttu-id="533d2-156">Haga **clic en Lista de** dispositivos en el panel de navegación.</span><span class="sxs-lookup"><span data-stu-id="533d2-156">Click **Devices list** on the Navigation pane.</span></span>

7. <span data-ttu-id="533d2-157">Para usar la función de búsqueda, escriba el nombre del dispositivo y seleccione **Dispositivo** como tipo de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="533d2-157">Use the search function by entering the device name and select **Device** as search type.</span></span>


## <a name="for-downlevel-skus"></a><span data-ttu-id="533d2-158">Para SKU de nivel inferior</span><span class="sxs-lookup"><span data-stu-id="533d2-158">For downlevel SKUs</span></span>

> [!NOTE]
> <span data-ttu-id="533d2-159">El registro siguiente es relevante solo cuando el objetivo es lograr una "entrada única para cada dispositivo".</span><span class="sxs-lookup"><span data-stu-id="533d2-159">The following registry is relevant only when the aim is to achieve a 'Single entry for each device'.</span></span>

1. <span data-ttu-id="533d2-160">Establezca el valor del Registro en:</span><span class="sxs-lookup"><span data-stu-id="533d2-160">Set registry value to:</span></span>

    ```console
   [HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging]
    "VDI"="NonPersistent"
    ```

    <span data-ttu-id="533d2-161">o mediante la línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="533d2-161">or using command line:</span></span>

    ```console
    reg add "HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging" /v VDI /t REG_SZ /d "NonPersistent" /f
    ```

2. <span data-ttu-id="533d2-162">Siga el [proceso de incorporación del servidor](configure-server-endpoints.md#windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016).</span><span class="sxs-lookup"><span data-stu-id="533d2-162">Follow the [server onboarding process](configure-server-endpoints.md#windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016).</span></span> 



## <a name="updating-non-persistent-virtual-desktop-infrastructure-vdi-images"></a><span data-ttu-id="533d2-163">Actualización de imágenes de infraestructura de escritorio virtual (VDI) no persistente</span><span class="sxs-lookup"><span data-stu-id="533d2-163">Updating non-persistent virtual desktop infrastructure (VDI) images</span></span>
<span data-ttu-id="533d2-164">Como práctica recomendada, se recomienda usar herramientas de mantenimiento sin conexión para aplicar revisiones a imágenes doradas o maestras.</span><span class="sxs-lookup"><span data-stu-id="533d2-164">As a best practice, we recommend using offline servicing tools to patch golden/master images.</span></span><br>
<span data-ttu-id="533d2-165">Por ejemplo, puede usar los siguientes comandos para instalar una actualización mientras la imagen permanece sin conexión:</span><span class="sxs-lookup"><span data-stu-id="533d2-165">For example, you can use the below commands to install an update while the image remains offline:</span></span>

```console
DISM /Mount-image /ImageFile:"D:\Win10-1909.vhdx" /index:1 /MountDir:"C:\Temp\OfflineServicing" 
DISM /Image:"C:\Temp\OfflineServicing" /Add-Package /Packagepath:"C:\temp\patch\windows10.0-kb4541338-x64.msu"
DISM /Unmount-Image /MountDir:"C:\Temp\OfflineServicing" /commit
```

<span data-ttu-id="533d2-166">Para obtener más información sobre los comandos DISM y el mantenimiento sin conexión, consulte los artículos siguientes:</span><span class="sxs-lookup"><span data-stu-id="533d2-166">For more information on DISM commands and offline servicing, please refer to the articles below:</span></span>
- [<span data-ttu-id="533d2-167">Modificar una imagen Windows con DISM</span><span class="sxs-lookup"><span data-stu-id="533d2-167">Modify a Windows image using DISM</span></span>](/windows-hardware/manufacture/desktop/mount-and-modify-a-windows-image-using-dism)
- [<span data-ttu-id="533d2-168">Opciones de administración de imágenes Command-Line DISM</span><span class="sxs-lookup"><span data-stu-id="533d2-168">DISM Image Management Command-Line Options</span></span>](/windows-hardware/manufacture/desktop/dism-image-management-command-line-options-s14)
- [<span data-ttu-id="533d2-169">Reducir el tamaño del almacén de componentes en una imagen Windows sin conexión</span><span class="sxs-lookup"><span data-stu-id="533d2-169">Reduce the Size of the Component Store in an Offline Windows Image</span></span>](/windows-hardware/manufacture/desktop/reduce-the-size-of-the-component-store-in-an-offline-windows-image)

<span data-ttu-id="533d2-170">Si el mantenimiento sin conexión no es una opción viable para el entorno VDI no persistente, se deben seguir los siguientes pasos para garantizar la coherencia y el estado del sensor:</span><span class="sxs-lookup"><span data-stu-id="533d2-170">If offline servicing is not a viable option for your non-persistent VDI environment, the following steps should be taken to ensure consistency and sensor health:</span></span>

1. <span data-ttu-id="533d2-171">Después de arrancar la imagen maestra para el mantenimiento o la revisión en línea, ejecute un script de offboarding para desactivar el sensor Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="533d2-171">After booting the master image for online servicing or patching, run an offboarding script to turn off the Defender for Endpoint sensor.</span></span> <span data-ttu-id="533d2-172">Para obtener más información, vea [Offboard devices using a local script](configure-endpoints-script.md#offboard-devices-using-a-local-script).</span><span class="sxs-lookup"><span data-stu-id="533d2-172">For more information, see [Offboard devices using a local script](configure-endpoints-script.md#offboard-devices-using-a-local-script).</span></span>

2. <span data-ttu-id="533d2-173">Asegúrese de que el sensor está detenido ejecutando el comando siguiente en una ventana cmd:</span><span class="sxs-lookup"><span data-stu-id="533d2-173">Ensure the sensor is stopped by running the command below in a CMD window:</span></span>

   ```console
   sc query sense
   ```

3. <span data-ttu-id="533d2-174">Servicio de la imagen según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="533d2-174">Service the image as needed.</span></span>

4. <span data-ttu-id="533d2-175">Ejecute los siguientes comandos mediante PsExec.exe (que se pueden descargar para limpiar el contenido de la carpeta cibernética que el sensor puede haber acumulado https://download.sysinternals.com/files/PSTools.zip) desde el arranque:</span><span class="sxs-lookup"><span data-stu-id="533d2-175">Run the below commands using PsExec.exe (which can be downloaded from https://download.sysinternals.com/files/PSTools.zip) to cleanup the cyber folder contents that the sensor may have accumulated since boot:</span></span>

    ```console
    PsExec.exe -s cmd.exe
    cd "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Cyber"
    del *.* /f /s /q
    REG DELETE “HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection" /v senseGuid /f
    exit
    ```

5. <span data-ttu-id="533d2-176">Vuelva a sellar la imagen dorada/maestra como lo haría normalmente.</span><span class="sxs-lookup"><span data-stu-id="533d2-176">Re-seal the golden/master image as you normally would.</span></span>

## <a name="related-topics"></a><span data-ttu-id="533d2-177">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="533d2-177">Related topics</span></span>
- [<span data-ttu-id="533d2-178">Incorporación Windows 10 dispositivos con directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="533d2-178">Onboard Windows 10 devices using Group Policy</span></span>](configure-endpoints-gp.md)
- [<span data-ttu-id="533d2-179">Incorporar Windows 10 dispositivos con Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="533d2-179">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md)
- [<span data-ttu-id="533d2-180">Incorporar dispositivos Windows 10 con herramientas de Administración de dispositivos móviles</span><span class="sxs-lookup"><span data-stu-id="533d2-180">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](configure-endpoints-mdm.md)
- [<span data-ttu-id="533d2-181">Incorporar dispositivos Windows 10 mediante un script local</span><span class="sxs-lookup"><span data-stu-id="533d2-181">Onboard Windows 10 devices using a local script</span></span>](configure-endpoints-script.md)
- [<span data-ttu-id="533d2-182">Solucionar problemas de incorporación de puntos de conexión de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="533d2-182">Troubleshoot Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
