---
title: Solucionar problemas del Antivirus de Windows Defender al migrar desde una solución de terceros
description: Solucionar errores comunes al migrar a Antivirus de Microsoft Defender
keywords: evento, código de error, registro, solución de problemas, antivirus de Microsoft Defender, antivirus de Windows Defender, migración
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
ms.topic: article
author: martyav
ms.author: v-maave
ms.custom: nextgen
ms.date: 09/11/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 3eb4d01957383efc8df47e9fee6eb6394c80015a
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/14/2021
ms.locfileid: "52924388"
---
# <a name="troubleshoot-microsoft-defender-antivirus-while-migrating-from-a-third-party-solution"></a><span data-ttu-id="1895d-104">Solucionar problemas del Antivirus de Windows Defender al migrar desde una solución de terceros</span><span class="sxs-lookup"><span data-stu-id="1895d-104">Troubleshoot Microsoft Defender Antivirus while migrating from a third-party solution</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1895d-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="1895d-105">**Applies to:**</span></span>

- [<span data-ttu-id="1895d-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="1895d-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)


<span data-ttu-id="1895d-107">Puede encontrar ayuda aquí si encuentra problemas al migrar desde una solución de seguridad de terceros a Antivirus de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="1895d-107">You can find help here if you encounter issues while migrating from a third-party security solution to Microsoft Defender Antivirus.</span></span>

## <a name="review-event-logs"></a><span data-ttu-id="1895d-108">Revisar registros de eventos</span><span class="sxs-lookup"><span data-stu-id="1895d-108">Review event logs</span></span>

<span data-ttu-id="1895d-109">Abra la aplicación Visor de eventos seleccionando el icono **Buscar** en la barra de tareas y buscando el *visor de eventos.*</span><span class="sxs-lookup"><span data-stu-id="1895d-109">Open the Event viewer app by selecting the **Search** icon in the taskbar, and searching for *event viewer*.</span></span>

<span data-ttu-id="1895d-110">Encontrará información Antivirus de Microsoft Defender en **Registros** de aplicaciones y servicios  >  **Microsoft**  >  **Windows**  >  **Windows Defender**.</span><span class="sxs-lookup"><span data-stu-id="1895d-110">Information about Microsoft Defender Antivirus can be found under  **Applications and Services Logs** > **Microsoft** > **Windows** > **Windows Defender**.</span></span> 

<span data-ttu-id="1895d-111">Desde allí, seleccione **Abrir debajo** de **Operativo**.</span><span class="sxs-lookup"><span data-stu-id="1895d-111">From there, select **Open** underneath **Operational**.</span></span>

<span data-ttu-id="1895d-112">Al seleccionar un evento en el panel de detalles, se mostrará más información sobre un evento en el panel inferior, en las pestañas **General** **y** Detalles.</span><span class="sxs-lookup"><span data-stu-id="1895d-112">Selecting an event from the details pane will show you more information about an event in the lower pane, under the **General** and **Details** tabs.</span></span>

## <a name="microsoft-defender-antivirus-wont-start"></a><span data-ttu-id="1895d-113">Antivirus de Microsoft Defender no se iniciará</span><span class="sxs-lookup"><span data-stu-id="1895d-113">Microsoft Defender Antivirus won't start</span></span>

<span data-ttu-id="1895d-114">Este problema puede manifestarse en forma de varios IDs de eventos diferentes, todos los cuales tienen la misma causa subyacente.</span><span class="sxs-lookup"><span data-stu-id="1895d-114">This issue can manifest in the form of  several different event IDs, all of which have the same underlying cause.</span></span>

