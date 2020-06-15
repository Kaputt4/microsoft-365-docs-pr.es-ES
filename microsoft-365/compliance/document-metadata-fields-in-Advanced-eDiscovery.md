---
title: Campos de metadatos del documento en eDiscovery avanzado
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: En este artículo se definen los campos de metadatos para los documentos en un conjunto de revisión en un caso en eDiscovery avanzado en Microsoft 365.
ms.openlocfilehash: 19a8b4968ea4b1d82cd6a9e9278530e6c155ef3f
ms.sourcegitcommit: df6cc8c2eb2a65c7668f2953b0f7ec783a596d15
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/13/2020
ms.locfileid: "44726452"
---
# <a name="document-metadata-fields-in-advanced-ediscovery"></a>Campos de metadatos del documento en eDiscovery avanzado

En la siguiente tabla se enumeran los campos de metadatos de los documentos en un conjunto de revisión en un caso en eDiscovery avanzado. La tabla proporciona la siguiente información:

- Nombre del **campo** y **nombre del campo de presentación:** el nombre del campo de metadatos y el nombre del campo que se muestra al ver los metadatos de archivo de un documento seleccionado en un conjunto de revisión. Algunos campos de metadatos no se incluyen al ver los metadatos de archivo de un documento. Estos campos se resaltan con un asterisco (*).

- **Nombre de campo de búsqueda:** Nombre de la propiedad que se puede buscar al ejecutar una consulta de [conjunto de revisión](review-set-search.md). Una celda en blanco significa que no se puede buscar el campo en una consulta de conjunto de revisiones.

- **Nombre del campo exportado:** Nombre del campo de metadatos que se incluye al exportar los documentos.  Una celda en blanco significa que el campo no está incluido en los metadatos exportados.

- **Descripción:** Descripción del campo de metadatos.

