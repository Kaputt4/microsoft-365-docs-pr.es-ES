---
title: Conectarse a todos los servicios de Microsoft 365 en una sola ventana de Windows PowerShell
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 11/23/2021
audience: ITPro
ms.topic: article
ms.service: microsoft-365-enterprise
ms.localizationpriority: high
ms.collection:
- scotvorg
- Ent_O365
f1.keywords:
- CSH
ms.custom:
- LIL_Placement
- Ent_Office_Other
- O365ITProTrain
- httpsfix
ms.assetid: 53d3eef6-4a16-4fb9-903c-816d5d98d7e8
description: 'Resumen: Conectarse a todos los servicios de Microsoft 365 en una sola ventana de Windows PowerShell.'
ms.openlocfilehash: f252c963d0f3f654f116410f06be2401b2f8a4e0
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68199073"
---
# <a name="connect-to-all-microsoft-365-services-in-a-single-powershell-window"></a>Conectarse a todos los servicios de Microsoft 365 en una sola ventana de Windows PowerShell

Cuando usa PowerShell para administrar Microsoft 365, puede tener varias sesiones de PowerShell abiertas al mismo tiempo. Es posible que tenga diferentes ventanas de PowerShell para administrar cuentas de usuario, SharePoint Online, Exchange Online, Microsoft Teams, características de Microsoft Defender para Office 365 (seguridad) y características de cumplimiento de Microsoft Purview.

Este escenario no es óptimo para la administración de Microsoft 365, porque no se pueden intercambiar datos entre esas ventanas para la administración entre servicios. En este artículo se describe cómo usar una única instancia de PowerShell para administrar las cuentas de Microsoft 365, Exchange Online, SharePoint Online, Microsoft Teams y las características del cumplimiento de Defender para Office 365 Microsoft Purview.

>[!Note]
>Actualmente, este artículo solo contiene los comandos para conectarse a la nube mundial (+GCC). Las notas brindan vínculos a artículos sobre cómo conectarse a otras nubes de Microsoft 365.

## <a name="before-you-begin"></a>Antes de empezar

Antes de poder administrar todo Microsoft 365 desde una sola instancia de Windows PowerShell, tenga en cuenta los siguientes requisitos previos:

- La cuenta profesional o educativa de Microsoft 365 que use debe ser un miembro del rol de administrador de Microsoft 365. Para obtener más información, vea [Sobre los roles de administrador](../admin/add-users/about-admin-roles.md). Este es un requisito de PowerShell para Microsoft 365, pero no necesariamente para todos los demás servicios de Microsoft 365.

- Puede usar las siguientes versiones de Windows de 64 bits:
  - Windows 11
  - Windows 10
  - Windows 8.1 o Windows 8
  - Windows Server 2019
  - Windows Server 2016
  - Windows Server 2012 R2 o Windows Server 2012
  - Windows 7 Service Pack 1 (SP1)*
  - Windows Server 2008 R2 SP1*

    \* Debe instalar Microsoft .NET Framework 4.5.*x* y, después, Windows Management Framework 3.0 o 4.0. Para obtener más información, vea [Windows Management Framework](/powershell/scripting/windows-powershell/wmf/overview).

