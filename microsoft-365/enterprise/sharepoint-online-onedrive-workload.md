---
title: Implementar SharePoint y OneDrive para Microsoft 365 Enterprise
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/11/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-collaboration
- Strat_O365_Enterprise
ms.custom: ''
description: Se detalla el proceso de planeación, implementación y aumento del valor de SharePoint en toda la organización.
ms.openlocfilehash: 0cad129cdca5f5dcc072f583b2b651a2547fc5fd
ms.sourcegitcommit: 68c54a45dd663027528b99f883c6ef04b04b19b0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/11/2019
ms.locfileid: "37469152"
---
# <a name="deploy-sharepoint-and-onedrive-for-microsoft-365-enterprise"></a>Implementar SharePoint y OneDrive para Microsoft 365 Enterprise

*Esta carga de trabajo está incluida en las versiones E3 y E5 de Microsoft 365 Enterprise*

SharePoint y Microsoft Teams se usan para el almacenamiento y uso compartido de archivos, la administración de contenido y la colaboración, y son un elemento clave del valor diseñado para trabajo en equipo de Microsoft 365 Enterprise. 

SharePoint también cuenta con funcionalidades de seguridad avanzadas que incluyen control con permisos de acceso y cifrado en vuelo y en reposo. La seguridad de SharePoint es un elemento clave del valor de seguridad Inteligente de Microsoft 365 Enterprise.

