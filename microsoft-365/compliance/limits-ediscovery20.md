---
title: Límites de eDiscovery avanzado
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Obtenga información sobre los límites de casos, los límites de indización y los límites de búsqueda en vigor para la solución Advanced eDiscovery en Microsoft 365.
ms.openlocfilehash: 335e40c6918fc33acc12082546b98f28c319c814
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244581"
---
# <a name="limits-in-advanced-ediscovery"></a>Límites de eDiscovery avanzado

En este artículo se describen los límites de la solución Advanced eDiscovery en Microsoft 365.

## <a name="case-and-review-set-limits"></a>Límites de conjunto de casos y revisión

En la tabla siguiente se enumeran los límites de los casos y los conjuntos de revisión de Advanced eDiscovery.

| Descripción del límite | Límite |
|:-----|:-----|
|Número total de documentos que se pueden agregar a un caso (para todos los conjuntos de revisión de un caso).  <br/> |3 millones <br/> |
|Tamaño total del archivo por conjunto de carga. Esto incluye la carga de Office 365 en un conjunto de revisión.  <br/> |300 GB <br/> |
|Cantidad total de datos cargados en todos los conjuntos de revisión de la organización por día.<br/> |2 TB <br/> |
|Número máximo de conjuntos de carga por caso.  <br/> |200 <br/> |
|Número máximo de conjuntos de revisión por caso.  <br/> |20 <br/> |
|Número máximo de grupos de etiquetas por caso.  <br/> |1000 <br/> |
|Número máximo de etiquetas por caso.  <br/> |1000 <br/> |
|Trabajos simultáneos máximos en la organización para agregar contenido a un conjunto de revisión. Estos trabajos se **denominan Agregar datos a un conjunto** de revisión y se muestran en la **pestaña** Trabajos en un caso.| 10 <sup>4</sup> |
|Trabajos simultáneos máximos para agregar contenido a un conjunto de opiniones por usuario. Estos trabajos se **denominan Agregar datos a un conjunto** de revisión y se muestran en la **pestaña** Trabajos en un caso. | 3 |
|||

## <a name="hold-limits"></a>Límites de retención

En la tabla siguiente se enumeran los límites para las retenciones asociadas con un Advanced eDiscovery caso.

| Descripción del límite | Límite |
|:-----|:-----|
|Número máximo de buzones en una única retención de casos. Este límite incluye el total combinado de buzones de usuario y los buzones asociados con grupos de Microsoft 365, Microsoft Teams y Yammer grupos. <br/> |1,000  <br/> |
|Número máximo de sitios en una única retención de casos. Este límite incluye el total combinado de sitios OneDrive para la Empresa, SharePoint y los sitios asociados con grupos de Microsoft 365, Microsoft Teams y Yammer grupos.  <br/> |100  <br/> |

## <a name="indexing-limits"></a>Límites de indexación

En la tabla siguiente se enumeran los límites de indización en Advanced eDiscovery.

| Descripción del límite | Límite |
|:-----|:-----|
|Número máximo de caracteres extraídos de un único archivo.  <br/> |10 millones<sup>1</sup> <br/> |
|Tamaño máximo de un solo archivo.   <br/> |100 MB<sup>1</sup> <br/> |
|Profundidad máxima de los elementos incrustados en un documento.  <br/> |25<sup>1</sup> <br/> |
|Tamaño máximo de los archivos procesados por reconocimiento óptico de caracteres (OCR).  <br/> |24 MB<sup>1</sup> <br/> 
|Número máximo de trabajos de indización por organización y día. <br/> |10<sup>6</sup> <br/>|  
|||

## <a name="search-limits"></a>Límites de búsqueda

Los límites descritos en esta sección están relacionados con el uso de la herramienta de búsqueda en la pestaña **Búsquedas** para recopilar datos de un caso. Para obtener más información, vea [Recopilar datos para un caso en Advanced eDiscovery](collecting-data-for-ediscovery.md).

| Descripción del límite | Límite |
|:-----|:-----|
|Número máximo de buzones o sitios que se pueden buscar en una sola búsqueda. |Sin límite|
|Número máximo de búsquedas que se pueden ejecutar al mismo tiempo. |Sin límite |
|Número máximo de búsquedas que un solo usuario puede iniciar al mismo tiempo. |10   | 
|Número máximo de caracteres para una consulta de búsqueda (incluidos los operadores y las condiciones). |10 000 &nbsp; <sup>2</sup>|
|Número máximo de caracteres para una consulta de búsqueda para SharePoint y OneDrive para la Empresa (incluidos los operadores y las condiciones). |10,000<br>4.000 con caracteres comodín &nbsp; <sup>2</sup>|
|Número mínimo de caracteres alfa para caracteres comodín de prefijo; por ejemplo, **un \* *_ o _* set \***.|3 |  
|Variantes máximas devueltas cuando se usa el carácter comodín de prefijo para buscar una frase exacta o cuando se usa un prefijo comodín y el **operador booleano NEAR.** |10 000 &nbsp; <sup>3</sup>|
|Número máximo de elementos por buzón de usuario que se muestran en la página de vista previa para las búsquedas. Se muestran los elementos más recientes. |100|
|Número máximo de elementos de todos los buzones que se muestran en la página de vista previa para las búsquedas.|1,000|
|Número máximo de buzones que se pueden obtener una vista previa de los resultados de la búsqueda.  Si hay más de 1000 buzones que contienen elementos que coinciden con la consulta de búsqueda, solo los 1.000 buzones con más resultados están disponibles para la vista previa.|1,000|
|Número máximo de elementos de los sitios SharePoint y OneDrive para la Empresa que se muestran en la página de vista previa para las búsquedas. Se muestran los elementos más recientes. |200|
|Número máximo de SharePoint y OneDrive para la Empresa que se pueden obtener una vista previa de los resultados de búsqueda. Si hay más de 200 sitios que contienen elementos que coinciden con la consulta de búsqueda, solo los 200 sitios principales con más resultados están disponibles para la vista previa.|200|
|Número máximo de elementos por buzón de carpetas públicas que se muestran en la página de vista previa para las búsquedas. |100|
|Número máximo de elementos encontrados en todos los elementos de buzón de carpetas públicas que se muestran en la página de vista previa para las búsquedas. |200|
|Número máximo de buzones de carpetas públicas que se pueden obtener una vista previa de los resultados de búsqueda. Si hay más de 500 buzones de carpetas públicas que contienen elementos que coinciden con la consulta de búsqueda, solo los 500 buzones principales con más resultados están disponibles para la vista previa.|500|
|||

