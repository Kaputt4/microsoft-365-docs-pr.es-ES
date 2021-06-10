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
author: denisebmsft
ms.author: deniseb
ms.reviewer: oogunrinde
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.date: 06/02/2021
ms.openlocfilehash: 5bdb7ed46bdf01d4fb6075f310b98dcdb98a5a7f
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771926"
---
# <a name="enable-attack-surface-reduction-rules"></a><span data-ttu-id="3a594-104">Habilitar las reglas de la reducción de superficie expuesta a ataques</span><span class="sxs-lookup"><span data-stu-id="3a594-104">Enable attack surface reduction rules</span></span>

<span data-ttu-id="3a594-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="3a594-105">**Applies to:**</span></span>

- [<span data-ttu-id="3a594-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="3a594-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="3a594-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3a594-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> <span data-ttu-id="3a594-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="3a594-108">Want to experience Defender for Endpoint?</span></span> <span data-ttu-id="3a594-109">[Registrarse para obtener una versión de prueba gratuita](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink).</span><span class="sxs-lookup"><span data-stu-id="3a594-109">[Sign up for a free trial](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink).</span></span>

<span data-ttu-id="3a594-110">[Las reglas de reducción de superficie de](attack-surface-reduction.md) ataque (reglas ASR) ayudan a evitar acciones que el malware suele abusar de dispositivos y redes.</span><span class="sxs-lookup"><span data-stu-id="3a594-110">[Attack surface reduction rules](attack-surface-reduction.md) (ASR rules) help prevent actions that malware often abuses to compromise devices and networks.</span></span>

<span data-ttu-id="3a594-111">**Requisitos** Puedes establecer reglas de reducción de superficie de ataque para dispositivos que ejecutan cualquiera de las siguientes ediciones y versiones de Windows:</span><span class="sxs-lookup"><span data-stu-id="3a594-111">**Requirements** You can set attack surface reduction rules for devices that are running any of the following editions and versions of Windows:</span></span>

- <span data-ttu-id="3a594-112">Windows 10 Pro versión [1709](/windows/whats-new/whats-new-windows-10-version-1709) o posterior</span><span class="sxs-lookup"><span data-stu-id="3a594-112">Windows 10 Pro, [version 1709](/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="3a594-113">Windows 10 Enterprise, versión [1709](/windows/whats-new/whats-new-windows-10-version-1709) o posterior</span><span class="sxs-lookup"><span data-stu-id="3a594-113">Windows 10 Enterprise, [version 1709](/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="3a594-114">Windows Servidor, [versión 1803 (canal semianual)](/windows-server/get-started/whats-new-in-windows-server-1803) o posterior</span><span class="sxs-lookup"><span data-stu-id="3a594-114">Windows Server, [version 1803 (Semi-Annual Channel)](/windows-server/get-started/whats-new-in-windows-server-1803) or later</span></span>
- [<span data-ttu-id="3a594-115">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="3a594-115">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="3a594-116">Aunque las reglas de reducción de superficie de ataque no requieren una licencia [Windows E5,](/windows/deployment/deploy-enterprise-licenses)si tienes Windows E5, obtienes capacidades de administración avanzadas.</span><span class="sxs-lookup"><span data-stu-id="3a594-116">Although attack surface reduction rules don't require a [Windows E5 license](/windows/deployment/deploy-enterprise-licenses), if you have Windows E5, you get advanced management capabilities.</span></span> <span data-ttu-id="3a594-117">Estas funcionalidades disponibles solo en Windows E5 incluyen supervisión, análisis y flujos de trabajo disponibles en [Defender para](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint?view=o365-worldwide&preserve-view=true)endpoint, así como capacidades de informes y configuración en el centro de seguridad de [Microsoft 365.](/microsoft-365/security/defender/overview-security-center?view=o365-worldwide&preserve-view=true)</span><span class="sxs-lookup"><span data-stu-id="3a594-117">These capabilities available only in Windows E5 include monitoring, analytics, and workflows available in [Defender for Endpoint](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint?view=o365-worldwide&preserve-view=true), as well as reporting and configuration capabilities in the [Microsoft 365 security center](/microsoft-365/security/defender/overview-security-center?view=o365-worldwide&preserve-view=true).</span></span> <span data-ttu-id="3a594-118">Estas funcionalidades avanzadas no están disponibles con una licencia Windows Professional o Windows E3; sin embargo, si tienes esas licencias, puedes usar el Visor de eventos y los Antivirus de Microsoft Defender para revisar los eventos de la regla de reducción de superficie de ataque.</span><span class="sxs-lookup"><span data-stu-id="3a594-118">These advanced capabilities aren't available with a Windows Professional or Windows E3 license; however, if you do have those licenses, you can use Event Viewer and Microsoft Defender Antivirus logs to review your attack surface reduction rule events.</span></span>

<span data-ttu-id="3a594-119">Cada regla ASR contiene una de cuatro opciones:</span><span class="sxs-lookup"><span data-stu-id="3a594-119">Each ASR rule contains one of four settings:</span></span>

- <span data-ttu-id="3a594-120">**No configurado:** deshabilitar la regla ASR</span><span class="sxs-lookup"><span data-stu-id="3a594-120">**Not configured**: Disable the ASR rule</span></span>
- <span data-ttu-id="3a594-121">**Bloquear:** habilitar la regla ASR</span><span class="sxs-lookup"><span data-stu-id="3a594-121">**Block**: Enable the ASR rule</span></span>
- <span data-ttu-id="3a594-122">**Auditoría:** evaluar cómo la regla ASR afectaría a su organización si está habilitada</span><span class="sxs-lookup"><span data-stu-id="3a594-122">**Audit**: Evaluate how the ASR rule would impact your organization if enabled</span></span>
- <span data-ttu-id="3a594-123">**Advertencia:** habilite la regla ASR pero permita al usuario final omitir el bloque</span><span class="sxs-lookup"><span data-stu-id="3a594-123">**Warn**: Enable the ASR rule but allow the end user to bypass the block</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3a594-124">Actualmente, el modo de advertencia no es compatible con tres reglas ASR al configurar reglas ASR en Microsoft Endpoint Manager (MEM).</span><span class="sxs-lookup"><span data-stu-id="3a594-124">Currently, warn mode is not supported for three ASR rules when you configure ASR rules in Microsoft Endpoint Manager (MEM).</span></span> <span data-ttu-id="3a594-125">Para obtener más información, vea [Casos en los que no se admite el modo de advertencia](attack-surface-reduction.md#cases-where-warn-mode-is-not-supported).</span><span class="sxs-lookup"><span data-stu-id="3a594-125">To learn more, see [Cases where warn mode is not supported](attack-surface-reduction.md#cases-where-warn-mode-is-not-supported).</span></span>

<span data-ttu-id="3a594-126">Es muy recomendable usar reglas ASR con una licencia E5 de Windows (o SKU de licencia similar) para aprovechar las capacidades avanzadas de supervisión e informes disponibles en [Microsoft Defender para](microsoft-defender-endpoint.md) endpoint (Defender para endpoint).</span><span class="sxs-lookup"><span data-stu-id="3a594-126">It's highly recommended to use ASR rules with a Windows E5 license (or similar licensing SKU) to take advantage of the advanced monitoring and reporting capabilities available in [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md) (Defender for Endpoint).</span></span> <span data-ttu-id="3a594-127">Sin embargo, si tiene otra licencia, como Windows Professional o Windows E3 que no incluyen funciones avanzadas de supervisión e informes, puede desarrollar sus propias herramientas de supervisión e informes encima de los eventos que se generan en cada extremo cuando se desencadenan reglas ASR (por ejemplo, reenvío de eventos).</span><span class="sxs-lookup"><span data-stu-id="3a594-127">However, if you have another license, such as Windows Professional or Windows E3 that don't include advanced monitoring and reporting capabilities, you can develop your own monitoring and reporting tools on top of the events that are generated at each endpoint when ASR rules are triggered (e.g., Event Forwarding).</span></span>

> [!TIP]
> <span data-ttu-id="3a594-128">Para obtener más información sobre Windows licencias, consulte [Windows 10 Licensing y](https://www.microsoft.com/licensing/product-licensing/windows10?activetab=windows10-pivot:primaryr5) obtenga la Guía de licencias por volumen para [Windows 10](https://download.microsoft.com/download/2/D/1/2D14FE17-66C2-4D4C-AF73-E122930B60F6/Windows-10-Volume-Licensing-Guide.pdf).</span><span class="sxs-lookup"><span data-stu-id="3a594-128">To learn more about Windows licensing, see [Windows 10 Licensing](https://www.microsoft.com/licensing/product-licensing/windows10?activetab=windows10-pivot:primaryr5) and get the [Volume Licensing guide for Windows 10](https://download.microsoft.com/download/2/D/1/2D14FE17-66C2-4D4C-AF73-E122930B60F6/Windows-10-Volume-Licensing-Guide.pdf).</span></span>

<span data-ttu-id="3a594-129">Puedes habilitar las reglas de reducción de superficie de ataque mediante cualquiera de estos métodos:</span><span class="sxs-lookup"><span data-stu-id="3a594-129">You can enable attack surface reduction rules by using any of these methods:</span></span>

- [<span data-ttu-id="3a594-130">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="3a594-130">Microsoft Intune</span></span>](#intune)
- [<span data-ttu-id="3a594-131">Administración de dispositivos móviles (MDM)</span><span class="sxs-lookup"><span data-stu-id="3a594-131">Mobile Device Management (MDM)</span></span>](#mdm)
- [<span data-ttu-id="3a594-132">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="3a594-132">Microsoft Endpoint Configuration Manager</span></span>](#microsoft-endpoint-configuration-manager)
- [<span data-ttu-id="3a594-133">Directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="3a594-133">Group Policy</span></span>](#group-policy)
- [<span data-ttu-id="3a594-134">PowerShell</span><span class="sxs-lookup"><span data-stu-id="3a594-134">PowerShell</span></span>](#powershell)

<span data-ttu-id="3a594-135">Enterprise de nivel de administración, como Intune o Microsoft Endpoint Manager se recomienda.</span><span class="sxs-lookup"><span data-stu-id="3a594-135">Enterprise-level management such as Intune or Microsoft Endpoint Manager is recommended.</span></span> <span data-ttu-id="3a594-136">Enterprise de nivel de usuario sobrescribirá cualquier configuración de PowerShell o directiva de grupo en conflicto al iniciarse.</span><span class="sxs-lookup"><span data-stu-id="3a594-136">Enterprise-level management will overwrite any conflicting Group Policy or PowerShell settings on startup.</span></span>

## <a name="exclude-files-and-folders-from-asr-rules"></a><span data-ttu-id="3a594-137">Excluir archivos y carpetas de reglas ASR</span><span class="sxs-lookup"><span data-stu-id="3a594-137">Exclude files and folders from ASR rules</span></span>

<span data-ttu-id="3a594-138">Puedes excluir archivos y carpetas de ser evaluados por la mayoría de las reglas de reducción de superficie de ataque.</span><span class="sxs-lookup"><span data-stu-id="3a594-138">You can exclude files and folders from being evaluated by most attack surface reduction rules.</span></span> <span data-ttu-id="3a594-139">Esto significa que incluso si una regla ASR determina que el archivo o carpeta contiene un comportamiento malintencionado, no bloqueará la ejecución del archivo.</span><span class="sxs-lookup"><span data-stu-id="3a594-139">This means that even if an ASR rule determines the file or folder contains malicious behavior, it will not block the file from running.</span></span> <span data-ttu-id="3a594-140">Esto podría permitir que los archivos no seguros se ejecuten e infecten los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="3a594-140">This could potentially allow unsafe files to run and infect your devices.</span></span>

<span data-ttu-id="3a594-141">También puede excluir las reglas ASR para que no se desencadene en función de los hashes de certificado y archivo, ya que permite que defender especificado para los indicadores de certificado y archivo de extremo.</span><span class="sxs-lookup"><span data-stu-id="3a594-141">You can also exclude ASR rules from triggering based on certificate and file hashes by allowing specified Defender for Endpoint file and certificate indicators.</span></span> <span data-ttu-id="3a594-142">(Vea [Administrar indicadores](manage-indicators.md).)</span><span class="sxs-lookup"><span data-stu-id="3a594-142">(See [Manage indicators](manage-indicators.md).)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3a594-143">Excluir archivos o carpetas puede reducir gravemente la protección proporcionada por las reglas ASR.</span><span class="sxs-lookup"><span data-stu-id="3a594-143">Excluding files or folders can severely reduce the protection provided by ASR rules.</span></span> <span data-ttu-id="3a594-144">Se permitirá la ejecución de archivos excluidos y no se registrará ningún informe o evento.</span><span class="sxs-lookup"><span data-stu-id="3a594-144">Excluded files will be allowed to run, and no report or event will be recorded.</span></span>
> <span data-ttu-id="3a594-145">Si las reglas ASR detectan archivos que cree que no deben detectarse, debe usar el modo de [auditoría primero para probar la regla](evaluate-attack-surface-reduction.md).</span><span class="sxs-lookup"><span data-stu-id="3a594-145">If ASR rules are detecting files that you believe shouldn't be detected, you should [use audit mode first to test the rule](evaluate-attack-surface-reduction.md).</span></span>

<span data-ttu-id="3a594-146">Puede especificar archivos o carpetas individuales (con rutas de carpeta o nombres de recursos completos), pero no puede especificar a qué reglas se aplican las exclusiones.</span><span class="sxs-lookup"><span data-stu-id="3a594-146">You can specify individual files or folders (using folder paths or fully qualified resource names), but you can't specify which rules the exclusions apply to.</span></span> <span data-ttu-id="3a594-147">Solo se aplica una exclusión cuando se inicia la aplicación o servicio excluidos.</span><span class="sxs-lookup"><span data-stu-id="3a594-147">An exclusion is applied only when the excluded application or service starts.</span></span> <span data-ttu-id="3a594-148">Por ejemplo, si agrega una exclusión para un servicio de actualización que ya se está ejecutando, el servicio de actualización seguirá desencadenando eventos hasta que el servicio se detenga y reinicie.</span><span class="sxs-lookup"><span data-stu-id="3a594-148">For example, if you add an exclusion for an update service that is already running, the update service will continue to trigger events until the service is stopped and restarted.</span></span>

<span data-ttu-id="3a594-149">Las reglas ASR admiten variables de entorno y caracteres comodín.</span><span class="sxs-lookup"><span data-stu-id="3a594-149">ASR rules support environment variables and wildcards.</span></span> <span data-ttu-id="3a594-150">Para obtener información sobre el uso de caracteres comodín, vea Usar caracteres comodín en las listas de exclusión de extensión o ruta de acceso de carpeta y [nombre de archivo.](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists)</span><span class="sxs-lookup"><span data-stu-id="3a594-150">For information about using wildcards, see [Use wildcards in the file name and folder path or extension exclusion lists](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists).</span></span>

<span data-ttu-id="3a594-151">Los siguientes procedimientos para habilitar reglas ASR incluyen instrucciones sobre cómo excluir archivos y carpetas.</span><span class="sxs-lookup"><span data-stu-id="3a594-151">The following procedures for enabling ASR rules include instructions for how to exclude files and folders.</span></span>

## <a name="intune"></a><span data-ttu-id="3a594-152">Intune</span><span class="sxs-lookup"><span data-stu-id="3a594-152">Intune</span></span>

1. <span data-ttu-id="3a594-153">Seleccione **Perfiles de configuración** de  >  **dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="3a594-153">Select **Device configuration** > **Profiles**.</span></span> <span data-ttu-id="3a594-154">Elija un perfil de protección de extremo existente o cree uno nuevo.</span><span class="sxs-lookup"><span data-stu-id="3a594-154">Choose an existing endpoint protection profile or create a new one.</span></span> <span data-ttu-id="3a594-155">Para crear uno nuevo, seleccione **Crear perfil** e introduzca información para este perfil.</span><span class="sxs-lookup"><span data-stu-id="3a594-155">To create a new one, select **Create profile** and enter information for this profile.</span></span> <span data-ttu-id="3a594-156">En **Tipo de perfil,** seleccione **Protección de extremo**.</span><span class="sxs-lookup"><span data-stu-id="3a594-156">For **Profile type**, select **Endpoint protection**.</span></span> <span data-ttu-id="3a594-157">Si ha elegido un perfil existente, seleccione **Propiedades** y, a continuación, **seleccione Configuración**.</span><span class="sxs-lookup"><span data-stu-id="3a594-157">If you've chosen an existing profile, select **Properties** and then select **Settings**.</span></span>

2. <span data-ttu-id="3a594-158">En el **panel Protección de** puntos de conexión, Windows Defender Protección contra **vulnerabilidades** de seguridad y, a continuación, **seleccione Reducción de superficie de ataque.**</span><span class="sxs-lookup"><span data-stu-id="3a594-158">In the **Endpoint protection** pane, select **Windows Defender Exploit Guard**, then select **Attack Surface Reduction**.</span></span> <span data-ttu-id="3a594-159">Seleccione la configuración deseada para cada regla ASR.</span><span class="sxs-lookup"><span data-stu-id="3a594-159">Select the desired setting for each ASR rule.</span></span>

3. <span data-ttu-id="3a594-160">En **Excepciones de reducción de superficie de ataque,** escriba archivos y carpetas individuales.</span><span class="sxs-lookup"><span data-stu-id="3a594-160">Under **Attack Surface Reduction exceptions**, enter individual files and folders.</span></span> <span data-ttu-id="3a594-161">También puede seleccionar **Importar para** importar un archivo CSV que contenga archivos y carpetas que se excluirán de las reglas ASR.</span><span class="sxs-lookup"><span data-stu-id="3a594-161">You can also select **Import** to import a CSV file that contains files and folders to exclude from ASR rules.</span></span> <span data-ttu-id="3a594-162">Cada línea del archivo CSV debe tener el siguiente formato:</span><span class="sxs-lookup"><span data-stu-id="3a594-162">Each line in the CSV file should be formatted as follows:</span></span>

   <span data-ttu-id="3a594-163">`C:\folder`, `%ProgramFiles%\folder\file`, `C:\path`</span><span class="sxs-lookup"><span data-stu-id="3a594-163">`C:\folder`, `%ProgramFiles%\folder\file`, `C:\path`</span></span>

4. <span data-ttu-id="3a594-164">Seleccione **Aceptar en** los tres paneles de configuración.</span><span class="sxs-lookup"><span data-stu-id="3a594-164">Select **OK** on the three configuration panes.</span></span> <span data-ttu-id="3a594-165">A **continuación,** seleccione Crear si está creando un nuevo archivo de protección de puntos de conexión o **Guardar** si está editando uno existente.</span><span class="sxs-lookup"><span data-stu-id="3a594-165">Then select **Create** if you're creating a new endpoint protection file or **Save** if you're editing an existing one.</span></span>

## <a name="mem"></a><span data-ttu-id="3a594-166">MEM</span><span class="sxs-lookup"><span data-stu-id="3a594-166">MEM</span></span>

<span data-ttu-id="3a594-167">Puede usar Microsoft Endpoint Manager (MEM) OMA-URI para configurar reglas ASR personalizadas.</span><span class="sxs-lookup"><span data-stu-id="3a594-167">You can use Microsoft Endpoint Manager (MEM) OMA-URI to configure custom ASR rules.</span></span> <span data-ttu-id="3a594-168">El siguiente procedimiento usa la regla Bloquear el uso indebido de controladores [firmados vulnerables](attack-surface-reduction.md#block-abuse-of-exploited-vulnerable-signed-drivers) explotados para el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="3a594-168">The following procedure uses the rule [Block abuse of exploited vulnerable signed drivers](attack-surface-reduction.md#block-abuse-of-exploited-vulnerable-signed-drivers) for the example.</span></span>

1. <span data-ttu-id="3a594-169">Abra el centro Microsoft Endpoint Manager administración de Microsoft Endpoint Manager (MEM).</span><span class="sxs-lookup"><span data-stu-id="3a594-169">Open the Microsoft Endpoint Manager (MEM) admin center.</span></span> <span data-ttu-id="3a594-170">En el **menú Inicio,** haga clic en **Dispositivos**, seleccione **Perfil de configuración** y, a continuación, haga clic en Crear **perfil.**</span><span class="sxs-lookup"><span data-stu-id="3a594-170">In the **Home** menu, click  **Devices**, select **Configuration profile**, and then click **Create profile**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3a594-171">![MEM Create Profile](images/mem01-create-profile.png)</span><span class="sxs-lookup"><span data-stu-id="3a594-171">![MEM Create Profile](images/mem01-create-profile.png)</span></span>

2. <span data-ttu-id="3a594-172">En **Crear un perfil**, en las dos listas desplegables siguientes, seleccione lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3a594-172">In **Create a profile**, in the following two drop-down lists, select the following:</span></span>

   - <span data-ttu-id="3a594-173">En **Plataforma,** **seleccione Windows 10 y versiones posteriores**</span><span class="sxs-lookup"><span data-stu-id="3a594-173">In **Platform**, select **Windows 10 and later**</span></span>
   - <span data-ttu-id="3a594-174">En **Tipo de perfil**, seleccione **Plantillas**</span><span class="sxs-lookup"><span data-stu-id="3a594-174">In **Profile type**, select **Templates**</span></span>

   <span data-ttu-id="3a594-175">Seleccione **Personalizado** y, a continuación, haga clic **en Crear**.</span><span class="sxs-lookup"><span data-stu-id="3a594-175">Select **Custom**, and then click **Create**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3a594-176">![Atributos de perfil de regla MEM](images/mem02-profile-attributes.png)</span><span class="sxs-lookup"><span data-stu-id="3a594-176">![MEM rule profile attributes](images/mem02-profile-attributes.png)</span></span>

3. <span data-ttu-id="3a594-177">La herramienta Plantilla personalizada se abre en el paso **1 Conceptos básicos**.</span><span class="sxs-lookup"><span data-stu-id="3a594-177">The Custom template tool opens to step **1 Basics**.</span></span> <span data-ttu-id="3a594-178">En **1 Conceptos básicos**, en **Nombre**, escriba un nombre para la plantilla y, en **Descripción,** puede escribir una descripción (opcional).</span><span class="sxs-lookup"><span data-stu-id="3a594-178">In **1 Basics**, in **Name**, type a name for your template, and in **Description** you can type a description (optional).</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3a594-179">![Atributos básicos de MEM](images/mem03-1-basics.png)</span><span class="sxs-lookup"><span data-stu-id="3a594-179">![MEM basic attributes](images/mem03-1-basics.png)</span></span>

4. <span data-ttu-id="3a594-180">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="3a594-180">Click **Next**.</span></span> <span data-ttu-id="3a594-181">Paso **2 Se abren las opciones de** configuración.</span><span class="sxs-lookup"><span data-stu-id="3a594-181">Step **2 Configuration settings** opens.</span></span> <span data-ttu-id="3a594-182">Para OMA-URI Configuración, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="3a594-182">For OMA-URI Settings, click **Add**.</span></span> <span data-ttu-id="3a594-183">Ahora aparecen dos opciones: **Agregar** y **Exportar**.</span><span class="sxs-lookup"><span data-stu-id="3a594-183">Two options now appear: **Add** and **Export**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3a594-184">![Configuración de MEM](images/mem04-2-configuration-settings.png)</span><span class="sxs-lookup"><span data-stu-id="3a594-184">![MEM Configuration settings](images/mem04-2-configuration-settings.png)</span></span>

5. <span data-ttu-id="3a594-185">Haga clic **en Agregar** de nuevo.</span><span class="sxs-lookup"><span data-stu-id="3a594-185">Click **Add** again.</span></span> <span data-ttu-id="3a594-186">Se abre el Configuración agregar fila **OMA-URI.**</span><span class="sxs-lookup"><span data-stu-id="3a594-186">The **Add Row OMA-URI Settings** opens.</span></span> <span data-ttu-id="3a594-187">En **Agregar fila**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3a594-187">In **Add Row**, do the following:</span></span>

   - <span data-ttu-id="3a594-188">En **Nombre**, escriba un nombre para la regla.</span><span class="sxs-lookup"><span data-stu-id="3a594-188">In **Name**, type a name for the rule.</span></span>
   - <span data-ttu-id="3a594-189">En **Descripción**, escriba una breve descripción.</span><span class="sxs-lookup"><span data-stu-id="3a594-189">In **Description**, type a brief description.</span></span>
   - <span data-ttu-id="3a594-190">En **OMA-URI,** escriba o pegue el vínculo OMA-URI específico de la regla que va a agregar.</span><span class="sxs-lookup"><span data-stu-id="3a594-190">In **OMA-URI**, type or paste the specific OMA-URI link for the rule that you are adding.</span></span>
   - <span data-ttu-id="3a594-191">En **Tipo de datos**, seleccione **Cadena**.</span><span class="sxs-lookup"><span data-stu-id="3a594-191">In **Data type**, select **String**.</span></span>
   - <span data-ttu-id="3a594-192">En **Value**, escriba o pegue el valor GUID, el signo y el valor State sin espacios \= (_GUID=StateValue_).</span><span class="sxs-lookup"><span data-stu-id="3a594-192">In **Value**, type or paste the GUID value, the \= sign and the State value with no spaces (_GUID=StateValue_).</span></span> <span data-ttu-id="3a594-193">Dónde: {0 : Disable (Disable the ASR rule)}, {1 : Block (Enable the ASR rule)}, {2 : Audit (Evaluate how the ASR rule would impact your organization if enabled)}, {6 : Warn (Enable the ASR rule but allow the end-user to bypass the block)}</span><span class="sxs-lookup"><span data-stu-id="3a594-193">Where: {0 : Disable (Disable the ASR rule)}, {1 : Block (Enable the ASR rule)}, {2 : Audit (Evaluate how the ASR rule would impact your organization if enabled)}, {6 : Warn (Enable the ASR rule but allow the end-user to bypass the block)}</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3a594-194">![Configuración de URI de OMA de MEM](images/mem05-add-row-oma-uri.png)</span><span class="sxs-lookup"><span data-stu-id="3a594-194">![MEM OMA URI configuration](images/mem05-add-row-oma-uri.png)</span></span>

6. <span data-ttu-id="3a594-195">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="3a594-195">Click **Save**.</span></span> <span data-ttu-id="3a594-196">**Agregar cierres** de fila.</span><span class="sxs-lookup"><span data-stu-id="3a594-196">**Add Row** closes.</span></span> <span data-ttu-id="3a594-197">En **Personalizado**, haga clic **en Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="3a594-197">In **Custom**, click **Next**.</span></span> <span data-ttu-id="3a594-198">En el paso **3 Etiquetas de ámbito,** las etiquetas de ámbito son opcionales.</span><span class="sxs-lookup"><span data-stu-id="3a594-198">In step **3 Scope tags**, scope tags are optional.</span></span> <span data-ttu-id="3a594-199">Realiza una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="3a594-199">Do one of the following:</span></span>

   - <span data-ttu-id="3a594-200">Haga **clic en Seleccionar etiquetas de ámbito,** seleccione la etiqueta de ámbito (opcional) y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="3a594-200">Click **Select Scope tags**, select the scope tag (optional) and then click **Next**.</span></span>
   - <span data-ttu-id="3a594-201">O haga clic en **Siguiente**</span><span class="sxs-lookup"><span data-stu-id="3a594-201">Or click **Next**</span></span>

7. <span data-ttu-id="3a594-202">En el **paso 4 Asignaciones**, en **Grupos** incluidos - para los grupos que desea que se aplique esta regla - seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="3a594-202">In step **4 Assignments**, in **Included Groups** - for the groups that you want this rule to apply - select from the following options:</span></span>

   - <span data-ttu-id="3a594-203">**Agregar grupos**</span><span class="sxs-lookup"><span data-stu-id="3a594-203">**Add groups**</span></span>
   - <span data-ttu-id="3a594-204">**Agregar todos los usuarios**</span><span class="sxs-lookup"><span data-stu-id="3a594-204">**Add all users**</span></span>
   - <span data-ttu-id="3a594-205">**Agregar todos los dispositivos**</span><span class="sxs-lookup"><span data-stu-id="3a594-205">**Add all devices**</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3a594-206">![Asignaciones de MEM](images/mem06-4-assignments.png)</span><span class="sxs-lookup"><span data-stu-id="3a594-206">![MEM assignments](images/mem06-4-assignments.png)</span></span>

8. <span data-ttu-id="3a594-207">En **Grupos excluidos,** seleccione los grupos que desee excluir de esta regla y, a continuación, haga clic **en Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="3a594-207">In **Excluded groups**, select any groups that you want to exclude from this rule, and then click **Next**.</span></span>

9. <span data-ttu-id="3a594-208">En el **paso 5 Reglas de aplicabilidad** para la siguiente configuración, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3a594-208">In step **5 Applicability Rules** for the following settings, do the following:</span></span>

   - <span data-ttu-id="3a594-209">En **Regla**, seleccione **Asignar perfil si**, o No asignar perfil **si**</span><span class="sxs-lookup"><span data-stu-id="3a594-209">In **Rule**, select either **Assign profile if**, or **Don’t assign profile if**</span></span>
   - <span data-ttu-id="3a594-210">En **Propiedad**, seleccione la propiedad a la que desea que se aplique esta regla</span><span class="sxs-lookup"><span data-stu-id="3a594-210">In **Property**, select the property to which you want this rule to apply</span></span>
   - <span data-ttu-id="3a594-211">En **Valor**, escriba el valor o intervalo de valores aplicable</span><span class="sxs-lookup"><span data-stu-id="3a594-211">In **Value**, enter the applicable value or value range</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3a594-212">![Reglas de aplicabilidad de MEM](images/mem07-5-applicability-rules.png)</span><span class="sxs-lookup"><span data-stu-id="3a594-212">![MEM Applicability rules](images/mem07-5-applicability-rules.png)</span></span>

10. <span data-ttu-id="3a594-213">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="3a594-213">Click **Next**.</span></span> <span data-ttu-id="3a594-214">En el paso **6 Revisar + crear**, revise la configuración y la información que ha seleccionado y especificado y, a continuación, haga clic en **Crear**.</span><span class="sxs-lookup"><span data-stu-id="3a594-214">In step **6 Review + create**, review the settings and information you have selected and entered, and then click **Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="3a594-215">![Revisión y creación de MEM](images/mem08-6-review-create.png)</span><span class="sxs-lookup"><span data-stu-id="3a594-215">![MEM Review and create](images/mem08-6-review-create.png)</span></span>

    > [!NOTE]
    > <span data-ttu-id="3a594-216">Las reglas están activas y están activas en cuestión de minutos.</span><span class="sxs-lookup"><span data-stu-id="3a594-216">Rules are active and live within minutes.</span></span>

>[!NOTE]
> <span data-ttu-id="3a594-217">Control de conflictos:</span><span class="sxs-lookup"><span data-stu-id="3a594-217">Conflict handling:</span></span>
> 
> <span data-ttu-id="3a594-218">Si asignas a un dispositivo dos directivas ASR diferentes, la forma en que se controla el conflicto son reglas a las que se asignan estados diferentes, no hay ninguna administración de conflictos en su lugar y el resultado es un error.</span><span class="sxs-lookup"><span data-stu-id="3a594-218">If you assign a device two different ASR policies, the way conflict is handled is rules that are assigned different states, there is no conflict management in place, and the result is an error.</span></span>
> 
> <span data-ttu-id="3a594-219">Las reglas no conflictivas no producirán un error y la regla se aplicará correctamente.</span><span class="sxs-lookup"><span data-stu-id="3a594-219">Non-conflicting rules will not result in an error, and the rule will be applied correctly.</span></span> <span data-ttu-id="3a594-220">El resultado es que se aplica la primera regla y las siguientes reglas no conflictivas se combinan en la directiva.</span><span class="sxs-lookup"><span data-stu-id="3a594-220">The result is that the first rule is applied, and subsequent non-conflicting rules are merged into the policy.</span></span>

## <a name="mdm"></a><span data-ttu-id="3a594-221">MDM</span><span class="sxs-lookup"><span data-stu-id="3a594-221">MDM</span></span>

<span data-ttu-id="3a594-222">Use el proveedor de servicios de configuración [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules](/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductionrules) (CSP) para habilitar y establecer individualmente el modo de cada regla.</span><span class="sxs-lookup"><span data-stu-id="3a594-222">Use the [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules](/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductionrules) configuration service provider (CSP) to individually enable and set the mode for each rule.</span></span>

<span data-ttu-id="3a594-223">A continuación se muestra un ejemplo de referencia mediante [valores GUID para reglas ASR.](attack-surface-reduction.md#attack-surface-reduction-rules)</span><span class="sxs-lookup"><span data-stu-id="3a594-223">The following is a sample for reference, using [GUID values for ASR rules](attack-surface-reduction.md#attack-surface-reduction-rules).</span></span>

`OMA-URI path: ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules`

`Value: 75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84=2|3B576869-A4EC-4529-8536-B80A7769E899=1|D4F940AB-401B-4EfC-AADC-AD5F3C50688A=2|D3E037E1-3EB8-44C8-A917-57927947596D=1|5BEB7EFE-FD9A-4556-801D-275E5FFC04CC=0|BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550=1`

<span data-ttu-id="3a594-224">Los valores para habilitar (Bloquear), deshabilitar, advertir o habilitar en modo auditoría son:</span><span class="sxs-lookup"><span data-stu-id="3a594-224">The values to enable (Block), disable, warn, or enable in audit mode are:</span></span>

- <span data-ttu-id="3a594-225">0 : Deshabilitar (deshabilitar la regla ASR)</span><span class="sxs-lookup"><span data-stu-id="3a594-225">0 : Disable (Disable the ASR rule)</span></span>
- <span data-ttu-id="3a594-226">1 : Bloquear (habilitar la regla ASR)</span><span class="sxs-lookup"><span data-stu-id="3a594-226">1 : Block (Enable the ASR rule)</span></span>
- <span data-ttu-id="3a594-227">2: Auditoría (Evaluar cómo afectaría la regla ASR a su organización si está habilitada)</span><span class="sxs-lookup"><span data-stu-id="3a594-227">2 : Audit (Evaluate how the ASR rule would impact your organization if enabled)</span></span>
- <span data-ttu-id="3a594-228">6 : Advertir (habilitar la regla ASR pero permitir que el usuario final omita el bloque).</span><span class="sxs-lookup"><span data-stu-id="3a594-228">6 : Warn  (Enable the ASR rule but allow the end-user to bypass the block).</span></span> <span data-ttu-id="3a594-229">El modo de advertencia ya está disponible para la mayoría de las reglas ASR.</span><span class="sxs-lookup"><span data-stu-id="3a594-229">Warn mode is now available for most of the ASR rules.</span></span>

<span data-ttu-id="3a594-230">Use [el proveedor ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) configuration service provider (CSP) para agregar exclusiones.</span><span class="sxs-lookup"><span data-stu-id="3a594-230">Use the [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) configuration service provider (CSP) to add exclusions.</span></span>

<span data-ttu-id="3a594-231">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="3a594-231">Example:</span></span>

`OMA-URI path: ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions`

`Value: c:\path|e:\path|c:\Exclusions.exe`

> [!NOTE]
> <span data-ttu-id="3a594-232">Asegúrese de escribir valores de OMA-URI sin espacios.</span><span class="sxs-lookup"><span data-stu-id="3a594-232">Be sure to enter OMA-URI values without spaces.</span></span>

## <a name="microsoft-endpoint-configuration-manager"></a><span data-ttu-id="3a594-233">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="3a594-233">Microsoft Endpoint Configuration Manager</span></span>

1. <span data-ttu-id="3a594-234">En Microsoft Endpoint Configuration Manager, vaya a **Assets and Compliance**  >  **Endpoint Protection** Windows Defender Exploit  >  **Guard**.</span><span class="sxs-lookup"><span data-stu-id="3a594-234">In Microsoft Endpoint Configuration Manager, go to **Assets and Compliance** > **Endpoint Protection** > **Windows Defender Exploit Guard**.</span></span>

2. <span data-ttu-id="3a594-235">Seleccione **Inicio Crear** directiva de protección contra  >  **vulnerabilidades** de seguridad .</span><span class="sxs-lookup"><span data-stu-id="3a594-235">Select **Home** > **Create Exploit Guard Policy**.</span></span>

3. <span data-ttu-id="3a594-236">Escribe un nombre y una descripción, selecciona **Reducción de superficie de** ataque y selecciona **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="3a594-236">Enter a name and a description, select **Attack Surface Reduction**, and select **Next**.</span></span>

4. <span data-ttu-id="3a594-237">Elija las reglas que bloquearán o auditarán las acciones y seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="3a594-237">Choose which rules will block or audit actions and select **Next**.</span></span>

5. <span data-ttu-id="3a594-238">Revise la configuración y seleccione **Siguiente** para crear la directiva.</span><span class="sxs-lookup"><span data-stu-id="3a594-238">Review the settings and select **Next** to create the policy.</span></span>

6. <span data-ttu-id="3a594-239">Después de crear la directiva, **Cierre**.</span><span class="sxs-lookup"><span data-stu-id="3a594-239">After the policy is created, **Close**.</span></span>

## <a name="group-policy"></a><span data-ttu-id="3a594-240">Directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="3a594-240">Group Policy</span></span>

> [!WARNING]
> <span data-ttu-id="3a594-241">Si administra los equipos y dispositivos con Intune, Configuration Manager u otra plataforma de administración de nivel empresarial, el software de administración sobrescribirá cualquier configuración de directiva de grupo en conflicto al iniciarse.</span><span class="sxs-lookup"><span data-stu-id="3a594-241">If you manage your computers and devices with Intune, Configuration Manager, or other enterprise-level management platform, the management software will overwrite any conflicting Group Policy settings on startup.</span></span>

1. <span data-ttu-id="3a594-242">En el equipo de administración de directivas de grupo, abra la [Consola de administración de directivas de grupo](https://technet.microsoft.com/library/cc731212.aspx), haga clic con el botón secundario en el objeto de directiva de grupo que quiera configurar y seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="3a594-242">On your Group Policy management computer, open the [Group Policy Management Console](https://technet.microsoft.com/library/cc731212.aspx), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="3a594-243">En el **Editor de administración de directiva de grupo**, vaya a **Configuración del equipo** y seleccione **Plantillas administrativas**.</span><span class="sxs-lookup"><span data-stu-id="3a594-243">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="3a594-244">Expanda el árbol para Windows **componentes Antivirus de Microsoft Defender**  >    >  **Protección contra vulnerabilidades de seguridad de Microsoft Defender**  >  **reducción de superficie de ataque**.</span><span class="sxs-lookup"><span data-stu-id="3a594-244">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Microsoft Defender Exploit Guard** > **Attack surface reduction**.</span></span>

4. <span data-ttu-id="3a594-245">Selecciona **Configurar reglas de reducción de superficie de ataque** y selecciona **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="3a594-245">Select **Configure Attack surface reduction rules** and select **Enabled**.</span></span> <span data-ttu-id="3a594-246">A continuación, puede establecer el estado individual de cada regla en la sección de opciones.</span><span class="sxs-lookup"><span data-stu-id="3a594-246">You can then set the individual state for each rule in the options section.</span></span>

   <span data-ttu-id="3a594-247">Seleccione **Mostrar...** y escriba el identificador de regla en la columna **Nombre** de valor y el estado elegido en la **columna** Valor de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="3a594-247">Select **Show...** and enter the rule ID in the **Value name** column and your chosen state in the **Value** column as follows:</span></span>

   - <span data-ttu-id="3a594-248">0 : Deshabilitar (deshabilitar la regla ASR)</span><span class="sxs-lookup"><span data-stu-id="3a594-248">0 : Disable (Disable the ASR rule)</span></span>
   - <span data-ttu-id="3a594-249">1 : Bloquear (habilitar la regla ASR)</span><span class="sxs-lookup"><span data-stu-id="3a594-249">1 : Block (Enable the ASR rule)</span></span>
   - <span data-ttu-id="3a594-250">2: Auditoría (Evaluar cómo afectaría la regla ASR a su organización si está habilitada)</span><span class="sxs-lookup"><span data-stu-id="3a594-250">2 : Audit (Evaluate how the ASR rule would impact your organization if enabled)</span></span>
   - <span data-ttu-id="3a594-251">6 : Advertir (habilitar la regla ASR pero permitir que el usuario final omita el bloque)</span><span class="sxs-lookup"><span data-stu-id="3a594-251">6 : Warn  (Enable the ASR rule but allow the end-user to bypass the block)</span></span>

   :::image type="content" source="images/asr-rules-gp.png" alt-text="Reglas de ASR en la directiva de grupo":::

5. <span data-ttu-id="3a594-253">Para excluir archivos y carpetas de  las reglas ASR, seleccione la opción Excluir archivos y rutas de acceso de las reglas de reducción de superficie de ataque y establezca la opción en **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="3a594-253">To exclude files and folders from ASR rules, select the **Exclude files and paths from Attack surface reduction rules** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="3a594-254">Seleccione **Mostrar** e introduzca cada archivo o carpeta en la **columna Nombre de** valor.</span><span class="sxs-lookup"><span data-stu-id="3a594-254">Select **Show** and enter each file or folder in the **Value name** column.</span></span> <span data-ttu-id="3a594-255">Escriba **0 en** la **columna Valor** de cada elemento.</span><span class="sxs-lookup"><span data-stu-id="3a594-255">Enter **0** in the **Value** column for each item.</span></span>

   > [!WARNING]
   > <span data-ttu-id="3a594-256">No use comillas, ya que no son compatibles con la columna **Nombre de** valor o la **columna** Valor.</span><span class="sxs-lookup"><span data-stu-id="3a594-256">Do not use quotes as they are not supported for either the **Value name** column or the **Value** column.</span></span>

## <a name="powershell"></a><span data-ttu-id="3a594-257">PowerShell</span><span class="sxs-lookup"><span data-stu-id="3a594-257">PowerShell</span></span>

> [!WARNING]
> <span data-ttu-id="3a594-258">Si administra los equipos y dispositivos con Intune, Configuration Manager u otra plataforma de administración de nivel empresarial, el software de administración sobrescribirá cualquier configuración de PowerShell en conflicto al iniciarse.</span><span class="sxs-lookup"><span data-stu-id="3a594-258">If you manage your computers and devices with Intune, Configuration Manager, or another enterprise-level management platform, the management software will overwrite any conflicting PowerShell settings on startup.</span></span> <span data-ttu-id="3a594-259">Para permitir que los usuarios definan el valor con PowerShell, use la opción "User Defined" para la regla en la plataforma de administración.</span><span class="sxs-lookup"><span data-stu-id="3a594-259">To allow users to define the value using PowerShell, use the "User Defined" option for the rule in the management platform.</span></span>

1. <span data-ttu-id="3a594-260">Escriba **powershell** en el menú Inicio, haga clic con el botón **Windows PowerShell** y seleccione Ejecutar **como administrador**.</span><span class="sxs-lookup"><span data-stu-id="3a594-260">Type **powershell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="3a594-261">Escriba el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="3a594-261">Type the following cmdlet:</span></span>

    ```PowerShell
    Set-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Enabled
    ```

    <span data-ttu-id="3a594-262">Para habilitar las reglas ASR en modo auditoría, use el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="3a594-262">To enable ASR rules in audit mode, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions AuditMode
    ```

    <span data-ttu-id="3a594-263">Para habilitar las reglas ASR en modo de advertencia, use el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="3a594-263">To enable ASR rules in warn mode, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Warn
    ```

    <span data-ttu-id="3a594-264">Para habilitar ASR Bloquear el uso indebido de controladores firmados vulnerables explotados, use el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="3a594-264">To enable ASR Block abuse of exploited vulnerable signed drivers, use the following cmdlet:</span></span>

   ```PowerShell
   Add-MpPreference -AttackSurfaceReductionRules_Ids 56a863a9-875e-4185-98a7-b882c64b5ce5 -AttackSurfaceReductionRules_Actions Enabled
   ```

    <span data-ttu-id="3a594-265">Para desactivar las reglas ASR, use el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="3a594-265">To turn off ASR rules, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Disabled
    ```

    > [!IMPORTANT]
    > <span data-ttu-id="3a594-266">Debe especificar el estado individualmente para cada regla, pero puede combinar reglas y estados en una lista separada por comas.</span><span class="sxs-lookup"><span data-stu-id="3a594-266">You must specify the state individually for each rule, but you can combine rules and states in a comma-separated list.</span></span>
    >
    > <span data-ttu-id="3a594-267">En el siguiente ejemplo, se habilitarán las dos primeras reglas, se deshabilitará la tercera regla y se habilitará la cuarta regla en modo auditoría:</span><span class="sxs-lookup"><span data-stu-id="3a594-267">In the following example, the first two rules will be enabled, the third rule will be disabled, and the fourth rule will be enabled in audit mode:</span></span>
    >
    > ```PowerShell
    > Set-MpPreference -AttackSurfaceReductionRules_Ids <rule ID 1>,<rule ID 2>,<rule ID 3>,<rule ID 4> -AttackSurfaceReductionRules_Actions Enabled, Enabled, Disabled, AuditMode
    > ```

    <span data-ttu-id="3a594-268">También puede usar el verbo `Add-MpPreference` de PowerShell para agregar nuevas reglas a la lista existente.</span><span class="sxs-lookup"><span data-stu-id="3a594-268">You can also use the `Add-MpPreference` PowerShell verb to add new rules to the existing list.</span></span>

    > [!WARNING]
    > <span data-ttu-id="3a594-269">`Set-MpPreference` sobrescribirá siempre el conjunto de reglas existente.</span><span class="sxs-lookup"><span data-stu-id="3a594-269">`Set-MpPreference` will always overwrite the existing set of rules.</span></span> <span data-ttu-id="3a594-270">Si desea agregar al conjunto existente, úselo `Add-MpPreference` en su lugar.</span><span class="sxs-lookup"><span data-stu-id="3a594-270">If you want to add to the existing set, use `Add-MpPreference` instead.</span></span>
    > <span data-ttu-id="3a594-271">Puede obtener una lista de reglas y su estado actual mediante `Get-MpPreference` .</span><span class="sxs-lookup"><span data-stu-id="3a594-271">You can obtain a list of rules and their current state by using `Get-MpPreference`.</span></span>

3. <span data-ttu-id="3a594-272">Para excluir archivos y carpetas de las reglas ASR, use el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="3a594-272">To exclude files and folders from ASR rules, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionOnlyExclusions "<fully qualified path or resource>"
    ```

    <span data-ttu-id="3a594-273">Siga usando para `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` agregar más archivos y carpetas a la lista.</span><span class="sxs-lookup"><span data-stu-id="3a594-273">Continue to use `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` to add more files and folders to the list.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="3a594-274">Se `Add-MpPreference` usa para anexar o agregar aplicaciones a la lista.</span><span class="sxs-lookup"><span data-stu-id="3a594-274">Use `Add-MpPreference` to append or add apps to the list.</span></span> <span data-ttu-id="3a594-275">El `Set-MpPreference` uso del cmdlet sobrescribirá la lista existente.</span><span class="sxs-lookup"><span data-stu-id="3a594-275">Using the `Set-MpPreference` cmdlet will overwrite the existing list.</span></span>

## <a name="related-articles"></a><span data-ttu-id="3a594-276">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="3a594-276">Related articles</span></span>

- [<span data-ttu-id="3a594-277">Reducir superficies de ataque con reglas de reducción de superficie de ataque</span><span class="sxs-lookup"><span data-stu-id="3a594-277">Reduce attack surfaces with attack surface reduction rules</span></span>](attack-surface-reduction.md)

- [<span data-ttu-id="3a594-278">Evaluar la reducción de superficie de ataque</span><span class="sxs-lookup"><span data-stu-id="3a594-278">Evaluate attack surface reduction</span></span>](evaluate-attack-surface-reduction.md)

- [<span data-ttu-id="3a594-279">Preguntas más frecuentes sobre la reducción de la superficie expuesta a ataques</span><span class="sxs-lookup"><span data-stu-id="3a594-279">Attack surface reduction FAQ</span></span>](attack-surface-reduction.md)
