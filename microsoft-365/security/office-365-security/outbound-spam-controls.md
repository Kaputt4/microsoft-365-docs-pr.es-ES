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
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.assetid: 6a601501-a6a8-4559-b2e7-56b59c96a586
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden obtener información sobre los controles de correo no deseado saliente en Exchange Online Protection (EOP) y qué hacer si necesita enviar correos electrónicos masivos.
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: 76e9e11d0b49237ff3a29dcb9eadf113f9db112e
ms.sourcegitcommit: 2b89bcff547e00be3d38dc8d1e6cbcf8f41eba42
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2022
ms.locfileid: "67598327"
---
# <a name="outbound-spam-protection-in-eop"></a>Protección contra correo no deseado saliente en EOP

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

En las organizaciones de Microsoft 365 con buzones de correo en organizaciones Exchange Online o independientes de Exchange Online Protection (EOP) sin Exchange Online buzones, tomamos en serio la administración del correo no deseado saliente. Incluso si un cliente envía correo no deseado de forma intencionada o involuntaria desde su organización, esa acción puede degradar la reputación de todo el servicio y puede afectar a la entrega de correo electrónico para otros clientes.

En este artículo se describen los controles y notificaciones que están diseñados para ayudar a evitar el correo no deseado saliente y lo que puede hacer si necesita enviar correos electrónicos masivos.

## <a name="what-admins-can-do-to-control-outbound-spam"></a>Qué pueden hacer los administradores para controlar el correo no deseado saliente

- **Usar notificaciones integradas**: cuando un usuario supera los límites de envío de las [directivas de correo no deseado de salida](configure-the-outbound-spam-policy.md) o [servicio](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) y tiene restringido el envío de correo electrónico, la directiva de alerta predeterminada denominada **Usuario restringido al envío de correo electrónico** envía notificaciones por correo electrónico a los miembros del grupo **TenantAdmins** (**administradores globales**). Para configurar quién más recibe estas notificaciones, consulte [Comprobación de la configuración de alertas para usuarios restringidos](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users). Además, se han superado las directivas de alerta predeterminadas denominadas **Email límite de envío** y los **patrones de envío de correo electrónico sospechoso detectados** envían notificaciones por correo electrónico a los miembros del grupo **TenantAdmins** (**administradores globales**). Para obtener más información sobre las directivas de alerta, consulte [Directivas de alerta en Microsoft 365](../../compliance/alert-policies.md).

- **Revisar las quejas de correo no deseado de proveedores de correo electrónico de terceros**: muchos servicios de correo electrónico como Outlook.com, Yahoo y AOL proporcionan un bucle de comentarios en el que, si algún usuario de su servicio marca un correo electrónico de Microsoft 365 como correo no deseado, el mensaje se empaqueta y nos envía para su revisión. Para obtener más información sobre la compatibilidad del remitente con Outlook.com, vaya a <https://sendersupport.olc.protection.outlook.com/pm/services.aspx>.

## <a name="how-eop-controls-outbound-spam"></a>Cómo controla EOP el correo no deseado saliente

- **Segregación del tráfico de correo electrónico saliente**: cada mensaje saliente que se envía a través del servicio se examina en busca de correo no deseado. Si se determina que el mensaje es correo no deseado, se entrega desde un grupo de direcciones IP secundario y menos confiable denominado grupo _de entregas de alto riesgo_. Para más información, consulte [Grupo de entrega de alto riesgo para mensajes salientes](high-risk-delivery-pool-for-outbound-messages.md).

- **Supervisión de la reputación de la dirección IP de origen**: Microsoft 365 consulta varias listas de bloques IP de terceros. Se genera una alerta si alguna de las direcciones IP que usamos para el correo electrónico saliente aparece en estas listas. Esta supervisión nos permite reaccionar rápidamente cuando el spam ha causado que nuestra reputación se degrade. Cuando se genera una alerta, tenemos documentación interna que describe cómo obtener las direcciones IP quitadas (deslistadas) de las listas de bloques.

- **Deshabilitar las cuentas que envían demasiado correo no deseado**<sup>\*</sup>: aunque segregamos el correo no deseado saliente en el grupo de entrega de alto riesgo, no podemos permitir que una cuenta (a menudo, una cuenta en peligro) envíe correo no deseado indefinidamente. Supervisamos las cuentas que envían correo no deseado y, cuando superan un límite no divulgado, se impide que la cuenta envíe correo electrónico. Hay umbrales diferentes para usuarios individuales y todo el inquilino.

- **Deshabilitación de cuentas que envían demasiado correo electrónico demasiado rápido**<sup>\*</sup>: además de los límites que buscan mensajes marcados como correo no deseado, también hay límites que bloquean las cuentas cuando alcanzan un límite de mensajes salientes global, independientemente del veredicto de filtrado de correo no deseado en los mensajes salientes. Una cuenta en peligro podría enviar correo no deseado de día cero (anteriormente no reconocido) que el filtro de correo no deseado pierde. Dado que puede ser difícil identificar una campaña de envío masivo legítimo frente a una campaña de correo no deseado, estos límites ayudan a minimizar cualquier daño potencial.

<sup>\*</sup> No anunciamos los límites exactos para que los spammers no puedan jugar al sistema, por lo que podemos aumentar o reducir los límites según sea necesario. Los límites son lo suficientemente altos como para evitar que un usuario empresarial promedio los supere y lo suficientemente bajos como para ayudar a contener los daños causados por un spammer.

## <a name="recommendations-for-customers-who-want-to-send-mass-mailings-through-eop"></a>Recomendaciones para los clientes que desean enviar correos electrónicos masivos a través de EOP

Es difícil lograr un equilibrio entre los clientes que desean enviar un gran volumen de correo electrónico frente a la protección del servicio frente a cuentas en peligro y remitentes de correo electrónico masivo con prácticas de adquisición de destinatarios deficientes. El costo de un origen de correo electrónico de Microsoft 365 que llega a una lista de bloqueos IP de terceros es mayor que bloquear a un usuario que envía demasiado correo electrónico.

Como se describe en la [descripción del servicio de Exchange Online](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits), el uso de EOP para enviar correo electrónico en masa no es un uso admitido del servicio y solo se permite en el "mejor esfuerzo". Para los clientes que desean enviar correo electrónico masivo, se recomiendan las siguientes soluciones:

- **Enviar correo electrónico masivo a través de servidores de correo electrónico locales**: los clientes mantienen su propia infraestructura de correo electrónico para envíos masivos.

- **Usar un proveedor de correo electrónico masivo de terceros**: hay varios proveedores de soluciones de correo electrónico masivo de terceros que puede usar para enviar envíos masivos de correo. Estas empresas tienen un interés adquirido en trabajar con los clientes para garantizar buenas prácticas de envío de correo electrónico.

El grupo de trabajo mensajería, móvil y contra el abuso de malware (MAAWG) publica su lista de miembros en <https://www.maawg.org/about/roster>. Varios proveedores de correo electrónico masivos están en la lista y se sabe que son ciudadanos responsables de Internet.
