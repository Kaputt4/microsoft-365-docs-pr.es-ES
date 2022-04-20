---
title: Elementos parcialmente indizados en la búsqueda de contenido
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.UnindexedItemsLearnMore
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: d1691de4-ca0d-446f-a0d0-373a4fc8487b
description: Obtenga información sobre los elementos sin indexar en Exchange y SharePoint que puede incluir en una búsqueda de eDiscovery que ejecute en el portal de cumplimiento de Microsoft Purview.
ms.openlocfilehash: 3e4f9521151755f97f3ad4b824c763f3ab5d807f
ms.sourcegitcommit: 52eea2b65c0598ba4a1b930c58b42dbe62cdaadc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/19/2022
ms.locfileid: "64932053"
---
# <a name="partially-indexed-items-in-ediscovery"></a>Elementos indizados parcialmente en eDiscovery

Una búsqueda de exhibición de documentos electrónicos de Microsoft Purview que se ejecuta desde el portal de cumplimiento de Microsoft Purview incluye automáticamente elementos parcialmente indexados en los resultados de búsqueda estimados al ejecutar una búsqueda. Los elementos indizados parcialmente son Exchange elementos y documentos de buzón de correo en sitios SharePoint y OneDrive para la Empresa que, por alguna razón, no estaban completamente indizados para la búsqueda. En Exchange, un elemento parcialmente indexado normalmente contiene un archivo (de un tipo de archivo que no se puede indexar) que está asociado a un mensaje de correo electrónico. Estas son algunas otras razones por las que los elementos no se pueden indexar para la búsqueda y se devuelven como elementos indizados parcialmente al ejecutar una búsqueda de exhibición de documentos electrónicos:
  
- El tipo de archivo no se admite o está deshabilitado para la indexación.

- Los mensajes tienen un archivo adjunto que no se puede abrir, como archivos de imagen; esta es la causa más común de los elementos de correo electrónico parcialmente indexados.

- El tipo de archivo se admite para indización pero se produjo un error de indización en un archivo específico.

- Se han adjuntado demasiados archivos a un mensaje de correo electrónico.

- Un archivo adjuntado a un mensaje de correo electrónico es demasiado grande.

- Un archivo se ha cifrado con tecnologías que no son de Microsoft.

- Un archivo está protegido por contraseña.

> [!NOTE]
> La mayoría de las organizaciones tienen menos del 1 % del contenido por volumen y menos del 12 % por tamaño que se indexa parcialmente. La razón de la diferencia entre volumen y tamaño es que los archivos más grandes tienen una mayor probabilidad de contener contenido que no se puede indexar completamente.
  
En el caso de las investigaciones legales, es posible que su organización tenga que revisar elementos parcialmente indexados. También puede especificar si se deben incluir elementos parcialmente indizados al exportar los resultados de búsqueda a un equipo local o al preparar los resultados para el análisis con eDiscovery (Premium). Para obtener más información, vea [Investigación de elementos parcialmente indexados en eDiscovery](investigating-partially-indexed-items-in-ediscovery.md).
  
## <a name="file-types-not-indexed-for-search"></a>Tipos de archivo no indexados para búsquedas

Determinados tipos de archivos, como mapas de bits o MP3, no incluyen contenido que se pueda indexar. Como resultado, los servidores de indexación de búsqueda de Exchange y SharePoint no realizan la indexación de texto completo en estos tipos de archivos. Estos tipos de archivo se consideran como no admitidos. También hay tipos de archivos para los que se ha deshabilitado la indexación de texto completo, ya sea de manera predeterminada o por un administrador. Los tipos de archivo no admitidos y deshabilitados se etiquetan como elementos sin indexar en Búsquedas de contenido. Como se indicó anteriormente, los elementos parcialmente indexados se pueden incluir en el conjunto de resultados de búsqueda al ejecutar una búsqueda, exportar los resultados de búsqueda a un equipo local o preparar los resultados de búsqueda para eDiscovery (Premium).
  
Para obtener una lista de formatos de archivo compatibles y deshabilitados, vea los temas siguientes:
  
-  - **formatos Exchange** [File indexados por Exchange Search](/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)

-  -  Exchange [Get-SearchDocumentFormat](/powershell/module/exchange/get-searchdocumentformat)

-  -  SharePoint [Nombre de archivo rastreado predeterminado y tipos de archivo analizados en SharePoint](/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)
  
