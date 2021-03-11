---
title: Elementos parcialmente indizados en búsqueda de contenido y otras herramientas de exhibición de documentos electrónicos
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
description: Obtenga información sobre los elementos no indexados en Exchange y SharePoint que puede incluir en una búsqueda de exhibición de documentos electrónicos que se ejecuta en el Centro de cumplimiento de Microsoft 365.
ms.openlocfilehash: 308e0755f1966b8e4559cf6f08b3133a00ea1b5a
ms.sourcegitcommit: 88ab08c0fa1acbc9e066009e131b9f2b0d506c64
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/10/2021
ms.locfileid: "50711910"
---
# <a name="partially-indexed-items-in-ediscovery"></a>Elementos parcialmente indizados en eDiscovery

Una búsqueda de exhibición de documentos electrónicos que se ejecuta desde el Centro de cumplimiento de Microsoft 365 incluye automáticamente elementos parcialmente indizados en los resultados de búsqueda estimados al ejecutar una búsqueda. Los elementos parcialmente indizados son elementos y documentos de buzones de Exchange en sitios de SharePoint y OneDrive para la Empresa que, por algún motivo, no se indizaron completamente para la búsqueda. En Exchange, un elemento parcialmente indizado normalmente contiene un archivo (de un tipo de archivo que no se puede indizar) que se adjunta a un mensaje de correo electrónico. Estos son algunos otros motivos por los que los elementos no se pueden indizar para la búsqueda y se devuelven como elementos parcialmente indizados al ejecutar una búsqueda de exhibición de documentos electrónicos:
  
- El tipo de archivo no se admite o está deshabilitado para la indexación.

- Los mensajes tienen un archivo adjunto sin un controlador válido, como archivos de imagen; esta es la causa más común de elementos de correo electrónico parcialmente indizados.

- El tipo de archivo se admite para indización pero se produjo un error de indización en un archivo específico.

- Se han adjuntado demasiados archivos a un mensaje de correo electrónico.

- Un archivo adjuntado a un mensaje de correo electrónico es demasiado grande.

- Un archivo se ha cifrado con tecnologías que no son de Microsoft.

- Un archivo está protegido por contraseña.

> [!NOTE]
> La mayoría de las organizaciones tienen menos del 1 % de contenido por volumen y menos del 12 % por tamaño que está parcialmente indizado. La razón de la diferencia entre el volumen y el tamaño es que los archivos más grandes tienen una mayor probabilidad de contener contenido que no se puede indizar por completo.
  
Para las investigaciones legales, es posible que su organización tenga que revisar elementos parcialmente indizados. También puede especificar si se deben incluir elementos parcialmente indizados al exportar los resultados de búsqueda a un equipo local o al preparar los resultados para el análisis con exhibición de documentos electrónicos avanzada. Para obtener más información, vea [Investigating partially indexed items in eDiscovery](investigating-partially-indexed-items-in-ediscovery.md).
  
## <a name="file-types-not-indexed-for-search"></a>Tipos de archivo no indexados para búsquedas

Determinados tipos de archivos, como mapas de bits o MP3, no incluyen contenido que se pueda indexar. Como resultado, los servidores de indización de búsqueda en Exchange y SharePoint no realizan indización de texto completo en estos tipos de archivos. Estos tipos de archivo se consideran como no admitidos. También hay tipos de archivos para los que se ha deshabilitado la indexación de texto completo, ya sea de manera predeterminada o por un administrador. Los tipos de archivo no admitidos y deshabilitados se etiquetan como elementos sin indizar en búsquedas de contenido. Como se ha indicado anteriormente, los elementos parcialmente indizados se pueden incluir en el conjunto de resultados de búsqueda al ejecutar una búsqueda, exportar los resultados de búsqueda a un equipo local o preparar los resultados de búsqueda para la exhibición de documentos electrónicos avanzada.
  
Para obtener una lista de formatos de archivo compatibles y deshabilitados, vea los temas siguientes:
  
