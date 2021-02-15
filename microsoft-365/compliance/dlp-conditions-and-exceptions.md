---
title: Condiciones, excepciones y acciones de directiva DLP (versión preliminar)
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: obtenga información sobre las condiciones y excepciones de la directiva dlp
ms.openlocfilehash: 5c2c8e010047c2de05cc8422da1958e2fe5fc54c
ms.sourcegitcommit: d859ea36152c227699c1786ef08cda5805ecf7db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/09/2020
ms.locfileid: "49604220"
---
# <a name="dlp-policy-conditions-exceptions-and-actions-preview"></a>Condiciones, excepciones y acciones de directiva DLP (versión preliminar)

Las condiciones y excepciones de las directivas DLP identifican los elementos confidenciales a los que se aplica la directiva. Las acciones definen lo que sucede como consecuencia de una condición de excepción que se cumple.

- Las condiciones definen qué incluir
- Las excepciones definen lo que se va a excluir.
- Las acciones definen lo que sucede como consecuencia de la condición o excepción que se cumple
 
La mayoría de las condiciones y excepciones tienen una propiedad que admite uno o más valores. Por ejemplo, si la directiva DLP se aplica a los correos electrónicos de Exchange, el **remitente** es una condición que requiere el remitente del mensaje. Algunas condiciones tienen dos propiedades. Por ejemplo, la condición **Un encabezado de mensaje incluye cualquiera de estas palabras** requiere una propiedad que especifique el campo de encabezado del mensaje y una segunda propiedad que especifique el texto que hay que buscar en el campo de encabezado. Algunas condiciones o excepciones no tienen ninguna propiedad. Por ejemplo, la condición **Datos adjuntos es protegida** con contraseña simplemente busca datos adjuntos en mensajes protegidos con contraseña.

Las acciones suelen necesitar propiedades adicionales. Por ejemplo, cuando la regla de directiva DLP redirige un mensaje, debe especificar a dónde se redirige el mensaje. 
<!-- Some actions have multiple properties that are available or required. For example, when the rule adds a header field to the message header, you need to specify both the name and value of the header. When the rule adds a disclaimer to messages, you need to specify the disclaimer text, but you can also specify where to insert the text, or what to do if the disclaimer can't be added to the message. Typically, you can configure multiple actions in a rule, but some actions are exclusive. For example, one rule can't reject and redirect the same message.-->

## <a name="conditions-and-exceptions-for-dlp-policies"></a>Condiciones y excepciones para directivas DLP

Las tablas de las secciones siguientes describen las condiciones y excepciones que están disponibles en DLP.

