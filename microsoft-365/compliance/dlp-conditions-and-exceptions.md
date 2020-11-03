---
title: Excepciones y condiciones de la Directiva de DLP (versión preliminar)
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
ms.openlocfilehash: 2ce49b15bdb13035a37f6895b4b8865b55a62f78
ms.sourcegitcommit: e56894917d2aae05705c3b9447388d10e2156183
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "48841480"
---
# <a name="dlp-policy-conditions-and-exceptions-preview"></a>Excepciones y condiciones de la Directiva de DLP (versión preliminar)

Las condiciones y excepciones de las directivas DLP identifican los elementos confidenciales a los que se aplica la Directiva. Las condiciones definen qué incluir y las excepciones definen qué excluir. Para cada condición, hay una excepción correspondiente y usan exactamente la misma sintaxis.

 La mayoría de las condiciones y excepciones tienen una propiedad que admite uno o más valores. Por ejemplo, si la Directiva DLP se aplica a los correos electrónicos de Exchange, la condición **el remitente** es requiere el remitente del mensaje. Algunas condiciones tienen dos propiedades. Por ejemplo, la condición **Un encabezado de mensaje incluye cualquiera de estas palabras** requiere una propiedad que especifique el campo de encabezado del mensaje y una segunda propiedad que especifique el texto que hay que buscar en el campo de encabezado. Algunas condiciones o excepciones no tienen ninguna propiedad. Por ejemplo, la condición **datos adjuntos está protegida con contraseña** simplemente busca datos adjuntos en mensajes protegidos con contraseña.

## <a name="conditions-and-exceptions-for-dlp-policies"></a>Condiciones y excepciones para directivas de DLP

Las tablas de las secciones siguientes describen las condiciones y excepciones que están disponibles en DLP.

