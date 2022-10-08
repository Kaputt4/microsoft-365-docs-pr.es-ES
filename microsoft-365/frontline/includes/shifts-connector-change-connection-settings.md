---
author: LanaChin
ms.author: v-lanachin
ms.date: ''
ms.topic: include
audience: admin
ms.service: microsoft-365-frontline
ms.openlocfilehash: beabbc18474a4454fbcfa448b76898de8af14c1b
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "68223510"
---
Use este script para cambiar la configuración de conexión. La configuración que puede cambiar incluye la cuenta de servicio de WFM y la contraseña, la cuenta del sistema de Microsoft 365, las asignaciones de equipo y la configuración de sincronización.

La configuración de sincronización incluye la frecuencia de sincronización (en minutos) y los datos de programación que se sincronizan entre el sistema de WFM y shifts. Los datos de programación se definen en los parámetros siguientes, que puede ver mediante la ejecución de [Get-CsTeamsShiftsConnectionConnector](/powershell/module/teams/get-csteamsshiftsconnectionconnector).

- El parámetro **enabledConnectorScenarios** define los datos que se sincronizan desde el sistema de WFM a Turnos. Las opciones son `Shift`, `SwapRequest`, `UserShiftPreferences`, `OpenShift`, `OpenShiftRequest`, `TimeOff` `TimeOffRequest`.
- El parámetro **enabledWfiScenarios** define los datos que se sincronizan de Shifts con el sistema de WFM. Las opciones son `SwapRequest`, `OpenShiftRequest`, `TimeOffRequest`, `UserShiftPreferences`.

    > [!NOTE]
    > Si decide no sincronizar turnos abiertos, solicitudes de turnos abiertas, solicitudes de intercambio o solicitudes de tiempo de expiración entre turnos y el sistema de WFM, hay otro paso que debe hacer para ocultar la funcionalidad en Turnos. Después de ejecutar este script, asegúrese de seguir los pasos de la sección [Deshabilitar turnos abiertos, solicitudes de turnos abiertos, solicitudes de intercambio y solicitudes de tiempo de expiración](#disable-open-shifts-open-shifts-requests-swap-requests-and-time-off-requests) más adelante en este artículo.

> [!IMPORTANT]
> Para la configuración que no desea cambiar, tendrá que volver a escribir la configuración original cuando se le solicite el script.
