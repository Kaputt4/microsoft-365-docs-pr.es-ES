---
title: Límites de búsqueda de contenido y exhibición de documentos electrónicos (estándar) en el centro de cumplimiento
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 78fe3147-1979-4c41-83bb-aeccf244368d
description: Obtenga información sobre los límites vigentes para las características búsqueda de contenido y exhibición de documentos electrónicos (estándar) en el portal de cumplimiento Microsoft Purview.
ms.openlocfilehash: 52239b2f82b46feecc18685b309c1420255b9039
ms.sourcegitcommit: 433f5b448a0149fcf462996bc5c9b45d17bd46c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2022
ms.locfileid: "67819279"
---
# <a name="limits-for-ediscovery-search"></a>Límites de búsqueda de eDiscovery

Se aplican varios límites a las herramientas de búsqueda de exhibición de documentos electrónicos en el portal de cumplimiento Microsoft Purview. Esto incluye las búsquedas que se ejecutan en la página **Búsqueda de contenido** y las búsquedas asociadas a un caso de exhibición de documentos electrónicos en la página **eDiscovery (estándar).** Estos límites ayudan a mantener la salud y la calidad de los servicios proporcionados a las organizaciones. También hay límites relacionados con la indexación de mensajes de correo electrónico en Exchange Online para la búsqueda. No se pueden modificar los límites de las búsquedas de exhibición de documentos electrónicos o la indexación de correo electrónico, pero debe tenerlos en cuenta para que pueda tener estos límites en cuenta al planear, ejecutar y solucionar problemas de búsquedas de eDiscovery.

Para conocer los límites relacionados con la herramienta Microsoft Purview eDiscovery (Premium), consulte [Límites en eDiscovery (Premium)](limits-ediscovery20.md)

## <a name="search-limits"></a>Límites de búsqueda

En la tabla siguiente se enumeran los límites de búsqueda al usar la herramienta de búsqueda de contenido en el portal de cumplimiento y las búsquedas asociadas a un caso de Microsoft Purview eDiscovery (estándar).

<br>

****

|Descripción del límite|Límite|
|---|---|
|Número máximo de buzones o sitios que se pueden buscar en una sola búsqueda|Sin límite <sup>1</sup>|
|El número máximo de elementos que se encuentran en todos los buzones de usuario que posiblemente se pueden mostrar en la página de vista previa al obtener una vista previa de los resultados de la búsqueda. Se muestran los elementos más recientes.|1000 <sup>2</sup>|
|El número máximo de buzones de usuario de los que se puede obtener una vista previa de los resultados de búsqueda. Si hay más de 1000 buzones que contienen contenido que coincide con la consulta de búsqueda, como máximo, solo los 1000 buzones principales con la mayoría de los resultados de búsqueda estarán disponibles para la versión preliminar.|1,000|
|El número máximo de elementos que se encuentran en SharePoint y OneDrive para la Empresa sitios que se muestran en la página de vista previa al obtener una vista previa de los resultados de la búsqueda. Se muestran los elementos más recientes.|200|
|Número máximo de sitios (en SharePoint y OneDrive para la Empresa) que se pueden obtener en vista previa para los resultados de la búsqueda. Si hay más de 200 sitios totales que contienen contenido que coincide con la consulta de búsqueda, solo los 200 sitios principales con más resultados de búsqueda estarán disponibles para la versión preliminar.|200|
|Número máximo de elementos por buzón de carpeta pública que se muestran en la página de vista previa al obtener una vista previa de los resultados de la búsqueda de contenido.|100|
|El número máximo de elementos que se encuentran en todos los buzones de carpeta pública que se muestran en la página de vista previa al obtener una vista previa de los resultados de la búsqueda de contenido.|200|
|Número máximo de buzones de carpetas públicas que se pueden obtener en vista previa para los resultados de la búsqueda. Si hay más de 500 buzones de carpetas públicas que contienen contenido que coincide con la consulta de búsqueda, solo los 500 buzones de carpetas públicas principales con la mayoría de los resultados de búsqueda estarán disponibles para la versión preliminar.|500|
|Tamaño máximo de un elemento que se puede ver en la página de vista previa.|10 000 000 bytes (aproximadamente 9,5 MB)|
|Número máximo de caracteres de la consulta de búsqueda (incluidos los operadores y las condiciones) de una búsqueda. <p> **Nota:** Este límite surte efecto después de expandir la consulta e incluya caracteres de la consulta de palabras clave, los filtros de permisos de búsqueda aplicados al usuario y las direcciones URL de todas las ubicaciones del sitio. Esto significa que la consulta se expandirá en cada una de las palabras clave. Por ejemplo, si una consulta de búsqueda tiene 15 palabras clave y parámetros y condiciones adicionales, la consulta se expande 15 veces, cada una con los otros parámetros y condiciones de la consulta. Por lo tanto, aunque el número de caracteres de la consulta de búsqueda puede estar por debajo del límite, es la consulta expandida la que puede contribuir a superar este límite.|**Buzones:** 10 000. <p> **Sitios:** 4000 al buscar en todos los sitios o 2000 al buscar hasta 20 sitios. <sup>3</sup>|
|Número máximo de variantes devueltas cuando se usa un carácter comodín de prefijo para buscar una frase exacta en una consulta de búsqueda o cuando se usa un carácter comodín de prefijo y el operador booleano **NEAR** .|10 000 <sup>4</sup>|
|Número mínimo de caracteres alfa para los caracteres comodín de prefijo; por ejemplo, `time*`, `one*`o `set*`.|3|
|El número máximo de buzones de una búsqueda en la que puede eliminar elementos realizando una acción de "búsqueda y purga" (mediante el comando **New-ComplianceSearchAction -Purge** ). Si la búsqueda para la que está realizando una acción de purga tiene más buzones de origen que este límite, se producirá un error en la acción de purga. Para obtener más información sobre la búsqueda y purga, consulte [Búsqueda y eliminación de mensajes de correo electrónico en su organización](search-for-and-delete-messages-in-your-organization.md).|50 000|
|Número máximo de ubicaciones en una búsqueda desde la que puede exportar elementos. Si la búsqueda que va a exportar tiene más ubicaciones que este límite, se producirá un error en la exportación. Para obtener más información, vea [Exportar resultados de búsqueda de contenido](export-search-results.md).|100 000|

