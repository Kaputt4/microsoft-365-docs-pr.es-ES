---
title: Ejecutar y personalizar exámenes a petición en Antivirus de Microsoft Defender
description: Ejecutar y configurar exámenes a petición con PowerShell, Windows Management Instrumentation o individualmente en puntos de conexión con la Seguridad de Windows aplicación
keywords: análisis, a petición, dos, intune, examen instantáneo
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/04/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: fdca059633ab0993e07b5b1be0c6f33cfe327fcf
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789176"
---
# <a name="configure-and-run-on-demand-microsoft-defender-antivirus-scans"></a><span data-ttu-id="dba50-104">Configurar y ejecutar análisis bajo petición en el Antivirus de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="dba50-104">Configure and run on-demand Microsoft Defender Antivirus scans</span></span>

<span data-ttu-id="dba50-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="dba50-105">**Applies to:**</span></span>

- [<span data-ttu-id="dba50-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="dba50-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="dba50-107">Puede ejecutar un examen a petición en puntos de conexión individuales.</span><span class="sxs-lookup"><span data-stu-id="dba50-107">You can run an on-demand scan on individual endpoints.</span></span> <span data-ttu-id="dba50-108">Estos exámenes se iniciarán inmediatamente y puede definir parámetros para el examen, como la ubicación o el tipo.</span><span class="sxs-lookup"><span data-stu-id="dba50-108">These scans will start immediately, and you can define parameters for the scan, such as the location or type.</span></span>

## <a name="quick-scan-versus-full-scan"></a><span data-ttu-id="dba50-109">Examen rápido frente a examen completo</span><span class="sxs-lookup"><span data-stu-id="dba50-109">Quick scan versus full scan</span></span>

<span data-ttu-id="dba50-110">El examen rápido examina todas las ubicaciones en las que podría haber malware registrado para empezar con el sistema, como las claves del Registro y las carpetas de inicio Windows de inicio.</span><span class="sxs-lookup"><span data-stu-id="dba50-110">Quick scan looks at all the locations where there could be malware registered to start with the system, such as registry keys and known Windows startup folders.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dba50-111">Antivirus de Microsoft Defender se ejecuta en el contexto de la cuenta [LocalSystem](/windows/win32/services/localsystem-account) al realizar un examen local.</span><span class="sxs-lookup"><span data-stu-id="dba50-111">Microsoft Defender Antivirus runs in the context of the [LocalSystem](/windows/win32/services/localsystem-account) account when performing a local scan.</span></span> <span data-ttu-id="dba50-112">Para los exámenes de red, usa el contexto de la cuenta del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="dba50-112">For network scans, it uses the context of the device account.</span></span> <span data-ttu-id="dba50-113">Si la cuenta de dispositivo de dominio no tiene los permisos adecuados para acceder al recurso compartido, el examen no funcionará.</span><span class="sxs-lookup"><span data-stu-id="dba50-113">If the domain device account doesn't have appropriate permissions to access the share, the scan won't work.</span></span> <span data-ttu-id="dba50-114">Asegúrese de que el dispositivo tiene permisos para el recurso compartido de red de acceso.</span><span class="sxs-lookup"><span data-stu-id="dba50-114">Ensure that the device has permissions to the access network share.</span></span>

<span data-ttu-id="dba50-115">Combinado con [la funcionalidad de protección](configure-real-time-protection-microsoft-defender-antivirus.md)en tiempo real siempre activa, un examen rápido ayuda a proporcionar una cobertura sólida tanto para malware que comienza con el malware del sistema como del nivel de kernel.</span><span class="sxs-lookup"><span data-stu-id="dba50-115">Combined with [always-on real-time protection capability](configure-real-time-protection-microsoft-defender-antivirus.md), a quick scan helps provide strong coverage both for malware that starts with the system and kernel-level malware.</span></span> <span data-ttu-id="dba50-116">La protección siempre activa y en tiempo real revisa los archivos cuando se abren y cierran, y siempre que un usuario navega a una carpeta.</span><span class="sxs-lookup"><span data-stu-id="dba50-116">Always-on, real-time protection reviews files when they're opened and closed, and whenever a user navigates to a folder.</span></span> <span data-ttu-id="dba50-117">De forma predeterminada, los exámenes rápidos se ejecutan en dispositivos extraíbles montados, como unidades USB.</span><span class="sxs-lookup"><span data-stu-id="dba50-117">By default, quick scans run on mounted removable devices, such as USB drives.</span></span> <span data-ttu-id="dba50-118">En la mayoría de los casos, un examen rápido es adecuado para encontrar malware que no fue recogido por la protección en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="dba50-118">In most instances, a quick scan is adequate to find malware that wasn't picked up by real-time protection.</span></span>

<span data-ttu-id="dba50-119">Un examen completo puede ser útil cuando se notifica una amenaza de malware en un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="dba50-119">A full scan can be useful when a malware threat is reported on an endpoint.</span></span> <span data-ttu-id="dba50-120">El examen puede identificar si hay componentes inactivos que requieren una limpieza más exhaustiva.</span><span class="sxs-lookup"><span data-stu-id="dba50-120">The scan can identify whether there are any inactive components that require a more thorough clean-up.</span></span> <span data-ttu-id="dba50-121">Sin embargo, Microsoft suele recomendar el uso de exámenes rápidos en lugar de exámenes completos.</span><span class="sxs-lookup"><span data-stu-id="dba50-121">However, Microsoft generally recommends using quick scans instead of full scans.</span></span> <span data-ttu-id="dba50-122">Un examen completo puede tardar unas horas o días en completarse, según la cantidad y el tipo de datos que se deben examinar.</span><span class="sxs-lookup"><span data-stu-id="dba50-122">A full scan can take a few hours or days to complete, depending on the amount and type of data that needs to be scanned.</span></span> 

> [!TIP]
> <span data-ttu-id="dba50-123">Para obtener más información sobre las diferencias entre los exámenes rápidos y los exámenes [completos, vea Examen rápido frente al examen completo y el examen personalizado.](scheduled-catch-up-scans-microsoft-defender-antivirus.md#quick-scan-versus-full-scan-and-custom-scan)</span><span class="sxs-lookup"><span data-stu-id="dba50-123">To learn more about the differences between quick and full scans, see [Quick scan versus full scan and custom scan](scheduled-catch-up-scans-microsoft-defender-antivirus.md#quick-scan-versus-full-scan-and-custom-scan).</span></span>

## <a name="use-microsoft-endpoint-manager-to-run-a-scan"></a><span data-ttu-id="dba50-124">Usar Microsoft Endpoint Manager para ejecutar un examen</span><span class="sxs-lookup"><span data-stu-id="dba50-124">Use Microsoft Endpoint Manager to run a scan</span></span>

1. <span data-ttu-id="dba50-125">Vaya al Centro Microsoft Endpoint Manager administración ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) e inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="dba50-125">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>
2. <span data-ttu-id="dba50-126">Elija **Endpoint security**  >  **Antivirus**.</span><span class="sxs-lookup"><span data-stu-id="dba50-126">Choose **Endpoint security** > **Antivirus**.</span></span>
3. <span data-ttu-id="dba50-127">En la lista de pestañas, **seleccione Windows 10 extremos en mal estado.**</span><span class="sxs-lookup"><span data-stu-id="dba50-127">In the list of tabs, select **Windows 10 unhealthy endpoints**.</span></span>
4. <span data-ttu-id="dba50-128">En la lista de acciones proporcionadas, seleccione **Examen rápido** o **Examen completo.**</span><span class="sxs-lookup"><span data-stu-id="dba50-128">From the list of actions provided, select **Quick Scan** or **Full Scan**.</span></span>

<span data-ttu-id="dba50-129">[![IMAGE ](images/mem-antivirus-scan-on-demand.png)](images/mem-antivirus-scan-on-demand.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="dba50-129">[ ![IMAGE](images/mem-antivirus-scan-on-demand.png) ](images/mem-antivirus-scan-on-demand.png#lightbox)</span></span>

> [!TIP]
> <span data-ttu-id="dba50-130">Para obtener más información acerca del Microsoft Endpoint Manager para ejecutar un examen, vea [Antimalware and firewall tasks: How to perform an on-demand scan](/configmgr/protect/deploy-use/endpoint-antimalware-firewall#how-to-perform-an-on-demand-scan-of-computers).</span><span class="sxs-lookup"><span data-stu-id="dba50-130">For more information about using Microsoft Endpoint Manager to run a scan, see [Antimalware and firewall tasks: How to perform an on-demand scan](/configmgr/protect/deploy-use/endpoint-antimalware-firewall#how-to-perform-an-on-demand-scan-of-computers).</span></span>

## <a name="use-the-mpcmdrunexe-command-line-utility-to-run-a-scan"></a><span data-ttu-id="dba50-131">Usar la utilidad mpcmdrun.exe línea de comandos para ejecutar un examen</span><span class="sxs-lookup"><span data-stu-id="dba50-131">Use the mpcmdrun.exe command-line utility to run a scan</span></span>

<span data-ttu-id="dba50-132">Use el parámetro `-scan` siguiente:</span><span class="sxs-lookup"><span data-stu-id="dba50-132">Use the following `-scan` parameter:</span></span>

```console
mpcmdrun.exe -scan -scantype 1
```

<span data-ttu-id="dba50-133">Para obtener más información acerca de cómo usar la herramienta y los parámetros adicionales, incluido el inicio de un examen completo o la definición de rutas de acceso, vea Usar la herramienta de línea de comandos mpcmdrun.exe para configurar y administrar [Antivirus de Microsoft Defender](command-line-arguments-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="dba50-133">For more information about how to use the tool and additional parameters, including starting a full scan, or defining paths, see [Use the mpcmdrun.exe commandline tool to configure and manage Microsoft Defender Antivirus](command-line-arguments-microsoft-defender-antivirus.md).</span></span>

## <a name="use-microsoft-intune-to-run-a-scan"></a><span data-ttu-id="dba50-134">Usar Microsoft Intune para ejecutar un examen</span><span class="sxs-lookup"><span data-stu-id="dba50-134">Use Microsoft Intune to run a scan</span></span>

1. <span data-ttu-id="dba50-135">Vaya al Centro Microsoft Endpoint Manager administración ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) e inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="dba50-135">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>
2. <span data-ttu-id="dba50-136">En la barra lateral, selecciona **Dispositivos > Todos** los dispositivos y elige el dispositivo que quieras examinar.</span><span class="sxs-lookup"><span data-stu-id="dba50-136">From the sidebar, select **Devices > All Devices** and choose the device you want to scan.</span></span>
3. <span data-ttu-id="dba50-137">Seleccione **... Más**.</span><span class="sxs-lookup"><span data-stu-id="dba50-137">Select **...More**.</span></span> <span data-ttu-id="dba50-138">En las opciones, seleccione **Examen rápido** o **Examen completo**.</span><span class="sxs-lookup"><span data-stu-id="dba50-138">From the options, select **Quick Scan** or **Full Scan**.</span></span>

## <a name="use-the-windows-security-app-to-run-a-scan"></a><span data-ttu-id="dba50-139">Usar la Seguridad de Windows para ejecutar un examen</span><span class="sxs-lookup"><span data-stu-id="dba50-139">Use the Windows Security app to run a scan</span></span>

<span data-ttu-id="dba50-140">Consulta [Ejecutar un examen en la aplicación Seguridad de Windows para](microsoft-defender-security-center-antivirus.md) obtener instrucciones sobre cómo ejecutar un examen en puntos de conexión individuales.</span><span class="sxs-lookup"><span data-stu-id="dba50-140">See [Run a scan in the Windows Security app](microsoft-defender-security-center-antivirus.md) for instructions on running a scan on individual endpoints.</span></span>

## <a name="use-powershell-cmdlets-to-run-a-scan"></a><span data-ttu-id="dba50-141">Usar cmdlets de PowerShell para ejecutar un examen</span><span class="sxs-lookup"><span data-stu-id="dba50-141">Use PowerShell cmdlets to run a scan</span></span>

<span data-ttu-id="dba50-142">Use el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="dba50-142">Use the following cmdlet:</span></span>

```PowerShell
Start-MpScan
```

<span data-ttu-id="dba50-143">Para obtener más información sobre cómo usar PowerShell con Antivirus de Microsoft Defender, vea [Use PowerShell cmdlets to configure and run Antivirus de Microsoft Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md) and Defender [cmdlets](/powershell/module/defender/).</span><span class="sxs-lookup"><span data-stu-id="dba50-143">For more information on how to use PowerShell with Microsoft Defender Antivirus, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span>

## <a name="use-windows-management-instruction-wmi-to-run-a-scan"></a><span data-ttu-id="dba50-144">Usar Windows de administración de documentos (WMI) para ejecutar un examen</span><span class="sxs-lookup"><span data-stu-id="dba50-144">Use Windows Management Instruction (WMI) to run a scan</span></span>

<span data-ttu-id="dba50-145">Use el [ **método Start**](/previous-versions/windows/desktop/defender/start-msft-mpscan) de la **MSFT_MpScan** clase.</span><span class="sxs-lookup"><span data-stu-id="dba50-145">Use the [**Start** method](/previous-versions/windows/desktop/defender/start-msft-mpscan) of the **MSFT_MpScan** class.</span></span>

<span data-ttu-id="dba50-146">Para obtener más información acerca de los parámetros permitidos, [vea Windows Defender API de WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="dba50-146">For more information about which parameters are allowed, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span></span>

## <a name="related-articles"></a><span data-ttu-id="dba50-147">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="dba50-147">Related articles</span></span>

- [<span data-ttu-id="dba50-148">Configurar opciones de análisis del Antivirus de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="dba50-148">Configure Microsoft Defender Antivirus scanning options</span></span>](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [<span data-ttu-id="dba50-149">Configurar exámenes Antivirus de Microsoft Defender programados</span><span class="sxs-lookup"><span data-stu-id="dba50-149">Configure scheduled Microsoft Defender Antivirus scans</span></span>](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="dba50-150">Antivirus de Microsoft Defender en Windows 10</span><span class="sxs-lookup"><span data-stu-id="dba50-150">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)