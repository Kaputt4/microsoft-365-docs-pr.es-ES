---
title: Tareas rápidas para empezar a trabajar con el cumplimiento en Microsoft Purview
description: Obtenga información sobre las tareas que le ayudarán a empezar a trabajar rápidamente con el cumplimiento en Microsoft Purview.
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
f1.keywords:
- NOCSH
ms.collection:
- m365-security-compliance
- m365initiative-compliance
ms.custom:
- admindeeplinkDEFENDER
- intro-get-started
ms.localizationpriority: medium
ms.openlocfilehash: cb8471ffea418ac47921777a0ee9594fa73fe4ac
ms.sourcegitcommit: a5e75d7f7651313818bd2de292d5c38b290d8975
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/07/2022
ms.locfileid: "65930227"
---
# <a name="quick-tasks-for-getting-started-with-compliance-in-microsoft-purview"></a>Tareas rápidas para empezar a trabajar con el cumplimiento en Microsoft Purview

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

Si no está familiarizado con Microsoft Purview y se pregunta por dónde empezar, en este artículo se proporcionan instrucciones sobre los conceptos básicos y se priorizan las tareas de cumplimiento importantes. Este artículo le ayudará a empezar a administrar y supervisar rápidamente los datos, proteger la información y minimizar los riesgos internos.

Este artículo también resulta útil si está averiguando cuál es la mejor manera de administrar los riesgos, proteger los datos y seguir cumpliendo con las normativas y estándares con un personal recién remoto. Los empleados ahora colaboran y se conectan entre sí de nuevas maneras, y este cambio significa que es posible que los procesos y controles de cumplimiento existentes necesiten adaptarse. La identificación y administración de estos nuevos riesgos de cumplimiento dentro de la organización es fundamental para proteger los datos y minimizar las amenazas y riesgos.

Una vez completadas estas tareas básicas de cumplimiento, considere la posibilidad de ampliar la cobertura de cumplimiento en su organización mediante la implementación de soluciones adicionales de Microsoft Purview.

## <a name="task-1-configure-compliance-permissions"></a>Tarea 1: Configurar permisos de cumplimiento

Es importante administrar quién de su organización tiene acceso al portal de cumplimiento de Microsoft Purview para ver el contenido y realizar tareas de administración. Microsoft 365 proporciona roles administrativos específicos del cumplimiento y para usar las herramientas incluidas en el portal de cumplimiento de Microsoft Purview.

Empiece por asignar permisos de cumplimiento a los usuarios de su organización para que puedan realizar estas tareas y evitar que personas no autorizadas tengan acceso a áreas fuera de sus responsabilidades. Querrá asegurarse de que ha asignado a las personas adecuadas al **administrador de datos de cumplimiento** y a los roles de administrador de **cumplimiento** antes de empezar a configurar e implementar soluciones de cumplimiento incluidas con Microsoft 365. También tendrá que asignar usuarios al rol de lector global de Azure Active Directory para ver los datos en el Administrador de cumplimiento.

Para obtener instrucciones paso a paso para configurar permisos y asignar personas a roles de administrador, consulte [Permisos en el Centro de cumplimiento de seguridad &](/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).

## <a name="task-2-know-your-state-of-compliance"></a>Tarea 2: Conocer el estado de cumplimiento

Es difícil saber a dónde ir si no sabes dónde estás. Satisfacer sus necesidades de cumplimiento incluye comprender el nivel actual de riesgo y qué actualizaciones pueden ser necesarias en estos tiempos en constante cambio. Tanto si su organización es nueva en los requisitos de cumplimiento como si tiene una amplia experiencia con estándares y regulaciones que rigen el sector, lo mejor que puede hacer para mejorar el cumplimiento es comprender dónde se encuentra su organización.

[El Administrador de cumplimiento de Microsoft Purview](/microsoft-365/compliance/compliance-manager) puede ayudarle a comprender la posición de cumplimiento de su organización y resaltar las áreas que pueden necesitar mejoras. El Administrador de cumplimiento usa un panel centralizado para calcular una puntuación basada en riesgos, midiendo el progreso en la realización de acciones que ayudan a reducir los riesgos relacionados con la protección de datos y los estándares normativos. También puede usar el Administrador de cumplimiento como herramienta para realizar un seguimiento de todas las evaluaciones de riesgos. Ofrece funciones de flujo de trabajo que le permiten completar de manera eficiente las evaluaciones de riesgos a través de una herramienta común.

