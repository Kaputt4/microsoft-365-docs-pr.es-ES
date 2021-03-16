---
title: Explorador de contenido de administración de riesgos de Insider
description: Obtenga información sobre el explorador de contenido de administración de riesgos de insider en Microsoft 365
keywords: Microsoft 365, administración de riesgos insider, administración de riesgos, cumplimiento
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
ms.openlocfilehash: ac5c423bffaa40d1b8cfbc50c68b1ca3f98ed0e6
ms.sourcegitcommit: 8b1bd7ca8cd81e4270f0c1e06d2b6ca81804a6aa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "50819852"
---
# <a name="insider-risk-management-content-explorer"></a>Explorador de contenido de administración de riesgos de Insider

El explorador de  contenido de administración de riesgos insider permite a los usuarios asignados al rol De investigadores de administración de riesgos de *Insider* examinar el contexto y los detalles del contenido asociado con la actividad en las alertas. Los datos de caso en el explorador de contenido se actualizan diariamente para incluir nueva actividad. Para todas las alertas que se confirman en un caso, las copias de los datos y los archivos de mensajes se archivan como una instantánea en el tiempo de los elementos, mientras se mantienen los archivos y mensajes originales en los orígenes de almacenamiento. La copia de datos y mensajes es transparente para el usuario asociado con la alerta y para el propietario del contenido. Para los nuevos casos, normalmente el contenido tarda aproximadamente una hora en rellenarse en el explorador de contenido. Para los casos con grandes cantidades de contenido, puede tardar más tiempo en crear una instantánea. Si el contenido se sigue cargando en el explorador de contenido, verá un indicador de progreso que muestra el porcentaje de finalización.

En algunos casos, es posible que los datos asociados a un caso no estén disponibles como instantánea para su revisión en el Explorador de contenido. Esta situación puede producirse cuando los datos de caso se han eliminado o movido, o cuando se produce un error temporal al procesar datos de caso. Si se produce esta situación, seleccione **Ver** archivos en la barra de advertencia para ver los nombres de archivo, la ruta de acceso al archivo y el motivo del error para cada archivo. Si es necesario, esta información se puede exportar a un archivo .csv (valores separados por comas).

Si el contenido incluye permisos de Information Rights Management, estos permisos se mantienen para el contenido copiado y los usuarios asignados al rol Investigadores de administración de riesgos de *Insider* necesitarán estos permisos y derechos si necesitan abrir y ver los archivos. A cada archivo y mensaje se le asigna automáticamente un identificador de archivo único en el caso de administración de riesgos de insider para fines de administración. Los documentos asociados con actividades de indicador de dispositivo no se incluyen en el Explorador de contenido.

![Explorador de contenido de administración de riesgos de Insider](../media/insider-risk-content-explorer.png)

>[!Note]
>El explorador de contenido incluye actividades relacionadas con Microsoft Office archivos. Las actividades de nivel de sitio, como cuando se elimina un sitio de SharePoint o si se cambian los permisos del sitio, no se incluyen en el explorador de contenido.

## <a name="column-options"></a>Opciones de columna

Para facilitar a los analistas de riesgos e investigadores revisar los datos y mensajes capturados y revisar el contexto del caso, se incluyen varias herramientas de filtrado y ordenación en el explorador de contenido. Para la ordenación básica, las columnas de clase **Date** y **File** admiten la ordenación mediante los títulos de columna en el panel de cola de contenido. Otras columnas de cola están disponibles para agregar a la vista para proporcionar diferentes dinámicas en los archivos y mensajes.

Para agregar o quitar encabezados de columna para la cola de contenido, use el control **Editar** columnas y seleccione de las siguientes opciones de columna. Estas columnas se asignan a las condiciones comunes de propiedad de correo electrónico y documento admitidas en el explorador de contenido y que se enumeran más adelante en este artículo.

