---
title: Introducción a la extensión de cumplimiento de Microsoft
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: Prepárese para implementar la extensión de cumplimiento de Microsoft.
ms.openlocfilehash: 084d8fea1bffb012b4a4685dd28ec93df8e29b19
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2021
ms.locfileid: "52730515"
---
# <a name="get-started-with-microsoft-compliance-extension"></a><span data-ttu-id="28653-103">Introducción a la extensión de cumplimiento de Microsoft</span><span class="sxs-lookup"><span data-stu-id="28653-103">Get started with Microsoft Compliance Extension</span></span>

<span data-ttu-id="28653-104">Use estos procedimientos para implementar la extensión de cumplimiento de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="28653-104">Use these procedures to roll out the Microsoft Compliance Extension.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="28653-105">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="28653-105">Before you begin</span></span>

<span data-ttu-id="28653-106">Para usar la extensión de cumplimiento de Microsoft, el dispositivo debe haber sido incorporado a la DLP del punto de conexión</span><span class="sxs-lookup"><span data-stu-id="28653-106">To use Microsoft Compliance Extension, the device must be onboarded into endpoint DLP.</span></span> <span data-ttu-id="28653-107">Consulte estos artículos si la DLP o la DLP del punto de conexión son algo nuevo para usted.</span><span class="sxs-lookup"><span data-stu-id="28653-107">Review these articles if you are new to DLP or endpoint DLP</span></span>

- [<span data-ttu-id="28653-108">Información sobre la extensión de cumplimiento de Microsoft</span><span class="sxs-lookup"><span data-stu-id="28653-108">Learn about Microsoft Compliance Extension</span></span>](dlp-chrome-learn-about.md)
- [<span data-ttu-id="28653-109">Obtenga más información acerca de la prevención contra la pérdida de datos</span><span class="sxs-lookup"><span data-stu-id="28653-109">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="28653-110">Crear, probar y optimizar una directiva DLP</span><span class="sxs-lookup"><span data-stu-id="28653-110">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="28653-111">Crear una directiva DLP desde una plantilla</span><span class="sxs-lookup"><span data-stu-id="28653-111">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)
- [<span data-ttu-id="28653-112">Obtenga más información sobre la prevención de pérdida de datos en punto de conexión</span><span class="sxs-lookup"><span data-stu-id="28653-112">Learn about endpoint data loss prevention</span></span>](endpoint-dlp-learn-about.md)
- [<span data-ttu-id="28653-113">Introducción a la prevención de pérdida de datos en punto de conexión</span><span class="sxs-lookup"><span data-stu-id="28653-113">Get started with Endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
- [<span data-ttu-id="28653-114">Herramientas y métodos de incorporación para dispositivos Windows 10</span><span class="sxs-lookup"><span data-stu-id="28653-114">Onboarding tools and methods for Windows 10 devices</span></span>](dlp-configure-endpoints.md)
- [<span data-ttu-id="28653-115">Configurar la conexión a Internet y el proxy del dispositivo para la DLP de punto de conexión</span><span class="sxs-lookup"><span data-stu-id="28653-115">Configure device proxy and internet connection settings for Endpoint DLP</span></span>](endpoint-dlp-configure-proxy.md)
- [<span data-ttu-id="28653-116">Uso de la prevención de pérdida de datos en punto de conexión</span><span class="sxs-lookup"><span data-stu-id="28653-116">Using Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)

### <a name="skusubscriptions-licensing"></a><span data-ttu-id="28653-117">Licencias de SKU y suscripciones</span><span class="sxs-lookup"><span data-stu-id="28653-117">SKU/subscriptions licensing</span></span>

<span data-ttu-id="28653-118">Antes de empezar, debe confirmar la [Suscripción a Microsoft 365](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) y cualquier complemento.</span><span class="sxs-lookup"><span data-stu-id="28653-118">Before you get started, you should confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) and any add-ons.</span></span> <span data-ttu-id="28653-119">Para acceder y usar la funcionalidad Endpoint DLP, debe tener una de estas suscripciones o complementos.</span><span class="sxs-lookup"><span data-stu-id="28653-119">To access and use Endpoint DLP functionality, you must have one of these subscriptions or add-ons.</span></span>

- <span data-ttu-id="28653-120">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="28653-120">Microsoft 365 E5</span></span>
- <span data-ttu-id="28653-121">Microsoft 365 A5 (EDU)</span><span class="sxs-lookup"><span data-stu-id="28653-121">Microsoft 365 A5 (EDU)</span></span>
- <span data-ttu-id="28653-122">Cumplimiento de Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="28653-122">Microsoft 365 E5 compliance</span></span>
- <span data-ttu-id="28653-123">Cumplimiento de Microsoft 365 A5</span><span class="sxs-lookup"><span data-stu-id="28653-123">Microsoft 365 A5 compliance</span></span>
- <span data-ttu-id="28653-124">Gobierno y protección de información de Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="28653-124">Microsoft 365 E5 information protection and governance</span></span>
- <span data-ttu-id="28653-125">Gobierno y protección de información de Microsoft 365 A5</span><span class="sxs-lookup"><span data-stu-id="28653-125">Microsoft 365 A5 information protection and governance</span></span>

