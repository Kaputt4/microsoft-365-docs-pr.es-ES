---
title: Antivirus de Microsoft Defender en la aplicación Seguridad de Windows aplicación
description: Con Antivirus de Microsoft Defender en la aplicación Seguridad de Windows, puedes revisar, comparar y realizar tareas comunes.
keywords: wdav, antivirus, firewall, seguridad, windows
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: ccb0d4cf168bbb4d3c1575c1e6611829909d0817
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275413"
---
# <a name="microsoft-defender-antivirus-in-the-windows-security-app"></a><span data-ttu-id="0acaf-104">Antivirus de Microsoft Defender en la aplicación Seguridad de Windows aplicación</span><span class="sxs-lookup"><span data-stu-id="0acaf-104">Microsoft Defender Antivirus in the Windows Security app</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="0acaf-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="0acaf-105">**Applies to:**</span></span>

- [<span data-ttu-id="0acaf-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="0acaf-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="0acaf-107">En Windows 10 versión 1703 y posteriores, la aplicación Windows Defender forma parte del Seguridad de Windows.</span><span class="sxs-lookup"><span data-stu-id="0acaf-107">In Windows 10, version 1703 and later, the Windows Defender app is part of the Windows Security.</span></span>

<span data-ttu-id="0acaf-108">Configuración que anteriormente formaban parte del cliente de Windows Defender y del Windows Configuración principal se han combinado y movido a la nueva aplicación, que se instala de forma predeterminada como parte de Windows 10, versión 1703.</span><span class="sxs-lookup"><span data-stu-id="0acaf-108">Settings that were previously part of the Windows Defender client and main Windows Settings have been combined and moved to the new app, which is installed by default as part of Windows 10, version 1703.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0acaf-109">Deshabilitar el servicio Seguridad de Windows centro no deshabilita Antivirus de Microsoft Defender o [Firewall de Windows Defender](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security).</span><span class="sxs-lookup"><span data-stu-id="0acaf-109">Disabling the Windows Security Center service does not disable Microsoft Defender Antivirus or [Windows Defender Firewall](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security).</span></span> <span data-ttu-id="0acaf-110">Estos se deshabilitan automáticamente cuando se instala un antivirus de terceros o un producto de firewall y se mantienen actualizados.</span><span class="sxs-lookup"><span data-stu-id="0acaf-110">These are disabled automatically when a third-party antivirus or firewall product is installed and kept up to date.</span></span>
>
> <span data-ttu-id="0acaf-111">Si deshabilita el servicio del Centro de Seguridad de Windows o configura sus opciones de directiva de grupo asociadas para evitar que se inicie o ejecute, la aplicación Seguridad de Windows puede mostrar información obsoleta o inexacta acerca de los productos antivirus o firewall que haya instalado en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0acaf-111">If you do disable the Windows Security Center service, or configure its associated Group Policy settings to prevent it from starting or running, the Windows Security app might display stale or inaccurate information about any antivirus or firewall products you have installed on the device.</span></span>
> <span data-ttu-id="0acaf-112">También puede impedir Antivirus de Microsoft Defender habilitarse si tiene un antivirus de terceros antiguo o obsoleto, o si desinstala productos antivirus de terceros que haya instalado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="0acaf-112">It might also prevent Microsoft Defender Antivirus from enabling itself if you have an old or outdated third-party antivirus, or if you uninstall any third-party antivirus products you might have previously installed.</span></span>
> <span data-ttu-id="0acaf-113">Esto disminuirá significativamente la protección del dispositivo y podría provocar una infección de malware.</span><span class="sxs-lookup"><span data-stu-id="0acaf-113">This will significantly lower the protection of your device and could lead to malware infection.</span></span>

<span data-ttu-id="0acaf-114">Consulta el [Seguridad de Windows para obtener](/windows/threat-protection/windows-defender-security-center/windows-defender-security-center) más información sobre otras Windows de seguridad que se pueden supervisar en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="0acaf-114">See the [Windows Security article](/windows/threat-protection/windows-defender-security-center/windows-defender-security-center) for more information on other Windows security features that can be monitored in the app.</span></span>

<span data-ttu-id="0acaf-115">La Seguridad de Windows es una interfaz de cliente en Windows 10 versión 1703 y posteriores.</span><span class="sxs-lookup"><span data-stu-id="0acaf-115">The Windows Security app is a client interface on Windows 10, version 1703 and later.</span></span> <span data-ttu-id="0acaf-116">No es el portal Centro de seguridad de Microsoft Defender web que se usa para revisar y administrar [Microsoft Defender para endpoint](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint).</span><span class="sxs-lookup"><span data-stu-id="0acaf-116">It is not the Microsoft Defender Security Center web portal that is used to review and manage [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint).</span></span>

## <a name="review-virus-and-threat-protection-settings-in-the-windows-security-app"></a><span data-ttu-id="0acaf-117">Revisar la configuración de protección contra virus y amenazas en la Seguridad de Windows aplicación</span><span class="sxs-lookup"><span data-stu-id="0acaf-117">Review virus and threat protection settings in the Windows Security app</span></span>

![Captura de pantalla de la etiqueta Protección contra virus y amenazas en la aplicación Seguridad de Windows](images/defender/wdav-protection-settings-wdsc.png)

1. <span data-ttu-id="0acaf-119">Abra la Seguridad de Windows haciendo clic en el icono de escudo de la barra de tareas o buscando en el menú inicio de **Defender**.</span><span class="sxs-lookup"><span data-stu-id="0acaf-119">Open the Windows Security app by clicking the shield icon in the task bar or searching the start menu for **Defender**.</span></span>

2. <span data-ttu-id="0acaf-120">Selecciona el **icono protección contra & virus** (o el icono de escudo de la barra de menús izquierda).</span><span class="sxs-lookup"><span data-stu-id="0acaf-120">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar).</span></span>
   
