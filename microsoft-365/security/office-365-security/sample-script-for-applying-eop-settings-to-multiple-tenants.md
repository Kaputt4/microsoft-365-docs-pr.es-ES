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
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: e87e84e1-7be0-44bf-a414-d91d60ed8817
ms.custom:
- seo-marvel-apr2020
description: En este artículo, aprenderá a usar PowerShell para aplicar opciones de configuración a los inquilinos en Microsoft Exchange Online Protection (EOP).
ms.openlocfilehash: b18fc71171a93e2a2f415800bcf2b5abd5c5a526
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2020
ms.locfileid: "49615869"
---
# <a name="sample-script-for-applying-eop-settings-to-multiple-tenants"></a><span data-ttu-id="b51c1-103">Script de ejemplo para aplicar la configuración de EOP a varios inquilinos</span><span class="sxs-lookup"><span data-stu-id="b51c1-103">Sample script for applying EOP settings to multiple tenants</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="b51c1-104">El siguiente script de ejemplo permite que los administradores de Microsoft Exchange Online Protection (EOP) que administran varios inquilinos (empresas) usen Exchange Online PowerShell para ver o aplicar opciones de configuración a sus inquilinos.</span><span class="sxs-lookup"><span data-stu-id="b51c1-104">The following sample script lets Microsoft Exchange Online Protection (EOP) admins who manage multiple tenants (companies) use Exchange Online PowerShell to view and/or apply configuration settings to their tenants.</span></span>

## <a name="to-run-a-script-or-cmdlet-on-multiple-tenants"></a><span data-ttu-id="b51c1-105">Para ejecutar un script o un cmdlet en varios inquilinos:</span><span class="sxs-lookup"><span data-stu-id="b51c1-105">To run a script or cmdlet on multiple tenants</span></span>

1. <span data-ttu-id="b51c1-106">Si aún no lo ha hecho, [Instale el módulo Exchange Online versión 2](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module).</span><span class="sxs-lookup"><span data-stu-id="b51c1-106">If you haven't already, [install the Exchange Online V2 module](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module).</span></span>

2. <span data-ttu-id="b51c1-107">Con una aplicación de hoja de cálculo (por ejemplo, Excel), cree un archivo. csv con los siguientes detalles:</span><span class="sxs-lookup"><span data-stu-id="b51c1-107">Using an spreadsheet app (for example, Excel), create a .csv file with the following details:</span></span>

   - <span data-ttu-id="b51c1-108">Columna UserName: la cuenta que usará para conectarse (por ejemplo, `admin@contoso.onmicrosoft.com` ).</span><span class="sxs-lookup"><span data-stu-id="b51c1-108">UserName column: The account that you'll use to connect (for example, `admin@contoso.onmicrosoft.com`).</span></span>
   - <span data-ttu-id="b51c1-109">Columna de cmdlet: cmdlet o comando que se va a ejecutar (por ejemplo, `Get-AcceptedDomain` o `Get-AcceptedDomain | FT Name` ).</span><span class="sxs-lookup"><span data-stu-id="b51c1-109">Cmdlet column: The cmdlet or command to run (for example, `Get-AcceptedDomain` or `Get-AcceptedDomain | FT Name`).</span></span>

   <span data-ttu-id="b51c1-110">El archivo tendrá un aspecto similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="b51c1-110">The file will look like this:</span></span>

   ```text
   UserName,Cmdlet
   admin@contoso.onmicrosoft.com,Get-AcceptedDomain | FT Name
   admin@fabrikam.onmicrosoft.com,Get-AcceptedDomain | FT Name
   ```

3. <span data-ttu-id="b51c1-111">Guarde el archivo. csv en una ubicación fácil de encontrar (por ejemplo, c:\scripts\inputfile.csv).</span><span class="sxs-lookup"><span data-stu-id="b51c1-111">Save the .csv file in a location that's easy to find (for example, c:\scripts\inputfile.csv).</span></span>

4. <span data-ttu-id="b51c1-112">Copie el script [RunCmdletOnMultipleTenants.ps1](#runcmdletonmultipletenantsps1) en el Bloc de notas y, a continuación, guarde el archivo en una ubicación que sea fácil de encontrar (por ejemplo, c:\Scripts).</span><span class="sxs-lookup"><span data-stu-id="b51c1-112">Copy the [RunCmdletOnMultipleTenants.ps1](#runcmdletonmultipletenantsps1) script into Notepad, and then save the file to a location that's easy to find (for example, c:\scripts).</span></span>

5. <span data-ttu-id="b51c1-113">Ejecute el script con la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="b51c1-113">Run the script by using the following syntax:</span></span>

   ```powershell
   & "<file path>\RunCmdletOnMultipleTenants.ps1" "<file path>\inputfile.csv"
   ```

   <span data-ttu-id="b51c1-114">Aquí le mostramos un ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b51c1-114">Here's an example:</span></span>

   ```powershell
   & "c:\scripts\RunCmdletOnMultipleTenants.ps1" "c:\scripts\inputfile.csv"
   ```

6. <span data-ttu-id="b51c1-115">Se iniciará sesión en cada inquilino y se ejecutará el script.</span><span class="sxs-lookup"><span data-stu-id="b51c1-115">Each tenant will be logged on to, and the script will be run.</span></span>

## <a name="runcmdletonmultipletenantsps1"></a><span data-ttu-id="b51c1-116">RunCmdletOnMultipleTenants.ps1</span><span class="sxs-lookup"><span data-stu-id="b51c1-116">RunCmdletOnMultipleTenants.ps1</span></span>

> [!NOTE]
> <span data-ttu-id="b51c1-117">Es posible que deba modificar la `Connect-IPPSSession` línea del script para que sea igual que la del entorno.</span><span class="sxs-lookup"><span data-stu-id="b51c1-117">You might need to modify the `Connect-IPPSSession` line in the script to match your environment.</span></span> <span data-ttu-id="b51c1-118">Por ejemplo, Office 365 Germany requiere un valor _ConnectionUri_ diferente del valor actual en un script.</span><span class="sxs-lookup"><span data-stu-id="b51c1-118">For example, Office 365 Germany requires a different _ConnectionUri_ value than the current value in a script.</span></span> <span data-ttu-id="b51c1-119">Para obtener más información, vea Connect to [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="b51c1-119">For details, see Connect to [Exchange Online Powershell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

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
