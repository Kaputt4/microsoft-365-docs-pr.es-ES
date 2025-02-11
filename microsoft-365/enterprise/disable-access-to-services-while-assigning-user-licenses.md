---
title: Deshabilitar el acceso a los servicios de Microsoft 365 al asignar licencias de usuario
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 04/24/2020
audience: Admin
ms.topic: article
ms.collection:
- scotvorg
- Ent_O365
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
search.appverid:
- MET150
f1.keywords:
- CSH
ms.custom:
- PowerShell
- Ent_Office_Other
ms.assetid: bb003bdb-3c22-4141-ae3b-f0656fc23b9c
description: Obtenga información sobre cómo asignar licencias a cuentas de usuario y deshabilitar planes de servicio específicos al mismo tiempo mediante PowerShell para Microsoft 365.
ms.openlocfilehash: fc6285c9f4df8a38fae8feb11bd0801d22728dc4
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68178853"
---
# <a name="disable-access-to-microsoft-365-services-while-assigning-user-licenses"></a>Deshabilitar el acceso a los servicios de Microsoft 365 al asignar licencias de usuario

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

Las suscripciones de Microsoft 365 incluyen planes de servicio para servicios individuales. Los administradores de Microsoft 365 suelen tener que deshabilitar determinados planes al asignar licencias a los usuarios. Con las instrucciones de este artículo, puede asignar una licencia de Microsoft 365 al deshabilitar planes de servicio específicos mediante PowerShell para una cuenta de usuario individual o varias cuentas de usuario.

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Use el módulo de PowerShell Azure Active Directory para Graph

En primer lugar, [conéctese a su inquilino de Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).


A continuación, enumere los planes de licencia del inquilino con este comando.

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

A continuación, obtenga el nombre de inicio de sesión de la cuenta a la que desea agregar una licencia, también conocida como nombre principal de usuario (UPN).

A continuación, compile una lista de servicios para habilitar. Para obtener una lista completa de los planes de licencia (también conocidos como nombres de producto), sus planes de servicio incluidos y sus nombres descriptivos [correspondientes, consulte Nombres de producto e identificadores de plan de servicio para licencias](/azure/active-directory/users-groups-roles/licensing-service-plan-reference).

En el bloque de comandos siguiente, rellene el nombre principal de usuario de la cuenta de usuario, el número de parte de sku y la lista de planes de servicio para habilitar y quitar el texto explicativo y los \< and > caracteres. A continuación, ejecute los comandos resultantes en el símbolo del sistema de PowerShell.

