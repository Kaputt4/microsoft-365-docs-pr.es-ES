---
title: Deshabilitar el acceso a Microsoft 365 servicios con PowerShell
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 07/27/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Ent_Office_Other
- PowerShell
- LIL_Placement
- seo-marvel-apr2020
ms.assetid: 264f4f0d-e2cd-44da-a9d9-23bef250a720
description: En este artículo, aprenderá a usar PowerShell para deshabilitar el acceso a Microsoft 365 servicios para los usuarios.
ms.openlocfilehash: eeb3c8dc0057318550a956d0d0f4f916f4515fd4
ms.sourcegitcommit: dc415d784226c77549ba246601f34324c4f94e73
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/19/2022
ms.locfileid: "64915871"
---
# <a name="disable-access-to-microsoft-365-services-with-powershell"></a>Deshabilitar el acceso a Microsoft 365 servicios con PowerShell

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

Cuando a una cuenta de Microsoft 365 se le asigna una licencia de un plan de licencias, Microsoft 365 servicios están disponibles para el usuario a partir de esa licencia. Sin embargo, puede controlar los servicios de Microsoft 365 a los que el usuario puede acceder. Por ejemplo, aunque la licencia permite el acceso al servicio SharePoint Online, puede deshabilitar el acceso a él. Puede usar PowerShell para deshabilitar el acceso a cualquier número de servicios para un plan de licencias específico para:

- Una cuenta individual.
- Un grupo de cuentas.
- Todas las cuentas de su organización.

>[!Note]
>Hay Microsoft 365 dependencias de servicio que pueden impedir que se deshabilite un servicio especificado cuando otros servicios dependen de él.
>

## <a name="use-the-microsoft-graph-powershell-sdk"></a>Uso del SDK de PowerShell de Microsoft Graph

