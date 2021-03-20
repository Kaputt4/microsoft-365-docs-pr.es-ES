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
description: Use casos de exhibición de documentos electrónicos en el Centro de seguridad & cumplimiento en Office 365 para administrar la investigación legal de su organización.
ms.openlocfilehash: c052daab8de33e21cccc3c638ab4995a007f60fb
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50903464"
---
# <a name="manage-legal-investigations-in-microsoft-365"></a>Administrar investigaciones legales en Microsoft 365

Las organizaciones tienen muchas razones para responder a un caso legal que implica a determinados ejecutivos u otros empleados de la organización. Esto puede implicar encontrar y conservar rápidamente información específica de la investigación en correo electrónico, documentos, conversaciones de mensajería instantánea y otras ubicaciones de contenido usadas por las personas en sus tareas diarias de trabajo. Puede realizar estas y muchas otras actividades similares mediante las herramientas de casos de exhibición de documentos electrónicos en el Centro de seguridad y cumplimiento.
  
**¿Quiere saber cómo Administra Microsoft sus investigaciones de exhibición de documentos electrónicos?** Esta es una [guía](https://go.microsoft.com/fwlink/?linkid=852161) técnica que puede descargar que explica cómo usamos las mismas herramientas de búsqueda e investigación para administrar nuestro flujo de trabajo interno de exhibición de documentos electrónicos.

## <a name="manage-legal-investigations-with-ediscovery-cases"></a>Administrar investigaciones legales con casos de exhibición de documentos electrónicos

Los casos de exhibición de documentos electrónicos permiten controlar quién puede crear, acceder y administrar casos de exhibición de documentos electrónicos en su organización. Use casos para agregar miembros y controlar qué tipos de acciones pueden realizar, colocar una retención en ubicaciones de contenido relevantes para un caso legal y usar la herramienta búsqueda de contenido para buscar en las ubicaciones en espera contenido que pueda responder a su caso. A continuación, también puede exportar y descargar esos resultados para una investigación posterior por parte de revisores externos.
  
- [Administre el flujo de trabajo de exhibición](./get-started-core-ediscovery.md) de documentos electrónicos mediante la creación y el uso de casos de exhibición de documentos electrónicos para cada investigación legal que su organización tenga que llevar a cabo.

- [Asigne permisos de exhibición de documentos electrónicos](assign-ediscovery-permissions.md) para controlar quién puede crear y administrar casos de exhibición de documentos electrónicos en su organización.

- [Configure los límites de cumplimiento para](set-up-compliance-boundaries.md) controlar las ubicaciones de contenido de usuario en las que los administradores de exhibición de documentos electrónicos pueden buscar.

- [Busque contenido en](search-for-content.md) su organización.

### <a name="use-scripts-for-advanced-scenarios"></a>Usar scripts para escenarios avanzados

Al igual que en la sección anterior que enumeraba scripts para escenarios de búsqueda de contenido, también hemos creado algunos scripts de PowerShell del Centro de seguridad & cumplimiento para ayudarle a administrar casos de exhibición de documentos electrónicos.
  
- [Cree un informe de retención de exhibición](create-a-report-on-holds-in-ediscovery-cases.md) de documentos electrónicos que contenga información sobre todas las retenciones asociadas con casos de exhibición de documentos electrónicos en su organización.

- [Agregue buzones y ubicaciones de OneDrive](use-a-script-to-add-users-to-a-hold-in-ediscovery.md) para una lista de usuarios a una retención de exhibición de documentos electrónicos.
  
## <a name="manage-legal-investigations-with-the-advanced-ediscovery-solution-in-microsoft-365"></a>Administrar investigaciones legales con la solución de exhibición de documentos electrónicos avanzada en Microsoft 365

La solución de exhibición de documentos electrónicos avanzada en Microsoft 365 se basa en las capacidades de análisis y exhibición de documentos electrónicos existentes en Office 365. Esta nueva solución, denominada *Exhibición* de documentos electrónicos avanzada, proporciona un flujo de trabajo completo para conservar, recopilar, revisar, analizar y exportar contenido que responda a las investigaciones internas y externas de la organización. También permite a los equipos legales administrar todo el flujo de trabajo de notificación de retención legal para comunicarse con los custodios implicados en un caso.

La exhibición de documentos electrónicos avanzada requiere una suscripción E5 para su organización de Microsoft 365 u Office 365. Para obtener más información acerca de las licencias, vea [Set up Advanced eDiscovery](get-started-with-advanced-ediscovery.md#step-1-verify-and-assign-appropriate-licenses).

Este es un resumen rápido del flujo de trabajo integrado en eDiscovery avanzado. Para obtener más información, vea [Manage the Advanced eDiscovery workflow](create-and-manage-advanced-ediscoveryv2-case.md#manage-the-workflow).

- [Cree un caso](create-and-manage-advanced-ediscoveryv2-case.md#create-a-case) para empezar.

- [Administre los custodios](managing-custodians.md) agregándolos a un caso y colocando una retención legal en el contenido de su buzón, cuenta de OneDrive y Microsoft Teams del que son miembros.

- [Administre las comunicaciones](managing-custodian-communications.md) con los custodios automatizando el proceso de notificación de retención legal.

- [Indexe los datos de custodia](processing-data-for-case.md) y corrija los errores de indización para que pueda recopilar datos de forma eficaz para las investigaciones.

- [Recopilar datos](collecting-data-for-ediscovery.md) para un caso y [agregarlos a un conjunto de revisión para](collecting-data-for-ediscovery.md#add-search-results-to-a-review-set) una investigación posterior.

- [Ver](view-documents-in-review-set.md) documentos, [datos de](review-set-search.md) consulta y [elementos de](tagging-documents.md) etiqueta en un conjunto de revisión.

- [Analizar los datos de casos](analyzing-data-in-review-set.md) con herramientas de análisis avanzadas.

- [Exportar datos de casos](exporting-data-ediscover20.md) para su revisión por parte de abogados externos.

- [Administrar trabajos de larga ejecución](managing-jobs-ediscovery20.md) en eDiscovery avanzada.