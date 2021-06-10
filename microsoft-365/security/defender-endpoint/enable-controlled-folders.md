---
title: Habilitar el acceso controlado a carpetas
keywords: Acceso controlado a carpetas, windows 10, Windows Defender, ransomware, protect, files, folders, enable, turn on, use
description: Obtenga información sobre cómo proteger los archivos importantes habilitando acceso controlado a carpetas
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.topic: article
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: dansimp
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 5a90a12457597fa38c648fd44bf194d2322a26af
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861229"
---
# <a name="enable-controlled-folder-access"></a><span data-ttu-id="64e16-104">Habilitar el acceso controlado a carpetas</span><span class="sxs-lookup"><span data-stu-id="64e16-104">Enable controlled folder access</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="64e16-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="64e16-105">**Applies to:**</span></span>
- [<span data-ttu-id="64e16-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="64e16-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="64e16-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="64e16-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="64e16-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="64e16-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="64e16-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="64e16-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="64e16-110">[El acceso controlado a](controlled-folders.md) carpetas te ayuda a proteger los datos valiosos de las amenazas y aplicaciones malintencionadas, como el ransomware.</span><span class="sxs-lookup"><span data-stu-id="64e16-110">[Controlled folder access](controlled-folders.md) helps you protect valuable data from malicious apps and threats, such as ransomware.</span></span> <span data-ttu-id="64e16-111">El acceso controlado a carpetas se incluye Windows 10 y Windows Server 2019.</span><span class="sxs-lookup"><span data-stu-id="64e16-111">Controlled folder access is included with Windows 10 and Windows Server 2019.</span></span>

<span data-ttu-id="64e16-112">Puede habilitar el acceso controlado a carpetas mediante cualquiera de estos métodos:</span><span class="sxs-lookup"><span data-stu-id="64e16-112">You can enable controlled folder access by using any of these methods:</span></span>

* [<span data-ttu-id="64e16-113">Seguridad de Windows app</span><span class="sxs-lookup"><span data-stu-id="64e16-113">Windows Security app</span></span>](#windows-security-app)
* [<span data-ttu-id="64e16-114">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="64e16-114">Microsoft Endpoint Manager</span></span>](#endpoint-manager)
* [<span data-ttu-id="64e16-115">Administración de dispositivos móviles (MDM)</span><span class="sxs-lookup"><span data-stu-id="64e16-115">Mobile Device Management (MDM)</span></span>](#mobile-device-management-mdm)
* [<span data-ttu-id="64e16-116">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="64e16-116">Microsoft Endpoint Configuration Manager</span></span>](#microsoft-endpoint-configuration-manager)
* [<span data-ttu-id="64e16-117">Directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="64e16-117">Group Policy</span></span>](#group-policy)
* [<span data-ttu-id="64e16-118">PowerShell</span><span class="sxs-lookup"><span data-stu-id="64e16-118">PowerShell</span></span>](#powershell)

<span data-ttu-id="64e16-119">[El modo auditoría](evaluate-controlled-folder-access.md) te permite probar cómo funcionaría la característica (y revisar los eventos) sin afectar al uso normal del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="64e16-119">[Audit mode](evaluate-controlled-folder-access.md) allows you to test how the feature would work (and review events) without impacting the normal use of the device.</span></span>

<span data-ttu-id="64e16-120">La configuración de directiva de grupo que deshabilita la combinación de listas de administradores locales invalidará la configuración de acceso controlado a carpetas.</span><span class="sxs-lookup"><span data-stu-id="64e16-120">Group Policy settings that disable local administrator list merging will override controlled folder access settings.</span></span> <span data-ttu-id="64e16-121">También invalidan las carpetas protegidas y las aplicaciones permitidas establecidas por el administrador local a través del acceso controlado a carpetas.</span><span class="sxs-lookup"><span data-stu-id="64e16-121">They also override protected folders and allowed apps set by the local administrator through controlled folder access.</span></span> <span data-ttu-id="64e16-122">Estas directivas incluyen:</span><span class="sxs-lookup"><span data-stu-id="64e16-122">These policies include:</span></span>

* <span data-ttu-id="64e16-123">Antivirus de Microsoft Defender configurar **el comportamiento de combinación de administradores locales para listas**</span><span class="sxs-lookup"><span data-stu-id="64e16-123">Microsoft Defender Antivirus **Configure local administrator merge behavior for lists**</span></span>
* <span data-ttu-id="64e16-124">System Center Endpoint Protection permitir **a los usuarios agregar exclusiones e invalidaciones**</span><span class="sxs-lookup"><span data-stu-id="64e16-124">System Center Endpoint Protection **Allow users to add exclusions and overrides**</span></span>

<span data-ttu-id="64e16-125">Para obtener más información sobre cómo deshabilitar la combinación de listas locales, vea [Prevent or allow users to locally modify Microsoft Defender AV policy settings](/windows/security/threat-protection/microsoft-defender-antivirus/configure-local-policy-overrides-microsoft-defender-antivirus#configure-how-locally-and-globally-defined-threat-remediation-and-exclusions-lists-are-merged).</span><span class="sxs-lookup"><span data-stu-id="64e16-125">For more information about disabling local list merging, see [Prevent or allow users to locally modify Microsoft Defender AV policy settings](/windows/security/threat-protection/microsoft-defender-antivirus/configure-local-policy-overrides-microsoft-defender-antivirus#configure-how-locally-and-globally-defined-threat-remediation-and-exclusions-lists-are-merged).</span></span>

## <a name="windows-security-app"></a><span data-ttu-id="64e16-126">Seguridad de Windows app</span><span class="sxs-lookup"><span data-stu-id="64e16-126">Windows Security app</span></span>

1. <span data-ttu-id="64e16-127">Abra la aplicación Seguridad de Windows mediante la selección del icono de escudo en la barra de tareas.</span><span class="sxs-lookup"><span data-stu-id="64e16-127">Open the Windows Security app by selecting the shield icon in the task bar.</span></span> <span data-ttu-id="64e16-128">También puede buscar en el menú inicio de **Defender**.</span><span class="sxs-lookup"><span data-stu-id="64e16-128">You can also search the start menu for **Defender**.</span></span>

2. <span data-ttu-id="64e16-129">Seleccione el **icono Protección contra &** virus (o el icono escudo de la barra de menús izquierda) y, a continuación, seleccione Protección contra **ransomware**.</span><span class="sxs-lookup"><span data-stu-id="64e16-129">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar) and then select **Ransomware protection**.</span></span>

3. <span data-ttu-id="64e16-130">Establezca el modificador para **Acceso controlado a carpetas** en **On**.</span><span class="sxs-lookup"><span data-stu-id="64e16-130">Set the switch for **Controlled folder access** to **On**.</span></span>

> [!NOTE]
> <span data-ttu-id="64e16-131">Si el acceso controlado a carpetas está configurado con directivas de grupo, PowerShell o CSP mdm, el estado cambiará en la aplicación Seguridad de Windows después de reiniciar el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="64e16-131">If controlled folder access is configured with Group Policy, PowerShell, or MDM CSPs, the state will change in the Windows Security app after a restart of the device.</span></span>
> <span data-ttu-id="64e16-132">Si la característica está establecida en **modo auditoría** con cualquiera de estas herramientas, la Seguridad de Windows aplicación mostrará el estado como **Desactivado**.</span><span class="sxs-lookup"><span data-stu-id="64e16-132">If the feature is set to **Audit mode** with any of those tools, the Windows Security app will show the state as **Off**.</span></span>
> <span data-ttu-id="64e16-133">Si protege los datos de perfil de usuario, se recomienda que el perfil de usuario esté en la unidad de instalación Windows usuario predeterminada.</span><span class="sxs-lookup"><span data-stu-id="64e16-133">If you are protecting user profile data, we recommend that the user profile should be on the default Windows installation drive.</span></span>

## <a name="endpoint-manager"></a><span data-ttu-id="64e16-134">Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="64e16-134">Endpoint Manager</span></span>

1. <span data-ttu-id="64e16-135">Inicie sesión en el [Endpoint Manager](https://endpoint.microsoft.com) y abra **Endpoint Security**.</span><span class="sxs-lookup"><span data-stu-id="64e16-135">Sign in to the [Endpoint Manager](https://endpoint.microsoft.com) and open **Endpoint Security**.</span></span>

2. <span data-ttu-id="64e16-136">Ve a **Directiva de reducción de superficie de**  >  **ataque**.</span><span class="sxs-lookup"><span data-stu-id="64e16-136">Go to **Attack Surface Reduction** > **Policy**.</span></span>

3. <span data-ttu-id="64e16-137">Selecciona **Plataforma,** elige **Windows 10 y posteriores** y selecciona el perfil Reglas de **reducción** de superficie de ataque  >  **Crear**.</span><span class="sxs-lookup"><span data-stu-id="64e16-137">Select **Platform**, choose **Windows 10 and later**, and select the profile **Attack Surface Reduction rules** > **Create**.</span></span>

4.  <span data-ttu-id="64e16-138">Asigne un nombre a la directiva y agregue una descripción.</span><span class="sxs-lookup"><span data-stu-id="64e16-138">Name the policy and add a description.</span></span> <span data-ttu-id="64e16-139">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="64e16-139">Select **Next**.</span></span>

5.  <span data-ttu-id="64e16-140">Desplácese hacia abajo hasta la parte inferior, seleccione la lista desplegable **Habilitar** protección de carpetas y elija **Habilitar**.</span><span class="sxs-lookup"><span data-stu-id="64e16-140">Scroll down to the bottom, select the **Enable Folder Protection** drop-down, and choose **Enable**.</span></span>

6.  <span data-ttu-id="64e16-141">Seleccione **Lista de carpetas adicionales que deben protegerse** y agregue las carpetas que deben protegerse.</span><span class="sxs-lookup"><span data-stu-id="64e16-141">Select **List of additional folders that need to be protected** and add the folders that need to be protected.</span></span>

7.  <span data-ttu-id="64e16-142">Selecciona **Lista de aplicaciones que tienen acceso a carpetas** protegidas y agrega las aplicaciones que tienen acceso a carpetas protegidas.</span><span class="sxs-lookup"><span data-stu-id="64e16-142">Select **List of apps that have access to protected folders** and add the apps that have access to protected folders.</span></span>

8.  <span data-ttu-id="64e16-143">Selecciona **Excluir archivos y rutas de acceso de** las reglas de reducción de superficie de ataque y agrega los archivos y rutas de acceso que deben excluirse de las reglas de reducción de superficie de ataque.</span><span class="sxs-lookup"><span data-stu-id="64e16-143">Select **Exclude files and paths from attack surface reduction rules** and add the files and paths that need to be excluded from attack surface reduction rules.</span></span>

9.  <span data-ttu-id="64e16-144">Seleccione el perfil Asignaciones , asignar a **Todos los usuarios & Todos** los **dispositivos** y seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="64e16-144">Select the profile **Assignments**, assign to **All Users & All Devices**, and select **Save**.</span></span>

10.  <span data-ttu-id="64e16-145">Seleccione **Siguiente** para guardar cada hoja abierta y, a continuación, **Crear**.</span><span class="sxs-lookup"><span data-stu-id="64e16-145">Select **Next** to save each open blade and then **Create**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="64e16-146">Los caracteres comodín se admiten para aplicaciones, pero no para carpetas.</span><span class="sxs-lookup"><span data-stu-id="64e16-146">Wildcards are supported for applications, but not for folders.</span></span> <span data-ttu-id="64e16-147">Las subcarpetas no están protegidas.</span><span class="sxs-lookup"><span data-stu-id="64e16-147">Subfolders are not protected.</span></span> <span data-ttu-id="64e16-148">Las aplicaciones permitidas seguirán desencadenando eventos hasta que se reinicien.</span><span class="sxs-lookup"><span data-stu-id="64e16-148">Allowed apps will continue to trigger events until they are restarted.</span></span>

## <a name="mobile-device-management-mdm"></a><span data-ttu-id="64e16-149">Administración de dispositivos móviles (MDM)</span><span class="sxs-lookup"><span data-stu-id="64e16-149">Mobile Device Management (MDM)</span></span>

<span data-ttu-id="64e16-150">Use el proveedor de servicios de configuración [./Vendor/MSFT/Policy/Config/ControlledFolderAccessProtectedFolders](/windows/client-management/mdm/policy-csp-defender#defender-controlledfolderaccessprotectedfolders) (CSP) para permitir que las aplicaciones realicen cambios en carpetas protegidas.</span><span class="sxs-lookup"><span data-stu-id="64e16-150">Use the [./Vendor/MSFT/Policy/Config/ControlledFolderAccessProtectedFolders](/windows/client-management/mdm/policy-csp-defender#defender-controlledfolderaccessprotectedfolders) configuration service provider (CSP) to allow apps to make changes to protected folders.</span></span>

## <a name="microsoft-endpoint-configuration-manager"></a><span data-ttu-id="64e16-151">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="64e16-151">Microsoft Endpoint Configuration Manager</span></span>

1. <span data-ttu-id="64e16-152">En Microsoft Endpoint Configuration Manager, vaya a **Assets and Compliance**  >  **Endpoint Protection** Windows Defender Exploit  >  **Guard**.</span><span class="sxs-lookup"><span data-stu-id="64e16-152">In Microsoft Endpoint Configuration Manager, go to **Assets and Compliance** > **Endpoint Protection** > **Windows Defender Exploit Guard**.</span></span>

2. <span data-ttu-id="64e16-153">Seleccione **Inicio Crear** directiva de protección contra  >  **vulnerabilidades** de seguridad .</span><span class="sxs-lookup"><span data-stu-id="64e16-153">Select **Home** > **Create Exploit Guard Policy**.</span></span>

3. <span data-ttu-id="64e16-154">Escriba un nombre y una descripción, seleccione Acceso controlado a **carpetas** y seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="64e16-154">Enter a name and a description, select **Controlled folder access**, and select **Next**.</span></span>

4. <span data-ttu-id="64e16-155">Elige si bloquea o audita los cambios, permite otras aplicaciones o agrega otras carpetas y selecciona **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="64e16-155">Choose whether block or audit changes, allow other apps, or add other folders, and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="64e16-156">Wilcard es compatible con aplicaciones, pero no para carpetas.</span><span class="sxs-lookup"><span data-stu-id="64e16-156">Wilcard is supported for applications, but not for folders.</span></span> <span data-ttu-id="64e16-157">Las subcarpetas no están protegidas.</span><span class="sxs-lookup"><span data-stu-id="64e16-157">Subfolders are not protected.</span></span> <span data-ttu-id="64e16-158">Las aplicaciones permitidas seguirán desencadenando eventos hasta que se reinicien.</span><span class="sxs-lookup"><span data-stu-id="64e16-158">Allowed apps will continue to trigger events until they are restarted.</span></span>

5. <span data-ttu-id="64e16-159">Revise la configuración y seleccione **Siguiente** para crear la directiva.</span><span class="sxs-lookup"><span data-stu-id="64e16-159">Review the settings and select **Next** to create the policy.</span></span>

6. <span data-ttu-id="64e16-160">Después de crear la directiva, **Cierre**.</span><span class="sxs-lookup"><span data-stu-id="64e16-160">After the policy is created, **Close**.</span></span>

## <a name="group-policy"></a><span data-ttu-id="64e16-161">Directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="64e16-161">Group Policy</span></span>

1. <span data-ttu-id="64e16-162">En el dispositivo de administración de directivas de grupo, abra la Consola de administración de directivas de [grupo,](https://technet.microsoft.com/library/cc731212.aspx)haga clic con el botón secundario en el objeto de directiva de grupo que desea configurar y **seleccione Editar**.</span><span class="sxs-lookup"><span data-stu-id="64e16-162">On your Group Policy management device, open the [Group Policy Management Console](https://technet.microsoft.com/library/cc731212.aspx), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="64e16-163">En el **Editor de administración de directiva de grupo**, vaya a **Configuración del equipo** y seleccione **Plantillas administrativas**.</span><span class="sxs-lookup"><span data-stu-id="64e16-163">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="64e16-164">Expanda el árbol para Windows **componentes > Antivirus de Microsoft Defender > Windows Defender Exploit Guard > acceso controlado a carpetas**.</span><span class="sxs-lookup"><span data-stu-id="64e16-164">Expand the tree to **Windows components > Microsoft Defender Antivirus > Windows Defender Exploit Guard > Controlled folder access**.</span></span>

4. <span data-ttu-id="64e16-165">Haga doble clic en la **opción Configurar acceso controlado a carpetas** y establezca la opción en **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="64e16-165">Double-click the **Configure Controlled folder access** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="64e16-166">En la sección opciones, debe especificar una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="64e16-166">In the options section you must specify one of the following options:</span></span>
    * <span data-ttu-id="64e16-167">**Habilitar:** las aplicaciones malintencionadas y sospechosas no podrán realizar cambios en los archivos de carpetas protegidas.</span><span class="sxs-lookup"><span data-stu-id="64e16-167">**Enable** - Malicious and suspicious apps won't be allowed to make changes to files in protected folders.</span></span> <span data-ttu-id="64e16-168">Se proporciona una notificación en el registro Windows eventos.</span><span class="sxs-lookup"><span data-stu-id="64e16-168">A notification will be provided in the Windows event log.</span></span>
    * <span data-ttu-id="64e16-169">**Deshabilitar (valor predeterminado):** la característica acceso controlado a carpetas no funcionará.</span><span class="sxs-lookup"><span data-stu-id="64e16-169">**Disable (Default)** - The Controlled folder access feature won't work.</span></span> <span data-ttu-id="64e16-170">Todas las aplicaciones pueden realizar cambios en los archivos de carpetas protegidas.</span><span class="sxs-lookup"><span data-stu-id="64e16-170">All apps can make changes to files in protected folders.</span></span>
    * <span data-ttu-id="64e16-171">**Modo auditoría:** se permitirán cambios si una aplicación malintencionada o sospechosa intenta realizar un cambio en un archivo de una carpeta protegida.</span><span class="sxs-lookup"><span data-stu-id="64e16-171">**Audit Mode** - Changes will be allowed if a malicious or suspicious app attempts to make a change to a file in a protected folder.</span></span> <span data-ttu-id="64e16-172">Sin embargo, se registrará en el registro Windows eventos donde puede evaluar el impacto en su organización.</span><span class="sxs-lookup"><span data-stu-id="64e16-172">However, it will be recorded in the Windows event log where you can assess the impact on your organization.</span></span>
    * <span data-ttu-id="64e16-173">**Bloquear solo modificación de disco:** los intentos de las aplicaciones que no son de confianza de escribir en los sectores de disco se iniciarán en Windows registro de eventos.</span><span class="sxs-lookup"><span data-stu-id="64e16-173">**Block disk modification only** - Attempts by untrusted apps to write to disk sectors will be logged in Windows Event log.</span></span> <span data-ttu-id="64e16-174">Estos registros se pueden encontrar en **Registros** de aplicaciones y servicios > Microsoft > Windows > Windows Defender > Operational > ID. 1123.</span><span class="sxs-lookup"><span data-stu-id="64e16-174">These logs can be found in **Applications and Services Logs** > Microsoft > Windows > Windows Defender > Operational > ID 1123.</span></span>
    * <span data-ttu-id="64e16-175">**Solo modificación** de disco de auditoría: solo se registrarán los intentos de escritura en los sectores de disco protegido en el registro de eventos de Windows (en Registros de aplicaciones y servicios Microsoft Windows Windows Defender Identificador operativo  >    >    >    >    >  **1124**).</span><span class="sxs-lookup"><span data-stu-id="64e16-175">**Audit disk modification only** - Only attempts to write to protected disk sectors will be recorded in the Windows event log (under **Applications and Services Logs** > **Microsoft** > **Windows** > **Windows Defender** > **Operational** > **ID 1124**).</span></span> <span data-ttu-id="64e16-176">No se registrarán los intentos de modificar o eliminar archivos en carpetas protegidas.</span><span class="sxs-lookup"><span data-stu-id="64e16-176">Attempts to modify or delete files in protected folders won't be recorded.</span></span>

      ![Captura de pantalla de la opción de directiva de grupo Habilitada y modo auditoría seleccionada en la lista desplegable](/microsoft-365/security/defender-endpoint/images/cfa-gp-enable)

> [!IMPORTANT]
> <span data-ttu-id="64e16-178">Para habilitar completamente el acceso controlado a carpetas, debe establecer la opción Directiva de grupo en **Habilitado** y seleccionar **Bloquear** en el menú desplegable opciones.</span><span class="sxs-lookup"><span data-stu-id="64e16-178">To fully enable controlled folder access, you must set the Group Policy option to **Enabled** and select **Block** in the options drop-down menu.</span></span>

## <a name="powershell"></a><span data-ttu-id="64e16-179">PowerShell</span><span class="sxs-lookup"><span data-stu-id="64e16-179">PowerShell</span></span>

1. <span data-ttu-id="64e16-180">Escriba **powershell** en el menú Inicio, haga clic con el botón **Windows PowerShell** y seleccione Ejecutar **como administrador**.</span><span class="sxs-lookup"><span data-stu-id="64e16-180">Type **powershell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="64e16-181">Escriba el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="64e16-181">Enter the following cmdlet:</span></span>

    ```PowerShell
    Set-MpPreference -EnableControlledFolderAccess Enabled
    ```

<span data-ttu-id="64e16-182">Puede habilitar la característica en modo auditoría especificando en `AuditMode` lugar de `Enabled` .</span><span class="sxs-lookup"><span data-stu-id="64e16-182">You can enable the feature in audit mode by specifying `AuditMode` instead of `Enabled`.</span></span>

<span data-ttu-id="64e16-183">Se `Disabled` usa para desactivar la característica.</span><span class="sxs-lookup"><span data-stu-id="64e16-183">Use `Disabled` to turn off the feature.</span></span>

## <a name="see-also"></a><span data-ttu-id="64e16-184">Consulte también</span><span class="sxs-lookup"><span data-stu-id="64e16-184">See also</span></span>

* [<span data-ttu-id="64e16-185">Proteger carpetas importantes con acceso controlado a carpetas</span><span class="sxs-lookup"><span data-stu-id="64e16-185">Protect important folders with controlled folder access</span></span>](controlled-folders.md)
* [<span data-ttu-id="64e16-186">Personalizar el acceso controlado a carpetas</span><span class="sxs-lookup"><span data-stu-id="64e16-186">Customize controlled folder access</span></span>](customize-controlled-folders.md)
* [<span data-ttu-id="64e16-187">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="64e16-187">Evaluate Microsoft Defender for Endpoint</span></span>](evaluate-mde.md)
