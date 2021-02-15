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
description: Implemente el paquete de configuración en el dispositivo de infraestructura de escritorio virtual (VDI) para que se incorpore al servicio de prevención de pérdida de datos del punto de conexión de Microsoft 365.
ms.openlocfilehash: ce5ad0ba6af3e18a6f6c53e1860fc47a77c38770
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769511"
---
# <a name="onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a><span data-ttu-id="b6423-103">Incorporar dispositivos de infraestructura de escritorio virtual (VDI) no persistente</span><span class="sxs-lookup"><span data-stu-id="b6423-103">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>

<span data-ttu-id="b6423-104">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="b6423-104">**Applies to:**</span></span>
- [<span data-ttu-id="b6423-105">Prevención de pérdida de datos (DLP) de Punto de conexión de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b6423-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](/microsoft-365/compliance/endpoint-dlp-learn-about)

- <span data-ttu-id="b6423-106">Dispositivos de infraestructura de escritorio virtual (VDI)</span><span class="sxs-lookup"><span data-stu-id="b6423-106">Virtual desktop infrastructure (VDI) devices</span></span>

>[!WARNING]
> <span data-ttu-id="b6423-107">Microsoft 365 Endpoint data loss prevention support for Windows Virtual Desktop supports single session scenarios.</span><span class="sxs-lookup"><span data-stu-id="b6423-107">Microsoft 365 Endpoint data loss prevention support for Windows Virtual Desktop supports single session scenarios.</span></span> <span data-ttu-id="b6423-108">Actualmente no se admiten escenarios de varias sesiones en Windows Virtual Desktop.</span><span class="sxs-lookup"><span data-stu-id="b6423-108">Multi-session scenarios on Windows Virtual Desktop are currently not supported.</span></span>

## <a name="onboard-vdi-devices"></a><span data-ttu-id="b6423-109">Incorporar dispositivos VDI</span><span class="sxs-lookup"><span data-stu-id="b6423-109">Onboard VDI devices</span></span>

<span data-ttu-id="b6423-110">La prevención de pérdida de datos de puntos de conexión de Microsoft 365 admite la incorporación de sesiones de VDI no persistentes.</span><span class="sxs-lookup"><span data-stu-id="b6423-110">Microsoft 365 Endpoint data loss prevention supports non-persistent VDI session onboarding.</span></span> 

>[!Note]
><span data-ttu-id="b6423-111">Para incorporar sesiones de VDI no persistentes, los dispositivos VDI deben estar en Windows 10 1809 o versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="b6423-111">To onboard non-persistent VDI sessions, VDI devices must be on Windows 10 1809 or higher.</span></span>

<span data-ttu-id="b6423-112">Es posible que haya desafíos asociados al incorporar los VDIs.</span><span class="sxs-lookup"><span data-stu-id="b6423-112">There might be associated challenges when onboarding VDIs.</span></span> <span data-ttu-id="b6423-113">Los siguientes son los desafíos típicos para este escenario:</span><span class="sxs-lookup"><span data-stu-id="b6423-113">The following are typical challenges for this scenario:</span></span>

- <span data-ttu-id="b6423-114">Incorporación anticipada instantánea de sesiones de corta duración, que deben incorporarse a la prevención de pérdida de datos del punto de conexión de Microsoft 365 antes del aprovisionamiento real.</span><span class="sxs-lookup"><span data-stu-id="b6423-114">Instant early onboarding of a short-lived sessions, which must be onboarded to  Microsoft 365 Endpoint data loss prevention prior to the actual provisioning.</span></span>
- <span data-ttu-id="b6423-115">El nombre del dispositivo se suele reutilizar para las sesiones nuevas.</span><span class="sxs-lookup"><span data-stu-id="b6423-115">The device name is typically reused for new sessions.</span></span>