| **Opción Columna** | **Descripción** |
|:------------------|:----------------|
| **Author** | El campo de autor de los documentos de Office, que persiste si se copia un documento. Por ejemplo, si un usuario crea un documento y lo envía por correo electrónico a otra persona que, a continuación, lo carga en SharePoint, el documento conservará el autor original. |
| **Bcc** | Disponible para mensajes de correo electrónico, los usuarios del campo Mensaje CCO. |
| **Cc** | Disponible para los mensajes de correo electrónico, los usuarios del campo Mensaje cc. |
| **Ruta compuesta** | Ruta de acceso legible humana que describe el origen del elemento. |
| **Id. de conversación** | Identificador de conversación del mensaje. |
| **Índice de conversación** | Índice de conversación del mensaje. |
| **Hora de creación** | La hora en que se creó el archivo o el mensaje de correo electrónico. |
| **Fecha (UTC)** | Para correo electrónico, la fecha en que un destinatario recibió un mensaje o en que un remitente envió un mensaje. En el caso de los documentos, la fecha en que se modificó por última vez un documento. Date se encuentra en la hora universal coordinada (UTC).|
| **Tema dominante** | Tema dominante calculado para análisis. |
| **Id. de conjunto de correo electrónico** | Id. de grupo para todos los mensajes del mismo conjunto de correo electrónico. |
| **Id. de familia** | Id. de familia agrupa todos los elementos; para el correo electrónico, esta columna incluye el mensaje y todos los datos adjuntos; para documentos, esta columna incluye el documento y los elementos incrustados. |
| **Clase File** | Para el contenido de SharePoint y OneDrive: **Document**; para el contenido de Exchange: **Correo electrónico** o **datos adjuntos**. |
| **Id. de archivo** | Identificador de documento único dentro del caso. |
| **Icono de tipo de archivo** | La extensión de un archivo; por ejemplo, docx, uno, pptx o xlsx. Este campo es la misma propiedad que la propiedad de sitio FileExtension. |
| **ID** | Identificador GUID del archivo. |
| **Identificador inmutable** | Identificador inmutable almacenado en Office 365. |
| **Tipo inclusivo** | Tipo inclusivo calculado para análisis: **0:** no inclusivo; **1** : inclusive; **2** : menos inclusivo; **3:** copia inclusiva. |
| **Última modificación** | La fecha en la que el documento se modificó por última vez. |
| **Marcado como representante** | Un documento de cada conjunto de duplicados exactos se marca como representantes. |
| **Tipo de mensaje** | Tipo de mensaje de correo electrónico que se debe buscar. Valores posibles: contactos, documentos, correo electrónico, datos externos, faxes, mensajería instantánea, diarios, reuniones, microsoft teams (devuelve elementos de chats, reuniones y llamadas en Microsoft Teams), notas, publicaciones, fuentes RSS, tareas, correo de voz |
| **Participantes** | Lista de todos los participantes de un mensaje; por ejemplo, Sender, To, Cc, CCO. |
| **Identificador dinámico** | El identificador de un pivot. |
| **Received** | La fecha en la que un destinatario recibió un mensaje de correo electrónico. Este campo es la misma propiedad que la propiedad de correo electrónico Recibido. |
| **Destinatarios** | Todos los campos de destinatario de un mensaje de correo electrónico. Estos campos son Para, Cc y CCO. |
| **Id. de representante** | Identificador numérico de cada conjunto de duplicados exactos. |
| **Sender** | El remitente de un mensaje de correo electrónico. |
| **Sender/Author** | Para correo electrónico, la persona que envió un mensaje. Para los documentos, la persona mencionada en el campo del autor de documentos de Office. Puede escribir más de un nombre, separados por comas. Dos o más valores están conectados de forma lógica por el operador de OR. |
| **Tipos de información confidencial** | Los tipos de información confidencial identificados en el contenido. |
| **Etiquetas de confidencialidad** | Las etiquetas de confidencialidad aplicadas al contenido. |
| **Sent** | La fecha en la que un remitente envió un mensaje de correo electrónico. Este campo es la misma propiedad que la propiedad De correo electrónico enviado. |
| **Tamaño** | Para los correos electrónicos y documentos, el tamaño del elemento (en bytes). |
| **Asunto** | El texto en la línea de asunto de un mensaje de correo electrónico. |
| **Asunto/Título** | Para correo electrónico, el texto en la línea de asunto de un mensaje. Para los documentos, el título del documento. Como se explicó anteriormente, la propiedad Title es metadatos especificados en Microsoft Office documentos. Puede escribir el nombre de más de un asunto o título, separados por comas. Dos o más valores están conectados de forma lógica por el operador de OR. |
| **Lista de temas** | Lista de temas calculada para análisis. |
| **Título** | El título del documento. La propiedad Título son metadatos que se especifican en los documentos de Office. Es diferente del nombre de archivo del documento. |
| **Para** | El destinatario de un mensaje de correo electrónico en el campo Para. |

