---
title: Implementación de Exchange Online para Microsoft 365 Enterprise
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/09/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-email-calendar
ms.custom:
- Strat_O365_Enterprise
description: Recorra el proceso de planeación, implementación y impulso del valor de Exchange online en Microsoft 365 Enterprise en toda la organización.
ms.openlocfilehash: 9214796c37e9cb5ca9fcb07ced5db7efd8e0f7d0
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "43634151"
---
# <a name="deploy-exchange-online-for-microsoft-365-enterprise"></a>Implementación de Exchange Online para Microsoft 365 Enterprise

*Esta carga de trabajo está incluida en las versiones E3 y E5 de Microsoft 365 Enterprise*

Exchange Online es el servicio de nube principal para el correo electrónico y el calendario que ayuda a los usuarios a colaborar de formas que no requieran la charla centralizada en tiempo real o el almacenamiento de documentos centralizado. Exchange Online es un elemento clave del valor creado para el trabajo en equipo de Microsoft 365 Enterprise. Exchange Online le permite realizar más tareas y trabajar de forma más eficaz con la aplicación de Outlook conocida, independientemente del dispositivo en el que se haya conectado.

Exchange Online también tiene capacidades de seguridad avanzadas, entre las que se incluyen el filtrado antimalware y contra correo electrónico no deseado para proteger los buzones y las funciones de prevención de pérdida de datos que impiden que los usuarios envíen información confidencial por error a personas no autorizadas. La seguridad de Exchange Online es un elemento clave del valor de seguridad inteligente de Microsoft 365 Enterprise.

