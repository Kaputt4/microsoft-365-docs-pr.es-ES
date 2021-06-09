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
ms.openlocfilehash: 431e6cb3b8d7ab7e1dd317918fab4821889c7d4e
ms.sourcegitcommit: 583fd1ac1f385c58b93bda648907a1bd8e0a1950
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2020
ms.locfileid: "45430464"
---
# <a name="get-started-with-app-control"></a>Introducción al control de aplicaciones

Antes de habilitar el control de aplicaciones en el entorno, asegúrate de revisar y comprender cómo [Escritorio administrado de Microsoft lo implementa](../service-description/app-control.md) y tus roles y responsabilidades.

Escritorio administrado de Microsoft simplifica el control de aplicaciones al ocuparse de los aspectos más difíciles de obtener una directiva base segura. Los administradores de TI aún deben probar las aplicaciones en el anillo de prueba y revisar los registros en busca de advertencias o errores. Si una aplicación necesita una exención, puedes presentar una solicitud o Escritorio administrado de Microsoft operación, según quién la detecte primero.

## <a name="initial-deployment-of-apps"></a>Implementación inicial de aplicaciones

Al implementar aplicaciones por primera vez, Escritorio administrado de Microsoft debe evaluar su comportamiento actual. Los pasos exactos para habilitar el control de aplicaciones dependen de si los dispositivos ya se han implementado en el entorno.

### <a name="devices-not-yet-in-use"></a>Dispositivos que aún no están en uso

Si aún no tienes ningún dispositivo en uso, abre un vale de servicio con Escritorio administrado de Microsoft Operations solicitando que activemos el control de la aplicación. Las operaciones implementarán de forma progresiva directivas en grupos de implementación siguiendo esta programación:

|Grupo de implementación  |Tipo de directiva  |Timing  |
|---------|---------|---------|
|Prueba     |  Auditoría       |  Día 0       |
|Primero     | Enforced        | Día 1        |
|Rápida     | Enforced        |  Día 2       |
|Amplias     | Enforced        |  Día 3       |

Siempre puede abrir otra solicitud de servicio para pausar o revertir parte de esta implementación en cualquier momento durante el lanzamiento.

### <a name="devices-already-in-use"></a>Dispositivos que ya están en uso

Si ya tiene al menos Escritorio administrado de Microsoft dispositivo en uso, siga estos pasos:

1. Abra un vale de servicio con Escritorio administrado de Microsoft operaciones solicitando que activemos el control de la aplicación. Las operaciones implementarán una [directiva de auditoría](../service-description/app-control.md#audit-policy) en todos los dispositivos.
2. [Pruebe las aplicaciones](../working-with-managed-desktop/work-with-app-control.md#add-a-new-app) para ver si se bloquearía alguna. Si se bloquearía una aplicación, abra una [solicitud de firmante](../working-with-managed-desktop/work-with-app-control.md#add-or-remove-a-trusted-signer). 
3. Una vez que haya completado las pruebas (independientemente de los resultados), notifique a Operaciones y notifique las solicitudes de firmante pendientes. Las operaciones implementarán de forma progresiva directivas en grupos de implementación siguiendo esta programación:

|Grupo de implementación  |Tipo de directiva  |Timing  |
|---------|---------|---------|
|Prueba     |  Auditoría       |  Día 0       |
|Primero     | Enforced        | Día 1        |
|Rápida     | Enforced        |  Paused, rollout on request       |
|Amplias     | Enforced        |  Paused, rollout on request       |

Siempre puede abrir otra solicitud de servicio para pausar o revertir parte de esta implementación en cualquier momento durante el lanzamiento.