### <a name="associated-event-ids"></a><span data-ttu-id="1895d-115">IDs de eventos asociados</span><span class="sxs-lookup"><span data-stu-id="1895d-115">Associated event IDs</span></span>

 <span data-ttu-id="1895d-116">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="1895d-116">Event ID</span></span> | <span data-ttu-id="1895d-117">Nombre de registro</span><span class="sxs-lookup"><span data-stu-id="1895d-117">Log name</span></span> | <span data-ttu-id="1895d-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="1895d-118">Description</span></span> | <span data-ttu-id="1895d-119">Origen</span><span class="sxs-lookup"><span data-stu-id="1895d-119">Source</span></span>
-|-|-|-
<span data-ttu-id="1895d-120">15</span><span class="sxs-lookup"><span data-stu-id="1895d-120">15</span></span> | <span data-ttu-id="1895d-121">Aplicación</span><span class="sxs-lookup"><span data-stu-id="1895d-121">Application</span></span> | <span data-ttu-id="1895d-122">Se Windows Defender el estado correctamente para SECURITY_PRODUCT_STATE_OFF.</span><span class="sxs-lookup"><span data-stu-id="1895d-122">Updated Windows Defender status successfully to SECURITY_PRODUCT_STATE_OFF.</span></span> | <span data-ttu-id="1895d-123">Centro de seguridad</span><span class="sxs-lookup"><span data-stu-id="1895d-123">Security Center</span></span>
<span data-ttu-id="1895d-124">5007</span><span class="sxs-lookup"><span data-stu-id="1895d-124">5007</span></span> | <span data-ttu-id="1895d-125">Microsoft-Windows-Windows Defender/Operational</span><span class="sxs-lookup"><span data-stu-id="1895d-125">Microsoft-Windows-Windows Defender/Operational</span></span> | <span data-ttu-id="1895d-126">Antivirus de Windows Defender La configuración ha cambiado.</span><span class="sxs-lookup"><span data-stu-id="1895d-126">Windows Defender Antivirus Configuration has changed.</span></span>  <span data-ttu-id="1895d-127">Si se trata de un evento inesperado, debes revisar la configuración, ya que puede ser el resultado de malware.</span><span class="sxs-lookup"><span data-stu-id="1895d-127">If this is an unexpected event you should review the settings as this may be the result of malware.</span></span><br /><br /><span data-ttu-id="1895d-128">**Valor antiguo:** Default\IsServiceRunning = 0x0</span><span class="sxs-lookup"><span data-stu-id="1895d-128">**Old value:** Default\IsServiceRunning = 0x0</span></span><br /><span data-ttu-id="1895d-129">**Nuevo valor:** HKLM\SOFTWARE\Microsoft\Windows Defender\IsServiceRunning = 0x1</span><span class="sxs-lookup"><span data-stu-id="1895d-129">**New value:** HKLM\SOFTWARE\Microsoft\Windows Defender\IsServiceRunning = 0x1</span></span> | <span data-ttu-id="1895d-130">Windows Defender</span><span class="sxs-lookup"><span data-stu-id="1895d-130">Windows Defender</span></span>
<span data-ttu-id="1895d-131">5010</span><span class="sxs-lookup"><span data-stu-id="1895d-131">5010</span></span> | <span data-ttu-id="1895d-132">Microsoft-Windows-Windows Defender/Operational</span><span class="sxs-lookup"><span data-stu-id="1895d-132">Microsoft-Windows-Windows Defender/Operational</span></span> | <span data-ttu-id="1895d-133">Antivirus de Windows Defender está deshabilitado el examen de spyware y otro software potencialmente no deseado.</span><span class="sxs-lookup"><span data-stu-id="1895d-133">Windows Defender Antivirus scanning for spyware and other potentially unwanted software is disabled.</span></span> | <span data-ttu-id="1895d-134">Windows Defender</span><span class="sxs-lookup"><span data-stu-id="1895d-134">Windows Defender</span></span>

### <a name="how-to-tell-if-microsoft-defender-antivirus-wont-start-because-a-third-party-antivirus-is-installed"></a><span data-ttu-id="1895d-135">Cómo saber si Antivirus de Microsoft Defender no se iniciará porque está instalado un antivirus de terceros</span><span class="sxs-lookup"><span data-stu-id="1895d-135">How to tell if Microsoft Defender Antivirus won't start because a third-party antivirus is installed</span></span>

