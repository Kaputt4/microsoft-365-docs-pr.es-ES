---
title: Implementar Microsoft Teams para Microsoft 365 Enterprise
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/28/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-collaboration
- Strat_O365_Enterprise
ms.custom: ''
description: Se detalla el proceso de planeación, implementación y aumento del valor de Microsoft Teams en Microsoft 365 Enterprise en toda la organización.
ms.openlocfilehash: fd2e72ddb0dfbcc437d30dee16241fbccc81b05b
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2019
ms.locfileid: "36982621"
---
# <a name="deploy-microsoft-teams-for-microsoft-365-enterprise"></a>Implementar Microsoft Teams para Microsoft 365 Enterprise

*Esta carga de trabajo está incluida en las versiones E3 y E5 de Microsoft 365 Enterprise*

Microsoft Teams reúne el chat, las conferencias, el uso compartido de documentos y las conversaciones encadenadas de forma que resulta más fácil crear y compartir contenido en grupos. Teams es la forma de trabajar en equipo y colaborar de Microsoft 365 Enterprise y es un elemento clave del valor creado para el trabajo en equipo de Microsoft 365. Si es nuevo en Teams, consulte [Introducción a Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-overview).
 
Si actualmente usa Skype Empresarial, estamos implementando funcionalidades de Skype Empresarial en Teams. Esto se llevará a cabo con el paso del tiempo y finalmente Teams será la única experiencia del cliente. Como cliente valioso de Skype Empresarial, Microsoft le ayudará. Consulte [Recorrido desde Skype Empresarial a Microsoft Teams](https://docs.microsoft.com/microsoftteams/journey-skypeforbusiness-teams) para obtener más información.

Los siguientes pasos y fases le guiarán a través del proceso de planificar el rol de Teams en su organización, incorporar su organización en Teams a través de una serie de implementaciones graduales y fomentar el uso de Teams y su valor para sus usuarios finales. 

Antes de empezar, asegúrese de haber configurado las fases de [infraestructura de la fundación](deploy-foundation-infrastructure.md) adecuadas para que los equipos tengan las capacidades de seguridad que usted necesita.

## <a name="phase-1-envision"></a>Fase 1: Planear

En esta fase, reunirá a las personas para la implementación de Teams y determinará cómo usará Teams su organización para satisfacer sus necesidades empresariales.

### <a name="step-1-gather-your-teams-deployment-members"></a>Paso 1: Reunir a los miembros de la implementación de Teams
Para conseguir una implementación correcta de Teams basada en la [infraestructura base](deploy-foundation-infrastructure.md) de Microsoft 365, deberá reunir a las personas adecuadas para que aporten y envíen comentarios. Las personas clave incluyen a los responsables de toma de decisiones empresariales, al personal de TI (como los arquitectos y los implementadores) y a los intercesores de los usuarios finales. 

Estos tres grupos aseguran que la implementación de Teams incluye consideraciones que satisfacen las necesidades empresariales, los aspectos técnicos sobre licencias y seguridad y que Teams se convertirá en algo que usarán los usuarios habituales.

#### <a name="result"></a>Resultado

Una lista de personas que representan los aspectos empresariales, técnicos y de usuario final de su organización.

### <a name="step-2-determine-and-prioritize-your-teams-business-scenarios"></a>Paso 2: Determinar y priorizar los escenarios empresariales de Teams
Teams se puede usar para muchas finalidades diferentes. Necesita conocer cuáles se ajustan a sus necesidades empresariales en los diferentes niveles de su organización, grupos empresariales, departamentos, equipos de trabajo y proyectos individuales. Vea ejemplos que le ayuden a definir los escenarios de Teams en la [Biblioteca de productividad de Microsoft 365 FastTrack](https://www.microsoft.com/microsoft-365/success/?rtc=1). 

Debería usar Teams para abordar equipos muy colaborativos y cambiantes que trabajan estrechamente y necesitan muchos más recursos que solo el correo electrónico que puede proporcionar Exchange Online. Algunos ejemplos son chats en grupo en directo con un historial registrado y un lugar fácil de encontrar y común para almacenar archivos y notas. 

Una forma de ver las ventajas de Teams es examinar cómo un equipo o equipo virtual interactúa hoy en día y, después, encontrar un escenario adecuado de Teams que reemplace la interacción y proporcione formas más sencillas de colaborar y ofrecer funcionalidades adicionales.

#### <a name="microsoft-teams-for-highly-regulated-data"></a>Microsoft Teams para datos altamente regulados

Los datos altamente regulados están sujetos a reglamentos regionales o son los datos más importantes para su organización, como por ejemplo secretos empresariales, información financiera o de recursos humanos y estrategias de organización. Para este tipo de datos, puede configurar un equipo con acceso restringido, clasificación de datos, prevención de pérdida de datos y cifrado. Para obtener más información, vea [Sitios de Microsoft Teams y SharePoint Online para datos altamente regulados](teams-sharepoint-online-sites-highly-regulated-data.md).

#### <a name="result"></a>Resultado

Una lista de escenarios de Teams que abordan las necesidades de su organización para el trabajo en equipo y la colaboración.

## <a name="phase-2-onboard"></a>Fase 2: Incorporar

En esta fase, planeará los aspectos técnicos de una implementación de Teams y empezará a implementar Teams en los grupos de usuarios seleccionados.

### <a name="prerequisites-identity-and-device-access-configuration"></a>Requisitos previos: configuración de acceso a dispositivos e identidades

Para proteger el acceso a los equipos, asegúrese de que configuró [directivas de acceso a dispositivos e identidades](identity-access-policies.md) y [directivas de acceso recomendadas de SharePoint Online](sharepoint-file-access-policies.md).

### <a name="step-1-complete-your-technical-planning"></a>Paso 1: Completar el planeamiento técnico

Antes de empezar con la planificación técnica, determine si quiere usar FastTrack. Si su organización tiene más de 50 puestos y participa en un [plan apto](https://technet.microsoft.com/library/dn783224.aspx), puede usar [FastTrack para Microsoft 365](https://fasttrack.microsoft.com/microsoft365), disponible sin coste adicional para guiarle en la planificación, la implementación y la adopción de servicios. O bien, puede realizar esto por su cuenta con los Asistentes para incorporación de FastTrack, que están disponibles en [FastTrack](https://fasttrack.microsoft.com/) después de iniciar sesión con su cuenta de Office 365.

Si va a realizar la planificación por su cuenta (o de forma conjunta con FastTrack), necesita determinar si la red y la organización están preparadas para Teams. Es especialmente importante que cumpla los criterios de salida de redes en su [infraestructura básica](deploy-foundation-infrastructure.md) y que preste especial atención a los retrasos de tráfico, el rendimiento y el ancho de banda para maximizar el rendimiento de las reuniones basadas en Teams.

Use estos recursos para preparar los aspectos técnicos de su organización para una implementación de Teams: 

- [Comprobación de la preparación del entorno para Teams](https://docs.microsoft.com/MicrosoftTeams/environment-readiness)
- [Preparar su red para Teams](https://docs.microsoft.com/MicrosoftTeams/prepare-network)
- [Direcciones URL e intervalos de direcciones IP de Office 365](https://docs.microsoft.com/MicrosoftTeams/office-365-urls-ip-address-ranges)

Para comprender mejor la seguridad en Teams, consulte los siguientes recursos adicionales:

- [Información general de seguridad y cumplimiento en Teams](https://docs.microsoft.com/MicrosoftTeams/security-compliance-overview)
- [Grupos de Office 365 y Teams](https://docs.microsoft.com/MicrosoftTeams/office-365-groups)
- [Acceso de invitado a Teams](https://docs.microsoft.com/MicrosoftTeams/office-365-groups)

A continuación, use estos recursos para comprender las licencias de Teams y llevar a cabo la configuración de Teams para su organización:

- [Licencias de Office 365 para Teams](https://docs.microsoft.com/MicrosoftTeams/office-365-licensing)
- [Administrar el acceso de los usuarios a Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/user-access)
- [Obtener clientes para Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/get-clients)
- [Activar Microsoft Teams en su organización de Office 365](https://docs.microsoft.com/MicrosoftTeams/office-365-set-up)
- [Administrar las características de Microsoft Teams en su organización de Office 365](https://docs.microsoft.com/microsoftteams/enable-features-office-365)

#### <a name="result"></a>Resultado

Ha llevado a cabo la planeación de licencias de Office 365, la seguridad y la red, y está listo para empezar a implementar Teams en los grupos seleccionados de su organización.

### <a name="step-2-run-an-it-pilot"></a>Paso 2: Ejecutar una prueba piloto de TI

En la mayoría de las organizaciones medianas y grandes, debería ejecutar una prueba piloto de TI con las partes interesadas de la fase 1, así como con usuarios pioneros y aficionados técnicos. Durante la prueba piloto de TI:

- Elija un escenario empresarial de Teams donde puedan practicar los participantes de la prueba piloto de TI. Consulte la [guía para comenzar con Microsoft Teams](http://microsoft.com/download/56505) para obtener ideas.
- Proporcione a los participantes piloto un conjunto de ejercicios con los que probar los chats, el almacenamiento, las reuniones y otras funcionalidades basadas en Teams.
- Determine su estrategia de administración de cambios y produzca materiales para fomentar la adopción de los usuarios de toda la organización. Los materiales de administración de cambios pueden incluir texto de anuncios de correo electrónico, planes de aprendizaje interno, pósteres y presentaciones. Estos materiales informarán a su organización sobre Teams y sus ventajas con los objetivos de concienciar y fomentar el uso. Vea [Crear una estrategia de administración de cambios para Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/change-management-strategy) para obtener algunas ideas.
- Haga que los participantes de la prueba piloto de TI revisen los materiales de la estrategia de administración de cambios en función de su experiencia. Pueden proporcionar sugerencias sobre procedimientos recomendados y consejos sobre cómo describir mejor las ventajas de Teams y cómo usarlo para colaborar y trabajar en equipo.

#### <a name="result"></a>Resultado

Ha completado la prueba piloto de Teams y ha desarrollado, revisado y perfeccionado los materiales de administración de cambios iniciales.

### <a name="step-3-roll-out-to-a-business-group"></a>Paso 3: Implementar en un grupo empresarial

Después de completar la prueba piloto de TI, implemente Teams en un grupo o departamento empresarial de su organización. Esta implementación debería incluir:

- Identificación de los escenarios empresariales clave para Teams dentro del grupo empresarial.
- Anuncio de actividades a fin de informar a los usuarios de las expectativas y escalas de tiempo del uso de Teams para equipos de departamento, trabajo o proyecto.
- Aprendizaje directo de los usuarios en Teams o vínculos a recursos para presentar Teams y cómo usarlo.
- Un mecanismo de comentarios, como un equipo central que contenga a todos los usuarios del grupo empresarial, para recopilar comentarios y problemas de los usuarios del grupo empresarial.

Durante la implementación, puede perfeccionar los materiales de administración de cambios a fin de preparar la implementación en toda la organización.

#### <a name="result"></a>Resultado

Tiene un grupo empresarial que usa Teams y ha probado y perfeccionado los materiales de administración de cambios.

## <a name="phase-3-drive-value"></a>Fase 3: Impulsar el valor

En esta fase, completará la implementación de Teams en su organización y proporcionará soporte técnico a los usuarios para que comprendan sus ventajas.

### <a name="step-1-roll-out-teams-to-the-rest-of-your-organization"></a>Paso 1: Implementar Teams en el resto de la organización

Después de completar la implementación en un grupo empresarial específico, implemente Teams en el resto de su organización. Esta implementación debería incluir:

- Identificación de los escenarios empresariales clave para Teams dentro de los grupos empresariales independientes.
- Uso de sus materiales de administración de cambios perfeccionados para anunciar actividades a fin de informar a la organización de las expectativas y escalas de tiempo del uso de Teams para equipos de departamento, trabajo o proyecto.
- Oferta de aprendizaje a los usuarios en Teams o vínculos a recursos para presentar Teams y cómo usarlo. Vea los recursos de aprendizaje de [Formación del usuario final para Microsoft Teams](https://docs.microsoft.com/microsoftteams/enduser-training).
- Un mecanismo de comentarios, como un equipo central que contenga a todos los usuarios, para recopilar comentarios y corregir los problemas de los usuarios de la organización. Si su organización tiene menos de 2500 personas, use un canal público en Teams. En caso contrario, use un grupo público en Yammer.

#### <a name="result"></a>Resultado

Su organización está lista y su estrategia de administración de cambios está preparada para informar, capacitar y habilitar a los usuarios para que puedan empezar a usar Teams.

### <a name="step-2-measure-usage-manage-satisfaction-and-drive-adoption"></a>Paso 2: Medir el uso, administrar la satisfacción y fomentar la adopción

Después de implementar Teams en toda la organización, debe seguir usando su estrategia de administración de cambios para:

- Hacer que su equipo directivo promueva Teams como la herramienta de colaboración y trabajo en equipo de la organización.
- Animar a los usuarios a usarlo para la colaboración y las comunicaciones de los equipos de proyecto, trabajo, departamento y grupos empresariales.

Estas son algunas actividades sugeridas:

- Vea la [guía de adopción de Office 365](https://aka.ms/successfactors) para obtener información sobre procedimientos recomendados generales para la adopción de servicios en la nube. 
- Vea [Informes de actividades de Office 365](https://support.office.com/article/Activity-Reports-in-the-Office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263) para comprender el uso del servicio de Office 365 en toda la organización. Si no es un administrador global de Office 365 de su organización, pida a alguien que lo sea que le conceda permisos de lectura de informes a su cuenta de usuario para que pueda obtener acceso a los informes de actividades.
- Supervise el espacio de los comentarios (un canal público en un equipo central o Yammer) para ver los problemas y comentarios de los usuarios sobre sus experiencias con Teams. Atienda a las preguntas y los problemas tan pronto como pueda para evitar posibles molestias y que los usuarios abandonen Teams.
- Identifique y promueva a los mejores de cada grupo empresarial y resalte sus logros y procedimientos recomendados con Teams. Muestre su éxito a la organización para mostrar el éxito y la adopción del proyecto. La aprobación de líderes técnicos dentro de un grupo empresarial puede ejercer una influencia eficaz en los líderes y compañeros.

#### <a name="result"></a>Resultado

Su organización ha adoptado Teams como su herramienta de colaboración y trabajo en equipo.

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Cómo Microsoft utiliza Microsoft 365 Enterprise

Para echar un vistazo dentro de Microsoft y conocer cómo la empresa implementó y utiliza Microsoft Teams para la colaboración, vea:

- [Deploying Microsoft Teams streamlines collaboration and improves teamwork](https://www.microsoft.com/itshowcase/Article/Content/1013/Deploying-Microsoft-Teams-streamlines-collaboration-and-improves-teamwork) (Implementar Microsoft Teams agiliza la colaboración y mejora el trabajo en equipo)
- [Microsoft Teams increases collaboration in the modern workplace at Microsoft](https://www.microsoft.com/itshowcase/Article/Content/1012/Microsoft-Teams-increases-collaboration-in-the-modern-workplace-at-Microsoft) (Microsoft Teams Mejora la colaboración en el área de trabajo moderna de Microsoft)

## <a name="next-steps"></a>Pasos siguientes

- [Administrar las características de Microsoft Teams en su organización de Office 365](https://docs.microsoft.com/microsoftteams/enable-features-office-365)
- [Formación de administradores para Microsoft Teams](https://docs.microsoft.com/microsoftteams/itadmin-readiness)
