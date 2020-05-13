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
# <a name="sample-script-for-applying-eop-settings-to-multiple-tenants"></a>Script de ejemplo para aplicar la configuración de EOP a varios inquilinos

El script de ejemplo siguiente permite a los administradores de Microsoft Exchange Online Protection (EOP) que administran varios inquilinos (compañías) aplicar en estos opciones de configuración con Windows PowerShell.

## <a name="to-run-a-script-or-cmdlet-on-multiple-tenants"></a>Para ejecutar un script o un cmdlet en varios inquilinos:

1. Cree un archivo .csv (por ejemplo, c:\scripts\inputfile.csv) con una aplicación como Excel:

2. En este archivo, especifique dos nombres de columna: UserName y Cmdlet.

3. En cada fila del archivo .csv, agregue el nombre de administrador del inquilino en la columna UserName y el cmdlet que debe ejecutarse para dicho inquilino en la columna Cmdlet. Por ejemplo, admin@contoso.com y Get-AcceptedDomain.

4. Copie el script [RunCmdletOnMultipleTenants. PS1](#runcmdletonmultipletenantsps1) en el Bloc de notas y, a continuación, guarde el archivo en una ubicación que sea fácil de encontrar (por ejemplo, c:\Scripts).

5. Ejecute el script con la sintaxis siguiente:

   ```powershell
   & "<file path>\RunCmdletOnMultipleTenants.ps1" "<file path>\inputfile.csv"
   ```

   Aquí le mostramos un ejemplo:

   ```powershell
   & "c:\scripts\RunCmdletOnMultipleTenanats.ps1" "c:\scripts\inputfile.csv"
   ```

6. Se iniciará sesión en cada inquilino y se ejecutará el script.

## <a name="runcmdletonmultipletenantsps1"></a>RunCmdletOnMultipleTenants. ps1

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