En primer lugar, [conéctese al inquilino de Microsoft 365](/graph/powershell/get-started#authentication).

La asignación y eliminación de licencias para un usuario requiere el ámbito de permisos User.ReadWrite.All o uno de los demás permisos enumerados en la [página de referencia "Asignar licencia" Graph API](/graph/api/user-assignlicense).

El ámbito de permisos Organization.Read.All es necesario para leer las licencias disponibles en el inquilino.

```powershell
Connect-Graph -Scopes User.ReadWrite.All, Organization.Read.All
```

A continuación, use este comando para ver los planes de licencia disponibles, también conocidos como SkuPartNumber:

```powershell
Get-MgSubscribedSku | Select SkuId, SkuPartNumber, ServicePlans | Sort SkuPartNumber
```

Para obtener más información, consulte [Visualización de licencias y servicios con PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).

Para ver los resultados antes y después de los procedimientos de este tema, consulte [Ver detalles de licencia de cuenta y servicio con PowerShell](view-account-license-and-service-details-with-microsoft-365-powershell.md).

### <a name="disable-specific-microsoft-365-services-for-specific-users-for-a-specific-licensing-plan"></a>Deshabilitación de servicios de Microsoft 365 específicos para usuarios específicos para un plan de licencias específico
  
Para deshabilitar un conjunto específico de servicios de Microsoft 365 para los usuarios para un plan de licencias específico, siga estos pasos:
  
#### <a name="step-1-identify-the-undesired-services-in-the-licensing-plan-by-using-the-following-syntax"></a>Paso 1: Identificar los servicios no deseados en el plan de licencias mediante la sintaxis siguiente:

En primer lugar, enumere los planes de licencia disponibles en el inquilino mediante el siguiente comando.

```powershell
Get-MgSubscribedSku | Select SkuPartNumber

SkuPartNumber
-------------
EMSPREMIUM
SPE_E5
RIGHTSMANAGEMENT_ADHOC

```

A continuación, use SkuPartNumber del comando anterior y enumere los planes de servicio disponibles para un plan de licencia (SKU) determinado.

En el ejemplo siguiente se enumeran todos los planes de servicio disponibles para **SPE_E5** (Microsoft 365 E5).

```powershell
Get-MgSubscribedSku -All | Where SkuPartNumber -eq 'SPE_E5' |  select -ExpandProperty ServicePlans
```

```text
AppliesTo ProvisioningStatus ServicePlanId                        ServicePlanName
--------- ------------------ -------------                        ---------------
User      Success            b21a6b06-1988-436e-a07b-51ec6d9f52ad PROJECT_O365_P3
User      Success            64bfac92-2b17-4482-b5e5-a0304429de3e MICROSOFTENDPOINTDLP
User      Success            199a5c09-e0ca-4e37-8f7c-b05d533e1ea2 MICROSOFTBOOKINGS
User      Success            6db1f1db-2b46-403f-be40-e39395f08dbb CUSTOMER_KEY
User      Success            4a51bca5-1eff-43f5-878c-177680f191af WHITEBOARD_PLAN3
User      Success            07699545-9485-468e-95b6-2fca3738be01 FLOW_O365_P3
User      Success            9c0dab89-a30c-4117-86e7-97bda240acd2 POWERAPPS_O365_P3
User      Success            e212cbc7-0961-4c40-9825-01117710dcb1 FORMS_PLAN_E5
User      Success            57ff2da0-773e-42df-b2af-ffb7a2317929 TEAMS1
User      Success            21b439ba-a0ca-424f-a6cc-52f954a5b111 WIN10_PRO_ENT_SUB
User      Success            eec0eb4f-6444-4f95-aba0-50c24d67f998 AAD_PREMIUM_P2
User      Success            c1ec4a95-1f05-45b3-a911-aa3fa01094f5 INTUNE_A
User      Success            7547a3fe-08ee-4ccb-b430-5077c5041653 YAMMER_ENTERPRISE
User      Success            a23b959c-7ce8-4e57-9140-b90eb88a9e97 SWAY
User      Success            e95bec33-7c88-4a70-8e19-b10bd9d0c014 SHAREPOINTWAC
User      Success            5dbe027f-2339-4123-9542-606e4d348a72 SHAREPOINTENTERPRISE
User      Success            b737dad2-2f6c-4c65-90e3-ca563267e8b9 PROJECTWORKMANAGEMENT
User      Success            43de0ff5-c92c-492b-9116-175376d08c38 OFFICESUBSCRIPTION
User      Success            0feaeb32-d00e-4d66-bd5a-43b5b83db82c MCOSTANDARD
User      Success            9f431833-0334-42de-a7dc-70aa40db46db LOCKBOX_ENTERPRISE
User      Success            efb87545-963c-4e0d-99df-69c6916d9eb0 EXCHANGE_S_ENTERPRISE
```

Para obtener una lista completa de los planes de licencia (también conocidos como nombres de producto), sus planes de servicio incluidos y sus nombres descriptivos [correspondientes, consulte Nombres de producto e identificadores de plan de servicio para licencias](/azure/active-directory/users-groups-roles/licensing-service-plan-reference). (Busque mediante ServicePlanId para buscar el nombre descriptivo correspondiente del plan de servicio).

En el ejemplo siguiente se asignan **SPE_E5** (Microsoft 365 E5) con los servicios **MICROSOFTBOOKINGS** (Microsoft Bookings) y **LOCKBOX_ENTERPRISE** (Caja de seguridad del cliente) desactivados:
  
```powershell
$e5Sku = Get-MgSubscribedSku -All | Where SkuPartNumber -eq 'SPE_E5'
$disabledPlans = $e5Sku.ServicePlans | `
    Where ServicePlanName -in ("LOCKBOX_ENTERPRISE", "MICROSOFTBOOKINGS") | `
    Select -ExpandProperty ServicePlanId

$addLicenses = @(
    @{
        SkuId = $e5Sku.SkuId
        DisabledPlans = $disabledPlans
    }
)

Set-MgUserLicense -UserId "belinda@litwareinc.com" -AddLicenses $addLicenses -RemoveLicenses @()
```

La propiedad DisabledPlans del parámetro AddLicenses de Set-MgUserLicense sobrescribirá el valor disabledPlans existente del usuario. Para conservar el estado de los planes de servicio existentes, el estado actual de los planes de servicio del usuario debe combinarse con los nuevos planes que se van a deshabilitar.

Si no se incluyen los planes deshabilitados existentes, se habilitará el plan deshabilitado anteriormente del usuario.

En el ejemplo siguiente se actualiza un usuario con **SPE_E5** (Microsoft 365 E5) y se desactivan los planes de servicio Sway y Forms al dejar los planes deshabilitados existentes del usuario en su estado actual:
  
```powershell
## Get the services that have already been disabled for the user.
$userLicense = Get-MgUserLicenseDetail -UserId "belinda@fdoau.onmicrosoft.com"
$userDisabledPlans = $userLicense.ServicePlans | `
    Where ProvisioningStatus -eq "Disabled" | `
    Select -ExpandProperty ServicePlanId

## Get the new service plans that are going to be disabled
$e5Sku = Get-MgSubscribedSku -All | Where SkuPartNumber -eq 'SPE_E5'
$newDisabledPlans = $e5Sku.ServicePlans | `
    Where ServicePlanName -in ("SWAY", "FORMS_PLAN_E5") | `
    Select -ExpandProperty ServicePlanId

## Merge the new plans that are to be disabled with the user's current state of disabled plans
$disabledPlans = ($userDisabledPlans + $newDisabledPlans) | Select -Unique

$addLicenses = @(
    @{
        SkuId = $e5Sku.SkuId
        DisabledPlans = $disabledPlans
    }
)
## Update user's license
Set-MgUserLicense -UserId "belinda@litwareinc.onmicrosoft.com" -AddLicenses $addLicenses -RemoveLicenses @()
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Use el Módulo Microsoft Azure Active Directory para Windows PowerShell

En primer lugar, [conéctese al inquilino de Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).

A continuación, use este comando para ver los planes de licencia disponibles, también conocidos como AccountSkuIds:

```powershell
Get-MsolAccountSku | Select AccountSkuId | Sort AccountSkuId
```

>[!Note]
>PowerShell Core no es compatible con el Módulo Microsoft Azure Active Directory para Windows PowerShell ni los cmdlet que llevan **Msol** en su nombre. Para seguir usando estos cmdlets, debe ejecutarlos desde Windows PowerShell.
>

Para obtener más información, consulte [Visualización de licencias y servicios con PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).
    
Para ver los resultados antes y después de los procedimientos de este tema, consulte [Ver detalles de licencia de cuenta y servicio con PowerShell](view-account-license-and-service-details-with-microsoft-365-powershell.md).
    
Hay un script de PowerShell que automatiza los procedimientos descritos en este tema. En concreto, el script le permite ver y deshabilitar los servicios de la organización de Microsoft 365, incluidos los Sway. Para obtener más información, vea [Deshabilitar el acceso a Sway con PowerShell](disable-access-to-sway-with-microsoft-365-powershell.md).
    
    
### <a name="disable-specific-microsoft-365-services-for-specific-users-for-a-specific-licensing-plan"></a>Deshabilitación de servicios de Microsoft 365 específicos para usuarios específicos para un plan de licencias específico
  
Para deshabilitar un conjunto específico de servicios de Microsoft 365 para los usuarios para un plan de licencias específico, siga estos pasos:
  
#### <a name="step-1-identify-the-undesired-services-in-the-licensing-plan-by-using-the-following-syntax"></a>Paso 1: Identificar los servicios no deseados en el plan de licencias mediante la sintaxis siguiente:
    
```powershell
$LO = New-MsolLicenseOptions -AccountSkuId <AccountSkuId> -DisabledPlans "<UndesiredService1>", "<UndesiredService2>"...
```

En el ejemplo siguiente se crea un objeto **LicenseOptions** que deshabilita los servicios Office y SharePoint Online en el plan de licencias denominado `litwareinc:ENTERPRISEPACK` (Office 365 Enterprise E3).
    
```powershell
$LO = New-MsolLicenseOptions -AccountSkuId "litwareinc:ENTERPRISEPACK" -DisabledPlans "SHAREPOINTWAC", "SHAREPOINTENTERPRISE"
```

#### <a name="step-2-use-the-licenseoptions-object-from-step-1-on-one-or-more-users"></a>Paso 2: Use el objeto **LicenseOptions** del paso 1 en uno o varios usuarios.
    
Para crear una nueva cuenta con los servicios deshabilitados, use la sintaxis siguiente:
    
```powershell
New-MsolUser -UserPrincipalName <Account> -DisplayName <DisplayName> -FirstName <FirstName> -LastName <LastName> -LicenseAssignment <AccountSkuId> -LicenseOptions $LO -UsageLocation <CountryCode>
```

En el ejemplo siguiente se crea una nueva cuenta para Allie Bellew que asigna la licencia y deshabilita los servicios descritos en el paso 1.
    
```powershell
New-MsolUser -UserPrincipalName allieb@litwareinc.com -DisplayName "Allie Bellew" -FirstName Allie -LastName Bellew -LicenseAssignment litwareinc:ENTERPRISEPACK -LicenseOptions $LO -UsageLocation US
```

Para obtener más información sobre cómo crear cuentas de usuario en PowerShell para Microsoft 365, consulte [Creación de cuentas de usuario con PowerShell](create-user-accounts-with-microsoft-365-powershell.md).
    
Para deshabilitar los servicios para un usuario con licencia existente, use la siguiente sintaxis:
    
```powershell
Set-MsolUserLicense -UserPrincipalName <Account> -LicenseOptions $LO
```

En este ejemplo se deshabilitan los servicios para el usuario BelindaN@litwareinc.com.
    
```powershell
Set-MsolUserLicense -UserPrincipalName belindan@litwareinc.com -LicenseOptions $LO
```

Para deshabilitar los servicios descritos en el paso 1 para todos los usuarios con licencia existentes, especifique el nombre del plan de Microsoft 365 desde la presentación del cmdlet **Get-MsolAccountSku** (como **litwareinc:ENTERPRISEPACK**) y, a continuación, ejecute los siguientes comandos:
    
```powershell
$acctSKU="<AccountSkuId>"
$AllLicensed = Get-MsolUser -All | Where {$_.isLicensed -eq $true -and $_.licenses.AccountSku.SkuPartNumber -contains ($acctSKU).Substring($acctSKU.IndexOf(":")+1, $acctSKU.Length-$acctSKU.IndexOf(":")-1)}
$AllLicensed | ForEach {Set-MsolUserLicense -UserPrincipalName $_.UserPrincipalName -LicenseOptions $LO}
```

 Si usa el cmdlet **Get-MsolUser** sin usar el parámetro _All_ , solo se devuelven las primeras 500 cuentas de usuario.

Para deshabilitar los servicios para un grupo de usuarios existentes, use cualquiera de los métodos siguientes para identificar a los usuarios:
    
**Método 1. Filtrar las cuentas en función de un atributo de cuenta existente** 

Para ello, utilice la siguiente sintaxis:
    
```powershell
$x = Get-MsolUser -All <FilterableAttributes>
$x | ForEach {Set-MsolUserLicense -UserPrincipalName $_.UserPrincipalName -LicenseOptions $LO}
```

En el ejemplo siguiente se deshabilitan los servicios para los usuarios del departamento de ventas de la Estados Unidos.
    
```powershell
$USSales = Get-MsolUser -All -Department "Sales" -UsageLocation "US"
$USSales | ForEach {Set-MsolUserLicense -UserPrincipalName $_.UserPrincipalName -LicenseOptions $LO}
```

**Método 2: Usar una lista de cuentas específicas** 

Para ello, siga estos pasos:
    
1. Cree un archivo de texto que contenga una cuenta en cada línea como en el ejemplo:
    
   ```powershell
   akol@contoso.com
   tjohnston@contoso.com
   kakers@contoso.com
   ```

   En este ejemplo, el archivo de texto es C:\\My Documents\\Accounts.txt.
    
2. Ejecute el siguiente comando:
    
   ```powershell
   Get-Content "C:\My Documents\Accounts.txt" | foreach {Set-MsolUserLicense -UserPrincipalName $_ -LicenseOptions $LO}
   ```

Si desea deshabilitar el acceso a los servicios para varios planes de licencia, repita las instrucciones anteriores para cada plan de licencias, asegurándose de que:

- A las cuentas de usuario se les ha asignado el plan de licencias.
- Los servicios que se van a deshabilitar están disponibles en el plan de licencias.

Para deshabilitar Microsoft 365 servicios para los usuarios mientras los asigna a un plan de licencias, consulte [Deshabilitar el acceso a los servicios al asignar licencias de usuario](disable-access-to-services-while-assigning-user-licenses.md).

### <a name="assign-all-services-in-a-licensing-plan-to-a-user-account"></a>Asignación de todos los servicios de un plan de licencias a una cuenta de usuario

Para las cuentas de usuario que han tenido servicios deshabilitados, puede habilitar todos los servicios para un plan de licencias específico con estos comandos:

```powershell
$userUPN="<user account UPN>"
$acctSKU="<AccountSkuId>"
$LO = New-MsolLicenseOptions -AccountSkuId $acctSKU
Set-MsolUserLicense -UserPrincipalName $userUPN -LicenseOptions $LO
```

## <a name="related-topic"></a>Tema relacionado

[Administrar cuentas de usuario, licencias y grupos de Microsoft 365 con PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Administrar Microsoft 365 con PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Introducción a PowerShell para Microsoft 365](getting-started-with-microsoft-365-powershell.md)
