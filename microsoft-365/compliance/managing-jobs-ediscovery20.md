---
title: Administrar trabajos en Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Advanced eDiscovery trabajos le ayudarán a realizar un seguimiento del estado de los procesos de larga ejecución relacionados con la realización de Advanced eDiscovery tareas.
ms.openlocfilehash: 27ac98d1f98e85800c8ca3dfc91cc5e0803ae2e8
ms.sourcegitcommit: d4604e333507c6f57d5bf327531a241b649052de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "51471083"
---
# <a name="manage-jobs-in-advanced-ediscovery"></a>Administrar trabajos en Advanced eDiscovery

Esta es una lista de los trabajos (que normalmente son procesos  de larga ejecución) que se realiza un seguimiento en la pestaña Trabajos de un caso en Advanced eDiscovery. Estos trabajos se desencadenan mediante acciones de usuario al usar y administrar casos.

| Tipo de trabajo           | Descripción     |
| :----------------- | :----------     |
|Agregar datos a un conjunto de revisión | Un usuario agrega una colección a un conjunto de opiniones. Este trabajo consta de dos sub trabajos: </br>• **Exportar:** se genera una lista de elementos de la colección. </br>• **Indización** de & de ingesta: los elementos de la colección que coinciden con la consulta de búsqueda se copian en una ubicación de Azure Storage (en un proceso denominado *ingestión)* y, a continuación, los elementos de la ubicación de Azure Storage se indizan de nuevo. Este nuevo índice se usa al consultar y analizar elementos del conjunto de datos. </br></br>Para obtener más información, vea [Agregar resultados de búsqueda a un conjunto de revisión.](add-data-to-review-set.md) |
|Agregar datos a otro conjunto de revisión | Un usuario agrega documentos de un conjunto de revisión a un conjunto de revisión diferente en el mismo caso. Para obtener más información, vea [Agregar datos a un conjunto de revisión de otro conjunto de revisión](add-data-to-review-set-from-another-review-set.md).|
|Agregar datos no Microsoft 365 a un conjunto de revisión | Un usuario carga datos que no Microsoft 365 a un conjunto de opiniones. Los datos también se indizan durante este proceso. Por ejemplo, los archivos de un servidor de archivos local o un equipo cliente se cargan en un conjunto de revisión. Para obtener más información, vea [Load non-Microsoft 365 data into a review set](load-non-office-365-data-into-a-review-set.md).| 
|Agregar datos corregidos a un conjunto de revisión | Los datos con errores de procesamiento se corrigen y se cargan de nuevo en un conjunto de revisión. Para obtener más información, vea:</br>• [Corrección de errores al procesar datos](error-remediation-when-processing-data-in-advanced-ediscovery.md)</br>• [Corrección de errores de elemento único](single-item-error-remediation.md)| 
|Comparación de conjuntos de carga | Un usuario examina las diferencias entre distintos conjuntos de carga de un conjunto de revisión. Un conjunto de carga es una instancia de agregar datos a un conjunto de revisión. Por ejemplo, si agrega los resultados de dos búsquedas diferentes al mismo conjunto de revisión, cada una representaría un conjunto de carga. |
|Reconstrucción de conversación|Cuando un usuario agrega los resultados de una búsqueda a un conjunto de revisión de conversación, las conversaciones de mensajes instantáneos (también denominadas conversaciones enhebradas) en servicios como Microsoft Teams se reconstruyen en un archivo PDF. Este trabajo también se desencadena cuando un usuario hace clic en **Acción > Crear archivos PDF** de conversación en un conjunto de opiniones. Para obtener más información, vea [Revisar conversaciones en Advanced eDiscovery](conversation-review-sets.md).
|Convertir documentos redactados en PDF|Después de que un usuario anota un documento en un conjunto de revisión y redacta una parte de él, puede elegir convertir el documento redactado en un archivo PDF. Esto garantiza que la parte redactada no será visible si el documento se exporta para la presentación. Para obtener más información, vea [Ver documentos en un conjunto de revisión.](annotating-and-redacting-documents.md) |
|Estimación de resultados de búsqueda | Después de que un usuario cree y ejecute o vuelva a ejecutar una colección de borradores, la herramienta de búsqueda busca en el índice elementos que coincidan con la consulta de búsqueda y prepara una estimación que incluye el número y el tamaño total de todos los elementos de la búsqueda y el número de orígenes de datos buscados.  Para obtener más información, vea [Recopilar datos para un caso](collecting-data-for-ediscovery.md). | 
|Preparación de datos para la exportación | Un usuario exporta documentos de un conjunto de revisión. Una vez completado el proceso de exportación, pueden descargar los datos exportados en un equipo local. Para obtener más información, vea [Export case data](exporting-data-ediscover20.md). | 
|Preparación para la resolución de errores |Cuando un usuario selecciona un archivo y crea una nueva  corrección de errores en la vista Error de la ficha Procesamiento de un caso, el primer paso del proceso es cargar el archivo que tiene el error de procesamiento en una ubicación de Azure Storage en la nube de Microsoft. Este trabajo realiza un seguimiento del progreso del proceso de carga. Para obtener más información acerca del flujo de trabajo de corrección de errores, vea [Error remediation when processing data](error-remediation-when-processing-data-in-advanced-ediscovery.md). | 
|Preparación de la vista previa de búsqueda | Después de que un usuario cree y ejecute una nueva colección de borradores (o vuelva a ejecutar una colección de borradores existente), la herramienta de búsqueda prepara un subconjunto de ejemplo de elementos (que coinciden con la consulta de búsqueda) que se pueden obtener una vista previa. La vista previa de los resultados de la búsqueda le ayuda a determinar la eficacia de la búsqueda.  Para obtener más información, vea [Recopilar datos para un caso](collecting-data-for-ediscovery.md#view-search-results-and-statistics). | 
|Volver a indizar datos de custodia | Cuando se agrega un custodio a un caso, todos los elementos parcialmente indizados en los orígenes de datos seleccionados del custodio se reindexa mediante un proceso denominado *Indexación avanzada*. Este trabajo también se  desencadena al  hacer clic en Actualizar índice en la pestaña Procesamiento de un caso y al actualizar el índice de un custodio específico en la página desplegable de propiedades de custodia. Para obtener más información, [vea Advanced indexing of custodian data](indexing-custodian-data.md).
|Ejecución de análisis | Un usuario analiza los datos de un conjunto de opiniones ejecutando Advanced eDiscovery de análisis, como la detección de duplicados cercanos, el análisis de subprocesos de correo electrónico y el análisis de temas. Para obtener más información, vea [Analizar datos en un conjunto de revisión.](analyzing-data-in-review-set.md) | 
|Etiquetar documentos | Este trabajo se desencadena cuando  un usuario hace clic en Iniciar el trabajo de etiquetado en el **panel** Etiquetado al revisar documentos de un conjunto de opiniones. Un usuario puede iniciar este trabajo después de etiquetar documentos en un conjunto de revisión y, a continuación, seleccionarlos de forma masiva en el panel de documentos de vista. Para obtener más información, vea [Tag documents in a review set](tagging-documents.md). | 
|||

## <a name="job-status"></a>Estado del trabajo

En la tabla siguiente se describen los distintos estados de estado de los trabajos.

| Estado           | Descripción     |
| :----------------- | :----------     |
| Submitted | Se creó un nuevo trabajo.  La fecha y hora en que se envió el trabajo se muestra en la **columna Creado** de la **ficha** Trabajos. |
| Error en el envío | Error en el envío del trabajo.  Debe intentar volver a ejecutar la acción que desencadenó el trabajo. |
| En curso | El trabajo está en curso, puede supervisar el progreso del trabajo en **la** pestaña Trabajos. |
| Correcto | El trabajo se completó correctamente. La fecha y hora en que se completó el trabajo se muestra en la **columna** Completado de la **ficha** Trabajos. |
| Parcialmente correcto | El trabajo se ha realizado correctamente. Este estado normalmente se devuelve cuando el trabajo no encontró datos parcialmente indizados (también denominados datos no indexados) en algunos de los orígenes de datos de custodia.  |
| Failed | Error en el trabajo.  Debe intentar volver a ejecutar la acción que desencadenó el trabajo. Si el trabajo falla una segunda vez, se recomienda ponerse en contacto con el Soporte técnico de Microsoft y proporcionar la información de soporte técnico del trabajo. |
|||
