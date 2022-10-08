---
title: Condiciones, excepciones y acciones de directiva DLP
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.localizationpriority: ''
ms.collection:
- tier1
- purview-compliance
search.appverid:
- MOE150
- MET150
recommendations: false
description: Obtenga información sobre las condiciones de directiva dlp y las excepciones que identifican los elementos confidenciales a los que se aplica la directiva.
ms.openlocfilehash: e66b92e9ecabbda0b3cc8e1dc902ad092c82abe0
ms.sourcegitcommit: 6df492719fecc2b213d55465dc1cd60ab4627ed6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2022
ms.locfileid: "68383951"
---
# <a name="dlp-policy-conditions-exceptions-and-actions"></a>Condiciones, excepciones y acciones de directiva DLP

Las condiciones y excepciones de las directivas DLP identifican los elementos confidenciales a los que se aplica la directiva. Las acciones definen lo que sucede como consecuencia de una condición de excepción que se cumple.

- Las condiciones definen lo que se debe incluir
- Las excepciones definen qué excluir.
- Las acciones definen lo que sucede como consecuencia de la condición o excepción que se cumple

La mayoría de las condiciones y excepciones tienen una propiedad que admite uno o varios valores. Por ejemplo, si la directiva DLP se aplica a los correos electrónicos de Exchange, la condición **El remitente** es requiere el remitente del mensaje. Algunas condiciones tienen dos propiedades. Por ejemplo, la condición **Un encabezado de mensaje incluye cualquiera de estas palabras** requiere una propiedad que especifique el campo de encabezado del mensaje y una segunda propiedad que especifique el texto que hay que buscar en el campo de encabezado. Algunas condiciones o excepciones no tienen ninguna propiedad. Por ejemplo, la condición **Attachment is password protected** simplemente busca datos adjuntos en los mensajes protegidos con contraseña.

Las acciones suelen necesitar propiedades adicionales. Por ejemplo, cuando la regla de directiva DLP redirige un mensaje, debe especificar a dónde se redirige el mensaje.
<!-- Some actions have multiple properties that are available or required. For example, when the rule adds a header field to the message header, you need to specify both the name and value of the header. When the rule adds a disclaimer to messages, you need to specify the disclaimer text, but you can also specify where to insert the text, or what to do if the disclaimer can't be added to the message. Typically, you can configure multiple actions in a rule, but some actions are exclusive. For example, one rule can't reject and redirect the same message.-->

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="conditions-and-exceptions-for-dlp-policies"></a>Condiciones y excepciones para directivas DLP

En las tablas de las secciones siguientes se describen las condiciones y excepciones que están disponibles en DLP.

