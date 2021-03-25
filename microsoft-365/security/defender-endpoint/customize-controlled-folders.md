---
title: Personalizar el acceso controlado a carpetas
description: Agregue otras carpetas que deben estar protegidas por el acceso controlado a carpetas o permitir aplicaciones que bloqueen incorrectamente los cambios en archivos importantes.
keywords: Acceso controlado a carpetas, windows 10, Windows Defender, ransomware, protect, files, folders, customize, add folder, add app, allow, add executable
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: jcedola, dbodorin, vladiso, nixanm, anvascon
manager: dansimp
ms.date: 01/06/2021
ms.technology: mde
ms.openlocfilehash: 64f96544361a672881c590716adea80f40777c6e
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163344"
---
# <a name="customize-controlled-folder-access"></a><span data-ttu-id="80765-104">Personalizar el acceso controlado a carpetas</span><span class="sxs-lookup"><span data-stu-id="80765-104">Customize controlled folder access</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="80765-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="80765-105">**Applies to:**</span></span>
- [<span data-ttu-id="80765-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="80765-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="80765-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="80765-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="80765-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="80765-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="80765-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="80765-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)


<span data-ttu-id="80765-110">El acceso controlado a carpetas te ayuda a proteger los datos valiosos de las amenazas y aplicaciones malintencionadas, como el ransomware.</span><span class="sxs-lookup"><span data-stu-id="80765-110">Controlled folder access helps you protect valuable data from malicious apps and threats, such as ransomware.</span></span> <span data-ttu-id="80765-111">El acceso controlado a carpetas es compatible con clientes de Windows Server 2019 y Windows 10.</span><span class="sxs-lookup"><span data-stu-id="80765-111">Controlled folder access is supported on Windows Server 2019 and Windows 10 clients.</span></span>

<span data-ttu-id="80765-112">En este artículo se describe cómo personalizar las capacidades de acceso controlado a carpetas e incluye las siguientes secciones:</span><span class="sxs-lookup"><span data-stu-id="80765-112">This article describes how to customize controlled folder access capabilities, and includes the following sections:</span></span>