<span data-ttu-id="0acaf-121">En las secciones siguientes se describe cómo realizar algunas de las tareas más comunes al revisar o interactuar con la protección contra amenazas proporcionada por Antivirus de Microsoft Defender en la Seguridad de Windows aplicación.</span><span class="sxs-lookup"><span data-stu-id="0acaf-121">The following sections describe how to perform some of the most common tasks when reviewing or interacting with the threat protection provided by Microsoft Defender Antivirus in the Windows Security app.</span></span>

> [!NOTE]
> <span data-ttu-id="0acaf-122">Si estas opciones de configuración se configuran e implementan mediante la directiva de grupo, la configuración descrita en esta sección será gris y no estará disponible para su uso en puntos de conexión individuales.</span><span class="sxs-lookup"><span data-stu-id="0acaf-122">If these settings are configured and deployed using Group Policy, the settings described in this section will be greyed-out and unavailable for use on individual endpoints.</span></span> <span data-ttu-id="0acaf-123">Los cambios realizados a través de un objeto de directiva de grupo deben implementarse en primer lugar en los extremos individuales antes de que se actualice la configuración en la configuración de Windows.</span><span class="sxs-lookup"><span data-stu-id="0acaf-123">Changes made through a Group Policy Object must first be deployed to individual endpoints before the setting will be updated in Windows Settings.</span></span> <span data-ttu-id="0acaf-124">El [tema Configure end-user interaction with Antivirus de Microsoft Defender](configure-end-user-interaction-microsoft-defender-antivirus.md) describe cómo se puede configurar la configuración de invalidación de directiva local.</span><span class="sxs-lookup"><span data-stu-id="0acaf-124">The [Configure end-user interaction with Microsoft Defender Antivirus](configure-end-user-interaction-microsoft-defender-antivirus.md) topic describes how local policy override settings can be configured.</span></span>

## <a name="run-a-scan-with-the-windows-security-app"></a><span data-ttu-id="0acaf-125">Ejecutar un examen con la Seguridad de Windows aplicación</span><span class="sxs-lookup"><span data-stu-id="0acaf-125">Run a scan with the Windows Security app</span></span>

1. <span data-ttu-id="0acaf-126">Abra la aplicación Seguridad de Windows búsqueda en el menú inicio de Seguridad y, a continuación, seleccione **Seguridad de Windows**.</span><span class="sxs-lookup"><span data-stu-id="0acaf-126">Open the Windows Security app by searching the start menu for **Security**, and then selecting **Windows Security**.</span></span>

