---
title: Ejecutar y personalizar exámenes a petición en Antivirus de Microsoft Defender
description: Ejecutar y configurar exámenes a petición con PowerShell, Windows Management Instrumentation o individualmente en puntos de conexión con la Seguridad de Windows aplicación
keywords: análisis, a petición, dos, intune, examen instantáneo
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/10/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: b2910f9fe1c49178b8696d1a421248156b0fc4c2
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925736"
---
# <a name="configure-and-run-on-demand-microsoft-defender-antivirus-scans"></a><span data-ttu-id="6ae47-104">Configurar y ejecutar análisis bajo petición en el Antivirus de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="6ae47-104">Configure and run on-demand Microsoft Defender Antivirus scans</span></span>

<span data-ttu-id="6ae47-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="6ae47-105">**Applies to:**</span></span>

- [<span data-ttu-id="6ae47-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="6ae47-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="6ae47-107">Puede ejecutar un examen a petición en puntos de conexión individuales.</span><span class="sxs-lookup"><span data-stu-id="6ae47-107">You can run an on-demand scan on individual endpoints.</span></span> <span data-ttu-id="6ae47-108">Estos exámenes se iniciarán inmediatamente y puede definir parámetros para el examen, como la ubicación o el tipo.</span><span class="sxs-lookup"><span data-stu-id="6ae47-108">These scans will start immediately, and you can define parameters for the scan, such as the location or type.</span></span> <span data-ttu-id="6ae47-109">Al ejecutar un examen, puede elegir entre tres tipos: Examen rápido, examen completo y examen personalizado.</span><span class="sxs-lookup"><span data-stu-id="6ae47-109">When you run a scan, you can choose from among three types: Quick scan, full scan, and custom scan.</span></span> <span data-ttu-id="6ae47-110">En la mayoría de los casos, use un examen rápido.</span><span class="sxs-lookup"><span data-stu-id="6ae47-110">In most cases, use a quick scan.</span></span> <span data-ttu-id="6ae47-111">Un examen rápido examina todas las ubicaciones donde podría haber malware registrado para empezar con el sistema, como las claves del Registro y las carpetas de inicio Windows de inicio.</span><span class="sxs-lookup"><span data-stu-id="6ae47-111">A quick scan looks at all the locations where there could be malware registered to start with the system, such as registry keys and known Windows startup folders.</span></span> 

<span data-ttu-id="6ae47-112">Combinado con la protección siempre activa y en tiempo real, que revisa los archivos cuando se abren y cierran, y siempre que un usuario navega a una carpeta, un examen rápido ayuda a proporcionar una protección segura contra malware que comienza con el malware del sistema y el nivel de kernel.</span><span class="sxs-lookup"><span data-stu-id="6ae47-112">Combined with always-on, real-time protection, which reviews files when they are opened and closed, and whenever a user navigates to a folder, a quick scan helps provide strong protection against malware that starts with the system and kernel-level malware.</span></span> <span data-ttu-id="6ae47-113">En la mayoría de los casos, un examen rápido es suficiente y es la opción recomendada para exámenes programados o a petición.</span><span class="sxs-lookup"><span data-stu-id="6ae47-113">In most cases, a quick scan is sufficient and is the recommended option for scheduled or on-demand scans.</span></span>  <span data-ttu-id="6ae47-114">[Obtenga más información sobre los tipos de examen](schedule-antivirus-scans.md#quick-scan-full-scan-and-custom-scan).</span><span class="sxs-lookup"><span data-stu-id="6ae47-114">[Learn more about scan types](schedule-antivirus-scans.md#quick-scan-full-scan-and-custom-scan).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6ae47-115">Antivirus de Microsoft Defender se ejecuta en el contexto de la cuenta [LocalSystem](/windows/win32/services/localsystem-account) al realizar un examen local.</span><span class="sxs-lookup"><span data-stu-id="6ae47-115">Microsoft Defender Antivirus runs in the context of the [LocalSystem](/windows/win32/services/localsystem-account) account when performing a local scan.</span></span> <span data-ttu-id="6ae47-116">Para los exámenes de red, usa el contexto de la cuenta del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6ae47-116">For network scans, it uses the context of the device account.</span></span> <span data-ttu-id="6ae47-117">Si la cuenta de dispositivo de dominio no tiene los permisos adecuados para acceder al recurso compartido, el examen no funcionará.</span><span class="sxs-lookup"><span data-stu-id="6ae47-117">If the domain device account doesn't have appropriate permissions to access the share, the scan won't work.</span></span> <span data-ttu-id="6ae47-118">Asegúrese de que el dispositivo tiene permisos para el recurso compartido de red de acceso.</span><span class="sxs-lookup"><span data-stu-id="6ae47-118">Ensure that the device has permissions to the access network share.</span></span>

## <a name="use-microsoft-endpoint-manager-to-run-a-scan"></a><span data-ttu-id="6ae47-119">Usar Microsoft Endpoint Manager para ejecutar un examen</span><span class="sxs-lookup"><span data-stu-id="6ae47-119">Use Microsoft Endpoint Manager to run a scan</span></span>

1. <span data-ttu-id="6ae47-120">Vaya al Centro Microsoft Endpoint Manager administración ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) e inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="6ae47-120">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>

2. <span data-ttu-id="6ae47-121">Elija **Endpoint security**  >  **Antivirus**.</span><span class="sxs-lookup"><span data-stu-id="6ae47-121">Choose **Endpoint security** > **Antivirus**.</span></span>

3. <span data-ttu-id="6ae47-122">En la lista de pestañas, **seleccione Windows 10 extremos en mal estado.**</span><span class="sxs-lookup"><span data-stu-id="6ae47-122">In the list of tabs, select **Windows 10 unhealthy endpoints**.</span></span>

4. <span data-ttu-id="6ae47-123">En la lista de acciones proporcionadas, seleccione **Examen rápido** (recomendado) o **Examen completo**.</span><span class="sxs-lookup"><span data-stu-id="6ae47-123">From the list of actions provided, select **Quick Scan** (recommended) or **Full Scan**.</span></span>

<span data-ttu-id="6ae47-124">[![IMAGE ](images/mem-antivirus-scan-on-demand.png)](images/mem-antivirus-scan-on-demand.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="6ae47-124">[ ![IMAGE](images/mem-antivirus-scan-on-demand.png) ](images/mem-antivirus-scan-on-demand.png#lightbox)</span></span>

> [!TIP]
> <span data-ttu-id="6ae47-125">Para obtener más información acerca del Microsoft Endpoint Manager para ejecutar un examen, vea [Antimalware and firewall tasks: How to perform an on-demand scan](/configmgr/protect/deploy-use/endpoint-antimalware-firewall#how-to-perform-an-on-demand-scan-of-computers).</span><span class="sxs-lookup"><span data-stu-id="6ae47-125">For more information about using Microsoft Endpoint Manager to run a scan, see [Antimalware and firewall tasks: How to perform an on-demand scan](/configmgr/protect/deploy-use/endpoint-antimalware-firewall#how-to-perform-an-on-demand-scan-of-computers).</span></span>

## <a name="use-the-mpcmdrunexe-command-line-utility-to-run-a-scan"></a><span data-ttu-id="6ae47-126">Usar la utilidad mpcmdrun.exe línea de comandos para ejecutar un examen</span><span class="sxs-lookup"><span data-stu-id="6ae47-126">Use the mpcmdrun.exe command-line utility to run a scan</span></span>

<span data-ttu-id="6ae47-127">Use el parámetro `-scan` siguiente:</span><span class="sxs-lookup"><span data-stu-id="6ae47-127">Use the following `-scan` parameter:</span></span>

```console
mpcmdrun.exe -scan -scantype 1
```

<span data-ttu-id="6ae47-128">Para obtener más información acerca de cómo usar la herramienta y los parámetros adicionales, incluido el inicio de un examen completo o la definición de rutas de acceso, vea Usar la herramienta de línea de comandos mpcmdrun.exe para configurar y administrar [Antivirus de Microsoft Defender](command-line-arguments-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="6ae47-128">For more information about how to use the tool and additional parameters, including starting a full scan, or defining paths, see [Use the mpcmdrun.exe commandline tool to configure and manage Microsoft Defender Antivirus](command-line-arguments-microsoft-defender-antivirus.md).</span></span>

## <a name="use-microsoft-intune-to-run-a-scan"></a><span data-ttu-id="6ae47-129">Usar Microsoft Intune para ejecutar un examen</span><span class="sxs-lookup"><span data-stu-id="6ae47-129">Use Microsoft Intune to run a scan</span></span>

1. <span data-ttu-id="6ae47-130">Vaya al Centro Microsoft Endpoint Manager administración ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) e inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="6ae47-130">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>

2. <span data-ttu-id="6ae47-131">En la barra lateral, selecciona  >  **Dispositivos todos los dispositivos** y elige el dispositivo que quieras examinar.</span><span class="sxs-lookup"><span data-stu-id="6ae47-131">From the sidebar, select **Devices** > **All Devices** and choose the device you want to scan.</span></span>

3. <span data-ttu-id="6ae47-132">Seleccione **... Más**.</span><span class="sxs-lookup"><span data-stu-id="6ae47-132">Select **...More**.</span></span> <span data-ttu-id="6ae47-133">En las opciones, **seleccione Examen rápido** (recomendado) o Examen **completo**.</span><span class="sxs-lookup"><span data-stu-id="6ae47-133">From the options, select **Quick Scan** (recommended) or **Full Scan**.</span></span>

## <a name="use-the-windows-security-app-to-run-a-scan"></a><span data-ttu-id="6ae47-134">Usar la Seguridad de Windows para ejecutar un examen</span><span class="sxs-lookup"><span data-stu-id="6ae47-134">Use the Windows Security app to run a scan</span></span>

<span data-ttu-id="6ae47-135">Consulta [Ejecutar un examen en la aplicación Seguridad de Windows para](microsoft-defender-security-center-antivirus.md) obtener instrucciones sobre cómo ejecutar un examen en puntos de conexión individuales.</span><span class="sxs-lookup"><span data-stu-id="6ae47-135">See [Run a scan in the Windows Security app](microsoft-defender-security-center-antivirus.md) for instructions on running a scan on individual endpoints.</span></span>

## <a name="use-powershell-cmdlets-to-run-a-scan"></a><span data-ttu-id="6ae47-136">Usar cmdlets de PowerShell para ejecutar un examen</span><span class="sxs-lookup"><span data-stu-id="6ae47-136">Use PowerShell cmdlets to run a scan</span></span>

<span data-ttu-id="6ae47-137">Use el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="6ae47-137">Use the following cmdlet:</span></span>

```PowerShell
Start-MpScan
```

<span data-ttu-id="6ae47-138">Para obtener más información sobre cómo usar PowerShell con Antivirus de Microsoft Defender, vea [Use PowerShell cmdlets to configure and run Antivirus de Microsoft Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md) and Defender [cmdlets](/powershell/module/defender/).</span><span class="sxs-lookup"><span data-stu-id="6ae47-138">For more information on how to use PowerShell with Microsoft Defender Antivirus, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span>

## <a name="use-windows-management-instruction-wmi-to-run-a-scan"></a><span data-ttu-id="6ae47-139">Usar Windows de administración de documentos (WMI) para ejecutar un examen</span><span class="sxs-lookup"><span data-stu-id="6ae47-139">Use Windows Management Instruction (WMI) to run a scan</span></span>

<span data-ttu-id="6ae47-140">Use el [ **método Start**](/previous-versions/windows/desktop/defender/start-msft-mpscan) de la **MSFT_MpScan** clase.</span><span class="sxs-lookup"><span data-stu-id="6ae47-140">Use the [**Start** method](/previous-versions/windows/desktop/defender/start-msft-mpscan) of the **MSFT_MpScan** class.</span></span>

<span data-ttu-id="6ae47-141">Para obtener más información acerca de los parámetros permitidos, [vea Windows Defender API de WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="6ae47-141">For more information about which parameters are allowed, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span></span>

