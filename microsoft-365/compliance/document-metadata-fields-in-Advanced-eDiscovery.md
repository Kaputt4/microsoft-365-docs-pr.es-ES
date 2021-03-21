---
title: Campos de metadatos de documentos en exhibición de documentos electrónicos avanzada
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
description: En este artículo se definen los campos de metadatos de los documentos de un conjunto de revisión en un caso de exhibición de documentos electrónicos avanzada en Microsoft 365.
ms.openlocfilehash: 3f8ac33e3f11557843b590ed2a9f7d903e33f5ea
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922064"
---
# <a name="document-metadata-fields-in-advanced-ediscovery"></a>Campos de metadatos de documentos en exhibición de documentos electrónicos avanzada

En la tabla siguiente se enumeran los campos de metadatos de los documentos de un conjunto de revisión en un caso de exhibición de documentos electrónicos avanzada. La tabla proporciona la siguiente información:

- **Nombre del** campo y Nombre del campo **mostrar:** el nombre del campo de metadatos y el nombre del campo que se muestra al ver los metadatos de archivo de un documento seleccionado en un conjunto de revisión. Algunos campos de metadatos no se incluyen al ver los metadatos de archivo de un documento. Estos campos se resaltan con un asterisco (*).

- **Nombre del campo que se puede buscar:** Nombre de la propiedad que puede buscar al ejecutar una [consulta de conjunto de revisión](review-set-search.md). Una celda en blanco significa que no puede buscar el campo en una consulta de conjunto de revisión.

- **Nombre del campo exportado:** Nombre del campo de metadatos que se incluye cuando se exportan documentos.  Una celda en blanco significa que el campo no se incluye con los metadatos exportados.

- **Descripción:** Una descripción del campo de metadatos.

> [!NOTE]
> El **campo Palabras clave de** la búsqueda del conjunto de [revisión](./review-set-search.md) usa lenguaje de consulta de palabras clave (KQL). Los campos **enumerados** en la columna **Nombre** de campo que se puede buscar se pueden usar en el campo Palabras clave en una búsqueda de conjunto de revisión para formar consultas complejas sin tener que usar el generador de consultas. Para obtener más información acerca de KQL, vea [Keyword Query Language syntax reference](/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference).

