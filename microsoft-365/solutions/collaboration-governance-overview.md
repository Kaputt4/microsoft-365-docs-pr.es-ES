---
title: Un marco de gobernanza de colaboración para Microsoft 365
ms.reviewer: mmclean
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- m365solution-overview
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
recommendations: false
description: Conozca los procedimientos recomendados de gobernanza para las herramientas de colaboración Microsoft 365, incluidos Grupos de Microsoft 365, Teams, SharePoint y Yammer.
ms.openlocfilehash: f4afed27fa6d40f7f6967583bcfd3f43c69c7963
ms.sourcegitcommit: 5c64002236561000c5bd63c71423e8099e803c2d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/09/2022
ms.locfileid: "65285004"
---
# <a name="what-is-collaboration-governance"></a>¿Qué es la gobernanza de la colaboración?

La gobernanza de la colaboración es la forma en que administra el acceso de los usuarios a los recursos, el cumplimiento de los estándares empresariales y la seguridad de los datos.

Las organizaciones hoy en día usan un conjunto de herramientas diverso. Está el equipo de desarrolladores que usa el chat de equipo, los ejecutivos que envían correo electrónico y toda la organización que se conecta a través de redes sociales empresariales. Se usan varias herramientas de colaboración porque cada grupo es único y tiene sus propias necesidades funcionales y estilo de trabajo. Algunos solo usarán correo electrónico, mientras que otros vivirán principalmente en el chat. 

Si los usuarios sienten que las herramientas proporcionadas por TI no se ajustan a sus necesidades, es probable que descarguen su aplicación de consumidor favorita que admita sus escenarios. Aunque este proceso permite a los usuarios empezar a trabajar rápidamente, conduce a una experiencia de usuario frustrante en toda la organización con varios inicios de sesión, dificultad para compartir y ningún lugar para ver el contenido. Este concepto se conoce como "Shadow IT" y supone un riesgo significativo para las organizaciones. Reduce la capacidad de administrar uniformemente el acceso de los usuarios, garantizar la seguridad y las necesidades de cumplimiento del servicio.

Servicios como Microsoft 365 grupos, Teams y Yammer capacitan a los usuarios y reducen el riesgo de shadow IT al proporcionar las herramientas necesarias para colaborar. Microsoft 365 tiene un amplio conjunto de herramientas para implementar las funcionalidades de gobernanza que su organización pueda necesitar. 

![Gráfico que muestra las opciones de gobernanza de colaboración en Microsoft 365.](../media/collaboration-governance-overview.png)

Esta serie de artículos le ayudará a comprender cómo interactúan los grupos, los equipos y la configuración de SharePoint, qué funcionalidades de gobernanza están disponibles y cómo crear e implementar un marco de gobernanza para las características de colaboración en Microsoft 365.

### <a name="setting-up-secure-collaboration-with-microsoft-365"></a>Configuración de la colaboración segura con Microsoft 365

Hay muchas opciones para implementar Grupos de Microsoft 365 y Teams para la colaboración segura en su organización. Se recomienda usar este contenido de gobernanza junto [con Configurar el uso compartido seguro de archivos y la colaboración con Microsoft Teams](setup-secure-collaboration-with-teams.md) y sus artículos asociados para crear la mejor solución de colaboración para su organización.

### <a name="data-residency-governance"></a>Gobernanza de residencia de datos

Si su organización es multinacional y tiene requisitos de residencia de datos para diferentes zonas geográficas, incluya [Microsoft 365 Multi-Geo](/microsoft-365/enterprise/microsoft-365-multi-geo) como parte del plan de gobernanza de colaboración.

## <a name="why-microsoft-365-groups-are-important-in-collaboration-governance"></a>Por qué los grupos de Microsoft 365 son importantes en la gobernanza de la colaboración

Microsoft 365 grupos le permite elegir un conjunto de personas con las que desea colaborar y configurar fácilmente una colección de recursos para que esas personas puedan compartir. Al agregar miembros al grupo, se conceden automáticamente los permisos necesarios a todos los recursos proporcionados por el grupo. Tanto Teams como Yammer usan grupos de Microsoft 365 para administrar su pertenencia.

