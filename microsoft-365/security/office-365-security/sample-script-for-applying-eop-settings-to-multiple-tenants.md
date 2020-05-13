---
title: 'Script de ejemplo para la configuración de EOP: varios inquilinos'
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: e87e84e1-7be0-44bf-a414-d91d60ed8817
ms.custom:
- seo-marvel-apr2020
description: En este artículo, aprenderá a usar PowerShell para aplicar opciones de configuración a los inquilinos en Microsoft Exchange Online Protection (EOP).
ms.openlocfilehash: c25bafe9ece71264931d8f059dd726147a6d28a4
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209144"
---
# <a name="sample-script-for-applying-eop-settings-to-multiple-tenants"></a><span data-ttu-id="455ad-103">Script de ejemplo para aplicar la configuración de EOP a varios inquilinos</span><span class="sxs-lookup"><span data-stu-id="455ad-103">Sample script for applying EOP settings to multiple tenants</span></span>

<span data-ttu-id="455ad-104">El script de ejemplo siguiente permite a los administradores de Microsoft Exchange Online Protection (EOP) que administran varios inquilinos (compañías) aplicar en estos opciones de configuración con Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="455ad-104">The following sample script lets Microsoft Exchange Online Protection (EOP) admins who manage multiple tenants (companies) use Windows PowerShell to apply configuration settings to their tenants.</span></span>

## <a name="to-run-a-script-or-cmdlet-on-multiple-tenants"></a><span data-ttu-id="455ad-105">Para ejecutar un script o un cmdlet en varios inquilinos:</span><span class="sxs-lookup"><span data-stu-id="455ad-105">To run a script or cmdlet on multiple tenants</span></span>

1. <span data-ttu-id="455ad-106">Cree un archivo .csv (por ejemplo, c:\scripts\inputfile.csv) con una aplicación como Excel:</span><span class="sxs-lookup"><span data-stu-id="455ad-106">Using an application such as Excel, create a .csv file (for example, c:\scripts\inputfile.csv):</span></span>

2. <span data-ttu-id="455ad-107">En este archivo, especifique dos nombres de columna: UserName y Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="455ad-107">In the .csv file, specify two column names: UserName and Cmdlet.</span></span>

3. <span data-ttu-id="455ad-p101">En cada fila del archivo .csv, agregue el nombre de administrador del inquilino en la columna UserName y el cmdlet que debe ejecutarse para dicho inquilino en la columna Cmdlet. Por ejemplo, admin@contoso.com y Get-AcceptedDomain.</span><span class="sxs-lookup"><span data-stu-id="455ad-p101">For each row in the .csv file, add the tenant's admin name in the UserName column and the cmdlet to run for that tenant in the Cmdlet column. For example, use admin@contoso.com and Get-AcceptedDomain.</span></span>

4. <span data-ttu-id="455ad-110">Copie el script [RunCmdletOnMultipleTenants. PS1](#runcmdletonmultipletenantsps1) en el Bloc de notas y, a continuación, guarde el archivo en una ubicación que sea fácil de encontrar (por ejemplo, c:\Scripts).</span><span class="sxs-lookup"><span data-stu-id="455ad-110">Copy the [RunCmdletOnMultipleTenants.ps1](#runcmdletonmultipletenantsps1) script into Notepad, and then save the file to a location that's easy to find  (for example, c:\scripts).</span></span>

5. <span data-ttu-id="455ad-111">Ejecute el script con la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="455ad-111">Run the script by using the following syntax:</span></span>

   ```powershell
   & "<file path>\RunCmdletOnMultipleTenants.ps1" "<file path>\inputfile.csv"
   ```

   <span data-ttu-id="455ad-112">Aquí le mostramos un ejemplo:</span><span class="sxs-lookup"><span data-stu-id="455ad-112">Here's an example:</span></span>

   ```powershell
   & "c:\scripts\RunCmdletOnMultipleTenanats.ps1" "c:\scripts\inputfile.csv"
   ```

6. <span data-ttu-id="455ad-113">Se iniciará sesión en cada inquilino y se ejecutará el script.</span><span class="sxs-lookup"><span data-stu-id="455ad-113">Each tenant will be logged on to, and the script will be run.</span></span>

## <a name="runcmdletonmultipletenantsps1"></a><span data-ttu-id="455ad-114">RunCmdletOnMultipleTenants. ps1</span><span class="sxs-lookup"><span data-stu-id="455ad-114">RunCmdletOnMultipleTenants.ps1</span></span>

```powershell
# This script runs Windows PowerShell cmdlets on multiple tenants.
# Usage: RunCmdletOnMultipleTenants.ps1 inputfile.csv
#
# .csv input file sample:
# UserName,Cmdlet
# admin@contoso.com,Get-AcceptedDomain | ft Name
# URI for connecting to remote Windows PowerShell
$URI = "https://ps.protection.outlook.com/powershell-liveid/"
# Get the .csv file name as an argument to this script.
$FilePath = $args[0]
# Import the UserName and Cmdlet values from the .csv file.
$CompanyList = Import-CSV $FilePath
# Loop through each entry from the .csv file.
ForEach ($Company in $CompanyList) {
# Get the current entry's UserName.
$UserName = $Company.UserName
# Get the current entry's Cmdlet.
$Cmdlet = $Company.Cmdlet
# Create a PowerShell credential object by using the current entry's UserName. Prompt for the password.
$UserCredential = Get-Credential -username $UserName
# Log on to a new Windows PowerShell session.
$Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri $URI -Credential $UserCredential -Authentication Basic -AllowRedirection
Import-PSSession $Session
# Here's where the script to be run on the tenant goes.
# In this example, the cmdlet in the .csv file runs.
Invoke-Expression $Cmdlet
# End the current PowerShell session.
Remove-PsSession -Session $Session
}
```
