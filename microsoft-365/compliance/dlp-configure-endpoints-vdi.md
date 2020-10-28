---
title: Dispositivos de infraestructura de escritorio virtual (VDI) no persistentes incorporados
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
description: Implemente el paquete de configuración en el dispositivo de infraestructura de escritorio virtual (VDI) para que estén integrados en el servicio de prevención de pérdida de datos de extremos de Microsoft 365.
ms.openlocfilehash: ce5ad0ba6af3e18a6f6c53e1860fc47a77c38770
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769511"
---
# <a name="onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a><span data-ttu-id="b9ffb-103">Dispositivos de infraestructura de escritorio virtual (VDI) no persistentes incorporados</span><span class="sxs-lookup"><span data-stu-id="b9ffb-103">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>

<span data-ttu-id="b9ffb-104">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="b9ffb-104">**Applies to:**</span></span>
- [<span data-ttu-id="b9ffb-105">Prevención de pérdida de datos (DLP) de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b9ffb-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](/microsoft-365/compliance/endpoint-dlp-learn-about)

- <span data-ttu-id="b9ffb-106">Dispositivos de infraestructura de escritorio virtual (VDI)</span><span class="sxs-lookup"><span data-stu-id="b9ffb-106">Virtual desktop infrastructure (VDI) devices</span></span>

>[!WARNING]
> <span data-ttu-id="b9ffb-107">La compatibilidad de prevención de pérdida de datos de extremos de Microsoft 365 para el escritorio virtual de Windows admite escenarios de sesión única.</span><span class="sxs-lookup"><span data-stu-id="b9ffb-107">Microsoft 365 Endpoint data loss prevention support for Windows Virtual Desktop supports single session scenarios.</span></span> <span data-ttu-id="b9ffb-108">Actualmente no se admiten escenarios de sesiones múltiples en el escritorio virtual de Windows.</span><span class="sxs-lookup"><span data-stu-id="b9ffb-108">Multi-session scenarios on Windows Virtual Desktop are currently not supported.</span></span>

## <a name="onboard-vdi-devices"></a><span data-ttu-id="b9ffb-109">Dispositivos VDI incorporados</span><span class="sxs-lookup"><span data-stu-id="b9ffb-109">Onboard VDI devices</span></span>

<span data-ttu-id="b9ffb-110">La prevención de pérdida de datos de Microsoft 365 Endpoint admite la incorporación de sesiones de VDI no persistentes.</span><span class="sxs-lookup"><span data-stu-id="b9ffb-110">Microsoft 365 Endpoint data loss prevention supports non-persistent VDI session onboarding.</span></span> 

>[!Note]
><span data-ttu-id="b9ffb-111">Para incorporar sesiones de VDI no persistentes, los dispositivos de VDI deben estar en Windows 10 1809 o versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="b9ffb-111">To onboard non-persistent VDI sessions, VDI devices must be on Windows 10 1809 or higher.</span></span>

<span data-ttu-id="b9ffb-112">Es posible que se produzcan retos asociados al VDIs de la incorporación.</span><span class="sxs-lookup"><span data-stu-id="b9ffb-112">There might be associated challenges when onboarding VDIs.</span></span> <span data-ttu-id="b9ffb-113">Los siguientes son desafíos típicos para este escenario:</span><span class="sxs-lookup"><span data-stu-id="b9ffb-113">The following are typical challenges for this scenario:</span></span>

- <span data-ttu-id="b9ffb-114">Incorporación rápida instantánea de sesiones de corta duración, que deben incorporarse a la prevención de pérdida de datos de Microsoft 365 Endpoint antes del aprovisionamiento real.</span><span class="sxs-lookup"><span data-stu-id="b9ffb-114">Instant early onboarding of a short-lived sessions, which must be onboarded to  Microsoft 365 Endpoint data loss prevention prior to the actual provisioning.</span></span>
- <span data-ttu-id="b9ffb-115">El nombre del dispositivo suele reutilizarse para las sesiones nuevas.</span><span class="sxs-lookup"><span data-stu-id="b9ffb-115">The device name is typically reused for new sessions.</span></span>

