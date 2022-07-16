---
author: LanaChin
ms.author: v-lanachin
ms.date: 03/31/2022
ms.topic: include
audience: admin
ms.service: msteams
ms.openlocfilehash: ab375a876eb62e5f41e5dd7cda3743d4010b95ff
ms.sourcegitcommit: 5e5c2c1f7c321b5eb1c5b932c03bdd510005de13
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/15/2022
ms.locfileid: "66822587"
---
Antes de empezar, asegúrese de que tiene los siguientes requisitos previos:

- Blue Yonder WFM versión 2020.3, 2021.1 o 2021.2.

    > [!NOTE]
    > Si tiene Blue Yonder WFM 2020.3 o 2021.1, aplique la revisión 2020.3.0.4 o 2021.1.0.3. Esta revisión corrige un problema por el que los usuarios reciben un mensaje de error persistente en Turnos. También corrige un problema que impide que los usuarios actualicen su disponibilidad en Turnos.

- El nombre de la cuenta de servicio de Blue Yonder WFM y las direcciones URL de servicio y contraseña:

    - URL de autenticación federada
    - URL de autenticación de cookie
    - URL de autoservicio para empleados
    - URL de la API del comercio minorista
    - URL de la API del administrador del sitio
    - URL de la API de administración

    Si no tiene esta información, póngase en contacto con el soporte técnico de Blue Yonder. Un administrador de empresa de Blue Yonder crea la cuenta en el nivel de empresa raíz. Debe tener acceso a la API, al Administrador de cliente y al Administrador de la tienda. La cuenta y la contraseña son necesarias para crear una conexión.
- La autenticación de SSO federado está habilitada en el entorno de WFM de Blue Yonder. Póngase en contacto con el soporte técnico de Blue Yonder para asegurarse de que el SSO federado está habilitado. Necesitarán la información siguiente:

    - federatedSSOValidationService: `https://wfmconnector.teams.microsoft.com/api/v1/fedauth/{tenantId}/6A51B888-FF44-4FEA-82E1-839401E9CD74/authorize` donde {tenantId} es su tenantId
     - proxyHeader: X-MS-AuthToken

- Al menos un equipo configurado en Teams.
- Ha agregado su cuenta del sistema de Microsoft 365 como propietario del equipo a todos los equipos que quiere asignar.</br> [Cree esta cuenta en Microsoft 365](/microsoft-365/admin/add-users/add-users) y asígnele una licencia de Microsoft 365. Después, agregue la cuenta como propietario de un equipo a todos los equipos que quiera asignar. El conector de Turnos usa esta cuenta al sincronizar los cambios de Turnos de WFM de Blue Yonder.

    Se recomienda crear una cuenta específicamente para este propósito y no usar su cuenta de usuario.