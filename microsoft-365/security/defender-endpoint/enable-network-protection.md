---
title: Habilitar protección de red
description: Habilite la protección de red con la directiva de grupo, PowerShell o Mobile Device Management y Configuration Manager.
keywords: Protección de ANetwork, vulnerabilidades, sitio web malintencionado, ip, dominio, dominios, habilitar, activar
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: dansimp
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: a513013c4b5f41cf95b876648882cb56ba818b32
ms.sourcegitcommit: 6e5c00f84b5201422aed094f2697016407df8fc2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2021
ms.locfileid: "51571001"
---
# <a name="turn-on-network-protection"></a><span data-ttu-id="32f7d-104">Habilitar protección de red</span><span class="sxs-lookup"><span data-stu-id="32f7d-104">Turn on network protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="32f7d-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="32f7d-105">**Applies to:**</span></span>
- [<span data-ttu-id="32f7d-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="32f7d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="32f7d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="32f7d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="32f7d-108">¿Desea experimentar Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="32f7d-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="32f7d-109">Regístrate para obtener una versión de prueba gratuita.</span><span class="sxs-lookup"><span data-stu-id="32f7d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="32f7d-110">[La protección de](network-protection.md) red ayuda a evitar que los empleados utilicen cualquier aplicación para tener acceso a dominios peligrosos que pueden hospedar estafas de phishing, vulnerabilidades de seguridad y otro contenido malintencionado en Internet.</span><span class="sxs-lookup"><span data-stu-id="32f7d-110">[Network protection](network-protection.md) helps to prevent employees from using any application to access dangerous domains that may host phishing scams, exploits, and other malicious content on the internet.</span></span> <span data-ttu-id="32f7d-111">Puedes [auditar la protección de red](evaluate-network-protection.md) en un entorno de prueba para ver qué aplicaciones se bloquearían antes de habilitarla.</span><span class="sxs-lookup"><span data-stu-id="32f7d-111">You can [audit network protection](evaluate-network-protection.md) in a test environment to view which apps would be blocked before you enable it.</span></span>

[<span data-ttu-id="32f7d-112">Más información sobre las opciones de configuración de filtrado de red</span><span class="sxs-lookup"><span data-stu-id="32f7d-112">Learn more about network filtering configuration options</span></span>](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10#network-filtering)

## <a name="check-if-network-protection-is-enabled"></a><span data-ttu-id="32f7d-113">Comprobar si la protección de red está habilitada</span><span class="sxs-lookup"><span data-stu-id="32f7d-113">Check if network protection is enabled</span></span>

<span data-ttu-id="32f7d-114">Compruebe si la protección de red se ha habilitado en un dispositivo local mediante el editor del Registro.</span><span class="sxs-lookup"><span data-stu-id="32f7d-114">Check if network protection has been enabled on a local device by using Registry editor.</span></span>

1. <span data-ttu-id="32f7d-115">Seleccione el **botón Inicio** en la barra de tareas y escriba **regedit** para abrir el editor del Registro</span><span class="sxs-lookup"><span data-stu-id="32f7d-115">Select the **Start** button in the task bar and type **regedit** to open Registry editor</span></span>
1. <span data-ttu-id="32f7d-116">Elija **HKEY_LOCAL_MACHINE** en el menú lateral</span><span class="sxs-lookup"><span data-stu-id="32f7d-116">Choose **HKEY_LOCAL_MACHINE** from the side menu</span></span>
1. <span data-ttu-id="32f7d-117">Navegue por los menús anidados a **Directivas de SOFTWARE** de  >    >  **Microsoft**  >  **Windows Defender** Windows Defender Protección  >  **de red de Protección contra**  >  **vulnerabilidades de seguridad**</span><span class="sxs-lookup"><span data-stu-id="32f7d-117">Navigate through the nested menus to **SOFTWARE** > **Policies** > **Microsoft** > **Windows Defender** > **Windows Defender Exploit Guard** > **Network Protection**</span></span>
1. <span data-ttu-id="32f7d-118">Selecciona **EnableNetworkProtection** para ver el estado actual de la protección de red en el dispositivo</span><span class="sxs-lookup"><span data-stu-id="32f7d-118">Select **EnableNetworkProtection** to see the current state of network protection on the device</span></span>

    * <span data-ttu-id="32f7d-119">0 o **Desactivado**</span><span class="sxs-lookup"><span data-stu-id="32f7d-119">0, or **Off**</span></span>
    * <span data-ttu-id="32f7d-120">1 o **On**</span><span class="sxs-lookup"><span data-stu-id="32f7d-120">1, or **On**</span></span>
    * <span data-ttu-id="32f7d-121">2, o modo **auditoría**</span><span class="sxs-lookup"><span data-stu-id="32f7d-121">2, or **Audit** mode</span></span>
    
    ![networkprotection](https://user-images.githubusercontent.com/3296790/95341270-b738b280-08d3-11eb-84a0-16abb140c9fd.PNG)

## <a name="enable-network-protection"></a><span data-ttu-id="32f7d-123">Habilitar la protección de red</span><span class="sxs-lookup"><span data-stu-id="32f7d-123">Enable network protection</span></span>

<span data-ttu-id="32f7d-124">Habilite la protección de red mediante cualquiera de estos métodos:</span><span class="sxs-lookup"><span data-stu-id="32f7d-124">Enable network protection by using any of these methods:</span></span>

* [<span data-ttu-id="32f7d-125">PowerShell</span><span class="sxs-lookup"><span data-stu-id="32f7d-125">PowerShell</span></span>](#powershell)
* [<span data-ttu-id="32f7d-126">Administración de dispositivos móviles (MDM)</span><span class="sxs-lookup"><span data-stu-id="32f7d-126">Mobile Device Management (MDM)</span></span>](#mobile-device-management-mdm)
* [<span data-ttu-id="32f7d-127">Microsoft Endpoint Manager /Intune</span><span class="sxs-lookup"><span data-stu-id="32f7d-127">Microsoft Endpoint Manager / Intune</span></span>](#microsoft-endpoint-manager-formerly-intune)
* [<span data-ttu-id="32f7d-128">Directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="32f7d-128">Group Policy</span></span>](#group-policy)

### <a name="powershell"></a><span data-ttu-id="32f7d-129">PowerShell</span><span class="sxs-lookup"><span data-stu-id="32f7d-129">PowerShell</span></span>

1. <span data-ttu-id="32f7d-130">Escriba **powershell** en el menú Inicio, haga clic con el Windows PowerShell **y** seleccione Ejecutar como **administrador**</span><span class="sxs-lookup"><span data-stu-id="32f7d-130">Type **powershell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**</span></span>
2. <span data-ttu-id="32f7d-131">Escriba el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="32f7d-131">Enter the following cmdlet:</span></span>

    ```PowerShell
    Set-MpPreference -EnableNetworkProtection Enabled
    ```

3. <span data-ttu-id="32f7d-132">Opcional: habilite la característica en modo auditoría con el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="32f7d-132">Optional: Enable the feature in audit mode using the following cmdlet:</span></span>

    ```PowerShell
    Set-MpPreference -EnableNetworkProtection AuditMode
    ```

    <span data-ttu-id="32f7d-133">Use `Disabled` en lugar de o para desactivar la `AuditMode` `Enabled` característica.</span><span class="sxs-lookup"><span data-stu-id="32f7d-133">Use `Disabled` instead of `AuditMode` or `Enabled` to turn off the feature.</span></span>

### <a name="mobile-device-management-mdm"></a><span data-ttu-id="32f7d-134">Administración de dispositivos móviles (MDM)</span><span class="sxs-lookup"><span data-stu-id="32f7d-134">Mobile device management (MDM)</span></span>

<span data-ttu-id="32f7d-135">Use [el proveedor ./Vendor/MSFT/Policy/Config/Defender/EnableNetworkProtection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-enablenetworkprotection) configuration service provider (CSP) para habilitar o deshabilitar la protección de red o habilitar el modo de auditoría.</span><span class="sxs-lookup"><span data-stu-id="32f7d-135">Use the [./Vendor/MSFT/Policy/Config/Defender/EnableNetworkProtection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-enablenetworkprotection) configuration service provider (CSP) to enable or disable network protection or enable audit mode.</span></span>

### <a name="microsoft-endpoint-manager-formerly-intune"></a><span data-ttu-id="32f7d-136">Microsoft Endpoint Manager (anteriormente Intune)</span><span class="sxs-lookup"><span data-stu-id="32f7d-136">Microsoft Endpoint Manager (formerly Intune)</span></span>

1. <span data-ttu-id="32f7d-137">Inicie sesión en el Centro de administración de Microsoft Endpoint Manager (https://endpoint.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="32f7d-137">Sign into the Microsoft Endpoint Manager admin center (https://endpoint.microsoft.com)</span></span>

2. <span data-ttu-id="32f7d-138">Crear o editar un perfil de [configuración de endpoint protection](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-configure)</span><span class="sxs-lookup"><span data-stu-id="32f7d-138">Create or edit an [endpoint protection configuration profile](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-configure)</span></span>

3. <span data-ttu-id="32f7d-139">En "Configuración de configuración" en el flujo de perfiles, vaya a Protección de red de Protección contra vulnerabilidades de seguridad de **Microsoft Defender** Habilitar o  >    >    >   **auditar solo**</span><span class="sxs-lookup"><span data-stu-id="32f7d-139">Under "Configuration Settings" in the profile flow, go to **Microsoft Defender Exploit Guard** > **Network filtering** > **Network protection** > **Enable** or **Audit only**</span></span>

### <a name="group-policy"></a><span data-ttu-id="32f7d-140">Directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="32f7d-140">Group Policy</span></span>

<span data-ttu-id="32f7d-141">Use el siguiente procedimiento para habilitar la protección de red en equipos unidos a un dominio o en un equipo independiente.</span><span class="sxs-lookup"><span data-stu-id="32f7d-141">Use the following procedure to enable network protection on domain-joined computers or on a standalone computer.</span></span>

1. <span data-ttu-id="32f7d-142">En un equipo independiente, vaya a **Inicio** y, a continuación, escriba y seleccione **Editar directiva de grupo**.</span><span class="sxs-lookup"><span data-stu-id="32f7d-142">On a standalone computer, go to **Start** and then type and select **Edit group policy**.</span></span>

    <span data-ttu-id="32f7d-143">*-Or-*</span><span class="sxs-lookup"><span data-stu-id="32f7d-143">*-Or-*</span></span>

    <span data-ttu-id="32f7d-144">En un equipo de administración de directivas de grupo unido a un dominio, abra la Consola de administración de directivas de grupo [,](https://technet.microsoft.com/library/cc731212.aspx)haga clic con el botón secundario en el objeto de directiva de grupo que desea configurar y **seleccione Editar**.</span><span class="sxs-lookup"><span data-stu-id="32f7d-144">On a domain-joined Group Policy management computer, open the [Group Policy Management Console](https://technet.microsoft.com/library/cc731212.aspx), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="32f7d-145">En el **Editor de administración de directivas de** grupo, vaya a Configuración del equipo **y** seleccione **Plantillas administrativas.**</span><span class="sxs-lookup"><span data-stu-id="32f7d-145">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="32f7d-146">Expande el árbol a **Componentes de Windows** Antivirus de Microsoft Defender  >  **Windows Defender** protección de la red de  >  **Protección** contra  >  **vulnerabilidades de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="32f7d-146">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Windows Defender Exploit Guard** > **Network protection**.</span></span>

> [!NOTE]
> <span data-ttu-id="32f7d-147">En versiones anteriores de Windows, la ruta de acceso de directiva de grupo puede decir "Windows Defender Antivirus" en lugar de "Antivirus de Microsoft Defender".</span><span class="sxs-lookup"><span data-stu-id="32f7d-147">On older versions of Windows, the group policy path may say "Windows Defender Antivirus" instead of "Microsoft Defender Antivirus."</span></span>

4. <span data-ttu-id="32f7d-148">Haz doble clic en la configuración **Impedir que los usuarios y aplicaciones** tengan acceso a sitios web peligrosos y establece la opción en **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="32f7d-148">Double-click the **Prevent users and apps from accessing dangerous websites** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="32f7d-149">En la sección opciones, debe especificar una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="32f7d-149">In the options section, you must specify one of the following options:</span></span>
    * <span data-ttu-id="32f7d-150">**Bloquear:** los usuarios no pueden acceder a direcciones IP malintencionadas y dominios</span><span class="sxs-lookup"><span data-stu-id="32f7d-150">**Block** - Users can't access malicious IP addresses and domains</span></span>
    * <span data-ttu-id="32f7d-151">**Deshabilitar (predeterminado):** la característica de protección de red no funcionará.</span><span class="sxs-lookup"><span data-stu-id="32f7d-151">**Disable (Default)** - The Network protection feature won't work.</span></span> <span data-ttu-id="32f7d-152">Los usuarios no se bloquearán para acceder a dominios malintencionados</span><span class="sxs-lookup"><span data-stu-id="32f7d-152">Users won't be blocked from accessing malicious domains</span></span>
    * <span data-ttu-id="32f7d-153">**Modo auditoría:** si un usuario visita una dirección IP malintencionada o un dominio, se registrará un evento en el registro de eventos de Windows.</span><span class="sxs-lookup"><span data-stu-id="32f7d-153">**Audit Mode** - If a user visits a malicious IP address or domain, an event will be recorded in the Windows event log.</span></span> <span data-ttu-id="32f7d-154">Sin embargo, no se bloqueará al usuario para que visite la dirección.</span><span class="sxs-lookup"><span data-stu-id="32f7d-154">However, the user won't be blocked from visiting the address.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="32f7d-155">Para habilitar completamente la protección de red, debe establecer la opción Directiva de grupo en **Habilitado** y también seleccionar **Bloquear** en el menú desplegable opciones.</span><span class="sxs-lookup"><span data-stu-id="32f7d-155">To fully enable network protection, you must set the Group Policy option to **Enabled** and also select **Block** in the options drop-down menu.</span></span>

<span data-ttu-id="32f7d-156">Confirme que la protección de red está habilitada en un equipo local mediante el editor del Registro:</span><span class="sxs-lookup"><span data-stu-id="32f7d-156">Confirm network protection is enabled on a local computer by using Registry editor:</span></span>

1. <span data-ttu-id="32f7d-157">Seleccione **Inicio** y escriba **regedit** para abrir **el Editor del Registro**.</span><span class="sxs-lookup"><span data-stu-id="32f7d-157">Select **Start** and type **regedit** to open **Registry Editor**.</span></span>

2. <span data-ttu-id="32f7d-158">Vaya a **HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender\Windows Defender Exploit Guard\Network Protection**</span><span class="sxs-lookup"><span data-stu-id="32f7d-158">Navigate to **HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender\Windows Defender Exploit Guard\Network Protection**</span></span>

3. <span data-ttu-id="32f7d-159">Seleccione **EnableNetworkProtection** y confirme el valor:</span><span class="sxs-lookup"><span data-stu-id="32f7d-159">Select **EnableNetworkProtection** and confirm the value:</span></span>
   * <span data-ttu-id="32f7d-160">0=Off</span><span class="sxs-lookup"><span data-stu-id="32f7d-160">0=Off</span></span>
   * <span data-ttu-id="32f7d-161">1=On</span><span class="sxs-lookup"><span data-stu-id="32f7d-161">1=On</span></span>
   * <span data-ttu-id="32f7d-162">2=Auditoría</span><span class="sxs-lookup"><span data-stu-id="32f7d-162">2=Audit</span></span>

## <a name="see-also"></a><span data-ttu-id="32f7d-163">Consulte también</span><span class="sxs-lookup"><span data-stu-id="32f7d-163">See also</span></span>

* [<span data-ttu-id="32f7d-164">Protección de red</span><span class="sxs-lookup"><span data-stu-id="32f7d-164">Network protection</span></span>](network-protection.md)
* [<span data-ttu-id="32f7d-165">Evaluar protección de red</span><span class="sxs-lookup"><span data-stu-id="32f7d-165">Evaluate network protection</span></span>](evaluate-network-protection.md)
* [<span data-ttu-id="32f7d-166">Solucionar problemas de protección de red</span><span class="sxs-lookup"><span data-stu-id="32f7d-166">Troubleshoot network protection</span></span>](troubleshoot-np.md)
