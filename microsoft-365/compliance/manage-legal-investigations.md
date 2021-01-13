---
title: Administrar investigaciones legales en Microsoft 365
f1.keywords:
- NOCSH
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
ms.custom:
- seo-marvel-apr2020
description: Use casos de eDiscovery en el Centro de seguridad & cumplimiento en Office 365 para administrar la investigación legal de su organización.
ms.openlocfilehash: 7a02bd47f93a85e643694efea4dcc140847916e0
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840709"
---
# <a name="manage-legal-investigations-in-microsoft-365"></a>Administrar investigaciones legales en Microsoft 365

Las organizaciones tienen muchas razones para responder a un caso legal que involucra a determinados ejecutivos u otros empleados de su organización. Esto puede implicar encontrar y conservar rápidamente información específica de la investigación en correo electrónico, documentos, conversaciones de mensajería instantánea y otras ubicaciones de contenido usadas por las personas en sus tareas diarias. Puede realizar estas y muchas otras actividades similares mediante las herramientas de casos de eDiscovery en el centro de seguridad y cumplimiento.
  
**¿Quiere saber cómo Microsoft administra sus investigaciones de exhibición de documentos electrónicos?** A continuación se muestra una [documentación](https://go.microsoft.com/fwlink/?linkid=852161) técnica que puede descargar que explica cómo usamos las mismas herramientas de búsqueda e investigación para administrar nuestro flujo de trabajo de exhibición de documentos electrónicos interno.

## <a name="manage-legal-investigations-with-ediscovery-cases"></a>Administrar investigaciones legales con casos de exhibición de documentos electrónicos

Los casos de exhibición de documentos electrónicos le permiten controlar quién puede crear, tener acceso y administrar casos de exhibición de documentos electrónicos en su organización. Use casos para agregar miembros y controlar qué tipos de acciones pueden realizar, retener ubicaciones de contenido relevantes para un caso legal y usar la herramienta de búsqueda de contenido para buscar en las ubicaciones en espera contenido que pueda responder a su caso. A continuación, también puede exportar y descargar esos resultados para una investigación posterior por parte de revisores externos.
  
- [Administre el flujo de trabajo de exhibición](ediscovery-cases.md) de documentos electrónicos mediante la creación y el uso de casos de exhibición de documentos electrónicos para cada investigación legal que su organización tenga que llevar a cabo.

- [Asigne permisos de exhibición de documentos electrónicos](assign-ediscovery-permissions.md) para controlar quién puede crear y administrar casos de exhibición de documentos electrónicos en su organización.

- [Configure los límites de cumplimiento para](set-up-compliance-boundaries.md) controlar las ubicaciones de contenido de usuario en las que los administradores de exhibición de documentos electrónicos pueden buscar.

- [Busque contenido en](search-for-content.md) su organización.

### <a name="use-scripts-for-advanced-scenarios"></a>Usar scripts para escenarios avanzados

Al igual que en la sección anterior que enumera scripts para escenarios de búsqueda de contenido, también hemos creado algunos scripts de PowerShell del Centro de seguridad & Cumplimiento para ayudarle a administrar casos de exhibición de documentos electrónicos.
  
- [Cree un informe de retención de](create-a-report-on-holds-in-ediscovery-cases.md) exhibición de documentos electrónicos que contenga información sobre todas las retenciones asociadas a casos de exhibición de documentos electrónicos en su organización.

- [Agregue buzones y ubicaciones de OneDrive](use-a-script-to-add-users-to-a-hold-in-ediscovery.md) para una lista de usuarios a una retención de exhibición de documentos electrónicos.
  
## <a name="manage-legal-investigations-with-the-advanced-ediscovery-solution-in-microsoft-365"></a>Administrar investigaciones legales con la solución de eDiscovery avanzado en Microsoft 365

La solución de eDiscovery avanzado en Microsoft 365 se basa en las capacidades de análisis y exhibición de documentos electrónicos existentes en Office 365. Esta nueva solución, denominada *eDiscovery* avanzado, proporciona un flujo de trabajo completo para conservar, recopilar, revisar, analizar y exportar contenido que responde a las investigaciones internas y externas de su organización. También permite a los equipos legales administrar todo el flujo de trabajo de notificación de retención legal para comunicarse con los administradores implicados en un caso.

EDiscovery avanzado requiere una suscripción E5 para su organización de Microsoft 365 u Office 365. Para obtener más información acerca de las licencias, vea [Configurar eDiscovery avanzado.](get-started-with-advanced-ediscovery.md#step-1-verify-and-assign-appropriate-licenses)

Esta es una introducción rápida del flujo de trabajo integrado en eDiscovery avanzado. Para obtener más información, vea [Administrar el flujo de trabajo de eDiscovery avanzado.](create-and-manage-advanced-ediscoveryv2-case.md#manage-the-workflow)

- [Cree un caso](create-and-manage-advanced-ediscoveryv2-case.md#create-a-case) para empezar.

- [Administre los administradores](managing-custodians.md) agregándolos a un caso y colocando una retención legal en el contenido de su buzón, cuenta de OneDrive y Microsoft Teams de los que son miembros.

- [Administre las](managing-custodian-communications.md) comunicaciones con los administradores mediante la automatización del proceso de notificación de retención legal.

- [Indexar datos de administrador y](processing-data-for-case.md) corregir errores de indización para que pueda recopilar datos de forma eficaz para sus investigaciones.

- [Recopilar datos de](collecting-data-for-ediscovery.md) un caso y [agregarlos a un conjunto de revisión para](collecting-data-for-ediscovery.md#add-search-results-to-a-review-set) una investigación posterior.

- [Ver](view-documents-in-review-set.md) documentos, [datos de](review-set-search.md) consulta y [elementos de](tagging-documents.md) etiqueta en un conjunto de revisión.

- [Analizar los datos de casos](analyzing-data-in-review-set.md) con herramientas de análisis avanzadas.

- [Exportar datos de casos](exporting-data-ediscover20.md) para que los revise un asesor externo.

- [Administrar trabajos de larga duración](managing-jobs-ediscovery20.md) en eDiscovery avanzado.
