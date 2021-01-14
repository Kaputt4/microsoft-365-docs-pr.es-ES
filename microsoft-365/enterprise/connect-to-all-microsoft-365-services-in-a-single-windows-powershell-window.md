---
title: Conectarse a todos los servicios de Microsoft 365 en una sola ventana de Windows PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/10/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- LIL_Placement
- Ent_Office_Other
- O365ITProTrain
- httpsfix
ms.assetid: 53d3eef6-4a16-4fb9-903c-816d5d98d7e8
description: 'Resumen: Conectarse a todos los servicios de Microsoft 365 en una sola ventana de Windows PowerShell.'
ms.openlocfilehash: 4266b4f216b4c9df48f0c19d1d2123269eb32cae
ms.sourcegitcommit: 00d231bf0100e843a5a93161695e87ceff9e1349
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/13/2021
ms.locfileid: "49849598"
---
# <a name="connect-to-all-microsoft-365-services-in-a-single-powershell-window"></a>Conectarse a todos los servicios de Microsoft 365 en una sola ventana de Windows PowerShell

Cuando usa PowerShell para administrar Microsoft 365, puede tener varias sesiones de PowerShell abiertas al mismo tiempo. Es posible que tenga distintas ventanas de PowerShell para administrar cuentas de usuario, SharePoint Online, Exchange Online, Skype empresarial online, Microsoft Teams y el centro de cumplimiento de &amp; seguridad.
  
Este escenario no es óptimo para la administración de Microsoft 365, porque no se pueden intercambiar datos entre esas ventanas para la administración entre servicios. Este artículo describe cómo usar una única instancia de PowerShell desde la que puede administrar cuentas de Microsoft 365, Skype empresarial online, Exchange Online, SharePoint Online, Microsoft Teams y el Centro de seguridad &amp; cumplimiento.

>[!Note]
>Actualmente, este artículo solo contiene los comandos para conectarse a la nube mundial (+GCC). Las notas brindan vínculos a artículos sobre cómo conectarse a otras nubes de Microsoft 365.

## <a name="before-you-begin"></a>Antes de empezar

Antes de poder administrar todo Microsoft 365 desde una sola instancia de Windows PowerShell, tenga en cuenta los siguientes requisitos previos:
  
- La cuenta profesional o educativa de Microsoft 365 que use debe ser un miembro del rol de administrador de Microsoft 365. Para obtener más información, vea [Sobre los roles de administrador](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles). Este es un requisito de PowerShell para Microsoft 365, pero no necesariamente para todos los demás servicios de Microsoft 365.
    
