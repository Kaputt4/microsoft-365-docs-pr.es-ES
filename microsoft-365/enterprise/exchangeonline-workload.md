---
title: La implementación de Exchange en línea para Microsoft 365 Enterprise
author: JoeDavies-MSFT
manager: laurawi
ms.date: 06/28/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- Strat_O365_Enterprise
description: Paso a través del proceso de planeación, implantar e impulsa el valor de Exchange Online de Microsoft 365 Enterprise en toda la organización.
ms.openlocfilehash: aafa1b28546eb77938bb3e4a5ebe9ccd60b9a60b
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2019
ms.locfileid: "26871781"
---
# <a name="deploy-exchange-online-for-microsoft-365-enterprise"></a>La implementación de Exchange en línea para Microsoft 365 Enterprise

Exchange Online es el servicio de nube principal para el correo electrónico y calendario que ayuda a los usuarios colaboran en formas que no requieren charlar en tiempo real o centralizados de almacenamiento de documentos. Exchange Online es cómo hacer programación y comunicación de corta duración del grupo individuales y pequeñas y es un elemento clave de la integrada para el valor de trabajo en equipo de Microsoft 365 Enterprise. Exchange Online le permite realizar más información y trabajar más eficazmente con la aplicación de Outlook Well-known, independientemente de qué dispositivo se encuentra en.

Exchange Online también cuenta con avanzadas capacidades de seguridad incluyen anti-malware y filtrado contra correo no deseado para proteger los buzones de correo y capacidades de prevención de pérdida de datos que impiden que los usuarios por error enviar información confidencial a personas no autorizadas. Seguridad de Exchange Online es un elemento clave del valor de seguridad inteligente de Microsoft 365 Enterprise.

