---
title: Correo de solución de problemas enviado a Microsoft 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: f4caa4e1-e414-4b21-8822-31c08064c059
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: En este artículo se proporciona información para solucionar problemas con el envío de correo electrónico a los buzones de correo de Microsoft 365 & procedimientos recomendados para el envío masivo de correo a los clientes de Microsoft 365.
ms.openlocfilehash: 895f2651529cd46968d053fefac10cb22b6a5d86
ms.sourcegitcommit: 7e003ee0a06f61bfb9f80441c3479fa3148afafe
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2020
ms.locfileid: "49568559"
---
# <a name="troubleshooting-mail-sent-to-microsoft-365"></a>Correo de solución de problemas enviado a Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


En este artículo se proporciona información de solución de problemas para los remitentes que experimentan problemas al intentar enviar correo electrónico a las bandejas de correo de Microsoft 365 y los procedimientos recomendados para el envío masivo de correo a los clientes.

## <a name="are-you-managing-your-ip-and-domains-sending-reputation"></a>¿Está administrando la reputación de envío de dominios e IP?

Las tecnologías de filtrado de EOP están diseñadas para proporcionar protección contra correo no deseado para Microsoft 365, además de otros productos de Microsoft como Exchange Server. También aprovechamos SPF, DKIM y DMARC; tecnologías de autenticación de correo electrónico que ayudan a solucionar el problema de la suplantación de identidad y phishing al comprobar que el dominio que envía el correo electrónico está autorizado a hacerlo. El filtrado de EOP se ve influenciado por una serie de factores relacionados con la IP de envío, dominio, autenticación, precisión de lista, tasas de denuncia, contenido, etc. De estos factores, uno de los que más empeora la reputación del remitente y su capacidad para entregar correo electrónico es su tasa de denuncia de correo electrónico no deseado.

## <a name="are-you-sending-email-from-new-ip-addresses"></a>¿Está enviando correo electrónico desde direcciones IP nuevas?

Las direcciones IP que no se hayan usado previamente para enviar correo electrónico por lo general no tienen ninguna reputación en nuestros sistemas. Como resultado, los correos electrónicos de IP nuevas es más probable que experimenten problemas de entrega. Una vez que la dirección IP tiene una reputación en la que no figura el envío de correo electrónico no deseado, EOP suele permitir un mejor proceso de entrega satisfactoria de correo electrónico.

Las IP nuevas que se agregan a dominios que están autenticados en los registros de SPF existentes suelen disfrutar del beneficio añadido de heredar parte de la reputación del remitente del dominio. Si su dominio tiene una buena reputación de envío, las nuevas IP puede que disfruten de un tiempo más rápido de impulso. Normalmente una nueva IP se impulsa completamente en un par de semanas o antes según el volumen, la exactitud de la lista y las tasas de denuncia de correo electrónico no deseado.

## <a name="confirm-that-your-dns-is-set-up-correctly"></a>Confirme que su DNS está configurado correctamente

Para obtener instrucciones acerca de cómo crear y mantener registros DNS, incluido el registro MX necesario para enrutar el correo, debe ponerse en contacto con su proveedor de hospedaje de DNS.

## <a name="ensure-that-you-do-not-advertise-yourself-as-a-non-routable-ip"></a>Asegúrese de que usted no se anuncia como una dirección IP no enrutable

No podemos aceptar correo electrónico de los remitentes que no logran una búsqueda de DNS inverso. En algunos casos, los remitentes legítimos se anuncian incorrectamente como IP no enrutable de Internet cuando se intenta abrir una conexión a EOP. Las direcciones IP reservadas para una red privada (no enrutable) incluyen:

- 192.168.0.0/16 (o 192.168.0.0 - 192.168.255.255)
- 10.0.0.0/8 (o 10.0.0.0 - 10.255.255.255)
- 172.16.0.0/11 (o 172.16.0.0 - 172.31.255.255)

## <a name="you-received-a-non-delivery-report-ndr-when-sending-email-to-a-user-in-office-365"></a>Ha recibido un informe de no entrega (NDR) al enviar un correo electrónico a un usuario en Office 365