2. <span data-ttu-id="0acaf-127">Selecciona el **icono protección contra & virus** (o el icono de escudo de la barra de menús izquierda).</span><span class="sxs-lookup"><span data-stu-id="0acaf-127">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar).</span></span>

3. <span data-ttu-id="0acaf-128">Seleccione **Examen rápido**.</span><span class="sxs-lookup"><span data-stu-id="0acaf-128">Select **Quick scan**.</span></span> <span data-ttu-id="0acaf-129">O bien, para ejecutar un examen completo, seleccione **Opciones de** examen y, a continuación, seleccione una opción, como **Examen completo**.</span><span class="sxs-lookup"><span data-stu-id="0acaf-129">Or, to run a full scan, select **Scan options**, and then select an option, such as **Full scan**.</span></span>

## <a name="review-the-security-intelligence-update-version-and-download-the-latest-updates-in-the-windows-security-app"></a><span data-ttu-id="0acaf-130">Revisa la versión de actualización de inteligencia de seguridad y descarga las actualizaciones más recientes en la aplicación Seguridad de Windows seguridad</span><span class="sxs-lookup"><span data-stu-id="0acaf-130">Review the security intelligence update version and download the latest updates in the Windows Security app</span></span>

![Información del número de versión de inteligencia de seguridad](images/defender/wdav-wdsc-defs.png)

1. <span data-ttu-id="0acaf-132">Abra la aplicación Seguridad de Windows búsqueda en el menú inicio de Seguridad y, a continuación, seleccione **Seguridad de Windows**.</span><span class="sxs-lookup"><span data-stu-id="0acaf-132">Open the Windows Security app by searching the start menu for *Security*, and then selecting **Windows Security**.</span></span>

2. <span data-ttu-id="0acaf-133">Selecciona el **icono protección contra & virus** (o el icono de escudo de la barra de menús izquierda).</span><span class="sxs-lookup"><span data-stu-id="0acaf-133">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar).</span></span>

