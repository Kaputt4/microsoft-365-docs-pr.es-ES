---
title: Límites de búsqueda de contenido y exhibición de documentos electrónicos principal en el centro de cumplimiento
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 78fe3147-1979-4c41-83bb-aeccf244368d
description: Obtenga información sobre los límites vigentes para la característica de búsqueda de contenido en el Centro de cumplimiento de Microsoft 365, como el número máximo de búsquedas simultáneas. Estos límites de búsqueda también se aplican a las búsquedas asociadas con los casos principales de exhibición de documentos electrónicos.
ms.openlocfilehash: 23751fd62b2d96400d8184faa0d8d74b06b68906
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840497"
---
# <a name="limits-for-content-search"></a>Límites de la búsqueda de contenido 
Se aplican varios límites a la herramienta de búsqueda de contenido en el Centro de cumplimiento de Microsoft 365. Esto incluye las búsquedas que se ejecutan en **la** página búsqueda de contenido y las búsquedas asociadas a un caso de exhibición de documentos electrónicos en la página **de exhibición** de documentos electrónicos principal. Estos límites ayudan a mantener el estado y la calidad de los servicios proporcionados a las organizaciones. También hay límites relacionados con la indización de mensajes de correo electrónico en Exchange Online para la búsqueda. No puede modificar los límites de la búsqueda de contenido o la indización de correo electrónico, pero debe conocerlos para poder tener en cuenta estos límites a la hora de planear, ejecutar y solucionar problemas de búsquedas de contenido.
  
## <a name="search-limits"></a>Límites de búsqueda

En la tabla siguiente se enumeran los límites de búsqueda al usar la herramienta de búsqueda de contenido en el Centro de cumplimiento de Microsoft 365 y para las búsquedas asociadas a un caso de exhibición de documentos electrónicos principal.
  
| Descripción del límite | Límite |
|:-----|:-----|
|El número máximo de buzones o sitios que se pueden buscar en una sola búsqueda  <br/> |Sin límite <sup>1</sup> <br/> |
|El número máximo de búsquedas que se pueden ejecutar al mismo tiempo en la organización.  <br/> |30  <br/> |
|El número máximo de búsquedas que un único usuario puede iniciar al mismo tiempo. Este límite es muy probable cuando el usuario intenta iniciar varias búsquedas mediante el comando **Get-ComplianceSearch \| Start-ComplianceSearch** en PowerShell del Centro de seguridad & cumplimiento.  <br/> |10   <br/> |
|El número máximo de elementos por buzón de usuario que se muestran en la página de vista previa al obtener una vista previa de los resultados de búsqueda de contenido.  <br/> |100  <br/> |
|El número máximo de elementos encontrados en todos los buzones de usuario que se muestran en la página de vista previa al obtener una vista previa de los resultados de la búsqueda. Se muestran los elementos más recientes.  <br/> |1,000  <br/> |
|El número máximo de buzones de usuario de los que se puede obtener una vista previa de los resultados de búsqueda. Si hay más de 1000 buzones que contienen contenido que coincide con la consulta de búsqueda, solo estarán disponibles los primeros 1000 buzones con la mayoría de resultados de búsqueda para la vista previa.  <br/> |1,000  <br/> |
|El número máximo de elementos encontrados en los sitios de SharePoint y OneDrive para la Empresa que se muestran en la página de vista previa al obtener una vista previa de los resultados de la búsqueda. Se muestran los elementos más recientes.  <br/> |200  <br/> |
|El número máximo de sitios (en SharePoint y OneDrive para la Empresa) que se pueden obtener una vista previa de los resultados de la búsqueda. Si hay más de 200 sitios totales que contienen contenido que coincide con la consulta de búsqueda, solo los 200 sitios principales con más resultados de búsqueda estarán disponibles para obtener una vista previa.  <br/> |200  <br/> |
|El número máximo de elementos por buzón de carpetas públicas que se muestran en la página de vista previa al obtener una vista previa de los resultados de la búsqueda de contenido.  <br/> |100  <br/> |
|El número máximo de elementos encontrados en todos los buzones de carpetas públicas que se muestran en la página de vista previa al obtener una vista previa de los resultados de búsqueda de contenido.  <br/> |200  <br/> |
|El número máximo de buzones públicos que se pueden obtener una vista previa de los resultados de la búsqueda. Si hay más de 500 buzones de carpetas públicas que contienen contenido que coincide con la consulta de búsqueda, solo los 500 buzones de carpetas públicas con más resultados de búsqueda estarán disponibles para la vista previa.  <br/> |500  <br/> |
|El número máximo de caracteres para la consulta de búsqueda (incluidos operadores y condiciones) para una búsqueda.  <br/><br/> **Nota:** Este límite tiene efecto después de expandir la consulta, lo que significa que la consulta se expandirá con cada una de las palabras clave. Por ejemplo, si una consulta de búsqueda tiene 15 palabras clave y parámetros y condiciones adicionales, la consulta se expande 15 veces, cada una con los demás parámetros y condiciones de la consulta. Por lo tanto, aunque el número de caracteres de la consulta de búsqueda puede estar por debajo del límite, es la consulta expandida la que puede contribuir a superar este límite.  <br/> |**Buzones:** 10.000  <br/> **Sitios:** 4.000 al buscar en todos los sitios o 2.000 al buscar hasta 20 sitios <sup>2</sup> <br/> |
|Número máximo de variantes devueltas al usar un carácter comodín de prefijo para buscar una frase exacta en una consulta de búsqueda o cuando se usa un carácter comodín de prefijo y el operador **booleano NEAR.**  <br/> |10 000 <sup>3</sup> <br/> |
|El número mínimo de caracteres alfa para caracteres comodín de prefijo; por ejemplo,  `time*`  `one*` , o  `set*` .  <br/> |3   <br/> |
|El número máximo de buzones de una búsqueda en el que puede eliminar elementos realizando una acción de "búsqueda y depuración" (mediante el comando **New-ComplianceSearchAction -Purge).** Si la búsqueda para la que está realizando una acción de depuración tiene más buzones de origen que este límite, se producirá un error en la acción de depuración. Para obtener más información acerca de la búsqueda y depuración, vea Buscar y eliminar mensajes de [correo electrónico en su organización.](search-for-and-delete-messages-in-your-organization.md)  <br/> |50 000  <br/> |
|El número máximo de ubicaciones en una búsqueda desde la que se pueden exportar elementos. Si la búsqueda que está exportando tiene más ubicaciones que este límite, se producirá un error en la exportación. Para obtener más información, vea [Exportar resultados de búsqueda de contenido.](export-search-results.md)  <br/> |100,000  <br/> |
|||

