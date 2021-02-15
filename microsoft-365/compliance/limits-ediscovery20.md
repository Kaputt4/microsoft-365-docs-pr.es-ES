---
title: Límites de eDiscovery avanzado
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Obtenga información sobre los límites de casos, los límites de indización y los límites de búsqueda en vigor para la solución de eDiscovery avanzado en Microsoft 365.
ms.openlocfilehash: 6994a3511b97e9209491fa61a8c6f9bc147b6b87
ms.sourcegitcommit: 1b30ac6e05906c8a014b1fed33fc71e1821f6ad2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2021
ms.locfileid: "50044636"
---
# <a name="limits-in-advanced-ediscovery"></a>Límites de eDiscovery avanzado

En este artículo se describen los límites de la solución de eDiscovery avanzado en Microsoft 365.

## <a name="case-and-review-set-limits"></a>Límites de conjunto de casos y revisión

En la tabla siguiente se enumeran los límites de casos y conjuntos de revisión en eDiscovery avanzado.

| Descripción del límite | Límite |
|:-----|:-----|
|Número total de documentos que se pueden agregar a un caso (para todos los conjuntos de revisión de un caso).  <br/> |3 millones <br/> |
|Tamaño total de archivo por conjunto de carga. Esto incluye la carga que no es de Office 365 en un conjunto de revisión.  <br/> |300 GB <br/> |
|Cantidad total de datos cargados en todos los conjuntos de revisión de la organización por día.<br/> |2 TB <br/> |
|Número máximo de cargas por caso.  <br/> |200 <br/> |
|Número máximo de conjuntos de revisión por caso.  <br/> |20 <br/> |
|Número máximo de grupos de etiquetas por caso.  <br/> |1000 <br/> |
|Número máximo de etiquetas por caso.  <br/> |1000 <br/> |
|||

## <a name="indexing-limits"></a>Límites de indexación

En la tabla siguiente se enumeran los límites de indización en eDiscovery avanzado.

| Descripción del límite | Límite |
  |:-----|:-----|
  |Número máximo de caracteres extraídos de un único archivo.  <br/> |10 millones<sup>1</sup> <br/> |
  |Tamaño máximo de un único archivo.   <br/> |100 MB<sup>1</sup> <br/> |
  |Profundidad máxima de los elementos incrustados en un documento.  <br/> |25<sup>1</sup> <br/> |
  |Tamaño máximo de los archivos procesados por el reconocimiento óptico de caracteres (OCR).  <br/> |24 MB<sup>1</sup> <br/> 
  |Número máximo de trabajos de indización por organización y día. <br/> |10<sup>6</sup> <br/>|  
|||

## <a name="search-limits"></a>Límites de búsqueda

Los límites descritos en esta sección están  relacionados con el uso de la herramienta de búsqueda en la pestaña Búsquedas para recopilar datos para un caso. Para obtener más información, [vea Recopilar datos para un caso en eDiscovery avanzado.](collecting-data-for-ediscovery.md)

| Descripción del límite | Límite |
|:-----|:-----|
|Número máximo de buzones o sitios que se pueden buscar en una sola búsqueda. |Sin límite|
|Número máximo de búsquedas que se pueden ejecutar al mismo tiempo. |Sin límite |
|Número máximo de búsquedas que un solo usuario puede iniciar al mismo tiempo. |10   | 
|Número máximo de caracteres para una consulta de búsqueda (incluidos operadores y condiciones). |10 000 &nbsp; <sup>2</sup>|
|Número mínimo de caracteres alfa para caracteres comodín de prefijo; por ejemplo, **one \** _ o _*set \**_.|3  |  
|Número máximo de variantes devueltas al usar caracteres comodín de prefijo para buscar una frase exacta o cuando se usa un carácter comodín de prefijo y el operador booleano _ *NEAR**. |10 000 &nbsp; <sup>3</sup>|
|Número máximo de elementos por buzón de usuario que se muestran en la página de vista previa para las búsquedas. Se muestran los elementos más recientes. |100|
|Número máximo de elementos de todos los buzones que se muestran en la página de vista previa para las búsquedas.|1,000|
|Número máximo de buzones que se pueden obtener una vista previa de los resultados de la búsqueda.  Si hay más de 1000 buzones que contienen elementos que coinciden con la consulta de búsqueda, solo los 1.000 buzones con más resultados están disponibles para la vista previa.|1,000|
|Número máximo de elementos de sitios de SharePoint y OneDrive para la Empresa que se muestran en la página de vista previa para búsquedas. Se muestran los elementos más recientes. |200|
|Número máximo de sitios de SharePoint y OneDrive para la Empresa que se pueden obtener una vista previa de los resultados de búsqueda. Si hay más de 200 sitios que contienen elementos que coinciden con la consulta de búsqueda, solo los 200 sitios principales con más resultados están disponibles para la vista previa.|200|
|Número máximo de elementos por buzón de carpetas públicas que se muestran en la página de vista previa para las búsquedas. |100|
|Número máximo de elementos encontrados en todos los elementos de buzón de carpetas públicas que se muestran en la página de vista previa para las búsquedas. |200|
|Número máximo de buzones de carpetas públicas que se pueden obtener una vista previa de los resultados de la búsqueda. Si hay más de 500 buzones de carpetas públicas que contienen elementos que coinciden con la consulta de búsqueda, solo los 500 buzones con más resultados están disponibles para la vista previa.|500|
|||

