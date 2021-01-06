---
title: eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: 143b3ab8-8cb0-4036-a5fc-6536d837bfce
description: Microsoft 365 ofrece varias herramientas de eDiscovery distintas que puede usar para buscar y conservar contenido que se encuentra en diferentes ubicaciones, como buzones de Exchange, sitios de SharePoint y OneDrive para la empresa, grupos de Microsoft 365 y conversaciones de Skype empresarial.
ms.openlocfilehash: a6708bdf012d2cfbb182d624c8c889de5fb51c7f
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/06/2021
ms.locfileid: "49760224"
---
# <a name="ediscovery-in-microsoft-365"></a>eDiscovery en Microsoft 365

La exhibición de documentos electrónicos, o eDiscovery, es el proceso de identificación y entrega de información electrónica que se puede usar como prueba en casos legales. Puede usar las herramientas de exhibición de documentos electrónicos de Microsoft 365 para buscar contenido en buzones de Exchange Online, grupos de Microsoft 365, Microsoft Teams, SharePoint Online y OneDrive para la empresa, conversaciones de Skype empresarial y equipos de Yammer. Puede buscar en buzones y sitios en la misma búsqueda de exhibición de documentos electrónicos mediante la herramienta de búsqueda de contenido. Además, puede usar los casos principales de eDiscovery para identificar, mantener y exportar el contenido que se encuentra en los buzones de correo y los sitios. Si su organización tiene una suscripción a Office 365 E5 o Microsoft 365 E5 (o las suscripciones a los complementos E5 relacionadas), podrá administrar los custodios y analizar el contenido mediante la solución de exhibición de documentos electrónicos avanzada en Microsoft 365.
  
Microsoft 365 proporciona las siguientes herramientas de eDiscovery:
  