<span data-ttu-id="b9ffb-116">Los dispositivos de VDI pueden aparecer en el centro de cumplimiento de Microsoft 365 como:</span><span class="sxs-lookup"><span data-stu-id="b9ffb-116">VDI devices can appear in the Microsoft 365 Compliance center as either:</span></span>

- <span data-ttu-id="b9ffb-117">Entrada única para cada dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b9ffb-117">Single entry for each device.</span></span>  
<span data-ttu-id="b9ffb-118">Tenga en cuenta que, en este caso, el *mismo* nombre de dispositivo debe configurarse cuando se crea la sesión (por ejemplo, mediante un archivo de respuesta de instalación desatendida).</span><span class="sxs-lookup"><span data-stu-id="b9ffb-118">Note that in this case, the *same* device name must be configured when the session is created, for example using an unattended answer file.</span></span>
- <span data-ttu-id="b9ffb-119">Varias entradas para cada dispositivo: uno para cada sesión.</span><span class="sxs-lookup"><span data-stu-id="b9ffb-119">Multiple entries for each device - one for each session.</span></span>

<span data-ttu-id="b9ffb-120">Los siguientes pasos le guiarán por los dispositivos VDI de incorporación y resaltarán los pasos para las entradas únicas y múltiples.</span><span class="sxs-lookup"><span data-stu-id="b9ffb-120">The following steps will guide you through onboarding VDI devices and will highlight steps for single and multiple entries.</span></span>

>[!WARNING]
> <span data-ttu-id="b9ffb-121">Para los entornos en los que hay configuraciones de recursos insuficientes, el procedimiento de arranque de VDI podría ralentizar la incorporación de prevención de pérdida de datos de extremos de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b9ffb-121">For environments where there are low resource configurations, the VDI boot procedure might slow the Microsoft 365 Endpoint data loss prevention onboarding.</span></span> 

1.  <span data-ttu-id="b9ffb-122">Abra el archivo. zip del paquete de configuración de VDI ( *DeviceCompliancePackage.zip* ) que ha descargado desde el Asistente de incorporación de servicios.</span><span class="sxs-lookup"><span data-stu-id="b9ffb-122">Open the VDI configuration package .zip file ( *DeviceCompliancePackage.zip* ) that you downloaded from the service onboarding wizard.</span></span>

2.  <span data-ttu-id="b9ffb-123">En el panel de navegación, seleccione la incorporación de la incorporación de dispositivos de **configuración**  >  **Device onboarding**  >  **Onboarding** .</span><span class="sxs-lookup"><span data-stu-id="b9ffb-123">In the navigation pane, select **Settings** > **Device onboarding** > **Onboarding** .</span></span>

3. <span data-ttu-id="b9ffb-124">En el campo **método de implementación** , seleccione **scripts de incorporación de VDI para los extremos no persistentes** .</span><span class="sxs-lookup"><span data-stu-id="b9ffb-124">In the **Deployment method** field, select **VDI onboarding scripts for non-persistent endpoints** .</span></span>

5. <span data-ttu-id="b9ffb-125">Haga clic en **Descargar paquete** y guarde el archivo. zip.</span><span class="sxs-lookup"><span data-stu-id="b9ffb-125">Click **Download package** and save the .zip file.</span></span>

6. <span data-ttu-id="b9ffb-126">Copie los archivos de la carpeta DeviceCompliancePackage extraídos del archivo. zip en la `golden/master` imagen de la ruta de acceso `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` .</span><span class="sxs-lookup"><span data-stu-id="b9ffb-126">Copy the files from the DeviceCompliancePackage folder extracted from the .zip file into the `golden/master` image under the path `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup`.</span></span> 

7. <span data-ttu-id="b9ffb-127">Si no va a implementar una entrada única para cada dispositivo, copie DeviceComplianceOnboardingScript. cmd.</span><span class="sxs-lookup"><span data-stu-id="b9ffb-127">If you are not implementing a single entry for each device, copy DeviceComplianceOnboardingScript.cmd.</span></span>

