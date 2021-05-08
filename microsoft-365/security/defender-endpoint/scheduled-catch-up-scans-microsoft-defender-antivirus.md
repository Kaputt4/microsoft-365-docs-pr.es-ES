---
title: Programar exámenes rápidos y completos regulares con Antivirus de Microsoft Defender
description: Configurar exámenes periódicos (programados), incluso cuándo deben ejecutarse y si se ejecutan como exámenes rápidos o completos
keywords: examen rápido, examen completo, rápido vs completo, examen de programación, diario, semanal, hora, programado, periódico, regular
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/05/2021
ms.reviewer: pauhijbr, ksarens
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 038818b711400eb16fea89573dc70664a442fc1d
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245905"
---
# <a name="configure-scheduled-quick-or-full-microsoft-defender-antivirus-scans"></a><span data-ttu-id="97cc6-104">Configurar los análisis programados rápidos o completos del Antivirus de Windows Defender</span><span class="sxs-lookup"><span data-stu-id="97cc6-104">Configure scheduled quick or full Microsoft Defender Antivirus scans</span></span>

<span data-ttu-id="97cc6-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="97cc6-105">**Applies to:**</span></span>

- [<span data-ttu-id="97cc6-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="97cc6-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)


> [!NOTE]
> <span data-ttu-id="97cc6-107">De forma predeterminada, Antivirus de Microsoft Defender busca una actualización 15 minutos antes de la hora de los exámenes programados.</span><span class="sxs-lookup"><span data-stu-id="97cc6-107">By default, Microsoft Defender Antivirus checks for an update 15 minutes before the time of any scheduled scans.</span></span> <span data-ttu-id="97cc6-108">Puede administrar [la programación de cuándo se](manage-protection-update-schedule-microsoft-defender-antivirus.md) deben descargar y aplicar las actualizaciones de protección para invalidar este valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="97cc6-108">You can [Manage the schedule for when protection updates should be downloaded and applied](manage-protection-update-schedule-microsoft-defender-antivirus.md) to override this default.</span></span> 

<span data-ttu-id="97cc6-109">Además de la protección siempre activa [](run-scan-microsoft-defender-antivirus.md) en tiempo real y los exámenes a petición, puede configurar exámenes regulares programados.</span><span class="sxs-lookup"><span data-stu-id="97cc6-109">In addition to always-on real-time protection and [on-demand](run-scan-microsoft-defender-antivirus.md) scans, you can set up regular, scheduled scans.</span></span> 

<span data-ttu-id="97cc6-110">Puede configurar el tipo de examen, cuándo debe producirse el [](manage-protection-updates-microsoft-defender-antivirus.md) examen y si el examen debe producirse después de una actualización de protección o si se está utilizando el extremo.</span><span class="sxs-lookup"><span data-stu-id="97cc6-110">You can configure the type of scan, when the scan should occur, and if the scan should occur after a [protection update](manage-protection-updates-microsoft-defender-antivirus.md) or if the endpoint is being used.</span></span> <span data-ttu-id="97cc6-111">También puede especificar cuándo deben producirse exámenes especiales para completar la corrección.</span><span class="sxs-lookup"><span data-stu-id="97cc6-111">You can also specify when special scans to complete remediation should occur.</span></span>

<span data-ttu-id="97cc6-112">En este artículo se describe cómo configurar exámenes programados con directiva de grupo, cmdlets de PowerShell y WMI.</span><span class="sxs-lookup"><span data-stu-id="97cc6-112">This article describes how to configure scheduled scans with Group Policy, PowerShell cmdlets, and WMI.</span></span> <span data-ttu-id="97cc6-113">También puede configurar exámenes de programación [con Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scheduled-scans-settings) o [Microsoft Intune](/mem/intune/configuration/device-restrictions-windows-10).</span><span class="sxs-lookup"><span data-stu-id="97cc6-113">You can also configure schedules scans with [Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scheduled-scans-settings) or [Microsoft Intune](/mem/intune/configuration/device-restrictions-windows-10).</span></span>

## <a name="to-configure-the-group-policy-settings-described-in-this-article"></a><span data-ttu-id="97cc6-114">Para configurar las opciones de directiva de grupo descritas en este artículo</span><span class="sxs-lookup"><span data-stu-id="97cc6-114">To configure the Group Policy settings described in this article</span></span>

1. <span data-ttu-id="97cc6-115">En el equipo de administración de directivas de grupo, en el Editor de directivas de grupo, vaya a Configuración del equipo Plantillas administrativas  >    >  **Windows componentes**  >  **Antivirus de Microsoft Defender**  >  **Examinar**.</span><span class="sxs-lookup"><span data-stu-id="97cc6-115">On your Group Policy management machine, in the Group Policy Editor, go to **Computer configuration** > **Administrative Templates** > **Windows Components** > **Microsoft Defender Antivirus** > **Scan**.</span></span>

2. <span data-ttu-id="97cc6-116">Haga clic con el botón secundario en el objeto de directiva de grupo que desea configurar y, a continuación, **seleccione Editar**.</span><span class="sxs-lookup"><span data-stu-id="97cc6-116">Right-click the Group Policy Object you want to configure, and then select **Edit**.</span></span>

3. <span data-ttu-id="97cc6-117">Especifique la configuración del objeto de directiva de grupo y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="97cc6-117">Specify settings for the Group Policy Object, and then select **OK**.</span></span> 

4. <span data-ttu-id="97cc6-118">Repita los pasos del 1 al 4 para cada configuración que desee configurar.</span><span class="sxs-lookup"><span data-stu-id="97cc6-118">Repeat steps 1-4 for each setting you want to configure.</span></span>

