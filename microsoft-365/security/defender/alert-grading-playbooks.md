---
title: Libros de juegos de clasificación de alertas
description: Revisa las alertas de ataques conocidos y toma las acciones recomendadas para corregir el ataque y proteger la red.
keywords: incidentes, alertas, investigar, analizar, responder, correlación, ataque, máquinas, dispositivos, usuarios, identidades, identidad, buzón, correo electrónico, 365, microsoft, m365
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: how-to
ms.custom:
- autoir
- admindeeplinkDEFENDER
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: fe0beb88cf613a5a966fc0534dfa4def715e81d2
ms.sourcegitcommit: e3bff611439354e6339bb666a88682078f32ec13
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2022
ms.locfileid: "62355234"
---
# <a name="alert-grading-playbooks"></a>Libros de juegos de clasificación de alertas

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**
- Microsoft 365 Defender

Los libros de juegos de clasificación de alertas te permiten revisar metóricamente y clasificar rápidamente las alertas de ataques conocidos y realizar acciones recomendadas para corregir el ataque y proteger la red. La clasificación de alertas también ayudará a clasificar correctamente el incidente general.

Como investigador de seguridad o analista del Centro de operaciones de seguridad (SOC), debe tener acceso al portal de Microsoft 365 Defender para que pueda:

- Evaluar y revisar las alertas generadas y los incidentes asociados. Consulta [Investigar alertas](investigate-alerts.md).
- Busque en los datos de señal de seguridad de su inquilino y compruebe si hay amenazas potenciales y actividades sospechosas. Consulta [búsqueda avanzada](advanced-hunting-overview.md).

>[!Note]
>Puede proporcionar comentarios a Microsoft sobre alertas de verdaderos positivos y falsos positivos, no solo al final de la investigación, sino también durante el proceso de investigación. Esto puede ayudar a Microsoft con el análisis futuro y la clasificación de eventos de seguridad.
>

## <a name="microsoft-defender-for-office-365"></a>Microsoft Defender para Office 365

[Microsoft Defender para Office 365](/microsoft-365/security/office-365-security/defender-for-office-365) protege su organización contra amenazas malintencionadas que suponen mensajes de correo electrónico, vínculos (URL) y herramientas de colaboración. Microsoft Defender para Office 365 incluye:

- Directivas de protección contra amenazas

   Defina directivas de protección contra amenazas para establecer el nivel de protección adecuado para su organización.

- Informes

  Ver informes en tiempo real para supervisar el rendimiento Office 365 defender en su organización.

- Capacidades de investigación y respuesta de amenazas

  Use herramientas de vanguardia para investigar, comprender, simular y evitar amenazas.

- Capacidades automatizadas de investigación y respuesta

  Ahorre tiempo y esfuerzo en la investigación y mitigación de amenazas.

Defender para Office 365 alertas se puede clasificar como: 

- Verdadero positivo (TP) para la actividad malintencionada confirmada. 
- Falso positivo (FP) para actividad no malintencionada confirmada.

>[!Note]
>Microsoft 365 Defender portal reúne [https://security.microsoft.com](https://security.microsoft.com) la funcionalidad de los portales de seguridad de Microsoft existentes. El portal Microsoft 365 Defender hace hincapié en el acceso rápido a la información, diseños más sencillos y reunir información relacionada para un uso más fácil.
>

## <a name="microsoft-defender-for-cloud-apps"></a>Microsoft Defender for Cloud Apps

[Microsoft Defender para aplicaciones en](/defender-cloud-apps) la nube es un agente de seguridad de acceso a la nube (CASB) que admite varios modos de implementación, como la recopilación de registros, los conectores de API y el proxy inverso. Ofrece una visibilidad completa, control sobre los datos que se transmiten y análisis sofisticados para identificar y combatir las ciberamenazas en todos los servicios en la nube de Microsoft y de terceros.

Defender for Cloud Apps se integra de forma nativa con las principales soluciones de Microsoft y está diseñado pensando en los profesionales de seguridad. Ofrece una implementación simple, una administración centralizada y capacidades de automatización innovadoras.

El marco de Defender for Cloud Apps incluye la capacidad de proteger la red contra ciberamenazas y anomalías, detecta un comportamiento inusual en las aplicaciones en la nube para identificar ransomware, usuarios comprometidos o aplicaciones no seguras. Permite el análisis del uso de alto riesgo y puede corregirse automáticamente para limitar el riesgo a su organización.

Las alertas de Defender para Aplicaciones en la nube se pueden clasificar como: 

- TP para la actividad malintencionada confirmada. 
- Positivo real benigno (B-TP) para actividad sospechosa pero no malintencionada, como una prueba de penetración u otra acción sospechosa autorizada. 
- FP para actividad no malintencionada confirmada.

## <a name="alert-grading-playbooks"></a>Libros de juegos de clasificación de alertas

Consulta estos libros de juegos para ver los pasos para calificar alertas más rápidamente para las siguientes amenazas:

- [Actividad de reenvío de correo electrónico sospechoso](alert-grading-playbook-email-forwarding.md)
- [Reglas sospechosas de manipulación de la bandeja de entrada](alert-grading-playbook-inbox-manipulation-rules.md)
- [Reglas de reenvío de bandeja de entrada sospechosas](alert-grading-playbook-inbox-forwarding-rules.md)

Consulte [Investigar alertas](investigate-alerts.md) para obtener información sobre cómo examinar las alertas con el portal Microsoft 365 Defender web.