8. <span data-ttu-id="b9ffb-128">Si va a implementar una entrada única para cada dispositivo, copie tanto Onboard-NonPersistentMachine.ps1 como DeviceComplianceOnboardingScript. cmd.</span><span class="sxs-lookup"><span data-stu-id="b9ffb-128">If you are implementing a single entry for each device, copy both Onboard-NonPersistentMachine.ps1 and DeviceComplianceOnboardingScript.cmd.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b9ffb-129">Si no ve la `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` carpeta, es posible que esté oculta.</span><span class="sxs-lookup"><span data-stu-id="b9ffb-129">If you don't see the `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` folder, it might be hidden.</span></span> <span data-ttu-id="b9ffb-130">Deberá elegir la opción **Mostrar todos los archivos y carpetas ocultos** en el explorador de archivos.</span><span class="sxs-lookup"><span data-stu-id="b9ffb-130">You'll need to choose the **Show hidden files and folders** option from File Explorer.</span></span>

9. <span data-ttu-id="b9ffb-131">Abra una ventana del editor de directivas de grupo local y desplácese hasta **configuración del equipo**  >  **Windows**  >  **scripts**  >  **Startup** .</span><span class="sxs-lookup"><span data-stu-id="b9ffb-131">Open a Local Group Policy Editor window and navigate to **Computer Configuration** > **Windows Settings** > **Scripts** > **Startup** .</span></span>

   > [!NOTE]
   > <span data-ttu-id="b9ffb-132">La Directiva de grupo de dominio también puede usarse para incorporar dispositivos no persistentes de VDI no persistentes.</span><span class="sxs-lookup"><span data-stu-id="b9ffb-132">Domain Group Policy may also be used for onboarding non-persistent VDI devices.</span></span>

4. <span data-ttu-id="b9ffb-133">Según el método que quiera implementar, siga los pasos apropiados:</span><span class="sxs-lookup"><span data-stu-id="b9ffb-133">Depending on the method you'd like to implement, follow the appropriate steps:</span></span>

   <span data-ttu-id="b9ffb-134">**Para una entrada única para cada dispositivo**</span><span class="sxs-lookup"><span data-stu-id="b9ffb-134">**For single entry for each device**</span></span>
   
   <span data-ttu-id="b9ffb-135">Seleccione la pestaña **scripts de PowerShell** y haga clic en **Agregar** (el explorador de Windows se abrirá directamente en la ruta de acceso donde copió anteriormente el script de incorporación).</span><span class="sxs-lookup"><span data-stu-id="b9ffb-135">Select the **PowerShell Scripts** tab, then click **Add** (Windows Explorer will open directly in the path where you copied the onboarding script earlier).</span></span> <span data-ttu-id="b9ffb-136">Navegue al script de PowerShell de incorporación `Onboard-NonPersistentMachine.ps1` .</span><span class="sxs-lookup"><span data-stu-id="b9ffb-136">Navigate to onboarding PowerShell script `Onboard-NonPersistentMachine.ps1`.</span></span>
   
   <span data-ttu-id="b9ffb-137">**Para varias entradas para cada dispositivo** :</span><span class="sxs-lookup"><span data-stu-id="b9ffb-137">**For multiple entries for each device** :</span></span>
   
   <span data-ttu-id="b9ffb-138">Seleccione la pestaña **scripts** y, a continuación, haga clic en **Agregar** (el explorador de Windows se abrirá directamente en la ruta de acceso donde copió el script de incorporación, anteriormente).</span><span class="sxs-lookup"><span data-stu-id="b9ffb-138">Select the **Scripts** tab, then click **Add** (Windows Explorer will open directly in the path where you copied the onboarding script earlier).</span></span> <span data-ttu-id="b9ffb-139">Navegue hasta el script de la bash de incorporación `DeviceComplianceOnboardingScript.cmd` .</span><span class="sxs-lookup"><span data-stu-id="b9ffb-139">Navigate to the onboarding bash script `DeviceComplianceOnboardingScript.cmd`.</span></span>

