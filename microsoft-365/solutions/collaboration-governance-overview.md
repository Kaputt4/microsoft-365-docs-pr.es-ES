---
title: Información general sobre el gobierno de colaboración en Microsoft 365
ms.reviewer: mmclean
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-overview
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: Obtenga información sobre cómo controlar las características relacionadas en grupos de Microsoft 365, Teams, SharePoint y Yammer.
ms.openlocfilehash: 8784f14530ec94a3151ef58589944947b5de9514
ms.sourcegitcommit: 9841058fcc95f7c2fed6af92bc3c3686944829b6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2020
ms.locfileid: "48377586"
---
# <a name="overview-of-collaboration-governance-in-microsoft-365"></a>Información general sobre el gobierno de colaboración en Microsoft 365

Microsoft 365 tiene un amplio conjunto de herramientas para implementar cualquier funcionalidad de gobierno que su organización pueda necesitar. Este artículo Guía a los profesionales de TI para que hagan las preguntas adecuadas para determinar sus requisitos de gobierno y cómo cumplirlos según su perfil de organización.

## <a name="what-are-microsoft-365-groups"></a>¿Qué son los grupos de Microsoft 365?

Sabemos que las organizaciones actuales usan un conjunto de herramientas diverso. Hay un grupo de desarrolladores que usan el chat de equipo, los ejecutivos que envían correo electrónico y toda la organización que se conecta a través de redes sociales empresariales. Hay varias herramientas de colaboración en uso, ya que cada grupo es único y tiene sus propias necesidades funcionales y estilo de trabajo. Algunos usarán solo el correo electrónico, mientras que otros vivirán principalmente en chat. 

Si los usuarios piensan que las herramientas proporcionadas por ti no se ajustan a sus necesidades, probablemente descargarán su aplicación de consumidor favorita que admite sus escenarios. Aunque este proceso permite que los usuarios empiecen a trabajar rápidamente, la experiencia del usuario se ve frustrada en toda la organización con varios inicios de sesión, problemas de uso compartido y no existe un solo lugar para ver el contenido. Este concepto se conoce como "sombrearlo" y representa un riesgo significativo para las organizaciones. Reduce la capacidad de administrar de manera uniforme el acceso de los usuarios, garantizar la seguridad y las necesidades de cumplimiento del servicio.

Servicios como Microsoft 365 Groups, Teams y Yammer habilitan a los usuarios y reduce el riesgo de sombrearlos proporcionando las herramientas necesarias para colaborar. Los grupos de 365 de Microsoft le permiten elegir un conjunto de personas con las que desea colaborar y configurar fácilmente una colección de recursos para que las compartan los usuarios. Al agregar miembros al grupo, se conceden automáticamente los permisos necesarios a todos los activos proporcionados por el grupo. Tanto Teams como Yammer usan grupos de Microsoft 365 para administrar su pertenencia.

![Diagrama que muestra los grupos de Microsoft 365 y los servicios relacionados](../media/microsoft-365-groups-hub-spoke.png)

Microsoft 365 grupos incluye una variedad de controles de gobierno, como una directiva de expiración, convenciones de nomenclatura y una directiva de palabras bloqueadas, para ayudarle a administrar los grupos de su organización. Para obtener más información [, vea planear el gobierno de la organización y el ciclo de vida para los grupos de microsoft 365 y Microsoft Teams](plan-organization-lifecycle-governance.md) .

## <a name="technical-architecture"></a>Arquitectura técnica

Hay tres métodos principales de comunicación que admite Microsoft 365:

- Outlook: colaboración a través del correo electrónico con un grupo compartido bandeja de entrada y calendario
- Microsoft Teams: un área de trabajo persistente basada en chat donde puede tener conversaciones informales, en tiempo real, sobre una variedad de temas, organizados por subgrupos específicos
- Yammer: experiencia social de empresa para colaboración

> [!NOTE]
> La creación de un nuevo grupo mediante otras aplicaciones de trabajo en equipo, como SharePoint, Planner o Stream-, creará un grupo con una bandeja de entrada de Outlook y la capacidad de conectarse a Microsoft Teams.