> [!NOTE]
> <sup>1</sup> Aunque puede buscar un número ilimitado de buzones en una sola búsqueda, solo puede descargar los resultados de búsqueda exportados de un máximo de 100 000 buzones mediante la herramienta de exportación de eDiscovery en el portal de cumplimiento.
>
> <sup>2</sup> La intención de la página de vista previa es mostrar un ejemplo limitado de los resultados. Incluso para búsquedas masivas con miles de resultados, el número de elementos que se muestran en la página de vista previa puede, y a menudo, ser mucho menor que el valor máximo posible de 1000. Para ver los resultados de búsqueda completos, debe exportar los resultados.
>
> <sup>3</sup> Al buscar ubicaciones de SharePoint y OneDrive para la Empresa, los caracteres de las direcciones URL de los sitios que se buscan se cuentan con este límite.
>
> <sup>4</sup> En el caso de las consultas sin frases (un valor de palabra clave que no usa comillas dobles), usamos un índice de prefijo especial. Esto nos indica que una palabra se produce en un documento, pero no donde se produce en el documento. Para realizar una consulta de frase (un valor de palabra clave con comillas dobles), es preciso comparar la posición dentro del documento para las palabras de la frase. Esto significa que no se puede usar el índice de prefijo para las consultas de frases. En este caso, ampliamos internamente la consulta con todas las palabras posibles a las que se expande el prefijo; por ejemplo, `"time*"` puede expandirse a `"time OR timer OR times OR timex OR timeboxed OR ..."`. 10.000 es el número máximo de variantes a las que se puede expandir la palabra, no el número de documentos que coinciden con la consulta. Para los términos que no son frases no hay ningún límite superior.

## <a name="search-times"></a>Horas de búsqueda

Microsoft recopila información de rendimiento para las búsquedas ejecutadas por todas las organizaciones. Aunque la complejidad de una consulta de búsqueda puede afectar al tiempo que lleva ejecutarla, en realidad, el factor más determinante es el número de buzones incluidos en la búsqueda. Aunque Microsoft no proporciona un contrato de nivel de servicio para los tiempos de búsqueda, en la tabla siguiente se enumeran los tiempos promedio de búsqueda de recopilación en función del número de buzones incluidos en la búsqueda.

<br>

****