## <a name="messages-and-documents-with-partially-indexed-file-types-can-be-returned-in-search-results"></a>Los mensajes y documentos con tipos de archivo parcialmente indexados se pueden devolver en los resultados de la búsqueda.

No todos los mensajes de correo electrónico con datos adjuntos de archivo parcialmente indexados o todos los SharePoint documento parcialmente indexados se devuelven automáticamente como un elemento parcialmente indexado. Esto se debe a que otras propiedades de mensaje o documento, como la propiedad **Subject** en los mensajes de correo electrónico y las propiedades **Title** o **Author** de los documentos están indexadas y están disponibles para buscarse. Por ejemplo, una búsqueda de palabras clave para "financial" devolverá elementos con un archivo adjunto parcialmente indexado si esa palabra clave aparece en el asunto de un mensaje de correo electrónico o en el nombre de archivo o el título de un documento. Sin embargo, si la palabra clave aparece solo en el cuerpo del archivo, el mensaje o documento se devolvería como un elemento parcialmente indexado.
  
De forma similar, los mensajes con datos adjuntos de archivos parcialmente indexados y documentos de un tipo de archivo indizado parcialmente se incluyen en los resultados de la búsqueda cuando otras propiedades de mensaje o documento, que se indizan y se pueden buscar, coinciden con los criterios de búsqueda. Las propiedades de los mensajes que se indexan para la búsqueda son las fechas de envío y recepción, el remitente y el destinatario, el nombre de archivo de un adjunto, y el texto del cuerpo del mensaje. Las propiedades de los documentos que se indexan para la búsqueda son las fechas de creación y modificación. Por lo tanto, aunque los datos adjuntos de un mensaje pueden ser un elemento parcialmente indexado, el mensaje se incluirá en los resultados de búsqueda normales si el valor de otras propiedades de mensaje o documento coincide con los criterios de búsqueda.
  
Para obtener una lista de las propiedades de correo electrónico y documento que puede buscar mediante herramientas de exhibición de documentos electrónicos en el portal de cumplimiento, vea [Consultas de palabras clave y condiciones de búsqueda para eDiscovery](keyword-queries-and-search-conditions.md).
  
> [!NOTE]
> Si un elemento de buzón de correo se mueve de una carpeta indizada a una carpeta que no está indizada, se establece una marca para anular la indexación del elemento y el elemento se quita del índice y no se puede buscar. Más adelante, si ese mismo elemento se mueve de nuevo a una carpeta indizada, la marca no se restablece. Esto significa que el elemento permanecerá sin indexar y no se podrá buscar.

## <a name="partially-indexed-items-included-in-the-search-results"></a>Elementos indizados parcialmente incluidos en los resultados de la búsqueda

Es posible que sea necesario que su organización identifique y realice análisis adicionales sobre los elementos parcialmente indexados para determinar qué son, qué contienen y si son pertinentes para una investigación específica. Como se explicó anteriormente, los elementos indizados parcialmente en las ubicaciones de contenido que se buscan se incluyen automáticamente con los resultados de búsqueda estimados. Tiene la opción de incluir estos elementos parcialmente indexados al exportar los resultados de búsqueda o preparar los resultados de búsqueda para eDiscovery (Premium).
  
Tenga en cuenta lo siguiente sobre los elementos indizados parcialmente:
  
- Al ejecutar una búsqueda de exhibición de documentos electrónicos, el número total y el tamaño de los elementos Exchange parcialmente indexados (devueltos por la consulta de búsqueda) se muestran en las estadísticas de búsqueda de la página de control flotante y se etiquetan como **elementos no indizados**. Las estadísticas sobre los elementos indizados parcialmente que se muestran en la página de control flotante no incluyen elementos indizados parcialmente en SharePoint sitios o cuentas de OneDrive.

- Si la búsqueda desde la que va a exportar los resultados era una búsqueda de ubicaciones de contenido específicas o de todas las ubicaciones de contenido de su organización, solo se exportarán los elementos no indizados de ubicaciones de contenido que contienen elementos que coinciden con los criterios de búsqueda. In other words, if no search results are found in a mailbox or site, then any unindexed items in that mailbox or site won't be exported. El motivo es que la exportación de elementos parcialmente indexados desde muchas ubicaciones de la organización podría aumentar la probabilidad de errores de exportación y aumentar el tiempo necesario para exportar y descargar los resultados de la búsqueda.

    Para exportar elementos indizados parcialmente desde todas las ubicaciones de contenido de una búsqueda, configure la búsqueda para que devuelva todos los elementos (quitando las palabras clave de la consulta de búsqueda) y, a continuación, exporte solo elementos parcialmente indizados al exportar los resultados de la búsqueda (haciendo clic **en Solo los elementos que tienen un formato no reconocido, se cifran o no se indexan por otros motivos** en **Opciones de salida**).