- Puede usar las siguientes versiones de Windows de 64 bits:
    
  - Windows 10
    
  - Windows 8.1 o Windows 8
    
  - Windows Server 2019
    
  - Windows Server 2016
    
  - Windows Server 2012 R2 o Windows Server 2012
    
  - Windows 7 Service Pack 1 (SP1)*
    
  - Windows Server 2008 R2 SP1*
    
    \* Debe instalar Microsoft .NET Framework 4.5.*x* y, después, Windows Management Framework 3.0 o 4.0. Para obtener más información, vea [Windows Management Framework](https://docs.microsoft.com/powershell/scripting/windows-powershell/wmf/overview?view=powershell-7).
    
    Debe usar una versión de 64 bits de Windows para cumplir los requisitos del módulo Skype Empresarial Online y uno de los módulos de Microsoft 365.
    
- Debe instalar los módulos necesarios para Azure Active Directory (Azure AD), Exchange Online, SharePoint Online, Skype Empresarial Online y Teams:
    
  - [Azure Active Directory V2](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
  - [Shell de administración de SharePoint Online](https://go.microsoft.com/fwlink/p/?LinkId=255251)
  - [Módulo Windows PowerShell para Skype Empresarial Online](https://docs.microsoft.com/microsoftteams/teams-powershell-overview)
  - [Exchange Online PowerShell V2](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exchange-online-powershell-v2-module)
  - [Descripción de PowerShell para Teams](https://docs.microsoft.com/microsoftteams/teams-powershell-overview)
    
-  PowerShell debe configurarse para ejecutar scripts firmados en Skype empresarial Online y en el Centro de seguridad &amp; cumplimiento. Ejecutar el siguiente comando en una sesión de PowerShell con privilegios elevados (una sesión de PowerShell que se abre seleccionando **Ejecutar como administrador**).
    
   ```powershell
   Set-ExecutionPolicy RemoteSigned
   ```

## <a name="exchange-online-and-security-amp-compliance-center-with-the-exchange-online-powershell-v2-module"></a>Exchange Online y Centro de seguridad &amp; cumplimiento con el módulo de Exchange Online PowerShell V2

Los procedimientos en este artículo utilizan el módulo PowerShell V2 de Exchange Online para conectarse tanto a Exchange Online como al Centro de seguridad &amp; cumplimiento. Pero actualmente no puede conectarse a ambos *en la misma ventana de PowerShell*. Así que tiene que elegir conectarse a uno u otro cuando configura una ventana de PowerShell para varios servicios de Microsoft 365.

## <a name="connection-steps-when-using-just-a-password"></a>Pasos de conexión al usar solo una contraseña

Siga estos pasos para conectarse a todos los servicios en una única ventana de PowerShell cuando use solo una contraseña para iniciar sesión.
  
1. Abra Windows PowerShell.
    
2. Ejecute este comando y escriba las credenciales de su cuenta profesional o educativa de Microsoft 365.
    
   ```powershell
   $credential = Get-Credential
   ```

3. Ejecute este comando para conectarse a Azure AD usando Azure Active Directory PowerShell para el módulo de Graph.
    
   ```powershell
   Connect-AzureAD -Credential $credential
   ```
  
   O si usa Microsoft Azure Active Directory para el módulo de Windows PowerShell, ejecute este comando.
      
   ```powershell
   Connect-MsolService -Credential $credential
   ```

   > [!Note]
   > PowerShell Core no es compatible con Microsoft Azure Active Directory para el módulo de Windows PowerShell ni los cmdlet que llevan *Msol* en su nombre. Debe ejecutar estos cmdlets desde PowerShell.

4. Ejecute estos comandos para conectarse a SharePoint Online. Especifique el nombre de la organización para su dominio. Por ejemplo, para "litwareinc\.onmicrosoft.com", el valor del nombre de la organización es "litwareinc".
    
   ```powershell
   $orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
   Connect-SPOService -Url https://$orgName-admin.sharepoint.com -Credential $Credential
   ```

5. Ejecute estos comandos para conectarse a Skype empresarial online. Se mostrará una advertencia sobre cómo aumentar el valor `WSMan NetworkDelayms` la primera vez que se conecte. Omítalo.
     
   > [!Note]
   > El conector en línea del cliente de Skype® Empresarial actualmente forma parte del módulo más reciente de Windows PowerShell de Teams. Si usa la versión pública más reciente de Teams PowerShell, no es necesario que instale el conector en línea de cliente de Skype® Empresarial.
   
   ```powershell
   Import-Module MicrosoftTeams
   $sfboSession = New-CsOnlineSession -Credential $credential
   Import-PSSession $sfboSession
   ```

6. Ejecute este comando para conectarse a Exchange Online.
    
   ```powershell
   Import-Module ExchangeOnlineManagement
   Connect-ExchangeOnline -Credential $credential -ShowProgress $true
   ```

   > [!Note]
   > Para conectarse a Exchange Online para las nubes de Microsoft 365 que no sean mundiales, consulte [Conectarse a Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

   Como alternativa, ejecute estos comandos para conectarse al Centro de seguridad &amp; cumplimiento.
    
   ```powershell
   $acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
   Import-Module ExchangeOnlineManagement
   Connect-IPPSSession -UserPrincipalName $acctName
   ```

   > [!Note]
   > Para conectarse al Centro de seguridad &amp; cumplimiento para nubes de Microsoft 365 que no sean mundiales, vea [Conectarse al Centro de seguridad y cumplimiento de PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).

   Ejecute estos comandos para conectarse a Teams PowerShell.
    
   ```powershell
   Import-Module MicrosoftTeams
   Connect-MicrosoftTeams -Credential $credential
   ```
  
   > [!Note]
   > Para conectarse a nubes de Microsoft Teams que no sean *mundiales*, consulte [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams).


### <a name="azure-active-directory-powershell-for-graph-module"></a>Azure Active Directory PowerShell para el módulo de Graph

Estos son los comandos para todos los servicios *excepto el Centro de seguridad &amp; cumplimiento* en un único bloque al usar Azure Active Directory PowerShell para el módulo de Graph. Especifique el nombre del host de su dominio y ejecútelo todos a la vez.
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$credential = Get-Credential
Connect-AzureAD -Credential $credential
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
Import-Module MicrosoftTeams
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -Credential $credential -ShowProgress $true
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

Estos son los comandos para todos los servicios *excepto Exchange Online* en un único bloque al usar Azure Active Directory PowerShell para el módulo de Graph. Especifica el nombre del host de su dominio y el UPN para el inicio de sesión y, a continuación, ejecútelos todos a la vez.
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$credential = Get-Credential -UserName $acctName
Connect-AzureAD -Credential $credential
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
Import-Module MicrosoftTeams
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
Import-Module ExchangeOnlineManagement
Connect-IPPSSession -UserPrincipalName $acctName
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

### <a name="microsoft-azure-active-directory-module-for-windows-powershell-module"></a>Microsoft Azure Active Directory para el módulo de Windows PowerShell

Estos son los comandos para todos los servicios *excepto el Centro de seguridad &amp; cumplimiento* en un único bloque al usar el Módulo Microsoft Azure Active Directory para el módulo de Windows PowerShell. Especifique el nombre del host de su dominio y ejecútelo todos en un momento.
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$credential = Get-Credential
Connect-MsolService -Credential $credential
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
Import-Module MicrosoftTeams
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -Credential $credential -ShowProgress $true
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

Estos son los comandos para todos los servicios *excepto Exchange Online* en un único bloque al usar Microsoft Azure Active Directory para el módulo de Windows PowerShell. Especifique el nombre del host de su dominio y el UPN para el inicio de sesión y, a continuación, ejecútelos todos a la vez.
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$credential = Get-Credential -UserName $acctName
Connect-AzureAD -Credential $credential
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
Import-Module MicrosoftTeams
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
Import-Module ExchangeOnlineManagement
Connect-IPPSSession -UserPrincipalName $acctName
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```
## <a name="connection-steps-when-using-multi-factor-authentication"></a>Pasos de conexión al usar autenticación multifactor

### <a name="azure-active-directory-powershell-for-graph-module"></a>Módulo de Azure Active Directory PowerShell para Graph

Estos son todos los comandos en un único bloque para conectarse a varios servicios de Microsoft 365 *excepto el Centro de seguridad &amp; cumplimiento* al usar la autenticación multifactor mediante de Azure Active Directory PowerShell para el módulo de Graph.

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-AzureAD
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
Import-Module MicrosoftTeams
$sfboSession = New-CsOnlineSession
Import-PSSession $sfboSession
#Exchange Online
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```
Estos son todos los comandos en un único bloque para conectarse a varios servicios de Microsoft 365 *excepto Exchange Online* con autenticación multifactor al usar Azure Active Directory PowerShell para el módulo de Graph.

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-AzureAD
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
Import-Module MicrosoftTeams
$sfboSession = New-CsOnlineSession
Import-PSSession $sfboSession
#Security & Compliance Center
Import-Module ExchangeOnlineManagement
Connect-IPPSSession -UserPrincipalName $acctName
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```
### <a name="microsoft-azure-active-directory-module-for-windows-powershell-module"></a>Microsoft Azure Active Directory para el módulo de Windows PowerShell

Estos son todos los comandos en un único bloque para conectarse a varios servicios de Microsoft 365 *excepto el Centro de seguridad &amp; cumplimiento* al usar la autenticación multifactor mediante Microsoft Azure Active Directory para el módulo de Windows PowerShell.

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-MsolService
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
Import-Module MicrosoftTeams
$sfboSession = New-CsOnlineSession
Import-PSSession $sfboSession
#Exchange Online
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```
Estos son todos los comandos en un único bloque para conectarse a varios servicios de Microsoft 365 *excepto Exchange Online* al usar la autenticación multifactor con Microsoft Azure Active Directory para el módulo de Windows PowerShell.

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-MsolService
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
Import-Module MicrosoftTeams
$sfboSession = New-CsOnlineSession
Import-PSSession $sfboSession
#Security & Compliance Center
Import-Module ExchangeOnlineManagement
Connect-IPPSSession -UserPrincipalName $acctName
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```

## <a name="close-the-powershell-window"></a>Cerrar la ventana de PowerShell

Para cerrar la ventana de PowerShell, ejecute este comando para quitar las sesiones activas de Skype empresarial online, SharePoint Online y Teams:
  
```powershell
Remove-PSSession $sfboSession ; Disconnect-SPOService ; Disconnect-MicrosoftTeams 
```

## <a name="see-also"></a>Consulte también

- [Conectarse a Microsoft 365 con PowerShell](connect-to-microsoft-365-powershell.md)
- [Administrar SharePoint Online con PowerShell](manage-sharepoint-online-with-microsoft-365-powershell.md)
- [Administrar cuentas de usuario, licencias y grupos de Microsoft 365 con PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
