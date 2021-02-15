---
title: Buscar contenido
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
ROBOTS: NOINDEX, NOFOLLOW
ms.assetid: df2d1e0f-b476-42c9-aade-4a260b24f193
description: Use la herramienta de exhibición de documentos electrónicos de búsqueda de contenido en el Centro de seguridad y cumplimiento de & para buscar rápidamente correo electrónico en buzones de Exchange, documentos en sitios de SharePoint y ubicaciones de OneDrive, y conversaciones de mensajería instantánea en Skype Empresarial.
ms.openlocfilehash: 6a82846514b3510c4ff9f9b79eeff20b789ad0ad
ms.sourcegitcommit: 8ad481ed61cb6dabf8afb0fb04296666fa166450
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "49422859"
---
# <a name="search-for-content-using-the-content-search-tool"></a>Buscar contenido mediante la herramienta de búsqueda de contenido

Use la herramienta de búsqueda de contenido en el Centro de seguridad & Cumplimiento para buscar rápidamente correo electrónico en buzones de Exchange, documentos en sitios de SharePoint y ubicaciones de OneDrive, y conversaciones de mensajería instantánea en Skype Empresarial. Puede usar la herramienta de búsqueda de contenido para buscar correo electrónico, documentos y conversaciones de mensajería instantánea en herramientas de colaboración como Microsoft Teams y Grupos de Microsoft 365.
  
## <a name="search-for-content"></a>Buscar contenido

El primer paso es empezar a usar la herramienta de búsqueda de contenido para elegir ubicaciones de contenido para buscar y configurar una consulta de palabra clave para buscar elementos específicos. O bien, simplemente puede dejar la consulta en blanco y devolver todos los elementos de las ubicaciones de destino.
  
- [Crear y ejecutar una](content-search.md) búsqueda de contenido 

- [Crear consultas de búsqueda y condiciones de uso para](keyword-queries-and-search-conditions.md) restringir la búsqueda 

- [Configurar el filtrado de permisos de búsqueda](permissions-filtering-for-content-search.md) para que un administrador de exhibición de documentos electrónicos solo pueda buscar en subconjuntos de buzones o sitios de su organización 

- [Ejecutar una búsqueda de lista de identificadores](csv-file-for-an-id-list-content-search.md) para buscar mensajes de correo electrónico específicos 

- [Buscar buzones basados en la nube ](search-cloud-based-mailboxes-for-on-premises-users.md) para usuarios locales en Microsoft 365

- [Ver estadísticas de palabras clave](view-keyword-statistics-for-content-search.md) para los resultados de una búsqueda y, a continuación, refinar la consulta si es necesario

- [Buscar datos de terceros que](use-content-search-to-search-third-party-data-that-was-imported.md) su organización ha importado a Microsoft 365

- [Edición masiva de](bulk-edit-content-searches.md) las ubicaciones de consulta y contenido para varias búsquedas

- [Reintentar una búsqueda de](retry-failed-content-search.md) contenido para resolver un error de ubicación de contenido

- [Conservar destinatarios CCO](https://docs.microsoft.com/exchange/policy-and-compliance/holds/preserve-bcc-recipients-and-group-members) para que pueda buscarlos 

## <a name="perform-actions-on-content-you-find"></a>Realizar acciones en el contenido que encuentre

Después de ejecutar una búsqueda y refinarla según sea necesario, el siguiente paso es hacer algo con los resultados devueltos por la búsqueda. Puede exportar y descargar los resultados en su equipo local o, en el caso de un ataque de correo electrónico en su organización, puede eliminar los resultados de una búsqueda de buzones de usuario.
  
- [Exportar los resultados de una búsqueda de contenido](export-search-results.md) y descargarlos en el equipo local 

- [Buscar y eliminar mensajes de correo electrónico,](search-for-and-delete-messages-in-your-organization.md) como mensajes con virus, datos adjuntos peligrosos o mensajes de suplantación de identidad

- [Exportar un informe sobre](export-a-content-search-report.md) los resultados de una búsqueda de contenido, sin exportar los resultados reales 

## <a name="learn-more-about-content-search"></a>Más información sobre la búsqueda de contenido

La búsqueda de contenido es fácil de usar, pero también es una herramienta eficaz. En segundo plano, está sucediendo mucho. Cuanto más lo sepa y comprenda su comportamiento y sus limitaciones, más correcto será usarlo para las necesidades de búsqueda e investigación de su organización. Obtenga información sobre:
  
- [Elementos parcialmente indizados en Exchange y SharePoint](partially-indexed-items-in-content-search.md) y cómo incluirlos o excluirlos al exportar y descargar resultados de búsqueda

- [Investigar elementos parcialmente indizados y](investigating-partially-indexed-items-in-ediscovery.md) determinar la exposición de su organización a ellos

- [Límites de la](limits-for-content-search.md)herramienta de búsqueda de contenido, como el número máximo de búsquedas que puede ejecutar a la vez y el número máximo de ubicaciones de contenido que puede incluir en una sola búsqueda

- [Resultados de búsqueda estimados](differences-between-estimated-and-actual-ediscovery-search-results.md) y reales y los motivos por los que puede haber diferencias entre ellos al exportar y descargar resultados de búsqueda

- [Desduplicación en los resultados](de-duplication-in-ediscovery-search-results.md) de búsqueda que puede habilitar al exportar mensajes de correo electrónico que son los resultados de una búsqueda

## <a name="use-scripts-for-advanced-scenarios"></a>Usar scripts para escenarios avanzados

A veces, debe realizar tareas de búsqueda de contenido más avanzadas, complejas y repetitivas. En estos casos, es más fácil y rápido usar comandos de PowerShell en el Centro de & cumplimiento. Para facilitar esto, hemos creado una serie de scripts de PowerShell del Centro de seguridad & cumplimiento para ayudarle a completar tareas complejas relacionadas con la búsqueda de contenido.
  
- [Buscar carpetas específicas de](use-content-search-for-targeted-collections.md) buzones y sitios (denominadas *colección de destino) cuando esté seguro de que los elementos que responden a un caso se encuentran en esa carpeta.

- [Buscar una lista de](search-the-mailbox-and-onedrive-for-business-for-a-list-of-users.md) usuarios en el buzón y la ubicación de OneDrive 

- [Crear, crear informes y eliminar varias](create-report-on-and-delete-multiple-content-searches.md) búsquedas para identificar y crear datos de búsqueda de forma rápida y eficaz 

- [Clone una búsqueda de contenido y](clone-a-content-search.md) compare rápidamente los resultados de diferentes consultas de búsqueda de palabras clave que se ejecutan en las mismas ubicaciones de contenido; o use el script para ahorrar tiempo al no tener que volver a escribir un gran número de ubicaciones de contenido al crear una nueva búsqueda
