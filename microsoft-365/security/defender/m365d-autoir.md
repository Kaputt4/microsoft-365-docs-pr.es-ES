---
title: Investigación y respuesta automatizadas en Microsoft 365 Defender
description: Obtenga información general sobre las funcionalidades automatizadas de investigación y respuesta, también denominadas recuperación automática, en Microsoft 365 Defender
keywords: automated, investigation, alert, trigger, action, remediation, self-healing
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: 332802150235ec6f47c4bdea34b34edb94ea1b90
ms.sourcegitcommit: dd7e5b67ff4ae4e7f74490e437c1795933c74cc7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2022
ms.locfileid: "64731337"
---
# <a name="automated-investigation-and-response-in-microsoft-365-defender"></a>Investigación y respuesta automatizadas en Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**
- Microsoft 365 Defender

Si su organización usa [Microsoft 365 Defender](microsoft-365-defender.md), el equipo de operaciones de seguridad recibe una alerta en el portal de Microsoft 365 Defender cada vez que se detecta una actividad o artefacto malintencionado o sospechoso. Dado el flujo aparentemente interminable de amenazas que pueden aparecer, los equipos de seguridad a menudo se enfrentan al desafío de abordar el alto volumen de alertas. Afortunadamente, Microsoft 365 Defender incluye funcionalidades de investigación y respuesta automatizadas (AIR) que pueden ayudar al equipo de operaciones de seguridad a abordar las amenazas de forma más eficaz y eficaz.

En este artículo se proporciona información general sobre AIR e incluye vínculos a los pasos siguientes y recursos adicionales.

## <a name="how-automated-investigation-and-self-healing-works"></a>Funcionamiento de la investigación automatizada y la recuperación automática

A medida que se desencadenan alertas de seguridad, depende del equipo de operaciones de seguridad examinar esas alertas y tomar medidas para proteger su organización. El establecimiento de prioridades y la investigación de las alertas pueden llevar mucho tiempo, sobre todo cuando siguen apareciendo nuevas alertas mientras se está realizando una investigación. Los equipos de operaciones de seguridad pueden sentirse abrumados por el gran volumen de amenazas que deben supervisar y ante las que deben protegerse. Las funcionalidades automatizadas de investigación y respuesta, con recuperación automática, en Microsoft 365 Defender pueden ayudar.

Vea el siguiente vídeo para ver cómo funciona la recuperación automática: <p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4BzwB]

En Microsoft 365 Defender, la investigación y la respuesta automatizadas con funcionalidades de recuperación automática funcionan en todos los dispositivos, el correo electrónico & contenido y las identidades.
 
> [!TIP]
> En este artículo se describe cómo funciona la investigación y la respuesta automatizadas. Para configurar estas funcionalidades, consulte [Configuración de funcionalidades automatizadas de investigación y respuesta en Microsoft 365 Defender](m365d-configure-auto-investigation-response.md).

## <a name="your-own-virtual-analyst"></a>Su propio analista virtual

Imagine tener un analista virtual en el equipo de operaciones de seguridad de nivel 1 o nivel 2. El analista virtual imita los pasos más idóneos que llevarían a cabo las operaciones de seguridad para investigar y solucionar las amenazas. El analista virtual podría trabajar 24x7, con capacidad ilimitada, y asumir una carga significativa de investigaciones y corrección de amenazas. Este tipo de analista virtual podría reducir significativamente el tiempo de respuesta, liberando al equipo de operaciones de seguridad para otras amenazas importantes o proyectos estratégicos. Si este escenario suena a ciencia ficción, no lo es. Este analista virtual forma parte del conjunto de Microsoft 365 Defender y su nombre es *investigación y respuesta automatizadas*.

Las funcionalidades automatizadas de investigación y respuesta permiten al equipo de operaciones de seguridad aumentar considerablemente la capacidad de su organización para hacer frente a alertas e incidentes de seguridad. Con la investigación y la respuesta automatizadas, puede reducir el costo de tratar las actividades de investigación y respuesta y sacar el máximo partido a su conjunto de protección contra amenazas. Las funcionalidades automatizadas de investigación y respuesta ayudan al equipo de operaciones de seguridad:

1. Determinar si una amenaza requiere una acción.
2. Realizar (o recomendar) todas las acciones de corrección necesarias.
3. Determinar si deben hacerse otras investigaciones y cuáles.
4. Repetir el proceso según sea necesario para otras alertas.

## <a name="the-automated-investigation-process"></a>El proceso de investigación automatizada

Una alerta crea un incidente, que puede iniciar una investigación automatizada. La investigación automatizada da como resultado un veredicto para cada pieza de evidencia. Los veredictos pueden ser:
- *Malintencionada*
- *Sospechoso* 
- *No se encontraron amenazas* 

Se identifican acciones de corrección para entidades malintencionadas o sospechosas. Entre los ejemplos de acciones de corrección se incluyen:

- Envío de un archivo a la cuarentena
- Detener un proceso
- Aislar un dispositivo
- Bloqueo de una dirección URL 
- Otras acciones

Para obtener más información, vea [Acciones de corrección en Microsoft 365 Defender](m365d-remediation-actions.md).

En función de [cómo se configuren las funcionalidades automatizadas de investigación y respuesta](m365d-configure-auto-investigation-response.md) para su organización, las acciones de corrección se realizan automáticamente o solo tras la aprobación del equipo de operaciones de seguridad. Todas las acciones, ya sean pendientes o completadas, aparecen en el [Centro de acciones](m365d-action-center.md).

Durante la ejecución de una investigación, todas las demás alertas relacionadas que puedan surgir se agregarán a la investigación hasta que se finalice. Si ve una entidad afectada en otro lugar, la investigación automatizada expande su ámbito para incluir esa entidad, y el proceso de investigación se repite. 

En Microsoft 365 Defender, cada investigación automatizada correlaciona las señales entre Microsoft Defender for Identity, Microsoft Defender para punto de conexión y Microsoft Defender para Office 365, como se resume en la tabla siguiente: 

|Entidades |Servicios de protección contra amenazas  |
|:---------|:---------|
|Dispositivos (también conocidos como puntos de conexión o máquinas) |[Defender para punto de conexión](../defender-endpoint/automated-investigations.md) |      
|Usuarios locales de Active Directory, comportamiento de entidad y actividades     |[Defender for Identity](/azure-advanced-threat-protection/what-is-atp) |      
|Contenido de correo electrónico (mensajes de correo electrónico que pueden contener archivos y direcciones URL)     |[Defender para Office 365](../office-365-security/defender-for-office-365.md) |

> [!NOTE]
> No todas las alertas desencadenan una investigación automatizada y no todas las investigaciones tienen como resultado acciones de corrección automatizadas. Depende de cómo se configure la investigación y la respuesta automatizadas para su organización. Consulte [Configuración de funcionalidades automatizadas de investigación y respuesta](m365d-configure-auto-investigation-response.md).

## <a name="viewing-a-list-of-investigations"></a>Visualización de una lista de investigaciones

Para ver las investigaciones, vaya a la página **Incidentes** . Seleccione un incidente y, a continuación, seleccione la pestaña **Investigaciones** . Para más información, consulte [Detalles y resultados de una investigación automatizada](m365d-autoir-results.md).

## <a name="training-for-security-analysts"></a>Aprendizaje para analistas de seguridad

Use este módulo de aprendizaje de Microsoft Learn para comprender cómo Microsoft 365 Defender usa la recuperación automática automatizada para la investigación y respuesta de incidentes.

|Aprendizaje:|Recuperación automática automatizada con Microsoft 365 Defender|
|---|---|
|![Automatice la recuperación automática con Microsoft 365 Defender icono de entrenamiento.](../../media/m365d-autoir/m365-defender-auto-self-healing.svg)| Microsoft 365 Defender usa la inteligencia artificial para automatizar la corrección de incidentes, lo que ayuda al equipo de operaciones de seguridad a abordar las amenazas de forma más eficaz y eficaz. <p> 11 min - 5 unidades |

> [!div class="nextstepaction"]
> [Iniciar >](/learn/modules/defender-self-healing/)

## <a name="next-steps"></a>Pasos siguientes

- [Consulte los requisitos previos para la investigación y la respuesta automatizadas.](m365d-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)
- [Configuración de la investigación y la respuesta automatizadas para su organización](m365d-configure-auto-investigation-response.md)
- [Más información sobre el Centro de actividades](m365d-action-center.md)