3. <span data-ttu-id="0acaf-134">Seleccione **Actualizaciones de protección contra & virus**.</span><span class="sxs-lookup"><span data-stu-id="0acaf-134">Select **Virus & threat protection updates**.</span></span> <span data-ttu-id="0acaf-135">La versión instalada actualmente se muestra junto con información sobre cuándo se descargó.</span><span class="sxs-lookup"><span data-stu-id="0acaf-135">The currently installed version is displayed along with some information about when it was downloaded.</span></span> <span data-ttu-id="0acaf-136">Puede comprobar la versión actual con la versión más reciente disponible para la descarga manual o revisar el registro de cambios de esa versión.</span><span class="sxs-lookup"><span data-stu-id="0acaf-136">You can check your current against the latest version available for manual download, or review the change log for that version.</span></span> <span data-ttu-id="0acaf-137">Vea [Security intelligence updates for Antivirus de Microsoft Defender and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span><span class="sxs-lookup"><span data-stu-id="0acaf-137">See [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

4. <span data-ttu-id="0acaf-138">Seleccione **Buscar actualizaciones para** descargar nuevas actualizaciones de protección (si las hay).</span><span class="sxs-lookup"><span data-stu-id="0acaf-138">Select **Check for updates** to download new protection updates (if there are any).</span></span>

## <a name="ensure-microsoft-defender-antivirus-is-enabled-in-the-windows-security-app"></a><span data-ttu-id="0acaf-139">Asegúrate Antivirus de Microsoft Defender está habilitado en la Seguridad de Windows aplicación</span><span class="sxs-lookup"><span data-stu-id="0acaf-139">Ensure Microsoft Defender Antivirus is enabled in the Windows Security app</span></span>

1. <span data-ttu-id="0acaf-140">Abra la aplicación Seguridad de Windows búsqueda en el menú inicio de Seguridad y, a continuación, seleccione **Seguridad de Windows**.</span><span class="sxs-lookup"><span data-stu-id="0acaf-140">Open the Windows Security app by searching the start menu for *Security*, and then selecting **Windows Security**.</span></span>

2. <span data-ttu-id="0acaf-141">Selecciona el **icono protección contra & virus** (o el icono de escudo de la barra de menús izquierda).</span><span class="sxs-lookup"><span data-stu-id="0acaf-141">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar).</span></span>

3. <span data-ttu-id="0acaf-142">Seleccione **Configuración de protección contra & virus**.</span><span class="sxs-lookup"><span data-stu-id="0acaf-142">Select **Virus & threat protection settings**.</span></span>

4. <span data-ttu-id="0acaf-143">Alterna el **conmutador de protección en tiempo** real a **On**.</span><span class="sxs-lookup"><span data-stu-id="0acaf-143">Toggle the **Real-time protection** switch to **On**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0acaf-144">Si desactiva la **protección en tiempo** real, se volverá a activar automáticamente después de un breve retraso.</span><span class="sxs-lookup"><span data-stu-id="0acaf-144">If you switch **Real-time protection** off, it will automatically turn back on after a short delay.</span></span> <span data-ttu-id="0acaf-145">Esto es para asegurarse de que está protegido contra malware y amenazas.</span><span class="sxs-lookup"><span data-stu-id="0acaf-145">This is to ensure you are protected from malware and threats.</span></span>
    > <span data-ttu-id="0acaf-146">Si instalas otro producto antivirus, Antivirus de Microsoft Defender se deshabilita automáticamente y se indica como tal en la Seguridad de Windows aplicación.</span><span class="sxs-lookup"><span data-stu-id="0acaf-146">If you install another antivirus product, Microsoft Defender Antivirus automatically disables itself and is indicated as such in the Windows Security app.</span></span> <span data-ttu-id="0acaf-147">Aparecerá una configuración que le permitirá habilitar el [examen periódico limitado.](limited-periodic-scanning-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="0acaf-147">A setting will appear that will allow you to enable [limited periodic scanning](limited-periodic-scanning-microsoft-defender-antivirus.md).</span></span>

## <a name="add-exclusions-for-microsoft-defender-antivirus-in-the-windows-security-app"></a><span data-ttu-id="0acaf-148">Agregar exclusiones para Antivirus de Microsoft Defender en la Seguridad de Windows aplicación</span><span class="sxs-lookup"><span data-stu-id="0acaf-148">Add exclusions for Microsoft Defender Antivirus in the Windows Security app</span></span>

1. <span data-ttu-id="0acaf-149">Abra la aplicación Seguridad de Windows búsqueda en el menú inicio de Seguridad y, a continuación, seleccione **Seguridad de Windows**.</span><span class="sxs-lookup"><span data-stu-id="0acaf-149">Open the Windows Security app by searching the start menu for *Security*, and then selecting **Windows Security**.</span></span>

2. <span data-ttu-id="0acaf-150">Selecciona el **icono protección contra & virus** (o el icono de escudo de la barra de menús izquierda).</span><span class="sxs-lookup"><span data-stu-id="0acaf-150">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar).</span></span>

3. <span data-ttu-id="0acaf-151">En Administrar **configuración,** seleccione **Virus & configuración de protección contra amenazas**.</span><span class="sxs-lookup"><span data-stu-id="0acaf-151">Under the **Manage settings**, select **Virus & threat protection settings**.</span></span>

4. <span data-ttu-id="0acaf-152">En la **configuración Exclusiones,** seleccione **Agregar o quitar exclusiones**.</span><span class="sxs-lookup"><span data-stu-id="0acaf-152">Under the **Exclusions** setting, select **Add or remove exclusions**.</span></span> 

5. <span data-ttu-id="0acaf-153">Seleccione el icono más ( **+** ) para elegir el tipo y establecer las opciones para cada exclusión.</span><span class="sxs-lookup"><span data-stu-id="0acaf-153">Select the plus icon (**+**) to choose the type and set the options for each exclusion.</span></span> 

<span data-ttu-id="0acaf-154">En la tabla siguiente se resumen los tipos de exclusión y lo que sucede:</span><span class="sxs-lookup"><span data-stu-id="0acaf-154">The following table summarizes exclusion types and what happens:</span></span>

|<span data-ttu-id="0acaf-155">Tipo de exclusión</span><span class="sxs-lookup"><span data-stu-id="0acaf-155">Exclusion type</span></span>  |<span data-ttu-id="0acaf-156">Definido por</span><span class="sxs-lookup"><span data-stu-id="0acaf-156">Defined by</span></span>  |<span data-ttu-id="0acaf-157">Qué ocurre</span><span class="sxs-lookup"><span data-stu-id="0acaf-157">What happens</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="0acaf-158">**Archivo**</span><span class="sxs-lookup"><span data-stu-id="0acaf-158">**File**</span></span> |<span data-ttu-id="0acaf-159">Ubicación</span><span class="sxs-lookup"><span data-stu-id="0acaf-159">Location</span></span> <br/><span data-ttu-id="0acaf-160">Ejemplo: `c:\sample\sample.test`</span><span class="sxs-lookup"><span data-stu-id="0acaf-160">Example: `c:\sample\sample.test`</span></span> |<span data-ttu-id="0acaf-161">El archivo específico se omite Antivirus de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="0acaf-161">The specific file is skipped by Microsoft Defender Antivirus.</span></span> |
|<span data-ttu-id="0acaf-162">**Folder**</span><span class="sxs-lookup"><span data-stu-id="0acaf-162">**Folder**</span></span>    |<span data-ttu-id="0acaf-163">Ubicación</span><span class="sxs-lookup"><span data-stu-id="0acaf-163">Location</span></span> <br/><span data-ttu-id="0acaf-164">Ejemplo: `c:\test\sample`</span><span class="sxs-lookup"><span data-stu-id="0acaf-164">Example: `c:\test\sample`</span></span>       |<span data-ttu-id="0acaf-165">Todos los elementos de la carpeta especificada se omiten Antivirus de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="0acaf-165">All items in the specified folder are skipped by Microsoft Defender Antivirus.</span></span>         |
|<span data-ttu-id="0acaf-166">**Tipo de archivo**</span><span class="sxs-lookup"><span data-stu-id="0acaf-166">**File type**</span></span>   |<span data-ttu-id="0acaf-167">Extensión de archivo</span><span class="sxs-lookup"><span data-stu-id="0acaf-167">File extension</span></span> <br/><span data-ttu-id="0acaf-168">Ejemplo: `.test`</span><span class="sxs-lookup"><span data-stu-id="0acaf-168">Example: `.test`</span></span> |<span data-ttu-id="0acaf-169">Todos los archivos con la extensión en cualquier lugar del dispositivo `.test` se omiten Antivirus de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="0acaf-169">All files with the `.test` extension anywhere on your device are skipped by Microsoft Defender Antivirus.</span></span>         |
|<span data-ttu-id="0acaf-170">**Proceso**</span><span class="sxs-lookup"><span data-stu-id="0acaf-170">**Process**</span></span>     |<span data-ttu-id="0acaf-171">Ruta de acceso de archivo ejecutable</span><span class="sxs-lookup"><span data-stu-id="0acaf-171">Executable file path</span></span> <br><span data-ttu-id="0acaf-172">Ejemplo: `c:\test\process.exe`</span><span class="sxs-lookup"><span data-stu-id="0acaf-172">Example: `c:\test\process.exe`</span></span>         |<span data-ttu-id="0acaf-173">El proceso específico y los archivos abiertos por ese proceso se omiten Antivirus de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="0acaf-173">The specific process and any files that are opened by that process are skipped by Microsoft Defender Antivirus.</span></span>         |

<span data-ttu-id="0acaf-174">Para obtener más información, consulte los siguientes recursos:</span><span class="sxs-lookup"><span data-stu-id="0acaf-174">To learn more, see the following resources:</span></span>
- [<span data-ttu-id="0acaf-175">Configurar y validar exclusiones en función de la extensión de archivo y la ubicación de la carpeta</span><span class="sxs-lookup"><span data-stu-id="0acaf-175">Configure and validate exclusions based on file extension and folder location</span></span>](./configure-extension-file-exclusions-microsoft-defender-antivirus.md) 
- [<span data-ttu-id="0acaf-176">Configurar exclusiones para archivos abiertos por procesos</span><span class="sxs-lookup"><span data-stu-id="0acaf-176">Configure exclusions for files opened by processes</span></span>](./configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)

## <a name="review-threat-detection-history-in-the-windows-defender-security-center-app"></a><span data-ttu-id="0acaf-177">Revisar el historial de detección de amenazas en la Windows Defender centro de seguridad</span><span class="sxs-lookup"><span data-stu-id="0acaf-177">Review threat detection history in the Windows Defender Security Center app</span></span>

1. <span data-ttu-id="0acaf-178">Abra la aplicación Seguridad de Windows búsqueda en el menú inicio de Seguridad y, a continuación, seleccione **Seguridad de Windows**.</span><span class="sxs-lookup"><span data-stu-id="0acaf-178">Open the Windows Security app by searching the start menu for *Security*, and then selecting **Windows Security**.</span></span>

2. <span data-ttu-id="0acaf-179">Selecciona el **icono protección contra & virus** (o el icono de escudo de la barra de menús izquierda).</span><span class="sxs-lookup"><span data-stu-id="0acaf-179">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar).</span></span>

