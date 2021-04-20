---
title: Incorporación de dispositivos Windows 10 a Microsoft Defender para el punto de conexión a través de la directiva de grupo
description: Usa la directiva de grupo para implementar el paquete de configuración en dispositivos Windows 10 para que se incorpore al servicio.
keywords: configurar dispositivos mediante directiva de grupo, administración de dispositivos, configurar dispositivos de Windows ATP, incorporar Microsoft Defender para dispositivos de punto de conexión, directiva de grupo
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
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: b839cf204e8ab042e0c88a8f8c48df79770e7b4f
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893642"
---
# <a name="onboard-windows-10-devices-using-group-policy"></a><span data-ttu-id="1ca50-104">Incorporación de dispositivos Windows 10 con la directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="1ca50-104">Onboard Windows 10 devices using Group Policy</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1ca50-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="1ca50-105">**Applies to:**</span></span>

- <span data-ttu-id="1ca50-106">Directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="1ca50-106">Group Policy</span></span>
- [<span data-ttu-id="1ca50-107">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="1ca50-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="1ca50-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1ca50-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="1ca50-109">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="1ca50-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="1ca50-110">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="1ca50-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configureendpointsgp-abovefoldlink)


> [!NOTE]
> <span data-ttu-id="1ca50-111">Para usar las actualizaciones de directiva de grupo (GP) para implementar el paquete, debes estar en Windows Server 2008 R2 o posterior.</span><span class="sxs-lookup"><span data-stu-id="1ca50-111">To use Group Policy (GP) updates to deploy the package, you must be on Windows Server 2008 R2 or later.</span></span>
> 
> <span data-ttu-id="1ca50-112">Para Windows Server 2019, es posible que deba reemplazar NT AUTHORITY\Well-Known-System-Account por NT AUTHORITY\SYSTEM del archivo XML que crea la preferencia de directiva de grupo.</span><span class="sxs-lookup"><span data-stu-id="1ca50-112">For Windows Server 2019, you may need to replace NT AUTHORITY\Well-Known-System-Account with NT AUTHORITY\SYSTEM of the XML file that the Group Policy preference creates.</span></span>

## <a name="onboard-devices-using-group-policy"></a><span data-ttu-id="1ca50-113">Incorporar dispositivos con la directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="1ca50-113">Onboard devices using Group Policy</span></span>

