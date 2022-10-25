---
title: Buscar contenido
description: Use la herramienta eDiscovery de búsqueda de contenido en el portal de cumplimiento Microsoft Purview para encontrar rápidamente correo electrónico en buzones de Exchange, documentos en sitios de SharePoint y ubicaciones de OneDrive, y conversaciones de mensajería instantánea en Skype Empresarial.
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- highpri
- tier1
- purview-compliance
- content-search
ms.openlocfilehash: 68adc95f2839d1e45957f0ac98cbcf19f9985807
ms.sourcegitcommit: e7dbe3b0d97cd8c64b5ae15f990d5e4b1dc9c464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/24/2022
ms.locfileid: "68687917"
---
# <a name="search-for-content-using-the-content-search-tool"></a>Búsqueda de contenido mediante la herramienta de búsqueda de contenido

Use la herramienta Búsqueda de contenido del portal de cumplimiento de Microsoft Purview para encontrar rápidamente correos electrónicos en buzones de Exchange, documentos en sitios de SharePoint y ubicaciones de OneDrive, y conversaciones de mensajería instantánea en Skype Empresarial. Puede usar la herramienta Búsqueda de contenido para buscar correos electrónicos, documentos y conversaciones de mensajería instantánea en herramientas de colaboración como Microsoft Teams y Grupos de Microsoft 365.
  
[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="search-for-content"></a>Buscar contenido

El primer paso consiste en empezar a usar la herramienta búsqueda de contenido para elegir ubicaciones de contenido para buscar y configurar una consulta de palabra clave para buscar elementos específicos. O bien, puede dejar la consulta en blanco y devolver todos los elementos de las ubicaciones de destino.

- [Cree y ejecute](content-search.md) una búsqueda de contenido.
- [Cree consultas de búsqueda y use condiciones](keyword-queries-and-search-conditions.md) para restringir la búsqueda.
- [Referencia de características](content-search-reference.md) para la búsqueda de contenido.
- [Configure el filtrado de permisos de búsqueda](permissions-filtering-for-content-search.md) para que un administrador de exhibición de documentos electrónicos solo pueda buscar en un subconjunto de buzones o sitios de su organización.
- [Busque en los buzones basados en la nube](search-cloud-based-mailboxes-for-on-premises-users.md) usuarios locales en Microsoft 365.
- [Vea las estadísticas de palabras clave](view-keyword-statistics-for-content-search.md) para los resultados de una búsqueda y, a continuación, refine la consulta si es necesario.
- [Busque datos de terceros](use-content-search-to-search-third-party-data-that-was-imported.md) que su organización haya importado a Microsoft 365.
- [Conserve los destinatarios de cco](/exchange/policy-and-compliance/holds/preserve-bcc-recipients-and-group-members) para que pueda buscarlos.

## <a name="perform-actions-on-content-you-find"></a>Realizar acciones en el contenido que encuentre

Después de ejecutar una búsqueda y refinarla según sea necesario, el siguiente paso es hacer algo con los resultados devueltos por la búsqueda. Puede exportar y descargar los resultados en el equipo local o, en el caso de un ataque por correo electrónico en su organización, puede eliminar los resultados de una búsqueda de buzones de usuario.

- [Exporte los resultados de una búsqueda de contenido](export-search-results.md) y descárguelos en el equipo local.
- [Busque y elimine mensajes de correo electrónico](search-for-and-delete-messages-in-your-organization.md), como mensajes que contengan un virus, datos adjuntos peligrosos o mensajes de phishing.
- [Exporte un informe](export-a-content-search-report.md) sobre los resultados de una búsqueda de contenido, sin exportar los resultados reales.

## <a name="learn-more-about-content-search"></a>Más información sobre la búsqueda de contenido

La búsqueda de contenido es fácil de usar, pero también es una herramienta eficaz. En segundo plano, hay mucho en marcha. Cuanto más lo sepa y comprenda su comportamiento y sus limitaciones, más éxito tendrá para las necesidades de búsqueda e investigación de su organización.
  
- [Límites de búsqueda de contenido](limits-for-content-search.md), como el número máximo de búsquedas que puede ejecutar a la vez y el número máximo de ubicaciones de contenido que puede incluir en una sola búsqueda.
- [Resultados de búsqueda estimados y reales](differences-between-estimated-and-actual-ediscovery-search-results.md) y las razones por las que puede haber diferencias entre ellos al exportar y descargar los resultados de búsqueda.
- [Elementos indizados parcialmente en Exchange y SharePoint y](partially-indexed-items-in-content-search.md) cómo incluirlos o excluirlos al exportar y descargar los resultados de búsqueda.
- [Investigue los elementos parcialmente indexados](investigating-partially-indexed-items-in-ediscovery.md) y determine la exposición de su organización a ellos.
- [Desduplicación en los resultados de búsqueda](de-duplication-in-ediscovery-search-results.md) que puede habilitar al exportar mensajes de correo electrónico que son los resultados de una búsqueda.

## <a name="use-scripts-for-advanced-scenarios"></a>Uso de scripts para escenarios avanzados

A veces tiene que realizar tareas de búsqueda de contenido más avanzadas, complejas y repetitivas. En estos casos, es más fácil y rápido usar comandos en [PowerShell de cumplimiento de seguridad &](/powershell/exchange/scc-powershell).

Para facilitar esto, hemos creado varios scripts de PowerShell de cumplimiento de seguridad & para ayudarle a completar tareas complejas relacionadas con la búsqueda de contenido.

- [Busque carpetas de buzón y de sitio específicas](use-content-search-for-targeted-collections.md) (denominadas recopilación  *de destino* ) cuando esté seguro de que los elementos que responden a un caso se encuentran en esa carpeta.
- Busque una lista de usuarios en [el buzón y la ubicación de OneDrive](search-the-mailbox-and-onedrive-for-business-for-a-list-of-users.md).
- [Cree, informe y elimine varias búsquedas](create-report-on-and-delete-multiple-content-searches.md) para identificar y eliminar datos de búsqueda de forma rápida y eficaz.
- [Clone una búsqueda de contenido](clone-a-content-search.md) y compare rápidamente los resultados de las distintas consultas de búsqueda de palabras clave que se ejecutan en las mismas ubicaciones de contenido; o use el script para ahorrar tiempo al no tener que volver a escribir un gran número de ubicaciones de contenido al crear una nueva búsqueda.