- [<span data-ttu-id="80765-113">Proteger carpetas adicionales</span><span class="sxs-lookup"><span data-stu-id="80765-113">Protect additional folders</span></span>](#protect-additional-folders)
- [<span data-ttu-id="80765-114">Agregar aplicaciones que deben tener acceso a carpetas protegidas</span><span class="sxs-lookup"><span data-stu-id="80765-114">Add apps that should be allowed to access protected folders</span></span>](#allow-specific-apps-to-make-changes-to-controlled-folders)
- [<span data-ttu-id="80765-115">Permitir que los archivos ejecutables firmados accedan a carpetas protegidas</span><span class="sxs-lookup"><span data-stu-id="80765-115">Allow signed executable files to access protected folders</span></span>](#allow-signed-executable-files-to-access-protected-folders)
- [<span data-ttu-id="80765-116">Personalizar la notificación</span><span class="sxs-lookup"><span data-stu-id="80765-116">Customize the notification</span></span>](#customize-the-notification)

> [!IMPORTANT]
> <span data-ttu-id="80765-117">El acceso controlado a carpetas supervisa las aplicaciones para las actividades que se detectan como malintencionadas.</span><span class="sxs-lookup"><span data-stu-id="80765-117">Controlled folder access monitors apps for activities that are detected as malicious.</span></span> <span data-ttu-id="80765-118">A veces, las aplicaciones legítimas no pueden realizar cambios en los archivos.</span><span class="sxs-lookup"><span data-stu-id="80765-118">Sometimes, legitimate apps are blocked from making changes to your files.</span></span> <span data-ttu-id="80765-119">Si el acceso controlado a carpetas afecta a la productividad de la organización, es posible que considere la posibilidad de ejecutar esta característica en modo [auditoría](audit-windows-defender.md) para evaluar completamente el impacto.</span><span class="sxs-lookup"><span data-stu-id="80765-119">If controlled folder access impacts your organization's productivity, you might consider running this feature in [audit mode](audit-windows-defender.md) to fully assess the impact.</span></span>

## <a name="protect-additional-folders"></a><span data-ttu-id="80765-120">Proteger carpetas adicionales</span><span class="sxs-lookup"><span data-stu-id="80765-120">Protect additional folders</span></span>

<span data-ttu-id="80765-121">El acceso controlado a carpetas se aplica a muchas carpetas del sistema y ubicaciones predeterminadas, incluidas carpetas como **Documentos,** **Imágenes** y **Películas.**</span><span class="sxs-lookup"><span data-stu-id="80765-121">Controlled folder access applies to many system folders and default locations, including folders such as **Documents**, **Pictures**, and **Movies**.</span></span> <span data-ttu-id="80765-122">Puede agregar carpetas adicionales para protegerse, pero no puede quitar las carpetas predeterminadas de la lista predeterminada.</span><span class="sxs-lookup"><span data-stu-id="80765-122">You can add additional folders to be protected, but you cannot remove the default folders in the default list.</span></span>

<span data-ttu-id="80765-123">Agregar otras carpetas al acceso controlado a carpetas puede ser útil para los casos en que no almacenas archivos en las bibliotecas predeterminadas de Windows o si has cambiado la ubicación predeterminada de tus bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="80765-123">Adding other folders to controlled folder access can be helpful for cases when you don't store files in the default Windows libraries, or you've changed the default location of your libraries.</span></span>

<span data-ttu-id="80765-124">También puede especificar recursos compartidos de red y unidades asignadas.</span><span class="sxs-lookup"><span data-stu-id="80765-124">You can also specify network shares and mapped drives.</span></span> <span data-ttu-id="80765-125">Se admiten variables de entorno y caracteres comodín.</span><span class="sxs-lookup"><span data-stu-id="80765-125">Environment variables and wildcards are supported.</span></span> <span data-ttu-id="80765-126">Para obtener información sobre el uso de caracteres comodín, vea Usar caracteres comodín en las listas de exclusión de extensión o ruta de acceso de carpeta y [nombre de archivo.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists)</span><span class="sxs-lookup"><span data-stu-id="80765-126">For information about using wildcards, see [Use wildcards in the file name and folder path or extension exclusion lists](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists).</span></span>

<span data-ttu-id="80765-127">Puede usar la aplicación seguridad de Windows, la directiva de grupo, los cmdlets de PowerShell o los proveedores de servicios de configuración de administración de dispositivos móviles para agregar y quitar carpetas protegidas adicionales.</span><span class="sxs-lookup"><span data-stu-id="80765-127">You can use the Windows Security app, Group Policy, PowerShell cmdlets, or mobile device management configuration service providers to add and remove additional protected folders.</span></span>

### <a name="use-the-windows-security-app-to-protect-additional-folders"></a><span data-ttu-id="80765-128">Usar la aplicación Seguridad de Windows para proteger carpetas adicionales</span><span class="sxs-lookup"><span data-stu-id="80765-128">Use the Windows Security app to protect additional folders</span></span>

1. <span data-ttu-id="80765-129">Abra la aplicación Seguridad de Windows seleccionando el icono de escudo en la barra de tareas o buscando en el menú inicio **seguridad**.</span><span class="sxs-lookup"><span data-stu-id="80765-129">Open the Windows Security app by selecting the shield icon in the task bar or searching the start menu for **Security**.</span></span>

2. <span data-ttu-id="80765-130">Seleccione **Protección contra & virus y,** a continuación, desplácese hacia abajo hasta la sección Protección **contra** ransomware.</span><span class="sxs-lookup"><span data-stu-id="80765-130">Select **Virus & threat protection**, and then scroll down to the **Ransomware protection** section.</span></span>

3. <span data-ttu-id="80765-131">Seleccione **Administrar protección contra ransomware** para abrir el panel Protección **contra** ransomware.</span><span class="sxs-lookup"><span data-stu-id="80765-131">Select **Manage ransomware protection** to open the **Ransomware protection** pane.</span></span>

4. <span data-ttu-id="80765-132">En la **sección Acceso controlado a** carpetas, seleccione **Carpetas protegidas.**</span><span class="sxs-lookup"><span data-stu-id="80765-132">Under the **Controlled folder access** section, select **Protected folders**.</span></span>

5. <span data-ttu-id="80765-133">Elija **Sí en** el símbolo del sistema de control **de** acceso de usuario.</span><span class="sxs-lookup"><span data-stu-id="80765-133">Choose **Yes** on the **User Access Control** prompt.</span></span> <span data-ttu-id="80765-134">Se **muestra el panel Carpetas** protegidas.</span><span class="sxs-lookup"><span data-stu-id="80765-134">The **Protected folders** pane displays.</span></span>

4. <span data-ttu-id="80765-135">Seleccione **Agregar una carpeta protegida** y siga las instrucciones para agregar carpetas.</span><span class="sxs-lookup"><span data-stu-id="80765-135">Select **Add a protected folder** and follow the prompts to add folders.</span></span>

### <a name="use-group-policy-to-protect-additional-folders"></a><span data-ttu-id="80765-136">Usar la directiva de grupo para proteger carpetas adicionales</span><span class="sxs-lookup"><span data-stu-id="80765-136">Use Group Policy to protect additional folders</span></span>

1. <span data-ttu-id="80765-137">En el equipo de administración de directivas de grupo, abra la Consola de administración de directivas de [grupo,](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true)haga clic con el botón secundario en el objeto de directiva de grupo que desea configurar y, a continuación, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="80765-137">On your Group Policy management computer, open the [Group Policy Management Console](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true), right-click the Group Policy Object you want to configure, and then and select **Edit**.</span></span>

2. <span data-ttu-id="80765-138">En el **Editor de administración de directivas de** grupo, vaya a Configuración del equipo **y** seleccione **Plantillas administrativas.**</span><span class="sxs-lookup"><span data-stu-id="80765-138">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="80765-139">Expande el árbol a **Componentes de Windows** Antivirus de Microsoft Defender  >  **Windows Defender** acceso controlado a  >  carpetas de **Protección**  >  **contra vulnerabilidades de seguridad.**</span><span class="sxs-lookup"><span data-stu-id="80765-139">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Windows Defender Exploit Guard** > **Controlled folder access**.</span></span>

4. <span data-ttu-id="80765-140">Haga doble clic **en Carpetas protegidas configuradas** y establezca la opción en **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="80765-140">Double-click **Configured protected folders** and set the option to **Enabled**.</span></span> <span data-ttu-id="80765-141">Seleccione **Mostrar** y escriba cada carpeta.</span><span class="sxs-lookup"><span data-stu-id="80765-141">Select **Show** and enter each folder.</span></span>

### <a name="use-powershell-to-protect-additional-folders"></a><span data-ttu-id="80765-142">Usar PowerShell para proteger carpetas adicionales</span><span class="sxs-lookup"><span data-stu-id="80765-142">Use PowerShell to protect additional folders</span></span>

1. <span data-ttu-id="80765-143">Escriba **PowerShell** en el menú Inicio, haga clic con el botón **secundario en Windows PowerShell** y seleccione Ejecutar como **administrador**</span><span class="sxs-lookup"><span data-stu-id="80765-143">Type **PowerShell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**</span></span>

2. <span data-ttu-id="80765-144">Escriba el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="80765-144">Enter the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessProtectedFolders "<the folder to be protected>"
    ```
3. <span data-ttu-id="80765-145">Repita el paso 2 hasta que haya agregado todas las carpetas que desea proteger.</span><span class="sxs-lookup"><span data-stu-id="80765-145">Repeat step 2 until you have added all the folders you want to protect.</span></span> <span data-ttu-id="80765-146">Las carpetas que se agregan están visibles en la aplicación Seguridad de Windows.</span><span class="sxs-lookup"><span data-stu-id="80765-146">Folders that are added are visible in the Windows Security app.</span></span>

   ![Captura de pantalla de una ventana de PowerShell con el cmdlet anterior especificado](/microsoft-365/security/defender-endpoint/images/cfa-allow-folder-ps)

> [!IMPORTANT]
> <span data-ttu-id="80765-148">Se `Add-MpPreference` usa para anexar o agregar aplicaciones a la lista.</span><span class="sxs-lookup"><span data-stu-id="80765-148">Use `Add-MpPreference` to append or add apps to the list.</span></span> <span data-ttu-id="80765-149">El `Set-MpPreference` uso del cmdlet sobrescribirá la lista existente.</span><span class="sxs-lookup"><span data-stu-id="80765-149">Using the `Set-MpPreference` cmdlet will overwrite the existing list.</span></span>

### <a name="use-mdm-csps-to-protect-additional-folders"></a><span data-ttu-id="80765-150">Usar CSP mdm para proteger carpetas adicionales</span><span class="sxs-lookup"><span data-stu-id="80765-150">Use MDM CSPs to protect additional folders</span></span>

<span data-ttu-id="80765-151">Use el proveedor de servicios de configuración [./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-guardedfolderslist) (CSP) para permitir que las aplicaciones realicen cambios en carpetas protegidas.</span><span class="sxs-lookup"><span data-stu-id="80765-151">Use the [./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-guardedfolderslist) configuration service provider (CSP) to allow apps to make changes to protected folders.</span></span>

## <a name="allow-specific-apps-to-make-changes-to-controlled-folders"></a><span data-ttu-id="80765-152">Permitir que aplicaciones específicas realicen cambios en carpetas controladas</span><span class="sxs-lookup"><span data-stu-id="80765-152">Allow specific apps to make changes to controlled folders</span></span>

<span data-ttu-id="80765-153">Puedes especificar si determinadas aplicaciones siempre se consideran seguras y dar acceso de escritura a archivos en carpetas protegidas.</span><span class="sxs-lookup"><span data-stu-id="80765-153">You can specify if certain apps are always considered safe and give write access to files in protected folders.</span></span> <span data-ttu-id="80765-154">Permitir aplicaciones puede ser útil si la característica de acceso controlado a carpetas bloquea una aplicación determinada que conoces y en la que confías.</span><span class="sxs-lookup"><span data-stu-id="80765-154">Allowing apps can be useful if a particular app you know and trust is being blocked by the controlled folder access feature.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="80765-155">De forma predeterminada, Windows agrega aplicaciones que se consideran fáciles de usar en la lista permitida.</span><span class="sxs-lookup"><span data-stu-id="80765-155">By default, Windows adds apps that are considered friendly to the allowed list.</span></span> <span data-ttu-id="80765-156">Estas aplicaciones que se agregan automáticamente no se registran en la lista que se muestra en la aplicación seguridad de Windows o mediante los cmdlets de PowerShell asociados.</span><span class="sxs-lookup"><span data-stu-id="80765-156">Such apps that are added automatically are not recorded in the list shown in the Windows Security app or by using the associated PowerShell cmdlets.</span></span> <span data-ttu-id="80765-157">No debes agregar la mayoría de las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="80765-157">You shouldn't need to add most apps.</span></span> <span data-ttu-id="80765-158">Solo agrega aplicaciones si se bloquean y puedes comprobar su fiabilidad.</span><span class="sxs-lookup"><span data-stu-id="80765-158">Only add apps if they are being blocked and you can verify their trustworthiness.</span></span>

<span data-ttu-id="80765-159">Cuando agregas una aplicación, debes especificar la ubicación de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="80765-159">When you add an app, you have to specify the app's location.</span></span> <span data-ttu-id="80765-160">Solo se permitirá el acceso de la aplicación en esa ubicación a las carpetas protegidas.</span><span class="sxs-lookup"><span data-stu-id="80765-160">Only the app in that location will be permitted access to the protected folders.</span></span> <span data-ttu-id="80765-161">Si la aplicación (con el mismo nombre) está en una ubicación diferente, no se agregará a la lista de permitidos y puede bloquearse mediante acceso controlado a carpetas.</span><span class="sxs-lookup"><span data-stu-id="80765-161">If the app (with the same name) is in a different location, it will not be added to the allow list and may be blocked by controlled folder access.</span></span>

<span data-ttu-id="80765-162">Una aplicación o servicio permitido solo tiene acceso de escritura a una carpeta controlada después de que se inicie.</span><span class="sxs-lookup"><span data-stu-id="80765-162">An allowed application or service only has write access to a controlled folder after it starts.</span></span> <span data-ttu-id="80765-163">Por ejemplo, un servicio de actualización seguirá desencadenando eventos después de permitirlo hasta que se detenga y reinicie.</span><span class="sxs-lookup"><span data-stu-id="80765-163">For example, an update service will continue to trigger events after it's allowed until it is stopped and restarted.</span></span>

### <a name="use-the-windows-defender-security-app-to-allow-specific-apps"></a><span data-ttu-id="80765-164">Usar la aplicación Windows Defender seguridad para permitir aplicaciones específicas</span><span class="sxs-lookup"><span data-stu-id="80765-164">Use the Windows Defender Security app to allow specific apps</span></span>

1. <span data-ttu-id="80765-165">Abra la aplicación Seguridad de Windows buscando en el menú inicio **seguridad**.</span><span class="sxs-lookup"><span data-stu-id="80765-165">Open the Windows Security app by searching the start menu for **Security**.</span></span>

2. <span data-ttu-id="80765-166">Seleccione el **icono Protección contra &** virus (o el icono escudo de la barra de menús izquierda) y, a continuación, seleccione Administrar protección contra **ransomware**.</span><span class="sxs-lookup"><span data-stu-id="80765-166">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar) and then select **Manage ransomware protection**.</span></span>

3. <span data-ttu-id="80765-167">En la **sección Acceso controlado a carpetas,** selecciona Permitir una aplicación a través de Acceso controlado a **carpetas**</span><span class="sxs-lookup"><span data-stu-id="80765-167">Under the **Controlled folder access** section, select **Allow an app through Controlled folder access**</span></span>

4. <span data-ttu-id="80765-168">Selecciona **Agregar una aplicación permitida** y sigue las indicaciones para agregar aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="80765-168">Select **Add an allowed app** and follow the prompts to add apps.</span></span>

    ![Captura de pantalla de cómo agregar un botón de aplicación permitido](/microsoft-365/security/defender-endpoint/images/cfa-allow-app)

### <a name="use-group-policy-to-allow-specific-apps"></a><span data-ttu-id="80765-170">Usar la directiva de grupo para permitir aplicaciones específicas</span><span class="sxs-lookup"><span data-stu-id="80765-170">Use Group Policy to allow specific apps</span></span>

1. <span data-ttu-id="80765-171">En el dispositivo de administración de directivas de grupo, abra la Consola de administración de directivas de [grupo,](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true)haga clic con el botón secundario en el objeto de directiva de grupo que desea configurar y **seleccione Editar**.</span><span class="sxs-lookup"><span data-stu-id="80765-171">On your Group Policy management device, open the [Group Policy Management Console](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="80765-172">En el **Editor de administración de directivas de** grupo, vaya a Configuración del equipo **y** seleccione **Plantillas administrativas.**</span><span class="sxs-lookup"><span data-stu-id="80765-172">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="80765-173">Expande el árbol a **Componentes de Windows** Antivirus de Microsoft Defender  >  **Windows Defender** acceso controlado a  >  carpetas de **Protección**  >  **contra vulnerabilidades de seguridad.**</span><span class="sxs-lookup"><span data-stu-id="80765-173">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Windows Defender Exploit Guard** > **Controlled folder access**.</span></span>

4. <span data-ttu-id="80765-174">Haga doble clic en **la configuración Configurar aplicaciones permitidas** y establezca la opción en **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="80765-174">Double-click the **Configure allowed applications** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="80765-175">Selecciona **Mostrar** y escribe cada aplicación.</span><span class="sxs-lookup"><span data-stu-id="80765-175">Select **Show** and enter each app.</span></span>

### <a name="use-powershell-to-allow-specific-apps"></a><span data-ttu-id="80765-176">Usar PowerShell para permitir aplicaciones específicas</span><span class="sxs-lookup"><span data-stu-id="80765-176">Use PowerShell to allow specific apps</span></span>

1. <span data-ttu-id="80765-177">Escriba **PowerShell** en el menú Inicio, haga clic con el botón **secundario en Windows PowerShell** y seleccione Ejecutar como **administrador**</span><span class="sxs-lookup"><span data-stu-id="80765-177">Type **PowerShell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**</span></span>
2. <span data-ttu-id="80765-178">Escriba el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="80765-178">Enter the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessAllowedApplications "<the app that should be allowed, including the path>"
    ```

    <span data-ttu-id="80765-179">Por ejemplo, para agregar el archivo *ejecutabletest.exe* en la carpeta *C:\apps,* el cmdlet sería el siguiente:</span><span class="sxs-lookup"><span data-stu-id="80765-179">For example, to add the executable *test.exe* located in the folder *C:\apps*, the cmdlet would be as follows:</span></span>

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessAllowedApplications "c:\apps\test.exe"
    ```

   <span data-ttu-id="80765-180">Sigue usando para `Add-MpPreference -ControlledFolderAccessAllowedApplications` agregar más aplicaciones a la lista.</span><span class="sxs-lookup"><span data-stu-id="80765-180">Continue to use `Add-MpPreference -ControlledFolderAccessAllowedApplications` to add more apps to the list.</span></span> <span data-ttu-id="80765-181">Las aplicaciones agregadas con este cmdlet aparecerán en la aplicación Seguridad de Windows.</span><span class="sxs-lookup"><span data-stu-id="80765-181">Apps added using this cmdlet will appear in the Windows Security app.</span></span>

![Captura de pantalla de una ventana de PowerShell con el cmdlet anterior especificado](/microsoft-365/security/defender-endpoint/images/cfa-allow-app-ps)

> [!IMPORTANT]
> <span data-ttu-id="80765-183">Se `Add-MpPreference` usa para anexar o agregar aplicaciones a la lista.</span><span class="sxs-lookup"><span data-stu-id="80765-183">Use `Add-MpPreference` to append or add apps to the list.</span></span> <span data-ttu-id="80765-184">El `Set-MpPreference` uso del cmdlet sobrescribirá la lista existente.</span><span class="sxs-lookup"><span data-stu-id="80765-184">Using the `Set-MpPreference` cmdlet will overwrite the existing list.</span></span>

### <a name="use-mdm-csps-to-allow-specific-apps"></a><span data-ttu-id="80765-185">Usar CSP mdm para permitir aplicaciones específicas</span><span class="sxs-lookup"><span data-stu-id="80765-185">Use MDM CSPs to allow specific apps</span></span>

<span data-ttu-id="80765-186">Use el proveedor de servicios de configuración [./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersAllowedApplications](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-guardedfoldersallowedapplications) (CSP) para permitir que las aplicaciones realicen cambios en carpetas protegidas.</span><span class="sxs-lookup"><span data-stu-id="80765-186">Use the [./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersAllowedApplications](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-guardedfoldersallowedapplications) configuration service provider (CSP) to allow apps to make changes to protected folders.</span></span>

## <a name="allow-signed-executable-files-to-access-protected-folders"></a><span data-ttu-id="80765-187">Permitir que los archivos ejecutables firmados accedan a carpetas protegidas</span><span class="sxs-lookup"><span data-stu-id="80765-187">Allow signed executable files to access protected folders</span></span>

<span data-ttu-id="80765-188">Los indicadores de archivo y certificado de Microsoft Defender para endpoint pueden permitir que los archivos ejecutables firmados obtengan acceso a carpetas protegidas.</span><span class="sxs-lookup"><span data-stu-id="80765-188">Microsoft Defender for Endpoint certificate and file indicators can allow signed executable files to access protected folders.</span></span> <span data-ttu-id="80765-189">Para obtener más información sobre la implementación, [vea Crear indicadores basados en certificados.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/indicator-certificates)</span><span class="sxs-lookup"><span data-stu-id="80765-189">For implementation details, see [Create indicators based on certificates](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/indicator-certificates).</span></span>

> [!Note]
> <span data-ttu-id="80765-190">Esto no se aplica a los motores de scripting, incluido Powershell</span><span class="sxs-lookup"><span data-stu-id="80765-190">This does no apply to scripting engines, including Powershell</span></span>

## <a name="customize-the-notification"></a><span data-ttu-id="80765-191">Personalizar la notificación</span><span class="sxs-lookup"><span data-stu-id="80765-191">Customize the notification</span></span>

<span data-ttu-id="80765-192">Para obtener más información acerca de cómo personalizar la notificación cuando se desencadena una regla y bloquea una aplicación o archivo, consulte [Configure alert notifications in Microsoft Defender for Endpoint](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-email-notifications).</span><span class="sxs-lookup"><span data-stu-id="80765-192">For more information about customizing the notification when a rule is triggered and blocks an app or file, see [Configure alert notifications in Microsoft Defender for Endpoint](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-email-notifications).</span></span>

## <a name="see-also"></a><span data-ttu-id="80765-193">Ver también</span><span class="sxs-lookup"><span data-stu-id="80765-193">See also</span></span>

- [<span data-ttu-id="80765-194">Proteger carpetas importantes con acceso controlado a carpetas</span><span class="sxs-lookup"><span data-stu-id="80765-194">Protect important folders with controlled folder access</span></span>](controlled-folders.md)
- [<span data-ttu-id="80765-195">Habilitar el acceso controlado a carpetas</span><span class="sxs-lookup"><span data-stu-id="80765-195">Enable controlled folder access</span></span>](enable-controlled-folders.md)
- [<span data-ttu-id="80765-196">Evaluar reglas de reducción de superficie de ataque</span><span class="sxs-lookup"><span data-stu-id="80765-196">Evaluate attack surface reduction rules</span></span>](evaluate-attack-surface-reduction.md)
