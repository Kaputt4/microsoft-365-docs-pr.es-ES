---
title: Protección contra correo no deseado saliente en Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6a601501-a6a8-4559-b2e7-56b59c96a586
ms.collection:
- M365-security-compliance
description: Los administradores pueden obtener información sobre cómo Office 365 y Exchange Online Protection (EOP) protegen a los clientes contra el correo no deseado saliente y qué hacer si necesita enviar correos masivos.
ms.openlocfilehash: 99e764944335be923ee1918851d4072ea98d3a32
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895328"
---
# <a name="outbound-spam-protection-in-office-365"></a>Protección contra correo no deseado saliente en Office 365

Tenemos que administrar el correo no deseado de salida en serio, porque Office 365 (Exchange online o Exchange Online Protection (EOP) sin buzones de correo de Exchange Online) es un servicio en línea en el que muchos clientes usan un grupo compartido de recursos. Un cliente de Office 365 el envío de correo no deseado intencional o accidentalmente a su organización puede degradar la reputación de todo el servicio y puede afectar la entrega de correo electrónico para otros clientes.

En este tema se describen los controles y las notificaciones diseñados para ayudar a evitar el correo no deseado saliente y qué se puede hacer si es necesario enviar correos masivos.

## <a name="what-admins-can-do-to-control-outbound-spam"></a>Qué pueden hacer los administradores para controlar el correo no deseado saliente

- **Usar notificaciones integradas**: cuando un usuario supere [el](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) envío de límites de las directivas de servicio o [correo no deseado salientes](configure-the-outbound-spam-policy.md) y se restringe el envío de correo electrónico, la Directiva de alerta predeterminada denominada **usuario con restricción de envío de correo** electrónico enviará notificaciones de correo electrónico a los miembros del grupo **TenantAdmins** (**administradores globales**). Para configurar quién más recibe estas notificaciones, consulte [Verify The Alert Settings for Restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users). Además, las directivas de alerta predeterminadas denominadas **límite de envío de correo electrónico y superado** los **modelos de envío de correo electrónico sospechoso** envían notificaciones de correo electrónico a los miembros del grupo **TenantAdmins** (**global Admins**). Para obtener más información acerca de las directivas de alertas, consulte [Alert policies en el centro de seguridad y cumplimiento](../../compliance/alert-policies.md).

- **Revise las reclamaciones de correo no deseado de proveedores de correo electrónico de terceros**: muchos servicios de correo electrónico como Outlook.com, Yahoo y AOL proporcionan un bucle de comentarios en el que si algún usuario del servicio marca un correo electrónico de Office 365 como correo no deseado, el mensaje se empaqueta y se envía a los usuarios para que los revisen. Para obtener más información acerca de la compatibilidad de remitentes para <https://sendersupport.olc.protection.outlook.com/pm/services.aspx>Outlook.com, vaya a.

## <a name="how-eop-controls-outbound-spam"></a>Cómo EOP controla el correo no deseado saliente

- **Segregación de tráfico de correo saliente**: todos los mensajes salientes que se envían a través del servicio se examinan en busca de correo no deseado. Si se determina que el mensaje es correo no deseado, se entrega desde un grupo de direcciones IP secundarias y menos prestigiosos denominado _grupo de entrega de alto riesgo_. Para obtener más información, consulte [grupo de entrega de alto riesgo para mensajes salientes en Office 365](high-risk-delivery-pool-for-outbound-messages.md).

- **Supervisión de nuestra dirección IP de origen reputación**: Office 365 consulta varias listas de direcciones IP bloqueadas de terceros. Se genera una alerta si alguna de las direcciones IP que usamos para el correo electrónico saliente aparece en estas listas. Esto nos permite reaccionar rápidamente cuando el correo no deseado ha provocado una degradación de nuestra reputación. Cuando se genera una alerta, tenemos documentación interna que describe cómo obtener nuestras direcciones IP (en la lista) de las listas de bloqueados.

- **Deshabilitar cuentas que envían demasiado correo no deseado**<sup>\*</sup>: aunque se segrega el correo no deseado saliente en el grupo de entrega de alto riesgo, no se puede permitir una cuenta (a menudo, una cuenta en peligro) para enviar correo electrónico no deseado de forma indefinida. Se supervisan las cuentas que envían correo no deseado y, cuando se supera un límite no divulgado, se bloquea la cuenta para enviar correo electrónico. Hay distintos umbrales para los usuarios individuales y para todo el espacio empresarial.

- **Deshabilitar cuentas que envían demasiado correo electrónico demasiado rápido**<sup>\*</sup>: además de los límites que buscan los mensajes marcados como correo no deseado, también hay límites para bloquear las cuentas cuando alcanzan un límite de mensajes salientes generales, independientemente del filtro de correo no deseado en los mensajes salientes. Una cuenta en peligro podría enviar correo no deseado de día cero (no reconocido previamente) que perdió el filtro de correo no deseado. Debido a que puede ser difícil identificar una campaña de correo masivo legítima en comparación con una campaña de correo no deseado, estos límites ayudan a minimizar los posibles daños.

<sup>\*</sup>No anunciamos los límites exactos para que los remitentes de correo no deseado puedan jugar el sistema y, por lo tanto, podemos aumentar o disminuir los límites según sea necesario. Los límites son lo suficientemente altos como para evitar que un usuario de una empresa promedio los supere siempre y lo suficientemente bajo como para ayudar a contener el daño causado por un remitente de correo no deseado.

## <a name="recommendations-for-customers-who-want-to-send-mass-mailings-through-eop"></a>Recomendaciones para los clientes que desean enviar correo masivo a través de EOP

Es difícil alcanzar un equilibrio entre los clientes que desean enviar un gran volumen de correo electrónico frente a proteger el servicio de cuentas comprometidas y remitentes de correo electrónico masivo con prácticas deficientes de adquisición de destinatarios. El costo de un aterrizaje de origen de correo electrónico de Office 365 en una lista de direcciones IP bloqueadas de terceros es mayor que el bloqueo de un usuario que está enviando demasiado correo electrónico.

Como se describe en la [Descripción del servicio de Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits), el uso de EOP para enviar correo electrónico masivo no es un uso compatible del servicio y solo se permite en base a un "mejor esfuerzo". Para los clientes que quieren enviar correo electrónico masivo, se recomiendan las siguientes soluciones:

- **Enviar correo electrónico masivo a través de servidores de correo electrónico locales**: Esto significa que los clientes deberán mantener su propia infraestructura de correo electrónico para el envío masivo de correo.

- **Usar un proveedor de correo electrónico masivo**de terceros: hay varios proveedores de soluciones de correo masivo de terceros que puede usar para enviar correos masivos. Estas empresas tienen un interés irrevocable en trabajar con los clientes para garantizar buenas prácticas de envío de correo electrónico.

El grupo de trabajo anti-abuse de mensajería, móvil y malware (MAAWG) publica su lista de <https://www.maawg.org/about/roster>pertenencia en. Hay varios proveedores de correo electrónico masivo en la lista y se sabe que son ciudadanos de Internet responsables.