<span data-ttu-id="1895d-136">En un dispositivo Windows 10, si no usa Microsoft Defender para Endpoint y tiene instalado un antivirus de terceros, Antivirus de Microsoft Defender se desactivará automáticamente.</span><span class="sxs-lookup"><span data-stu-id="1895d-136">On a Windows 10 device, if you are not using Microsoft Defender for Endpoint, and you have a third-party antivirus installed, then Microsoft Defender Antivirus will be automatically turned off.</span></span> <span data-ttu-id="1895d-137">Si usa Microsoft Defender para Endpoint con un antivirus de terceros instalado, Antivirus de Microsoft Defender se iniciará en modo pasivo, con funcionalidad reducida.</span><span class="sxs-lookup"><span data-stu-id="1895d-137">If you are using Microsoft Defender for Endpoint with a third-party antivirus installed, Microsoft Defender Antivirus will start in passive mode, with reduced functionality.</span></span>

> [!TIP]
> <span data-ttu-id="1895d-138">El escenario descrito solo se aplica a Windows 10.</span><span class="sxs-lookup"><span data-stu-id="1895d-138">The scenario just described applies only to Windows 10.</span></span> <span data-ttu-id="1895d-139">Otras versiones de Windows [tienen diferentes respuestas](microsoft-defender-antivirus-compatibility.md) a Antivirus de Microsoft Defender se ejecutan junto con software de seguridad de terceros.</span><span class="sxs-lookup"><span data-stu-id="1895d-139">Other versions of Windows have [different responses](microsoft-defender-antivirus-compatibility.md) to Microsoft Defender Antivirus being run alongside third-party security software.</span></span>

#### <a name="use-services-app-to-check-if-microsoft-defender-antivirus-is-turned-off"></a><span data-ttu-id="1895d-140">Usar la aplicación Servicios para comprobar si Antivirus de Microsoft Defender está desactivado</span><span class="sxs-lookup"><span data-stu-id="1895d-140">Use Services app to check if Microsoft Defender Antivirus is turned off</span></span>

<span data-ttu-id="1895d-141">Para abrir la aplicación Servicios, seleccione el icono **Buscar** de la barra de tareas y busque *servicios.*</span><span class="sxs-lookup"><span data-stu-id="1895d-141">To open the Services app, select the **Search** icon from the taskbar and search for *services*.</span></span> <span data-ttu-id="1895d-142">También puedes abrir la aplicación desde la línea de comandos escribiendo *services.msc*.</span><span class="sxs-lookup"><span data-stu-id="1895d-142">You can also open the app from the command-line by typing *services.msc*.</span></span>

<span data-ttu-id="1895d-143">La información sobre Antivirus de Microsoft Defender aparecerá en la aplicación Servicios en **Windows Defender**  >  **Operativo**.</span><span class="sxs-lookup"><span data-stu-id="1895d-143">Information about Microsoft Defender Antivirus will be listed within the Services app under **Windows Defender** > **Operational**.</span></span> <span data-ttu-id="1895d-144">El nombre del servicio antivirus *es Antivirus de Windows Defender servicio*.</span><span class="sxs-lookup"><span data-stu-id="1895d-144">The antivirus service name is *Windows Defender Antivirus Service*.</span></span>

<span data-ttu-id="1895d-145">Al comprobar la aplicación, es posible que veas que el servicio *de Antivirus de Windows Defender* está establecido en manual, pero cuando intentas iniciar este servicio manualmente, recibes una advertencia que indica que el servicio de servicio Antivirus de Windows Defender en el equipo local se inició y, a continuación, se *detuvo. Algunos servicios se detienen automáticamente si otros* servicios o programas no los usan.</span><span class="sxs-lookup"><span data-stu-id="1895d-145">While checking the app, you may see that *Windows Defender Antivirus Service* is set to manual — but when you try to start this service manually, you get a warning stating, *The Windows Defender Antivirus Service service on Local Computer started and then stopped. Some services stop automatically if they are not in use by other services or programs.*</span></span>

