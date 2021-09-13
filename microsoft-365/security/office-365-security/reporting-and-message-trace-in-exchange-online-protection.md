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
localization_priority: Normal
ms.assetid: f40253f2-50a1-426e-9979-be74ba74cb61
ms.custom:
- seo-marvel-apr2020
description: En este artículo, aprenderá sobre los informes y las herramientas de solución de problemas disponibles para los administradores de Microsoft Exchange Online protección contra errores (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: cc49a92d5fb1fb0368b14eef7524638542f38deb
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/12/2021
ms.locfileid: "59187350"
---
# <a name="reporting-and-message-trace-in-eop"></a>Informes y seguimiento de mensajes en EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

En Microsoft 365 organizaciones con buzones en organizaciones Exchange Online o independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online, EOP ofrece muchos informes diferentes que pueden ayudarle a determinar el estado general y el estado de su organización. También hay herramientas para ayudarle a solucionar problemas de eventos específicos (por ejemplo, un mensaje que no llegue a sus destinatarios) e informes de auditoría para ayudar con los requisitos de cumplimiento.

## <a name="usage-reports"></a>Informes de uso

- **Microsoft 365 de grupos:** ver información sobre el número de grupos Microsoft 365 que se crean y usan. Para obtener más información, [vea Microsoft 365 informes en el](../../admin/activity-reports/office-365-groups.md)Centro de administración : Microsoft 365 grupos .
- **Actividad de correo** electrónico: vea información sobre el número de mensajes enviados, recibidos y leídos en toda la organización y por usuarios específicos. Para obtener más información, [vea Microsoft 365 informes en el Centro de administración - Actividad de correo electrónico](../../admin/activity-reports/email-activity.md).
- **Uso de la aplicación de** correo electrónico: ver información sobre las aplicaciones de correo electrónico que se usan. Esto incluye el número total de conexiones para cada aplicación y las versiones de Outlook que se conectan. Para obtener más información, consulta Microsoft 365 informes en el Centro de [administración : Uso de aplicaciones de correo electrónico.](../../admin/activity-reports/email-apps-usage.md)
- **Uso del** buzón: ver información sobre el almacenamiento usado, el consumo de cuota, el recuento de elementos y la última actividad (actividad de envío o lectura) de los buzones. Para obtener más información, [vea Microsoft 365 informes en el Centro de administración - Uso de buzones](../../admin/activity-reports/mailbox-usage.md).

## <a name="security-reports-in-the-microsoft-365-defender-portal"></a>Informes de seguridad en el portal Microsoft 365 defender

Estos informes mejorados proporcionan una experiencia interactiva de informes para los administradores de EOP, que incluye información de resumen y la capacidad de explorar más detalles.

- **Defender para Office 365:** ver información sobre Caja fuerte vínculos y Caja fuerte adjuntos que forman parte de Microsoft Defender para Office 365. Para obtener más información, vea [View Defender for Office 365 reports in the Microsoft 365 Defender portal](view-reports-for-mdo.md).
- **EOP:** ver información sobre detecciones de malware, correo suplantado, detecciones de correo no deseado y flujo de correo desde y hacia su organización. Para obtener más información, vea [View email security reports in the Microsoft 365 Defender portal](view-email-security-reports.md).

## <a name="custom-reports-using-microsoft-graph"></a>Informes personalizados con Microsoft Graph

Cree informes disponibles en el Centro de administración mediante programación mediante Microsoft Graph. Para obtener más información, vea [Overview of Microsoft Graph](/graph/overview) and Working with Office 365 usage reports in Microsoft [Graph](/graph/api/resources/report).

## <a name="message-trace"></a>Seguimiento de mensajes

Sigue los mensajes de correo electrónico mientras viajan a través de EOP. Puede determinar si el servicio recibió, rechazó, aplazó o entregó un mensaje de correo electrónico. También muestra qué acciones se realizaron en el mensaje antes de alcanzar su estado final.

Puede usar esta información para responder eficazmente a las preguntas del usuario, solucionar problemas de flujo de correo, validar los cambios de directiva y aliviar la necesidad de ponerse en contacto con el soporte técnico para obtener asistencia.

Vea [Seguimiento de mensajes en el Microsoft 365 Defender portal](message-trace-scc.md).

## <a name="audit-logging"></a>Registro de auditoría

Realiza un seguimiento de los cambios específicos realizados por los administradores en su organización. Estos informes pueden ayudarle a solucionar problemas de configuración o a encontrar la causa de problemas relacionados con la seguridad o el cumplimiento. Vea [Informes de auditoría en Exchange Online](/exchange/security-and-compliance/exchange-auditing-reports/exchange-auditing-reports).

## <a name="reporting-and-message-trace-data-availability-and-latency"></a>Informes, disponibilidad y latencia de los datos de seguimiento de mensajes

En la tabla siguiente se describe cuándo los datos de seguimiento de mensajes y informes de EOP están disponibles y durante cuánto tiempo.

<br>

****

|Tipo de informe|Datos disponibles (período retrospectivo)|Latencia|
|---|---|---|
|Informes de resumen de protección de correo|90 días|La agregación de datos de mensajes se completa casi por completo en 24-48 horas. Se pueden producir algunos pequeños cambios agregados incrementales durante un período de hasta 5 días.|
|Informes de detalles de protección de correo|90 días|Para los datos detallados que tienen menos de 7 días de antigüedad, los datos deberían aparecer en un plazo de 24 horas, pero puede que no estén completos hasta que transcurran 48 horas. Se pueden producir algunos pequeños cambios incrementales durante un período de hasta 5 días. <p> Para ver informes detallados de los mensajes que tienen más de 7 días de antigüedad, los resultados pueden tardar hasta unas cuantas horas.|
|Datos de seguimiento de mensajes|90 días|Cuando se ejecuta un seguimiento de mensajes para mensajes con antigüedad menor a 7 días, los mensajes deberían aparecer en un plazo de 5 a 30 minutos.<p> Cuando se ejecuta un seguimiento de mensajes para mensajes con antigüedad mayor a 7 días, los resultados pueden tardar hasta unas cuantas horas.|
|

> [!NOTE]
> La disponibilidad y la latencia de los datos son las mismas si se solicitan a través del Centro de administración o powerShell remoto.
