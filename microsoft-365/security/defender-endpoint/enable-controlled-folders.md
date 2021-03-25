---
title: Habilitar el acceso controlado a carpetas
keywords: Acceso controlado a carpetas, windows 10, Windows Defender, ransomware, protect, files, folders, enable, turn on, use
description: Obtenga información sobre cómo proteger los archivos importantes habilitando acceso controlado a carpetas
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: levinec
ms.author: ellevin
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 6d07e2a21bb01794990160cf02837fc524008098
ms.sourcegitcommit: 8685b0f7d53c99577fa65144ab60295dfa60f46f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2021
ms.locfileid: "51218765"
---
# <a name="enable-controlled-folder-access"></a><span data-ttu-id="1fde0-104">Habilitar el acceso controlado a carpetas</span><span class="sxs-lookup"><span data-stu-id="1fde0-104">Enable controlled folder access</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1fde0-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="1fde0-105">**Applies to:**</span></span>
- [<span data-ttu-id="1fde0-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="1fde0-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="1fde0-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1fde0-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="1fde0-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="1fde0-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="1fde0-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="1fde0-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="1fde0-110">[El acceso controlado a](controlled-folders.md) carpetas te ayuda a proteger los datos valiosos de las amenazas y aplicaciones malintencionadas, como el ransomware.</span><span class="sxs-lookup"><span data-stu-id="1fde0-110">[Controlled folder access](controlled-folders.md) helps you protect valuable data from malicious apps and threats, such as ransomware.</span></span> <span data-ttu-id="1fde0-111">El acceso controlado a carpetas se incluye con Windows 10 y Windows Server 2019.</span><span class="sxs-lookup"><span data-stu-id="1fde0-111">Controlled folder access is included with Windows 10 and Windows Server 2019.</span></span>

<span data-ttu-id="1fde0-112">Puede habilitar el acceso controlado a carpetas mediante cualquiera de estos métodos:</span><span class="sxs-lookup"><span data-stu-id="1fde0-112">You can enable controlled folder access by using any of these methods:</span></span>

* [<span data-ttu-id="1fde0-113">Aplicación seguridad de Windows</span><span class="sxs-lookup"><span data-stu-id="1fde0-113">Windows Security app</span></span>](#windows-security-app)
* [<span data-ttu-id="1fde0-114">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="1fde0-114">Microsoft Intune</span></span>](#intune)
* [<span data-ttu-id="1fde0-115">Administración de dispositivos móviles (MDM)</span><span class="sxs-lookup"><span data-stu-id="1fde0-115">Mobile Device Management (MDM)</span></span>](#mobile-device-management-mdm)
* [<span data-ttu-id="1fde0-116">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="1fde0-116">Microsoft Endpoint Configuration Manager</span></span>](#microsoft-endpoint-configuration-manager)
* [<span data-ttu-id="1fde0-117">Directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="1fde0-117">Group Policy</span></span>](#group-policy)
* [<span data-ttu-id="1fde0-118">PowerShell</span><span class="sxs-lookup"><span data-stu-id="1fde0-118">PowerShell</span></span>](#powershell)

<span data-ttu-id="1fde0-119">[El modo auditoría](evaluate-controlled-folder-access.md) te permite probar cómo funcionaría la característica (y revisar los eventos) sin afectar al uso normal del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="1fde0-119">[Audit mode](evaluate-controlled-folder-access.md) allows you to test how the feature would work (and review events) without impacting the normal use of the device.</span></span>

<span data-ttu-id="1fde0-120">La configuración de directiva de grupo que deshabilita la combinación de listas de administradores locales invalidará la configuración de acceso controlado a carpetas.</span><span class="sxs-lookup"><span data-stu-id="1fde0-120">Group Policy settings that disable local administrator list merging will override controlled folder access settings.</span></span> <span data-ttu-id="1fde0-121">También invalidan las carpetas protegidas y las aplicaciones permitidas establecidas por el administrador local a través del acceso controlado a carpetas.</span><span class="sxs-lookup"><span data-stu-id="1fde0-121">They also override protected folders and allowed apps set by the local administrator through controlled folder access.</span></span> <span data-ttu-id="1fde0-122">Estas directivas incluyen:</span><span class="sxs-lookup"><span data-stu-id="1fde0-122">These policies include:</span></span>

* <span data-ttu-id="1fde0-123">Antivirus de Microsoft Defender **Configure local administrator merge behavior for lists**</span><span class="sxs-lookup"><span data-stu-id="1fde0-123">Microsoft Defender Antivirus **Configure local administrator merge behavior for lists**</span></span>
* <span data-ttu-id="1fde0-124">System Center Endpoint Protection **Permitir a los usuarios agregar exclusiones e invalidaciones**</span><span class="sxs-lookup"><span data-stu-id="1fde0-124">System Center Endpoint Protection **Allow users to add exclusions and overrides**</span></span>

<span data-ttu-id="1fde0-125">Para obtener más información sobre cómo deshabilitar la combinación de listas locales, vea [Prevent or allow users to locally modify Microsoft Defender AV policy settings](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-local-policy-overrides-microsoft-defender-antivirus#configure-how-locally-and-globally-defined-threat-remediation-and-exclusions-lists-are-merged).</span><span class="sxs-lookup"><span data-stu-id="1fde0-125">For more information about disabling local list merging, see [Prevent or allow users to locally modify Microsoft Defender AV policy settings](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-local-policy-overrides-microsoft-defender-antivirus#configure-how-locally-and-globally-defined-threat-remediation-and-exclusions-lists-are-merged).</span></span>

## <a name="windows-security-app"></a><span data-ttu-id="1fde0-126">Aplicación seguridad de Windows</span><span class="sxs-lookup"><span data-stu-id="1fde0-126">Windows Security app</span></span>

1. <span data-ttu-id="1fde0-127">Abre la aplicación Seguridad de Windows seleccionando el icono de escudo en la barra de tareas.</span><span class="sxs-lookup"><span data-stu-id="1fde0-127">Open the Windows Security app by selecting the shield icon in the task bar.</span></span> <span data-ttu-id="1fde0-128">También puede buscar en el menú inicio de **Defender**.</span><span class="sxs-lookup"><span data-stu-id="1fde0-128">You can also search the start menu for **Defender**.</span></span>

2. <span data-ttu-id="1fde0-129">Seleccione el **icono Protección contra &** virus (o el icono escudo de la barra de menús izquierda) y, a continuación, seleccione Protección contra **ransomware**.</span><span class="sxs-lookup"><span data-stu-id="1fde0-129">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar) and then select **Ransomware protection**.</span></span>

3. <span data-ttu-id="1fde0-130">Establezca el modificador para **Acceso controlado a carpetas** en **On**.</span><span class="sxs-lookup"><span data-stu-id="1fde0-130">Set the switch for **Controlled folder access** to **On**.</span></span>

> [!NOTE]
> <span data-ttu-id="1fde0-131">Si el acceso controlado a carpetas está configurado con directivas de grupo, PowerShell o CSP mdm, el estado cambiará en la aplicación seguridad de Windows después de reiniciar el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="1fde0-131">If controlled folder access is configured with Group Policy, PowerShell, or MDM CSPs, the state will change in the Windows Security app after a restart of the device.</span></span>
> <span data-ttu-id="1fde0-132">Si la característica está establecida en **modo Auditoría** con cualquiera de estas herramientas, la aplicación Seguridad de Windows mostrará el estado como **Desactivado**.</span><span class="sxs-lookup"><span data-stu-id="1fde0-132">If the feature is set to **Audit mode** with any of those tools, the Windows Security app will show the state as **Off**.</span></span>
> <span data-ttu-id="1fde0-133">Si protege los datos de perfil de usuario, se recomienda que el perfil de usuario esté en la unidad de instalación predeterminada de Windows.</span><span class="sxs-lookup"><span data-stu-id="1fde0-133">If you are protecting user profile data, we recommend that the user profile should be on the default Windows installation drive.</span></span>

## <a name="intune"></a><span data-ttu-id="1fde0-134">Intune</span><span class="sxs-lookup"><span data-stu-id="1fde0-134">Intune</span></span>

1. <span data-ttu-id="1fde0-135">Inicie sesión en [Azure Portal y](https://portal.azure.com) abra Intune.</span><span class="sxs-lookup"><span data-stu-id="1fde0-135">Sign in to the [Azure portal](https://portal.azure.com) and open Intune.</span></span>

2. <span data-ttu-id="1fde0-136">Vaya a **Perfiles de configuración**  >  **de dispositivo Crear**  >  **perfil**.</span><span class="sxs-lookup"><span data-stu-id="1fde0-136">Go to **Device configuration** > **Profiles** > **Create profile**.</span></span>

3. <span data-ttu-id="1fde0-137">Asigne un nombre al perfil, **elija Windows 10 y versiones posteriores** y **Endpoint protection**.</span><span class="sxs-lookup"><span data-stu-id="1fde0-137">Name the profile, choose **Windows 10 and later** and **Endpoint protection**.</span></span> <br/> <span data-ttu-id="1fde0-138">![Crear perfil de protección de puntos de conexión](/microsoft-365/security/defender-endpoint/images/create-endpoint-protection-profile)</span><span class="sxs-lookup"><span data-stu-id="1fde0-138">![Create endpoint protection profile](/microsoft-365/security/defender-endpoint/images/create-endpoint-protection-profile)</span></span> <br/>

4. <span data-ttu-id="1fde0-139">Vaya a **Configure Windows Defender**  >  **Exploit Guard** Controlled folder  >  **access**  >  **Enable**.</span><span class="sxs-lookup"><span data-stu-id="1fde0-139">Go to **Configure** > **Windows Defender Exploit Guard** > **Controlled folder access** > **Enable**.</span></span>

5. <span data-ttu-id="1fde0-140">Escriba la ruta de acceso a cada aplicación que tenga acceso a carpetas protegidas y la ruta de acceso a cualquier carpeta adicional que necesite protección.</span><span class="sxs-lookup"><span data-stu-id="1fde0-140">Type the path to each application that has access to protected folders and the path to any additional folder that needs protection.</span></span> <span data-ttu-id="1fde0-141">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="1fde0-141">Select **Add**.</span></span><br/> <span data-ttu-id="1fde0-142">![Habilitar el acceso controlado a carpetas en Intune](/microsoft-365/security/defender-endpoint/images/enable-cfa-intune)</span><span class="sxs-lookup"><span data-stu-id="1fde0-142">![Enable controlled folder access in Intune](/microsoft-365/security/defender-endpoint/images/enable-cfa-intune)</span></span><br/>

   > [!NOTE]
   > <span data-ttu-id="1fde0-143">Wilcard es compatible con aplicaciones, pero no para carpetas.</span><span class="sxs-lookup"><span data-stu-id="1fde0-143">Wilcard is supported for applications, but not for folders.</span></span> <span data-ttu-id="1fde0-144">Las subcarpetas no están protegidas.</span><span class="sxs-lookup"><span data-stu-id="1fde0-144">Subfolders are not protected.</span></span> <span data-ttu-id="1fde0-145">Las aplicaciones permitidas seguirán desencadenando eventos hasta que se reinicien.</span><span class="sxs-lookup"><span data-stu-id="1fde0-145">Allowed apps will continue to trigger events until they are restarted.</span></span>

6. <span data-ttu-id="1fde0-146">Seleccione **Aceptar** para guardar cada hoja abierta y **Crear**.</span><span class="sxs-lookup"><span data-stu-id="1fde0-146">Select **OK** to save each open blade and **Create**.</span></span>

7. <span data-ttu-id="1fde0-147">Seleccione el perfil **Asignaciones**, asignar a Todos los usuarios & Todos los **dispositivos** y **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="1fde0-147">Select the profile **Assignments**, assign to **All Users & All Devices**, and **Save**.</span></span>

## <a name="mobile-device-management-mdm"></a><span data-ttu-id="1fde0-148">Administración de dispositivos móviles (MDM)</span><span class="sxs-lookup"><span data-stu-id="1fde0-148">Mobile Device Management (MDM)</span></span>

<span data-ttu-id="1fde0-149">Use el proveedor de servicios de configuración [./Vendor/MSFT/Policy/Config/ControlledFolderAccessProtectedFolders](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-controlledfolderaccessprotectedfolders) (CSP) para permitir que las aplicaciones realicen cambios en carpetas protegidas.</span><span class="sxs-lookup"><span data-stu-id="1fde0-149">Use the [./Vendor/MSFT/Policy/Config/ControlledFolderAccessProtectedFolders](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-controlledfolderaccessprotectedfolders) configuration service provider (CSP) to allow apps to make changes to protected folders.</span></span>

## <a name="microsoft-endpoint-configuration-manager"></a><span data-ttu-id="1fde0-150">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="1fde0-150">Microsoft Endpoint Configuration Manager</span></span>

1. <span data-ttu-id="1fde0-151">En Microsoft Endpoint Configuration Manager, vaya a **Assets and Compliance** Endpoint  >  **Protection** Windows Defender  >  **Exploit Guard**.</span><span class="sxs-lookup"><span data-stu-id="1fde0-151">In Microsoft Endpoint Configuration Manager, go to **Assets and Compliance** > **Endpoint Protection** > **Windows Defender Exploit Guard**.</span></span>

2. <span data-ttu-id="1fde0-152">Seleccione **Inicio Crear** directiva de protección contra  >  **vulnerabilidades** de seguridad .</span><span class="sxs-lookup"><span data-stu-id="1fde0-152">Select **Home** > **Create Exploit Guard Policy**.</span></span>

3. <span data-ttu-id="1fde0-153">Escriba un nombre y una descripción, seleccione Acceso controlado a **carpetas** y seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="1fde0-153">Enter a name and a description, select **Controlled folder access**, and select **Next**.</span></span>

4. <span data-ttu-id="1fde0-154">Elige si bloquea o audita los cambios, permite otras aplicaciones o agrega otras carpetas y selecciona **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="1fde0-154">Choose whether block or audit changes, allow other apps, or add other folders, and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="1fde0-155">Wilcard es compatible con aplicaciones, pero no para carpetas.</span><span class="sxs-lookup"><span data-stu-id="1fde0-155">Wilcard is supported for applications, but not for folders.</span></span> <span data-ttu-id="1fde0-156">Las subcarpetas no están protegidas.</span><span class="sxs-lookup"><span data-stu-id="1fde0-156">Subfolders are not protected.</span></span> <span data-ttu-id="1fde0-157">Las aplicaciones permitidas seguirán desencadenando eventos hasta que se reinicien.</span><span class="sxs-lookup"><span data-stu-id="1fde0-157">Allowed apps will continue to trigger events until they are restarted.</span></span>

5. <span data-ttu-id="1fde0-158">Revise la configuración y seleccione **Siguiente** para crear la directiva.</span><span class="sxs-lookup"><span data-stu-id="1fde0-158">Review the settings and select **Next** to create the policy.</span></span>

6. <span data-ttu-id="1fde0-159">Después de crear la directiva, **Cierre**.</span><span class="sxs-lookup"><span data-stu-id="1fde0-159">After the policy is created, **Close**.</span></span>

## <a name="group-policy"></a><span data-ttu-id="1fde0-160">Directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="1fde0-160">Group Policy</span></span>

1. <span data-ttu-id="1fde0-161">En el dispositivo de administración de directivas de grupo, abra la Consola de administración de directivas de [grupo,](https://technet.microsoft.com/library/cc731212.aspx)haga clic con el botón secundario en el objeto de directiva de grupo que desea configurar y **seleccione Editar**.</span><span class="sxs-lookup"><span data-stu-id="1fde0-161">On your Group Policy management device, open the [Group Policy Management Console](https://technet.microsoft.com/library/cc731212.aspx), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="1fde0-162">En el **Editor de administración de directivas de** grupo, vaya a Configuración del equipo **y** seleccione **Plantillas administrativas.**</span><span class="sxs-lookup"><span data-stu-id="1fde0-162">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="1fde0-163">Expande el árbol a **componentes de Windows > Antivirus de Microsoft Defender > Windows Defender Exploit Guard > acceso controlado a carpetas**.</span><span class="sxs-lookup"><span data-stu-id="1fde0-163">Expand the tree to **Windows components > Microsoft Defender Antivirus > Windows Defender Exploit Guard > Controlled folder access**.</span></span>

4. <span data-ttu-id="1fde0-164">Haga doble clic en la **opción Configurar acceso controlado a carpetas** y establezca la opción en **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="1fde0-164">Double-click the **Configure Controlled folder access** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="1fde0-165">En la sección opciones, debe especificar una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="1fde0-165">In the options section you must specify one of the following options:</span></span>
    * <span data-ttu-id="1fde0-166">**Habilitar:** las aplicaciones malintencionadas y sospechosas no podrán realizar cambios en los archivos de carpetas protegidas.</span><span class="sxs-lookup"><span data-stu-id="1fde0-166">**Enable** - Malicious and suspicious apps won't be allowed to make changes to files in protected folders.</span></span> <span data-ttu-id="1fde0-167">Se proporciona una notificación en el registro de eventos de Windows.</span><span class="sxs-lookup"><span data-stu-id="1fde0-167">A notification will be provided in the Windows event log.</span></span>
    * <span data-ttu-id="1fde0-168">**Deshabilitar (valor predeterminado):** la característica acceso controlado a carpetas no funcionará.</span><span class="sxs-lookup"><span data-stu-id="1fde0-168">**Disable (Default)** - The Controlled folder access feature won't work.</span></span> <span data-ttu-id="1fde0-169">Todas las aplicaciones pueden realizar cambios en los archivos de carpetas protegidas.</span><span class="sxs-lookup"><span data-stu-id="1fde0-169">All apps can make changes to files in protected folders.</span></span>
    * <span data-ttu-id="1fde0-170">**Modo auditoría:** se permitirán cambios si una aplicación malintencionada o sospechosa intenta realizar un cambio en un archivo de una carpeta protegida.</span><span class="sxs-lookup"><span data-stu-id="1fde0-170">**Audit Mode** - Changes will be allowed if a malicious or suspicious app attempts to make a change to a file in a protected folder.</span></span> <span data-ttu-id="1fde0-171">Sin embargo, se registrará en el registro de eventos de Windows, donde puedes evaluar el impacto en tu organización.</span><span class="sxs-lookup"><span data-stu-id="1fde0-171">However, it will be recorded in the Windows event log where you can assess the impact on your organization.</span></span>
    * <span data-ttu-id="1fde0-172">**Bloquear solo modificación de disco:** los intentos de las aplicaciones que no son de confianza de escribir en sectores de disco se registrarán en el registro de eventos de Windows.</span><span class="sxs-lookup"><span data-stu-id="1fde0-172">**Block disk modification only** - Attempts by untrusted apps to write to disk sectors will be logged in Windows Event log.</span></span> <span data-ttu-id="1fde0-173">Estos registros se pueden encontrar en **Registros** de aplicaciones y servicios > Microsoft > Windows > Windows Defender > Operational > ID. 1123.</span><span class="sxs-lookup"><span data-stu-id="1fde0-173">These logs can be found in **Applications and Services Logs** > Microsoft > Windows > Windows Defender > Operational > ID 1123.</span></span>
    * <span data-ttu-id="1fde0-174">**Solo modificación de** disco de auditoría: solo se registrarán los intentos de escritura en los sectores de disco protegido en el registro de eventos de Windows (en Registros de aplicaciones y servicios Microsoft Windows Windows Defender Identificador operativo  >    >    >    >    >  **1124**).</span><span class="sxs-lookup"><span data-stu-id="1fde0-174">**Audit disk modification only** - Only attempts to write to protected disk sectors will be recorded in the Windows event log (under **Applications and Services Logs** > **Microsoft** > **Windows** > **Windows Defender** > **Operational** > **ID 1124**).</span></span> <span data-ttu-id="1fde0-175">No se registrarán los intentos de modificar o eliminar archivos en carpetas protegidas.</span><span class="sxs-lookup"><span data-stu-id="1fde0-175">Attempts to modify or delete files in protected folders won't be recorded.</span></span>

      ![Captura de pantalla de la opción de directiva de grupo Habilitada y modo auditoría seleccionada en la lista desplegable](/microsoft-365/security/defender-endpoint/images/cfa-gp-enable)

> [!IMPORTANT]
> <span data-ttu-id="1fde0-177">Para habilitar completamente el acceso controlado a carpetas, debe establecer la opción Directiva de grupo en **Habilitado** y seleccionar **Bloquear** en el menú desplegable opciones.</span><span class="sxs-lookup"><span data-stu-id="1fde0-177">To fully enable controlled folder access, you must set the Group Policy option to **Enabled** and select **Block** in the options drop-down menu.</span></span>

## <a name="powershell"></a><span data-ttu-id="1fde0-178">PowerShell</span><span class="sxs-lookup"><span data-stu-id="1fde0-178">PowerShell</span></span>

1. <span data-ttu-id="1fde0-179">Escriba **powershell** en el menú Inicio, haga clic con el botón **secundario en Windows PowerShell** y seleccione Ejecutar como **administrador**.</span><span class="sxs-lookup"><span data-stu-id="1fde0-179">Type **powershell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="1fde0-180">Escriba el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="1fde0-180">Enter the following cmdlet:</span></span>

    ```PowerShell
    Set-MpPreference -EnableControlledFolderAccess Enabled
    ```

<span data-ttu-id="1fde0-181">Puede habilitar la característica en modo auditoría especificando en `AuditMode` lugar de `Enabled` .</span><span class="sxs-lookup"><span data-stu-id="1fde0-181">You can enable the feature in audit mode by specifying `AuditMode` instead of `Enabled`.</span></span>

<span data-ttu-id="1fde0-182">Se `Disabled` usa para desactivar la característica.</span><span class="sxs-lookup"><span data-stu-id="1fde0-182">Use `Disabled` to turn off the feature.</span></span>

## <a name="see-also"></a><span data-ttu-id="1fde0-183">Vea también</span><span class="sxs-lookup"><span data-stu-id="1fde0-183">See also</span></span>

* [<span data-ttu-id="1fde0-184">Proteger carpetas importantes con acceso controlado a carpetas</span><span class="sxs-lookup"><span data-stu-id="1fde0-184">Protect important folders with controlled folder access</span></span>](controlled-folders.md)
* [<span data-ttu-id="1fde0-185">Personalizar el acceso controlado a carpetas</span><span class="sxs-lookup"><span data-stu-id="1fde0-185">Customize controlled folder access</span></span>](customize-controlled-folders.md)
* [<span data-ttu-id="1fde0-186">Evaluar Microsoft Defender para el punto de conexión</span><span class="sxs-lookup"><span data-stu-id="1fde0-186">Evaluate Microsoft Defender for Endpoint</span></span>](evaluate-mde.md)