- Si decide incluir todos los elementos de buzón en los resultados de la búsqueda, o si una consulta de búsqueda no especifica ninguna palabra clave o solo especifica un intervalo de fechas, es posible que los elementos parcialmente indizados no se copien en el archivo PST que contiene los elementos indizados parcialmente. Esto se debe a que todos los elementos, incluidos los elementos parcialmente indizados, se incluirán automáticamente en los resultados de búsqueda normales.

- Los elementos indizados parcialmente no están disponibles para obtener una vista previa. Tiene que exportar los resultados de la búsqueda para ver los elementos parcialmente indexados devueltos por la búsqueda.

   Además, al exportar resultados de búsqueda e incluir elementos parcialmente indizados en la exportación, los elementos indizados parcialmente de SharePoint elementos se exportan a una carpeta denominada **Uncrawlable**. Al exportar elementos Exchange parcialmente indizados, se exportan de forma diferente en función de si los elementos parcialmente indexados coincidían o no con la consulta de búsqueda y la configuración de la configuración de exportación. 

- En la tabla siguiente se muestra el comportamiento de exportación de los elementos indexados y parcialmente indexados y si cada uno de ellos se incluye para los distintos valores de configuración de exportación.

  |**Configuración de exportación**|**Elementos indizados que coinciden con la consulta de búsqueda**|**Elementos indizados parcialmente que coinciden con la consulta de búsqueda**|**Elementos indizados parcialmente que no coinciden con la consulta de búsqueda**|
  |:-----|:-----|:-----|:-----|
  |Exportar solo los elementos indexados  <br/> |Exported<br/> |Exportado (incluido con los elementos indizados que se exportan)<br/>  |No exportado <br/>|
  |Exportar solo elementos parcialmente indizados  <br/> |No exportado  <br/> |Exportado (como elementos parcialmente indexados)<br/> |Exportado (como elementos parcialmente indexados)|
  |Exportación de elementos indexados y parcialmente indizados  <br/> |Exported<br/> |Exportado (incluido con los elementos indizados que se exportan)<br/>  |Exportado (como elementos parcialmente indexados)<br/>|
  ||||
  
## <a name="workaround-for-using-a-date-range-to-exclude-partially-indexed-items"></a>Solución alternativa para usar un intervalo de fechas para excluir elementos parcialmente indizados

En Búsqueda de contenido y Exhibición de documentos electrónicos de Microsoft Purview (estándar), no puede usar un intervalo de fechas para excluir que una consulta de búsqueda devuelva elementos parcialmente indizados. Es decir, los elementos indizados parcialmente que se encuentran fuera de un intervalo de fechas se siguen incluyendo como elementos indizados parcialmente en las estadísticas de búsqueda y al exportar elementos parcialmente indizados. En eDiscovery (Premium), puede excluir elementos parcialmente indexados mediante un intervalo de fechas en una consulta de búsqueda.

Como solución alternativa a esta limitación, se recomienda el procedimiento siguiente.

1. Cree y ejecute una búsqueda mediante una consulta de búsqueda que cumpla sus requisitos y devuelva los resultados deseados.

2. Exporte los resultados de la búsqueda del paso 1, pero no incluya elementos parcialmente indexados en la exportación. Para ello, seleccionaría **la opción Todos los elementos, excepto los que tienen formato no reconocido, se cifran o no se indexan por otros motivos** . <sup>1</sup>

   ![Opciones de salida de exportación.](../media/ExportOutputOptions.png)

3. Cree y ejecute una segunda búsqueda que use la misma consulta de búsqueda (y busque en las mismas ubicaciones) que usó en el paso 1. Anexe la cláusula siguiente a la consulta original mediante el operador **AND** :

   ```text
   <original query> AND ((IndexingErrorCode>0 OR IndexingErrorCode<0) AND sent:date1..date2)
   ```

   Al agregar esta cláusula, se devolverán elementos parcialmente indexados que coincidan con la consulta de búsqueda original y que se encuentren dentro de un intervalo de fechas específico. <sup>2</sup>