<span data-ttu-id="1895d-146">Esto indica que Antivirus de Microsoft Defender se ha desactivado automáticamente para conservar la compatibilidad con un antivirus de terceros.</span><span class="sxs-lookup"><span data-stu-id="1895d-146">This indicates that Microsoft Defender Antivirus has been automatically turned off to preserve compatibility with a third-party antivirus.</span></span>

#### <a name="generate-a-detailed-report"></a><span data-ttu-id="1895d-147">Generar un informe detallado</span><span class="sxs-lookup"><span data-stu-id="1895d-147">Generate a detailed report</span></span>

<span data-ttu-id="1895d-148">Puede generar un informe detallado sobre las directivas de  grupo activas actualmente abriendo un símbolo del sistema en modo Ejecutar como administrador y, a continuación, escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="1895d-148">You can generate a detailed report about currently active group policies by opening a command prompt in **Run as admin** mode, then entering the following command:</span></span>

```powershell
GPresult.exe /h gpresult.html
```

<span data-ttu-id="1895d-149">Esto generará un informe ubicado en *./gpresult.html*.</span><span class="sxs-lookup"><span data-stu-id="1895d-149">This will generate a report located at *./gpresult.html*.</span></span> <span data-ttu-id="1895d-150">Abra este archivo y es posible que vea los siguientes resultados, en función de cómo Antivirus de Microsoft Defender se ha desactivado.</span><span class="sxs-lookup"><span data-stu-id="1895d-150">Open this file and you might see the following results, depending on how Microsoft Defender Antivirus was turned off.</span></span>

##### <a name="group-policy-results"></a><span data-ttu-id="1895d-151">Resultados de la directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="1895d-151">Group policy results</span></span>

##### <a name="if-security-settings-are-implemented-via-group-policy-gpo-at-the-domain-or-local-level-or-though-system-center-configuration-manager-sccm"></a><span data-ttu-id="1895d-152">Si la configuración de seguridad se implementa a través de la directiva de grupo (GPO) en el nivel de dominio o local, o a través de System Center configuration Manager (SCCM)</span><span class="sxs-lookup"><span data-stu-id="1895d-152">If security settings are implemented via group policy (GPO) at the domain or local level, or though System center configuration manager (SCCM)</span></span>

<span data-ttu-id="1895d-153">En el informe GPResults, bajo el título *Windows Components/Antivirus de Windows Defender*, puede ver algo como la siguiente entrada, que indica que Antivirus de Microsoft Defender está desactivado.</span><span class="sxs-lookup"><span data-stu-id="1895d-153">Within the GPResults report, under the heading, *Windows Components/Windows Defender Antivirus*, you may see something like the following entry, indicating that Microsoft Defender Antivirus is turned off.</span></span>

<span data-ttu-id="1895d-154">Directiva</span><span class="sxs-lookup"><span data-stu-id="1895d-154">Policy</span></span> | <span data-ttu-id="1895d-155">Configuración</span><span class="sxs-lookup"><span data-stu-id="1895d-155">Setting</span></span> | <span data-ttu-id="1895d-156">GPO ganador</span><span class="sxs-lookup"><span data-stu-id="1895d-156">Winning GPO</span></span>
-|-|-
<span data-ttu-id="1895d-157">Desactivar Antivirus de Windows Defender</span><span class="sxs-lookup"><span data-stu-id="1895d-157">Turn off Windows Defender Antivirus</span></span> | <span data-ttu-id="1895d-158">Habilitado</span><span class="sxs-lookup"><span data-stu-id="1895d-158">Enabled</span></span> | <span data-ttu-id="1895d-159">Win10-Workstations</span><span class="sxs-lookup"><span data-stu-id="1895d-159">Win10-Workstations</span></span>