Según el lugar en el que se cree un grupo, ciertos recursos se aprovisionan automáticamente, por ejemplo:
- [Bandeja de entrada](https://support.office.com/article/have-a-group-conversation-in-outlook-a0482e24-a769-4e39-a5ba-a7c56e828b22) : para conversaciones de correo electrónico entre miembros del grupo. Esta bandeja de entrada tiene una dirección de correo electrónico y se puede configurar para que acepte mensajes de personas ajenas al grupo e incluso de fuera de la organización, como una lista de distribución tradicional.
 - [Calendario](https://support.office.com/article/schedule-a-meeting-on-a-group-calendar-in-outlook-0cf1ad68-1034-4306-b367-d75e9818376a) : para programar eventos relacionados con el grupo
- [Sitio de grupo de SharePoint](https://support.office.com/article/what-is-a-sharepoint-team-site-75545757-36c3-46a7-beed-0aaa74f0401e) : repositorio central de información, vínculos y contenido relacionado con el grupo
- [Bloc de notas de OneNote](https://support.office.com/article/get-started-with-onenote-e768fafa-8f9b-4eac-8600-65aa10b2fe97) : para recopilar ideas, investigar e información
- [Planner](https://support.office.com/article/microsoft-planner-help-4a9a13c6-3adf-4a60-a6fc-15c0b15e16fc) : para asignar y administrar tareas de proyecto entre los miembros del grupo
- [Grupo de Yammer](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2) : un punto común para tener conversaciones y compartir información
- Teams: un área de trabajo basada en chat en Microsoft 365
- Stream-un servicio de streaming de vídeo

> [!NOTE]
> Cuando se crea un nuevo grupo de Office 365 a través de Yammer o Teams, el grupo no es visible en Outlook ni en la libreta de direcciones porque la comunicación principal entre esos usuarios se produce en sus respectivos clientes. Los grupos de Yammer no se pueden conectar a Microsoft Teams.

## <a name="collaboration-options"></a>Opciones de colaboración

Hay varios lugares para colaborar y mantener conversaciones en Microsoft 365. Comprender dónde iniciar una conversación puede ayudarle a definir una estrategia de comunicación.

![Diagrama que muestra Cuándo usar Teams, Yammer y Outlook](../media/inner-loop-outer-loop.png)

- Teams: área de trabajo basada en chat (colaboración en alta velocidad): bucle interno
  - Creado para colaborar con las personas con las que trabaja cada día
  - Pone la información al alcance de los usuarios en una sola experiencia
  - Agregar pestañas, conectores y bots
  - Chat en directo, Conferencia de audio/vídeo, reuniones grabadas

- Yammer: conectarse a través de la organización (redes sociales de empresa): bucle externo
  - Comunidades de prácticas: grupos de personas con funciones cruzadas de personas que comparten un interés o experiencia comunes, pero que no tienen que trabajar juntos de forma cotidiana.
  - Conexión de liderazgo, comunidades de aprendizaje, comunidades basadas en roles

- Buzón y calendario (colaboración basada en correo electrónico)
  - Usar para comunicación dirigida a un grupo de personas
  - Calendario compartido para reuniones con otros miembros del grupo
 
Cada grupo obtiene un sitio de grupo de SharePoint conectado donde los usuarios pueden compartir contenido, crear páginas personalizadas y noticias de autor. También puede [conectar sitios de grupo de SharePoint existentes a nuevos grupos de 365 de Microsoft](https://docs.microsoft.com/sharepoint/dev/features/groupify/groupify-overview).

## <a name="illustrations"></a>Ilustraciones

### <a name="microsoft-teams-and-related-productivity-services-in-microsoft-365-for-it-architects"></a>Microsoft Teams y servicios de productividad relacionados de Microsoft 365 para arquitectos de TI
La arquitectura lógica de los servicios de productividad en Microsoft 365, una de las más destacadas gracias a Microsoft Teams.

|**Item**|**Descripción**|
|:-----|:-----|
|[![Imagen en miniatura para el póster de la arquitectura lógica de Teams](../downloads/msft-teams-logical-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-teams-logical-architecture.pdf) <br/> [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-teams-logical-architecture.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-teams-logical-architecture.vsdx)  <br>Actualizado en abril de 2019   |Microsoft proporciona un conjunto de servicios de productividad que funcionan en conjunto para proporcionar experiencias de colaboración con funcionalidades de gobierno, seguridad y cumplimiento. <br/> <br/>Esta serie de ilustraciones proporciona una vista de la arquitectura lógica de los servicios de productividad para arquitectos empresariales, que es una de las más destacadas gracias a Microsoft Teams.|


### <a name="groups-in-microsoft-365-for-it-architects"></a>Grupos en Microsoft 365 para arquitectos de TI
Lo que necesitan saber los arquitectos de TI sobre los grupos en Microsoft 365

|**Item**|**Descripción**|
|:-----|:-----|
|[![Imagen en miniatura para la infografía de grupos](../downloads/msft-m365-groups-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) <br/> [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-groups.vsdx) <br> Actualizado en junio de 2019|Estas ilustraciones detallan los diferentes tipos de grupos, cómo se crean y administran, y algunas recomendaciones para el gobierno de estos.|

## <a name="conference-sessions"></a>Sesiones de conferencia

Vea estas sesiones de conferencia para obtener más información sobre el gobierno para grupos y equipos de Microsoft 365.

**Conceptos básicos**

Conozca los conceptos básicos y las nuevas innovaciones de los grupos de 365 de Microsoft, incluidos la administración y el gobierno a escala, procedimientos recomendados para impulsar el uso y la adopción, y autoservicio.

- [Adoptar grupos de 365 de Microsoft](https://www.youtube.com/watch?v=dAamBF1gb7M)

**Gobierno**

Obtenga información sobre cómo configurar el ciclo de vida de expiración de grupos, las directivas de nomenclatura, las etiquetas de clasificación, la colaboración con invitados externos y administrar los permisos de creación de grupos.

- [Transformar la colaboración y luchar sombrearla con los grupos de Office 365](https://www.youtube.com/watch?v=Bhf_bKx3lAg)

**Ejemplo de cliente**

Vea un ejemplo en segundo plano sobre cómo Microsoft 365 grupos, SharePoint, Teams y Yammer trabajan juntos para proporcionar una plataforma de colaboración global.

- [Buscar el punto de acción de colaboración con Office 365 grupos, SharePoint, Teams y Yammer](https://www.youtube.com/watch?v=Rx9eVwqXeQk)