<span data-ttu-id="1ca50-114">[![Imagen del PDF que muestra las distintas rutas de implementación](images/onboard-gp.png)](images/onboard-gp.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="1ca50-114">[![Image of the PDF showing the various deployment paths](images/onboard-gp.png)](images/onboard-gp.png#lightbox)</span></span>

<span data-ttu-id="1ca50-115">Consulte el [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  o  [Visio para](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) ver las distintas rutas de acceso en la implementación de Defender para endpoint.</span><span class="sxs-lookup"><span data-stu-id="1ca50-115">Check out the [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  or  [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) to see the various paths in deploying Defender for Endpoint.</span></span> 



1. <span data-ttu-id="1ca50-116">Abra el archivo .zip del paquete de configuración de GP (*WindowsDefenderATPOnboardingPackage.zip*) que descargó del Asistente para incorporación de servicios.</span><span class="sxs-lookup"><span data-stu-id="1ca50-116">Open the GP configuration package .zip file (*WindowsDefenderATPOnboardingPackage.zip*) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="1ca50-117">También puede obtener el paquete del Centro de seguridad [de Microsoft Defender:](https://securitycenter.windows.com/)</span><span class="sxs-lookup"><span data-stu-id="1ca50-117">You can also get the package from [Microsoft Defender Security Center](https://securitycenter.windows.com/):</span></span>
 
    1. <span data-ttu-id="1ca50-118">En el panel de navegación, seleccione **Configuración**  >  **incorporación**.</span><span class="sxs-lookup"><span data-stu-id="1ca50-118">In the navigation pane, select **Settings** > **Onboarding**.</span></span>

    1. <span data-ttu-id="1ca50-119">Selecciona Windows 10 como sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="1ca50-119">Select Windows 10 as the operating system.</span></span>
    
    1. <span data-ttu-id="1ca50-120">En el **campo Método de** implementación, seleccione Directiva de **grupo**.</span><span class="sxs-lookup"><span data-stu-id="1ca50-120">In the **Deployment method** field, select **Group policy**.</span></span>
    
    1. <span data-ttu-id="1ca50-121">Haga **clic en Descargar paquete** y guarde el archivo .zip.</span><span class="sxs-lookup"><span data-stu-id="1ca50-121">Click **Download package** and save the .zip file.</span></span>

2. <span data-ttu-id="1ca50-122">Extrae el contenido del archivo .zip en una ubicación compartida de solo lectura a la que pueda tener acceso el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="1ca50-122">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the device.</span></span> <span data-ttu-id="1ca50-123">Debe tener una carpeta denominada *OptionalParamsPolicy* y el archivo *WindowsDefenderATPOnboardingScript.cmd*.</span><span class="sxs-lookup"><span data-stu-id="1ca50-123">You should have a folder called *OptionalParamsPolicy* and the file *WindowsDefenderATPOnboardingScript.cmd*.</span></span>

3. <span data-ttu-id="1ca50-124">Abra la [Consola de administración de directivas de](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) grupo (GPMC), haga clic con el botón secundario en el objeto de directiva de grupo (GPO) que desea configurar y haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="1ca50-124">Open the [Group Policy Management Console](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC), right-click the Group Policy Object (GPO) you want to configure and click **Edit**.</span></span>

4. <span data-ttu-id="1ca50-125">En el **Editor de administración de directivas de** grupo, vaya a Configuración **del** equipo , luego Preferencias **y,** a continuación, **Configuración del panel de control.**</span><span class="sxs-lookup"><span data-stu-id="1ca50-125">In the **Group Policy Management Editor**, go to **Computer configuration**, then **Preferences**, and then **Control panel settings**.</span></span>

5. <span data-ttu-id="1ca50-126">Haga clic con el botón secundario en **Tareas programadas**, elija **Nuevo** y, a continuación, haga clic en Tarea inmediata **(al menos Windows 7).**</span><span class="sxs-lookup"><span data-stu-id="1ca50-126">Right-click **Scheduled tasks**, point to **New**, and then click **Immediate Task (At least Windows 7)**.</span></span>

6. <span data-ttu-id="1ca50-127">En la **ventana Tarea** que se abre, vaya a la **pestaña General.** En **Opciones de seguridad,** **haga clic en Cambiar usuario o grupo** y escriba SISTEMA y, a continuación, haga clic en Comprobar nombres **y, a** continuación, en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1ca50-127">In the **Task** window that opens, go to the **General** tab. Under **Security options** click **Change User or Group** and type SYSTEM and then click **Check Names** then **OK**.</span></span> <span data-ttu-id="1ca50-128">NT AUTHORITY\SYSTEM aparece como la cuenta de usuario en la que se ejecutará la tarea.</span><span class="sxs-lookup"><span data-stu-id="1ca50-128">NT AUTHORITY\SYSTEM appears as the user account the task will run as.</span></span>

7. <span data-ttu-id="1ca50-129">Seleccione **Ejecutar si el usuario ha iniciado sesión o no** y active la casilla Ejecutar con **privilegios** más altos.</span><span class="sxs-lookup"><span data-stu-id="1ca50-129">Select **Run whether user is logged on or not** and check the **Run with highest privileges** check box.</span></span>

8. <span data-ttu-id="1ca50-130">Vaya a la **pestaña Acciones** y haga clic **en Nuevo...** Asegúrese de **que Iniciar un programa** está seleccionado en el **campo** Acción.</span><span class="sxs-lookup"><span data-stu-id="1ca50-130">Go to the **Actions** tab and click **New...** Ensure that **Start a program** is selected in the **Action** field.</span></span> <span data-ttu-id="1ca50-131">Escriba el nombre de archivo y la ubicación del archivo *compartido WindowsDefenderATPOnboardingScript.cmd.*</span><span class="sxs-lookup"><span data-stu-id="1ca50-131">Enter the file name and location of the shared *WindowsDefenderATPOnboardingScript.cmd* file.</span></span>

9. <span data-ttu-id="1ca50-132">Haga **clic en Aceptar** y cierre las ventanas GPMC abiertas.</span><span class="sxs-lookup"><span data-stu-id="1ca50-132">Click **OK** and close any open GPMC windows.</span></span>

>[!TIP]
> <span data-ttu-id="1ca50-133">Después de incorporar el dispositivo, puedes elegir ejecutar una prueba de detección para comprobar que el dispositivo está correctamente incorporado al servicio.</span><span class="sxs-lookup"><span data-stu-id="1ca50-133">After onboarding the device, you can choose to run a detection test to verify that the device is properly onboarded to the service.</span></span> <span data-ttu-id="1ca50-134">Para obtener más información, consulta [Ejecutar una prueba de detección en un dispositivo defender para endpoint](run-detection-test.md)recién incorporado.</span><span class="sxs-lookup"><span data-stu-id="1ca50-134">For more information, see [Run a detection test on a newly onboarded Defender for Endpoint device](run-detection-test.md).</span></span>

## <a name="additional-defender-for-endpoint-configuration-settings"></a><span data-ttu-id="1ca50-135">Opciones adicionales de configuración de Defender para puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="1ca50-135">Additional Defender for Endpoint configuration settings</span></span>
<span data-ttu-id="1ca50-136">Para cada dispositivo, puedes especificar si se pueden recopilar muestras del dispositivo cuando se realiza una solicitud a través del Centro de seguridad de Microsoft Defender para enviar un archivo para un análisis profundo.</span><span class="sxs-lookup"><span data-stu-id="1ca50-136">For each device, you can state whether samples can be collected from the device when a request is made through Microsoft Defender Security Center to submit a file for deep analysis.</span></span>

<span data-ttu-id="1ca50-137">Puede usar la directiva de grupo (GP) para configurar opciones, como las opciones para el uso compartido de muestras usado en la característica de análisis profundo.</span><span class="sxs-lookup"><span data-stu-id="1ca50-137">You can use Group Policy (GP) to configure settings, such as settings for the sample sharing used in the deep analysis feature.</span></span>

### <a name="configure-sample-collection-settings"></a><span data-ttu-id="1ca50-138">Configuración de la colección de ejemplo</span><span class="sxs-lookup"><span data-stu-id="1ca50-138">Configure sample collection settings</span></span>
1.  <span data-ttu-id="1ca50-139">En el dispositivo de administración de GP, copie los siguientes archivos del paquete de configuración:</span><span class="sxs-lookup"><span data-stu-id="1ca50-139">On your GP management device, copy the following files from the configuration package:</span></span>

    - <span data-ttu-id="1ca50-140">Copiar _AtpConfiguration.admx_ en _C: \\ \\ PolicyDefinitions de Windows_</span><span class="sxs-lookup"><span data-stu-id="1ca50-140">Copy _AtpConfiguration.admx_ into _C:\\Windows\\PolicyDefinitions_</span></span>

    - <span data-ttu-id="1ca50-141">Copiar _AtpConfiguration.adml_ en _C: \\ \\ PolicyDefinitions de Windows \\ en-US_</span><span class="sxs-lookup"><span data-stu-id="1ca50-141">Copy _AtpConfiguration.adml_ into _C:\\Windows\\PolicyDefinitions\\en-US_</span></span>

    <span data-ttu-id="1ca50-142">Si usa un Almacén central para plantillas administrativas de directiva [de](https://support.microsoft.com/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra)grupo, copie los siguientes archivos del paquete de configuración:</span><span class="sxs-lookup"><span data-stu-id="1ca50-142">If you are using a [Central Store for Group Policy Administrative Templates](https://support.microsoft.com/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra), copy the following files from the configuration package:</span></span>
    
    - <span data-ttu-id="1ca50-143">Copiar _AtpConfiguration.admx_ en _\\ \\ \<forest.root\> \\ SysVol \\ \<forest.root\> \\ Policies \\ PolicyDefinitions_</span><span class="sxs-lookup"><span data-stu-id="1ca50-143">Copy _AtpConfiguration.admx_ into _\\\\\<forest.root\>\\SysVol\\\<forest.root\>\\Policies\\PolicyDefinitions_</span></span>

    - <span data-ttu-id="1ca50-144">Copiar _AtpConfiguration.adml_ en _\\ \\ \<forest.root\> \\ SysVol \\ \<forest.root\> \\ Policies \\ PolicyDefinitions \\ en-US_</span><span class="sxs-lookup"><span data-stu-id="1ca50-144">Copy _AtpConfiguration.adml_ into _\\\\\<forest.root\>\\SysVol\\\<forest.root\>\\Policies\\PolicyDefinitions\\en-US_</span></span>

2.  <span data-ttu-id="1ca50-145">Abra la [Consola de administración de directivas de grupo,](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11)haga clic con el botón secundario en el GPO que desea configurar y haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="1ca50-145">Open the [Group Policy Management Console](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11), right-click the GPO you want to configure and click **Edit**.</span></span>

3.  <span data-ttu-id="1ca50-146">En el **Editor de administración de directivas de** grupo, vaya a Configuración del **equipo**.</span><span class="sxs-lookup"><span data-stu-id="1ca50-146">In the **Group Policy Management Editor**, go to **Computer configuration**.</span></span>

4.  <span data-ttu-id="1ca50-147">Haga **clic en Directivas** y, a **continuación, en Plantillas administrativas.**</span><span class="sxs-lookup"><span data-stu-id="1ca50-147">Click **Policies**, then **Administrative templates**.</span></span>

5.  <span data-ttu-id="1ca50-148">Haga clic **en Componentes de Windows** **y, a continuación, Windows Defender ATP**.</span><span class="sxs-lookup"><span data-stu-id="1ca50-148">Click **Windows components** and then **Windows Defender ATP**.</span></span>

6.  <span data-ttu-id="1ca50-149">Elige habilitar o deshabilitar el uso compartido de muestras desde tus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="1ca50-149">Choose to enable or disable sample sharing from your devices.</span></span>

>[!NOTE]
> <span data-ttu-id="1ca50-150">Si no establece un valor, el valor predeterminado es habilitar la colección de muestras.</span><span class="sxs-lookup"><span data-stu-id="1ca50-150">If you don't set a value, the default value is to enable sample collection.</span></span>


## <a name="other-recommended-configuration-settings"></a><span data-ttu-id="1ca50-151">Otras opciones de configuración recomendadas</span><span class="sxs-lookup"><span data-stu-id="1ca50-151">Other recommended configuration settings</span></span>

### <a name="update-endpoint-protection-configuration"></a><span data-ttu-id="1ca50-152">Actualizar la configuración de protección de puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="1ca50-152">Update endpoint protection configuration</span></span>

<span data-ttu-id="1ca50-153">Después de configurar el script de incorporación, siga editando la misma directiva de grupo para agregar configuraciones de protección de extremos.</span><span class="sxs-lookup"><span data-stu-id="1ca50-153">After configuring the onboarding script, continue editing the same group policy to add endpoint protection configurations.</span></span> <span data-ttu-id="1ca50-154">Realice ediciones de directivas de grupo desde un sistema que ejecute Windows 10 o Server 2019 para asegurarse de que tiene todas las funcionalidades necesarias de Antivirus de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="1ca50-154">Perform group policy edits from a system running Windows 10 or Server 2019 to ensure you have all of the required Microsoft Defender Antivirus capabilities.</span></span> <span data-ttu-id="1ca50-155">Es posible que deba cerrar y volver a abrir el objeto de directiva de grupo para registrar las opciones de configuración de Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="1ca50-155">You may need to close and reopen the group policy object to register the Defender ATP configuration settings.</span></span>

<span data-ttu-id="1ca50-156">Todas las directivas se encuentran en `Computer Configuration\Policies\Administrative Templates` .</span><span class="sxs-lookup"><span data-stu-id="1ca50-156">All policies are located under `Computer Configuration\Policies\Administrative Templates`.</span></span>

<span data-ttu-id="1ca50-157">**Ubicación de la directiva:** \Componentes de Windows\Windows Defender ATP</span><span class="sxs-lookup"><span data-stu-id="1ca50-157">**Policy location:** \Windows Components\Windows Defender ATP</span></span>

<span data-ttu-id="1ca50-158">Policy</span><span class="sxs-lookup"><span data-stu-id="1ca50-158">Policy</span></span> | <span data-ttu-id="1ca50-159">Setting</span><span class="sxs-lookup"><span data-stu-id="1ca50-159">Setting</span></span> 
:---|:---
<span data-ttu-id="1ca50-160">Enable\Disable Sample (colección)</span><span class="sxs-lookup"><span data-stu-id="1ca50-160">Enable\Disable Sample collection</span></span>|   <span data-ttu-id="1ca50-161">Habilitado: "Habilitar la colección de muestras en máquinas" activada</span><span class="sxs-lookup"><span data-stu-id="1ca50-161">Enabled - "Enable sample collection on machines" checked</span></span>

<br/>

<span data-ttu-id="1ca50-162">**Ubicación de la directiva:**  \Componentes de Windows\Windows Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="1ca50-162">**Policy location:**  \Windows Components\Windows Defender Antivirus</span></span>

<span data-ttu-id="1ca50-163">Policy</span><span class="sxs-lookup"><span data-stu-id="1ca50-163">Policy</span></span> | <span data-ttu-id="1ca50-164">Setting</span><span class="sxs-lookup"><span data-stu-id="1ca50-164">Setting</span></span> 
:---|:---
<span data-ttu-id="1ca50-165">Configurar la detección para aplicaciones potencialmente no deseadas</span><span class="sxs-lookup"><span data-stu-id="1ca50-165">Configure detection for potentially unwanted applications</span></span> | <span data-ttu-id="1ca50-166">Enabled, Block</span><span class="sxs-lookup"><span data-stu-id="1ca50-166">Enabled, Block</span></span>

<br/>

<span data-ttu-id="1ca50-167">**Ubicación de la directiva:** \Componentes de Windows\Windows Defender Antivirus\MAPS</span><span class="sxs-lookup"><span data-stu-id="1ca50-167">**Policy location:** \Windows Components\Windows Defender Antivirus\MAPS</span></span>

<span data-ttu-id="1ca50-168">Policy</span><span class="sxs-lookup"><span data-stu-id="1ca50-168">Policy</span></span> | <span data-ttu-id="1ca50-169">Setting</span><span class="sxs-lookup"><span data-stu-id="1ca50-169">Setting</span></span> 
:---|:---
<span data-ttu-id="1ca50-170">Unirse a Microsoft MAPS</span><span class="sxs-lookup"><span data-stu-id="1ca50-170">Join Microsoft MAPS</span></span> | <span data-ttu-id="1ca50-171">Mapas avanzados habilitados</span><span class="sxs-lookup"><span data-stu-id="1ca50-171">Enabled, Advanced MAPS</span></span>
<span data-ttu-id="1ca50-172">Enviar ejemplos de archivos cuando sea necesario realizar análisis adicionales</span><span class="sxs-lookup"><span data-stu-id="1ca50-172">Send file samples when further analysis is required</span></span> | <span data-ttu-id="1ca50-173">Habilitado, Enviar muestras seguras</span><span class="sxs-lookup"><span data-stu-id="1ca50-173">Enabled, Send safe samples</span></span>

<br/>

<span data-ttu-id="1ca50-174">**Ubicación de la directiva:** \Componentes de Windows\Windows Defender Antivirus\Protección en tiempo real</span><span class="sxs-lookup"><span data-stu-id="1ca50-174">**Policy location:** \Windows Components\Windows Defender Antivirus\Real-time Protection</span></span>

<span data-ttu-id="1ca50-175">Policy</span><span class="sxs-lookup"><span data-stu-id="1ca50-175">Policy</span></span> | <span data-ttu-id="1ca50-176">Setting</span><span class="sxs-lookup"><span data-stu-id="1ca50-176">Setting</span></span> 
:---|:---
<span data-ttu-id="1ca50-177">Desactivar la protección en tiempo real</span><span class="sxs-lookup"><span data-stu-id="1ca50-177">Turn off real-time protection</span></span>|<span data-ttu-id="1ca50-178">Deshabilitada</span><span class="sxs-lookup"><span data-stu-id="1ca50-178">Disabled</span></span>
<span data-ttu-id="1ca50-179">Activar la supervisión del comportamiento</span><span class="sxs-lookup"><span data-stu-id="1ca50-179">Turn on behavior monitoring</span></span>|<span data-ttu-id="1ca50-180">Habilitado</span><span class="sxs-lookup"><span data-stu-id="1ca50-180">Enabled</span></span>
<span data-ttu-id="1ca50-181">Examinar todos los archivos y datos adjuntos descargados</span><span class="sxs-lookup"><span data-stu-id="1ca50-181">Scan all downloaded files and attachments</span></span>|<span data-ttu-id="1ca50-182">Habilitado</span><span class="sxs-lookup"><span data-stu-id="1ca50-182">Enabled</span></span>
<span data-ttu-id="1ca50-183">Supervisar la actividad de archivos y programas en el equipo</span><span class="sxs-lookup"><span data-stu-id="1ca50-183">Monitor file and program activity on your computer</span></span>|<span data-ttu-id="1ca50-184">Habilitado</span><span class="sxs-lookup"><span data-stu-id="1ca50-184">Enabled</span></span>

<br/>

<span data-ttu-id="1ca50-185">**Ubicación de la directiva:**  \Componentes de Windows\Windows Defender Antivirus\Scan</span><span class="sxs-lookup"><span data-stu-id="1ca50-185">**Policy location:**  \Windows Components\Windows Defender Antivirus\Scan</span></span>

<span data-ttu-id="1ca50-186">Estas opciones configuran exámenes periódicos del extremo.</span><span class="sxs-lookup"><span data-stu-id="1ca50-186">These settings configure periodic scans of the endpoint.</span></span> <span data-ttu-id="1ca50-187">Se recomienda realizar un examen rápido semanal, lo que permite el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="1ca50-187">We recommend performing a weekly quick scan, performance permitting.</span></span>

<span data-ttu-id="1ca50-188">Policy</span><span class="sxs-lookup"><span data-stu-id="1ca50-188">Policy</span></span> | <span data-ttu-id="1ca50-189">Setting</span><span class="sxs-lookup"><span data-stu-id="1ca50-189">Setting</span></span> 
:---|:---
<span data-ttu-id="1ca50-190">Compruebe la inteligencia de seguridad de virus y spyware más reciente antes de ejecutar un examen programado</span><span class="sxs-lookup"><span data-stu-id="1ca50-190">Check for the latest virus and spyware security intelligence before running a scheduled scan</span></span> |<span data-ttu-id="1ca50-191">Habilitado</span><span class="sxs-lookup"><span data-stu-id="1ca50-191">Enabled</span></span>


<br/>

<span data-ttu-id="1ca50-192">**Ubicación de la directiva:** \Componentes de Windows\Windows Defender Antivirus\Windows Defender Protección contra vulnerabilidades de seguridad\Reducción de superficie de ataque</span><span class="sxs-lookup"><span data-stu-id="1ca50-192">**Policy location:** \Windows Components\Windows Defender Antivirus\Windows Defender Exploit Guard\Attack Surface Reduction</span></span>

<span data-ttu-id="1ca50-193">Obtener la lista actual de GUID de reducción de superficie de ataque de [Personalizar reglas de reducción de superficie de ataque](customize-attack-surface-reduction.md)</span><span class="sxs-lookup"><span data-stu-id="1ca50-193">Get the current list of attack surface reduction GUIDs from [Customize attack surface reduction rules](customize-attack-surface-reduction.md)</span></span>

1. <span data-ttu-id="1ca50-194">Abre la **directiva Configurar reducción de superficie de ataque.**</span><span class="sxs-lookup"><span data-stu-id="1ca50-194">Open the **Configure Attack Surface Reduction** policy.</span></span>

1. <span data-ttu-id="1ca50-195">Seleccione **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="1ca50-195">Select **Enabled**.</span></span>

1. <span data-ttu-id="1ca50-196">Seleccione el **botón Mostrar.**</span><span class="sxs-lookup"><span data-stu-id="1ca50-196">Select the **Show** button.</span></span>

1. <span data-ttu-id="1ca50-197">Agregue cada GUID en el **campo Nombre de** valor con un valor de 2.</span><span class="sxs-lookup"><span data-stu-id="1ca50-197">Add each GUID in the **Value Name** field with a Value of 2.</span></span>

   <span data-ttu-id="1ca50-198">Esto configurará cada uno solo para auditoría.</span><span class="sxs-lookup"><span data-stu-id="1ca50-198">This will set each up for audit only.</span></span>

   ![Imagen de configuración de reducción de superficie de ataque](images/asr-guid.png)



<span data-ttu-id="1ca50-200">Policy</span><span class="sxs-lookup"><span data-stu-id="1ca50-200">Policy</span></span> | <span data-ttu-id="1ca50-201">Setting</span><span class="sxs-lookup"><span data-stu-id="1ca50-201">Setting</span></span> 
:---|:---
<span data-ttu-id="1ca50-202">Configurar acceso controlado a carpetas</span><span class="sxs-lookup"><span data-stu-id="1ca50-202">Configure Controlled folder access</span></span>| <span data-ttu-id="1ca50-203">Habilitado, modo auditoría</span><span class="sxs-lookup"><span data-stu-id="1ca50-203">Enabled, Audit Mode</span></span>



## <a name="offboard-devices-using-group-policy"></a><span data-ttu-id="1ca50-204">Dispositivos offboard con directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="1ca50-204">Offboard devices using Group Policy</span></span>
<span data-ttu-id="1ca50-205">Por motivos de seguridad, el paquete usado para dispositivos offboard expirará 30 días después de la fecha en que se descargó.</span><span class="sxs-lookup"><span data-stu-id="1ca50-205">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="1ca50-206">Se rechazarán los paquetes de offboarding expirados enviados a un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="1ca50-206">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="1ca50-207">Al descargar un paquete de offboarding, se le notificará la fecha de expiración de los paquetes y también se incluirá en el nombre del paquete.</span><span class="sxs-lookup"><span data-stu-id="1ca50-207">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="1ca50-208">Las directivas de incorporación y de incorporación no deben implementarse en el mismo dispositivo al mismo tiempo, de lo contrario esto provocará colisiones impredecibles.</span><span class="sxs-lookup"><span data-stu-id="1ca50-208">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

1. <span data-ttu-id="1ca50-209">Obtener el paquete de offboarding del Centro de [seguridad de Microsoft Defender:](https://securitycenter.windows.com/)</span><span class="sxs-lookup"><span data-stu-id="1ca50-209">Get the offboarding package from [Microsoft Defender Security Center](https://securitycenter.windows.com/):</span></span>

    1. <span data-ttu-id="1ca50-210">En el panel de navegación, seleccione **Configuración**  >  **de offboarding**.</span><span class="sxs-lookup"><span data-stu-id="1ca50-210">In the navigation pane, select **Settings** > **Offboarding**.</span></span>

    1. <span data-ttu-id="1ca50-211">Selecciona Windows 10 como sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="1ca50-211">Select Windows 10 as the operating system.</span></span>
    
    1. <span data-ttu-id="1ca50-212">En el **campo Método de** implementación, seleccione Directiva de **grupo**.</span><span class="sxs-lookup"><span data-stu-id="1ca50-212">In the **Deployment method** field, select **Group policy**.</span></span>

    1. <span data-ttu-id="1ca50-213">Haga **clic en Descargar paquete** y guarde el archivo .zip.</span><span class="sxs-lookup"><span data-stu-id="1ca50-213">Click **Download package** and save the .zip file.</span></span>

2. <span data-ttu-id="1ca50-214">Extrae el contenido del archivo .zip en una ubicación compartida de solo lectura a la que pueda tener acceso el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="1ca50-214">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the device.</span></span> <span data-ttu-id="1ca50-215">Debe tener un archivo denominado *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*.</span><span class="sxs-lookup"><span data-stu-id="1ca50-215">You should have a file named *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*.</span></span>

3. <span data-ttu-id="1ca50-216">Abra la [Consola de administración de directivas de](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) grupo (GPMC), haga clic con el botón secundario en el objeto de directiva de grupo (GPO) que desea configurar y haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="1ca50-216">Open the [Group Policy Management Console](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC), right-click the Group Policy Object (GPO) you want to configure and click **Edit**.</span></span>

4. <span data-ttu-id="1ca50-217">En el **Editor de administración de directivas de** grupo, vaya a Configuración del **equipo, preferencias** **y,** a continuación, **configuración del panel de control.**</span><span class="sxs-lookup"><span data-stu-id="1ca50-217">In the **Group Policy Management Editor**, go to **Computer configuration,** then **Preferences**, and then **Control panel settings**.</span></span>

5. <span data-ttu-id="1ca50-218">Haga clic con el botón secundario **en Tareas programadas**, **elija Nuevo** y, a continuación, haga clic en **Tarea inmediata**.</span><span class="sxs-lookup"><span data-stu-id="1ca50-218">Right-click **Scheduled tasks**, point to **New**, and then click **Immediate task**.</span></span>

6. <span data-ttu-id="1ca50-219">En la **ventana Tarea** que se abre, vaya a la **pestaña General.** Elija la cuenta de usuario del SISTEMA local (BUILTIN\SYSTEM) en **Opciones de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="1ca50-219">In the **Task** window that opens, go to the **General** tab. Choose the local SYSTEM user account (BUILTIN\SYSTEM) under **Security options**.</span></span>

7. <span data-ttu-id="1ca50-220">Seleccione **Ejecutar si el usuario ha iniciado sesión o no** y active la casilla Ejecutar con **privilegios** más altos.</span><span class="sxs-lookup"><span data-stu-id="1ca50-220">Select **Run whether user is logged on or not** and check the **Run with highest privileges** check-box.</span></span>

8. <span data-ttu-id="1ca50-221">Vaya a la **pestaña Acciones** y haga clic **en Nuevo...**. Asegúrese de **que Iniciar un programa** está seleccionado en el **campo** Acción.</span><span class="sxs-lookup"><span data-stu-id="1ca50-221">Go to the **Actions** tab and click **New...**. Ensure that **Start a program** is selected in the **Action** field.</span></span> <span data-ttu-id="1ca50-222">Escriba el nombre de archivo y la ubicación del archivo  *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd* compartido.</span><span class="sxs-lookup"><span data-stu-id="1ca50-222">Enter the file name and location of the shared  *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd* file.</span></span>

9. <span data-ttu-id="1ca50-223">Haga **clic en Aceptar** y cierre las ventanas GPMC abiertas.</span><span class="sxs-lookup"><span data-stu-id="1ca50-223">Click **OK** and close any open GPMC windows.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1ca50-224">Offboarding hace que el dispositivo deje de enviar datos del sensor al portal, pero los datos del dispositivo, incluida la referencia a las alertas que ha tenido, se conservarán durante un máximo de 6 meses.</span><span class="sxs-lookup"><span data-stu-id="1ca50-224">Offboarding causes the device to stop sending sensor data to the portal but data from the device, including reference to any alerts it has had will be retained for up to 6 months.</span></span>


## <a name="monitor-device-configuration"></a><span data-ttu-id="1ca50-225">Supervisar la configuración del dispositivo</span><span class="sxs-lookup"><span data-stu-id="1ca50-225">Monitor device configuration</span></span>
<span data-ttu-id="1ca50-226">Con la directiva de grupo no hay una opción para supervisar la implementación de directivas en los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="1ca50-226">With Group Policy there isn’t an option to monitor deployment of policies on the devices.</span></span> <span data-ttu-id="1ca50-227">La supervisión se puede realizar directamente en el portal o mediante las distintas herramientas de implementación.</span><span class="sxs-lookup"><span data-stu-id="1ca50-227">Monitoring can be done directly on the portal, or by using the different deployment tools.</span></span>

## <a name="monitor-devices-using-the-portal"></a><span data-ttu-id="1ca50-228">Supervisar dispositivos con el portal</span><span class="sxs-lookup"><span data-stu-id="1ca50-228">Monitor devices using the portal</span></span>
1. <span data-ttu-id="1ca50-229">Vaya al [Centro de seguridad de Microsoft Defender](https://securitycenter.windows.com/).</span><span class="sxs-lookup"><span data-stu-id="1ca50-229">Go to [Microsoft Defender Security Center](https://securitycenter.windows.com/).</span></span>
2. <span data-ttu-id="1ca50-230">Haga clic **en Lista dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="1ca50-230">Click **Devices list**.</span></span>
3. <span data-ttu-id="1ca50-231">Compruebe que aparecen dispositivos.</span><span class="sxs-lookup"><span data-stu-id="1ca50-231">Verify that devices are appearing.</span></span>

> [!NOTE]
> <span data-ttu-id="1ca50-232">Los dispositivos pueden tardar varios días en aparecer en la **lista Dispositivos.**</span><span class="sxs-lookup"><span data-stu-id="1ca50-232">It can take several days for devices to start showing on the **Devices list**.</span></span> <span data-ttu-id="1ca50-233">Esto incluye el tiempo que tardan las directivas en distribuirse en el dispositivo, el tiempo que tarda antes de que el usuario inicie sesión y el tiempo que tarda el punto de conexión en iniciar la presentación de informes.</span><span class="sxs-lookup"><span data-stu-id="1ca50-233">This includes the time it takes for the policies to be distributed to the device, the time it takes before the user logs on, and the time it takes for the endpoint to start reporting.</span></span>


## <a name="related-topics"></a><span data-ttu-id="1ca50-234">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="1ca50-234">Related topics</span></span>
- [<span data-ttu-id="1ca50-235">Incorporación de dispositivos Windows 10 con Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="1ca50-235">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md)
- [<span data-ttu-id="1ca50-236">Incorporar dispositivos Windows 10 con herramientas de Administración de dispositivos móviles</span><span class="sxs-lookup"><span data-stu-id="1ca50-236">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](configure-endpoints-mdm.md)
- [<span data-ttu-id="1ca50-237">Incorporar dispositivos Windows 10 mediante un script local</span><span class="sxs-lookup"><span data-stu-id="1ca50-237">Onboard Windows 10 devices using a local script</span></span>](configure-endpoints-script.md)
- [<span data-ttu-id="1ca50-238">Incorporar dispositivos de infraestructura de escritorio virtual (VDI) no persistente</span><span class="sxs-lookup"><span data-stu-id="1ca50-238">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](configure-endpoints-vdi.md)
- [<span data-ttu-id="1ca50-239">Ejecutar una prueba de detección en un Microsoft Defender recién incorporado para dispositivos de punto de conexión</span><span class="sxs-lookup"><span data-stu-id="1ca50-239">Run a detection test on a newly onboarded Microsoft Defender for Endpoint devices</span></span>](run-detection-test.md)
- [<span data-ttu-id="1ca50-240">Solucionar problemas de incorporación de puntos de conexión de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="1ca50-240">Troubleshoot Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
