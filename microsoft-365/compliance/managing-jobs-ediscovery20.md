---
title: Administrar trabajos en eDiscovery (Premium)
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Los trabajos de eDiscovery (Premium) le ayudan a realizar un seguimiento del estado de los procesos de ejecución prolongada relacionados con la realización de varias tareas de eDiscovery (Premium).
ms.openlocfilehash: a87bb2a3bd90ff915392ae38c7355f3ad24f8061
ms.sourcegitcommit: a7c1acfb3d2cbba913e32493b16ebd8cbfeee456
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/13/2022
ms.locfileid: "66043196"
---
# <a name="manage-jobs-in-ediscovery-premium"></a>Administrar trabajos en eDiscovery (Premium)

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

Esta es una lista de los trabajos (que suelen ser procesos de ejecución prolongada) de los que se realiza un seguimiento en la pestaña **Trabajos** de un caso en eDiscovery de Microsoft Purview (Premium). Estos trabajos se desencadenan mediante acciones del usuario al usar y administrar casos.

|Tipo de trabajo|Descripción|
|---|---|
|Adición de datos a un conjunto de revisión|Un usuario agrega una colección a un conjunto de revisión. Este trabajo consta de dos sub jobs: <ul><li>**Exportar** : se genera una lista de elementos de la colección.</li><li>**Indexación de & de ingesta**: los elementos de la colección que coinciden con la consulta de búsqueda se copian en una ubicación de Azure Storage (en un proceso denominado *ingesta*) y, a continuación, se vuelven a indexar los elementos de la ubicación de Azure Storage. Este nuevo índice se usa al consultar y analizar elementos del conjunto de datos.</li><ul> <p> Para obtener más información, vea [Agregar resultados de búsqueda a un conjunto de revisión](add-data-to-review-set.md).|
|Adición de datos a otro conjunto de revisión|Un usuario agrega documentos de un conjunto de revisión a otro conjunto de revisión en el mismo caso. Para obtener más información, vea [Agregar datos a un conjunto de revisión de otro conjunto de revisión](add-data-to-review-set-from-another-review-set.md).|
|Adición de datos que no son Microsoft 365 a un conjunto de revisión|Un usuario carga datos no Microsoft 365 en un conjunto de revisión. Los datos también se indizan durante este proceso. Por ejemplo, los archivos de un servidor de archivos local o de un equipo cliente se cargan en un conjunto de revisión. Para obtener más información, consulte [Carga de datos que no son Microsoft 365 en un conjunto de revisión](load-non-office-365-data-into-a-review-set.md).|
|Adición de datos corregidos a un conjunto de revisión|Los datos con errores de procesamiento se corrigen y se cargan de nuevo en un conjunto de revisión. Para más información, vea: <ul><li>[Corrección de errores al procesar los datos](error-remediation-when-processing-data-in-advanced-ediscovery.md)</li><li>[Corrección de errores de un único elemento](single-item-error-remediation.md)</li></ul>|
|Comparación de conjuntos de carga|Un usuario examina las diferencias entre los distintos conjuntos de carga de un conjunto de revisión. Un conjunto de carga es una instancia de agregar datos a un conjunto de revisión. Por ejemplo, si agrega los resultados de dos búsquedas diferentes al mismo conjunto de revisión, cada una representaría un conjunto de carga.|
|Reconstrucción de conversaciones|Cuando un usuario agrega los resultados de una búsqueda a un conjunto de revisión de conversaciones, las conversaciones de mensajes instantáneos (también *denominadas conversaciones en subprocesos*) en servicios como Microsoft Teams se reconstruyeron en un archivo PDF. Este trabajo también se desencadena cuando un usuario hace clic en **Acción > Crear archivos PDF de conversación** en un conjunto de revisión. Para obtener más información, vea [Revisar conversaciones en eDiscovery (Premium)](conversation-review-sets.md).
|Conversión de documentos redactados en PDF|Después de que un usuario anota un documento en un conjunto de revisión y redacta una parte del mismo, puede optar por convertir el documento redactado en un archivo PDF. Esto garantiza que la parte redactada no será visible si el documento se exporta para la presentación. Para obtener más información, vea [Ver documentos en un conjunto de revisión](view-documents-in-review-set.md).|
|Estimación de los resultados de la búsqueda|Después de que un usuario crea y ejecuta o vuelve a ejecutar una colección de borradores, la herramienta de búsqueda busca en el índice los elementos que coinciden con la consulta de búsqueda y prepara una estimación que incluye el número y el tamaño total de todos los elementos por la búsqueda y el número de orígenes de datos buscados.  Para obtener más información, consulte [Recopilación de datos para un caso](collecting-data-for-ediscovery.md).|
|Preparación de datos para la exportación|Un usuario exporta documentos de un conjunto de revisión. Una vez completado el proceso de exportación, pueden descargar los datos exportados en un equipo local. Para obtener más información, consulte [Exportación de datos de casos](exporting-data-ediscover20.md).|
|Preparación para la resolución de errores|Cuando un usuario selecciona un archivo y crea una nueva corrección de errores en la vista Error de la pestaña **Procesamiento** de un caso, el primer paso del proceso es cargar el archivo que tiene el error de procesamiento en una ubicación de Azure Storage en la nube de Microsoft. Este trabajo realiza un seguimiento del progreso del proceso de carga. Para obtener más información sobre el flujo de trabajo de corrección de errores, consulte [Corrección de errores al procesar datos](error-remediation-when-processing-data-in-advanced-ediscovery.md).|
|Preparación de la vista previa de búsqueda|Después de que un usuario crea y ejecuta una nueva colección de borradores (o vuelve a ejecutar una colección de borradores existente), la herramienta de búsqueda prepara un subconjunto de ejemplo de elementos (que coinciden con la consulta de búsqueda) que se pueden obtener en vista previa. La vista previa de los resultados de la búsqueda le ayuda a determinar la eficacia de la búsqueda.  Para obtener más información, consulte [Recopilación de datos para un caso](collecting-data-for-ediscovery.md#view-search-results-and-statistics).|
|Volver a indexar los datos del custodio|Al agregar un custodio a un caso, todos los elementos indizados parcialmente en los orígenes de datos seleccionados del custodio se vuelven a indexar mediante un proceso denominado *Indexación avanzada*. Este trabajo también se desencadena al hacer clic en **Actualizar índice** en la pestaña **Procesamiento** de un caso y al actualizar el índice de un custodio específico en la página flotante de propiedades del custodio. Para obtener más información, vea [Indexación avanzada de datos de custodios](indexing-custodian-data.md).
|Ejecución de análisis|Un usuario analiza los datos de un conjunto de revisión mediante la ejecución de herramientas de análisis de eDiscovery (Premium), como la detección casi duplicada, el análisis de subprocesos de correo electrónico y el análisis de temas. Para obtener más información, vea [Analizar datos en un conjunto de revisión](analyzing-data-in-review-set.md).|
|Etiquetado de documentos|Este trabajo se desencadena cuando un usuario hace clic en **Iniciar trabajo de etiquetado** en el **panel Etiquetado** al revisar documentos de un conjunto de revisión. Un usuario puede iniciar este trabajo después de etiquetar documentos en un conjunto de revisión y seleccionarlos de forma masiva en el panel del documento de vista. Para obtener más información, vea [Etiquetar documentos en un conjunto de revisión](tagging-documents.md).|

## <a name="job-status"></a>Estado del trabajo

En la tabla siguiente se describen los distintos estados de estado de los trabajos.

|Estado|Descripción|
|---|---|
|Submitted|Se ha creado un nuevo trabajo.  La fecha y hora en que se envió el trabajo se muestra en la columna **Creado** de la pestaña **Trabajos** .|
|Error de envío|Error en el envío del trabajo.  Debe intentar volver a ejecutar la acción que desencadenó el trabajo.|
|En curso|El trabajo está en curso, puede supervisar el progreso del trabajo en la pestaña **Trabajos** .|
|Correcto|El trabajo se completó correctamente. La fecha y hora en que se completó el trabajo se muestra en la columna **Completado** de la pestaña **Trabajos** .|
|Parcialmente correcto|El trabajo se realizó correctamente. Este estado se devuelve normalmente cuando el trabajo no encontró datos parcialmente indexados (también denominados *datos sin indexar*) en algunos de los orígenes de datos del custodio.|
|Fallido|Error en el trabajo.  Debe intentar volver a ejecutar la acción que desencadenó el trabajo. Si se produce un error en el trabajo por segunda vez, se recomienda ponerse en contacto con Soporte técnico de Microsoft y proporcionar la información de soporte técnico del trabajo.|
