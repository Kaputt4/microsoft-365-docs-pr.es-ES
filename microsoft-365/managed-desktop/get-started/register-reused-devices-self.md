---
title: Registre dispositivos existentes usted mismo
description: Registrar dispositivos reutilizados que quizás ya tenga usted mismo para que puedan ser administrados por Microsoft Managed Desktop
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 1703e4ed4ea0f3306edf6fdf07ab9c97a9266d4f
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445571"
---
# <a name="register-existing-devices-yourself"></a><span data-ttu-id="ce325-104">Registre dispositivos existentes usted mismo</span><span class="sxs-lookup"><span data-stu-id="ce325-104">Register existing devices yourself</span></span>

>[!NOTE]
><span data-ttu-id="ce325-105">En este tema se describen los pasos para volver a usar los dispositivos que ya tiene y registrarlos en Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="ce325-105">This topic describes the steps for you to reuse devices you already have and register them in Microsoft Managed Desktop.</span></span> <span data-ttu-id="ce325-106">Si está trabajando con dispositivos nuevos, siga los pasos descritos en Registrar nuevos dispositivos [en Microsoft Managed Desktop usted mismo.](register-devices-self.md)</span><span class="sxs-lookup"><span data-stu-id="ce325-106">If you are working with brand-new devices, follow the steps in [Register new devices in Microsoft Managed Desktop yourself](register-devices-self.md) instead.</span></span>

<span data-ttu-id="ce325-107">El proceso para partners se documenta en [Pasos para que los partners registren dispositivos.](register-devices-partner.md)</span><span class="sxs-lookup"><span data-stu-id="ce325-107">The process for Partners is documented in [Steps for Partners to register devices](register-devices-partner.md).</span></span>

<span data-ttu-id="ce325-108">Microsoft Managed Desktop puede funcionar con dispositivos nuevos o puede reutilizar los dispositivos que ya tenga (lo que requerirá que los vuelva a crear).</span><span class="sxs-lookup"><span data-stu-id="ce325-108">Microsoft Managed Desktop can work with brand-new devices or you can reuse devices you might already have (which will require that you reimage them).</span></span> <span data-ttu-id="ce325-109">Puede registrar dispositivos con Microsoft Managed Desktop en el portal de Microsoft Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="ce325-109">You can register devices with Microsoft Managed Desktop in the Microsoft Endpoint Manager portal.</span></span>

## <a name="prepare-to-register-existing-devices"></a><span data-ttu-id="ce325-110">Prepararse para registrar dispositivos existentes</span><span class="sxs-lookup"><span data-stu-id="ce325-110">Prepare to register existing devices</span></span>


<span data-ttu-id="ce325-111">Para registrar dispositivos existentes, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="ce325-111">To register existing devices, follow these steps:</span></span>

