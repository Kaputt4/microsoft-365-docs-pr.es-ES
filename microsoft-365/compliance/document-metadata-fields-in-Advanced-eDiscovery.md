---
title: Campos de metadatos de documento en eDiscovery avanzado
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: En este artículo se definen los campos de metadatos de los documentos de un conjunto de revisión en un caso Advanced eDiscovery en Microsoft 365.
ms.openlocfilehash: 7b8628973a8b07a3cd31e2b42df28c181e77e288
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2021
ms.locfileid: "52730503"
---
# <a name="document-metadata-fields-in-advanced-ediscovery"></a>Campos de metadatos de documento en eDiscovery avanzado

En la tabla siguiente se enumeran los campos de metadatos de los documentos de un conjunto de revisión en un caso Advanced eDiscovery. La tabla proporciona la siguiente información:

- **Nombre del** campo y Nombre del campo **mostrar:** el nombre del campo de metadatos y el nombre del campo que se muestra al ver los metadatos de archivo de un documento seleccionado en un conjunto de revisión. Algunos campos de metadatos no se incluyen al ver los metadatos de archivo de un documento. Estos campos se resaltan con un asterisco (*).

- **Nombre del campo que se puede buscar:** Nombre de la propiedad que puede buscar al ejecutar una [consulta de conjunto de revisión](review-set-search.md). Una celda en blanco significa que no puede buscar el campo en una consulta de conjunto de revisión.

- **Nombre del campo exportado:** Nombre del campo de metadatos que se incluye cuando se exportan documentos.  Una celda en blanco significa que el campo no se incluye con los metadatos exportados.

- **Descripción:** Una descripción del campo de metadatos.

> [!NOTE]
> El **campo Palabras clave de** la búsqueda del conjunto de [revisión](./review-set-search.md) usa lenguaje de consulta de palabras clave (KQL). Los campos **enumerados** en la columna **Nombre** de campo que se puede buscar se pueden usar en el campo Palabras clave en una búsqueda de conjunto de revisión para formar consultas complejas sin tener que usar el generador de consultas. Para obtener más información acerca de KQL, vea [Keyword Query Language syntax reference](/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference).

