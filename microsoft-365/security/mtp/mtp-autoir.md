---
title: Investigación y respuesta automatizada en la Protección contra amenazas de Microsoft
description: Obtenga información general sobre la investigación automatizada y las capacidades de respuesta, también llamadas autorreparación, en protección contra amenazas de Microsoft
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
ms.topic: conceptual
ms.custom: autoir
ms.date: 09/16/2020
ms.reviewer: evaldm, isco
ms.openlocfilehash: f2a0a439996f13cea3823815aceb9dd1c235e2f2
ms.sourcegitcommit: 7c0873d2a804f17697844fb13f1a100fabce86c4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2020
ms.locfileid: "47962670"
---
# <a name="automated-investigation-and-response-in-microsoft-threat-protection"></a>Investigación y respuesta automatizada en la Protección contra amenazas de Microsoft

**Se aplica a:**
- Protección contra amenazas de Microsoft

A medida que se activen las alertas de seguridad, el equipo de operaciones de seguridad será el encargado de consultar esas alertas y tomar las medidas necesarias para proteger su organización. El establecimiento de prioridades y la investigación de las alertas pueden llevar mucho tiempo, sobre todo cuando siguen apareciendo nuevas alertas mientras se está realizando una investigación. Los equipos de operaciones de seguridad pueden sentirse abrumados por el gran volumen de amenazas que deben supervisar y ante las que deben protegerse. Las capacidades automatizadas de investigación y respuesta, con autorreparación, en Microsoft Threat Protection pueden ser de ayuda.

Vea el siguiente vídeo para ver cómo funciona la característica de reparación automática:

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4BzwB]

En Microsoft Threat Protection, la investigación y la respuesta automatizadas con capacidades de recuperación automática funcionan en los dispositivos, el correo electrónico & contenido y las identidades. Microsoft Threat Protection combina capacidades de: 
- [Investigación y corrección automáticas en protección contra amenazas avanzada de Microsoft defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)
- [Investigación y respuesta automatizadas de la protección contra amenazas avanzada de Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)
- [Detección de amenazas avanzadas de Azure](https://docs.microsoft.com/azure/security/fundamentals/threat-detection)
- [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
 
En este artículo se describe cómo funciona la investigación y la respuesta automatizadas. Para configurar estas funciones, consulte [Configure Automated Investigation and Response Capabilities in Microsoft Threat Protection](mtp-configure-auto-investigation-response.md).

## <a name="your-virtual-analyst"></a>Su analista virtual

Imagínese tener un analista virtual en su equipo de operaciones de seguridad de nivel 1/nivel 2. El analista virtual imita los pasos más idóneos que llevarían a cabo las operaciones de seguridad para investigar y solucionar las amenazas. El asistente virtual podría funcionar de forma permanente y con capacidad ilimitada realizando una carga considerable de investigación y corrección de amenazas. Ese asistente virtual podría reducir el tiempo de respuesta considerablemente, lo que permitiría al equipo de operaciones de seguridad trabajar en otros proyectos estratégicos importantes. Si este escenario suena como ciencia ficción, no lo es. Este analista virtual forma parte de su conjunto de aplicaciones de protección contra amenazas de Microsoft y su nombre es *investigación y respuesta automatizadas*.

La investigación y la respuesta automatizadas permiten al equipo de operaciones de seguridad aumentar drásticamente la capacidad de la organización para tratar las alertas de seguridad y los incidentes. Con la investigación y la respuesta automatizadas, puede reducir el coste de la gestión de actividades de investigación y corrección y sacar el máximo partido a su suite de protección contra amenazas. la investigación y la respuesta automatizadas ayudan al equipo de operaciones de seguridad por:

1. Determinar si una amenaza requiere una acción;
2. Llevar a cabo (o recomendar) todas las acciones de corrección necesarias;
3. Determinar qué investigaciones adicionales deben realizarse; y
4. Repetir el proceso según sea necesario para otras alertas.

## <a name="the-automated-investigation-process"></a>El proceso de investigación automatizada

**Alerta** > **incidente** > **investigación automatizada** > **veredicto** > **acción de corrección**

Una alerta desencadenada crea un incidente, que puede iniciar una investigación automatizada. Esa investigación puede dar como resultado una o varias acciones correctivas. En la Protección contra amenazas de Microsoft, cada investigación automatizada correlaciona las señales en Azure Advanced Threat Protection (Azure ATP), la Protección contra amenazas avanzada de Microsoft Defender (ATP de Microsoft Defender) y la Protección contra amenazas avanzada de Office 365 (ATP de Office 365), tal y como se resume en la tabla siguiente: 

|Entidades |Servicios de protección contra amenazas  |
|---------|---------|
|Dispositivos (también denominados puntos de conexión)     |[ATP de Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)<br/>[Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) |      
|Contenido de correo electrónico (archivos y mensajes de los buzones)     |[ATP de Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)         |

Cada investigación genera veredictos (*malintencionadas*, *sospechosas*o *no se han encontrado amenazas*) para cada fragmento de pruebas investigado. Según el tipo de amenaza y el veredicto resultante, las acciones de corrección se producen automáticamente o al aprobarlas por parte del equipo de operaciones de seguridad de la organización. Las acciones pendientes y completadas se muestran en el [Centro de actividades](mtp-action-center.md).

Durante la ejecución de una investigación, todas las demás alertas relacionadas que puedan surgir se agregarán a la investigación hasta que se finalice. Si se detecta una entidad involucrada en otro lugar, la investigación automatizada ampliará el ámbito para incluir esa entidad y se ejecutará un cuaderno de estrategias de seguridad. 

> [!NOTE]
> No todas las alertas activan una investigación automatizada, y no todas las investigaciones dan como resultado acciones de corrección automatizadas; todo esto depende de cómo esté configurada la respuesta y la investigación automatizadas para su organización. Consulte [Configure Automated Investigation and Response Capabilities in Microsoft Threat Protection](mtp-configure-auto-investigation-response.md).


## <a name="next-steps"></a>Pasos siguientes

- [Consulte los requisitos previos para la investigación y la respuesta automatizadas en la protección contra amenazas de Microsoft](mtp-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-threat-protection)
- [Configurar la investigación y la respuesta automatizadas para su organización](mtp-configure-auto-investigation-response.md)
- [Más información sobre el Centro de actividades](mtp-action-center.md)
