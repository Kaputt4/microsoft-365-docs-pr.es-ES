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
ms.date: 05/10/2021
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: e12368b6241a2c79eead66ed77b30b7864af3955
ms.sourcegitcommit: 68383240ef7a673d5f28e2ecfab9f105bf1d8c8f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "52326540"
---
# <a name="customize-controlled-folder-access"></a><span data-ttu-id="c3bea-104">Personalizar el acceso controlado a carpetas</span><span class="sxs-lookup"><span data-stu-id="c3bea-104">Customize controlled folder access</span></span>

<span data-ttu-id="c3bea-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="c3bea-105">**Applies to:**</span></span>
- [<span data-ttu-id="c3bea-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="c3bea-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c3bea-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c3bea-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> <span data-ttu-id="c3bea-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="c3bea-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="c3bea-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="c3bea-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="c3bea-110">El acceso controlado a carpetas te ayuda a proteger los datos valiosos de las amenazas y aplicaciones malintencionadas, como el ransomware.</span><span class="sxs-lookup"><span data-stu-id="c3bea-110">Controlled folder access helps you protect valuable data from malicious apps and threats, such as ransomware.</span></span> <span data-ttu-id="c3bea-111">El acceso controlado a carpetas se admite Windows Server 2019 y Windows 10 cliente.</span><span class="sxs-lookup"><span data-stu-id="c3bea-111">Controlled folder access is supported on Windows Server 2019 and Windows 10 clients.</span></span> <span data-ttu-id="c3bea-112">En este artículo se describe cómo personalizar las capacidades de acceso controlado a carpetas e incluye las siguientes secciones:</span><span class="sxs-lookup"><span data-stu-id="c3bea-112">This article describes how to customize controlled folder access capabilities, and includes the following sections:</span></span>

- [<span data-ttu-id="c3bea-113">Proteger carpetas adicionales</span><span class="sxs-lookup"><span data-stu-id="c3bea-113">Protect additional folders</span></span>](#protect-additional-folders)
- [<span data-ttu-id="c3bea-114">Agregar aplicaciones que deben tener acceso a carpetas protegidas</span><span class="sxs-lookup"><span data-stu-id="c3bea-114">Add apps that should be allowed to access protected folders</span></span>](#allow-specific-apps-to-make-changes-to-controlled-folders)
- [<span data-ttu-id="c3bea-115">Permitir que los archivos ejecutables firmados accedan a carpetas protegidas</span><span class="sxs-lookup"><span data-stu-id="c3bea-115">Allow signed executable files to access protected folders</span></span>](#allow-signed-executable-files-to-access-protected-folders)
- [<span data-ttu-id="c3bea-116">Personalizar la notificación</span><span class="sxs-lookup"><span data-stu-id="c3bea-116">Customize the notification</span></span>](#customize-the-notification)

> [!IMPORTANT]
> <span data-ttu-id="c3bea-117">El acceso controlado a carpetas supervisa las aplicaciones para las actividades que se detectan como malintencionadas.</span><span class="sxs-lookup"><span data-stu-id="c3bea-117">Controlled folder access monitors apps for activities that are detected as malicious.</span></span> <span data-ttu-id="c3bea-118">A veces, las aplicaciones legítimas no pueden realizar cambios en los archivos.</span><span class="sxs-lookup"><span data-stu-id="c3bea-118">Sometimes, legitimate apps are blocked from making changes to your files.</span></span> <span data-ttu-id="c3bea-119">Si el acceso controlado a carpetas afecta a la productividad de la organización, es posible que considere la posibilidad de ejecutar esta característica en modo [auditoría](audit-windows-defender.md) para evaluar completamente el impacto.</span><span class="sxs-lookup"><span data-stu-id="c3bea-119">If controlled folder access impacts your organization's productivity, you might consider running this feature in [audit mode](audit-windows-defender.md) to fully assess the impact.</span></span>

## <a name="protect-additional-folders"></a><span data-ttu-id="c3bea-120">Proteger carpetas adicionales</span><span class="sxs-lookup"><span data-stu-id="c3bea-120">Protect additional folders</span></span>

<span data-ttu-id="c3bea-121">El acceso controlado a carpetas se aplica a muchas carpetas del sistema y ubicaciones predeterminadas, incluidas carpetas como **Documentos,** **Imágenes** y **Películas.**</span><span class="sxs-lookup"><span data-stu-id="c3bea-121">Controlled folder access applies to many system folders and default locations, including folders such as **Documents**, **Pictures**, and **Movies**.</span></span> <span data-ttu-id="c3bea-122">Puede agregar otras carpetas para protegerse, pero no puede quitar las carpetas predeterminadas de la lista predeterminada.</span><span class="sxs-lookup"><span data-stu-id="c3bea-122">You can add other folders to be protected, but you cannot remove the default folders in the default list.</span></span>

<span data-ttu-id="c3bea-123">Agregar otras carpetas al acceso controlado a carpetas puede ser útil para los casos en que no almacena archivos en las bibliotecas de Windows predeterminadas o si ha cambiado la ubicación predeterminada de las bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="c3bea-123">Adding other folders to controlled folder access can be helpful for cases when you don't store files in the default Windows libraries, or you've changed the default location of your libraries.</span></span>

<span data-ttu-id="c3bea-124">También puede especificar recursos compartidos de red y unidades asignadas.</span><span class="sxs-lookup"><span data-stu-id="c3bea-124">You can also specify network shares and mapped drives.</span></span> <span data-ttu-id="c3bea-125">Se admiten variables de entorno y caracteres comodín.</span><span class="sxs-lookup"><span data-stu-id="c3bea-125">Environment variables and wildcards are supported.</span></span> <span data-ttu-id="c3bea-126">Para obtener información sobre el uso de caracteres comodín, vea Usar caracteres comodín en las listas de exclusión de extensión o ruta de acceso de carpeta y [nombre de archivo.](configure-extension-file-exclusions-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="c3bea-126">For information about using wildcards, see [Use wildcards in the file name and folder path or extension exclusion lists](configure-extension-file-exclusions-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="c3bea-127">Puede usar la aplicación Seguridad de Windows, la directiva de grupo, los cmdlets de PowerShell o los proveedores de servicios de configuración de administración de dispositivos móviles para agregar y quitar carpetas protegidas.</span><span class="sxs-lookup"><span data-stu-id="c3bea-127">You can use the Windows Security app, Group Policy, PowerShell cmdlets, or mobile device management configuration service providers to add and remove protected folders.</span></span>

### <a name="use-the-windows-security-app-to-protect-additional-folders"></a><span data-ttu-id="c3bea-128">Usar la aplicación Seguridad de Windows para proteger carpetas adicionales</span><span class="sxs-lookup"><span data-stu-id="c3bea-128">Use the Windows Security app to protect additional folders</span></span>

1. <span data-ttu-id="c3bea-129">Abre la Seguridad de Windows de seguridad seleccionando el icono de escudo en la barra de tareas o buscando seguridad *en* el menú Inicio.</span><span class="sxs-lookup"><span data-stu-id="c3bea-129">Open the Windows Security app by selecting the shield icon in the task bar, or by searching for *security* in the Start menu.</span></span>

2. <span data-ttu-id="c3bea-130">Seleccione **Protección contra & virus y,** a continuación, desplácese hacia abajo hasta la sección Protección **contra** ransomware.</span><span class="sxs-lookup"><span data-stu-id="c3bea-130">Select **Virus & threat protection**, and then scroll down to the **Ransomware protection** section.</span></span>

3. <span data-ttu-id="c3bea-131">Seleccione **Administrar protección contra ransomware** para abrir el panel Protección **contra** ransomware.</span><span class="sxs-lookup"><span data-stu-id="c3bea-131">Select **Manage ransomware protection** to open the **Ransomware protection** pane.</span></span>

4. <span data-ttu-id="c3bea-132">En la **sección Acceso controlado a** carpetas, seleccione **Carpetas protegidas.**</span><span class="sxs-lookup"><span data-stu-id="c3bea-132">Under the **Controlled folder access** section, select **Protected folders**.</span></span>

5. <span data-ttu-id="c3bea-133">Elija **Sí en** el símbolo del sistema de control **de** acceso de usuario.</span><span class="sxs-lookup"><span data-stu-id="c3bea-133">Choose **Yes** on the **User Access Control** prompt.</span></span> <span data-ttu-id="c3bea-134">Se **muestra el panel Carpetas** protegidas.</span><span class="sxs-lookup"><span data-stu-id="c3bea-134">The **Protected folders** pane displays.</span></span>

6. <span data-ttu-id="c3bea-135">Seleccione **Agregar una carpeta protegida** y siga las instrucciones para agregar carpetas.</span><span class="sxs-lookup"><span data-stu-id="c3bea-135">Select **Add a protected folder** and follow the prompts to add folders.</span></span>

### <a name="use-group-policy-to-protect-additional-folders"></a><span data-ttu-id="c3bea-136">Usar la directiva de grupo para proteger carpetas adicionales</span><span class="sxs-lookup"><span data-stu-id="c3bea-136">Use Group Policy to protect additional folders</span></span>

1. <span data-ttu-id="c3bea-137">En el equipo de administración de directivas de grupo, abra la [Consola de administración de directivas de grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true).</span><span class="sxs-lookup"><span data-stu-id="c3bea-137">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true).</span></span> 

2. <span data-ttu-id="c3bea-138">Haga clic con el botón secundario en el objeto de directiva de grupo que desea configurar y, a continuación, **seleccione Editar**.</span><span class="sxs-lookup"><span data-stu-id="c3bea-138">Right-click the Group Policy Object you want to configure, and then select **Edit**.</span></span>

3. <span data-ttu-id="c3bea-139">En el **Editor de administración de directivas de** grupo, vaya a Directivas de **configuración** del equipo  >    >  **Plantillas administrativas.**</span><span class="sxs-lookup"><span data-stu-id="c3bea-139">In your **Group Policy Management Editor**, go to **Computer configuration** > **Policies** > **Administrative templates**.</span></span>

4. <span data-ttu-id="c3bea-140">Expanda el árbol para Windows **componentes Antivirus de Microsoft Defender** Windows Defender acceso controlado a carpetas de Protección contra  >    >    >  **vulnerabilidades de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="c3bea-140">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Windows Defender Exploit Guard** > **Controlled folder access**.</span></span> <br/><span data-ttu-id="c3bea-141">**NOTA**: En las versiones anteriores de Windows, es posible que vea Antivirus de Windows Defender **en** lugar de **Antivirus de Microsoft Defender**.</span><span class="sxs-lookup"><span data-stu-id="c3bea-141">**NOTE**: On older versions of Windows, you might see **Windows Defender Antivirus** instead of **Microsoft Defender Antivirus**.</span></span>

5. <span data-ttu-id="c3bea-142">Haga doble clic en **Carpetas protegidas configuradas** y, a continuación, establezca la opción en **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="c3bea-142">Double-click **Configured protected folders**, and then set the option to **Enabled**.</span></span> <span data-ttu-id="c3bea-143">Seleccione **Mostrar** y especifique cada carpeta que desee proteger.</span><span class="sxs-lookup"><span data-stu-id="c3bea-143">Select **Show**, and specify each folder that you want to protect.</span></span>

6. <span data-ttu-id="c3bea-144">Implemente el objeto de directiva de grupo como suele hacer.</span><span class="sxs-lookup"><span data-stu-id="c3bea-144">Deploy your Group Policy Object as you usually do.</span></span>

### <a name="use-powershell-to-protect-additional-folders"></a><span data-ttu-id="c3bea-145">Usar PowerShell para proteger carpetas adicionales</span><span class="sxs-lookup"><span data-stu-id="c3bea-145">Use PowerShell to protect additional folders</span></span>

1. <span data-ttu-id="c3bea-146">Escriba **PowerShell** en el menú Inicio, haga clic con el botón **secundario en Windows PowerShell** y seleccione Ejecutar como **administrador**</span><span class="sxs-lookup"><span data-stu-id="c3bea-146">Type **PowerShell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**</span></span>

2. <span data-ttu-id="c3bea-147">Escriba el siguiente cmdlet de PowerShell, reemplazando por la ruta de acceso de la carpeta `<the folder to be protected>` (por `"c:\apps\"` ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c3bea-147">Type the following PowerShell cmdlet, replacing `<the folder to be protected>` with the folder's path (such as `"c:\apps\"`):</span></span>

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessProtectedFolders "<the folder to be protected>"
    ```
3. <span data-ttu-id="c3bea-148">Repita el paso 2 para cada carpeta que desee proteger.</span><span class="sxs-lookup"><span data-stu-id="c3bea-148">Repeat step 2 for each folder that you want to protect.</span></span> <span data-ttu-id="c3bea-149">Las carpetas que están protegidas están visibles en la Seguridad de Windows aplicación.</span><span class="sxs-lookup"><span data-stu-id="c3bea-149">Folders that are protected are visible in the Windows Security app.</span></span>

   :::image type="content" source="images/cfa-allow-folder-ps.png" alt-text="Ventana de PowerShell con cmdlet mostrado":::

> [!IMPORTANT]
> <span data-ttu-id="c3bea-151">Se `Add-MpPreference` usa para anexar o agregar aplicaciones a la lista y no `Set-MpPreference` para .</span><span class="sxs-lookup"><span data-stu-id="c3bea-151">Use `Add-MpPreference` to append or add apps to the list and not `Set-MpPreference`.</span></span> <span data-ttu-id="c3bea-152">El `Set-MpPreference` uso del cmdlet sobrescribirá la lista existente.</span><span class="sxs-lookup"><span data-stu-id="c3bea-152">Using the `Set-MpPreference` cmdlet will overwrite the existing list.</span></span>

### <a name="use-mdm-csps-to-protect-additional-folders"></a><span data-ttu-id="c3bea-153">Usar CSP mdm para proteger carpetas adicionales</span><span class="sxs-lookup"><span data-stu-id="c3bea-153">Use MDM CSPs to protect additional folders</span></span>

<span data-ttu-id="c3bea-154">Use el proveedor de servicios de configuración [./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersList](/windows/client-management/mdm/policy-csp-defender#defender-guardedfolderslist) (CSP) para permitir que las aplicaciones realicen cambios en carpetas protegidas.</span><span class="sxs-lookup"><span data-stu-id="c3bea-154">Use the [./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersList](/windows/client-management/mdm/policy-csp-defender#defender-guardedfolderslist) configuration service provider (CSP) to allow apps to make changes to protected folders.</span></span>

## <a name="allow-specific-apps-to-make-changes-to-controlled-folders"></a><span data-ttu-id="c3bea-155">Permitir que aplicaciones específicas realicen cambios en carpetas controladas</span><span class="sxs-lookup"><span data-stu-id="c3bea-155">Allow specific apps to make changes to controlled folders</span></span>

<span data-ttu-id="c3bea-156">Puedes especificar si determinadas aplicaciones siempre se consideran seguras y dar acceso de escritura a archivos en carpetas protegidas.</span><span class="sxs-lookup"><span data-stu-id="c3bea-156">You can specify if certain apps are always considered safe and give write access to files in protected folders.</span></span> <span data-ttu-id="c3bea-157">Permitir aplicaciones puede ser útil si la característica de acceso controlado a carpetas bloquea una aplicación determinada que conoces y en la que confías.</span><span class="sxs-lookup"><span data-stu-id="c3bea-157">Allowing apps can be useful if a particular app you know and trust is being blocked by the controlled folder access feature.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c3bea-158">De forma predeterminada, Windows aplicaciones que se consideran fáciles de usar en la lista permitida.</span><span class="sxs-lookup"><span data-stu-id="c3bea-158">By default, Windows adds apps that are considered friendly to the allowed list.</span></span> <span data-ttu-id="c3bea-159">Estas aplicaciones que se agregan automáticamente no se registran en la lista que se muestra en la aplicación Seguridad de Windows o mediante los cmdlets de PowerShell asociados.</span><span class="sxs-lookup"><span data-stu-id="c3bea-159">Such apps that are added automatically are not recorded in the list shown in the Windows Security app or by using the associated PowerShell cmdlets.</span></span> <span data-ttu-id="c3bea-160">No debes agregar la mayoría de las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="c3bea-160">You shouldn't need to add most apps.</span></span> <span data-ttu-id="c3bea-161">Solo agrega aplicaciones si se bloquean y puedes comprobar su fiabilidad.</span><span class="sxs-lookup"><span data-stu-id="c3bea-161">Only add apps if they are being blocked and you can verify their trustworthiness.</span></span>

<span data-ttu-id="c3bea-162">Cuando agregas una aplicación, debes especificar la ubicación de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="c3bea-162">When you add an app, you have to specify the app's location.</span></span> <span data-ttu-id="c3bea-163">Solo se permitirá el acceso de la aplicación en esa ubicación a las carpetas protegidas.</span><span class="sxs-lookup"><span data-stu-id="c3bea-163">Only the app in that location will be permitted access to the protected folders.</span></span> <span data-ttu-id="c3bea-164">Si la aplicación (con el mismo nombre) está en una ubicación diferente, no se agregará a la lista de permitidos y puede bloquearse mediante el acceso controlado a carpetas.</span><span class="sxs-lookup"><span data-stu-id="c3bea-164">If the app (with the same name) is in a different location, it will not be added to the allowlist and may be blocked by controlled folder access.</span></span>

<span data-ttu-id="c3bea-165">Una aplicación o servicio permitido solo tiene acceso de escritura a una carpeta controlada después de que se inicie.</span><span class="sxs-lookup"><span data-stu-id="c3bea-165">An allowed application or service only has write access to a controlled folder after it starts.</span></span> <span data-ttu-id="c3bea-166">Por ejemplo, un servicio de actualización seguirá desencadenando eventos después de permitirlo hasta que se detenga y reinicie.</span><span class="sxs-lookup"><span data-stu-id="c3bea-166">For example, an update service will continue to trigger events after it's allowed until it is stopped and restarted.</span></span>

### <a name="use-the-windows-defender-security-app-to-allow-specific-apps"></a><span data-ttu-id="c3bea-167">Usar la aplicación Windows Defender seguridad para permitir aplicaciones específicas</span><span class="sxs-lookup"><span data-stu-id="c3bea-167">Use the Windows Defender Security app to allow specific apps</span></span>

1. <span data-ttu-id="c3bea-168">Abre la aplicación Seguridad de Windows búsqueda en el menú inicio de **Seguridad**.</span><span class="sxs-lookup"><span data-stu-id="c3bea-168">Open the Windows Security app by searching the start menu for **Security**.</span></span>

2. <span data-ttu-id="c3bea-169">Seleccione el **icono Protección contra &** virus (o el icono escudo de la barra de menús izquierda) y, a continuación, seleccione Administrar protección contra **ransomware**.</span><span class="sxs-lookup"><span data-stu-id="c3bea-169">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar) and then select **Manage ransomware protection**.</span></span>

3. <span data-ttu-id="c3bea-170">En la **sección Acceso controlado a carpetas,** selecciona Permitir una aplicación a través de Acceso controlado a **carpetas**</span><span class="sxs-lookup"><span data-stu-id="c3bea-170">Under the **Controlled folder access** section, select **Allow an app through Controlled folder access**</span></span>

4. <span data-ttu-id="c3bea-171">Selecciona **Agregar una aplicación permitida** y sigue las indicaciones para agregar aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="c3bea-171">Select **Add an allowed app** and follow the prompts to add apps.</span></span>

   :::image type="content" source="images/cfa-allow-app.png" alt-text="Agregar un botón de aplicación permitido":::

### <a name="use-group-policy-to-allow-specific-apps"></a><span data-ttu-id="c3bea-173">Usar la directiva de grupo para permitir aplicaciones específicas</span><span class="sxs-lookup"><span data-stu-id="c3bea-173">Use Group Policy to allow specific apps</span></span>

1. <span data-ttu-id="c3bea-174">En el dispositivo de administración de directivas de grupo, abra la Consola de administración de directivas de [grupo,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true)haga clic con el botón secundario en el objeto de directiva de grupo que desea configurar y **seleccione Editar**.</span><span class="sxs-lookup"><span data-stu-id="c3bea-174">On your Group Policy management device, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="c3bea-175">En el **Editor de administración de directiva de grupo**, vaya a **Configuración del equipo** y seleccione **Plantillas administrativas**.</span><span class="sxs-lookup"><span data-stu-id="c3bea-175">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="c3bea-176">Expanda el árbol para Windows **componentes Antivirus de Microsoft Defender** Windows Defender acceso controlado a carpetas de Protección contra  >    >    >  **vulnerabilidades de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="c3bea-176">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Windows Defender Exploit Guard** > **Controlled folder access**.</span></span>

4. <span data-ttu-id="c3bea-177">Haga doble clic en **la configuración Configurar aplicaciones permitidas** y establezca la opción en **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="c3bea-177">Double-click the **Configure allowed applications** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="c3bea-178">Selecciona **Mostrar** y escribe cada aplicación.</span><span class="sxs-lookup"><span data-stu-id="c3bea-178">Select **Show** and enter each app.</span></span>

### <a name="use-powershell-to-allow-specific-apps"></a><span data-ttu-id="c3bea-179">Usar PowerShell para permitir aplicaciones específicas</span><span class="sxs-lookup"><span data-stu-id="c3bea-179">Use PowerShell to allow specific apps</span></span>

1. <span data-ttu-id="c3bea-180">Escriba **PowerShell** en el menú Inicio, haga clic con el botón **secundario en Windows PowerShell** y seleccione Ejecutar como **administrador**</span><span class="sxs-lookup"><span data-stu-id="c3bea-180">Type **PowerShell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**</span></span>
2. <span data-ttu-id="c3bea-181">Escriba el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="c3bea-181">Enter the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessAllowedApplications "<the app that should be allowed, including the path>"
    ```

    <span data-ttu-id="c3bea-182">Por ejemplo, para agregar el archivo *ejecutabletest.exe* en la carpeta *C:\apps,* el cmdlet sería el siguiente:</span><span class="sxs-lookup"><span data-stu-id="c3bea-182">For example, to add the executable *test.exe* located in the folder *C:\apps*, the cmdlet would be as follows:</span></span>

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessAllowedApplications "c:\apps\test.exe"
    ```

   <span data-ttu-id="c3bea-183">Sigue usando para `Add-MpPreference -ControlledFolderAccessAllowedApplications` agregar más aplicaciones a la lista.</span><span class="sxs-lookup"><span data-stu-id="c3bea-183">Continue to use `Add-MpPreference -ControlledFolderAccessAllowedApplications` to add more apps to the list.</span></span> <span data-ttu-id="c3bea-184">Las aplicaciones agregadas con este cmdlet aparecerán en la Seguridad de Windows aplicación.</span><span class="sxs-lookup"><span data-stu-id="c3bea-184">Apps added using this cmdlet will appear in the Windows Security app.</span></span>

   :::image type="content" source="images/cfa-allow-app-ps.png" alt-text="Cmdlet de PowerShell para permitir una aplicación":::

> [!IMPORTANT]
> <span data-ttu-id="c3bea-186">Se `Add-MpPreference` usa para anexar o agregar aplicaciones a la lista.</span><span class="sxs-lookup"><span data-stu-id="c3bea-186">Use `Add-MpPreference` to append or add apps to the list.</span></span> <span data-ttu-id="c3bea-187">El `Set-MpPreference` uso del cmdlet sobrescribirá la lista existente.</span><span class="sxs-lookup"><span data-stu-id="c3bea-187">Using the `Set-MpPreference` cmdlet will overwrite the existing list.</span></span>

### <a name="use-mdm-csps-to-allow-specific-apps"></a><span data-ttu-id="c3bea-188">Usar CSP mdm para permitir aplicaciones específicas</span><span class="sxs-lookup"><span data-stu-id="c3bea-188">Use MDM CSPs to allow specific apps</span></span>

<span data-ttu-id="c3bea-189">Use el proveedor de servicios de configuración [./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersAllowedApplications](/windows/client-management/mdm/policy-csp-defender#defender-guardedfoldersallowedapplications) (CSP) para permitir que las aplicaciones realicen cambios en carpetas protegidas.</span><span class="sxs-lookup"><span data-stu-id="c3bea-189">Use the [./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersAllowedApplications](/windows/client-management/mdm/policy-csp-defender#defender-guardedfoldersallowedapplications) configuration service provider (CSP) to allow apps to make changes to protected folders.</span></span>

## <a name="allow-signed-executable-files-to-access-protected-folders"></a><span data-ttu-id="c3bea-190">Permitir que los archivos ejecutables firmados accedan a carpetas protegidas</span><span class="sxs-lookup"><span data-stu-id="c3bea-190">Allow signed executable files to access protected folders</span></span>

<span data-ttu-id="c3bea-191">Los indicadores de archivo y certificado de Microsoft Defender para endpoint pueden permitir que los archivos ejecutables firmados obtengan acceso a carpetas protegidas.</span><span class="sxs-lookup"><span data-stu-id="c3bea-191">Microsoft Defender for Endpoint certificate and file indicators can allow signed executable files to access protected folders.</span></span> <span data-ttu-id="c3bea-192">Para obtener más información sobre la implementación, [vea Crear indicadores basados en certificados.](indicator-certificates.md)</span><span class="sxs-lookup"><span data-stu-id="c3bea-192">For implementation details, see [Create indicators based on certificates](indicator-certificates.md).</span></span>

> [!Note]
> <span data-ttu-id="c3bea-193">Esto no se aplica a los motores de scripting, incluido Powershell</span><span class="sxs-lookup"><span data-stu-id="c3bea-193">This does no apply to scripting engines, including Powershell</span></span>

## <a name="customize-the-notification"></a><span data-ttu-id="c3bea-194">Personalizar la notificación</span><span class="sxs-lookup"><span data-stu-id="c3bea-194">Customize the notification</span></span>

<span data-ttu-id="c3bea-195">Para obtener más información acerca de cómo personalizar la notificación cuando se desencadena una regla y bloquea una aplicación o archivo, consulte [Configure alert notifications in Microsoft Defender for Endpoint](configure-email-notifications.md).</span><span class="sxs-lookup"><span data-stu-id="c3bea-195">For more information about customizing the notification when a rule is triggered and blocks an app or file, see [Configure alert notifications in Microsoft Defender for Endpoint](configure-email-notifications.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c3bea-196">Vea también</span><span class="sxs-lookup"><span data-stu-id="c3bea-196">See also</span></span>

- [<span data-ttu-id="c3bea-197">Proteger carpetas importantes con acceso controlado a carpetas</span><span class="sxs-lookup"><span data-stu-id="c3bea-197">Protect important folders with controlled folder access</span></span>](controlled-folders.md)
- [<span data-ttu-id="c3bea-198">Habilitar el acceso controlado a carpetas</span><span class="sxs-lookup"><span data-stu-id="c3bea-198">Enable controlled folder access</span></span>](enable-controlled-folders.md)
- [<span data-ttu-id="c3bea-199">Evaluar las reglas de la reducción de la superficie expuesta a ataques</span><span class="sxs-lookup"><span data-stu-id="c3bea-199">Evaluate attack surface reduction rules</span></span>](evaluate-attack-surface-reduction.md)
