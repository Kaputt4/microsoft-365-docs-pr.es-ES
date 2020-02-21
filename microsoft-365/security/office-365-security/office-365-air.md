---
title: Investigación y respuesta automatizada de Office 365
keywords: AIR, autoIR, ATP, automatizado, investigación, respuesta, corrección, amenazas, avanzadas, amenazas, protección
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: Empiece a usar la investigación automatizada y las capacidades de respuesta en Office 365 Advanced Threat Protection Plan 2.
ms.openlocfilehash: d777ca0a61655c8df16d62c72691195bdec330a9
ms.sourcegitcommit: 2f117a6fd27a097ca25afa933dd088b69d483974
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/20/2020
ms.locfileid: "42175784"
---
# <a name="office-365-automated-investigation-and-response"></a>Investigación y respuesta automatizada de Office 365

[Protección contra amenazas avanzada de Office 365](office-365-atp.md) El plan 2 incluye capacidades de investigación y respuesta automatizada (AIR) potentes que pueden ahorrar tiempo y esfuerzo en el equipo de operaciones de seguridad. Cuando se desencadenan determinadas alertas, se inician una o más guías de seguridad y se inicia el proceso de investigación automatizada. Esto permite al equipo de operaciones de seguridad centrarse en las tareas de prioridad alta sin perder la vista de las alertas que se desencadenan. 

En un nivel alto, el flujo de aire funciona de la siguiente manera:

|Paso  |Qué ocurre  |
|---------|---------|
|1     |Un evento de Office desencadena una alerta y una guía de [seguridad](automated-investigation-response-office.md#security-playbooks) inicia una investigación automatizada de las alertas seleccionadas. <br/><br/>Como alternativa, un analista de seguridad puede [desencadenar una investigación automatizada](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer) mientras usa el [Explorador de amenazas](threat-explorer.md).        |
|segundo     |Mientras se ejecuta una investigación automatizada, recopila datos adicionales sobre el correo electrónico y las entidades relacionadas con ese correo electrónico: archivos, direcciones URL y destinatarios.  El ámbito de la investigación puede aumentar, a medida que se desencadenen nuevas alertas relacionadas.         |
|3     |Durante y después de una investigación automatizada, [los detalles y los resultados](air-view-investigation-results.md) están disponibles para su visualización. Los resultados incluyen [acciones recomendadas](air-remediation-actions.md) que se pueden llevar a cabo para responder y corregir cualquier amenaza que se detectó. Además, hay disponible un registro de la [Guía](air-view-investigation-results.md#playbook-log) que realiza un seguimiento de la actividad de la investigación.<br/><br/>Si su organización usa una solución de informes personalizada o una solución de terceros, puede [usar la API de actividad de administración de Office 365](air-custom-reporting.md) para ver información sobre las amenazas y las investigaciones automatizadas.         |
|4     |El equipo de operaciones de seguridad revisa los resultados de la [investigación y las recomendaciones](air-view-investigation-results.md)y [aprueba las acciones de corrección](air-remediation-actions.md#approve-or-reject-pending-actions). En Office 365, no se realiza ninguna acción automáticamente. Las acciones de corrección solo se realizan tras la aprobación del equipo de seguridad de la organización.         |

Durante y después de un proceso de investigación automatizado, su equipo de seguridad puede hacer lo siguiente:

- [Ver los detalles de una alerta relacionada con una investigación](air-view-investigation-results.md#view-details-about-an-alert-related-to-an-investigation)
- [Ver los detalles de los resultados de una investigación](air-view-investigation-results.md#view-details-of-an-investigation)
- [Revisión y aprobación de acciones como resultado de una investigación](air-remediation-actions.md#approve-or-reject-pending-actions)

Para obtener más información, vea [Cómo funciona Air](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office).