## <a name="viewer-limits"></a>Límites de visor

| Descripción del límite | Límite |
|:-----|:-----|
|Tamaño máximo del archivo de Excel que se puede ver en el visor nativo.  <br/> |4 MB  <br/> |
|||

## <a name="export-limits"></a>Límites de exportación

| Descripción del límite | Límite |
|:-----|:-----|
|Tamaño máximo de una única exportación.|3 millones de documentos o 100 GB, lo que sea más pequeño|
|Cantidad máxima de datos en un solo día. | 2 TB |
|Máximo de exportaciones simultáneas en la organización. | 10 <sup>4</sup> |
|Máximo de exportaciones simultáneas por usuario. | 3  |
|Tamaño máximo de un único archivo PST. | 10 GB |
|Máximo de exportaciones simultáneas por conjunto de revisión. | 1  |
|||

## <a name="review-set-download-limits"></a>Revisar los límites de descarga establecidos

| Descripción del límite | Límite |
|:-----|:-----|
|Tamaño total del archivo o número máximo de documentos descargados de un conjunto de revisión.  <br/> |3 MB o 50 documentos <sup>5</sup>|
|||

<br/>
<br/>

> [!NOTE]
> <sup>1 Cualquier</sup> elemento que supere un único límite de archivos se mostrará como un error de procesamiento.
>
> <sup>2</sup> Al buscar en ubicaciones de SharePoint y OneDrive para la Empresa, los caracteres de las direcciones URL de los sitios en los que se busca tienen en cuenta este límite.
>
> <sup>3</sup> Para consultas que no son frases (un valor de palabra clave que no usa comillas dobles) usamos un índice de prefijo especial. Esto nos indica que una palabra se produce en un documento, pero no donde se produce en el documento. Para realizar una consulta de frase (un valor de palabra clave con comillas dobles), debemos comparar la posición dentro del documento de las palabras de la frase. Esto significa que no podemos usar el índice de prefijo para las consultas de frases. En este caso, ampliamos internamente la consulta con todas las palabras posibles a las que se expande el prefijo; por ejemplo, **la hora _ puede \* *expandirse a _*"hora O temporizador O horas O horaX O timeboxed OR ..."**. El límite de 10.000 es el número máximo de variantes a las que se puede expandir la palabra, no el número de documentos que coinciden con la consulta. Para los términos que no son frases no hay ningún límite superior.
>
> <sup>4</sup> Este límite se comparte en todas las herramientas de exhibición de documentos electrónicos. Esto significa que las exportaciones simultáneas en búsqueda de contenido, eDiscovery principal y eDiscovery avanzado se aplican a este límite.
>
> <sup>5 Este</sup> límite se aplica a la descarga de documentos seleccionados desde un conjunto de revisión. No se aplica a la exportación de documentos desde un conjunto de revisión. Para obtener más información acerca de cómo descargar y exportar documentos, vea Exportar datos [de casos en eDiscovery avanzado.](exporting-data-ediscover20.md)
>
> <sup>6 Límites</sup> de indización por organización y día. Como solución alternativa, puede seleccionar varios  administradores en la pestaña  Orígenes de datos en un caso y, a continuación, hacer clic en Actualizar índice para evitar crear un trabajo de índice independiente para cada administrador. 