###### <a name="if-security-settings-are-implemented-via-group-policy-preference-gpp"></a><span data-ttu-id="1895d-160">Si la configuración de seguridad se implementa mediante la preferencia de directiva de grupo (GPP)</span><span class="sxs-lookup"><span data-stu-id="1895d-160">If security settings are implemented via Group policy preference (GPP)</span></span>

<span data-ttu-id="1895d-161">Bajo el encabezado, Elemento del Registro (ruta de acceso *clave: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender, Nombre del valor: DisableAntiSpyware),* puede ver algo parecido a la siguiente entrada, que indica que Antivirus de Microsoft Defender está desactivado.</span><span class="sxs-lookup"><span data-stu-id="1895d-161">Under the heading, *Registry item (Key path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender, Value name: DisableAntiSpyware)*, you may see something like the following entry, indicating that Microsoft Defender Antivirus is turned off.</span></span>

<span data-ttu-id="1895d-162">DisableAntiSpyware</span><span class="sxs-lookup"><span data-stu-id="1895d-162">DisableAntiSpyware</span></span> | -
-|-
<span data-ttu-id="1895d-163">GPO ganador</span><span class="sxs-lookup"><span data-stu-id="1895d-163">Winning GPO</span></span> | <span data-ttu-id="1895d-164">Win10-Workstations</span><span class="sxs-lookup"><span data-stu-id="1895d-164">Win10-Workstations</span></span>
<span data-ttu-id="1895d-165">Resultado: Correcto</span><span class="sxs-lookup"><span data-stu-id="1895d-165">Result: Success</span></span> | 
<span data-ttu-id="1895d-166">**General**</span><span class="sxs-lookup"><span data-stu-id="1895d-166">**General**</span></span> | 
<span data-ttu-id="1895d-167">Acción</span><span class="sxs-lookup"><span data-stu-id="1895d-167">Action</span></span> | <span data-ttu-id="1895d-168">Actualizar</span><span class="sxs-lookup"><span data-stu-id="1895d-168">Update</span></span>
<span data-ttu-id="1895d-169">**Propiedades**</span><span class="sxs-lookup"><span data-stu-id="1895d-169">**Properties**</span></span> | 
<span data-ttu-id="1895d-170">Subárbol</span><span class="sxs-lookup"><span data-stu-id="1895d-170">Hive</span></span> | <span data-ttu-id="1895d-171">HKEY_LOCAL_MACHINE</span><span class="sxs-lookup"><span data-stu-id="1895d-171">HKEY_LOCAL_MACHINE</span></span>
<span data-ttu-id="1895d-172">Ruta de acceso clave</span><span class="sxs-lookup"><span data-stu-id="1895d-172">Key path</span></span> | <span data-ttu-id="1895d-173">SOFTWARE\Policies\Microsoft\Windows Defender</span><span class="sxs-lookup"><span data-stu-id="1895d-173">SOFTWARE\Policies\Microsoft\Windows Defender</span></span>
<span data-ttu-id="1895d-174">Nombre del valor</span><span class="sxs-lookup"><span data-stu-id="1895d-174">Value name</span></span> | <span data-ttu-id="1895d-175">DisableAntiSpyware</span><span class="sxs-lookup"><span data-stu-id="1895d-175">DisableAntiSpyware</span></span>
<span data-ttu-id="1895d-176">Tipo de valor</span><span class="sxs-lookup"><span data-stu-id="1895d-176">Value type</span></span> | <span data-ttu-id="1895d-177">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="1895d-177">REG_DWORD</span></span>
<span data-ttu-id="1895d-178">Datos del valor</span><span class="sxs-lookup"><span data-stu-id="1895d-178">Value data</span></span> | <span data-ttu-id="1895d-179">0x1 (1)</span><span class="sxs-lookup"><span data-stu-id="1895d-179">0x1 (1)</span></span>

