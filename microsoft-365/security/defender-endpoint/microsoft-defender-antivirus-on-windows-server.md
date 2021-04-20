---
title: Antivirus de Microsoft Defender en Windows Server
description: Aprende a habilitar y configurar Microsoft Defender Antivirus en Windows Server 2016 y Windows Server 2019.
keywords: windows defender, server, scep, system center endpoint protection, server 2016, current branch, server 2012
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.reviewer: pahuijbr, shwjha
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 50e6f9b16dbc633e75e86acdc54ac43580107ae3
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893382"
---
# <a name="microsoft-defender-antivirus-on-windows-server"></a><span data-ttu-id="2bbcd-104">Antivirus de Microsoft Defender en Windows Server</span><span class="sxs-lookup"><span data-stu-id="2bbcd-104">Microsoft Defender Antivirus on Windows Server</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2bbcd-105">**Se aplica a:**</span><span class="sxs-lookup"><span data-stu-id="2bbcd-105">**Applies to:**</span></span>

- [<span data-ttu-id="2bbcd-106">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="2bbcd-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="2bbcd-107">Antivirus de Microsoft Defender está disponible en las siguientes ediciones o versiones de Windows Server:</span><span class="sxs-lookup"><span data-stu-id="2bbcd-107">Microsoft Defender Antivirus is available on the following editions/versions of Windows Server:</span></span>
- <span data-ttu-id="2bbcd-108">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="2bbcd-108">Windows Server 2019</span></span>
- <span data-ttu-id="2bbcd-109">Windows Server, versión 1803 o posterior</span><span class="sxs-lookup"><span data-stu-id="2bbcd-109">Windows Server, version  1803 or later</span></span>
- <span data-ttu-id="2bbcd-110">Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="2bbcd-110">Windows Server 2016.</span></span> 

<span data-ttu-id="2bbcd-111">En algunos casos, Antivirus de Microsoft Defender se conoce como *Endpoint Protection*; sin embargo, el motor de protección es el mismo.</span><span class="sxs-lookup"><span data-stu-id="2bbcd-111">In some instances, Microsoft Defender Antivirus is referred to as *Endpoint Protection*; however, the protection engine is the same.</span></span> <span data-ttu-id="2bbcd-112">Aunque la funcionalidad, configuración y administración son en gran medida las mismas para Antivirus de Microsoft Defender en [Windows 10,](microsoft-defender-antivirus-in-windows-10.md)existen algunas diferencias clave en Windows Server:</span><span class="sxs-lookup"><span data-stu-id="2bbcd-112">Although the functionality, configuration, and management are largely the same for [Microsoft Defender Antivirus on Windows 10](microsoft-defender-antivirus-in-windows-10.md), there are a few key differences on Windows Server:</span></span>

- <span data-ttu-id="2bbcd-113">En Windows Server, [las exclusiones automáticas](configure-server-exclusions-microsoft-defender-antivirus.md) se aplican en función del rol de servidor definido.</span><span class="sxs-lookup"><span data-stu-id="2bbcd-113">In Windows Server, [automatic exclusions](configure-server-exclusions-microsoft-defender-antivirus.md) are applied based on your defined Server Role.</span></span>
- <span data-ttu-id="2bbcd-114">En Windows Server, Antivirus de Microsoft Defender no se deshabilita automáticamente si ejecutas otro producto antivirus.</span><span class="sxs-lookup"><span data-stu-id="2bbcd-114">In Windows Server, Microsoft Defender Antivirus does not automatically disable itself if you are running another antivirus product.</span></span>

## <a name="the-process-at-a-glance"></a><span data-ttu-id="2bbcd-115">El proceso de un vistazo</span><span class="sxs-lookup"><span data-stu-id="2bbcd-115">The process at a glance</span></span>

<span data-ttu-id="2bbcd-116">El proceso de configuración y ejecución de Antivirus de Microsoft Defender en una plataforma de servidor incluye varios pasos:</span><span class="sxs-lookup"><span data-stu-id="2bbcd-116">The process of setting up and running Microsoft Defender Antivirus on a server platform includes several steps:</span></span>

1. <span data-ttu-id="2bbcd-117">[Habilitar la interfaz](#enable-the-user-interface-on-windows-server).</span><span class="sxs-lookup"><span data-stu-id="2bbcd-117">[Enable the interface](#enable-the-user-interface-on-windows-server).</span></span>
2. <span data-ttu-id="2bbcd-118">[Instalar Antivirus de Microsoft Defender](#install-microsoft-defender-antivirus-on-windows-server).</span><span class="sxs-lookup"><span data-stu-id="2bbcd-118">[Install Microsoft Defender Antivirus](#install-microsoft-defender-antivirus-on-windows-server).</span></span>
3. <span data-ttu-id="2bbcd-119">[Compruebe que antivirus de Microsoft Defender se está ejecutando](#verify-microsoft-defender-antivirus-is-running).</span><span class="sxs-lookup"><span data-stu-id="2bbcd-119">[Verify Microsoft Defender Antivirus is running](#verify-microsoft-defender-antivirus-is-running).</span></span>
4. <span data-ttu-id="2bbcd-120">[Actualizar la inteligencia de seguridad antimalware](#update-antimalware-security-intelligence).</span><span class="sxs-lookup"><span data-stu-id="2bbcd-120">[Update your antimalware Security intelligence](#update-antimalware-security-intelligence).</span></span>
5. <span data-ttu-id="2bbcd-121">(Según sea necesario) [Enviar ejemplos](#submit-samples).</span><span class="sxs-lookup"><span data-stu-id="2bbcd-121">(As needed) [Submit samples](#submit-samples).</span></span>
6. <span data-ttu-id="2bbcd-122">(Según sea necesario) [Configurar exclusiones automáticas](#configure-automatic-exclusions).</span><span class="sxs-lookup"><span data-stu-id="2bbcd-122">(As needed) [Configure automatic exclusions](#configure-automatic-exclusions).</span></span>
7. <span data-ttu-id="2bbcd-123">(Solo si es necesario) [Establece Antivirus de Microsoft Defender en modo pasivo](#need-to-set-microsoft-defender-antivirus-to-passive-mode).</span><span class="sxs-lookup"><span data-stu-id="2bbcd-123">(Only if necessary) [Set Microsoft Defender Antivirus to passive mode](#need-to-set-microsoft-defender-antivirus-to-passive-mode).</span></span>

## <a name="enable-the-user-interface-on-windows-server"></a><span data-ttu-id="2bbcd-124">Habilitar la interfaz de usuario en Windows Server</span><span class="sxs-lookup"><span data-stu-id="2bbcd-124">Enable the user interface on Windows Server</span></span>

<span data-ttu-id="2bbcd-125">De forma predeterminada, Antivirus de Microsoft Defender está instalado y funciona en Windows Server.</span><span class="sxs-lookup"><span data-stu-id="2bbcd-125">By default, Microsoft Defender Antivirus is installed and functional on Windows Server.</span></span> <span data-ttu-id="2bbcd-126">La interfaz de usuario (GUI) está instalada de forma predeterminada en algunas SKU, pero no es necesaria porque puede usar PowerShell u otros métodos para administrar Antivirus de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="2bbcd-126">The user interface (GUI) is installed by default on some SKUs, but is not required because you can use PowerShell or other methods to manage Microsoft Defender Antivirus.</span></span> <span data-ttu-id="2bbcd-127">Si la GUI no está instalada en el servidor, puede agregarla mediante el Asistente para agregar **roles** y características o mediante cmdlets de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2bbcd-127">If the GUI is not installed on your server, you can add it by using the **Add Roles and Features** wizard, or by using PowerShell cmdlets.</span></span>

### <a name="turn-on-the-gui-using-the-add-roles-and-features-wizard"></a><span data-ttu-id="2bbcd-128">Activar la GUI mediante el Asistente para agregar roles y características</span><span class="sxs-lookup"><span data-stu-id="2bbcd-128">Turn on the GUI using the Add Roles and Features Wizard</span></span>

1. <span data-ttu-id="2bbcd-129">Consulte [Instalar roles, servicios de roles](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard)y características mediante el Asistente para agregar roles y características y usar el Asistente para agregar roles y **características.**</span><span class="sxs-lookup"><span data-stu-id="2bbcd-129">See [Install roles, role services, and features by using the add Roles and Features Wizard](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard), and use the **Add Roles and Features Wizard**.</span></span>

2. <span data-ttu-id="2bbcd-130">Cuando llegue al paso **Características** del asistente, en **Windows Defender,** seleccione la **guia para Windows Defender.**</span><span class="sxs-lookup"><span data-stu-id="2bbcd-130">When you get to the **Features** step of the wizard, under **Windows Defender Features**, select the **GUI for Windows Defender** option.</span></span>

   <span data-ttu-id="2bbcd-131">En Windows Server 2016, el Asistente para agregar **roles y** características tiene este aspecto:</span><span class="sxs-lookup"><span data-stu-id="2bbcd-131">In Windows Server 2016, the **Add Roles and Features Wizard** looks like this:</span></span>

   ![Agregar roles y asistente para características que muestran la gui Windows Defender opción](images/server-add-gui.png)

   <span data-ttu-id="2bbcd-133">En Windows Server 2019, el Asistente para agregar roles y **características** es similar.</span><span class="sxs-lookup"><span data-stu-id="2bbcd-133">In Windows Server 2019, the **Add Roles and Feature Wizard** is similar.</span></span>

### <a name="turn-on-the-gui-using-powershell"></a><span data-ttu-id="2bbcd-134">Activar la GUI con PowerShell</span><span class="sxs-lookup"><span data-stu-id="2bbcd-134">Turn on the GUI using PowerShell</span></span>

<span data-ttu-id="2bbcd-135">El siguiente cmdlet de PowerShell habilitará la interfaz:</span><span class="sxs-lookup"><span data-stu-id="2bbcd-135">The following PowerShell cmdlet will enable the interface:</span></span> 

```PowerShell
Install-WindowsFeature -Name Windows-Defender-GUI
```

## <a name="install-microsoft-defender-antivirus-on-windows-server"></a><span data-ttu-id="2bbcd-136">Instalar Antivirus de Microsoft Defender en Windows Server</span><span class="sxs-lookup"><span data-stu-id="2bbcd-136">Install Microsoft Defender Antivirus on Windows Server</span></span>

<span data-ttu-id="2bbcd-137">Puede usar el Asistente para agregar **roles y características** o PowerShell para instalar Antivirus de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="2bbcd-137">You can use either the **Add Roles and Features Wizard** or PowerShell to install Microsoft Defender Antivirus.</span></span>

### <a name="use-the-add-roles-and-features-wizard"></a><span data-ttu-id="2bbcd-138">Usar el Asistente para agregar roles y características</span><span class="sxs-lookup"><span data-stu-id="2bbcd-138">Use the Add Roles and Features Wizard</span></span>

1. <span data-ttu-id="2bbcd-139">Consulte este [artículo y](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard)use el Asistente para agregar roles **y características.**</span><span class="sxs-lookup"><span data-stu-id="2bbcd-139">Refer to [this article](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard), and use the **Add Roles and Features Wizard**.</span></span>

2. <span data-ttu-id="2bbcd-140">Cuando llegues al paso **Características** del asistente, selecciona la opción Antivirus de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="2bbcd-140">When you get to the **Features** step of the wizard, select the Microsoft Defender Antivirus option.</span></span> <span data-ttu-id="2bbcd-141">También seleccione la **GUI para Windows Defender** opción.</span><span class="sxs-lookup"><span data-stu-id="2bbcd-141">Also select the **GUI for Windows Defender** option.</span></span>

### <a name="use-powershell"></a><span data-ttu-id="2bbcd-142">Usar PowerShell</span><span class="sxs-lookup"><span data-stu-id="2bbcd-142">Use PowerShell</span></span>

<span data-ttu-id="2bbcd-143">Para usar PowerShell para instalar Microsoft Defender Antivirus, ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="2bbcd-143">To use PowerShell to install Microsoft Defender Antivirus, run the following cmdlet:</span></span>

```PowerShell
Install-WindowsFeature -Name Windows-Defender
```

<span data-ttu-id="2bbcd-144">Los mensajes de evento para el motor de antimalware incluido con Antivirus de Microsoft Defender se pueden encontrar en [Eventos AV de Microsoft Defender.](troubleshoot-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="2bbcd-144">Event messages for the antimalware engine included with Microsoft Defender Antivirus can be found in [Microsoft Defender AV Events](troubleshoot-microsoft-defender-antivirus.md).</span></span>


## <a name="verify-microsoft-defender-antivirus-is-running"></a><span data-ttu-id="2bbcd-145">Comprobar que antivirus de Microsoft Defender se está ejecutando</span><span class="sxs-lookup"><span data-stu-id="2bbcd-145">Verify Microsoft Defender Antivirus is running</span></span>

<span data-ttu-id="2bbcd-146">Para comprobar que Antivirus de Microsoft Defender se está ejecutando en el servidor, ejecute el siguiente cmdlet de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="2bbcd-146">To verify that Microsoft Defender Antivirus is running on your server, run the following PowerShell cmdlet:</span></span>

```PowerShell
Get-Service -Name windefend
```

<span data-ttu-id="2bbcd-147">Para comprobar que la protección del firewall está activada, ejecute el siguiente cmdlet de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="2bbcd-147">To verify that firewall protection is turned on, run the following PowerShell cmdlet:</span></span>

```PowerShell 
Get-Service -Name mpssvc
```

<span data-ttu-id="2bbcd-148">Como alternativa a PowerShell, puede usar el símbolo del sistema para comprobar que se está ejecutando Antivirus de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="2bbcd-148">As an alternative to PowerShell, you can use Command Prompt to verify that Microsoft Defender Antivirus is running.</span></span> <span data-ttu-id="2bbcd-149">Para ello, ejecute el siguiente comando desde un símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="2bbcd-149">To do that, run the following command from a command prompt:</span></span> 

```console
sc query Windefend
```

<span data-ttu-id="2bbcd-150">El `sc query` comando devuelve información sobre el servicio Antivirus de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="2bbcd-150">The `sc query` command returns information about the Microsoft Defender Antivirus service.</span></span> <span data-ttu-id="2bbcd-151">Cuando se ejecuta Antivirus de Microsoft Defender, `STATE` el valor muestra `RUNNING` .</span><span class="sxs-lookup"><span data-stu-id="2bbcd-151">When Microsoft Defender Antivirus is running, the `STATE` value displays `RUNNING`.</span></span>

## <a name="update-antimalware-security-intelligence"></a><span data-ttu-id="2bbcd-152">Actualizar inteligencia de seguridad antimalware</span><span class="sxs-lookup"><span data-stu-id="2bbcd-152">Update antimalware Security intelligence</span></span> 

<span data-ttu-id="2bbcd-153">Para obtener la inteligencia de seguridad antimalware actualizada, debe tener el servicio Windows Update en ejecución.</span><span class="sxs-lookup"><span data-stu-id="2bbcd-153">To get updated antimalware security intelligence, you must have the Windows Update service running.</span></span> <span data-ttu-id="2bbcd-154">Si usas un servicio de administración de actualizaciones, como Windows Server Update Services (WSUS), asegúrate de que las actualizaciones de inteligencia de Seguridad antivirus de Microsoft Defender estén aprobadas para los equipos que administras.</span><span class="sxs-lookup"><span data-stu-id="2bbcd-154">If you use an update management service, like Windows Server Update Services (WSUS), make sure that updates for Microsoft Defender Antivirus Security intelligence are approved for the computers you manage.</span></span>

<span data-ttu-id="2bbcd-155">De forma predeterminada, Windows Update no descarga e instala actualizaciones automáticamente en Windows Server 2019 o Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="2bbcd-155">By default, Windows Update does not download and install updates automatically on Windows Server 2019 or Windows Server 2016.</span></span> <span data-ttu-id="2bbcd-156">Puede cambiar esta configuración mediante uno de los métodos siguientes:</span><span class="sxs-lookup"><span data-stu-id="2bbcd-156">You can change this configuration by using one of the following methods:</span></span>


|<span data-ttu-id="2bbcd-157">Método</span><span class="sxs-lookup"><span data-stu-id="2bbcd-157">Method</span></span>  |<span data-ttu-id="2bbcd-158">Descripción</span><span class="sxs-lookup"><span data-stu-id="2bbcd-158">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="2bbcd-159">**Windows Update** en el Panel de control</span><span class="sxs-lookup"><span data-stu-id="2bbcd-159">**Windows Update** in Control Panel</span></span>     |<span data-ttu-id="2bbcd-160">- **Instalar actualizaciones automáticamente da como** resultado que todas las actualizaciones se instalen automáticamente, incluidas Windows Defender de inteligencia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="2bbcd-160">- **Install updates automatically** results in all updates being automatically installed, including Windows Defender Security intelligence updates.</span></span> <br/><span data-ttu-id="2bbcd-161">- **Descargue las actualizaciones, pero permítanme** elegir si instalarlas permite a Windows Defender descargar e instalar actualizaciones de inteligencia de seguridad automáticamente, pero otras actualizaciones no se instalan automáticamente.</span><span class="sxs-lookup"><span data-stu-id="2bbcd-161">- **Download updates but let me choose whether to install them** allows Windows Defender to download and install Security intelligence updates automatically, but other updates are not automatically installed.</span></span>       |
|<span data-ttu-id="2bbcd-162">**Directiva de grupo**</span><span class="sxs-lookup"><span data-stu-id="2bbcd-162">**Group Policy**</span></span>     | <span data-ttu-id="2bbcd-163">Puedes configurar y administrar Windows Update mediante la configuración disponible en la directiva de grupo, en la siguiente ruta de acceso: **Plantillas administrativas\Componentes de Windows\Windows Update\Configurar actualizaciones automáticas**</span><span class="sxs-lookup"><span data-stu-id="2bbcd-163">You can set up and manage Windows Update by using the settings available in Group Policy, in the following path: **Administrative Templates\Windows Components\Windows Update\Configure Automatic Updates**</span></span>         |
|<span data-ttu-id="2bbcd-164">La **clave del Registro AUOptions**</span><span class="sxs-lookup"><span data-stu-id="2bbcd-164">The **AUOptions** registry key</span></span>     |<span data-ttu-id="2bbcd-165">Los dos valores siguientes permiten a Windows Update descargar e instalar automáticamente las actualizaciones de inteligencia de seguridad:</span><span class="sxs-lookup"><span data-stu-id="2bbcd-165">The following two values allow Windows Update to automatically download and install Security intelligence updates:</span></span> <br/><span data-ttu-id="2bbcd-166">- **4**  -  **Instalar actualizaciones automáticamente**.</span><span class="sxs-lookup"><span data-stu-id="2bbcd-166">- **4** - **Install updates automatically**.</span></span> <span data-ttu-id="2bbcd-167">Este valor da como resultado que todas las actualizaciones se instalen automáticamente, incluidas Windows Defender de inteligencia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="2bbcd-167">This value results in all updates being automatically installed, including Windows Defender Security intelligence updates.</span></span> <br/><span data-ttu-id="2bbcd-168">- **3**  -  **Descargue las actualizaciones, pero permítanme elegir si desea instalarlas.**</span><span class="sxs-lookup"><span data-stu-id="2bbcd-168">- **3** - **Download updates but let me choose whether to install them**.</span></span>  <span data-ttu-id="2bbcd-169">Este valor permite Windows Defender descargar e instalar actualizaciones de inteligencia de seguridad automáticamente, pero otras actualizaciones no se instalan automáticamente.</span><span class="sxs-lookup"><span data-stu-id="2bbcd-169">This value allows Windows Defender to download and install Security intelligence updates automatically, but other updates are not automatically installed.</span></span>         |

<span data-ttu-id="2bbcd-170">Para garantizar que se mantiene la protección contra malware, se recomienda habilitar los siguientes servicios:</span><span class="sxs-lookup"><span data-stu-id="2bbcd-170">To ensure that protection from malware is maintained, we recommend that you enable the following services:</span></span>

- <span data-ttu-id="2bbcd-171">Servicio de informes de errores de Windows</span><span class="sxs-lookup"><span data-stu-id="2bbcd-171">Windows Error Reporting service</span></span>

- <span data-ttu-id="2bbcd-172">Servicio de Windows Update</span><span class="sxs-lookup"><span data-stu-id="2bbcd-172">Windows Update service</span></span>

<span data-ttu-id="2bbcd-173">En la tabla siguiente se enumeran los servicios de Antivirus de Microsoft Defender y los servicios dependientes.</span><span class="sxs-lookup"><span data-stu-id="2bbcd-173">The following table lists the services for Microsoft Defender Antivirus and the dependent services.</span></span>

|<span data-ttu-id="2bbcd-174">Nombre del servicio</span><span class="sxs-lookup"><span data-stu-id="2bbcd-174">Service Name</span></span>|<span data-ttu-id="2bbcd-175">Ubicación del archivo</span><span class="sxs-lookup"><span data-stu-id="2bbcd-175">File Location</span></span>|<span data-ttu-id="2bbcd-176">Descripción</span><span class="sxs-lookup"><span data-stu-id="2bbcd-176">Description</span></span>|
|--------|---------|--------|
|<span data-ttu-id="2bbcd-177">Windows Defender (WinDefend)</span><span class="sxs-lookup"><span data-stu-id="2bbcd-177">Windows Defender Service (WinDefend)</span></span>|`C:\Program Files\Windows Defender\MsMpEng.exe`|<span data-ttu-id="2bbcd-178">Este es el servicio antivirus principal de Microsoft Defender que debe ejecutarse en todo momento.</span><span class="sxs-lookup"><span data-stu-id="2bbcd-178">This is the main Microsoft Defender Antivirus service that needs to be running at all times.</span></span>|
|<span data-ttu-id="2bbcd-179">Servicio de informes de errores de Windows (Wersvc)</span><span class="sxs-lookup"><span data-stu-id="2bbcd-179">Windows Error Reporting Service (Wersvc)</span></span>|`C:\WINDOWS\System32\svchost.exe -k WerSvcGroup`|<span data-ttu-id="2bbcd-180">Este servicio devuelve informes de error a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2bbcd-180">This service sends error reports back to Microsoft.</span></span>|
|<span data-ttu-id="2bbcd-181">Windows Defender firewall (MpsSvc)</span><span class="sxs-lookup"><span data-stu-id="2bbcd-181">Windows Defender Firewall (MpsSvc)</span></span>|`C:\WINDOWS\system32\svchost.exe -k LocalServiceNoNetwork`|<span data-ttu-id="2bbcd-182">Se recomienda dejar el servicio Windows Defender firewall habilitado.</span><span class="sxs-lookup"><span data-stu-id="2bbcd-182">We recommend leaving the Windows Defender Firewall service enabled.</span></span>|
|<span data-ttu-id="2bbcd-183">Windows Update (Wuauserv)</span><span class="sxs-lookup"><span data-stu-id="2bbcd-183">Windows Update (Wuauserv)</span></span>|`C:\WINDOWS\system32\svchost.exe -k netsvcs`|<span data-ttu-id="2bbcd-184">Windows Update es necesario para obtener actualizaciones de inteligencia de seguridad y actualizaciones del motor de antimalware</span><span class="sxs-lookup"><span data-stu-id="2bbcd-184">Windows Update is needed to get Security intelligence updates and antimalware engine updates</span></span>|

## <a name="submit-samples"></a><span data-ttu-id="2bbcd-185">Enviar ejemplos</span><span class="sxs-lookup"><span data-stu-id="2bbcd-185">Submit samples</span></span>

<span data-ttu-id="2bbcd-186">El envío de ejemplo permite a Microsoft recopilar muestras de software potencialmente malintencionado.</span><span class="sxs-lookup"><span data-stu-id="2bbcd-186">Sample submission allows Microsoft to collect samples of potentially malicious software.</span></span> <span data-ttu-id="2bbcd-187">Para ayudar a proporcionar una protección continua y actualizada, los investigadores de Microsoft usan estas muestras para analizar actividades sospechosas y producir inteligencia de seguridad antimalware actualizada.</span><span class="sxs-lookup"><span data-stu-id="2bbcd-187">To help provide continued and up-to-date protection, Microsoft researchers use these samples to analyze suspicious activities and produce updated antimalware Security intelligence.</span></span> <span data-ttu-id="2bbcd-188">Recopilamos archivos ejecutables del programa, como archivos .exe y archivos .dll.</span><span class="sxs-lookup"><span data-stu-id="2bbcd-188">We collect program executable files, such as .exe files and .dll files.</span></span> <span data-ttu-id="2bbcd-189">No recopilamos archivos que contienen datos personales, como documentos de Microsoft Word y archivos PDF.</span><span class="sxs-lookup"><span data-stu-id="2bbcd-189">We do not collect files that contain personal data, like Microsoft Word documents and PDF files.</span></span>

### <a name="submit-a-file"></a><span data-ttu-id="2bbcd-190">Enviar un archivo</span><span class="sxs-lookup"><span data-stu-id="2bbcd-190">Submit a file</span></span>

1. <span data-ttu-id="2bbcd-191">Revise la [guía de envío](/windows/security/threat-protection/intelligence/submission-guide).</span><span class="sxs-lookup"><span data-stu-id="2bbcd-191">Review the [submission guide](/windows/security/threat-protection/intelligence/submission-guide).</span></span>

2. <span data-ttu-id="2bbcd-192">Visite el portal [de envío de ejemplo](https://www.microsoft.com/wdsi/filesubmission)y envíe el archivo.</span><span class="sxs-lookup"><span data-stu-id="2bbcd-192">Visit the [sample submission portal](https://www.microsoft.com/wdsi/filesubmission), and submit your file.</span></span>


### <a name="enable-automatic-sample-submission"></a><span data-ttu-id="2bbcd-193">Habilitar el envío automático de muestra</span><span class="sxs-lookup"><span data-stu-id="2bbcd-193">Enable automatic sample submission</span></span>

<span data-ttu-id="2bbcd-194">Para habilitar el envío automático de ejemplo, inicie una consola Windows PowerShell como administrador y establezca los datos de valor **SubmitSamplesConsent** de acuerdo con una de las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="2bbcd-194">To enable automatic sample submission, start a Windows PowerShell console as an administrator, and set the **SubmitSamplesConsent** value data according to one of the following settings:</span></span>

|<span data-ttu-id="2bbcd-195">Configuración</span><span class="sxs-lookup"><span data-stu-id="2bbcd-195">Setting</span></span>  |<span data-ttu-id="2bbcd-196">Descripción</span><span class="sxs-lookup"><span data-stu-id="2bbcd-196">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="2bbcd-197">**0**  -  **Preguntar siempre**</span><span class="sxs-lookup"><span data-stu-id="2bbcd-197">**0** - **Always prompt**</span></span>     |<span data-ttu-id="2bbcd-198">El servicio Antivirus de Microsoft Defender le pide que confirme el envío de todos los archivos necesarios.</span><span class="sxs-lookup"><span data-stu-id="2bbcd-198">The Microsoft Defender Antivirus service prompts you to confirm submission of all required files.</span></span> <span data-ttu-id="2bbcd-199">Esta es la configuración predeterminada para Antivirus de Microsoft Defender, pero no se recomienda para instalaciones en Windows Server 2016 o 2019 sin una GUI.</span><span class="sxs-lookup"><span data-stu-id="2bbcd-199">This is the default setting for Microsoft Defender Antivirus, but is not recommended for installations on Windows Server 2016 or 2019 without a GUI.</span></span>         |
|<span data-ttu-id="2bbcd-200">**1**   -  **Enviar muestras seguras automáticamente**</span><span class="sxs-lookup"><span data-stu-id="2bbcd-200">**1**  - **Send safe samples automatically**</span></span>     |<span data-ttu-id="2bbcd-201">El servicio Antivirus de Microsoft Defender envía todos los archivos marcados como "seguros" y solicita el resto de los archivos.</span><span class="sxs-lookup"><span data-stu-id="2bbcd-201">The Microsoft Defender Antivirus service sends all files marked as "safe" and prompts for the remainder of the files.</span></span>         |
|<span data-ttu-id="2bbcd-202">**2**  -  **Nunca enviar**</span><span class="sxs-lookup"><span data-stu-id="2bbcd-202">**2** - **Never send**</span></span>      |<span data-ttu-id="2bbcd-203">El servicio antivirus de Microsoft Defender no solicita y no envía ningún archivo.</span><span class="sxs-lookup"><span data-stu-id="2bbcd-203">The Microsoft Defender Antivirus service does not prompt and does not send any files.</span></span>         |
|<span data-ttu-id="2bbcd-204">**3**  -  **Enviar todas las muestras automáticamente**</span><span class="sxs-lookup"><span data-stu-id="2bbcd-204">**3** - **Send all samples automatically**</span></span>     |<span data-ttu-id="2bbcd-205">El servicio Antivirus de Microsoft Defender envía todos los archivos sin necesidad de confirmación.</span><span class="sxs-lookup"><span data-stu-id="2bbcd-205">The Microsoft Defender Antivirus service sends all files without a prompt for confirmation.</span></span>         |

## <a name="configure-automatic-exclusions"></a><span data-ttu-id="2bbcd-206">Configurar exclusiones automáticas</span><span class="sxs-lookup"><span data-stu-id="2bbcd-206">Configure automatic exclusions</span></span>

<span data-ttu-id="2bbcd-207">Para garantizar la seguridad y el rendimiento, se agregan automáticamente determinadas exclusiones en función de los roles y características que instales al usar Antivirus de Microsoft Defender en Windows Server 2016 o 2019.</span><span class="sxs-lookup"><span data-stu-id="2bbcd-207">To help ensure security and performance, certain exclusions are automatically added based on the roles and features you install when using Microsoft Defender Antivirus on Windows Server 2016 or 2019.</span></span>

<span data-ttu-id="2bbcd-208">Consulta [Configurar exclusiones en Antivirus de Microsoft Defender en Windows Server](configure-server-exclusions-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="2bbcd-208">See [Configure exclusions in Microsoft Defender Antivirus on Windows Server](configure-server-exclusions-microsoft-defender-antivirus.md).</span></span> 

## <a name="need-to-set-microsoft-defender-antivirus-to-passive-mode"></a><span data-ttu-id="2bbcd-209">¿Necesita establecer Antivirus de Microsoft Defender en modo pasivo?</span><span class="sxs-lookup"><span data-stu-id="2bbcd-209">Need to set Microsoft Defender Antivirus to passive mode?</span></span>

<span data-ttu-id="2bbcd-210">Si usa un producto antivirus que no sea de Microsoft como solución antivirus principal, establezca Antivirus de Microsoft Defender en modo pasivo.</span><span class="sxs-lookup"><span data-stu-id="2bbcd-210">If you are using a non-Microsoft antivirus product as your primary antivirus solution, set Microsoft Defender Antivirus to passive mode.</span></span>  

### <a name="set-microsoft-defender-antivirus-to-passive-mode-using-a-registry-key"></a><span data-ttu-id="2bbcd-211">Establecer Antivirus de Microsoft Defender en modo pasivo con una clave del Registro</span><span class="sxs-lookup"><span data-stu-id="2bbcd-211">Set Microsoft Defender Antivirus to passive mode using a registry key</span></span>

<span data-ttu-id="2bbcd-212">Si usa Windows Server, versión 1803 o Windows Server 2019, puede establecer Antivirus de Microsoft Defender en modo pasivo estableciendo la siguiente clave del Registro:</span><span class="sxs-lookup"><span data-stu-id="2bbcd-212">If you are using Windows Server, version 1803 or Windows Server 2019, you can set Microsoft Defender Antivirus to passive mode by setting the following registry key:</span></span>
- <span data-ttu-id="2bbcd-213">Ruta de acceso: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`</span><span class="sxs-lookup"><span data-stu-id="2bbcd-213">Path: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`</span></span>
- <span data-ttu-id="2bbcd-214">Nombre: `ForceDefenderPassiveMode`</span><span class="sxs-lookup"><span data-stu-id="2bbcd-214">Name: `ForceDefenderPassiveMode`</span></span>
- <span data-ttu-id="2bbcd-215">Tipo: `REG_DWORD`</span><span class="sxs-lookup"><span data-stu-id="2bbcd-215">Type: `REG_DWORD`</span></span>
- <span data-ttu-id="2bbcd-216">Valor: `1`</span><span class="sxs-lookup"><span data-stu-id="2bbcd-216">Value: `1`</span></span>

### <a name="disable-microsoft-defender-antivirus-using-the-remove-roles-and-features-wizard"></a><span data-ttu-id="2bbcd-217">Deshabilitar Antivirus de Microsoft Defender con el Asistente para quitar roles y características</span><span class="sxs-lookup"><span data-stu-id="2bbcd-217">Disable Microsoft Defender Antivirus using the Remove Roles and Features wizard</span></span>

1. <span data-ttu-id="2bbcd-218">Vea [Instalar o desinstalar roles, servicios de roles o características](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#remove-roles-role-services-and-features-by-using-the-remove-roles-and-features-wizard)y use el Asistente para quitar roles y **características.**</span><span class="sxs-lookup"><span data-stu-id="2bbcd-218">See [Install or Uninstall Roles, Role Services, or Features](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#remove-roles-role-services-and-features-by-using-the-remove-roles-and-features-wizard), and use the **Remove Roles and Features Wizard**.</span></span> 

2. <span data-ttu-id="2bbcd-219">Cuando llegue al paso **Características** del asistente, desactive la **opción Windows Defender Características.**</span><span class="sxs-lookup"><span data-stu-id="2bbcd-219">When you get to the **Features** step of the wizard, clear the **Windows Defender Features** option.</span></span> 

    <span data-ttu-id="2bbcd-220">Si borras **Windows Defender** en la sección Características de **Windows Defender,** se te pedirá que quites la gui de opción de interfaz para **Windows Defender**.</span><span class="sxs-lookup"><span data-stu-id="2bbcd-220">If you clear **Windows Defender** by itself under the **Windows Defender Features** section, you will be prompted to remove the interface option **GUI for Windows Defender**.</span></span> 
    
    <span data-ttu-id="2bbcd-221">Antivirus de Microsoft Defender seguirá ejecundo normalmente sin la interfaz de usuario, pero la interfaz de usuario no se puede habilitar si deshabilita la característica **principal Windows Defender** usuario.</span><span class="sxs-lookup"><span data-stu-id="2bbcd-221">Microsoft Defender Antivirus will still run normally without the user interface, but the user interface cannot be enabled if you disable the core **Windows Defender** feature.</span></span>

### <a name="turn-off-the-microsoft-defender-antivirus-user-interface-using-powershell"></a><span data-ttu-id="2bbcd-222">Desactivar la interfaz de usuario de Antivirus de Microsoft Defender con PowerShell</span><span class="sxs-lookup"><span data-stu-id="2bbcd-222">Turn off the Microsoft Defender Antivirus user interface using PowerShell</span></span>

<span data-ttu-id="2bbcd-223">Para desactivar la GUI de Antivirus de Microsoft Defender, use el siguiente cmdlet de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="2bbcd-223">To turn off the Microsoft Defender Antivirus GUI, use the following PowerShell cmdlet:</span></span>

```PowerShell
Uninstall-WindowsFeature -Name Windows-Defender-GUI
```

### <a name="are-you-using-windows-server-2016"></a><span data-ttu-id="2bbcd-224">¿Estás usando Windows Server 2016?</span><span class="sxs-lookup"><span data-stu-id="2bbcd-224">Are you using Windows Server 2016?</span></span>

<span data-ttu-id="2bbcd-225">Si usas Windows Server 2016 y un producto antivirus o antimalware de terceros que Microsoft no ofrece ni desarrolla, tendrás que deshabilitar o desinstalar Antivirus de Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="2bbcd-225">If you are using Windows Server 2016 and a third-party antimalware/antivirus product that is not offered or developed by Microsoft, you'll need to disable/uninstall Microsoft Defender Antivirus.</span></span> 

> [!NOTE]
> <span data-ttu-id="2bbcd-226">No puedes desinstalar la aplicación seguridad de Windows, pero puedes deshabilitar la interfaz con estas instrucciones.</span><span class="sxs-lookup"><span data-stu-id="2bbcd-226">You can't uninstall the Windows Security app, but you can disable the interface with these instructions.</span></span>

<span data-ttu-id="2bbcd-227">El siguiente cmdlet de PowerShell desinstala Antivirus de Microsoft Defender en Windows Server 2016:</span><span class="sxs-lookup"><span data-stu-id="2bbcd-227">The following PowerShell cmdlet uninstalls Microsoft Defender Antivirus on Windows Server 2016:</span></span>

```PowerShell
Uninstall-WindowsFeature -Name Windows-Defender
```

## <a name="see-also"></a><span data-ttu-id="2bbcd-228">Vea también</span><span class="sxs-lookup"><span data-stu-id="2bbcd-228">See also</span></span>

- [<span data-ttu-id="2bbcd-229">Antivirus de Microsoft Defender en Windows 10</span><span class="sxs-lookup"><span data-stu-id="2bbcd-229">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="2bbcd-230">Compatibilidad con Antivirus de Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="2bbcd-230">Microsoft Defender Antivirus compatibility</span></span>](microsoft-defender-antivirus-compatibility.md)
