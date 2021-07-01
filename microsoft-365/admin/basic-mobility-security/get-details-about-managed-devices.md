---
title: Obtener detalles sobre dispositivos administrados de movilidad básica y seguridad
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
description: Usa Windows PowerShell para obtener detalles sobre los dispositivos de movilidad y seguridad básicas de la organización.
ms.openlocfilehash: 2edee1b08f137d3e4f977b4d6800c1b0fc0e0473
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228176"
---
# <a name="get-details-about-basic-mobility-and-security-managed-devices"></a><span data-ttu-id="ff755-103">Obtener detalles sobre dispositivos administrados de movilidad básica y seguridad</span><span class="sxs-lookup"><span data-stu-id="ff755-103">Get details about Basic Mobility and Security managed devices</span></span>

<span data-ttu-id="ff755-104">En este artículo se muestra cómo usar Windows PowerShell para obtener detalles sobre los dispositivos de la organización configurados para movilidad y seguridad básicas.</span><span class="sxs-lookup"><span data-stu-id="ff755-104">This article shows you how to use Windows PowerShell to get details about the devices in your organization that you set up for Basic Mobility and Security.</span></span>

<span data-ttu-id="ff755-105">Este es un desglose de los detalles del dispositivo disponibles.</span><span class="sxs-lookup"><span data-stu-id="ff755-105">Here's a breakdown for the device details available to you.</span></span>

|<span data-ttu-id="ff755-106">**Detalle**</span><span class="sxs-lookup"><span data-stu-id="ff755-106">**Detail**</span></span>|<span data-ttu-id="ff755-107">**Qué buscar en PowerShell**</span><span class="sxs-lookup"><span data-stu-id="ff755-107">**What to look for in PowerShell**</span></span>|
|:----------------|:------------------------------------------------------------------------------|
|<span data-ttu-id="ff755-108">El dispositivo está inscrito en Movilidad y seguridad básicas.</span><span class="sxs-lookup"><span data-stu-id="ff755-108">Device is enrolled in Basic Mobility and Security.</span></span> <span data-ttu-id="ff755-109">Para obtener más información, consulta [Inscribir el dispositivo móvil con Movilidad y seguridad básicas](enroll-your-mobile-device.md)</span><span class="sxs-lookup"><span data-stu-id="ff755-109">For more info, see [Enroll your mobile device using Basic Mobility and Security](enroll-your-mobile-device.md)</span></span>|<span data-ttu-id="ff755-110">El valor del *parámetro isManaged*   es:</span><span class="sxs-lookup"><span data-stu-id="ff755-110">The value of the *isManaged* parameter is:</span></span><br/><span data-ttu-id="ff755-111">**True**= el dispositivo está inscrito.</span><span class="sxs-lookup"><span data-stu-id="ff755-111">**True**= device is enrolled.</span></span><br/><span data-ttu-id="ff755-112">**False**= el dispositivo no está inscrito.</span><span class="sxs-lookup"><span data-stu-id="ff755-112">**False**= device is not enrolled.</span></span> |
|<span data-ttu-id="ff755-113">El dispositivo es compatible con las directivas de seguridad del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ff755-113">Device is compliant with your device security policies.</span></span> <span data-ttu-id="ff755-114">Para obtener más información, consulta [Crear directivas de seguridad de dispositivos](create-device-security-policies.md)</span><span class="sxs-lookup"><span data-stu-id="ff755-114">For more info, see [Create device security policies](create-device-security-policies.md)</span></span>|<span data-ttu-id="ff755-115">El valor del *parámetro isCompliant*   es:</span><span class="sxs-lookup"><span data-stu-id="ff755-115">The value of the *isCompliant* parameter is:</span></span><br/><span data-ttu-id="ff755-116">**True**   = el dispositivo es compatible con las directivas.</span><span class="sxs-lookup"><span data-stu-id="ff755-116">**True** = device is compliant with policies.</span></span><br/><span data-ttu-id="ff755-117">**False**   = el dispositivo no es compatible con las directivas.</span><span class="sxs-lookup"><span data-stu-id="ff755-117">**False** = device is not compliant with policies.</span></span>|