- [Remitentes](#senders)
- [Destinatarios](#recipients)
- [Asunto o cuerpo del mensaje](#message-subject-or-body)
- [Datos adjuntos](#attachments)
- [Encabezados de mensaje](#message-headers)
- [Propiedades de mensajes](#message-properties)

## <a name="senders"></a>Senders


|**condición o excepción en DLP**  |**parámetros de condición/excepción en Microsoft 365 PowerShell** |**tipo de propiedad**  |**description**|
|---------|---------|---------|---------|
|El remitente es |condición: *de* <br/> excepción: *ExceptIfFrom*      |Addresses |     Mensajes enviados por los buzones de correo especificados, los usuarios de correo, los contactos de correo o los grupos de Microsoft 365 de la organización.|
|La dirección IP del remitente es     |condición: *SenderIPRanges*<br/> excepción: *ExceptIfSenderIPRanges*         |  IPAddressRanges       | Mensajes en los que la dirección IP del remitente coincide con la dirección IP especificada o se encuentra en el intervalo de direcciones IP especificado.       |
|La dirección del remitente contiene palabras   | condición: *FromAddressContainsWords* <br/> excepción: *ExceptIfFromAddressContainsWords*        |   Words      |   Mensajes que contienen las palabras especificadas en la dirección de correo electrónico del remitente.|
| La dirección del remitente coincide con los patrones    | condición: *FromAddressMatchesPatterns* <br/> excepción: *ExceptFromAddressMatchesPatterns*       |      Patrones   |  Mensajes en los que la dirección de correo electrónico contiene patrones de texto que coinciden con las expresiones regulares especificadas.  |
|El dominio del remitente es  |  condición: *SenderDomainIs* <br/> excepción: *ExceptIfSenderDomainIs*       |Nombredominio         |     Mensajes en los que el dominio de la dirección de correo electrónico del remitente coincide con el valor especificado. Si necesita buscar dominios de remitentes que *contengan* el dominio especificado (por ejemplo, cualquier subdominio de un dominio), use **la condición coincidencia de dirección del remitente** ( *FromAddressMatchesPatterns* ) y especifique el dominio mediante la sintaxis: ' \. dominio \. com $ '.    |

## <a name="recipients"></a>Recipientes

|**condición o excepción en DLP**| **parámetros de condición/excepción en Microsoft 365 PowerShell** |    **tipo de propiedad** | **description**|
|---------|---------|---------|---------|
|El destinatario es|  condición: *sentto* <br/> excepción: *ExceptIfSentTo* | Addresses | Mensajes en los que uno de los destinatarios es el buzón especificado, el usuario de correo o el contacto de correo de la organización. Los destinatarios pueden estar en los campos **para** , **CC** o **CCO** del mensaje.|
|El dominio del destinatario es|   condición: *RecipientDomainIs* <br/> excepción: *ExceptIfRecipientDomainIs* |   Nombredominio |    Mensajes en los que el dominio de la dirección de correo electrónico del remitente coincide con el valor especificado.|
|La dirección del destinatario contiene palabras|  condición: *RecipientAddressContainsWords* <br/> excepción: *ExceptIfRecipientAddressContainsWords*|    Words|  Mensajes que contienen las palabras especificadas en la dirección de correo electrónico del destinatario. <br/>**Nota** : Esta condición no considera los mensajes que se envían a direcciones de proxy del destinatario. Solo coincide con los mensajes que se envían a la dirección de correo electrónico principal del destinatario.|
|La dirección del destinatario coincide con los patrones| condición: *RecipientAddressMatchesPatterns* <br/> excepción: *ExceptIfRecipientAddressMatchesPatterns*|   Patrones    |Mensajes en los que la dirección de correo electrónico de un destinatario contiene patrones de texto que coinciden con las expresiones regulares especificadas. <br/> **Nota** : Esta condición no considera los mensajes que se envían a direcciones de proxy del destinatario. Solo coincide con los mensajes que se envían a la dirección de correo electrónico principal del destinatario.|
|Enviado a miembro de| condición: *SentToMemberOf* <br/> excepción: *ExceptIfSentToMemberOf*|  Addresses|  Mensajes que contienen destinatarios que son miembros del grupo de distribución especificado, el grupo de seguridad habilitado para correo o el grupo Microsoft 365. El grupo puede incluirse en los campos **To** , **Cc** o **Bcc** del mensaje.|

## <a name="message-subject-or-body"></a>Asunto o cuerpo del mensaje

|**condición o excepción en DLP** | **parámetros de condición/excepción en Microsoft 365 PowerShell** |**tipo de propiedad**| **description**|
|---------|---------|---------|---------|
|El asunto contiene palabras o frases| condición: *SubjectContainsWords* <br/> excepción: *ExceptIf SubjectContainsWords*| Words   |Mensajes que contengan las palabras especificadas en el campo Subject.|
|El asunto coincide con los patrones|condición: *SubjectMatchesPatterns* <br/> excepción: *ExceptIf SubjectMatchesPatterns*|Patrones   |Mensajes en los que el campo Subject contiene patrones de texto que coinciden con las expresiones regulares especificadas.|
|Contenido contiene|  condición: *ContentContainsSensitiveInformation* <br/> excepción *ExceptIfContentContainsSensitiveInformation*| SensitiveInformationTypes|  Mensajes o documentos que contienen información confidencial, tal y como se define en las directivas de prevención de pérdida de datos (DLP).|


## <a name="attachments"></a>Attachments

|**condición o excepción en DLP**| **parámetros de condición/excepción en Microsoft 365 PowerShell**| **tipo de propiedad**   |**description**|
|---------|---------|---------|---------|
|Los datos adjuntos están protegidos con contraseña|condición: *DocumentIsPasswordProtected* <br/> excepción: *ExceptIfDocumentIsPasswordProtected*|ninguno| Mensajes en los que un archivo adjunto está protegido por contraseña (y, por lo tanto, no se puede examinar). La detección de contraseñas solo funciona para documentos de Office y archivos .zip.|
|La extensión de archivo de datos adjuntos es|condición: *ContentExtensionMatchesWords* <br/> excepción: *ExceptIfContentExtensionMatchesWords*|  Words   |Mensajes en los que la extensión de archivo de los datos adjuntos coincide con cualquiera de las palabras especificadas.|
|No se pudo analizar el contenido de los datos adjuntos de correo electrónico|condición: *DocumentIsUnsupported* <br/>excepción: *ExceptIf DocumentIsUnsupported*|   No aplicable|    Mensajes en los que Exchange online no reconoce de forma nativa los datos adjuntos.|
|No se completó el análisis del contenido de los datos adjuntos de correo|   condición: *ProcessingLimitExceeded* <br/> excepción: *ExceptIfProcessingLimitExceeded*|    N/D |Mensajes en los que el motor de reglas no pudo completar el examen de los datos adjuntos. Puede usar esta condición para crear reglas que trabajen conjuntamente para identificar y procesar mensajes en los que el contenido no pudo examinarse por completo.|
|El nombre del documento contiene palabras|condición: *DocumentNameMatchesWords* <br/> excepción: *ExceptIfDocumentNameMatchesWords* |Words  |Mensajes en los que el nombre de archivo de datos adjuntos coincide con alguna de las palabras especificadas.|
|El nombre del documento coincide con los patrones|condición: *DocumentNameMatchesPatterns* <br/> excepción: *ExceptIfDocumentNameMatchesPatterns*|    Patrones    |Mensajes en los que el nombre de archivo de los datos adjuntos contiene patrones de texto que coinciden con las expresiones regulares especificadas.|
|La propiedad del documento es|condición: *ContentPropertyContainsWords* <br/> excepción: *ExceptIfContentPropertyContainsWords* |Words| Mensajes o documentos en los que la extensión de archivo de datos adjuntos coincide con cualquiera de las palabras especificadas.|
|El tamaño del documento es igual a o es mayor que| condición: *DocumentSizeOver* <br/> excepción: *ExceptIfDocumentSizeOver*|    Size    |Mensajes en los que algún documento adjunto es mayor o igual que el valor especificado.|

## <a name="message-headers"></a>Encabezados de mensaje

|**condición o excepción en DLP**| **parámetros de condición/excepción en Microsoft 365 PowerShell**| **tipo de propiedad**|  **description**|
|---------|---------|---------|---------|
|El encabezado contiene palabras o frases|condición: *HeaderContainsWords* <br/> excepción: *ExceptIfHeaderContainsWords*|  Tabla hash  |Los mensajes que contienen el campo de encabezado especificado y el valor de ese campo de encabezado contienen las palabras especificadas.|
|El encabezado coincide con los patrones|   condición: *HeaderMatchesPatterns* <br/> excepción: *ExceptIfHeaderMatchesPatterns*|    Tabla hash  |Los mensajes que contienen el campo de encabezado especificado y el valor de ese campo de encabezado contienen las expresiones regulares especificadas.|

## <a name="message-properties"></a>Propiedades del mensaje

|**condición o excepción en DLP**| **parámetros de condición/excepción en Microsoft 365 PowerShell**| **tipo de propiedad**   |**description**|
|---------|---------|---------|---------|
|Tamaño del mensaje en|condición: *MessageSizeOver* <br/> excepción: *ExceptIfMessageSizeOver*| Size    |Mensajes en los que el tamaño total (mensaje más archivos adjuntos) es mayor o igual al valor especificado. <br/>**Nota** : Los límites de tamaño de los mensajes en los buzones se evalúan antes de las reglas de flujo de correo. Un mensaje que es demasiado grande para un buzón se rechazará antes de que una regla con esta condición sea capaz de actuar en el mensaje.  |

