---
title: Introducción a la solución eDiscovery (Premium) en Microsoft Purview
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 04/08/2022
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
description: Obtenga información sobre la solución eDiscovery (Premium) en Microsoft Purview. En este artículo se proporciona información general sobre eDiscovery (Premium) en Microsoft Purview, una herramienta que le ayudará a administrar investigaciones internas y externas. También enmarca los motivos empresariales para usar eDiscovery (Premium) para administrar las investigaciones legales.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1a26d1abe9965ad71383a6d07e277999d85e31ef
ms.sourcegitcommit: caedcf7f16eed23596487d97c375d4bc4c8f3566
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2022
ms.locfileid: "64999088"
---
# <a name="overview-of-microsoft-purview-ediscovery-premium"></a>Introducción a la exhibición de documentos electrónicos de Microsoft Purview (Premium)

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

La solución eDiscovery (Premium) de Microsoft Purview se basa en las funcionalidades existentes de Microsoft eDiscovery y análisis. eDiscovery (Premium) proporciona un flujo de trabajo de un extremo a otro para conservar, recopilar, analizar, revisar y exportar contenido que responda a las investigaciones internas y externas de la organización. También permite al equipo legal gestionar todo el flujo de trabajo de notificación de retención legal para comunicarse con los administradores de un caso.

## <a name="ediscovery-premium-capabilities"></a>Funcionalidades de eDiscovery (Premium)

eDiscovery (Premium) puede ayudar a su organización a responder a asuntos legales o investigaciones internas mediante la detección de datos donde se encuentran. Puede administrar sin problemas los flujos de trabajo de eDiscovery mediante la identificación de personas de interés y sus orígenes de datos, aplicar retenciones sin problemas para conservar los datos y, a continuación, administrar el proceso de comunicación de suspensión legal. Mediante la recopilación de datos del origen, puede buscar en la plataforma de Microsoft 365 en vivo para encontrar rápidamente lo que necesita. Las funcionalidades inteligentes de aprendizaje automático, como la indexación profunda, el subproceso de correo electrónico y la detección casi duplicada, también le ayudan a reducir grandes volúmenes de datos a un conjunto de datos pertinente.

En las secciones siguientes se describe cómo estas funcionalidades de eDiscovery (Premium) pueden ayudar a su organización.

![Funcionalidades de eDiscovery (Premium).](../media/advanced-ediscovery-capabilities.png)

### <a name="discover-and-collect-data-in-place"></a>Detección y recopilación de datos locales

Tradicionalmente, las organizaciones que se basan en varias soluciones de exhibición de documentos electrónicos de terceros requieren copiar grandes volúmenes de datos fuera de Microsoft 365 para procesar y tener que hospedar datos duplicados. Esta necesidad aumenta el tiempo para encontrar datos pertinentes y el riesgo, el costo y la complejidad de la administración de varias soluciones.

eDiscovery (Premium) en Microsoft 365 le permite detectar datos en el origen y permanecer dentro del límite de seguridad y cumplimiento de Microsoft 365.  Mediante la recopilación de datos en contexto del sistema en directo, eDiscovery (Premium) reduce la fricción de volver al origen y reduce el trabajo innecesario de tener que encontrar contenido que falta, lo que suele ocurrir cuando se producen retrasos en el registro en diario en soluciones de eDiscovery tradicionales.

Las funcionalidades nativas de búsqueda y recopilación de datos en Teams, Yammer, SharePoint Online, OneDrive para la Empresa y Exchange Online mejoran aún más la detección de datos. Por ejemplo, eDiscovery (Premium):

- Reconstruye Teams conversaciones (en lugar de devolver mensajes individuales de conversaciones).

- Recopila contenido basado en la nube compartido con los usuarios mediante vínculos o datos adjuntos modernos en mensajes de correo electrónico y chats Teams.

- Tiene compatibilidad integrada con cientos de tipos de archivo que no son Microsoft 365.

- Recopila datos de orígenes de terceros (como Bloomberg, Facebook, Slack y Zoom Meetings) que se importan y archivan en Microsoft 365 por [conectores de datos](archiving-third-party-data.md).

### <a name="manage-ediscovery-workflow-in-one-platform"></a>Administración del flujo de trabajo de eDiscovery en una plataforma

eDiscovery (Premium) puede ayudarle a reducir el número de soluciones de eDiscovery en las que debe confiar. Proporciona un flujo de trabajo simplificado de un extremo a otro, todo lo que se produce dentro de Microsoft 365. eDiscovery (Premium) ayuda a reducir la fricción de la identificación y recopilación de posibles orígenes de información pertinente mediante la asignación automática de orígenes de datos únicos y compartidos a la persona de interés (conocido como *custodio*), y proporcionando informes y análisis sobre datos potencialmente relevantes antes de recopilarlos para su análisis y revisión.

