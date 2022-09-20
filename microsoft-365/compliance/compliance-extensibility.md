---
title: Extensibilidad de Microsoft Purview
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
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Obtenga información sobre cómo ampliar las soluciones de Microsoft Purview mediante conectores de datos de terceros y API de Microsoft Graph.
ms.openlocfilehash: 48cae8240e91e553ceb8194a283730b1f4adde50
ms.sourcegitcommit: 433f5b448a0149fcf462996bc5c9b45d17bd46c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2022
ms.locfileid: "67826805"
---
# <a name="microsoft-purview-and-microsoft-priva-extensibility"></a>Extensibilidad de Microsoft Purview y Microsoft Priva

Las soluciones de Microsoft Purview ayudan a las organizaciones a evaluar de forma inteligente sus riesgos de cumplimiento, controlar y proteger los datos confidenciales y responder de forma eficaz a los requisitos normativos. Microsoft Purview es rico en escenarios de extensibilidad y permite a las organizaciones adaptar, ampliar, integrar, acelerar y admitir sus soluciones de cumplimiento.

Hay dos bloques de creación clave para la extensibilidad de cumplimiento:

- **Conectores de datos**. Use para importar y archivar datos que no sean de Microsoft, de modo que pueda aplicar funcionalidades de protección y gobernanza de Microsoft 365 a datos de terceros.

- **API**. Permite el acceso mediante programación a las funcionalidades de Microsoft Purview.

## <a name="data-connectors"></a>Conectores de datos

