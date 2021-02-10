---
title: 'Script de ejemplo para la configuración de EOP: varios inquilinos'
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: e87e84e1-7be0-44bf-a414-d91d60ed8817
ms.custom:
- seo-marvel-apr2020
description: En este artículo, aprenderá a usar PowerShell para aplicar opciones de configuración a los inquilinos en Microsoft Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b7d856a7cec3bddc32455ba3afadf0323ddce935
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166596"
---
# <a name="sample-script-for-applying-eop-settings-to-multiple-tenants"></a>Script de ejemplo para aplicar la configuración de EOP a varios inquilinos

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
-  [Exchange Online Protection independiente](https://go.microsoft.com/fwlink/?linkid=2148611)

El siguiente script de ejemplo permite a los administradores de Microsoft Exchange Online Protection (EOP) que administran varios inquilinos (empresas) usar Exchange Online PowerShell para ver o aplicar opciones de configuración a sus inquilinos.

## <a name="to-run-a-script-or-cmdlet-on-multiple-tenants"></a>Para ejecutar un script o un cmdlet en varios inquilinos:

1. Si aún no lo ha hecho, [instale el módulo Exchange Online V2](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module).

2. Con una aplicación de hoja de cálculo (por ejemplo, Excel), cree un archivo .csv con los siguientes detalles:

   - Columna UserName: la cuenta que usará para conectarse (por ejemplo, `admin@contoso.onmicrosoft.com` ).
   - Columna de cmdlet: cmdlet o comando que se debe ejecutar (por ejemplo, `Get-AcceptedDomain` o `Get-AcceptedDomain | FT Name` ).

   El archivo tendrá este aspecto:

   ```text
   UserName,Cmdlet
   admin@contoso.onmicrosoft.com,Get-AcceptedDomain | FT Name
   admin@fabrikam.onmicrosoft.com,Get-AcceptedDomain | FT Name
   ```

3. Guarde el archivo .csv en una ubicación que sea fácil de encontrar (por ejemplo, c:\scripts\inputfile.csv).

4. Copie el [ scriptRunCmdletOnMultipleTenants.ps1](#runcmdletonmultipletenantsps1) en el Bloc de notas y, a continuación, guarde el archivo en una ubicación que sea fácil de encontrar (por ejemplo, c:\scripts).

5. Ejecute el script con la sintaxis siguiente:

   ```powershell
   & "<file path>\RunCmdletOnMultipleTenants.ps1" "<file path>\inputfile.csv"
   ```

   Aquí le mostramos un ejemplo:

   ```powershell
   & "c:\scripts\RunCmdletOnMultipleTenants.ps1" "c:\scripts\inputfile.csv"
   ```

6. Cada inquilino tendrá una sesión iniciada y se ejecutará el script.

## <a name="runcmdletonmultipletenantsps1"></a>RunCmdletOnMultipleTenants.ps1

> [!NOTE]
> Es posible que deba modificar la `Connect-IPPSSession` línea del script para que coincida con su entorno. Por ejemplo, Office 365 Germany requiere un valor _ConnectionUri_ diferente del valor actual en un script. Para obtener más información, consulte Conectarse [a Exchange Online Powershell.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)

```powershell
# This script runs Windows PowerShell cmdlets on multiple tenants.
#
# Usage: RunCmdletOnMultipleTenants.ps1 inputfile.csv
#
# .csv input file sample:
#
# UserName,Cmdlet
# admin@contoso.onmicrosoft.com,Get-AcceptedDomain | FT Name
# admin@fabrikam.onmicrosoft.com,Get-AcceptedDomain | FT Name

# Get the .csv file name as an argument to this script.
$FilePath = $args[0]

# Import the UserName and Cmdlet values from the .csv file.
$CompanyList = Import-CSV $FilePath

# Load the EXO V2 module
Import-Module ExchangeOnlineManagement

# Loop through each entry from the .csv file.
ForEach ($Company in $CompanyList) {

# Get the current entry's UserName.
$UserName = $Company.UserName

# Get the current entry's Cmdlet.
$Cmdlet = $Company.Cmdlet

# Connect to EOP PowerShell by using the current entry's UserName. Prompt for the password.
Connect-IPPSSession -UserPrincipalName $UserName -ConnectionUri https://ps.protection.outlook.com/powershell-liveid/

# Here's where the script to be run on the tenant goes.
# In this example, the cmdlet in the .csv file runs.
Invoke-Expression $Cmdlet

# End the current PowerShell session.
Disconnect-ExchangeOnline -Confirm:$false
}
```
