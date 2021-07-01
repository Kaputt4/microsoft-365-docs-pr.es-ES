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
# <a name="get-details-about-basic-mobility-and-security-managed-devices"></a>Obtener detalles sobre dispositivos administrados de movilidad básica y seguridad

En este artículo se muestra cómo usar Windows PowerShell para obtener detalles sobre los dispositivos de la organización configurados para movilidad y seguridad básicas.

Este es un desglose de los detalles del dispositivo disponibles.

|**Detalle**|**Qué buscar en PowerShell**|
|:----------------|:------------------------------------------------------------------------------|
|El dispositivo está inscrito en Movilidad y seguridad básicas. Para obtener más información, consulta [Inscribir el dispositivo móvil con Movilidad y seguridad básicas](enroll-your-mobile-device.md)|El valor del *parámetro isManaged*   es:<br/>**True**= el dispositivo está inscrito.<br/>**False**= el dispositivo no está inscrito. |
|El dispositivo es compatible con las directivas de seguridad del dispositivo. Para obtener más información, consulta [Crear directivas de seguridad de dispositivos](create-device-security-policies.md)|El valor del *parámetro isCompliant*   es:<br/>**True**   = el dispositivo es compatible con las directivas.<br/>**False**   = el dispositivo no es compatible con las directivas.|

:::image type="content" source="../../media/basic-mobility-security/bms-7-powershell-parameters.png" alt-text="Parámetros básicos de PowerShell de movilidad y seguridad":::

> [!NOTE]
> Los comandos y scripts de este artículo también devuelven detalles sobre los dispositivos administrados [por Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune).

## <a name="before-you-begin"></a>Antes de empezar

Hay algunas cosas que debe configurar para ejecutar los comandos y scripts descritos en este artículo.

### <a name="step-1-download-and-install-the-azure-active-directory-module-for-windows-powershell"></a>Paso 1: Descargar e instalar el módulo Azure Active Directory para Windows PowerShell

Para obtener más información sobre estos pasos, vea [Conectar para Microsoft 365 con PowerShell](/office365/enterprise/powershell/connect-to-office-365-powershell).

1. Vaya a Microsoft Online Services Sign-In asistente para profesionales de [TI RTWl](https://download.microsoft.com/download/7/1/E/71EF1D05-A42C-4A1F-8162-96494B5E615C/msoidcli_32bit.msi)y seleccione Descargar para Microsoft Online Services   asistente de inicio de  **sesión**.

2. Instale el Módulo Microsoft Azure Active Directory para Windows PowerShell siguiendo estos pasos:

    1. Abra un símbolo del sistema de PowerShell con permisos de administrador.

    2. Ejecute el comando `Install-Module MSOnline`.

    3. Si se le pide que instale el proveedor de NuGet, escriba Y y presione ENTRAR.

    4. Si se le pide que instale el módulo desde PSGallery, escriba Y y presione ENTRAR.

    5. Después de la instalación, cierre la ventana de comandos de PowerShell.

### <a name="step-2-connect-to-your-microsoft-365-subscription"></a>Paso 2: Conectar a su Microsoft 365 suscripción

1. En el Windows Azure Active Directory para Windows PowerShell, ejecute el siguiente comando.

   ```powershell
   $UserCredential = Get-Credential
   ```

2. En el Windows PowerShell de diálogo Solicitud de credenciales, escriba el nombre de usuario y la contraseña de su cuenta de administrador global Microsoft 365 y, a continuación, seleccione **Aceptar**.

3. Ejecuta el siguiente comando.

   ```powershell
   Connect-MsolService -Credential $UserCredential
   ```

### <a name="step-3-make-sure-youre-able-to-run-powershell-scripts"></a>Paso 3: Asegúrese de que puede ejecutar scripts de PowerShell

> [!NOTE]
> Puede omitir este paso si ya está configurado para ejecutar scripts de PowerShell.

Para ejecutar el script Get-MsolUserDeviceComplianceStatus.ps1, debe habilitar la ejecución de scripts de PowerShell.

1. En el escritorio Windows, seleccione **Inicio** y, a continuación, escriba Windows PowerShell. Haga clic con el Windows PowerShell y, a continuación, **seleccione Ejecutar como administrador**.

2. Ejecuta el siguiente comando.

   ```powershell
   Set-ExecutionPolicy  RemoteSigned
   ```

3. Cuando se le pida, escriba Y y, a continuación, presione ENTRAR.

#### <a name="run-the-get-msoldevice-cmdlet-to-display-details-for-all-devices-in-your-organization"></a>Ejecute el cmdlet Get-MsolDevice para mostrar detalles para todos los dispositivos de la organización

1. Abra el Módulo Microsoft Azure Active Directory para Windows PowerShell.

2. Ejecuta el siguiente comando.

   ```powershell
   Get-MsolDevice -All -ReturnRegisteredOwners | Where-Object {$_.RegisteredOwners.Count -gt 0}
   ```

Para obtener más ejemplos,  [vea Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=2157939).

## <a name="run-a-script-to-get-device-details"></a>Ejecutar un script para obtener detalles del dispositivo

En primer lugar, guarde el script en el equipo.

1. Copie y pegue el siguiente texto en Bloc de notas.

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

2. Guárdelo como un archivo Windows PowerShell script mediante el uso de la extensión de .ps1; por ejemplo, Get-MsolUserDeviceComplianceStatus.ps1.

## <a name="run-the-script-to-get-device-information-for-a-single-user-account"></a>Ejecutar el script para obtener información del dispositivo para una sola cuenta de usuario

1. Abra el Módulo Microsoft Azure Active Directory para Windows PowerShell.

2. Vaya a la carpeta donde guardó el script. Por ejemplo, si lo guardó en C:\PS-Scripts, ejecute el siguiente comando.

   ```powershell
   cd C:\PS-Scripts
   ```

3. Ejecute el siguiente comando para identificar el usuario para el que desea obtener los detalles del dispositivo. En este ejemplo se obtienen detalles bar@example.com.

   ```powershell
   $u = Get-MsolUser -UserPrincipalName bar@example.com
   ```

4. Ejecute el siguiente comando para iniciar el script.

   ```powershell
   .\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export
   ```

La información se exporta a su escritorio Windows como un archivo CSV. Puede usar parámetros adicionales para especificar el nombre de archivo y la ruta de acceso del CSV.

## <a name="run-the-script-to-get-device-information-for-a-group-of-users"></a>Ejecutar el script para obtener información del dispositivo para un grupo de usuarios

1. Abra el Módulo Microsoft Azure Active Directory para Windows PowerShell.

2. Vaya a la carpeta donde guardó el script. Por ejemplo, si lo guardó en C:\PS-Scripts, ejecute el siguiente comando.

   ```powershell
   cd C:\PS-Scripts
   ```

3. Ejecute el siguiente comando para identificar el grupo para el que desea obtener los detalles del dispositivo. En este ejemplo se obtienen detalles para los usuarios del grupo FinanceStaff.

   ```powershell
   $u = Get-MsolGroupMember -SearchString "FinanceStaff" | % { Get-MsolUser -ObjectId $_.ObjectId }
   ```

4. Ejecute el siguiente comando para iniciar el script.

   ```powershell
   .\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export
   ```

La información se exporta a su escritorio Windows como un archivo CSV. Puede usar parámetros adicionales para especificar el nombre de archivo y la ruta de acceso del CSV.

## <a name="related-topics"></a>Temas relacionados

[Microsoft Conectar se ha retirado](/collaborate/connect-redirect)

[Información general sobre Movilidad y seguridad básicas](overview.md)

[Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=2157939)
