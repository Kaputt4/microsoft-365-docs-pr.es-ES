---
author: LanaChin
ms.author: v-lanachin
ms.date: ''
ms.topic: include
audience: admin
ms.service: microsoft-365-frontline
ms.openlocfilehash: a411ff6608f09f7c5eff7f83dcc1dd3a98714378
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "68223422"
---
> [!IMPORTANT]
> Siga estos pasos solo si eligió deshabilitar turnos abiertos, solicitudes de turnos abiertos, solicitudes de intercambio o solicitudes de tiempo de expiración mediante el script de la sección [Cambiar configuración de conexión](#change-connection-settings) anteriormente en este artículo o mediante el cmdlet [Set-CsTeamsShiftsConnectionInstance](/powershell/module/teams/set-csteamsshiftsconnectioninstance). Al completar este paso, se oculta la funcionalidad en Turnos. Sin este segundo paso, los usuarios seguirán viendo la funcionalidad en Turnos y recibirán un mensaje de error de “operación no admitida” si intentan usarlo.

Para ocultar turnos abiertos, solicitudes de intercambio y solicitudes de tiempo de espera en Turnos, use el tipo de [recurso de programación](/graph/api/resources/schedule) Graph API para establecer los parámetros ```false``` siguientes en para cada equipo asignado a una instancia de WFM:

- Abrir turnos: ```openShiftsEnabled```
- Solicitudes de intercambio: ```swapShiftsRequestsEnabled```
- Solicitudes de tiempo de expiración: ```timeOffRequestsEnabled```

Para ocultar las solicitudes de turnos abiertos en Turnos, vaya a **Configuración** en Turnos y, a continuación, desactive la opción **Abrir turnos**.
