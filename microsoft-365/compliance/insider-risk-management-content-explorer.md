---
title: Explorador de contenido de administración de riesgos de Insider
description: Obtenga información sobre el explorador de contenido de administración de riesgos de Insider en Microsoft 365
keywords: Microsoft 365, administración de riesgos de Insider, administración de riesgos, cumplimiento
localization_priority: Normal
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: 6eb8bf91f5af60658686066b75b33b7a8dabe6bc
ms.sourcegitcommit: e03bc2945e63f7f2638257e530056ae9283b45d9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2020
ms.locfileid: "49070874"
---
# <a name="insider-risk-management-content-explorer"></a>Explorador de contenido de administración de riesgos de Insider

El explorador de contenido de administración de riesgos de Insider permite a los usuarios que tengan asignado el rol de *investigadores de administración de riesgos de Insider* examinar el contexto y los detalles de contenido asociado a la actividad en las alertas. Para todas las alertas que se confirman en un caso, las copias de los datos y los archivos de mensajes se archivan como instantánea en el tiempo de los elementos, a la vez que mantienen los archivos y los mensajes originales en los orígenes de almacenamiento. La copia de datos y mensajes es transparente para el usuario asociado a la alerta y para el propietario del contenido. Si el contenido incluye permisos de Information Rights Management, estos permisos se mantienen para el contenido que se ha copiado y los usuarios a los que se les ha asignado el rol de *investigadores de administración de riesgos de Insider* necesitarán estos permisos y derechos si necesitan abrir y ver los archivos. A cada archivo y mensaje se les asigna automáticamente un identificador de archivo único en el caso de administración de riesgos de Insider con fines de administración. Los documentos asociados con actividades de indicador de dispositivo no se incluyen en el explorador de contenido.

![Explorador de contenido de administración de riesgos de Insider](../media/insider-risk-content-explorer.png)

## <a name="column-options"></a>Opciones de columna

Para que sea más fácil para los analistas de riesgos y los investigadores revisar los datos y mensajes capturados y revisar el contexto en el caso, se incluyen varias herramientas de filtrado y ordenación en el explorador de contenido. Para la ordenación básica, las columnas de **clase de archivo** y **fecha** admiten la ordenación con los títulos de columna en el panel Cola de contenido. Hay otras columnas de cola disponibles para agregar a la vista a fin de proporcionar diferentes tablas dinámicas a los archivos y mensajes.

Para agregar o quitar encabezados de columna de la cola de contenido, use el control **Editar columnas** y seleccione una de las siguientes opciones de columna. Estas columnas se asignan a las condiciones comunes, de correo electrónico y de propiedad de documento admitidas en el explorador de contenido y enumeradas más adelante en este artículo.

