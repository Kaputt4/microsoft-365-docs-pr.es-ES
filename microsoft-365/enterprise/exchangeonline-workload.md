---
title: Implementación de Exchange Online para Microsoft 365 Enterprise
author: JoeDavies-MSFT
manager: laurawi
ms.date: 06/28/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-email-calendar
ms.custom:
- Strat_O365_Enterprise
description: Recorra el proceso de planeación, implementación y impulso del valor de Exchange online en Microsoft 365 Enterprise en toda la organización.
ms.openlocfilehash: 6efd94da7806b6268881f7eaabe5efacc8920f47
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32281211"
---
# <a name="deploy-exchange-online-for-microsoft-365-enterprise"></a>Implementación de Exchange Online para Microsoft 365 Enterprise

*Esta carga de trabajo se incluye en las versiones E3 y E5 de Microsoft 365 Enterprise*

Exchange Online es el servicio de nube principal para el correo electrónico y el calendario que ayuda a los usuarios a colaborar de formas que no requieran el almacenamiento en tiempo real de chats o documentos centralizados. Exchange Online es el modo en que se realiza la comunicación y programación a corto y pequeño grupo, y es un elemento clave del valor creado para el trabajo en equipo de Microsoft 365 Enterprise. Exchange Online le permite realizar más tareas y trabajar de forma más eficaz con la aplicación de Outlook conocida, independientemente del dispositivo en el que se haya conectado.

Exchange Online también tiene capacidades de seguridad avanzadas que incluyen filtrado antimalware y contra correo no deseado para proteger los buzones y las capacidades de prevención de pérdida de datos que impiden que los usuarios envíen por error información confidencial a personas no autorizadas. La seguridad de Exchange Online es un elemento clave del valor de seguridad inteligente de Microsoft 365 Enterprise.

