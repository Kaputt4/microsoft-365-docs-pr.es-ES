---
title: Introducción al control de aplicaciones
description: ''
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 12df7b074019ea47f2e293b71c6b0b25fe46f66f
ms.sourcegitcommit: 63887d742c59cc660fc85537b335e98a9dc66fbe
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/18/2020
ms.locfileid: "45170714"
---
# <a name="get-started-with-app-control"></a>Introducción al control de aplicaciones

Antes de habilitar el control de aplicaciones en el entorno, asegúrese de revisar y comprender [cómo Microsoft Managed Desktop lo implementa](../service-description/app-control.md) y sus roles y responsabilidades.

Microsoft Managed Desktop simplifica el control de aplicaciones, ya que se ocupa de los aspectos más desafiantes de obtener una directiva de base segura. Los administradores de TI todavía deben probar sus aplicaciones en el anillo de prueba y revisar los registros en busca de advertencias o errores. Si una aplicación necesita una exención, puede archivar una solicitud, o la operación de escritorio administrada de Microsoft podría, en función de quién la detecte primero.

## <a name="initial-deployment-of-apps"></a>Implementación inicial de aplicaciones

Cuando se implementan las aplicaciones por primera vez, las necesidades del escritorio administrado por Microsoft deben evaluar su comportamiento actual. Los pasos exactos para habilitar el control de aplicaciones dependen de si ya se han implementado los dispositivos en su entorno.

### <a name="devices-already-in-use"></a>Dispositivos que ya están en uso

Si ya tiene al menos un dispositivo de escritorio administrado de Microsoft en uso, siga estos pasos:

1. Abrir un vale de servicio con Microsoft Managed Desktop Operations solicitando que se active el control de aplicaciones. Operaciones implementará una [Directiva de auditoría](../service-description/app-control.md#audit-policy) para todos los dispositivos.
2. [Pruebe las aplicaciones](../working-with-managed-desktop/work-with-app-control.md#add-a-new-app) para ver si alguna se bloquea. Si se bloquea una aplicación, abra una [solicitud de firmante](../working-with-managed-desktop/work-with-app-control.md#add-or-remove-a-trusted-signer). 
3. Una vez que haya completado las pruebas (independientemente de los resultados), avise a las operaciones y anote las solicitudes de firma pendientes. Las operaciones implementarán progresivamente las directivas en los grupos de implementación siguiendo esta programación:

|Grupo de implementación  |Tipo de directiva  |Timing  |
|---------|---------|---------|
|Prueba     |  Auditoría       |  Día 0       |
|Primero     | Enforced        | Día 1        |
|Rápida     | Enforced        |  Día 3       |
|Amplias     | Enforced        |  Día 7       |

Siempre puede abrir otra solicitud de servicio para pausar o revertir una parte de esta implementación en cualquier momento durante la ejecución.

### <a name="devices-not-yet-in-use"></a>Dispositivos que todavía no están en uso

Si aún no tiene ningún dispositivo en uso, abra un vale de servicio con Microsoft Managed Desktop Operations solicitando que se active el control de aplicaciones. Las operaciones implementarán progresivamente las directivas en los grupos de implementación siguiendo esta programación:

|Grupo de implementación  |Tipo de directiva  |Timing  |
|---------|---------|---------|
|Prueba     |  Auditoría       |  Día 0       |
|Primero     | Enforced        | Día 1        |
|Rápida     | Enforced        |  Día 3       |
|Amplias     | Enforced        |  Día 7       |

Siempre puede abrir otra solicitud de servicio para pausar o revertir una parte de esta implementación en cualquier momento durante la ejecución.

