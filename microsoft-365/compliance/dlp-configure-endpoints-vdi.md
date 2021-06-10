---
title: Incorporar dispositivos de infraestructura de escritorio virtual (VDI) no persistente
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Implemente el paquete de configuración en el dispositivo de infraestructura de escritorio virtual (VDI) para que se incorpore al servicio de prevención de pérdida de datos Microsoft 365 endpoint.
ms.openlocfilehash: 2a62de6c238c1f681bde8a9bf25ecd596a10d390
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917956"
---
# <a name="onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a><span data-ttu-id="3b6ea-103">Incorporar dispositivos de infraestructura de escritorio virtual (VDI) no persistente</span><span class="sxs-lookup"><span data-stu-id="3b6ea-103">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>

<span data-ttu-id="3b6ea-104">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="3b6ea-104">**Applies to:**</span></span>
- [<span data-ttu-id="3b6ea-105">Microsoft 365 Prevención de pérdida de datos de extremo (DLP)</span><span class="sxs-lookup"><span data-stu-id="3b6ea-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](./endpoint-dlp-learn-about.md)

- <span data-ttu-id="3b6ea-106">Dispositivos de infraestructura de escritorio virtual (VDI)</span><span class="sxs-lookup"><span data-stu-id="3b6ea-106">Virtual desktop infrastructure (VDI) devices</span></span>

>[!WARNING]
> <span data-ttu-id="3b6ea-107">Microsoft 365 La compatibilidad de prevención de pérdida de datos de puntos de conexión Windows Escritorio virtual admite escenarios de sesión única.</span><span class="sxs-lookup"><span data-stu-id="3b6ea-107">Microsoft 365 Endpoint data loss prevention support for Windows Virtual Desktop supports single session scenarios.</span></span> <span data-ttu-id="3b6ea-108">Actualmente, no se admiten Windows escenarios de varias sesiones en Escritorio virtual.</span><span class="sxs-lookup"><span data-stu-id="3b6ea-108">Multi-session scenarios on Windows Virtual Desktop are currently not supported.</span></span>

## <a name="onboard-vdi-devices"></a><span data-ttu-id="3b6ea-109">Incorporar dispositivos VDI</span><span class="sxs-lookup"><span data-stu-id="3b6ea-109">Onboard VDI devices</span></span>

<span data-ttu-id="3b6ea-110">Microsoft 365 La prevención de pérdida de datos de extremo admite la incorporación de sesiones VDI no persistentes.</span><span class="sxs-lookup"><span data-stu-id="3b6ea-110">Microsoft 365 Endpoint data loss prevention supports non-persistent VDI session onboarding.</span></span> 

>[!Note]
><span data-ttu-id="3b6ea-111">Para incorporar sesiones VDI no persistentes, los dispositivos VDI deben estar en Windows 10 1809 o posterior.</span><span class="sxs-lookup"><span data-stu-id="3b6ea-111">To onboard non-persistent VDI sessions, VDI devices must be on Windows 10 1809 or higher.</span></span>

<span data-ttu-id="3b6ea-112">Puede haber desafíos asociados al incorporar LOS VDIs.</span><span class="sxs-lookup"><span data-stu-id="3b6ea-112">There might be associated challenges when onboarding VDIs.</span></span> <span data-ttu-id="3b6ea-113">Los siguientes son los desafíos típicos de este escenario:</span><span class="sxs-lookup"><span data-stu-id="3b6ea-113">The following are typical challenges for this scenario:</span></span>

- <span data-ttu-id="3b6ea-114">Incorporación instantánea y anticipada de sesiones de corta duración, que deben incorporarse a Microsoft 365 prevención de pérdida de datos del punto de conexión antes del aprovisionamiento real.</span><span class="sxs-lookup"><span data-stu-id="3b6ea-114">Instant early onboarding of a short-lived sessions, which must be onboarded to  Microsoft 365 Endpoint data loss prevention prior to the actual provisioning.</span></span>
- <span data-ttu-id="3b6ea-115">El nombre del dispositivo normalmente se reutiliza para nuevas sesiones.</span><span class="sxs-lookup"><span data-stu-id="3b6ea-115">The device name is typically reused for new sessions.</span></span>

<span data-ttu-id="3b6ea-116">Los dispositivos VDI pueden aparecer en el centro Microsoft 365 cumplimiento como:</span><span class="sxs-lookup"><span data-stu-id="3b6ea-116">VDI devices can appear in the Microsoft 365 Compliance center as either:</span></span>

- <span data-ttu-id="3b6ea-117">Entrada única para cada dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3b6ea-117">Single entry for each device.</span></span>  
<span data-ttu-id="3b6ea-118">Tenga en cuenta que, en este caso, *debe* configurarse el mismo nombre de dispositivo cuando se crea la sesión, por ejemplo, mediante un archivo de respuesta desatendido.</span><span class="sxs-lookup"><span data-stu-id="3b6ea-118">Note that in this case, the *same* device name must be configured when the session is created, for example using an unattended answer file.</span></span>
- <span data-ttu-id="3b6ea-119">Varias entradas para cada dispositivo: una para cada sesión.</span><span class="sxs-lookup"><span data-stu-id="3b6ea-119">Multiple entries for each device - one for each session.</span></span>

<span data-ttu-id="3b6ea-120">Los siguientes pasos le guiarán a través de la incorporación de dispositivos VDI y resaltarán los pasos para entradas únicas y múltiples.</span><span class="sxs-lookup"><span data-stu-id="3b6ea-120">The following steps will guide you through onboarding VDI devices and will highlight steps for single and multiple entries.</span></span>

>[!WARNING]
> <span data-ttu-id="3b6ea-121">En los entornos en los que hay configuraciones de recursos bajos, el procedimiento de arranque de VDI puede ralentizar la incorporación Microsoft 365 prevención de pérdida de datos del punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="3b6ea-121">For environments where there are low resource configurations, the VDI boot procedure might slow the Microsoft 365 Endpoint data loss prevention onboarding.</span></span> 

1.  <span data-ttu-id="3b6ea-122">Abra el archivo de configuración .zip VDI (*DeviceCompliancePackage.zip*) que descargó del Asistente para incorporación de servicios.</span><span class="sxs-lookup"><span data-stu-id="3b6ea-122">Open the VDI configuration package .zip file (*DeviceCompliancePackage.zip*) that you downloaded from the service onboarding wizard.</span></span>

2.  <span data-ttu-id="3b6ea-123">En el panel de navegación, **seleccione Configuración** Incorporación  >  **de**  >  **dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="3b6ea-123">In the navigation pane, select **Settings** > **Device onboarding** > **Onboarding**.</span></span>

3. <span data-ttu-id="3b6ea-124">En el **campo Método de** implementación, seleccione Scripts de incorporación de VDI para puntos de conexión no **persistentes.**</span><span class="sxs-lookup"><span data-stu-id="3b6ea-124">In the **Deployment method** field, select **VDI onboarding scripts for non-persistent endpoints**.</span></span>

5. <span data-ttu-id="3b6ea-125">Haga **clic en Descargar paquete** y guarde el .zip archivo.</span><span class="sxs-lookup"><span data-stu-id="3b6ea-125">Click **Download package** and save the .zip file.</span></span>

6. <span data-ttu-id="3b6ea-126">Copie los archivos de la carpeta DeviceCompliancePackage extraídos del archivo .zip en la `golden/master` imagen debajo de la ruta de acceso `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` .</span><span class="sxs-lookup"><span data-stu-id="3b6ea-126">Copy the files from the DeviceCompliancePackage folder extracted from the .zip file into the `golden/master` image under the path `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup`.</span></span> 

7. <span data-ttu-id="3b6ea-127">Si no implementa una sola entrada para cada dispositivo, copie DeviceComplianceOnboardingScript.cmd.</span><span class="sxs-lookup"><span data-stu-id="3b6ea-127">If you are not implementing a single entry for each device, copy DeviceComplianceOnboardingScript.cmd.</span></span>

8. <span data-ttu-id="3b6ea-128">Si va a implementar una sola entrada para cada dispositivo, copie tanto Onboard-NonPersistentMachine.ps1 como DeviceComplianceOnboardingScript.cmd.</span><span class="sxs-lookup"><span data-stu-id="3b6ea-128">If you are implementing a single entry for each device, copy both Onboard-NonPersistentMachine.ps1 and DeviceComplianceOnboardingScript.cmd.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="3b6ea-129">Si no ve la `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` carpeta, podría estar oculta.</span><span class="sxs-lookup"><span data-stu-id="3b6ea-129">If you don't see the `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` folder, it might be hidden.</span></span> <span data-ttu-id="3b6ea-130">Tendrás que elegir la opción Mostrar **archivos y carpetas** ocultos en el Explorador de archivos.</span><span class="sxs-lookup"><span data-stu-id="3b6ea-130">You'll need to choose the **Show hidden files and folders** option from File Explorer.</span></span>

9. <span data-ttu-id="3b6ea-131">Abra una ventana Editor de directivas de grupo local y vaya a **Configuración** del  >  **equipo Windows Configuración** inicio de  >    >  **scripts.**</span><span class="sxs-lookup"><span data-stu-id="3b6ea-131">Open a Local Group Policy Editor window and navigate to **Computer Configuration** > **Windows Settings** > **Scripts** > **Startup**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="3b6ea-132">La directiva de grupo de dominio también se puede usar para incorporar dispositivos VDI no persistentes.</span><span class="sxs-lookup"><span data-stu-id="3b6ea-132">Domain Group Policy may also be used for onboarding non-persistent VDI devices.</span></span>

4. <span data-ttu-id="3b6ea-133">Según el método que quiera implementar, siga los pasos correspondientes:</span><span class="sxs-lookup"><span data-stu-id="3b6ea-133">Depending on the method you'd like to implement, follow the appropriate steps:</span></span>

   <span data-ttu-id="3b6ea-134">**Para una sola entrada para cada dispositivo**</span><span class="sxs-lookup"><span data-stu-id="3b6ea-134">**For single entry for each device**</span></span>
   
   <span data-ttu-id="3b6ea-135">Seleccione la **pestaña Scripts de PowerShell** y, a continuación, haga clic en Agregar **(el** Explorador de Windows se abrirá directamente en la ruta de acceso en la que copió el script de incorporación anteriormente).</span><span class="sxs-lookup"><span data-stu-id="3b6ea-135">Select the **PowerShell Scripts** tab, then click **Add** (Windows Explorer will open directly in the path where you copied the onboarding script earlier).</span></span> <span data-ttu-id="3b6ea-136">Navegue a la incorporación del script de PowerShell `Onboard-NonPersistentMachine.ps1` .</span><span class="sxs-lookup"><span data-stu-id="3b6ea-136">Navigate to onboarding PowerShell script `Onboard-NonPersistentMachine.ps1`.</span></span>
   
   <span data-ttu-id="3b6ea-137">**Para varias entradas para cada dispositivo:**</span><span class="sxs-lookup"><span data-stu-id="3b6ea-137">**For multiple entries for each device**:</span></span>
   
   <span data-ttu-id="3b6ea-138">Seleccione la **pestaña Scripts** y, a continuación, haga clic en Agregar **(Windows** Explorer se abrirá directamente en la ruta de acceso en la que copió el script de incorporación anteriormente).</span><span class="sxs-lookup"><span data-stu-id="3b6ea-138">Select the **Scripts** tab, then click **Add** (Windows Explorer will open directly in the path where you copied the onboarding script earlier).</span></span> <span data-ttu-id="3b6ea-139">Vaya al script bash de incorporación `DeviceComplianceOnboardingScript.cmd` .</span><span class="sxs-lookup"><span data-stu-id="3b6ea-139">Navigate to the onboarding bash script `DeviceComplianceOnboardingScript.cmd`.</span></span>

5. <span data-ttu-id="3b6ea-140">Pruebe la solución:</span><span class="sxs-lookup"><span data-stu-id="3b6ea-140">Test your solution:</span></span>

   1. <span data-ttu-id="3b6ea-141">Crea un grupo de servidores con un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3b6ea-141">Create a pool with one device.</span></span>
      
   1. <span data-ttu-id="3b6ea-142">Inicie sesión en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3b6ea-142">Logon to device.</span></span>
      
   1. <span data-ttu-id="3b6ea-143">Cierre sesión desde el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3b6ea-143">Logoff from device.</span></span>

   1. <span data-ttu-id="3b6ea-144">Inicie sesión en el dispositivo con otro usuario.</span><span class="sxs-lookup"><span data-stu-id="3b6ea-144">Logon to device with another user.</span></span>
      
   1. <span data-ttu-id="3b6ea-145">**Para una sola entrada para cada dispositivo:** compruebe solo una entrada en Centro de seguridad de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="3b6ea-145">**For single entry for each device**: Check only one entry in Microsoft Defender Security Center.</span></span><br>
      <span data-ttu-id="3b6ea-146">**Para varias entradas para cada dispositivo:** compruebe varias entradas en Centro de seguridad de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="3b6ea-146">**For multiple entries for each device**: Check multiple entries in Microsoft Defender Security Center.</span></span>

6. <span data-ttu-id="3b6ea-147">Haga **clic en Lista de** dispositivos en el panel de navegación.</span><span class="sxs-lookup"><span data-stu-id="3b6ea-147">Click **Devices list** on the Navigation pane.</span></span>

7. <span data-ttu-id="3b6ea-148">Para usar la función de búsqueda, escriba el nombre del dispositivo y seleccione **Dispositivo** como tipo de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="3b6ea-148">Use the search function by entering the device name and select **Device** as search type.</span></span>

## <a name="updating-non-persistent-virtual-desktop-infrastructure-vdi-images"></a><span data-ttu-id="3b6ea-149">Actualización de imágenes de infraestructura de escritorio virtual (VDI) no persistente</span><span class="sxs-lookup"><span data-stu-id="3b6ea-149">Updating non-persistent virtual desktop infrastructure (VDI) images</span></span>
<span data-ttu-id="3b6ea-150">Como práctica recomendada, se recomienda usar herramientas de mantenimiento sin conexión para aplicar revisiones a imágenes doradas o maestras.</span><span class="sxs-lookup"><span data-stu-id="3b6ea-150">As a best practice, we recommend using offline servicing tools to patch golden/master images.</span></span><br>
<span data-ttu-id="3b6ea-151">Por ejemplo, puede usar los siguientes comandos para instalar una actualización mientras la imagen permanece sin conexión:</span><span class="sxs-lookup"><span data-stu-id="3b6ea-151">For example, you can use the below commands to install an update while the image remains offline:</span></span>

```console
DISM /Mount-image /ImageFile:"D:\Win10-1909.vhdx" /index:1 /MountDir:"C:\Temp\OfflineServicing" 
DISM /Image:"C:\Temp\OfflineServicing" /Add-Package /Packagepath:"C:\temp\patch\windows10.0-kb4541338-x64.msu"
DISM /Unmount-Image /MountDir:"C:\Temp\OfflineServicing" /commit
```

<span data-ttu-id="3b6ea-152">Para obtener más información sobre los comandos DISM y el mantenimiento sin conexión, consulte los artículos siguientes:</span><span class="sxs-lookup"><span data-stu-id="3b6ea-152">For more information on DISM commands and offline servicing, please refer to the articles below:</span></span>
- [<span data-ttu-id="3b6ea-153">Modificar una imagen Windows con DISM</span><span class="sxs-lookup"><span data-stu-id="3b6ea-153">Modify a Windows image using DISM</span></span>](/windows-hardware/manufacture/desktop/mount-and-modify-a-windows-image-using-dism)
- [<span data-ttu-id="3b6ea-154">Opciones de administración de imágenes Command-Line DISM</span><span class="sxs-lookup"><span data-stu-id="3b6ea-154">DISM Image Management Command-Line Options</span></span>](/windows-hardware/manufacture/desktop/dism-image-management-command-line-options-s14)
- [<span data-ttu-id="3b6ea-155">Reducir el tamaño del almacén de componentes en una imagen Windows sin conexión</span><span class="sxs-lookup"><span data-stu-id="3b6ea-155">Reduce the Size of the Component Store in an Offline Windows Image</span></span>](/windows-hardware/manufacture/desktop/reduce-the-size-of-the-component-store-in-an-offline-windows-image)

<span data-ttu-id="3b6ea-156">Si el mantenimiento sin conexión no es una opción viable para el entorno VDI no persistente, se deben seguir los siguientes pasos para garantizar la coherencia y el estado del sensor:</span><span class="sxs-lookup"><span data-stu-id="3b6ea-156">If offline servicing is not a viable option for your non-persistent VDI environment, the following steps should be taken to ensure consistency and sensor health:</span></span>

1. <span data-ttu-id="3b6ea-157">Después de arrancar la imagen maestra para el mantenimiento en línea o la revisión, ejecute un script de offboarding para desactivar el sensor de prevención de pérdida de datos Microsoft 365 endpoint.</span><span class="sxs-lookup"><span data-stu-id="3b6ea-157">After booting the master image for online servicing or patching, run an offboarding script to turn off the Microsoft 365 Endpoint data loss prevention sensor.</span></span> <span data-ttu-id="3b6ea-158">Para obtener más información, vea [Offboard devices using a local script](dlp-configure-endpoints-script.md#offboard-devices-using-a-local-script).</span><span class="sxs-lookup"><span data-stu-id="3b6ea-158">For more information, see [Offboard devices using a local script](dlp-configure-endpoints-script.md#offboard-devices-using-a-local-script).</span></span>

2. <span data-ttu-id="3b6ea-159">Asegúrese de que el sensor está detenido ejecutando el comando siguiente en una ventana cmd:</span><span class="sxs-lookup"><span data-stu-id="3b6ea-159">Ensure the sensor is stopped by running the command below in a CMD window:</span></span>

   ```console
   sc query sense
   ```

3. <span data-ttu-id="3b6ea-160">Servicio de la imagen según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="3b6ea-160">Service the image as needed.</span></span>

4. <span data-ttu-id="3b6ea-161">Ejecute los siguientes comandos mediante PsExec.exe (que se pueden descargar para limpiar el contenido de la carpeta cibernética que el sensor puede haber acumulado https://download.sysinternals.com/files/PSTools.zip) desde el arranque:</span><span class="sxs-lookup"><span data-stu-id="3b6ea-161">Run the below commands using PsExec.exe (which can be downloaded from https://download.sysinternals.com/files/PSTools.zip) to cleanup the cyber folder contents that the sensor may have accumulated since boot:</span></span>

    ```console
    PsExec.exe -s cmd.exe
    cd "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Cyber"
    del *.* /f /s /q
    REG DELETE “HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection" /v senseGuid /f
    exit
    ```

5. <span data-ttu-id="3b6ea-162">Vuelva a sellar la imagen dorada/maestra como lo haría normalmente.</span><span class="sxs-lookup"><span data-stu-id="3b6ea-162">Re-seal the golden/master image as you normally would.</span></span>

## <a name="related-topics"></a><span data-ttu-id="3b6ea-163">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="3b6ea-163">Related topics</span></span>
- [<span data-ttu-id="3b6ea-164">Incorporación Windows 10 dispositivos con directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="3b6ea-164">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md)
- [<span data-ttu-id="3b6ea-165">Incorporar Windows 10 dispositivos con Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="3b6ea-165">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md)
- [<span data-ttu-id="3b6ea-166">Incorporar dispositivos Windows 10 con herramientas de Administración de dispositivos móviles</span><span class="sxs-lookup"><span data-stu-id="3b6ea-166">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md)
- [<span data-ttu-id="3b6ea-167">Incorporar dispositivos Windows 10 mediante un script local</span><span class="sxs-lookup"><span data-stu-id="3b6ea-167">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md)
- [<span data-ttu-id="3b6ea-168">Solucionar Protección contra amenazas avanzada de Microsoft Defender problemas de incorporación</span><span class="sxs-lookup"><span data-stu-id="3b6ea-168">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)