- [Búsqueda de contenido](#content-search)

- [eDiscovery principal](#core-ediscovery)

- [eDiscovery avanzado](#advanced-ediscovery)

## <a name="content-search"></a>Búsqueda de contenido

La tabla siguiente contiene vínculos a temas que le ayudarán a usar la herramienta de búsqueda de contenido.
  
|**Tema**|**Descripción**|
|:-----|:-----|
|[Ejecutar una búsqueda de contenido](content-search.md) <br/> |Obtenga información sobre cómo usar la herramienta de búsqueda de contenido para buscar en buzones de correo, carpetas públicas, grupos de 365 Microsoft Teams, Microsoft Teams, sitios de SharePoint Online, ubicaciones de una sola unidad de negocio y conversaciones de Skype empresarial en la organización en una sola búsqueda.  <br/> |
|[Consultas de palabras clave y condiciones de búsqueda para la búsqueda de contenido](keyword-queries-and-search-conditions.md). <br/> |Obtenga información sobre las propiedades de correo electrónico y de archivo y las condiciones de búsqueda que puede usar para buscar contenido en los buzones y los sitios de la organización.  <br/> |
|[Ver las estadísticas de palabras clave para resultados de búsqueda de contenido](view-keyword-statistics-for-content-search.md) <br/> |Obtenga información sobre cómo usar las estadísticas de búsqueda para mostrar y comparar las estadísticas de una o más búsquedas de contenido, y cómo configurar búsquedas nuevas y existentes para devolver las estadísticas de cada palabra clave en la consulta de búsqueda.  <br/> |
|[Exportar resultados de la búsqueda](export-search-results.md) <br/> |Obtenga información sobre cómo exportar los resultados de una búsqueda de contenido.  <br/> |
|[Configurar el filtrado de permisos para Búsqueda de contenido](permissions-filtering-for-content-search.md) <br/> |Obtenga información sobre cómo usar el filtrado de permisos para permitir que un administrador de eDiscovery busque solo un subconjunto de buzones de correo y sitios de la organización.  <br/> |
|[Exportar un informe de búsqueda de contenido](export-a-content-search-report.md) <br/> |Obtenga información sobre cómo descargar el informe de exportación sin tener que exportar los resultados de la búsqueda real.  <br/> |
|[Límites de búsqueda de contenido](limits-for-content-search.md) <br/> |Obtenga información sobre los límites de la herramienta de búsqueda de contenido, como el número máximo de búsquedas que se pueden ejecutar a la vez.  <br/> |
|[Elementos sin indexar en la búsqueda de contenido](partially-indexed-items-in-content-search.md) <br/> |Obtenga información sobre los elementos sin indexar en Exchange y SharePoint que puede incluir en las estadísticas de resultados de búsqueda estimadas al ejecutar una búsqueda. También puede incluir elementos sin indexar al exportar los resultados de la búsqueda.  <br/> |
|[Búsqueda y eliminación de mensajes de correo electrónico](search-for-and-delete-messages-in-your-organization.md) <br/> |Obtenga información sobre cómo usar la búsqueda de contenido para buscar y eliminar un mensaje de correo electrónico de  *todos los*  buzones de la organización. Esto puede ayudarle a encontrar y eliminar mensajes de correo electrónico potencialmente dañinos o de alto riesgo.  <br/> |
|[Usar la búsqueda de contenido para buscar una lista de usuarios en el buzón y en las cuentas de OneDrive](search-the-mailbox-and-onedrive-for-business-for-a-list-of-users.md) <br/> |Obtenga información sobre cómo usar un script para buscar en el buzón y un sitio de una unidad de negocio para un grupo de usuarios. Vea [crear una lista de todas las ubicaciones de OneDrive](https://docs.microsoft.com/onedrive/list-onedrive-urls) para obtener los pasos sobre cómo generar rápidamente una lista de direcciones de correo electrónico que puede usar para las ubicaciones de contenido de origen cuando crea y ejecuta búsquedas de contenido.  <br/> |
|[Usar búsqueda de contenido para colecciones específicas](use-content-search-for-targeted-collections.md) <br/> |Obtenga información sobre cómo usar el script de Windows PowerShell de este artículo para realizar colecciones de destino con la búsqueda de contenido. Una colección de destino significa que desea buscar en una carpeta determinada porque está seguro de que los elementos que responden a un caso (o a elementos con privilegios) se encuentran en esa carpeta. Use el script de este artículo para obtener el identificador de carpeta o la ruta de acceso de las carpetas de sitio o de buzón de correo específicas que desea buscar.  <br/> |
|||
  
## <a name="core-ediscovery"></a>eDiscovery principal

La tabla siguiente contiene vínculos a temas que le ayudarán a usar los casos de eDiscovery principales. Puede usar los casos de eDiscovery principales para agregar administradores de exhibición de documentos electrónicos que puedan tener acceso al caso, realizar una retención de eDiscovery en ubicaciones de contenido relevantes para el caso, buscar contenido y exportar los resultados de la búsqueda desde el caso.
  
|**Tema**|**Descripción**|
|:-----|:-----|
|[Introducción a Core eDiscovery](get-started-core-ediscovery.md) |Obtenga información sobre cómo asignar permisos de exhibición de documentos electrónicos y crear casos de eDiscovery principales. En este tema también se proporciona información general sobre el flujo de trabajo de eDiscovery principal.<br/> |
|[Crear un caso de retención de eDiscovery](create-ediscovery-holds.md)|Obtenga información sobre cómo crear suspensiones de eDiscovery que se asocian con un caso de exhibición de documentos electrónicos principal para conservar el contenido relevante para el caso que está investigando.|
|[Buscar contenido en un caso de exhibición de documentos electrónicos principal](search-for-content-in-core-ediscovery.md)|Obtenga información sobre cómo buscar contenido que sea relevante para un caso. Puede crear rápidamente búsquedas que busquen en las ubicaciones de contenido en espera.|
|[Exportar contenido de un caso de eDiscovery principal](export-content-in-core-ediscovery.md)|Obtenga información sobre cómo exportar y descargar contenido desde un caso de exhibición de documentos electrónicos principal.|
|[Cerrar, volver a abrir y eliminar un caso de exhibición de documentos electrónicos principal](close-reopen-delete-core-ediscovery-cases.md)|Obtenga información sobre cómo administrar el ciclo de vida de un caso de exhibición de documentos electrónicos principal.|
|[Asignar permisos de exhibición de documentos electrónicos](assign-ediscovery-permissions.md)|Obtenga información sobre cómo asignar permisos a los usuarios para que puedan buscar contenido, poner ubicaciones de contenido en suspensión y realizar otras tareas relacionadas con la exhibición de documentos electrónicos.|
|[Configurar los límites de cumplimiento para la exhibición de documentos electrónicos principal](set-up-compliance-boundaries.md)|Obtenga información sobre cómo usar límites de cumplimiento para crear límites lógicos dentro de una organización que controlan las ubicaciones de contenido que puede buscar un administrador de exhibición de documentos electrónicos.|
|||
  
## <a name="advanced-ediscovery"></a>eDiscovery avanzado

La solución de eDiscovery avanzada de Microsoft 365 (también denominada *eDiscovery avanzado v 2.0*) se basa en las capacidades existentes de eDiscovery y de análisis en Office 365. Esta solución de eDiscovery proporciona un flujo de trabajo de un extremo a otro para preservar, recopilar, revisar, analizar y exportar contenido que responde a las investigaciones internas y externas de su organización. También permite a los equipos jurídicos administrar los custodios y el flujo de trabajo completo de notificación de retención legal para comunicarse con los administradores involucrados en un caso.

|**Tema**|**Descripción**|
|:-----|:-----|
|[Información general sobre eDiscovery avanzado](overview-ediscovery-20.md)|Este artículo presenta eDiscovery avanzado v 2.0 y proporciona una introducción de alto nivel del flujo de trabajo integrado de eDiscovery avanzado y cómo se alinea con el proceso de eDiscovery descrito por el modelo de referencia de detección electrónica|.
|[Introducción a eDiscovery avanzado](get-started-with-advanced-ediscovery.md)|Obtenga información sobre cómo empezar a usar la exhibición avanzada de documentos electrónicos, incluido el permiso necesario para la concesión de licencias y la exhibición de documentos electrónicos. En este artículo se muestra cómo crear un caso avanzado de eDiscovery y se proporciona un recorrido por el flujo de trabajo de eDiscovery avanzado.|
|[Trabajar con administradores](managing-custodians.md)|Obtenga información sobre cómo trabajar con custodios en una exhibición avanzada de documentos electrónicos. Este tema contiene vínculos a instrucciones paso a paso para agregar custodios a un caso, administrar custodios en un caso y ver la actividad de custodios en Microsoft 365 mediante la búsqueda en el registro de auditoría.|
|[Trabajar con las comunicaciones](managing-custodian-communications.md)|Obtenga información sobre cómo administrar el proceso de notificación de retención legal en eDiscovery avanzado. Esto incluye la creación y automatización del flujo de trabajo de notificaciones y cómo un usuario confirmó una notificación de retención.
|[Trabajar con errores de proceso](processing-data-for-case.md)|Obtenga información sobre la indización avanzada y cómo corregir errores de indización en el contenido de ubicaciones de contenido de apoyo y no Private, como los buzones de correo de Exchange, los sitios de SharePoint y las cuentas de OneDrive. Puede remediar los errores y, a continuación, cargar los archivos corregidos en un conjunto de revisión o corregir los errores de procesamiento individuales dentro de un conjunto de revisión.|
|[Recopilar datos para un caso](collecting-data-for-ediscovery.md)|Obtenga información acerca de la búsqueda de contenido en ubicaciones de contenido de Private y, a continuación, agregar datos de casos relevantes a un conjunto de revisión. Al copiar contenido en un conjunto de revisión, los datos se copian desde las ubicaciones originales de contenido a una ubicación de Azure Storage proporcionada por Microsoft. Esto proporciona un conjunto estático de documentos para el proceso de revisión.|
|[Administrar conjuntos de revisión](managing-review-sets.md)|Obtenga información sobre cómo revisar datos de casos en un conjunto de revisiones. Esto incluye la visualización, consulta, filtrado y etiquetado de documentos en un conjunto de revisión.
|[Analizar datos en un conjunto de revisión](analyzing-data-in-review-set.md)|Obtenga información sobre cómo ejecutar el análisis en los documentos de un conjunto de revisión. Los resultados de la ejecución del análisis incluyen la detección de sobreduplicación, el subprocesamiento de correo electrónico y la identificación de temas.|
|[Exportar datos de casos](exporting-data-ediscover20.md)|Obtenga información sobre cómo exportar datos de un caso para una revisión externa.|
|||

## <a name="roadmap"></a>Guía básica

Para ver qué características de eDiscovery se han iniciado, están implementando o están en desarrollo, visite el plan de desarrollo de [Microsoft 365](https://aka.ms/eDiscoRoadMap).