Microsoft 365 grupos incluyen un conjunto de recursos vinculados que los usuarios pueden usar para la comunicación y la colaboración. Los grupos siempre incluyen un sitio de SharePoint, Planner, un área de trabajo de Power BI, un buzón y un calendario, y Stream. Dependiendo de cómo cree el grupo, opcionalmente puede agregar otros servicios, como Teams, Yammer y Project.

![Diagrama que muestra Grupos de Microsoft 365 y servicios relacionados.](../media/microsoft-365-groups-hub-spoke.png)

|Recurso|Descripción|
|:------|:----------|
|[Calendario](https://support.office.com/article/schedule-a-meeting-on-a-group-calendar-in-outlook-0cf1ad68-1034-4306-b367-d75e9818376a)|Para programar eventos relacionados con el grupo|
|[Bandeja de entrada](https://support.office.com/article/have-a-group-conversation-in-outlook-a0482e24-a769-4e39-a5ba-a7c56e828b22)|Para las conversaciones por correo electrónico entre miembros del grupo. Esta bandeja de entrada tiene una dirección de correo electrónico y se puede establecer para aceptar mensajes de personas ajenas al grupo e incluso fuera de su organización, de forma muy similar a una lista de distribución tradicional.|
|[cuaderno de OneNote](https://support.office.com/article/get-started-with-onenote-e768fafa-8f9b-4eac-8600-65aa10b2fe97)|Para recopilar ideas, investigación e información|
|[Planificador](https://support.office.com/article/microsoft-planner-help-4a9a13c6-3adf-4a60-a6fc-15c0b15e16fc)|Para asignar y administrar tareas de proyecto entre los miembros del grupo|
|[área de trabajo de Power BI](/power-bi/collaborate-share/service-new-workspaces)|Un espacio de colaboración de datos con paneles e informes|
|[Project y hoja de ruta](https://support.microsoft.com/project)|Herramientas de administración de proyectos basadas en web|
|[Sitio de grupo de SharePoint](https://support.office.com/article/what-is-a-sharepoint-team-site-75545757-36c3-46a7-beed-0aaa74f0401e)|Un repositorio central para información, vínculos y contenido relacionado con el grupo|
|[Stream](https://support.microsoft.com/microsoft-stream)|Un servicio de streaming de vídeo|
|[Teams](https://support.microsoft.com/teams)|Un área de trabajo basada en chat en Microsoft 365|
|[grupo de Yammer](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2)|Un lugar común para tener conversaciones y compartir información|

Grupos de Microsoft 365 incluye una variedad de controles de gobernanza, incluida una directiva de expiración, convenciones de nomenclatura y una directiva de palabras bloqueadas, para ayudarle a administrar grupos de su organización. Dado que los grupos controlan la pertenencia y el acceso a este conjunto de recursos, la administración de grupos es una parte clave de la administración de la colaboración en Microsoft 365.

## <a name="define-collaboration-governance-best-practices-for-your-organization"></a>Definición de procedimientos recomendados de gobernanza de colaboración para su organización

Hay varios lugares para colaborar y tener conversaciones dentro de Microsoft 365. Comprender dónde pueden iniciar conversaciones los usuarios puede ayudarle a definir una estrategia de comunicación.

Hay tres métodos de comunicación principales admitidos por Microsoft 365:

- Outlook: colaboración por correo electrónico con una bandeja de entrada de grupo compartido y un calendario
- Microsoft Teams: un área de trabajo basada en chat persistente en la que puede tener conversaciones informales, en tiempo real, en torno a una variedad de temas, organizadas por subgrupos específicos.
- Yammer: experiencia social empresarial para la colaboración

![Diagrama que muestra cuándo usar Teams, Yammer y Outlook.](../media/inner-loop-outer-loop.png)

- Teams: área de trabajo basada en chat (colaboración de alta velocidad): bucle interno
  - Creado para la colaboración con las personas con las que trabajan los usuarios cada día
  - Pone la información al alcance de los usuarios en una única experiencia
  - Adición de pestañas, conectores y bots
  - Chat en vivo, audio/videoconferencia, reuniones grabadas

- Yammer: conectarse a través de la organización (redes sociales empresariales): bucle externo
  - Comunidades de práctica: grupos multifuncionales de personas que comparten un interés común o conocimientos, pero que no trabajan necesariamente juntos día a día
  - Conexión de liderazgo, comunidades de aprendizaje, comunidades basadas en roles

- Buzón y calendario (colaboración basada en correo electrónico)
  - Se usa para la comunicación dirigida con un grupo de personas
  - Calendario compartido para reuniones con otros miembros del grupo
 
A medida que determine cómo desea usar las características de colaboración en Microsoft 365, tenga en cuenta estos métodos de comunicación y cuáles es probable que los usuarios usen en diferentes escenarios.

> [!NOTE]
> Cuando se crea un nuevo grupo de Office 365 a través de Yammer o Teams, el grupo no es visible en Outlook ni en la libreta de direcciones porque la comunicación principal entre esos usuarios se produce en sus respectivos clientes. Yammer grupos no se pueden conectar a Teams.

## <a name="collaboration-governance-best-practices-checklist"></a>Lista de comprobación de procedimientos recomendados de gobernanza de colaboración

Al iniciar el proceso de planeamiento de gobernanza, tenga en cuenta estos procedimientos recomendados:

- **Hable con los usuarios** : identifique a los usuarios más grandes de las características de colaboración y reúnase con ellos para comprender sus principales requisitos empresariales y escenarios de casos de uso.

- **Equilibrar riesgos y ventajas** : revise sus necesidades empresariales, normativas, legales y de cumplimiento y planee una solución que se optimice para todos los resultados.

- **Adaptarse a diferentes organizaciones y diferentes tipos de contenido y escenarios**: tenga en cuenta las diferentes necesidades de los distintos grupos o departamentos y los distintos tipos de contenido, como el contenido de la intranet frente al contenido OneDrive de un usuario.

- **Alinearse con las prioridades empresariales** : los objetivos empresariales le ayudarán a definir cuánto tiempo y energía necesita para invertir en gobernanza.

- **Insertar decisiones de gobernanza directamente en las soluciones que cree**: muchas decisiones de gobernanza se pueden implementar activando o desactivando las características de Microsoft 365.


- **Usar un enfoque por fases** : implemente primero las características de colaboración para un grupo pequeño de usuarios. Obtenga comentarios de ellos, vea los vales del departamento de soporte técnico y actualice cualquier configuración o proceso necesario antes de continuar con un grupo mayor.

- **Reforzar con el entrenamiento**: adapte soluciones como [Microsoft 365 caminos de aprendizaje](/office365/customlearning) para garantizar que las expectativas específicas de la organización se refuercen con el entrenamiento proporcionado por Microsoft.

- **Tenga una estrategia para comunicar directivas y directrices de gobernanza en su organización**: cree un centro de adopción de Microsoft 365 en un sitio de comunicación SharePoint para comunicar directivas y procedimientos.

- **Definir roles y responsabilidades** : identifique primero el equipo principal de gobernanza y trabaje a través de decisiones clave de gobernanza sobre el aprovisionamiento y la nomenclatura y el acceso externo y, a continuación, siga las decisiones restantes.

- **Revise sus decisiones a medida que cambien la empresa y la tecnología** : reúnase periódicamente para revisar las nuevas funcionalidades y las nuevas expectativas empresariales.

Para más información sobre estas prácticas, consulte Creación de un [plan de gobernanza de colaboración](collaboration-governance-first.md).

## <a name="end-user-impact-and-change-management"></a>Impacto del usuario final y administración de cambios

Dado que los grupos y los equipos se pueden crear de varias maneras, se recomienda entrenar a los usuarios para que usen el método que mejor se adapte a su organización:

- Si la organización realiza la mayor parte de su comunicación mediante correo electrónico, indique a los usuarios que creen grupos en Outlook.
- Si su organización usa en gran medida SharePoint o está migrando desde SharePoint local, indique a los usuarios que creen sitios de SharePoint equipo para la colaboración.
- Si su organización ha implementado Teams, indique a los usuarios que creen un equipo cuando necesiten un espacio de colaboración.

Esto ayuda a evitar confusiones si los usuarios no están familiarizados con cómo se relacionan los grupos con sus servicios relacionados. Para obtener más información sobre cómo comunicarse con los usuarios sobre grupos, consulte [Explicación de Grupos de Microsoft 365 a los usuarios](../admin/create-groups/explain-groups-knowledge-worker.md).

## <a name="key-collaboration-governance-capabilities-and-licensing-requirements"></a>Funcionalidades clave de gobernanza de colaboración y requisitos de licencia

Las funcionalidades de gobernanza para la colaboración en Microsoft 365 incluyen características en Microsoft 365, Teams, SharePoint y Azure Active Directory.

| Funcionalidad o característica | Description | Licencias |
|:----------------------|:------------|:----------|
|Uso compartido de sitios y equipos|Controlar si los equipos, grupos y sitios se pueden compartir con personas ajenas a la organización.|Microsoft 365 E5 o E3|
|Permitir o bloquear dominios|Restringir el uso compartido con personas ajenas a la organización a personas de dominios específicos.|Microsoft 365 E5 o E3|
|Creación de sitios sin intervención del administrador|Permitir o impedir que los usuarios creen sus propios sitios de SharePoint.|Microsoft 365 E5 o E3|
|Uso compartido de archivos y sitios restringidos|Restrinja el uso compartido de sitios, archivos y carpetas a los miembros de un grupo de seguridad específico.|Microsoft 365 E5 o E3|
|Creación de grupos restringidos|Restrinja la creación de grupos y equipos a los miembros de un grupo de seguridad específico.|Microsoft 365 E5 o E3 con licencias edu básicas de Azure AD Premium o Azure AD|
|Directiva de nomenclatura de grupos|Aplicar prefijos o sufijos en los nombres de grupo y equipo.|Microsoft 365 E5 o E3 con licencias edu básicas de Azure AD Premium o Azure AD|
|Directiva de expiración de grupo|Establezca grupos inactivos y equipos para que expiren y se eliminen después de un período de tiempo especificado.|Microsoft 365 E5 o E3 con licencias de Azure AD Premium|
|Acceso de invitado por grupo|Permitir o impedir el uso compartido de grupos y equipos con personas ajenas a la organización por grupo.|Microsoft 365 E5 o E3|

## <a name="collaboration-governance-planning-recommendations"></a>Recomendaciones de planeamiento de gobernanza de colaboración

Siga estos pasos básicos para crear su plan de gobernanza:

1. Tenga en cuenta los principales objetivos y procesos empresariales: [cree su plan de gobernanza](collaboration-governance-first.md) para satisfacer las necesidades de su empresa.
2. Descripción de la configuración en los servicios: [la configuración en grupos y SharePoint](groups-sharepoint-governance.md) interactúan entre sí, al igual que [la configuración en grupos, SharePoint y Teams](groups-sharepoint-teams-governance.md) y [otros servicios](groups-services-interactions.md). Asegúrese de comprender estas interacciones al planear la estrategia de gobernanza.
3. Planear la administración del acceso de usuario: planee [el nivel de acceso que desea conceder a los usuarios en grupos, SharePoint y Teams](groups-teams-access-governance.md).
4. Planear la administración de la configuración de cumplimiento: revise las [opciones de cumplimiento disponibles para grupos de Microsoft 365, Teams y colaboración SharePoint](groups-teams-compliance-governance.md).
5. Planear la administración de las comunicaciones: revise las [opciones de gobernanza de comunicaciones disponibles para escenarios de colaboración](groups-teams-communication-governance.md).
6. Planeamiento de la gobernanza de la organización y del ciclo de vida: elija [las directivas que desea usar para la creación, nomenclatura, expiración y archivado de grupos y equipos](plan-organization-lifecycle-governance.md). Además, comprenda las [opciones de fin de ciclo de vida para grupos, equipos y Yammer](end-life-cycle-groups-teams-sites-yammer.md)

![Ilustración de los pasos de gobernanza recomendados.](../media/collaboration-governance-steps.png)

## <a name="training-for-administrators"></a>Entrenamiento para administradores

Estos módulos de entrenamiento de Microsoft Learn pueden ayudarle a aprender las características de gobernanza de Microsoft 365.

#### <a name="information-protection"></a>Protección de la información

|Aprendizaje:|Administrar el gobierno y la protección de la información|
|:---|:---|
|![Icono de entrenamiento de protección de la información.](../media/information-protection-governance.svg)|La cantidad de datos que se generan hoy está creciendo más rápido que nunca, los empleados quieren hacer su trabajo en todas partes y el panorama normativo cambia constantemente. Las soluciones de Microsoft para el gobierno y la protección de la información ayudan a las organizaciones a lograr el equilibrio adecuado entre mantener la protección de los datos y la productividad de los usuarios. Esta ruta de aprendizaje puede ayudarle a preparar los certificados Microsoft 365 Certified: Security Administrator Associate y Microsoft 365 Certified: Enterprise Administration Expert.<br><br>5 h 13 min - Learning Ruta de acceso - 7 módulos|

> [!div class="nextstepaction"]
> [Iniciar >](/learn/modules/m365-compliance-information-governance/introduction/)

<br><br>

|Aprendizaje:|Proteger la información de la empresa con Microsoft 365|
|:---|:---|
|![Teams icono de entrenamiento.](../media/protect-enterprise-information-microsoft-365.svg)|Proteger y asegurar la información de su organización es más difícil que nunca. La ruta de aprendizaje Proteger la información de la empresa con Microsoft 365 analiza cómo proteger su información confidencial de un uso excesivo o indebido accidental, cómo descubrir y clasificar los datos, cómo protegerlos con etiquetas de confidencialidad y cómo supervisar y analizar su información confidencial para protegerla contra su pérdida. Esta ruta de aprendizaje puede ayudarle a prepararse para las certificaciones Microsoft 365 Certified: Security Administrator Associate y Microsoft 365 Certified: Enterprise Administration Expert.<br><br>1 h - ruta de acceso Learning - 5 módulos|

> [!div class="nextstepaction"]
> [Iniciar >](/learn/modules/m365-security-info-overview/introduction/)

#### <a name="security-and-compliance"></a>Seguridad y cumplimiento

|Aprendizaje:|Demuestre conocimientos básicos de las funciones del Centro de seguridad y cumplimiento normativo de Microsoft 365|
|:---|:---|
|![Icono de entrenamiento de seguridad y cumplimiento.](../media/microsoft-365-security-and-compliance-capabilities.svg)|Obtenga información sobre las áreas de soluciones de seguridad y cumplimiento de Microsoft 365 y las funcionalidades disponibles para ayudar a las empresas a proteger sus empresas y cumplir con los requisitos reglamentarios. Si no está familiarizado con los conceptos básicos de informática en la nube, le recomendamos que tome [Conceptos en la nube: principios de la informática en la nube](/learn/modules/principles-cloud-computing/index).<br><br>3 h 11 min - Learning Ruta de acceso - 8 módulos|

> [!div class="nextstepaction"]
> [Iniciar >](/learn/modules/what-is-m365/1-introduction/)

## <a name="illustrations"></a>Ilustraciones

Estas ilustraciones le ayudarán a comprender cómo los grupos y equipos interactúan con otros servicios de Microsoft 365 y qué características de gobernanza y cumplimiento están disponibles para ayudarle a administrar estos servicios en su organización.

### <a name="groups-in-microsoft-365-for-it-architects"></a>Grupos en Microsoft 365 para arquitectos de TI
Lo que necesitan saber los arquitectos de TI sobre los grupos en Microsoft 365

|**Item**|**Descripción**|
|:-----|:-----|
|[![Imagen del pulgar para la infografía de grupos.](../downloads/msft-m365-groups-architecture-thumb.png)](https://download.microsoft.com/download/6/3/0/6309218f-a169-4f2d-af4c-2fe49e30ba17/msft-m365-groups.pdf) <br/> [PDF](https://download.microsoft.com/download/6/3/0/6309218f-a169-4f2d-af4c-2fe49e30ba17/msft-m365-groups.pdf) \| [Visio](https://download.microsoft.com/download/6/3/0/6309218f-a169-4f2d-af4c-2fe49e30ba17/msft-m365-groups.vsdx) <br> Actualizado en mayo de 2022|Estas ilustraciones detallan los diferentes tipos de grupos, cómo se crean y administran, y algunas recomendaciones para el gobierno de estos.|

### <a name="microsoft-teams-and-related-productivity-services-in-microsoft-365-for-it-architects"></a>Microsoft Teams y servicios de productividad relacionados de Microsoft 365 para arquitectos de TI
La arquitectura lógica de los servicios de productividad en Microsoft 365, una de las más destacadas gracias a Microsoft Teams.

|**Item**|**Descripción**|
|:-----|:-----|
|[![Imagen digital para Teams póster de arquitectura lógica.](../downloads/msft-teams-logical-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-teams-logical-architecture.pdf) <br/> [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-teams-logical-architecture.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-teams-logical-architecture.vsdx)  <br>Actualizado en abril de 2019   |Microsoft proporciona un conjunto de servicios de productividad que funcionan en conjunto para proporcionar experiencias de colaboración con funcionalidades de gobierno, seguridad y cumplimiento. <br/> <br/>Esta serie de ilustraciones proporciona una vista de la arquitectura lógica de los servicios de productividad para arquitectos empresariales, que es una de las más destacadas gracias a Microsoft Teams.|

### <a name="microsoft-365-information-protection-and-compliance-capabilities"></a>Microsoft 365 capacidades de cumplimiento y protección de la información

Microsoft 365 incluye un amplio conjunto de funcionalidades de cumplimiento y protección de la información. Junto con las herramientas de productividad de Microsoft, estas funcionalidades están diseñadas para ayudar a las organizaciones a colaborar en tiempo real a la vez que se adhieren a marcos de cumplimiento normativo estrictos. 

Este conjunto de ilustraciones usa uno de los sectores más regulados, los servicios financieros, para demostrar cómo se pueden aplicar estas capacidades para abordar los requisitos normativos comunes. Siéntase libre de adaptar estas ilustraciones para su propio uso. 


| Elemento | Description |
|:-----|:-----|
|[![Póster del modelo: Funcionalidades de cumplimiento y protección de la información de Microsoft Purview.](../media/solutions-architecture-center/m365-compliance-illustrations-thumb.png)](https://download.microsoft.com/download/3/a/6/3a6ab1a3-feb0-4ee2-8e77-62415a772e53/m365-compliance-illustrations.pdf) <br/> Inglés: [Descargar como PDF](https://download.microsoft.com/download/3/a/6/3a6ab1a3-feb0-4ee2-8e77-62415a772e53/m365-compliance-illustrations.pdf)  \| [Descargar como Visio](https://download.microsoft.com/download/3/a/6/3a6ab1a3-feb0-4ee2-8e77-62415a772e53/m365-compliance-illustrations.vsdx) <br/> Japonés: [Descargar como PDF](https://download.microsoft.com/download/6/f/1/6f1a7d0e-dd8e-442e-b073-8e94327ae4f8/m365-compliance-illustrations.pdf)  \| [Descargar como Visio](https://download.microsoft.com/download/6/f/1/6f1a7d0e-dd8e-442e-b073-8e94327ae4f8/m365-compliance-illustrations.vsdx) <br/> Actualizado en noviembre de 2020|Incluye: <ul><li>  Prevención de pérdida de datos de Microsoft Purview Information Protection y Microsoft Purview</li><li>Directivas y etiquetas de retención </li><li>Barreras de información</li><li>Cumplimiento de comunicaciones</li><li>Riesgo de Insider</li><li>Ingesta de datos de terceros</li>|

## <a name="conference-sessions"></a>Sesiones de conferencia

Vea estas sesiones de conferencia para obtener más información sobre la gobernanza de Grupos de Microsoft 365 y Teams.

**Conceptos básicos**

Conozca los aspectos básicos y las nuevas innovaciones en Grupos de Microsoft 365, incluida la administración y la gobernanza a escala, los procedimientos recomendados para impulsar el uso y la adopción, y el autoservicio.

- [Adoptar Grupos de Microsoft 365](https://www.youtube.com/watch?v=dAamBF1gb7M)

**Gobierno**

Obtenga información sobre cómo configurar el ciclo de vida de expiración de los grupos, las directivas de nomenclatura, las etiquetas de clasificación, la colaboración con invitados externos y administrar los permisos de creación de grupos.

- [Transformación de la colaboración y lucha contra la ti instantánea con grupos de Office 365](https://www.youtube.com/watch?v=Bhf_bKx3lAg)

**Ejemplo de cliente**

Vea un ejemplo en segundo plano de cómo Grupos de Microsoft 365, SharePoint, Teams y Yammer funcionan juntos para proporcionar una plataforma de colaboración global.

- [Encontrar el punto ideal de colaboración con Grupos de Microsoft 365, SharePoint, Teams y Yammer](https://www.youtube.com/watch?v=Rx9eVwqXeQk)

## <a name="see-also"></a>Consulte también

[Documentación de Seguridad de Microsoft 365](../security/index.yml)

[Documentación de Microsoft Purview](../compliance/index.yml)