| **Opción de columna** | **Descripción** |
|:------------------|:----------------|
| **Author** | El campo de autor de los documentos de Office, que persiste si se copia un documento. Por ejemplo, si un usuario crea un documento y lo envía por correo electrónico a otra persona que la carga a SharePoint, el documento seguirá conservando el autor original. |
| **Bcc** | Disponible para los mensajes de correo electrónico, los usuarios en el campo de mensaje CCO. |
| **Cc** | Disponible para los mensajes de correo electrónico, los usuarios en el campo de mensaje CC. |
| **Ruta de acceso compuesta** | Ruta de acceso legible que describe el origen del elemento. |
| **IDENTIFICADOR de conversación** | Identificador de la conversación del mensaje. |
| **Índice de conversaciones** | Índice de la conversación del mensaje. |
| **Fecha de creación** | La hora en la que se creó el archivo o mensaje de correo electrónico. |
| **Date** | Para correo electrónico, la fecha en que un destinatario recibió un mensaje o en que un remitente envió un mensaje. Para los documentos, la fecha en que se modificó por última vez un documento. |
| **Tema dominante** | Tema dominante como se calcula para el análisis. |
| **IDENTIFICADOR de conjunto de correo electrónico** | IDENTIFICADOR de grupo para todos los mensajes en el mismo conjunto de correo electrónico. |
| **IDENTIFICADOR de familia** | ID de familia agrupa todos los elementos; para el correo electrónico, esta columna incluye el mensaje y todos los datos adjuntos; para los documentos, esta columna incluye el documento y los elementos incrustados. |
| **Clase File** | Para contenido de SharePoint y OneDrive: **documento** ; para contenido de Exchange: * * correo electrónico o **datos adjuntos**. |
| **IDENTIFICADOR de archivo** | Identificador del documento único en el caso. |
| **Icono de tipo de archivo** | La extensión de un archivo; por ejemplo, docx, One, pptx o XLSX. Este campo es la misma propiedad que la propiedad de sitio FileExtension. |
| **Id.** | Identificador GUID del archivo. |
| **Identificador inmutable** | Identificador inmutable tal y como se almacena en Office 365. |
| **Tipo inclusivo** | Tipo inclusivo calculado para análisis: **0** -no inclusivo; **1** -ambos inclusive; **2** -inclusive menos; **3** -copia inclusiva. |
| **Última modificación** | La fecha en la que el documento se modificó por última vez. |
| **Marcado como representativo** | Un documento de cada conjunto de duplicados exactos está marcado como representantes. |
| **Tipo de mensaje** | Tipo de mensaje de correo electrónico que se va a buscar. Valores posibles: contactos, documentos, correo electrónico, datos externos, faxes, mensajería instantánea, diarios, reuniones, Microsoft Teams (devuelve elementos de chats, reuniones y llamadas en Microsoft Teams), notas, publicaciones, RSSFeeds, tareas, correo de voz |
| **Participante** | Lista de todos los participantes de un mensaje; por ejemplo, Sender, to, CC o BCC. |
| **IDENTIFICADOR dinámico** | IDENTIFICADOR de una tabla dinámica. |
| **Received** | La fecha en la que un destinatario recibió un mensaje de correo electrónico. Este campo es la misma propiedad que la propiedad de correo electrónico recibido. |
| **Destinatarios** | Todos los campos de destinatarios en un mensaje de correo electrónico. Estos campos son para, CC y CCO. |
| **IDENTIFICADOR representativo** | Identificador numérico de cada conjunto de duplicados exactos. |
| **Sender** | El remitente de un mensaje de correo electrónico. |
| **Remitente/autor** | Para correo electrónico, la persona que envió un mensaje. Para los documentos, la persona mencionada en el campo del autor de documentos de Office. Puede escribir más de un nombre, separados por comas. Dos o más valores están conectados de forma lógica por el operador de OR. |
| **Sent** | La fecha en la que un remitente envió un mensaje de correo electrónico. Este campo es la misma propiedad que la propiedad email enviada. |
| **Tamaño** | Para los correos electrónicos y documentos, el tamaño del elemento (en bytes). |
| **Asunto** | El texto en la línea de asunto de un mensaje de correo electrónico. |
| **Asunto/título** | Para correo electrónico, el texto en la línea de asunto de un mensaje. Para los documentos, el título del documento. Como se ha explicado anteriormente, la propiedad title es metadatos especificados en los documentos de Microsoft Office. Puede escribir el nombre de más de un asunto o título, separados por comas. Dos o más valores están conectados de forma lógica por el operador de OR. |
| **Lista de temas** | Lista de temas tal y como se calcula para el análisis. |
| **Title** | El título del documento. La propiedad Título son metadatos que se especifican en los documentos de Office. Es diferente del nombre de archivo del documento. |
| **To** | El destinatario de un mensaje de correo electrónico en el campo para. |

## <a name="advanced-search-conditions"></a>Condiciones de búsqueda avanzadas

Puede agregar condiciones de búsqueda para restringir el ámbito de una búsqueda y devolver un conjunto de resultados más refinado. Cada condición agrega una cláusula a la consulta de búsqueda que se crea y se ejecuta cuando se inicia la búsqueda. Una condición está conectada lógicamente a la consulta de palabras clave (que se especifica en el cuadro palabra clave) por un operador lógico (que se representa como c:c) que es similar en funcionalidad al operador AND. Esto significa que los elementos deben cumplir con la consulta de palabra clave y una o más condiciones que se van a incluir en los resultados de la búsqueda. Esta funcionalidad es la forma en que las condiciones ayudan a restringir los resultados.

