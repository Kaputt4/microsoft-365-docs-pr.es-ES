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
ms.openlocfilehash: d34263ee215c568834034f2735bb69d9cef9ac6d
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2020
ms.locfileid: "47430307"
---
# <a name="get-details-about-basic-mobility-and-security-managed-devices"></a><span data-ttu-id="15821-103">Obtener información sobre la movilidad básica y los dispositivos administrados de seguridad</span><span class="sxs-lookup"><span data-stu-id="15821-103">Get details about Basic Mobility and Security managed devices</span></span>

<span data-ttu-id="15821-104">En este artículo se muestra cómo usar Windows PowerShell para obtener detalles sobre los dispositivos de la organización que ha configurado para la movilidad y la seguridad básicos.</span><span class="sxs-lookup"><span data-stu-id="15821-104">This article shows you how to use Windows PowerShell to get details about the devices in your organization that you set up for Basic Mobility and Security.</span></span>

<span data-ttu-id="15821-105">Este es un desglose de los detalles de dispositivos disponibles.</span><span class="sxs-lookup"><span data-stu-id="15821-105">Here's a breakdown for the device details available to you.</span></span>

|<span data-ttu-id="15821-106">**Detalle**</span><span class="sxs-lookup"><span data-stu-id="15821-106">**Detail**</span></span>|<span data-ttu-id="15821-107">**Qué buscar en PowerShell**</span><span class="sxs-lookup"><span data-stu-id="15821-107">**What to look for in PowerShell**</span></span>|
|:----------------|:------------------------------------------------------------------------------|
|<span data-ttu-id="15821-108">El dispositivo está inscrito en la movilidad y la seguridad básicas.</span><span class="sxs-lookup"><span data-stu-id="15821-108">Device is enrolled in Basic Mobility and Security.</span></span> <span data-ttu-id="15821-109">Para obtener más información, consulte [inscribir un dispositivo móvil usando la movilidad y la seguridad básicas](enroll-your-mobile-device.md)</span><span class="sxs-lookup"><span data-stu-id="15821-109">For more info, see [Enroll your mobile device using Basic Mobility and Security](enroll-your-mobile-device.md)</span></span>|<span data-ttu-id="15821-110">El valor del parámetro *isManaged*   es:</span><span class="sxs-lookup"><span data-stu-id="15821-110">The value of the *isManaged* parameter is:</span></span><br/><span data-ttu-id="15821-111">**True**= el dispositivo está inscrito.</span><span class="sxs-lookup"><span data-stu-id="15821-111">**True**= device is enrolled.</span></span><br/><span data-ttu-id="15821-112">**False**= no se inscribe el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="15821-112">**False**= device is not enrolled.</span></span> |
|<span data-ttu-id="15821-113">El dispositivo es compatible con las directivas de seguridad del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="15821-113">Device is compliant with your device security policies.</span></span> <span data-ttu-id="15821-114">Para obtener más información, consulte [crear directivas de seguridad de dispositivos](create-device-security-policies.md) .</span><span class="sxs-lookup"><span data-stu-id="15821-114">For more info, see [Create device security policies](create-device-security-policies.md)</span></span>|<span data-ttu-id="15821-115">El valor del parámetro *isCompliant*   es:</span><span class="sxs-lookup"><span data-stu-id="15821-115">The value of the *isCompliant* parameter is:</span></span><br/><span data-ttu-id="15821-116">**True**   = el dispositivo es compatible con las directivas.</span><span class="sxs-lookup"><span data-stu-id="15821-116">**True** = device is compliant with policies.</span></span><br/><span data-ttu-id="15821-117">**False**   = el dispositivo no es compatible con las directivas.</span><span class="sxs-lookup"><span data-stu-id="15821-117">**False** = device is not compliant with policies.</span></span>|

:::image type="content" source="../../media/basic-mobility-security/bms-7-powershell-parameters.png" alt-text="Parámetros básicos de PowerShell de seguridad y movilidad":::

