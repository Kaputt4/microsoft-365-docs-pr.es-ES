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
ms.openlocfilehash: 77a1dce25901845628f8148c44a0d0783088255e
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2021
ms.locfileid: "51207386"
---
# <a name="sample-script-for-applying-eop-settings-to-multiple-tenants"></a><span data-ttu-id="393c9-103">Script de ejemplo para aplicar la configuración de EOP a varios inquilinos</span><span class="sxs-lookup"><span data-stu-id="393c9-103">Sample script for applying EOP settings to multiple tenants</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="393c9-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="393c9-104">**Applies to**</span></span>
-  [<span data-ttu-id="393c9-105">Exchange Online Protection independiente</span><span class="sxs-lookup"><span data-stu-id="393c9-105">Exchange Online Protection standalone</span></span>](exchange-online-protection-overview.md)

<span data-ttu-id="393c9-106">El siguiente script de ejemplo permite Microsoft Exchange Online Protection (EOP) administradores que administran varios inquilinos (empresas) usan Exchange Online PowerShell para ver o aplicar opciones de configuración a sus inquilinos.</span><span class="sxs-lookup"><span data-stu-id="393c9-106">The following sample script lets Microsoft Exchange Online Protection (EOP) admins who manage multiple tenants (companies) use Exchange Online PowerShell to view and/or apply configuration settings to their tenants.</span></span>

## <a name="to-run-a-script-or-cmdlet-on-multiple-tenants"></a><span data-ttu-id="393c9-107">Para ejecutar un script o un cmdlet en varios inquilinos:</span><span class="sxs-lookup"><span data-stu-id="393c9-107">To run a script or cmdlet on multiple tenants</span></span>

1. <span data-ttu-id="393c9-108">Si aún no lo ha hecho, [instale el módulo Exchange Online V2](/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module).</span><span class="sxs-lookup"><span data-stu-id="393c9-108">If you haven't already, [install the Exchange Online V2 module](/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module).</span></span>

2. <span data-ttu-id="393c9-109">Con una aplicación de hoja de cálculo (por ejemplo, Excel), cree un archivo .csv con los siguientes detalles:</span><span class="sxs-lookup"><span data-stu-id="393c9-109">Using an spreadsheet app (for example, Excel), create a .csv file with the following details:</span></span>

   - <span data-ttu-id="393c9-110">Columna UserName: la cuenta que usará para conectarse (por ejemplo, `admin@contoso.onmicrosoft.com` ).</span><span class="sxs-lookup"><span data-stu-id="393c9-110">UserName column: The account that you'll use to connect (for example, `admin@contoso.onmicrosoft.com`).</span></span>
   - <span data-ttu-id="393c9-111">Columna cmdlet: cmdlet o comando que se debe ejecutar (por ejemplo, `Get-AcceptedDomain` o `Get-AcceptedDomain | FT Name` ).</span><span class="sxs-lookup"><span data-stu-id="393c9-111">Cmdlet column: The cmdlet or command to run (for example, `Get-AcceptedDomain` or `Get-AcceptedDomain | FT Name`).</span></span>

   <span data-ttu-id="393c9-112">El archivo tendrá este aspecto:</span><span class="sxs-lookup"><span data-stu-id="393c9-112">The file will look like this:</span></span>

   ```text
   UserName,Cmdlet
   admin@contoso.onmicrosoft.com,Get-AcceptedDomain | FT Name
   admin@fabrikam.onmicrosoft.com,Get-AcceptedDomain | FT Name
   ```

3. <span data-ttu-id="393c9-113">Guarde el archivo .csv en una ubicación fácil de encontrar (por ejemplo, c:\scripts\inputfile.csv).</span><span class="sxs-lookup"><span data-stu-id="393c9-113">Save the .csv file in a location that's easy to find (for example, c:\scripts\inputfile.csv).</span></span>

4. <span data-ttu-id="393c9-114">Copie el [ scriptRunCmdletOnMultipleTenants.ps1](#runcmdletonmultipletenantsps1) en el Bloc de notas y, a continuación, guarde el archivo en una ubicación fácil de encontrar (por ejemplo, c:\scripts).</span><span class="sxs-lookup"><span data-stu-id="393c9-114">Copy the [RunCmdletOnMultipleTenants.ps1](#runcmdletonmultipletenantsps1) script into Notepad, and then save the file to a location that's easy to find (for example, c:\scripts).</span></span>

5. <span data-ttu-id="393c9-115">Ejecute el script con la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="393c9-115">Run the script by using the following syntax:</span></span>

   ```powershell
   & "<file path>\RunCmdletOnMultipleTenants.ps1" "<file path>\inputfile.csv"
   ```

   <span data-ttu-id="393c9-116">Aquí le mostramos un ejemplo:</span><span class="sxs-lookup"><span data-stu-id="393c9-116">Here's an example:</span></span>

   ```powershell
   & "c:\scripts\RunCmdletOnMultipleTenants.ps1" "c:\scripts\inputfile.csv"
   ```

6. <span data-ttu-id="393c9-117">Todos los inquilinos iniciarán sesión y se ejecutará el script.</span><span class="sxs-lookup"><span data-stu-id="393c9-117">Each tenant will be logged on to, and the script will be run.</span></span>

## <a name="runcmdletonmultipletenantsps1"></a><span data-ttu-id="393c9-118">RunCmdletOnMultipleTenants.ps1</span><span class="sxs-lookup"><span data-stu-id="393c9-118">RunCmdletOnMultipleTenants.ps1</span></span>

> [!NOTE]
> <span data-ttu-id="393c9-119">Es posible que deba modificar la `Connect-IPPSSession` línea del script para que coincida con el entorno.</span><span class="sxs-lookup"><span data-stu-id="393c9-119">You might need to modify the `Connect-IPPSSession` line in the script to match your environment.</span></span> <span data-ttu-id="393c9-120">Por ejemplo, Office 365 Germany requiere un valor _ConnectionUri_ diferente al valor actual de un script.</span><span class="sxs-lookup"><span data-stu-id="393c9-120">For example, Office 365 Germany requires a different _ConnectionUri_ value than the current value in a script.</span></span> <span data-ttu-id="393c9-121">Para obtener más información, vea Connect to [Exchange Online Powershell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="393c9-121">For details, see Connect to [Exchange Online Powershell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

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