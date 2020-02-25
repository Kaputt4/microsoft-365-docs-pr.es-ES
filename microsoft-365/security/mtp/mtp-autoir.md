---
title: Capacidades de investigación y respuesta automatizadas en la protección contra amenazas de Microsoft
description: Obtenga información general sobre la investigación y respuesta automatizada en la Protección contra amenazas de Microsoft
keywords: automatizada, investigación, alerta, desencadenante, acción, corrección
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
ms.openlocfilehash: f54ec3c0b318acaf6c81d26f32cfde5e87585a13
ms.sourcegitcommit: 133bf7936e5ef1a4d06998429d0d01096bda929f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2020
ms.locfileid: "42261997"
---
# <a name="automated-investigation-and-response-air-capabilities-in-microsoft-threat-protection"></a>Capacidades de investigación y respuesta automatizadas (AIR) en Microsoft Threat Protection

**Se aplica a:**
- Protección contra amenazas de Microsoft

Cuando se activan las alertas de seguridad, el equipo de operaciones de seguridad tiene la responsabilidad de consultar esas alertas y tomar medidas para proteger la organización. El establecimiento de prioridades y la investigación de las alertas pueden llevar mucho tiempo, sobre todo cuando siguen apareciendo nuevas alertas mientras se está realizando una investigación. Los equipos de operaciones de seguridad pueden sentirse abrumados por el gran volumen de amenazas que deben supervisar y ante las que deben protegerse. Las capacidades de investigación y respuesta automatizadas (AIR) de Microsoft Threat Protection pueden ser de ayuda. AIR es como tener un analista virtual en el centro de operaciones de seguridad.

## <a name="your-virtual-analyst"></a>Su analista virtual

Imagínese tener un analista virtual en su equipo de operaciones de seguridad de nivel 1/nivel 2. El analista virtual imita los pasos más idóneos que llevarían a cabo las operaciones de seguridad para investigar y solucionar las amenazas. El asistente virtual podría funcionar de forma permanente y con capacidad ilimitada realizando una carga considerable de investigación y corrección de amenazas. Ese asistente virtual podría reducir el tiempo de respuesta considerablemente, lo que permitiría al equipo de operaciones de seguridad trabajar en otros proyectos estratégicos importantes. Puede que este escenario le suena a ciencia ficción, pero no es así. Un analista virtual de este tipo ya forma parte del conjunto de aplicaciones de Protección contra amenazas de Microsoft, se llama *Investigación y respuesta automatizada* (AIR).

AIR permite al equipo de operaciones de seguridad aumentar drásticamente la capacidad de la organización para abordar las alertas de seguridad y las incidencias. Con AIR, puede reducir el coste de la gestión de las actividades de investigación y corrección y sacar el máximo partido del conjunto de aplicaciones de protección contra amenazas. AIR ayuda a su equipo de operaciones de seguridad a:

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

En cada investigación se generan veredictos (*Malintencionado*, *Sospechoso* o *Limpio*) para cada elemento que se investiga. En función del tipo de amenaza y el veredicto resultante, las acciones de corrección se ejecutan automáticamente o una vez que el equipo de operaciones de seguridad de la organización las aprueban. Las acciones pendientes y completadas se muestran en el [Centro de actividades](mtp-action-center.md).

> [!TIP]
> Si cree que algo ha perdido o detectado erróneamente las características de respuesta e investigación automatizada en la protección contra amenazas de Microsoft, háganoslo saber. Consulte [Cómo informar de falsos positivos/negativos en capacidades de investigación y respuesta automatizadas (Air) en la protección contra amenazas de Microsoft](mtp-autoir-report-false-positives-negatives.md).

Durante la ejecución de una investigación, todas las demás alertas relacionadas que puedan surgir se agregarán a la investigación hasta que se finalice. Si se detecta una entidad involucrada en otro lugar, la investigación automatizada ampliará el ámbito para incluir esa entidad y se ejecutará un cuaderno de estrategias de seguridad. 

> [!NOTE]
> No todas las alertas activan una investigación automatizada y no todas las investigaciones generan acciones de corrección automatizadas, todo depende de cómo se configure AIR para la organización. 

## <a name="requirements-for-air-in-microsoft-threat-protection"></a>Requisitos de AIR en la Protección contra amenazas de Microsoft

| | |
|--|--|
|Requisitos de suscripción |- Microsoft 365 E5 o Microsoft 365 E3 junto con la protección de identidad y contra amenazas<br/>- Consulte [Planes de Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-overview#plans)|
|Requisitos de red |- [Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) habilitada<br/>- [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) (MCAS) configurada<br/>- [MCAS integrada con Azure ATP](https://docs.microsoft.com/cloud-app-security/aatp-integration) |
|Requisitos de Windows del equipo |- Windows 10, versión 1709 o posterior instalado (consulte [Información sobre la versión de Windows 10](https://docs.microsoft.com/windows/release-information/))<br/>- [ATP de Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints) configurada <br/>- [Antivirus de Windows Defender](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features) configurado |
|Protección para el contenido de correo electrónico y los archivos de Office |[Office 365 protección contra amenazas avanzada](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) configurada |
|Permisos |- Para *configurar* AIR, debe tener el rol de **administrador global** o **administrador de seguridad** asignado en Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) o en el Centro de administración de Microsoft 365 ([https://admin.microsoft.com](https://admin.microsoft.com)).<br/><br/>- Para *usar* las capacidades de AIR, consulte [Permisos necesarios para las tareas del Centro de actividades](mtp-action-center.md#required-permissions-for-action-center-tasks). |

## <a name="next-steps"></a>Siguientes pasos

- [Aprobar o rechazar acciones relacionadas con la investigación y la respuesta automatizadas](mtp-autoir-actions.md)
- [Más información sobre el Centro de actividades](mtp-action-center.md)