## <a name="advanced-search-conditions"></a>Condiciones de búsqueda avanzadas

Puede agregar condiciones de búsqueda para restringir el ámbito de una búsqueda y devolver un conjunto de resultados más refinado. Cada condición agrega una cláusula a la consulta de búsqueda que se crea y se ejecuta cuando se inicia la búsqueda. Una condición está conectada lógicamente a la consulta de palabras clave (especificada en el cuadro de palabras clave) por un operador lógico (que se representa como c:c) que es similar en funcionalidad al operador AND. Esto significa que los elementos deben satisfacer tanto la consulta de palabras clave como una o más condiciones para incluirse en los resultados de la búsqueda. Esta funcionalidad es la forma en que las condiciones ayudan a restringir los resultados.

Para herramientas avanzadas de filtro y búsqueda, expanda el **panel Filtro** en el lado izquierdo de la cola de contenido. Seleccione el **botón Agregar una condición** para abrir la lista de condiciones:

### <a name="operators-used-with-conditions"></a>Operadores usados con condiciones

|**Operador**|**Equivalente de consulta**|**Descripción**|
|:-----------|:-------------------|:--------------|
| **After** |`property>date`| Se usa con condiciones de fecha. Devuelve los elementos que se enviaron, recibieron o modificaron después de la fecha especificada.|
| **Before** |`property<date`| Se usa con condiciones de fecha. Devuelve los elementos que se enviaron, recibieron o modificaron antes de la fecha especificada.|
| **Between** |`date..date`| Se usa con condiciones de fecha y tamaño. Cuando se usa con una condición de fecha, devuelve los elementos que se enviaron, recibieron o modificaron durante el intervalo de fechas especificado. Cuando se usa con una condición de tamaño, devuelve los elementos cuyo tamaño está dentro del intervalo especificado.|
| **Contiene todas las** |`(property:value) OR (property:value)`| Se usa con condiciones para las propiedades que especifican un valor de cadena. Devuelve elementos que contienen todos los valores de cadena especificados. |
| **Contiene cualquiera de** |`(property:value) OR (property:value)`| Se usa con condiciones para las propiedades que especifican un valor de cadena. Devuelve elementos que contienen cualquier parte de uno o más valores de cadena especificados.|
| **No contiene ninguno de** |`-property:value`  <br/> `NOT property:value`| Se usa con condiciones para las propiedades que especifican un valor de cadena. Devuelve elementos que no contienen ninguna parte del valor de cadena especificado.|
| **No es igual a ninguna de** |`-property=value`  <br/> `NOT property=value`| Se usa con condiciones para las propiedades que especifican un valor de cadena. Devuelve elementos que no contienen la cadena especificada.|
| **Igual a** |`size=value`| Devuelve elementos que son iguales al tamaño especificado. <sup>1</sup>|
| **Es igual a cualquiera de** |`(property=value) OR (property=value)`| Se usa con condiciones para las propiedades que especifican un valor de cadena. Devuelve elementos que coinciden exactamente con uno o más valores de cadena especificados.|
| **No es igual a ninguna de** |`(property=value) OR (property=value)`| Se usa con condiciones para las propiedades que especifican un valor de cadena. Devuelve elementos que no coinciden con uno o más valores de cadena especificados. |
| **Mayor que** |`size>value`| Devuelve elementos donde la propiedad especificada es mayor que el valor especificado. <sup>1</sup>|
| **Mayor o igual** |`size>=value`| Devuelve elementos donde la propiedad especificada es mayor o igual que el valor especificado. <sup>1</sup>|
| **Menor que** |`size<value`| Devuelve elementos que son mayores o iguales que el valor específico. <sup>1</sup>|
| **Menor o igual** |`size<=value`| Devuelve elementos que son mayores o iguales que el valor específico. <sup>1</sup>|
| **No es igual** |`size<>value`| Devuelve elementos que no son iguales al tamaño especificado. <sup>1</sup>|

> [!NOTE]
> <sup>1</sup> Este operador solo está disponible para las condiciones que usan la propiedad Size.

