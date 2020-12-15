---
title: Investigación y respuesta automatizadas en Microsoft 365 defender
description: Obtenga información general sobre la investigación automatizada y las capacidades de respuesta, también llamadas autorreparación, en Microsoft 365 defender.
keywords: automatizada, investigación, alerta, desencadenador, acción, corrección, resolución automática de mensajes
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.date: 12/09/2020
ms.reviewer: evaldm, isco
ms.openlocfilehash: 7c28b7f3ac797f7402cfdb1f604fcef1e142a31b
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/15/2020
ms.locfileid: "49683312"
---
# <a name="automated-investigation-and-response-in-microsoft-365-defender"></a>Investigación y respuesta automatizadas en Microsoft 365 defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

> ¿Quiere experimentar Microsoft 365 defender? Puede [evaluarlo en un entorno de laboratorio](https://aka.ms/mtp-trial-lab) o [ejecutar el proyecto piloto en producción](https://aka.ms/m365d-pilotplaybook).
>

## <a name="how-automated-investigation-and-self-healing-works"></a>Cómo funciona la investigación automática y la Autorrecuperación

A medida que se activen las alertas de seguridad, el equipo de operaciones de seguridad será el encargado de consultar esas alertas y tomar las medidas necesarias para proteger su organización. El establecimiento de prioridades y la investigación de las alertas pueden llevar mucho tiempo, sobre todo cuando siguen apareciendo nuevas alertas mientras se está realizando una investigación. Los equipos de operaciones de seguridad pueden sentirse abrumados por el gran volumen de amenazas que deben supervisar y ante las que deben protegerse. Las capacidades de investigación y respuesta automatizadas, con autorreparación, en Microsoft 365 defender pueden ser de ayuda.

Vea el siguiente vídeo para ver cómo funciona la característica de reparación automática:

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4BzwB]

En Microsoft 365 defender, la investigación y la respuesta automatizadas con capacidades de recuperación automática funcionan en los dispositivos, el correo electrónico & el contenido y las identidades.
 
> [!TIP]
> En este artículo se describe cómo funciona la investigación y la respuesta automatizadas. Para configurar estas funciones, consulte [Configure Automated Investigation and Response Capabilities in Microsoft 365 defender](mtp-configure-auto-investigation-response.md).

## <a name="your-own-virtual-analyst"></a>Su propio Analista virtual

Imagínese tener un analista virtual en su equipo de operaciones de seguridad de nivel 1/nivel 2. El analista virtual imita los pasos más idóneos que llevarían a cabo las operaciones de seguridad para investigar y solucionar las amenazas. El asistente virtual podría funcionar de forma permanente y con capacidad ilimitada realizando una carga considerable de investigación y corrección de amenazas. Ese asistente virtual podría reducir el tiempo de respuesta considerablemente, lo que permitiría al equipo de operaciones de seguridad trabajar en otros proyectos estratégicos importantes. Si este escenario suena como ciencia ficción, no lo es. Este analista virtual forma parte de su conjunto de aplicaciones de Microsoft 365 defender y su nombre es *investigación y respuesta automatizadas*.

La investigación y la respuesta automatizadas permiten al equipo de operaciones de seguridad aumentar drásticamente la capacidad de la organización para tratar las alertas de seguridad y los incidentes. Con la investigación y la respuesta automatizadas, puede reducir el coste de la gestión de actividades de investigación y corrección y sacar el máximo partido a su suite de protección contra amenazas. la investigación y la respuesta automatizadas ayudan al equipo de operaciones de seguridad por:

1. Determinar si una amenaza requiere una acción;
2. Llevar a cabo (o recomendar) todas las acciones de corrección necesarias;
3. Determinar qué investigaciones adicionales deben realizarse; y
4. Repetir el proceso según sea necesario para otras alertas.

## <a name="the-automated-investigation-process"></a>El proceso de investigación automatizada

**Alerta** > **incidente** > **investigación automatizada** > **veredicto** > **acción de corrección**

Una alerta desencadenada crea un incidente, que puede iniciar una investigación automatizada. Esa investigación puede dar como resultado una o varias acciones correctivas. En Microsoft 365 defender, cada investigación automatizada correlaciona las señales en Microsoft defender para identidad, Microsoft defender para Endpoint y defender para Office 365, tal como se resume en la tabla siguiente: 

|Entidades |Servicios de protección contra amenazas  |
|---------|---------|
|Dispositivos (también denominados puntos de conexión)     |[Microsoft Defender para punto de conexión](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)<br/>[Microsoft Defender for Identity](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) |      
|Contenido de correo electrónico (archivos y mensajes de los buzones)     |[Microsoft Defender para Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)         |

Cada investigación genera veredictos (*malintencionadas*, *sospechosas* o *no se han encontrado amenazas*) para cada fragmento de pruebas investigado. Según el tipo de amenaza y el veredicto resultante, las acciones de corrección se producen automáticamente o al aprobarlas por parte del equipo de operaciones de seguridad de la organización. Las acciones pendientes y completadas se muestran en el [Centro de actividades](mtp-action-center.md).

Durante la ejecución de una investigación, todas las demás alertas relacionadas que puedan surgir se agregarán a la investigación hasta que se finalice. Si se detecta una entidad involucrada en otro lugar, la investigación automatizada ampliará el ámbito para incluir esa entidad y se ejecutará un cuaderno de estrategias de seguridad. 

> [!NOTE]
> No todas las alertas activan una investigación automatizada, y no todas las investigaciones dan como resultado acciones de corrección automatizadas; todo esto depende de cómo esté configurada la respuesta y la investigación automatizadas para su organización. Consulte [Configure Automated Investigation and Response Capabilities in Microsoft 365 defender](mtp-configure-auto-investigation-response.md).


## <a name="next-steps"></a>Pasos siguientes

- [Vea los requisitos previos para la investigación y la respuesta automatizadas en Microsoft 365 defender](mtp-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)
- [Configurar la investigación y la respuesta automatizadas para su organización](mtp-configure-auto-investigation-response.md)
- [Más información sobre el Centro de actividades](mtp-action-center.md)