5. <span data-ttu-id="b9ffb-140">Pruebe la solución:</span><span class="sxs-lookup"><span data-stu-id="b9ffb-140">Test your solution:</span></span>

   1. <span data-ttu-id="b9ffb-141">Cree un grupo de servidores con un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b9ffb-141">Create a pool with one device.</span></span>
      
   1. <span data-ttu-id="b9ffb-142">Inicie sesión en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b9ffb-142">Logon to device.</span></span>
      
   1. <span data-ttu-id="b9ffb-143">Cierre la sesión del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b9ffb-143">Logoff from device.</span></span>

   1. <span data-ttu-id="b9ffb-144">Inicie sesión en el dispositivo con otro usuario.</span><span class="sxs-lookup"><span data-stu-id="b9ffb-144">Logon to device with another user.</span></span>
      
   1. <span data-ttu-id="b9ffb-145">**Para una entrada única para cada dispositivo** : Compruebe solo una entrada en el centro de seguridad de Microsoft defender.</span><span class="sxs-lookup"><span data-stu-id="b9ffb-145">**For single entry for each device** : Check only one entry in Microsoft Defender Security Center.</span></span><br>
      <span data-ttu-id="b9ffb-146">**Para varias entradas para cada dispositivo** : Compruebe varias entradas en el centro de seguridad de Microsoft defender.</span><span class="sxs-lookup"><span data-stu-id="b9ffb-146">**For multiple entries for each device** : Check multiple entries in Microsoft Defender Security Center.</span></span>

6. <span data-ttu-id="b9ffb-147">Haga clic en **lista de dispositivos** en el panel de navegación.</span><span class="sxs-lookup"><span data-stu-id="b9ffb-147">Click **Devices list** on the Navigation pane.</span></span>

7. <span data-ttu-id="b9ffb-148">Use la función de búsqueda escribiendo el nombre del dispositivo y seleccione **dispositivo** como tipo de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="b9ffb-148">Use the search function by entering the device name and select **Device** as search type.</span></span>

## <a name="updating-non-persistent-virtual-desktop-infrastructure-vdi-images"></a><span data-ttu-id="b9ffb-149">Actualización de imágenes de infraestructura de escritorio virtual (VDI) no persistentes</span><span class="sxs-lookup"><span data-stu-id="b9ffb-149">Updating non-persistent virtual desktop infrastructure (VDI) images</span></span>
<span data-ttu-id="b9ffb-150">Como procedimiento recomendado, se recomienda el uso de herramientas de servicio sin conexión para aplicar revisiones a imágenes maestras o en oro.</span><span class="sxs-lookup"><span data-stu-id="b9ffb-150">As a best practice, we recommend using offline servicing tools to patch golden/master images.</span></span><br>
<span data-ttu-id="b9ffb-151">Por ejemplo, puede usar los comandos siguientes para instalar una actualización mientras la imagen permanece sin conexión:</span><span class="sxs-lookup"><span data-stu-id="b9ffb-151">For example, you can use the below commands to install an update while the image remains offline:</span></span>

```console
DISM /Mount-image /ImageFile:"D:\Win10-1909.vhdx" /index:1 /MountDir:"C:\Temp\OfflineServicing" 
DISM /Image:"C:\Temp\OfflineServicing" /Add-Package /Packagepath:"C:\temp\patch\windows10.0-kb4541338-x64.msu"
DISM /Unmount-Image /MountDir:"C:\Temp\OfflineServicing" /commit
```

<span data-ttu-id="b9ffb-152">Para obtener más información acerca de los comandos de DISM y el servicio sin conexión, consulte los artículos siguientes:</span><span class="sxs-lookup"><span data-stu-id="b9ffb-152">For more information on DISM commands and offline servicing, please refer to the articles below:</span></span>
- [<span data-ttu-id="b9ffb-153">Modificación de una imagen de Windows mediante DISM</span><span class="sxs-lookup"><span data-stu-id="b9ffb-153">Modify a Windows image using DISM</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/mount-and-modify-a-windows-image-using-dism)
- [<span data-ttu-id="b9ffb-154">Opciones de Command-Line de administración de imágenes de DISM</span><span class="sxs-lookup"><span data-stu-id="b9ffb-154">DISM Image Management Command-Line Options</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/dism-image-management-command-line-options-s14)
- [<span data-ttu-id="b9ffb-155">Reducir el tamaño del almacén de componentes en una imagen de Windows sin conexión</span><span class="sxs-lookup"><span data-stu-id="b9ffb-155">Reduce the Size of the Component Store in an Offline Windows Image</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/reduce-the-size-of-the-component-store-in-an-offline-windows-image)

