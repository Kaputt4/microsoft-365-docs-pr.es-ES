---
title: Ejecutar y personalizar exámenes a petición en Microsoft Defender AV
description: Ejecutar y configurar exámenes a petición con PowerShell, Instrumental de administración de Windows o individualmente en puntos de conexión con la aplicación Seguridad de Windows
keywords: análisis, a petición, dos, intune, examen instantáneo
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 11/13/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 2f60bdb0bbd8b87895547e608b5c3c92414ea834
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691175"
---
# <a name="configure-and-run-on-demand-microsoft-defender-antivirus-scans"></a><span data-ttu-id="8ba8f-104">Configurar y ejecutar exámenes de Antivirus de Microsoft Defender a petición</span><span class="sxs-lookup"><span data-stu-id="8ba8f-104">Configure and run on-demand Microsoft Defender Antivirus scans</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8ba8f-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="8ba8f-105">**Applies to:**</span></span>

- [<span data-ttu-id="8ba8f-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="8ba8f-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="8ba8f-107">Puede ejecutar un examen a petición en puntos de conexión individuales.</span><span class="sxs-lookup"><span data-stu-id="8ba8f-107">You can run an on-demand scan on individual endpoints.</span></span> <span data-ttu-id="8ba8f-108">Estos exámenes se iniciarán inmediatamente y puede definir parámetros para el examen, como la ubicación o el tipo.</span><span class="sxs-lookup"><span data-stu-id="8ba8f-108">These scans will start immediately, and you can define parameters for the scan, such as the location or type.</span></span>

## <a name="quick-scan-versus-full-scan"></a><span data-ttu-id="8ba8f-109">Examen rápido frente a examen completo</span><span class="sxs-lookup"><span data-stu-id="8ba8f-109">Quick scan versus full scan</span></span>

<span data-ttu-id="8ba8f-110">El examen rápido examina todas las ubicaciones donde podría haber malware registrado para empezar con el sistema, como las claves del Registro y las carpetas de inicio conocidas de Windows.</span><span class="sxs-lookup"><span data-stu-id="8ba8f-110">Quick scan looks at all the locations where there could be malware registered to start with the system, such as registry keys and known Windows startup folders.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8ba8f-111">Antivirus de Microsoft Defender se ejecuta en el contexto de la cuenta [LocalSystem](/windows/win32/services/localsystem-account) al realizar un examen local.</span><span class="sxs-lookup"><span data-stu-id="8ba8f-111">Microsoft Defender Antivirus runs in the context of the [LocalSystem](/windows/win32/services/localsystem-account) account when performing a local scan.</span></span> <span data-ttu-id="8ba8f-112">Para los exámenes de red, usa el contexto de la cuenta del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8ba8f-112">For network scans, it uses the context of the device account.</span></span> <span data-ttu-id="8ba8f-113">Si la cuenta de dispositivo de dominio no tiene los permisos adecuados para acceder al recurso compartido, el examen no funcionará.</span><span class="sxs-lookup"><span data-stu-id="8ba8f-113">If the domain device account doesn't have appropriate permissions to access the share, the scan won't work.</span></span> <span data-ttu-id="8ba8f-114">Asegúrese de que el dispositivo tiene permisos para el recurso compartido de red de acceso.</span><span class="sxs-lookup"><span data-stu-id="8ba8f-114">Ensure that the device has permissions to the access network share.</span></span>

<span data-ttu-id="8ba8f-115">Combinado con la funcionalidad de protección siempre activa en tiempo [real](configure-real-time-protection-microsoft-defender-antivirus.md)(que revisa los archivos cuando se abren y cierran y cuando un usuario navega a una carpeta), un examen rápido ayuda a proporcionar una cobertura segura tanto para malware que comienza con el malware del sistema como del nivel de kernel.</span><span class="sxs-lookup"><span data-stu-id="8ba8f-115">Combined with [always-on real-time protection capability](configure-real-time-protection-microsoft-defender-antivirus.md)--which reviews files when they're opened and closed, and whenever a user navigates to a folder--a quick scan helps provide strong coverage both for malware that starts with the system and kernel-level malware.</span></span>  

<span data-ttu-id="8ba8f-116">En la mayoría de los casos, un examen rápido es adecuado para encontrar malware que no fue recogido por la protección en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="8ba8f-116">In most instances, a quick scan is adequate to find malware that wasn't picked up by real-time protection.</span></span>

<span data-ttu-id="8ba8f-117">Un examen completo puede ser útil en puntos de conexión que han notificado una amenaza de malware.</span><span class="sxs-lookup"><span data-stu-id="8ba8f-117">A full scan can be useful on endpoints that have reported a malware threat.</span></span> <span data-ttu-id="8ba8f-118">El examen puede identificar si hay componentes inactivos que requieren una limpieza más exhaustiva.</span><span class="sxs-lookup"><span data-stu-id="8ba8f-118">The scan can identify if there are any inactive components that require a more thorough clean-up.</span></span> <span data-ttu-id="8ba8f-119">Esto es ideal si su organización está ejecutando exámenes a petición.</span><span class="sxs-lookup"><span data-stu-id="8ba8f-119">This is  ideal if your organization is running on-demand scans.</span></span>

> [!NOTE]
> <span data-ttu-id="8ba8f-120">De forma predeterminada, los exámenes rápidos se ejecutan en dispositivos extraíbles montados, como unidades USB.</span><span class="sxs-lookup"><span data-stu-id="8ba8f-120">By default, quick scans run on mounted removable devices, such as USB drives.</span></span>

## <a name="use-microsoft-endpoint-manager-to-run-a-scan"></a><span data-ttu-id="8ba8f-121">Usar Microsoft Endpoint Manager para ejecutar un examen</span><span class="sxs-lookup"><span data-stu-id="8ba8f-121">Use Microsoft Endpoint Manager to run a scan</span></span>

1. <span data-ttu-id="8ba8f-122">Vaya al Centro de administración de Microsoft Endpoint Manager ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) e inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="8ba8f-122">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>
2. <span data-ttu-id="8ba8f-123">Elija **Endpoint security**  >  **Antivirus**.</span><span class="sxs-lookup"><span data-stu-id="8ba8f-123">Choose **Endpoint security** > **Antivirus**.</span></span>
3. <span data-ttu-id="8ba8f-124">En la lista de pestañas, selecciona Puntos de conexión en mal estado de **Windows 10.**</span><span class="sxs-lookup"><span data-stu-id="8ba8f-124">In the list of tabs, select **Windows 10 unhealthy endpoints**.</span></span>
4. <span data-ttu-id="8ba8f-125">En la lista de acciones proporcionadas, seleccione **Examen rápido** o **Examen completo.**</span><span class="sxs-lookup"><span data-stu-id="8ba8f-125">From the list of actions provided, select **Quick Scan** or **Full Scan**.</span></span>