Microsoft proporciona conectores de datos de terceros que se pueden configurar en el portal de cumplimiento Microsoft Purview. Para obtener una lista de los conectores de datos proporcionados por Microsoft, consulte la tabla [Conectores de datos de terceros](archiving-third-party-data.md#third-party-data-connectors) . La tabla de conectores de datos de terceros también resume las soluciones de cumplimiento que puede aplicar a los datos de terceros después de importar y archivar datos en Microsoft 365, y vínculos a las instrucciones paso a paso para cada conector.

Para más información sobre los conectores de datos de Microsoft Purview, consulte [Archivado de datos de terceros](archiving-third-party-data.md). Si los conectores de datos disponibles en el portal de cumplimiento no admiten un tipo de datos de terceros, puede trabajar con un asociado que pueda proporcionarle un conector personalizado. Para obtener una lista de asociados con los que puede trabajar y el proceso paso a paso para este método, consulte [Trabajo con un asociado para archivar datos de terceros](work-with-partner-to-archive-third-party-data.md).

### <a name="prerequisites-for-data-connectors"></a>Requisitos previos para conectores de datos

Muchos de los conectores de datos disponibles en el portal de cumplimiento para importar y archivar datos de terceros requieren que prepare y realice tareas de configuración en el origen de datos de terceros. Estos requisitos previos se documentan en detalle para cada conector de datos de terceros.

Para los conectores de datos en el portal de cumplimiento proporcionado por uno de los asociados de Microsoft, su organización necesitará una relación empresarial con el asociado antes de poder implementar un conector.

Para obtener instrucciones y requisitos para conectores de datos de terceros, consulte la sección "Conectores de datos" en [Guía de Microsoft 365 para el cumplimiento de & seguridad: Descripciones del servicio | Microsoft Docs](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).

## <a name="apis"></a>API

Microsoft Purview y las API de Microsoft Priva están disponibles en el SDK de Microsoft Information Protection, Microsoft Graph API y la API de actividad de administración de Office 365. Algunas API de cumplimiento forman parte de un nuevo conjunto de API de seguridad y cumplimiento que permiten a los desarrolladores de clientes de Microsoft 365, proveedores de software independientes, integradores de sistemas y proveedores de servicios de seguridad administrados crear soluciones de seguridad y cumplimiento de alto valor.

Para obtener más información sobre cómo acceder a las API de Graph, consulte [Información general de Microsoft Graph](/graph/overview).

### <a name="microsoft-graph-apis-for-subject-rights-requests"></a>API de Microsoft Graph para solicitudes de derechos de sujeto

De acuerdo con ciertas regulaciones de privacidad en todo el mundo, las personas pueden hacer solicitudes para revisar o administrar los datos personales sobre sí mismos que las empresas han recopilado. Estas solicitudes se conocen como *solicitudes de derechos de sujeto* dentro de la solución Solicitudes de datos personales Microsoft Priva. Las solicitudes de derechos del interesado también se conocen como *solicitudes de interesado (* DSR) o *solicitudes de acceso del interesado* (DSAR). Las API de Microsoft Graph para solicitudes de derechos de sujetos permiten a los desarrolladores integrar solicitudes de derechos de sujeto relacionadas con Microsoft 365 con el ecosistema de privacidad más amplio. Esta extensibilidad basada en API permite a las organizaciones responder a las solicitudes de derechos del interesado de forma unificada en todo su patrimonio de datos que abarca tanto los entornos de Microsoft como los que no son de Microsoft. Esta funcionalidad también ayuda a la automatización a escala y ayuda a las organizaciones a cumplir las normativas del sector de forma más eficaz sin depender de procesos manuales.

Para obtener más información, consulte [Api de Microsoft Graph para la solicitud de derechos de sujeto](/graph/api/resources/subjectrightsrequest-subjectrightsrequestapioverview).

### <a name="microsoft-information-protection-mip-sdk"></a>SDK de Microsoft Information Protection (MIP)

El SDK de MIP expone los servicios de etiquetado y protección de los centros de seguridad y cumplimiento de Microsoft 365 a aplicaciones y servicios de terceros. Los desarrolladores pueden usar el SDK para crear compatibilidad nativa para aplicar etiquetas y protección a los archivos. Los desarrolladores pueden determinar qué acciones deben realizarse cuando se detectan etiquetas específicas y razonar sobre la información cifrada por MIP.

Los casos de uso del SDK de MIP de alto nivel incluyen:

- Una aplicación de línea de negocio que aplica etiquetas de clasificación a los archivos de exportación.

- Una aplicación de diseño CAD/CAM que proporciona compatibilidad nativa con las etiquetas de confidencialidad.

- Un agente de seguridad de acceso a la nube o una solución de prevención de pérdida de datos que puede cifrar los datos con Azure Information Protection.

Para más información sobre el SDK de MIP, los requisitos previos, escenarios adicionales y ejemplos, consulte [Información general sobre el SDK de MIP](/information-protection/develop/overview).

### <a name="microsoft-graph-api-for-teams-dlp"></a>DLP de Microsoft Graph API para Teams

Las funcionalidades de [prevención de pérdida de datos (DLP)](dlp-microsoft-teams.md) se usan ampliamente en Microsoft Teams, especialmente cuando las organizaciones se han desplazado al trabajo remoto. Recientemente [anunciamos la disponibilidad general](https://devblogs.microsoft.com/microsoft365dev/change-notifications-for-microsoft-teams-messages-now-generally-available/) de la API de notificación de cambios de Microsoft Graph para los mensajes en Teams. Esta API permite a los desarrolladores crear aplicaciones que puedan escuchar mensajes de Microsoft Teams casi en tiempo real y, a continuación, implementar escenarios DLP para clientes y asociados. Además, La API de revisión de Microsoft Graph le permite aplicar acciones DLP a los mensajes de Teams.

Estas dos API forman el Graph API de Microsoft para DLP de Teams. Para empezar, pruebe la [aplicación de ejemplo](https://github.com/microsoftgraph/aspnetcore-webhooks-sample). Para obtener más información sobre los webhooks de mensajería de Microsoft Teams, consulte la [documentación](/graph/api/subscription-post-subscriptions).

Para conocer los requisitos de licencia para DLP de Teams, consulte [Guía de licencias de Microsoft 365 para el cumplimiento de & seguridad](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).

### <a name="microsoft-graph-api-for-ediscovery-preview"></a>Microsoft Graph API para eDiscovery (versión preliminar)

Con [eDiscovery (Premium),](overview-ediscovery-20.md) las organizaciones pueden detectar datos donde se encuentran y administrar más flujos de trabajo de eDiscovery de un extremo a otro con funcionalidades inteligentes de aprendizaje automático y análisis para reducir los datos al conjunto pertinente, todo ello mientras los datos permanecen dentro del límite de seguridad y cumplimiento de Microsoft 365.

Las API de Graph para eDiscovery (Premium) se pueden usar para crear y administrar casos, revisar conjuntos y revisar consultas de conjuntos de forma escalable y repetible. Esto permite a los clientes y asociados crear aplicaciones y flujos de trabajo para automatizar procesos comunes y repetitivos, como la creación de casos y la administración de custodios y retenciones legales.

El primer conjunto de API de Graph para eDiscovery está disponible en versión preliminar pública. Tenemos previsto agregar más funcionalidades para el final del año natural. Para obtener más información sobre estas API y otras actualizaciones de eDiscovery (Premium), consulte este [blog](https://aka.ms/Ignite2020AeDAA).

Para conocer los requisitos de licencia de eDiscovery (Premium) y la API, consulte la sección "eDiscovery" en la [guía de licencias de Microsoft 365 para el cumplimiento de & de seguridad](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#ediscovery).

### <a name="microsoft-graph-api-for-teams-export"></a>Exportación de Microsoft Graph API para Teams

El archivado de información empresarial (EIA) para Microsoft Teams es un escenario clave para nuestros clientes, ya que les permite resolver los requisitos normativos. Además de nuestras funcionalidades integradas para archivar contenido en Microsoft Teams, los clientes y asociados ahora pueden usar las API de exportación de Teams para resolver escenarios de integración y aplicaciones personalizados. Las API de exportación de Teams admiten la exportación masiva (hasta 200 solicitudes por segundo/por aplicación/por inquilino) de mensajes y datos adjuntos de mensajes de Teams. La API también puede acceder a los mensajes eliminados durante un máximo de 30 días después de su eliminación. Para obtener más información sobre estas API de exportación de Teams y cómo usarlas en las aplicaciones, consulte [Exportación de contenido con las API de exportación de Microsoft Teams](/microsoftteams/export-teams-content).

Para conocer los requisitos de licencias para el uso de las API de exportación de Teams, consulte [Guía de licencias de Microsoft 365 para obtener seguridad & cumplimiento](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).

### <a name="microsoft-graph-connector-apis-preview"></a>API del conector de Microsoft Graph (versión preliminar)

Con [los conectores de Microsoft Graph, las organizaciones](/microsoftsearch/connectors-overview) pueden indexar datos de terceros para que aparezcan en los resultados de Búsqueda de Microsoft. Esta característica expande los tipos de orígenes de contenido que se pueden buscar en las aplicaciones de productividad de Microsoft 365 y del ecosistema más amplio de Microsoft. Los datos de terceros se pueden hospedar de forma local o en nubes públicas o privadas. A partir de eDiscovery (Premium), estamos habilitando la versión preliminar para desarrolladores del valor de cumplimiento integrado de las aplicaciones conectadas a Microsoft 365. Esto permite el cumplimiento de las aplicaciones que se integran en el ecosistema de Microsoft 365 para capacitar a los usuarios con experiencias de cumplimiento sin problemas. Para obtener más información sobre cómo incorporar las API del conector de Microsoft Graph en la vista de aplicaciones, consulte [Creación, actualización y eliminación de conexiones en Microsoft Graph](/graph/connecting-external-content-connectors-api-overview).

### <a name="microsoft-graph-api-for-records-management-preview"></a>API de Microsoft Graph para la administración de registros (versión preliminar)

Las organizaciones de todos los tipos requieren una solución de administración de registros para administrar registros críticos en sus datos. [Administración de registros de Microsoft Purview](records-management.md) ayuda a una organización a administrar sus obligaciones legales, proporciona la capacidad de demostrar el cumplimiento de las regulaciones y aumenta la eficacia con la eliminación regular de los elementos que ya no son necesarios.

Las organizaciones de grandes volúmenes usan la solución de administración de registros para usar sus diversas funcionalidades para proteger, etiquetar, conservar o eliminar sus datos. Las API de Microsoft Graph para la administración de registros permiten a las organizaciones administrar las etiquetas de retención y sus acciones asociadas de forma más eficaz, automatizar tareas repetitivas y dotar a los clientes de flexibilidad en las opciones.

Ahora, la primera versión de graph API para la administración de registros admite la administración de etiquetas de retención y la retención basada en eventos. Escenarios de ejemplo:

- **Administración de etiquetas de retención**
    
    Los administradores y desarrolladores de administración de registros deben mantener sus sistemas de administración de registros con etiquetas que se crean, actualizan y eliminan periódicamente.
    
    Los desarrolladores y administradores de cumplimiento usan las API de Graph para la administración de registros con el fin de realizar operaciones CRUD en la entidad de etiqueta para mantener sus sistemas.

- **Desencadenamiento de un evento para una etiqueta existente**
    
    Cuando un empleado deja una organización, la información se actualiza en el sistema de administración de RR. HH. A partir de la fecha de salida, los documentos confidenciales deben conservarse durante siete años. Estos documentos ya tienen aplicada la etiqueta de retención "Employee_departure".
    
    Los desarrolladores y administradores de cumplimiento usan las API de Graph para la administración de registros para leer la etiqueta "Employee_departure" y buscar el tipo de evento asociado "Event-employee_departure".
    
    A continuación, usan las API de Graph para la administración de registros para crear un evento para el tipo de evento asociado. El período de retención de los documentos confidenciales comienza después de crear este evento.

Para obtener más información sobre las API de Graph para la administración de registros, consulte [Uso de la API de administración de registros de Microsoft Graph](/graph/api/resources/security-recordsmanagement-overview?view=graph-rest-beta&preserve-view=true).

Para conocer los requisitos de licencia para usar estas API, consulte la información de administración de registros de la guía de Microsoft 365 para el cumplimiento de la seguridad &, [Administración del ciclo de vida de Microsoft Purview & Administración de registros de Microsoft Purview ](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#microsoft-purview-data-lifecycle-management--microsoft-purview-records-management) Sección.
