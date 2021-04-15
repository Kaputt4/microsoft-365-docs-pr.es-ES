---
title: Recopilar datos de diagnóstico del antivirus de Microsoft Defender
description: Usar una herramienta para recopilar datos para solucionar problemas de Antivirus de Microsoft Defender
keywords: troubleshoot, error, fix, update compliance, oms, monitor, report, Microsoft Defender av, group policy object, setting, diagnostic data
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/29/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: d74a8921af677f6ed66580bd00830440d59cf1aa
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764728"
---
# <a name="collect-microsoft-defender-av-diagnostic-data"></a><span data-ttu-id="a8c95-104">Recopilar datos de diagnóstico antivirus de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="a8c95-104">Collect Microsoft Defender AV diagnostic data</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="a8c95-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="a8c95-105">**Applies to:**</span></span>

- [<span data-ttu-id="a8c95-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="a8c95-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="a8c95-107">En este artículo se describe cómo recopilar datos de diagnóstico que pueden usar los equipos de soporte técnico e ingeniería de Microsoft para ayudar a solucionar problemas que puedan surgir al usar el antivirus de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="a8c95-107">This article describes how to collect diagnostic data that can be used by Microsoft support and engineering teams to help troubleshoot issues you might encounter when using the Microsoft Defender AV.</span></span>

> [!NOTE]
> <span data-ttu-id="a8c95-108">Como parte del proceso de investigación o respuesta, puedes recopilar un paquete de investigación desde un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a8c95-108">As part of the investigation or response process, you can collect an investigation package from a device.</span></span> <span data-ttu-id="a8c95-109">Este es el modo: [Recopilar paquete de investigación de dispositivos](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#collect-investigation-package-from-devices).</span><span class="sxs-lookup"><span data-stu-id="a8c95-109">Here's how: [Collect investigation package from devices](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#collect-investigation-package-from-devices).</span></span>

<span data-ttu-id="a8c95-110">En al menos dos dispositivos que están experimentando el mismo problema, obtenga el archivo de diagnóstico .cab siguiendo los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="a8c95-110">On at least two devices that are experiencing the same issue, obtain the .cab diagnostic file by taking the following steps:</span></span>

1. <span data-ttu-id="a8c95-111">Abra una versión de nivel de administrador del símbolo del sistema de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="a8c95-111">Open an administrator-level version of the command prompt as follows:</span></span>

    <span data-ttu-id="a8c95-112">a.</span><span class="sxs-lookup"><span data-stu-id="a8c95-112">a.</span></span> <span data-ttu-id="a8c95-113">Abra el **menú** Inicio.</span><span class="sxs-lookup"><span data-stu-id="a8c95-113">Open the **Start** menu.</span></span>

    <span data-ttu-id="a8c95-114">b.</span><span class="sxs-lookup"><span data-stu-id="a8c95-114">b.</span></span> <span data-ttu-id="a8c95-115">Escriba **cmd**.</span><span class="sxs-lookup"><span data-stu-id="a8c95-115">Type **cmd**.</span></span> <span data-ttu-id="a8c95-116">Haga clic con el botón secundario en **el símbolo del sistema** y haga clic en Ejecutar como **administrador.**</span><span class="sxs-lookup"><span data-stu-id="a8c95-116">Right-click on **Command Prompt** and click **Run as administrator**.</span></span>

    <span data-ttu-id="a8c95-117">c.</span><span class="sxs-lookup"><span data-stu-id="a8c95-117">c.</span></span> <span data-ttu-id="a8c95-118">Escriba las credenciales de administrador o apruebe el mensaje.</span><span class="sxs-lookup"><span data-stu-id="a8c95-118">Enter administrator credentials or approve the prompt.</span></span>

2. <span data-ttu-id="a8c95-119">Vaya al directorio de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="a8c95-119">Navigate to the Microsoft Defender directory.</span></span> <span data-ttu-id="a8c95-120">El valor predeterminado es `C:\Program Files\Windows Defender`</span><span class="sxs-lookup"><span data-stu-id="a8c95-120">By default, this is `C:\Program Files\Windows Defender`.</span></span>

> [!NOTE]
> <span data-ttu-id="a8c95-121">Si está ejecutando una versión actualizada [de Microsoft Defender Platform,](https://support.microsoft.com/help/4052623/update-for-microsoft-defender-antimalware-platform)ejecute `MpCmdRun` desde la siguiente ubicación: `C:\ProgramData\Microsoft\Windows Defender\Platform\<version>` .</span><span class="sxs-lookup"><span data-stu-id="a8c95-121">If you're running an [updated Microsoft Defender Platform version](https://support.microsoft.com/help/4052623/update-for-microsoft-defender-antimalware-platform), please run `MpCmdRun` from the following location: `C:\ProgramData\Microsoft\Windows Defender\Platform\<version>`.</span></span>

3. <span data-ttu-id="a8c95-122">Escriba el siguiente comando y, a continuación, presione **ENTRAR**</span><span class="sxs-lookup"><span data-stu-id="a8c95-122">Type the following command, and then press **Enter**</span></span>  

    ```Dos
    mpcmdrun.exe -GetFiles
    ```
  
4. <span data-ttu-id="a8c95-123">Se generará un archivo .cab que contenga varios registros de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="a8c95-123">A .cab file will be generated that contains various diagnostic logs.</span></span> <span data-ttu-id="a8c95-124">La ubicación del archivo se especificará en la salida del símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="a8c95-124">The location of the file will be specified in the output in the command prompt.</span></span> <span data-ttu-id="a8c95-125">De forma predeterminada, la ubicación es `C:\ProgramData\Microsoft\Microsoft Defender\Support\MpSupportFiles.cab` .</span><span class="sxs-lookup"><span data-stu-id="a8c95-125">By default, the location is `C:\ProgramData\Microsoft\Microsoft Defender\Support\MpSupportFiles.cab`.</span></span>

> [!NOTE]
> <span data-ttu-id="a8c95-126">Para redirigir el archivo cab a una ruta de acceso o recurso compartido UNC diferente, use el siguiente comando: `mpcmdrun.exe -GetFiles -SupportLogLocation <path>`</span><span class="sxs-lookup"><span data-stu-id="a8c95-126">To redirect the cab file to a a different path or UNC share, use the following command: `mpcmdrun.exe -GetFiles -SupportLogLocation <path>`</span></span>  <br/><span data-ttu-id="a8c95-127">Para obtener más información, vea [Redirect diagnostic data to a UNC share](#redirect-diagnostic-data-to-a-unc-share).</span><span class="sxs-lookup"><span data-stu-id="a8c95-127">For more information, see [Redirect diagnostic data to a UNC share](#redirect-diagnostic-data-to-a-unc-share).</span></span>

5. <span data-ttu-id="a8c95-128">Copie estos archivos .cab en una ubicación a la que pueda tener acceso el soporte técnico de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a8c95-128">Copy these .cab files to a location that can be accessed by Microsoft support.</span></span> <span data-ttu-id="a8c95-129">Un ejemplo podría ser una carpeta de OneDrive protegida con contraseña que puede compartir con nosotros.</span><span class="sxs-lookup"><span data-stu-id="a8c95-129">An example could be a password-protected OneDrive folder that you can share with us.</span></span>

> [!NOTE]
><span data-ttu-id="a8c95-130">Si tiene un problema con el cumplimiento <a href="mailto:ucsupport@microsoft.com?subject=WDAV assessment issue&body=I%20am%20encountering%20the%20following%20issue%20when%20using%20Windows%20Defender%20AV%20in%20Update%20Compliance%3a%20%0d%0aI%20have%20provided%20at%20least%202%20support%20.cab%20files%20at%20the%20following%20location%3a%20%3Caccessible%20share%2c%20including%20access%20details%20such%20as%20password%3E%0d%0aMy%20OMS%20workspace%20ID%20is%3a%20%0d%0aPlease%20contact%20me%20at%3a"></a>de la actualización, envíe un correo electrónico con la plantilla de correo electrónico de soporte técnico actualizar cumplimiento y rellene la plantilla con la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="a8c95-130">If you have a problem with Update compliance, send an email using the <a href="mailto:ucsupport@microsoft.com?subject=WDAV assessment issue&body=I%20am%20encountering%20the%20following%20issue%20when%20using%20Windows%20Defender%20AV%20in%20Update%20Compliance%3a%20%0d%0aI%20have%20provided%20at%20least%202%20support%20.cab%20files%20at%20the%20following%20location%3a%20%3Caccessible%20share%2c%20including%20access%20details%20such%20as%20password%3E%0d%0aMy%20OMS%20workspace%20ID%20is%3a%20%0d%0aPlease%20contact%20me%20at%3a">Update Compliance support email template</a>, and fill out the template with the following information:</span></span>
>```
> I am encountering the following issue when using Microsoft Defender Antivirus in Update Compliance:
> I have provided at least 2 support .cab files at the following location:  
> <accessible share, including access details such as password>
>
>    My OMS workspace ID is:
>
>    Please contact me at:

## <a name="redirect-diagnostic-data-to-a-unc-share"></a><span data-ttu-id="a8c95-131">Redirigir datos de diagnóstico a un recurso compartido UNC</span><span class="sxs-lookup"><span data-stu-id="a8c95-131">Redirect diagnostic data to a UNC share</span></span>
<span data-ttu-id="a8c95-132">Para recopilar datos de diagnóstico en un repositorio central, puede especificar el parámetro SupportLogLocation.</span><span class="sxs-lookup"><span data-stu-id="a8c95-132">To collect diagnostic data on a central repository, you can specify the SupportLogLocation parameter.</span></span>

```Dos
mpcmdrun.exe -GetFiles -SupportLogLocation <path>
```

<span data-ttu-id="a8c95-133">Copia los datos de diagnóstico en la ruta de acceso especificada.</span><span class="sxs-lookup"><span data-stu-id="a8c95-133">Copies the diagnostic data to the specified path.</span></span> <span data-ttu-id="a8c95-134">Si no se especifica la ruta de acceso, los datos de diagnóstico se copiarán en la ubicación especificada en la configuración de ubicación del registro de soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="a8c95-134">If the path is not specified, the diagnostic data will be copied to the location specified in the Support Log Location Configuration.</span></span>

<span data-ttu-id="a8c95-135">Cuando se usa el parámetro SupportLogLocation, se creará una estructura de carpetas como la siguiente en la ruta de destino:</span><span class="sxs-lookup"><span data-stu-id="a8c95-135">When the SupportLogLocation parameter is used, a folder structure like as follows will be created in the destination path:</span></span>

```Dos
<path>\<MMDD>\MpSupport-<hostname>-<HHMM>.cab
```

| <span data-ttu-id="a8c95-136">campo</span><span class="sxs-lookup"><span data-stu-id="a8c95-136">field</span></span>  | <span data-ttu-id="a8c95-137">Descripción</span><span class="sxs-lookup"><span data-stu-id="a8c95-137">Description</span></span>   |
|:----|:----|
| <span data-ttu-id="a8c95-138">path</span><span class="sxs-lookup"><span data-stu-id="a8c95-138">path</span></span> | <span data-ttu-id="a8c95-139">Ruta de acceso especificada en la línea de comandos o recuperada de la configuración</span><span class="sxs-lookup"><span data-stu-id="a8c95-139">The path as specified on the command line or retrieved from configuration</span></span>
| <span data-ttu-id="a8c95-140">MMDD</span><span class="sxs-lookup"><span data-stu-id="a8c95-140">MMDD</span></span> | <span data-ttu-id="a8c95-141">Mes y día en que se recopilaron los datos de diagnóstico (por ejemplo, 0530)</span><span class="sxs-lookup"><span data-stu-id="a8c95-141">Month and day when the diagnostic data was collected (for example, 0530)</span></span>
| <span data-ttu-id="a8c95-142">nombre de host</span><span class="sxs-lookup"><span data-stu-id="a8c95-142">hostname</span></span> | <span data-ttu-id="a8c95-143">Nombre de host del dispositivo en el que se recopilaron los datos de diagnóstico</span><span class="sxs-lookup"><span data-stu-id="a8c95-143">The hostname of the device on which the diagnostic data was collected</span></span>
| <span data-ttu-id="a8c95-144">HHMM</span><span class="sxs-lookup"><span data-stu-id="a8c95-144">HHMM</span></span> | <span data-ttu-id="a8c95-145">Horas y minutos cuando se recopilaron los datos de diagnóstico (por ejemplo, 1422)</span><span class="sxs-lookup"><span data-stu-id="a8c95-145">Hours and minutes when the diagnostic data was collected (for example, 1422)</span></span>

> [!NOTE]
> <span data-ttu-id="a8c95-146">Al usar un recurso compartido de archivos, asegúrese de que la cuenta usada para recopilar el paquete de diagnóstico tenga acceso de escritura al recurso compartido.</span><span class="sxs-lookup"><span data-stu-id="a8c95-146">When using a file share please make sure that account used to collect the diagnostic package has write access to the share.</span></span>  

## <a name="specify-location-where-diagnostic-data-is-created"></a><span data-ttu-id="a8c95-147">Especificar la ubicación donde se crean los datos de diagnóstico</span><span class="sxs-lookup"><span data-stu-id="a8c95-147">Specify location where diagnostic data is created</span></span>

<span data-ttu-id="a8c95-148">También puede especificar dónde se creará el archivo .cab de diagnóstico mediante un objeto de directiva de grupo (GPO).</span><span class="sxs-lookup"><span data-stu-id="a8c95-148">You can also specify where the diagnostic .cab file will be created using a Group Policy Object (GPO).</span></span> 

1. <span data-ttu-id="a8c95-149">Abra el Editor de directivas de grupo local y busque el GPO SupportLogLocation en: `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender\SupportLogLocation`</span><span class="sxs-lookup"><span data-stu-id="a8c95-149">Open the Local Group Policy Editor and find the SupportLogLocation GPO at: `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender\SupportLogLocation`</span></span>
   
1. <span data-ttu-id="a8c95-150">Seleccione **Definir la ruta de acceso del directorio para copiar los archivos de registro de soporte técnico.**</span><span class="sxs-lookup"><span data-stu-id="a8c95-150">Select **Define the directory path to copy support log files**.</span></span>

    ![Captura de pantalla del editor de directivas de grupo local](images/GPO1-SupportLogLocationDefender.png)  
        
     ![Captura de pantalla de definición de ruta de acceso para la configuración de archivos de registro](images/GPO2-SupportLogLocationGPPage.png)  
3. <span data-ttu-id="a8c95-153">Dentro del editor de directivas, seleccione **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="a8c95-153">Inside the policy editor, select **Enabled**.</span></span>
       
4. <span data-ttu-id="a8c95-154">Especifique la ruta de acceso del directorio en la que desea copiar los archivos de registro de soporte técnico en el **campo** Opciones.</span><span class="sxs-lookup"><span data-stu-id="a8c95-154">Specify the directory path where you want to copy the support log files in the **Options** field.</span></span>
     <span data-ttu-id="a8c95-155">![Captura de pantalla de configuración personalizada de ruta de acceso de directorio habilitada](images/GPO3-SupportLogLocationGPPageEnabledExample.png)</span><span class="sxs-lookup"><span data-stu-id="a8c95-155">![Screenshot of Enabled directory path custom setting](images/GPO3-SupportLogLocationGPPageEnabledExample.png)</span></span> 
5. <span data-ttu-id="a8c95-156">Seleccione **Aceptar** o **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="a8c95-156">Select **OK** or **Apply**.</span></span>

## <a name="see-also"></a><span data-ttu-id="a8c95-157">Vea también</span><span class="sxs-lookup"><span data-stu-id="a8c95-157">See also</span></span>

- [<span data-ttu-id="a8c95-158">Solucionar problemas de informes de Antivirus de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="a8c95-158">Troubleshoot Microsoft Defender Antivirus reporting</span></span>](troubleshoot-reporting.md)