---
title: Investigar entidades en dispositivos con respuesta en directo en Microsoft Defender para endpoint
description: Accede a un dispositivo mediante una conexión segura del shell remoto para realizar trabajos de investigación y realizar acciones de respuesta inmediatas en un dispositivo en tiempo real.
keywords: remoto, shell, conexión, live, response, en tiempo real, comando, script, remediate, hunt, export, log, drop, download, file,
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
ms.technology: mde
ms.openlocfilehash: fc1c1e0d3f68016651c04521e04ce348e5ab9a65
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "52246470"
---
# <a name="investigate-entities-on-devices-using-live-response"></a><span data-ttu-id="2867c-104">Investigar entidades en dispositivos con respuesta en directo</span><span class="sxs-lookup"><span data-stu-id="2867c-104">Investigate entities on devices using live response</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2867c-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="2867c-105">**Applies to:**</span></span>
- [<span data-ttu-id="2867c-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="2867c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="2867c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2867c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="2867c-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="2867c-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="2867c-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="2867c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="2867c-110">La respuesta en directo proporciona a los equipos de operaciones de seguridad acceso instantáneo a un dispositivo (también denominado máquina) mediante una conexión remota del shell.</span><span class="sxs-lookup"><span data-stu-id="2867c-110">Live response gives security operations teams instantaneous access to a device (also referred to as a machine) using a remote shell connection.</span></span> <span data-ttu-id="2867c-111">Esto le da la capacidad de realizar un trabajo de investigación en profundidad y tomar acciones de respuesta inmediatas para contener rápidamente las amenazas identificadas, en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="2867c-111">This gives you the power to do in-depth investigative work and take immediate response actions to promptly contain identified threats—in real time.</span></span> 

<span data-ttu-id="2867c-112">La respuesta activa está diseñada para mejorar las investigaciones, ya que permite al equipo de operaciones de seguridad recopilar datos forenses, ejecutar scripts, enviar entidades sospechosas para su análisis, corregir amenazas y buscar proactivamente amenazas emergentes.</span><span class="sxs-lookup"><span data-stu-id="2867c-112">Live response is designed to enhance investigations by enabling your security operations team to collect forensic data, run scripts, send suspicious entities for analysis, remediate threats, and proactively hunt for emerging threats.</span></span><br/><br/>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4qLUW]

<span data-ttu-id="2867c-113">Con la respuesta en directo, los analistas pueden realizar todas las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="2867c-113">With live response, analysts can do all of the following tasks:</span></span>
- <span data-ttu-id="2867c-114">Ejecute comandos básicos y avanzados para realizar trabajos de investigación en un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2867c-114">Run basic and advanced commands to do investigative work on a device.</span></span>
- <span data-ttu-id="2867c-115">Descargue archivos como ejemplos de malware y resultados de scripts de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2867c-115">Download files such as malware samples and outcomes of PowerShell scripts.</span></span>
- <span data-ttu-id="2867c-116">Descargar archivos en segundo plano (¡nuevo!).</span><span class="sxs-lookup"><span data-stu-id="2867c-116">Download files in the background (new!).</span></span>
- <span data-ttu-id="2867c-117">Upload un script de PowerShell o ejecutable a la biblioteca y ejecutarlo en un dispositivo desde un nivel de inquilino.</span><span class="sxs-lookup"><span data-stu-id="2867c-117">Upload a PowerShell script or executable to the library and run it on a device from a tenant level.</span></span>
- <span data-ttu-id="2867c-118">Realizar o deshacer acciones de corrección.</span><span class="sxs-lookup"><span data-stu-id="2867c-118">Take or undo remediation actions.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="2867c-119">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="2867c-119">Before you begin</span></span>

<span data-ttu-id="2867c-120">Antes de iniciar una sesión en un dispositivo, asegúrate de cumplir los siguientes requisitos:</span><span class="sxs-lookup"><span data-stu-id="2867c-120">Before you can initiate a session on a device, make sure you fulfill the following requirements:</span></span>

