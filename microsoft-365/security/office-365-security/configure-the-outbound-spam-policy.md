---
title: Configurar la directiva de correo no deseado saliente
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 10/02/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a44764e9-a5d2-4c67-8888-e7fb871c17c7
ms.collection:
- M365-security-compliance
description: El filtrado de correo no deseado saliente siempre está habilitado si utiliza el servicio para enviar correo electrónico saliente, lo que protege a las organizaciones que utilizan el servicio y sus destinatarios.
ms.openlocfilehash: baf6999923a4c4cf346915800b8f97a0d0378f58
ms.sourcegitcommit: 2468bcb01625f97a322459814d81b9faad717859
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2019
ms.locfileid: "39871916"
---
# <a name="configure-the-outbound-spam-policy"></a>Configurar la directiva de correo no deseado saliente

El filtrado de correo no deseado saliente siempre está habilitado si utiliza el servicio para enviar correo electrónico saliente, lo que protege a las organizaciones que utilizan el servicio y sus destinatarios. De forma similar al filtrado de entrada, el filtrado de correo no deseado saliente se compone del filtrado de la conexión y el filtrado de contenido, y permite que algunos controles específicos controlen los mensajes salientes. Tipos de configuración de directiva de filtro de correo no deseado saliente:

- Valor predeterminado: la Directiva de filtro de correo no deseado saliente predeterminada se usa para configurar las opciones de filtro de correo no deseado de toda la empresa. No se puede cambiar el nombre de esta directiva y siempre está activada.

- Personalizado: las directivas de filtro de correo no deseado saliente personalizadas pueden ser específicas y aplicarse a usuarios, grupos o dominios específicos de la organización. Las directivas personalizadas siempre tienen prioridad sobre la predeterminada. Puede cambiar el orden en el que se ejecutan las directivas personalizadas cambiando la prioridad de cada directiva personalizada; sin embargo, solo se aplicará la Directiva de prioridad más alta (es decir, el número más cercano a 0) si el usuario coincide con varias directivas.

