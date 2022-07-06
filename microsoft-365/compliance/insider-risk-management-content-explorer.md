---
title: Explorador de contenido de administración de riesgos internos
description: Más información sobre el Explorador de contenido de administración de riesgos internos en Microsoft Purview
keywords: Microsoft 365, Microsoft Purview, riesgo interno, administración de riesgos, cumplimiento
ms.localizationpriority: medium
ms.service: O365-seccomp
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: c193325608feef3bc8114b50af9d5e5832eb9d66
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2022
ms.locfileid: "66642555"
---
# <a name="insider-risk-management-content-explorer"></a>Explorador de contenido de administración de riesgos internos

El **explorador de contenido** de administración de riesgos internos permite a los usuarios *asignados el rol Insider Risk Management Investigators* examinar el contexto y los detalles del contenido asociado a la actividad en las alertas. Los datos del caso en el Explorador de contenido se actualizan diariamente para incluir nueva actividad. Para todas las alertas que se confirman en un caso, las copias de los archivos de datos y mensajes se archivan como una instantánea en el tiempo de los elementos, a la vez que se mantienen los archivos y mensajes originales en los orígenes de almacenamiento. Si es necesario, los archivos de datos de casos se pueden exportar como un archivo de documento portátil (PDF) o en el formato de archivo original.

En los casos nuevos, el contenido suele tardar aproximadamente una hora en rellenarse en el Explorador de contenido. En los casos con grandes cantidades de contenido, puede tardar más tiempo en crear una instantánea. Si el contenido se sigue cargando en el Explorador de contenido, verá un indicador de progreso que muestra el porcentaje de finalización.

En algunos casos, es posible que los datos asociados a un caso no estén disponibles como instantánea para su revisión en el Explorador de contenido. Esta situación puede producirse cuando los datos del caso se han eliminado o movido, o cuando se produce un error temporal al procesar datos de casos. Si se produce esta situación, seleccione **Ver archivos** en la barra de advertencia para ver los nombres de archivo, la ruta de acceso del archivo y el motivo del error de cada archivo. Si es necesario, esta información se puede exportar a un archivo .csv (valores separados por comas).

Si el contenido incluye permisos de Information Rights Management, estos permisos se mantienen para el contenido copiado y los usuarios *asignados al rol Investigadores de Insider Risk Management* necesitarán estos permisos y derechos si necesitan abrir y ver los archivos. A cada archivo y mensaje se le asigna automáticamente un identificador de archivo único en el caso de administración de riesgos internos con fines de administración. Los documentos asociados a las actividades de indicador de dispositivo no se incluyen en el Explorador de contenido.

> [!NOTE]
> El Explorador de contenido incluye actividades de usuario relacionadas con archivos de servicio de Microsoft 365, como la actividad de usuario en SharePoint, Exchange, Microsoft Teams y OneDrive para la Empresa.

## <a name="column-options"></a>Opciones de columna

Para facilitar que los analistas e investigadores de riesgo revisen los datos y mensajes capturados y revisen el contexto del caso, se incluyen varias herramientas de filtrado y ordenación en el Explorador de contenido. Para la ordenación básica, las columnas de clase **Date** y **File** admiten la ordenación mediante los títulos de columna en el panel de cola de contenido. Hay otras columnas de cola disponibles para agregarlas a la vista para proporcionar diferentes dinámicas en los archivos y mensajes.

Para agregar o quitar encabezados de columna para la cola de contenido, use el control **Editar columnas** y seleccione una de las siguientes opciones de columna. Estas columnas se asignan a las condiciones comunes, de correo electrónico y de propiedad de documento admitidas en el Explorador de contenido y que se enumeran más adelante en este artículo.

