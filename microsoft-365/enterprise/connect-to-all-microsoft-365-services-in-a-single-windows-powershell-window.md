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
ms.openlocfilehash: e4cb3a10d14f6d4c16ef9323d6e5b3c500ebc0c5
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/12/2020
ms.locfileid: "47545979"
---
# <a name="connect-to-all-microsoft-365-services-in-a-single-powershell-window"></a>Conectarse a todos los servicios de Microsoft 365 en una sola ventana de Windows PowerShell

Cuando usa PowerShell para administrar Microsoft 365, es posible tener varias sesiones de Windows PowerShell abiertas al mismo tiempo en diferentes ventanas de Windows PowerShell, que corresponden al manejo de cuentas de usuario, SharePoint Online, Exchange Online, Skype Empresarial Online, Microsoft Teams y el Centro de seguridad &amp; cumplimiento. 
  
Esto no es ideal para la administración de Microsoft 365 porque no podemos intercambiar datos entre esas ventanas para la administración entre servicios. Este tema describe cómo usar una única instancia de Windows PowerShell desde la que puede administrar cuentas de Microsoft 365, Skype Empresarial Online, Exchange Online, SharePoint Online, Microsoft Teams y el Centro de seguridad &amp; cumplimiento.

>[!Note]
>Actualmente, este artículo solo contiene los comandos para conectarse a la nube mundial (+GCC). Las notas brindan vínculos a artículos que explican cómo conectarse a otras nubes de Microsoft 365.
>

## <a name="before-you-begin"></a>Antes de empezar

Antes de poder administrar todo Microsoft 365 desde una sola instancia de Windows PowerShell, tenga en cuenta los siguientes requisitos previos:
  
- La cuenta profesional o educativa de Microsoft 365 que use para estos procedimientos tiene que ser un miembro del rol de administrador de Microsoft 365. Para obtener más información, vea [Asignar roles de administrador](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles). Este es un requisito de PowerShell para Microsoft 365, no necesariamente para todos los demás servicios de Microsoft 365.
    