4. Exporte los resultados de la búsqueda del paso 3 y, esta vez, incluya elementos parcialmente indexados en la exportación. Para ello, seleccionaría **la opción Todos los elementos, incluidos los que tienen formato no reconocido, se cifran o no se indexan por otros motivos** .

   > [!NOTE]
   > <sup>1</sup> La salida del paso 2 solo da como resultado la exportación de elementos indexados.<br/>
   > <sup>2</sup> La condición usada en el paso 3 identifica solo los elementos con errores de indexación que se encuentran dentro del intervalo de fechas especificado. No devuelve ningún elemento que esté totalmente indexado. Esto significa que los elementos exportados en el paso 4 solo incluyen elementos sin indexar que se encuentran dentro del intervalo de fechas. La exportación no incluye elementos indizados. Como resultado, la salida combinada de los pasos 2 y 4 contiene todos los elementos indexados y sin indexar que se encuentran dentro del intervalo de fechas especificado.

Use la segunda búsqueda que creó en el paso 3 y la exportación correspondiente para ver y comprender los elementos parcialmente indexados que coinciden con la consulta de búsqueda original. La exportación de la segunda búsqueda también incluye todos los elementos parcialmente indexados que se exportaron para que pueda revisarlos si es necesario.

> [!TIP]
> En el procedimiento anterior, puede exportar los resultados de búsqueda reales o solo exportar un informe.

## <a name="indexing-limits-for-messages"></a>Límites de indexación de mensajes

En la tabla siguiente se describen los límites de indexación que podrían dar lugar a que se devuelva un mensaje de correo electrónico como un elemento parcialmente indexado en una búsqueda de exhibición de documentos electrónicos en Microsoft 365.
  
Para obtener una lista de los límites de indexación de SharePoint documentos, consulte [Límites de búsqueda para SharePoint Online](/sharepoint/search-limits).
  
|**Límite de indexación**|**Notas**|**Descripción**|
|:-----|:-----|:-----|
|Tamaño máximo de datos adjuntos (excepto Excel archivos)  <br/> |150 MB  <br/> |Tamaño máximo de los datos adjuntos de un correo electrónico que se analizarán para la indexación. Los datos adjuntos que sean mayores que este límite no se analizarán para la indexación y el mensaje con los datos adjuntos se marcará como indizado parcialmente.  <br/><br/> **Nota:** El análisis es el proceso en el que el servicio de indexación extrae texto de los datos adjuntos, quita caracteres innecesarios como signos de puntuación y espacios y, a continuación, divide el texto en palabras (en un proceso denominado tokenización) que, a continuación, se almacenan en el índice.           |
|Tamaño máximo de Excel archivos  <br/> |4 MB  <br/> |Tamaño máximo de un archivo Excel ubicado en un sitio o adjunto a un mensaje de correo electrónico que se analizará para la indexación. No se analizará ningún archivo Excel que sea mayor que este límite y el archivo o el mensaje de correo electrónico con los datos adjuntos del archivo se marcarán como sin indexar.  <br/> |
|Número máximo de datos adjuntos  <br/> |250  <br/> |Número máximo de archivos adjuntos a un mensaje de correo electrónico que se analizarán para la indexación. Si un mensaje tiene más de 250 datos adjuntos, los primeros 250 datos adjuntos se analizan e indexa, y el mensaje se marca como parcialmente indexado porque tenía datos adjuntos adicionales que no se analizaron.  <br/> |
|Profundidad máxima de datos adjuntos  <br/> |30  <br/> |Número máximo de datos adjuntos anidados que se analizan. Por ejemplo, si un mensaje de correo electrónico tiene otro mensaje adjunto y el mensaje adjunto tiene un documento de Word adjunto, el documento de Word y el mensaje adjunto se indexarán. Este comportamiento continuará hasta 30 datos adjuntos anidados.  <br/> |
|Número máximo de imágenes adjuntas  <br/> |0  <br/> |El analizador omite una imagen adjunta a un mensaje de correo electrónico y no se indexa.  <br/> |
|Tiempo máximo dedicado al análisis de un elemento  <br/> |30 segundos  <br/> |Se dedica un máximo de 30 segundos a analizar un elemento para la indexación. Si el tiempo de análisis supera los 30 segundos, el elemento se marca como indizado parcialmente.  <br/> |
|Salida máxima del analizador  <br/> |2 millones de caracteres  <br/> |Cantidad máxima de salida de texto del analizador que se indexa. Por ejemplo, si el analizador extrajo 8 millones de caracteres de un documento, solo se indizan los dos primeros millones de caracteres.  <br/> |
|Número máximo de tokens de anotación  <br/> |2 millones  <br/> |Cuando se indexa un mensaje de correo electrónico, cada palabra se anota con instrucciones de procesamiento diferentes que especifican cómo se debe indexar esa palabra. Cada conjunto de instrucciones de procesamiento se denomina token de anotación. Para mantener la calidad del servicio en Office 365, hay un límite de 2 millones de tokens de anotación para un mensaje de correo electrónico.  <br/> |
|Tamaño máximo del cuerpo en el índice  <br/> |67 millones de caracteres  <br/> |Número total de caracteres en el cuerpo de un mensaje de correo electrónico y todos sus datos adjuntos. Cuando se indexa un mensaje de correo electrónico, todo el texto del cuerpo del mensaje y de todos los datos adjuntos se concatena en una sola cadena. El tamaño máximo de esta cadena indexada es de 67 millones de caracteres.  <br/> |
|Número máximo de tokens únicos en el cuerpo  <br/> |1 millón  <br/> |Como se explicó anteriormente, los tokens son el resultado de extraer texto del contenido, quitar signos de puntuación y espacios y, a continuación, dividirlo en palabras (denominadas tokens) que se almacenan en el índice. Por ejemplo, la frase  `"cat, mouse, bird, dog, dog"` contiene 5 tokens. Pero solo 4 de ellos son tokens únicos. Hay un límite de 1 millón de tokens únicos por mensaje de correo electrónico, lo que ayuda a evitar que el índice se vuelva demasiado grande con tokens aleatorios.  <br/> |
||||

