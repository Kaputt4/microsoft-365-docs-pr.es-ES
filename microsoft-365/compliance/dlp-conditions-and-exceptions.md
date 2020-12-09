---
title: Condiciones, excepciones y acciones de la Directiva DLP (versión preliminar)
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
description: información sobre las condiciones y excepciones de la Directiva de DLP
ms.openlocfilehash: 5c2c8e010047c2de05cc8422da1958e2fe5fc54c
ms.sourcegitcommit: d859ea36152c227699c1786ef08cda5805ecf7db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/09/2020
ms.locfileid: "49604220"
---
# <a name="dlp-policy-conditions-exceptions-and-actions-preview"></a>Condiciones, excepciones y acciones de la Directiva DLP (versión preliminar)

Las condiciones y excepciones de las directivas DLP identifican los elementos confidenciales a los que se aplica la Directiva. Las acciones definen lo que ocurre como consecuencia de que se cumple una condición de excepción.

- Las condiciones definen qué se debe incluir
- Las excepciones definen qué excluir.
- Las acciones definen lo que ocurre como consecuencia de una condición o excepción que se cumple
 
La mayoría de las condiciones y excepciones tienen una propiedad que admite uno o más valores. Por ejemplo, si la Directiva DLP se aplica a los correos electrónicos de Exchange, la condición **el remitente** es requiere el remitente del mensaje. Algunas condiciones tienen dos propiedades. Por ejemplo, la condición **Un encabezado de mensaje incluye cualquiera de estas palabras** requiere una propiedad que especifique el campo de encabezado del mensaje y una segunda propiedad que especifique el texto que hay que buscar en el campo de encabezado. Algunas condiciones o excepciones no tienen ninguna propiedad. Por ejemplo, la condición **datos adjuntos está protegida con contraseña** simplemente busca datos adjuntos en mensajes protegidos con contraseña.

Las acciones suelen necesitar propiedades adicionales. Por ejemplo, cuando la regla de directiva DLP redirige un mensaje, debe especificar el lugar al que se redirige el mensaje. 
<!-- Some actions have multiple properties that are available or required. For example, when the rule adds a header field to the message header, you need to specify both the name and value of the header. When the rule adds a disclaimer to messages, you need to specify the disclaimer text, but you can also specify where to insert the text, or what to do if the disclaimer can't be added to the message. Typically, you can configure multiple actions in a rule, but some actions are exclusive. For example, one rule can't reject and redirect the same message.-->

## <a name="conditions-and-exceptions-for-dlp-policies"></a>Condiciones y excepciones para directivas de DLP

Las tablas de las secciones siguientes describen las condiciones y excepciones que están disponibles en DLP.