Además, las API de Microsoft Graph pueden ayudarle a automatizar el flujo de trabajo de eDiscovery y ampliar eDiscovery (Premium) para soluciones personalizadas.

### <a name="cull-data-intelligently"></a>Eliminación de datos de forma inteligente

Las funcionalidades inteligentes de aprendizaje automático en eDiscovery (Premium) ayudan a reducir la cantidad de datos que se van a revisar. Estas funcionalidades inteligentes le ayudan a reducir y seleccionar grandes volúmenes de datos en un conjunto pertinente. Por ejemplo, una consulta de conjunto de revisión integrada ayuda a filtrar solo por contenido único mediante la identificación de duplicados cercanos. Esta funcionalidad puede reducir considerablemente la cantidad de datos que se van a revisar.

Las funcionalidades adicionales de aprendizaje automático pueden refinar e identificar aún más los datos pertinentes mediante etiquetas inteligentes y herramientas de revisión asistida por tecnología, como los módulos de relevancia.

## <a name="ediscovery-premium-alignment-with-the-electronic-discovery-reference-model"></a>Alineación de eDiscovery (Premium) con el modelo de referencia de detección electrónica

El flujo de trabajo integrado de eDiscovery (Premium) en Microsoft 365 se alinea con el proceso de eDiscovery descrito por el modelo de referencia de detección electrónica (EDRM).

![Modelo de referencia de detección electrónica (EDRM).](../media/EDRMv2.png)

(Imagen basada en el modelo EDRM en edrm.net)

En un nivel alto, aquí se muestra cómo eDiscovery (Premium) admite el flujo de trabajo de EDRM:

- **Identificación.** Después de identificar a las posibles personas de interés en una investigación, puede agregarlas como custodios (también *denominados custodios de datos*, ya que pueden poseer información relevante para la investigación) a un caso de exhibición de documentos electrónicos (Premium). Una vez añadidos los usuarios como custodios, es fácil conservar, recopilar y revisar los documentos de los custodios.

- **Preservación.** Para conservar y proteger los datos que son relevantes para una investigación, eDiscovery (Premium) permite colocar una suspensión legal en los orígenes de datos asociados a los custodios en un caso. También puede poner en espera los datos no custodiados. eDiscovery (Premium) también tiene un flujo de trabajo de comunicaciones integrado para que pueda enviar notificaciones de suspensión legal a los custodios y realizar un seguimiento de sus confirmaciones.

- **Colección.** Después de identificar (y conservar) los orígenes de datos pertinentes para la investigación, puede usar la herramienta de búsqueda integrada en eDiscovery (Premium) para buscar y recopilar datos activos de los orígenes de datos custodiales (y orígenes de datos que no son de custodia, si procede) que pueden ser pertinentes para el caso.

- **Tratamiento.** Una vez recopilados todos los datos relevantes para el caso, el siguiente paso es procesarlos para su posterior revisión y análisis. En eDiscovery (Premium), los datos locales que identificó en la fase de recopilación se copian en una ubicación Azure Storage (denominada *conjunto de revisión*), lo que proporciona una vista estática de los datos del caso. 

- **Revisión.** Una vez agregados los datos a un conjunto de revisión, puede ver documentos específicos y ejecutar consultas adicionales para reducir los datos a lo más relevante para el caso. Además, puede anotar y etiquetar documentos específicos.

- **Análisis.** eDiscovery (Premium) proporciona una herramienta de análisis integrada que le ayuda a seleccionar más datos del conjunto de revisión que determine que no son relevantes para la investigación. Además de reducir el volumen de datos relevantes, eDiscovery avanzado también le ayuda a ahorrar costes de revisión legal al permitirle organizar el contenido para que el proceso de revisión sea más fácil y eficiente.

- **Producción** y **presentación.** Cuando esté listo, puede exportar los documentos de un conjunto de revisión para su revisión legal. Puede exportar los documentos en su formato nativo o en un formato especificado por EDRM para poder importarlos en aplicaciones de revisión de terceros.

## <a name="subscriptions-and-licensing"></a>Suscripciones y licencias

Las licencias para eDiscovery (Premium) requieren la suscripción de la organización adecuada y las licencias por usuario.

