---
title: Campos de metadatos de documento en eDiscovery (Premium)
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: En este artículo se definen los campos de metadatos de los documentos de un conjunto de revisión en un caso de Microsoft Purview eDiscovery (Premium) en Microsoft 365.
ms.openlocfilehash: a6fc8479d3ecd2b89c0331220fb7f88f46bda1e4
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2022
ms.locfileid: "66629759"
---
# <a name="document-metadata-fields-in-ediscovery-premium"></a>Campos de metadatos de documento en eDiscovery (Premium)

En la tabla siguiente se enumeran los campos de metadatos de los documentos de un conjunto de revisión en un caso de Microsoft Purview eDiscovery (Premium). La tabla proporciona la siguiente información:

- **Nombre** del **campo y Nombre del campo para mostrar:** el nombre del campo de metadatos y el nombre del campo que se muestra al ver los metadatos de archivo de un documento seleccionado en un conjunto de revisión. Algunos campos de metadatos no se incluyen al ver los metadatos de archivo de un documento. Estos campos se resaltan con un asterisco (*).

- **Nombre del campo que se puede buscar:** Nombre de la propiedad que puede buscar al ejecutar una [consulta de conjunto de revisión](review-set-search.md). Una celda en blanco significa que no puede buscar el campo en una consulta de conjunto de revisión.

- **Nombre del campo exportado:** Nombre del campo de metadatos que se incluye cuando se exportan documentos.  Una celda en blanco significa que el campo no se incluye con los metadatos exportados.

- **Descripción:** Descripción del campo de metadatos.

> [!NOTE]
> El campo **Palabras clave** de [la búsqueda de conjuntos de revisión](./review-set-search.md) usa lenguaje de consulta de palabras clave (KQL). Los campos enumerados en la columna **Nombre de campo** que se pueden buscar se pueden usar en el campo **Palabras clave** de una búsqueda de conjunto de revisión para formar consultas complejas sin tener que usar el generador de consultas. Para obtener más información sobre KQL, vea [Referencia de sintaxis del lenguaje de consulta de palabras clave](/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference).

<br>

****