<span data-ttu-id="b6423-116">Los dispositivos VDI pueden aparecer en el Centro de cumplimiento de Microsoft 365 como:</span><span class="sxs-lookup"><span data-stu-id="b6423-116">VDI devices can appear in the Microsoft 365 Compliance center as either:</span></span>

- <span data-ttu-id="b6423-117">Entrada única para cada dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b6423-117">Single entry for each device.</span></span>  
<span data-ttu-id="b6423-118">Ten en cuenta que, en este caso, *debe* configurarse el mismo nombre de dispositivo cuando se crea la sesión, por ejemplo, mediante un archivo de respuesta desatendido.</span><span class="sxs-lookup"><span data-stu-id="b6423-118">Note that in this case, the *same* device name must be configured when the session is created, for example using an unattended answer file.</span></span>
- <span data-ttu-id="b6423-119">Varias entradas para cada dispositivo: una para cada sesión.</span><span class="sxs-lookup"><span data-stu-id="b6423-119">Multiple entries for each device - one for each session.</span></span>

<span data-ttu-id="b6423-120">Los siguientes pasos te guiarán a través de la incorporación de dispositivos VDI y resaltarán los pasos para entradas únicas y múltiples.</span><span class="sxs-lookup"><span data-stu-id="b6423-120">The following steps will guide you through onboarding VDI devices and will highlight steps for single and multiple entries.</span></span>

>[!WARNING]
> <span data-ttu-id="b6423-121">Para entornos en los que hay configuraciones de recursos bajos, el procedimiento de arranque de VDI podría ralentizar la incorporación de la prevención de pérdida de datos de Puntos de conexión de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b6423-121">For environments where there are low resource configurations, the VDI boot procedure might slow the Microsoft 365 Endpoint data loss prevention onboarding.</span></span> 

1.  <span data-ttu-id="b6423-122">Abre el archivo .zip del paquete de configuración VDI (*DeviceCompliancePackage.zip*) que descargaste desde el Asistente para la incorporación de servicios.</span><span class="sxs-lookup"><span data-stu-id="b6423-122">Open the VDI configuration package .zip file (*DeviceCompliancePackage.zip*) that you downloaded from the service onboarding wizard.</span></span>

2.  <span data-ttu-id="b6423-123">En el panel de navegación, selecciona **Configuración**  >  **de incorporación de**  >  **dispositivos.**</span><span class="sxs-lookup"><span data-stu-id="b6423-123">In the navigation pane, select **Settings** > **Device onboarding** > **Onboarding**.</span></span>

3. <span data-ttu-id="b6423-124">En el **campo Método de** implementación, seleccione scripts de incorporación de **VDI para extremos no persistentes.**</span><span class="sxs-lookup"><span data-stu-id="b6423-124">In the **Deployment method** field, select **VDI onboarding scripts for non-persistent endpoints**.</span></span>

5. <span data-ttu-id="b6423-125">Haz **clic en Descargar paquete** y guarda el archivo .zip.</span><span class="sxs-lookup"><span data-stu-id="b6423-125">Click **Download package** and save the .zip file.</span></span>

6. <span data-ttu-id="b6423-126">Copie los archivos de la carpeta DeviceCompliancePackage extraídos del archivo .zip en la `golden/master` imagen bajo la ruta de `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` acceso.</span><span class="sxs-lookup"><span data-stu-id="b6423-126">Copy the files from the DeviceCompliancePackage folder extracted from the .zip file into the `golden/master` image under the path `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup`.</span></span> 

7. <span data-ttu-id="b6423-127">Si no vas a implementar una sola entrada para cada dispositivo, copia DeviceComplianceOnboardingScript.cmd.</span><span class="sxs-lookup"><span data-stu-id="b6423-127">If you are not implementing a single entry for each device, copy DeviceComplianceOnboardingScript.cmd.</span></span>

