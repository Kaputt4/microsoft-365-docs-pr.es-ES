---
title: Antivirus de Microsoft Defender Infraestructura de escritorio virtual de implementación
description: Obtenga información sobre cómo implementar Antivirus de Microsoft Defender en un entorno de escritorio virtual para obtener el mejor equilibrio entre la protección y el rendimiento.
keywords: vdi, hyper-v, vm, máquina virtual, Windows Defender, antivirus, av, escritorio virtual, rds, escritorio remoto
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/11/2021
ms.reviewer: jesquive
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: ce200ca12bacc3ae8d9f7b48d36274ca54322586
ms.sourcegitcommit: 3e197d1ff7d8100faeaf1f5a33f1ad4ed2f72e99
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/11/2021
ms.locfileid: "52908034"
---
# <a name="deployment-guide-for-microsoft-defender-antivirus-in-a-virtual-desktop-infrastructure-vdi-environment"></a><span data-ttu-id="11209-104">Guía de implementación del Antivirus de Microsoft Defender en un entorno de infraestructura de escritorio virtual</span><span class="sxs-lookup"><span data-stu-id="11209-104">Deployment guide for Microsoft Defender Antivirus in a virtual desktop infrastructure (VDI) environment</span></span>

<span data-ttu-id="11209-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="11209-105">**Applies to:**</span></span>