Para las herramientas de búsqueda y filtro avanzadas, expanda el panel de **filtros** en la parte izquierda de la cola de contenido. Seleccione el botón **Agregar una condición** para abrir la lista de condiciones:

### <a name="operators-used-with-conditions"></a>Operadores usados con condiciones

|**Operator**|**Equivalente de consulta**|**Descripción**|
|:-----------|:-------------------|:--------------|
| **After** |`property>date`| Se usa con condiciones de fecha. Devuelve los elementos que se enviaron, recibieron o modificaron después de la fecha especificada.|
| **Before** |`property<date`| Se usa con condiciones de fecha. Devuelve los elementos que se enviaron, recibieron o modificaron antes de la fecha especificada.|
| **Entre** |`date..date`| Se usa con condiciones de fecha y tamaño. Cuando se usa con una condición de fecha, devuelve los elementos que se enviaron, recibieron o modificaron durante el intervalo de fechas especificado. Cuando se usa con una condición de tamaño, devuelve los elementos cuyo tamaño está dentro del intervalo especificado.|
| **Contiene todos los** |`(property:value) OR (property:value)`| Se usa con condiciones para las propiedades que especifican un valor de cadena. Devuelve elementos que contienen todos los valores de una cadena especificada. |
| **Contiene cualquiera de** |`(property:value) OR (property:value)`| Se usa con condiciones para las propiedades que especifican un valor de cadena. Devuelve elementos que contienen cualquier parte de uno o más valores de cadena especificados.|
| **No contiene ninguno de** |`-property:value`  <br/> `NOT property:value`| Se usa con condiciones para las propiedades que especifican un valor de cadena. Devuelve elementos que no contienen ninguna parte del valor de cadena especificado.|
| **No es igual a ninguno de** |`-property=value`  <br/> `NOT property=value`| Se usa con condiciones para las propiedades que especifican un valor de cadena. Devuelve elementos que no contienen la cadena especificada.|
| **Igual a** |`size=value`| Devuelve elementos que son iguales al tamaño especificado. <sup>1</sup>|
| **Es igual a cualquiera de** |`(property=value) OR (property=value)`| Se usa con condiciones para las propiedades que especifican un valor de cadena. Devuelve elementos que coinciden exactamente con uno o más valores de cadena especificados.|
| **Es igual a ninguno de** |`(property=value) OR (property=value)`| Se usa con condiciones para las propiedades que especifican un valor de cadena. Devuelve elementos que no coinciden con uno o más valores de cadena especificados. |
| **Mayor que** |`size>value`| Devuelve los elementos en los que la propiedad especificada es mayor que el valor especificado. <sup>1</sup>|
| **Mayor o igual** |`size>=value`| Devuelve los elementos en los que la propiedad especificada es mayor o igual que el valor especificado. <sup>1</sup>|
| **Menor que** |`size<value`| Devuelve elementos que son mayores o iguales que el valor específico. <sup>1</sup>|
| **Menor o igual** |`size<=value`| Devuelve elementos que son mayores o iguales que el valor específico. <sup>1</sup>|
| **No es igual** |`size<>value`| Devuelve elementos que no son iguales al tamaño especificado. <sup>1</sup>|

> [!NOTE]
> <sup>1</sup> este operador solo está disponible para las condiciones que usan la propiedad Size.

### <a name="common-property-conditions"></a>Condiciones de propiedad comunes

| **Opción de condición** | **Descripción** |
|:---------------------|:----------------|
| **Date** | Para correo electrónico, la fecha en que un destinatario recibió un mensaje o en que un remitente envió un mensaje. Para los documentos, la fecha en que se modificó por última vez un documento. |
| **Remitente/autor** | Para correo electrónico, la persona que envió un mensaje. Para los documentos, la persona mencionada en el campo del autor de documentos de Office. Puede escribir más de un nombre, separados por comas. Dos o más valores están conectados de forma lógica por el operador de **OR**. |
| **Tamaño** | Para los correos electrónicos y documentos, el tamaño del elemento (en bytes). |
| **Asunto/título** | Para correo electrónico, el texto en la línea de asunto de un mensaje. Para los documentos, el título del documento. La propiedad title de los documentos son los metadatos especificados en los documentos de Microsoft Office. Puede escribir el nombre de más de un asunto o título, separados por comas. Dos o más valores están conectados de forma lógica por el operador de OR. |

