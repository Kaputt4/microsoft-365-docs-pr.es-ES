---
title: Obtener detalles sobre los dispositivos administrados de movilidad básica y seguridad
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
description: Usa Windows PowerShell para obtener detalles sobre los dispositivos de movilidad y seguridad básica de la organización.
ms.openlocfilehash: 7c6a0365dfd573377c3675bbcee8ee8280e33816
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "49876893"
---
# <a name="get-details-about-basic-mobility-and-security-managed-devices"></a>Obtener detalles sobre los dispositivos administrados de movilidad básica y seguridad

En este artículo se muestra cómo usar Windows PowerShell obtener detalles sobre los dispositivos de la organización configurados para movilidad y seguridad básicas.

Este es un desglose de los detalles del dispositivo disponibles para ti.

|**Detalle**|**Qué buscar en PowerShell**|
|:----------------|:------------------------------------------------------------------------------|
|El dispositivo está inscrito en movilidad y seguridad básicas. Para obtener más información, consulta [Inscribir el dispositivo móvil con movilidad y seguridad básicas](enroll-your-mobile-device.md)|El valor del *parámetro isManaged*   es:<br/>**True**= el dispositivo está inscrito.<br/>**False**= el dispositivo no está inscrito. |
|El dispositivo es compatible con las directivas de seguridad del dispositivo. Para obtener más información, consulta [Crear directivas de seguridad de dispositivos](create-device-security-policies.md)|El valor del *parámetro isCompliant*   es:<br/>**True**   = el dispositivo es compatible con las directivas.<br/>**False**   = el dispositivo no cumple con las directivas.|

:::image type="content" source="../../media/basic-mobility-security/bms-7-powershell-parameters.png" alt-text="Parámetros básicos de PowerShell de movilidad y seguridad":::

