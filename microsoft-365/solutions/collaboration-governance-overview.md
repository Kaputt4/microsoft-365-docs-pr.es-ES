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
description: Obtenga información sobre cómo gobernar características relacionadas en grupos de Microsoft 365, Teams, SharePoint y Yammer.
ms.openlocfilehash: 2319a0f5b8c74925569d00eb781d247fe61a5a76
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/09/2020
ms.locfileid: "49613037"
---
# <a name="what-is-collaboration-governance"></a>¿Qué es el gobierno de colaboración?

El gobierno de colaboración es la forma de administrar el acceso de los usuarios a los recursos, el cumplimiento de los estándares empresariales y garantizar la seguridad de los datos.

Hoy en día, las organizaciones usan un conjunto de herramientas variado. Está el equipo de desarrolladores que usa el chat del equipo, los ejecutivos que envían correo electrónico y toda la organización que se conecta a través de redes sociales empresariales. Hay varias herramientas de colaboración en uso porque cada grupo es único y tiene sus propias necesidades funcionales y estilo de trabajo. Algunos solo usarán el correo electrónico, mientras que otros se encontrarán principalmente en el chat. 

Si los usuarios creen que las herramientas proporcionadas por IT no se ajustan a sus necesidades, es probable que descarguen su aplicación de consumidor favorita que admite sus escenarios. Aunque este proceso permite que los usuarios se inicien rápidamente, da lugar a una experiencia de usuario frustrante en toda la organización con varios inicios de sesión, dificultades para compartir y ningún lugar único para ver contenido. Este concepto se conoce como "Ti de instantánea" y supone un riesgo importante para las organizaciones. Reduce la capacidad de administrar uniformemente el acceso de los usuarios, garantizar la seguridad y las necesidades de cumplimiento del servicio.

Servicios como los grupos de Microsoft 365, Teams y Yammer permiten a los usuarios y reducen el riesgo de ti de instantáneas al proporcionar las herramientas necesarias para colaborar. Microsoft 365 tiene un amplio conjunto de herramientas para implementar las capacidades de gobierno que su organización pueda necesitar. 

![Gráfico que muestra las opciones de gobierno de colaboración en Microsoft 365](../media/collaboration-governance-overview.png)

Esta serie de artículos le ayudará a comprender cómo interactúan los grupos, los equipos y la configuración de SharePoint, qué capacidades de gobierno están disponibles y cómo crear e implementar un plan de gobierno para las características de colaboración de Microsoft 365.

## <a name="what-are-microsoft-365-groups"></a>¿Qué son los grupos de Microsoft 365?

Los grupos de Microsoft 365 le permiten elegir un conjunto de personas con las que desea colaborar y configurar fácilmente una colección de recursos para que esas personas las compartan. Agregar miembros al grupo concede automáticamente los permisos necesarios a todos los activos proporcionados por el grupo. Tanto Teams como Yammer usan grupos de Microsoft 365 para administrar su pertenencia.

Los grupos de Microsoft 365 incluyen un conjunto de recursos vinculados que los usuarios pueden usar para la comunicación y la colaboración. Los grupos siempre incluyen un sitio de SharePoint, Planner, un área de trabajo de Power BI, un buzón y un calendario, y Stream. Según cómo cree el grupo, opcionalmente puede agregar otros servicios como Teams, Yammer y Project.

![Diagrama que muestra Grupos de Microsoft 365 y servicios relacionados](../media/microsoft-365-groups-hub-spoke.png)

