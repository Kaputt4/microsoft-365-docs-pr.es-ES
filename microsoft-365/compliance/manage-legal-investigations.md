---
title: Administración de investigaciones legales en Microsoft 365
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 2e5fbe9f-ee4d-4178-8ff8-4356bc1b168e
ms.custom:
- seo-marvel-apr2020
description: Use casos de eDiscovery en el portal de cumplimiento de Microsoft Purview para administrar la investigación legal de su organización.
ms.openlocfilehash: f75d59e58ae51e5cb525044edb775c87b52686d1
ms.sourcegitcommit: 133bf9097785309da45df6f374a712a48b33f8e9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/10/2022
ms.locfileid: "66010074"
---
# <a name="manage-legal-investigations-in-microsoft-365"></a>Administración de investigaciones legales en Microsoft 365

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

Las organizaciones tienen muchas razones para responder a un caso legal que involucra a ciertos ejecutivos u otros empleados de su organización. Esto puede implicar encontrar y conservar rápidamente información específica de investigación adicional en correo electrónico, documentos, conversaciones de mensajería instantánea y otras ubicaciones de contenido usadas por personas en sus tareas diarias de trabajo. Puede realizar estas y muchas otras actividades similares mediante las herramientas de casos de exhibición de documentos electrónicos en el Centro de seguridad y cumplimiento.
  
**¿Desea saber cómo Microsoft administra sus investigaciones de exhibición de documentos electrónicos?** Este es un [documento técnico](https://go.microsoft.com/fwlink/?linkid=852161) que puede descargar y que explica cómo usamos las mismas herramientas de búsqueda e investigación para administrar nuestro flujo de trabajo interno de eDiscovery.

## <a name="manage-legal-investigations-with-ediscovery-cases"></a>Administración de investigaciones legales con casos de eDiscovery

Los casos de eDiscovery permiten controlar quién puede crear, acceder y administrar casos de exhibición de documentos electrónicos en su organización. Use casos para agregar miembros y controlar qué tipos de acciones pueden realizar, colocar una suspensión en las ubicaciones de contenido pertinentes para un caso legal y usar la herramienta Búsqueda de contenido para buscar contenido que pueda responder a su caso en las ubicaciones en espera. A continuación, también puede exportar y descargar esos resultados para una investigación adicional por parte de revisores externos.
  
- [Administre el flujo de trabajo de eDiscovery](./get-started-core-ediscovery.md) mediante la creación y el uso de casos de exhibición de documentos electrónicos para cada investigación legal que su organización tenga que realizar.

- [Asigne permisos de exhibición de documentos electrónicos](assign-ediscovery-permissions.md) para controlar quién puede crear y administrar casos de exhibición de documentos electrónicos en su organización.

- [Configure los límites de cumplimiento](set-up-compliance-boundaries.md) para controlar las ubicaciones de contenido del usuario que los administradores de eDiscovery pueden buscar.

- [Busque contenido](search-for-content.md) en su organización.

### <a name="use-scripts-for-advanced-scenarios"></a>Uso de scripts para escenarios avanzados

Al igual que en la sección anterior que enumeraba scripts para escenarios de búsqueda de contenido, también hemos creado algunos scripts de PowerShell de cumplimiento de seguridad & para ayudarle a administrar casos de eDiscovery.
  
- [Cree un informe de suspensión de eDiscovery](create-a-report-on-holds-in-ediscovery-cases.md) que contenga información sobre todas las retenciones asociadas a casos de exhibición de documentos electrónicos en su organización.

- [Agregue buzones de correo y ubicaciones de OneDrive](use-a-script-to-add-users-to-a-hold-in-ediscovery.md) para una lista de usuarios a una suspensión de eDiscovery.
  
## <a name="manage-legal-investigations-with-the-ediscovery-premium-solution-in-microsoft-365"></a>Administrar investigaciones legales con la solución eDiscovery (Premium) en Microsoft 365

La solución eDiscovery (Premium) de Microsoft Purview en Microsoft 365 se basa en las funcionalidades de eDiscovery y análisis existentes en Office 365. Esta nueva solución, denominada *eDiscovery (Premium)*, proporciona un flujo de trabajo de un extremo a otro para conservar, recopilar, revisar, analizar y exportar contenido que responda a las investigaciones internas y externas de su organización. También permite al equipo legal gestionar todo el flujo de trabajo de notificación de retención legal para comunicarse con los administradores de un caso.

eDiscovery (Premium) requiere una suscripción A5 para la organización Microsoft 365 o Office 365. Para obtener más información sobre las licencias, vea [Configurar eDiscovery (Premium)](get-started-with-advanced-ediscovery.md#step-1-verify-and-assign-appropriate-licenses).

Esta es una introducción rápida al flujo de trabajo integrado en eDiscovery (Premium). Para obtener más información, vea [Administrar el flujo de trabajo de eDiscovery (Premium).](create-and-manage-advanced-ediscoveryv2-case.md#manage-the-workflow)

- [Cree un caso](create-and-manage-advanced-ediscoveryv2-case.md#create-a-case) para empezar.

- [Administre los custodios](managing-custodians.md) agregándolos a un caso y colocando una suspensión legal del contenido en su buzón de correo, OneDrive cuenta y Microsoft Teams de los que son miembros.

- [Administre las comunicaciones](managing-custodian-communications.md) con los custodios mediante la automatización del proceso de notificación de suspensión legal.

- [Indexe los datos del custodio](processing-data-for-case.md) y corrija los errores de indexación para que pueda recopilar datos de forma eficaz para las investigaciones.

- [Recopile datos](collecting-data-for-ediscovery.md) para un caso y [agréguelos a un conjunto de revisión](collecting-data-for-ediscovery.md#add-search-results-to-a-review-set) para una investigación más detallada.

- [Ver](view-documents-in-review-set.md) documentos, [consultar](review-set-search.md) datos y [etiquetar](tagging-documents.md) elementos en un conjunto de revisión.

- [Analice los datos de casos](analyzing-data-in-review-set.md) con herramientas de análisis avanzadas.

- [Exportación de datos de casos](exporting-data-ediscover20.md) para su revisión por parte de un asesor externo.

- [Administrar trabajos de larga duración](managing-jobs-ediscovery20.md) en eDiscovery (Premium).