|**Nombre del campo** y **Nombre del campo para mostrar**|**Nombre del campo que se puede buscar**|**Nombre del campo exportado**|**Descripción**|
|:-----|:-----|:-----|:-----|
|Id. de contenido de datos adjuntos|AttachmentContentId||Identificador de contenido de datos adjuntos del elemento.|
|Nombres de datos adjuntos|AttachmentNames|Attachment_Names|Lista de nombres de datos adjuntos.|
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
|Fecha de documento creada|CreatedTime|Doc_date_created|Crear fecha a partir de metadatos del documento.|
|Custodio|Custodio|Custodio|Nombre del custodio al que se asoció el elemento.|
|Fecha|Fecha|Fecha|Date es un campo calculado que depende del tipo de archivo.<br /><br />Correo electrónico: fecha de envío<br />Datos adjuntos de correo electrónico: fecha de última modificación del documento; si no está disponible, la fecha de envío del elemento primario<br />Documentos incrustados: fecha de última modificación del documento; si no está disponible, la última fecha de modificación del elemento primario<br />Documentos SPO (incluye datos adjuntos modernos): Fecha de última modificación de SharePoint; si no está disponible, la fecha de última modificación de los documentos<br />Documentos que no son de Office 365: Fecha de última modificación<br />Reuniones: fecha de inicio de la reunión<br />VoiceMail: fecha de envío<br />MI: Fecha de envío|
|Otras rutas de acceso|Dedupedcompoundpath|Deduped_compound_path|Lista de rutas de acceso compuestas de documentos que son duplicados exactos (correo electrónico: basado en contenido, documentos: basados en hash).|
|Otros custodios|DedupedCustodians|Deduped_custodians|Lista de custodios de documentos que son duplicados exactos (para correo electrónico, basado en contenido; para documentos, basados en hash).|
|Otros IDs de archivo|DedupedFileIds|Deduped_file_IDs|Lista de los nombres de archivo de documentos que son duplicados exactos (para correo electrónico, basado en contenido; para documentos, basados en hash).|
|Comentarios del documento|DocComments|Doc_comments|Comentarios de los metadatos del documento.|
|Empresa de documentos||Doc_company|Empresa de los metadatos del documento.|
|DocIndex*|||Índice de la familia. **-1** o **0** significa que es la raíz.|
|Palabras clave de documento||Doc_keywords|Palabras clave de los metadatos del documento.|
|Documento modificado por||Doc_modified_by|Fecha de última modificación de los metadatos del documento.|
|Revisión de documentos||Doc_revision|Revisión de los metadatos del documento.|
|Asunto del documento||Doc_subject|Asunto de los metadatos del documento.|
|Plantilla de documento||Doc_template|Plantilla de los metadatos del documento.|
|Tema dominante|DominantTheme|Dominant_theme|Tema dominante calculado para análisis.|
|Subconjunto duplicado||Duplicate_subset|Id. de grupo para duplicados exactos.|
|EmailAction*||Email_action|Los valores **son None,** **Reply** o **Forward**; según la línea de asunto de un mensaje.|
|Recibo de entrega de correo electrónico||Email_delivery_receipt|Dirección de correo electrónico proporcionada en encabezados de Internet para el recibo de entrega.|
|Importance|EmailImportance|Email_importance|Importancia del mensaje: **0** - Low; **1** : Normal; **2** - High|
|EmailLevel*||Email_level|Indica el nivel de un mensaje dentro del subproceso de correo electrónico al que pertenece; los datos adjuntos heredan el valor de su mensaje primario.|
|Id. de mensaje de correo electrónico||Email_message_ID|Identificador de mensaje de Internet del mensaje.|
|EmailReadReceipt*||Email_read_receipt|Dirección de correo electrónico proporcionada en encabezados de Internet para recibo de lectura.|
|Seguridad de correo electrónico|EmailSecurity|Email_security|Configuración de seguridad del mensaje: **0** - Ninguno; **1:** Firmado; **2** : cifrado; **3:** cifrado y firmado.|
|Confidencialidad del correo electrónico|EmailSensitivity|email_sensitivity|Configuración de confidencialidad del mensaje: **0** - Ninguno; **1** Personal; **2** - Privado; **3** - CompanyConfidential.|
|Conjunto de correo electrónico|EmailSet|Email_set|Id. de grupo para todos los mensajes del mismo conjunto de correo electrónico.|
|EmailThread*||Email_thread|Posición del mensaje dentro del conjunto de correo electrónico; consta de los IDs de nodo de la raíz al mensaje actual y se separan por puntos (.).|
|Tipo de contenido extraído||Extracted_content_type|Tipo de contenido extraído, en forma de tipo mime; por ejemplo, **image/jpeg**|
|ExtractedTextLength*||Extracted_text_length|Número de caracteres en el texto extraído.|
|Puntuación de relevancia familiar Caso número 1*||Family_relevance_score_case_issue_1|Puntuación de relevancia familiar Caso número 1 de Relevancia.|
|FamilyDuplicateSet*||Family_duplicate_set|Identificador numérico para familias que son exactamente duplicados entre sí (mismo contenido y todos los mismos datos adjuntos).|
|Id. de familia|FamilyId|Family_ID|Id. de familia agrupa todos los elementos; para el correo electrónico, esto incluye el mensaje y todos los datos adjuntos; para documentos, esto incluye el documento y los elementos incrustados.|
|Tamaño de familia||Family_size|Número de documentos de la familia.|
|Puntuación de relevancia de archivo Problema de caso 1*||File_relevance_score_case_issue_1|Puntuación de relevancia de archivo Caso número 1 de Relevancia.|
|Clase File|FileClass|File_class|Para el contenido de SharePoint y OneDrive: **Document**; para el contenido de Exchange: **Correo electrónico** o **datos adjuntos**.|
|Id. de archivo|FileId|File_ID|Identificador de documento único dentro del caso.|
|Fecha de creación del sistema de archivos||File_system_date_created|Fecha de creación desde el sistema de archivos (solo se aplica a datos que no son de Office 365).|
|Fecha de modificación del sistema de archivos||File_system_date_modified|Fecha de modificación del sistema de archivos (solo se aplica a datos que no son de Office 365).|
|Tipo de archivo|FileType||Tipo de archivo del elemento basado en la extensión de archivo.|
|Id. de grupo| GroupID|  |Id. de grupo para contenido agrupado.|
|Tiene datos adjuntos|HasAttachment|Email_has_attachment|Indica si el mensaje tiene datos adjuntos.|
|Tiene abogado|HasAttorney||**True** cuando al menos uno de los participantes se encuentra en la lista de abogados; de lo contrario, el valor es **False**.|
|HasText*||Has_text|Indica si el elemento tiene texto; los valores posibles **son True** y **False**.|
|Identificador inmutable||Immutable_ID|Este identificador se usa para identificar de forma única un documento dentro de un conjunto de revisión. Este campo no se puede usar en una búsqueda de conjunto de revisión y el identificador no se puede usar para tener acceso a un documento en su ubicación nativa.|
|Tipo inclusivo|InclusiveType|Inclusive_type|Tipo inclusivo calculado para análisis: **0:** no inclusivo; **1** : inclusive; **2** : menos inclusivo; **3:** copia inclusiva.|
|En Reply To Id||In_reply_to_ID|En respuesta a Id. del mensaje.|
|Es datos adjuntos modernos| IsModernAttachment|  |Este archivo es un archivo adjunto moderno o un archivo vinculado.|
|Es de la versión del documento | IsFromDocumentVersion |  |El documento actual es de una versión diferente de otro documento.|
|¿Son datos adjuntos de correo electrónico? | IsEmailAttachment|  |Este elemento es de un archivo adjunto de correo electrónico que se muestra como un elemento adjunto al mensaje.|
|Es datos adjuntos en línea| IsInlineAttachment|  |Se adjuntaba en línea y se muestra en el cuerpo del mensaje.|
|Es representativo|IsRepresentative|Is_representative|Un documento de cada conjunto de duplicados exactos se marca como representativo.|
|Clase Item|ItemClass|Item_class|Clase de elemento suministrada por el servidor exchange; por ejemplo, **IPM. Nota**|
|Última modificación|LastModifiedDate|Doc_date_modified|Fecha de última modificación de los metadatos del documento.|
|Id. de carga|LoadId|Load_ID|Identificador del conjunto de carga en el que se agregó el elemento a un conjunto de revisión.|
|Ubicación|Ubicación|Ubicación|Cadena que indica el tipo de ubicación de la que se han origen los documentos.<br /><br />**Datos importados:** datos que no son de Office 365<br />**Teams:** Microsoft Teams<br />**Exchange:** buzones de Exchange<br />**SharePoint:** sitios de SharePoint<br />**OneDrive:** cuentas de OneDrive|
|Nombre de ubicación|LocationName|Location_name|Cadena que identifica el origen del elemento. Para Exchange, esta será la dirección SMTP del buzón; para SharePoint y OneDrive, la dirección URL de la colección de sitios.|
|Marcado como representante|MarkAsRepresentative||Un documento de cada conjunto de duplicados exactos se marca como representantes.|
|Marcado como problema case etiquetado previamente 1*||Marked_as_pre_tagged_Case_issue_1|Marcado como número de caso 1 etiquetado previamente desde Relevancia.|
|Marcado como seed Case issue 1*||Marked_as_seed_Case_issue_1|Marcado como seed Case issue 1 from Relevance.|
|Fecha de finalización de la reunión|MeetingEndDate|Meeting_end_date|Fecha de finalización de la reunión para reuniones.|
|Fecha de inicio de la reunión|MeetingStartDate|Meeting_start_date|Fecha de inicio de la reunión para reuniones.|
|Tipo de mensaje|MessageKind|Message_kind|Tipo de mensaje que se debe buscar. Valores posibles: los documentos de contactos envía faxes externos de datos externos a reuniones de **<br /> <br /> <br /> <br /> <br /> <br /> <br /> <br /> <br /> <br /> microsoftteams** (devuelve elementos de chats, reuniones y llamadas en Microsoft Teams) notas publicaciones **<br /> <br /> <br /> rssfeeds <br /> tasks <br /> voicemail**| 
|Extensión nativa|NativeExtension|Native_extension|Extensión nativa del elemento.|
|Nombre de archivo nativo|NativeFileName|Native_file_name|Nombre de archivo nativo del elemento.|
|NativeMD5||Native_MD5|Hash MD5 (valor hash de 128 bits) de la secuencia de archivos.|
|NativeSHA256||Native_SHA_256|Hash SHA256 (valor hash de 256 bits) de la secuencia de archivos.|
|Ordenación de ND/ET: excluir datos adjuntos|NdEtSortExclAttach|ND_ET_sort_excl_attach|Concatenación del conjunto de subprocesos de correo electrónico (ET) y del conjunto Casi duplicado (ND). Este campo se usa para una ordenación eficaz en el momento de la revisión. Una **D** tiene el prefijo de conjuntos de ND y **una E** tiene el prefijo et sets.|
|Ordenación de ND/ET: incluir datos adjuntos|NdEtSortInclAttach|ND_ET_sort_incl_attach|Concatenación de un conjunto de subprocesos de correo electrónico (ET) y un conjunto casi duplicado (ND). Este campo se usa para una ordenación eficaz en el momento de la revisión. Una **D** tiene el prefijo de conjuntos de ND y **una E** tiene el prefijo et sets. Cada elemento de correo electrónico de un conjunto de ET va seguido de sus datos adjuntos adecuados.|
|Puntuación de relevancia normalizada Número de caso 1||Normalized_relevance_score_case_issue_1|Puntuación de relevancia normalizada Caso número 1 de Relevancia.|
|Autores de O365||O365_authors|Autor de SharePoint.|
|O365 creado por||O365_created_by|Creado por desde SharePoint.|
|Fecha de creación de O365||O365_date_created|Fecha de creación desde SharePoint.|
|Fecha de modificación de O365||O365_date_modified|Fecha de última modificación de SharePoint.|
|O365 modificado por||O365_modified_by|Modificado por desde SharePoint.|
|Id. principal|ParentId|Parent_ID|Id. del elemento primario.|
|ParentNode||Parent_node|El mensaje de correo electrónico anterior más cercano en el subproceso de correo electrónico.|
|Ruta de acceso principal|ParentPath|Parent_path|Ruta de acceso compuesta del elemento primario directo del elemento.|
|Dominios de participante|ParticipantDomains|Email_participant_domains|Lista de todos los dominios de participantes de un mensaje.|
|Participantes|Participantes|Email_participants|Lista de todos los participantes de un mensaje; por ejemplo, Sender, To, Cc, CCO.|
|Identificador dinámico|PivotId|Pivot_ID|El identificador de un pivot.|
|Potencialmente con privilegios|PotentiallyPrivileged|Potentially_privileged|True si el modelo de detección de privilegios abogado-cliente considera que el documento puede tener privilegios|
|Estado de procesamiento|ProcessingStatus|Error_code|Estado de procesamiento después de agregar el elemento a un conjunto de revisión.|
|Porcentaje de lectura del problema de caso 1||Read_percent_Case_issue_1|Leer porcentaje De caso número 1 de Relevancia.|
|Percentil de lectura|ReadPercentile||Percentil de lectura para el documento basado en relevancia.|
|Recuento de destinatarios||Recipient_count|Número de destinatarios en el mensaje.|
|Dominios de destinatarios|RecipientDomains|Email_recipient_domains|Lista de todos los dominios de destinatarios de un mensaje.|
|Destinatarios|Destinatarios|Email_recipients|Lista de todos los destinatarios de un mensaje (Para, Cc, CCO).|
|Grupo de carga de relevancia Problema de caso 1||Relevance_load_group_case_issue_1|Grupo de carga de relevancia Caso número 1 de Relevancia.|
|Descripción del estado de relevancia Caso número 1||Relevance_status_description_Case_issue_1|Descripción del estado de relevancia Caso número 1 de Relevancia.|
|Etiqueta de relevancia Asunto número 1||Relevance_tag_case_issue_1|Etiqueta relevancia Asunto número 1 de Relevancia.|
|Comentario de relevancia||Relevance_comment|Campo Comentario de Relevancia.|
|Puntuación de relevancia|RelevanceScore||Puntuación de relevancia de un documento basada en relevancia.|
|Etiqueta relevancia|RelevanceTag||Puntuación de relevancia de un documento basada en relevancia.|
|Id. de representante|RepresentativeId||Identificador numérico de cada conjunto de duplicados exactos.|
|Remitente|Remitente|Email_sender|Campo Remitente (De) para tipos de mensaje. Format es **DisplayName \<SmtpAddress>**.|
|Sender/Author|SenderAuthor||Campo calculado formado por el remitente o autor del elemento.|
|Dominio del remitente|SenderDomain|Email_sender_domain|Dominio del remitente.|
|Sent|Sent|Email_date_sent|Fecha de envío del mensaje.|
|Establecer orden: Primero inclusivo|SetOrderInclusivesFirst|Set_order_inclusives_first|Campo de ordenación: correo electrónico y datos adjuntos: contra cronológicos; documents: pivot first then by descending similarity score.|
|SimilarityPercent||Similarity_percent|Indica lo parecido que es un documento al pivote del conjunto casi duplicado.|
|Tamaño de archivo nativo|Size|Native_size|Número de bytes del elemento nativo.|
|Subject|Subject|Email_subject|Asunto del mensaje.|
|Asunto/Título|SubjectTitle||Campo calculado formado por el asunto o el título del elemento.|
|Etiquetado por el problema de caso 1||Tagged_by_Case_issue_1|Usuario que etiquetó este documento para el número de caso 1 en Relevancia.|
|Etiquetas|Etiquetas|Etiquetas|Etiquetas aplicadas en un conjunto de revisión.|
|Lista de temas|ThemesList|Themes_list|Lista de temas calculada para análisis.|
|Título|Título|Doc_title|Título de los metadatos del documento.|
|To|To|Email_to|Para el campo para los tipos de mensaje. Format es **DisplayName \<SmtpAddress>**|
|Único en el conjunto de correo electrónico|UniqueInEmailSet||**False** si hay un duplicado de los datos adjuntos en su conjunto de correo electrónico.|
|Se ha corregido|WasRemediated|Was_Remediated|**True** si el elemento se ha corregido, de lo contrario **Es False**.|
|Word count|WordCount|Word_count|Número de palabras en el elemento.|
|||||

> [!NOTE]
> Para obtener más información acerca de las propiedades que se pueden buscar al buscar en ubicaciones de contenido de Office 365 al recopilar datos para un caso de exhibición de documentos electrónicos avanzada, vea [Consultas de](keyword-queries-and-search-conditions.md)palabras clave y condiciones de búsqueda para búsqueda de contenido.