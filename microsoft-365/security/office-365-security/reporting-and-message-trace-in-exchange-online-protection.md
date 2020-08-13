---
title: Creación de informes y seguimiento de mensajes
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: f40253f2-50a1-426e-9979-be74ba74cb61
ms.custom:
- seo-marvel-apr2020
description: En este artículo, obtendrá información sobre los informes y las herramientas de solución de problemas disponibles para los administradores de Microsoft Exchange Online Protection (EOP).
ms.openlocfilehash: ddf8c021681bb600548b134d678d1e0fb0f29d0c
ms.sourcegitcommit: 6a1a8aa024fd685d04da97bfcbc8eadacc488534
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2020
ms.locfileid: "46652806"
---
# <a name="reporting-and-message-trace-in-eop"></a>Informes y seguimiento de mensajes en EOP

En Microsoft 365 organizaciones con buzones de correo en Exchange online o en organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online, EOP ofrece muchos informes diferentes que pueden ayudarle a determinar el estado general y el mantenimiento de su organización. También hay herramientas para ayudarle a solucionar problemas de eventos específicos (por ejemplo, un mensaje que no llegue a sus destinatarios) e informes de auditoría para ayudar con los requisitos de cumplimiento.

## <a name="usage-reports"></a>Informes de uso

**Actividad de microsoft 365 Groups**: ver información sobre el número de grupos de Microsoft 365 que se crean y usan.

**Actividad de correo electrónico**: ver información sobre el número de mensajes enviados, recibidos y leídos en toda la organización y por usuarios específicos.

**Uso de la aplicación de correo electrónico**: ver información sobre las aplicaciones de correo electrónico que se usan. Esto incluye el número total de conexiones de cada aplicación y las versiones de Outlook que se conectan.

**Uso de buzón de correo**: ver información sobre el almacenamiento usado, el consumo de cuotas, el recuento de elementos y la última actividad (actividad de envío o lectura) para los buzones.

Consulte los siguientes recursos para obtener más información:

- [Informes de Microsoft 365 en el centro de administración (grupos de Microsoft 365)](https://docs.microsoft.com/microsoft-365/admin/activity-reports/office-365-groups)

- [Informes de Microsoft 365 en el centro de administración: actividad de correo electrónico](https://docs.microsoft.com/microsoft-365/admin/activity-reports/email-activity)

- [Informes de Microsoft 365 en el centro de administración: uso de aplicaciones de correo electrónico](https://docs.microsoft.com/microsoft-365/admin/activity-reports/email-apps-usage)

- [Informes de Microsoft 365 en el centro de administración: uso de buzones](https://docs.microsoft.com/microsoft-365/admin/activity-reports/mailbox-usage)

## <a name="security--compliance-reports-in-the-microsoft-365-admin-center"></a>Informes de cumplimiento de & de seguridad en el centro de administración de Microsoft 365

Estos informes mejorados proporcionan una experiencia de creación de informes interactiva para los administradores de EOP, que incluye información de Resumen y la capacidad de profundizar para obtener más detalles.

**Protección contra amenazas avanzada (ATP)**: ver información sobre vínculos seguros y datos adjuntos seguros que forman parte de ATP.

**EOP**: ver información sobre las detecciones de malware, el correo falsificado, las detecciones de correo no deseado y el flujo de correo hacia y desde la organización.

[Ver informes para la protección contra amenazas avanzada de Office 365](view-reports-for-atp.md)

## <a name="custom-reports-using-microsoft-graph"></a>Informes personalizados con Microsoft Graph

Cree mediante programación informes que estén disponibles en el centro de administración mediante Microsoft Graph. Para obtener más información, vea [información general de Microsoft Graph](https://docs.microsoft.com/graph/overview) y [trabajar con los informes de uso de Office 365 en Microsoft Graph](https://docs.microsoft.com/graph/api/resources/report).

## <a name="message-trace"></a>Seguimiento de mensajes

Sigue los mensajes de correo electrónico mientras viajan a través de EOP. Puede determinar si un mensaje de correo electrónico se ha recibido, rechazado, aplazado o entregado por el servicio. También muestra las acciones que se tomaron en el mensaje antes de que alcanzara su estado final.

Puede usar esta información para responder de forma eficaz a las preguntas del usuario, solucionar problemas del flujo de correo, validar los cambios en la Directiva y aliviar la necesidad de ponerse en contacto con el soporte técnico para obtener ayuda.

Consulte [seguimiento de mensajes en el centro de seguridad & cumplimiento](message-trace-scc.md).

## <a name="audit-logging"></a>Registro de auditoría

Realiza un seguimiento de los cambios específicos realizados por los administradores en la organización. Estos informes pueden ayudarle a solucionar problemas de configuración o a encontrar la causa de problemas relacionados con el cumplimiento o la seguridad. Vea [Auditing Reports in EOP](auditing-reports-in-eop.md).

## <a name="reporting-and-message-trace-data-availability-and-latency"></a>Informes, disponibilidad y latencia de los datos de seguimiento de mensajes

En la tabla siguiente se describe cuándo están disponibles los informes y los datos de seguimiento de mensajes de EOP y durante cuánto tiempo.

****

|Tipo de informe|Datos disponibles (período retrospectivo)|Latencia|
|---|---|---|
|Informes de Resumen de protección de correo|90 días|La agregación de datos de mensajes se completa casi por completo en 24-48 horas. Se pueden producir algunos pequeños cambios agregados incrementales durante un período de hasta 5 días.|
|Informes de detalles de protección de correo|90 días|Para los datos detallados que tienen menos de 7 días de antigüedad, los datos deberían aparecer en un plazo de 24 horas, pero puede que no estén completos hasta que transcurran 48 horas. Se pueden producir algunos pequeños cambios incrementales durante un período de hasta 5 días. <br/><br/> Para ver informes detallados de los mensajes que tienen más de 7 días de antigüedad, los resultados pueden tardar hasta unas cuantas horas.|
|Datos de seguimiento de mensajes|90 días|Cuando se ejecuta un seguimiento de mensajes para mensajes con antigüedad menor a 7 días, los mensajes deberían aparecer en un plazo de 5 a 30 minutos.<br/><br/> Cuando se ejecuta un seguimiento de mensajes para mensajes con antigüedad mayor a 7 días, los resultados pueden tardar hasta unas cuantas horas.|
|

> [!NOTE]
> La disponibilidad y la latencia de los datos son las mismas si se solicitan a través del centro de administración o PowerShell remoto.