5. <span data-ttu-id="97cc6-119">Implemente el objeto de directiva de grupo como lo hace normalmente.</span><span class="sxs-lookup"><span data-stu-id="97cc6-119">Deploy your Group Policy Object as you normally do.</span></span> <span data-ttu-id="97cc6-120">Si necesita ayuda con objetos de directiva de grupo, vea [Crear un objeto de directiva de grupo](/windows/security/threat-protection/windows-firewall/create-a-group-policy-object).</span><span class="sxs-lookup"><span data-stu-id="97cc6-120">If you need help with Group Policy Objects, see [Create a Group Policy Object](/windows/security/threat-protection/windows-firewall/create-a-group-policy-object).</span></span>

<span data-ttu-id="97cc6-121">Vea también administrar cuándo [se deben](manage-protection-update-schedule-microsoft-defender-antivirus.md) descargar y aplicar las actualizaciones de protección y Evitar o permitir que los usuarios [modifiquen localmente los](configure-local-policy-overrides-microsoft-defender-antivirus.md) temas de configuración de directivas.</span><span class="sxs-lookup"><span data-stu-id="97cc6-121">Also see the [Manage when protection updates should be downloaded and applied](manage-protection-update-schedule-microsoft-defender-antivirus.md) and [Prevent or allow users to locally modify policy settings](configure-local-policy-overrides-microsoft-defender-antivirus.md) topics.</span></span>

## <a name="quick-scan-versus-full-scan-and-custom-scan"></a><span data-ttu-id="97cc6-122">Examen rápido frente a examen completo y examen personalizado</span><span class="sxs-lookup"><span data-stu-id="97cc6-122">Quick scan versus full scan and custom scan</span></span>

<span data-ttu-id="97cc6-123">Al configurar exámenes programados, puede configurar si el examen debe ser un examen completo o rápido.</span><span class="sxs-lookup"><span data-stu-id="97cc6-123">When you set up scheduled scans, you can set up whether the scan should be a full or quick scan.</span></span>


|<span data-ttu-id="97cc6-124">Examen rápido</span><span class="sxs-lookup"><span data-stu-id="97cc6-124">Quick scan</span></span>  |<span data-ttu-id="97cc6-125">Examen completo</span><span class="sxs-lookup"><span data-stu-id="97cc6-125">Full scan</span></span>  | <span data-ttu-id="97cc6-126">Examen personalizado</span><span class="sxs-lookup"><span data-stu-id="97cc6-126">Custom scan</span></span> |
|---------|---------|---------|
|<span data-ttu-id="97cc6-127">Un examen rápido examina todas las ubicaciones donde podría haber malware registrado para empezar con el sistema, como las claves del Registro y las carpetas de inicio Windows de inicio.</span><span class="sxs-lookup"><span data-stu-id="97cc6-127">A quick scan looks at all the locations where there could be malware registered to start with the system, such as registry keys and known Windows startup folders.</span></span> <p><span data-ttu-id="97cc6-128">En la mayoría de los casos, un examen rápido es suficiente y se recomienda para exámenes programados.</span><span class="sxs-lookup"><span data-stu-id="97cc6-128">In most cases, a quick scan is sufficient and is recommended for scheduled scans.</span></span> |<span data-ttu-id="97cc6-129">Un examen completo comienza ejecutando un examen rápido y, a continuación, continúa con un examen secuencial de archivos de todos los discos fijos montados y unidades extraíbles/de red (si el examen completo está configurado para hacerlo).</span><span class="sxs-lookup"><span data-stu-id="97cc6-129">A full scan starts by running a quick scan and then continues with a sequential file scan of all mounted fixed disks and removable/network drives (if the full scan is configured to do so).</span></span> <p><span data-ttu-id="97cc6-130">Un examen completo puede tardar unas horas o días en completarse, según la cantidad y el tipo de datos que se deben examinar.</span><span class="sxs-lookup"><span data-stu-id="97cc6-130">A full scan can take a few hours or days to complete, depending on the amount and type of data that needs to be scanned.</span></span><p><span data-ttu-id="97cc6-131">Cuando se completa el examen completo, hay nueva inteligencia de seguridad disponible y se requiere un nuevo examen para asegurarse de que no se detecten otras amenazas con la nueva inteligencia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="97cc6-131">When the full scan is complete, new security intelligence is available, and a new scan is required to make sure that no other threats are detected with the new security intelligence.</span></span>   | <span data-ttu-id="97cc6-132">Un examen personalizado es un examen rápido que se ejecuta en los archivos y carpetas que especifique.</span><span class="sxs-lookup"><span data-stu-id="97cc6-132">A custom scan is a quick scan that runs on the files and folders you specify.</span></span> <span data-ttu-id="97cc6-133">Por ejemplo, puedes optar por examinar una unidad USB o una carpeta específica en la unidad local del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="97cc6-133">For example, you can opt to scan a USB drive, or a specific folder on your device's local drive.</span></span> <p> | 

>[!NOTE]
><span data-ttu-id="97cc6-134">De forma predeterminada, los exámenes rápidos se ejecutan en dispositivos extraíbles montados, como unidades USB.</span><span class="sxs-lookup"><span data-stu-id="97cc6-134">By default, quick scans run on mounted removable devices, such as USB drives.</span></span>

### <a name="how-do-i-know-which-scan-type-to-choose"></a><span data-ttu-id="97cc6-135">¿Cómo sé qué tipo de examen elegir?</span><span class="sxs-lookup"><span data-stu-id="97cc6-135">How do I know which scan type to choose?</span></span>

