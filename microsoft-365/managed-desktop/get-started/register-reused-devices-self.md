---
title: Registre dispositivos existentes usted mismo
description: Registrar dispositivos reutilizados que ya puede tener usted mismo para que puedan ser administrados por escritorio administrado de Microsoft
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: c2ba687b38f1de4d2ed09b0bd690e02b43f15f8d
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840520"
---
# <a name="register-existing-devices-yourself"></a><span data-ttu-id="ddfae-103">Registre dispositivos existentes usted mismo</span><span class="sxs-lookup"><span data-stu-id="ddfae-103">Register existing devices yourself</span></span>

>[!NOTE]
><span data-ttu-id="ddfae-104">En este tema se describen los pasos para volver a usar los dispositivos que ya tiene y registrarlos en el Escritorio administrado de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ddfae-104">This topic describes the steps for you to reuse devices you already have and register them in Microsoft Managed Desktop.</span></span> <span data-ttu-id="ddfae-105">Si trabaja con dispositivos nuevos, siga los pasos descritos en Registrar nuevos dispositivos en escritorio administrado [de Microsoft.](register-devices-self.md)</span><span class="sxs-lookup"><span data-stu-id="ddfae-105">If you are working with brand-new devices, follow the steps in [Register new devices in Microsoft Managed Desktop yourself](register-devices-self.md) instead.</span></span>

<span data-ttu-id="ddfae-106">El proceso para partners se documenta en [pasos para que los asociados registren dispositivos.](register-devices-partner.md)</span><span class="sxs-lookup"><span data-stu-id="ddfae-106">The process for Partners is documented in [Steps for Partners to register devices](register-devices-partner.md).</span></span>

<span data-ttu-id="ddfae-107">Escritorio administrado de Microsoft puede funcionar con dispositivos nuevos o puede volver a usar los dispositivos que ya tenga (lo que requerirá que los vuelva a crear una imagen).</span><span class="sxs-lookup"><span data-stu-id="ddfae-107">Microsoft Managed Desktop can work with brand-new devices or you can reuse devices you might already have (which will require that you reimage them).</span></span> <span data-ttu-id="ddfae-108">Puedes registrar dispositivos con escritorio administrado de Microsoft en el portal de Microsoft Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="ddfae-108">You can register devices with Microsoft Managed Desktop in the Microsoft Endpoint Manager portal.</span></span>

## <a name="prepare-to-register-existing-devices"></a><span data-ttu-id="ddfae-109">Prepararse para registrar dispositivos existentes</span><span class="sxs-lookup"><span data-stu-id="ddfae-109">Prepare to register existing devices</span></span>


<span data-ttu-id="ddfae-110">Para registrar dispositivos existentes, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="ddfae-110">To register existing devices, follow these steps:</span></span>