Algunos problemas de entrega se deben a que Microsoft ha bloqueado la dirección IP del remitente o a que la cuenta de usuario se identifica como remitente prohibido debido a una actividad precedente de correo no deseado. Si cree que ha recibido el NDR por error, en primer lugar, siga las instrucciones del mensaje de NDR para resolver el problema.

Para obtener más información sobre el error que ha recibido, consulte la lista de códigos de error en [informes de no entrega de correo electrónico en Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online).

 Por ejemplo, si recibe el NDR siguiente, indica que Microsoft ha bloqueado la dirección IP de envío:

 `550 5.7.606-649 Access denied, banned sending IP [x.x.x.x]; To request removal from this list please visit https://sender.office.com/ and follow the directions.`

Para solicitar la eliminación de esta lista, puede [usar el portal de eliminación de la lista para quitarse de la lista de remitentes bloqueados](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).

## <a name="my-email-landed-in-the-recipients-junk-email-folder"></a>Mi correo electrónico descargado en la carpeta de correo no deseado del destinatario

Si EOP identificó incorrectamente un mensaje como correo no deseado, puede hablar con el destinatario para enviar este mensaje falso positivo al equipo de análisis de correo no deseado de Microsoft, que lo evaluará y analizará. Para obtener más información, consulte [Notificar mensajes y archivos a Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="traffic-from-my-ip-address-is-throttled-by-eop"></a>El tráfico de mi dirección IP está limitado por EOP

Si recibe un NDR de EOP que indica que EOP está limitando su dirección IP, por ejemplo:

 `host xxxx.outlook.com [x.x.x.x]: 451 4.7.550 Access denied, please try again later`

Ha recibido el NDR porque se ha detectado actividad sospechosa procedente de la dirección IP en cuestión y se ha restringido temporalmente mientras se analiza el caso en profundidad. Si después del análisis, la dirección deja de ser sospechosa, la restricción se levantará en breve.

## <a name="i-cant-receive-email-from-senders-in-microsoft-365"></a>No puedo recibir correo electrónico de remitentes en Microsoft 365

 Para recibir mensajes de nuestros usuarios, asegúrese de que la red permite conexiones desde las direcciones IP que EOP usa en nuestros centros de datos. Para obtener más información, consulte [Exchange Online Protection IP addresses](https://docs.microsoft.com/microsoft-365/enterprise/urls-and-ip-address-ranges).

## <a name="best-practices-for-bulk-emailing-to-microsoft-365-users"></a>Procedimientos recomendados para el correo electrónico masivo a los usuarios de Microsoft 365

Si suele llevar a cabo campañas de correo electrónico masivo a los usuarios de Microsoft 365 y desea asegurarse de que los mensajes llegan de manera oportuna y segura, siga las sugerencias de esta sección.

### <a name="ensure-that-the-from-name-reflects-who-is-sending-the-message"></a>Asegurarse de que el nombre from refleja quién envía el mensaje

El Asunto debe ser un breve resumen del contenido del mensaje y el cuerpo del mensaje debe indicar clara y sucintamente de qué trata la oferta, servicio o producto. Por ejemplo:

Correcto:

> De: marketing@shoppershandbag.com <br/> Asunto: ¡ Catálogo actualizado para la temporada de Navidad!

Incorrecto:

> De: someone@outlook.com <br/> Asunto: Catálogos

Cuanto más fácil sea que las personas sepan quién es usted y lo que hace, menos problemas tendrá para entregar correctamente sus mensajes a través de la mayoría de los filtros de correo electrónico no deseado.

### <a name="always-include-an-unsubscribe-option-in-campaign-emails"></a>Incluir siempre una opción de cancelación de suscripción en mensajes de correo electrónico de campaña

Los correos electrónicos de marketing, especialmente los boletines, siempre deben incluir una manera de cancelar la suscripción de futuros correos. Por ejemplo:

 `This email was sent to example@contoso.com by sender@fabrikam.com.`

 `Update Profile/Email Address | Instant removal with SafeUnsubscribe&trade; | Privacy Policy`

Algunos remitentes incluyen esta opción requiriendo a los destinatarios enviar un correo electrónico a un alias determinado con "Cancelar suscripción" en el asunto. Es preferible decantarse por el ejemplo de un solo clic anterior. Si decide que los destinatarios tengan que enviar un correo, asegúrese de que cuando hagan clic en el vínculo, todos los campos obligatorios estén cumplimentados previamente.

### <a name="use-the-double-opt-in-option-for-marketing-email-or-newsletter-registration"></a>Use la opción de doble verificación para registros de correo electrónico de marketing o boletines

Se aconseja optar por esta práctica recomendada si su empresa requiere o anima a los usuarios a registrar su información de contacto para poder acceder a sus productos o servicios. Algunas empresas siguen la práctica de suscribir automáticamente a sus usuarios a mensajes de correo electrónico de marketing o boletines durante el proceso de registro, pero esto se considera un procedimiento cuestionable de marketing en el mundo del filtrado del correo electrónico.

Durante el proceso de registro, si la casilla de verificación "Sí, por favor, envíame el boletín" o "Sí, envíenme ofertas especiales" está seleccionada por defecto, los usuarios que no presten atención pueden suscribirse involuntariamente a correo electrónico de marketing o boletines de noticias que no quieren recibir.

 Se recomienda en su lugar la opción de doble verificación, lo que significa que la casilla de verificación no está seleccionada de forma predeterminada para correos electrónicos de marketing o boletines. Además, una vez que se ha enviado el formulario de registro, se envía al usuario un correo electrónico de verificación con una dirección URL que le permite confirmar su decisión de recibir correos electrónicos de marketing.

 Esto ayuda a garantizar que solo aquellos usuarios que quieren recibir correo electrónico de marketing se registraron para mensajes de correo electrónico, lo que libera a la empresa de envío de ser acusada de hacer uso de cualquier práctica de marketing de correo electrónico cuestionable.

### <a name="ensure-that-email-message-content-is-transparent-and-traceable"></a>Asegúrese de que el contenido del mensaje de correo electrónico sea transparente y rastreable.

Igual de importante que la forma en que se envían los mensajes de correo electrónico es su contenido. Al crear contenido de correo electrónico, siga las siguientes prácticas recomendadas para asegurarse de que los servicios de filtrado del correo electrónico no marcarán sus correos electrónicos:

- Cuando el mensaje de correo requiera que los destinatarios agreguen al remitente a la libreta de direcciones, debe especificarse claramente que dicha acción no es una garantía de entrega.

- Los redireccionamientos que se incluyen en el cuerpo del mensaje deben ser similares y coherentes, y no múltiples ni variados. Un redireccionamiento en este contexto es cualquier cosa que apunta fuera del mensaje, como vínculos y documentos. Si tiene mucha publicidad o vínculos de cancelación de suscripción o de actualización de perfiles, todo debe apuntar al mismo dominio. Por ejemplo:

  Correcto:

  `unsubscribe.bulkmailer.com`

  `profile.bulkmailer.com`

  `options.bulkmailer.com`

  Incorrecto:

  `unsubscribe.bulkmailer.com`

  `profile.excite.com`

  `options.yahoo.com`

- Evite contenidos con imágenes o datos adjuntos pesados, o mensajes que estén únicamente compuestos por una imagen.

- Su configuración de P3P o de privacidad pública debe especificar claramente la presencia de píxeles de seguimiento (errores o señalizaciones web).

### <a name="remove-incorrect-email-aliases-from-your-databases"></a>Quitar alias de correo electrónico incorrectos de sus bases de datos

Los alias de correo electrónico de la base de datos que generan devoluciones son innecesarios y exponen a sus correos electrónicos salientes al riesgo de ser objeto de un mayor escrutinio por parte de los servicios de filtrado del correo electrónico. Asegúrese de que la base de datos de su correo electrónico está actualizada.