<span data-ttu-id="97cc6-136">Use la tabla siguiente para elegir un tipo de examen.</span><span class="sxs-lookup"><span data-stu-id="97cc6-136">Use the following table to choose a scan type.</span></span>


|<span data-ttu-id="97cc6-137">Escenario</span><span class="sxs-lookup"><span data-stu-id="97cc6-137">Scenario</span></span>  |<span data-ttu-id="97cc6-138">Tipo de examen recomendado</span><span class="sxs-lookup"><span data-stu-id="97cc6-138">Recommended scan type</span></span>  |
|---------|---------|
|<span data-ttu-id="97cc6-139">Desea configurar exámenes regulares y programados</span><span class="sxs-lookup"><span data-stu-id="97cc6-139">You want to set up regular, scheduled scans</span></span>     | <span data-ttu-id="97cc6-140">Examen rápido</span><span class="sxs-lookup"><span data-stu-id="97cc6-140">Quick scan</span></span> <p><span data-ttu-id="97cc6-141">Un examen rápido comprueba los procesos, la memoria, los perfiles y determinadas ubicaciones del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="97cc6-141">A quick scan checks the processes, memory, profiles, and certain locations on the device.</span></span> <span data-ttu-id="97cc6-142">Combinado con la protección siempre activa en tiempo [real,](configure-real-time-protection-microsoft-defender-antivirus.md)un examen rápido ayuda a proporcionar una cobertura sólida tanto para malware que comienza con el malware del sistema como del nivel de kernel.</span><span class="sxs-lookup"><span data-stu-id="97cc6-142">Combined with [always-on real-time protection](configure-real-time-protection-microsoft-defender-antivirus.md), a quick scan helps provide strong coverage both for malware that starts with the system and kernel-level malware.</span></span> <span data-ttu-id="97cc6-143">La protección en tiempo real revisa los archivos cuando se abren y cierran, y siempre que un usuario navega a una carpeta.</span><span class="sxs-lookup"><span data-stu-id="97cc6-143">Real-time protection reviews files when they are opened and closed, and whenever a user navigates to a folder.</span></span>         |
|<span data-ttu-id="97cc6-144">Las amenazas, como el malware, se detectan en un dispositivo</span><span class="sxs-lookup"><span data-stu-id="97cc6-144">Threats, such as malware, are detected on a device</span></span>     | <span data-ttu-id="97cc6-145">Examen completo</span><span class="sxs-lookup"><span data-stu-id="97cc6-145">Full scan</span></span> <p><span data-ttu-id="97cc6-146">Un examen completo puede ayudar a identificar si hay componentes inactivos que requieren una limpieza más exhaustiva.</span><span class="sxs-lookup"><span data-stu-id="97cc6-146">A full scan can help identify whether there are any inactive components that require a more thorough clean-up.</span></span>         |
|<span data-ttu-id="97cc6-147">Desea ejecutar un examen a [petición](run-scan-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="97cc6-147">You want to run an [on-demand scan](run-scan-microsoft-defender-antivirus.md)</span></span>     | <span data-ttu-id="97cc6-148">Examen completo</span><span class="sxs-lookup"><span data-stu-id="97cc6-148">Full scan</span></span>  <p><span data-ttu-id="97cc6-149">Un examen completo examina todos los archivos del disco del dispositivo, incluidos los archivos obsoletos, archivados y a los que no se accede diariamente.</span><span class="sxs-lookup"><span data-stu-id="97cc6-149">A full scan looks at all files on the device disk, including files that are stale, archived, and not accessed on a daily basis.</span></span>      |
| <span data-ttu-id="97cc6-150">Quieres asegurarte de que un dispositivo portátil, como una unidad USB, no contiene malware</span><span class="sxs-lookup"><span data-stu-id="97cc6-150">You want to make sure a portable device, such as a USB drive, does not contain malware</span></span> | <span data-ttu-id="97cc6-151">Examen personalizado</span><span class="sxs-lookup"><span data-stu-id="97cc6-151">Custom scan</span></span> <p><span data-ttu-id="97cc6-152">Un examen personalizado permite seleccionar ubicaciones, carpetas o archivos específicos y ejecuta un examen rápido.</span><span class="sxs-lookup"><span data-stu-id="97cc6-152">A custom scan enables you to select specific locations, folders, or files and runs a quick scan.</span></span> |

### <a name="what-else-do-i-need-to-know-about-quick-and-full-scans"></a><span data-ttu-id="97cc6-153">¿Qué más necesito saber sobre los exámenes rápidos y completos?</span><span class="sxs-lookup"><span data-stu-id="97cc6-153">What else do I need to know about quick and full scans?</span></span>

- <span data-ttu-id="97cc6-154">Los archivos malintencionados se pueden almacenar en ubicaciones que no se incluyen en un examen rápido.</span><span class="sxs-lookup"><span data-stu-id="97cc6-154">Malicious files can be stored in locations that are not included in a quick scan.</span></span> <span data-ttu-id="97cc6-155">Sin embargo, la protección siempre activa en tiempo real revisa todos los archivos que se abren y cierran y los archivos que se encuentran en carpetas a las que un usuario tiene acceso.</span><span class="sxs-lookup"><span data-stu-id="97cc6-155">However, always-on real-time protection reviews all files that are opened and closed, and any files that are in folders that are accessed by a user.</span></span> <span data-ttu-id="97cc6-156">La combinación de protección en tiempo real y un examen rápido ayuda a proporcionar una protección segura contra malware.</span><span class="sxs-lookup"><span data-stu-id="97cc6-156">The combination of real-time protection and a quick scan helps provide strong protection against malware.</span></span>

- <span data-ttu-id="97cc6-157">La protección en tiempo de acceso [con](cloud-protection-microsoft-defender-antivirus.md) protección entregada en la nube ayuda a garantizar que todos los archivos a los que se accede en el sistema se examinan con los modelos de inteligencia de seguridad y aprendizaje automático en la nube más recientes.</span><span class="sxs-lookup"><span data-stu-id="97cc6-157">On-access protection with [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) helps ensure that all the files accessed on the system are being scanned with the latest security intelligence and cloud machine learning models.</span></span>

- <span data-ttu-id="97cc6-158">Cuando la protección en tiempo real detecta malware y el alcance de los archivos afectados no se determina inicialmente, Antivirus de Microsoft Defender inicia un examen completo como parte del proceso de corrección.</span><span class="sxs-lookup"><span data-stu-id="97cc6-158">When real-time protection detects malware and the extent of the affected files is not determined initially, Microsoft Defender Antivirus initiates a full scan as part of the remediation process.</span></span>

- <span data-ttu-id="97cc6-159">Un examen completo puede detectar archivos malintencionados que no fueron detectados por otros exámenes, como un examen rápido.</span><span class="sxs-lookup"><span data-stu-id="97cc6-159">A full scan can detect malicious files that were not detected by other scans, such as a quick scan.</span></span> <span data-ttu-id="97cc6-160">Sin embargo, un examen completo puede tardar un tiempo y usar valiosos recursos del sistema para completarse.</span><span class="sxs-lookup"><span data-stu-id="97cc6-160">However, a full scan can take a while and use valuable system resources to complete.</span></span>

- <span data-ttu-id="97cc6-161">Si un dispositivo está sin conexión durante un período prolongado de tiempo, un examen completo puede tardar más tiempo en completarse.</span><span class="sxs-lookup"><span data-stu-id="97cc6-161">If a device is offline for an extended period of time, a full scan can take longer to complete.</span></span> 

## <a name="set-up-scheduled-scans"></a><span data-ttu-id="97cc6-162">Configurar exámenes programados</span><span class="sxs-lookup"><span data-stu-id="97cc6-162">Set up scheduled scans</span></span>

<span data-ttu-id="97cc6-163">Los exámenes programados se ejecutan en el día y la hora que especifique.</span><span class="sxs-lookup"><span data-stu-id="97cc6-163">Scheduled scans run on the day and time that you specify.</span></span> <span data-ttu-id="97cc6-164">Puede usar la directiva de grupo, PowerShell y WMI para configurar exámenes programados.</span><span class="sxs-lookup"><span data-stu-id="97cc6-164">You can use Group Policy, PowerShell, and WMI to configure scheduled scans.</span></span>

> [!NOTE]
> <span data-ttu-id="97cc6-165">Si un dispositivo se desconecta y se ejecuta en la batería durante un examen completo programado, el examen programado se detendrá con el evento 1002, que indica que el examen se detuvo antes de finalizar.</span><span class="sxs-lookup"><span data-stu-id="97cc6-165">If a device is unplugged and running on battery during a scheduled full scan, the scheduled scan will stop with event 1002, which states that the scan stopped before completion.</span></span> <span data-ttu-id="97cc6-166">Antivirus de Microsoft Defender se ejecutará un examen completo en la próxima hora programada.</span><span class="sxs-lookup"><span data-stu-id="97cc6-166">Microsoft Defender Antivirus will run a full scan at the next scheduled time.</span></span>

### <a name="use-group-policy-to-schedule-scans"></a><span data-ttu-id="97cc6-167">Usar directiva de grupo para programar exámenes</span><span class="sxs-lookup"><span data-stu-id="97cc6-167">Use Group Policy to schedule scans</span></span>

|<span data-ttu-id="97cc6-168">Ubicación</span><span class="sxs-lookup"><span data-stu-id="97cc6-168">Location</span></span> | <span data-ttu-id="97cc6-169">Configuración</span><span class="sxs-lookup"><span data-stu-id="97cc6-169">Setting</span></span> | <span data-ttu-id="97cc6-170">Descripción</span><span class="sxs-lookup"><span data-stu-id="97cc6-170">Description</span></span> | <span data-ttu-id="97cc6-171">Configuración predeterminada (si no está configurada)</span><span class="sxs-lookup"><span data-stu-id="97cc6-171">Default setting (if not configured)</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="97cc6-172">Examinar</span><span class="sxs-lookup"><span data-stu-id="97cc6-172">Scan</span></span> | <span data-ttu-id="97cc6-173">Especificar el tipo de examen que se usará para un examen programado</span><span class="sxs-lookup"><span data-stu-id="97cc6-173">Specify the scan type to use for a scheduled scan</span></span> | <span data-ttu-id="97cc6-174">Examen rápido</span><span class="sxs-lookup"><span data-stu-id="97cc6-174">Quick scan</span></span> |
|<span data-ttu-id="97cc6-175">Examinar</span><span class="sxs-lookup"><span data-stu-id="97cc6-175">Scan</span></span> | <span data-ttu-id="97cc6-176">Especificar el día de la semana para ejecutar un examen programado</span><span class="sxs-lookup"><span data-stu-id="97cc6-176">Specify the day of the week to run a scheduled scan</span></span> | <span data-ttu-id="97cc6-177">Especifique el día (o nunca) para ejecutar un examen.</span><span class="sxs-lookup"><span data-stu-id="97cc6-177">Specify the day (or never) to run a scan.</span></span> | <span data-ttu-id="97cc6-178">Nunca</span><span class="sxs-lookup"><span data-stu-id="97cc6-178">Never</span></span> |
|<span data-ttu-id="97cc6-179">Examinar</span><span class="sxs-lookup"><span data-stu-id="97cc6-179">Scan</span></span> | <span data-ttu-id="97cc6-180">Especificar la hora del día para ejecutar un examen programado</span><span class="sxs-lookup"><span data-stu-id="97cc6-180">Specify the time of day to run a scheduled scan</span></span> | <span data-ttu-id="97cc6-181">Especifique el número de minutos después de medianoche (por ejemplo, escriba **60** para la 1 a.m.).</span><span class="sxs-lookup"><span data-stu-id="97cc6-181">Specify the number of minutes after midnight (for example, enter **60** for 1 a.m.).</span></span> | <span data-ttu-id="97cc6-182">2 a. m.</span><span class="sxs-lookup"><span data-stu-id="97cc6-182">2 a.m.</span></span> |
|<span data-ttu-id="97cc6-183">Raíz</span><span class="sxs-lookup"><span data-stu-id="97cc6-183">Root</span></span> | <span data-ttu-id="97cc6-184">Randomize scheduled task times</span><span class="sxs-lookup"><span data-stu-id="97cc6-184">Randomize scheduled task times</span></span> |<span data-ttu-id="97cc6-185">En Antivirus de Microsoft Defender, aleatorice la hora de inicio del examen a cualquier intervalo de 0 a 4 horas.</span><span class="sxs-lookup"><span data-stu-id="97cc6-185">In Microsoft Defender Antivirus, randomize the start time of the scan to any interval from 0 to 4 hours.</span></span> <p><span data-ttu-id="97cc6-186">En [SCEP,](/mem/intune/protect/certificates-scep-configure)aleatorice los exámenes a cualquier intervalo más o menos 30 minutos.</span><span class="sxs-lookup"><span data-stu-id="97cc6-186">In [SCEP](/mem/intune/protect/certificates-scep-configure), randomize scans to any interval plus or minus 30 minutes.</span></span> <span data-ttu-id="97cc6-187">Esto puede ser útil en máquinas virtuales o implementaciones de VDI.</span><span class="sxs-lookup"><span data-stu-id="97cc6-187">This can be useful in virtual machines or VDI deployments.</span></span> | <span data-ttu-id="97cc6-188">Habilitado</span><span class="sxs-lookup"><span data-stu-id="97cc6-188">Enabled</span></span> |


### <a name="use-powershell-cmdlets-to-schedule-scans"></a><span data-ttu-id="97cc6-189">Usar cmdlets de PowerShell para programar exámenes</span><span class="sxs-lookup"><span data-stu-id="97cc6-189">Use PowerShell cmdlets to schedule scans</span></span>

<span data-ttu-id="97cc6-190">Use los cmdlets siguientes:</span><span class="sxs-lookup"><span data-stu-id="97cc6-190">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanParameters
Set-MpPreference -ScanScheduleDay
Set-MpPreference -ScanScheduleTime
Set-MpPreference -RandomizeScheduleTaskTimes

```

<span data-ttu-id="97cc6-191">Para obtener más información, vea [Use PowerShell cmdlets to configure and run Antivirus de Microsoft Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md) and Defender [cmdlets](/powershell/module/defender/) para obtener más información sobre cómo usar PowerShell con Antivirus de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="97cc6-191">For more information, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi-to-schedule-scans"></a><span data-ttu-id="97cc6-192">Usar Windows de administración de documentos (WMI) para programar exámenes</span><span class="sxs-lookup"><span data-stu-id="97cc6-192">Use Windows Management Instruction (WMI) to schedule scans</span></span>

<span data-ttu-id="97cc6-193">Utilice el [ **método Set** de la **clase MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) para las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="97cc6-193">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ScanParameters
ScanScheduleDay
ScanScheduleTime
RandomizeScheduleTaskTimes
```

<span data-ttu-id="97cc6-194">Para obtener más información y parámetros permitidos, [vea Windows Defender API wmiv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="97cc6-194">For more information and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span></span>


## <a name="start-scheduled-scans-only-when-the-endpoint-is-not-in-use"></a><span data-ttu-id="97cc6-195">Iniciar exámenes programados solo cuando el extremo no esté en uso</span><span class="sxs-lookup"><span data-stu-id="97cc6-195">Start scheduled scans only when the endpoint is not in use</span></span>

<span data-ttu-id="97cc6-196">Puede establecer que el examen programado solo se produzca cuando el extremo está activado pero no se usa con la directiva de grupo, PowerShell o WMI.</span><span class="sxs-lookup"><span data-stu-id="97cc6-196">You can set the scheduled scan to only occur when the endpoint is turned on but not in use with Group Policy, PowerShell, or WMI.</span></span>

> [!NOTE]
> <span data-ttu-id="97cc6-197">Estos exámenes no respetarán la configuración de limitación de CPU y aprovecharán al máximo los recursos disponibles para completar el examen lo más rápido posible.</span><span class="sxs-lookup"><span data-stu-id="97cc6-197">These scans will not honor the CPU throttling configuration and take full advantage of the resources available to complete the scan as fast as possible.</span></span>

### <a name="use-group-policy-to-schedule-scans"></a><span data-ttu-id="97cc6-198">Usar directiva de grupo para programar exámenes</span><span class="sxs-lookup"><span data-stu-id="97cc6-198">Use Group Policy to schedule scans</span></span>

|<span data-ttu-id="97cc6-199">Ubicación</span><span class="sxs-lookup"><span data-stu-id="97cc6-199">Location</span></span> | <span data-ttu-id="97cc6-200">Configuración</span><span class="sxs-lookup"><span data-stu-id="97cc6-200">Setting</span></span> | <span data-ttu-id="97cc6-201">Descripción</span><span class="sxs-lookup"><span data-stu-id="97cc6-201">Description</span></span> | <span data-ttu-id="97cc6-202">Configuración predeterminada (si no está configurada)</span><span class="sxs-lookup"><span data-stu-id="97cc6-202">Default setting (if not configured)</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="97cc6-203">Examinar</span><span class="sxs-lookup"><span data-stu-id="97cc6-203">Scan</span></span> | <span data-ttu-id="97cc6-204">Iniciar el examen programado solo cuando el equipo está en uso pero no está en uso</span><span class="sxs-lookup"><span data-stu-id="97cc6-204">Start the scheduled scan only when computer is on but not in use</span></span> | <span data-ttu-id="97cc6-205">Los exámenes programados no se ejecutarán, a menos que el equipo esté en uso pero no esté en uso</span><span class="sxs-lookup"><span data-stu-id="97cc6-205">Scheduled scans will not run, unless the computer is on but not in use</span></span> | <span data-ttu-id="97cc6-206">Habilitado</span><span class="sxs-lookup"><span data-stu-id="97cc6-206">Enabled</span></span> |

### <a name="use-powershell-cmdlets"></a><span data-ttu-id="97cc6-207">Usar cmdlets de PowerShell</span><span class="sxs-lookup"><span data-stu-id="97cc6-207">Use PowerShell cmdlets</span></span>

<span data-ttu-id="97cc6-208">Use los cmdlets siguientes:</span><span class="sxs-lookup"><span data-stu-id="97cc6-208">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanOnlyIfIdleEnabled
```

<span data-ttu-id="97cc6-209">Para obtener más información, vea [Use PowerShell cmdlets to configure and run Antivirus de Microsoft Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md) and Defender [cmdlets](/powershell/module/defender/).</span><span class="sxs-lookup"><span data-stu-id="97cc6-209">For more information, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span>

### <a name="use-windows-management-instruction-wmi"></a><span data-ttu-id="97cc6-210">Use Windows Management Instruction (WMI)</span><span class="sxs-lookup"><span data-stu-id="97cc6-210">Use Windows Management Instruction (WMI)</span></span>

<span data-ttu-id="97cc6-211">Utilice el [ **método Set** de la **clase MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) para las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="97cc6-211">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ScanOnlyIfIdleEnabled
```

<span data-ttu-id="97cc6-212">Para obtener más información acerca de las API y los [parámetros permitidos, vea Windows Defender API wmiv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span><span class="sxs-lookup"><span data-stu-id="97cc6-212">For more information about APIs and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

<a id="remed"></a>
## <a name="configure-when-full-scans-should-be-run-to-complete-remediation"></a><span data-ttu-id="97cc6-213">Configurar cuándo deben ejecutarse exámenes completos para completar la corrección</span><span class="sxs-lookup"><span data-stu-id="97cc6-213">Configure when full scans should be run to complete remediation</span></span>

<span data-ttu-id="97cc6-214">Algunas amenazas pueden requerir un examen completo para completar su eliminación y corrección.</span><span class="sxs-lookup"><span data-stu-id="97cc6-214">Some threats might require a full scan to complete their removal and remediation.</span></span> <span data-ttu-id="97cc6-215">Puede especificar cuándo deben producirse estos exámenes con la directiva de grupo, PowerShell o WMI.</span><span class="sxs-lookup"><span data-stu-id="97cc6-215">You can specify when these scans should occur with Group Policy, PowerShell, or WMI.</span></span>

### <a name="use-group-policy-to-schedule-remediation-required-scans"></a><span data-ttu-id="97cc6-216">Usar la directiva de grupo para programar exámenes necesarios para la corrección</span><span class="sxs-lookup"><span data-stu-id="97cc6-216">Use Group Policy to schedule remediation-required scans</span></span>

| <span data-ttu-id="97cc6-217">Ubicación</span><span class="sxs-lookup"><span data-stu-id="97cc6-217">Location</span></span> | <span data-ttu-id="97cc6-218">Configuración</span><span class="sxs-lookup"><span data-stu-id="97cc6-218">Setting</span></span> | <span data-ttu-id="97cc6-219">Descripción</span><span class="sxs-lookup"><span data-stu-id="97cc6-219">Description</span></span> | <span data-ttu-id="97cc6-220">Configuración predeterminada (si no está configurada)</span><span class="sxs-lookup"><span data-stu-id="97cc6-220">Default setting (if not configured)</span></span> |
|---|---|---|---|
|<span data-ttu-id="97cc6-221">Corrección</span><span class="sxs-lookup"><span data-stu-id="97cc6-221">Remediation</span></span> | <span data-ttu-id="97cc6-222">Especificar el día de la semana para ejecutar un examen completo programado para completar la corrección</span><span class="sxs-lookup"><span data-stu-id="97cc6-222">Specify the day of the week to run a scheduled full scan to complete remediation</span></span> | <span data-ttu-id="97cc6-223">Especifique el día (o nunca) para ejecutar un examen.</span><span class="sxs-lookup"><span data-stu-id="97cc6-223">Specify the day (or never) to run a scan.</span></span> | <span data-ttu-id="97cc6-224">Nunca</span><span class="sxs-lookup"><span data-stu-id="97cc6-224">Never</span></span> |
|<span data-ttu-id="97cc6-225">Corrección</span><span class="sxs-lookup"><span data-stu-id="97cc6-225">Remediation</span></span> | <span data-ttu-id="97cc6-226">Especificar la hora del día para ejecutar un examen completo programado para completar la corrección</span><span class="sxs-lookup"><span data-stu-id="97cc6-226">Specify the time of day to run a scheduled full scan to complete remediation</span></span> | <span data-ttu-id="97cc6-227">Especifique el número de minutos después de la medianoche (por ejemplo, escriba **60** para la 1 a.m.)</span><span class="sxs-lookup"><span data-stu-id="97cc6-227">Specify the number of minutes after midnight (for example, enter **60** for 1 a.m.)</span></span> | <span data-ttu-id="97cc6-228">2 a. m.</span><span class="sxs-lookup"><span data-stu-id="97cc6-228">2 a.m.</span></span> |

### <a name="use-powershell-cmdlets"></a><span data-ttu-id="97cc6-229">Usar cmdlets de PowerShell</span><span class="sxs-lookup"><span data-stu-id="97cc6-229">Use PowerShell cmdlets</span></span>

<span data-ttu-id="97cc6-230">Use los cmdlets siguientes:</span><span class="sxs-lookup"><span data-stu-id="97cc6-230">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -RemediationScheduleDay
Set-MpPreference -RemediationScheduleTime
```

<span data-ttu-id="97cc6-231">Consulte [Use PowerShell cmdlets to configure and run Antivirus de Microsoft Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md) and Defender [cmdlets](/powershell/module/defender/) para obtener más información sobre cómo usar PowerShell con Antivirus de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="97cc6-231">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi"></a><span data-ttu-id="97cc6-232">Use Windows Management Instruction (WMI)</span><span class="sxs-lookup"><span data-stu-id="97cc6-232">Use Windows Management Instruction (WMI)</span></span>

<span data-ttu-id="97cc6-233">Utilice el [ **método Set** de la **clase MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) para las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="97cc6-233">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
RemediationScheduleDay
RemediationScheduleTime
```

<span data-ttu-id="97cc6-234">Para obtener más información y parámetros [permitidos, vea Windows Defender API wmiv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span><span class="sxs-lookup"><span data-stu-id="97cc6-234">For more information and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>


## <a name="set-up-daily-quick-scans"></a><span data-ttu-id="97cc6-235">Configurar exámenes rápidos diarios</span><span class="sxs-lookup"><span data-stu-id="97cc6-235">Set up daily quick scans</span></span>

<span data-ttu-id="97cc6-236">Puede habilitar un examen rápido diario que se puede ejecutar además de los otros exámenes programados con la directiva de grupo, PowerShell o WMI.</span><span class="sxs-lookup"><span data-stu-id="97cc6-236">You can enable a daily quick scan that can be run in addition to your other scheduled scans with Group Policy, PowerShell, or WMI.</span></span>

### <a name="use-group-policy-to-schedule-daily-scans"></a><span data-ttu-id="97cc6-237">Usar directiva de grupo para programar exámenes diarios</span><span class="sxs-lookup"><span data-stu-id="97cc6-237">Use Group Policy to schedule daily scans</span></span>

|<span data-ttu-id="97cc6-238">Ubicación</span><span class="sxs-lookup"><span data-stu-id="97cc6-238">Location</span></span> | <span data-ttu-id="97cc6-239">Configuración</span><span class="sxs-lookup"><span data-stu-id="97cc6-239">Setting</span></span> | <span data-ttu-id="97cc6-240">Descripción</span><span class="sxs-lookup"><span data-stu-id="97cc6-240">Description</span></span> | <span data-ttu-id="97cc6-241">Configuración predeterminada (si no está configurada)</span><span class="sxs-lookup"><span data-stu-id="97cc6-241">Default setting (if not configured)</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="97cc6-242">Examinar</span><span class="sxs-lookup"><span data-stu-id="97cc6-242">Scan</span></span> | <span data-ttu-id="97cc6-243">Especificar el intervalo para ejecutar exámenes rápidos por día</span><span class="sxs-lookup"><span data-stu-id="97cc6-243">Specify the interval to run quick scans per day</span></span> | <span data-ttu-id="97cc6-244">Especifique cuántas horas debe transcurrir antes del siguiente examen rápido.</span><span class="sxs-lookup"><span data-stu-id="97cc6-244">Specify how many hours should elapse before the next quick scan.</span></span> <span data-ttu-id="97cc6-245">Por ejemplo, para ejecutarse cada dos horas, escriba **2**, para una vez al día, escriba **24**.</span><span class="sxs-lookup"><span data-stu-id="97cc6-245">For example, to run every two hours, enter **2**, for once a day, enter **24**.</span></span> <span data-ttu-id="97cc6-246">Escriba **0** para nunca ejecutar un examen rápido diario.</span><span class="sxs-lookup"><span data-stu-id="97cc6-246">Enter **0** to never run a daily quick scan.</span></span> | <span data-ttu-id="97cc6-247">Nunca</span><span class="sxs-lookup"><span data-stu-id="97cc6-247">Never</span></span> |
|<span data-ttu-id="97cc6-248">Examinar</span><span class="sxs-lookup"><span data-stu-id="97cc6-248">Scan</span></span> | <span data-ttu-id="97cc6-249">Especificar la hora de un examen rápido diario</span><span class="sxs-lookup"><span data-stu-id="97cc6-249">Specify the time for a daily quick scan</span></span> | <span data-ttu-id="97cc6-250">Especifique el número de minutos después de la medianoche (por ejemplo, escriba **60** para la 1 a.m.)</span><span class="sxs-lookup"><span data-stu-id="97cc6-250">Specify the number of minutes after midnight (for example, enter **60** for 1 a.m.)</span></span> | <span data-ttu-id="97cc6-251">2 a. m.</span><span class="sxs-lookup"><span data-stu-id="97cc6-251">2 a.m.</span></span> |

### <a name="use-powershell-cmdlets-to-schedule-daily-scans"></a><span data-ttu-id="97cc6-252">Usar cmdlets de PowerShell para programar exámenes diarios</span><span class="sxs-lookup"><span data-stu-id="97cc6-252">Use PowerShell cmdlets to schedule daily scans</span></span>

<span data-ttu-id="97cc6-253">Use los cmdlets siguientes:</span><span class="sxs-lookup"><span data-stu-id="97cc6-253">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanScheduleQuickScanTime
```

<span data-ttu-id="97cc6-254">Para obtener más información acerca de cómo usar PowerShell con Antivirus de Microsoft Defender, vea [Use PowerShell cmdlets to configure and run Antivirus de Microsoft Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md) and Defender [cmdlets](/powershell/module/defender/).</span><span class="sxs-lookup"><span data-stu-id="97cc6-254">For more information about how to use PowerShell with Microsoft Defender Antivirus, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span>

### <a name="use-windows-management-instruction-wmi-to-schedule-daily-scans"></a><span data-ttu-id="97cc6-255">Usar Windows de administración de documentos (WMI) para programar exámenes diarios</span><span class="sxs-lookup"><span data-stu-id="97cc6-255">Use Windows Management Instruction (WMI) to schedule daily scans</span></span>

<span data-ttu-id="97cc6-256">Utilice el [ **método Set** de la **clase MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) para las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="97cc6-256">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ScanScheduleQuickScanTime
```

<span data-ttu-id="97cc6-257">Para obtener más información y parámetros [permitidos, vea Windows Defender API wmiv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span><span class="sxs-lookup"><span data-stu-id="97cc6-257">For more information and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>


## <a name="enable-scans-after-protection-updates"></a><span data-ttu-id="97cc6-258">Habilitar exámenes después de actualizaciones de protección</span><span class="sxs-lookup"><span data-stu-id="97cc6-258">Enable scans after protection updates</span></span>

<span data-ttu-id="97cc6-259">Puede forzar que se produzca un examen después de cada actualización [de protección con](manage-protection-updates-microsoft-defender-antivirus.md) la directiva de grupo.</span><span class="sxs-lookup"><span data-stu-id="97cc6-259">You can force a scan to occur after every [protection update](manage-protection-updates-microsoft-defender-antivirus.md) with Group Policy.</span></span>

### <a name="use-group-policy-to-schedule-scans-after-protection-updates"></a><span data-ttu-id="97cc6-260">Usar la directiva de grupo para programar exámenes después de las actualizaciones de protección</span><span class="sxs-lookup"><span data-stu-id="97cc6-260">Use Group Policy to schedule scans after protection updates</span></span>

|<span data-ttu-id="97cc6-261">Ubicación</span><span class="sxs-lookup"><span data-stu-id="97cc6-261">Location</span></span> | <span data-ttu-id="97cc6-262">Configuración</span><span class="sxs-lookup"><span data-stu-id="97cc6-262">Setting</span></span> | <span data-ttu-id="97cc6-263">Descripción</span><span class="sxs-lookup"><span data-stu-id="97cc6-263">Description</span></span> | <span data-ttu-id="97cc6-264">Configuración predeterminada (si no está configurada)</span><span class="sxs-lookup"><span data-stu-id="97cc6-264">Default setting (if not configured)</span></span>|
|:---|:---|:---|:---|
|<span data-ttu-id="97cc6-265">Actualizaciones de firmas</span><span class="sxs-lookup"><span data-stu-id="97cc6-265">Signature updates</span></span> | <span data-ttu-id="97cc6-266">Activar el examen después de la actualización de inteligencia de seguridad</span><span class="sxs-lookup"><span data-stu-id="97cc6-266">Turn on scan after Security intelligence update</span></span> | <span data-ttu-id="97cc6-267">Un examen se realizará inmediatamente después de descargar una nueva actualización de protección</span><span class="sxs-lookup"><span data-stu-id="97cc6-267">A scan will occur immediately after a new protection update is downloaded</span></span> | <span data-ttu-id="97cc6-268">Habilitado</span><span class="sxs-lookup"><span data-stu-id="97cc6-268">Enabled</span></span> |

## <a name="see-also"></a><span data-ttu-id="97cc6-269">Vea también</span><span class="sxs-lookup"><span data-stu-id="97cc6-269">See also</span></span>

- [<span data-ttu-id="97cc6-270">Impedir o permitir que los usuarios modifiquen localmente la configuración de directiva</span><span class="sxs-lookup"><span data-stu-id="97cc6-270">Prevent or allow users to locally modify policy settings</span></span>](configure-local-policy-overrides-microsoft-defender-antivirus.md)
- [<span data-ttu-id="97cc6-271">Configurar y ejecutar análisis bajo petición en el Antivirus de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="97cc6-271">Configure and run on-demand Microsoft Defender Antivirus scans</span></span>](run-scan-microsoft-defender-antivirus.md)
- [<span data-ttu-id="97cc6-272">Configurar opciones de análisis del Antivirus de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="97cc6-272">Configure Microsoft Defender Antivirus scanning options</span></span>](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [<span data-ttu-id="97cc6-273">Administrar Antivirus de Microsoft Defender actualizaciones y aplicar líneas base</span><span class="sxs-lookup"><span data-stu-id="97cc6-273">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>](manage-updates-baselines-microsoft-defender-antivirus.md)
- [<span data-ttu-id="97cc6-274">Administrar cuándo se deben descargar y aplicar las actualizaciones de protección</span><span class="sxs-lookup"><span data-stu-id="97cc6-274">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) 
- [<span data-ttu-id="97cc6-275">Antivirus de Microsoft Defender en Windows 10</span><span class="sxs-lookup"><span data-stu-id="97cc6-275">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)