Si no conoce SharePoint, vea [SharePoint](https://products.office.com/sharepoint/collaboration) y la[Introducción a SharePoint](https://support.office.com/article/video-what-is-sharepoint-online-c17b6824-cc22-478f-8757-497cc6b57121).

Los siguientes pasos y fases le guiarán a través del proceso de planificar el rol de SharePoint en la organización, incorporar la organización a través de una serie de implementaciones graduales y fomentar el uso de su valor para sus usuarios finales. Antes de empezar, asegúrese de haber configurado las fases de [infraestructura de la fundación](deploy-workloads.md#foundation-infrastructure-prerequisites) adecuadas para que los sitios de SharePoint tengan las capacidades de seguridad que usted necesita. 

Para implementar OneDrive para Microsoft 365 Enterprise, vea la [Guía de OneDrive para empresas](https://docs.microsoft.com/onedrive/plan-onedrive-enterprise).

## <a name="phase-1-envision"></a>Fase 1: Planear
En esta fase, reunirá a los socios de su organización para la implementación de SharePoint y OneDrive para la Empresa y determinará cómo usará SharePoint su organización para satisfacer sus necesidades empresariales.

### <a name="step-1-gather-your-sharepoint-deployment-members"></a>Paso 1: Reunir a los miembros de la implementación de SharePoint

Para conseguir una implementación correcta de SharePoint y OneDrive para la Empresa basada en la [infraestructura básica de Microsoft 365 Enterprise](deploy-foundation-infrastructure.md), necesita reunir a las personas adecuadas para que proporcionen comentarios. Entre las personas clave, se incluyen los responsables de toma de decisiones empresariales, el personal de TI (como los arquitectos y los implementadores) y los defensores de los usuarios finales. 

Estos tres grupos garantizan que la implementación incluya consideraciones que aborden las necesidades empresariales, los aspectos técnicos de la migración de carpetas y documentos y la seguridad, y que se convertirá en algo que usarán los usuarios habituales.

#### <a name="result"></a>Resultado

Una lista de personas que representan las perspectivas empresariales, técnicas y del usuario final de su organización.

### <a name="step-2-determine-and-prioritize-your-sharepoint-business-scenarios"></a>Paso 2: Determinar y priorizar los escenarios empresariales de SharePoint

SharePoint puede usarse con distintos fines. Necesita determinar qué fines se corresponden con sus necesidades empresariales. Su objetivo es que SharePoint satisfaga las necesidades de almacenamiento y uso compartido de documentos, de administración de contenidos y de colaboración de los equipos, la división o toda la organización. 

Vea la lista de escenarios y funciones en [SharePoint](https://products.office.com/sharepoint/collaboration ).

Los siguientes pilares empresariales pueden abordar las necesidades de la organización:

|||
|:-----|:-----|
| Compartir y colaborar | Aproveche las ventajas de los sitios de grupo, los sitios de comunicación y la sincronización. |
| Informar e interactuar | La información que viene en el futuro. |
| Transformar | Usa Flow para crear flujos de trabajo automatizados entre aplicaciones y servicios. |
| Aprovechar el conocimiento colectivo | Se utiliza la búsqueda para proporcionar los resultados que quiere en su organización. |
| Proteger | Garantiza que su organización está protegida y cuenta con el cumplimiento normativo correcto. |
|||

Vea [Administrador de SharePoint](https://docs.microsoft.com/sharepoint/sharepoint-online) para obtener recursos sobre cómo configurar SharePoint según sus necesidades.

Una forma de ver los beneficios de SharePoint es examinar cómo interactúan actualmente las personas, un equipo, una división o toda la organización y luego encontrar un escenario apropiado que ofrezca formas más fáciles de almacenar y compartir archivos. Tenga en cuenta que [Microsoft Teams](teams-workload.md) puede ser la mejor opción para algunos de los escenarios.

#### <a name="sharepoint-site-for-highly-regulated-data"></a>Sitio de SharePoint para datos altamente regulados

Los datos extremadamente regulados son los que están sujetos a altas regulaciones locales, o que son los más importantes para su organización, como pueden ser secretos comerciales, información de recursos humanos o financiera y estrategias de la organización. Puede configurar un sitio de SharePoint para el acceso restringido, la clasificación de datos, la prevención de pérdida de datos y el cifrado de este tipo de datos. Para saber más, vea [Sitios de Microsoft Teams y SharePoint para datos extremadamente regulados](teams-sharepoint-online-sites-highly-regulated-data.md)

#### <a name="result"></a>Resultado
Una lista de escenarios de SharePoint y OneDrive para la Empresa que satisfacen las necesidades de almacenamiento y uso compartido de documentos, administración de contenidos, colaboración y seguridad de la organización.

## <a name="phase-2-onboard"></a>Fase 2: Incorporar

En esta fase, planeará los aspectos técnicos de una implementación de SharePoint y OneDrive para la Empresa y empezará a implementarlos en grupos de usuarios seleccionados.

### <a name="prerequisites-identity-and-device-access-configuration"></a>Requisitos previos: configuración de acceso a dispositivos e identidades

Para proteger el acceso a los sitios de SharePoint, asegúrese de que configuró las [directivas de acceso a dispositivos e identidades](identity-access-policies.md) y las [directivas de acceso recomendadas de SharePoint](sharepoint-file-access-policies.md).

### <a name="step-1-complete-your-technical-planning"></a>Paso 1: Completar el planeamiento técnico

Antes de iniciar la planificación técnica, decida si desea usar FastTrack. Si su organización tiene más de 50 puestos y participa en un [plan admitido](https://docs.microsoft.com/fasttrack/O365-fasttrack-benefit-for-office-365), puede usar las ventajas de FastTrack sin coste adicional para guiarse a través de los procesos de planificación, migración, implementación y adopción del servicio. También puede completar este trabajo usted mismo usando los asistentes de incorporación de FastTrack, que están disponibles en [FastTrack](https://docs.microsoft.com/fasttrack/m365-fasttrack-benefit-overview), después de iniciar sesión con la cuenta de Microsoft 365.

Ya lo planifique usted mismo o con FastTrack, debe determinar si su red y su organización están listas para SharePoint. Es especialmente importante que cumpla los [criterios de salida de redes](networking-exit-criteria.md) en su infraestructura base y que preste especial atención a los retrasos de tráfico, el rendimiento y el ancho de banda de Internet para maximizar el rendimiento del tráfico adicional de documentos basados en SharePoint.

Use [Migrar a SharePoint](https://docs.microsoft.com/sharepointmigration/migrate-to-sharepoint-online) para preparar la implementación de SharePoint: 

Para comprender mejor la seguridad en SharePoint, revise los recursos siguientes:

-   [¿Cómo protegen SharePoint y OneDrive sus datos en la nube?](https://docs.microsoft.com/sharepoint/safeguarding-your-data)
-   [Cifrado de datos en OneDrive y SharePoint](https://docs.microsoft.com/microsoft-365/compliance/data-encryption-in-odb-and-spo)

#### <a name="result"></a>Resultado

Comprenderá la migración de carpetas y documentos locales y la seguridad de sitios de SharePoint y estará preparado para empezar a implementar SharePoint y OneDrive para la Empresa en grupos específicos de la organización.

### <a name="step-2-run-an-it-pilot"></a>Paso 2: Ejecutar una prueba piloto de TI

En la mayoría de las organizaciones medianas y grandes, debería ejecutar una prueba piloto de TI con las partes interesadas de la fase 1, así como con usuarios pioneros y aficionados técnicos. Durante la prueba piloto de TI:

- Elija un escenario de negocios de SharePoint en el que los participantes en la prueba piloto de TI puedan practicar.
- Ofrezca a los participantes en la prueba piloto un conjunto de ejercicios para probar el almacenamiento y uso compartido de documentos, la colaboración y otras funcionalidades de SharePoint.
- Determine la estrategia de administración de cambios y elabore materiales para impulsar la adopción general de SharePoint en los usuarios de su organización. Los materiales para la gestión de cambios pueden incluir anuncios en correos electrónicos, formación interna, carteles en los pasillos y presentaciones. Estos materiales informarán a su organización de SharePoint y sus ventajas, para sensibilizar a los usuarios y aumentar su uso del software. Consulte los [recursos de la adopción de SharePoint](https://resources.techcommunity.microsoft.com/resources/SharePoint-adoption/) para empezar.
- Los participantes de la prueba piloto de TI deben revisar los materiales de administración de cambios en función de su experiencia. Pueden aportar sugerencias sobre las prácticas recomendadas y dar consejos sobre cómo describir mejor las ventajas de SharePoint y cómo usarlas.

#### <a name="result"></a>Resultado

Ha completado la prueba piloto de TI de SharePoint y ha desarrollado, revisado y perfeccionado los materiales de administración de cambios inicial.

### <a name="step-3-roll-out-to-a-business-group"></a>Paso 3: Implementar en un grupo empresarial

Después de completar la prueba piloto de TI, implemente SharePoint en un grupo o departamento empresarial de su organización. Esta implementación ha de incluir:

- Identificación de los principales escenarios de negocios para SharePoint dentro del grupo empresarial.
- Anuncio de actividades a fin de informar a los usuarios de las expectativas y escalas de tiempo del uso de SharePoint para equipos de departamento, trabajo o proyecto.
- Migración de carpetas y documentos locales de los miembros del grupo empresarial a SharePoint.
- Impartir aprendizaje a los usuarios u ofrecer vínculos a recursos para presentar SharePoint y mostrar cómo usarlo. Vea el aprendizaje de vídeo de [SharePoint](https://support.office.com/article/sharepoint-online-video-training-cb8ef501-84db-4427-ac77-ec2009fb8e23)
- Un mecanismo de comentarios, como un equipo central de Microsoft Teams que contenga a todos los usuarios del grupo empresarial, para recopilar comentarios y actuar en problemas de los usuarios del grupo empresarial.
 
Durante la implementación, puede perfeccionar los materiales de administración de cambios a fin de preparar la implementación en toda la organización.

#### <a name="result"></a>Resultado

Puso en marcha un grupo empresarial con SharePoint y OneDrive para la Empresa y se probaron y perfeccionaron los materiales de administración de cambios.

## <a name="phase-3-drive-value"></a>Fase 3: Impulsar el valor

En esta fase, completará la implementación de SharePoint y ayudará a los usuarios a aprovechar sus ventajas.

### <a name="step-1-roll-out-to-the-rest-of-your-organization"></a>Paso 1: Implementar en el resto de la organización

La implementación para el resto de su organización tiene que incluir lo siguiente:

- Identificación de los principales escenarios empresariales para SharePoint dentro de grupos empresariales independientes.
- Uso de los materiales de administración de cambios perfeccionados para anunciar actividades con el fin de informar a la organización de las expectativas y escalas de tiempo del uso.
- Migración de carpetas y documentos para el resto de la organización a SharePoint.
- Impartir aprendizaje a los usuarios u ofrecer vínculos a recursos para presentar SharePoint y mostrar cómo usarlo.
- Un mecanismo de comentarios, como un equipo central que contenga a todos los usuarios, para recopilar comentarios y corregir los problemas de los usuarios de la organización. Si su organización tiene menos de 2500 personas, use un canal público en Teams. En caso contrario, use un grupo público en Yammer.

#### <a name="result"></a>Resultado
Su organización está lista y su estrategia de administración de cambios está preparada para informar, proporcionar aprendizaje y permitir a los usuarios empezar a usar SharePoint.

### <a name="step-2-measure-usage-manage-satisfaction-and-drive-adoption"></a>Paso 2: Medir el uso, administrar la satisfacción y fomentar la adopción

Después de completar la implementación en toda la organización, tiene que seguir usando su estrategia de administración de cambios para:

- Haga que la dirección promocione SharePoint como la herramienta principal para el almacenamiento y el uso compartido de documentos.
- Anime a los usuarios a emplearlo para almacenar y compartir documentos entre grupos empresariales, departamentos y equipos de trabajo y proyecto.

Estas son algunas actividades sugeridas:

- Vea la [Factores de éxito para Office 365](https://aka.ms/successfactors) para obtener información sobre procedimientos recomendados generales para la adopción de servicios en la nube. 
- Vea [Informes de actividades de Office 365](https://docs.microsoft.com/office365/admin/activity-reports/activity-reports) para comprender el uso del servicio de Office 365 en toda la organización. Si no es administrador global de Office 365 de su organización, pida a alguien que lo sea que le conceda permisos de lectura de informes a su cuenta de usuario para que pueda tener acceso a los informes de actividades.
- Visite el centro de opiniones (un canal público en un equipo central de Teams o Yammer) para ver qué problemas tienen los usuarios y leer sus comentarios sobre su experiencia con SharePoint. Responda a las preguntas y los problemas tan pronto como pueda para prevenir que surja la frustración y demostrar que apoya a los usuarios en la implementación.
- Identifique y apoye a los mejores usuarios de cada grupo empresarial y resalte sus logros y prácticas recomendadas en SharePoint. Divulgue su éxito en la organización para demostrar el éxito y la adopción del proyecto. El respaldo de la dirección técnica de un grupo empresarial puede conllevar una influencia positiva en el resto de la dirección y los compañeros.

#### <a name="result"></a>Resultado

Su organización ha adoptado SharePoint en Microsoft 365 Enterprise para mejorar la colaboración y el almacenamiento de la documentación.

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Cómo Microsoft utiliza Microsoft 365 Enterprise

Para echar un vistazo a Microsoft y conocer cómo implementamos SharePoint, vea [SharePoint en la nube: cómo Microsoft llevó a cabo su propia migración](https://www.microsoft.com/es-ES/itshowcase/sharepoint-to-the-cloud-learn-how-microsoft-ran-its-own-migration).

## <a name="next-steps"></a>Siguientes pasos

Vea estos recursos para el mantenimiento continuo de SharePoint: 

- [Información sobre los niveles de permisos en SharePoint](https://docs.microsoft.com/sharepoint/understanding-permission-levels)
- [Personalizar permisos del sitio de SharePoint](https://docs.microsoft.com/sharepoint/customize-sharepoint-site-permissions)
- [Activar y desactivar el uso compartido externo para SharePoint](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off)
- [Configurar y administrar solicitudes de acceso](https://support.office.com/article/Set-up-and-manage-access-requests-94B26E0B-2822-49D4-929A-8455698654B3)
