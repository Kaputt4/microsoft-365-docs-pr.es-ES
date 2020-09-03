---
title: Obtener información sobre la movilidad básica y los dispositivos administrados de seguridad
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: Use Windows PowerShell para obtener detalles sobre los dispositivos de seguridad y movilidad básicos de su organización.
ms.openlocfilehash: 7b041e54d512291163616d3b61973cef989cec5c
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "47337079"
---
# <a name="get-details-about-basic-mobility-and-security-managed-devices"></a><span data-ttu-id="a4ef5-103">Obtener información sobre la movilidad básica y los dispositivos administrados de seguridad</span><span class="sxs-lookup"><span data-stu-id="a4ef5-103">Get details about Basic Mobility and Security managed devices</span></span>

<span data-ttu-id="a4ef5-104">En este artículo se muestra cómo usar Windows PowerShell para obtener detalles sobre los dispositivos de la organización que ha configurado para la movilidad y la seguridad básicos.</span><span class="sxs-lookup"><span data-stu-id="a4ef5-104">This article shows you how to use Windows PowerShell to get details about the devices in your organization that you set up for Basic Mobility and Security.</span></span>

<span data-ttu-id="a4ef5-105">Este es un desglose de los detalles de dispositivos disponibles.</span><span class="sxs-lookup"><span data-stu-id="a4ef5-105">Here's a breakdown for the device details available to you.</span></span>

|<span data-ttu-id="a4ef5-106">**Detalle**</span><span class="sxs-lookup"><span data-stu-id="a4ef5-106">**Detail**</span></span>|<span data-ttu-id="a4ef5-107">**Qué buscar en PowerShell**</span><span class="sxs-lookup"><span data-stu-id="a4ef5-107">**What to look for in PowerShell**</span></span>|
|:----------------|:------------------------------------------------------------------------------|
|<span data-ttu-id="a4ef5-108">El dispositivo está inscrito en la movilidad y la seguridad básicas.</span><span class="sxs-lookup"><span data-stu-id="a4ef5-108">Device is enrolled in Basic Mobility and Security.</span></span> <span data-ttu-id="a4ef5-109">Para obtener más información, consulte [inscribir un dispositivo móvil usando la movilidad y la seguridad básicas](enroll-your-mobile-device-using-basic-mobility-and-security.md)</span><span class="sxs-lookup"><span data-stu-id="a4ef5-109">For more info, see [Enroll your mobile device using Basic Mobility and Security](enroll-your-mobile-device-using-basic-mobility-and-security.md)</span></span>|<span data-ttu-id="a4ef5-110">El valor del parámetro *isManaged*   es:</span><span class="sxs-lookup"><span data-stu-id="a4ef5-110">The value of the *isManaged* parameter is:</span></span><br/><span data-ttu-id="a4ef5-111">**True**= el dispositivo está inscrito.</span><span class="sxs-lookup"><span data-stu-id="a4ef5-111">**True**= device is enrolled.</span></span><br/><span data-ttu-id="a4ef5-112">**False**= no se inscribe el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a4ef5-112">**False**= device is not enrolled.</span></span> |
|<span data-ttu-id="a4ef5-113">El dispositivo es compatible con las directivas de seguridad del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a4ef5-113">Device is compliant with your device security policies.</span></span> <span data-ttu-id="a4ef5-114">Para obtener más información, consulte [crear directivas de seguridad de dispositivos](create-device-security-policies-in-basic-mmobility-and-security.md) .</span><span class="sxs-lookup"><span data-stu-id="a4ef5-114">For more info, see [Create device security policies](create-device-security-policies-in-basic-mmobility-and-security.md)</span></span>|<span data-ttu-id="a4ef5-115">El valor del parámetro *isCompliant*   es:</span><span class="sxs-lookup"><span data-stu-id="a4ef5-115">The value of the *isCompliant* parameter is:</span></span><br/><span data-ttu-id="a4ef5-116">**True**   = el dispositivo es compatible con las directivas.</span><span class="sxs-lookup"><span data-stu-id="a4ef5-116">**True** = device is compliant with policies.</span></span><br/><span data-ttu-id="a4ef5-117">**False**   = el dispositivo no es compatible con las directivas.</span><span class="sxs-lookup"><span data-stu-id="a4ef5-117">**False** = device is not compliant with policies.</span></span>|