###### <a name="if-security-settings-are-implemented-via-registry-key"></a><span data-ttu-id="1895d-180">Si la configuración de seguridad se implementa a través de la clave del Registro</span><span class="sxs-lookup"><span data-stu-id="1895d-180">If security settings are implemented via registry key</span></span>

<span data-ttu-id="1895d-181">El informe puede contener el siguiente texto, que indica que Antivirus de Microsoft Defender está desactivado:</span><span class="sxs-lookup"><span data-stu-id="1895d-181">The report may contain the following text, indicating that Microsoft Defender Antivirus is turned off:</span></span>
 
> <span data-ttu-id="1895d-182">Registro (regedit.exe)</span><span class="sxs-lookup"><span data-stu-id="1895d-182">Registry (regedit.exe)</span></span>
>
> <span data-ttu-id="1895d-183">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender DisableAntiSpyware (dword) 1 (hexadecimal)</span><span class="sxs-lookup"><span data-stu-id="1895d-183">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender DisableAntiSpyware (dword) 1 (hex)</span></span>

###### <a name="if-security-settings-are-set-in-windows-or-your-windows-server-image"></a><span data-ttu-id="1895d-184">Si la configuración de seguridad se establece en Windows o en la Windows de servidor</span><span class="sxs-lookup"><span data-stu-id="1895d-184">If security settings are set in Windows or your Windows Server image</span></span>

<span data-ttu-id="1895d-185">El administrador de imaginación puede haber establecido la directiva de seguridad **[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware)**, localmente a través de *GPEdit.exe*, *LGPO.exe*, o modificando el Registro en su secuencia de tareas.</span><span class="sxs-lookup"><span data-stu-id="1895d-185">Your imagining admin might have set the security policy, **[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware)**, locally via *GPEdit.exe*, *LGPO.exe*, or by modifying the registry in their task sequence.</span></span> <span data-ttu-id="1895d-186">Puede configurar [un identificador de imagen de confianza](/windows-hardware/manufacture/desktop/configure-a-trusted-image-identifier-for-windows-defender) para Antivirus de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="1895d-186">You can [configure a Trusted Image Identifier](/windows-hardware/manufacture/desktop/configure-a-trusted-image-identifier-for-windows-defender) for Microsoft Defender Antivirus.</span></span>

### <a name="turn-microsoft-defender-antivirus-back-on"></a><span data-ttu-id="1895d-187">Volver Antivirus de Microsoft Defender activar</span><span class="sxs-lookup"><span data-stu-id="1895d-187">Turn Microsoft Defender Antivirus back on</span></span>

<span data-ttu-id="1895d-188">Antivirus de Microsoft Defender se activará automáticamente si ningún otro antivirus está activo actualmente.</span><span class="sxs-lookup"><span data-stu-id="1895d-188">Microsoft Defender Antivirus will automatically turn on if no other antivirus is currently active.</span></span> <span data-ttu-id="1895d-189">Tendrás que desactivar completamente el antivirus de terceros para garantizar que Antivirus de Microsoft Defender se pueda ejecutar con funcionalidad completa.</span><span class="sxs-lookup"><span data-stu-id="1895d-189">You'll need to turn the third-party antivirus completely off to ensure Microsoft Defender Antivirus can run with full functionality.</span></span>

> [!WARNING]
> <span data-ttu-id="1895d-190">Las soluciones que sugieren que edite los valores de inicio de Windows Defender para *wdboot*, *wdfilter*, *wdnisdrv*, *wdnissvc* y *windefend* en HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services no son compatibles y pueden forzarle a volver *a* crear una imagen del sistema.</span><span class="sxs-lookup"><span data-stu-id="1895d-190">Solutions suggesting that you edit the *Windows Defender* start values for *wdboot*, *wdfilter*, *wdnisdrv*, *wdnissvc*, and *windefend* in  HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services are unsupported, and may force you to re-image your system.</span></span>