> [!NOTE]
> <sup>1</sup> Aunque puede buscar en un número ilimitado de buzones en una sola búsqueda, solo puede descargar los resultados de búsqueda exportados de un máximo de 100 000 buzones mediante la herramienta de exportación de exhibición de documentos electrónicos en el Centro de cumplimiento de Microsoft 365. Para descargar los resultados de la búsqueda de más de 100 000 buzones, debe usar PowerShell del Centro de seguridad & cumplimiento. Para obtener más información y un script de ejemplo, vea Exportar resultados de más de [100 000 buzones.](export-search-results.md#exporting-results-from-more-than-100000-mailboxes) <br/><br/> <sup>2 Al</sup> buscar en ubicaciones de SharePoint y OneDrive para la Empresa, los caracteres de las direcciones URL de los sitios en los que se busca se cuentan con este límite. <br/><br/> <sup>3</sup> Para consultas que no son frases (un valor de palabra clave que no usa comillas dobles) usamos un índice de prefijo especial. Esto nos indica que una palabra se produce en un documento, pero no donde se produce en el documento. Para realizar una consulta de frase (un valor de palabra clave con comillas dobles), debemos comparar la posición dentro del documento de las palabras de la frase. Esto significa que no podemos usar el índice de prefijo para las consultas de frases. En este caso, ampliamos internamente la consulta con todas las palabras posibles a las que se expande el prefijo; por ejemplo,  `"time*"` puede expandirse a  `"time OR timer OR times OR timex OR timeboxed OR …"` . 10.000 es el número máximo de variantes a las que se puede expandir la palabra, no el número de documentos que coinciden con la consulta. Para los términos que no son frases no hay ningún límite superior. 
  
## <a name="export-limits"></a>Límites de exportación
En la tabla siguiente se enumeran los límites al exportar los resultados de una búsqueda de contenido. Estos límites también se aplican al exportar contenido de un caso de exhibición de documentos electrónicos principal.

|Descripción del límite|Límite|
|:-----|:-----|
|Cantidad máxima de datos exportables de una sola búsqueda  <br/><br/> **Nota:** Si los resultados de la búsqueda son superiores a 2 TB, considere la posibilidad de usar intervalos de fechas u otros tipos de filtros para reducir el tamaño total de los resultados de la búsqueda. <br/>  |2 TB  <br/> | 
|Máximo que una organización puede exportar en un solo día <br/><br/> **Nota:** Este límite se restablece diariamente a las 12:00 UTC <br/> |2 TB <br/> |
|Máximo de exportaciones simultáneas que se pueden ejecutar al mismo tiempo en la organización <br/><br/> **Nota:** La ejecución de **una exportación de solo** informe cuenta con respecto al total de exportaciones simultáneas de la organización. Si tres usuarios realizan 3 exportaciones cada uno, solo se puede realizar una exportación más. Independientemente de si exporta un informe o resultados de búsqueda, no se pueden realizar otras exportaciones hasta que se haya completado una.   <br/> |10  <br/> |
|Máximo de exportaciones que puede ejecutar un solo usuario en cualquier momento <br/> |3  <br/> |
|Número máximo de buzones de correo para los resultados de búsqueda que se pueden descargar con la herramienta de exportación de exhibición de documentos electrónicos <br/><br/> **Nota:** Para descargar los resultados de la búsqueda de más de 100 000 buzones, debe usar PowerShell del Centro de seguridad & cumplimiento. Para obtener instrucciones, consulte Exportar resultados de más de [100 000 buzones.](export-search-results.md#exporting-results-from-more-than-100000-mailboxes) <br/> | 100,000 <br/>|
|Tamaño máximo del archivo PST que se puede exportar <br/><br/> **Nota:** Si los resultados de la búsqueda del buzón de un usuario tienen más de 10 GB, los resultados de la búsqueda del buzón se exportarán en dos (o más) archivos PST independientes. Si decide exportar todos los resultados de la búsqueda en un único archivo PST, el archivo PST se mostrará en archivos PST adicionales si el tamaño total de los resultados de la búsqueda es superior a 10 GB. Si desea cambiar este tamaño predeterminado, puede editar el Registro de Windows en el equipo que usa para exportar los resultados de la búsqueda. Vea [Cambiar el tamaño de los archivos PST al exportar los resultados de la búsqueda de exhibición de documentos electrónicos.](change-the-size-of-pst-files-when-exporting-results.md) Los resultados de la búsqueda de un buzón específico no se dividirán entre varios archivos PST a menos que el contenido de un único buzón sea de más de 10 GB. Si decidió exportar los resultados de la búsqueda en un archivo PST para que contenga todos los mensajes en una sola carpeta y los resultados de la búsqueda sean superiores a 10 GB, los elementos siguen organizados en orden cronológico, por lo que se mostrarán en archivos PST adicionales en función de la fecha de envío.<br/> | 10 GB <br/> |
|Tasa a la que se cargan los resultados de búsqueda de buzones y sitios en una ubicación de Azure Storage proporcionada por Microsoft. |Máximo de 2 GB por hora|
|||

## <a name="indexing-limits-for-email-messages"></a>Límites de indización para mensajes de correo electrónico

En la tabla siguiente se describen los límites de indización que pueden provocar que se devuelva un mensaje de correo electrónico como un elemento no indexado o un elemento parcialmente indizado en los resultados de una búsqueda de contenido.
  
| Límite de indización | Valor máximo | Descripción |
|:-----|:-----|:-----|
|Tamaño máximo de datos adjuntos|150 MB  <br/> |El tamaño máximo de un archivo adjunto de correo electrónico que se analizará para la indización. Los datos adjuntos que sean mayores que este límite no se analizarán para la indización y el mensaje con los datos adjuntos se marcará como parcialmente indizado.  <br/> <br/>**Nota:** El análisis es el proceso en el que el servicio de indización extrae texto de los datos adjuntos, quita caracteres innecesarios como signos de puntuación y espacios y, a continuación, divide el texto en palabras (en un proceso denominado tokenización), que luego se almacenan en el índice.           |
|Número máximo de datos adjuntos  <br/> |250  <br/> |El número máximo de archivos adjuntos a un mensaje de correo electrónico que se analizarán para la indización. Si un mensaje tiene más de 250 datos adjuntos, los primeros 250 datos adjuntos se analizan e indizan, y el mensaje se marca como parcialmente indizado porque tenía datos adjuntos adicionales que no se analizaron.  <br/> |
|Profundidad máxima de datos adjuntos  <br/> |30  <br/> |El número máximo de datos adjuntos anidados que se analizan. Por ejemplo, si un mensaje de correo electrónico tiene otro mensaje adjunto y el mensaje adjunto tiene un documento de Word adjunto, se indizarán el documento de Word y el mensaje adjunto. Este comportamiento continuará para hasta 30 datos adjuntos anidados.  <br/> |
|Número máximo de imágenes adjuntas  <br/> |0  <br/> |El analizador omite una imagen adjunta a un mensaje de correo electrónico y no se indiza.  <br/> |
|Tiempo máximo dedicado a analizar un elemento  <br/> |30 segundos  <br/> |Se dedica un máximo de 30 segundos al análisis de un elemento para la indización. Si el tiempo de análisis supera los 30 segundos, el elemento se marca como parcialmente indizado.  <br/> |
|Salida máxima del analizador  <br/> |2 millones de caracteres  <br/> |La cantidad máxima de salida de texto del analizador indizado. Por ejemplo, si el analizador extrajo 8 millones de caracteres de un documento, solo se indizarán los primeros 2 millones de caracteres.  <br/> |
|Máximo de tokens de anotación  <br/> |2 millones  <br/> |Cuando se indiza un mensaje de correo electrónico, cada palabra se anota con diferentes instrucciones de procesamiento que especifican cómo se debe indizar esa palabra. Cada conjunto de instrucciones de procesamiento se denomina token de anotación. Para mantener la calidad de servicio en Office 365, hay un límite de 2 millones de tokens de anotación para un mensaje de correo electrónico.  <br/> |
|Tamaño máximo del cuerpo en el índice  <br/> |67 millones de caracteres  <br/> |El número total de caracteres en el cuerpo de un mensaje de correo electrónico y todos sus datos adjuntos. Cuando se indiza un mensaje de correo electrónico, todo el texto del cuerpo del mensaje y de todos los datos adjuntos se concatena en una sola cadena. El tamaño máximo de esta cadena indizada es de 67 millones de caracteres.  <br/> |
|Máximo de tokens únicos en el cuerpo  <br/> |1 millón  <br/> |Como se ha explicado anteriormente, los tokens son el resultado de extraer texto del contenido, quitar signos de puntuación y espacios y, a continuación, dividirlo en palabras (denominadas tokens) almacenadas en el índice. Por ejemplo, la frase  `"cat, mouse, bird, dog, dog"` contiene 5 tokens. Pero solo 4 de estos son tokens únicos. Hay un límite de 1 millón de tokens únicos por mensaje de correo electrónico, lo que ayuda a evitar que el índice se haga demasiado grande con tokens aleatorios.  <br/> |
|||
  
## <a name="more-information"></a>Más información

Existen límites adicionales relacionados con diferentes aspectos de la búsqueda de contenido, como la indización de contenido. Para obtener más información acerca de estos límites, consulte los siguientes temas:

- [Elementos parcialmente indizados en la búsqueda de contenido](partially-indexed-items-in-content-search.md)

- [Investigar elementos parcialmente indizados en eDiscovery](investigating-partially-indexed-items-in-ediscovery.md)

- [Límites de búsqueda para SharePoint Online](https://docs.microsoft.com/sharepoint/search-limits)

Para obtener información acerca de las búsquedas de contenido, vea:
  
- [Búsqueda de contenido en Microsoft 365](content-search.md)

- [Buscar contenido en un caso de exhibición de documentos electrónicos principal](search-for-content-in-core-ediscovery.md)

- [Consultas de palabras clave y condiciones de búsqueda para la búsqueda de contenido](keyword-queries-and-search-conditions.md)

Para ver los límites de casos relacionados con eDiscovery principal y eDiscovery avanzado, vea:

- [Límites de eDiscovery principal](limits-core-ediscovery.md)

- [Límites de eDiscovery avanzado](limits-ediscovery20.md)
