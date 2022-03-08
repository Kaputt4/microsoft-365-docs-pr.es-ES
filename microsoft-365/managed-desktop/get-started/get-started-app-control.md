---
title: Introducción al control de aplicaciones
description: En este artículo se describe cómo habilitar el control de aplicaciones
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: tiaraquan
ms.author: tiaraquan
manager: dougeby
audience: ITpro
ms.topic: article
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.openlocfilehash: a671bf36e957ffc416f51ec531aaeed6ddfa41b3
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2022
ms.locfileid: "63315405"
---
# <a name="get-started-with-app-control"></a>Introducción al control de aplicaciones

Antes de habilitar el control de aplicaciones en el entorno, asegúrese de revisar y comprender cómo lo implementa [Microsoft Managed Desktop](../service-description/app-control.md) y sus roles y responsabilidades.

Microsoft Managed Desktop simplifica el control de aplicaciones al ocuparse de los aspectos más difíciles de obtener una directiva base segura.

Los administradores de TI deben probar las aplicaciones en el anillo de prueba y revisar los registros en busca de advertencias o errores. Si una aplicación necesita una exención, puedes presentar una solicitud o la operación de escritorio administrado de Microsoft podría depender de quién la detecte primero.

## <a name="initial-deployment-of-apps"></a>Implementación inicial de aplicaciones

Al implementar aplicaciones por primera vez, Microsoft Managed Desktop debe evaluar su comportamiento actual. Los pasos exactos para habilitar el control de aplicaciones dependen de si los dispositivos ya se han implementado en el entorno.

### <a name="devices-not-yet-in-use"></a>Dispositivos que aún no están en uso

Si aún no tienes ningún dispositivo en uso, abre un vale de soporte técnico con Operaciones de escritorio administrado de Microsoft para solicitar que actives el control de aplicaciones. Las operaciones implementarán de forma progresiva directivas en grupos de implementación siguiendo esta programación:

| Grupo de implementación | Tipo de directiva | Timing |
| ------ | ------ | ------ |
| Prueba |  Auditoría |  Día 0 |
| Primero | Enforced | Día 1 |
| Rápida | Enforced |  Día 2 |
| Amplias | Enforced |  Día 3 |

Siempre puede abrir otra solicitud de soporte técnico para pausar o revertir parte de esta implementación en cualquier momento durante el lanzamiento.

### <a name="devices-already-in-use"></a>Dispositivos que ya están en uso

Si ya tiene al menos un dispositivo de Escritorio administrado de Microsoft en uso, siga estos pasos:

1. Abra un vale de servicio con Microsoft Managed Desktop Operations solicitando que activemos el control de aplicaciones. Las operaciones implementarán una [directiva de auditoría](../service-description/app-control.md#audit-policy) en todos los dispositivos.
2. [Pruebe las aplicaciones](../working-with-managed-desktop/work-with-app-control.md#add-a-new-app) para ver si se bloquearía alguna. Si se bloquearía una aplicación, abra una [solicitud de firmante](../working-with-managed-desktop/work-with-app-control.md#add-or-remove-a-trusted-signer).
3. Una vez que haya completado las pruebas (independientemente de los resultados), notifique a Operaciones y notifique las solicitudes de firmante pendientes. Las operaciones implementarán de forma progresiva directivas en grupos de implementación siguiendo esta programación:

| Grupo de implementación | Tipo de directiva | Timing |
| ------ | ------ | ------ |
| Prueba     | Auditoría |  Día 0 |
| Primero     | Enforced | Día 1 |
| Rápida     | Enforced |  Paused, rollout on request |
| Amplias     | Enforced |  Paused, rollout on request |

Siempre puede abrir otra solicitud de soporte técnico para pausar o revertir parte de esta implementación en cualquier momento durante el lanzamiento.

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Pasos para empezar con Microsoft Managed Desktop

1. Acceder al [portal de administrador](access-admin-portal.md).
1. [Agregar y verificar los contactos de administración en el portal de administrador](add-admin-contacts.md).
1. [Ajustar la configuración después de la inscripción](conditional-access.md).
1. Implementar y asignar el [Portal de empresa de Intune](company-portal.md).
1. [Asignar las licencias](assign-licenses.md).
1. [Implementar las aplicaciones](deploy-apps.md).
1. [Preparar dispositivos](prepare-devices.md).
1. Configurar la [experiencia de primera ejecución con el Autopilot y la página de estado de inscripción](esp-first-run.md).
1. [Habilitar las características de soporte técnico para el usuario](enable-support.md).
1. [Preparar a los usuarios para que usen los dispositivos](get-started-devices.md).
1. Introducción al control de aplicaciones (en este artículo).