- **Suscripción a la organización:** Para acceder a eDiscovery (Premium) en el portal de cumplimiento de Microsoft Purview, su organización debe tener una de las siguientes opciones:

  - Suscripciones a Microsoft 365 E5 u Office 365 E5.
  
  - Suscripción a Microsoft 365 E3 con complemento de cumplimiento E5

  - Microsoft 365 E3 suscripción con el complemento E5 eDiscovery y Audit

  - Microsoft 365 Educación suscripción A5 o Office 365 Educación A5

   Si no tiene un plan de Microsoft 365 E5 existente y quiere probar eDiscovery (Premium), puede [agregar Microsoft 365](/office365/admin/try-or-buy-microsoft-365) a la suscripción existente o [registrarse para obtener una prueba](https://www.microsoft.com/microsoft-365/enterprise) de Microsoft 365 E5.

- **Licencias por usuario:** Para agregar un usuario como custodio en un caso de exhibición de documentos electrónicos avanzados, ese usuario debe tener asignada una de las licencias siguientes, en función de la suscripción de su organización:

  - Microsoft 365: Se debe asignar a los usuarios una de las siguientes opciones:
  
    - Microsoft 365 E5 licencia, una licencia de complemento de cumplimiento E5 o un complemento E5 eDiscovery y Audit

    - Microsoft 365 a los usuarios de primera línea se les debe asignar un complemento de cumplimiento de F5 o cumplimiento de seguridad de F5 &

    - Microsoft 365 Educación a los usuarios se les debe asignar una licencia A5

  - Office 365: a los usuarios se les debe asignar una licencia Office 365 E5 o Office 365 Educación A5.

Para obtener información sobre las licencias, descargue y vea la sección "eDiscovery and auditing" (Exhibición de documentos electrónicos y auditoría) en la [tabla Microsoft 365 Comparison (Comparación de Microsoft 365).](https://go.microsoft.com/fwlink/?linkid=2139145)

Para obtener información sobre cómo asignar licencias, consulte [Asignación de licencias a usuarios](/microsoft-365/admin/manage/assign-licenses-to-users).

> [!NOTE]
> Los usuarios solo necesitan una licencia E5 o A5 (o la licencia de complemento adecuada) para agregarse como custodios a un caso de exhibición de documentos electrónicos (Premium). Los administradores de TI, administradores de eDiscovery, abogados, asistentes o investigadores que usan eDiscovery (Premium) para administrar casos y revisar los datos de casos no necesitan una licencia E5, A5 o complemento.

## <a name="get-started-with-ediscovery-premium"></a>Comenzar con eDiscovery (Premium)

Hay dos pasos rápidos y sencillos para empezar a trabajar con eDiscovery (Premium).

![Introducción al flujo de trabajo con eDiscovery (Premium).](../media/get-started-AeD.png)

|Pasos  |Descripción  |
|:---------|:---------|
|[Configurar eDiscovery (Premium)](get-started-with-advanced-ediscovery.md)| Después de comprobar los requisitos de suscripción y licencia, puede asignar permisos y configurar la configuración de toda la organización para empezar a usar eDiscovery (Premium).|
|[Creación y administración de casos](create-and-manage-advanced-ediscoveryv2-case.md) | Cree casos para administrar el flujo de trabajo de eDiscovery (Premium) para todos los tipos legales y otros tipos de investigaciones de su organización.|
|||

## <a name="ediscovery-premium-architecture"></a>Arquitectura de eDiscovery (Premium)

Este es un diagrama de arquitectura de eDiscovery (Premium) que muestra el flujo de trabajo de un extremo a otro en un entorno de una sola ubicación geográfica y en un entorno multigeográfico, y el flujo de datos de un extremo a otro que está alineado con [EDRM](#ediscovery-premium-alignment-with-the-electronic-discovery-reference-model).

[![Póster del modelo: arquitectura de eDiscovery (Premium) en Microsoft 365.](../media/solutions-architecture-center/ediscovery-poster-thumb.png)](../media/solutions-architecture-center/m365-advanced-ediscovery-architecture.png)

[Visualización como imagen](../media/solutions-architecture-center/m365-advanced-ediscovery-architecture.png)

[Descargar como un archivo PDF](https://download.microsoft.com/download/d/1/c/d1ce536d-9bcf-4d31-b75b-fcf0dc560665/m365-advanced-ediscovery-architecture.pdf)

[Descargar como un archivo Visio](https://download.microsoft.com/download/d/1/c/d1ce536d-9bcf-4d31-b75b-fcf0dc560665/m365-advanced-ediscovery-architecture.vsdx)

## <a name="training"></a>Formación

El entrenamiento de los administradores de TI, los administradores de eDiscovery y los equipos de investigación de cumplimiento en los conceptos básicos de eDiscovery (Premium) puede ayudar a su organización a empezar a trabajar más rápidamente con Microsoft 365 herramientas de eDiscovery. Microsoft 365 proporciona el siguiente recurso para ayudar a estos usuarios de la organización a empezar a trabajar con eDiscovery: [Describir las funcionalidades de eDiscovery y auditoría de Microsoft 365](/learn/modules/describe-ediscovery-capabilities-of-microsoft-365).
