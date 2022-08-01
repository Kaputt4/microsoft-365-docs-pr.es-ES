---
title: Microsoft Defender for Identity en Microsoft 365 Defender
description: Obtenga información sobre los cambios de la Microsoft Defender for Identity a Microsoft 365 Defender
keywords: Introducción a Microsoft 365 Defender, Microsoft Defender for Identity, NDI
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: dacurwin
author: dcurwin
manager: dansimp
ms.date: 07/06/2022
audience: ITPro
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.collection:
- M365-security-compliance
ms.custom: admindeeplinkDEFENDER
ms.openlocfilehash: 76044b7451014cc578800b6e1726556688d9db14
ms.sourcegitcommit: 7e551fa4e9b8b25ed62b5f406143b6b1dae08cbf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2022
ms.locfileid: "67107291"
---
# <a name="microsoft-defender-for-identity-in-microsoft-365-defender"></a>Microsoft Defender for Identity en Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft 365 Defender](microsoft-365-defender.md)
- [Microsoft Defender for Identity](/defender-for-identity/)

Microsoft Defender for Identity ahora forma parte de Microsoft 365 Defender. El portal de Microsoft 365 Defender permite a los administradores de seguridad realizar sus tareas de seguridad en una ubicación. Esto simplificará los flujos de trabajo y agregará la funcionalidad de los demás servicios de Microsoft 365 Defender. Microsoft 365 Defender será el hogar para supervisar y administrar la seguridad en las identidades, los datos, los dispositivos, las aplicaciones y la infraestructura de Microsoft.

Microsoft Defender for Identity aporta información centrada en la identidad en los incidentes y alertas que Microsoft 365 Defender presenta. Esta información es clave para proporcionar contexto y correlacionar alertas de los demás productos dentro de Microsoft 365 Defender.

## <a name="quick-reference"></a>Referencia rápida

En la tabla siguiente se enumeran los cambios en la navegación entre Microsoft Defender for Identity y Microsoft 365 Defender.