<span data-ttu-id="28653-126">Para una guía detallada sobre las licencias, vea: [Guía de licencias de Microsoft 365 para la seguridad y el cumplimiento](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection).</span><span class="sxs-lookup"><span data-stu-id="28653-126">For detailed licensing guidance, see [Microsoft 365 licensing guidance for security & compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection).</span></span>

- <span data-ttu-id="28653-127">Su organización debe tener la licencia de DLP para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="28653-127">Your org must be licensed for Endpoint DLP</span></span>
- <span data-ttu-id="28653-128">Sus dispositivos deben ejecutar Windows 10 x64 compilación 1809 o posterior.</span><span class="sxs-lookup"><span data-stu-id="28653-128">Your devices must be running Windows 10 x64 build 1809 or later.</span></span>
- <span data-ttu-id="28653-129">El dispositivo debe tener la versión del cliente antimalware 4.18.2101.9 o posterior.</span><span class="sxs-lookup"><span data-stu-id="28653-129">The device must have Antimalware Client Version is 4.18.2101.9 or later.</span></span> <span data-ttu-id="28653-130">Para comprobar la versión actual, abra la aplicación de **Seguridad de Windows**, seleccione el icono **Configuración** y, a continuación, **Acerca de**.</span><span class="sxs-lookup"><span data-stu-id="28653-130">Check your current version by opening **Windows Security** app, select the **Settings** icon, and then select **About**.</span></span>


### <a name="permissions"></a><span data-ttu-id="28653-131">Permisos</span><span class="sxs-lookup"><span data-stu-id="28653-131">Permissions</span></span>

