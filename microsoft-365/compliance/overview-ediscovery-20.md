---
title: Introducción a la solución eDiscovery (Premium) en Microsoft Purview
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
ms.date: 07/08/2022
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- m365-security-compliance
- m365solution-aed
- m365initiative-compliance
- m365solution-overview
search.appverid:
- MOE150
- MET150
description: Obtenga información sobre la solución eDiscovery (Premium) en Microsoft Purview. En este artículo se proporciona información general sobre eDiscovery (Premium) en Microsoft Purview, una herramienta que le ayudará a administrar investigaciones internas y externas. También se enmarcan los motivos empresariales para usar eDiscovery (Premium) para administrar las investigaciones legales.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7f6841412402761d5eeb34162269bd659582e5e8
ms.sourcegitcommit: 078149c9645ce220911ccd6ce54f984a4c92ce53
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2022
ms.locfileid: "67809625"
---
# <a name="overview-of-microsoft-purview-ediscovery-premium"></a>Información general de Microsoft Purview eDiscovery (Premium)

La solución Microsoft Purview eDiscovery (Premium) se basa en las funcionalidades existentes de Microsoft eDiscovery y análisis. eDiscovery (Premium) proporciona un flujo de trabajo de un extremo a otro para conservar, recopilar, analizar, revisar y exportar contenido que responda a las investigaciones internas y externas de la organización. También permite al equipo legal gestionar todo el flujo de trabajo de notificación de retención legal para comunicarse con los administradores de un caso.

## <a name="ediscovery-premium-capabilities"></a>Funcionalidades de eDiscovery (Premium)

eDiscovery (Premium) puede ayudar a su organización a responder a asuntos legales o investigaciones internas mediante la detección de datos donde reside. Puede administrar sin problemas los flujos de trabajo de eDiscovery mediante la identificación de personas de interés y sus orígenes de datos, aplicar retenciones sin problemas para conservar los datos y, a continuación, administrar el proceso de comunicación de suspensión legal. Al recopilar datos del origen, puede buscar en la plataforma de Microsoft 365 en directo para encontrar rápidamente lo que necesita. Las funcionalidades inteligentes de aprendizaje automático, como la indexación profunda, el subproceso de correo electrónico y la detección casi duplicada, también le ayudan a reducir grandes volúmenes de datos a un conjunto de datos pertinente.

En las secciones siguientes se describe cómo estas funcionalidades de eDiscovery (Premium) pueden ayudar a su organización.

![Funcionalidades de eDiscovery (Premium).](../media/advanced-ediscovery-capabilities.png)

### <a name="discover-and-collect-data-in-place"></a>Detección y recopilación de datos locales

Tradicionalmente, las organizaciones que dependen de varias soluciones de exhibición de documentos electrónicos de terceros requieren copiar grandes volúmenes de datos de Microsoft 365 para procesar y tener que hospedar datos duplicados. Esta necesidad aumenta el tiempo para encontrar datos pertinentes y el riesgo, el costo y la complejidad de la administración de varias soluciones.

eDiscovery (Premium) en Microsoft 365 le permite detectar datos en el origen y permanecer dentro del límite de seguridad y cumplimiento de Microsoft 365.  Mediante la recopilación de datos en contexto del sistema en directo, eDiscovery (Premium) reduce la fricción de volver al origen y reduce el trabajo innecesario de tener que encontrar contenido que falta, lo que a menudo ocurre cuando el registro en diario se retrasa en las soluciones de eDiscovery tradicionales.

Las funcionalidades nativas de búsqueda y recopilación de datos en Teams, Yammer, SharePoint Online, OneDrive para la Empresa y Exchange Online mejoran aún más la detección de datos. Por ejemplo, eDiscovery (Premium):

- Reconstruye las conversaciones de Teams (en lugar de devolver mensajes individuales de las conversaciones).

- Recopila contenido basado en la nube compartido con los usuarios mediante vínculos o datos adjuntos modernos en mensajes de correo electrónico y chats de Teams.

- Tiene compatibilidad integrada con cientos de tipos de archivo que no son de Microsoft 365.

