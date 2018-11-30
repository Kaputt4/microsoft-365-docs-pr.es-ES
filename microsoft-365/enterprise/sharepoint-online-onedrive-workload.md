---
title: Implementar SharePoint Online y OneDrive para la Empresa para Microsoft 365 Enterprise
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Se detalla el proceso de planeación, implementación y aumento del valor de SharePoint Online en Microsoft 365 Enterprise en toda la organización.
ms.openlocfilehash: 7a9fc1733c64b3f639d2de0b5b64e20df60e04a9
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2018
ms.locfileid: "26871175"
---
# <a name="deploy-sharepoint-online-for-microsoft-365-enterprise"></a>Implementar SharePoint Online para Microsoft 365 Enterprise


SharePoint Online y Microsoft Teams es cómo se realiza el almacenamiento y uso compartido de archivos, la administración de contenido y la colaboración, y es un elemento clave del valor diseñado para trabajo en equipo de Microsoft 365 Enterprise. 

SharePoint Online también cuenta con funcionalidades de seguridad avanzadas que incluyen control y permisos de acceso y cifrado en vuelo y en reposo. La seguridad de SharePoint Online es un elemento clave del valor de seguridad Inteligente de Microsoft 365 Enterprise.

Si es nuevo en SharePoint Online, vea [SharePoint Online](https://products.office.com/sharepoint/sharepoint-online-collaboration-software) e [Introducción a SharePoint](https://support.office.com/article/Get-started-with-SharePoint-3a26444b-08c5-46ad-b80a-cda82b11b27b#ID0EAABAAA=Basics).

Los pasos y fases siguientes le servirán como guía en el proceso de planeamiento del rol de SharePoint Online en su organización, en la incorporación de la organización mediante una serie de implementaciones progresivas y en el impulso del uso y su valor para los usuarios finales. Siga estas instrucciones de implementación solo después de completar la [infraestructura básica](deploy-foundation-infrastructure.md). 

>[!Note]
>Para implementar OneDrive para la Empresa para Microsoft 365 Enterprise, vea la [Guía de OneDrive para empresas](https://docs.microsoft.com/onedrive/plan-onedrive-enterprise).
>

## <a name="phase-1-envision"></a>Fase 1: Planear
En esta fase, reunirá a las personas para la implementación de SharePoint Online y OneDrive para la Empresa y determinará cómo las usará su organización para satisfacer sus necesidades empresariales.

### <a name="step-1-gather-your-sharepoint-online-deployment-members"></a>Paso 1: Reunir a los miembros de la implementación de SharePoint Online

Para conseguir una implementación correcta de SharePoint Online y OneDrive para la Empresa basada en la [infraestructura básica de Microsoft 365 Enterprise](deploy-foundation-infrastructure.md), necesita reunir a las personas adecuadas para que proporcionen comentarios. Entre las personas clave, se incluyen los responsables de toma de decisiones empresariales, el personal de TI (como los arquitectos y los implementadores) y los defensores de los usuarios finales. 

Estos tres grupos garantizan que la implementación incluya consideraciones que aborden las necesidades empresariales, los aspectos técnicos de la migración de carpetas y documentos y la seguridad, y que se convertirá en algo que usarán los usuarios habituales.

#### <a name="result"></a>Resultado

Una lista de personas que representan los aspectos empresariales, técnicos y de usuario final de la organización.

### <a name="step-2-determine-and-prioritize-your-sharepoint-online-business-scenarios"></a>Paso 2: Determinar y priorizar los escenarios empresariales de SharePoint Online

SharePoint Online puede usarse con distintos fines. Necesita determinar qué fines se corresponden con sus necesidades empresariales. Su objetivo es que SharePoint Online satisfaga las necesidades de almacenamiento y uso compartido de documentos, de administración de contenidos y de colaboración de los equipos, la división o toda la organización. 

Vea la lista de escenarios y funciones en [SharePoint Online](https://products.office.com/sharepoint/sharepoint-online-collaboration-software).

Los siguientes pilares empresariales pueden abordar las necesidades de la organización:

|||
|:-----|:-----|
| Compartir y colaborar | Aproveche las ventajas de los sitios de grupo, sitios de colaboración y la sincronización. |
| Informar e interactuar | La información que viene en el futuro. |
| Transformar | Se utiliza Flow para crear un flujo de trabajo o tienda. |
| Aprovechar el conocimiento colectivo | Se utiliza la búsqueda para proporcionar los resultados que quiere en su organización. |
| Proteger | Garantiza que su organización está protegida y cuenta con el cumplimiento normativo correcto. |
| Externo/Desarrollar | Permite que su organización desarrolle soluciones y aplicaciones personalizadas mediante SharePoint Framework. |
|||

Vea [Administrador de SharePoint Online](https://docs.microsoft.com/sharepoint/sharepoint-online) para obtener recursos sobre cómo configurar SharePoint Online según sus necesidades.

Una forma de ver los beneficios de SharePoint Online es examinar cómo interactúan actualmente las personas, un equipo, una división o toda la organización y luego encontrar un escenario apropiado que ofrezca formas más fáciles de almacenar y compartir archivos de colaboración. Tenga en cuenta que [Microsoft Teams](teams-workload.md) puede ser la mejor opción para algunos de los escenarios.

SharePoint Online facilita estos escenarios empresariales estratégicos para Microsoft 365 Enterprise:

- Comunicarse con su equipo para mantenerse informado, solicitar comentarios y facilitar la cohesión y el consenso
- Aprovechar el conocimiento colectivo
- Proporcionar recursos a los usuarios para transformar los procesos empresariales
- Conformar la cultura corporativa
- Administrar proyectos, tareas y fechas límite para cumplir con sus objetivos de negocio
- Implicar a los Firstline Workers para facilitar su transformación digital
- Comprender sus hábitos de trabajo para mejorar su influencia e impacto
- Comunicarse con partners, compañeros y clientes
- Almacenar y compartir archivos, tanto dentro como fuera de la organización, para trabajar de forma fluida más allá de los límites organizativos
- Trabajar de forma segura en el dispositivo en cualquier momento y lugar para mejorar la productividad, a la vez que mantiene un estilo de trabajo flexible
- Proteger su información y reducir el riesgo de pérdida de datos
- Apoyar a su organización con mayor privacidad y cumplimiento normativo para ajustarse al Reglamento General de Protección de Datos (RGPD)

Para obtener más información, vea [Transformación Digital con Microsoft 365](http://transform.microsoft.com). 

#### <a name="sharepoint-online-site-for-highly-regulated-data"></a>Sitio de SharePoint Online para datos altamente regulados

Los datos altamente regulados están sujetos a reglamentos regionales o son los datos más importantes para su organización, como por ejemplo secretos empresariales, información financiera o de recursos humanos y estrategias de organización. Para este tipo de datos, puede configurar un sitio de SharePoint Online con acceso restringido, clasificación de datos, prevención de pérdida de datos y cifrado. Para obtener más información, vea [Sitios de Microsoft Teams y SharePoint Online para datos altamente regulados](teams-sharepoint-online-sites-highly-regulated-data.md).

#### <a name="result"></a>Resultado
Una lista de escenarios de SharePoint Online y OneDrive para la Empresa que satisfacen las necesidades de almacenamiento y uso compartido de documentos, administración de contenidos y colaboración de la organización.

## <a name="phase-2-onboard"></a>Fase 2: Incorporar

En esta fase, planeará los aspectos técnicos de una implementación de SharePoint Online y OneDrive para la Empresa y empezará a implementarlos en grupos de usuarios seleccionados.

### <a name="prerequisites-identity-and-device-access-configuration"></a>Requisitos previos: configuración de acceso a dispositivos e identidades

Para proteger el acceso a los sitios de SharePoint Online, asegúrese de que configuró las [directivas de acceso a dispositivos e identidades](identity-access-policies.md) y las [directivas de acceso recomendadas de SharePoint Online](sharepoint-file-access-policies.md).

### <a name="step-1-complete-your-technical-planning"></a>Paso 1: Completar el planeamiento técnico

Antes de empezar con la planeación técnica, determine si quiere usar FastTrack. Si su organización tiene más de 50 puestos y participa en un [plan apto](https://technet.microsoft.com/library/dn783224.aspx), puede usar las ventajas de FastTrack, disponible sin costo adicional para guiarle por la planeación, la implementación y la adopción del servicio. También puede realizar este trabajo usted mismo con los asistentes de incorporación de FastTrack, que están disponibles en [FastTrack](https://fasttrack.microsoft.com/) una vez que inicia sesión con su cuenta de Office 365.

Si va a realizar la planeación por su cuenta (o de forma conjunta con FastTrack), necesita determinar si la red y la organización están preparadas para SharePoint Online. Es especialmente importante que cumpla los criterios de salida de redes en su infraestructura base y que preste especial atención a los retrasos de tráfico, el rendimiento y el ancho de banda de Internet para maximizar el rendimiento del tráfico adicional de documentos basados en SharePoint Online.

Use estos recursos para preparar los aspectos técnicos de una implementación de SharePoint Online: 

- [Guía de planeamiento de SharePoint Online](https://support.office.com/article/sharepoint-online-planning-guide-abacd1bb-295d-4235-afdd-15f5e4cc2e6c)
- [Migrar a SharePoint Online](https://docs.microsoft.com/sharepointmigration/migrate-to-sharepoint-online) 

Para comprender mejor la seguridad en SharePoint Online, revise los recursos siguientes:

-   [¿Cómo protegen SharePoint Online y OneDrive sus datos en la nube?](https://support.office.com/article/How-SharePoint-Online-and-OneDrive-safeguard-your-data-in-the-cloud-5aa038e8-8ff0-4704-9e6a-fd72af0a2035)
-   [Cifrado de datos en OneDrive para la Empresa y SharePoint Online](https://support.office.com/article/Data-Encryption-in-OneDrive-for-Business-and-SharePoint-Online-6501B5EF-6BF7-43DF-B60D-F65781847D6C)

#### <a name="result"></a>Resultado

Comprenderá la migración de carpetas y documentos locales y la seguridad de sitios de SharePoint Online y estará preparado para empezar a implementar SharePoint Online y OneDrive para la Empresa en grupos específicos de la organización.

### <a name="step-2-run-an-it-pilot"></a>Paso 2: Ejecutar una prueba piloto de TI

En la mayoría de las organizaciones medianas y grandes, debería ejecutar una prueba piloto de TI con las partes interesadas de la fase 1, así como con usuarios pioneros y aficionados técnicos. Durante la prueba piloto de TI:

- Elija un escenario de negocios de SharePoint Online en el que los participantes en la prueba piloto de TI puedan practicar.
- Ofrezca a los participantes en la prueba piloto un conjunto de ejercicios para probar el almacenamiento y uso compartido de documentos, la colaboración, la programación basada en el equipo y otras funcionalidades de SharePoint Online.
- Determine su estrategia de administración de cambios y produzca materiales para fomentar la adopción de SharePoint Online por parte de los usuarios de toda la organización. Los materiales de administración de cambios pueden incluir texto de anuncios de correo electrónico, planes de aprendizaje interno, pósteres y presentaciones. Estos materiales informarán a su organización sobre SharePoint Online y sus ventajas con los objetivos de concienciar y fomentar el uso. Vea el artículo sobre la estrategia de administración de cambios para [Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/change-management-strategy) para obtener algunas ideas.
- Haga que los participantes de la prueba piloto de TI revisen los materiales de administración de cambios en función de su experiencia. Pueden proporcionar sugerencias sobre procedimientos recomendados y consejos sobre cómo describir mejor las ventajas de SharePoint Online y cómo usarlo a efectos de comunicación y programación.

#### <a name="result"></a>Resultado

Ha completado la prueba piloto de TI de SharePoint Online y ha desarrollado, revisado y perfeccionado los materiales de administración de cambios inicial.

### <a name="step-3-roll-out-to-a-business-group"></a>Paso 3: Implementar en un grupo empresarial

Después de completar la prueba piloto de TI, implemente SharePoint Online en un grupo o departamento empresarial de su organización. Esta implementación ha de incluir:

- Identificación de los principales escenarios de negocios para SharePoint Online dentro del grupo empresarial.
- Anuncio de actividades a fin de informar a los usuarios de las expectativas y escalas de tiempo del uso de SharePoint Online para equipos de departamento, trabajo o proyecto.
- Migración de carpetas y documentos locales de los miembros del grupo empresarial a SharePoint Online.
- Impartir aprendizaje a los usuarios u ofrecer vínculos a recursos para presentar SharePoint Online y mostrar cómo usarlo. Vea el vídeo de aprendizaje de [SharePoint Online](https://support.office.com/article/sharepoint-online-video-training-cb8ef501-84db-4427-ac77-ec2009fb8e23).
- Un mecanismo de comentarios, como un equipo central de Microsoft Teams que contenga a todos los usuarios del grupo empresarial, para recopilar comentarios y actuar en problemas de los usuarios del grupo empresarial.
 
Durante la implementación, puede perfeccionar los materiales de administración de cambios a fin de preparar la implementación en toda la organización.

#### <a name="result"></a>Resultado

Puso en marcha un grupo empresarial con SharePoint Online y OneDrive para la Empresa y se probaron y perfeccionaron los materiales de administración de cambios.

## <a name="phase-3-drive-value"></a>Fase 3: Impulsar el valor

En esta fase, completará la implementación del soporte técnico de SharePoint Online para los usuarios con el fin de ayudarles a comprender sus ventajas.

### <a name="step-1-roll-out-to-the-rest-of-your-organization"></a>Paso 1: Implementar en el resto de la organización

La implementación para el resto de su organización tiene que incluir lo siguiente:

- Identificación de los principales escenarios empresariales para SharePoint Online dentro de grupos empresariales independientes.
- Uso de los materiales de administración de cambios perfeccionados para anunciar actividades con el fin de informar a la organización de las expectativas y escalas de tiempo del uso.
- Migración de carpetas y documentos para el resto de la organización a SharePoint Online.
- Impartir aprendizaje a los usuarios u ofrecer vínculos a recursos para presentar SharePoint Online y mostrar cómo usarlo.
- Un mecanismo de comentarios, como un equipo central que contenga a todos los usuarios, para recopilar comentarios y corregir los problemas de los usuarios de la organización. Si su organización tiene menos de 2500 personas, use un canal público en Teams. En caso contrario, use un grupo público en Yammer.

#### <a name="result"></a>Resultado
Su organización está lista y su estrategia de administración de cambios está preparada para informar, proporcionar aprendizaje y permitir a los usuarios empezar a usar SharePoint Online.

### <a name="step-2-measure-usage-manage-satisfaction-and-drive-adoption"></a>Paso 2: Medir el uso, administrar la satisfacción e impulsar la adopción

Después de completar la implementación en toda la organización, tiene que seguir usando su estrategia de administración de cambios para:

- Conseguir que el equipo directivo promueva SharePoint Online como la herramienta principal para el almacenamiento y uso compartido de documentos y la colaboración en el equipo, la división o en toda la organización.
- Animar a los usuarios a usarlo para los calendarios y la colaboración de los equipos de proyecto, trabajo, departamento y grupos empresariales.

Estas son algunas actividades sugeridas:

- Vea la [Guía de adopción de Office 365](https://aka.ms/successfactors) para obtener información sobre procedimientos recomendados generales para la adopción de servicios en la nube. 
- Vea [Informes de actividades de Office 365](https://support.office.com/article/Activity-Reports-in-the-Office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263) para comprender el uso del servicio de Office 365 en toda la organización. Si no es administrador global de Office 365 de su organización, pida a alguien que lo sea que le conceda permisos de lectura de informes a su cuenta de usuario para que pueda tener acceso a los informes de actividades.
- Supervise el espacio de los comentarios (un canal público en un equipo central de Teams o Yammer) para ver los problemas y comentarios de los usuarios sobre sus experiencias con SharePoint Online y OneDrive para la Empresa. Solucione las preguntas y los problemas lo antes posible para evitar que los usuarios se sientan frustrados y demostrar que apoya la implementación.
- Identifique y promueva a los mejores de cada grupo empresarial y resalte sus logros y procedimientos recomendados mediante SharePoint Online. Refleje su éxito en la organización para mostrar el éxito y la adopción del proyecto. La aprobación de líderes técnicos dentro de un grupo empresarial puede ejercer una influencia eficaz en los líderes y compañeros.

#### <a name="result"></a>Resultado

Su organización ha adoptado SharePoint Online como servicio que admite la colaboración y el almacenamiento de documentación.

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Cómo Microsoft utiliza Microsoft 365 Enterprise

Para echar un vistazo a Microsoft y conocer cómo la compañía implementó SharePoint Online, vea [SharePoint en la nube: Obtenga información sobre cómo Microsoft llevó a cabo su propia migración](https://www.microsoft.com/itshowcase/Article/Content/691/SharePoint-to-the-cloud-Learn-how-Microsoft-ran-its-own-migration).

## <a name="next-steps"></a>Pasos siguientes

Vea estos recursos para el mantenimiento continuo de SharePoint Online: 

- [Descripción de los permisos en SharePoint](https://support.office.com/article/Understanding-permission-levels-in-SharePoint-87ecbb0e-6550-491a-8826-c075e4859848)
- [Personalizar permisos del sitio de SharePoint](https://support.office.com/article/Customize-SharePoint-site-permissions-b1e3cd23-1a78-4264-9284-87fed7282048)
- [Activar y desactivar el uso compartido externo para SharePoint Online](https://support.office.com/article/Turn-external-sharing-on-or-off-for-SharePoint-Online-6288296a-b6b7-4ea4-b4ed-c297bf833e30)
- [Configurar y administrar solicitudes de acceso](https://support.office.com/article/Set-up-and-manage-access-requests-94B26E0B-2822-49D4-929A-8455698654B3)