Si es nuevo en Exchange Online, consulte [Microsoft Exchange Online](https://products.office.com/exchange/exchange-online).

Las siguientes fases y pasos le guiarán a través del proceso de visualización de la función de Exchange online en su organización, la incorporación de su organización a Exchange Online a través de una serie de implementaciones progresivas y el uso de Exchange Online y su valor para los usuarios finales.

>[!Note]
>Estas instrucciones de implementación solo deben seguirse después de haber completado la [fase 2-identidad](identity-infrastructure.md) de la infraestructura básica de Microsoft 365 Enterprise.
>

## <a name="phase-1-envision"></a>Fase 1: Planificar

En esta fase, recopilará a los usuarios de su implementación de Exchange Online y determinará cómo su organización usará Exchange Online para satisfacer sus necesidades empresariales.

### <a name="step-1-gather-your-exchange-online-deployment-members"></a>Paso 1: recopilar los miembros de implementación de Exchange Online

Para que la implementación de Exchange Online se realice correctamente en la [fase 2: identidad](identity-infrastructure.md) de la infraestructura de Microsoft 365 Enterprise Foundation, es necesario obtener las personas adecuadas para la entrada y los comentarios. Entre los responsables clave se incluyen los responsables de decisiones empresariales, el personal de ti, como arquitectos e implementadores, y los defensores de los usuarios finales. 

Estos tres grupos garantizan que la implementación de Exchange Online incluya consideraciones para las necesidades empresariales, los aspectos técnicos de la migración y la seguridad de los buzones de correo, y que el resultado será algo que los usuarios típicos usarán.

#### <a name="result"></a>Resultado

Una lista de personas que representan los aspectos empresariales, técnicos y de usuario final de su organización.

### <a name="step-2-determine-and-prioritize-your-exchange-online-business-scenarios"></a>Paso 2: determinar y priorizar los escenarios empresariales de Exchange Online

Exchange Online se puede usar para distintos fines. Debe averiguar qué propósito se asigna a sus necesidades empresariales en los distintos niveles de la organización, los grupos empresariales, los departamentos o los equipos individuales de trabajo y de proyecto. Debe dirigirse a Exchange Online para dirigirse a sus necesidades de comunicación y programación de corta y pequeña vida de grupo. 

Una forma de ver las ventajas de Exchange Online es analizar la forma en que interactúan los individuos, un equipo o un equipo v y, después, encontrar un escenario adecuado que proporcione formas más sencillas de comunicarse, programar reuniones y colaborar. Tenga en cuenta que [Microsoft Teams](teams-workload.md) puede ser una opción mejor para algunos de los escenarios de colaboración.

Exchange Online permite estos escenarios empresariales estratégicos para Microsoft 365 Enterprise:

- Colaborar en documentos en tiempo real o en su propio tiempo para simplificar el proceso de creación conjunta
- Administrar proyectos, tareas y fechas límite para cumplir con sus objetivos de negocio
- Comprender sus hábitos de trabajo para mejorar su influencia e impacto
- Comunicarse con su equipo para permanecer informado, solicitar comentarios y facilitar la cohesión y el consenso
- Almacenar y compartir archivos, tanto dentro como fuera de la organización, para trabajar de forma fluida más allá de los límites organizativos
- Trabajar de forma segura en el dispositivo en cualquier momento y lugar para mejorar la productividad, a la vez que mantiene un estilo de trabajo flexible
- Proteger su información y reducir el riesgo de pérdida de datos
- Detección y protección contra amenazas externas 
- Supervisar, informar y analizar actividades para reaccionar con prontitud para proporcionar seguridad organizativa
- Apoyar a su organización con mayor privacidad y cumplimiento normativo para ajustarse al Reglamento General de Protección de Datos (RGPD)

Para obtener más información, vea [Transformación Digital con Microsoft 365](http://transform.microsoft.com). 

#### <a name="result"></a>Resultado
Una lista de escenarios de Exchange online que abordan las necesidades de la organización para la comunicación, la programación y la colaboración de corta duración.

## <a name="phase-2-onboard"></a>Fase 2: Incorporar

En esta fase, planeará los aspectos técnicos de una implementación de Exchange Online y empezará a implementarlos en grupos de usuarios seleccionados.

### <a name="prerequisites-identity-and-device-access-configuration"></a>Requisitos previos: configuración de acceso a dispositivos e identidades

Para proteger el acceso a los buzones de Exchange Online, asegúrese de que ha configurado [las directivas de acceso a dispositivos](identity-access-policies.md) e identidades y las [directivas de acceso de Exchange Online recomendadas](secure-email-recommended-policies.md).

### <a name="step-1-complete-your-technical-planning"></a>Paso 1: Completar el planeamiento técnico

Antes de comenzar con la planeación técnica, determine si desea usar FastTrack. Si su organización tiene más de 50 puestos y participa en un [plan elegible](https://technet.microsoft.com/library/dn783224.aspx), puede usar [FastTrack para Microsoft 365](https://fasttrack.microsoft.com/microsoft365), disponible sin costo adicional para guiarle a través de la planeación, la implementación y la adopción de servicios. O bien, puede completar este trabajo usted mismo con los asistentes de incorporación de FastTrack, que están disponibles en [FastTrack](https://fasttrack.microsoft.com/) una vez que inicie sesión con su cuenta de Office 365.

Si va a realizar su propia planeación, o junto con FastTrack, debe determinar si la red y la organización están listas para Exchange Online. Es especialmente importante que cumpla los criterios de salida de la red en su infraestructura básica, con especial atención a los retrasos en el ancho de banda, el rendimiento y el tráfico de Internet para maximizar el rendimiento del tráfico adicional de Exchange Correo electrónico y datos adjuntos basados en línea.

Use estos recursos para preparar los aspectos técnicos de un lanzamiento de Exchange Online: 

- [Formas de migrar varias cuentas de correo electrónico a Office 365](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration)
- [Colaboración en Exchange Online](https://technet.microsoft.com/library/jj983794(v=exchg.150).aspx)
- [Destinatarios en Exchange Online](https://technet.microsoft.com/library/jj200702(v=exchg.150).aspx)

Para comprender mejor la seguridad en Exchange Online, revise los siguientes recursos:

- [Permisos en Exchange Online](https://technet.microsoft.com/library/jj200692(v=exchg.150).aspx) 
- [Seguridad y cumplimiento de Exchange Online](https://technet.microsoft.com/library/jj200706(v=exchg.150).aspx) 
- [Protección contra correo no deseado y malware](https://technet.microsoft.com/library/jj200731(v=exchg.150).aspx)

A continuación, use estos recursos para comprender la administración de buzones de correo de Exchange Online:

- [Crear buzones de usuario en Exchange Online](https://technet.microsoft.com/library/jj907304(v=exchg.150).aspx)
- [Administrar los buzones de usuario](https://technet.microsoft.com/library/bb123809(v=exchg.150).aspx) 
- [Crear y administrar grupos de distribución](https://technet.microsoft.com/library/bb124513%28v=exchg.150%29.aspx)

#### <a name="result"></a>Resultado

Comprender la migración, la seguridad y la administración de buzones de correo y está preparado para comenzar a implementar Exchange online en los grupos seleccionados de la organización.

### <a name="step-2-run-an-it-pilot"></a>Paso 2: Ejecutar una prueba piloto de TI

En la mayoría de las organizaciones medianas y grandes, debería ejecutar una prueba piloto de TI con las partes interesadas de la fase 1, así como con usuarios pioneros y aficionados técnicos. Durante la prueba piloto de TI:

- Elija un escenario empresarial de Exchange online en el que puedan practicar los participantes de la prueba piloto de ti.
- Dé a los participantes en la prueba piloto Office 365 licencias y migre sus buzones locales a Exchange Online.
- Proporcione a los participantes de la prueba piloto un conjunto de ejercicios para probar el correo electrónico, la programación y otras capacidades de Exchange Online.
- DeTermine la estrategia de administración de cambios y genere materiales para impulsar la adopción por parte del usuario de Exchange online de toda la organización. Los materiales de administración de cambios pueden incluir texto de anuncio de correo electrónico, planes de formación interna, pósteres de vestíbulos y presentaciones. Estos materiales le informarán a su organización sobre Exchange Online y sus ventajas con los objetivos de la sensibilización y el uso. Consulte el artículo sobre la [estrategia de administración de cambios para Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/change-management-strategy) para ver algunas ideas.
- Los participantes de la prueba piloto de ti revisan los materiales de administración de cambios en función de sus experiencias. Pueden proporcionar sugerencias sobre los procedimientos recomendados y consejos sobre cómo describir mejor las ventajas de Exchange Online y cómo usarla para la comunicación y la programación.

#### <a name="result"></a>Resultado

Su piloto de TI de Exchange Online está completo y los materiales de administración de cambios iniciales se han desarrollado, revisado y perfeccionado.

### <a name="step-3-roll-out-to-a-business-group"></a>Paso 3: Implementar en un grupo empresarial

Una vez completada la prueba piloto de ti, implemente Exchange online en un departamento o grupo de negocio de su organización. Si su organización usa un servicio de correo electrónico local como Exchange Server, esta implementación consta de la migración de buzones. Este lanzamiento debe incluir:

- Identificación de los escenarios empresariales clave para Exchange online dentro del grupo empresarial.
- Actividades de anuncios para informar a los usuarios de las expectativas y escalas de tiempo del uso de Exchange Online para departamentos y equipos de trabajo o proyectos.
- Migrar buzones locales de los miembros del grupo empresarial a Exchange Online.
- Entrega de formación de los usuarios en Exchange online o vínculos a recursos para presentar Exchange Online y cómo usarlo.
- Un mecanismo de comentarios, como un equipo central de Microsoft Teams que contenga a todos los usuarios del grupo empresarial, para recopilar comentarios y actuar en problemas de los usuarios del grupo empresarial.

Durante la implementación, puede perfeccionar los materiales de administración de cambios a fin de preparar la implementación en toda la organización.

#### <a name="result"></a>Resultado

Un grupo de negocio está en funcionamiento con Exchange Online y los materiales de administración de cambios se han probado y perfeccionado.

## <a name="phase-3-drive-value"></a>Fase 3: Impulsar el valor

En esta fase, completará la implementación de Exchange Online y apoyará a los usuarios para que les ayuden a obtener sus ventajas.

### <a name="step-1-roll-out-exchange-online-to-the-rest-of-your-organization"></a>Paso 1: implementar Exchange online en el resto de la organización

La implementación para el resto de su organización tiene que incluir lo siguiente:

- Identificación de los escenarios empresariales clave para Exchange online en grupos empresariales independientes.
- Uso de los materiales de administración de cambios perfeccionados para las actividades de anuncios para informar a la organización de las expectativas y escalas de tiempo del uso de Exchange Online.
- Migración de los buzones del resto de la organización a Exchange Online.
- Entregar formación de los usuarios en Exchange online o proporcionar vínculos a recursos para presentar Exchange Online y cómo usarlo.
- Un mecanismo de comentarios, como un equipo central que contenga a todos los usuarios, para recopilar comentarios y corregir los problemas de los usuarios de la organización. Si su organización tiene menos de 2500 personas, use un canal público en Teams. En caso contrario, use un grupo público en Yammer.

#### <a name="result"></a>Resultado

Su organización está en funcionamiento y su estrategia de administración de cambios está implementada para informar, entrenar y permitir que los usuarios usen Exchange Online.

### <a name="step-2-measure-usage-manage-satisfaction-and-drive-adoption"></a>Paso 2: Medir el uso, administrar la satisfacción y fomentar la adopción

Después de implementar Exchange online en toda la organización, debe seguir usando su estrategia de administración de cambios para:

- Hacer que su liderazgo promocione Exchange online como la herramienta principal para la programación y la comunicación individual y de corta duración.
- Anime a los usuarios a usarlo para el grupo de negocio, el Departamento, el trabajo y las comunicaciones, el calendario y la colaboración del equipo del proyecto.

Estas son algunas actividades sugeridas:

- Vea la [Guía de adopción de Office 365](https://aka.ms/successfactors) para obtener información sobre procedimientos recomendados generales para la adopción de servicios en la nube. 
- Vea [Informes de actividades de Office 365](https://docs.microsoft.com/office365/admin/activity-reports/activity-reports) para comprender el uso del servicio de Office 365 en toda la organización. Si no es administrador global de Office 365 de su organización, pida a alguien que lo sea que le conceda permisos de lectura de informes a su cuenta de usuario para que pueda tener acceso a los informes de actividades.
- Supervise su centro de comentarios (un canal público en un equipo central de Microsoft Teams o Yammer) para conocer los problemas y los comentarios de los usuarios sobre su experiencia con Exchange Online. Resuelva las preguntas y los problemas tan pronto como pueda evitar que los individuos frustrados y demostrar la compatibilidad para el lanzamiento.
- Identificar y cultivar a los expertos en cada grupo empresarial y resaltar sus logros y procedimientos recomendados con Exchange Online. Reflejar sus éxitos en la organización para mostrar el éxito y la adopción del proyecto. La aprobación por parte de líderes técnicos dentro de un grupo de negocio puede ejercer una influencia eficaz sobre los líderes y los colegas.

#### <a name="result"></a>Resultado

Su organización ha adoptado Exchange online como una herramienta de programación y comunicación de corta duración y grupo de tamaño reducido principal.

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Cómo Microsoft migra a Microsoft 365 Enterprise

Para obtener una ojeada dentro de Microsoft y saber cómo migra la compañía a Exchange Online y está usando Exchange Online Protection para protegerse contra ataques cibernéticos, consulte:

- [Microsoft migra 150.000 buzones a Exchange Online](https://www.microsoft.com/itshowcase/Article/Content/577/Microsoft-migrates-150000-mailboxes-to-Exchange-Online)
- [Microsoft uses threat intelligence to protect, detect, and respond to threats](https://www.microsoft.com/itshowcase/Article/Content/934/Microsoft-uses-threat-intelligence-to-protect-detect-and-respond-to-threats) (Microsoft usa inteligencia de amenazas para proteger, detectar y responder a las amenazas)
- [Microsoft thwarts phishing attempts with Office 365](https://www.microsoft.com/itshowcase/Article/Content/956/Microsoft-thwarts-phishing-attempts-with-Office-365) (Microsoft frustra intentos de suplantación de identidad (phishing) con Office 365)

## <a name="next-steps"></a>Pasos siguientes

Consulte estos recursos para el mantenimiento continuo de Exchange Online:

- [Centro de administración de Exchange en Exchange Online](https://technet.microsoft.com/library/jj200743(v=exchg.150).aspx) 
- [Supervisión, informes y seguimiento de mensajes en Exchange Online](https://technet.microsoft.com/library/jj200725(v=exchg.150).aspx)
- [Hacer una copia de seguridad del correo electrónico en Exchange Online](https://technet.microsoft.com/library/dn440734(v=exchg.150).aspx) 
