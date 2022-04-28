---
title: Límites de eDiscovery (Premium)
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Obtenga información sobre los límites de casos, los límites de indexación y los límites de búsqueda en vigor para la solución eDiscovery (Premium) en Microsoft 365.
ms.openlocfilehash: 3d0204eb452b669937d30fe5519e5af073b64d6d
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "65099221"
---
# <a name="limits-in-ediscovery-premium"></a>Límites en eDiscovery (Premium)

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

En este artículo se describen los límites de la solución eDiscovery (Premium) de Microsoft Purview en Microsoft 365.

## <a name="case-and-review-set-limits"></a>Límites establecidos de casos y revisiones

En la tabla siguiente se enumeran los límites de los casos y los conjuntos de revisión en eDiscovery (Premium).

|Descripción del límite|Límite|
|---|---|
|Número total de documentos que se pueden agregar a un caso (para todos los conjuntos de revisión en un caso).|3 millones|
|Tamaño total de archivo por conjunto de carga. Esto incluye la carga de Office 365 en un conjunto de revisión.|300 GB|
|Cantidad total de datos cargados en todos los conjuntos de revisión de la organización al día.<br/>|2 TB|
|Número máximo de conjuntos de carga por caso.|200|
|Número máximo de conjuntos de revisión por caso.|20|
|Número máximo de grupos de etiquetas por caso.|1,000|
|Número máximo de etiquetas únicas por caso.|10001<sup></sup>|
|Número máximo de trabajos simultáneos en su organización para agregar contenido a un conjunto de revisión. Estos trabajos se denominan **Adición de datos a un conjunto de revisión** y se muestran en la pestaña **Trabajos** en un caso.|<sup>102</sup>|
|Número máximo de trabajos simultáneos para agregar contenido a un conjunto de revisión por usuario. Estos trabajos se denominan **Adición de datos a un conjunto de revisión** y se muestran en la pestaña **Trabajos** en un caso.|3|

## <a name="hold-limits"></a>Límites de retención

En la tabla siguiente se enumeran los límites de las retenciones asociadas a un caso de exhibición de documentos electrónicos (Premium).

| Descripción del límite | Límite |
|:-----|:-----|
|Número máximo de directivas de suspensión para una organización. Este límite incluye el total combinado de directivas de suspensión en casos de exhibición de documentos electrónicos de Microsoft Purview (estándar) y eDiscovery de Microsoft Purview (Premium). <br/> |10 000<sup>3</sup>  <br/> |
|Número máximo de buzones en una única retención de mayúsculas y minúsculas. Este límite incluye el total combinado de buzones de usuario y los buzones asociados a Grupos de Microsoft 365, Microsoft Teams y grupos de Yammer. <br/> |1,000  <br/> |
|Número máximo de sitios en una única retención de mayúsculas y minúsculas. Este límite incluye el total combinado de sitios de OneDrive para la Empresa, sitios SharePoint y los sitios asociados con Grupos de Microsoft 365, Microsoft Teams y grupos de Yammer.  <br/> |100  <br/> |

## <a name="indexing-limits"></a>Límites de indexación

En la tabla siguiente se enumeran los límites de indexación en eDiscovery (Premium).

|Descripción del límite|Límite|
|---|---|
|Número máximo de caracteres extraídos de un único archivo.|10 <sup>millones4</sup>|
|Tamaño máximo de un solo archivo.|150 <sup>MB4</sup>|
|Profundidad máxima de los elementos incrustados en un documento.|<sup>254</sup>|
|Tamaño máximo de los archivos procesados por reconocimiento óptico de caracteres (OCR).|24 <sup>MB4</sup> <br/>  

## <a name="search-limits"></a>Límites de búsqueda

Los límites descritos en esta sección están relacionados con el uso de la herramienta de búsqueda en la pestaña **Búsquedas** para recopilar datos de un caso. Para obtener más información, vea [Recopilar datos para un caso en eDiscovery (Premium)](collecting-data-for-ediscovery.md).

