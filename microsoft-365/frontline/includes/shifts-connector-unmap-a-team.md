---
author: LanaChin
ms.author: v-lanachin
ms.date: ''
ms.topic: include
audience: admin
ms.service: microsoft-365-frontline
ms.openlocfilehash: ec11ee0ed02d05da683caeb025e52522444d8215
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "68223444"
---
> [!NOTE]
> La cuenta del sistema de Microsoft 365 debe ser la misma para ambas conexiones. Si no es así, recibirá un mensaje de error "Este perfil de actor designado no tiene privilegios de propiedad de equipo".

Si desea desajustar un equipo de una conexión y asignarlo a otra conexión:

1. [Configure el entorno](#set-up-your-environment) (si aún no lo ha hecho).
1. Vea una lista de todas las asignaciones de equipo para una conexión.

    ```powershell
    Get-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId <ConnectorInstanceId>
    ```

1. Quite una asignación de equipo de la conexión.

    ```powershell
    Remove-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId <ConnectorInstanceId> -TeamId <TeamId>
    ```

1. Asigne el equipo a otra conexión.

    ```powershell
    New-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId <ConnectorInstanceId> -TeamId <TeamId> -WfmTeamId <SiteId> -TimeZone <TimeZone>
    ```

Para obtener más información, consulte [Get-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/get-csteamsshiftsconnectionteammap), [Remove-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/remove-csteamsshiftsconnectionteammap) y [New-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/new-csteamsshiftsconnectionteammap).