Para obtener instrucciones paso a paso para empezar a trabajar con el Administrador de cumplimiento, consulte [Introducción al Administrador de cumplimiento](/microsoft-365/compliance/compliance-manager-setup).

> [!IMPORTANT]
> La seguridad y el cumplimiento están estrechamente integrados para la mayoría de las organizaciones. Es importante que su organización aborde las áreas básicas de seguridad, protección contra amenazas y administración de identidades y acceso para ayudar a proporcionar un enfoque de defensa en profundidad para la seguridad y el cumplimiento.
>
> Compruebe la [Puntuación de seguridad de Microsoft 365](/microsoft-365/security/defender/microsoft-secure-score) en el <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">portal de Microsoft 365 Defender</a> y complete las tareas descritas en los artículos siguientes:
>
> - [Hoja de ruta de seguridad: prioridades principales para los primeros 30 días, 90 días y posteriores](/microsoft-365/security/office-365-security/security-roadmap)
> - [12 tareas principales para que los equipos de seguridad admitan el trabajo desde casa](/microsoft-365/security/top-security-tasks-for-remote-work)

## <a name="task-3-enable-auditing-for-your-organization"></a>Tarea 3: Habilitar la auditoría para su organización

Ahora que ha determinado el estado actual de la organización y quién puede administrar las funciones de cumplimiento, el siguiente paso es asegurarse de que tiene los datos para llevar a cabo investigaciones de cumplimiento y generar informes para las actividades de red y de usuario en su organización. La habilitación de la auditoría también es un requisito previo importante para las soluciones de cumplimiento que se tratarán más adelante en este artículo.

La información proporcionada por el registro de auditoría es una herramienta valiosa para ayudar a ajustar los requisitos de cumplimiento a las soluciones que pueden ayudarle a administrar y supervisar las áreas de cumplimiento que necesitan mejoras. El registro de auditoría debe estar habilitado antes de que se registren las actividades y para poder buscar en el registro de auditoría. Cuando se habilita, la actividad de usuario y administrador de su organización se registra en el registro de auditoría y se conserva durante 90 días y hasta un año, en función de la licencia asignada a los usuarios.

Para obtener instrucciones paso a paso para activar la auditoría, consulte [Activar o desactivar la búsqueda de registros de auditoría](/microsoft-365/compliance/turn-audit-log-search-on-or-off).

## <a name="task-4-create-policies-to-alert-you-about-potential-compliance-issues"></a>Tarea 4: Crear directivas para alertarle sobre posibles problemas de cumplimiento

Microsoft proporciona varias directivas de alertas integradas que ayudan a identificar el abuso de permisos de administrador, la actividad de malware, las posibles amenazas externas e internas y los riesgos de administración del ciclo de vida de los datos. Estas directivas están activadas de forma predeterminada, pero es posible que tenga que configurar alertas personalizadas para ayudar a administrar los requisitos de cumplimiento específicos de su organización.

Use las herramientas de directiva de alertas y panel de alertas para crear directivas de alertas personalizadas y ver las alertas generadas cuando los usuarios realizan actividades que coinciden con las condiciones de la directiva. Algunos ejemplos podrían ser el uso de directivas de alerta para realizar un seguimiento de las actividades de usuario y administrador que afectan a los requisitos de cumplimiento, los permisos y los incidentes de pérdida de datos en la organización.

Para obtener instrucciones paso a paso para crear directivas de alerta personalizadas, consulte [Directivas de alerta en el Centro de seguridad y cumplimiento](/microsoft-365/compliance/alert-policies).

## <a name="task-5-classify-and-protect-sensitive-data"></a>Tarea 5: Clasificación y protección de datos confidenciales