## <a name="search-times"></a>Tiempos de búsqueda

Microsoft recopila información de rendimiento para las búsquedas ejecutadas por todas las organizaciones. Aunque la complejidad de una consulta de búsqueda puede afectar al tiempo que lleva ejecutarla, en realidad, el factor más determinante es el número de buzones incluidos en la búsqueda. Aunque Microsoft no proporciona un contrato de nivel de servicio para los tiempos de búsqueda, en la tabla siguiente se enumeran los tiempos promedios de búsqueda para las búsquedas de colección en función del número de buzones incluidos en la búsqueda.
  
  | Número de buzones | Promedio de tiempo de búsqueda |
  |:-----|:-----|
  |100  <br/> |30 segundos  <br/> |
  |1,000  <br/> |45 segundos  <br/> |
  |10 000  <br/> |4 minutos  <br/> |
  |25 000  <br/> |10 minutos  <br/> |
  |50 000  <br/> |20 minutos  <br/> |
  |100 000  <br/> |25 minutos  <br/> |
  |||

## <a name="viewer-limits"></a>Límites del visor

| Descripción del límite | Límite |
|:-----|:-----|
|Tamaño máximo de Excel archivo que se puede ver en el visor nativo.  <br/> |4 MB  <br/> |
|||

## <a name="export-limits---final-export-out-of-review-set"></a>Límites de exportación: exportación final fuera del conjunto de revisión

Los límites descritos en esta sección están relacionados con la exportación de documentos fuera de un conjunto de revisión.

| Descripción del límite | Límite |
|:-----|:-----|
|Tamaño máximo de una sola exportación.|5 millones de documentos o 500 GB, lo que sea menor|
|Máximo de exportaciones simultáneas por conjunto de revisión. | 1 |
|||

## <a name="review-set-download-limits"></a>Revisar establecer límites de descarga

| Descripción del límite | Límite |
|:-----|:-----|
|Tamaño total del archivo o número máximo de documentos descargados de un conjunto de revisión.  <br/> |3 MB o 50 documentos <sup>5</sup>|
|||

<br/>
<br/>

> [!NOTE]
> <sup>1</sup> Cualquier elemento que supere un único límite de archivo se mostrará como un error de procesamiento.
>
> <sup>2</sup> Al buscar SharePoint y OneDrive para la Empresa, los caracteres de las direcciones URL de los sitios que se buscan cuentan con este límite. El número total de caracteres consta de:<br>
> - Todos los caracteres de los campos Usuarios y Filtros.
> - Todos los filtros de permisos de búsqueda que se aplican al usuario.
> - Los caracteres de cualquier propiedad de ubicación de la búsqueda; Esto incluye ExchangeLocation,PublicFolderLocation,SharPointLocation,ExchangeLocationExclusion,PublicFolderLocationExclusion,SharePointLocationExclusion, OneDriveLocationExclusion.
>   Por ejemplo, incluir todos los sitios SharePoint y las cuentas de OneDrive en la búsqueda contarán como seis caracteres, ya que la palabra "ALL" aparecerá para el campo SharePointLocation y OneDriveLocation.
>
> <sup>3</sup> Para consultas que no son de frase (un valor de palabra clave que no usa comillas dobles) usamos un índice de prefijo especial. Esto nos indica que una palabra se produce en un documento, pero no donde se produce en el documento. Para realizar una consulta de frase (un valor de palabra clave con comillas dobles), debemos comparar la posición dentro del documento para las palabras de la frase. Esto significa que no podemos usar el índice de prefijo para las consultas de frases. En este caso, expandemos internamente la consulta con todas las palabras posibles a las que se expande el prefijo; por ejemplo, **time \* *_ puede expandirse a _*"time OR timer OR times OR timex OR timeboxed OR ..."**. El límite de 10 000 es el número máximo de variantes a las que se puede expandir la palabra, no el número de documentos que coinciden con la consulta. Para los términos que no son frases no hay ningún límite superior.
>
> <sup>4</sup> Este límite se comparte con la exportación de contenido en otras herramientas de exhibición de documentos electrónicos. Esto significa que las exportaciones simultáneas en búsqueda de contenido y exhibición de documentos electrónicos principales (y agregar contenido para revisar conjuntos en Advanced eDiscovery) se aplican a este límite.
>
> <sup>5</sup> Este límite se aplica a la descarga de documentos seleccionados de un conjunto de opiniones. No se aplica a la exportación de documentos de un conjunto de revisión. Para obtener más información acerca de la descarga y exportación de documentos, vea [Export case data in Advanced eDiscovery](exporting-data-ediscover20.md).
>
> <sup>6</sup> Límites de indización por organización y día. Como solución alternativa, puede seleccionar varios custodios en la  pestaña **Orígenes** de datos en un caso y, a continuación, hacer clic en Actualizar índice para evitar crear un trabajo de índice independiente para cada custodio. 