<span data-ttu-id="8ba8f-126">[![IMAGE ](images/mem-antivirus-scan-on-demand.png)](images/mem-antivirus-scan-on-demand.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="8ba8f-126">[ ![IMAGE](images/mem-antivirus-scan-on-demand.png) ](images/mem-antivirus-scan-on-demand.png#lightbox)</span></span>

> [!TIP]
> <span data-ttu-id="8ba8f-127">Para obtener más información acerca del uso de Microsoft Endpoint Manager para ejecutar un examen, vea [Antimalware and firewall tasks: How to perform an on-demand scan](/configmgr/protect/deploy-use/endpoint-antimalware-firewall#how-to-perform-an-on-demand-scan-of-computers).</span><span class="sxs-lookup"><span data-stu-id="8ba8f-127">For more information about using Microsoft Endpoint Manager to run a scan, see [Antimalware and firewall tasks: How to perform an on-demand scan](/configmgr/protect/deploy-use/endpoint-antimalware-firewall#how-to-perform-an-on-demand-scan-of-computers).</span></span>

## <a name="use-the-mpcmdrunexe-command-line-utility-to-run-a-scan"></a><span data-ttu-id="8ba8f-128">Usar la utilidad mpcmdrun.exe línea de comandos para ejecutar un examen</span><span class="sxs-lookup"><span data-stu-id="8ba8f-128">Use the mpcmdrun.exe command-line utility to run a scan</span></span>

<span data-ttu-id="8ba8f-129">Use el parámetro `-scan` siguiente:</span><span class="sxs-lookup"><span data-stu-id="8ba8f-129">Use the following `-scan` parameter:</span></span>

```console
mpcmdrun.exe -scan -scantype 1
```

<span data-ttu-id="8ba8f-130">Para obtener más información acerca de cómo usar la herramienta y los parámetros adicionales, como iniciar un examen completo o definir rutas de acceso, vea Usar la herramienta de línea de comandos mpcmdrun.exe para configurar y administrar Antivirus de [Microsoft Defender](command-line-arguments-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="8ba8f-130">For more information about how to use the tool and additional parameters, including starting a full scan, or defining paths, see [Use the mpcmdrun.exe commandline tool to configure and manage Microsoft Defender Antivirus](command-line-arguments-microsoft-defender-antivirus.md).</span></span>

## <a name="use-microsoft-intune-to-run-a-scan"></a><span data-ttu-id="8ba8f-131">Usar Microsoft Intune para ejecutar un examen</span><span class="sxs-lookup"><span data-stu-id="8ba8f-131">Use Microsoft Intune to run a scan</span></span>

1. <span data-ttu-id="8ba8f-132">Vaya al Centro de administración de Microsoft Endpoint Manager ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) e inicie sesión.</span><span class="sxs-lookup"><span data-stu-id="8ba8f-132">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>
2. <span data-ttu-id="8ba8f-133">En la barra lateral, selecciona **Dispositivos > Todos** los dispositivos y elige el dispositivo que quieras examinar.</span><span class="sxs-lookup"><span data-stu-id="8ba8f-133">From the sidebar, select **Devices > All Devices** and choose the device you want to scan.</span></span>
3. <span data-ttu-id="8ba8f-134">Seleccione **... Más**.</span><span class="sxs-lookup"><span data-stu-id="8ba8f-134">Select **...More**.</span></span> <span data-ttu-id="8ba8f-135">En las opciones, seleccione **Examen rápido** o **Examen completo**.</span><span class="sxs-lookup"><span data-stu-id="8ba8f-135">From the options, select **Quick Scan** or **Full Scan**.</span></span>

## <a name="use-the-windows-security-app-to-run-a-scan"></a><span data-ttu-id="8ba8f-136">Usar la aplicación Seguridad de Windows para ejecutar un examen</span><span class="sxs-lookup"><span data-stu-id="8ba8f-136">Use the Windows Security app to run a scan</span></span>

<span data-ttu-id="8ba8f-137">Consulta [Ejecutar un examen en la aplicación seguridad de Windows](microsoft-defender-security-center-antivirus.md) para obtener instrucciones sobre cómo ejecutar un examen en puntos de conexión individuales.</span><span class="sxs-lookup"><span data-stu-id="8ba8f-137">See [Run a scan in the Windows Security app](microsoft-defender-security-center-antivirus.md) for instructions on running a scan on individual endpoints.</span></span>

## <a name="use-powershell-cmdlets-to-run-a-scan"></a><span data-ttu-id="8ba8f-138">Usar cmdlets de PowerShell para ejecutar un examen</span><span class="sxs-lookup"><span data-stu-id="8ba8f-138">Use PowerShell cmdlets to run a scan</span></span>

<span data-ttu-id="8ba8f-139">Use el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="8ba8f-139">Use the following cmdlet:</span></span>

```PowerShell
Start-MpScan
```

<span data-ttu-id="8ba8f-140">Para obtener más información sobre cómo usar PowerShell con Antivirus de Microsoft Defender, vea [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and Defender [cmdlets](/powershell/module/defender/).</span><span class="sxs-lookup"><span data-stu-id="8ba8f-140">For more information on how to use PowerShell with Microsoft Defender Antivirus, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span>

## <a name="use-windows-management-instruction-wmi-to-run-a-scan"></a><span data-ttu-id="8ba8f-141">Usar Windows Management Instruction (WMI) para ejecutar un examen</span><span class="sxs-lookup"><span data-stu-id="8ba8f-141">Use Windows Management Instruction (WMI) to run a scan</span></span>

<span data-ttu-id="8ba8f-142">Use el [ **método Start**](/previous-versions/windows/desktop/defender/start-msft-mpscan) de la **MSFT_MpScan** clase.</span><span class="sxs-lookup"><span data-stu-id="8ba8f-142">Use the [**Start** method](/previous-versions/windows/desktop/defender/start-msft-mpscan) of the **MSFT_MpScan** class.</span></span>

<span data-ttu-id="8ba8f-143">Para obtener más información acerca de los parámetros permitidos, [vea Windows Defender API de WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="8ba8f-143">For more information about which parameters are allowed, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span></span>

## <a name="related-articles"></a><span data-ttu-id="8ba8f-144">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="8ba8f-144">Related articles</span></span>

- [<span data-ttu-id="8ba8f-145">Configurar opciones de análisis de Antivirus de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="8ba8f-145">Configure Microsoft Defender Antivirus scanning options</span></span>](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [<span data-ttu-id="8ba8f-146">Configurar exámenes programados de Antivirus de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="8ba8f-146">Configure scheduled Microsoft Defender Antivirus scans</span></span>](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="8ba8f-147">Antivirus de Microsoft Defender en Windows 10</span><span class="sxs-lookup"><span data-stu-id="8ba8f-147">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)