|Número de buzones|Promedio de tiempo de búsqueda|
|---|---|
|100|30 segundos|
|1,000|45 segundos|
|10 000|4 minutos|
|25 000|10 minutos|
|50 000|20 minutos|
|100 000|25 minutos|

## <a name="export-limits"></a>Límites de exportación

En la tabla siguiente se enumeran los límites al exportar los resultados de una búsqueda de contenido. Estos límites también se aplican al exportar contenido desde un caso de exhibición de documentos electrónicos (estándar).

<br>

****

|Descripción del límite|Límite|
|---|---|
|Cantidad máxima de datos exportables de una sola búsqueda  <p> **Nota:** Si los resultados de la búsqueda superan los 2 TB, considere la posibilidad de usar intervalos de fechas u otros tipos de filtros para reducir el tamaño total de los resultados de la búsqueda.|2 TB|
|Máximo que una organización puede exportar en un solo día <p> **Nota:** Este límite se restablece diariamente a las 12:00 UTC|2 TB|
|Número máximo de buzones de correo para los resultados de búsqueda que se pueden descargar mediante la herramienta de exportación de eDiscovery|100 000|
|Tamaño máximo del archivo PST que se puede exportar <p> **Nota:** Si los resultados de la búsqueda del buzón de un usuario son mayores que 10 GB, los resultados de la búsqueda del buzón se exportarán en dos (o más) archivos PST independientes. Si decide exportar todos los resultados de búsqueda en un único archivo PST, el archivo PST se derramará en archivos PST adicionales si el tamaño total de los resultados de la búsqueda es mayor que 10 GB. Si desea cambiar este tamaño predeterminado, puede editar el Registro de Windows en el equipo que use para exportar los resultados de la búsqueda. Vea [Cambiar el tamaño de los archivos PST al exportar los resultados de búsqueda de eDiscovery](change-the-size-of-pst-files-when-exporting-results.md). Los resultados de la búsqueda de un buzón específico no se dividirán entre varios archivos PST a menos que el contenido de un solo buzón sea superior a 10 GB. Si decide exportar los resultados de la búsqueda en un archivo PST para que contenga todos los mensajes de una sola carpeta y los resultados de la búsqueda sean mayores que 10 GB, los elementos todavía se organizan en orden cronológico, por lo que se enviarán a archivos PST adicionales en función de la fecha de envío.|10 GB|
|Velocidad a la que se cargan los resultados de búsqueda de buzones y sitios en una ubicación de Azure Storage proporcionada por Microsoft.|Máximo de 2 GB por hora|

## <a name="indexing-limits-for-email-messages"></a>Límites de indexación de mensajes de correo electrónico

En la tabla siguiente se describen los límites de indexación que pueden dar lugar a que se devuelva un mensaje de correo electrónico como un elemento sin indexar o un elemento parcialmente indexado en los resultados de una búsqueda de contenido.

<br>

****