- [Remitentes](#senders)
- [Destinatarios](#recipients)
- [Asunto o cuerpo del mensaje](#message-subject-or-body)
- [Datos adjuntos](#attachments)
- [Encabezados de mensaje](#message-headers)
- [Propiedades de mensajes](#message-properties)

### <a name="senders"></a>Senders


|**condición o excepción en DLP**  |**parámetros de condición/excepción en PowerShell de Microsoft 365** |**tipo de propiedad**  |**description**|
|---------|---------|---------|---------|
|El remitente es |condition: *From* <br/> excepción: *ExceptIfFrom*      |Addresses |     Mensajes enviados por los buzones especificados, usuarios de correo, contactos de correo o grupos de Microsoft 365 de la organización.|
|La dirección IP del remitente es     |condición: *SenderIPRanges*<br/> *excepción: ExceptIfSenderIPRanges*         |  IPAddressRanges       | Mensajes en los que la dirección IP del remitente coincide con la dirección IP especificada o se encuentra en el intervalo de direcciones IP especificado.       |
|La dirección del remitente contiene palabras   | condición: *FromAddressContainsWords* <br/> *excepción: ExceptIfFromAddressContainsWords*        |   Words      |   Mensajes que contienen las palabras especificadas en la dirección de correo electrónico del remitente.|
| La dirección del remitente coincide con los patrones    | condición: *FromAddressMatchesPatterns* <br/> *excepción: ExceptFromAddressMatchesPatterns*       |      Patrones   |  Mensajes en los que la dirección de correo electrónico contiene patrones de texto que coinciden con las expresiones regulares especificadas.  |
|El dominio del remitente es  |  condición: *SenderDomainIs* <br/> *excepción: ExceptIfSenderDomainIs*       |DomainName         |     Mensajes en los que el dominio de la dirección de correo electrónico del remitente coincide con el valor especificado. Si necesita buscar dominios  de remitente que contengan el dominio especificado (por ejemplo, cualquier subdominio de un dominio), **use** la condición de coincidencias de dirección del remitente (*FromAddressMatchesPatterns)* y especifique el dominio mediante la sintaxis: \. 'dominio \. com$'.    |
|Ámbito del remitente    | condición: *FromScope* <br/> excepción: *ExceptIfFromScope*    | UserScopeFrom    |    Mensajes enviados por remitentes internos o externos.    |

### <a name="recipients"></a>Recipientes

|**condición o excepción en DLP**| **parámetros de condición/excepción en PowerShell de Microsoft 365** |    **tipo de propiedad** | **description**|
|---------|---------|---------|---------|
|El destinatario es|  condición: *SentTo* <br/> excepción: *ExceptIfSentTo* | Addresses | Mensajes en los que uno de los destinatarios es el buzón, usuario de correo o contacto de correo especificado de la organización. Los destinatarios pueden estar en los campos **Para,** **CC** o **CCO** del mensaje.|
|El dominio del destinatario es|   condición: *RecipientDomainIs* <br/> *excepción: ExceptIfRecipientDomainIs* |   DomainName |    Mensajes en los que el dominio de la dirección de correo electrónico del remitente coincide con el valor especificado.|
|La dirección del destinatario contiene palabras|  condición: *RecipientAddressContainsWords* <br/> *excepción: ExceptIfRecipientAddressContainsWords*|    Words|  Mensajes que contienen las palabras especificadas en la dirección de correo electrónico del destinatario. <br/>**Nota**: Esta condición no considera los mensajes que se envían a direcciones de proxy del destinatario. Solo coincide con los mensajes que se envían a la dirección de correo electrónico principal del destinatario.|
|La dirección del destinatario coincide con los patrones| condición: *RecipientAddressMatchesPatterns* <br/> excepción: *ExceptIfRecipientAddressMatchesPatterns*|   Patrones    |Mensajes en los que la dirección de correo electrónico de un destinatario contiene patrones de texto que coinciden con las expresiones regulares especificadas. <br/> **Nota**: Esta condición no considera los mensajes que se envían a direcciones de proxy del destinatario. Solo coincide con los mensajes que se envían a la dirección de correo electrónico principal del destinatario.|
|Enviado al miembro de| condición: *SentToMemberOf* <br/> *excepción: ExceptIfSentToMemberOf*|  Addresses|  Mensajes que contienen destinatarios que son miembros del grupo de distribución especificado, grupo de seguridad habilitado para correo o grupo de Microsoft 365. El grupo puede incluirse en los campos **To**, **Cc** o **Bcc** del mensaje.|

### <a name="message-subject-or-body"></a>Asunto o cuerpo del mensaje

|**condición o excepción en DLP** | **parámetros de condición/excepción en PowerShell de Microsoft 365** |**tipo de propiedad**| **description**|
|---------|---------|---------|---------|
|El asunto contiene palabras o frases| condición: *SubjectContainsWords* <br/> excepción: *ExceptIf SubjectContainsWords*| Words   |Mensajes que contengan las palabras especificadas en el campo Subject.|
|El asunto coincide con los patrones|condición: *SubjectMatchesPatterns* <br/> excepción: *ExceptIf SubjectMatchesPatterns*|Patrones   |Mensajes en los que el campo Asunto contiene patrones de texto que coinciden con las expresiones regulares especificadas.|
|El contenido contiene|  condición: *ContentContainsSensitiveInformation* <br/> exception *ExceptIfContentContainsSensitiveInformation*| SensitiveInformationTypes|  Mensajes o documentos que contienen información confidencial según se definen en las directivas de prevención de pérdida de datos (DLP).|
| Patrón de coincidencias de asunto o cuerpo    | condición: *SubjectOrBodyMatchesPatterns* <br/> *excepción: ExceptIfSubjectOrBodyMatchesPatterns*    | Patrones    | Mensajes en los que el campo de asunto o el cuerpo del mensaje contienen patrones de texto que coinciden con las expresiones regulares especificadas.    |
| El asunto o el cuerpo contiene palabras    | condición: *SubjectOrBodyContainsWords* <br/> *excepción: ExceptIfSubjectOrBodyContainsWords*    | Words    | Mensajes que tienen las palabras especificadas en el campo de asunto o el cuerpo del mensaje    |


### <a name="attachments"></a>Attachments

|**condición o excepción en DLP**| **parámetros de condición/excepción en PowerShell de Microsoft 365**| **tipo de propiedad**   |**description**|
|---------|---------|---------|---------|
|Los datos adjuntos están protegidos con contraseña|condición: *DocumentIsPasswordProtected* <br/> excepción: *ExceptIfDocumentIsPasswordProtected*|none| Mensajes en los que un archivo adjunto está protegido por contraseña (y, por lo tanto, no se puede examinar). La detección de contraseñas solo funciona para documentos de Office, archivos .zip y archivos .7z.|
|La extensión de archivo de datos adjuntos es|condición: *ContentExtensionMatchesWords* <br/> excepción: *ExceptIfContentExtensionMatchesWords*|  Words   |Mensajes en los que la extensión de archivo de los datos adjuntos coincide con cualquiera de las palabras especificadas.|
|No se pudo examinar el contenido de los datos adjuntos de correo electrónico|condición: *DocumentIsUnsupported* <br/>*excepción: ExceptIf DocumentIsUnsupported*|   No aplicable|    Mensajes en los que Exchange Online no reconoce de forma nativa los datos adjuntos.|
|El contenido de los datos adjuntos de correo electrónico no ha completado el examen|   condición: *ProcessingLimitExceeded* <br/> excepción: *ExceptIfProcessingLimitExceeded*|    N/D |Mensajes en los que el motor de reglas no pudo completar el examen de los datos adjuntos. Puede usar esta condición para crear reglas que trabajen conjuntamente para identificar y procesar mensajes en los que el contenido no pudo examinarse por completo.|
|El nombre del documento contiene palabras|condición: *DocumentNameMatchesWords* <br/> excepción: *ExceptIfDocumentNameMatchesWords* |Words  |Mensajes en los que el nombre de archivo de un archivo adjunto coincide con cualquiera de las palabras especificadas.|
|El nombre del documento coincide con los patrones|condición: *DocumentNameMatchesPatterns* <br/> excepción: *ExceptIfDocumentNameMatchesPatterns*|    Patrones    |Mensajes en los que el nombre de archivo de los datos adjuntos contiene patrones de texto que coinciden con las expresiones regulares especificadas.|
|La propiedad del documento es|condición: *ContentPropertyContainsWords* <br/> excepción: *ExceptIfContentPropertyContainsWords* |Words| Mensajes o documentos en los que la extensión de archivo de un archivo adjunto coincide con cualquiera de las palabras especificadas.|
|El tamaño del documento es igual o mayor que| condición: *DocumentSizeOver* <br/> excepción: *ExceptIfDocumentSizeOver*|    Size    |Mensajes en los que algún documento adjunto es mayor o igual que el valor especificado.|

### <a name="message-headers"></a>Encabezados de mensaje

|**condición o excepción en DLP**| **parámetros de condición/excepción en PowerShell de Microsoft 365**| **tipo de propiedad**|  **description**|
|---------|---------|---------|---------|
|El encabezado contiene palabras o frases|condición: *HeaderContainsWords* <br/> excepción: *ExceptIfHeaderContainsWords*|  Tabla hash  |Los mensajes que contienen el campo de encabezado especificado y el valor de ese campo de encabezado contienen las palabras especificadas.|
|El encabezado coincide con patrones|   condición: *HeaderMatchesPatterns* <br/> excepción: *ExceptIfHeaderMatchesPatterns*|    Tabla hash  |Los mensajes que contienen el campo de encabezado especificado y el valor de ese campo de encabezado contienen las expresiones regulares especificadas.|

### <a name="message-properties"></a>Propiedades del mensaje

|**condición o excepción en DLP**| **parámetros de condición/excepción en PowerShell de Microsoft 365**| **tipo de propiedad**   |**description**|
|---------|---------|---------|---------|
|Tamaño del mensaje encima|condición: *MessageSizeOver* <br/> excepción: *ExceptIfMessageSizeOver*| Size    |Mensajes en los que el tamaño total (mensaje más archivos adjuntos) es mayor o igual al valor especificado. <br/>**Nota**: Los límites de tamaño de los mensajes en los buzones se evalúan antes de las reglas de flujo de correo. Un mensaje que es demasiado grande para un buzón se rechazará antes de que una regla con esta condición sea capaz de actuar en el mensaje.  |
| Con importancia    | condición: *WithImportance* <br/> excepción: *ExceptIfWithImportance*    | Importance    | Mensajes marcados con el nivel de importancia especificado.    |
| El juego de caracteres de contenido contiene palabras    | condición: *ContentCharacterSetContainsWords* <br/> *ExceptIfContentCharacterSetContainsWords*    | CharacterSets    | Mensajes que contienen alguno de los nombres de juego de caracteres especificados.    |
| Tiene invalidación de remitente    | condición: *HasSenderOverride* <br/> *excepción: ExceptIfHasSenderOverride*    | N/D    | Mensajes en los que el remitente ha elegido invalidar una directiva de prevención de pérdida de datos (DLP). Para obtener más información acerca de las directivas DLP, vea [Prevención de pérdida de datos.](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)   |
| Coincidencias de tipo de mensaje    | condición: *MessageTypeMatches* <br/> excepción: *ExceptIfMessageTypeMatches*    | MessageType    | Mensajes del tipo especificado.    |

## <a name="actions-for-dlp-policies"></a>Acciones para directivas DLP

En esta tabla se describen las acciones disponibles en DLP.


|**acción en DLP**|**parámetros de acción en PowerShell de Microsoft 365**|**tipo de propiedad**|**description**|
|---------|---------|---------|---------|
|Establecer encabezado|SetHeader|Primera propiedad: *Nombre de encabezado* </br> Segunda propiedad: *Valor de encabezado*|El parámetro SetHeader especifica una acción para la regla DLP que agrega o modifica un campo de encabezado y un valor en el encabezado del mensaje. Este parámetro usa la sintaxis "HeaderName:HeaderValue". Puede especificar varios pares de nombre de encabezado y valor separados por comas|
|Quitar encabezado| RemoveHeader| Primera propiedad: *MessageHeaderField*</br> Segunda propiedad: *String*|  El parámetro RemoveHeader especifica una acción para la regla DLP que quita un campo de encabezado del encabezado del mensaje. Este parámetro usa la sintaxis "HeaderName" o "HeaderName:HeaderValue". Puede especificar varios nombres de encabezado o pares de nombre de encabezado y valor separados por comas|
|Redirigir el mensaje a usuarios específicos|*RedirectMessageTo*|Addresses| Redirige el mensaje a los destinatarios especificados. El mensaje no se entrega a los destinatarios originales y no se envía ninguna notificación al remitente ni a los destinatarios originales.|
|Reenviar el mensaje para su aprobación al administrador del remitente| Moderado|Primera propiedad: *ModerateMessageByManager*</br> Segunda propiedad: *Boolean*|El parámetro Moderate especifica una acción para la regla DLP que envía el mensaje de correo electrónico a un moderador. Este parámetro usa la sintaxis: @{ModerateMessageByManager = <$true \| $false>;|
|Reenviar el mensaje para su aprobación a aprobadores específicos| Moderado|Primera propiedad: *ModerateMessageByUser*</br>Segunda propiedad: *Addresses*|El parámetro Moderate especifica una acción para la regla DLP que envía el mensaje de correo electrónico a un moderador. Este parámetro usa la sintaxis: @{ ModerateMessageByUser = @("emailaddress1","emailaddress2",..."emailaddressN")}|
|Agregar destinatario|AddRecipients|Primera propiedad: *Field*</br>Segunda propiedad: *Addresses*| Agrega uno o más destinatarios al campo Para/CC/CCO del mensaje. Este parámetro usa la sintaxis: @{<AddToRecipients \| CopyTo \| BlindCopyTo> = "emailaddress"}|
|Agregar el administrador del remitente como destinatario|AddRecipients | Primera propiedad: *AddedManagerAction*</br>Segunda propiedad: *Field* | Agrega el administrador del remitente al mensaje como el tipo de destinatario especificado ( To, Cc o Bcc ) o redirige el mensaje al administrador del remitente sin notificar al remitente ni al destinatario. Esta acción solo funciona si el atributo Manager del remitente se define en Active Directory. Este parámetro usa la sintaxis: @{AddManagerAsRecipientType = "<To \| CC \| Bcc>"}|    
Anteponer asunto    |PrependSubject    |Cadena    |Agrega el texto especificado al principio del campo Subject del mensaje. Considere la posibilidad de usar un espacio o un signo de dos puntos (:) como último carácter del texto especificado para diferenciarlo del texto del asunto original.</br>Para evitar que se agregue la misma cadena a los mensajes que ya contienen el texto del asunto (por ejemplo, respuestas), agregue la excepción "El asunto contiene palabras" (ExceptIfSubjectContainsWords) a la regla.    |
Aplicar declinación de responsabilidades html    |ApplyHtmlDisclaimer    |Primera propiedad: *Texto*</br>Segunda propiedad: *Ubicación*</br>Tercera propiedad: *acción de reserva*    |Aplica el aviso de declinación de responsabilidades HTML especificado a la ubicación necesaria del mensaje.</br>Este parámetro usa la sintaxis: @{ Text = " ; Location = <Append \| Prepend>; FallbackAction = <Wrap \| Ignore \| Reject> }