> [!NOTE]
> El campo **palabras clave** en [revisar configurar búsqueda](https://docs.microsoft.com/microsoft-365/compliance/review-set-search) usa la palabra clave Query Language (KQL). Los campos enumerados en la columna **nombre de campo de búsqueda** pueden usarse en el campo **palabras clave** en una revisión de la configuración de revisión para crear consultas complejas sin tener que usar el generador de consultas. Para obtener más información sobre KQL, vea [referencia de sintaxis de lenguaje de consulta de palabras clave](https://go.microsoft.com/fwlink/?LinkId=269603).

|Nombre del **campo** y **nombre del campo de visualización**|**Nombre de campo de búsqueda**|**Nombre del campo exportado**|**Descripción**|
|:-----|:-----|:-----|:-----|
|Identificador de contenido de datos adjuntos|AttachmentContentId||Identificador de contenido de datos adjuntos del elemento.|
|Nombres de datos adjuntos|AttachmentNames|Attachment_Names|Lista de nombres de datos adjuntos.|
|Puntuación de privilegios de cliente abogado|AttorneyClientPrivilegeScore||Abogado-puntuación del contenido del modelo de privilegio de cliente.|
|Autor|Autor|Doc_authors|Autor de los metadatos del documento.|
|BCC|Bcc|Email_bcc|Campo Cco para tipos de mensaje. Format es **displayName \<SMTPAddress> **.|
|CC|Cc|Email_cc|Campo CC para los tipos de mensaje. Format es **displayName \<SMTPAddress> **.|
|Etiquetas de cumplimiento|ComplianceLabels|Compliance_labels|[Etiquetas de retención](labels.md) aplicadas al contenido en Office 365.|
|Ruta de acceso compuesta|CompoundPath|Compound_path|Ruta de acceso legible que describe el origen del elemento.|
|Contenido|Contenido||Texto extraído del elemento.|
|Cuerpo de la conversación|Cuerpo de la conversación||Cuerpo de la conversación del elemento.|
|Tema de conversación|Tema de conversación||Tema de conversación del elemento.|
|IDENTIFICADOR de conversación|ConversationId|Conversation_ID|Identificador de la conversación del mensaje.|
|Índice de conversaciones||Conversation_index|Índice de la conversación del mensaje.|
|Tiempo de PDF de conversación|ConversationPdfTime||Fecha en que se creó la versión PDF de la conversación.|
|Tiempo de grabación de redacción de conversación|ConversationRedactionBurnTime||Fecha en que se creó la versión PDF de la conversación para el chat.|
|Fecha de documento creada|CreatedTime|Doc_date_created|Crear fecha a partir de los metadatos del documento.|
|Custodian|Custodian|Custodian|Nombre del custodio al que estaba asociado el elemento.|
|Fecha|Fecha|Fecha|Fecha es un campo calculado que depende del tipo de archivo.<br /><br />Correo electrónico: fecha de envío<br />Datos adjuntos de correo electrónico: fecha de la última modificación del documento; si no está disponible, la fecha de envío del elemento primario<br />Documentos incrustados: fecha de la última modificación del documento; Si no está disponible, la fecha de la última modificación del elemento principal<br />Documentos de SPO (incluye datos adjuntos modernos): fecha de la última modificación de SharePoint; Si no está disponible, la fecha de última modificación de los documentos<br />Documentos que no son de Office 365: fecha de la última modificación<br />Reuniones: fecha de inicio de la reunión<br />Correo de voz: fecha de envío<br />MI: fecha de envío|
|Otras rutas de|Dedupedcompoundpath|Deduped_compound_path|Lista de rutas de datos compuestas de documentos que son duplicados exactos (correo electrónico: basado en contenido, documentos: basado en hash).|
|Otros custodios|DedupedCustodians|Deduped_custodians|Lista de custodios de documentos que son duplicados exactos (para correo electrónico, en función del contenido; para documentos, según el hash).|
|Otros identificadores de archivo|DedupedFileIds|Deduped_file_IDs|Lista de identificadores de archivos de documentos que son duplicados exactos (para correo electrónico, en función del contenido; para documentos, según el hash).|
|Comentarios del documento|DocComments|Doc_comments|Comentarios de los metadatos del documento.|
|Empresa de documentos||Doc_company|Compañía de los metadatos del documento.|
|DocIndex*|||Índice de la familia. **-1** o **0** significa que es la raíz.|
|Palabras clave de documento||Doc_keywords|Palabras clave de los metadatos del documento.|
|Documento modificado por||Doc_modified_by|Fecha de la última modificación de los metadatos del documento.|
|Revisión del documento||Doc_revision|Revisión a partir de los metadatos del documento.|
|Asunto del documento||Doc_subject|Asunto de los metadatos del documento.|
|Plantilla de documento||Doc_template|Plantilla de los metadatos del documento.|
|Tema dominante|DominantTheme|Dominant_theme|Tema dominante como se calcula para el análisis.|
|Subconjunto duplicado||Duplicate_subset|IDENTIFICADOR de grupo para los duplicados exactos.|
|EmailAction*||Email_action|Los valores son **None**, **reply**o **Forward**; se basa en la línea de asunto de un mensaje.|
|Confirmación de entrega de correo electrónico||Email_delivery_receipt|Dirección de correo electrónico suministrada en encabezados de Internet para la confirmación de entrega.|
|Importance|EmailImportance|Email_importance|Importancia del mensaje: **0** -bajo; **1** -normal; **2** : alto|
|EmailLevel*||Email_level|Indica el nivel de un mensaje dentro del subproceso de correo al que pertenece; los datos adjuntos heredan el valor del mensaje principal.|
|Identificador del mensaje de correo electrónico||Email_message_ID|Identificador del mensaje de Internet del mensaje.|
|EmailReadReceipt*||Email_read_receipt|Dirección de correo electrónico suministrada en encabezados de Internet para la confirmación de lectura.|
|Seguridad del correo electrónico|EmailSecurity|Email_security|Configuración de seguridad del mensaje: **0** -ninguno; **1** -firmado; **2** -cifrado; **3** : cifrado y firmado.|
|Confidencialidad del correo electrónico|EmailSensitivity|email_sensitivity|Configuración de sensibilidad del mensaje: **0** -ninguno; **1** personal; **2** -privado; **3** -CompanyConfidential.|
|Conjunto de correo electrónico|EmailSet|Email_set|IDENTIFICADOR de grupo para todos los mensajes en el mismo conjunto de correo electrónico.|
|EmailThread*||Email_thread|Posición del mensaje dentro del conjunto de correo electrónico; consta de identificadores de nodo desde la raíz al mensaje actual y están separados por puntos (.).|
|Tipo de contenido extraído||Extracted_content_type|Tipo de contenido extraído, en forma de tipo MIME; por ejemplo, **image/JPEG**|
|ExtractedTextLength*||Extracted_text_length|Número de caracteres en el texto extraído.|
|Número de caso de puntuación de la relevancia familiar, problema 1 *||Family_relevance_score_case_issue_1|Puntuación de relevancia de familia el problema 1 de la relevancia.|
|FamilyDuplicateSet*||Family_duplicate_set|Identificador numérico de las familias que son duplicados exactos entre sí (el mismo contenido y todos los mismos datos adjuntos).|
|IDENTIFICADOR de familia|FamilyId|Family_ID|ID de familia agrupa todos los elementos; para el correo electrónico, incluye el mensaje y todos los datos adjuntos; en el caso de los documentos, esto incluye el documento y los elementos incrustados.|
|Tamaño de la familia||Family_size|Número de documentos de la familia.|
|Número 1 de caso de puntuación de relevancia de archivo *||File_relevance_score_case_issue_1|Puntuación de relevancia de archivo caso del problema 1 de la relevancia.|
|Clase File|FileClass|File_class|Para contenido de SharePoint y OneDrive: **documento**; para contenido de Exchange: **correo electrónico** o **datos adjuntos**.|
|IDENTIFICADOR de archivo|FileId|File_ID|Identificador del documento único en el caso.|
|Fecha de creación del sistema de archivos||File_system_date_created|Fecha de creación desde el sistema de archivos (solo se aplica a los datos que no son de Office 365).|
|Fecha del sistema de archivos modificada||File_system_date_modified|Fecha de modificación del sistema de archivos (solo se aplica a los datos que no son de Office 365).|
|Tipo de archivo|FileType||Tipo de archivo del elemento en función de la extensión de archivo.|
|Tiene datos adjuntos|HasAttachment|Email_has_attachment|Indica si el mensaje tiene o no datos adjuntos.|
|Tiene abogado|HasAttorney||**True** cuando al menos uno de los participantes se encuentra en la lista de abogados; de lo contrario, el valor es **false**.|
|HasText||Has_text|Indica si el elemento tiene texto; los valores posibles son **true** y **false**.|
|Identificador inmutable||Immutable_ID|Este identificador se usa para identificar de forma única un documento dentro de un conjunto de revisión. Este campo no se puede usar en una búsqueda de conjunto de revisión y el identificador no puede usarse para obtener acceso a un documento en su ubicación nativa.|
|Tipo inclusivo|InclusiveType|Inclusive_type|Tipo inclusivo calculado para análisis: **0** -no inclusivo; **1** -ambos inclusive; **2** -inclusive menos; **3** -copia inclusiva.|
|En responder a ID.||In_reply_to_ID|En responder al identificador del mensaje.|
|Es representativo|IsRepresentative|Is_representative|Un documento de cada conjunto de duplicados exactos se marca como representativo.|
|Clase Item|ItemClass|Item_class|Clase de elemento proporcionada por Exchange Server; por ejemplo, **IPM. Nota:**|
|Última modificación|LastModifiedDate|Doc_date_modified|Fecha de última modificación de los metadatos del documento.|
|IDENTIFICADOR de carga|LoadId|Load_ID|Identificador del conjunto de carga en el que se agregó el elemento a un conjunto de revisión.|
|Location|Location|Location|Cadena que indica el tipo de ubicación desde la que se originaron los documentos.<br /><br />Datos **importados** -no de Office 365<br />**Teams** : Microsoft Teams<br />Buzones de **Exchange** -Exchange<br />**SharePoint** : sitios de SharePoint<br />**Onedrive** : cuentas de onedrive|
|Nombre de la ubicación|LocationName|Location_name|Cadena que identifica el origen del elemento. Para Exchange, será la dirección SMTP del buzón de correo; para SharePoint y OneDrive, la dirección URL de la colección de sitios.|
|Marcado como representativo|MarkAsRepresentative||Un documento de cada conjunto de duplicados exactos está marcado como representantes.|
|Marcado como un problema de caso con etiqueta previa 1 *||Marked_as_pre_tagged_Case_issue_1|Marcado como un problema de caso predefinido 1 de la relevancia.|
|Marcado como caso de inicialización, problema 1 *||Marked_as_seed_Case_issue_1|Marcado como el problema del caso de inicialización 1 de la relevancia.|
|Fecha de finalización de la reunión|MeetingEndDate|Meeting_end_date|Fecha de finalización de la reunión para las reuniones.|
|Fecha de inicio de la reunión|MeetingStartDate|Meeting_start_date|Fecha de inicio de la reunión para las reuniones.|
|Tipo de mensaje|MessageKind|Message_kind|El tipo de mensaje que se va a buscar. Valores posibles: ** <br /> <br /> contactos <br /> <br /> correo <br /> externaldata <br /> faxes <br /> mensajes <br /> <br /> <br /> de correo electrónico de contactos de contactos de Microsoft Teams** (devuelve elementos de chats, reuniones y llamadas en Microsoft Teams) publicaciones de RSSFeeds de correo de ** <br /> <br /> <br /> <br /> <br /> voz de Notes**| 
|Extensión nativa|NativeExtension|Native_extension|Extensión nativa del elemento.|
|Nombre de archivo nativo|NativeFileName|Native_file_name|Nombre de archivo nativo del elemento.|
|NativeMD5||Native_MD5|Hash MD5 (valor hash de 128 bits) de la secuencia de archivo.|
|NativeSHA256||Native_SHA_256|Hash SHA256 (valor hash de 256 bits) de la secuencia de archivo.|
|Ordenación de ND: excluir datos adjuntos|NdEtSortExclAttach|ND_ET_sort_excl_attach|Concatenación del conjunto de subprocesos de correo electrónico (ET) y del conjunto Near-duplicado (ND). Este campo se usa para la ordenación eficaz en el momento de la revisión. Un **D** se ANTEPONE a ND sets y un **e** se antepone a et sets.|
|Ordenación de ND: incluidos datos adjuntos|NdEtSortInclAttach|ND_ET_sort_incl_attach|Concatenación de un conjunto de subprocesos de correo electrónico (ET) y un conjunto casi duplicado (ND). Este campo se usa para la ordenación eficaz en el momento de la revisión. Un **D** se ANTEPONE a ND sets y un **e** se antepone a et sets. Cada elemento de correo electrónico de un conjunto ET sigue sus datos adjuntos apropiados.|
|Número de caso 1 de puntuación de relevancia normalizada||Normalized_relevance_score_case_issue_1|Problema de la puntuación del caso 1 de relevancia normalizada respecto a la relevancia.|
|Autores de O365||O365_authors|Autor de SharePoint.|
|O365 creado por||O365_created_by|Creado por desde SharePoint.|
|Fecha de creación de O365||O365_date_created|Fecha de creación de SharePoint.|
|Fecha de modificación de O365||O365_date_modified|Fecha de última modificación de SharePoint.|
|O365 modificada por||O365_modified_by|Modificado por desde SharePoint.|
|IDENTIFICADOR primario|ParentId|Parent_ID|Identificador del elemento primario del elemento.|
|ParentNode||Parent_node|El mensaje de correo electrónico anterior más cercano en el hilo de correo electrónico.|
|Ruta de acceso primaria|ParentPath|Parent_path|Ruta de acceso compuesta del elemento primario directo del elemento.|
|Dominios de participantes|ParticipantDomains|Email_participant_domains|Lista de todos los dominios de participantes de un mensaje.|
|Participantes|Participantes|Email_participants|Lista de todos los participantes de un mensaje; por ejemplo, Sender, to, CC o BCC.|
|IDENTIFICADOR dinámico|PivotId|Pivot_ID|IDENTIFICADOR de una tabla dinámica.|
|Potencialmente privilegiado|PotentiallyPrivileged|Potentially_privileged|True si el modelo de detección de privilegios de cliente de abogado considera el documento potencialmente privilegiado|
|Estado de procesamiento|ProcessingStatus|Error_code|Estado de procesamiento después de que el elemento se haya agregado a un conjunto de revisión.|
|Número 1 del caso de lectura porcentual||Read_percent_Case_issue_1|El caso de porcentaje de lectura del problema 1 de la relevancia.|
|Percentil de lectura|ReadPercentile||El percentil de lectura del documento en función de la relevancia.|
|Número de destinatarios||Recipient_count|Número de destinatarios del mensaje.|
|Dominios de destinatarios|RecipientDomains|Email_recipient_domains|Lista de todos los dominios de los destinatarios de un mensaje.|
|Destinatarios|Destinatarios|Email_recipients|Lista de todos los destinatarios de un mensaje (para, CC, CCO).|
|Problema del caso del grupo de carga de relevancia 1||Relevance_load_group_case_issue_1|Problema del caso de grupo de carga de relevancia 1 de la relevancia.|
|Problema de Descripción del caso de estado de relevancia 1||Relevance_status_description_Case_issue_1|Descripción del estado de relevancia caso del problema 1 de la relevancia.|
|Problema de caso de etiqueta de relevancia 1||Relevance_tag_case_issue_1|Caso de la etiqueta de relevancia el problema 1 de la relevancia.|
|Comentario de relevancia||Relevance_comment|Campo Comentario de la relevancia.|
|Puntuación de relevancia|RelevanceScore||Puntuación de relevancia de un documento en función de su relevancia.|
|Etiqueta de relevancia|RelevanceTag||Puntuación de relevancia de un documento en función de su relevancia.|
|IDENTIFICADOR representativo|RepresentativeId||Identificador numérico de cada conjunto de duplicados exactos.|
|Sender|Sender|Email_sender|Campo de remitente (de) para los tipos de mensaje. Format es **displayName \<SmtpAddress> **.|
|Remitente/autor|SenderAuthor||Campo calculado formado por el remitente o el autor del elemento.|
|Dominio del remitente|SenderDomain|Email_sender_domain|Dominio del remitente.|
|Sent|Sent|Email_date_sent|Fecha de envío del mensaje.|
|Establecer orden: primero inclusive|SetOrderInclusivesFirst|Set_order_inclusives_first|Campo de ordenación-correo electrónico y datos adjuntos: Counter-cronológico; Documents: Pivot primero, a continuación, por puntuación de similitud descendente.|
|SimilarityPercent||Similarity_percent|Indica la similitud de un documento con el pivote del conjunto de duplicados near.|
|Tamaño de archivo nativo|Size|Native_size|Número de bytes del elemento nativo.|
|Subject|Subject|Email_subject|Asunto del mensaje.|
|Asunto/título|SubjectTitle||Campo calculado compuesto por el asunto o el título del elemento.|
|Se etiquetan por el número de caso 1||Tagged_by_Case_issue_1|Usuario que etiquetó este documento por el problema de caso 1 en relevancia.|
|Etiquetas|Etiquetas|Etiquetas|Etiquetas aplicadas en un conjunto de revisión.|
|Lista de temas|ThemesList|Themes_list|Lista de temas tal y como se calcula para el análisis.|
|Título|Título|Doc_title|Título de los metadatos del documento.|
|To|To|Email_to|Campo para para los tipos de mensaje. El formato **es \<SmtpAddress> displayName**|
|Único en el conjunto de correo electrónico|UniqueInEmailSet||**False** si hay un duplicado de los datos adjuntos en su conjunto de correo electrónico.|
|Se corrigió|WasRemediated|Was_Remediated|**True** si el elemento se ha corregido; en caso contrario, **false**.|
|Word count|WordCount|Word_count|Número de palabras del elemento.|
|||||

> [!NOTE]
> Para obtener más información acerca de las propiedades que permiten búsquedas al buscar ubicaciones de contenido de Office 365 cuando está recopilando datos para un caso de exhibición avanzada de documentos electrónicos, vea [consultas de palabras clave y condiciones de búsqueda para la búsqueda de contenido](keyword-queries-and-search-conditions.md).