8. <span data-ttu-id="b6423-128">Si vas a implementar una sola entrada para cada dispositivo, copia tanto Onboard-NonPersistentMachine.ps1 como DeviceComplianceOnboardingScript.cmd.</span><span class="sxs-lookup"><span data-stu-id="b6423-128">If you are implementing a single entry for each device, copy both Onboard-NonPersistentMachine.ps1 and DeviceComplianceOnboardingScript.cmd.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b6423-129">Si no ve la `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` carpeta, es posible que esté oculta.</span><span class="sxs-lookup"><span data-stu-id="b6423-129">If you don't see the `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` folder, it might be hidden.</span></span> <span data-ttu-id="b6423-130">Tendrás que elegir la opción Mostrar archivos **y** carpetas ocultos en el Explorador de archivos.</span><span class="sxs-lookup"><span data-stu-id="b6423-130">You'll need to choose the **Show hidden files and folders** option from File Explorer.</span></span>

9. <span data-ttu-id="b6423-131">Abra una ventana del Editor de directivas de grupo local y vaya a Configuración **del** equipo Inicio de scripts  >  **de configuración**  >  **de**  >  **Windows**.</span><span class="sxs-lookup"><span data-stu-id="b6423-131">Open a Local Group Policy Editor window and navigate to **Computer Configuration** > **Windows Settings** > **Scripts** > **Startup**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="b6423-132">La directiva de grupo de dominio también se puede usar para incorporar dispositivos VDI no persistentes.</span><span class="sxs-lookup"><span data-stu-id="b6423-132">Domain Group Policy may also be used for onboarding non-persistent VDI devices.</span></span>

4. <span data-ttu-id="b6423-133">En función del método que quieras implementar, sigue los pasos adecuados:</span><span class="sxs-lookup"><span data-stu-id="b6423-133">Depending on the method you'd like to implement, follow the appropriate steps:</span></span>

   <span data-ttu-id="b6423-134">**Para una sola entrada para cada dispositivo**</span><span class="sxs-lookup"><span data-stu-id="b6423-134">**For single entry for each device**</span></span>
   
   <span data-ttu-id="b6423-135">Selecciona la pestaña Scripts de **PowerShell** y, a continuación, haz clic en Agregar **(el** Explorador de Windows se abrirá directamente en la ruta de acceso donde has copiado el script de incorporación anteriormente).</span><span class="sxs-lookup"><span data-stu-id="b6423-135">Select the **PowerShell Scripts** tab, then click **Add** (Windows Explorer will open directly in the path where you copied the onboarding script earlier).</span></span> <span data-ttu-id="b6423-136">Vaya al script de PowerShell de `Onboard-NonPersistentMachine.ps1` incorporación.</span><span class="sxs-lookup"><span data-stu-id="b6423-136">Navigate to onboarding PowerShell script `Onboard-NonPersistentMachine.ps1`.</span></span>
   
   <span data-ttu-id="b6423-137">**Para varias entradas para cada dispositivo:**</span><span class="sxs-lookup"><span data-stu-id="b6423-137">**For multiple entries for each device**:</span></span>
   
   <span data-ttu-id="b6423-138">Selecciona la **pestaña Scripts** y, a continuación, haz clic en Agregar **(el** Explorador de Windows se abrirá directamente en la ruta de acceso donde has copiado el script de incorporación anteriormente).</span><span class="sxs-lookup"><span data-stu-id="b6423-138">Select the **Scripts** tab, then click **Add** (Windows Explorer will open directly in the path where you copied the onboarding script earlier).</span></span> <span data-ttu-id="b6423-139">Navegue al script bash de `DeviceComplianceOnboardingScript.cmd` incorporación.</span><span class="sxs-lookup"><span data-stu-id="b6423-139">Navigate to the onboarding bash script `DeviceComplianceOnboardingScript.cmd`.</span></span>