Para realizar su trabajo, las personas de su organización colaboran con otras tanto dentro como fuera de la organización. Esto significa que el contenido ya no se queda detrás de un firewall, sino que puede desplazarse a todas partes, a través de dispositivos, aplicaciones y servicios. Y cuando se desplaza, usted quiere que lo haga de una forma segura y protegida que cumpla con las directivas empresariales y de cumplimiento de normas de su organización.

[Las etiquetas de confidencialidad](/microsoft-365/compliance/sensitivity-labels) le permiten clasificar y proteger los datos de su organización, a la vez que se asegura de que la productividad del usuario y su capacidad de colaboración no se ve obstaculizada. Use etiquetas de confidencialidad para aplicar restricciones de cifrado y uso, aplique marcas visuales y proteja la información entre plataformas y dispositivos, en el entorno local y en la nube.

Para obtener instrucciones paso a paso para configurar y usar etiquetas de confidencialidad, consulte [Introducción a las etiquetas de confidencialidad](/microsoft-365/compliance/get-started-with-sensitivity-labels).

## <a name="task-6-configure-retention-policies"></a>Tarea 6: Configurar directivas de retención

Una [directiva de retención](/microsoft-365/compliance/retention) le permite decidir de forma proactiva si desea conservar contenido, eliminar contenido o ambos, conservar y, a continuación, eliminar el contenido al final de un período de retención especificado. Estas acciones podrían ser necesarias para cumplir con las regulaciones del sector y las directivas internas, y para reducir el riesgo en caso de litigio o una infracción de seguridad.

Cuando el contenido está sujeto a una directiva de retención, los usuarios pueden seguir editando y trabajando con el contenido como si no hubiera cambiado nada. El contenido se conserva en su lugar, en su ubicación original. Pero si alguien edita o elimina el contenido que está sujeto a la directiva de retención, se guarda una copia del contenido original en una ubicación segura donde se conserva mientras la directiva de retención de ese contenido está en vigor.

Puede establecer rápidamente directivas de retención para varios servicios en el entorno de Microsoft 365 que incluyen mensajes de Teams y Yammer, correo de Exchange, sitios de SharePoint y cuentas de OneDrive. No hay límites en el número de usuarios, buzones o sitios que una directiva de retención puede incluir automáticamente. Pero si necesita obtener más selectiva, puede hacerlo configurando un ámbito adaptable basado en consultas para dirigirse dinámicamente a instancias específicas, o bien un ámbito estático que especifique instancias específicas para incluir o excluir siempre.

Para obtener instrucciones paso a paso para configurar directivas de retención, consulte [Creación y configuración de directivas de retención](/microsoft-365/compliance/create-retention-policies). Dado que las directivas de retención constituyen la piedra angular de una estrategia de administración del ciclo de vida de datos para aplicaciones y servicios de Microsoft 365, consulte también [Introducción a la administración del ciclo de vida de datos](/microsoft-365/compliance/get-started-with-data-lifecycle-management).

## <a name="task-7-configure-sensitive-information-and-inappropriate-language-policies"></a>Tarea 7: Configurar información confidencial y directivas de lenguaje inadecuadas

La protección de información confidencial y la detección y actuación sobre incidentes de acoso en el lugar de trabajo es una parte importante del cumplimiento de las directivas y estándares internos. [El cumplimiento de comunicaciones](/microsoft-365/compliance/communication-compliance) en Microsoft Purview ayuda a minimizar estos riesgos, ya que le ayuda a detectar, capturar y tomar medidas de corrección rápidas para el correo electrónico y las comunicaciones de Microsoft Teams. Estas incluyen comunicaciones inapropiadas que contienen palabras soeces, amenazas y acoso y comunicaciones que comparten información confidencial dentro y fuera de su organización.

Una plantilla de directiva de *texto de detección* predefinida permite examinar las comunicaciones internas y externas en busca de coincidencias de directivas para que puedan ser examinadas por revisores designados. Los revisores pueden investigar el correo electrónico digitalizado, Microsoft Teams, Yammer o las comunicaciones de terceros de su organización y tomar las medidas de corrección adecuadas para asegurarse de que cumplen los estándares de su organización.

