---
title: Habilitar las reglas de la reducción de superficie expuesta a ataques
description: Habilita las reglas de reducción de superficie de ataque (ASR) para proteger los dispositivos de ataques que usan macros, scripts y técnicas de inserción comunes.
keywords: Reducción de superficie de ataque, caderas, sistema de prevención de intrusiones de host, reglas de protección, antiexploit, vulnerabilidad, prevención de infecciones, habilitar, activar
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: dansimp
ms.author: dansimp
ms.reviewer: oogunrinde
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: e6f3d6da2424b2b3b6b7c1f2c9973e4046d6e27f
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689174"
---
# <a name="enable-attack-surface-reduction-rules"></a><span data-ttu-id="8fb8f-104">Habilitar las reglas de la reducción de superficie expuesta a ataques</span><span class="sxs-lookup"><span data-stu-id="8fb8f-104">Enable attack surface reduction rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8fb8f-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="8fb8f-105">**Applies to:**</span></span>
- [<span data-ttu-id="8fb8f-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="8fb8f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="8fb8f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8fb8f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> <span data-ttu-id="8fb8f-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="8fb8f-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="8fb8f-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="8fb8f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="8fb8f-110">[Las reglas de reducción de superficie de](attack-surface-reduction.md) ataque (reglas ASR) ayudan a evitar acciones que el malware suele abusar de dispositivos y redes.</span><span class="sxs-lookup"><span data-stu-id="8fb8f-110">[Attack surface reduction rules](attack-surface-reduction.md) (ASR rules) help prevent actions that malware often abuses to compromise devices and networks.</span></span> <span data-ttu-id="8fb8f-111">Puedes establecer reglas ASR para dispositivos que ejecuten cualquiera de las siguientes ediciones y versiones de Windows:</span><span class="sxs-lookup"><span data-stu-id="8fb8f-111">You can set ASR rules for devices running any of the following editions and versions of Windows:</span></span>
- <span data-ttu-id="8fb8f-112">Windows 10 Pro, [versión 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) o posterior</span><span class="sxs-lookup"><span data-stu-id="8fb8f-112">Windows 10 Pro, [version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="8fb8f-113">Windows 10 Enterprise, [versión 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) o posterior</span><span class="sxs-lookup"><span data-stu-id="8fb8f-113">Windows 10 Enterprise, [version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="8fb8f-114">Windows Server, [versión 1803 (canal semianual)](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) o posterior</span><span class="sxs-lookup"><span data-stu-id="8fb8f-114">Windows Server, [version 1803 (Semi-Annual Channel)](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) or later</span></span>
- [<span data-ttu-id="8fb8f-115">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="8fb8f-115">Windows Server 2019</span></span>](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="8fb8f-116">Cada regla ASR contiene una de cuatro opciones:</span><span class="sxs-lookup"><span data-stu-id="8fb8f-116">Each ASR rule contains one of four settings:</span></span>

- <span data-ttu-id="8fb8f-117">**No configurado:** deshabilitar la regla ASR</span><span class="sxs-lookup"><span data-stu-id="8fb8f-117">**Not configured**: Disable the ASR rule</span></span>
- <span data-ttu-id="8fb8f-118">**Bloquear:** habilitar la regla ASR</span><span class="sxs-lookup"><span data-stu-id="8fb8f-118">**Block**: Enable the ASR rule</span></span>
- <span data-ttu-id="8fb8f-119">**Auditoría:** evaluar cómo la regla ASR afectaría a su organización si está habilitada</span><span class="sxs-lookup"><span data-stu-id="8fb8f-119">**Audit**: Evaluate how the ASR rule would impact your organization if enabled</span></span>
- <span data-ttu-id="8fb8f-120">**Advertencia:** habilite la regla ASR pero permita al usuario final omitir el bloque</span><span class="sxs-lookup"><span data-stu-id="8fb8f-120">**Warn**: Enable the ASR rule but alow the end user to bypass the block</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8fb8f-121">Actualmente, el modo de advertencia no es compatible con tres reglas ASR al configurar reglas ASR en Microsoft Endpoint Manager (MEM).</span><span class="sxs-lookup"><span data-stu-id="8fb8f-121">Currently, warn mode is not supported for three ASR rules when you configure ASR rules in Microsoft Endpoint Manager (MEM).</span></span> <span data-ttu-id="8fb8f-122">Para obtener más información, vea [Casos en los que no se admite el modo de advertencia](attack-surface-reduction.md#cases-where-warn-mode-is-not-supported).</span><span class="sxs-lookup"><span data-stu-id="8fb8f-122">To learn more, see [Cases where warn mode is not supported](attack-surface-reduction.md#cases-where-warn-mode-is-not-supported).</span></span>

<span data-ttu-id="8fb8f-123">Es muy recomendable usar reglas ASR con una licencia de Windows E5 (o SKU de licencia similar) para aprovechar las capacidades avanzadas de supervisión e informes disponibles en [Microsoft Defender para](https://docs.microsoft.com/windows/security/threat-protection) endpoint (Defender para endpoint).</span><span class="sxs-lookup"><span data-stu-id="8fb8f-123">It's highly recommended you use ASR rules with a Windows E5 license (or similar licensing SKU) to take advantage of the advanced monitoring and reporting capabilities available in [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) (Defender for Endpoint).</span></span> <span data-ttu-id="8fb8f-124">Sin embargo, para otras licencias como Windows Professional o E3 que no tienen acceso a funciones avanzadas de supervisión e informes, puedes desarrollar tus propias herramientas de supervisión e informes encima de los eventos que se generan en cada punto de conexión cuando se desencadenan reglas ASR (por ejemplo, reenvío de eventos).</span><span class="sxs-lookup"><span data-stu-id="8fb8f-124">However, for other licenses like Windows Professional or E3 that don't have access to advanced monitoring and reporting capabilities, you can develop your own monitoring and reporting tools on top of the events that are generated at each endpoint when ASR rules are triggered (e.g., Event Forwarding).</span></span>

> [!TIP]
> <span data-ttu-id="8fb8f-125">Para obtener más información sobre las licencias de Windows, consulta [Licencias de Windows 10](https://www.microsoft.com/licensing/product-licensing/windows10?activetab=windows10-pivot:primaryr5) y obtén la Guía de licencias por [volumen para Windows 10](https://download.microsoft.com/download/2/D/1/2D14FE17-66C2-4D4C-AF73-E122930B60F6/Windows-10-Volume-Licensing-Guide.pdf).</span><span class="sxs-lookup"><span data-stu-id="8fb8f-125">To learn more about Windows licensing, see [Windows 10 Licensing](https://www.microsoft.com/licensing/product-licensing/windows10?activetab=windows10-pivot:primaryr5) and get the [Volume Licensing guide for Windows 10](https://download.microsoft.com/download/2/D/1/2D14FE17-66C2-4D4C-AF73-E122930B60F6/Windows-10-Volume-Licensing-Guide.pdf).</span></span>

<span data-ttu-id="8fb8f-126">Puedes habilitar las reglas de reducción de superficie de ataque mediante cualquiera de estos métodos:</span><span class="sxs-lookup"><span data-stu-id="8fb8f-126">You can enable attack surface reduction rules by using any of these methods:</span></span>

- [<span data-ttu-id="8fb8f-127">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="8fb8f-127">Microsoft Intune</span></span>](#intune)
- [<span data-ttu-id="8fb8f-128">Administración de dispositivos móviles (MDM)</span><span class="sxs-lookup"><span data-stu-id="8fb8f-128">Mobile Device Management (MDM)</span></span>](#mdm)
- [<span data-ttu-id="8fb8f-129">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="8fb8f-129">Microsoft Endpoint Configuration Manager</span></span>](#microsoft-endpoint-configuration-manager)
- [<span data-ttu-id="8fb8f-130">Directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="8fb8f-130">Group Policy</span></span>](#group-policy)
- [<span data-ttu-id="8fb8f-131">PowerShell</span><span class="sxs-lookup"><span data-stu-id="8fb8f-131">PowerShell</span></span>](#powershell)

<span data-ttu-id="8fb8f-132">Se recomienda la administración de nivel de empresa, como Intune o Microsoft Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="8fb8f-132">Enterprise-level management such as Intune or Microsoft Endpoint Manager is recommended.</span></span> <span data-ttu-id="8fb8f-133">La administración de nivel de empresa sobrescribirá cualquier configuración de PowerShell o directiva de grupo en conflicto al iniciarse.</span><span class="sxs-lookup"><span data-stu-id="8fb8f-133">Enterprise-level management will overwrite any conflicting Group Policy or PowerShell settings on startup.</span></span>

## <a name="exclude-files-and-folders-from-asr-rules"></a><span data-ttu-id="8fb8f-134">Excluir archivos y carpetas de reglas ASR</span><span class="sxs-lookup"><span data-stu-id="8fb8f-134">Exclude files and folders from ASR rules</span></span>

<span data-ttu-id="8fb8f-135">Puedes excluir archivos y carpetas de ser evaluados por la mayoría de las reglas de reducción de superficie de ataque.</span><span class="sxs-lookup"><span data-stu-id="8fb8f-135">You can exclude files and folders from being evaluated by most attack surface reduction rules.</span></span> <span data-ttu-id="8fb8f-136">Esto significa que incluso si una regla ASR determina que el archivo o carpeta contiene un comportamiento malintencionado, no bloqueará la ejecución del archivo.</span><span class="sxs-lookup"><span data-stu-id="8fb8f-136">This means that even if an ASR rule determines the file or folder contains malicious behavior, it will not block the file from running.</span></span> <span data-ttu-id="8fb8f-137">Esto podría permitir que los archivos no seguros se ejecuten e infecten los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="8fb8f-137">This could potentially allow unsafe files to run and infect your devices.</span></span>

<span data-ttu-id="8fb8f-138">También puede excluir las reglas ASR para que no se desencadene en función de los hashes de certificado y archivo, ya que permite que defender especificado para los indicadores de certificado y archivo de extremo.</span><span class="sxs-lookup"><span data-stu-id="8fb8f-138">You can also exclude ASR rules from triggering based on certificate and file hashes by allowing specified Defender for Endpoint file and certificate indicators.</span></span> <span data-ttu-id="8fb8f-139">(Vea [Administrar indicadores](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-indicators).)</span><span class="sxs-lookup"><span data-stu-id="8fb8f-139">(See [Manage indicators](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-indicators).)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8fb8f-140">Excluir archivos o carpetas puede reducir gravemente la protección proporcionada por las reglas ASR.</span><span class="sxs-lookup"><span data-stu-id="8fb8f-140">Excluding files or folders can severely reduce the protection provided by ASR rules.</span></span> <span data-ttu-id="8fb8f-141">Se permitirá la ejecución de archivos excluidos y no se registrará ningún informe o evento.</span><span class="sxs-lookup"><span data-stu-id="8fb8f-141">Excluded files will be allowed to run, and no report or event will be recorded.</span></span>
> <span data-ttu-id="8fb8f-142">Si las reglas ASR detectan archivos que cree que no deben detectarse, debe usar el modo de [auditoría primero para probar la regla](evaluate-attack-surface-reduction.md).</span><span class="sxs-lookup"><span data-stu-id="8fb8f-142">If ASR rules are detecting files that you believe shouldn't be detected, you should [use audit mode first to test the rule](evaluate-attack-surface-reduction.md).</span></span>


<span data-ttu-id="8fb8f-143">Puede especificar archivos o carpetas individuales (con rutas de carpeta o nombres de recursos completos), pero no puede especificar a qué reglas se aplican las exclusiones.</span><span class="sxs-lookup"><span data-stu-id="8fb8f-143">You can specify individual files or folders (using folder paths or fully qualified resource names), but you can't specify which rules the exclusions apply to.</span></span> <span data-ttu-id="8fb8f-144">Solo se aplica una exclusión cuando se inicia la aplicación o servicio excluidos.</span><span class="sxs-lookup"><span data-stu-id="8fb8f-144">An exclusion is applied only when the excluded application or service starts.</span></span> <span data-ttu-id="8fb8f-145">Por ejemplo, si agrega una exclusión para un servicio de actualización que ya se está ejecutando, el servicio de actualización seguirá desencadenando eventos hasta que el servicio se detenga y reinicie.</span><span class="sxs-lookup"><span data-stu-id="8fb8f-145">For example, if you add an exclusion for an update service that is already running, the update service will continue to trigger events until the service is stopped and restarted.</span></span>

<span data-ttu-id="8fb8f-146">Las reglas ASR admiten variables de entorno y caracteres comodín.</span><span class="sxs-lookup"><span data-stu-id="8fb8f-146">ASR rules support environment variables and wildcards.</span></span> <span data-ttu-id="8fb8f-147">Para obtener información sobre el uso de caracteres comodín, vea Usar caracteres comodín en las listas de exclusión de extensión o ruta de acceso de carpeta y [nombre de archivo.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists)</span><span class="sxs-lookup"><span data-stu-id="8fb8f-147">For information about using wildcards, see [Use wildcards in the file name and folder path or extension exclusion lists](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists).</span></span>

<span data-ttu-id="8fb8f-148">Los siguientes procedimientos para habilitar reglas ASR incluyen instrucciones sobre cómo excluir archivos y carpetas.</span><span class="sxs-lookup"><span data-stu-id="8fb8f-148">The following procedures for enabling ASR rules include instructions for how to exclude files and folders.</span></span>

## <a name="intune"></a><span data-ttu-id="8fb8f-149">Intune</span><span class="sxs-lookup"><span data-stu-id="8fb8f-149">Intune</span></span>

1. <span data-ttu-id="8fb8f-150">Seleccione **Perfiles de configuración** de  >  **dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="8fb8f-150">Select **Device configuration** > **Profiles**.</span></span> <span data-ttu-id="8fb8f-151">Elija un perfil de protección de extremo existente o cree uno nuevo.</span><span class="sxs-lookup"><span data-stu-id="8fb8f-151">Choose an existing endpoint protection profile or create a new one.</span></span> <span data-ttu-id="8fb8f-152">Para crear uno nuevo, seleccione **Crear perfil** e introduzca información para este perfil.</span><span class="sxs-lookup"><span data-stu-id="8fb8f-152">To create a new one, select **Create profile** and enter information for this profile.</span></span> <span data-ttu-id="8fb8f-153">En **Tipo de perfil,** seleccione **Protección de extremo**.</span><span class="sxs-lookup"><span data-stu-id="8fb8f-153">For **Profile type**, select **Endpoint protection**.</span></span> <span data-ttu-id="8fb8f-154">Si ha elegido un perfil existente, seleccione **Propiedades** y, a continuación, **seleccione Configuración**.</span><span class="sxs-lookup"><span data-stu-id="8fb8f-154">If you've chosen an existing profile, select **Properties** and then select **Settings**.</span></span>

2. <span data-ttu-id="8fb8f-155">En el **panel Protección de** puntos de conexión, Windows Defender Protección contra **vulnerabilidades** de seguridad y, a continuación, **seleccione Reducción de superficie de ataque**.</span><span class="sxs-lookup"><span data-stu-id="8fb8f-155">In the **Endpoint protection** pane, select **Windows Defender Exploit Guard**, then select **Attack Surface Reduction**.</span></span> <span data-ttu-id="8fb8f-156">Seleccione la configuración deseada para cada regla ASR.</span><span class="sxs-lookup"><span data-stu-id="8fb8f-156">Select the desired setting for each ASR rule.</span></span>

3. <span data-ttu-id="8fb8f-157">En **Excepciones de reducción de superficie de ataque,** escriba archivos y carpetas individuales.</span><span class="sxs-lookup"><span data-stu-id="8fb8f-157">Under **Attack Surface Reduction exceptions**, enter individual files and folders.</span></span> <span data-ttu-id="8fb8f-158">También puede seleccionar **Importar para** importar un archivo CSV que contenga archivos y carpetas que se excluirán de las reglas ASR.</span><span class="sxs-lookup"><span data-stu-id="8fb8f-158">You can also select **Import** to import a CSV file that contains files and folders to exclude from ASR rules.</span></span> <span data-ttu-id="8fb8f-159">Cada línea del archivo CSV debe tener el siguiente formato:</span><span class="sxs-lookup"><span data-stu-id="8fb8f-159">Each line in the CSV file should be formatted as follows:</span></span>

   <span data-ttu-id="8fb8f-160">`C:\folder`, `%ProgramFiles%\folder\file`, `C:\path`</span><span class="sxs-lookup"><span data-stu-id="8fb8f-160">`C:\folder`, `%ProgramFiles%\folder\file`, `C:\path`</span></span>

4. <span data-ttu-id="8fb8f-161">Seleccione **Aceptar en** los tres paneles de configuración.</span><span class="sxs-lookup"><span data-stu-id="8fb8f-161">Select **OK** on the three configuration panes.</span></span> <span data-ttu-id="8fb8f-162">A **continuación,** seleccione Crear si está creando un nuevo archivo de protección de puntos de conexión o **Guardar** si está editando uno existente.</span><span class="sxs-lookup"><span data-stu-id="8fb8f-162">Then select **Create** if you're creating a new endpoint protection file or **Save** if you're editing an existing one.</span></span>

## <a name="mdm"></a><span data-ttu-id="8fb8f-163">MDM</span><span class="sxs-lookup"><span data-stu-id="8fb8f-163">MDM</span></span>

<span data-ttu-id="8fb8f-164">Use el proveedor de servicios de configuración [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductionrules) (CSP) para habilitar y establecer individualmente el modo de cada regla.</span><span class="sxs-lookup"><span data-stu-id="8fb8f-164">Use the [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductionrules) configuration service provider (CSP) to individually enable and set the mode for each rule.</span></span>

<span data-ttu-id="8fb8f-165">A continuación se muestra un ejemplo de referencia mediante [valores GUID para reglas ASR.](attack-surface-reduction.md#attack-surface-reduction-rules)</span><span class="sxs-lookup"><span data-stu-id="8fb8f-165">The following is a sample for reference, using [GUID values for ASR rules](attack-surface-reduction.md#attack-surface-reduction-rules).</span></span>

`OMA-URI path: ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules`

`Value: 75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84=2|3B576869-A4EC-4529-8536-B80A7769E899=1|D4F940AB-401B-4EfC-AADC-AD5F3C50688A=2|D3E037E1-3EB8-44C8-A917-57927947596D=1|5BEB7EFE-FD9A-4556-801D-275E5FFC04CC=0|BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550=1`

<span data-ttu-id="8fb8f-166">Los valores para habilitar (Bloquear), deshabilitar, advertir o habilitar en modo auditoría son:</span><span class="sxs-lookup"><span data-stu-id="8fb8f-166">The values to enable (Block), disable, warn, or enable in audit mode are:</span></span>

- <span data-ttu-id="8fb8f-167">0 : Deshabilitar (deshabilitar la regla ASR)</span><span class="sxs-lookup"><span data-stu-id="8fb8f-167">0 : Disable (Disable the ASR rule)</span></span>
- <span data-ttu-id="8fb8f-168">1 : Bloquear (habilitar la regla ASR)</span><span class="sxs-lookup"><span data-stu-id="8fb8f-168">1 : Block (Enable the ASR rule)</span></span>
- <span data-ttu-id="8fb8f-169">2: Auditoría (Evaluar cómo afectaría la regla ASR a su organización si está habilitada)</span><span class="sxs-lookup"><span data-stu-id="8fb8f-169">2 : Audit (Evaluate how the ASR rule would impact your organization if enabled)</span></span>
- <span data-ttu-id="8fb8f-170">6 : Advertir (habilitar la regla ASR pero permitir que el usuario final omita el bloque)</span><span class="sxs-lookup"><span data-stu-id="8fb8f-170">6 : Warn  (Enable the ASR rule but allow the end-user to bypass the block)</span></span>

<span data-ttu-id="8fb8f-171">Use [el proveedor ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) configuration service provider (CSP) para agregar exclusiones.</span><span class="sxs-lookup"><span data-stu-id="8fb8f-171">Use the [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) configuration service provider (CSP) to add exclusions.</span></span>

<span data-ttu-id="8fb8f-172">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8fb8f-172">Example:</span></span>

`OMA-URI path: ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions`

`Value: c:\path|e:\path|c:\Exclusions.exe`

> [!NOTE]
> <span data-ttu-id="8fb8f-173">Asegúrese de escribir valores de OMA-URI sin espacios.</span><span class="sxs-lookup"><span data-stu-id="8fb8f-173">Be sure to enter OMA-URI values without spaces.</span></span>

## <a name="microsoft-endpoint-configuration-manager"></a><span data-ttu-id="8fb8f-174">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="8fb8f-174">Microsoft Endpoint Configuration Manager</span></span>

1. <span data-ttu-id="8fb8f-175">En Microsoft Endpoint Configuration Manager, vaya a **Assets and Compliance** Endpoint  >  **Protection** Windows Defender  >  **Exploit Guard**.</span><span class="sxs-lookup"><span data-stu-id="8fb8f-175">In Microsoft Endpoint Configuration Manager, go to **Assets and Compliance** > **Endpoint Protection** > **Windows Defender Exploit Guard**.</span></span>

2. <span data-ttu-id="8fb8f-176">Seleccione **Inicio Crear** directiva de protección contra  >  **vulnerabilidades** de seguridad .</span><span class="sxs-lookup"><span data-stu-id="8fb8f-176">Select **Home** > **Create Exploit Guard Policy**.</span></span>

3. <span data-ttu-id="8fb8f-177">Escribe un nombre y una descripción, selecciona **Reducción de superficie de** ataque y selecciona **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="8fb8f-177">Enter a name and a description, select **Attack Surface Reduction**, and select **Next**.</span></span>

4. <span data-ttu-id="8fb8f-178">Elija las reglas que bloquearán o auditarán las acciones y seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="8fb8f-178">Choose which rules will block or audit actions and select **Next**.</span></span>

5. <span data-ttu-id="8fb8f-179">Revise la configuración y seleccione **Siguiente** para crear la directiva.</span><span class="sxs-lookup"><span data-stu-id="8fb8f-179">Review the settings and select **Next** to create the policy.</span></span>

6. <span data-ttu-id="8fb8f-180">Después de crear la directiva, **Cierre**.</span><span class="sxs-lookup"><span data-stu-id="8fb8f-180">After the policy is created, **Close**.</span></span>

## <a name="group-policy"></a><span data-ttu-id="8fb8f-181">Directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="8fb8f-181">Group Policy</span></span>

> [!WARNING]
> <span data-ttu-id="8fb8f-182">Si administra los equipos y dispositivos con Intune, Configuration Manager u otra plataforma de administración de nivel empresarial, el software de administración sobrescribirá cualquier configuración de directiva de grupo en conflicto al iniciarse.</span><span class="sxs-lookup"><span data-stu-id="8fb8f-182">If you manage your computers and devices with Intune, Configuration Manager, or other enterprise-level management platform, the management software will overwrite any conflicting Group Policy settings on startup.</span></span>

1. <span data-ttu-id="8fb8f-183">En el equipo de administración de directivas de grupo, abra la Consola de administración de directivas de [grupo,](https://technet.microsoft.com/library/cc731212.aspx)haga clic con el botón secundario en el objeto de directiva de grupo que desea configurar y **seleccione Editar**.</span><span class="sxs-lookup"><span data-stu-id="8fb8f-183">On your Group Policy management computer, open the [Group Policy Management Console](https://technet.microsoft.com/library/cc731212.aspx), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="8fb8f-184">En el **Editor de administración de directivas de** grupo, vaya a Configuración del equipo **y** seleccione **Plantillas administrativas.**</span><span class="sxs-lookup"><span data-stu-id="8fb8f-184">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="8fb8f-185">Expande el árbol a **Componentes de Windows** Microsoft Defender  >  **Antivirus** Microsoft Defender  >  **Exploit Guard**  >  **Reducción de superficie de ataque**.</span><span class="sxs-lookup"><span data-stu-id="8fb8f-185">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Microsoft Defender Exploit Guard** > **Attack surface reduction**.</span></span>

4. <span data-ttu-id="8fb8f-186">Selecciona **Configurar reglas de reducción de superficie de ataque** y selecciona **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="8fb8f-186">Select **Configure Attack surface reduction rules** and select **Enabled**.</span></span> <span data-ttu-id="8fb8f-187">A continuación, puede establecer el estado individual de cada regla en la sección de opciones.</span><span class="sxs-lookup"><span data-stu-id="8fb8f-187">You can then set the individual state for each rule in the options section.</span></span>

   <span data-ttu-id="8fb8f-188">Seleccione **Mostrar...** y escriba el identificador de regla en la columna **Nombre** de valor y el estado elegido en la **columna** Valor de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="8fb8f-188">Select **Show...** and enter the rule ID in the **Value name** column and your chosen state in the **Value** column as follows:</span></span>

   - <span data-ttu-id="8fb8f-189">0 : Deshabilitar (deshabilitar la regla ASR)</span><span class="sxs-lookup"><span data-stu-id="8fb8f-189">0 : Disable (Disable the ASR rule)</span></span>
   - <span data-ttu-id="8fb8f-190">1 : Bloquear (habilitar la regla ASR)</span><span class="sxs-lookup"><span data-stu-id="8fb8f-190">1 : Block (Enable the ASR rule)</span></span>
   - <span data-ttu-id="8fb8f-191">2: Auditoría (Evaluar cómo afectaría la regla ASR a su organización si está habilitada)</span><span class="sxs-lookup"><span data-stu-id="8fb8f-191">2 : Audit (Evaluate how the ASR rule would impact your organization if enabled)</span></span>
   - <span data-ttu-id="8fb8f-192">6 : Advertir (habilitar la regla ASR pero permitir que el usuario final omita el bloque)</span><span class="sxs-lookup"><span data-stu-id="8fb8f-192">6 : Warn  (Enable the ASR rule but allow the end-user to bypass the block)</span></span>

   :::image type="content" source="images/asr-rules-gp.png" alt-text="Reglas de ASR en la directiva de grupo":::

5. <span data-ttu-id="8fb8f-194">Para excluir archivos y carpetas de  las reglas ASR, seleccione la opción Excluir archivos y rutas de acceso de las reglas de reducción de superficie de ataque y establezca la opción en **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="8fb8f-194">To exclude files and folders from ASR rules, select the **Exclude files and paths from Attack surface reduction rules** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="8fb8f-195">Seleccione **Mostrar** e introduzca cada archivo o carpeta en la **columna Nombre de** valor.</span><span class="sxs-lookup"><span data-stu-id="8fb8f-195">Select **Show** and enter each file or folder in the **Value name** column.</span></span> <span data-ttu-id="8fb8f-196">Escriba **0 en** la **columna Valor** de cada elemento.</span><span class="sxs-lookup"><span data-stu-id="8fb8f-196">Enter **0** in the **Value** column for each item.</span></span>

> [!WARNING]
> <span data-ttu-id="8fb8f-197">No use comillas, ya que no son compatibles con la columna **Nombre de** valor o la **columna** Valor.</span><span class="sxs-lookup"><span data-stu-id="8fb8f-197">Do not use quotes as they are not supported for either the **Value name** column or the **Value** column.</span></span>

## <a name="powershell"></a><span data-ttu-id="8fb8f-198">PowerShell</span><span class="sxs-lookup"><span data-stu-id="8fb8f-198">PowerShell</span></span>

> [!WARNING]
> <span data-ttu-id="8fb8f-199">Si administra los equipos y dispositivos con Intune, Configuration Manager u otra plataforma de administración de nivel empresarial, el software de administración sobrescribirá cualquier configuración de PowerShell en conflicto al iniciarse.</span><span class="sxs-lookup"><span data-stu-id="8fb8f-199">If you manage your computers and devices with Intune, Configuration Manager, or another enterprise-level management platform, the management software will overwrite any conflicting PowerShell settings on startup.</span></span> <span data-ttu-id="8fb8f-200">Para permitir que los usuarios definan el valor con PowerShell, use la opción "User Defined" para la regla en la plataforma de administración.</span><span class="sxs-lookup"><span data-stu-id="8fb8f-200">To allow users to define the value using PowerShell, use the "User Defined" option for the rule in the management platform.</span></span>

1. <span data-ttu-id="8fb8f-201">Escriba **powershell** en el menú Inicio, haga clic con el botón **secundario en Windows PowerShell** y seleccione Ejecutar como **administrador**.</span><span class="sxs-lookup"><span data-stu-id="8fb8f-201">Type **powershell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="8fb8f-202">Escriba el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="8fb8f-202">Type the following cmdlet:</span></span>

    ```PowerShell
    Set-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Enabled
    ```

    <span data-ttu-id="8fb8f-203">Para habilitar las reglas ASR en modo auditoría, use el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="8fb8f-203">To enable ASR rules in audit mode, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions AuditMode
    ```

    <span data-ttu-id="8fb8f-204">Para habilitar las reglas ASR en modo de advertencia, use el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="8fb8f-204">To enable ASR rules in warn mode, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Warn
    ```

    <span data-ttu-id="8fb8f-205">Para desactivar las reglas ASR, use el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="8fb8f-205">To turn off ASR rules, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Disabled
    ```

    > [!IMPORTANT]
    > <span data-ttu-id="8fb8f-206">Debe especificar el estado individualmente para cada regla, pero puede combinar reglas y estados en una lista separada por comas.</span><span class="sxs-lookup"><span data-stu-id="8fb8f-206">You must specify the state individually for each rule, but you can combine rules and states in a comma-separated list.</span></span>
    >
    > <span data-ttu-id="8fb8f-207">En el siguiente ejemplo, se habilitarán las dos primeras reglas, se deshabilitará la tercera regla y se habilitará la cuarta regla en modo auditoría:</span><span class="sxs-lookup"><span data-stu-id="8fb8f-207">In the following example, the first two rules will be enabled, the third rule will be disabled, and the fourth rule will be enabled in audit mode:</span></span>
    >
    > ```PowerShell
    > Set-MpPreference -AttackSurfaceReductionRules_Ids <rule ID 1>,<rule ID 2>,<rule ID 3>,<rule ID 4> -AttackSurfaceReductionRules_Actions Enabled, Enabled, Disabled, AuditMode
    > ```

    <span data-ttu-id="8fb8f-208">También puede usar el verbo `Add-MpPreference` de PowerShell para agregar nuevas reglas a la lista existente.</span><span class="sxs-lookup"><span data-stu-id="8fb8f-208">You can also use the `Add-MpPreference` PowerShell verb to add new rules to the existing list.</span></span>

    > [!WARNING]
    > <span data-ttu-id="8fb8f-209">`Set-MpPreference` sobrescribirá siempre el conjunto de reglas existente.</span><span class="sxs-lookup"><span data-stu-id="8fb8f-209">`Set-MpPreference` will always overwrite the existing set of rules.</span></span> <span data-ttu-id="8fb8f-210">Si desea agregar al conjunto existente, úselo `Add-MpPreference` en su lugar.</span><span class="sxs-lookup"><span data-stu-id="8fb8f-210">If you want to add to the existing set, use `Add-MpPreference` instead.</span></span>
    > <span data-ttu-id="8fb8f-211">Puede obtener una lista de reglas y su estado actual mediante `Get-MpPreference` .</span><span class="sxs-lookup"><span data-stu-id="8fb8f-211">You can obtain a list of rules and their current state by using `Get-MpPreference`.</span></span>

3. <span data-ttu-id="8fb8f-212">Para excluir archivos y carpetas de las reglas ASR, use el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="8fb8f-212">To exclude files and folders from ASR rules, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionOnlyExclusions "<fully qualified path or resource>"
    ```

    <span data-ttu-id="8fb8f-213">Siga usando para `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` agregar más archivos y carpetas a la lista.</span><span class="sxs-lookup"><span data-stu-id="8fb8f-213">Continue to use `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` to add more files and folders to the list.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="8fb8f-214">Se `Add-MpPreference` usa para anexar o agregar aplicaciones a la lista.</span><span class="sxs-lookup"><span data-stu-id="8fb8f-214">Use `Add-MpPreference` to append or add apps to the list.</span></span> <span data-ttu-id="8fb8f-215">El `Set-MpPreference` uso del cmdlet sobrescribirá la lista existente.</span><span class="sxs-lookup"><span data-stu-id="8fb8f-215">Using the `Set-MpPreference` cmdlet will overwrite the existing list.</span></span>

## <a name="related-articles"></a><span data-ttu-id="8fb8f-216">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="8fb8f-216">Related articles</span></span>

- [<span data-ttu-id="8fb8f-217">Reducir superficies de ataque con reglas de reducción de superficie de ataque</span><span class="sxs-lookup"><span data-stu-id="8fb8f-217">Reduce attack surfaces with attack surface reduction rules</span></span>](attack-surface-reduction.md)

- [<span data-ttu-id="8fb8f-218">Evaluar la reducción de superficie de ataque</span><span class="sxs-lookup"><span data-stu-id="8fb8f-218">Evaluate attack surface reduction</span></span>](evaluate-attack-surface-reduction.md)

- [<span data-ttu-id="8fb8f-219">Preguntas más frecuentes sobre la reducción de la superficie expuesta a ataques</span><span class="sxs-lookup"><span data-stu-id="8fb8f-219">Attack surface reduction FAQ</span></span>](attack-surface-reduction.md)