- <span data-ttu-id="2867c-121">**Compruebe que está ejecutando una versión compatible de Windows**.</span><span class="sxs-lookup"><span data-stu-id="2867c-121">**Verify that you're running a supported version of Windows**.</span></span> <br/>
<span data-ttu-id="2867c-122">Los dispositivos deben ejecutar una de las siguientes versiones de Windows</span><span class="sxs-lookup"><span data-stu-id="2867c-122">Devices must be running one of the following versions of Windows</span></span>

  - <span data-ttu-id="2867c-123">**Windows 10**</span><span class="sxs-lookup"><span data-stu-id="2867c-123">**Windows 10**</span></span>
    - <span data-ttu-id="2867c-124">[Versión 1909](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1909) o posterior</span><span class="sxs-lookup"><span data-stu-id="2867c-124">[Version 1909](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1909) or later</span></span>  
    - <span data-ttu-id="2867c-125">[Versión 1903](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1903) con [KB4515384](https://support.microsoft.com/en-us/help/4515384/windows-10-update-kb4515384)</span><span class="sxs-lookup"><span data-stu-id="2867c-125">[Version 1903](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1903) with [KB4515384](https://support.microsoft.com/en-us/help/4515384/windows-10-update-kb4515384)</span></span>
    - <span data-ttu-id="2867c-126">[Versión 1809 (RS 5)](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1809) con [KB4537818](https://support.microsoft.com/help/4537818/windows-10-update-kb4537818)</span><span class="sxs-lookup"><span data-stu-id="2867c-126">[Version 1809 (RS 5)](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1809) with [with KB4537818](https://support.microsoft.com/help/4537818/windows-10-update-kb4537818)</span></span>
    - <span data-ttu-id="2867c-127">[Versión 1803 (RS 4)](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1803) con [KB4537795](https://support.microsoft.com/help/4537795/windows-10-update-kb4537795)</span><span class="sxs-lookup"><span data-stu-id="2867c-127">[Version 1803 (RS 4)](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1803) with [KB4537795](https://support.microsoft.com/help/4537795/windows-10-update-kb4537795)</span></span>
    - <span data-ttu-id="2867c-128">[Versión 1709 (RS 3)](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) con [KB4537816](https://support.microsoft.com/help/4537816/windows-10-update-kb4537816)</span><span class="sxs-lookup"><span data-stu-id="2867c-128">[Version 1709 (RS 3)](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) with [KB4537816](https://support.microsoft.com/help/4537816/windows-10-update-kb4537816)</span></span>
  
  - <span data-ttu-id="2867c-129">**Windows Servidor 2019: solo aplicable para la versión preliminar pública**</span><span class="sxs-lookup"><span data-stu-id="2867c-129">**Windows Server 2019 - Only applicable for Public preview**</span></span>
    - <span data-ttu-id="2867c-130">Versión 1903 o (con [KB4515384](https://support.microsoft.com/en-us/help/4515384/windows-10-update-kb4515384)) posterior</span><span class="sxs-lookup"><span data-stu-id="2867c-130">Version 1903 or (with [KB4515384](https://support.microsoft.com/en-us/help/4515384/windows-10-update-kb4515384)) later</span></span> 
    - <span data-ttu-id="2867c-131">Versión 1809 (con [KB4537818](https://support.microsoft.com/en-us/help/4537818/windows-10-update-kb4537818))</span><span class="sxs-lookup"><span data-stu-id="2867c-131">Version 1809 (with [KB4537818](https://support.microsoft.com/en-us/help/4537818/windows-10-update-kb4537818))</span></span>

- <span data-ttu-id="2867c-132">**Habilitar la respuesta en directo desde la página de configuración avanzada**.</span><span class="sxs-lookup"><span data-stu-id="2867c-132">**Enable live response from the advanced settings page**.</span></span><br>
<span data-ttu-id="2867c-133">Tendrás que habilitar la funcionalidad de respuesta en directo en la [página Configuración de características avanzadas.](advanced-features.md)</span><span class="sxs-lookup"><span data-stu-id="2867c-133">You'll need to enable the live response capability in the [Advanced features settings](advanced-features.md) page.</span></span>

    >[!NOTE]
    ><span data-ttu-id="2867c-134">Solo los usuarios con roles de administración global o de seguridad pueden editar esta configuración.</span><span class="sxs-lookup"><span data-stu-id="2867c-134">Only users with manage security or global admin roles can edit these settings.</span></span>

- <span data-ttu-id="2867c-135">**Habilitar la respuesta en directo para los servidores desde la página de configuración avanzada** (recomendado).</span><span class="sxs-lookup"><span data-stu-id="2867c-135">**Enable live response for servers from the advanced settings page** (recommended).</span></span><br>

    >[!NOTE]
    ><span data-ttu-id="2867c-136">Solo los usuarios con roles de administración global o de seguridad pueden editar esta configuración.</span><span class="sxs-lookup"><span data-stu-id="2867c-136">Only users with manage security or global admin roles can edit these settings.</span></span>
    
- <span data-ttu-id="2867c-137">**Asegúrese de que el dispositivo tiene asignado un** nivel de corrección de automatización .</span><span class="sxs-lookup"><span data-stu-id="2867c-137">**Ensure that the device has an Automation Remediation level assigned to it**.</span></span><br>
<span data-ttu-id="2867c-138">Tendrás que habilitar, al menos, el nivel mínimo de corrección para un grupo de dispositivos determinado.</span><span class="sxs-lookup"><span data-stu-id="2867c-138">You'll need to enable, at least, the minimum Remediation Level for a given Device Group.</span></span> <span data-ttu-id="2867c-139">De lo contrario, no podrá establecer una sesión de live response a un miembro de ese grupo.</span><span class="sxs-lookup"><span data-stu-id="2867c-139">Otherwise you won't be able to establish a Live Response session to a member of that group.</span></span>

    <span data-ttu-id="2867c-140">Recibirá el siguiente error:</span><span class="sxs-lookup"><span data-stu-id="2867c-140">You'll receive the following error:</span></span>

    ![Imagen del mensaje de error](images/live-response-error.png)

- <span data-ttu-id="2867c-142">**Habilitar la ejecución de script sin signo de respuesta** en directo (opcional).</span><span class="sxs-lookup"><span data-stu-id="2867c-142">**Enable live response unsigned script execution** (optional).</span></span> <br>

    >[!WARNING]
    ><span data-ttu-id="2867c-143">Permitir el uso de scripts sin signo puede aumentar la exposición a amenazas.</span><span class="sxs-lookup"><span data-stu-id="2867c-143">Allowing the use of unsigned scripts may increase your exposure to threats.</span></span>
 
  <span data-ttu-id="2867c-144">No se recomienda ejecutar scripts sin firma, ya que puede aumentar la exposición a amenazas.</span><span class="sxs-lookup"><span data-stu-id="2867c-144">Running unsigned scripts is not recommended as it can increase your exposure to threats.</span></span> <span data-ttu-id="2867c-145">Sin embargo, si debe usarlos, deberá habilitar la configuración en la [página Configuración de características avanzadas.](advanced-features.md)</span><span class="sxs-lookup"><span data-stu-id="2867c-145">If you must use them however, you'll need to enable the setting in the [Advanced features settings](advanced-features.md) page.</span></span>
    
- <span data-ttu-id="2867c-146">**Asegúrese de que tiene los permisos adecuados**.</span><span class="sxs-lookup"><span data-stu-id="2867c-146">**Ensure that you have the appropriate permissions**.</span></span><br>
    <span data-ttu-id="2867c-147">Solo los usuarios que se han aprovisionado con los permisos adecuados pueden iniciar una sesión.</span><span class="sxs-lookup"><span data-stu-id="2867c-147">Only users who have been provisioned with the appropriate permissions can initiate a session.</span></span> <span data-ttu-id="2867c-148">Para obtener más información sobre las asignaciones de roles, vea [Create and manage roles](user-roles.md).</span><span class="sxs-lookup"><span data-stu-id="2867c-148">For more information on role assignments, see [Create and manage roles](user-roles.md).</span></span> 

    > [!IMPORTANT]
    > <span data-ttu-id="2867c-149">La opción para cargar un archivo en la biblioteca solo está disponible para aquellos con los permisos RBAC adecuados.</span><span class="sxs-lookup"><span data-stu-id="2867c-149">The option to upload a file to the library is only available to those with the appropriate RBAC permissions.</span></span> <span data-ttu-id="2867c-150">El botón está gris para los usuarios con solo permisos delegados.</span><span class="sxs-lookup"><span data-stu-id="2867c-150">The button is greyed out for users with only delegated permissions.</span></span>

    <span data-ttu-id="2867c-151">Según el rol que se le haya concedido, puede ejecutar comandos de respuesta en directo básicos o avanzados.</span><span class="sxs-lookup"><span data-stu-id="2867c-151">Depending on the role that's been granted to you, you can run basic or advanced live response commands.</span></span> <span data-ttu-id="2867c-152">Los permisos de los usuarios están controlados por el rol personalizado RBAC.</span><span class="sxs-lookup"><span data-stu-id="2867c-152">Users permissions are controlled by RBAC custom role.</span></span> 

## <a name="live-response-dashboard-overview"></a><span data-ttu-id="2867c-153">Introducción al panel de respuestas en directo</span><span class="sxs-lookup"><span data-stu-id="2867c-153">Live response dashboard overview</span></span>
<span data-ttu-id="2867c-154">Cuando inicias una sesión de respuesta en directo en un dispositivo, se abre un panel.</span><span class="sxs-lookup"><span data-stu-id="2867c-154">When you initiate a live response session on a device, a dashboard opens.</span></span> <span data-ttu-id="2867c-155">El panel proporciona información sobre la sesión, como la siguiente:</span><span class="sxs-lookup"><span data-stu-id="2867c-155">The dashboard provides information about the session such as the following:</span></span> 

- <span data-ttu-id="2867c-156">Quién la sesión</span><span class="sxs-lookup"><span data-stu-id="2867c-156">Who created the session</span></span>
- <span data-ttu-id="2867c-157">Cuando se inició la sesión</span><span class="sxs-lookup"><span data-stu-id="2867c-157">When the session started</span></span>
- <span data-ttu-id="2867c-158">Duración de la sesión</span><span class="sxs-lookup"><span data-stu-id="2867c-158">The duration of the session</span></span>

<span data-ttu-id="2867c-159">El panel también le da acceso a:</span><span class="sxs-lookup"><span data-stu-id="2867c-159">The dashboard also gives you access to:</span></span>
- <span data-ttu-id="2867c-160">Desconectar sesión</span><span class="sxs-lookup"><span data-stu-id="2867c-160">Disconnect session</span></span>
- <span data-ttu-id="2867c-161">Upload archivos a la biblioteca</span><span class="sxs-lookup"><span data-stu-id="2867c-161">Upload files to the library</span></span> 
- <span data-ttu-id="2867c-162">Consola de comandos</span><span class="sxs-lookup"><span data-stu-id="2867c-162">Command console</span></span>
- <span data-ttu-id="2867c-163">Registro de comandos</span><span class="sxs-lookup"><span data-stu-id="2867c-163">Command log</span></span>


## <a name="initiate-a-live-response-session-on-a-device"></a><span data-ttu-id="2867c-164">Iniciar una sesión de respuesta en directo en un dispositivo</span><span class="sxs-lookup"><span data-stu-id="2867c-164">Initiate a live response session on a device</span></span> 

1. <span data-ttu-id="2867c-165">Inicie sesión en Centro de seguridad de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="2867c-165">Sign in to Microsoft Defender Security Center.</span></span>

2. <span data-ttu-id="2867c-166">Vaya a la página de lista de dispositivos y seleccione un dispositivo para investigar.</span><span class="sxs-lookup"><span data-stu-id="2867c-166">Navigate to the devices list page and select a device to investigate.</span></span> <span data-ttu-id="2867c-167">Se abre la página dispositivos.</span><span class="sxs-lookup"><span data-stu-id="2867c-167">The devices page opens.</span></span>

3. <span data-ttu-id="2867c-168">Inicie la sesión de respuesta activa seleccionando **Iniciar sesión de respuesta en directo**.</span><span class="sxs-lookup"><span data-stu-id="2867c-168">Launch the live response session by selecting **Initiate live response session**.</span></span> <span data-ttu-id="2867c-169">Se muestra una consola de comandos.</span><span class="sxs-lookup"><span data-stu-id="2867c-169">A command console is displayed.</span></span> <span data-ttu-id="2867c-170">Espere mientras la sesión se conecta al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2867c-170">Wait while the session connects to the device.</span></span>

4. <span data-ttu-id="2867c-171">Use los comandos integrados para realizar trabajos de investigación.</span><span class="sxs-lookup"><span data-stu-id="2867c-171">Use the built-in commands to do investigative work.</span></span> <span data-ttu-id="2867c-172">Para obtener más información, vea [Comandos de respuesta en directo](#live-response-commands).</span><span class="sxs-lookup"><span data-stu-id="2867c-172">For more information, see [Live response commands](#live-response-commands).</span></span>

5. <span data-ttu-id="2867c-173">Después de completar la investigación, seleccione **Desconectar sesión** y, a continuación, **seleccione Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="2867c-173">After completing your investigation, select **Disconnect session**, then select **Confirm**.</span></span>

## <a name="live-response-commands"></a><span data-ttu-id="2867c-174">Comandos de respuesta en directo</span><span class="sxs-lookup"><span data-stu-id="2867c-174">Live response commands</span></span>

<span data-ttu-id="2867c-175">Según el rol que se le haya concedido, puede ejecutar comandos de respuesta en directo básicos o avanzados.</span><span class="sxs-lookup"><span data-stu-id="2867c-175">Depending on the role that's been granted to you, you can run basic or advanced live response commands.</span></span> <span data-ttu-id="2867c-176">Los permisos de usuario se controlan mediante roles personalizados rbac.</span><span class="sxs-lookup"><span data-stu-id="2867c-176">User permissions are controlled by RBAC custom roles.</span></span> <span data-ttu-id="2867c-177">Para obtener más información sobre las asignaciones de roles, vea [Create and manage roles](user-roles.md).</span><span class="sxs-lookup"><span data-stu-id="2867c-177">For more information on role assignments, see [Create and manage roles](user-roles.md).</span></span> 


>[!NOTE]
><span data-ttu-id="2867c-178">La respuesta en directo es un shell interactivo basado en la nube, por lo que la experiencia de comandos específica puede variar en el tiempo de respuesta según la calidad de la red y la carga del sistema entre el usuario final y el dispositivo de destino.</span><span class="sxs-lookup"><span data-stu-id="2867c-178">Live response is a cloud-based interactive shell, as such, specific command experience may vary in response time depending on network quality and system load between the end user and the target device.</span></span>

### <a name="basic-commands"></a><span data-ttu-id="2867c-179">Comandos básicos</span><span class="sxs-lookup"><span data-stu-id="2867c-179">Basic commands</span></span>

<span data-ttu-id="2867c-180">Los siguientes comandos están disponibles para los roles de usuario a los que se les concede la capacidad de ejecutar **comandos** básicos de respuesta en directo.</span><span class="sxs-lookup"><span data-stu-id="2867c-180">The following commands are available for user roles that are granted the ability to run **basic** live response commands.</span></span> <span data-ttu-id="2867c-181">Para obtener más información sobre las asignaciones de roles, vea [Create and manage roles](user-roles.md).</span><span class="sxs-lookup"><span data-stu-id="2867c-181">For more information on role assignments, see [Create and manage roles](user-roles.md).</span></span> 

| <span data-ttu-id="2867c-182">Comando</span><span class="sxs-lookup"><span data-stu-id="2867c-182">Command</span></span> | <span data-ttu-id="2867c-183">Descripción</span><span class="sxs-lookup"><span data-stu-id="2867c-183">Description</span></span> |
|---|---|--- |
|`cd` | <span data-ttu-id="2867c-184">Cambia el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="2867c-184">Changes the current directory.</span></span> | 
|`cls` | <span data-ttu-id="2867c-185">Borra la pantalla de la consola.</span><span class="sxs-lookup"><span data-stu-id="2867c-185">Clears the console screen.</span></span>  |
|`connect` | <span data-ttu-id="2867c-186">Inicia una sesión de respuesta en directo al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2867c-186">Initiates a live response session to the device.</span></span> |
|`connections` | <span data-ttu-id="2867c-187">Muestra todas las conexiones activas.</span><span class="sxs-lookup"><span data-stu-id="2867c-187">Shows all the active connections.</span></span> |
|`dir` | <span data-ttu-id="2867c-188">Muestra una lista de archivos y subdirectorios en un directorio.</span><span class="sxs-lookup"><span data-stu-id="2867c-188">Shows a list of files and subdirectories in a directory.</span></span> |
|`drivers` |  <span data-ttu-id="2867c-189">Muestra todos los controladores instalados en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2867c-189">Shows all drivers installed on the device.</span></span> |
|`fg <command ID>` | <span data-ttu-id="2867c-190">Coloque el trabajo especificado en primer plano en primer plano, lo que lo hace el trabajo actual.</span><span class="sxs-lookup"><span data-stu-id="2867c-190">Place the specified job in the foreground in the foreground, making it the current job.</span></span> <br> <span data-ttu-id="2867c-191">NOTA: fg toma un "identificador de comando" disponible desde trabajos, no un PID</span><span class="sxs-lookup"><span data-stu-id="2867c-191">NOTE: fg takes a “command ID” available from jobs, not a PID</span></span> |
|`fileinfo` | <span data-ttu-id="2867c-192">Obtener información acerca de un archivo.</span><span class="sxs-lookup"><span data-stu-id="2867c-192">Get information about a file.</span></span> |
|`findfile` | <span data-ttu-id="2867c-193">Localiza los archivos por un nombre determinado en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2867c-193">Locates files by a given name on the device.</span></span> |
|`getfile <file_path>` | <span data-ttu-id="2867c-194">Descarga un archivo.</span><span class="sxs-lookup"><span data-stu-id="2867c-194">Downloads a file.</span></span> |
|`help` | <span data-ttu-id="2867c-195">Proporciona información de ayuda para comandos de respuesta en directo.</span><span class="sxs-lookup"><span data-stu-id="2867c-195">Provides help information for live response commands.</span></span> |
|`jobs` | <span data-ttu-id="2867c-196">Muestra trabajos en ejecución, su identificador y estado.</span><span class="sxs-lookup"><span data-stu-id="2867c-196">Shows currently running jobs, their ID and status.</span></span> |
|`persistence` | <span data-ttu-id="2867c-197">Muestra todos los métodos de persistencia conocidos en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2867c-197">Shows all known persistence methods on the device.</span></span> |
|`processes` | <span data-ttu-id="2867c-198">Muestra todos los procesos que se ejecutan en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2867c-198">Shows all processes running on the device.</span></span> |
|`registry` | <span data-ttu-id="2867c-199">Muestra los valores del Registro.</span><span class="sxs-lookup"><span data-stu-id="2867c-199">Shows registry values.</span></span> |
|`scheduledtasks` | <span data-ttu-id="2867c-200">Muestra todas las tareas programadas en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2867c-200">Shows all scheduled tasks on the device.</span></span> |
|`services` | <span data-ttu-id="2867c-201">Muestra todos los servicios del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2867c-201">Shows all services on the device.</span></span> |
|`trace` | <span data-ttu-id="2867c-202">Establece el modo de registro del terminal en depuración.</span><span class="sxs-lookup"><span data-stu-id="2867c-202">Sets the terminal's logging mode to debug.</span></span> |

### <a name="advanced-commands"></a><span data-ttu-id="2867c-203">Comandos avanzados</span><span class="sxs-lookup"><span data-stu-id="2867c-203">Advanced commands</span></span>
<span data-ttu-id="2867c-204">Los siguientes comandos están disponibles para los roles de usuario a los que se les concede la capacidad de ejecutar **comandos avanzados** de respuesta en directo.</span><span class="sxs-lookup"><span data-stu-id="2867c-204">The following commands are available for user roles that are granted the ability to run **advanced** live response commands.</span></span> <span data-ttu-id="2867c-205">Para obtener más información sobre las asignaciones de roles, vea [Create and manage roles](user-roles.md).</span><span class="sxs-lookup"><span data-stu-id="2867c-205">For more information on role assignments, see [Create and manage roles](user-roles.md).</span></span> 

| <span data-ttu-id="2867c-206">Comando</span><span class="sxs-lookup"><span data-stu-id="2867c-206">Command</span></span> | <span data-ttu-id="2867c-207">Descripción</span><span class="sxs-lookup"><span data-stu-id="2867c-207">Description</span></span> |
|---|---|
| `analyze` | <span data-ttu-id="2867c-208">Analiza la entidad con varios motores de incriminación para llegar a un veredicto.</span><span class="sxs-lookup"><span data-stu-id="2867c-208">Analyses the entity with various incrimination engines to reach a verdict.</span></span> |
| `run` | <span data-ttu-id="2867c-209">Ejecuta un script de PowerShell desde la biblioteca en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2867c-209">Runs a PowerShell script from the library on the device.</span></span> |
| `library` | <span data-ttu-id="2867c-210">Enumera los archivos que se cargaron en la biblioteca de respuestas en directo.</span><span class="sxs-lookup"><span data-stu-id="2867c-210">Lists files that were uploaded to the live response library.</span></span> |
| `putfile` | <span data-ttu-id="2867c-211">Coloca un archivo de la biblioteca en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2867c-211">Puts a file from the library to the device.</span></span> <span data-ttu-id="2867c-212">Los archivos se guardan en una carpeta de trabajo y se eliminan cuando el dispositivo se reinicia de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="2867c-212">Files are saved in a working folder and are deleted when the device restarts by default.</span></span> |
| `remediate` | <span data-ttu-id="2867c-213">Corrige una entidad en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2867c-213">Remediates an entity on the device.</span></span> <span data-ttu-id="2867c-214">La acción de corrección variará según el tipo de entidad:</span><span class="sxs-lookup"><span data-stu-id="2867c-214">The remediation action will vary depending on the entity type:</span></span><br><span data-ttu-id="2867c-215">- Archivo: eliminar</span><span class="sxs-lookup"><span data-stu-id="2867c-215">- File: delete</span></span><br><span data-ttu-id="2867c-216">- Proceso: detener, eliminar archivo de imagen</span><span class="sxs-lookup"><span data-stu-id="2867c-216">- Process: stop, delete image file</span></span><br><span data-ttu-id="2867c-217">- Servicio: detener, eliminar archivo de imagen</span><span class="sxs-lookup"><span data-stu-id="2867c-217">- Service: stop, delete image file</span></span><br><span data-ttu-id="2867c-218">- Entrada del Registro: eliminar</span><span class="sxs-lookup"><span data-stu-id="2867c-218">- Registry entry: delete</span></span><br><span data-ttu-id="2867c-219">- Tarea programada: quitar</span><span class="sxs-lookup"><span data-stu-id="2867c-219">- Scheduled task: remove</span></span><br><span data-ttu-id="2867c-220">- Elemento de carpeta de inicio: eliminar archivo</span><span class="sxs-lookup"><span data-stu-id="2867c-220">- Startup folder item: delete file</span></span> <br> <span data-ttu-id="2867c-221">NOTA: Este comando tiene un comando de requisito previo.</span><span class="sxs-lookup"><span data-stu-id="2867c-221">NOTE: This command has a prerequisite command.</span></span> <span data-ttu-id="2867c-222">Puede usar el `-auto` comando junto con para ejecutar automáticamente el comando de `remediate` requisitos previos.</span><span class="sxs-lookup"><span data-stu-id="2867c-222">You can use the `-auto` command in conjunction with `remediate` to automatically run the prerequisite command.</span></span> 
|`undo` | <span data-ttu-id="2867c-223">Restaura una entidad que se ha corregido.</span><span class="sxs-lookup"><span data-stu-id="2867c-223">Restores an entity that was remediated.</span></span> |


## <a name="use-live-response-commands"></a><span data-ttu-id="2867c-224">Usar comandos de respuesta en directo</span><span class="sxs-lookup"><span data-stu-id="2867c-224">Use live response commands</span></span>

<span data-ttu-id="2867c-225">Los comandos que se pueden usar en la consola siguen principios similares a [Windows comandos](https://docs.microsoft.com/windows-server/administration/windows-commands/windows-commands#BKMK_c).</span><span class="sxs-lookup"><span data-stu-id="2867c-225">The commands that you can use in the console follow similar principles as [Windows Commands](https://docs.microsoft.com/windows-server/administration/windows-commands/windows-commands#BKMK_c).</span></span>

<span data-ttu-id="2867c-226">Los comandos avanzados ofrecen un conjunto más sólido de acciones que te permiten realizar acciones más eficaces, como descargar y cargar un archivo, ejecutar scripts en el dispositivo y realizar acciones de corrección en una entidad.</span><span class="sxs-lookup"><span data-stu-id="2867c-226">The advanced commands offer a more robust set of actions that allow you to take more powerful actions such as download and upload a file, run scripts on the device, and take remediation actions on an entity.</span></span>

### <a name="get-a-file-from-the-device"></a><span data-ttu-id="2867c-227">Obtener un archivo del dispositivo</span><span class="sxs-lookup"><span data-stu-id="2867c-227">Get a file from the device</span></span>

<span data-ttu-id="2867c-228">Para escenarios en los que quieras obtener un archivo de un dispositivo que estés investigando, puedes usar el `getfile` comando.</span><span class="sxs-lookup"><span data-stu-id="2867c-228">For scenarios when you'd like get a file from a device you're investigating, you can use the `getfile` command.</span></span> <span data-ttu-id="2867c-229">Esto te permite guardar el archivo del dispositivo para una investigación posterior.</span><span class="sxs-lookup"><span data-stu-id="2867c-229">This allows you to save the file from the device for further investigation.</span></span>

>[!NOTE]
><span data-ttu-id="2867c-230">Se aplican los siguientes límites de tamaño de archivo:</span><span class="sxs-lookup"><span data-stu-id="2867c-230">The following file size limits apply:</span></span>
>- <span data-ttu-id="2867c-231">`getfile` límite: 3 GB</span><span class="sxs-lookup"><span data-stu-id="2867c-231">`getfile` limit: 3 GB</span></span>
>- <span data-ttu-id="2867c-232">`fileinfo` límite: 10 GB</span><span class="sxs-lookup"><span data-stu-id="2867c-232">`fileinfo` limit: 10 GB</span></span>
>- <span data-ttu-id="2867c-233">`library` límite: 250 MB</span><span class="sxs-lookup"><span data-stu-id="2867c-233">`library` limit: 250 MB</span></span>

### <a name="download-a-file-in-the-background"></a><span data-ttu-id="2867c-234">Descargar un archivo en segundo plano</span><span class="sxs-lookup"><span data-stu-id="2867c-234">Download a file in the background</span></span>

<span data-ttu-id="2867c-235">Para permitir que el equipo de operaciones de seguridad continúe investigando un dispositivo afectado, los archivos ahora se pueden descargar en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="2867c-235">To enable your security operations team to continue investigating an impacted device, files can now be downloaded in the background.</span></span>

- <span data-ttu-id="2867c-236">Para descargar un archivo en segundo plano, en la consola de comandos de respuesta en directo, escriba `download <file_path> &` .</span><span class="sxs-lookup"><span data-stu-id="2867c-236">To download a file in the background, in the live response command console, type `download <file_path> &`.</span></span>
- <span data-ttu-id="2867c-237">Si está esperando a que se descargue un archivo, puede moverlo al fondo mediante Ctrl + Z.</span><span class="sxs-lookup"><span data-stu-id="2867c-237">If you are waiting for a file to be downloaded, you can move it to the background by using Ctrl + Z.</span></span>
- <span data-ttu-id="2867c-238">Para llevar una descarga de archivos al primer plano, en la consola de comandos de respuesta en directo, escriba `fg <command_id>` .</span><span class="sxs-lookup"><span data-stu-id="2867c-238">To bring a file download to the foreground, in the live response command console, type `fg <command_id>`.</span></span>

<span data-ttu-id="2867c-239">Estos son algunos ejemplos:</span><span class="sxs-lookup"><span data-stu-id="2867c-239">Here are some examples:</span></span>


|<span data-ttu-id="2867c-240">Command</span><span class="sxs-lookup"><span data-stu-id="2867c-240">Command</span></span>  |<span data-ttu-id="2867c-241">Qué hace</span><span class="sxs-lookup"><span data-stu-id="2867c-241">What it does</span></span>  |
|---------|---------|
|`getfile "C:\windows\some_file.exe" &`     |<span data-ttu-id="2867c-242">Inicia la descarga de un archivo *denominadosome_file.exe* en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="2867c-242">Starts downloading a file named *some_file.exe* in the background.</span></span>         |
|`fg 1234`     |<span data-ttu-id="2867c-243">Devuelve una descarga con el identificador de comando *1234* en primer plano.</span><span class="sxs-lookup"><span data-stu-id="2867c-243">Returns a download with command ID *1234* to the foreground.</span></span>         |


### <a name="put-a-file-in-the-library"></a><span data-ttu-id="2867c-244">Colocar un archivo en la biblioteca</span><span class="sxs-lookup"><span data-stu-id="2867c-244">Put a file in the library</span></span>

<span data-ttu-id="2867c-245">La respuesta en directo tiene una biblioteca en la que puede colocar archivos.</span><span class="sxs-lookup"><span data-stu-id="2867c-245">Live response has a library where you can put files into.</span></span> <span data-ttu-id="2867c-246">La biblioteca almacena archivos (como scripts) que se pueden ejecutar en una sesión de respuesta activa en el nivel de inquilino.</span><span class="sxs-lookup"><span data-stu-id="2867c-246">The library stores files (such as scripts) that can be run in a live response session at the tenant level.</span></span>

<span data-ttu-id="2867c-247">La respuesta en directo permite ejecutar scripts de PowerShell, pero primero debe colocar los archivos en la biblioteca antes de poder ejecutarlos.</span><span class="sxs-lookup"><span data-stu-id="2867c-247">Live response allows PowerShell scripts to run, however you must first put the files into the library before you can run them.</span></span> 

<span data-ttu-id="2867c-248">Puede tener una colección de scripts de PowerShell que se pueden ejecutar en dispositivos con los que inicie sesiones de respuesta en directo.</span><span class="sxs-lookup"><span data-stu-id="2867c-248">You can have a collection of PowerShell scripts that can run on devices that you initiate live response sessions with.</span></span> 

#### <a name="to-upload-a-file-in-the-library"></a><span data-ttu-id="2867c-249">Para cargar un archivo en la biblioteca</span><span class="sxs-lookup"><span data-stu-id="2867c-249">To upload a file in the library</span></span>

1. <span data-ttu-id="2867c-250">Haga **clic Upload archivo en la biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="2867c-250">Click **Upload file to library**.</span></span> 

2. <span data-ttu-id="2867c-251">Haga **clic en** Examinar y seleccione el archivo.</span><span class="sxs-lookup"><span data-stu-id="2867c-251">Click **Browse** and select the file.</span></span>

3. <span data-ttu-id="2867c-252">Proporcione una breve descripción.</span><span class="sxs-lookup"><span data-stu-id="2867c-252">Provide a brief description.</span></span>

4. <span data-ttu-id="2867c-253">Especifica si quieres sobrescribir un archivo con el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="2867c-253">Specify if you'd like to overwrite a file with the same name.</span></span>

5. <span data-ttu-id="2867c-254">Si desea serlo, sepa qué parámetros son necesarios para el script, active la casilla parámetros de script.</span><span class="sxs-lookup"><span data-stu-id="2867c-254">If you'd like to be,  know what parameters are needed for the script, select the script parameters check box.</span></span> <span data-ttu-id="2867c-255">En el campo de texto, escriba un ejemplo y una descripción.</span><span class="sxs-lookup"><span data-stu-id="2867c-255">In the text field, enter an example and a description.</span></span>

6. <span data-ttu-id="2867c-256">Haga clic **en Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="2867c-256">Click **Confirm**.</span></span> 

7. <span data-ttu-id="2867c-257">(Opcional) Para comprobar que el archivo se ha cargado en la biblioteca, ejecute el `library` comando.</span><span class="sxs-lookup"><span data-stu-id="2867c-257">(Optional) To verify that the file was uploaded to the library, run the `library` command.</span></span>


### <a name="cancel-a-command"></a><span data-ttu-id="2867c-258">Cancelar un comando</span><span class="sxs-lookup"><span data-stu-id="2867c-258">Cancel a command</span></span>
<span data-ttu-id="2867c-259">En cualquier momento durante una sesión, puede cancelar un comando presionando CTRL + C.</span><span class="sxs-lookup"><span data-stu-id="2867c-259">Anytime during a session, you can cancel a command by pressing CTRL + C.</span></span>  

>[!WARNING]
><span data-ttu-id="2867c-260">El uso de este acceso directo no detendrá el comando en el lado del agente.</span><span class="sxs-lookup"><span data-stu-id="2867c-260">Using this shortcut will not stop the command in the agent side.</span></span> <span data-ttu-id="2867c-261">Solo cancelará el comando en el portal.</span><span class="sxs-lookup"><span data-stu-id="2867c-261">It will only cancel the command in the portal.</span></span> <span data-ttu-id="2867c-262">Por lo tanto, el cambio de operaciones como "remediate" puede continuar, mientras que el comando se cancela.</span><span class="sxs-lookup"><span data-stu-id="2867c-262">So, changing operations such as "remediate" may continue, while the command is canceled.</span></span> 

## <a name="run-a-powershell-script"></a><span data-ttu-id="2867c-263">Ejecutar un script de PowerShell</span><span class="sxs-lookup"><span data-stu-id="2867c-263">Run a PowerShell script</span></span> 

<span data-ttu-id="2867c-264">Para poder ejecutar un script de PowerShell, primero debe cargarlo en la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="2867c-264">Before you can run a PowerShell script, you must first upload it to the library.</span></span> 

<span data-ttu-id="2867c-265">Después de cargar el script en la biblioteca, use el `run` comando para ejecutar el script.</span><span class="sxs-lookup"><span data-stu-id="2867c-265">After uploading the script to the library, use the `run` command to run the script.</span></span>

<span data-ttu-id="2867c-266">Si planea usar un script sin signo en la sesión, deberá habilitar la configuración en la [página Configuración de características avanzadas.](advanced-features.md)</span><span class="sxs-lookup"><span data-stu-id="2867c-266">If you plan to use an unsigned script in the session, you'll need to enable the setting in the [Advanced features settings](advanced-features.md) page.</span></span>

>[!WARNING]
><span data-ttu-id="2867c-267">Permitir el uso de scripts sin signo puede aumentar la exposición a amenazas.</span><span class="sxs-lookup"><span data-stu-id="2867c-267">Allowing the use of unsigned scripts may increase your exposure to threats.</span></span>

## <a name="apply-command-parameters"></a><span data-ttu-id="2867c-268">Aplicar parámetros de comando</span><span class="sxs-lookup"><span data-stu-id="2867c-268">Apply command parameters</span></span>

- <span data-ttu-id="2867c-269">Vea la ayuda de la consola para obtener información sobre los parámetros de comandos.</span><span class="sxs-lookup"><span data-stu-id="2867c-269">View the console help to learn about command parameters.</span></span> <span data-ttu-id="2867c-270">Para obtener información sobre un comando individual, ejecute:</span><span class="sxs-lookup"><span data-stu-id="2867c-270">To learn about an individual command, run:</span></span>
 
    `help <command name>`

- <span data-ttu-id="2867c-271">Al aplicar parámetros a comandos, tenga en cuenta que los parámetros se controlan en función de un orden fijo:</span><span class="sxs-lookup"><span data-stu-id="2867c-271">When applying parameters to commands, note that parameters are handled based on a fixed order:</span></span>
 
    `<command name> param1 param2` 

- <span data-ttu-id="2867c-272">Al especificar parámetros fuera del orden fijo, especifique el nombre del parámetro con un guión antes de proporcionar el valor:</span><span class="sxs-lookup"><span data-stu-id="2867c-272">When specifying parameters outside of the fixed order, specify the name of the parameter with a hyphen before providing the value:</span></span>
 
    `<command name> -param2_name param2`

- <span data-ttu-id="2867c-273">Al usar comandos que tienen comandos de requisitos previos, puede usar marcas:</span><span class="sxs-lookup"><span data-stu-id="2867c-273">When using commands that have prerequisite commands, you can use flags:</span></span>

    <span data-ttu-id="2867c-274">`<command name> -type file -id <file path> - auto` o `remediate file <file path> - auto`.</span><span class="sxs-lookup"><span data-stu-id="2867c-274">`<command name> -type file -id <file path> - auto` or `remediate file <file path> - auto`.</span></span>

## <a name="supported-output-types"></a><span data-ttu-id="2867c-275">Tipos de salida compatibles</span><span class="sxs-lookup"><span data-stu-id="2867c-275">Supported output types</span></span>

<span data-ttu-id="2867c-276">La respuesta en directo admite tipos de salida de formato JSON y tabla.</span><span class="sxs-lookup"><span data-stu-id="2867c-276">Live response supports table and JSON format output types.</span></span> <span data-ttu-id="2867c-277">Para cada comando, hay un comportamiento de salida predeterminado.</span><span class="sxs-lookup"><span data-stu-id="2867c-277">For each command, there's a default output behavior.</span></span> <span data-ttu-id="2867c-278">Puede modificar el resultado en el formato de salida preferido mediante los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="2867c-278">You can modify the output in your preferred output format using the following commands:</span></span>

- `-output json`
- `-output table`

>[!NOTE]
><span data-ttu-id="2867c-279">Se muestran menos campos en formato de tabla debido al espacio limitado.</span><span class="sxs-lookup"><span data-stu-id="2867c-279">Fewer fields are shown in table format due to the limited space.</span></span> <span data-ttu-id="2867c-280">Para ver más detalles en el resultado, puede usar el comando de salida JSON para que se muestran más detalles.</span><span class="sxs-lookup"><span data-stu-id="2867c-280">To see more details in the output, you can use the JSON output command so that more details are shown.</span></span>

## <a name="supported-output-pipes"></a><span data-ttu-id="2867c-281">Canalizaciones de salida admitidas</span><span class="sxs-lookup"><span data-stu-id="2867c-281">Supported output pipes</span></span>

<span data-ttu-id="2867c-282">La respuesta en directo admite la canalización de salida a la CLI y al archivo.</span><span class="sxs-lookup"><span data-stu-id="2867c-282">Live response supports output piping to CLI and file.</span></span> <span data-ttu-id="2867c-283">CLI es el comportamiento de salida predeterminado.</span><span class="sxs-lookup"><span data-stu-id="2867c-283">CLI is the default output behavior.</span></span> <span data-ttu-id="2867c-284">Puede canalizar el resultado a un archivo mediante el siguiente comando: [comando] > [filename].txt.</span><span class="sxs-lookup"><span data-stu-id="2867c-284">You can pipe the output to a file using the following command: [command] > [filename].txt.</span></span>  

<span data-ttu-id="2867c-285">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="2867c-285">Example:</span></span>

```console
processes > output.txt
```

## <a name="view-the-command-log"></a><span data-ttu-id="2867c-286">Ver el registro de comandos</span><span class="sxs-lookup"><span data-stu-id="2867c-286">View the command log</span></span>

<span data-ttu-id="2867c-287">Selecciona la **pestaña Registro de** comandos para ver los comandos usados en el dispositivo durante una sesión.</span><span class="sxs-lookup"><span data-stu-id="2867c-287">Select the **Command log** tab to see the commands used on the device during a session.</span></span> <span data-ttu-id="2867c-288">Cada comando se realiza un seguimiento con detalles completos como:</span><span class="sxs-lookup"><span data-stu-id="2867c-288">Each command is tracked with full details such as:</span></span>
- <span data-ttu-id="2867c-289">ID</span><span class="sxs-lookup"><span data-stu-id="2867c-289">ID</span></span>
- <span data-ttu-id="2867c-290">Línea de comandos</span><span class="sxs-lookup"><span data-stu-id="2867c-290">Command line</span></span>
- <span data-ttu-id="2867c-291">Duración</span><span class="sxs-lookup"><span data-stu-id="2867c-291">Duration</span></span>
- <span data-ttu-id="2867c-292">Estado y barra lateral de entrada o salida</span><span class="sxs-lookup"><span data-stu-id="2867c-292">Status and input or output side bar</span></span>

## <a name="limitations"></a><span data-ttu-id="2867c-293">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="2867c-293">Limitations</span></span>

- <span data-ttu-id="2867c-294">Las sesiones de respuesta en directo están limitadas a 25 sesiones de respuesta en directo a la vez.</span><span class="sxs-lookup"><span data-stu-id="2867c-294">Live response sessions are limited to 25 live response sessions at a time.</span></span>
- <span data-ttu-id="2867c-295">El valor de tiempo de espera inactivo de la sesión de respuesta en directo es de 30 minutos.</span><span class="sxs-lookup"><span data-stu-id="2867c-295">Live response session inactive timeout value is 30 minutes.</span></span> 
- <span data-ttu-id="2867c-296">Un usuario puede iniciar hasta 10 sesiones simultáneas.</span><span class="sxs-lookup"><span data-stu-id="2867c-296">A user can initiate up to 10 concurrent sessions.</span></span>
- <span data-ttu-id="2867c-297">Un dispositivo solo puede estar en una sesión a la vez.</span><span class="sxs-lookup"><span data-stu-id="2867c-297">A device can only be in one session at a time.</span></span>
- <span data-ttu-id="2867c-298">Se aplican los siguientes límites de tamaño de archivo:</span><span class="sxs-lookup"><span data-stu-id="2867c-298">The following file size limits apply:</span></span>
   - <span data-ttu-id="2867c-299">`getfile` límite: 3 GB</span><span class="sxs-lookup"><span data-stu-id="2867c-299">`getfile` limit: 3 GB</span></span>
   - <span data-ttu-id="2867c-300">`fileinfo` límite: 10 GB</span><span class="sxs-lookup"><span data-stu-id="2867c-300">`fileinfo` limit: 10 GB</span></span>
   - <span data-ttu-id="2867c-301">`library` límite: 250 MB</span><span class="sxs-lookup"><span data-stu-id="2867c-301">`library` limit: 250 MB</span></span>

## <a name="related-article"></a><span data-ttu-id="2867c-302">Artículo relacionado</span><span class="sxs-lookup"><span data-stu-id="2867c-302">Related article</span></span>
- [<span data-ttu-id="2867c-303">Ejemplos de comandos de respuesta en vivo</span><span class="sxs-lookup"><span data-stu-id="2867c-303">Live response command examples</span></span>](live-response-command-examples.md)
