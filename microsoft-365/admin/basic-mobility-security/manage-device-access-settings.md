---
title: Administración de la configuración de acceso a dispositivos en Basic Mobility and Security
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- Tier3
- scotvorg
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: En el caso de los dispositivos que no se pueden administrar con Basic Mobility and Security, bloquee Exchange ActiveSync acceso de la aplicación al correo electrónico y use PowerShell de Azure AD para obtener detalles sobre los dispositivos de la organización.
ms.openlocfilehash: 833f155570e3234c5731ac23541ca8db7948c403
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2022
ms.locfileid: "68720490"
---
# <a name="manage-device-access-settings-in-basic-mobility-and-security"></a>Administración de la configuración de acceso a dispositivos en Basic Mobility and Security

Si usa Basic Mobility and Security, es posible que haya dispositivos que no pueda administrar con Basic Mobility and Security. Si es así, debe bloquear Exchange ActiveSync acceso de la aplicación al correo electrónico de Microsoft 365 para dispositivos móviles que no son compatibles con Basic Mobility and Security. Esto ayuda a proteger la información de la organización en más dispositivos.

Siga estos pasos:

1. Inicie sesión en Microsoft 365 con su cuenta de administrador global.

2. En el explorador, escriba: <https://protection.office.com/>.

    > [!IMPORTANT]
    > Si es la primera vez que usa Basic Mobility and Security para Microsoft 365 Empresa Estándar, actívelo aquí: [Activar seguridad y movilidad básicas](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx). Después de activarlo, administre los dispositivos con [Office 365 Security & Compliance](https://protection.office.com/).

3. Vaya a **Prevención de pérdida de datos Directivas** \> **de** **dispositivos de administración** \> de dispositivos y seleccione **Administrar la configuración de acceso a dispositivos de toda la organización**.

4. Seleccione **Acceso**.

    :::image type="content" source="../../media/basic-mobility-security/basic-mobility-access.png" alt-text="La casilla De movilidad básica y seguridad bloquea el acceso.":::

5. Seleccione **Guardar**.

Para obtener información sobre qué dispositivos admite Basic Mobility and Security, consulte [Funcionalidades de movilidad y seguridad básicas](capabilities.md).

## <a name="get-details-about-basic-mobility-and-security-managed-devices"></a>Obtener detalles sobre los dispositivos administrados de movilidad y seguridad básicas

Además, puede usar PowerShell de Azure AD para obtener detalles sobre los dispositivos de la organización que configuró para Basic Mobility and Security.

Este es un desglose de los detalles del dispositivo disponibles.

|Detalles|Qué buscar en PowerShell|
|---|---|
|El dispositivo está inscrito en Basic Mobility and Security. Para obtener más información, consulte [Inscripción de un dispositivo móvil mediante Basic Mobility and Security](enroll-your-mobile-device.md)|El valor del parámetro *isManaged* es:<br/>**True**= el dispositivo está inscrito.<br/>**False**= el dispositivo no está inscrito.|
|El dispositivo es compatible con las directivas de seguridad del dispositivo. Para obtener más información, consulte [Creación de directivas de seguridad de dispositivos](create-device-security-policies.md).|El valor del parámetro *isCompliant* es:<br/>**True** = el dispositivo es compatible con las directivas.<br/>**False** = el dispositivo no es compatible con las directivas.|

:::image type="content" source="../../media/basic-mobility-security/bms-7-powershell-parameters.png" alt-text="Parámetros básicos de PowerShell de movilidad y seguridad.":::

> [!NOTE]
> Los comandos y scripts siguientes también devuelven detalles sobre los dispositivos administrados por [Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune).

Estas son algunas cosas que debe configurar para ejecutar los comandos y scripts siguientes:

### <a name="step-1-download-and-install-the-azure-active-directory-module-for-windows-powershell"></a>Paso 1: Descargar e instalar el módulo de Azure Active Directory para Windows PowerShell

Para obtener más información sobre estos pasos, consulte [Conexión a Microsoft 365 con PowerShell](/office365/enterprise/powershell/connect-to-office-365-powershell).

1. Vaya a [Microsoft Online Services Sign-In Assistant for IT Professionals RTWl](https://download.microsoft.com/download/7/1/E/71EF1D05-A42C-4A1F-8162-96494B5E615C/msoidcli_32bit.msi) y seleccione **Download for Microsoft Online Services Sign-in Assistant (Descargar para el Asistente de inicio de sesión de Microsoft Online Services).**

2. Instale el Módulo Microsoft Azure Active Directory para Windows PowerShell siguiendo estos pasos:

    1. Abra un símbolo del sistema de PowerShell con permisos de administrador.

    2. Ejecute el comando `Install-Module MSOnline`.

    3. Si se le pide que instale el proveedor de NuGet, escriba Y y presione ENTRAR.

    4. Si se le pide que instale el módulo desde PSGallery, escriba Y y presione ENTRAR.

    5. Después de la instalación, cierre la ventana de comandos de PowerShell.

### <a name="step-2-connect-to-your-microsoft-365-subscription"></a>Paso 2: Conectarse a la suscripción de Microsoft 365

1. En el módulo de Windows Azure Active Directory para Windows PowerShell, ejecute el siguiente comando.

   ```powershell
   $UserCredential = Get-Credential
   ```

2. En el cuadro de diálogo Windows PowerShell solicitud de credenciales, escriba el nombre de usuario y la contraseña de la cuenta de administrador global de Microsoft 365 y, a continuación, seleccione **Aceptar**.

3. Ejecuta el siguiente comando.

   ```powershell
   Connect-MsolService -Credential $UserCredential
   ```

### <a name="step-3-make-sure-youre-able-to-run-powershell-scripts"></a>Paso 3: Asegúrese de que puede ejecutar scripts de PowerShell

> [!NOTE]
> Puede omitir este paso si ya está configurado para ejecutar scripts de PowerShell.

Para ejecutar el script de Get-MsolUserDeviceComplianceStatus.ps1, debe habilitar la ejecución de scripts de PowerShell.

1. En el escritorio de Windows, seleccione **Inicio** y, a continuación, escriba Windows PowerShell. Haga clic con el botón derecho en Windows PowerShell y, a continuación, seleccione **Ejecutar como administrador**.

2. Ejecuta el siguiente comando.

   ```powershell
   Set-ExecutionPolicy RemoteSigned
   ```

3. Cuando se le solicite, escriba Y y presione Entrar.

#### <a name="run-the-get-msoldevice-cmdlet-to-display-details-for-all-devices-in-your-organization"></a>Ejecute el cmdlet Get-MsolDevice para mostrar los detalles de todos los dispositivos de la organización.

1. Abra el Módulo Microsoft Azure Active Directory para Windows PowerShell.

2. Ejecuta el siguiente comando.

   ```powershell
   Get-MsolDevice -All -ReturnRegisteredOwners | Where-Object {$_.RegisteredOwners.Count -gt 0}
   ```

Para obtener más ejemplos, vea [Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=2157939).

### <a name="run-a-script-to-get-device-details"></a>Ejecución de un script para obtener los detalles del dispositivo

En primer lugar, guarde el script en el equipo.

1. Copie y pegue el texto siguiente en el Bloc de notas.

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

2. Guárdelo como un archivo de script Windows PowerShell mediante la extensión de archivo .ps1; por ejemplo, Get-MsolUserDeviceComplianceStatus.ps1.

### <a name="run-the-script-to-get-device-information-for-a-single-user-account"></a>Ejecute el script para obtener información del dispositivo para una sola cuenta de usuario.

1. Abra el Módulo Microsoft Azure Active Directory para Windows PowerShell.

2. Vaya a la carpeta donde guardó el script. Por ejemplo, si lo guardó en C:\PS-Scripts, ejecute el siguiente comando.

   ```powershell
   cd C:\PS-Scripts
   ```

3. Ejecute el siguiente comando para identificar al usuario para el que desea obtener los detalles del dispositivo. En este ejemplo se obtienen detalles de bar@example.com.

   ```powershell
   $u = Get-MsolUser -UserPrincipalName bar@example.com
   ```

4. Ejecute el siguiente comando para iniciar el script.

   ```powershell
   .\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export
   ```

La información se exporta al escritorio de Windows como un archivo CSV. Puede usar parámetros adicionales para especificar el nombre de archivo y la ruta de acceso del ARCHIVO CSV.

### <a name="run-the-script-to-get-device-information-for-a-group-of-users"></a>Ejecutar el script para obtener información del dispositivo para un grupo de usuarios

1. Abra el Módulo Microsoft Azure Active Directory para Windows PowerShell.

2. Vaya a la carpeta donde guardó el script. Por ejemplo, si lo guardó en C:\PS-Scripts, ejecute el siguiente comando.

   ```powershell
   cd C:\PS-Scripts
   ```

3. Ejecute el siguiente comando para identificar el grupo para el que desea obtener los detalles del dispositivo. En este ejemplo se obtienen los detalles de los usuarios del grupo FinanceStaff.

   ```powershell
   $u = Get-MsolGroupMember -SearchString "FinanceStaff" | % { Get-MsolUser -ObjectId $_.ObjectId }
   ```

4. Ejecute el siguiente comando para iniciar el script.

   ```powershell
   .\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export
   ```

La información se exporta al escritorio de Windows como un archivo CSV. Puede usar parámetros adicionales para especificar el nombre de archivo y la ruta de acceso del ARCHIVO CSV.

## <a name="related-content"></a>Contenido relacionado

[Microsoft Connect se ha retirado](/collaborate/connect-redirect)

[Información general sobre Movilidad y seguridad básicas](overview.md)

[Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=2157939)