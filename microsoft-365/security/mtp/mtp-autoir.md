---
title: Investigación y respuesta automatizadas en Microsoft 365 Defender
description: Obtenga información general sobre las capacidades automatizadas de investigación y respuesta, también denominada recuperación automática, en Microsoft 365 Defender
keywords: automatizado, investigación, alerta, desencadenador, acción, corrección, recuperación automática
search.appverid: met150
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 905455e4cd70485e099f8005b5f8876b1a5d9caf
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930335"
---
# <a name="automated-investigation-and-response-in-microsoft-365-defender"></a>Investigación y respuesta automatizadas en Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender

> ¿Desea experimentar Microsoft 365 Defender? Puede [evaluarlo en un entorno de laboratorio o](https://aka.ms/mtp-trial-lab) ejecutar el proyecto piloto en [producción.](https://aka.ms/m365d-pilotplaybook)
>

## <a name="how-automated-investigation-and-self-healing-works"></a>Cómo funciona la investigación automatizada y la recuperación automática

A medida que se desencadenan las alertas de seguridad, es el equipo de operaciones de seguridad quien debe buscar esas alertas y tomar medidas para proteger su organización. El establecimiento de prioridades y la investigación de las alertas pueden llevar mucho tiempo, sobre todo cuando siguen apareciendo nuevas alertas mientras se está realizando una investigación. Los equipos de operaciones de seguridad pueden sentirse abrumados por el gran volumen de amenazas que deben supervisar y ante las que deben protegerse. Las capacidades automatizadas de investigación y respuesta, con recuperación automática, en Microsoft 365 Defender pueden ayudar.

Vea el siguiente vídeo para ver cómo funciona la recuperación automática:

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4BzwB]

En Microsoft 365 Defender, la investigación automatizada y la respuesta con capacidades de recuperación automática funcionan en sus dispositivos, correo electrónico & contenido e identidades.
 
> [!TIP]
> En este artículo se describe cómo funciona la investigación automatizada y la respuesta. Para configurar estas capacidades, vea Configurar las capacidades automatizadas de investigación y respuesta [en Microsoft 365 Defender.](mtp-configure-auto-investigation-response.md)

## <a name="your-own-virtual-analyst"></a>Su propio analista virtual

Imagínese tener un analista virtual en su equipo de operaciones de seguridad de nivel 1/nivel 2. El analista virtual imita los pasos más idóneos que llevarían a cabo las operaciones de seguridad para investigar y solucionar las amenazas. El asistente virtual podría funcionar de forma permanente y con capacidad ilimitada realizando una carga considerable de investigación y corrección de amenazas. Ese asistente virtual podría reducir el tiempo de respuesta considerablemente, lo que permitiría al equipo de operaciones de seguridad trabajar en otros proyectos estratégicos importantes. Si este escenario parece ciencia-ciencia, no es así. Este analista virtual forma parte de su conjunto de aplicaciones de Microsoft 365 Defender y su nombre es *investigación y respuesta automatizadas.*

La investigación y la respuesta automatizadas permiten al equipo de operaciones de seguridad aumentar considerablemente la capacidad de su organización para hacer frente a alertas e incidentes de seguridad. Con la investigación y respuesta automatizadas, puede reducir el costo de trabajar con actividades de investigación y corrección y sacar el máximo partido a su conjunto de protección contra amenazas. la investigación automatizada y la respuesta ayudan al equipo de operaciones de seguridad a:

1. Determinar si una amenaza requiere una acción;
2. Llevar a cabo (o recomendar) todas las acciones de corrección necesarias;
3. Determinar qué investigaciones adicionales deben realizarse; y
4. Repetir el proceso según sea necesario para otras alertas.

## <a name="the-automated-investigation-process"></a>El proceso de investigación automatizada

**Alerta** > **incidente** > **investigación automatizada** > **veredicto** > **acción de corrección**

Una alerta desencadenada crea un incidente, que puede iniciar una investigación automatizada. Esa investigación puede dar como resultado una o varias acciones correctivas. En Microsoft 365 Defender, cada investigación automatizada correlaciona las señales en Microsoft Defender para Identity, Microsoft Defender para Endpoint y Defender para Office 365, como se resume en la siguiente tabla: 

|Entidades |Servicios de protección contra amenazas  |
|---------|---------|
|Dispositivos (también denominados puntos de conexión)     |[Microsoft Defender para punto de conexión](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)<br/>[Microsoft Defender for Identity](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) |      
|Contenido de correo electrónico (archivos y mensajes de los buzones)     |[Microsoft Defender para Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)         |

Cada investigación genera veredictos *(malintencionados,* sospechosos o *sin* amenazas encontradas) para cada evidencia investigada. Según el tipo de amenaza y el veredicto resultante, las acciones de corrección se producen automáticamente o tras la aprobación por parte del equipo de operaciones de seguridad de la organización. Las acciones pendientes y completadas se muestran en el [Centro de actividades](mtp-action-center.md).

Durante la ejecución de una investigación, todas las demás alertas relacionadas que puedan surgir se agregarán a la investigación hasta que se finalice. Si se detecta una entidad involucrada en otro lugar, la investigación automatizada ampliará el ámbito para incluir esa entidad y se ejecutará un cuaderno de estrategias de seguridad. 

> [!NOTE]
> No todas las alertas desencadenan una investigación automatizada y no todas las investigaciones tienen como resultado acciones de corrección automatizadas; todo depende de cómo se configure la investigación y respuesta automatizadas para su organización. Consulte [Configurar las capacidades automatizadas de investigación y respuesta en Microsoft 365 Defender.](mtp-configure-auto-investigation-response.md)


## <a name="next-steps"></a>Siguientes pasos

- [Ver los requisitos previos para la investigación automatizada y la respuesta en Microsoft 365 Defender](mtp-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)
- [Configurar la investigación automatizada y la respuesta para su organización](mtp-configure-auto-investigation-response.md)
- [Más información sobre el Centro de actividades](mtp-action-center.md)