|Límite de indexación|Valor máximo|Descripción|
|---|---|---|
|Tamaño máximo de datos adjuntos|150 MB|Tamaño máximo de los datos adjuntos de un correo electrónico que se analizarán para la indexación. Los datos adjuntos que sean mayores que este límite no se analizarán para la indexación y el mensaje con los datos adjuntos se marcará como indizado parcialmente. <p> **Nota:** El análisis es el proceso en el que el servicio de indexación extrae texto de los datos adjuntos, quita caracteres innecesarios como signos de puntuación y espacios y, a continuación, divide el texto en palabras (en un proceso denominado tokenización) que, a continuación, se almacenan en el índice.|
|Número máximo de datos adjuntos|250|Número máximo de archivos adjuntos a un mensaje de correo electrónico que se analizarán para la indexación. Si un mensaje tiene más de 250 datos adjuntos, los primeros 250 datos adjuntos se analizan e indexa, y el mensaje se marca como parcialmente indexado porque tenía datos adjuntos adicionales que no se analizaron.|
|Profundidad máxima de datos adjuntos|30|Número máximo de datos adjuntos anidados que se analizan. Por ejemplo, si un mensaje de correo electrónico tiene otro mensaje adjunto y el mensaje adjunto tiene un documento de Word adjunto, el documento de Word y el mensaje adjunto se indexarán. Este comportamiento continuará hasta 30 datos adjuntos anidados.|
|Número máximo de imágenes adjuntas|0|El analizador omite una imagen adjunta a un mensaje de correo electrónico y no se indexa.|
|Tiempo máximo dedicado al análisis de un elemento|30 segundos|Se dedica un máximo de 30 segundos a analizar un elemento para la indexación. Si el tiempo de análisis supera los 30 segundos, el elemento se marca como indizado parcialmente.|
|Salida máxima del analizador|2 millones de caracteres|Cantidad máxima de salida de texto del analizador que se indexa. Por ejemplo, si el analizador extrajo 8 millones de caracteres de un documento, solo se indizan los dos primeros millones de caracteres.|
|Número máximo de tokens de anotación|2 millones|Cuando se indexa un mensaje de correo electrónico, cada palabra se anota con instrucciones de procesamiento diferentes que especifican cómo se debe indexar esa palabra. Cada conjunto de instrucciones de procesamiento se denomina token de anotación. Para mantener la calidad del servicio en Office 365, hay un límite de 2 millones de tokens de anotación para un mensaje de correo electrónico.|
|Tamaño máximo del cuerpo en el índice|67 millones de caracteres|Número total de caracteres en el cuerpo de un mensaje de correo electrónico y todos sus datos adjuntos. Cuando se indexa un mensaje de correo electrónico, todo el texto del cuerpo del mensaje y de todos los datos adjuntos se concatena en una sola cadena. El tamaño máximo de esta cadena indexada es de 67 millones de caracteres.|
|Número máximo de tokens únicos en el cuerpo|1 millón|Como se explicó anteriormente, los tokens son el resultado de extraer texto del contenido, quitar signos de puntuación y espacios y, a continuación, dividirlo en palabras (denominadas tokens) que se almacenan en el índice. Por ejemplo, la frase `"cat, mouse, bird, dog, dog"` contiene 5 tokens. Pero solo 4 de ellos son tokens únicos. Hay un límite de 1 millón de tokens únicos por mensaje de correo electrónico, lo que ayuda a evitar que el índice se vuelva demasiado grande con tokens aleatorios.|
|||

## <a name="jobs-limits"></a>Límites de trabajos

> [!NOTE]
> Los trabajos de eDiscovery (Premium) se cuentan para los límites de eDiscovery (Estándar). Por ejemplo, si tiene 50 trabajos en ejecución en eDiscovery (Premium), no podrá iniciar trabajos en eDiscovery (Estándar). Los trabajos de eDiscovery (Estándar) no cuentan para los límites de eDiscovery (Premium).

|Descripción|Límite|
|---|---|
|Número máximo de trabajos simultáneos en la organización.|50|
|Número máximo de trabajos simultáneos que un único usuario puede iniciar al mismo tiempo.|25|
|Número máximo de trabajos simultáneos en todo el inquilino (por ejemplo, búsquedas en todo el inquilino) en la organización.|5|
|Número máximo de trabajos simultáneos en todo el inquilino (por ejemplo, búsquedas en todo el inquilino) que un único usuario puede iniciar a la vez.|5|
|Número máximo de trabajos por día en la organización. <p> **Nota:** Este límite se restablece diariamente a las 12:00 UTC|500|

## <a name="more-information"></a>Más información

Hay límites adicionales relacionados con diferentes aspectos de la búsqueda de contenido, como la indexación de contenido. Para obtener más información sobre estos límites, consulte los temas siguientes:

- [Elementos parcialmente indizados en la búsqueda de contenido](partially-indexed-items-in-content-search.md)

- [Investigación de elementos parcialmente indexados en eDiscovery](investigating-partially-indexed-items-in-ediscovery.md)

- [Límites de búsqueda de SharePoint Online](/sharepoint/search-limits)

Para obtener información sobre las búsquedas de contenido, consulte:

- [Búsqueda de contenido en Microsoft 365](content-search.md)

- [Buscar contenido en un caso de exhibición de documentos electrónicos (estándar)](search-for-content-in-core-ediscovery.md)

- [Consultas de palabras clave y condiciones de búsqueda para la búsqueda de contenido](keyword-queries-and-search-conditions.md)

Para conocer los límites de mayúsculas y minúsculas relacionados con eDiscovery (Estándar) y eDiscovery (Premium), consulte:

- [Límites en eDiscovery (estándar)](limits-core-ediscovery.md)

- [Límites en eDiscovery (Premium)](limits-ediscovery20.md)