| **Opción Columna** | **Description** |
|:------------------|:----------------|
| **Author** | El campo de autor de los documentos de Office, que persiste si se copia un documento. Por ejemplo, si un usuario crea un documento y lo envía por correo electrónico a otra persona que luego lo carga en SharePoint, el documento conservará el autor original. |
| **Bcc** | Disponibles para los mensajes de correo electrónico, los usuarios en el campo mensaje CCO. |
| **Cc** | Disponible para los mensajes de correo electrónico, los usuarios en el campo Mensaje cc. |
| **Ruta de acceso compuesta** | Ruta de acceso legible humana que describe el origen del elemento. |
| **Identificador de conversación** | Identificador de conversación del mensaje. |
| **Índice de conversación** | Índice de conversación del mensaje. |
| **Tiempo de creación** | La hora en que se creó el archivo o el mensaje de correo electrónico. |
| **Fecha (UTC)** | Para correo electrónico, la fecha en que un destinatario recibió un mensaje o en que un remitente envió un mensaje. En el caso de los documentos, la fecha en que se modificó por última vez un documento. La fecha está en hora universal coordinada (UTC).|
| **Tema dominante** | Tema dominante calculado para el análisis. |
| **Id. del conjunto de correo electrónico** | Id. de grupo para todos los mensajes del mismo conjunto de correo electrónico. |
| **Id. de familia** | Id. de familia agrupa todos los elementos; para el correo electrónico, esta columna incluye el mensaje y todos los datos adjuntos; para los documentos, esta columna incluye el documento y los elementos incrustados. |
| **Clase de archivo** | Para el contenido de SharePoint y OneDrive: **Documento**; para el contenido de Exchange: **correo electrónico** o **datos adjuntos**. |
| **Id. de archivo** | Identificador de documento único dentro del caso. |
| **Icono de tipo de archivo** | Extensión de un archivo; por ejemplo, docx, one, pptx o xlsx. Este campo es la misma propiedad que la propiedad de sitio FileExtension. |
| **ID** | Identificador GUID del archivo. |
| **Identificador inmutable** | Identificador inmutable almacenado en Office 365. |
| **Tipo inclusivo** | Tipo inclusivo calculado para el análisis: **0** - no inclusivo; **1** - inclusivo; **2** - inclusive menos; **3** - copia inclusiva. |
| **Última modificación** | La fecha en la que el documento se modificó por última vez. |
| **Marcado como representativo** | Un documento de cada conjunto de duplicados exactos se marca como representantes. |
| **Tipo de mensaje** | Tipo de mensaje de correo electrónico que se va a buscar. Valores posibles: contactos, documentos, correo electrónico, datos externos, faxes, mi, diarios, reuniones, microsoft teams (devuelve elementos de chats, reuniones y llamadas en Microsoft Teams), notas, publicaciones, fuentes RSS, tareas, correo de voz |
| **Participantes** | Lista de todos los participantes de un mensaje; por ejemplo, Sender, To, Cc, Bcc. |
| **Identificador dinámico** | Identificador de una tabla dinámica. |
| **Received** | La fecha en la que un destinatario recibió un mensaje de correo electrónico. Este campo es la misma propiedad que la propiedad De correo electrónico recibido. |
| **Destinatarios** | Todos los campos de destinatario de un mensaje de correo electrónico. Estos campos son To, Cc y Bcc. |
| **Id. de representante** | Identificador numérico de cada conjunto de duplicados exactos. |
| **Sender** | El remitente de un mensaje de correo electrónico. |
| **Remitente/autor** | Para correo electrónico, la persona que envió un mensaje. Para los documentos, la persona mencionada en el campo del autor de documentos de Office. Puede escribir más de un nombre, separados por comas. Dos o más valores están conectados de forma lógica por el operador de OR. |
| **Tipos de información confidencial** | Tipos de información confidencial identificados en el contenido. |
| **Etiquetas de confidencialidad** | Las etiquetas de confidencialidad aplicadas al contenido. |
| **Sent** | La fecha en la que un remitente envió un mensaje de correo electrónico. Este campo es la misma propiedad que la propiedad Correo electrónico enviado. |
| **Size** | Para los correos electrónicos y documentos, el tamaño del elemento (en bytes). |
| **Subject** | El texto en la línea de asunto de un mensaje de correo electrónico. |
| **Asunto o título** | Para correo electrónico, el texto en la línea de asunto de un mensaje. Para los documentos, el título del documento. Como se explicó anteriormente, la propiedad Title es metadatos especificados en documentos de Microsoft Office. Puede escribir el nombre de más de un asunto o título, separados por comas. Dos o más valores están conectados de forma lógica por el operador de OR. |
| **Lista de temas** | Lista de temas calculada para el análisis. |
| **Title** | El título del documento. La propiedad Título son metadatos que se especifican en los documentos de Office. Es diferente del nombre de archivo del documento. |
| **Para** | Destinatario de un mensaje de correo electrónico en el campo Para. |

