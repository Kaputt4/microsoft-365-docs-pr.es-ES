---
title: Incorporar dispositivos de varias sesiones a Windows 10 en Windows Virtual Desktop
description: Lea más en este artículo sobre la incorporación Windows 10 dispositivos de varias sesiones en Windows Escritorio virtual
keywords: Windows Escritorio virtual, WVD, microsoft defender, punto de conexión, incorporación
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
ms.topic: article
author: dansimp
ms.author: dansimp
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.openlocfilehash: 7ade1ae1e045cb52f48d231acbc1712e753b6bc3
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841851"
---
# <a name="onboard-windows-10-multi-session-devices-in-windows-virtual-desktop"></a><span data-ttu-id="91f5a-104">Incorporar dispositivos de varias sesiones a Windows 10 en Windows Virtual Desktop</span><span class="sxs-lookup"><span data-stu-id="91f5a-104">Onboard Windows 10 multi-session devices in Windows Virtual Desktop</span></span> 
<span data-ttu-id="91f5a-105">6 minutos para leer</span><span class="sxs-lookup"><span data-stu-id="91f5a-105">6 minutes to read</span></span> 

<span data-ttu-id="91f5a-106">Se aplica a:</span><span class="sxs-lookup"><span data-stu-id="91f5a-106">Applies to:</span></span> 
- <span data-ttu-id="91f5a-107">Windows 10 varias sesiones que se ejecutan en Windows Virtual Desktop (WVD)</span><span class="sxs-lookup"><span data-stu-id="91f5a-107">Windows 10 multi-session running on Windows Virtual Desktop (WVD)</span></span> 

<span data-ttu-id="91f5a-108">Microsoft Defender para endpoint admite la supervisión de VDI y Windows sesiones de Escritorio virtual.</span><span class="sxs-lookup"><span data-stu-id="91f5a-108">Microsoft Defender for Endpoint supports monitoring both VDI and Windows Virtual Desktop sessions.</span></span> <span data-ttu-id="91f5a-109">Según las necesidades de la organización, es posible que deba implementar sesiones de VDI o Windows Virtual Desktop para ayudar a los empleados a tener acceso a datos corporativos y aplicaciones desde un dispositivo no administrado, una ubicación remota o un escenario similar.</span><span class="sxs-lookup"><span data-stu-id="91f5a-109">Depending on your organization's needs, you might need to implement VDI or Windows Virtual Desktop sessions to help your employees access corporate data and apps from an unmanaged device, remote location, or similar scenario.</span></span> <span data-ttu-id="91f5a-110">Con Microsoft Defender para endpoint, puede supervisar estas máquinas virtuales en busca de actividad anómala.</span><span class="sxs-lookup"><span data-stu-id="91f5a-110">With Microsoft Defender for Endpoint, you can monitor these virtual machines for anomalous activity.</span></span>

 ## <a name="before-you-begin"></a><span data-ttu-id="91f5a-111">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="91f5a-111">Before you begin</span></span>
