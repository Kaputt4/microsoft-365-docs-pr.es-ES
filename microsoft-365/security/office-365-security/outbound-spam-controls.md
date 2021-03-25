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
description: Los administradores pueden obtener información sobre los controles de correo no deseado salientes en Exchange Online Protection (EOP) y qué hacer si necesita enviar correos masivos.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6e84cd636abee42a03ff8590091542c96714f2d8
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205450"
---
# <a name="outbound-spam-protection-in-eop"></a>Protección contra correo no deseado saliente en EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

En las organizaciones de Microsoft 365 con buzones en Exchange Online o en organizaciones independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online, nos tomamos en serio la administración de correo no deseado saliente. Un cliente que envía correo no deseado de forma intencionada o involuntarla desde su organización puede degradar la reputación de todo el servicio y puede afectar a la entrega de correo electrónico para otros clientes.

En este tema se describen los controles y notificaciones diseñados para ayudar a evitar el correo no deseado saliente y lo que puede hacer si necesita enviar correos masivos.

## <a name="what-admins-can-do-to-control-outbound-spam"></a>Qué pueden hacer los administradores para controlar el correo no deseado saliente

- Usar notificaciones **integradas:** cuando un usuario supera los [](configure-the-outbound-spam-policy.md) límites de envío de las directivas de  correo no deseado saliente o de servicio y se le restringe el envío de correo electrónico, la directiva de alerta predeterminada denominada Usuario restringido para enviar correo electrónico envía notificaciones por correo electrónico a los miembros del grupo [](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) **TenantAdmins** (**Administradores globales**). Para configurar quién más recibe estas notificaciones, consulte [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users). Además, se superaron las directivas de  alerta predeterminadas denominadas **Límite** de envío de correo electrónico y los patrones de envío de correo electrónico sospechoso detectados envían notificaciones de correo electrónico a los miembros del grupo **TenantAdmins** (**Administradores** globales ). Para obtener más información sobre las directivas de alerta, consulte [Directivas de alerta en el centro de seguridad y cumplimiento](../../compliance/alert-policies.md).

- Revisar las **quejas** de correo no deseado de proveedores de correo electrónico de terceros: muchos servicios de correo electrónico como Outlook.com, Yahoo y AOL proporcionan un bucle de comentarios en el que si algún usuario de su servicio marca un correo electrónico de Microsoft 365 como correo no deseado, el mensaje se empaqueta y se envía de vuelta a nosotros para su revisión. Para obtener más información sobre la compatibilidad de remitentes Outlook.com, vaya a <https://sendersupport.olc.protection.outlook.com/pm/services.aspx> .

## <a name="how-eop-controls-outbound-spam"></a>Cómo EOP controla el correo no deseado saliente

- **Segregación del tráfico de correo** electrónico saliente: cada mensaje saliente que se envía a través del servicio se examina en busca de correo no deseado. Si se determina que el mensaje es correo no deseado, se entrega desde un grupo de direcciones IP secundario y menos confiable denominado grupo de entrega de alto _riesgo._ Para más información, consulte [Grupo de entrega de alto riesgo para mensajes salientes](high-risk-delivery-pool-for-outbound-messages.md).

- **Supervisión de la reputación de nuestra dirección IP de origen:** Microsoft 365 consulta varias listas de direcciones IP de terceros. Se genera una alerta si alguna de las direcciones IP que usamos para el correo electrónico saliente aparece en estas listas. Esto nos permite reaccionar rápidamente cuando el correo no deseado ha hecho que nuestra reputación se degrade. Cuando se genera una alerta, tenemos documentación interna que describe cómo quitar (deslistar) nuestras direcciones IP de listas de bloqueo.

- **Deshabilitar cuentas** que envían demasiado correo no deseado: aunque segregamos correo no deseado saliente en el grupo de entrega de alto riesgo, no podemos permitir que una cuenta (a menudo, una cuenta comprometida) envíe correo no deseado de forma <sup>\*</sup> indefinida. Supervisamos las cuentas que envían correo no deseado y, cuando superan un límite no divulgado, la cuenta se bloquea para que no envíe correo electrónico. Hay diferentes umbrales para usuarios individuales y todo el espacio empresarial.

- **Deshabilitar** cuentas que envían demasiado correo electrónico demasiado rápido: además de los límites que buscan mensajes marcados como correo no deseado, también hay límites que bloquean las cuentas cuando alcanzan un límite global de mensajes salientes, independientemente del veredicto de filtrado de correo no deseado de los mensajes <sup>\*</sup> salientes. Una cuenta comprometida podría enviar correo no deseado de día cero (no reconocido previamente) que no se encuentra en el filtro de correo no deseado. Dado que puede ser difícil identificar una campaña de correo masivo legítima frente a una campaña de correo no deseado, estos límites ayudan a minimizar los posibles daños.

<sup>\*</sup> No anunciamos los límites exactos para que los spammers no puedan jugar al sistema, por lo que podemos aumentar o disminuir los límites según sea necesario. Los límites son lo suficientemente altos como para evitar que un usuario empresarial promedio los supere y lo suficientemente bajos como para ayudar a contener los daños causados por un spammer.

## <a name="recommendations-for-customers-who-want-to-send-mass-mailings-through-eop"></a>Recomendaciones para clientes que desean enviar correos masivos a través de EOP

Es difícil encontrar un equilibrio entre los clientes que desean enviar un gran volumen de correo electrónico frente a proteger el servicio de cuentas comprometidas y remitentes de correo electrónico masivo con prácticas de adquisición de destinatarios deficientes. El costo de un origen de correo electrónico de Microsoft 365 que se desembarque en una lista de direcciones IP de terceros es mayor que bloquear a un usuario que envía demasiado correo electrónico.

Como se describe en la Descripción del servicio [de Exchange Online](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits), el uso de EOP para enviar correo electrónico masivo no es un uso compatible del servicio y solo se permite en el "mejor esfuerzo". Para los clientes que quieran enviar correo electrónico masivo, se recomiendan las siguientes soluciones:

- **Enviar correo masivo a través de servidores** de correo electrónico locales: esto significa que los clientes tendrán que mantener su propia infraestructura de correo electrónico para envíos masivos de correo.

- **Usar un proveedor de correo masivo** de terceros: hay varios proveedores de soluciones de correo masivo de terceros que puede usar para enviar correos masivos. Estas empresas tienen un interés creado en trabajar con clientes para garantizar buenas prácticas de envío de correo electrónico.

El Grupo de trabajo contra el maltrato de mensajería, móvil y malware (MAAWG) publica su lista de miembros en <https://www.maawg.org/about/roster> . Varios proveedores de correo electrónico masivo están en la lista y se sabe que son ciudadanos de Internet responsables.