- [<span data-ttu-id="11209-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="11209-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="11209-107">Además de las configuraciones de hardware o locales estándar, también puede usar Antivirus de Microsoft Defender en un entorno de escritorio remoto (RDS) o de infraestructura de escritorio virtual (VDI).</span><span class="sxs-lookup"><span data-stu-id="11209-107">In addition to standard on-premises or hardware configurations, you can also use Microsoft Defender Antivirus in a remote desktop (RDS) or virtual desktop infrastructure (VDI) environment.</span></span>

<span data-ttu-id="11209-108">Consulte [Windows documentación de Escritorio virtual para](/azure/virtual-desktop) obtener más información sobre Escritorio remoto de Microsoft servicios y compatibilidad con VDI.</span><span class="sxs-lookup"><span data-stu-id="11209-108">See [Windows Virtual Desktop Documentation](/azure/virtual-desktop) for more details on Microsoft Remote Desktop Services and VDI support.</span></span>

<span data-ttu-id="11209-109">Para las máquinas virtuales basadas en Azure, [consulte Install Endpoint Protection in Azure Defender](/azure/security-center/security-center-install-endpoint-protection).</span><span class="sxs-lookup"><span data-stu-id="11209-109">For Azure-based virtual machines, see [Install Endpoint Protection in Azure Defender](/azure/security-center/security-center-install-endpoint-protection).</span></span>

<span data-ttu-id="11209-110">Con la capacidad de implementar fácilmente actualizaciones en máquinas virtuales que se ejecutan en VDI, hemos acortado esta guía para centrarse en cómo puede obtener actualizaciones en sus máquinas de forma rápida y sencilla.</span><span class="sxs-lookup"><span data-stu-id="11209-110">With the ability to easily deploy updates to VMs running in VDIs, we've shortened this guide to focus on how you can get updates on your machines quickly and easily.</span></span> <span data-ttu-id="11209-111">Ya no es necesario crear y sellar imágenes doradas periódicamente, ya que las actualizaciones se expanden en sus bits de componente en el servidor host y, a continuación, se descargan directamente en la máquina virtual cuando está activada.</span><span class="sxs-lookup"><span data-stu-id="11209-111">You no longer need to create and seal golden images on a periodic basis, as updates are expanded into their component bits on the host server and then downloaded directly to the VM when it's turned on.</span></span>

<span data-ttu-id="11209-112">En esta guía se describe cómo configurar las máquinas virtuales para obtener una protección y un rendimiento óptimos, incluido cómo:</span><span class="sxs-lookup"><span data-stu-id="11209-112">This guide describes how to configure your VMs for optimal protection and performance, including how to:</span></span>

- [<span data-ttu-id="11209-113">Configurar un recurso compartido de archivos VDI dedicado para actualizaciones de inteligencia de seguridad</span><span class="sxs-lookup"><span data-stu-id="11209-113">Set up a dedicated VDI file share for security intelligence updates</span></span>](#set-up-a-dedicated-vdi-file-share)
- [<span data-ttu-id="11209-114">Aleatorizar exámenes programados</span><span class="sxs-lookup"><span data-stu-id="11209-114">Randomize scheduled scans</span></span>](#randomize-scheduled-scans)
- [<span data-ttu-id="11209-115">Usar exámenes rápidos</span><span class="sxs-lookup"><span data-stu-id="11209-115">Use quick scans</span></span>](#use-quick-scans)
- [<span data-ttu-id="11209-116">Impedir notificaciones</span><span class="sxs-lookup"><span data-stu-id="11209-116">Prevent notifications</span></span>](#prevent-notifications)
- [<span data-ttu-id="11209-117">Deshabilitar los exámenes para que no se produzcan después de cada actualización</span><span class="sxs-lookup"><span data-stu-id="11209-117">Disable scans from occurring after every update</span></span>](#disable-scans-after-an-update)
- [<span data-ttu-id="11209-118">Examinar máquinas o máquinas no actualizadas que han estado sin conexión durante un tiempo</span><span class="sxs-lookup"><span data-stu-id="11209-118">Scan out-of-date machines or machines that have been offline for a while</span></span>](#scan-vms-that-have-been-offline)
- [<span data-ttu-id="11209-119">Aplicar exclusiones</span><span class="sxs-lookup"><span data-stu-id="11209-119">Apply exclusions</span></span>](#exclusions)

<span data-ttu-id="11209-120">También puede descargar el documento técnico Antivirus de Microsoft Defender en [Infraestructura de escritorio virtual](https://demo.wd.microsoft.com/Content/wdav-testing-vdi-ssu.pdf), que analiza la nueva característica de actualización de inteligencia de seguridad compartida, junto con las pruebas de rendimiento y las instrucciones sobre cómo probar el rendimiento del antivirus en su propio VDI.</span><span class="sxs-lookup"><span data-stu-id="11209-120">You can also download the whitepaper [Microsoft Defender Antivirus on Virtual Desktop Infrastructure](https://demo.wd.microsoft.com/Content/wdav-testing-vdi-ssu.pdf), which looks at the new shared security intelligence update feature, alongside performance testing and guidance on how you can test antivirus performance on your own VDI.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="11209-121">Aunque la VDI se puede hospedar en Windows Server 2012 o Windows Server 2016, las máquinas virtuales (VM) deben ejecutar Windows 10, 1607 como mínimo, debido al aumento de las tecnologías y características de protección que no están disponibles en versiones anteriores de Windows.</span><span class="sxs-lookup"><span data-stu-id="11209-121">Although the VDI can be hosted on Windows Server 2012 or Windows Server 2016, the virtual machines (VMs) should be running Windows 10, 1607 at a minimum, due to increased protection technologies and features that are unavailable in earlier versions of Windows.</span></span><br/><span data-ttu-id="11209-122">Hay mejoras de rendimiento y características en la forma en que Microsoft Defender AV funciona en máquinas virtuales en Windows 10 Insider Preview, compilación 18323 (y versiones posteriores).</span><span class="sxs-lookup"><span data-stu-id="11209-122">There are performance and feature improvements to the way in which Microsoft Defender AV operates on virtual machines in Windows 10 Insider Preview, build 18323 (and later).</span></span> <span data-ttu-id="11209-123">Identificaremos en esta guía si necesita usar una compilación de Insider Preview; si no se especifica, la versión mínima necesaria para la mejor protección y rendimiento es Windows 10 1607.</span><span class="sxs-lookup"><span data-stu-id="11209-123">We'll identify in this guide if you need to be using an Insider Preview build; if it isn't specified, then the minimum required version for the best protection and performance is Windows 10 1607.</span></span>

## <a name="set-up-a-dedicated-vdi-file-share"></a><span data-ttu-id="11209-124">Configurar un recurso compartido de archivos VDI dedicado</span><span class="sxs-lookup"><span data-stu-id="11209-124">Set up a dedicated VDI file share</span></span>

<span data-ttu-id="11209-125">En Windows 10, versión 1903, presentamos la característica de inteligencia de seguridad compartida, que descarga el desempaquetar las actualizaciones de inteligencia de seguridad descargadas en un equipo host, lo que ahorra recursos anteriores de CPU, disco y memoria en máquinas individuales.</span><span class="sxs-lookup"><span data-stu-id="11209-125">In Windows 10, version 1903, we introduced the shared security intelligence feature, which offloads the unpackaging of downloaded security intelligence updates onto a host machine—thus saving previous CPU, disk, and memory resources on individual machines.</span></span> <span data-ttu-id="11209-126">Esta característica se ha backported y ahora funciona Windows 10 versión 1703 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="11209-126">This feature has been backported and now works in Windows 10 version 1703 and above.</span></span> <span data-ttu-id="11209-127">Puede establecer esta característica con una directiva de grupo o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="11209-127">You can set this feature with a Group Policy, or PowerShell.</span></span>

### <a name="use-group-policy-to-enable-the-shared-security-intelligence-feature"></a><span data-ttu-id="11209-128">Use la directiva de grupo para habilitar la característica de inteligencia de seguridad compartida:</span><span class="sxs-lookup"><span data-stu-id="11209-128">Use Group Policy to enable the shared security intelligence feature:</span></span>

1. <span data-ttu-id="11209-129">En el equipo de administración de directivas de grupo, abra la Consola de administración de directivas de grupo, haga clic con el botón secundario en el objeto de directiva de grupo que desea configurar y, a continuación, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="11209-129">On your Group Policy management computer, open the Group Policy Management Console, right-click the Group Policy Object you want to configure, and then click **Edit**.</span></span>

2. <span data-ttu-id="11209-130">En el **Editor de administración de directivas de grupo** vaya a Configuración del **equipo.**</span><span class="sxs-lookup"><span data-stu-id="11209-130">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="11209-131">Haga clic **en Plantillas administrativas**.</span><span class="sxs-lookup"><span data-stu-id="11209-131">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="11209-132">Expanda el árbol para Windows **componentes Antivirus de Microsoft Defender** actualizaciones  >    >  **de inteligencia de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="11209-132">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Security Intelligence Updates**.</span></span>

5. <span data-ttu-id="11209-133">Haga doble clic en **Definir ubicación de inteligencia de seguridad para clientes VDI** y, a continuación, establezca la opción en **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="11209-133">Double-click **Define security intelligence location for VDI clients**, and then set the option to **Enabled**.</span></span> <span data-ttu-id="11209-134">Aparece automáticamente un campo.</span><span class="sxs-lookup"><span data-stu-id="11209-134">A field automatically appears.</span></span>

6. <span data-ttu-id="11209-135">Escriba `\\<sharedlocation\>\wdav-update` (para obtener ayuda con este valor, vea [Descargar y desempaquete](#download-and-unpackage-the-latest-updates)).</span><span class="sxs-lookup"><span data-stu-id="11209-135">Enter `\\<sharedlocation\>\wdav-update` (for help with this value, see [Download and unpackage](#download-and-unpackage-the-latest-updates)).</span></span>

7. <span data-ttu-id="11209-136">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="11209-136">Click **OK**.</span></span>

8. <span data-ttu-id="11209-137">Implemente el GPO en las máquinas virtuales que desea probar.</span><span class="sxs-lookup"><span data-stu-id="11209-137">Deploy the GPO to the VMs you want to test.</span></span>

### <a name="use-powershell-to-enable-the-shared-security-intelligence-feature"></a><span data-ttu-id="11209-138">Usar PowerShell para habilitar la característica de inteligencia de seguridad compartida</span><span class="sxs-lookup"><span data-stu-id="11209-138">Use PowerShell to enable the shared security intelligence feature</span></span>

<span data-ttu-id="11209-139">Use el siguiente cmdlet para habilitar la característica.</span><span class="sxs-lookup"><span data-stu-id="11209-139">Use the following cmdlet to enable the feature.</span></span> <span data-ttu-id="11209-140">Tendrá que insertar esto como normalmente insertaría directivas de configuración basadas en PowerShell en las máquinas virtuales:</span><span class="sxs-lookup"><span data-stu-id="11209-140">You’ll need to then push this as you normally would push PowerShell-based configuration policies onto the VMs:</span></span>

```PowerShell
Set-MpPreference -SharedSignaturesPath \\<shared location>\wdav-update
```

<span data-ttu-id="11209-141">Consulta la sección Descargar y desempaquete para saber cuál [](#download-and-unpackage-the-latest-updates) \<shared location\> será.</span><span class="sxs-lookup"><span data-stu-id="11209-141">See the [Download and unpackage](#download-and-unpackage-the-latest-updates) section for what the \<shared location\> will be.</span></span>

## <a name="download-and-unpackage-the-latest-updates"></a><span data-ttu-id="11209-142">Descargar y desempaquete las actualizaciones más recientes</span><span class="sxs-lookup"><span data-stu-id="11209-142">Download and unpackage the latest updates</span></span>

<span data-ttu-id="11209-143">Ahora puedes empezar a descargar e instalar nuevas actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="11209-143">Now you can get started on downloading and installing new updates.</span></span> <span data-ttu-id="11209-144">Hemos creado un script de PowerShell de ejemplo para usted a continuación.</span><span class="sxs-lookup"><span data-stu-id="11209-144">We’ve created a sample PowerShell script for you below.</span></span> <span data-ttu-id="11209-145">Este script es la forma más sencilla de descargar nuevas actualizaciones y prepararlas para las máquinas virtuales.</span><span class="sxs-lookup"><span data-stu-id="11209-145">This script is the easiest way to download new updates and get them ready for your VMs.</span></span> <span data-ttu-id="11209-146">A continuación, debe establecer el script para que se ejecute en un momento determinado en el equipo de administración mediante una tarea programada (o, si está familiarizado con el uso de scripts de PowerShell en Azure, Intune o SCCM, también podría usar esos scripts).</span><span class="sxs-lookup"><span data-stu-id="11209-146">You should then set the script to run at a certain time on the management machine by using a scheduled task (or, if you’re familiar with using PowerShell scripts in Azure, Intune, or SCCM, you could also use those scripts).</span></span>

```PowerShell
$vdmpathbase = "$env:systemdrive\wdav-update\{00000000-0000-0000-0000-"
$vdmpathtime = Get-Date -format "yMMddHHmmss"
$vdmpath = $vdmpathbase + $vdmpathtime + '}'
$vdmpackage = $vdmpath + '\mpam-fe.exe'

New-Item -ItemType Directory -Force -Path $vdmpath | Out-Null

Invoke-WebRequest -Uri 'https://go.microsoft.com/fwlink/?LinkID=121721&arch=x64' -OutFile $vdmpackage

cmd /c "cd $vdmpath & c: & mpam-fe.exe /x"
```

<span data-ttu-id="11209-147">Puede establecer una tarea programada para que se ejecute una vez al día de modo que siempre que se descargue y desempaquete el paquete, las máquinas virtuales recibirán la nueva actualización.</span><span class="sxs-lookup"><span data-stu-id="11209-147">You can set a scheduled task to run once a day so that whenever the package is downloaded and unpacked then the VMs will receive the new update.</span></span> <span data-ttu-id="11209-148">Se recomienda empezar por una vez al día, pero debe experimentar con aumentar o disminuir la frecuencia para comprender el impacto.</span><span class="sxs-lookup"><span data-stu-id="11209-148">We suggest starting with once a day—but you should experiment with increasing or decreasing the frequency to understand the impact.</span></span> 

<span data-ttu-id="11209-149">Los paquetes de inteligencia de seguridad suelen publicarse una vez cada tres o cuatro horas.</span><span class="sxs-lookup"><span data-stu-id="11209-149">Security intelligence packages are typically published once every three to four hours.</span></span> <span data-ttu-id="11209-150">No se recomienda establecer una frecuencia inferior a cuatro horas porque aumentará la sobrecarga de red en el equipo de administración sin ningún beneficio.</span><span class="sxs-lookup"><span data-stu-id="11209-150">Setting a frequency shorter than four hours isn’t advised because it will increase the network overhead on your management machine for no benefit.</span></span>

### <a name="set-a-scheduled-task-to-run-the-powershell-script"></a><span data-ttu-id="11209-151">Establecer una tarea programada para ejecutar el script de PowerShell</span><span class="sxs-lookup"><span data-stu-id="11209-151">Set a scheduled task to run the PowerShell script</span></span>

1. <span data-ttu-id="11209-152">En el equipo de administración, abra el menú Inicio y escriba **Programador de tareas**.</span><span class="sxs-lookup"><span data-stu-id="11209-152">On the management machine, open the Start menu and type **Task Scheduler**.</span></span> <span data-ttu-id="11209-153">Ábralo y seleccione **Crear tarea...**</span><span class="sxs-lookup"><span data-stu-id="11209-153">Open it and select **Create task…**</span></span> <span data-ttu-id="11209-154">en el panel lateral.</span><span class="sxs-lookup"><span data-stu-id="11209-154">on the side panel.</span></span>

2. <span data-ttu-id="11209-155">Escriba el nombre como **Desempaquete de inteligencia de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="11209-155">Enter the name as **Security intelligence unpacker**.</span></span> <span data-ttu-id="11209-156">Vaya a la **pestaña Desencadenador.** Seleccione **Nuevo...**</span><span class="sxs-lookup"><span data-stu-id="11209-156">Go to the **Trigger** tab. Select **New…**</span></span><span data-ttu-id="11209-157"> > **Diario** y seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="11209-157"> > **Daily**, and select **OK**.</span></span>

3. <span data-ttu-id="11209-158">Vaya a la **pestaña** Acciones. Seleccione **Nuevo...**</span><span class="sxs-lookup"><span data-stu-id="11209-158">Go to the **Actions** tab. Select **New…**</span></span> <span data-ttu-id="11209-159">Escriba **PowerShell** en el **campo Programa/Script.**</span><span class="sxs-lookup"><span data-stu-id="11209-159">Enter **PowerShell** in the **Program/Script** field.</span></span> <span data-ttu-id="11209-160">Escriba `-ExecutionPolicy Bypass c:\wdav-update\vdmdlunpack.ps1` en el campo Agregar **argumentos.**</span><span class="sxs-lookup"><span data-stu-id="11209-160">Enter `-ExecutionPolicy Bypass c:\wdav-update\vdmdlunpack.ps1` in the **Add arguments** field.</span></span> <span data-ttu-id="11209-161">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="11209-161">Select **OK**.</span></span>

4. <span data-ttu-id="11209-162">Puede elegir configurar opciones adicionales si lo desea.</span><span class="sxs-lookup"><span data-stu-id="11209-162">You can choose to configure additional settings if you wish.</span></span>

5. <span data-ttu-id="11209-163">Seleccione **Aceptar** para guardar la tarea programada.</span><span class="sxs-lookup"><span data-stu-id="11209-163">Select **OK** to save the scheduled task.</span></span>
 
<span data-ttu-id="11209-164">Puede iniciar la actualización manualmente haciendo clic con el botón secundario en la tarea y haciendo clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="11209-164">You can initiate the update manually by right-clicking on the task and clicking **Run**.</span></span>

### <a name="download-and-unpackage-manually"></a><span data-ttu-id="11209-165">Descargar y desempaquete manualmente</span><span class="sxs-lookup"><span data-stu-id="11209-165">Download and unpackage manually</span></span>

<span data-ttu-id="11209-166">Si prefiere hacer todo manualmente, esto es lo que debe hacer para replicar el comportamiento del script:</span><span class="sxs-lookup"><span data-stu-id="11209-166">If you would prefer to do everything manually, here's what to do to replicate the script’s behavior:</span></span>

1. <span data-ttu-id="11209-167">Cree una nueva carpeta en la raíz del sistema llamada para almacenar actualizaciones de `wdav_update` inteligencia, por ejemplo, cree la carpeta `c:\wdav_update` .</span><span class="sxs-lookup"><span data-stu-id="11209-167">Create a new folder on the system root called `wdav_update` to store intelligence updates, for example, create the folder `c:\wdav_update`.</span></span>

2. <span data-ttu-id="11209-168">Crear una subcarpeta en *wdav_update* con un nombre GUID, como, por ejemplo, `{00000000-0000-0000-0000-000000000000}`</span><span class="sxs-lookup"><span data-stu-id="11209-168">Create a subfolder under *wdav_update* with a GUID name, such as `{00000000-0000-0000-0000-000000000000}`</span></span>

<span data-ttu-id="11209-169">Este es un ejemplo: `c:\wdav_update\{00000000-0000-0000-0000-000000000000}`</span><span class="sxs-lookup"><span data-stu-id="11209-169">Here's an example: `c:\wdav_update\{00000000-0000-0000-0000-000000000000}`</span></span>

   > [!NOTE]
   > <span data-ttu-id="11209-170">En el script lo establecemos para que los últimos 12 dígitos del GUID sean el año, mes, día y hora en que se descargó el archivo para que se cree una nueva carpeta cada vez.</span><span class="sxs-lookup"><span data-stu-id="11209-170">In the script we set it so the last 12 digits of the GUID are the year, month, day, and time when the file was downloaded so that a new folder is created each time.</span></span> <span data-ttu-id="11209-171">Puede cambiar esto para que el archivo se descargue en la misma carpeta cada vez.</span><span class="sxs-lookup"><span data-stu-id="11209-171">You can change this so that the file is downloaded to the same folder each time.</span></span>

3. <span data-ttu-id="11209-172">Descargue un paquete de inteligencia de seguridad [https://www.microsoft.com/wdsi/definitions](https://www.microsoft.com/wdsi/definitions)  desde en la carpeta GUID.</span><span class="sxs-lookup"><span data-stu-id="11209-172">Download a security intelligence package from [https://www.microsoft.com/wdsi/definitions](https://www.microsoft.com/wdsi/definitions)  into the GUID folder.</span></span> <span data-ttu-id="11209-173">El archivo debe tener el nombre `mpam-fe.exe` .</span><span class="sxs-lookup"><span data-stu-id="11209-173">The file should be named `mpam-fe.exe`.</span></span>

4. <span data-ttu-id="11209-174">Abra una ventana del símbolo del sistema cmd y vaya a la carpeta GUID que creó.</span><span class="sxs-lookup"><span data-stu-id="11209-174">Open a cmd prompt window and navigate to the GUID folder you created.</span></span> <span data-ttu-id="11209-175">Use el **comando de extracción /X** para extraer los archivos, por ejemplo `mpam-fe.exe /X` .</span><span class="sxs-lookup"><span data-stu-id="11209-175">Use the **/X** extraction command to extract the files, for example `mpam-fe.exe /X`.</span></span>

   > [!NOTE]
   > <span data-ttu-id="11209-176">Las máquinas virtuales recogerán el paquete actualizado siempre que se cree una nueva carpeta GUID con un paquete de actualización extraído o siempre que se actualice una carpeta existente con un nuevo paquete extraído.</span><span class="sxs-lookup"><span data-stu-id="11209-176">The VMs will pick up the updated package whenever a new GUID folder is created with an extracted update package or whenever an existing folder is updated with a new extracted package.</span></span>

## <a name="randomize-scheduled-scans"></a><span data-ttu-id="11209-177">Aleatorizar exámenes programados</span><span class="sxs-lookup"><span data-stu-id="11209-177">Randomize scheduled scans</span></span>

<span data-ttu-id="11209-178">Los exámenes programados se ejecutan además de la protección y [el examen en tiempo real.](configure-real-time-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="11209-178">Scheduled scans run in addition to [real-time protection and scanning](configure-real-time-protection-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="11209-179">La hora de inicio del examen en sí se sigue basando en la directiva de examen programada (**ScheduleDay**, **ScheduleTime** y **ScheduleQuickScanTime**).</span><span class="sxs-lookup"><span data-stu-id="11209-179">The start time of the scan itself is still based on the scheduled scan policy (**ScheduleDay**, **ScheduleTime**, and **ScheduleQuickScanTime**).</span></span> <span data-ttu-id="11209-180">La aleatorización hará Antivirus de Microsoft Defender iniciar un examen en cada equipo dentro de una ventana de 4 horas desde el tiempo establecido para el examen programado.</span><span class="sxs-lookup"><span data-stu-id="11209-180">Randomization will cause Microsoft Defender Antivirus to start a scan on each machine within a 4-hour window from the time set for the scheduled scan.</span></span>

<span data-ttu-id="11209-181">Consulte [Programar exámenes para](scheduled-catch-up-scans-microsoft-defender-antivirus.md) obtener otras opciones de configuración disponibles para exámenes programados.</span><span class="sxs-lookup"><span data-stu-id="11209-181">See [Schedule scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md) for other configuration options available for scheduled scans.</span></span>

## <a name="use-quick-scans"></a><span data-ttu-id="11209-182">Usar exámenes rápidos</span><span class="sxs-lookup"><span data-stu-id="11209-182">Use quick scans</span></span>

<span data-ttu-id="11209-183">Puede especificar el tipo de examen que se debe realizar durante un examen programado.</span><span class="sxs-lookup"><span data-stu-id="11209-183">You can specify the type of scan that should be performed during a scheduled scan.</span></span> <span data-ttu-id="11209-184">Los exámenes rápidos son el enfoque preferido, ya que están diseñados para buscar en todos los lugares donde el malware debe residir para estar activo.</span><span class="sxs-lookup"><span data-stu-id="11209-184">Quick scans are the preferred approach as they are designed to look in all places where malware needs to reside to be active.</span></span> <span data-ttu-id="11209-185">El siguiente procedimiento describe cómo configurar exámenes rápidos mediante la directiva de grupo.</span><span class="sxs-lookup"><span data-stu-id="11209-185">The following procedure describes how to set up quick scans using Group Policy.</span></span>

1. <span data-ttu-id="11209-186">En el Editor de directivas de grupo, vaya a **Plantillas administrativas** Windows  >  **componentes**  >  **Antivirus de Microsoft Defender**  >  **Examinar**.</span><span class="sxs-lookup"><span data-stu-id="11209-186">In your Group Policy Editor, go to **Administrative templates** > **Windows components** > **Microsoft Defender Antivirus** > **Scan**.</span></span>

2. <span data-ttu-id="11209-187">Seleccione **Especificar el tipo de examen que se usará para un examen programado** y, a continuación, edite la configuración de directiva.</span><span class="sxs-lookup"><span data-stu-id="11209-187">Select **Specify the scan type to use for a scheduled scan** and then edit the policy setting.</span></span>

3. <span data-ttu-id="11209-188">Establezca la directiva en **Habilitado** y, a continuación, en **Opciones,** seleccione  **Examen rápido**.</span><span class="sxs-lookup"><span data-stu-id="11209-188">Set the policy to **Enabled**, and then under **Options**, select  **Quick scan**.</span></span>

4. <span data-ttu-id="11209-189">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="11209-189">Select **OK**.</span></span> 

5. <span data-ttu-id="11209-190">Implemente el objeto de directiva de grupo como lo haría normalmente.</span><span class="sxs-lookup"><span data-stu-id="11209-190">Deploy your Group Policy object as you usually do.</span></span>

## <a name="prevent-notifications"></a><span data-ttu-id="11209-191">Impedir notificaciones</span><span class="sxs-lookup"><span data-stu-id="11209-191">Prevent notifications</span></span>

<span data-ttu-id="11209-192">A veces, Antivirus de Microsoft Defender notificaciones se pueden enviar o conservar en varias sesiones.</span><span class="sxs-lookup"><span data-stu-id="11209-192">Sometimes, Microsoft Defender Antivirus notifications may be sent to or persist across multiple sessions.</span></span> <span data-ttu-id="11209-193">Para minimizar este problema, puede bloquear la interfaz Antivirus de Microsoft Defender usuario.</span><span class="sxs-lookup"><span data-stu-id="11209-193">In order to minimize this problem, you can lock down the Microsoft Defender Antivirus user interface.</span></span> <span data-ttu-id="11209-194">En el siguiente procedimiento se describe cómo suprimir las notificaciones con la directiva de grupo.</span><span class="sxs-lookup"><span data-stu-id="11209-194">The following procedure describes how to suppress notifications with Group Policy.</span></span>

1. <span data-ttu-id="11209-195">En el Editor de directivas de grupo, vaya **a Windows componentes Antivirus de Microsoft Defender** interfaz de  >    >  **cliente**.</span><span class="sxs-lookup"><span data-stu-id="11209-195">In your Group Policy Editor, go to **Windows components** > **Microsoft Defender Antivirus** > **Client Interface**.</span></span>

2. <span data-ttu-id="11209-196">Seleccione **Suprimir todas las notificaciones** y, a continuación, edite la configuración de directiva.</span><span class="sxs-lookup"><span data-stu-id="11209-196">Select **Suppress all notifications** and then edit the policy settings.</span></span> 

3. <span data-ttu-id="11209-197">Establezca la directiva en **Habilitado** y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="11209-197">Set the policy to **Enabled**, and then select **OK**.</span></span>

4. <span data-ttu-id="11209-198">Implemente el objeto de directiva de grupo como lo haría normalmente.</span><span class="sxs-lookup"><span data-stu-id="11209-198">Deploy your Group Policy object as you usually do.</span></span>

<span data-ttu-id="11209-199">La supresión de notificaciones impide que las notificaciones Antivirus de Microsoft Defender se muestren en el Centro de acciones en Windows 10 cuando se realizan exámenes o se realizan acciones de corrección.</span><span class="sxs-lookup"><span data-stu-id="11209-199">Suppressing notifications prevents notifications from Microsoft Defender Antivirus from showing up in the Action Center on Windows 10 when scans are done or remediation actions are taken.</span></span> <span data-ttu-id="11209-200">Sin embargo, el equipo de operaciones de seguridad verá los resultados del examen en [el portal Microsoft 365 Defender](microsoft-defender-security-center.md).</span><span class="sxs-lookup"><span data-stu-id="11209-200">However, your security operations team will see the results of the scan in the [Microsoft 365 Defender portal](microsoft-defender-security-center.md).</span></span>

> [!TIP]
> <span data-ttu-id="11209-201">Para abrir el Centro de acciones en Windows 10, siga uno de los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="11209-201">To open the Action Center on Windows 10, take one of the following steps:</span></span>
> - <span data-ttu-id="11209-202">En el extremo derecho de la barra de tareas, seleccione el icono centro de acciones.</span><span class="sxs-lookup"><span data-stu-id="11209-202">On the right end of the taskbar, select the Action Center icon.</span></span>
> - <span data-ttu-id="11209-203">Presione el Windows tecla de logotipo + A.</span><span class="sxs-lookup"><span data-stu-id="11209-203">Press the Windows logo key button + A.</span></span>
> - <span data-ttu-id="11209-204">En un dispositivo con pantalla táctil, desliza el dedo desde el borde derecho de la pantalla.</span><span class="sxs-lookup"><span data-stu-id="11209-204">On a touchscreen device, swipe in from the right edge of the screen.</span></span>

## <a name="disable-scans-after-an-update"></a><span data-ttu-id="11209-205">Deshabilitar exámenes después de una actualización</span><span class="sxs-lookup"><span data-stu-id="11209-205">Disable scans after an update</span></span>

<span data-ttu-id="11209-206">Deshabilitar un examen después de una actualización impedirá que se produzca un examen después de recibir una actualización.</span><span class="sxs-lookup"><span data-stu-id="11209-206">Disabling a scan after an update will prevent a scan from occurring after receiving an update.</span></span> <span data-ttu-id="11209-207">Puedes aplicar esta configuración al crear la imagen base si también has ejecutado un examen rápido.</span><span class="sxs-lookup"><span data-stu-id="11209-207">You can apply this setting when creating the base image if you have also run a quick scan.</span></span> <span data-ttu-id="11209-208">De este modo, puede impedir que la máquina virtual recién actualizada vuelva a realizar un examen (como ya la ha examinado al crear la imagen base).</span><span class="sxs-lookup"><span data-stu-id="11209-208">This way, you can prevent the newly updated VM from performing a scan again (as you've already scanned it when you created the base image).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="11209-209">La ejecución de exámenes después de una actualización ayudará a garantizar que las máquinas virtuales estén protegidas con las últimas actualizaciones de inteligencia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="11209-209">Running scans after an update will help ensure your VMs are protected with the latest Security intelligence updates.</span></span> <span data-ttu-id="11209-210">Deshabilitar esta opción reducirá el nivel de protección de las máquinas virtuales y solo se debe usar al crear o implementar la imagen base por primera vez.</span><span class="sxs-lookup"><span data-stu-id="11209-210">Disabling this option will reduce the protection level of your VMs and should only be used when first creating or deploying the base image.</span></span>

1. <span data-ttu-id="11209-211">En el Editor de directivas de grupo, vaya **a Windows componentes Antivirus de Microsoft Defender** actualizaciones de inteligencia de  >    >  **seguridad**.</span><span class="sxs-lookup"><span data-stu-id="11209-211">In your Group Policy Editor, go to **Windows components** > **Microsoft Defender Antivirus** > **Security Intelligence Updates**.</span></span>

2. <span data-ttu-id="11209-212">Seleccione **Activar el examen después de la actualización de inteligencia de seguridad** y, a continuación, edite la configuración de directiva.</span><span class="sxs-lookup"><span data-stu-id="11209-212">Select **Turn on scan after security intelligence update** and then edit the policy setting.</span></span>

3. <span data-ttu-id="11209-213">Establezca la directiva en **Deshabilitado**.</span><span class="sxs-lookup"><span data-stu-id="11209-213">Set the policy to **Disabled**.</span></span>

4. <span data-ttu-id="11209-214">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="11209-214">Select **OK**.</span></span>

5. <span data-ttu-id="11209-215">Implemente el objeto de directiva de grupo como lo haría normalmente.</span><span class="sxs-lookup"><span data-stu-id="11209-215">Deploy your Group Policy object as you usually do.</span></span>

<span data-ttu-id="11209-216">Esta directiva impide que un examen se ejecute inmediatamente después de una actualización.</span><span class="sxs-lookup"><span data-stu-id="11209-216">This policy prevents a scan from running immediately after an update.</span></span>

## <a name="scan-vms-that-have-been-offline"></a><span data-ttu-id="11209-217">Examinar máquinas virtuales sin conexión</span><span class="sxs-lookup"><span data-stu-id="11209-217">Scan VMs that have been offline</span></span>

1. <span data-ttu-id="11209-218">En el Editor de directivas de grupo, vaya a Windows **componentes Antivirus de Microsoft Defender**  >    >  **Scan**.</span><span class="sxs-lookup"><span data-stu-id="11209-218">In your Group Policy Editor, go to to **Windows components** > **Microsoft Defender Antivirus** > **Scan**.</span></span>

2. <span data-ttu-id="11209-219">Seleccione **Activar el examen rápido de puesta al día** y, a continuación, edite la configuración de directiva.</span><span class="sxs-lookup"><span data-stu-id="11209-219">Select **Turn on catch-up quick scan** and then edit the policy setting.</span></span>

3. <span data-ttu-id="11209-220">Establezca la directiva en **Enabled**.</span><span class="sxs-lookup"><span data-stu-id="11209-220">Set the policy to **Enabled**.</span></span>

4. <span data-ttu-id="11209-221">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="11209-221">Select **OK**.</span></span>

5. <span data-ttu-id="11209-222">Implemente el objeto de directiva de grupo como suele hacer.</span><span class="sxs-lookup"><span data-stu-id="11209-222">Deploy your Group Policy Object as you usually do.</span></span>

<span data-ttu-id="11209-223">Esta directiva fuerza un examen si la máquina virtual ha perdido dos o más exámenes programados consecutivos.</span><span class="sxs-lookup"><span data-stu-id="11209-223">This policy forces a scan if the VM has missed two or more consecutive scheduled scans.</span></span>

## <a name="enable-headless-ui-mode"></a><span data-ttu-id="11209-224">Habilitar el modo de interfaz de usuario sin cabeza</span><span class="sxs-lookup"><span data-stu-id="11209-224">Enable headless UI mode</span></span>

1. <span data-ttu-id="11209-225">En el Editor de directivas de grupo, vaya **a Windows componentes Antivirus de Microsoft Defender** interfaz de  >    >  **cliente**.</span><span class="sxs-lookup"><span data-stu-id="11209-225">In your Group Policy Editor, go to **Windows components** > **Microsoft Defender Antivirus** > **Client Interface**.</span></span>

2. <span data-ttu-id="11209-226">Selecciona **Habilitar el modo de interfaz de usuario sin** cabeza y edita la directiva.</span><span class="sxs-lookup"><span data-stu-id="11209-226">Select **Enable headless UI mode** and edit the policy.</span></span>

3. <span data-ttu-id="11209-227">Establezca la directiva en **Enabled**.</span><span class="sxs-lookup"><span data-stu-id="11209-227">Set the policy to **Enabled**.</span></span>

4. <span data-ttu-id="11209-228">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="11209-228">Click **OK**.</span></span>

5. <span data-ttu-id="11209-229">Implemente el objeto de directiva de grupo como suele hacer.</span><span class="sxs-lookup"><span data-stu-id="11209-229">Deploy your Group Policy Object as you usually do.</span></span>
 
<span data-ttu-id="11209-230">Esta directiva oculta toda la interfaz Antivirus de Microsoft Defender usuario de los usuarios finales de la organización.</span><span class="sxs-lookup"><span data-stu-id="11209-230">This policy hides the entire Microsoft Defender Antivirus user interface from end users in your organization.</span></span>

## <a name="exclusions"></a><span data-ttu-id="11209-231">Exclusiones</span><span class="sxs-lookup"><span data-stu-id="11209-231">Exclusions</span></span>

<span data-ttu-id="11209-232">Las exclusiones se pueden agregar, quitar o personalizar para que se adapten a sus necesidades.</span><span class="sxs-lookup"><span data-stu-id="11209-232">Exclusions can be added, removed, or customized to suit your needs.</span></span>

<span data-ttu-id="11209-233">Para obtener más información, [vea Configure Antivirus de Microsoft Defender exclusiones en Windows Server](configure-exclusions-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="11209-233">For more information, see [Configure Microsoft Defender Antivirus exclusions on Windows Server](configure-exclusions-microsoft-defender-antivirus.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="11209-234">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="11209-234">Additional resources</span></span>

- [<span data-ttu-id="11209-235">Blog Community tech: Configuración de Antivirus de Microsoft Defender para máquinas VDI no persistentes</span><span class="sxs-lookup"><span data-stu-id="11209-235">Tech Community Blog: Configuring Microsoft Defender Antivirus for non-persistent VDI machines</span></span>](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/configuring-microsoft-defender-antivirus-for-non-persistent-vdi/ba-p/1489633)
- [<span data-ttu-id="11209-236">Foros de TechNet en Servicios de Escritorio remoto y VDI</span><span class="sxs-lookup"><span data-stu-id="11209-236">TechNet forums on Remote Desktop Services and VDI</span></span>](https://social.technet.microsoft.com/Forums/windowsserver/en-US/home?forum=winserverTS)
- [<span data-ttu-id="11209-237">Script de PowerShell SignatureDownloadCustomTask</span><span class="sxs-lookup"><span data-stu-id="11209-237">SignatureDownloadCustomTask PowerShell script</span></span>](https://www.powershellgallery.com/packages/SignatureDownloadCustomTask/1.4)