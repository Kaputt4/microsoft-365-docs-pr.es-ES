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
# <a name="get-details-about-basic-mobility-and-security-managed-devices"></a>Obtener información sobre la movilidad básica y los dispositivos administrados de seguridad

En este artículo se muestra cómo usar Windows PowerShell para obtener detalles sobre los dispositivos de la organización que ha configurado para la movilidad y la seguridad básicos.

Este es un desglose de los detalles de dispositivos disponibles.

|**Detalle**|**Qué buscar en PowerShell**|
|:----------------|:------------------------------------------------------------------------------|
|El dispositivo está inscrito en la movilidad y la seguridad básicas. Para obtener más información, consulte [inscribir un dispositivo móvil usando la movilidad y la seguridad básicas](enroll-your-mobile-device-using-basic-mobility-and-security.md)|El valor del parámetro *isManaged*   es:<br/>**True**= el dispositivo está inscrito.<br/>**False**= no se inscribe el dispositivo. |
|El dispositivo es compatible con las directivas de seguridad del dispositivo. Para obtener más información, consulte [crear directivas de seguridad de dispositivos](create-device-security-policies-in-basic-mmobility-and-security.md) .|El valor del parámetro *isCompliant*   es:<br/>**True**   = el dispositivo es compatible con las directivas.<br/>**False**   = el dispositivo no es compatible con las directivas.|

:::image type="content" source="../../media/basic-mobility-security/bms-7-powershell-parameters.png" alt-text="Parámetros básicos de PowerShell de seguridad y movilidad":::

>[!NOTE]
>Los comandos y los scripts de este artículo también devuelven detalles sobre los dispositivos administrados por [Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune).

## <a name="before-you-begin"></a>Antes de empezar

Hay algunas cosas que debe configurar para ejecutar los comandos y scripts descritos en este artículo.

### <a name="step-1-download-and-install-the-azure-active-directory-module-for-windows-powershell"></a>Paso 1: descargar e instalar el módulo de Azure Active Directory para Windows PowerShell

Para obtener más información sobre estos pasos, consulte [conectarse a Microsoft 365 con PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell).

1. Vaya a [Microsoft Online Services-ayudante para el inicio de sesión para profesionales de ti RTWl](https://www.microsoft.com/download/details.aspx?id=41950)   y seleccione  **descargar para el ayudante para el inicio de sesión de Microsoft Online Services**.   

2. Instale el Módulo Microsoft Azure Active Directory para Windows PowerShell siguiendo estos pasos:   

    1. Abra un símbolo del sistema de PowerShell con permisos de administrador.  

    2. Ejecute el comando Install-Module MSOnline.
    
    3. Si se le pide que instale el proveedor de NuGet, escriba Y y presione ENTRAR.   

    4. Si se le pide que instale el módulo desde PSGallery, escriba Y y presione ENTRAR.   

    5. Después de la instalación, cierre la ventana de comandos de PowerShell.
    
### <a name="step-2-connect-to-your-microsoft-365-subscription"></a>Paso 2: conectarse a la suscripción de Microsoft 365

1. En el módulo Windows Azure Active Directory para Windows PowerShell, ejecute el siguiente comando.  

    $UserCredential = Get-Credential

2. En el cuadro de diálogo solicitud de credenciales para Windows PowerShell, escriba el nombre de usuario y la contraseña de su cuenta de administrador global de Microsoft 365 y, a continuación, seleccione **Aceptar**.
    
3. Ejecute el comando siguiente.
    
    $UserCredential Connect-MsolService-Credential

### <a name="step-3-make-sure-youre-able-to-run-powershell-scripts"></a>Paso 3: Asegúrese de que puede ejecutar scripts de PowerShell

>[!NOTE]
>Puede omitir este paso si ya está configurado para ejecutar scripts de PowerShell.

Para ejecutar el script de Get-MsolUserDeviceComplianceStatus.ps1, debe habilitar la ejecución de scripts de PowerShell.

1. En el escritorio de Windows, seleccione **Inicio**y, a continuación, escriba Windows PowerShell. Haga clic con el botón secundario en Windows PowerShell y seleccione **Ejecutar como administrador**.

2. Ejecute el comando siguiente.
    
    Set-ExecutionPolicy RemoteSigned

3. Cuando se le solicite, escriba s y, a continuación, presione Entrar.
    
**Ejecute el cmdlet Get-MsolDevice para mostrar los detalles de todos los dispositivos de su organización.**

1. Abra el Módulo Microsoft Azure Active Directory para Windows PowerShell.  

2. Ejecute el comando siguiente.
    
    Get-MsolDevice-All-ReturnRegisteredOwners | Where-Object {$ _. RegisteredOwners. Count-gt 0}

Para obtener más ejemplos, consulte  [Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=841721).

## <a name="run-a-script-to-get-device-details"></a>Ejecutar un script para obtener detalles del dispositivo

En primer lugar, guarde el script en el equipo.

1. Copie y pegue el texto siguiente en el Bloc de notas.  

2.  parámetro
    

3.  [PSObject []] $users = @ (),
    

4.  [Modificador] $export,
    

5.  [String] $exportFileName = "UserDeviceComplianceStatus_" + (get-Date-Format "yyMMdd_HHMMss") + ". csv",
    

6.  [String] $exportPath = [Environment]:: GetFolderPath ("Desktop")
    

7.  )
    

