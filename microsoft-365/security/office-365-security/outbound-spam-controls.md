---
title: Protección contra el spam de salida
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6a601501-a6a8-4559-b2e7-56b59c96a586
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden obtener información sobre los controles de correo no deseado saliente en Exchange Online Protection (EOP) y qué hacer si necesita enviar correos masivos.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6d5a82b4a2c7f94b3c5d0958abc8c4552cc04032
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150693"
---
# <a name="outbound-spam-protection-in-eop"></a>Protección contra correo no deseado saliente en EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender para Office 365 plan 1 y plan 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

En las organizaciones de Microsoft 365 con buzones en Exchange Online o en organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online, nos tomamos muy en serio la administración del correo no deseado saliente. Un cliente que envía correo no deseado de forma intencionada o involuntarla desde su organización puede degradar la reputación de todo el servicio y puede afectar a la entrega de correo electrónico de otros clientes.

En este tema se describen los controles y notificaciones diseñados para ayudar a evitar el correo no deseado saliente y lo que puede hacer si necesita enviar correos masivos.

## <a name="what-admins-can-do-to-control-outbound-spam"></a>Qué pueden hacer los administradores para controlar el correo no deseado saliente

- Usar notificaciones **integradas:** cuando un usuario [](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) supera los [](configure-the-outbound-spam-policy.md) límites de envío de las directivas de servicio o correo no deseado saliente y tiene restricciones para enviar correo electrónico, la directiva de alerta predeterminada denominada **Usuario** restringido para enviar correo electrónico envía notificaciones por correo electrónico a los miembros del grupo **TenantAdmins** (administradores **globales).** Para configurar quién más recibe estas notificaciones, consulte Comprobar la configuración [de alerta para usuarios restringidos.](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users) Además, las directivas de alerta predeterminadas  denominadas **Límite** de envío de correo electrónico superaron y los patrones de envío de correo electrónico sospechoso detectados envían notificaciones de correo electrónico a los miembros del grupo **TenantAdmins** **(administradores** globales). Para obtener más información sobre las directivas de alerta, consulte [Directivas de alerta en el centro de seguridad y cumplimiento](../../compliance/alert-policies.md).

- Revise las **quejas** de correo no deseado de proveedores de correo electrónico de terceros: muchos servicios de correo electrónico como Outlook.com, Yahoo y AOL proporcionan un bucle de comentarios en el que, si algún usuario de su servicio marca un correo electrónico de Microsoft 365 como correo no deseado, el mensaje se empaqueta y se nos envía para su revisión. Para obtener más información sobre la compatibilidad de remitentes Outlook.com, vaya a <https://sendersupport.olc.protection.outlook.com/pm/services.aspx> .

## <a name="how-eop-controls-outbound-spam"></a>Cómo controla EOP el correo no deseado saliente

- **Segregación del tráfico de correo** electrónico saliente: todos los mensajes salientes que se envían a través del servicio se examinan en busca de correo no deseado. Si se determina que el mensaje es correo no deseado, se entrega desde un grupo de direcciones IP secundario de menor reputación denominado grupo _de entrega de alto riesgo._ Para más información, consulte [Grupo de entrega de alto riesgo para mensajes salientes](high-risk-delivery-pool-for-outbound-messages.md).

- **Supervisión de la reputación de la dirección IP** de origen: Microsoft 365 consulta varias listas de direcciones IP no válidas de terceros. Se genera una alerta si alguna de las direcciones IP que usamos para el correo electrónico saliente aparece en estas listas. Esto nos permite reaccionar rápidamente cuando el correo no deseado ha provocado que nuestra reputación se degrade. Cuando se genera una alerta, tenemos documentación interna que describe cómo quitar (eliminar) las direcciones IP de las listas de bloqueados.

- **Deshabilitar** cuentas que envían demasiado correo no deseado: aunque segregamos correo no deseado saliente en el grupo de entrega de alto riesgo, no podemos permitir que una cuenta (a menudo, una cuenta comprometida) envíe correo no deseado <sup>\*</sup> indefinidamente. Supervisamos las cuentas que envían correo no deseado y, cuando superan un límite no divulgado, se bloquea el envío de correo electrónico a la cuenta. Hay diferentes umbrales para usuarios individuales y para todo el espacio empresarial.

- Deshabilitar las cuentas que envían demasiado correo electrónico demasiado rápido: además de los límites que buscan mensajes marcados como correo no deseado, también hay límites que bloquean las cuentas cuando alcanzan un límite global de mensajes salientes, independientemente del veredicto de filtrado de correo no deseado en los mensajes <sup>\*</sup> salientes. Una cuenta comprometida podría enviar correo no deseado de día cero (no reconocido previamente) que el filtro de correo no deseado pierde. Dado que puede ser difícil identificar una campaña de correo masivo legítima frente a una campaña de correo no deseado, estos límites ayudan a minimizar los posibles daños.

<sup>\*</sup> No anunciamos los límites exactos para que los spammers no puedan jugar al sistema, por lo que podemos aumentar o disminuir los límites según sea necesario. Los límites son lo suficientemente altos como para evitar que un usuario empresarial promedio los supere y lo suficientemente bajos como para ayudar a contener los daños causados por un spammer.

## <a name="recommendations-for-customers-who-want-to-send-mass-mailings-through-eop"></a>Recomendaciones para los clientes que desean enviar correos masivos a través de EOP

Es difícil encontrar un equilibrio entre los clientes que desean enviar un gran volumen de correo electrónico frente a proteger el servicio de cuentas comprometidas y remitentes de correo electrónico masivo con procedimientos de adquisición de destinatarios deficientes. El costo de que un origen de correo electrónico de Microsoft 365 se aterriza en una lista de bloqueados de IP de terceros es mayor que bloquear a un usuario que envía demasiado correo electrónico.

Como se describe en la descripción del servicio [de Exchange Online,](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits)el uso de EOP para enviar correo electrónico masivo no es un uso admitido del servicio y solo se permite en el "mejor esfuerzo". Para los clientes que quieran enviar correo electrónico masivo, se recomiendan las siguientes soluciones:

- **Enviar correo masivo a través de** servidores de correo electrónico locales: esto significa que los clientes tendrán que mantener su propia infraestructura de correo electrónico para envíos masivos de correo.

- **Use un proveedor de correo** masivo de terceros: hay varios proveedores de soluciones de correo masivo de terceros que puede usar para enviar correos masivos. Estas compañías tienen un interés especial en trabajar con los clientes para garantizar buenas prácticas de envío de correo electrónico.

The Messaging, Mobile, Malware Anti-Abuse Working Group (GOLDWG) publishes its membership roster at <https://www.maawg.org/about/roster> . Hay varios proveedores de correo electrónico masivo en la lista y se sabe que son ciudadanos de Internet responsables.