|Recurso|Descripción|
|:------|:----------|
|[Calendario](https://support.office.com/article/schedule-a-meeting-on-a-group-calendar-in-outlook-0cf1ad68-1034-4306-b367-d75e9818376a)|Para programar eventos relacionados con el grupo|
|[Bandeja de entrada](https://support.office.com/article/have-a-group-conversation-in-outlook-a0482e24-a769-4e39-a5ba-a7c56e828b22)|Para las conversaciones de correo electrónico entre los miembros del grupo. Esta bandeja de entrada tiene una dirección de correo electrónico y se puede configurar para aceptar mensajes de personas fuera del grupo e incluso fuera de la organización, de forma muy parecido a una lista de distribución tradicional.|
|[Bloc de notas de OneNote](https://support.office.com/article/get-started-with-onenote-e768fafa-8f9b-4eac-8600-65aa10b2fe97)|Para recopilar ideas, investigación e información|
|[Planificador](https://support.office.com/article/microsoft-planner-help-4a9a13c6-3adf-4a60-a6fc-15c0b15e16fc)|Para asignar y administrar tareas de proyecto entre los miembros del grupo|
|[Área de trabajo de Power BI](https://docs.microsoft.com/power-bi/collaborate-share/service-new-workspaces)|Un espacio de colaboración de datos con paneles e informes|
|[Proyecto y plan de desarrollo](https://support.microsoft.com/project)|Herramientas de administración de proyectos basadas en web|
|[Sitio de grupo de SharePoint](https://support.office.com/article/what-is-a-sharepoint-team-site-75545757-36c3-46a7-beed-0aaa74f0401e)|Un repositorio central de información, vínculos y contenido relacionado con el grupo|
|[Secuencia](https://support.microsoft.com/microsoft-stream)|Un servicio de streaming de vídeo|
|[Teams](https://support.microsoft.com/teams)|Un área de trabajo basada en chat en Microsoft 365|
|[Grupo de Yammer](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2)|Un lugar común para tener conversaciones y compartir información|

Grupos de Microsoft 365 incluye una variedad de controles de gobierno, incluida una directiva de expiración, convenciones de nomenclatura y una directiva de palabras bloqueadas, para ayudarle a administrar grupos en su organización. Dado que los grupos controlan la pertenencia y el acceso a este conjunto de recursos, la administración de grupos es una parte clave de la administración de la colaboración en Microsoft 365.

## <a name="define-a-collaboration-strategy-for-your-organization"></a>Definir una estrategia de colaboración para su organización

Hay varios lugares para colaborar y tener conversaciones en Microsoft 365. Comprender dónde pueden iniciar las conversaciones los usuarios puede ayudarle a definir una estrategia de comunicación.

Microsoft 365 admite tres métodos de comunicación principales:

- Outlook: colaboración a través del correo electrónico con un calendario y una bandeja de entrada de un grupo compartido
- Microsoft Teams: un área de trabajo basada en chat persistente donde puede tener conversaciones informales, en tiempo real, en torno a una variedad de temas, organizadas por subgrupos específicos
- Yammer: experiencia social empresarial para la colaboración

![Diagrama que muestra cuándo usar Teams, Yammer y Outlook](../media/inner-loop-outer-loop.png)

- Teams: área de trabajo basada en chat (colaboración de alta velocidad): bucle interno
  - Creado para la colaboración con las personas con las que trabajan los usuarios todos los días
  - Pone información al alcance de los usuarios en una sola experiencia
  - Agregar fichas, conectores y bots
  - Chat en directo, conferencias de audio y vídeo, reuniones grabadas

- Yammer: conectarse a través de la organización (social empresarial): bucle externo
  - Comunidades de prácticas: grupos funcionales cruzados de personas que comparten un interés o experiencia comunes, pero que no necesariamente trabajan conjuntamente de forma diaria
  - Conexión de liderazgo, comunidades de aprendizaje, comunidades basadas en roles

- Buzón de correo y calendario (colaboración basada en correo electrónico)
  - Se usa para la comunicación dirigida con un grupo de personas
  - Calendario compartido para reuniones con otros miembros del grupo
 
A medida que determine cómo desea usar las características de colaboración en Microsoft 365, tenga en cuenta estos métodos de comunicación y que los usuarios probablemente usarán en diferentes escenarios.

> [!NOTE]
> Cuando se crea un nuevo grupo de Office 365 a través de Yammer o Teams, el grupo no está visible en Outlook ni en la libreta de direcciones porque la comunicación principal entre esos usuarios se produce en sus respectivos clientes. Los grupos de Yammer no se pueden conectar a Teams.


## <a name="best-practices"></a>Procedimientos recomendados

Al iniciar el proceso de planeación del gobierno, tenga en cuenta estos procedimientos recomendados:

- **Hable con los usuarios:** identifique a los usuarios más grandes de las características de colaboración y reúnase con ellos para comprender sus requisitos empresariales principales y usar escenarios de casos.

- **Equilibrar los riesgos y los beneficios:** revise sus necesidades empresariales, reglamentarias, legales y de cumplimiento, y planee una solución que se optimice para todos los resultados.

- Adaptarse a diferentes organizaciones y distintos tipos de contenido **y escenarios:** tenga en cuenta las diferentes necesidades para distintos grupos o departamentos y diferentes tipos de contenido, como contenido de intranet frente al contenido de OneDrive de un usuario.

- **Alinearse con las prioridades empresariales:** los objetivos empresariales le ayudarán a definir cuánto tiempo y energía necesita invertir en el gobierno.

- **Insertar decisiones de gobierno directamente en** las soluciones que cree: muchas decisiones de gobierno se pueden implementar al activar o desactivar las características de Microsoft 365.

- **Refuerce la** formación: adapte soluciones como las rutas de aprendizaje de [Microsoft 365](https://docs.microsoft.com/office365/customlearning) para garantizar que las expectativas específicas de su organización se refuercen con la formación proporcionada por Microsoft.

- **Tener una estrategia** para comunicar directivas y directrices de gobierno en su organización: cree un Centro de adopción de Microsoft 365 en un sitio de comunicación de SharePoint para comunicar directivas y procedimientos.

- Defina roles y **responsabilidades:** identifique su equipo principal de gobierno y trabaje primero con las decisiones clave de gobierno sobre el aprovisionamiento y la nomenclatura y el acceso externo y, a continuación, trabaje en las decisiones restantes.

- **Revise sus decisiones a medida que cambie la tecnología y la** empresa: reúnase periódicamente para revisar las nuevas capacidades y las nuevas expectativas empresariales.

Para ver más de cerca estos procedimientos, lea [Crear el plan de gobierno de colaboración.](collaboration-governance-first.md)

## <a name="end-user-impact-and-change-management"></a>Impacto del usuario final y administración de cambios

Dado que los grupos y equipos se pueden crear de varias maneras, se recomienda formar a los usuarios para que usen el método que mejor se adapte a su organización:

- Si su organización realiza la mayor parte de su comunicación mediante correo electrónico, indique a los usuarios que creen grupos en Outlook.
- Si su organización usa en gran medida SharePoint o está migrando desde SharePoint local, indique a los usuarios que creen sitios de grupo de SharePoint para la colaboración.
- Si su organización ha implementado Teams, indique a los usuarios que creen un equipo cuando necesiten un espacio de colaboración.

Esto ayuda a evitar confusiones si los usuarios no están familiarizados con la relación de los grupos con sus servicios relacionados. Para obtener más información acerca de cómo hablar con los usuarios sobre los grupos, consulte Explicar grupos de [Microsoft 365 a los usuarios.](../admin/create-groups/explain-groups-knowledge-worker.md)

## <a name="key-governance-capabilities-and-licensing-requirements"></a>Capacidades de gobierno clave y requisitos de licencias

Las capacidades de gobierno para la colaboración en Microsoft 365 incluyen características de Microsoft 365, Teams, SharePoint y Azure Active Directory.

| Funcionalidad o característica | Description | Licencias |
|:----------------------|:------------|:----------|
|Uso compartido de equipos y sitios|Controle si los equipos, grupos y sitios se pueden compartir con personas de fuera de su organización.|Microsoft 365 E5 o E3|
|Dominio permitido/bloqueado|Restringir el uso compartido con personas fuera de la organización a personas de dominios específicos.|Microsoft 365 E5 o E3|
|Creación de sitios sin intervención del administrador|Permitir o impedir que los usuarios creen sus propios sitios de SharePoint.|Microsoft 365 E5 o E3|
|Uso compartido restringido de sitios y archivos|Restringir el uso compartido de sitios, archivos y carpetas a los miembros de un grupo de seguridad específico.|Microsoft 365 E5 o E3|
|Creación de grupos restringidos|Restringir la creación de equipos y grupos a los miembros de un grupo de seguridad específico.|Microsoft 365 E5 o E3 con licencias de Azure AD Premium o Azure AD Basic EDU|
|Directiva de nomenclatura de grupos|Aplicar prefijos o sufijos en los nombres de grupo y equipo.|Microsoft 365 E5 o E3 con licencias de Azure AD Premium o Azure AD Basic EDU|
|Directiva de expiración de grupo|Establecer grupos inactivos y equipos para que expiren y se eliminen después de un período de tiempo especificado.|Microsoft 365 E5 o E3 con licencias de Azure AD Premium|
|Acceso de invitado por grupo|Permitir o impedir el uso compartido de equipos y grupos con personas ajenas a la organización por grupo.|Microsoft 365 E5 o E3|

## <a name="collaboration-governance-planning-step-by-step"></a>Planeación paso a paso de gobierno de colaboración

Siga estos pasos básicos para crear su plan de gobierno:

1. Tenga en cuenta los objetivos y procesos empresariales [clave: cree su plan de gobierno](collaboration-governance-first.md) para satisfacer las necesidades de su empresa.
2. Comprender la configuración de los servicios: la configuración en grupos y [SharePoint](groups-sharepoint-governance.md) interactúan entre sí, al igual que la configuración en [grupos, SharePoint](groups-sharepoint-teams-governance.md) y Teams y [otros servicios.](groups-services-interactions.md) Asegúrese de comprender estas interacciones al planear su estrategia de gobierno.
3. Planear la administración del acceso de usuarios: planee el nivel de acceso que desea conceder a los usuarios en [grupos, SharePoint y Teams.](groups-teams-access-governance.md)
4. Planee la administración de la configuración de cumplimiento: revise las opciones de cumplimiento disponibles para grupos de [Microsoft 365, Teams y colaboración de SharePoint.](groups-teams-compliance-governance.md)
5. Plan para administrar las comunicaciones: revise las opciones de gobierno de [comunicaciones disponibles para escenarios de colaboración.](groups-teams-communication-governance.md)
6. Planifique el gobierno de la organización y del ciclo de vida: elija las directivas que desea usar para la creación, la nomenclatura, la expiración y el archivado de grupos [y equipos.](plan-organization-lifecycle-governance.md) Además, comprenda las opciones de fin del ciclo [de vida para grupos, equipos y Yammer](end-life-cycle-groups-teams-sites-yammer.md)

![Ilustración de pasos de gobierno recomendados](../media/collaboration-governance-steps.png)

## <a name="training-for-administrators"></a>Formación para administradores

Estos módulos de aprendizaje de Microsoft Learn pueden ayudarle a aprender las características de colaboración en Teams y SharePoint.

#### <a name="teams"></a>Teams

|Aprendizaje:|Administración de la colaboración en grupo con Microsoft Teams|
|:---|:---|
|![Icono de aprendizaje de Teams](../media/manage-team-collaboration-with-microsoft-teams.svg)|Administración de la colaboración en grupo con Microsoft Teams le presenta las características y funciones de Microsoft Teams, el núcleo central para la colaboración en grupo de Microsoft 365. Aprenderá cómo puede usar Teams para facilitar el trabajo en equipo y la comunicación dentro de la organización, tanto en un entorno local como externo, en dispositivos muy diversos, desde equipos de escritorio a tabletas y teléfonos, a la vez que aprovecha toda la funcionalidad enriquecida de las aplicaciones de Office 365. Comprenderá cómo Teams ofrece un entorno completo y flexible para la colaboración en aplicaciones y dispositivos. Esta ruta de aprendizaje puede ayudarle a preparar el certificado Microsoft 365 Certified: Teams Administrator Associate.<br><br>2 horas 17 minutos - Ruta de aprendizaje - 5 módulos|

> [!div class="nextstepaction"]
> [Inicie >](https://docs.microsoft.com/learn/modules/m365-teams-collab-prepare-deployment/introduction/)

#### <a name="sharepoint"></a>SharePoint

|Aprendizaje:|Colaborar con SharePoint en Microsoft 365|
|:---|:---|
|![Icono de aprendizaje de SharePoint](../media/collaborate-with-sharepoint-in-microsoft-365.svg)|Administrar el contenido compartido con Microsoft SharePoint le ofrece una introducción a las características y funciones de SharePoint y cómo funciona con Microsoft 365. Obtendrá información sobre los distintos tipos de sitios de SharePoint, incluidos los sitios concentradores, así como la protección de la información, la creación de informes y la supervisión. También obtendrá información sobre cómo emplear el uso compartido de archivos y carpetas de SharePoint para optimizar la colaboración, cómo compartir archivos externamente y cómo administrar sitios de SharePoint en el centro de administración de SharePoint. Esta ruta de aprendizaje puede ayudarle a preparar el certificado Microsoft 365 Certified: Teamwork Administrator Associate.<br><br>1 hora 14 minutos - Ruta de aprendizaje - 4 módulos|

> [!div class="nextstepaction"]
> [Inicie >](https://docs.microsoft.com/learn/modules/m365-teams-sharepoint-plan-sharepoint/introduction/)

## <a name="training-for-end-users"></a>Entrenamiento para usuarios finales

Estos módulos de aprendizaje pueden ayudar a los usuarios a usar Teams, grupos y SharePoint para la colaboración en Microsoft 365.

|Teams|SharePoint|
|:---|:---|
|![Configurar y personalizar el icono de aprendizaje de equipo](../media/set-up-customize-team-training.png)<br>**[Configurar y personalizar el equipo](https://support.microsoft.com/office/702a2977-e662-4038-bef5-bdf8ee47b17b)**|![Icono de aprendizaje para compartir y sincronizar de SharePoint](../media/sharepoint-share-sync-training.png)<br>**[Compartir y sincronizar](https://support.microsoft.com/office/98cb2ff2-c27e-42ea-b055-c2d895f8a5de)**|
|![Icono de aprendizaje de carga y búsqueda de archivos de Teams](../media/smc-teams-upload-find-files-training.png)<br>**[Cargar y buscar archivos](https://support.microsoft.com/office/57b669db-678e-424e-b0a0-15d19215cb12)**||
|![Icono Colaborar en equipos y canales](../media/teams-collaborate-channels-training.png)<br>**[Colaborar en equipos y canales](https://support.microsoft.com/office/c3d63c10-77d5-4204-a566-53ddcf723b46)**|||

## <a name="illustrations"></a>Ilustraciones

Estas ilustraciones le ayudarán a comprender cómo interactúan los grupos y equipos con otros servicios de Microsoft 365 y qué características de cumplimiento y gobierno están disponibles para ayudarle a administrar estos servicios en su organización.

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

### <a name="microsoft-365-information-protection-and-compliance-capabilities"></a>Capacidades de cumplimiento y protección de la información de Microsoft 365

Microsoft 365 incluye un amplio conjunto de capacidades de protección de la información y cumplimiento. Junto con las herramientas de productividad de Microsoft, estas capacidades están diseñadas para ayudar a las organizaciones a colaborar en tiempo real a la vez que se cumplen los estrictos marcos de cumplimiento normativo. 

Este conjunto de ilustraciones usa una de las industrias más reguladas, los servicios financieros, para demostrar cómo se pueden aplicar estas capacidades para cumplir los requisitos normativos comunes. Siéntase libre de adaptar estas ilustraciones para su propio uso. 


| Elemento | Descripción |
|:-----|:-----|
|[![Póster modelo: capacidades de protección y cumplimiento de la información de Microsoft 365](../media/solutions-architecture-center/m365-compliance-illustrations-thumb.png)](https://download.microsoft.com/download/3/a/6/3a6ab1a3-feb0-4ee2-8e77-62415a772e53/m365-compliance-illustrations.pdf) <br/> Inglés: [Descargar como PDF](https://download.microsoft.com/download/3/a/6/3a6ab1a3-feb0-4ee2-8e77-62415a772e53/m365-compliance-illustrations.pdf)  \| [Descargar como Visio](https://download.microsoft.com/download/3/a/6/3a6ab1a3-feb0-4ee2-8e77-62415a772e53/m365-compliance-illustrations.vsdx) <br/> Japonés: [Descargar como PDF](https://download.microsoft.com/download/6/f/1/6f1a7d0e-dd8e-442e-b073-8e94327ae4f8/m365-compliance-illustrations.pdf)  \| [Descargar como Visio](https://download.microsoft.com/download/6/f/1/6f1a7d0e-dd8e-442e-b073-8e94327ae4f8/m365-compliance-illustrations.vsdx) <br/> Actualizado en noviembre de 2020|Incluye: <ul><li>  Protección de la información y prevención de la pérdida de datos de Microsoft</li><li>Directivas y etiquetas de retención </li><li>Barreras de información</li><li>Cumplimiento de comunicaciones</li><li>Riesgo de Insider</li><li>Ingesta de datos de terceros</li>|

## <a name="conference-sessions"></a>Sesiones de conferencia

Vea estas sesiones de conferencia para obtener más información sobre el gobierno de Grupos de Microsoft 365 y Teams.

**Conceptos básicos**

Conozca los conceptos básicos y las nuevas innovaciones de los Grupos de Microsoft 365, incluidos la administración y el gobierno a escala, los procedimientos recomendados para impulsar el uso y la adopción, y el autoservicio.

- [Adoptar grupos de Microsoft 365](https://www.youtube.com/watch?v=dAamBF1gb7M)

**Gobierno**

Obtenga información sobre cómo configurar el ciclo de vida de expiración de los grupos, las directivas de nomenclatura, las etiquetas de clasificación, la colaboración con invitados externos y administrar los permisos de creación de grupos.

- [Transformar la colaboración y la sombra de LA INFORMACIÓN con grupos de Office 365](https://www.youtube.com/watch?v=Bhf_bKx3lAg)

**Ejemplo de cliente**

Vea un ejemplo en segundo plano de cómo los Grupos de Microsoft 365, SharePoint, Teams y Yammer trabajan juntos para proporcionar una plataforma de colaboración global.

- [Buscar el punto ideal de colaboración con Grupos de Office 365, SharePoint, Teams y Yammer](https://www.youtube.com/watch?v=Rx9eVwqXeQk)
