---
title: Elementos parcialmente indizados en la búsqueda de contenido y otras herramientas de exhibición de documentos electrónicos
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
f1_keywords:
- ms.o365.cc.UnindexedItemsLearnMore
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: d1691de4-ca0d-446f-a0d0-373a4fc8487b
description: Obtenga información sobre los elementos no indexados en Exchange y SharePoint que puede incluir en una búsqueda de exhibición de documentos electrónicos que ejecute en el Centro de cumplimiento de Microsoft 365.
ms.openlocfilehash: 34758ae904678d194e889a4f1b65606d2420a3c7
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920304"
---
# <a name="partially-indexed-items-in-ediscovery"></a>Elementos parcialmente indizados en eDiscovery

Una búsqueda de exhibición de documentos electrónicos que se ejecuta desde el Centro de cumplimiento de Microsoft 365 incluye automáticamente elementos parcialmente indizados en los resultados de búsqueda estimados cuando se ejecuta una búsqueda. Los elementos parcialmente indizados son documentos y elementos de buzón de Exchange en sitios de SharePoint y OneDrive para la Empresa que, por algún motivo, no se indizaron completamente para la búsqueda. En Exchange, un elemento parcialmente indizado normalmente contiene un archivo (de un tipo de archivo que no se puede indizar) adjunto a un mensaje de correo electrónico. Estas son algunas otras razones por las que los elementos no se pueden indizar para la búsqueda y se devuelven como elementos parcialmente indizados cuando se ejecuta una búsqueda de exhibición de documentos electrónicos:
  
- El tipo de archivo no se admite o está deshabilitado para la indexación.

- Los mensajes tienen un archivo adjunto sin un controlador válido, como archivos de imagen; esta es la causa más común de los elementos de correo electrónico parcialmente indizados.

- El tipo de archivo se admite para indización pero se produjo un error de indización en un archivo específico.

- Se han adjuntado demasiados archivos a un mensaje de correo electrónico.

- Un archivo adjuntado a un mensaje de correo electrónico es demasiado grande.

- Un archivo se ha cifrado con tecnologías que no son de Microsoft.

- Un archivo está protegido por contraseña.

> [!NOTE]
> La mayoría de las organizaciones tienen menos del 1 % de contenido por volumen y menos del 12 % por tamaño parcialmente indizado. La razón de la diferencia entre el volumen y el tamaño es que los archivos más grandes tienen una probabilidad mayor de contener contenido que no se puede indizar por completo.
  
Para las investigaciones legales, es posible que su organización tenga que revisar elementos parcialmente indizados. También puede especificar si desea incluir elementos parcialmente indizados al exportar los resultados de la búsqueda a un equipo local o al preparar los resultados para su análisis con eDiscovery avanzado. Para obtener más información, vea [Investigar elementos parcialmente indizados en la exhibición de documentos electrónicos.](investigating-partially-indexed-items-in-ediscovery.md)
  
## <a name="file-types-not-indexed-for-search"></a>Tipos de archivo no indexados para búsquedas

Determinados tipos de archivos, como mapas de bits o MP3, no incluyen contenido que se pueda indexar. Como resultado, los servidores de indización de búsqueda de Exchange y SharePoint no realizan indización de texto completo en estos tipos de archivos. Estos tipos de archivo se consideran como no admitidos. También hay tipos de archivos para los que se ha deshabilitado la indexación de texto completo, ya sea de manera predeterminada o por un administrador. Los tipos de archivo no admitidos y deshabilitados se etiquetan como elementos no indexados en las búsquedas de contenido. Como se indicó anteriormente, los elementos parcialmente indizados se pueden incluir en el conjunto de resultados de búsqueda cuando se ejecuta una búsqueda, se exportan los resultados de la búsqueda a un equipo local o se prepararán los resultados de la búsqueda para eDiscovery avanzado.
  
Para obtener una lista de formatos de archivo compatibles y deshabilitados, vea los temas siguientes:
  
