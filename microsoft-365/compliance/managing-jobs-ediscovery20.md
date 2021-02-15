---
title: Administrar trabajos en eDiscovery avanzado
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
description: Los trabajos avanzados de exhibición de documentos electrónicos le ayudan a realizar un seguimiento del estado de los procesos de larga ejecución relacionados con la realización de diversas tareas de eDiscovery avanzado.
ms.openlocfilehash: f5c366b8809b1b5c08b15972118c40d7d29e33c4
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/05/2021
ms.locfileid: "49750771"
---
# <a name="manage-jobs-in-advanced-ediscovery"></a>Administrar trabajos en eDiscovery avanzado

Esta es una lista de los trabajos (que normalmente son procesos  de larga ejecución) que se rastrean en la pestaña Trabajos de un caso en eDiscovery avanzado. Estos trabajos se desencadenan mediante acciones de usuario al usar y administrar casos.

| Tipo de trabajo           | Descripción     |
| :----------------- | :----------     |
|Agregar datos a un conjunto de revisión | Un usuario agrega los resultados de una búsqueda a un conjunto de revisión. Este trabajo consta de dos subproyecciones: </br>• **GatheringItems:** se genera una lista de elementos que coinciden con la consulta de búsqueda (y el origen de datos de Microsoft 365 en el que se encuentran). </br>• **Ingesta &** indización: los elementos que coinciden con la consulta de búsqueda se copian en una ubicación de Azure Storage (en un proceso denominado ingesta) y, a continuación, se reindexa esos elementos en la ubicación de Azure Storage.  Este nuevo índice se usa al consultar y analizar elementos del conjunto de datos. </br></br>Para obtener más información, vea [Agregar resultados de búsqueda a un conjunto de revisión.](add-data-to-review-set.md) |
|Agregar datos a otro conjunto de revisión | Un usuario agrega documentos de un conjunto de revisión a un conjunto de revisión diferente en el mismo caso. Para obtener más información, vea [Agregar datos a un conjunto de revisión desde otro conjunto de revisión.](add-data-to-review-set-from-another-review-set.md)|
|Agregar datos que no son de Microsoft 365 a un conjunto de revisión | Un usuario carga datos que no son de Microsoft 365 en un conjunto de revisión. Los datos también se indizan durante este proceso. Por ejemplo, los archivos de un servidor de archivos local o un equipo cliente se cargan en un conjunto de revisión. Para obtener más información, vea Cargar datos que no son [de Microsoft 365 en un conjunto de revisión.](load-non-office-365-data-into-a-review-set.md)| 
|Agregar datos corregidos a un conjunto de revisión | Los datos con errores de procesamiento se corrigen y se cargan de nuevo en un conjunto de revisión. Para obtener más información, vea:</br>• [Corrección de errores al procesar datos](error-remediation-when-processing-data-in-advanced-ediscovery.md)</br>• [Corrección de errores de elemento único](single-item-error-remediation.md)| 
|Comparación de conjuntos de carga | Un usuario examina las diferencias entre los distintos conjuntos de carga de un conjunto de revisión. Un conjunto de carga es una instancia de agregar datos a un conjunto de revisión. Por ejemplo, si agrega los resultados de dos búsquedas diferentes al mismo conjunto de revisión, cada una representaría un conjunto de carga. |
|Reconstrucción de conversación|Cuando un usuario agrega los resultados de una búsqueda a un conjunto de revisión de conversación, las conversaciones de mensajes instantáneos (también denominadas conversaciones en *conversación)* en servicios como Microsoft Teams se reconstruyen en un archivo PDF. Este trabajo también se desencadena cuando un usuario hace clic en Acción **> archivos PDF** de conversación en un conjunto de revisión. Para obtener más información, vea [Revisar conversaciones en eDiscovery avanzado.](conversation-review-sets.md)
|Convertir documentos redactados en PDF|Después de que un usuario anota un documento en un conjunto de revisión y redacta una parte de él, puede elegir convertir el documento redactado en un archivo PDF. Esto garantiza que la parte redactada no será visible si el documento se exporta para su presentación. Para obtener más información, vea [Ver documentos en un conjunto de revisión.](annotating-and-redacting-documents.md) |
|Estimación de los resultados de la búsqueda | Una vez que un usuario crea y ejecuta una nueva búsqueda (o vuelve a ejecutar una búsqueda existente), la herramienta de búsqueda busca en el índice elementos que coincidan con la consulta de búsqueda y prepara una estimación que incluye el número y el tamaño total de todos los elementos por la búsqueda, y el número de orígenes de datos buscados.  Para obtener más información, vea [Recopilar datos para un caso.](collecting-data-for-ediscovery.md) | 
|Preparación de los datos para la exportación | Un usuario exporta documentos de un conjunto de revisión. Una vez completado el proceso de exportación, pueden descargar los datos exportados en un equipo local. Para obtener más información, vea [Exportar datos de casos.](exporting-data-ediscover20.md) | 
|Preparación para la resolución de errores |Cuando un usuario selecciona un archivo y crea una nueva  corrección de errores en la vista Error de la pestaña Procesamiento de un caso, el primer paso del proceso es cargar el archivo que tiene el error de procesamiento en una ubicación de Azure Storage en la nube de Microsoft. Este trabajo realiza un seguimiento del progreso del proceso de carga. Para obtener más información acerca del flujo de trabajo de corrección de errores, vea [Error remediation when processing data](error-remediation-when-processing-data-in-advanced-ediscovery.md). | 
|Preparación de la vista previa de búsqueda | Después de que un usuario cree y ejecute una nueva búsqueda (o vuelva a ejecutar una búsqueda existente), la herramienta de búsqueda prepara un subconjunto de ejemplo de elementos (que coinciden con la consulta de búsqueda) que se puede obtener una vista previa. La vista previa de los resultados de la búsqueda ayuda a determinar la eficacia de la búsqueda.  Para obtener más información, vea [Recopilar datos para un caso.](collecting-data-for-ediscovery.md#view-search-results-and-statistics) | 
|Volver a indizar los datos de administrador | Cuando se agrega un administrador a un caso, todos los elementos parcialmente indizados en los orígenes de datos seleccionados del administrador se reindexa mediante un proceso denominado *indización avanzada*. Este trabajo también se  desencadena al  hacer clic en Actualizar índice en la pestaña Procesamiento de un caso y al actualizar el índice de un administrador específico en la página desplegable de propiedades de administrador. Para obtener más información, vea [Indización avanzada de datos de administrador.](indexing-custodian-data.md)
|Ejecución de análisis | Un usuario analiza los datos de un conjunto de revisión mediante la ejecución de herramientas de análisis de eDiscovery avanzado, como la detección de duplicados cercanos, el análisis de subprocesos de correo electrónico y el análisis de temas. Para obtener más información, vea [Analizar datos en un conjunto de revisión.](analyzing-data-in-review-set.md) | 
|Etiquetado de documentos | Este trabajo se desencadena cuando  un usuario hace clic en Iniciar trabajo de etiquetado en el **panel** etiquetado al revisar documentos de un conjunto de revisión. Un usuario puede iniciar este trabajo después de etiquetar documentos en un conjunto de revisión y, a continuación, seleccionarlos en masa en el panel de documentos de vista. Para obtener más información, vea [Etiquetar documentos en un conjunto de revisión.](tagging-documents.md) | 
|||

## <a name="job-status"></a>Estado del trabajo

En la tabla siguiente se describen los diferentes estados de los trabajos.

| Estado           | Descripción     |
| :----------------- | :----------     |
| Submitted | Se creó un nuevo trabajo.  La fecha y la hora en que se envió el trabajo se muestra en la **columna Creado** en la **ficha** Trabajos. |
| Error de envío | Error en el envío del trabajo.  Debe intentar volver a ejecutar la acción que desencadenó el trabajo. |
| En curso | El trabajo está en curso, puede supervisar el progreso del trabajo en la **ficha** Trabajos. |
| Correcto | El trabajo se completó correctamente. La fecha y la hora en que se completó el trabajo se muestra en la **columna** Completado de la **ficha** Trabajos. |
| Parcialmente correcto | El trabajo se ha realizado parcialmente correctamente. Este estado se suele devolver cuando el trabajo no encontró datos parcialmente indizados (también denominados datos no indexados) en algunos de los orígenes de datos de administrador.  |
| Fallido | Error en el trabajo.  Debe intentar volver a ejecutar la acción que desencadenó el trabajo. Si el trabajo falla una segunda vez, se recomienda ponerse en contacto con el Soporte técnico de Microsoft y proporcionar la información de soporte técnico del trabajo. |
|||