- Recopila datos de orígenes de terceros (como Bloomberg, Facebook, Slack y Zoom Meetings) importados y archivados en Microsoft 365 por [conectores de datos](archiving-third-party-data.md).

### <a name="manage-ediscovery-workflow-in-one-platform"></a>Administración del flujo de trabajo de eDiscovery en una plataforma

eDiscovery (Premium) puede ayudarle a reducir el número de soluciones de exhibición de documentos electrónicos en las que debe confiar. Proporciona un flujo de trabajo simplificado de un extremo a otro, todo lo que ocurre en Microsoft 365. eDiscovery (Premium) ayuda a reducir la fricción de la identificación y recopilación de posibles orígenes de información pertinente mediante la asignación automática de orígenes de datos únicos y compartidos a la persona de interés (conocido como *custodio*), y proporcionando informes y análisis sobre datos potencialmente relevantes antes de recopilarlos para su análisis y revisión.

Además, las API de Microsoft Graph pueden ayudarle a automatizar el flujo de trabajo de eDiscovery y ampliar eDiscovery (Premium) para soluciones personalizadas.

### <a name="cull-data-intelligently"></a>Eliminación de datos de forma inteligente

Las funcionalidades inteligentes de aprendizaje automático en eDiscovery (Premium) ayudan a reducir la cantidad de datos que se van a revisar. Estas funcionalidades inteligentes le ayudan a reducir y seleccionar grandes volúmenes de datos en un conjunto pertinente. Por ejemplo, una consulta de conjunto de revisión integrada ayuda a filtrar solo por contenido único mediante la identificación de duplicados cercanos. Esta funcionalidad puede reducir considerablemente la cantidad de datos que se van a revisar.

Las funcionalidades adicionales de aprendizaje automático pueden refinar e identificar aún más los datos pertinentes mediante etiquetas inteligentes y herramientas de revisión asistida por tecnología, como los módulos de relevancia.

## <a name="ediscovery-premium-alignment-with-the-electronic-discovery-reference-model"></a>Alineación de eDiscovery (Premium) con el modelo de referencia de detección electrónica

El flujo de trabajo integrado de eDiscovery (Premium) en Microsoft 365 se alinea con el proceso de eDiscovery descrito por el modelo de referencia de detección electrónica (EDRM).

![Modelo de referencia de detección electrónica (EDRM).](../media/EDRMv2.png)

(Imagen basada en el modelo EDRM en edrm.net)

En un nivel alto, aquí se muestra cómo eDiscovery (Premium) admite el flujo de trabajo de EDRM:

- **Identificación.** Después de identificar a los posibles interesados en una investigación, puede agregarlos como custodios (también *denominados custodios de datos*, ya que pueden poseer información relevante para la investigación) a un caso de eDiscovery (Premium). Una vez añadidos los usuarios como custodios, es fácil conservar, recopilar y revisar los documentos de los custodios.

- **Preservación.** Para conservar y proteger los datos que son relevantes para una investigación, eDiscovery (Premium) permite colocar una suspensión legal en los orígenes de datos asociados a los custodios en un caso. También puede poner en espera los datos no custodiados. eDiscovery (Premium) también tiene un flujo de trabajo de comunicaciones integrado para que pueda enviar notificaciones de suspensión legal a los custodios y realizar un seguimiento de sus confirmaciones.

- **Colección.** Después de identificar (y conservar) los orígenes de datos pertinentes para la investigación, puede usar la herramienta de búsqueda integrada en eDiscovery (Premium) para buscar y recopilar datos activos de los orígenes de datos de custodia (y orígenes de datos que no son de custodia, si procede) que pueden ser pertinentes para el caso.

- **Tratamiento.** Una vez recopilados todos los datos relevantes para el caso, el siguiente paso es procesarlos para su posterior revisión y análisis. En eDiscovery (Premium), los datos locales que identificó en la fase de recopilación se copian en una ubicación de Azure Storage (denominada *conjunto de revisión*), lo que proporciona una vista estática de los datos del caso.