- **Exchange**  -  [Formatos de archivo indizados por la búsqueda de Exchange](https://go.microsoft.com/fwlink/p/?LinkID=386618)

- **Exchange**  -  [Get-SearchDocumentFormat](https://go.microsoft.com/fwlink/p/?LinkID=724037)

- **SharePoint**  -  [Extensiones de nombre de archivo rastreadas predeterminadas y tipos de archivo analizadas en SharePoint](https://go.microsoft.com/fwlink/p/?LinkID=404033)
  
## <a name="messages-and-documents-with-partially-indexed-file-types-can-be-returned-in-search-results"></a>Los mensajes y documentos con tipos de archivo parcialmente indizados se pueden devolver en los resultados de búsqueda

No todos los mensajes de correo electrónico con datos adjuntos de archivo parcialmente indizados o todos los documentos parcialmente indizados de SharePoint se devuelven automáticamente como un elemento parcialmente indizado. Esto se debe a que otras propiedades de mensaje o documento, como la propiedad **Subject** de los mensajes de correo electrónico y las propiedades **Title** o **Author** de los documentos están indizadas y están disponibles para buscarse. Por ejemplo, una búsqueda de palabras clave para "financial" devolverá elementos con datos adjuntos de archivo parcialmente indizados si esa palabra clave aparece en el asunto de un mensaje de correo electrónico o en el nombre de archivo o el título de un documento. Sin embargo, si la palabra clave aparece solo en el cuerpo del archivo, el mensaje o documento se devolverá como un elemento parcialmente indizado.
  
Del mismo modo, los mensajes con datos adjuntos de archivo parcialmente indizados y documentos de un tipo de archivo parcialmente indizado se incluyen en los resultados de búsqueda cuando otras propiedades de mensaje o documento, que son indizadas y que se pueden buscar, cumplen los criterios de búsqueda. Las propiedades de los mensajes que se indexan para la búsqueda son las fechas de envío y recepción, el remitente y el destinatario, el nombre de archivo de un adjunto, y el texto del cuerpo del mensaje. Las propiedades de los documentos que se indexan para la búsqueda son las fechas de creación y modificación. Por lo tanto, aunque los datos adjuntos de un mensaje pueden ser un elemento parcialmente indizado, el mensaje se incluirá en los resultados de búsqueda normales si el valor de otras propiedades de mensaje o documento coincide con los criterios de búsqueda.
  
Para obtener una lista de propiedades de correo electrónico y documentos que puede buscar mediante la característica de búsqueda en el Centro de seguridad y cumplimiento de &, vea Consultas de palabras clave y condiciones de búsqueda para [eDiscovery](keyword-queries-and-search-conditions.md).
  
## <a name="partially-indexed-items-included-in-the-search-results"></a>Elementos parcialmente indizados incluidos en los resultados de búsqueda

Es posible que su organización tenga que identificar y realizar análisis adicionales en elementos parcialmente indizados para determinar qué son, qué contienen y si son relevantes para una investigación específica. Como se explicó anteriormente, los elementos parcialmente indizados en las ubicaciones de contenido que se buscan se incluyen automáticamente con los resultados de búsqueda estimados. Tiene la opción de incluir estos elementos parcialmente indizados al exportar los resultados de búsqueda o preparar los resultados de búsqueda para la exhibición de documentos electrónicos avanzada.
  
Tenga en cuenta lo siguiente acerca de los elementos parcialmente indizados:
  
- Cuando se ejecuta una búsqueda de exhibición de documentos electrónicos, el número total y el tamaño de los elementos parcialmente indizados de Exchange (devueltos por la consulta de búsqueda) se muestran en las estadísticas de búsqueda de la página desplegable y se etiquetan como elementos sin indizar. Las estadísticas sobre elementos parcialmente indizados que se muestran en la página desplegable no incluyen elementos parcialmente indizados en SharePoint o OneDrive.

- Si la búsqueda de la que está exportando resultados era una búsqueda de ubicaciones de contenido específicas o de todas las ubicaciones de contenido de la organización, solo se exportarán los elementos sin indizar de las ubicaciones de contenido que contienen elementos que coinciden con los criterios de búsqueda. In other words, if no search results are found in a mailbox or site, then any unindexed items in that mailbox or site won't be exported. El motivo es que exportar elementos parcialmente indizados desde muchas ubicaciones de la organización podría aumentar la probabilidad de errores de exportación y aumentar el tiempo necesario para exportar y descargar los resultados de la búsqueda.

    Para exportar elementos parcialmente indizados de todas las ubicaciones de contenido de una búsqueda, configure la búsqueda para que devuelva todos los elementos (quitando las palabras clave de la consulta de búsqueda) y, a continuación, exporte solo elementos parcialmente indizados al exportar los resultados de la búsqueda (haciendo clic en Solo los elementos que tienen un formato no **reconocido,** se cifran o no se indizan por otros motivos en Opciones de **salida).**

- Si decide incluir todos los elementos de buzón de correo en los resultados de búsqueda, o si una consulta de búsqueda no especifica ninguna palabra clave o solo especifica un intervalo de fechas, es posible que los elementos parcialmente indizados no se copien en el archivo PST que contiene los elementos parcialmente indizados. Esto se debe a que todos los elementos, incluidos los elementos parcialmente indizados, se incluirán automáticamente en los resultados de búsqueda normales.

- Los elementos indizados parcialmente no están disponibles para obtener una vista previa. Debe exportar los resultados de la búsqueda para ver los elementos parcialmente indizados devueltos por la búsqueda.

Además, al exportar resultados de búsqueda e incluir elementos parcialmente indizados en la exportación, los elementos parcialmente indizados de elementos de SharePoint se exportan a una carpeta denominada **Uncrawlable**. Al exportar elementos parcialmente indizados de Exchange, se exportan de forma diferente en función de si los elementos parcialmente indizados coinciden o no con la consulta de búsqueda y la configuración de la configuración de exportación. 

En la tabla siguiente se muestra el comportamiento de exportación de los elementos indizados y parcialmente indizados y si cada uno está incluido o no para las distintas opciones de configuración de exportación.

|**Configuración de exportación**|**Elementos indizados que coinciden con la consulta de búsqueda**|**Elementos parcialmente indizados que coinciden con la consulta de búsqueda**|**Elementos parcialmente indizados que no coinciden con la consulta de búsqueda**|
|:-----|:-----|:-----|:-----|
|Exportar solo los elementos indexados  <br/> |Exported<br/> |Exportada (incluida con los elementos indizados que se exportan)<br/>  |No exportado <br/>|
|Exportar solo elementos parcialmente indizados  <br/> |No exportado  <br/> |Exportada (como elementos parcialmente indizados)<br/> |Exportada (como elementos parcialmente indizados)|
|Exportar elementos indexados y parcialmente indizados  <br/> |Exported<br/> |Exportada (incluida con los elementos indizados que se exportan)<br/>  |Exportada (como elementos parcialmente indizados)<br/>|
||||

## <a name="partially-indexed-items-excluded-from-the-search-results"></a>Elementos parcialmente indizados excluidos de los resultados de búsqueda

Si un elemento se indiza parcialmente pero no cumple los criterios de consulta de búsqueda, no se incluirá como elemento parcialmente indizado en los resultados de búsqueda. En otras palabras, el elemento se excluye de los resultados de la búsqueda. Por ejemplo, supongamos que ejecuta una búsqueda y no incluye ninguna palabra clave o propiedad porque desea incluir todo el contenido. Sin embargo, incluye una condición de intervalo de fechas para la consulta. Si un elemento parcialmente indizado se encuentra fuera de ese intervalo de fechas, no se incluirá como elemento parcialmente indizado. Los intervalos de fechas son una forma eficaz de excluir elementos parcialmente indizados de los resultados de búsqueda.
  
Del mismo modo, si decide incluir elementos parcialmente indizados al exportar los resultados de una búsqueda, los elementos parcialmente indizados que se excluyeron de los resultados de búsqueda no se exportarán.
  
Una excepción a esta regla es cuando se crea una retención basada en consultas asociada a un caso de exhibición de documentos electrónicos. Si crea una retención de exhibición de documentos electrónicos basada en consultas, todos los elementos parcialmente indizados se colocan en espera. Esto incluye elementos parcialmente indizados que no coinciden con los criterios de consulta de búsqueda y elementos parcialmente indizados que podrían estar fuera de una condición de intervalo de fechas. Para obtener más información acerca de cómo crear retenciones de exhibición de documentos electrónicos basadas en consultas, vea [Create an eDiscovery hold](create-ediscovery-holds.md).
  
## <a name="indexing-limits-for-messages"></a>Límites de indización de mensajes

En la tabla siguiente se describen los límites de indización que pueden provocar que se devuelva un mensaje de correo electrónico como elemento parcialmente indizado en una búsqueda de exhibición de documentos electrónicos en Microsoft 365.
  
Para obtener una lista de límites de indización para documentos de SharePoint, vea [Search limits for SharePoint Online](https://docs.microsoft.com/sharepoint/search-limits).
  
|**Límite de indización**|**Notas**|**Descripción**|
|:-----|:-----|:-----|
|Tamaño máximo de datos adjuntos (excluidos los archivos de Excel)  <br/> |150 MB  <br/> |El tamaño máximo de un archivo adjunto de correo electrónico que analizará la indización. Los datos adjuntos que sean mayores que este límite no se analizarán para la indización y el mensaje con los datos adjuntos se marcará como parcialmente indizado.  <br/><br/> **Nota:** El análisis es el proceso en el que el servicio de indización extrae texto de los datos adjuntos, quita caracteres innecesarios como signos de puntuación y espacios y, a continuación, divide el texto en palabras (en un proceso denominado tokenización), que luego se almacenan en el índice.           |
|Tamaño máximo de los archivos de Excel  <br/> |4 MB  <br/> |Tamaño máximo de un archivo de Excel ubicado en un sitio o adjunto a un mensaje de correo electrónico que se analizará para la indización. Los archivos de Excel que superen este límite no se analizarán y el archivo o el correo electrónico del mensaje con los datos adjuntos del archivo se marcarán como no indexados.  <br/> |
|Número máximo de datos adjuntos  <br/> |250  <br/> |El número máximo de archivos adjuntos a un mensaje de correo electrónico que se analizarán para la indización. Si un mensaje tiene más de 250 datos adjuntos, los primeros 250 datos adjuntos se analizan e indizan y el mensaje se marca como parcialmente indizado porque tenía datos adjuntos adicionales que no se analizaron.  <br/> |
|Profundidad máxima de datos adjuntos  <br/> |30  <br/> |Número máximo de datos adjuntos anidados que se analizan. Por ejemplo, si un mensaje de correo electrónico tiene otro mensaje adjunto y el mensaje adjunto tiene un documento de Word adjunto, se indizarán el documento de Word y el mensaje adjunto. Este comportamiento continuará hasta 30 datos adjuntos anidados.  <br/> |
|Número máximo de imágenes adjuntas  <br/> |0  <br/> |El analizador omite una imagen adjunta a un mensaje de correo electrónico y no está indizada.  <br/> |
|Tiempo máximo dedicado a analizar un elemento  <br/> |30 segundos  <br/> |Se pasa un máximo de 30 segundos analizando un elemento para la indización. Si el tiempo de análisis supera los 30 segundos, el elemento se marca como parcialmente indizado.  <br/> |
|Salida máxima del analizador  <br/> |2 millones de caracteres  <br/> |La cantidad máxima de salida de texto del analizador indizado. Por ejemplo, si el analizador extrajo 8 millones de caracteres de un documento, solo se indizarán los dos primeros millones de caracteres.  <br/> |
|Tokens de anotación máximos  <br/> |2 millones  <br/> |Cuando se indiza un mensaje de correo electrónico, cada palabra se anota con diferentes instrucciones de procesamiento que especifican cómo se debe indizar esa palabra. Cada conjunto de instrucciones de procesamiento se denomina token de anotación. Para mantener la calidad del servicio en Office 365, hay un límite de 2 millones de tokens de anotación para un mensaje de correo electrónico.  <br/> |
|Tamaño máximo del cuerpo en el índice  <br/> |67 millones de caracteres  <br/> |El número total de caracteres en el cuerpo de un mensaje de correo electrónico y todos sus datos adjuntos. Cuando se indiza un mensaje de correo electrónico, todo el texto del cuerpo del mensaje y de todos los datos adjuntos se concatena en una sola cadena. El tamaño máximo de esta cadena indizada es de 67 millones de caracteres.  <br/> |
|Tokens únicos máximos en el cuerpo  <br/> |1 millón  <br/> |Como se explicó anteriormente, los tokens son el resultado de extraer texto del contenido, quitar la puntuación y los espacios y, a continuación, dividirlo en palabras (denominadas tokens) que se almacenan en el índice. Por ejemplo, la frase  `"cat, mouse, bird, dog, dog"` contiene 5 tokens. Pero solo 4 de estos son tokens únicos. Hay un límite de 1 millón de tokens únicos por mensaje de correo electrónico, lo que ayuda a evitar que el índice se haga demasiado grande con tokens aleatorios.  <br/> |

## <a name="more-information-about-partially-indexed-items"></a>Más información sobre elementos parcialmente indizados

- Como se ha indicado anteriormente, como las propiedades del mensaje y del documento y sus metadatos están indizados, una búsqueda de palabras clave podría devolver resultados si esa palabra clave aparece en los metadatos indizados. En cambio, la misma búsqueda de palabra clave podría no devolver el mismo elemento si la palabra clave solo aparece en el contenido de un elemento con un tipo de archivo no admitido. En este caso, el elemento se devolvería como un elemento parcialmente indizado.

- Si un elemento parcialmente indizado se incluye en los resultados de búsqueda porque cumple los criterios de consulta de búsqueda (y no se excluye), no se incluirá como elemento parcialmente indizado en las estadísticas de búsqueda estimadas. Además, no se incluirá con elementos parcialmente indizados al exportar resultados de búsqueda.

- Aunque un tipo de archivo es compatible con la indización y está indizado, puede haber errores de indización o de búsqueda que harán que un archivo se devuelva como un elemento indizado parcialmente. Por ejemplo, la búsqueda en un archivo de Excel muy grande puede ser parcialmente correcta (porque se indizan los primeros 4 MB), pero, a continuación, se produce un error porque se supera el límite de tamaño del archivo. En este caso, es posible que se devuelva el mismo archivo con los resultados de búsqueda y como elemento parcialmente indizado.

- Los archivos cifrados con [tecnologías](encryption.md) de cifrado de Microsoft y adjuntos a un mensaje de correo electrónico que coincida con los criterios de una búsqueda se pueden obtener una vista previa y se descifrarán cuando se exporten. En este momento, los archivos cifrados con tecnologías de cifrado de Microsoft (y almacenados en SharePoint o OneDrive para la Empresa) se indizan parcialmente.

- Los mensajes de correo electrónico cifrados con S/MIME se indizan parcialmente. Esto incluye los mensajes cifrados con o sin datos adjuntos.

- Los mensajes de correo electrónico protegidos con Azure Rights Management se indizan y se incluirán en los resultados de búsqueda si coinciden con la consulta de búsqueda. Los mensajes de correo electrónico protegidos por derechos se descifran y se pueden obtener una vista previa y exportarse. Esta funcionalidad requiere que se le asigne el rol Descifrar RMS, que se asigna de forma predeterminada al grupo de roles administrador de exhibición de documentos electrónicos.

## <a name="see-also"></a>Vea también

[Investigar elementos parcialmente indizados en eDiscovery](investigating-partially-indexed-items-in-ediscovery.md)