## <a name="filtering"></a>Filtrado

Puede usar uno o varios filtros para restringir el ámbito de una búsqueda y devolver un conjunto de resultados más refinado. Para establecer un filtro, seleccione **Filtros** en la parte superior de la cola de contenido. Muchos filtros incluyen opciones de filtrado adicionales para ayudar a restringir los resultados devueltos por el filtro. Por ejemplo, el filtro *Fecha* incluye controles para configurar una *fecha de inicio* y *una fecha de finalización* para el filtro **Fecha** . Seleccione uno o varios elementos de filtro de las categorías siguientes:

### <a name="common-filters"></a>Filtros comunes

| **Filtro** | **Descripción** |
|:---------------------|:----------------|
| **Fecha (UTC)** | Para correo electrónico, la fecha en que un destinatario recibió un mensaje o en que un remitente envió un mensaje. En el caso de los documentos, la fecha en que se modificó por última vez un documento. |
| **Remitente/autor** | Para correo electrónico, la persona que envió un mensaje. En el caso de los documentos, la persona citada en el campo *Autor* de documentos de Office. Puede escribir más de un nombre, separados por comas. |
| **Source** | Ubicación del documento en la organización. Por ejemplo, una ubicación de sitio de SharePoint específica. |
| **Asunto o título** | Para correo electrónico, el texto en la línea de asunto de un mensaje. Para los documentos, el título del documento. La propiedad Title de los documentos es metadatos especificados en documentos de Microsoft Office. Puede escribir el nombre de más de un asunto o título, separados por comas. Dos o más valores están conectados de forma lógica por el operador de OR. |

### <a name="email-filters"></a>Filtros de correo electrónico

| **Filtro** | **Descripción** |
|:---------------------|:----------------|
| **Bcc** | Campo CCO de un mensaje de correo electrónico. |
| **Cc** | Campo Cc de un mensaje de correo electrónico. |
| **Tiene datos adjuntos** | Indica si un mensaje tiene datos adjuntos. Los valores se muestran como **true** o **false**. |
| **Es datos adjuntos de correo electrónico** | Si el documento es un archivo adjunto, el valor aparece como **Sí**. |
| **Es un documento incrustado** | Si el documento está incrustado en el mensaje de correo electrónico, el valor aparece como **Sí**. |
| **Es datos adjuntos insertados** | Si el documento es un archivo adjunto insertado en el mensaje de correo electrónico, el valor aparece como **Sí**. |
| **Participantes** | Todos los campos de personas de un mensaje de correo electrónico. Estos campos son From, To, Cc y Bcc. |
| **Received** | La fecha en la que un destinatario recibió un mensaje de correo electrónico. |
| **Dominios de destinatario** | Lista de todos los dominios de destinatarios de un mensaje. |
| **Destinatarios** | Destinatarios del mensaje de correo electrónico. |
| **Sender** | Campo Remitente (Desde) para los tipos de mensaje.  El formato es **DisplayName \<SmtpAddress>**. |
| **Dominio del remitente** | Dominio del remitente. |
| **Para** | El campo Para de un mensaje de correo electrónico. |
| **Único en el conjunto de correo electrónico** | False si hay un duplicado de los datos adjuntos en su conjunto de correo electrónico. |

## <a name="document-filters"></a>Filtros de documento

| **Filters** | **Description** |
|:---------------------|:----------------|
| **Etiquetas de cumplimiento** | Etiquetas de cumplimiento aplicadas en Office 365. |
| **Hora de creación (UTC)** | Fecha y hora en que se creó el archivo o mensaje de correo electrónico. La fecha y hora están en hora universal coordinada (UTC). |
| **Fecha de última modificación (UTC)** | La fecha en la que el documento se modificó por última vez. La fecha y hora están en hora universal coordinada (UTC). |
| **Extensión de archivo** | Tipo de extensión del archivo. |
| **Eventos de actividad de usuario** | Actividad de elementos relacionados con una actividad de usuario específica en un caso.  Por ejemplo, al seleccionar un vínculo a "Explorar contenido" para una actividad en la página **Actividad del usuario** de un caso, este filtro se usa para mostrar elementos relacionados con esa actividad. |
| **Producto de trabajo** | Tipo de producto de trabajo para el documento. Por ejemplo, anotaciones o etiquetas en el documento. |
