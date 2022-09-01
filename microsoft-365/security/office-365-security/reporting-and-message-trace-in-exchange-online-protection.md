---
title: Creación de informes y seguimiento de mensajes
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.collection: M365-security-compliance
ms.localizationpriority: medium
ms.assetid: f40253f2-50a1-426e-9979-be74ba74cb61
ms.custom:
- seo-marvel-apr2020
description: En este artículo, obtendrá información sobre los informes y las herramientas de solución de problemas disponibles para los administradores de Microsoft Exchange Online Protection (EOP).
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: c8bca790e7916daacada685f15581f6c5fbcf6f2
ms.sourcegitcommit: ecc04b5b8f84b34255a2d5e90b5ab596af0d16c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2022
ms.locfileid: "67495798"
---
# <a name="reporting-and-message-trace-in-eop"></a>Seguimiento de mensajes y creación de informes Exchange Online Protection

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

En las organizaciones de Microsoft 365 con buzones de Exchange Online o organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online, EOP ofrece muchos informes diferentes que pueden ayudarle a determinar el estado general y el estado de su organización. También hay herramientas para ayudarle a solucionar problemas de eventos específicos (por ejemplo, un mensaje que no llegue a sus destinatarios) e informes de auditoría para ayudar con los requisitos de cumplimiento.

## <a name="usage-reports"></a>Informes de uso

- **Actividad de grupos de Microsoft 365**: vea información sobre el número de grupos de Microsoft 365 que se crean y usan. Para obtener más información, consulte [Informes de Microsoft 365 en el Centro de administración: grupos de Microsoft 365](../../admin/activity-reports/office-365-groups.md).
- **Email actividad**: vea información sobre el número de mensajes enviados, recibidos y leídos en toda la organización y por usuarios específicos. Para obtener más información, vea [Informes de Microsoft 365 en el Centro de administración: Email actividad](../../admin/activity-reports/email-activity.md).
- **Email uso de la aplicación**: vea información sobre las aplicaciones de correo electrónico que se usan. Esto incluye el número total de conexiones para cada aplicación y las versiones de Outlook que se conectan. Para obtener más información, consulte [Informes de Microsoft 365 en el Centro de administración: uso de aplicaciones Email](../../admin/activity-reports/email-apps-usage.md).
- **Uso del buzón de correo**: vea información sobre el almacenamiento usado, el consumo de cuota, el recuento de elementos y la última actividad (actividad de envío o lectura) de los buzones. Para obtener más información, consulte [Informes de Microsoft 365 en el Centro de administración: Uso del buzón de correo](../../admin/activity-reports/mailbox-usage.md).

## <a name="security-reports-in-the-microsoft-365-defender-portal"></a>Informes de seguridad en el portal de Microsoft 365 Defender

Estos informes mejorados proporcionan una experiencia de generación de informes interactiva para los administradores de EOP, que incluye información de resumen y la capacidad de explorar en profundidad para obtener más detalles.

- **Defender para Office 365**: ver información sobre vínculos seguros y datos adjuntos seguros que forman parte de Microsoft Defender para Office 365. Para obtener más información, vea [Ver informes de Defender para Office 365 en el portal de Microsoft 365 Defender](view-reports-for-mdo.md).
- **EOP**: vea información sobre las detecciones de malware, el correo suplantado, las detecciones de correo no deseado y el flujo de correo hacia y desde su organización. Para obtener más información, vea [Ver informes de seguridad de correo electrónico en el portal de Microsoft 365 Defender](view-email-security-reports.md).

## <a name="mail-flow-insights-in-the-security--compliance-center"></a>Reportes de flujo de Correo en el Centro de seguridad y cumplimiento

Para obtener más información, vea [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).

## <a name="custom-reports-using-microsoft-graph"></a>Informes personalizados con Microsoft Graph

Cree mediante programación informes que estén disponibles en el Centro de administración mediante Microsoft Graph. Para obtener más información, consulte [Introducción a Microsoft Graph](/graph/overview) y [Trabajar con informes de uso de Office 365 en Microsoft Graph](/graph/api/resources/report).

## <a name="message-trace"></a>Seguimiento de mensajes

Sigue los mensajes de correo electrónico mientras viajan a través de EOP. Puede determinar si el servicio recibió, rechazó, aplazó o entregó un mensaje de correo electrónico. También muestra qué acciones se realizaron en el mensaje antes de que alcanzara su estado final.

Puede usar esta información para responder de forma eficaz a las preguntas del usuario, solucionar problemas de flujo de correo, validar los cambios de directiva y aliviar la necesidad de ponerse en contacto con el soporte técnico para obtener ayuda.

Consulte [Seguimiento de mensajes en el portal de Microsoft 365 Defender](message-trace-scc.md).

## <a name="audit-logging"></a>Registro de auditoría

Realiza un seguimiento de los cambios específicos realizados por los administradores en su organización. Estos informes pueden ayudarle a solucionar problemas de configuración o a encontrar la causa de problemas relacionados con la seguridad o el cumplimiento. Consulte [Auditoría de informes en Exchange Online](/exchange/security-and-compliance/exchange-auditing-reports/exchange-auditing-reports).

## <a name="reporting-and-message-trace-data-availability-and-latency"></a>Informes, disponibilidad y latencia de los datos de seguimiento de mensajes

En la tabla siguiente se describe cuándo están disponibles los datos de informes y seguimiento de mensajes de EOP y durante cuánto tiempo.

|Tipo de informe|Datos disponibles (período retrospectivo)|Latencia|
|---|---|---|
|Informes de resumen de protección de correo|90 días|La agregación de datos de mensajes se completa casi por completo en 24-48 horas. Se pueden producir algunos pequeños cambios agregados incrementales durante un período de hasta 5 días.|
|Informes de detalles de protección de correo|90 días|Para los datos detallados que tienen menos de 7 días de antigüedad, los datos deberían aparecer en un plazo de 24 horas, pero puede que no estén completos hasta que transcurran 48 horas. Se pueden producir algunos pequeños cambios incrementales durante un período de hasta 5 días. <p> Para ver informes detallados de los mensajes que tienen más de 7 días de antigüedad, los resultados pueden tardar hasta unas cuantas horas.|
|Datos de seguimiento de mensajes|90 días|Cuando se ejecuta un seguimiento de mensajes para mensajes con antigüedad menor a 7 días, los mensajes deberían aparecer en un plazo de 5 a 30 minutos.<p> Cuando se ejecuta un seguimiento de mensajes para mensajes con antigüedad mayor a 7 días, los resultados pueden tardar hasta unas cuantas horas.|

> [!NOTE]
> La disponibilidad y latencia de los datos es la misma, tanto si se solicita a través del centro de administración como de PowerShell remoto.