<span data-ttu-id="1895d-191">El modo pasivo está disponible si empiezas a usar Microsoft Defender para Endpoint y un antivirus de terceros junto con Antivirus de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="1895d-191">Passive mode is available if you start using Microsoft Defender for Endpoint and a third-party antivirus together with Microsoft Defender Antivirus.</span></span> <span data-ttu-id="1895d-192">El modo pasivo permite a Microsoft Defender examinar archivos y actualizarse, pero no corregirá las amenazas.</span><span class="sxs-lookup"><span data-stu-id="1895d-192">Passive mode allows Microsoft Defender to scan files and update itself, but it will not remediate threats.</span></span> <span data-ttu-id="1895d-193">Además, la supervisión del comportamiento a través de la Protección en tiempo [real](configure-real-time-protection-microsoft-defender-antivirus.md) no está disponible en modo pasivo, a menos que se implemente prevención de pérdida de datos de extremo [(DLP).](/microsoft-365/security/defender-endpoint/information-protection-in-windows-overview)</span><span class="sxs-lookup"><span data-stu-id="1895d-193">In addition, behavior monitoring via [Real Time Protection](configure-real-time-protection-microsoft-defender-antivirus.md) is not available under passive mode, unless [Endpoint data loss prevention (DLP)](/microsoft-365/security/defender-endpoint/information-protection-in-windows-overview) is deployed.</span></span>

<span data-ttu-id="1895d-194">Otra característica, conocida como [examen periódico limitado,](limited-periodic-scanning-microsoft-defender-antivirus.md)está disponible para los usuarios finales cuando Antivirus de Microsoft Defender se configura para desactivarse automáticamente.</span><span class="sxs-lookup"><span data-stu-id="1895d-194">Another feature, known as [limited periodic scanning](limited-periodic-scanning-microsoft-defender-antivirus.md), is available to end-users when Microsoft Defender Antivirus is set to automatically turn off.</span></span> <span data-ttu-id="1895d-195">Esta característica permite Antivirus de Microsoft Defender archivos periódicamente junto con un antivirus de terceros, con un número limitado de detecciones.</span><span class="sxs-lookup"><span data-stu-id="1895d-195">This feature allows Microsoft Defender Antivirus to scan files periodically alongside a third-party antivirus, using a limited number of detections.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1895d-196">No se recomienda el examen periódico limitado en entornos empresariales.</span><span class="sxs-lookup"><span data-stu-id="1895d-196">Limited periodic scanning is not recommended in enterprise environments.</span></span> <span data-ttu-id="1895d-197">Las capacidades de detección, administración e informes disponibles al ejecutar Antivirus de Microsoft Defender en este modo se reducen en comparación con el modo activo.</span><span class="sxs-lookup"><span data-stu-id="1895d-197">The detection, management and reporting capabilities available when running Microsoft Defender Antivirus in this mode are reduced as compared to active mode.</span></span>

### <a name="see-also"></a><span data-ttu-id="1895d-198">Ver también</span><span class="sxs-lookup"><span data-stu-id="1895d-198">See also</span></span>

* [<span data-ttu-id="1895d-199">Antivirus de Microsoft Defender compatibilidad</span><span class="sxs-lookup"><span data-stu-id="1895d-199">Microsoft Defender Antivirus compatibility</span></span>](microsoft-defender-antivirus-compatibility.md)
* [<span data-ttu-id="1895d-200">Antivirus de Microsoft Defender en la aplicación Seguridad de Windows aplicación</span><span class="sxs-lookup"><span data-stu-id="1895d-200">Microsoft Defender Antivirus in the Windows Security app</span></span>](microsoft-defender-security-center-antivirus.md)