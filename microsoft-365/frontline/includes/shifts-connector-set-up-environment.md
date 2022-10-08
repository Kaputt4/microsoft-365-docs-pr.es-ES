---
author: LanaChin
ms.author: v-lanachin
ms.date: 03/31/2022
ms.topic: include
audience: admin
ms.service: microsoft-365-frontline
ms.openlocfilehash: 7415d4dfd8d6a7a1935d9aca2e04726f7b929996
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "68222614"
---
1. Instale PowerShell versión 7 o posterior. Para obtener instrucciones paso a paso, consulte [Instalar PowerShell en Windows](/powershell/scripting/install/installing-powershell-on-windows).

1. Ejecute PowerShell en modo de administrador.
1. Instalar el módulo de PowerShell de Microsoft Graph.

    ```powershell
    Install-Module Microsoft.Graph
    Import-Module Microsoft.Graph
    ```

    Compruebe que es la versión 1.6.1 o posterior.

    ```powershell
    Get-InstalledModule Microsoft.Graph 
    ```

1. Instalar el módulo de PowerShell de Teams en versión preliminar.

    ```powershell
    Install-Module -Name MicrosoftTeams -AllowPrerelease -Force
    Import-Module MicrosoftTeams 
    ```

    Compruebe que es al menos la versión 4.7.0 y contiene los cmdlets del conector Shifts.

    ```powershell
    Get-Command -Module MicrosoftTeams -Name *teamsshiftsconnection* 
    ```

1. Establezca PowerShell para salir si se produce un error al ejecutar el script.

    ```powershell
    $ErrorActionPreference = "Stop" 
    ```

1. Habilitación de la ejecución de scripts en Windows.

    ```powershell
    Set-ExecutionPolicy bypass 
    ```