:::image type="content" source="../../media/basic-mobility-security/bms-7-powershell-parameters.png" alt-text="Parámetros básicos de PowerShell de movilidad y seguridad":::

> [!NOTE]
> <span data-ttu-id="ff755-119">Los comandos y scripts de este artículo también devuelven detalles sobre los dispositivos administrados [por Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune).</span><span class="sxs-lookup"><span data-stu-id="ff755-119">The commands and scripts in this article also return details about any devices managed by [Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="ff755-120">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="ff755-120">Before you begin</span></span>

<span data-ttu-id="ff755-121">Hay algunas cosas que debe configurar para ejecutar los comandos y scripts descritos en este artículo.</span><span class="sxs-lookup"><span data-stu-id="ff755-121">There are a few things you need to set up to run the commands and scripts described in this article.</span></span>

### <a name="step-1-download-and-install-the-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="ff755-122">Paso 1: Descargar e instalar el módulo Azure Active Directory para Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ff755-122">Step 1: Download and install the Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="ff755-123">Para obtener más información sobre estos pasos, vea [Conectar para Microsoft 365 con PowerShell](/office365/enterprise/powershell/connect-to-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="ff755-123">For more info on these steps, see [Connect to Microsoft 365 with PowerShell](/office365/enterprise/powershell/connect-to-office-365-powershell).</span></span>

1. <span data-ttu-id="ff755-124">Vaya a Microsoft Online Services Sign-In asistente para profesionales de [TI RTWl](https://download.microsoft.com/download/7/1/E/71EF1D05-A42C-4A1F-8162-96494B5E615C/msoidcli_32bit.msi)y seleccione Descargar para Microsoft Online Services   asistente de inicio de  **sesión**.</span><span class="sxs-lookup"><span data-stu-id="ff755-124">Go to [Microsoft Online Services Sign-In Assistant for IT Professionals RTWl](https://download.microsoft.com/download/7/1/E/71EF1D05-A42C-4A1F-8162-96494B5E615C/msoidcli_32bit.msi) and select  **Download for Microsoft Online Services Sign-in Assistant**.</span></span>

2. <span data-ttu-id="ff755-125">Instale el Módulo Microsoft Azure Active Directory para Windows PowerShell siguiendo estos pasos:</span><span class="sxs-lookup"><span data-stu-id="ff755-125">Install the Microsoft Azure Active Directory Module for Windows PowerShell with these steps:</span></span>

    1. <span data-ttu-id="ff755-126">Abra un símbolo del sistema de PowerShell con permisos de administrador.</span><span class="sxs-lookup"><span data-stu-id="ff755-126">Open an administrator-level PowerShell command prompt.</span></span>

    2. <span data-ttu-id="ff755-127">Ejecute el comando `Install-Module MSOnline`.</span><span class="sxs-lookup"><span data-stu-id="ff755-127">Run the `Install-Module MSOnline` command.</span></span>

    3. <span data-ttu-id="ff755-128">Si se le pide que instale el proveedor de NuGet, escriba Y y presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="ff755-128">If prompted to install the NuGet provider, type Y and press ENTER.</span></span>

    4. <span data-ttu-id="ff755-129">Si se le pide que instale el módulo desde PSGallery, escriba Y y presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="ff755-129">If prompted to install the module from PSGallery, type Y and press ENTER.</span></span>

    5. <span data-ttu-id="ff755-130">Después de la instalación, cierre la ventana de comandos de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ff755-130">After installation, close the PowerShell command window.</span></span>

### <a name="step-2-connect-to-your-microsoft-365-subscription"></a><span data-ttu-id="ff755-131">Paso 2: Conectar a su Microsoft 365 suscripción</span><span class="sxs-lookup"><span data-stu-id="ff755-131">Step 2: Connect to your Microsoft 365 subscription</span></span>

1. <span data-ttu-id="ff755-132">En el Windows Azure Active Directory para Windows PowerShell, ejecute el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="ff755-132">In the Windows Azure Active Directory Module for Windows PowerShell, run the following command.</span></span>

   ```powershell
   $UserCredential = Get-Credential
   ```

2. <span data-ttu-id="ff755-133">En el Windows PowerShell de diálogo Solicitud de credenciales, escriba el nombre de usuario y la contraseña de su cuenta de administrador global Microsoft 365 y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ff755-133">In the Windows PowerShell Credential Request dialog box, type the user name and password for your Microsoft 365 global admin account, and then select **OK**.</span></span>

3. <span data-ttu-id="ff755-134">Ejecuta el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="ff755-134">Run the following command.</span></span>

   ```powershell
   Connect-MsolService -Credential $UserCredential
   ```

### <a name="step-3-make-sure-youre-able-to-run-powershell-scripts"></a><span data-ttu-id="ff755-135">Paso 3: Asegúrese de que puede ejecutar scripts de PowerShell</span><span class="sxs-lookup"><span data-stu-id="ff755-135">Step 3: Make sure you’re able to run PowerShell scripts</span></span>

> [!NOTE]
> <span data-ttu-id="ff755-136">Puede omitir este paso si ya está configurado para ejecutar scripts de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ff755-136">You can skip this step if you’re already set up to run PowerShell scripts.</span></span>

<span data-ttu-id="ff755-137">Para ejecutar el script Get-MsolUserDeviceComplianceStatus.ps1, debe habilitar la ejecución de scripts de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ff755-137">To run the Get-MsolUserDeviceComplianceStatus.ps1 script, you need to enable the running of PowerShell scripts.</span></span>

1. <span data-ttu-id="ff755-138">En el escritorio Windows, seleccione **Inicio** y, a continuación, escriba Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ff755-138">From your Windows Desktop, select **Start**, and then type Windows PowerShell.</span></span> <span data-ttu-id="ff755-139">Haga clic con el Windows PowerShell y, a continuación, **seleccione Ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="ff755-139">Right-click Windows PowerShell, and then select **Run as administrator**.</span></span>

2. <span data-ttu-id="ff755-140">Ejecuta el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="ff755-140">Run the following command.</span></span>

   ```powershell
   Set-ExecutionPolicy  RemoteSigned
   ```

3. <span data-ttu-id="ff755-141">Cuando se le pida, escriba Y y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="ff755-141">When prompted, type Y and then press Enter.</span></span>

#### <a name="run-the-get-msoldevice-cmdlet-to-display-details-for-all-devices-in-your-organization"></a><span data-ttu-id="ff755-142">Ejecute el cmdlet Get-MsolDevice para mostrar detalles para todos los dispositivos de la organización</span><span class="sxs-lookup"><span data-stu-id="ff755-142">Run the Get-MsolDevice cmdlet to display details for all devices in your organization</span></span>

1. <span data-ttu-id="ff755-143">Abra el Módulo Microsoft Azure Active Directory para Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ff755-143">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>

2. <span data-ttu-id="ff755-144">Ejecuta el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="ff755-144">Run the following command.</span></span>

   ```powershell
   Get-MsolDevice -All -ReturnRegisteredOwners | Where-Object {$_.RegisteredOwners.Count -gt 0}
   ```

<span data-ttu-id="ff755-145">Para obtener más ejemplos,  [vea Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=2157939).</span><span class="sxs-lookup"><span data-stu-id="ff755-145">For more examples, see  [Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=2157939).</span></span>

## <a name="run-a-script-to-get-device-details"></a><span data-ttu-id="ff755-146">Ejecutar un script para obtener detalles del dispositivo</span><span class="sxs-lookup"><span data-stu-id="ff755-146">Run a script to get device details</span></span>

<span data-ttu-id="ff755-147">En primer lugar, guarde el script en el equipo.</span><span class="sxs-lookup"><span data-stu-id="ff755-147">First, save the script to your computer.</span></span>

1. <span data-ttu-id="ff755-148">Copie y pegue el siguiente texto en Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="ff755-148">Copy and paste the following text into Notepad.</span></span>

   ```powershell
   param (
   [PSObject[]]$users = @(),
   [Switch]$export,
   [String]$exportFileName = "UserDeviceComplianceStatus_" + (Get-Date -Format "yyMMdd_HHMMss") + ".csv",
   [String]$exportPath = [Environment]::GetFolderPath("Desktop")
   )
   [System.Collections.IDictionary]$script:schema = @{
   DeviceId = ''
   DeviceOSType = ''
   DeviceOSVersion = ''
   DeviceTrustLevel = ''
   DisplayName = ''
   IsCompliant = ''
   IsManaged = ''
   ApproximateLastLogonTimestamp = ''
   DeviceObjectId = ''
   RegisteredOwnerUpn = ''
   RegisteredOwnerObjectId = ''
   RegisteredOwnerDisplayName = ''
   }
   function createResultObject
   {
   [PSObject]$resultObject = New-Object -TypeName PSObject -Property $script:schema
   return $resultObject
   }
   If ($users.Count -eq 0)
   {
   $users = Get-MsolUser
   }
   [PSObject[]]$result = foreach ($u in $users)
   {
   [PSObject]$devices = get-msoldevice -RegisteredOwnerUpn $u.UserPrincipalName
   foreach ($d in $devices)
   {
   [PSObject]$deviceResult = createResultObject
   $deviceResult.DeviceId = $d.DeviceId
   $deviceResult.DeviceOSType = $d.DeviceOSType
   $deviceResult.DeviceOSVersion = $d.DeviceOSVersion
   $deviceResult.DeviceTrustLevel = $d.DeviceTrustLevel
   $deviceResult.DisplayName = $d.DisplayName
   $deviceResult.IsCompliant = $d.GraphDeviceObject.IsCompliant
   $deviceResult.IsManaged = $d.GraphDeviceObject.IsManaged
   $deviceResult.DeviceObjectId = $d.ObjectId
   $deviceResult.RegisteredOwnerUpn = $u.UserPrincipalName
   $deviceResult.RegisteredOwnerObjectId = $u.ObjectId
   $deviceResult.RegisteredOwnerDisplayName = $u.DisplayName
   $deviceResult.ApproximateLastLogonTimestamp = $d.ApproximateLastLogonTimestamp
   $deviceResult
   }
   }
   If ($export)
   {
   $result | Export-Csv -path ($exportPath + "\" + $exportFileName) -NoTypeInformation
   }
   Else
   {
   $result
   }
   ```

2. <span data-ttu-id="ff755-149">Guárdelo como un archivo Windows PowerShell script mediante el uso de la extensión de .ps1; por ejemplo, Get-MsolUserDeviceComplianceStatus.ps1.</span><span class="sxs-lookup"><span data-stu-id="ff755-149">Save it as a Windows PowerShell script file by using the file extension .ps1; for example, Get-MsolUserDeviceComplianceStatus.ps1.</span></span>

## <a name="run-the-script-to-get-device-information-for-a-single-user-account"></a><span data-ttu-id="ff755-150">Ejecutar el script para obtener información del dispositivo para una sola cuenta de usuario</span><span class="sxs-lookup"><span data-stu-id="ff755-150">Run the script to get device information for a single user account</span></span>

1. <span data-ttu-id="ff755-151">Abra el Módulo Microsoft Azure Active Directory para Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ff755-151">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>

2. <span data-ttu-id="ff755-152">Vaya a la carpeta donde guardó el script.</span><span class="sxs-lookup"><span data-stu-id="ff755-152">Go to the folder where you saved the script.</span></span> <span data-ttu-id="ff755-153">Por ejemplo, si lo guardó en C:\PS-Scripts, ejecute el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="ff755-153">For example, if you saved it to C:\PS-Scripts, run the following command.</span></span>

   ```powershell
   cd C:\PS-Scripts
   ```

3. <span data-ttu-id="ff755-154">Ejecute el siguiente comando para identificar el usuario para el que desea obtener los detalles del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ff755-154">Run the following command to identify the user you want to get device details for.</span></span> <span data-ttu-id="ff755-155">En este ejemplo se obtienen detalles bar@example.com.</span><span class="sxs-lookup"><span data-stu-id="ff755-155">This example gets details for bar@example.com.</span></span>

   ```powershell
   $u = Get-MsolUser -UserPrincipalName bar@example.com
   ```

4. <span data-ttu-id="ff755-156">Ejecute el siguiente comando para iniciar el script.</span><span class="sxs-lookup"><span data-stu-id="ff755-156">Run the following command to initiate the script.</span></span>

   ```powershell
   .\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export
   ```

<span data-ttu-id="ff755-157">La información se exporta a su escritorio Windows como un archivo CSV.</span><span class="sxs-lookup"><span data-stu-id="ff755-157">The information is exported to your Windows Desktop as a CSV file.</span></span> <span data-ttu-id="ff755-158">Puede usar parámetros adicionales para especificar el nombre de archivo y la ruta de acceso del CSV.</span><span class="sxs-lookup"><span data-stu-id="ff755-158">You can use additional parameters to specify the file name and path of the CSV.</span></span>

## <a name="run-the-script-to-get-device-information-for-a-group-of-users"></a><span data-ttu-id="ff755-159">Ejecutar el script para obtener información del dispositivo para un grupo de usuarios</span><span class="sxs-lookup"><span data-stu-id="ff755-159">Run the script to get device information for a group of users</span></span>

1. <span data-ttu-id="ff755-160">Abra el Módulo Microsoft Azure Active Directory para Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ff755-160">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>

2. <span data-ttu-id="ff755-161">Vaya a la carpeta donde guardó el script.</span><span class="sxs-lookup"><span data-stu-id="ff755-161">Go to the folder where you saved the script.</span></span> <span data-ttu-id="ff755-162">Por ejemplo, si lo guardó en C:\PS-Scripts, ejecute el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="ff755-162">For example, if you saved it to C:\PS-Scripts, run the following command.</span></span>

   ```powershell
   cd C:\PS-Scripts
   ```

3. <span data-ttu-id="ff755-163">Ejecute el siguiente comando para identificar el grupo para el que desea obtener los detalles del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ff755-163">Run the following command to identify the group you want to get device details for.</span></span> <span data-ttu-id="ff755-164">En este ejemplo se obtienen detalles para los usuarios del grupo FinanceStaff.</span><span class="sxs-lookup"><span data-stu-id="ff755-164">This example gets details for users in the FinanceStaff group.</span></span>

   ```powershell
   $u = Get-MsolGroupMember -SearchString "FinanceStaff" | % { Get-MsolUser -ObjectId $_.ObjectId }
   ```

4. <span data-ttu-id="ff755-165">Ejecute el siguiente comando para iniciar el script.</span><span class="sxs-lookup"><span data-stu-id="ff755-165">Run the following command to initiate the script.</span></span>

   ```powershell
   .\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export
   ```

<span data-ttu-id="ff755-166">La información se exporta a su escritorio Windows como un archivo CSV.</span><span class="sxs-lookup"><span data-stu-id="ff755-166">The information is exported to your Windows Desktop as a CSV file.</span></span> <span data-ttu-id="ff755-167">Puede usar parámetros adicionales para especificar el nombre de archivo y la ruta de acceso del CSV.</span><span class="sxs-lookup"><span data-stu-id="ff755-167">You can use additional parameters to specify the file name and path of the CSV.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ff755-168">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="ff755-168">Related topics</span></span>

[<span data-ttu-id="ff755-169">Microsoft Conectar se ha retirado</span><span class="sxs-lookup"><span data-stu-id="ff755-169">Microsoft Connect Has Been Retired</span></span>](/collaborate/connect-redirect)

[<span data-ttu-id="ff755-170">Información general sobre Movilidad y seguridad básicas</span><span class="sxs-lookup"><span data-stu-id="ff755-170">Overview of Basic Mobility and Security</span></span>](overview.md)

[<span data-ttu-id="ff755-171">Get-MsolDevice</span><span class="sxs-lookup"><span data-stu-id="ff755-171">Get-MsolDevice</span></span>](https://go.microsoft.com/fwlink/?linkid=2157939)
