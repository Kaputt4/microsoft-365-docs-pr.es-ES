---
title: Microsoft 365 extensibilidad de cumplimiento normativo
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
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Obtenga información sobre cómo ampliar Microsoft 365 de cumplimiento normativo mediante conectores de datos de terceros y API Graph Microsoft.
ms.openlocfilehash: 1127064394e5b4873adb046e2b0540b361064c9d
ms.sourcegitcommit: 355ab75eb7b604c6afbe9a5a1b97ef16a1dec4fc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2022
ms.locfileid: "62806845"
---
# <a name="microsoft-365-compliance-and-microsoft-priva-extensibility"></a>Microsoft 365 cumplimiento normativo y extensibilidad de Microsoft Priva

Microsoft 365 soluciones de cumplimiento ayudan a las organizaciones a evaluar inteligentemente sus riesgos de cumplimiento, a controlar y proteger datos confidenciales y a responder eficazmente a los requisitos normativos. Microsoft 365 cumplimiento es rico en escenarios de extensibilidad y permite a las organizaciones adaptar, ampliar, integrar, acelerar y admitir sus soluciones de cumplimiento.

Hay dos bloques de creación clave para la extensibilidad de cumplimiento:

- **Conectores de datos**. Se usa para importar y archivar datos que no son de Microsoft para que pueda aplicar Microsoft 365 de protección y gobierno a datos de terceros.

- **API**. Permite el acceso mediante programación a Microsoft 365 de cumplimiento normativo.

## <a name="data-connectors"></a>Conectores de datos

