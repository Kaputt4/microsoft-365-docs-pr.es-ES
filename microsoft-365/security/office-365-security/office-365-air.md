---
title: Investigación y respuesta automatizadas (AIR) en Office 365
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
ms.custom: air
ms.openlocfilehash: c06874ea5d55334d9049d6c5d9d5c55a499dae06
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/13/2020
ms.locfileid: "42634028"
---
# <a name="automated-investigation-and-response-air-in-office-365"></a>Investigación y respuesta automatizadas (AIR) en Office 365

[Protección contra amenazas avanzada de Office 365](office-365-atp.md) El plan 2 incluye capacidades de investigación y respuesta automatizada (AIR) potentes que pueden ahorrar tiempo y esfuerzo en el equipo de operaciones de seguridad. Cuando se desencadenan determinadas alertas, se inician una o más guías de seguridad y se inicia el proceso de investigación automatizada. Esto permite al equipo de operaciones de seguridad centrarse en las tareas de prioridad alta sin perder la vista de las alertas que se desencadenan. 

## <a name="the-overall-flow-of-air"></a>Flujo general de aire

Se desencadena una alerta y se inicia una guía de seguridad, que inicia una investigación automatizada. O bien, un analista de seguridad desencadena una investigación automatizada mientras utiliza el explorador de amenazas. La investigación automática se ejecuta y, normalmente, se identifican ciertas acciones de corrección. Esas acciones son revisadas y aprobadas por su equipo de operaciones de seguridad y se completa la investigación. 

En la siguiente tabla se describe el flujo de aire general, paso a paso:

|Paso  |Qué ocurre  |
|---------|---------|
|1     |Un evento de Office desencadena una alerta y una guía de [seguridad](automated-investigation-response-office.md#security-playbooks) inicia una investigación automatizada de las alertas seleccionadas. <br/><br/>Como alternativa, un analista de seguridad puede [desencadenar una investigación automatizada](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer) mientras usa el [Explorador de amenazas](threat-explorer.md).        |
|segundo     |Mientras se ejecuta una investigación automatizada, recopila datos adicionales sobre el correo electrónico y las entidades relacionadas con ese correo electrónico: archivos, direcciones URL y destinatarios.  El ámbito de la investigación puede aumentar, a medida que se desencadenen nuevas alertas relacionadas.         |
|3     |Durante y después de una investigación automatizada, [los detalles y los resultados](air-view-investigation-results.md) están disponibles para su visualización. Los resultados incluyen [acciones recomendadas](air-remediation-actions.md) que se pueden llevar a cabo para responder y corregir cualquier amenaza que se detectó. Además, hay disponible un registro de la [Guía](air-view-investigation-results.md#playbook-log) que realiza un seguimiento de la actividad de la investigación.<br/><br/>Si su organización usa una solución de informes personalizada o una solución de terceros, puede [usar la API de actividad de administración de Office 365](air-custom-reporting.md) para ver información sobre las amenazas y las investigaciones automatizadas.         |
|4      |El equipo de operaciones de seguridad revisa los resultados de la [investigación y las recomendaciones](air-view-investigation-results.md)y [aprueba las acciones de corrección](air-remediation-actions.md#approve-or-reject-pending-actions). En Office 365, no se realiza ninguna acción automáticamente. Las acciones de corrección solo se realizan tras la aprobación del equipo de seguridad de la organización.         |

Durante y después de un proceso de investigación automatizado, su equipo de seguridad puede hacer lo siguiente:

- [Ver los detalles de una alerta relacionada con una investigación](air-view-investigation-results.md#view-details-about-an-alert-related-to-an-investigation)
- [Ver los detalles de los resultados de una investigación](air-view-investigation-results.md#view-details-of-an-investigation)
- [Revisión y aprobación de acciones como resultado de una investigación](air-remediation-actions.md#approve-or-reject-pending-actions)

Para obtener más información, vea [Cómo funciona Air](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office).

## <a name="how-to-get-air"></a>Cómo obtener aire

Office 365 AIR está incluido en las siguientes suscripciones:

- Microsoft 365 E5
- Office 365 E5
- Protección contra amenazas de Microsoft
- Protección contra amenazas avanzada de Office 365 (plan 2)

Si no tiene ninguna de estas suscripciones, [inicie una prueba gratuita](https://go.microsoft.com/fwlink/p/?LinkID=698279&culture=en-US&country=US).

Para obtener más información acerca de la disponibilidad de características, visite la [característica disponibilidad en los planes de protección contra amenazas avanzada (ATP)](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).

## <a name="required-permissions-to-use-air-capabilities"></a>Permisos necesarios para usar capacidades de AIR

Los permisos se conceden a través de determinadas funciones, como las que se describen en la tabla siguiente: 

|Tarea |Roles necesarios |
|--|--|
|Para configurar las características de AIR |Una de las siguientes funciones: <br/>- **Administrador global**<br/>- **Administrador de seguridad** <br/>Estos roles se pueden asignar en [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) o en el [centro de seguridad & cumplimiento de Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center). |
|Para aprobar o rechazar las acciones recomendadas|Una de las siguientes funciones, asignada en [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) o en el [centro de seguridad & cumplimiento de Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)):<br/>- **Administrador global** <br/>- **Administrador de seguridad**<br/>- **Lector de seguridad** <br/>--- y ---<br/>- **Búsqueda y depuración** (este rol solo se asigna en el [centro de cumplimiento de & de seguridad de Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center). Es posible que tenga que crear un nuevo grupo de funciones y agregar el rol de búsqueda y depuración al nuevo grupo de roles.

## <a name="related-articles"></a>Artículos relacionados

- [Investigación y respuesta automatizada en la Protección contra amenazas de Microsoft](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)

- [Investigación y corrección automáticas en protección contra amenazas avanzada de Microsoft defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)