| **Defender para** Identidad  | **Microsoft 365 Defender**                                   |
| -------------------------- | ------------------------------------------------------------ |
| Escala de tiempo                   | cola de alertas e incidentes de Microsoft 365 Defender                |
| Informes                    | Permanecerá en el [portal clásico de Defender for Identity](/defender-for-identity/classic-workspace-portal). <br> Los informes personalizados se pueden crear en el portal de Microsoft 365 Defender mediante [la búsqueda avanzada](#advanced-hunting-new).               |
| Página de usuario                  | Microsoft 365 Defender página Usuario                             |
| Página dispositivo                | Microsoft 365 Defender página Dispositivo                           |
| Página de grupo                 | panel lateral de grupos de Microsoft 365 Defender                      |
| Página alerta                 | Microsoft 365 Defender página Alerta                            |
| Búsqueda                     | búsqueda de Microsoft 365 Defender                                |
| Centro de salud              | Configuración -> Identidades -sensores de >                            |
| Actividades de entidad          | Búsqueda avanzada de amenazas                                             |
| Configuración                   | Configuración -> identidades                                       |
| Usuarios y cuentas         | Recursos -> identidades                                         |
| Posición de seguridad de identidad  | [evaluaciones de la posición de seguridad de Microsoft Defender for Identity](/defender-for-identity/security-assessment) |
| Incorporación de un nuevo área de trabajo | Configuración -> identidades (automáticamente)                       |

## <a name="whats-changed"></a>Modificaciones

### <a name="defender-for-identity-settings"></a>Configuración de Defender for Identity

Para acceder a los valores de configuración de Microsoft Defender for Identity, en [Microsoft 365 Defender](https://security.microsoft.com), vaya a **Configuración** y, a continuación, **Identidades**.

### <a name="defender-for-identity-security-posture"></a>Posición de seguridad de Defender for Identity

Todas las evaluaciones de administración de la posición de seguridad de identidad a las que anteriormente se podía acceder en Defender for Cloud Apps ahora están disponibles en Puntuación segura de Microsoft, que se puede encontrar en <https://security.microsoft.com/securescore> el [portal de Microsoft 365 Defender](https://security.microsoft.com). Para obtener más información, consulte [las evaluaciones de la posición de seguridad de Microsoft Defender for Identity](/defender-for-identity/security-assessment).

### <a name="global-search"></a>Búsqueda global

La búsqueda global en Microsoft 365 Defender (mediante la barra de búsqueda de la parte superior de la página) permite a los equipos de seguridad buscar cualquier entidad supervisada por Microsoft 365 Defender, ya sea identidad, punto de conexión, datos Office 365, etc. Los resultados se pueden interactuar con directamente desde la lista desplegable de búsqueda, o los equipos de seguridad pueden elegir seleccionar **Todos los usuarios** o **Todos los dispositivos**  para ver todas las entidades asociadas a ese término de búsqueda.

### <a name="onboarding-and-administration"></a>Incorporación y administración

El proceso de incorporación ahora es automático para los nuevos clientes, sin necesidad de configurar manualmente un área de trabajo. Además, todas las características de administrador están disponibles en el menú **Identidades** de la configuración de Microsoft 365 Defender.

### <a name="alerting-and-incident-correlation"></a>Alertas y correlación de incidentes

Las alertas de Defender for Identity ahora se incluyen en la cola de alertas de Microsoft 365 Defender, lo que las pone a disposición de la característica de correlación automática de incidentes. Esto garantiza que todas las alertas estén disponibles en un solo lugar y que el ámbito de una infracción se pueda determinar más rápido que antes. Para obtener más información, consulte [Alertas de seguridad de Defender for Identity en Microsoft 365 Defender](/defender-for-identity/manage-security-alerts).

### <a name="advanced-hunting-new"></a>Búsqueda avanzada (nueva)

Ahora puede buscar amenazas y actividades malintencionadas de forma proactiva mediante consultas de búsqueda avanzadas. Estas consultas eficaces se pueden usar para buscar y revisar indicadores de amenazas y entidades para las amenazas conocidas y potenciales.

Las reglas de detección personalizadas se pueden crear a partir de consultas de búsqueda avanzadas para ayudarle a observar de forma proactiva los eventos que podrían indicar la actividad de infracción y los dispositivos mal configurados. Para obtener más información, consulte [Búsqueda proactiva de amenazas con la búsqueda avanzada en Microsoft 365 Defender](advanced-hunting-overview.md).

### <a name="alert-exclusions-updated"></a>Exclusiones de alertas (actualizadas)

La interfaz de alerta es más fácil de usar, incluida la adición de una función de búsqueda útil. Además, ahora incluye exclusiones globales. Esto significa que cualquier entidad se puede excluir de todas las alertas generadas por Defender for Identity, lo que ayuda con cualquier escenario de prueba que pueda tener. Para obtener más información, vea [Configurar exclusiones de detección de Defender for Identity en Microsoft 365 Defender](/defender-for-identity/exclusions).

### <a name="entity-profiles"></a>Perfiles de entidad

Los datos de Defender for Identity ahora se incluyen en los perfiles de entidad usuario y dispositivo de Microsoft 365.

### <a name="remediation-actions-new"></a>Acciones de corrección (nuevas)

Las acciones de corrección de Defender for Identity, como deshabilitar cuentas o requerir restablecimientos de contraseña, ahora se pueden realizar desde la página Microsoft 365 Defender Usuario. Para obtener más información, vea [Acciones de corrección en Microsoft Defender for Identity](/defender-for-identity/remediation-actions).

### <a name="lateral-movement-paths"></a>Rutas de desplazamiento lateral

Además de la pestaña **Rutas de desplazamiento lateral** de la página del usuario, las rutas de desplazamiento lateral también se pueden detectar a través de la característica **búsqueda avanzada** y la evaluación de la seguridad de las rutas de desplazamiento lateral. Para obtener más información, vea [Microsoft Defender for Identity rutas de desplazamiento lateral (LMP).](/defender-for-identity/understand-lateral-movement-paths)

## <a name="related-videos"></a>Vídeos relacionados

- [Nuevo para Microsoft Defender for Identity](https://www.microsoft.com/videoplayer/embed/RE4HcEU)

## <a name="related-information"></a>Información relacionada

- [Microsoft 365 Defender](microsoft-365-defender.md)
