---
title: Extensibilidad de cumplimiento de Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Obtenga información sobre cómo ampliar las soluciones de cumplimiento de Microsoft 365 mediante conectores de datos de terceros y API de Microsoft Graph.
ms.openlocfilehash: 676c0ba41e517dd0c3692fec29a1d4034641b634
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919726"
---
# <a name="microsoft-365-compliance-extensibility"></a>Extensibilidad de cumplimiento de Microsoft 365

Las soluciones de cumplimiento de Microsoft 365 ayudan a las organizaciones a evaluar de forma inteligente sus riesgos de cumplimiento, a controlar y proteger datos confidenciales y a responder eficazmente a los requisitos normativos. El cumplimiento de Microsoft 365 está enriquecido en escenarios de extensibilidad y permite a las organizaciones adaptar, ampliar, integrar, acelerar y admitir sus soluciones de cumplimiento.

Hay dos bloques de creación clave para la extensibilidad de cumplimiento:

- **Conectores de datos**. Se usa para importar y archivar datos que no son de Microsoft para que pueda aplicar capacidades de protección y gobierno de Microsoft 365 a datos de terceros.

- **API**. Permite el acceso mediante programación a las capacidades de cumplimiento de Microsoft 365.

## <a name="data-connectors"></a>Conectores de datos

