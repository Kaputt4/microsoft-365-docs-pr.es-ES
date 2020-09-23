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
description: Obtenga información sobre cómo extender las soluciones de cumplimiento de Microsoft 365 mediante conectores de datos de terceros y API de Microsoft Graph.
ms.openlocfilehash: 284125db8243b10f5c8de7e0a37c1b7284709c28
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "48204515"
---
# <a name="microsoft-365-compliance-extensibility"></a>Extensibilidad de cumplimiento de Microsoft 365

Las soluciones de cumplimiento de Microsoft 365 ayudan a las organizaciones a evaluar de manera inteligente sus riesgos de cumplimiento, controlar y proteger los datos confidenciales y responder de manera eficaz a los requisitos normativos. El cumplimiento de Microsoft 365 es rico en escenarios de extensibilidad y permite a las organizaciones adaptar, ampliar, integrar, acelerar y admitir sus soluciones de cumplimiento.

Hay dos bloques de creación clave para la extensibilidad del cumplimiento:

- **Conectores de datos**. Use para importar y archivar datos que no son de Microsoft para poder aplicar las funciones de administración y protección de Microsoft 365 a datos de terceros.

- Las **API**. Permite el acceso mediante programación a las capacidades de cumplimiento de Microsoft 365.

## <a name="data-connectors"></a>Conectores de datos