### <a name="email-property-conditions"></a>Condiciones de propiedad de correo electrónico

En la tabla siguiente se enumeran las condiciones de propiedad de mensaje de correo electrónico disponibles en el explorador de contenido.

| **Opción de condición** | **Descripción** |
|:---------------------|:----------------|
| **Bcc** | El campo CCO de un mensaje de correo electrónico. |
| **Cc** | El campo CC de un mensaje de correo electrónico. |
| **Seguridad del correo electrónico** | Configuración de seguridad del mensaje. |
| **Confidencialidad del correo electrónico** | Configuración de sensibilidad del mensaje. |
| **IDENTIFICADOR de conjunto de correo electrónico** | IDENTIFICADOR de grupo para todos los mensajes en el mismo conjunto de correo electrónico. |
| **From** | El remitente de un mensaje de correo electrónico. |
| **Tiene datos adjuntos** | Indica si un mensaje tiene datos adjuntos. Use los valores **true** o **false**. |
| **Importance** | La importancia de un mensaje de correo electrónico, que un remitente puede especificar al enviar un mensaje. De manera predeterminada, los mensajes se envían con importancia normal, a menos que el remitente establezca la importancia como **alta** o **baja**.   |
| **Fecha de finalización de la reunión** | Fecha de finalización de la reunión para las reuniones. |
| **Fecha de inicio de la reunión** | Fecha de inicio de la reunión para las reuniones. |
| **Tipo de mensaje** | Tipo de mensaje de correo electrónico que se va a buscar. Valores posibles: contactos, documentos, correo electrónico, datos externos, faxes, mensajería instantánea, diarios, reuniones, Microsoft Teams (devuelve elementos de chats, reuniones y llamadas en Microsoft Teams), notas, publicaciones, RSSFeeds, tareas, correo de voz |
| **Dominio del participante** | Lista de todos los dominios de participantes de un mensaje. |
| **Participante** | Todos los campos de personas en un mensaje de correo electrónico. Estos campos son de, para, CC y CCO. |
| **Received** | La fecha en la que un destinatario recibió un mensaje de correo electrónico. |
| **Dominios de destinatarios** | Lista de todos los dominios de los destinatarios de un mensaje. |
| **Sender** | Campo de remitente (de) para los tipos de mensaje.  Format es **displayName \<SmtpAddress>**. |
| **Dominio del remitente** | Dominio del remitente. |
| **Asunto** | El texto en la línea de asunto de un mensaje de correo electrónico.  <br/> **Nota:** Cuando se usa la propiedad Subject en una consulta, la búsqueda devuelve todos los mensajes en los que la línea de asunto contiene el texto que se está buscando. En otras palabras, la consulta no devuelve solo los mensajes que tienen una coincidencia exacta. Por ejemplo, si busca `subject:"Quarterly Financials"` , los resultados incluirán los mensajes con el asunto "Quarterly financials 2018". |
| **To** | El campo Para de un mensaje de correo electrónico. |
| **Único en el conjunto de correo electrónico** | False si hay un duplicado de los datos adjuntos en su conjunto de correo electrónico. |

## <a name="document-property-conditions"></a>Condiciones de propiedades de documento

En la siguiente tabla se enumeran las condiciones de propiedad de documentos disponibles en el explorador de contenido. Muchas de estas condiciones de propiedad se comparten con los conjuntos de revisión incluidos en [casos de exhibición avanzada](document-metadata-fields-in-Advanced-eDiscovery.md)de documentos electrónicos.