3. <span data-ttu-id="0acaf-180">Seleccione **Historial de protección**.</span><span class="sxs-lookup"><span data-stu-id="0acaf-180">Select **Protection history**.</span></span> <span data-ttu-id="0acaf-181">Se enumeran los elementos recientes.</span><span class="sxs-lookup"><span data-stu-id="0acaf-181">Any recent items are listed.</span></span>

## <a name="set-ransomware-protection-and-recovery-options"></a><span data-ttu-id="0acaf-182">Establecer opciones de protección y recuperación de ransomware</span><span class="sxs-lookup"><span data-stu-id="0acaf-182">Set ransomware protection and recovery options</span></span>

1. <span data-ttu-id="0acaf-183">Abra la aplicación Seguridad de Windows búsqueda en el menú inicio de Seguridad y, a continuación, seleccione **Seguridad de Windows**.</span><span class="sxs-lookup"><span data-stu-id="0acaf-183">Open the Windows Security app by searching the start menu for *Security*, and then selecting **Windows Security**.</span></span>

2. <span data-ttu-id="0acaf-184">Selecciona el **icono protección contra & virus** (o el icono de escudo de la barra de menús izquierda).</span><span class="sxs-lookup"><span data-stu-id="0acaf-184">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar).</span></span>

3. <span data-ttu-id="0acaf-185">En **Protección contra ransomware,** seleccione **Administrar protección contra ransomware**.</span><span class="sxs-lookup"><span data-stu-id="0acaf-185">Under **Ransomware protection**, select **Manage ransomware protection**.</span></span>