Microsoft proporciona conectores de datos de terceros que se pueden configurar en el centro de cumplimiento de Microsoft 365. Para obtener una lista de los conectores de datos proporcionados por Microsoft, consulte la tabla [conectores de datos de terceros](archiving-third-party-data.md#third-party-data-connectors) . La tabla de conectores de datos de terceros también resume las soluciones de cumplimiento que se pueden aplicar a los datos de terceros después de importar y archivar datos en Microsoft 365 y vínculos a las instrucciones paso a paso para cada conector.

Para obtener más información acerca de los conectores de datos de Microsoft 365, consulte [archivado de datos de terceros](archiving-third-party-data.md). Si un tipo de datos de terceros no es compatible con los conectores de datos disponibles en el centro de cumplimiento de Microsoft 365, puede trabajar con un socio que pueda proporcionarle un conector personalizado. Para obtener una lista de los socios con los que puede trabajar y el proceso paso a paso para este método, vea [trabajar con un partner para archivar datos de terceros](work-with-partner-to-archive-third-party-data.md).

### <a name="prerequisites-for-data-connectors"></a>Requisitos previos para los conectores de datos

Muchos de los conectores de datos disponibles en el centro de cumplimiento de Microsoft 365 para importar y archivar datos de terceros requieren que prepare y realice tareas de configuración en el origen de datos de terceros. Estos requisitos previos se documentan en detalle para cada conector de datos de terceros.

Para los conectores de datos del centro de cumplimiento de Microsoft 365 proporcionado por uno de los socios de Microsoft, la organización necesitará una relación comercial con el partner para poder implementar un conector.

Puede encontrar los requisitos de licencia para los conectores de datos de terceros en el documento de [comparación de licencias de cumplimiento de Microsoft 365](https://docs.microsoft.com/office365/servicedescriptions/downloads/microsoft-365-compliance-licensing-comparison.xlsx) .

## <a name="apis"></a>API

Las API de cumplimiento de Microsoft 365 están disponibles en el SDK de Microsoft Information Protection, la API de Microsoft Graph y la API de actividad de administración de Office 365. Algunas API de cumplimiento forman parte de un nuevo conjunto de API de seguridad y cumplimiento que permiten a los desarrolladores de Microsoft 365 clientes, proveedores de software independientes, integradores de sistemas y proveedores de servicios de seguridad administrados crear soluciones de seguridad y cumplimiento de alto valor.

Para obtener más información sobre cómo acceder a las API de Graph, vea [información general de Microsoft Graph](https://docs.microsoft.com/graph/overview).

### <a name="microsoft-information-protection-mip-sdk"></a>SDK de Microsoft Information Protection (MIP)

El SDK de MIP expone los servicios de etiquetado y protección de los centros de seguridad y cumplimiento de Microsoft 365 a aplicaciones y servicios de terceros. Los desarrolladores pueden usar el SDK para crear compatibilidad nativa para aplicar etiquetas y protección a los archivos. Los desarrolladores pueden determinar las acciones que se deben llevar a cabo cuando se detectan etiquetas específicas y la razón sobre la información cifrada de MIP.

Los casos de uso del SDK de MIP de alto nivel incluyen:

- Una aplicación de línea de negocio que aplica Etiquetas de clasificación a los archivos en la exportación.

- Una aplicación de diseño CAD/CAM que proporciona compatibilidad nativa con la etiquetación MIP.

- Una solución de agente de seguridad de acceso a la nube o prevención de pérdida de datos que pueda cifrar datos con Azure Information Protection.

Para obtener más información sobre el SDK de MIP, los requisitos previos, los escenarios adicionales y los ejemplos, vea [información general del SDK de MIP](https://docs.microsoft.com/information-protection/develop/overview).

### <a name="microsoft-graph-api-for-teams-dlp"></a>API de Microsoft Graph para DLP de Teams

Las capacidades de [prevención de pérdida de datos (DLP)](dlp-microsoft-teams.md) se usan ampliamente en Microsoft Teams, especialmente cuando las organizaciones se han desplazado al trabajo remoto. Al principio de este año, [anunciamos la versión preliminar pública](https://developer.microsoft.com/graph/blogs/announcing-change-notifications-for-microsoft-teams-messages/) de la API de notificación de cambios de Microsoft Graph para los mensajes en Teams. Esta API permite a los programadores crear aplicaciones que puedan escuchar los mensajes de Microsoft Teams en tiempo casi real y, a continuación, implementar escenarios de DLP para clientes y socios. Además, la API de revisión de Microsoft Graph le permite aplicar acciones de DLP a los mensajes de Microsoft Teams.

Estas dos API forman la API de Microsoft Graph para la DLP de Teams. Puede empezar por probar la [aplicación de muestra](https://github.com/microsoftgraph/csharp-webhook-with-resource-data). Para obtener más información acerca de los webhooks de mensajería de Microsoft Teams, vea la [documentación](https://docs.microsoft.com/graph/api/subscription-post-subscriptions)de.

Para obtener información sobre los requisitos de licencia para DLP de Teams, consulte [Microsoft 365 Licensing Guidance for security & Compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#office-365-data-loss-prevention-for-exchange-online-sharepoint-online-and-onedrive-for-business).

### <a name="microsoft-graph-api-for-ediscovery-preview"></a>API de Microsoft Graph para eDiscovery (versión preliminar)

Con la [exhibición avanzada](overview-ediscovery-20.md)de documentos electrónicos, las organizaciones pueden descubrir datos en los que residen y administrar más flujos de trabajo de eDiscovery de un extremo a otro con capacidades de análisis y aprendizaje de máquina inteligentes para reducir los datos al conjunto pertinente, todo mientras los datos permanecen dentro del límite de seguridad y cumplimiento de Microsoft 365.

Las API de Graph para la exhibición avanzada de documentos electrónicos se pueden usar para crear y administrar casos, revisar conjuntos y revisar conjuntos de consultas de manera escalable y repetible. Esto permite a los clientes y socios crear aplicaciones y flujos de trabajo para automatizar procesos comunes y repetitivos, como crear casos y administrar custodios y retenciones legales.

El primer conjunto de API de Graph para eDiscovery está disponible en la versión preliminar pública. Tenemos previsto agregar más capacidades antes de que finalice el año natural. Para obtener más información sobre estas API y otras actualizaciones para la exhibición avanzada de documentos electrónicos, vea este [blog](https://aka.ms/Ignite2020AeDAA).

Para obtener información sobre los requisitos de licencia para la exhibición avanzada de documentos electrónicos y la API, consulte la sección "exhibición de documentos electrónicos" en [Guía de licencias de 365 de seguridad para cumplimiento de &](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#ediscovery).

### <a name="microsoft-graph-api-for-teams-export-preview"></a>Exportación de la API de Microsoft Graph para Microsoft Teams (versión preliminar)

El archivo de información empresarial (EIA) para Microsoft Teams es un escenario clave para los clientes, ya que les permite resolver los requisitos normativos. Además de nuestras capacidades integradas para archivar contenido en Microsoft Teams, los clientes y socios ahora pueden usar las API de exportación de Microsoft Teams para solucionar los escenarios de integración y aplicaciones personalizadas. Las API de exportación de Microsoft Teams admiten la exportación en masa (hasta 200 solicitudes por segundo/por aplicación/por inquilino) de mensajes de Microsoft Teams y datos adjuntos de mensajes. La API también puede tener acceso a los mensajes eliminados durante un máximo de 30 días después de su eliminación. Para obtener más información sobre estas API de exportación de equipos y cómo usarlas en sus aplicaciones, vea [exportar contenido con las API de exportación de Microsoft Teams](https://docs.microsoft.com/microsoftteams/export-teams-content).

Para conocer los requisitos de licencia para el uso de las API de exportación de Teams, vea [Microsoft 365 Licensing Guidance for security & Compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).