- [Remitentes](#senders)
- [Destinatarios](#recipients)
- [Asunto o cuerpo del mensaje](#message-subject-or-body)
- [Datos adjuntos](#attachments)
- [Encabezados de mensaje](#message-headers)
- [Propiedades de mensajes](#message-properties)

### <a name="senders"></a>Senders


|**condición o excepción en DLP**  |**parámetros de condición/excepción en Microsoft 365 PowerShell** |**tipo de propiedad**  |**description**|
|---------|---------|---------|---------|
|El remitente es |condición: *de* <br/> excepción: *ExceptIfFrom*      |Addresses |     Mensajes enviados por los buzones de correo especificados, los usuarios de correo, los contactos de correo o los grupos de Microsoft 365 de la organización.|
|La dirección IP del remitente es     |condición: *SenderIPRanges*<br/> excepción: *ExceptIfSenderIPRanges*         |  IPAddressRanges       | Mensajes en los que la dirección IP del remitente coincide con la dirección IP especificada o se encuentra en el intervalo de direcciones IP especificado.       |
|La dirección del remitente contiene palabras   | condición: *FromAddressContainsWords* <br/> excepción: *ExceptIfFromAddressContainsWords*        |   Words      |   Mensajes que contienen las palabras especificadas en la dirección de correo electrónico del remitente.|
| La dirección del remitente coincide con los patrones    | condición: *FromAddressMatchesPatterns* <br/> excepción: *ExceptFromAddressMatchesPatterns*       |      Patrones   |  Mensajes en los que la dirección de correo electrónico contiene patrones de texto que coinciden con las expresiones regulares especificadas.  |
|El dominio del remitente es  |  condición: *SenderDomainIs* <br/> excepción: *ExceptIfSenderDomainIs*       |Nombredominio         |     Mensajes en los que el dominio de la dirección de correo electrónico del remitente coincide con el valor especificado. Si necesita buscar dominios de remitentes que *contengan* el dominio especificado (por ejemplo, cualquier subdominio de un dominio), use **la condición coincidencia de dirección del remitente**(*FromAddressMatchesPatterns*) y especifique el dominio mediante la sintaxis: ' \. dominio \. com $ '.    |
|Ámbito del remitente    | condición: *FromScope* <br/> excepción: *ExceptIfFromScope*    | UserScopeFrom    |    Mensajes enviados por remitentes internos o externos.    |

### <a name="recipients"></a>Recipientes

|**condición o excepción en DLP**| **parámetros de condición/excepción en Microsoft 365 PowerShell** |    **tipo de propiedad** | **description**|
|---------|---------|---------|---------|
|El destinatario es|  condición: *sentto* <br/> excepción: *ExceptIfSentTo* | Addresses | Mensajes en los que uno de los destinatarios es el buzón especificado, el usuario de correo o el contacto de correo de la organización. Los destinatarios pueden estar en los campos **para**, **CC** o **CCO** del mensaje.|
|El dominio del destinatario es|   condición: *RecipientDomainIs* <br/> excepción: *ExceptIfRecipientDomainIs* |   Nombredominio |    Mensajes en los que el dominio de la dirección de correo electrónico del remitente coincide con el valor especificado.|
|La dirección del destinatario contiene palabras|  condición: *RecipientAddressContainsWords* <br/> excepción: *ExceptIfRecipientAddressContainsWords*|    Words|  Mensajes que contienen las palabras especificadas en la dirección de correo electrónico del destinatario. <br/>**Nota**: Esta condición no considera los mensajes que se envían a direcciones de proxy del destinatario. Solo coincide con los mensajes que se envían a la dirección de correo electrónico principal del destinatario.|
|La dirección del destinatario coincide con los patrones| condición: *RecipientAddressMatchesPatterns* <br/> excepción: *ExceptIfRecipientAddressMatchesPatterns*|   Patrones    |Mensajes en los que la dirección de correo electrónico de un destinatario contiene patrones de texto que coinciden con las expresiones regulares especificadas. <br/> **Nota**: Esta condición no considera los mensajes que se envían a direcciones de proxy del destinatario. Solo coincide con los mensajes que se envían a la dirección de correo electrónico principal del destinatario.|
|Enviado a miembro de| condición: *SentToMemberOf* <br/> excepción: *ExceptIfSentToMemberOf*|  Addresses|  Mensajes que contienen destinatarios que son miembros del grupo de distribución especificado, el grupo de seguridad habilitado para correo o el grupo Microsoft 365. El grupo puede incluirse en los campos **To**, **Cc** o **Bcc** del mensaje.|

### <a name="message-subject-or-body"></a>Asunto o cuerpo del mensaje

|**condición o excepción en DLP** | **parámetros de condición/excepción en Microsoft 365 PowerShell** |**tipo de propiedad**| **description**|
|---------|---------|---------|---------|
|El asunto contiene palabras o frases| condición: *SubjectContainsWords* <br/> excepción: *ExceptIf SubjectContainsWords*| Words   |Mensajes que contengan las palabras especificadas en el campo Subject.|
|El asunto coincide con los patrones|condición: *SubjectMatchesPatterns* <br/> excepción: *ExceptIf SubjectMatchesPatterns*|Patrones   |Mensajes en los que el campo Subject contiene patrones de texto que coinciden con las expresiones regulares especificadas.|
|Contenido contiene|  condición: *ContentContainsSensitiveInformation* <br/> excepción *ExceptIfContentContainsSensitiveInformation*| SensitiveInformationTypes|  Mensajes o documentos que contienen información confidencial, tal y como se define en las directivas de prevención de pérdida de datos (DLP).|
| El asunto o el cuerpo coincide con el patrón    | condición: *SubjectOrBodyMatchesPatterns* <br/> excepción: *ExceptIfSubjectOrBodyMatchesPatterns*    | Patrones    | Mensajes en los que el cuerpo del mensaje o el campo asunto contienen patrones de texto que coinciden con las expresiones regulares especificadas.    |
| El asunto o el cuerpo contiene palabras    | condición: *SubjectOrBodyContainsWords* <br/> excepción: *ExceptIfSubjectOrBodyContainsWords*    | Words    | Mensajes que contienen las palabras especificadas en el campo Subject o el cuerpo del mensaje    |


### <a name="attachments"></a>Attachments

|**condición o excepción en DLP**| **parámetros de condición/excepción en Microsoft 365 PowerShell**| **tipo de propiedad**   |**description**|
|---------|---------|---------|---------|
|Los datos adjuntos están protegidos con contraseña|condición: *DocumentIsPasswordProtected* <br/> excepción: *ExceptIfDocumentIsPasswordProtected*|ninguno| Mensajes en los que un archivo adjunto está protegido por contraseña (y, por lo tanto, no se puede examinar). La detección de contraseñas solo funciona con documentos de Office, archivos. zip y archivos. 7z.|
|La extensión de archivo de datos adjuntos es|condición: *ContentExtensionMatchesWords* <br/> excepción: *ExceptIfContentExtensionMatchesWords*|  Words   |Mensajes en los que la extensión de archivo de los datos adjuntos coincide con cualquiera de las palabras especificadas.|
|No se pudo analizar el contenido de los datos adjuntos de correo electrónico|condición: *DocumentIsUnsupported* <br/>excepción: *ExceptIf DocumentIsUnsupported*|   No aplicable|    Mensajes en los que Exchange online no reconoce de forma nativa los datos adjuntos.|
|No se completó el análisis del contenido de los datos adjuntos de correo|   condición: *ProcessingLimitExceeded* <br/> excepción: *ExceptIfProcessingLimitExceeded*|    N/D |Mensajes en los que el motor de reglas no pudo completar el examen de los datos adjuntos. Puede usar esta condición para crear reglas que trabajen conjuntamente para identificar y procesar mensajes en los que el contenido no pudo examinarse por completo.|
|El nombre del documento contiene palabras|condición: *DocumentNameMatchesWords* <br/> excepción: *ExceptIfDocumentNameMatchesWords* |Words  |Mensajes en los que el nombre de archivo de datos adjuntos coincide con alguna de las palabras especificadas.|
|El nombre del documento coincide con los patrones|condición: *DocumentNameMatchesPatterns* <br/> excepción: *ExceptIfDocumentNameMatchesPatterns*|    Patrones    |Mensajes en los que el nombre de archivo de los datos adjuntos contiene patrones de texto que coinciden con las expresiones regulares especificadas.|
|La propiedad del documento es|condición: *ContentPropertyContainsWords* <br/> excepción: *ExceptIfContentPropertyContainsWords* |Words| Mensajes o documentos en los que la extensión de archivo de datos adjuntos coincide con cualquiera de las palabras especificadas.|
|El tamaño del documento es igual a o es mayor que| condición: *DocumentSizeOver* <br/> excepción: *ExceptIfDocumentSizeOver*|    Size    |Mensajes en los que algún documento adjunto es mayor o igual que el valor especificado.|

### <a name="message-headers"></a>Encabezados de mensaje

|**condición o excepción en DLP**| **parámetros de condición/excepción en Microsoft 365 PowerShell**| **tipo de propiedad**|  **description**|
|---------|---------|---------|---------|
|El encabezado contiene palabras o frases|condición: *HeaderContainsWords* <br/> excepción: *ExceptIfHeaderContainsWords*|  Tabla hash  |Los mensajes que contienen el campo de encabezado especificado y el valor de ese campo de encabezado contienen las palabras especificadas.|
|El encabezado coincide con los patrones|   condición: *HeaderMatchesPatterns* <br/> excepción: *ExceptIfHeaderMatchesPatterns*|    Tabla hash  |Los mensajes que contienen el campo de encabezado especificado y el valor de ese campo de encabezado contienen las expresiones regulares especificadas.|

### <a name="message-properties"></a>Propiedades del mensaje

|**condición o excepción en DLP**| **parámetros de condición/excepción en Microsoft 365 PowerShell**| **tipo de propiedad**   |**description**|
|---------|---------|---------|---------|
|Tamaño del mensaje en|condición: *MessageSizeOver* <br/> excepción: *ExceptIfMessageSizeOver*| Size    |Mensajes en los que el tamaño total (mensaje más archivos adjuntos) es mayor o igual al valor especificado. <br/>**Nota**: Los límites de tamaño de los mensajes en los buzones se evalúan antes de las reglas de flujo de correo. Un mensaje que es demasiado grande para un buzón se rechazará antes de que una regla con esta condición sea capaz de actuar en el mensaje.  |
| Con importancia    | condición: *WithImportance* <br/> excepción: *ExceptIfWithImportance*    | Importance    | Mensajes que están marcados con el nivel de importancia especificado.    |
| El juego de caracteres de contenido contiene palabras    | condición: *ContentCharacterSetContainsWords* <br/> *ExceptIfContentCharacterSetContainsWords*    | CharacterSets    | Mensajes que contienen alguno de los nombres de juego de caracteres especificados.    |
| El remitente ha invalidado    | condición: *HasSenderOverride* <br/> excepción: *ExceptIfHasSenderOverride*    | N/D    | Mensajes en los que el remitente ha elegido invalidar una directiva de prevención de pérdida de datos (DLP). Para obtener más información sobre las directivas de DLP, vea [prevención de pérdida de datos](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies).   |
| Coincidencia de tipo de mensaje    | condición: *MessageTypeMatches* <br/> excepción: *ExceptIfMessageTypeMatches*    | MessageType    | Mensajes del tipo especificado.    |

## <a name="actions-for-dlp-policies"></a>Acciones para directivas de DLP

En esta tabla se describen las acciones que están disponibles en DLP.


|**acción en DLP**|**parámetros de acción en Microsoft 365 PowerShell**|**tipo de propiedad**|**description**|
|---------|---------|---------|---------|
|Encabezado Set|SetHeader|Primera propiedad: *nombre de encabezado* </br> Segunda propiedad: *valor de encabezado*|El parámetro SetHeader especifica una acción para la regla DLP que agrega o modifica un campo de encabezado y un valor en el encabezado del mensaje. Este parámetro usa la sintaxis "HeaderName: HeaderValue". Puede especificar varios pares de nombre de encabezado y valor separados por comas|
|Quitar encabezado| RemoveHeader| Primera propiedad: *MessageHeaderField*</br> Segunda propiedad: *String*|  El parámetro RemoveHeader especifica una acción para la regla DLP que quita un campo de encabezado del encabezado del mensaje. Este parámetro usa la sintaxis "HeaderName" o "HeaderName: HeaderValue". Puede especificar varios nombres de encabezado o nombres de encabezado y pares de valores separados por comas|
|Redirigir el mensaje a usuarios específicos|*RedirectMessageTo*|Addresses| Redirige el mensaje a los destinatarios especificados. El mensaje no se entrega a los destinatarios originales y no se envía ninguna notificación al remitente ni a los destinatarios originales.|
|Reenviar el mensaje para su aprobación al administrador del remitente| Moderado|Primera propiedad: *ModerateMessageByManager*</br> Segunda propiedad: *Boolean*|El parámetro moderado especifica una acción para la regla DLP que envía el mensaje de correo electrónico a un moderador. Este parámetro usa la siguiente sintaxis: @ {ModerateMessageByManager = <$true \| $false>;|
|Reenviar el mensaje para su aprobación a aprobadores específicos| Moderado|Primera propiedad: *ModerateMessageByUser*</br>Segunda propiedad: *Addresses*|El parámetro moderado especifica una acción para la regla DLP que envía el mensaje de correo electrónico a un moderador. Este parámetro usa la siguiente sintaxis: @ {ModerateMessageByUser = @ ("emailaddress1", "emailaddress2",... "emailaddressN")}|
|Agregar destinatario|AddRecipients|Primera propiedad: *campo*</br>Segunda propiedad: *Addresses*| Agrega uno o más destinatarios al campo para/CC/CCO del mensaje. Este parámetro usa la siguiente sintaxis: @ {<AddToRecipients \| CopyTo \| BlindCopyTo> = "EmailAddress"}|
|Agregar el administrador del remitente como destinatario|AddRecipients | Primera propiedad: *AddedManagerAction*</br>Segunda propiedad: *campo* | Agrega el administrador del remitente al mensaje como el tipo de destinatario especificado ( To, Cc o Bcc ) o redirige el mensaje al administrador del remitente sin notificar al remitente ni al destinatario. Esta acción solo funciona si el atributo Manager del remitente se define en Active Directory. Este parámetro usa la siguiente sintaxis: @ {AddManagerAsRecipientType = "<to \| CC \| CCO>"}|    
Asunto antepuesto    |PrependSubject    |String    |Agrega el texto especificado al principio del campo Subject del mensaje. Considere la posibilidad de usar un espacio o un signo de dos puntos (:) como último carácter del texto especificado para diferenciarlo del texto del asunto original.</br>Para evitar que se agregue la misma cadena a los mensajes que ya contienen el texto en el asunto (por ejemplo, respuestas), agregue la excepción "el asunto contiene palabras" (ExceptIfSubjectContainsWords) a la regla.    |
Aplicar aviso de declinación de responsabilidades HTML    |ApplyHtmlDisclaimer    |Primera propiedad: *Text*</br>Segunda propiedad: *Ubicación*</br>Tercera propiedad: *acción de reserva*    |Aplica el aviso de declinación de responsabilidades HTML especificado a la ubicación requerida del mensaje.</br>Este parámetro usa la sintaxis: @ {Text = ""; Location = <anexar \| Prepend>; FallbackAction = <ajustar \| omitir \|> de rechazo}




