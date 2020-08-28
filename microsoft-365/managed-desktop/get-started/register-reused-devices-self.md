---
title: Registre dispositivos existentes usted mismo
description: Registrar los dispositivos reutilizados es posible que ya los pueda administrar el escritorio administrado de Microsoft.
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: 51c241c46a4c8745bcae169a1c1d89e5c4393f2f
ms.sourcegitcommit: abf63669daf12993ad3353e4b578f41c8910b20f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2020
ms.locfileid: "47289144"
---
# <a name="register-existing-devices-yourself"></a><span data-ttu-id="2f404-103">Registre dispositivos existentes usted mismo</span><span class="sxs-lookup"><span data-stu-id="2f404-103">Register existing devices yourself</span></span>

>[!NOTE]
><span data-ttu-id="2f404-104">En este tema se describen los pasos necesarios para volver a usar dispositivos que ya tiene y registrarlos en el escritorio administrado de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2f404-104">This topic describes the steps for you to re-use devices you already have and register them in Microsoft Managed Desktop.</span></span> <span data-ttu-id="2f404-105">Si está trabajando con dispositivos nuevos, siga los pasos descritos en [registrar los nuevos dispositivos en el escritorio administrado de Microsoft en](register-devices-self.md) su lugar.</span><span class="sxs-lookup"><span data-stu-id="2f404-105">If you are working with brand-new devices, follow the steps in [Register new devices in Microsoft Managed Desktop yourself](register-devices-self.md) instead.</span></span>

<span data-ttu-id="2f404-106">El proceso para socios se documenta en [pasos para que los partners registren dispositivos](register-devices-partner.md).</span><span class="sxs-lookup"><span data-stu-id="2f404-106">The process for Partners is documented in [Steps for Partners to register devices](register-devices-partner.md).</span></span>

<span data-ttu-id="2f404-107">Microsoft Managed Desktop puede trabajar con dispositivos nuevos o puede volver a usar dispositivos que ya tiene (lo que requerirá que vuelva a crear imágenes).</span><span class="sxs-lookup"><span data-stu-id="2f404-107">Microsoft Managed Desktop can work with brand-new devices or you can re-use devices you might already have (which will require that you re-image them).</span></span> <span data-ttu-id="2f404-108">Puede registrar dispositivos mediante el portal de administración de escritorio administrado de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2f404-108">You can register devices by using the Microsoft Managed Desktop Admin Portal.</span></span>

## <a name="prepare-to-register-existing-devices"></a><span data-ttu-id="2f404-109">Preparar el registro de los dispositivos existentes</span><span class="sxs-lookup"><span data-stu-id="2f404-109">Prepare to register existing devices</span></span>


<span data-ttu-id="2f404-110">Para registrar los dispositivos existentes, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="2f404-110">To register existing devices, follow these steps:</span></span>

