---
author: LanaChin
ms.author: v-lanachin
ms.date: ''
ms.topic: include
audience: admin
ms.service: microsoft-365-frontline
ms.openlocfilehash: 348370981c75fd0ca435b5c7f58a96f5790df11b
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "68223466"
---
Para comprobar el estado de la conexión que configuró mediante el identificador de operación que recibió en el correo electrónico:

1. [Configure el entorno](#set-up-your-environment) (si aún no lo ha hecho).
1. Ejecuta el siguiente comando. Este comando proporciona el estado general de las asignaciones de equipo para la conexión.

    ``` powershell
    Get-CsTeamsShiftsConnectionOperation -OperationId <YourOperationId>
    ```

Para obtener más información, consulte [Get-CsTeamsShiftsConnectionOperation](/powershell/module/teams/get-csteamsshiftsconnectionoperation).