:::image type="content" source="../../media/basic-mobility-security/bms-7-powershell-parameters.png" alt-text="Parámetros básicos de PowerShell de seguridad y movilidad":::

>[!NOTE]
><span data-ttu-id="a4ef5-119">Los comandos y los scripts de este artículo también devuelven detalles sobre los dispositivos administrados por [Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune).</span><span class="sxs-lookup"><span data-stu-id="a4ef5-119">The commands and scripts in this article also return details about any devices managed by [Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="a4ef5-120">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="a4ef5-120">Before you begin</span></span>

<span data-ttu-id="a4ef5-121">Hay algunas cosas que debe configurar para ejecutar los comandos y scripts descritos en este artículo.</span><span class="sxs-lookup"><span data-stu-id="a4ef5-121">There are a few things you need to set up to run the commands and scripts described in this article.</span></span>

### <a name="step-1-download-and-install-the-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="a4ef5-122">Paso 1: descargar e instalar el módulo de Azure Active Directory para Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a4ef5-122">Step 1: Download and install the Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="a4ef5-123">Para obtener más información sobre estos pasos, consulte [conectarse a Microsoft 365 con PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="a4ef5-123">For more info on these steps, see [Connect to Microsoft 365 with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell).</span></span>

1. <span data-ttu-id="a4ef5-124">Vaya a [Microsoft Online Services-ayudante para el inicio de sesión para profesionales de ti RTWl](https://www.microsoft.com/download/details.aspx?id=41950)   y seleccione  **descargar para el ayudante para el inicio de sesión de Microsoft Online Services**.</span><span class="sxs-lookup"><span data-stu-id="a4ef5-124">Go to [Microsoft Online Services Sign-In Assistant for IT Professionals RTWl](https://www.microsoft.com/download/details.aspx?id=41950) and select  **Download for Microsoft Online Services Sign-in Assistant**.</span></span>   

2. <span data-ttu-id="a4ef5-125">Instale el Módulo Microsoft Azure Active Directory para Windows PowerShell siguiendo estos pasos:</span><span class="sxs-lookup"><span data-stu-id="a4ef5-125">Install the Microsoft Azure Active Directory Module for Windows PowerShell with these steps:</span></span>   

    1. <span data-ttu-id="a4ef5-126">Abra un símbolo del sistema de PowerShell con permisos de administrador.</span><span class="sxs-lookup"><span data-stu-id="a4ef5-126">Open an administrator-level PowerShell command prompt.</span></span>  

    2. <span data-ttu-id="a4ef5-127">Ejecute el comando Install-Module MSOnline.</span><span class="sxs-lookup"><span data-stu-id="a4ef5-127">Run the Install-Module MSOnline command.</span></span>
    
    3. <span data-ttu-id="a4ef5-128">Si se le pide que instale el proveedor de NuGet, escriba Y y presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="a4ef5-128">If prompted to install the NuGet provider, type Y and press ENTER.</span></span>   

    4. <span data-ttu-id="a4ef5-129">Si se le pide que instale el módulo desde PSGallery, escriba Y y presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="a4ef5-129">If prompted to install the module from PSGallery, type Y and press ENTER.</span></span>   

    5. <span data-ttu-id="a4ef5-130">Después de la instalación, cierre la ventana de comandos de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a4ef5-130">After installation, close the PowerShell command window.</span></span>
    
### <a name="step-2-connect-to-your-microsoft-365-subscription"></a><span data-ttu-id="a4ef5-131">Paso 2: conectarse a la suscripción de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a4ef5-131">Step 2: Connect to your Microsoft 365 subscription</span></span>

1. <span data-ttu-id="a4ef5-132">En el módulo Windows Azure Active Directory para Windows PowerShell, ejecute el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="a4ef5-132">In the Windows Azure Active Directory Module for Windows PowerShell, run the following command.</span></span>  

    <span data-ttu-id="a4ef5-133">$UserCredential = Get-Credential</span><span class="sxs-lookup"><span data-stu-id="a4ef5-133">$UserCredential = Get-Credential</span></span>

2. <span data-ttu-id="a4ef5-134">En el cuadro de diálogo solicitud de credenciales para Windows PowerShell, escriba el nombre de usuario y la contraseña de su cuenta de administrador global de Microsoft 365 y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a4ef5-134">In the Windows PowerShell Credential Request dialog box, type the user name and password for your Microsoft 365 global admin account, and then select **OK**.</span></span>
    
3. <span data-ttu-id="a4ef5-135">Ejecute el comando siguiente.</span><span class="sxs-lookup"><span data-stu-id="a4ef5-135">Run the following command.</span></span>
    
    <span data-ttu-id="a4ef5-136">$UserCredential Connect-MsolService-Credential</span><span class="sxs-lookup"><span data-stu-id="a4ef5-136">Connect-MsolService -Credential $UserCredential</span></span>

### <a name="step-3-make-sure-youre-able-to-run-powershell-scripts"></a><span data-ttu-id="a4ef5-137">Paso 3: Asegúrese de que puede ejecutar scripts de PowerShell</span><span class="sxs-lookup"><span data-stu-id="a4ef5-137">Step 3: Make sure you’re able to run PowerShell scripts</span></span>

>[!NOTE]
><span data-ttu-id="a4ef5-138">Puede omitir este paso si ya está configurado para ejecutar scripts de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a4ef5-138">You can skip this step if you’re already set up to run PowerShell scripts.</span></span>

<span data-ttu-id="a4ef5-139">Para ejecutar el script de Get-MsolUserDeviceComplianceStatus.ps1, debe habilitar la ejecución de scripts de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a4ef5-139">To run the Get-MsolUserDeviceComplianceStatus.ps1 script, you need to enable the running of PowerShell scripts.</span></span>

1. <span data-ttu-id="a4ef5-140">En el escritorio de Windows, seleccione **Inicio**y, a continuación, escriba Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a4ef5-140">From your Windows Desktop, select **Start**, and then type Windows PowerShell.</span></span> <span data-ttu-id="a4ef5-141">Haga clic con el botón secundario en Windows PowerShell y seleccione **Ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="a4ef5-141">Right-click Windows PowerShell, and then select **Run as administrator**.</span></span>

2. <span data-ttu-id="a4ef5-142">Ejecute el comando siguiente.</span><span class="sxs-lookup"><span data-stu-id="a4ef5-142">Run the following command.</span></span>
    
    <span data-ttu-id="a4ef5-143">Set-ExecutionPolicy RemoteSigned</span><span class="sxs-lookup"><span data-stu-id="a4ef5-143">Set-ExecutionPolicy  RemoteSigned</span></span>

3. <span data-ttu-id="a4ef5-144">Cuando se le solicite, escriba s y, a continuación, presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="a4ef5-144">When prompted, type Y and then press Enter.</span></span>
    
<span data-ttu-id="a4ef5-145">**Ejecute el cmdlet Get-MsolDevice para mostrar los detalles de todos los dispositivos de su organización.**</span><span class="sxs-lookup"><span data-stu-id="a4ef5-145">**Run the Get-MsolDevice cmdlet to display details for all devices in your organization**</span></span>

1. <span data-ttu-id="a4ef5-146">Abra el Módulo Microsoft Azure Active Directory para Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a4ef5-146">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>  

2. <span data-ttu-id="a4ef5-147">Ejecute el comando siguiente.</span><span class="sxs-lookup"><span data-stu-id="a4ef5-147">Run the following command.</span></span>
    
    <span data-ttu-id="a4ef5-148">Get-MsolDevice-All-ReturnRegisteredOwners | Where-Object {$ _. RegisteredOwners. Count-gt 0}</span><span class="sxs-lookup"><span data-stu-id="a4ef5-148">Get-MsolDevice -All -ReturnRegisteredOwners | Where-Object {$_.RegisteredOwners.Count -gt 0}</span></span>

<span data-ttu-id="a4ef5-149">Para obtener más ejemplos, consulte  [Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=841721).</span><span class="sxs-lookup"><span data-stu-id="a4ef5-149">For more examples, see  [Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=841721).</span></span>

## <a name="run-a-script-to-get-device-details"></a><span data-ttu-id="a4ef5-150">Ejecutar un script para obtener detalles del dispositivo</span><span class="sxs-lookup"><span data-stu-id="a4ef5-150">Run a script to get device details</span></span>

<span data-ttu-id="a4ef5-151">En primer lugar, guarde el script en el equipo.</span><span class="sxs-lookup"><span data-stu-id="a4ef5-151">First, save the script to your computer.</span></span>

1. <span data-ttu-id="a4ef5-152">Copie y pegue el texto siguiente en el Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="a4ef5-152">Copy and paste the following text into Notepad.</span></span>  

2.  <span data-ttu-id="a4ef5-153">parámetro</span><span class="sxs-lookup"><span data-stu-id="a4ef5-153">param (</span></span>
    

3.  <span data-ttu-id="a4ef5-154">[PSObject []] $users = @ (),</span><span class="sxs-lookup"><span data-stu-id="a4ef5-154">[PSObject[]]$users = @(),</span></span>
    

4.  <span data-ttu-id="a4ef5-155">[Modificador] $export,</span><span class="sxs-lookup"><span data-stu-id="a4ef5-155">[Switch]$export,</span></span>
    

5.  <span data-ttu-id="a4ef5-156">[String] $exportFileName = "UserDeviceComplianceStatus_" + (get-Date-Format "yyMMdd_HHMMss") + ". csv",</span><span class="sxs-lookup"><span data-stu-id="a4ef5-156">[String]$exportFileName = "UserDeviceComplianceStatus_" + (Get-Date -Format "yyMMdd_HHMMss") + ".csv",</span></span>
    

6.  <span data-ttu-id="a4ef5-157">[String] $exportPath = [Environment]:: GetFolderPath ("Desktop")</span><span class="sxs-lookup"><span data-stu-id="a4ef5-157">[String]$exportPath = [Environment]::GetFolderPath("Desktop")</span></span>
    

7.  <span data-ttu-id="a4ef5-158">)</span><span class="sxs-lookup"><span data-stu-id="a4ef5-158">)</span></span>
    

9.  <span data-ttu-id="a4ef5-159">[System. Collections. IDictionary] $script: Schema = @ {</span><span class="sxs-lookup"><span data-stu-id="a4ef5-159">[System.Collections.IDictionary]$script:schema = @{</span></span>
    

11.  <span data-ttu-id="a4ef5-160">DeviceId = ' '</span><span class="sxs-lookup"><span data-stu-id="a4ef5-160">DeviceId = ''</span></span>
    

12.  <span data-ttu-id="a4ef5-161">DeviceOSType = ' '</span><span class="sxs-lookup"><span data-stu-id="a4ef5-161">DeviceOSType = ''</span></span>
    

13.  <span data-ttu-id="a4ef5-162">DeviceOSVersion = ' '</span><span class="sxs-lookup"><span data-stu-id="a4ef5-162">DeviceOSVersion = ''</span></span>
    

14.  <span data-ttu-id="a4ef5-163">DeviceTrustLevel = ' '</span><span class="sxs-lookup"><span data-stu-id="a4ef5-163">DeviceTrustLevel = ''</span></span>
    

15.  <span data-ttu-id="a4ef5-164">DisplayName = ' '</span><span class="sxs-lookup"><span data-stu-id="a4ef5-164">DisplayName = ''</span></span>
    

16.  <span data-ttu-id="a4ef5-165">IsCompliant = ' '</span><span class="sxs-lookup"><span data-stu-id="a4ef5-165">IsCompliant = ''</span></span>
    

17.  <span data-ttu-id="a4ef5-166">IsManaged = ' '</span><span class="sxs-lookup"><span data-stu-id="a4ef5-166">IsManaged = ''</span></span>
    

18.  <span data-ttu-id="a4ef5-167">ApproximateLastLogonTimestamp = ' '</span><span class="sxs-lookup"><span data-stu-id="a4ef5-167">ApproximateLastLogonTimestamp = ''</span></span>
    

19.  <span data-ttu-id="a4ef5-168">DeviceObjectId = ' '</span><span class="sxs-lookup"><span data-stu-id="a4ef5-168">DeviceObjectId = ''</span></span>
    

20.  <span data-ttu-id="a4ef5-169">RegisteredOwnerUpn = ' '</span><span class="sxs-lookup"><span data-stu-id="a4ef5-169">RegisteredOwnerUpn = ''</span></span>
    

21.  <span data-ttu-id="a4ef5-170">RegisteredOwnerObjectId = ' '</span><span class="sxs-lookup"><span data-stu-id="a4ef5-170">RegisteredOwnerObjectId = ''</span></span>
    

22.  <span data-ttu-id="a4ef5-171">RegisteredOwnerDisplayName = ' '</span><span class="sxs-lookup"><span data-stu-id="a4ef5-171">RegisteredOwnerDisplayName = ''</span></span>
    

23.  <span data-ttu-id="a4ef5-172">}</span><span class="sxs-lookup"><span data-stu-id="a4ef5-172">}</span></span>
    

25.  <span data-ttu-id="a4ef5-173">función createResultObject</span><span class="sxs-lookup"><span data-stu-id="a4ef5-173">function createResultObject</span></span>
    

26.  <span data-ttu-id="a4ef5-174">{</span><span class="sxs-lookup"><span data-stu-id="a4ef5-174">{</span></span>
    

28.  <span data-ttu-id="a4ef5-175">[PSObject] $resultObject = New-Object-TypeName PSObject-Property $script: Schema</span><span class="sxs-lookup"><span data-stu-id="a4ef5-175">[PSObject]$resultObject = New-Object -TypeName PSObject -Property $script:schema</span></span>
    

30.  <span data-ttu-id="a4ef5-176">devolver $resultObject</span><span class="sxs-lookup"><span data-stu-id="a4ef5-176">return $resultObject</span></span>
    

31.  <span data-ttu-id="a4ef5-177">}</span><span class="sxs-lookup"><span data-stu-id="a4ef5-177">}</span></span>
    

33.  <span data-ttu-id="a4ef5-178">If ($users. Count-EQ 0)</span><span class="sxs-lookup"><span data-stu-id="a4ef5-178">If ($users.Count -eq 0)</span></span>
    

34.  <span data-ttu-id="a4ef5-179">{</span><span class="sxs-lookup"><span data-stu-id="a4ef5-179">{</span></span>
    

35.  <span data-ttu-id="a4ef5-180">$users = Get-MsolUser</span><span class="sxs-lookup"><span data-stu-id="a4ef5-180">$users = Get-MsolUser</span></span>
    

36.  <span data-ttu-id="a4ef5-181">}</span><span class="sxs-lookup"><span data-stu-id="a4ef5-181">}</span></span>
    

38.  <span data-ttu-id="a4ef5-182">[PSObject []] $result = foreach ($u en $users)</span><span class="sxs-lookup"><span data-stu-id="a4ef5-182">[PSObject[]]$result = foreach ($u in $users)</span></span>
    

39.  <span data-ttu-id="a4ef5-183">{</span><span class="sxs-lookup"><span data-stu-id="a4ef5-183">{</span></span>
    

41.  <span data-ttu-id="a4ef5-184">[PSObject] $devices = Get-msoldevice-RegisteredOwnerUpn $u. UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="a4ef5-184">[PSObject]$devices = get-msoldevice -RegisteredOwnerUpn $u.UserPrincipalName</span></span>
    

42.  <span data-ttu-id="a4ef5-185">foreach ($d en $devices)</span><span class="sxs-lookup"><span data-stu-id="a4ef5-185">foreach ($d in $devices)</span></span>
    

43.  <span data-ttu-id="a4ef5-186">{</span><span class="sxs-lookup"><span data-stu-id="a4ef5-186">{</span></span>
    

44.  <span data-ttu-id="a4ef5-187">[PSObject] $deviceResult = createResultObject</span><span class="sxs-lookup"><span data-stu-id="a4ef5-187">[PSObject]$deviceResult = createResultObject</span></span>
    

45.  <span data-ttu-id="a4ef5-188">$deviceResult. DeviceId = $d. DeviceId</span><span class="sxs-lookup"><span data-stu-id="a4ef5-188">$deviceResult.DeviceId = $d.DeviceId</span></span>
    

46.  <span data-ttu-id="a4ef5-189">$deviceResult. DeviceOSType = $d. DeviceOSType</span><span class="sxs-lookup"><span data-stu-id="a4ef5-189">$deviceResult.DeviceOSType = $d.DeviceOSType</span></span>
    

47.  <span data-ttu-id="a4ef5-190">$deviceResult. DeviceOSVersion = $d. DeviceOSVersion</span><span class="sxs-lookup"><span data-stu-id="a4ef5-190">$deviceResult.DeviceOSVersion = $d.DeviceOSVersion</span></span>
    

48.  <span data-ttu-id="a4ef5-191">$deviceResult. DeviceTrustLevel = $d. DeviceTrustLevel</span><span class="sxs-lookup"><span data-stu-id="a4ef5-191">$deviceResult.DeviceTrustLevel = $d.DeviceTrustLevel</span></span>
    

49.  <span data-ttu-id="a4ef5-192">$deviceResult. DisplayName = $d. DisplayName</span><span class="sxs-lookup"><span data-stu-id="a4ef5-192">$deviceResult.DisplayName = $d.DisplayName</span></span>
    

50.  <span data-ttu-id="a4ef5-193">$deviceResult. IsCompliant = $d. GraphDeviceObject. IsCompliant</span><span class="sxs-lookup"><span data-stu-id="a4ef5-193">$deviceResult.IsCompliant = $d.GraphDeviceObject.IsCompliant</span></span>
    

51.  <span data-ttu-id="a4ef5-194">$deviceResult. IsManaged = $d. GraphDeviceObject. IsManaged</span><span class="sxs-lookup"><span data-stu-id="a4ef5-194">$deviceResult.IsManaged = $d.GraphDeviceObject.IsManaged</span></span>
    

52.  <span data-ttu-id="a4ef5-195">$deviceResult. DeviceObjectId = $d. ObjectId</span><span class="sxs-lookup"><span data-stu-id="a4ef5-195">$deviceResult.DeviceObjectId = $d.ObjectId</span></span>
    

53.  <span data-ttu-id="a4ef5-196">$deviceResult. RegisteredOwnerUpn = $u. UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="a4ef5-196">$deviceResult.RegisteredOwnerUpn = $u.UserPrincipalName</span></span>
    

54.  <span data-ttu-id="a4ef5-197">$deviceResult. RegisteredOwnerObjectId = $u. ObjectId</span><span class="sxs-lookup"><span data-stu-id="a4ef5-197">$deviceResult.RegisteredOwnerObjectId = $u.ObjectId</span></span>
    

55.  <span data-ttu-id="a4ef5-198">$deviceResult. RegisteredOwnerDisplayName = $u. DisplayName</span><span class="sxs-lookup"><span data-stu-id="a4ef5-198">$deviceResult.RegisteredOwnerDisplayName = $u.DisplayName</span></span>
    

56.  <span data-ttu-id="a4ef5-199">$deviceResult. ApproximateLastLogonTimestamp = $d. ApproximateLastLogonTimestamp</span><span class="sxs-lookup"><span data-stu-id="a4ef5-199">$deviceResult.ApproximateLastLogonTimestamp = $d.ApproximateLastLogonTimestamp</span></span>
    

58.  <span data-ttu-id="a4ef5-200">$deviceResult</span><span class="sxs-lookup"><span data-stu-id="a4ef5-200">$deviceResult</span></span>
    

59.  <span data-ttu-id="a4ef5-201">}</span><span class="sxs-lookup"><span data-stu-id="a4ef5-201">}</span></span>
    

61.  <span data-ttu-id="a4ef5-202">}</span><span class="sxs-lookup"><span data-stu-id="a4ef5-202">}</span></span>
    

63.  <span data-ttu-id="a4ef5-203">If ($export)</span><span class="sxs-lookup"><span data-stu-id="a4ef5-203">If ($export)</span></span>
    

64.  <span data-ttu-id="a4ef5-204">{</span><span class="sxs-lookup"><span data-stu-id="a4ef5-204">{</span></span>
    

65.  <span data-ttu-id="a4ef5-205">$result | Export-CSV-Path ($exportPath + " \" + $exportFileName)-NoTypeInformation</span><span class="sxs-lookup"><span data-stu-id="a4ef5-205">$result | Export-Csv -path ($exportPath + "\" + $exportFileName) -NoTypeInformation</span></span>
    

66.  <span data-ttu-id="a4ef5-206">}</span><span class="sxs-lookup"><span data-stu-id="a4ef5-206">}</span></span>
    

67.  <span data-ttu-id="a4ef5-207">Else</span><span class="sxs-lookup"><span data-stu-id="a4ef5-207">Else</span></span>
    

68.  <span data-ttu-id="a4ef5-208">{</span><span class="sxs-lookup"><span data-stu-id="a4ef5-208">{</span></span>
    

69.  <span data-ttu-id="a4ef5-209">$result</span><span class="sxs-lookup"><span data-stu-id="a4ef5-209">$result</span></span>
    

70.  <span data-ttu-id="a4ef5-210">}</span><span class="sxs-lookup"><span data-stu-id="a4ef5-210">}</span></span>
    

71.  <span data-ttu-id="a4ef5-211">Guárdelo como un archivo de script de Windows PowerShell mediante la extensión de archivo. ps1; por ejemplo, Get-MsolUserDeviceComplianceStatus.ps1.</span><span class="sxs-lookup"><span data-stu-id="a4ef5-211">Save it as a Windows PowerShell script file by using the file extension .ps1; for example, Get-MsolUserDeviceComplianceStatus.ps1.</span></span>   

## <a name="run-the-script-to-get-device-information-for-a-single-user-account"></a><span data-ttu-id="a4ef5-212">Ejecutar el script para obtener información del dispositivo para una sola cuenta de usuario</span><span class="sxs-lookup"><span data-stu-id="a4ef5-212">Run the script to get device information for a single user account</span></span>

1. <span data-ttu-id="a4ef5-213">Abra el Módulo Microsoft Azure Active Directory para Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a4ef5-213">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>
    
2. <span data-ttu-id="a4ef5-214">Vaya a la carpeta en la que guardó el script.</span><span class="sxs-lookup"><span data-stu-id="a4ef5-214">Go to the folder where you saved the script.</span></span> <span data-ttu-id="a4ef5-215">Por ejemplo, si lo guardó en C:\PS-Scripts, ejecute el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="a4ef5-215">For example, if you saved it to C:\PS-Scripts, run the following command.</span></span>
    
    <span data-ttu-id="a4ef5-216">CD C:\PS-Scripts</span><span class="sxs-lookup"><span data-stu-id="a4ef5-216">cd C:\PS-Scripts</span></span>

3. <span data-ttu-id="a4ef5-217">Ejecute el siguiente comando para identificar el usuario para el que desea obtener detalles del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a4ef5-217">Run the following command to identify the user you want to get device details for.</span></span> <span data-ttu-id="a4ef5-218">En este ejemplo se obtienen los detalles de bar@example.com.</span><span class="sxs-lookup"><span data-stu-id="a4ef5-218">This example gets details for bar@example.com.</span></span>
    
    <span data-ttu-id="a4ef5-219">$u = Get-MsolUser-UserPrincipalName bar@example.com</span><span class="sxs-lookup"><span data-stu-id="a4ef5-219">$u = Get-MsolUser -UserPrincipalName bar@example.com</span></span>

4. <span data-ttu-id="a4ef5-220">Ejecute el siguiente comando para iniciar el script.</span><span class="sxs-lookup"><span data-stu-id="a4ef5-220">Run the following command to initiate the script.</span></span>

    <span data-ttu-id="a4ef5-221">.\Get-MsolUserDeviceComplianceStatus.ps1: $u de usuario: exportar</span><span class="sxs-lookup"><span data-stu-id="a4ef5-221">.\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export</span></span>

<span data-ttu-id="a4ef5-222">La información se exporta al escritorio de Windows como un archivo CSV.</span><span class="sxs-lookup"><span data-stu-id="a4ef5-222">The information is exported to your Windows Desktop as a CSV file.</span></span> <span data-ttu-id="a4ef5-223">Puede usar parámetros adicionales para especificar el nombre de archivo y la ruta de acceso del archivo CSV.</span><span class="sxs-lookup"><span data-stu-id="a4ef5-223">You can use additional parameters to specify the file name and path of the CSV.</span></span>

## <a name="run-the-script-to-get-device-information-for-a-group-of-users"></a><span data-ttu-id="a4ef5-224">Ejecutar el script para obtener información del dispositivo para un grupo de usuarios</span><span class="sxs-lookup"><span data-stu-id="a4ef5-224">Run the script to get device information for a group of users</span></span>

1. <span data-ttu-id="a4ef5-225">Abra el Módulo Microsoft Azure Active Directory para Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a4ef5-225">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>
    
2. <span data-ttu-id="a4ef5-226">Vaya a la carpeta en la que guardó el script.</span><span class="sxs-lookup"><span data-stu-id="a4ef5-226">Go to the folder where you saved the script.</span></span> <span data-ttu-id="a4ef5-227">Por ejemplo, si lo guardó en C:\PS-Scripts, ejecute el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="a4ef5-227">For example, if you saved it to C:\PS-Scripts, run the following command.</span></span>   

    <span data-ttu-id="a4ef5-228">CD C:\PS-Scripts</span><span class="sxs-lookup"><span data-stu-id="a4ef5-228">cd C:\PS-Scripts</span></span>

3. <span data-ttu-id="a4ef5-229">Ejecute el siguiente comando para identificar el grupo para el que desea obtener detalles del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a4ef5-229">Run the following command to identify the group you want to get device details for.</span></span> <span data-ttu-id="a4ef5-230">En este ejemplo se obtienen los detalles de los usuarios en el grupo FinanceStaff.</span><span class="sxs-lookup"><span data-stu-id="a4ef5-230">This example gets details for users in the FinanceStaff group.</span></span> 

    <span data-ttu-id="a4ef5-231">$u = Get-MsolGroupMember-SearchString "FinanceStaff" | % {Get-MsolUser-ObjectId $ _. ObjectId</span><span class="sxs-lookup"><span data-stu-id="a4ef5-231">$u = Get-MsolGroupMember -SearchString "FinanceStaff" | % { Get-MsolUser -ObjectId $_.ObjectId }</span></span>

4. <span data-ttu-id="a4ef5-232">Ejecute el siguiente comando para iniciar el script.</span><span class="sxs-lookup"><span data-stu-id="a4ef5-232">Run the following command to initiate the script.</span></span>   

    <span data-ttu-id="a4ef5-233">.\Get-MsolUserDeviceComplianceStatus.ps1: $u de usuario: exportar</span><span class="sxs-lookup"><span data-stu-id="a4ef5-233">.\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export</span></span>

<span data-ttu-id="a4ef5-234">La información se exporta al escritorio de Windows como un archivo CSV.</span><span class="sxs-lookup"><span data-stu-id="a4ef5-234">The information is exported to your Windows Desktop as a CSV file.</span></span> <span data-ttu-id="a4ef5-235">Puede usar parámetros adicionales para especificar el nombre de archivo y la ruta de acceso del archivo CSV.</span><span class="sxs-lookup"><span data-stu-id="a4ef5-235">You can use additional parameters to specify the file name and path of the CSV.</span></span>

## <a name="related-topics"></a><span data-ttu-id="a4ef5-236">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="a4ef5-236">Related topics</span></span>

[<span data-ttu-id="a4ef5-237">Microsoft Connect se ha retirado</span><span class="sxs-lookup"><span data-stu-id="a4ef5-237">Microsoft Connect Has Been Retired</span></span>](https://docs.microsoft.com/collaborate/connect-redirect)

[<span data-ttu-id="a4ef5-238">Introducción a la movilidad y la seguridad básicas</span><span class="sxs-lookup"><span data-stu-id="a4ef5-238">Overview of Basic Mobility and Security</span></span>](overview-of-basic-mobility-and-security-for-microsoft-365.md)

[<span data-ttu-id="a4ef5-239">Get-MsolDevice</span><span class="sxs-lookup"><span data-stu-id="a4ef5-239">Get-MsolDevice</span></span>](https://go.microsoft.com/fwlink/?linkid=841721)