Microsoft proporciona conectores de datos de terceros que se pueden configurar en el Centro de cumplimiento de Microsoft 365. Para obtener una lista de conectores de datos proporcionados por Microsoft, consulte la [tabla Conectores](archiving-third-party-data.md#third-party-data-connectors) de datos de terceros. La tabla de conectores de datos de terceros también resume las soluciones de cumplimiento que puede aplicar a datos de terceros después de importar y archivar datos en Microsoft 365 y vínculos a las instrucciones paso a paso para cada conector.

Para obtener más información acerca de los conectores de datos de Microsoft 365, vea [Archivado de datos de terceros](archiving-third-party-data.md). Si un tipo de datos de terceros no es compatible con los conectores de datos disponibles en el Centro de cumplimiento de Microsoft 365, puede trabajar con un partner que pueda proporcionarle un conector personalizado. Para obtener una lista de partners con los que puede trabajar y el proceso paso a paso para este método, vea Trabajar con un partner para archivar datos [de terceros](work-with-partner-to-archive-third-party-data.md).

### <a name="prerequisites-for-data-connectors"></a>Requisitos previos para conectores de datos

Muchos de los conectores de datos disponibles en el Centro de cumplimiento de Microsoft 365 para importar y archivar datos de terceros requieren que prepare y realice tareas de configuración en el origen de datos de terceros. Estos requisitos previos se documentan detalladamente para cada conector de datos de terceros.

Para los conectores de datos del Centro de cumplimiento de Microsoft 365 proporcionado por uno de los partners de Microsoft, la organización necesitará una relación comercial con el partner antes de poder implementar un conector.

Puede encontrar los requisitos de licencias para conectores de datos de terceros en el documento Comparación de licencias de cumplimiento de [Microsoft 365.](/office365/servicedescriptions/downloads/microsoft-365-compliance-licensing-comparison.xlsx)

## <a name="apis"></a>API

Las API de cumplimiento de Microsoft 365 están disponibles en el SDK de Microsoft Information Protection, la API de Microsoft Graph y la API de actividad de administración de Office 365. Algunas API de cumplimiento forman parte de un nuevo conjunto de API de seguridad y cumplimiento que permiten a los desarrolladores de clientes de Microsoft 365, proveedores de software independientes, integradores de sistemas y proveedores de servicios de seguridad administrados crear soluciones de seguridad y cumplimiento de alto valor.

Para obtener más información sobre cómo obtener acceso a las API de Graph, vea [Overview of Microsoft Graph](/graph/overview).

### <a name="microsoft-information-protection-mip-sdk"></a>Microsoft Information Protection (MIP) SDK

El SDK de MIP expone los servicios de etiquetado y protección de los centros de seguridad y cumplimiento de Microsoft 365 a servicios y aplicaciones de terceros. Los desarrolladores pueden usar el SDK para crear compatibilidad nativa para aplicar etiquetas y protección a los archivos. Los desarrolladores pueden determinar qué acciones deben realizarse cuando se detectan etiquetas específicas y la razón sobre la información cifrada por MIP.

Los casos de uso de SDK de MIP de alto nivel incluyen:

- Una aplicación de línea de negocio que aplica etiquetas de clasificación a los archivos que se exportan.

- Una aplicación de diseño CAD/CAM que proporciona compatibilidad nativa con el etiquetado MIP.

- Un agente de seguridad de acceso a la nube o una solución de prevención de pérdida de datos que puede cifrar datos con Azure Information Protection.

Para obtener más información sobre el SDK de MIP, los requisitos previos, los escenarios adicionales y los ejemplos, vea [Introducción al SDK de MIP](/information-protection/develop/overview).

### <a name="microsoft-graph-api-for-teams-dlp"></a>API de Microsoft Graph para DLP de Teams

[Las capacidades de](dlp-microsoft-teams.md) prevención de pérdida de datos (DLP) se usan ampliamente en Microsoft Teams, especialmente a medida que las organizaciones se han desplazado al trabajo remoto. A principios de este año [anunciamos la versión preliminar](https://developer.microsoft.com/graph/blogs/announcing-change-notifications-for-microsoft-teams-messages/) pública de la API de notificación de cambios de Microsoft Graph para los mensajes en Teams. Esta API permite a los desarrolladores crear aplicaciones que puedan escuchar mensajes de Microsoft Teams en tiempo casi real y, a continuación, implementar escenarios dlp para clientes y partners. Además, la API de revisión de Microsoft Graph te permite aplicar acciones DLP a los mensajes de Teams.

Estas dos API forman la API de Microsoft Graph para DLP de Teams. Puedes empezar probando la aplicación [de ejemplo](https://github.com/microsoftgraph/csharp-webhook-with-resource-data). Para obtener más información acerca de los webhooks de mensajería de Microsoft Teams, consulte la [documentación](/graph/api/subscription-post-subscriptions).

Para obtener información sobre los requisitos de licencia para DLP de Teams, consulte [Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#communication-data-loss-prevention-for-teams).

### <a name="microsoft-graph-api-for-ediscovery-preview"></a>API de Microsoft Graph para exhibición de documentos electrónicos (versión preliminar)

Con la exhibición de documentos electrónicos [avanzada,](overview-ediscovery-20.md)las organizaciones pueden descubrir los datos donde se encuentran y administrar más flujos de trabajo de exhibición de documentos electrónicos de extremo a extremo con capacidades inteligentes de aprendizaje automático y análisis para reducir los datos al conjunto pertinente, todo ello mientras los datos permanecen dentro del límite de seguridad y cumplimiento de Microsoft 365.

Las API de Graph para eDiscovery avanzada se pueden usar para crear y administrar casos, conjuntos de revisión y consultas de conjunto de revisión de forma escalable y repetible. Esto permite a los clientes y partners crear aplicaciones y flujos de trabajo para automatizar procesos comunes y repetitivos, como crear casos y administrar custodias y retenciones legales.

El primer conjunto de API de Graph para eDiscovery están disponibles en versión preliminar pública. Planeamos agregar más funcionalidades al final del año calendario. Para obtener más información sobre estas API y otras actualizaciones de eDiscovery avanzada, vea este [blog](https://aka.ms/Ignite2020AeDAA).

Para obtener información sobre los requisitos de licencia para la exhibición de documentos electrónicos avanzada y la API, consulte la sección "eDiscovery" en la guía de licencias de [Microsoft 365](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#ediscovery)para la seguridad y & cumplimiento.

### <a name="microsoft-graph-api-for-teams-export-preview"></a>API de Microsoft Graph para La exportación de Teams (versión preliminar)

El Archivado de información empresarial (EIA) para Microsoft Teams es un escenario clave para nuestros clientes, ya que les permite resolver los requisitos normativos. Además de nuestras capacidades integradas para archivar contenido en Microsoft Teams, los clientes y asociados ahora pueden usar las API de exportación de Teams para resolver escenarios de integración y aplicaciones personalizados. Las API de Exportación de Teams admiten la exportación masiva (hasta 200 solicitudes por segundo/por aplicación/por inquilino) de mensajes y datos adjuntos de mensajes de Teams. La API también puede acceder a los mensajes eliminados hasta 30 días después de eliminarse. Para obtener más información acerca de estas API de exportación de Teams y cómo usarlas en las aplicaciones, vea Exportar contenido con las API de exportación de [Microsoft Teams](/microsoftteams/export-teams-content).

Para obtener información sobre los requisitos de licencia para el uso de las API de exportación de Teams, consulte [Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).