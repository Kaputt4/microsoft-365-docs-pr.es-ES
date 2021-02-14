---
title: Campos de metadatos de documentos en eDiscovery avanzado
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
description: En este artículo se definen los campos de metadatos de los documentos de un conjunto de revisión en un caso de eDiscovery avanzado en Microsoft 365.
ms.openlocfilehash: 2bf9773f6c36e53231bb577c30e9900bf3e24df7
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358448"
---
# <a name="document-metadata-fields-in-advanced-ediscovery"></a>Campos de metadatos de documentos en eDiscovery avanzado

En la tabla siguiente se enumeran los campos de metadatos de los documentos de un conjunto de revisión en un caso de eDiscovery avanzado. La tabla proporciona la siguiente información:

- **Nombre del** campo y nombre del campo para **mostrar:** el nombre del campo de metadatos y el nombre del campo que se muestra al ver los metadatos de archivo de un documento seleccionado en un conjunto de revisión. Algunos campos de metadatos no se incluyen al ver los metadatos de archivo de un documento. Estos campos se resaltan con un asterisco (*).

- **Nombre de campo que permite búsquedas:** El nombre de la propiedad que puede buscar al ejecutar una consulta [de conjunto de revisión.](review-set-search.md) Una celda en blanco significa que no se puede buscar el campo en una consulta de conjunto de revisión.

- **Nombre del campo exportado:** Nombre del campo de metadatos que se incluye al exportar documentos.  Una celda en blanco significa que el campo no se incluye con los metadatos exportados.

- **Descripción:** Descripción del campo de metadatos.

