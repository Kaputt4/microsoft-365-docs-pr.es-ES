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
description: Use la herramienta de exhibición de documentos electrónicos de búsqueda de contenido en el Centro de seguridad y cumplimiento de & para buscar rápidamente correo electrónico en buzones de Exchange, documentos en sitios SharePoint y ubicaciones OneDrive y conversaciones de mensajería instantánea en Skype Empresarial.
ms.openlocfilehash: a70c234331d1329fb80f32fb81762391a862d487
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/30/2021
ms.locfileid: "53226064"
---
# <a name="search-for-content-using-the-content-search-tool"></a>Buscar contenido con la herramienta de búsqueda de contenido

Use la herramienta búsqueda de contenido en el Centro de seguridad y cumplimiento de & para buscar rápidamente correo electrónico en buzones de Exchange, documentos en sitios SharePoint y ubicaciones OneDrive y conversaciones de mensajería instantánea en Skype Empresarial. Puede usar la herramienta de búsqueda de contenido para buscar conversaciones de correo electrónico, documentos y mensajería instantánea en herramientas de colaboración como Microsoft Teams y Microsoft 365 grupos.

## <a name="search-for-content"></a>Buscar contenido

El primer paso es empezar a usar la herramienta búsqueda de contenido para elegir ubicaciones de contenido para buscar y configurar una consulta de palabras clave para buscar elementos específicos. O bien, puede dejar la consulta en blanco y devolver todos los elementos de las ubicaciones de destino.

- [Crear y ejecutar una](content-search.md) búsqueda de contenido

- [Referencia de característica] para búsqueda de contenido (content-search-reference.md)

- [Crear consultas de búsqueda y usar condiciones para](keyword-queries-and-search-conditions.md) restringir la búsqueda

- [Configurar el filtrado de permisos de búsqueda](permissions-filtering-for-content-search.md) para que un administrador de exhibición de documentos electrónicos solo pueda buscar subconjunto de buzones o sitios de su organización

- [Ejecutar una búsqueda de lista de identificadores](csv-file-for-an-id-list-content-search.md) para buscar mensajes de correo electrónico específicos

- [Buscar buzones de correo basados en la nube](search-cloud-based-mailboxes-for-on-premises-users.md) para usuarios locales en Microsoft 365

- [Ver estadísticas de palabras clave](view-keyword-statistics-for-content-search.md) para los resultados de una búsqueda y, a continuación, refinar la consulta si es necesario

- [Busque datos de terceros que](use-content-search-to-search-third-party-data-that-was-imported.md) su organización haya importado a Microsoft 365

- [Editar de forma masiva](bulk-edit-content-searches.md) las ubicaciones de consulta y contenido de varias búsquedas

- [Reintentar una búsqueda de](retry-failed-content-search.md) contenido para resolver un error de ubicación de contenido

- [Conservar destinatarios CCO para](/exchange/policy-and-compliance/holds/preserve-bcc-recipients-and-group-members) que pueda buscarlos

## <a name="perform-actions-on-content-you-find"></a>Realizar acciones en el contenido que encuentre

Después de ejecutar una búsqueda y refinarla según sea necesario, el siguiente paso es hacer algo con los resultados devueltos por la búsqueda. Puede exportar y descargar los resultados en el equipo local o, en el caso de un ataque de correo electrónico en su organización, puede eliminar los resultados de una búsqueda de buzones de usuario.

- [Exportar los resultados de una búsqueda de contenido](export-search-results.md) y descargarlos en el equipo local

- [Buscar y eliminar mensajes de correo electrónico,](search-for-and-delete-messages-in-your-organization.md) como mensajes que contenta un virus, datos adjuntos peligrosos o mensajes de suplantación de identidad

- [Exportar un informe sobre](export-a-content-search-report.md) los resultados de una búsqueda de contenido, sin exportar los resultados reales

## <a name="learn-more-about-content-search"></a>Más información sobre la búsqueda de contenido

La búsqueda de contenido es fácil de usar, pero también es una herramienta eficaz. En segundo plano, hay mucho que hacer. Cuanto más sepa sobre él y comprenda su comportamiento y sus limitaciones, más correcto lo va a usar para las necesidades de búsqueda e investigación de su organización. Obtenga información sobre:

- [Elementos parcialmente indizados en Exchange](partially-indexed-items-in-content-search.md) y SharePoint y cómo incluirlos o excluirlos al exportar y descargar resultados de búsqueda

- [Investigar elementos parcialmente indizados](investigating-partially-indexed-items-in-ediscovery.md) y determinar la exposición de su organización a ellos

- [Límites de la herramienta de](limits-for-content-search.md)búsqueda de contenido, como el número máximo de búsquedas que puede ejecutar a la vez y el número máximo de ubicaciones de contenido que puede incluir en una sola búsqueda

- [Resultados de búsqueda estimados y](differences-between-estimated-and-actual-ediscovery-search-results.md) reales y los motivos por los que puede haber diferencias entre ellos al exportar y descargar resultados de búsqueda

- [Desduplicación en los resultados](de-duplication-in-ediscovery-search-results.md) de búsqueda que puede habilitar al exportar mensajes de correo electrónico que son los resultados de una búsqueda

## <a name="use-scripts-for-advanced-scenarios"></a>Usar scripts para escenarios avanzados

A veces, debe realizar tareas de búsqueda de contenido más avanzadas, complejas y repetitivas. En estos casos, es más fácil y rápido usar comandos de PowerShell en el Centro de seguridad & cumplimiento. Para facilitar esta tarea, hemos creado una serie de scripts de PowerShell del Centro de seguridad & cumplimiento para ayudarle a completar tareas complejas relacionadas con la búsqueda de contenido.

- [Buscar carpetas de sitios](use-content-search-for-targeted-collections.md) y buzones específicos (denominadas colecciones *dirigidas) cuando esté seguro de que los elementos que responden a un caso se encuentran en esa carpeta.

- [Busque una lista de usuarios en OneDrive buzón](search-the-mailbox-and-onedrive-for-business-for-a-list-of-users.md) de correo y la ubicación del buzón de correo.

- [Crear, informar y eliminar varias búsquedas](create-report-on-and-delete-multiple-content-searches.md) para identificar y controlar de forma rápida y eficaz los datos de búsqueda

- [Clone una búsqueda de contenido](clone-a-content-search.md) y compare rápidamente los resultados de diferentes consultas de búsqueda de palabras clave que se ejecutan en las mismas ubicaciones de contenido; o usar el script para ahorrar tiempo al no tener que volver a escribir un gran número de ubicaciones de contenido al crear una nueva búsqueda