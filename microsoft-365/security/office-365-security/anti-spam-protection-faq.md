---
title: Preguntas más frecuentes sobre protección contra correo electrónico no deseado
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c534a35d-b121-45da-9d0a-ce738ce51fce
ms.collection:
- M365-security-compliance
description: Preguntas más frecuentes y respuestas para administradores acerca de la protección contra correo no deseado en Exchange Online y Exchange Online Protection (EOP) independiente.
ms.openlocfilehash: 30ab9ceb7d2e9e4a264311ff43343485a57d622c
ms.sourcegitcommit: 9ed3283dd6dd959faeca5c22613f9126261b9590
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2020
ms.locfileid: "43528318"
---
# <a name="anti-spam-protection-faq-in-office-365"></a>Preguntas más frecuentes sobre protección contra correo no deseado en Office 365

En este tema se proporcionan preguntas frecuentes y respuestas sobre la protección contra correo no deseado para Office 365 los clientes con buzones en Exchange online o los clientes independientes de Exchange Online Protection (EOP) sin buzones de Exchange Online.

Para ver las preguntas y sus correspondientes respuestas sobre la cuarentena, consulte [Preguntas más frecuentes sobre la cuarentena](quarantine-faq.md).

Para preguntas y respuestas sobre la protección antimalware, consulte [preguntas más frecuentes sobre la protección contra malware](anti-malware-protection-faq-eop.md).

Para obtener preguntas y respuestas sobre la protección contra la suplantación de identidad, vea [preguntas más frecuentes sobre protección contra la suplantación de identidad](anti-spoofing-protection-faq.md).

## <a name="q-by-default-what-happens-to-a-spam-detected-message"></a>T. De forma predeterminada, ¿qué ocurre con los mensajes detectados como correo no deseado?

A. **Para los mensajes entrantes**: la mayoría del correo no deseado se elimina mediante el filtrado de la conexión, que se basa en la dirección IP del servidor de correo electrónico de origen. Las directivas contra correo no deseado (también conocidas como directivas de filtro de correo no deseado o directivas de filtro de contenido) inspeccionan y clasifican mensajes como correo no deseado, masivo o de suplantación de identidad. De forma predeterminada, los mensajes clasificados como correo no deseado o masivo se entregan en la carpeta de correo no deseado del destinatario, mientras que los mensajes clasificados como suplantación de identidad se ponen en cuarentena. Puede modificar la Directiva contra correo no deseado predeterminada (se aplica a todos los destinatarios) o puede crear directivas contra correo no deseado personalizadas con una configuración más estricta para grupos de usuarios específicos (por ejemplo, puede poner en cuarentena el correo no deseado que se envía a los ejecutivos). Para obtener más información, vea [configurar directivas contra correo no deseado en Office 365](configure-your-spam-filter-policies.md) y [configuración recomendada para la Directiva contra correo no deseado](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings).

> [!IMPORTANT]
> En las implementaciones híbridas donde EOP protege los buzones locales, debe configurar dos reglas de flujo de correo de Exchange (también conocidas como reglas de transporte) en su organización de Exchange local para detectar los encabezados de filtrado de correo no deseado de EOP que se agregan a los mensajes. Para obtener información, consulte [Configuración de un EOP independiente para entregar el correo no deseado en la carpeta de correo no deseado en entornos híbridos](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).

 **Para los mensajes salientes**: el mensaje se enruta a través del [grupo de entrega de alto riesgo](high-risk-delivery-pool-for-outbound-messages.md) o se devuelve al remitente en un informe de no entrega (también conocido como mensaje NDR o de devolución). Para obtener más información acerca de la protección de correo no deseado saliente, vea [controles de correo no deseado salientes en Office 365](outbound-spam-controls.md).

## <a name="q-whats-a-zero-day-spam-variant-and-how-is-it-handled-by-the-service"></a>T. ¿Qué es una variante de cero días de correo no deseado y cómo se encarga el servicio?

A. Una variante de día cero de correo no deseado es una primera generación, una variante desconocida del correo no deseado que nunca se ha capturado o analizado, por lo que nuestros filtros contra correo electrónico no deseado todavía no tienen información disponible para su detección. Una vez que nuestros analistas de correo no deseado capturan y analizan un ejemplo de correo no deseado de día cero, si cumplen los criterios de clasificación de correo no deseado, se actualizan los filtros contra correo no deseado para detectarlo y ya no se considera "día cero".