1. [<span data-ttu-id="ce325-112">Obtener el hash de hardware para cada dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ce325-112">Obtain the hardware hash for each device.</span></span>](#obtain-the-hardware-hash)
2. [<span data-ttu-id="ce325-113">Combinar los datos hash</span><span class="sxs-lookup"><span data-stu-id="ce325-113">Merge the hash data</span></span>](#merge-hash-data)
3. <span data-ttu-id="ce325-114">[Registrar los dispositivos en Microsoft Managed Desktop](#register-devices-by-using-the-admin-portal).</span><span class="sxs-lookup"><span data-stu-id="ce325-114">[Register the devices in Microsoft Managed Desktop](#register-devices-by-using-the-admin-portal).</span></span>
4. [<span data-ttu-id="ce325-115">Compruebe que la imagen es correcta.</span><span class="sxs-lookup"><span data-stu-id="ce325-115">Double-check that the image is correct.</span></span>](#check-the-image)
5. [<span data-ttu-id="ce325-116">Entregar el dispositivo</span><span class="sxs-lookup"><span data-stu-id="ce325-116">Deliver the device</span></span>](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a><span data-ttu-id="ce325-117">Obtener el hash de hardware</span><span class="sxs-lookup"><span data-stu-id="ce325-117">Obtain the hardware hash</span></span>

<span data-ttu-id="ce325-118">Microsoft Managed Desktop identifica cada dispositivo de forma única haciendo referencia a su hash de hardware.</span><span class="sxs-lookup"><span data-stu-id="ce325-118">Microsoft Managed Desktop identifies each device uniquely by referencing its hardware hash.</span></span> <span data-ttu-id="ce325-119">Tienes cuatro opciones para obtener esta información de los dispositivos que ya estás usando:</span><span class="sxs-lookup"><span data-stu-id="ce325-119">You have four options for getting this information from devices you're already using:</span></span>

- <span data-ttu-id="ce325-120">Pida a su proveedor OEM el archivo de registro de AutoPilot, que incluirá los hashes de hardware.</span><span class="sxs-lookup"><span data-stu-id="ce325-120">Ask your OEM supplier for the AutoPilot registration file, which will include the hardware hashes.</span></span>
- <span data-ttu-id="ce325-121">Recopilar información en [Microsoft Endpoint Configuration Manager](#microsoft-endpoint-configuration-manager).</span><span class="sxs-lookup"><span data-stu-id="ce325-121">Collect information in [Microsoft Endpoint Configuration Manager](#microsoft-endpoint-configuration-manager).</span></span>
- <span data-ttu-id="ce325-122">Ejecute un Windows PowerShell script (ya sea mediante [Active Directory](#active-directory-powershell-script-method) o [manualmente](#manual-powershell-script-method) en cada dispositivo) y recopile los resultados en un archivo.</span><span class="sxs-lookup"><span data-stu-id="ce325-122">Run a Windows PowerShell script--either by using [Active Directory](#active-directory-powershell-script-method) or [manually](#manual-powershell-script-method) on each device--and collect the results in a file.</span></span>
- <span data-ttu-id="ce325-123">Inicie cada dispositivo, pero no complete la experiencia de configuración de Windows, y recopile los [hashes en una unidad flash extraíble.](#flash-drive-method)</span><span class="sxs-lookup"><span data-stu-id="ce325-123">Start each device--but don't complete the Windows setup experience--and [collect the hashes on a removable flash drive](#flash-drive-method).</span></span>

#### <a name="microsoft-endpoint-configuration-manager"></a><span data-ttu-id="ce325-124">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="ce325-124">Microsoft Endpoint Configuration Manager</span></span>

<span data-ttu-id="ce325-125">Puede usar Microsoft Endpoint Configuration Manager para recopilar los hashes de hardware de los dispositivos existentes que desea registrar con Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="ce325-125">You can use Microsoft Endpoint Configuration Manager to collect the hardware hashes from existing devices that you want to register with Microsoft Managed Desktop.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ce325-126">Los dispositivos para los que quieras obtener esta información deben ejecutar Windows 10, versión 1703 o posterior.</span><span class="sxs-lookup"><span data-stu-id="ce325-126">Any devices you want to get this information for must be running Windows 10, version 1703 or later.</span></span> 

<span data-ttu-id="ce325-127">Si ha cumplido todos estos requisitos previos, puede recopilar la información siguiendo estos pasos:</span><span class="sxs-lookup"><span data-stu-id="ce325-127">If you've met all these prerequisites, you're ready to collect the information by following these steps:</span></span>

1. <span data-ttu-id="ce325-128">En la consola de Configuration Manager, seleccione **Supervisión**.</span><span class="sxs-lookup"><span data-stu-id="ce325-128">In the Configuration Manager console, select **Monitoring**.</span></span> 
2. <span data-ttu-id="ce325-129">En el área de trabajo Supervisión, expanda el **nodo Informes,** expanda **Informes** y seleccione el **nodo Hardware - General.**</span><span class="sxs-lookup"><span data-stu-id="ce325-129">In the Monitoring workspace, expand the **Reporting** node, expand **Reports**, and select the **Hardware - General** node.</span></span> 
3. <span data-ttu-id="ce325-130">Ejecute el informe, **Windows Autopilot Device Information** y vea los resultados.</span><span class="sxs-lookup"><span data-stu-id="ce325-130">Run the report, **Windows Autopilot Device Information**, and view the results.</span></span>
4. <span data-ttu-id="ce325-131">En el visor de informes, seleccione el **icono** Exportar y elija la opción **CSV (delimitada por** comas).</span><span class="sxs-lookup"><span data-stu-id="ce325-131">In the report viewer, select the **Export** icon, and choose the **CSV (comma-delimited)** option.</span></span>
5. <span data-ttu-id="ce325-132">Después de guardar el archivo, tendrá que filtrar los resultados solo a los dispositivos que tiene previsto registrar con Microsoft Managed Desktop y cargar los datos en Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="ce325-132">After saving the file, you will need to filter results to just those devices you plan to register with Microsoft Managed Desktop and upload the data to Microsoft Managed Desktop.</span></span> <span data-ttu-id="ce325-133">Abra Microsoft Endpoint Manager y vaya al menú **Dispositivos,** busque la sección Escritorio administrado de Microsoft y seleccione **Dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="ce325-133">Open Microsoft Endpoint Manager and navigate to the **Devices** menu, then look for Microsoft Managed Desktop section and select **Devices**.</span></span> <span data-ttu-id="ce325-134">Seleccione **+ Registrar dispositivos**, que abre un fly-in para registrar nuevos dispositivos.</span><span class="sxs-lookup"><span data-stu-id="ce325-134">Select **+ Register devices**, which opens a fly-in to register new devices.</span></span>


<span data-ttu-id="ce325-135">Consulte [Registrar dispositivos mediante el Portal de administración](#register-devices-by-using-the-admin-portal) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="ce325-135">Refer to [Register devices by using the Admin Portal](#register-devices-by-using-the-admin-portal) for more information.</span></span>


#### <a name="active-directory-powershell-script-method"></a><span data-ttu-id="ce325-136">Método de script de PowerShell de Active Directory</span><span class="sxs-lookup"><span data-stu-id="ce325-136">Active Directory PowerShell script method</span></span>

<span data-ttu-id="ce325-137">En un entorno de Active Directory, puede usar el cmdlet de PowerShell para recopilar de forma remota la información de dispositivos en grupos de `Get-WindowsAutoPilotInfo` Active Directory mediante WinRM.</span><span class="sxs-lookup"><span data-stu-id="ce325-137">In an Active Directory environment, you can use the `Get-WindowsAutoPilotInfo` PowerShell cmdlet to remotely collect the information from devices in Active Directory Groups by using WinRM.</span></span> <span data-ttu-id="ce325-138">También puede usar el cmdlet y obtener resultados filtrados para un nombre de modelo de `Get-AD Computer` hardware específico incluido en el catálogo.</span><span class="sxs-lookup"><span data-stu-id="ce325-138">You can also use the `Get-AD Computer` cmdlet and get filtered results for a specific hardware model name included in the catalog.</span></span> <span data-ttu-id="ce325-139">Antes de continuar, confirme primero estos requisitos previos y, a continuación, siga los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="ce325-139">Before you proceed, first confirm these prerequisites, and then proceed with the steps:</span></span>

- <span data-ttu-id="ce325-140">WinRM está habilitado.</span><span class="sxs-lookup"><span data-stu-id="ce325-140">WinRM is enabled.</span></span>
- <span data-ttu-id="ce325-141">Los dispositivos que desea registrar están activos en la red (es decir, no están desconectados ni desactivados).</span><span class="sxs-lookup"><span data-stu-id="ce325-141">The devices you want to register are active on the network (that is, they are not disconnected or turned off).</span></span>
- <span data-ttu-id="ce325-142">Asegúrese de que tiene un parámetro de credenciales de dominio que tiene permiso para ejecutarse de forma remota en los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="ce325-142">Make sure you have a domain credential parameter that has permission to execute remotely on the devices.</span></span>
- <span data-ttu-id="ce325-143">Asegúrate de que Firewall de Windows permite el acceso a WMI.</span><span class="sxs-lookup"><span data-stu-id="ce325-143">Make sure that Windows Firewall allows access to WMI.</span></span> <span data-ttu-id="ce325-144">Para ello, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="ce325-144">To do that, follow these steps:</span></span>

    1. <span data-ttu-id="ce325-145">Abra el **panel Windows Defender** control Firewall y seleccione Permitir una aplicación o característica a través **Windows Defender Firewall**.</span><span class="sxs-lookup"><span data-stu-id="ce325-145">Open the **Windows Defender Firewall** control panel and select **Allow an app or feature through Windows Defender Firewall**.</span></span>
    
    2. <span data-ttu-id="ce325-146">Busque **Instrumental de administración de Windows (WMI)** en la lista, habilite Private y **Public** y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ce325-146">Find **Windows Management Instrumentation (WMI)** in the list, enable for both **Private and Public**, and then select **OK**.</span></span>

1.  <span data-ttu-id="ce325-147">Abra un símbolo del sistema de PowerShell con derechos administrativos.</span><span class="sxs-lookup"><span data-stu-id="ce325-147">Open a PowerShell prompt with administrative rights.</span></span>

2.  <span data-ttu-id="ce325-148">Ejecute *cualquiera de* estos scripts:</span><span class="sxs-lookup"><span data-stu-id="ce325-148">Run *either one* of these scripts:</span></span>

    ```powershell
    Install-script -name Get-WindowsAutoPilotInfo 
    #example one – leverage Get-ADComputer to enumerate devices 
    Get-ADComputer -filter * | powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname>
    ```

    ```powershell 
    #example two – target specific devices: 
    Set-ExecutionPolicy powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname> -Name Machine1,Machine2,Machine3
    ```

3. <span data-ttu-id="ce325-149">Accede a los directorios en los que pueda haber entradas para los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="ce325-149">Access any directories where there might be entries for the devices.</span></span> <span data-ttu-id="ce325-150">Quite las entradas de cada dispositivo de *todos los* directorios, incluidos los Servicios de dominio de Active Directory de Windows Server y Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ce325-150">Remove entries for each device from *all* directories, including Windows Server Active Directory Domain Services and Azure Active Directory.</span></span> <span data-ttu-id="ce325-151">Tenga en cuenta que la eliminación podría tardar unas horas en procesarse por completo.</span><span class="sxs-lookup"><span data-stu-id="ce325-151">Be aware that removal could take a few hours to completely process.</span></span>

4. <span data-ttu-id="ce325-152">Acceder a los servicios de administración en los que puede haber entradas para los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="ce325-152">Access management services where there might be entries for the devices.</span></span> <span data-ttu-id="ce325-153">Quita las entradas de cada dispositivo de todos *los* servicios de administración, incluidos Microsoft Endpoint Configuration Manager, Microsoft Intune y Windows Autopilot.</span><span class="sxs-lookup"><span data-stu-id="ce325-153">Remove entries for each device from *all* management services, including Microsoft Endpoint Configuration Manager, Microsoft Intune, and Windows Autopilot.</span></span> <span data-ttu-id="ce325-154">Tenga en cuenta que la eliminación podría tardar unas horas en procesarse por completo.</span><span class="sxs-lookup"><span data-stu-id="ce325-154">Be aware that removal could take a few hours to completely process.</span></span>

<span data-ttu-id="ce325-155">Ahora puede continuar con el [registro de dispositivos](#register-devices-by-using-the-admin-portal).</span><span class="sxs-lookup"><span data-stu-id="ce325-155">Now you can proceed to [register devices](#register-devices-by-using-the-admin-portal).</span></span>

#### <a name="manual-powershell-script-method"></a><span data-ttu-id="ce325-156">Método de script manual de PowerShell</span><span class="sxs-lookup"><span data-stu-id="ce325-156">Manual PowerShell script method</span></span>

1.  <span data-ttu-id="ce325-157">Abra un símbolo del sistema de PowerShell con derechos administrativos.</span><span class="sxs-lookup"><span data-stu-id="ce325-157">Open a PowerShell prompt with administrative rights.</span></span>
2.  <span data-ttu-id="ce325-158">Ejecutar `Install-Script -Name Get-WindowsAutoPilotInfo`</span><span class="sxs-lookup"><span data-stu-id="ce325-158">Run `Install-Script -Name Get-WindowsAutoPilotInfo`</span></span>
3.  <span data-ttu-id="ce325-159">Ejecutar `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="ce325-159">Run `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span></span>
4. [<span data-ttu-id="ce325-160">Combinar los datos hash.</span><span class="sxs-lookup"><span data-stu-id="ce325-160">Merge the hash data.</span></span>](#merge-hash-data)

#### <a name="flash-drive-method"></a><span data-ttu-id="ce325-161">Método de unidad flash</span><span class="sxs-lookup"><span data-stu-id="ce325-161">Flash drive method</span></span>

1. <span data-ttu-id="ce325-162">En un dispositivo que no sea el que está registrando, inserte una unidad USB.</span><span class="sxs-lookup"><span data-stu-id="ce325-162">On a device other than the one you're registering, insert a USB drive.</span></span>
2. <span data-ttu-id="ce325-163">Abra un símbolo del sistema de PowerShell con derechos administrativos.</span><span class="sxs-lookup"><span data-stu-id="ce325-163">Open a PowerShell prompt with administrative rights.</span></span>
3. <span data-ttu-id="ce325-164">Ejecutar `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`</span><span class="sxs-lookup"><span data-stu-id="ce325-164">Run `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`</span></span>
4. <span data-ttu-id="ce325-165">Activa el dispositivo que estás registrando, pero *no inicies la experiencia de configuración.*</span><span class="sxs-lookup"><span data-stu-id="ce325-165">Turn on the device you are registering, but *do not start the setup experience*.</span></span> <span data-ttu-id="ce325-166">Si inicias accidentalmente la experiencia de configuración, tendrás que restablecer o volver a crear una imagen del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ce325-166">If you accidentally start the setup experience, you'll have to reset or reimage the device.</span></span>
5. <span data-ttu-id="ce325-167">Inserte la unidad USB y, a continuación, presione MAYÚS + F10.</span><span class="sxs-lookup"><span data-stu-id="ce325-167">Insert the USB drive, and then press SHIFT + F10.</span></span>
6. <span data-ttu-id="ce325-168">Abra un símbolo del sistema de PowerShell con derechos administrativos y, a continuación, ejecute `cd <pathToUsb>` .</span><span class="sxs-lookup"><span data-stu-id="ce325-168">Open a PowerShell prompt with administrative rights, and then run `cd <pathToUsb>`.</span></span>
7. <span data-ttu-id="ce325-169">Ejecutar `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span><span class="sxs-lookup"><span data-stu-id="ce325-169">Run `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span></span>
8. <span data-ttu-id="ce325-170">Ejecutar `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="ce325-170">Run `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span></span>
9. <span data-ttu-id="ce325-171">Quitar la unidad USB y, a continuación, apagar el dispositivo ejecutando `shutdown -s -t 0`</span><span class="sxs-lookup"><span data-stu-id="ce325-171">Remove the USB drive, and then shut down the device by running `shutdown -s -t 0`</span></span>
10. [<span data-ttu-id="ce325-172">Combinar los datos hash.</span><span class="sxs-lookup"><span data-stu-id="ce325-172">Merge the hash data.</span></span>](#merge-hash-data)

>[!IMPORTANT]
><span data-ttu-id="ce325-173">No enciendas el dispositivo que estás registrando de nuevo hasta que hayas completado el registro para él.</span><span class="sxs-lookup"><span data-stu-id="ce325-173">Do not power on the device you are registering again until you've completed registration for it.</span></span> 



### <a name="merge-hash-data"></a><span data-ttu-id="ce325-174">Combinar datos hash</span><span class="sxs-lookup"><span data-stu-id="ce325-174">Merge hash data</span></span>

<span data-ttu-id="ce325-175">Si recopiló los datos de hash de hardware mediante los métodos manuales de PowerShell o unidad flash, ahora debe combinar los datos de los archivos CSV en un solo archivo para completar el registro.</span><span class="sxs-lookup"><span data-stu-id="ce325-175">If you collected the hardware hash data by the manual PowerShell or flash drive methods, you now need to have the data in the CSV files combined into a single file to complete registration.</span></span> <span data-ttu-id="ce325-176">Este es un script de PowerShell de ejemplo para que sea fácil:</span><span class="sxs-lookup"><span data-stu-id="ce325-176">Here's a sample PowerShell script to make it easy:</span></span>

```powershell
Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv
```

<span data-ttu-id="ce325-177">Con los datos hash combinados en un archivo CSV, ahora puede continuar con [el registro de los dispositivos](#register-devices-by-using-the-admin-portal).</span><span class="sxs-lookup"><span data-stu-id="ce325-177">With the hash data merged into one CSV file, you can now proceed to [register the devices](#register-devices-by-using-the-admin-portal).</span></span>


#### <a name="register-devices-by-using-the-admin-portal"></a><span data-ttu-id="ce325-178">Registrar dispositivos mediante el Portal de administración</span><span class="sxs-lookup"><span data-stu-id="ce325-178">Register devices by using the Admin Portal</span></span>

<span data-ttu-id="ce325-179">En [Microsoft Endpoint Manager,](https://endpoint.microsoft.com/)seleccione **Dispositivos** en el panel de navegación izquierdo.</span><span class="sxs-lookup"><span data-stu-id="ce325-179">In [Microsoft Endpoint Manager](https://endpoint.microsoft.com/), select **Devices** in the left navigation pane.</span></span> <span data-ttu-id="ce325-180">Busque la sección Escritorio administrado de Microsoft del menú y seleccione **Dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="ce325-180">Look for the Microsoft Managed Desktop section of the menu and select **Devices**.</span></span> <span data-ttu-id="ce325-181">En el área de trabajo Dispositivos de escritorio administrados de Microsoft, seleccione **+ Registrar** dispositivos, que abre un control remoto para registrar nuevos dispositivos.</span><span class="sxs-lookup"><span data-stu-id="ce325-181">In the Microsoft Managed Desktop Devices workspace, Select **+ Register devices**, which opens a fly-in to register new devices.</span></span>

<!-- Update with new picture [![Fly-in after selecting Register devices, listing devices with columns for assigned users, serial number, status, last-seen date, and age](../../media/new-registration-ui.png)](../../media/new-registration-ui.png) -->


<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


<span data-ttu-id="ce325-182">Siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="ce325-182">Follow these steps:</span></span>

1. <span data-ttu-id="ce325-183">En **Carga de archivos,** proporcione una ruta de acceso al archivo CSV que creó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="ce325-183">In **File upload**, provide a path to the CSV file you created previously.</span></span>

1. <span data-ttu-id="ce325-184">Seleccione **Registrar dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="ce325-184">Select **Register devices**.</span></span> <span data-ttu-id="ce325-185">El sistema agregará los dispositivos a la lista de dispositivos de la hoja **Dispositivos,** marcados como **Registro pendiente.**</span><span class="sxs-lookup"><span data-stu-id="ce325-185">The system will add the devices to your list of devices on the **Devices blade**, marked as **Registration Pending**.</span></span> <span data-ttu-id="ce325-186">El registro suele demorar menos de 10 minutos  y, cuando se realiza correctamente, el dispositivo se muestra como Listo para el usuario, lo que significa que está listo y a la espera de que un usuario empiece a usarlo.</span><span class="sxs-lookup"><span data-stu-id="ce325-186">Registration typically takes less than 10 minutes, and when successful the device will show as **Ready for user** meaning it's ready and waiting for a user to start using.</span></span>


<span data-ttu-id="ce325-187">Puedes supervisar el progreso del registro del dispositivo en la página principal.</span><span class="sxs-lookup"><span data-stu-id="ce325-187">You can monitor the progress of device registration on the main page.</span></span> <span data-ttu-id="ce325-188">Entre los posibles estados notificados se incluyen:</span><span class="sxs-lookup"><span data-stu-id="ce325-188">Possible states reported there include:</span></span>

| <span data-ttu-id="ce325-189">Estado</span><span class="sxs-lookup"><span data-stu-id="ce325-189">State</span></span> | <span data-ttu-id="ce325-190">Descripción</span><span class="sxs-lookup"><span data-stu-id="ce325-190">Description</span></span> |
|---------------|-------------|
| <span data-ttu-id="ce325-191">Registro pendiente</span><span class="sxs-lookup"><span data-stu-id="ce325-191">Registration Pending</span></span> | <span data-ttu-id="ce325-192">El registro aún no se ha realizado.</span><span class="sxs-lookup"><span data-stu-id="ce325-192">Registration is not done yet.</span></span> <span data-ttu-id="ce325-193">Vuelva más tarde.</span><span class="sxs-lookup"><span data-stu-id="ce325-193">Check back later.</span></span> |
| <span data-ttu-id="ce325-194">Error de registro</span><span class="sxs-lookup"><span data-stu-id="ce325-194">Registration failed</span></span> | <span data-ttu-id="ce325-195">No se pudo completar el registro.</span><span class="sxs-lookup"><span data-stu-id="ce325-195">Registration could not be completed.</span></span> <span data-ttu-id="ce325-196">Consulte [Troubleshooting device registration para](#troubleshooting-device-registration) obtener más información.</span><span class="sxs-lookup"><span data-stu-id="ce325-196">Refer to [Troubleshooting device registration](#troubleshooting-device-registration) for more information.</span></span> |
| <span data-ttu-id="ce325-197">Listo para el usuario</span><span class="sxs-lookup"><span data-stu-id="ce325-197">Ready for user</span></span> | <span data-ttu-id="ce325-198">El registro se ha registrado correctamente y el dispositivo ya está listo para entregarse al usuario.</span><span class="sxs-lookup"><span data-stu-id="ce325-198">Registration succeeded and the device is now ready to be delivered to the user.</span></span> <span data-ttu-id="ce325-199">El Escritorio administrado de Microsoft los guiará a través de la configuración por primera vez, por lo que no es necesario realizar ninguna preparación adicional.</span><span class="sxs-lookup"><span data-stu-id="ce325-199">Microsoft Managed Desktop will guide them through first-time set-up, so there’s no need for you to do any further preparations.</span></span> |
| <span data-ttu-id="ce325-200">Activo</span><span class="sxs-lookup"><span data-stu-id="ce325-200">Active</span></span> | <span data-ttu-id="ce325-201">El dispositivo se ha entregado al usuario y se ha registrado con el inquilino.</span><span class="sxs-lookup"><span data-stu-id="ce325-201">The device has been delivered to the user and they have registered with your tenant.</span></span> <span data-ttu-id="ce325-202">Esto también indica que usan regularmente el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ce325-202">This also indicates that they are regularly using the device.</span></span> |
| <span data-ttu-id="ce325-203">Inactivo</span><span class="sxs-lookup"><span data-stu-id="ce325-203">Inactive</span></span> | <span data-ttu-id="ce325-204">El dispositivo se ha entregado al usuario y se ha registrado con el inquilino.</span><span class="sxs-lookup"><span data-stu-id="ce325-204">The device has been delivered to the user and they have registered with your tenant.</span></span> <span data-ttu-id="ce325-205">Sin embargo, no han usado el dispositivo recientemente (en los últimos 7 días).</span><span class="sxs-lookup"><span data-stu-id="ce325-205">However, they have not used the device recently (in the last 7 days).</span></span>  | 

#### <a name="troubleshooting-device-registration"></a><span data-ttu-id="ce325-206">Solución de problemas de registro de dispositivos</span><span class="sxs-lookup"><span data-stu-id="ce325-206">Troubleshooting device registration</span></span>

| <span data-ttu-id="ce325-207">Mensaje de error</span><span class="sxs-lookup"><span data-stu-id="ce325-207">Error message</span></span> | <span data-ttu-id="ce325-208">Detalles</span><span class="sxs-lookup"><span data-stu-id="ce325-208">Details</span></span> |
|---------------|-------------|
| <span data-ttu-id="ce325-209">Dispositivo no encontrado</span><span class="sxs-lookup"><span data-stu-id="ce325-209">Device not found</span></span> | <span data-ttu-id="ce325-210">No pudimos registrar este dispositivo porque no pudimos encontrar una coincidencia para el fabricante, modelo o número de serie proporcionado.</span><span class="sxs-lookup"><span data-stu-id="ce325-210">We couldn’t register this device because we could not find a match for the provided manufacturer, model, or serial number.</span></span> <span data-ttu-id="ce325-211">Confirme estos valores con el proveedor de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="ce325-211">Confirm these values with your device supplier.</span></span> |
| <span data-ttu-id="ce325-212">El hash de hardware no es válido</span><span class="sxs-lookup"><span data-stu-id="ce325-212">Hardware hash not valid</span></span> | <span data-ttu-id="ce325-213">El hash de hardware que proporcionaste para este dispositivo no se formateó correctamente.</span><span class="sxs-lookup"><span data-stu-id="ce325-213">The hardware hash you provided for this device was not formatted correctly.</span></span> <span data-ttu-id="ce325-214">Compruebe el hash de hardware y vuelva a enviar.</span><span class="sxs-lookup"><span data-stu-id="ce325-214">Double-check the hardware hash and then resubmit.</span></span> |
| <span data-ttu-id="ce325-215">Dispositivo ya registrado</span><span class="sxs-lookup"><span data-stu-id="ce325-215">Device already registered</span></span> | <span data-ttu-id="ce325-216">Este dispositivo ya está registrado en la organización.</span><span class="sxs-lookup"><span data-stu-id="ce325-216">This device is already registered to your organization.</span></span> <span data-ttu-id="ce325-217">No se requiere ninguna acción adicional.</span><span class="sxs-lookup"><span data-stu-id="ce325-217">No further action required.</span></span> |
| <span data-ttu-id="ce325-218">Dispositivo reclamado por otra organización</span><span class="sxs-lookup"><span data-stu-id="ce325-218">Device claimed by another organization</span></span> | <span data-ttu-id="ce325-219">Este dispositivo ya ha sido reclamado por otra organización.</span><span class="sxs-lookup"><span data-stu-id="ce325-219">This device has already been claimed by another organization.</span></span> <span data-ttu-id="ce325-220">Consulta con el proveedor de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="ce325-220">Check with your device supplier.</span></span> |
| <span data-ttu-id="ce325-221">Error inesperado</span><span class="sxs-lookup"><span data-stu-id="ce325-221">Unexpected error</span></span> | <span data-ttu-id="ce325-222">La solicitud no se pudo procesar automáticamente.</span><span class="sxs-lookup"><span data-stu-id="ce325-222">Your request could not be automatically processed.</span></span> <span data-ttu-id="ce325-223">Póngase en contacto con el soporte técnico y proporcione el identificador de solicitud: <requestId></span><span class="sxs-lookup"><span data-stu-id="ce325-223">Contact Support and provide the Request ID: <requestId></span></span> |

### <a name="check-the-image"></a><span data-ttu-id="ce325-224">Comprobar la imagen</span><span class="sxs-lookup"><span data-stu-id="ce325-224">Check the image</span></span>

<span data-ttu-id="ce325-225">Si el dispositivo procede de un proveedor de partners de Escritorio administrado de Microsoft, la imagen debe ser correcta.</span><span class="sxs-lookup"><span data-stu-id="ce325-225">If your device has come from a Microsoft Managed Desktop partner supplier, the image should be correct.</span></span>

<span data-ttu-id="ce325-226">También puedes aplicar la imagen por tu cuenta si lo prefieres.</span><span class="sxs-lookup"><span data-stu-id="ce325-226">You’re also welcome to apply the image on your own if you prefer.</span></span> <span data-ttu-id="ce325-227">Para empezar, póngase en contacto con el representante de Microsoft con el que está trabajando y le proporcionarán la ubicación y los pasos para aplicar la imagen.</span><span class="sxs-lookup"><span data-stu-id="ce325-227">To get started, contact the Microsoft representative you’re working with and they will provide you the location and steps for applying the image.</span></span>

### <a name="deliver-the-device"></a><span data-ttu-id="ce325-228">Entregar el dispositivo</span><span class="sxs-lookup"><span data-stu-id="ce325-228">Deliver the device</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ce325-229">Antes de entregar el dispositivo al usuario, asegúrese de haber obtenido y aplicado las licencias adecuadas [para](../get-ready/prerequisites.md) ese usuario.</span><span class="sxs-lookup"><span data-stu-id="ce325-229">Before you hand off the device to your user, make sure you have obtained and applied the [appropriate licenses](../get-ready/prerequisites.md) for that user.</span></span>

<span data-ttu-id="ce325-230">Si se aplican todas las [](get-started-devices.md)licencias, puedes preparar a los usuarios para usar dispositivos y, a continuación, el usuario puede iniciar el dispositivo y continuar con la experiencia de configuración de Windows.</span><span class="sxs-lookup"><span data-stu-id="ce325-230">If all the licenses are applied, you can [get your users ready to use devices](get-started-devices.md), and then your user can start up the device and proceed through the Windows setup experience.</span></span>