| **Opción de condición** | **Descripción** |
|:---------------------|:----------------|
| **Abogado-puntuación de privilegios de cliente** | Abogado-puntuación del contenido del modelo de privilegio de cliente. |
| **Author** | El campo de autor de los documentos de Office, que persiste si se copia un documento. Por ejemplo, si un usuario crea un documento y lo envía por correo electrónico a otra persona que la carga a SharePoint, el documento seguirá conservando el autor original. |
| **Etiquetas de cumplimiento** | Etiquetas de cumplimiento aplicadas en Office 365. |
| **Ruta de acceso compuesta** | Ruta de acceso legible que describe el origen del elemento. |
| **IDENTIFICADOR de conversación** | Identificador de la conversación del mensaje. |
| **Fecha de creación** | La hora en la que se creó el archivo o mensaje de correo electrónico. |
| **Custodian** | Nombre del custodio al que estaba asociado el elemento. |
| **Tema dominante** | Tema dominante como se calcula para el análisis. |
| **IDENTIFICADOR de familia** | ID de familia agrupa todos los elementos; para el correo electrónico, este campo incluye el mensaje y todos los datos adjuntos; para los documentos, este campo incluye el documento y los elementos incrustados. |
| **Clase File** | Para contenido de SharePoint y OneDrive: **documento** ; para contenido de Exchange: * * correo electrónico o **datos adjuntos**. |
| **Tipos de archivo** | La extensión de un archivo; por ejemplo, docx, One, pptx o XLSX. |
| **Tiene un participante abogado** | True cuando al menos uno de los participantes se encuentra en la lista de abogados; de lo contrario, el valor es false. |
| **Identificador inmutable** | Identificador inmutable tal y como se almacena en Office 365. |
| **Tipo inclusivo** | Tipo inclusivo calculado para análisis: **0** -no inclusivo; **1** -ambos inclusive; **2** -inclusive menos; **3** -copia inclusiva. |
| **Clase Item** | Clase de elemento proporcionada por Exchange Server; por ejemplo, **IPM. Nota:** |
| **Última modificación** | La fecha en la que el documento se modificó por última vez. |
| **IDENTIFICADOR de carga** | Identificador de carga, en el que el elemento se cargó en un conjunto de revisión. |
| **Nombre de la ubicación** | Cadena que identifica el origen del elemento.  Para Exchange, este campo será la dirección SMTP del buzón. Para SharePoint y OneDrive, la dirección URL de la colección de sitios. |
| **Marcado como representativo** | Un documento de cada conjunto de duplicados exactos está marcado como representantes. |
| **Extensión de archivo nativa** | Extensión nativa del elemento. |
| **Nombre de archivo nativo** | Nombre de archivo nativo del elemento. |
| **NdEtSortExclAttach** | Concatenación de un conjunto de correo electrónico y un conjunto de ND para una ordenación eficaz en el momento de la revisión; D se agrega como prefijo a los conjuntos de ND y E se agrega a los conjuntos de correo electrónico. |
| **IDENTIFICADOR dinámico** | IDENTIFICADOR de una tabla dinámica. |
| **Potencialmente privilegiado** | True si el modelo de detección de privilegios de cliente de abogado considera el documento potencialmente privilegiado. |
| **Estado de procesamiento** | Estado de procesamiento después de que el elemento se haya agregado a un conjunto de revisión. |
| **Percentil de lectura** | El percentil de lectura del documento en función de la relevancia. |
| **Puntuación de relevancia** | Puntuación de relevancia de un documento en función de su relevancia. |
| **Etiqueta de relevancia** | Puntuación de relevancia de un documento en función de su relevancia. |
| **IDENTIFICADOR representativo** | Identificador numérico de cada conjunto de duplicados exactos. |
| **Tags** | Etiquetas aplicadas en un conjunto de revisión. |
| **Lista de temas** | Lista de temas tal y como se calcula para el análisis. |
| **Title** | El título del documento. La propiedad Título son metadatos que se especifican en los documentos de Office. Es diferente del nombre de archivo del documento. |
| **Se corrigió** | True si el elemento se ha corregido; en caso contrario, false. |
| **Conteo de palabras** | Número de palabras en un archivo. |