|Descripción del límite|Límite|
|---|---|
|Número máximo de buzones o sitios que se pueden buscar en una sola búsqueda.|Sin límite|
|Número máximo de búsquedas que se pueden ejecutar al mismo tiempo.|Sin límite|
|Número máximo de búsquedas que un solo usuario puede iniciar al mismo tiempo.|10|
|Número máximo de caracteres para una consulta de búsqueda (incluidos operadores y condiciones).|10 <sup>0005</sup>|
|Número máximo de caracteres para una consulta de búsqueda de sitios de SharePoint y OneDrive para la Empresa (incluidos operadores y condiciones).|10,000<br>4000 con caracteres <sup>comodín5</sup>|
|Número mínimo de caracteres alfa para caracteres comodín de prefijo; por ejemplo, **one\**_ o _* set\***.|3|
|Número máximo de variantes devueltas cuando se usa el carácter comodín de prefijo para buscar una frase exacta o cuando se usa un carácter comodín de prefijo y el operador booleano **NEAR** .|10 <sup>0006</sup>|
|Número máximo de elementos por buzón de usuario que se muestran en la página de vista previa para las búsquedas. Se muestran los elementos más recientes.|100|
|Número máximo de elementos de todos los buzones que se muestran en la página de vista previa para las búsquedas.|1,000|
|Número máximo de buzones que se pueden obtener en vista previa para los resultados de búsqueda.  Si hay más de 1000 buzones que contienen elementos que coinciden con la consulta de búsqueda, solo los 1000 buzones principales con más resultados están disponibles para la versión preliminar.|1,000|
|Número máximo de elementos de SharePoint y OneDrive para la Empresa sitios que se muestran en la página de vista previa para las búsquedas. Se muestran los elementos más recientes.|200|
|Número máximo de sitios de SharePoint y OneDrive para la Empresa que se pueden obtener en vista previa para los resultados de la búsqueda. Si hay más de 200 sitios que contienen elementos que coinciden con la consulta de búsqueda, solo los 200 sitios principales con más resultados están disponibles para la versión preliminar.|200|
|Número máximo de elementos por buzón de carpeta pública que se muestra en la página de vista previa para las búsquedas.|100|
|Número máximo de elementos encontrados en todos los elementos de buzón de carpeta pública que se muestran en la página de vista previa para las búsquedas.|200|
|Número máximo de buzones de carpetas públicas que se pueden obtener en vista previa para los resultados de búsqueda. Si hay más de 500 buzones de carpetas públicas que contienen elementos que coinciden con la consulta de búsqueda, solo los 500 buzones con más resultados están disponibles para la versión preliminar.|500|
|Tamaño máximo de un elemento que se puede ver en la página de ejemplo de una colección de borradores.|10 000 000 bytes (aproximadamente 9,5 MB)|

## <a name="search-times"></a>Horas de búsqueda

Microsoft recopila información de rendimiento para las búsquedas ejecutadas por todas las organizaciones. Aunque la complejidad de una consulta de búsqueda puede afectar al tiempo que lleva ejecutarla, en realidad, el factor más determinante es el número de buzones incluidos en la búsqueda. Aunque Microsoft no proporciona un contrato de nivel de servicio para los tiempos de búsqueda, en la tabla siguiente se enumeran los tiempos promedio de búsqueda de recopilación en función del número de buzones incluidos en la búsqueda.
  
|Número de buzones|Promedio de tiempo de búsqueda|
|---|---|
|100|30 segundos|
|1,000|45 segundos|
|10 000|4 minutos|
|25 000|10 minutos|
|50 000|20 minutos|
|100 000|25 minutos|

## <a name="viewer-limits"></a>Límites de visor

|Descripción del límite|Límite|
|---|---|
|Tamaño máximo de Excel archivo que se puede ver en el visor nativo.|4 MB|

