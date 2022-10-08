---
author: LanaChin
ms.author: v-lanachin
ms.date: ''
ms.topic: include
audience: admin
ms.service: microsoft-365-frontline
ms.openlocfilehash: 30186298f83ea1a1e1721b9dc31a77eb4af33975
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "68223488"
---
Puede ejecutar un informe que muestre los detalles del error de una conexión. En el informe se enumeran las asignaciones de usuario y de equipo que se realizaron correctamente y con errores. También proporciona información sobre los problemas relacionados con las cuentas asociadas a la conexión.

1. [Configure el entorno](#set-up-your-environment) (si aún no lo ha hecho).
1. Obtener una lista de informes de errores para una conexión.

    ``` powershell
    Get-CsTeamsShiftsConnectionErrorReport -ConnectorInstanceId <ConnectorInstanceId>
    ```

1. Para ver un informe de errores específico, ejecute el siguiente comando:

    ``` powershell
    Get-CsTeamsShiftsConnectionErrorReport -ErrorReportId <ErrorReportId>
    ```

Para obtener más información vea [Permisos](/powershell/module/teams/get-csteamsshiftsconnectionerrorreport).