## <a name="more-information-about-partially-indexed-items"></a>Más información sobre los elementos parcialmente indizados

- Como se indicó anteriormente, dado que las propiedades de mensajes y documentos y sus metadatos están indexados, una búsqueda de palabras clave podría devolver resultados si esa palabra clave aparece en los metadatos indizados. En cambio, la misma búsqueda de palabra clave podría no devolver el mismo elemento si la palabra clave solo aparece en el contenido de un elemento con un tipo de archivo no admitido. En este caso, el elemento se devolvería como un elemento parcialmente indexado.

- Si se incluye un elemento parcialmente indexado en los resultados de la búsqueda porque coincidió con los criterios de consulta de búsqueda, no se incluirá como un elemento parcialmente indexado en las estadísticas de búsqueda estimadas. Además, no se incluirá con elementos indizados parcialmente al exportar los resultados de la búsqueda.

- Aunque se admite un tipo de archivo para la indexación y se indexa, puede haber errores de indexación o búsqueda que harán que un archivo se devuelva como un elemento indizado parcialmente. Por ejemplo, la búsqueda de un archivo de Excel grande podría ser parcialmente correcto (porque los primeros 4 MB están indizados), pero, a continuación, se produce un error porque se supera el límite de tamaño del archivo. En este caso, es posible que se devuelva el mismo archivo con los resultados de búsqueda y como un elemento parcialmente indexado.

- Los archivos que se cifran con [tecnologías de cifrado de Microsoft](encryption.md) y se adjuntan a un mensaje de correo electrónico que coincide con los criterios de una búsqueda se pueden obtener en versión preliminar y se descifrarán cuando se exporten. En este momento, los archivos cifrados con tecnologías de cifrado de Microsoft (y almacenados en SharePoint o OneDrive para la Empresa) se indizan parcialmente.

- Los mensajes de correo electrónico cifrados con S/MIME se indizan parcialmente. Esto incluye los mensajes cifrados con o sin datos adjuntos.

- Los mensajes de correo electrónico protegidos mediante Azure Rights Management se indexan y se incluirán en los resultados de búsqueda si coinciden con la consulta de búsqueda. Los mensajes de correo electrónico protegidos con derechos se descifran y se pueden obtener en vista previa y exportar. Esta funcionalidad requiere que se le asigne el rol Descifrado de RMS, que se asigna de forma predeterminada al grupo de roles administrador de exhibición de documentos electrónicos.

- Si crea una suspensión basada en consultas asociada a un caso de exhibición de documentos electrónicos, todos los elementos indizados parcialmente se colocan en suspensión. Esto incluye elementos parcialmente indexados que no coinciden con los criterios de consulta de búsqueda para la suspensión. Para obtener más información sobre cómo crear retenciones de exhibición de documentos electrónicos basadas en consultas, vea [Crear una suspensión de eDiscovery](create-ediscovery-holds.md).

## <a name="see-also"></a>Vea también

[Investigación de elementos parcialmente indexados en eDiscovery](investigating-partially-indexed-items-in-ediscovery.md)