5. <span data-ttu-id="b6423-140">Pruebe la solución:</span><span class="sxs-lookup"><span data-stu-id="b6423-140">Test your solution:</span></span>

   1. <span data-ttu-id="b6423-141">Crea un grupo de servidores con un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b6423-141">Create a pool with one device.</span></span>
      
   1. <span data-ttu-id="b6423-142">Inicie sesión en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b6423-142">Logon to device.</span></span>
      
   1. <span data-ttu-id="b6423-143">Cierre la sesión del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b6423-143">Logoff from device.</span></span>

   1. <span data-ttu-id="b6423-144">Inicie sesión en el dispositivo con otro usuario.</span><span class="sxs-lookup"><span data-stu-id="b6423-144">Logon to device with another user.</span></span>
      
   1. <span data-ttu-id="b6423-145">**Para una sola entrada para cada dispositivo:** compruebe solo una entrada en el Centro de seguridad de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="b6423-145">**For single entry for each device**: Check only one entry in Microsoft Defender Security Center.</span></span><br>
      <span data-ttu-id="b6423-146">**Para varias entradas para cada dispositivo:** compruebe varias entradas en el Centro de seguridad de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="b6423-146">**For multiple entries for each device**: Check multiple entries in Microsoft Defender Security Center.</span></span>

6. <span data-ttu-id="b6423-147">Haga **clic en la lista Dispositivos** en el panel de navegación.</span><span class="sxs-lookup"><span data-stu-id="b6423-147">Click **Devices list** on the Navigation pane.</span></span>

7. <span data-ttu-id="b6423-148">Para usar la función de búsqueda, escribe el nombre del dispositivo y selecciona **Dispositivo** como tipo de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="b6423-148">Use the search function by entering the device name and select **Device** as search type.</span></span>

## <a name="updating-non-persistent-virtual-desktop-infrastructure-vdi-images"></a><span data-ttu-id="b6423-149">Actualización de imágenes de infraestructura de escritorio virtual (VDI) no persistente</span><span class="sxs-lookup"><span data-stu-id="b6423-149">Updating non-persistent virtual desktop infrastructure (VDI) images</span></span>
<span data-ttu-id="b6423-150">Como procedimiento recomendado, se recomienda usar herramientas de mantenimiento sin conexión para aplicar revisiones a imágenes maestras o de oro.</span><span class="sxs-lookup"><span data-stu-id="b6423-150">As a best practice, we recommend using offline servicing tools to patch golden/master images.</span></span><br>
<span data-ttu-id="b6423-151">Por ejemplo, puedes usar los siguientes comandos para instalar una actualización mientras la imagen permanece sin conexión:</span><span class="sxs-lookup"><span data-stu-id="b6423-151">For example, you can use the below commands to install an update while the image remains offline:</span></span>

```console
DISM /Mount-image /ImageFile:"D:\Win10-1909.vhdx" /index:1 /MountDir:"C:\Temp\OfflineServicing" 
DISM /Image:"C:\Temp\OfflineServicing" /Add-Package /Packagepath:"C:\temp\patch\windows10.0-kb4541338-x64.msu"
DISM /Unmount-Image /MountDir:"C:\Temp\OfflineServicing" /commit
```

<span data-ttu-id="b6423-152">Para obtener más información sobre los comandos DISM y el mantenimiento sin conexión, consulta los artículos siguientes:</span><span class="sxs-lookup"><span data-stu-id="b6423-152">For more information on DISM commands and offline servicing, please refer to the articles below:</span></span>
- [<span data-ttu-id="b6423-153">Modificar una imagen de Windows con DISM</span><span class="sxs-lookup"><span data-stu-id="b6423-153">Modify a Windows image using DISM</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/mount-and-modify-a-windows-image-using-dism)
- [<span data-ttu-id="b6423-154">Opciones de administración de imágenes Command-Line DISM</span><span class="sxs-lookup"><span data-stu-id="b6423-154">DISM Image Management Command-Line Options</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/dism-image-management-command-line-options-s14)
- [<span data-ttu-id="b6423-155">Reducir el tamaño del almacén de componentes en una imagen de Windows sin conexión</span><span class="sxs-lookup"><span data-stu-id="b6423-155">Reduce the Size of the Component Store in an Offline Windows Image</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/reduce-the-size-of-the-component-store-in-an-offline-windows-image)