Microsoft proporciona conectores de datos de terceros que se pueden configurar en el Centro de cumplimiento de Microsoft 365. Para obtener una lista de conectores de datos proporcionados por Microsoft, consulte la [tabla Conectores](archiving-third-party-data.md#third-party-data-connectors) de datos de terceros. La tabla de conectores de datos de terceros también resume las soluciones de cumplimiento que puede aplicar a datos de terceros después de importar y archivar datos en Microsoft 365 y vínculos a las instrucciones paso a paso para cada conector.

Para obtener más información Microsoft 365 conectores de datos, consulte [Archivado de datos de terceros](archiving-third-party-data.md). Si un tipo de datos de terceros no es compatible con los conectores de datos disponibles en el Centro de cumplimiento de Microsoft 365, puede trabajar con un partner que pueda proporcionarle un conector personalizado. Para obtener una lista de partners con los que puede trabajar y el proceso paso a paso para este método, vea Trabajar con un partner para archivar datos [de terceros](work-with-partner-to-archive-third-party-data.md).

### <a name="prerequisites-for-data-connectors"></a>Requisitos previos para conectores de datos

Muchos de los conectores de datos disponibles en el Centro de cumplimiento de Microsoft 365 para importar y archivar datos de terceros requieren que prepare y realice tareas de configuración en el origen de datos de terceros. Estos requisitos previos se documentan detalladamente para cada conector de datos de terceros.

Para los conectores de datos en el Centro de cumplimiento de Microsoft 365 proporcionado por uno de los partners de Microsoft, su organización necesitará una relación comercial con el partner antes de poder implementar un conector.

Para obtener información sobre los requisitos de licencias para conectores de datos [de terceros](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance), consulte la sección "Conectores de datos" en Microsoft 365 de licencias para el cumplimiento de & seguridad.

## <a name="apis"></a>API

Microsoft 365 cumplimiento normativo y las API de Microsoft Priva están disponibles en el SDK de Microsoft Information Protection, la API de Microsoft Graph y la API Office 365 actividad de administración. Algunas API de cumplimiento forman parte de un nuevo conjunto de API de seguridad y cumplimiento que permiten a los desarrolladores de clientes de Microsoft 365, proveedores de software independientes, integradores de sistemas y proveedores de servicios de seguridad administrados crear soluciones de seguridad y cumplimiento de alto valor.

Para obtener más información sobre cómo obtener acceso a Graph API, consulte [Overview of Microsoft Graph](/graph/overview).

### <a name="microsoft-graph-apis-for-subject-rights-requests"></a>API Graph Microsoft para solicitudes de derechos de sujeto

De acuerdo con ciertas normativas de privacidad de todo el mundo, los individuos pueden realizar solicitudes para revisar o administrar los datos personales sobre sí mismos que las empresas han recopilado. Estas solicitudes se denominan *solicitudes de* derechos de sujeto dentro de la solución Solicitudes de derechos del sujeto de Microsoft Priva. Las solicitudes de derechos del sujeto también se conocen como solicitudes de *interesados* (DSR) o solicitudes de acceso del *interesado (* DSARs). Las API Graph microsoft para solicitudes de derechos de sujeto permiten a los desarrolladores integrar Microsoft 365 de derechos de sujeto relacionados con el ecosistema de privacidad más amplio. Esta extensibilidad basada en API permite a las organizaciones responder a solicitudes de derechos de sujeto de forma unificada en toda su propiedad de datos que abarca entornos de Microsoft y no de Microsoft. Esta funcionalidad también ayuda con la automatización a escala y ayuda a las organizaciones a cumplir las normativas del sector de forma más eficaz sin depender de procesos manuales.

Para obtener más información, vea [Microsoft Graph API para la solicitud de derechos de sujeto](/graph/api/resources/subjectrightsrequest-subjectrightsrequestapioverview).

### <a name="microsoft-information-protection-mip-sdk"></a>MICROSOFT INFORMATION PROTECTION SDK de Microsoft Information Protection (MIP)

El SDK de MIP expone los servicios de etiquetado y protección de Microsoft 365 de seguridad y cumplimiento a servicios y aplicaciones de terceros. Los desarrolladores pueden usar el SDK para crear compatibilidad nativa para aplicar etiquetas y protección a los archivos. Los desarrolladores pueden determinar qué acciones deben realizarse cuando se detectan etiquetas específicas y la razón sobre la información cifrada por MIP.

Los casos de uso de SDK de MIP de alto nivel incluyen:

- Una aplicación de línea de negocio que aplica etiquetas de clasificación a los archivos que se exportan.

- Una aplicación de diseño CAD/CAM que proporciona compatibilidad nativa con el etiquetado MIP.

- Un agente de seguridad de acceso a la nube o una solución de prevención de pérdida de datos que puede cifrar datos con Azure Information Protection.

Para obtener más información sobre el SDK de MIP, los requisitos previos, los escenarios adicionales y los ejemplos, consulte [Introducción al SDK de MIP](/information-protection/develop/overview).

### <a name="microsoft-graph-api-for-teams-dlp"></a>API Graph Microsoft para dlp Teams dlp

[Las capacidades de](dlp-microsoft-teams.md) prevención de pérdida de datos (DLP) se usan ampliamente en Microsoft Teams especialmente a medida que las organizaciones se han desplazado al trabajo remoto. Recientemente [anunciamos la disponibilidad general de](https://devblogs.microsoft.com/microsoft365dev/change-notifications-for-microsoft-teams-messages-now-generally-available/) la API de notificaciones de cambios de Microsoft Graph para los mensajes de Teams. Esta API permite a los desarrolladores crear aplicaciones que puedan escuchar Microsoft Teams mensajes en tiempo casi real y, a continuación, implementar escenarios dlp para clientes y partners. Además, la API de revisión Graph Microsoft le permite aplicar acciones DLP a Teams mensajes.

Estas dos API forman la API de Microsoft Graph para Teams DLP. Puedes empezar probando la aplicación [de ejemplo](https://github.com/microsoftgraph/aspnetcore-webhooks-sample). Para obtener más información Microsoft Teams webhooks de mensajería, consulte la [documentación](/graph/api/subscription-post-subscriptions).

Para obtener información sobre los requisitos de licencia Teams DLP, [consulte Microsoft 365 guía de licencias para el cumplimiento de & seguridad](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).

### <a name="microsoft-graph-api-for-ediscovery-preview"></a>API Graph Microsoft para exhibición de documentos electrónicos (versión preliminar)

Con [Advanced eDiscovery](overview-ediscovery-20.md), las organizaciones pueden descubrir los datos donde viven y administrar más flujos de trabajo de exhibición de documentos electrónicos de extremo a extremo con capacidades inteligentes de aprendizaje automático y análisis para reducir los datos al conjunto pertinente, todo mientras los datos permanecen dentro del límite de seguridad y cumplimiento de Microsoft 365.

Graph API de Advanced eDiscovery pueden usarse para crear y administrar casos, conjuntos de revisión y consultas de conjunto de revisión de forma escalable y repetible. Esto permite a los clientes y partners crear aplicaciones y flujos de trabajo para automatizar procesos comunes y repetitivos, como crear casos y administrar custodias y retenciones legales.

El primer conjunto de API Graph para eDiscovery están disponibles en versión preliminar pública. Planeamos agregar más funcionalidades al final del año calendario. Para obtener más información sobre estas API y otras actualizaciones para Advanced eDiscovery, vea este [blog](https://aka.ms/Ignite2020AeDAA).

Para obtener información sobre los requisitos de Advanced eDiscovery y la API, consulte la sección "eDiscovery" en la guía de licencias de Microsoft 365 para el cumplimiento de & [seguridad](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#ediscovery).

### <a name="microsoft-graph-api-for-teams-export"></a>API Graph Microsoft para Teams Export

Enterprise information archiving (EIA) para Microsoft Teams es un escenario clave para nuestros clientes, ya que les permite resolver los requisitos normativos. Además de nuestras capacidades integradas para archivar contenido en Microsoft Teams, los clientes y asociados ahora pueden usar las API de exportación de Teams para resolver escenarios de integración y aplicaciones personalizados. Las API Teams Export admiten la exportación masiva (hasta 200 solicitudes por segundo/por aplicación/por inquilino) de mensajes Teams y datos adjuntos de mensajes. La API también puede acceder a los mensajes eliminados hasta 30 días después de eliminarse. Para obtener más información acerca de estas Teams Exportar API y cómo usarlas en las aplicaciones, vea [Export content with the Microsoft Teams Export API](/microsoftteams/export-teams-content).

Para obtener información sobre los requisitos de licencia para el uso de las API de exportación Teams, consulte Microsoft 365 de licencias para el cumplimiento de & [seguridad](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).

### <a name="microsoft-graph-connector-apis-preview"></a>API de Microsoft Graph Connector (versión preliminar)

Con [los conectores Graph Microsoft](/microsoftsearch/connectors-overview), las organizaciones pueden indizar datos de terceros para que aparezcan en Búsqueda de Microsoft resultados. Esta característica expande los tipos de orígenes de contenido que se pueden buscar en las aplicaciones de productividad de Microsoft 365 y del ecosistema más amplio de Microsoft. Los datos de terceros se pueden hospedar localmente o en nubes públicas o privadas. A partir Advanced eDiscovery, estamos habilitando la vista previa del desarrollador del valor de cumplimiento integrado de Microsoft 365 aplicaciones conectadas. Esto permite el cumplimiento de aplicaciones que se integran en el Microsoft 365 para habilitar a los usuarios con experiencias de cumplimiento sin problemas. Para obtener más información sobre cómo incorporar las API de Microsoft Graph Connector en la vista aplicaciones, vea [Crear,](/graph/connecting-external-content-connectors-api-overview) actualizar y eliminar conexiones en microsoft Graph.
