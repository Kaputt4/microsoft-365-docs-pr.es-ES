---
title: Cuadernos de estrategias de calificación de alertas
description: Revise las alertas en busca de ataques conocidos y realice las acciones recomendadas para corregir el ataque y proteger la red.
keywords: incidentes, alertas, investigar, analizar, respuesta, correlación, ataque, máquinas, dispositivos, usuarios, identidades, identidad, buzón de correo electrónico, 365, microsoft, m365
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
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
- m365-security
- tier2
ms.topic: how-to
ms.custom:
- autoir
- admindeeplinkDEFENDER
ms.reviewer: evaldm, isco
ms.openlocfilehash: bdb8acc0e3b56d59f6afb6fcbf8a3f6c4c538874
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68089155"
---
# <a name="alert-grading-playbooks"></a>Cuadernos de estrategias de calificación de alertas

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**
- Microsoft 365 Defender

Los cuadernos de estrategias de clasificación de alertas le permiten revisar y clasificar rápidamente las alertas de ataques conocidos y realizar las acciones recomendadas para corregir el ataque y proteger la red. La clasificación de alertas también ayudará a clasificar correctamente el incidente general.

Como investigador de seguridad o analista del Centro de operaciones de seguridad (SOC), debe tener acceso al portal de Microsoft 365 Defender para que pueda:

- Evalúe y revise las alertas generadas y los incidentes asociados. Consulte [Investigar alertas](investigate-alerts.md).
- Busque en los datos de señal de seguridad del inquilino y compruebe si hay posibles amenazas y actividades sospechosas. Consulte [búsqueda avanzada](advanced-hunting-overview.md).

>[!Note]
>Puede proporcionar comentarios a Microsoft sobre alertas de verdaderos positivos y falsos positivos, no solo al final de la investigación, sino también durante el proceso de investigación. Esto puede ayudar a Microsoft con el análisis y la clasificación futuros de eventos de seguridad.
>

## <a name="microsoft-defender-for-office-365"></a>Microsoft Defender para Office 365

[Microsoft Defender para Office 365](/microsoft-365/security/office-365-security/defender-for-office-365) protege a su organización frente a amenazas malintencionadas planteadas por mensajes de correo electrónico, vínculos (DIRECCIONES URL) y herramientas de colaboración. Microsoft Defender para Office 365 incluye:

- Directivas de protección contra amenazas

   Defina directivas de protección contra amenazas para establecer el nivel de protección adecuado para su organización.

- Informes

  Vea informes en tiempo real para supervisar el rendimiento de Defender para Office 365 en su organización.

- Capacidades de investigación y respuesta de amenazas

  Use herramientas de vanguardia para investigar, comprender, simular y evitar amenazas.

- Funcionalidades automatizadas de investigación y respuesta

  Ahorre tiempo y esfuerzo investigando y mitigando amenazas.

Defender para Office 365 alertas se pueden clasificar como: 

- Verdadero positivo (TP) para la actividad malintencionada confirmada. 
- Falso positivo (FP) para la actividad no malintencionada confirmada.

>[!Note]
>Microsoft 365 Defender portal [https://security.microsoft.com](https://security.microsoft.com) reúne la funcionalidad de los portales de seguridad de Microsoft existentes. El portal de Microsoft 365 Defender hace hincapié en el acceso rápido a la información, diseños más sencillos y reunir información relacionada para facilitar su uso.
>

## <a name="microsoft-defender-for-cloud-apps"></a>Microsoft Defender for Cloud Apps

[Microsoft Defender for Cloud Apps](/defender-cloud-apps) es un agente de seguridad de acceso a la nube (CASB) que admite varios modos de implementación, como la recopilación de registros, los conectores de API y el proxy inverso. Ofrece una visibilidad completa, control sobre los datos que se transmiten y análisis sofisticados para identificar y combatir las ciberamenazas en todos los servicios en la nube de Microsoft y de terceros.

Defender for Cloud Apps se integra de forma nativa con las principales soluciones de Microsoft y está diseñado pensando en los profesionales de seguridad. Ofrece una implementación simple, una administración centralizada y capacidades de automatización innovadoras.

El marco de Defender for Cloud Apps incluye la capacidad de proteger la red contra ciberamenazas y anomalías, detecta un comportamiento inusual en las aplicaciones en la nube para identificar ransomware, usuarios en peligro o aplicaciones no autorizadas. Permite el análisis del uso de alto riesgo y puede corregirse automáticamente para limitar el riesgo para su organización.

Las alertas de Defender for Cloud Apps se pueden clasificar como: 

- TP para la actividad malintencionada confirmada. 
- Verdadero positivo benigno (B-TP) para actividades sospechosas pero no malintencionadas, como una prueba de penetración u otra acción sospechosa autorizada. 
- FP para actividad no malintencionada confirmada.

## <a name="alert-grading-playbooks"></a>Cuadernos de estrategias de calificación de alertas

Consulte estos cuadernos de estrategias para conocer los pasos para calificar más rápidamente las alertas de las siguientes amenazas:

- [Actividad de reenvío de correo electrónico sospechoso](alert-grading-playbook-email-forwarding.md)
- [Reglas sospechosas de manipulación de la bandeja de entrada](alert-grading-playbook-inbox-manipulation-rules.md)
- [Reglas del reenvío sospechoso desde la bandeja de entrada](alert-grading-playbook-inbox-forwarding-rules.md)

Consulte [Investigar alertas](investigate-alerts.md) para obtener información sobre cómo examinar alertas con el portal de Microsoft 365 Defender.