- **Exchange**  -  [Formatos de archivo indizados por exchange Search](https://go.microsoft.com/fwlink/p/?LinkID=386618)

- **Exchange**  -  [Get-SearchDocumentFormat](https://go.microsoft.com/fwlink/p/?LinkID=724037)

- **SharePoint**  -  [Extensiones de nombre de archivo rastreadas predeterminadas y tipos](https://go.microsoft.com/fwlink/p/?LinkID=404033) de archivo analizadas en SharePoint
  
## <a name="messages-and-documents-with-partially-indexed-file-types-can-be-returned-in-search-results"></a>Los mensajes y documentos con tipos de archivo parcialmente indizados se pueden devolver en los resultados de la búsqueda

No todos los mensajes de correo electrónico con datos adjuntos de archivo parcialmente indizados o todos los documentos de SharePoint parcialmente indizados se devuelven automáticamente como un elemento parcialmente indizado. Esto se debe a que otras propiedades de mensaje o documento, como la propiedad **Subject** en los mensajes de correo electrónico y las propiedades **Título** o Autor de los documentos están indizadas y están disponibles para su búsqueda.  Por ejemplo, una búsqueda de palabras clave para "financial" devolverá elementos con un archivo adjunto parcialmente indizado si esa palabra clave aparece en el asunto de un mensaje de correo electrónico o en el nombre de archivo o título de un documento. Sin embargo, si la palabra clave aparece solo en el cuerpo del archivo, el mensaje o documento se devolverá como un elemento parcialmente indizado.
  
De forma similar, los mensajes con datos adjuntos de archivo parcialmente indizados y documentos de un tipo de archivo parcialmente indizado se incluyen en los resultados de la búsqueda cuando otras propiedades de mensaje o documento, que se indizan y se pueden buscar, cumplen los criterios de búsqueda. Las propiedades de los mensajes que se indexan para la búsqueda son las fechas de envío y recepción, el remitente y el destinatario, el nombre de archivo de un adjunto, y el texto del cuerpo del mensaje. Las propiedades de los documentos que se indexan para la búsqueda son las fechas de creación y modificación. Por lo tanto, aunque los datos adjuntos de un mensaje pueden ser un elemento parcialmente indizado, el mensaje se incluirá en los resultados de búsqueda normales si el valor de otras propiedades de mensaje o documento coincide con los criterios de búsqueda.
  
Para obtener una lista de las propiedades de correo electrónico y documento que puede buscar mediante la característica de búsqueda en el Centro de seguridad y cumplimiento de &, vea Consultas de palabras clave y condiciones de búsqueda para la exhibición de [documentos electrónicos.](keyword-queries-and-search-conditions.md)
  
## <a name="partially-indexed-items-included-in-the-search-results"></a>Elementos parcialmente indizados incluidos en los resultados de la búsqueda

Es posible que su organización tenga que identificar y realizar análisis adicionales en elementos parcialmente indizados para determinar qué son, qué contienen y si son relevantes para una investigación específica. Como se ha explicado anteriormente, los elementos parcialmente indizados en las ubicaciones de contenido que se buscan se incluyen automáticamente con los resultados de búsqueda estimados. Tiene la opción de incluir estos elementos parcialmente indizados al exportar los resultados de la búsqueda o preparar los resultados de búsqueda para eDiscovery avanzado.
  
Tenga en cuenta lo siguiente sobre los elementos parcialmente indizados:
  
- Cuando se ejecuta una búsqueda de exhibición de documentos electrónicos, el número total y el tamaño de los elementos de Exchange parcialmente indizados (devueltos por la consulta de búsqueda) se muestran en las estadísticas de búsqueda en el panel de detalles y se etiquetan como elementos indizados **.** Las estadísticas sobre los elementos parcialmente indizados que se muestran en el panel de detalles no incluyen elementos parcialmente indizados en SharePoint o OneDrive.

- Si la búsqueda de la que exporta los resultados era una búsqueda de ubicaciones de contenido específicas o de todas las ubicaciones de contenido de la organización, solo se exportarán los elementos no indexados de las ubicaciones de contenido que contengan elementos que coincidan con los criterios de búsqueda. In other words, if no search results are found in a mailbox or site, then any unindexed items in that mailbox or site won't be exported. El motivo de esto es que exportar elementos parcialmente indizados desde muchas ubicaciones de la organización puede aumentar la probabilidad de errores de exportación y aumentar el tiempo necesario para exportar y descargar los resultados de la búsqueda.

    Para exportar elementos parcialmente indizados de todas las ubicaciones de contenido de una búsqueda, configure la búsqueda para que devuelva todos los elementos (quitando las palabras clave de la consulta de búsqueda) y, a continuación, exporte solo elementos parcialmente indizados cuando exporte los resultados de la búsqueda (haciendo clic en Solo los elementos que tienen un formato no **reconocido,** están cifrados o no se indexaron por otros motivos en opciones de **salida).**

- Si decide incluir todos los elementos del buzón en los resultados de la búsqueda, o si una consulta de búsqueda no especifica palabras clave o solo especifica un intervalo de fechas, es posible que los elementos parcialmente indizados no se copien en el archivo PST que contiene los elementos parcialmente indizados. Esto se debe a que todos los elementos, incluidos los elementos parcialmente indizados, se incluirán automáticamente en los resultados de búsqueda normales.

- Los elementos parcialmente indizados no están disponibles para obtener una vista previa. Debe exportar los resultados de la búsqueda para ver los elementos parcialmente indizados devueltos por la búsqueda.

Además, al exportar los resultados de la búsqueda e incluir elementos parcialmente indizados en la exportación, los elementos parcialmente indizados de los elementos de SharePoint se exportan a una carpeta denominada **Uncrawlable**. Al exportar elementos de Exchange parcialmente indizados, estos se exportan de forma diferente en función de si los elementos parcialmente indizados coinciden o no con la consulta de búsqueda y la configuración de la configuración de exportación. 

En la tabla siguiente se muestra el comportamiento de exportación de los elementos indizados y parcialmente indizados y si cada uno se incluye o no para las distintas opciones de configuración de exportación.

|**Exportar configuración**|**Elementos indizados que coinciden con la consulta de búsqueda**|**Elementos parcialmente indizados que coinciden con la consulta de búsqueda**|**Elementos parcialmente indizados que no coinciden con la consulta de búsqueda**|
|:-----|:-----|:-----|:-----|
|Exportar solo los elementos indexados  <br/> |Exported<br/> |Exportado (incluido con los elementos indizados que se exportan)<br/>  |No exportado <br/>|
|Exportar solo elementos parcialmente indizados  <br/> |No exportado  <br/> |Exportado (como elementos parcialmente indizados)<br/> |Exportado (como elementos parcialmente indizados)|
|Exportar elementos indizados y parcialmente indizados  <br/> |Exported<br/> |Exportado (incluido con los elementos indizados que se exportan)<br/>  |Exportado (como elementos parcialmente indizados)<br/>|
||||

## <a name="partially-indexed-items-excluded-from-the-search-results"></a>Elementos parcialmente indizados excluidos de los resultados de la búsqueda

Si un elemento se indiza parcialmente pero no cumple los criterios de consulta de búsqueda, no se incluirá como elemento parcialmente indizado en los resultados de la búsqueda. En otras palabras, el elemento se excluye de los resultados de la búsqueda. Por ejemplo, supongamos que ejecuta una búsqueda y no incluye ninguna palabra clave o propiedad porque desea incluir todo el contenido. Sin embargo, incluye una condición de intervalo de fechas para la consulta. Si un elemento parcialmente indizado está fuera de ese intervalo de fechas, no se incluirá como elemento parcialmente indizado. Los intervalos de fechas son una forma eficaz de excluir elementos parcialmente indizados de los resultados de la búsqueda.
  
De forma similar, si decide incluir elementos parcialmente indizados al exportar los resultados de una búsqueda, los elementos parcialmente indizados que se excluyeron de los resultados de la búsqueda no se exportarán.
  
Una excepción a esta regla es cuando se crea una retención basada en consultas que está asociada a un caso de exhibición de documentos electrónicos. Si crea una retención de exhibición de documentos electrónicos basada en consultas, todos los elementos parcialmente indizados se colocan en retención. Esto incluye elementos parcialmente indizados que no coinciden con los criterios de consulta de búsqueda y elementos parcialmente indizados que podrían estar fuera de una condición de intervalo de fechas. Para obtener más información acerca de la creación de retenciones de exhibición de documentos electrónicos basadas en consultas, vea [Crear una retención de exhibición de documentos electrónicos.](create-ediscovery-holds.md)
  
## <a name="indexing-limits-for-messages"></a>Límites de indización de mensajes

En la tabla siguiente se describen los límites de indización que pueden provocar que se devuelva un mensaje de correo electrónico como elemento parcialmente indizado en una búsqueda de exhibición de documentos electrónicos en Microsoft 365.
  
Para obtener una lista de los límites de indización para documentos de SharePoint, vea [Límites de búsqueda para SharePoint Online](https://docs.microsoft.com/sharepoint/search-limits).
  
|**Límite de indización**|**Notas**|**Descripción**|
|:-----|:-----|:-----|
|Tamaño máximo de datos adjuntos (excluidos los archivos de Excel)  <br/> |150 MB  <br/> |El tamaño máximo de un archivo adjunto de correo electrónico que se analizará para la indización. Los datos adjuntos que sean mayores que este límite no se analizarán para la indización y el mensaje con los datos adjuntos se marcará como parcialmente indizado.  <br/><br/> **Nota:** El análisis es el proceso en el que el servicio de indización extrae texto de los datos adjuntos, quita caracteres innecesarios como signos de puntuación y espacios y, a continuación, divide el texto en palabras (en un proceso denominado tokenización), que luego se almacenan en el índice.           |
|Tamaño máximo de los archivos de Excel  <br/> |4 MB  <br/> |El tamaño máximo de un archivo de Excel ubicado en un sitio o adjunto a un mensaje de correo electrónico que se analizará para la indización. No se analizará ningún archivo de Excel que supere este límite y el archivo o el correo electrónico con el archivo adjunto se marcará como no indexado.  <br/> |
|Número máximo de datos adjuntos  <br/> |250  <br/> |El número máximo de archivos adjuntos a un mensaje de correo electrónico que se analizarán para la indización. Si un mensaje tiene más de 250 datos adjuntos, los primeros 250 datos adjuntos se analizan e indizan, y el mensaje se marca como parcialmente indizado porque tenía datos adjuntos adicionales que no se analizaron.  <br/> |
|Profundidad máxima de datos adjuntos  <br/> |30  <br/> |El número máximo de datos adjuntos anidados que se analizan. Por ejemplo, si un mensaje de correo electrónico tiene otro mensaje adjunto y el mensaje adjunto tiene un documento de Word adjunto, se indizarán el documento de Word y el mensaje adjunto. Este comportamiento continuará para hasta 30 datos adjuntos anidados.  <br/> |
|Número máximo de imágenes adjuntas  <br/> |0  <br/> |El analizador omite una imagen adjunta a un mensaje de correo electrónico y no se indiza.  <br/> |
|Tiempo máximo dedicado a analizar un elemento  <br/> |30 segundos  <br/> |Se dedica un máximo de 30 segundos al análisis de un elemento para la indización. Si el tiempo de análisis supera los 30 segundos, el elemento se marca como parcialmente indizado.  <br/> |
|Salida máxima del analizador  <br/> |2 millones de caracteres  <br/> |La cantidad máxima de salida de texto del analizador indizado. Por ejemplo, si el analizador extrajo 8 millones de caracteres de un documento, solo se indizarán los primeros 2 millones de caracteres.  <br/> |
|Máximo de tokens de anotación  <br/> |2 millones  <br/> |Cuando se indiza un mensaje de correo electrónico, cada palabra se anota con diferentes instrucciones de procesamiento que especifican cómo se debe indizar esa palabra. Cada conjunto de instrucciones de procesamiento se denomina token de anotación. Para mantener la calidad del servicio en Office 365, hay un límite de 2 millones de tokens de anotación para un mensaje de correo electrónico.  <br/> |
|Tamaño máximo del cuerpo en el índice  <br/> |67 millones de caracteres  <br/> |El número total de caracteres en el cuerpo de un mensaje de correo electrónico y todos sus datos adjuntos. Cuando se indiza un mensaje de correo electrónico, todo el texto del cuerpo del mensaje y de todos los datos adjuntos se concatena en una sola cadena. El tamaño máximo de esta cadena indizada es de 67 millones de caracteres.  <br/> |
|Máximo de tokens únicos en el cuerpo  <br/> |1 millón  <br/> |Como se ha explicado anteriormente, los tokens son el resultado de extraer texto del contenido, quitar signos de puntuación y espacios y, a continuación, dividirlo en palabras (denominadas tokens) almacenadas en el índice. Por ejemplo, la frase  `"cat, mouse, bird, dog, dog"` contiene 5 tokens. Pero solo 4 de estos son tokens únicos. Hay un límite de 1 millón de tokens únicos por mensaje de correo electrónico, lo que ayuda a evitar que el índice se haga demasiado grande con tokens aleatorios.  <br/> |

## <a name="more-information-about-partially-indexed-items"></a>Más información sobre elementos parcialmente indizados

- Como se indicó anteriormente, como las propiedades de mensaje y documento y sus metadatos se indizan, una búsqueda de palabras clave podría devolver resultados si esa palabra clave aparece en los metadatos indizados. En cambio, la misma búsqueda de palabra clave podría no devolver el mismo elemento si la palabra clave solo aparece en el contenido de un elemento con un tipo de archivo no admitido. En este caso, el elemento se devolvería como un elemento parcialmente indizado.

- Si se incluye un elemento parcialmente indizado en los resultados de la búsqueda porque cumple los criterios de consulta de búsqueda (y no se ha excluido), no se incluirá como elemento parcialmente indizado en las estadísticas de búsqueda estimadas. Además, no se incluirá con elementos parcialmente indizados al exportar los resultados de la búsqueda.

- Aunque un tipo de archivo es compatible con la indización y se indiza, puede haber errores de indización o búsqueda que provocarán que un archivo se devuelva como elemento parcialmente indizado. Por ejemplo, la búsqueda en un archivo de Excel muy grande podría ser parcialmente correcta (porque los primeros 4 MB están indizados), pero luego se produce un error porque se supera el límite de tamaño de archivo. En este caso, es posible que se devuelva el mismo archivo con los resultados de búsqueda y como elemento parcialmente indizado.

- Los archivos que se cifran con tecnologías de cifrado de [Microsoft](encryption.md) y se adjuntan a un mensaje de correo electrónico que coincide con los criterios de una búsqueda se pueden obtener una vista previa y se descifrarán cuando se exporten. En este momento, los archivos cifrados con tecnologías de cifrado de Microsoft (y almacenados en SharePoint o OneDrive para la Empresa) se indizan parcialmente.

- Los mensajes de correo electrónico cifrados con S/MIME se indizan parcialmente. Esto incluye los mensajes cifrados con o sin datos adjuntos.

- Los mensajes de correo electrónico protegidos con Azure Rights Management se indizan y se incluirán en los resultados de la búsqueda si coinciden con la consulta de búsqueda. Los mensajes de correo electrónico protegidos por derechos se descifran y se pueden obtener una vista previa y exportarse. Esta funcionalidad requiere que se le asigne el rol Desciframiento de RMS, que se asigna de forma predeterminada al grupo de roles administrador de exhibición de documentos electrónicos.

## <a name="see-also"></a>Vea también

[Investigar elementos parcialmente indizados en eDiscovery](investigating-partially-indexed-items-in-ediscovery.md)