- **Revisión.** Una vez agregados los datos a un conjunto de revisión, puede ver documentos específicos y ejecutar consultas adicionales para reducir los datos a lo más relevante para el caso. Además, puede anotar y etiquetar documentos específicos.

- **Análisis.** eDiscovery (Premium) proporciona una herramienta de análisis integrada que le ayuda a seleccionar más datos del conjunto de revisión que determine que no son relevantes para la investigación. Además de reducir el volumen de datos relevantes, eDiscovery avanzado también le ayuda a ahorrar costes de revisión legal al permitirle organizar el contenido para que el proceso de revisión sea más fácil y eficiente.

- **Producción** y **presentación.** Cuando esté listo, puede exportar los documentos de un conjunto de revisión para su revisión legal. Puede exportar los documentos en su formato nativo o en un formato especificado por EDRM para poder importarlos en aplicaciones de revisión de terceros.

## <a name="subscriptions-and-licensing"></a>Suscripciones y licencias

Para obtener información sobre qué licencias proporcionan los derechos para que un usuario se beneficie de eDiscovery (Premium), consulte [guía de Microsoft 365 para el cumplimiento de & de seguridad](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#microsoft-purview-ediscovery) y vea la sección "eDiscovery and auditing" en la [tabla Comparación de Microsoft 365](https://go.microsoft.com/fwlink/?linkid=2139145).

Para obtener información sobre cómo asignar licencias, consulte [Asignación de licencias a usuarios](/microsoft-365/admin/manage/assign-licenses-to-users).

## <a name="get-started-with-ediscovery-premium"></a>Introducción a eDiscovery (Premium)

Hay dos pasos rápidos y sencillos para empezar a trabajar con eDiscovery (Premium).

![Introducción al flujo de trabajo con eDiscovery (Premium).](../media/get-started-AeD.png)

|Pasos  |Descripción  |
|:---------|:---------|
|[Configurar eDiscovery (Premium)](get-started-with-advanced-ediscovery.md)| Después de comprobar los requisitos de suscripción y licencia, puede asignar permisos y configurar la configuración de toda la organización para empezar a usar eDiscovery (Premium).|
|[Creación y administración de casos](create-and-manage-advanced-ediscoveryv2-case.md) | Cree casos para administrar el flujo de trabajo de eDiscovery (Premium) para todos los tipos legales y otros tipos de investigaciones de su organización.|
|||

## <a name="ediscovery-premium-architecture"></a>Arquitectura de eDiscovery (Premium)

Este es un diagrama de arquitectura de eDiscovery (Premium) que muestra el flujo de trabajo de un extremo a otro en un entorno de una sola ubicación geográfica y en un entorno multigeográfico, y el flujo de datos de un extremo a otro que está alineado con [EDRM](#ediscovery-premium-alignment-with-the-electronic-discovery-reference-model).

[![Póster del modelo: Arquitectura de eDiscovery (Premium) en Microsoft 365.](../media/solutions-architecture-center/ediscovery-poster-thumb.png)](../media/solutions-architecture-center/m365-advanced-ediscovery-architecture.png)

[Visualización como imagen](../media/solutions-architecture-center/m365-advanced-ediscovery-architecture.png)

[Descargar como un archivo PDF](https://download.microsoft.com/download/d/1/c/d1ce536d-9bcf-4d31-b75b-fcf0dc560665/m365-advanced-ediscovery-architecture.pdf)

[Descarga como archivo de Visio](https://download.microsoft.com/download/d/1/c/d1ce536d-9bcf-4d31-b75b-fcf0dc560665/m365-advanced-ediscovery-architecture.vsdx)

## <a name="training"></a>Formación

Entrenar a los administradores de TI, los administradores de eDiscovery y los equipos de investigación de cumplimiento en los conceptos básicos de eDiscovery (Premium) puede ayudar a su organización a empezar a trabajar más rápidamente con las herramientas de eDiscovery de Microsoft 365. Microsoft 365 proporciona el siguiente recurso para ayudar a estos usuarios de su organización a empezar a trabajar con eDiscovery: [Describir las funcionalidades de eDiscovery y auditoría de Microsoft 365](/training/modules/describe-ediscovery-capabilities-of-microsoft-365).