- [Remitentes](#senders)
- [Destinatarios](#recipients)
- [Asunto o cuerpo del mensaje](#message-subject-or-body)
- [Adjuntos](#attachments)
- [Encabezados de mensaje](#message-headers)
- [Propiedades de mensajes](#message-properties)

### <a name="senders"></a>Remitentes

Si usa la dirección del remitente como condición o excepción, el campo real donde se busca el valor varía en función de la ubicación de la dirección del remitente configurada. De forma predeterminada, las reglas DLP usan la dirección de encabezado como dirección del remitente.

![Imagen de un encabezado de correo electrónico que muestra la diferencia entre la dirección envelope (P1) y la dirección de encabezado (P2)](../media/dlp-conditions-exceptions-meetinginvite-callouts.png)

En el nivel de inquilino, puede configurar una ubicación de dirección del remitente para que se use en todas las reglas, a menos que se invalide por una sola regla. Para establecer la configuración de directiva DLP de inquilino para evaluar la dirección del remitente desde envelope en todas las reglas, puede ejecutar el siguiente comando:

```PowerShell
Set-PolicyConfig -SenderAddressLocation Envelope
```

Para configurar la ubicación de la dirección del remitente en un nivel de regla DLP, el parámetro es *SenderAddressLocation*. Los valores disponibles son los siguientes:

- **Encabezado**: examine solo los remitentes en los encabezados del mensaje (por ejemplo, los campos **From**, **Sender** o **Reply-To** ). Este es el valor predeterminado.

- **Sobre**: examine solo los remitentes del sobre del mensaje (el valor **MAIL FROM** que se usó en la transmisión SMTP, que normalmente se almacena en el campo **Return-Path** ).

- **Encabezado o sobre** (`HeaderOrEnvelope`) Examine los remitentes en el encabezado del mensaje y el sobre del mensaje.

|condición o excepción en DLP|Parámetros de condición o excepción en PowerShell de cumplimiento de & de seguridad|tipo de propiedad|description|
|---|---|---|---|
|El remitente es|condición: *Desde* <br/><br/> excepción: *ExceptIfFrom*|Addresses|Mensajes enviados por los buzones, usuarios de correo, contactos de correo o grupos de Microsoft 365 especificados en la organización.|
|El remitente es un miembro de |*FromMemberOf* <br/><br/> *ExceptIfFromMemberOf*|Addresses|Mensajes enviados por un miembro del grupo de distribución especificado, un grupo de seguridad habilitado para correo o un grupo de Microsoft 365.|
|La dirección IP del remitente es|condición: *SenderIPRanges*<br/><br/> excepción: *ExceptIfSenderIPRanges*|IPAddressRanges|Mensajes en los que la dirección IP del remitente coincide con la dirección IP especificada o se encuentra en el intervalo de direcciones IP especificado.|
|La dirección del remitente contiene palabras|condición: *FromAddressContainsWords* <br/><br/> excepción: *ExceptIfFromAddressContainsWords*|Words|Mensajes que contienen las palabras especificadas en la dirección de correo electrónico del remitente.|
|La dirección del remitente coincide con patrones|condición: *FromAddressMatchesPatterns* <br/><br/> excepción: *ExceptFromAddressMatchesPatterns*|Patrones|Mensajes en los que la dirección de correo electrónico contiene patrones de texto que coinciden con las expresiones regulares especificadas.|
|El dominio del remitente es|condición: *SenderDomainIs* <br/><br/> excepción: *ExceptIfSenderDomainIs*|Nombrededominio|Mensajes en los que el dominio de la dirección de correo electrónico del remitente coincide con el valor especificado. Si necesita buscar dominios de remitente que *contengan* el dominio especificado (por ejemplo, cualquier subdominio de un dominio), use **la condición The sender address matches**(*FromAddressMatchesPatterns*) y especifique el dominio mediante la sintaxis : "\.domain\.com$".|
|Ámbito del remitente|condición: *FromScope* <br/><br/> excepción: *ExceptIfFromScope*|UserScopeFrom|Mensajes enviados por remitentes internos o externos.|
|Las propiedades especificadas del remitente incluyen cualquiera de estas palabras|condición: *SenderADAttributeContainsWords* <br/><br/> excepción: *ExceptIfSenderADAttributeContainsWords*|Primera propiedad:  `ADAttribute` <br/><br/> Segunda propiedad: `Words`|Mensajes en los que el atributo Active Directory especificado del remitente contiene alguna de las palabras especificadas.|
|Las propiedades especificadas del remitente coinciden con estos patrones de texto|condición: *SenderADAttributeMatchesPatterns* <br/><br/> exception: *ExceptIfSenderADAttributeMatchesPatterns*|Primera propiedad:  `ADAttribute` <br/><br/> Segunda propiedad: `Patterns`|Mensajes en los que el atributo Active Directory especificado del remitente contiene patrones de texto que coinciden con las expresiones regulares especificadas.|

### <a name="recipients"></a>Recipientes

|condición o excepción en DLP|Parámetros de condición o excepción en PowerShell de cumplimiento de & de seguridad|tipo de propiedad|description|
|---|---|---|---|
|El destinatario es|condición: *SentTo* <br/><br/> excepción: *ExceptIfSentTo*|Addresses|Mensajes en los que uno de los destinatarios es el buzón de correo, el usuario de correo o el contacto de correo especificados en la organización. Los destinatarios pueden estar en los campos **To**, **Cc** o **Bcc** del mensaje.|
|El dominio del destinatario es|condición: *RecipientDomainIs* <br/><br/> exception: *ExceptIfRecipientDomainIs*|Nombrededominio|Mensajes en los que el dominio de la dirección de correo electrónico del destinatario coincide con el valor especificado.|
|La dirección del destinatario contiene palabras|condición: *AnyOfRecipientAddressContainsWords* <br/><br/> excepción: *ExceptIfAnyOfRecipientAddressContainsWords*|Words|Mensajes que contienen las palabras especificadas en la dirección de correo electrónico del destinatario. <br/><br/>**Note**: This condition doesn't consider messages that are sent to recipient proxy addresses. It only matches messages that are sent to the recipient's primary email address.|
|La dirección del destinatario coincide con patrones|condición: *AnyOfRecipientAddressMatchesPatterns* <br/><br/> exception: *ExceptIfAnyOfRecipientAddressMatchesPatterns*|Patrones|Mensajes en los que la dirección de correo electrónico de un destinatario contiene patrones de texto que coinciden con las expresiones regulares especificadas. <br/><br/> **Note**: This condition doesn't consider messages that are sent to recipient proxy addresses. It only matches messages that are sent to the recipient's primary email address.|
|Enviado al miembro de|condición: *SentToMemberOf* <br/><br/> exception: *ExceptIfSentToMemberOf*|Addresses|Mensajes que contienen destinatarios que son miembros del grupo de distribución especificado, un grupo de seguridad habilitado para correo o un grupo de Microsoft 365. El grupo puede incluirse en los campos **To**, **Cc** o **Bcc** del mensaje.|
|Las propiedades especificadas del destinatario incluyen cualquiera de estas palabras |*RecipientADAttributeContainsWords* <br/><br/> *ExceptIfRecipientADAttributeContainsWords*|Primera propiedad:  `ADAttribute` <br/><br/> Segunda propiedad: `Words`|Mensajes en los que el atributo Active Directory especificado del destinatario contiene alguna de las palabras especificadas. <br/><br/> Tenga en cuenta que el atributo **Country** requiere el valor de código de país de dos letras (por ejemplo, DE para Alemania).|
|Las propiedades especificadas del destinatario coinciden con estos patrones de texto |*RecipientADAttributeMatchesPatterns* <br/><br/> *ExceptIfRecipientADAttributeMatchesPatterns*|Primera propiedad:  `ADAttribute` <br/><br/> Segunda propiedad: `Patterns`|Mensajes en los que el atributo Active Directory especificado del destinatario contiene patrones de texto que coinciden con las expresiones regulares especificadas.|

### <a name="message-subject-or-body"></a>Asunto o cuerpo del mensaje

|condición o excepción en DLP|Parámetros de condición o excepción en PowerShell de cumplimiento de & de seguridad|tipo de propiedad|description|
|---|---|---|---|
|El asunto contiene palabras o frases|condición: *SubjectContainsWords* <br/> excepción: *ExceptIf SubjectContainsWords*|Words|Mensajes que contengan las palabras especificadas en el campo Subject.|
|El asunto coincide con patrones|condición: *SubjectMatchesPatterns* <br/> exception: *ExceptIf SubjectMatchesPatterns*|Patrones|Mensajes en los que el campo Asunto contiene patrones de texto que coinciden con las expresiones regulares especificadas.|
|El contenido contiene|condición: *ContentContainsSensitiveInformation* <br/> exception *ExceptIfContentContainsSensitiveInformation*|SensitiveInformationTypes|Mensajes o documentos que contienen información confidencial según lo definido por las directivas de Prevención de pérdida de datos de Microsoft Purview (DLP).|
|El asunto o el cuerpo coinciden con el patrón|condición: *SubjectOrBodyMatchesPatterns* <br/> excepción: *ExceptIfSubjectOrBodyMatchesPatterns*|Patrones|Los mensajes en los que el campo de asunto o el cuerpo del mensaje contienen patrones de texto que coinciden con las expresiones regulares especificadas.|
|Subject o Body contiene palabras|condición: *SubjectOrBodyContainsWords* <br/> excepción: *ExceptIfSubjectOrBodyContainsWords*|Words|Mensajes que tienen las palabras especificadas en el campo de asunto o el cuerpo del mensaje|
|

### <a name="attachments"></a>Datos adjuntos

|condición o excepción en DLP|Parámetros de condición o excepción en PowerShell de cumplimiento de & de seguridad|tipo de propiedad|description|
|---|---|---|---|
|Los datos adjuntos están protegidos con contraseña|condición: *DocumentIsPasswordProtected* <br/><br/> excepción: *ExceptIfDocumentIsPasswordProtected*|ninguno|Mensajes en los que un archivo adjunto está protegido por contraseña (y, por lo tanto, no se puede examinar). La detección de contraseñas solo funciona para documentos de Office, archivos .zip y archivos .7z.|
|La extensión del archivo adjunto es|condición: *ContentExtensionMatchesWords* <br/><br/> excepción: *ExceptIfContentExtensionMatchesWords*|Words|Mensajes en los que la extensión de archivo de los datos adjuntos coincide con cualquiera de las palabras especificadas.|
|No se pudo digitalizar algún contenido de los datos adjuntos del correo|condición: *DocumentIsUnsupported* <br/><br/>excepción: *ExceptIf DocumentIsUnsupported*|No aplicable|Mensajes en los que los datos adjuntos no se reconocen de forma nativa por Exchange Online.|
|No se pudo completar el análisis de algún contenido de los datos adjuntos del correo|condición: *ProcessingLimitExceeded* <br/><br/> excepción: *ExceptIfProcessingLimitExceeded*|No aplicable|Messages where the rules engine couldn't complete the scanning of the attachments. You can use this condition to create rules that work together to identify and process messages where the content couldn't be fully scanned.|
|El nombre del documento contiene palabras|condición: *DocumentNameMatchesWords* <br/><br/> excepción: *ExceptIfDocumentNameMatchesWords*|Words|Mensajes en los que el nombre de archivo de un archivo adjunto coincide con cualquiera de las palabras especificadas.|
|El nombre del documento coincide con los patrones|condición: *DocumentNameMatchesPatterns* <br/><br/> excepción: *ExceptIfDocumentNameMatchesPatterns*|Patrones|Mensajes en los que el nombre de archivo de los datos adjuntos contiene patrones de texto que coinciden con las expresiones regulares especificadas.|
|La propiedad del documento es|condición: *ContentPropertyContainsWords* <br/><br/> excepción: *ExceptIfContentPropertyContainsWords*|Words|Mensajes con documentos en los que la propiedad personalizada de los datos adjuntos coincide con el valor especificado.|
|El tamaño del documento es igual o mayor que|condición: *DocumentSizeOver* <br/><br/> exception: *ExceptIfDocumentSizeOver*|Size|Mensajes en los que algún documento adjunto es mayor o igual que el valor especificado.|
|El contenido de cualquier archivo adjunto incluye alguna de estas palabras|condición: *DocumentContainsWords* <br/><br/> excepción: *ExceptIfDocumentContainsWords*|`Words`|Mensajes en los que un archivo adjunto contiene las palabras especificadas.|
|Cualquier contenido adjunto coincide con estos patrones de texto|condición: *DocumentMatchesPatterns* <br/><br/> excepción: *ExceptIfDocumentMatchesPatterns*|`Patterns`|Mensajes en los que un archivo adjunto contiene patrones de texto que coinciden con las expresiones regulares especificadas.|

### <a name="message-headers"></a>Encabezados de mensaje

|condición o excepción en DLP|Parámetros de condición o excepción en PowerShell de cumplimiento de & de seguridad|tipo de propiedad|description|
|---|---|---|---|
|El encabezado contiene palabras o frases|condición: *HeaderContainsWords* <br/><br/> excepción: *ExceptIfHeaderContainsWords*|Tabla hash|Los mensajes que contienen el campo de encabezado especificado y el valor de ese campo de encabezado contiene las palabras especificadas.|
|El encabezado coincide con patrones|condición: *HeaderMatchesPatterns* <br/><br/> excepción: *ExceptIfHeaderMatchesPatterns*|Tabla hash|Los mensajes que contienen el campo de encabezado especificado y el valor de ese campo de encabezado contiene las expresiones regulares especificadas.|

### <a name="message-properties"></a>Propiedades de los mensajes

|condición o excepción en DLP|Parámetros de condición o excepción en PowerShell de cumplimiento de & de seguridad|tipo de propiedad|description|
|---|---|---|---|
|Con importancia|condición: *WithImportance* <br/><br/> excepción: *ExceptIfWithImportance*|Importancia|Mensajes marcados con el nivel de importancia especificado.|
|El juego de caracteres de contenido contiene palabras|condición: *ContentCharacterSetContainsWords* <br/><br/> *ExceptIfContentCharacterSetContainsWords*|Conjuntos de caracteres|Mensajes que contienen alguno de los nombres de juego de caracteres especificados.|
|Tiene la invalidación del remitente|condición: *HasSenderOverride* <br/><br/> excepción: *ExceptIfHasSenderOverride*|No aplicable|Mensajes en los que el remitente ha elegido invalidar una directiva de prevención de pérdida de datos (DLP). Para obtener más información sobre las directivas DLP, consulte [Más información sobre la prevención de pérdida de datos](./dlp-learn-about-dlp.md).|
|Coincidencias de tipo de mensaje|condición: *MessageTypeMatches* <br/><br/> exception: *ExceptIfMessageTypeMatches*|MessageType|Mensajes del tipo especificado. **Nota**: Los tipos de mensaje disponibles son Respuesta automática, Reenvío automático, Cifrado (S/MIME), Calendario, Control de permisos (administración de derechos), Correo de voz, Firmado, Recibo de lectura y Solicitud de aprobación. |
|El tamaño del mensaje es mayor o igual que|condición: *MessageSizeOver* <br/><br/> excepción: *ExceptIfMessageSizeOver*|`Size`|Mensajes en los que el tamaño total (mensaje más archivos adjuntos) es mayor o igual al valor especificado. **Nota**: Los límites de tamaño de los mensajes en los buzones se evalúan antes de las reglas de flujo de correo. Un mensaje que es demasiado grande para un buzón se rechazará antes de que una regla con esta condición sea capaz de actuar en el mensaje.|

## <a name="actions-for-dlp-policies"></a>Acciones para directivas DLP

En esta tabla se describen las acciones que están disponibles en DLP.

|acción en DLP|parámetros de acción en PowerShell de cumplimiento de & de seguridad|tipo de propiedad|description|
|---|---|---|---|
|Establecer encabezado|SetHeader|Primera propiedad: *Nombre del encabezado* <br/><br/> Segunda propiedad: *Valor de encabezado*|El parámetro SetHeader especifica una acción para la regla DLP que agrega o modifica un campo de encabezado y un valor en el encabezado del mensaje. Este parámetro usa la sintaxis "HeaderName:HeaderValue". Puede especificar varios pares de nombre de encabezado y valor separados por comas|
|Quitar encabezado|RemoveHeader|Primera propiedad: *MessageHeaderField*<br/><br/> Segunda propiedad: *String*|El parámetro RemoveHeader especifica una acción para la regla DLP que quita un campo de encabezado del encabezado del mensaje. Este parámetro usa la sintaxis "HeaderName" o "HeaderName:HeaderValue". Puede especificar varios nombres de encabezado o pares de nombre de encabezado y valor separados por comas|
|Redirigir el mensaje a usuarios específicos|*RedirectMessageTo*|Addresses|Redirects the message to the specified recipients. The message isn't delivered to the original recipients, and no notification is sent to the sender or the original recipients.|
|Reenviar el mensaje para su aprobación al administrador del remitente|Moderado|Primera propiedad: *ModerateMessageByManager*<br/><br/> Segunda propiedad: *Boolean*|El parámetro Moderate especifica una acción para la regla DLP que envía el mensaje de correo electrónico a un moderador. Este parámetro usa la sintaxis @{ModerateMessageByManager = <$true \|$false>;|
|Reenviar el mensaje para su aprobación a aprobadores específicos|Moderado|Primera propiedad: *ModerateMessageByUser*<br/><br/>Segunda propiedad: *Addresses*|El parámetro Moderate especifica una acción para la regla DLP que envía el mensaje de correo electrónico a un moderador. Este parámetro usa la sintaxis @{ ModerateMessageByUser = @("emailaddress1","emailaddress2",..."emailaddressN")}|
|Agregar destinatario|AddRecipients|Primera propiedad: *Field*<br/><br/>Segunda propiedad: *Addresses*|Agrega uno o varios destinatarios al campo To/Cc/Bcc del mensaje. Este parámetro usa la sintaxis @{<AddToRecipients \<CopyTo \| BlindCopyTo\> = "emailaddress"}|
|Agregar el administrador del remitente como destinatario|AddRecipients|Primera propiedad: *AddedManagerAction*<br/><br/>Segunda propiedad: *Field*|Agrega el administrador del remitente al mensaje como el tipo de destinatario especificado (To, Cc o Bcc) o redirige el mensaje al administrador del remitente sin notificar al remitente ni al destinatario. Esta acción solo funciona si el atributo Manager del remitente se define en Active Directory. Este parámetro usa la sintaxis @{AddManagerAsRecipientType = "\<To \| Cc \| Bcc\>"}|
Anteponer asunto|PrependSubject|Cadena|Adds the specified text to the beginning of the Subject field of the message. Consider using a space or a colon (:) as the last character of the specified text to differentiate it from the original subject text.<br/><br/>Para evitar que se agregue la misma cadena a los mensajes que ya contienen el texto del asunto (por ejemplo, respuestas), agregue la excepción "The subject contains words" (ExceptIfSubjectContainsWords) a la regla.|
|Aplicación de declinación de responsabilidades de HTML|ApplyHtmlDisclaimer|Primera propiedad: *Text*<br/><br/>Segunda propiedad: *Location*<br/><br/>Tercera propiedad: *Acción de reserva*|Aplica la declinación de responsabilidades HTML especificada a la ubicación necesaria del mensaje.<br/><br/>Este parámetro usa la sintaxis : @{ Text = " " ; Location = \<Append \| Prepend\>; FallbackAction = \<Wrap \| Ignore \| Reject\> }|
|Eliminación del cifrado de mensajes y la protección de derechos|RemoveRMSTemplate|No aplicable|Quita el cifrado de mensajes aplicado en un correo electrónico|
|Entrega del mensaje a la cuarentena hospedada |*Cuarentena*|No aplicable| Esta acción se encuentra actualmente en **versión preliminar pública**. Durante esta fase, los correos electrónicos en cuarentena por directivas DLP mostrarán el tipo de directiva como ExchangeTransportRule.<br/><br/> Entrega el mensaje a la cuarentena en EOP. Para obtener más información, vea [Mensajes de correo electrónico en cuarentena en EOP](/microsoft-365/security/office-365-security/quarantine-email-messages).|
|Modificar asunto|ModifySubject|PswsHashTable | Quite el texto de la línea de asunto que coincida con un patrón específico y reemplácelo por otro texto. Consulte el ejemplo siguiente. Puede: <br/><br/>- **Reemplazar** todas las coincidencias del asunto por el texto de reemplazo <br/><br/>- **Anexar** para quitar todas las coincidencias en el asunto e inserta el texto de reemplazo al final del asunto. <br/><br/>- **Anteponga** para quitar todas las coincidencias e inserte el texto de reemplazo al principio del asunto. Consulte ModifySubject parameter in, /powershell/module/exchange/new-dlpcompliancerule|
