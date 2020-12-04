---
title: ¿Qué es el gobierno de colaboración?
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
ms.openlocfilehash: 2e4064ec64c52d4d3afe3d2e83f34079b3749f97
ms.sourcegitcommit: 7e003ee0a06f61bfb9f80441c3479fa3148afafe
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2020
ms.locfileid: "49568449"
---
# <a name="what-is-collaboration-governance"></a>¿Qué es el gobierno de colaboración?

El gobierno de colaboración es cómo administrar el acceso de los usuarios a los recursos, el cumplimiento de los estándares empresariales y garantizar la seguridad de sus datos.

Las organizaciones de hoy en día usan un conjunto de herramientas diverso. Hay un grupo de desarrolladores que usan el chat de equipo, los ejecutivos que envían correo electrónico y toda la organización que se conecta a través de redes sociales empresariales. Hay varias herramientas de colaboración en uso, ya que cada grupo es único y tiene sus propias necesidades funcionales y estilo de trabajo. Algunos usarán solo el correo electrónico, mientras que otros vivirán principalmente en chat. 

Si los usuarios piensan que las herramientas proporcionadas por ti no se ajustan a sus necesidades, probablemente descargarán su aplicación de consumidor favorita que admite sus escenarios. Aunque este proceso permite que los usuarios empiecen a trabajar rápidamente, la experiencia del usuario se ve frustrada en toda la organización con varios inicios de sesión, problemas de uso compartido y no existe un solo lugar para ver el contenido. Este concepto se conoce como "sombrearlo" y representa un riesgo significativo para las organizaciones. Reduce la capacidad de administrar de manera uniforme el acceso de los usuarios, garantizar la seguridad y las necesidades de cumplimiento del servicio.

Servicios como Microsoft 365 Groups, Teams y Yammer habilitan a los usuarios y reduce el riesgo de sombrearlos proporcionando las herramientas necesarias para colaborar. Microsoft 365 tiene un amplio conjunto de herramientas para implementar cualquier funcionalidad de gobierno que su organización pueda necesitar. 

![Gráfico que muestra las opciones de gobierno de colaboración en Microsoft 365](../media/collaboration-governance-overview.png)

Esta serie de artículos le ayudará a comprender cómo interactúan los grupos, los equipos y la configuración de SharePoint, las funciones de gobierno disponibles y cómo crear e implementar un plan de gobierno para las características de colaboración de Microsoft 365.

## <a name="what-are-microsoft-365-groups"></a>¿Qué son los grupos de Microsoft 365?

Los grupos de 365 de Microsoft le permiten elegir un conjunto de personas con las que desea colaborar y configurar fácilmente una colección de recursos para que las compartan los usuarios. Al agregar miembros al grupo, se conceden automáticamente los permisos necesarios a todos los activos proporcionados por el grupo. Tanto Teams como Yammer usan grupos de Microsoft 365 para administrar su pertenencia.

Los grupos de Microsoft 365 incluyen un conjunto de recursos vinculados que los usuarios pueden usar para la comunicación y la colaboración. Los grupos siempre incluyen un sitio de SharePoint, Planner, un área de trabajo de Power BI, un buzón, un calendario y una secuencia. En función de cómo cree el grupo, puede Agregar también otros servicios como Teams, Yammer y Project.

![Diagrama que muestra los grupos de Microsoft 365 y los servicios relacionados](../media/microsoft-365-groups-hub-spoke.png)