|Nombre del campo y Nombre del campo para mostrar|Nombre del campo en el que se puede buscar|Nombre del campo exportado|Description|
|---|---|---|---|
|Identificador de contenido de datos adjuntos|AttachmentContentId||Identificador de contenido de datos adjuntos del elemento.|
|Puntuación de privilegios de cliente de abogado|AttorneyClientPrivilegeScore||Puntuación de contenido del modelo de privilegios abogado-cliente.|
|Autor|Autor|Doc_authors|Crear a partir de los metadatos del documento.|
|BCC|Bcc|Email_bcc|Campo CCO para los tipos de mensaje. El formato es **DisplayName \<SMTPAddress\>**.|
|CC|Cc|Email_cc|Campo Cc para los tipos de mensaje. El formato es **DisplayName \<SMTPAddress\>**.|
|Etiquetas de cumplimiento|ComplianceLabels|Compliance_labels|[Etiquetas de retención aplicadas](retention.md) al contenido de Office 365.|
|Ruta de acceso compuesta|CompoundPath|Compound_path|Ruta de acceso legible humana que describe el origen del elemento.|
|Contenido*|Contenido||Texto extraído del elemento.|
|Cuerpo de la conversación|ConversationBody||Cuerpo de la conversación del elemento.|
|Identificador de conversación|ConversationId|Conversation_ID|Identificador de conversación del mensaje. Para Teams 1:1 y los chats de grupo, todos los archivos de transcripción y sus elementos familiares dentro de la misma conversación comparten el mismo identificador de conversación. Para obtener más información, vea [Flujo de trabajo de eDiscovery (Premium) para contenido en Microsoft Teams](teams-workflow-in-advanced-ediscovery.md).|
|Id. de familia de conversación|ConversationFamilyID|ConversationFamilyID|Identificador que identifica elementos individuales de una conversación, así como los elementos relacionados de la conversación.|
|Índice de conversación||Conversation_index|Índice de conversación del mensaje.|
|Nombre de la conversación||ConversationName|Este campo depende del tipo de contenido.<br>**Chat de Teams 1:1:** primeros 40 caracteres del primer mensaje.<br>**Chat de Teams 1:N:** Nombre del chat de grupo; si no está disponible, los primeros 40 caracteres del primer mensaje.<br>**Publicación del canal de Teams:** Título de publicación o subpartida de anuncio; si no está disponible, los primeros 40 caracteres del primer mensaje.|
|Tiempo de conversación en pdf|ConversationPdfTime||Fecha en la que se creó la versión en PDF de la conversación.|
|Tiempo de grabación de redacción de conversación|ConversationRedactionBurnTime||Fecha en la que se creó la versión en PDF de la conversación para Chat.|
|Tema de conversación|ConversationTopic||Tema de conversación del elemento.|
|Tipo de conversación|ConversationType|ConversationType|Tipo de conversación de chat. Los valores son: <br>**Teams 1:1 y chats grupales y todas las conversaciones de Yammer:** Grupo<br>**Canales de Teams y canales privados:** Canal|
|Contiene el mensaje eliminado|ContainsDeletedMessage|ContainsDeletedMessage|Indica si la transcripción del chat incluye un mensaje eliminado|
|Contiene el mensaje editado|ContainsEditedMessage|ContainsEditedMessage|Indica si la transcripción del chat incluye un mensaje editado|
|Título del anuncio de Teams|TeamsAnnouncementTitle|TeamsAnnouncementTitle|Título de un [anuncio de equipos](https://support.microsoft.com/office/send-an-announcement-to-a-channel-8f244ea6-235a-4dcc-9143-9c5b801b4992).|
|||Converted_file_path|Ruta de acceso del archivo de exportación convertido. Solo para uso interno de Microsoft.|
|Custodio|Custodio|Custodio|Nombre del custodio al que estaba asociado el elemento.|
|Fecha|Fecha|Fecha|Date es un campo calculado que depende del tipo de archivo.<p>**Correo electrónico**: fecha de envío<br>**Datos adjuntos de correo electrónico**: fecha de última modificación del documento; si no está disponible, la fecha de envío del elemento primario<br>**Documentos incrustados**: fecha de última modificación del documento; si no está disponible, la fecha de última modificación del elemento primario<br>**Documentos SPO (incluye datos adjuntos modernos):** fecha de última modificación del documento; si no está disponible, fecha de última modificación de SharePoint<br>**Documentos no Office 365**: fecha de última modificación<br>**Reuniones**: fecha de inicio de la reunión<br>**VoiceMail**: fecha de envío<br>**MI**: fecha de envío<br>**Teams**: fecha de envío|
|Comentarios del documento|DocComments|Doc_comments|Comentarios de los metadatos del documento.|
|Empresa de documentos||Doc_company|Empresa de los metadatos del documento.|
|Fecha de creación del documento|CreatedTime|Doc_date_created|Cree la fecha a partir de los metadatos del documento.|
|DocIndex*|||Índice de la familia. **-1** o **0** significa que es la raíz.|
|Palabras clave de documento||Doc_keywords|Palabras clave de los metadatos del documento.|
|Documento modificado por||Doc_modified_by|El usuario que modificó por última vez el documento a partir de los metadatos del documento.|
|Revisión del documento|Doc_Version|Doc_Version|Revisión de los metadatos del documento.|
|Asunto del documento||Doc_subject|Asunto de los metadatos del documento.|
|Plantilla de documento||Doc_template|Plantilla de los metadatos del documento.|
|DocLastSavedBy||Doc_last_saved_by|Nombre del usuario que guardó por última vez el documento.|
|Tema dominante|DominantTheme|Dominant_theme|Tema dominante calculado para el análisis.|
|Subconjunto duplicado||Duplicate_subset|Id. de grupo para duplicados exactos.|
|EmailAction*||Email_action|Los valores son **None**, **Reply** o **Forward**; en función de la línea de asunto de un mensaje.|
|Recibo de entrega por correo electrónico solicitado||Email_delivery_receipt|Dirección de correo electrónico proporcionada en Encabezados de Internet para el recibo de entrega.|
|Importancia|EmailImportance|Email_importance|Importancia del mensaje: **0** - Bajo; **1** - Normal; **2** - Alto|
|Errores de procesamiento omitidos|ErrorIgnored|Error_Ignored|Se omitió el error y no se corrigió.|
|EmailInternetHeaders|EmailInternetHeaders|Email_internet_headers|Conjunto completo de encabezados de correo electrónico del mensaje de correo electrónico|
|EmailLevel*||Email_level|Indica el nivel de un mensaje dentro del subproceso de correo electrónico al que pertenece; los datos adjuntos heredan el valor de su mensaje primario.|
|Id. de mensaje de correo electrónico||Email_message_ID|Identificador de mensaje de Internet del mensaje.|
|EmailReadReceiptRequested||Email_read_receipt|Dirección de correo electrónico proporcionada en Encabezados de Internet para la recepción de lectura.|
|Seguridad del correo electrónico|EmailSecurity|Email_security|Configuración de seguridad del mensaje: **0** - Ninguno; **1** - Firmado; **2** - Cifrado; **3** - Cifrado y firmado.|
|Confidencialidad del correo electrónico|EmailSensitivity|email_sensitivity|Configuración de confidencialidad del mensaje: **0** - Ninguno; **1** Personal; **2** - Privado; **3** - CompanyConfidential.|
|Conjunto de correo electrónico|EmailSet|Email_set|Id. de grupo para todos los mensajes del mismo conjunto de correo electrónico.|
|EmailThread*||Email_thread|Posición del mensaje dentro del conjunto de correo electrónico; consta de identificadores de nodo de la raíz al mensaje actual y están separados por puntos (.).|
|||Export_native_path|Ruta de acceso del archivo exportado.|
|Tipo de contenido extraído||Native_type|Tipo de contenido extraído, en forma de tipo mime; por ejemplo, **image/jpeg**|
|||Extracted_text_path|Ruta de acceso al archivo de texto extraído en la exportación.|
|ExtractedTextLength*||Extracted_text_length|Número de caracteres en el texto extraído.|
|FamilyDuplicateSet*||Family_duplicate_set|Identificador numérico de las familias que son duplicados exactos entre sí (el mismo contenido y todos los mismos datos adjuntos).|
|Id. de familia|FamilyId|Family_ID|Agrupa los datos adjuntos y los elementos extraídos del correo electrónico y chats con su elemento primario. Esto incluye el chat o el correo electrónico y todos los datos adjuntos y los elementos extraídos.|
|Tamaño de familia||Family_size|Número de documentos de la familia.|
|Clase de archivo|FileClass|File_class|Para el contenido de SharePoint y OneDrive: **Documento**. <br>Para el contenido de Exchange: **correo electrónico** o **datos adjuntos**. <br>Para el contenido de Teams o Yammer: **conversaciones**.|
|Id. de archivo|FileId|File_ID|Identificador de documento único dentro del caso.|
|Fecha de creación del sistema de archivos||File_system_date_created|Fecha de creación a partir del sistema de archivos (solo se aplica a datos que no son de Office 365).|
|Fecha de modificación del sistema de archivos||File_system_date_modified|Fecha de modificación del sistema de archivos (solo se aplica a datos que no son Office 365).|
|Tipo de archivo|FileType||Tipo de archivo del elemento basado en la extensión de archivo.|
|Id. de grupo|GroupId|Group_ID|Agrupa todos los elementos de correo electrónico y documentos. En el caso del correo electrónico, esto incluye el mensaje y todos los datos adjuntos y los elementos extraídos. En el caso de los documentos, esto incluye el documento y los elementos incrustados.|
|Tiene datos adjuntos|EmailHasAttachment|Email_has_attachment|Indica si el mensaje tiene datos adjuntos.|
|Tiene abogado|HasAttorney||**True** cuando al menos uno de los participantes se encuentra en la lista de abogados; De lo contrario, el valor es **False**.|
|HasText*||Has_text|Indica si el elemento tiene o no texto; los valores posibles son **True** y **False**.|
|Identificador inmutable||Immutable_ID|Este identificador se usa para identificar de forma única un documento dentro de un conjunto de revisión. Este campo no se puede usar en una búsqueda de conjuntos de revisión y el identificador no se puede usar para acceder a un documento en su ubicación nativa.|
|Tipo inclusivo|InclusiveType|Inclusive_type|Tipo inclusivo calculado para el análisis: **0** - no inclusivo; **1** - inclusivo; **2** - inclusive menos; **3** - copia inclusiva.|
|En Respuesta al identificador||In_reply_to_ID|En respuesta al identificador del mensaje.|
|InputFileExtension||Original_file_extension|Extensión de archivo original del archivo.|
|InputFileID||Input_file_ID|Identificador de archivo del elemento de nivel superior del conjunto de revisión. Para los datos adjuntos, este identificador será el identificador del elemento primario. Esto se puede usar para agrupar familias.|
|Es datos adjuntos modernos|IsModernAttachment||Este archivo es un archivo adjunto o vinculado moderno.|
|Es de la versión del documento|IsFromDocumentVersion||El documento actual es de una versión diferente de otro documento.|
|Es datos adjuntos de correo electrónico|IsEmailAttachment||Este elemento procede de un archivo adjunto de correo electrónico que aparece como un elemento adjunto al mensaje.|
|Es datos adjuntos insertados|IsInlineAttachment||Se adjuntaba en línea y se muestra en el cuerpo del mensaje.|
|¿Es representativo?|IsRepresentative|Is_representative|Un documento de cada conjunto de duplicados exactos se marca como representativo.|
|Clase Item|ItemClass|Item_class|Clase de elemento proporcionada por exchange server; por ejemplo, **IPM. Nota**|
|Última modificación|LastModifiedDate|Doc_date_modified|Fecha de última modificación de los metadatos del documento.|
|Id. de carga|LoadId|Load_ID|Identificador del conjunto de carga en el que se agregó el elemento a un conjunto de revisión.|
|Ubicación|Ubicación|Ubicación|Cadena que indica el tipo de ubicación desde la que se originaron los documentos.<p>**Datos importados**: datos no Office 365<br>**Teams** : Microsoft Teams<br>**Exchange** : buzones de Exchange<br>**SharePoint** : sitios de SharePoint<br>**OneDrive** : cuentas de OneDrive|
|Nombre de ubicación|LocationName|Location_name|Cadena que identifica el origen del elemento. Para el intercambio, esta será la dirección SMTP del buzón; para SharePoint y OneDrive, la dirección URL de la colección de sitios.|
|||Marked_as_pivot|Este archivo es la dinámica de un conjunto casi duplicado.|
|Marcado como representativo|MarkAsRepresentative||Un documento de cada conjunto de duplicados exactos se marca como representantes.|
|Fecha de finalización de la reunión|MeetingEndDate|Meeting_end_date|Fecha de finalización de la reunión para reuniones.|
|Fecha de inicio de la reunión|MeetingStartDate|Meeting_start_date|Fecha de inicio de la reunión para las reuniones.|
|Tipo de mensaje|MessageKind|Message_kind|Tipo de mensaje que se va a buscar. Valores posibles: **<p>contactos <br>docs <br>email <br>externaldata <br>faxes <br>im <br>journals <br><br>meeting microsoftteams** (devuelve elementos de chats, reuniones y llamadas en Microsoft Teams) **<br>entradas <br><br>rssfeeds <br>tasks <br>voicemail**|
|Identificador primario de datos adjuntos modernos||ModernAttachment_ParentId|Identificador inmutable del elemento primario del documento.|
|Extensión nativa|NativeExtension|Native_extension|Extensión nativa del elemento.|
|Nombre de archivo nativo|NativeFileName|Native_file_name|Nombre de archivo nativo del elemento.|
|NativeMD5||Native_MD5|Hash MD5 (valor hash de 128 bits) del flujo de archivo.|
|NativeSHA256||Native_SHA_256|Hash SHA256 (valor hash de 256 bits) de la secuencia de archivos.|
|Ordenación de ND/ET: exclusión de datos adjuntos|NdEtSortExclAttach|ND_ET_sort_excl_attach|Concatenación del conjunto de subprocesos de correo electrónico (ET) y conjunto casi duplicado (ND). Este campo se usa para una ordenación eficaz en tiempo de revisión. Una **D** tiene el prefijo de conjuntos de ND y una **E** se anteponga a los conjuntos ET.|
|Ordenación de ND/ET: incluir datos adjuntos|NdEtSortInclAttach|ND_ET_sort_incl_attach|Concatenación de un conjunto de subprocesos de correo electrónico (ET) y un conjunto casi duplicado (ND). Este campo se usa para una ordenación eficaz en tiempo de revisión. Una **D** tiene el prefijo de conjuntos de ND y una **E** se anteponga a los conjuntos ET. Cada elemento de correo electrónico de un conjunto et va seguido de sus datos adjuntos adecuados.|
|Conjunto casi duplicado||ND_set|Los elementos que son similares al documento dinámico comparten el mismo ND_set.|
|Autores de O365||O365_authors|Crear desde SharePoint.|
|O365 creado por||O365_created_by|Creado por desde SharePoint.|
|Fecha de creación de O365||O365_date_created|Fecha de creación desde SharePoint.|
|O365ModifiedDate||O365_date_modified|La fecha en que se modificó un documento (o versión del documento) recopilado de SharePoint o OneDrive para la Empresa. Esta es la misma fecha de modificación que la que se muestra en el historial de versiones de la experiencia de usuario de SharePoint y OneDrive.|
|O365 modificado por||O365_modified_by|Modificado por desde SharePoint o OneDrive.|
|Otros custodios|DedupedCustodians|Deduped_custodians|Lista de custodios de documentos que son duplicados exactos (por correo electrónico, en función del contenido; para documentos, basados en hash).|
|Otros identificadores de archivo|DedupedFileIds|Deduped_file_IDs|Lista de identificadores de archivo de documentos que son duplicados exactos (para correo electrónico, en función del contenido; para documentos, basados en hash).|
|Otras rutas de acceso|Desdupedcompoundpath|Deduped_compound_path|Lista de rutas de acceso compuestas de documentos que son duplicados exactos (correo electrónico: basado en contenido, documentos: basado en hash).|
|Id. primario|ParentId|Parent_ID|Identificador del elemento primario del elemento.|
|ParentNode||Parent_node|El mensaje de correo electrónico anterior más cercano en el subproceso de correo electrónico.|
|Dominios de participantes|ParticipantDomains|Email_participant_domains|Lista de todos los dominios de participantes de un mensaje.|
|Participantes|Participantes|Email_participants|Lista de todos los participantes de un mensaje; por ejemplo, Sender, To, Cc, Bcc.|
|Identificador dinámico|PivotId|Pivot_ID|Identificador de una tabla dinámica.|
|Potencialmente con privilegios|Potencialmente con privilegios|Potentially_privileged|True si el modelo de detección de privilegios abogado-cliente considera el documento potencialmente con privilegios|
|Estado de procesamiento|ProcessingStatus|Error_code|Estado de procesamiento después de agregar el elemento a un conjunto de revisión.|
|Percentil de lectura|ReadPercentile||Lea el percentil del documento en función de la relevancia.|
|Cantidad.Recibida|Cantidad.Recibida|Email_date_received|Fecha y hora en que se recibió el correo electrónico en UTC.|
|Recuento de destinatarios||Recipient_count|Número de destinatarios del mensaje.|
|Dominios de destinatario|RecipientDomains|Email_recipient_domains|Lista de todos los dominios de destinatarios de un mensaje.|
|Destinatarios|Destinatarios|Email_recipients|Lista de todos los destinatarios de un mensaje (To, Cc, Bcc).|
|||Redacted_file_path|Ruta de acceso del archivo de reemplazo censurado en la exportación.|
|||Redacted_text_path|Ruta de acceso del reemplazo del archivo de texto redactado en la exportación. Solo para uso interno de Microsoft.|
|Etiqueta de relevancia Problema de caso 1||Relevance_tag_case_issue_1|Etiqueta de relevancia Problema 1 de relevancia.|
|Puntuación de relevancia|RelevanceScore||Puntuación de relevancia de un documento en función de la relevancia.|
|Etiqueta de relevancia|RelevanceTag||Puntuación de relevancia de un documento en función de la relevancia.|
|Id. de representante|RepresentativeId||Identificador numérico de cada conjunto de duplicados exactos.|
|||Row_number|Número de fila del elemento en el archivo de carga.|
|Remitente|Remitente|Email_sender|Campo Remitente (Desde) para los tipos de mensaje. El formato es **DisplayName \<SmtpAddress>**.|
|Remitente/autor|SenderAuthor||Campo calculado compuesto por el remitente o autor del elemento.|
|Dominio del remitente|SenderDomain|Email_sender_domain|Dominio del remitente.|
|Sent|Sent|Email_date_sent|Fecha de envío del mensaje.<br>Chats: fecha de inicio de la transcripción|
|Establecer orden: Inclusión primero|SetOrderInclusivesFirst|Set_order_inclusives_first|Campo de ordenación : correo electrónico y datos adjuntos: contracronológico; documents: dinamizar primero y, a continuación, descendiendo la puntuación de similitud.|
|Establecer id.||Set_ID|Los documentos de contenido similar (ND_set) o correo electrónico dentro del mismo subproceso de correo electrónico (Email_set) comparten el mismo Set_ID.|
|SimilarityPercent||Similarity_percent|Indica lo similar que es un documento a la dinámica del conjunto casi duplicado.|
|Tamaño de archivo nativo|Size|Native_size|Número de bytes del elemento nativo.|
|Subject|Subject|Email_subject|Asunto del mensaje.|
|Asunto o título|SubjectTitle||Campo calculado compuesto por el asunto o el título del elemento.|
|Etiquetas|Etiquetas|Etiquetas|Etiquetas aplicadas en un conjunto de revisión.|
|Nombre del canal|Canal|ChannelName|Este es el nombre del canal de Teams. Solo se aplica al contenido de Microsoft Teams.|
|Nombre del equipo|TeamName|TeamName|**Equipos:** Nombre del equipo<br>**Yammer:** Nombre de la comunidad|
|Lista de temas|ThemesList|Themes_list|Lista de temas calculada para el análisis.|
|Título|Título|Doc_title|Título de los metadatos del documento. Título de los metadatos del documento. Para el contenido de Teams y Yammer, este es el valor de la propiedad ConversationName.|
|To|To|Email_to|Campo para los tipos de mensaje. El formato es **DisplayName\<SmtpAddress>**|
|Único en el conjunto de correo electrónico|UniqueInEmailSet||**False** si hay un duplicado de los datos adjuntos en su conjunto de correo electrónico.|
|Id. de grupo de versiones||Version_Group_Id|Agrupa las distintas versiones del mismo documento.|
|VersionNumber||Version_Number|Número de versión de un documento recopilado de SharePoint o OneDrive para la Empresa. Este es el mismo número de versión que el que se muestra en el historial de versiones de la experiencia de usuario de SharePoint y OneDrive.|
|Se corrigió|WasRemediated|Was_Remediated|**True** si el elemento se corrigió; de lo contrario, **False**.|
|Word count|WordCount|Word_count|Número de palabras en el elemento.|
|||||

> [!NOTE]
> Para obtener más información sobre las propiedades que se pueden buscar al buscar Office 365 ubicaciones de contenido al recopilar datos para un caso de eDiscovery (Premium), vea Consultas de [palabras clave y condiciones de búsqueda para búsqueda de contenido](keyword-queries-and-search-conditions.md).