- Puede usar las siguientes versiones de Windows de 64 bits:
    
  - Windows 10
    
  - Windows 8.1 o Windows 8
    
  - Windows Server 2019
    
  - Windows Server 2016
    
  - Windows Server 2012 R2 o Windows Server 2012
    
  - Windows 7 Service Pack 1 (SP1)*
    
  - Windows Server 2008 R2 SP1*
    
    \* Es necesario instalar Microsoft .NET Framework 4.5.*x* y, luego, Windows Management Framework 3.0 o Windows Management Framework 4.0. Para más información, consulte [Instalación de .NET Framework](https://go.microsoft.com/fwlink/p/?LinkId=257868) y [Windows Management Framework 3.0](https://go.microsoft.com/fwlink/p/?LinkId=272757) o [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/p/?LinkId=391344).
    
    Debe usar una versión de 64 bits de Windows para cumplir los requisitos del módulo Skype Empresarial Online y uno de los módulos de Microsoft 365.
    
- Debe instalar los módulos necesarios para Azure Active Directory (Azure AD), Exchange Online, SharePoint Online, Skype Empresarial Online y Teams:
    
  - [Azure Active Directory V2](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
  - [Shell de administración de SharePoint Online](https://go.microsoft.com/fwlink/p/?LinkId=255251)
  - [Módulo Windows PowerShell para Skype Empresarial Online](https://go.microsoft.com/fwlink/p/?LinkId=532439)
  - [Exchange Online PowerShell V2](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exchange-online-powershell-v2-module)
  - [Descripción de PowerShell para Teams](https://docs.microsoft.com/microsoftteams/teams-powershell-overview)
    
-  Windows PowerShell necesita configurarse para ejecutar scripts firmados en Skype Empresarial Online y en el Centro de seguridad &amp; cumplimiento. Para ello, ejecute el siguiente comando en una sesión de Windows PowerShell con privilegios elevados (es decir, una ventana de Windows PowerShell que se abre seleccionando **Ejecutar como administrador**).
    
   ```powershell
   Set-ExecutionPolicy RemoteSigned
   ```

## <a name="exchange-online-and-security-amp-compliance-center-with-the-exchange-online-powershell-v2-module"></a>Exchange Online y Centro de seguridad &amp; cumplimiento con el módulo de Exchange Online PowerShell V2

En este artículo, se usa el módulo de Exchange Online PowerShell V2 para conectarse a Exchange Online y al Centro de seguridad &amp; cumplimiento. Sin embargo, en este momento no puede conectarse al mismo tiempo a Exchange Online y al Centro de seguridad &amp; cumplimiento **en la misma ventana de PowerShell**.

Por lo tanto, al configurar una ventana de PowerShell para varios servicios de Microsoft 365, debe elegir una conexión o bien con Exchange Online *o* con el Centro de seguridad &amp; cumplimiento.

## <a name="connection-steps-when-using-just-a-password"></a>Pasos de conexión al usar solo una contraseña

Estos son los pasos para conectarse a todos los servicios en una única ventana de PowerShell cuando se usa solo una contraseña para iniciar sesión.
  
1. Abra Windows PowerShell.
    
2. Ejecute este comando y escriba las credenciales de su cuenta profesional o educativa de Microsoft 365.
    
   ```powershell
   $credential = Get-Credential
   ```

3. Ejecute este comando para conectarse a Azure AD con el módulo Azure Active Directory PowerShell para Graph.
    
   ```powershell
   Connect-AzureAD -Credential $credential
   ```
  
   Si usa el Módulo Microsoft Azure Active Directory para Windows PowerShell, también puede ejecutar este comando.
      
   ```powershell
   Connect-MsolService -Credential $credential
   ```

   > [!Note]
   > PowerShell Core no es compatible con el Módulo Microsoft Azure Active Directory para Windows PowerShell ni los cmdlet que llevan **Msol** en su nombre. Para seguir usando estos cmdlets, debe ejecutarlos desde Windows PowerShell.

4. Ejecute estos comandos para conectarse a SharePoint Online. Especifique el nombre de la organización para su dominio. Por ejemplo, para "litwareinc.onmicrosoft.com", el valor del nombre de la organización es "litwareinc".
    
   ```powershell
   $orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
   Connect-SPOService -Url https://$orgName-admin.sharepoint.com -Credential $userCredential
   ```

5. Ejecute estos comandos para conectarse a Skype Empresarial Online. La primera vez que se conecte, verá una advertencia sobre el aumento del valor `WSMan NetworkDelayms` que debe omitir.
     
   ```powershell
   Import-Module SkypeOnlineConnector
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

7. Como alternativa, puede ejecutar estos comandos para conectarse al Centro de seguridad &amp; cumplimiento.
    
   ```powershell
   $acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
   Import-Module ExchangeOnlineManagement
   Connect-IPPSSession -UserPrincipalName $acctName
   ```

   > [!Note]
   > Para conectarse al Centro de seguridad &amp; cumplimiento para nubes de Microsoft 365 que no sean mundiales, vea [Conectarse al Centro de seguridad y cumplimiento de PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).

8. Ejecute estos comandos para conectarse a Teams PowerShell.
    
   ```powershell
   Import-Module MicrosoftTeams
   Connect-MicrosoftTeams -Credential $credential
   ```
  
   > [!Note]
   > Para conectarse a nubes de Microsoft Teams que no sean mundiales, consulte [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams).


### <a name="azure-active-directory-powershell-for-graph-module"></a>Módulo de Azure Active Directory PowerShell para Graph

Estos son los comandos para todos los servicios *excepto el Centro de seguridad &amp; cumplimiento* en un único bloque al usar el módulo de Azure Active Directory PowerShell para Graph. Especifique el nombre del host de su dominio y, a continuación, ejecútelos todos a la vez.
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$credential = Get-Credential
Connect-AzureAD -Credential $credential
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
Import-Module SkypeOnlineConnector
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -Credential $credential -ShowProgress $true
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

Estos son los comandos para todos los servicios *excepto Exchange Online* en un único bloque al usar el módulo de Azure Active Directory PowerShell para Graph. Especifique el nombre del host de su dominio y el UPN para el inicio de sesión y, a continuación, ejecútelos todos a la vez.
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$credential = Get-Credential -UserName $acctName
Connect-AzureAD -Credential $credential
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
Import-Module SkypeOnlineConnector
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
Import-Module ExchangeOnlineManagement
Connect-IPPSSession -UserPrincipalName $acctName
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

### <a name="microsoft-azure-active-directory-module-for-windows-powershell-module"></a>Módulo Microsoft Azure Active Directory para el módulo de Windows PowerShell

Estos son los comandos para todos los servicios *excepto el Centro de seguridad &amp; cumplimiento* en un único bloque al usar el Módulo Microsoft Azure Active Directory para el módulo de Windows PowerShell. Especifique el nombre del host de su dominio y, a continuación, ejecútelos todos a la vez.
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$credential = Get-Credential
Connect-MsolService -Credential $credential
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
Import-Module SkypeOnlineConnector
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -Credential $credential -ShowProgress $true
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

Estos son los comandos para todos los servicios *excepto Exchange Online* en un único bloque al usar el Módulo Microsoft Azure Active Directory para el módulo de Windows PowerShell. Especifique el nombre del host de su dominio y el UPN para el inicio de sesión y, a continuación, ejecútelos todos a la vez.
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$credential = Get-Credential -UserName $acctName
Connect-AzureAD -Credential $credential
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
Import-Module SkypeOnlineConnector
$sfboSession = New-CsOnlineSession -Credential $credential
Import-PSSession $sfboSession
Import-Module ExchangeOnlineManagement
Connect-IPPSSession -UserPrincipalName $acctName
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```
## <a name="connection-steps-when-using-multi-factor-authentication"></a>Pasos de conexión al usar autenticación multifactor

### <a name="azure-active-directory-powershell-for-graph-module"></a>Módulo de Azure Active Directory PowerShell para Graph

Estos son todos los comandos de un único bloque para conectarse a varios servicios de Microsoft 365 *excepto el Centro de seguridad &amp; cumplimiento* con autenticación multifactor mediante el módulo de Azure Active Directory PowerShell para Graph.

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-AzureAD
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
$sfboSession = New-CsOnlineSession -UserName $acctName
Import-PSSession $sfboSession
#Exchange Online
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```
Estos son todos los comandos de un único bloque para conectarse a varios servicios de Microsoft 365 *excepto Exchange Online* con autenticación multifactor mediante el módulo de Azure Active Directory PowerShell para Graph.

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-AzureAD
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
$sfboSession = New-CsOnlineSession -UserName $acctName
Import-PSSession $sfboSession
#Security & Compliance Center
Import-Module ExchangeOnlineManagement
Connect-IPPSSession -UserPrincipalName $acctName
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```
### <a name="microsoft-azure-active-directory-module-for-windows-powershell-module"></a>Módulo Microsoft Azure Active Directory para el módulo de Windows PowerShell

Estos son todos los comandos de un único bloque para conectarse a varios servicios de Microsoft 365 *excepto el Centro de seguridad &amp; cumplimiento* con autenticación multifactor mediante el Módulo Microsoft Azure Active Directory para el módulo de Windows PowerShell.

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-MsolService
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
$sfboSession = New-CsOnlineSession -UserName $acctName
Import-PSSession $sfboSession
#Exchange Online
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```
Estos son todos los comandos de un único bloque para conectarse a varios servicios de Microsoft 365 *excepto Exchange Online* mediante autenticación multifactor con el Módulo Microsoft Azure Active Directory para el módulo de Windows PowerShell.

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-MsolService
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Skype for Business Online
$sfboSession = New-CsOnlineSession -UserName $acctName
Import-PSSession $sfboSession
#Security & Compliance Center
Import-Module ExchangeOnlineManagement
Connect-IPPSSession -UserPrincipalName $acctName
#Teams
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```

## <a name="close-the-powershell-window"></a>Cerrar la ventana de PowerShell

Cuando esté listo para cerrar la ventana de Windows PowerShell, ejecute este comando para quitar las sesiones activas de Skype Empresarial Online, SharePoint Online y Teams:
  
```powershell
Remove-PSSession $sfboSession ; Disconnect-SPOService ; Disconnect-MicrosoftTeams 
```


## <a name="see-also"></a>Consulte también

- [Conectarse a Microsoft 365 con PowerShell](connect-to-microsoft-365-powershell.md)
- [Administrar SharePoint Online con PowerShell](manage-sharepoint-online-with-microsoft-365-powershell.md)
- [Administrar cuentas de usuario, licencias y grupos de Microsoft 365 con PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
