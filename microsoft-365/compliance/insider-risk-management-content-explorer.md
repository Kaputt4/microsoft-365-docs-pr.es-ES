---
title: Explorador de contenido de administración de riesgos de Insider
description: Obtenga información sobre la administración de riesgos de insider Explorador de contenido en Microsoft 365
keywords: Microsoft 365, administración de riesgos internos, administración de riesgos, cumplimiento
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
ms.openlocfilehash: 44a17471f1e2ba92d0099f62b95dec8d0e56a224
ms.sourcegitcommit: b6763a8ab240fbdd56078a7c9452445d0c4b9545
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2021
ms.locfileid: "51957497"
---
# <a name="insider-risk-management-content-explorer"></a>Explorador de contenido de administración de riesgos de Insider

El explorador de  contenido de administración de riesgos insider permite a los usuarios asignados al rol De investigadores de administración de riesgos de *Insider* examinar el contexto y los detalles del contenido asociado con la actividad en las alertas. Los datos de caso en el explorador de contenido se actualizan diariamente para incluir nueva actividad. Para todas las alertas que se confirman en un caso, las copias de los datos y los archivos de mensajes se archivan como una instantánea en el tiempo de los elementos, mientras se mantienen los archivos y mensajes originales en los orígenes de almacenamiento. Si es necesario, los archivos de datos de caso pueden exportarse como un archivo de documento portátil (PDF) o en el formato de archivo original.

La copia de datos y mensajes es transparente para el usuario asociado con la alerta y para el propietario del contenido. Para los nuevos casos, normalmente el contenido tarda aproximadamente una hora en rellenarse en el explorador de contenido. Para los casos con grandes cantidades de contenido, puede tardar más tiempo en crear una instantánea. Si el contenido se sigue cargando en el explorador de contenido, verá un indicador de progreso que muestra el porcentaje de finalización.

En algunos casos, es posible que los datos asociados a un caso no estén disponibles como instantánea para su revisión en el Explorador de contenido. Esta situación puede producirse cuando los datos de caso se han eliminado o movido, o cuando se produce un error temporal al procesar datos de caso. Si se produce esta situación, seleccione **Ver** archivos en la barra de advertencia para ver los nombres de archivo, la ruta de acceso al archivo y el motivo del error para cada archivo. Si es necesario, esta información se puede exportar a un .csv (valores separados por comas).

Si el contenido incluye permisos de Information Rights Management, estos permisos se mantienen para el contenido copiado y los usuarios asignados al rol Investigadores de administración de riesgos de *Insider* necesitarán estos permisos y derechos si necesitan abrir y ver los archivos. A cada archivo y mensaje se le asigna automáticamente un identificador de archivo único en el caso de administración de riesgos de insider para fines de administración. Los documentos asociados con actividades de indicador de dispositivo no se incluyen en el Explorador de contenido.

>[!Note]
>El explorador de contenido incluye actividades relacionadas con Microsoft Office archivos. Las actividades de nivel de sitio, como cuando se elimina un sitio SharePoint o si se cambian los permisos del sitio, no se incluyen en el explorador de contenido.

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
| **Identificador inmutable** | Id. inmutable almacenado en Office 365. |
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
| **To** | El destinatario de un mensaje de correo electrónico en el campo Para. |

## <a name="filtering"></a>Filtrado

Puede usar uno o varios filtros para restringir el ámbito de una búsqueda y devolver un conjunto de resultados más refinado. Para establecer un filtro, seleccione **Filtros** en la parte superior de la cola de contenido. Muchos filtros incluyen opciones de filtrado adicionales para ayudar a restringir los resultados devueltos por el filtro. Por ejemplo, el filtro *Fecha* incluye controles para configurar una fecha *de inicio* y una fecha *de finalización* para el **filtro Fecha.** Seleccione uno o varios elementos de filtro de las siguientes categorías:

### <a name="common-filters"></a>Filtros comunes

| **Filtro** | **Descripción** |
|:---------------------|:----------------|
| **Fecha (UTC)** | Para correo electrónico, la fecha en que un destinatario recibió un mensaje o en que un remitente envió un mensaje. En el caso de los documentos, la fecha en que se modificó por última vez un documento. |
| **Sender/Author** | Para correo electrónico, la persona que envió un mensaje. Para los documentos, la persona que se cita en el *campo* Autor de Office documentos. Puede escribir más de un nombre, separados por comas. |
| **Source** | La ubicación del documento en la organización. Por ejemplo, una ubicación SharePoint sitio específico. |
| **Asunto/Título** | Para correo electrónico, el texto en la línea de asunto de un mensaje. Para los documentos, el título del documento. La propiedad Title de los documentos es metadatos especificados en Microsoft Office documentos. Puede escribir el nombre de más de un asunto o título, separados por comas. Dos o más valores están conectados de forma lógica por el operador de OR. |

### <a name="email-filters"></a>Filtros de correo electrónico

| **Filtro** | **Descripción** |
|:---------------------|:----------------|
| **Bcc** | Campo CCO de un mensaje de correo electrónico. |
| **Cc** | Campo Cc de un mensaje de correo electrónico. |
| **Tiene datos adjuntos** | Indica si un mensaje tiene datos adjuntos. Los valores se enumeran como **true** o **false**. |
| **¿Son datos adjuntos de correo electrónico?** | Si el documento es un archivo adjunto, el valor aparece como **Sí**. |
| **Es un documento incrustado** | Si el documento está incrustado en el mensaje de correo electrónico, el valor aparece como **Sí**. |
| **Es datos adjuntos en línea** | Si el documento es un archivo adjunto en línea en el mensaje de correo electrónico, el valor aparece como **Sí**. |
| **Participantes** | Todos los campos de personas de un mensaje de correo electrónico. Estos campos son From, To, Cc y CCO. |
| **Received** | La fecha en la que un destinatario recibió un mensaje de correo electrónico. |
| **Dominios de destinatarios** | Lista de todos los dominios de destinatarios de un mensaje. |
| **Destinatarios** | Destinatarios del mensaje de correo electrónico. |
| **Sender** | Campo Remitente (De) para tipos de mensaje.  Format es **DisplayName \<SmtpAddress>**. |
| **Dominio del remitente** | Dominio del remitente. |
| **To** | El campo Para de un mensaje de correo electrónico. |
| **Único en el conjunto de correo electrónico** | False si hay un duplicado de los datos adjuntos en su conjunto de correo electrónico. |

## <a name="document-filters"></a>Filtros de documentos

| **Filters** | **Descripción** |
|:---------------------|:----------------|
| **Etiquetas de cumplimiento** | Etiquetas de cumplimiento aplicadas en Office 365. |
| **Hora de creación (UTC)** | La fecha y hora en que se creó el archivo o el mensaje de correo electrónico. La fecha y la hora se encuentran en hora universal coordinada (UTC). |
| **Fecha de última modificación (UTC)** | La fecha en la que el documento se modificó por última vez. La fecha y la hora se encuentran en hora universal coordinada (UTC). |
| **Extensión de archivo** | Tipo de extensión del archivo. |
| **Eventos de actividad de usuario** | Actividad de elementos relacionados con una actividad de usuario específica en un caso.  Por ejemplo, cuando selecciona un vínculo a "Explorar contenido" para una actividad en la página **Actividad** del usuario de un caso, este filtro se usa para mostrar elementos relacionados con esa actividad. |
| **Producto de trabajo** | Tipo de producto de trabajo para el documento. Por ejemplo, anotaciones o etiquetas en el documento. |