<span data-ttu-id="91f5a-112">Familiarícese con las [consideraciones para VDI no persistente.](/microsoft-365/security/defender-endpoint/configure-endpoints-vdi#onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices-1)</span><span class="sxs-lookup"><span data-stu-id="91f5a-112">Familiarize yourself with the [considerations for non-persistent VDI](/microsoft-365/security/defender-endpoint/configure-endpoints-vdi#onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices-1).</span></span> <span data-ttu-id="91f5a-113">Aunque [Windows Virtual Desktop](/azure/virtual-desktop/overview) no proporciona opciones de no persistencia, sí proporciona formas de usar una imagen de Windows dorada que se puede usar para aprovisionar nuevos hosts y volver a implementar máquinas.</span><span class="sxs-lookup"><span data-stu-id="91f5a-113">While [Windows Virtual Desktop](/azure/virtual-desktop/overview) doesn't provide non-persistence options, it does provide ways to use a golden Windows image that can be used to provision new hosts and redeploy machines.</span></span> <span data-ttu-id="91f5a-114">Esto aumenta la inestabilidad en el entorno y, por lo tanto, afecta a las entradas que se crean y mantienen en el portal de Microsoft Defender para endpoints, lo que potencialmente reduce la visibilidad de los analistas de seguridad.</span><span class="sxs-lookup"><span data-stu-id="91f5a-114">This increases volatility in the environment and thus impacts what entries are created and maintained in the Microsoft Defender for Endpoint portal, potentially reducing visibility for your security analysts.</span></span>

> [!NOTE]
> <span data-ttu-id="91f5a-115">Según la elección del método de incorporación, los dispositivos pueden aparecer en el portal de Microsoft Defender para endpoints como:</span><span class="sxs-lookup"><span data-stu-id="91f5a-115">Depending on your choice of onboarding method, devices can appear in Microsoft Defender for Endpoint portal as either:</span></span> 
> - <span data-ttu-id="91f5a-116">Entrada única para cada escritorio virtual</span><span class="sxs-lookup"><span data-stu-id="91f5a-116">Single entry for each virtual desktop</span></span> 
> - <span data-ttu-id="91f5a-117">Varias entradas para cada escritorio virtual</span><span class="sxs-lookup"><span data-stu-id="91f5a-117">Multiple entries for each virtual desktop</span></span> 

<span data-ttu-id="91f5a-118">Microsoft recomienda la incorporación Windows Escritorio virtual como una única entrada por escritorio virtual.</span><span class="sxs-lookup"><span data-stu-id="91f5a-118">Microsoft recommends onboarding Windows Virtual Desktop as a single entry per virtual desktop.</span></span> <span data-ttu-id="91f5a-119">Esto garantiza que la experiencia de investigación en el portal de puntos de conexión de Microsoft Defender se encuentra en el contexto de un dispositivo basado en el nombre del equipo.</span><span class="sxs-lookup"><span data-stu-id="91f5a-119">This ensures that the investigation experience in the Microsoft Defender Endpoint portal is in the context of one device based on the machine name.</span></span> <span data-ttu-id="91f5a-120">Las organizaciones que suelen eliminar y volver a implementar hosts WVD deben considerar encarecidamente el uso de este método, ya que impide que se cree varios objetos para la misma máquina en el portal de Microsoft Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="91f5a-120">Organizations that frequently delete and redeploy WVD hosts should strongly consider using this method as it prevents multiple objects for the same machine from being created in the Microsoft Defender for Endpoint portal.</span></span> <span data-ttu-id="91f5a-121">Esto puede provocar confusión al investigar incidentes.</span><span class="sxs-lookup"><span data-stu-id="91f5a-121">This can lead to confusion when investigating incidents.</span></span> <span data-ttu-id="91f5a-122">Para entornos de prueba o no volátiles, puede optar por elegir de forma diferente.</span><span class="sxs-lookup"><span data-stu-id="91f5a-122">For test or non-volatile environments, you may opt to choose differently.</span></span> 

<span data-ttu-id="91f5a-123">Microsoft recomienda agregar el script de incorporación de Microsoft Defender para endpoint a la imagen dorada de WVD.</span><span class="sxs-lookup"><span data-stu-id="91f5a-123">Microsoft recommends adding the Microsoft Defender for Endpoint onboarding script to the WVD golden image.</span></span> <span data-ttu-id="91f5a-124">De esta forma, puede asegurarse de que este script de incorporación se ejecute inmediatamente al primer arranque.</span><span class="sxs-lookup"><span data-stu-id="91f5a-124">This way, you can be sure that this onboarding script runs immediately at first boot.</span></span> <span data-ttu-id="91f5a-125">Se ejecuta como un script de inicio al inicio en todas las máquinas WVD aprovisionadas desde la imagen dorada de WVD.</span><span class="sxs-lookup"><span data-stu-id="91f5a-125">It's executed as a startup script at first boot on all the WVD machines that are provisioned from the WVD golden image.</span></span> <span data-ttu-id="91f5a-126">Sin embargo, si usa una de las imágenes de la galería sin modificaciones, coloque el script en una ubicación compartida y llámelo desde una directiva de grupo local o de dominio.</span><span class="sxs-lookup"><span data-stu-id="91f5a-126">However, if you're using one of the gallery images without modification, place the script in a shared location and call it from either local or domain group policy.</span></span> 

> [!NOTE]
> <span data-ttu-id="91f5a-127">La ubicación y configuración del script de inicio de incorporación de VDI en la imagen dorada de WVD lo configura como un script de inicio que se ejecuta cuando se inicia WVD.</span><span class="sxs-lookup"><span data-stu-id="91f5a-127">The placement and configuration of the VDI onboarding startup script on the WVD golden image configures it as a startup script that runs when the WVD starts.</span></span> <span data-ttu-id="91f5a-128">NO se recomienda incorporar la imagen dorada de WVD real.</span><span class="sxs-lookup"><span data-stu-id="91f5a-128">It's NOT recommended to onboard the actual WVD golden image.</span></span> <span data-ttu-id="91f5a-129">Otra consideración es el método usado para ejecutar el script.</span><span class="sxs-lookup"><span data-stu-id="91f5a-129">Another consideration is the method used to run the script.</span></span> <span data-ttu-id="91f5a-130">Debe ejecutarse lo antes posible en el proceso de inicio o aprovisionamiento para reducir el tiempo entre la máquina que está disponible para recibir sesiones y la incorporación del dispositivo al servicio.</span><span class="sxs-lookup"><span data-stu-id="91f5a-130">It should run as early in the startup/provisioning process as possible to reduce the time between the machine being available to receive sessions and the device onboarding to the service.</span></span> <span data-ttu-id="91f5a-131">En los escenarios siguientes, 1 & 2 tienen esto en cuenta.</span><span class="sxs-lookup"><span data-stu-id="91f5a-131">Below scenarios 1 & 2 take this into account.</span></span>

### <a name="scenarios"></a><span data-ttu-id="91f5a-132">Escenarios</span><span class="sxs-lookup"><span data-stu-id="91f5a-132">Scenarios</span></span>
<span data-ttu-id="91f5a-133">Hay varias formas de incorporar un equipo host WVD:</span><span class="sxs-lookup"><span data-stu-id="91f5a-133">There are several ways to onboard a WVD host machine:</span></span>

- <span data-ttu-id="91f5a-134">Ejecute el script en la imagen dorada (o desde una ubicación compartida) durante el inicio.</span><span class="sxs-lookup"><span data-stu-id="91f5a-134">Run the script in the golden image (or from a shared location) during startup.</span></span>
- <span data-ttu-id="91f5a-135">Use una herramienta de administración para ejecutar el script.</span><span class="sxs-lookup"><span data-stu-id="91f5a-135">Use a management tool to run the script.</span></span>

#### <a name="scenario-1-using-local-group-policy"></a><span data-ttu-id="91f5a-136">*Escenario 1: Uso de la directiva de grupo local*</span><span class="sxs-lookup"><span data-stu-id="91f5a-136">*Scenario 1: Using local group policy*</span></span>
<span data-ttu-id="91f5a-137">Este escenario requiere colocar el script en una imagen dorada y usa la directiva de grupo local para ejecutarse al principio del proceso de arranque.</span><span class="sxs-lookup"><span data-stu-id="91f5a-137">This scenario requires placing the script in a golden image and uses local group policy to run early in the boot process.</span></span>

<span data-ttu-id="91f5a-138">Use las instrucciones de [Incorporación de dispositivos VDI de](configure-endpoints-vdi.md#onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices-1)infraestructura de escritorio virtual no persistente.</span><span class="sxs-lookup"><span data-stu-id="91f5a-138">Use the instructions in [Onboard non-persistent virtual desktop infrastructure VDI devices](configure-endpoints-vdi.md#onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices-1).</span></span>

<span data-ttu-id="91f5a-139">Siga las instrucciones de una sola entrada para cada dispositivo.</span><span class="sxs-lookup"><span data-stu-id="91f5a-139">Follow the instructions for a single entry for each device.</span></span>

#### <a name="scenario-2-using-domain-group-policy"></a><span data-ttu-id="91f5a-140">*Escenario 2: Uso de la directiva de grupo de dominio*</span><span class="sxs-lookup"><span data-stu-id="91f5a-140">*Scenario 2: Using domain group policy*</span></span>
<span data-ttu-id="91f5a-141">Este escenario usa un script ubicado centralmente y lo ejecuta mediante una directiva de grupo basada en dominio.</span><span class="sxs-lookup"><span data-stu-id="91f5a-141">This scenario uses a centrally located script and runs it using a domain-based group policy.</span></span> <span data-ttu-id="91f5a-142">También puede colocar el script en la imagen dorada y ejecutarlo de la misma manera.</span><span class="sxs-lookup"><span data-stu-id="91f5a-142">You can also place the script in the golden image and run it in the same way.</span></span>

<span data-ttu-id="91f5a-143">**Descargue el WindowsDefenderATPOnboardingPackage.zip desde el Centro de seguridad Windows Defender de seguridad**</span><span class="sxs-lookup"><span data-stu-id="91f5a-143">**Download the WindowsDefenderATPOnboardingPackage.zip file from the Windows Defender Security Center**</span></span>

1. <span data-ttu-id="91f5a-144">Abra el archivo de configuración .zip VDI (WindowsDefenderATPOnboardingPackage.zip)</span><span class="sxs-lookup"><span data-stu-id="91f5a-144">Open the VDI configuration package .zip file (WindowsDefenderATPOnboardingPackage.zip)</span></span>  

    1. <span data-ttu-id="91f5a-145">En el panel Centro de seguridad de Microsoft Defender navegación, **seleccione Configuración**  >  **Incorporación**.</span><span class="sxs-lookup"><span data-stu-id="91f5a-145">In the Microsoft Defender Security Center navigation pane, select **Settings** > **Onboarding**.</span></span> 
    1. <span data-ttu-id="91f5a-146">Seleccione Windows 10 como sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="91f5a-146">Select Windows 10 as the operating system.</span></span> 
    1. <span data-ttu-id="91f5a-147">En el **campo Método de** implementación, seleccione Scripts de incorporación de VDI para puntos de conexión no persistentes.</span><span class="sxs-lookup"><span data-stu-id="91f5a-147">In the **Deployment method** field, select VDI onboarding scripts for non-persistent endpoints.</span></span> 
    1. <span data-ttu-id="91f5a-148">Haga **clic en Descargar paquete** y guarde el .zip archivo.</span><span class="sxs-lookup"><span data-stu-id="91f5a-148">Click **Download package** and save the .zip file.</span></span> 

2. <span data-ttu-id="91f5a-149">Extraiga el contenido del archivo .zip a una ubicación compartida de solo lectura a la que pueda tener acceso el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="91f5a-149">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the device.</span></span> <span data-ttu-id="91f5a-150">Debe tener una carpeta denominada **OptionalParamsPolicy** y los archivos **WindowsDefenderATPOnboardingScript.cmd** **yOnboard-NonPersistentMachine.ps1**.</span><span class="sxs-lookup"><span data-stu-id="91f5a-150">You should have a folder called **OptionalParamsPolicy** and the files **WindowsDefenderATPOnboardingScript.cmd** and **Onboard-NonPersistentMachine.ps1**.</span></span>

<span data-ttu-id="91f5a-151">**Usar la consola de administración de directivas de grupo para ejecutar el script cuando se inicia la máquina virtual**</span><span class="sxs-lookup"><span data-stu-id="91f5a-151">**Use Group Policy management console to run the script when the virtual machine starts**</span></span>

1. <span data-ttu-id="91f5a-152">Abra la Consola de administración de directivas de grupo (GPMC), haga clic con el botón secundario en el objeto de directiva de grupo (GPO) que desea configurar y haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="91f5a-152">Open the Group Policy Management Console (GPMC), right-click the Group Policy Object (GPO) you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="91f5a-153">En el Editor de administración de directivas de grupo, vaya a **Configuración** del equipo Preferencias \>  \> **configuración Configuración del panel de control .**</span><span class="sxs-lookup"><span data-stu-id="91f5a-153">In the Group Policy Management Editor, go to **Computer configuration** \> **Preferences** \> **Control panel settings**.</span></span> 

3. <span data-ttu-id="91f5a-154">Haga clic con el botón secundario en **Tareas programadas,** haga clic en **Nuevo** y, a continuación, haga clic en Tarea **inmediata** (al menos Windows 7).</span><span class="sxs-lookup"><span data-stu-id="91f5a-154">Right-click **Scheduled tasks**, click **New**, and then click **Immediate Task** (At least Windows 7).</span></span> 

4. <span data-ttu-id="91f5a-155">En la ventana Tarea que se abre, vaya a la **pestaña General.** En **Opciones de seguridad,** **haga clic en Cambiar usuario o grupo** y escriba SISTEMA.</span><span class="sxs-lookup"><span data-stu-id="91f5a-155">In the Task window that opens, go to the **General** tab. Under **Security options** click **Change User or Group** and type SYSTEM.</span></span> <span data-ttu-id="91f5a-156">Haga **clic en Comprobar nombres** y, a continuación, en Aceptar.</span><span class="sxs-lookup"><span data-stu-id="91f5a-156">Click **Check Names** and then click OK.</span></span> <span data-ttu-id="91f5a-157">NT AUTHORITY\SYSTEM aparece como la cuenta de usuario en la que se ejecutará la tarea.</span><span class="sxs-lookup"><span data-stu-id="91f5a-157">NT AUTHORITY\SYSTEM appears as the user account the task will run as.</span></span> 

5. <span data-ttu-id="91f5a-158">Seleccione **Ejecutar si el usuario ha iniciado sesión o no** y active la casilla Ejecutar con **privilegios** más altos.</span><span class="sxs-lookup"><span data-stu-id="91f5a-158">Select **Run whether user is logged on or not** and check the **Run with highest privileges** check box.</span></span> 

6. <span data-ttu-id="91f5a-159">Vaya a la **pestaña Acciones** y haga clic **en Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="91f5a-159">Go to the **Actions** tab and click **New**.</span></span> <span data-ttu-id="91f5a-160">Asegúrese de **que Iniciar un programa** está seleccionado en el campo Acción.</span><span class="sxs-lookup"><span data-stu-id="91f5a-160">Ensure that **Start a program** is selected in the Action field.</span></span> <span data-ttu-id="91f5a-161">Especifique lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="91f5a-161">Enter the following:</span></span> 

   `Action = "Start a program"`

   `Program/Script = C:\WINDOWS\system32\WindowsPowerShell\v1.0\powershell.exe`

   `Add Arguments (optional) = -ExecutionPolicy Bypass -command "& \\Path\To\Onboard-NonPersistentMachine.ps1"`

   <span data-ttu-id="91f5a-162">A **continuación, seleccione Aceptar** y cierre las ventanas GPMC abiertas.</span><span class="sxs-lookup"><span data-stu-id="91f5a-162">Then select **OK** and close any open GPMC windows.</span></span>

#### <a name="scenario-3-onboarding-using-management-tools"></a><span data-ttu-id="91f5a-163">*Escenario 3: Incorporación con herramientas de administración*</span><span class="sxs-lookup"><span data-stu-id="91f5a-163">*Scenario 3: Onboarding using management tools*</span></span>

<span data-ttu-id="91f5a-164">Si planea administrar las máquinas con una herramienta de administración, puede incorporar dispositivos con Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="91f5a-164">If you plan to manage your machines using a management tool, you can onboard devices with Microsoft Endpoint Configuration Manager.</span></span>

<span data-ttu-id="91f5a-165">Para obtener más información, vea [Onboard Windows 10 devices using Configuration Manager](configure-endpoints-sccm.md).</span><span class="sxs-lookup"><span data-stu-id="91f5a-165">For more information, see [Onboard Windows 10 devices using Configuration Manager](configure-endpoints-sccm.md).</span></span>

> [!WARNING]
> <span data-ttu-id="91f5a-166">Si tienes previsto usar reglas de reducción de superficie de [ataque,](attack-surface-reduction.md)ten en cuenta que no se debe usar la regla " Bloquear creaciones de proceso que se originen a partir de comandos[PSExec](attack-surface-reduction.md#block-process-creations-originating-from-psexec-and-wmi-commands)y WMI", ya que dicha regla es incompatible con la administración a través de Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="91f5a-166">If you plan to use [Attack Surface reduction Rules](attack-surface-reduction.md), note that the rule “[Block process creations originating from PSExec and WMI commands](attack-surface-reduction.md#block-process-creations-originating-from-psexec-and-wmi-commands)" should not be used, because that rule is incompatible with management through Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="91f5a-167">La regla bloquea los comandos WMI que el cliente de Configuration Manager usa para funcionar correctamente.</span><span class="sxs-lookup"><span data-stu-id="91f5a-167">The rule blocks WMI commands that the Configuration Manager client uses to function correctly.</span></span> 

> [!TIP]
> <span data-ttu-id="91f5a-168">Después de incorporar el dispositivo, puedes elegir ejecutar una prueba de detección para comprobar que el dispositivo está correctamente incorporado al servicio.</span><span class="sxs-lookup"><span data-stu-id="91f5a-168">After onboarding the device, you can choose to run a detection test to verify that the device is properly onboarded to the service.</span></span> <span data-ttu-id="91f5a-169">Para obtener más información, consulta [Ejecutar una prueba de detección en un dispositivo de Microsoft Defender para endpoint](run-detection-test.md)recién incorporado.</span><span class="sxs-lookup"><span data-stu-id="91f5a-169">For more information, see [Run a detection test on a newly onboarded Microsoft Defender for Endpoint device](run-detection-test.md).</span></span> 

#### <a name="tagging-your-machines-when-building-your-golden-image"></a><span data-ttu-id="91f5a-170">Etiquetar las máquinas al crear la imagen dorada</span><span class="sxs-lookup"><span data-stu-id="91f5a-170">Tagging your machines when building your golden image</span></span> 

<span data-ttu-id="91f5a-171">Como parte de la incorporación, es posible que quieras establecer una etiqueta de máquina para diferenciar los equipos WVD más fácilmente en el Centro de seguridad de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="91f5a-171">As part of your onboarding, you may want to consider setting a machine tag to can differentiate WVD machines more easily in the Microsoft Security Center.</span></span> <span data-ttu-id="91f5a-172">Para obtener más información, consulta [Agregar etiquetas de dispositivo estableciendo un valor de clave del Registro.](machine-tags.md#add-device-tags-by-setting-a-registry-key-value)</span><span class="sxs-lookup"><span data-stu-id="91f5a-172">For more information, see [Add device tags by setting a registry key value](machine-tags.md#add-device-tags-by-setting-a-registry-key-value).</span></span> 

#### <a name="other-recommended-configuration-settings"></a><span data-ttu-id="91f5a-173">Otras opciones de configuración recomendadas</span><span class="sxs-lookup"><span data-stu-id="91f5a-173">Other recommended configuration settings</span></span> 

<span data-ttu-id="91f5a-174">Al crear la imagen dorada, es posible que también quieras configurar la configuración de protección inicial.</span><span class="sxs-lookup"><span data-stu-id="91f5a-174">When building your golden image, you may want to configure initial protection settings as well.</span></span> <span data-ttu-id="91f5a-175">Para obtener más información, vea [Otras opciones de configuración recomendadas.](configure-endpoints-gp.md#other-recommended-configuration-settings)</span><span class="sxs-lookup"><span data-stu-id="91f5a-175">For more information, see [Other recommended configuration settings](configure-endpoints-gp.md#other-recommended-configuration-settings).</span></span> 

<span data-ttu-id="91f5a-176">Además, si usa perfiles de usuario FSlogix, se recomienda excluir los siguientes archivos de la protección siempre en uso:</span><span class="sxs-lookup"><span data-stu-id="91f5a-176">Also, if you're using FSlogix user profiles, we recommend you exclude the following files from always-on protection:</span></span> 

<span data-ttu-id="91f5a-177">**Excluir archivos:**</span><span class="sxs-lookup"><span data-stu-id="91f5a-177">**Exclude Files:**</span></span> 

`%ProgramFiles%\FSLogix\Apps\frxdrv.sys`

`%ProgramFiles%\FSLogix\Apps\frxdrvvt.sys`

`%ProgramFiles%\FSLogix\Apps\frxccd.sys`

`%TEMP%\*.VHD`

`%TEMP%\*.VHDX`

`%Windir%\TEMP\*.VHD`

`%Windir%\TEMP\*.VHDX`

`\\storageaccount.file.core.windows.net\share\*\*.VHD`

`\\storageaccount.file.core.windows.net\share\*\*.VHDX`

<span data-ttu-id="91f5a-178">**Excluir procesos:**</span><span class="sxs-lookup"><span data-stu-id="91f5a-178">**Exclude Processes:**</span></span>

`%ProgramFiles%\FSLogix\Apps\frxccd.exe`

`%ProgramFiles%\FSLogix\Apps\frxccds.exe`

`%ProgramFiles%\FSLogix\Apps\frxsvc.exe`

#### <a name="licensing-requirements"></a><span data-ttu-id="91f5a-179">Requisitos de licencias</span><span class="sxs-lookup"><span data-stu-id="91f5a-179">Licensing requirements</span></span> 

<span data-ttu-id="91f5a-180">Nota sobre las licencias Windows 10 Enterprise: cuando se usa una sesión múltiple, según sus requisitos, puede elegir que todos los usuarios tengan licencia a través de Microsoft Defender para Endpoint (por usuario), Windows Enterprise E5, Microsoft 365 Security o Microsoft 365 E5, o que la máquina virtual tenga licencia a través de Azure Defender.</span><span class="sxs-lookup"><span data-stu-id="91f5a-180">Note on licensing: When using Windows 10 Enterprise multi-session, depending on your requirements, you can choose to either have all users licensed through Microsoft Defender for Endpoint (per user), Windows Enterprise E5, Microsoft 365 Security, or Microsoft 365 E5, or have the VM licensed through Azure Defender.</span></span>
<span data-ttu-id="91f5a-181">Los requisitos de licencia para Microsoft Defender para el punto de conexión se pueden encontrar en: [Requisitos de licencias](minimum-requirements.md#licensing-requirements).</span><span class="sxs-lookup"><span data-stu-id="91f5a-181">Licensing requirements for Microsoft Defender for endpoint can be found at: [Licensing requirements](minimum-requirements.md#licensing-requirements).</span></span>
