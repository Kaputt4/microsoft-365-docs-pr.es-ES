---
title: Investigación y respuesta automatizadas en Microsoft 365 Defender
description: Obtenga información general sobre las capacidades automatizadas de investigación y respuesta, también denominadas recuperación automática, en Microsoft 365 Defender
keywords: automatizado, investigación, alerta, desencadenador, acción, corrección, recuperación automática
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: fcb7283faed6fe8c5af59cedeeb90577b557ab34
ms.sourcegitcommit: 5a1cb7d95070eef47d401a4693cc137a90550a5e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "52259540"
---
# <a name="automated-investigation-and-response-in-microsoft-365-defender"></a>Investigación y respuesta automatizadas en Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**
- Microsoft 365 Defender

Si su organización usa [Microsoft 365 Defender,](microsoft-365-defender.md)el equipo de operaciones de seguridad recibe una alerta en el centro de seguridad de Microsoft 365 siempre que se detecte una actividad o artefacto malintencionados o sospechosos. Dado el flujo aparentemente interminable de amenazas que pueden llegar, los equipos de seguridad a menudo se enfrentan al desafío de abordar el alto volumen de alertas. Afortunadamente, Microsoft 365 Defender incluye capacidades automatizadas de investigación y corrección (AIR) que pueden ayudar a su equipo de operaciones de seguridad a abordar las amenazas de forma más eficaz y eficaz.

En este artículo se proporciona información general sobre AIR e incluye vínculos a los siguientes pasos y recursos adicionales.

> [!TIP]
> ¿Quiere experimentar Microsoft 365 Defender? Puede [evaluarlo en un entorno de pruebas](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) o bien [ejecutar el proyecto piloto en producción](m365d-pilot.md?ocid=cx-evalpilot).

## <a name="how-automated-investigation-and-self-healing-works"></a>Cómo funciona la investigación automatizada y la recuperación automática

A medida que se desencadenan las alertas de seguridad, el equipo de operaciones de seguridad debe buscar esas alertas y tomar medidas para proteger su organización. El establecimiento de prioridades y la investigación de las alertas pueden llevar mucho tiempo, sobre todo cuando siguen apareciendo nuevas alertas mientras se está realizando una investigación. Los equipos de operaciones de seguridad pueden sentirse abrumados por el gran volumen de amenazas que deben supervisar y ante las que deben protegerse. Las capacidades automatizadas de investigación y respuesta, con recuperación automática, en Microsoft 365 Defender pueden ayudar.

Vea el siguiente vídeo para ver cómo funciona la recuperación automática: <p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4BzwB]

En Microsoft 365 Defender, la investigación automatizada y la respuesta con capacidades de recuperación automática funcionan en todos los dispositivos, el correo & contenido y las identidades.
 
> [!TIP]
> En este artículo se describe cómo funciona la investigación automatizada y la respuesta. Para configurar estas capacidades, vea [Configure automated investigation and response capabilities in Microsoft 365 Defender](m365d-configure-auto-investigation-response.md).

## <a name="your-own-virtual-analyst"></a>Su propio analista virtual

Imagine un analista virtual en su equipo de operaciones de seguridad de nivel 1 o nivel 2. El analista virtual imita los pasos más idóneos que llevarían a cabo las operaciones de seguridad para investigar y solucionar las amenazas. El analista virtual podría trabajar 24 x 7, con capacidad ilimitada, y asumir una carga significativa de investigaciones y corrección de amenazas. Este tipo de analista virtual podría reducir significativamente el tiempo de respuesta, liberando al equipo de operaciones de seguridad para otras amenazas importantes o proyectos estratégicos. Si este escenario suena a ciencia ficción, no lo es. Dicho analista virtual forma parte de su conjunto de Microsoft 365 Defender y su nombre es *investigación y respuesta automatizadas.*

Las capacidades automatizadas de investigación y respuesta permiten al equipo de operaciones de seguridad aumentar considerablemente la capacidad de su organización para hacer frente a las alertas e incidentes de seguridad. Con la investigación y la respuesta automatizadas, puede reducir el costo de las actividades de investigación y corrección y sacar el máximo partido a su conjunto de protección contra amenazas. Las capacidades automatizadas de investigación y respuesta ayudan al equipo de operaciones de seguridad:

1. Determinar si una amenaza requiere acción.
2. Realizar (o recomendar) las acciones de corrección necesarias.
3. Determinar si deben producirse otras investigaciones y qué otras.
4. Repetir el proceso según sea necesario para otras alertas.

## <a name="the-automated-investigation-process"></a>El proceso de investigación automatizada

Una alerta crea un incidente, que puede iniciar una investigación automatizada. La investigación automatizada da como resultado un veredicto para cada elemento de evidencia. Los veredictos pueden ser:
- *Malintencionada*
- *Sospechoso* 
- *No se encontraron amenazas* 

Se identifican acciones de corrección para entidades malintencionadas o sospechosas. Algunos ejemplos de acciones de corrección son:

- Enviar un archivo a la cuarentena
- Detención de un proceso
- Aislar un dispositivo
- Bloquear una dirección URL 
- Otras acciones

Para obtener más información, vea [Acciones de corrección en Microsoft 365 Defender](m365d-remediation-actions.md).

En función [de cómo se configuren](m365d-configure-auto-investigation-response.md) las capacidades automatizadas de investigación y respuesta para su organización, las acciones de corrección se toman automáticamente o solo tras la aprobación del equipo de operaciones de seguridad. Todas las acciones, ya sean pendientes o completadas, se enumeran en el [Centro de acciones](m365d-action-center.md).

Durante la ejecución de una investigación, todas las demás alertas relacionadas que puedan surgir se agregarán a la investigación hasta que se finalice. Si se ve una entidad afectada en otro lugar, la investigación automatizada expande su ámbito para incluir esa entidad y el proceso de investigación se repite. 

En Microsoft 365 Defender, cada investigación automatizada correlaciona las señales entre Microsoft Defender for Identity, Microsoft Defender para Endpoint y Microsoft Defender para Office 365, como se resume en la tabla siguiente: 

|Entidades |Servicios de protección contra amenazas  |
|:---------|:---------|
|Dispositivos (también denominados extremos o máquinas) |[Defender for Endpoint](../defender-endpoint/automated-investigations.md) |      
|Usuarios locales de Active Directory, comportamiento de entidad y actividades     |[Defender for Identity](/azure-advanced-threat-protection/what-is-atp) |      
|Contenido de correo electrónico (mensajes de correo electrónico que pueden contener archivos y direcciones URL)     |[Defender para Office 365](../office-365-security/defender-for-office-365.md) |

> [!NOTE]
> No todas las alertas desencadenan una investigación automatizada y no todas las investigaciones tienen como resultado acciones de corrección automatizadas. Depende de cómo se configure la investigación y la respuesta automatizadas para su organización. Vea [Configure automated investigation and response capabilities](m365d-configure-auto-investigation-response.md).

## <a name="viewing-a-list-of-investigations"></a>Visualización de una lista de investigaciones

Para ver las investigaciones, vaya a la **página Incidentes.** Seleccione un incidente y, a continuación, seleccione la **pestaña Investigaciones.** Para obtener más información, vea [Detalles y resultados de una investigación automatizada.](m365d-autoir-results.md)


## <a name="next-steps"></a>Pasos siguientes

- [Consulte los requisitos previos para la investigación y respuesta automatizadas](m365d-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)
- [Configurar la investigación automatizada y la respuesta para su organización](m365d-configure-auto-investigation-response.md)
- [Más información sobre el Centro de actividades](m365d-action-center.md)