## <a name="export-limits---final-export-out-of-review-set"></a>Límites de exportación: exportación final fuera del conjunto de revisión

Los límites descritos en esta sección están relacionados con la exportación de documentos fuera de un conjunto de revisión.

|Descripción del límite|Límite|
|---|---|
|Tamaño máximo de una sola exportación.|5 millones de documentos o 500 GB, lo que sea más pequeño|
|Número máximo de exportaciones simultáneas por conjunto de revisión.|1|

## <a name="review-set-download-limits"></a>Revisión de los límites de descarga establecidos

|Descripción del límite|Límite|
|---|---|
|Tamaño total de archivo o número máximo de documentos descargados de un conjunto de revisión.|3 MB o 50 <sup>documentos7</sup>|

## <a name="notes"></a>Notas

> [!NOTE]
> <sup>1</sup> Este es el número máximo de etiquetas que puede crear en un caso. Este límite no está relacionado con el número de documentos que se pueden etiquetar.
>
> <sup>2</sup> Este límite se comparte con la exportación de contenido en otras herramientas de exhibición de documentos electrónicos. Esto significa que las exportaciones simultáneas en búsqueda de contenido y exhibición de documentos electrónicos (estándar) (y agregar contenido para revisar conjuntos en eDiscovery (Premium)) se aplican a este límite.
>
> <sup>3</sup> Cuando coloca más de 1000 buzones de correo o 100 sitios en espera en una sola directiva de suspensión, el sistema escalará automáticamente la suspensión según sea necesario. Esto significa que el sistema agregará automáticamente ubicaciones de datos a varias directivas de suspensión, en lugar de agregarlas a una sola directiva de suspensión. Sin embargo, todavía se aplica el límite de 10 000 directivas de suspensión de casos por organización.
>
> <sup>4</sup> Cualquier elemento que supere un único límite de archivo se mostrará como un error de procesamiento.
>
> <sup>5</sup> Al buscar SharePoint y OneDrive para la Empresa ubicaciones, los caracteres de las direcciones URL de los sitios que se buscan cuentan con este límite. El número total de caracteres consta de:
>
> - Todos los caracteres de los campos Usuarios y Filtros.
> - Todos los filtros de permisos de búsqueda que se aplican al usuario.
> - Los caracteres de las propiedades de ubicación de la búsqueda; esto incluye ExchangeLocation,PublicFolderLocation,SharPointLocation,ExchangeLocationExclusion,PublicFolderLocationExclusion,SharePointLocationExclusion, OneDriveLocationExclusion.
>   Por ejemplo, incluir todos los sitios de SharePoint y cuentas de OneDrive en la búsqueda contará como seis caracteres, ya que aparecerá la palabra "ALL" para los campos SharePointLocation y OneDriveLocation.
>
> <sup>6</sup> En el caso de las consultas sin frases (un valor de palabra clave que no usa comillas dobles), usamos un índice de prefijo especial. Esto nos indica que una palabra se produce en un documento, pero no donde se produce en el documento. Para realizar una consulta de frase (un valor de palabra clave con comillas dobles), es preciso comparar la posición dentro del documento para las palabras de la frase. Esto significa que no se puede usar el índice de prefijo para las consultas de frases. En este caso, ampliamos internamente la consulta con todas las palabras posibles a las que se expande el prefijo; por ejemplo,  **time\**_ puede expandirse a _*"time OR timer OR times OR timex OR timex OR timeboxed OR ..."**. El límite de 10 000 es el número máximo de variantes a las que la palabra puede expandirse, no el número de documentos que coinciden con la consulta. Para los términos que no son frases no hay ningún límite superior.
>
> <sup>7</sup> Este límite se aplica a la descarga de documentos seleccionados de un conjunto de revisión. No se aplica a la exportación de documentos desde un conjunto de revisión. Para obtener más información sobre cómo descargar y exportar documentos, vea [Exportar datos de casos en eDiscovery (Premium)](exporting-data-ediscover20.md).