- Debe instalar los módulos necesarios para Azure Active Directory (Azure AD), Exchange Online, Defender para Office 365, cumplimiento de Microsoft Purview, SharePoint Online y Teams:

  - [Azure Active Directory V2](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
  - [Shell de administración de SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)
  - [Módulo de PowerShell de Teams](/microsoftteams/teams-powershell-overview)
  - [Instalación y mantenimiento del módulo de PowerShell Exchange Online](/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exchange-online-powershell-module)
  - [Descripción de PowerShell para Teams](/microsoftteams/teams-powershell-overview)

- PowerShell debe configurarse para ejecutar scripts firmados para Exchange Online, Defender para Office 365 y cumplimiento de Microsoft Purview. Ejecutar el siguiente comando en una sesión de PowerShell con privilegios elevados (una sesión de PowerShell que se abre seleccionando **Ejecutar como administrador**).

   ```powershell
   Set-ExecutionPolicy RemoteSigned
   ```

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

   > [!NOTE]
   > PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name. You must run these cmdlets from PowerShell.

4. Ejecute estos comandos para conectarse a SharePoint Online. Especifique el nombre de la organización para su dominio. Por ejemplo, para "litwareinc\.onmicrosoft.com", el valor del nombre de la organización es "litwareinc".

   ```powershell
   $orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
   Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
   Connect-SPOService -Url https://$orgName-admin.sharepoint.com -Credential $Credential
   ```

5. Ejecute estos comandos para conectarse a Exchange Online.

   ```powershell
   Import-Module ExchangeOnlineManagement
   Connect-ExchangeOnline -ShowProgress $true
   ```

   > [!Note]
   > Para conectarse a Exchange Online para las nubes de Microsoft 365 que no sean mundiales, consulte [Conectarse a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

6. Ejecute estos comandos para conectarse a Seguridad y cumplimiento de PowerShell.

   ```powershell
   $acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
   Connect-IPPSSession -UserPrincipalName $acctName
   ```

   > [!NOTE]
   > Para conectarse a Seguridad y cumplimiento de PowerShell para nubes de Microsoft 365 que no sean mundiales, consulte [Conectarse a Seguridad y cumplimiento de PowerShell](/powershell/exchange/connect-to-scc-powershell).

7. Ejecute estos comandos para conectarse a Teams PowerShell.

   ```powershell
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```

   > [!NOTE]
   > El conector en línea del cliente de Skype® Empresarial actualmente forma parte del módulo más reciente de Windows PowerShell de Teams. Si usa la versión pública más reciente de Teams PowerShell, no es necesario que instale el conector en línea de cliente de Skype® Empresarial.
   >
   > Para conectarse a nubes de Microsoft Teams que no sean *mundiales*, consulte [Connect-MicrosoftTeams](/powershell/module/teams/connect-microsoftteams).

### <a name="azure-active-directory-powershell-for-graph-module-when-using-just-a-password"></a>Azure Active Directory PowerShell para el módulo de Graph cuando se usa solo una contraseña

Estos son los comandos para todos los servicios en un único bloque al usar Azure Active Directory PowerShell para el módulo de Graph. Especifica el nombre del host de su dominio y el UPN para el inicio de sesión y, a continuación, ejecútelos todos a la vez.

```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$credential = Get-Credential -UserName $acctName -Message "Type the account's password."
#Azure Active Directory
Connect-AzureAD -Credential $credential
#SharePoint Online
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
#Exchange Online
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -ShowProgress $true
#Security & Compliance
Connect-IPPSSession -UserPrincipalName $acctName
#Teams and Skype for Business Online
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

### <a name="microsoft-azure-active-directory-module-for-windows-powershell-module-when-using-just-a-password"></a>Módulo Microsoft Azure Active Directory para Windows PowerShell cuando se usa solo una contraseña

Estos son los comandos para todos los servicios en un único bloque al usar el Módulo Microsoft Azure Active Directory para Windows PowerShell. Especifique el nombre del host de su dominio y el UPN para el inicio de sesión y, a continuación, ejecútelos todos a la vez.

```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$credential = Get-Credential -UserName $acctName -Message "Type the account's password."
#Azure Active Directory
Connect-MsolService -Credential $credential
#SharePoint Online
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
#Exchange Online
Connect-ExchangeOnline -ShowProgress $true
#Security & Compliance
Connect-IPPSSession -UserPrincipalName $acctName
#Teams and Skype for Business Online
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

## <a name="connection-steps-when-using-multi-factor-authentication"></a>Pasos de conexión al usar autenticación multifactor

### <a name="azure-active-directory-powershell-for-graph-module-when-using-mfa"></a>Azure Active Directory PowerShell para el módulo de Graph cuando se usa la autenticación multifactor

Estos son todos los comandos en un único bloque para conectarse a varios servicios de Microsoft 365 al usar la autenticación multifactor mediante el módulo de Azure Active Directory PowerShell para Graph.

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-AzureAD
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Exchange Online
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Security & Compliance
Connect-IPPSSession -UserPrincipalName $acctName
#Teams and Skype for Business Online
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```

### <a name="microsoft-azure-active-directory-module-for-windows-powershell-module-when-using-mfa"></a>Módulo Microsoft Azure Active Directory para Windows PowerShell cuando se usa la autenticación multifactor

Estos son todos los comandos en un único bloque para conectarse a varios servicios de Microsoft 365 al usar la autenticación multifactor con el Módulo Microsoft Azure Active Directory para Windows PowerShell.

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-MsolService
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Exchange Online
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Security & Compliance Center
Connect-IPPSSession -UserPrincipalName $acctName
#Teams and Skype for Business Online
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```

## <a name="close-the-powershell-window"></a>Cerrar la ventana de PowerShell

Para cerrar la ventana de PowerShell, ejecute este comando para quitar las sesiones activas de SharePoint Online, Teams, Defender para Office 365 y cumplimiento de Microsoft Purview:

```powershell
Disconnect-SPOService; Disconnect-MicrosoftTeams; Disconnect-ExchangeOnline
```

## <a name="see-also"></a>Consulte también

- [Conectarse a Microsoft 365 con PowerShell](connect-to-microsoft-365-powershell.md)
- [Administrar SharePoint Online con PowerShell](manage-sharepoint-online-with-microsoft-365-powershell.md)
- [Administrar cuentas de usuario, licencias y grupos de Microsoft 365 con PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