1. [<span data-ttu-id="2f404-111">Obtenga el hash de hardware para cada dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2f404-111">Obtain the hardware hash for each device.</span></span>](#obtain-the-hardware-hash)
2. [<span data-ttu-id="2f404-112">Combinar los datos hash</span><span class="sxs-lookup"><span data-stu-id="2f404-112">Merge the hash data</span></span>](#merge-hash-data)
3. <span data-ttu-id="2f404-113">[Registre los dispositivos en el escritorio administrado por Microsoft](#register-devices-by-using-the-admin-portal).</span><span class="sxs-lookup"><span data-stu-id="2f404-113">[Register the devices in Microsoft Managed Desktop](#register-devices-by-using-the-admin-portal).</span></span>
4. [<span data-ttu-id="2f404-114">Compruebe que la imagen es correcta.</span><span class="sxs-lookup"><span data-stu-id="2f404-114">Double-check that the image is correct.</span></span>](#check-the-image)
5. [<span data-ttu-id="2f404-115">Entregar el dispositivo</span><span class="sxs-lookup"><span data-stu-id="2f404-115">Deliver the device</span></span>](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a><span data-ttu-id="2f404-116">Obtener el hash de hardware</span><span class="sxs-lookup"><span data-stu-id="2f404-116">Obtain the hardware hash</span></span>

<span data-ttu-id="2f404-117">Microsoft Managed Desktop identifica cada dispositivo de manera única haciendo referencia a su hash de hardware.</span><span class="sxs-lookup"><span data-stu-id="2f404-117">Microsoft Managed Desktop identifies each device uniquely by referencing its hardware hash.</span></span> <span data-ttu-id="2f404-118">Tiene cuatro opciones para obtener esta información de los dispositivos que ya está usando:</span><span class="sxs-lookup"><span data-stu-id="2f404-118">You have four options for getting this information from devices you're already using:</span></span>

- <span data-ttu-id="2f404-119">Solicite al proveedor de OEM el archivo de registro de AutoPilot, que incluirá los hash de hardware.</span><span class="sxs-lookup"><span data-stu-id="2f404-119">Ask your OEM supplier for the AutoPilot registration file, which will include the hardware hashes.</span></span>
- <span data-ttu-id="2f404-120">Recopilar información en el [Administrador de configuración de Microsoft Endpoint](#microsoft-endpoint-configuration-manager).</span><span class="sxs-lookup"><span data-stu-id="2f404-120">Collect information in [Microsoft Endpoint Configuration Manager](#microsoft-endpoint-configuration-manager).</span></span>
- <span data-ttu-id="2f404-121">Ejecute un script de Windows PowerShell, ya sea mediante [Active](#active-directory-powershell-script-method) Directory o [manualmente](#manual-powershell-script-method) en cada dispositivo, y recopile los resultados en un archivo.</span><span class="sxs-lookup"><span data-stu-id="2f404-121">Run a Windows PowerShell script--either by using [Active Directory](#active-directory-powershell-script-method) or [manually](#manual-powershell-script-method) on each device--and collect the results in a file.</span></span>
- <span data-ttu-id="2f404-122">Inicie cada dispositivo, pero no complete la experiencia del programa de instalación de Windows y [reúna los valores hash en una unidad Flash extraíble](#flash-drive-method).</span><span class="sxs-lookup"><span data-stu-id="2f404-122">Start each device--but don't complete the Windows setup experience--and [collect the hashes on a removable flash drive](#flash-drive-method).</span></span>

#### <a name="microsoft-endpoint-configuration-manager"></a><span data-ttu-id="2f404-123">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="2f404-123">Microsoft Endpoint Configuration Manager</span></span>

<span data-ttu-id="2f404-124">Puede usar el administrador de configuración de Microsoft Endpoint para recopilar los hash de hardware de los dispositivos existentes que desee registrar con el escritorio administrado de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2f404-124">You can use Microsoft Endpoint Configuration Manager to collect the hardware hashes from existing devices that you want to register with Microsoft Managed Desktop.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2f404-125">Los dispositivos para los que quiera obtener esta información deben ejecutar Windows 10, versión 1703 o posterior.</span><span class="sxs-lookup"><span data-stu-id="2f404-125">Any devices you want to get this information for must be running Windows 10, version 1703 or later.</span></span> 

<span data-ttu-id="2f404-126">Si ha cumplido todos estos requisitos previos, estará listo para recopilar la información siguiendo estos pasos:</span><span class="sxs-lookup"><span data-stu-id="2f404-126">If you've met all these prerequisites, you're ready to collect the information by following these steps:</span></span>

1. <span data-ttu-id="2f404-127">En la consola de Configuration Manager, seleccione **supervisión**.</span><span class="sxs-lookup"><span data-stu-id="2f404-127">In the Configuration Manager console, select **Monitoring**.</span></span> 
2. <span data-ttu-id="2f404-128">En el área de trabajo supervisión, expanda el nodo **informes** , expanda **informes**y seleccione el nodo **hardware general** .</span><span class="sxs-lookup"><span data-stu-id="2f404-128">In the Monitoring workspace, expand the **Reporting** node, expand **Reports**, and select the **Hardware - General** node.</span></span> 
3. <span data-ttu-id="2f404-129">Ejecute el informe, la **información del dispositivo de Windows AutoPilot**y vea los resultados.</span><span class="sxs-lookup"><span data-stu-id="2f404-129">Run the report, **Windows Autopilot Device Information**, and view the results.</span></span>
4. <span data-ttu-id="2f404-130">En el visor de informes, seleccione el icono **exportar** y elija la opción **CSV (delimitado por comas)** .</span><span class="sxs-lookup"><span data-stu-id="2f404-130">In the report viewer, select the **Export** icon, and choose the **CSV (comma-delimited)** option.</span></span>
5. <span data-ttu-id="2f404-131">Después de guardar el archivo, tendrá que filtrar los resultados para que solo los dispositivos que va a registrar con el escritorio administrado de Microsoft y cargar los datos en el [portal de administración](https://aka.ms/mmdportal)de escritorio administrado de Microsoft, seleccione **dispositivos** en el panel de navegación izquierdo.</span><span class="sxs-lookup"><span data-stu-id="2f404-131">After saving the file, you will need to filter results to just those devices you plan to register with Microsoft Managed Desktop and upload the data to Microsoft Managed Desktop [Admin Portal](https://aka.ms/mmdportal), select **Devices** in the left navigation pane.</span></span> <span data-ttu-id="2f404-132">Seleccione **+ registrar dispositivos**; se abre el repaso:</span><span class="sxs-lookup"><span data-stu-id="2f404-132">Select **+ Register devices**; the fly-in opens:</span></span>


<span data-ttu-id="2f404-133">Para obtener más información [, consulte registrar dispositivos mediante el portal de administración](#register-devices-by-using-the-admin-portal) .</span><span class="sxs-lookup"><span data-stu-id="2f404-133">Refer to [Register devices by using the Admin Portal](#register-devices-by-using-the-admin-portal) for more information.</span></span>


#### <a name="active-directory-powershell-script-method"></a><span data-ttu-id="2f404-134">Método de script de PowerShell de Active Directory</span><span class="sxs-lookup"><span data-stu-id="2f404-134">Active Directory PowerShell script method</span></span>

<span data-ttu-id="2f404-135">En un entorno de Active Directory, puede usar el `Get-WindowsAutoPilotInfo` cmdlet de PowerShell para recopilar de forma remota la información de los dispositivos de los grupos de Active Directory mediante WinRM.</span><span class="sxs-lookup"><span data-stu-id="2f404-135">In an Active Directory environment, you can use the `Get-WindowsAutoPilotInfo` PowerShell cmdlet to remotely collect the information from devices in Active Directory Groups by using WinRM.</span></span> <span data-ttu-id="2f404-136">También puede usar el `Get-AD Computer` cmdlet y obtener resultados filtrados para los nombres de modelo de hardware específicos incluidos en el catálogo.</span><span class="sxs-lookup"><span data-stu-id="2f404-136">You can also use the `Get-AD Computer` cmdlet and get filtered results for a specific hardware model names included in the catalog.</span></span> <span data-ttu-id="2f404-137">Para ello, primero confirme estos requisitos previos y, a continuación, siga los pasos:</span><span class="sxs-lookup"><span data-stu-id="2f404-137">To do this, first confirm these prerequisites, and then proceed with the steps:</span></span>

- <span data-ttu-id="2f404-138">WinRM está habilitado.</span><span class="sxs-lookup"><span data-stu-id="2f404-138">WinRM is enabled.</span></span>
- <span data-ttu-id="2f404-139">Los dispositivos que desea registrar están activos en la red (es decir, no están desconectados ni desactivados).</span><span class="sxs-lookup"><span data-stu-id="2f404-139">The devices you want to register are active on the network (that is, they are not disconnected or turned off).</span></span>
- <span data-ttu-id="2f404-140">Asegúrese de que tiene un parámetro de credencial de dominio con permiso para ejecutar de forma remota en los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="2f404-140">Make sure you have a domain credential parameter that has permission to execute remotely on the devices.</span></span>
- <span data-ttu-id="2f404-141">Asegúrese de que el Firewall de Windows permite el acceso a WMI.</span><span class="sxs-lookup"><span data-stu-id="2f404-141">Make sure that Windows Firewall allows access to WMI.</span></span> <span data-ttu-id="2f404-142">Para ello, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="2f404-142">To do that, follow these steps:</span></span>

    1. <span data-ttu-id="2f404-143">Abra el panel de control del **firewall de Windows Defender** y seleccione **permitir una aplicación o una característica a través de Firewall de Windows Defender**.</span><span class="sxs-lookup"><span data-stu-id="2f404-143">Open the **Windows Defender Firewall** control panel and select **Allow an app or feature through Windows Defender Firewall**.</span></span>
    
    2. <span data-ttu-id="2f404-144">Buscar **instrumental de administración de Windows (WMI)** en la lista, habilitar para **privado y público**y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="2f404-144">Find **Windows Management Instrumentation (WMI)** in the list, enable for both **Private and Public**, and then select **OK**.</span></span>

1.  <span data-ttu-id="2f404-145">Abra un símbolo del sistema de PowerShell con derechos administrativos.</span><span class="sxs-lookup"><span data-stu-id="2f404-145">Open a PowerShell prompt with administrative rights.</span></span>

2.  <span data-ttu-id="2f404-146">Ejecute *alguno de estos* scripts:</span><span class="sxs-lookup"><span data-stu-id="2f404-146">Run *either one* of these scripts:</span></span>

    ```powershell
    Install-script -name Get-WindowsAutoPilotInfo 
    #example one – leverage Get-ADComputer to enumerate devices 
    Get-ADComputer -filter * | powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname>
    ```

    ```powershell 
    #example two – target specific devices: 
    Set-ExecutionPolicy powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname> -Name Machine1,Machine2,Machine3
    ```

3. <span data-ttu-id="2f404-147">Obtenga acceso a los directorios en los que haya entradas para los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="2f404-147">Access any directories where there might be entries for the devices.</span></span> <span data-ttu-id="2f404-148">Quite las entradas de *todos los dispositivos de todos los* directorios, incluidos los servicios de dominio de Active Directory de Windows Server y Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2f404-148">Remove entries for each device from *all* directories, including Windows Server Active Directory Domain Services and Azure Active Directory.</span></span> <span data-ttu-id="2f404-149">Tenga en cuenta que esta eliminación puede tardar varias horas en procesarse por completo.</span><span class="sxs-lookup"><span data-stu-id="2f404-149">Be aware that this removal could take a few hours to completely process.</span></span>

4. <span data-ttu-id="2f404-150">Acceso a servicios de administración donde es posible que haya entradas para los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="2f404-150">Access management services where there might be entries for the devices.</span></span> <span data-ttu-id="2f404-151">Quite las entradas de *todos los dispositivos de todos los* servicios de administración, incluidos Microsoft Endpoint Configuration Manager, Microsoft Intune y Windows AutoPilot.</span><span class="sxs-lookup"><span data-stu-id="2f404-151">Remove entries for each device from *all* management services, including Microsoft Endpoint Configuration Manager, Microsoft Intune, and Windows Autopilot.</span></span> <span data-ttu-id="2f404-152">Tenga en cuenta que esta eliminación puede tardar varias horas en procesarse por completo.</span><span class="sxs-lookup"><span data-stu-id="2f404-152">Be aware that this removal could take a few hours to completely process.</span></span>

<span data-ttu-id="2f404-153">Ahora puede seguir [registrando dispositivos](#register-devices-by-using-the-admin-portal).</span><span class="sxs-lookup"><span data-stu-id="2f404-153">Now you can proceed to [register devices](#register-devices-by-using-the-admin-portal).</span></span>

#### <a name="manual-powershell-script-method"></a><span data-ttu-id="2f404-154">Método de script de PowerShell manual</span><span class="sxs-lookup"><span data-stu-id="2f404-154">Manual PowerShell script method</span></span>

1.  <span data-ttu-id="2f404-155">Abra un símbolo del sistema de PowerShell con derechos administrativos.</span><span class="sxs-lookup"><span data-stu-id="2f404-155">Open a PowerShell prompt with administrative rights.</span></span>
2.  <span data-ttu-id="2f404-156">Realizar `Install-Script -Name Get-WindowsAutoPilotInfo`</span><span class="sxs-lookup"><span data-stu-id="2f404-156">Run `Install-Script -Name Get-WindowsAutoPilotInfo`</span></span>
3.  <span data-ttu-id="2f404-157">Realizar `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="2f404-157">Run `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span></span>
4. [<span data-ttu-id="2f404-158">Combinar los datos hash.</span><span class="sxs-lookup"><span data-stu-id="2f404-158">Merge the hash data.</span></span>](#merge-hash-data)

#### <a name="flash-drive-method"></a><span data-ttu-id="2f404-159">Método Flash Drive</span><span class="sxs-lookup"><span data-stu-id="2f404-159">Flash drive method</span></span>

1. <span data-ttu-id="2f404-160">Inserte una unidad USB en un dispositivo que no sea el que está registrando.</span><span class="sxs-lookup"><span data-stu-id="2f404-160">On a device other than the one you're registering, insert a USB drive.</span></span>
2. <span data-ttu-id="2f404-161">Abra un símbolo del sistema de PowerShell con derechos administrativos.</span><span class="sxs-lookup"><span data-stu-id="2f404-161">Open a PowerShell prompt with administrative rights.</span></span>
3. <span data-ttu-id="2f404-162">Realizar `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`</span><span class="sxs-lookup"><span data-stu-id="2f404-162">Run `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`</span></span>
4. <span data-ttu-id="2f404-163">Activa el dispositivo que estás registrando, pero *no inicia la experiencia de instalación*.</span><span class="sxs-lookup"><span data-stu-id="2f404-163">Turn on the device you are registering, but *do not start the setup experience*.</span></span> <span data-ttu-id="2f404-164">Si inicia de forma accidental la experiencia del programa de instalación, tendrá que restablecer o volver a crear una imagen del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2f404-164">If you accidentally start the setup experience, you'll have to reset or reimage the device.</span></span>
5. <span data-ttu-id="2f404-165">Inserte la unidad USB y, a continuación, presione Mayús + F10.</span><span class="sxs-lookup"><span data-stu-id="2f404-165">Insert the USB drive, and then press SHIFT + F10.</span></span>
6. <span data-ttu-id="2f404-166">Abra un símbolo del sistema de PowerShell con derechos administrativos y, a continuación, ejecute `cd <pathToUsb>` .</span><span class="sxs-lookup"><span data-stu-id="2f404-166">Open a PowerShell prompt with administrative rights, and then run `cd <pathToUsb>`.</span></span>
7. <span data-ttu-id="2f404-167">Realizar `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span><span class="sxs-lookup"><span data-stu-id="2f404-167">Run `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span></span>
8. <span data-ttu-id="2f404-168">Realizar `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="2f404-168">Run `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span></span>
9. <span data-ttu-id="2f404-169">Quite la unidad USB y, a continuación, apague el dispositivo ejecutando `shutdown -s -t 0`</span><span class="sxs-lookup"><span data-stu-id="2f404-169">Remove the USB drive, and then shut down the device by running `shutdown -s -t 0`</span></span>
10. [<span data-ttu-id="2f404-170">Combinar los datos hash.</span><span class="sxs-lookup"><span data-stu-id="2f404-170">Merge the hash data.</span></span>](#merge-hash-data)

>[!IMPORTANT]
><span data-ttu-id="2f404-171">No encienda el dispositivo de nuevo hasta que haya completado el registro para él.</span><span class="sxs-lookup"><span data-stu-id="2f404-171">Do not power on the device you are registering again until you've completed registration for it.</span></span> 



### <a name="merge-hash-data"></a><span data-ttu-id="2f404-172">Combinar datos hash</span><span class="sxs-lookup"><span data-stu-id="2f404-172">Merge hash data</span></span>

<span data-ttu-id="2f404-173">Si ha recopilado los datos de hash de hardware mediante los métodos manuales de la unidad de disco o de PowerShell, ahora debe tener los datos en los archivos CSV combinados en un único archivo para completar el registro.</span><span class="sxs-lookup"><span data-stu-id="2f404-173">If you collected the hardware hash data by the manual PowerShell or flash drive methods, you now need to have the data in the CSV files combined into a single file to complete registration.</span></span> <span data-ttu-id="2f404-174">Este es un script de PowerShell de ejemplo para facilitar esta tarea:</span><span class="sxs-lookup"><span data-stu-id="2f404-174">Here's a sample PowerShell script to make this easy:</span></span>

```powershell
Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv
```

<span data-ttu-id="2f404-175">Una vez que los datos de hash se combinan en un archivo CSV, ahora puede continuar con [el registro de los dispositivos](#register-devices-by-using-the-admin-portal).</span><span class="sxs-lookup"><span data-stu-id="2f404-175">With the hash data merged into one CSV file, you can now proceed to [register the devices](#register-devices-by-using-the-admin-portal).</span></span>


#### <a name="register-devices-by-using-the-admin-portal"></a><span data-ttu-id="2f404-176">Registrar dispositivos mediante el portal de administración</span><span class="sxs-lookup"><span data-stu-id="2f404-176">Register devices by using the Admin Portal</span></span>

<span data-ttu-id="2f404-177">En el [portal de administración](https://aka.ms/mmdportal)de escritorio administrado de Microsoft, seleccione **dispositivos** en el panel de navegación izquierdo.</span><span class="sxs-lookup"><span data-stu-id="2f404-177">From the Microsoft Managed Desktop [Admin Portal](https://aka.ms/mmdportal), select **Devices** in the left navigation pane.</span></span> <span data-ttu-id="2f404-178">Seleccione **+ registrar dispositivos**; se abre el repaso:</span><span class="sxs-lookup"><span data-stu-id="2f404-178">Select **+ Register devices**; the fly-in opens:</span></span>

<span data-ttu-id="2f404-179">[![Paso a paso después de seleccionar los dispositivos de registro, enumerar los dispositivos con columnas para los usuarios asignados, el número de serie, el estado, la fecha de última visualización y la antigüedad.](../../media/new-registration-ui.png)](../../media/new-registration-ui.png)</span><span class="sxs-lookup"><span data-stu-id="2f404-179">[![Fly-in after selecting Register devices, listing devices with columns for assigned users, serial number, status, last-seen date, and age](../../media/new-registration-ui.png)](../../media/new-registration-ui.png)</span></span>


<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


<span data-ttu-id="2f404-180">Siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="2f404-180">Follow these steps:</span></span>

1. <span data-ttu-id="2f404-181">En **carga de archivos**, especifique una ruta de acceso al archivo CSV que creó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="2f404-181">In **File upload**, provide a path to the CSV file you created previously.</span></span>

1. <span data-ttu-id="2f404-182">Seleccione **registrar dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="2f404-182">Select **Register devices**.</span></span> <span data-ttu-id="2f404-183">El sistema agregará los dispositivos a la lista de dispositivos en la **hoja dispositivos**, marcada como **AutopilotRegistrationRequested**.</span><span class="sxs-lookup"><span data-stu-id="2f404-183">The system will add the devices to your list of devices on the **Devices blade**, marked as **AutopilotRegistrationRequested**.</span></span> <span data-ttu-id="2f404-184">El registro suele tardar menos de 10 minutos y, cuando se ejecuta correctamente, el dispositivo se muestra como **listo para el usuario** significa que está listo y esperando a que un usuario empiece a usar.</span><span class="sxs-lookup"><span data-stu-id="2f404-184">Registration typically takes less than 10 minutes, and when successful the device will show as **Ready for user** meaning it's ready and waiting for a user to start using.</span></span>


<span data-ttu-id="2f404-185">Puede supervisar el progreso del registro de dispositivos en la Página principal de **Microsoft administrada para equipos de escritorio** .</span><span class="sxs-lookup"><span data-stu-id="2f404-185">You can monitor the progress of device registration on the main **Microsoft Managed Desktop - Devices** page.</span></span> <span data-ttu-id="2f404-186">Los posibles Estados que se notifican incluyen:</span><span class="sxs-lookup"><span data-stu-id="2f404-186">Possible states reported there include:</span></span>

| <span data-ttu-id="2f404-187">Estado</span><span class="sxs-lookup"><span data-stu-id="2f404-187">State</span></span> | <span data-ttu-id="2f404-188">Descripción</span><span class="sxs-lookup"><span data-stu-id="2f404-188">Description</span></span> |
|---------------|-------------|
| <span data-ttu-id="2f404-189">AutopilotRegistrationRequested</span><span class="sxs-lookup"><span data-stu-id="2f404-189">AutopilotRegistrationRequested</span></span> | <span data-ttu-id="2f404-190">Aún no se ha realizado el registro.</span><span class="sxs-lookup"><span data-stu-id="2f404-190">Registration is not done yet.</span></span> <span data-ttu-id="2f404-191">Vuelva a comprobarla más tarde.</span><span class="sxs-lookup"><span data-stu-id="2f404-191">Check back later.</span></span> |
| <span data-ttu-id="2f404-192">Error en el registro</span><span class="sxs-lookup"><span data-stu-id="2f404-192">Registration failed</span></span> | <span data-ttu-id="2f404-193">No se pudo completar el registro.</span><span class="sxs-lookup"><span data-stu-id="2f404-193">Registration could not be completed.</span></span> <span data-ttu-id="2f404-194">Consulte [solución de problemas del registro de dispositivos](#troubleshooting-device-registration) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="2f404-194">Refer to [Troubleshooting device registration](#troubleshooting-device-registration) for more information.</span></span> |
| <span data-ttu-id="2f404-195">Listo para el usuario</span><span class="sxs-lookup"><span data-stu-id="2f404-195">Ready for user</span></span> | <span data-ttu-id="2f404-196">El registro se realizó correctamente y el dispositivo ya está listo para entregarse al usuario.</span><span class="sxs-lookup"><span data-stu-id="2f404-196">Registration succeeded and the device is now ready to be delivered to the user.</span></span> <span data-ttu-id="2f404-197">El escritorio administrado de Microsoft los guiará a través de la primera configuración, por lo que no es necesario que realice ninguna preparación adicional.</span><span class="sxs-lookup"><span data-stu-id="2f404-197">Microsoft Managed Desktop will guide them through first time set-up, so there’s no need for you to do any further preparations.</span></span> |
| <span data-ttu-id="2f404-198">Activo</span><span class="sxs-lookup"><span data-stu-id="2f404-198">Active</span></span> | <span data-ttu-id="2f404-199">El dispositivo se entregó al usuario y se registró en su espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="2f404-199">The device has been delivered to the user and they have registered with your tenant.</span></span> <span data-ttu-id="2f404-200">Esto también indica que los usuarios usan el dispositivo con regularidad.</span><span class="sxs-lookup"><span data-stu-id="2f404-200">This also indicates that they are regularly using the device.</span></span> |
| <span data-ttu-id="2f404-201">Inactivo</span><span class="sxs-lookup"><span data-stu-id="2f404-201">Inactive</span></span> | <span data-ttu-id="2f404-202">El dispositivo se entregó al usuario y se registró en su espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="2f404-202">The device has been delivered to the user and they have registered with your tenant.</span></span> <span data-ttu-id="2f404-203">Sin embargo, no han usado el dispositivo recientemente (en los últimos 7 días).</span><span class="sxs-lookup"><span data-stu-id="2f404-203">However, they have not used the device recently (in the last 7 days).</span></span>  | 

#### <a name="troubleshooting-device-registration"></a><span data-ttu-id="2f404-204">Solución de problemas de registro de dispositivos</span><span class="sxs-lookup"><span data-stu-id="2f404-204">Troubleshooting device registration</span></span>

| <span data-ttu-id="2f404-205">Mensaje de error</span><span class="sxs-lookup"><span data-stu-id="2f404-205">Error message</span></span> | <span data-ttu-id="2f404-206">Detalles</span><span class="sxs-lookup"><span data-stu-id="2f404-206">Details</span></span> |
|---------------|-------------|
| <span data-ttu-id="2f404-207">No se encontró el dispositivo</span><span class="sxs-lookup"><span data-stu-id="2f404-207">Device not found</span></span> | <span data-ttu-id="2f404-208">No pudimos registrar este dispositivo porque no encontramos una coincidencia para el fabricante, modelo o número de serie que se ha proporcionado.</span><span class="sxs-lookup"><span data-stu-id="2f404-208">We couldn’t register this device because we could not find a match for the provided manufacturer, model, or serial number.</span></span> <span data-ttu-id="2f404-209">Confirma estos valores con el proveedor del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2f404-209">Confirm these values with your device supplier.</span></span> |
| <span data-ttu-id="2f404-210">Hash de hardware no válido</span><span class="sxs-lookup"><span data-stu-id="2f404-210">Hardware hash not valid</span></span> | <span data-ttu-id="2f404-211">El hash de hardware que ha proporcionado para este dispositivo no tiene el formato correcto.</span><span class="sxs-lookup"><span data-stu-id="2f404-211">The hardware hash you provided for this device was not formatted correctly.</span></span> <span data-ttu-id="2f404-212">Compruebe el hash de hardware y vuelva a enviarlo.</span><span class="sxs-lookup"><span data-stu-id="2f404-212">Double-check the hardware hash and then resubmit.</span></span> |
| <span data-ttu-id="2f404-213">El dispositivo ya está registrado</span><span class="sxs-lookup"><span data-stu-id="2f404-213">Device already registered</span></span> | <span data-ttu-id="2f404-214">Este dispositivo ya está registrado en su organización.</span><span class="sxs-lookup"><span data-stu-id="2f404-214">This device is already registered to your organization.</span></span> <span data-ttu-id="2f404-215">No se requiere ninguna otra acción.</span><span class="sxs-lookup"><span data-stu-id="2f404-215">No further action required.</span></span> |
| <span data-ttu-id="2f404-216">Dispositivo reclamado por otra organización</span><span class="sxs-lookup"><span data-stu-id="2f404-216">Device claimed by another organization</span></span> | <span data-ttu-id="2f404-217">Este dispositivo ya ha sido reclamado por otra organización.</span><span class="sxs-lookup"><span data-stu-id="2f404-217">This device has already been claimed by another organization.</span></span> <span data-ttu-id="2f404-218">Consulta con el proveedor del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2f404-218">Check with your device supplier.</span></span> |
| <span data-ttu-id="2f404-219">Error inesperado</span><span class="sxs-lookup"><span data-stu-id="2f404-219">Unexpected error</span></span> | <span data-ttu-id="2f404-220">La solicitud no se pudo procesar automáticamente.</span><span class="sxs-lookup"><span data-stu-id="2f404-220">Your request could not be automatically processed.</span></span> <span data-ttu-id="2f404-221">Póngase en contacto con el soporte técnico y proporcione el identificador de solicitud: <requestId></span><span class="sxs-lookup"><span data-stu-id="2f404-221">Contact Support and provide the Request ID: <requestId></span></span> |

### <a name="check-the-image"></a><span data-ttu-id="2f404-222">Comprobar la imagen</span><span class="sxs-lookup"><span data-stu-id="2f404-222">Check the image</span></span>

<span data-ttu-id="2f404-223">Si el dispositivo proviene de un proveedor de asociados de escritorio administrado por Microsoft, la imagen debe ser correcta.</span><span class="sxs-lookup"><span data-stu-id="2f404-223">If your device has come from a Microsoft Managed Desktop partner supplier, the image should be correct.</span></span>

<span data-ttu-id="2f404-224">También tiene la bienvenida de aplicar la imagen por su cuenta si lo prefiere.</span><span class="sxs-lookup"><span data-stu-id="2f404-224">You’re also welcome to apply the image on your own if you prefer.</span></span> <span data-ttu-id="2f404-225">Para empezar, póngase en contacto con el representante de Microsoft con el que está trabajando y le proporcionará la ubicación y los pasos para aplicar la imagen.</span><span class="sxs-lookup"><span data-stu-id="2f404-225">To get started, contact the Microsoft representative you’re working with and they will provide you the location and steps for applying the image.</span></span>

### <a name="deliver-the-device"></a><span data-ttu-id="2f404-226">Entregar el dispositivo</span><span class="sxs-lookup"><span data-stu-id="2f404-226">Deliver the device</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2f404-227">Antes de entregar el dispositivo al usuario, asegúrese de que ha obtenido y aplicado las [licencias adecuadas](../get-ready/prerequisites.md) para ese usuario.</span><span class="sxs-lookup"><span data-stu-id="2f404-227">Before you hand off the device to your user, make sure you have obtained and applied the [appropriate licenses](../get-ready/prerequisites.md) for that user.</span></span>

<span data-ttu-id="2f404-228">Si se aplican todas las licencias, puede preparar a los [usuarios para que usen dispositivos](get-started-devices.md)y, a continuación, el usuario puede iniciar el dispositivo y continuar con la experiencia del programa de instalación de Windows.</span><span class="sxs-lookup"><span data-stu-id="2f404-228">If all the licenses are applied, you can [get your users ready to use devices](get-started-devices.md), and then your user can start up the device and proceed through the Windows setup experience.</span></span>









