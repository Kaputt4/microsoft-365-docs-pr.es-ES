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
ms.openlocfilehash: c45b7d1b01ee776e9519d67ee52d36b8f48bf0ef
ms.sourcegitcommit: 89178b8f20d59ca88cfca303a13062b91fbeae9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "46552359"
---
# <a name="automated-investigation-and-response-capabilities-in-microsoft-threat-protection"></a>Capacidades de investigación y respuesta automatizadas en la protección contra amenazas de Microsoft

**Se aplica a:**
- Protección contra amenazas de Microsoft

A medida que se activen las alertas de seguridad, el equipo de operaciones de seguridad será el encargado de consultar esas alertas y tomar las medidas necesarias para proteger su organización. El establecimiento de prioridades y la investigación de las alertas pueden llevar mucho tiempo, sobre todo cuando siguen apareciendo nuevas alertas mientras se está realizando una investigación. Los equipos de operaciones de seguridad pueden sentirse abrumados por el gran volumen de amenazas que deben supervisar y ante las que deben protegerse. Las capacidades de investigación y respuesta automatizadas (también conocidas como capacidades *automatizadas de Autorrecuperación* ) en Microsoft Threat Protection pueden ser de ayuda. 

Vea el siguiente vídeo para ver cómo funcionan las capacidades de reparación automática automatizadas:

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4BzwB]

La investigación y la respuesta automatizadas son como tener un analista virtual en el centro de operaciones de seguridad.

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

> [!TIP]
> Si cree que algo ha perdido o detectado erróneamente las características de respuesta e investigación automatizada en la protección contra amenazas de Microsoft, háganoslo saber. Consulte [Cómo informar de falsos positivos/negativos en capacidades automatizadas de investigación y respuesta en la protección contra amenazas de Microsoft](mtp-autoir-report-false-positives-negatives.md).

Durante la ejecución de una investigación, todas las demás alertas relacionadas que puedan surgir se agregarán a la investigación hasta que se finalice. Si se detecta una entidad involucrada en otro lugar, la investigación automatizada ampliará el ámbito para incluir esa entidad y se ejecutará un cuaderno de estrategias de seguridad. 

> [!NOTE]
> No todas las alertas activan una investigación automatizada, y no todas las investigaciones dan como resultado acciones de corrección automatizadas; todo esto depende de cómo esté configurada la respuesta y la investigación automatizadas para su organización. 

## <a name="requirements-for-automated-investigation-and-response-in-microsoft-threat-protection"></a>Requisitos para la investigación y la respuesta automatizadas en protección contra amenazas de Microsoft

|Requisito |Detalles |
|--|--|
|Requisitos de suscripción |Uno de los siguientes: <br/>-Microsoft 365 E5 <br/>-Microsoft 365 A5 <br/>-Seguridad de Microsoft 365 E5<br/>-Seguridad de Microsoft 365 A5<br/>-Office 365 E5 más Enterprise Mobility + Security E5 más Windows E5<br/><br/>Consulte [requisitos de licencia de Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites?#licensing-requirements).|
|Requisitos de red |- [Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) habilitada<br/>- [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) (MCAS) configurada<br/>- [MCAS integrada con Azure ATP](https://docs.microsoft.com/cloud-app-security/aatp-integration) |
|Requisitos de Windows del equipo |-Windows 10, versión 1709 o posterior instalada (consulte la información de la [versión Windows 10](https://docs.microsoft.com/windows/release-information/)) con los siguientes servicios de protección contra amenazas configurados:<br/>- [ATP de Microsoft defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints) <br/>- [Antivirus de Windows Defender](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features) |
|Protección para el contenido de correo electrónico y los archivos de Office |[Office 365 protección contra amenazas avanzada](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) configurada |
|Permisos |-Para configurar la investigación y la respuesta automatizadas, debe tener asignado el rol de administrador global o administrador de seguridad en Azure Active Directory ( [https://portal.azure.com](https://portal.azure.com) ) o en el centro de administración de 365 de Microsoft ( [https://admin.microsoft.com](https://admin.microsoft.com) ).<br/><br/>-Para usar las capacidades de investigación y respuesta automatizadas, consulte [permisos necesarios para las tareas del centro de actividades](mtp-action-center.md#required-permissions-for-action-center-tasks). |

## <a name="next-steps"></a>Siguientes pasos

- [Aprobar o rechazar acciones relacionadas con la investigación y la respuesta automatizadas](mtp-autoir-actions.md)
- [Más información sobre el Centro de actividades](mtp-action-center.md)
