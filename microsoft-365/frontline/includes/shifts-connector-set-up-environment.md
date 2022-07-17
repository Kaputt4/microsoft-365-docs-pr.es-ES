---
author: LanaChin
ms.author: v-lanachin
ms.date: 03/31/2022
ms.topic: include
audience: admin
ms.service: msteams
ms.openlocfilehash: 3d4ec38f0007460fa119e69eadc79cd9c51887ee
ms.sourcegitcommit: 5e5c2c1f7c321b5eb1c5b932c03bdd510005de13
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/15/2022
ms.locfileid: "66822600"
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

    Compruebe que es al menos la versión 4.1.0 y que contiene los cmdlets del conector Shifts.

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