|Recurso|Descripción|
|:------|:----------|
|[Calendario](https://support.office.com/article/schedule-a-meeting-on-a-group-calendar-in-outlook-0cf1ad68-1034-4306-b367-d75e9818376a)|Para programar eventos relacionados con el grupo|
|[Bandeja de entrada](https://support.office.com/article/have-a-group-conversation-in-outlook-a0482e24-a769-4e39-a5ba-a7c56e828b22)|Para conversaciones de correo electrónico entre miembros del grupo. Esta bandeja de entrada tiene una dirección de correo electrónico y se puede configurar para que acepte mensajes de personas ajenas al grupo e incluso de fuera de la organización, como una lista de distribución tradicional.|
|[Bloc de notas de OneNote](https://support.office.com/article/get-started-with-onenote-e768fafa-8f9b-4eac-8600-65aa10b2fe97)|Para recopilar ideas, investigaciones e información|
|[Planificador](https://support.office.com/article/microsoft-planner-help-4a9a13c6-3adf-4a60-a6fc-15c0b15e16fc)|Para asignar y administrar tareas de proyecto entre los miembros del grupo|
|[Área de trabajo de Power BI](https://docs.microsoft.com/power-bi/collaborate-share/service-new-workspaces)|Un espacio de colaboración de datos con paneles e informes|
|[Guía básica y de proyecto](https://support.microsoft.com/project)|Herramientas de administración de proyectos basada en Web|
|[Sitio de grupo de SharePoint](https://support.office.com/article/what-is-a-sharepoint-team-site-75545757-36c3-46a7-beed-0aaa74f0401e)|Un repositorio central para información, vínculos y contenido relacionado con su grupo|
|[Secuencia](https://support.microsoft.com/microsoft-stream)|Un servicio de streaming de vídeo|
|[Teams](https://support.microsoft.com/teams)|Un área de trabajo basada en chat en Microsoft 365|
|[Grupo de Yammer](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2)|Un punto común para tener conversaciones y compartir información|

Microsoft 365 grupos incluye una variedad de controles de gobierno, como una directiva de expiración, convenciones de nomenclatura y una directiva de palabras bloqueadas, para ayudarle a administrar los grupos de su organización. Como los grupos controlan la pertenencia y el acceso a esta serie de recursos, la administración de grupos es una parte fundamental de la administración de la colaboración en Microsoft 365.

## <a name="define-a-collaboration-strategy-for-your-organization"></a>Definir una estrategia de colaboración para la organización

Hay varios lugares para colaborar y mantener conversaciones en Microsoft 365. Conocer dónde pueden iniciar las conversaciones los usuarios pueden ayudarle a definir una estrategia de comunicación.

Hay tres métodos principales de comunicación que admite Microsoft 365:

- Outlook: colaboración a través del correo electrónico con un grupo compartido bandeja de entrada y calendario
- Microsoft Teams: un área de trabajo persistente basada en chat donde puede tener conversaciones informales, en tiempo real, sobre una variedad de temas, organizados por subgrupos específicos
- Yammer: experiencia social de empresa para colaboración

![Diagrama que muestra Cuándo usar Teams, Yammer y Outlook](../media/inner-loop-outer-loop.png)

- Teams: área de trabajo basada en chat (colaboración en alta velocidad): bucle interno
  - Creado para colaborar con las personas a las que trabajan los usuarios cada día
  - Pone la información al alcance de los usuarios en una sola experiencia
  - Agregar pestañas, conectores y bots
  - Chat en directo, Conferencia de audio/vídeo, reuniones grabadas

- Yammer: conectarse a través de la organización (redes sociales de empresa): bucle externo
  - Comunidades de prácticas: grupos de personas con funciones cruzadas de personas que comparten un interés o experiencia comunes, pero que no tienen que trabajar juntos de forma cotidiana.
  - Conexión de liderazgo, comunidades de aprendizaje, comunidades basadas en roles

- Buzón y calendario (colaboración basada en correo electrónico)
  - Se usa para la comunicación dirigida a un grupo de personas.
  - Calendario compartido para reuniones con otros miembros del grupo
 
A medida que determine cómo desea usar las características de colaboración de Microsoft 365, tenga en cuenta estos métodos de comunicación y que es probable que los usuarios usen en diferentes escenarios.

> [!NOTE]
> Cuando se crea un nuevo grupo de Office 365 a través de Yammer o Teams, el grupo no es visible en Outlook ni en la libreta de direcciones porque la comunicación principal entre esos usuarios se produce en sus respectivos clientes. Los grupos de Yammer no se pueden conectar a Microsoft Teams.


## <a name="best-practices"></a>Procedimientos recomendados

Cuando inicie el proceso de planeación del gobierno, tenga en cuenta estos procedimientos recomendados:

- **Hable con sus usuarios** : identifique a sus usuarios más grandes de características de colaboración y reúnase con ellos para conocer sus principales requisitos empresariales y escenarios de uso de casos.

- **Equilibre los riesgos y los beneficios** : Revise sus necesidades empresariales, reglamentarias, legales y de cumplimiento, y planee una solución que optimice todos los resultados.

- **Adaptarse a distintas organizaciones y a diferentes tipos de contenido y escenarios** : tenga en cuenta las distintas necesidades de los distintos grupos o departamentos, así como los distintos tipos de contenido, como el contenido de una intranet en lugar del contenido de OneDrive de un usuario.

- **Alinear con las prioridades empresariales** : los objetivos empresariales le ayudarán a definir cuánto tiempo y energía necesita invertir en el gobierno.

- **Insertar decisiones de gobierno directamente en las soluciones que cree** : se pueden implementar muchas decisiones de gobierno mediante la activación o desactivación de características de Microsoft 365.

- **Reforzar la formación** : adapte las soluciones como los [caminos de aprendizaje de Microsoft 365](https://docs.microsoft.com/office365/customlearning) para garantizar que las expectativas específicas de la organización se refuerzan con la formación proporcionada por Microsoft.

- **Tiene una estrategia para comunicar las directivas de gobierno y las directrices en su organización** : cree un centro de adopción de Microsoft 365 en un sitio de comunicación de SharePoint para comunicar directivas y procedimientos.

- **Definir funciones y responsabilidades** : identificar el equipo principal del gobierno y trabajar en las decisiones de gobierno clave sobre el aprovisionamiento y la nomenclatura y el acceso externo en primer lugar y, a continuación, trabajar con las demás decisiones.

- Revise de nuevo **sus decisiones a medida que cambian los cambios tecnológicos y de negocios** periódicamente para revisar nuevas capacidades y nuevas expectativas empresariales.

Para obtener una visión más detallada de estos procedimientos, lea [Create Your Collaboration Governance plan](collaboration-governance-first.md).

## <a name="end-user-impact-and-change-management"></a>Impacto en el usuario final y administración de cambios

Como los grupos y los equipos se pueden crear de varias formas, recomendamos que los usuarios realicen una formación para que los usuarios usen el método que mejor se adapte a su organización:

- Si su organización realiza la mayor parte de su comunicación con el correo electrónico, indique a los usuarios que creen grupos en Outlook.
- Si su organización usa mucho SharePoint o está migrando desde SharePoint local, indique a los usuarios que creen sitios de grupo de SharePoint para la colaboración.
- Si su organización ha implementado Microsoft Teams, indique a los usuarios que creen un equipo cuando necesiten un espacio de colaboración.

Esto ayuda a evitar la confusión si los usuarios no están familiarizados con el modo en que los grupos se relacionan con sus servicios relacionados. Para obtener más información acerca de cómo hablar con los usuarios sobre grupos, vea [explicando los grupos de Microsoft 365 a los usuarios](../admin/create-groups/explain-groups-knowledge-worker.md).

## <a name="key-governance-capabilities-and-licensing-requirements"></a>Capacidades de administración de claves y requisitos de licencia

Las capacidades de gobierno para colaboración en Microsoft 365 incluyen características en Microsoft 365, Teams, SharePoint y Azure Active Directory.

| Funcionalidad o característica | Description | Licencias |
|:----------------------|:------------|:----------|
|Uso compartido de equipos y sitios|Controle si se pueden compartir equipos, grupos y sitios con personas externas a la organización.|Microsoft 365 E5 o E3|
|Permitir/bloquear dominio|Restringir el uso compartido con personas de fuera de la organización a personas de dominios específicos.|Microsoft 365 E5 o E3|
|Creación de sitios sin intervención del administrador|Permitir o impedir que los usuarios creen sus propios sitios de SharePoint.|Microsoft 365 E5 o E3|
|Uso compartido de sitios y archivos restringidos|Restrinja el uso compartido de sitios, archivos y carpetas a los miembros de un grupo de seguridad específico.|Microsoft 365 E5 o E3|
|Creación de grupos restringidos|Restringir la creación de grupos y equipos a los miembros de un grupo de seguridad específico.|Microsoft 365 E5 o E3 con Azure AD Premium o con licencias de Azure AD Basic EDU|
|Directiva de nomenclatura de grupos|Aplique prefijos o sufijos en los nombres de grupo y de equipo.|Microsoft 365 E5 o E3 con Azure AD Premium o con licencias de Azure AD Basic EDU|
|Directiva de expiración de grupos|Establezca grupos y equipos inactivos para que expiren y se eliminen después de un período de tiempo especificado.|Microsoft 365 E5 o E3 con licencias de Azure AD Premium|
|Acceso de invitado por grupo|Permitir o impedir el uso compartido de grupos y usuarios con personas de fuera de la organización por grupo.|Microsoft 365 E5 o E3|

## <a name="create-your-governance-plan"></a>Crear el plan de gobierno

Siga estos pasos básicos para crear el plan de gobierno:

1. Considere los objetivos y procesos clave del negocio: [cree el plan de gobierno](collaboration-governance-first.md) para satisfacer las necesidades de su empresa.
2. Comprenda la configuración de Services- [Settings en grupos y SharePoint](groups-sharepoint-governance.md) interactúan entre sí, al igual que las [Opciones de configuración en grupos, SharePoint y Teams](groups-sharepoint-teams-governance.md) y [otros servicios](groups-services-interactions.md). Asegúrese de comprender estas interacciones cuando planifique su estrategia de gobierno.
3. Planeación de la administración del acceso de usuarios: Planee [el nivel de acceso que desea para conceder a los usuarios en grupos, SharePoint y Teams](groups-teams-access-governance.md).
4. Planeación de la administración de la configuración de cumplimiento: Revise las [Opciones de cumplimiento disponibles para Microsoft 365 Groups, Teams y SharePoint Collaboration](groups-teams-compliance-governance.md).
5. Planeación de la administración de comunicaciones: Revise las [Opciones de gobierno de comunicaciones disponibles para escenarios de colaboración](groups-teams-communication-governance.md).
6. Planeación del gobierno de la organización y el ciclo de vida: elija [las directivas que desea usar para la creación, el nombre, la expiración y el archivado de grupos y equipos](plan-organization-lifecycle-governance.md). Además, comprenda las [Opciones de finalización del ciclo de vida para grupos, equipos y Yammer](end-life-cycle-groups-teams-sites-yammer.md)

![Ilustración de los pasos recomendados de gobierno](../media/collaboration-governance-steps.png)

## <a name="training-for-administrators"></a>Formación para administradores

Estos módulos de aprendizaje de Microsoft le ayudarán a obtener información sobre las características de colaboración en Teams y SharePoint.

#### <a name="teams"></a>Teams

|Aprendizaje|Administración de la colaboración en grupo con Microsoft Teams|
|:---|:---|
|![Icono de formación de Microsoft Teams](../media/manage-team-collaboration-with-microsoft-teams.svg)|Administración de la colaboración en grupo con Microsoft Teams le presenta las características y funciones de Microsoft Teams, el núcleo central para la colaboración en grupo de Microsoft 365. Aprenderá cómo puede usar Teams para facilitar el trabajo en equipo y la comunicación dentro de la organización, tanto en un entorno local como externo, en dispositivos muy diversos, desde equipos de escritorio a tabletas y teléfonos, a la vez que aprovecha toda la funcionalidad enriquecida de las aplicaciones de Office 365. Comprenderá cómo Teams ofrece un entorno completo y flexible para la colaboración en aplicaciones y dispositivos. Esta ruta de aprendizaje puede ayudarle a preparar el certificado Microsoft 365 Certified: Teams Administrator Associate.<br><br>2 módulos de la ruta de acceso de 17 horas/min de aprendizaje: 5|

> [!div class="nextstepaction"]
> [Iniciar >](https://docs.microsoft.com/learn/modules/m365-teams-collab-prepare-deployment/introduction/)

#### <a name="sharepoint"></a>SharePoint

|Aprendizaje|Colaborar con SharePoint en Microsoft 365|
|:---|:---|
|![Icono de aprendizaje de SharePoint](../media/collaborate-with-sharepoint-in-microsoft-365.svg)|Administrar el contenido compartido con Microsoft SharePoint le ofrece una introducción a las características y funciones de SharePoint y cómo funciona con Microsoft 365. Obtendrá información sobre los distintos tipos de sitios de SharePoint, incluidos los sitios concentradores, así como la protección de la información, la creación de informes y la supervisión. También obtendrá información sobre cómo emplear el uso compartido de archivos y carpetas de SharePoint para optimizar la colaboración, cómo compartir archivos externamente y cómo administrar sitios de SharePoint en el centro de administración de SharePoint. Esta ruta de aprendizaje puede ayudarle a preparar el certificado Microsoft 365 Certified: Teamwork Administrator Associate.<br><br>1 h 14 para la ruta de aprendizaje: 4 módulos|

> [!div class="nextstepaction"]
> [Iniciar >](https://docs.microsoft.com/learn/modules/m365-teams-sharepoint-plan-sharepoint/introduction/)

## <a name="training-for-end-users"></a>Entrenamiento para usuarios finales

Estos módulos de formación pueden ayudar a sus usuarios a usar equipos, grupos y SharePoint para la colaboración en Microsoft 365.

|Teams|SharePoint|
|:---|:---|
|![Configurar y personalizar el icono de formación de su equipo](../media/set-up-customize-team-training.png)<br>**[Configurar y personalizar el equipo](https://support.microsoft.com/office/702a2977-e662-4038-bef5-bdf8ee47b17b)**|![Icono de aprendizaje para compartir y sincronizar de SharePoint](../media/sharepoint-share-sync-training.png)<br>**[Compartir y sincronizar](https://support.microsoft.com/office/98cb2ff2-c27e-42ea-b055-c2d895f8a5de)**|
|![Icono de formación para cargar y buscar archivos en Microsoft Teams](../media/smc-teams-upload-find-files-training.png)<br>**[Cargar y buscar archivos](https://support.microsoft.com/office/57b669db-678e-424e-b0a0-15d19215cb12)**||
|![Icono colaborar en equipos y canales](../media/teams-collaborate-channels-training.png)<br>**[Colaborar en equipos y canales](https://support.microsoft.com/office/c3d63c10-77d5-4204-a566-53ddcf723b46)**|||

## <a name="illustrations"></a>Ilustraciones

Estas ilustraciones le ayudarán a comprender cómo los grupos y equipos interactúan con otros servicios en Microsoft 365 y qué características de gobierno y cumplimiento están disponibles para ayudarle a administrar estos servicios en su organización.

### <a name="groups-in-microsoft-365-for-it-architects"></a>Grupos en Microsoft 365 para arquitectos de TI
Lo que necesitan saber los arquitectos de TI sobre los grupos en Microsoft 365

|**Item**|**Descripción**|
|:-----|:-----|
|[![Imagen en miniatura para la infografía de grupos](../downloads/msft-m365-groups-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) <br/> [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-groups.vsdx) <br> Actualizado en junio de 2019|Estas ilustraciones detallan los diferentes tipos de grupos, cómo se crean y administran, y algunas recomendaciones para el gobierno de estos.|

### <a name="microsoft-teams-and-related-productivity-services-in-microsoft-365-for-it-architects"></a>Microsoft Teams y servicios de productividad relacionados de Microsoft 365 para arquitectos de TI
La arquitectura lógica de los servicios de productividad en Microsoft 365, una de las más destacadas gracias a Microsoft Teams.

|**Item**|**Descripción**|
|:-----|:-----|
|[![Imagen en miniatura para el póster de la arquitectura lógica de Teams](../downloads/msft-teams-logical-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-teams-logical-architecture.pdf) <br/> [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-teams-logical-architecture.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-teams-logical-architecture.vsdx)  <br>Actualizado en abril de 2019   |Microsoft proporciona un conjunto de servicios de productividad que funcionan en conjunto para proporcionar experiencias de colaboración con funcionalidades de gobierno, seguridad y cumplimiento. <br/> <br/>Esta serie de ilustraciones proporciona una vista de la arquitectura lógica de los servicios de productividad para arquitectos empresariales, que es una de las más destacadas gracias a Microsoft Teams.|

### <a name="microsoft-365-information-protection-and-compliance-capabilities"></a>Capacidades de protección y cumplimiento de la información de Microsoft 365

Microsoft 365 incluye un amplio conjunto de capacidades de protección y cumplimiento de la información. Junto con las herramientas de productividad de Microsoft, estas capacidades están diseñadas para ayudar a las organizaciones a colaborar en tiempo real y adherirse a los marcos de cumplimiento normativo más estrictos. 

Este conjunto de ilustraciones utiliza una de las industrias más reguladas, servicios financieros, para demostrar cómo se pueden aplicar estas capacidades para cumplir los requisitos normativos comunes. No dude en adaptar estas ilustraciones a su propio uso. 


| Item | Descripción |
|:-----|:-----|
|[![Póster de modelo: Microsoft 365 de protección de la información y capacidades de cumplimiento](../media/solutions-architecture-center/m365-compliance-illustrations-thumb.png)](https://download.microsoft.com/download/3/a/6/3a6ab1a3-feb0-4ee2-8e77-62415a772e53/m365-compliance-illustrations.pdf) <br/> Inglés: descargar [como una](https://download.microsoft.com/download/3/a/6/3a6ab1a3-feb0-4ee2-8e77-62415a772e53/m365-compliance-illustrations.pdf) descarga de PDF \| [como un](https://download.microsoft.com/download/3/a/6/3a6ab1a3-feb0-4ee2-8e77-62415a772e53/m365-compliance-illustrations.vsdx) archivo de Visio   <br/> Japonés: descargar [como una](https://download.microsoft.com/download/6/f/1/6f1a7d0e-dd8e-442e-b073-8e94327ae4f8/m365-compliance-illustrations.pdf) descarga de PDF \| [como un](https://download.microsoft.com/download/6/f/1/6f1a7d0e-dd8e-442e-b073-8e94327ae4f8/m365-compliance-illustrations.vsdx) archivo de Visio   <br/> Se actualizó el 2020 de noviembre|Incluya <ul><li>  Protección de la información y prevención de pérdida de datos de Microsoft</li><li>Directivas de retención y etiquetas de retención </li><li>Barreras de la información</li><li>Cumplimiento de las comunicaciones</li><li>Riesgo de Insider</li><li>Recopilación de datos de terceros</li>|

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