Si no está familiarizado con la marca de Exchange online, consulte[Microsoft Exchange Online](https://products.office.com/exchange/exchange-online).

Las siguientes fases y pasos le guiarán a través del proceso de visualización de la función de Exchange online en su organización, la incorporación de su organización a Exchange Online a través de una serie de implementaciones progresivas y el uso de Exchange Online y su valor para los usuarios finales.

>[!Note]
>Estas instrucciones de implementación solo deben seguirse después de haber completado [la fase 2-identidad de la infraestructura básica de Microsoft 365 Enterprise](identity-infrastructure.md).
>

## <a name="phase-1-envision-your-exchange-online-deployment"></a>Fase 1: previsión de la implementación de Exchange Online

En esta fase, recopilará a los usuarios de su implementación de Exchange Online y determinará cómo su organización usará Exchange Online para satisfacer sus necesidades empresariales.

### <a name="step-1-gather-your-exchange-online-deployment-members"></a>Paso 1: recopilar los miembros de implementación de Exchange Online

Para una implementación correcta de Exchange online en la [fase 2: identidad](identity-infrastructure.md) de la infraestructura de Microsoft 365 Enterprise Foundation, debe recopilar a las personas adecuadas para obtener información y comentarios. Entre los responsables clave se incluyen los responsables de decisiones empresariales, el personal de ti, como arquitectos e implementadores, y los defensores de los usuarios finales. 

Estos tres grupos garantizan que la implementación de Exchange Online incluya consideraciones que satisfagan las necesidades empresariales, los aspectos técnicos de la migración y la seguridad de los buzones de correo y que el resultado sea algo que los usuarios típicos usarán.

#### <a name="result"></a>Resultado

Una lista de personas que representan los aspectos empresariales, técnicos y de usuario final de su organización.

### <a name="step-2-determine-and-prioritize-your-exchange-online-business-scenarios"></a>Paso 2: determinar y priorizar los escenarios empresariales de Exchange Online

Exchange Online se puede usar para distintos fines. Debe averiguar qué propósito se asigna a sus necesidades empresariales en los distintos niveles de la organización, los grupos empresariales, los departamentos o los equipos individuales de trabajo y de proyecto. Debe dirigirse a Exchange Online para dirigirse a sus necesidades de comunicación y programación de corta y pequeña vida de grupo. 

Una forma de ver las ventajas de Exchange Online es analizar la forma en que interactúan los individuos, un equipo o un equipo v y, después, encontrar un escenario adecuado que proporcione formas más sencillas de comunicarse, programar reuniones y colaborar. Tenga en cuenta que [Microsoft Teams](teams-workload.md) puede ser una opción mejor para algunos de los escenarios de colaboración.

#### <a name="result"></a>Resultado
Una lista de escenarios de Exchange online que abordan las necesidades de la organización para la comunicación, la programación y la colaboración de corta duración.

## <a name="phase-2-onboard"></a>Fase 2: Incorporar

En esta fase, planeará los aspectos técnicos de una implementación de Exchange Online y empezará a implementarlos en grupos de usuarios seleccionados.

### <a name="prerequisites-identity-and-device-access-configuration"></a>Requisitos previos: configuración de acceso a dispositivos e identidades

Para proteger el acceso a los buzones de Exchange Online, asegúrese de que ha configurado [las directivas de acceso a dispositivos e identidades](identity-access-policies.md) y las [directivas de acceso de Exchange Online recomendadas](secure-email-recommended-policies.md).

### <a name="step-1-complete-your-technical-planning"></a>Paso 1: Completar el planeamiento técnico

Antes de iniciar la planificación técnica, decida si desea usar FastTrack. Si su organización tiene más de 50 puestos y participa en un [plan elegible](https://docs.microsoft.com/fasttrack/O365-fasttrack-benefit-for-office-365), puede usar [FastTrack para Microsoft 365](https://fasttrack.microsoft.com/microsoft365), *disponible sin costo adicional* para guiarle a través de la planeación, la implementación y la adopción de servicios. También puede completar este trabajo usted mismo usando los asistentes de incorporación de FastTrack, que están disponibles en [FastTrack](https://fasttrack.microsoft.com/), después de iniciar sesión con la cuenta de Microsoft 365.

Si va a realizar su propia planeación, o junto con FastTrack, debe determinar si la red y la organización están listas para Exchange Online. Es especialmente importante que cumpla los criterios de salida de la [red en su](networking-infrastructure.md) infraestructura básica para los usuarios conectados a la red de su organización. Preste especial atención a los retrasos en el ancho de banda, el rendimiento y el tráfico de Internet para maximizar el rendimiento del tráfico adicional para el correo electrónico y los datos adjuntos basados en Exchange Online.

Use estos recursos para preparar los aspectos técnicos de un lanzamiento de Exchange Online: 

- [Formas de migrar varias cuentas de correo electrónico a Office 365](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration)
- [Migrar carpetas públicas de Exchange Server a Exchange Online](https://docs.microsoft.com/Exchange/collaboration/public-folders/migrate-to-exchange-online?view=exchserver-2019)
- [Migrar carpetas públicas de Exchange Server a grupos de 365 de Microsoft](https://docs.microsoft.com/Exchange/collaboration/public-folders/batch-migration-to-office-365-groups?view=exchserver-2019)
- [Colaboración en Exchange Online](https://docs.microsoft.com/exchange/collaboration-exo/collaboration-exo)
- [Destinatarios en Exchange Online](https://docs.microsoft.com/exchange/recipients-in-exchange-online/recipients-in-exchange-online)
- [Outlook para iOS y Android](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android)

Para comprender mejor la seguridad en Exchange Online, revise los siguientes recursos:

- [Permisos de Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) 
- [Seguridad y cumplimiento de Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/security-and-compliance) 
- [Protección contra correo no deseado y malware](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spam-and-anti-malware-protection)

A continuación, use estos recursos para comprender la administración de buzones de correo de Exchange Online:

- [Crear buzones de usuario en Exchange Online](https://docs.microsoft.com/exchange/recipients-in-exchange-online/create-user-mailboxes)
- [Administrar los buzones de usuario](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/manage-user-mailboxes) 
- [Crear y administrar grupos de distribución](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)

#### <a name="result"></a>Resultado

Comprender la migración, la seguridad y la administración de buzones de correo y está preparado para comenzar a implementar Exchange online en los grupos seleccionados de la organización.

### <a name="step-2-run-an-it-pilot"></a>Paso 2: Ejecutar una prueba piloto de TI

Para la mayoría de las organizaciones medianas y grandes, debe ejecutar una prueba piloto de TI con las partes interesadas de la fase 1, los pioneros y los entusiastas técnicos. Durante la prueba piloto de TI:

- Proporcionar a los participantes en la prueba piloto licencias de 365 de Microsoft y migrar sus buzones locales a Exchange Online.
- Proporcione a los participantes de la prueba piloto un conjunto de ejercicios para probar el correo electrónico, la programación y otras capacidades de Exchange Online.
- Determine la estrategia de administración de cambios y cree materiales para impulsar la adopción por parte del usuario de Outlook y Exchange online de toda la organización. 
 
  Los materiales para la gestión de cambios pueden incluir anuncios en correos electrónicos, formación interna, carteles en los pasillos y presentaciones. Estos materiales le informarán a su organización sobre Exchange Online y sus ventajas con los objetivos de la sensibilización y el uso. Consulte el artículo sobre la [estrategia de administración de cambios para Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/change-management-strategy) para ver algunas ideas.

- Los participantes de la prueba piloto de TI deben revisar los materiales de administración de cambios en función de su experiencia. Pueden proporcionar sugerencias sobre los procedimientos recomendados y consejos sobre cómo describir mejor las ventajas de Outlook y Exchange Online, y cómo usarla para la comunicación y la programación.

#### <a name="result"></a>Resultado

Su piloto de TI de Exchange Online está completo y los materiales de administración de cambios iniciales se han desarrollado, revisado y perfeccionado.

### <a name="step-3-roll-out-to-a-business-group"></a>Paso 3: Implementar en un grupo empresarial

Una vez completada la prueba piloto de ti, implemente Exchange online en un departamento o grupo de negocio de su organización. Si su organización usa un servicio de correo electrónico local como Exchange Server, esta implementación consta de la migración de buzones. Esta implementación ha de incluir:

- Identificación de los escenarios empresariales clave para Exchange online dentro del grupo empresarial.
- Actividades de anuncios para informar a los usuarios de las expectativas y escalas de tiempo del uso de Exchange Online para departamentos y equipos de trabajo o proyectos.
- Migrar buzones locales de los miembros del grupo empresarial a Exchange Online.
- Proporcionar [formación](https://support.office.com/article/outlook-training-8a5b816d-9052-4190-a5eb-494512343cca) de los usuarios en Outlook o vínculos a recursos para presentar Outlook y cómo usarlo.
- Un mecanismo de comentarios, como un equipo central de Microsoft Teams que contenga a todos los usuarios del grupo empresarial, para recopilar comentarios y actuar en problemas de los usuarios del grupo empresarial.

Durante la implementación, puede perfeccionar los materiales de administración de cambios a fin de preparar la implementación en toda la organización.

#### <a name="result"></a>Resultado

Un grupo de negocio está en funcionamiento con Outlook y Exchange Online, y los materiales de administración de cambios se han probado y perfeccionado.

## <a name="phase-3-drive-value"></a>Fase 3: Impulsar el valor

En esta fase, completará la implementación de Exchange Online y apoyará a los usuarios para que les ayuden a obtener sus ventajas.

### <a name="step-1-roll-out-exchange-online-to-the-rest-of-your-organization"></a>Paso 1: implementar Exchange online en el resto de la organización

La implementación para el resto de su organización tiene que incluir lo siguiente:

- Identificación de los escenarios empresariales clave para Exchange online en grupos empresariales independientes.
- Uso de los materiales de administración de cambios perfeccionados para las actividades de anuncios para informar a la organización de las expectativas y escalas de tiempo del uso de Exchange Online.
- Migración de los buzones del resto de la organización a Exchange Online.
- Proporcionar [formación](https://support.office.com/article/outlook-training-8a5b816d-9052-4190-a5eb-494512343cca) de los usuarios en Outlook o proporcionar vínculos a recursos para presentar Outlook y cómo usarlo.
- Un mecanismo de comentarios, como un equipo central que contenga a todos los usuarios, para recopilar comentarios y corregir los problemas de los usuarios de la organización. Si su organización tiene menos de 2500 personas, use un canal público en Teams. En caso contrario, use un grupo público en Yammer.

#### <a name="result"></a>Resultado

Su organización está en funcionamiento y su estrategia de administración de cambios está implementada para informar, entrenar y permitir que los usuarios usen Exchange Online.

### <a name="step-2-measure-usage-manage-satisfaction-and-drive-adoption"></a>Paso 2: Medir el uso, administrar la satisfacción y fomentar la adopción

Después de implementar Exchange online en toda la organización, debe seguir usando su estrategia de administración de cambios para:

- Hacer que su liderazgo promocione Exchange online como la herramienta principal para la programación y la comunicación individual y de corta duración.
- Anime a los usuarios a usarlo para el grupo de negocio, el Departamento, el trabajo y las comunicaciones, el calendario y la colaboración del equipo del proyecto.

Estas son algunas actividades sugeridas:

- Vea [factores de éxito para Microsoft 365](https://aka.ms/successfactors) para obtener información sobre los procedimientos recomendados generales para la adopción de servicios en la nube. 
- Consulte [Microsoft 365 Reports en el centro de administración](https://docs.microsoft.com/office365/admin/activity-reports/activity-reports) para conocer el uso del servicio en toda la organización. Si no es un administrador global de su organización, pida a alguien que sea administrador global que conceda permisos de lector de informes a su cuenta de usuario para que pueda obtener acceso a los informes de actividades.
- Supervise su centro de comentarios (un canal público en un equipo central de Microsoft Teams o Yammer) para conocer los problemas y los comentarios de los usuarios sobre su experiencia con Exchange Online. Responda a las preguntas y los problemas tan pronto como pueda para prevenir que surja la frustración y demostrar que apoya a los usuarios en la implementación.
- Identificar y cultivar a los expertos en cada grupo empresarial y destacar sus mejores prácticas mediante Outlook. Divulgue su éxito en la organización para demostrar el éxito y la adopción del proyecto. La aprobación por parte de líderes técnicos dentro de un grupo de negocio puede ejercer una influencia eficaz sobre los líderes y los colegas.

#### <a name="result"></a>Resultado

Su organización ha adoptado Exchange Online y Outlook como su principal y la herramienta de programación y comunicación de corta duración y grupo reducido.

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Cómo Microsoft utiliza Microsoft 365 Enterprise

Para echar un vistazo dentro de Microsoft y saber cómo migramos a Exchange Online y estamos usando Exchange Online Protection para proteger contra ataques cibernéticos, consulte:

- [Microsoft migra 150.000 buzones a Exchange Online](https://www.microsoft.com/itshowcase/Article/Content/577/Microsoft-migrates-150000-mailboxes-to-Exchange-Online)
- [Microsoft uses threat intelligence to protect, detect, and respond to threats](https://www.microsoft.com/itshowcase/Article/Content/934/Microsoft-uses-threat-intelligence-to-protect-detect-and-respond-to-threats) (Microsoft usa inteligencia de amenazas para proteger, detectar y responder a las amenazas)
- [Microsoft thwarts phishing attempts with Office 365](https://www.microsoft.com/itshowcase/Article/Content/956/Microsoft-thwarts-phishing-attempts-with-Office-365) (Microsoft frustra intentos de suplantación de identidad (phishing) con Office 365)

## <a name="next-steps"></a>Pasos siguientes

Consulte estos recursos para el mantenimiento continuo de Exchange Online:

- [Centro de administración de Exchange en Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center) 
- [Supervisión, informes y seguimiento de mensajes en Exchange Online](https://docs.microsoft.com/exchange/monitoring/monitoring)
- [Haga una copia de seguridad del correo electrónico en Exchange Online](https://docs.microsoft.com/exchange/back-up-email) 