|**Nombre del campo** y **Nombre del campo para mostrar**|**Nombre del campo que se puede buscar**|**Nombre del campo exportado**|**Descripción**|
|:-----|:-----|:-----|:-----|
|Id. de contenido de datos adjuntos|AttachmentContentId||Identificador de contenido de datos adjuntos del elemento.|
|Puntuación de privilegios de cliente de abogado|AttorneyClientPrivilegeScore||Puntuación de contenido del modelo de privilegios abogado-cliente.|
|Autor|Autor|Doc_authors|Autor de los metadatos del documento.|
|BCC|Bcc|Email_bcc|Campo CCO para tipos de mensaje. Format es **DisplayName \<SMTPAddress>**.|
|CC|Cc|Email_cc|Campo Cc para tipos de mensaje. Format es **DisplayName \<SMTPAddress>**.|
|Etiquetas de cumplimiento|ComplianceLabels|Compliance_labels|[Etiquetas de](retention.md) retención aplicadas al contenido en Office 365.|
|Ruta compuesta|CompoundPath|Compound_path|Ruta de acceso legible humana que describe el origen del elemento.|
|Contenido*|Contenido||Texto extraído del elemento.|
|Cuerpo de la conversación|Cuerpo de la conversación||Cuerpo de conversación del elemento.|
|Tema de conversación|Tema de conversación||Tema de conversación del elemento.|
|Id. de conversación|ConversationId|Conversation_ID|Identificador de conversación del mensaje.|
|Índice de conversación||Conversation_index|Índice de conversación del mensaje.|
|Hora de pdf de conversación|ConversationPdfTime||Fecha en la que se creó la versión PDF de la conversación.|
|Tiempo de grabación de redacción de conversación|ConversationRedactionBurnTime||Fecha en la que se creó la versión PDF de la conversación para Chat.|
|||Converted_file_path|Ruta de acceso del archivo de exportación convertido. Solo para uso interno de Microsoft.|
|Fecha de documento creada|CreatedTime|Doc_date_created|Crear fecha a partir de metadatos del documento.|
|Custodio|Custodio|Custodio|Nombre del custodio al que se asoció el elemento.|
|Fecha|Fecha|Fecha|Date es un campo calculado que depende del tipo de archivo.<br /><br />Correo electrónico: fecha de envío<br />Datos adjuntos de correo electrónico: fecha de última modificación del documento; si no está disponible, la fecha de envío del elemento primario<br />Documentos incrustados: fecha de última modificación del documento; si no está disponible, la última fecha de modificación del elemento primario<br />Documentos SPO (incluye datos adjuntos modernos): SharePoint fecha de última modificación; si no está disponible, la fecha de última modificación de los documentos<br />Documentos no Office 365: Fecha de última modificación<br />Reuniones: fecha de inicio de la reunión<br />VoiceMail: fecha de envío<br />MI: Fecha de envío|
|Otras rutas de acceso|Dedupedcompoundpath|Deduped_compound_path|Lista de rutas de acceso compuestas de documentos que son duplicados exactos (correo electrónico: basado en contenido, documentos: basados en hash).|
|Otros custodios|DedupedCustodians|Deduped_custodians|Lista de custodios de documentos que son duplicados exactos (para correo electrónico, basado en contenido; para documentos, basados en hash).|
|Otros IDs de archivo|DedupedFileIds|Deduped_file_IDs|Lista de los nombres de archivo de documentos que son duplicados exactos (para correo electrónico, basado en contenido; para documentos, basados en hash).|
|Comentarios del documento|DocComments|Doc_comments|Comentarios de los metadatos del documento.|
|Empresa de documentos||Doc_company|Empresa de los metadatos del documento.|
|DocIndex*|||Índice de la familia. **-1** o **0** significa que es la raíz.|
|Palabras clave de documento||Doc_keywords|Palabras clave de los metadatos del documento.|
|Documento modificado por||Doc_modified_by|Fecha de última modificación de los metadatos del documento.|
|Revisión de documentos|Doc_Version|Doc_Version|Revisión de los metadatos del documento.|
|Asunto del documento||Doc_subject|Asunto de los metadatos del documento.|
|Plantilla de documento||Doc_template|Plantilla de los metadatos del documento.|
|DocLastSavedBy||Doc_last_saved_by|Nombre del usuario que guardó por última vez el documento.|
|Tema dominante|DominantTheme|Dominant_theme|Tema dominante calculado para análisis.|
|Subconjunto duplicado||Duplicate_subset|Id. de grupo para duplicados exactos.|
|EmailAction*||Email_action|Los valores **son None,** **Reply** o **Forward**; según la línea de asunto de un mensaje.|
|Recibo de entrega de correo electrónico solicitado||Email_delivery_receipt|Dirección de correo electrónico proporcionada en encabezados de Internet para el recibo de entrega.|
|Importance|EmailImportance|Email_importance|Importancia del mensaje: **0** - Low; **1** : Normal; **2** - High|
|EmailInternetHeaders|EmailInternetHeaders|Email_internet_headers|Conjunto completo de encabezados de correo electrónico del mensaje de correo electrónico|
|EmailLevel*||Email_level|Indica el nivel de un mensaje dentro del subproceso de correo electrónico al que pertenece; los datos adjuntos heredan el valor de su mensaje primario.|
|Id. de mensaje de correo electrónico||Email_message_ID|Identificador de mensaje de Internet del mensaje.|
|EmailReadReceiptRequested||Email_read_receipt|Dirección de correo electrónico proporcionada en encabezados de Internet para recibo de lectura.|
|Seguridad de correo electrónico|EmailSecurity|Email_security|Configuración de seguridad del mensaje: **0** - Ninguno; **1:** Firmado; **2** : cifrado; **3:** cifrado y firmado.|
|Confidencialidad del correo electrónico|EmailSensitivity|email_sensitivity|Configuración de confidencialidad del mensaje: **0** - Ninguno; **1** Personal; **2** - Privado; **3** - CompanyConfidential.|
|Conjunto de correo electrónico|EmailSet|Email_set|Id. de grupo para todos los mensajes del mismo conjunto de correo electrónico.|
|EmailThread*||Email_thread|Posición del mensaje dentro del conjunto de correo electrónico; consta de los IDs de nodo de la raíz al mensaje actual y se separan por puntos (.).|
|||Export_native_path|Ruta de acceso del archivo exportado.|
|Tipo de contenido extraído||Native_type|Tipo de contenido extraído, en forma de tipo mime; por ejemplo, **image/jpeg**|
|||Extracted_text_path|Ruta de acceso al archivo de texto extraído en la exportación.|
|ExtractedTextLength*||Extracted_text_length|Número de caracteres en el texto extraído.|
|FamilyDuplicateSet*||Family_duplicate_set|Identificador numérico para familias que son exactamente duplicados entre sí (mismo contenido y todos los mismos datos adjuntos).|
|Id. de familia|FamilyId|Family_ID|Id. de familia agrupa todos los elementos; para el correo electrónico, esto incluye el mensaje y todos los datos adjuntos; para documentos, esto incluye el documento y los elementos incrustados.|
|Tamaño de familia||Family_size|Número de documentos de la familia.|
|Clase File|FileClass|File_class|Para el contenido de SharePoint y OneDrive: **Document**; para el contenido de Exchange: **Correo electrónico** o **datos adjuntos**.|
|Id. de archivo|FileId|File_ID|Identificador de documento único dentro del caso.|
|Fecha de creación del sistema de archivos||File_system_date_created|Fecha de creación desde el sistema de archivos (solo se aplica a datos que no Office 365 datos).|
|Fecha de modificación del sistema de archivos||File_system_date_modified|Fecha de modificación del sistema de archivos (solo se aplica a datos que no Office 365 datos).|
|Tipo de archivo|FileType||Tipo de archivo del elemento basado en la extensión de archivo.|
|Id. de grupo|GroupID||Id. de grupo para contenido agrupado.|
|Tiene datos adjuntos|HasAttachment|Email_has_attachment|Indica si el mensaje tiene datos adjuntos.|
|Tiene abogado|HasAttorney||**True** cuando al menos uno de los participantes se encuentra en la lista de abogados; de lo contrario, el valor es **False**.|
|HasText*||Has_text|Indica si el elemento tiene texto; los valores posibles **son True** y **False**.|
|Identificador inmutable||Immutable_ID|Este identificador se usa para identificar de forma única un documento dentro de un conjunto de revisión. Este campo no se puede usar en una búsqueda de conjunto de revisión y el identificador no se puede usar para tener acceso a un documento en su ubicación nativa.|
|Tipo inclusivo|InclusiveType|Inclusive_type|Tipo inclusivo calculado para análisis: **0:** no inclusivo; **1** : inclusive; **2** : menos inclusivo; **3:** copia inclusiva.|
|En Reply To Id||In_reply_to_ID|En respuesta a Id. del mensaje.|
|InputFileExtension||Original_file_extension|La extensión de archivo original del archivo.|
|InputFileID||Input_file_ID|El identificador de archivo del elemento de nivel superior del conjunto de revisión. Para datos adjuntos, este identificador será el identificador del elemento primario. Esto se puede usar para agrupar familias.|
|Es datos adjuntos modernos| IsModernAttachment|  |Este archivo es un archivo adjunto moderno o un archivo vinculado.|
|Es de la versión del documento | IsFromDocumentVersion |  |El documento actual es de una versión diferente de otro documento.|
|¿Son datos adjuntos de correo electrónico? | IsEmailAttachment|  |Este elemento es de un archivo adjunto de correo electrónico que se muestra como un elemento adjunto al mensaje.|
|Es datos adjuntos en línea| IsInlineAttachment|  |Se adjuntaba en línea y se muestra en el cuerpo del mensaje.|
|Es representativo|IsRepresentative|Is_representative|Un documento de cada conjunto de duplicados exactos se marca como representativo.|
|Clase Item|ItemClass|Item_class|Clase de elemento suministrada por el servidor exchange; por ejemplo, **IPM. Nota**|
|Última modificación|LastModifiedDate|Doc_date_modified|Fecha de última modificación de los metadatos del documento.|
|Id. de carga|LoadId|Load_ID|Identificador del conjunto de carga en el que se agregó el elemento a un conjunto de revisión.|
|Ubicación|Ubicación|Ubicación|Cadena que indica el tipo de ubicación de la que se han origen los documentos.<br /><br />**Datos importados:** datos no Office 365 datos<br />**Teams:** Microsoft Teams<br />**Exchange:** Exchange buzones de correo<br />**SharePoint:** SharePoint sitios<br />**OneDrive:** OneDrive cuentas|
|Nombre de ubicación|LocationName|Location_name|Cadena que identifica el origen del elemento. Para Exchange, esta será la dirección SMTP del buzón; para SharePoint y OneDrive, la dirección URL de la colección de sitios.|
|||Marked_as_pivot|Este archivo es el elemento dinámico de un conjunto casi duplicado.|
|Marcado como representante|MarkAsRepresentative||Un documento de cada conjunto de duplicados exactos se marca como representantes.|
|Fecha de finalización de la reunión|MeetingEndDate|Meeting_end_date|Fecha de finalización de la reunión para reuniones.|
|Fecha de inicio de la reunión|MeetingStartDate|Meeting_start_date|Fecha de inicio de la reunión para reuniones.|
|Tipo de mensaje|MessageKind|Message_kind|Tipo de mensaje que se debe buscar. Valores **<br /> <br /> <br /> posibles: contacts docs <br /> email <br /> externaldata <br /> faxes im <br /> <br /> journals <br /> <br /> meetings microsoftteams** (devuelve elementos de chats, reuniones y llamadas en Microsoft Teams) notas publicaciones **<br /> <br /> <br /> rssfeeds <br /> tasks <br /> voicemail**| 
|Identificador principal de datos adjuntos modernos||ModernAttachment_ParentId|El identificador inmutable del elemento primario del documento.|
|Extensión nativa|NativeExtension|Native_extension|Extensión nativa del elemento.|
|Nombre de archivo nativo|NativeFileName|Native_file_name|Nombre de archivo nativo del elemento.|
|NativeMD5||Native_MD5|Hash MD5 (valor hash de 128 bits) de la secuencia de archivos.|
|NativeSHA256||Native_SHA_256|Hash SHA256 (valor hash de 256 bits) de la secuencia de archivos.|
|Ordenación de ND/ET: excluir datos adjuntos|NdEtSortExclAttach|ND_ET_sort_excl_attach|Concatenación del conjunto de subprocesos de correo electrónico (ET) y del conjunto Casi duplicado (ND). Este campo se usa para una ordenación eficaz en el momento de la revisión. Una **D** tiene el prefijo de conjuntos de ND y **una E** tiene el prefijo et sets.|
|Ordenación de ND/ET: incluir datos adjuntos|NdEtSortInclAttach|ND_ET_sort_incl_attach|Concatenación de un conjunto de subprocesos de correo electrónico (ET) y un conjunto casi duplicado (ND). Este campo se usa para una ordenación eficaz en el momento de la revisión. Una **D** tiene el prefijo de conjuntos de ND y **una E** tiene el prefijo et sets. Cada elemento de correo electrónico de un conjunto de ET va seguido de sus datos adjuntos adecuados.|
|Autores de O365||O365_authors|Autor de SharePoint.|
|O365 creado por||O365_created_by|Creado por desde SharePoint.|
|Fecha de creación de O365||O365_date_created|Fecha de creación a partir SharePoint.|
|Fecha de modificación de O365||O365_date_modified|Fecha de última modificación de SharePoint.|
|O365 modificado por||O365_modified_by|Modificado por desde SharePoint.|
|Id. principal|ParentId|Parent_ID|Id. del elemento primario.|
|ParentNode||Parent_node|El mensaje de correo electrónico anterior más cercano en el subproceso de correo electrónico.|
|Dominios de participante|ParticipantDomains|Email_participant_domains|Lista de todos los dominios de participantes de un mensaje.|
|Participantes|Participantes|Email_participants|Lista de todos los participantes de un mensaje; por ejemplo, Sender, To, Cc, CCO.|
|Identificador dinámico|PivotId|Pivot_ID|El identificador de un pivot.|
|Potencialmente con privilegios|PotentiallyPrivileged|Potentially_privileged|True si el modelo de detección de privilegios abogado-cliente considera que el documento puede tener privilegios|
|Estado de procesamiento|ProcessingStatus|Error_code|Estado de procesamiento después de agregar el elemento a un conjunto de revisión.|
|Percentil de lectura|ReadPercentile||Percentil de lectura para el documento basado en relevancia.|
|Cantidad.Recibida|Cantidad.Recibida|Email_date_received|La fecha y hora en que se recibió el correo electrónico en UTC.|
|Recuento de destinatarios||Recipient_count|Número de destinatarios en el mensaje.|
|Dominios de destinatarios|RecipientDomains|Email_recipient_domains|Lista de todos los dominios de destinatarios de un mensaje.|
|Destinatarios|Destinatarios|Email_recipients|Lista de todos los destinatarios de un mensaje (Para, Cc, CCO).|
|||Redacted_file_path|Ruta de acceso del archivo de reemplazo redactada en la exportación.|
|||Redacted_text_path|Ruta de acceso del reemplazo del archivo de texto redactada en la exportación. Solo para uso interno de Microsoft.|
|Etiqueta de relevancia Asunto número 1||Relevance_tag_case_issue_1|Etiqueta relevancia Asunto número 1 de Relevancia.|
|Puntuación de relevancia|RelevanceScore||Puntuación de relevancia de un documento basada en relevancia.|
|Etiqueta relevancia|RelevanceTag||Puntuación de relevancia de un documento basada en relevancia.|
|Id. de representante|RepresentativeId||Identificador numérico de cada conjunto de duplicados exactos.|
|||Row_number|Número de fila del elemento en el archivo de carga.|
|Remitente|Remitente|Email_sender|Campo Remitente (De) para tipos de mensaje. Format es **DisplayName \<SmtpAddress>**.|
|Sender/Author|SenderAuthor||Campo calculado formado por el remitente o autor del elemento.|
|Dominio del remitente|SenderDomain|Email_sender_domain|Dominio del remitente.|
|Sent|Sent|Email_date_sent|Fecha de envío del mensaje.|
|Establecer orden: Primero inclusivo|SetOrderInclusivesFirst|Set_order_inclusives_first|Campo de ordenación: correo electrónico y datos adjuntos: contra cronológicos; documents: pivot first then by descending similarity score.|
|SimilarityPercent||Similarity_percent|Indica lo parecido que es un documento al pivote del conjunto casi duplicado.|
|Tamaño de archivo nativo|Size|Native_size|Número de bytes del elemento nativo.|
|Subject|Subject|Email_subject|Asunto del mensaje.|
|Asunto/Título|SubjectTitle||Campo calculado formado por el asunto o el título del elemento.|
|Etiquetas|Etiquetas|Etiquetas|Etiquetas aplicadas en un conjunto de revisión.|
|Lista de temas|ThemesList|Themes_list|Lista de temas calculada para análisis.|
|Título|Título|Doc_title|Título de los metadatos del documento.|
|To|To|Email_to|Para el campo para los tipos de mensaje. Format es **DisplayName \<SmtpAddress>**|
|Único en el conjunto de correo electrónico|UniqueInEmailSet||**False** si hay un duplicado de los datos adjuntos en su conjunto de correo electrónico.|
|Id. de grupo de versión||Version_Group_Id|Agrupa las distintas versiones del mismo documento.|
|Se ha corregido|WasRemediated|Was_Remediated|**True** si el elemento se ha corregido, de lo contrario **Es False**.|
|Word count|WordCount|Word_count|Número de palabras en el elemento.|
|||||

> [!NOTE]
> Para obtener más información acerca de las propiedades que se pueden buscar al buscar en ubicaciones de contenido Office 365 cuando se recopilan datos para un caso Advanced eDiscovery, vea [Consultas de](keyword-queries-and-search-conditions.md)palabras clave y condiciones de búsqueda para búsqueda de contenido .