### <a name="common-property-conditions"></a>Condiciones de propiedad comunes

| **Opción Condición** | **Descripción** |
|:---------------------|:----------------|
| **Date** | Para correo electrónico, la fecha en que un destinatario recibió un mensaje o en que un remitente envió un mensaje. En el caso de los documentos, la fecha en que se modificó por última vez un documento. |
| **Sender/Author** | Para correo electrónico, la persona que envió un mensaje. Para los documentos, la persona mencionada en el campo del autor de documentos de Office. Puede escribir más de un nombre, separados por comas. Dos o más valores están conectados de forma lógica por el operador de **OR**. |
| **Tamaño** | Para los correos electrónicos y documentos, el tamaño del elemento (en bytes). |
| **Asunto/Título** | Para correo electrónico, el texto en la línea de asunto de un mensaje. Para los documentos, el título del documento. La propiedad Title de los documentos son metadatos especificados en Microsoft Office documentos. Puede escribir el nombre de más de un asunto o título, separados por comas. Dos o más valores están conectados de forma lógica por el operador de OR. |

### <a name="email-property-conditions"></a>Condiciones de la propiedad email

En la tabla siguiente se enumeran las condiciones de propiedad del mensaje de correo electrónico disponibles en el explorador de contenido.

| **Opción Condición** | **Descripción** |
|:---------------------|:----------------|
| **Bcc** | Campo CCO de un mensaje de correo electrónico. |
| **Cc** | Campo Cc de un mensaje de correo electrónico. |
| **Seguridad del correo electrónico** | Configuración de seguridad del mensaje. |
| **Confidencialidad del correo electrónico** | Configuración de confidencialidad del mensaje. |
| **Id. de conjunto de correo electrónico** | Id. de grupo para todos los mensajes del mismo conjunto de correo electrónico. |
| **From** | El remitente de un mensaje de correo electrónico. |
| **Tiene datos adjuntos** | Indica si un mensaje tiene datos adjuntos. Use los valores **true** o **false**. |
| **Importance** | La importancia de un mensaje de correo electrónico, que un remitente puede especificar al enviar un mensaje. De manera predeterminada, los mensajes se envían con importancia normal, a menos que el remitente establezca la importancia como **alta** o **baja**.   |
| **Fecha de finalización de la reunión** | Fecha de finalización de la reunión para reuniones. |
| **Fecha de inicio de la reunión** | Fecha de inicio de la reunión para reuniones. |
| **Tipo de mensaje** | Tipo de mensaje de correo electrónico que se debe buscar. Valores posibles: contactos, documentos, correo electrónico, datos externos, faxes, mensajería instantánea, diarios, reuniones, microsoft teams (devuelve elementos de chats, reuniones y llamadas en Microsoft Teams), notas, publicaciones, fuentes rss, tareas, correo de voz |
| **Dominio de participante** | Lista de todos los dominios de participantes de un mensaje. |
| **Participantes** | Todos los campos de personas de un mensaje de correo electrónico. Estos campos son From, To, Cc y CCO. |
| **Received** | La fecha en la que un destinatario recibió un mensaje de correo electrónico. |
| **Dominios de destinatarios** | Lista de todos los dominios de destinatarios de un mensaje. |
| **Sender** | Campo Remitente (De) para tipos de mensaje.  Format es **DisplayName \<SmtpAddress>**. |
| **Dominio del remitente** | Dominio del remitente. |
| **Asunto** | El texto en la línea de asunto de un mensaje de correo electrónico.  <br/> **Nota:** Cuando se usa la propiedad Subject en una consulta, la búsqueda devuelve todos los mensajes en los que la línea de asunto contiene el texto que está buscando. En otras palabras, la consulta no devuelve solo los mensajes que tienen una coincidencia exacta. Por ejemplo, si busca , los resultados incluirán mensajes con el `subject:"Quarterly Financials"` asunto "Finanzas trimestrales 2018". |
| **Para** | El campo Para de un mensaje de correo electrónico. |
| **Único en el conjunto de correo electrónico** | False si hay un duplicado de los datos adjuntos en su conjunto de correo electrónico. |

## <a name="document-property-conditions"></a>Condiciones de la propiedad Document

