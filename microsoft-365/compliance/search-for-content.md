---
title: Buscar contenido
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
description: Use la herramienta eDiscovery de búsqueda de contenido en el portal de cumplimiento de Microsoft Purview para encontrar rápidamente correo electrónico en buzones de Exchange, documentos en sitios de SharePoint y ubicaciones de OneDrive, y conversaciones de mensajería instantánea en Skype Empresarial.
ms.openlocfilehash: b339d2f4ebe738407c42eda86f18a5167af03921
ms.sourcegitcommit: 52eea2b65c0598ba4a1b930c58b42dbe62cdaadc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/19/2022
ms.locfileid: "64941949"
---
# <a name="search-for-content-using-the-content-search-tool"></a>Búsqueda de contenido mediante la herramienta de búsqueda de contenido

Use la herramienta búsqueda de contenido en el portal de cumplimiento de Microsoft Purview para encontrar rápidamente correo electrónico en buzones de Exchange, documentos en sitios SharePoint y ubicaciones de OneDrive, y conversaciones de mensajería instantánea en Skype Empresarial. Puede usar la herramienta Búsqueda de contenido para buscar correos electrónicos, documentos y conversaciones de mensajería instantánea en herramientas de colaboración como Microsoft Teams y Grupos de Microsoft 365.
  
## <a name="search-for-content"></a>Buscar contenido

El primer paso consiste en empezar a usar la herramienta búsqueda de contenido para elegir ubicaciones de contenido para buscar y configurar una consulta de palabra clave para buscar elementos específicos. O bien, puede dejar la consulta en blanco y devolver todos los elementos de las ubicaciones de destino.
  
- [Creación y ejecución](content-search.md) de una búsqueda de contenido

- [Compilación de consultas de búsqueda y condiciones de uso](keyword-queries-and-search-conditions.md) para restringir la búsqueda

- [Referencia de características](content-search-reference.md) para la búsqueda de contenido

- [Configurar el filtrado de permisos de búsqueda](permissions-filtering-for-content-search.md) para que un administrador de exhibición de documentos electrónicos solo pueda buscar un subconjunto de buzones o sitios de la organización

- [Busque en los buzones basados en la nube](search-cloud-based-mailboxes-for-on-premises-users.md) los usuarios locales de Microsoft 365

- [Ver estadísticas de palabras clave](view-keyword-statistics-for-content-search.md) para los resultados de una búsqueda y, a continuación, refinar la consulta si es necesario

- [Busque datos de terceros](use-content-search-to-search-third-party-data-that-was-imported.md) que la organización haya importado a Microsoft 365

- [Conservar destinatarios de cco](/exchange/policy-and-compliance/holds/preserve-bcc-recipients-and-group-members) para que pueda buscarlos

## <a name="perform-actions-on-content-you-find"></a>Realizar acciones en el contenido que encuentre

Después de ejecutar una búsqueda y refinarla según sea necesario, el siguiente paso es hacer algo con los resultados devueltos por la búsqueda. Puede exportar y descargar los resultados en el equipo local o, en el caso de un ataque por correo electrónico en su organización, puede eliminar los resultados de una búsqueda de buzones de usuario.
  
- [Exportar los resultados de una búsqueda de contenido](export-search-results.md) y descargarlos en el equipo local

- [Busque y elimine mensajes de correo electrónico](search-for-and-delete-messages-in-your-organization.md), como mensajes que contengan un virus, datos adjuntos peligrosos o mensajes de suplantación de identidad

- [Exportación de un informe](export-a-content-search-report.md) sobre los resultados de una búsqueda de contenido, sin exportar los resultados reales

## <a name="learn-more-about-content-search"></a>Más información sobre la búsqueda de contenido

La búsqueda de contenido es fácil de usar, pero también es una herramienta eficaz. En segundo plano, hay mucho en marcha. Cuanto más lo sepa y comprenda su comportamiento y sus limitaciones, más éxito tendrá para las necesidades de búsqueda e investigación de su organización. Obtenga información sobre:
  
- [Límites de búsqueda de contenido](limits-for-content-search.md), como el número máximo de búsquedas que puede ejecutar a la vez y el número máximo de ubicaciones de contenido que puede incluir en una sola búsqueda.

- [Resultados de búsqueda estimados y reales](differences-between-estimated-and-actual-ediscovery-search-results.md) y las razones por las que puede haber diferencias entre ellos al exportar y descargar los resultados de búsqueda.

- [Elementos indizados parcialmente en Exchange y SharePoint](partially-indexed-items-in-content-search.md) y cómo incluirlos o excluirlos al exportar y descargar los resultados de la búsqueda

- [Investigar elementos parcialmente indexados](investigating-partially-indexed-items-in-ediscovery.md) y determinar la exposición de su organización a ellos

- [Desduplicación en los resultados de búsqueda](de-duplication-in-ediscovery-search-results.md) que puede habilitar al exportar mensajes de correo electrónico que son los resultados de una búsqueda

## <a name="use-scripts-for-advanced-scenarios"></a>Uso de scripts para escenarios avanzados

A veces tiene que realizar tareas de búsqueda de contenido más avanzadas, complejas y repetitivas. En estos casos, es más fácil y rápido usar comandos en PowerShell de Security & Compliance Center. Para facilitar esto, hemos creado una serie de scripts de PowerShell de Security & Compliance Center para ayudarle a completar tareas complejas relacionadas con la búsqueda de contenido.

- [Busque carpetas de buzón de correo y de sitio específicas](use-content-search-for-targeted-collections.md) (denominadas recopilación  *de destino* ) cuando esté seguro de que los elementos que responden a un caso se encuentran en esa carpeta.

- Busque una lista de usuarios [en el buzón de correo y OneDrive ubicación](search-the-mailbox-and-onedrive-for-business-for-a-list-of-users.md).

- [Creación, generación de informes y eliminación de varias búsquedas](create-report-on-and-delete-multiple-content-searches.md) para identificar y eliminar datos de búsqueda de forma rápida y eficaz

- [Clone una búsqueda de contenido](clone-a-content-search.md) y compare rápidamente los resultados de las distintas consultas de búsqueda de palabras clave que se ejecutan en las mismas ubicaciones de contenido; o usar el script para ahorrar tiempo al no tener que volver a escribir un gran número de ubicaciones de contenido al crear una nueva búsqueda