4. <span data-ttu-id="0acaf-186">Para cambiar **la configuración de acceso controlado a** carpetas, vea Proteger [carpetas importantes con acceso controlado a carpetas.](/microsoft-365/security/defender-endpoint/controlled-folders)</span><span class="sxs-lookup"><span data-stu-id="0acaf-186">To change **Controlled folder access** settings, see [Protect important folders with Controlled folder access](/microsoft-365/security/defender-endpoint/controlled-folders).</span></span>

5. <span data-ttu-id="0acaf-187">Para configurar las opciones  de recuperación de ransomware, selecciona Configurar en Recuperación de datos ransomware y sigue las instrucciones para vincular o configurar tu cuenta de OneDrive para que puedas recuperarte fácilmente de un ataque de ransomware. </span><span class="sxs-lookup"><span data-stu-id="0acaf-187">To set up ransomware recovery options, select **Set up** under **Ransomware data recovery** and follow the instructions for linking or setting up your OneDrive account so you can easily recover from a ransomware attack.</span></span>

## <a name="see-also"></a><span data-ttu-id="0acaf-188">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0acaf-188">See also</span></span>
- [<span data-ttu-id="0acaf-189">Antivirus de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="0acaf-189">Microsoft Defender Antivirus</span></span>](microsoft-defender-antivirus-in-windows-10.md)