1. [<span data-ttu-id="ddfae-111">Obtener el hash de hardware para cada dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ddfae-111">Obtain the hardware hash for each device.</span></span>](#obtain-the-hardware-hash)
2. [<span data-ttu-id="ddfae-112">Combinar los datos hash</span><span class="sxs-lookup"><span data-stu-id="ddfae-112">Merge the hash data</span></span>](#merge-hash-data)
3. <span data-ttu-id="ddfae-113">[Registre los dispositivos en el Escritorio administrado de Microsoft.](#register-devices-by-using-the-admin-portal)</span><span class="sxs-lookup"><span data-stu-id="ddfae-113">[Register the devices in Microsoft Managed Desktop](#register-devices-by-using-the-admin-portal).</span></span>
4. [<span data-ttu-id="ddfae-114">Compruebe de nuevo que la imagen es correcta.</span><span class="sxs-lookup"><span data-stu-id="ddfae-114">Double-check that the image is correct.</span></span>](#check-the-image)
5. [<span data-ttu-id="ddfae-115">Entregar el dispositivo</span><span class="sxs-lookup"><span data-stu-id="ddfae-115">Deliver the device</span></span>](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a><span data-ttu-id="ddfae-116">Obtener el hash de hardware</span><span class="sxs-lookup"><span data-stu-id="ddfae-116">Obtain the hardware hash</span></span>

<span data-ttu-id="ddfae-117">Escritorio administrado de Microsoft identifica cada dispositivo de forma única haciendo referencia a su hash de hardware.</span><span class="sxs-lookup"><span data-stu-id="ddfae-117">Microsoft Managed Desktop identifies each device uniquely by referencing its hardware hash.</span></span> <span data-ttu-id="ddfae-118">Tienes cuatro opciones para obtener esta información de los dispositivos que ya estás usando:</span><span class="sxs-lookup"><span data-stu-id="ddfae-118">You have four options for getting this information from devices you're already using:</span></span>

- <span data-ttu-id="ddfae-119">Pida a su proveedor oem el archivo de registro de AutoPilot, que incluirá los hash de hardware.</span><span class="sxs-lookup"><span data-stu-id="ddfae-119">Ask your OEM supplier for the AutoPilot registration file, which will include the hardware hashes.</span></span>
- <span data-ttu-id="ddfae-120">Recopilar información en [Microsoft Endpoint Configuration Manager.](#microsoft-endpoint-configuration-manager)</span><span class="sxs-lookup"><span data-stu-id="ddfae-120">Collect information in [Microsoft Endpoint Configuration Manager](#microsoft-endpoint-configuration-manager).</span></span>
- <span data-ttu-id="ddfae-121">Ejecute un Windows PowerShell script (ya sea mediante [Active Directory](#active-directory-powershell-script-method) o [manualmente](#manual-powershell-script-method) en cada dispositivo) y recopile los resultados en un archivo.</span><span class="sxs-lookup"><span data-stu-id="ddfae-121">Run a Windows PowerShell script--either by using [Active Directory](#active-directory-powershell-script-method) or [manually](#manual-powershell-script-method) on each device--and collect the results in a file.</span></span>
- <span data-ttu-id="ddfae-122">Inicie cada dispositivo, pero no complete la experiencia de configuración de Windows, y recopile los [hash en una unidad flash extraíble.](#flash-drive-method)</span><span class="sxs-lookup"><span data-stu-id="ddfae-122">Start each device--but don't complete the Windows setup experience--and [collect the hashes on a removable flash drive](#flash-drive-method).</span></span>

#### <a name="microsoft-endpoint-configuration-manager"></a><span data-ttu-id="ddfae-123">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="ddfae-123">Microsoft Endpoint Configuration Manager</span></span>

<span data-ttu-id="ddfae-124">Puedes usar Microsoft Endpoint Configuration Manager para recopilar los hash de hardware de los dispositivos existentes que quieras registrar con el Escritorio administrado de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ddfae-124">You can use Microsoft Endpoint Configuration Manager to collect the hardware hashes from existing devices that you want to register with Microsoft Managed Desktop.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ddfae-125">Los dispositivos para los que quieras obtener esta información deben ejecutar Windows 10, versión 1703 o posterior.</span><span class="sxs-lookup"><span data-stu-id="ddfae-125">Any devices you want to get this information for must be running Windows 10, version 1703 or later.</span></span> 

<span data-ttu-id="ddfae-126">Si ha cumplido todos estos requisitos previos, está listo para recopilar la información siguiendo estos pasos:</span><span class="sxs-lookup"><span data-stu-id="ddfae-126">If you've met all these prerequisites, you're ready to collect the information by following these steps:</span></span>

1. <span data-ttu-id="ddfae-127">En la consola de Configuration Manager, seleccione **Supervisión.**</span><span class="sxs-lookup"><span data-stu-id="ddfae-127">In the Configuration Manager console, select **Monitoring**.</span></span> 
2. <span data-ttu-id="ddfae-128">En el área de trabajo Supervisión, expanda **el** nodo Informes, **Informes** y seleccione el **nodo Hardware - General.**</span><span class="sxs-lookup"><span data-stu-id="ddfae-128">In the Monitoring workspace, expand the **Reporting** node, expand **Reports**, and select the **Hardware - General** node.</span></span> 
3. <span data-ttu-id="ddfae-129">Ejecuta el informe, **Información de dispositivo de Windows Autopilot** y visualiza los resultados.</span><span class="sxs-lookup"><span data-stu-id="ddfae-129">Run the report, **Windows Autopilot Device Information**, and view the results.</span></span>
4. <span data-ttu-id="ddfae-130">En el visor de informes, seleccione el **icono** Exportar y elija la opción **CSV (delimitada por** comas).</span><span class="sxs-lookup"><span data-stu-id="ddfae-130">In the report viewer, select the **Export** icon, and choose the **CSV (comma-delimited)** option.</span></span>
5. <span data-ttu-id="ddfae-131">Después de guardar el archivo, tendrá que filtrar los resultados solo a los dispositivos que planee registrar con el Escritorio administrado de Microsoft y cargar los datos en el Escritorio administrado de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ddfae-131">After saving the file, you will need to filter results to just those devices you plan to register with Microsoft Managed Desktop and upload the data to Microsoft Managed Desktop.</span></span> <span data-ttu-id="ddfae-132">Abre Microsoft Endpoint Manager  y ve al menú Dispositivos, busca la sección Escritorio administrado de Microsoft y selecciona **Dispositivos.**</span><span class="sxs-lookup"><span data-stu-id="ddfae-132">Open Microsoft Endpoint Manager and navigate to the **Devices** menu, then look for Microsoft Managed Desktop section and select **Devices**.</span></span> <span data-ttu-id="ddfae-133">Selecciona **+ Registrar dispositivos,** que abre un menú desplegable para registrar nuevos dispositivos.</span><span class="sxs-lookup"><span data-stu-id="ddfae-133">Select **+ Register devices**, which opens a fly-in to register new devices.</span></span>


<span data-ttu-id="ddfae-134">Consulta Registrar [dispositivos mediante el Portal de administración](#register-devices-by-using-the-admin-portal) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="ddfae-134">Refer to [Register devices by using the Admin Portal](#register-devices-by-using-the-admin-portal) for more information.</span></span>


#### <a name="active-directory-powershell-script-method"></a><span data-ttu-id="ddfae-135">Método de script de PowerShell de Active Directory</span><span class="sxs-lookup"><span data-stu-id="ddfae-135">Active Directory PowerShell script method</span></span>

<span data-ttu-id="ddfae-136">En un entorno de Active Directory, puede usar el cmdlet de PowerShell para recopilar de forma remota la información de dispositivos en grupos de `Get-WindowsAutoPilotInfo` Active Directory mediante WinRM.</span><span class="sxs-lookup"><span data-stu-id="ddfae-136">In an Active Directory environment, you can use the `Get-WindowsAutoPilotInfo` PowerShell cmdlet to remotely collect the information from devices in Active Directory Groups by using WinRM.</span></span> <span data-ttu-id="ddfae-137">También puede usar el `Get-AD Computer` cmdlet y obtener resultados filtrados para un nombre de modelo de hardware específico incluido en el catálogo.</span><span class="sxs-lookup"><span data-stu-id="ddfae-137">You can also use the `Get-AD Computer` cmdlet and get filtered results for a specific hardware model name included in the catalog.</span></span> <span data-ttu-id="ddfae-138">Antes de continuar, confirme primero estos requisitos previos y, a continuación, siga los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="ddfae-138">Before you proceed, first confirm these prerequisites, and then proceed with the steps:</span></span>

- <span data-ttu-id="ddfae-139">WinRM está habilitado.</span><span class="sxs-lookup"><span data-stu-id="ddfae-139">WinRM is enabled.</span></span>
- <span data-ttu-id="ddfae-140">Los dispositivos que quieres registrar están activos en la red (es decir, no están desconectados ni desactivados).</span><span class="sxs-lookup"><span data-stu-id="ddfae-140">The devices you want to register are active on the network (that is, they are not disconnected or turned off).</span></span>
- <span data-ttu-id="ddfae-141">Asegúrese de que tiene un parámetro de credenciales de dominio que tiene permiso para ejecutarse de forma remota en los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="ddfae-141">Make sure you have a domain credential parameter that has permission to execute remotely on the devices.</span></span>
- <span data-ttu-id="ddfae-142">Asegúrate de que Firewall de Windows permite el acceso a WMI.</span><span class="sxs-lookup"><span data-stu-id="ddfae-142">Make sure that Windows Firewall allows access to WMI.</span></span> <span data-ttu-id="ddfae-143">Para ello, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="ddfae-143">To do that, follow these steps:</span></span>

    1. <span data-ttu-id="ddfae-144">Abra el **panel Windows Defender** control firewall y seleccione Permitir una aplicación o característica a través de **Windows Defender Firewall.**</span><span class="sxs-lookup"><span data-stu-id="ddfae-144">Open the **Windows Defender Firewall** control panel and select **Allow an app or feature through Windows Defender Firewall**.</span></span>
    
    2. <span data-ttu-id="ddfae-145">Busque **Instrumental de administración de Windows (WMI)** en la lista, habilite para Privado y **Público** y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ddfae-145">Find **Windows Management Instrumentation (WMI)** in the list, enable for both **Private and Public**, and then select **OK**.</span></span>

1.  <span data-ttu-id="ddfae-146">Abra un símbolo del sistema de PowerShell con derechos administrativos.</span><span class="sxs-lookup"><span data-stu-id="ddfae-146">Open a PowerShell prompt with administrative rights.</span></span>

2.  <span data-ttu-id="ddfae-147">Ejecute *uno de* estos scripts:</span><span class="sxs-lookup"><span data-stu-id="ddfae-147">Run *either one* of these scripts:</span></span>

    ```powershell
    Install-script -name Get-WindowsAutoPilotInfo 
    #example one – leverage Get-ADComputer to enumerate devices 
    Get-ADComputer -filter * | powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname>
    ```

    ```powershell 
    #example two – target specific devices: 
    Set-ExecutionPolicy powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname> -Name Machine1,Machine2,Machine3
    ```

3. <span data-ttu-id="ddfae-148">Accede a los directorios en los que pueda haber entradas para los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="ddfae-148">Access any directories where there might be entries for the devices.</span></span> <span data-ttu-id="ddfae-149">Quite las entradas de cada dispositivo de *todos los* directorios, incluidos Los Servicios de dominio de Active Directory de Windows Server y Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ddfae-149">Remove entries for each device from *all* directories, including Windows Server Active Directory Domain Services and Azure Active Directory.</span></span> <span data-ttu-id="ddfae-150">Tenga en cuenta que la eliminación puede tardar unas horas en procesarse completamente.</span><span class="sxs-lookup"><span data-stu-id="ddfae-150">Be aware that removal could take a few hours to completely process.</span></span>

4. <span data-ttu-id="ddfae-151">Acceder a los servicios de administración en los que puede haber entradas para los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="ddfae-151">Access management services where there might be entries for the devices.</span></span> <span data-ttu-id="ddfae-152">Quita las entradas de cada dispositivo de todos *los* servicios de administración, incluidos Microsoft Endpoint Configuration Manager, Microsoft Intune y Windows Autopilot.</span><span class="sxs-lookup"><span data-stu-id="ddfae-152">Remove entries for each device from *all* management services, including Microsoft Endpoint Configuration Manager, Microsoft Intune, and Windows Autopilot.</span></span> <span data-ttu-id="ddfae-153">Tenga en cuenta que la eliminación puede tardar unas horas en procesarse completamente.</span><span class="sxs-lookup"><span data-stu-id="ddfae-153">Be aware that removal could take a few hours to completely process.</span></span>

<span data-ttu-id="ddfae-154">Ahora puede continuar con el registro [de dispositivos.](#register-devices-by-using-the-admin-portal)</span><span class="sxs-lookup"><span data-stu-id="ddfae-154">Now you can proceed to [register devices](#register-devices-by-using-the-admin-portal).</span></span>

#### <a name="manual-powershell-script-method"></a><span data-ttu-id="ddfae-155">Método manual de script de PowerShell</span><span class="sxs-lookup"><span data-stu-id="ddfae-155">Manual PowerShell script method</span></span>

1.  <span data-ttu-id="ddfae-156">Abra un símbolo del sistema de PowerShell con derechos administrativos.</span><span class="sxs-lookup"><span data-stu-id="ddfae-156">Open a PowerShell prompt with administrative rights.</span></span>
2.  <span data-ttu-id="ddfae-157">Ejecutar `Install-Script -Name Get-WindowsAutoPilotInfo`</span><span class="sxs-lookup"><span data-stu-id="ddfae-157">Run `Install-Script -Name Get-WindowsAutoPilotInfo`</span></span>
3.  <span data-ttu-id="ddfae-158">Ejecutar `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="ddfae-158">Run `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span></span>
4. [<span data-ttu-id="ddfae-159">Combinar los datos hash.</span><span class="sxs-lookup"><span data-stu-id="ddfae-159">Merge the hash data.</span></span>](#merge-hash-data)

#### <a name="flash-drive-method"></a><span data-ttu-id="ddfae-160">Método de unidad flash</span><span class="sxs-lookup"><span data-stu-id="ddfae-160">Flash drive method</span></span>

1. <span data-ttu-id="ddfae-161">En un dispositivo distinto del que registras, inserta una unidad USB.</span><span class="sxs-lookup"><span data-stu-id="ddfae-161">On a device other than the one you're registering, insert a USB drive.</span></span>
2. <span data-ttu-id="ddfae-162">Abra un símbolo del sistema de PowerShell con derechos administrativos.</span><span class="sxs-lookup"><span data-stu-id="ddfae-162">Open a PowerShell prompt with administrative rights.</span></span>
3. <span data-ttu-id="ddfae-163">Ejecutar `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`</span><span class="sxs-lookup"><span data-stu-id="ddfae-163">Run `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`</span></span>
4. <span data-ttu-id="ddfae-164">Activa el dispositivo que estás registrando, pero *no inicies la experiencia de configuración.*</span><span class="sxs-lookup"><span data-stu-id="ddfae-164">Turn on the device you are registering, but *do not start the setup experience*.</span></span> <span data-ttu-id="ddfae-165">Si inicias accidentalmente la experiencia de configuración, tendrás que restablecer o volver a crear una imagen del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ddfae-165">If you accidentally start the setup experience, you'll have to reset or reimage the device.</span></span>
5. <span data-ttu-id="ddfae-166">Inserta la unidad USB y, a continuación, presiona MAYÚS + F10.</span><span class="sxs-lookup"><span data-stu-id="ddfae-166">Insert the USB drive, and then press SHIFT + F10.</span></span>
6. <span data-ttu-id="ddfae-167">Abra un símbolo del sistema de PowerShell con derechos administrativos y, a continuación, ejecute `cd <pathToUsb>` .</span><span class="sxs-lookup"><span data-stu-id="ddfae-167">Open a PowerShell prompt with administrative rights, and then run `cd <pathToUsb>`.</span></span>
7. <span data-ttu-id="ddfae-168">Ejecutar `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span><span class="sxs-lookup"><span data-stu-id="ddfae-168">Run `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span></span>
8. <span data-ttu-id="ddfae-169">Ejecutar `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="ddfae-169">Run `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span></span>
9. <span data-ttu-id="ddfae-170">Quitar la unidad USB y, a continuación, apagar el dispositivo ejecutando `shutdown -s -t 0`</span><span class="sxs-lookup"><span data-stu-id="ddfae-170">Remove the USB drive, and then shut down the device by running `shutdown -s -t 0`</span></span>
10. [<span data-ttu-id="ddfae-171">Combinar los datos hash.</span><span class="sxs-lookup"><span data-stu-id="ddfae-171">Merge the hash data.</span></span>](#merge-hash-data)

>[!IMPORTANT]
><span data-ttu-id="ddfae-172">No enciendas el dispositivo que estás registrando de nuevo hasta que hayas completado el registro para él.</span><span class="sxs-lookup"><span data-stu-id="ddfae-172">Do not power on the device you are registering again until you've completed registration for it.</span></span> 



### <a name="merge-hash-data"></a><span data-ttu-id="ddfae-173">Combinar datos hash</span><span class="sxs-lookup"><span data-stu-id="ddfae-173">Merge hash data</span></span>

<span data-ttu-id="ddfae-174">Si recopiló los datos hash de hardware mediante los métodos manuales de PowerShell o unidad flash, ahora debe combinar los datos de los archivos CSV en un solo archivo para completar el registro.</span><span class="sxs-lookup"><span data-stu-id="ddfae-174">If you collected the hardware hash data by the manual PowerShell or flash drive methods, you now need to have the data in the CSV files combined into a single file to complete registration.</span></span> <span data-ttu-id="ddfae-175">Este es un script de PowerShell de ejemplo para que sea fácil:</span><span class="sxs-lookup"><span data-stu-id="ddfae-175">Here's a sample PowerShell script to make it easy:</span></span>

```powershell
Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv
```

<span data-ttu-id="ddfae-176">Con los datos hash combinados en un archivo CSV, ahora puede continuar con el [registro de los dispositivos.](#register-devices-by-using-the-admin-portal)</span><span class="sxs-lookup"><span data-stu-id="ddfae-176">With the hash data merged into one CSV file, you can now proceed to [register the devices](#register-devices-by-using-the-admin-portal).</span></span>


#### <a name="register-devices-by-using-the-admin-portal"></a><span data-ttu-id="ddfae-177">Registrar dispositivos mediante el Portal de administración</span><span class="sxs-lookup"><span data-stu-id="ddfae-177">Register devices by using the Admin Portal</span></span>

<span data-ttu-id="ddfae-178">En [Microsoft Endpoint Manager,](https://endpoint.microsoft.com/)selecciona **Dispositivos** en el panel de navegación izquierdo.</span><span class="sxs-lookup"><span data-stu-id="ddfae-178">In [Microsoft Endpoint Manager](https://endpoint.microsoft.com/), select **Devices** in the left navigation pane.</span></span> <span data-ttu-id="ddfae-179">Busque la sección Escritorio administrado de Microsoft del menú y seleccione **Dispositivos.**</span><span class="sxs-lookup"><span data-stu-id="ddfae-179">Look for the Microsoft Managed Desktop section of the menu and select **Devices**.</span></span> <span data-ttu-id="ddfae-180">En el área de trabajo Dispositivos de escritorio administrados de Microsoft, seleccione **+ Registrar** dispositivos, que abre un control remoto para registrar nuevos dispositivos.</span><span class="sxs-lookup"><span data-stu-id="ddfae-180">In the Microsoft Managed Desktop Devices workspace, Select **+ Register devices**, which opens a fly-in to register new devices.</span></span>

<!-- Update with new picture [![Fly-in after selecting Register devices, listing devices with columns for assigned users, serial number, status, last-seen date, and age](../../media/new-registration-ui.png)](../../media/new-registration-ui.png) -->


<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


<span data-ttu-id="ddfae-181">Siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="ddfae-181">Follow these steps:</span></span>

1. <span data-ttu-id="ddfae-182">En **Carga de archivos,** proporcione una ruta de acceso al archivo CSV que creó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="ddfae-182">In **File upload**, provide a path to the CSV file you created previously.</span></span>

1. <span data-ttu-id="ddfae-183">Seleccione **Registrar dispositivos.**</span><span class="sxs-lookup"><span data-stu-id="ddfae-183">Select **Register devices**.</span></span> <span data-ttu-id="ddfae-184">El sistema agregará los dispositivos a la lista de dispositivos en la hoja **Dispositivos,** marcada como **Registro pendiente.**</span><span class="sxs-lookup"><span data-stu-id="ddfae-184">The system will add the devices to your list of devices on the **Devices blade**, marked as **Registration Pending**.</span></span> <span data-ttu-id="ddfae-185">El registro normalmente tarda menos de 10 minutos  y, cuando se realiza correctamente, el dispositivo se mostrará como Listo para el usuario, lo que significa que está listo y esperando a que un usuario empiece a usarlo.</span><span class="sxs-lookup"><span data-stu-id="ddfae-185">Registration typically takes less than 10 minutes, and when successful the device will show as **Ready for user** meaning it's ready and waiting for a user to start using.</span></span>


<span data-ttu-id="ddfae-186">Puedes supervisar el progreso del registro de dispositivos en la página principal.</span><span class="sxs-lookup"><span data-stu-id="ddfae-186">You can monitor the progress of device registration on the main page.</span></span> <span data-ttu-id="ddfae-187">Entre los posibles estados notificados se incluyen:</span><span class="sxs-lookup"><span data-stu-id="ddfae-187">Possible states reported there include:</span></span>

| <span data-ttu-id="ddfae-188">Estado</span><span class="sxs-lookup"><span data-stu-id="ddfae-188">State</span></span> | <span data-ttu-id="ddfae-189">Descripción</span><span class="sxs-lookup"><span data-stu-id="ddfae-189">Description</span></span> |
|---------------|-------------|
| <span data-ttu-id="ddfae-190">Registro pendiente</span><span class="sxs-lookup"><span data-stu-id="ddfae-190">Registration Pending</span></span> | <span data-ttu-id="ddfae-191">El registro aún no se ha realizado.</span><span class="sxs-lookup"><span data-stu-id="ddfae-191">Registration is not done yet.</span></span> <span data-ttu-id="ddfae-192">Vuelva a consultar más tarde.</span><span class="sxs-lookup"><span data-stu-id="ddfae-192">Check back later.</span></span> |
| <span data-ttu-id="ddfae-193">Error de registro</span><span class="sxs-lookup"><span data-stu-id="ddfae-193">Registration failed</span></span> | <span data-ttu-id="ddfae-194">No se pudo completar el registro.</span><span class="sxs-lookup"><span data-stu-id="ddfae-194">Registration could not be completed.</span></span> <span data-ttu-id="ddfae-195">Consulta Solución [de problemas del registro de dispositivos](#troubleshooting-device-registration) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="ddfae-195">Refer to [Troubleshooting device registration](#troubleshooting-device-registration) for more information.</span></span> |
| <span data-ttu-id="ddfae-196">Listo para el usuario</span><span class="sxs-lookup"><span data-stu-id="ddfae-196">Ready for user</span></span> | <span data-ttu-id="ddfae-197">El registro se ha registrado correctamente y el dispositivo ya está listo para entregarse al usuario.</span><span class="sxs-lookup"><span data-stu-id="ddfae-197">Registration succeeded and the device is now ready to be delivered to the user.</span></span> <span data-ttu-id="ddfae-198">Escritorio administrado de Microsoft les guiará a través de la configuración por primera vez, por lo que no es necesario realizar ninguna preparación adicional.</span><span class="sxs-lookup"><span data-stu-id="ddfae-198">Microsoft Managed Desktop will guide them through first-time set-up, so there’s no need for you to do any further preparations.</span></span> |
| <span data-ttu-id="ddfae-199">Activo</span><span class="sxs-lookup"><span data-stu-id="ddfae-199">Active</span></span> | <span data-ttu-id="ddfae-200">El dispositivo se ha entregado al usuario y se ha registrado con el inquilino.</span><span class="sxs-lookup"><span data-stu-id="ddfae-200">The device has been delivered to the user and they have registered with your tenant.</span></span> <span data-ttu-id="ddfae-201">Esto también indica que usan el dispositivo con regularidad.</span><span class="sxs-lookup"><span data-stu-id="ddfae-201">This also indicates that they are regularly using the device.</span></span> |
| <span data-ttu-id="ddfae-202">Inactivo</span><span class="sxs-lookup"><span data-stu-id="ddfae-202">Inactive</span></span> | <span data-ttu-id="ddfae-203">El dispositivo se ha entregado al usuario y se ha registrado con el inquilino.</span><span class="sxs-lookup"><span data-stu-id="ddfae-203">The device has been delivered to the user and they have registered with your tenant.</span></span> <span data-ttu-id="ddfae-204">Sin embargo, no han usado el dispositivo recientemente (en los últimos 7 días).</span><span class="sxs-lookup"><span data-stu-id="ddfae-204">However, they have not used the device recently (in the last 7 days).</span></span>  | 

#### <a name="troubleshooting-device-registration"></a><span data-ttu-id="ddfae-205">Solución de problemas del registro de dispositivos</span><span class="sxs-lookup"><span data-stu-id="ddfae-205">Troubleshooting device registration</span></span>

| <span data-ttu-id="ddfae-206">Mensaje de error</span><span class="sxs-lookup"><span data-stu-id="ddfae-206">Error message</span></span> | <span data-ttu-id="ddfae-207">Detalles</span><span class="sxs-lookup"><span data-stu-id="ddfae-207">Details</span></span> |
|---------------|-------------|
| <span data-ttu-id="ddfae-208">No se encontró el dispositivo</span><span class="sxs-lookup"><span data-stu-id="ddfae-208">Device not found</span></span> | <span data-ttu-id="ddfae-209">No pudimos registrar este dispositivo porque no pudimos encontrar una coincidencia para el fabricante, modelo o número de serie proporcionado.</span><span class="sxs-lookup"><span data-stu-id="ddfae-209">We couldn’t register this device because we could not find a match for the provided manufacturer, model, or serial number.</span></span> <span data-ttu-id="ddfae-210">Confirma estos valores con el proveedor de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="ddfae-210">Confirm these values with your device supplier.</span></span> |
| <span data-ttu-id="ddfae-211">El hash de hardware no es válido</span><span class="sxs-lookup"><span data-stu-id="ddfae-211">Hardware hash not valid</span></span> | <span data-ttu-id="ddfae-212">El hash de hardware que proporcionaste para este dispositivo no tenía el formato correcto.</span><span class="sxs-lookup"><span data-stu-id="ddfae-212">The hardware hash you provided for this device was not formatted correctly.</span></span> <span data-ttu-id="ddfae-213">Vuelva a comprobar el hash de hardware y, a continuación, vuelva a enviar.</span><span class="sxs-lookup"><span data-stu-id="ddfae-213">Double-check the hardware hash and then resubmit.</span></span> |
| <span data-ttu-id="ddfae-214">Dispositivo ya registrado</span><span class="sxs-lookup"><span data-stu-id="ddfae-214">Device already registered</span></span> | <span data-ttu-id="ddfae-215">Este dispositivo ya está registrado en la organización.</span><span class="sxs-lookup"><span data-stu-id="ddfae-215">This device is already registered to your organization.</span></span> <span data-ttu-id="ddfae-216">No es necesario realizar ninguna otra acción.</span><span class="sxs-lookup"><span data-stu-id="ddfae-216">No further action required.</span></span> |
| <span data-ttu-id="ddfae-217">Dispositivo reclamado por otra organización</span><span class="sxs-lookup"><span data-stu-id="ddfae-217">Device claimed by another organization</span></span> | <span data-ttu-id="ddfae-218">Este dispositivo ya ha sido reclamado por otra organización.</span><span class="sxs-lookup"><span data-stu-id="ddfae-218">This device has already been claimed by another organization.</span></span> <span data-ttu-id="ddfae-219">Consulta con el proveedor de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="ddfae-219">Check with your device supplier.</span></span> |
| <span data-ttu-id="ddfae-220">Error inesperado</span><span class="sxs-lookup"><span data-stu-id="ddfae-220">Unexpected error</span></span> | <span data-ttu-id="ddfae-221">No se pudo procesar automáticamente la solicitud.</span><span class="sxs-lookup"><span data-stu-id="ddfae-221">Your request could not be automatically processed.</span></span> <span data-ttu-id="ddfae-222">Póngase en contacto con el soporte técnico y proporcione el id. de solicitud: <requestId></span><span class="sxs-lookup"><span data-stu-id="ddfae-222">Contact Support and provide the Request ID: <requestId></span></span> |

### <a name="check-the-image"></a><span data-ttu-id="ddfae-223">Comprobar la imagen</span><span class="sxs-lookup"><span data-stu-id="ddfae-223">Check the image</span></span>

<span data-ttu-id="ddfae-224">Si el dispositivo procede de un proveedor de partners de Escritorio administrado de Microsoft, la imagen debe ser correcta.</span><span class="sxs-lookup"><span data-stu-id="ddfae-224">If your device has come from a Microsoft Managed Desktop partner supplier, the image should be correct.</span></span>

<span data-ttu-id="ddfae-225">También puedes aplicar la imagen por tu cuenta si lo prefieres.</span><span class="sxs-lookup"><span data-stu-id="ddfae-225">You’re also welcome to apply the image on your own if you prefer.</span></span> <span data-ttu-id="ddfae-226">To get started, contact the Microsoft representative you're working with and they will provide you the location and steps for applying the image.</span><span class="sxs-lookup"><span data-stu-id="ddfae-226">To get started, contact the Microsoft representative you’re working with and they will provide you the location and steps for applying the image.</span></span>

### <a name="deliver-the-device"></a><span data-ttu-id="ddfae-227">Entregar el dispositivo</span><span class="sxs-lookup"><span data-stu-id="ddfae-227">Deliver the device</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ddfae-228">Antes de entregar el dispositivo al usuario, asegúrate de que has obtenido y aplicado las licencias adecuadas [para](../get-ready/prerequisites.md) ese usuario.</span><span class="sxs-lookup"><span data-stu-id="ddfae-228">Before you hand off the device to your user, make sure you have obtained and applied the [appropriate licenses](../get-ready/prerequisites.md) for that user.</span></span>

<span data-ttu-id="ddfae-229">Si se aplican todas las [](get-started-devices.md)licencias, puedes preparar a los usuarios para usar dispositivos y, a continuación, el usuario puede iniciar el dispositivo y continuar con la experiencia de configuración de Windows.</span><span class="sxs-lookup"><span data-stu-id="ddfae-229">If all the licenses are applied, you can [get your users ready to use devices](get-started-devices.md), and then your user can start up the device and proceed through the Windows setup experience.</span></span>









