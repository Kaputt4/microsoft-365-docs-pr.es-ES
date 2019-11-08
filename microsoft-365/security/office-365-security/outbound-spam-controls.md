---
title: Controlar el correo no deseado saliente en Office 365
ms.author: tracyp
author: MSFTTracyP
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
description: Si su organización envía una gran cantidad de correo masivo marcado como correo no deseado, puede bloquear el envío de correo electrónico con Office 365. Lea este artículo para obtener más información sobre por qué ocurre esto y lo que puede hacer al respecto.
ms.openlocfilehash: 28677e2bbfad7f44595de1300e42b9c58ab99c2b
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2019
ms.locfileid: "38031855"
---
# <a name="control-outbound-spam-in-office-365"></a>Controlar el correo no deseado saliente en Office 365

Tenemos que administrar el correo no deseado de salida en serio porque nuestro es un servicio compartido.  Hay muchos clientes detrás de un grupo compartido de recursos, donde si un cliente envía correo no deseado saliente, puede degradar la reputación IP saliente del servicio y afecta a la entrega correcta del correo electrónico para otros clientes.

> [!IMPORTANT]
> La notificación para cuando un remitente está restringido ahora forma parte de la plataforma de alertas del centro de cumplimiento de & de seguridad (SCC). En lugar de usar los métodos descritos a continuación para enviar notificaciones, la lista de usuarios a los que se les avisa puede encontrarse en el **usuario restringido al envío de una alerta de correo electrónico** . Empiece a usar la [Página directivas de alerta](https://sip.protection.office.com/alertpolicies) en el centro de seguridad & cumplimiento para configurar la alerta, ya que el método anterior se quitará en el futuro. Obtenga información sobre el nuevo [quitar un usuario del portal de usuarios restringidos después de enviar correo no deseado](removing-user-from-restricted-users-portal-after-spam.md). "

## <a name="what-admins-can-do-to-control-outbound-spam"></a>Qué pueden hacer los administradores para controlar el correo no deseado saliente

- **Habilitar las notificaciones cuando una cuenta envía correo no deseado o se cierra**: los administradores pueden obtener CCO siempre que un mensaje se marca como correo no deseado saliente y se envía a través del grupo de riesgo alto. Mediante la supervisión de este buzón, un administrador puede detectar si tiene una cuenta en peligro en su red o si el filtro de correo no deseado marca de forma errónea su correo electrónico como correo no deseado. [Aquí](configure-the-outbound-spam-policy.md)puede encontrar más información sobre cómo configurar la Directiva de correo no deseado saliente.

- **Revise manualmente las reclamaciones de correo no deseado de proveedores de correo electrónico de**terceros: muchos servicios de correo electrónico de terceros como Outlook.com, Yahoo y AOL proporcionan un bucle de comentarios en el que si algún usuario del servicio marca un correo electrónico de nuestro servicio como correo no deseado, el mensaje se empaqueta y se envía a nosotros para que lo revisen. Para obtener más información acerca de la compatibilidad de remitentes para Outlook.com, haga clic [aquí](https://sendersupport.olc.protection.outlook.com/pm/services.aspx).

## <a name="what-eop-does-to-control-outbound-spam"></a>Qué hace EOP para controlar el correo no deseado saliente

1. **Segregación de tráfico saliente en grupos de direcciones IP independientes**: todos los mensajes que los clientes envían a través del servicio se examinan en busca de correo no deseado. Si el mensaje es correo no deseado, se enruta a través del grupo de entrega de alto riesgo. Este grupo de direcciones IP contiene notificaciones de estado no entregadas y correo no deseado. No se garantiza la entrega al destinatario previsto, ya que muchas terceras partes no aceptarán correo electrónico porque la calidad del correo electrónico que emite.

   Al dividir el tráfico de este modo, se garantiza que el correo electrónico de menor calidad (correo no deseado, NDR de reenvío masivo) no se arrastra hacia abajo la reputación de los grupos de correo electrónico salientes normales. El grupo de alto riesgo suele tener una reputación baja en muchos receptores por Internet, aunque no es universal.

2. **Supervisión de la reputación de IP**: Office 365 consulta varios blocklists IP de terceros y genera alertas si alguna de nuestras IP de salida se enumeran en ellas. Esto nos permite reaccionar rápidamente cuando el correo no deseado ha provocado una degradación de nuestra reputación. Cuando se genera una alerta, tenemos documentación interna que no depende de los pasos que se deben tomar para devolverse a la lista.

3. La **deshabilitación de cuentas infractoras cuando envían demasiado correo electrónico como correo no deseado**: aunque se segrega el correo no deseado y no spam en dos grupos de servidores IP salientes independientes, las cuentas de correo electrónico no pueden enviar correo no deseado de manera indefinida. Supervisamos qué cuentas envían correo no deseado y, si supera un límite no divulgado, se bloquea la cuenta para enviar correo no deseado.

   Un solo mensaje marcado como correo no deseado puede ser un error de clasificación por el motor de correo no deseado y también conocido como falso positivo. Lo enviamos a través del grupo de alto riesgo para darle la oportunidad de salir; sin embargo, un gran número de mensajes en un breve período de tiempo es indicativo de un problema y, cuando esto ocurre, se impide que la cuenta envíe más correo electrónico. Existen distintos umbrales para las cuentas de correo electrónico individuales y para todo el espacio empresarial.

4. La **deshabilitación de cuentas infractoras cuando envían demasiado correo electrónico en un período de tiempo demasiado corto**: además de los límites superiores que buscan una proporción de mensajes marcados como correo no deseado, también hay límites que bloquean las cuentas cuando alcanzan un límite general independientemente de si los mensajes se marcan como correo no deseado o no. El motivo por el que se encuentra este límite es que una cuenta en peligro podría enviar correo no deseado de día cero que no está presente por el filtro de correo no deseado. Debido a que es difícil, si no imposible, a veces distinguir la diferencia entre una campaña de correo masivo legítima y una campaña de correo no deseado masiva, estos límites se activan para limitar los posibles daños.

> [!NOTE]
> Para los #3 y #4, no anunciamos los límites exactos para evitar que los remitentes de correo no deseado puedan jugar con el sistema y asegurarnos de que podemos cambiar los límites que necesitamos. Los límites son lo suficientemente altos como para que un usuario promedio de la empresa nunca los Presione y lo suficientemente bajo como para que contenga la mayoría de los daños que puede hacer un remitente de correo no deseado.

## <a name="recommended-workarounds-for-customers-who-want-to-send-outbound-a-lot-of-email-through-eop"></a>Soluciones recomendadas para los clientes que deseen enviar un gran número de mensajes de correo electrónico a través de EOP

Es difícil alcanzar un equilibrio entre los clientes que quieren enviar un gran volumen de correo electrónico frente a proteger el servicio de cuentas comprometidas y correo electrónico masivo con prácticas de adquisición de listas deficientes. Una vez más, el costo de un aterrizaje saliente de IP en una lista de bloqueo de terceros es superior al bloqueo de un cliente para que no envíe correo electrónico saliente. Como se describe en la [Descripción del servicio de Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits), el uso de EOP para enviar correo electrónico masivo no es un uso compatible del servicio y solo se permite en base a un "mejor esfuerzo". Para los clientes que quieren enviar correo masivo, recomendamos lo siguiente:

1. **Enviar el correo electrónico masivo a través de sus propios servidores de correo locales**: Esto significa que el cliente tendrá que mantener su propia infraestructura de correo electrónico para este tipo de correo electrónico.

2. **Usar un correo electrónico masivo de terceros para enviar la comunicación masiva**: hay varios correos electrónicos masivos de terceros cuyo único negocio es enviar correo electrónico masivo. Pueden trabajar con los clientes para asegurarse de que tienen buenas prácticas de correo electrónico y tienen recursos dedicados a su aplicación.

El grupo de trabajo de mensajería, móviles y contra el abuso de malware (MAAWG) publica [aquí](https://www.maawg.org/about/roster)su lista de pertenencia. Hay varios proveedores de correo electrónico masivo en la lista que se conocen como ciudadanos de Internet responsables.

## <a name="for-more-information"></a>Más información

[Notificación de muestra cuando se bloquea a un remitente para enviar correo no deseado de salida](sample-notification-when-a-sender-is-blocked-sending-outbound-spam.md)

[Protección contra correo no deseado de Office 365](anti-spam-protection.md)

[Protección contra suplantación de identidad en Office 365](anti-spoofing-protection.md)

[Niveles de confianza del correo no deseado](spam-confidence-levels.md)