```powershell
$userUPN="<user account UPN>"
$skuPart="<SKU part number>"
$serviceList=<double-quoted enclosed, comma-separated list of enabled services>
$user = Get-AzureADUser -ObjectID $userUPN
$skuID= (Get-AzureADSubscribedSku  | Where {$_.SkuPartNumber -eq $skuPart}).SkuID
$SkuFeaturesToEnable = @($serviceList)
$StandardLicense = Get-AzureADSubscribedSku | Where {$_.SkuId -eq $skuID}
$SkuFeaturesToDisable = $StandardLicense.ServicePlans | ForEach-Object { $_ | Where {$_.ServicePlanName -notin $SkuFeaturesToEnable }}
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = $StandardLicense.SkuId
$License.DisabledPlans = $SkuFeaturesToDisable.ServicePlanId
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $user.ObjectId -AssignedLicenses $LicensesToAssign
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Use el Módulo Microsoft Azure Active Directory para Windows PowerShell

En primer lugar, [conéctese a su inquilino de Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).

A continuación, ejecute este comando para ver las suscripciones actuales:

```powershell
Get-MsolAccountSku
```

>[!Note]
>PowerShell Core no es compatible con el Módulo Microsoft Azure Active Directory para Windows PowerShell ni los cmdlet que llevan **Msol** en su nombre. Para seguir usando estos cmdlets, debe ejecutarlos desde Windows PowerShell.
>

En la presentación del  `Get-MsolAccountSku` comando:

- **AccountSkuId** es una suscripción para su organización en \<OrganizationName>formato :\<Subscription> . \<OrganizationName> es el valor que proporcionó al inscribirse en Microsoft 365 y es único para su organización. El \<Subscription> valor es para una suscripción específica. Por ejemplo, para litwareinc:ENTERPRISEPACK, el nombre de la organización es litwareinc y el nombre de la suscripción es ENTERPRISEPACK (Office 365 Enterprise E3).

- **ActiveUnits** es el número de licencias que ha comprado para la suscripción.

- **WarningUnits** es el número de licencias de una suscripción que no ha renovado y que expirarán después del período de gracia de 30 días.

- **ConsumedUnits** es el número de licencias que ha asignado a los usuarios para la suscripción.

Tenga en cuenta el AccountSkuId de la suscripción de Microsoft 365 que contiene los usuarios que desea licenciar. Además, asegúrese de que hay suficientes licencias para asignar (reste **ConsumedUnits** de **ActiveUnits**).

A continuación, ejecute este comando para ver los detalles sobre los planes de servicio de Microsoft 365 que están disponibles en todas las suscripciones:

```powershell
Get-MsolAccountSku | Select -ExpandProperty ServiceStatus
```

En la presentación de este comando, determine qué planes de servicio desea deshabilitar al asignar licencias a los usuarios.

Esta es una lista parcial de los planes de servicio y sus servicios de Microsoft 365 correspondientes.

En la tabla siguiente se muestran los planes de servicio de Microsoft 365 y sus nombres descriptivos para los servicios más comunes. Su lista de planes de servicio puede ser diferente.

|**Plan de servicio**|**Descripción**|
|:-----|:-----|
| `SWAY` <br/> |Sway  <br/> |
| `TEAMS1` <br/> |Microsoft Teams  <br/> |
| `YAMMER_ENTERPRISE` <br/> |Yammer  <br/> |
| `RMS_S_ENTERPRISE` <br/> |Azure Rights Management (RMS)  <br/> |
| `OFFICESUBSCRIPTION` <br/> |Aplicaciones Microsoft 365 para empresas *(anteriormente denominado Office 365 ProPlus)*  <br/> |
| `MCOSTANDARD` <br/> |Skype Empresarial Online  <br/> |
| `SHAREPOINTWAC` <br/> |Oficina   <br/> |
| `SHAREPOINTENTERPRISE` <br/> |SharePoint Online  <br/> |
| `EXCHANGE_S_ENTERPRISE` <br/> |Plan 2 de Exchange Online  <br/> |

Para obtener una lista completa de los planes de licencia (también conocidos como nombres de producto), sus planes de servicio incluidos y sus nombres descriptivos [correspondientes, consulte Nombres de producto e identificadores de plan de servicio para licencias](/azure/active-directory/users-groups-roles/licensing-service-plan-reference).

Ahora que tiene accountSkuId y los planes de servicio para deshabilitar, puede asignar licencias para un usuario individual o para varios usuarios.

### <a name="for-a-single-user"></a>Para un único usuario

Para un único usuario, rellene el nombre principal de usuario de la cuenta de usuario, accountSkuId y la lista de planes de servicio para deshabilitar y quitar el texto explicativo y los \< and > caracteres. A continuación, ejecute los comandos resultantes en el símbolo del sistema de PowerShell.

```powershell
$userUPN="<the user's account name in email format>"
$accountSkuId="<the AccountSkuId from the Get-MsolAccountSku command>"
$planList=@( <comma-separated, double-quote enclosed list of the service plans to disable> )
$licenseOptions=New-MsolLicenseOptions -AccountSkuId $accountSkuId -DisabledPlans $planList
Set-MsolUserLicense -UserPrincipalName $userUpn -AddLicenses $accountSkuId -ErrorAction SilentlyContinue
Sleep -Seconds 5
Set-MsolUserLicense -UserPrincipalName $userUpn -LicenseOptions $licenseOptions -ErrorAction SilentlyContinue
```

Este es un bloque de comandos de ejemplo para la cuenta denominada belindan@contoso.com, para la licencia contoso:ENTERPRISEPACK y los planes de servicio que se van a deshabilitar son RMS_S_ENTERPRISE, SWAY, INTUNE_O365 y YAMMER_ENTERPRISE:

```powershell
$userUPN="belindan@contoso.com"
$accountSkuId="contoso:ENTERPRISEPACK"
$planList=@( "RMS_S_ENTERPRISE","SWAY","INTUNE_O365","YAMMER_ENTERPRISE" )
$licenseOptions=New-MsolLicenseOptions -AccountSkuId $accountSkuId -DisabledPlans $planList
Set-MsolUserLicense -UserPrincipalName $userUpn -AddLicenses $accountSkuId -ErrorAction SilentlyContinue
Sleep -Seconds 5
Set-MsolUserLicense -UserPrincipalName $userUpn -LicenseOptions $licenseOptions -ErrorAction SilentlyContinue
```

### <a name="for-multiple-users"></a>Para varios usuarios

Para realizar esta tarea de administración para varios usuarios, cree un archivo de texto de valores separados por comas (CSV) que contenga los campos UserPrincipalName y UsageLocation. A continuación le mostramos un ejemplo:

```powershell
UserPrincipalName,UsageLocation
ClaudeL@contoso.onmicrosoft.com,FR
LynneB@contoso.onmicrosoft.com,US
ShawnM@contoso.onmicrosoft.com,US
```

A continuación, rellene la ubicación de los archivos CSV de entrada y salida, el identificador de SKU de la cuenta y la lista de planes de servicio que se van a deshabilitar y, a continuación, ejecute los comandos resultantes en el símbolo del sistema de PowerShell.

```powershell
$inFileName="<path and file name of the input CSV file that contains the users, example: C:\admin\Users2License.CSV>"
$outFileName="<path and file name of the output CSV file that records the results, example: C:\admin\Users2License-Done.CSV>"
$accountSkuId="<the AccountSkuId from the Get-MsolAccountSku command>"
$planList=@( <comma-separated, double-quote enclosed list of the plans to disable> )
$users=Import-Csv $inFileName
$licenseOptions=New-MsolLicenseOptions -AccountSkuId $accountSkuId -DisabledPlans $planList
ForEach ($user in $users)
{
$user.Userprincipalname
$upn=$user.UserPrincipalName
Set-MsolUserLicense -UserPrincipalName $upn -AddLicenses $accountSkuId -ErrorAction SilentlyContinue
sleep -Seconds 5
Set-MsolUserLicense -UserPrincipalName $upn -LicenseOptions $licenseOptions -ErrorAction SilentlyContinue
$users | Get-MsolUser | Select UserPrincipalName, Islicensed,Usagelocation | Export-Csv $outFileName
}
```

Este bloque de comandos de PowerShell:

- Muestra el nombre principal de usuario de cada usuario.

- Asigna licencias personalizadas a cada usuario.

- Crea un archivo CSV con todos los usuarios que se procesaron y muestra su estado de licencia.

## <a name="see-also"></a>Vea también

[Deshabilitar el acceso a los servicios de Microsoft 365 con PowerShell](disable-access-to-services-with-microsoft-365-powershell.md)

[Deshabilitar el acceso a Sway con PowerShell](disable-access-to-sway-with-microsoft-365-powershell.md)

[Administrar cuentas de usuario, licencias y grupos de Microsoft 365 con PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)

[Administrar Microsoft 365 con PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)