En la tabla siguiente se enumeran las condiciones de propiedad de documentos disponibles en el explorador de contenido. Muchas de estas condiciones de propiedad se comparten con conjuntos de revisión incluidos en [los casos de exhibición de documentos electrónicos avanzados.](document-metadata-fields-in-Advanced-eDiscovery.md)

| **Opción Condición** | **Descripción** |
|:---------------------|:----------------|
| **Puntuación de privilegios abogado-cliente** | Puntuación de contenido del modelo de privilegios abogado-cliente. |
| **Author** | El campo de autor de los documentos de Office, que persiste si se copia un documento. Por ejemplo, si un usuario crea un documento y lo envía por correo electrónico a otra persona que, a continuación, lo carga en SharePoint, el documento conservará el autor original. |
| **Etiquetas de cumplimiento** | Etiquetas de cumplimiento aplicadas en Office 365. |
| **Ruta compuesta** | Ruta de acceso legible humana que describe el origen del elemento. |
| **Id. de conversación** | Identificador de conversación del mensaje. |
| **Hora de creación** | La hora en que se creó el archivo o el mensaje de correo electrónico. |
| **Custodian** | Nombre del custodio al que se asoció el elemento. |
| **Tema dominante** | Tema dominante calculado para análisis. |
| **Id. de familia** | Id. de familia agrupa todos los elementos; para el correo electrónico, este campo incluye el mensaje y todos los datos adjuntos; para documentos, este campo incluye el documento y los elementos incrustados. |
| **Clase File** | Para el contenido de SharePoint y OneDrive: **Document**; para el contenido de Exchange: **Correo electrónico o **datos adjuntos**. |
| **Tipos de archivo** | La extensión de un archivo; por ejemplo, docx, uno, pptx o xlsx. |
| **Tiene participante del abogado** | True cuando al menos uno de los participantes se encuentra en la lista de abogados; de lo contrario, el valor es False. |
| **Identificador inmutable** | Identificador inmutable almacenado en Office 365. |
| **Tipo inclusivo** | Tipo inclusivo calculado para análisis: **0:** no inclusivo; **1** : inclusive; **2** : menos inclusivo; **3:** copia inclusiva. |
| **Clase Item** | Clase de elemento suministrada por el servidor exchange; por ejemplo, **IPM. Nota** |
| **Última modificación** | La fecha en la que el documento se modificó por última vez. |
| **Id. de carga** | Identificador de carga, en el que el elemento se cargó en un conjunto de revisión. |
| **Nombre de ubicación** | Cadena que identifica el origen del elemento.  Para Exchange, este campo será la dirección SMTP del buzón. Para SharePoint y OneDrive, la dirección URL de la colección de sitios. |
| **Marcado como representante** | Un documento de cada conjunto de duplicados exactos se marca como representantes. |
| **Extensión de archivo nativo** | Extensión nativa del elemento. |
| **Nombre de archivo nativo** | Nombre de archivo nativo del elemento. |
| **NdEtSortExclAttach** | Concatenación del conjunto de correo electrónico y del conjunto de ND para una ordenación eficaz en el momento de la revisión; D se agrega como prefijo a conjuntos de ND y E se agrega a conjuntos de correo electrónico. |
| **Identificador dinámico** | El identificador de un pivot. |
| **Potencialmente con privilegios** | True si el modelo de detección de privilegios abogado-cliente considera que el documento puede tener privilegios. |
| **Estado de procesamiento** | Estado de procesamiento después de agregar el elemento a un conjunto de revisión. |
| **Percentil de lectura** | Percentil de lectura para el documento basado en relevancia. |
| **Puntuación de relevancia** | Puntuación de relevancia de un documento basada en relevancia. |
| **Etiqueta relevancia** | Puntuación de relevancia de un documento basada en relevancia. |
| **Id. de representante** | Identificador numérico de cada conjunto de duplicados exactos. |
| **Tags** | Etiquetas aplicadas en un conjunto de revisión. |
| **Lista de temas** | Lista de temas calculada para análisis. |
| **Título** | El título del documento. La propiedad Título son metadatos que se especifican en los documentos de Office. Es diferente del nombre de archivo del documento. |
| **Se corrija** | True si el elemento se ha corregido, de lo contrario Es False. |
| **Conteo de palabras** | El número de palabras de un archivo. |