> [!NOTE]
> Para obtener más información acerca de [los controles de correo no deseado saliente en Office 365](https://docs.microsoft.com/office365/securitycompliance/outbound-spam-controls). <br><br> Las actualizaciones de la Directiva de correo no deseado saliente se están implementando actualmente, con la actualización esperada completada antes del final del 2019 de octubre. Durante este tiempo, es posible que algunas opciones no estén disponibles.  Para obtener más información, consulte [Office 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap?featureid=54125) 

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?
<a name="sectionSection0"> </a>

Tiempo estimado para finalizar: 5 minutos

Deberá tener permisos asignados para poder llevar a cabo estos procedimientos. Para ver qué permisos necesita, consulte la entrada "Contra el correo electrónico no deseado" en el tema [Permisos de características de Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions).

El siguiente procedimiento también se puede llevar a cabo mediante PowerShell remoto. Use el cmdlet [Get-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-hostedoutboundspamfilterpolicy) para revisar su configuración y [Set-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedoutboundspamfilterpolicy) para editar su configuración de directiva de correo no deseado saliente. Para aprender a usar Windows PowerShell para conectarse a Exchange Online Protection, vea [Conectarse a Exchange Online Protection con PowerShell remoto](https://go.microsoft.com/fwlink/p/?linkid=627290). Para obtener información sobre cómo usar Windows PowerShell para conectarse a Exchange Online, vea [Conexión a Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).

## <a name="use-the-security-and-compliance-center-scc-to-edit-the-default-outbound-spam-policy"></a>Usar el centro de seguridad y cumplimiento (SCC) para editar la Directiva de correo no deseado saliente predeterminada

Utilice el siguiente procedimiento para editar la directiva predeterminada del correo no deseado saliente:

### <a name="to-configure-the-default-outbound-spam-policy"></a>Para configurar la directiva de correo no deseado saliente predeterminada

1. En el SCC, desplácese hasta la **Directiva** \> de **Administración** \> de amenazas **contra correo no deseado**

2. Expanda la sección **Directiva de filtro de correo no deseado saliente (Always On)** y haga clic en **Editar Directiva**.

3. Expanda la sección **notificaciones** y active las siguientes casillas de verificación relativas a los mensajes salientes y, después, seleccione **Agregar personas** para agregar una o varias direcciones de correo electrónico asociadas en el cuadro de diálogo correspondiente. (pueden ser listas de distribución si se resuelven como destinos SMTP válidos):

   - **Envíe una copia de todos los mensajes de correo electrónico saliente sospechosos a las siguientes direcciones o direcciones de correo electrónico**: se trata de mensajes marcados como correo no deseado por el filtro (independientemente de la clasificación SCL). El filtro no los rechaza y son enviados al grupo de envío de mayor riesgo. Separar varias direcciones con un punto y coma. Tenga en cuenta que los destinatarios especificados recibirán los mensajes como una dirección con copia oculta (CCC) (los campos De y Para son el remitente y el destinatario originales).

   - **Enviar una notificación a la siguiente dirección de correo electrónico cuando un remitente haya bloqueado el envío de correo no deseado saliente**: Separe varias direcciones con un punto y coma.

   Cuando se detecta una cantidad importante de anomalías u otras anomalías de envío de un usuario en particular, el usuario tiene restringido el envío de mensajes de correo electrónico y se envía una notificación a las direcciones de correo electrónico especificadas.

   Al administrador del dominio, que se especifica con esta opción de configuración, se le informa de que se han bloqueado los mensajes salientes de este usuario.  Para ver el aspecto que tiene esta notificación, véase [Notificación de muestra cuando se bloquea a un remitente para enviar correo no deseado de salida](sample-notification-when-a-sender-is-blocked-sending-outbound-spam.md).

   [Nota] También se genera una alerta del sistema que indica que el usuario se ha restringido.  Para obtener más información sobre la alerta y cómo recuperar el usuario, vea [quitar un usuario del portal de usuarios restringidos después de enviar correo no deseado](removing-user-from-restricted-users-portal-after-spam.md).

4. Expanda la sección **límites de destinatarios** para especificar el número máximo de destinatarios a los que puede enviar un usuario, por hora, para los destinatarios internos y externos, junto con el número máximo por día.

    [Nota] El número máximo para cualquier entrada es 10.000.  Para obtener más información [, consulte límites de recepción y envío en Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#receiving-and-sending-limits) .

7. Especifica la **acción** que se llevará a cabo cuando un usuario supere los límites especificados.  Las acciones posibles son las siguientes:
    * **Restringir al usuario el envío de correo hasta el siguiente día**.  Una vez que se ha superado el límite de envío (interno, externo o diario), se generará una alerta para el administrador y el usuario no podrá enviar más mensajes de correo electrónico hasta el día siguiente, en función de la hora UTC. El administrador no tiene forma de anular este bloque.

    * **Restringir al usuario el envío de correo**.  Una vez que se ha superado el límite de envío (interno, externo o diario), se generará una alerta para el administrador y el usuario no podrá enviar más correo electrónico hasta que el administrador elimine la restricción.  En estos casos, el usuario aparece en la [Página usuarios restringidos](removing-user-from-restricted-users-portal-after-spam.md).  Una vez que se eliminó de la lista, el usuario no volverá a estar restringido para ese día.

    * **No se realiza ninguna acción o alerta**. Una vez que se haya superado el límite de envío (interno, externo o diario), se generará una alerta para el administrador, pero no se llevará a cabo ninguna acción para restringir el usuario.

6. Expanda la sección **se aplica a** y, a continuación, cree una regla basada en condiciones para especificar los usuarios, los grupos y los dominios a los que se aplicará esta Directiva. Puede crear varias condiciones siempre que sean únicas.  Nota: los usuarios deben cumplir todas las condiciones cuando se especifican varias condiciones.  

      * Para seleccionar usuarios, seleccione **el remitente**. En el cuadro de diálogo posterior, seleccione uno o más remitentes de la empresa en la lista del selector de usuarios y luego haga clic en Agregar. Para agregar remitentes que no están en la lista, escriba sus direcciones de correo electrónico y haga clic en Comprobar nombres. Cuando termine de seleccionar, haga clic en aceptar para volver a la pantalla principal.

      * Para seleccionar grupos, seleccione **el remitente es un miembro de**. Después, en el cuadro de diálogo posterior, seleccione o especifique los grupos. Haga clic en Aceptar para volver a la pantalla principal.

      * Para seleccionar dominios, seleccione **el dominio del remitente**. Después agregue los dominios en el cuadro de diálogo posterior. Haga clic en Aceptar para volver a la pantalla principal.

        Puede crear excepciones para la regla. Por ejemplo, puede filtrar mensajes de todos los dominios excepto de uno en concreto. Haga clic en agregar excepción y cree sus condiciones de excepción de forma parecida a como creó las otras condiciones.

        La aplicación de una directiva de correo no deseado saliente a un grupo solo se admite para los grupos de seguridad habilitados para correo.

7. Haga clic en **Guardar**.

## <a name="to-create-a-custom-policy-for-a-specific-set-of-users"></a>Para crear una directiva personalizada para un conjunto específico de usuarios
1. En el SCC, desplácese hasta la **Directiva** \> de **Administración** \> de amenazas **contra correo no deseado**

2. Haga clic en el botón **crear una directiva de salida** .

3. Expanda la sección **notificaciones** y active las siguientes casillas de verificación relativas a los mensajes salientes y, después, seleccione **Agregar personas** para agregar una o varias direcciones de correo electrónico asociadas en el cuadro de diálogo correspondiente.

4. Expanda la sección **límites de destinatarios** para especificar el número máximo de destinatarios que puede enviar un usuario, por hora, para destinatarios internos y externos, y el número máximo de días por día.

7. Especifica la **acción** que se llevará a cabo cuando un usuario supere los límites especificados.

6. Expanda la sección **se aplica a** y cree una regla basada en condiciones para especificar los usuarios, grupos y dominios a los que se va a aplicar esta Directiva. Puede crear varias condiciones siempre que sean únicas.  

8. Haga clic en **Guardar**

## <a name="for-more-information"></a>Más información

[Quitar un usuario desde el Portal de usuarios restringidos después de enviar correo no deseado](https://docs.microsoft.com/office365/SecurityCompliance/removing-user-from-restricted-users-portal-after-spam)

[Grupo de entrega de alto riesgo para mensajes salientes](high-risk-delivery-pool-for-outbound-messages.md)

[Preguntas más frecuentes sobre la protección contra correo electrónico no deseado](anti-spam-protection-faq.md)