>[!NOTE]
>Los comandos y scripts de este artículo también devuelven detalles sobre los dispositivos administrados [por Microsoft Intune.](https://www.microsoft.com/cloud-platform/microsoft-intune)

## <a name="before-you-begin"></a>Antes de empezar

Hay algunas cosas que debe configurar para ejecutar los comandos y scripts que se describen en este artículo.

### <a name="step-1-download-and-install-the-azure-active-directory-module-for-windows-powershell"></a>Paso 1: Descargar e instalar el módulo de Azure Active Directory para Windows PowerShell

Para obtener más información sobre estos pasos, vea [Conectarse a Microsoft 365 con PowerShell.](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell)

1. Vaya a Microsoft Online Services Sign-In asistente para profesionales de TI [RTWl](https://www.microsoft.com/download/details.aspx?id=41950)y seleccione Descargar para Microsoft Online Services   de inicio de  **sesión.**   

2. Instale el Módulo Microsoft Azure Active Directory para Windows PowerShell siguiendo estos pasos:

    1. Abra un símbolo del sistema de PowerShell con permisos de administrador.  

    2. Ejecute el comando Install-Module MSOnline.

    3. Si se le pide que instale el proveedor de NuGet, escriba Y y presione ENTRAR.

    4. Si se le pide que instale el módulo desde PSGallery, escriba Y y presione ENTRAR.

    5. Después de la instalación, cierre la ventana de comandos de PowerShell.

### <a name="step-2-connect-to-your-microsoft-365-subscription"></a>Paso 2: Conectarse a su suscripción de Microsoft 365

1. En el Windows Azure módulo de Active Directory para Windows PowerShell, ejecute el siguiente comando.  

    $UserCredential = Get-Credential

2. En el Windows PowerShell de diálogo Solicitud de credenciales, escriba el nombre de usuario y la contraseña de su cuenta de administrador global de Microsoft 365 y, a continuación, **seleccione Aceptar.**

3. Ejecute el comando siguiente.

    Connect-MsolService -Credential $UserCredential

### <a name="step-3-make-sure-youre-able-to-run-powershell-scripts"></a>Paso 3: Asegúrese de que puede ejecutar scripts de PowerShell

>[!NOTE]
>Puede omitir este paso si ya está configurado para ejecutar scripts de PowerShell.

Para ejecutar el script Get-MsolUserDeviceComplianceStatus.ps1, debe habilitar la ejecución de scripts de PowerShell.

1. En el escritorio de Windows, selecciona **Inicio** y, a continuación, escribe Windows PowerShell. Haga clic con el Windows PowerShell y, a continuación, seleccione **Ejecutar como administrador.**

2. Ejecute el comando siguiente.

    Set-ExecutionPolicy RemoteSigned

3. Cuando se le solicite, escriba Y y, a continuación, presione ENTRAR.

**Ejecute el cmdlet Get-MsolDevice para mostrar los detalles de todos los dispositivos de la organización**

1. Abra el Módulo Microsoft Azure Active Directory para Windows PowerShell.  

2. Ejecute el comando siguiente.

    Get-MsolDevice -All -ReturnRegisteredOwners | Where-Object {$_. RegisteredOwners.Count -gt 0}

Para obtener más ejemplos,  [vea Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=841721).

## <a name="run-a-script-to-get-device-details"></a>Ejecutar un script para obtener detalles del dispositivo

En primer lugar, guarde el script en el equipo.

1. Copie y pegue el siguiente texto en el Bloc de notas.  

2.  param (

3.  [PSObject[]]$users = @(),

4.  [Switch]$export,

5.  [String]$exportFileName = "UserDeviceComplianceStatus_" + (Get-Date -Format "yyMMdd_HHMMss") + ".csv",

6.  [String]$exportPath = [Environment]::GetFolderPath("Desktop")

7.  )

9.  [System.Collections.IDictionary]$script:schema = @{

11.  DeviceId = ''

12.  DeviceOSType = ''

13.  DeviceOSVersion = ''

14.  DeviceTrustLevel = ''

15.  DisplayName = ''

16.  IsCompliant = ''

17.  IsManaged = ''

18.  ApproximateLastLogonTimestamp = ''

19.  DeviceObjectId = ''

20.  RegisteredOwnerUpn = ''

21.  RegisteredOwnerObjectId = ''
    

22.  RegisteredOwnerDisplayName = ''
    

23.  }
    

25.  function createResultObject
    

26.  {
    

28.  [PSObject]$resultObject = New-Object -TypeName PSObject -Property $script:schema
    

30.  devolver $resultObject
    

31.  }
    

33.  If ($users. Count -eq 0)
    

34.  {
    

35.  $users = Get-MsolUser
    

36.  }
    

38.  [PSObject[]]$result = foreach ($u en $users)
    

39.  {
    

41.  [PSObject]$devices = get-msoldevice -RegisteredOwnerUpn $u.UserPrincipalName
    

42.  foreach ($d en $devices)
    

43.  {
    

44.  [PSObject]$deviceResult = createResultObject
    

45.  $deviceResult.DeviceId = $d.DeviceId
    

46.  $deviceResult.DeviceOSType = $d.DeviceOSType
    

47.  $deviceResult.DeviceOSVersion = $d.DeviceOSVersion
    

48.  $deviceResult.DeviceTrustLevel = $d.DeviceTrustLevel
    

49.  $deviceResult.DisplayName = $d.DisplayName
    

50.  $deviceResult.IsCompliant = $d.GraphDeviceObject.IsCompliant
    

51.  $deviceResult.IsManaged = $d.GraphDeviceObject.IsManaged
    

52.  $deviceResult.DeviceObjectId = $d.ObjectId
    

53.  $deviceResult.RegisteredOwnerUpn = $u.UserPrincipalName
    

54.  $deviceResult.RegisteredOwnerObjectId = $u.ObjectId
    

55.  $deviceResult.RegisteredOwnerDisplayName = $u.DisplayName
    

56.  $deviceResult.ApproximateLastLogonTimestamp = $d.ApproximateLastLogonTimestamp
    

58.  $deviceResult
    

59.  }
    

61.  }
    

63.  If ($export)
    

64.  {
    

65.  $result | Export-Csv -path ($exportPath + " \" + $exportFileName) -NoTypeInformation
    

66.  }
    

67.  Else
    

68.  {
    

69.  $result
    

70.  }
    

71.  Guárdelo como un Windows PowerShell de script mediante la extensión de archivo .ps1; por ejemplo, Get-MsolUserDeviceComplianceStatus.ps1.   

## <a name="run-the-script-to-get-device-information-for-a-single-user-account"></a>Ejecutar el script para obtener información del dispositivo para una sola cuenta de usuario

1. Abra el Módulo Microsoft Azure Active Directory para Windows PowerShell.
    
2. Vaya a la carpeta donde guardó el script. Por ejemplo, si lo guardó en C:\PS-Scripts, ejecute el siguiente comando.
    
    cd C:\PS-Scripts

3. Ejecuta el siguiente comando para identificar el usuario para el que quieres obtener los detalles del dispositivo. En este ejemplo se obtienen los detalles bar@example.com.
    
    $u = Get-MsolUser -UserPrincipalName bar@example.com

4. Ejecute el siguiente comando para iniciar el script.

    .\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export

La información se exporta al escritorio de Windows como un archivo CSV. Puede usar parámetros adicionales para especificar el nombre de archivo y la ruta de acceso del ARCHIVO CSV.

## <a name="run-the-script-to-get-device-information-for-a-group-of-users"></a>Ejecutar el script para obtener información del dispositivo para un grupo de usuarios

1. Abra el Módulo Microsoft Azure Active Directory para Windows PowerShell.
    
2. Vaya a la carpeta donde guardó el script. Por ejemplo, si lo guardó en C:\PS-Scripts, ejecute el siguiente comando.   

    cd C:\PS-Scripts

3. Ejecuta el siguiente comando para identificar el grupo para el que quieres obtener los detalles del dispositivo. En este ejemplo se obtienen detalles de los usuarios del grupo FinanceStaff. 

    $u = Get-MsolGroupMember -SearchString "FinanceStaff" | % { Get-MsolUser -ObjectId $_. ObjectId }

4. Ejecute el siguiente comando para iniciar el script.   

    .\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export

La información se exporta al escritorio de Windows como un archivo CSV. Puede usar parámetros adicionales para especificar el nombre de archivo y la ruta de acceso del ARCHIVO CSV.

## <a name="related-topics"></a>Temas relacionados

[Microsoft Connect se ha retirado](https://docs.microsoft.com/collaborate/connect-redirect)

[Información general sobre Movilidad y seguridad básicas](overview.md)

[Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=841721)