>[!NOTE]
><span data-ttu-id="15821-119">Los comandos y los scripts de este artículo también devuelven detalles sobre los dispositivos administrados por [Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune).</span><span class="sxs-lookup"><span data-stu-id="15821-119">The commands and scripts in this article also return details about any devices managed by [Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="15821-120">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="15821-120">Before you begin</span></span>

<span data-ttu-id="15821-121">Hay algunas cosas que debe configurar para ejecutar los comandos y scripts descritos en este artículo.</span><span class="sxs-lookup"><span data-stu-id="15821-121">There are a few things you need to set up to run the commands and scripts described in this article.</span></span>

### <a name="step-1-download-and-install-the-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="15821-122">Paso 1: descargar e instalar el módulo de Azure Active Directory para Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="15821-122">Step 1: Download and install the Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="15821-123">Para obtener más información sobre estos pasos, consulte [conectarse a Microsoft 365 con PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="15821-123">For more info on these steps, see [Connect to Microsoft 365 with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell).</span></span>

1. <span data-ttu-id="15821-124">Vaya a [Microsoft Online Services-ayudante para el inicio de sesión para profesionales de ti RTWl](https://www.microsoft.com/download/details.aspx?id=41950)   y seleccione  **descargar para el ayudante para el inicio de sesión de Microsoft Online Services**.</span><span class="sxs-lookup"><span data-stu-id="15821-124">Go to [Microsoft Online Services Sign-In Assistant for IT Professionals RTWl](https://www.microsoft.com/download/details.aspx?id=41950) and select  **Download for Microsoft Online Services Sign-in Assistant**.</span></span>   

2. <span data-ttu-id="15821-125">Instale el Módulo Microsoft Azure Active Directory para Windows PowerShell siguiendo estos pasos:</span><span class="sxs-lookup"><span data-stu-id="15821-125">Install the Microsoft Azure Active Directory Module for Windows PowerShell with these steps:</span></span>   

    1. <span data-ttu-id="15821-126">Abra un símbolo del sistema de PowerShell con permisos de administrador.</span><span class="sxs-lookup"><span data-stu-id="15821-126">Open an administrator-level PowerShell command prompt.</span></span>  

    2. <span data-ttu-id="15821-127">Ejecute el comando Install-Module MSOnline.</span><span class="sxs-lookup"><span data-stu-id="15821-127">Run the Install-Module MSOnline command.</span></span>
    
    3. <span data-ttu-id="15821-128">Si se le pide que instale el proveedor de NuGet, escriba Y y presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="15821-128">If prompted to install the NuGet provider, type Y and press ENTER.</span></span>   

    4. <span data-ttu-id="15821-129">Si se le pide que instale el módulo desde PSGallery, escriba Y y presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="15821-129">If prompted to install the module from PSGallery, type Y and press ENTER.</span></span>   

    5. <span data-ttu-id="15821-130">Después de la instalación, cierre la ventana de comandos de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="15821-130">After installation, close the PowerShell command window.</span></span>
    
### <a name="step-2-connect-to-your-microsoft-365-subscription"></a><span data-ttu-id="15821-131">Paso 2: conectarse a la suscripción de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="15821-131">Step 2: Connect to your Microsoft 365 subscription</span></span>

1. <span data-ttu-id="15821-132">En el módulo Windows Azure Active Directory para Windows PowerShell, ejecute el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="15821-132">In the Windows Azure Active Directory Module for Windows PowerShell, run the following command.</span></span>  

    <span data-ttu-id="15821-133">$UserCredential = Get-Credential</span><span class="sxs-lookup"><span data-stu-id="15821-133">$UserCredential = Get-Credential</span></span>

2. <span data-ttu-id="15821-134">En el cuadro de diálogo solicitud de credenciales para Windows PowerShell, escriba el nombre de usuario y la contraseña de su cuenta de administrador global de Microsoft 365 y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="15821-134">In the Windows PowerShell Credential Request dialog box, type the user name and password for your Microsoft 365 global admin account, and then select **OK**.</span></span>
    
3. <span data-ttu-id="15821-135">Ejecute el comando siguiente.</span><span class="sxs-lookup"><span data-stu-id="15821-135">Run the following command.</span></span>
    
    <span data-ttu-id="15821-136">$UserCredential Connect-MsolService-Credential</span><span class="sxs-lookup"><span data-stu-id="15821-136">Connect-MsolService -Credential $UserCredential</span></span>

### <a name="step-3-make-sure-youre-able-to-run-powershell-scripts"></a><span data-ttu-id="15821-137">Paso 3: Asegúrese de que puede ejecutar scripts de PowerShell</span><span class="sxs-lookup"><span data-stu-id="15821-137">Step 3: Make sure you’re able to run PowerShell scripts</span></span>

>[!NOTE]
><span data-ttu-id="15821-138">Puede omitir este paso si ya está configurado para ejecutar scripts de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="15821-138">You can skip this step if you’re already set up to run PowerShell scripts.</span></span>

<span data-ttu-id="15821-139">Para ejecutar el script de Get-MsolUserDeviceComplianceStatus.ps1, debe habilitar la ejecución de scripts de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="15821-139">To run the Get-MsolUserDeviceComplianceStatus.ps1 script, you need to enable the running of PowerShell scripts.</span></span>

1. <span data-ttu-id="15821-140">En el escritorio de Windows, seleccione **Inicio**y, a continuación, escriba Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="15821-140">From your Windows Desktop, select **Start**, and then type Windows PowerShell.</span></span> <span data-ttu-id="15821-141">Haga clic con el botón secundario en Windows PowerShell y seleccione **Ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="15821-141">Right-click Windows PowerShell, and then select **Run as administrator**.</span></span>

2. <span data-ttu-id="15821-142">Ejecute el comando siguiente.</span><span class="sxs-lookup"><span data-stu-id="15821-142">Run the following command.</span></span>
    
    <span data-ttu-id="15821-143">Set-ExecutionPolicy RemoteSigned</span><span class="sxs-lookup"><span data-stu-id="15821-143">Set-ExecutionPolicy  RemoteSigned</span></span>

3. <span data-ttu-id="15821-144">Cuando se le solicite, escriba s y, a continuación, presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="15821-144">When prompted, type Y and then press Enter.</span></span>
    
<span data-ttu-id="15821-145">**Ejecute el cmdlet Get-MsolDevice para mostrar los detalles de todos los dispositivos de su organización.**</span><span class="sxs-lookup"><span data-stu-id="15821-145">**Run the Get-MsolDevice cmdlet to display details for all devices in your organization**</span></span>

1. <span data-ttu-id="15821-146">Abra el Módulo Microsoft Azure Active Directory para Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="15821-146">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>  

2. <span data-ttu-id="15821-147">Ejecute el comando siguiente.</span><span class="sxs-lookup"><span data-stu-id="15821-147">Run the following command.</span></span>
    
    <span data-ttu-id="15821-148">Get-MsolDevice-All-ReturnRegisteredOwners | Where-Object {$ _. RegisteredOwners. Count-gt 0}</span><span class="sxs-lookup"><span data-stu-id="15821-148">Get-MsolDevice -All -ReturnRegisteredOwners | Where-Object {$_.RegisteredOwners.Count -gt 0}</span></span>

<span data-ttu-id="15821-149">Para obtener más ejemplos, consulte  [Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=841721).</span><span class="sxs-lookup"><span data-stu-id="15821-149">For more examples, see  [Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=841721).</span></span>

## <a name="run-a-script-to-get-device-details"></a><span data-ttu-id="15821-150">Ejecutar un script para obtener detalles del dispositivo</span><span class="sxs-lookup"><span data-stu-id="15821-150">Run a script to get device details</span></span>

<span data-ttu-id="15821-151">En primer lugar, guarde el script en el equipo.</span><span class="sxs-lookup"><span data-stu-id="15821-151">First, save the script to your computer.</span></span>

1. <span data-ttu-id="15821-152">Copie y pegue el texto siguiente en el Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="15821-152">Copy and paste the following text into Notepad.</span></span>  

2.  <span data-ttu-id="15821-153">parámetro</span><span class="sxs-lookup"><span data-stu-id="15821-153">param (</span></span>
    

3.  <span data-ttu-id="15821-154">[PSObject []] $users = @ (),</span><span class="sxs-lookup"><span data-stu-id="15821-154">[PSObject[]]$users = @(),</span></span>
    

4.  <span data-ttu-id="15821-155">[Modificador] $export,</span><span class="sxs-lookup"><span data-stu-id="15821-155">[Switch]$export,</span></span>
    

5.  <span data-ttu-id="15821-156">[String] $exportFileName = "UserDeviceComplianceStatus_" + (get-Date-Format "yyMMdd_HHMMss") + ". csv",</span><span class="sxs-lookup"><span data-stu-id="15821-156">[String]$exportFileName = "UserDeviceComplianceStatus_" + (Get-Date -Format "yyMMdd_HHMMss") + ".csv",</span></span>
    

6.  <span data-ttu-id="15821-157">[String] $exportPath = [Environment]:: GetFolderPath ("Desktop")</span><span class="sxs-lookup"><span data-stu-id="15821-157">[String]$exportPath = [Environment]::GetFolderPath("Desktop")</span></span>
    

7.  <span data-ttu-id="15821-158">)</span><span class="sxs-lookup"><span data-stu-id="15821-158">)</span></span>
    

9.  <span data-ttu-id="15821-159">[System. Collections. IDictionary] $script: Schema = @ {</span><span class="sxs-lookup"><span data-stu-id="15821-159">[System.Collections.IDictionary]$script:schema = @{</span></span>
    

11.  <span data-ttu-id="15821-160">DeviceId = ' '</span><span class="sxs-lookup"><span data-stu-id="15821-160">DeviceId = ''</span></span>
    

12.  <span data-ttu-id="15821-161">DeviceOSType = ' '</span><span class="sxs-lookup"><span data-stu-id="15821-161">DeviceOSType = ''</span></span>
    

13.  <span data-ttu-id="15821-162">DeviceOSVersion = ' '</span><span class="sxs-lookup"><span data-stu-id="15821-162">DeviceOSVersion = ''</span></span>
    

14.  <span data-ttu-id="15821-163">DeviceTrustLevel = ' '</span><span class="sxs-lookup"><span data-stu-id="15821-163">DeviceTrustLevel = ''</span></span>
    

15.  <span data-ttu-id="15821-164">DisplayName = ' '</span><span class="sxs-lookup"><span data-stu-id="15821-164">DisplayName = ''</span></span>
    

16.  <span data-ttu-id="15821-165">IsCompliant = ' '</span><span class="sxs-lookup"><span data-stu-id="15821-165">IsCompliant = ''</span></span>
    

17.  <span data-ttu-id="15821-166">IsManaged = ' '</span><span class="sxs-lookup"><span data-stu-id="15821-166">IsManaged = ''</span></span>
    

18.  <span data-ttu-id="15821-167">ApproximateLastLogonTimestamp = ' '</span><span class="sxs-lookup"><span data-stu-id="15821-167">ApproximateLastLogonTimestamp = ''</span></span>
    

19.  <span data-ttu-id="15821-168">DeviceObjectId = ' '</span><span class="sxs-lookup"><span data-stu-id="15821-168">DeviceObjectId = ''</span></span>
    

20.  <span data-ttu-id="15821-169">RegisteredOwnerUpn = ' '</span><span class="sxs-lookup"><span data-stu-id="15821-169">RegisteredOwnerUpn = ''</span></span>
    

21.  <span data-ttu-id="15821-170">RegisteredOwnerObjectId = ' '</span><span class="sxs-lookup"><span data-stu-id="15821-170">RegisteredOwnerObjectId = ''</span></span>
    

22.  <span data-ttu-id="15821-171">RegisteredOwnerDisplayName = ' '</span><span class="sxs-lookup"><span data-stu-id="15821-171">RegisteredOwnerDisplayName = ''</span></span>
    

23.  <span data-ttu-id="15821-172">}</span><span class="sxs-lookup"><span data-stu-id="15821-172">}</span></span>
    

25.  <span data-ttu-id="15821-173">función createResultObject</span><span class="sxs-lookup"><span data-stu-id="15821-173">function createResultObject</span></span>
    

26.  <span data-ttu-id="15821-174">{</span><span class="sxs-lookup"><span data-stu-id="15821-174">{</span></span>
    

28.  <span data-ttu-id="15821-175">[PSObject] $resultObject = New-Object-TypeName PSObject-Property $script: Schema</span><span class="sxs-lookup"><span data-stu-id="15821-175">[PSObject]$resultObject = New-Object -TypeName PSObject -Property $script:schema</span></span>
    

30.  <span data-ttu-id="15821-176">devolver $resultObject</span><span class="sxs-lookup"><span data-stu-id="15821-176">return $resultObject</span></span>
    

31.  <span data-ttu-id="15821-177">}</span><span class="sxs-lookup"><span data-stu-id="15821-177">}</span></span>
    

33.  <span data-ttu-id="15821-178">If ($users. Count-EQ 0)</span><span class="sxs-lookup"><span data-stu-id="15821-178">If ($users.Count -eq 0)</span></span>
    

34.  <span data-ttu-id="15821-179">{</span><span class="sxs-lookup"><span data-stu-id="15821-179">{</span></span>
    

35.  <span data-ttu-id="15821-180">$users = Get-MsolUser</span><span class="sxs-lookup"><span data-stu-id="15821-180">$users = Get-MsolUser</span></span>
    

36.  <span data-ttu-id="15821-181">}</span><span class="sxs-lookup"><span data-stu-id="15821-181">}</span></span>
    

38.  <span data-ttu-id="15821-182">[PSObject []] $result = foreach ($u en $users)</span><span class="sxs-lookup"><span data-stu-id="15821-182">[PSObject[]]$result = foreach ($u in $users)</span></span>
    

39.  <span data-ttu-id="15821-183">{</span><span class="sxs-lookup"><span data-stu-id="15821-183">{</span></span>
    

41.  <span data-ttu-id="15821-184">[PSObject] $devices = Get-msoldevice-RegisteredOwnerUpn $u. UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="15821-184">[PSObject]$devices = get-msoldevice -RegisteredOwnerUpn $u.UserPrincipalName</span></span>
    

42.  <span data-ttu-id="15821-185">foreach ($d en $devices)</span><span class="sxs-lookup"><span data-stu-id="15821-185">foreach ($d in $devices)</span></span>
    

43.  <span data-ttu-id="15821-186">{</span><span class="sxs-lookup"><span data-stu-id="15821-186">{</span></span>
    

44.  <span data-ttu-id="15821-187">[PSObject] $deviceResult = createResultObject</span><span class="sxs-lookup"><span data-stu-id="15821-187">[PSObject]$deviceResult = createResultObject</span></span>
    

45.  <span data-ttu-id="15821-188">$deviceResult. DeviceId = $d. DeviceId</span><span class="sxs-lookup"><span data-stu-id="15821-188">$deviceResult.DeviceId = $d.DeviceId</span></span>
    

46.  <span data-ttu-id="15821-189">$deviceResult. DeviceOSType = $d. DeviceOSType</span><span class="sxs-lookup"><span data-stu-id="15821-189">$deviceResult.DeviceOSType = $d.DeviceOSType</span></span>
    

47.  <span data-ttu-id="15821-190">$deviceResult. DeviceOSVersion = $d. DeviceOSVersion</span><span class="sxs-lookup"><span data-stu-id="15821-190">$deviceResult.DeviceOSVersion = $d.DeviceOSVersion</span></span>
    

48.  <span data-ttu-id="15821-191">$deviceResult. DeviceTrustLevel = $d. DeviceTrustLevel</span><span class="sxs-lookup"><span data-stu-id="15821-191">$deviceResult.DeviceTrustLevel = $d.DeviceTrustLevel</span></span>
    

49.  <span data-ttu-id="15821-192">$deviceResult. DisplayName = $d. DisplayName</span><span class="sxs-lookup"><span data-stu-id="15821-192">$deviceResult.DisplayName = $d.DisplayName</span></span>
    

50.  <span data-ttu-id="15821-193">$deviceResult. IsCompliant = $d. GraphDeviceObject. IsCompliant</span><span class="sxs-lookup"><span data-stu-id="15821-193">$deviceResult.IsCompliant = $d.GraphDeviceObject.IsCompliant</span></span>
    

51.  <span data-ttu-id="15821-194">$deviceResult. IsManaged = $d. GraphDeviceObject. IsManaged</span><span class="sxs-lookup"><span data-stu-id="15821-194">$deviceResult.IsManaged = $d.GraphDeviceObject.IsManaged</span></span>
    

52.  <span data-ttu-id="15821-195">$deviceResult. DeviceObjectId = $d. ObjectId</span><span class="sxs-lookup"><span data-stu-id="15821-195">$deviceResult.DeviceObjectId = $d.ObjectId</span></span>
    

53.  <span data-ttu-id="15821-196">$deviceResult. RegisteredOwnerUpn = $u. UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="15821-196">$deviceResult.RegisteredOwnerUpn = $u.UserPrincipalName</span></span>
    

54.  <span data-ttu-id="15821-197">$deviceResult. RegisteredOwnerObjectId = $u. ObjectId</span><span class="sxs-lookup"><span data-stu-id="15821-197">$deviceResult.RegisteredOwnerObjectId = $u.ObjectId</span></span>
    

55.  <span data-ttu-id="15821-198">$deviceResult. RegisteredOwnerDisplayName = $u. DisplayName</span><span class="sxs-lookup"><span data-stu-id="15821-198">$deviceResult.RegisteredOwnerDisplayName = $u.DisplayName</span></span>
    

56.  <span data-ttu-id="15821-199">$deviceResult. ApproximateLastLogonTimestamp = $d. ApproximateLastLogonTimestamp</span><span class="sxs-lookup"><span data-stu-id="15821-199">$deviceResult.ApproximateLastLogonTimestamp = $d.ApproximateLastLogonTimestamp</span></span>
    

58.  <span data-ttu-id="15821-200">$deviceResult</span><span class="sxs-lookup"><span data-stu-id="15821-200">$deviceResult</span></span>
    

59.  <span data-ttu-id="15821-201">}</span><span class="sxs-lookup"><span data-stu-id="15821-201">}</span></span>
    

61.  <span data-ttu-id="15821-202">}</span><span class="sxs-lookup"><span data-stu-id="15821-202">}</span></span>
    

63.  <span data-ttu-id="15821-203">If ($export)</span><span class="sxs-lookup"><span data-stu-id="15821-203">If ($export)</span></span>
    

64.  <span data-ttu-id="15821-204">{</span><span class="sxs-lookup"><span data-stu-id="15821-204">{</span></span>
    

65.  <span data-ttu-id="15821-205">$result | Export-CSV-Path ($exportPath + " \" + $exportFileName)-NoTypeInformation</span><span class="sxs-lookup"><span data-stu-id="15821-205">$result | Export-Csv -path ($exportPath + "\" + $exportFileName) -NoTypeInformation</span></span>
    

66.  <span data-ttu-id="15821-206">}</span><span class="sxs-lookup"><span data-stu-id="15821-206">}</span></span>
    

67.  <span data-ttu-id="15821-207">Else</span><span class="sxs-lookup"><span data-stu-id="15821-207">Else</span></span>
    

68.  <span data-ttu-id="15821-208">{</span><span class="sxs-lookup"><span data-stu-id="15821-208">{</span></span>
    

69.  <span data-ttu-id="15821-209">$result</span><span class="sxs-lookup"><span data-stu-id="15821-209">$result</span></span>
    

70.  <span data-ttu-id="15821-210">}</span><span class="sxs-lookup"><span data-stu-id="15821-210">}</span></span>
    

71.  <span data-ttu-id="15821-211">Guárdelo como un archivo de script de Windows PowerShell mediante la extensión de archivo. ps1; por ejemplo, Get-MsolUserDeviceComplianceStatus.ps1.</span><span class="sxs-lookup"><span data-stu-id="15821-211">Save it as a Windows PowerShell script file by using the file extension .ps1; for example, Get-MsolUserDeviceComplianceStatus.ps1.</span></span>   

## <a name="run-the-script-to-get-device-information-for-a-single-user-account"></a><span data-ttu-id="15821-212">Ejecutar el script para obtener información del dispositivo para una sola cuenta de usuario</span><span class="sxs-lookup"><span data-stu-id="15821-212">Run the script to get device information for a single user account</span></span>

1. <span data-ttu-id="15821-213">Abra el Módulo Microsoft Azure Active Directory para Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="15821-213">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>
    
2. <span data-ttu-id="15821-214">Vaya a la carpeta en la que guardó el script.</span><span class="sxs-lookup"><span data-stu-id="15821-214">Go to the folder where you saved the script.</span></span> <span data-ttu-id="15821-215">Por ejemplo, si lo guardó en C:\PS-Scripts, ejecute el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="15821-215">For example, if you saved it to C:\PS-Scripts, run the following command.</span></span>
    
    <span data-ttu-id="15821-216">CD C:\PS-Scripts</span><span class="sxs-lookup"><span data-stu-id="15821-216">cd C:\PS-Scripts</span></span>

3. <span data-ttu-id="15821-217">Ejecute el siguiente comando para identificar el usuario para el que desea obtener detalles del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="15821-217">Run the following command to identify the user you want to get device details for.</span></span> <span data-ttu-id="15821-218">En este ejemplo se obtienen los detalles de bar@example.com.</span><span class="sxs-lookup"><span data-stu-id="15821-218">This example gets details for bar@example.com.</span></span>
    
    <span data-ttu-id="15821-219">$u = Get-MsolUser-UserPrincipalName bar@example.com</span><span class="sxs-lookup"><span data-stu-id="15821-219">$u = Get-MsolUser -UserPrincipalName bar@example.com</span></span>

4. <span data-ttu-id="15821-220">Ejecute el siguiente comando para iniciar el script.</span><span class="sxs-lookup"><span data-stu-id="15821-220">Run the following command to initiate the script.</span></span>

    <span data-ttu-id="15821-221">.\Get-MsolUserDeviceComplianceStatus.ps1: $u de usuario: exportar</span><span class="sxs-lookup"><span data-stu-id="15821-221">.\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export</span></span>

<span data-ttu-id="15821-222">La información se exporta al escritorio de Windows como un archivo CSV.</span><span class="sxs-lookup"><span data-stu-id="15821-222">The information is exported to your Windows Desktop as a CSV file.</span></span> <span data-ttu-id="15821-223">Puede usar parámetros adicionales para especificar el nombre de archivo y la ruta de acceso del archivo CSV.</span><span class="sxs-lookup"><span data-stu-id="15821-223">You can use additional parameters to specify the file name and path of the CSV.</span></span>

## <a name="run-the-script-to-get-device-information-for-a-group-of-users"></a><span data-ttu-id="15821-224">Ejecutar el script para obtener información del dispositivo para un grupo de usuarios</span><span class="sxs-lookup"><span data-stu-id="15821-224">Run the script to get device information for a group of users</span></span>

1. <span data-ttu-id="15821-225">Abra el Módulo Microsoft Azure Active Directory para Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="15821-225">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>
    
2. <span data-ttu-id="15821-226">Vaya a la carpeta en la que guardó el script.</span><span class="sxs-lookup"><span data-stu-id="15821-226">Go to the folder where you saved the script.</span></span> <span data-ttu-id="15821-227">Por ejemplo, si lo guardó en C:\PS-Scripts, ejecute el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="15821-227">For example, if you saved it to C:\PS-Scripts, run the following command.</span></span>   

    <span data-ttu-id="15821-228">CD C:\PS-Scripts</span><span class="sxs-lookup"><span data-stu-id="15821-228">cd C:\PS-Scripts</span></span>

3. <span data-ttu-id="15821-229">Ejecute el siguiente comando para identificar el grupo para el que desea obtener detalles del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="15821-229">Run the following command to identify the group you want to get device details for.</span></span> <span data-ttu-id="15821-230">En este ejemplo se obtienen los detalles de los usuarios en el grupo FinanceStaff.</span><span class="sxs-lookup"><span data-stu-id="15821-230">This example gets details for users in the FinanceStaff group.</span></span> 

    <span data-ttu-id="15821-231">$u = Get-MsolGroupMember-SearchString "FinanceStaff" | % {Get-MsolUser-ObjectId $ _. ObjectId</span><span class="sxs-lookup"><span data-stu-id="15821-231">$u = Get-MsolGroupMember -SearchString "FinanceStaff" | % { Get-MsolUser -ObjectId $_.ObjectId }</span></span>

4. <span data-ttu-id="15821-232">Ejecute el siguiente comando para iniciar el script.</span><span class="sxs-lookup"><span data-stu-id="15821-232">Run the following command to initiate the script.</span></span>   

    <span data-ttu-id="15821-233">.\Get-MsolUserDeviceComplianceStatus.ps1: $u de usuario: exportar</span><span class="sxs-lookup"><span data-stu-id="15821-233">.\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export</span></span>

<span data-ttu-id="15821-234">La información se exporta al escritorio de Windows como un archivo CSV.</span><span class="sxs-lookup"><span data-stu-id="15821-234">The information is exported to your Windows Desktop as a CSV file.</span></span> <span data-ttu-id="15821-235">Puede usar parámetros adicionales para especificar el nombre de archivo y la ruta de acceso del archivo CSV.</span><span class="sxs-lookup"><span data-stu-id="15821-235">You can use additional parameters to specify the file name and path of the CSV.</span></span>

## <a name="related-topics"></a><span data-ttu-id="15821-236">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="15821-236">Related topics</span></span>

[<span data-ttu-id="15821-237">Microsoft Connect se ha retirado</span><span class="sxs-lookup"><span data-stu-id="15821-237">Microsoft Connect Has Been Retired</span></span>](https://docs.microsoft.com/collaborate/connect-redirect)

[<span data-ttu-id="15821-238">Introducción a la movilidad y la seguridad básicas</span><span class="sxs-lookup"><span data-stu-id="15821-238">Overview of Basic Mobility and Security</span></span>](overview.md)

[<span data-ttu-id="15821-239">Get-MsolDevice</span><span class="sxs-lookup"><span data-stu-id="15821-239">Get-MsolDevice</span></span>](https://go.microsoft.com/fwlink/?linkid=841721)