La plantilla de directiva *Detección de información confidencial* predefinida le ayuda a crear rápidamente una directiva para examinar el correo electrónico y las comunicaciones de Microsoft Teams que contienen tipos de información confidencial definidos o palabras clave para asegurarse de que los datos importantes no se comparten con personas que no deben tener acceso. Estas actividades podrían incluir comunicaciones no autorizadas sobre proyectos confidenciales o normas específicas del sector sobre comercio interno u otras actividades de colusión.

Para obtener instrucciones paso a paso para planear y configurar el cumplimiento de las comunicaciones, consulte [Plan for communication compliance (Planear el cumplimiento de comunicaciones](/microsoft-365/compliance/communication-compliance-plan) ) y [Get started with communication compliance (Introducción al cumplimiento de comunicaciones](/microsoft-365/compliance/communication-compliance-configure)). Para obtener información sobre las licencias de cumplimiento de comunicaciones, consulte [Guía de licencias de Microsoft 365 para el cumplimiento de & de seguridad](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#communication-compliance).

## <a name="task-8-see-whats-happening-with-your-sensitive-items"></a>Tarea 8: Ver lo que sucede con los elementos confidenciales

Las etiquetas de confidencialidad, los tipos de información confidencial, las etiquetas y directivas de retención y los clasificadores entrenables se pueden usar para clasificar y etiquetar elementos confidenciales en Exchange, SharePoint y OneDrive, como ha visto en las tareas anteriores. El último paso del recorrido rápido de la tarea es ver qué elementos se han etiquetado y qué acciones están llevando a cabo los usuarios en esos elementos confidenciales. [el explorador de contenido](/microsoft-365/compliance/data-classification-content-explorer) y el [explorador de actividad](/microsoft-365/compliance/data-classification-activity-explorer) proporcionan esta visibilidad.

### <a name="content-explorer"></a>Explorador de contenido

El Explorador de contenido permite ver, en su formato nativo, todos los elementos que se han clasificado como un tipo de información confidencial o que pertenecen a una clasificación determinada mediante un clasificador entrenable, y todos los elementos que tienen aplicada la etiqueta de confidencialidad o retención.

Para obtener instrucciones paso a paso sobre cómo usar el explorador de contenido, consulte [Información general sobre la clasificación de datos de los datos](/microsoft-365/compliance/data-classification-overview) y [Introducción al explorador de contenido](/microsoft-365/compliance/data-classification-content-explorer).

### <a name="activity-explorer"></a>Explorador de actividad

El explorador de actividad le ayuda a supervisar lo que se está haciendo con los elementos confidenciales clasificados y etiquetados en:

- SharePoint
- Exchange
- OneDrive

Hay más de 30 filtros diferentes disponibles, estos son algunos:

- Intervalo de fechas:
- TIPO DE ACTIVIDAD
- Ubicación
- Usuario
- Etiqueta de confidencialidad
- Etiqueta de retención:
- ruta de acceso del archivo
- Directiva DLP

Para obtener instrucciones paso a paso sobre cómo usar el explorador de actividad, consulte [Introducción al explorador de actividades](/microsoft-365/compliance/data-classification-activity-explorer).

## <a name="next-steps"></a>Pasos siguientes

Ahora que ha configurado los conceptos básicos para la administración de cumplimiento de su organización, tenga en cuenta las siguientes soluciones de cumplimiento en Microsoft Purview para ayudarle a proteger la información confidencial y a detectar y actuar sobre riesgos internos adicionales.

### <a name="configure-retention-labels"></a>Configurar etiquetas de retención

Mientras que las directivas de retención se aplican automáticamente a todos los elementos en el nivel de contenedor (como sitios de SharePoint, buzones de usuario, etc.), [las etiquetas de retención](/microsoft-365/compliance/retention#retention-labels) se aplican a elementos individuales, como un documento de SharePoint o un mensaje de correo electrónico. Puede aplicar estas etiquetas de forma manual o automática.

Las etiquetas de retención se pueden usar como parte de la estrategia de gobernanza de datos para conservar lo que necesita y eliminar lo que no. Use estas etiquetas cuando necesite excepciones a las directivas de retención cuando documentos o correos electrónicos específicos necesiten una configuración de retención o eliminación diferente. Por ejemplo, la directiva de SharePoint conserva todos los documentos durante tres años, pero los documentos empresariales específicos deben conservarse durante cinco años. Para obtener más información, consulte [Creación de etiquetas de retención para las excepciones a las directivas de retención](/microsoft-365/compliance/create-retention-labels-data-lifecycle-management).

Sin embargo, las etiquetas de retención, cuando se usan con [la administración de registros](/microsoft-365/compliance/records-management), proporcionan muchas más opciones de administración para admitir documentos y correos electrónicos en el nivel de elemento. Este nivel de administración de datos es adecuado para elementos de alto valor para los requisitos empresariales, legales o normativos de mantenimiento de registros. Para obtener más información, consulte [Introducción a la administración de registros](/microsoft-365/compliance/get-started-with-records-management).

### <a name="identify-and-define-sensitive-information-types"></a>Identificación y definición de tipos de información confidencial

Defina tipos de información confidencial en función del patrón contenido en la información de los datos de la organización. Usar [tipos de información confidencial integrados](./sensitive-information-type-entity-definitions.md) ayuda a identificar y proteger los números de tarjeta de crédito, los números de cuenta bancaria, los números de pasaporte y mucho más. O bien, cree sus propios [tipos de información de confidencialidad personalizados](/microsoft-365/compliance/create-a-custom-sensitive-information-type) específicos de su organización.

Para obtener instrucciones paso a paso para definir tipos de información confidencial personalizados, consulte [Creación de un tipo de información confidencial personalizada en el Centro de cumplimiento de seguridad &](./create-a-custom-sensitive-information-type.md).

### <a name="prevent-data-loss"></a>Prevenir la pérdida de datos

[Las directivas de prevención de pérdida de datos (DLP) de Microsoft Purview](/microsoft-365/compliance/dlp-learn-about-dlp) permiten identificar, supervisar y proteger automáticamente la información confidencial en toda la organización de Microsoft 365. Use directivas DLP para identificar elementos confidenciales en los servicios de Microsoft, evitar el uso compartido accidental de elementos confidenciales y ayudar a los usuarios a aprender a cumplir las normas sin interrumpir su flujo de trabajo.

Para obtener instrucciones paso a paso para configurar directivas DLP, [cree, pruebe y ajuste una directiva DLP](/microsoft-365/compliance/create-test-tune-dlp-policy). Para obtener información sobre las licencias de administración de pérdida de datos, consulte [Guía de licencias de Microsoft 365 para el cumplimiento de & de seguridad](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#office-365-data-loss-prevention-for-exchange-online-sharepoint-online-and-onedrive-for-business).

### <a name="detect-and-act-on-insider-risks"></a>Detectar y actuar sobre riesgos internos

Cada vez más, los empleados tienen acceso creciente para crear, administrar y compartir datos en un amplio espectro de plataformas y servicios. En la mayoría de los casos, las organizaciones tienen recursos y herramientas limitados para identificar y mitigar los riesgos de toda la organización, a la vez que cumplen los requisitos de cumplimiento y los estándares de privacidad de los empleados. Estos riesgos pueden incluir el robo de datos al dejar a los empleados y la pérdida de información fuera de su organización por uso compartido accidental o intenciones malintencionadas.

[La administración de riesgos](/microsoft-365/compliance/insider-risk-management-policies) internos usa toda la amplitud del servicio y los indicadores de terceros para ayudarle a identificar, evaluar y actuar rápidamente en la actividad de usuario de riesgo. Al usar registros de Microsoft 365 y Microsoft Graph, la administración de riesgos internos le permite definir directivas específicas para identificar indicadores de riesgo y tomar medidas para mitigar estos riesgos.

Para obtener instrucciones paso a paso para planear y configurar directivas de administración de riesgos internos, consulte [Planeamiento de la administración de riesgos internos](/microsoft-365/compliance/insider-risk-management-plan) y [Introducción a la administración de riesgos](/microsoft-365/compliance/insider-risk-management-configure) internos. Para obtener información sobre las licencias de administración de riesgos internos, consulte [Guía de licencias de Microsoft 365 para el cumplimiento de & de seguridad](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#insider-risk-management).