<span data-ttu-id="b6423-156">Si el mantenimiento sin conexión no es una opción viable para el entorno de VDI no persistente, se deben realizar los siguientes pasos para garantizar la coherencia y el estado del sensor:</span><span class="sxs-lookup"><span data-stu-id="b6423-156">If offline servicing is not a viable option for your non-persistent VDI environment, the following steps should be taken to ensure consistency and sensor health:</span></span>

1. <span data-ttu-id="b6423-157">Después de arrancar la imagen maestra para el mantenimiento en línea o la revisión, ejecute un script de descarga para desactivar el sensor de prevención de pérdida de datos del punto de conexión de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b6423-157">After booting the master image for online servicing or patching, run an offboarding script to turn off the Microsoft 365 Endpoint data loss prevention sensor.</span></span> <span data-ttu-id="b6423-158">Para obtener más información, vea [Dispositivos de fuera de la oficina con un script local.](dlp-configure-endpoints-script.md#offboard-devices-using-a-local-script)</span><span class="sxs-lookup"><span data-stu-id="b6423-158">For more information, see [Offboard devices using a local script](dlp-configure-endpoints-script.md#offboard-devices-using-a-local-script).</span></span>

2. <span data-ttu-id="b6423-159">Asegúrate de que el sensor se detiene ejecutando el siguiente comando en una ventana cmd:</span><span class="sxs-lookup"><span data-stu-id="b6423-159">Ensure the sensor is stopped by running the command below in a CMD window:</span></span>

   ```console
   sc query sense
   ```

3. <span data-ttu-id="b6423-160">Servicio de la imagen según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="b6423-160">Service the image as needed.</span></span>

4. <span data-ttu-id="b6423-161">Ejecuta los siguientes comandos con PsExec.exe (que se pueden descargar para limpiar el contenido de la carpeta cibernética que el sensor haya acumulado https://download.sysinternals.com/files/PSTools.zip) desde el arranque:</span><span class="sxs-lookup"><span data-stu-id="b6423-161">Run the below commands using PsExec.exe (which can be downloaded from https://download.sysinternals.com/files/PSTools.zip) to cleanup the cyber folder contents that the sensor may have accumulated since boot:</span></span>

    ```console
    PsExec.exe -s cmd.exe
    cd "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Cyber"
    del *.* /f /s /q
    REG DELETE “HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection" /v senseGuid /f
    exit
    ```

5. <span data-ttu-id="b6423-162">Vuelva a sellar la imagen de patrón o dorado como lo haría normalmente.</span><span class="sxs-lookup"><span data-stu-id="b6423-162">Re-seal the golden/master image as you normally would.</span></span>

## <a name="related-topics"></a><span data-ttu-id="b6423-163">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="b6423-163">Related topics</span></span>
- [<span data-ttu-id="b6423-164">Incorporar dispositivos Windows 10 mediante la directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="b6423-164">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md)
- [<span data-ttu-id="b6423-165">Incorporar dispositivos Windows 10 con Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="b6423-165">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md)
- [<span data-ttu-id="b6423-166">Incorporar dispositivos Windows 10 con herramientas de Administración de dispositivos móviles</span><span class="sxs-lookup"><span data-stu-id="b6423-166">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md)
- [<span data-ttu-id="b6423-167">Incorporar dispositivos Windows 10 mediante un script local</span><span class="sxs-lookup"><span data-stu-id="b6423-167">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md)
- [<span data-ttu-id="b6423-168">Solucionar problemas de incorporación de Protección contra amenazas avanzada de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="b6423-168">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