<span data-ttu-id="b9ffb-156">Si el mantenimiento sin conexión no es una opción viable para el entorno de la VDI no persistente, debe seguir estos pasos para garantizar la coherencia y el estado de los sensores:</span><span class="sxs-lookup"><span data-stu-id="b9ffb-156">If offline servicing is not a viable option for your non-persistent VDI environment, the following steps should be taken to ensure consistency and sensor health:</span></span>

1. <span data-ttu-id="b9ffb-157">Después de arrancar la imagen maestra para el servicio en línea o la revisión, ejecute un script de descarga para desactivar el sensor de prevención de pérdida de datos de extremos de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b9ffb-157">After booting the master image for online servicing or patching, run an offboarding script to turn off the Microsoft 365 Endpoint data loss prevention sensor.</span></span> <span data-ttu-id="b9ffb-158">Para obtener más información, vea [desincorpora dispositivos con un script local](dlp-configure-endpoints-script.md#offboard-devices-using-a-local-script).</span><span class="sxs-lookup"><span data-stu-id="b9ffb-158">For more information, see [Offboard devices using a local script](dlp-configure-endpoints-script.md#offboard-devices-using-a-local-script).</span></span>

2. <span data-ttu-id="b9ffb-159">Asegúrese de detener el sensor ejecutando el comando siguiente en una ventana de CMD:</span><span class="sxs-lookup"><span data-stu-id="b9ffb-159">Ensure the sensor is stopped by running the command below in a CMD window:</span></span>

   ```console
   sc query sense
   ```

3. <span data-ttu-id="b9ffb-160">Servicio de la imagen según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="b9ffb-160">Service the image as needed.</span></span>

4. <span data-ttu-id="b9ffb-161">Ejecute los siguientes comandos con PsExec.exe (que se puede descargar de https://download.sysinternals.com/files/PSTools.zip) para limpiar el contenido de la carpeta Cyber que el sensor puede haber acumulado desde el inicio:</span><span class="sxs-lookup"><span data-stu-id="b9ffb-161">Run the below commands using PsExec.exe (which can be downloaded from https://download.sysinternals.com/files/PSTools.zip) to cleanup the cyber folder contents that the sensor may have accumulated since boot:</span></span>

    ```console
    PsExec.exe -s cmd.exe
    cd "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Cyber"
    del *.* /f /s /q
    REG DELETE “HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection" /v senseGuid /f
    exit
    ```

5. <span data-ttu-id="b9ffb-162">Vuelva a sellar la imagen Golden/Master como lo haría normalmente.</span><span class="sxs-lookup"><span data-stu-id="b9ffb-162">Re-seal the golden/master image as you normally would.</span></span>

## <a name="related-topics"></a><span data-ttu-id="b9ffb-163">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="b9ffb-163">Related topics</span></span>
- [<span data-ttu-id="b9ffb-164">Dispositivos de Windows 10 incorporados mediante la Directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="b9ffb-164">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md)
- [<span data-ttu-id="b9ffb-165">Dispositivos con Windows 10 en placa mediante el administrador de configuración de Microsoft Endpoint</span><span class="sxs-lookup"><span data-stu-id="b9ffb-165">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md)
- [<span data-ttu-id="b9ffb-166">Dispositivos de Windows 10 en placa con herramientas de administración de dispositivos móviles</span><span class="sxs-lookup"><span data-stu-id="b9ffb-166">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md)
- [<span data-ttu-id="b9ffb-167">Dispositivos de Windows 10 incorporados que usan un script local</span><span class="sxs-lookup"><span data-stu-id="b9ffb-167">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md)
- [<span data-ttu-id="b9ffb-168">Solucionar problemas de incorporación de la protección contra amenazas avanzada de Microsoft defender</span><span class="sxs-lookup"><span data-stu-id="b9ffb-168">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