Si es nuevo en Exchange Online, consulte [Microsoft Exchange Online](https://products.office.com/exchange/exchange-online).

Las fases y los pasos siguientes le guían por el proceso de previsión la función de Exchange Online en su organización, la incorporación de la organización a Exchange Online a través de una serie de las implantaciones progresivas y que dirigen el uso de Exchange Online y su valor a los usuarios finales.

>[!Note]
>Deben seguir estas instrucciones de implementación sólo una vez completada la [Fase 2-Identity](identity-infrastructure.md) de la infraestructura de Microsoft 365 Enterprise foundation.
>

## <a name="phase-1-envision"></a>Fase 1: Planear

En esta fase, recopilar a las personas para su implementación de Exchange Online y determinar cómo va a usar la organización Exchange Online a solucionar las necesidades de negocio.

### <a name="step-1-gather-your-exchange-online-deployment-members"></a>Paso 1: Recopilar a los miembros de su implementación de Exchange Online

Para una implementación correcta de Exchange Online en la parte superior [Fase 2-Identity](identity-infrastructure.md) de la infraestructura de Microsoft 365 Enterprise foundation, debe obtener las personas adecuadas para la entrada y los comentarios. Las personas claves son responsables de decisiones empresariales, el personal de TI, como los arquitectos y los implementadores y abogados para los usuarios finales. 

Estos tres grupos Asegúrese de que la implementación de Exchange Online incluye consideraciones referentes a las necesidades empresariales, aspectos técnicos de seguridad y la migración de buzones de correo y que el resultado será algo que va a usar los usuarios típicos.

#### <a name="result"></a>Resultado

Una lista de personas que representan los aspectos empresariales, técnicos y de usuario final de la organización.

### <a name="step-2-determine-and-prioritize-your-exchange-online-business-scenarios"></a>Paso 2: Determinar y dar prioridad a los escenarios empresariales Exchange Online

Exchange Online puede usarse para distintos propósitos. Necesita averiguar qué fines se asignan a las necesidades de negocio en los niveles de independientes de su organización, los grupos de negocio, los departamentos o los equipos de trabajo y proyectos individuales. Se debe dirigir Exchange Online para cubrir sus comunicaciones de corta duración del grupo individuales y pequeñas y las necesidades de programación. 

Una manera de ver las ventajas de Exchange Online es examinar cómo personas, un equipo o un equipo de v interactuar hoy mismo y, a continuación, busque un escenario adecuado que proporciona métodos más sencillos para comunicarse, programar reuniones y colaborar. Tenga en cuenta que [Los equipos de Microsoft](teams-workload.md) puede ser una mejor opción para algunos de los escenarios de colaboración.

Exchange Online facilita estos escenarios empresariales estratégicos para Microsoft 365 Enterprise:

- Colaborar en documentos en tiempo real o en su propio tiempo para simplificar el proceso de creación conjunta
- Administrar proyectos, tareas y fechas límite para cumplir con sus objetivos de negocio
- Comprender sus hábitos de trabajo para mejorar su influencia e impacto
- Comunicarse con su equipo para mantenerse informado, solicitar comentarios y facilitar la cohesión y el consenso
- Almacenar y compartir archivos, tanto dentro como fuera de la organización, para trabajar de forma fluida más allá de los límites organizativos
- Trabajar de forma segura en el dispositivo en cualquier momento y lugar para mejorar la productividad, a la vez que mantiene un estilo de trabajo flexible
- Proteger su información y reducir el riesgo de pérdida de datos
- Detectar y proteger contra las amenazas externas 
- Supervisar, informar y analizar la actividad para reaccionar rápidamente para proporcionar seguridad de la organización
- Apoyar a su organización con mayor privacidad y cumplimiento normativo para ajustarse al Reglamento General de Protección de Datos (RGPD)

Para obtener más información, vea [Transformación Digital con Microsoft 365](http://transform.microsoft.com). 

#### <a name="result"></a>Resultado
Una lista de escenarios de Exchange Online que a satisfacer las necesidades de su organización para la comunicación, programación y colaboración de corta duración.

## <a name="phase-2-onboard"></a>Fase 2: Incorporar

En esta fase, planeación de los aspectos técnicos de una implementación de Exchange Online y empezar a implementar para los grupos de usuarios seleccionados.

### <a name="prerequisites-identity-and-device-access-configuration"></a>Requisitos previos: configuración de acceso a dispositivos e identidades

Para proteger el acceso a buzones de Exchange Online, asegúrese de que ha configurado [las directivas de acceso de identidad y dispositivo](identity-access-policies.md) y la [recomendada de directivas de acceso de Exchange Online](secure-email-recommended-policies.md).

### <a name="step-1-complete-your-technical-planning"></a>Paso 1: Completar el planeamiento técnico

Antes de empezar a planear técnica, determine si desea usar FastTrack. Si su organización tiene más de 50 puestos y está participando en un [plan optan](https://technet.microsoft.com/library/dn783224.aspx), puede usar [FastTrack para Microsoft 365](https://fasttrack.microsoft.com/microsoft365), disponible sin costo adicional que le guiarán a través de planeación, implementación y adopción de servicio. O bien, puede completar este trabajo usted mismo mediante los asistentes de incorporación FastTrack, que están disponibles desde [FastTrack](https://fasttrack.microsoft.com/) una vez que inicie sesión con su cuenta de Office 365.

Si va a realizar su propio diseño o junto con FastTrack, debe determinar si la red y la organización están preparados para Exchange Online. Es especialmente importante que cumplen los criterios de salida para redes en su infraestructura de foundation, con especial atención al ancho de banda de Internet, el rendimiento y los retrasos de tráfico para maximizar el rendimiento para el tráfico adicional para Exchange Correo electrónico basado en línea y los datos adjuntos.

Use estos recursos para preparar para los aspectos técnicos de una implementación de Exchange Online: 

- [Formas de migrar varias cuentas de correo electrónico a Office 365](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration)
- [Asesor de migración de correo de Office 365](https://portal.office.com/onboarding/mailsetupadvisor#/) (debe haber iniciado sesión en su suscripción de Office 365)
- [Colaboración en Exchange Online](https://technet.microsoft.com/library/jj983794(v=exchg.150).aspx)
- [Destinatarios en Exchange Online](https://technet.microsoft.com/library/jj200702(v=exchg.150).aspx)

Para comprender mejor seguridad de Exchange Online, revise los siguientes recursos:

- [Permisos de Exchange Online](https://technet.microsoft.com/library/jj200692(v=exchg.150).aspx) 
- [Seguridad y cumplimiento de Exchange Online](https://technet.microsoft.com/library/jj200706(v=exchg.150).aspx) 
- [Protección contra correo no deseado y malware](https://technet.microsoft.com/library/jj200731(v=exchg.150).aspx)

A continuación, use estos recursos para comprender la administración de buzones de correo de Exchange Online:

- [Crear buzones de usuario en Exchange Online](https://technet.microsoft.com/library/jj907304(v=exchg.150).aspx)
- [Administrar los buzones de usuario](https://technet.microsoft.com/library/bb123809(v=exchg.150).aspx) 
- [Crear y administrar grupos de distribución](https://technet.microsoft.com/library/bb124513%28v=exchg.150%29.aspx)

#### <a name="result"></a>Resultado

Comprender la administración, la seguridad y la migración de buzones y está listo para empezar a implantar Exchange Online para los grupos seleccionados en la organización.

### <a name="step-2-run-an-it-pilot"></a>Paso 2: Ejecutar una prueba piloto de TI

En la mayoría de las organizaciones medianas y grandes, debería ejecutar una prueba piloto de TI con las partes interesadas de la fase 1, así como con usuarios pioneros y aficionados técnicos. Durante la prueba piloto de TI:

- Elija un escenario de negocio Exchange Online en el que pueden practicar los participantes pilotos de TI.
- Dar a los participantes pilotos licencias de Office 365 y migrar sus buzones locales a Exchange Online.
- Dar a un conjunto de ejercicios para probar el correo electrónico de Exchange Online, la programación y otras funciones de los participantes pilotos.
- Determinar la estrategia de administración de cambio y producir materiales para estimular la adopción de usuario de toda la organización de Exchange Online. Material de administración del cambio puede incluir texto de anuncio de correo electrónico, los planes de aprendizaje interno, Pósteres Vestíbulo y presentaciones. Estos materiales le informará de su organización acerca de Exchange Online y sus ventajas con los objetivos de uso fuerzas y provocar conocimiento del producto. Vea el artículo [cambiar la estrategia de administración de equipos de Microsoft](https://docs.microsoft.com/MicrosoftTeams/change-management-strategy) para algunas ideas.
- Tienen los participantes pilotos de TI revise los materiales de administración de cambios en función de sus experiencias. Pueden proporcionar sugerencias sobre las mejores prácticas y consejos sobre cómo mejor describen las ventajas de Exchange Online y cómo usar para la comunicación y la programación.

#### <a name="result"></a>Resultado

El piloto de TI en línea de Exchange ha finalizado y los materiales de administración de cambio inicial haya desarrollado, revisados y refinado.

### <a name="step-3-roll-out-to-a-business-group"></a>Paso 3: Implementar en un grupo empresarial

Después de completar al piloto de TI, lleve a cabo Exchange Online a un grupo de trabajo o departamento en la organización. Si su organización usa un servicio de correo electrónico local como el servidor de Exchange, esta implantación consta de migración de buzones de correo. Debe incluir esta implantación:

- Identificación de escenarios empresariales clave para Exchange Online en el grupo de negocio.
- Actividades de anuncio para informar a los usuarios de las expectativas y escalas de tiempo para el uso de Exchange Online para departamentos y grupos de trabajo o proyecto.
- Migración de buzones locales de los miembros del grupo de negocio a Exchange Online.
- Impartir cursos de aprendizaje del usuario en Exchange Online o vínculos a recursos que presentan Exchange Online y cómo usarla.
- Un mecanismo de comentarios, como un equipo central de Microsoft Teams que contenga a todos los usuarios del grupo empresarial, para recopilar comentarios y actuar en problemas de los usuarios del grupo empresarial.

Durante la implementación, puede perfeccionar los materiales de administración de cambios a fin de preparar la implementación en toda la organización.

#### <a name="result"></a>Resultado

Un grupo de negocio es copia de seguridad y ejecución con Exchange Online y los materiales de administración de cambios se han probado y refinado.

## <a name="phase-3-drive-value"></a>Fase 3: Impulsar el valor

En esta fase, completar la implantación de Exchange Online y admitir los usuarios para que puedan obtener su beneficios.

### <a name="step-1-roll-out-exchange-online-to-the-rest-of-your-organization"></a>Paso 1: Desplegar Exchange Online para el resto de la organización

La implementación para el resto de su organización tiene que incluir lo siguiente:

- Identificación de escenarios empresariales clave para Exchange Online dentro de los grupos de trabajo independiente.
- Uso de los materiales de administración de cambio refinada para actividades de anuncio informar a la organización de las expectativas y escalas de tiempo para el uso de Exchange Online.
- Migración de buzones de correo para el resto de la organización a Exchange Online.
- Impartir cursos de aprendizaje del usuario en Exchange Online o proporcionan vínculos a recursos que presentan Exchange Online y cómo usarla.
- Un mecanismo de comentarios, como un equipo central que contenga a todos los usuarios, para recopilar comentarios y corregir los problemas de los usuarios de la organización. Si su organización tiene menos de 2500 personas, use un canal público en Teams. En caso contrario, use un grupo público en Yammer.

#### <a name="result"></a>Resultado

Depende de la organización y ejecución y su estrategia de administración de cambios está en su lugar para informar, aprendizaje y permiten a los usuarios usar Exchange Online.

### <a name="step-2-measure-usage-manage-satisfaction-and-drive-adoption"></a>Paso 2: Medir el uso, administrar la satisfacción e impulsar la adopción

Después de implementar Exchange Online para toda la organización, debe seguir emplear su estrategia de administración de cambios para:

- Tener su liderazgo promover Exchange Online como la principal herramienta para la comunicación individual y de corta duración y programación.
- Anime a las personas a usar para el grupo de negocio, departamento, trabajo y las comunicaciones del equipo, calendario y colaboración de project.

Estas son algunas actividades sugeridas:

- Vea la [Guía de adopción de Office 365](https://aka.ms/successfactors) para obtener información sobre procedimientos recomendados generales para la adopción de servicios en la nube. 
- Vea [Informes de actividades de Office 365](https://docs.microsoft.com/office365/admin/activity-reports/activity-reports) para comprender el uso del servicio de Office 365 en toda la organización. Si no es administrador global de Office 365 de su organización, pida a alguien que lo sea que le conceda permisos de lectura de informes a su cuenta de usuario para que pueda tener acceso a los informes de actividades.
- Supervisar el lugar de comentarios (un canal público en un equipo de los equipos o Yammer central) para problemas y los comentarios de las personas sobre su experiencia con Exchange Online. Direcciones preguntas y problemas antes posible para evitar que a las personas frustradas y demostrar la compatibilidad para la implantación.
- Identificar y fomentar a campeones de cada grupo de negocio y resaltar sus logros y procedimientos recomendados con Exchange Online. Reflejar sus éxitos out en la organización para mostrar la adopción y el éxito del proyecto. Aprobación por responsables técnicos dentro de un grupo de negocio puede influir en eficaces en responsables y compañeros.

#### <a name="result"></a>Resultado

La organización ha adoptado Exchange Online como su comunicación de corta duración del grupo principal de individuales y pequeñas y herramienta de programación.

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Cómo Microsoft utiliza Microsoft 365 Enterprise

Para desplegar dentro de Microsoft y obtenga información sobre cómo la compañía migra a Exchange Online y está usando Exchange Online Protection para proteger frente a ataques de Internet, vea:

- [Microsoft migra 150.000 buzones a Exchange Online](https://www.microsoft.com/itshowcase/Article/Content/577/Microsoft-migrates-150000-mailboxes-to-Exchange-Online)
- [Microsoft uses threat intelligence to protect, detect, and respond to threats](https://www.microsoft.com/itshowcase/Article/Content/934/Microsoft-uses-threat-intelligence-to-protect-detect-and-respond-to-threats) (Microsoft usa inteligencia de amenazas para proteger, detectar y responder a las amenazas)
- [Microsoft thwarts phishing attempts with Office 365](https://www.microsoft.com/itshowcase/Article/Content/956/Microsoft-thwarts-phishing-attempts-with-Office-365) (Microsoft frustra intentos de suplantación de identidad (phishing) con Office 365)

## <a name="next-steps"></a>Pasos siguientes

Consulte estos recursos para el mantenimiento continuado de Exchange Online:

- [Centro de administración de Exchange en Exchange Online](https://technet.microsoft.com/library/jj200743(v=exchg.150).aspx) 
- [Supervisión, informe y seguimiento de mensajes en Exchange Online](https://technet.microsoft.com/library/jj200725(v=exchg.150).aspx)
- [Hacer una copia de seguridad del correo electrónico en Exchange Online](https://technet.microsoft.com/library/dn440734(v=exchg.150).aspx) 
