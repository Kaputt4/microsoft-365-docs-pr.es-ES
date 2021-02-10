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
description: En este artículo, aprenderá sobre los informes y las herramientas de solución de problemas disponibles para los administradores de Microsoft Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 86c9eb0ee050c4c1a40ef7f29ea3d01dc202be9a
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166680"
---
# <a name="reporting-and-message-trace-in-eop"></a>Informes y seguimiento de mensajes en EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

En organizaciones de Microsoft 365 con buzones en Exchange Online o organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online, EOP ofrece muchos informes diferentes que pueden ayudarle a determinar el estado general y el estado de su organización. También hay herramientas para ayudarle a solucionar problemas de eventos específicos (por ejemplo, un mensaje que no llegue a sus destinatarios) e informes de auditoría para ayudar con los requisitos de cumplimiento.

## <a name="usage-reports"></a>Informes de uso

**Actividad de grupos de Microsoft 365:** ver información sobre el número de grupos de Microsoft 365 que se crean y usan.

**Actividad de correo** electrónico: ver información sobre el número de mensajes enviados, recibidos y leídos en toda la organización y por usuarios específicos.

**Uso de la aplicación de** correo electrónico: ver información sobre las aplicaciones de correo electrónico que se usan. Esto incluye el número total de conexiones para cada aplicación y las versiones de Outlook que se conectan.

**Uso del buzón:** ver información sobre el almacenamiento usado, el consumo de cuota, el recuento de elementos y la última actividad (actividad de envío o lectura) de los buzones.

Consulte los siguientes recursos para obtener más información:

- [Informes de Microsoft 365 en el centro de administración: grupos de Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/activity-reports/office-365-groups)

- [Informes de Microsoft 365 en el centro de administración: actividad de correo electrónico](https://docs.microsoft.com/microsoft-365/admin/activity-reports/email-activity)

- [Informes de Microsoft 365 en el centro de administración: uso de aplicaciones de correo electrónico](https://docs.microsoft.com/microsoft-365/admin/activity-reports/email-apps-usage)

- [Informes de Microsoft 365 en el centro de administración: uso del buzón](https://docs.microsoft.com/microsoft-365/admin/activity-reports/mailbox-usage)

## <a name="security--compliance-reports-in-the-microsoft-365-admin-center"></a>Informes de & cumplimiento normativo en el Centro de administración de Microsoft 365

Estos informes mejorados proporcionan una experiencia interactiva de informes para los administradores de EOP, que incluye información resumida y la capacidad de explorar en profundidad para obtener más detalles.

**Defender para Office 365:** ver información sobre vínculos seguros y datos adjuntos seguros que forman parte de Microsoft Defender para Office 365.

**EOP:** ver información sobre detecciones de malware, correo suplantado, detecciones de correo no deseado y flujo de correo hacia y desde su organización.

[Ver informes de Defender para Office 365](view-reports-for-atp.md)

## <a name="custom-reports-using-microsoft-graph"></a>Informes personalizados con Microsoft Graph

Cree mediante programación informes que estén disponibles en el centro de administración mediante Microsoft Graph. Para obtener más información, vea [Información general sobre Microsoft Graph](https://docs.microsoft.com/graph/overview) y trabajar con informes de uso de Office [365 en Microsoft Graph.](https://docs.microsoft.com/graph/api/resources/report)

## <a name="message-trace"></a>Seguimiento de mensajes

Sigue los mensajes de correo electrónico mientras viajan a través de EOP. Puede determinar si el servicio recibió, rechazó, aplazó o entregó un mensaje de correo electrónico. También muestra las acciones que se realizaron en el mensaje antes de alcanzar su estado final.

Puede usar esta información para responder eficazmente a las preguntas del usuario, solucionar problemas de flujo de correo, validar los cambios de directiva y mitigar la necesidad de ponerse en contacto con el soporte técnico para obtener ayuda.

Consulte [Seguimiento de mensajes en el Centro de seguridad & cumplimiento.](message-trace-scc.md)

## <a name="audit-logging"></a>Registro de auditoría

Realiza un seguimiento de los cambios específicos realizados por los administradores en su organización. Estos informes pueden ayudarle a solucionar problemas de configuración o a encontrar la causa de problemas relacionados con la seguridad o el cumplimiento. Vea [Informes de auditoría en EOP.](auditing-reports-in-eop.md)

## <a name="reporting-and-message-trace-data-availability-and-latency"></a>Informes, disponibilidad y latencia de los datos de seguimiento de mensajes

En la tabla siguiente se describe cuándo están disponibles los datos de informes y seguimiento de mensajes de EOP y durante cuánto tiempo.

****

|Tipo de informe|Datos disponibles (período retrospectivo)|Latencia|
|---|---|---|
|Informes de resumen de protección de correo|90 días|La agregación de datos de mensajes se completa casi por completo en 24-48 horas. Se pueden producir algunos pequeños cambios agregados incrementales durante un período de hasta 5 días.|
|Informes de detalles de protección de correo|90 días|Para los datos detallados que tienen menos de 7 días de antigüedad, los datos deberían aparecer en un plazo de 24 horas, pero puede que no estén completos hasta que transcurran 48 horas. Se pueden producir algunos pequeños cambios incrementales durante un período de hasta 5 días. <p> Para ver informes detallados de los mensajes que tienen más de 7 días de antigüedad, los resultados pueden tardar hasta unas cuantas horas.|
|Datos de seguimiento de mensajes|90 días|Cuando se ejecuta un seguimiento de mensajes para mensajes con antigüedad menor a 7 días, los mensajes deberían aparecer en un plazo de 5 a 30 minutos.<p> Cuando se ejecuta un seguimiento de mensajes para mensajes con antigüedad mayor a 7 días, los resultados pueden tardar hasta unas cuantas horas.|
|

> [!NOTE]
> La disponibilidad y la latencia de los datos son las mismas si se solicitan a través del Centro de administración o PowerShell remoto.