**Nota:** Si recibe un mensaje que puede ser una variante de cero días de correo no deseado, para ayudarnos a mejorar el servicio, envíe el mensaje a Microsoft mediante uno de los métodos descritos en [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="q-do-i-need-to-configure-the-service-to-provide-anti-spam-protection"></a>T. ¿Es necesario configurar el servicio para proporcionar protección contra correo no deseado?

A. Después de registrarse en el servicio y agregar su dominio, el filtrado de correo no deseado se habilita automáticamente. De forma predeterminada, el filtrado de correo no deseado está optimizado para protegerle sin necesidad de ninguna configuración adicional (además de la excepción indicada anteriormente para clientes independientes de EOP de EOP en entornos híbridos). Como administrador, puede editar la configuración predeterminada de filtrado de correo no deseado para satisfacer las necesidades de su organización. Para una mayor granularidad, también puede crear directivas contra correo no deseado y directivas de correo no deseado salientes que se aplican a usuarios, grupos o dominios específicos de la organización. Las directivas personalizadas siempre tienen prioridad con respecto a la directiva predeterminada, pero puede cambiar la prioridad (es decir, el orden de ejecución) de las directivas personalizadas.

Para obtener más información, vea los siguientes temas:

[Configuración recomendada para EOP y la seguridad de ATP de Office 365](recommended-settings-for-eop-and-office365-atp.md)

[Configurar la Directiva de protección](configure-the-connection-filter-policy.md)

[Configuración de directivas contra correo no deseado en Office 365](configure-your-spam-filter-policies.md)

[Configurar la directiva de correo no deseado saliente](configure-the-outbound-spam-policy.md)

## <a name="q-if-i-make-a-change-to-an-anti-spam-policy-how-long-does-it-take-after-i-save-my-changes-for-them-to-take-effect"></a>T. Si realizo cambios en una directiva contra correo no deseado, ¿cuánto tardan en tener efecto después de guardarlos?

A. Los cambios pueden tardar hasta una hora en surtir efecto.

## <a name="q-is-bulk-email-filtering-automatically-enabled"></a>T. ¿Se habilita automáticamente el filtrado masivo de correo electrónico?

R. Sí. Para obtener más información sobre el correo masivo, vea [¿cuál es la diferencia entre correo electrónico no deseado y correo electrónico masivo?](what-s-the-difference-between-junk-email-and-bulk-email.md).

## <a name="q-does-the-service-provide-url-filtering"></a>T. ¿El servicio proporciona filtrado de direcciones URL?

A. Sí, el servicio tiene un filtro de URL que comprueba si hay direcciones URL en los mensajes. Si se detectan direcciones URL asociadas a correo no deseado o a contenido malintencionado conocido, el mensaje se marcará como correo no deseado.

## <a name="q-how-can-customers-using-the-service-send-false-negative-spam-and-false-positive-non-spam-messages-to-microsoft"></a>T. ¿Cómo pueden los clientes usar el servicio enviar mensajes falsos negativos (correo no deseado) y falsos positivos (correo seguro) a Microsoft?

P. Los mensajes de correo no deseado y los mensajes seguros se pueden enviar a Microsoft para su análisis de varias maneras. Para obtener más información, vea [informar de mensajes y archivos a Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="q-can-i-get-spam-reports"></a>T. ¿Puedo obtener informes de correo no deseado?

A. Sí, por ejemplo, puede obtener un informe de detección de correo no deseado en el centro de administración de Microsoft 365. Este informe muestra el volumen de correo no deseado como un recuento de mensajes únicos. Para obtener más información sobre los informes, consulte los siguientes vínculos:

Clientes de Exchange Online: [supervisión, informes y seguimiento de mensajes en Exchange Online](https://docs.microsoft.com/exchange/monitoring/monitoring)

Clientes de EOP independientes: [informes y seguimiento de mensajes en Exchange Online Protection](reporting-and-message-trace-in-exchange-online-protection.md)

## <a name="q-someone-sent-me-a-message-and-i-cant-find-it-i-suspect-that-it-may-have-been-detected-as-spam-is-there-a-tool-that-i-can-use-to-find-out"></a>T. Alguien me ha enviado un mensaje y no lo encuentro. Sospecho que es posible que se haya detectado como correo no deseado. ¿Hay alguna herramienta que pueda usar para averiguarlo?

R: Sí, la herramienta de seguimiento de mensajes le permite realizar un seguimiento de los mensajes de correo electrónico a medida que pasan por el servicio a fin de averiguar qué sucedió con ellos. Consulte Was a message marked as spam?  Para obtener más información acerca de cómo usar la herramienta de seguimiento de mensajes para averiguar por qué un mensaje se marcó como correo no deseado, consulte ¿ [se marcó un mensaje como correo no deseado?](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/message-trace-faq#was-a-message-marked-as-spam)

## <a name="q-will-the-service-throttle-rate-limit-my-mail-if-my-users-send-outbound-spam"></a>T. ¿La limitación de servicio (límite de velocidad) mi correo si los usuarios envían correo no deseado salientes?

A. Si Office 365 determina que más de la mitad del correo que se envía de un usuario a través del servicio en un período de tiempo determinado (por ejemplo, por hora) es correo no deseado, se bloqueará el usuario y no podrá enviar mensajes. En la mayoría de los casos, si se determina que un mensaje saliente es correo no deseado, se redirige a través del grupo de entrega de alto riesgo, lo cual reduce la probabilidad de que el grupo de IP saliente normal se agregue a una lista de bloqueados.

Puede enviar una notificación a la dirección de correo electrónico especificada cuando se bloquee un remitente por enviar correo electrónico no deseado. Para más información sobre esta configuración, consulte [Configurar la directiva de correo no deseado saliente](configure-the-outbound-spam-policy.md).

## <a name="q-can-i-use-a-third-party-anti-spam-and-anti-malware-provider-in-conjunction-with-exchange-online"></a>T. ¿Puedo usar un proveedor contra correo no deseado y contra malware de terceros junto con Exchange Online?

R. Sí. Aunque le recomendamos que apunte su registro MX a Office 365, sabemos que hay razones empresariales legítimas para redirigir el correo electrónico a otro lugar que no sea Office 365 en primer lugar.

- **Entrante**: cambie los registros MX para que apunten al proveedor de terceros y, a continuación, redirija los mensajes a EOP para un procesamiento adicional. Para obtener más información, vea [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).

- **Saliente**: configurar el enrutamiento de host inteligente desde Office 365 al proveedor de terceros de destino.

## <a name="q-does-microsoft-have-any-documentation-about-how-i-can-protect-myself-from-phishing-scams"></a>T. ¿Tiene Microsoft alguna documentación sobre cómo puedo protegerme de las estafas de suplantación de identidad?

R. Sí. Para obtener más información, consulte [proteger la privacidad en Internet](https://support.microsoft.com/help/4091455) .

## <a name="q-are-spam-and-malware-messages-being-investigated-as-to-who-sent-them-or-being-transferred-to-law-enforcement-entities"></a>T. ¿Se investigan los mensajes de malware o correo no deseado en cuanto a quién los envió o se transfieren a las autoridades judiciales?

R. El servicio se enfoca en la detección y eliminación de malware y correo no deseado, aunque de vez en cuando podemos investigar campañas de ataques o correo no deseado particularmente peligroso, y perseguir a sus autores. Esto puede implicar trabajar con nuestras unidades especializadas en crimen digital y legal para desmantelar la botnet de un spammer, impidiendo que el spammer use el servicio (si lo está usando para enviar correo electrónico saliente) y transmitiendo la información a las autoridades judiciales para que lleven a cabo una acusación penal.

## <a name="q-what-are-a-set-of-best-outbound-mailing-practices-that-will-ensure-that-my-mail-is-delivered"></a>T. ¿Qué conjunto de procedimientos recomendados para el correo saliente garantizará la entrega de mi correo?

A. Las pautas presentadas a continuación son los procedimientos recomendados para el envío de mensajes de correo electrónico salientes.

- **El dominio de correo electrónico de origen debe resolverse en DNS.**

  Por ejemplo, si el remitente es user@fabrikam, el dominio Fabrikam se resuelve en la dirección IP 192.0.43.10.
  
  Si un dominio de envío no tiene registro A ni registro MX en DNS, el servicio enrutará el mensaje a través de su grupo de entrega de mayor riesgo, independientemente de si el contenido del mensaje es correo no deseado o no. Para obtener más información acerca del grupo de entrega de mayor riesgo, consulte [grupo de entrega de alto riesgo para los mensajes salientes](high-risk-delivery-pool-for-outbound-messages.md).

- **El correo saliente eServer debe tener una entrada DNS (PTR) inversa.**

  Por ejemplo, si la dirección IP de origen del correo electrónico es 192.0.43.10, la entrada DNS `43-10.any.icann.org`inversa sería ".

- **Los comandos HELO/EHLO y MAIL FROM deben ser coherentes y estar presentes en la forma de un nombre de dominio, en vez de una dirección IP.**

  El comando HELO/EHLO debe configurarse para coincidir con el DNS inverso de la dirección IP de envío, de modo que el dominio continúe siendo el mismo en varias partes de los encabezados del mensaje.

- **Asegúrese de que los registros de SPF apropiados estén configurados en DNS.**

  Los registros de SPF son un mecanismo para validar que el correo enviado desde un dominio realmente proviene de ese domino y no es una suplantación. Para obtener más información acerca de los registros de SPF, consulte los siguientes vínculos:

  [Configurar SPF en Office 365 para ayudar a evitar la suplantación de identidad](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

  [Preguntas más frecuentes de dominios](https://docs.microsoft.com/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain)

- **Firma de correo electrónico con DKIM, firma con la resolución de nombres canónicos relajada.**

  Si un remitente desea firmar sus mensajes con un Correo identificado con claves de dominio (DKIM) y desea enviar correo saliente mediante el servicio, para firmar debe utilizar el algoritmo de resolución de nombres canónicos relajada del encabezado. Firmar con una resolución de nombres canónicos del encabezado estricta puede invalidar la firma cuando pase por el servicio.

- **Los propietarios de dominio deben disponer de información precisa en la base de datos WHOIS.**

  Esto identifica a los propietarios del dominio y la forma de ponerse en contacto con ellos mediante la especificación de una empresa principal estable, un punto de contacto y servidores de nombre.

- **Para el envío masivo de correo, el nombre De: debe reflejar quién envía el mensaje, mientras que la línea de asunto del mensaje debe ser un resumen del tema del mensaje.**

  El cuerpo del mensaje debe tener un indicación clara de la oferta, el servicio o el producto. Por ejemplo, si el remitente envía correo masivamente para la empresa Contoso, los campos De y Asunto del correo electrónico deberían ser parecidos a lo siguiente:

  > De: marketing@contoso.com <br/> Asunto: ¡Nuevo catálogo actualizado para la temporada de Navidad!

  A continuación, se muestra un ejemplo de qué no se debe hacer porque no es descriptivo:

  > De: user@hotmail.com <br/> Asunto: Catálogos

- **Si se envía correo masivo a muchos destinatarios y el mensaje tiene formato de boletín, debe haber una manera de cancelar la suscripción en la parte inferior del mensaje.**

  La opción de cancelar la suscripción debe parecerse a:

  > sender@fabrikam.com envió este mensaje a example@contoso.com. Actualizar perfil/dirección de correo electrónico | Eliminación instantánea con **SafeUnsubscribe** &trade; | Directiva de privacidad

- **Si envía correo masivamente, la adquisición de listas debe realizarse con una suscripción doble. Si envía correo masivamente, la suscripción doble es un procedimiento recomendado.**

  La suscripción doble es una práctica consistente en solicitar a un usuario que realice dos acciones para suscribirse a un correo de marketing:

  1. Una vez, cuando el usuario hace clic en una casilla sin activar previamente para elegir recibir más ofertas o mensajes de correo electrónico del especialista en marketing.

  2. La segunda, cuando el especialista en marketing envíe un correo electrónico de confirmación a la dirección de correo proporcionada por el usuario donde le solicite que haga clic en un vínculo sujeto a limitación temporal que completará al confirmación.

  El uso de la suscripción doble construye una buena reputación para las personas que envían correo electrónico masivo.

- **Las personas que envían correo electrónico masivo deben crear contenido transparente del cual puedan hacerse responsables:**

  1. El vocabulario que requiera que los destinatarios agreguen a los remitentes a la libreta de direcciones debe especificar claramente que dicha acción no es una garantía de entrega.

  2. Cuando el cuerpo del mensaje incluya contenido que redirija, utilice un estilo coherente para los vínculos.

  3. No envíe imágenes o datos adjuntos pesados o mensajes que estén únicamente compuestos por una imagen.

  4. Cuando utilice píxeles de seguimiento (errores o señalizaciones web), especifique claramente su presencia en su directiva de privacidad o configuración de P3P.

- **Dar formato a los mensajes de devolución de salida.**

  Al generar mensajes de notificación de estado de entrega (también conocidos como informes de no entrega, NDR o mensajes de devolución), los remitentes deben seguir el formato de un rebote, como se especifica en [RFC 3464](https://www.ietf.org/rfc/rfc3464.txt).

- **Elimine las direcciones de correo electrónico rebotadas de los usuarios inexistentes.**

  Si recibe un informe de no entrega que le indica que una dirección de correo electrónico ya no se utiliza, elimine el alias de correo no existente de su lista. Las direcciones de correo electrónico cambian con el tiempo, y la gente a veces deja de utilizarlas.

- **Utilice el programa de Servicios de datos de red inteligente (SNDS) de Hotmail.**

  Hotmail utiliza un programa denominado Servicios de datos de red inteligente que permite a los remitentes comprobar los reclamos enviados por los usuarios finales. SNDS es el portal principal para solucionar problemas de entrega a Hotmail.