9.  [System. Collections. IDictionary] $script: Schema = @ {
    

11.  DeviceId = ' '
    

12.  DeviceOSType = ' '
    

13.  DeviceOSVersion = ' '
    

14.  DeviceTrustLevel = ' '
    

15.  DisplayName = ' '
    

16.  IsCompliant = ' '
    

17.  IsManaged = ' '
    

18.  ApproximateLastLogonTimestamp = ' '
    

19.  DeviceObjectId = ' '
    

20.  RegisteredOwnerUpn = ' '
    

21.  RegisteredOwnerObjectId = ' '
    

22.  RegisteredOwnerDisplayName = ' '
    

23.  }
    

25.  función createResultObject
    

26.  {
    

28.  [PSObject] $resultObject = New-Object-TypeName PSObject-Property $script: Schema
    

30.  devolver $resultObject
    

31.  }
    

33.  If ($users. Count-EQ 0)
    

34.  {
    

35.  $users = Get-MsolUser
    

36.  }
    

38.  [PSObject []] $result = foreach ($u en $users)
    

39.  {
    

41.  [PSObject] $devices = Get-msoldevice-RegisteredOwnerUpn $u. UserPrincipalName
    

42.  foreach ($d en $devices)
    

43.  {
    

44.  [PSObject] $deviceResult = createResultObject
    

45.  $deviceResult. DeviceId = $d. DeviceId
    

46.  $deviceResult. DeviceOSType = $d. DeviceOSType
    

47.  $deviceResult. DeviceOSVersion = $d. DeviceOSVersion
    

48.  $deviceResult. DeviceTrustLevel = $d. DeviceTrustLevel
    

49.  $deviceResult. DisplayName = $d. DisplayName
    

50.  $deviceResult. IsCompliant = $d. GraphDeviceObject. IsCompliant
    

51.  $deviceResult. IsManaged = $d. GraphDeviceObject. IsManaged
    

52.  $deviceResult. DeviceObjectId = $d. ObjectId
    

53.  $deviceResult. RegisteredOwnerUpn = $u. UserPrincipalName
    

54.  $deviceResult. RegisteredOwnerObjectId = $u. ObjectId
    

55.  $deviceResult. RegisteredOwnerDisplayName = $u. DisplayName
    

56.  $deviceResult. ApproximateLastLogonTimestamp = $d. ApproximateLastLogonTimestamp
    

58.  $deviceResult
    

59.  }
    

61.  }
    

63.  If ($export)
    

64.  {
    

65.  $result | Export-CSV-Path ($exportPath + " \" + $exportFileName)-NoTypeInformation
    

66.  }
    

67.  Else
    

68.  {
    

69.  $result
    

70.  }
    

71.  Guárdelo como un archivo de script de Windows PowerShell mediante la extensión de archivo. ps1; por ejemplo, Get-MsolUserDeviceComplianceStatus.ps1.   

## <a name="run-the-script-to-get-device-information-for-a-single-user-account"></a>Ejecutar el script para obtener información del dispositivo para una sola cuenta de usuario

1. Abra el Módulo Microsoft Azure Active Directory para Windows PowerShell.
    
2. Vaya a la carpeta en la que guardó el script. Por ejemplo, si lo guardó en C:\PS-Scripts, ejecute el siguiente comando.
    
    CD C:\PS-Scripts

3. Ejecute el siguiente comando para identificar el usuario para el que desea obtener detalles del dispositivo. En este ejemplo se obtienen los detalles de bar@example.com.
    
    $u = Get-MsolUser-UserPrincipalName bar@example.com

4. Ejecute el siguiente comando para iniciar el script.

    .\Get-MsolUserDeviceComplianceStatus.ps1: $u de usuario: exportar

La información se exporta al escritorio de Windows como un archivo CSV. Puede usar parámetros adicionales para especificar el nombre de archivo y la ruta de acceso del archivo CSV.

## <a name="run-the-script-to-get-device-information-for-a-group-of-users"></a>Ejecutar el script para obtener información del dispositivo para un grupo de usuarios

1. Abra el Módulo Microsoft Azure Active Directory para Windows PowerShell.
    
2. Vaya a la carpeta en la que guardó el script. Por ejemplo, si lo guardó en C:\PS-Scripts, ejecute el siguiente comando.   

    CD C:\PS-Scripts

3. Ejecute el siguiente comando para identificar el grupo para el que desea obtener detalles del dispositivo. En este ejemplo se obtienen los detalles de los usuarios en el grupo FinanceStaff. 

    $u = Get-MsolGroupMember-SearchString "FinanceStaff" | % {Get-MsolUser-ObjectId $ _. ObjectId

4. Ejecute el siguiente comando para iniciar el script.   

    .\Get-MsolUserDeviceComplianceStatus.ps1: $u de usuario: exportar

La información se exporta al escritorio de Windows como un archivo CSV. Puede usar parámetros adicionales para especificar el nombre de archivo y la ruta de acceso del archivo CSV.

## <a name="related-topics"></a>Temas relacionados

[Microsoft Connect se ha retirado](https://docs.microsoft.com/collaborate/connect-redirect)

[Introducción a la movilidad y la seguridad básicas](overview-of-basic-mobility-and-security-for-microsoft-365.md)

[Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=841721)