<span data-ttu-id="28653-132">Los datos de Endpoint DLP se pueden ver en el [Explorador de actividad](data-classification-activity-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="28653-132">Data from Endpoint DLP can be viewed in [Activity explorer](data-classification-activity-explorer.md).</span></span> <span data-ttu-id="28653-133">Hay siete roles que conceden permisos al explorador de actividad; la cuenta que use para acceder a los datos debe pertenecer a uno de ellos.</span><span class="sxs-lookup"><span data-stu-id="28653-133">There are seven roles that grant permission to activity explorer, the account you use for accessing the data must be a member of any one of them.</span></span>

- <span data-ttu-id="28653-134">Administrador global</span><span class="sxs-lookup"><span data-stu-id="28653-134">Global admin</span></span>
- <span data-ttu-id="28653-135">Administrador de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="28653-135">Compliance admin</span></span>
- <span data-ttu-id="28653-136">Administrador de seguridad</span><span class="sxs-lookup"><span data-stu-id="28653-136">Security admin</span></span>
- <span data-ttu-id="28653-137">Administrador de datos de cumplimiento</span><span class="sxs-lookup"><span data-stu-id="28653-137">Compliance data admin</span></span>
- <span data-ttu-id="28653-138">Lector global</span><span class="sxs-lookup"><span data-stu-id="28653-138">Global reader</span></span>
- <span data-ttu-id="28653-139">Lector de seguridad</span><span class="sxs-lookup"><span data-stu-id="28653-139">Security reader</span></span>
- <span data-ttu-id="28653-140">Lector de informes</span><span class="sxs-lookup"><span data-stu-id="28653-140">Reports reader</span></span>

### <a name="overall-installation-workflow"></a><span data-ttu-id="28653-141">Flujo general de trabajo de la instalación</span><span class="sxs-lookup"><span data-stu-id="28653-141">Overall installation workflow</span></span>

<span data-ttu-id="28653-p105">La implementación de la extensión de cumplimiento de Microsoft es un proceso de varias fases. Puede elegir entre instalar en las máquinas de una en una o usar Microsoft Endpoint Manager o la directiva de grupo para la implementación a nivel de la organización.</span><span class="sxs-lookup"><span data-stu-id="28653-p105">Deploying Microsoft Compliance Extension is a multi-phase process. You can choose to install on one machine at a time, or use Microsoft Endpoint Manager or Group Policy for organization-wide deployments.</span></span>

1. <span data-ttu-id="28653-144">[Preparar sus dispositivos](#prepare-your-devices).</span><span class="sxs-lookup"><span data-stu-id="28653-144">[Prepare your devices](#prepare-your-devices).</span></span>
2. [<span data-ttu-id="28653-145">Autohospedaje de máquina única de instalación básica</span><span class="sxs-lookup"><span data-stu-id="28653-145">Basic Setup Single Machine Selfhost</span></span>](#basic-setup-single-machine-selfhost)
3. [<span data-ttu-id="28653-146">Implementar con Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="28653-146">Deploy using Microsoft Endpoint Manager</span></span>](#deploy-using-microsoft-endpoint-manager)
4. [<span data-ttu-id="28653-147">Implementar mediante la directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="28653-147">Deploy using Group Policy</span></span>](#deploy-using-group-policy)
5. [<span data-ttu-id="28653-148">Probar la extensión</span><span class="sxs-lookup"><span data-stu-id="28653-148">Test the Extension</span></span>](#test-the-extension)
6. [<span data-ttu-id="28653-149">Usar el panel de administración de alertas para ver las alertas de DLP de Chrome</span><span class="sxs-lookup"><span data-stu-id="28653-149">Use the Alerts Management Dashboard to viewing Chrome DLP alerts</span></span>](#use-the-alerts-management-dashboard-to-viewing-chrome-dlp-alerts)
7. [<span data-ttu-id="28653-150">Visualizar datos de DLP de Chrome en el explorador de actividad</span><span class="sxs-lookup"><span data-stu-id="28653-150">Viewing Chrome DLP data in activity explorer</span></span>](#viewing-chrome-dlp-data-in-activity-explorer) 

### <a name="prepare-infrastructure"></a><span data-ttu-id="28653-151">Preparar la infraestructura</span><span class="sxs-lookup"><span data-stu-id="28653-151">Prepare infrastructure</span></span>

<span data-ttu-id="28653-152">Si va a implementar la extensión de cumplimiento de Microsoft en todos sus dispositivos Windows 10 supervisados, debería quitar Google Chrome de las listas de aplicaciones y de exploradores no permitidos.</span><span class="sxs-lookup"><span data-stu-id="28653-152">If you are rolling out the Microsoft Compliance Extension to all your monitored Windows 10 devices, you should remove Google Chrome from the unallowed app and unallowed browser lists.</span></span> <span data-ttu-id="28653-153">Para más información, consulte [Exploradores no permitidos](endpoint-dlp-using.md#unallowed-browsers).</span><span class="sxs-lookup"><span data-stu-id="28653-153">For more information, see [Unallowed browsers](endpoint-dlp-using.md#unallowed-browsers).</span></span> <span data-ttu-id="28653-154">Si solo va a realizar la implementación en unos pocos dispositivos, puede dejar Chrome en las listas de aplicaciones o exploradores no permitidos.</span><span class="sxs-lookup"><span data-stu-id="28653-154">If you are only rolling it out to a few devices, you can leave Chrome on the unallowed browser or unallowed app lists.</span></span> <span data-ttu-id="28653-155">La extensión de cumplimiento de Microsoft ignorará las restricciones de ambas listas para aquellos equipos en los que se haya instalado.</span><span class="sxs-lookup"><span data-stu-id="28653-155">The Microsoft Compliance Extension will bypass the restrictions of both lists for those computers where it is installed.</span></span>  

### <a name="prepare-your-devices"></a><span data-ttu-id="28653-156">Preparar sus dispositivos</span><span class="sxs-lookup"><span data-stu-id="28653-156">Prepare your devices</span></span>

1. <span data-ttu-id="28653-157">Use los procedimientos de estos temas para incorporar sus dispositivos:</span><span class="sxs-lookup"><span data-stu-id="28653-157">Use the procedures in these topics to onboard your devices:</span></span>
    1. [<span data-ttu-id="28653-158">Introducción a la prevención de pérdida de datos en punto de conexión</span><span class="sxs-lookup"><span data-stu-id="28653-158">Get started with Endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
    1. [<span data-ttu-id="28653-159">Herramientas y métodos de incorporación para dispositivos Windows 10</span><span class="sxs-lookup"><span data-stu-id="28653-159">Onboarding tools and methods for Windows 10 devices</span></span>](dlp-configure-endpoints.md)
    1. [<span data-ttu-id="28653-160">Configurar la conexión a Internet y el proxy del dispositivo para la DLP de punto de conexión</span><span class="sxs-lookup"><span data-stu-id="28653-160">Configure device proxy and internet connection settings for Endpoint DLP</span></span>](endpoint-dlp-configure-proxy.md)

### <a name="basic-setup-single-machine-selfhost"></a><span data-ttu-id="28653-161">Autohospedaje de máquina única de instalación básica</span><span class="sxs-lookup"><span data-stu-id="28653-161">Basic Setup Single Machine Selfhost</span></span>

<span data-ttu-id="28653-162">Esta método es el recomendado.</span><span class="sxs-lookup"><span data-stu-id="28653-162">This is the recommended method.</span></span> 

1. <span data-ttu-id="28653-163">Inicie sesión en el equipo de Windows 10 en el que quiera instalar la extensión de cumplimiento de Microsoft y ejecute este script de PowerShell como administrador.</span><span class="sxs-lookup"><span data-stu-id="28653-163">Sign in to the Windows 10 computer on which you want to install the Microsoft Compliance Extension on, and run this PowerShell script as an administrator.</span></span> 

   ```powershell
   Get-Item -path "HKLM:\SOFTWARE\Microsoft\Windows Defender\Miscellaneous Configuration" | New-ItemProperty -Name DlpDisableBrowserCache -Value 0 -Force
   ``` 

2.  <span data-ttu-id="28653-164">Vaya a [Extensión de cumplimiento de Microsoft - Almacén web de Chrome (google.com)](https://chrome.google.com/webstore/detail/microsoft-compliance-exte/echcggldkblhodogklpincgchnpgcdco).</span><span class="sxs-lookup"><span data-stu-id="28653-164">Navigate to [Microsoft Compliance Extension - Chrome Web Store (google.com)](https://chrome.google.com/webstore/detail/microsoft-compliance-exte/echcggldkblhodogklpincgchnpgcdco).</span></span>

3.  <span data-ttu-id="28653-165">Instale la extensión mediante las instrucciones de la página del almacén web de Chrome.</span><span class="sxs-lookup"><span data-stu-id="28653-165">Install the extension using the instructions on the Chrome Web Store page.</span></span>

### <a name="deploy-using-microsoft-endpoint-manager"></a><span data-ttu-id="28653-166">Implementación con Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="28653-166">Deploy using Microsoft Endpoint Manager</span></span>

<span data-ttu-id="28653-167">Use este método de configuración para implementaciones a nivel de la organización.</span><span class="sxs-lookup"><span data-stu-id="28653-167">Use this setup method for organization-wide deployments.</span></span>


##### <a name="enabling-required-registry-key-via-microsoft-endpoint-manager"></a><span data-ttu-id="28653-168">Habilitar la clave del registro requerida mediante Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="28653-168">Enabling Required Registry Key via Microsoft Endpoint Manager</span></span>

1.  <span data-ttu-id="28653-169">Cree un script de PowerShell con el contenido siguiente:</span><span class="sxs-lookup"><span data-stu-id="28653-169">Create a PowerShell script with the following contents:</span></span>

    ```powershell
    Get-Item -path "HKLM:\SOFTWARE\Microsoft\Windows Defender\Miscellaneous Configuration" | New-ItemProperty -Name DlpDisableBrowserCache -Value 0 -Force
    ```

2.  <span data-ttu-id="28653-170">Inicie sesión en el [Centro de administración de Microsoft Endpoint Manager](https://endpoint.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="28653-170">Sign in to the [Microsoft Endpoint Manager Admin Center](https://endpoint.microsoft.com).</span></span>

3.  <span data-ttu-id="28653-171">Vaya a **Dispositivos** > **Scripts** y seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="28653-171">Navigate to **Devices** > **Scripts** and select **Add**.</span></span>

4.  <span data-ttu-id="28653-172">Cuando se le solicite, vaya a la ubicación del script creado.</span><span class="sxs-lookup"><span data-stu-id="28653-172">Browse to the location of the script created when prompted.</span></span>

5.  <span data-ttu-id="28653-173">Seleccione la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="28653-173">Select the following settings:</span></span>
    1. <span data-ttu-id="28653-174">Ejecutar este script con las credenciales de inicio de sesión: SÍ</span><span class="sxs-lookup"><span data-stu-id="28653-174">Run this script using the logged-on credentials: YES</span></span>
    1. <span data-ttu-id="28653-175">Aplicar comprobación de firma de script: NO</span><span class="sxs-lookup"><span data-stu-id="28653-175">Enforce script signature check: NO</span></span>
    1. <span data-ttu-id="28653-176">Ejecutar script en host de PowerShell de 64 bits: SÍ</span><span class="sxs-lookup"><span data-stu-id="28653-176">Run script in 64-bit PowerShell Host: YES</span></span>

6.  <span data-ttu-id="28653-177">Seleccione los grupos adecuados de dispositivos y aplique la directiva.</span><span class="sxs-lookup"><span data-stu-id="28653-177">Select the proper device groups and apply the policy.</span></span>

#### <a name="microsoft-endpoint-manager-force-install-steps"></a><span data-ttu-id="28653-178">Pasos para la instalación forzada de Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="28653-178">Microsoft Endpoint Manager Force Install Steps</span></span>

<span data-ttu-id="28653-179">Antes de agregar la extensión de cumplimiento de Microsoft a la lista de extensiones instaladas de manera forzosa, es importante incorporar ADMX de Chrome.</span><span class="sxs-lookup"><span data-stu-id="28653-179">Before adding the Microsoft Compliance Extension to the list of force-installed extensions, it is important to ingest the Chrome ADMX.</span></span> <span data-ttu-id="28653-180">Los pasos de este proceso en Microsoft Endpoint Manager son documentados por Google: [Administrar el explorador Chrome con Microsoft Intune - Ayuda de Google Chrome Enterprise](https://support.google.com/chrome/a/answer/9102677?hl=en#zippy=%2Cstep-ingest-the-chrome-admx-file-into-intune).</span><span class="sxs-lookup"><span data-stu-id="28653-180">Steps for this process in Microsoft Endpoint Manager are documented by Google: [Manage Chrome Browser with Microsoft Intune - Google Chrome Enterprise Help](https://support.google.com/chrome/a/answer/9102677?hl=en#zippy=%2Cstep-ingest-the-chrome-admx-file-into-intune).</span></span>

 <span data-ttu-id="28653-181">Tras incorporar ADMX, se pueden dar los siguientes pasos para crear un perfil de configuración para esta extensión.</span><span class="sxs-lookup"><span data-stu-id="28653-181">After ingesting the ADMX, the steps below can be followed to create a configuration profile for this extension.</span></span>

1.  <span data-ttu-id="28653-182">Inicie sesión en el Centro de administración de Microsoft Endpoint Manager (https://endpoint.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="28653-182">Sign in to the Microsoft Endpoint Manager Admin Center (https://endpoint.microsoft.com).</span></span>

2.  <span data-ttu-id="28653-183">Vaya a Perfiles de configuración.</span><span class="sxs-lookup"><span data-stu-id="28653-183">Navigate to Configuration Profiles.</span></span>

3.  <span data-ttu-id="28653-184">Seleccione **Crear perfil**.</span><span class="sxs-lookup"><span data-stu-id="28653-184">Select **Create Profile**.</span></span>

4.  <span data-ttu-id="28653-185">Seleccione **Windows 10** como plataforma.</span><span class="sxs-lookup"><span data-stu-id="28653-185">Select **Windows 10** as the platform.</span></span>

5.  <span data-ttu-id="28653-186">Seleccione **Personalizado** como tipo de perfil.</span><span class="sxs-lookup"><span data-stu-id="28653-186">Select **Custom** as profile type.</span></span>

6.  <span data-ttu-id="28653-187">Seleccione la pestaña **Configuración**.</span><span class="sxs-lookup"><span data-stu-id="28653-187">Select the **Settings** tab.</span></span>

7.  <span data-ttu-id="28653-188">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="28653-188">Select **Add**.</span></span>

8.  <span data-ttu-id="28653-189">Escriba la información siguiente de directiva:</span><span class="sxs-lookup"><span data-stu-id="28653-189">Enter the following policy information.</span></span>
    
    <span data-ttu-id="28653-190">OMA-URI: `./Device/Vendor/MSFT/Policy/Config/Chrome~Policy~googlechrome~Extensions/ExtensionInstallForcelist`</span><span class="sxs-lookup"><span data-stu-id="28653-190">OMA-URI: `./Device/Vendor/MSFT/Policy/Config/Chrome~Policy~googlechrome~Extensions/ExtensionInstallForcelist`</span></span><br/>
    <span data-ttu-id="28653-191">Tipo de datos: `String`</span><span class="sxs-lookup"><span data-stu-id="28653-191">Data type: `String`</span></span><br/>
    <span data-ttu-id="28653-192">Valor: `<enabled/><data id="ExtensionInstallForcelistDesc" value="1&#xF000; echcggldkblhodogklpincgchnpgcdco;https://clients2.google.com/service/update2/crx"/>`</span><span class="sxs-lookup"><span data-stu-id="28653-192">Value: `<enabled/><data id="ExtensionInstallForcelistDesc" value="1&#xF000; echcggldkblhodogklpincgchnpgcdco;https://clients2.google.com/service/update2/crx"/>`</span></span>

9.  <span data-ttu-id="28653-193">Haga clic en Crear</span><span class="sxs-lookup"><span data-stu-id="28653-193">Click create.</span></span>

### <a name="deploy-using-group-policy"></a><span data-ttu-id="28653-194">Implementar mediante la directiva de grupo</span><span class="sxs-lookup"><span data-stu-id="28653-194">Deploy using Group Policy</span></span>

<span data-ttu-id="28653-195">Si no quiere usar Microsoft Endpoint Manager, puede usar directivas de grupo para implementar la extensión de cumplimiento de Microsoft en toda la organización</span><span class="sxs-lookup"><span data-stu-id="28653-195">If you don't want to use Microsoft Endpoint Manager, you can use group policies to deploy the Microsoft Compliance Extension across your organization</span></span>

1. <span data-ttu-id="28653-196">Sus dispositivos deben poder ser administrados mediante la directiva de grupo, y debe importar todos los ADMX de Chrome en el almacén central de la directiva de grupo.</span><span class="sxs-lookup"><span data-stu-id="28653-196">Your devices must be manageable via Group Policy, and you need to import all Chrome ADMXs into the Group Policy Central Store.</span></span> <span data-ttu-id="28653-197">Para más información, consulte [Cómo crear y administrar el almacén central de plantillas administrativas de directiva de grupo en Windows](https://docs.microsoft.com/troubleshoot/windows-client/group-policy/create-and-manage-central-store).</span><span class="sxs-lookup"><span data-stu-id="28653-197">For more information, see [How to create and manage the Central Store for Group Policy Administrative Templates in Windows](https://docs.microsoft.com/troubleshoot/windows-client/group-policy/create-and-manage-central-store).</span></span>

2.  <span data-ttu-id="28653-198">Crear un script de PowerShell mediante este comando de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="28653-198">Create a PowerShell script using this PowerShell command:</span></span>

    ```powershell
    Get-Item -path "HKLM:\SOFTWARE\Microsoft\Windows Defender\Miscellaneous Configuration" | New-ItemProperty -Name DlpDisableBrowserCache -Value 0 -Force
    ```

3.  <span data-ttu-id="28653-199">Abra la **Consola de administración de la directiva de grupo** y vaya a la unidad organizativa (OU).</span><span class="sxs-lookup"><span data-stu-id="28653-199">Open the **Group Policy Management Console** and navigate to your organizational unit (OU).</span></span>

4.  <span data-ttu-id="28653-200">Haga clic y seleccione **Crear un GPO en este dominio y vincularlo aquí**.</span><span class="sxs-lookup"><span data-stu-id="28653-200">Right-click and select **Create a GPO in this domain and Link it here**.</span></span> <span data-ttu-id="28653-201">Cuando se solicite, asigne un nombre descriptivo a este objeto de directiva de grupo (GPO) y finalice la creación.</span><span class="sxs-lookup"><span data-stu-id="28653-201">When prompted, assign a descriptive name to this group policy object (GPO) and finish creating it.</span></span>

5.  <span data-ttu-id="28653-202">Haga clic en el GPO y seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="28653-202">Right-click the GPO and select **Edit**.</span></span>

6.  <span data-ttu-id="28653-203">Vaya a **Configuración del equipo** > **Preferencias** > **Configuración del panel de control** > **Tareas programadas**.</span><span class="sxs-lookup"><span data-stu-id="28653-203">Go to **Computer Configuration** > **Preferences** > **Control Panel Settings** > **Scheduled Tasks**.</span></span>

7.  <span data-ttu-id="28653-204">Cree una nueva tarea inmediata. Para ello, haga clic y seleccione **Nuevo** > **Tarea inmediata (al menos Windows 7)**.</span><span class="sxs-lookup"><span data-stu-id="28653-204">Create a new immediate task by selecting right-clicking and selecting **New** > **Immediate Task (At least Windows 7)**.</span></span>

8.  <span data-ttu-id="28653-205">Asigne un nombre y una descripción a la tarea.</span><span class="sxs-lookup"><span data-stu-id="28653-205">Give the task a name & description.</span></span>

9.  <span data-ttu-id="28653-206">Elija la cuenta correspondiente para ejecutar la tarea inmediata, por ejemplo NT Authority.</span><span class="sxs-lookup"><span data-stu-id="28653-206">Choose the corresponding account to run the immediate task, for example NT Authority</span></span>

10. <span data-ttu-id="28653-207">Seleccione **Ejecutar con los privilegios más altos**.</span><span class="sxs-lookup"><span data-stu-id="28653-207">Select **Run with highest privileges**.</span></span>

11. <span data-ttu-id="28653-208">Configure la directiva para Windows 10.</span><span class="sxs-lookup"><span data-stu-id="28653-208">Configure the policy for Windows 10.</span></span>

12. <span data-ttu-id="28653-209">En la pestaña **Acciones**, seleccione la acción **Iniciar un programa**.</span><span class="sxs-lookup"><span data-stu-id="28653-209">In the **Actions** tab, select the action **Start a program**.</span></span>

13. <span data-ttu-id="28653-210">Escriba la ruta de acceso al Programa/Script creado en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="28653-210">Enter the path to the Program/Script created in Step 1.</span></span>

14. <span data-ttu-id="28653-211">Seleccione **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="28653-211">Select **Apply**.</span></span>

#### <a name="adding-the-chrome-extension-to-the-forceinstall-list"></a><span data-ttu-id="28653-212">Agregar la extensión de Chrome a la lista ForceInstall</span><span class="sxs-lookup"><span data-stu-id="28653-212">Adding the Chrome Extension to the ForceInstall List</span></span>

1.  <span data-ttu-id="28653-213">En el Editor de administración de directivas de grupo, vaya a su OU.</span><span class="sxs-lookup"><span data-stu-id="28653-213">In the Group Policy Management Editor, navigate to your OU.</span></span>

2.  <span data-ttu-id="28653-214">Expanda la siguiente ruta **Configuración del equipo/usuario** > **Directivas** > **Plantillas administrativas** > **Plantillas administrativas clásicas** > **Google** > **Google Chrome** > **Extensiones**.</span><span class="sxs-lookup"><span data-stu-id="28653-214">Expand the following path **Computer/User configuration** > **Policies** > **Administrative templates** > **Classic administrative templates** > **Google** > **Google Chrome** > **Extensions**.</span></span> <span data-ttu-id="28653-215">Esta ruta puede variar en función de su configuración.</span><span class="sxs-lookup"><span data-stu-id="28653-215">This path may vary depending on your configuration.</span></span>

3.  <span data-ttu-id="28653-216">Seleccione **Configurar la lista de extensiones instaladas de manera forzosa**.</span><span class="sxs-lookup"><span data-stu-id="28653-216">Select **Configure the list of force-installed extensions**.</span></span>

4.  <span data-ttu-id="28653-217">Haga clic con el botón derecho y seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="28653-217">Right click and select **Edit**.</span></span>

5.  <span data-ttu-id="28653-218">Seleccione **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="28653-218">Select **Enabled**.</span></span>

6.  <span data-ttu-id="28653-219">Seleccionar **Mostrar**.</span><span class="sxs-lookup"><span data-stu-id="28653-219">Select **Show**.</span></span>

7.  <span data-ttu-id="28653-220">En **Valor**, agregue la siguiente entrada: `echcggldkblhodogklpincgchnpgcdco;https://clients2.google.com/service/update2/crx`</span><span class="sxs-lookup"><span data-stu-id="28653-220">Under **Value**, add the following entry: `echcggldkblhodogklpincgchnpgcdco;https://clients2.google.com/service/update2/crx`</span></span>

8.  <span data-ttu-id="28653-221">Seleccione **Aceptar** y, luego, **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="28653-221">Select **OK** and then **Apply**.</span></span>

### <a name="test-the-extension"></a><span data-ttu-id="28653-222">Probar la extensión</span><span class="sxs-lookup"><span data-stu-id="28653-222">Test the Extension</span></span>

#### <a name="upload-to-cloud-service-or-access-by-unallowed-browsers-cloud-egress"></a><span data-ttu-id="28653-223">Cargar en el servicio en la nube o acceso por salida de la nube de exploradores no permitidos</span><span class="sxs-lookup"><span data-stu-id="28653-223">Upload to cloud service, or access by unallowed browsers Cloud Egress</span></span>  

1. <span data-ttu-id="28653-224">Cree u obtenga un elemento confidencial y pruebe a cargar un archivo a uno de los dominios de servicio restringido de la organización.</span><span class="sxs-lookup"><span data-stu-id="28653-224">Create or get a sensitive item and, try to upload a file to one of your organization’s restricted service domains.</span></span> <span data-ttu-id="28653-225">Los datos confidenciales deben coincidir con uno de nuestros [Tipos de información confidencial](sensitive-information-type-entity-definitions.md) o con uno de los tipos de información confidencial de su organización.</span><span class="sxs-lookup"><span data-stu-id="28653-225">The sensitive data must match one of our built-in [Sensitive Info Types](sensitive-information-type-entity-definitions.md), or one of your organization’s sensitive information types.</span></span> <span data-ttu-id="28653-226">Debería recibir una notificación del sistema DLP en el dispositivo en el que esté probando que muestre que esta acción no está permitida cuando el archivo está abierto.</span><span class="sxs-lookup"><span data-stu-id="28653-226">You should get a DLP toast notification on the device you are testing from that shows that this action is not allowed when the file is open.</span></span>

#### <a name="testing-other-dlp-scenarios-in-chrome"></a><span data-ttu-id="28653-227">Probar otros escenarios DLP en Chrome</span><span class="sxs-lookup"><span data-stu-id="28653-227">Testing other DLP scenarios in Chrome</span></span> 

<span data-ttu-id="28653-228">Ahora que ha quitado Chrome de la lista de aplicaciones/exploradores no permitidos, puede probar los siguientes escenarios para confirmar que el comportamiento se ajusta a los requisitos de su organización:</span><span class="sxs-lookup"><span data-stu-id="28653-228">Now that you’ve removed Chrome from the disallowed browsers/apps list, you can test the scenarios below to confirm the behavior meets your organization’s requirements:</span></span>

- <span data-ttu-id="28653-229">Copiar datos de un elemento confidencial a otro documento mediante el Portapapeles</span><span class="sxs-lookup"><span data-stu-id="28653-229">Copy data from a sensitive item to another document using the Clipboard</span></span>
    - <span data-ttu-id="28653-230">Para probarlo, abra un archivo que esté protegido contra acciones de copiar al portapapeles en el explorador Chrome y trate de copiar datos del archivo.</span><span class="sxs-lookup"><span data-stu-id="28653-230">To test, open a file that is protected against copy to clipboard actions in the Chrome browser and attempt to copy data from the file.</span></span>
    - <span data-ttu-id="28653-231">Resultado esperado: se muestra una notificación de sistema de DLP que indica que esta acción no se permite cuando el archivo está abierto.</span><span class="sxs-lookup"><span data-stu-id="28653-231">Expected Result: A DLP toast notification showing that this action is not allowed when the file is open.</span></span>
- <span data-ttu-id="28653-232">Imprimir un documento</span><span class="sxs-lookup"><span data-stu-id="28653-232">Print a document</span></span>
    - <span data-ttu-id="28653-233">Para probarlo, abra un archivo que esté protegido contra acciones de impresión en el explorador Chrome y trate de imprimir el archivo.</span><span class="sxs-lookup"><span data-stu-id="28653-233">To test, open a file that is protected against print actions in the Chrome browser and attempt to print the file.</span></span>
    - <span data-ttu-id="28653-234">Resultado esperado: se muestra una notificación de sistema de DLP que indica que esta acción no se permite cuando el archivo está abierto.</span><span class="sxs-lookup"><span data-stu-id="28653-234">Expected Result: A DLP toast notification showing that this action is not allowed when the file is open.</span></span>
- <span data-ttu-id="28653-235">Copiar en un medio extraíble USB</span><span class="sxs-lookup"><span data-stu-id="28653-235">Copy to USB Removeable Media</span></span>
    - <span data-ttu-id="28653-236">Para probarlo, trate de guardar el archivo en un almacenamiento de medio extraíble.</span><span class="sxs-lookup"><span data-stu-id="28653-236">To test, try to save the file to a removeable media storage.</span></span>
    - <span data-ttu-id="28653-237">Resultado esperado: se muestra una notificación de sistema de DLP que indica que esta acción no se permite cuando el archivo está abierto.</span><span class="sxs-lookup"><span data-stu-id="28653-237">Expected Result: A DLP toast notification showing that this action is not allowed when the file is open.</span></span>
- <span data-ttu-id="28653-238">Copiar en un recurso compartido de red</span><span class="sxs-lookup"><span data-stu-id="28653-238">Copy to Network Share</span></span>
    - <span data-ttu-id="28653-239">Para probarlo, trate de guardar el archivo en un recurso compartido de red.</span><span class="sxs-lookup"><span data-stu-id="28653-239">To test, try to save the file to a network share.</span></span>
    - <span data-ttu-id="28653-240">Resultado esperado: se muestra una notificación de sistema de DLP que indica que esta acción no se permite cuando el archivo está abierto.</span><span class="sxs-lookup"><span data-stu-id="28653-240">Expected Result: A DLP toast notification showing that this action is not allowed when the file is open.</span></span>


### <a name="use-the-alerts-management-dashboard-to-viewing-chrome-dlp-alerts"></a><span data-ttu-id="28653-241">Usar el panel de administración de alertas para ver las alertas de DLP de Chrome</span><span class="sxs-lookup"><span data-stu-id="28653-241">Use the Alerts Management Dashboard to viewing Chrome DLP alerts</span></span>

1. <span data-ttu-id="28653-242">Abra la página sobre la **Prevención de pérdida de datos** en el [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com) y seleccione **Alertas**.</span><span class="sxs-lookup"><span data-stu-id="28653-242">Open the **Data loss prevention** page in the [Microsoft 365 Compliance center](https://compliance.microsoft.com) and select **Alerts**.</span></span>

2. <span data-ttu-id="28653-243">Vea los procedimientos descritos en [Cómo configurar y ver las alertas de las directivas DLP](dlp-configure-view-alerts-policies.md) para ver las alertas de las directivas DLP del punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="28653-243">Refer to the procedures in [How to configure and view alerts for your DLP policies](dlp-configure-view-alerts-policies.md) to view alerts for your Endpoint DLP policies.</span></span>


### <a name="viewing-chrome-dlp-data-in-activity-explorer"></a><span data-ttu-id="28653-244">Visualizar datos de Endpoint DLP en el explorador de actividad</span><span class="sxs-lookup"><span data-stu-id="28653-244">Viewing Chrome DLP data in activity explorer</span></span>

1. <span data-ttu-id="28653-245">Abra la [Página clasificación de datos](https://compliance.microsoft.com/dataclassification?viewid=overview) del dominio en el Centro de cumplimiento de Microsoft 365 y elija **Explorador de actividad**.</span><span class="sxs-lookup"><span data-stu-id="28653-245">Open the [Data classification page](https://compliance.microsoft.com/dataclassification?viewid=overview) for your domain in the Microsoft 365 Compliance center and choose **Activity explorer**.</span></span>

2. <span data-ttu-id="28653-246">Consulte los procedimientos descritos en [Introducción al explorador de actividad](data-classification-activity-explorer.md) para tener acceso a todos los datos de los dispositivos con Endpoint y filtrarlos.</span><span class="sxs-lookup"><span data-stu-id="28653-246">Refer to the procedures in [Get started with Activity explorer](data-classification-activity-explorer.md) to access and filter all the data for your Endpoint devices.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="28653-247">![filtro de explorador de actividad filtro para dispositivos de punto de conexión](../media/endpoint-dlp-4-getting-started-activity-explorer.png)</span><span class="sxs-lookup"><span data-stu-id="28653-247">![activity explorer filter for endpoint devices](../media/endpoint-dlp-4-getting-started-activity-explorer.png)</span></span>

### <a name="known-issues-and-limitations"></a><span data-ttu-id="28653-248">Problemas y limitaciones conocidos</span><span class="sxs-lookup"><span data-stu-id="28653-248">Known Issues and Limitations</span></span>

1. <span data-ttu-id="28653-249">No se admite la Invalidación del bloqueo para la salida de la nube.</span><span class="sxs-lookup"><span data-stu-id="28653-249">Block Override enforcement for cloud egress is not supported.</span></span>
2. <span data-ttu-id="28653-250">No se admite el modo incógnito y se debe deshabilitar.</span><span class="sxs-lookup"><span data-stu-id="28653-250">Incognito mode is not supported and must be disabled.</span></span>

## <a name="next-steps"></a><span data-ttu-id="28653-251">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="28653-251">Next steps</span></span>
<span data-ttu-id="28653-252">Ahora que tiene dispositivos incorporados y puede ver los datos de la actividad en el explorador de actividad, está listo para realizar el siguiente paso, donde puede crear directivas DLP que protegen los elementos confidenciales.</span><span class="sxs-lookup"><span data-stu-id="28653-252">Now that you have onboarded devices and can view the activity data in Activity explorer, you are ready to move on to your next step where you create DLP policies that protect your sensitive items.</span></span>

- [<span data-ttu-id="28653-253">Uso de la prevención de pérdida de datos en punto de conexión</span><span class="sxs-lookup"><span data-stu-id="28653-253">Using Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)

## <a name="see-also"></a><span data-ttu-id="28653-254">Consulte también</span><span class="sxs-lookup"><span data-stu-id="28653-254">See also</span></span>

- [<span data-ttu-id="28653-255">Obtenga información sobre la prevención de pérdida de datos en punto de conexión</span><span class="sxs-lookup"><span data-stu-id="28653-255">Learn about Endpoint data loss prevention </span></span>](endpoint-dlp-learn-about.md)
- [<span data-ttu-id="28653-256">Uso de la prevención de pérdida de datos en punto de conexión</span><span class="sxs-lookup"><span data-stu-id="28653-256">Using Endpoint data loss prevention </span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="28653-257">Obtenga más información acerca de la prevención contra la pérdida de datos</span><span class="sxs-lookup"><span data-stu-id="28653-257">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="28653-258">Crear, probar y optimizar una directiva DLP</span><span class="sxs-lookup"><span data-stu-id="28653-258">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="28653-259">Introducción al explorador de actividad</span><span class="sxs-lookup"><span data-stu-id="28653-259">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="28653-260">Microsoft Defender para punto de conexión</span><span class="sxs-lookup"><span data-stu-id="28653-260">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)
- <span data-ttu-id="28653-261">[Herramientas y métodos de incorporación para equipos con Windows 10](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span><span class="sxs-lookup"><span data-stu-id="28653-261">[Onboarding tools and methods for Windows 10 machines](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)</span></span>
- [<span data-ttu-id="28653-262">Suscripción a Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="28653-262">Microsoft 365 subscription</span></span>](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [<span data-ttu-id="28653-263">Dispositivos de Azure AD Unidos</span><span class="sxs-lookup"><span data-stu-id="28653-263">Azure AD joined devices</span></span>](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join)
- [<span data-ttu-id="28653-264">Descargar el nuevo Microsoft Edge basado en Chromium</span><span class="sxs-lookup"><span data-stu-id="28653-264">Download the new Microsoft Edge based on Chromium</span></span>](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)
