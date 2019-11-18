---
title: Administración de investigaciones legales en Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 2e5fbe9f-ee4d-4178-8ff8-4356bc1b168e
description: Use casos de exhibición de documentos electrónicos en el centro de seguridad & cumplimiento en Office 365 para administrar la investigación legal de su organización. Si tiene una suscripción a E5, puede analizar más datos de caso con las capacidades de análisis de texto, aprendizaje de la máquina y Codificación predictiva de eDiscovery avanzado.
ms.openlocfilehash: ce476c93e9c33d949c5615f872b8399a97420bba
ms.sourcegitcommit: 31392b9599f4b4e9981a1278d6beb9f0a2839ecf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/14/2019
ms.locfileid: "38687604"
---
# <a name="manage-legal-investigations-in-office-365"></a>Administración de investigaciones legales en Office 365

Las organizaciones tienen muchas razones para responder a un caso legal en el que participan determinados ejecutivos u otros empleados de la organización. Esto puede implicar una rápida búsqueda y retención de información específica de investigación en el correo electrónico, los documentos, las conversaciones de mensajería instantánea y otras ubicaciones de contenido que usan los usuarios en sus tareas de trabajo cotidianas. Puede realizar estas y muchas otras actividades similares usando las herramientas de caso de exhibición de documentos electrónicos en el centro de seguridad y cumplimiento.
  
**¿Desea saber cómo administra Microsoft sus investigaciones de eDiscovery?** A continuación se describen las [notas del producto](https://go.microsoft.com/fwlink/?linkid=852161) que puede descargar y que explican cómo usamos las mismas herramientas de búsqueda e investigación de Office 365 para administrar nuestro flujo de trabajo de eDiscovery interno.
   
## <a name="manage-legal-investigations-with-ediscovery-cases"></a>Administración de investigaciones legales con casos de eDiscovery

los casos de eDiscovery le permiten controlar quién puede crear, acceder y administrar casos de eDiscovery en su organización. Use casos para agregar miembros y controlar los tipos de acciones que pueden realizar, poner una retención en las ubicaciones de contenido relevantes para un caso legal y usar la herramienta de búsqueda de contenido para buscar en las ubicaciones en espera el contenido que pueda responder a su caso. A continuación, también puede exportar y descargar los resultados para seguir investigando por revisores externos.
  
- [Administrar el flujo de trabajo de eDiscovery](ediscovery-cases.md) mediante la creación y el uso de casos de eDiscovery para cada investigación legal que la organización tiene que llevar a cabo 
    
- [Asignar permisos de exhibición](assign-ediscovery-permissions.md) de documentos electrónicos para controlar quién puede crear y administrar casos de eDiscovery en su organización 
    
- [Configurar límites de cumplimiento](tagging-and-assessment-in-advanced-ediscovery.md) para controlar las ubicaciones de contenido del usuario que los administradores de eDiscovery pueden buscar 
    
- [Buscar contenido](search-for-content.md) en la organización 
    
### <a name="use-scripts-for-advanced-scenarios"></a>Usar scripts para escenarios avanzados

Al igual que en la sección anterior que enumeraba scripts para escenarios de búsqueda de contenido, también hemos creado algunos scripts de PowerShell del centro de cumplimiento de & de seguridad para ayudarle a administrar casos de eDiscovery.
  
- [Crear un informe de suspensión de exhibición](create-a-report-on-holds-in-ediscovery-cases.md) de documentos electrónicos que contenga información sobre todas las retenciones asociadas con casos de eDiscovery en su organización 
    
- [Agregar buzones de correo y ubicaciones de OneDrive](use-a-script-to-add-users-to-a-hold-in-ediscovery.md) para una lista de usuarios a una suspensión de exhibición de documentos electrónicos 
  
## <a name="manage-legal-investigations-with-the-advanced-ediscovery-solution-in-microsoft-365"></a>Administración de investigaciones legales con la solución de eDiscovery avanzada en Microsoft 365

La solución Advanced eDiscovery de Microsoft 365 se basa en las capacidades existentes de eDiscovery y de análisis en Office 365. Esta nueva solución, denominada *exhibición avanzada*de documentos electrónicos, proporciona un flujo de trabajo de un extremo a otro para preservar, recopilar, revisar, analizar y exportar contenido que responde a las investigaciones internas y externas de la organización. También permite a los equipos jurídicos administrar todo el flujo de trabajo de notificación de retención legal para comunicarse con los administradores involucrados en un caso.

EDiscovery avanzado requiere una suscripción a e5 para la organización de Office 365 o Microsoft 365. Como alternativa, los usuarios con una licencia E3 requieren la suscripción complementaria de cumplimiento avanzado para que pueda administrarlos como custodios en un caso de eDiscovery avanzado.

A continuación, se presenta una introducción rápida al flujo de trabajo integrado en eDiscovery avanzado. Para obtener más información, vea [Overview of The Advanced eDiscovery Solution en Microsoft 365](overview-ediscovery-20.md).

- [Crear un caso](create-new-ediscovery-case.md) para empezar

- [Administrar los custodios](managing-custodians.md) agregándolos a un caso y colocando una retención legal en el contenido de su buzón de correo, la cuenta de OneDrive y Microsoft Teams de los que son miembros

- [Administrar las comunicaciones](managing-custodian-communications.md) con los custodios mediante la automatización del proceso de notificación de retención legal

- [Indizar los datos de custodios](processing-data-for-case.md) y corregir errores de indización para que pueda recopilar datos de forma eficaz para sus investigaciones

- [Recopilar datos](collecting-data-for-ediscovery.md) para un caso y agregarlos [a un conjunto de revisión](collecting-data-for-ediscovery.md#adding-search-results-to-a-review-set) para una investigación más detallada

- [Ver](view-documents-in-review-set.md) documentos, [consultar](review-set-search.md) datos y [etiquetar](tagging-documents.md) elementos en un conjunto de revisión

- [Analizar datos de casos](analyzing-data-in-review-set.md) con herramientas de análisis avanzadas

- [Exportar datos de casos](exporting-data-ediscover20.md) para revisión de asesores externos

- [Administrar trabajos de ejecución prolongada](managing-jobs-ediscovery20.md) en eDiscovery avanzado