> [!NOTE]
> El **campo Palabras clave de** la búsqueda del conjunto de [revisión](https://docs.microsoft.com/microsoft-365/compliance/review-set-search) usa el lenguaje de consulta de palabras clave (KQL). Los campos enumerados en la columna **Nombre** de campo que permite **búsquedas** se pueden usar en el campo Palabras clave en una búsqueda de conjunto de revisión para formar consultas complejas sin tener que usar el generador de consultas. Para obtener más información acerca de KQL, vea referencia de sintaxis [del lenguaje de consulta de palabras clave.](https://go.microsoft.com/fwlink/?LinkId=269603)

|**Nombre del campo** y **nombre del campo para mostrar**|**Nombre de campo que permite búsquedas**|**Nombre del campo exportado**|**Descripción**|
|:-----|:-----|:-----|:-----|
|Id. de contenido de datos adjuntos|AttachmentContentId||Identificador de contenido de datos adjuntos del elemento.|
|Nombres de datos adjuntos|AttachmentNames|Attachment_Names|Lista de nombres de datos adjuntos.|
|Puntuación de privilegios de cliente abogado|AttorneyClientPrivilegeScore||Puntuación de contenido del modelo de privilegios abogado-cliente.|
|Autor|Autor|Doc_authors|Autor de los metadatos del documento.|
|BCC|Bcc|Email_bcc|Campo CCO para tipos de mensaje. El formato **es DisplayName \<SMTPAddress>**.|
|CC|Cc|Email_cc|Campo CC para tipos de mensaje. El formato **es DisplayName \<SMTPAddress>**.|
|Etiquetas de cumplimiento|ComplianceLabels|Compliance_labels|[Etiquetas de](retention.md) retención aplicadas al contenido de Office 365.|
|Ruta compuesta|CompoundPath|Compound_path|Ruta de acceso legible para personas que describe el origen del elemento.|
|Contenido*|Contenido||Texto extraído del elemento.|
|Cuerpo de la conversación|Cuerpo de la conversación||Cuerpo de conversación del elemento.|
|Tema de conversación|Tema de conversación||Tema de conversación del elemento.|
|Id. de conversación|ConversationId|Conversation_ID|Identificador de conversación del mensaje.|
|Índice de conversación||Conversation_index|Índice de conversación del mensaje.|
|Hora de pdf de conversación|ConversationPdfTime||Fecha en la que se creó la versión EN PDF de la conversación.|
|Hora de grabación de la redacción de la conversación|ConversationRedactionBurnTime||Fecha en la que se creó la versión EN PDF de la conversación para Chat.|
|Fecha de creación del documento|CreatedTime|Doc_date_created|Crear fecha a partir de metadatos del documento.|
|Custodian|Custodian|Custodian|Nombre del administrador con el que se asoció el elemento.|
|Fecha|Fecha|Fecha|Date es un campo calculado que depende del tipo de archivo.<br /><br />Correo electrónico: fecha de envío<br />Datos adjuntos de correo electrónico: fecha de la última modificación del documento; si no está disponible, la fecha de envío del elemento primario<br />Documentos incrustados: fecha de la última modificación del documento; si no está disponible, la fecha de la última modificación del elemento primario<br />Documentos de SPO (incluye datos adjuntos modernos): Fecha de última modificación de SharePoint; si no está disponible, la fecha de la última modificación de los documentos<br />Documentos que no son de Office 365: Fecha de la última modificación<br />Reuniones: fecha de inicio de la reunión<br />VoiceMail: Fecha de envío<br />MI: Fecha de envío|
|Otras rutas de acceso|Dedupedcompoundpath|Deduped_compound_path|Lista de rutas compuestas de documentos que son duplicados exactos (correo electrónico: basado en contenido, documentos: basados en hash).|
|Otros administradores|DedupedCustodians|Deduped_custodians|Lista de administradores de documentos que son duplicados exactos (para correo electrónico, basado en contenido; para documentos, basados en hash).|
|Otros iDs de archivo|DedupedFileIds|Deduped_file_IDs|Lista de los nombres de archivo de los documentos que son duplicados exactos (para el correo electrónico, en función del contenido; para los documentos, basados en hash).|
|Comentarios del documento|DocComments|Doc_comments|Comentarios de los metadatos del documento.|
|Compañía de documentos||Doc_company|Compañía a partir de los metadatos del documento.|
|DocIndex*|||Índice de la familia. **-1** o **0** significa que es la raíz.|
|Palabras clave de documento||Doc_keywords|Palabras clave de los metadatos del documento.|
|Documento modificado por||Doc_modified_by|Fecha de la última modificación de los metadatos del documento.|
|Revisión del documento||Doc_revision|Revisión de los metadatos del documento.|
|Asunto del documento||Doc_subject|Asunto de los metadatos del documento.|
|Plantilla de documento||Doc_template|Plantilla de los metadatos del documento.|
|Tema dominante|DominantTheme|Dominant_theme|Tema dominante calculado para el análisis.|
|Subconjunto duplicado||Duplicate_subset|Id. de grupo de duplicados exactos.|
|EmailAction*||Email_action|Los valores **son None**, **Reply** o **Forward**; en función de la línea de asunto de un mensaje.|
|Confirmación de entrega de correo electrónico||Email_delivery_receipt|Dirección de correo electrónico proporcionada en los encabezados de Internet para la recepción de entrega.|
|Importance|EmailImportance|Email_importance|Importancia del mensaje: **0** - Baja; **1** - Normal; **2** - Alta|
|EmailLevel*||Email_level|Indica el nivel de un mensaje dentro del subproceso de correo electrónico al que pertenece; heredan el valor de su mensaje primario.|
|Id. de mensaje de correo electrónico||Email_message_ID|Identificador de mensaje de Internet del mensaje.|
|EmailReadReceipt*||Email_read_receipt|Dirección de correo electrónico proporcionada en encabezados de Internet para confirmación de lectura.|
|Seguridad de correo electrónico|EmailSecurity|Email_security|Configuración de seguridad del mensaje: **0** - Ninguno; **1-** Firmado; **2** - Cifrado; **3-** Cifrado y firmado.|
|Confidencialidad de correo electrónico|EmailSensitivity|email_sensitivity|Configuración de confidencialidad del mensaje: **0** - Ninguno; **1** Personal; **2** - Privado; **3** - CompanyConfidential.|
|Conjunto de correo electrónico|EmailSet|Email_set|Id. de grupo de todos los mensajes del mismo conjunto de correo electrónico.|
|EmailThread*||Email_thread|Posición del mensaje dentro del conjunto de correo electrónico; consta de los IDs de nodo desde la raíz al mensaje actual y se separan por puntos (.).|
|Tipo de contenido extraído||Extracted_content_type|Tipo de contenido extraído, en forma de tipo mime; por ejemplo, **image/jpeg**|
|ExtractedTextLength*||Extracted_text_length|Número de caracteres del texto extraído.|
|Puntuación de relevancia familiar Problema 1*||Family_relevance_score_case_issue_1|Puntuación de relevancia de familia Caso número 1 de Relevancia.|
|FamilyDuplicateSet*||Family_duplicate_set|Identificador numérico de las familias que son duplicados exactos entre sí (mismo contenido y todos los mismos datos adjuntos).|
|Id. de familia|FamilyId|Family_ID|Id. de familia agrupa todos los elementos; para el correo electrónico, esto incluye el mensaje y todos los datos adjuntos; para documentos, esto incluye el documento y todos los elementos incrustados.|
|Tamaño de familia||Family_size|Número de documentos de la familia.|
|Puntuación de relevancia de archivo Problema 1*||File_relevance_score_case_issue_1|Puntuación de relevancia de archivo Caso número 1 de Relevancia.|
|Clase File|FileClass|File_class|Para el contenido de SharePoint y OneDrive: **Documento;** para el contenido de Exchange: **correo electrónico** o **datos adjuntos.**|
|Id. de archivo|FileId|File_ID|Identificador de documento único dentro del caso.|
|Fecha de creación del sistema de archivos||File_system_date_created|Fecha de creación desde el sistema de archivos (solo se aplica a datos que no son de Office 365).|
|Fecha de modificación del sistema de archivos||File_system_date_modified|Fecha de modificación del sistema de archivos (solo se aplica a datos que no son de Office 365).|
|Tipo de archivo|FileType||Tipo de archivo del elemento basado en la extensión de archivo.|
|Id. de grupo| GroupID|  |Id. de grupo para contenido agrupado.|
|Tiene datos adjuntos|HasAttachment|Email_has_attachment|Indica si el mensaje tiene datos adjuntos.|
|Tiene abogado|HasAttorney||**True** cuando al menos uno de los participantes se encuentra en la lista de abogados; de lo contrario, el valor es **False**.|
|HasText*||Has_text|Indica si el elemento tiene texto; los valores posibles **son True** y **False**.|
|Identificador inmutable||Immutable_ID|Este identificador se usa para identificar de forma única un documento dentro de un conjunto de revisión. Este campo no se puede usar en una búsqueda de conjunto de revisión y el identificador no se puede usar para tener acceso a un documento en su ubicación nativa.|
|Tipo inclusivo|InclusiveType|Inclusive_type|Tipo inclusivo calculado para análisis: **0,** no inclusivo; **1:** inclusive; **2** : menos inclusivo; **3:** copia inclusiva.|
|In Reply To Id||In_reply_to_ID|Responder al identificador del mensaje.|
|¿Son datos adjuntos modernos?| IsModernAttachment|  |Este archivo es un archivo adjunto o vinculado moderno.|
|Es de la versión del documento | IsFromDocumentVersion |  |El documento actual es de una versión diferente de otro documento.|
|¿Son datos adjuntos de correo electrónico? | IsEmailAttachment|  |Este elemento es de un archivo adjunto de correo electrónico que se muestra como un elemento adjunto al mensaje.|
|Es datos adjuntos en línea| IsInlineAttachment|  |Se ha adjuntado en línea y se muestra en el cuerpo del mensaje.|
|Es representativo|IsRepresentative|Is_representative|Un documento de cada conjunto de duplicados exactos se marca como representativo.|
|Clase Item|ItemClass|Item_class|Clase de elemento proporcionada por exchange Server; por ejemplo, **IPM. Nota**|
|Última modificación|LastModifiedDate|Doc_date_modified|Fecha de la última modificación de los metadatos del documento.|
|Id. de carga|LoadId|Load_ID|Identificador del conjunto de carga en el que se agregó el elemento a un conjunto de revisión.|
|Ubicación|Ubicación|Ubicación|Cadena que indica el tipo de ubicación de la que se han origen los documentos.<br /><br />**Datos importados:** datos que no son de Office 365<br />**Teams:** Microsoft Teams<br />**Exchange:** buzones de Exchange<br />**SharePoint:** sitios de SharePoint<br />**OneDrive:** cuentas de OneDrive|
|Nombre de la ubicación|LocationName|Location_name|Cadena que identifica el origen del elemento. Para Exchange, será la dirección SMTP del buzón; para SharePoint y OneDrive, la dirección URL de la colección de sitios.|
|Marcado como representativo|MarkAsRepresentative||Un documento de cada conjunto de duplicados exactos se marca como representante.|
|Marcado como problema de caso 1 etiquetado previamente*||Marked_as_pre_tagged_Case_issue_1|Marcado como problema de caso 1 etiquetado previamente desde Relevancia.|
|Marcado como problema de mayúsculas y minúsculas 1*||Marked_as_seed_Case_issue_1|Marcado como problema de caso de 1 de relevancia.|
|Fecha de finalización de la reunión|MeetingEndDate|Meeting_end_date|Fecha de finalización de la reunión para reuniones.|
|Fecha de inicio de la reunión|MeetingStartDate|Meeting_start_date|Fecha de inicio de la reunión para las reuniones.|
|Tipo de mensaje|MessageKind|Message_kind|Tipo de mensaje que se debe buscar. Valores posibles: contacts **<br /> <br /> <br /> docs <br /> email <br /> externaldata <br /> faxes <br /> im <br /> journals <br /> <br /> meetings microsoftteams** (returns items from chats, meetings, and calls in Microsoft Teams) **<br /> notes posts <br /> <br /> rssfeeds <br /> tasks <br /> voicemail**| 
|Extensión nativa|NativeExtension|Native_extension|Extensión nativa del elemento.|
|Nombre de archivo nativo|NativeFileName|Native_file_name|Nombre de archivo nativo del elemento.|
|NativeMD5||Native_MD5|Hash MD5 (valor hash de 128 bits) de la secuencia de archivos.|
|NativeSHA256||Native_SHA_256|Hash SHA256 (valor hash de 256 bits) de la secuencia de archivos.|
|ND/ET Sort: Exclusión de datos adjuntos|NdEtSortExclAttach|ND_ET_sort_excl_attach|Concatenación del conjunto de subprocesos de correo electrónico (ET) y del conjunto De duplicados cercanos (ND). Este campo se usa para una ordenación eficaz en tiempo de revisión. A **D** tiene el prefijo de conjuntos de ND y **E** a conjuntos ET.|
|ND/ET Sort: Incluir datos adjuntos|NdEtSortInclAttach|ND_ET_sort_incl_attach|Concatenación de un conjunto de subprocesos de correo electrónico (ET) y un conjunto casi duplicado (ND). Este campo se usa para una ordenación eficaz en tiempo de revisión. A **D** tiene el prefijo de conjuntos de ND y **E** a conjuntos ET. Cada elemento de correo electrónico de un conjunto de ET va seguido de sus datos adjuntos adecuados.|
|Puntuación de relevancia normalizada Problema 1||Normalized_relevance_score_case_issue_1|Puntuación de relevancia normalizada Problema 1 de relevancia.|
|Autores de O365||O365_authors|Autor desde SharePoint.|
|O365 creado por||O365_created_by|Creado por SharePoint.|
|Fecha de creación de O365||O365_date_created|Fecha de creación desde SharePoint.|
|Fecha de modificación de O365||O365_date_modified|Fecha de la última modificación de SharePoint.|
|O365 modificado por||O365_modified_by|Modificado por SharePoint.|
|Id. principal|ParentId|Parent_ID|Identificador del elemento primario.|
|ParentNode||Parent_node|El mensaje de correo electrónico anterior más cercano en el subproceso de correo electrónico.|
|Ruta de acceso principal|ParentPath|Parent_path|Ruta compuesta del elemento primario directo del elemento.|
|Dominios de participante|ParticipantDomains|Email_participant_domains|Lista de todos los dominios de participantes de un mensaje.|
|Participantes|Participantes|Email_participants|Lista de todos los participantes de un mensaje; por ejemplo, Remitente, Para, CC, CCO.|
|Identificador de tabla dinámica|PivotId|Pivot_ID|Identificador de una tabla dinámica.|
|Potencialmente con privilegios|PotentiallyPrivileged|Potentially_privileged|True si el modelo de detección de privilegios abogado-cliente considera que el documento puede tener privilegios|
|Estado de procesamiento|ProcessingStatus|Error_code|Estado de procesamiento después de agregar el elemento a un conjunto de revisión.|
|Lectura del porcentaje de caso 1||Read_percent_Case_issue_1|Leer el porcentaje de caso número 1 de Relevancia.|
|Percentil de lectura|ReadPercentile||Percentil de lectura para el documento basado en relevancia.|
|Número de destinatarios||Recipient_count|Número de destinatarios en el mensaje.|
|Dominios de destinatario|RecipientDomains|Email_recipient_domains|Lista de todos los dominios de destinatarios de un mensaje.|
|Destinatarios|Destinatarios|Email_recipients|Lista de todos los destinatarios de un mensaje (Para, CC, CCO).|
|Problema 1 del caso del grupo de carga de relevancia||Relevance_load_group_case_issue_1|Problema 1 del caso del grupo de carga de relevancia de Relevancia.|
|Descripción del estado de relevancia Caso número 1||Relevance_status_description_Case_issue_1|Descripción del estado de relevancia Caso número 1 de Relevancia.|
|Etiqueta de relevancia Problema 1||Relevance_tag_case_issue_1|Etiqueta de relevancia Asunto número 1 de Relevancia.|
|Comentario de relevancia||Relevance_comment|Campo Comentario de Relevancia.|
|Puntuación de relevancia|RelevanceScore||Puntuación de relevancia de un documento basado en relevancia.|
|Etiqueta de relevancia|RelevanceTag||Puntuación de relevancia de un documento basado en relevancia.|
|Id. de representante|RepresentativeId||Identificador numérico de cada conjunto de duplicados exactos.|
|Remitente|Remitente|Email_sender|Campo Remitente (de) para tipos de mensaje. El formato **es DisplayName \<SmtpAddress>**.|
|Remitente/autor|SenderAuthor||Campo calculado formado por el remitente o autor del elemento.|
|Dominio del remitente|SenderDomain|Email_sender_domain|Dominio del remitente.|
|Sent|Sent|Email_date_sent|Fecha de envío del mensaje.|
|Establecer orden: Inclusión primero|SetOrderInclusivesFirst|Set_order_inclusives_first|Campo de ordenación: correo electrónico y datos adjuntos: cronológicos contrarios; documentos: pivote primero por puntuación de similitud descendente.|
|SimilarityPercent||Similarity_percent|Indica la similitud de un documento con la tabla dinámica del conjunto casi duplicado.|
|Tamaño de archivo nativo|Size|Native_size|Número de bytes del elemento nativo.|
|Subject|Subject|Email_subject|Asunto del mensaje.|
|Asunto/Título|SubjectTitle||Campo calculado formado por el asunto o el título del elemento.|
|Etiquetado por el problema de caso 1||Tagged_by_Case_issue_1|Usuario que etiquetó este documento para el problema de caso 1 en Relevancia.|
|Etiquetas|Etiquetas|Etiquetas|Etiquetas aplicadas en un conjunto de revisión.|
|Lista de temas|ThemesList|Themes_list|Lista de temas calculada para análisis.|
|Título|Título|Doc_title|Título de los metadatos del documento.|
|To|To|Email_to|Para el campo de los tipos de mensaje. El formato **es DisplayName \<SmtpAddress>**|
|Único en el conjunto de correo electrónico|UniqueInEmailSet||**False** si hay un duplicado de los datos adjuntos en su conjunto de correo electrónico.|
|Se corrija|WasRemediated|Was_Remediated|**True** si se ha corregido el elemento; de lo **contrario, False**.|
|Word count|WordCount|Word_count|Número de palabras del elemento.|
|||||

> [!NOTE]
> Para obtener más información acerca de las propiedades que se pueden buscar al buscar en ubicaciones de contenido de Office 365 cuando se recopilan datos para un caso de eDiscovery avanzado, vea Consultas de palabras clave y condiciones de búsqueda para búsqueda de [contenido.](keyword-queries-and-search-conditions.md)
